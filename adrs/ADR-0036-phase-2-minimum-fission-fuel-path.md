# ADR-0036: Set the Minimum Phase 2 Fission-Fuel Capability

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) selects distinct uranium- and thorium-cycle fission options in Phase 2. [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects a uranium-derived fissile startup seed for the thorium route, followed by U-233 breeding and reprocessing in the gameplay model.

The Power System places fission in Phase 2 and requires fuel-fabrication capability. Infrastructure currently places the Uranium Conversion Line in Phase 2–3, the Cladding Tube Mill in Phase 3, and the Fuel Rod Assembly Line in Phase 3–4. As written, the Phase 2 reactor may depend on manufacturing capabilities not available until later.

## Decision

Provide a minimum Phase 2 fuel-conversion and preparation path that produces a fuel form directly usable by the Phase 2 reactor. Neither selected Phase 2 fission option may depend on Phase 3+ cladding or fuel-rod assembly for its baseline fuel path.

The minimum route must preserve the selected uranium and thorium cycle identities. For thorium, the Phase 2 route retains the uranium-derived startup-seed dependency in ADR-0023. Advanced cladding and fuel-rod assembly remain later capabilities rather than prerequisites for baseline Phase 2 fission.

This sets the capability and phase boundary only. Exact fuel forms, conversion and enrichment steps, material balances, equipment assignments, recipes, and research gates remain open.

## Options Considered

1. **Keep the current later fuel-fabrication timing as a prerequisite for Phase 2 reactors.** Not selected; it would make Phase 2 fission depend on Phase 3+ capabilities.
2. **Move all cladding and fuel-rod assembly capabilities into Phase 2.** Not selected; the baseline route need only produce reactor-usable fuel, and advanced fabrication can remain a later capability.
3. **Make the minimum reactor-usable fuel path available in Phase 2 and keep advanced cladding/assembly later.** Accepted; aligns fuel availability with the selected Phase 2 reactor progression without requiring the full advanced fabrication chain.

## Rationale

The phase gate for a generator and its minimum fuel supply must align. Allowing the baseline reactor to consume a basic prepared fuel form directly keeps Phase 2 fission buildable while preserving later cladding and assembly as potential capability upgrades.

## Consequences

- Positive: Phase 2 fission no longer depends on Phase 3 or Phase 4 fuel-assembly infrastructure.
- Trade-offs: The basic fuel form and its handling must be made clear in the final recipes and player-facing explanations.
- Follow-up work: Define the minimum uranium and thorium fuel routes, validate their material balances, and assign recipes, equipment, and research gates. Keep advanced cladding and fuel-rod assembly as later capabilities unless route validation shows a Phase 2 dependency.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), which selects Phase 2 uranium and thorium fission options, and [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md), which selects the thorium startup-seed and breeding model.
- Supersedes / superseded by: Refines the Phase 2 fuel-fabrication boundary in ADR-0019 without changing its selected generation routes or the thorium model in ADR-0023.
