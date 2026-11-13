# Endgame Vision — Distributed Planetary Computing

*For: Project Prometheus Factorio Overhaul*  
*Status: Draft — the planetary simulation network is the endgame direction; the first Core construction gate is accepted in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md), while higher Core stages, facilities, and the final milestone remain proposals.*
*Last updated: 2026-11-13*

Related documents: [Mod Overview](mod-overview.md), [Intermediate Products](intermediate-products.md), [Infrastructure](infrastructure.md), [Power System](power-system.md), and [Research and Progression](research-progression.md) for simulation-gated research mechanics.
Related ADRs: [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md), [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md), [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0020](adrs/ADR-0020-seven-distinct-domain-pack-tiers.md), [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md), [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md), [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md), and [ADR-0037](adrs/ADR-0037-defer-array-neutron-reference-material.md) for the deferred neutron-reference material selection and pre-Core constraints.

## Summary

This document describes the proposed endgame direction: building a planetary digital twin through a distributed computational civilization. A Planetary Simulation Core could coordinate model runs across specialized facilities, while wafer and processor fabrication would serve as prerequisite chains rather than endgame facilities themselves.

**What it covers:** The core hook ("planetary digital twin of thinking entities"), recognizable structure (Core + memory archives + regional compute campuses + research/observation facilities), candidate simulation research loop (datasets → Core schedules runs → model results unlock research), and open design decisions about dataset families, simulation-research gate ratios, and the final victory condition.

**What it does not cover:** Research progression mechanics — including how conventional science transitions to simulation-gated research, domain science pack design, and technology gating rules. These are defined in [Research and Progression](research-progression.md). Semiconductor fabrication mechanics or specific recipe pathways — those are tracked in [Intermediate Products](intermediate-products.md). Infrastructure requirements like power consumption are outlined here but detailed in [Power System](power-system.md).

## North Star

The current north star is: **build a planetary digital twin through a computational civilization.** The simulation is intended to model physical systems and populations of information-based entities — beings composed of structured data, not artificial intelligence. These entities would perceive their environment, make decisions, and interact with modeled systems through emergent structure and dynamics; the premise is not an AI character housed inside a building.

The planetary digital twin is the clear, concrete promise. Modeling broader physical laws or a virtual cosmos can be a final extension of that work, but should not replace the planetary-scale hook or imply literal simulation of every particle in the universe.

The proposed computational capacity is distributed across specialized facilities spread over the map, each dependent on the industrial ecosystem built earlier. The intent is for this network to culminate mining, refining, metallurgy, chemistry, power, electronics, logistics, and factory control.

## Candidate Production Prerequisites and Facility Network

```text
Semiconductor and specialty-material supply chains
        -> wafer / processor production (prerequisite chains)
        -> regional compute campuses + memory archives
        -> research / observation facilities supplying domain datasets
        -> Planetary Simulation Core coordinating distributed model runs
        -> simulation findings that enable further research
```

Wafer and processor fabrication are means to build the computational civilization; they are not themselves the endgame facility chain. The physical endgame is a Core connected to distributed compute, memory, and research/data facilities. Facilities may be distributed, duplicated, or connected by logistics and power infrastructure according to the final design.

## Recognizable Structure and Peripheral Network

### Candidate Planetary Simulation Core

The Core is proposed as a **modular orchestration hub** — not a megastructure or AI persona. It would sit at the center of a distributed network, receive domain datasets from six facility types, coordinate model runs across compute campuses, and output findings that unlock Phase 3 technologies.

**Candidate Core Structure Components:**

Conventional CPU-grade packaged processors are available by late Phase 2 and supply the initial Computation Cluster under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md). The standard CPU path for initial Core supply requires the selected Phase 2 material stack and mineral feed families under [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md) and [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md); detailed production routes remain open. The Josephson/SFQ superconducting compute array is a later post-activation upgrade; its exact Core level and production path remain open. The first-Core Calibration Reference Frame uses a Phase 2-compatible non-semiconductor precision alignment mechanism under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md).

