# ADR-0004: Sparse Military Patrols at the Map Edge

*Status: Accepted*
*Decision date: 2026-11-06*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Military System](../military-system.md).

## Context

Expansion should offer some relief from military pressure without making the map edge an unreachable hard wall or eliminating the logistics cost of remote territory. The source first says map-edge enemy density increases, with enemies drawn by pollution and no infinite spawn zones; if the map ends without more nearby factories, expansion stops. A later resolved decision says enemies thin to a sparse patrol layer. The earlier open-decision text also asks whether enemies stop, redirect, or spread out at boundaries.

## Decision

At the map edge, enemies do not stop; density thins to a sparse patrol layer of approximately 10% of base density. Pressure is lowest at the edge, while logistics costs are highest. This is a world-generation/expansion principle; detailed enemy behavior and attack mechanics remain owned by the military design.

## Options Considered

1. **Stop enemies at the edge.** Creates a hard safety boundary.
2. **Increase density at the edge.** Appears in an earlier draft passage, but conflicts with the later resolved decision.
3. **Thin to sparse patrols.** Keeps the edge part of the world while offering relative breathing room. This is the selected design.

## Rationale

The selected model aims to make expansion a strategic choice: safer territory is farther from the factory and more expensive to supply. It avoids both a hard wall and an edge that is more dangerous than the territory being left behind.

## Consequences

- Positive: expansion can reduce exposure without guaranteeing complete safety.
- Trade-off: patrol density and its meaning depend on the military pressure model and require gameplay validation.
- Follow-up: reconcile map-edge behavior with the authoritative military design and tune the approximate density.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Military System](../military-system.md).
- Related ADRs: [ADR-0005](ADR-0005-map-scale-and-discovery-distances.md).
- Supersedes / superseded by: Supersedes the earlier draft statement that map-edge density increases; no superseding ADR recorded.
