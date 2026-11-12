# ADR-0016: Reject Late-Game Military Drones

*Status: Rejected*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Military System](../military-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md).

## Context

The Military System draft proposed two late-game drone roles inspired by The Riftbreaker: patrol attack drones and sensor/early-warning drones. The source described semiconductor, power-cell, sensor, and precision-optics supply chains and placed these concepts in the infrastructure catalog. On 2026-11-12, the user rejected military drones, specifying fixed defenses and identifying optional spider-bot and power-suit additions for a more advanced military extension. The spider-bot and power-suit direction is distinct from military drone defense; its scope remains to be designed.

## Decision

**Rejected:** Do not add military drones. The patrol-attack and sensor/early-warning drone concepts below are retained as rejected history, not as core or extension requirements. The current direction relies on fixed defenses; an optional advanced military extension may instead consider spider-bot and power-suit additions, whose product scope and details remain open.

## Options Considered

1. **Add patrol-attack and sensor/early-warning drones.** This was the rejected source proposal; it connects military coverage to semiconductors, power cells, sensors, and automation.
2. **Rely on fixed defenses and existing logistics tools.** This is the user's direction and avoids adding military drones.
3. **Defer military drones to an optional extension.** Rejected along with the drone direction; the optional advanced military extension may instead consider spider-bot and power-suit additions.

## Rationale

The user selected fixed defenses and rejected military drones. The optional spider-bot and power-suit direction retains room for advanced military additions without reopening the rejected patrol or sensor drone proposal. No additional rationale or implementation details have been specified.

## Consequences

- Positive: The current military direction avoids autonomous drone-defense behavior and keeps defense centered on fixed installations.
- Follow-up: Scope the optional spider-bot and power-suit additions in the advanced military extension; do not treat the rejected drone supply chains as current product requirements.

## Preserved Rejected Proposal

The following table preserves the former candidate design and supply-chain rationale for traceability. It is not current design.

| Drone Type | Tier/Phase | Operations | Supply Chain Requirement | Design Role |
|---|---|---|---|---|
| **Patrol Drone (Attack)** | Phase 3+ | Autonomous patrol of designated perimeter zones; auto-targets nearby enemies within range | Semiconductor guidance module + precision power cell (lithium battery from electrochemical chain) + tungsten micro-penetrator ammo | Fills gaps between stationary turret coverage; handles small infiltration waves that would overwhelm fixed positions. Battery life = operational radius × time |
| **Sensor Drone (Early Warning)** | Phase 3+ | Scans area for burrowing threats and enemy composition analysis; broadcasts warning data to nearby turrets | Semiconductor guidance module + cryogenic sensor array (superconducting materials from Nb₃Sn wire chain) + precision optics | Reveals hidden worm burrows before they emerge; identifies incoming enemy class composition so players can switch turret ammo types proactively. Essential near expansion frontier |

The rejected proposal described drones as engineered systems that complement, rather than replace, stationary turrets, extending coverage to perimeter gaps and expansion zones.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md).
- Related ADRs: [ADR-0012](ADR-0012-bound-core-military-scope.md), [ADR-0014](ADR-0014-capability-based-ammunition.md).
- Supersedes / superseded by: Rejects the former patrol-attack and sensor/early-warning military drone proposal.

## Open Questions

- [ ] What scope, unlocks, and product families belong in the optional spider-bot and power-suit extension?

## Revisions

- 2026-11-12 — User rejected military drones and specified fixed defenses, with optional spider-bot and power-suit additions as a separate advanced military extension direction. Preserved the rejected drone roles and supply chains here.
