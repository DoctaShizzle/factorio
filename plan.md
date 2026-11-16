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
- Account for recipe coproducts with a useful consumer, a bounded buffer, production control, or powered, pollution-producing disposal for gas/fluid streams under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md). Free or automatic discarding and permanent accumulation are not acceptable.
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

**Status: Phase 2 is complete; Phase 1 is complete and Phase 3 has not started.**

**Decision source:** Use the owning domain documents identified in [Documentation Map](documentation-map.md) for current design, and the [ADR index](adrs/README.md) for decision history. This plan tracks phase status, dependencies, gates, and safe deferrals rather than restating technical decisions.

**Phase 2 exit disposition:** High-impact decisions are resolved or explicitly bounded by the deferrals below, and the Power System review is complete and aligned. Phase 3 must classify recommendations affected by unresolved scope choices as needing a decision, not assume a candidate is accepted. Phase 5 coverage must demonstrate viable paths for deferred process details before catalog freeze; reopen the affected decision if a selected feed family, access deadline, shared-stage boundary, or first-Core prerequisite cannot be supported.

**Safe deferral — additional starting-area resources:** [Map and World Generation](map-world-generation.md) records the selected CPU, LFP, fission, and bridge-feed access deadlines. The molybdenite, cassiterite, and columbite-tantalite bridge feeds have no starting-region or colocation guarantee under [ADR-0061](adrs/ADR-0061-select-phase-2-molybdenite-rhenium-feed.md) and [ADR-0062](adrs/ADR-0062-select-phase-2-niobium-tin-bridge-feeds.md). Defer any broader starting-area resource package and exact placement/quantities to map validation; preserve all selected access deadlines and do not assume any other feed is guaranteed.

**Safe deferral — exact world-generation distances:** [ADR-0005](adrs/ADR-0005-map-scale-and-discovery-distances.md) selects x5 as the default map scale and retains 5–15 km Phase 2 bridge-material and 20–40 km rare late-game-material distances as untested planning targets; earlier starting-resource, oil/salt, biome-adjacency, and map-edge examples conflict. Defer authoritative ranges and generator feasibility to map validation. The selected feed access deadlines, including [ADR-0061](adrs/ADR-0061-select-phase-2-molybdenite-rhenium-feed.md) and [ADR-0062](adrs/ADR-0062-select-phase-2-niobium-tin-bridge-feeds.md), remain binding; do not treat source distance examples as implementation requirements.

**Safe deferral — detailed monazite recovery:** [ADR-0060](adrs/ADR-0060-select-phase-2-monazite-thorium-feed.md) selects the feed family and access boundary, and [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) selects the separate ThO2-bearing fertile-material architecture. Because this is an optional Phase 2 fission branch rather than a first-Core/CPU prerequisite, defer deposit assignment and access validation to world-generation work. Defer item forms, recovery chemistry, grades, residues, and process balances to detailed product and recipe design after Phase 5 coverage; equipment and research assignments remain for their owning design phases. The Phase 5 coverage gate must still identify a credible route from monazite to the selected fertile material; preserve unlock-level access without a starting-region guarantee, and do not assume Uraninite's thorium secondary or a phosphate deposit is the selected source.

**Safe deferral — detailed PV and LFP production:** [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md) selects a dedicated Phase 2 crystalline-silicon PV route independent of CPU wafer/chip fabrication and post-Core-only capability; [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md) selects LFP chemistry, and [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) selects brine and apatite-rich phosphorite as starting-region feeds, with spodumene as a regional alternative. Defer exact PV grade/process, shared upstream silicon, PV-specific cleanliness and equipment, lithium/phosphate recovery, cell/pack design, capacities, tiers, site design, efficiencies, and research gates to downstream design. Phase 5 coverage must verify viable PV and LFP supply paths before catalog freeze; preserve the selected feeds and access, and do not make cobalt or nickel necessary for initial LFP storage.

**Safe deferral — detailed Zr/Hf separation and cladding processing:** [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) and [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) select zirconium-alloy cladding, shared early/mid-Phase-2 zircon access, and a distinct Zr/Hf separation stage. Keep equipment/entity scope and research gates for their owning design phases; defer feed preparation/conversion, separation chemistry, output forms/grades, alloying/tube forming, and quantities/balances to the relevant process, product, and recipe work. Phase 5 coverage must verify viable paths for both CPU hafnium and fission cladding and validate their combined zircon demand; preserve the access timing and do not assume separate end-to-end ore routes. Reopen the stage/feed assumptions before catalog freeze if no viable shared path can be shown.

