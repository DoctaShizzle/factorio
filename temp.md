# Factorio Overhaul Concept V2
## Industrial Ecosystems and Process Engineering

---

# Executive Summary

This project is not intended to be:

- Factorio but larger
- Pyanodon's but harder
- GTNH but in Factorio
- Angel's with more ores

The goal is to create a coherent industrial ecosystem where every major mechanic supports a common vision.

The central design philosophy is:

> Progression should come from understanding and choosing industrial strategies rather than unlocking longer recipe chains.

The player should feel less like a factory builder and more like an industrial engineer.

---

# Grand Design Philosophy

Every major system should reinforce every other system:

- resource extraction
- refining
- metallurgy
- chemistry
- power generation
- pollution
- military pressure
- semiconductors
- endgame research

Every system should support the same industrial philosophy.

---

# Design Pillars

## Pillar 1: Multiple Industrial Processes
Every major product should have multiple viable production methods.

## Pillar 2: Tradeoffs Instead of Progression
Every product should have multiple viable production methods, each optimising different primary constraints.

### Primary Axes (the core tension)
- **Resource efficiency** — a la Angel's equilibrium
- **Pollution / military pressure** — a consequence axis, not a standalone one
- **Capital complexity** — infrastructure cost, not power or space

Almost every interesting conversation maps onto those three.

### Secondary Axes (useful but not central)
- Throughput
- Power consumption
- Floor space

Power and space matter, but they are levers — not the core tension.

## Pillar 3: Processes Instead of Recipes
The player should ask:

> Which process should I use?

instead of:

> Which recipe do I unlock next?

## Pillar 4: Refining Creates Options
Better refining should create additional options, not simply higher yields.

## Pillar 5: Pollution as an Optimisation Axis
Pollution is a strategic choice, not merely punishment.

## Pillar 6: Military Is Economic, Not Gimmicky
Avoid:
- "Special enemy X attacks thing Y"

Instead:

**Military is the price paid for industrial decisions.**

Dirty steel:
- throughput
- pollution → alien attacks

Clean steel:
- throughput
- alien attacks (but deferred/managed)

Pollution = **deferred military spending.**
This connects metallurgy, refining, power generation, and military into one system.

## Pillar 7: Equilibrium Over Disposal
Storage may exist.
Voiding may exist.
Neither should be required.

The optimal solution should be:

> equilibrium

rather than:

> disposal

---

## Pillar 8: Capabilities Over Numbers (NEW)
The player should unlock:
- prospecting
- flotation
- chemical refining
- semiconductor fabrication
- automation systems
- simulation infrastructure

rather than simply:
```
+20% efficiency
+50% throughput
Tier 5 machine
```

This is one of GTNH's greatest strengths. People remember:

> "I got a cleanroom."

Not:

> "My machine got 12% faster."

---

# Key Inspirations

## Satisfactory
- Situational optimisation
- Alternate recipes as tradeoffs
- No universally correct solution

## Angel's Refining
- Refinery equilibrium
- Self-balancing production systems
- Discoverability is the challenge, not complexity

## GTNH
- Memorable capability unlocks
- Real-world materials
- Industrial depth

## Dyson Sphere Program
- Grand purpose for industrial growth
- Computing and simulation as an endgame goal

---

# Resource Extraction Philosophy

Prefer real-world minerals:
- Hematite
- Magnetite
- Chalcopyrite
- Galena
- Sphalerite
- Bauxite
- Cassiterite

## Mining Evolution: Deposits Evolve, Not Just Scale

The player doesn't transition to _bigger miners_.
The player transitions to _more complex resource streams_.

### Early Game — Simple Surface Deposits (Learning Phase)

Factorio-like:
- Iron Deposit
- Copper Deposit
- Coal Deposit

Familiar, accessible. The tutorial layer.

### Mid Game — Real Mineral Deposits (Geology Phase)

Real minerals where geology matters:
- Hematite Deposit (iron oxide, high purity)
- Magnetite Deposit (magnetic separation possible)
- Chalcopyrite Deposit (CuFeS₂ — copper and iron together, plus sulfur)
- Bauxite Deposit (aluminum precursor)
- Galena / Sphalerite Pairs (lead/zinc deposits that must be separated)

