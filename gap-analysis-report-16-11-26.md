# Project Prometheus - Updated Comparative Gap Analysis

*Date: 2026-11-16*

*Status: Work-plan Phase 3 evidence and gap-ledger baseline; not an approved product catalog or design decision.*

This report replaces the assessment in the [2026-11-11 gap analysis](gap-analysis-report-11-11-26.md), while preserving that report as historical evidence. It also reassesses the recommendations in the earlier [market research](market-research-report.md). The current design belongs to the domain owners in the [Documentation Map](documentation-map.md); the [plan](plan.md) owns work order and gates.

## Executive Assessment

- **The primary comparisons are Space Exploration and Bob's/Angel's:** both are Factorio overhauls, but they offer different lessons. Space Exploration is a benchmark for a long, coherent sequence of new capabilities and logistics challenges; Bob's/Angel's is a benchmark for breadth of industrial processing and interconnected material demand. Prometheus needs to be credible against *both*, not merely smaller than GTNH.
- **GTNH is an inspiration, not a material-count target.** Its geology, recoveries, and route selection offer useful ideas, but Minecraft's mechanics and item granularity differ. The concern that its material index can feel chaotic is a design risk raised by the project author, not a measured conclusion about all players.
- **Prometheus already has substantial advanced-industry direction.** Six bridge materials and their facility mappings, 42 distinct domain-pack tiers, contemporary Phase 2 semiconductor capability, several power routes, and controlled waste handling are selected in part. They are not yet a playable, validated production tree. The 42 domain-pack items are a design commitment, not an implemented count or a measure of game depth.
- **The principal gaps are evidence and integration, not an established item deficit:** scope and machine-family classification, credible source-to-consumer and startup paths, useful process choices, coproduct handling, geographic access, and a discoverable player journey remain to be demonstrated. Detailed products, recipes, and technology gates belong to later work-plan phases.
- **Comparability is not yet demonstrated.** The documents contain strong concepts, but no playtested timing, difficulty, quality-of-life, completion, or performance evidence. Neither matching a reference mod's count nor avoiding additional items proves that the experience is sufficiently deep or legible.
- **Provisional percentage assessment:** A subjective readiness rubric gives approximately **43%** for the proposed 300+ hour journey, **40%** against selected Space Exploration pillars, and **45%** against selected Bob's/Angel's pillars. These are planning indices, not measured shares of engaging hours or of either mod's content; actual playtime and gameplay quality remain unknown. See [Quantitative Planning Assessment](#quantitative-planning-assessment).

## Method and Evidence Limits

In this report, **gameplay Phase 1-4** means the industrial/power progression; **work-plan Phase 3-8** means the documentation and design stages in [plan.md](plan.md). These are different phase systems.

Each older recommendation is assigned one of the work-plan dispositions:

- **Confirmed gap:** a requirement or capability already in the current design lacks the necessary documented coverage or validation. This does not prove that the capability is impossible, that an additional item is needed, or that detailed recipes should be designed now.
- **Already covered:** the capability or concept exists in the current design; individual implementation details can still be open.
- **Not a gap:** no current requirement or evidence establishes the proposed addition or shortfall. This is not a permanent rejection.
- **Conflict:** the recommendation or assumption contradicts a selected constraint or the current design's explicitly bounded rules.
- **Optional/extension:** an idea is nonessential to the core requirement or is outside the accepted Core boundary. An unapproved idea is not thereby approved for an extension.
- **Needs a decision:** a genuine scope, behavior, or candidate-selection question remains open; this report does not choose the answer.

**Priority** indicates when missing evidence threatens the planned gates, not an implementation schedule. High-priority coverage must be addressed at the named gate; medium-priority work can proceed once its scope is chosen. Recipe quantities and numerical balances remain work-plan Phase 7, and the technology graph remains Phase 8.

This review uses current repository documents and the public descriptions below. It did **not** install or play the comparator modsets, inspect their full prototype inventories, or benchmark Prometheus. Counts from different versions, settings, dependencies, and product classes are not like-for-like.

### Comparator Sources

