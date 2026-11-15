# ADR-0050: Select Uraninite as the Phase 2 Uranium Feed

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Power System](../power-system.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects uranium concentrate as the high-level input to the Phase 2 UF6-based fuel cycle, but left the mined feed family and its access timing open. The current [Minerals and Refining](../minerals-and-refining.md) recovery matrix already lists Uraninite as a candidate source of uranium concentrate. The EIA fuel-cycle overview describes uranium concentrate, commonly U3O8 yellowcake, as the feed to UF6 conversion ([The Nuclear Fuel Cycle](https://www.eia.gov/energyexplained/nuclear/the-nuclear-fuel-cycle.php)).

## Decision

1. Select Uraninite as the baseline mined feed for the Phase 2 uranium-concentrate input to the uranium route under ADR-0048. U3O8/yellowcake remains a real-world reference form, not a fully specified in-game item.
2. Make limited Uraninite supply accessible no later than the UF6-conversion unlock. A starting-region guarantee is not required; exact deposit occurrence, placement, and quantity remain open.
3. The mineral matrix's listed thorium secondary output remains a candidate only. This decision does not select it as a required coproduct or as the source/form of the thorium startup seed.
4. This does not select uranium recovery chemistry, grade, yields, equipment, material or power balances, waste handling, recipes, or research gates.

## Options Considered

1. **Uraninite as the baseline mined feed, accessible by UF6-conversion unlock.** Selected; it promotes an existing mineral-catalog candidate to the feed required by the accepted Phase 2 uranium trunk.
2. **Keep the uranium-concentrate source and access abstract.** Not selected; this would leave the fission route's geological input and progression dependency unbounded.
3. **Choose a different uranium-bearing feed.** Not selected; no alternative feed family is selected in the current mineral catalog.

## Rationale

Selecting the existing Uraninite candidate gives the Phase 2 uranium route an explicit mined source while retaining uranium concentrate as the high-level chemical-form interface. Access by the conversion unlock is sufficient to support the selected route without imposing starting-area placement. Keeping thorium recovery as an unselected candidate avoids changing the separately selected shared-chain startup-seed model.

## Consequences

- Positive: the uranium-concentrate input now has a selected mineral feed and access boundary.
- Negative or trade-offs: limited Uraninite supply must be recoverable by the UF6-conversion unlock; deposit placement and the extraction/refining route remain open.
- Follow-up work: determine Uraninite recovery, grades, yields, quantities, deposit placement, process waste and balance, and research requirements. Do not treat the listed thorium secondary stream as an approved coproduct or seed input.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Power System](../power-system.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the uranium-concentrate/UF6/enrichment/UO2 form sequence; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium chain as the thorium startup-seed source while leaving seed specifics open.
- Supersedes / superseded by: No prior decision is superseded. This resolves the mined uranium feed family and access boundary left open by ADR-0048; recovery and the thorium secondary stream remain open.
