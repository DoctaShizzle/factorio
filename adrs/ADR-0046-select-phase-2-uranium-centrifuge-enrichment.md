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
2. This selects the enrichment method only. Uranium feed preparation, conversion and reconversion chemistry, output forms, enrichment target, equipment layout and integration, material and power balances, waste handling, pellet preparation, and research gates remain open.
3. This does not decide whether or how the uranium route supplies the thorium cycle's startup seed. The seed remains a thorium-route prerequisite only; its composition, item identity, and production relationship remain open under ADR-0023.

## Options Considered

1. **Gas-centrifuge enrichment.** Selected; it is a contemporary industrial method and provides a concrete Phase 2 route direction without fixing detailed plant design.
2. **Gaseous-diffusion enrichment.** Not selected; it is a historically used alternative, but no distinct gameplay need has been established to prefer it.
3. **Leave the enrichment method abstract.** Not selected; the enrichment capability is already required, and selecting a method clarifies the trunk without requiring recipe-level detail.

## Rationale

The centrifuge method aligns the Phase 2 uranium route with a contemporary, industrially demonstrated enrichment technology. It resolves the technology choice while preserving the open work on feed conversion, equipment configuration, balance, waste, and progression.

## Consequences

- Positive: the Phase 2 uranium route has an explicit enrichment method that can inform later process and infrastructure design.
- Trade-offs: the route depends on a centrifuge-enrichment capability; its construction footprint, power use, throughput, and operating costs have not been selected.
- Follow-up work: define the upstream and downstream uranium conversion path, equipment integration, output forms, balances, waste handling, and research gates. The shared uranium chain supplies the thorium startup seed under [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md); the seed's exact form, quantity, and additional preparation remain open.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) selects the Phase 2 uranium and thorium options; [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) defines the thorium startup-seed model; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires Phase 2 cladding and rod assembly; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium chain for the thorium seed.
- Supersedes / superseded by: No prior decision is superseded. This resolves the enrichment-method follow-up in ADR-0042; ADR-0047 resolves the seed-source follow-up. The remaining uranium conversion and fuel-cycle details stay open.
