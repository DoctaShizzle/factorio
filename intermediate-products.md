# Intermediate Products and Non-Building Outputs

*For: Project Prometheus*
*Status: Candidate design; product inventory and pathways provisional*
*Owner: Cross-domain non-building product catalog*
*Last updated: 2026-11-16*

Related documents: [Minerals and Refining](minerals-and-refining.md) for mined feeds and mineral-derived products; [Chemical Products and Processes](chemical-processes.md) for reactions and chemical feeds; [Infrastructure](infrastructure.md) for candidate placeable equipment families and construction hypotheses. Related ADRs: [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md), [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md), [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md), [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md), [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md), [ADR-0024](adrs/ADR-0024-include-chemical-process-concepts-in-core-scope.md), [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md), [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md), [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md), [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md), [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md), [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md), [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md), [ADR-0037](adrs/ADR-0037-defer-array-neutron-reference-material.md), [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md), [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md), [ADR-0041](adrs/ADR-0041-phase-2-direct-use-fission-fuel.md), [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md), [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md), [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md), [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md), [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md), [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md), [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md), [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md), [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md), [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), and [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md). Exact product-to-machine assignments remain open.

Related closure ADRs: [ADR-0063](adrs/ADR-0063-select-depleted-uranium-oxide-reuse.md), [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md), [ADR-0065](adrs/ADR-0065-practical-phase-2-fission-readiness.md), [ADR-0066](adrs/ADR-0066-select-phase-2-nuclear-recovery-flows.md), and [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md).

## Summary

This document is the cross-domain catalog of non-building products downstream of pure/refined materials and chemical processes. Its scope includes materials and components used to construct buildings, vehicles and fuels, weapons and ammunition, armor equipment and modules, research ingredients, and endgame components. Placeable buildings are consumers of products, not catalog entries here.

**What it covers:** Candidate inventories and uses for manufactured materials, components, energy and mobility products, military and personal equipment, research inputs, and endgame components. Detailed product lists, recipes, and progression remain provisional.

**What it does not cover:** Mined feeds and pure/refined materials (see [Minerals and Refining](minerals-and-refining.md)), detailed chemical reactions and process routes (see [Chemical Products and Processes](chemical-processes.md)), or placeable buildings and machine entities (see [Infrastructure](infrastructure.md)).

## Product Scope and Ownership

“Intermediate products” is the project name for this broad non-building product catalog; it is not a claim that every entry is a recipe intermediate. Assign each product the appropriate primary class and secondary-role tags from [Product Taxonomy](product-taxonomy.md). The catalog includes:

- Materials and components consumed when constructing buildings or other constructables; the buildings themselves are excluded.
- Non-building utility outputs, including vehicles and their fuel.
- Weapons, ammunition, armor equipment, armor utilities, and equipment modules.
- Research ingredients and other produced research inputs or results.
- Energy-storage, electronics, nuclear, and endgame products that have a defined role in the tree.

This document owns the product catalog's identities, roles, and consumer links. Specialized design documents remain authoritative for process behavior and domain mechanics:

| Design area | Owning document |
|---|---|
| Mined feeds, recovery, and pure/refined materials | [Minerals and Refining](minerals-and-refining.md) |
| Chemical reactions, reagents, and detailed chemical routes | [Chemical Products and Processes](chemical-processes.md) |
| Placeable buildings, machines, and construction-demand hypotheses | [Infrastructure](infrastructure.md) |
| Military behavior and combat capability; current candidate weapon/ammo chains | [Military System](military-system.md) |
| Power-generation and fuel-system behavior | [Power System](power-system.md) |
| Vehicle and transport behavior | [Logistics System](logistics-system.md) |
| Research mechanics, technology gates, and research progression | [Research and Progression](research-progression.md) |
| Endgame facility concepts and simulation network behavior | [Endgame Vision](endgame-vision.md) |

Product entries are candidates unless explicitly approved. Favor products that unlock a capability or satisfy a distinct demand over near-duplicates; no fixed product-count target is approved. The selected Factorio 2.1 base-game baseline and family-by-family vanilla-overhaul policy are in [ADR-0069](adrs/ADR-0069-target-factorio-2-1-base-game.md) and [ADR-0070](adrs/ADR-0070-overhaul-vanilla-recipes-and-progression.md).

## Factorio Product-Family Coverage Checklist

This family-level scope review uses the Factorio 2.1 base game; it is not an enumerated item catalog. **Core** describes the family or capability, not approval of every listed item. Vanilla entries can be retained or modified without becoming new Prometheus products; the exact recipe and progression of each item remain open.

