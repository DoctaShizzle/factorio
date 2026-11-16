# Chemical Products and Processes Design

*For: Project Prometheus*
*Status: Current process-family concepts are in Core scope; process registry entries, routes, and recipes remain provisional*
*Owner: Chemical products and processes*
*Last updated: 2026-11-16*

Related documents: [Minerals and Refining](minerals-and-refining.md) for deposits, minerals, and refining; [Intermediate Products](intermediate-products.md) for alloys, components, and manufactured materials. Related ADRs: [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md) for early Phase 2 salt/brine access, [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md) for the thorium fuel-cycle model, [ADR-0024](adrs/ADR-0024-include-chemical-process-concepts-in-core-scope.md) for Core process-family scope, [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) and [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md) for required CPU semiconductor materials, [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md) for the selected polysilicon route, [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md) for its selected quartz-to-silicon feed route, [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md) for the HCl startup and makeup source, [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md) for gas/fluid disposal, [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md) for Phase 2 LFP battery chemistry, [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) for the selected mineral feed sources and access, [ADR-0041](adrs/ADR-0041-phase-2-direct-use-fission-fuel.md) for the superseded direct-use fuel boundary, [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md) for the Phase 2 uranium enrichment requirement, [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md) for required Phase 2 cladding and fuel-rod assembly, [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) for the distinct Zr/Hf separation-stage boundary, [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) for the selected uranium enrichment method, [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) for the thorium seed's shared uranium-chain source, [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) for the selected high-level uranium chemical-form path, [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) for the selected fluorine-bearing mineral feed and access timing, [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) for the selected mined uranium feed and access timing, [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) for the deferred numeric uranium-fuel target, [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) for the thorium seed's shared qualitative grade, and [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md) for required Phase 2 post-discharge reprocessing/recovery of spent uranium fuel.

Related closure ADRs: [ADR-0063](adrs/ADR-0063-select-depleted-uranium-oxide-reuse.md) for oxide reuse, [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md) for PTFE startup, [ADR-0066](adrs/ADR-0066-select-phase-2-nuclear-recovery-flows.md) for recovery interfaces, and [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md) for continuous, slightly polluting nuclear disposal.

## Summary

This document tracks named industrial reactions, chemical processes, reagents, and intermediate compounds. All process-family concepts currently documented are in Core scope under [ADR-0024](adrs/ADR-0024-include-chemical-process-concepts-in-core-scope.md). The four initial chains (sulfuric acid, chlor-alkali, plastics, cement/lime) are prioritized for readable first routes; additional concepts include ammonia/nitric acid, nylon/engineering polymers, titanium/Kroll, nuclear fuel chemistry, and fusion fuel handling. The product index and reaction/process registry remain provisional.

**What it covers:** Process families, candidate chains, product index, and reaction registry — all grounded in real industrial chemistry but simplified for gameplay.

**What it does not cover:** Solid alloys and components downstream of chemistry (see [Intermediate Products](intermediate-products.md)), or equipment families that execute these processes. Candidate placeable equipment families are owned by [Infrastructure](infrastructure.md); exact route-to-machine assignments remain open.

## Purpose and Boundaries

Chemistry is an industrial decision layer, not a catalog of reactions for its own sake. Use real process names and useful intermediates to teach how industrial chains connect, while simplifying kinetics and plant design into understandable factory choices.

- Give every required product one clear, reliable happy path.
- Add alternatives when they create meaningful differences in resource recovery, pollution, infrastructure, or product quality.
- Reveal advanced options through capability unlocks; keep future processes visible in the handbook before they are buildable.
- Keep reaction chains and chemical products here. Track solid alloys, components, and assemblies in the [Intermediate Products](intermediate-products.md) document.
- Treat recipe ratios and simplified reactions as gameplay abstractions, and distinguish them from universal real-world assays in educational text.

#### Scope Boundaries

There is no numeric cap or target for chemical products, reactions, or research intermediates. Registry entries are retained only when they support a validated capability, meaningful tradeoff, or traceable downstream use.

