# ADR-0029: Assign Phase 2 Mineral Feed Families for the Core CPU Chain

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), and [Plan](../plan.md).

## Context

[ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) requires silicon wafers, lithography chemistry, HfO₂ dielectric, Cu/TaN interconnect, and package-material families for contemporary Phase 2 chipmaking. [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md) requires all five families on the standard late-Phase-2 CPU path for initial Core supply. The mineral inventory contains candidate source-family associations for silicon, hafnium, tantalum, and copper, but they had not been selected for this path.

## Decision

1. Select quartz as the mineral feed family for metallurgical silicon in the Phase 2 CPU chain.
2. Select zircon as the hafnium-bearing feed family; hafnium remains a secondary product of the zirconium-bearing feed.
3. Select columbite-tantalite as the tantalum-bearing feed family; tantalum remains a secondary product of the niobium-bearing feed.
4. Accept the existing copper-bearing feed families—malachite, chalcopyrite, and pentlandite—as eligible copper sources. No exact ore mix or priority among these sources is selected.
5. These assignments establish feed families for the standard late-Phase-2 CPU path. They do not select extraction, separation, or refining routes; grades, yields, quantities, phase gates, and resource placement/accessibility remain open.

## Options Considered

1. **Accept all current feed-family associations for the CPU chain.** Accepted; it resolves the source-family level while preserving detailed route and balance work.
2. **Accept silicon and copper feeds but defer the hafnium and tantalum coproduct feeds.** Not selected; it would leave required CPU material families without a source-family assignment.
3. **Keep all feed-family assignments provisional.** Not selected; the direct CPU-to-Core trunk now requires these source families to be explicit.

## Rationale

Selecting the existing source families makes the required CPU material stack traceable to the mineral inventory without prematurely promoting candidate mining and refining processes. The zirconium/hafnium and niobium/tantalum coproduct relationships remain visible as consequential trunk dependencies.

## Consequences

- Positive: The required silicon, hafnium, tantalum, and copper inputs have explicit Phase 2 source-family assignments for the standard CPU path.
- Negative or trade-offs: Hafnium and tantalum supply depends on coproduct-bearing feeds; their yields and useful coproduct sinks must be established during route design.
- Follow-up work: Demonstrate viable mining, recovery, separation, and refining paths and ensure the source families are reachable before the late-Phase-2 CPU gate. Keep exact deposit locations, ore mix, grades, and balancing open.

## Affected Design and Related Decisions

- Design documents: [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Research and Progression](../research-progression.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md), and [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md).
- Supersedes / superseded by: No prior decision is superseded. This assigns source families for the material requirements established in ADR-0027 and ADR-0028; ADR-0030 sets limited early/mid-Phase-2 access for zircon and columbite-tantalite. Detailed source and process routes remain open.