| Family to verify | Factorio-style examples | Treatment and owner |
|---|---|---|
| Extracted feeds and resource fluids | Ores, stone, crude oil, water | Core; vanilla modified as appropriate. Deposit and feed ownership is [Minerals and Refining](minerals-and-refining.md), with placement in [Map and World Generation](map-world-generation.md). |
| Pure and refined materials | Metals, purified elements, refined minerals | Core; vanilla modified as appropriate. [Minerals and Refining](minerals-and-refining.md) owns upstream materials. |
| Chemical fluids, gases, and reagents | Acids, solvents, catalysts, coproducts | Core process-family scope under [ADR-0024](adrs/ADR-0024-include-chemical-process-concepts-in-core-scope.md); individual products/routes remain provisional in [Chemical Processes](chemical-processes.md). |
| Manufactured materials and components | Alloys, ceramics, glass, circuits, mechanical parts | Core; vanilla components may be modified. This catalog owns non-building products and their uses. |
| Placeable production and utility infrastructure | Machines, power facilities, labs, turrets | Core families are owned by [Infrastructure](infrastructure.md); entities and their placing items are not non-building products in this checklist. Construction inputs remain in scope here. |
| Logistics and automation products | Belts, inserters, pipes, chests, rails, robots, circuit parts | Core; retain/modify useful vanilla families. Separate entity/placing-item identities from non-building components; see [Infrastructure](infrastructure.md) and [Logistics System](logistics-system.md). |
| Vehicles and vehicle equipment | Cars, tanks, locomotives, wagons, spider vehicles | Core retains/modifies ordinary car, tank, and wagon families; electric locomotives replace fueled locomotives under [ADR-0073](adrs/ADR-0073-core-electric-only-rail.md). Base-game Spidertron and further spider-bot vehicles are optional advanced-military extension candidates under [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md); exact vehicle products remain open. |
| Fuels and energy carriers | Burner items, nuclear fuel, vehicle fuels, batteries | Core; vanilla modified as appropriate. Electric trains do not consume fuel items; other burner and vehicle-fuel uses remain. Electricity is a system flow, not an inventory product. |
| Weapons and combat consumables | Guns, ammunition, rockets, grenades, capsules | Core retains/modifies useful base-game weapon and consumable families; exact additions remain open. Vanilla deployable combat-robot capsules are extension candidates, not Core; new patrol/sensor drones remain rejected under [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md). |
| Armor and personal equipment | Armor, shields, batteries, exoskeletons, personal roboports | Core retains/modifies base-game personal equipment; additional advanced power-suit equipment is an extension candidate. Product identities and progression remain open. |
| Upgrade modules and process consumables | Speed/productivity/efficiency modules, catalysts, filters, repair packs | Core retains/modifies base-game upgrade and repair families and includes needed process consumables. Quality modules are not assumed to be base-game content or a Core feature; additional families remain open. |
| Research ingredients and data | Conventional packs, domain packs, datasets, findings | Core; vanilla packs may be modified. [Research and Progression](research-progression.md) owns mechanics and gates; packs are not physical Array construction inputs under [ADR-0077](adrs/ADR-0077-domain-packs-not-array-construction-inputs.md). |
| Endgame computation assemblies and facilities | Compute components, Array, Core structures, observation systems | Core simulation direction and the first-Core Array/CPU/alignment boundaries are selected; item/entity splits and other satellite requirements remain open. Facilities belong to [Infrastructure](infrastructure.md) and [Endgame Vision](endgame-vision.md). |
| Launch and space products | Base-game rocket parts and satellite; stellar collector components | Base-game launch families may be retained/modified; a second victory is not selected. The selected stellar-beaming route needs a DLC-independent implementation; Space Age platforms and their items are not assumed. |
| Biological and agricultural products | Wood, biofeedstocks, nutrients, cultivation | Base-game wood and documented Core bioprocess concepts remain in scope; new agricultural systems, spoilage mechanics, and specific products are not selected merely because a DLC offers them. |
| Terrain and tile products | Landfill, concrete, paths | Core retains/modifies useful base-game terrain items; tile behavior belongs to [Map and World Generation](map-world-generation.md). |
| Tools, containers, and interface items | Repair tools, barrels, blueprints, planners, remotes | Core retains vanilla interface and construction tools and may modify manufactured containers/repair items; non-recipe UI tools are not counted as new products. |
| Byproducts, waste, and recycling streams | Slag, spent fuel, sludge, recovered materials | Core includes required coproduct handling and nuclear recovery/disposal; individual products, routes, and recipe forms remain with their domain owners. |

Phase 5 traces required capability paths and remaining uncertain item-level dispositions; it must not treat a family entry as an approved recipe or a complete list of products. Keep the classes and scope labels in [Product Taxonomy](product-taxonomy.md) separate.

