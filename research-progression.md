# Research and Progression - Design Proposal

*For: Factorio Overhaul Mod (Project Prometheus)*  
*Status: Concept / requirements phase*

Related documents: [Mod Overview](mod-overview.md) for design philosophy; [Endgame Vision](endgame-vision.md) for the planetary simulation network; [Machine Systems](machine-systems.md) for capability milestones.

## Summary

This document defines how technology advancement works across all phases of play — from conventional science packs in the early game through a phased transition to simulation-gated research at the endgame boundary. The mod's core philosophy is **"knowledge before capability"**: the player should earn technologies by accumulating understanding, not just by checking boxes on supply-chain milestones.

**What it covers:** Three-phase progression (conventional → transitional domain science → full simulation research), when and where the transition from conventional to simulation-gated research happens, what domain science packs look like mechanically, which technologies require simulation results vs. conventional science, and how completing the planetary digital twin connects to the final victory condition.

**What it does not cover:** Specific recipe ratios for research item production (covered in [Chemical Products and Processes](chemical-processes.md)); facility construction requirements or infrastructure specs (covered in [Endgame Vision](endgame-vision.md) and [Machine Systems](machine-systems.md)).

## Core Design Philosophy: Knowledge Before Capability

From [Mod Overview](mod-overview.md): *"The player should feel less like a factory builder following longer recipe chains and more like an industrial engineer choosing and balancing processes."*

This applies to research too. Technology advancement should model **how real engineering progress happens**: you don't build a Tokamak-class fusion reactor because you've gathered enough steel — you need the physics knowledge first, then the materials capability, then the manufacturing precision. The simulation network exists because conventional industry *cannot reach certain thresholds without help from a higher entity.*

### The Three-Phase Progression

| Phase | Research Mechanism | Scope | Player identity |
|---|---|---|---|
| **Phase 1: Conventional** | Standard tech tree using science packs | First ~30–40 hours. Establishes baseline industrial capability, teaching mechanics and setting up the factory for transition | Factory builder following recipe chains |
| **Phase 2: Transitional (Domain Science)** | Hybrid system — conventional science packs continue but new *domain science packs* are introduced as additional gates; each domain has a five-tier pack progression that stretches Phase 2 through deep industrial investment | ~180–200 hours. The borders between phases stay intentionally vague rather than a hard gate at Fission → Fusion. As conventional industry hits the physics wall and simulation help becomes necessary, the player produces progressively deeper domain packs across all six domains — balanced investment is forced by the design | Industrial engineer choosing processes |
| **Phase 3: Simulation-Gated** | Full research loop — domain datasets → Planetary Simulation Core runs models → findings unlock technologies. Domain pack tiers T3a–T3c produced using Core infrastructure, scaling in requirement to maintain engagement | ~70–100 hours. The simulation network consumes increasingly advanced domain packs to reach higher fidelity states; player expands Phase 2 industrial base to feed the loop. Some conventional technology remains available as an alternative path for capabilities that don't require new physics | Industrial engineer who must *understand* the universe to manipulate it |

### Why This Shape?

The transition mirrors real scientific progress:
- **Conventional era:** We understood enough physics to build factories — Newtonian mechanics, basic thermodynamics, electrochemistry. Research was about discovering *how to make things better*, not about whether they were *physically possible*.
- **Transition zone:** The leading edge moves where conventional industry hits the wall of known physics — fusion requires plasma confinement physics we can't engineer from first principles without simulation; advanced materials require quantum mechanical understanding; deep chemistry requires molecular dynamics modeling. We *know* these things are physically possible but can't reach them through trial-and-error in a lab.
- **Simulation era:** The Planetary Simulation Core becomes the "higher entity" — an artificial scientific authority that lets us push beyond what factory-scale experimentation alone can achieve. This is exactly the role of computational physics, quantum field theory solvers, and molecular dynamics simulators in our world.

### Candidate Research/Progression Flow

Here is the full progression arc, from player identity to final milestone:

```text
Phase 1 (Conventional)
├── Conventional science packs unlock industrial foundations
├── Mining → refining → metallurgy → chemistry basics
├── Baseline power generation and factory automation
└── Player learns: "I am a factory builder"

Transition Point: Fission → Fusion boundary
Phase 2 (Domain Science)
├── Conventional + domain packs gate nuclear advancement
├── Six domain labs: Superconductivity, Plasma, Nanofabrication, Isotope Separation, Reaction Dynamics, Quantum States
├── Pack tiers per domain: T1 → T2a → T2b1 → T2b2 → each producing distinct research items
├── Phase 2 wall: all six domains at T2b2 required before Core construction (no shortcuts)
├── Convergence item (one pack from each of six domains) unlocks Planetary Simulation Core
└── Player learns: "I am an industrial engineer who chooses processes"

Transition Point: First compute capacity commissioned, first simulation model run
Phase 3 (Simulation-Gated)
├── Planetary/Industrial Model gates cleanrooms, advanced materials
├── Domain datasets from real facilities → Core runs models → findings unlock tech
├── Information-Based Model gates deep infrastructure and control tools
├── General-Physics Model gates Phase 4 (Hawking Radiation Engine)
└── Player learns: "I am an engineer who must understand the universe to manipulate it"

Final Milestone: Planetary Digital Twin Complete
└── Unlocks general-physics discovery. The player has demonstrated mastery of every industrial domain and proven that their simulation network can model reality accurately enough to push beyond known physics.
```

## Phase 1: Conventional Science (Early Game)

### Mechanism
Standard science pack tech tree — largely inspired by vanilla Factorio but re-skinned to fit the mod's industrial narrative. The exact roster of technologies unlocked by conventional packs remains open until the mineral/chemical rosters are stable.

### Design Notes
- This phase is intentionally brief. It exists to teach mechanics and establish baseline factory flow, not to be a long, drawn-out progression layer.
- Players learn about resource extraction, chemical processing, refining, and basic metallurgy through conventional research — these are all well-understood processes that real-world science already solved centuries ago. No simulation needed because we already know the answers.
- The handbook (mod overview) establishes **"Knowledge before capability"** here: every step's industrial journey is shown in the handbook *before* it can be built, teaching players what to expect.

### When Phase 1 Ends
Phase 1 transitions to Phase 2 when the player reaches the **Fission → Fusion boundary** — roughly when they have established nuclear fuel fabrication (enrichment/fuel conversion) and are considering whether to pursue fusion energy production. At this point, conventional industry has exhausted its ability to independently discover advanced physics.

## Phase 2: Transitional Domain Science (Mid-Game Bridge)

### Mechanism
Conventional science packs continue to function but domain science packs are introduced as *additional* requirements alongside conventional packs. Some technologies can be researched with conventional packs alone; others require both conventional + domain pack. The ratio shifts over time — earlier in Phase 2, conventional dominance is strong; later, domain packs become the primary gate.

**Where they go:** Domain packs are fed into the **conventional research building**, not to a simulation Core. At this stage there *is* no simulation Core. This follows the Space Exploration model: domain packs supplement and gate the existing vanilla tech tree through the standard research infrastructure. Each technology may require different combinations of conventional + domain packs, creating a hybrid gating system.

