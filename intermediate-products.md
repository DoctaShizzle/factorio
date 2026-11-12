# Intermediate Products and Non-Building Outputs

*For: Project Prometheus*
*Status: Candidate design; product inventory and pathways provisional*
*Owner: Cross-domain non-building product catalog*
*Last updated: 2026-11-12*

Related documents: [Minerals and Refining](minerals-and-refining.md) for mined feeds and mineral-derived products; [Chemical Products and Processes](chemical-processes.md) for reactions and chemical feeds. The optional spider-bot and power-suit extension direction is recorded in [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md). Equipment-family ownership is not assigned here; the referenced `machine-systems.md` is absent from the current repository inventory, as tracked in the [Documentation Map](documentation-map.md).

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

Product entries are candidates unless explicitly approved. Favor products that unlock a capability or satisfy a distinct demand over near-duplicates; no fixed product-count target is approved.

## Factorio Product-Family Coverage Checklist

This is a completeness checklist for the production tree, not a commitment to add every vanilla or modded item. Each family must receive a scope disposition during coverage work. The examples describe gameplay families and object forms, not a version-specific inventory of Factorio GUI groups or Lua prototype types.

| Family to verify | Factorio-style examples | Treatment and owner |
|---|---|---|
| Extracted feeds and resource fluids | Ores, stone, crude oil, water, and other raw deposits | Upstream inputs; deposits and mineral feeds belong to [Minerals and Refining](minerals-and-refining.md), with placement owned by [Map and World Generation](map-world-generation.md). |
| Pure and refined materials | Separated metals, purified elements, and refined mineral products | Upstream feedstocks owned by [Minerals and Refining](minerals-and-refining.md); downstream product uses are cross-referenced here. |
| Chemical fluids, gases, and reagents | Acids, solvents, process gases, catalysts, and chemical coproducts | Chemical routes belong to [Chemical Products and Processes](chemical-processes.md); catalog identities and downstream uses are cross-referenced here. |
| Manufactured materials and components | Alloys, plates, structural parts, ceramics, glass, electronics, circuits, semiconductors, and mechanical components | Non-building products belong in this catalog; candidate coverage is partial. |
| Placeable production and utility infrastructure | Machines, power facilities, storage, transport buildings, labs, turrets, and other placeable entities | Excluded as product entries here; constructables and construction-demand hypotheses belong to [Infrastructure](infrastructure.md). Materials used to build them remain in scope here. |
| Logistics and automation products | Belts, inserters, pipes, chests, rails, rolling stock, robots, roboports, and circuit-network components | Separate placeable entities from non-building items; entity inventories belong to [Infrastructure](infrastructure.md), system behavior to [Logistics System](logistics-system.md), and manufactured non-building products to this catalog. |
| Vehicles and vehicle equipment | Cars, tanks, locomotives, wagons, spider vehicles, vehicle modules, and their service parts | Non-building vehicle items and products belong in this catalog; transport and combat behavior belongs to [Logistics System](logistics-system.md) and [Military System](military-system.md). |
| Fuels and energy carriers | Solid, liquid, gas, nuclear, and vehicle fuels; batteries and other stored-energy items | Non-building fuel and storage products belong here; generation equipment and power-system behavior belong to [Power System](power-system.md). Electricity itself is a system flow, not an inventory product. |
| Weapons and combat consumables | Guns, ammunition, rockets, explosives, grenades, capsules, and combat robots | Non-building products belong here; turrets, mines, and other placeable defenses belong to [Infrastructure](infrastructure.md), with combat progression in [Military System](military-system.md). |
| Armor and personal equipment | Armor, equipment-grid items, shields, batteries, exoskeletons, night vision, and personal roboports | Non-building products belong in this catalog; the candidate inventory still needs coverage work. |
| Upgrade modules and process consumables | Factory speed/productivity/efficiency/quality modules, equipment modules, catalysts, filters, and repair packs | Include distinct manufactured items when they have a defined role; machine behavior and constructables remain with their domain owners. |
| Research ingredients and data | Science packs, domain packs, samples, datasets, and produced findings | Research items belong in this catalog; production/consumption mechanics and technology gates belong to [Research and Progression](research-progression.md) and [Endgame Vision](endgame-vision.md). |
| Endgame computation assemblies and facilities | Compute racks, memory/archive modules, observation systems, Core assemblies, and calibration hardware | Non-building component products belong here; placeable facilities belong to [Infrastructure](infrastructure.md) and [Endgame Vision](endgame-vision.md). Ambiguous assembly outputs remain there until classified. |
| Launch and space products | Rocket parts and fuel, satellites, cargo, and space-platform components | Non-building products belong here when in scope; launch structures and placeable facilities belong to [Infrastructure](infrastructure.md) and [Endgame Vision](endgame-vision.md). |
| Biological and agricultural products | Cultivated resources, biological intermediates, nutrients, and spoilable outputs | Not yet established in the current design; explicitly decide scope before cataloging. |
| Terrain and tile products | Landfill, concrete, paths, and other placeable terrain items | Review for production/progression relevance; terrain behavior belongs to [Map and World Generation](map-world-generation.md), and placeable construction inventory to [Infrastructure](infrastructure.md). |
| Tools, containers, and interface items | Repair/construction tools, barrels, blueprints, planners, and remotes | Check against the selected vanilla-content scope; include only when they participate in the production or progression tree. |
| Byproducts, waste, and recycling streams | Slag, spent fuel, sludge, recovered materials, and other coproducts | Track each materialized item or fluid and its use or handling here; detailed route ownership remains with the relevant mineral, chemical, or power document. |

