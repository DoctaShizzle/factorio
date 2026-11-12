# ADR-0006: Scope Intermediate Products by Capability

*Status: Accepted*
*Decision date: Unknown*
*Last updated: 2026-11-12*

Related documents: [Intermediate Products](../intermediate-products.md), [Documentation Conventions](../documentation-conventions.md), [Product Taxonomy](../product-taxonomy.md).

## Context

The intermediate-products design checks state that the downstream list should be built incrementally against actual recipe needs and that a superseded 65–83 item target must not be restored. The current source does not preserve the date or full deliberation behind superseding that target.

## Decision

Derive the required intermediate roster from capabilities, distinct industrial demands, and actual recipe dependencies. Do not treat 65–83 or another numeric product count as a target.

## Options Considered

1. **Restore the previous 65–83 target.** This would make catalog size a design constraint.
2. **Build the roster incrementally from demonstrated needs.** This is the current design direction; each product must unlock a capability, satisfy a distinct demand, or connect systems.

## Rationale

The design favors recognizable capability unlocks over near-duplicate products. A fixed count can reward catalog growth without demonstrating that products support the intended production and progression tree.

## Consequences

- Positive: the catalog can remain bounded by meaningful use rather than by a target number.
- Trade-off: the final count remains unknown until coverage and recipe work are complete.
- Follow-up: keep candidate items distinct from required products and give each required entry a traceable use.

## Affected Design and Related Decisions

- Design documents: [Intermediate Products](../intermediate-products.md), [Product Taxonomy](../product-taxonomy.md).
- Related ADRs: None.
- Supersedes / superseded by: Supersedes the previous 65–83 item target; the date and original rationale are not recorded in the source.
