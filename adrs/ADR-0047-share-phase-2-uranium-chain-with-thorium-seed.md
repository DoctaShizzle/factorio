# ADR-0047: Supply the Thorium Startup Seed from the Shared Uranium Chain

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Mod Overview](../mod-overview.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).

## Context

[ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects a uranium-derived fissile startup seed for the thorium route, followed by a U-233 breeding/reprocessing gameplay model without continuous uranium top-up. [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects gas-centrifuge enrichment for the Phase 2 uranium route but leaves its relationship to the thorium seed open.

## Decision

Use the shared Phase 2 uranium preparation/conversion/enrichment chain to supply the thorium startup seed. The seed may still require a distinct product form or thorium-specific preparation; this decision does not select its composition, identity, enrichment level, quantity, or final fuel form.

## Options Considered

1. **Use the shared uranium chain.** Selected; one uranium supply chain serves the uranium-fission route and provides the thorium route's startup seed.
2. **Use a separate uranium-derived seed input.** Not selected; this would retain a distinct uranium supply path for the thorium startup seed.
3. **Defer the relationship until fuel balances are available.** Not selected; the shared-chain dependency is now established, while the seed details and balances remain open.

## Rationale

Sharing the uranium chain makes the startup dependency explicit without introducing a second uranium source path. Leaving the seed's final form and any thorium-specific processing open preserves the remaining design work.

## Consequences

- Positive: the thorium startup seed has a defined upstream source in the Phase 2 uranium chain.
- Trade-offs: the shared uranium chain must support both uranium-fuel demand and thorium startup-seed demand; the combined material, power, and waste balance remains to be validated.
- Follow-up work: the shared uranium chain's high-level concentrate/UF6/centrifuge/UO2 sequence is selected under [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md). Determine the seed's composition, item identity, enrichment level, quantity, branch point, any additional preparation, and research gates; include its demand in the uranium and thorium route balances.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Mod Overview](../mod-overview.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the uranium-derived seed and thorium breeding/reprocessing model; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 for uranium fission; [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects gas-centrifuge enrichment for the shared uranium chain; [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects its high-level chemical-form sequence.
- Supersedes / superseded by: No prior decision is superseded. This resolves the seed-source relationship left open by ADR-0023 and ADR-0046; seed-specific details remain open.
