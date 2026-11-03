# Factorio Overhaul — Complete Material Chain Map

*For: Factorio Overhaul Mod — Design Phase*
*Status: Requirements mapping (not final)*

Related design: [Mining, Refining & Metallurgy](mining-refining-metallurgy.md)

---

> **Draft catalog v0.4:** Use real mineral/resource names and real geological deposit classes as identifiers; this draft does not assign invented site names. Recovery associations are candidate gameplay mappings, not claims that every specimen contains each listed element. Exact assays, ratios, and recipe availability remain to be validated.

## Mining Catalog

The tiers describe deposit/feed profiles. The same mineral may occur in multiple deposits or tiers. Surface deposits are finite and single-mineral; underground deposits have one dominant mineral plus traces; Orefields combine several major minerals. A deposit's trace minerals are distinct from secondary and tertiary materials recovered from refining its main mineral.

"Mineral" is used here as a player-facing umbrella for mined feeds. Some entries are technically rocks or commodities rather than single mineral species: coal, bauxite, limestone, gypsum, and mineral-sand concentrates. Educational articles should identify that distinction.

### Tier 1: Surface Deposits

| Primary mineral / resource | Real feed / deposit type | Primary material | Secondary material | Tertiary material |
| --- | --- | --- | --- | --- |
| Hematite | Hematite-bearing surface outcrop | Iron | Manganese | Silica |
| Malachite | Oxidized copper occurrence | Copper | Cobalt | Silica |
| Coal | Coal seam (industrial raw resource) | Carbon / coke | Sulfur | Germanium |
| Quartz | Quartz-rich sand or vein | Metallurgical silicon | Alumina | Titanium |
| Native sulfur | Native sulfur deposit | Sulfur | Selenium | Tellurium |
| Calcite / limestone | Carbonate rock deposit | Lime | Magnesium | Carbon dioxide |
| Gypsum | Gypsum-bearing evaporite bed | Gypsum | Sulfur | Lime |

These are finite starter supplies of foundational materials. Secondary and tertiary recovery are later refining capabilities; listing a material here does not mean the early process exposes it.

### Tier 2: Underground Deposits

| Primary mineral | Secondary mineral | Tertiary mineral / trace phase | Real deposit setting |
| --- | --- | --- | --- |
| Magnetite | Ilmenite | Pyrite | Titanomagnetite / iron-titanium oxide setting |
| Chalcopyrite | Pyrite | Arsenopyrite or native gold | Porphyry copper or polymetallic sulfide setting |
| Native gold | Arsenopyrite | Pyrite | Orogenic gold-bearing quartz vein |
| Sphalerite | Galena | Pyrite | Zinc-lead sulfide replacement or vein deposit |
| Galena | Sphalerite | Pyrite | Lead-zinc sulfide vein or replacement deposit |
| Pentlandite | Chalcopyrite | Cooperite | Magmatic nickel-copper sulfide setting |
| Bauxite | Quartz | Rutile | Lateritic or karst bauxite profile |
| Chromite | Magnetite | Cooperite | Chromitite in a layered or ultramafic intrusion |
| Cassiterite | Columbite-tantalite | Beryl | Tin-bearing granite, pegmatite, greisen, or placer |
| Scheelite | Molybdenite | Fluorite | Tungsten skarn or W-Mo greisen |
| Pyrolusite | Hematite | Apatite | Sedimentary or supergene manganese oxide deposit |
| Zircon | Ilmenite | Rutile | Heavy-mineral placer sand |
| Graphite | Pyrite | Apatite | Graphite-bearing metamorphic rock |
| Apatite | Monazite | Calcite | Phosphorite or apatite-rich igneous deposit |
| Spodumene | Beryl | Columbite-tantalite | Rare-element pegmatite |
| Halite | Sylvite | Gypsum | Evaporite basin |
| Bastnaesite | Monazite | Fluorite | Carbonatite or alkaline igneous rare-earth setting |
| Uraninite | Pyrite | Monazite | Uranium-bearing vein or sandstone-hosted deposit |

