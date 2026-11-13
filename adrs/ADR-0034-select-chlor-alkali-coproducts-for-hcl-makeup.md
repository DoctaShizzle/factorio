# ADR-0034: Select Chlor-Alkali Coproducts for Phase 2 HCl Makeup

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Chemical Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Plan](../plan.md).

## Context

[ADR-0032](ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md) selects trichlorosilane formation and hydrogen deposition with HCl recycle for Phase 2 polysilicon. The route still needs an initial HCl charge and makeup supply. [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md) makes salt/brine reachable by early Phase 2 and chlor-alkali a Phase 2 capability. The chemical-process inventory lists HCl synthesis from hydrogen and chlorine as a candidate.

## Decision

Use the hydrogen and chlorine coproducts of Phase 2 chlor-alkali electrolysis to synthesize the initial HCl charge and makeup for the standard trichlorosilane route. HCl recovery from chlorinated-organic chemistry is not required for the initial CPU path and may remain a later supplemental capability.

The startup buffer, HCl loss/makeup rates, exact balances and process details, and a useful downstream consumer for chlor-alkali sodium hydroxide remain open. Surplus NaOH may be disposed under [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md); choosing a useful consumer is not a prerequisite for the initial HCl route.

## Options Considered

1. **Synthesize HCl from chlor-alkali hydrogen and chlorine coproducts.** Accepted; uses a Phase 2 chemical capability and provides a direct startup source.
2. **Use HCl recovery from chlorinated-organic chemistry as the primary source.** Not selected; its availability timing is not established for the initial CPU path.
3. **Leave the HCl source open.** Not selected; the user chose chlor-alkali coproduct synthesis as the standard source.

## Rationale

The selected route establishes an upstream source for the initial HCl charge without depending on later chlorinated-organic production. HCl recycle in polysilicon deposition limits the makeup demand, while the exact startup inventory and process losses remain available for later route balancing.

## Consequences

- Positive: The selected silicon-purification chain now has a standard Phase 2 source for HCl startup and makeup.
- Negative or trade-offs: Chlor-alkali operation produces sodium hydroxide as an additional coproduct; a useful downstream consumer remains unselected, while surplus disposal consumes power and produces pollution under ADR-0035. HCl startup inventory and losses are not yet quantified.
- Follow-up work: Evaluate an optional useful NaOH consumer alongside the brine and chlor-alkali balance, HCl buffer and makeup rates, and detailed process/equipment requirements. Do not require chlorinated-organic HCl recovery or a useful NaOH consumer for initial CPU supply.

## Affected Design and Related Decisions

- Design documents: [Chemical Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0032](ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md), [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md), and [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md).
- Supersedes / superseded by: No prior decision is superseded. This selects the HCl startup and makeup source for the polysilicon route in ADR-0032; the Phase 2 salt/brine boundary in ADR-0021 remains in force.
