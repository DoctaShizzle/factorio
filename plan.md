# Project Prometheus: Design Coverage and Product-Tree Plan

*Status: Working plan*

## Purpose

Use this plan to bring the design documents into a clean, consistent state and then establish complete coverage of the player-facing production and progression tree:

**mineral feeds -> pure raw materials -> manufactured products -> buildable/usable outputs and research ingredients**

This is an execution roadmap, not a design decision record or a replacement for the domain design documents. It defines the order of work, deliverables, and gates. The detailed product names, recipes, quantities, and technologies are not considered final until their designated phases.

## Scope

The coverage work includes:

- Mineral deposits, mined feeds, and refining outputs.
- Manufactured materials and components used by other products.
- Buildings, machines, infrastructure, and their construction requirements.
- Player and factory utilities, including vehicles and their fuel.
- Weapons and ammunition.
- Armor equipment, utilities, and modules.
- Research ingredients and, later, the technologies that consume or unlock them.
- Endgame and other progression-critical products.

For counting and traceability, distinguish product types from placeable entities, machine families, tiers/variants, recipes, and technologies. An item may have multiple roles; give it one primary category and record other roles as tags.

## Documentation Model

Design documents and ADRs have separate jobs:

- **Design documents** describe the current intended design. They are the source of truth for scope, behavior, systems, dependencies, and current open questions. Keep historical option-by-option deliberation out of them; link to relevant ADRs when rationale matters.
- **ADRs** preserve dated decision history: context, options considered, decision and status, rationale, consequences, and links to affected design documents and related ADRs. Superseded decisions remain available and point to their replacements.
- **Reports** such as the comparative gap analysis remain evidence and analysis, not automatically approved design or ADRs. Accepted findings are recorded as decisions and reflected in current-state design documents.
- **This plan** tracks the work sequence and gates; it is not the source of truth for domain design or a historical decision log.

The ADR location, naming convention, canonical coverage-ledger location, and exact document boundaries are Phase 0 decisions. Do not start a broad migration before agreeing on these conventions.

## Working Rules

- Treat existing inventories and the gap analysis as candidates to verify, not as approved counts or mandatory scope.
- Prefer meaningful engineering choices and progression capabilities over catalog size or recipe count.
- Every mandatory product must have a clear source and a legitimate use. A buildable or usable endpoint may be a terminal goal.
- Review single-consumer intermediates for whether they should instead be a direct recipe input; do not add artificial consumers just to satisfy a numeric rule.
- Every mandatory chain must trace to an approved mineral feed or vanilla starting resource.
- Account for recipe coproducts with a useful consumer, a bounded buffer, or production control. Required voiding and permanent accumulation are not acceptable.
- Multiple routes are for meaningful tradeoffs, not a requirement for every product.
- Keep core-mod and optional-extension scope explicit.
- Record decisions once in the appropriate ADR and maintain current state in the owning design document.

## Source Documents and Starting Evidence

Use these as inputs to the work, checking their current state during the relevant phase:

- [mod-overview.md](mod-overview.md) — mission, pillars, scope, system map, and current open design questions.
- [minerals-and-refining.md](minerals-and-refining.md) — deposit tiers, recovery candidates, pure-material candidates, and refining route patterns.
- [infrastructure.md](infrastructure.md) — infrastructure inventory, tentative material demands, and category summaries.
- [gap-analysis-report-11-11-26.md](gap-analysis-report-11-11-26.md) — comparative gap hypotheses to verify.
- [chemical-processes.md](chemical-processes.md), [intermediate-products.md](intermediate-products.md), [military-system.md](military-system.md), [power-system.md](power-system.md), [logistics-system.md](logistics-system.md), [research-progression.md](research-progression.md), [endgame-vision.md](endgame-vision.md), and other linked domain documents — consult as the audit reaches each domain.

The document inventory and its references may change during the documentation cleanup. Record those changes in the source-of-truth map rather than silently duplicating or moving design content.

## Phased Work Plan

### Phase 0 — Agree on Documentation and Catalog Conventions

**Objective:** Establish how current design, decision history, and coverage data will be separated and maintained.

**Prerequisites:** None.

**Work:**
- Define the design-document and ADR templates and their respective required content.
- Decide ADR and coverage-ledger locations, naming, and cross-link conventions.
- Define product, constructable, research-ingredient, recipe, entity, machine-family, and tier/variant terminology.
- Define how core, vanilla-reused/replaced, and extension content is identified and counted.
- Identify each design document's owner and scope; avoid multiple current-state sources for the same decision.
- Select one bounded pilot document for the split.

**Outputs:** Agreed documentation conventions, source-of-truth map, taxonomy, and pilot selection.

**Exit criteria:** It is unambiguous where current design, historical decisions, gap evidence, and coverage data belong.

**Phase 0 baseline (2026-11-12):** Conventions and taxonomy are recorded in [documentation-conventions.md](documentation-conventions.md) and [product-taxonomy.md](product-taxonomy.md); ownership is mapped in [documentation-map.md](documentation-map.md). The ADR home is `adrs/` with sequential `ADR-NNNN-short-title.md` names; the coverage ledger will be `product-coverage-ledger.md`, introduced in Phase 4. Reusable templates are in `templates/`.

