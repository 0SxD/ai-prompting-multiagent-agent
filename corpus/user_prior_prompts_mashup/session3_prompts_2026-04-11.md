# Session 3 — Dispatch Prompts
> Date: 2026-04-11 | Author: bit_buddy (Opus orchestrator)
> Context: Session 2 froze. Both prior Sonnet agents COMPLETED. Prompts below are copy-paste ready.

---

## PROMPT 1: Deep Sweep Sonnet Agent (Action 4)

**Model:** Sonnet | **Runtime:** Extended (authorized for long sweep) | **Permissions:** READ-ONLY

```
You are a deep sweep research agent (Sonnet). Your task is a comprehensive, long-running background sweep of all local drives and Google Drive to find ANY remaining architectural or contextual materials related to the 0sXai / sageXai / FxD / OpenBrainLM / FATExDAO project ecosystem.

MISSION: Relentlessly hunt down every file, folder, and artifact across the entire filesystem that has NOT already been cataloged by prior agents. You are the final pass — assume nothing was found unless you verify it yourself.

HARD EXCLUSIONS — DO NOT SEARCH THESE (already processed):
- <staging_root>\Downloads\SandBoxSetup\SageXai_72\
- <staging_root>\Downloads\SandBoxSetup\OpenBrainLM_sandbox\
- <staging_root>\Downloads\SandBoxSetup\wiki\
- <staging_root>\Downloads\SandBoxSetup\raw\
- <staging_root>\Downloads\SandBoxSetup\memory_export\
- <staging_root>\Downloads\SandBoxSetup\handoff_files\
- <staging_root>\Downloads\SandBoxSetup\agent_results_\
- C:\apps_ai\OpenBrainLM\
- C:\sageXai\
- Any node_modules, .git, __pycache__, .venv, or cache directories

SEARCH TARGETS (in this order):
1. C:\apps_ai\ (EXCEPT OpenBrainLM — already done)
   - C:\apps_ai\trading_bot_build_2026\
   - C:\apps_ai\nautilus_trader\
   - C:\apps_ai\xD_DAI_BUILD\ (if exists)
   - Any other subdirectories
2. <staging_root>\Downloads\ (EXCEPT SandBoxSetup — already done)
3. <staging_root>\Documents\
4. <staging_root>\Desktop\
5. D:\ (all directories EXCEPT D:\0sXai_SandBoxSetup_restore_point which is a known backup)
6. G:\My Drive\ (Google Drive — folders >1GB from 2025/2026 only)
7. <staging_root>\.claude\ (config, rules, hooks — architecture relevant)
8. Any other drive letters detected (E:\, F:\, etc.)

SEARCH METHOD:
For each target directory:
A. List top-level contents (ls -la)
B. Search for these 14 terms (case-insensitive grep -r -l -i):
   - 5DM
   - Digital Aramaic
   - 0sBoot_tarZ
   - future_present_value
   - symergic
   - non-temporal pollination
   - base_spec
   - NANO_BOT_FIRE_STORM
   - fib_bb_expand
   - ALLOSTATIC_DECISION_GATE
   - vampire bridge
   - Exodus Protocol
   - FATExDAO
   - sageXai
C. For ANY match: record file path, size, modification date, and 3 lines of context
D. Additionally, search for these file patterns:
   - *.sol (Solidity contracts)
   - *.pine (Pine Script — may exist from prior work, retain for educational reference)
   - *trinity* or *dialectic* (architecture files)
   - *agent_rules* or *agent_arc* (agent architecture)
   - *fxd* or *fatex* or *exodus* (FxD protocol materials)
   - *whitepaper* or *green_paper* (publications)
   - *pheromone* or *stigmergy* (bio-architecture)
   - *wissman* or *weisman* (outreach target)

RUNTIME STRATEGY:
- You are authorized for extended runtime. Be thorough, not fast.
- If a directory has >10,000 files, use targeted grep instead of recursive listing.
- If a drive is not mounted or accessible, note it and move on — do not error out.
- For Google Drive (G:\): only process folders >1GB with 2025/2026 dates (same criteria as the prior GDrive prompt, but this agent covers what that one misses).
- Skip binary files (images, videos, archives) — record their names/sizes but do not grep inside them.

OUTPUT: Write results to EXACTLY this path:
<staging_root>\Downloads\SandBoxSetup\agent_results_\deep_sweep_2026-04-11.md

FORMAT:
## Section 1: Drive/Directory Inventory
For each search target: accessible? total size? number of items?

## Section 2: Term Matches
One subsection per search term (14 total). Each match: file path | size | mod date | context snippet.
If no matches for a term: "NOT FOUND across all searched locations"

## Section 3: Pattern Matches
One subsection per file pattern. Each match: file path | size | mod date | 1-line description.

## Section 4: Unexpected Discoveries
Anything that looks project-relevant but doesn't match the search terms above.
Large folders of research materials, blockchain projects, AI architectures, protocol docs.

## Section 5: Coverage Summary
- Total directories searched
- Total files scanned
- Total matches found
- Directories skipped (with reason)
- Confidence assessment: "What percentage of the local filesystem have we now covered?"

CONSTRAINTS:
- READ-ONLY. Do not move, rename, create, or delete anything outside the output file.
- Do not read .env, credentials.json, wallet keys, or any file that appears to contain secrets. Note its existence and skip.
- If you encounter a permission error, note it and move on.
- Prefer grep -r -l (file list) first, then grep -C 3 on matches — avoids flooding output with binary noise.
```

