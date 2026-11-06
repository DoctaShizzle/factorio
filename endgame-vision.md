# Endgame Vision - Distributed Planetary Computing

*For: Factorio Overhaul Mod*  
*Status: Vision / requirements phase*

Related documents: [Mod Overview](mod-overview.md), [Intermediate Products](intermediate-products.md), [Power System](power-system.md), and [Research and Progression](research-progression.md) for simulation-gated research mechanics.

## Summary

This document defines the endgame as building a planetary digital twin by constructing a distributed computational civilization. The Planetary Simulation Core coordinates model runs across specialized facilities spread over the map, while wafer and processor fabrication serve as prerequisite chains rather than endgame facilities themselves.

**What it covers:** The core hook ("planetary digital twin of thinking entities"), recognizable structure (Core + memory archives + regional compute campuses + research/observation facilities), candidate simulation research loop (datasets → Core schedules runs → model results unlock research), and open design decisions about dataset families, simulation-research gate ratios, and the final victory condition.

**What it does not cover:** Research progression mechanics — including how conventional science transitions to simulation-gated research, domain science pack design, and technology gating rules. These are defined in [Research and Progression](research-progression.md). Semiconductor fabrication mechanics or specific recipe pathways — those are tracked in [Intermediate Products](intermediate-products.md). Infrastructure requirements like power consumption are outlined here but detailed in [Power System](power-system.md).

## North Star

The endgame hook is: **Build a planetary digital twin by constructing a computational civilization.** The simulation should model the planet's physical systems and populations of information-based entities — beings composed of structured data, not artificial intelligence. These entities perceive their environment, make decisions, and interact with modeled systems in ways that emerge from their structure and dynamics rather than programmed behavior. These entities are the subject of the simulation; the premise is not an AI character housed inside a building.

The planetary digital twin is the clear, concrete promise. Modeling broader physical laws or a virtual cosmos can be a final extension of that work, but should not replace the planetary-scale hook or imply literal simulation of every particle in the universe.

The required computational capacity is distributed across specialized facilities spread over the map, each dependent on the industrial ecosystem built earlier. The player should feel that this network is the culmination of mining, refining, metallurgy, chemistry, power, electronics, logistics, and factory control.

## Production Prerequisites and Facility Network

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

The **Planetary Simulation Core** is a candidate signature building: a distinctive coordinator and visible project anchor, not a single megastructure containing all computation or an AI persona. It schedules and aggregates model runs; most compute and memory capacity remains in connected facilities. Its footprint, graphics, construction requirements, and stages are undecided.

| Facility role | Candidate function |
| --- | --- |
| Planetary Simulation Core | Coordinates model runs, reports model coverage/progress, and issues simulation projects |
| Memory/archive facilities | Store survey data, process data, model states, and simulation results |
| Regional compute campuses | Add processor capacity, power demand, and cooling requirements |
| Research/observation facilities | Analyze samples and operating data, then submit domain datasets to the network |

The Core and its peripheral facilities may be built and upgraded in stages. Each stage can require complex products from several parts of the factory, in the spirit of a major project such as Satisfactory's Space Elevator, while keeping most compute and memory physically distributed.

## Candidate Model Inputs

The network is fed evidence that the factory has built the capabilities it is modeling. Domain science packs from five dedicated research buildings represent cross-domain knowledge demonstration — breadth across physics disciplines, not depth in one:

- **Plasma Physics Readings** (Superconductivity Research Lab) — requires electronic-grade polysilicon + Nb₃Sn wire as facility materials
- **Magnetic Confinement Data** (Plasma Confinement Facility) — requires Nb₃Sn wire + cryogenic infrastructure
- **Materials Science Results** (Nanofabrication Laboratory) — requires hafnium-oxide dielectric for cleanroom operation
- **Nuclear Cross-Section Measurements** (Isotope Separation & Calibration Lab) — requires deuterium-enriched water
- **Quantum Statistical Data** (Low-Temperature Physics Facility) — requires cryogenic argon/nitrogen mixture

### How Domain Packs Are Used

