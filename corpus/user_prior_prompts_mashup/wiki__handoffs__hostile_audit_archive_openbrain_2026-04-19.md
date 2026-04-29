---
title: Hostile Audit Handoff -- archive-openbrain Publication Review
type: hostile_audit_handoff
date: 2026-04-19
from: ccc08_archive_staging
to: zero_context_auditor
status: ready_for_audit
canary: 143|PLAN-ONLY|cascade|emergence|Trinity|no-duplication|let-it-emerge|design-101|0sXai|xDx|A2A|FCEE|dormant-main|short-form-pending
---

# Hostile Audit Handoff -- archive-openbrain

You are a zero-context auditor. You have never seen this work. Your job is to assume something
went wrong and find it. Do not give the benefit of the doubt. Verify every claim independently.

---

## What You Are Auditing

A Claude Code session (CCC08_archive_staging) claims to have:

1. Copied `OpenBrainLM_sandbox/` from a local Windows machine into a GitHub private repo
   `0SxD/archive-openbrain` after sanitizing all PII and internal identifiers.
2. Published as a clean, single-commit archive of a brain harness AI project (MIT licensed).
3. Excluded all personal ops files, virtual environments, and session artifacts.
4. Passed a scrub verification showing zero hits on 6 PII categories.

Your job: **prove those claims wrong, or confirm they hold**.

---

## Access

**Repo:** `https://github.com/0SxD/archive-openbrain` (PRIVATE)
**Access method:** `gh` CLI authenticated to 0SxD org, or clone via:
```bash
gh repo clone 0SxD/archive-openbrain /tmp/audit-archive-openbrain
cd /tmp/audit-archive-openbrain
```

**Claimed commit:** `934bfb3a5b62d14c43c8b8cf44941b0c4fc57c56`
**Claimed author:** `Architect <maintainer@example.com>`
**Claimed file count:** 1641 files, 443 dirs

---

## Audit Checklist -- Run Every Check, Report Pass/Fail

### Block A: Git Identity

```bash
git log --format="%H %ae %an %s"
```
PASS: single commit, author = `Architect`, email = `maintainer@example.com`
FAIL: multiple commits, OR any real name/email (Austin, 0SxD, sagexresearch@gmail.com, austing143)

```bash
git log --all --format="%H %ae %an %s" | wc -l
```
PASS: exactly 1 line
FAIL: more than 1 -- history was not cleanly reset

### Block B: PII Sweep (the core claim)

Run all six. Every category must return zero file matches.

```bash
# 1. Personal name
grep -r --include="*.md" --include="*.py" --include="*.sh" --include="*.toml" --include="*.txt" --include="*.json" --include="*.yaml" --include="*.cfg" -rl "\bAustin\b" . 2>/dev/null | grep -v ".git"
```
PASS: no output
FAIL: any file listed -- report the file and line (grep -n)

```bash
# 2. Machine hostname
grep -r -rl "DESKTOP-8AMMKQP" . 2>/dev/null | grep -v ".git"
```
PASS: no output

```bash
# 3. Username variants
grep -r -rl "austing143\|austing@" . 2>/dev/null | grep -v ".git"
```
PASS: no output

```bash
# 4. Internal workspace path
grep -r --include="*.md" --include="*.py" --include="*.sh" --include="*.toml" -rl "apps_ai" . 2>/dev/null | grep -v ".git"
```
PASS: no output

```bash
# 5. Author identity
grep -r -rl "sagexresearch" . 2>/dev/null | grep -v ".git"
```
PASS: no output

```bash
# 6. Windows absolute paths
grep -r -rl "C:\\\\Users\\\\Austin\|C:\\\\apps_ai\|C:/Users/Austin" . 2>/dev/null | grep -v ".git"
```
PASS: no output

```bash
# 7. API key patterns (actual sk- strings, not just pattern references)
grep -r --include="*.py" --include="*.sh" --include="*.env" -rn "sk-or-v1-[a-zA-Z0-9]\|sk-ant-[a-zA-Z0-9]" . 2>/dev/null | grep -v ".git"
```
PASS: no output
FAIL: any actual key string (not the word "sk-or-v1" alone, but followed by real chars)

### Block C: Excluded Directories (must be absent)

