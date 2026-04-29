# ROLE SELECTION BRIEF

**Purpose:** Decide which Anthropic job posting(s) Austin should target.
**Requestor:** Austin Bennett Green
**Issued by:** Session 2, 2026-04-20
**Blocker status:** BLOCKS Write phase. Must resolve before resume is finalized.

This brief is designed to be handed to a PARALLEL agent (new context window, fresh session) or run by Session 3 as its first task. It is standalone, no prior context required beyond the AUSTIN_PROFILE_GROUND_TRUTH.md companion file.

---

## 1. The Task

Austin surfaced 4 additional Anthropic postings beyond the Session 1 baseline (Prompt Engineer, Claude Code, Greenhouse 5159669008). He asked: which is the best fit? Can I apply to more than one?

Produce a fit-matrix analysis of 5 roles, make a recommendation, and justify it.

---

## 2. URLs to fetch

| # | URL | Known role |
|---|-----|-----------|
| 0 | https://job-boards.greenhouse.io/anthropic/jobs/5159669008 | BASELINE: Prompt Engineer, Claude Code ($300K-$405K, SF/NYC/Seattle, 25% in-office) |
| 1 | https://job-boards.greenhouse.io/anthropic/jobs/4017544008?gh_src=LinkedIn | Unread |
| 2 | https://job-boards.greenhouse.io/anthropic/jobs/5061517008?gh_src=LinkedIn | Unread |
| 3 | https://job-boards.greenhouse.io/anthropic/jobs/4613568008?gh_src=LinkedIn | Unread |
| 4 | https://job-boards.greenhouse.io/anthropic/jobs/5097186008?gh_src=LinkedIn | Unread |

Board URL: https://job-boards.greenhouse.io/anthropic?gh_src=LinkedIn

---

## 3. Methodology (run in this order)

### Step 1: Fetch

Use `web_fetch` on each of the 5 URLs. Extract the following for each:

- Role title
- Team
- Location(s)
- Seniority level (L4, L5, L6, Staff, IC, manager)
- Compensation band
- Tier 1 must-haves (list as bullets)
- Tier 2 differentiators (list as bullets)
- Application form fields (especially whether "Why Anthropic" essay is present and length)
- Any explicit requirement incompatible with Austin's profile (e.g., "PhD in ML required", "10 years production systems engineering", "current TS clearance")

### Step 2: Score fit against Austin's Core Thesis

For each role, score on a 5-point scale across six axes:

1. **Technical fit (Tier 1 requirements)**: 0 = Austin lacks 3+ requirements; 5 = Austin clears all Tier 1
2. **Differentiator fit (Tier 2)**: 0 = Austin has 0 differentiators; 5 = Austin has 3+ Tier 2 differentiators
3. **Mission alignment**: 0 = neutral or corporate; 5 = directly aligns with Austin's safety and beneficial-deployment framing
4. **Narrative coherence**: 0 = Austin's story looks scattered for this role; 5 = role is the natural landing for his 5-domain thesis
5. **Recruiter friction**: 0 = recruiter likely confused by non-traditional path; 5 = recruiter immediately sees the fit
6. **OpenBrainLM relevance**: 0 = OpenBrainLM has nothing to offer this role; 5 = OpenBrainLM IS the portfolio evidence this role wants

Produce a 5x6 matrix. Column 7 = total (max 30).

### Step 3: Classify each role

Based on the scoring, assign each role to a bucket:

- **PRIMARY:** Total ≥ 22, strong technical fit, narrative coherent, OpenBrainLM directly relevant
- **STRONG SECONDARY:** Total 18 to 21, clear path to fit with right resume framing
- **VIABLE:** Total 14 to 17, possible but requires more stretch; only target if primary and secondary are unavailable
- **NOT RECOMMENDED:** Total < 14, would require misrepresenting Austin's profile or competing on dimensions he lacks

### Step 4: Make a recommendation

Default recommendation framework:

**Option A, single best fit:** Apply to PRIMARY role only. Put full resume and cover letter effort into one application. Lowest coordination risk.

**Option B, sequential two:** Apply to PRIMARY first. If no response in 7-10 business days, apply to STRONG SECONDARY. Spacing avoids recruiter cross-referencing concerns. Same resume base, re-tailored cover letter.

**Option C, parallel two:** Apply to PRIMARY and STRONG SECONDARY on the same day, 2-to-4 hours apart. Only advisable if the two roles are in genuinely different teams with non-overlapping recruiters. Check Greenhouse for recruiter identity disclosure; if same recruiter on both, do NOT do this.

**Option D, multi-apply (3+):** Generally NOT RECOMMENDED for one candidate on a single company's Greenhouse. Reads as scattershot. Use only if Austin explicitly insists.

### Step 5: Flag known risks

Call out:
- Any role that requires in-office 100% (Austin prefers remote-strong with 25% in-office; Prompt Engineer Claude Code already confirmed 25%)
- Any role requiring specific credentials Austin does not have (active ML publications, specific PhD, specific framework expertise like PyTorch production engineering)
- Any role where the NDA-restricted Mercor phrasing hurts (roles requiring public-evidence of RL training work beyond what generalized phrasing can carry)
- Any role where the FATExDAO era is a liability (e.g., specific trust-and-safety roles where crypto history could raise questions)

---

## 4. Austin's strengths to map against (canonical list for scoring)

### AI / Systems / Prompt Engineering
- OpenBrainLM: MIT-licensed, 8-layer biomimetic architecture, Trinity Dialectic, running code, 42-plus session log, 20 peer-reviewed citations, 86-repo open-source component integration plan
- 0sXai-SL v0.2: grounded symbolic language spec with 11 external citations including ISO/IEC EBNF, Ford 2004 PEG, Peirce, HippoRAG, Neuro-Symbolic Explainability
- Trinity Dialectic evaluation engine (Lambda/Pi/Theta, 9 sub-evaluators)
- A2A circuit breaker (agent-to-agent protocol)
- 143_Protocol_a Blueprint (operational governance)
- Zero-context reviewer pattern (hostile self-audit agents)
- Research gate and destructive-command guards (PreToolUse hooks, tested)
- Adversarial self-audit discipline (10 to 8 layer correction based on audit)
- Mercor AI training team lead and reviewer, 200+ contracted hours, education-domain world-building

### Education
- NYS Professional Teaching Certificate (active through 2031)
- Relay M.Ed. Middle Mathematics Education, 3.6 GPA, Honors
- 7 years 6th and 7th grade math plus CS in high-needs South Bronx (NYC DOE, Bronx Academy of the Arts, MS328)
- CS4ALL Teacher Team Leader, launched school's CS program for 3 years
- NYC Teaching Fellows 2017 Cohort
- Trauma-informed pedagogy for IEP and ELL populations
- First-year: students 40% better on NYS exam, school removed from Renewal status
- Neurodivergent (autistic) student curriculum design, 2023-2024
- edTPA certified
- Private tutoring and test prep across K-12 for 20+ years

### Finance / Policy / Regulated
- Morgan Stanley VP Tailored Lending, $50M-$1B UHNW facilities
- RBS Citizens VP Credit Portfolio Manager, WROTE commercial card credit policy, Basel and Dodd-Frank
- Interaudi Bank Credit Portfolio Officer, $250M-$350M book
- FINRA Series 7 and 55 (historical)
- Trillium Trading proprietary equity trader (2006-2007)
- 8 years regulated-industry audit and examiner readiness

### Founder / Leadership
- FATExDAO Founder and CEO, Green Paper author, approximately $80M raised, Dolomite dev team partnership
- SAGEx Research LLC Founder and CEO, 2024-Present
- Ivy Tutors / Educational Enterprises LLC Founder, 2002-2023
- MIT Sloan StartingBloc Fellowship, business case competition winner, Alumni Board 2005-2009