### Tier 3: Orefields

**Orefield** is the generic player-facing category for large polymetallic deposits. The UI can show the real deposit class and its primary, secondary, and tertiary minerals. The trace-phase column is design metadata and need not be shown in the UI. Composition varies by formation and should be prospectable before full-scale extraction.

| Real deposit class | Primary mineral | Secondary mineral | Tertiary mineral | Deposit-dependent trace phases |
| --- | --- | --- | --- | --- |
| Volcanogenic massive sulfide (VMS) | Chalcopyrite | Sphalerite | Galena | Pyrite; possible gold and silver |
| Banded iron formation (BIF) | Hematite | Magnetite | Quartz | Apatite or ilmenite in some deposits |
| Porphyry copper-molybdenum | Chalcopyrite | Molybdenite | Pyrite | Gold in some deposits |
| Rare-element pegmatite | Spodumene | Columbite-tantalite | Beryl | Cassiterite and quartz |
| Layered mafic-ultramafic intrusion | Chromite | Pentlandite | Magnetite | Platinum-group minerals in some deposits |
| Evaporite basin | Halite | Sylvite | Gypsum | Borate minerals in some deposits |
| Orogenic gold / greenstone-hosted lode | Native gold | Arsenopyrite | Pyrite | Chalcopyrite only in polymetallic variants |

These are candidate formation archetypes, not guaranteed recipes. Orefields should combine minerals in geology-inspired profiles, rather than one universal composition.

## Mineral Recovery Matrix

This is the current candidate feed roster, not a chemical formula table. A mined feed includes its dominant mineral plus associated minerals, trace phases, and gangue. Primary/secondary/tertiary are game-design recovery roles for a specified feed profile and route; they are not universal properties of the mineral species. Educational entries should distinguish elements bound in the mineral from trace elements recovered from associated phases or processing residues. Every listed association remains a candidate pending reference checks.

| Mineral / raw feed | Primary material | Secondary material | Tertiary material |
| --- | --- | --- | --- |
| Hematite | Iron | Manganese | Silica |
| Malachite | Copper | Cobalt | Silica |
| Coal | Carbon / coke | Sulfur | Germanium |
| Quartz | Metallurgical silicon | — | — |
| Native sulfur | Sulfur | — | — |
| Calcite / limestone | Lime | Magnesium | Carbon dioxide |
| Gypsum | Gypsum | Lime | — |
| Magnetite | Iron | Vanadium | Titanium |
| Chalcopyrite | Copper | Iron | Sulfur |
| Pyrite | Iron | Sulfur | Cobalt |
| Arsenopyrite | Arsenic | Iron | Gold |
| Sphalerite | Zinc | Cadmium | Indium |
| Galena | Lead | Silver | Sulfur |
| Pentlandite | Nickel | Copper | Cobalt |
| Cooperite (platinum-group sulfide) | Platinum | Palladium | Rhodium |
| Chromite | Chromium | Iron | Magnesium |
| Bauxite | Alumina / aluminum | Gallium | Iron |
| Cassiterite-bearing concentrate | Tin | Niobium-tantalum | Tungsten |
| Scheelite | Tungsten | Molybdenum | Lime |
| Molybdenite | Molybdenum | Rhenium | Sulfur |
| Pyrolusite | Manganese | Iron | Cobalt |
| Ilmenite | Titanium | Iron | Vanadium |
| Apatite | Phosphorus | Calcium | Rare-earth concentrate |
| Spodumene | Lithium compounds | Aluminum | Silica |
| Halite | Sodium | Chlorine | Potassium |
| Sylvite | Potassium | Chlorine | Sodium |
| Fluorite | Fluorine-bearing chemical feed | Calcium | — |
| Native gold | Gold | Silver | Tellurium |
| Monazite | Cerium / rare earths | Neodymium | Thorium |
| Bastnaesite | Cerium / rare earths | Lanthanum | Fluorine-bearing chemical feed |
| Columbite-tantalite | Niobium | Tantalum | Tin |
| Beryl | Beryllium | Aluminum | Silica |
| Zircon | Zirconium | Hafnium | Silicon |
| Uraninite | Uranium concentrate | Thorium | — |
| Borax | Boron compounds | Sodium | Water |
| Graphite | Carbon | Silica | Iron |