## Product Families and Candidate Inventory

### Construction and Structural Materials

| Product | Candidate inputs / route | Industrial role |
| --- | --- | --- |
| Pig iron | Hematite or magnetite feed, coke, flux; blast furnace | Early ironmaking intermediate for steel |
| Direct-reduced iron (DRI) | Iron oxide feed plus hydrogen reduction | Lower-carbon ironmaking route; feeds steelmaking |
| Carbon steel | Pig iron/DRI and scrap; basic oxygen or electric-arc steelmaking | Main structural metal and factory machinery |
| Stainless steel | Steel plus chromium and nickel | Corrosion-resistant chemical plant, pipe, and reactor equipment |
| Niobium microalloyed steel | Steel plus ferroniobium from columbite-tantalite | High-strength structures and pressure-bearing plant components |
| Tool steel | Steel plus carbon and selected tungsten/vanadium additions | Durable drills, cutters, and machine parts |
| Invar / low-expansion alloy | Iron-nickel alloy; a viable iron/nickel feed and alloy/fabrication path must exist before first Core | Selected material for the mechanical first-Core alignment assembly under [ADR-0076](adrs/ADR-0076-invar-mechanical-first-core-alignment.md); exact grade and product form remain open |
| Titanium alloy | Titanium plus aluminum/vanadium or steel additions | High-strength, corrosion-resistant late-game structures |
| Aluminum alloys | Aluminum plus selected alloying elements | Lightweight structures, heat exchangers, and transport components |

Chromium and niobium have confirmed roles in steelmaking. The gameplay distinction can be capability-based: stainless steel unlocks corrosive service, while niobium microalloyed steel enables high-strength structural parts.

PTFE resin and construction-grade seals/linings have a selected Phase 2 supply role under [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md). First polymerization and basic forming/sintering must work before PTFE-built nuclear/cleanroom equipment, without a PTFE-dependent finishing machine or nuclear HF recovery. Exact catalog forms remain open; chemistry and equipment belong to their owners.

### Mobility, Fuels, and Energy Storage

Vehicles and their fuel products are in scope as non-building outputs. Core electric locomotives use grid-fed powered rail instead of fuel items; wagons and ordinary land-vehicle families remain in scope. Spider-bot vehicles remain optional advanced-military extension candidates. Exact products and sources belong to the later catalog; see [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md) and [ADR-0073](adrs/ADR-0073-core-electric-only-rail.md).

#### Battery Products

The initial Phase 2 grid-storage battery uses LFP (LiFePO4) cathode chemistry under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md). Lithium source alternatives, apatite-rich phosphorite, and starting-region access are selected under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md); extraction/recovery, product forms, and full cell or pack design remain open.

| Product | Candidate inputs | Industrial role |
| --- | --- | --- |
| Lithium battery salts | Lithium carbonate or hydroxide | Cathode precursor and electrolyte supply |
| Cobalt and manganese cathode compounds | Cobalt sulfate and manganese compounds | Candidate alternate chemistries; not required for the initial LFP route |
| Graphite anode material | Purified natural or synthetic graphite | Battery electrodes and electrical components |
| Battery cells / packs | Cathode, anode, electrolyte, casing, current collectors | Grid buffering, mobile equipment, and process backup |

Lithium/phosphate extraction and conversion routes, product forms, anode and electrolyte, exact cell/pack routes, and capacity progression remain open. Cobalt- and manganese-based cathodes remain candidates for alternate chemistries; avoid adding every real battery formulation.

### Military Products: Weapons and Ammunition

Weapons, ammunition, and other non-building military products are in scope here. Their gameplay role and capability progression remain in [Military System](military-system.md), which currently contains the candidate weapon/ammo chains. Consolidate product identities and uses into this catalog during the catalog phase rather than duplicating that list now. Turrets and other placeable defense infrastructure remain in [Infrastructure](infrastructure.md).

### Personal Equipment: Armor, Utilities, and Modules

Armor items, wearable or personal equipment, armor utilities, and equipment modules are in scope as non-building product outputs. Their candidate inventory has not yet been established in this document; identify the needed families during coverage work before enumerating products and recipes. The user also identified power-suit equipment additions as an optional advanced military extension direction; exact product families and scope remain open (see [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md)).

### Research-Facility Prerequisite Materials

The following are candidate material products used to construct or operate dedicated research facilities. They are not themselves research ingredients: the facility produces the research pack or data item. The relevant research mechanics and gates remain in [Research and Progression](research-progression.md).

**Current direction:** Six Phase 2 bridge products and their one-to-one facility mappings are selected in [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md). These are bridge selections, not finalized recipes, yields, or technology assignments; additional supporting materials and exact construction/operation requirements remain open.

