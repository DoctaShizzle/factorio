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
- Other Factorio-style families, including logistics/control items, maintenance consumables, terrain products, biological/agricultural products, and launch/space outputs, must be explicitly classified as in scope, cross-referenced, vanilla retained/modified/replaced, extension, unresolved, or out of scope.

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

**Phase 0 baseline (2026-11-12):** Conventions and taxonomy are recorded in [documentation-conventions.md](documentation-conventions.md) and [product-taxonomy.md](product-taxonomy.md); ownership is mapped in [documentation-map.md](documentation-map.md). The ADR home is `adrs/` with sequential `ADR-NNNN-short-title.md` names; the coverage ledger will be `product-coverage-ledger.md`, introduced in Phase 5. Reusable templates are in `templates/`.

**Pilot selected:** [map-world-generation.md](map-world-generation.md). It is bounded, has explicit committed/rejected decisions, and is suitable for testing how to separate current design from decision history without changing its content in this phase.

**Checkpoint and gate:** Phase 0 is complete. Begin the pilot only in Phase 1, preserving all source information and recording unresolved provenance rather than guessing. The missing-document references identified in the documentation map must be reconciled during migration, not silently redirected.

### Phase 1 — Pilot and Migrate Documentation

**Status: Complete (2026-11-12).**

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

**Pilot checkpoint (2026-11-12):** The user accepted the world-generation split as the migration pattern. It consists of a current-state design, five linked ADRs, an updated ADR index, and a [migration map](migration-map.md). Conflicting distance targets and missing cross-reference files are recorded, not silently resolved. Repository-level rules are in [AGENTS.md](AGENTS.md); migrate the remaining design docs in the manifest's bounded batches.

**Product-tree batch and scope update (2026-11-12):** The mineral/refining, chemical-process, and intermediate-product documents retain their candidate inventories and current-state boundaries. The non-building product catalog now includes a Factorio-style family checklist, with category scope recorded in [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md). The rhenium selection and capability-based catalog-size decision remain in [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md) and [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md). Candidate endgame facility pathways moved to [Infrastructure](infrastructure.md), while former Phase A2 quantities and assembly proposals are preserved as unapproved history in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md). The five-versus-six research-prerequisite count remains open; Phase 1 is still active and Phase 2 must not start before its migration gate is met.

**Infrastructure and systems batch (2026-11-12):** [Infrastructure](infrastructure.md), [Power System](power-system.md), [Logistics System](logistics-system.md), and [Military System](military-system.md) now distinguish candidate design from history. Source-recorded power and military decisions are traceable to proposed [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) through [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md); no unverified proposal was promoted to approved design. The powered-rail/core-power dependency, Phase 4 boundary, generator-phase mismatch, diagnostics/stabilization scope conflict, military count conflicts, and vanilla-enemy/armored-variant conflict remain visible. The former Machine Systems document was subsumed into Infrastructure; exact route-to-machine assignments remain deferred. These four manifest entries are migrated, but Phase 1 remains active until the remaining manifest documents and navigation reconciliation pass the gate.

**Power and military decision reconciliation (2026-11-12):** The user accepted [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) (retain the vanilla grid and add tiered poles), [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md) (Hawking Radiation Engine as one Phase 4 option, with at least one alternative Phase 3/4 route still required), [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md) (capability-based ammo progression), and [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md) (sustained defense power). The user rejected military drones in [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md), specifying fixed defenses and optional spider-bot/power-suit additions for an advanced military extension. [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) remains proposed, with a bounded, layer-based focus on power-based turret options. Exact pole tiers, power alternatives and gates, turret roster and loads, ammunition counts, and extension scope remain open. The affected current-state documents and ADR index have been aligned; Phase 1 remains active and Phase 2 must not start before its migration gate is met.

