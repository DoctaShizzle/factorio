# Chemical Products and Processes

*For: Factorio Overhaul Mod*  
*Status: Design reference / requirements phase*

Related documents: [Minerals and Refining](minerals-and-refining.md) for deposits, minerals, and refining; [Intermediate Products](intermediate-products.md) for alloys, components, and manufactured materials.

## Summary

This document tracks named industrial reactions, chemical processes, reagents, and intermediate compounds. It covers four core chains (sulfuric acid, chlor-alkali, plastics, cement/lime), later candidates (ammonia/nitric acid, nylon/engineering polymers, titanium/Kroll, nuclear fuel chemistry, fusion fuel handling), a chemical product index organized by family, and a provisional reaction/process registry with equations where meaningful.

**What it covers:** Process families, candidate chains, product index, and reaction registry — all grounded in real industrial chemistry but simplified for gameplay.

**What it does not cover:** Solid alloys and components downstream of chemistry (see [Intermediate Products](intermediate-products.md)), or equipment families that execute these processes (see [Machine Systems](machine-systems.md)).

## Purpose and Boundaries

Chemistry is an industrial decision layer, not a catalog of reactions for its own sake. Use real process names and useful intermediates to teach how industrial chains connect, while simplifying kinetics and plant design into understandable factory choices.

- Give every required product one clear, reliable happy path.
- Add alternatives when they create meaningful differences in resource recovery, pollution, infrastructure, or product quality.
- Reveal advanced options through capability unlocks; keep future processes visible in the handbook before they are buildable.
- Keep reaction chains and chemical products here. Track solid alloys, components, and assemblies in the [Intermediate Products](intermediate-products.md) document.
- Treat recipe ratios and simplified reactions as gameplay abstractions, and distinguish them from universal real-world assays in educational text.

## Core Chemical Chains

These four chains are the initial chemistry scope. Each needs a readable first route; alternatives are added only when they earn their complexity.

| Chain | Straightforward route | Later choice / capability | Connects to |
| --- | --- | --- | --- |
| Sulfuric acid | Sulfur or sulfide off-gas -> sulfur dioxide -> contact process -> acid | Capture and clean off-gas; catalyst and purity tradeoffs | Leaching, metal recovery, batteries, semiconductor processing |
| Chlor-alkali | Purified brine -> electrolysis -> chlorine + sodium hydroxide + hydrogen | Brine purification, cell configuration, coproduct balancing | Bayer alumina refining, metal leaching, PVC, hydrogen reduction |
| Plastics and polyethylene | Oil -> petrochemical feed -> ethylene -> polymerization -> plastic | Alternate cracking feeds and catalyst/polymer grades | Construction, fluid infrastructure, electronics |
| Cement and lime | Limestone -> calcination -> lime + carbon dioxide -> clinker/cement | Fuel choice, emissions capture, slag and residue use | Construction, steelmaking, endgame infrastructure |

These are process families, not final recipes. Exact inputs, yields, and machine counts remain open.

## Later Chemical Candidates

| Candidate | Real process idea | Potential gameplay role |
| --- | --- | --- |
| Coal gasification (Bosch-Messig / Lurgi) | Coal + steam/oxygen -> synthetic gas (CO+H2), ammonia byproduct | Synthetic fuel/hydrogen when oil is unavailable; bridges coal mining to petrochemical chain |
| Coal tar fractionation | Steam and solvent distillation of coal tar | Separates benzene, toluene, naphthalene, phenol, light/heavy oils — enables aromatic chemistry |
| Ammonia liquor processing | Alkali treatment of aqueous coking byproduct -> ammonium sulfate fertilizer | Recovers nitrogen from coal carbonization; links coal to agriculture |
| Methanol synthesis | CO + 2H2 -> CH3OH (Cu/ZnO catalyst) | Gateway C1 building block: formaldehyde, acetic acid, MTBE, methanol-to-olefins |
| Fischer-Tropsch synthesis | n(CO+2H2) -> -(CH2)-n + nH2O (Fe or Co catalyst) | Converts synthetic gas from coal gasification into synthetic gasoline/diesel/paraffin; bridges coal mining and fuel production |
| Cumene process (phenol) | Benzene + propylene -> cumene -> phenol + acetone (acid catalyst) | Gateway to Bakelite/phenolic resins, polycarbonates, pharmaceuticals, nylon precursors |
| Titanium chemistry | Chlorination to TiCl4 followed by magnesium reduction (Kroll process) | A high-capital, high-purity metal capability; detailed route also appears in the refining design |
| Nuclear fuel chemistry | Uranium conversion and oxide fuel fabrication; optional thorium-to-U-233 cycle | A later fission capability if nuclear power is part of the mod; see [Intermediate Products](intermediate-products.md) |
| Fusion fuel handling | Deuterium supply and tritium extraction/recycling from a lithium breeder loop | Late-game chemical separation linked to fusion infrastructure |

