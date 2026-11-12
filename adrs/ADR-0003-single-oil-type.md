# ADR-0003: Use a Single Oil Type

*Status: Accepted (light/heavy crude variation rejected)*
*Decision date: 2026-11-06*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Chemical Products and Processes](../chemical-processes.md).

## Context

The world-generation proposal considered distinct light sweet and high-viscosity crude. Light crude would be easier to process and yield more, but be rarer; heavy crude could be more abundant, but require additional processing and yield less. The proposal also notes that oil should occur within the playable area, near enough to support the Phase 1/2 transition rather than being restricted to vanilla's map edges. Distinct oil types would add chemistry entries and route complexity.

## Decision

Use one oil type. The source rationale assigns differences in crude-processing capability to machine tiers rather than parallel oil chemistries.

## Options Considered

1. **Separate light and heavy crude.** Light crude would be easier to process and yield more; heavy crude could be more abundant but require more processing and have lower yield.
2. **One oil type with tiered processing capability.** Avoids parallel resource and chemistry chains; machine tiers represent capability differences. This was accepted.

## Rationale

The source rejects the extra chemistry and dual-route complexity, treating machine tier progression as sufficient differentiation.

## Consequences

- Positive: fewer resource types and chemical pathways.
- Trade-off: oil fields do not provide a light/heavy resource-choice axis.
- Follow-up: clarify what “heavier crude” means in the machine-tier rationale if the design keeps only one oil item; do not imply an unmodeled oil variant.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Chemical Products and Processes](../chemical-processes.md).
- Related ADRs: None.
- Supersedes / superseded by: Rejects the earlier open proposal to introduce light and heavy crude; no superseding ADR recorded.
