# Minerals and Refining Design

*For: Project Prometheus*
*Status: Candidate design; catalog and routes require validation*
*Owner: Minerals and refining*
*Last updated: 2026-11-16*

Related documents: [Map and World Generation](map-world-generation.md), [Chemical Products and Processes](chemical-processes.md), and [Intermediate Products](intermediate-products.md). Related ADRs: [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md) for material and brine phase boundaries, [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) for the pre-Core polysilicon precursor, [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md) for the selected thorium fuel-cycle model, [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) for required Phase 2 semiconductor material families, [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md) for their use on the standard CPU path, [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md) for selected mineral feed families, [ADR-0030](adrs/ADR-0030-early-access-to-semiconductor-feed-deposits.md) for limited early/mid-Phase-2 access to zircon and columbite-tantalite, [ADR-0031](adrs/ADR-0031-starting-region-access-to-cpu-feed-families.md) for quartz and copper starting-region access, [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md) for the downstream polysilicon route, [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md) for the selected quartz reduction route, [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md) for powered, pollution-producing gas/fluid disposal, [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md) for the selected Phase 2 battery chemistry and feed requirements, [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) for selected feed sources and starting-region access, [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md) for the Phase 2 cladding and rod requirement, [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) for zirconium-alloy cladding and shared zircon access, [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) for the distinct Zr/Hf separation-stage boundary, [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) for the high-level uranium-concentrate conversion and fuel-cycle forms, [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) for the selected fluorspar feed and access timing, [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) for the selected Uraninite feed and access timing, and [ADR-0060](adrs/ADR-0060-select-phase-2-monazite-thorium-feed.md) for the selected Th-232 feed family and access boundary.

Related closure ADRs: [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md) for first-use fluorine supply, [ADR-0065](adrs/ADR-0065-practical-phase-2-fission-readiness.md) for Phase 2 hafnium preparation, and [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md) for the narrow conditioned nuclear-solid disposal exception.

> **Draft catalog v0.4:** Use real mineral/resource names and real geological deposit classes as identifiers; this draft does not assign invented site names. Recovery associations are candidate gameplay mappings, not claims that every specimen contains each listed element. Exact assays, ratios, and recipe availability remain to be validated.

## Summary

This document catalogs the mining and refining scope: three tiers of deposits (surface, underground, polymineral), a mineral recovery matrix mapping mined feeds to primary/secondary/tertiary pure materials, a consolidated pure-material inventory organized by group, five reusable refining stages with route templates, and balanceability requirements.

**What it covers:** Deposit tiers, mineral catalog, recovery assignments, pure-material roster, refining process templates, dedicated exceptions (Al, Ti, REEs, PGM), balanceability checks, and reference inspirations from GTNH / Bob's / Angel's.

**What it does not cover:** Chemical reactions and reagents (see [Chemical Products and Processes](chemical-processes.md)), manufactured alloys and components downstream of refining (see [Intermediate Products](intermediate-products.md)), or machine equipment families. Candidate placeable processing equipment is cataloged in [Infrastructure](infrastructure.md); route-specific machine assignments remain open.

## Current Design and Boundaries

The deposit roster, recovery associations, pure-material inventory, and route exceptions below are candidates, not a final approved product list or chemical formula table. The draft uses real mineral/resource and geological deposit names; recovery roles are gameplay mappings to validate, not universal claims about every specimen. Exact assays, yields, recipe quantities, and recipe availability remain undecided.

The current draft lists approximately 36 deposit types across three tiers; this is an inventory estimate, not a target or cap. Refined-product scope follows capability, meaningful choice, and progression needs rather than a fixed count; geological existence alone is not sufficient.

Chemical products and manufactured alloys/components are owned by their linked domain documents. This document owns mined feeds, mineral recovery, mineral-derived pure materials, and reusable refining route patterns.

### Mining Catalog

The tiers describe deposit/feed profiles. The same mineral may occur in multiple deposits or tiers. Surface deposits are finite and single-mineral; underground deposits have one dominant mineral plus traces; polymineral deposits combine several major minerals. A deposit's trace minerals are distinct from secondary and tertiary materials recovered from refining its main mineral.

"Mineral" is used here as a player-facing umbrella for mined feeds. Some entries are technically rocks or commodities rather than single mineral species: coal, bauxite, limestone, gypsum, and mineral-sand concentrates. Educational articles should identify that distinction.