**Safe deferral — first-Core alignment assembly:** The exact non-semiconductor alignment assembly and source are deferred to Core facility/constructable design in Phase 4; assess its product path in Phase 6 and recipe in Phase 7. This does not block Phase 2 material-trunk decisions because [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) already sets the essential constraint: first-Core alignment must be Phase 2-compatible and must not require semiconductor-grade positioning hardware. Do not treat Invar, tool steel, precision screws, or any other candidate as selected; include the chosen assembly's eventual demand when the Core construction bill of materials is defined.

**Safe deferral — useful sodium-hydroxide consumer:** The Phase 2 HCl startup/makeup route is selected under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md), and surplus NaOH may be disposed under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md). A separate useful NaOH consumer is not required for the initial CPU chain; evaluate an optional Bayer/alumina or other use when those routes are balanced, and account for the disposal power and pollution if surplus is released.

**Safe deferral — first-Core Array and bridge dependencies:** [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md) and [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) select the first-Core gate and six bridge mappings, but leave bridge production routes and the complete Array bill of materials open; [ADR-0037](adrs/ADR-0037-defer-array-neutron-reference-material.md) defers the neutron-reference material. Defer the Array construction list to Phase 4 and its product/recipe details to Phases 6-7; settle whether domain packs are physical Array inputs in the owning research/constructable design rather than assuming they are. Phase 5 coverage must demonstrate an acyclic capability-level path from conventional starting capabilities through all six domain facilities and T2b2 packs, the mandatory bridges, CPU, and selected Array inputs. The bridge must be available by its first facility use and T2a stage, and no facility may require its own unavailable packs to bootstrap. Phase 8 must verify the concrete technology graph, including cross-domain cycles. Do not require a fission-fuel cycle or rely on capabilities unlocked only after Core Level 1; conventional CPU-grade processors and contemporary cleanroom production remain available pre-Core in Phase 2 under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) and [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md). Do not promote candidate materials or feeds to requirements without a demonstrated path.

**Rhenium bridge boundary:** [ADR-0061](adrs/ADR-0061-select-phase-2-molybdenite-rhenium-feed.md) selects rhenium-bearing molybdenite and requires access by the bridge's first required use, without a starting-region guarantee or a dependency on the Reaction Dynamics Facility, its own packs, or the first Core. Phase 5 must verify a viable recovery path and coproduct handling; detailed chemistry, quantities, placement, equipment, and gates remain with their owning work.

**Niobium-tin bridge boundary:** [ADR-0062](adrs/ADR-0062-select-phase-2-niobium-tin-bridge-feeds.md) selects niobium from the shared columbite-tantalite feed and tin from cassiterite, with both accessible by the wire's first required use. Neither a starting-region guarantee nor colocation is required. Phase 5 must verify viable recovery and wire paths, shared-feed demand, and acyclic progression; detailed processing, quantities, placement, equipment, and gates remain open.

**Objective:** Identify and resolve the open decisions that would otherwise materially skew gap assessment, scope, or the later product, recipe, constructable, and research lists.

**Prerequisites:** Phase 1 is complete. Use the migrated current-state documents and their linked ADRs as the baseline.

**Work:**
- Inventory open decisions, ambiguities, and conflicts across the domain documents and linked ADRs. For each, record its owner, evidence, and impact on products, recipes, constructables, or research.
- Prioritize decisions by downstream impact and dependency; distinguish decisions required before proceeding from those that can safely remain open.
- Resolve bounded decisions under the user's delegated direction and surface major unresolved paths. Record accepted, rejected, or superseded decisions in ADRs and update the owning current-state documents; do not infer approval from a proposal.
- Align [Power System](power-system.md) with related domain documents and accepted decisions. The selected route identities and non-steam converter families are recorded in ADR-0018; maintain that direction while keeping unapproved implementation details, constructables, and gates open.
- Carry forward the selected minimum of three distinct power options in each of Phases 3 and 4, including Phase 3 concentrated solar, and track their unresolved construction dependencies and research gates without reopening the accepted route identities.
- For decisions deferred beyond this phase, state why deferral is safe, what later phase or evidence will resolve them, and which assumptions must not be made meanwhile.

**Outputs:** A prioritized disposition of high-impact open decisions; updated ADRs and owning design documents for decisions made; and explicit constraints, blockers, and safe deferrals for the next phases.

**Exit criteria:** Every open decision with material downstream impact has a recorded decision or an explicit, justified deferral. Decisions needed to assess gaps and establish scope are resolved or bounded. The Power System review is complete and aligned with related documents.

**Checkpoint and gate:** Record the decisions, affected documents, remaining blockers, and constraints for Phase 3. Do not treat unresolved, high-impact choices as settled while reviewing the gap analysis.

