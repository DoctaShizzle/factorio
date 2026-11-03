# Power System - Design Proposal

*For: Factorio Overhaul Mod*  
*Status: Concept / requirements phase*

Related documents: [Chemical Products and Processes](chemical-processes.md) for fuels and reagents; [Intermediate Products](intermediate-products.md) for nuclear materials, batteries, and endgame infrastructure; [Minerals and Refining](minerals-and-refining.md) for fuel-resource links; [Endgame Vision](endgame-vision.md) for late-game research network.

## Summary

This document defines the complete power architecture — from energy **production** through generator phases and fuel-density progression, to **transmission** across a factory grid with voltage tiers, conductor tradeoffs, loss modeling, and diagnostics. Power is an industrial decision layer, not a global infinite bus.

**What it covers:** Four phases of power generation (combustion → fission → fusion → simulation), fuel-density spectrum, infrastructure hooks per generator class, grid transmission model with voltage tiers, conductor material choices, transmission loss principles, required diagnostic overlays, and onboarding needs.

**What it does not cover:** Specific recipe ratios or exact MW/kWh values (to be defined during tuning); detailed fuel-cycling for fission/fusion (covered in [Intermediate Products](intermediate-products.md)); machine power consumption numbers; electrical engineering formulas — the model should teach a useful voltage/current/resistance analogy without requiring players to calculate circuits by hand.

## Core Design Principles for Power Production

1. **Generation choices create tradeoffs, not just raw output.** Compact dense fuels → pollution pressure; clean distributed sources → space pressure; complex supply chains → capital investment.
2. **Every generator class connects to the industrial ecosystem built earlier.** A player who has navigated chemistry, metallurgy, and refining should feel that new generation options are the payoff for that effort.
3. **Fuel density is a primary axis.** The mod's space-pressure design makes fuel-energy-per-unit-volume a meaningful comparison tool across phases.
4. **Progression feels earned but not gated by artificial difficulty.** Each phase opens through capability unlocks (chemical plants, nuclear fabrication, fusion infrastructure), not by making the previous tier too weak to use.
5. **No generator is universally superior.** Tradeoffs exist in resource cost, space footprint, pollution output, maintenance, and supply-chain complexity.

## Four Phases of Power Production

### Phase 1: Combustion (Early Game)

*Accessible from the start; the foundational power mode for every factory.*

| Generator type | Fuel source | Design role | Key tradeoff |
|---|---|---|---|
| Steam engine (thermal) | Any solid fuel (coal, coke, wood, charcoal, processed carbon feeds) | Universal early-game generator; teach that *fuel density → power density* | Burns any combustible solid; player learns to rank fuels by energy content without needing a dashboard |
| Gasifier / producer-gas reactor | Coal or coal-derived feedstock + controlled air/steam input | Bridges coal mining to power production; unlocks via chemical-process capability | Produces synthetic fuel (producer gas) from solid coal; higher efficiency than direct burning but needs water, reagent handling, and off-gas management |
| Liquid-fuel burner | Oil-derived fuels or Fischer-Tropsch synthetic fuels | Higher-density combustion when petrochemistry is available | Requires oil extraction, refining, and possibly catalytic synthesis infrastructure — the player earns high-density fuel through chemistry |

**Phase 1 design notes:**
- The core lesson of Phase 1: **fuel density matters.** Coal beats coke; refined hydrocarbon beats coal; producer gas sits between. This teaches that *how* you refine your fuel is as important as *what* you burn.
- Pollution pressure from dirty combustion routes (unscrubbed sulfur, unfiltered off-gas) creates the first military-pressure driver — connecting power production to the military system.
- Steam engines should use *any combustible solid*, not just coal. This rewards creative fuel recycling (charcoal from biomass, coke from coal, processed carbon from chemical plants) without forcing it.

### Phase 2: Fission (Mid Game)

*Requires nuclear fuel fabrication infrastructure; unlocks when the player has built enrichment/fuel-conversion capability.*

| Generator type | Fuel source | Design role | Key tradeoff |
|---|---|---|---|
| Thermal fission reactor | Uranium oxide fuel pellets (enriched U-235 or Pu-239) | Dense, sustained power independent of fuel supply chains once built | Massive upfront resource cost (refractory steel, zirconium cladding, graphite moderator); requires fuel fabrication chain; waste/cooling demands create ongoing operational tension |
| Optional: Thorium breeder reactor | Thorium feed + neutron source → bred U-233 | Long-horizon alternative fission cycle; late-mid game capability | Requires monazite prospecting and thorium processing; breeding time creates a "start once, run forever" feel with delayed payoff |

