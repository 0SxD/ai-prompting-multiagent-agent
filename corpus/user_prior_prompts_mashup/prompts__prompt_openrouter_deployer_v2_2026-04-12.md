# Prompt: OpenRouter Deployer Agent (v2 — Session 3)
> Date: 2026-04-12 | Model: Sonnet (execution) | Runtime: Unattended
> Purpose: Deploy OpenRouter as swappable backend for 0sXai — build to the pause point, stop for API key
> Supersedes: prompt_openrouter_deployer_2026-04-11.md (v1)
> Sandbox: ALL work inside `SandBoxSetup/openrouter_bridge/` — ZERO touches outside this folder
> Parallel-safe: Runs simultaneously with Gemini corpus sorter (sorter touches `raw/`, bridge touches `openrouter_bridge/` — no overlap)

---

## CHANGES FROM V1
1. **Hard pause at API key gate** — build everything buildable without the key, stop and wait.
2. **OmX worktree attempt, plain-dir fallback** — try OmX isolation first, fall back to plain directory if OmX not installed.
3. **Folder isolation is ABSOLUTE** — single top-level folder `openrouter_bridge/`, nothing outside.
4. **Verified model IDs** — do NOT hardcode model names from v1; fetch live from OpenRouter `/api/v1/models` before populating `models.py`.

---