**Safe deferral — uranium-fuel enrichment target:** Keep the Phase 2 uranium route at the qualitative enriched-UO2 level. Defer the numeric target until detailed recipe and material/power-balance design under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md); treat 3%–5% U-235 as background only. Select the target before approving detailed enrichment/fuel recipe quantities or final balances. This deferral does not waive the Phase 2 depleted-UF6 handling capability required under [ADR-0052](adrs/ADR-0052-require-phase-2-depleted-uf6-tails-handling.md); deconversion to uranium oxide and HF is selected under [ADR-0053](adrs/ADR-0053-select-depleted-uf6-deconversion.md); uranium oxide recovery for later uranium use and HF reuse in UF6 conversion are selected under [ADR-0054](adrs/ADR-0054-select-depleted-uf6-output-fates.md); exact forms and process integration remain open. The thorium seed uses the same qualitative grade under [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), so the eventual numeric target applies to both routes; no separate seed-specific target is implied.

**Safe deferral — spent-uranium-fuel reprocessing details:** The Phase 2 post-discharge reprocessing/recovery branch is required under [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md); do not defer or omit that capability. Defer the recovered streams and fates, residual-waste handling, process chemistry, storage/containment, equipment, balances, and research gate until detailed fuel-cycle design, where they can be resolved together. This deferral is safe at the current decision stage because it does not treat spent fuel as disposal-only or count any recovered material as supply; resolve the details before finalizing the Phase 2 fuel-cycle product and recipe design. Do not infer plutonium recovery or a military-ammunition link. This branch is separate from depleted-UF6 tails handling under ADR-0052 through ADR-0054 and the thorium U-233 cycle under ADR-0023 and ADR-0055.

**Phase 2 thorium feed status:** Monazite is the selected Th-232 feed family under [ADR-0060](adrs/ADR-0060-select-phase-2-monazite-thorium-feed.md), with limited supply accessible by the thorium power-route unlock and no starting-region guarantee. The source/access boundary is established; detailed recovery and deposit implementation are deferred as specified below. First-Core prerequisites are unchanged.

**Safe deferral — selected CPU and fission trunk process details:** The high-level feed families, route sequences, access boundaries, and required rod assembly are selected in [Minerals and Refining](minerals-and-refining.md), [Chemical Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), and [Power System](power-system.md). Defer quartz preparation/reductant balance, HCl startup buffer and loss rates, uranium/fluorspar recovery and reagent preparation, detailed UF6/UO2 conversion, exact oxide/HF forms and conditioning, thorium seed identity/isotope composition/quantity/preparation, breeding and waste balances, fuel-pellet/rod fabrication details, and exact recipe balances to Phases 5-7. Phase 5 must verify plausible source-to-capability paths before catalog freeze; Phase 4 assigns equipment and Phase 8 assigns research gates. Keep the uranium enrichment target, spent-uranium recovery, monazite recovery, and Zr/Hf/cladding details under their specific deferrals above. This does not select new feeds, product forms, or waste uses; reopen a route decision if coverage cannot demonstrate a viable path. Any newly identified requirement that changes a selected feed family, access deadline, shared-stage requirement, or first-Core prerequisite remains a Phase 2 blocker and must be decided or separately deferred before the exit gate.

**Safe deferral — power implementation details:** The Phase 1-4 route and converter identities are selected under [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) and [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md). Defer exact constructables, heat/coolant transfer, working fluids and thermal-storage materials, normal controls and monitoring, capacity/efficiency balances, powered-disposal implementation and its exact power/pollution values, and research gates to Phases 4, 7, and 8. Phase 5 coverage must retain all selected route capabilities and verify phase-compatible construction and fuel paths for Phase 2 fission and the Phase 3 Tokamak; later-phase candidate equipment must not silently gate these earlier routes. A modeled gas/fluid coproduct needs viable handling when first produced without permanent accumulation; any disposal must consume power and produce pollution, and the gas flare must be available no later than silicon reduction under ADR-0035. Preserve the minimum of three distinct options in Phases 3 and 4, native-grid feedback without custom Core diagnostics under [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md), and the exclusion of blackout-induced meltdown gameplay under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md); do not reopen selected route identities without a concrete conflict.

**Safe deferral — post-activation Core upgrades and gates:** The first-Core gate remains as selected in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md). Defer Core Level 2/3 gates to Phase 8 research design and Josephson/SFQ upgrade products, recipes, and gates to Phases 6-8; these are post-activation capabilities, not first-Core or Phase 2 trunk prerequisites under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md). Phase 5 should represent their capability coverage without inventing exact products or thresholds. Do not feed upgrade materials back into the first-Core bill of materials or change the accepted gate without a demonstrated pre-Core path and an explicit decision.