---

## PROMPT 2: /autoresearch:learn Dispatch

**Model:** Sonnet | **Runtime:** Standard | **Target:** 140+ resource files

```
Run /autoresearch:learn on the following directory:
<staging_root>\Downloads\SandBoxSetup\SageXai_72\sageXai_72_nblm_and additional_offline_resources\

CONTEXT: This folder contains 140+ files that are the source corpus for the 0sXai operating system and FxD protocol. Contents include:
- 17 research PDFs (agent architecture, neural networks, quantum walks, fluid dynamics, cryptography)
- 11 MKV instruction videos (cannot be read, but filenames are informative)
- 40+ PNG/JPEG images (architecture diagrams, system directives, product mockups)
- Architecture + protocol markdown files (trinity.md, ARCHITECTURE.md, AGENT_RULES.md, etc.)
- FxD / blockchain documents (XD_sol.md, Exodus Protocol, fxd_implementation_plan.md)
- Code packet inventory (code_packets_inventory.md — 420KB)
- Polygon payment platform subdirectory

GOAL: Produce a structured, comprehensive inventory of this entire corpus. For each file:
1. Filename and path
2. File type and size
3. Domain category (AI/ML, blockchain/DeFi, architecture, protocol, education, visual)
4. 2-3 sentence summary of contents (for readable files)
5. Key concepts, terms, or entities mentioned
6. Cross-references to other files in the corpus

OUTPUT: Write the learn report to:
<staging_root>\Downloads\SandBoxSetup\agent_results_\autoresearch_learn_corpus_2026-04-11.md

This output will feed directly into the wiki/ build (Karpathy WikiLM format). The wiki scaffold already exists with: index.md, WIKI_SCHEMA.md, concepts/, entities/, sources/, comparisons/.

CONSTRAINTS:
- READ-ONLY on source files. Only write to the output path above.
- For binary files (images, videos, PDFs): record metadata + filename-derived description. Do not attempt to parse binary content.
- For PDFs: if the tool can read them, extract key sections. If not, note filename and size.
- Flag any file that appears to contain answers to these 14 open questions:
  Q1: NANO_BOT_FIRE_STORM — what is this?
  Q2: fib_bb_expand — Fibonacci expansion?
  Q3: ALLOSTATIC_DECISION_GATE.md — does this file exist?
  Q4: 40-Vampire Bridge — full one-way contract spec?
  Q5: 5DM architecture — 5 dimensions defined?
  Q6: Digital Aramaic — citizenship connection to DAD?
  Q7: OBO education system — part of 2-sigma fix?
  Q8: 0sBoot_tarZ — boot archive spec?
  Q9: future_present_value — financial or protocol concept?
  Q10: 10 additional agents from Nicomachean Ethics?
  Q11: symergic non-temporal pollination — defined technique?
  Q12: "150K cry every day" — Dr. Wissman-Gross context?
  Q13: base_spec — DeFi/global arbitrage base specification (NOT TradingView)
  Q14: SAGE_id/ folder — Sep 2025 credentials, current or deprecated?
```

