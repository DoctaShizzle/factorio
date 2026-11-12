# ADR-0008: Map Factorio Product Families Before Cataloging

*Status: Accepted; item-level coverage and version-specific inventory deferred*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Intermediate Products](../intermediate-products.md), [Product Taxonomy](../product-taxonomy.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md).

## Context

The product-tree goal spans raw and refined materials, manufactured products, constructables, usable outputs, and research ingredients. The non-building product catalog must account for products used for construction, vehicles and fuels, weapons and ammunition, personal equipment and modules, research, and endgame progression without duplicating building inventories or omitting less obvious Factorio-style product families.

The user requested mapping products to all applicable Factorio categories as a completeness check. The exact Factorio version, vanilla-content disposition, and final item roster are not yet established.

## Decision

Maintain a category-level, Factorio-style product-family checklist before detailed product enumeration. For each family, record its scope disposition and authoritative owner. Keep non-building product identities and uses in the product catalog; keep placeable entities and construction-demand hypotheses in Infrastructure; keep domain behavior and process routes in their owning documents.

The checklist is an audit aid, not a commitment to add every vanilla or modded item. The coverage phase must cross-check the categories against the selected Factorio version and the project's core, vanilla, extension, and out-of-scope labels.

## Options Considered

1. **Catalog products only as they are discovered.** This is simple initially but makes it easier to overlook whole product families.
2. **Create a Factorio-style product-family checklist with ownership and scope dispositions.** This supports completeness while preserving the existing domain ownership boundaries.
3. **Put every product family and entity in one catalog.** This would blur the distinction between product outputs, placeable entities, domain behavior, and research mechanics.

## Rationale

The category checklist provides a systematic way to find omissions while preserving the project's separation between non-building products, placeable constructables, and domain-specific system designs. Deferring item-level decisions avoids treating category existence or vanilla precedent as proof that a product belongs in the mod.

## Consequences

- Positive: product coverage can be checked across construction, logistics, vehicles, energy, combat, personal equipment, research, space, and other relevant families.
- Trade-off: some families remain explicitly unresolved until the Factorio version and scope are confirmed.
- Follow-up: use the checklist during Phase 4; disposition biological/agricultural products, terrain items, interface tools, and any version-specific families before the coverage gate.

## Affected Design and Related Decisions

- Design documents: [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Product Taxonomy](../product-taxonomy.md), [Plan](../plan.md).
- Related ADRs: [ADR-0006](ADR-0006-capability-based-intermediate-scope.md); [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md).
- Supersedes / superseded by: No superseding ADR recorded.
