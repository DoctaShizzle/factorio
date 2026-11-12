# Project Prometheus — Comparative Gap Analysis Report

*Date: 2026-11-11*  
*Purpose: Compare Prometheus design scope against GregTech, Bob's/Angels, and Space Exploration; identify quantitative and qualitative gaps in intermediate products, infrastructure, personal items, and tools.*

---

## Executive Summary

Project Prometheus has **strong design foundations** with a coherent philosophy (knowledge before capability), well-scoped progression (three phases), and clear boundaries. However, several quantitative gaps compared to GTNH, Bob's/Angels, and Space Exploration remain in machine count, intermediate product density, infrastructure variety, and personal/specialized items that affect the mod's depth-per-hour ratio.

---

## 1. Quantitative Comparison Matrix

| Metric | Project Prometheus | GregTech (GTNH) | Bob's + Angel's | Space Exploration |
|--------|-------------------|-------------------|-----------------|-------------------|
| **Unique machine types** | ~70–80 (infrastructure.md §1–18) | ~450+ machines | ~120–130 machines | ~180–200 buildings |
| **Machine tiers total** | ~5 per type × 70 = ~350 tiered builds | Variable, many types have 5+ tiers | ~3–4 tiers × 120 = ~400 | ~2–3 tiers per building |
| **Pure raw materials** | ~38 of ~50 candidates (with infrastructure paths) | ~200+ refined materials | ~80 refined materials | ~60 refined materials |
| **Intermediate products** | ~40 candidates + 6 bridge products + endgame components | ~700+ intermediates | ~100–120 intermediates | ~50–60 intermediates |
| **Chemical reactions** | ~45 reaction candidates (core chains + later) | ~3500+ named reactions | ~150 named reactions | ~80 named reactions |
| **Technology count** | ~800–1500 planned | ~2000+ techs | ~400 techs | ~600 techs |
| **Research domains / alternative paths** | 6 domain labs + conventional hybrid | Multi-route for nearly everything | Single route per product with quality variants | Domain-locked progression (minimal choice) |

### Key Takeaways

- **Machine count is well-scoped at ~70–80 types.** This sits comfortably between Bob's/Angels (~120) and Space Exploration (~180). It aligns with Prometheus's stated target of 50–80 performance budget.
- **Pure materials are slightly under-indexed** vs. GregTech but well-matched to Space Exploration's scale (~60). The 38 verified + ~12 candidate materials is adequate for Phase 1–2 bridge.
- **Intermediate products need the most work** — only ~40 candidates with incomplete mapping to downstream consumers. GTNH has ~700; Bob's/Angels has ~120. For a mod targeting 300+ hours, this density gap is significant.

---

## 2. Domain-by-Domain Gap Analysis

### 2A: Minerals and Refining (infrastructure gaps)

**Current state in Prometheus:**
- ~36 deposit types across 3 tiers
- Mineral recovery matrix with primary/secondary/tertiary assignments
- 5 process templates + 3 dedicated exceptions
- ~38 materials verified with infrastructure consumption paths

**Gaps vs. reference mods:**

| Gap | Severity | Reference Mod Comparison | Recommendation |
|-----|----------|------------------------|----------------|
| **Fewer deposit types than GTNH (~36 vs ~200)** | Medium-Low | GTNH's density comes from many ore-bearing rocks and trace associations, not just deposit count. Prometheus's multi-tiers per deposit compensate partially | Ensure each of the 36 deposits has at least 2 viable recovery routes (baseline + advanced) to match GTNH's decision space without expanding the roster |
| **No dedicated "residue/recovery" tier as a distinct infrastructure capability** | Medium | Angel's has a full late-game residue processing layer; Prometheus mentions tailings re-processing (§16) but it's underdeveloped | Expand §16 Waste Processing from 4 machines to ~8: add ion-exchange skid, precious-metal electrowinning circuit, acid regeneration unit, and activated-carbon purification column. This adds recovery depth without new ore types |
| **Missing "flux/refractory material" category** | Medium | Bob's has limestone/quicklime/silica sand as construction flux materials for smelting; Prometheus lists them in minerals but not as distinct intermediate products with recipes | Create a "Refractory & Flux Materials" intermediate sub-category: firebrick clay, silicate refractory bricks, magnesia-carbon bricks, aluminum-oxide ceramic pellets. Each needs its own production chain from raw minerals |
| **No "gas product" category** | Low-Medium | GTNH tracks industrial gases (H₂, O₂, N₂, Cl₂, HCl, SO₂, CO, CO₂) as distinct intermediates with infrastructure for compression/storage. Prometheus mentions some in chemistry docs but not as a structured catalog | Formalize gas products in intermediate-products.md: compressed hydrogen, liquid oxygen, nitrogen feedstock, chlorine gas cylinders, SO₂ storage tank contents. These are critical inputs to later phases |

