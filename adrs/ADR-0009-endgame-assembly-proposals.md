# ADR-0009: Preserve Former Phase A2 Endgame Assembly Proposals

*Status: Accepted as a historical record; recipe values remain unapproved*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Research and Progression](../research-progression.md), [Plan](../plan.md).

## Context

An earlier version of `plan.md` marked Phase A2 endgame assembly chains as complete and recorded candidate Core, satellite, convergence-array, and Hawking-engine build inputs. The current phased plan defers detailed recipes and quantities until product coverage and recipe work. Current owner documents retain the endgame concepts and facility hypotheses, but not every quantity, component name, phase assignment, or rationale from the former plan.

The former Phase A2 status is historical source wording, not evidence that these exact recipe values were validated or approved. Preserve the material for future review without treating it as current requirements.

## Decision

Retain the former Phase A2 assembly tables and rationale here as unapproved design proposals. Use [Endgame Vision](../endgame-vision.md) for current system and facility concepts, [Infrastructure](../infrastructure.md) for constructable and construction-demand hypotheses, [Power System](../power-system.md) for generator design, and [Intermediate Products](../intermediate-products.md) for non-building product identities and uses.

Do not treat the quantities, phases, component list, or material-demand assertions below as approved recipes. Reassess them after the coverage gate and during the designated recipe and research phases.

## Options Considered

1. **Promote the former quantities and component lists into current requirements.** This would bypass the planned coverage and recipe gates and could preserve unsupported assumptions.
2. **Preserve them as unapproved candidate history and revalidate later.** This retains the design work while keeping current requirements open.
3. **Discard the former Phase A2 details when repurposing the plan.** This would lose design information and its rationale.

## Rationale

The product-tree plan requires coverage to be established before detailed recipes are finalized. Preserving the earlier work in an ADR maintains traceability and avoids both accidental approval and information loss.

## Consequences

- Positive: prior quantities, candidate components, progression assignments, and design rationale remain available for review.
- Trade-off: several assembly names, counts, and phase assignments conflict with or go beyond the current owner documents.
- Follow-up: reconcile the Unified Metrology Reference Array's activation timing, the five-versus-six prerequisite count, Core assembly quantities, satellite requirements, and the Hawking Engine's component architecture before adopting any values.

## Preserved Candidate Assemblies

The tables below reproduce the former plan's candidate values. The outputs and quantities are hypotheses, not a recipe specification.

### Planetary Simulation Core

The former plan described two Core stages: initial activation (T1) followed by L2 and L3 upgrades, with the T1 assemblies forming the primary construction chain.

| Core sub-assembly | Candidate build inputs | Former phase | Candidate capability link |
|---|---|---|---|
| Thermal Frame Assembly | Heat exchanger coils × 40, cryogenic insulation panels × 60, thermal interface material stacks × 30, refrigeration cascade components (liquid N₂/Ar circuit parts) × 20, corrosion-resistant structural steel frames × 50 | T1 construction | Nb₃Sn wire for cryogenic circuits, HfO₂ dielectric for insulation panels, and electronic-grade polysilicon for thermal sensors |
| Computation Cluster | Packaged ICs × 100, ultra-pure copper bonding wire spools × 15, advanced thermal interface material × 25, electromagnetic-shielded memory enclosures × 40 | T1 construction | Polysilicon for IC substrates and Nb₃Sn wire for shielding |
| Integration Bus | Superconducting interconnect cable lengths × 80, photolithography-processed glass waveguide panels × 30, mu-metal/electromagnetic shielding sheets × 50, fiber routing hardware sets × 20 | T1 construction | Nb₃Sn wire for interconnects and HfO₂ dielectric for waveguide coating |
| Calibration Reference Frame | Unified Metrology Reference Array × 1, precision alignment mechanism parts × 15, vibration isolation system components × 10, environmental control sub-system × 1 | T1 construction | Bridge products for the metrology array |
| Unified Metrology Reference Array | Nb₃Sn wire bundle × 8, electronic-grade polysilicon wafer substrates × 12, D₂O enrichment chamber parts × 6, rhenium-catalyst powder beds × 4, cryogenic Ar/N₂ mixture reservoirs × 3, enriched fuel stock cells × 2 | T1 construction; gates Core activation | All six bridge materials contribute |

### Hawking Radiation Engine