## Pure-Material Inventory

This is the consolidated candidate list of refined mineral products represented in the matrix above. Compounds are listed where elemental production would be an unnecessary or unrealistic extra step. Further additions should earn their place through a distinct use, a meaningful refining choice, or an endgame dependency.

| Material group | Candidate pure materials |
| --- | --- |
| Base and structural | Iron, copper, aluminum, alumina, metallurgical silicon, carbon, sulfur, lime, silica, gypsum |
| Common alloy and process metals | Zinc, lead, nickel, cobalt, chromium, tin, manganese, titanium, vanadium, magnesium |
| Precious and catalyst metals | Gold, silver, platinum, palladium, rhodium |
| Specialty and semiconductor metals | Gallium, germanium, indium, cadmium, tungsten, molybdenum, rhenium, niobium, tantalum, beryllium, zirconium, hafnium |
| Chemical and battery feedstocks | Lithium carbonate / hydroxide, sodium chloride / sodium compounds, potassium chloride, phosphorus / phosphate, boron compounds, fluorine-bearing feedstocks |
| Rare, radioactive, and trace | Uranium, thorium, cerium, lanthanum, neodymium, yttrium, selenium, tellurium, arsenic |
| Other recovered compounds | Carbon dioxide, water |

"Rare-earth concentrate" is an intermediate, not a final pure material. Its separation into individual rare earths is a later capability. This inventory covers mineral-derived products; chemicals, polymers, semiconductor products, and endgame materials remain provisional downstream candidates below.

## Refining Stages and Route Patterns

### Reusable Stages

| Stage | Operations | Role |
| --- | --- | --- |
| 1. Prepare | Crush, grind, screen, wash, classify | Liberate mineral grains and remove coarse gangue |
| 2. Concentrate | Gravity, magnetic, or flotation separation | Enrich target minerals and create manageable tails |
| 3. Extract | Roast, smelt, reduce, or leach | Separate target materials from the concentrate |
| 4. Purify | Precipitate, crystallize, electrowin, or electrorefine | Produce usable-purity metals or compounds |
| 5. Recover and finish | Reprocess selected residues; wash, dry, calcine, or cast | Recover valuable traces and make stable products |

### Route Templates

| Core route pattern | Typical sequence | Strength / tradeoff |
| --- | --- | --- |
| Mechanical concentration | Prepare -> gravity/magnetic separation -> concentrate | Reusable and low-reagent; leaves mineral-bearing tails |
| Flotation concentration | Prepare -> flotation -> concentrate -> thermal or chemical extraction | Selective sulfide recovery; uses water/reagents and creates secondary streams |
| Thermal extraction | Prepare -> roast/smelt/reduce -> purify | High throughput; fuel/power, off-gas, and slag decisions |
| Chemical extraction | Prepare -> leach -> purify solution -> precipitate/electrowin | Selective, often high purity; needs reagent loops and residue treatment |
| Electrorefining | Impure metal/anode -> electrorefine -> recover anode residues | High purity; continuous power and residue handling |
| Residue recovery | Route selected tails/slags/slimes -> reprocess -> recover trace products | Adds late trace recovery without making traces the main ore; bounded by residue supply |

### Dedicated Exceptions

- **Aluminum:** Bayer digestion and Hall-Heroult electrolysis; a distinctive chemical-refining and power capability.
- **Titanium:** Kroll reduction as a late, capital-intensive capability.
- **Rare earths and platinum-group metals:** staged concentrate separation and residue recovery, not a generic one-step route.
- **Semiconductor silicon:** metallurgical silicon, chlorosilane purification, polysilicon, and wafer growth belong to the semiconductor chain, not the common ore route.

