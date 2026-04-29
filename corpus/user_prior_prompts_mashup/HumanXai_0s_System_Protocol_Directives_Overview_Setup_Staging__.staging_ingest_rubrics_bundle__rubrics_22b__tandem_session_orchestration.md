# tandem_session_orchestration.md | sub-skill | v1.2 clean 2026-04-22
# Multi-chat orchestration to run 2+ parallel chats in this project without file-write conflict.
# Sprint/xlsx references removed.

---

## why this skill exists

User opens parallel chats: 1 orchestrator (instructions / state-changes) + N task chats. All chats share the same project file system. Without isolation, per-turn writes to spec.md / skills.md / Wiki_Log clash.

Solution: per-task spec files isolated by task ID. Shared writes batched at task close.

---

## roles

### orchestrator chat (one per session set)

Owns:
- spec.md (canonical state, per-turn updates)
- project_instructions.md (canon updates only when versioned)
- skills.md (tree only, batched updates from task chats)
- Rubric_Correction_Wiki_Log.md (batched)
- Rubric_Correction_Wiki_Index.md (batched)

Duties:
1. Confirm onboarding canon files present at session open (day + night PDFs).
2. Compare deltas if new canon files added.
3. Validate per-task spec files for cross-task conflict (same task claimed twice).
4. Batch-promote insights from per-task spec_TASK_NNN.md files to canonical spec.md INSIGHTS_LEDGER at task close.
5. Update Wiki_Log per task close.
6. Maintain TASK_QUEUE in canonical spec.md.

### task chat (one per task)

Owns:
- spec_TASK_NNN.md (per-task state)
- outputs://Rubric_Correction_Task_NNN_<slug>_<date>_*.md (analysis, cutpaste, coverage map)

Duties:
1. Bootstrap from project_instructions.md auto-inject (protocol injects automatically via Claude Project settings).
2. project_knowledge_search "spec.md HOT_CACHE" for canon state at chat open.
3. After first user message names task, copy task_spec_template.md to spec_TASK_NNN.md.
4. Per turn: write HOT_CACHE updates only to spec_TASK_NNN.md, NOT spec.md.
5. Per turn: append to spec_TASK_NNN.md INSIGHTS_LOCAL.
6. At task close: output spec_TASK_NNN.md final state. Hand to orchestrator for promotion.

---

## conflict prevention rules

### rule 1: file ownership exclusivity
Each file has exactly one owner per session set. Non-owner chats may READ but NOT write.

Owner table:
- spec.md -> orchestrator
- spec_TASK_NNN.md -> task chat NNN
- skills.md -> orchestrator (task chats SUGGEST updates via spec_TASK_NNN.md TASK_CLOSE_PROMOTION block)
- project_instructions.md -> orchestrator (task chats SUGGEST via spec_TASK_NNN.md INSIGHTS_LOCAL)
- Rubric_Correction_Wiki_Log.md / Rubric_Correction_Wiki_Index.md -> orchestrator (batched at close)

### rule 2: insight promotion at close
Task chat does NOT touch canonical spec.md INSIGHTS_LEDGER per turn. Insights stay in spec_TASK_NNN.md INSIGHTS_LOCAL until task close. Orchestrator promotes in batch.

### rule 3: skill suggestions surface, do not write
If a task chat discovers a new pattern that would warrant a skill .md, draft the pattern in spec_TASK_NNN.md INSIGHTS_LOCAL with promote_to_skill: <slug> tag. Orchestrator creates the skill file.

### rule 4: same-task dual-claim prevention
Before opening spec_TASK_NNN.md, task chat checks if file already exists. If yes with another chat's TASK_META.claimed_at < this chat's open time, this chat YIELDS. Tells user: "Task NNN already claimed by chat at <timestamp>. Pick another task."

---

## per-session bootstrap

### orchestrator bootstrap
1. project_knowledge_search "spec.md HOT_CACHE" -> load canon state.
2. List /mnt/project/spec_TASK_*.md files -> enumerate active task chats.
3. For each spec_TASK_NNN.md, read TASK_META + HOT_CACHE STATUS to know what task chats are doing.
4. Tell user: "Tandem mode active. N task chats detected: <list>. Orchestrator ready."

### task chat bootstrap
1. project_knowledge_search "spec.md HOT_CACHE" -> load canon state.
2. After first user message identifies the task (e.g., "Task 207"), check if spec_TASK_207.md already exists.
3. If yes (and timestamps suggest another chat owns it), STOP, alert user.
4. If no, copy task_spec_template.md to spec_TASK_207.md, fill TASK_META.
5. Proceed with standard intake.

---

## task close handoff

When task chat ships submit (RLS Approved + reviewer-pending):
1. Task chat outputs final spec_TASK_NNN.md to /mnt/user-data/outputs/ for user to drop into project root.
2. Task chat outputs WIKI_LOG_DRAFT block (one line) to be appended.
3. Task chat outputs INSIGHT_PROMOTION block (any insights to lift to canonical).
4. User drops files. Orchestrator chat reads spec_TASK_NNN.md and promotes.

---

## edge cases

### orchestrator chat closes mid-session
New chat started in project becomes orchestrator. Reads spec.md to find tandem mode active. Validates per-task specs unchanged. Resumes orchestrator duties.

### two task chats claim same task
If task chat opens spec_TASK_NNN.md and finds it exists with another chat's TASK_META.claimed_at < this chat's open time, this chat YIELDS.

### task chat needs canonical spec write mid-task
Should not happen. If a true emergency canonical update is needed, task chat surfaces it as OPEN_Q in spec_TASK_NNN.md, alerts user, blocks. Orchestrator handles.

---

## recovery

### lost orchestrator chat
Any new chat reads spec.md TASK_QUEUE and per-task spec files, picks up orchestrator role.

### lost task chat
Task chat's spec_TASK_NNN.md persists. New chat reads it, resumes from HOT_CACHE NEXT_ACTION.

---

END_SUBSKILL