### 2B: Intermediate Products (largest gap)

**Current state in Prometheus:**
- ~40 intermediate candidates across metallurgy, batteries, semiconductors, nuclear
- 6 bridge products committed
- Former Phase A2 endgame assembly proposals are preserved as unapproved candidate history in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md); current facility ownership is in [Endgame Vision](endgame-vision.md) and [Infrastructure](infrastructure.md)

**Gaps vs. reference mods:**

| Gap | Severity | Reference Mod Comparison | Recommendation |
|-----|----------|------------------------|----------------|
| **No alloy catalog beyond 9 candidates** | High | Bob's has ~30+ distinct alloys (not just compositional variants but *process-variant* ones: e.g., different stainless grades, tool steels per use case). GTNH has dedicated "steel variant" trees with carbon content and trace elements affecting properties. Prometheus has only 9 alloy candidates that are mostly compositional | Expand to ~20 alloys. Add at minimum: maraging steel (Ni-Mo for high strength), Hastelloy/Nickel-625 analogs (corrosion-resistant reactors), Inconel variants (high-temp turbines), duplex stainless (austenitic-ferritic), and 3–4 tool steel grades (HSS, D2, M2). Each needs a distinct intermediate step from standard steel |
| **No "catalyst materials" category** | High | GTNH has ~50 catalyst types (Pt-group on various supports, zeolites, supported nickel, copper-chromium, etc.) as a critical game layer. Bob's/Angels has catalytic converters and catalyst beds. Prometheus mentions "catalyst material input per recipe" for the Fixed-Bed Reactor but no catalog | Create a "Catalyst Materials" intermediate sub-category: platinum/alumina catalyst pellets, palladium/carbon catalyst, supported nickel catalyst, vanadium pentoxide catalyst, zeolite molecular sieves, activated carbon (treated). These are **consumable/replaceable** items that gate specific chemical processes |
| **No "refractory / ceramic materials" category** | Medium | Angel's has a massive ceramic/refractory sub-system. GTNH separates ceramics from structural products. Prometheus mentions HfO₂, alumina ceramics in passing but no dedicated product line | Create: alumina ceramic pellets, silicon-carborundum (SiC) refractory bricks, zirconia insulating tiles, fused-silica glass sheets, mullite fiber panels. These feed into machine construction tiers and cleanroom infrastructure |
| **No "precision/optical materials" category** | Medium-Low | GTNH has precision optical components (quartz optics, UV-grade fused silica, germanium lenses) as high-tier items. Prometheus's former endgame proposal mentions "photolithography glass optics panels"; the proposal is preserved in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md), but there is no dedicated catalog | Add: quartz optical lens blanks, sapphire window panes, IR-transmitting germanium plates, UV-grade fused silica sheets. These are endgame materials for cleanroom and simulation infrastructure |
| **Battery chemistry too sparse** | Low-Medium | Bob's has Li-ion, NiMH, Lead-acid variants. Prometheus only lists "lithium cathode precursor" and generic battery cells | Add: lithium cobalt oxide cathode powder, graphite anode flakes (sintered), solid polymer electrolyte sheets, nickel-cobalt-aluminum (NCA) cathode blend. This creates battery diversity without exploding count |
| **No "fiber / composite precursors"** | Medium | GTNH has carbon fiber, fiberglass, aramid, and Kevlar precursors as distinct product lines. Prometheus mentions polymer processing (§15) but no intermediate catalog | Add: carbon fiber tows (PAN-derived), E-glass fiber bundles, epoxy resin laminates, aramid fiber sheets. These feed into composite infrastructure construction tiers |

