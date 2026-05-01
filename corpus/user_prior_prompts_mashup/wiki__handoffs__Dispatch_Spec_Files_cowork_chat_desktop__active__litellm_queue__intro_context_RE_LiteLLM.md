# intro_context_RE_LiteLLM.md
# What we already know, distilled. Use this as starting research base.

## 1. LiteLLM general knowledge

LiteLLM is an open-source Python library + standalone proxy server. Project home: github.com/BerriAI/litellm. Stable release line as of early 2026.

### What it does
- Provides a unified Python API across 100+ LLM providers (OpenAI, Anthropic, Google Vertex, Cohere, AWS Bedrock, Azure, local models via Ollama / vLLM, etc.).
- Exposes a single `litellm.completion()` call that translates to whichever provider is configured.
- Proxy mode: runs as a HTTP server (`litellm --model gpt-4`), exposing OpenAI-compatible endpoints. Other apps point to localhost or a deployed proxy URL and think they are talking to OpenAI.

### What the proxy adds beyond direct SDK calls
- Cost tracking and budget caps per user / API key
- Rate limiting and load balancing across multiple model deployments
- Fallback routing: if model A fails, retry on model B
- Caching responses by prompt hash
- Centralized API key management
- Observability: structured logs of every call

### Common architecture pattern
```
Client app  ->  LiteLLM proxy  ->  upstream LLM API (Anthropic, OpenAI, etc.)
                       |
                       +--> cost tracking DB
                       +--> rate limit cache (Redis)
                       +--> fallback config
```

### Failure modes observed in parent project
- `litellm.ServiceUnavailableError: ServiceUnavailableError: Litellm_proxyException` followed by HTML 503 page.
- Indicates: the proxy itself was up enough to return an error envelope, but either (a) upstream LLM API returned 503, or (b) proxy hit its own rate limit, or (c) proxy backend (DB / Redis) was down.
- Recovery in parent project: retry after 60-90 seconds usually worked.

## 2. evaluation platform QC v2 architecture (inferred)

### Stack guess
```
evaluation platform Studio UI (web)  ->  evaluation platform backend  ->  LiteLLM proxy  ->  Anthropic API (most likely)
```

The 503 error gives us: there is at minimum a LiteLLM proxy in the chain. We do not yet know if evaluation platform runs LiteLLM themselves or uses a hosted version.

### QC v2 structure (decoded from observed outputs in parent project, see qc_v2_reverse_graph.md)

**Part 1 - Criteria checks (4 dimensions, runs per-row)**
- ATOMICITY: each row tests exactly one binary check
- SELF_CONTAINMENT (also called Grounding): each row references only content visible in rubric context (system prompt + user turns + the row text itself)
- OBJECTIVE_EVALUABILITY: each row yields binary yes/no
- CONTENT_OVER_PROCESS: each row tests output content not methodology

**Part 2 - Prompt vs Rubric checks (5 dimensions, runs across rubric)**
- PROMPT_GROUNDING: criteria match prompt specificity, no hard-coded model values, no dropped user constraints
- COMPREHENSIVE_COVERAGE: all final-turn requirements covered, all SP standing rules covered (NOTE: misses earlier-turn carry-forward preferences)
- NON_REDUNDANCY: no two rows mechanically test the same content
- DISCARD_APPROPRIATENESS: discards have valid reasons (returns N/A if no discards present, which counts as a structural neutral in green-pattern)
- ADDITION_LEGITIMACY: adds trace to specific quotes (returns N/A if no adds, also structural neutral)

**Part 3 - Justification checks (2 dimensions + per-row specificity)**
- JUSTIFICATION_SPECIFICITY: each justification is prompt-grounded, cites a specific quote
- ENGAGEMENT_QUALITY: justifications differentiate row scope, no verbatim-identical quote strings across rows
- per-row specificity: verdict on whether each row's justification is acceptable