| Scope | Bound By |
|---|---|
| Core process-family scope | All concepts currently documented, per ADR-0024; this does not approve each species, reaction, or recipe as a required product |
| Adding new chemical entries | Must solve an existing gap (missing capability, missing tradeoff, missing horizon). Each must have a visible downstream consumer beyond "it exists in the chain" |
| Semiconductor process chemicals guardrail | Entries like WF₆, SF₆, NF₃ earn their place through storyline/progression necessity (required for cleanroom and simulation infrastructure), not because they are chemically interesting. Review against this standard before promotion |
| Alternative routes gate | Only products creating meaningful tradeoffs get multiple processes. Many have one clear path with QoL improvements instead |

## Current Design and Status

All process-family concepts currently documented are in Core scope, while registry products, reactions, and recipes remain provisional except for explicitly selected capability boundaries below. No entry is approved solely because it appears here; validate its use, capability, or meaningful tradeoff and traceable downstream consumer before making it a required product or recipe.

The equations are simplified design references, not final Factorio recipes or claims about universal industrial yields. Product scope, route availability, machine assignment, quantities, and research gates remain provisional.

## Initial Chemical Chains

These four chains are the initial route priorities. Each needs a readable first route; alternatives are added only when they earn their complexity. Other process-family concepts in this document are also Core scope, but their detailed product and recipe requirements remain open.

| Chain | Straightforward route | Later choice / capability | Connects to |
| --- | --- | --- | --- |
| Sulfuric acid | Sulfur or sulfide off-gas -> sulfur dioxide -> contact process -> acid | Capture and clean off-gas; catalyst and purity tradeoffs | Leaching, metal recovery, batteries, semiconductor processing |
| Chlor-alkali | Purified brine -> electrolysis -> chlorine + sodium hydroxide + hydrogen | Brine purification, cell configuration, coproduct balancing | Bayer alumina refining, metal leaching, PVC, hydrogen reduction, and HCl synthesis under ADR-0034 |
| Plastics and polyethylene | Oil -> petrochemical feed -> ethylene -> polymerization -> plastic | Alternate cracking feeds and catalyst/polymer grades | Construction, fluid infrastructure, electronics |
| Cement and lime | Limestone -> calcination -> lime + carbon dioxide -> clinker/cement | Fuel choice, emissions capture, slag and residue use | Construction, steelmaking, endgame infrastructure |

These are process families, not final recipes. Exact inputs, yields, and machine counts remain open.

Under [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) and [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md), lithography chemistry is a required Phase 2 input family and a dependency of the standard CPU path for initial Core supply. Specific photoresist compounds, process gases, source routes, grades, and recipes remain open; the decisions do not make every candidate semiconductor gas mandatory.

## Additional Core Process Concepts

