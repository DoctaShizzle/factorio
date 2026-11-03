# Chemical Processes — Design Reference

*For: Factorio Overhaul Mod*
*Status: Brainstorming / Requirements Phase*

---

# Design Intent

Real chemistry with multiple viable production pathways. Educational value emerges from discovery, not text walls. Each chemical process should reveal:

1. The real-world chemistry
2. Multiple production routes (with tradeoffs)
3. Why the alternatives exist

---

# Core Principles for Chemical Depth

## Principle 1: One Happy Path Per Process
Every player should be able to produce every product via at least one straightforward route. Complexity comes from **choice**, not necessity.

Example: Making plastic has a "follow these steps" path AND optional alternative routes that become available later.

## Principle 2: Real Chemistry → Gameplay Tradeoffs, Not Simulated Chemistry
We're not simulating molecular bonds or reaction kinetics. We're taking **real industrial chemistry patterns** and turning them into gameplay mechanics.

Good: "Real polyethylene production has catalyst choices that affect polymerization rate, yield, and byproducts" → gameplay: different catalysts in the reactor change output mix.

Bad: "Simulate temperature gradients inside a reaction chamber with precision."

## Principle 3: Complexity Reveals With Capability
Early game: follow the happy path.  
Mid game: discover alternatives exist (shown in handbook).  
Late game: choose which to use based on your constraints.

---

# Anchors & Inspiration Sources

These games/ mods have done chemistry-related design worth studying:

## GregTech (Gregtech 6 / GTNH)
- Hundreds of named chemical reactions
- Multi-stage processing chains
- Real intermediates (Sulfuric acid, Hydrogen peroxide, Phosgene...)
- Pro: deeply authentic industrial chemistry
- Con: complexity wall at ~40 hours
- **Lesson to take:** Name every process. Players build mental models from real names.

## Bob's Mods / Angel's Mod
- Streamlined chemical chains focused on usability
- Clearer progression than GregTech
- Fewer reactions but more digestible
- **Lesson to take:** Quality over quantity. 20 excellent paths > 200 overwhelming ones.

## Dyson Sphere Program
- Compressed chemistry: fewer steps, broader scope
- Chemicals feed directly into endgame (space programs)
- **Lesson to take:** Connect chemicals to the overall game goal — don't let them become their own isolated economy.

---

# Candidate Chemical Chains (Prioritized)

These are candidates for implementation order. Priority based on: connection to core loop, educational value, and capability unlock potential.

## Tier 1: Core Pathways (Must Have)

### 1. Plastics / Polyethylene
- **Why:** Connects oil refining → chemistry → downstream manufacturing
- **Happy path:** Oil → Petrochemical Plant → Plastic (simple)
- **Alternatives:** Catalytic cracking routes, polymerization variants with different catalysts
- **Real chemistry:** Ethylene polymerization, Ziegler-Natta vs metallocene catalysts
- **Gameplay hook:** Different polyethylene types for different applications

### 2. Sulfuric Acid
- **Why:** The "bottleneck of bottlenecks" in real industrial chemistry
- **Connects to:** Ore processing (acid leaching), fertilizer, battery production, semiconductor etching
- **Real chemistry:** Contact process — SO₂ → SO₃ → H₂SO₄ using vanadium pentoxide catalyst
- **Gameplay hook:** Catalyst availability controls acid production capacity

### 3. Cement / Concrete
- **Why:** Infrastructure building material for mid/late game construction
- **Connects to:** Steel production, construction industry, endgame megafactory bases
- **Real chemistry:** Limestone calcination (CaCO₃ → CaO + CO₂), clinker formation
- **Gameplay hook:** CO₂ byproduct is a pollutant AND a precursor for other chemicals

### 4. Chlor-Alkali Process
- **Why:** Produces chlorine, sodium hydroxide, hydrogen — all essential mid-game chemicals
- **Connects to:** PVC (from Step 1), water purification, battery chemistry
- **Real chemistry:** Electrolysis of brine solution
- **Gameplay hook:** Requires pure brine preparation + electrical infrastructure

## Tier 2: Expansion Paths

### 5. Nitrogen Fixation (Haber-Bosch)
- Produces ammonia from atmospheric nitrogen + hydrogen
- Fertilizer production → food industry (niche but interesting)
- Explosives precursor → military connection
- Real chemistry: N₂ + H₂ → NH₃ at high pressure with iron catalyst

### 6. Adipic Acid / Nylon
- From benzene/cyclohexane oxidation
- Connects petroleum refining to manufacturing
- Alternative plastic/fiber path

### 7. Titanium Production (Kroll Process)
- From rutile/titanium ore → TiCl₄ → pure titanium
- High-value metal for mid/late game
- Lots of intermediate chemistry
- Great capability unlock: "I got a titanium production line"

---

# Chemical Plant Design Philosophy

## Machine: Chemical Reactor(s)

Not one giant machine. Different reactor types for different processes:
- **Packed-bed reactors** — for catalytic gas reactions (sulfuric acid, Haber-Bosch)
- **Stirred-tank reactors** — for liquid-phase chemistry (chlor-alkali)
- **Fluidized beds** — for high-temp solid-catalyst reactions
- **Electrolysis cells** — for ionic processes

Each reactor type has different:
- Supported reactions
- Throughput limits
- Catalyst slot configurations
- Power requirements

## Catalyst System

Catalysts are the primary "tuning knob" for chemical plants — not sliders, but physical items you insert:
- Different catalysts change output ratios (like GTNH's catalyst choices)
- Catalysts degrade over time → replacement mechanic
- Some catalysts require rare elements (platinum group metals from refining)

## Intermediates Matter

Real industrial chemistry uses intermediates. Players should manage them:
- Sulfur dioxide isn't a final product — it feeds into the next stage
- Ethylene needs to flow directly to polymerization
- Storing intermediates is possible but inefficient (encourages continuous flow)

This mirrors how real chemical plants work: **batch processing is wasteful, continuous flow is efficient.**

---

# Connection to Design Pillars

## Pillar 1: Multiple Industrial Processes
Each chemical should have 2-3 production routes with different tradeoffs.

Example — Sulfuric Acid:
| Route | Pros | Cons |
|-------|------|------|
| Contact Process (vanadium catalyst) | Balanced, standard | Requires pure SO₂ |
| Wet sulfuric acid | Direct from mining runoff | Polluting, hard to control |
| Lead chamber (legacy) | Simple infrastructure | Low purity, high pollution |

## Pillar 2: Tradeoffs Map to Primary Axes
- Resource efficiency (acid yield per sulfur input)
- Capital complexity (contact process needs catalyst infrastructure)
- Pollution impact (wet process vs contact process)

## Pillar 8: Capability Over Numbers
Unlocks should be memorable:
> "I built a Kroll titanium plant." ✓  
Not:
> "My chemical reactor got 15% faster." ✗

---

# Scope Management

## Hard Constraints
- Start with **Tier 1 only** (4 core chains)
- Each chain must have: happy path + at least one alternative
- Every intermediate must be visible in the handbook

## Expansion Criteria (for later)
Before adding Tier 2 chemicals:
1. Do they connect to existing infrastructure?
2. Do they unlock a new capability?
3. Do they create meaningful tradeoffs?
4. Is their real-world chemistry interesting enough to justify the implementation?

If it fails any of these, don't add it.

---

# Notes

- Chemical processes are **not** the theme. They serve the same purpose as refining: creating process choices that connect to every other system in the game.
- If a chemical doesn't feed into at least 2 downstream systems (refining, metallurgy, semiconductor, endgame), question its existence.
- Realism is only valuable when it creates meaningful engineering decisions (True North Star).
