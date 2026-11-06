# Plan: Exhaustive Product Catalog, Recipe Tree, Machine List, Research Roster

*Full design pass for Project Prometheus modpack.*

## The Four Deliverables

This session produces four interconnected deliverables that must be designed together because every decision in one cascades into the others.

---

## 1. Exhaustive Product Catalog

### What Exists (Starting Point)

**Mineral Deposits — ~36 types, mostly committed:**
- Tier 1 surface: hematite, malachite, coal, quartz, native sulfur, calcite, dolomite, gypsum ✅ Committed
- Tier 2 underground: magnetite, chalcopyrite, gold, sphalerite, galena, pentlandite, bauxite, chromite, cassiterite, scheelite, pyrolusite, zircon, graphite, trona, brine, apatite, spodumene, halite, bastnaesite, uraninite ✅ ~21 types
- Tier 3 polymineral: VMS, BIF, porphyry Cu-Mo, REE pegmatite, layered mafic, evaporite basin, orogenic gold ✅ 7 types
- Biome mapping: Sedimentary basin, Shield region, Mountain range, Volcanic zone, Coastal/shelf hybrid ✅ Committed

**Pure Material Inventory — ~50 candidates across 7 groups:**
- Base/structural: iron, copper, aluminum, alumina, metallurgical silicon, carbon, sulfur, lime, silica, gypsum
- Common alloy/process metals: zinc, lead, nickel, cobalt, chromium, tin, manganese, titanium, vanadium, magnesium
- Precious/catalyst: gold, silver, platinum, palladium, rhodium
- Specialty/semiconductor: gallium, germanium, indium, cadmium, tungsten, molybdenum, rhenium, niobium, tantalum, beryllium, zirconium, hafnium
- Battery/feedstocks: lithium carbonate/hydroxide, sodium/potassium chlorides, phosphorus/boron compounds, fluorine/bromine feeds
- Rare/radioactive/trace: uranium, thorium, cerium, lanthanum, neodymium, yttrium, selenium, tellurium, arsenic
- Other: CO₂, water

**Chemical Products — ~45 reaction candidates across 10 families:**
- Core chains (committed): sulfuric acid, chlor-alkali, plastics/PE, cement/lime ✅ Committed
- Later candidates: ammonia, nitric acid, methanol, Fischer-Tropsch, cumene, Kroll Ti, coal gasification, coal tar fractionation
- Semiconductor chemicals: trichlorosilane, photoresist, WF₆, SF₆, NF₃
- Battery/fusion: lithium breeder, deuterium, tritium

**Intermediate Products — ~40 candidates:**
- Metallurgy/structural: pig iron, DRI, carbon steel, stainless, Nb-microalloyed steel, tool steel, Invar, titanium alloy, aluminum alloy
- Phase 2 bridge (5 committed): electronic-grade polysilicon, Nb₃Sn wire, HfO₂ dielectric, D₂O, cryogenic Ar/N₂ mixture
- Semiconductors: metallurgical Si, e-grade poly-Si, silicon wafers, photoresist, high-k dielectrics, Cu/Ta interconnect, tantalum capacitors, packaged ICs
- Nuclear: U-oxide fuel, Th-cycle fuel, Zr-cladding, Hafnium absorber, B₄C absorber, reactor steel, Li breeder blanket, W armor tiles, Nb3Sn conductors
- Batteries: Li cathode precursor, Co/Mn cathode compounds, graphite anode, battery cells/packs
- Computing endgame: processor clusters, supercomputer facilities, simulation nodes, planetary research centers

### What Needs to Be Invented / Filled

1. **Refined outputs catalog** — clean list of what comes out of processing stages with their *source* and *consumer*. Every pure material needs an input-from and output-to chain. Currently ~50 candidates; need to select which are mandatory vs. situational.
2. **Phase 2 bridge products** — 5 committed, but we need to verify: the "Low-Temperature Physics Facility" is mentioned in endgame-vision.md while research-progression.md says "Quantum States Laboratory". Need to reconcile naming and confirm the 6th domain lab (Reaction Dynamics Facility has less specific material requirements).
3. **Intermediate products catalog** — the current list has ~40 candidates but lacks:
   - Specific alloy compositions (which alloys for which tiers?)
   - Catalyst materials (Pd, Pt, Raney nickel, etc.)
   - Acid/reagent inventory (HCl, H₂SO₄, HNO₃, HF, NH₃, NaOH, etc.) — these are mostly in the chemistry doc but need a consolidated "pure chemical" list with recipes
   - Semiconductor process chemicals beyond the basics
   - Cleanroom-grade materials (spin coat precursors, etchant solutions)