| Component | Required Inputs | Physical Meaning |
|-----------|----------------|------------------|
| **Thermal Frame Assembly** | Heat exchanger coils, cryogenic insulation panels, thermal interface materials, refrigeration cascade components (liquid N₂/Ar circuits), corrosion-resistant structural steel framework | Mandatory first Core assembly — cascading thermal loop infrastructure that removes computation heat and stabilizes measurement temperatures across all subsystems. Without this, no precision operation is possible. |
| **Computation Cluster** | Conventional CPU-grade packaged processors, ultra-pure copper bonding wire, advanced thermal interface materials, shielded memory enclosures | Initial physical computational center: silicon processor modules with dedicated cooling channels, memory arrays in electromagnetic-shielded enclosures, and synchronization hardware. A later Josephson/SFQ array may upgrade its compute capability. |
| **Integration Bus** | Superconducting interconnect cable (Nb₃Sn/NbTi), photolithography-processed glass optical waveguides, EM shielding material (mu-metal/permalloy alloy), fiber routing hardware with precision mechanical mounts | Physical interconnect infrastructure — cables, waveguides, and isolation enclosures connecting satellite nodes to the Core. Upgradeable across tiers: early cores have basic connections; higher tiers require faster/more reliable Phase 2 materials. |
| **Calibration Reference Frame** | Unified Metrology Reference Array + Phase 2-compatible non-semiconductor precision alignment mechanism, vibration isolation system, environmental control components tied to thermal infrastructure | Where the convergence array is mounted and *actively functions* — not just a piece that "unlocks" something. Active temperature/vibration control makes it genuine calibration hardware. |
| **Unified Metrology Reference Array** | Nb₃Sn wire + electronic-grade polysilicon; D₂O + neutron-reference materials (specific inputs open); rhenium-catalyst powder + graphite support; cryogenic Ar/N₂ mixture → single precision-instrument enclosure mounted in Calibration Reference Frame | Active calibration hardware: coherent instrument integrating six physics measurement zones into one physical device. Each zone is genuine scientific hardware — not administrative proof but real instrumentation that produces measurable reference data while the Core operates. Cross-domain calibration between zones enables multi-physics validation. The "convergence" is the physical co-location of these six zones, allowing each to calibrate the others in real time: the neutron standard calibrates the superconducting sensor; the cryogenic bath validates thermal models. Enriched fission fuel is not a first-Core prerequisite under ADR-0022. |

The Array's specific neutron-reference material and supply route are deferred under [ADR-0037](adrs/ADR-0037-defer-array-neutron-reference-material.md). Before its bill of materials is finalized, the selected input must have a pre-Core supply path and must not require enriched fission fuel.

**Physical description:** *A precision metrology instrument that integrates six distinct physics measurement domains into one coherent device mounted inside a vibration-isolated, thermally-stabilized calibration frame. Each zone operates as independent instrumentation, scientific hardware from each practitioner's field — co-located to enable cross-domain calibration while the simulation network runs.*

### Candidate Satellite Buildings

The Core has four satellite facility types, each adding capacity or data streams:

