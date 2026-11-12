# Research and Progression — Design Proposal

*For: Factorio Overhaul Mod (Project Prometheus)*  
*Status: Working design; six domains are the current roster. Core Level 2/3 gates, pack tiers, bridge mappings, technology assignments, and timing remain open.*
*Last updated: 2026-11-12*

Related documents: [Mod Overview](mod-overview.md) for cross-domain direction; [Endgame Vision](endgame-vision.md) for the planetary simulation network; [Infrastructure](infrastructure.md) for candidate machine families and placeable facilities.
Related ADRs: [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md) for first-Core prerequisites and [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) for Phase 3/4 power routes and converters.

## Summary

This document proposes how technology advancement could work across all phases of play — from conventional science packs in the early game through a transition to simulation-gated research. The guiding philosophy is **"knowledge before capability"**: the player should earn technologies by accumulating understanding, not just by checking boxes on supply-chain milestones.

**What it covers:** Three-phase progression (conventional → transitional domain science → full simulation research), when and where the transition from conventional to simulation-gated research happens, what domain science packs look like mechanically, which technologies require simulation results vs. conventional science, and how completing the planetary digital twin connects to the final victory condition.

**What it does not cover:** Specific recipe ratios for research items (covered in [Chemical Products and Processes](chemical-processes.md)); candidate facility construction and placeable infrastructure (covered in [Endgame Vision](endgame-vision.md) and [Infrastructure](infrastructure.md)). Exact product-to-machine assignments remain open.

## Core Design Philosophy: Knowledge Before Capability

From [Mod Overview](mod-overview.md): *"The player should feel less like a factory builder following longer recipe chains and more like an industrial engineer choosing and balancing processes."*

This applies to research too. Technology advancement should model **how real engineering progress happens**: you don't build a Tokamak-class fusion reactor because you've gathered enough steel — you need the physics knowledge first, then the materials capability, then the manufacturing precision. The simulation network exists because conventional industry *cannot reach certain thresholds without help from a higher entity.*

### Candidate Three-Phase Progression

The phase structure and duration estimates below are proposals, not an accepted schedule.

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
├── First-Core construction requirements are listed in Candidate Core Unlock Requirements below
└── Player learns: "I am an industrial engineer who chooses processes"

Transition Point: First compute capacity commissioned, first simulation model run
Phase 3 (Simulation-Gated)
├── Planetary/Industrial Model gates cleanrooms, advanced materials
├── Domain datasets from real facilities → Core runs models → findings unlock tech
├── Information-Based Model gates deep infrastructure and control tools
├── General-Physics Model supports late-game power research; Hawking is one accepted route, with its gate still open
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

