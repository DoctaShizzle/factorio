# ADR-0057: Require Phase 2 Reprocessing for Spent Uranium Fuel

*Status: Accepted; recovered-stream and residual-destination deferrals partially superseded by [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md) and [ADR-0068](ADR-0068-continuous-nuclear-waste-disposal.md)*
*Decision date: 2026-11-15*
*Last updated: 2026-11-16*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Technical Architecture](../technical-architecture.md), and [Plan](../plan.md).

## Context

The Phase 2 uranium-fission path converts uranium feed through UF6 enrichment and UO2 fuel fabrication before reactor use. The depleted-UF6 tails decisions under [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md), [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md), and [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) concern a separate stream produced before fuel fabrication, not discharged reactor fuel. The thorium route has its own U-233 breeding and reprocessing model under [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) and its solid-oxide architecture under [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md).

The post-discharge fate of spent uranium fuel remained open. The Power System also contained an optional plutonium-extraction candidate linked to military ammunition and a candidate spent-fuel storage-pool concept; neither had been selected.

## Decision

1. Require a Phase 2 post-discharge reprocessing/recovery branch for spent uranium fuel. This establishes a required capability, not a closed fuel cycle or a specific recovered product.
2. Keep the recovered streams and their uses, process chemistry, residual waste, storage or containment, equipment, material and power balances, and research gate open for detailed fuel-cycle design.
3. Do not infer plutonium extraction, a plutonium output, a military-ammunition link, or a specific storage-pool design from this decision.
4. Keep this branch distinct from depleted-UF6 tails handling under ADR-0052 through ADR-0054 and from the thorium U-233 cycle under ADR-0023 and ADR-0055.

## Options Considered

1. **Treat spent uranium fuel as a bounded inventory without a recovery route.** Not selected; the user chose reprocessing rather than leaving discharged fuel as an accumulating byproduct.
2. **Require post-discharge reprocessing/recovery while deferring its products and implementation.** Selected; this establishes the required fuel-cycle capability without inventing outputs or process details.
3. **Select plutonium extraction and connect it to nuclear ammunition.** Not selected; this was only a candidate in the Power System and was not part of the user's decision.

## Rationale

Requiring the branch gives spent uranium fuel an explicit post-discharge handling path while avoiding unsupported choices about recovered materials, waste, or military use. Keeping its implementation open allows those details to be resolved with the fuel-cycle chemistry and balances.

## Consequences

- Positive: the Phase 2 uranium-fission route must account for post-discharge recovery rather than treating spent fuel as disposal-only inventory.
- Negative or trade-offs: the route has an additional required capability whose material outputs, residues, process, and progression gate are not yet defined.
- Follow-up work: establish recovered streams and fates, residual-waste handling, any storage or containment needs, process and equipment boundaries, balances, and the research gate during detailed Phase 2 fuel-cycle design.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Technical Architecture](../technical-architecture.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) and [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) define the separate thorium cycle; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md), [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md), and [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) define the Phase 2 uranium fuel path; [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md), [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md), and [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) define the distinct depleted-UF6 tails path.
- Supersedes / superseded by: No prior decision is superseded. [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md) and [ADR-0068](ADR-0068-continuous-nuclear-waste-disposal.md) partially supersede the recovered-stream and residual-destination deferrals. [ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md) preserves the superseded finite-capacity endpoint. The required Phase 2 recovery capability and exclusion of inferred plutonium/military links remain in force; the original decision text above is preserved.