| Candidate component | Candidate build inputs | Former phase | Candidate rationale |
|---|---|---|---|
| Event-Horizon Containment Coil | Nb₃Sn superconducting cable spools × 60, cryogenic insulation panels × 80, corrosion-resistant structural steel frame × 30 | Phase 3 (Core L2) | Magnetic field to contain and stabilize the event horizon; identified as a major Nb₃Sn consumer beyond the Integration Bus |
| Precision Gravitational Lens Array | Photolithography glass optics panels × 40, electronic-grade polysilicon wafers × 20, ultra-pure copper alignment frame parts × 15 | Phase 3 (Core L2) | Focuses Hawking-radiation extraction using cleanroom optics |
| Thermal Gradient Converter | Thermoelectric semiconductor modules (Bi₂Te₃ from refined bismuth/tellurium), high-purity copper heat spreaders × 30, thermal interface material stacks × 25, HfO₂ dielectric panels × 40 | Phase 3 (Core L2→L3) | Converts a temperature differential into power; bismuth and tellurium were proposed as recoverable copper/gold anode-slime products |
| Hawking Radiation Collector Nozzle | Refractory tungsten alloy plates × 50, molybdenum support structures × 20, rhenium-catalyst treatment coating × 10, graphite backing panels × 30 | Phase 4 (general physics) | Withstands plasma-facing heat loads; tungsten was traced to scheelite/molybdenite refining |
| Vacuum Isolation Chamber | Cryogenic insulation panels × 100, titanium-alloy and steel structural frames × 60, precision sealing ring assemblies × 25, electromagnetic shielding layers × 40, refrigeration cascade components × 15 | Phase 3 (Core L3) | Creates the vacuum boundary between the extraction point and factory; described as the largest single Hawking Engine material consumer |

The former plan proposed engineering-oriented names rather than abstract physics terminology. It assigned the Containment Coil, Lens Array, and Thermal Converter to Core L2 as heavy users of Phase 2 materials, and assigned the Collector Nozzle and Vacuum Chamber to Core L3/Phase 4 as users of later capabilities. It also proposed the Collector Nozzle as the only mandatory endgame use of tungsten, justified by plasma-facing heat loads; bismuth and tellurium as situational recoverable products from copper/gold anode slimes; and titanium alloy as the lightweight high-strength vacuum-chamber material, connecting the Kroll process chain to endgame construction. These are hypotheses requiring validation, not accepted constraints.

### Satellite Facilities and Calibration Sub-Network

| Candidate facility or system | Candidate build inputs | Former phase | Candidate purpose |
|---|---|---|---|
| Compute Campus Node (×4 or more recommended) | Packaged ICs × 30, advanced cooling module assemblies × 10, power regulation units × 8, superconducting cable lengths × 20, thermal interface material stacks × 15 | T1 construction; upgrades at L2 | Processor capacity for model runs |
| Memory/Archive Module (×3 or more recommended) | High-density storage elements × 20, thermal management units × 8, stable power supply modules × 6, cryogenic insulation panels × 15, structural alloy frame parts × 10 | T1 construction | Long-term data preservation |
| Regional Observation Facility (×3–4 recommended) | Sensor array components × 12, sample processing equipment × 8, domain lab sub-components × 5, structural frames × 10, power supply modules × 4 | T1 construction, phase varies | Feeds raw measurement data into calibration hardware |
| Calibration Sub-Network | Precision alignment mechanisms × 3 per lab, vibration isolation components × 3 per lab, environmental control sub-systems × 2 per lab | Post-activation upgrades | Repurposes domain labs as active calibration references |

### Unified Metrology Reference Array: Separate Former Assembly Record

The former plan recorded a second, more specific version of the array recipe, including a proposed crafting location and research gate. Its timing differs from the Core table above and remains unresolved.

| Candidate item | Candidate build inputs | Former crafting location | Former phase/gate |
|---|---|---|---|
| Unified Metrology Reference Array | Nb₃Sn wire bundle × 8, electronic-grade polysilicon wafers × 12, D₂O enrichment chamber parts × 6, rhenium-catalyst powder beds × 4, cryogenic Ar/N₂ mixture reservoirs × 3, enriched fuel stock cells × 2 | Metrology assembly station (Phase 3 machine) | All six domains at T2a |

The former plan explicitly described this as a physical precision instrument, not "six packs in a crafting grid," and as the player's first substantial Phase 3 assembly, harder than any Phase 2 craft. Each ingredient was meant to trace to a domain lab's bridge product. It also proposed that the metrology station itself require Nb₃Sn and electronic-grade polysilicon, and that each bridge material be produced at its respective Phase 2 domain lab before assembly, so Phase 2 represented building capability rather than administrative proof.

## Affected Design and Related Decisions

- Design documents: [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Research and Progression](../research-progression.md), [Plan](../plan.md).
- Related ADRs: [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md), [ADR-0008](ADR-0008-factorio-product-family-coverage.md).
- Supersedes / superseded by: No superseding ADR recorded; candidate recipe values are deferred to future design gates.
