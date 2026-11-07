# Power System - Design Proposal

*For: Factorio Overhaul Mod*  
*Status: Concept / requirements phase*

Related documents: [Chemical Products and Processes](chemical-processes.md) for fuels and reagents; [Intermediate Products](intermediate-products.md) for nuclear materials, batteries, and endgame infrastructure; [Minerals and Refining](minerals-and-refining.md) for fuel-resource links; [Endgame Vision](endgame-vision.md) for late-game research network.

## Design Decisions

| Decision | Resolution | Date |
|----------|-----------|------|
| **Core mod power delivery** | All generators feed vanilla Factorio pole grid. No voltage tiers, no transmission loss, no custom conductors. Generators produce different power outputs to create tradeoffs through placement pressure (proximity to loads). | 2026-11-07 |
| **Full power-system replacement (Approach C)** | Deferred as a future extension mod `power-transmission-override`. Would add voltage tiers, loss-bearing transmission lines, transformers, HVDC converter stations, grid diagnostics, and fault propagation. This is an opt-in complexity layer — not required for the core experience. | 2026-11-07 |

### Why Vanilla for Core?

Research into existing Factorio mods (Space Exploration, Bob's Mods, Pyanodons) confirms that all major overhaul mods use vanilla power poles. The closest comparisons:

- **Space Exploration** — adds fusion reactors and dozens of generator types but uses vanilla pole projection 100%. The SpEx author explicitly chose this to maintain mod compatibility and avoid rewriting Factorio's core power architecture.
- **Advanced Power Poles** — the most invasive dedicated power mod; it only adds larger poles with more range/capacity, not a new transmission system.
- **Bob's/Pyanodons** — deep chemistry/industry overhauls that still use vanilla poles entirely.

Replacing Factorio's pole-projection system would require rewriting one of the game's most fundamental C++ subsystems via Lua. This is: incompatible with other power mods; fragile across Factorio updates; and a massive additional engineering burden on top of ~80 new machines, 1200 items, and 4000 recipes already planned.

### What Approach C Would Add (Deferred Extension)

| Mechanic | Description |
|----------|-------------|
| Discrete transmission lines | Wires between poles as real entities with length-based power loss |
| Voltage tiers | 4-tier system (0–3) requiring transformers to step up/down |
| Transmission loss | % loss per 100 tiles, dependent on conductor material and voltage tier |
| HVDC converter stations | AC→DC conversion for ultra-long-distance endgame transmission |
| Grid diagnostics | Real-time display of load, capacity, loss, fault propagation |
| Fault propagation | Cascading brownouts when generators trip without stabilization |

This extension would create a parallel power architecture alongside vanilla poles — players could opt in entirely or mix both systems. It would be its own standalone extension pack (not bundled with core).

This document defines power **production** through generator phases and fuel-density progression. In the core mod, all generators deliver vanilla Factorio pole-grid power (no custom transmission). A **full replacement of Factorio's power system** (Approach C below) is deferred as a future extension mod.

**What it covers:** Four phases of power generation (combustion → fission → fusion → simulation), fuel-density spectrum, generator infrastructure requirements, and design intent for vanilla-compatible generators.

**What it does not cover in the core mod:** Voltage tiers, transmission loss modeling, conductors, transformers, or grid diagnostics — these are deferred to a potential `power-transmission-override` extension mod. See [Approach C: Full Replacement](#approach-c-full-replacement-deferred-to-extension-mod) below.

**What it does not cover anyway:** Specific recipe ratios or exact MW/kWh values (to be defined during tuning); detailed fuel-cycling for fission/fusion (covered in [Intermediate Products](intermediate-products.md)); machine power consumption numbers; electrical engineering formulas.

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

#### Reactor Core Assembly (infra.md §10)

| Component | Infrastructure Source | Power Requirements | Design Notes |
|-----------|----------------------|-------------------|--------------|
| Pressure vessel shell | Refractory steel panels + zirconium cladding ingots (infra.md §4 smelting) | Tier 2 welding/inspection infrastructure during construction | High-pressure coolant containment; rated for MTier 4 power at highest reactor tier |
| Graphite moderator blocks | Pure graphite from carbon processing chain | None directly, but thermal management critical | Neutron moderation without electrical input; precise spacing controlled by servo mechanisms (Automation §5) |
| Hafnium control rod assemblies | Hafnium Absorber Plate Liner + Boron Carbide Press/Sintering Furnace (infra.md §10) | Servo motors for insertion/extraction (~kW range); Tier 0 stable power | Neutron-absorbing plates with B₄C filler; tier determines reactivity control precision and lifespan |

#### Fuel Fabrication Chain — Parallel Supply Line (infra.md §10)

| Sub-component | Source (infra.md §10) | Power Needs | Design Notes |
|--------------|----------------------|-------------|--------------|
| Uranium Conversion Line | Leach/purification → precipitation → pellet pressing → sintering furnace (infra.md §10) | Tier 1 grid for chemical pumps, heaters, agitators | Parallel chain from minerals-and-refining through chemistry; each sub-step has independent power draw |
| Fuel Pellet Sintering Furnace | infra.md §10; refractory construction | Tier 2+ thermal process; draws heavy power during firing cycle | High-temperature densification; green pellets → sintered fuel pellets |
| Cladding Tube Mill | infra.md §10: Zr-alloy tube extrusion + pilger rolling | Tier 1 stable power for hydraulic forming systems | Produces hollow zirconium cladding for fuel rods; tier determines pressure vessel quality and precision |
| Fuel Rod Assembly Line (MTier 1-3) | infra.md §10: manual load → semi-auto → fully automated with inline inspection | Tier 1 grid; higher tiers add semiconductor inspection systems | Three sub-steps on one line: pellet loading → end-cap welding → helium leak-testing. MTier 3 adds automated QC with precision sensors (Automation §5) |
| Zr/Hf Separation Plant | infra.md §10: fractional distillation of chlorides + hydrometallurgical purification | Tier 2 grid for distillation columns and separation tanks | Critical nuclear gate — hafnium absorbs neutrons and must be removed for fuel-grade zirconium. Co-product: Hf for control rod absorber plates |

#### Waste Handling & Maintenance (infra.md §10 cross-reference)
- Spent fuel storage pools require active cooling pumps connected to power grid (Tier 0 or Tier 1 for reliable continuous operation)
- Optional reprocessing pathway (plutonium extraction from spent fuel) connects to military system's nuclear-ammo scope via plutonium feedstock
- Dead-Battery Capacitor / Fuse Link (Power Storage table above): safety device that intentionally depletes to shut down the core before meltdown; not reusable

### Fusion Generators

| Component | Infrastructure Source (infra.md) | Power Requirements | Design Notes |
|-----------|----------------------------------|-------------------|--------------|
| Tungsten Plasma-Facing Armor Tiles | infra.md §10: Tungsten Armor Tile Molder (Phase 4+) | Pre-assembly heating during fabrication; no operational power draw | High-material-demand construction milestone. Each tile sintered under extreme pressure/temperature |
| Nb₃Sn/NbTi Superconducting Magnet Coils | infra.md §10: Coil Winding Machine (MTier 2-4) | Cryogenic cooling during operation (~MW range); winding precision determines magnetic field strength | Niobium + tin/titanium processing + cryogenic wiring. Tier = winding tension control + insulation precision |
| Lithium Breeder Blanket Panels | infra.md §10: Lithium Breeder Blanket Panel Assembler (Phase 4+) | Liquid lithium circulation requires pumps connected to coolant loop; blanket fabrication is endgame project | Direct link to mineral-refining (spodumene, brine) and chemical processing |
| Deuterium Concentration Facility | infra.md §7: Chlor-Alkali Membrane Cell + AEM Water Electrolyzer | Sustained DC current for electrochemical separation; tier = membrane quality + electrode area | Concentration cascade from water source → fusion-grade D₂. Tied to chlor-alkali capability for H₂ production |
| Tokamak Vacuum Vessel Assembly | infra.md §10: Extreme-Pressure Containment Vessel Assembler (Phase 4+) | Tier 2+ welding inspection systems; autoclave curing of composite layers | Multi-layer pressure vessel shells for plasma containment. Weld forming → autoclave curing → in-situ inspection at high tiers |

### Endgame Physics-Driven Generators

#### Hawking Radiation Engine — Construction Infrastructure

The Hawking Engine requires four distinct endgame infrastructure categories from infra.md Section 10:

| Component | Source (infra.md) | Phase | Power Requirements | Role in Engine |
|-----------|-------------------|-------|-------------------|----------------|
| Precision Optics Fabrication Station | infra.md §10; Phase 4+, cleanroom required | Construction | Tier 0 stable power (cleanroom-grade) + precision servo motors (Automation §5) | Produces lenses/mirrors/interferometers for optical concentrator array that collapses radiation into micro-singularity |
| Extreme-Pressure Containment Vessel Assembler | infra.md §10; MTier 3+ required | Construction | Tier 2 infrastructure for welding inspection systems and autoclave curing | Welds multi-layer pressure vessel shells for singularity containment |
| Thermoelectric Conversion Array Module | infra.md §10; Phase 4+, p-type/n-type semiconductor junctions | Operational (power output, not consumption) | Connects directly to engine's Tier 3 HVDC output | Converts Hawking radiation heat to electricity via Seebeck effect; assembled from thermocouple pairs on semiconductor packaging line |
| Superconducting Magnetic Containment Structure | infra.md §10: Coil Winding Machine + Nb₃Sn/NbTi wire | Construction → Operation | Tier 3 power during winding operations; cryogenic cooling during operation | Maintains singularity within confinement field during construction phase; determines containment stability |

**Operational details:**
- **Feeding matter to extend life:** Player feeds concentrated matter/fuel into the singularity (mass → energy via E=mc²). Each fuel type has different mass-energy yield connecting back to the [fuel-density spectrum](#fuel-density-spectrum-reference-guide) table.
- **Size vs. lifetime tradeoff:** Smaller initial black hole has higher Hawking temperature (more efficient thermal conversion via Thermoelectric Array) but evaporates faster. Player chooses: compact fast-burning engine vs. massive slow-dying one.
- **Simulation's role:** Planetary Simulation Core computes Hawking radiation spectrum for Thermal Converter optimization, models collapse dynamics during construction to prevent containment breach, predicts remaining lifetime based on feeding schedule.

#### Subspace Capacitor — Reference Only (dropped per design rationale)

The Subspace Capacitor is kept as documentation only — see [Design rationale section](#design-rationale-hawking-engine-preferred-over-subspace-capacitor) above for why Option B was chosen over Option A. Its infrastructure requirements are:
- Cleanroom facility (nanometer-scale precision fabrication, infra.md §9)
- Ultra-pure silicon wafer production chain (infra.md §9: Czochralski Crystal Grower, CMP Polisher)
- Tantalum alloy containment lattice (forged under extreme pressure/temperature, infra.md §4)
- Precision crystal resonators (advanced optics/optical glass chain)
- Quantum computation module (simulation chip output from Planetary Simulation Core infrastructure)

**Note:** Both concepts require the Planetary Simulation Core as *operational* infrastructure — not just a research unlock, but active computational partner during construction and/or ongoing operation.

## Design Tensions to Resolve

| Tension | Options | Recommended approach |
|---|---|---|
| Combustion pollution as military driver | Make all combustion pollute; or let scrubbing/scrubbed-fuel eliminate pollution | Pollution should be a *process choice* — clean fuel or scrubbing removes the pressure, but each option has its own cost (space, complexity, resources) |
| Fusion: too strong too early? | Gate behind endgame network commissioning; or gate behind fusion-research from simulation model | Fusion should require deep industrial capability (tungsten refining, niobium-titanium alloy, lithium processing, precision control), which naturally gates it to late-game without arbitrary research walls |
| Fission: is it too convenient? | Add maintenance, waste-accumulation, or meltdown risk; or keep it simple and let fabrication cost be the gate | **Meltdown risk via cooling dependency** — GTNH-inspired. The reactor requires continuous active cooling. If grid power is lost and backup capacitance depletes, the core escalates: elevated temperature → increased pressure → fuel rod stress → potential meltdown. Each stage has clear UI feedback (thermal indicators, pressure gauges, warning alarms) giving time to react. This makes thermal redundancy a meaningful engineering decision rather than punishment — players who invested in grid diversity and load-shedding diagnostics have built-in resilience. |
| Space pressure from renewables vs. density axis | Do we include solar/wind as explicit generators? Or let the density axis speak for itself | **Option A:** Include a compact "solar array" machine with area-dependent output, built from semiconductor-grade silicon — connecting to the wafer/processor chain but requiring raw cells and glass. **Option B:** Let the *concept* of distributed renewables exist as design flavor (see military-system.md's space pressure section) without building explicit solar/wind generators. |
| Fusion fuel: infinite power → does it remove all tension? | No — the *construction cost* is enormous, and once built, the generator may still need cooling, maintenance, or grid integration. The tension shifts from "can I afford fuel?" to "where do I put this facility?" | Emphasize placement/logistics over supply. Fusion solves the fuel problem but creates an *infrastructure* challenge: connecting massive power output to the grid, managing heat rejection, and protecting against grid surges |
| Phase 4 (simulation-driven) scope | Define it concretely with simulation dependency; or leave as placeholder for endgame finalization | **Option B chosen:** Hawking Radiation Engine — optical concentrators collapse radiation into a micro-black hole; Hawking radiation harvested. Finite lifetime extendable by feeding matter (mass → energy). Simulations predict spectrum/lifetime and model collapse dynamics. Option A (Subspace Capacitor) dropped: same gameplay shape as fusion with less engagement. See "Design rationale" section above. |
| Grid transmission infrastructure: voltage tiers, conductors, transformers | How detailed should grid model be at this stage? | **Fully specified:** 4-tier voltage model (0–3), 5 conductor materials mapped to tiers, transformer MTier 1–3 progression with material upgrades. See Candidate Grid Model section below for complete catalog. |
| Underground power cable vs overhead towers | Should players have both; or pick one transmission aesthetic? | **Both:** overhead towers for early/mid-game (visual clarity, standard infrastructure), underground trench system for Phase 3+ (space savings, no line-of-sight constraints). Same conductor options in concrete conduit. |

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

## Candidate Grid Model — DEFERRED TO EXTENSION MOD

> All subsections below are **deferred** to the `power-transmission-override` extension mod discussed in [Approach C](#approach-c-full-replacement-deferred-to-extension-mod). They remain here as design reference only. **No materials, recipes, or infrastructure items for these concepts should be planned or added to the core mod.** When (and if) this extension is developed, these notes can be revisited.

### Voltage Tier Catalog

| Tier | Name | Power Range | Typical Reach (tiles/segment) | Primary Consumers |
|------|------|-------------|------------------------------|-------------------|
| 0 | Low-voltage distribution | 1–25 kW | Short (~50 tiles) | Generators (steam, solar, wind), small machine loads, early factories |
| 1 | Medium-voltage transmission | 25–250 kW | Medium (~200 tiles) | Industrial clusters (smelters, electrochemical cells, chemical reactors) |
| 2 | High-voltage transmission | 250 kW–2.5 MW | Long (~500 tiles) | Large fission reactors output feed, remote generator aggregation |
| 3 | Ultra-high-voltage DC (HVDC) | 2.5–25 MW | Very long (1000+ tiles) / unlimited with repeater stations | Endgame generators (fusion, Hawking Engine), planetary-scale grid backbone |

### Conductor Capabilities by Tier

| Conductor | Valid Voltage Tiers | Max Capacity per Segment | Transmission Loss Factor | Design Role |
| --- | --- | --- | --- | --- |
| Tin-plated copper wire | Tier 0 only | ~5 kW | 8% per 100 tiles | Cheap early/local wiring; low capacity, high loss |
| Copper cable | Tier 0–1 | ~25 kW | 4% per 100 tiles (T0), 3% per 100 tiles (T1 with transformer) | Reliable general-purpose conductor; sweet spot for most factory distribution |
| Aluminum wire | Tier 1–2 | ~100 kW | 2.5% per 100 tiles | Lightweight, long-distance transmission option; lighter than copper for equivalent capacity |
| Aluminum-steel composite cable | Tier 2 | ~500 kW | 1.5% per 100 tiles | Mid-game long-haul; cheaper than pure metal conductor for high-voltage segments |
| Gold alloy wire | Tier 3 | ~2 MW | 0.5% per 100 tiles | Endgame ultra-low-loss specialist conductor; extremely expensive, only viable for critical backbone segments |

### Transformer Progression by Tier

| Transformer Tier | Material / Components | Capabilities |
|-----------------|----------------------|---------------|
| MTier 1 (Iron-core) | Iron plates, basic copper windings, insulating ceramic | Basic step-up / step-down between adjacent tiers only (0→1 or 1→2). No load balancing. Single-input/output port |
| MTier 2 (Copper-wound + Tap Changer) | Refined copper wire, tap-changing switch, reinforced core | Step-up/step-down across one additional tier gap (0→2 allowed). Limited load balancing — can prioritize outputs under stress | Multi-port with directional flow control; allows asymmetric power routing |
| MTier 3 (Digital Monitoring + Active Load Balancer) | Semiconductor-grade sensors, programmable controller, gold-contact relays | Unlimited cross-tier conversion (0↔1↔2↔3). Real-time load balancing across all connected segments. Auto-detects and isolates overloads | Intelligent grid node — prevents cascade failures by cutting underloaded branches before they propagate |

### Generator-to-Voltage Mapping

Every generator has minimum voltage tier requirements for its output:

| Phase | Generator Type | Min Voltage Tier | Notes |
|-------|---------------|------------------|-------|
| 1 | Enhanced Steam Engine (all tiers) | Tier 0 | Direct power to nearby machines only; must step up via transformer for long-distance |
| 1 | Wind Turbine (Enhanced) | Tier 0 | Output varies by season/weather; same range limitations as steam |
| 1 | Solar Panel Array (MTier 1-3) | Tier 0 | No built-in storage; output depends on time/day cycle |
| 1 | Oil Gasifier / Producer-Gas Reactor | Tier 0 | Early diversification when oil is available |
| 1 | Diesel Burner / Liquid-Fuel Engine | Tier 0 | First reliable high-output continuous power before fission |
| 2 | Geothermal Tap / Heat Exchanger Station | Tier 1 required | Location-dependent (volcanic zones only) |
| 2 | Thermal Fission Reactor (MTier 1-4) | Tier 1 min, Tier 2 recommended | Output so large that Tier 0 grid cannot handle it at MTier 3+; step-up transformer mandatory |
| 3 | Fusion Tokamak Reactor | Tier 2 min (Tier 3 optimal) | Massive output dwarfs all previous generators |
| Endgame | Hawking Radiation Engine | Tier 3 mandatory | Requires ultra-high-voltage DC infrastructure |

### Transmission Infrastructure Catalog

| Machine | Voltage Tier(s) | Power Role | Grid Integration Notes |
|--------------------|-----------------|------------|------------------------|
| Wooden Distribution Pole + Line (Phase 1) | Tier 0 only | Short-range distribution from early generators | ~50 tile max reach; replaces vanilla pole. Cannot cross voltage tiers. Build: treated wood + basic copper wire. |
| Steel Transmission Tower + High-Voltage Line (MTier 1–3) | Tiers 1–2 | Long-distance bulk power transmission | MTier 1: basic steel tower, copper conductors (~25 kW/tile). MTier 2: reinforced with composite insulators (~100 kW/tile). MTier 3: ultra-high-tension towers supporting gold-alloy endgame conductor. |
| Step-Down Transformer / Substation (MTier 1–3) | Crosses any tier boundary | Converts high-voltage → industrial-use voltage for factory machines | MTier 1 = adjacent-tier only; MTier 2 = one-gap bridging; MTier 3 = all-tier conversion with active load balancing. |
| Underground Power Cable Trench System (Phase 3+) | Tiers 1–2 | Bury power lines to free surface space; reduce exposure loss | Uses same conductor materials (copper/aluminum/composite in concrete conduit). Recommended for dense factory zones where overhead towers would block expansion or visual clarity. |
| HVDC Converter Station (Phase 4+) | Tier 3 | AC→DC conversion for ultra-long-distance transmission with minimal losses | Required infrastructure for fusion/Hawking Engine grid integration — these generators cannot feed Tier 2 AC grids. |

### Transmission Losses and Factory Layout Rules

Transmission losses depend on line length, conductor properties, voltage tier, and load:

| Tier | Loss per 100 tiles (standard) | Loss per 100 tiles (optimized) |
|------|-------------------------------|--------------------------------|
| 0 (tin-plated copper) | ~8% | ~4% (upgrade to pure copper) |
| 0–1 (copper, no transformer) | ~7% | — |
| 1–2 (aluminum wire) | ~2.5% | ~1.5% (aluminum-steel composite) |
| 3 HVDC (gold alloy) | — | ~0.5% |

**Layout implications for factory planning:**
- Place high-output generators (fission at MTier 3+, fusion) near their primary load clusters to avoid expensive step-up/step-down sequences
- Use Tier 2–3 transmission only beyond ~200 tile distance
- HVDC Converter Station becomes mandatory when connecting remote power sources >1 km from main grid
- Transformer placement creates strategic choke points: clustering transformers at factory edges frees interior space but risks cascading failures

## Power Storage and Stabilization

The grid needs both energy storage and voltage stabilization to handle variable generation, peak demand, and fault conditions.

### Energy Storage Systems

| Machine / Entity | Phase | Role | Key Design Notes |
|-----------------|-------|------|-----------------|
| Capacitor Bank (accumulation) | Phase 1 | Buffer short-term power fluctuations; provides burst power for machine startups | Upgrade path uses battery + circuit components per tier. Same function as vanilla accumulator but with multi-tier build |
| Battery Storage Unit | Phase 2+ | Longer-duration energy storage for load leveling, backup power during outages | Requires refined copper, processed chemicals (electrolyte); higher capacity and discharge rate per tier |
| Dead-Battery Capacitor / Fuse Link | Phase 2 | Safety device that intentionally depletes to shut down a fission reactor core before meltdown | Critical safety mechanism for fission reactors — provides the last-resort power cutoff when grid fails. Not reusable; must be replaced after activation |
| Flywheel Energy Store | Phase 3+ | Mechanical kinetic energy storage with high round-trip efficiency | Alternative to batteries; requires precision manufacturing (semiconductor components at high tiers) but no chemical degradation |

### Grid Stabilization

| Machine / System | Phase | Role | Key Design Notes |
|-----------------|-------|------|-----------------|
| Reactive Power Compensator | Phase 2+ | Maintain voltage stability on AC lines; prevents brownouts when large loads start up | Required for high-capacity industrial clusters (electrochemical cells, EAF); tier = compensation capacity |
| Surge Protector / Lightning Arrester | Phase 1+ | Divert power spikes to ground before they damage grid or equipment | Prevents cascading failures from generator trip events; essential for fission reactor safety |
| Frequency Regulator | Phase 3+ | Maintain stable AC frequency when load/generation balance shifts rapidly | Required when connecting variable renewables (wind, solar) to main grid; prevents frequency drift that damages sensitive equipment |

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
- Let infrastructure and factory layout solve power problems; basic grid stability works without programmable control. Programmable tools are optional for advanced load management and plant coordination.
- Treat exact voltage tiers, loss formulas, conductor stats, and machine behavior as open design decisions until tested together.

## Reference Inspiration

GTNH demonstrates that voltage tiers and current capacity can create engineering choices; its opaque failure diagnosis is the caution. The overhaul should preserve the meaningful constraints and make grid state legible at a glance.
