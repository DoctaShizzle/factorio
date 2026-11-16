# ADR-0077: Keep Domain Packs Out of Array Construction Inputs

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md), and [Intermediate Products](../intermediate-products.md).

## Context

First-Core construction requires all six domains at T2b2 plus the Unified Metrology Reference Array under [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md). Whether domain packs were also physical ingredients in the Array remained open.

## Decision

Use domain packs to establish the research prerequisites; do not consume them as physical ingredients when constructing the Array. The Array remains a physical instrument assembled from appropriate materials and components. Its complete bill of materials, including the deferred neutron-reference material, remains open.

This decision does not change the six-domain T2b2 plus Array first-Core gate, the selected facility-to-bridge mappings, or any later simulation-research mechanics.

## Options Considered

1. **Use packs for research prerequisites only, not as Array ingredients.** Selected.
2. **Also consume domain packs as physical Array ingredients.** Not selected.
3. **Keep the physical-input question open.** Not selected.

## Rationale

Research evidence and physical instrumentation retain distinct roles without changing the existing convergence gate.

## Consequences

- Positive: Array construction and domain research do not duplicate the packs' role as physical construction materials.
- Trade-offs: Actual instrument materials and a pre-Core neutron-reference supply still need design and validation.
- Follow-up work: establish the material-family coverage in Phase 5 and define products and recipes in Phases 6-7.

## Affected Design and Related Decisions

- Design documents: [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md), and [Intermediate Products](../intermediate-products.md).
- Related ADRs: [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), and [ADR-0037](ADR-0037-defer-array-neutron-reference-material.md).
- Supersedes / superseded by: Resolves the previously open physical-use question; the accepted first-Core and bridge decisions remain in force.