**Total recommended additions for intermediates: ~30 new items.** This brings the total from ~40 to ~70, which is still well below GTNH's 700+ but matches the depth of Bob's/Angels (~120) for a more manageable scope.

### 2C: Infrastructure / Buildable Items (personal items, utilities)

**Current state in Prometheus:**
- ~100–120 unique building types across 18 categories
- Multi-tiered with capability changes per tier
- Materials consumption index mapped for all categories

**Gaps vs. reference mods:**

| Gap | Severity | Reference Mod Comparison | Recommendation |
|-----|----------|------------------------|----------------|
| **No "personal/specialized tool" category** | High | GTNH has wrenches, wirecutters, circuit programmers, multimeters, welding helmets, hard hats, radiation dosimeters as personal items with functional effects. Bob's/Angels have engineering tools (blueprint books, precision calipers). Prometheus completely lacks this dimension | Add a "Personal & Engineering Tools" section to intermediate-products.md: ~8–10 tools. Minimum set: **engineering measurement caliper** (precision alignment during assembly), **radiation dosimeter** (fission safety UI element), **welding helmet** (EAF/high-temp operation), **multimeter** (circuit debugging for automation), **calibration reference kit** (for domain lab operation), **pressure testing gauge**, **insulation resistance tester**, **thermal imaging camera**. These are crafted items that enable *correct* operation of machinery or provide UI feedback |
| **No "safety / environmental" category** | Medium | GTNH has blast doors, fume hoods, containment walls, spill booms. Angel's has pollution scrubbers as dedicated buildings. Prometheus mentions pollution only in military-pressure context | Add ~4–5 safety/environmental buildings: **fume extraction hood** (reduces local pollution for chemical buildings), **acid-resistant containment flooring tiles** (prevents fluid spread from leaks), **explosion vent panels** (safety relief for pressure vessels), **dust suppression system** (particulate control for ore processing) |
| **No "sample / collection" infrastructure** | Low-Medium | GTNH has core sample drills, rock chippings, mineral samplers. Space Exploration has planetary survey equipment. Prometheus mentions prospect scanner but no sampling chain | Add: **Core Sample Drill** (extracts subsurface core samples for analysis → informs prospecting), **mineral specimen display cabinet** (aesthetic/QoL — lets player catalog recovered specimens), **field spectrometer** (portable mineral ID tool) |
| **Insulation materials missing from construction** | Medium-Low | GTNH has thermal insulation, cryogenic insulation, acoustic insulation as distinct construction products. Prometheus mentions "cryogenic insulation panels" in assembly chains but no standalone product with its own production chain | Create a standalone **Thermal & Cryogenic Insulation Materials** category: aerogel blanket rolls (general high-temp insulation), liquid-nitrogen-compatible insulation panels, molecular sieve desiccant beds, vacuum-insulated panel cores. Each needs its own production from existing intermediates |
| **No "sealing / gasket materials" catalog** | Medium | GTNH has rubber compounds, PTFE tape, copper gaskets, compressed fiber gaskets as distinct items that gate pipe/fluid connections. Prometheus mentions these in passing but they're not explicit products | Add: **PTFE sealing tape rolls**, **copper gasket blanks**, **graphite-compressed gasket sheets**, **FKM elastomer seal kits** (high-temp/corrosion). These are small-item consumables that gate fluid infrastructure quality |
| **No "lubricant / process oil" category** | Medium | GTNH has hydraulic fluid, machine oil, lubricant (white/black), emulsion oils as critical items. Bob's/Angels have gear boxes and grease. Prometheus mentions "hydraulic piston assemblies" in construction but no product chain | Add: **hydraulic fluid** (from refined petroleum + additives → powers high-tier machines), **industrial lubricant** (reduces wear for grinding/ball mills), **cooling process oil** (for transformer/EAF cooling), **synthetic gear oil** (high-load bearing lubrication) |

