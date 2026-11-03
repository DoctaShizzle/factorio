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
| **Phase 1: Conventional** | Standard tech tree using science packs | First ~40–50% of the game. Establishes baseline industrial capability, teaching mechanics and setting up the factory for transition | Factory builder following recipe chains |
| **Phase 2: Transitional (Domain Science)** | Hybrid system — conventional science packs continue but new *domain science packs* are introduced as additional gates | ~40–50% through the game. The borders between phases stay intentionally vague rather than a hard gate at Fission → Fusion. As conventional industry hits the physics wall and simulation help becomes necessary | Industrial engineer choosing processes |
| **Phase 3: Simulation-Gated** | Full research loop — domain datasets → Planetary Simulation Core runs models → findings unlock technologies | Final third (~100 hours). Domain packs are produced by science-pack-style buildings. Some conventional technology remains available as an alternative path for capabilities that don't require new physics | Industrial engineer who must *understand* the universe to manipulate it |

### Why This Shape?

The transition mirrors real scientific progress:
- **Conventional era:** We understood enough physics to build factories — Newtonian mechanics, basic thermodynamics, electrochemistry. Research was about discovering *how to make things better*, not about whether they were *physically possible*.
- **Transition zone:** The leading edge moves where conventional industry hits the wall of known physics — fusion requires plasma confinement physics we can't engineer from first principles without simulation; advanced materials require quantum mechanical understanding; deep chemistry requires molecular dynamics modeling. We *know* these things are physically possible but can't reach them through trial-and-error in a lab.
- **Simulation era:** The Planetary Simulation Core becomes the "higher entity" — an artificial scientific authority that lets us push beyond what factory-scale experimentation alone can achieve. This is exactly the role of computational physics, quantum field theory solvers, and molecular dynamics simulators in our world.

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

### Domain Science Packs: Design
Domain science packs are produced by operating specific facilities and capturing readings/experimental data. They represent **accumulated understanding** of a physical domain, not just "items from a machine." Key design points:

| Aspect | Design Approach |
|---|---|
| **Source** | Meaningful facilities already built for production (not dedicated research machines) |
| **Mechanic** | Facility operates at specific conditions → captures data over time → outputs a domain science pack representing accumulated understanding |
| **Examples** | *Nuclear Physics Readings* from operating fission reactors; *Plasma Physics Readings* from experimental fusion chambers; *Materials Science Data* from cleanroom analysis facilities; *Thermodynamics Measurements* from high-throughput chemical processing |
| **Production rate** | Tied to facility operation quality — a well-run reactor produces more/better readings than one that's barely functional. This rewards competent factory engineering. |

### Why Domain Packs at This Phase?
The transition zone is where the player has mastered conventional industry but hits the physics wall: they know *how* to run fission reactors but can't independently discover how to confine fusion plasma, synthesize cleanroom materials, or model advanced molecular processes. They need **domain-level understanding** — enough expertise in a field that simulation can build on it.

This is also where your existing Endgame Vision "Planetary and Industrial Model" stage begins. Domain packs are the evidence the player submits to say: "I understand this domain well enough to let the simulation extend my knowledge."

### When Phase 2 Ends
Phase 2 ends when the player commissions their **first regional compute capacity** and connects it to a research facility, enabling their first full simulation model run. This is roughly when they've built enough industrial diversity to produce all required domain datasets and have established the infrastructure for Phase 3.

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
| **Agent-based Civilization Model** | Planetary/industrial model results + behavioral datasets | Deep simulation infrastructure, PLC optimization systems, advanced factory control |
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

**Resolved:** The simulation network construction occupies approximately **1/3 of total game time** (~100 hours within the 300+ hour ambition). This is the final third of gameplay, bridging from fusion power through building the full distributed computational civilization.

Phase 4 power generation (Hawking Radiation Engine) is available *during* this construction phase — enabled by a basic Planetary Simulation Core. The player uses Phase 4 power to fuel the massive energy demands of expanding the simulation network. As the Core grows from basic physics model → planetary industrial model → agent-based civilization, its power requirements increase, and Phase 4 scales alongside it.

### The Final Victory Condition

What does completing the planetary digital twin accomplish? This remains open, but the leading candidate:

> **Completing the planetary digital twin unlocks general-physics discovery.** By demonstrating mastery of every industrial domain and proving that your simulation network can model the planet accurately enough, you earn the right to push beyond known physics. The final capability is access to cutting-edge theoretical knowledge — extending what's possible even further.

Dataset (or "science pack") production uses buildings that produce information items — functionally identical to existing science packs but thematically representing readings and experimental results. **Keep it simple.** The mechanic is the same: facility processes materials over time → outputs item. The distinction is purely semantic, not mechanical.

