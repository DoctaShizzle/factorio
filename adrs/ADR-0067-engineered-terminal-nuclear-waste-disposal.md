# ADR-0067: Permit Engineered Terminal Disposal of Nuclear Solids

*Status: Superseded by [ADR-0068](ADR-0068-continuous-nuclear-waste-disposal.md)*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Power System](../power-system.md), [Mod Overview](../mod-overview.md), [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Technical Architecture](../technical-architecture.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

The balance policy allowed powered, pollution-producing gas/fluid disposal but no terminal solid-waste endpoint. Nuclear recovery leaves radioactive residues, and depleted-oxide reuse cannot guarantee continuous demand. The user explicitly approved a narrow exception for conditioned nuclear solids rather than pretending recycling removes all waste.

## Decision

1. Permit intentional terminal emplacement of conditioned nuclear solids from the selected fuel cycles, including non-recovered radioactive residues and surplus depleted uranium oxide. This is a Core nuclear-waste exception to the general solid-coproduct and permanent-accumulation restrictions, not a generic solid voider.
2. Require the selected useful-material recovery first. Spent rods and untreated nuclear-bearing liquids are not direct substitutes for conditioned waste packages; disposal must not bypass [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md).
3. Immobilize residual material in a suitable stable matrix, seal it into shielded packages, and emplace the packages in purpose-built, finite-capacity engineered repository cells. Exact matrix chemistry, site constraints, package identities, and constructable split remain open.
4. Keep occupancy visible and persistent. Continued operation requires additional repository capacity when cells fill; this is intentional terminal disposal, not a buffer assumed to empty later. Do not silently delete packages or accept unrelated ordinary solid overflow.
5. Give conditioning and emplacement construction and operating costs, including power during processing/emplacement. Sealed containment must not require a new permanent backup-power or blackout-failure loop. Exact costs, throughput, capacity, and pollution treatment remain deferred.
6. Provide suitable ordinary shielding as an alternative to depleted-uranium shielding for the entire back end. Thorium operation after its startup seed must not depend on continued uranium enrichment or tails production.
7. Retain radioactive fractions from nuclear-bearing gas/liquid streams in recovery and conditioning. The generic Gas Flare Stack and Liquid Effluent Clarifier must not directly erase those fractions; suitably cleaned carrier streams may use the ordinary gas/fluid policy.
8. Make minimum recovery, conditioning, packaging, and emplacement available in Phase 2 by the first corresponding output. Optional extensions may add isotope/decay detail but cannot be the sole home of this endpoint. Numerical balance remains deferred.

## Options Considered

1. **Require complete recycling with no residue.** Rejected; it hides losses and radioactive residual material.
2. **Rely on ammunition or construction growth forever.** Not selected; demand does not guarantee a sink for steady nuclear operation.
3. **Use a general solid voider or unrestricted radioactive-fluid release.** Rejected; it bypasses recovery and removes the intended containment tradeoff.
4. **Use costly, finite-capacity terminal nuclear repositories.** Selected; it makes the exception explicit and gives unavoidable residuals a legitimate endpoint.

## Rationale

Terminal disposal is a different product role from an operating buffer. A visible, capacity-limited endpoint allows nuclear operation without compulsory combat or endless useful-product demand, while preserving material accountability and a meaningful long-term footprint.

## Consequences

- Positive: the selected nuclear cycles have a residual endpoint even with no military demand or new nuclear-building construction.
- Negative or trade-offs: continuous nuclear operation consumes repository capacity and construction materials; this deliberately permits permanent emplacement within a narrowly bounded exception.
- Follow-up work: verify uranium operation with saturated reuse demand and thorium operation without new uranium supply; define packaging, repository scope, capacities, recipes, and gates in the existing design phases. Do not report the flows as numerically balanced before Phase 7 validation.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md) owns nuclear endpoint behavior; [Mod Overview](../mod-overview.md) owns the cross-domain guardrail; [Minerals and Refining](../minerals-and-refining.md) and [Chemical Processes](../chemical-processes.md) apply the handling exception; [Intermediate Products](../intermediate-products.md) owns packaged-product roles; [Infrastructure](../infrastructure.md) owns repository capabilities; [Technical Architecture](../technical-architecture.md) owns extension boundaries; [Research Progression](../research-progression.md) owns gates; [Plan](../plan.md) tracks validation.
- Related ADRs: [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md), [ADR-0059](ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md), [ADR-0063](ADR-0063-select-depleted-uranium-oxide-reuse.md), and [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md).
- Supersedes / superseded by: Superseded by [ADR-0068](ADR-0068-continuous-nuclear-waste-disposal.md), which replaces finite repository capacity with continuous powered/material-consuming disposal and slight pollution. The original decision text above is preserved. Its partial amendments to ADR-0035's nuclear-stream eligibility/solid-handling boundary and ADR-0057's residual-destination deferral continue through ADR-0068; ordinary gas/fluid disposal and required nuclear recovery remain in force.
