# ADR-0069: Target Factorio 2.1 Without a Required DLC

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Technical Architecture](../technical-architecture.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Plan](../plan.md).

## Context

Version-dependent vanilla scope could not be classified while the game version and DLC requirement were open. Factorio's [2.1.25 prototype data](https://github.com/wube/factorio-data/tree/2.1.25) and [2.1.25 API documentation](https://lua-api.factorio.com/2.1.25/) provide a concrete reference for this review.

## Decision

Target the Factorio 2.1 base game; do not require Space Age or another DLC for Core. The 2.1.25 sources are evidence for the 2.1 family review, not a minimum patch-level commitment. DLC compatibility or optional integrations are not selected by this decision.

Keep the selected stellar solar collection and beaming route in scope without assuming Space Age platforms or other DLC-only content. Its independent implementation and feasibility remain open.

## Options Considered

1. **Factorio 2.1 base game, no required DLC.** Selected.
2. **Factorio 2.1 with Space Age required.** Not selected.
3. **Factorio 2.0, with or without Space Age.** Not selected.

## Rationale

The chosen baseline permits the Core experience without a paid expansion and makes the version-specific inventory review concrete. It does not establish that every candidate mechanic is implementable without further work.

## Consequences

- Positive: Core dependencies and vanilla family comparisons have a defined baseline.
- Trade-offs: DLC-only prototypes and mechanics cannot be assumed available; space-based concepts need an independent design.
- Follow-up work: validate APIs and implementation on the selected 2.1 release, and decide any optional DLC compatibility separately.

## Affected Design and Related Decisions

- Design documents: [Technical Architecture](../technical-architecture.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Power System](../power-system.md).
- Related ADRs: [ADR-0008](ADR-0008-factorio-product-family-coverage.md) and [ADR-0018](ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md).
- Supersedes / superseded by: Resolves the previously open version and required-DLC baseline.
