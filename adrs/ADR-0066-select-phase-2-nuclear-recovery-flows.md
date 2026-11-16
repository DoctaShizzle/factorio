# ADR-0066: Select Phase 2 Nuclear Recovery Flows

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Power System](../power-system.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research Progression](../research-progression.md), [Technical Architecture](../technical-architecture.md), and [Plan](../plan.md).

## Context

[ADR-0057](ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md) requires Phase 2 spent-uranium recovery without selecting its outputs. The thorium route already requires U-233 breeding/reprocessing. The user approved explicit recovered-material destinations and conditioned residual waste while keeping numerical balance deferred.

The [World Nuclear Association used-fuel overview](https://world-nuclear.org/information-library/nuclear-fuel-cycle/fuel-recycling/processing-of-used-nuclear-fuel) supports uranium recovery and reuse, but recovered uranium is not automatically equivalent to fresh qualified fuel, and reprocessing does not eliminate waste.

## Decision

Select these Core capability-level interfaces for the chosen Phase 2 fission route:

| Stream | Required destination |
|---|---|
| Uranium recovered from spent uranium fuel | Recovered uranium oxide -> purification/requalification -> existing uranium conversion/enrichment front end -> qualified oxide fuel and rod fabrication |
| Thorium recovered from the separate thorium cycle | Return to fertile-material preparation, with fresh thorium makeup as required |
| Bred/recovered U-233 | Return through oxide-fuel preparation and cladded rod assembly, separate from depleted uranium and the initial uranium-derived seed |
| Recoverable cladding metal | Controlled metal recovery and qualification; only suitable output returns to the appropriate metallurgy/fabrication route |
| Fluorine-bearing outputs from depleted-UF6 deconversion and enriched-UF6 reconversion | Recover and condition into reusable fluorine reagent supply for UF6 conversion; retain fresh startup and makeup feeds |
| Nuclear-bearing process liquids and other contaminated carriers | Recover useful material/reagents; transfer remaining radioactive fractions to waste conditioning rather than generic release |
| Non-recovered radioactive material and rejected recovery fractions | Immobilization -> sealed waste packages -> engineered terminal disposal under [ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md) |

Keep depleted oxide from enrichment tails distinct under [ADR-0063](ADR-0063-select-depleted-uranium-oxide-reuse.md). Do not return recovered uranium directly as qualified pellets, assume all cladding is nuclear-grade, or model a lossless closed fuel cycle.

The thorium gameplay model still needs no continuous uranium top-up after startup. Do not introduce that dependency through waste-cask shielding or other back-end consumables.

No separate plutonium product, MOX route, or military-ammunition dependency is selected. Unrecovered actinides and fission products remain within the residual-waste role; detailed species and grouping are catalog decisions.

Make the minimum recovery and residual-handling capabilities available in Phase 2 by first production of the streams they handle. Exact process chemistry, isotope/grade qualification, recovery losses, cooling/buffer design, equipment split, recipes, capacities, and research gates remain open. No particular storage-pool or backup-power mechanic is selected.

## Options Considered

1. **Leave all recovered streams and waste fates open.** Not selected; it prevents meaningful source/consumer coverage of the required branch.
2. **Restore spent fuel directly to fresh rods.** Rejected; it hides enrichment, qualification, losses, and residual waste.
3. **Recover uranium and suitable materials through qualified routes, with a separate residual endpoint.** Selected; it closes material interfaces without claiming a numerical balance.
4. **Require plutonium or military demand.** Not selected; neither is needed for the approved recovery capability.

## Rationale

Explicit destinations distinguish recoverable resources from unavoidable residues. Reusing the existing front end limits new process-family scope while retaining the need to qualify recovered material rather than treating chemical form alone as fuel grade.

## Consequences

- Positive: both fission back ends and both UF6 branches have defined material handoffs.
- Negative or trade-offs: recovery needs reagents, energy, qualification, makeup, and a nonzero residual-handling path; no numerical recovery performance is implied.
- Follow-up work: Phase 5 must verify viable handoffs and startup; Phases 6-8 define products, detailed chemistry/recipes, balances, equipment assignments, and gates under their existing prerequisites.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md) owns cycle direction; [Chemical Processes](../chemical-processes.md) owns chemistry; [Intermediate Products](../intermediate-products.md) owns product roles/fates; [Infrastructure](../infrastructure.md) owns required equipment capability; [Research Progression](../research-progression.md) owns gates; [Technical Architecture](../technical-architecture.md) must keep the required back end out of extension-only scope.
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md), [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md), [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md), [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md), [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md), [ADR-0057](ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md), [ADR-0063](ADR-0063-select-depleted-uranium-oxide-reuse.md), and [ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md).
- Supersedes / superseded by: Partially supersedes ADR-0057's recovered-stream and fate deferral; its required Phase 2 recovery capability and exclusion of inferred plutonium/military links remain in force. Refines the thorium recovery interfaces in ADR-0023/0055 and HF integration in ADR-0054.