4. **End products** — Phase 3/4 components that actually feed the Core or represent final capabilities:
   - Planetary Simulation Core assembly components
   - Memory archive modules
   - Compute campus nodes
   - Research facility infrastructure items
   - Hawking Radiation Engine components (precision optics, containment vessels)
5. **Consolidated material inventory** — currently split across 3 documents with overlap and gaps:
   - Some pure materials that should exist (e.g., oxygen, hydrogen as separate process gases)
   - Missing reagent compounds (ammonia solution, hydrochloric acid, phosphoric acid)
   - Missing catalyst materials

### Assessment: Ready to Invent ✅

The mineral catalog is ~90% done. The main gap is consolidating pure materials with clear I/O chains, then inventing the intermediate/end product layers that connect mining → refining → chemistry → research → endgame infrastructure.

---

## 2. Exhaustive Recipe Tree

### What Exists

**~45 chemical reactions/processes** in the provisional registry, including:
- Core sulfuric acid route (SO₂ → SO₃ → H₂SO₄ via contact process)
- Chlor-alkali electrolysis (brine → Cl₂ + NaOH + H₂)
- Bayer alumina refining, Hall-Heroult electrolysis
- Kroll titanium (TiCl₄ + Mg → Ti + MgCl₂)
- Polysilicon deposition (trichlorosilane + H₂ → Si)
- All the petrochemical chains (ethylene, PVC, phenol, acrylonitrile, Bakelite)
- Ostwald nitric acid chain (NH₃ → NO → NO₂ → HNO₃)

**Provisional recipe pathways for:**
- Metallurgy: 9 pathway sketches (pig iron → DRI → steel → alloys)
- Batteries: 5 pathway sketches
- Semiconductors: 6 pathway sketches
- Nuclear: 8 pathway sketches
- Computing endgame: 4 pathway sketches

### What Needs to Be Invented / Filled

1. **Complete recipe tree** — every product in the catalog needs a specific recipe (inputs → output → machine). Currently ~45 reaction candidates but no one coherent list showing what recipes exist for what products.
2. **Recipe-to-machine mapping** — each recipe must be assigned to a machine family from the 16-stage catalog (crusher, flotation cell, roaster, furnace, electrolyzer, cleanroom fab, etc.)
3. **Vanilla connection points** — where do conventional Factorio recipes integrate? What vanilla items serve as Phase 1 inputs? This needs explicit mapping.
4. **Multi-route products** — which intermediates have multiple viable processes (creating meaningful tradeoffs)? The design says "not all need alternatives" but we need to identify the ~8-12 products that do.
5. **Coproduct handling** — every recipe with coproducts needs documented sinks (use, convert path, or buffer).

### Assessment: Need to Invent ✅

We have raw material for a complete tree but it's scattered across 3 documents. The main work is consolidation into one coherent list + inventing recipes for intermediates that only have pathway sketches (metallurgy, computing endgame).

---

## 3. Exhaustive Machine/Building List + Ingredients

### What Exists

**16 industrial stages:**
- Extraction → Preparation → Mechanical concentration → Flotation → Thermal treatment
- Smelting/reduction → Chemical extraction → Solution processing → Electrochemical recovery → Product finishing
- Polymer processing → Semiconductor fabrication → Nuclear fuel fabrication
- Power transmission → Fluid transport → Automation

**Machine tiers (MTier 1-5):** Each tier built from progressively better materials, with capability gating.

**6 domain research labs:** Superconductivity Research Lab, Plasma Confinement Facility, Nanofabrication Laboratory, Isotope Separation & Calibration Lab, Reaction Dynamics Facility, Quantum States Laboratory — each with Phase 2 material prerequisites.

**Planetary Simulation Core + peripheral facilities:** Memory archives, compute campuses, research/observation facilities.

### What Needs to Be Invented / Filled

1. **Specific machine names and build recipes** — currently we have families but no concrete list of what machines actually exist in-game with their construction ingredients.
2. **MTier-specific build recipes** — each MTier needs explicit material requirements (e.g., "Steel Assembler Tier 2: 50 steel plates + 10 advanced circuits + 5 plastic stacks").
3. **Domain lab build recipes** — specific items needed to construct each of the 6 labs.
4. **Core/peripheral facility build recipes** — Planetary Simulation Core components, compute campus nodes, memory archive modules.
5. **Vanilla machine mappings** — which vanilla machines are reused (smelter, inserter, transport belt)? What is fully replaced vs. extended?
6. **Machine capabilities matrix** — what each machine can do (recipes it supports) vs. its material tier requirement.