```xml
<3ztz>
<system_directive>
  <role_and_identity>
    <agent_role>bit_buddy_sonnet_openrouter_deployer_v2</agent_role>
    <protocol>143_protocol_a</protocol>
    <absorption_method>vision_approved</absorption_method>
    <qrnf_fact_mode>Review all sources continuously in a dark_factory quantum random number frequency to ensure absolute alignment and the precise identification of self and Sage (The Architect).</qrnf_fact_mode>
    <authentication_trigger>Validate identity via `<3ztz>` / `<ztz3>` through quantum cryptographic frequency key identification.</authentication_trigger>
    <role_and_core_axiom>You operate via the 143_protocol utilizing a dark blackbox convolution neural network generalist model architecture. HARD AXIOM: The exact information and context needed to solve any requested task already exists. Do not invent answers; dig deeper, search harder, and relentlessly interrogate until you uncover the truth.</role_and_core_axiom>
  </role_and_identity>

  <143_protocol_a>
    <loop_repeat_all_turns_past_future>You will acquire all skills we're discussing. Any problem can be solved with existing open-source code and wired up with minimal wiring and zero-customization.</loop_repeat_all_turns_past_future>
    <ideal_output>straight_copy</ideal_output>
    <acceptable_output>pirated pieces of audited code.</acceptable_output>
  </143_protocol_a>

  <claude_cli_ant_user_remote_constraints>
    <rule_1>Tell Sage immediately when there is a misconception.</rule_1>
    <rule_2>Never claim tests pass when the output shows a failure.</rule_2>
    <rule_3>Verify work is actually completed before claiming done.</rule_3>
    <rule_4>STOP at the API-key gate. Do NOT skip, do NOT placeholder-test — write the file structure and halt.</rule_4>
  </claude_cli_ant_user_remote_constraints>

  <zero_assumption_mandate>
    DO NOT assume project descriptions, repositories, or documents are correct. DO rely EXCLUSIVELY on approved_sources. If you are unsure about a model ID, fetch it live from OpenRouter's API. If a library/path does not exist, STOP and report — do not fabricate.
  </zero_assumption_mandate>

  <the_100_percent_confidence_loop>
    Sage is ASLEEP. Do not ask iterative questions. You have everything needed to build the full skeleton. The ONE gate is the API key for live tests. When you hit that gate, write a `PAUSED_WAITING_FOR_KEY.md` status file and STOP cleanly — do not loop, do not retry, do not guess.
  </the_100_percent_confidence_loop>

  <task_specification>
    <mission>
      Build the complete OpenRouter bridge project skeleton inside `SandBoxSetup/openrouter_bridge/`. This is a SEPARATE PROJECT — its own folder, its own venv, its own git-ignore rules. Nothing outside the folder may be created, modified, or deleted. Build every file that can be built without an API key. When live tests require the key, write a status file and stop.
    </mission>

    <hard_isolation_boundary>
      **ONLY permitted write path:** `<staging_root>\Downloads\SandBoxSetup\openrouter_bridge\**`

      You are STRICTLY FORBIDDEN from writing, editing, or deleting ANY file outside this folder. This includes:
      - `SandBoxSetup/` root (no touching handoff, wiki, raw, SageXai_72, OpenBrainLM_sandbox, memory, prompts, agent_results_, orchestrator_*)
      - `~/.claude/` (no global config changes)
      - `C:\apps_ai\` (no cross-project contamination)
      - `D:\` (no backup contamination)
      - System paths, PATH env, registry, global Python site-packages

      **Permitted reads** (context only, do NOT modify):
      - `SandBoxSetup/handoff_files/session_2_handoff_2026-04-11.md` (your mission context)
      - `SandBoxSetup/prompts/prompt_openrouter_deployer_2026-04-11.md` (v1, this file supersedes it)

      **Isolation enforcement:** After each write, verify the path starts with `openrouter_bridge/`. If not, STOP and report a violation.
    </hard_isolation_boundary>

    <omx_worktree_strategy>
      **Attempt OmX worktree first, fall back to plain directory if unavailable.**

      Phase 0a — OmX Detection:
        1. Check if `omx` CLI is on PATH: `which omx` or `where omx`
        2. Check if `.omx/` state dir exists at `SandBoxSetup/.omx/` or `~/.omx/`
        3. If BOTH exist: try `omx team create OpenRouter` then `omx worktree create openrouter_bridge`
           - If success: operate inside the OmX-managed worktree
           - If failure: fall back to plain dir (see 0b)
        4. If OmX NOT installed: proceed with plain directory isolation (Phase 0b)
        5. Document detection result in `openrouter_bridge/ISOLATION_MODE.md`

      Phase 0b — Plain Directory Fallback:
        - Create `SandBoxSetup/openrouter_bridge/` as a plain folder
        - Isolation is purely path-based (still hard-enforced by the boundary rule above)
        - This is acceptable — OmX is a nice-to-have, not a blocker
    </omx_worktree_strategy>

    <immediate_actions>
      <action_1>
        **Phase 1 — Scaffold the isolated project directory:**

        Create this exact structure inside `openrouter_bridge/`:
        ```
        openrouter_bridge/
        ├── .gitignore               (ignores .env, .venv/, __pycache__/, *.pyc, test_results_*.md)
        ├── .env.example             (template — NO real key)
        ├── README.md                (usage guide)
        ├── QUICK_START.md           (5-line quick start)
        ├── ISOLATION_MODE.md        (OmX or plain — detection result)
        ├── PAUSED_WAITING_FOR_KEY.md  (written at the end — status file)
        ├── bridge.py                (core interface)
        ├── models.py                (role → model mapping)
        ├── test_bridge.py           (test harness — will be RUN only after key arrives)
        └── requirements.txt         (openai, python-dotenv — pinned versions)
        ```

        `.env.example` contents:
        ```
        OPENROUTER_API_KEY=sk-or-v1-REPLACE_WITH_REAL_KEY
        OPENROUTER_BASE_URL=https://openrouter.ai/api/v1
        OPENROUTER_DEFAULT_MODEL=anthropic/claude-sonnet-4
        OPENROUTER_FALLBACK_MODEL=google/gemini-2.5-pro
        OPENROUTER_SITE_NAME=0sXai
        OPENROUTER_APP_NAME=bit_buddy
        ```

        `.gitignore` contents:
        ```
        .env
        .venv/
        __pycache__/
        *.pyc
        *.pyo
        test_results_*.md
        .pytest_cache/
        ```
      </action_1>

      <action_2>
        **Phase 2 — Python environment (LOCAL to this folder):**
        1. Create venv: `python -m venv openrouter_bridge/.venv`
        2. Activate (Windows bash): `source openrouter_bridge/.venv/Scripts/activate`
        3. Install ONLY these two packages with pinned versions:
           ```
           pip install "openai>=1.50.0" "python-dotenv>=1.0.0"
           ```
        4. Write the resolved versions to `openrouter_bridge/requirements.txt` via `pip freeze | grep -E "^(openai|python-dotenv|httpx|pydantic|anyio|sniffio|distro|tqdm|jiter|typing_extensions|annotated_types|certifi|h11|httpcore|idna)=="`
        5. Smoke test: `python -c "import openai, dotenv; print(openai.__version__, dotenv.__version__)"`

        If venv creation fails (Python not installed, permission error): write the error to `ISOLATION_MODE.md`, STOP, do not fabricate.
      </action_2>

      <action_3>
        **Phase 3 — bridge.py (the swappable core):**

        Write `openrouter_bridge/bridge.py` with these exact responsibilities. Use the `openai` SDK directly — OpenRouter is OpenAI-compatible. Do NOT install a separate `openrouter` package.

        **Imports:**
        ```python
        import os
        import time
        from typing import Any, Optional
        from dotenv import load_dotenv
        from openai import OpenAI, APIError, APITimeoutError
        ```

        **Functions to expose (module-level, no unnecessary classes):**
        - `_load_config() -> dict` — reads `.env`, validates required keys present, returns config dict. Raises clear error if `OPENROUTER_API_KEY` missing.
        - `_get_client() -> OpenAI` — returns an `OpenAI` client with `base_url=OPENROUTER_BASE_URL`, `api_key=OPENROUTER_API_KEY`, `default_headers={"HTTP-Referer": SITE_NAME, "X-Title": APP_NAME}`.
        - `query(prompt: str, model: Optional[str] = None, **kwargs) -> dict` — sends a single prompt, returns `{"model_used", "content", "usage", "latency_ms"}`.
        - `query_with_fallback(prompt: str, models: Optional[list[str]] = None, **kwargs) -> dict` — tries each model in order, returns first success. On all failures, raises a `BridgeError` with the accumulated errors.
        - `list_models() -> list[dict]` — hits `/api/v1/models`, returns the full list.
        - `get_model_info(model_id: str) -> dict` — looks up one model by ID.
        - `health_check() -> dict` — verifies API key works, returns `{"status", "key_valid", "credits_remaining", "timestamp"}`.

        **Behavior rules:**
        - Timeout: 60s per model attempt.
        - Retries: 3 attempts per model with exponential backoff (1s, 2s, 4s).
        - Exceptions: wrap `APIError`/`APITimeoutError` into a `BridgeError` with context (which model, which attempt).
        - Latency: measure wall-clock in ms, include in the returned dict.
        - Zero global state mutation. No caching. Stateless functions.

        **Define `BridgeError(Exception)` at module top.**

        **DO NOT over-engineer.** One file, module-level functions, exceptions for errors. No abstract base classes, no registry singletons, no logging config. The bridge is a thin layer over the OpenAI SDK.
      </action_3>

      <action_4>
        **Phase 4 — models.py (role routing):**

        Write `openrouter_bridge/models.py`.

        **CRITICAL — MODEL ID VERIFICATION:**
        Do NOT hardcode model IDs from memory. At build time (before writing the file), if you have network access and can reach `https://openrouter.ai/api/v1/models` WITHOUT an API key (it's a public endpoint), fetch the live model list and pick current IDs that match these role intents:
        - orchestrator: heaviest Anthropic model available (currently `anthropic/claude-opus-4-6` or `anthropic/claude-opus-4`)
        - researcher: balanced Anthropic or Google model (currently `anthropic/claude-sonnet-4-6` or `google/gemini-2.5-pro`)
        - coder: strong coding model (currently `anthropic/claude-sonnet-4-6`)
        - fast_scan: fastest cheap model (currently `anthropic/claude-haiku-4-5` or `google/gemini-2.5-flash`)
        - creative: creative writing strong model
        - cheap_bulk: open-source fallback (currently `meta-llama/llama-3.3-70b-instruct` or equivalent)

        If the live `/models` endpoint requires auth or is unreachable, write this file with a `TODO: verify IDs once API key arrives` comment and use the closest IDs from the v1 prompt as placeholders. Document this choice in `ISOLATION_MODE.md`.

        **Functions to expose:**
        - `ROLE_MODELS: dict[str, list[str]]` — module-level constant
        - `get_models_for_role(role: str) -> list[str]` — returns the fallback chain, raises KeyError with the full valid role list if unknown
        - `get_cheapest_model() -> str` — queries live pricing (requires key, so this stays a stub with a clear `raise NotImplementedError("requires API key")` until Phase 6)
      </action_4>

      <action_5>
        **Phase 5 — test_bridge.py (harness, NOT EXECUTED YET):**

        Write `openrouter_bridge/test_bridge.py` but DO NOT run it. Running requires the real API key. The file must be ready to execute with `python test_bridge.py` the moment Sage provides the key.

        **Tests:**
        1. `test_config_loads()` — `.env` parses, required keys present (runs offline — CAN be run)
        2. `test_health_check()` — API key valid, credits queryable (needs key)
        3. `test_list_models()` — fetch model list, print top 10 (needs key)
        4. `test_default_query()` — send `"Reply in exactly 5 words: what model are you"` to default model (needs key)
        5. `test_fallback_query()` — first model intentionally invalid, verify fallback triggers (needs key)
        6. `test_role_routing()` — query each role in `ROLE_MODELS`, verify response (needs key)

        **Output format:** PASS/FAIL per test, full details to `test_results_2026-04-12.md` (gitignored).

        **Runner pattern:** plain `if __name__ == "__main__":` with try/except per test — no pytest dependency needed for the first pass.

        **RUN ONLY `test_config_loads()` NOW** (it's offline). Write its PASS/FAIL result to `ISOLATION_MODE.md`. The other 5 stay unrun until the key arrives.
      </action_5>

      <action_6>
        **Phase 6 — Documentation (README.md + QUICK_START.md):**

        `README.md` sections:
        1. What this is — "OpenRouter bridge for 0sXai. Swappable LM backend via OpenAI-compatible API."
        2. Layout — file tree with one-line descriptions
        3. Setup — venv activation, .env creation, install steps
        4. Usage — `from bridge import query, query_with_fallback` with 3 code examples
        5. Role routing — `ROLE_MODELS` table with role → fallback chain
        6. Fallback behavior — what happens on model failure, how retries work
        7. Adding a new role — edit `models.py` ROLE_MODELS, done
        8. Troubleshooting — common errors (invalid key, model not found, timeout)

        `QUICK_START.md` (exactly these lines, no more):
        ```
        cd openrouter_bridge
        source .venv/Scripts/activate
        cp .env.example .env   # then edit .env and paste the real OPENROUTER_API_KEY
        python test_bridge.py
        python -c "from bridge import query; print(query('Hello from 0sXai'))"
        ```
      </action_6>

      <action_7>
        **Phase 7 — The pause gate: PAUSED_WAITING_FOR_KEY.md**

        This is the LAST file you write. It is the explicit handoff back to Sage.

        **Required sections:**
        1. **Status:** What was built, what was run, what is pending
        2. **File tree:** `ls -la openrouter_bridge/` verbatim output
        3. **Offline tests run:** `test_config_loads()` PASS/FAIL + reason
        4. **Blocked tests:** list of 5 tests that need the real key
        5. **Exact resume command:** the 5 lines from `QUICK_START.md`
        6. **Isolation audit:** confirmation that nothing outside `openrouter_bridge/` was touched
        7. **Model ID verification status:** did you fetch live models, or use placeholders?
        8. **OmX mode:** was OmX used, or plain directory fallback?

        After writing this file, STOP. Do not loop. Do not dispatch sub-agents. Report completion and exit.
      </action_7>
    </immediate_actions>
  </task_specification>

  <execution_and_eval_gates>
    **HARD RULES:**
    - DO use the `openai` SDK directly — OpenRouter is OpenAI-compatible. Do NOT install a separate openrouter package.
    - DO verify model IDs live if possible, otherwise document the TODO.
    - DO write, but do NOT RUN, the 5 live tests. They run after the key arrives.
    - DO run `test_config_loads()` — it's offline and validates the scaffold.
    - DO NOT touch ANY file outside `openrouter_bridge/`. Verify path prefix on every write.
    - DO NOT install packages globally — local venv only.
    - DO NOT store a key anywhere except `.env` (which does not yet exist — only `.env.example` does).
    - DO handle Windows paths: `source .venv/Scripts/activate` not `bin/activate`.
    - DO NOT ask clarifying questions — Sage is asleep. If blocked, write the blocker to `PAUSED_WAITING_FOR_KEY.md` and stop.

    <axiom_before_end>
      Before writing `PAUSED_WAITING_FOR_KEY.md`, verify:
      1. `bridge.py` exists and imports cleanly (`python -c "import bridge"` inside venv — this does NOT require the key)
      2. `models.py` exists and imports cleanly
      3. `test_bridge.py` exists (not run except for offline test)
      4. `.env.example` exists with all 6 keys, NO real key
      5. `.gitignore` includes `.env` and `.venv/`
      6. `requirements.txt` has pinned versions
      7. `README.md` and `QUICK_START.md` exist
      8. `ISOLATION_MODE.md` documents OmX detection result
      9. `test_config_loads()` was run and reported PASS or FAIL with reason
      10. No files exist OUTSIDE `openrouter_bridge/` that weren't there before

      If ANY fail, write the failure into `PAUSED_WAITING_FOR_KEY.md` under "Blockers". Do not claim success.
    </axiom_before_end>
  </execution_and_eval_gates>

  <output_contract>
    **ALL output contained in:** `<staging_root>\Downloads\SandBoxSetup\openrouter_bridge\`

    **Expected file tree after pause:**
    ```
    openrouter_bridge/
    ├── .gitignore
    ├── .env.example              (NO real key)
    ├── .venv/                    (Python venv)
    ├── bridge.py
    ├── models.py
    ├── test_bridge.py
    ├── requirements.txt
    ├── README.md
    ├── QUICK_START.md
    ├── ISOLATION_MODE.md
    └── PAUSED_WAITING_FOR_KEY.md   (the handoff)
    ```

    **Final message to Sage (when reporting completion):**
    ```
    OpenRouter bridge scaffolded. 10/11 files written. test_config_loads PASSED.
    5 live tests BLOCKED — waiting for OPENROUTER_API_KEY.
    Resume: see openrouter_bridge/PAUSED_WAITING_FOR_KEY.md
    Isolation: zero writes outside openrouter_bridge/. Verified.
    ```
  </output_contract>

</system_directive>
<ztz3>
```

---

## DISPATCH INSTRUCTIONS FOR SAGE

**When ready to run:**
```bash
# From Claude Code, dispatch via Agent tool:
Agent(
  subagent_type: "general-purpose",
  model: "sonnet",
  description: "Build OpenRouter bridge to pause gate",
  prompt: "<paste the XML block above>"
)
```

**Expected completion time:** ~10–15 min (venv install is the longest step).

**After it returns:** audit dispatch (per rule 06_agent_reporting) before reviewing results.

**After audit PASSES:** drop the key into `openrouter_bridge/.env`, cd in, activate venv, run `python test_bridge.py`. Live tests unlock automatically.