| Satellite | Function | Links to Core |
|-----------|---------|---------------|
| **Compute Campus Node** | Adds processor capacity for model runs | Connected via integration bus (superconducting cables + optical waveguides) to Computation Cluster |
| **Memory/Archive Module** | Stores model states and simulation results for feedback loops | Direct storage interface with Thermal Frame cooling infrastructure |
| **Regional Observation Facility** | Analyzes samples/operating data → submits domain datasets | Feeds raw measurement data into the Calibration Reference Frame hardware |
| **Calibration Sub-Network** | Improves model fidelity and efficiency via domain-lab feedback loops | Uses all six domain labs as active measurement calibration reference points (labs don't just "produce packs" — they calibrate Core measurement fidelity) |

The following Core tier progression is a candidate:

| Tier | What Changes | Upgrade Requirements |
|------|-------------|---------------------|
| **Activation (T1)** | Basic coordination of 6 domain inputs | Thermal Frame + conventional CPU-based Computation Cluster + Calibration Reference Frame (with Unified Metrology Array mounted) |
| **Level 2** | Higher-fidelity models, accelerated discovery | Quantum-state enhancement module + memory expansion + Integration Bus upgrade for faster satellite communication |
| **Level 3 / Final Milestone** | General-physics discovery unlock | Multi-domain synthesis components — fully integrated across all facilities; Calibration Reference can model phenomena beyond known physics |

The Core and its peripheral facilities may be built and upgraded in stages. The draft favors an overlapping, gradual handoff across Core Levels 1–3 rather than an abrupt switch, with domain labs changing from research-pack production to Model Calibration sub-facilities ("simulation trainers") that improve fidelity and efficiency. These roles remain proposals. Each stage could require complex products from several parts of the factory while keeping most compute and memory physically distributed.

The Josephson/SFQ compute direction is a post-activation upgrade, not part of the first-Core gate. Its exact Core level, materials, cryogenic requirements, and research unlock remain open.

## Candidate Model Inputs

The network is proposed to be fed evidence that the factory has built the capabilities it is modeling. Domain science packs from the six listed research facilities represent cross-domain knowledge demonstration — breadth across physics disciplines, not depth in one.

- **Plasma Physics Readings** (Superconductivity Research Lab) — requires electronic-grade polysilicon + Nb₃Sn wire as facility materials
- **Magnetic Confinement Data** (Plasma Confinement Facility) — requires Nb₃Sn wire + cryogenic infrastructure
- **Materials Science Results** (Nanofabrication Laboratory) — requires hafnium-oxide dielectric for cleanroom operation
- **Nuclear Cross-Section Measurements** (Isotope Separation & Calibration Lab) — requires deuterium-enriched water
- **Chemical Kinetics Data** (Reaction Dynamics Facility) — requires **high-performance rhenium-catalyst powder** 
- **Quantum Statistical Data** (Quantum States Laboratory) — requires cryogenic argon/nitrogen mixture

### How Domain Packs Are Used

**Phase 2 (Bridge):** Domain packs are fed into the conventional research building *alongside* standard science packs, augmenting the existing tech tree. This is the Space Exploration model — domain packs supplement but don't replace the standard research infrastructure. They do **not** go to a simulation Core at this stage because the Core does not yet exist. The player is still researching technologies through the conventional research building; domain packs simply add *additional capability gates* that require cross-domain knowledge before certain technologies can be unlocked.

**Phase 3 (simulation-gated, candidate):** After the six domain research facilities are operational, the proposed loop transitions to the Planetary Simulation Core: domain datasets → simulation models → findings unlock technologies.

These are six separate research facilities, each with a selected Phase 2 bridge product as its industrial prerequisite under [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md). Additional construction and operating inputs remain open; the selected bridge products alone do not define complete facility bills of materials. The player must demonstrate knowledge across all six domains before advancing any simulation fidelity tier.

## Simulation Scope Candidates

The network's modeling capability evolves through stages as more domains are understood and connected to the Core. These describe what the simulation *models* at each stage, not which technologies they gate (see [Research and Progression](research-progression.md) for research mechanics).

| Stage candidate | Model scope | Candidate evidence / inputs from facilities |
| --- | --- | --- |
| Planetary model | Geology, resources, major physical systems | Survey results plus operating data from real production chains |
| Industrial model | Extraction, refining, power, chemistry, and logistics as interacting systems | Industrial process data from operational factories |
| Information-based model | Populations of information-formed entities that perceive, decide, and act within the modeled world | Planetary/industrial model results plus behavioral datasets |
| General-physical model (possible final extension) | Broader physical laws beyond the planet | Advanced physics experiments, extreme-energy facility data |

These are scope candidates for what the simulation network grows to model. The exact sequence, dependency between stages, and which infrastructure changes occur at each transition remain open — they should be designed alongside the research-progression document so that physical infrastructure milestones align with research gates.

## Candidate Network Requirements

| Capability | Candidate facilities / dependencies |
| --- | --- |
| Research/data production | Survey, assay, process-monitoring, materials-analysis, and experimental facilities |
| Memory/archive | Storage capacity, stable power, logistics/network links |
| Regional compute | Packaged processors, cooling, stable power, network infrastructure |
| Planetary Simulation Core | Core structure, model-control components, connected dataset and compute networks |
| Simulation cluster | Multiple compute sites, high-capacity power, thermal management, synchronization/control systems |

Semiconductor-grade silicon, wafers, processors, packaging, and specialty materials are prerequisite production chains described in [Intermediate Products](intermediate-products.md), rather than facilities in this endgame network.

Specific material recipes belong in the [Intermediate Products](intermediate-products.md) map; chemical syntheses and purification reactions belong in [Chemical Products and Processes](chemical-processes.md).

## Candidate Design Principles

- **Distributed, not monolithic:** the final achievement spans multiple facilities and locations.
- **A visible anchor, distributed capability:** the Core is recognizable, but peripheral facilities provide most memory, compute, and evidence.
- **Simulation, not AI housing:** model thinking entities as part of the simulated world rather than framing the Core as a home for an AI character.
- **Evidence-backed inputs:** model datasets represent surveyed or operated systems and should have understandable sources.
- **Capability milestones:** establish conventional CPU production and full contemporary cleanroom/chipmaking before first-Core activation under [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md), then use the Core to unlock primarily beyond-current-day semiconductor and superconducting-compute capabilities rather than a sequence of generic numerical upgrades.
- **Simulation has progression value:** reserve meaningful late-game research for model results so building the network is necessary to advance, not just decorative endgame production.
- **Cross-chain demand:** the endgame should pull distinct materials from mining/refining, chemistry, metallurgy, and power systems.
- **Meaningful placement:** regional facilities should create logistics, cooling, power, and land-use decisions.
- **Legible progress:** the handbook and factory UI should show the network's outstanding dependencies and completed capabilities.
- **No arbitrary disposal:** excess and coproducts remain governed by the same balanceability rules as the rest of the mod.

## Open Design Decisions

### Facility Infrastructure

- What gates and roles should apply to Core Levels 2–3? See [Research and Progression](research-progression.md).
- Which post-activation Core level should introduce Josephson/SFQ compute?
- **Deferred to Phases 4, 6, and 7 — first-Core alignment assembly:** The Phase 2-compatible, non-semiconductor constraint is set, but the exact mechanism, materials, and source are not. Define its constructable role in Phase 4, select its product path in Phase 6, and specify its recipe in Phase 7. This is not a Phase 2 material-trunk blocker, but its eventual construction demand must be assessed before finalizing the Core bill of materials. Do not treat any candidate mechanism or material as selected.
- Are Core Levels 1–3, their pack totals, and the proposed post-activation role of domain labs part of the final progression?
- Is there a single final milestone, or a staged set of regional commissioning goals?
- How much of the compute network must be physically distributed to make the spatial requirement meaningful without becoming arbitrary busywork?
- What are the power, cooling, and network constraints, and which are core versus optional optimization?
- What is the endgame's intended playtime contribution within the broader 300+ hour overhaul ambition?
- Does completing the planetary digital twin end the game, or unlock further gameplay?
