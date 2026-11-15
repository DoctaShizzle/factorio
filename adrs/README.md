# Architecture Decision Records

ADRs preserve significant decision history separately from current-state design documents. Current design lives in the owning domain document listed in [documentation-map.md](../documentation-map.md).

## Naming and status

- Name files `ADR-NNNN-short-title.md`, assigning the next unused sequential number.
- Never reuse an ADR number. Keep superseded records and link them to their replacements.
- Use the structure in [the ADR template](../templates/adr.md).
- Preserve known historical dates; state `Unknown` if the date cannot be established.

## Index

| ADR | Decision | Status |
|---|---|---|
| [ADR-0001](ADR-0001-geological-biome-layout.md) | Geological Biome Layout | Accepted |
| [ADR-0002](ADR-0002-geology-led-exploration.md) | Geology-Led Exploration | Accepted |
| [ADR-0003](ADR-0003-single-oil-type.md) | Use a Single Oil Type | Accepted; light/heavy variation rejected |
| [ADR-0004](ADR-0004-map-edge-pressure.md) | Sparse Military Patrols at the Map Edge | Accepted |
| [ADR-0005](ADR-0005-map-scale-and-discovery-distances.md) | Default Map Scale and Discovery Distances | Accepted with distance validation outstanding |
| [ADR-0006](ADR-0006-capability-based-intermediate-scope.md) | Scope Intermediate Products by Capability | Accepted |
| [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md) | Rhenium Catalyst as a Reaction Dynamics Bridge | Accepted; six-bridge count and facility mapping selected; route validation outstanding |
| [ADR-0008](ADR-0008-factorio-product-family-coverage.md) | Map Factorio Product Families Before Cataloging | Accepted; item-level coverage and version-specific inventory deferred |
| [ADR-0009](ADR-0009-endgame-assembly-proposals.md) | Preserve Former Phase A2 Endgame Assembly Proposals | Accepted as a historical record; recipe values remain unapproved |
| [ADR-0010](ADR-0010-core-power-distribution-scope.md) | Retain the Vanilla Grid with Tiered Power Poles | Accepted; exact tiers and pole properties open |
| [ADR-0011](ADR-0011-hawking-radiation-endgame-generator.md) | Add a Hawking Radiation Engine as a Phase 4 Power Option | Accepted option; at least one alternative Phase 3/4 route required |
| [ADR-0012](ADR-0012-bound-core-military-scope.md) | Bound Core Military Scope to Industrial Defense | Proposed; bounded, layer-based electrical direction; roster and scope open |
| [ADR-0013](ADR-0013-military-pressure-model.md) | Use Pollution and Space as Complementary Military Pressures | Proposed; model and thresholds require validation |
| [ADR-0014](ADR-0014-capability-based-ammunition.md) | Use Capability-Based Ammunition Progression | Accepted principle; types, tiers, and recipe counts open |
| [ADR-0015](ADR-0015-sustained-power-for-defense.md) | Give Defense Infrastructure a Sustained Power Load | Accepted principle; profiles and values require validation |
| [ADR-0016](ADR-0016-late-game-defense-drones.md) | Reject Late-Game Military Drones | Rejected; fixed defense, with optional spider-bot/power-suit extension scope open |
| [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md) | Set Phase 2 Core and Bridge Prerequisites | Accepted |
| [ADR-0018](ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) | Select Phase 3/4 Power Routes and Non-Steam Conversion | Accepted; implementation details and progression gates open |
| [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) | Set Phase 1/2 Power Progression | Accepted; exact fuel processing, storage progression, and balance remain open |
| [ADR-0020](ADR-0020-seven-distinct-domain-pack-tiers.md) | Use Seven Distinct Domain-Pack Tiers | Accepted; exact pack content and higher Core gates open |
| [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md) | Set Phase 2 Material and Solar Boundaries | Accepted; exact solar route and material recipes open |
| [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) | Finalize Phase 2 Bridge Mappings and Core Dependencies | Accepted; semiconductor timing partially superseded by ADR-0025 |
| [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) | Set the Thorium Startup-Seed and Breeding Model | Accepted; seed uses the shared uranium chain under ADR-0047; solid-oxide seed-and-blanket architecture selected under ADR-0055; exact seed details, breeding/reprocessing balance, and waste handling remain open |
| [ADR-0024](ADR-0024-include-chemical-process-concepts-in-core-scope.md) | Include Current Chemical-Process Concepts in Core Scope | Accepted; product and reaction validation remains open |
| [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) | Set Phase 2 CPU Availability and Superconducting Core Compute Progression | Accepted; manufacturing routes, stages, and upgrade gate remain open |
| [ADR-0026](ADR-0026-phase-2-contemporary-semiconductor-capability.md) | Place Contemporary Cleanroom and Advanced Chipmaking in Phase 2 | Accepted; material routes, equipment tiers, and research gates remain open |
| [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) | Require a Contemporary Semiconductor Material Stack in Phase 2 | Accepted; source routes, grades, and recipes remain open |
| [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md) | Require the Material Stack in the Initial Core CPU Path | Accepted; exact products, routes, grades, and gates remain open |
| [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) | Assign Phase 2 Mineral Feed Families for the Core CPU Chain | Accepted; extraction/refining routes, grades, yields, and access timing remain open |
| [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) | Require Limited Early Access to Semiconductor Feed Deposits | Accepted; quantities, placement, distances, and yields remain open |
| [ADR-0031](ADR-0031-starting-region-access-to-cpu-feed-families.md) | Require Starting-Region Access to Quartz and Copper Feeds | Accepted; exact copper source, quantities, placement, and routes remain open |
| [ADR-0032](ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md) | Select the Trichlorosilane Route for Phase 2 Polysilicon | Accepted; upstream silicon and HCl source selected in ADR-0033/0034; purity targets, yields, and detailed values remain open |
| [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md) | Select Carbothermic Quartz Reduction in a Phase 2 Submerged-Arc Furnace | Accepted; preparation, reductant balance, CO disposal recipe, gate, and balance details remain open under ADR-0035 |
| [ADR-0034](ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md) | Select Chlor-Alkali Coproducts for Phase 2 HCl Makeup | Accepted; startup buffer and losses remain open; useful NaOH sink is optional because surplus may be disposed under ADR-0035 |
| [ADR-0035](ADR-0035-powered-polluting-gas-fluid-disposal.md) | Permit Powered, Pollution-Producing Disposal of Gases and Fluids | Accepted; separate gas flare and liquid effluent clarifier selected; recipes, costs, and gates remain open |
| [ADR-0036](ADR-0036-phase-2-minimum-fission-fuel-path.md) | Set the Minimum Phase 2 Fission-Fuel Capability | Superseded by ADR-0043; its original minimum fuel boundary is preserved |
| [ADR-0037](ADR-0037-defer-array-neutron-reference-material.md) | Defer the Array's Neutron-Reference Material Selection | Accepted deferral; exact material and route remain open, must be pre-Core accessible and not require enriched fission fuel |
| [ADR-0038](ADR-0038-select-phase-2-crystalline-silicon-pv.md) | Select Crystalline-Silicon PV for Phase 2 | Accepted; detailed PV-grade supply, cell process, equipment, gates, tiers, and storage remain open |
| [ADR-0039](ADR-0039-phase-2-lfp-battery-storage.md) | Select Phase 2 LFP Battery Storage | Accepted; feed sources and access are set in ADR-0040; full cell/pack routes remain open |
| [ADR-0040](ADR-0040-phase-2-lfp-feed-sources-and-access.md) | Select Phase 2 LFP Feed Sources and Access | Accepted; brine and apatite-rich phosphorite are starting-area sources; recovery routes, spodumene access, and detailed battery routes remain open |
| [ADR-0041](ADR-0041-phase-2-direct-use-fission-fuel.md) | Select Direct-Use Unclad Fuel for Phase 2 Fission | Superseded by ADR-0043; its original unclad-fuel decision is preserved |
| [ADR-0042](ADR-0042-require-enriched-phase-2-uranium-fuel.md) | Require Enriched UO2 for Phase 2 Uranium Fission | Accepted; enriched pellets feed the required Phase 2 rods; centrifuge enrichment selected under ADR-0046; the shared uranium chain supplies the thorium seed under ADR-0047, which uses the same qualitative enrichment grade under ADR-0056; the numeric target deferred under ADR-0051 applies to both; depleted-UF6 deconversion and output fates selected under ADR-0053/0054 |
| [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) | Require Phase 2 Cladding and Fuel-Rod Assembly for Fission | Accepted; both fission routes require Phase 2 rods; thorium oxide seed-and-blanket direction selected under ADR-0055; exact seed/fuel identities, recipes, and gates remain open |
| [ADR-0044](ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) | Extend Shared Phase 2 Zircon Supply to Fission Cladding | Accepted; zirconium-alloy cladding and shared early/mid-Phase-2 zircon access selected; route, quantities, and grades remain open |
| [ADR-0045](ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) | Require a Distinct Phase 2 Zirconium-Hafnium Separation Stage | Accepted; stage boundary selected; chemistry, equipment, products, and balances remain open |
| [ADR-0046](ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) | Select Gas-Centrifuge Enrichment for Phase 2 Uranium Fuel | Accepted; shared uranium-chain supply of the thorium seed is set in ADR-0047; the seed shares uranium fuel's qualitative enrichment grade under ADR-0056; numeric target deferred under ADR-0051; depleted-UF6 deconversion selected under ADR-0053 and output fates under ADR-0054; exact forms, conditioning, conversion details, equipment configuration, balances, seed form, and gates remain open |
| [ADR-0047](ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) | Supply the Thorium Startup Seed from the Shared Uranium Chain | Accepted; solid-oxide seed-and-blanket architecture selected under ADR-0055; the seed uses uranium fuel's qualitative enrichment grade under ADR-0056, with the numeric target deferred under ADR-0051; exact seed composition, quantity, preparation, balances, and gates remain open |
| [ADR-0048](ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) | Select a UF6-Based Phase 2 Uranium Fuel-Cycle Path | Accepted; Uraninite and fluorspar feed/access are set in ADR-0050/0049; numeric enrichment target deferred under ADR-0051; Phase 2 depleted-UF6 handling required under ADR-0052, deconversion selected under ADR-0053, and output fates under ADR-0054; exact forms, conditioning, and detailed chemistry remain open |
| [ADR-0049](ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) | Select Fluorspar as the Phase 2 Fluorine Feed | Accepted; feed and UF6-conversion-unlock access selected; recovery, placement, quantities, and detailed chemistry remain open |
| [ADR-0050](ADR-0050-select-phase-2-uraninite-uranium-feed.md) | Select Uraninite as the Phase 2 Uranium Feed | Accepted; mined feed and UF6-conversion-unlock access selected; recovery, placement, quantities, and thorium coproduct status remain open |
| [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md) | Defer the Phase 2 Uranium-Fuel Enrichment Target | Accepted; keep enriched UO2 qualitative and defer the numeric target until detailed recipe and balance design; 3%–5% remains a reference only; tails handling is required under ADR-0052, deconversion is selected under ADR-0053, and output fates under ADR-0054; the thorium seed shares the qualitative uranium-fuel grade under ADR-0056, and the deferred numeric target applies to both |
| [ADR-0052](ADR-0052-require-phase-2-depleted-uf6-tails-handling.md) | Require Phase 2 Handling for Depleted UF6 Tails | Accepted; Phase 2 tails handling is required; the deconversion route is selected in ADR-0053 and output fates in ADR-0054; exact forms and implementation remain open |
| [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) | Select Deconversion of Depleted UF6 to Uranium Oxide and HF | Accepted; select the high-level deconversion direction; output fates are selected under ADR-0054; exact oxide/HF forms, conditioning, chemistry, facility, balances, and gate remain open |
| [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) | Select Fates for Depleted-UF6 Deconversion Outputs | Accepted; recover uranium oxide for later uranium use and HF for reuse in UF6 conversion; exact forms, conditioning, detailed chemistry, balances, facility, and gate remain open |
| [ADR-0055](ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md) | Select a Phase 2 Thorium Oxide Seed-and-Blanket Architecture | Accepted; separate ThO2-bearing fertile material and uranium-derived startup seed, with bred U-233 returned as oxide fuel rods; same qualitative uranium enrichment grade selected under ADR-0056, while numeric target and exact seed details, routes, balances, waste, and gates remain open |
| [ADR-0056](ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) | Share the Uranium-Fuel Enrichment Grade with the Thorium Startup Seed | Accepted; use one qualitative grade for both routes; the numeric target is deferred under ADR-0051 and exact seed specifications remain open |
| [ADR-0057](ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md) | Require Phase 2 Reprocessing for Spent Uranium Fuel | Accepted; post-discharge reprocessing/recovery is required for spent Phase 2 uranium fuel; recovered streams, fates, residues, process, storage, equipment, balances, and gate remain open; no plutonium or military-ammunition link selected |
| [ADR-0058](ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md) | Keep Custom Power Diagnostics and Stabilization Out of Core | Accepted; use native grid feedback in Core; custom diagnostics and stabilization remain unapproved extension candidates |
| [ADR-0059](ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md) | Exclude Blackout-Meltdown Gameplay from Phase 2 Core Fission | Accepted; retain normal heat transfer but exclude blackout-induced meltdown gameplay and a dedicated safety fuse from Phase 2 Core |