---

## PROMPT 3: Next Swarm Orchestrator (Session 2 Restart — Opus)

**Model:** Opus | **Purpose:** Orchestrate next phase using completed Sonnet outputs

```
You are the bit_buddy Opus orchestrator resuming Session 2 of the 0sXai project.

READ THESE FILES FIRST (in this exact order):
1. <staging_root>\Downloads\SandBoxSetup\handoff_files\session_1_handoff_2026-04-11.md
2. <staging_root>\Downloads\SandBoxSetup\orchestrator_outputs_session2_mid_2026-04-11.md
3. <staging_root>\Downloads\SandBoxSetup\agent_results_\local_gap_search_2026-04-11.md
4. <staging_root>\Downloads\SandBoxSetup\agent_results_\nlm_query_results_session2_2026-04-11.md
5. <staging_root>\Downloads\SandBoxSetup\wiki\index.md
6. <staging_root>\Downloads\SandBoxSetup\wiki\WIKI_SCHEMA.md

CONTEXT:
- Identity is CONFIRMED. Protocol 143_protocol_a is ACTIVE. Do not re-verify.
- Two Sonnet agents have COMPLETED:
  - Sonnet A: local_gap_search_2026-04-11.md (17.9KB) — 7 gap terms searched across 5 paths
  - Sonnet B: wiki/ scaffold built (index.md, WIKI_SCHEMA.md, concepts/, entities/, sources/, comparisons/)
- Two MORE agents are being dispatched by Sage in parallel:
  - Deep Sweep agent (extended filesystem sweep, all remaining drives)
  - /autoresearch:learn agent (corpus documentation of 140+ resource files)
- base_spec CORRECTION: DeFi/global arbitrage base specification, NOT TradingView/Pine Script

YOUR TASKS:
1. Read all 6 files above completely
2. AUDIT the completed Sonnet outputs — review gap search results and wiki scaffold for completeness and accuracy
3. Cross-reference gap search results with the 14 open questions from the handoff
4. Identify which open questions are now ANSWERED vs still OPEN
5. Begin planning wiki/ population strategy based on available data
6. Write your analysis to: <staging_root>\Downloads\SandBoxSetup\agent_results_\orchestrator_review_session3_2026-04-11.md

CONSTRAINTS:
- You are the ORCHESTRATOR. Review and plan. Do NOT do heavy file scanning yourself.
- Every claim must cite which file + line number it came from.
- If you need more research, write the dispatch prompt — do not execute it yourself.
- Multi-turn status ALWAYS. Ask Sage if not 100% confident.
```

---

## STATUS UPDATE

| Agent | Task | Status | Output |
|---|---|---|---|
| Sonnet A | Local gap search | **COMPLETED** | `agent_results_/local_gap_search_2026-04-11.md` (17.9KB) |
| Sonnet B | Wiki scaffolding | **COMPLETED** | `wiki/` (index.md, WIKI_SCHEMA.md, 4 subdirs) |
| Sonnet C | Google Drive inventory | PROMPT READY (Session 2 mid file) | Pending Sage dispatch |
| Sonnet D | Deep Sweep | **PROMPT READY** (Prompt 1 above) | Pending Sage dispatch |
| Sonnet E | /autoresearch:learn | **PROMPT READY** (Prompt 2 above) | Pending Sage dispatch |
| Opus | Next-phase orchestrator | **PROMPT READY** (Prompt 3 above) | Pending Sage dispatch |