#### Exception Candidates to Evaluate

- **Lithium brines:** spodumene can use the chemical-extraction route, while brines may need evaporation/concentration and precipitation. Treat this as a source-specific branch only if brines are included as a meaningful mineable feed.
- **Nb-Ta and Zr-Hf separation:** these chemically similar element pairs may justify dedicated late separation steps after shared concentration. They do not need separate end-to-end ore routes.
- **Ga, Ge, In, and Re:** keep these as residue/byproduct recovery capabilities within aluminum, zinc, coal, and molybdenum chains, rather than creating a bespoke primary route for each.

These are candidates, not committed exceptions. A dedicated route should add a distinct capability or teach a genuinely different industrial process; rarity or a long recipe chain alone is not enough.

Finishing (washing, drying, calcining, casting) is part of the relevant route, not a separate progression tree. The route catalog is a compact process vocabulary, not a mandate that every mineral use every step. A given template should keep primary/secondary/tertiary output proportions consistent across accepted feeds, while mineral identities and geological associations vary.

### Balanceability Checks

- Every Orefield feed must have at least one viable baseline route and a discoverable advanced route.
- Across the mineral roster, common primary materials need multiple sources and multiple consumers; trace targets should be recoverable from residues without requiring pure primary products to be consumed at the same rate.
- For each route template, account for every output as a useful material, an input to further recovery, a finite buffer, or a reason to throttle/pause feed. Required voiding is not an acceptable balance solution.
- Test the roster against iron-heavy, copper-heavy, alloy-heavy, and trace-recovery demand profiles. No profile should force permanent accumulation when the player selects compatible deposits and routes.
- Smart routing and throughput control should be enough for stable operation. PLCs can automate the decisions, but basic balance must not depend on custom code.

### Reference Inspirations

