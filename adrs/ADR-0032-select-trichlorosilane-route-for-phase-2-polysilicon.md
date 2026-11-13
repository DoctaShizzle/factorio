# ADR-0032: Select the Trichlorosilane Route for Phase 2 Polysilicon

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), and [Plan](../plan.md).

## Context

[ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) selects electronic-grade polysilicon as a Phase 2 bridge product and requires a limited supply before first-Core construction. [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) and [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md) make silicon wafers a required input to the standard late-Phase-2 CPU path. The current candidate route converts metallurgical silicon to trichlorosilane, purifies it, then deposits high-purity silicon using hydrogen, with HCl recycle; the route itself had not been selected.

## Decision

1. Use trichlorosilane formation and purification/distillation followed by hydrogen deposition with HCl recycle as the standard Phase 2 route from metallurgical silicon to electronic-grade polysilicon.
2. Use this route for the Phase 2 polysilicon precursor supply that supports wafer and CPU production; exact purity targets and recipe parameters remain open.
3. This does not select the upstream quartz-to-metallurgical-silicon route, the source and makeup supply for HCl, yields, grades, equipment construction materials, or research gates. Downstream wafer-growth and chip recipes also remain open.

## Options Considered

1. **Select trichlorosilane purification/distillation and hydrogen deposition with HCl recycle.** Accepted; it provides an established industrial route to high-purity polysilicon and uses the existing candidate chemical-process chain.
2. **Require electronic-grade polysilicon but leave its production route open.** Not selected; it would leave a major Phase 2 CPU precursor chain unspecified.
3. **Choose a different high-purity silicon route.** Not selected; no alternate route was established as preferable for this standard CPU path.

## Rationale

The selected route is consistent with the existing trichlorosilane formation and polysilicon-deposition process concepts, gives the pre-Core bridge a concrete supply path, and connects mineral, chemical, and semiconductor production without fixing recipe balance or equipment details prematurely.

## Consequences

- Positive: The path from metallurgical silicon to electronic-grade polysilicon is defined for the Phase 2 CPU chain, including recovery and recycle of HCl from deposition.
- Negative or trade-offs: HCl remains required for startup and makeup; its chlor-alkali coproduct source is selected under [ADR-0034](ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md), but startup inventory and loss rates remain open. The upstream silicon reduction route is selected under [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md); detailed process validation and the downstream wafer path remain open.
- Follow-up work: The upstream silicon-reduction route and HCl startup/makeup source are selected under [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md) and [ADR-0034](ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md). Material grades, yields, purity targets, startup quantities, and remaining process/research gates still require validation before the Phase 2 chain is finalized.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md), [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md), [ADR-0031](ADR-0031-starting-region-access-to-cpu-feed-families.md), [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md), and [ADR-0034](ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md).
- Supersedes / superseded by: No prior decision is superseded. This selects the production route for the electronic-grade polysilicon bridge in ADR-0022; mineral-feed, CPU-material, and Phase 2 capability decisions remain in force.
