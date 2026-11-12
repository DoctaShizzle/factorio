# ADR-0025: Set Phase 2 CPU Availability and Superconducting Core Compute Progression

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Endgame Vision](../endgame-vision.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) placed the electronic-grade polysilicon precursor in Phase 2 but deferred wafer/chip and cleanroom fabrication until after Core Level 1. This left the candidate packaged-IC input to the first Core without a pre-Core supply path. The user clarified that conventional CPU-grade packaged silicon processors should be available by late Phase 2, while the Core's higher-performance compute should use a near-real superconducting logic technology.

## Decision

1. Make conventional CPU-grade packaged processors available by late Phase 2, before first-Core construction. This partially supersedes ADR-0022's semiconductor timing boundary: a baseline wafer, chip, and packaging capability must exist in Phase 2. Exact routes, equipment, material grades, cleanroom requirements, and research gates remain open.
2. Use conventional CPU-grade packaged processors as the initial compute supply for the first Core.
3. Introduce cryogenic Josephson-junction / Single-Flux-Quantum (SFQ) compute as a later, post-activation Core upgrade, not a first-Core prerequisite. The Core level and unlock gate for this upgrade remain open.
4. Treat Josephson/SFQ logic as a superconducting compute technology, not as superconducting silicon. Its potential low switching energy and high switching rates do not mean electrical signals travel faster; cryogenic cooling, refrigeration power, and control-electronics heat remain part of the system.
5. Replace the semiconductor-grade positioning stage in the first-Core Calibration Reference Frame with a Phase 2-compatible non-semiconductor precision alignment mechanism. Its exact design, materials, machine family, and supply route remain open.

## Options Considered

1. **Keep all wafer/chip fabrication after Core Level 1.** Rejected for the conventional CPU-grade supply: it would leave first-Core compute without the Phase 2 availability the user selected.
2. **Require Josephson/SFQ compute for first-Core activation.** Not selected; it would add an unestablished cryogenic-fabrication dependency to the initial Core gate.
3. **Use conventional packaged CPUs for initial activation and add Josephson/SFQ compute later.** Selected; it provides a non-circular first-Core compute path while reserving a distinct superconducting compute progression.
4. **Keep semiconductor-grade positioning stages as a first-Core input.** Rejected; use a Phase 2-compatible non-semiconductor alignment mechanism instead, with its exact design still open.

## Rationale

Conventional silicon processors provide a credible Phase 2 bootstrap for the initial Core. A later superconducting-logic upgrade gives the Core a more advanced near-future compute identity without making first-Core activation depend on fabrication capabilities that the Core itself is intended to unlock. The distinction preserves the physical limits of superconducting systems: switching may be low-energy and fast, but cryogenic support has a real power and heat cost.

## Consequences

- Positive: The first Core has an intended conventional compute supply, and its later compute progression has a distinct superconducting direction.
- Trade-offs: Phase 2 now requires a baseline conventional semiconductor manufacturing path; its materials, equipment, construction inputs, and gates are not yet specified.
- Follow-up work: Reconcile baseline versus advanced semiconductor equipment phases in Infrastructure and Research and Progression; define the CPU supply route before the Phase 2 exit gate; select and source the non-semiconductor alignment mechanism; and determine the later Josephson/SFQ materials, fabrication, cooling, and Core gate.

## Affected Design and Related Decisions

- Design documents: [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Endgame Vision](../endgame-vision.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md), and [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).
- Supersedes / superseded by: Partially supersedes ADR-0022's post-Core timing for wafer/chip and cleanroom fabrication, and its treatment of packaged ICs as lacking a pre-Core path. ADR-0022's bridge mappings and fission boundary remain in force.