**Total recommended additions for infrastructure/buildables: ~25 new items. Personal/specialized tools: ~10.**

### 2D: Research / Technology Structure

**Current state in Prometheus:**
- Six domains × 7 tiers = 42 domain pack variants (distinct items with recipes)
- Three-phase progression (conventional → hybrid → simulation-gated)
- Core levels L1/L2/L3 with specific pack requirements

**Gaps vs. reference mods:**

| Gap | Severity | Reference Mod Comparison | Recommendation |
|-----|----------|------------------------|----------------|
| **Research items are only packs — no "data / dataset" layer** | Medium-Low | GTNH has research items that are *physical* (magnetic tapes, paper tape rolls, data chips) with multiple quality variants. Prometheus's domain packs are well-structured but the T3a→T3c transition to simulation-produced items could use more granularity | Add 2–3 intermediate research item tiers between T2b2 and Core activation: **Raw Measurement Logs** (unprocessed lab data → calibration hub), **Cross-Domain Analysis Report** (synthesized findings from multiple labs), **Simulation Validation Dataset** (Core L1 output that gates higher-level research) |
| **No "manual / technical documentation" research item category** | Medium | GTNH has engineering manuals, process handbooks, and scientific journals as research items. Bob's/Angels have reference books. Prometheus mentions handbook in design but not as a game mechanic | Add: **Engineering Reference Manual** (unlocks machine tier recipes), **Process Engineering Handbook** (reveals alternative production routes), **Scientific Journal Archive Access** (enables simulation model refinement) |
| **No "scrap / recycling" research pathway** | Low-Medium | GTNH allows reverse-engineering items back to blueprints/research. Prometheus has no mechanism for recovering or learning from decommissioned infrastructure | Consider adding: **Disassembled Component Analysis** (research item produced by analyzing scrapped machinery → unlocks basic recipes for that machine type). This supports the "equilibrium over disposal" pillar |

---

## 3. Critical Gap Prioritization

### Must-Add Before Phase C (Blocking)

| # | Gap | Impact | Items to Add |
|---|-----|--------|--------------|
| **1** | Catalyst materials catalog | Blocks all chemical processing — every reactor needs a catalyst input | ~8 items: Pt/alumina, Pd/carbon, Ni/supported, V₂O₅, zeolite, activated carbon, Raney nickel, copper-chromium |
| **2** | Personal engineering tools | No tool dimension for construction/operation; no way to "handle" infrastructure correctly | ~10 items: measurement caliper, dosimeter, welding helmet, multimeter, calibration kit, pressure gauge, insulation tester, thermal camera |
| **3** | Insulation/refractory materials | Machine tiers reference these but they don't exist as crafted intermediates | ~8 items: aerogel blankets, cryo-insulation panels, alumina pellets, SiC bricks, zirconia tiles, fused-silica sheets, mullite fiber |
| **4** | Gasket/sealing materials | Every fluid pipeline needs seals; missing product line blocks Phase 2+ infrastructure | ~4 items: PTFE tape, copper gaskets, graphite sheets, FKM seal kits |

### Should-Add Before Phase D (Important but Not Blocking)

| # | Gap | Impact | Items to Add |
|---|-----|--------|--------------|
| **5** | Alloy catalog expansion | 9 alloys is too few for a 300-hour mod; needs material differentiation | ~10 items: maraging steel, Hastelloy-analogs, Inconel, duplex stainless, 4 tool steel grades |
| **6** | Fiber/composite precursors | Missing materials for Phase 3–4 infrastructure construction | ~5 items: carbon fiber tows, E-glass bundles, epoxy laminates, aramid sheets |
| **7** | Safety/environmental buildings | No pollution control beyond military pressure; misses "equilibrium" pillar | ~4 buildings: fume hood, containment flooring, explosion vents, dust suppression |
| **8** | Gas products category | Critical inputs for later phases not tracked as intermediate products | ~6 items: compressed H₂, liquid O₂, N₂ feedstock, Cl₂ gas cylinders, SO₂ storage |

