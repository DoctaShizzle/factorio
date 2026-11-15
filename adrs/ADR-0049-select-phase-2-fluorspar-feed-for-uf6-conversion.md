# ADR-0049: Select Fluorspar as the Phase 2 Fluorine Feed

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Power System](../power-system.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the high-level uranium-concentrate-to-UF6 conversion, gas-centrifuge enrichment, and UO2 reconversion path. Its fluorine-bearing feed and access requirements were unresolved.

The USGS identifies fluorspar as fluorite (calcium fluoride) and states that it is used directly or indirectly to manufacture uranium fuel. The same source notes that byproduct fluorosilicic acid from some phosphoric-acid producers supplements fluorspar as a domestic source of fluorine ([Fluorspar Statistics and Information](https://www.usgs.gov/centers/national-minerals-information-center/fluorspar-statistics-and-information)).

## Decision

1. Select mined fluorspar (fluorite) as the baseline fluorine-bearing mineral feed for Phase 2 uranium conversion to UF6.
2. Make limited fluorspar supply accessible no later than the UF6-conversion unlock. This does not require the feed to be guaranteed in the starting region; exact deposit occurrence, placement, and quantity remain open.
3. Keep phosphoric-acid-derived fluorosilicic acid as a possible supplemental route only; it is not required by the baseline and is not selected as a production route.
4. This decision does not select fluorite recovery, grade, fluorine reagent form or preparation, conversion chemistry, equipment, material or power balances, recipes, or research gates.

## Options Considered

1. **Fluorspar baseline by the UF6-conversion unlock.** Selected; it provides a mineral feed for the fluorine-dependent uranium route without making fuel availability depend on a phosphoric-acid process.
2. **Phosphoric-acid-derived fluorosilicic acid as the baseline.** Not selected; it would couple uranium fuel availability to a phosphate-processing route that has not been defined.
3. **Keep the fluorine feed and access generic.** Not selected; the high-level uranium material trunk would retain an unresolved source and access dependency.

## Rationale

Fluorspar is a documented mineral source associated with uranium-fuel manufacture, and the existing mineral-refining design already represents fluorite as a candidate feed. Selecting it establishes the required Phase 2 mineral family and access gate while leaving the actual recovery and conversion route open. Treating fluorosilicic acid as optional avoids making the fission path depend on an unselected phosphate-processing chain.

## Consequences

- Positive: the Phase 2 uranium route has a selected fluorine-bearing mineral feed and a bounded access requirement.
- Negative or trade-offs: a fluorspar source must be placed and made recoverable by the conversion unlock; no starting-region guarantee or deposit configuration is selected.
- Follow-up work: determine fluorite occurrence and recovery, grades and quantities, reagent preparation, detailed uranium conversion chemistry, and the associated power, pollution, equipment, and research requirements.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Chemical Products and Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Power System](../power-system.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) selects the uranium material-form sequence; [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) selects its mined uranium feed; [ADR-0040](ADR-0040-phase-2-lfp-feed-sources-and-access.md) selects starting-area phosphate and lithium-bearing feeds for LFP storage.
- Supersedes / superseded by: No prior decision is superseded. This resolves the fluorine-feed family and access boundary left open by ADR-0048; detailed recovery and chemistry remain open.
