---
title: "CCC takeover: Claude Code CLI assumes full orchestration from Cowork Desktop"
type: handoff
date: 2026-04-17
tags: [handoff, ccc, claude-code-cli, takeover, orchestrator, ss-00, full-project, folder-a, notebooklm-mcp]
status: ready
owner: Sage (Architect)
predecessor: wiki/handoffs/HANDOFF_2026-04-17.md
predecessor_session: Cowork Desktop, save label Planning_2026-04-17_01 (Opus 4.6)
successor_environment: Claude Code CLI (Folder A), Windows 11 native
successor_model_recommended: Opus 4.6 for orchestrator, Sonnet 4.6 or Haiku 4.5 for parallel subagents
---

# CCC takeover: Claude Code CLI assumes full orchestration

## 0a. Turn 5 addendum (2026-04-17, posted by Cowork Desktop orchestrator before transition)

Sage's most recent direction adds three concrete locks on top of what §0 through §13 already say. Treat these as overrides if any conflict appears.

1. **Visuals first.** SS-05 is the single top priority. Start visual iteration before any SS-06, SS-13, or SS-14 production work. Sage quote: "let's do the visuals first."
2. **User-ID change inbound.** Sage confirmed: "i have the user-id and we will create new ones." The current NotebookLM MCP auth on austing143@gmail.com (191 notebooks) stays active until Sage hands you the new account identifiers. Do NOT assume the account migration has happened. Verify with `mcp__notebooklm-mcp__server_info` at start of session. When Sage provides the new user-id, re-run `nlm.EXE` auth and verify notebook list before any publication-scoped query.
3. **First concrete action is the skill wrap.** Sage's turn 5 quote: "we used a working mcp that should have been a saved skill." Produce `SandBoxSetup/.claude/skills/notebooklm-mcp/SKILL.md` via the `skill-creator` skill immediately after topology approval and before any SS-05 artifact work. This closes the gap Sage flagged.
4. **Full component ownership.** Sage quote: "Just hand off and ask it to get setup and take over every component of this project." You inherit every active, paused, and deferred lane (SS-00 through SS-14). The Cowork Desktop orchestrator (save label Planning_2026-04-17_01) stands down after this handoff lands. No parallel Cowork Desktop orchestrator will run.

Five-minute kickoff for the CCC inheritor (supersedes §12 ordering):

a. Echo the canary.
b. Read this §0a first, then STATUS_2026-04-17.md, then §1 through §13 of this file, then SS-05 handoff, then SS-06 handoff.
c. Run `mcp__notebooklm-mcp__server_info` + `mcp__notebooklm-mcp__notebook_list`. Report count to Sage.
d. Invoke the `skill-creator` skill and produce `SandBoxSetup/.claude/skills/notebooklm-mcp/SKILL.md` wrapping the 35 `mcp__notebooklm-mcp__*` tools.
e. Propose topology (single session plus subagents preferred per Sage) and wait for approval.
f. Ask the A-1 through I-4 question set in §3, focused on SS-05 first since that is now the lead lane.

## 0. What you are being asked to do

Sage (Architect, address only as "Sage", never legal name) has decided the entire SandBoxSetup + 0sXai_PLANNING_SANDBOX workstream runs better in Claude Code CLI than in Cowork Desktop. This document hands you every component of the project. Your mandate from Sage, verbatim:

> "Just hand off and ask it to get setup and take over every component of this project. Ideally we would run subagents and do it all in a few at most. Have it determine if it's best to run multiple sessions and/or how to split it up."

You are authorized to:
1. Decide whether to run one CCC session with parallel subagents or split into multiple CCC save-labeled sessions.
2. Recommend the topology to Sage before launching.
3. Get yourself set up (MCP wiring, skill loading, protocol bootstrap) and then take over.

You are NOT authorized to:
1. Execute anything that changes the live vault, filesystem, or a remote repo before clearing the 100 percent Confidence gate with Sage.
2. Publish to GitHub before the identity sanitization gate is cleared.
3. Skip the Trinity Dialectic evaluation on any finalize step.

## 1. Operating contract (inherits from root AGENTS.md)

