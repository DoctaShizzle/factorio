# ADR-0013: Use Pollution and Space as Complementary Military Pressures

*Status: Proposed*
*Decision date: Unknown*
*Last updated: 2026-11-12*

Related documents: [Military System](../military-system.md), [Map and World Generation](../map-world-generation.md), [Power System](../power-system.md), [Mod Overview](../mod-overview.md).

## Context

The Military System draft proposes two independent pressures arising from industrial choices:

- **Pollution pressure:** emissions create military consequences and defensive demand.
- **Space pressure:** less space-efficient processes consume more land and can make exploration necessary even when pollution is low.

The source labels several choices resolved but provides no decision date or independent approval evidence. This ADR preserves the proposed model without treating its thresholds or effects as approved.

## Decision

The source proposal is to model pollution pressure using local, radius-based pollution density, with attack frequency and composition influenced by pollution and distance. At a proposed high threshold of more than 1000 units per second, pollution types would alter attack profiles. Enemy unit sprites would remain vanilla; the candidate effects are earlier or more numerous spitters for acid emissions and closer burrowing or armored ground units for heavy-metal contamination.

Space pressure would be communicated through the player's experience of running out of usable room, not through an in-game dashboard or explicit warning. Optional quality-of-life mod integration was mentioned as a possible external aid. Both parts remain proposed pending review.

The source also conflicts on enemy scope: its vanilla-only decision rejects pollution-adapted variants and says vanilla stats remain unchanged, while the heavy-metal proposal describes armored ground variants. Whether that means changing the mix of vanilla units or introducing new variants is unresolved.

## Options Considered

1. **Use pollution density and emergent space pressure.** Industrial choices affect attacks and factory footprint without adding a separate space meter.
2. **Use more elaborate pollution zones or time-decay models.** This could add detail but would increase complexity beyond the radius-based model proposed in the source.
3. **Display explicit space-pressure metrics.** This would make space constraints legible but would replace the source's intended player-discovered urgency.
4. **Use enemy variety rather than attack-profile changes.** This could create more combat variety but conflicts with the bounded vanilla-enemy proposal in [ADR-0012](ADR-0012-bound-core-military-scope.md).

## Rationale

The source argues that pollution makes process cleanliness a defensive choice, while process footprint creates a separate reason to expand. It describes radius-based pressure as simple and predictable and claims the approach is proven by Bob's ecosystem playtesting; that evidence was not independently checked. It favors player-discovered spatial urgency and no new enemy sprites.

## Consequences

- Positive if accepted: Pollution mitigation, process efficiency, factory layout, and exploration have distinct but related consequences.
- Trade-offs: The proposed `>1000 units/s` threshold and pollution-specific effects require balance and implementation validation; no dashboard means players need clear feedback through ordinary gameplay.
- Follow-up: Validate pollution units and scaling against Factorio behavior, reconcile the vanilla-only/armored-variant conflict, decide whether type-specific effects are feasible, and confirm whether space pressure should remain entirely implicit.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Map and World Generation](../map-world-generation.md), [Power System](../power-system.md), [Mod Overview](../mod-overview.md).
- Related ADRs: [ADR-0004](ADR-0004-map-edge-pressure.md), [ADR-0012](ADR-0012-bound-core-military-scope.md).
- Supersedes / superseded by: None.