#### Scope Boundaries

The mineral catalog is bounded by validated gameplay capabilities, not by a Phase 2 intermediate cap. Every deposit type must earn its place through gameplay value — either enabling a unique capability or creating a meaningful tradeoff. The current roster of approximately 36 deposit types across 3 tiers is an unvalidated inventory estimate.

| Scope | Bound By |
|---|---|
| Total deposits | ~36 types (8 Tier 1 surface + 21 Tier 2 underground + 7 Tier 3 polymineral) |
| Primary materials per deposit | One clear dominant output; secondary/tertiary listed only where they connect to usable capabilities |
| Adding new deposits | Must solve an existing gap — missing capability, missing tradeoff, or missing horizon. "It exists in real geology" is not sufficient |

### Tier 1: Surface Deposits

| Primary mineral / resource | Real feed / deposit type | Biome | Primary material | Secondary material | Tertiary material |
| --- | --- | --- | --- | --- | --- |
| Hematite | Hematite-bearing surface outcrop | Shield region, Mountain range (BIF edges) | Iron | Manganese | Silica |
| Malachite | Oxidized copper occurrence | Shield region (oxidized zone), Mountain range | Copper | Cobalt | Silica |
| Coal | Coal seam (industrial raw resource) | Mountain range (uplifted seams) | Carbon / coke | Sulfur | Germanium |
| Quartz | Quartz-rich sand or vein | Shield region, Sedimentary basin edges | Metallurgical silicon | — | — |
| Native sulfur | Native sulfur deposit | Volcanic zone | Sulfur | — | — |
| Calcite | Carbonate rock deposit | Sedimentary basin | Lime (calcium oxide) | — | Carbon dioxide |
| Dolomite | Magnesian limestone or dolostone | Sedimentary basin | Magnesium compounds | Calcium/lime | Silica traces |
| Gypsum | Gypsum-bearing evaporite bed | Sedimentary basin, Coastal/shelf hybrid | Gypsum | Lime | — |

These are finite starter supplies of foundational materials. Secondary and tertiary recovery are later refining capabilities; listing a material here does not mean the early process exposes it. Under [ADR-0031](adrs/ADR-0031-starting-region-access-to-cpu-feed-families.md), the starting region provides accessible quartz and at least one eligible copper-bearing feed for the later Phase 2 CPU chain. This does not select the copper deposit or require Phase 1 semiconductor processing.

### Tier 2: Underground Deposits

| Primary mineral | Secondary mineral | Tertiary mineral / trace phase | Real deposit setting | Biome(s) |
| --- | --- | --- | --- | --- |
| Magnetite | Ilmenite | Pyrite | Titanomagnetite / iron-titanium oxide setting | Shield region, Mountain range (BIF edges) |
| Chalcopyrite | Pyrite | Arsenopyrite or native gold | Porphyry copper or polymetallic sulfide setting | Shield region, Volcanic zone |
| Native gold | Arsenopyrite | Pyrite | Orogenic gold-bearing quartz vein | Volcanic zone, Mountain range (adjacent) |
| Sphalerite | Galena | Pyrite | Zinc-lead sulfide replacement or vein deposit | Mountain range |
| Galena | Sphalerite | Pyrite | Lead-zinc sulfide vein or replacement deposit | Mountain range |
| Pentlandite | Chalcopyrite | Cooperite | Magmatic nickel-copper sulfide setting | Shield region |
| Bauxite | Quartz | Rutile | Lateritic or karst bauxite profile | Shield region (weathering cap), Volcanic zone edges |
| Chromite | Magnetite | Cooperite | Chromitite in a layered or ultramafic intrusion | Shield region |
| Cassiterite | Columbite-tantalite | Beryl | Tin-bearing granite, pegmatite, greisen, or placer | Mountain range, Coastal/shelf hybrid (placer) |
| Scheelite | Molybdenite | Fluorite | Tungsten skarn or W-Mo greisen | Mountain range |
| Pyrolusite | Hematite | Apatite | Sedimentary or supergene manganese oxide deposit | Sedimentary basin, Shield region (oxidized zone) |
| Zircon | Ilmenite | Rutile | Heavy-mineral placer sand | Coastal/shelf hybrid, river deltas |
| Graphite | Pyrite | Apatite | Graphite-bearing metamorphic rock | Mountain range |
| Trona | Evaporite soda-ash deposit | Sodium carbonate | Potassium compounds | Sedimentary basin |
| Brine (subsurface) | — | Bromine compounds; Sodium; Potassium, lithium traces | Concentrated saltwater aquifer | Sedimentary basin, Coastal/shelf hybrid |
| Apatite | Monazite | Calcite | Phosphorite or apatite-rich igneous deposit | Sedimentary basin, Mountain range (carbonatite) |
| Spodumene | Beryl | Columbite-tantalite | Rare-element pegmatite | Mountain range |
| Halite | Sylvite | Gypsum | Evaporite basin | Sedimentary basin, Coastal/shelf hybrid |
| Bastnaesite | Monazite | Fluorite | Carbonatite or alkaline igneous rare-earth setting | Mountain range |
| Uraninite | Pyrite | Monazite | Uranium-bearing vein or sandstone-hosted deposit | Shield region, Sedimentary basin |