During the coverage phase, cross-check these families against the selected Factorio version and apply the scope labels in [Product Taxonomy](product-taxonomy.md): core, vanilla retained, vanilla modified, vanilla replaced, extension, or out of scope. Category presence alone does not justify adding a product. This checklist approach is recorded in [ADR-0008](adrs/ADR-0008-factorio-product-family-coverage.md).

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
| Invar / low-expansion alloy | Iron-nickel alloy | Precision tooling and temperature-stable components |
| Titanium alloy | Titanium plus aluminum/vanadium or steel additions | High-strength, corrosion-resistant late-game structures |
| Aluminum alloys | Aluminum plus selected alloying elements | Lightweight structures, heat exchangers, and transport components |

Chromium and niobium have confirmed roles in steelmaking. The gameplay distinction can be capability-based: stainless steel unlocks corrosive service, while niobium microalloyed steel enables high-strength structural parts.

### Mobility, Fuels, and Energy Storage

Vehicles and their fuel products are in scope as non-building outputs. The candidate vehicle roster, fuel items, and their source/consumer links still need to be established; fuel-process detail belongs to chemistry or power design, while transport behavior belongs to logistics. The user identified a spider-bot vehicle as an optional advanced military extension direction; it is not yet a finalized catalog entry. See [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md).

#### Battery Products

| Product | Candidate inputs | Industrial role |
| --- | --- | --- |
| Lithium battery salts | Lithium carbonate or hydroxide | Cathode precursor and electrolyte supply |
| Cobalt and manganese cathode compounds | Cobalt sulfate and manganese compounds | Higher-performance battery chemistries |
| Graphite anode material | Purified natural or synthetic graphite | Battery electrodes and electrical components |
| Battery cells / packs | Cathode, anode, electrolyte, casing, current collectors | Grid buffering, mobile equipment, and process backup |

Battery chemistry choices may trade material intensity, energy storage, lifetime, and manufacturing complexity. Specific cell chemistries remain open; avoid adding every real battery formulation.

### Military Products: Weapons and Ammunition

Weapons, ammunition, and other non-building military products are in scope here. Their gameplay role and capability progression remain in [Military System](military-system.md), which currently contains the candidate weapon/ammo chains. Consolidate product identities and uses into this catalog during the catalog phase rather than duplicating that list now. Turrets and other placeable defense infrastructure remain in [Infrastructure](infrastructure.md).

### Personal Equipment: Armor, Utilities, and Modules

Armor items, wearable or personal equipment, armor utilities, and equipment modules are in scope as non-building product outputs. Their candidate inventory has not yet been established in this document; identify the needed families during coverage work before enumerating products and recipes. The user also identified power-suit equipment additions as an optional advanced military extension direction; exact product families and scope remain open (see [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md)).

### Research-Facility Prerequisite Materials

The following are candidate material products used to construct or operate dedicated research facilities. They are not themselves research ingredients: the facility produces the research pack or data item. The relevant research mechanics and gates remain in [Research and Progression](research-progression.md).

**Count reconciliation required:** The table currently contains six products, including the committed rhenium-catalyst selection, while the earlier description and Domain distribution below refer to five. Preserve this discrepancy until the domain and product counts are reconciled; do not assume that one count is authoritative.

Each product requires deep Phase 1 capability (high-purity processing, isotopic separation, cryogenics). Every description follows the design guideline from [mod-overview.md](mod-overview.md): a concrete physical property ("what happens") followed by its implication ("why it matters").

