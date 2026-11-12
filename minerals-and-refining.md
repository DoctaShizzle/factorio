# Minerals and Refining Design

*For: Project Prometheus*
*Status: Candidate design; catalog and routes require validation*
*Owner: Minerals and refining*
*Last updated: 2026-11-12*

Related documents: [Map and World Generation](map-world-generation.md), [Chemical Products and Processes](chemical-processes.md), and [Intermediate Products](intermediate-products.md). Related ADRs: [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md) for material and brine phase boundaries, [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) for the pre-Core polysilicon precursor, [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md) for the selected thorium fuel-cycle model, [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) for required Phase 2 semiconductor material families, [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md) for their use on the standard CPU path, [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md) for selected mineral feed families, and [ADR-0030](adrs/ADR-0030-early-access-to-semiconductor-feed-deposits.md) for limited early/mid-Phase-2 access to zircon and columbite-tantalite.

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

These are finite starter supplies of foundational materials. Secondary and tertiary recovery are later refining capabilities; listing a material here does not mean the early process exposes it.

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
| Chemical and battery feedstocks | Lithium carbonate / hydroxide, sodium chloride / sodium compounds, potassium chloride, phosphorus / phosphate, boron compounds, fluorine-bearing feedstocks, bromine compounds |

Under [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) and [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md), the standard late-Phase-2 CPU path for initial Core supply requires silicon, hafnium, tantalum, and copper material families. Their feed-family assignments are selected in [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md): quartz for metallurgical silicon, zircon for hafnium as a secondary product, columbite-tantalite for tantalum as a secondary product, and copper-bearing deposits (malachite, chalcopyrite, and pentlandite) as eligible copper sources. Limited zircon and columbite-tantalite supply must be reachable by early/mid Phase 2 under [ADR-0030](adrs/ADR-0030-early-access-to-semiconductor-feed-deposits.md); exact ore mix, extraction/separation/refining routes, grades, yields, quantities, and phase gates remain open.
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

#### Exception Candidates to Evaluate

- **Lithium from brines:** Salt/brine is reachable by early Phase 2, with basic extraction/evaporation; chlor-alkali remains Phase 2. Lithium recovery from brines, beyond the accepted basic salt/brine access, remains a source-specific route candidate. Spodumene remains a separate chemical-extraction path.
- **Nb-Ta and Zr-Hf separation:** these chemically similar element pairs may justify dedicated late separation steps after shared concentration. They do not need separate end-to-end ore routes.
- **Ga, Ge, In, and Re:** keep these as residue/byproduct recovery capabilities within aluminum, zinc, coal, and molybdenum chains, rather than creating a bespoke primary route for each.

These are candidates, not committed exceptions. A dedicated route should add a distinct capability or teach a genuinely different industrial process; rarity or a long recipe chain alone is not enough.

Finishing (washing, drying, calcining, casting) is part of the relevant route, not a separate progression tree. The route catalog is a compact process vocabulary, not a mandate that every mineral use every step. A given template should keep primary/secondary/tertiary output proportions consistent across accepted feeds, while mineral identities and geological associations vary.

### Balanceability Checks

- Every polymineral deposit feed must have at least one viable baseline route and a discoverable advanced route.
- Across the mineral roster, common primary materials need multiple sources and multiple consumers; trace targets should be recoverable from residues without requiring pure primary products to be consumed at the same rate.
- For each route template, account for every output as a useful material, an input to further recovery, a finite buffer, or a reason to throttle/pause feed. Required voiding is not an acceptable balance solution.
- Test the roster against iron-heavy, copper-heavy, alloy-heavy, and trace-recovery demand profiles. No profile should force permanent accumulation when the player selects compatible deposits and routes.
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

- Validate the candidate deposit roster, recovery associations, and pure-material inventory against the intended product-tree scope; do not treat the current candidate counts as targets.
- Reconcile deposit-to-biome assignments with the current [Map and World Generation](map-world-generation.md) design, including any locations or resource classes not represented by its committed biome model.
- Evaluate the lithium-brine, niobium-tantalum, zirconium-hafnium, and Ga/Ge/In/Re exception candidates before promoting any to required routes.
- Verify that primary, secondary, and tertiary outputs have legitimate uses or bounded handling under the balanceability rules; do not introduce required voiding.
- Align refining-stage equipment ownership once the referenced machine-system design has been recovered or its replacement owner is agreed.
- Validate all geological recovery associations against references before educational claims or recipes are finalized.

No separate dated decision log was present in this document's current draft. Catalog revisions remain candidates here; this migration did not invent decisions or extract unsupported ADRs.
