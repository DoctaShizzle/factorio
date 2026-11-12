# ADR-0019: Set Phase 1/2 Power Progression

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), and [Plan](../plan.md).

## Context

The early power design needed a clear boundary between fuel processing and electricity generation. Its draft included a steam-engine concept that accepted fuel directly, dedicated producer-gas/liquid-fuel generators, and uncertainty over when to retire steam turbines. The user asked to follow Factorio's recognizable boiler → steam → steam-engine model, retain an early renewable route, distinguish the two fission cycles, and retire steam-turbine generation after Phase 2.

## Decision

1. Use burner-item fuels in vanilla boilers to produce steam; vanilla, untiered steam engines consume that steam to generate electricity. Do not tier the steam engine.
2. Producer gas, biogas, and liquid fuels are not direct generator inputs. If used for power, they must be processed into burner items first; gasifiers and fuel processors are not generator families.
3. Introduce photovoltaic generation no earlier than Phase 2, using its material progression rather than a Phase 1 vanilla-style bypass; see [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md). Exact in-phase unlock, cell route, tiers, storage chemistry, and values remain open.
4. Introduce fission in Phase 2 with distinct uranium and thorium-cycle options. A thorium breeder requires fissile startup fuel and a breeding/reprocessing path to U-233; Th-232 alone is not fissile. The selected startup-seed model is recorded in [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md); exact routes, breeding balance, and waste handling remain open.
5. Keep vanilla steam turbines through Phase 2 fission, then retire steam-turbine generation. Fusion begins in Phase 3; its non-steam conversion boundary is defined in [ADR-0018](ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md).

## Options Considered

1. **Direct-fuel steam engine or dedicated gas/liquid generators.** Rejected; it blurs the vanilla boiler/steam/engine roles and bypasses burner-item processing.
2. **Vanilla boiler and untiered steam engine, with fuel preparation upstream.** Selected; preserves the familiar conversion boundary while allowing processed fuels to differ in energy density and logistics.
3. **Retire steam turbines after Phase 1, before fission.** Rejected; Phase 2 fission uses the retained turbine path for heat-exchanger steam.
4. **Retain steam turbines through Phase 2, retiring them afterward.** Selected; creates a clear boundary before Phase 3/4 non-steam conversion.
5. **Use one generic fission route or keep uranium and thorium as distinct routes.** Selected the distinct uranium and thorium-cycle options; the thorium route has a more involved startup and breeding/reprocessing chain.

## Rationale

Separating burner items, boilers, steam, and steam engines makes the early conversion process legible to players familiar with vanilla Factorio. Fuel processing remains an industrial choice rather than a second generator architecture. Basic solar and storage add a clean, spatially intensive alternative before fission. Keeping uranium and thorium as distinct Phase 2 routes gives them different fuel-cycle requirements; thorium's breeding and startup needs make it more complex rather than a simple second reactor tier.

## Consequences

- Positive: Combustion has one consistent fuel-to-electricity path, and direct gas/liquid generators are excluded.
- Positive: Solar and storage provide an early non-combustion option; later solar progression remains possible.
- Trade-offs: Phase 2 fission can use steam turbines only until the Phase 2 boundary; reactor fuel chains and phase-compatible construction remain to be designed.
- Follow-up: Specify burner-item products, minimum uranium and thorium fabrication paths, the Phase 2 photovoltaic cell route, storage chemistry, and balancing values before detailed catalog work.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md), [ADR-0011](ADR-0011-hawking-radiation-endgame-generator.md), [ADR-0018](ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md), [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md), and [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md).
- Supersedes / superseded by: Supersedes the conflicting direct-fuel steam-engine and early turbine-retirement proposals in the Power System draft; not superseded.
