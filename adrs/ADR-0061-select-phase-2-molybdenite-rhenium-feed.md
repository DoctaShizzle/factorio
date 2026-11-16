# ADR-0061: Select Molybdenite as the Phase 2 Rhenium Feed

*Status: Accepted*
*Decision date: 2026-11-16 (pragmatic default under delegated Phase 2 direction)*
*Last updated: 2026-11-16*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Intermediate Products](../intermediate-products.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md) selects rhenium-catalyst powder as a bridge to the Reaction Dynamics Facility, and [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) selects its facility mapping. The first Core requires progress across all six domains, but the rhenium source and its access timing were not selected.

This feed choice is an autonomous default under the user's direction to favor realistic, low-friction Phase 2 decisions; it is not represented as a direct user selection.

The existing mineral catalog identifies molybdenite as a candidate rhenium-bearing feed. The [USGS rhenium overview](https://www.usgs.gov/centers/national-minerals-information-center/rhenium-statistics-and-information) describes rhenium production from the molybdenite fraction of porphyry copper ores, often as a byproduct of roasting molybdenum.

The former intermediate-product proposal described molybdenite concentrate followed by acid attack and solvent extraction of MoS2 residue, high-purity rhenium powder reduction, and controlled-particle-size catalyst-bed preparation. Those specific process claims are unverified and are not selected by this feed decision.

## Decision

1. Use rhenium-bearing molybdenite as the baseline feed family for the Phase 2 Reaction Dynamics bridge. This does not require a separate rhenium ore or select a specific deposit profile.
2. Make limited supply reachable using then-available exploration, extraction, and logistics by the first time the bridge material is needed for the facility or its T2a progression, whichever is earlier. A starting-region deposit is not guaranteed.
3. Make the access and recovery path available without requiring the Reaction Dynamics Facility, its own domain packs, or the first Core. Later research design must also avoid cross-domain dependency cycles.
4. Validate that rhenium recovery and any primary-molybdenum or other coproduct handling can support the required bridge without forcing permanent accumulation.

The feed family and access boundary are selected; deposit assignment, extraction and recovery chemistry, equipment, product forms, grades, quantities, yields, recipes, and exact research gates remain open.

## Options Considered

1. **Use molybdenite-bearing feed.** Selected; it uses an existing candidate and a documented real-world rhenium association.
2. **Add a separate rhenium ore.** Not selected; it adds an unnecessary source family and does not reflect the documented byproduct association.
3. **Leave the source and access timing open.** Not selected; the mandatory bridge could otherwise lack a reachable pre-Core source.

## Rationale

Molybdenite gives the selected bridge a credible mineral origin while retaining a geological exploration opportunity. A limited access deadline and an acyclic recovery path prevent that opportunity from becoming an impossible first-Core gate; detailed processing remains for later coverage and recipe work.

## Consequences

- Positive: The mandatory rhenium bridge has a selected feed family and an explicit access boundary.
- Trade-offs: The route needs workable trace recovery and coproduct handling, and world generation must make an appropriate supply reachable.
- Follow-up work: Phase 4 must represent the required recovery capability; Phase 5 must establish a credible pre-Core source-to-bridge path and coproduct handling. Later product, recipe, research, and world-generation work must resolve the remaining details without requiring the facility or its own packs to bootstrap itself.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Intermediate Products](../intermediate-products.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md), [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0020](ADR-0020-seven-distinct-domain-pack-tiers.md), and [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).
- Supersedes / superseded by: None.