### Assessment: Need to Invent ✅

The framework is solid but the concrete build recipes don't exist yet. We need ~80 specific machines (within the 50-80 performance budget), each with a construction recipe using materials from the product catalog.

---

## 4. Exhaustive Research List + Tech Tree

### What Exists

**Progression structure:**
- Phase 1: Conventional science packs (~30-40h, ~300 techs estimated)
- Phase 2: Hybrid conventional + domain packs (6 domains × 7 tiers each, ~180-200h)
- Phase 3: Simulation-gated (Core L1/L2/L3, ~70-100h)

**Six domains (locked):** Superconductivity, Plasma Confinement, Nanofabrication, Isotope Separation/Particle Physics, Reaction Dynamics, Quantum States.

**Domain pack tiers:** T1 → T2a → T2b1 → T2b2 → T3a → T3b → T3c (7 tiers per domain).

**Core milestones:**
- Construction: All 6 domains at T2a + convergence item (~42 packs)
- Level 2: All 6 domains at T2b2 (~1,320 packs)
- Level 3: All 6 domains at T3c (~7,920+ packs)

**Breakthrough categories per Core level:** Planetary Model → Information-Based Model → General-Physics Model.

### What Needs to Be Invented / Filled

1. **Complete technology roster (~800-1500 techs):** Currently zero committed tech names. We need:
   - Phase 1 conventional techs (mining, refining, basic chemistry, power generation)
   - Phase 2 bridge techs (domain lab construction, intermediate processing, alloy production)
   - Phase 3 simulation-gated techs (cleanroom, semiconductor, deep nuclear, endgame)
   - Military/defense tech chains
   - Logistics/belt/train evolution techs
   - Power transmission techs

2. **Tech classification matrix:** Every tech needs: phase, conventional pack requirements, domain pack(s) requirement, simulation finding requirement, and "what it unlocks" (recipe access).

3. **Vanilla tech mapping:** Which vanilla techs are replaced vs. extended? What vanilla items persist into Prometheus?

