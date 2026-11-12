# ADR-0028: Require the Material Stack in the Initial Core CPU Path

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) selects conventional CPU-grade packaged processors by late Phase 2 for initial Core computation. [ADR-0026](ADR-0026-phase-2-contemporary-semiconductor-capability.md) places contemporary cleanroom and advanced chipmaking in Phase 2, and [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) requires silicon wafers, lithography chemistry, HfO₂ dielectric, Cu/TaN interconnect, and package-material families in the Phase 2 chipmaking chain. Whether these families were direct inputs to the standard CPU path remained open.

## Decision

1. The standard late-Phase-2 conventional CPU production path that supplies the initial Core must use all five selected material families: silicon wafers, lithography chemistry, HfO₂ dielectric, Cu/TaN interconnect, and package materials.
2. This requirement applies to the standard CPU path for initial Core supply; it does not prohibit alternate processor variants or routes.
3. Exact product and recipe definitions, material grades, ore mix, extraction/separation/refining routes, quantities, equipment configuration, and research gates remain open. Mineral feed-family assignments for silicon, hafnium, tantalum, and copper are selected separately in [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md).

## Options Considered

1. **Require all five material families on the standard late-Phase-2 CPU path.** Accepted; it makes the selected material stack a direct dependency of initial Core compute.
2. **Require the families somewhere in Phase 2 chipmaking, but allow the standard CPU path to bypass some of them.** Rejected; it would leave the main CPU-to-Core trunk disconnected from the selected stack.

## Rationale

The initial Core depends on a late-Phase-2 conventional CPU supply, and the user selected contemporary chipmaking material families as required. Connecting all five to the standard CPU path makes those material and process branches consequential to the main trunk rather than parallel optional capabilities.

## Consequences

- Positive: The initial Core CPU path now has explicit upstream silicon, lithography-chemistry, HfO₂, Cu/TaN, and packaging dependencies.
- Negative or trade-offs: Phase 2 must demonstrate supply routes for all five families before the Core CPU is available; this raises the dependency and balancing burden of the standard semiconductor chain.
- Follow-up work: Establish viable feed, purification, manufacturing, and research paths for these families without changing the selected late-Phase-2 CPU availability. Keep recipes, quantities, and detailed equipment assignments open for their designated design phases.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), [ADR-0026](ADR-0026-phase-2-contemporary-semiconductor-capability.md), [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), and [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md).
- Supersedes / superseded by: No prior decision is superseded. This specifies the standard CPU path's dependency on the material families selected in ADR-0027; ADR-0029 assigns mineral feed families for silicon, hafnium, tantalum, and copper. ADR-0025's late-Phase-2 CPU availability and later superconducting-compute decisions remain in force.
