# Factorio Overhaul — Complete Material Chain Map

*For: Factorio Overhaul Mod — Design Phase*
*Status: Requirements mapping (not final)*

Related design: [Mining, Refining & Metallurgy](mining-refining-metallurgy.md)

---

# Tier 0: Base Resources (Vanilla-Adjacent)

These replace or augment vanilla starting resources. Player sees them in early game.

| Resource | Type | Early Game Form | Purpose |
|----------|------|-----------------|---------|
| Iron Ore | Surface deposit → Underground hematite/magnetite deposits | Iron Deposit (vanilla replacement) | Steel production, base industry |
| Copper Ore | Surface deposit → Underground chalcopyrite deposits | Copper Deposit (vanilla replacement) | Wiring, motors, chemical processes |
| Coal | Surface deposit → Underground coal seam | Coal Deposit (vanilla replacement) | Fuel, coke precursor, carbon source |
| Sand/Stone | Surface deposit | Stone/Ghost Rock (vanilla replacement) | Construction, glass, silica source |
| Sulfur | Underground deposit | Sulfur node (vanilla replacement) | Acid production, sulfide ores, batteries |
| Limestone/Gypsum | Underground deposit | New: limestone quarry nodes | Cement, BOF flux, acid neutralization |

---

# Tier 1: Primary Refined Materials (Mid-Game Foundation)

These are the first processed materials the player creates from raw minerals.

## Iron Industry Chain

| Material | From | Purpose |
|----------|------|---------|
| Pig iron | Blast furnace (hematite + coke) | Steelmaking input |
| Steel (carbon) | BOF or electric arc (pig iron + scrap) | Primary structural material |
| Sponge iron / DRI | Hydrogen reduction (hematite) | Direct-feed specialty steel |
| Slag (blast furnace) | Byproduct of pig iron production | Cement/construction use |

## Copper Industry Chain

| Material | From | Purpose |
|----------|------|---------|
| Copper concentrate | Froth flotation (chalcopyrite) | Intermediate — feeds smelting or leaching |
| Blister copper | Smelting (copper concentrate) | Electrorefining input |
| High-purity copper | Electrorefining (blister copper) | Wiring, semiconductor substrate, catalysts |
| Iron sulfide residue | Byproduct of flotation | Steel line feed or disposal challenge |

## Aluminum Industry Chain

| Material | From | Purpose |
|----------|------|---------|
| Alumina (purified) | Bayer process (bauxite + NaOH) | Electrolysis input |
| Aluminum metal | Hall-Héroult electrolysis (alumina) | Lightweight alloys, endgame infrastructure |
| Red mud | Byproduct of Bayer process | Steel/caustic integration challenge |

## Silicon Industry Chain (Semiconductor Bridge)

| Material | From | Purpose |
|----------|------|---------|
| Quartz/silica concentrate | Mechanical separation (sand/quartz deposits) | Metallurgical silicon input |
| Metallurgical silicon (98-99%) | Thermal reduction (silica + carbon in arc furnace) | Downstream purification target |
| Trichlorosilane (SiHCl₃) | Chemical reaction (met Si + HCl) | Semiconductor-grade precursor |
| Electronic-grade polysilicon (>99.9999%) | Purification (chemical distillation of trichlorosilane) | Wafer fabrication feedstock |

---

# Tier 2: Chemical Intermediates

These connect multiple industrial chains together. The "glue" between minerals.

## Acid Production Chain

| Material | From | Purpose |
|----------|------|---------|
| Sulfur dioxide (SO₂) | Byproduct of sulfide smelting (chalcopyrite) | Acid feedstock or pollution |
| Sulfuric acid (H₂SO₄) | Contact process (SO₂ + O₂ over V₂O₅ catalyst) | Feeds leaching, Bayer process, chemical synthesis |

## Chlor-Alkali Chain

| Material | From | Purpose |
|----------|------|---------|
| Brine (purified NaCl solution) | Dissolved salt from salt deposits | Electrolysis input |
| Chlorine gas (Cl₂) | Chlor-alkali electrolysis of brine | PVC, ferric chloride leaching agent |
| Sodium hydroxide (NaOH) | Chlor-alkali electrolysis | Bayer process solvent, pH control |
| Hydrogen gas (H₂) | Chlor-alkali or water electrolysis | H₂ reduction for hematite, fuel |

## Nitrogen Chain

| Material | From | Purpose |
|----------|------|---------|
| Ammonia (NH₃) | Haber-Bosch (N₂ from air + H₂) | Fertilizer, nitric acid precursor |
| Nitric acid (HNO₃) | Ostwald process (ammonia + oxygen over Pt catalyst) | Explosives, specialty chemical synthesis |

## Carbon Chain

