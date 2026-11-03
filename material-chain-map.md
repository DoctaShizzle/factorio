# Factorio Overhaul — Complete Material Chain Map

*For: Factorio Overhaul Mod — Design Phase*
*Status: Requirements mapping (not final)*

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

# Mirroring vs Asymmetric Assessment Against This Map

With ~65-83 materials across 7 tiers, here's what each approach means:

## With Mirroring (what we designed above)

Every ore has three mirrored methods:
- Method A → Physical Separation (equilibrium challenge via byproducts)
- Method B → Chemical Processing (high value, needs infrastructure)
- Method C → Thermal/Industrial (scale + pollution)

**Pros for this scope:**
- 15+ ores all follow the same pattern — cognitive load stays low even as materials multiply
- Tier progression maps directly to method tiers: early ores = simple Method A only; later ores = full access to A/B/C
- Byproduct integration creates natural cross-chain interlocks
- Easy to add new ores without redesigning process logic

**Cons for this scope:**
- Can feel repetitive if all 15 ores produce the same three output types
- Less "aha!" moments when discovering new minerals — they're structurally identical

## With Asymmetric (5 archetypes)

Each mineral enters the five archetypes differently:
- Chalcopyrite touches all 5 with rich interlocks
- Hematite has a simpler linear path + optional branch
- Bauxite forces forced coupling (Bayer → electrolysis)
- New ores can enter at different points

**Pros for this scope:**
- Every ore feels genuinely different to process
- Natural progression: early ores touch 2 archetypes, late ores touch all 5
- Cross-mineral interlocks emerge from pathway structure, not forced design

**Cons for this scope:**
- **This is the critical concern:** with 15+ ores × potentially 3 entry points each = many unique input/output configurations. Logistics complexity scales as O(n²) in ore count.
- Each new ore needs custom processing chain design — harder to template code
- Player must memorize not just "which methods" but "how this mineral flows through the ecosystem"

## Verdict on Your Concern

**Your fear is valid.** Asymmetric pathways with 15+ ores absolutely creates logistical complexity. The question is whether that complexity serves the game or becomes cognitive overload.

Here's the thing Factorio teaches us: **players love logistics puzzles IF they understand the rules.** A player who understands "all copper concentrates go to smelting" finds balancing sulfur streams satisfying, not overwhelming. The problem isn't complexity — it's *memorization of arbitrary routing*.

**The hybrid solution** might be the right one:
- Keep mirroring as the **primary pattern** (every ore has A/B/C methods) — this handles cognitive load and code templating
- Add **asymmetric bridges** at key moments (forced couplings, optional late-game optimizations, capability unlocks) — this handles novelty
- The 5 archetypes still exist but as a **mental model**, not as routing rules. "I process chalcopyrite via mechanical separation first" is true, but mechanically it's froth flotation Method A — same template as everything else

This way you get the best of both:
- Mirroring handles scale (15+ ores, low cognitive load, easy templating)
- Asymmetric bridges handle surprise (a few "aha!" moments that differentiate minerals)
- The 5 archetypes serve as designer's framework for understanding pathways, not player-facing logic
