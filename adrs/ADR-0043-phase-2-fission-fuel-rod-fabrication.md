# ADR-0043: Require Phase 2 Cladding and Fuel-Rod Assembly for Fission

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0036](ADR-0036-phase-2-minimum-fission-fuel-path.md) initially kept cladding and fuel-rod assembly outside the minimum Phase 2 fission path. [ADR-0041](ADR-0041-phase-2-direct-use-fission-fuel.md) then selected direct-use unclad fuel. The user now wants a more involved solid-fuel fission chain in which those fabrication capabilities are necessary to operate either Phase 2 fission option. The uranium route continues to require enriched UO2 under [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md).

## Decision

1. Both Phase 2 fission options require cladding and fuel-rod assembly to produce reactor-usable baseline fuel. Bare pellets or other unassembled fuel forms are not reactor inputs.
2. The Cladding Tube Mill and Fuel Rod Assembly Line are Phase 2 minimum capabilities and prerequisites for operating either baseline fission option. Their exact research gates and recipes remain open.
3. Enriched UO2 pellets remain an intermediate for the uranium route under ADR-0042 and must be clad and assembled before reactor use.
4. The thorium route retains the Th-232 feed, uranium-derived fissile startup seed, and U-233 breeding/reprocessing model under [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md). Its solid-oxide seed-and-blanket architecture is selected under [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md); exact seed and fuel composition and item identities remain open, but the reactor-usable output must be cladded and assembled as fuel rods.
5. The current zirconium-alloy cladding and fabrication details remain candidates; the Phase 2 path must have a viable cladding-material supply, but this ADR does not finalize its chemistry, source route, balances, or equipment configuration.

## Options Considered

1. **Use direct-use unclad fuel in Phase 2 and defer cladding/rod assembly.** Superseded; this does not provide the requested fabrication depth for fission.
2. **Require Phase 2 cladding and fuel-rod assembly for both fission options.** Selected; fuel fabrication becomes part of the baseline fission capability rather than a later upgrade.
3. **Keep the machines as optional later fission upgrades.** Not selected; fission would remain operable without the fabrication chain.

## Rationale

Requiring assembled rods gives both Phase 2 fission routes a meaningful manufacturing and material dependency. It also gives the cladding and rod-fabrication capabilities a defined purpose, rather than assigning them a later phase without an approved use.

## Consequences

- Positive: the Cladding Tube Mill and Fuel Rod Assembly Line have an explicit role and phase; fission fuel is a manufactured reactor input rather than a directly consumed pellet.
- Trade-offs: baseline fission now depends on Phase 2 cladding-material supply and rod-fabrication infrastructure.
- Follow-up work: reconcile the Phase 2 zirconium/cladding supply path, define exact uranium and thorium rod products and balances, and assign recipes, equipment specifications, and research gates. The high-level thorium fuel architecture is recorded in ADR-0055.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Research Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) selects the Phase 2 uranium and thorium options; [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the thorium cycle; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 for the uranium route; [ADR-0044](ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) selects the cladding family and shared zircon access boundary; [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) selects the high-level thorium fuel architecture; [ADR-0057](ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md) requires post-discharge reprocessing/recovery for spent uranium fuel.
- Supersedes / superseded by: Supersedes [ADR-0036](ADR-0036-phase-2-minimum-fission-fuel-path.md) and [ADR-0041](ADR-0041-phase-2-direct-use-fission-fuel.md). ADR-0044 resolves the cladding-family and zircon-access follow-up; ADR-0043 remains active for the Phase 2 rod requirement.