| Candidate | Real process idea | Potential gameplay role |
| --- | --- | --- |
| Coal gasification (Bosch-Messig / Lurgi) | Coal + steam/oxygen -> synthetic gas (CO+H2), ammonia byproduct | Synthetic fuel/hydrogen when oil is unavailable; bridges coal mining to petrochemical chain |
| Coal tar fractionation | Steam and solvent distillation of coal tar | Separates benzene, toluene, naphthalene, phenol, light/heavy oils — enables aromatic chemistry |
| Ammonia liquor processing | Alkali treatment of aqueous coking byproduct -> ammonium sulfate fertilizer | Recovers nitrogen from coal carbonization; links coal to agriculture |
| Methanol synthesis | CO + 2H2 -> CH3OH (Cu/ZnO catalyst) | Gateway C1 building block: formaldehyde, acetic acid, MTBE, methanol-to-olefins |
| Fischer-Tropsch synthesis | n(CO+2H2) -> -(CH2)-n + nH2O (Fe or Co catalyst) | Converts synthetic gas from coal gasification into synthetic gasoline/diesel/paraffin; bridges coal mining and fuel production |
| Cumene process (phenol) | Benzene + propylene -> cumene -> phenol + acetone (acid catalyst) | Gateway to Bakelite/phenolic resins, polycarbonates, pharmaceuticals, nylon precursors |
| Titanium chemistry | Chlorination to TiCl4 followed by magnesium reduction (Kroll process) | A high-capital, high-purity metal capability; detailed route also appears in the refining design |
| Nuclear fuel chemistry | Uranium conversion and oxide-rod fabrication; spent-uranium recovery; separate thorium/U-233 breeding and recovery | The selected front end is Uraninite -> uranium concentrate -> UF6 -> gas-centrifuge enrichment -> enriched UF6 -> UO2 -> cladded rods, with separate depleted-UF6 tails. Fluorspar supplies fluorine, including PTFE startup before nuclear equipment. The thorium route keeps separate ThO2-bearing fertile material and a shared-chain uranium startup seed, then returns U-233 as oxide rods. Recovery interfaces, oxide reuse, and conditioned residual handling are selected in the [Phase 2 interfaces](#selected-phase-2-polymer-and-nuclear-interfaces); exact chemistry, seed specifications, grades, quantities, and gates remain open. The shared qualitative uranium-fuel/seed enrichment target remains numerically deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) and [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) |
| Fusion fuel handling | Deuterium supply and tritium extraction/recycling from a lithium breeder loop | Late-game chemical separation linked to fusion infrastructure |

Before promoting a candidate species, reaction, or recipe to a required product route, verify that it connects to existing chains, unlocks a capability, creates a meaningful tradeoff, and has enough educational value to justify its footprint.

## Chemical Product Index

The process-family concepts are in Core scope; individual entries in this candidate index are not automatically approved as required products or recipes.

| Family | Candidate products / intermediates |
| --- | --- |
| Sulfur | Sulfur dioxide, sulfur trioxide, sulfuric acid, sulfates |
| Bromine | Elemental bromine, hydrogen bromide, sodium/potassium bromides |
| Brine and electrolysis | Brine, chlorine, sodium hydroxide, hydrogen |
| Nitrogen | Ammonia, nitric acid, nitrate salts |
| Carbon and mineral chemicals | Coke, producer gas, coal gas (from gasification), coal tar (separated fractions: naphthalene, phenol, light/heavy oils), activated carbon, calcium carbide, acetylene, ammonia liquor (coal coking byproduct) |
| Methanol and C1 chemistry | Methanol (wood alcohol), formaldehyde, formic acid, methyl formate |
| Petrochemical feedstocks | Crude oil, naphtha, BTX aromatics (benzene, toluene, xylenes), naphthalene from coal/petroleum, ethylene, propylene, acrylonitrile, hydrogen |
| Polymers and resins | HDPE/LDPE, polypropylene (PP), PVC, nylon 6,6, PMMA (acrylic/plexiglass from acrylonitrile), Bakelite (phenolic resin), ABS/MABS (acrylonitrile-butadiene-styrene), PVA (polyvinyl alcohol), epoxy, fluoropolymer |

| Semiconductor chemistry | Trichlorosilane, photoresist precursors, WF6, SF6, NF3, deposition and etch gases |
| Nuclear and fusion chemistry | Uranium oxide fuel intermediates, lithium-bearing breeder material, deuterium, recovered tritium |

## Process Equipment and Catalysts

Choose equipment around process needs rather than introducing a unique machine for every reaction. Candidate families include catalytic gas reactors, electrolysis cells, stirred liquid reactors, thermal furnaces, and polymerization vessels. A machine family may support multiple recipes when the operation is similar.

Catalysts are physical process inputs or machine components where they create a legible choice. Different catalysts can shift selectivity, yield, purity, or operating cost. Some real catalysts deactivate and need regeneration or replacement; do not make all catalysts consumable by default.

## Selected Phase 2 Polymer and Nuclear Interfaces

### PTFE Startup

[ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md) requires a complete PTFE-free startup path:

**fluorspar + Phase 2 chemical/petrochemical capabilities -> fluorine reagents and tetrafluoroethylene -> baseline polymerization -> PTFE -> initial forming/sintering -> construction-grade seals and linings**

The baseline Polymerization Reactor uses compatible metal construction and non-PTFE sealing. Upstream reagent/monomer preparation and initial PTFE finishing must also be buildable without PTFE and before the first nuclear/cleanroom consumer. Do not rely on recovered nuclear HF to start this chain or on a PTFE-equipped extruder/Phase 3 molding press to finish its first seals. PTFE finishing must not be assumed to use ordinary melt processing.

Exact monomer synthesis, reagents, service-compatible materials, construction-product forms, equipment allocation, and quantities remain open. Stainless steel is not a universal compatibility guarantee for HF, fluorine, or every process condition.

### Nuclear Recovery and Conditioning

The [Power System](power-system.md#phase-2-startup-and-material-handling) owns cycle direction; [Intermediate Products](intermediate-products.md#recovery-reuse-and-terminal-products) owns the distinct product roles. Chemistry must support these selected handoffs under [ADR-0066](adrs/ADR-0066-select-phase-2-nuclear-recovery-flows.md):

- Depleted-UF6 deconversion produces depleted oxide and recoverable HF. Enriched-UF6 reconversion must also account for its fluorine-bearing outputs. Recover and condition reusable fluorine into the UF6 reagent supply; fresh fluorspar-derived startup/makeup remains necessary.
- Spent uranium fuel yields recovered uranium oxide for purification/requalification and return through the existing conversion/enrichment front end. Chemical purification alone does not establish isotopic suitability; do not restore spent material directly to qualified pellets.
- Recover thorium to fertile-material preparation and U-233 to oxide-fuel preparation and rod assembly. Preserve the separate startup seed and the gameplay model's lack of continuous uranium top-up.
- Recover suitable cladding metal through qualification and metallurgy; rejected metal fractions and other non-recovered radioactive material enter waste conditioning.
- Recover useful material/reagents from nuclear-bearing carriers. Immobilize remaining radioactive fractions in a stable matrix and seal them into suitable packages for continuous deep disposal under [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md). Disposal consumes power/materials and produces slight pollution representing abstracted underground leakage; it has no tracked storage cap. Generic flares/clarifiers cannot erase radioactive fractions.

Stabilization of depleted oxide for shielding is selected under [ADR-0063](adrs/ADR-0063-select-depleted-uranium-oxide-reuse.md). Exact oxide forms, matrix chemistry, recovery species, reagent regeneration, qualification, losses, and numerical balances remain open; no separate plutonium product or lossless fuel cycle is selected.

## Balance and Factory Control

- Route templates should have stable output proportions across compatible feed profiles; the material identities vary with the feed.
- Every coproduct needs a useful downstream route, recovery, a bounded operating buffer, production control, or an allowed disposal path. Conditioned nuclear solids alone may use continuous powered/material-consuming disposal with slight pollution under ADR-0068; other solid coproducts do not gain a generic disposal route.
- Ordinary gas/fluid disposal is an explicit process, not silent recipe deletion; every release consumes power and produces pollution under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md). Nuclear-bearing streams must retain radioactive fractions for recovery/conditioning under ADR-0068 before cleaned carrier release.
- Make viable handling available by first production of every modeled coproduct. Unhandled permanent accumulation is not acceptable; continuous nuclear disposal is an explicit terminal process, not storage assumed to empty later.
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

All current process-family concepts are in Core scope under ADR-0024. Entries in this registry remain **candidates for review, not approved product or recipe requirements**. It inventories the chemical species, products, and transformations raised so far, including provisional downstream chains from the material map. Grouped terms such as "sulfates" represent a candidate family, not a commitment to implement every salt.

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
| Battery and energy chemicals | Lithium carbonate, lithium hydroxide, lithium iron phosphate (LFP) cathode material, cobalt sulfate, manganese compounds, uranium oxide fuel intermediates, thorium oxide, deuterium, tritium |

Several entries are mixtures or industrial product classes rather than pure compounds (for example, producer gas, photoresist, and manganese compounds). Keep those grouped unless a distinct recipe or gameplay use requires a specific composition.

The initial Phase 2 grid-storage battery uses LFP cathode chemistry under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md), with lithium and phosphate feed families and starting-region access selected under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). Lithium recovery, phosphate conversion, and cathode production routes remain open.

