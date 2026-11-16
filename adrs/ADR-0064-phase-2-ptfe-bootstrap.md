# ADR-0064: Provide a PTFE-Free Phase 2 PTFE Bootstrap

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Chemical Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Minerals and Refining](../minerals-and-refining.md), [Map and World Generation](../map-world-generation.md), [Research Progression](../research-progression.md), and [Plan](../plan.md).

## Context

The candidate Uranium Conversion Line and Zr/Hf Separation Plant use PTFE construction. The initial Polymerization Reactor was limited to polyethylene, while its next tier already required PTFE. The monomer route was open, so a first-batch construction loop was possible rather than proven. The user approved a baseline polymerization route that does not consume its own product in construction.

## Decision

1. Make PTFE production available in the baseline Phase 2 Polymerization Reactor / Vessel before the first PTFE-consuming nuclear or cleanroom equipment. No new polymerization machine family is selected.
2. Its initial construction must use a compatible metal pressure vessel and non-PTFE sealing. Stainless steel and service-appropriate metal/graphite seals are construction candidates, not a claim of universal compatibility with fluorine reagents.
3. Supply the first fluorine reagents and fluoromonomer from fluorspar and existing Phase 2 chemical/petrochemical capabilities. The complete startup path must be buildable without PTFE and without recovered HF from an operating uranium cycle.
4. Make fluorspar accessible by this first fluorochemical use, no later than its existing UF6-conversion deadline. Do not add a starting-region guarantee.
5. Include Phase 2-compatible initial forming/sintering of construction-grade PTFE seals and linings. This finishing path must not require a PTFE die, an already PTFE-lined machine, or a Phase 3-only molding press.
6. Retain PTFE-lined polymerization upgrades and the candidate PTFE requirements of nuclear equipment after the bootstrap. Detailed monomer chemistry, material compatibility, equipment allocation, recipe quantities, and research gates remain open.

## Options Considered

1. **Require PTFE-lined equipment for the first PTFE.** Rejected; it leaves the startup dependency unresolved.
2. **Remove PTFE from all nuclear construction.** Not selected; it discards a useful chemical-service material rather than establishing its supply.
3. **Use the baseline polymerization family with a PTFE-free upstream and finishing path.** Selected; it breaks the loop without another machine family.
4. **Provide a free starter inventory or hand-crafted exception.** Not selected; startup should follow a repeatable industrial path.

## Rationale

PTFE production does not inherently require pre-existing PTFE; even the [original polymer patent](https://patents.google.com/patent/US2230654A/en) describes production in a steel container. Actual process-service compatibility still needs validation when the chemistry is chosen. The accepted boundary is an acyclic capability path, not an approved detailed plant recipe.

## Consequences

- Positive: PTFE can supply its first nuclear consumers without relying on the nuclear reagent-recovery loop.
- Negative or trade-offs: initial vessel/seal compatibility and PTFE finishing require explicit coverage rather than an assumed generic plastics recipe.
- Follow-up work: verify the entire mineral-to-monomer-to-finished-PTFE path in Phase 5, assign equipment in Phase 4, and define products, recipes, and gates in Phases 6-8.

## Affected Design and Related Decisions

- Design documents: [Chemical Processes](../chemical-processes.md) owns chemistry; [Infrastructure](../infrastructure.md) owns baseline and upgraded equipment; [Intermediate Products](../intermediate-products.md) owns resin and construction-product roles; [Minerals and Refining](../minerals-and-refining.md) and [Map and World Generation](../map-world-generation.md) own feed recovery and access; [Research Progression](../research-progression.md) owns gates.
- Related ADRs: [ADR-0024](ADR-0024-include-chemical-process-concepts-in-core-scope.md), [ADR-0045](ADR-0045-phase-2-zirconium-hafnium-separation-stage.md), and [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md).
- Supersedes / superseded by: Refines ADR-0049's access boundary to cover earlier PTFE startup; its fluorspar selection and lack of a starting-region guarantee remain unchanged. Replaces unapproved candidate equipment dependencies, not an accepted polymerization tier roster.
