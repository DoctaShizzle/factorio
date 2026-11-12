# Phase 1 Migration Map

*Status: Phase 1 migration complete*
*Last updated: 2026-11-12*

This map records where source content from Phase 1 design documents was retained or moved. The world-generation pilot mapping is the validated migration pattern; later batches record their current-design destinations, ADRs, and unresolved provenance or conflicts. Unresolved conflicts remain visible rather than being harmonized by assumption.

## Pilot Mapping

| Original source content | Current destination |
|---|---|
| Purpose, world-gen role, scope, and design philosophy | [Map and World Generation](map-world-generation.md), Summary and Purpose/Boundaries |
| No-trade/no-economy principle and player extraction narrative | Current design; decision rationale in [ADR-0002](adrs/ADR-0002-geology-led-exploration.md) |
| Seven key principles | Current design sections for biome availability, clustering, exploration, prospecting, and military pressure; rationales in ADR-0001, ADR-0002, and ADR-0004 |
| Broad biomes, final biome table, coastal hybrid | Current design, Geological Biomes; alternatives and revised candidate scope in [ADR-0001](adrs/ADR-0001-geological-biome-layout.md) |
| Geological adjacency and distance heuristics | Current design, Geological Continuity; discrepancies recorded in [ADR-0001](adrs/ADR-0001-geological-biome-layout.md) and [ADR-0005](adrs/ADR-0005-map-scale-and-discovery-distances.md) |
| Map size recommendations, cluster examples, Phase 1–3 resource progression, and draft progression ranges | Current design, Resource Clustering and Progression / Scale and Geographic Targets; all source values preserved in [ADR-0005](adrs/ADR-0005-map-scale-and-discovery-distances.md) |
| Prospecting options and final hybrid decision | Current design, Prospecting; decision context and options in [ADR-0002](adrs/ADR-0002-geology-led-exploration.md) |
| Oil and water placement | Current design, Oil and Water |
| Light/heavy crude proposal and rejection | Current design, Oil and Water; [ADR-0003](adrs/ADR-0003-single-oil-type.md) |
| Map-edge behavior and its conflict between increasing density and sparse patrols | Current design, Expansion and Military Pressure; conflict and decision in [ADR-0004](adrs/ADR-0004-map-edge-pressure.md) |
| Links to military pressure, material boundaries, and product-catalog work | Current design, Requirements and Dependencies; obsolete gap labels are not treated as current ownership. |
| `mineral-catalog.md` placeholder | No file or historical source was found. Deposit and refining ownership is [Minerals and Refining](minerals-and-refining.md); the placeholder reference is removed. |
| Former Machine Systems content | The user confirmed that Machine Systems was subsumed in [Infrastructure](infrastructure.md). The archived route-to-machine matrix was empty; exact assignments remain deferred to product/process coverage work. |
| `session-plan.md` reference | No file or historical source was found. [Plan](plan.md) is the current work roadmap; no separate design content was available to migrate. |

## Provenance and Preservation Notes

- The source Git history shows the four-core-biome plus coastal-hybrid mapping and resolved decision table were recorded on 2026-11-06.
- The earlier candidate table included river delta/alluvial as a separate area, with placer deposits such as gold, tin, and rare minerals; ADR-0001 preserves that superseded candidate.
- Earlier source text described map-edge density as increasing. ADR-0004 preserves that conflict and the later sparse-patrol resolution.
- The current design and ADR-0005 preserve all distinct resource-distance and map-scale values found in the source. Conflicts are explicitly open for review.
- No recipe, deposit, or progression value was silently promoted from a candidate into a tested implementation requirement.

## Product-Tree Inputs Batch

| Source document | Content retained or moved |
|---|---|
| [Minerals and Refining](minerals-and-refining.md) | Deposit tiers, all deposit and recovery tables, the pure-material inventory, route templates, refining exceptions, balanceability checks, and reference inspirations remain in the owner document. Candidate status and unresolved scope were made explicit. Its current draft had no dated decision log to extract; catalog revisions remain source history, not invented ADRs. |
| [Chemical Products and Processes](chemical-processes.md) | Core chain table, later candidates, chemical index, process/equipment guidance, educational principles, and the full provisional chemical/reaction registry remain in the owner document. The registry remains explicitly unapproved; no dated decision log was present in the current draft. |
| [Intermediate Products](intermediate-products.md) | The document now defines the cross-domain non-building product scope and a Factorio-style family checklist. The user selected six candidate bridge products for the six-domain roster, including the committed rhenium selection in [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md); the count is recorded in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md). Capability-based catalog size remains in [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md); category-level coverage is recorded in [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md). Candidate endgame facility pathways moved to the Infrastructure inventory; former Phase A2 quantities and assembly proposals remain unapproved in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md). Detailed product routes and facility mapping remain open. Candidate machine families are owned by Infrastructure; exact route mappings remain deferred. |

## Infrastructure and Systems Batch

