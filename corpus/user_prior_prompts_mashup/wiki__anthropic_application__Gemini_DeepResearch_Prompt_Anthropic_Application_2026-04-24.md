# Gemini Deep Research Prompt: Anthropic Prompt Engineer Application Briefing Pack

**Use:** paste the content between the two "PROMPT START" and "PROMPT END" markers into Google Gemini Deep Research. Select the Deep Research mode (not the default chat mode). Approve the research plan when Gemini presents it, or tell it to proceed.

**Expected runtime:** 8 to 20 minutes.

**Re-ingestion path:** the output document returns to this Claude project as input for resume tailoring, cover letter drafting, the "Why Anthropic" essay, and the required application form answer about a prompt engineering challenge.

---

## PROMPT START

You are a senior research analyst building a pre-interview briefing pack for a candidate applying to the role **Prompt Engineer, Agent Prompts & Evals at Anthropic** (Greenhouse requisition 5107121008, based in San Francisco or New York City, posted as of April 2026). The candidate is strong and will do their own final synthesis. Your job is to hand them raw, sourced, trustworthy material, not a polished narrative.

Another AI agent will re-ingest your output, so structure matters more than prose.

### Role snapshot (already captured, for grounding only)

The role sits in product engineering. Responsibilities include designing and optimizing system prompts, tool prompts, and skills across consumer and API surfaces; building evaluation suites; supporting model launches; mentoring product engineers on prompt engineering; and partnering with research and safeguards. Required: 5+ years Python or similar, demonstrable LLM and prompt engineering experience, evaluation methodology fluency, strong written communication, CI/CD familiarity. Preferred: production experience with Claude or frontier models, ML or NLP background, A/B testing and Statsig, AI safety familiarity, ML tooling experience. Salary band $320k to $405k USD. Full JD URL: https://job-boards.greenhouse.io/anthropic/jobs/5107121008

### Research objectives, ranked by priority

Spend the most effort on the top objectives. If you run out of budget, truncate from the bottom.

1. **Anthropic culture and working style from primary sources.** What does Anthropic say about itself in its own words? Responsible scaling policy, core views posts, how they work as a team, Dario Amodei essays, Jack Clark posts, company values pages. What public statements have Anthropic leaders (Dario, Daniela, Jared Kaplan, Chris Olah, Amanda Askell, others) made about hiring, culture, communication norms, and big-science research style?

2. **Anthropic interview process, specifically for prompt engineer and product engineer roles.** First-hand candidate reports from the last 18 months: what does the loop look like, what kinds of exercises are given, what do they probe for? Glassdoor, Levels.fyi, candidate blog posts, LinkedIn posts, interviewing.io, Blind (only if the thread has verifiable signal). Separate prompt engineer reports from research scientist or ML engineer reports; do not conflate.

3. **Current state of the art in prompt engineering and LLM evaluations (2024 to 2026).** Techniques practitioners are actually using now: system prompt design patterns, tool-use prompting, agent prompting, skills and subagents, evaluation rubric design, LLM-as-judge methodology, constitutional AI prompting, prompt chaining, retrieval-augmented prompts, context window management, prompt injection defenses. Prefer: Anthropic's own prompt engineering documentation at docs.claude.com, Anthropic's courses and cookbooks on GitHub, papers from Anthropic and OpenAI and DeepMind, and well-known practitioner writeups. Include 2025-2026 developments explicitly.

4. **Claude-specific prompting behaviors and quirks.** What does Anthropic publish about how Claude specifically responds to prompting patterns? Constitutional AI, harmlessness, refusal patterns, long-context performance, extended thinking, artifacts, computer use, MCP, skills. Include links to system prompts Anthropic has published.

5. **Recent Anthropic research and public communications to cite in a "Why Anthropic" essay (200 to 400 words).** Catalog the last 12 months of Anthropic's most quoted work: interpretability papers (Chris Olah's team), model cards, RSP updates, Claude model releases, policy statements, Economic Index data, AUP changes. For each, give a one-sentence summary and the most quotable line (attributed, not paraphrased into invisibility).

