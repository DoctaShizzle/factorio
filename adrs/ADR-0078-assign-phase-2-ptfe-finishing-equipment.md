# ADR-0078: Assign Phase 2 PTFE Finishing to Existing Equipment Families

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Infrastructure](../infrastructure.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), and [Plan](../plan.md).

## Context

[ADR-0064](ADR-0064-phase-2-ptfe-bootstrap.md) requires first construction-grade PTFE seals and linings to be formed and sintered using Phase 2-compatible, non-PTFE tooling, but leaves equipment allocation open. The infrastructure inventory already includes general press and thermal-processing families.

## Decision

Allocate the initial forming capability to a Phase 2-compatible configuration of the Pellet Press / Briquette Machine family and the sintering capability to a compatible general-purpose thermal furnace in the existing thermal-processing inventory. The equipment and tooling used for the first finished PTFE must be buildable without PTFE and without recovered nuclear HF. A rotary kiln or other suitable existing thermal configuration is a candidate; the exact furnace type and process conditions remain open.

Do not require the later PTFE-die extruder, Phase 3 injection molder, tungsten-carbide specialist tooling, or a separately selected dedicated PTFE machine. This allocation selects capability coverage, not the old proposed tier inputs, exact machine entities, recipe, or service-material compatibility.

## Options Considered

1. **Reuse the existing press and thermal equipment families with a PTFE-free baseline.** Selected.
2. **Require PTFE-dependent finishing equipment or a Phase 3 molder.** Rejected because it breaks the selected bootstrap.
3. **Add a new dedicated PTFE finishing machine.** Not selected.

## Rationale

Reusing general equipment covers the missing end of the accepted PTFE bootstrap without adding a redundant machine family or introducing the finished product into its own construction.

## Consequences

- Positive: The initial PTFE resin-to-construction-material capability has an explicit Phase 2 equipment allocation.
- Trade-offs: Suitable non-PTFE tooling and thermal service must be demonstrated for the eventual process.
- Follow-up work: verify the entire fluorspar-to-finished-PTFE path in Phase 5, including upstream equipment and coproducts; define exact products, machines, recipes, and gates in their owning phases.

## Affected Design and Related Decisions

- Design documents: [Infrastructure](../infrastructure.md), [Chemical Processes](../chemical-processes.md), and [Intermediate Products](../intermediate-products.md).
- Related ADRs: [ADR-0064](ADR-0064-phase-2-ptfe-bootstrap.md) and [ADR-0075](ADR-0075-capability-based-machine-family-tiering.md).
- Supersedes / superseded by: Resolves the equipment-allocation follow-up in ADR-0064 without changing its startup boundary.