Each bridge must be producible in Phase 2 by its first required facility use and the corresponding T2a capability stage. Exact in-phase timing, recipes, yields, alternate routes, and process machinery remain open; the selected zircon and columbite-tantalite feeds have their own early/mid-Phase-2 access boundary. The electronic-grade polysilicon bridge is a precursor, not a complete processor route; conventional CPU-grade packaged processors are a late-Phase-2 capability under ADR-0025. Every description follows the design guideline from [mod-overview.md](mod-overview.md): a concrete physical property ("what happens") followed by its implication ("why it matters").

| Product | Candidate inputs / route | Industrial role & capability unlock | Description hook |
|---|---|---|---|
| Electronic-grade polysilicon | Metallurgical silicon → trichlorosilane formation and purification/distillation → hydrogen deposition with HCl recycle (route selected under [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md); HCl startup/makeup source selected under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md); exact purity target open) | Semiconductor precursor; selected bridge for the Superconductivity Research Lab. | Silicon purified to a level where every impurity matters — one wrong atom in a billion changes how it conducts electricity. At this purity, you can *choose* which state it's in by adding the right trace element. |
| Nb₃Sn superconducting wire | Niobium from columbite-tantalite and tin from cassiterite are selected baseline feeds under [ADR-0062](adrs/ADR-0062-select-phase-2-niobium-tin-bridge-feeds.md); recovery and wire fabrication remain open | High-field magnet material; enables Plasma Confinement Facility. | When cooled below a threshold, this alloy carries electric current without resistance. Cold superconducting coils can generate magnetic fields that confine plasma far hotter than the coils themselves. |
| Hafnium-oxide (HfO₂) dielectric | Hafnium-bearing stream from the distinct zirconium-hafnium separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) → oxide conversion → high-purity deposition; exact output form and grade remain open | Nanofabrication and chipmaking material; enables Nanofabrication Laboratory. | Hafnium oxide is an electrical insulator with a high dielectric constant, allowing thin transistor structures to control electric fields while limiting leakage. |
| Deuterium-enriched water (D₂O) | Brine/water → large-scale electrolysis → isotopic enrichment | Isotope and calibration research; selected bridge for the Isotope Separation & Calibration Lab. | Water where the hydrogen atoms carry an extra neutron — heavy enough that it behaves differently in nuclear reactions. A single drop can reveal how neutrons interact with matter, information no ordinary element provides. |
| High-purity cryogenic argon/nitrogen mixture | Air → multi-stage refrigeration cascade → cryogenic distillation | Cryogenic research input; selected bridge for the Quantum States Laboratory. | Argon and nitrogen can be separated from air and used at cryogenic temperatures to support low-temperature experiments. |
| High-performance rhenium-catalyst powder | Rhenium-bearing molybdenite is the selected baseline feed under [ADR-0061](adrs/ADR-0061-select-phase-2-molybdenite-rhenium-feed.md); recovery and catalyst preparation remain open | Reaction Dynamics gate; enables Reaction Dynamics Facility. Product selection is recorded in [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md). | Description hook not yet drafted. |

**Domain distribution:** The six one-to-one bridge mappings are selected in ADR-0022 and summarized in [Research and Progression](research-progression.md). Recipes, additional construction and operating materials, and technology assignments remain open.

Water/brine for D₂O and air separation for the cryogenic mixture are candidate routes, not selected processing methods. Phase 5 coverage must establish viable, accessible pre-Core paths for both without circular research or unhandled coproducts; detailed processes, machinery, and gates remain open.

### Research Ingredients and Data Products

Research ingredients are a separate product family from the materials used to construct research facilities. Conventional science packs, domain science packs, simulation datasets, and produced findings/results belong in the non-building product catalog when represented as items. Their production and consumption mechanics, tiering, and technology gates remain in [Research and Progression](research-progression.md) and [Endgame Vision](endgame-vision.md). The complete item roster is deferred to the catalog and research phases.

### Electronics and Semiconductor Products

