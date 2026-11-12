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
- ADRs are the sole historical record for decisions. Do not add a `Decision Log`, dated decision entries, `Options Considered`, `Revisions`, or detailed alternatives/rationale for settled decisions to a domain design document. State the operative current design once, then link its ADR in the document's related-ADR list.
- For unresolved design questions, keep the current question, impact, and status in the owning document. Do not repeat the history or alternatives for an already-recorded decision; put substantial decision analysis in an ADR.
- These repository rules override generic agent skills or templates that recommend embedding decision logs in design documents. Use `templates/design-document.md` for current-state documents and `templates/adr.md` for decision history.
- Record each significant decision in one ADR under `adrs/`, using `ADR-NNNN-short-title.md` and the template in `templates/adr.md`. Assign the next unused sequential number and update `adrs/README.md`.
- When a decision changes, preserve the old ADR, mark it superseded, link the replacement, and update the owning design document.
- Do not turn candidates, recommendations, or unresolved questions into approved design without evidence. Label their status explicitly.
- Keep only the concise rationale needed to understand an operative constraint in a design document; put the alternatives, decision rationale, consequences, and chronology in the ADR.
- Before finishing a domain-document change, check that no decision-history section was added and that each significant decision is represented by a related ADR link.

## Migration and Preservation

- Never silently discard, overwrite, or promote source information. Before a migration, identify the source sections and map each to the current design, an ADR, or an explicit unresolved item in `migration-map.md`.
- Preserve known dates and provenance. Use `Unknown` rather than inventing missing dates or decision histories.
- If sources conflict or acceptance is unclear, record the conflict and leave it open instead of choosing by assumption.
- Update cross-references and ownership only after checking the referenced documents. Do not silently replace links to missing documents; record them for reconciliation.
- Use relative Markdown links between repository files and keep the ADR index and `documentation-map.md` current.

## Scope and Phase Discipline

- Follow the gates in `plan.md`; do not begin a later phase while its prerequisites remain unresolved.
- Treat `plan.md` as the living stream of current design stages. Keep it up to date as work evolves; stages and sequencing may be modified, shifted, or added. Keep the current status, gates, and next actions accurate. The plan remains a roadmap, not a source for detailed domain design or ADR history.
- Keep counts for products, constructables, entities, machine families, tiers/variants, recipes, and technologies separate.
- Identify core, vanilla-retained, vanilla-modified, vanilla-replaced, and extension scope explicitly.
- Prefer precise, bounded edits. Do not expand a documentation change into unrelated design decisions.
- Check the working tree before editing and preserve unrelated user changes.
