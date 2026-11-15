# ADR-0045: Require a Distinct Phase 2 Zirconium-Hafnium Separation Stage

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).

## Context

[ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects zircon as the hafnium-bearing feed for the standard late-Phase-2 CPU path. [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) sets limited early/mid-Phase-2 zircon access. [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires cladding and rod assembly for both Phase 2 fission options, and [ADR-0044](ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) selects zirconium-alloy cladding and shares zircon access across the CPU and fission paths.

The Infrastructure candidate had represented zircon processing as one recipe producing zirconium with hafnium as a coproduct, naming fractional chlorination as the separation method; its note described this as a simplification from multi-step distillation. The Power System candidate instead listed fractional chloride distillation and hydrometallurgical purification. These conflicting candidate descriptions were not selected, and the exact earlier multi-step proposal was not specified. A route boundary is needed that makes the shared feed's two uses explicit without prematurely fixing detailed chemistry or recipes.

## Decision

1. The shared Phase 2 zircon pathway must represent Zr/Hf separation as a distinct processing stage, separate from upstream feed preparation/conversion and downstream product processing.
2. The separated zirconium-bearing stream supports zirconium-alloy cladding; the hafnium-bearing stream supports the CPU hafnium path and other selected hafnium uses.
3. This selects a route-stage boundary, not a specific reaction, separation technique, intermediate item, recipe count, machine/entity, or equipment configuration. Their designs remain open.
4. Validate the combined CPU and fission-cladding demand against accessible zircon supply when quantities and material balances are established.

## Options Considered

1. **Keep a single combined zircon-to-zirconium recipe with hafnium as a coproduct.** Not selected; it collapses feed conversion and Zr/Hf separation into one operation and obscures the shared material split.
2. **Require a distinct Zr/Hf separation stage while leaving its chemistry and implementation open.** Selected; it makes the material dependency legible without deciding an unvalidated industrial route.
3. **Select a detailed multi-step chemical route now.** Deferred; exact conversion chemistry, separation method, equipment, and recipes need route and balance validation.

## Rationale

The CPU and fission paths rely on different outputs from the same zircon-bearing feed. Showing their separation as a distinct stage preserves that dependency and provides an explicit point for later chemistry, equipment, and material-balance design, while avoiding unsupported process detail.

## Consequences

- Positive: the shared zircon chain has a clear processing boundary between its hafnium and cladding uses.
- Trade-offs: the explicit stage adds route complexity compared with a single combined recipe; its gameplay representation and throughput still need validation.
- Follow-up work: determine feed preparation/conversion, separation chemistry, output forms and grades, equipment, alloying and tube-forming routes, research timing, and combined accessible-supply quantities.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects zircon as the CPU hafnium feed; [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) sets early/mid-Phase-2 access; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires Phase 2 cladding and rod assembly; [ADR-0044](ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) selects zirconium-alloy cladding and shared zircon access.
- Supersedes / superseded by: No prior decision is superseded. This resolves the route-stage follow-up left open by ADR-0044; the detailed processing route remains open.