Geological knowledge becomes mechanically relevant.

### Late Game — Ore Bodies (Complex Stream Phase)

Not individual ores. **Ore bodies.**

Example: Volcanogenic Massive Sulfide (VMS) Deposit outputs:
- chalcopyrite
- pyrite
- sphalerite
- galena
- plus trace precious metals

Now refining equilibrium matters — not because you need more of everything, but because **every choice to prioritize one output creates imbalance in others**. The challenge is designing the factory to absorb that balance.

## Resource Extraction Implications for Refining

This deposit evolution directly sets up the refining system:
- Early game: single-output deposits → simple processing
- Mid game: mineral-specific deposits → process-specific solutions
- Late game: multi-mineral ore bodies → equilibrium challenges by design

---

# Refining Philosophy

The factory begins at the refinery, not at the smelter.

Mine Ore
→ Smelt Plate

becomes:

Extract Minerals
→ Process Streams
→ Separate Materials
→ Optimise Refinery
→ Manufacture Products

## Byproduct Philosophy

Storage is not a solution.

Voiding is not a solution.

Industrial equilibrium is the solution.

---

# Process Control: Physical, Not UI-Based

Ore + Process Configuration → Preferred Output Mix

## How Players Configure Processes (Avoid Sliders)

**Sliders feel gamey. Configuration should be physical — via factory design.**

### Option A: Catalyst Choices
Example — Copper Flotation:
- Catalyst A: maximize copper recovery
- Catalyst B: maximize nickel recovery
- Catalyst C: maximize precious-metal recovery

Each catalyst produces the same raw stream but emphasizes different outputs.

### Option B: Machine Configuration
Different recipes for different modes — like Angel's process control but more discoverable.

### Option C: Process Module Slots
Like inserters/underground belts as tangible machine parts:
- Recovery Module → higher yield, lower throughput
- Purity Module → cleaner separation, higher power
- Throughput Module → raw capacity over efficiency

> Configuration through factory design. Not through UI menus.

---

# Industrial Knowledge as Progression

## Knowledge Should Unlock Earlier Than Capability

Information unlocks **before** the player can implement it.

Early game, a player opens the handbook and sees:
```
Iron Industry
- Primitive Blast Furnace
- Oxygen Furnace
- Hydrogen Reduction
- Plasma Reduction
```
The player **cannot build them yet.** But they know they exist.

This creates **anticipation** — similar to GTNH, but with a crucial difference:

GTNH often says: > "Here's the next thing."

Our handbook should say: > "Here's the entire industrial journey."

### The Principle: Don't Hide Complexity. Reveal It Gradually.
- ✅ Reveal future systems
- ✅ Explain their purpose
- ✅ Explain tradeoffs
- ❌ Hide them until hours later

---

# Semiconductor Philosophy

Semiconductors are not the theme.
They are the culmination.

Early Game:
- Extraction
- Refining
- Metallurgy

Mid Game:
- Chemistry
- Catalysts
- Process optimisation

Late Game:
- Silicon purification
- Specialty gases
- Cleanrooms
- Wafer fabrication

End Game:
- Processors
- Computational clusters
- Simulation hardware

---

# Endgame Vision: Distributed Network

The final objective is creating computational capacity.

### NOT a single megastructure (DSP already did that)

**A network across the map:**

```
Wafer Fab
→ CPU Fab
→ Supercomputer Facility
→ Simulation Cluster
→ Planetary Research Center
```

spread across the terrain. This is more Factorio-like and more scalable.

The "Planetary Simulation Engine" is a **network** — not a building.

---

# Things To Avoid

- Recipe inflation
- Mandatory upgrades
- Single correct answers
- Artificial complexity
- Reliance on storage
- Reliance on voiding
- Stitched-together design

---

# The True North Star

> The goal is not to simulate industry.
>
> The goal is to make the player think like an industrial engineer.
>
> Realism is valuable only when it creates meaningful engineering decisions.

