# ADR-0071: Bound Core Defense to Vanilla Families Plus Electrical Additions

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Military System](../military-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Power System](../power-system.md).

## Context

[ADR-0012](ADR-0012-bound-core-military-scope.md) preserved a proposed bounded roster but did not select the Core scope of its plasma and railgun candidates. The 2.1 base game has its own fixed defenses; the Space Age rocket turret is not a base-game prototype. The user also distinguished deployable vanilla combat robots from the rejected new patrol and sensor drones.

## Decision

Keep the base-game fixed-defense families in Core and add a plasma turret and a railgun turret as two bounded electrical-defense families. Recipes and progression may be overhauled. Both added families must fit the accepted sustained-defense-power principle; their tiers, phases, attack details, ammunition or consumables, profiles, and balance remain open.

Vanilla deployable combat-robot capsules are outside Core and may be considered for an optional extension. Base-game Spidertron and further spider-bot vehicles follow the optional advanced-military direction in [ADR-0016](ADR-0016-late-game-defense-drones.md), not the Core vehicle baseline. This does not reinstate the new patrol-attack or sensor/early-warning drone concepts rejected in ADR-0016. A separate rocket-turret candidate is not selected for Core by this decision, and no Space Age content is required.

## Options Considered

1. **Vanilla fixed defenses plus both electrical additions.** Selected.
2. **Vanilla-only Core with both additions left to extensions.** Not selected.
3. **A broader or different new-turret roster.** Not selected by this decision.
4. **Keep vanilla combat robots in Core or exclude them entirely.** Neither selected; their possible use is limited to an optional extension.

## Rationale

The chosen roster provides distinct electrical-defense directions while bounding the number of additions and preserving the fixed-defense emphasis.

## Consequences

- Positive: Scope and the distinction between vanilla combat robots and rejected new drone concepts are explicit.
- Trade-offs: The two new turret families need independent implementation, power, balance, and progression design.
- Follow-up work: verify the vanilla family mapping and trace retained defense capabilities and power supply in Phase 5; define products, recipes, and gates later.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Power System](../power-system.md).
- Related ADRs: [ADR-0012](ADR-0012-bound-core-military-scope.md), [ADR-0014](ADR-0014-capability-based-ammunition.md), [ADR-0015](ADR-0015-sustained-power-for-defense.md), [ADR-0016](ADR-0016-late-game-defense-drones.md), and [ADR-0069](ADR-0069-target-factorio-2-1-base-game.md).
- Supersedes / superseded by: Resolves the Core turret-scope question in ADR-0012; its unselected detailed behavior and other proposals remain historical candidates.