| Product | Candidate inputs / route | Industrial role |
| --- | --- | --- |
| Metallurgical silicon | Carbothermic quartz/silica reduction in a dedicated Phase 2 submerged-arc silicon furnace under [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md); preparation, reductant mix, and recipe values remain open | Starting material for silicon purification |
| Electronic-grade polysilicon | Trichlorosilane purification/distillation and hydrogen deposition with HCl recycle; startup/makeup HCl from chlor-alkali coproducts under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md) | Phase 2 feedstock for wafer growth under [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md) |
| Silicon wafers | Single-crystal growth, slicing, polishing, doping | Semiconductor fabrication substrate |
| Photolithography materials | Specialty organic chemistry | Patterning during wafer fabrication |
| High-k dielectric compounds | Hafnium- or aluminum-based precursors and deposition | Advanced transistor insulation |
| Copper / tantalum-nitride interconnect stack | Ultra-pure copper and tantalum compounds | Reliable chip wiring and diffusion barrier |
| Tantalum capacitor powder and capacitors | Refined tantalum and capacitor fabrication | Compact, reliable electronics for control and computing |
| Packaged integrated circuits | Fabricated dies, packaging materials, electrical contacts | Conventional CPU-grade packages are available by late Phase 2 for factory automation and the initial Core; exact production route remains open |

Electronic-grade polysilicon remains a Phase 2 precursor bridge. Its standard purification and deposition route from metallurgical silicon is selected under [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md); the upstream carbothermic quartz-reduction route and dedicated Phase 2 submerged-arc silicon furnace are selected under [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md), and the HCl startup/makeup source from chlor-alkali coproducts is selected under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md). Under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md), the CO coproduct may be released through the powered, pollution-producing Gas Flare Stack; exact recipe, balance, and gate details remain open. Quartz preparation, reductant mix, HCl startup buffer and loss rates, NaOH sink, purity targets, and recipe values also remain open. Conventional CPU-grade packaged processors are available by late Phase 2 under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), and full contemporary cleanroom and advanced chipmaking capability belongs in Phase 2 under [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md). The required Phase 2 chipmaking material families are silicon wafers, lithography chemistry, HfO₂ dielectric, Cu/TaN interconnect, and package materials under [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md); all five must be used by the standard late-Phase-2 CPU path for initial Core supply under [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md). Mineral feed-family assignments for silicon, hafnium, tantalum, and copper are selected under [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md); detailed extraction/refining routes, grades, quantities, and recipes remain open. Josephson/SFQ compute is a later Core upgrade. The first-Core alignment uses an Invar mechanical assembly under [ADR-0076](adrs/ADR-0076-invar-mechanical-first-core-alignment.md); its product form and source route remain open.

Tantalum's circuit role should be distinct from its mineral recovery: concentrate it from niobium-tantalum feeds, refine it, then use it for capacitor products and selected chip components.

### Nuclear Materials and Assemblies

Phase 2 post-discharge recovery is required under [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md). Its material roles and destinations are selected under [ADR-0066](adrs/ADR-0066-select-phase-2-nuclear-recovery-flows.md), with continuous conditioned-waste disposal under [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md). Exact item identities, detailed chemistry, qualification, recipes, and balances remain open. Keep spent-uranium recovery distinct from depleted-UF6 tails and the separate thorium/U-233 cycle.

There is no universal real-world reactor bill of materials. The selected game baseline has distinct uranium and thorium options, Phase 2 cladded rods, and Phase 2 hafnium absorber preparation/forming under [ADR-0065](adrs/ADR-0065-practical-phase-2-fission-readiness.md); other configuration-specific materials remain candidates. Uraninite supplies the uranium-concentrate -> UF6 -> gas-centrifuge enrichment -> UO2 path, with separate depleted-UF6 tails. Fluorspar supplies fluorine by its first required PTFE/reagent use under [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md), no later than UF6 conversion; neither mineral has a starting-region guarantee. Detailed recovery, chemistry, grades, quantities, and equipment remain open.

The thorium option keeps separate ThO2-bearing fertile material and a uranium-derived startup seed from the shared uranium chain under [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) and [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md). The seed shares uranium fuel's qualitative enrichment grade under [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), and the numeric target remains deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md). Exact seed compound, isotope composition, quantity, item identity, preparation, detailed breeding/reprocessing chemistry, and balances remain open. The gameplay model requires no continuous uranium top-up, including through waste packaging.

#### Fission