**Completion checkpoint (2026-11-12):** The user accepted the world-generation pilot. All Phase 1 manifest documents now have a traceable current-state destination or an explicit missing-source disposition; unapproved proposals, estimates, and internal conflicts are labeled and linked to their owners. The accepted power and military decisions remain traceable to their ADRs. The user confirmed that Machine Systems was subsumed into Infrastructure; the `session-plan.md` and `mineral-catalog.md` references were resolved without inventing missing content. README and source-of-truth navigation were reconciled. Local Markdown links/anchors, changed table shapes, and `git diff --check` pass. Phase 1 is complete; Phase 2 can begin under its own entry criteria.

### Phase 2 — Review and Resolve High-Impact Cross-Domain Decisions

**Status: In progress. Phase 1 is complete; the Phase 2 cross-domain review and Power System review are underway.**

**Current decision checkpoint (2026-11-12):** The user selected all six domains at T2b2 plus the Unified Metrology Reference Array (convergence item) for first Core construction, and six Phase 2 bridge products including the accepted rhenium selection; see [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md). Phase 3/4 power-route identities and non-steam converter families are selected in [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md); the Core Level 2 gate, detailed bridge mapping, and power implementation gates remain open.

**Objective:** Identify and resolve the open decisions that would otherwise materially skew gap assessment, scope, or the later product, recipe, constructable, and research lists.

**Prerequisites:** Phase 1 is complete. Use the migrated current-state documents and their linked ADRs as the baseline.

**Work:**
- Inventory open decisions, ambiguities, and conflicts across the domain documents and linked ADRs. For each, record its owner, evidence, and impact on products, recipes, constructables, or research.
- Prioritize decisions by downstream impact and dependency; distinguish decisions required before proceeding from those that can safely remain open.
- Review required decisions with the user. Record accepted, rejected, or superseded decisions in ADRs and update the owning current-state documents; do not infer approval from a proposal.
- Review and align [Power System](power-system.md) with related domain documents and accepted power decisions, using the user's detailed prompt. Record the selected route identities and converter families; keep unapproved implementation details proposed and do not infer acceptance of recipes, constructables, or gates.
- Document the selected minimum of three distinct power options in each of Phases 3 and 4, including the additional Phase 3 concentrated-solar route. Resolve or explicitly defer their construction dependencies and research gates before later catalog work.
- For decisions deferred beyond this phase, state why deferral is safe, what later phase or evidence will resolve them, and which assumptions must not be made meanwhile.

**Outputs:** A prioritized disposition of high-impact open decisions; updated ADRs and owning design documents for decisions made; and explicit constraints, blockers, and safe deferrals for the next phases.

**Exit criteria:** Every open decision with material downstream impact has a recorded decision or an explicit, justified deferral. Decisions needed to assess gaps and establish scope are resolved or bounded. The Power System review is complete and aligned with related documents.

**Checkpoint and gate:** Record the decisions, affected documents, remaining blockers, and constraints for Phase 3. Do not treat unresolved, high-impact choices as settled while reviewing the gap analysis.

### Phase 3 — Verify the Gap Analysis

**Objective:** Determine which reported gaps are real requirements for the intended design.

**Prerequisites:** Phase 1 has produced a trustworthy current-state baseline, and Phase 2 has resolved or bounded the high-impact decisions needed for gap assessment.

**Work:**
- Assess each recommendation in the gap report against the design north star, current scope, and intended player capabilities.
- Classify each as **confirmed gap**, **already covered**, **not a gap**, **conflict**, **optional/extension**, or **needs a decision**.
- For a confirmed gap, state the missing capability or product family, affected progression, evidence, and priority.
- Check proposed item counts and reference-mod comparisons as hypotheses; do not adopt them as targets without a design reason.
- Identify conflicts with existing constraints, including product-count assumptions, the no-voiding principle, and proposed single-use products.

**Outputs:** A prioritized gap ledger with evidence, dispositions, affected documents, and owners.

**Exit criteria:** Every recommendation has a disposition; confirmed gaps and unresolved decisions are clearly separated from speculative additions.

