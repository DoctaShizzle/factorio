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

# Mining, Refining & Metallurgy

The working design and examples have moved to [mining-refining-metallurgy.md](mining-refining-metallurgy.md).

The material inventory and dependency sketch remain in [material-chain-map.md](material-chain-map.md).

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

# Programmable Logic Controllers (NEW — FROM FAMILY IDEAS)

## Vision: A General-Purpose Factory Control Language

A programmable controller for industrial automation. Not a circuit-logic toy, not a constrained template builder — a general-purpose control system embedded in Factorio.

### What It Does

Players write programs that:
- Read sensor data from any connected machine (flow rate, temperature, pressure, tank levels, item throughput)
- Control machines dynamically (start/stop pumps, open/close valves, adjust machine modes, cycle between recipes)
- Implement feedback loops autonomously (tank full → redirect flow → throttle production)
- Enable true "smart factories" that self-regulate based on factory state

### Why General-Purpose?

Constraint-based systems work until they don't. A player who can only do pre-built templates will hit the edge of those templates within hours of a serious factory. The moment they want "split this flow 60/40 if both tanks are above X but prioritize Y when Z happens" — templates fail.

A general-purpose control language gives players **expressive freedom**. Yes, it raises the learning curve. But this is an overhaul mod aimed at industrial engineers, not casual builders. The target audience **wants** to write code that controls their factory.

### Implementation Surface (Target Design)

- **PLC unit** — the hardware controller, with memory/slot limits scaling as a progression element
- **Text-based programming language** — in-game editor, not external files. Syntax designed for industrial logic: conditionals, loops, variables, functions, time/delay primitives
- **Sensor API** — read values from connected machines (fluid levels, temperatures, throughput counters, machine states)
- **Control API** — write commands to connected machines (start/stop, mode switches, valve positions)
- **Network connectivity** — wired connections + wireless range option. Programmed logic can't magically reach across the map without infrastructure
- **Debug tools** — watch variables in real-time, set breakpoints, step execution, log sensor snapshots
- **Modular architecture** — subroutines/functions for reusable control patterns (PID-like controllers, state machines)

### Language Design Considerations

Options to consider:
1. **Custom DSL** — purpose-built language with industrial semantics (like Structured Text / IEC 61131-3 subset). Easier to constrain and optimize, harder for programmers who want flexibility.
2. **Embedded Lua/Python** — use Factorio's existing scripting or a lightweight embedded VM. Leverages familiar languages, gives full expressiveness, but adds implementation overhead.
3. **Hybrid** — core control primitives in a simple DSL + optional advanced functions in a scriptable language

### MVP Stage

Even with general-purpose ambition, there's a practical minimum:
- Core PLC hardware unit
- Basic text editor with syntax highlighting
- 5-7 sensor inputs (fluid level, temperature, machine status)
- 5-7 control outputs (start/stop, mode toggle, valve open/close)
- Variables and conditionals (if/then/else)
- Loops with configurable delay
- Local network connectivity (wired only)

MVP scope: enough to write programs that actually solve real problems (production balancing, overflow protection, auto-startup sequences). Not just a proof of concept — genuinely useful.

### Full Vision

Beyond MVP:
- Custom data types and arrays
- Named functions/subroutines with parameters
- Interrupt handling for fault detection
- PID control loops for temperature/pressure regulation
- Wireless communication between PLCs (for distributed systems)
- Time-series data logging and visualization
- Simulation mode (test programs without affecting running factories)

### Connection to Design Pillars

**Pillar 3: Processes Instead of Recipes**
The PLC automates *industrial processes*, not conveyor logic. A player can write a program that manages refinery equilibrium automatically — the core mechanic becomes designing and programming the controller, not just placing machines.

**Pillar 8: Capabilities Over Numbers**
"I built a programmable control system for my chemical plant." This is a genuine capability milestone.

**Pillar 10: Configured Through Factory Design**
The PLC connects to machines physically (wired infrastructure), making automation a tangible engineering decision, not an abstract setting.

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

### UX Requirements (CRITICAL — this is what makes or breaks the system)

The most frustrating part of GTNH's power was diagnosing failures. We solve that with transparency:

**Hover diagnostics on poles/lines:**
```
400A @ 1000V
Loss: 2.3% per tile (copper, low-voltage)
Total drop: 87V over 38 tiles
Capacity remaining: 92%
```

**Onboarding requirement:**
Dedicated page/tutorial explaining:
- Why power grids exist (vs Factorio's "connect anything anywhere")
- Voltage = pressure analogy
- Resistance + distance = loss
- How to read the diagnostics overlay
- Common failure modes and how to fix them

The player should feel smart for solving a power problem — not confused by it.

This is the difference between GTNH's power system (opaque frustration) and this design (transparent complexity).

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
