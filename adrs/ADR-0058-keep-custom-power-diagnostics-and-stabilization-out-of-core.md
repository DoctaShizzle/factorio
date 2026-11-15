# ADR-0058: Keep Custom Power Diagnostics and Stabilization Out of Core

*Status: Accepted*
*Decision date: 2026-11-15 (pragmatic resolution under delegated Phase 2 direction)*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Logistics System](../logistics-system.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).

## Context

[ADR-0010](ADR-0010-core-power-distribution-scope.md) accepts Factorio's vanilla electrical grid with compatible tiered poles and keeps a custom transmission model out of Core. It did not settle whether Core should add grid-specific diagnostics or stabilization devices. The current proposals include custom voltage, line-loss, load-analysis, reactive-power, surge-protection, and frequency-regulation mechanics, while other text describes diagnostics as a Core feature.

The Phase 2 direction favors understandable, low-friction power systems. The accepted vanilla grid already supplies its own network feedback; custom grid simulation is not needed to use the selected generation routes.

## Decision

Core power distribution uses Factorio's native electrical network and its native network and machine feedback. Core does not add custom voltage, line-loss, fault-propagation, load-analysis, or load-shedding diagnostics, nor custom grid-stabilization devices.

These concepts may remain unapproved candidates for a future optional extension. This decision does not change the accepted vanilla-grid-plus-tiered-poles direction or ordinary machine status and energy-consumption information.

## Options Considered

1. **Add custom diagnostics and stabilization to Core.** This would make a custom grid model a dependency of ordinary power use and would require additional mechanics and onboarding.
2. **Use native grid feedback in Core.** This preserves the accepted vanilla network and avoids requiring custom grid simulation; accepted.
3. **Keep custom grid mechanics as optional extension candidates.** This preserves the possibility of a separate advanced system without making it part of Core; retained as an unapproved possibility.

## Rationale

The vanilla-grid decision already provides a usable power network. Requiring custom voltage, loss, or stabilization mechanics would expand the Core power model without an accepted Phase 2 need and would make power behavior harder to learn.

## Consequences

- Core generation and storage do not depend on custom grid diagnostics or stabilization.
- The candidate devices in Power System and Infrastructure are not Core requirements, research gates, or approved constructables.
- Exact scope, mechanics, and progression for any future grid extension remain open.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Logistics System](../logistics-system.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md).
- Supersedes / superseded by: Clarifies the unresolved diagnostics/stabilization boundary under ADR-0010; does not supersede it.
