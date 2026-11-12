# Project Prometheus Documentation Conventions

*Status: Approved for the documentation pilot*
*Last updated: 2026-11-12*

## Purpose

Keep current design, historical decisions, evidence, and product-tree coverage distinct while preserving traceability between them.

## Document Roles and Locations

| Artifact | Canonical location | Role |
|---|---|---|
| Current-state design documents | Existing root-level domain documents | State the current intended design, scope, dependencies, and open decisions for the owned domain. |
| Architecture Decision Records (ADRs) | `adrs/ADR-NNNN-short-title.md` | Preserve one significant decision's context, alternatives, outcome, rationale, and consequences. The index is `adrs/README.md`. |
| Reusable templates | `templates/design-document.md` and `templates/adr.md` | Provide the required structure for new or migrated documents. |
| Product-tree coverage ledger | `product-coverage-ledger.md` | Canonical coverage matrix, introduced in Phase 4. Use Markdown tables with stable entry IDs and links to owning design documents. |
| Plans and work checkpoints | `plan.md` and session checkpoints | Track sequence, gates, progress, and handoffs; they do not own domain design. |
| Reports and comparative analyses | Existing report documents | Provide evidence and recommendations. They do not become approved design merely by being present. |

Use relative Markdown links between repository documents. ADR IDs are sequential, stable, and never reused. Do not create an ADR for every minor edit; record decisions that materially affect scope, behavior, dependencies, or progression.

## Current-State Design Rules

- Describe the approved or intended current design, not the history of how it evolved.
- Distinguish **approved**, **proposed**, **deferred**, and **open** content explicitly. Do not promote candidates or recommendations to requirements without an accepted decision.
- Keep concise current rationale when it helps explain a constraint; link to the ADR for alternatives and full decision history.
- State the document's purpose, boundaries, dependencies, current design, and unresolved decisions. Use the template as the starting structure, adapting sections to the domain.
- Each design area has one owning document, as listed in `documentation-map.md`. Other documents may summarize it but must link to the owner rather than establish a competing source of truth.

## ADR Rules

- Record one coherent decision per ADR. Preserve the original decision date when known; otherwise state that the date is unknown rather than inventing one.
- Record context, status, viable alternatives where recoverable, the decision, rationale, consequences, affected design documents, and links to related or superseding ADRs.
- Mark decisions that change as superseded and link to the replacement. Do not erase the old decision.
- During migration, preserve all source information. Move history into ADRs, update current-state documents, and keep a migration map. If provenance or acceptance is unclear, flag it for review instead of guessing.

## Product-Tree Counting and Scope Rules

Use the definitions and counting rules in `product-taxonomy.md`. Keep distinct counts for products, constructables, entities, machine families, tiers/variants, recipes, and technologies.

Classify scope explicitly:

- **Core:** required content in the main Project Prometheus experience.
- **Vanilla retained:** existing Factorio content used without a Prometheus replacement.
- **Vanilla modified:** vanilla content whose behavior, recipe, or progression changes.
- **Vanilla replaced:** vanilla content intentionally supplanted by Prometheus content.
- **Extension:** optional content outside the core experience; record dependencies on core content.

These are scope labels, not mutually exclusive product classes. Do not include extension-only content in core totals. Do not count retained vanilla content as a new Prometheus product unless it is materially modified or replaced.