### Nice-to-Have (Can Defer)

| # | Gap | Impact | Items to Add |
|---|-----|--------|--------------|
| **9** | Precision/optical materials | Only needed for Phase 3+ cleanroom and simulation | ~4 items: quartz lens blanks, sapphire windows, Ge plates, UV silica sheets |
| **10** | Battery chemistry diversity | Existing battery products are sufficient; variants add depth | ~3–4 items: LCO cathode powder, NCA blend, graphite flakes, solid polymer electrolyte |
| **11** | Sample/collection infrastructure | Mostly QoL/aesthetic; doesn't block progression | ~3 items: core sample drill, specimen cabinet, field spectrometer |

---

## 4. Overall Recommendations

### Structural Recommendations

1. **The Phase 2 bridge product list (6 items) is well-scoped.** These are the keystone materials connecting Phase 1 to Phase 3. Don't add more bridge products — instead, expand the *infrastructure that consumes them* (more categories use Nb₃Sn wire than currently documented).

2. **The ~70–80 machine count is appropriate for Prometheus's scope.** It sits between Bob's/Angels and Space Exploration. The key differentiator is *tier depth*, not raw count — which Prometheus handles well with capability-gated tiers.

3. **The 6-domain × 7-tier research structure is ambitious but coherent.** The progression from observation → analysis → survey → cross-reference → simulation records mirrors real scientific development. This is actually *more* elegant than GTNH's approach.

4. **Gap in "crafting layer" between pure materials and infrastructure:** Prometheus has mineral → refined material → intermediate product → machine, but the intermediates are too thin. The biggest quantitative gap is the missing **catalyst, insulation, gasket, alloy, fiber, and tool layers** — these are the small items that make factory engineering feel real.

### Quantitative Targets

