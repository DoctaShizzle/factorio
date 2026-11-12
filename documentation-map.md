# Project Prometheus Documentation Map

*Status: Phase 1 migration complete*
*Last updated: 2026-11-12*

This map assigns one current-state owner per design area. Reports, summaries, and the plan support the work but do not replace the owning design document. The map reflects intended ownership; it does not certify that every existing statement is current or internally consistent.

## Current Repository Documents

| Document | Primary ownership / role | Authority and migration notes |
|---|---|---|
| [README.md](README.md) | Project landing page and navigation | Summary only; keep aligned with `mod-overview.md`, not an independent detailed design source. |
| [mod-overview.md](mod-overview.md) | North star, pillars, global scope, guardrails, and cross-domain open-work queue | Owns cross-cutting direction. Detailed system behavior belongs to domain owners below. |
| [plan.md](plan.md) | Work sequence, phase outputs, gates, and checkpoints | Process roadmap only; not a domain specification or decision history. |
| [technical-architecture.md](technical-architecture.md) | Candidate modpack deployment structure, dependencies, and technical/performance hypotheses | Owns technical architecture. Packaging, dependency, count, and performance claims remain proposals or unvalidated estimates. |
| [map-world-generation.md](map-world-generation.md) | Terrain, biome/resource placement, exploration, and world-generation behavior | Phase 1 pilot accepted by the user on 2026-11-12; see [migration map](migration-map.md) and linked ADRs. |
| [minerals-and-refining.md](minerals-and-refining.md) | Deposit/feed catalog, recovery assignments, pure materials, and refining routes | Current-state structure clarified on 2026-11-12; candidate inventories remain provisional. No standalone ADR extracted from the current draft. |
| [chemical-processes.md](chemical-processes.md) | Chemical products, reactions, process families, and reagents | Current candidate design clarified on 2026-11-12; no historical decision log extracted. |
| [intermediate-products.md](intermediate-products.md) | Cross-domain catalog of non-building product identities, roles, uses, and candidate pathways; includes a Factorio-style product-family completeness checklist | Category scope is recorded in [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md); capability-based catalog size in [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md); the committed rhenium selection in [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md). Placeable entities and their construction hypotheses remain with Infrastructure. |
| [infrastructure.md](infrastructure.md) | Candidate machine/building/infrastructure inventory, family coverage, and construction-demand hypotheses | Phase 1 migration complete. The former Machine Systems content was subsumed here; there is no separate machine-systems owner. The vanilla grid plus compatible tiered poles is accepted in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md); exact pole and construction mappings remain provisional for Phase 3, including the fission/fusion phase mismatch with Power System. |
| [power-system.md](power-system.md) | Core power generation and power-related extension concepts | Phase 1 migration complete; [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) accepts vanilla-grid distribution with tiered poles, and [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md) accepts Hawking as one Phase 4 option. At least one alternative route, production design, generator-phase alignment, and diagnostics/stabilization scope remain open. |
| [logistics-system.md](logistics-system.md) | Physical transport and information-logistics progression | Phase 1 migration complete; vision and transport details remain candidate proposals, with no dated decision log extracted. Powered rails remain unapproved; custom voltage/loss mechanics are extension-only candidates. Candidate placeable transport entities are owned by Infrastructure. |
| [military-system.md](military-system.md) | Military pressure, defense behavior, and military product-chain requirements | Phase 1 migration complete; decision outcomes are recorded in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) through [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md): ADR-0012 remains proposed, ADR-0014/0015 principles are accepted, and ADR-0016 rejects military drones. Ammo counts, enemy-variant conflicts, turret scope, and balance values remain open. |
| [research-progression.md](research-progression.md) | Research phases, mechanics, and technology gating | Owns the candidate research progression; the six-domain roster is the current recorded baseline, while pack tiers, prerequisite counts, Core gates, technology assignments, and timing remain open or conflicting. |
| [endgame-vision.md](endgame-vision.md) | Planetary simulation endgame concept, facilities, and victory direction | Owns the endgame vision and candidate facility concepts; detailed research gating remains in `research-progression.md`. The final milestone and Core progression are not locked. |
| [gap-analysis-report-11-11-26.md](gap-analysis-report-11-11-26.md) | Comparative gap evidence and recommendations | Evidence only. Each recommendation requires a disposition in the planned gap audit before affecting design. |
| [market-research-report.md](market-research-report.md) | Market comparisons and recommendations | Evidence only; recommendations do not override the north star or become requirements automatically. |

## Product-Tree Ownership Boundaries

- World placement and availability: `map-world-generation.md`.
- Extracted feeds, recovery, pure materials, refining: `minerals-and-refining.md`.
- Reagents, reactions, chemical products, and coproduct chemistry: `chemical-processes.md`.
- Non-building product identities, roles, consumer links, and candidate pathways: `intermediate-products.md`; placeable entities and construction-demand hypotheses: `infrastructure.md`.
- Buildable infrastructure, machine families, construction demand, and candidate tier progression: `infrastructure.md`; exact route-to-machine assignments remain deferred.
- Power, logistics, military, endgame, and research behavior: their respective domain owners in the table.
- Cross-domain intent and open items: `mod-overview.md`; detailed resolutions belong in the affected domain owner and, when significant, a linked ADR.
- Complete coverage: `product-coverage-ledger.md` (to be created in Phase 4).
- Migration provenance and content mapping: [migration-map.md](migration-map.md); this is a process record, not a competing domain design source.

## Missing and Historical Reference Dispositions

| Former reference | Status and disposition |
|---|---|
| `machine-systems.md` | Historical document, deleted when `infrastructure.md` was introduced; the user confirmed its content was subsumed in Infrastructure. Machine families and candidate progression are owned there. The archived route-to-machine matrix was empty, so exact assignments remain deferred to product/process coverage work. |
| `session-plan.md` | Not present in the current tree or visible Git history. The current work roadmap is [plan.md](plan.md); no separate design content was available to migrate. |
| `mineral-catalog.md` | Not present in the current tree or visible Git history; it was a placeholder filename in the overview. Deposit and refining ownership is [Minerals and Refining](minerals-and-refining.md). |
