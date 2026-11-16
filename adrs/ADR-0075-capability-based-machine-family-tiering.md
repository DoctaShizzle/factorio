# ADR-0075: Select Machine Tiers by Family and Capability

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Infrastructure](../infrastructure.md), [Logistics System](../logistics-system.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

Several infrastructure sections proposed mandatory tiers for every machine in a category, while the general equipment principles left family-specific tiering open. The user selected a capability-based, family-by-family policy.

## Decision

Decide tiering separately for each family; an untiered or shared machine is valid. A newly required progression tier must add a meaningful capability, such as a genuinely different process, material-service range, or precision, rather than being justified by speed or capacity alone. Existing vanilla throughput variants are not automatically new Prometheus capability tiers.

This does not select exact tier counts, materials, recipes, or research gates. Preserve the accepted tiered-pole family and untiered boiler, steam engine, and steam-turbine boundaries.

## Options Considered

1. **Require tiers for every family.** Not selected.
2. **Choose tiers by family and meaningful capability.** Selected.
3. **Treat every speed-only variant as a required new capability tier.** Not selected.

## Rationale

The policy supports industrial choices and specialized equipment without multiplying builds solely to increase counts.

## Consequences

- Positive: Single-purpose equipment and shared machine families remain viable.
- Trade-offs: Each proposed tier needs an explicit role and phase rather than inheriting a universal ladder.
- Follow-up work: normalize family identities and candidate tiers, then verify routes and concrete unlocks in later phases.

## Affected Design and Related Decisions

- Design documents: [Infrastructure](../infrastructure.md), [Logistics System](../logistics-system.md), and [Research and Progression](../research-progression.md).
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md), [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), and [ADR-0070](ADR-0070-overhaul-vanilla-recipes-and-progression.md).
- Supersedes / superseded by: Replaces the conflicting unapproved blanket-tier proposals; accepted pole and steam boundaries remain in force.
