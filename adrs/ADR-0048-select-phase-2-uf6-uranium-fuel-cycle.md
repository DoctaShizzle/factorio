# ADR-0048: Select a UF6-Based Phase 2 Uranium Fuel-Cycle Path

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 pellets for the Phase 2 uranium route. [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects gas-centrifuge enrichment, and [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium chain as the source for the thorium startup seed. The high-level chemical forms around enrichment remained open.

The U.S. Energy Information Administration describes the conventional sequence as uranium concentrate (typically U3O8 yellowcake) converted to UF6 gas, centrifuge enrichment, then reconversion of enriched UF6 to UO2 for fuel fabrication. It gives 3%–5% U-235 as a current U.S. commercial-reactor reference, not a universal target for this design ([The Nuclear Fuel Cycle](https://www.eia.gov/energyexplained/nuclear/the-nuclear-fuel-cycle.php)).

## Decision

1. Use uranium concentrate as the high-level feed to a conversion path that produces UF6 gas. Uraninite is the selected mined feed under [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md); U3O8 yellowcake is the real-world reference form, and the upstream recovery route remains open.
2. Feed gaseous UF6 to the selected gas-centrifuge enrichment stage. Track enriched UF6 and depleted-UF6 tails as separate streams.
3. Reconvert enriched UF6 to UO2 powder for the enriched-oxide pellets required by [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) and the rod route required by [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md).
4. The shared uranium chain continues to supply the thorium startup seed under [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md). This ADR does not select the seed's branch point or its exact composition, enrichment, quantity, or product form.
5. Treat the 3%–5% U-235 figure as background only. This ADR does not select an enrichment target for uranium fuel or the thorium seed.
6. This selects high-level chemical-form interfaces only. The fluorine-feed family and access timing are selected under [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md); exact conversion/reconversion chemistry, fluorine-reagent form and preparation, enrichment target, tails disposition, yields, material and power balances, equipment split, recipes, and research gates remain open.

## Options Considered

1. **Use the conventional UF6 conversion, centrifuge, and UO2 reconversion sequence.** Selected; it aligns the already-selected centrifuge method and enriched-UO2 fuel requirement with a real-world industrial fuel-cycle pathway.
2. **Keep the uranium chemical forms abstract until detailed process design.** Not selected; this would leave the Phase 2 material trunk underspecified despite the selected enrichment technology and fuel form.

## Rationale

The UF6 route provides the clearest high-level match to commercial gas-centrifuge enrichment while connecting the selected uranium-concentrate feed boundary to the enriched UO2 fuel requirement. Stopping at material-form interfaces preserves the remaining chemistry, engineering, balance, and progression decisions for later design.

## Consequences

- Positive: the Phase 2 uranium route has a defined high-level sequence from uranium concentrate through UF6 enrichment to UO2 fuel fabrication, with a shared upstream chain for the thorium seed.
- Trade-offs: the route requires fluorine-bearing process inputs and produces a depleted-UF6 tails stream that must be accounted for.
- Follow-up work: resolve Uraninite and fluorspar recovery, detailed conversion chemistry and reagent preparation, enrichment target, tails handling, equipment integration, material and power balances, recipe scope, and research gates. Include the thorium seed's demand and any additional preparation in the shared-chain balance.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) sets the thorium startup-seed and U-233 gameplay model; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires cladded rods; [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects gas centrifuges; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium-chain source for the seed; [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) selects the fluorspar feed family and access timing; [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) selects the mined uranium feed and access timing.
- Supersedes / superseded by: No prior decision is superseded. This resolves the high-level uranium chemical-form sequence left open by ADR-0042, ADR-0046, and ADR-0047; detailed chemistry and implementation remain open.