| Category | Current | Recommended Target | Reference (Bob's/Angels) |
|----------|---------|-------------------|--------------------------|
| Unique machines | 70–80 types | Keep at ~80 | ~120 |
| Machine tiers total | ~350 | ~400 | ~400 |
| Pure materials with verified use | ~38 | ~45 | ~80 |
| Intermediate products (crafted items) | ~40 | ~70–75 | ~120 |
| Catalyst types | 0 (unstructured) | ~8–10 | ~50+ (GTNH) |
| Insulation/refractory items | 0 (unstructured) | ~6–8 | — |
| Gasket/seal materials | 0 (unstructured) | ~4 | — |
| Personal/specialized tools | 0 | ~10 | — |
| Gas products | Partial | ~6 | ~20+ (GTNH) |

### Design Recommendations

5. **Maintain the "knowledge before capability" philosophy.** Prometheus's core strength is its thematic coherence — every product, machine, and research tier serves the narrative of understanding → building → pushing boundaries. GTNH's weakness is that many items exist for catalog completeness rather than narrative purpose. Don't copy GTNH's density; use it as a ceiling reference, not a target.

6. **The "equilibrium over disposal" pillar needs explicit coproduct sink documentation.** As you expand the intermediate catalog, every new product must have at least one verified consumer. GTNH suffers from coproduct accumulation problems where items only exist as inputs to void recipes. Prometheus avoids this by design but needs the catalog depth to make it work mechanically.

7. **Add a "materials engineering" dimension.** This means small-crafting items (tools, gaskets, insulation, catalysts) that make the player feel like they're *building infrastructure*, not just checking tech-tree boxes. This is what distinguishes Bob's/Angels from vanilla and makes GTNH's item economy feel meaningful.

8. **Consider a "handbook unlock" mechanic tied to engineering reference manuals** (Recommendation #11). This creates an internal progression loop: research → manual → handbook reveals → player builds infrastructure → unlocks deeper research. It connects the research system to the player's understanding of their factory without adding game complexity.

---

## 5. Final Assessment

**Project Prometheus is currently at ~60% of the depth it needs for its stated 300-hour target.** The architecture, philosophy, and three-phase progression are solid — these are the hardest parts to get right. What's missing is the *micro-infrastructure*: catalysts, gaskets, insulation materials, engineering tools, alloy variants, and composite precursors that make factory engineering feel concrete and tactile.

Adding the ~60 items from the "Must-Add" and "Should-Add" lists would bring Prometheus to **~85% of Bob's/Angels depth** (which is appropriate for a more focused experience) while maintaining its thematic coherence — something GTNH lacks at scale. The unique value proposition (simulation-gated research bridging domain science packs to a planetary digital twin) gives Prometheus an identity that none of the reference mods have, and the recommended additions support that identity rather than diluting it.

**Priority order for implementation: catalysts → tools → insulation/refractory → gaskets → alloys → fibers/composites → safety/environmental → gas products.** These cascade naturally from early-game (catalysts gate all chemistry) to late-game (composites gate endgame infrastructure).

---

## Appendix: Items to Add by Priority

### Must-Add Before Phase C

#### 1. Catalyst Materials (~8 items)
| Item | Source | Use |
|------|--------|-----|
| Platinum/alumina catalyst pellets | Pt-group metals + alumina refinement | Contact process (SO₂ → SO₃), Ostwald chain (NH₃ oxidation) |
| Palladium/carbon catalyst | Pd + activated carbon support | Hydrogenation reactions, organic synthesis |
| Supported nickel catalyst | Ni + silica/alumina support | Fischer-Tropsch synthesis, hydrogenation |
| Vanadium pentoxide (V₂O₅) catalyst | V from magnetite traces + sulfur oxidation | Contact process alternative (lower cost than Pt) |
| Zeolite molecular sieves | Zeolite mineral processing | Cracking fractionation, isomerization reactions |
| Activated carbon (treated) | Refined coal/graphite → steam activation | Catalyst support, adsorption/filtration media |
| Raney nickel catalyst | High-purity Ni + NaOH leaching | Selective hydrogenation of organic compounds |
| Copper-chromium catalyst | Cu + Cr refining + oxide formation | Esterification, methanol synthesis |

#### 2. Personal & Engineering Tools (~10 items)
| Item | Craft Inputs | Purpose |
|------|-------------|---------|
| Engineering measurement caliper | Steel plates + precision gears + tungsten carbide tips | Verify alignment during infrastructure assembly; required for Core-level construction |
| Radiation dosimeter | Tantalum capacitors + semiconductor sensor + battery cell | Monitor fission reactor proximity; UI feedback layer |
| Welding helmet | Heat-resistant glass + steel frame + auto-darkening circuit (IC) | Required to operate EAF and high-temperature facilities safely |
| Multimeter | Copper wiring + semiconductor sensor + plastic housing | Debug automation circuits; verify PLC connectivity |
| Calibration reference kit | Polished metal standards + optical glass + precision tools | Calibrate domain labs for accurate research output |
| Pressure testing gauge | Stainless steel tube + copper bourdon tube + glass window | Test pressure vessel integrity before commissioning |
| Insulation resistance tester | Ceramic insulators + high-voltage probe + display circuit | Verify electrical insulation quality on high-tier equipment |
| Thermal imaging camera | Semiconductor sensor array + lead-glass lens + battery pack | Detect heat leaks, thermal bridges in factory layout |
| Precision alignment laser | Polysilicon laser diode + optical lens + steel housing | Laser-guided alignment for large-scale infrastructure |
| Non-destructive testing probe | Ultrasonic sensor + niobium transducer + display unit | Inspect weld integrity without disassembly |

#### 3. Insulation & Refractory Materials (~8 items)
| Item | Source | Use |
|------|--------|-----|
| Aerogel blanket rolls | Silica sol + supercritical CO₂ drying → flexible matting | General high-temperature insulation for pipes/vessels |
| Cryogenic insulation panels | Multi-layer reflective foil + spacers (HfO₂-coated) | Liquid nitrogen/argon storage and transport |
| Alumina ceramic pellets | Purified bauxite → calcined Al₂O₃ → pelletized | Furnace lining, high-temp reactor beds |
| Silicon-carborundum (SiC) refractory bricks | Quartz sand + coke sintered at 2000°C | Kiln lining, EAF roof sections |
| Zirconia insulating tiles | Purified zirconium oxide → pressed/sintered | Ultra-high-temp insulation (>1500°C) |
| Fused-silica glass sheets | High-purity silica melted and cast | Furnace viewports, UV-transmission windows |
| Mullite fiber panels | Alumina + silica fibers compressed and fired | Flexible high-temp insulation blankets |
| Magnesia-carbon bricks | Calcined magnesite + graphite flake pressed | Blast furnace hearth lining, converter repair |

#### 4. Gasket & Sealing Materials (~4 items)
| Item | Source | Use |
|------|--------|-----|
| PTFE sealing tape rolls | Fluoropolymer processing → thin-film extrusion | Thread sealing for chemical-rated pipe connections |
| Copper gasket blanks | Annealed copper sheet die-cut to diameter | High-temperature flange sealing (steam, hot gas) |
| Graphite-compressed gasket sheets | Purified graphite + resin binders → compressed sheets | Corrosive fluid service, acid-resistant sealing |
| FKM elastomer seal kits | Synthetic rubber compound (fluoroelastomer) molding | High-temp/corrosion dynamic seals (pumps, valves) |

### Should-Add Before Phase D

#### 5. Alloy Catalog Expansion (~10 items)
| Item | Base Material | Additive/Process | Purpose |
|------|--------------|------------------|---------|
| Maraging steel | Low-carbon iron + nickel | Mo, Co, Ti aging → ultra-high strength | Core assembly structural components (Phase 3) |
| Hastelloy-analog | Nickel base | Mo, Cr, W corrosion-resistant alloy | Acid-processing vessels, electrowinning cells |
| Inconel variant | Nickel-chromium | Fe, Mo, Nb for high-temp strength | Fusion reactor internals, high-temp furnace parts |
| Duplex stainless steel | Iron + chromium + nickel | Nitrogen addition → austenitic-ferritic mix | High-pressure chemical pipelines (better than standard SS) |
| HSS tool steel | High-carbon steel | W, Co, V for hot hardness | Cutting tools, drill bits at MTier 4+ |
| D2 tool steel | High-carbon + chromium | Mo, V → wear-resistant cold-work steel | Punch dies, stamping tools for component manufacturing |
| M2 tool steel | High-speed steel | W, Mo, V, Co → red-hardness | High-speed machining inserts, precision tooling |
| 17-4 PH precipitation hardening steel | Cr-Ni-Ma base | Cu precipitation → adjustable strength/fatigue resistance | Aerospace-grade shafts, high-stress fasteners |
| Aluminum 7075 alloy | Aluminum base | Zn, Mg, Cu → highest-strength Al alloy | Lightweight high-load structures (satellite infrastructure) |
| Copper-molybdenum heat spreader | Pure Cu + W/Mo infiltrated | Thermal expansion match for semiconductor substrates | EAF cooling plates, laser turret heat sinks |

#### 6. Fiber & Composite Precursors (~5 items)
| Item | Source | Use |
|------|--------|-----|
| Carbon fiber tows (PAN-derived) | Polyacrylonitrile stabilization + carbonization at 1000°C+ | High-strength lightweight structural reinforcement |
| E-glass fiber bundles | Silica + alumina + boron oxide drawn into fibers | Composite layup for containment structures, tanks |
| Epoxy resin laminates | Bisphenol A + epichlorohydrin → cured prepreg sheets | Structural bonding, PCB substrate manufacturing |
| Aramid fiber sheets | Polyamide condensation → extruded fibers → woven fabric | High-temp insulation blankets, flame-resistant barriers |
| Basalt rock fiber | Volcanic basalt melted and drawn | Abrasion-resistant lining for ore processing equipment |

#### 7. Safety & Environmental Buildings (~4 items)
| Building | Purpose | Materials Required |
|----------|---------|-------------------|
| Fume extraction hood | Captures toxic gases from chemical buildings before release to atmosphere | Stainless steel ducting + PTFE lining + semiconductor-grade flow sensors + activated carbon filter bank |
| Acid-resistant containment flooring tiles | Prevents fluid spread from leaks; channels spills to collection sump | Chemical-hardened concrete composite + rubber-seal grout + corrosion-resistant coating |
| Explosion vent panels | Pressure-relief mechanism for pressurized vessels that safely directs blast upward | Flame-arrestor mesh + calibrated rupture discs + steel mounting frame |
| Dust suppression system | Wet particulate collection from ore processing; captures airborne powders | Water sprayer array + cyclonic pre-separator + PTFE baghouse filter + sludge pump |

#### 8. Gas Products (~6 items)
| Item | Source | Use |
|------|--------|-----|
| Compressed hydrogen cylinders | Water electrolysis → compression/storage | Reducing atmosphere for sintering, Haber-Bosch feed |
| Liquid oxygen tanks | Cryogenic air distillation → condensed O₂ | Oxidizer for combustion enhancement, medical supply |
| Nitrogen feedstock (pressurized) | Cryogenic air separation → N₂ storage | Inert purging for chemical reactors, pressurization |
| Chlorine gas cylinders (stabilized) | Chlor-alkali output → compressed in steel cylinders with Fe catalyst | PVC production, metal chlorination (Kroll process) |
| SO₂ storage tank contents | Roaster off-gas capture + compression | Sulfuric acid feedstock when native sulfur is insufficient |
| Producer gas (mixed CO+H₂) | Coal gasification output | Alternative fuel for steam engines when refined fuels are scarce |

### Nice-to-Have (Can Defer)

#### 9. Precision & Optical Materials (~4 items)
| Item | Source | Use |
|------|--------|-----|
| Quartz optical lens blanks | Fused high-purity silica → precision ground/polished | Photolithography stepper optics, UV transmission windows |
| Sapphire window panes | Synthetic alumina crystal growth → sliced/polished | High-pressure viewport material, IR-transparent windows |
| IR-transmitting germanium plates | Germanium from coal/copper trace recovery → polished wafers | Thermal imaging lens elements, IR sensor windows |
| UV-grade fused silica sheets | Ultra-pure SiO₂ melted in platinum crucible → cast/sheeted | Photolithography reticle substrate, UV reactor windowing |

#### 10. Battery Chemistry Diversity (~3–4 items)
| Item | Source | Use |
|------|--------|-----|
| Lithium cobalt oxide (LCO) cathode powder | Li compounds + cobalt sulfate → calcined layered oxide | High-energy-density battery cells for mobile equipment |
| Nickel-cobalt-aluminum (NCA) cathode blend | Ni + Co + Al compounds co-precipitated → calcined | Higher-stability alternative to LCO; longer cycle life |
| Graphite anode flakes (sintered) | Purified natural graphite → exfoliated/sintered pellets | Battery anode material with controlled interlayer spacing |
| Solid polymer electrolyte sheets | Polymer matrix + lithium salt dissolved and cast | Safety-enhanced batteries (no liquid electrolyte leakage risk) |

#### 11. Sample & Collection Infrastructure (~3 items)
| Item | Purpose | Materials Required |
|------|---------|-------------------|
| Core sample drill | Extract cylindrical subsurface cores for geological analysis | Tungsten-carbide drill bit + steel core barrel + motor housing |
| Mineral specimen display cabinet | Catalog and showcase recovered mineral specimens; provides reference lookup in informatron | Glass panels (silica) + steel frame + LED illumination circuits |
| Field spectrometer | Portable handheld mineral ID tool for prospecting support | Semiconductor sensor array + calibrated light source + processing unit |

---

*This report was generated on 2026-11-11 as a comparative analysis between Project Prometheus and three reference mods (GregTech, Bob's/Angels, Space Exploration). Use it to guide Phase B–D design work before finalizing machine build recipes and intermediate product catalogs.*
