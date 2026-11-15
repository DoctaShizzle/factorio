# ADR-0041: Select Direct-Use Unclad Fuel for Phase 2 Fission

*Status: Superseded by [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md)*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Power System](../power-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0036](ADR-0036-phase-2-minimum-fission-fuel-path.md) requires reactor-usable baseline fuel for both Phase 2 fission options without Phase 3+ cladding or fuel-rod assembly, but leaves the direct-use fuel form open. The candidate uranium-oxide pellet route also has an unresolved timing mismatch: the minimum Phase 2 reactor needs fuel while the candidate dedicated pellet-sintering furnace is listed in Phase 3.

## Decision

1. Both Phase 2 fission options must produce a fuel item that can be used directly by the reactor without cladding or fuel-rod assembly.
2. The Phase 2 uranium route uses an unclad uranium-dioxide (UO2) fuel pellet as its direct-use fuel item. The minimum capability to produce the finished pellet must be available in Phase 2; whether pellet finishing is a separate machine or part of an integrated process remains open.
3. The Phase 2 thorium route retains the Th-232 feed and uranium-derived fissile startup seed, followed by U-233 breeding and reprocessing under [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md). It must provide a direct-use unclad fuel item, but its exact composition and physical form remain open.
4. Direct use of unclad fuel items is an explicit gameplay abstraction, not a claim that an unclad pellet is a conventional commercial reactor fuel assembly.
5. Uranium enrichment requirements and methods, exact conversion and thorium-processing routes, material balances, equipment assignments, recipes, and research gates remain open.

## Options Considered

1. **Leave the direct-use fuel form unspecified.** Not selected; it would leave the Phase 2 fuel item and the pellet-preparation timing mismatch unresolved.
2. **Move basic cladding and fuel-rod assembly into Phase 2.** Not selected; this would expand the minimum Phase 2 fuel chain beyond the selected direct-use boundary.
3. **Use direct-use unclad fuel items in Phase 2 and keep cladding and rod assembly later.** Selected; uranium uses UO2 pellets, while the thorium cycle retains its selected startup-seed and U-233 model with its exact fuel form open.

## Rationale

This makes the accepted Phase 2 reactor-usable-fuel boundary concrete without adding cladding and rod assembly to the minimum Phase 2 path. It preserves the distinct uranium and thorium cycles while making the non-literal fuel handling explicit.

## Consequences

- Positive: the Phase 2 uranium reactor has a defined direct-use fuel item, and neither fission route requires later cladding or rod assembly for baseline operation.
- Trade-offs: direct use of unclad fuel is a deliberate gameplay abstraction; the thorium fuel form is not yet specified.
- Follow-up work: reconcile the minimum Phase 2 pellet-production capability with the candidate infrastructure inventory; resolve uranium enrichment, thorium fuel chemistry, material balances, equipment, recipes, waste handling, and research gates.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) selects the Phase 2 uranium and thorium options; [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the thorium startup-seed and U-233 gameplay model; [ADR-0036](ADR-0036-phase-2-minimum-fission-fuel-path.md) sets the Phase 2 reactor-usable-fuel capability boundary.
- Supersedes / superseded by: Superseded by [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md), which replaces direct-use unclad fuel with Phase 2 cladding and fuel-rod assembly requirements.
