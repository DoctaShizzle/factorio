# ADR-0022: Finalize Phase 2 Bridge Mappings and Core Dependencies

*Status: Accepted; semiconductor timing and packaged-IC dependency partially superseded by [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md)*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Research and Progression](../research-progression.md), [Intermediate Products](../intermediate-products.md), [Endgame Vision](../endgame-vision.md), [Power System](../power-system.md), [Plan](../plan.md), and [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) for the updated semiconductor timing.

## Context

[ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md) selected six bridge products and the first-Core gate but left product-to-facility mappings open. The research and endgame drafts also listed enriched fuel stock as a candidate input to the isotope facility and Unified Metrology Reference Array, which could inadvertently make a fission fuel cycle a first-Core prerequisite. The user accepted the existing six mappings, specified that electronic-grade polysilicon must be available before the Core while full semiconductor fabrication follows Core Level 1, and excluded uranium and thorium cycles from the Core gate except where a route is chosen to provide power.

## Decision

1. Use these one-to-one Phase 2 bridge mappings:
   - Electronic-grade polysilicon → Superconductivity Research Lab.
   - Nb₃Sn wire → Plasma Confinement Facility.
   - HfO₂ dielectric → Nanofabrication Laboratory.
   - D₂O → Isotope Separation & Calibration Lab.
   - High-performance rhenium-catalyst powder → Reaction Dynamics Facility.
   - Cryogenic argon/nitrogen mixture → Quantum States Laboratory.
2. Make the limited purification route for electronic-grade polysilicon available before first-Core construction in Phase 2. Full wafer/chip fabrication and cleanroom manufacturing remain post-Core Level 1.
3. Neither uranium nor thorium fuel fabrication is a first-Core prerequisite. The Core requires sufficient operating power, but no particular fission route; a fission fuel chain is required only if that route is chosen for power.
4. Do not require enriched fission fuel to construct or operate the isotope facility or Unified Metrology Reference Array before the first Core. Exact neutron-reference instrumentation and remaining Array materials are unresolved.
5. Any first-Core construction input still needs a demonstrated pre-Core supply path. Candidate packaged integrated circuits and semiconductor-grade positioning stages do not become requirements until that path is established; they may not rely on the post-Core Level 1 fabrication unlock.

The selected mappings do not approve additional supporting materials, construction inputs, recipes, quantities, facility operating requirements, or the complete Array bill of materials.

## Options Considered

1. **Leave the six facility mappings as candidates.** Rejected; the user accepted the existing one-to-one mapping.
2. **Make the enriched-fuel candidates mandatory inputs to the isotope facility and Array.** Rejected because this would turn a fission fuel cycle into an unintended first-Core gate.
3. **Require the full semiconductor fabrication chain before the Core.** Rejected; only the polysilicon precursor route is pre-Core, with full wafer/chip and cleanroom fabrication after Core Level 1.

## Rationale

The mapping assigns one selected bridge material to each research domain without converting every proposed support input into a requirement. Separating electronic-grade polysilicon from wafer/chip fabrication avoids a circular Core gate. Keeping fission optional to the first-Core threshold preserves the accepted gate while allowing uranium or thorium power when the player chooses it.

## Consequences

- Positive: bridge ownership is clear, and no research or Array input silently requires a fission cycle or post-Core fabrication capability.
- Trade-offs: the Array's neutron-reference materials and the pre-Core source of candidate Core electronics remain unresolved.
- Follow-up: validate each bridge route and supporting inputs; reconcile Core hardware candidates with pre-Core manufacturing before finalizing the Array or Core recipe.

## Affected Design and Related Decisions

- Design documents: [Research and Progression](../research-progression.md), [Intermediate Products](../intermediate-products.md), [Endgame Vision](../endgame-vision.md), [Power System](../power-system.md), [Plan](../plan.md).
- Related ADRs: [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md), [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0020](ADR-0020-seven-distinct-domain-pack-tiers.md).
- Supersedes / superseded by: Resolves the bridge-mapping and fission-dependency follow-ups left open by ADR-0017. Its semiconductor timing and packaged-IC dependency are partially superseded by ADR-0025; the bridge mappings and fission boundary remain in force. ADR-0017 remains in force for the first-Core gate and six-bridge count.
