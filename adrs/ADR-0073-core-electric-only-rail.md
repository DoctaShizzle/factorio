# ADR-0073: Use Electric-Only Rail Traction in Core

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Logistics System](../logistics-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), and [Technical Architecture](../technical-architecture.md).

## Context

The logistics draft proposed powered rails while leaving vanilla fuel-powered locomotives and Core scope undecided. The accepted power direction retains the native electrical grid without custom voltage or transmission losses. Factorio 2.1's [locomotive prototype](https://lua-api.factorio.com/2.1.25/prototypes/LocomotivePrototype.html#energy_source) exposes burner or void energy sources, not a direct electric-grid source.

## Decision

Replace fuel-powered locomotives in Core with electric locomotives supplied through powered rail infrastructure connected to the native grid. Allow a Core runtime adapter to bridge the engine limitation; its design and feasibility are not yet established. It must account for actual grid power rather than grant free traction, and must not require a separate mod, custom grid voltage, or transmission-loss mechanics.

When traction power is lost, trains stop safely without losing their schedules and resume automatically when power returns. The implementation must provide a usable electric rail, power, and locomotive path by the first intended train use, without requiring an operating train, advanced dispatch, an extension, or post-Core capability to bootstrap itself.

Rail geometry, signals, stations, and wagons may reuse vanilla behavior with modified construction or progression. The powered-rail entity model, connection rules, adapter, performance, exact phases, materials, recipes, and research gates remain open.

## Options Considered

1. **Electric locomotives and grid-fed powered rails only in Core.** Selected, with a Core runtime adapter to be validated.
2. **Keep fuel-powered and electric locomotives together in Core.** Not selected.
3. **Keep fueled locomotives in Core and defer electric rail to an extension.** Not selected.
4. **Use rechargeable battery-fueled locomotives instead of grid-fed rails.** Not selected.

## Rationale

The user selected electric-only traction as the Core transport direction and accepted custom integration after the native prototype limitation was identified. Automatic resumption avoids requiring repetitive intervention after outages.

## Consequences

- Positive: Rail transport connects directly to the Core power network.
- Trade-offs: Electrical accounting, safe stopping, restoration, scalability, and compatibility need implementation evidence; the prototype API alone does not provide direct electric locomotives.
- Follow-up work: demonstrate an acyclic early rail path in Phase 5, define products/recipes/gates in Phases 6-8, and test the adapter and performance before implementation approval.

## Affected Design and Related Decisions

- Design documents: [Logistics System](../logistics-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), and [Technical Architecture](../technical-architecture.md).
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md), [ADR-0069](ADR-0069-target-factorio-2-1-base-game.md), and [ADR-0074](ADR-0074-core-demand-based-train-dispatch.md).
- Supersedes / superseded by: Replaces the unapproved proposal to retain fueled locomotives in Core; other burner-fuel uses are unchanged.