### Tier 3: Polymineral Deposits

**Polymineral deposit** is the player-facing category for large polymineral deposits. The UI can show the real deposit class and its primary, secondary, and tertiary minerals. The trace-phase column is design metadata and need not be shown in the UI. Composition varies by formation and should be prospectable before full-scale extraction.

| Real deposit class | Primary mineral | Secondary mineral | Tertiary mineral | Deposit-dependent trace phases | Biome(s) |
| --- | --- | --- | --- | --- | --- |
| Volcanogenic massive sulfide (VMS) | Chalcopyrite | Sphalerite | Galena | Pyrite; possible gold and silver | Volcanic zone, Mountain range (adjacent) |
| Banded iron formation (BIF) | Hematite | Magnetite | Quartz | Apatite or ilmenite in some deposits | Shield region, Mountain range edges |
| Porphyry copper-molybdenum | Chalcopyrite | Molybdenite | Pyrite | Gold in some deposits | Mountain range, Shield region (uplifted zone) |
| Rare-element pegmatite | Spodumene | Columbite-tantalite | Beryl | Cassiterite and quartz | Mountain range |
| Layered mafic-ultramafic intrusion | Chromite | Pentlandite | Magnetite | Platinum-group minerals in some deposits | Shield region |
| Evaporite basin | Halite | Sylvite | Gypsum | Borate minerals in some deposits | Sedimentary basin, Coastal/shelf hybrid |
| Orogenic gold / greenstone-hosted lode | Native gold | Arsenopyrite | Pyrite | Chalcopyrite only in polymetallic variants | Volcanic zone, Mountain range (adjacent) |

These are candidate formation archetypes, not guaranteed recipes. Polymineral deposits should combine minerals in geology-inspired profiles, rather than one universal composition.

## Mineral Recovery Matrix

This is the current candidate feed roster, not a chemical formula table. A mined feed includes its dominant mineral plus associated minerals, trace phases, and gangue. Primary/secondary/tertiary are game-design recovery roles for a specified feed profile and route; they are not universal properties of the mineral species. Educational entries should distinguish elements bound in the mineral from trace elements recovered from associated phases or processing residues. Every listed association remains a candidate pending reference checks.

| Mineral / raw feed | Primary material | Secondary material | Tertiary material |
| --- | --- | --- | --- |
| Hematite | Iron | Manganese | Silica |
| Malachite | Copper | Cobalt | Silica |
| Coal | Carbon / coke | Sulfur | Germanium |
| Quartz | Metallurgical silicon | — | — |
| Native sulfur | Sulfur | — | — |
| Calcite | Lime (calcium oxide) | — | Carbon dioxide |
| Dolomite | Magnesium compounds | Calcium/lime | Silica traces |
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
| Fluorite (fluorspar) | Fluorine-bearing chemical feed | Calcium | — |
| Native gold | Gold | Silver | Tellurium |
| Monazite | Cerium / rare earths | Neodymium | Thorium |
| Bastnaesite | Cerium / rare earths | Lanthanum | Fluorine-bearing chemical feed |
| Columbite-tantalite | Niobium | Tantalum | Tin |
| Beryl | Beryllium | Aluminum | Silica |
| Zircon | Zirconium | Hafnium | Silicon |
| Uraninite | Uranium concentrate | Thorium | — |
| Borax | Boron compounds | Sodium | Water |
| Graphite | Carbon | Silica | Iron |