**Phase 2 (Bridge):** Domain packs are fed into the conventional research building *alongside* standard science packs, augmenting the existing tech tree. This is the Space Exploration model — domain packs supplement but don't replace the standard research infrastructure. They do **not** go to a simulation Core at this stage because the Core does not yet exist. The player is still researching technologies through the conventional research building; domain packs simply add *additional capability gates* that require cross-domain knowledge before certain technologies can be unlocked.

**Phase 3 (Simulation-gated):** Only after all five domain research facilities are operational and domain pack production begins do we transition to the Planetary Simulation Core. Phase 3 introduces the core loop: domain datasets → simulation models → findings unlock new technologies.

These are five separate research facilities, each requiring a distinct Phase 2 bridge product as industrial prerequisite. The player must demonstrate knowledge across all five domains before advancing any simulation fidelity tier.

## Simulation Scope Candidates

The network's modeling capability evolves through stages as more domains are understood and connected to the Core. These describe what the simulation *models* at each stage, not which technologies they gate (see [Research and Progression](research-progression.md) for research mechanics).

| Stage candidate | Model scope | Candidate evidence / inputs from facilities |
| --- | --- | --- |
| Planetary model | Geology, resources, major physical systems | Survey results plus operating data from real production chains |
| Industrial model | Extraction, refining, power, chemistry, and logistics as interacting systems | Industrial process data from operational factories |
| Information-based model | Populations of information-formed entities that perceive, decide, and act within the modeled world | Planetary/industrial model results plus behavioral datasets |
| General-physical model (possible final extension) | Broader physical laws beyond the planet | Advanced physics experiments, extreme-energy facility data |

These are scope candidates for what the simulation network grows to model. The exact sequence, dependency between stages, and which infrastructure changes occur at each transition remain open — they should be designed alongside the research-progression document so that physical infrastructure milestones align with research gates.

## What the Network Needs

| Capability | Candidate facilities / dependencies |
| --- | --- |
| Research/data production | Survey, assay, process-monitoring, materials-analysis, and experimental facilities |
| Memory/archive | Storage capacity, stable power, logistics/network links |
| Regional compute | Packaged processors, cooling, stable power, network infrastructure |
| Planetary Simulation Core | Core structure, model-control components, connected dataset and compute networks |
| Simulation cluster | Multiple compute sites, high-capacity power, thermal management, synchronization/control systems |

Semiconductor-grade silicon, wafers, processors, packaging, and specialty materials are prerequisite production chains described in [Intermediate Products](intermediate-products.md), rather than facilities in this endgame network.

Specific material recipes belong in the [Intermediate Products](intermediate-products.md) map; chemical syntheses and purification reactions belong in [Chemical Products and Processes](chemical-processes.md).

## Design Principles

- **Distributed, not monolithic:** the final achievement spans multiple facilities and locations.
- **A visible anchor, distributed capability:** the Core is recognizable, but peripheral facilities provide most memory, compute, and evidence.
- **Simulation, not AI housing:** model thinking entities as part of the simulated world rather than framing the Core as a home for an AI character.
- **Evidence-backed inputs:** model datasets represent surveyed or operated systems and should have understandable sources.
- **Capability milestones:** unlock cleanrooms, wafer fabrication, advanced packaging, and simulation infrastructure rather than a sequence of generic numerical upgrades.
- **Simulation has progression value:** reserve meaningful late-game research for model results so building the network is necessary to advance, not just decorative endgame production.
- **Cross-chain demand:** the endgame should pull distinct materials from mining/refining, chemistry, metallurgy, and power systems.
- **Meaningful placement:** regional facilities should create logistics, cooling, power, and land-use decisions.
- **Legible progress:** the handbook and factory UI should show the network's outstanding dependencies and completed capabilities.
- **No arbitrary disposal:** excess and coproducts remain governed by the same balanceability rules as the rest of the mod.

## Open Design Decisions

### Facility Infrastructure

- Is there a single final milestone, or a staged set of regional commissioning goals?
- How much of the compute network must be physically distributed to make the spatial requirement meaningful without becoming arbitrary busywork?
- What are the power, cooling, and network constraints, and which are core versus optional optimization?
- What is the endgame's intended playtime contribution within the broader 300+ hour overhaul ambition?