**Safe deferral — military scope and pressure:** [Military System](military-system.md) owns the unresolved enemy/pressure conflict and bounded turret roster; [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) and [ADR-0013](adrs/ADR-0013-military-pressure-model.md) remain proposed. Phase 3 can classify affected gaps as needing a decision without choosing a roster; resolve core/extension and vanilla-enemy/variant scope before closing Phase 4, then trace selected defense capabilities and sustained power in Phase 5. Ammo identities and count conflicts, recipes, power values, and research gates belong to Phases 6–8. Preserve capability-based ammunition and sustained defense power under [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md) and [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md); military drones remain rejected under [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md). Do not assume the proposed nuclear-ammunition chain or a second victory condition is required.

**Safe deferral — transport and machine-family scope:** [Logistics System](logistics-system.md) owns transport behavior and [Infrastructure](infrastructure.md) owns placeable families. Phase 3 can mark dependent gaps as needing a decision; before closing Phase 4, classify powered rails, vanilla train treatment, dispatch, and family-specific tiers as core, vanilla retained/modified/replaced, extension, or out of scope. Phase 5 must trace selected capabilities and resource access; exact recipes and research gates follow in Phases 7–8. Do not require unapproved powered rails, external dispatch, or custom voltage/loss mechanics for a mandatory pre-Core path, and do not assume every machine family is tiered.

**Safe deferral — technical packaging and game version:** [Technical Architecture](technical-architecture.md) owns packaging, dependency, and feasibility choices. Version-dependent gap claims can remain unresolved during Phase 3, but select the target Factorio version and any required DLC before closing Phase 4's vanilla-scope classification and beginning Phase 5's version-specific coverage. Packaging and third-party dependencies can wait until implementation planning; no mandatory core path may depend on an unapproved extension or external mod. Treat performance estimates as hypotheses until benchmarked.

**Safe deferral — endgame endpoints:** [Endgame Vision](endgame-vision.md) owns the unresolved milestone and victory-versus-sandbox direction. Phase 3 can mark dependent recommendations as needing a decision; determine required versus optional endpoint capabilities before the Phase 5 coverage gate, without adopting candidate facility inputs or a second victory by assumption. Later Core-level gates belong to Phase 8; presentation and balance can follow once endpoint scope is known. The selected first-Core gate and pre-Core CPU/Array constraints do not change.

### Phase 3 — Verify the Gap Analysis

**Objective:** Determine which reported gaps are real requirements for the intended design.

**Prerequisites:** Phase 1 has produced a trustworthy current-state baseline, and Phase 2 has resolved or bounded the high-impact decisions needed for gap assessment.

**Work:**
- Assess each recommendation in the gap report against the design north star, current scope, and intended player capabilities.
- Classify each as **confirmed gap**, **already covered**, **not a gap**, **conflict**, **optional/extension**, or **needs a decision**.
- For a confirmed gap, state the missing capability or product family, affected progression, evidence, and priority.
- Check proposed item counts and reference-mod comparisons as hypotheses; do not adopt them as targets without a design reason.
- Identify conflicts with existing constraints, including product-count assumptions, the powered and pollution-producing gas/fluid disposal policy, and proposed single-use products.

**Outputs:** A prioritized gap ledger with evidence, dispositions, affected documents, and owners.

**Exit criteria:** Every recommendation has a disposition; confirmed gaps and unresolved decisions are clearly separated from speculative additions.

**Checkpoint and gate:** Freeze the gap ledger for infrastructure alignment. A new recommendation discovered later reopens only its affected entry and dependencies.

### Phase 4 — Align Infrastructure and Buildable/Usable Scope

**Objective:** Make the infrastructure inventory consistent with the intended game scope and player-facing progression.

**Prerequisites:** Phases 1-3 are complete enough to identify current scope, confirmed gaps, and decision constraints.

**Work:**
- Select the target Factorio version and any required DLC before finalizing version-dependent vanilla scope.
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
- Demonstrate an acyclic capability-level path to all six pre-Core T2b2 domain tiers, the bridge facilities, conventional CPU, and Array; check selected access deadlines, coproduct handling, viable Phase 2 fission and PV/LFP paths, and phase-compatible Phase 3 Tokamak construction and fuel. Validate the concrete technology graph in Phase 8.
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
- Test coproduct destinations, production throttling, and loops for equilibrium, accounting for power and pollution from any gas/fluid disposal.

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
- Check that progression does not require a technology or domain facility to produce its own required inputs, that cross-domain dependencies do not form cycles, and that every important capability has an intentional gate.
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
