# ADR-0010: Retain the Vanilla Grid with Tiered Power Poles

*Status: Accepted*
*Decision date: 2026-11-12 (user acceptance; source proposal dated 2026-11-07)*
*Last updated: 2026-11-12*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Logistics System](../logistics-system.md), [Military System](../military-system.md).

## Context

The Power System draft records two dated choices: use Factorio's vanilla pole grid for core-mod generators, and defer a full transmission-system replacement to an optional `power-transmission-override` extension. The source called these decisions, but its overall status was concept/requirements and no separate approval record was found. On 2026-11-12, the user accepted retaining the vanilla system and added a direction to introduce tiered power poles.

The source rationale is that major overhauls such as Space Exploration, Bob's Mods, and Pyanodons retain the vanilla pole network; it also notes that Advanced Power Poles expands pole range/capacity without replacing transmission. A custom grid would have to replace a fundamental game subsystem through Lua. The draft identifies compatibility with other power mods, fragility across Factorio updates, and additional engineering effort as risks, on top of the planned machine and recipe scope.

The proposed extension would add discrete transmission lines, voltage tiers, length- and material-dependent losses, transformers, HVDC converters, grid diagnostics, and fault propagation. The source describes it as a parallel architecture alongside vanilla poles, which players could use alone or mix with the vanilla network; it would be optional and separate from the core experience.

The same source later calls power diagnostics a core feature, despite placing grid diagnostics in the proposed extension. It does not distinguish basic vanilla-grid status from voltage/loss diagnostics, so the diagnostics boundary remains unresolved.

## Decision

**Accepted:** Retain Factorio's existing pole-grid system for core power distribution and add compatible tiered power-pole buildables. The added poles use the vanilla electrical network; they do not introduce custom voltage tiers, transmission losses, or a replacement grid. The user cited tiered-pole approaches in Space Exploration and Bob's/Angel's as inspiration, not as a verified feature specification. Exact pole count, phase, materials, reach, coverage, and connection limits remain open. A full transmission replacement, if pursued, remains a separate opt-in `power-transmission-override` extension proposal.

## Options Considered

1. **Retain only vanilla pole delivery in core.** Keeps the existing power interface but does not add pole progression; this was the source's original scope proposal.
2. **Retain the vanilla grid and add compatible tiered poles.** Adds material and placement progression without requiring custom voltage or transmission behavior; accepted.
3. **Replace the pole network in core.** Adds a custom transmission model, but incurs the compatibility, update, and implementation risks identified in the source.
4. **Defer a full replacement to an extension.** Preserves the vanilla core while retaining the possibility of an optional, more complex grid.

## Rationale

The accepted direction retains compatibility with Factorio's power network while using tiered poles to add a bounded, visible progression layer. Custom transmission remains an optional complexity layer rather than a core dependency.

## Consequences

- Positive: Core generation remains compatible with the vanilla network, while pole variants add construction and placement choices.
- Trade-offs: Tier count, pole statistics, materials, and phase gates still need design; the core grid does not model voltage or transmission loss.
- Follow-up: Add the tiered pole family to [Infrastructure](../infrastructure.md), align powered-rail assumptions in [Logistics System](../logistics-system.md), and reconcile basic versus grid-specific diagnostics and stabilization scope.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Logistics System](../logistics-system.md), [Military System](../military-system.md).
- Related ADRs: None recorded.
- Supersedes / superseded by: Replaces the source's proposed vanilla-only core pole scope with the accepted vanilla-grid-plus-tiered-poles direction; the optional full-grid replacement remains separate.

## Revisions

- 2026-11-12 — User accepted retaining the vanilla power system and requested compatible tiered power poles; pole statistics and progression details remain open.