| Product | Candidate inputs / route | Role and design hook |
| --- | --- | --- |
| Enriched uranium-oxide fuel pellet | Qualified uranium feed -> concentrate/UF6 conversion -> gas-centrifuge enrichment -> enriched UF6 -> UO2 powder -> pellet preparation; depleted UF6 is separate | Required Phase 2 rod intermediate under [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md) and [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md). Fresh Uraninite and qualified recovered-uranium routes are distinct inputs; detailed chemistry, grades, and balances remain open |
| Thorium-cycle fuel form | Separate ThO2-bearing fertile material and uranium-derived startup seed -> breeding/reprocessing -> U-233-bearing oxide rods | Selected Phase 2 architecture under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md); thorium/U-233 recovery and residual destinations are selected below. Exact seed specifications, detailed chemistry, recipes, and balances remain open |
| Zirconium-alloy cladding | Zircon-bearing feed → feed preparation/conversion → distinct Zr/Hf separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) → zirconium-bearing material for alloying and tube forming | Selected cladding family under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md); early/mid-Phase-2 zircon access is shared with the CPU hafnium chain. Separation chemistry, output form and grade, alloying and tube-forming routes, quantities, and balances are deferred to detailed design after Phase 5 coverage, which must verify a viable path for both CPU hafnium and fission cladding |
| Phase 2 fission fuel-rod assembly | Uranium fuel pellets or thorium oxide seed-and-blanket fuel, assembled with cladding | Required reactor input for both baseline fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); the thorium architecture is selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md), while exact uranium/thorium item identities, material variants, recipes, and balances remain open |
| Hafnium absorber components | Shared Zr/Hf split -> hafnium preparation to suitable metal stock -> basic absorber forming | Selected Phase 2 baseline control-material capability under ADR-0065; chipmaking HfO2 is not interchangeable metal stock. Exact grades, product form, and fabrication details remain open |
| Boron-carbide absorber parts | Boron compounds and carbon | Optional alternative absorber candidate; not a universal first-fission prerequisite |
| Reactor structural steel | Stainless and specialty steels | Pressure vessels, heat exchangers, and chemical handling |
| Graphite moderator | Purified graphite | Moderator option for selected reactor designs |

The educational process choice is unusually clean: zircon and hafnium commonly occur together, yet nuclear cladding favors zirconium with hafnium minimized, while hafnium is useful as a neutron absorber.

#### Recovery, Reuse, and Terminal Products

These are approved Phase 2 product roles under ADR-0063/0066/0068, not a frozen item catalog. Names are functional; exact item/fluid identities, forms, grouping, and recipe quantities belong to the later catalog and recipe phases.

| Product role | Source | Consumer or terminal role |
|---|---|---|
| Depleted uranium oxide | Depleted-UF6 deconversion | Stabilized shielding ceramics; surplus enters nuclear-solid conditioning. Not qualified enriched fuel |
| Uranium-oxide shielding ceramics | Stabilized depleted oxide and suitable matrix/forming | Alternative shielding for nuclear buildings and waste casks; ordinary shielding must remain available, including for first construction |
| Recovered uranium oxide | Spent uranium-fuel reprocessing | Purification/requalification -> existing conversion/enrichment front end -> qualified fuel fabrication; no direct fresh-pellet substitution |
| Recovered thorium-bearing material | Separate thorium-cycle recovery | Fertile-material preparation, with fresh thorium makeup as required |
| Bred/recovered U-233 material | Separate thorium-cycle breeding/reprocessing | Oxide-fuel preparation and cladded rod assembly |
| Recoverable cladding metal | Controlled spent-rod recovery | Qualified metallurgy/fabrication reuse; unsuitable fractions join radioactive residues |
| Recovered fluorine reagent supply | Both UF6 branches, with conditioning | UF6 conversion reagent supply; fresh mineral-derived startup/makeup is still required |
| Conditioned nuclear solids and sealed packages | Radioactive residues, contaminated recovery rejects, and surplus depleted oxide | Continuous deep disposal with power/material costs and slight pollution; no storage cap or generic solid-overflow eligibility |