**Phase 2 design notes:**
- Fission power density should be **orders of magnitude higher** than combustion, creating massive spatial relief for the factory. However, the *fabrication cost* of a reactor (stainless steel pressure vessel, zirconium cladding, graphite moderator, control rods with hafnium/boron absorbers) is substantial.
- Cooling is a genuine requirement — not just a number but physical infrastructure (heat exchangers, fluid transport, condensers). This connects to thermal management in endgame facilities.
- **Meltdown risk** (GTNH-inspired): The reactor requires *continuous active cooling*, even when the factory grid is offline. If power is lost and backup batteries/dead-battery capacitors deplete, the core begins a visible escalation: elevated temperature → increased pressure → fuel rod stress → potential meltdown. Each stage has clear UI feedback (thermal indicators, pressure gauges, warning alarms), giving the player time to react — route emergency power, start passive cooling loops, or initiate safe shutdown.
- The tension is not "does fission work?" but "can I keep it cool when everything else fails?" This makes thermal redundancy a meaningful engineering decision rather than a punishment loop. A player who invested in grid diversity and load-shedding diagnostics (see Diagnostics section) will have built-in resilience.
- Fission creates **breathing room from military pressure** if operated cleanly. No combustion pollution means fewer attacks, giving the player a choice: dense power without the military consequence.

### Phase 3: Fusion (Late Game)

*Requires fusion fuel infrastructure; connects to the deepest mining and chemistry of the mod.*

| Generator type | Fuel source | Design role | Key tradeoff |
|---|---|---|---|
| Tokamak-class fusion reactor | Deuterium (from water electrolysis/concentration) + tritium (bred from lithium blanket) | Near-infinite fuel supply; ultimate density; requires the deepest industrial chain in the mod | Massive construction cost: tungsten armor, Nb3Sn/NbTi superconducting conductors, lithium breeder processing, precision structural steel; fuel itself is essentially limitless once built |
| Magnetic confinement (advanced) / inertial fusion (optional) | Same D-T fuel; different confinement approach | Alternative design path with different material demands and operational characteristics | Remains optional — different reactor designs emphasize different aspects of the industrial chain |

**Phase 3 design notes:**
- Fusion fuel is **effectively infinite**: deuterium from water, tritium bred from lithium. The constraint is not fuel supply but *infrastructure*.
- The fusion chain touches more parts of the mod than any other single capability: mining (tungsten, niobium/tantalum, lithium), chemistry (deuterium concentration, lithium processing), metallurgy (superconducting alloys, plasma-facing tungsten), and semiconductor electronics (magnet control systems).
- Fusion should be **the ultimate spatial relief** — a small footprint delivering enormous power. However, building the first fusion reactor should feel like a major project rivaling the endgame Core in scope.

### Phase 4: Micro-Verse Harvesting (Endgame / Optional)

*Connected to the Planetary Simulation Core; requires active computational partnership, not just research unlocks.*

| Generator concept | Principle | Design role | Key tradeoff |
|---|---|---|---|
| Micro-Verse Harvester (ZPM-inspired) | Casimir-effect cavity collapsed into a micro-parallel universe; harvested via vacuum fluctuations | Endgame energy frontier; optional capstone generator. Represents harnessing zero-point energy from an accessible parallel quantum vacuum | Requires Planetary Simulation Core as *active operational partner* for real-time stabilization; nanometer-scale fabrication precision (cleanroom, tantalum interconnects, ultra-pure silicon); no fuel supply chain but enormous infrastructure demand |
| Kugelblitz Array (alternate concept) | Optical concentrator array collapses intense radiation field into a micro-black hole; Hawking radiation harvested via thermal-to-electric conversion | Alternate endgame path emphasizing optics and high-power transmission over precision cavity fabrication | Ironic cycle: requires enormous power *to build* the concentrators, produces more than consumed after breakeven; needs extreme-voltage infrastructure and precision mirror/glass fabrication |

**Phase 4 design notes:**
- **The simulation is operationally required**, not just a research gate. For the Micro-Verse Harvester:
  - The Planetary Simulation Core must compute *which vacuum fluctuations are extractable* from the target universe's quantum structure (the cavity geometry depends on real-time predictions of zero-point energy density)
  - It stabilizes the *nascent micro-universe against vacuum decay* — computing spacetime boundary conditions faster than they evolve, feeding correction parameters to the device's electromagnetic containment field
  - As the micro-verse evolves, the simulation must *adapt extraction parameters* (cavity tuning, harmonic dampening) or efficiency degrades and risk of vacuum fluctuation feedback increases
