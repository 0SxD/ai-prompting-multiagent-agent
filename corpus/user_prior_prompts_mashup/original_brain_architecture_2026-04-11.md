# OpenBrainLM — Complete Architecture Map
> Research-only output. Compiled 2026-04-11 from all sandbox architecture documents.
> Source: `OpenBrainLM_sandbox/` — BIRTHDAY.md, ARCHITECTURE.md, OPERATIONAL_LAYERS.md, AGENT_RULES.md,
>   OPEN_BRAIN.md, WHITEPAPER.md, WHAT_IS_OPENBRAIN.md, IMPLEMENTATION_PLAN.md,
>   docs/specs/SELF_EVOLUTION_LOOP.md, docs/specs/EPIMORPHIC_REGENERATION.md,
>   docs/specs/ALLOSTATIC_DECISION_GATE.md, docs/concept_papers/01_THE_DIALECTIC_LOOP.md,
>   and all memory/ files.

---

## CRITICAL DUAL-TRACK REALITY

**Biological Python architecture** = VISION/CONCEPT. Frozen. 135 tests pass. Do NOT modify.
**Operational harness** = Trinity dialectic + memory consolidation + brainstem hooks. This is what runs NOW.

Source: CLAUDE.md — "Do NOT mix vision language into operational work. No biological naming, no 'queen pheromone', no 'hippocampal', no 'basal ganglia' in operational context."
Source: trinity_mode_spec.md — "the operational harness IS Trinity Mode + memory. That's it."

---

## 1. ORIGIN — BIRTHDAY.md

- Born overnight 2026-03-20 in a single session
- Adversarial audit received grade **B-** (not F, not A)
- Two immediate corrections from audit: 10 layers → 8 layers, Trinity definition clarified
- Quote: "We didn't just read about it. We took on the adversarial audit. We corrected. We improved."
- The audit process itself validated the dialectic design pattern

---

## 2. THREE BIOLOGICAL SUBSTRATES

Source: WHITEPAPER.md §2.1–2.6, OPERATIONAL_LAYERS.md hybrid justification table

### Substrate 1 — Octopus (Distributed Cognition)
- **Biology**: 500M neurons, 2/3 in arms. Arms process independently, act autonomously.
- **RNA editing**: 60% of transcriptome recoded without DNA changes = reversible adaptation
- **Principle extracted**: Distributed processing; peripheral intelligence; reversible learning
- **Compute analog**: Agent arms process independently; RNA editing → weight mutation during sleep (NEAT)
- **Key weakness**: No persistent long-term memory (short lifespan)

