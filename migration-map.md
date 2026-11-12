# Phase 1 Migration Map

*Status: Pilot accepted; Phase 1 migration in progress*
*Last updated: 2026-11-12*

This map records where content from the original [Map and World Generation](map-world-generation.md) draft was retained or moved. The source document's Git history contains an earlier candidate-biome table and earlier open-decision wording; those are explicitly preserved below and in the ADRs. Unresolved conflicts remain visible rather than being harmonized by assumption.

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

## Review Gate

The user accepted the world-generation pilot as the migration pattern on 2026-11-12. The following inventory bounds the remaining Phase 1 work; move each document to **Migrated** only after its content has a traceable destination and its cross-references are checked.

| Batch | Document | Phase 1 status |
|---|---|---|
| Pilot | [map-world-generation.md](map-world-generation.md) | Accepted |
| Product-tree inputs | [minerals-and-refining.md](minerals-and-refining.md) | Not started |
| Product-tree inputs | [chemical-processes.md](chemical-processes.md) | Not started |
| Product-tree inputs | [intermediate-products.md](intermediate-products.md) | Not started |
| Constructables | [infrastructure.md](infrastructure.md) | Not started |
| Systems | [power-system.md](power-system.md) | Not started |
| Systems | [logistics-system.md](logistics-system.md) | Not started |
| Systems | [military-system.md](military-system.md) | Not started |
| Progression | [research-progression.md](research-progression.md) | Not started |
| Progression | [endgame-vision.md](endgame-vision.md) | Not started |
| Cross-domain | [mod-overview.md](mod-overview.md) | Not started |
| Technical architecture | [technical-architecture.md](technical-architecture.md) | Not started |
| Navigation summary | [README.md](README.md) | Reconcile links and summary after design migrations |

The gap-analysis and market-research reports remain evidence documents and are not part of the design/ADR split. [Plan](plan.md), [documentation conventions](documentation-conventions.md), [documentation map](documentation-map.md), [product taxonomy](product-taxonomy.md), and templates are process/reference artifacts rather than domain design documents.