Uraninite is selected as the Phase 2 mined feed for uranium concentrate, with limited supply accessible by the UF6-conversion unlock under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md). Its listed thorium secondary output remains a candidate only; it is not selected as a coproduct or as the Th-232 feed for the thorium fuel route. The uranium-derived startup seed comes from the shared uranium chain under [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md).

Monazite-bearing deposits are the selected mined feed family for Th-232 under [ADR-0060](adrs/ADR-0060-select-phase-2-monazite-thorium-feed.md). Limited supply must be reachable by the thorium power-route unlock without a starting-region guarantee. This feed-family selection does not assign an exact deposit profile or item form; recovery chemistry, grades, quantities, residues, and balances are deferred to detailed product and recipe design after Phase 5 coverage. Uranium recovery, deposit occurrence, placement, grades, quantities, and balances also remain open.

Rhenium-bearing molybdenite is the selected baseline feed for the Phase 2 Reaction Dynamics bridge under [ADR-0061](adrs/ADR-0061-select-phase-2-molybdenite-rhenium-feed.md). Limited supply and recovery must be accessible by the bridge's first required use without relying on the Reaction Dynamics Facility, its own domain packs, or the first Core; a starting-region deposit is not guaranteed. Deposit profile, recovery chemistry, coproduct handling, forms, grades, quantities, and gates remain open.

The first-Core Invar mechanical alignment assembly under [ADR-0076](adrs/ADR-0076-invar-mechanical-first-core-alignment.md) requires an accessible pre-Core iron/nickel supply and alloy/fabrication capability. Hematite is a candidate iron feed and pentlandite a candidate nickel feed; neither this requirement nor the matrix selects a particular feed, guarantees a nickel deposit in the starting region, or establishes a recovery route.

The Phase 2 Nb3Sn wire bridge uses niobium from columbite-tantalite and tin from cassiterite under [ADR-0062](adrs/ADR-0062-select-phase-2-niobium-tin-bridge-feeds.md). Columbite-tantalite supply is shared with the CPU tantalum path. Both feeds and their recovery must be accessible by the wire's first required use without relying on the Plasma Confinement Facility, its own packs, or the first Core; neither a starting-region deposit nor colocation is guaranteed. Recovery, shared-feed balances, fabrication, and gates remain open.

## Pure-Material Inventory

This is the consolidated candidate list of refined mineral products represented in the matrix above. Compounds are listed where elemental production would be an unnecessary or unrealistic extra step. Further additions should earn their place through a distinct use, a meaningful refining choice, or an endgame dependency.

| Material group | Candidate pure materials |
| --- | --- |
| Base and structural | Iron, copper, aluminum, alumina, metallurgical silicon, carbon, sulfur, lime, silica, gypsum |
| Common alloy and process metals | Zinc, lead, nickel, cobalt, chromium, tin, manganese, titanium, vanadium, magnesium |
| Precious and catalyst metals | Gold, silver, platinum, palladium, rhodium |
| Specialty and semiconductor metals | Gallium, germanium, indium, cadmium, tungsten, molybdenum, rhenium, niobium, tantalum, beryllium, zirconium, hafnium |
| Chemical and battery feedstocks | Lithium carbonate / hydroxide, sodium chloride / sodium compounds, potassium chloride, phosphorus / phosphate, boron compounds, fluorine-bearing feedstocks, bromine compounds |

Under [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) and [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md), the standard late-Phase-2 CPU path for initial Core supply requires silicon, hafnium, tantalum, and copper material families. Their feed-family assignments are selected in [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md): quartz for metallurgical silicon, zircon for hafnium as a secondary product, columbite-tantalite for tantalum as a secondary product, and copper-bearing deposits (malachite, chalcopyrite, and pentlandite) as eligible copper sources. Limited zircon and columbite-tantalite supply must be reachable by early/mid Phase 2 under [ADR-0030](adrs/ADR-0030-early-access-to-semiconductor-feed-deposits.md); carbothermic quartz reduction in a dedicated Phase 2 submerged-arc silicon furnace is selected under [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md), feeding the electronic-grade polysilicon route in [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md). Quartz preparation, carbon reductant mix, other-feed recovery routes, grades, yields, quantities, CO handling, and phase gates remain open.

