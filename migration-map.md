# Phase 1 Migration Map

*Status: Pilot accepted; Phase 1 migration in progress*
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
| Missing `mineral-catalog.md` reference | Replaced in current-state design by the existing [Minerals and Refining](minerals-and-refining.md) owner. The missing filename remains recorded as a repository reconciliation item in [Documentation Map](documentation-map.md). |
| Reference to machine-system ownership | Current design names only existing domain owners; the missing `machine-systems.md` file remains recorded in [Documentation Map](documentation-map.md) for reconciliation. |

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
| [Intermediate Products](intermediate-products.md) | The document now defines the cross-domain non-building product scope and a Factorio-style family checklist. The committed rhenium selection remains linked to [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md); capability-based catalog size remains in [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md); category-level coverage is recorded in [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md). Candidate endgame facility pathways moved to the Infrastructure inventory; former Phase A2 quantities and assembly proposals remain unapproved in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md). The five-versus-six research-prerequisite count remains open. Missing machine-system references are recorded, not redirected. |

## Infrastructure and Systems Batch

| Source document | Content retained or moved |
|---|---|
| [Infrastructure](infrastructure.md) | The candidate constructable inventory, Factorio-style infrastructure-family checklist, construction-demand hypotheses, and provisional counts remain in the owner document. Core distribution now follows accepted [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md): vanilla grid plus compatible tiered poles; exact pole details remain open. The electrical turret direction remains proposed in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md). The fission/fusion phase mismatch with Power System is explicitly recorded. |
| [Power System](power-system.md) | Accepted [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) retains the vanilla grid and adds tiered poles. [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md) accepts Hawking as one Phase 4 option and requires at least one alternative Phase 3/4 route. Custom voltage, transmission-loss, and grid-infrastructure details remain optional extension candidates; the fusion/Phase 4 boundary, fission/fusion phase mismatch, and diagnostics/stabilization scope remain open. |
| [Logistics System](logistics-system.md) | The transport, bot, and information-logistics vision remains candidate design; no dated decision log was present. Powered rails remain unapproved and their voltage/loss mechanics are extension-only candidates, separate from the accepted core grid direction. The source's missing `machine-systems.md` reference remains recorded in [Documentation Map](documentation-map.md), not silently redirected. |
| [Military System](military-system.md) | Comparative research and decision rationales are preserved in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) through [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md). ADR-0012 remains proposed; ADR-0014 and ADR-0015 are accepted principles; ADR-0016 rejects military drones. Current candidate ammo, turret, power-load, and extension details remain in the owner document; rejected drone roles and supply paths remain in ADR-0016. Ammo type/tier/recipe counts and the vanilla-enemy/armored-variant conflict remain open. |

## Review Gate

The user accepted the world-generation pilot as the migration pattern on 2026-11-12. The following inventory bounds the remaining Phase 1 work; move each document to **Migrated** only after its content has a traceable destination and its cross-references are checked. Proposed ADRs may remain unresolved, provided their status and source provenance are explicit.

| Batch | Document | Phase 1 status |
|---|---|---|
| Pilot | [map-world-generation.md](map-world-generation.md) | Accepted |
| Product-tree inputs | [minerals-and-refining.md](minerals-and-refining.md) | Migrated; candidate catalog preserved, no ADR extracted |
| Product-tree inputs | [chemical-processes.md](chemical-processes.md) | Migrated; candidate registry preserved, no historical ADR extracted |
| Product-tree inputs | [intermediate-products.md](intermediate-products.md) | Migrated; broad non-building scope and category checklist added; candidate facility pathways moved to Infrastructure; ADR-0006 through ADR-0009 linked; prerequisite-count conflict preserved |
| Constructables | [infrastructure.md](infrastructure.md) | Migrated; candidate inventory retained, tiered poles accepted, exact scope and counts open |
| Systems | [power-system.md](power-system.md) | Migrated; core distribution and Hawking option accepted, alternative route and Phase 4 boundary open |
| Systems | [logistics-system.md](logistics-system.md) | Migrated; powered rails and extension voltage/loss model remain open, missing reference flagged |
| Systems | [military-system.md](military-system.md) | Migrated; ADR-0012 proposed, ADR-0014/0015 accepted principles, ADR-0016 rejected; ammo-count and enemy-variant conflicts open |
| Progression | [research-progression.md](research-progression.md) | Not started |
| Progression | [endgame-vision.md](endgame-vision.md) | Not started |
| Cross-domain | [mod-overview.md](mod-overview.md) | Not started |
| Technical architecture | [technical-architecture.md](technical-architecture.md) | Not started |
| Navigation summary | [README.md](README.md) | Reconcile links and summary after design migrations |

The gap-analysis and market-research reports remain evidence documents and are not part of the design/ADR split. [Plan](plan.md), [documentation conventions](documentation-conventions.md), [documentation map](documentation-map.md), [product taxonomy](product-taxonomy.md), and templates are process/reference artifacts rather than domain design documents.