### Substrate 2 — Insect Colony (Emergence + Stigmergy)
- **Biology**: No central command. Individual ants follow pheromone gradients. Colony-level intelligence emerges.
- **Quorum sensing**: Bees use quorum threshold (usually 15) before committing to a new hive site
- **Principle extracted**: Stigmergy (indirect coordination via environment); emergence; quorum thresholds
- **Compute analog**: Pheromone files (research/*.md, memory/*.md, OPEN_BRAIN.md); L3 stigmergy layer; L6 quorum sensing
- **Key weakness**: No individual learning; slow to adapt to novel threats

### Substrate 3 — Human Brain (Memory + Inhibition + Dialectic)
- **Biology**: Hippocampus (memory consolidation), Amygdala (threat/emotion gating), Basal Ganglia (inhibition-by-default), DMN (self-referential/creative), Prefrontal Cortex (executive control)
- **Principle extracted**: Inhibition-by-default (BG); sleep consolidation (hippocampus); emotional gating (amygdala); dialectic reasoning (prefrontal); dreaming/exploration (DMN)
- **Compute analog**: L4 inhibition gate; L5 memory consolidation; L6 threat assessment; L8 exploration mode
- **Key weakness**: Single-instance bottleneck; slow; energy-expensive

### Complementary Weaknesses Table (from WHITEPAPER.md)
| Weakness | Solution substrate |
|---|---|
| Octopus: no long-term memory | Human brain hippocampus |
| Insect colony: no individual learning | Octopus distributed processing |
| Human brain: single-instance bottleneck | Insect colony parallelism |

---

## 3. EIGHT COGNITIVE AGENTS

Source: ARCHITECTURE.md agents table, OPERATIONAL_LAYERS.md, WHITEPAPER.md §5

All agents derived from **SPAUN 2.0** (Eliasmith et al.) — 2.5M neuron functional brain model.
Boot state: 8 agents initialized at startup; system self-evolves from there.

| Agent | Role | Biology | Status |
|---|---|---|---|
| hippocampus | Memory storage + retrieval + consolidation | Hippocampus (CA1/CA3/DG) | Functional stub |
| explorer | Novel path generation; serendipitous discovery | DMN + curiosity circuits | Functional stub |
| verifier | Cross-reference claims against known corpus | Prefrontal working memory | Functional stub |
| immune | Detect foreign/malicious content; quarantine | Immune system + amygdala threat detection | Functional stub |
| prefrontal | Executive planning; task decomposition | Prefrontal cortex (DLPFC) | Functional stub |
| morphogen | Architecture evolution (NEAT); fitness evaluation | Morphogen gradient fields | Functional stub |
| consolidator | Memory promotion (short→long); quality gating | Hippocampal consolidation | Functional stub |
| homeostasis | Resource monitoring; allostatic regulation | Hypothalamus + autonomic NS | Functional stub |

**Note**: "Functional stubs" = basic implementations that pass 135 tests. NOT production agents. Agents are CONCEPT, not deployed harness.

---

## 4. EIGHT OPERATIONAL LAYERS

Source: OPERATIONAL_LAYERS.md v2 (corrected from 10 layers after adversarial audit)

### L1 — Active Sensing (Perceptual Front-End)
- **Biology**: Reticular activating system; sensory cortex
- **Principle**: Pre-attentive filtering; signal from noise before cognitive processing
- **Implementation**: Input normalization; token/context preprocessing; relevance scoring
- **Status**: Specification complete; Python stub

### L2 — Ganglion (Peripheral Processing)
- **Biology**: Octopus arm ganglions (local processing without central brain)
- **Principle**: Peripheral autonomy; offload routine processing from central layers
- **Implementation**: Parallel sub-agent workers; routine query handlers
- **Status**: Specification complete; Python stub

### L3 — Stigmergy + Swarm (Indirect Coordination)
- **Biology**: Ant pheromone trails; termite mound construction
- **Principle**: Agents coordinate via environment (files), not direct communication
- **Implementation**: Pheromone file system (see §9 below); shared task signals; research/*.md trail files
- **Status**: Partially operational (pheromone files exist and are used)

### L4 — Basal Ganglia + Thalamus (Action Selection Gate)
- **Biology**: Basal ganglia = inhibition-by-default. Thalamus = routing relay.
- **Principle**: **ALL channels SUPPRESSED. Actions RELEASED, not activated.** The brain doesn't fire neurons to stop — it stops firing neurons to act.
- **Implementation**: brainstem.md + brainstem_inject.sh PreToolUse hook = L4 in production. Every tool call passes through inhibition gate before execution.
- **Status**: OPERATIONAL (brainstem hook live)
- **Key insight**: This is the only layer that is fully operational as described

### L5 — Hippocampus + Prefrontal (Memory + Executive)
- **Biology**: Hippocampus: episodic memory, spatial navigation, consolidation during sleep. Prefrontal: working memory, planning, inhibitory control.
- **Principle**: Two-phase sleep (quiet consolidation + active replay); schema-driven memory promotion
- **Implementation**: short_term.md → long_term.md → archival NotebookLM. Trinity Consolidation lifecycle.
- **Status**: OPERATIONAL (memory files live; consolidation protocol active)

### L6 — Amygdala + Quorum (Threat + Consensus)
- **Biology**: Amygdala: fast-path threat detection bypassing cortex. Bee quorum: 15+ scouts required before hive move.
- **Principle**: Threat gating; consensus thresholds before irreversible actions
- **Implementation**: Rule 00 (no public actions without approval); immune agent quarantine; knowledge promotion 2/2 quorum (immune + domain agent)
- **Status**: Operationally enforced via rules; Python stub for agent layer

### L7 — Chromatophore (Adaptive Output)
- **Biology**: Octopus chromatophores: millisecond color/texture change for camouflage or signaling
- **Principle**: Output adapts to context/audience; same knowledge, different presentation
- **Implementation**: Output style adaptation; audience-aware formatting
- **Status**: Specification complete; not yet implemented

### L8 — Pathos + DMN (Identity + Exploration)
- **Biology**: Default Mode Network: active during rest, self-referential thought, creativity, future simulation
- **Principle**: Identity coherence; exploratory divergent thinking; "dreaming" = consolidation + novel connection
- **Implementation**: Pathos voice in Trinity dialectic; OPEN_BRAIN.md as queen pheromone / identity anchor
- **Status**: Operationally active (Pathos role in Trinity; OPEN_BRAIN.md live)

---

## 5. FOUR CROSS-CUTTING MECHANISMS + 5TH ALLOSTATIC GATE

Source: OPERATIONAL_LAYERS.md cross-cutting mechanisms section, ALLOSTATIC_DECISION_GATE.md

### Mechanism 1 — Hebbian STDP (Spike-Timing Dependent Plasticity)
- **Biology**: Neurons that fire together wire together; timing of co-activation determines connection weight
- **Implementation**: connection_strengths.json — tracks which agent pairs co-activate; weights update after each task
- **Status**: Specified; not yet implemented

### Mechanism 2 — Sleep Consolidation Protocol
- **Biology**: Two sleep phases — slow-wave (quiet consolidation, hippocampus → neocortex) + REM (active replay, novel connection formation)
- **Implementation**: Two-phase consolidation: (1) quiet = Trinity Consolidation at breakpoints; (2) active = morphogen NEAT evolution during session end
- **Triggers**: Memory pressure | Task completion | Session end | User-initiated
- **Status**: Phase 1 (quiet) operationally active; Phase 2 (NEAT evolution) specification only

### Mechanism 3 — RNA Editing Analog (Reversible Adaptation)
- **Biology**: Octopus recodes 60% of transcriptome via A-to-I RNA editing; reversible without DNA mutation
- **Implementation**: NEAT weight mutation during sleep phase; weights can be rolled back; not permanent architecture changes
- **Status**: Specified in EPIMORPHIC_REGENERATION.md; not yet implemented

### Mechanism 4 — Epimorphic Regeneration (Arm Regrowth Analog)
- **Biology**: Octopus regenerates lost arms through blastema — undifferentiated cell mass that redifferentiates
- **Implementation**: Blastema sandbox — 6-stage lifecycle for risky changes
- **6 Stages**: DETECT (failure signature) → ISOLATE (quarantine failing component) → DESIGN (candidate replacement in shadow) → SHADOW (run old+new in parallel, compare outputs) → CANARY (route 5% traffic to new) → PROMOTE (swap, archive old)
- **Status**: Specified in EPIMORPHIC_REGENERATION.md; not yet implemented

### Mechanism 5 (5th) — Allostatic Decision Gate
- **Allostasis vs homeostasis**: Homeostasis = maintain fixed setpoint. Allostasis = adjust setpoint based on predicted future load (proactive, not reactive).
- **Three signals evaluated**:
  1. `is_structural_failure` — is it a fundamental design flaw?
  2. `is_degrading_faster_than_sleep` — is performance degrading faster than sleep can heal?
  3. `is_blocking_current_task` — is it blocking right now?
- **Four-tier escalation**:
  | Tier | Condition | Action |
  |---|---|---|
  | WAIT_FOR_SLEEP | Default (none of above) | Log, continue, fix during next sleep |
  | BLASTEMA_SANDBOX | Structural failure only | Launch 6-stage shadow rebuild |
  | PRIORITY_SLEEP | Degrading faster than sleep | Trigger immediate consolidation |
  | EMERGENCY_AUTOTOMY | Blocking current task | Disable component, route around, alert |
- **Default**: Always WAIT_FOR_SLEEP. The system is biased toward patience.
- **Biological source**: Glucocorticoid anticipatory stress response; octopus autotomy (arm self-amputation as last resort)
- **Status**: Specified in ALLOSTATIC_DECISION_GATE.md; not yet implemented

---

## 6. TRINITY DIALECTIC ENGINE

Source: WHAT_IS_OPENBRAIN.md, OPEN_BRAIN.md, trinity_mode_spec.md, docs/concept_papers/01_THE_DIALECTIC_LOOP.md

### Core Definition (from OPEN_BRAIN.md)
"Trinity is the dialectic: Logos vs Pathos, both armed with Ethos. The fight IS the thinking. Not a pipeline. Not a vote. A structured disagreement that cannot resolve without evidence."

### Three Voices
| Voice | Role | Bias | Weapon |
|---|---|---|---|
| **Ethos** | Evidence corridors + rules + evaluation criteria | Neutral — sets the arena | Shared evidence (same ammunition for both sides) |
| **Pathos** | Creative/ambitious path; longest route | Expansive; wants to build | Evidence from Ethos, used to argue for ambition |
| **Logos** | Proven/safe path; shortest route | Conservative; wants to constrain | Same evidence from Ethos, used to argue for caution |

### Key Insight (Concept Paper 1)
"Ethos is the shared ammunition, not the arbiter. Both Logos and Pathos must use the same evidence pool. Neither side can win by assertion — only by evidence. The fight IS the thinking."

### Operational Implementation (trinity_mode_spec.md — AUTHORITATIVE)
- **Ethos** = corridors + rules + evaluation criteria (set per task by Sage)
- **Pathos** = Opus doing work, managing agents and memory
- **Logos** = Sonnet subagent checking Pathos's work against Ethos
- No biological naming in operational context

### Trinity of Trinities
Each of the 3 voices has its own internal Ethos/Logos/Pathos = **9 sub-evaluators total**

**Logos internal triad** (3 questions):
1. Is this logically consistent with what we know?
2. What is the shortest proven path to the goal?
3. What evidence contradicts this approach?

**Pathos internal triad** (3 questions):
1. What is the most ambitious interpretation of the goal?
2. What novel connection have we not considered?
3. What would we do if we knew we couldn't fail?

**Ethos internal triad** (3 questions):
1. Does this align with the stated mission and values?
2. What are the ethical implications and second-order effects?
3. What evidence pool should both sides draw from?

**Resolution gate**: Any of the 9 sub-evaluators can block. Unanimous pass required. If deadlock at 10 rounds → escalate to Sage.

### Weighting Gate Formula (WHAT_IS_OPENBRAIN.md)
Configurable per task: `α × Ethos_score + β × Logos_score + γ × Pathos_score`
Default weights unspecified — set by task context.

### AlphaEvolve Integration (Concept Paper 1)
- AlphaEvolve (DeepMind) meta-evolves the Ethos criteria themselves
- The evaluation criteria are not fixed — they co-evolve with the system
- "Scaling from research verification to consciousness" — the same dialectic pattern applies at any scale

---

## 7. FIVE-PHASE EVOLUTION ROADMAP

Source: ARCHITECTURE.md roadmap, IMPLEMENTATION_PLAN.md phase sequence, memory/long_term.md (Phase 2+ TABLED per Austin directive 2026-03-23)

### Phase 1 — DONE ✓
- Python CLI (`python -m openbrainlm`)
- 8 cognitive agents (stubs), 8 brain regions
- 135 tests pass
- Biological naming in code (FROZEN — do not modify)

### Phase 2 — TABLED (Austin directive 2026-03-23)
- Reference implementations for each agent
- Intended libraries: LangChain agents, Chroma vector store
- Status: BLOCKED until further notice — focus shifted to operational harness

### Phase 3a — TABLED
- Sleep cycle implementation (quiet consolidation automation)
- Intended: scheduled task runner; consolidation agent chain

### Phase 3b — TABLED
- Epimorphic regeneration (NEAT + blastema sandbox)
- Intended library: neat-python (BSD license) for weight evolution

### Phase 4 — TABLED
- LangGraph orchestrator replacing custom agent dispatch
- Intended: LangGraph (MIT) workflow graph; state machines

### Phase 5 — TABLED
- Community release; contributor onboarding
- Requires Phase 1-4 complete and stable

**Current focus**: Operational harness only — Trinity dialectic, memory consolidation, brainstem hooks, NotebookLM archival.

---

## 8. MEMORY ARCHITECTURE

Source: ARCHITECTURE.md memory section, OPERATIONAL_LAYERS.md L5, SELF_EVOLUTION_LOOP.md, memory/long_term.md, memory/trinity_mode_spec.md

### Three-Tier Model
| Tier | File | Lifecycle | Promotion criteria |
|---|---|---|---|
| Working memory | Context window | Session-scoped; lost on compression | Consolidate before compression |
| Short-term | short_term.md | Session + recent; cleared after consolidation | Verified + schema-complete → long_term |
| Long-term | long_term.md | Permanent; never deleted | Human review or Confidence Bouncer (≥0.6) |
| Archival | NotebookLM (23 notebooks) | Permanent; queryable from any project | Manual curation |

### Consolidation Quality Gates (Pattern 2 — schema-driven)
Every entry promoted to long_term.md MUST include:
1. **Statement** — the claim
2. **Confidence** — 0.0–1.0
3. **Source** — exact citation
4. **Status** — verified | disputed | needs_review
5. **Last Verified Date** — YYYY-MM-DD

Entries missing any field stay in short_term.md until complete.

### Three Consolidation Loops (SELF_EVOLUTION_LOOP.md)
1. **Memory pressure loop**: working memory approaches limit → immediate short_term.md write
2. **Task completion loop**: major task done → findings → short_term.md → Trinity Consolidation
3. **Session end loop**: full Trinity Consolidation; promote to long_term; update connections.md; clear processed items

### Confidence Bouncer (Pattern 5)
Claims with confidence < 0.6 → quarantined, NOT promoted. Flag "needs_review", notify Sage.

### Frequency Anti-Pattern WARNING (Pattern 8)
NEVER prune memory based on access frequency. AI optimizes for statistical saliency (noise), not importance. Human-in-the-loop or confidence bouncer ONLY for pruning.

### Hebbian STDP Implementation
- connection_strengths.json tracks co-activation frequency between agent pairs
- After each task: update weights for all co-activating agents
- Informs routing decisions at L4

---

## 9. PHEROMONE TAXONOMY (L3 Stigmergy Layer)

Source: AGENT_RULES.md pheromone taxonomy

| Type | File pattern | Decay | Purpose |
|---|---|---|---|
| Trail | research/*.md | 1 month | Research paths; stale after 1 month = mandatory refresh |
| Alarm | barrier entries in memory | Never | Block propagation of bad patterns |
| Nest | memory/*.md | Persistent | Accumulated knowledge; session state |
| Queen | OPEN_BRAIN.md | Persistent | Core identity; in every brain region |
| Recruitment | task signals | Session-scoped | Agent coordination; what needs attention now |

**Queen pheromone rule**: OPEN_BRAIN.md is copied/referenced in every project brain. It IS the cross-project identity signal.

---

## 10. SELF-EVOLUTION LOOP

Source: docs/specs/SELF_EVOLUTION_LOOP.md

### Three Missing Feedback Loops (identified in spec)
1. **Consolidation triggers** — when does sleep fire?
2. **Morphogen fitness function** — what makes an architecture "better"?
3. **Knowledge promotion barrier** — what prevents bad knowledge from promoting?

### Morphogen Fitness Function
```
fitness = α × prediction_accuracy + β × handoff_efficiency + γ × dialectic_efficiency
defaults: α=0.4, β=0.4, γ=0.2
```
The weights α/β/γ themselves meta-evolve — the fitness function is not fixed.

### Knowledge Promotion Barrier Protocol
- Requires **2/2 unanimous quorum**: immune agent + domain-specific agent both PASS
- Either agent can block promotion
- Blocks bad/malicious/unverified knowledge from entering long_term.md
- Source: L6 quorum sensing (bee threshold pattern)

### NEAT Evolution (Morphogen Agent)
- Library: neat-python (BSD license)
- Runs during sleep phase (quiet consolidation complete)
- Mutates agent connection weights, not architecture
- RNA editing analog: reversible; can roll back
- neat_config.ini: pop_size=50, elitism=2, survival_threshold=0.2

---

## 11. EPIMORPHIC REGENERATION

Source: docs/specs/EPIMORPHIC_REGENERATION.md

### Two Biological Mechanisms
1. **RNA editing analog** (already covered in §5 Mechanism 3): reversible weight mutation, no DNA change
2. **Arm regeneration analog**: blastema — structural rebuild of failed component

### Blastema Sandbox — 6-Stage Lifecycle
| Stage | Bio mapping | Compute action |
|---|---|---|
| DETECT | Arm nerve signals injury | Failure signature identified (3+ repeated failures) |
| ISOLATE | Autotomy — arm self-severs | Failing component quarantined; traffic rerouted |
| DESIGN | Blastema forms (undifferentiated cells) | Candidate replacement designed in isolation |
| SHADOW | Blastema redifferentiates alongside old tissue | New + old run in parallel; outputs compared |
| CANARY | New limb tested under load | 5% of real traffic routed to new component |
| PROMOTE | Old limb fully replaced | Swap complete; old component archived (never deleted) |

### Shadow Mode Detail
- Old component continues serving 100% of traffic during SHADOW
- New component receives same inputs; outputs compared but NOT served
- Divergence threshold triggers rollback to DESIGN
- No user-visible change until CANARY

---

## 12. EIGHT BRAIN REGIONS

Source: ARCHITECTURE.md brain regions table

| Region | Function | Analogous biology |
|---|---|---|
| Hippocampus | Episodic memory; spatial navigation; consolidation | CA1/CA3/DG hippocampal fields |
| Prefrontal Cortex | Executive planning; working memory; inhibitory control | DLPFC + OFC |
| Amygdala | Threat detection; emotional salience; fast-path gating | Basolateral + central amygdala |
| Basal Ganglia | Action selection via inhibition-by-default; habit formation | Striatum + GPi/GPe + SNr |
| Thalamus | Routing relay; sensory gating; attention modulation | VPL + MD nuclei |
| Default Mode Network | Self-referential thought; creativity; future simulation | Medial PFC + PCC + angular gyrus |
| Cerebellum | Precision timing; error correction; motor learning | Purkinje cells + deep cerebellar nuclei |
| Brainstem | Arousal regulation; autonomic; vital functions | Reticular formation + LC + raphe |

---

## 13. PROCESSING PIPELINE

Source: ARCHITECTURE.md system diagram, WHITEPAPER.md architecture section

```
Input
  ↓ L1 Active Sensing (pre-attentive filter)
  ↓ L2 Ganglion (peripheral processing; parallel sub-agents)
  ↓ L3 Stigmergy (read pheromone files; update trail)
  ↓ L4 Basal Ganglia GATE (inhibition-by-default; release or suppress)
     ↓ [released]
  ↓ L5 Hippocampus/Prefrontal (memory retrieval; planning)
  ↓ Trinity Dialectic (Logos vs Pathos; Ethos arbitrates)
     → Sonnet audit agent (Logos) checks Opus work (Pathos) against rules (Ethos)
  ↓ L6 Amygdala/Quorum (threat check; consensus gate)
  ↓ L7 Chromatophore (output adaptation)
  ↓ L8 DMN/Pathos (identity coherence check)
Output
  ↓ L5 write-back (findings → short_term.md)
  ↓ [at breakpoints] Trinity Consolidation (short→long→archival)
```

---

## 14. THE BRIDGE — PLUGGABLE BACKENDS (SpinalCord)

Source: IMPLEMENTATION_PLAN.md, WHITEPAPER.md §6

### Brain CORE (locked — MIT/Apache/BSD only)
- Trinity dialectic engine
- Memory consolidation protocol
- Brainstem hooks
- Agent dispatch framework

### Swappable Backends (3 protocols)
| Protocol | Interface | Current implementation | Planned replacement |
|---|---|---|---|
| KnowledgeBackend | `.search()` `.store()` `.retrieve()` | File-based (memory/*.md) | Chroma vector store (Phase 2) |
| AgentBackend | `.dispatch()` `.collect()` | Claude Code Agent tool | LangGraph (Phase 4) |
| NotifyBackend | `.send()` `.receive()` | File-based (handoffs/) | Event bus (Phase 4+) |

### LM-Agnostic Design
- Any LLM backend plugs in via SpinalCord
- Core never imports a specific LLM library
- Model routing handled at L4 (orchestrator selects Opus/Sonnet/Haiku per task)

### License Rule (IMPLEMENTATION_PLAN.md)
- Core and all deps: MIT/Apache/BSD only
- GPL-licensed code: isolated behind wrapper; never in core
- Every dependency cited in deps audit table

---

## 15. KEY DESIGN DECISIONS

Source: memory/decisions.md (26 entries, 2026-03-21 to 2026-03-25), memory/long_term.md

| Decision | Reasoning | Status | Confidence |
|---|---|---|---|
| 10 layers → 8 layers | Adversarial audit found redundancy; 8 maps cleanly to biology | Verified | 0.95 |
| Trinity = dialectic not pipeline | Fight IS the thinking; pipeline loses the disagreement | Verified | 0.99 |
| Inhibition-by-default at L4 | BG biology: suppress all, release specific; prevents runaway | Verified | 0.95 |
| Phase 2+ TABLED | Austin directive 2026-03-23; focus operational harness | Verified | 1.0 |
| No biological naming in operational | Prevents confusion between vision and deployed system | Verified | 1.0 |
| Memory: append-only, never delete | Frequency anti-pattern (Pattern 8); human pruning only | Verified | 0.9 |
| 2/2 quorum for knowledge promotion | Immune + domain = adversarial consensus; blocks contamination | Verified | 0.85 |
| Morphogen fitness: 0.4/0.4/0.2 | Balanced prediction+handoff; 0.2 dialectic (exploratory) | Verified | 0.8 |
| GPL isolation via wrapper | License contamination risk; MIT core must stay clean | Verified | 0.9 |
| OB1 (Nate B Jones): inspiration only | Different architecture; no code taken; no collaboration | Verified | 1.0 |
| 86 repos → ~11 actual deps | Scout research found most repos are wrappers; distilled | Verified | 0.9 |
| Allostatic gate default = WAIT | Biology: glucocorticoid anticipation; patience is adaptive | Verified | 0.85 |

---

## 16. IMPLEMENTATION STATUS

Source: IMPLEMENTATION_PLAN.md, memory/long_term.md, OPERATIONAL_LAYERS.md status column

| Component | Status |
|---|---|
| brainstem.md + brainstem_inject.sh (L4 hook) | OPERATIONAL |
| short_term.md → long_term.md consolidation (L5) | OPERATIONAL |
| Trinity dialectic (Pathos=Opus, Logos=Sonnet) | OPERATIONAL |
| OPEN_BRAIN.md queen pheromone | OPERATIONAL |
| Rule 00 (no public actions) | OPERATIONAL |
| NotebookLM MCP (23 notebooks) | OPERATIONAL (auth verified 2026-03-30) |
| Pheromone file system (L3) | PARTIALLY OPERATIONAL |
| Python CLI + 135 tests (Phase 1) | DONE (FROZEN) |
| Zero-trust hook chain (4 hooks) | VALIDATED 4/4 |
| Agent backends (8 cognitive agents) | FUNCTIONAL STUBS (concept layer) |
| NEAT evolution (morphogen) | SPECIFICATION ONLY |
| Blastema sandbox | SPECIFICATION ONLY |
| Allostatic gate | SPECIFICATION ONLY |
| LangGraph orchestrator (Phase 4) | TABLED |
| Chroma/FAISS RAG (Phase 2) | TABLED |
| Hebbian STDP weights | SPECIFICATION ONLY |
| L7 Chromatophore output | NOT STARTED |
| L2 Ganglion parallel workers | PYTHON STUB |

---

## 17. WHAT DOES NOT SELF-EVOLVE

Source: OPEN_BRAIN.md, trinity_mode_spec.md, memory/decisions.md

The following are FIXED and cannot be modified by any agent, sleep cycle, or NEAT evolution:

1. **Core identity** (OPEN_BRAIN.md) — the queen pheromone; never overwritten
2. **Trinity structure** — 3 voices, dialectic pattern, Ethos as shared ammunition
3. **Inhibition-by-default principle** — L4 always suppresses; never inverted
4. **Memory append-only rule** — long_term.md never loses entries; archival only
5. **License boundary** — MIT/Apache/BSD core; GPL isolation; never relaxed
6. **Rule 00** — no public actions without explicit approval; hardcoded
7. **2/2 quorum for knowledge promotion** — adversarial consensus; cannot be reduced to 1/2

Quote from OPEN_BRAIN.md: "Identity defined by affirmation not negation. The point is not storage. The point is incorporation."

---

## 18. FULL BIBLIOGRAPHY (from WHITEPAPER.md)

[1] Hochner, B. (2012). An Embodied View of Octopus Neurobiology. *Current Biology* 22(20).
[2] Zullo, L., & Hochner, B. (2011). A new perspective on the organization of an invertebrate brain. *Communicative & Integrative Biology* 4(1).
[3] Liscovitch-Brauer, N. et al. (2017). Trade-off between Transcriptome Plasticity and Genome Evolution in Cephalopods. *Cell* 169(2).
[4] Seeley, T.D. (2010). *Honeybee Democracy*. Princeton University Press.
[5] Dorigo, M., & Stützle, T. (2004). *Ant Colony Optimization*. MIT Press.
[6] Bonabeau, E., Dorigo, M., & Theraulaz, G. (1999). *Swarm Intelligence*. Oxford University Press.
[7] Srinivasan, M.V. (2010). Honey Bees as a Model for Vision, Perception, and Cognition. *Annual Review of Entomology* 55.
[8] Frankland, P.W., & Bontempi, B. (2005). The organization of recent and remote memories. *Nature Reviews Neuroscience* 6.
[9] Deisseroth, K. (2014). Circuit dynamics of adaptive and maladaptive behaviour. *Nature* 505.
[10] Redgrave, P. et al. (1999). The basal ganglia: a vertebrate solution to the selection problem? *Neuroscience* 89(4).
[11] Eliasmith, C. et al. (2012). A Large-Scale Model of the Functioning Brain. *Science* 338(6111). [SPAUN 2.0]
[12] Yuste, R., & Church, G.M. (2014). The new century of the brain. *Scientific American* 310(3).
[13] Hassabis, D. et al. (2017). Neuroscience-Inspired Artificial Intelligence. *Neuron* 95(2).
[14] Marcus, G. (2018). Deep Learning: A Critical Appraisal. *arXiv:1801.00631*.
[15] LeCun, Y., Bengio, Y., & Hinton, G. (2015). Deep learning. *Nature* 521.
[16] Schmidhuber, J. (2015). Deep learning in neural networks: An overview. *Neural Networks* 61.
[17] Bengio, Y. et al. (2013). Representation Learning: A Review and New Perspectives. *IEEE TPAMI* 35(8).
[18] Sutton, R.S., & Barto, A.G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
[19] Stanley, K.O., & Miikkulainen, R. (2002). Evolving Neural Networks through Augmenting Topologies. *Evolutionary Computation* 10(2). [NEAT]
[20] Aristotle. *Nicomachean Ethics*. (Trans. Ross, W.D., 1998). Oxford University Press. [Trinity dialectic source]
