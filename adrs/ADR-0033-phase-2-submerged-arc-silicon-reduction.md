# ADR-0033: Select Carbothermic Quartz Reduction in a Phase 2 Submerged-Arc Furnace

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), and [Plan](../plan.md).

## Context

[ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects quartz as the mineral feed for metallurgical silicon, and [ADR-0031](ADR-0031-starting-region-access-to-cpu-feed-families.md) requires starting-region access to quartz. [ADR-0032](ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md) selects the downstream route from metallurgical silicon to electronic-grade polysilicon, leaving quartz reduction open.

The current candidate reaction is carbothermic reduction, `SiO2 + 2C -> Si + 2CO`. Industrial silicon production requires temperatures well above the 1200°C capability attributed to the Phase 2 rotary kiln in Infrastructure, while the listed electric-arc furnace is scoped to scrap and direct-reduced iron.

## Decision

Use carbothermic reduction of quartz/silica with carbon in a dedicated Phase 2 submerged-arc silicon furnace to produce metallurgical silicon for the selected trichlorosilane route.

This selects the route and dedicated facility family, not the quartz preparation, reductant mix, exact recipe, product grade, yields, furnace construction materials, or research gate. CO may be released through the powered, pollution-producing disposal policy in [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md); a useful CO sink is not required.

## Options Considered

1. **Dedicated Phase 2 submerged-arc silicon furnace** — Accepted; provides a dedicated high-temperature facility for the selected carbothermic route.
2. **Reuse the general electric-arc furnace as a silicon-reduction subtype** — Not selected; the user chose a dedicated silicon furnace rather than folding this operation into the general EAF family.
3. **Use the Phase 2 rotary kiln** — Not selected; its documented 1200°C capability is insufficient for industrial silicon reduction.
4. **Select the chemistry but defer the furnace family** — Not selected; the user selected both the carbothermic route and its dedicated facility family.

## Rationale

The selected route establishes the upstream mineral-to-silicon link required by the accepted Phase 2 polysilicon pathway. A dedicated submerged-arc furnace reflects the high-temperature industrial process and avoids treating the rotary kiln or general scrap-melting EAF as equivalent equipment.

## Consequences

- Positive: Quartz now has a selected route to the metallurgical silicon required by the standard late-Phase-2 CPU chain.
- Negative or trade-offs: The route adds a dedicated Phase 2 facility and produces CO that needs an acceptable handling or use path.
- Follow-up work: Define quartz preparation, carbon reductant supply and balance, grades, yields, process values, furnace construction materials, research gates, and the CO disposal recipe, balance values, and gate under ADR-0035.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md), [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md), [ADR-0031](ADR-0031-starting-region-access-to-cpu-feed-families.md), [ADR-0032](ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md), and [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md).
- Supersedes / superseded by: No prior decision is superseded. This selects the quartz-reduction route upstream of the polysilicon route in ADR-0032; the feed-family and starting-region access decisions in ADR-0029 and ADR-0031 remain in force.
