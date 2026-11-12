# ADR-0027: Require a Contemporary Semiconductor Material Stack in Phase 2

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) selects conventional CPU-grade packaged processors for late Phase 2 and initial Core computation. [ADR-0026](ADR-0026-phase-2-contemporary-semiconductor-capability.md) places full cleanroom and advanced chipmaking through contemporary real-world practice in Phase 2. The current product and process drafts identify silicon wafers, lithography chemistry, hafnium oxide, copper/tantalum-nitride interconnects, and package materials as candidate parts of that production chain, but their required status was not settled.

## Decision

1. Require these material families in the Phase 2 contemporary chipmaking chain: silicon wafers, lithography chemistry, hafnium-oxide (HfO₂) dielectric, copper/tantalum-nitride (Cu/TaN) interconnect, and semiconductor package materials.
2. This selects the required material families, not exact recipes or a requirement that every processor recipe consume every family. Exact material grades, ore mix, extraction/separation/refining routes, process chemicals, package variants, quantities, and research gates remain open; mineral feed-family assignments are selected separately in [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md).
3. This decision does not approve specific mineral-to-product or chemical reaction routes. ADR-0029 selects mineral source families; detailed source-to-product routes remain open.

## Options Considered

1. **Use a simpler mandatory CPU path and leave HfO₂, Cu/TaN, lithography chemistry, and advanced package materials optional.** Rejected; it would not make the selected contemporary advanced-chipmaking stack a required Phase 2 capability.
2. **Require silicon wafers, lithography chemistry, HfO₂ dielectric, Cu/TaN interconnect, and package-material families in the Phase 2 chipmaking chain.** Accepted; it establishes the material-family demand while leaving route and recipe details open.

## Rationale

The Phase 2 manufacturing boundary now includes contemporary advanced chipmaking, so its major material families must be visible in the cross-domain chain. Selecting the families exposes the consequential silicon, hafnium, tantalum, copper, and chemical-process dependencies without prematurely choosing unvalidated feed routes or recipes.

## Consequences

- Positive: Contemporary chipmaking has an explicit, cross-domain material demand rather than an unspecified CPU package input.
- Negative or trade-offs: Phase 2 now depends on semiconductor material families from mineral, chemical, and manufactured-product chains; their supply paths and process demands must be validated.
- Follow-up work: Establish Phase 2 routes and material grades for the selected families before the Phase 2 exit gate. Keep exact recipes, quantities, equipment configuration, and research gates open until their designated design phases.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), [ADR-0026](ADR-0026-phase-2-contemporary-semiconductor-capability.md), [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md), and [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md).
- Supersedes / superseded by: No prior decision is superseded. This selects required material families under the Phase 2 capability boundary in ADR-0026; ADR-0028 specifies their use in the standard CPU path, and ADR-0029 assigns mineral feed families for silicon, hafnium, tantalum, and copper. ADR-0025's CPU availability and later superconducting-compute decisions remain in force.