| Material | From | Purpose |
|----------|------|---------|
| Coke | Coal carbonization (heated without air) | Blast furnace fuel/reducer |
| Activated carbon | Pyrolyzed biomass/coal | Water purification, catalyst support |
| Calcium carbide (CaC₂) | Lime + coke in electric arc furnace | Acetylene production, steel deoxidizer |
| Carbon nanotubes/fibers | CVD from hydrocarbon gas | Advanced composite material (late-game) |

---

# Tier 3: Specialty Metals & Alloys

These require mid-to-late game infrastructure. Capability unlocks.

## Refining Group Metals (From Chalcopyrite Byproduct Recovery)

| Material | From | Purpose |
|----------|------|---------|
| Gold | Precious metal recovery from sulfide ore processing | Catalyst substrate, electronics |
| Silver | Same as gold | Catalyst, chemical processing equipment |
| Platinum group metals (PGM) | Trace in sulfide ores, concentrated via flotation tailings | Inert anodes, Haber-Bosch catalyst, nitric acid catalyst |

## Specialty Steel Alloys

| Material | From | Purpose |
|----------|------|---------|
| Stainless steel | Steel + chromium/nickel in electric arc furnace | Corrosion-resistant construction, acid handling equipment |
| Titanium steel | Steel + titanium addition (from Kroll process, see below) | Lightweight structural alloy |
| Tool steel | High-carbon steel + tungsten/vanadium | Hardwearing machine parts, drill bits |
| Invar/low-expansion alloy | Iron + nickel (36% Ni) | Precision components, measurement equipment |

## Non-Ferrous Specialty Metals

| Material | From | Purpose |
|----------|------|---------|
| Zinc | Roasting + electrolysis of sphalerite concentrate | Galvanizing, alloys, batteries |
| Lead | Roasting + reduction of galena concentrate | Acid-resistant construction, battery plates |
| Nickel | High-pressure acid leaching of laterite ore or sulfide roast-leach | Stainless steel ingredient, catalyst, batteries |
| Titanium (pure) | Kroll process (TiCl₄ + Mg in argon atmosphere) | Lightweight high-strength structures |
| Magnesium | Electrolysis of molten MgCl₂ or carbothermal reduction of MgO | Reducing agent for Kroll process, lightweight alloy |

## Battery Materials (Mid-to-Late Game)

| Material | From | Purpose |
|----------|------|---------|
| Lithium carbonate/hydroxide | Brine evaporation or leaching from spodumene ore | Battery chemistry, electrolyte |
| Cobalt sulfate | Leaching + purification of cobalt-containing ores | Battery cathode material |
| Manganese compounds | Leaching of manganese oxide ores | Battery cathodes, steel additive |

---

# Tier 4: Polymer & Plastics Chain

These connect oil refining to downstream manufacturing. Not ore-based but critical for the mod.

## Oil/Rubber Refining Path

| Material | From | Purpose |
|----------|------|---------|
| Naphtha | Fractional distillation of crude oil | Petrochemical feedstock |
| Ethylene | Catalytic cracking of naphtha or natural gas liquids | Polymerization monomer, chemical intermediate |
| Propylene | Catalytic cracking | Polymerization, propylene oxide precursor |
| Benzene | Reforming of naphtha | Adipic acid/nylon precursor, chlorobenzene |
| Polyethylene (HDPE/LDPE) | Polymerization of ethylene + catalyst | Plastic production, pipe materials for fluid handling |
| PVC | Chlorination of ethylene → polymerization with Cl₂ | Pipes, cable insulation, fluid system materials |

## Advanced Polymers (Late Game)

| Material | From | Purpose |
|----------|------|---------|
| Nylon 6,6 (polyamide) | Adipic acid + hexamethylenediamine from benzene | Fiber, engineering plastic |
| Epoxy resin precursor | Phenol + formaldehyde (from coal or petrochemical route) | Adhesives, composite matrix |
| Fluoropolymer (PTFE analog) | Ethylene + fluorine (from fluoride minerals) | Chemical-resistant piping/sealing for cleanroom |

---

# Tier 5: Semiconductor Materials (Late Game Bridge)

These connect the base industry chain to the endgame.

| Material | From | Purpose |
|----------|------|---------|
| Silicon wafers (single crystal) | Czochralski process from polysilicon + dopant | Base substrate for IC fabrication |
| Photolithography resist | Specialty organic synthesis | Pattern definition on wafers |
| High-k dielectric (HfO₂, Al₂O₃) | Chemical vapor deposition precursors | Gate insulation for advanced transistors |
| Interconnect metals (Cu, TaN barrier) | Ultra-pure metal refining + sputtering targets | Wiring within chips |
| Specialty gases (WF₆, SF₆, NF₃) | Gas synthesis from refined elements | Etching and deposition in cleanroom |

---

# Tier 6: Endgame Materials

