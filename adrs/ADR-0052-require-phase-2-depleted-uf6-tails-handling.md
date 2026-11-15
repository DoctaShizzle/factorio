# ADR-0052: Require Phase 2 Handling for Depleted UF6 Tails

*Status: Accepted*
*Decision date: Unknown*
*Last updated: Unknown*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).

## Context

[ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium-concentrate -> UF6 -> gas-centrifuge enrichment -> UO2 sequence and tracks enriched UF6 and depleted-UF6 tails separately, but does not choose how the tails are handled. [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) defers the numeric enrichment target, not the need to account for the tails. The U.S. Department of Energy's [DUF6 Conversion Project](https://www.energy.gov/pppo/depleted-uranium-hexafluoride-duf6-conversion) is one real-world example: it converts stored DUF6 into uranium oxide and hydrofluoric acid, with the oxide available for storage, reuse, or disposal. That route is evidence for a candidate, not an accepted design choice. The general gas/fluid disposal policy under [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md) does not itself assign a handling route to depleted UF6. The route selected after this requirement decision is recorded in [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md).

## Decision

1. The Phase 2 uranium fuel cycle must include an explicit capability to handle depleted-UF6 tails.
2. Keep enriched UF6 and depleted-UF6 tails as separate streams under ADR-0048. This ADR does not select the tails' route, physical form, products, facility, quantities, use, disposal, or research gate.
3. This ADR does not designate the Gas Flare Stack, Liquid Effluent Clarifier, or any other existing facility as the tails route. Select the route before approving detailed uranium-fuel recipes and final material/power balances, and before treating the Phase 2 uranium cycle as complete.

## Options Considered

1. **Require Phase 2 tails handling while leaving the route open for follow-up.** Selected; the uranium process chain must account for its separate tails stream without prematurely choosing its treatment.
2. **Track the tails but defer all handling beyond Phase 2.** Not selected; that would leave a required Phase 2 fuel-cycle output without a Phase 2 handling capability.
3. **Select a specific handling route in this decision.** Not selected; the handling requirement is established here, and route selection is a separate follow-up decision.

## Rationale

Requiring a Phase 2 capability makes depleted-UF6 tails an explicit part of the uranium fuel-cycle design rather than an implicit loss or an unaccounted coproduct. Keeping the route open preserves the user's requested boundary between setting the requirement and selecting a process, facility, or disposition.

## Consequences

- Positive: depleted-UF6 handling is a Phase 2 dependency and must be represented in the fuel-cycle design.
- Negative or trade-offs: the selected route may add process outputs, a facility or storage step, material and power demands, waste obligations, and research gates; none are selected yet.
- Follow-up work: the deconversion route to uranium oxide and HF is selected under [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md), and the outputs' high-level fates are selected under [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md). Define exact output forms and conditioning, the process/facility boundary, inputs and outputs, material and power balances, and progression gate.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).
- Related ADRs: [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md) sets the general gas/fluid-disposal policy; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 for uranium fission; [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects gas-centrifuge enrichment; [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium form sequence and separate tails stream; [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) defers only the numeric enrichment target; [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) selects the handling route; [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) selects the outputs' high-level fates.
- Supersedes / superseded by: No prior decision is superseded. This resolves whether Phase 2 must include a depleted-UF6 handling capability; ADR-0053 resolves its route, and ADR-0054 resolves the outputs' high-level fates.