This single sentence explains almost every decision we've made so far:
- why we like Angel's equilibrium
- why we dislike mandatory storage
- why we like DSP's end goal
- why we want real minerals
- why we don't want heat-pipe busywork
- why GTNH's strongest moments are capability unlocks

---

---

# Chemical Processes (NEW — FROM FAMILY IDEAS)

Like GregTech and Bob/Angels, real chemical processes should be **educational as well as mechanical**.

Players should encounter:
- Multiple pathways to the same product (e.g., different ways to make polyethylene / plastics)
- Named reactions with real chemistry
- Intermediates that mirror actual industrial chemistry
- Discovery of "oh, this is how they actually make it in real life" moments

Chemical depth should serve the design pillars — not exist for its own sake.

Each chemical process reveals:
1. The real-world chemistry
2. Multiple viable production routes
3. Tradeoffs between them (efficiency, infrastructure, pollution)

---

# Power System Overhaul (NEW — FROM FAMILY IDEAS)

Satisfactory and Factorio's global infinite power grid is unrealistic. GTNH's voltage/ampere system adds meaningful dimension.

## Vision: Grid-Based Power, Not Global Bus

**No more connect-everything-to-the-nearest-wire.**

### Transmission Tiers
- **Low-voltage wiring** — limited distance, small loads (early game / local use)
- **High-voltage lines** — long-distance transmission with losses
- **Transformation stations** — step-up / step-down between voltage tiers

### Conductor Variety (GTNH-inspired)
Different metals = different conductivity:
- **Copper** — good conductivity, standard high-voltage
- **Tin** — lower capacity, cheaper
- **Gold** — superior conductivity for late-game precision distribution
- **Aluminum** — lightweight, long-distance overhead lines

### Power Losses
Distance-based losses make generator placement matter:
- Power plants can't just be "placed anywhere"
- Industrial clusters need their own generation
- Long-haul transmission is expensive and wasteful
- Local generation becomes a strategic choice

This turns power into an **engineering problem**, not a checkbox.

---

# Fluid System Overhaul (NEW — FROM FAMILY IDEALS)

Bob/Angels attempted this but the systems felt bolted-on. Our approach:

## Pipe Diameter & Material Matters

### Diameter Tiers
- Narrow pipes → lower throughput (m³/h equivalent)
- Wide pipes → higher throughput, more material cost

### Material Properties
Different pipe materials can handle:
- **Temperature ranges** — some fluids break standard pipes
- **Chemical resistance** — corrosive fluids degrade certain materials
- **Pressure ratings** — high-flow systems need reinforced piping

### Pumps as Mechanical Components
- Add pumps with rated throughput (m³/h)
- Pressure drops across long pipe runs
- Pump placement affects flow rates

This turns fluid logistics into a tangible engineering challenge rather than "just connect it and hope."

---

# Questbook / Handhook Mechanic (NEW — FROM FAMILY IDEAS)

Informatron exists as our handbook base but **lacks quest/progression mechanics**. GTNH-style capability unlocking requires custom work.

## Research Direction: Can we modify Informatron?

- [ ] Investigate Informatron's addon/plugin API
- [ ] Determine if "capability unlock" entries are feasible on top of it
- [ ] If not feasible, plan a fork or separate mod

## Design for the Mod

The questbook should:
1. Show the **full industrial journey** (not hidden chapters)
2. Provide **capability unlocks** when tasks are completed — new recipes, systems, processes become available
3. Maintain **information availability before capability** — consistent with Pillar 9
4. Use Informatron as the display layer, quest mechanics as an extension

## Key Distinction from Existing Quest Mods

Existing mods (e.g., `factorio-quest-system`) generate **random challenge objectives**. Ours is **fixed progression**:
- Completing Task A unlocks Process B
- Not "here's a random challenge" but "here's the next step in your industrial education"

---

# Mission Statement

> Build a coherent industrial ecosystem where extraction, refining, metallurgy, chemistry, power generation, pollution, military pressure, semiconductors, and the endgame all emerge from the same design philosophy.

Or more simply:

> Angel's equilibrium, GTNH's ambition, Satisfactory's meaningful choices, Dyson Sphere Program's vision, and Factorio's clarity.