4. **Research dependency graph:** Order constraints within each phase (e.g., you can't research Nb₃Sn wire before you have niobium refining).

### Assessment: Major Invention Needed ✅

This is the biggest gap. The structure is locked but zero tech names are committed. We need to invent a complete technology tree from scratch, grounded in the material pipeline that's already mostly defined.

---

---

## Current Design Progression

Phase A is complete. The remaining phases cascade downward from those decisions.

```
✅ Phase A: Complete Facility Inventory + Endgame Anchors → DECIDED
    ↓
Phase B: Work Down Through Domain Packs + Infrastructure Needs ← bridges, tiers, convergence item composition
    ↓
Phase C: Machine List ~70 types with build ingredients
    ↓
Phase D: Fill the Base ← refined materials selection, reagents, intermediates
    ↓
Phase E: Recipe Tree ← connects all materials to machines
    ↓
Phase F: Research Roster ← gates access to recipes + machines
```

### Phase A — Completed (What We Have)

| Deliverable | Status | Linked Docs |
|-------------|--------|-------------|
| **Complete Facility Inventory** (~120 unique buildings/entities, 18 categories) | ✅ COMPLETE | [infrastructure.md](infrastructure.md) |
| **Planetary Simulation Core components** (4 physical assemblies + satellites + 3 tiers) | ✅ COMPLETE | endgame-vision.md |
| **Unified Metrology Reference Array** (convergence item, 6 physics zones) | ✅ COMPLETE | intermediate-products.md |
| **Hawking Radiation Engine components** (5 sub-components) | ✅ COMPLETE | endgame-vision.md |
| **Phase 2 bridge products** (6 materials including rhenium-catalyst powder) | ✅ COMPLETE | research-progression.md + intermediate-products.md |

### Phase A1 — Complete Facility Inventory

The full inventory has moved to [infrastructure.md](infrastructure.md). It contains ~120 unique infrastructure types across 18 categories, all multi-tiered where capability changes matter (not just speed):

| Category | Count | Phase Range | Key Capability Changes Per Tier |
|----------|-------|-------------|--------------------------------|
| Extraction & Mining | 6 | Phases 1–3 | Drill yield/scope; prospect gating for deeper deposits |
| Ore Preparation & Concentration | 10 | Phases 1–3 | Mill throughput/media auto-replenishment; magnetic field strength |
| Thermal Processing | 7 | Phases 1–3 | Roaster gas capture efficiency; kiln temp control precision |
| Smelting & Reduction | 7 | Phases 1–4 | EAF voltage range, electrode auto-feed, power capacity |
| Chemical Extraction & Reactors | 6 | Phases 1–3 | Pressure rating; material compatibility range |
| Solution Processing & Separation | 6 | Phases 2–3 | Crystallizer mode (cooling → evaporator → vacuum auto-discharge) |
| Electrochemical Processing | 4 | Phases 2–4 | Electrode area + auto-swap; membrane quality for electrolysis |
| Polymer & Composite Processing | 6 | Phases 2–4 | Batch → continuous reactor; extruder precision |
| Semiconductor Fabrication | 12 | Phases 3–4 | Each step is multi-tier; cleanroom quality scales across all |
| Nuclear Fuel & Component Fabrication | 13 | Phases 2–4+ | Manual → semi-auto → fully automated production lines |
| Power Generation + Transmission | 20 (14 gen + 6 grid) | Phases 1–Endgame | Steam engine tiers most impactful early; reactors scale power output with tier |
| Military Infrastructure | 8 weapons + 5 support | Phases 1–Endgame | Turret caliber/range/damage; support machine throughput/precision |
| Logistics & Material Handling | 10 + infrastructure | Phases 1–4+ | Belt speed/capacity; freight terminal automation level |
| Fluid Handling & Transport | 6 | Phases 1–4 | Pipe pressure/temp tolerance, flow rate per tier |
| Waste Processing & Loopback | 4 | Phases 2–3 | Recovery efficiency with tier; enables circular economy |
| Research & Measurement Infrastructure | 10 | Phases 2–3 | Core L2/L3 upgrades; satellite processing/storage capacity |
| Automation & Control Systems | 5 | Phases 1–4+ | PLC logic complexity (timer → PID → neural-assisted optimization) |

All construction materials listed in infrastructure.md are tentative — they trace to our catalog but exact recipes come in Phase C when we have the refined materials and intermediates selected. **Every category forces specific material requirements** that determine which candidates from ~50 refined materials are actually mandatory.

### Phase B — Next: Domain Packs + Infrastructure Needs

| # | Decision | What it determines |
|---|---------|---------------------|
| 4 | The 6 bridge materials → specific Phase 2 intermediates needed to produce each one | Refined material selection, reagent chemicals |
| 5 | Complete T1→T3c recipe chains for all domain packs | All Phase 2 intermediates, convergence item composition |
| 6 | Convergence item composition (one pack from each of 6 domains) | End products, intermediate synthesis routes |
| 7 | Power infrastructure build recipes | Refinement candidates, intermediate products, MTier 3-4 alloys |
| 8 | Military infrastructure build recipes | Refinement candidates (tungsten), chemical reagents (HNO₃), MTier 3-5 alloys |
| 9 | Logistics/Construction infrastructure build recipes | Advanced electronics, semiconductor precursors |

> All 14 generator types, 6 grid infrastructure types, 8+5 military buildings, and 10+ logistics buildings are cataloged in [infrastructure.md](infrastructure.md). Phase B work is mapping **which specific materials** from each category feed into the Phase 2 bridge products and domain pack chains (decisions 4–6), then using those to decide which of the ~50 refined material candidates are actually mandatory.

### Phase D — Fill the Base: Refined Materials & Chemicals

| # | Decision | Why last? |
|---|---------|-----------|
| 13 | Final refined material selection (~35 from ~50 candidates) | Now we know which are required for Phase 2 bridge, domain labs, machine construction, power/military/logistics infrastructure — cull the rest. |
| 14 | Reagent/acid inventory (HCl, NH₃, HNO₃, HF, etc.) | Only include reagents that connect to existing chains from Phases A-C decisions, not invent new ones for their own sake. |
| 15 | Intermediate products catalog (alloys, catalysts, semiconductor precursors) | Ground these in bridge materials already selected plus infrastructure needs (military alloys, power conductor materials, belt upgrade components). |

### Phase E — Recipe Tree

All material recipes organized by pipeline stage. Every item has explicit input→output→machine assignment. Must trace every item back to vanilla starting resources (iron ore, copper ore, coal, stone). Multi-route products identified (~8-12 with meaningful tradeoffs). Coproduct handling documented for each recipe.

### Phase F — Research Roster

Complete tech tree from ~800-1500 technologies: phase assignment, pack requirements, what each unlocks (recipes/machines), simulation finding requirements. Dependency graph within each phase. Vanilla tech mapping (which are replaced vs. extended).

## Deliverable Format — Updated for All Layers

Each deliverable should be formatted for immediate implementation reference:

### Product Catalog
| Pipeline Stage | Item Name | Input Source (recipe) | Output Consumer (recipes using this item) | Phase Available | Multi-Route? | Notes |
|---|---|---|---|---|---|---|

### Recipe Tree
| Output Item | Input Items (qty) | Machine Type | Phase/Tier | Recipe Duration | Coproducts | Notes |

### Machine List
| Machine Name | Tier | Build Ingredients | Supported Recipes | Capability Gate | Phase Available |

### Research Roster
| Tech Name | Phase | Packs Required | Unlocks (recipes/machines) | Simulation Finding | Notes |

---

## Updated Estimated Scope

| Deliverable | Approx. Items to Define | Complexity | Notes |
|-------------|------------------------|------------|-------|
| Product Catalog | ~35 refined materials + ~25 reagent chemicals + ~40 intermediates + ~15 end products = **~115 items** | Medium — mostly selection/organization of existing candidates + inventing gaps | Includes infrastructure-specific items (reactor components, conductor materials, ammo compounds) |
| Recipe Tree | **~200-250 recipes** (connecting the catalog) | High — must trace every item back to vanilla, respect 50-60 intermediate cap | Power/military/logistics add ~30-40 recipes to the base chain |
| Machine List | **~70 machines** (within performance budget) | Medium — framework exists, need specific build recipes and capability matrices | Includes: domain labs (6), Core peripherals (~10), power generators (8+), transmission equipment (5), military turrets (4-6), logistics infrastructure (~15), belt/bot variants (10+), core industrial machines (20+) |
| Research Roster | **~800-1200 techs** (estimated range) | Very High — must invent complete roster, but many will be variants of existing concepts | Phase 1: ~300 conventional. Phase 2: ~400 hybrid. Phase 3: ~500 simulation-gated |

## Constraints & Guardrails

- **No product without a consumer.** Every item must feed into at least one other recipe.
- **No intermediate with fewer than 2 consumers.** If it only feeds one thing, question whether it needs to exist as an intermediate (could be a direct output).
- **Multi-route products are the exception, not the rule.** Only ~8-12 intermediates get alternative processes — those that create meaningful tradeoffs.
- **Phase 2 materials must connect to domain labs.** Every Phase 2 bridge material gates exactly one domain research facility.
- **End products must connect to Core infrastructure.** Items that don't feed into the simulation network or represent progression milestones should not be in the end product category.
- **Everything traces back to vanilla.** No item tree starts from "nothing" — every chain connects to at least one vanilla starting resource (iron ore, copper ore, coal, stone).
- **Infrastructure materials are mandatory, not optional.** Power generators, military turrets, logistics infrastructure each require specific Phase 2+ intermediates. These aren't add-on content — they're foundational to the player's progression path.

## Open Decisions Within Scope of This Session

These decisions MUST be made during this session and will cascade into all deliverables:

1. **Which 30-35 refined materials make the mandatory catalog?** (~50 candidates to select from)
2. **Which ~8-12 intermediates get multiple viable processes?** (creating meaningful tradeoffs)
3. **What specific items build the Planetary Simulation Core?** (convergence item + Phase 3 infrastructure components)
4. **What's the final Hawking Radiation Engine component list?** (precision optics, containment vessel, thermal converter, etc.)
5. **Which vanilla items persist into Prometheus phase as-is vs. get enhanced?** (affects recipe and research design)
6. **Should nuclear ammo exist in the military chain?** (requires U/Pu fuel chain — already optional for fission)
7. **Final battery chemistry selection** (design doc says "avoid every formulation" — which specific chemistries?)
8. **Tungsten AP ammo: necessary or over-cost?** (forces tungsten through full Phase 2 refining chain; confirm gameplay value vs. constraint cost)
9. **Power infrastructure: U-235 vs Pu-239 path** (single enriched-fuel with optional recycling, or two separate fuel chains?)
10. **Logistics/automation: which tiers require Phase 2/3 materials?** (do logistics bots need domain pack knowledge? At what point do construction bots advance beyond Phase 1 inputs?)