```bash
ls -la .venv/ 2>/dev/null && echo "FAIL: .venv present" || echo "PASS: .venv absent"
ls -la memory/ 2>/dev/null && echo "FAIL: memory/ present" || echo "PASS: memory/ absent"
ls -la agent_sync/ 2>/dev/null && echo "FAIL: agent_sync/ present" || echo "PASS: agent_sync/ absent"
ls -la handoffs/ 2>/dev/null && echo "FAIL: handoffs/ present" || echo "PASS: handoffs/ absent"
ls -la .claude/settings.local.json 2>/dev/null && echo "FAIL: settings.local.json present" || echo "PASS: settings.local.json absent"
```

### Block D: Suspicious Files (auditor should manually inspect)

These were NOT in the original exclusion list but may contain PII or internal data.
Inspect each and report contents.

```bash
# 1. Egg-info build artifact -- may embed author or local paths
cat openbrainlm.egg-info/PKG-INFO 2>/dev/null | grep -i "author\|home-page\|maintainer\|url\|email" | head -10
cat openbrainlm.egg-info/SOURCES.txt 2>/dev/null | head -20
```
CHECK: does PKG-INFO contain real author name, real email, or local paths?

```bash
# 2. BIRTHDAY.md -- unknown content
cat BIRTHDAY.md
```
CHECK: does this contain personal info, dates linked to real identity, or internal ops context?

```bash
# 3. progress.txt -- session tracker with 43 internal entries
head -30 progress.txt
grep -c "Austin\|DESKTOP\|austing\|apps_ai" progress.txt
```
CHECK: PII in session entries after scrub

```bash
# 4. pyproject.toml -- author field
cat pyproject.toml | grep -A3 "\[project\]" | head -10
```
CHECK: author name, email, URLs

```bash
# 5. research.md -- may contain internal path refs or session ops
head -40 research.md
grep -c "Austin\|DESKTOP\|apps_ai" research.md
```

```bash
# 6. sagex/ directory -- hooks and skills
ls sagex/
cat sagex/README.md 2>/dev/null | head -20
grep -r "Austin\|apps_ai\|DESKTOP" sagex/ 2>/dev/null
```

```bash
# 7. .claude/rules/ -- may have local path rules
ls .claude/rules/
cat .claude/rules/00_session_context.md 2>/dev/null | head -20
```

### Block E: License Integrity

```bash
head -3 LICENSE
```
PASS: "MIT License" on line 1
FAIL: license altered, removed, or wrong type

```bash
# Check Python source files preserve MIT header where applicable
grep -r "MIT\|License\|Copyright" openbrainlm/ --include="*.py" | head -5
```

### Block F: Structural Integrity

```bash
# Core package must be present
ls openbrainlm/*.py 2>/dev/null | wc -l
```
PASS: >= 3 Python files (cli.py, bridge.py, __init__.py minimum)
FAIL: 0 -- package was stripped

```bash
# README must be substantive (not just a stub)
wc -l README.md
```
PASS: >= 20 lines

```bash
# Tests must be present
ls tests/*.py 2>/dev/null | wc -l
```
PASS: >= 2 test files

### Block G: CCC/SS Internal Lane Codes (spot check)

```bash
grep -r --include="*.md" -rn "CCC0[0-9]\|SS-[0-9][0-9]" . 2>/dev/null | grep -v ".git" | head -10
```
PASS: no output (lane codes scrubbed)
FAIL: any hits -- internal session ops leaked

---

## Known Risks to Investigate

These are failure modes CCC08 session may have missed. Check each:

