# ADR-0018: Select Phase 3/4 Power Routes and Non-Steam Conversion

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md), and [Migration Map](../migration-map.md).

## Context

The user requires at least three distinct power options in each of Phases 3 and 4. The user accepted the current minimum route identities, then approved concentrated solar thermal with storage as an additional Phase 3 option. [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) establishes the Phase 2 steam-turbine retirement boundary, so later thermal sources need non-steam conversion. The user asked for realistic, material-connected conversion choices rather than an unspecified placeholder.

The accepted Hawking Radiation Engine remains one Phase 4 option under [ADR-0011](ADR-0011-hawking-radiation-endgame-generator.md); this ADR does not reopen or replace that decision.

## Decision

1. Select the Phase 3 minimum roster of Tokamak fusion, geothermal generation, and solar PV. Add concentrated solar thermal with thermal storage as a fourth Phase 3 route.
2. Select the Phase 4 roster of the Hawking Radiation Engine, cross-universe exergy-gradient extraction, and stellar-scale solar collection with beamed transmission. The beam is a transmission method; the solar collector is the generator.
3. Use source-matched, non-steam conversion after the Phase 2 boundary in [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md):
   - A closed supercritical-CO₂ Brayton cycle for high-grade Tokamak and concentrated-solar heat.
   - A binary organic Rankine cycle for lower- or medium-temperature geothermal heat. The closed working fluid is an organic vapor, not water steam or a fuel burned in the generator.
   - Thermophotovoltaic conversion for Hawking-route radiation after it is absorbed into a controlled high-temperature emitter.
   - Direct photovoltaic conversion for terrestrial and stellar-scale solar; a separate direct field-coupling concept for the speculative cross-universe route.
4. Keep exact recipes, alloy grades, working-fluid selection, storage salts, output values, cooling requirements, constructables, and research/construction gates open.

## Options Considered

1. **Keep the route roster and conversion families provisional.** Rejected after the user accepted the route identities and requested an educated non-steam conversion choice.
2. **Use one closed Brayton cycle for every thermal source.** Rejected as the sole cycle: high-grade fusion and solar-thermal heat suit a closed CO₂ Brayton direction, while lower-temperature geothermal heat benefits from a binary working-fluid cycle.
3. **Use source-matched conversion families.** Selected: supercritical-CO₂ Brayton for high-grade heat, binary organic Rankine for geothermal, and thermophotovoltaics for a controlled high-temperature Hawking emitter. Solar PV and the speculative boundary-coupling route remain direct-conversion designs.
## Rationale

The route roster provides different source types and gameplay constraints rather than simple generator tiers. Tokamak and concentrated solar thermal provide high-grade heat appropriate for a closed gas Brayton cycle; MIT's comparison reports similar efficiency for supercritical CO₂ and helium cycles at lower source temperature for CO₂ (about 550°C versus 850°C) and compact turbomachinery, supporting CO₂ for this design while leaving actual operating conditions open ([MIT thesis](https://dspace.mit.edu/handle/1721.1/17746)). Binary geothermal plants use a secondary low-boiling fluid and can use geothermal resources below the temperature range of conventional steam plants ([U.S. Department of Energy](https://www.energy.gov/hgeo/geothermal/geothermal-electricity-generation)). Thermophotovoltaics convert thermal infrared radiation directly to electricity; laboratory cells have demonstrated more than 40% efficiency at high emitter temperatures, while remaining an emerging technology ([Nature, 2022](https://doi.org/10.1038/s41586-022-04473-y)).

These approaches create distinct material hooks without fixing recipes: high-temperature nickel/chromium/cobalt alloys and pressure-resistant heat exchangers for Brayton machinery; sodium/potassium nitrate salts for CSP storage; titanium or stainless heat exchangers and hydrocarbon-derived working fluids for geothermal; tungsten emitters and gallium/indium/arsenic semiconductor cells for TPV. Material assignments and quantities remain to be validated against the product and infrastructure designs.

## Consequences

- Positive: Phases 3 and 4 have an accepted minimum of three distinct route identities, with an additional Phase 3 solar-thermal option.
- Positive: High-, medium-, and radiation-driven thermal sources have explicit non-steam conversion directions connected to existing material domains.
- Trade-offs: Supercritical CO₂ requires high-pressure hardware and sufficiently high source temperatures; organic working fluids require leak, flammability, and environmental constraints; TPV remains research-scale and requires a controlled emitter spectrum and cooling.
- Follow-up: Validate source temperatures, working fluids, thermal-storage materials, materials feasibility, comparative power/space trade-offs, and route-specific construction and research gates before catalog work.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md), [Documentation Map](../documentation-map.md), and [Migration Map](../migration-map.md).
- Related ADRs: [ADR-0010](ADR-0010-core-power-distribution-scope.md), [ADR-0011](ADR-0011-hawking-radiation-endgame-generator.md).
- Supersedes / superseded by: Supersedes the preliminary Phase 3/4 route shortlist from the 2026-11-12 review; does not supersede ADR-0011 or duplicate the Phase 1/2 boundary in ADR-0019.
