# Project Prometheus Documentation Map

*Status: Phase 1 migration in progress*
*Last updated: 2026-11-12*

This map assigns one current-state owner per design area. Reports, summaries, and the plan support the work but do not replace the owning design document. The map reflects intended ownership; it does not certify that every existing statement is current or internally consistent.

## Current Repository Documents

| Document | Primary ownership / role | Authority and migration notes |
|---|---|---|
| [README.md](README.md) | Project landing page and navigation | Summary only; keep aligned with `mod-overview.md`, not an independent detailed design source. |
| [mod-overview.md](mod-overview.md) | North star, pillars, global scope, guardrails, and cross-domain open-work queue | Owns cross-cutting direction. Detailed system behavior belongs to domain owners below. |
| [plan.md](plan.md) | Work sequence, phase outputs, gates, and checkpoints | Process roadmap only; not a domain specification or decision history. |
| [technical-architecture.md](technical-architecture.md) | Modpack deployment structure, dependencies, and technical/performance constraints | Owns technical architecture; align its claims with approved scope and domain designs. |
| [map-world-generation.md](map-world-generation.md) | Terrain, biome/resource placement, exploration, and world-generation behavior | Phase 1 pilot converted to current-state design on 2026-11-12; see [migration map](migration-map.md) and linked ADRs. Pilot review is pending. |
| [minerals-and-refining.md](minerals-and-refining.md) | Deposit/feed catalog, recovery assignments, pure materials, and refining routes | Current-state structure clarified on 2026-11-12; candidate inventories remain provisional. No standalone ADR extracted from the current draft. |
| [chemical-processes.md](chemical-processes.md) | Chemical products, reactions, process families, and reagents | Current candidate design clarified on 2026-11-12; no historical decision log extracted. |
| [intermediate-products.md](intermediate-products.md) | Cross-domain catalog of non-building product identities, roles, uses, and candidate pathways; includes a Factorio-style product-family completeness checklist | Category scope is recorded in [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md); capability-based catalog size in [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md); the committed rhenium selection in [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md). Placeable entities and their construction hypotheses remain with Infrastructure. |
| [infrastructure.md](infrastructure.md) | Candidate machine/building/infrastructure inventory and construction-demand hypotheses | Phase 1 migration complete; candidate inventory and family checklist retained. The vanilla grid plus compatible tiered poles is accepted in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md); exact pole and construction mappings remain provisional for Phase 3, including the fission/fusion phase mismatch with Power System. |
| [power-system.md](power-system.md) | Core power generation and power-related extension concepts | Phase 1 migration complete; [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) accepts vanilla-grid distribution with tiered poles, and [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md) accepts Hawking as one Phase 4 option. At least one alternative route, production design, generator-phase alignment, and diagnostics/stabilization scope remain open. |
| [logistics-system.md](logistics-system.md) | Physical transport and information-logistics progression | Phase 1 migration complete; vision and transport details remain candidate proposals, with no dated decision log extracted. Powered rails remain unapproved; custom voltage/loss mechanics are extension-only candidates. The missing machine-systems reference remains recorded below. |
| [military-system.md](military-system.md) | Military pressure, defense behavior, and military product-chain requirements | Phase 1 migration complete; decision outcomes are recorded in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) through [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md): ADR-0012 remains proposed, ADR-0014/0015 principles are accepted, and ADR-0016 rejects military drones. Ammo counts, enemy-variant conflicts, turret scope, and balance values remain open. |
| [research-progression.md](research-progression.md) | Research phases, research mechanics, and technology gating | Owns research progression; endgame narrative/structure is owned by `endgame-vision.md`. |
| [endgame-vision.md](endgame-vision.md) | Planetary simulation endgame concept, facilities, and victory direction | Owns the endgame vision and facility concepts; detailed research gating remains in `research-progression.md`. |
| [gap-analysis-report-11-11-26.md](gap-analysis-report-11-11-26.md) | Comparative gap evidence and recommendations | Evidence only. Each recommendation requires a disposition in the planned gap audit before affecting design. |
| [market-research-report.md](market-research-report.md) | Market comparisons and recommendations | Evidence only; recommendations do not override the north star or become requirements automatically. |

## Product-Tree Ownership Boundaries

- World placement and availability: `map-world-generation.md`.
- Extracted feeds, recovery, pure materials, refining: `minerals-and-refining.md`.
- Reagents, reactions, chemical products, and coproduct chemistry: `chemical-processes.md`.
- Non-building product identities, roles, consumer links, and candidate pathways: `intermediate-products.md`; placeable entities and construction-demand hypotheses: `infrastructure.md`.
- Buildable infrastructure and construction demand: `infrastructure.md`.
- Power, logistics, military, endgame, and research behavior: their respective domain owners in the table.
- Cross-domain intent and open items: `mod-overview.md`; detailed resolutions belong in the affected domain owner and, when significant, a linked ADR.
- Complete coverage: `product-coverage-ledger.md` (to be created in Phase 4).
- Migration provenance and content mapping: [migration-map.md](migration-map.md); this is a process record, not a competing domain design source.

## References Requiring Reconciliation

The current documents link to `machine-systems.md`, `session-plan.md`, and `mineral-catalog.md`, none of which is present in the Phase 0 root-level Markdown inventory. Do not assume those files exist or silently replace their intended content. Determine whether each reference should be redirected, the referenced design recovered, or the document explicitly marked as deferred during the relevant migration.
