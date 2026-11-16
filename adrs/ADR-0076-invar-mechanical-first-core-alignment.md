# ADR-0076: Use Invar Mechanical Alignment for the First Core

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), and [Research and Progression](../research-progression.md).

## Context

[ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) requires a Phase 2-compatible, non-semiconductor precision alignment mechanism for the first-Core Calibration Reference Frame but left its design and material source open.

## Decision

Use a low-expansion iron-nickel Invar frame with mechanical fine adjustment for the first-Core alignment assembly. The alignment mechanism itself must not require semiconductor-grade positioning hardware. Conventional packaged CPUs remain the selected initial compute supply for the separate Computation Cluster.

Iron and a nickel-bearing feed, alloying, and mechanical fabrication must be available before first-Core construction. Hematite and pentlandite are candidate feed paths, not newly selected deposits or starting-region guarantees. Confirm a viable supply and fabrication route in Phase 5; exact alloy grade, mechanisms, item forms, equipment, quantities, and gates remain open.

## Options Considered

1. **Machined steel frame with mechanical fine adjustment.** Not selected.
2. **Invar frame with mechanical fine adjustment.** Selected.
3. **Keep the mechanism and material open.** Not selected.

## Rationale

The selected low-expansion material provides a distinct precision-construction role while retaining the accepted non-semiconductor and pre-Core boundaries.

## Consequences

- Positive: The first-Core alignment demand has a concrete material family and mechanism.
- Trade-offs: A pre-Core nickel and alloy/fabrication path must now be demonstrated; no particular feed placement is assumed.
- Follow-up work: establish access and an acyclic supply path, then define product forms, quantities, recipes, and technology gates in their respective phases.

## Affected Design and Related Decisions

- Design documents: [Endgame Vision](../endgame-vision.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), and [Research and Progression](../research-progression.md).
- Related ADRs: [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), and [ADR-0037](ADR-0037-defer-array-neutron-reference-material.md).
- Supersedes / superseded by: Resolves ADR-0025's open first-Core alignment mechanism and material family; its CPU and post-activation compute boundaries remain in force.
