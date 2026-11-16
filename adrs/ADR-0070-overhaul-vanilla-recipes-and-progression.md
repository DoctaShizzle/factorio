# ADR-0070: Overhaul Vanilla Recipes and Progression Where Useful

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Technical Architecture](../technical-architecture.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Plan](../plan.md).

## Context

Phase 4 needs a consistent distinction between vanilla content that is retained, modified, or replaced. The user clarified that overhauling most vanilla gameplay families means retaining existing prototypes where useful while changing recipes and progression, rather than automatically replacing them with new prototypes.

## Decision

Use the existing base-game items and entities where they serve the intended capability, modifying their recipes or progression where appropriate. Add or replace prototypes when a distinct capability or an explicitly selected replacement warrants it. This is a scope policy, not approval of any particular recipe, unlock, variant, or wholesale retention of all vanilla content.

Preserve the accepted vanilla electrical grid, boiler and steam machinery, and selected vanilla defense baseline. Electric locomotives replace fueled locomotives in Core under [ADR-0073](ADR-0073-core-electric-only-rail.md); other explicit exclusions and extensions remain separately classified.

## Options Considered

1. **Replace most vanilla prototypes with new counterparts.** Not selected.
2. **Reuse useful prototypes while overhauling recipes and progression and adding capability-specific content.** Selected.
3. **Retain vanilla families without an overhaul by default.** Not selected as the general approach.

## Rationale

This preserves familiar engine behavior where useful while allowing the industrial progression to change without creating redundant entities solely for a new name.

## Consequences

- Positive: New prototypes and tiers can be justified by player-facing capability rather than a blanket replacement rule.
- Trade-offs: Individual prototype, recipe, and technology dispositions still require family-level review.
- Follow-up work: classify the inventory against the 2.1 base game and verify actual item and technology changes in later phases.

## Affected Design and Related Decisions

- Design documents: [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and the affected system owners.
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md), [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0069](ADR-0069-target-factorio-2-1-base-game.md), and [ADR-0073](ADR-0073-core-electric-only-rail.md).
- Supersedes / superseded by: No accepted vanilla-wide replacement rule is superseded.