### Domain Science Packs: Design
Domain science packs are produced by **dedicated research buildings** (modeled after Space Exploration's domain labs), not by running industrial machinery. These buildings function mechanically identically to existing science pack factories — they process materials over time → output a science pack item — but the semantic layer ("measurements" or "results of experiments") is handled through naming and informatron descriptions, not additional game systems.

**Industrial products are prerequisites.** Each Phase 2 bridge product (electronic-grade polysilicon, Nb₃Sn wire, HfO₂ dielectric, D₂O, cryogenic argon/nitrogen) serves as the industrial prerequisite for building one specific domain research facility. The player produces the material to construct and power the research building; the building itself is what generates the domain pack as output. This separation means:
- **Phase 2 products = materials** (industrial outputs, factory engineering problems). They enable the *capability* to build and operate a research facility.
- **Research buildings = dedicated science pack generators** (like any other production line). They consume raw inputs over time and produce domain packs as output.

Key design points for each dedicated research facility:

| Facility | Produces | Phase 2 material prerequisite | Scientific field demonstrated |
|---|---|---|---|
| Superconductivity Research Lab | Domain data on superconductive states and critical currents | Electronic-grade polysilicon + Nb₃Sn wire | Condensed matter physics — zero-resistance current flow, magnetic confinement |
| Plasma Confinement Facility | Domain data on ionized gas behavior and field dynamics | Nb₃Sn wire + cryogenic infrastructure | Applied electromagnetism — high-field magnet operation, plasma stability |
| Nanofabrication Laboratory | Domain data on materials at atomic-scale dimensions | Hafnium-oxide (HfO₂) dielectric | Materials science — surface science, nanoscale behavior, quantum tunneling |
| Isotope Separation & Calibration Lab | Domain data on nuclear interactions and decay pathways | Deuterium-enriched water (D₂O) + enriched fuel stock | Particle physics — neutron interaction modeling, weak/strong force phenomena |
| Reaction Dynamics Facility | Domain data on reaction rates, catalysis, and equilibrium states | High-performance rhenium-catalyst powder (from molybdenite trace recovery) | Chemical kinetics — how reactions move, not just that they occur |
| Quantum States Laboratory | Domain data on atomic bonding, crystalline structures, and quantum states | High-purity cryogenic mixture + purified noble gases | Quantum mechanics — atomic structure, bond formation, phase transitions at low temperature |

**Production rate tied to facility quality.** A well-designed research facility with proper materials and operating conditions produces more domain packs than a makeshift setup — rewarding competent factory engineering without over-engineering the mechanic.

#### Domain Pack Tiers — Distinct Items per Tier (Not Alt Recipes)

Each domain produces its own **five-tier pack progression**. Each tier is a distinct item with its own recipe — you do not upgrade one item; you produce the next tier from scratch using previous-tier output as input. This makes every tier a *capability unlock*, not just a speed boost.

**Naming convention per domain:** `[Domain] [Tier Descriptor]` — e.g., *Superconductivity Observation Log*, *Superconductivity Analysis Dossier*, *Superconductivity Condition Survey*, *Superconductivity Cross-Reference Study*, *Superconductivity Simulation Record*. The tier descriptor is consistent across all domains for recognizability without sacrificing domain identity.

| Tier | Item Name Pattern (example: Superconductivity) | Input Source | What It Represents |
|------|---|---|---|
| **T1** | `Superconductivity Observation Log` | Phase 1 products + basic bridge materials | "I observe this phenomenon" — raw observational data from the lab |
| **T2a** | `Superconductivity Analysis Dossier` | T1 output + Phase 2 intermediates (electronic-grade polysilicon, Nb₃Sn wire) | "I've modeled it once" — first theoretical pass with material-specific calibration |
| **T2b1** | `Superconductivity Condition Survey` | T2a output + one additional refined Phase 2 intermediate | "I understand the primary boundary conditions" — mapping what conditions the phenomenon operates under |
| **T2b2** | `Superconductivity Cross-Reference Study` | T2b1 output + high-purity Phase 2 intermediates from adjacent domains | "I've cross-calibrated against related domains" — validating results across multiple domains |
| **T3a** | `Superconductivity Simulation Record` | T2b2 output + basic Core infrastructure module | "The simulation has extended my understanding" — the simulation network produces its own model of this domain |
| **T3b** | `Superconductivity Calibration Report` | T3a output + high-fidelity infrastructure item (Core-produced) | Simulation results checked against experimental benchmarks |
| **T3c** | `Superconductivity Synthesis Report` | T3b output + convergence-level materials spanning multiple domains | "Full multi-domain synthesis" — required for Core Level 3 / final milestone |

#### Core Unlock Requirements (Per Domain)

| Core Stage | Packs Required per Domain | Total Packs (~6 domains) | What It Unlocks |
|-----------|--------------------------|--------------------------|------------------|
| Core construction (first activation) | All 6 domains at T2a + **Unified Metrology Reference Array** → calibrated reference hardware mounted in Calibration Reference Frame | Thermal Frame + Computation Cluster installed; Phase 4 power access (Hawking engine), basic simulation model operational |
| **Core Level 2** | All six domains at T2b2 — ~1,320 packs total | Quantum-state enhancement module + memory expansion + Integration Bus upgrade for faster satellite communication | Higher-fidelity models, accelerated discovery |
| **Core Level 3 / Final milestone** | All six domains at T3c — ~7,920+ packs spread over extended production | Multi-domain synthesis components fully integrated; Calibration Reference can model phenomena beyond known physics | General-physics discovery unlock |

> The Core itself is a hybrid technology — requires both conventional science packs (real materials to build) and domain datasets (operational evidence the network functions). **Unified Metrology Reference Array** bridges both by integrating six genuine scientific instruments measuring real physical quantities.

> **Critical gate: Phase 2 must be completed in full (all six domains at T2b2) before any Core-related construction begins.** This forces balanced investment across all six physics domains — no shortcuts through specialization. The domain pack tiers are the progression bar for Phase 2; you know where you stand by asking "what's the highest tier I have on all six?"

#### Breakthroughs Per Core Level (Phase 3 Capabilities)

Each Core level adds *new* research categories — different technology pools, not just "more of the same."

| Core Level | Breakthrough Category | Unlockable Tech Classes | Design Notes |
|---|---|---|---|
| **Level 1** (T2a minimum) | **Planetary + Industrial Model** — simulation can accurately model physical systems at planetary scale. Breakthrough: *predictive modeling of known physics.* | Cleanroom fabrication protocols, high-purity refining methods, semiconductor process chains, advanced materials science frameworks | First "we now have the data to go further" state. Simulation hasn't discovered new physics — it's proving it can reliably predict existing physics across all six domains. Gateway to Phase 3 research requiring cross-domain validation. |
| **Level 2** (T2b2 minimum) | **Information-Based Civilization Model** — simulation can model populations of information-formed entities whose behavior *emerges* from structure, not programming. Breakthrough: *understanding how structured data produces perception and decision-making.* | Deep simulation infrastructure designs, advanced factory control frameworks (PLC expansion), emergent-system modeling tools, behavioral dataset collection methods | The "new physics" here is that the simulation itself has proven it can model entities that perceive, decide, and act — not simulated AI but mathematical beings whose behavior emerges from their information structure. Moves player from "modeling physics" to "modeling intelligence." |
| **Level 3** (T3c final milestone) | **General-Physics Model** — simulation has achieved sufficient fidelity that it can predict phenomena *beyond* known physics. Breakthrough: *access to cutting-edge theoretical knowledge the player's civilization cannot independently discover.* New physics frontiers unlocked. | Phase 4 power generation specifics, advanced quantum mechanics applications, exotic matter manipulation frameworks, general-physics research protocols | The **final milestone**. Simulation has validated itself against every known physics domain (Core L1), proven it can model emergent information structures (Core L2), and now reaches beyond — predicting phenomena that conventional science cannot reach. Unlocking "general-physics discovery" isn't a single recipe; it's *access* to research categories previously impossible. |

#### Domain Pack Recipes: Required Intermediate Products Per Tier

The **tip of the chain** for research purposes is small — ~30 intermediates across all six domains. Each tier requires distinct inputs, creating a progressive industrial investment path:

| Tier | Intermediates Needed | Examples |
|------|---------------------|----------|
| **T1 (6 items)** | Phase 1 products + basic bridge materials. ~6–8 distinct intermediates total: refined metals (iron, copper, aluminum), basic acids, simple solvents. Accessible from early Phase 2 |
| **T2a (6 items)** | T1 output + Phase 2 intermediates. ~10–15 distinct intermediates: electronic-grade polysilicon, Nb₃Sn wire, HfO₂ dielectric, D₂O, cryogenic mixtures, noble gas purification |
| **T2b1 (6 items)** | T2a output + one additional refined Phase 2 intermediate per domain. ~8–10 distinct intermediates total — domain-specific, not shared |
| **T2b2 (6 items)** | T2b1 output + high-purity cross-domain intermediate. ~6–8 distinct intermediates — requires materials from *adjacent* domains, forcing balanced production infrastructure |
| **T3a (6 items)** | T2b2 output + Core-produced infrastructure module. ~3–5 distinct modules across all domains, produced by facilities built using Phase 2 products but activated only after first Core construction |
| **T3b → T3c** | Progressively complex synthesis using prior tier outputs plus convergence-level multi-domain materials. Each requires additional high-purity inputs from adjacent domains |

Total estimated intermediates across all tiers: ~50–60 distinct items (including Phase 2 bridge materials). This is comparable to other overhaul mods' effective decision space — GTNH acknowledges the *effective* choice surface per player is ~40–50 categories, even if the theoretical roster is larger. The key constraint is **human cognitive capacity**: a player can only hold so many simultaneous processing decisions without fatigue. These 6 domains × 7 tiers with progressive revelation keep any given moment within that bound.

### Why Domain Packs at This Phase?
The transition zone is where the player has mastered conventional industry but hits the physics wall: they know *how* to run fission reactors but can't independently discover how to confine fusion plasma, synthesize cleanroom materials, or model advanced molecular processes. They need **domain-level understanding** — enough expertise in a field that simulation can build on it.

This is also where your existing Endgame Vision "Planetary and Industrial Model" stage begins. Domain packs are the evidence the player submits to say: "I understand this domain well enough to let the simulation extend my knowledge."

### When Phase 2 Ends
Phase 2 ends when the player has produced all six domain pack progression chains through T2b2 — a wall that forces balanced investment across every physics domain. The simulation network requires demonstrated breadth and depth across all six domains before accepting any Core-related construction.

This wall is deliberate, not punitive. It prevents cheating Phase 3 by specializing two domains (e.g., superconductivity + plasma) and neglecting the rest. To unlock the Planetary Simulation Core, every domain must have reached the same intermediate understanding level — the convergence item requires one T2a pack from *each* of the six domains.

**Duration estimate:** Phase 2 stretches ~180–200 hours within the 300+ hour ambition. The majority of this time comes from deep mineral → refinement → chemical chains needed for Phase 2 bridge materials, not from item count. Each domain pack tier traces back through multiple minerals and processing stages, generating hours through *depth per category*, not breadth all at once.

#### Six Domains — Equal Depth Requirement

All six physics domains must reach approximately equal depth. Balance is achieved either through the number of intermediates or the logistics complexity required for each domain — whichever is appropriate for that domain's natural complexity. This prevents artificial padding in low-complexity domains and ensures no single domain dominates the Phase 2 time budget.

#### Phase 2 Freeze Gate

Once Phase 2 intermediates are defined, stop adding new ones unless they solve an existing gap. The intermediate catalog is frozen; expansion only when an existing system has a hole (missing capability, missing tradeoff, missing horizon). Total intermediates across all tiers: ~50-60 distinct items.

#### Player Context

Target players are fluent vanilla Factorio players — vanilla is essentially the tutorial for this overhaul (similar to how Space Exploration players approach the game). The six-parallel-chain depth is a proven pattern; the iterative wave structure (Satisfactory/SE model) ensures no single moment requires tracking 90+ items simultaneously. Players iterate through tiers progressively, not all at once.

### Machine Tiering Through Material — Capability Gated by Build Materials

Machine tiering follows the Bob's/Angel model: each assembler/processing machine type has **multiple tiers** built from progressively better materials. Higher-tier machines don't just run faster — they unlock recipes that lower-tier machines physically cannot perform, because the machinery must withstand higher temperatures, pressures, or precision requirements. This is capability gating, not ore quality.

**Committed: 5 tiers.** Each tier maps to materials available from a specific phase, creating a reinforcing progression loop — later-phase production enables higher-tier machine construction which unlocks deeper processing:

| Machine Tier | Build Materials | What It Enables | Phase Availability |
|------|----------------|-----------------|-------------------|
| **MTier 1** | Early-game metals + basic electronics | Basic recipes only (smelting, simple assembly) | Available from start — all Phase 1 players build these |
| **MTier 2** | Intermediate metals + improved electronics | Unlocks intermediate processing steps requiring higher precision or temperature control | Requires Phase 2 bridge materials (steel → processed intermediates). Unlocks during Wave 1–2 of Phase 2 |
| **MTier 3** | Advanced/corrosion-resistant alloys + advanced PCB | Unlocks chemical handling at scale, electrochemistry, high-temperature processes | Requires stainless steel processing + electronics chain. Available by Wave 2–3 of Phase 2; required to build the six domain labs |
| **MTier 4** | High-performance alloys (titanium, etc.) + semiconductor-grade components | Deep chemistry, nuclear fuel fabrication, wafer production — capabilities between MTier 3 and cleanroom grade | Requires deeper Phase 2 processing. Available by Wave 3–4 of Phase 2 |
| **MTier 5** | Ultra-pure/specialty alloys + semiconductor-grade components | Cleanroom-grade fabrication; Phase 3 Core infrastructure modules only | Requires materials from the deepest Phase 2/Phase 3 intermediate chains. Unlocks during Wave 4–5 or later |

The exact materials for each tier will be determined by the intermediate-product tree — this table describes the capability ladder mapped to phases, not the specific build recipes. What matters is that progressing through tiers requires both material capability (you must produce/build with better alloys) and machine capability (the recipe must require a tier you don't yet have).

**Progression impact on research:** The same domain pack recipe may require a machine tier that doesn't exist yet. This means:
- The player must plan *which machines to build* alongside *what materials to produce* — both are parallel gating layers
- Building the right machine type is as important as having the right materials. A lower-tier assembler with high-purity input still can't produce a higher-tier pack because the machinery cannot maintain the required environment
- This reinforces the "capabilities over numbers" pillar: progressing means acquiring new capabilities, not just producing more of the same thing

**Cross-cutting impact on Phase 2:** The six domain labs themselves are MTier 3+ machines — they can't be built until the player has established steel → advanced alloy processing. Each lab's construction prerequisite (electronic-grade polysilicon, Nb₃Sn wire, HfO₂ dielectric) reflects both material capability and machine tier progression working together.

## Phase 3: Simulation-Gated Research (Late Game / Endgame)

### Mechanism
This is your existing Endgame Vision core loop:
```
Domain datasets → Planetary Simulation Core schedules model runs 
→ results unlock selected technologies and next simulation stage
```

**Conventional science packs don't fully retire.** They persist as an alternative path for late-game technologies that *don't require new physics* — things like alternative fuel production methods, standard metallurgy improvements, and other well-understood processes. The core simulation loop (datasets → Core runs models → findings unlock technologies) handles new physics capabilities.

### Which Technologies Require Simulation Results?

Based on the existing Endgame Vision stages:

| Stage | Gate | Examples of technologies unlocked |
|---|---|---|
| **Planetary + Industrial Model** (first Phase 3 stage) | Planetary survey data + industrial process data from real production chains | Cleanroom fabrication, high-purity refining, basic semiconductor processes, advanced materials science |
| **Information-Based Civilization Model** | Planetary/industrial model results + behavioral datasets | Deep simulation infrastructure, advanced factory control tools |
| **General-Physics Model** (final extension) | Advanced physics experiments + extreme-energy facility data | Quantum mechanics applications, new physics frontiers |

### Phase 4 Power and the Planetary Simulation Core

Phase 4 power production (Hawking Radiation Engine) is **not gated behind completing the simulation network.** Instead:

> **The player must build a basic Planetary Simulation Core to access Phase 4 power generation.** Phase 4 power grows *alongside* the scope and power requirements of the simulation core until it's ready to simulate an entire civilization.

This means Phase 4 power is available *during* the final third of gameplay, scaling with the Core as it expands. The Hawking Radiation Engine isn't the endgame victory condition — it's a late-game capability enabled by basic simulation infrastructure that provides enormous power during the simulation network construction phase.

By having Phase 4 power available *while* building the full simulation, the player gets access to extreme energy density exactly when they need it most: to power an expanding computational civilization. The Core starts small (basic physics model), but its needs grow — and Phase 4 scales alongside it, providing both the incentive to build the first Core and a massive power source for the ambitious infrastructure project ahead.

### How Many Technologies Gate on Simulation?

**Rough split: ~60% simulation-gated, ~30% conventional pack only, ~10% hybrid.** The exact breakdown depends on the final technology roster. Key design decisions:

- **Some technologies remain conventional:** Things that real-world industry already solved (advanced combustion variants, alternative fuel production methods, standard metallurgy improvements) can be researched without simulation. This keeps a portion of late-game accessible and gives players who want to avoid the endgame network a path.
- **Most "capability unlock" gates are simulation-gated:** New machine families (cleanrooms, wafer fabrication), new process capabilities (deep electrolysis, high-pressure synthesis), and Phase 4 power generation require simulation findings. These represent genuine knowledge gaps that no factory-scale experimentation can bridge.
- **The Planetary Simulation Core itself is a hybrid technology** — requires both conventional science packs (it needs real materials to build) and domain datasets (the network needs operational evidence to function).

### Playtime Contribution: Simulation Construction Phase

The simulation network construction occupies approximately **1/3 of total game time** (~70–100 hours within the 300+ hour ambition).

| Segment | Hours | Activities |
|---------|-------|-----------|
| First Core construction (T2a packs) | ~25 | Balancing all six domains, building convergence item, first Core infrastructure |
| Core Level 2 progression (T2b2 packs) | ~30–40 | Deepening Phase 2 production, cross-domain calibration, higher-fidelity simulation tiers |
| Core Level 3 / final milestone (T3c packs) | ~15–35 | Expanded industrial base feeding Tier 3 domain pack production, convergence synthesis |

Phase 4 power generation (Hawking Radiation Engine) is available *during* this construction phase — enabled by a basic Planetary Simulation Core. The player uses Phase 4 power to fuel the massive energy demands of expanding the simulation network. As the Core grows from basic physics model → planetary industrial model → information-formed civilization, its power requirements increase, and Phase 4 scales alongside it.

### Time Validation Against Design Scope

The phased time estimate is realistic because **Phase 2's duration comes from mineral → refinement → chemical chain depth**, not item count. The estimated ~50–60 intermediates across all tiers sounds small compared to GTNH's thousands, but each intermediate traces back through:
- Mining deposit (one of ~15–20 deposit types depending on mineral class)
- Refinement route (surface → underground → polymineral processing stages)
- Chemical processing chain (multiple reactions with coproduct handling)
- Phase 2 bridge material synthesis
- Domain pack tier progression

GTNH's hours come from depth of tracing, not breadth of simultaneous decisions. Our approach achieves the same goal through **progressive revelation** instead: materials and chemical chains are introduced iteratively throughout Phase 2, not all at once.

| Wave | Approx. Hours In | New Materials Introduced |
|------|------------------|-------------------------|
| Wave 1 (Phase 2 early) | ~30–40h | First 3 domains' T1 → T2a path; ~8–10 mineral types, ~15 refinements |
| Wave 2 (Phase 2 mid) | ~60–70h | Remaining 3 domains' T1 → T2a + first wave of T2b1 for early domains |
| Wave 3 (Phase 2 late) | ~60–70h | T2b2 chains requiring cross-domain materials; convergence item construction |
| Wave 4 (Phase 3 early/Core L1→L2) | ~30–40h | Core infrastructure modules (T3a), first iteration of simulation feeding |
| Wave 5 (Phase 3 mid/Core L2→L3) | ~15–35h | T3b/T3c production, convergence-level multi-domain synthesis |

Total across all waves: **~280–345 hours** — consistent with the 300+ hour ambition when accounting for player exploration speed, iteration time, and industrial engineering complexity.

### Logistical Complexity Across All Phases

The logistical patterns that stretch Phase 2 chains also apply game-wide. For a complete list of these design patterns (coproduct management, feedback loops, catalyst degradation, mismatched flow ratios, and more), see [logistics-system.md](logistics-system.md) "Engineering Complexity Patterns — Game-Wide Logistics Design."

How complexity scales across phases:

| Phase | Logistical Complexity Pattern (see reference doc for full details) | Research Impact |
|-------|----------------------|-----------------|
| Phase 1 (Conventional) | Simple chains, minimal coproducts | Basic science packs from straightforward input trees |
| Phase 2 (Domain Science) | Coproducts, feedback loops, mismatched ratios across domain pack chains | Domain pack intermediate recipes add routing complexity; each tier traces back through substantial input trees with deliberate logistical difficulty |
| Phase 3 (Simulation-Gated) | Multi-chain coordination, Core module dependencies, nested feedback loops | T3c Finalized Datasets require cross-domain convergence materials whose production chains now generate coproducts from every phase's processing infrastructure simultaneously |

Total across all waves: **~280–345 hours**. Playtime generated by engineering depth (solving routing problems, balancing production ratios, managing waste) rather than just mineral breadth (counting how many ores exist).

### Dataset Production Mechanism

Dataset (or "science pack") production uses buildings that produce information items — functionally identical to existing science packs but thematically representing readings and experimental results. **Keep it simple.** The mechanic is the same: facility processes materials over time → outputs item. The distinction is purely semantic, not mechanical.

> "Basically buildings that produce 'science packs', but the science packs are readings and results from experiments rather than just a set of complex-to-fabricate materials. It's really still the same, it's only semantics that make them feel different."

The existing Endgame Vision proposals for overly complex dataset mechanics were overthinking it. Each domain dataset functions exactly like an existing science pack: produced by factories, routed to the Planetary Simulation Core as a research input. The thematic layer ("these are readings," not "these are manufactured goods") is handled through naming and informatron descriptions — **not** through additional game systems.

### Conventional Science Retirement

Conventional packs don't vanish at a hard boundary. They persist as an alternative path for capabilities that *don't require new physics* — things like alternative fuel production methods, standard metallurgy improvements, and other well-understood processes. This preserves some conventional tech access in late game without undermining the simulation's role.

## Informatron/Guidebook Integration

From the Power System document — informatron pages explaining underlying physics apply across all research domains:

- **Fission entry:** Nuclear binding energy, mass defect → E=mc², chain reactions, enrichment necessity
- **Fusion entry:** Coulomb barrier, binding energy curve peak near iron-56, magnetic confinement principles, D-T reaction
- **Phase 4 (Hawking Engine):** Hawking radiation from QFT in curved spacetime; event horizons creating particle pairs where one escapes
- Each guidebook entry explains *what* happens at early depth and *why* at advanced depth — accessible to any player willing to read

The informatron pages are not just flavor text. They represent **accumulated theoretical understanding** that the simulation network synthesizes into actionable research findings. A player who engages with the deeper explanations gets better context for what each technology represents physically.

## Endgame Feedback Loop — Design Resolutions

These resolutions were discussed and finalized during active design work. They are committed decisions, not open questions.

### Core as Phase 3 Research Center
**Simulation Output:** The Planetary Simulation Core becomes the Phase 3 research center. Players upload domain packs into the Core itself, and the Core advances the tech tree at that stage. This is a mechanical shift: Phase 2 uses conventional research buildings; Phase 3 uses the Core as the research facility.

### Breakthrough Categories Per Core Level

Each Core level adds *new* research categories to the tree — different technology pools, not just "more of the same." The progression is:

| Core Stage | Packs Required per Domain | Total Packs (~6 domains) | What It Unlocks |
|-----------|--------------------------|--------------------------|------------------|
| **Core construction (first activation)** | All 6 domains at T2a minimum + convergence item | ~6 × 7 = ~42 packs (plus convergence item) | Phase 4 power access (Hawking engine), basic simulation model |
| **Core Level 2** | All 6 domains at T2b2 | ~1,320 packs total | Higher-fidelity models, accelerated discovery |
| **Core Level 3 / Final milestone** | All 6 domains at T3c | ~7,920+ packs total (spread over extended production) | General-physics discovery unlock |

Each tier unlocks tech that previous tiers cannot touch, gated by the domain pack tiers required for that Core level.

### Domain-Specific Tech Impact

**Pre-Simulation Investment:** Each of the six domains unlocks *different* technologies with *different* gameplay impacts — not interchangeable fuel. Players strategically prioritize domains based on desired edge: materials science → better military options, particle physics → better power generation, superconductivity → advanced factory infrastructure, etc. Domain investment is a meaningful strategic choice, not just "produce everything."

### Endgame Tension Model

Tension comes from two dimensions, not artificial constraints:

- **Scale:** Power demands, resource demands, and space requirements all explode as tiers progress. The player must constantly scale production capacity in every dimension simultaneously to meet the next tech's demands.
- **Complexity:** Manufacturing tree depth increases significantly — Phase 4 end is far more complex than Phase 3 start (similar to Satisfactory where each major milestone adds layers of processing depth, not just more belts and machines). The tension isn't "build a bigger factory" but "build a *deeper* and *more interconnected* factory while managing the complexity."

No separate scarcity mechanic is needed — the implicit pressure of scaling production capacity and complexity across all dimensions simultaneously is sufficient to maintain engagement for 70–100 hours.

## Open Items (All Phase-Independent)

These decisions block further detail work across all domains. **Pending: mineral, chemical, and intermediate-product stabilization.** Once the material pipeline is locked, all items below can be finalized.

| Item | Status | Blocks |
|------|--------|--------|
| **Exact technology roster** | Open — which techs gate on conventional vs domain packs vs simulation findings? | Finalizing domain pack recipes, simulating time budget accuracy |
| **Final victory condition specifics** | Open — is completing the planetary digital twin itself the win, or does it unlock further gameplay? | Endgame Vision alignment, Core L3 milestone definition |
| **Technology classification matrix (WIP)** | See table below — placeholder categories until mineral/chemical roster approved | All domain documents' tech tree planning |

### WIP: Technology Roster Matrix (Placeholder)

A technology may gate on multiple domain packs if it spans >1 physics domain. The exact roster will be finalized once the material pipeline is stable.

| Tech Name (placeholder) | Phase | Conventional Packs | Domain Pack(s) | Simulation Finding? | Notes |
|---|---|---|---|---|---|
| *— pending stabilization —* | Phase 1 | ✅ required | — | No | Baseline industrial tech |
| *e.g., enriched uranium fuel* | Phase 2 | ✅ + domain pack(s) | e.g., Superconductivity T2a + Isotope Separation T2b1 | No | Supplement conventional research building |
| *e.g., cleanroom fabrication* | Phase 3 | — | All six domains at T2b2+ | Yes, Core L1 | Requires simulation understanding |
| *e.g., tungsten armor tiles* | Phase 3 | — | e.g., Plasma Confinement T3a + Superconductivity T3a | Yes, Core L2 | Specific domain fidelity gate |
| *— core infrastructure techs —* | Phase 3 | Hybrid (varies) | Variable per tech | Yes, Core L1/L2/L3 | Final milestone chain gates on Core L3 synthesis reports |

### Technology Classification Rules

| Gate Type | Meaning | Phase |
|-----------|---------|-------|
| `conventional only` | Real-world science already solved — no new physics needed | Phase 1 / Phase 2 bridge |
| `conventional + domain pack(s)` | Requires specific physics knowledge from one or more domains | Phase 2 |
| `simulation finding` | Cannot be discovered without a computational model | Phase 3 |

### Endgame Vision Dependencies

These decisions in [Endgame Vision](endgame-vision.md) block or gate on the work tracked above:

| Dependency | Status | Blocks |
|-----------|--------|--------|
| Simulation fidelity tiers (basic → accurate → predictive model) | Open | Core requirement definitions, technology unlock gates |
| Final milestone structure (single vs. staged) | Open | Core L3 requirements, victory condition specifics |
| Compute distribution requirements | Open | Phase 3 infrastructure planning, power scaling |
| Power/cooling/network constraints for Core | Open | Facility design specs, phase 4 power integration |