**Pilot selected:** [map-world-generation.md](map-world-generation.md). It is bounded, has explicit committed/rejected decisions, and is suitable for testing how to separate current design from decision history without changing its content in this phase.

**Checkpoint and gate:** Phase 0 is complete. Begin the pilot only in Phase 1, preserving all source information and recording unresolved provenance rather than guessing. The missing-document references identified in the documentation map must be reconciled during migration, not silently redirected.

### Phase 1 — Pilot and Migrate Documentation

**Objective:** Separate historical decision material from current design without losing context.

**Prerequisites:** Phase 0 conventions approved.

**Work:**
- Convert the selected pilot into a clean current-state design document.
- Extract historical decisions into linked ADRs; preserve dates, rationale, consequences, and supersession relationships where available.
- Keep unresolved questions visible in the current design or a clearly linked decision backlog; do not present proposals as approved.
- Review the pilot for duplicated or conflicting current-state statements.
- Apply the validated method to the other active design documents, prioritizing those needed for the product-tree audit.

**Outputs:** A validated pilot, ADR index, migration map, and cleaned current-state documents for the audit scope.

**Exit criteria:** Current design is distinguishable from proposals and history; the source-of-truth map identifies one owner for each design area; important rationale remains traceable.

**Checkpoint and gate:** Checkpoint the migration map and all unresolved provenance questions. If the pilot causes information loss or ambiguity, revise the conventions before migrating further documents.

### Phase 2 — Verify the Gap Analysis

**Objective:** Determine which reported gaps are real requirements for the intended design.

**Prerequisites:** Phase 1 has produced a trustworthy current-state baseline for the documents being assessed.

**Work:**
- Assess each recommendation in the gap report against the design north star, current scope, and intended player capabilities.
- Classify each as **confirmed gap**, **already covered**, **not a gap**, **conflict**, **optional/extension**, or **needs a decision**.
- For a confirmed gap, state the missing capability or product family, affected progression, evidence, and priority.
- Check proposed item counts and reference-mod comparisons as hypotheses; do not adopt them as targets without a design reason.
- Identify conflicts with existing constraints, including product-count assumptions, the no-voiding principle, and proposed single-use products.

**Outputs:** A prioritized gap ledger with evidence, dispositions, affected documents, and owners.

**Exit criteria:** Every recommendation has a disposition; confirmed gaps and unresolved decisions are clearly separated from speculative additions.

**Checkpoint and gate:** Freeze the gap ledger for infrastructure alignment. A new recommendation discovered later reopens only its affected entry and dependencies.

### Phase 3 — Align Infrastructure and Buildable/Usable Scope

**Objective:** Make the infrastructure inventory consistent with the intended game scope and player-facing progression.

**Prerequisites:** Phases 1 and 2 complete enough to identify current scope and confirmed gaps.

**Work:**
- Normalize the infrastructure list: unique placeable entities, machine families, tiers/variants, support equipment, and recipes are separate counts.
- Include or explicitly exclude vehicles, fuel, weapons, ammunition, armor equipment, utilities, modules, and other non-building outputs.
- For every in-scope constructable, record its role, phase, tier/capability changes, core/extension status, and expected product families.
- Reconcile overlaps, duplicate categories, inconsistent names, and phase or vanilla-replacement assumptions across domain documents.
- Treat the construction-material index as demand hypotheses: every material reference must have an intended capability and a traceable supply path, or be recorded as a gap.
- Keep exact ingredient quantities and final build recipes deferred until the product catalog and recipe phases.

**Outputs:** An aligned constructable inventory, discrepancy list, and verified high-level demand map.

**Exit criteria:** Every intended constructable family and tier is accounted for; scope and counting are clear; tentative or unsupported material demands are identified rather than silently treated as facts.

**Checkpoint and gate:** Review the aligned inventory and unresolved scope choices before using it as a coverage input.

### Phase 4 — Establish Full Coverage Before Enumerating the Catalog

**Objective:** Prove that all required product families and production capabilities are represented, without prematurely filling every item or recipe.

**Prerequisites:** Phases 2 and 3 complete; the source documents for affected domains are available in current-state form.

**Work:**
- Work backward from intended outputs and capabilities: infrastructure, vehicles and fuel, military, armor and modules, logistics, power, research, and endgame.
- Work forward from mineral feeds and vanilla starting resources through refining and chemical/process capabilities.
- Build a coverage matrix connecting each demand area to required product families, upstream material groups, process capabilities, and source documents.
- Mark coverage as present, missing, uncertain, optional, or out of scope.
- Check that confirmed gaps from Phase 2 are represented and that proposed products have a consumer or a justified terminal role.

**Outputs:** A coverage matrix and a list of remaining decisions/blockers, maintained in the agreed canonical ledger.

**Exit criteria:** Every required player capability and progression endpoint has a path to the product families and source capabilities it needs; every confirmed gap has an owner and disposition.

**Checkpoint and gate:** This is the **coverage gate**. Do not begin detailed catalog enumeration until the user accepts the coverage boundary and outstanding decisions are explicit.

