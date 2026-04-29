# spec.md -- AI Prompting + Multi-Agent Orchestration Agent

---
zero_bloat_protocol: HOT_CACHE overwrite only. 500 word max. Never append.
Insights go to INSIGHTS_LEDGER. Tasks go to TASK_QUEUE. Costs go to metrics_ledger.
---

## HOT_CACHE

```
STATUS: scaffold complete. Corpus intake pass 1 done.

SESSION_TYPE: initial build session.

BOOKS_COPIED_IN: 15 entries across 3 sub-folders.
SUB_FOLDERS_WITH_BOOKS: prompt_engineering (5), multi_agent_systems (5), llm_orchestration (5).

NEXT_INTAKE_STEP: intake pass 2 -- scan software-engineering/architecture-design
and ai-ml/knowledge-graphs for additional orchestration and RAG-adjacent titles.
Flag any additional agentic pipeline books found in ml-general not yet pulled.

ACTIVE_TASK: T01 -- confirm corpus intake complete or queue pass 2.

ACTIVE_VARS:
- corpus_sub_folders: prompt_engineering, multi_agent_systems, llm_orchestration
- intake_pass: 1 of N
- skills_status: all PENDING_DRAFT (6 sub-skills seeded)
- system_directive: written, not yet deployed to live agent
- trinity_thresholds: 15=PROCEED, 10-14=LOOP_BACK, <10=BLOCK

CONFIDENCE: TRUE=1 scaffold + corpus pass 1. FALSE=0 skills content.
```

---

## GRAPH_LINKS

| File | Path | Status |
|------|------|--------|
| bootstrap.md | ./bootstrap.md | LIVE |
| spec.md | ./spec.md | LIVE |
| skills.md | ./skills.md | LIVE |
| system_directive.md | ./system_directive.md | LIVE |
| metrics_ledger.md | ./metrics_ledger.md | LIVE |
| corpus intake log | ./corpus/INTAKE_LOG.md | LIVE |
| prompt_engineering catalog | ./corpus/prompt_engineering/_index.md | LIVE |
| multi_agent_systems catalog | ./corpus/multi_agent_systems/_index.md | LIVE |
| llm_orchestration catalog | ./corpus/llm_orchestration/_index.md | LIVE |
| source: llm-nlp-pt1 | ../../../Corpus_Library_Agentic_Ethos_v1/organized_library_v3/ai-ml/llm-nlp-pt1/_index.md | REFERENCE |
| source: ml-general | ../../../Corpus_Library_Agentic_Ethos_v1/organized_library_v3/ai-ml/ml-general/_index.md | REFERENCE |
| source: knowledge-graphs | ../../../Corpus_Library_Agentic_Ethos_v1/organized_library_v3/ai-ml/knowledge-graphs/_index.md | REFERENCE |
| library audit | ../../../wiki/handoffs/CORPUS_LIBRARY_AUDIT_v1.md | REFERENCE |

---

## COMPACTION_LEDGER

2026-04-24 SCAFFOLD: 5 core files written. Corpus dirs created.
Corpus intake pass 1: 15 book entries pulled from llm-nlp-pt1 and ml-general.
Source: organized_library_v3 (canonical per CORPUS_LIBRARY_AUDIT_v1).
Dark psychology books and personal school docs excluded per audit flags.

---

## TASK_QUEUE

- [ ] T01: Confirm corpus intake pass 1. Queue pass 2 if Sage approves.
- [ ] T02: Write first skill draft -- prompt_pattern_extract (trigger: first real task failure or gate fire)
- [ ] T03: Write first skill draft -- system_directive_write
- [ ] T04: Extract prompt patterns from Raschka S. Build a Large Language Model 2025
- [ ] T05: Extract multi-agent coordination patterns from Campos / Cuevas agent-based models books
- [ ] T06: Write first wiki entry on chain-of-thought prompting
- [ ] T07: Dry-run verification (zero-context Sonnet load test of bootstrap.md)

---

## INSIGHTS_LEDGER

*(empty -- no insights yet. Append here after first real session.)*

---

## OPEN_Q

OQ-01 (OPEN): Should corpus intake pass 2 pull from software-engineering/architecture-design?
Several titles there (SOLID, C4 model, Software Architecture Research Roadmaps) are relevant
to agentic pipeline architecture. Sage to confirm scope.

OQ-02 (OPEN): knowledge-graphs folder has Bratanic T. Essential GraphRAG and Rothman D. RAG-Driven Generative AI.
Both are directly relevant to LLM orchestration (RAG pipelines). Include in pass 2?

OQ-03 (OPEN): llm-nlp-pt1 has ReEvo_LLMs_as_HHs (LLMs as Hyper-Heuristics paper) and
Symbolic-Vector Attention Fusion for Collective Intelligence. These are research papers not books.
Include in corpus as research papers sub-folder? Sage to decide.

---

## RULES

1. HOT_CACHE: overwrite every session. 500 word max. Never append.
2. INSIGHTS_LEDGER: append only. Never delete. Tag with date.
3. COMPACTION_LEDGER: append only. One line per session.
4. TASK_QUEUE: update status inline. Never delete completed tasks, mark [x].
5. OPEN_Q: add new questions as OQ-N. Mark RESOLVED with answer when closed.
6. system_directive_protocol = identity and loop contract in system_directive.md. Not "143_Protocol".
7. All corpus intakes logged in corpus/INTAKE_LOG.md. Append only.
8. Dark psychology books and personal school docs: excluded from this corpus. Flagged in audit.

---

*spec.md v1 | 2026-04-24 | PMAO agent*
