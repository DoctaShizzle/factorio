# ADR-0011: Add a Hawking Radiation Engine as a Phase 4 Power Option

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Power System](../power-system.md), [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md).

## Context

The Power System draft compares two optional, simulation-linked Phase 4 generators. It recommends the Hawking Radiation Engine as the sole Phase 4 concept and describes the ZPM-style Subspace Capacitor as dropped. The source does not establish an approval date, and it leaves the boundary between advanced fusion and Phase 4 pending alignment with the endgame design. On 2026-11-12, the user accepted the Hawking Radiation Engine but clarified that power progression must not have only one forward path; alternatives across Phases 3 and 4 still need to be developed.

The Hawking concept is a player-built, contained micro-black-hole engine, with radiation harvested through thermal-to-electric conversion. The source describes it as a physics-grounded concept related to quantum field theory in curved spacetime and mentions laboratory analogs using sonic horizons. It proposes that a Planetary Simulation Core model the radiation spectrum, collapse dynamics, and remaining lifetime; the player can feed matter to extend the finite operating life. Smaller initial black holes would convert heat more efficiently but evaporate faster. Construction would require precision optics, containment, superconducting structures, and a large initial power investment.

The alternative was a player-built, Stargate-inspired Subspace Capacitor: an artificial pocket of spacetime that extracts zero-point energy until it equilibrates with the surrounding vacuum, then collapses into an inert shell. The source proposed a lifetime of thousands of years at moderate draw, no refueling, and replacement by building another unit. It required a cleanroom capable of nanometer-scale fabrication, ultra-pure silicon wafers, a tantalum-alloy containment lattice, precision crystal resonators, and a quantum-computation module; the construction project was compared in scale to the first fusion reactor. The Simulation Core would compute planet-specific boundary conditions during construction, including proposed dependence on rotation, magnetic field, and composition; greater simulation research was proposed to improve cavity designs. No pre-built capacitor would be found on the map.

The source further proposed that the Simulation Core calculate cavity plate spacings for selected vacuum-fluctuation frequencies and harmonic-dampening parameters to prevent destabilization. It described this as a quantum-field simulation problem at nanometer scales, where ordinary measurements and perturbative approximations would be insufficient. Research was proposed to improve the theoretical models and resulting cavity designs. The source is internally inconsistent about whether the Simulation Core is used once during construction or is required for building and maintaining the device; both claims are preserved here as an unresolved conflict. These details are unapproved source proposals, not validated physics or requirements.

## Decision

**Accepted:** Include the Hawking Radiation Engine as a Phase 4 power option. It is not the exclusive route through late-game power progression: at least one viable alternative route across Phases 3 and 4 must be explored before the progression is considered complete. The former Subspace Capacitor remains a historical alternative that may be revisited, but this acceptance neither selects nor rejects it. Generator mechanics, requirements, and the alternative route remain subject to design and alignment with [Endgame Vision](../endgame-vision.md).

## Options Considered

1. **Hawking Radiation Engine.** A finite-life generator with an ongoing matter-feeding loop, a size-versus-lifetime tradeoff, and operational use of the Simulation Core.
2. **ZPM-style Subspace Capacitor.** A finite but very long-lived device whose challenge is construction and simulation-guided design; after construction it has no fuel or maintenance loop.
3. **Other Phase 3/4 generation route(s).** At least one alternative to the Hawking route is required, but no additional concept has been selected.

The source compared the options on these dimensions:

| Criterion | Hawking Radiation Engine | Subspace Capacitor |
|---|---|---|
| Ongoing gameplay loop | Feeding matter connects operation to fuel density, logistics, and supply chains. | Build once, then operate for thousands of years without ongoing interaction. |
| Meaningful tradeoff | Size versus lifetime, plus choices about feed material and efficiency. | Primarily the size or efficiency selected at construction. |
| Factorio rhythm | A continuously operated machine with a supply and optimization loop. | More like a battery than a generator after construction. |
| Physics intuition | A micro-black hole emitting radiation is comparatively easy to explain visually. | Casimir-cavity plate spacing and vacuum extraction are harder to communicate. |
| Differentiation from fusion | Adds finite lifetime and ongoing matter delivery. | Risks resembling another build-once, long-lived source alongside fusion. |

The source also proposed guidebook material: accessible and advanced explanations of Hawking radiation and quantum-vacuum concepts, alongside existing fission and fusion education. The Subspace option's proposed explanation covered Casimir cavities, boundary conditions, and stability. These are historical content proposals, not approved educational requirements.

## Rationale

The source argues that fusion already provides a dense source with effectively inexhaustible fuel, while a matter-fed Hawking engine would add a distinct, recurring logistics decision. It considers the Subspace Capacitor less interactive and harder to explain. The user accepted the Hawking concept while requiring alternatives, so the former comparison is retained as input rather than a final exclusion of all other paths.

## Consequences

- Positive: Phase 4 includes the accepted Hawking generator concept with finite operation and an ongoing supply chain.
- Trade-offs: The Hawking concept depends on complex endgame infrastructure and ongoing matter delivery; its balance and simulation role remain unvalidated.
- Follow-up: Develop and compare at least one alternative Phase 3/4 power route, resolve the boundary between fusion and Phase 4, and align requirements with Endgame Vision.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md).
- Related ADRs: [ADR-0009](ADR-0009-endgame-assembly-proposals.md).
- Supersedes / superseded by: The former single-route Phase 4 recommendation is superseded; Hawking is accepted as one option, with additional paths required.

## Revisions

- 2026-11-12 — User accepted Hawking Radiation Engine as a Phase 4 option and required that alternative Phase 3/4 power routes also be developed.
