# ADR-0024: Include Current Chemical-Process Concepts in Core Scope

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Intermediate Products](../intermediate-products.md), [Documentation Conventions](../documentation-conventions.md), [Plan](../plan.md).

## Context

The Chemical Products and Processes draft distinguished four initial chains from later candidates, leaving unclear whether those later process concepts were part of the core experience or optional scope. The user directed that the entire document's current ideas be treated as core scope, not only its four initial chains.

## Decision

1. Include all process-family concepts currently documented in Chemical Products and Processes in the Core design scope, including the initial chains and the additional process concepts currently labeled as later candidates.
2. This scope decision does not approve every listed chemical species, reaction row, recipe, yield, alternative route, or grouped compound as a required distinct product. The registry remains provisional until entries are normalized and technically validated against a downstream use, capability, or meaningful trade-off.
3. Do not treat the prior approximate product or reaction counts as caps or targets. Intermediate-product scope remains capability-driven under [ADR-0006](ADR-0006-capability-based-intermediate-scope.md).

## Options Considered

1. **Keep only the four initial chains in Core and treat later concepts as optional or out of scope.** Rejected; it would narrow the user's intended chemistry scope.
2. **Include the full set of documented process concepts in Core scope while validating product-level details separately.** Selected; it establishes broad scope without turning provisional reaction rows into approved recipes.

## Rationale

The chemical system is intended to support the complete material trunk, including later nuclear, semiconductor, polymer, and energy processes. Defining those process families as Core scope prevents them from being silently deferred as extensions, while separate product and recipe validation preserves the capability-based catalog rule and technical accuracy.

## Consequences

- Positive: the full current chemistry concept set is available for cross-domain trunk mapping and later coverage work.
- Trade-offs: the document's process and product registry is broad and still requires use, route, coproduct, and phase validation before detailed catalog and recipe work.
- Follow-up: distinguish scope status from product/recipe approval in Chemical Products and Processes and reconcile its Phase 2+ process gates with the material and research owners.

## Affected Design and Related Decisions

- Design documents: [Chemical Products and Processes](../chemical-processes.md), [Minerals and Refining](../minerals-and-refining.md), [Intermediate Products](../intermediate-products.md), [Plan](../plan.md).
- Related ADRs: [ADR-0006](ADR-0006-capability-based-intermediate-scope.md), [ADR-0008](ADR-0008-factorio-product-family-coverage.md).
- Supersedes / superseded by: Resolves the Core-scope question for process concepts already present in the Chemical Products and Processes draft; no prior ADR is superseded.