These are used to build the endgame computational network.

| Material | From | Purpose |
|----------|------|---------|
| Processed semiconductor units | Wafer fab → diced chips → packaged ICs | Computing capacity component |
| Superconductor materials | Specialty metal alloy synthesis (NbTi, YBCO) | Zero-loss power distribution for cluster |
| Cryogenic fluid (liquid He/N₂) | Gas liquefaction and separation | Cooling for superconducting systems |
| Precision optics | Optical glass synthesis + polishing | Photonics/simulation interconnects |

---

# Material Dependency Graph (Simplified)

```
TIER 0 (Base)                    TIER 1 (Primary Refined)
Iron ore → Hematite             Pig iron → Steel, Slag
Copper ore → Chalcopyrite       Copper → Wiring, Substrate
Bauxite                          Alumina → Aluminum
Silica                           Metallurgical Si → Polysilicon
Sulfur, Limestone, Salt          Sulfuric acid, NaOH, Cl₂

         ┌────────── Chemical Intermediates (Tier 2) ──────────┐
         │ SO₂/H₂SO₄ ←→ Feeds leaching & Bayer                │
         │ Cl₂/NaOH/H₂ ←→ Chlor-alkali supports everything    │
         │ NH₃/HNO₃ ←→ Fertilizer, explosives, catalysts      │
         │ Coke/Carbon chain ←→ Fuel, reducer, structural     │
         └────────────────────────────────────────────────────┘

TIER 3 (Specialty Metals)              TIER 4 (Polymers/Oil)
PGM from chalcopyrite tailings        Oil → Naphtha → Ethylene → Polyethylene
Stainless steel, Ti, Mg, Zn, Pb       PVC, Nylon, Epoxy → pipes & chemical handling
Battery materials                      Advanced polymers → cleanroom infrastructure

         ┌──────── Semiconductor (Tier 5) ────────┐
         │ Polysilicon + dopants → Silicon wafers  │
         │ Wafers + photoresist → Fabricated chips │
         │ Specialty gases + interconnect metals    │
         └──────────────────────────────────────────┘

              TIER 6 (Endgame)
        Processed ICs + superconductors
        Cryogenics + precision optics
              ↓
       Computational Network
```

---

# Total Material Count

| Tier | Category | Approximate Materials |
|------|----------|---------------------|
| 0 | Base resources | ~6-8 |
| 1 | Primary refined (metals) | ~12-15 |
| 2 | Chemical intermediates | ~10-12 |
| 3 | Specialty metals/alloys | ~15-20 |
| 4 | Polymers/oil products | ~10-12 |
| 5 | Semiconductor materials | ~8-10 |
| 6 | Endgame materials | ~4-6 |
| **Total** | | **~65-83 distinct materials** |

---

# Key Observations for Design Decisions

1. **The majority of materials are Tier 1 + Tier 2** — this is where the refining design needs to be strongest. These are the materials players interact with daily.

2. **Tier 3 and Tier 4 are capability unlocks** — they shouldn't appear until the player has built the prerequisite industrial ecosystem. This is where "Pillar 8: Capabilities Over Numbers" shines. Titanium production = "I got a Kroll plant." Chlor-alkali = "I can make my own acid now."

3. **Cross-mineral interlocks exist in Tier 2** — the chemical intermediates are what connect all minerals together. If your refinery doesn't feed the acid plant, nothing else matters. This is where equilibrium is won or lost.

4. **Oil/polymer chain is separate but feeds everything** — it runs parallel to ore refining and provides piping (PVC, polyethylene), cleanroom materials (fluoropolymers), and chemical feedstocks (benzene → nylon). It's a second ecosystem that converges with the mineral ecosystem at Tier 4+.

5. **The endgame is reachable from multiple directions** — you can't just "build chips." You need silicon purification AND specialty gases AND semiconductor-grade metals. Each comes from a different part of your factory. That's the Factorio feel: no single path to the end.

---

## Current Refining Direction

The current preference is to lean toward Angel's mirrored processing model while supporting a broader and more geologically varied set of raw materials.

- Reuse a small number of recognizable processing stages and progression patterns across most mineral lines.
- Let the three extraction tiers add complexity through deposit composition and mixed output streams, rather than inventing unrelated process logic for every ore.
- Allow exceptions when the real material chemistry warrants them. Aluminum production from bauxite is a candidate: its Bayer-to-electrolysis chain is meaningfully different from common iron and copper processing.
- Treat the specific number and shape of methods per mineral as unresolved; the examples are design probes, not a rule that every ore must have exactly three routes.

This is a working direction, not a final process specification. The dedicated [Mining, Refining & Metallurgy](mining-refining-metallurgy.md) document holds the extraction model and worked examples; this map tracks candidate materials and dependencies.
