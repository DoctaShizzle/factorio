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

- Design documents describe the current intended design, accepted constraints, dependencies, and open questions. Keep old alternatives and decision chronology out of their main body; link to ADRs where the decision history matters.
- Record each significant decision in one ADR under `adrs/`, using `ADR-NNNN-short-title.md` and the template in `templates/adr.md`. Assign the next unused sequential number and update `adrs/README.md`.
- When a decision changes, preserve the old ADR, mark it superseded, link the replacement, and update the owning design document.
- Do not turn candidates, recommendations, or unresolved questions into approved design without evidence. Label their status explicitly.
- Keep concise current rationale in a design document when useful; put alternatives and full historical rationale in the ADR.

## Migration and Preservation

- Never silently discard, overwrite, or promote source information. Before a migration, identify the source sections and map each to the current design, an ADR, or an explicit unresolved item in `migration-map.md`.
- Preserve known dates and provenance. Use `Unknown` rather than inventing missing dates or decision histories.
- If sources conflict or acceptance is unclear, record the conflict and leave it open instead of choosing by assumption.
- Update cross-references and ownership only after checking the referenced documents. Do not silently replace links to missing documents; record them for reconciliation.
- Use relative Markdown links between repository files and keep the ADR index and `documentation-map.md` current.

## Scope and Phase Discipline

- Follow the gates in `plan.md`; do not begin a later phase while its prerequisites remain unresolved.
- Keep counts for products, constructables, entities, machine families, tiers/variants, recipes, and technologies separate.
- Identify core, vanilla-retained, vanilla-modified, vanilla-replaced, and extension scope explicitly.
- Prefer precise, bounded edits. Do not expand a documentation change into unrelated design decisions.
- Check the working tree before editing and preserve unrelated user changes.