**Checkpoint and gate:** Freeze the gap ledger for infrastructure alignment. A new recommendation discovered later reopens only its affected entry and dependencies.

### Phase 4 — Align Infrastructure and Buildable/Usable Scope

**Objective:** Make the infrastructure inventory consistent with the intended game scope and player-facing progression.

**Prerequisites:** Phases 1-3 are complete enough to identify current scope, confirmed gaps, and decision constraints.

**Work:**
- Normalize the infrastructure list: unique placeable entities, machine families, tiers/variants, support equipment, and recipes are separate counts.
- Use the Factorio-style infrastructure-family checklist in [Infrastructure](infrastructure.md) to verify placeable families and record an explicit scope disposition for each.
- Include or explicitly exclude vehicles, fuel, weapons, ammunition, armor equipment, utilities, modules, and other non-building outputs.
- For every in-scope constructable, record its role, phase, tier/capability changes, core/extension status, and expected product families.
- Include the accepted tiered power-pole family in the constructable inventory; keep its tier count, statistics, materials, and phase gates open until designed.
- Carry the Phase 2 power decisions and any explicit deferrals into the constructable inventory; represent the accepted Hawking option and any approved alternative route(s) consistently without silently reopening settled decisions.
- Reconcile overlaps, duplicate categories, inconsistent names, and phase or vanilla-replacement assumptions across domain documents.
- Treat the construction-material index as demand hypotheses: every material reference must have an intended capability and a traceable supply path, or be recorded as a gap.
- Keep exact ingredient quantities and final build recipes deferred until the product catalog and recipe phases.

**Outputs:** An aligned constructable inventory, discrepancy list, and verified high-level demand map.

**Exit criteria:** Every intended constructable family and tier is accounted for; scope and counting are clear; tentative or unsupported material demands are identified rather than silently treated as facts.

**Checkpoint and gate:** Review the aligned inventory and unresolved scope choices before using it as a coverage input.

### Phase 5 — Establish Full Coverage Before Enumerating the Catalog

**Objective:** Prove that all required product families and production capabilities are represented, without prematurely filling every item or recipe.

**Prerequisites:** Phases 2-4 complete; the source documents for affected domains are available in current-state form.

**Work:**
- Begin with the Factorio-style product-family checklist in [Intermediate Products](intermediate-products.md) and cross-check the infrastructure-family checklist in [Infrastructure](infrastructure.md). Verify relevant families against the selected game version and give each an explicit scope disposition; category presence alone does not require adding products.
- Work backward from intended outputs and capabilities: infrastructure, vehicles and fuel, military, armor and modules, logistics, power, research, and endgame.
- Work forward from mineral feeds and vanilla starting resources through refining and chemical/process capabilities.
- Build a coverage matrix connecting each demand area to required product families, upstream material groups, process capabilities, and source documents.
- Mark coverage as present, missing, uncertain, optional, or out of scope.
- Check that confirmed gaps from Phase 3 are represented and that proposed products have a consumer or a justified terminal role.

**Outputs:** A coverage matrix and a list of remaining decisions/blockers, maintained in the agreed canonical ledger; the product-family and infrastructure-family checklists have dispositions for every category.

**Exit criteria:** Every required player capability and progression endpoint has a path to the product families and source capabilities it needs; every confirmed gap has an owner and disposition.

**Checkpoint and gate:** This is the **coverage gate**. Do not begin detailed catalog enumeration until the user accepts the coverage boundary and outstanding decisions are explicit.

### Phase 6 — Complete the Product Catalog

**Objective:** Enumerate the approved products across the complete tree.

**Prerequisites:** Phase 5 coverage gate approved.