| Reference | What the source supports | Limits and relevance |
|---|---|---|
| [Space Exploration](https://mods.factorio.com/mod/space-exploration) | The author describes a long logistics-and-complexity challenge, 29 science packs, an average completion time of about 500 hours, over 50 hours to space, regional resource differences, and four specialist science branches. | These are the mod author's description and estimates, not independent distributions or a target for Prometheus. Planetary logistics is not a requirement to copy its planets or space travel. |
| [Angel's Refining and suite overview](https://mods.factorio.com/mod/angelsrefining) | The description presents six compound ores, successive refining, ore yields and unlocked outputs, petrochemistry, metallurgy, and optional industry-overhaul settings. | A compound ore is not a Prometheus deposit type. The combined Bob's/Angel's experience depends on selected modules and settings; the description is not a normalized catalog. |
| [Bob's Metals, Chemicals and Intermediates](https://mods.factorio.com/mod/bobplates) | The author describes reusable processing equipment, multiple metals and alloys, chemicals, ceramics, component materials, and battery tiers. | This is one Bob's module, not a complete combined-modset inventory. The existence of a material or variant is not itself a reason to require its Prometheus counterpart. |
| [GTNH ore-processing concepts](https://wiki.gtnewhorizons.com/wiki/Ore_Processing_Concepts) and [ore generation](https://wiki.gtnewhorizons.com/wiki/Ore_Generation) | Veins have recognizable compositions and ore-processing routes can trade different outputs, such as bauxite routes yielding different byproducts. | Useful inspiration for prospecting and conditional route choice; not a comparable recipe, material, machine, or playtime quota. |

For context, the public release APIs on the review date list [Space Exploration 0.7.64](https://mods.factorio.com/api/mods/space-exploration), [Angel's Refining 2.1.3](https://mods.factorio.com/api/mods/angelsrefining), and [Bob's Metals 3.0.2](https://mods.factorio.com/api/mods/bobplates) with Factorio 2.1 metadata. The descriptive pages are not version-pinned inventories, and these three releases were not installed or tested as a combined configuration. Prometheus has not yet selected its target Factorio version or DLC.

The market report is useful for its questions about pacing, payoff, military pressure, and onboarding. Its audience forecasts, abandonment rates, sci-fi percentages, community sentiment, and cross-title causal claims are not established by cited measurements. The Space Exploration author's 500-hour estimate does not establish Prometheus playtime, unique players, or market size.

## Quantitative Planning Assessment

**Answer to the 300+ hour question:** The current design scores **approximately 43%** on the time-weighted readiness model below. This is an estimate of how far the *documented journey's gameplay systems* have progressed from concept toward playable loops. It is **not** a finding that 43% of 300 hours, or approximately 129 hours, are already designed, playable, or enjoyable. The number of enriching hours is unknown; no Prometheus-specific playtest hours are recorded in this repository.

**Answer to the comparison question:** On separate, equally weighted pillar checklists, Prometheus scores **40% relative to Space Exploration** and **45% relative to Bob's/Angel's**. These figures compare the readiness of the selected functional pillars against reference features described as available in those mods. They are **not** percentages of the mods' total content, playtime, quality, or fun, and the five-point difference is not meaningful evidence that Prometheus is closer to one overall. Confidence in all three indices is very low.

For this assessment, an *enriching loop* is one in which a player can recognize a goal, make an understandable engineering or exploration choice, see its consequences, and receive a useful capability or other payoff. This is an analytical aid, not a new approved design rule or proof of player enjoyment.

### Scoring Method

Each journey era or comparison pillar receives a subjective score:

| Score | Evidence required |
|---|---|
| 0 | No identifiable corresponding goal or loop. |
| 1 | A goal or candidate concept exists, but key player actions, decisions, or payoffs remain open. |
| 2 | Some named functions, progression boundaries, or constraints are selected, but the connected player loop or key dependencies are incomplete. |
| 3 | A coherent, end-to-end loop is documented, including the goal, player actions, tradeoffs, payoff, and critical dependencies, but it is not yet playable. |
| 4 | An implemented, playable loop is described as available; this alone does not establish its duration or that players find it engaging. |

These are ordinal judgments, not statistically calibrated measures. Candidate concepts can support a score of 1, but are not treated as selected requirements. A score of 2 does not mean half of a loop's recipes, hours, or development effort is complete.

### Readiness of the Proposed Long-Form Journey

The [Research and Progression](research-progression.md) document proposes three research eras totaling **280-340 hours**; their midpoints form an illustrative **310-hour** scenario. Those durations are unvalidated proposals, not approved milestones. The earlier market report uses a different, unsupported phase split and is not the basis for this calculation.

| Proposed research era | Candidate hours; midpoint | Score | Evidence and the missing enriching loop |
|---|---|---|---|
| Conventional industry | 30-40; 35 | 2/4 | [World Generation](map-world-generation.md) sets geological discovery and [Power System](power-system.md) selects the early combustion boundary. Early supply paths, introductory process choices, and player guidance remain incomplete; see G02 and G08. |
| Domain-science bridge | 180-200; 190 | 2/4 | Six domains, their pre-Core tiers and bridge mappings, CPU supply, and the first-Core boundary are selected. Routes, useful choices, payoff cadence, and the complete dependency graph remain open; see G03-G07 and G10. |
| Simulation-gated progression | 70-100; 85 | 1/4 | [Endgame Vision](endgame-vision.md) proposes distributed facilities and a data-to-model-to-research loop, but later facility roles, player decisions, progression gates, and final payoff remain open; see G10 and Q04. |

The calculation is `((35 x 2) + (190 x 2) + (85 x 1)) / (310 x 4) = 43.1%`, rounded to **43%**. The weight reflects the *proposed* time distribution, not observed player time. For example, scoring the bridge 1/4 instead of 2/4 changes the result to **28%**; that sensitivity illustrates why this is a rough judgment rather than a precise completion measurement. A longer proposed era must not be interpreted as evidence that it already contains more engaging content.

### Readiness Relative to Space Exploration

The baseline is the [Space Exploration author's description](https://mods.factorio.com/mod/space-exploration), not an installed or independently played version. For each chosen pillar, the reference is normalized to 4/4 because its public description presents that feature as playable; 100% is a comparison baseline, **not** a claim that the experimental mod is finished or perfect. Prometheus may provide an equivalent kind of decision without copying space travel or planets.

| Reference pillar | Prometheus evidence and missing work | Score |
|---|---|---|
| Early industrial progression and a major transition | Basic industrial and power direction and the first-Core threshold exist; the actual early-to-bridge journey and payoff cadence remain untraced. | 2/4 |
| Distinct research branches and unlocks | Six domains and first-Core convergence are selected; exact technologies, intermediate rewards, and branch choices remain open. | 2/4 |
| Resource discovery and spatial logistics | Geological regions and access constraints are selected; transport behavior, generated maps, and meaningful expedition-to-factory loops remain unvalidated. | 2/4 |
| New late-game gameplay mechanics | Distributed computing and simulation are candidate concepts; their actual player interactions and tradeoffs are not specified end to end. | 1/4 |
| Endgame milestones and payoff | A planetary digital twin is the intended hook; required network capabilities and the final milestone or victory remain open. | 1/4 |

**Result:** `(2 + 2 + 2 + 1 + 1) / 20 = 40%`. The largest gaps against this lens are a coherent discovery/logistics journey and concrete late-game interactions and payoffs, not the absence of space itself. See G09, G10, Q03, and Q04.

### Readiness Relative to Bob's/Angel's

The reference lens uses the publicly described [Angel's Refining and suite](https://mods.factorio.com/mod/angelsrefining) and [Bob's Metals, Chemicals and Intermediates](https://mods.factorio.com/mod/bobplates): refining, petrochemistry, metallurgy, materials, and the cited equipment. It is not a complete or version-pinned combined modpack, and optional modules and settings change the experience. The same 4/4 reference normalization and untested-source limitations apply.

| Reference pillar | Prometheus evidence and missing work | Score |
|---|---|---|
| Ores, refining stages, and recoverable outputs | Feed categories, shared route patterns, and the baseline/advanced rule for polymineral feeds exist; individual usable routes and outputs remain to be traced. | 2/4 |
| Chemicals and coproduct handling | Chlor-alkali, silicon chemistry, and powered disposal boundaries are selected; complete operating loops and uneven-demand handling remain to be demonstrated. | 2/4 |
| Materials and downstream uses | Bridge products and selected semiconductor and power material roles connect production to capabilities; construction demand and many consumer paths remain candidate or incomplete. | 2/4 |
| Factory equipment and industrial integration | Some roles, including the silicon furnace and disposal facilities, are selected; machine-family scope, tiering, builds, and full process assignments remain open. | 2/4 |
| Actionable process tradeoffs and progression | Alternative routes and tradeoffs are design goals, with steel and lithium examples proposed; their actual choices, consequences, and balances are not yet established. | 1/4 |

**Result:** `(2 + 2 + 2 + 2 + 1) / 20 = 45%`. Prometheus has substantial industrial direction, but not yet a demonstrated network of usable routes, consumers, and tradeoffs comparable to the referenced experience. See G01, G02, G06, and G07.

### How to Improve and Replace These Estimates

1. In the planned coverage work, trace representative early, bridge, and post-Core player journeys: goal, available choices, required inputs, consequences, payoff, and the next meaningful decision. The long bridge deserves particular attention because it dominates the proposed time budget.
2. Resolve and trace representative refining, chemistry/coproduct, construction, geographic logistics, and simulation examples against G02, G03, G06-G10. Do not equate more products, science packs, or repeated construction with more enriching hours.
3. After playable slices exist, record player actions and milestone times, ask players about interest, confusion, and repetition, and test the full journey. Compare against a stated Space Exploration version and a stated Bob's/Angel's mod list and settings using comparable player profiles. Select a completion criterion and intended player profile before interpreting the 300+ hour goal.

Re-score the same rows as evidence changes. Replace these subjective indices with measured timing and player feedback when those data exist; neither a long completion time nor a completed checklist alone establishes an enriching experience.

## Factorio Comparison: What Must Be Demonstrated

| Dimension | Reference signal | Current Prometheus evidence | Remaining comparison question |
|---|---|---|---|
| Ore and material breadth | Bob's/Angel's combines a compact refining vocabulary with a wide range of downstream materials. | [Minerals and Refining](minerals-and-refining.md) has candidate deposits, shared stages, and recovery patterns; [Intermediate Products](intermediate-products.md) has candidate alloys and components. Counts and demand assignments are provisional. | Do the selected deposits and materials create sufficiently varied, understandable factory problems without separate items whose only purpose is index growth? See G01, G02, and G06. |
| Process choice | Angel's describes advanced refinement with different yields and outputs; GTNH illustrates route-dependent byproducts. | Candidate blast-furnace and direct-reduction steel paths, refining templates, and selected lithium feed alternatives exist. Their exact routes and tradeoffs are not validated. | Can a player make a defensible different choice for major products and exploit an advanced route for each polymineral feed? See G06. |
| Chemistry and coproducts | Bob's/Angel's connects chemistry, refining, and manufactured materials; excess-stream handling is part of the factory problem. | The [chemistry owner](chemical-processes.md) lists interconnected process families, including chlor-alkali and the selected silicon route; disposal and nuclear recovery rules are selected. | Can the player operate representative chains under changing demand, with useful feedback and valid handling at first output? See G04 and G07. |
| Research and pacing | Space Exploration describes an early launch milestone, four specialist branches, and new mechanics over a long game. | Six domains have seven distinct pack tiers each: four pre-Core and three post-Core. All six reach T2b2 plus the Array before the first Core; exact inputs and technology assignments remain open. | Do individual domains provide worthwhile intermediate payoffs and manageable decisions before their mandatory convergence? The 42 domain items exclude conventional packs and cannot be compared directly to Space Exploration's stated 29 science packs. See G03 and G10. |
| Exploration and logistics | Space Exploration gives different locations distinct resources and logistics constraints. | [World Generation](map-world-generation.md) proposes geological regions and prospecting, with selected access deadlines for several Phase 2 feeds; rail and dispatch behavior remains candidate design. | Do geography and transport create discoverable, varied choices while every required feed remains reachable in time? Do not assume interplanetary logistics is needed. See G09 and Q03. |
| Construction and usable outputs | Bob's/Angel's includes production, component, transport, and equipment systems, depending on modules and settings. | [Infrastructure](infrastructure.md) and [Intermediate Products](intermediate-products.md) have family checklists, but their scope dispositions, construction demands, and product identities are incomplete. | Are the needed factory, logistics, defense, personal, and research families covered as new, retained, modified, replaced, optional, or out of scope? See G01 and G02. |
| Motivation and payoff | Space Exploration's described milestones give logistics work a visible purpose. | Phase 2 includes superconducting bridge material, fission options, PV/LFP storage, and contemporary chipmaking; the simulation network is a distinct later goal. Exact milestone presentation and completion are open. | Do players encounter understandable, rewarding capabilities throughout the industrial journey, rather than only a distant payoff? See G08, G10, and Q04. |
| Learnability | Both references put considerable demands on players; Space Exploration's page explicitly calls out circuitry knowledge. | The handbook must show the industrial journey before construction, and machine/chemistry guidance should expose inputs, outputs, coproducts, uses, and eligibility. | Can players find the next useful capability, understand a tradeoff, and diagnose a blocked chain without a large unexplained materials index? See G08. |

These are comparison questions, not evidence that either reference is uniformly more accessible, more interesting, or less chaotic. A long intended playthrough is an ambition, not proof of the necessary amount of content.

## Current Scope Boundaries

| Scope | Relevant current direction |
|---|---|
| **Core** | Current chemical process-family concepts, required bridge and semiconductor capabilities, the selected power choices, ordinary gas/fluid disposal, and required nuclear recovery/disposal when a fission route is used. Individual candidate chemicals, machines, recipes, and exact product forms are not automatically approved. |
| **Vanilla retained** | The native power grid, vanilla boilers and untiered steam engines, and the Phase 2 steam-turbine conversion path are selected, with compatible tiered poles added. See [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) and [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md). |
| **Vanilla modified** | The selected progression makes PV unavailable in gameplay Phase 1 and available no earlier than Phase 2. Exact treatment of individual vanilla solar, storage, recipe, and technology prototypes remains to be classified. |
| **Vanilla replaced** | Some infrastructure entries propose replacements, but a version-specific replacement inventory is not approved. Classify each family rather than assuming a wholesale replacement. |
| **Extension** | Custom voltage/loss and grid-specific diagnostics/stabilization are outside Core and remain unapproved extension candidates. Spider-bot and power-suit additions are optional advanced-military directions, not selected products. |
| **Other open or excluded scope** | Military drones were rejected; a trade/economy system is not in the current world-generation design. The enemy/pressure model, powered rails, dispatch, other equipment, final victory, and the target game version remain open. |

The selected ordinary disposal policy uses separate powered, pollution-producing gas and liquid facilities. The nuclear-only exception permits continuous disposal of eligible conditioned residues and surplus depleted oxide with power/material costs, slight pollution, and no tracked storage cap; useful recovery remains required. It does not permit generic solid-coproduct deletion. See [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md) and [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md).

## Prioritized Confirmed Gap Ledger

### G01 - Complete scope and constructable-family dispositions

- **Priority / progression:** High; all gameplay phases. Resolve version-dependent scope before work-plan Phase 4 closes.
- **Evidence:** The [Infrastructure checklist](infrastructure.md) and [product-family checklist](intermediate-products.md) identify missing dispositions for general assembly, rail/signals, support entities, armor, modules, vehicles, and other families. Candidate counts mix families, entities, tiers, and items; [Technical Architecture](technical-architecture.md) leaves Factorio version and DLC open.
- **Required evidence:** Select the game version and DLC; classify each relevant family as Core, vanilla retained/modified/replaced, extension, unresolved, or out of scope. Identify its role and owning document, separating placeable entities from non-building products. Do not prescribe a count or invent variants. **Owners:** Infrastructure and Intermediate Products, with each system owner; version choice in Technical Architecture.

### G02 - Connect required construction materials to credible supplies

- **Priority / progression:** High; beginning with gameplay Phase 1, then all later constructables. Work-plan Phases 4-5.
- **Evidence:** Infrastructure construction materials are demand hypotheses rather than a verified bill of materials. [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md) requires basic Phase 1 refractories without Phase 1 aluminum, bauxite-derived alumina, or alumina-bearing construction materials; the precise product and supply path are not established. The early flux/lime and later ceramic, seal, insulation, and component demands are not a completed catalog.
- **Required evidence:** For every selected construction capability, identify a phase-compatible material family, an upstream source/process, and a real consumer or justified terminal role. In particular, show a credible basic refractory path before it is first needed. Do not require a separate item for every brick, gasket, grade, or construction detail. **Owners:** Infrastructure, Intermediate Products, Minerals and Refining, and Chemical Processes.

### G03 - Demonstrate the first-Core and semiconductor dependency path

- **Priority / progression:** High; gameplay Phase 2 through first Core. Work-plan Phase 5 capability coverage; technology dependencies in Phase 8.
- **Evidence:** [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0020](adrs/ADR-0020-seven-distinct-domain-pack-tiers.md), and [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) select six bridges, their facilities, four pre-Core tiers per domain, and the Array gate. [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) and [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md) require conventional packaged CPUs and contemporary cleanroom capability before first Core. Routes, supporting inputs, and gates are not fully traced.
- **Required evidence:** Show an acyclic capability path from accessible starting resources through all six T2b2 domains, the Array, and standard CPU material families. First semiconductor-vacuum equipment must not require chips made using itself. Fission, enriched fuel, post-Core SFQ compute, and a semiconductor-grade alignment mechanism must not become first-Core prerequisites. **Owners:** Research and Progression, Intermediate Products, Minerals and Refining, Chemical Processes, Infrastructure, and Endgame Vision.

### G04 - Prove PTFE bootstrap and usable fission back ends

- **Priority / progression:** High; gameplay Phase 2 when the relevant capabilities are used. Work-plan Phases 4-5; detailed balances in Phase 7.
- **Evidence:** [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md) selects the first-PTFE boundary, and [ADR-0065](adrs/ADR-0065-practical-phase-2-fission-readiness.md) requires usable, normally automated first fission with Phase 2 hafnium forming. Recovery and terminal roles are selected in [ADR-0066](adrs/ADR-0066-select-phase-2-nuclear-recovery-flows.md) and ADR-0068, but chemistry, equipment split, and values remain open.
- **Required evidence:** Trace fluorspar through reagent/monomer preparation, baseline polymerization, and finished construction-grade PTFE without PTFE-built startup equipment or nuclear HF. For each chosen fission route, show fuel/rod and absorber supply, ordinary-shielded startup, recovery, conditioning, and disposal by first output. Test saturated shielding demand and thorium operation without ongoing uranium supply. Fission remains optional for first Core; do not make superconductors, later specialist machines, or a blackout-safety item mandatory. **Owners:** Chemical Processes, Minerals and Refining, Infrastructure, Intermediate Products, Power System, and Research and Progression.

### G05 - Cover Phase 2 PV and LFP supply

- **Priority / progression:** High; gameplay Phase 2. Work-plan Phase 5 coverage; recipes and balance later.
- **Evidence:** [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md), [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md), and [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) select a dedicated PV route and LFP storage, with starting-region lithium-bearing brine and apatite-rich phosphorite and an alternative spodumene feed. Recovery, cell manufacture, and the PV-specific process remain open.
- **Required evidence:** Show credible, accessible silicon-to-PV and lithium/phosphate-to-LFP cell/pack capability paths, without depending on CPU wafer/chip fabrication or post-Core-only capability for initial PV. Do not make cobalt or nickel mandatory for initial LFP. **Owners:** Power System, Minerals and Refining, Chemical Processes, Intermediate Products, Infrastructure, and World Generation.

### G06 - Demonstrate meaningful process alternatives

- **Priority / progression:** High; gameplay Phases 1-3. Work-plan Phase 5 capability evidence; route quantities and tradeoffs in Phase 7.
- **Evidence:** The [north star](mod-overview.md) calls for alternatives for major products when they create meaningful choices. [Minerals and Refining](minerals-and-refining.md) requires a baseline and discoverable advanced route for each polymineral feed, but its routes and [steel pathways](intermediate-products.md) remain candidates.
- **Required evidence:** Select representative major outputs and show a straightforward route plus a justified alternative where appropriate. Compare at least resource/feed availability, coproducts and pollution, and infrastructure requirements; power, space, and throughput can support the comparison. Candidate examples are blast-furnace versus hydrogen direct-reduction steel and brine versus spodumene lithium, not pre-approved final recipes. A universal two-route rule for every deposit is not selected. **Owners:** Minerals and Refining, Chemical Processes, Intermediate Products, and Infrastructure.

### G07 - Trace coproduct handling under uneven demand

- **Priority / progression:** High; by the first output of each modeled stream, across all gameplay phases. Work-plan Phase 5 coverage and Phase 7 balance.
- **Evidence:** Chlor-alkali supplies hydrogen and chlorine for HCl, while a useful NaOH consumer is still open; powered, polluting disposal is permitted. Zircon separation serves independent CPU hafnium, fission absorber, and cladding demands. Nuclear recovery and continuous disposal are selected, but no numerical balance is established. See [Chemical Processes](chemical-processes.md), [Minerals and Refining](minerals-and-refining.md), and [Power System](power-system.md).
- **Required evidence:** Trace useful recovery, bounded buffers, production control, and eligible disposal for each representative output. Test chlor-alkali without a useful NaOH consumer, CPU demand without fission, fission demand without matching CPU demand, and nuclear disposal with no military or depleted-oxide shielding demand. Ordinary solid coproducts do not get a generic voider; nuclear-bearing fractions cannot be released untreated. Phase 5 establishes credible handling; Phase 7 quantifies flows, costs, and pollution. **Owners:** the mineral, chemical, power, infrastructure, and product owners.

### G08 - Specify discoverable guidance and ordinary diagnostics

- **Priority / progression:** High; gameplay Phase 1 onward. Establish coverage in work-plan Phases 4-5 and link it to eventual research/UI work.
- **Evidence:** [Mod Overview](mod-overview.md) requires knowledge before capability; [Chemical Processes](chemical-processes.md) requires players to see inputs, outputs, coproducts, and known uses. [Infrastructure](infrastructure.md) leaves the exact handbook and machine-UI contract open. No complete guidebook workflow or content pipeline is established.
- **Required evidence:** For a representative new chain, show how the player can find the capability before building it, identify required inputs and coproducts, understand a route tradeoff, and diagnose a blocked output or missing power. Keep optional scientific detail distinguishable from gameplay abstractions. Native power-network feedback remains the Core baseline under [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md); no crafted diagnostic tool or custom grid system is implied. **Owners:** Mod Overview, Infrastructure, Chemical Processes, and Research and Progression.

### G09 - Validate geographic access without eliminating discovery

- **Priority / progression:** High; starting region through gameplay Phase 2. Work-plan Phase 5 checks capability access; generated-map feasibility and tuning remain subsequent world-generation validation.
- **Evidence:** [World Generation](map-world-generation.md) selects or records deadlines for CPU, LFP, fluorspar/PTFE, fission, rhenium, and niobium-tin feeds, but placement, quantities, travel distances, and generation feasibility are open.
- **Required evidence:** Trace each selected feed to its earliest required use without its own locked facility or Core, preserving starting-region guarantees only where selected. Later test representative generated worlds and settings for reachability, recognizable geological clues, and transport demands; do not treat untested distance examples as hard requirements. **Owners:** World Generation and Minerals and Refining, with affected product and research owners.

### G10 - Map research and simulation capabilities to player-visible milestones

- **Priority / progression:** High for the accepted first-Core boundary; medium for unselected post-Core/endgame details. Work-plan Phase 5 establishes capability coverage, with specific research gates in Phase 8.
- **Evidence:** [Research and Progression](research-progression.md) selects the domain tiers and first-Core threshold but leaves exact recipes, technology assignments, and later Core gates open. [Endgame Vision](endgame-vision.md) proposes a distributed network and model/data loop, while its required versus optional facilities and final milestone remain unresolved.
- **Required evidence:** Show how the accepted domain stages and bridge facilities connect to first Core, and decide required versus optional endpoint capabilities before the coverage gate. After scope is selected, trace the simulation/research loop and player-facing milestones without inventing a victory condition or additional research items. Test whether meaningful intermediate payoffs and available choices support the long-form ambition. **Owners:** Research and Progression and Endgame Vision, with Infrastructure and Intermediate Products.

## Open Decisions and Inventory Discrepancies

| ID | Disposition | Question and deadline |
|---|---|---|
| Q01 | Needs a decision | Select the target Factorio version and any required DLC before closing work-plan Phase 4. Until then, vanilla retention, modification, and replacement claims are version-dependent. |
| Q02 | Needs a decision | Bound Core military scope and reconcile the vanilla-enemy proposal with pollution-adapted armored variants before Phase 4 closes. [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) and [ADR-0013](adrs/ADR-0013-military-pressure-model.md) remain proposed; ammunition capability and sustained defense power are accepted principles, not an approved roster. |
| Q03 | Needs a decision | Classify powered rails, train treatment, dispatch, and family-specific tiering before Phase 4 closes. Basic balance must not depend on custom code or an unapproved extension. |
| Q04 | Needs a decision | Decide required versus optional distributed-network capabilities and victory versus continued sandbox before the Phase 5 coverage gate; higher Core gates and exact technology assignments remain for Phase 8. |
| Q05 | Needs a decision | Decide which material variants, tools, maintenance loops, safety/environmental facilities, and additional research items earn distinct gameplay roles. Their presence in an older report or a candidate inventory is not approval. |
| Q06 | Needs a decision | Determine how to present near-future and speculative milestones through the journey. The existing Phase 2 superconducting wire and contemporary chipmaking already provide advanced capabilities; a fixed sci-fi percentage, specific hour, or early fictional material has not been selected. |
| Q07 | Conflict | [Infrastructure](infrastructure.md) contains broad candidate statements that all preparation, chemical, fluid, or polymer machines must be tiered, while its equipment principles and [plan](plan.md) leave family-specific tiering open. Reconcile the candidate rows during Phase 4; do not count five tiers per family by assumption. |
| Q08 | Confirmed gap | Candidate research/compute rows in [Infrastructure](infrastructure.md) section 17 describe early polysilicon-based Core hardware without explicitly mapping the selected packaged CPU supply. [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) requires conventional packaged CPUs for initial Core compute. Treat the rows as incomplete construction hypotheses and reconcile them in Phase 4, not as an alternative accepted Core path. |
| Q09 | Confirmed gap | The candidate blast-furnace family in [Infrastructure](infrastructure.md) spans Phases 1-2, while its construction-material summary lists alumina refractory without a tier or phase distinction. Interpreting that material as a Phase 1 requirement would conflict with ADR-0021. Clarify the candidate demand in Phase 4 and trace Phase 1 basic refractory under G02; no blast-furnace recipe is selected by this report. |

## Disposition of Every Earlier Gap Recommendation

The following rows cover the domain recommendations in sections 2A-2D of the [earlier report](gap-analysis-report-11-11-26.md), its priority and structural recommendations in sections 3-5, and the named appendix candidates. Repeated items are grouped by their original family; a grouped **needs a decision** disposition applies to each listed candidate unless the row identifies an already selected or covered role. No listed example becomes a required product merely by appearing here.

| ID / earlier recommendation | Disposition | Evidence and follow-up |
|---|---|---|
| L01 - Two routes for every deposit (§2A) | Conflict | Multiple routes must earn meaningful tradeoffs; the current explicit baseline-plus-advanced rule is for **polymineral** feeds, not every deposit. See G06. |
| L02 - Residue/recovery capability (§2A) | Already covered | A residue-recovery route pattern, tailings processing, metal recovery, and nuclear recovery/conditioning capabilities are present as selected roles or candidates. Their complete assignments and balances remain open; see G04 and G07. |
| L03 - Add ion-exchange skid, precious-metal electrowinning, acid regeneration, and activated-carbon column; expand to eight machines (§2A) | Needs a decision | Some operations and media are already candidate concepts. Decide equipment allocation only for selected routes; eight entities are not a requirement. |
| L04 - Flux/basic refractory supply (§2A, §2B) | Confirmed gap | Early basic refractory capability and a phase-compatible path need coverage; lime and construction roles already exist as concepts. Do not require alumina-bearing construction materials in Phase 1. See G02. |
| L05 - Firebrick clay, silicate refractory bricks, magnesia-carbon bricks, alumina pellets, SiC bricks, zirconia tiles, fused-silica sheets, and mullite fiber (§2A, §2B, appendix) | Needs a decision | Evaluate each actual use and supply phase; some may be shared materials or direct inputs rather than distinct products. No exact brick or ceramic roster is selected. |
| L06 - Gas and chemical product category (§2A) | Already covered | [Chemical Processes](chemical-processes.md) indexes gases and reagents; the product checklist cross-references them. Individual forms, uses, and handling still require coverage. |
| L07 - Compressed hydrogen, liquid oxygen, pressurized nitrogen, chlorine cylinders, SO2 storage, and producer gas (§2A, appendix) | Needs a decision | The gases or gas families appear as candidates or selected flows, but packaging each as an item is not established. Producer gas is not a direct boiler/engine fuel under ADR-0019. |
| L08 - Expand the alloy catalog to about 20 (§2B) | Conflict | [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md) derives product scope from capabilities and demand, not a numeric target. Nine listed candidates are not proof of either sufficient or insufficient depth. |
| L09 - Maraging, Hastelloy/625-like, Inconel, duplex, HSS, D2, M2, 17-4 PH, aluminum 7075, and copper-molybdenum heat-spreader variants (§2B, appendix) | Needs a decision | General tool steel, stainless, Invar, titanium, and aluminum alloy families already appear as candidates. Retain a distinct grade only where it creates a real capability, tradeoff, or consumer. |
| L10 - Catalyst materials as an industrial concept (§2B) | Already covered | The chemistry owner already describes catalyst inputs/components, different effects, and possible regeneration or replacement; named candidates appear in its reaction registry. Rhenium catalyst is a selected bridge. |
| L11 - Every reactor needs a consumable/replaceable catalyst (§2B, §3) | Conflict | A candidate fixed-bed reactor is catalyst-specific; this does not establish a catalyst requirement for every reactor or consumption for every catalyst. Replacement depends on the selected process. |
| L12 - Platinum/alumina, palladium/carbon, supported nickel, vanadium pentoxide, zeolite, activated carbon, Raney nickel, and copper-chromium catalysts (§2B, appendix) | Needs a decision | Some already appear in the chemistry registry as catalysts or support candidates. Distinct item identities and lifecycles must be justified by selected processes, not the proposed count. |
| L13 - Precision optics needed only in Phase 3 or later (§2B) | Conflict | Contemporary cleanroom and advanced chipmaking belong in Phase 2 under ADR-0026. That boundary does not select any particular optical part or recipe. |
| L14 - Quartz lens blanks, sapphire windows, germanium IR plates, and UV fused-silica sheets (§2B, appendix) | Needs a decision | Determine actual cleanroom, measurement, or endgame demand and a phase-compatible path; do not assume each component must be a separate item. |
| L15 - LCO, NCA, graphite-anode, and solid-polymer-electrolyte battery products (§2B, appendix) | Needs a decision | Initial Phase 2 storage is LFP, with its feed/access constraints selected; graphite and other cell roles are candidates. Alternative chemistries must earn distinct roles and cannot make cobalt or nickel a first-LFP prerequisite. See G05. |
| L16 - Carbon fiber, E-glass fiber, epoxy laminates, aramid, and basalt fiber (§2B, appendix) | Needs a decision | Polymer and composite process concepts exist, but exact fibers, products, consumers, and phases remain open. Evaluate demand before adding distinct chains. |
| L17 - Personal engineering tools are a blocking prerequisite for machinery (§2C, §3) | Not a gap | The product checklist includes tools and personal equipment, but no evidence requires hand-held tools to operate each machine. Core fission must be normally automated and excludes a dedicated blackout-safety item. |
| L18 - Caliper, dosimeter, welding helmet, multimeter, calibration kit, pressure gauge, insulation tester, thermal camera, alignment laser, and inspection probe (§2C, appendix) | Needs a decision | Consider a distinct item only for a clear player interaction; ordinary UI feedback may meet the need. The first-Core alignment mechanism is required but its exact hardware is not selected; custom grid diagnostics remain outside Core. |
| L19 - Pollution and environmental handling are absent (§2C) | Already covered | Gas flare, liquid clarifier, recovery, and nuclear conditioning/disposal roles are in the current design. Their operation and exact equipment remain to be designed. |
| L20 - Fume hood, containment flooring, explosion vents, and dust suppression (§2C, appendix) | Needs a decision | These require a justified pollution, leak, explosion, or particulate mechanic and a role distinct from existing handling; those mechanics and entities are not selected. |
| L21 - Prospecting and sampling capability (§2C) | Already covered | World Generation describes geological clues and prospecting; Infrastructure lists a candidate prospect scanner. Their behavior and coverage remain open. |
| L22 - Core-sample drill, specimen cabinet, and field spectrometer (§2C, appendix) | Needs a decision | Decide whether sampling or a portable instrument improves prospecting; a specimen display is a nonessential presentation idea, not an approved Core or extension requirement. |
| L23 - Aerogel blankets, cryogenic panels, desiccant beds, and vacuum-insulated cores (§2C, appendix) | Needs a decision | Thermal/cryogenic insulation is a candidate construction demand. Exact material, item form, route, and use must follow the selected facility rather than a four-item target. |
| L24 - A Phase 2 PTFE construction-seal/lining capability (§2C) | Confirmed gap | The role and PTFE-free bootstrap are selected, but the complete source-to-finished-construction-product path is not yet demonstrated. See G04. |
| L25 - PTFE tape, copper gasket blanks, compressed graphite sheets, and FKM seal kits (§2C, appendix) | Needs a decision | These exact forms are not selected. A required construction-grade PTFE role does not automatically require separate tape, gasket, or every pipe-connection item. |
| L26 - Hydraulic fluid, industrial lubricant, cooling oil, and synthetic gear oil (§2C) | Needs a decision | Check existing vanilla scope and actual machine/service requirements first. Machine wear and a separate lubricant for every service are not selected Core mechanics. |
| L27 - Research logs, cross-domain work, and simulation-data concepts (§2D) | Already covered | Seven distinct domain-pack tiers per domain include observation, cross-reference, and post-Core simulation-related stages; research/data product categories also exist. Exact names, ingredients, and mechanics remain open. |
| L28 - Additional raw logs, cross-domain analysis reports, and simulation validation datasets (§2D) | Needs a decision | Avoid automatically adding three more item layers on top of the selected domain tiers. Decide only if an independently useful research interaction or output needs representation. |
| L29 - Crafted engineering manuals, process handbooks, and journal access as research/handbook gates (§2D, §4) | Needs a decision | A handbook and knowledge-before-capability are current direction; physical manual items and their gating are not. Any selected approach must still show required process information before the corresponding step can be built. |
| L30 - Research from disassembled scrap (§2D) | Not a gap | Recovery/recycling and research from scrapped machinery are different capabilities. No current requirement establishes reverse-engineering research; it remains an optional idea, not a prerequisite. |
| L31 - Six bridge products and one-to-one facility mappings (§4) | Already covered | ADR-0017 and ADR-0022 select six, including rhenium, with explicit mappings. No additional bridge is selected; an absolute ban on future additions is not established. Their routes and supporting inputs remain to be demonstrated under G03. |
| L32 - Add more Nb3Sn consumers (§4) | Needs a decision | The bridge and superconducting capability are selected; extra consumers must have genuine demand and phase-compatible supply. Do not create consumers merely to increase material use counts. |
| L33 - Keep 70-80 machine types / target about 400 tiers (§1, §4) | Not a gap | Neither Prometheus's candidate inventory nor reference-mod figures are normalized. No measured performance budget or comparable shortfall establishes these targets. |
| L34 - Assume about five tiers per machine (§1, §4) | Conflict | Family tiering and counts are unresolved; single-tier specialist candidates exist. See Q07. |
| L35 - Target 45 pure materials, 70-75 intermediates, fixed specialist counts, or 60%/85% of another mod's depth (§4-5) | Conflict | Product counts and the earlier percentages do not establish capability or depth; ADR-0006 expressly rejects a fixed intermediate target. The new percentages above are subjective readiness indices, not measured depth or catalog targets. |
| L36 - Every new product must have a consumer and disposal must be avoided (§4) | Conflict | Required products need a legitimate use **or justified terminal role**. Gas/liquid disposal is explicitly allowed with power and pollution; the nuclear-only conditioned-solid exception also applies. Do not invent consumers just to satisfy a numeric rule. |
| L37 - Knowledge before capability and understandable material roles (§4) | Already covered | This is a current pillar, with the guidance-contract gap tracked in G08. A crafted-manual mechanic is a separate open choice, not implied by the pillar. |
| L38 - Add a materials-engineering layer of catalysts, tools, gaskets, insulation, and alloys (§4-5) | Needs a decision | Existing candidate families and selected PTFE roles already provide material-engineering opportunities. Retain each further layer only if it creates a useful industrial or player capability, not to imitate GTNH's granularity. |

The former report's “must-add before Phase C,” “should-add before Phase D,” and appendix priorities are repetitions of the families above; those legacy phase labels and item totals are not current gates.

## Disposition of Market-Report Recommendations

| Recommendation | Disposition | Current assessment |
|---|---|---|
| Introduce advanced or futuristic milestones earlier; aim for roughly two-thirds sci-fi | Needs a decision | The pacing question is worth testing, but the percentage and predicted retention benefit are unsupported. Phase 2 already includes selected Nb3Sn bridge wire, fission, and contemporary semiconductor capability; whether to add earlier speculative capabilities is open. Do not turn superconducting wire into an assumed grid replacement or move accepted first-Core boundaries. |
| Make military/expansion pressure meaningful | Needs a decision | The concern is relevant, but the roster, enemy/pressure conflict, and Core/extension scope remain open. Bound them before work-plan Phase 4 closes rather than silently accepting the market report's proposed mechanics. |
| Add a lightweight trade/economy, or use rare regional resources | Conflict for a new economy; already covered for regional-resource intent | The current world design has no trade/economy system and already intends geology-led regional exploration. Validate access and logistics under G09; neither a market nor interplanetary trade is required. |
| Prioritize capability awareness over recipe transparency | Conflict if it hides required process information | The current handbook and UI direction includes inputs, outputs, coproducts, known uses, and eligibility before construction. A staged writing pipeline and optional deeper explanations remain useful open implementation questions; see G08. |
| Use predicted audience size, abandonment rates, and 300-600-hour comparisons as viability evidence | Not a gap | These figures are hypotheses without recorded supporting methodology. The 300+ hour ambition and Space Exploration author's playtime estimate do not establish actual pacing or market demand. |

## Follow-up Validation Cases

These are proposed checks for later phases, not tests already run and not new recipe requirements.

| Case | Pass evidence to develop | Owning work |
|---|---|---|
| First Core | A capability graph reaches all six T2b2 tiers, the Array, and conventional packaged CPU supply from available feeds with no self-dependency, first-vacuum/chip loop, or required fission chain. | Phase 5 capability coverage; Phase 8 technology graph. |
| PTFE and fission startup | First finished PTFE is available without PTFE equipment or nuclear HF; selected fission can start from ordinary power and shielding and has automated fuel handling and eligible recovery/disposal at first output. | Phase 4 equipment scope; Phase 5 coverage; Phase 7 numerical balance. |
| Unequal coproduct demand | Trace chlor-alkali with no useful NaOH demand, CPU without fission, fission without matching CPU consumption, and nuclear operation without depleted-oxide shielding or ammunition demand. Each modeled output has an allowed handling path. | Phase 5 coverage and Phase 7 balance. |
| PV/LFP alternatives | Show a pre-Core dedicated PV path and an LFP path using starting-region brine and phosphate; assess the separate spodumene alternative without requiring both lithium sources. | Phase 5 coverage; Phase 7 routes and balance. |
| Meaningful process choice | For candidate steel and lithium examples, document available inputs, outputs, coproducts, infrastructure, and at least one meaningful tradeoff; verify baseline and advanced options for each retained polymineral feed. | Phase 5 capability coverage; Phase 7 recipes and balance. |
| Discovery and onboarding | With selected resource-access rules, follow a representative player from finding a feed through understanding the next process and diagnosing a blocked output. Later test generated worlds and player comprehension; do not invent pass rates or travel-time targets now. | Phase 5 capability coverage, then map/UI and playtest validation. |
| Progression payoff | Once endgame scope and gates are chosen, trace visible intermediate domain milestones and the required network loop; assess pacing through play rather than counting packs or imposing a sci-fi percentage. | Phase 5 coverage, Phase 8 research, later playtesting. |
| 300+ hour experience | Trace representative journeys, then record milestone times, player choices, repetition, comprehension, and feedback in playable versions. Define the player profile and completion criterion; use stated comparator versions and settings before comparing experiences. | Phase 5 coverage, Phases 7-8 balance and research, later playtesting. |

## Work-Plan Handoff

The Phase 3 ledger is the frozen analysis baseline for work-plan Phase 4, not approval of individual recommendations or proof of a playable mod. Phase 4 should align infrastructure and resolve its required scope choices; Phase 5 should establish the canonical coverage ledger without prematurely enumerating products. Phases 6-8 then define approved items, recipes/balances, and technologies. A new recommendation or a changed decision reopens only the affected findings and dependencies.
