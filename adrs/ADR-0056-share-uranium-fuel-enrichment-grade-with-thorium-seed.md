# ADR-0056: Share the Uranium-Fuel Enrichment Grade with the Thorium Startup Seed

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects a uranium-derived fissile startup seed for the thorium route. [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) sources that seed from the shared Phase 2 uranium chain, while [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 pellets for the baseline uranium route. The seed's relationship to the uranium-fuel enrichment grade remained open. The numeric uranium-fuel target is deferred under [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md).

## Decision

1. Use the same qualitative uranium enrichment grade for the thorium startup seed as for the enriched UO2 fuel pellets in the baseline uranium-fission route.
2. Do not create a separate seed-specific enrichment grade or target. When the numeric uranium-fuel target is selected under ADR-0051, it applies to the startup seed as well.
3. This selects only the grade relationship. It does not select a numeric enrichment level, exact seed isotope composition or compound, item identity or form, quantity, or preparation route. The solid-oxide seed-and-blanket architecture remains as selected under [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md).

## Options Considered

1. **Use the uranium-fuel enrichment grade for the startup seed.** Selected; one qualitative enrichment grade serves both Phase 2 fuel paths, with the numeric target still deferred.
2. **Give the startup seed a distinct enrichment grade.** Not selected; it would add a separate seed-specific target and complicate the shared uranium chain.
3. **Defer the grade relationship until fuel-cycle balances are designed.** Not selected; the user selected a shared grade while leaving the numeric target and detailed balances open.

## Rationale

Sharing the grade is consistent with the selected shared uranium chain and avoids creating a second enrichment target. Deferring the numeric value preserves the existing requirement to choose it alongside detailed recipes, tails, and material and power balances.

## Consequences

- Positive: the startup seed does not require a separate uranium enrichment grade or target.
- Negative or trade-offs: the eventual target must support both the uranium-fuel route and the thorium startup-seed role; detailed fuel-cycle work must validate their compatibility.
- Follow-up work: select the numeric enrichment target before approving detailed fuel recipes or final balances. Define the seed's exact compound, isotope composition, item identity, quantity, branch point, and preparation route, and include its demand in the shared-chain balances.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the thorium startup-seed and breeding model; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 for the uranium route; [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects the enrichment method; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium-chain source; [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) defers the numeric target; [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) selects the thorium fuel architecture.
- Supersedes / superseded by: No decision is superseded. This resolves the enrichment-grade relationship left open by ADR-0042, ADR-0046, and ADR-0047 without selecting the deferred numeric target.
