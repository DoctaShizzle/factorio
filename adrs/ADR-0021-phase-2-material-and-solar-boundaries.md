# ADR-0021: Set Phase 2 Material and Solar Boundaries

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Power System](../power-system.md), [Plan](../plan.md).

## Context

The early resource roster and infrastructure candidates placed aluminum among Phase 1 needs and allowed photovoltaic generation to start in Phase 1, despite bauxite, soda ash, and silicon-processing dependencies appearing in the Phase 2 material trunk. Salt and brine were intended to be geographically reachable near the Phase 1/2 transition, but their simple extraction and crystallization timing was not explicit.

## Decision

1. Photovoltaic generation is not available in Phase 1. Its earliest availability is Phase 2, using a material progression that does not bypass the Phase 2 supply chain. The exact Phase 2 unlock point and first-cell production route remain open. This does not set the timing or chemistry of energy storage.
2. Aluminum metal and bauxite-derived alumina are Phase 2 or later; neither is a Phase 1 material. Early equipment uses basic refractory materials, with alumina-bearing construction materials introduced no earlier than Phase 2.
3. Salt/brine is reachable by early Phase 2 through simple extraction and evaporation/crystallization. The chlor-alkali process remains a Phase 2 capability. Exact deposit layout, recipes, yields, and coproduct handling remain open.

## Options Considered

1. **Introduce vanilla-style photovoltaic generation in Phase 1.** Rejected because it bypasses the intended material progression.
2. **Make photovoltaic generation available no earlier than Phase 2.** Selected; solar becomes an industrial capability tied to its material inputs rather than a free early-game substitute.
3. **Keep aluminum and alumina in the Phase 1 starting roster.** Rejected; bauxite-derived materials follow the Phase 2 mining and refining chain.
4. **Defer salt/brine access until deep Phase 2.** Rejected; a simple route should be reachable by early Phase 2, while chlor-alkali remains within Phase 2.

## Rationale

These boundaries preserve the intended material progression: early power uses the established combustion path, while solar, aluminum, alumina, and brine chemistry enter with their relevant Phase 2 capabilities. Early access to salt does not require the player to build the full chlor-alkali process chain in Phase 1.

## Consequences

- Positive: Phase 1 no longer depends on aluminum, alumina, or a vanilla-style photovoltaic bypass; Phase 2 has a clear point of entry for solar and salt chemistry.
- Trade-offs: the exact first Phase 2 photovoltaic cell route is not yet defined, and early storage may precede or accompany solar.
- Follow-up: reconcile resource-tier and infrastructure rows, then validate the Phase 2 solar route and salt/brine supply.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Power System](../power-system.md), [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0006](ADR-0006-capability-based-intermediate-scope.md).
- Supersedes / superseded by: Resolves the Phase 1/Phase 2 availability questions for photovoltaic generation, aluminum/alumina, and early salt/brine access; does not supersede ADR-0019.
