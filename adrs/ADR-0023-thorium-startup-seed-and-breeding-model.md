# ADR-0023: Set the Thorium Startup-Seed and Breeding Model

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Plan](../plan.md).

## Context

The Phase 2 power design distinguishes uranium and thorium cycles, but the thorium cycle's relationship to uranium fuel was open. Thorium-232 is fertile rather than fissile, so a thorium reactor needs an initial fissile driver and a breeding/reprocessing path to U-233. The user selected a uranium-derived startup seed followed by U-233 breeding and reprocessing, without a mandatory continuous uranium fuel input in the game model.

## Decision

1. Model the thorium power route as Th-232 feed plus a uranium-derived fissile startup seed.
2. After startup, the gameplay route breeds and reprocesses U-233 without requiring a continuous uranium-fuel top-up.
3. Treat this as a deliberate gameplay abstraction, not a claim that every real thorium reactor design achieves a self-sustaining breeding ratio. Exact seed quantities, reactor configuration, conversion performance, reprocessing, and waste handling remain open.
4. The uranium seed is a prerequisite only for choosing and starting the thorium power route; it is not a first-Core prerequisite under [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).

## Options Considered

1. **Require continuous uranium-derived fissile co-feed.** Not selected; it would make ongoing uranium-fuel production a balancing requirement for the thorium route.
2. **Use a uranium-derived startup seed, followed by breeding and reprocessing of U-233.** Selected; it distinguishes the thorium route from a direct uranium cycle while avoiding an assumed permanent uranium feed.
3. **Leave the uranium/thorium relationship unspecified.** Not selected; the startup dependency materially affects the Phase 2 fuel tree.

## Rationale

The selected model preserves the real distinction between fertile Th-232 and fissile fuel while giving the game a clear startup dependency and a separate long-horizon breeding loop. It avoids presenting a continuous uranium feed as a scientific necessity and keeps the selected cycle's recipe balance open for later validation.

## Consequences

- Positive: the uranium-to-thorium dependency is explicit and bounded to startup in the game model.
- Trade-offs: the breeding/reprocessing loop and its material balance still need validation; the design does not assert a real-world self-sustaining reactor outcome.
- Follow-up: align the minimum Phase 2 uranium seed route with the selected fission infrastructure and power gates.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).
- Supersedes / superseded by: Resolves the thorium startup-fuel relationship left open by ADR-0019; does not supersede its uranium/thorium route selection.
