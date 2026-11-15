# ADR-0046: Select Gas-Centrifuge Enrichment for Phase 2 Uranium Fuel

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).

## Context

[ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 pellets for the Phase 2 uranium fission route but leaves the enrichment method open. [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires those pellets to be clad and assembled before reactor use. Separately, [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) requires a uranium-derived fissile startup seed for the thorium route, while leaving its composition and relationship to the uranium-fuel chain open.

The U.S. Energy Information Administration describes gas centrifuges as the method used at the operating U.S. enrichment plant and notes gaseous diffusion as another process used historically ([The Nuclear Fuel Cycle](https://www.eia.gov/energyexplained/nuclear/the-nuclear-fuel-cycle.php)).

## Decision

1. Select gas-centrifuge enrichment for the Phase 2 uranium-fuel route.
2. This selects the enrichment method only. The high-level uranium-concentrate/UF6/UO2 form sequence is selected under [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md); the numeric enrichment target is deferred under [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) until detailed recipe and balance design. Upstream feed recovery, detailed conversion and reconversion chemistry, equipment layout and integration, material and power balances, the depleted-UF6 deconversion route to uranium oxide and HF selected under [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md), uranium-oxide recovery and HF reuse selected under [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md), exact forms, conditioning, pellet preparation, and research gates remain open.
3. This ADR does not decide whether or how the uranium route supplies the thorium cycle's startup seed. The shared-chain source is selected under [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md), and the seed uses the same qualitative enrichment grade as uranium fuel under [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md). The numeric target and exact seed composition, identity, and preparation remain open under ADR-0051 and the related thorium ADRs.

## Options Considered

1. **Gas-centrifuge enrichment.** Selected; it is a contemporary industrial method and provides a concrete Phase 2 route direction without fixing detailed plant design.
2. **Gaseous-diffusion enrichment.** Not selected; it is a historically used alternative, but no distinct gameplay need has been established to prefer it.
3. **Leave the enrichment method abstract.** Not selected; the enrichment capability is already required, and selecting a method clarifies the trunk without requiring recipe-level detail.

## Rationale

The centrifuge method aligns the Phase 2 uranium route with a contemporary, industrially demonstrated enrichment technology. It resolves the technology choice while preserving the open work on feed conversion, equipment configuration, balance, waste, and progression.

## Consequences

- Positive: the Phase 2 uranium route has an explicit enrichment method that can inform later process and infrastructure design.
- Trade-offs: the route depends on a centrifuge-enrichment capability; its construction footprint, power use, throughput, and operating costs have not been selected.
- Follow-up work: [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level sequence from uranium concentrate through UF6 centrifuge enrichment to UO2. Resolve feed recovery, detailed conversion/reconversion chemistry and reagent supply, the deferred target before detailed recipes and final balances, exact forms and implementation for the output fates selected under [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md), equipment integration, balances, and research gates. The shared uranium chain supplies the thorium startup seed under [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md); the seed uses the same qualitative enrichment grade under [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), while its exact form, quantity, and additional preparation remain open.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) selects the Phase 2 uranium and thorium options; [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) defines the thorium startup-seed model; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires Phase 2 cladding and rod assembly; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium chain for the thorium seed; [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects its high-level chemical-form sequence; [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) defers the numeric target until detailed recipe and balance design; [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) requires Phase 2 depleted-UF6 handling; [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) selects deconversion to uranium oxide and HF; [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) selects the outputs' high-level fates; [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) sets the shared grade relationship for the startup seed.
- Supersedes / superseded by: No prior decision is superseded. This resolves the enrichment-method follow-up in ADR-0042; ADR-0047 resolves the seed-source follow-up. The remaining uranium conversion and fuel-cycle details stay open.
