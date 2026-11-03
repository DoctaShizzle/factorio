# Endgame Vision - Distributed Planetary Computing

*For: Factorio Overhaul Mod*  
*Status: Vision / requirements phase*

Related documents: [Mod Overview](mod-overview.md), [Intermediate Products](intermediate-products.md), and [Power System](power-system.md).

## North Star

The endgame hook is: **Build a planetary digital twin by constructing a computational civilization.** The simulation should model the planet's physical systems and populations of agent-like entities that make decisions, somewhat like people. These entities are the subject of the simulation; the premise is not an AI character housed inside a building.

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

The network should be fed evidence that the factory has built the capabilities it is modeling. Rather than adding a large generic science-pack family, consider a small number of traceable dataset products:

- **Planetary survey data:** prospecting, mineral analysis, and resource mapping.
- **Industrial process data:** operating chemical, refining, metallurgy, and power systems.
- **Materials and physics data:** cleanroom fabrication, precision measurements, and advanced experiments.
- **Agent/civilization models:** later simulation inputs representing decision-making entities and interacting systems.

The number and exact form of datasets remain open. They should come from meaningful processes, not require every ordinary machine to emit a bookkeeping item.

## Candidate Simulation Research Loop

One possible interpretation of the distributed simulation network is a set of connected research/data facilities plus regional compute and memory nodes, coordinated by the Planetary Simulation Core. Research facilities accept domain datasets; the Core runs the relevant model if the network has enough installed compute, memory, power, and cooling; completed runs produce findings or model results that unlock selected technologies and the next simulation stage.

In this model, conventional science packs can carry the early game. Later simulation research adds a distinct requirement: the right evidence datasets and enough operational network capacity. Compute capacity would normally be infrastructure, not a consumable item; model results could be research inputs or unlock flags. Whether datasets are consumed, retained, or represented as research ingredients is still open.

## Simulation and Research Progression

The simulation should become necessary for late-game research, not merely be a final monument players build after unlocking everything. Conventional research can establish early and mid-game capabilities; later discoveries should require model results produced by the Core from relevant datasets and available compute capacity.

| Candidate stage | Model scope | Candidate evidence / inputs | Progression role |
| --- | --- | --- | --- |
| Conventional science | Established technologies and known processes | Existing research system | Opens industrial foundations and the first survey/model facilities |
| Planetary and industrial model | Deposits, material flows, power, chemistry, and manufacturing systems | Survey results plus operating data from real production chains | Gates selected advanced process, materials, and cleanroom capabilities |
| Agent-based civilization model | Populations of decision-making entities interacting with a modeled planet | Planetary/industrial model results plus a small set of social or behavioral datasets | Gates the planetary simulation project and highest computation capabilities |
| General-physics model (possible final extension) | Deeper physical laws and virtual-cosmos experiments | Advanced physics experiments, extreme-energy facilities, and expanded compute | Optional or final research frontier; scope and literalness remain undecided |

Candidate research loop: produce a small number of domain datasets from meaningful facilities; route them to the simulation network; provide the required compute, power, and cooling; receive model results that unlock selected late technologies. This can echo science packs without simply adding more colored packs. Exact dataset items, research gates, and whether research consumes or only checks those inputs remain open.

## Candidate Simulation Milestones

Possible stages broaden the model from the planet's industrial foundations toward more abstract systems:

1. **Planetary model:** map geology, resources, and major physical systems.
2. **Industrial model:** represent extraction, refining, power, chemistry, and logistics as interacting systems.
3. **Agent-based model:** simulate populations of entities that perceive, decide, and act within the modeled world.
4. **General physical model:** explore broader physical laws and processes beyond the planet.

These are scope candidates, not a committed research tree. The final target should feel intellectually ambitious while remaining understandable and grounded in capabilities the player has actually built.

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

- What exactly does completing the planetary digital twin accomplish in gameplay: unlock technologies, enable new modeling capabilities, complete a final project, or some combination?
- How many late-game technologies should require simulation results, and which capabilities remain researchable through conventional science?
- Is general-physics simulation an optional extension, a final victory stage, or out of scope? What does "universe-scale" mean without promising literal particle-by-particle simulation?
- What are the dataset families, and how are they produced without turning ordinary factory operation into paperwork?
- Is there a single final milestone, or a staged set of regional commissioning goals?
- How much of the compute network must be physically distributed to make the spatial requirement meaningful without becoming arbitrary busywork?
- What are the power, cooling, and network constraints, and which are core versus optional optimization?
- How will PLCs and simulation infrastructure interact without making a general-purpose control language mandatory for victory?
- What is the endgame's intended playtime contribution within the broader 300+ hour overhaul ambition?

The final victory condition and exact recipes are deliberately not fixed yet. They should be designed after the industrial material roster and capability progression are stable.
