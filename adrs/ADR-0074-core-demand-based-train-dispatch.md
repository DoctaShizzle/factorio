# ADR-0074: Add Optional Core Demand-Based Train Dispatch

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Logistics System](../logistics-system.md), [Infrastructure](../infrastructure.md), and [Technical Architecture](../technical-architecture.md).

## Context

The logistics draft proposed both dedicated train connections and demand-based dispatch, but their Core scope and dependency on outside integrations were open.

## Decision

Keep ordinary vanilla-style train scheduling and add demand-based dispatch as an optional Core capability. Dedicated routes and pooled demand dispatch can coexist. Basic rail transport and mandatory resource access must remain usable without advanced dispatch or an external dispatch mod.

The exact implementation, interface, station requirements, research gate, computational cost, and optional compatibility with third-party mods remain open.

## Options Considered

1. **Ordinary schedules plus optional Core demand dispatch.** Selected.
2. **Ordinary schedules in Core; advanced dispatch only as an extension candidate.** Not selected.
3. **Require an external dispatch mod for normal transport.** Not selected.

## Rationale

Players can use predictable dedicated connections while gaining a later option for changing demand without making basic rail service dependent on another mod.

## Consequences

- Positive: The two intended logistics styles have explicit Core scope.
- Trade-offs: The implementation and performance of automated matching remain to be designed and tested.
- Follow-up work: define the player-facing station and dispatch contract and verify the early rail path independently of it.

## Affected Design and Related Decisions

- Design documents: [Logistics System](../logistics-system.md), [Infrastructure](../infrastructure.md), and [Technical Architecture](../technical-architecture.md).
- Related ADRs: [ADR-0073](ADR-0073-core-electric-only-rail.md).
- Supersedes / superseded by: Resolves the previously unapproved Core dispatch-scope proposal.