Both baseline fission options require Phase 2 cladding and fuel-rod assembly under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md). Zirconium alloy is the selected cladding family, and early/mid-Phase-2 zircon access is shared with the CPU hafnium chain under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md). The shared path requires a distinct Zr/Hf separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md); feed preparation/conversion, separation chemistry, output forms and grades, alloying, quantities, and balances are deferred to detailed design after Phase 5 coverage. Equipment/entity scope and research gates remain for their owning design phases. Coverage must verify viable paths for both CPU hafnium and fission cladding; validate their combined demand before fixing supply balances.

The same separated hafnium stream must support Phase 2 preparation to suitable metal stock and basic reactor-absorber forming under [ADR-0065](adrs/ADR-0065-practical-phase-2-fission-readiness.md). Ore access or chipmaking HfO2 alone is not that capability. CPU hafnium, reactor absorbers, and zirconium cladding have independent demands; coverage must not assume one continually consumes the others' coproducts.

The Phase 2 uranium route uses Uraninite as the selected mined feed for uranium concentrate and fluorspar (fluorite) as the baseline fluorine-bearing feed, both accessible by the UF6-conversion unlock under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) and [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md), respectively. Neither feed is required in the starting region. Uranium and fluorite recovery, deposit occurrence and placement, grades, quantities, reagent preparation, and balances remain open.

Fluorspar recovery and reagent preparation must additionally support the first PTFE/fluorochemical use before PTFE-built nuclear equipment under [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md). This startup supply cannot depend on recovered nuclear HF or equipment that already needs PTFE; the selected mineral family and lack of a starting-region guarantee are unchanged.

The initial Phase 2 battery uses LFP cathode chemistry under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md). Lithium may come from spodumene or brine as alternative sources, and apatite-rich phosphorite supplies phosphate under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). The starting region guarantees apatite-rich phosphorite and lithium-bearing brine; spodumene may be regional. Detailed recovery routes and grades are deferred to process and recipe design after Phase 5 coverage; exact deposit placement and quantities remain world-generation validation work.
| Rare, radioactive, and trace | Uranium, thorium, cerium, lanthanum, neodymium, yttrium, selenium, tellurium, arsenic |
| Other recovered compounds | Carbon dioxide, water |

"Rare-earth concentrate" is an intermediate, not a final pure material. Its separation into individual rare earths is a later capability. This inventory covers mineral-derived products; chemicals, polymers, semiconductor products, and endgame materials are mapped in the companion documents.

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

- **Aluminum and alumina:** Bayer digestion and Hall-Heroult electrolysis are Phase 2-or-later capabilities under [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md). Neither aluminum nor alumina is a Phase 1 material prerequisite; Phase 1 equipment uses basic refractory.
- **Titanium:** Kroll reduction as a late, capital-intensive capability.
- **Rare earths and platinum-group metals:** staged concentrate separation and residue recovery, not a generic one-step route.
- **Semiconductor silicon:** metallurgical silicon, chlorosilane purification, polysilicon, and wafer growth belong to the semiconductor chain, not the common ore route.

#### Exception Routes and Candidates

- **Lithium source routes:** Brine and spodumene are selected as alternative lithium sources for LFP under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). Salt/brine is reachable by early Phase 2, with basic extraction/evaporation; chlor-alkali remains a Phase 2 process. Detailed brine-lithium recovery and the separate spodumene extraction route are deferred to process and recipe design after Phase 5 coverage.
- **Zr-Hf separation:** The shared zircon chain requires a distinct Phase 2 separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md); the stage boundary is selected, but specific chemistry, outputs, equipment, and balances remain open. It does not require a separate end-to-end ore route.
- **Nb-Ta separation:** A dedicated separation stage after shared concentration remains a candidate; no separate end-to-end ore route is selected.
- **Ga, Ge, In, and Re:** keep these as residue/byproduct recovery capabilities within aluminum, zinc, coal, and molybdenum chains, rather than creating a bespoke primary route for each.

The LFP feed families and Zr/Hf stage are selected, although their detailed recovery routes remain open. Nb-Ta and Ga/Ge/In/Re recovery remain candidates, not requirements. A dedicated route should add a distinct capability or teach a genuinely different industrial process; rarity or a long recipe chain alone is not enough.

