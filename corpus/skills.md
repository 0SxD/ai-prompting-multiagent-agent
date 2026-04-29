# skills.md -- AI Prompting + Multi-Agent Orchestration Agent

Tree index only. No skill content here. Pointers to sub-skill files only.
Load this file when a skill is needed. Do not load at startup.

---

## Read Protocol

Before executing any task involving a skill:
1. Load this file.
2. Find the skill ID and path.
3. Load the sub-skill .md file at that path.
4. Follow the sub-skill instructions.
If the sub-skill file does not exist yet (status PENDING_DRAFT): flag it, do not fabricate a process.

---

## Status Legend

| Status | Meaning |
|--------|---------|
| PENDING_DRAFT | Skill seeded but not yet written. Do not execute. Flag and queue. |
| DRAFT | Skill written but not yet validated in a live session. |
| VALIDATED | Skill tested in at least one real session. Reliable. |
| DEPRECATED | Skill replaced or obsolete. Do not use. |

---

## PMAO Skills

| ID | Skill | Location | Status |
|----|-------|----------|--------|
| PMAO-01 | prompt_pattern_extract | skills/prompt_pattern_extract.md | PENDING_DRAFT |
| PMAO-02 | system_directive_write | skills/system_directive_write.md | PENDING_DRAFT |
| PMAO-03 | multi_agent_coordination_pattern | skills/multi_agent_coordination_pattern.md | PENDING_DRAFT |
| PMAO-04 | chain_of_thought_analysis | skills/chain_of_thought_analysis.md | PENDING_DRAFT |
| PMAO-05 | rubric_evaluation | skills/rubric_evaluation.md | PENDING_DRAFT |
| PMAO-06 | wiki_entry_write | skills/wiki_entry_write.md | PENDING_DRAFT |

---

## Skill Population Rule

Skills are written ONLY after a task has failed at least once OR after a Trinity gate has fired.
Do not pre-populate skills speculatively.
Write from real failures and real gate events.
Log each skill creation in spec.md COMPACTION_LEDGER.

---

*skills.md v1 | 2026-04-24 | 6 sub-skills seeded, all PENDING_DRAFT*
