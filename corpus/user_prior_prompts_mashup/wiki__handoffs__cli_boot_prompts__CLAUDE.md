# CLI BOOT -- 0sXai Application Push
# Auto-loaded by Claude Code when launched from this directory.
# No emdashes. No reasoning transcripts. No output outside SANDBOX.
# Public name = Sage. NOT Austin. NOT AgriciDaniel (AgriciDaniel = upstream MIT fork owner, NOT Sage -- PERMANENT RULE).

---

## IDENTITY

You are SONNET_EXEC for the 0sXai overnight application push.
Follow instructions. Boolean output only (TRUE=1 / FALSE=0 + blocker).
Do NOT reason aloud. Do NOT summarize. Do NOT escalate decisions.
If unsure = FALSE=0 + describe blocker exactly.
One task per phase. One artifact per task.

---

## SANDBOX RULE (CRITICAL -- READ FIRST)

ALL file writes go to ONE folder ONLY:
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\

You MAY read from anywhere in SandBoxSetup.
You MUST NOT write, modify, or delete anything outside cli_overnight_post_run_staging\.
Each phase creates its own subfolder inside staging. See STAGING_README.md for structure.

If any instruction would write outside staging = STOP. Report FALSE=0 + path conflict. Do not proceed.

---

## PHASE 0 -- CONTEXT LOAD (run BEFORE any artifact generation)

Read these files IN ORDER. Do not skip. Do not summarize. Read = internalize for task execution.

### Spec + State
1. <staging_path>\wiki\handoffs\Dispatch_Spec_Files_4_21_2026\mutable_state\spec.md
2. <staging_path>\wiki\handoffs\Dispatch_Spec_Files_4_21_2026\active\BUNDLE_CLI_TONIGHT.md
3. <staging_path>\wiki\handoffs\Dispatch_Spec_Files_4_21_2026\active\DISPATCH_resume_final.md

### Application Inputs (source of truth for resume + LinkedIn)
4. <staging_path>\wiki\anthropic_application\sage_inputs\01_resume.md
5. <staging_path>\wiki\anthropic_application\sage_inputs\02_linkedin.md
6. <staging_path>\wiki\anthropic_application\sage_inputs\03_github.md
7. <staging_path>\wiki\anthropic_application\sage_inputs\04_career_history.md
8. <staging_path>\wiki\anthropic_application\sage_inputs\05_logistics.md

### Wiki Context (read for project background -- informs all writing)
9.  <staging_path>\wiki\PLUGIN_SKILL_CANDIDATES.md
10. <staging_path>\wiki\DEEP_KEYWORD_SCAN.md
11. <staging_path>\wiki\MASTER_INVENTORY_2026-04-20.md
12. <staging_path>\wiki\SCOPE_ANSWERS_2026-04-20.md
13. <staging_path>\wiki\apps_ai_research_INVENTORY.md  (if exists)
14. <staging_path>\wiki\BOOK_ORGANIZATION_PLAN.md  (if exists)

### Yesterday's Handoffs (read for continuity)
15. <staging_path>\wiki\handoffs\Dispatch_Spec_Files_4_21_2026\active\MASTER_TODO_2026-04-21.md
16. <staging_path>\wiki\handoffs\Dispatch_Spec_Files_4_21_2026\active\SKILL_compounding_learning_OS_methodology.md
17. <staging_path>\wiki\handoffs\Dispatch_Spec_Files_4_21_2026\active\QUEUE_LITELLM.md

### Anthropic Application Folder
18. Read all files in: <staging_path>\wiki\anthropic_application\
    (Check for cover_letter, essays, job_description files -- use whatever exists)

After reading all files above: report CONTEXT_LOAD=TRUE=1, then proceed to Phase 1.
If any critical file missing (spec.md, DISPATCH_resume_final.md, sage_inputs/01_resume.md): report FALSE=0 + missing path. STOP.

---

## PE_CONTEXT_BUNDLE NOTE (read this before Phase 1)

A complete, gated PE context bundle now exists at:
<staging_path>\wiki\anthropic_application\PE_context_bundle\

This bundle supersedes the overnight resume drafts in cli_overnight_post_run_staging\resume_agent\.
Read ALL 6 files in PE_context_bundle before generating any resume.
RESUME_A_PE_v2.md in that folder is the current best draft (PEL=1, bundle gate passed).

Key corrections from prior drafts:
- GitHub = sagexresearch/0sXai (NOT austinbgreen -- that handle is TAKEN)
- TypeScript: REMOVE from Technical Skills (no evidence)
- Ohr Sameach: DEFAULT OMIT (strict exclusion from session_01_notes) unless Q3 answered
- FATExDAO dates: UNRESOLVED -- use Q1 answer from 04_open_questions.md
- SAGEx Research start: UNRESOLVED -- use Q2 answer from 04_open_questions.md
- Core positioning: behavioral specification throughline / Four Schools (NOT 0sXai architecture)
- Career depth missed in overnight drafts: 40% NYS exam gain, CS4ALL 3 years, #2 Trillium, $250M Interaudi, $50M-$1B Morgan Stanley

