# ADR-0042: Require Enriched UO2 for Phase 2 Uranium Fission

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0041](ADR-0041-phase-2-direct-use-fission-fuel.md) selected an unclad UO2 pellet as the Phase 2 uranium reactor's direct-use fuel item, but left open whether the uranium must be enriched. [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) later superseded that direct-use form and requires cladded fuel rods; the enriched UO2 pellet remains the uranium rod-fabrication input.

## Decision

1. The baseline Phase 2 uranium fission route requires enriched UO2 fuel pellets.
2. The enrichment capability must be available on the Phase 2 route before enriched UO2 pellets can be produced and assembled into the required fuel rods.
3. This ADR selects the enrichment requirement. Gas-centrifuge enrichment is selected under [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md), and the UF6-based high-level chemical-form path is selected under [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md). The enrichment target, detailed conversion/reconversion chemistry and reagents, equipment, material and power balances, waste handling, recipes, and research gates remain open.
4. This decision does not determine the isotope composition or preparation route for the uranium-derived startup seed in the thorium cycle under [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md).
5. Natural-uranium UO2 is not part of the baseline uranium route; adding it would require a separate reactor/fuel-route decision.

## Options Considered

1. **Require enriched UO2 for the baseline uranium route.** Selected; it aligns the route with the existing enriched-oxide candidate and makes enrichment part of the Phase 2 fuel chain.
2. **Use natural-uranium UO2 in a neutron-efficient reactor design.** Not selected; it would require a distinct moderator/coolant and reactor configuration decision.
3. **Defer the enrichment requirement until the uranium reactor design is selected.** Not selected; it would leave the baseline uranium fuel chain materially ambiguous.

## Rationale

The uranium option should have a defined isotope-processing requirement before its material and research path is detailed. Selecting enriched UO2 establishes that capability boundary without prematurely choosing a specific enrichment technology or reactor implementation.

## Consequences

- Positive: the Phase 2 uranium route has a clear baseline fuel requirement and can be evaluated against the thorium cycle as a separate power option.
- Trade-offs: Phase 2 uranium fission requires an enrichment capability and its associated material, power, and progression costs.
- Follow-up work: the high-level UF6-based chemical-form sequence is selected under [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), fluorspar feed/access under [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md), and Uraninite feed/access under [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md). Resolve Uraninite and fluorspar recovery, detailed conversion/reconversion chemistry and reagent preparation, enrichment target, depleted-tails handling, material and power balances, equipment, recipes, and research gates; the seed's exact form and quantity remain open under [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md).

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) selects Phase 2 uranium and thorium power options; [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the thorium startup-seed model; [ADR-0036](ADR-0036-phase-2-minimum-fission-fuel-path.md) and [ADR-0041](ADR-0041-phase-2-direct-use-fission-fuel.md) record superseded fuel boundaries; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires cladded rod assemblies; [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects the gas-centrifuge enrichment method; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium-chain source for the thorium seed; [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium chemical-form path.
- Supersedes / superseded by: Sets the uranium enrichment requirement. ADR-0043 supersedes ADR-0041's unclad-pellet input boundary while retaining the enriched UO2 requirement.
