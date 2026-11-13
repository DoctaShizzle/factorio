# ADR-0040: Select Phase 2 LFP Feed Sources and Access

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Plan](../plan.md).

## Context

[ADR-0039](ADR-0039-phase-2-lfp-battery-storage.md) selects LFP as the initial Phase 2 battery cathode chemistry and requires lithium and phosphate feeds by the storage unlock. The mineral design lists spodumene and lithium-bearing brine as lithium-source candidates and apatite as a phosphate source, but source families and starting-area access were unresolved.

## Decision

- Use spodumene and lithium-bearing brine as alternative sources of lithium for Phase 2 LFP storage. A single initial supply route needs only one source.
- Use apatite-rich phosphorite as the phosphate feed for Phase 2 LFP storage.
- Guarantee starting-region access to apatite-rich phosphorite and lithium-bearing brine. Spodumene remains an alternative source and may be regional.
- The required lithium and phosphate feeds remain available by the LFP storage unlock under ADR-0039. This decision does not select extraction or recovery routes, grades, quantities, exact deposit placement, spodumene access timing, or recipes.

## Options Considered

1. **Spodumene-only lithium supply.** Not selected; it would omit the brine source direction.
2. **Brine-only lithium supply.** Not selected; it would omit the hard-rock source direction.
3. **Spodumene and brine as alternative lithium sources.** Selected; brine is the starting-region source, and spodumene remains an alternative that may be regional. The initial LFP chain does not require both sources simultaneously.
4. **Apatite-rich phosphorite as the phosphate feed.** Selected; other phosphate-source families are not selected for the initial LFP chain.
5. **Starting-area access to both lithium sources and phosphate.** Not selected; the starting region guarantees apatite-rich phosphorite and lithium-bearing brine, while spodumene may be regional.

## Rationale

Apatite-rich phosphorite fits the existing sedimentary-basin deposit model and provides a clear phosphate feed without fixing the chemical recovery route. Reachable salt/brine is already part of the early Phase 2 map direction under ADR-0021, making lithium-bearing brine the most direct starting-area source. Spodumene preserves a distinct hard-rock alternative without requiring its mountain-range deposit setting near the start.

## Consequences

- Positive: The initial LFP chain has explicit starting-region access to apatite-rich phosphorite and lithium-bearing brine, while retaining spodumene as an alternative lithium source.
- Negative or trade-offs: A lithium recovery path and phosphate processing path are required in Phase 2; their detailed designs remain open.
- Follow-up work: Design brine-lithium recovery, phosphate conversion, grades, quantities, and the remaining battery cell/pack route; determine whether and when the optional regional spodumene route is available.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Plan](../plan.md).
- Related ADRs: [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0031](ADR-0031-starting-region-access-to-cpu-feed-families.md), [ADR-0039](ADR-0039-phase-2-lfp-battery-storage.md).
- Supersedes / superseded by: None.
