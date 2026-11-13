# ADR-0038: Select Crystalline-Silicon PV for Phase 2

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md).

## Context

[ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) and [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md) establish photovoltaic generation no earlier than Phase 2 but leave its first cell platform and production route open. [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) keeps the first panel from depending on post-Core CPU wafer/chip or cleanroom fabrication. The initial PV platform needs to use a Phase 2 material direction without making the Core CPU fabrication chain a prerequisite.

## Decision

Use crystalline-silicon cells for the initial Phase 2 photovoltaic option. Develop them through a dedicated Phase 2 PV production route based on the selected silicon supply direction; this route must not depend on post-Core Level 1 CPU wafer/chip or cleanroom fabrication.

This selects the initial cell platform and its phase boundary only. The silicon grade, detailed process steps, equipment assignment, research gate, and whether the route shares an intermediate with electronic-grade polysilicon remain open. This decision does not set solar tiers, storage timing or chemistry, output values, or later PV upgrades.

## Options Considered

1. **Crystalline-silicon PV on a dedicated Phase 2 route.** Selected; it uses the established silicon supply direction while keeping the initial PV capability independent of CPU wafer/chip fabrication.
2. **CdTe thin-film PV.** Not selected for the initial Phase 2 platform; it would add cadmium and tellurium feed-path decisions.
3. **CIGS thin-film PV.** Not selected for the initial Phase 2 platform; it would add indium, gallium, and selenium feed-path decisions.
4. **Defer the initial cell platform.** Not selected; determining the platform now lets later product and recipe work proceed without assuming an additional mineral feed family.

## Rationale

Crystalline silicon connects the initial PV route to the selected Phase 2 silicon supply direction without introducing a new base-cell mineral feed family. A dedicated PV route preserves the accepted boundary that solar availability does not require post-Core CPU wafer/chip or cleanroom fabrication. Keeping the precise grade and process open avoids assuming that CPU-grade polysilicon is required.

## Consequences

- Positive: The initial Phase 2 PV cell platform is defined and can be aligned with the silicon material chain.
- Negative or trade-offs: A separate Phase 2 PV production route must be designed; its exact materials, processing, equipment, and progression remain open.
- Follow-up work: Define the PV-grade silicon supply and cell process, then resolve its machine and research gates, storage chemistry and timing, output, and later upgrade options.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0032](ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md), [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md).
- Supersedes / superseded by: None.