6. **AI safety and alignment framing Anthropic uses publicly.** How does Anthropic describe its safety bet relative to other labs? What's the public framing of "race to the top," "beneficial AI," "interpretability as the path," and "responsible scaling"? Where do their public statements on safety and commercialization intersect and where do they seem in tension?

7. **Background noise check: how the broader AI community perceives Anthropic in 2025-2026.** What are the notable, credentialed critiques and endorsements? Stick to sources that meet the social-media filter below.

### Source fidelity rules (strict)

- **Tier 1 (highest trust):** Anthropic's own publications (anthropic.com, alignment.anthropic.com, docs.claude.com, research.anthropic.com), named-author arXiv papers, SEC filings, court filings, official press releases.
- **Tier 2:** Published interviews with named Anthropic employees on established outlets (New York Times, Bloomberg, The Verge, Stratechery, Dwarkesh Patel podcast, Lex Fridman, Hard Fork, Lenny's Newsletter, Every). Named authors, dated within 18 months.
- **Tier 3 (use only with explicit credibility note):** Substack posts by credentialed practitioners, LinkedIn articles by identified ML engineers or researchers, Medium posts with citations.
- **Tier 4 (use only if they meet the quality filter below):** Reddit, Twitter/X, YouTube discussion, Hacker News comments, Glassdoor, Blind.
- **Excluded:** AI-generated content farms, aggregators that restate Tier 1 without adding analysis, anonymous posts without verifiable claims, training-data summaries with no URL, speculative podcasts without transcripts.

### Social media quality filter

Apply this filter before including any Tier 4 source:

- **YouTube:** established channels only. Include Lex Fridman, Dwarkesh Patel, Hard Fork, No Priors, Machine Learning Street Talk, Every Latent Space, Yannic Kilcher, Andrej Karpathy's own uploads, Anthropic's own channel. Exclude low-subscriber reaction videos. For each, extract the specific timestamp and quote if relevant.
- **LinkedIn:** only articles (not status posts) authored by Anthropic employees, alumni, or named ML practitioners with verifiable titles. Engagement floor: 500+ reactions or substantive comment thread with named engineers participating.
- **Twitter/X:** threads of 3+ posts by verified or widely-followed accounts (10k+ followers AND established in ML, safety, or product), posted within the last 18 months, with visible engagement (500+ likes or quote threads by other named practitioners). No screenshots; only linkable threads.
- **Reddit:** r/MachineLearning, r/LocalLLaMA, r/singularity, r/cscareerquestions. Posts must have 100+ upvotes, substantive top-three comments with flair or named authors, and the claim must be verifiable against a Tier 1 or Tier 2 source. If a Reddit thread is the only source for a claim, downgrade the claim to "anecdotal."
- **Hacker News:** only threads with 100+ points and comments by people whose identities can be verified. Prefer threads with participation from Anthropic employees or known researchers.

If a section of your research is thin on high-tier sources, say so. Do not backfill with low-tier material.

### Output format (structured markdown, single document)

Produce ONE markdown document with the following sections, in this order:

```
# Anthropic Prompt Engineer Application Briefing Pack
Generated: [YYYY-MM-DD]
Research mode: Gemini Deep Research
Total sources consulted: [N]
Tier 1 sources: [N] | Tier 2: [N] | Tier 3: [N] | Tier 4: [N]

## 1. Executive Summary
[10 to 15 bullets capturing the most load-bearing findings]

## 2. Anthropic Culture and Working Style
### 2.1 Official self-description
### 2.2 Leadership statements (with quotes and dates)
### 2.3 How they describe their hiring bar
### 2.4 Communication and collaboration norms

## 3. Interview Process for Prompt Engineer and Product Engineer Roles
### 3.1 Loop structure (from candidate reports)
### 3.2 Exercise types encountered
### 3.3 Questions reported (verbatim where possible, attributed to source)
### 3.4 What the bar seems to be, per credible reports

## 4. State of the Art in Prompt Engineering and Evals (2024-2026)
### 4.1 Prompting techniques in active use
### 4.2 Evaluation design patterns
### 4.3 Tools and frameworks (Inspect, Promptfoo, Braintrust, Langfuse, Statsig, others)
### 4.4 Key papers (with 1-sentence summaries)

## 5. Claude-Specific Prompting
### 5.1 What Anthropic's docs teach
### 5.2 Public system prompts and analyses
### 5.3 Known behavioral quirks and how to handle them
### 5.4 Tool use, skills, MCP, extended thinking, artifacts: current guidance

## 6. Quotes Library for "Why Anthropic" Essay
[15 to 25 exact quotes from Anthropic leadership or official channels, each with attribution, date, URL, and a one-line note on why it's useful]

## 7. Recent Anthropic Research and Releases (last 12 months)
[Chronological list. For each: date, title, authors, 1-sentence summary, most quotable line, URL.]

## 8. AI Safety Framing
### 8.1 "Race to the top" public positioning
### 8.2 Responsible Scaling Policy updates
### 8.3 Visible internal tensions (safety vs commercial) from public statements

## 9. External Perceptions (Tier 2 and 3 only)
### 9.1 Notable endorsements
### 9.2 Notable credentialed critiques
### 9.3 Neutral expert synthesis

## 10. Anecdotal Signal (Tier 4, flagged)
[Anything useful from the social filter that survived. Each item flagged as "anecdotal" with the filter criteria it met.]

## 11. Open Questions and Research Gaps
[Things you could not source to Tier 1 or 2. Be explicit.]

## 12. Source Table
[All sources used, numbered, with: URL, tier, date accessed, one-line description. The briefing above references sources by number.]
```

### Hard constraints

- Cite every factual claim with a source number from Section 12.
- Never paraphrase a quote into invisibility: if you use someone's exact wording, quote it. If you paraphrase, do not attach quote marks.
- Do not fabricate. If you cannot find a source for something the candidate might want, put it in Section 11.
- Distinguish Anthropic's own statements from third-party commentary at every turn.
- No em dashes in the output. Use commas, semicolons, colons, or parentheses.
- Do not give the candidate strategic advice ("you should say X in your cover letter"). Give them raw material. The candidate and the downstream agent will do the synthesis.
- Dates: prefer items from 2024, 2025, and 2026. Flag anything older than 2024 as "context, not current."
- If Google Deep Research budget runs out before Section 12 is complete, stop at the current section and explicitly state where the output was truncated.

Begin.

## PROMPT END

---

## Notes for Sage (not part of the Gemini prompt)

1. **Deep Research vs regular Gemini:** the prompt assumes Deep Research mode. If you run it in regular Gemini chat, output quality will drop significantly because regular mode does not fetch sources aggressively.

2. **Approval step:** Gemini will show a research plan before running. Approve it as-is unless it misses Section 5 (Claude-specific) or Section 6 (Quotes Library), which are the two highest-value sections for the application.

3. **Expected output size:** 30 to 60 pages of structured markdown, 100 to 200 sources. Do not truncate it on paste-back; I will ingest the full thing.

4. **Re-ingestion path when you return:** paste the full Gemini output here, or save it as a .md file and attach to the project. I will then:
   - Score findings against Protocol Strict Source Fidelity
   - Quarantine Tier 4 material per Section 3 of the Protocol
   - Feed Sections 2, 3, and 6 into the "Why Anthropic" essay draft
   - Feed Section 4 into the prompt engineering challenge form answer
   - Feed Section 5 into resume bullet refinement

5. **Role mismatch flag (pending your decision):** the URL you gave me is for `Prompt Engineer, Agent Prompts & Evals` (req 5107121008). The project canon (spec.md ACTIVE_VARS) targets `Prompt Engineer, Claude Code` (req 5159669008). This Gemini prompt is engineered for 5107121008. If you want it tuned for 5159669008 instead, or for both in parallel, tell me and I'll produce the variant.