Depleted oxide, recovered spent-fuel uranium oxide, and qualified enriched fuel must remain distinct in recipe eligibility. Optional depleted-uranium military uses are not guaranteed consumers or mandatory fission dependencies. Waste packaging must have a suitable ordinary-shielding route so sustained thorium does not require ongoing uranium production. Detailed chemistry and cycle behavior remain with [Chemical Processes](chemical-processes.md#selected-phase-2-polymer-and-nuclear-interfaces) and [Power System](power-system.md#phase-2-startup-and-material-handling).

#### Fusion

| Product | Candidate inputs / route | Role and design hook |
| --- | --- | --- |
| Deuterium-tritium fuel | Deuterium from water; tritium from a lithium-breeding loop | Fusion fuel cycle; tritium is produced and recovered, not mined as an ore |
| Lithium breeder blanket | Lithium-bearing feed processed into a ceramic or liquid breeder material | Neutron blanket breeds tritium and transfers heat |
| Tungsten plasma-facing armor | Refined tungsten fabricated into tiles/components | Handles intense plasma-facing heat loads in candidate designs |
| Nb3Sn / NbTi superconducting conductors | Niobium with tin or titanium, wire processing, cryogenic systems | High-field magnets for plasma confinement |
| Fusion structural and shielding materials | Stainless steel, copper, selected neutron-multiplier materials | Magnet support, heat removal, and shielding; final selection depends on reactor design |

Beryllium can serve as a neutron multiplier in some blanket concepts, but it should be an optional, well-motivated branch rather than an assumed universal fusion input. ITER's current blanket plan uses tungsten armor; alternative plasma-facing materials can remain documented variants rather than parallel mandatory chains.

### Endgame Component Products

The facility network and its buildable components are described in [Endgame Vision](endgame-vision.md) and [Infrastructure](infrastructure.md). This catalog retains the non-building product inputs and outputs used by that network.

| Product | Candidate inputs / route | Industrial role |
| --- | --- | --- |
| **Unified Metrology Reference Array** | Candidate instrument materials include Nb₃Sn wire, electronic-grade polysilicon, D₂O, rhenium catalyst, graphite support, and cryogenic Ar/N₂; their inclusion and the neutron-reference material remain open. The neutron reference must be pre-Core accessible and not require enriched fission fuel under [ADR-0037](adrs/ADR-0037-defer-array-neutron-reference-material.md) | Required physical convergence instrument for first-Core construction; six measurement zones are the intended concept. Domain packs establish research prerequisites and are not physical Array ingredients under [ADR-0077](adrs/ADR-0077-domain-packs-not-array-construction-inputs.md). Other exact inputs and recipe remain open; see [Endgame Vision](endgame-vision.md). |

Other candidate endgame assemblies whose item/entity form is unresolved remain in the Infrastructure inventory until their constructable classification is settled.

## Provisional Recipe Pathways

This is a recipe-family inventory, not a finalized recipe book. It records high-level transformations and uses, including explicitly selected capabilities, but not numeric quantities, crafting times, machine counts, or unlock requirements. Chemical inputs and reactions are specified in [Chemical Products and Processes](chemical-processes.md); candidate placeable equipment families are cataloged in [Infrastructure](infrastructure.md), while exact route-to-machine assignments remain open. Endgame facility assembly pathways belong to [Infrastructure](infrastructure.md), not this non-building product catalog. Detailed recipes remain candidates until approved.

### Recipe Pathways: Metallurgy

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Pig iron | Iron concentrate + carbon reductant + flux -> pig iron + slag/off-gas | Steelmaking feed |
| Direct-reduced iron | Iron oxide feed + hydrogen -> DRI + water | Lower-carbon steelmaking feed |
| Carbon steel | Pig iron/DRI + scrap + carbon/oxygen adjustment -> steel + slag | Main structural material |
| Stainless steel | Steel + chromium + nickel -> stainless steel | Corrosion-resistant plant, pipes, and vessels |
| Niobium microalloyed steel | Steel + ferroniobium -> high-strength steel | Pressure-bearing and high-strength structures |
| Tool steel | Steel + carbon + selected tungsten/vanadium additions -> tool steel | Durable cutters, drills, and machine parts |
| Invar | Iron + nickel -> low-expansion alloy | Precision tooling and temperature-stable parts |
| Titanium alloy | Titanium + selected alloy additions -> titanium alloy | Lightweight, high-strength structures |
| Aluminum alloy | Aluminum + selected alloy additions -> aluminum alloy | Lightweight structures and heat exchangers |

### Recipe Pathways: Batteries

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Lithium cathode precursor | Lithium carbonate/hydroxide + selected transition-metal compounds -> cathode precursor | Battery cathode material |
| Cobalt/manganese cathode compounds | Leach and purify cobalt/manganese-bearing feed -> sulfate or oxide compounds | Higher-performance battery chemistries |
| Graphite anode material | Purified graphite -> grind/classify and coat or shape | Battery anode |
| Battery cell | Cathode + anode + electrolyte + separator + casing -> cell | Electrical storage |
| Battery pack | Cells + casing + control electronics -> pack | Grid buffering and mobile equipment |

### Semiconductor and Electronics Products

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Electronic-grade polysilicon | Metallurgical silicon -> trichlorosilane purification/distillation -> hydrogen deposition with HCl recycle | Phase 2 wafer feedstock under ADR-0032 |
| Silicon wafer | Polysilicon -> single-crystal growth -> slicing/polishing/doping | Semiconductor substrate |
| Patterned wafer | Wafer + photoresist + specialty process gases -> patterned wafer | Circuit fabrication |
| Copper/tantalum-nitride interconnect | Ultra-pure copper + tantalum compound -> deposited interconnect stack | Chip wiring and diffusion barrier |
| Tantalum capacitor | Refined tantalum -> capacitor powder/anode + dielectric and packaging | Compact electronics |
| Packaged integrated circuit | Fabricated die + contacts + package -> packaged IC | Conventional CPU-grade packages by late Phase 2 for factory automation and initial Core computation |

### Recipe Pathways: Nuclear Materials

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Enriched uranium-oxide fuel pellet | Fresh Uraninite or suitably qualified recovered uranium -> uranium front end -> enriched UF6 -> UO2 -> pellets | Required Phase 2 rod intermediate; depleted tails, recovered reagents, and residuals retain the distinct destinations in [Recovery, Reuse, and Terminal Products](#recovery-reuse-and-terminal-products). Numerical enrichment targets and recipe balances remain deferred |
| Thorium-cycle fuel form | Separate ThO2-bearing fertile material and shared-chain uranium startup seed -> breeding/reprocessing -> U-233 oxide rods | Rod-compatible architecture under ADR-0055, with thorium/U-233 recovery under ADR-0066 and continuous residual disposal under ADR-0068; no continuous uranium top-up. Exact seed specifications, chemistry, and balances remain open |
| Zirconium-alloy cladding | Shared Phase 2 zircon feed -> feed preparation/conversion -> distinct Zr/Hf separation stage -> zirconium-bearing material -> alloying -> cladding tube | Selected cladding family and shared early/mid-Phase-2 access under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md); distinct separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md). Exact chemistry, output forms, alloy grade, yields, and balances remain open |
| Phase 2 fission fuel-rod assembly | Uranium or thorium oxide fuel material + cladding tube -> assembled fuel rods | Required reactor input for both baseline fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); the thorium oxide seed-and-blanket architecture is selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md), while exact item variants, recipes, and balances remain open |
| Hafnium absorber | Distinct Zr/Hf separation -> suitable hafnium metal preparation -> basic forming -> absorber component | Phase 2 baseline neutron-control capability under ADR-0065; detailed grades, fabrication, and quantities remain open |
| Boron-carbide absorber | Boron compound + carbon -> B4C component | Alternative neutron-control assembly |
| Reactor steel assembly | Stainless/specialty steel -> fabricated vessel, heat exchanger, and support parts | Reactor plant construction |
| Lithium breeder blanket | Lithium-bearing material -> ceramic/liquid breeder form -> blanket module | Fusion tritium breeding and heat transfer |
| Tungsten armor tile | Refined tungsten -> formed/finished plasma-facing tile | Fusion chamber protection |
| Nb3Sn or NbTi conductor | Niobium + tin or titanium -> superconducting alloy -> wire/cable | High-field fusion magnets |

