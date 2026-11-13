# ADR-0031: Require Starting-Region Access to Quartz and Copper Feeds

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).

## Context

[ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects quartz for metallurgical silicon and malachite, chalcopyrite, and pentlandite as eligible copper feeds for the standard late-Phase-2 CPU path. [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) sets limited early/mid-Phase-2 access to zircon and columbite-tantalite, which supply its hafnium and tantalum. The remaining required source families, quartz and copper, were not guaranteed near the starting region.

## Decision

1. The starting region must provide accessible quartz and a usable copper supply from at least one of the eligible copper-bearing feed families selected in ADR-0029.
2. This is a raw-feed access requirement for the later Phase 2 CPU chain; it does not make semiconductor processing a Phase 1 capability.
3. This selects starting-region accessibility only. Exact copper source, quantities, deposit locations, biome assignments, mining and refining routes, and yields remain open. Other eligible copper deposits may remain regional or rare.

## Options Considered

1. **Provide quartz and at least one copper-bearing feed in the starting region.** Accepted; it keeps the CPU chain's common mineral feeds from becoming a long-range exploration gate.
2. **Require only that quartz and copper be reachable by the late-Phase-2 CPU gate, allowing regional exploration.** Not selected; it adds another potential late access bottleneck to the required CPU path.
3. **Defer feed accessibility while keeping only the CPU dependency.** Not selected; the starting-resource guarantee materially affects world-generation progression.

## Rationale

Quartz and copper are foundational feeds for the required silicon-wafer and Cu/TaN branches. Their starting-region availability secures the CPU trunk while the limited early/mid-Phase-2 zircon and columbite-tantalite supply and richer deposits preserve exploration and logistics progression.

## Consequences

- Positive: The starting region provides the quartz and copper-bearing raw feeds needed by the standard CPU chain without requiring distant exploration for those feed families.
- Negative or trade-offs: The guaranteed starting-resource set expands; world-generation design must balance this access against finite supply and the value of richer regional deposits.
- Follow-up work: Set exact quantities, copper source, placement, extraction/refining routes, and yields during map and resource-chain design. Do not infer Phase 1 semiconductor processing from raw-feed access.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md), [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md), and [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md).
- Supersedes / superseded by: No prior decision is superseded. This sets starting-region access for quartz and copper feeds; ADR-0029's feed-family assignments and ADR-0030's zircon/columbite-tantalite access timing remain in force.
