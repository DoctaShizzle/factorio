# ADR-0065: Make Baseline Phase 2 Fission Practically Usable

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Minerals and Refining](../minerals-and-refining.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

The candidate first reactor required frequent operator attention and was described as impractical for primary power. Practical operation appeared only with later hafnium controls, while the named hafnium-forming machine was assigned to Phase 3. This conflicted with the intended usable Phase 2 fission option. The user approved minimum hafnium fabrication in Phase 2 and a normally automated first reactor.

## Decision

1. Make the first Phase 2 fission reactor a usable, normally automated industrial power source, not a mandatory operator-babysitting prototype.
2. Provide the full minimum hafnium-absorber path in Phase 2: the selected shared zircon feed and distinct Zr/Hf split, hafnium preparation to suitable metal stock, and basic absorber forming before reactor construction.
3. Give the Hafnium Absorber Plate Liner a baseline Phase 2 capability. Initial tooling and construction must be Phase 2-compatible and must not require its own finished absorbers. Later precision tooling, instrumentation, and fabrication upgrades may remain Phase 3 candidates.
4. Include baseline hafnium controls and ordinary automated fuel handling. The minimum rod-supply capability must support normal item-fed batch operation rather than mandatory per-pellet player actions. Advanced inspection and control upgrades remain optional candidates.
5. Do not make boron carbide, beryllium reflectors, superconducting wiring, or later specialist fabrication universal prerequisites for first fission. A complete reactor configuration and exact bills of materials remain open.
6. Preserve native-grid operation, combustion-powered startup, the exclusion of blackout-meltdown gameplay and a dedicated emergency-safety item, and fission's optionality to first-Core activation.

## Options Considered

1. **Retain an impractical Phase 2 prototype and move useful fission later.** Rejected; it undermines the selected Phase 2 power option.
2. **Add a new mandatory absorber feed instead of hafnium.** Not selected; the shared zircon/hafnium supply already has a Phase 2 role.
3. **Provide basic hafnium fabrication and usable automation in Phase 2, with later refinements.** Selected; it resolves the timing mismatch without a new material trunk.

## Rationale

A selected generation option needs a buildable and practically operable baseline in its assigned gameplay phase. Later upgrades should add capability or efficiency rather than retroactively provide the basic controls required to use it.

## Consequences

- Positive: practical fission no longer depends on a Phase 3 hafnium-forming machine or repeated player intervention.
- Negative or trade-offs: Phase 2 must cover metal preparation and absorber forming, not merely access to hafnium-bearing ore or chipmaking oxide.
- Follow-up work: verify the first-plant construction graph, including ordinary shielding and PTFE startup, without first Core or operating fission; retain exact tiers, controls, coolant design, quantities, and research gates for their owning work.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md) owns baseline operability; [Infrastructure](../infrastructure.md) owns machines and candidate upgrades; [Intermediate Products](../intermediate-products.md) owns absorber roles; [Minerals and Refining](../minerals-and-refining.md) owns the shared feed and recovery; [Research Progression](../research-progression.md) owns gates.
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md), [ADR-0044](ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md), [ADR-0045](ADR-0045-phase-2-zirconium-hafnium-separation-stage.md), [ADR-0058](ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md), [ADR-0059](ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md), and [ADR-0064](ADR-0064-phase-2-ptfe-bootstrap.md).
- Supersedes / superseded by: Resolves candidate timing and automation conflicts; no accepted reactor-tier roster is superseded.