Finishing (washing, drying, calcining, casting) is part of the relevant route, not a separate progression tree. The route catalog is a compact process vocabulary, not a mandate that every mineral use every step. A given template should keep primary/secondary/tertiary output proportions consistent across accepted feeds, while mineral identities and geological associations vary.

### Balanceability Checks

- Every polymineral deposit feed must have at least one viable baseline route and a discoverable advanced route.
- Across the mineral roster, common primary materials need multiple sources and multiple consumers; trace targets should be recoverable from residues without requiring pure primary products to be consumed at the same rate.
- For each route template, account for every output as a useful material, further recovery input, finite operating buffer, production control, or permitted disposal. Ordinary gas/fluid release consumes power and produces pollution under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md); nuclear-bearing streams retain radioactive fractions for recovery/conditioning under ADR-0068.
- Ordinary solid outputs still need a consumer, recovery path, buffer, or production control. ADR-0068 permits continuous disposal only for conditioned nuclear-cycle solids, including surplus depleted oxide, with power/material costs and slight pollution rather than a storage cap; it does not permit generic mineral-tailings or Zr/Hf overflow deletion.
- Test iron-heavy, copper-heavy, alloy-heavy, trace-recovery, CPU-without-fission, and fission-heavy demand profiles. Compatible deposits and routes must avoid unhandled permanent accumulation; the selected nuclear disposal endpoint is not proof that independent Zr/Hf demands are balanced.
- Smart routing and throughput control should be enough for stable operation. PLCs can automate the decisions, but basic balance must not depend on custom code.

### Reference Inspirations

- [GTNH Ore Generation](https://wiki.gtnewhorizons.com/wiki/Ore_Generation): deposits composed of primary, secondary, between, and sporadic minerals; use this as a model for geological variety and prospectable deposit identity, not for copying its full roster.
- [GTNH Ore Processing Concepts](https://wiki.gtnewhorizons.com/wiki/Ore_Processing_Concepts): multiple routes per mineral, route flexibility, expandable processing, and staged recovery of tertiary byproducts.
- [Angel's Refining](https://mods.factorio.com/mod/angelsrefining): a compact compound-ore set and reusable multi-step refining backbone; borrow its readability goals, not its fixed ore roster or exact balance assumptions.
- [Bob's Ores](https://mods.factorio.com/mods/Bobingabout/bobores) and [Bob's Plates](https://mods.factorio.com/mod/bobplates): broader material coverage and reusable smelting, chemical, and electrolysis capabilities.

## Product Maps

- [Chemical Products and Processes](chemical-processes.md) covers chemical reactions, reagents, chemical intermediates, petrochemistry, polymers, and process chemicals.
- [Intermediate Products](intermediate-products.md) covers alloys, batteries, semiconductor components, nuclear assemblies, and the distributed computational endgame.

## Open Decisions and Validation

- **Thorium recovery details:** Monazite is selected as the Th-232 feed family under [ADR-0060](adrs/ADR-0060-select-phase-2-monazite-thorium-feed.md), with limited access by the thorium-route unlock and no starting-region guarantee. Map owns deposit assignment and access validation. After Phase 5 coverage, detailed product and recipe design must define the recovery/output form, grade, yields, residues, and process balances, and demonstrate a credible path to the ThO2-bearing fertile material selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md); equipment and research gates remain for their owning design phases.
- Validate the candidate deposit roster, recovery associations, and pure-material inventory against the intended product-tree scope; do not treat the current candidate counts as targets.
- Reconcile deposit-to-biome assignments with the current [Map and World Generation](map-world-generation.md) design, including any locations or resource classes not represented by its committed biome model.
- Define the selected LFP brine, spodumene, phosphorite, and molybdenite recovery routes during downstream process design; Nb-Ta and Ga/Ge/In/Re exception process templates remain candidates, not selected methods. Keep the distinct Zr/Hf stage selected under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) while its chemistry and equipment remain open.
- Verify that primary, secondary, and tertiary outputs have legitimate uses or bounded handling under the balanceability rules, including the power and pollution costs for gas/fluid disposal under ADR-0035.
- Align refining-stage equipment assignments with [Infrastructure](infrastructure.md); exact route-to-machine assignments remain open.
- Validate all geological recovery associations against references before educational claims or recipes are finalized.
