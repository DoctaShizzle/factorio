# ADR-0015: Give Defense Infrastructure a Sustained Power Load

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Military System](../military-system.md), [Power System](../power-system.md), [Infrastructure](../infrastructure.md).

## Context

The Military System draft proposes that turrets and defense infrastructure draw continuous power, making defense an ongoing grid load rather than only a construction cost. The source labels this as adopted from The Riftbreaker, but records no decision date or independent approval evidence. On 2026-11-12, the user accepted sustained power for defense. Illustrative turret power values remain unvalidated. The proposed plasma and railgun turret families should also have substantial power draw as a balance cost; their power profiles and values are not specified.

## Decision

**Accepted principle:** Active defense systems, including turrets, impose sustained power demand rather than only construction cost. This does not set the idle or firing draw of individual defenses. For the proposed plasma and railgun families, substantial electrical demand is a requested balancing constraint; whether it is continuous draw, peak draw while firing, stored energy per shot, or a combination remains open. All numeric power values remain unvalidated.

## Options Considered

1. **Require sustained power for active defense.** This connects perimeter size and weapon use to generation, grid capacity, and storage.
2. **Limit defense costs to construction and ammunition.** This avoids adding continuous power demand but leaves defense less connected to the power design.

## Rationale

The source argues that sustained defense load creates an industrial tradeoff: players must plan defensive density alongside production demand and may invest in storage or generation to support it.

## Consequences

- Positive: Military infrastructure becomes a meaningful consumer in power planning, and advanced electrical defenses trade combat capability against grid capacity.
- Trade-offs: Continuous or peak defense loads can become punitive if outages or consumption are difficult to diagnose; values need balancing against the eventual core power model.
- Follow-up: Align military power draw with the approved [Power System](../power-system.md), reconcile the existing laser-turret estimates across Military System and Infrastructure, and validate candidate values in gameplay.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Power System](../power-system.md), [Infrastructure](../infrastructure.md).
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md).
- Supersedes / superseded by: None.

## Open Questions

- [ ] Should each electrical turret use sustained draw, firing bursts, energy storage per shot, or a combination?
- [ ] What power values and grid behavior balance the plasma and railgun candidates without making defense punitive?
- [ ] How should the existing laser-turret power estimates in Military System and Infrastructure be reconciled?

## Revisions

- 2026-11-12 — Added the proposed plasma and railgun turrets' substantial power draw as a balancing constraint; left draw profile and values open.
- 2026-11-12 — User accepted sustained power demand for defense; numerical values and per-turret load profiles remain open.
