# ADR-0068: Use Continuous, Slightly Polluting Nuclear-Waste Disposal

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Power System](../power-system.md), [Mod Overview](../mod-overview.md), [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Technical Architecture](../technical-architecture.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md) selected finite-capacity repositories for conditioned nuclear solids. The user subsequently rejected expanding permanent storage for depleted uranium and other nuclear residues, accepted continuous powered treatment/deep disposal with no tracked storage cap, and requested slight pollution representing underground leakage or similar environmental impact.

The useful-material recovery and distinct uranium-stream roles in [ADR-0063](ADR-0063-select-depleted-uranium-oxide-reuse.md) and [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md) remain necessary. Changing the terminal endpoint does not make recycling lossless.

## Decision

1. Use continuous nuclear-waste conditioning and deep disposal as a Core Phase 2 capability. Accept eligible conditioned fuel-cycle residues and surplus depleted uranium oxide, with no tracked lifetime storage capacity, repository-cell occupancy, or obligation to expand storage.
2. Limit disposal by processing throughput, electrical power, and conditioning/packaging material supply. More waste requires more operating capacity, not more permanent storage cells. Exact equipment split, product forms, inputs, and values remain open.
3. Give disposal a small, nonzero operating pollution cost representing abstracted underground leakage/environmental impact. Use the ordinary pollution system; do not introduce a groundwater, radiation-dose, cumulative-leakage, or accident simulation. Exact emissions remain deferred.
4. Recover useful uranium, thorium/U-233, suitable cladding metal, and reusable reagents through their selected routes first. Do not bypass required reprocessing by feeding untreated spent rods or nuclear-bearing effluent directly into a generic sink.
5. Retain immobilization, suitable containment/packaging, and ordinary-shielding alternatives before terminal disposal. Depleted-oxide shielding remains useful but optional; no military consumption or continuing uranium supply for thorium is required.
6. Preserve radioactive fractions from nuclear-bearing gas/liquid streams for recovery/conditioning. Only suitably cleaned carrier streams may use the ordinary powered, pollution-producing flare/clarifier policy.
7. Represent final deep disposal as an explicit terminal removal from the modeled material network. Underground capacity and long-term waste fate are deliberately abstracted, not asserted to be infinite in reality or described as destruction/recycling of the material. This is a nuclear-cycle exception, not permission to delete arbitrary solid coproducts.
8. Provide handling by first production of the corresponding Phase 2 stream. Loss of power or materials pauses processing; operating buffers may then fill, but there is no new permanent containment-power, blackout-meltdown, or manual storage-expansion loop. Numerical balance remains deferred.

## Options Considered

1. **Keep finite repository cells.** Superseded; the user rejected permanent storage expansion as the operating constraint.
2. **Use continuous powered treatment/deep disposal with slight pollution and no storage counter.** Selected; it preserves visible costs and waste handling without indefinite storage management.
3. **Fold all disposal into reprocessing without separate waste roles.** Not selected; it is simpler but obscures the distinction between recovery and terminal handling.
4. **Export waste off-map.** Not selected; it adds logistics and worldbuilding not needed for this fix.
5. **Add advanced fuel reuse or omit waste items entirely.** Not selected; additional fuel cycles do not eliminate residues, while complete abstraction hides the selected recovery/disposal handoff.

## Rationale

The meaningful factory constraint is sustained treatment capacity and operating cost, rather than periodically adding permanent storage. Slight pollution retains an environmental tradeoff while avoiding a detailed leakage or contamination subgame.

## Consequences

- Positive: uranium and thorium operation can continue without compulsory combat, construction growth, or expanding permanent waste storage.
- Negative or trade-offs: final underground capacity and long-term behavior are intentionally outside the simulation; disposal still consumes power/materials and creates slight pollution.
- Follow-up work: verify saturated shielding demand and thorium operation without new uranium supply in Phase 5; define products, recipes, material/power/emission rates, throughput, equipment, and gates in their owning phases.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md) owns endpoint behavior; [Mod Overview](../mod-overview.md) owns the cross-domain guardrail; [Minerals and Refining](../minerals-and-refining.md) and [Chemical Processes](../chemical-processes.md) apply stream eligibility; [Intermediate Products](../intermediate-products.md) owns terminal product roles; [Infrastructure](../infrastructure.md) owns operating capability; [Technical Architecture](../technical-architecture.md) preserves Core scope; [Research Progression](../research-progression.md) owns gates; [Plan](../plan.md) tracks validation.
- Related ADRs: [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md), [ADR-0057](ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md), [ADR-0059](ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md), [ADR-0063](ADR-0063-select-depleted-uranium-oxide-reuse.md), and [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md).
- Supersedes / superseded by: Supersedes [ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md). Retains its nuclear-only eligibility, recovery-first boundary, and radioactive-stream restrictions, replacing finite emplacement with continuous disposal and slight pollution. Partially supersedes ADR-0035's unrestricted nuclear-stream release and unchanged-solid-handling boundary, and ADR-0057's residual-destination deferral; their remaining decisions stay in force.