## Design Checks

- Every listed product should unlock a capability, satisfy a distinct industrial demand, or connect two existing systems.
- Keep chemical transformations and intermediate fluids in the chemistry document; keep non-building alloys, compounds-in-use, components, and assemblies here. Placeable entities and their construction pathways belong in the infrastructure document.
- Nuclear product routes must be optional where they represent particular reactor designs; do not imply that all fission or fusion systems require the same materials.
- Show real material use in the handbook, while labeling gameplay ratios, simplified fuel cycles, and fictional applications as design abstractions.
- Check every family in the Factorio product-family checklist against the selected game version and vanilla-content scope before passing the coverage gate.
- Build the downstream list incrementally against actual recipe needs; do not restore the superseded 65–83 item target. The scope decision is recorded in [ADR-0006](adrs/ADR-0006-capability-based-intermediate-scope.md).

## Reference Sources

- [USGS niobium and tantalum statistics](https://www.usgs.gov/centers/national-minerals-information-center/niobium-and-tantalum-statistics-and-information)
- [USGS chromium statistics](https://www.usgs.gov/centers/national-minerals-information-center/chromium-statistics-and-information)
- [USGS zirconium and hafnium statistics](https://www.usgs.gov/centers/national-minerals-information-center/zirconium-and-hafnium-statistics-and-information)
- [US Department of Energy: Nuclear Fuels](https://www.energy.gov/ne/nuclear-fuels)
- [US Nuclear Regulatory Commission: Fuel Cycle](https://www.nrc.gov/materials/new-fuels)
- [ITER Blanket](https://www.iter.org/machine/blanket)
- [ITER Superconducting Magnets](https://www.iter.org/machine/magnets)

## Open Decisions and Validation

- Validate production routes for the six selected bridge products and identify their additional construction/operating inputs and research gates; the one-to-one mappings are recorded in [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).
- Decide which candidate materials, components, batteries, nuclear assemblies, and endgame products have a required downstream use.
- Select battery, fission, and fusion configurations without treating every real-world option as mandatory.
- Define whether the optional spider-bot vehicle and power-suit equipment belong in the advanced military extension; do not reintroduce the rejected military drone products.
- Validate that proposed products connect to approved mineral and chemical inputs before finalizing recipes.
- Reconcile equipment-family ownership and product-to-machine mapping.
- Confirm the product roster from capability needs rather than adopting a numeric target.