| Source document | Content retained or moved |
|---|---|
| [Infrastructure](infrastructure.md) | The candidate constructable inventory, Factorio-style infrastructure-family checklist, construction-demand hypotheses, and provisional counts remain in the owner document. Core distribution now follows accepted [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md): vanilla grid plus compatible tiered poles; exact pole details remain open. The electrical turret direction remains proposed in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md). Power progression now follows the user's direction: fission in Phase 2 and fusion in Phase 3; fuel-fabrication availability and construction compatibility remain open. |
| [Power System](power-system.md) | Accepted [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) retains the vanilla grid and adds tiered poles. [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md) accepts Hawking as one Phase 4 option. [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) selects at least three Phase 3/4 route identities, adds concentrated solar thermal with storage as an additional Phase 3 route, and selects non-steam conversion families. Custom voltage, transmission-loss, and grid-infrastructure details remain optional extension candidates; detailed materials, fuel chains, performance, research/construction gates, and diagnostics/stabilization scope remain open. |
| [Logistics System](logistics-system.md) | The transport, bot, and information-logistics vision remains candidate design; no dated decision log was present. Powered rails remain unapproved and their voltage/loss mechanics are extension-only candidates, separate from the accepted core grid direction. Candidate placeable logistics entities are owned by Infrastructure; detailed logistics behavior remains here. |
| [Military System](military-system.md) | Comparative research and decision rationales are preserved in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) through [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md). ADR-0012 remains proposed; ADR-0014 and ADR-0015 are accepted principles; ADR-0016 rejects military drones. Current candidate ammo, turret, power-load, and extension details remain in the owner document; rejected drone roles and supply paths remain in ADR-0016. Ammo type/tier/recipe counts and the vanilla-enemy/armored-variant conflict remain open. |

## Progression and Cross-Domain Batch

| Source document | Content retained or moved |
|---|---|
| [Research and Progression](research-progression.md) | The six-domain roster remains the baseline. The first Core construction gate is selected: all six domains at T2b2 plus the Unified Metrology Reference Array (convergence item), recorded in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md). Six bridge products including rhenium are selected by count; facility mapping, Core Level 2 gate, pack totals, technology assignments, and playtime remain open. Hawking as one accepted Phase 4 option and the need for alternatives link to [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md). |
| [Endgame Vision](endgame-vision.md) | The planetary-simulation direction and candidate facility/model details are retained. The selected first-Core gate is all six domains at T2b2 plus the Unified Metrology Reference Array, as recorded in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md); higher Core-level gates remain open. Earlier “design locked” wording is clarified as unlinked source language, and the stale five-facility source reference is identified as historical. Former Phase A2 quantities remain in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md). |
| [Mod Overview](mod-overview.md) | Cross-domain intent, the working queue, and domain ownership links are retained and aligned with the living [plan](plan.md). Timing and chemistry-performance figures are identified as estimates or hypotheses. |
| [Technical Architecture](technical-architecture.md) | The deployment, dependency, count, and performance proposals are retained but marked unverified; they are not hard limits. Core power distribution follows accepted [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md). No dated architecture decision log was present. |

## Review Gate

The user accepted the world-generation pilot as the migration pattern on 2026-11-12. Every manifest document now has a traceable current-state destination or an explicit missing-source disposition; open proposals and conflicts remain labeled and linked to their owners. Proposed ADRs may remain unresolved when their status and provenance are explicit.

| Batch | Document | Phase 1 status |
|---|---|---|
| Pilot | [map-world-generation.md](map-world-generation.md) | Accepted |
| Product-tree inputs | [minerals-and-refining.md](minerals-and-refining.md) | Migrated; candidate catalog preserved, no ADR extracted |
| Product-tree inputs | [chemical-processes.md](chemical-processes.md) | Migrated; candidate registry preserved, no historical ADR extracted |
| Product-tree inputs | [intermediate-products.md](intermediate-products.md) | Migrated; broad non-building scope and category checklist added; candidate facility pathways moved to Infrastructure; ADR-0006 through ADR-0009 linked; prerequisite-count conflict preserved |
| Constructables | [infrastructure.md](infrastructure.md) | Migrated; candidate inventory retained, tiered poles accepted, exact scope and counts open |
| Systems | [power-system.md](power-system.md) | Migrated; core distribution and Hawking option accepted, alternative route and Phase 4 boundary open |
| Systems | [logistics-system.md](logistics-system.md) | Migrated; powered rails and extension voltage/loss model remain open; placeable families owned by Infrastructure |
| Systems | [military-system.md](military-system.md) | Migrated; ADR-0012 proposed, ADR-0014/0015 accepted principles, ADR-0016 rejected; ammo-count and enemy-variant conflicts open |
| Progression | [research-progression.md](research-progression.md) | Migrated; proposal status and conflicting gates, counts, and estimates are explicit |
| Progression | [endgame-vision.md](endgame-vision.md) | Migrated; planetary simulation direction retained, detailed facilities and gates remain proposals |
| Cross-domain | [mod-overview.md](mod-overview.md) | Migrated; work queue and design direction aligned with the living plan and current owners |
| Technical architecture | [technical-architecture.md](technical-architecture.md) | Migrated; deployment, dependency, count, and performance claims labeled as unverified proposals |
| Navigation summary | [README.md](README.md) | Reconciled with current owners, accepted decisions, and Phase 1 status |

The gap-analysis and market-research reports remain evidence documents and are not part of the design/ADR split. [Plan](plan.md), [documentation conventions](documentation-conventions.md), [documentation map](documentation-map.md), [product taxonomy](product-taxonomy.md), and templates are process/reference artifacts rather than domain design documents.
