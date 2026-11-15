# ADR-0060: Select Monazite as the Phase 2 Thorium Feed

*Status: Accepted*
*Decision date: 2026-11-15*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), and [Plan](../plan.md).

## Context

[ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects a Th-232 fuel cycle with a uranium-derived fissile startup seed and U-233 breeding/reprocessing in the gameplay model. [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the shared uranium chain only for that startup seed, and [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) selects a separate ThO2-bearing fertile blanket. The mined source for the blanket's Th-232 feed and its access timing remained open.

[ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) selects Uraninite as the uranium feed and leaves its listed thorium secondary as a candidate only. The current [Minerals and Refining](../minerals-and-refining.md) design already lists monazite in candidate deposit profiles, but does not yet assign it a thorium recovery route. The [World Nuclear Association thorium overview](https://world-nuclear.org/information-library/current-and-future-generation/thorium) identifies monazite as the most common thorium source and describes recovery of thorium oxide from it.

The user asked that Phase 2 work proceed autonomously with semi-realistic, non-annoying defaults while surfacing major decision paths. This is that pragmatic default, not a direct answer to the specific feed-selection question.

## Decision

1. Select monazite-bearing deposits as the baseline mined feed family for the Th-232-bearing fertile stream used in the Phase 2 thorium blanket.
2. Require limited supply to be reachable no later than the thorium power-route unlock. A starting-region guarantee is not required.
3. Keep Uraninite's listed thorium secondary as a candidate only; it is not the baseline Th-232 feed or a required coproduct.
4. This selects only the feed family and access boundary. Exact deposit assignment, recovery chemistry, output form and grade, quantities, residues, balances, equipment, and research gates remain open.

## Options Considered

1. **Monazite-bearing deposits.** Selected; monazite is an established thorium source and already appears in candidate deposit profiles, allowing a distinct thorium feed without adding a standalone mineral family. Recovery and residue handling still require design.
2. **Uraninite secondary thorium.** Not selected; it would couple the thorium blanket feed to the uranium mine and promote a candidate secondary stream that ADR-0050 did not select as a required coproduct.
3. **A dedicated thorium-bearing deposit, such as thorite.** Not selected; it would add a new deposit family and processing route when an existing monazite-bearing candidate can serve as the baseline.
4. **Defer the feed source.** Not selected; leaving the source unbounded would prevent completing the optional thorium route's Phase 2 material-access path.

## Rationale

Monazite is a realistic, established thorium source and is already represented in the candidate geological profiles. Selecting it keeps the thorium feed distinct from Uraninite, while avoiding a new dedicated ore family or a starting-region resource guarantee. The Phase 2 route remains optional and does not become a first-Core prerequisite. The choice does not imply a particular monazite concentration, deposit location, recovery method, or material balance.

## Consequences

- Positive: the thorium route has a distinct high-level mined feed and a bounded access requirement.
- Negative or trade-offs: the route depends on prospecting and a separate thorium recovery path; process residues and interactions with rare-earth or phosphate processing remain to be designed.
- Follow-up work: assign the relevant monazite-bearing deposit profile, define recovery to a ThO2-bearing fertile stream and its residue handling, and determine grades, quantities, balances, equipment, and research gates. Do not infer monazite as a guaranteed coproduct of the starting-region LFP phosphate feed.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) selects the startup-seed and U-233 gameplay model; [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) selects the uranium source for the startup seed; [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) selects Uraninite for uranium and leaves its thorium secondary unselected; [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) selects the separate ThO2-bearing blanket.
- Supersedes / superseded by: No decision is superseded. This resolves the Th-232 feed-family and access-boundary gap without changing the uranium feed or startup-seed decisions.