- The Kugelblitz variant also requires active simulation: predicting Hawking radiation spectrum for thermal conversion optimization, modeling the collapse dynamics to prevent containment breach.
- **Harder constraint is fabrication precision, not fuel supply.** Building a nanometer-scale Casimir cavity demands semiconductor-grade silicon wafers, ultra-pure tantalum interconnects, cleanroom fabrication facilities, and precision metrology equipment. The simulation tells you *what* to build and *how to keep it stable* — it doesn't replace those material demands.
- **The ironic Kugelblitz cycle:** You need enormous power to construct the optical concentrator array (feeding high-intensity light into a collapsing field), but once the micro-black hole stabilizes, its Hawking radiation output exceeds your construction power input. The breakeven point depends on concentrator precision — more precise mirrors = earlier breakeven.
- Both concepts connect the endgame simulation network to *something tangible* — not just "research unlock" but an ongoing operational dependency that makes the Planetary Simulation Core feel like an indispensable factory asset, not a prestige project.
- Should *not* be required for victory. These represent what happens when the player has demonstrated mastery of every industrial domain and wants to push beyond conventional physics. The simulation research connection comes from [Endgame Vision](endgame-vision.md).

**Phase 4 vs Phase 3 boundary question:** At what point does "advanced fusion" end and "micro-verse harvesting" begin? The distinction should be clear: fusion manipulates *existing* fundamental forces (electromagnetic confinement of plasma); micro-verse harvesting creates *new spacetime structure* accessible to conventional physics. This is a research-design decision pending deeper alignment with endgame-vision.md.

## Fuel Density Spectrum (Reference Guide)

The mod's space-pressure design makes fuel density a critical comparison axis. This table organizes candidate fuels by energy-per-unit-volume, mapped to their game-phase and industrial connections:

| Phase | Fuel candidate | Source chain connection | Relative density |
|---|---|---|---|
| 1 (combustion) | Wood / biomass | Biomass processing or plant matter | Very low |
| 1 (combustion) | Charcoal / carbonized biomass | Carbonization from raw biomass | Low |
| 1 (combustion) | Coke / processed carbon | Coal carbonization | Medium |
| 1 (combustion) | Coal (raw mined) | Surface or underground mining, Tier 1–2 deposit | Medium-high |
| 1 (combustion) | Producer gas (coal gasification) | Bosch-Messig / Lurgi coal gasifier + steam/air | Medium (volumetric; gaseous fuel has inherent density limits) |
| 1→2 transition | Crude oil / refined hydrocarbon fuels | Oil extraction, fractionation, catalytic cracking | High — liquid fuels dominate the density axis |
| 1→2 transition | Fischer-Tropsch synthetic fuels (gasoline/diesel/paraffin) | Coal gasification → syngas → FT synthesis | High — bridges coal to high-density fuel when oil is unavailable |
| 2 (fission) | Uranium oxide fuel pellets (enriched) | Uraninate mining → conversion → enrichment → pellet fabrication | Extreme — orders of magnitude above combustion fuels |
| 2 (fission, optional) | Plutonium / bred U-233 | Thorium breeder cycle or plutonium recycling | Extreme — alternative long-horizon fuel |
| 3 (fusion) | Deuterium + tritium (D-T) | Water concentration → deuterium; lithium breeder → tritium | Extreme — near-infinite supply, requiring infrastructure not fuel extraction |

**Key insight:** The progression from Phase 1 to Phase 2 is a **~10,000x density jump**. This makes the spatial relief of nuclear power profound and should be communicated through factory-scale comparison (one reactor replacing dozens of generators). Phase 3's advantage is not just more power — it's *sustainable* dense power with effectively infinite fuel.

## Infrastructure Hooks per Generator Class

### Combustion Generators
- **Steam engine:** Simplest; one input (solid fuel), one output (electricity). Pollutant off-gas connects to military pressure. Can use water cooling loop.
- **Gasifier:** Requires coal feed + steam injection + air control. Produces combustible gas that feeds the generator. Needs gas storage/buffering. Connects to chemical-process capability.
- **Liquid-fuel burner:** Requires fuel tank input. Higher combustion efficiency than solid burning. Off-gas scrubbing option connects to pollution mitigation (military system).

