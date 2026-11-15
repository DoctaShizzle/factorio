# ADR-0054: Select Fates for Depleted-UF6 Deconversion Outputs

*Status: Accepted*
*Decision date: Unknown*
*Last updated: Unknown*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).

## Context

[ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) requires Phase 2 handling for depleted-UF6 tails. [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) selects deconversion to uranium oxide and HF but leaves the outputs' downstream fates open.

## Decision

1. Recover the uranium oxide as a uranium-bearing coproduct for later uranium use. Its specific destination remains open; this does not designate it as reactor fuel or place it back into a particular point in the uranium fuel route.
2. Recover the HF for reuse in the Phase 2 UF6-conversion process. Its exact form, concentration, conditioning, role within that process, and integration remain open.
3. Keep the uranium-oxide and HF outputs distinct. This decision does not select exact chemistry, yields, inputs, quantities, facilities, material or power balances, or research gates; the numeric uranium-fuel enrichment target remains deferred under [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md).

## Options Considered

1. **Recover both outputs for later uranium use and UF6 conversion, respectively.** Selected; it gives each deconversion output a defined high-level role while leaving detailed process design open.
2. **Store either output without assigning a later use.** Not selected as the baseline disposition.
3. **Dispose of either output without recovering it for use.** Not selected as the baseline disposition.

## Rationale

These output fates retain the uranium-bearing coproduct for later uranium use and return HF to UF6 conversion. They establish useful destinations without deciding exact product forms, conditioning steps, recipes, or balances.

## Consequences

- Positive: both depleted-UF6 deconversion outputs have a selected high-level fate.
- Trade-offs: the uranium-oxide output has no specified next process, and HF reuse requires detailed form, conditioning, compatibility, and make-up/loss balancing.
- Follow-up work: define exact output forms and grades, HF conditioning and integration into UF6 conversion, process inputs and yields, facilities, material and power balances, and research gates.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).
- Related ADRs: [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium form sequence; [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) selects the fluorine-bearing feed family and access timing; [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) defers the numeric enrichment target; [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) requires Phase 2 tails handling; [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) selects the deconversion route.
- Supersedes / superseded by: No prior decision is superseded. This resolves the output-fate follow-up to ADR-0053; detailed forms and implementation remain open.
