# ADR-0055: Select a Phase 2 Thorium Oxide Seed-and-Blanket Architecture

*Status: Accepted*
*Decision date: Unknown*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects a Th-232 cycle with a uranium-derived fissile startup seed, followed by U-233 breeding and reprocessing without continuous uranium-fuel top-up in the gameplay model. [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) sources the seed from the shared Phase 2 uranium chain. [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires cladded fuel rods for both Phase 2 fission options, but the thorium fuel architecture remained open.

Th-232 is fertile rather than fissile and requires a fissile driver. The [World Nuclear Association thorium overview](https://world-nuclear.org/information-library/current-and-future-generation/thorium) describes separate seed-and-blanket arrangements as favorable for thermal breeding. The design needs a high-level fuel architecture compatible with Phase 2 rods without fixing detailed fuel chemistry or breeding balances.

## Decision

1. Use a solid-oxide seed-and-blanket architecture for the Phase 2 thorium option. Keep the ThO2-bearing fertile material separate from the uranium-derived fissile startup seed.
2. After breeding and reprocessing, return bred U-233 to the reactor as oxide fuel rods.
3. This refines, and does not supersede, the startup and U-233 cycle selected in ADR-0023. The gameplay model still does not require continuous uranium-fuel input after startup.
4. The startup seed uses the same qualitative uranium enrichment grade as uranium fuel under [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md); its numeric target remains deferred under [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md). Do not infer the seed's exact compound, isotope composition, item identity, quantity, or preparation route. Reactor configuration, detailed conversion/reprocessing routes, balances, waste handling, and research gates also remain open.

## Options Considered

1. **Separate solid-oxide seed and fertile blanket.** Selected; it preserves the fissile-driver/fertile-material distinction and supports the selected breeding gameplay while using the required rod-fabrication capability.
2. **Homogeneous thorium-bearing mixed-oxide rods.** Not selected; it offers a more unified fuel form but makes the seed/blanket distinction and breeding dependency less explicit.
3. **Molten-salt fluoride fuel.** Not carried forward for this Phase 2 design; it conflicts with the cladded-rod requirement in ADR-0043 and would require a separate decision to change that boundary.

## Rationale

The selected architecture makes the thorium route visibly different from direct uranium fission: a separate uranium-derived driver starts the cycle, ThO2 is the fertile material, and bred U-233 returns as oxide fuel. The separated arrangement is also more consistent with the cited breeding model than a homogeneous blend, while leaving its chemical and material balances for later validation.

## Consequences

- Positive: the Phase 2 thorium fuel architecture is defined at a high level and remains compatible with cladded fuel-rod assembly.
- Trade-offs: separate driver and fertile streams add processing and inventory complexity; detailed U-233 separation, fuel fabrication, and waste handling remain to be designed.
- Follow-up work: select the numeric uranium-fuel enrichment target under ADR-0051 and apply it to the startup seed under ADR-0056. Define exact seed and bred-fuel identities and compositions, seed quantity, process routes, material and breeding balances, waste handling, and research gates. Do not assume a real-world self-sustaining breeding ratio from the gameplay abstraction.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the startup and breeding model; [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) requires enriched UO2 for the uranium route; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires Phase 2 rods; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium-chain source for the startup seed; [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) selects the same qualitative enrichment grade.
- Supersedes / superseded by: No decision is superseded. This refines the open thorium fuel-form boundary in ADR-0023, ADR-0043, and ADR-0047.