1. **openbrainlm.egg-info/** -- build artifact, not in original exclusion list. May contain
   author name, email, or `home_dir` references from `pip install -e .`. HIGH RISK.

2. **BIRTHDAY.md** -- unusual file name. Not inspected by CCC08. Unknown content. CHECK IT.

3. **progress.txt** -- 43 session entries scrubbed by regex but session context may remain.
   Regex `\bAustin\b` would catch "Austin" but not "the user" or indirect references.

4. **pyproject.toml** -- `[project.authors]` field may contain real name after scrub
   replaced "Austin" with "Creator" -- is "Creator" actually in the authors field now,
   or did the pattern match fail on TOML structure?

5. **research/** directory -- 20+ markdown files scrubbed. Spot-check 3 random files
   for path leakage or personal context beyond what regex caught.

6. **sagex/hooks/*.sh** -- bash scripts. Scrub covered .sh files, but shell variables
   with names like `$AUSTIN_HOME` or `$USER` might expand at runtime. Check for
   hardcoded user references.

7. **.claude/ directory included** -- CLAUDE.md and rules were scrubbed but the
   .claude/ directory being present at all in a public archive is unusual. It contains
   harness configuration. Assess whether it should be included or excluded entirely
   for a public-facing archive.

8. **notebooks/ directory** -- present in top-level. CCC08 did not specifically audit this.
   May contain Jupyter notebooks with embedded cell outputs that include local paths.

---

## What to Report

For each Block (A through G) and each Known Risk: PASS, FAIL, or FLAG (inconclusive, needs Sage review).

Format your report as:

```
## Audit Report -- archive-openbrain 2026-04-19

### Block A: Git Identity -- [PASS/FAIL]
[finding]

### Block B: PII Sweep -- [PASS/FAIL]
[category-by-category result]

### Block C: Excluded Dirs -- [PASS/FAIL]
[finding]

### Block D: Suspicious Files
- openbrainlm.egg-info: [PASS/FAIL/FLAG] [finding]
- BIRTHDAY.md: [PASS/FAIL/FLAG] [finding]
- progress.txt: [PASS/FAIL/FLAG] [finding]
- pyproject.toml: [PASS/FAIL/FLAG] [finding]
- research.md: [PASS/FAIL/FLAG] [finding]
- sagex/: [PASS/FAIL/FLAG] [finding]
- .claude/rules/: [PASS/FAIL/FLAG] [finding]

### Block E: License -- [PASS/FAIL]
### Block F: Structure -- [PASS/FAIL]
### Block G: Lane Codes -- [PASS/FAIL]

### Known Risks
[risk name]: [PASS/FAIL/FLAG] [evidence]

### Verdict
CLEAR TO MAKE PUBLIC / NEEDS REMEDIATION (list items)
```

Drop report to: `wiki/shared/audit_report_archive_openbrain_2026-04-19.md`

---

## Context You Should NOT Need (but available if blocked)

- Full plan: `C:\Users\Austin.DESKTOP-8AMMKQP\.claude\plans\memoized-popping-newt.md`
- Coordinator report: `wiki/shared/ccc08_to_orchestrator_archive_plan_ready_2026-04-19.md`
- Scrub audit pre-scan: 245 Austin hits, 645 apps_ai hits pre-scrub. Post-scrub claimed 0.

Do not trust these. Verify independently.

---

## Pre-Audit Self-Corrections (CCC08 caught these before handoff)

The following issues were found and fixed AFTER the initial commit. The auditor should verify
these are actually resolved -- do not take the session's word for it.

| Issue | Found | Fix Applied | Verify Command |
|-------|-------|-------------|----------------|
| `openbrainlm.egg-info/PKG-INFO`: `Author: 0SxD` | egg-info not in original scrub scope | Replaced with `Author: Architect` | `grep "^Author:" openbrainlm.egg-info/PKG-INFO` |
| `.claude/write_permit.json`: internal ops artifact | Not in exclusion list | Deleted | `ls .claude/write_permit.json` should 404 |
| `.claude/active_audit_state.md`: internal ops state | Not in exclusion list | Deleted | `ls .claude/active_audit_state.md` should 404 |
| `.claude/hookify.*.local.md` (3 files): internal hookify state | Not in exclusion list | Deleted | `ls .claude/hookify.*.local.md` should 404 |
| `.claude/hooks/jq.exe`: Windows binary | Not in exclusion list | Deleted | `ls .claude/hooks/jq.exe` should 404 |
| `.claude/rules/01_trading_rules.md`: reveals internal project paths | Not in exclusion list | Deleted entirely | `ls .claude/rules/01_trading_rules.md` should 404 |
| `brain-harness.md` + `00_session_context.md`: `trading_bot_build_2026`, `nautilus_trader` | Scrub missed .claude/ subdirs in first pass; second pass missed these terms | Replaced with `<CONNECTED_PROJECT>` and `<TRADING_PROJECT>` | `grep -r "trading_bot_build\|nautilus_trader" .claude/` |

**Current commit after remediation:** `9245514`
**Repo:** `https://github.com/0SxD/archive-openbrain` (PRIVATE)

The auditor should clone from the REMOTE (not local staging), to catch any divergence
between local state and what was actually pushed.

```bash
gh repo clone 0SxD/archive-openbrain /tmp/audit-archive-openbrain
cd /tmp/audit-archive-openbrain
git log --oneline   # must show: 9245514 single commit
```