> "Basically buildings that produce 'science packs', but the science packs are readings and results from experiments rather than just a set of complex-to-fabricate materials. It's really still the same, it's only semantics that make them feel different."

The existing Endgame Vision proposals for overly complex dataset mechanics were overthinking it. Each domain dataset functions exactly like an existing science pack: produced by factories, routed to the Planetary Simulation Core as a research input. The thematic layer ("these are readings," not "these are manufactured goods") is handled through naming and informatron descriptions — **not** through additional game systems.

### Conventional Science Retirement

Conventional packs don't vanish at a hard boundary. They persist as an alternative path for capabilities that *don't require new physics* — things like alternative fuel production methods, standard metallurgy improvements, and other well-understood processes. This preserves some conventional tech access in late game without undermining the simulation's role.

## Candidate Research/Progression Flow

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
├── First experimental fusion chamber → Plasma Physics Readings
├── Deep chemistry → Materials Science Data
└── Player learns: "I am an industrial engineer who chooses processes"

Transition Point: First compute capacity commissioned, first simulation model run
Phase 3 (Simulation-Gated)
├── Planetary/Industrial Model gates cleanrooms, advanced materials
├── Domain datasets from real facilities → Core runs models → findings unlock tech
├── Agent-based Model gates deep infrastructure and PLC capabilities
├── General-Physics Model gates Phase 4 (Hawking Radiation Engine)
└── Player learns: "I am an engineer who must understand the universe to manipulate it"

Final Milestone: Planetary Digital Twin Complete
└── Unlocks general-physics discovery. The player has demonstrated mastery of every industrial domain and proven that their simulation network can model reality accurately enough to push beyond known physics.
```

## Informatron/Guidebook Integration

From the Power System document — informatron pages explaining underlying physics apply across all research domains:

- **Fission entry:** Nuclear binding energy, mass defect → E=mc², chain reactions, enrichment necessity
- **Fusion entry:** Coulomb barrier, binding energy curve peak near iron-56, magnetic confinement principles, D-T reaction
- **Phase 4 (Hawking Engine):** Hawking radiation from QFT in curved spacetime; event horizons creating particle pairs where one escapes
- Each guidebook entry explains *what* happens at early depth and *why* at advanced depth — accessible to any player willing to read

The informatron pages are not just flavor text. They represent **accumulated theoretical understanding** that the simulation network synthesizes into actionable research findings. A player who engages with the deeper explanations gets better context for what each technology represents physically.

## Resolved Design Decisions

| Decision | Resolution | Notes |
|---|---|---|
| Dataset production mechanic | **Science-pack-style buildings.** Functionally identical to existing science packs — factory processes materials over time → outputs item. The thematic layer ("these are readings") is handled through naming and informatron descriptions, not additional game systems. | Per discussion: "It's really still the same, it's only semantics that make them feel different." Avoided over-engineering dataset mechanics into a separate system. |
| Playtime contribution | **1/3 of total game time (~100 hours)** for simulation network construction within the 300+ hour ambition. This is the final third of gameplay, bridging from fusion power through building the full distributed computational civilization. | |
| Phase 4 power timing | **Available DURING simulation construction,** gated only by a basic Planetary Simulation Core build. Power grows alongside the simulation core's scope until it simulates a civilization. Phase 4 is not the endgame victory condition — it's a late-game capability enabled by basic simulation infrastructure. | Provides massive energy exactly when needed to power the expanding computational civilization. Scales with Core growth. |

## Open Design Decisions

- **Exact technology roster:** Which technologies gate on conventional science, which on domain packs, and which require simulation results? This can only be finalized once the mineral, chemical, and intermediate-product candidates are approved — the tech tree depends on having a stable industrial roster to reference.
- **Simulation fidelity tiers:** Does the Planetary Simulation Core have upgradeable fidelity levels (basic model → accurate model → predictive model)? If so, what upgrades are required, and how does fidelity affect research outcomes?
- **Conventional science retirement timing:** Does conventional packs phase out entirely at Phase 3, or do they persist as an alternative (slower, less complete) path to some technologies?
- **Hybrid research paths:** Can a player choose to invest in simulation infrastructure early and bypass much of the conventional tech tree? Or must every player progress through all three phases in sequence?
- **Final victory condition specifics:** Is completing the planetary digital twin *itself* the win condition? Or does it unlock further gameplay (new physics discoveries, space expansion)? What exactly "completes" — building all facilities to a certain capacity, achieving a fidelity threshold, or running a specific final model?