- [GTNH Ore Generation](https://wiki.gtnewhorizons.com/wiki/Ore_Generation): deposits composed of primary, secondary, between, and sporadic minerals; use this as a model for geological variety and prospectable deposit identity, not for copying its full roster.
- [GTNH Ore Processing Concepts](https://wiki.gtnewhorizons.com/wiki/Ore_Processing_Concepts): multiple routes per mineral, route flexibility, expandable processing, and staged recovery of tertiary byproducts.
- [Angel's Refining](https://mods.factorio.com/mod/angelsrefining): a compact compound-ore set and reusable multi-step refining backbone; borrow its readability goals, not its fixed ore roster or exact balance assumptions.
- [Bob's Ores](https://mods.factorio.com/mods/Bobingabout/bobores) and [Bob's Plates](https://mods.factorio.com/mod/bobplates): broader material coverage and reusable smelting, chemical, and electrolysis capabilities.

---

## Downstream Chains (Provisional)

These are downstream systems supported by the mineral catalog. Their recipes and detailed material inventories are intentionally deferred; this section is a connection map, not a second mining/refining progression.

### Chemicals (Initial Candidates)

These connect multiple industrial chains together. The "glue" between minerals.

#### Acid Production Chain

| Material | From | Purpose |
| --- | --- | --- |
| Sulfur dioxide (SO₂) | Roasting sulfide feeds such as pyrite or chalcopyrite | Acid feedstock or pollution |
| Sulfuric acid (H₂SO₄) | Contact process from captured SO₂ | Leaching, metal recovery, and chemical synthesis |

#### Chlor-Alkali Chain

| Material | From | Purpose |
| --- | --- | --- |
| Brine (purified NaCl solution) | Dissolved salt from salt deposits | Electrolysis input |
| Chlorine gas (Cl₂) | Chlor-alkali electrolysis of brine | PVC, ferric chloride leaching agent |
| Sodium hydroxide (NaOH) | Chlor-alkali electrolysis | Bayer process solvent, pH control |
| Hydrogen gas (H₂) | Chlor-alkali or water electrolysis | H₂ reduction for hematite, fuel |

#### Nitrogen Chain

| Material | From | Purpose |
| --- | --- | --- |
| Ammonia (NH₃) | Haber-Bosch (N₂ from air + H₂) | Fertilizer, nitric acid precursor |
| Nitric acid (HNO₃) | Ostwald process (ammonia + oxygen over Pt catalyst) | Explosives, specialty chemical synthesis |

#### Carbon Chain

| Material | From | Purpose |
| --- | --- | --- |
| Coke | Coal carbonization (heated without air) | Blast furnace fuel/reducer |
| Activated carbon | Pyrolyzed biomass/coal | Water purification, catalyst support |
| Calcium carbide (CaC₂) | Lime + coke in electric arc furnace | Acetylene production, steel deoxidizer |
| Carbon nanotubes/fibers | CVD from hydrocarbon gas | Advanced composite material (late-game) |

### Nuclear Materials (Candidate Scope)

There is no single universal materials list for fission or fusion; reactor designs differ. Treat these as a bounded set of industrial capability branches, not as a requirement to simulate every reactor type.

| Capability branch | Candidate feed materials | Refined products / role | Design status |
| --- | --- | --- | --- |
| Fission fuel | Uraninite; optional monazite/thorium feed | Uranium oxide fuel; optional thorium-to-U-233 fuel-cycle branch | Uranium fuel is core if modded fission is in scope; thorium cycle is optional late-game depth |
| Fuel cladding and neutron control | Zircon; hafnium-bearing zircon concentrate; boron minerals | High-purity zirconium alloy cladding; hafnium- or boron-based neutron absorbers | Zr-Hf separation is a strong dedicated capability because both are co-produced but serve opposing reactor roles |
| Structural reactor alloys | Chromium, nickel, iron, niobium | Stainless and niobium-alloy steels for hot, corrosive, or high-load plant equipment | Reuse the metallurgy/alloy system; no new ore-processing ladder |
| Fusion fuel breeding | Lithium minerals or brines; water-derived deuterium | Lithium-bearing blanket material breeds tritium from fusion neutrons; recover and recycle tritium as fuel | Strong late-game process chain; lithium brine is a source-specific alternative to spodumene |
| Fusion plasma and magnets | Tungsten; niobium, tin, titanium; copper | Tungsten plasma-facing armor; Nb3Sn or NbTi superconducting magnet conductors | Capability unlock linking specialty metals, fabrication, and cryogenic power systems |

Candidate supporting materials include graphite or water as fission moderators, beryllium as a possible fusion blanket neutron multiplier, and cadmium/boron/hafnium as neutron absorbers. Include these only where a chosen reactor design makes their role legible and useful.

The most distinctive gameplay chain is zircon concentrate -> Zr/Hf separation -> zirconium alloy for fuel cladding plus hafnium absorber products. It turns a demanding separation into two complementary products. For fusion, lithium-to-tritium breeding and Nb-based superconducting magnets are similarly strong capability milestones. Deuterium and tritium are fuels, not mined mineral products.

Reference sources: [U.S. DOE nuclear fuels](https://www.energy.gov/ne/nuclear-fuels), [U.S. NRC fuel cycle](https://www.nrc.gov/materials/new-fuels), [USGS zirconium and hafnium](https://www.usgs.gov/centers/national-minerals-information-center/zirconium-and-hafnium-statistics-and-information), [ITER blanket](https://www.iter.org/machine/blanket), and [ITER superconducting magnets](https://www.iter.org/machine/magnets).

---

### Alloys and Specialty Metals

These require mid-to-late game infrastructure. Capability unlocks.

#### Refining Group Metals (From Chalcopyrite Byproduct Recovery)

| Material | From | Purpose |
| --- | --- | --- |
| Gold | Precious metal recovery from sulfide ore processing | Catalyst substrate, electronics |
| Silver | Same as gold | Catalyst, chemical processing equipment |
| Platinum group metals (PGM) | Trace in sulfide ores, concentrated via flotation tailings | Inert anodes, Haber-Bosch catalyst, nitric acid catalyst |

#### Specialty Steel Alloys

| Material | From | Purpose |
| --- | --- | --- |
| Stainless steel | Steel + chromium/nickel in electric arc furnace | Corrosion-resistant construction, acid handling equipment |
| Niobium microalloyed steel | Steel + ferroniobium from columbite-tantalite concentrate | High-strength structural steel and pressure-vessel components |
| Titanium steel | Steel + titanium addition (from Kroll process, see below) | Lightweight structural alloy |
| Tool steel | High-carbon steel + tungsten/vanadium | Hardwearing machine parts, drill bits |
| Invar/low-expansion alloy | Iron + nickel (36% Ni) | Precision components, measurement equipment |

#### Non-Ferrous Specialty Metals

| Material | From | Purpose |
| --- | --- | --- |
| Zinc | Roasting + electrolysis of sphalerite concentrate | Galvanizing, alloys, batteries |
| Lead | Roasting + reduction of galena concentrate | Acid-resistant construction, battery plates |
| Nickel | High-pressure acid leaching of laterite ore or sulfide roast-leach | Stainless steel ingredient, catalyst, batteries |
| Titanium (pure) | Kroll process (TiCl₄ + Mg in argon atmosphere) | Lightweight high-strength structures |
| Magnesium | Electrolysis of molten MgCl₂ or carbothermal reduction of MgO | Reducing agent for Kroll process, lightweight alloy |

#### Battery Materials (Mid-to-Late Game)

| Material | From | Purpose |
| --- | --- | --- |
| Lithium carbonate/hydroxide | Brine evaporation or leaching from spodumene ore | Battery chemistry, electrolyte |
| Cobalt sulfate | Leaching + purification of cobalt-containing ores | Battery cathode material |
| Manganese compounds | Leaching of manganese oxide ores | Battery cathodes, steel additive |

---

### Polymers and Plastics

These connect oil refining to downstream manufacturing. Not ore-based but critical for the mod.

#### Oil/Rubber Refining Path

| Material | From | Purpose |
| --- | --- | --- |
| Naphtha | Fractional distillation of crude oil | Petrochemical feedstock |
| Ethylene | Catalytic cracking of naphtha or natural gas liquids | Polymerization monomer, chemical intermediate |
| Propylene | Catalytic cracking | Polymerization, propylene oxide precursor |
| Benzene | Reforming of naphtha | Adipic acid/nylon precursor, chlorobenzene |
| Polyethylene (HDPE/LDPE) | Polymerization of ethylene + catalyst | Plastic production, pipe materials for fluid handling |
| PVC | Chlorination of ethylene → polymerization with Cl₂ | Pipes, cable insulation, fluid system materials |

#### Advanced Polymers (Late Game)

| Material | From | Purpose |
| --- | --- | --- |
| Nylon 6,6 (polyamide) | Adipic acid + hexamethylenediamine from benzene | Fiber, engineering plastic |
| Epoxy resin precursor | Phenol + formaldehyde (from coal or petrochemical route) | Adhesives, composite matrix |
| Fluoropolymer (PTFE analog) | Ethylene + fluorine (from fluoride minerals) | Chemical-resistant piping/sealing for cleanroom |

---

### Semiconductor Materials

These connect the base industry chain to the endgame.

| Material | From | Purpose |
| --- | --- | --- |
| Silicon wafers (single crystal) | Czochralski process from polysilicon + dopant | Base substrate for IC fabrication |
| Photolithography resist | Specialty organic synthesis | Pattern definition on wafers |
| High-k dielectric (HfO₂, Al₂O₃) | Chemical vapor deposition precursors | Gate insulation for advanced transistors |
| Tantalum capacitors and Cu/TaN interconnects | Tantalum oxide capacitor powders; ultra-pure copper and tantalum nitride barrier | Compact electronics and reliable chip wiring |
| Specialty gases (WF₆, SF₆, NF₃) | Gas synthesis from refined elements | Etching and deposition in cleanroom |

---

### Endgame Network Materials

These are used to build the endgame computational network.

| Material | From | Purpose |
| --- | --- | --- |
| Processed semiconductor units | Wafer fab → diced chips → packaged ICs | Computing capacity component |
| Superconductor materials | Specialty metal alloy synthesis (NbTi, YBCO) | Zero-loss power distribution for cluster |
| Cryogenic fluid (liquid He/N₂) | Gas liquefaction and separation | Cooling for superconducting systems |
| Precision optics | Optical glass synthesis + polishing | Photonics/simulation interconnects |

---

### Scope and Progression Intent

The design target is an ambitious overhaul that can support a 300+ hour playthrough, in the space between Bob's/Angel's and Pyanodon's in perceived complexity. That is a playthrough ambition, not a promise that raw recipe count alone should create hundreds of hours. The catalog should earn its scope through geological discovery, capability unlocks, reusable process patterns, cross-chain demand, and factory-scale logistics.

Keep the mineral roster bounded and memorable. Chemical reactions, polymers, semiconductor fabrication, and endgame computation extend the ecosystem, but their detailed recipes and complete inventories remain future design work. The superseded 65-83 material estimate is not a target.

### Educational Content Direction

Handbook entries should clearly separate:

- **Real mineral or deposit-type facts:** composition, formation, common associations, and actual industrial recovery routes.
- **Game abstraction:** simplified feed ratios, recipe outputs, stage unlocks, and fictional Orefield/site names.
- **Design choices:** where output ratios are deliberately standardized for playability, explain that the ratio is a game rule rather than a universal geological assay.

Use the real mineral and deposit-class name as the article/UI label. Do not add invented locality names or present a game-specific co-product ratio as a universal geological fact.

Initial reference set:

- [USGS volcanogenic massive sulfide occurrence model](https://www.usgs.gov/publications/volcanogenic-massive-sulfide-occurrence-model) for VMS mineral assemblages and deposit context.
- [USGS chalcopyrite overview](https://www.usgs.gov/publications/chalcopyrite-bearer-a-precious-non-precious-metal) for chalcopyrite composition, copper use, and weathering context.
- [USGS gallium resource data for bauxite](https://www.usgs.gov/publications/compilation-gallium-resource-data-bauxite-deposits) for the bauxite-gallium association and its variability.
- [USGS alluvial placer tin model](https://pubs.usgs.gov/bul/b1693/html/bull3pke.htm) for cassiterite and associated heavy-mineral products such as ilmenite, zircon, monazite, and columbite-tantalite.
- [USGS rare-earth mineral resources](https://www.usgs.gov/centers/national-minerals-information-center/rare-earths-statistics-and-information) for principal rare-earth minerals and resource context.

---

## Current Refining Direction

The catalog above is the current candidate roster: finite single-mineral surface deposits, underground deposits with one dominant mineral plus traces, and variable Orefields containing several main minerals. Mining determines the feed; refining capabilities determine which materials can be recovered.

- Use GTNH primarily as inspiration for geological and material breadth, and Bob's/Angel's for accessible, reusable processing stages and output balancing; do not copy either mod's exact material list or ratios.
- Reuse recognizable mechanical, chemical, and thermal/electrolytic stages where appropriate, with exceptions for material chemistry.
- For a given refining-process template, keep primary-material, trace-material, and residue output proportions consistent across the minerals using it; vary material identities by mineral. Different process templates can have different ratios and tradeoffs.
- Later refining capabilities may recover more trace materials at the cost of lower primary-material yield per unit of feed.
- Avoid required voiding. A key unresolved constraint is recovering trace materials without requiring saturated primary outputs to be consumed at a matching rate.
- The mineral roster and process network must support stable operation without unavoidable output backups when players choose appropriate feeds and routes. Smart routing and throughput control should suffice for basic stability; PLCs can optionally automate them. Validate this against multiple demand profiles.

This is a working direction, not a final process specification. The dedicated [Mining, Refining & Metallurgy](mining-refining-metallurgy.md) document holds the feed-profile model and refining requirements; this map tracks candidate materials and dependencies.