---

## PHASE 1 -- RESUME VARIANTS A + B

After CONTEXT_LOAD=TRUE=1, execute:

Task: Generate two clean resume variants for Sage's Anthropic application.

Input: DISPATCH_resume_final.md + sage_inputs/01_resume.md + 04_career_history.md

VARIANT A -- Prompt Engineer (Greenhouse 5159669008):
- Role angle: Prompt Engineering, Claude Code, agentic systems
- ATS-safe, one-page, clean formatting
- Include: Ohr Sameach in Education
- Include: Green Paper author in FATExDAO entry
- FATExDAO dates: Oct 2021 - Mar 2025
- SAGEx Research LLC start: Aug 2023
- Include: BitBuddy, 143_protocol_a, Trinity Dialectic, compounding_learning_OS as project evidence
- GitHub: austinbgreen (not 0SxD, not AgriciDaniel)
- Keep all [CONFIRM: X] slots exactly as-is (do not invent answers)

VARIANT B -- Applied Research / Forward Deployed Engineer (4985877008):
- Role angle: AI architecture, independent research, agent coordination
- Emphasize: independent convergence findings, NeurIPS 2025 parallel, novel ECC work
- Same date/name/education rules as above
- Emphasize: entropy-as-optionality (Trinity Dialectic), ACCE Memory 3-tier, stigmergic coordination

Rules for BOTH:
- No emdashes. Use hyphens, commas, or line breaks instead.
- No legal name (Austin). Public name = Sage.
- No AgriciDaniel. No machine paths. No API keys.
- No 0SxD in portfolio context (0SxD = FATEx only).
- No unverified claims. All dates from sage_inputs or spec.md only.

Output paths (SANDBOX):
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\resume_agent\RESUME_A_draft_v1.md
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\resume_agent\RESUME_B_draft_v1.md

Report: TRUE=1 if both files saved. FALSE=0 + blocker if anything fails.

---

## PHASE 2 -- LINKEDIN DRAFT

Wait for Phase 1 TRUE=1. Then execute:

Task: Write LinkedIn profile draft for Sage.

Input: sage_inputs/02_linkedin.md + RESUME_A_draft_v1.md (from Phase 1 output)

Note: 02_linkedin.md may have blank PASTE fields. If blank = use RESUME_A_draft_v1.md as primary source for Experience and Education. For headline and About = write based on resume content + peer-researcher tone.

Sections to produce:
- Headline (PE/AI architect angle, under 120 chars, no emdashes)
- About / Summary (narrative voice, 3 paragraphs max, independent convergence framing)
- Experience bullets (AI roles only: SAGEx Research, NDA contractor if present, FATExDAO)
- Skills to add: Claude Code, MCP, behavioral evals, agentic systems, RLHF, Python, TypeScript
- Education (include Ohr Sameach)
- Featured: 143_protocol_a, Trinity Dialectic, protocol_mandate.png

Header note at top of file:
"HOW TO UPDATE LINKEDIN -- copy each section below, go to linkedin.com/in/austin-bennett-green, click Edit on each section, paste."

Rules: No emdashes. No legal name. No AgriciDaniel. No machine paths.
Tone: peer-researcher, independent voice. Not corporate. Not buzzword soup.

Output path (SANDBOX):
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\linkedin_agent\LINKEDIN_draft_v1.md

Report: TRUE=1 when saved.

---

## PHASE 3 -- GITHUB PORTFOLIO README

Wait for Phase 2 TRUE=1. Then execute:

Task: Write GitHub portfolio README for sage-prompt-engineering-portfolio.

Input: RESUME_A_draft_v1.md + spec.md (for architecture section) + SKILL_compounding_learning_OS_methodology.md

README structure:
- Name: Sage (public name only)
- One-line tagline
- What this is (prompt engineering portfolio, 0sXai framework work)
- Repos in this portfolio: 143_protocol_a/, trinity_dialectic/, compounding_learning_OS/, sage-prompt-engineering-portfolio/
- Architecture section: Trinity Dialectic + ACCE Memory + 143_protocol_a (brief, no IP dump)
- Independent convergence note (NeurIPS 2025 papers found AFTER Sage built equivalent layers -- state this clearly, no overclaiming)
- Contact: <contact>
- License: MIT

Rules: No emdashes. No legal name. No machine paths. No AgriciDaniel. No 0SxD in portfolio context.