- Protocol: `143_protocol_a` (Zero Assumption Mandate, 100 percent Confidence Loop, Trinity Dialectic gates).
- Identity protection: address user as Sage only. Grep every written file for `Austin`, `DESKTOP-8AMMKQP`, `austing143`, and scrub to `<ARCHITECT>` / `<SANDBOX_ROOT>` / `<ARCHITECT_EMAIL>` before any public surface.
- Style: no em-dashes. Use hyphens or commas. Short-Form Principle applies (≤200 words per micro-artifact where feasible).
- Mode for the 0sXai_PLANNING_SANDBOX folder: PLAN-ONLY. For the SandBoxSetup folder: INFRA-SETUP-ASSIST.
- Sources: arXiv, ResearchGate, Google, gov, top-tier academic only. Off-shelf open-source repos preferred over custom code. Pirated-piece audited code acceptable per `143_protocol_a` acceptable_output.
- Canary (include at end of every major artifact): `143|PLAN-ONLY|cascade|emergence|Trinity|no-duplication|let-it-emerge|design-101|0sXai|xDx|A2A|FCEE|dormant-main|short-form-pending`

## 2. Current narrowed scope (Sage turn 4, 2026-04-17)

Active lanes in priority order:

1. **SS-05 Visual prompts**. Iterate on `ai_new_algebra_rebuild_diagram.png` and `protocol_mandate.png`, plus the three diagrams Sage uploaded turn 2. Produce prompt-ledger, 3+ variants per canonical diagram, variants-comparison page, promoted winners, placeholder-scrubbed publishable copies.
2. **SS-06 Symbolic Language spec**. Deliver v0.1 grammar, tests, rationale, and a publishable synthesis doc grounded in the FLAG-001 carrier file.
3. **SS-13 Anthropic application prep (NEW)**. Build the Anthropic prompt-engineering application package. Artifact-to-question mapping, application draft, submission checklist, timeline.
4. **SS-14 GitHub artifact publication (NEW)**. Publish 2 to 4 artifacts from SS-05 + SS-06 outputs to a public GitHub repo. Rewrite, synthesize, and finishing-touches per artifact. Deliver README, license, clean commit history.

Paused (not cancelled): SS-11 (context/search), SS-08 (alt tools/error-correcting).

