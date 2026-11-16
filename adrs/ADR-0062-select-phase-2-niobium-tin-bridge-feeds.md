# ADR-0062: Select Phase 2 Niobium and Tin Feeds for the Wire Bridge

*Status: Accepted*
*Decision date: 2026-11-16 (pragmatic default under delegated Phase 2 direction)*
*Last updated: 2026-11-16*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Intermediate Products](../intermediate-products.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) selects Nb3Sn superconducting wire as the Plasma Confinement Facility bridge. Its niobium and tin feed families were not selected, although all six domains must progress before the first Core.

This feed choice is an autonomous default under the user's direction to favor realistic, low-friction Phase 2 decisions; it is not represented as a direct user selection.

The mineral catalog lists niobium from columbite-tantalite and tin from cassiterite. Columbite-tantalite is already the selected tantalum-bearing feed for the Phase 2 CPU chain under [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md), with limited access by early/mid Phase 2 under [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md). The [USGS tin overview](https://www.usgs.gov/centers/national-minerals-information-center/tin-statistics-and-information) identifies cassiterite as the principal commercial tin mineral.

The former wire proposal named a niobium plus tin/silver alloy, wire drawing, and cryogenic treatment. These specific fabrication and additive claims were candidate detail, not an accepted route.

## Decision

1. Use the niobium-bearing stream from columbite-tantalite as the baseline niobium feed for the Phase 2 Nb3Sn wire bridge. The limited columbite-tantalite supply already required by ADR-0030 must support both this bridge and the CPU tantalum path.
2. Use cassiterite-bearing feed as the baseline tin source for that bridge.
3. Make limited supply of both feeds and their recovery capabilities accessible by the first time the wire is needed for the Plasma Confinement Facility or its T2a progression, whichever is earlier. Neither a starting-region deposit nor colocation of the two feeds is guaranteed.
4. The access, recovery, and wire-production paths must not require the Plasma Confinement Facility, its own domain packs, or the first Core. Later research design must also avoid cross-domain dependency cycles.

These are feed-family and access decisions, not a selection of extraction or separation chemistry, ore coproduct ratios, wire fabrication, silver or other additives, exact deposit profiles, quantities, yields, recipes, or research gates.

## Options Considered

1. **Share columbite-tantalite for niobium and use cassiterite for tin.** Selected; both are existing plausible feed families and the niobium source is shared with the CPU chain.
2. **Require a separate niobium source or tin as a columbite coproduct.** Not selected; neither additional constraint is needed for the baseline wire path.
3. **Leave both feed families unselected.** Not selected; the mandatory wire bridge could otherwise lack an accessible pre-Core source.

## Rationale

The selected pair supplies the two defining elements of Nb3Sn using established mineral candidates without adding an unnecessary niobium feed family. The access and bootstrap boundaries keep the bridge usable in Phase 2 while leaving the actual refining and wiremaking methods to later design.

## Consequences

- Positive: The Plasma bridge has explicit niobium and tin sources, and the CPU and bridge chains share a known feed.
- Trade-offs: World generation must provide the required feeds in time, and shared columbite-tantalite quantities and coproduct handling need validation.
- Follow-up work: Phase 4 must represent the required recovery and wiremaking capabilities; Phase 5 must verify viable pre-Core paths and shared-feed handling. Later product, recipe, research, and world-generation work must resolve details without requiring the facility or its own packs to bootstrap itself.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Intermediate Products](../intermediate-products.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0020](ADR-0020-seven-distinct-domain-pack-tiers.md), [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md), and [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md).
- Supersedes / superseded by: None.