### Candidate Domain Science Pack Design
Domain science packs are produced by **dedicated research buildings** (modeled after Space Exploration's domain labs), not by running industrial machinery. These buildings function mechanically identically to existing science pack factories — they process materials over time → output a science pack item — but the semantic layer ("measurements" or "results of experiments") is handled through naming and informatron descriptions, not additional game systems.

**Industrial products are prerequisites.** The current bridge set has six candidate products for the six-domain roster: electronic-grade polysilicon, Nb₃Sn wire, HfO₂ dielectric, D₂O, cryogenic argon/nitrogen, and high-performance rhenium-catalyst powder. The candidate facility associations are recorded in [Intermediate Products](intermediate-products.md). Additional inputs shown below may support construction or operation; their mapping is not a one-to-one recipe commitment. The player produces materials to construct and operate research facilities; the facilities generate domain packs as output. This separation means:
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

**Candidate facility-quality mechanic:** A research facility with better materials and operating conditions could produce more domain packs than a makeshift setup. This remains a proposal, not a required mechanic.

#### Candidate Domain Pack Tiers — Distinct Items per Tier (Not Alt Recipes)

The candidate domain-pack progression has a tier-count conflict: the current prose and progression table describe five and seven tiers, respectively. Item identities, tier count, and upgrade mechanics remain unresolved.

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

#### Candidate Core Unlock Requirements (Per Domain)

| Core Stage | Packs Required per Domain | Total Packs (~6 domains) | What It Unlocks |
|-----------|--------------------------|--------------------------|------------------|
| Core construction (first activation) | All 6 domains at T2b2 + **Unified Metrology Reference Array (convergence item)** → calibrated reference hardware mounted in Calibration Reference Frame | TBD; estimate requires reassessment for this gate | Thermal Frame + Computation Cluster installed; basic simulation model operational. Access to the Hawking route is a proposal; exact and alternative-route gates remain open. |
| **Core Level 2** | Gate TBD; must follow first-Core construction | TBD; no estimate assigned | Quantum-state enhancement module + memory expansion + Integration Bus upgrade for faster satellite communication; higher-fidelity models and accelerated discovery |
| **Core Level 3 / Final milestone** | All six domains at T3c | ~7,920+ packs over extended production (unvalidated estimate) | Multi-domain synthesis components fully integrated; Calibration Reference could model phenomena beyond known physics; general-physics discovery unlock |

> The Core itself is a hybrid technology — requires both conventional science packs (real materials to build) and domain datasets (operational evidence the network functions). **Unified Metrology Reference Array** bridges both by integrating six genuine scientific instruments measuring real physical quantities.

#### Breakthroughs Per Core Level (Phase 3 Capabilities)

Each Core level adds *new* research categories — different technology pools, not just "more of the same."

| Core Level | Breakthrough Category | Unlockable Tech Classes | Design Notes |
|---|---|---|---|
| **Level 1** (T2b2 minimum) | **Planetary + Industrial Model** — simulation can accurately model physical systems at planetary scale. Breakthrough: *predictive modeling of known physics.* | Cleanroom fabrication protocols, high-purity refining methods, semiconductor process chains, advanced materials science frameworks | First "we now have the data to go further" state. Simulation hasn't discovered new physics — it's proving it can reliably predict existing physics across all six domains. Gateway to Phase 3 research requiring cross-domain validation. |
| **Level 2** (gate TBD) | **Information-Based Civilization Model** — simulation can model populations of information-formed entities whose behavior *emerges* from structure, not programming. Breakthrough: *understanding how structured data produces perception and decision-making.* | Deep simulation infrastructure designs, advanced factory control frameworks (PLC expansion), emergent-system modeling tools, behavioral dataset collection methods | The "new physics" here is that the simulation itself has proven it can model entities that perceive, decide, and act — not simulated AI but mathematical beings whose behavior emerges from their information structure. Moves player from "modeling physics" to "modeling intelligence." |
| **Level 3** (T3c final milestone) | **General-Physics Model** — simulation has achieved sufficient fidelity that it can predict phenomena *beyond* known physics. Breakthrough: *access to cutting-edge theoretical knowledge the player's civilization cannot independently discover.* New physics frontiers unlocked. | Additional Phase 4 power-generation specifics (scope and gates still open), advanced quantum mechanics applications, exotic matter manipulation frameworks, general-physics research protocols | The **final milestone**. Simulation has validated itself against every known physics domain (Core L1), proven it can model emergent information structures (Core L2), and now reaches beyond — predicting phenomena that conventional science cannot reach. Unlocking "general-physics discovery" isn't a single recipe; it's *access* to research categories previously impossible. |

#### Domain Pack Recipes: Required Intermediate Products Per Tier

The **tip of the chain** for research purposes is small — ~30 intermediates across all six domains. Each tier requires distinct inputs, creating a progressive industrial investment path:

| Tier | Intermediates Needed | Examples |
|------|---------------------|----------|
| **T1 (6 items)** | Phase 1 products + basic bridge materials (~6–8 distinct intermediates); accessible from early Phase 2 | Refined metals (iron, copper, aluminum), basic acids, simple solvents |
| **T2a (6 items)** | T1 output + Phase 2 intermediates (~10–15 distinct intermediates) | Electronic-grade polysilicon, Nb₃Sn wire, HfO₂ dielectric, D₂O, cryogenic mixtures, noble-gas purification |
| **T2b1 (6 items)** | T2a output + one additional refined Phase 2 intermediate per domain (~8–10 distinct intermediates) | Domain-specific intermediate; specific material remains pending |
| **T2b2 (6 items)** | T2b1 output + high-purity cross-domain intermediate (~6–8 distinct intermediates); requires materials from *adjacent* domains | High-purity cross-domain intermediate |
| **T3a (6 items)** | T2b2 output + Core-produced infrastructure module (~3–5 distinct modules across all domains) | Modules from facilities built using Phase 2 products; activated after first Core construction |
| **T3b → T3c** | Prior-tier outputs plus convergence-level multi-domain materials | Additional high-purity inputs from adjacent domains |

Total estimated intermediates across all tiers: ~50–60 distinct items (including Phase 2 bridge materials). This is comparable to other overhaul mods' effective decision space — GTNH acknowledges the *effective* choice surface per player is ~40–50 categories, even if the theoretical roster is larger. The key constraint is **human cognitive capacity**: a player can only hold so many simultaneous processing decisions without fatigue. These 6 domains × 7 tiers with progressive revelation keep any given moment within that bound.

### Why Domain Packs at This Phase?
The transition zone is where the player has mastered conventional industry but hits the physics wall: they know *how* to run fission reactors but can't independently discover how to confine fusion plasma, synthesize cleanroom materials, or model advanced molecular processes. They need **domain-level understanding** — enough expertise in a field that simulation can build on it.

This is also where your existing Endgame Vision "Planetary and Industrial Model" stage begins. Domain packs are the evidence the player submits to say: "I understand this domain well enough to let the simulation extend my knowledge."

### When Phase 2 Ends
Phase 2 ends when the first-Core requirements in the Core Unlock Requirements table above are met; see [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md) for the recorded prerequisites.

Whether domain packs are also physical inputs to the Array, and what gate applies to Core Level 2, remain open.

**Duration estimate:** Phase 2 stretches ~180–200 hours within the 300+ hour ambition. The majority of this time comes from deep mineral → refinement → chemical chains needed for Phase 2 bridge materials, not from item count. Each domain pack tier traces back through multiple minerals and processing stages, generating hours through *depth per category*, not breadth all at once.

#### Candidate Six-Domain Equal-Depth Requirement

The proposal is for all six domains to reach approximately equal depth. Balance could come from intermediate count or logistics complexity, according to each domain's needs; the requirement and its implementation remain open.

#### Candidate Phase 2 Freeze Gate

One proposal is to stop adding Phase 2 intermediates after the catalog is defined, except to fill a verified capability, tradeoff, or progression gap. The ~50–60-item estimate is unvalidated and does not freeze the catalog.

#### Candidate Player Context

Target players are fluent vanilla Factorio players — vanilla is essentially the tutorial for this overhaul (similar to how Space Exploration players approach the game). The six-parallel-chain depth is a proven pattern; the iterative wave structure (Satisfactory/SE model) ensures no single moment requires tracking 90+ items simultaneously. Players iterate through tiers progressively, not all at once.

### Candidate Machine Tiering Through Material — Capability Gated by Build Materials

The draft, citing Bob's/Angel's as inspiration, proposes material-based machine tiers that unlock operations requiring higher temperatures, pressures, or precision rather than only increasing speed or reflecting ore quality. This five-tier example is not committed and must be reconciled with the candidate family/tier coverage in [Infrastructure](infrastructure.md).

**Candidate example: five tiers.** The exact number of tiers, materials, phases, and recipe eligibility remains open.

| Machine Tier | Build Materials | What It Enables | Phase Availability |
|------|----------------|-----------------|-------------------|
| **MTier 1** | Early-game metals + basic electronics | Basic recipes only (smelting, simple assembly) | Available from start — all Phase 1 players build these |
| **MTier 2** | Intermediate metals + improved electronics | Unlocks intermediate processing steps requiring higher precision or temperature control | Requires Phase 2 bridge materials (steel → processed intermediates). Unlocks during Wave 1–2 of Phase 2 |
| **MTier 3** | Advanced/corrosion-resistant alloys + advanced PCB | Unlocks chemical handling at scale, electrochemistry, high-temperature processes | Requires stainless steel processing + electronics chain. Available by Wave 2–3 of Phase 2; required to build the six domain labs |
| **MTier 4** | High-performance alloys (titanium, etc.) + semiconductor-grade components | Deep chemistry, nuclear fuel fabrication, wafer production — capabilities between MTier 3 and cleanroom grade | Requires deeper Phase 2 processing. Available by Wave 3–4 of Phase 2 |
| **MTier 5** | Ultra-pure/specialty alloys + semiconductor-grade components | Cleanroom-grade fabrication; Phase 3 Core infrastructure modules only | Requires materials from the deepest Phase 2/Phase 3 intermediate chains. Unlocks during Wave 4–5 or later |

The table describes a possible capability ladder, not specific build recipes or approved requirements. Its proposed material and machine gates must be reconciled with the intermediate-product tree and Infrastructure.

**Candidate progression impact:** A domain pack recipe could require a machine tier that does not exist yet. Under this proposal:
- The player must plan *which machines to build* alongside *what materials to produce* — both are parallel gating layers
- Building the right machine type is as important as having the right materials. A lower-tier assembler with high-purity input still can't produce a higher-tier pack because the machinery cannot maintain the required environment
- This reinforces the "capabilities over numbers" pillar: progressing means acquiring new capabilities, not just producing more of the same thing

**Cross-cutting impact on Phase 2:** The six domain labs themselves are MTier 3+ machines — they can't be built until the player has established steel → advanced alloy processing. Each lab's candidate bridge product and supporting inputs (see [Intermediate Products](intermediate-products.md)) reflect both material capability and machine-tier progression working together.

## Candidate Phase 3: Simulation-Gated Research (Late Game / Endgame)

### Mechanism
The proposed Endgame Vision loop is:
```
Domain datasets → Planetary Simulation Core schedules model runs 
→ results unlock selected technologies and next simulation stage
```

**Candidate behavior:** Conventional science packs may persist as an alternative path for late-game technologies that do not require new physics. The Core loop would handle new-physics capabilities; the technology split remains open.

### Which Technologies Require Simulation Results?

Candidate mapping based on the current Endgame Vision stages:

| Stage | Gate | Examples of technologies unlocked |
|---|---|---|
| **Planetary + Industrial Model** (first Phase 3 stage) | Planetary survey data + industrial process data from real production chains | Cleanroom fabrication, high-purity refining, basic semiconductor processes, advanced materials science |
| **Information-Based Civilization Model** | Planetary/industrial model results + behavioral datasets | Deep simulation infrastructure, advanced factory control tools |
| **General-Physics Model** (final extension) | Advanced physics experiments + extreme-energy facility data | Quantum mechanics applications, new physics frontiers |

### Phase 4 Power Options and the Planetary Simulation Core

The Phase 3/4 power-route identities and non-steam converter families are recorded in [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) and detailed in [Power System](power-system.md). Their unlock gates, relationship to Core progression, and whether each route is optional or required remain open. Late-game power should support the expanding computational network without assuming a specific Core dependency.

### How Many Technologies Gate on Simulation?

**Unvalidated planning estimate: ~60% simulation-gated, ~30% conventional-pack-only, ~10% hybrid.** The exact breakdown depends on the final technology roster; these percentages are not targets.

- **Some technologies remain conventional:** Things that real-world industry already solved (advanced combustion variants, alternative fuel production methods, standard metallurgy improvements) can be researched without simulation. This keeps a portion of late-game accessible and gives players who want to avoid the endgame network a path.
- **Most "capability unlock" gates are simulation-gated:** New machine families (cleanrooms, wafer fabrication), new process capabilities (deep electrolysis, high-pressure synthesis), and some Phase 4 power capabilities are proposed to require simulation findings. The Hawking route's current basic-Core gate and the gates for alternatives remain unresolved.
- **Candidate Core gate:** The Planetary Simulation Core could require both conventional science packs (for its construction materials) and domain datasets (as evidence that the network functions).

### Unvalidated Playtime Estimate: Simulation Construction Phase

An unvalidated planning estimate places simulation-network construction at about **1/3 of total game time** (~70–100 hours within the 300+ hour ambition).

| Segment | Hours | Activities |
|---------|-------|-----------|
| First Core construction | TBD; estimate requires reassessment for the selected gate | Balancing all six domains, building the convergence item, first Core infrastructure |
| Core Level 2 progression (gate TBD) | TBD; current estimate unvalidated | Deepening Phase 2 production, cross-domain calibration, higher-fidelity simulation tiers |
| Core Level 3 / final milestone (T3c packs) | ~15–35 | Expanded industrial base feeding Tier 3 domain pack production, convergence synthesis |

A proposal would make the Hawking route available during this construction phase, after a basic Planetary Simulation Core. Its role in powering network expansion, how it scales with the Core, and how alternatives fit this progression remain to be designed.

### Unvalidated Total Playtime Estimate

The draft estimates **~280–345 hours** across all phases, with Phase 2 time attributed to mineral → refining → chemical chain depth rather than item count. Neither the estimates nor the comparison to other mods has been validated. Each proposed intermediate is expected to trace through:
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

Total across all waves: **~280–345 hours** (unvalidated estimate; retain only as a planning hypothesis for the 300+ hour ambition).

### Logistical Complexity Across All Phases

The logistical patterns that stretch Phase 2 chains also apply game-wide. For a complete list of these design patterns (coproduct management, feedback loops, catalyst degradation, mismatched flow ratios, and more), see [logistics-system.md](logistics-system.md) "Engineering Complexity Patterns — Game-Wide Logistics Design."

How complexity scales across phases:

| Phase | Logistical Complexity Pattern (see reference doc for full details) | Research Impact |
|-------|----------------------|-----------------|
| Phase 1 (Conventional) | Simple chains, minimal coproducts | Basic science packs from straightforward input trees |
| Phase 2 (Domain Science) | Coproducts, feedback loops, mismatched ratios across domain pack chains | Domain pack intermediate recipes add routing complexity; each tier traces back through substantial input trees with deliberate logistical difficulty |
| Phase 3 (Simulation-Gated) | Multi-chain coordination, Core module dependencies, nested feedback loops | T3c Finalized Datasets require cross-domain convergence materials whose production chains now generate coproducts from every phase's processing infrastructure simultaneously |

This draft estimates **~280–345 hours** across the waves. The intended source of playtime is engineering depth (routing, production ratios, and waste management), not mineral breadth alone; both the duration and pacing require later validation.

### Dataset Production Mechanism

**Candidate mechanism:** Domain datasets could be produced as information items in buildings, using the familiar science-pack pattern and representing readings or experimental results. The distinction would be primarily semantic rather than mechanical.

> "Basically buildings that produce 'science packs', but the science packs are readings and results from experiments rather than just a set of complex-to-fabricate materials. It's really still the same, it's only semantics that make them feel different."

The source favors factory-produced dataset items routed to the Planetary Simulation Core, with their meaning conveyed through names and guidebook descriptions. This simpler approach is a proposal; more complex dataset mechanics have not been formally rejected.

### Conventional Science Retirement

**Candidate behavior:** Conventional packs would not vanish at a hard boundary; they could remain an alternative path for capabilities that do not require new physics. The exact late-game split remains open.

## Candidate Informatron/Guidebook Integration

From the Power System document — informatron pages explaining underlying physics apply across all research domains:

- **Fission entry:** Nuclear binding energy, mass defect → E=mc², chain reactions, enrichment necessity
- **Fusion entry:** Coulomb barrier, binding energy curve peak near iron-56, magnetic confinement principles, D-T reaction
- **Phase 4 (Hawking Engine):** Hawking radiation from QFT in curved spacetime; event horizons creating particle pairs where one escapes
- Each guidebook entry explains *what* happens at early depth and *why* at advanced depth — accessible to any player willing to read

The informatron pages are not just flavor text. They represent **accumulated theoretical understanding** that the simulation network synthesizes into actionable research findings. A player who engages with the deeper explanations gets better context for what each technology represents physically.

## Candidate Endgame Feedback Loop

The following concepts remain proposals and are not approved requirements.

### Core as Phase 3 Research Center
**Candidate:** The Planetary Simulation Core could become the Phase 3 research center, with domain packs submitted to it to advance the tech tree. This would shift from conventional research buildings in Phase 2 to the Core in Phase 3.

### Candidate Breakthrough Categories Per Core Level

One proposal is for each Core level to add a distinct research category rather than only increase existing capabilities:

| Core Stage | Packs Required per Domain | Total Packs (~6 domains) | What It Unlocks |
|-----------|--------------------------|--------------------------|------------------|
| **Core construction (first activation)** | See [Candidate Core Unlock Requirements (Per Domain)](#candidate-core-unlock-requirements-per-domain) | TBD | Basic simulation model; route-specific access gates remain open |
| **Core Level 2** | Gate TBD; must follow first-Core construction | TBD | Higher-fidelity models, accelerated discovery |
| **Core Level 3 / Final milestone** | All 6 domains at T3c | ~7,920+ packs total (spread over extended production) | General-physics discovery unlock |

Each tier unlocks tech that previous tiers cannot touch, gated by the domain pack tiers required for that Core level.

### Candidate Domain-Specific Tech Impact

Each domain could unlock different technologies and gameplay effects, making pre-simulation investment a strategic choice rather than interchangeable research fuel. The specific examples and domain-to-technology assignments remain unapproved.

### Candidate Endgame Tension Model

The draft proposes two sources of tension:

- **Scale:** Power demands, resource demands, and space requirements all explode as tiers progress. The player must constantly scale production capacity in every dimension simultaneously to meet the next tech's demands.
- **Complexity:** Manufacturing tree depth increases significantly — Phase 4 end is far more complex than Phase 3 start (similar to Satisfactory where each major milestone adds layers of processing depth, not just more belts and machines). The tension isn't "build a bigger factory" but "build a *deeper* and *more interconnected* factory while managing the complexity."

The draft argues that these pressures could provide sufficient engagement without a separate scarcity mechanic. This is a design hypothesis, not a resolved decision.

## Open Items (All Phase-Independent)

The items below remain open as the material pipeline and technology roster are developed. The estimates, gates, and examples above are not approved requirements.

### Internal Consistency Issues to Resolve

- The pack ladder prose says five tiers, while the named progression lists seven (T1 through T3c).
- This document's five-tier machine example must be reconciled with the candidate machine-family and tier counts in [Infrastructure](infrastructure.md).

| Item | Status | Blocks |
|------|--------|--------|
| **Exact technology roster** | Open — which techs gate on conventional vs domain packs vs simulation findings? | Finalizing domain pack recipes, simulating time budget accuracy |
| **First-Core prerequisites and bridge mapping** | Selected in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md); Core Level 2 gate, Array recipe, detailed bridge mapping, and pack-count estimates remain open | Core Level 2 progression, facility requirements, and power-route gates |
| **Pack tier count and facility count** | Open — five-tier prose conflicts with seven named tiers; confirm six facilities align with the finalized pack catalog | Pack catalog and endgame facility requirements |
| **Machine-tier model** | Open — the five-tier example is not aligned with Infrastructure's candidate family progression | Machine recipe eligibility and research gates |
| **Final victory condition specifics** | Open — is completing the planetary digital twin itself the win, or does it unlock further gameplay? | Endgame Vision alignment, Core L3 milestone definition |
| **Technology classification matrix (WIP)** | See table below — placeholder categories until mineral/chemical roster approved | All domain documents' tech tree planning |

### WIP: Technology Roster Matrix (Placeholder)

A technology may gate on multiple domain packs if it spans >1 physics domain. The exact roster will be finalized once the material pipeline is stable.

| Tech Name (placeholder) | Phase | Conventional Packs | Domain Pack(s) | Simulation Finding? | Notes |
|---|---|---|---|---|---|
| *— pending stabilization —* | Phase 1 | ✅ required | — | No | Baseline industrial tech |
| *e.g., enriched uranium fuel* | Phase 2 | ✅ + domain pack(s) | e.g., Superconductivity T2a + Isotope Separation T2b1 | No | Supplement conventional research building |
| *e.g., cleanroom fabrication* | Phase 3 | — | TBD (placeholder) | Yes, Core L1 | Requires simulation understanding |
| *e.g., tungsten armor tiles* | Phase 3 | — | e.g., Plasma Confinement T3a + Superconductivity T3a | Yes, Core L2 | Specific domain fidelity gate |
| *— core infrastructure techs —* | Phase 3 | Hybrid (varies) | Variable per tech | Yes, Core L1/L2/L3 | Final milestone chain gates on Core L3 synthesis reports |

### Candidate Technology Classification Rules

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
