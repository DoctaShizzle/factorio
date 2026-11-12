# ADR-0001: Geological Biome Layout

*Status: Accepted*
*Decision date: 2026-11-06*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Mod Overview](../mod-overview.md).

## Context

World generation needs to create geological discovery without placing every resource everywhere or overwhelming players with many narrowly differentiated biomes. The project aims for a 300+ hour progression, but geological variety should remain learnable rather than reproduce the cognitive-load problem associated with hundreds of resource types in GTNH.

The earlier candidate design included six areas: sedimentary basin (oil, salt, limestone, evaporites); shield region (iron, nickel, copper); volcanic zone (sulfur, phosphates, gold/placer metals); river delta/alluvial (placer gold, tin, rare minerals); mountain range (polymineral bodies and high-grade veins); and coastal/shelf (saltwater brines and phosphorite).

The decision was revised in the 2026-11-06 source change. The earlier candidate table and open questions remain in repository history; the final source instead identifies four core biomes plus a coastal hybrid.

## Decision

Use four core biomes, each with at most three characteristic resource groups, and a coastal/shelf hybrid overlay. The committed mapping is:

- Sedimentary basin: oil, salt/limestone, phosphorite.
- Shield region: iron formations and copper-nickel sulfides.
- Mountain range: polymineral ore bodies, high-grade veins, and coal/seams.
- Volcanic zone: sulfur, precious metals (placer/gold), and rare mineral traces.
- Coastal/shelf: saltwater brines and evaporites, overlaid on the adjoining core biome.

Use fixed high-level adjacency: sedimentary borders shield; shield connects to mountain uplift; mountain borders volcanic; coastal areas can meet all core biomes. This commits to an adjacency pattern, not yet to precise distances or generator code.

## Options Considered

1. **Keep the six distinct candidate areas.** This retained river delta/alluvial as a separate resource region and listed more candidate resources per area.
2. **Use four core biomes plus a coastal hybrid.** This bounds the number of core geology types and treats coastal resources as an overlay.
3. **Use unrestricted randomized deposits.** This was the rejected contrast in the design: it would make resource expectation and geological learning less legible.

## Rationale

The accepted mapping preserves differentiated resource regions while limiting the number of core biome categories. The hybrid coast adds brines and evaporites without requiring a distinct inland map region. Fixed adjacency is intended to make geology learnable and connect exploration routes.

The source contains inconsistent geographic heuristics: one section says oil and iron are within 3–5 km; another describes a general 2–3 km expectation. These are not treated as verified guarantees. Reconcile them with the broader distance targets in [ADR-0005](ADR-0005-map-scale-and-discovery-distances.md).

## Consequences

- Positive: resource availability is legible through geology, and region types remain bounded.
- Positive: coastal features provide chemical resources across the core biome layout.
- Trade-off: hard adjacency rules constrain map-generation layouts and need technical validation.
- Follow-up: map every catalog deposit to a biome or terrain feature and validate actual travel distances.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md).
- Related ADRs: [ADR-0002](ADR-0002-geology-led-exploration.md), [ADR-0005](ADR-0005-map-scale-and-discovery-distances.md).
- Supersedes / superseded by: Replaces the earlier six-area candidate mapping; no superseding ADR recorded.