| Product | Candidate inputs / route | Industrial role & capability unlock | Description hook |
|---|---|---|---|
| Electronic-grade polysilicon | Metallurgical silicon → chlorosilane purification → deposition (4–6N purity) | Wafer fabrication gateway; enables Superconductivity Research Lab. Silicon purified to a level where every impurity matters — one wrong atom in a billion changes how it conducts electricity. At this purity, you can *choose* which state it's in by adding the right trace element. |
| Nb₃Sn superconducting wire | Niobium + tin/silver alloy → wire drawing + cryogenic treatment | High-field magnet material; enables Plasma Confinement Facility. When cooled below a threshold, this alloy carries electric current with zero resistance — and generates magnetic fields strong enough to confine plasma at temperatures hotter than the sun's core. It's one of the few materials that can survive both. |
| Hafnium-oxide (HfO₂) dielectric | Hafnium from zirconium-bearing feed → oxide conversion → high-purity deposition | Cleanroom fabrication gate; enables Nanofabrication Laboratory. At thicknesses approaching a single molecule, hafnium oxide becomes one of the most effective electrical insulators known — yet it conducts heat well enough to prevent the structure it protects from melting. It solves a problem classical materials couldn't. |
| Deuterium-enriched water (D₂O) | Brine/water → large-scale electrolysis → isotopic enrichment | Fusion fuel feedstock + neutron moderator; enables Isotope Separation & Calibration Lab. Water where the hydrogen atoms carry an extra neutron — heavy enough that it behaves differently in nuclear reactions. A single drop can reveal how neutrons interact with matter, information no ordinary element provides. |
| High-purity cryogenic argon/nitrogen mixture | Air → multi-stage refrigeration cascade → cryogenic distillation | Superconducting cooling infrastructure + low-temperature experiments; enables Quantum States Laboratory. Gases cooled to within degrees of absolute zero — the point where thermal noise disappears and quantum effects become macroscopically visible. Below certain temperatures, matter stops behaving like particles and starts behaving like waves. |
| High-performance rhenium-catalyst powder | Molybdenite concentrate → acid attack + solvent extraction from MoS₂ residue → high-purity rhenium powder reduction → catalyst bed preparation with controlled particle size | Reaction Dynamics gate; enables Reaction Dynamics Facility. The product selection is recorded in [ADR-0007](adrs/ADR-0007-rhenium-reaction-dynamics-bridge.md); its detailed route remains provisional. |

**Domain distribution count requires reconciliation:** The earlier source statement says five prerequisite products span five physics disciplines and all five are required before advancing a simulation-fidelity tier. That conflicts with this six-row table, which includes the Reaction Dynamics selection. Preserve the breadth-across-domains gate concept while leaving the exact count and mapping open.

### Research Ingredients and Data Products

Research ingredients are a separate product family from the materials used to construct research facilities. Conventional science packs, domain science packs, simulation datasets, and produced findings/results belong in the non-building product catalog when represented as items. Their production and consumption mechanics, tiering, and technology gates remain in [Research and Progression](research-progression.md) and [Endgame Vision](endgame-vision.md). The complete item roster is deferred to the catalog and research phases.

### Electronics and Semiconductor Products

| Product | Candidate inputs / route | Industrial role |
| --- | --- | --- |
| Metallurgical silicon | Quartz reduction with carbon | Starting material for silicon purification |
| Electronic-grade polysilicon | Chlorosilane purification and deposition | Feedstock for wafer growth |
| Silicon wafers | Single-crystal growth, slicing, polishing, doping | Semiconductor fabrication substrate |
| Photolithography materials | Specialty organic chemistry | Patterning during wafer fabrication |
| High-k dielectric compounds | Hafnium- or aluminum-based precursors and deposition | Advanced transistor insulation |
| Copper / tantalum-nitride interconnect stack | Ultra-pure copper and tantalum compounds | Reliable chip wiring and diffusion barrier |
| Tantalum capacitor powder and capacitors | Refined tantalum and capacitor fabrication | Compact, reliable electronics for control and computing |
| Packaged integrated circuits | Fabricated dies, packaging materials, electrical contacts | Automation, PLCs, and advanced factory equipment |

Tantalum's circuit role should be distinct from its mineral recovery: concentrate it from niobium-tantalum feeds, refine it, then use it for capacitor products and selected chip components.

### Nuclear Materials and Assemblies