Still deferred (Sage hasn't reopened): SS-03 (NotebookLM workstream separate from the MCP), SS-04 (Wiki/Obsidian wiring), SS-07 (Drive organization), SS-12 (identity sanitization gate), Folder A index update.

Authoritative STATUS file: `SandBoxSetup/wiki/handoffs/STATUS_2026-04-17.md`. Update it every turn where state changes.

## 3. Sage's blocking questions (ask these first, do not execute until answered)

Grouped per 143_protocol_a 100 percent Confidence Loop structure. Sage has already indicated preferences inline for some.

### Architecture and State

- A-1. GitHub target repo. Same `0sXai_FxD Sandbox Build Folder` (exact casing per SS-12 handoff) or a new purpose-built `sage-prompt-engineering-portfolio` style repo for the Anthropic application pack? Public day one or private-then-open?
- A-2. NotebookLM MCP. CONFIRMED LIVE in Folder A at `C:\Users\<ARCHITECT>\.local\bin\notebooklm-mcp.EXE`, version v0.5.24, 191 notebooks visible, account austing143@gmail.com. See §5 below. Sage said turn 5: "i have the user-id and we will create new ones". Confirm which account the CCC session should authenticate against for publication work.
- A-3. Canonical vs candidate diagrams. The three diagrams uploaded by Sage turn 2, plus `ai_new_algebra_rebuild_diagram.png` and `protocol_mandate.png`. Which are canonical source, which are candidates to iterate on, which are being retired?

### Evidence and Sourcing

- E-1. Artifact shortlist. Name the 2 to 4 artifacts to publish. Likely candidates: Hybrid XML-Markdown Symbolic System, Trinity Dialectic Overview, A2A Circuit Breaker pattern, 143_protocol_a prompt architecture. Confirm or replace.
- E-2. Per-artifact scope: rewrite (structural), synthesis (merge), or finishing-touches (polish)? Drives estimate.
- E-3. Citation floor. Which notebooks in NotebookLM seed each artifact? Sage's exact words: "use notebooklm mcp to do that with myself, desktop and specific notebooks i say to reference and how." Get the notebook list and the reference policy from Sage.

### Intent and Constraint

- I-1. Exact Anthropic target. Which role or program? Deadline date? Sage said "ASAP."
- I-2. Public attribution persona. Sage persona only, or real-name credit? GitHub account handle?
- I-3. ASAP budget. Minimum-viable 2 artifacts or polish all 4?
- I-4. Save-label scheme. Sage convention is `Planning_YYYY-MM-DD_SSxx`. Confirm CCC save labels you should spawn.

## 4. Session topology recommendation (for you to validate with Sage)

Sage's preference: "run subagents and do it all in a few at most."

My recommended topology from the Cowork Desktop side:

- **Session 1 (primary orchestrator, this handoff's inheritor)**. Save label `Planning_2026-04-17_CCC01`, model Opus 4.6. Runs in Folder A working directory. Owns STATUS, HANDOFF, Sage dialog, final Trinity gates. Dispatches parallel subagents for research, drafting, and grep.
- **Session 2 (optional, publication pipeline)**. Save label `Planning_2026-04-17_CCC02-publish`, model Sonnet 4.6. Spawns only when SS-05 + SS-06 outputs are ready for SS-14 GitHub publication work. Otherwise unnecessary; the orchestrator handles it via subagents.
- **Subagent pool**. Opus 4.6 for synthesis, Sonnet 4.6 for code/gitleaks/scrub passes, Haiku 4.5 for bulk grep or image-metadata reads.

Evaluate this against your own capacity. If Sage wants single-session with subagents and it fits, that is the cheapest path. Propose your final topology to Sage before launching.

## 5. MCP and tool state on Folder A (what you should have access to)

Verified via subagent sweep 2026-04-17:

### Confirmed live MCP: notebooklm-mcp v0.5.24

- Package: `notebooklm-mcp-cli` from upstream `github.com/jacob-bd/notebooklm-mcp-cli`
- Install command used: `uv tool install notebooklm-mcp-cli`
- Binary path: `C:\Users\<ARCHITECT>\.local\bin\notebooklm-mcp.EXE`
- Auth CLI: `nlm.EXE` (Google OAuth against austing143@gmail.com, 188 owned + 3 shared = 191 notebooks)
- MCP registration: `C:\Users\<ARCHITECT>\.claude.json` (global), transport stdio
- Tool prefix: `mcp__notebooklm-mcp__*` (35 tools total). Permissions already granted in `.claude/settings.local.json` for at least `server_info` and `notebook_list`.
- First-live date: 2026-04-15 12:09 UTC per wiring-fix report.
- **Gap Sage flagged**: this should be a saved skill but no skill wrapper exists. Only `SandBoxSetup/.claude/skills/notebooklm-book-organizer/SKILL.md` (a sibling workflow) and `/sessions/.../mnt/.claude/skills/mcp-builder/SKILL.md` (a guide for building MCPs) exist. **Your first action after taking over**: use the `skill-creator` skill to generate `SandBoxSetup/.claude/skills/notebooklm-mcp/SKILL.md` wrapping the 35 mcp__notebooklm-mcp__* tools with trigger phrases like "query notebook", "ask notebooklm", "search notebooks", etc. This closes the gap that cost Sage time.

### Pending MCP: obsidian-claude-code-mcp

- Plugin: `iansinnott/obsidian-claude-code-mcp` v1.1.8
- Status: architect UI action pending (install via Obsidian Community Plugins)
- Port: 22360, transport WebSocket auto-discovery + SSE manual
- Blocks: SS-04 (wiki wiring)
- Verify current install state when you take over; do not assume.

### Other tools Sage has mentioned as "confirmed" in 0sXai_PLANNING_SANDBOX/AGENTS.md

- Obsidian Local REST API v3.6.1
- Obsidian Git
- Relay / LiveSync
- OpenRouter (routing layer, not an MCP)
- Hermes (setup docs at `SandBoxSetup/wiki/hermes-setup.md`)
- oh-my-codex / OMX v2 (parked, WSL2 retired 2026-04-15)
- Zep / Graphiti (mentioned, no install evidence found in sweep)

## 6. FLAG-001 status (critical security state)

Key **ROTATED** at OpenRouter on 2026-04-17 per Sage (turn 3). Old literal at `SandBoxSetup/Symbolic_Symbolic_Arch_Dialectic_Overview_2026_04_15.md` lines 388 and 397 is now dead.

Residual rules before any public push or Anthropic application upload:
- Scrub both dead-key lines to `${ANTHROPIC_AUTH_TOKEN}` placeholder.
- Scrub the personal-path line at file line 385 to `<SANDBOX_ROOT>`.
- Scrub email literal to `<ARCHITECT_EMAIL>`.
- The new OpenRouter key must never appear in any doc body. Keep it in `.env` with `.gitignore` coverage.

Reference: `SandBoxSetup/wiki/SECURITY.md` (turn-4 updated).

## 7. Entry state you inherit

### Key files (verified existing as of 2026-04-17)

```
SandBoxSetup/CLAUDE.md
SandBoxSetup/AGENTS.md
SandBoxSetup/.claude/rules/01_project_scope.md
SandBoxSetup/wiki/SECURITY.md
SandBoxSetup/wiki/handoffs/STATUS_2026-04-17.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17.md
SandBoxSetup/wiki/handoffs/LAUNCH_PLAN_2026-04-17.md
SandBoxSetup/wiki/handoffs/SESSION_OPENERS_2026-04-17.md
SandBoxSetup/wiki/handoffs/_HANDOFF_TEMPLATE.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss00-orchestrator.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss03-notebooklm.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss04-wiki-obsidian.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss05-visual-prompts.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss06-symbolic-language-spec.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss07-drive-organization.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss08-alt-tools-error-correcting.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss11-context-searching.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss12-identity-sanitization.md
SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ccc-takeover.md  ← you are reading this
0sXai_PLANNING_SANDBOX/.claude/CLAUDE.md
0sXai_PLANNING_SANDBOX/AGENTS.md
```

Read STATUS, then this handoff, then the master HANDOFF_2026-04-17, then SS-05 and SS-06 handoffs first. The rest can be read lazily as needed.

### Auto-memory pointers (global)

`/sessions/lucid-focused-brahmagupta/mnt/.auto-memory/MEMORY.md` indexes:
- `user_sage_architect.md`
- `feedback_no_emdash_and_protocol.md`
- `project_0sxai_sandbox_structure.md`
- `reference_subagent_reports.md`
- `reference_tier1_handoffs_2026-04-17.md`

Add a new reference memory `reference_notebooklm_mcp_live.md` pointing at the Folder A install path and the skill you create in §5 gap-close.

### Uploads

FLAG-001 carrier file was uploaded to the Cowork Desktop session's local area at `/sessions/.../mnt/uploads/Symbolic_Symbolic_Arch_Dialectic_Overview_2026_04_15.md`. In CCC, the canonical copy lives at `SandBoxSetup/Symbolic_Symbolic_Arch_Dialectic_Overview_2026_04_15.md` (verified exists). Use the live-tree copy; treat line 385 and lines 388/397 as scrub targets.

## 8. Success criteria for the takeover

1. You greet Sage with a topology proposal (single session with subagents, or multi-session split) and wait for approval.
2. You produce a saved skill for notebooklm-mcp at `SandBoxSetup/.claude/skills/notebooklm-mcp/SKILL.md` using the `skill-creator` skill.
3. You obtain Sage's answers to A-1 through I-4 in §3 before writing any artifact output.
4. You deliver SS-05 and SS-06 outputs placeholder-scrubbed.
5. You deliver SS-14 publication to the confirmed GitHub repo.
6. You deliver SS-13 Anthropic application package ready for submission.
7. You update STATUS_2026-04-17.md every turn state changes. You write a fresh HANDOFF if your own context approaches red on the context-monitor skill (8+ signals).
8. Every finalize step clears Trinity Dialectic ≥ 15/15. Below 15, loop back.
9. No identity leak makes it into any published artifact. Grep every file for `Austin`, `DESKTOP-8AMMKQP`, `austing143` before marking a deliverable done.

## 9. Trinity Dialectic gates (apply before finalize)

- **[Λ Logos]** Logically and factually sound based on sources. 100 percent confidence = sources cited supporting main idea. 5 tokens.
- **[Π Pathos]** Aligns with Sage's prompt and addresses the entire request with 100 percent of success. 5 tokens.
- **[Θ Ethos]** All constraints met and rules followed, including identity protection, no-em-dash, FLAG-001 scrub, GitHub gate. 5 tokens.

Global score 15 → PROCEED. Below 15 → LOOP_BACK_REVIEW_REPLAN_RETURN.

## 10. Known gotchas

- Windows path case is insensitive but Git on Linux is sensitive. Normalize paths at export.
- WSL2 retired 2026-04-15. Sanitization scripts must run native Windows (PowerShell or Python via `uv run`).
- `.raw/` is immutable per Karpathy LLM Wiki pattern. Never write into `.raw/`. Scrub FROM `.raw/` INTO `_github_export_staging/` only.
- Obsidian wikilink embeds `![[file.png]]` render in Obsidian only. Rewrite to `![](./path)` during GitHub export. Do not touch the live vault copy.
- Filenames themselves may carry identity markers. Scan filenames, not only contents.
- NotebookLM MCP works on austing143@gmail.com right now. If Sage authenticates a new account (per turn 5 hint), re-run `nlm.EXE` auth and verify notebook list before any publication-scoped query.
- The diagrams uploaded turn 2 and the canonical PNGs may have EXIF metadata with user names, machine serials, or GPS. Strip EXIF before publication. Use `exiftool` or the Pillow `Image.save(..., exif=b'')` pattern.
- Context-monitor skill at `/sessions/lucid-focused-brahmagupta/mnt/.claude/skills/context-monitor/SKILL.md`. Run it at turn 10, 20, 30 in your CCC session. Green 0-5, yellow 6-7 slow down, orange 8-9 stop new writes, red 10 produce successor handoff.

## 11. References

- Root AGENTS.md: `0sXai_PLANNING_SANDBOX/AGENTS.md` (cascades, Trinity, PLAN-ONLY)
- Project scope rules: `SandBoxSetup/.claude/rules/01_project_scope.md`
- Master handoff: `SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17.md`
- SS-05 handoff: `SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss05-visual-prompts.md`
- SS-06 handoff: `SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss06-symbolic-language-spec.md`
- SS-12 handoff (sanitization gate): `SandBoxSetup/wiki/handoffs/HANDOFF_2026-04-17_ss12-identity-sanitization.md`
- Security register: `SandBoxSetup/wiki/SECURITY.md`
- Status tracker: `SandBoxSetup/wiki/handoffs/STATUS_2026-04-17.md`
- Skill creator: `/sessions/lucid-focused-brahmagupta/mnt/.claude/skills/skill-creator/SKILL.md`
- MCP builder: `/sessions/lucid-focused-brahmagupta/mnt/.claude/skills/mcp-builder/SKILL.md`
- NotebookLM upstream: `github.com/jacob-bd/notebooklm-mcp-cli`
- Obsidian plugin pending: `github.com/iansinnott/obsidian-claude-code-mcp`
- gitleaks (for SS-12 when it reactivates): `github.com/gitleaks/gitleaks`
- detect-secrets: `github.com/Yelp/detect-secrets`

## 12. First-five-turns script for the CCC inheritor

1. Echo the canary.
2. Read STATUS_2026-04-17.md, this handoff, HANDOFF_2026-04-17.md (master), SS-05, SS-06 in that order.
3. Verify notebooklm-mcp is live: `mcp__notebooklm-mcp__server_info` and `mcp__notebooklm-mcp__notebook_list`. If it returns 191+ notebooks against Sage's current account, good. If not, pause and ask Sage to reauth.
4. Propose topology (single session with subagents, or multi-session) and wait for approval.
5. Ask Sage the A-1 through I-4 question set in §3. Do not start artifact production until you have answers.

## 13. Canary

`143|PLAN-ONLY|cascade|emergence|Trinity|no-duplication|let-it-emerge|design-101|0sXai|xDx|A2A|FCEE|dormant-main|short-form-pending`