**Work:**
- Catalog mined feeds, pure raw/refined materials, chemical products, manufactured intermediates, directly usable products, constructables, and research ingredients.
- For each entry, capture its primary class, source, consumers or terminal role, phase, mandatory/optional status, and relevant capability dependencies.
- Reconcile duplicates and naming across domain documents; distinguish a product from the building or machine that produces it.
- Include vehicles/fuel, weapons/ammo, armor utilities/modules, and research ingredients rather than treating infrastructure as the whole constructable tree.
- Apply performance, learnability, and complexity constraints when deciding whether a candidate merits its own product.

**Outputs:** Complete approved product catalog and unresolved product decisions.

**Exit criteria:** Every mandatory catalog entry has a role, source, and consumer or terminal purpose; no confirmed coverage requirement is left without a product representation.

**Checkpoint and gate:** Freeze the catalog version before assigning detailed recipe quantities. Changes after this gate must identify affected recipes and research.

### Phase 7 — Complete the Recipe Tree

**Objective:** Connect every approved product to its production process.

**Prerequisites:** Phase 6 catalog approved.

**Work:**
- Define inputs, outputs, quantities, machine/process family, phase, prerequisites, and coproducts for each recipe.
- Trace base inputs to mineral feeds or vanilla starting resources.
- Identify alternate routes only where the routes offer meaningful tradeoffs.
- Map each recipe to machine capabilities and flag missing or unjustified machine families.
- Test coproduct destinations, production throttling, and loops for equilibrium without required voiding.

**Outputs:** Recipe tree, machine/process mapping, coproduct map, and balance issues.

**Exit criteria:** Every mandatory product is producible at its intended progression point; every recipe has supported inputs and a compatible process; coproducts have legitimate handling.

**Checkpoint and gate:** Freeze a validated recipe graph before finalizing technology dependencies.

### Phase 8 — Complete the Research Roster

**Objective:** Define the technologies and research ingredients that gate the approved product and recipe graph.

**Prerequisites:** Phases 6 and 7 approved.

**Work:**
- Define conventional, domain, and simulation-gated research items and their production chains.
- Define each technology's phase, prerequisites, research requirements, and explicit unlocks.
- Map vanilla technologies and items as retained, modified, replaced, or extended.
- Check that progression does not require a technology to produce its own required research inputs, and that every important capability has an intentional gate.
- Avoid setting a technology-count target before the roster is derived from required capabilities.

**Outputs:** Research ingredient catalog, technology roster, dependency graph, and vanilla mapping.

**Exit criteria:** Each technology unlocks a defined capability; all required ingredients are producible before use; no required product or capability is left inaccessible.

**Checkpoint and gate:** Freeze the research graph before integrated consistency review.

### Phase 9 — Integrated Consistency Review and Publication

**Objective:** Validate the complete current-state design across documents.

**Prerequisites:** Phases 1-8 complete.

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
| Separate historical ADR material from clean current design | 0-1, verified again in 9 |
| Review and resolve high-impact cross-domain decisions, including Power System alignment | 2 |
| Check the gap analysis against intended complexity and scope | 3 |
| Align infrastructure and all other buildable/usable outputs | 4 |
| Establish complete coverage before detailed lists | 5 |
| Enumerate products from mineral feeds through research ingredients | 6 |
| Define production processes and recipe dependencies | 7 |
| Define research ingredients, technologies, and unlocks | 8 |
| Verify end-to-end consistency and preserve decision history | 9 |

## State Transfer, Checkpoints, and Recovery

Maintain a canonical coverage ledger and decision/ADR index as the work progresses. Each phase checkpoint should record:

- Approved scope, terminology, and counts or counting rules.
- Decisions made, with links to ADRs.
- Current document owners and versions.
- Accepted, rejected, deferred, and unresolved gap entries.
- Coverage or graph entries completed and their dependencies.
- Open blockers and the next phase's entry criteria.

If a gate fails, stop at that boundary, report the specific missing evidence or conflict, and revise only the affected scope. If a later decision changes, reopen the impacted nodes and their upstream/downstream dependencies; do not silently rewrite unrelated phases or erase superseded decisions.