### Fission Generators
- **Pressure vessel / core:** Requires refractory steel, zirconium cladding, graphite moderator, hafnium/boron control absorbers.
- **Heat exchanger loop:** Transfers reactor heat to steam → turbine or directly to power conversion. Requires fluid transport infrastructure (pipes, pumps).
- **Fuel fabrication line:** Uranium concentration → conversion → pellet pressing → sintering → cladding. Parallel chain from minerals-and-refining through chemistry.
- **Waste handling:** Spent fuel storage; optional reprocessing pathway (plutonium extraction) connects to military system's nuclear-ammo scope.

### Fusion Generators
- **Tungsten plasma-facing armor:** Refined tungsten tiles/tiles assembly. High-material-demand, late-game construction milestone.
- **Nb3Sn/NbTi superconducting magnet coil:** Niobium + tin/titanium processing + cryogenic wiring. Connects to metallurgy and specialty-alloy chains.
- **Lithium breeder blanket module:** Lithium-bearing ceramic or liquid feed → processed into breeding form → assembled module. Direct link to mineral-refining (spodumene, brine) and chemical processing.
- **Deuterium concentration facility:** Electrolysis + concentration cascade from water source. Tied to chlor-alkali capability for hydrogen production.

### Endgame Simulation Generators
- **Micro-Verse Harvester:** Requires cleanroom facility (nanometer-scale Casimir cavity fabrication), active Planetary Simulation Core connection for real-time boundary stabilization, precision metrology equipment, ultra-pure tantalum interconnects, semiconductor-grade silicon wafers.
- **Kugelblitz Array:** Requires optical concentrator infrastructure (precision glass/mirror array, coated silicon elements), extreme-voltage power transmission systems, containment structures, active simulation network for Hawking radiation spectrum prediction.
- Both concepts require the Planetary Simulation Core as *operational* infrastructure — not just a research unlock, but an ongoing real-time computational partner.

## Design Tensions to Resolve

| Tension | Options | Recommended approach |
|---|---|---|
| Combustion pollution as military driver | Make all combustion pollute; or let scrubbing/scrubbed-fuel eliminate pollution | Pollution should be a *process choice* — clean fuel or scrubbing removes the pressure, but each option has its own cost (space, complexity, resources) |
| Fusion: too strong too early? | Gate behind endgame network commissioning; or gate behind fusion-research from simulation model | Fusion should require deep industrial capability (tungsten refining, niobium-titanium alloy, lithium processing, precision control), which naturally gates it to late-game without arbitrary research walls |
| Fission: is it too convenient? | Add maintenance, waste-accumulation, or meltdown risk; or keep it simple and let fabrication cost be the gate | **Meltdown risk via cooling dependency** — GTNH-inspired. The reactor requires continuous active cooling. If grid power is lost and backup capacitance depletes, the core escalates: elevated temperature → increased pressure → fuel rod stress → potential meltdown. Each stage has clear UI feedback (thermal indicators, pressure gauges, warning alarms) giving time to react. This makes thermal redundancy a meaningful engineering decision rather than punishment — players who invested in grid diversity and load-shedding diagnostics have built-in resilience. |
| Space pressure from renewables vs. density axis | Do we include solar/wind as explicit generators? Or let the density axis speak for itself | **Option A:** Include a compact "solar array" machine with area-dependent output, built from semiconductor-grade silicon — connecting to the wafer/processor chain but requiring raw cells and glass. **Option B:** Let the *concept* of distributed renewables exist as design flavor (see military-system.md's space pressure section) without building explicit solar/wind generators. |
| Fusion fuel: infinite power → does it remove all tension? | No — the *construction cost* is enormous, and once built, the generator may still need cooling, maintenance, or grid integration. The tension shifts from "can I afford fuel?" to "where do I put this facility?" | Emphasize placement/logistics over supply. Fusion solves the fuel problem but creates an *infrastructure* challenge: connecting massive power output to the grid, managing heat rejection, and protecting against grid surges |
| Phase 4 (simulation-driven) scope | Define it concretely with simulation dependency; or leave as placeholder for endgame finalization | **Micro-Verse Harvester** (ZPM-inspired: player-built Casimir cavity that collapses into a micro-parallel universe, harvested via vacuum fluctuations) with the Planetary Simulation Core as *active operational infrastructure* — not just a research unlock. The simulation computes initial cavity geometry, stabilizes spacetime boundaries in real-time, and tunes extraction parameters as the micro-verse evolves. **Alternate: Kugelblitz Array** (optical concentrators collapse radiation into a micro-black hole; Hawking radiation harvested). Both tie to simulation meaningfully without requiring map-placed black holes. |

## Open Design Decisions (Power Production)

- **Which exact combustion generators appear in Phase 1?** Steam engine (universal), gasifier (chemical bridge), liquid-fuel burner? What about compacted-compressed biomass options?
- **Should fission include both U-235 and Pu-239 paths** with separate fuel chains, or a single enriched-fuel path that optionally includes plutonium recycling?
- **How does fusion connect to the endgame network?** Is fusion itself an endgame milestone, or is it parallel to (or prerequisite for) the Planetary Simulation Core?
- **What about geothermal power taps?** Factorio's vanilla map has oil/water wells at specific locations. Should the mod add geothermal resource sites that act as natural generator locations (like Satisfactory's geothermal generators)?
- **Should any renewable generation exist explicitly** (solar panels, wind turbines), or should the "clean but space-hungry" alternative be communicated through gameplay experience and handbook text only?
- **How much does each generator class contribute to military pressure?** Clean combustion (scrubbed) vs. dirty combustion; fission's thermal pollution; fusion's zero-emission profile — these affect the player's decision calculus.
- **Is waste handling for fission a meaningful mechanic** (spent fuel storage, reprocessing choice) or just flavor text with an item input?