Before promoting a candidate into the core scope, verify that it connects to existing chains, unlocks a capability, creates a meaningful tradeoff, and has enough educational value to justify its footprint.

## Chemical Product Index

This is a candidate index of chemical products and intermediates. It is not a commitment to implement every entry.

| Family | Candidate products / intermediates |
| --- | --- |
| Sulfur | Sulfur dioxide, sulfur trioxide, sulfuric acid, sulfates |
| Bromine | Elemental bromine, hydrogen bromide, sodium/potassium bromides |
| Brine and electrolysis | Brine, chlorine, sodium hydroxide, hydrogen |
| Nitrogen | Ammonia, nitric acid, nitrate salts |
| Carbon and mineral chemicals | Coke, producer gas, coal gas (from gasification), coal tar (separated fractions: naphthalene, phenol, light/heavy oils), activated carbon, calcium carbide, acetylene, ammonia liquor (coal coking byproduct) |
| Methanol and C1 chemistry | Methanol (wood alcohol), formaldehyde, formic acid, methyl formate |
| Petrochemical feedstocks | Crude oil, naphtha, BTX aromatics (benzene, toluene, xylenes), naphthalene from coal/petroleum, ethylene, propylene, hydrogen |
| Polymers and resins | HDPE/LDPE, polypropylene (PP), PVC, nylon 6,6, PMMA (acrylic/plexiglass), Bakelite (phenolic resin), ABS/MABS, epoxy, fluoropolymer |

| Semiconductor chemistry | Trichlorosilane, photoresist precursors, WF6, SF6, NF3, deposition and etch gases |
| Nuclear and fusion chemistry | Uranium oxide fuel intermediates, lithium-bearing breeder material, deuterium, recovered tritium |

## Process Equipment and Catalysts

Choose equipment around process needs rather than introducing a unique machine for every reaction. Candidate families include catalytic gas reactors, electrolysis cells, stirred liquid reactors, thermal furnaces, and polymerization vessels. A machine family may support multiple recipes when the operation is similar.

Catalysts are physical process inputs or machine components where they create a legible choice. Different catalysts can shift selectivity, yield, purity, or operating cost. Some real catalysts deactivate and need regeneration or replacement; do not make all catalysts consumable by default.

## Balance and Factory Control

- Route templates should have stable output proportions across compatible feed profiles; the material identities vary with the feed.
- Every coproduct needs a useful downstream route, an optional recovery path, a bounded operating buffer, or feed throttling when demand is saturated.
- Avoid recipes whose intended operation depends on voiding useful products. Short buffers are acceptable; permanent accumulation is a warning to revisit ratios or applications.
- Smart routing and circuits should support stable operation. PLCs may automate complex plant control, but should not be required for basic balance.
- Show inputs, outputs, coproducts, and known uses in the handbook so players can understand a route before building it.

## Educational Content

Each handbook entry should briefly distinguish the real industrial process from the simplified game recipe. Explain what the process makes, why an alternative exists, and which details are abstracted for play. Use trustworthy references for the facts; do not present invented yields, catalyst lifetimes, or universal ore assays as real data.

## Inspiration

- **GregTech / GTNH:** memorable named reactions, real intermediates, and capability milestones; avoid its complexity wall and exhaustive reaction count.
- **Bob's / Angel's:** recognizable processing patterns and accessible chains; improve clarity around route choice and coproduct balancing.
- **Dyson Sphere Program:** keep chemistry connected to the factory's larger computational endgame rather than making it a detached subgame.

The target is meaningful industrial understanding with a bounded set of repeatable process patterns, not a fixed number of recipes or hours of playtime.

## Provisional Chemical and Reaction Registry

Everything in this registry is a **candidate for review, not approved design content**. It inventories the chemical species, products, and transformations raised so far, including provisional downstream chains from the material map. Grouped terms such as "sulfates" represent a candidate family, not a commitment to implement every salt. Count named species and products individually when estimating scope; reaction rows may produce several of them at once.

