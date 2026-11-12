# ADR-0017: Set Phase 2 Core and Bridge Prerequisites

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md).

## Context

The research design contained conflicting first-Core gates: one passage required all six domains at T2b2 before Core construction, while another proposed T2a plus the Unified Metrology Reference Array. The source also described a convergence item separately from the Array. The product inventory had six candidate bridge products, including the accepted rhenium-catalyst selection, while earlier prose referred to five.

On 2026-11-12, the user clarified that first Core construction requires all six domain chains at T2b2 and the Unified Metrology Reference Array, which is the convergence item. The user also selected six bridge products for the six-domain roster, counting rhenium-catalyst powder as the sixth. This does not reopen the accepted rhenium decision in [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md).

## Decision

1. Require all six domains at T2b2 and the Unified Metrology Reference Array (the convergence item) before first Core construction.
2. Use six Phase 2 bridge products for the six-domain roster, including the accepted rhenium-catalyst powder.
3. At the time of this decision, keep product-to-facility mappings open. The six mappings were later selected in [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md); exact production routes, Unified Metrology Reference Array materials, and the Core Level 2 gate remain open. This ADR does not approve recipes or facility material lists.

## Options Considered

1. **First Core at T2a plus the Array, with T2b2 at Core Level 2.** This was an earlier candidate, but it does not match the user's clarified first-Core gate.
2. **First Core at T2b2 plus the Array.** Selected; it aligns the all-domain threshold with the convergence item before Core construction.
3. **Five bridge products or six.** Six is selected to match the six-domain roster, with the already accepted rhenium selection counted as the sixth. The facility mappings were subsequently selected in ADR-0022.

## Rationale

The T2b2 requirement creates a common cross-domain threshold before the first simulation Core is constructed, while the Array provides the physical convergence item. Counting six bridge products matches the recorded six-domain roster and preserves ADR-0007 without reopening the rhenium choice.

## Consequences

- Positive: The first Core gate and bridge-product count now have a consistent Phase 2 direction.
- Trade-offs: Existing pack-count and playtime estimates were based on earlier gates and require reassessment; the Core Level 2 gate remains undecided.
- Follow-up: Validate the selected bridge routes and supporting inputs across the owning documents; resolve the Array construction requirements separately.

## Affected Design and Related Decisions

- Design documents: [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md), [Migration Map](../migration-map.md).
- Related ADRs: [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md), [ADR-0009](ADR-0009-endgame-assembly-proposals.md), [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).
- Supersedes / superseded by: Supersedes the T2a first-Core proposal in the current-state research draft; does not supersede ADR-0007.
