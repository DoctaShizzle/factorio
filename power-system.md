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

### Phase 4: Near-Realistic Sci-Fi Endgame Power Generation (Endgame / Optional)

*Connected to the Planetary Simulation Core; requires active computational partnership, not just research unlocks.*

Both concepts below represent physics-grounded energy generation that goes beyond conventional fusion. Neither is required for victory. Each connects meaningfully to the simulation network — not as a simple research gate, but as an operational requirement during construction and/or operation.

| Generator concept | Principle | Design role | Key tradeoff |
|---|---|---|---|
| Hawking Radiation Engine (Option B) | Contained micro-black hole emitting Hawking radiation; harvested via thermal-to-electric conversion | Endgame energy engine with finite operational lifetime extendable by feeding matter. Physics-grounded: Hawking radiation is a derived result from QFT in curved spacetime; analog Hawking radiation has been demonstrated in laboratory settings using sonic horizons | Construction requires enormous one-time power draw to *create* the singularity (optical concentrators collapse radiation until field collapse); operational lifetime finite but extendable by feeding matter (mass → energy via E=mc²); smaller = more efficient but evaporates faster; requires precision optics, extreme-voltage infrastructure, superconducting containment |
| ZPM-style Subspace Capacitor (Option A) | Player-built device that creates an artificial pocket of subspace-time and extracts zero-point energy until the pocket reaches maximum entropy (equilibration with our universe's vacuum state); then collapses into a dead crystal shell — not infinite but lasting thousands of years at moderate draw | Stargate-inspired capstone generator representing reverse-engineered Ancient physics. Finite, player-constructed, no map-placed power sources found | Construction requires the Planetary Simulation Core to compute precise spacetime boundary conditions for *this planet's* specific properties (rotation, magnetic field, composition); fabrication demands ultra-pure silicon wafers, tantalum alloy containment lattice, precision crystal resonators, quantum computation module; no fuel supply chain but massive construction project; each capacitor is finite and must be replaced when depleted |

**Option B: Hawking Radiation Engine — design notes:**
- **Construction phase (massive power investment):** Player builds an optical concentrator array (precision glass/mirror elements from optics chain) that collapses a concentrated radiation field into a micro-singularity. This requires enormous input power to achieve the threshold for radiation-pressure collapse. Ironic cycle: you need more power to build it than it produces initially — but once stable, output exceeds construction draw.
- **Operational phase (finite but extendable):** The contained micro-black hole emits Hawking radiation at a predictable spectrum (computed by the Planetary Simulation Core). Thermal-to-electric converters harvest this as power. The black hole's mass decreases over time as it radiates — its operational lifetime is finite, inversely proportional to initial mass.
- **Feeding matter to extend life:** Player can feed concentrated matter/fuel into the singularity (mass → energy via E=mc²). This extends operational life but costs resources: you trade material inputs for power output at a predictable rate. Different fuel types have different mass-energy yields, connecting back to the fuel-density spectrum.
- **Smaller = faster evaporation:** The physics is unforgiving here — smaller initial black hole has higher Hawking temperature (more efficient thermal conversion) but evaporates much faster. Player chooses: compact fast-burning engine vs. massive slow-dying one. This creates a meaningful size-vs-lifetime tradeoff with real engineering consequences.
- **Simulation's role:** Computes Hawking radiation spectrum for thermal converter optimization, models collapse dynamics during construction to prevent containment breach, predicts remaining lifetime based on feeding schedule.

**Option A: ZPM-style Subspace Capacitor — design notes:**
- **Construction is the challenge, not fuel supply.** The player constructs a Subspace Capacitor device (not finding pre-made artifacts on the map). Construction is an endgame project rivaling the first fusion reactor in scope:
  - Cleanroom facility with nanometer-scale precision fabrication
  - Ultra-pure silicon wafer production (semiconductor chain output)
  - Tantalum alloy containment lattice (forged under extreme pressure/temperature)
  - Precision crystal resonators (advanced optics/optical glass chain)
  - Quantum computation module (simulation chip output from Planetary Simulation Core infrastructure)
- **The simulation computes the pocket.** The Planetary Simulation Core is used *once during construction* to compute boundary conditions needed to stabilize the pocket against collapse — essentially running a quantum field theory simulation at nanometer scales where no lab instrument can directly measure. The simulation determines precise cavity plate spacings that extract specific frequency ranges from vacuum fluctuations, and calculates harmonic dampening parameters to prevent destabilization.
- **Research investment matters.** Years of using the simulation network to understand quantum vacuum behavior unlock different cavity designs with different energy extraction rates and stability profiles. Better theoretical understanding → more efficient device. The player's investment in simulation research earlier determines what designs they know how to optimize — not different planet properties, but deeper physical models.
- **The simulation connection is about modeling complexity:** stabilizing a subspace pocket requires solving QFT equations at scales where perturbative approximations break down. Only a full quantum field simulation can predict which cavity geometries remain stable long enough for practical energy extraction.
- **Finite but huge.** Each capacitor lasts thousands of years at moderate power draw, less under heavy draw. When depleted (pocket equilibrated with our universe's vacuum state), it becomes a dead inert crystal shell — no refueling, just construct another. This respects the requirement that endgame power be realistically finite when scaling to planetary levels.
- **Simulation connection:** The Planetary Simulation Core is not optional for building or maintaining these devices. Different planet types yield different pocket properties (energy density, longevity). The more sophisticated your simulation data, the better capacitor you can construct. This connects late-game research investment directly to endgame infrastructure quality.

**Player education — informatron/guidebook entries:**
- Both Phase 4 options have **dedicated physics pages** in the player's guidebook (informatron or equivalent). These explain the underlying science at increasing levels of depth:
  - **Fission entry:** How nuclear binding energy works, why splitting heavy nuclei releases energy, mass defect → E=mc², chain reactions, why enrichment is necessary
  - **Fusion entry:** How light nuclei fusion overcomes Coulomb barrier, binding energy curve peak near iron-56, why extreme temperature/pressure needed, magnetic confinement principles, the D-T reaction
  - **Phase 4 entries (both options):** Hawking radiation derivation from QFT in curved spacetime (accessible explanation: event horizons create particle pairs where one escapes); quantum vacuum structure and Casimir cavities (why precisely spaced plates matter for zero-point extraction); why artificial subspace pockets can be stable (and what happens when they're not)
- The guidebook doesn't assume prior physics knowledge but rewards players who engage with the deeper explanations. Early-game summaries explain *what* happens; advanced entries explain *why* — accessible to any player willing to read.

**Common design principles for both Phase 4 concepts:**
- Neither requires finding pre-made power sources on the map — everything is player-built from the mod's industrial chain
- Both connect the Planetary Simulation Core to something tangible, not just "research unlock" flavor
- The simulation provides computational value (boundary conditions, spectrum prediction, lifetime modeling) rather than replacing material constraints
- Neither is required for victory; these represent pushing beyond conventional physics after demonstrating mastery of every industrial domain
**Design rationale: Hawking Engine preferred over Subspace Capacitor**

The original Phase 4 design considered two options — Hawking Radiation Engine (Option B) and ZPM-style Subspace Capacitor (Option A). Below is a design assessment for reference during development discussions. The recommendation is to **keep Option B as the primary/sole Phase 4 generator** and drop Option A.

| Criterion | Option B: Hawking Engine | Option A: Subspace Capacitor |
|---|---|---|
| **Ongoing gameplay loop** | Strong — player feeds matter into the singularity, connecting to fuel-density spectrum, logistics, supply chains. Every feed event is a micro-decision about efficiency vs. resource cost | Weak — build once, forget for thousands of years. No ongoing interaction, no tension after construction |
| **Meaningful tradeoff** | Size-vs-lifetime (smaller = faster evaporation but higher thermal conversion). Different feeding choices yield different strategies. No single right answer | One dimension only: "how big/efficient do I build it?" After construction, nothing happens |
| **Factorio rhythm fit** | Excellent — one machine, constantly operational with a maintenance loop. Fits construction → supply chain → optimization core loop | Poor — functions as a battery, not a generator. Removes player from gameplay rather than engaging them |
| **Physics intuition** | High — players can picture a micro-black hole emitting radiation; the concept is accessible and awe-inspiring | Low — quantum Casimir cavity plate spacings are hard to visualize; harder for players to emotionally engage with the "why" |
| **Differentiation from fusion** | Clear — fusion = near-infinite fuel, one-time build. Hawking Engine = finite lifetime, requires ongoing matter delivery, creates supply chain tension | Weak — too similar to fusion in gameplay shape. Both are "build once, get power forever." Doesn't add distinct value |

**Key insight:** Fusion already fills the slot of "no-fuel-supply-chain endgame power." The Subspace Capacitor does not create a *different kind* of engagement from the Hawking Engine — it creates a *less engaged* version. Factorio players benefit from options that feel different, not variants on "store energy."

**The one case for keeping Option A:** if you want an endgame option for players who truly want infinite power with zero maintenance burden. But that's exactly what fusion provides. Adding a second option with the same gameplay shape doesn't serve the design — it just gives another way to do what fusion already does.

**Verdict:** Keep Hawking Engine. It creates genuine ongoing tension (size choice, feeding logistics, finite lifetime), connects to multiple systems (optics chain, matter delivery, simulation network, fuel-density spectrum), and tells a compelling sci-fi story players can understand. Drop Option A. At what point does "advanced fusion" end and "endgame physics-driven generation" begin? The distinction should be clear: fusion manipulates *existing* fundamental forces (electromagnetic confinement of plasma); Phase 4 creates *new physical structures* in spacetime itself — either an artificial pocket of subspace or a controlled singularity. This is a research-design decision pending deeper alignment with endgame-vision.md.

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

### Endgame Physics-Driven Generators
- **Hawking Radiation Engine:** Requires optical concentrator infrastructure (precision glass/mirror array, coated silicon elements), extreme-voltage input power systems for singularity creation, superconducting magnetic containment structures, thermal-to-electric conversion loop, active simulation network for Hawking radiation spectrum prediction and lifetime modeling. Feeding matter into the singularity connects back to fuel-density spectrum.
- **Subspace Capacitor:** Requires cleanroom facility (nanometer-scale precision fabrication), ultra-pure silicon wafer production chain, tantalum alloy containment lattice forging, precision crystal resonators (advanced optics), quantum computation module, Planetary Simulation Core during construction for spacetime boundary condition computation. Each capacitor is finite but lasts thousands of years at moderate draw.
- Both concepts require the Planetary Simulation Core as *operational* infrastructure — not just a research unlock, but active computational partner during construction and/or ongoing operation.

## Design Tensions to Resolve

| Tension | Options | Recommended approach |
|---|---|---|
| Combustion pollution as military driver | Make all combustion pollute; or let scrubbing/scrubbed-fuel eliminate pollution | Pollution should be a *process choice* — clean fuel or scrubbing removes the pressure, but each option has its own cost (space, complexity, resources) |
| Fusion: too strong too early? | Gate behind endgame network commissioning; or gate behind fusion-research from simulation model | Fusion should require deep industrial capability (tungsten refining, niobium-titanium alloy, lithium processing, precision control), which naturally gates it to late-game without arbitrary research walls |
| Fission: is it too convenient? | Add maintenance, waste-accumulation, or meltdown risk; or keep it simple and let fabrication cost be the gate | **Meltdown risk via cooling dependency** — GTNH-inspired. The reactor requires continuous active cooling. If grid power is lost and backup capacitance depletes, the core escalates: elevated temperature → increased pressure → fuel rod stress → potential meltdown. Each stage has clear UI feedback (thermal indicators, pressure gauges, warning alarms) giving time to react. This makes thermal redundancy a meaningful engineering decision rather than punishment — players who invested in grid diversity and load-shedding diagnostics have built-in resilience. |
| Space pressure from renewables vs. density axis | Do we include solar/wind as explicit generators? Or let the density axis speak for itself | **Option A:** Include a compact "solar array" machine with area-dependent output, built from semiconductor-grade silicon — connecting to the wafer/processor chain but requiring raw cells and glass. **Option B:** Let the *concept* of distributed renewables exist as design flavor (see military-system.md's space pressure section) without building explicit solar/wind generators. |
| Fusion fuel: infinite power → does it remove all tension? | No — the *construction cost* is enormous, and once built, the generator may still need cooling, maintenance, or grid integration. The tension shifts from "can I afford fuel?" to "where do I put this facility?" | Emphasize placement/logistics over supply. Fusion solves the fuel problem but creates an *infrastructure* challenge: connecting massive power output to the grid, managing heat rejection, and protecting against grid surges |
| Phase 4 (simulation-driven) scope | Define it concretely with simulation dependency; or leave as placeholder for endgame finalization | **Two documented options, neither required for victory:** <br>**Option B: Hawking Radiation Engine** — optical concentrators collapse radiation into a micro-black hole; Hawking radiation harvested. Finite lifetime extendable by feeding matter (mass → energy). Simulations predict spectrum/lifetime and model collapse dynamics.<br>**Option A: Subspace Capacitor** — player-built device creating artificial subspace pocket; extracts zero-point energy until entropy equilibrium. Simulation computes boundary conditions during construction; different planets yield different yields. Finite but lasts thousands of years at moderate draw.<br>Both tie to simulation meaningfully without requiring map-placed black holes or finding pre-made ZPMs on the map. |

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
