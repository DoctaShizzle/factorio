# ADR-0005: Default Map Scale and Discovery Distances

*Status: Accepted with distance validation outstanding*
*Decision date: 2026-11-06*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Logistics System](../logistics-system.md), [Minerals and Refining](../minerals-and-refining.md).

## Context

Map size and resource distances should support the project's 300+ hour ambition in which Phase 1 can begin locally, while later materials motivate prospecting and logistics investment. The source includes several overlapping recommendations and example distances, some of which conflict.

## Decision

- Use x5 as the default map scale, with x4 and x6 selectable at world creation.
- The final committed decision table uses a 5–15 km radius for Phase 2 bridge materials and 20–40 km for rare late-game Phase 2/3 materials.
- Treat these distance ranges as planning targets, not tested or tuned generation guarantees.

## Options Considered

1. **Choose x4, x5, or x6 as the only scale.** The accepted decision selects x5 by default and exposes x4/x6 as alternatives.
2. **Place all necessary resources near the starting area.** This reduces exploration but conflicts with the committed geological progression intent.
3. **Use staged resource distances.** This supports local startup and later logistics-based exploration; the final source decision uses staged Phase 2 and rare-material ranges.

## Rationale

The source ties map scale to the project's long-play ambition and wants Phase 2 logistics to make distant resource access meaningful. The default plus selectable scales provide a baseline while preserving player choice.

## Consequences

- Positive: establishes a default scale and a progression-oriented distance target.
- Trade-off: the selected targets may imply substantial travel and logistics demands; feasibility and pacing are unvalidated.
- Follow-up: reconcile and test all values below before treating any as implementation requirements.

## Source Values Requiring Reconciliation

The source document contains all of the following values or ranges:

- Starting resources: within about 500 m in the draft progression; within about 2 km in the progression table and about 2 km to establish a sustainable base.
- Medium oil/salt cluster: about 2 km.
- Polymineral mountain cluster: about 3–8 km.
- Phase 2 materials: 3–10 km in the progression table; 5–10 km in the map-scale recommendation; 5–15 km in the final committed decision.
- Rare deposits: 15 km or farther in the cluster example; 20–40 km in the final committed decision.
- Map edge: 30–50 km from the starting origin in the map-scale recommendation.
- Biome adjacency: 2–3 km as a general learned expectation; 3–5 km for oil-to-iron in the specific sedimentary/shield rule.
- Informal continuity example: oil within about 2 km, with iron formations roughly another 3 km farther along the deposit chain.
- Earlier map-size recommendation: at least “very large” (x4 default), ideally x5–x6; later committed decision is x5 default with x4/x6 selectable.

These are preserved as source evidence, not silently harmonized. The selected values above come from the final committed decision table in the source; remaining discrepancies stay open.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Logistics System](../logistics-system.md), [Minerals and Refining](../minerals-and-refining.md).
- Related ADRs: [ADR-0001](ADR-0001-geological-biome-layout.md), [ADR-0002](ADR-0002-geology-led-exploration.md), [ADR-0004](ADR-0004-map-edge-pressure.md).
- Supersedes / superseded by: Later committed distance values supersede earlier recommendations only where they conflict; no tested implementation values or superseding ADR are recorded.