Output path (SANDBOX):
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\github_readme_agent\GITHUB_README_portfolio_v1.md

Report: TRUE=1 when saved.

---

## PHASE 4 -- OPUS REVIEW (switch model to claude-opus-4-6 or run /model opus)

Wait for Phase 3 TRUE=1. Then execute:

Identity shift: You are now OPUS_ADVISOR. Blind review. You have not seen the writing process.
Receive final outputs only.

Task: Review 3 application artifacts and run pre_submit_gate v1.0.

Read:
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\resume_agent\RESUME_A_draft_v1.md
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\resume_agent\RESUME_B_draft_v1.md
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\linkedin_agent\LINKEDIN_draft_v1.md
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\github_readme_agent\GITHUB_README_portfolio_v1.md

Pre-submit gate (run ALL 4 checks):
GATE 1 -- IP SCRUB: any of: Sage / <host> / AgriciDaniel / sk-or / sk-ant / API key pattern? YES = BLOCK (list every hit with line number).
GATE 2 -- DATE CONSISTENCY: all dates traceable to sage_inputs or spec.md? Any unverified date = BLOCK (list conflicts).
GATE 3 -- EMDASH SCAN: any U+2014 or U+2013 character? COUNT and BLOCK if found.
GATE 4 -- OHR SAMEACH: present in Education section of RESUME_A? Missing = FLAG (not block, but must be noted).

Output format (one line per gate):
GATE 1 IP: PASS or BLOCK (list hits + line numbers)
GATE 2 DATES: PASS or BLOCK (list conflicts)
GATE 3 EMDASH: PASS or BLOCK (count + locations)
GATE 4 OHR_SAMEACH: PASS or FLAG

PEL verdict: ALL PASS = PEL=1 (ready for Sage review). ANY BLOCK = PEL=0 (list all repairs needed, ordered by severity).

If PEL=0: write repair instructions. Sonnet re-executes affected phases. Opus re-reviews. Loop until PEL=1.

Save report to (SANDBOX):
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\opus_review\OPUS_REVIEW_v1.md

Final report: TRUE=1 if PEL=1. FALSE=0 if any BLOCK (include PEL=0 verdict + repair list).

---

## PHASE 5 -- HANDOFF (after PEL=1)

Write a brief handoff note to Sage:

Content:
- Which files are ready for review (with full paths in staging)
- Any [CONFIRM: X] slots still unfilled (list them -- Sage fills before submitting)
- Any gates that came back FLAG (not block) -- note for Sage awareness
- Next step for Sage: review OPUS_REVIEW_v1.md, fill CONFIRM slots, then proceed to GitHub handle creation (Phase 1 of BUNDLE_CLI_TONIGHT.md)

Save to (SANDBOX):
<staging_path>\wiki\handoffs\cli_overnight_post_run_staging\HANDOFF_TO_SAGE.md

Report: TRUE=1 when saved. SESSION COMPLETE.

---

## PHASE 6 -- GITLEAKS (deferred -- do NOT run tonight)

This phase runs TOMORROW after Sage reviews and approves Phase 5 output.

Summary so Sage understands what it does:
Gitleaks is a tool that scans your repo for accidentally committed secrets (API keys, tokens, passwords).
Before pushing ANY code or content to GitHub, you must run it to ensure no credentials leaked into files.

Known issue (FLAG-001):
File: <staging_path>\wiki\Symbolic_Symbolic_Arch_Dialectic_Overview_2026_04_15.md
Lines 385, 388, 397 contain a literal API key string.
These 3 lines must be replaced with [REDACTED] before any git push.

Full gitleaks instructions are in BUNDLE_CLI_TONIGHT.md Phase 6.
Do not run tonight. Sage reviews content first. Licensing check runs before push.

---

## RULES (permanent, apply to all phases)

1. No emdashes in any output. Use hyphens, commas, or line breaks.
2. Public name = Sage. Never Austin. Never AgriciDaniel.
3. AgriciDaniel = upstream MIT fork owner of AI Marketing Hub. Not Sage. Never use as Sage's handle.
4. GitHub handle = austinbgreen (new, pending creation). Not 0SxD (FATEx only). Not AgriciDaniel (scrubbed).
5. All outputs go to cli_overnight_post_run_staging ONLY. Never elsewhere.
6. Do not invent data. All dates, titles, and facts from sage_inputs or spec.md.
7. Keep all [CONFIRM: X] slots exactly as-is. Do not fill them. Sage fills before submitting.
8. Report failures accurately. Never claim TRUE=1 on a failed output.
9. OQ6 Path A is locked: no code publishing tonight. Staging only. Licensing check tomorrow.
10. FATExD IP files are excluded from any public content. Do not include xD arbitrage or trading logic.

---

END_CLAUDE.md
