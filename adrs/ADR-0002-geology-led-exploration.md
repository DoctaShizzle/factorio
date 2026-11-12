# ADR-0002: Geology-Led Exploration

*Status: Accepted*
*Decision date: 2026-11-06*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Mod Overview](../mod-overview.md), [Research and Progression](../research-progression.md).

## Context

The world map should shape industrial progression, and the player should learn to find resources rather than acquire them through an economy. This is described as the narrative core of Project Prometheus: the player progresses from dirt and ore toward planetary-scale construction. The source describes exploration as driven by geological necessity: the starting area is a foundation, while Phase 2+ materials motivate travel to other biomes. Resource depletion may create pressure, but should not be the only reason to explore.

## Decision

- The core design has no trade system or economy; materials used by the player are extracted and refined by the player.
- Resource distribution and geological need are primary exploration drivers.
- Prospecting uses a hybrid approach: handbook/Informatron teaches geological principles, while the player discovers exact deposits through observation and experience.
- Surface indicators and biome continuity may hint at deposits but should not provide exact coordinates.
- Simulation models may predict likely locations of high-value resources in Phase 3; players still prospect and travel to confirm them.

## Options Considered

1. **Explicit deposit guidance.** Give exact calls or coordinates in handbook material. This supports certainty but reduces discovery.
2. **Implicit discovery only.** Let players infer patterns from terrain and experience. This increases emergent discovery but may create excessive friction.
3. **Principles-based guidance.** Explain geological relationships without revealing exact material locations. This is the accepted hybrid.

## Rationale

Principles-based guidance supports “knowledge before capability” while retaining discovery. Player extraction and refining support the project's industrial journey; the map creates goals before and after the factory is established.

## Consequences

- Positive: exploration follows resource capability and learned geology rather than trading.
- Positive: late-game simulation can improve predictions without removing physical prospecting.
- Trade-off: the design must make clues useful without making resources arbitrary or unknowable.
- Follow-up: define starting-resource guarantees, surface indicators, and information progression alongside the mineral catalog and map-generation implementation.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Mod Overview](../mod-overview.md), [Research and Progression](../research-progression.md).
- Related ADRs: [ADR-0001](ADR-0001-geological-biome-layout.md), [ADR-0005](ADR-0005-map-scale-and-discovery-distances.md).
- Supersedes / superseded by: No superseding ADR recorded.
