# ADR-0030: Require Limited Early Access to Semiconductor Feed Deposits

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), and [Plan](../plan.md).

## Context

[ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects zircon as the hafnium-bearing feed family and columbite-tantalite as the tantalum-bearing feed family for the standard late-Phase-2 CPU path. The current world-generation concept places niobium/tantalum among rare deposits, while zircon access timing is unspecified. If the required feeds are only reachable through distant, rich deposits, they could block Phase 2 CPU supply.

## Decision

1. Provide limited accessible supplies of zircon and columbite-tantalite by early to mid Phase 2 so the required hafnium and tantalum feeds can enter the CPU material chain.
2. Richer deposits may remain regional or rare and can continue to reward prospecting and logistics.
3. This sets an access-timing constraint only. Exact deposit quantities, locations, biome assignments, distances, cluster sizes, prospecting gates, and mining yields remain open.

## Options Considered

1. **Keep all zircon and columbite-tantalite deposits rare or distant until the late-Phase-2 CPU gate.** Not selected; it risks making required CPU inputs depend entirely on the late exploration bottleneck.
2. **Guarantee limited early/mid-Phase-2 access while retaining richer distant deposits.** Accepted; it protects the CPU path without removing exploration and logistics progression.
3. **Defer resource accessibility entirely.** Not selected; access timing is a direct dependency of the required CPU material chain.

## Rationale

The CPU path needs hafnium and tantalum before the Core can activate, but making all supply remote would conflate material progression with a single late exploration gate. A small early/mid-Phase-2 supply preserves access to the trunk while allowing richer deposits to retain their intended exploration value.

## Consequences

- Positive: Required hafnium and tantalum feeds can be available before the late-Phase-2 CPU gate.
- Negative or trade-offs: World-generation progression must balance the early supply against the value of richer regional deposits.
- Follow-up work: Set quantities, location, accessibility, and prospecting details during map and resource-generation design. Preserve the access timing without assuming exact distances or deposit layouts.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md) and [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md).
- Supersedes / superseded by: No prior decision is superseded. This adds an access-timing constraint for the feed families selected in ADR-0029; exact map placement and distances remain open.