## Design Intent

Power should be a factory-design decision, not a global infinite bus. Local generation, industrial clustering, conductor choice, and transmission infrastructure should matter, while diagnostics make losses and limits understandable.

Power and floor space are secondary optimization axes in the overall design. They should create meaningful tradeoffs without becoming opaque punishment or maintenance busywork.

Power should be a factory-design decision, not a global infinite bus. Local generation, industrial clustering, conductor choice, and transmission infrastructure should matter, while diagnostics make losses and limits understandable.

Power and floor space are secondary optimization axes in the overall design. They should create meaningful tradeoffs without becoming opaque punishment or maintenance busywork.

## Candidate Grid Model

### Transmission Tiers

- **Low-voltage distribution:** local wiring for small loads and early factories, with limited reach and capacity.
- **High-voltage transmission:** long-distance lines for large or remote loads, with conversion stations between local and transmission networks.
- **Transformation stations:** step voltage up for transmission and down for industrial consumers; placement and capacity are factory layout choices.

Exact voltages, distances, and conversion ratios remain undecided. The model should teach a useful voltage/current/resistance analogy without requiring players to perform electrical engineering calculations by hand.

### Conductor Materials

Candidate conductor materials can trade cost, capacity, transmission loss, and physical placement:

| Conductor | Candidate role |
| --- | --- |
| Tin | Cheap early/local wiring with lower capacity |
| Copper | Reliable general-purpose conductor |
| Aluminum | Lightweight, long-distance transmission option |
| Gold | High-performance specialist conductor for late-game precision or compact high-load networks |

These roles are initial design hypotheses; the final list should follow the approved material roster and avoid making rare metals mandatory for ordinary factory power.

### Transmission Losses and Factory Layout

Transmission losses should depend on line length, conductor properties, voltage tier, and load. This should make remote power generation and industrial clusters situationally valuable, not universally superior. Generators may be placed near large process loads to avoid long-haul loss, while high-voltage lines can connect separated facilities when their infrastructure cost is worthwhile.

## Diagnostics and Onboarding

Power diagnostics are a core feature, not a later polish task. A pole, transformer, or line overlay should make it easy to inspect:

- Voltage tier and current load
- Connected capacity and remaining headroom
- Estimated loss per segment and cumulative transmission loss
- The limiting segment or reason a consumer is underpowered

The interface should use clear units and concise messages. Early onboarding should explain local versus long-distance distribution, the voltage analogy, why transformers exist, and common failure causes. Numerical examples are illustrative only until the power model is tuned.

## Connections to Other Systems

- Steel and alloy choices provide conductor options.
- Electrolysis, electric furnaces, cleanrooms, and semiconductor fabrication create distinct load profiles.
- High-demand process clusters can motivate local generation or dedicated transmission.
- The endgame network needs reliable power and may justify specialized low-loss distribution as an optional capability.

## Design Guardrails

- Explain every limit and loss in the UI; avoid hidden grid failures.
- Make early power simple to establish and diagnose.
- Let infrastructure and factory layout solve power problems; do not require PLC programming for basic grid stability.
- Use PLCs for optional advanced control, load shedding, and power-plant coordination.
- Treat exact voltage tiers, loss formulas, conductor stats, and machine behavior as open design decisions until tested together.

## Reference Inspiration

GTNH demonstrates that voltage tiers and current capacity can create engineering choices; its opaque failure diagnosis is the caution. The overhaul should preserve the meaningful constraints and make grid state legible at a glance.