### Reaction and Process Inventory

| Process | Simplified transformation | Status / use |
| --- | --- | --- |
| Water electrolysis | 2H2O -> 2H2 + O2 | Candidate hydrogen source and electrochemical capability |
| Chlor-alkali electrolysis | 2NaCl + 2H2O -> Cl2 + H2 + 2NaOH | Phase 2 source of H2 and Cl2 for HCl synthesis under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md); a useful NaOH consumer remains open, but surplus may be disposed under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md) |
| Hydrogen chloride synthesis | H2 + Cl2 -> 2HCl | Selected Phase 2 startup/makeup route under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md), using chlor-alkali coproducts; startup buffer and loss rates remain open |
| Sulfur combustion | S + O2 -> SO2 | Candidate sulfur-to-acid feed route; off-gas capture versus pollution choice |
| Pyrite roasting | 4FeS2 + 11O2 -> 2Fe2O3 + 8SO2 (heat-driven) | Industrial SO2 source from sulfide ores (chalcopyrite/sphalerite); enables acid without native sulfur mine |
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
| Methanol oxidation (formaldehyde) | CH3OH + 0.5O2 -> HCHO + H2O (iron-molybdate catalyst) | Formaldehyde production: Bakelite, resins, disinfectants; essential bridge from methanol synthesis |
| Acetic acid synthesis (oxidation route) | CH3OH + CO -> CH3COOH (Rh/Ir catalyst, 150°C/50 bar) | Acetic acid/anhydride: cellulose acetate fiber/film, vinyl acetate, nylon precursors |
| Catalytic cracking | Naphtha/heavier hydrocarbons -> lighter olefins and other products | Candidate ethylene/propylene route; product mix depends on process configuration |
| Catalytic reforming | Naphtha -> aromatic-rich reformate, including benzene-family feedstocks | Candidate petrochemical route |
| Ethylene polymerization | n CH2=CH2 -> (CH2-CH2)n | Core polyethylene route; catalyst grades can create meaningful variants |
| Ethylene dichlorination | C2H4 + Cl2 -> C2H4Cl2 | Candidate PVC precursor route |
| EDC cracking | C2H4Cl2 -> C2H3Cl + HCl | Vinyl chloride and recyclable HCl candidate route |
| Ethylene oxidation to ethylene oxide | 2C2H4 + O2 -> 2C2H4O (Ag catalyst, 200-300°C) | Gateway to PET polyester, antifreeze/coolant (ethylene glycol), solvents; major GTNH petrochemical branch |
| Ethylene oxide hydration to glycol | C2H4O + H2O -> HOCH2CH2OH (acid-catalyzed) | Antifreeze and PET precursor; bridges ethylene chemistry to polymer production |
| Vinyl chloride polymerization | n C2H3Cl -> (C2H3Cl)n | Candidate PVC route |
| Cumene process (phenol production) | C6H6 + CH3CH=CH2 -> C6H5C(CH3)2OH -> phenol + acetone (acid-catalyzed oxidation/rearrangement) | Modern phenol pathway; gateway to Bakelite, polycarbonates, and pharmaceuticals |
| HCl recovery from chlorinated organics | R-Cl + H2O (or O2 dehydrochlorination) -> R' + HCl | Closes the PVC loop: recovers HCl for reuse in ethylene dichlorination; key to PVC economics |
| Acrylonitrile ammoxidation (Sohio process) | CH3CH=CH2 + NH3 + 1.5O2 -> CH2CHCN + 3H2O (Bi-Mo catalyst) | Gateway to MABS plastics, acrylic fiber, and ABS polymer; links propylene to engineering plastics |
| Phenol-formaldehyde condensation (Bakelite) | Phenol + formaldehyde -> Bakelite resin + water | Early synthetic plastic; electrical insulators, high-temp components |
| Nylon 6,6 condensation | Adipic acid + hexamethylenediamine -> nylon 6,6 + water | Later polymer route |
| Epoxy resin production | Bisphenol A + epichlorohydrin -> epoxy resin | Candidate resin chemistry; downstream polymer route remains open |
| Fluoropolymer production | Tetrafluoroethylene polymerization -> PTFE -> initial construction-product forming/sintering | Selected Phase 2 bootstrap capability under ADR-0064 in the baseline Polymerization Reactor; upstream monomer/reagent chemistry and finishing equipment remain open, but the complete startup path cannot require PTFE or nuclear HF recovery |
| Bayer alumina refining | Bauxite digestion in NaOH -> sodium aluminate liquor -> Al(OH)3 precipitation -> calcination to Al2O3 | Dedicated aluminum exception; residue and caustic recovery matter |
| Hall-Heroult electrolysis | 2Al2O3 + 3C -> 4Al + 3CO2 (simplified net reaction) | Dedicated aluminum metal-production step; sustained power requirement |
| Kroll chlorination | TiO2 + 2Cl2 + C -> TiCl4 + CO2 | Dedicated titanium precursor route |
| Kroll reduction | TiCl4 + 2Mg -> Ti + 2MgCl2 | Dedicated titanium exception; magnesium/chlorine loop candidate |
| Metallurgical-silicon reduction | SiO2 + 2C -> Si + 2CO | Selected Phase 2 carbothermic route in a dedicated submerged-arc silicon furnace under [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md); CO may be released through the Gas Flare Stack under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md), with recipe, balance, and gate details open |
| Trichlorosilane formation | Si + 3HCl -> HSiCl3 + H2 | Selected Phase 2 electronic-grade polysilicon route under ADR-0032 |
| Trichlorosilane distillation | HSiCl3-bearing chlorosilane mixture -> purified HSiCl3 | Selected purification stage under ADR-0032; exact purity target remains open |
| Polysilicon deposition | HSiCl3 + H2 -> Si + 3HCl | Selected Phase 2 deposition step under ADR-0032; HCl recycle is part of the route |
| Semiconductor gas preparation | Refined elements/compounds -> WF6, SF6, NF3 and other specialty gases | Candidate capability set; individual synthesis routes remain future work |
| Uranium fuel conversion | Uraninite -> uranium concentrate (U3O8/yellowcake reference) -> UF6 conversion -> gas-centrifuge enrichment -> enriched UF6 -> UO2 powder -> pellets for Phase 2 fuel-rod assembly; depleted UF6 tails are tracked separately | The high-level chemical-form path is selected under [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), Uraninite feed/access under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md), and fluorspar (fluorite) feed/access under [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md). Enriched UO2 and rod assembly are required under [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md) and [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md), and gas centrifuges are selected under [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md). Uranium/fluorite recovery, reagent preparation, detailed conversion chemistry, equipment, balances, and research gates remain open. Tails deconversion to uranium oxide and HF is selected under [ADR-0053](adrs/ADR-0053-select-depleted-uf6-deconversion.md), uranium oxide is recovered for later uranium use and HF for reuse in UF6 conversion under [ADR-0054](adrs/ADR-0054-select-depleted-uf6-output-fates.md); exact forms and conditioning remain open; the numeric uranium-fuel enrichment target is deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) until detailed recipe and balance design |
| Nuclear recovery and reagent conditioning | Spent fuel -> qualified recovered-material routes + residuals; fluorine-bearing conversion outputs -> reusable reagent supply + rejects | Selected interfaces under ADR-0066; uranium, thorium/U-233, and cladding retain separate qualification and reuse paths |
| Nuclear-solid conditioning | Radioactive residues or surplus depleted oxide + suitable matrix/packaging -> conditioned packages -> continuous deep disposal | Selected terminal role under ADR-0068; power/material inputs, slight operating pollution, and throughput constrain disposal, not a storage cap. Matrix chemistry and recipes remain open |
| Lithium breeder processing | Lithium mineral/brine -> lithium-bearing blanket material -> bred tritium recovery | Fusion-linked candidate; neutron breeding is nuclear physics, not a chemical reaction |

This registry is intentionally broad to make the current process concepts visible. Promotion of a product or intermediate to a required design element still needs a documented use path and validation.

## Open Decisions and Validation

- The current process-family concepts are in Core scope under ADR-0024. Validate product entries, reactions, routes, and any process concepts added later separately; do not infer recipe approval from scope inclusion.
- Reconcile the candidate reaction and research-intermediate counts with the shared product taxonomy; the current approximate counts are not targets.
- Validate chemical coproducts, reagent recovery, and ordinary gas/fluid disposal costs under ADR-0035, retaining radioactive-stream restrictions and continuous nuclear-solid disposal with slight pollution under ADR-0068.
- Demonstrate the full PTFE-free reagent/monomer/polymerization/finishing bootstrap and both UF6 fluorine-return paths before catalog freeze; then select detailed chemistry, qualification, losses, and balances in their owning phases.
- Confirm each retained chemistry product has a downstream use and an owning product-tree entry.
- Assign process equipment to candidate families in [Infrastructure](infrastructure.md) after the relevant routes are approved.
- Validate educational claims and reaction simplifications against trustworthy references before promoting them to player-facing content.
