# ADR-0026: Place Contemporary Cleanroom and Advanced Chipmaking in Phase 2

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), and [Plan](../plan.md).

## Context

[ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) makes conventional CPU-grade packaged processors available by late Phase 2 for the first Core, while leaving their production route, equipment, material grades, cleanroom requirements, and research gates open. The user clarified that full cleanroom and advanced chipmaking up to contemporary real-world practice belong in Phase 2; post-Core progression should be primarily science-fiction or otherwise beyond current industrial practice.

## Decision

1. Make full contemporary cleanroom and advanced semiconductor-manufacturing capability available in Phase 2, including the capability to produce and package the selected conventional CPU-grade processors.
2. Use present-day real-world industrial practice as the era boundary, not a specific process node or equipment roster. Exact machine tiers, process routes, material grades and quantities, and research gates remain open; the required material-family set is selected separately in [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md).
3. Keep post-Core progression primarily focused on speculative capabilities beyond current-day industrial practice. The exact technologies and gates remain open.
4. Preserve ADR-0025's decisions that conventional packaged processors supply the first Core and Josephson-junction / Single-Flux-Quantum compute is a later Core upgrade.

## Options Considered

1. **Limit Phase 2 to a baseline CPU line and reserve contemporary advanced cleanroom and chipmaking for after Core activation.** Rejected; it would place real-world manufacturing capability behind the science-fiction progression the Core is meant to open.
2. **Place full contemporary cleanroom and advanced chipmaking in Phase 2, reserving post-Core progression primarily for beyond-current-day capabilities.** Accepted; this matches the selected technology-era boundary while preserving the first-Core CPU supply.

## Rationale

The Phase 2 boundary now includes the full cleanroom and semiconductor capability that exists in present-day industry. The Core therefore does not gate the real-world manufacturing capability needed to supply its own initial computation; it opens the primarily speculative progression beyond that boundary.

## Consequences

- Positive: Contemporary cleanroom and chipmaking capability has a clear Phase 2 home, and post-Core progression has a distinct beyond-current-day direction.
- Negative or trade-offs: Phase 2 has a larger semiconductor materials and infrastructure demand than a baseline CPU line alone; its full supply path must be established.
- Follow-up work: Reconcile candidate machine phases and semiconductor research gates with this boundary. Define the material grades, routes, equipment, recipes, and research gates before the Phase 2 exit gate; do not treat candidate inputs or equipment details as approved merely because the capability boundary is accepted.

## Affected Design and Related Decisions

- Design documents: [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Research and Progression](../research-progression.md), [Endgame Vision](../endgame-vision.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).
- Related ADRs: [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), and [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md).
- Supersedes / superseded by: Clarifies the contemporary semiconductor timing boundary left open by ADR-0025. ADR-0022's bridge mappings and fission boundary remain unchanged; ADR-0025's CPU availability and later superconducting-compute decisions remain in force.