The equations below are simplified design references. Balanced equations are given where a single reaction is meaningful; separations, cracking, mineral processing, and polymer production are identified as process steps where a single equation would misrepresent the industrial operation.

### Chemical Inventory

| Family | Candidate chemicals and products |
| --- | --- |
| Water, gases, and brine | Water, hydrogen, oxygen, nitrogen, brine, sodium chloride, chlorine |
| Sulfur chemistry | Native sulfur feed, sulfur dioxide, sulfur trioxide, sulfuric acid, sulfates |
| Alkali and mineral chemicals | Sodium hydroxide, lime (calcium oxide), hydrated lime (calcium hydroxide), carbon dioxide, phosphates, borates, fluorine-bearing feedstocks |
| Nitrogen chemistry | Ammonia, nitric oxide, nitrogen dioxide, nitric acid, nitrate salts |
| Carbon and coal products | Coke, producer gas, coal tar, activated carbon, calcium carbide, acetylene |
| Petrochemical feedstocks | Crude oil, naphtha, methane/natural gas, ethylene, propylene, benzene, hydrochloric acid |
| Polymer and resin products | 1,2-dichloroethane, vinyl chloride, polyethylene (HDPE/LDPE), PVC, adipic acid, hexamethylenediamine, nylon 6,6, bisphenol A, epichlorohydrin, epoxy resin, tetrafluoroethylene, PTFE/fluoropolymer |
| Metal and silicon process chemicals | Alumina, sodium aluminate liquor, titanium tetrachloride, magnesium chloride, trichlorosilane, electronic-grade polysilicon |
| Semiconductor process chemicals | Photoresist precursors, tungsten hexafluoride, sulfur hexafluoride, nitrogen trifluoride |
| Battery and energy chemicals | Lithium carbonate, lithium hydroxide, cobalt sulfate, manganese compounds, uranium oxide fuel intermediates, thorium oxide, deuterium, tritium |

Several entries are mixtures or industrial product classes rather than pure compounds (for example, producer gas, photoresist, and manganese compounds). Keep those grouped unless a distinct recipe or gameplay use requires a specific composition.

### Reaction and Process Inventory