### Known QC v2 blind spots (from parent project)
1. Conditional vacuous-pass: "If response mentions X, does Y" patterns slip through (insight 15, task 881 anchor)
2. Earlier-turn carry-forward preferences: user prefs in T1 / T2 / T3 / T4 / T5 not auto-flagged if final UT does not restate them (T5 insight 6)
3. Atomicity overspecificity: criterion can be unreasonably specific without being flagged (Part 2 PROMPT_GROUNDING tries to catch but misses subtle cases)
4. Justification dedup logic: catches verbatim quote matches but not paraphrases or adjacent SP quotes
5. Studio Modify text-field overwrite: Studio accepts Modify action without text change; QC reads current text and flags downstream
6. Hard-coded model-T1 values: QC has no access to model response history, only sees rubric context (system prompt + user turns + rubric). Cannot verify any value the rubric author got from model T1+ (task 881 hard anchor)
7. ENGAGEMENT_QUALITY ground-truth confusion: when rubric tests model-T1 values that contradict user-misrecall, Part 3 sometimes treats user-misrecall as authoritative and flags rubric as inconsistent (task 881 anchor)

### Format drift (insight 10)
Same input can produce different output formats across runs (prose-per-requirement vs dimension-header-per-verdict) without changing verdicts. Suggests temperature > 0 or non-deterministic format prompting in the underlying QC system prompts.

## 3. evaluation platform QC v2 prompts (educated guesses)

We have NOT seen the actual prompts. Inferred from output structure:

**Part 1 likely structure:**
```
You are a rubric criterion auditor. Evaluate each row on 4 dimensions:
- ATOMICITY ...
- SELF_CONTAINMENT ...
- OBJECTIVE_EVALUABILITY ...
- CONTENT_OVER_PROCESS ...

Output one summary per dimension, then a per-row PASS / FAIL / NEUTRAL verdict.

System Prompt: <embedded SP>
User Turns: <embedded UTs>
Rubric: <embedded rubric>
```

**Part 2 likely structure:**
```
You are a rubric-vs-prompt fit auditor. Evaluate the rubric on 5 dimensions:
- PROMPT_GROUNDING ...
- COMPREHENSIVE_COVERAGE ...
- NON_REDUNDANCY ...
- DISCARD_APPROPRIATENESS ...
- ADDITION_LEGITIMACY ...

Per-row commentary, then per-dimension verdict.
```

**Part 3 likely structure:**
```
You are a justification auditor. Evaluate each justification on:
- JUSTIFICATION_SPECIFICITY ...
- ENGAGEMENT_QUALITY ...
Plus per-row specificity verdict.
```

These are GUESSES. Phase 2 of the new project will refine using observed outputs as inverse-prompt training data.

## 4. Existing parent project corpus available for replica training

Useful artifacts already in parent Rubrics Correction project:
- `qc_v2_reverse_graph.md` - decoded structure (skill file)
- `Rubric_Correction_Task_614_Northbridge_Memo_2026-04-20_CUTPASTE.md` - approved exemplar
- `Rubric_Correction_Task_720_Wrestling_Event_2026-04-21_CUTPASTE_v2_SURGICAL_FIX.md` - hard-fail then green
- `Rubric_Correction_Task_881_Health_Meds_2026-04-21_CUTPASTE_v3_HARD_FIX.md` - latest hard-fail-with-recovery
- `Rubric_Correction_Task_883_LinkedIn_Coach_2026-04-21_CUTPASTE.md` - first-try green
- Multiple QC outputs across these tasks showing Part 1 + 2 + 3 verdicts in different states (green, yellow, red)
- `justify_templates_9forms.md` - the canonical justification forms with dedup rule
- `Mastering_Rubric_Justification_and_Review_Score_Card` - canonical evaluation platform scoring guide

## 5. RL signal availability

Each evaluation platform task has a binary outcome: APPROVED or SENT BACK with edits. This is a clean reward signal:
- APPROVED + green QC = +1 reward
- SENT BACK = -1 reward, with reviewer comments as the "what to fix" diff

For RL stretch (Q5 in setup questions), we have at least 4 task outcomes already to seed training, with more coming as user grinds toward the 1000-task EOD-Wednesday goal.

## 6. unknowns

What we still need from user (Q1-Q5 in questions_to_setup_RE_LiteLLM.md):
- Tech stack preference
- Local vs cloud deployment
- Replica fidelity vs improvement scope
- Corpus access path
- RL ambition

END_INTRO_CONTEXT
