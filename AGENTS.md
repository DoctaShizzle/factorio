# Repository Agent Guidance

This repository separates current-state design from historical decision records. Preserve that boundary in every agent-assisted change.

## Required Reading and Source of Truth

Before changing design documentation, read:

- [Documentation Conventions](documentation-conventions.md)
- [Documentation Map](documentation-map.md)
- [Product Taxonomy](product-taxonomy.md) when changing product, constructable, recipe, entity, tier, or technology inventories
- [Plan](plan.md) for phase order and gates

The owning domain document in `documentation-map.md` is the source of truth for current design. Reports provide evidence and recommendations; they are not approved requirements by default.

## Design Documents and ADRs

- Follow `documentation-conventions.md` and the repository templates; they are authoritative when generic skills or workflows conflict.
- Record each significant decision in one sequential ADR under `adrs/`; update `adrs/README.md` and the owning document. Preserve superseded ADRs and link their replacements.

## Migration and Preservation

- Follow the migration and preservation rules in `documentation-conventions.md`: preserve source information and provenance, keep conflicts and unclear acceptance unresolved, and use `Unknown` rather than inventing dates.
- Use relative Markdown links and keep `adrs/README.md` and `documentation-map.md` current.

## Scope and Phase Discipline

- Follow the gates in `plan.md`; do not begin a later phase while its prerequisites remain unresolved.
- Treat `plan.md` as the living stream of current design stages. Keep it up to date as work evolves; stages and sequencing may be modified, shifted, or added. Keep the current status, gates, and next actions accurate. The plan remains a roadmap, not a source for detailed domain design or ADR history.
- Keep counts for products, constructables, entities, machine families, tiers/variants, recipes, and technologies separate.
- Identify core, vanilla-retained, vanilla-modified, vanilla-replaced, and extension scope explicitly.
- Prefer precise, bounded edits. Do not expand a documentation change into unrelated design decisions.
- Check the working tree before editing and preserve unrelated user changes.