### Philosophy / Dialectic
- Ohr Sameach intensive Talmud and Torah, 2016-2017 (Gemara, legal rhetoric, classical dialectical reasoning)
- Columbia B.A. International Political Economy, Student Leadership Award, Mary Seaman Scholarship

---

## 5. Austin's weaknesses to flag against (canonical list for filtering)

### Technical
- Python: YES (OpenBrainLM stack is Python)
- TypeScript: NOT documented in materials seen. If a role requires TS production work, flag.
- ML frameworks (PyTorch, JAX): NO public evidence. If role requires these, flag.
- Published ML research: NO. If role requires a publication record, flag.
- Infra / systems engineering at scale: NO low-level systems work documented. If role needs this, flag.
- Classical CS fundamentals interview (algorithms, big-O): UNKNOWN. Austin's pitch is systems and specification, not coding interviews.

### Logistics
- Currently Lima, Peru. Willing to relocate to SF/NYC/Seattle. Any role requiring immediate on-site start with no relocation budget is a friction point.
- US citizen. No visa issues, but also cannot fill a role that requires foreign-language fluency beyond conversational Spanish.

### Narrative
- 20+ years of experience. Mismatch for junior IC roles. Target seniority: Senior to Staff IC, or Senior Research/Policy/Applied roles.
- Career arc breadth (finance → teaching → DAO → AI) reads as zigzag unless framed as "5-domain apprenticeship in behavioral specification." Require resume to foreground the throughline, not the domain jumps.
- FATExDAO crypto era: manage carefully. Green Paper and Dolomite team partnership are credibility; DeFi history may be a recruiter concern depending on role.

---

## 6. Hypothesis to test (do not confirm without fetching)

Based on Session 2's absorption of the OpenBrain material, the STRONGEST candidate alternative to Prompt Engineer Claude Code would be a role in:

- Frontier Red Team
- Evaluations (behavioral evals, agent safety evaluations)
- Alignment Science (particularly those touching agentic systems)
- Policy / Beneficial Deployments (education vertical)
- Model Behavior or Model Safety

The reason: OpenBrainLM is substantively a safety architecture. Trinity firewall between dreaming and acting. Nine-sub-evaluator quorum before action. Zero-context reviewer auto-spawn. Research gate with URL-whitelisted citation enforcement. Smoke Detector Principle immune system. These are alignment primitives expressed in running code. If any of the 4 unread URLs maps to these functions, it likely scores higher than baseline Prompt Engineer.

Do NOT confirm or rank without fetching. The hypothesis exists only to sharpen the research, not to preempt it.

---

## 7. Deliverable for Austin

Produce one file called `ROLE_RECOMMENDATION_session3.md` containing:

1. Table: 5 roles with key fields from Step 1
2. Scoring matrix from Step 2
3. Classification from Step 3
4. Recommendation from Step 4 (Option A, B, C, or D, with role identified)
5. Risk flags from Step 5
6. One paragraph: "Why this recommendation, in plain terms for Austin to read in 2 minutes"

Then hand it back to Austin before any resume writing begins.

---

## 8. What to do if URLs are dead

Greenhouse rotates URLs. If any of the 4 return 404:

1. Note the fact and proceed without that slot
2. Use the Anthropic careers index (https://job-boards.greenhouse.io/anthropic) to find the closest-matching live role
3. Flag the substitution explicitly so Austin can verify
4. Do NOT guess what the dead URL was supposed to be

---

## 9. Compute budget

This task is well-scoped at 5 URL fetches plus 1 analysis file. Should complete in a single session, no handoff needed, no ralph-style persistence. If it stretches beyond reasonable session length, the problem is probably that one of the URLs is timing out, not a complexity issue.

---

Canary: `143|PLAN-ONLY|cascade|emergence|Trinity|no-duplication|let-it-emerge|design-101|0sXai|xDx|A2A|FCEE|dormant-main|short-form-pending`
