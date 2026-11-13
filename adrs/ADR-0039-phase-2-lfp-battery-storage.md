# ADR-0039: Select Phase 2 LFP Battery Storage

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Plan](../plan.md).

## Context

Phase 2 photovoltaic generation now uses crystalline-silicon cells under [ADR-0038](ADR-0038-select-phase-2-crystalline-silicon-pv.md). The current power and product designs include a Phase 2+ battery-storage unit but leave the cell chemistry open. The first chemistry must connect to the material chain without silently selecting mineral sources or their world placement.

## Decision

Use lithium iron phosphate (LFP / LiFePO4) lithium-ion cells as the initial Phase 2 battery-storage chemistry. Lithium and phosphate feeds must be available by the Phase 2 storage unlock; iron is part of the selected cathode chemistry. This decision does not select a lithium or phosphate deposit, extraction/recovery route, regional placement, quantity, or exact in-phase unlock order.

This selects the LFP cathode chemistry, not a complete cell or pack design. The anode, electrolyte, separator, casing, current collectors, recipes, equipment, capacity, tier progression, and later battery chemistries remain open. Cobalt- and manganese-based cathodes are not required for the initial LFP route.

## Options Considered

1. **LFP lithium-ion storage.** Selected; its lithium-iron-phosphate cathode avoids cobalt and nickel requirements while connecting storage to lithium and phosphate materials.
2. **NMC lithium-ion storage.** Not selected for the initial Phase 2 battery; its cathode would add nickel, cobalt, and manganese feed dependencies.
3. **Lead-acid storage.** Not selected for the initial Phase 2 battery; it would use a separate lead and sulfuric-acid route.
4. **Defer chemistry and use a generic battery unit.** Not selected; choosing LFP now makes the required Phase 2 feed families explicit for access planning.

## Rationale

LFP is a realistic stationary-storage chemistry that fits the requested Phase 2 battery option and avoids making cobalt or nickel necessary for the baseline. Its lithium and phosphate requirements are meaningful supply-chain dependencies, so they are recorded as required feeds while their sources and access remain unresolved.

## Consequences

- Positive: The initial Phase 2 battery cathode chemistry is defined and the required lithium/phosphate feed families are explicit.
- Negative or trade-offs: Battery production now depends on Phase 2 access to lithium and phosphate; neither feed route nor placement is selected.
- Follow-up work: Resolve accessible lithium and phosphate sources, detailed chemical and refining routes, the rest of the cell/pack design, and storage capacity and progression.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0038](ADR-0038-select-phase-2-crystalline-silicon-pv.md).
- Supersedes / superseded by: None.
