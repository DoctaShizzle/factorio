# ADR-0037: Defer the Array's Neutron-Reference Material Selection

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Intermediate Products](../intermediate-products.md), [Endgame Vision](../endgame-vision.md), and [Plan](../plan.md).

## Context

[ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md) requires the Unified Metrology Reference Array for first-Core construction. Its candidate material list includes deuterium-enriched water (D₂O) and unspecified neutron-reference materials. [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) explicitly excludes enriched fission fuel as a first-Core prerequisite but leaves the Array's specific neutron-reference inputs open.

Selecting a reference material without a defined instrument bill of materials could introduce an unsupported new product or resource dependency. The exact material can be chosen when the Array's physical design and construction requirements are detailed, provided the first-Core constraints remain explicit.

## Decision

Defer selection of the specific neutron-reference material and its supply route until the Unified Metrology Reference Array's bill of materials is designed. Retain the neutron-reference function as a placeholder; do not treat any candidate as selected or add a new product or mineral feed by assumption.

Before the Array's bill of materials and recipe are finalized, select a specific input and demonstrate a supply path available before first-Core construction. The input must not require enriched fission fuel. This deferral does not remove or weaken the accepted first-Core requirement for the Array.

## Options Considered

1. **Select a specific neutron-reference material and route now.** Deferred; the Array's detailed instrument design and bill of materials are not yet defined.
2. **Defer the material choice with explicit pre-Core and no-enriched-fuel constraints.** Accepted; preserves the Core gate without assuming a new material chain.
3. **Remove the neutron-reference function from the Array.** Not selected; no change to the accepted Array concept or first-Core gate was requested.

## Rationale

The deferral keeps the first-Core material chain bounded while preserving the Array's intended neutron-reference function. Requiring a proven pre-Core supply route before finalizing the bill of materials prevents a later material choice from creating a hidden post-Core or enriched-fuel dependency.

## Consequences

- Positive: No new material, mineral feed, or fission dependency is introduced into the Phase 2 trunk by assumption.
- Trade-offs: The Array's final constructability and recipe cannot be considered complete until this input is selected and its pre-Core supply is demonstrated.
- Follow-up work: Resolve the specific material and route during Array bill-of-materials design, before its recipe and construction requirements are finalized.

## Affected Design and Related Decisions

- Design documents: [Intermediate Products](../intermediate-products.md), [Endgame Vision](../endgame-vision.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md), which requires the Array for the first-Core gate, and [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), which excludes enriched fission fuel as a first-Core prerequisite.
- Supersedes / superseded by: No prior decision is superseded. This records the safe deferral and guardrails for an input left open under ADR-0017 and ADR-0022.