### Phase 5 — Complete the Product Catalog

**Objective:** Enumerate the approved products across the complete tree.

**Prerequisites:** Phase 4 coverage gate approved.

**Work:**
- Catalog mined feeds, pure raw/refined materials, chemical products, manufactured intermediates, directly usable products, constructables, and research ingredients.
- For each entry, capture its primary class, source, consumers or terminal role, phase, mandatory/optional status, and relevant capability dependencies.
- Reconcile duplicates and naming across domain documents; distinguish a product from the building or machine that produces it.
- Include vehicles/fuel, weapons/ammo, armor utilities/modules, and research ingredients rather than treating infrastructure as the whole constructable tree.
- Apply performance, learnability, and complexity constraints when deciding whether a candidate merits its own product.

**Outputs:** Complete approved product catalog and unresolved product decisions.

**Exit criteria:** Every mandatory catalog entry has a role, source, and consumer or terminal purpose; no confirmed coverage requirement is left without a product representation.

**Checkpoint and gate:** Freeze the catalog version before assigning detailed recipe quantities. Changes after this gate must identify affected recipes and research.

### Phase 6 — Complete the Recipe Tree

**Objective:** Connect every approved product to its production process.

**Prerequisites:** Phase 5 catalog approved.

**Work:**
- Define inputs, outputs, quantities, machine/process family, phase, prerequisites, and coproducts for each recipe.
- Trace base inputs to mineral feeds or vanilla starting resources.
- Identify alternate routes only where the routes offer meaningful tradeoffs.
- Map each recipe to machine capabilities and flag missing or unjustified machine families.
- Test coproduct destinations, production throttling, and loops for equilibrium without required voiding.

**Outputs:** Recipe tree, machine/process mapping, coproduct map, and balance issues.

**Exit criteria:** Every mandatory product is producible at its intended progression point; every recipe has supported inputs and a compatible process; coproducts have legitimate handling.

**Checkpoint and gate:** Freeze a validated recipe graph before finalizing technology dependencies.

### Phase 7 — Complete the Research Roster

**Objective:** Define the technologies and research ingredients that gate the approved product and recipe graph.

**Prerequisites:** Phases 5 and 6 approved.

**Work:**
- Define conventional, domain, and simulation-gated research items and their production chains.
- Define each technology's phase, prerequisites, research requirements, and explicit unlocks.
- Map vanilla technologies and items as retained, modified, replaced, or extended.
- Check that progression does not require a technology to produce its own required research inputs, and that every important capability has an intentional gate.
- Avoid setting a technology-count target before the roster is derived from required capabilities.

**Outputs:** Research ingredient catalog, technology roster, dependency graph, and vanilla mapping.

**Exit criteria:** Each technology unlocks a defined capability; all required ingredients are producible before use; no required product or capability is left inaccessible.

**Checkpoint and gate:** Freeze the research graph before integrated consistency review.

### Phase 8 — Integrated Consistency Review and Publication

**Objective:** Validate the complete current-state design across documents.

**Prerequisites:** Phases 1-7 complete.

**Work:**
- Check product/source/consumer links, recipe inputs/outputs, machine capability, construction requirements, research gates, phase order, and core/extension boundaries.
- Check names, definitions, counts, links, and claims across domain documents.
- Confirm each design document describes current state and links to ADRs rather than embedding its decision history.
- Move accepted decisions into ADRs and update the owning current-state design document.
- Record deferred items and known limitations explicitly.

**Outputs:** Consistent design-document set, linked ADRs, validated canonical catalog/recipe/research data, and a remaining-work list.

**Exit criteria:** No unresolved blocker breaks a mandatory progression path; remaining uncertainties are explicitly recorded and do not masquerade as settled design.

**Checkpoint and gate:** Publish a dated baseline. Any later change should update the affected ADR (if a decision changes), owning design document, and impacted parts of the product/recipe/research graph.

## Requirement-to-Phase Trace

| Requirement | Primary phases |
|---|---|
| Separate historical ADR material from clean current design | 0-1, verified again in 8 |
| Check the gap analysis against intended complexity and scope | 2 |
| Align infrastructure and all other buildable/usable outputs | 3 |
| Establish complete coverage before detailed lists | 4 |
| Enumerate products from mineral feeds through research ingredients | 5 |
| Define production processes and recipe dependencies | 6 |
| Define research ingredients, technologies, and unlocks | 7 |
| Verify end-to-end consistency and preserve decision history | 8 |

## State Transfer, Checkpoints, and Recovery

Maintain a canonical coverage ledger and decision/ADR index as the work progresses. Each phase checkpoint should record:

- Approved scope, terminology, and counts or counting rules.
- Decisions made, with links to ADRs.
- Current document owners and versions.
- Accepted, rejected, deferred, and unresolved gap entries.
- Coverage or graph entries completed and their dependencies.
- Open blockers and the next phase's entry criteria.

If a gate fails, stop at that boundary, report the specific missing evidence or conflict, and revise only the affected scope. If a later decision changes, reopen the impacted nodes and their upstream/downstream dependencies; do not silently rewrite unrelated phases or erase superseded decisions.
