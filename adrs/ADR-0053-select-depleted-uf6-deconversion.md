# ADR-0053: Select Deconversion of Depleted UF6 to Uranium Oxide and HF

*Status: Accepted*
*Decision date: Unknown*
*Last updated: Unknown*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).

## Context

[ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) tracks depleted-UF6 tails separately from enriched UF6. [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) requires an explicit Phase 2 handling capability while leaving its route open. The U.S. Department of Energy's [DUF6 Conversion Project](https://www.energy.gov/pppo/depleted-uranium-hexafluoride-duf6-conversion) describes converting stored DUF6 into uranium oxide and hydrofluoric acid (HF), making deconversion a real-world precedent for the follow-up route decision.

## Decision

1. Deconvert the Phase 2 depleted-UF6 tails into uranium oxide and HF as the selected high-level handling route.
2. Keep the depleted-UF6 stream separate from enriched UF6 and uranium fuel. This selects only the output families and deconversion direction; exact oxide phase, HF form/concentration, chemistry, yields, inputs, and balances remain open.
3. The downstream fates are selected under [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md): recover uranium oxide for later uranium use and HF for reuse in the UF6-conversion process. This does not assign the oxide to reactor fuel or specify its later destination, nor does it fix HF's exact form, concentration, conditioning, or process integration.
4. The numeric uranium-fuel enrichment target remains deferred under [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md); this route decision does not choose that target or a tails quantity.

## Options Considered

1. **Deconvert depleted UF6 to uranium oxide and HF.** Selected; it provides an established deconversion direction and produces a stable uranium-oxide stream plus a potentially useful fluorine-bearing coproduct.
2. **Store depleted UF6 in sealed cylinders without deconversion.** Not selected; storage remains a possible handling step but does not implement the chosen deconversion route.
3. **Re-enrich the tails as a recovery loop.** Not selected; it would add enrichment throughput and power demand and could constrain the still-deferred enrichment target.
4. **Track the tails without a Phase 2 handling route.** Not selected under ADR-0052.

## Rationale

Deconversion changes the tails from UF6 into a more stable uranium-oxide form and recovers HF as a coproduct, giving the Phase 2 process chain an explicit treatment direction. ADR-0054 selects high-level fates for both outputs; exact chemistry, product grades, conditioning, and balances remain open.

## Consequences

- Positive: the Phase 2 uranium chain has a defined direction for handling its depleted-UF6 stream and identifies uranium oxide and HF as high-level outputs.
- Negative or trade-offs: the route adds a deconversion capability and two output streams whose exact forms, conditioning, and balance impacts are unresolved.
- Follow-up work: define exact output forms and grades, HF conditioning and integration into UF6 conversion, process chemistry, facility needs, recipes, material/power/waste balances, and research gates.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).
- Related ADRs: [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md) sets the general gas/fluid-disposal policy; [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium form sequence and separate tails stream; [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) defers the numeric enrichment target; [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) requires Phase 2 tails handling; [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) selects the outputs' high-level fates.
- Supersedes / superseded by: No prior decision is superseded. This resolves the handling-route follow-up to ADR-0052; ADR-0054 resolves the output-fate follow-up. Exact forms and implementation remain open.
