# ADR-0051: Defer the Phase 2 Uranium-Fuel Enrichment Target

*Status: Accepted*
*Decision date: Unknown*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).

## Context

Phase 2 uranium fuel requires enriched UO2 under [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md), uses gas-centrifuge enrichment under [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md), and follows the selected uranium-concentrate -> UF6 -> enriched/depleted UF6 -> UO2 form sequence under [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md). The uranium and fluorine-bearing mineral feeds are selected under [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) and [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md). A numeric enrichment target is still needed for detailed recipes and balances. ADR-0048 cites 3%–5% U-235 as a commercial-reactor reference only, not as a target for this design.

## Decision

1. Keep the baseline Phase 2 uranium-fuel identity at the qualitative level of enriched UO2; do not assign a numeric U-235 target or recipe grade yet.
2. Defer selection of the numeric uranium-fuel target until detailed recipe and balance design begins. Resolve it before approving enrichment/fuel recipe quantities or final material and power balances.
3. Keep the 3%–5% U-235 range as background only. It is not a game requirement, selected target, or recipe parameter.
4. Continue tracking enriched UF6 and depleted-UF6 tails as separate streams under ADR-0048. Phase 2 tails handling is required under [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md), and the deconversion route is selected under [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md); this ADR does not select tails quantities.
5. The thorium startup seed uses the same qualitative uranium enrichment grade under [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md). The numeric target deferred here therefore applies to both routes; the seed's exact compound, isotope composition, item identity, quantity, and preparation remain open under [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) and [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md).

## Options Considered

1. **Defer the numeric uranium-fuel target until detailed recipe and balance design.** Selected; preserves the accepted high-level trunk while preventing unsupported recipe or balance assumptions.
2. **Adopt the cited 3%–5% U-235 commercial-reactor reference as the design target now.** Not selected; the reference is background, not an accepted game requirement.
3. **Select a different numeric target now.** Not selected; the detailed process and material/power balance are not yet designed.

## Rationale

The selected fuel identity, feed families, chemical-form sequence, and enrichment method are sufficient to define the Phase 2 uranium trunk without assigning a numeric grade. The target should be determined as detailed recipes and balances are developed, where enrichment yield, depleted tails, throughput, and power demand can be assessed together.

## Consequences

- Positive: the Phase 2 trunk avoids prematurely treating a real-world reference range as a game parameter.
- Negative or trade-offs: enrichment throughput, tails quantity, detailed fuel composition, and related material and power balances cannot be finalized before the target is selected.
- Follow-up work: select the target before approving detailed enrichment/fuel recipes or final material and power balances; the thorium startup seed shares that target under ADR-0056 rather than receiving a separate grade. Implement the output fates selected under [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) and define their exact forms and balances.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2; [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) selects gas centrifuges; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium-chain source for the thorium seed; [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium form sequence; [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) selects fluorspar; [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) selects Uraninite; [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) requires Phase 2 tails handling; [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) selects deconversion to uranium oxide and HF; [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) selects the outputs' high-level fates; [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) selects the same qualitative enrichment grade for the thorium seed.
- Supersedes / superseded by: No prior decision is superseded. This resolves the timing and guardrails for selecting the numeric uranium-fuel enrichment target while leaving its value open.