| Process | Simplified transformation | Status / use |
| --- | --- | --- |
| Water electrolysis | 2H2O -> 2H2 + O2 | Candidate hydrogen source and electrochemical capability |
| Chlor-alkali electrolysis | 2NaCl + 2H2O -> Cl2 + H2 + 2NaOH | Core brine route; the three coproducts must have useful sinks |
| Hydrogen chloride synthesis | H2 + Cl2 -> 2HCl | Candidate reagent supply for metal and silicon chemistry |
| Sulfur combustion | S + O2 -> SO2 | Candidate sulfur-to-acid feed route; off-gas capture versus pollution choice |
| Contact-process oxidation | 2SO2 + O2 -> 2SO3 (V2O5 catalyst) | Core sulfuric-acid route |
| Sulfur trioxide hydration | SO3 + H2O -> H2SO4 | Core sulfuric-acid route |
| Haber-Bosch ammonia synthesis | N2 + 3H2 -> 2NH3 (iron catalyst) | Later candidate; high-pressure process capability |
| Ammonia oxidation | 4NH3 + 5O2 -> 4NO + 6H2O (platinum-group catalyst) | Ostwald nitric-acid chain candidate |
| Nitrogen dioxide formation | 2NO + O2 -> 2NO2 | Ostwald chain intermediate |
| Nitric acid absorption | 3NO2 + H2O -> 2HNO3 + NO | Ostwald chain; NO returns to oxidation |
| Limestone calcination | CaCO3 -> CaO + CO2 | Core lime/cement route and carbon dioxide coproduct |
| Lime slaking | CaO + H2O -> Ca(OH)2 | Candidate construction and pH-control product |
| Clinker formation | Lime + silica + alumina/iron-bearing minerals -> clinker phases | Cement process; multi-phase industrial transformation, not a single balanced equation |
| Coal gasification (Bosch-Messig / Lurgi) | Coal + H₂O/O₂ -> syngas (CO+H₂), ammonia coproduct | Synthetic fuel/hydrogen from coal; bridges mining to petrochemical when oil is scarce |
| Coal tar fractionation | Steam/solvent distillation of coal tar -> benzene, toluene, naphthalene, phenol fractions | Enables aromatic chemistry: dyes, solvents, Bakelite precursors, plasticizers |
| Ammonia liquor processing (coal coking byproduct) | Alkali treatment of aqueous coking effluent -> ammonium sulfate / recovered cyanides | Nitrogen recovery from coal carbonization; links coal to fertilizer/chemistry |
| Calcium carbide production | CaO + 3C -> CaC2 + CO | Candidate electric-arc capability |
| Acetylene generation | CaC2 + 2H2O -> C2H2 + Ca(OH)2 | Candidate chemical feedstock route |
| Activated-carbon production | Carbonaceous feed -> porous activated carbon (steam/CO2 activation) | Candidate water-treatment and catalyst-support material |
| Crude-oil fractionation | Crude oil -> gas, naphtha, and heavier cuts | Separation, not a chemical reaction |
| Steam methane reforming | CH4 + H2O -> CO + 3H2 | Candidate hydrogen route with carbon-dioxide tradeoff downstream |
| Water-gas shift | CO + H2O -> CO2 + H2 | Candidate hydrogen/CO2 balancing step |
| Catalytic cracking | Naphtha/heavier hydrocarbons -> lighter olefins and other products | Candidate ethylene/propylene route; product mix depends on process configuration |
| Catalytic reforming | Naphtha -> aromatic-rich reformate, including benzene-family feedstocks | Candidate petrochemical route |
| Ethylene polymerization | n CH2=CH2 -> (CH2-CH2)n | Core polyethylene route; catalyst grades can create meaningful variants |
| Ethylene dichlorination | C2H4 + Cl2 -> C2H4Cl2 | Candidate PVC precursor route |
| EDC cracking | C2H4Cl2 -> C2H3Cl + HCl | Vinyl chloride and recyclable HCl candidate route |
| Vinyl chloride polymerization | n C2H3Cl -> (C2H3Cl)n | Candidate PVC route |
| Cumene process (phenol production) | C6H6 + CH3CH=CH2 -> C6H5C(CH3)2OH -> phenol + acetone (acid-catalyzed oxidation/rearrangement) | Modern phenol pathway; gateway to Bakelite, polycarbonates, and pharmaceuticals |
| Phenol-formaldehyde condensation (Bakelite) | Phenol + formaldehyde -> Bakelite resin + water | Early synthetic plastic; electrical insulators, high-temp components |
| Nylon 6,6 condensation | Adipic acid + hexamethylenediamine -> nylon 6,6 + water | Later polymer route |
| Epoxy resin production | Bisphenol A + epichlorohydrin -> epoxy resin | Candidate resin chemistry; replaces the earlier oversimplified phenol/formaldehyde note |
| Fluoropolymer production | Tetrafluoroethylene polymerization -> PTFE-like polymer | Candidate cleanroom/chemical-service material; monomer route remains open |
| Bayer alumina refining | Bauxite digestion in NaOH -> sodium aluminate liquor -> Al(OH)3 precipitation -> calcination to Al2O3 | Dedicated aluminum exception; residue and caustic recovery matter |
| Hall-Heroult electrolysis | 2Al2O3 + 3C -> 4Al + 3CO2 (simplified net reaction) | Dedicated aluminum metal-production step; sustained power requirement |
| Kroll chlorination | TiO2 + 2Cl2 + C -> TiCl4 + CO2 | Dedicated titanium precursor route |
| Kroll reduction | TiCl4 + 2Mg -> Ti + 2MgCl2 | Dedicated titanium exception; magnesium/chlorine loop candidate |
| Metallurgical-silicon reduction | SiO2 + 2C -> Si + 2CO | Quartz-to-silicon route; furnace and gas handling decision |
| Trichlorosilane formation | Si + 3HCl -> HSiCl3 + H2 | Semiconductor silicon purification precursor |
| Polysilicon deposition | HSiCl3 + H2 -> Si + 3HCl | Candidate high-purity silicon deposition; recycle HCl |
| Semiconductor gas preparation | Refined elements/compounds -> WF6, SF6, NF3 and other specialty gases | Candidate capability set; individual synthesis routes remain future work |
| Uranium fuel conversion | Uranium concentrate -> uranium oxide fuel intermediates | Candidate fission chemistry; detailed fuel-cycle design stays in the nuclear product branch |
| Lithium breeder processing | Lithium mineral/brine -> lithium-bearing blanket material -> bred tritium recovery | Fusion-linked candidate; neutron breeding is nuclear physics, not a chemical reaction |

This registry is intentionally broad so the proposal's scale is visible. Promotion to the approved design still requires your review and a documented use path for each product or intermediate.