There is no single universal reactor bill of materials. These are candidate capabilities for the mod's fission and fusion systems; select a coherent reactor family rather than combining every real-world option.

#### Fission

| Product | Candidate inputs / route | Role and design hook |
| --- | --- | --- |
| Uranium oxide fuel | Uranium concentrate, conversion, and fuel fabrication | Main fission fuel path; enrichment and recycling are optional progression decisions |
| Optional thorium fuel cycle | Thorium-bearing monazite, irradiation/breeding, and U-233 fuel fabrication | Alternative long-horizon fuel capability, not a simple direct thorium burn recipe |
| Zirconium-alloy cladding | Zircon concentrate, Zr/Hf separation, alloying | Low-neutron-absorption fuel-rod cladding; high-purity zirconium is the goal |
| Hafnium absorber components | Hafnium separated from zirconium-bearing feed | Neutron-absorbing control material; a valuable co-product rather than waste |
| Boron-carbide absorber parts | Boron compounds and carbon | Alternative neutron absorber for control assemblies |
| Reactor structural steel | Stainless and specialty steels | Pressure vessels, heat exchangers, and chemical handling |
| Graphite moderator | Purified graphite | Moderator option for selected reactor designs |

The educational process choice is unusually clean: zircon and hafnium commonly occur together, yet nuclear cladding favors zirconium with hafnium minimized, while hafnium is useful as a neutron absorber.

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
| **Unified Metrology Reference Array** | Nb₃Sn wire + electronic-grade polysilicon; D₂O + enriched fuel stock; rhenium-catalyst powder + graphite support; cryogenic Ar/N₂ mixture + noble-gas purification | Candidate non-building reference instrument combining six physics measurement zones; required for calibrated Core activation. Its detailed physical concept is in [Endgame Vision](endgame-vision.md); former candidate quantities are preserved, not approved, in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md). |

Other candidate endgame assemblies whose item/entity form is unresolved remain in the Infrastructure inventory until their constructable classification is settled.

## Provisional Recipe Pathways

This is a recipe-family inventory, not a finalized recipe book. It records the candidate transformation and output use, but not numeric quantities, crafting times, machine counts, or unlock requirements. Chemical inputs and reactions are specified in [Chemical Products and Processes](chemical-processes.md); equipment ownership is unresolved because the referenced `machine-systems.md` is absent. Endgame facility assembly pathways belong to [Infrastructure](infrastructure.md), not this non-building product catalog. All entries remain candidates until approved.

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
| Electronic-grade polysilicon | Metallurgical silicon -> chlorosilane purification/deposition -> polysilicon | Wafer feedstock |
| Silicon wafer | Polysilicon -> single-crystal growth -> slicing/polishing/doping | Semiconductor substrate |
| Patterned wafer | Wafer + photoresist + specialty process gases -> patterned wafer | Circuit fabrication |
| Copper/tantalum-nitride interconnect | Ultra-pure copper + tantalum compound -> deposited interconnect stack | Chip wiring and diffusion barrier |
| Tantalum capacitor | Refined tantalum -> capacitor powder/anode + dielectric and packaging | Compact electronics |
| Packaged integrated circuit | Fabricated die + contacts + package -> packaged IC | PLCs, factory automation, and computation |

### Recipe Pathways: Nuclear Materials

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Uranium oxide fuel pellet | Uranium concentrate -> fuel conversion -> UO2 powder -> pressed/sintered pellet | Fission fuel assembly |
| Thorium-cycle fuel | Thorium-bearing feed -> optional breeding/conversion route -> U-233-bearing fuel | Optional alternative fission cycle |
| Zirconium-alloy cladding | Zircon concentrate -> Zr/Hf separation -> zirconium sponge/alloy -> cladding | Fuel-rod cladding |
| Hafnium absorber | Hafnium-bearing separation stream -> refined hafnium -> absorber component | Neutron-control assembly |
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

- Reconcile the five-versus-six research-facility prerequisite count and confirm each product's domain, facility, progression role, and research gate.
- Decide which candidate materials, components, batteries, nuclear assemblies, and endgame products have a required downstream use.
- Select battery, fission, and fusion configurations without treating every real-world option as mandatory.
- Define whether the optional spider-bot vehicle and power-suit equipment belong in the advanced military extension; do not reintroduce the rejected military drone products.
- Validate that proposed products connect to approved mineral and chemical inputs before finalizing recipes.
- Reconcile equipment-family ownership and product-to-machine mapping.
- Confirm the product roster from capability needs rather than adopting a numeric target.
