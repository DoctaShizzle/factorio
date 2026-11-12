# ADR-0020: Use Seven Distinct Domain-Pack Tiers

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Plan](../plan.md).

## Context

The research draft listed seven named tiers but also described a five-tier Phase 2 ladder, leaving both the tier count and item model unresolved. The first-Core threshold at T2b2 is already accepted in [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md). The user confirmed that the seven named tiers are the intended progression and that each tier is a distinct domain-pack item, not an alternate recipe.

## Decision

1. Use seven distinct domain-pack tiers for each of the six domains: T1, T2a, T2b1, T2b2, T3a, T3b, and T3c.
2. T1 through T2b2 are the pre-Core Phase 2 progression. T3a through T3c are post-first-Core Phase 3 progression.
3. Keep the first-Core requirement at all six domains reaching T2b2 plus the Unified Metrology Reference Array, as recorded in ADR-0017. This ADR does not set the Core Level 2 or Level 3 gates.
4. Align the tier ladder to the material trunk by capability stage: foundational Phase 2 inputs at T1; the selected domain bridge material at T2a; deeper domain-specific refinement at T2b1; cross-domain high-purity inputs at T2b2; Core-produced simulation outputs at T3a; calibration and higher-fidelity outputs at T3b; and convergent multi-domain synthesis at T3c.

The material-trunk alignment is not a recipe commitment. Exact item names, materials, routes, yields, research assignments, and later Core-level requirements remain open.

## Options Considered

1. **Keep the five-versus-seven conflict open.** Rejected because it leaves the Phase 2 ladder and catalog shape ambiguous despite the selected T2b2 Core gate.
2. **Use the seven named tiers as distinct items per domain.** Selected; it preserves the established T2b2 threshold and gives each progression stage a separate research input.
3. **Represent tiers as alternate recipes for one pack item.** Rejected; the selected design uses distinct research items.

## Rationale

The seven named stages already describe a progression from observation through cross-domain synthesis. Treating them as distinct items makes that progression legible while keeping the accepted first-Core boundary at T2b2. The material-trunk alignment connects each stage to increasing process depth without prematurely fixing the product or recipe catalog.

## Consequences

- Positive: the five-versus-seven conflict is resolved, and pre-Core and post-Core pack progression have a clear boundary.
- Trade-offs: pack names, recipes, ingredient lists, technology assignments, production values, and Core Level 2/3 gates still require design and validation.
- Follow-up: map the accepted bridge products and deeper material capabilities to the tier stages without treating estimates as catalog targets.

## Affected Design and Related Decisions

- Design documents: [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Plan](../plan.md).
- Related ADRs: [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0006](ADR-0006-capability-based-intermediate-scope.md).
- Supersedes / superseded by: Resolves the five-versus-seven tier-count question in the research draft; does not supersede ADR-0017.
