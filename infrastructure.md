# Infrastructure - Exhaustive Multi-Tier Catalog

*For: Project Prometheus Factorio Overhaul Mod*  
*Status: Comprehensive infrastructure inventory (pre-ingredients mapping)*

Related documents: [Minerals and Refining](minerals-and-refining.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Power System](power-system.md), [Session Plan](session-plan.md).

> **Scope**: This is the exhaustive list of unique infrastructure types (~100-120 buildings/entities) across all phases. Each type is multi-tiered where it matters for gameplay progression. Construction ingredients are mapped later (Phase C of the session plan).
>
> **What's not here yet**: specific build recipes, capability matrices, recipe assignments, and research gates — those come from Phase C/D of the session plan.

---

## Equipment Principles

- A machine family should support multiple related processes where practical.
- Every machine type built multiple times by the player must have multi-tier progression with different build ingredients per tier (Bob's/Angels approach).
- Tier progression must change capability — not just speed. Higher tiers can handle more materials, higher pressures/temperatures, automate sub-tasks, or improve precision.
- Introduce specialized equipment when it changes the player's capability, input/output behavior, or meaningful constraints, not just to add a machine tier.
- Keep recipe eligibility, inputs, outputs, coproducts, catalysts, and required technology visible in the handbook and machine UI.
- Allow a process line to throttle when products or coproducts have no legitimate destination. Do not rely on voiding.
- Machine throughput, footprint, power, and capital complexity can differentiate routes, but should not obscure the primary tradeoffs of resource efficiency, pollution, and infrastructure.
- Exact build recipes for each tier remain provisional until Phase C; this catalog defines *what* exists, not *what it's built from*.

---

## 1. Extraction & Mining

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Electric Mining Drill | MTier 1–4 (Phases 1–3) | Mine single mineral deposits from surface | Multi-tier: larger footprint, higher ore yield multiplier per tick at each tier |
| Underground Mining Belt | MTier 2–3 (Phases 1–2) | Auto-extract from buried deposit onto belt | Replaces vanilla underground belt; needs specific tier for each deposit type |
| Deep Borehole Drill | Phase 3 | Access Tier 3 polymineral deposits in situ | Broaches mixed feed at depth; lower yield per tick but no excavation pit needed |
| Prospect Scanner | Phase 2 | Reveal depth/grade of hidden mineral veins under terrain | Diagnostic tool, not productive; reveals deposit data for player planning |
| Open-Pit Excavator | Phase 3 | High-throughput surface mining of bulk materials (coal, stone, iron) | Large footprint, massive output — endgame mining alternative to electric drills |
| Offshore Pump (Enhanced) | Phases 1–4 | Extract brine from coastal deposits; crude oil from offshore | Multi-tier: each tier increases flow rate and unlocks new deposit types |

## 2. Ore Preparation & Physical Concentration

### Size Reduction

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Jaw Crusher | MTier 1–3 (Phases 1–2) | Primary crushing of raw ore to ~10 cm chunks | First step for all hard-rock mining; tier = throughput/speed |
| Cone Crusher | Phase 2 | Secondary crushing to ~5 mm particles | MTier 2+ only; produces more uniform output than jaw crusher |
| Ball/Rod Mill | MTier 2–4 (Phases 2–3) | Grind crushed ore to powder (<100 µm) with steel/rod media | Larger mills at higher tiers; automatic media replenishment at MTier 4 |
| Roller Mill | Phase 3 | Compression grinding for harder minerals; better energy efficiency than ball mill | Alternative to ball mill with different output size profile |
| Vibrating Screen / Classifier | MTier 1–3 (Phases 1–2) | Size-separate ground material into fractions | Tier = screen area + precision; feeds multiple output belts |
| Mineral Washer | Phase 1–2 | Remove surface clays and gravels by agitation in water | Pre-floatation prep; reduces slime interference in flotation cells |

### Density & Magnetic Separation

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Spiral Concentrator | Phase 2 | Density separation of liberated grains using flowing film | No reagents needed; works on chromite, platinum, gold in mineral sands |
| Jigging Machine | Phase 2 | Pulsed-water gravity separation for coarse particles | Higher capacity than spiral concentrator but coarser cut point |
| Magnetic Drum Separator | MTier 1–3 (Phases 1–3) | Extract magnetic minerals (magnetite, chromite) from gangue | Tier = magnetic field strength; higher tiers separate weaker ferrimagnetic ores |
| Electrostatic Separator | Phase 3 | Separate conductive/non-conductive minerals by charge in high-voltage field | Used for ilmenite/rutile separation; needs advanced insulators at MTier 2+ |
| Friction/Contact Separator | Phase 3 | Fine-separation of minerals with different friction coefficients | Complements magnetic/electrostatic; used for specific mineral pairs |

### Froth Flotation

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Rougher Flotation Cell | Phase 2 | Bulk concentration of sulfide ores (chalcopyrite, sphalerite, galena) | Requires collector + frother reagents; produces rough concentrate |
| Cleaner/Scavenger Flotation Bank | MTier 1–3 (Phases 2–3) | Re-process rougher tailings or re-clean concentrates for higher grade | Bank = multiple cells in series; tier = cell count + air control precision |

## 3. Thermal Processing

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Rotary Dryer | Phase 1–2 | Remove moisture from wet concentrates or sludge | Simple thermal machine; coal/gas fired, hot gas input from burner/furnace |
| Roaster (Oxidizing) | MTier 1–3 (Phases 1–2) | Drive off volatile components (SO₂ from sulfides, CO₂ from carbonates) | Produces usable process gases (SO₂ for sulfuric acid); tier = gas capture efficiency |
| Calciner | Phase 2 | Thermal decomposition without oxidation (e.g., CaCO₃ → CaO + CO₂) | Similar to roaster but controlled atmosphere; produces calcined products and byproduct gases |
| Rotary Kiln | MTier 2–3 (Phases 2–3) | Continuous high-temperature thermal treatment of bulk materials | Versatile: can roast, calcine, or sinter; higher tiers have better temp control |
| Sintering Machine / Sinter Strand | Phase 2 | Agglomerate fine ore fines into porous pellets for furnace feed | Essential for using fine-grained ores that can't go directly in blast furnace; produces sintered lumps |
| Pellet Press / Briquette Machine | Phases 1–3 | Compress powders/fines into shaped fuel briquettes or ore pellets with binder | Multi-purpose: iron oxide pellets, coal briquettes for gasifier, powdered catalyst presses |
| Spray Dryer | Phase 2 | Atomize liquid feed into hot gas stream to produce dry powder | Used for precipitate dewatering, slurry-to-powder in solution processing |

## 4. Smelting & Reduction (Metallic Extraction)

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Enhanced Blast Furnace | MTier 1–3 (Phases 1–2) | Carbon-reduced iron smelting from ore + coke/lignite → pig iron | Larger hearth, better heat recovery, automated tap at higher tiers. Replaces vanilla blast furnace |
| Direct Reduction Furnace | Phase 2 | Produce DRI (direct reduced iron) from ore using reducing gas (H₂/CO mix) | Gas feed from gasifier or electrolysis; alternative to blast furnace path |
| Converter (BOF/LD) | MTier 1–3 (Phases 2–3) | Convert pig iron to steel by blowing oxygen to burn off excess carbon | Requires pig iron input + oxygen; tier = blow rate/temperature control |
| Electric-Arc Furnace (EAF) | MTier 1–4 (Phases 2–4) | Melt scrap metal or DRI with graphite electrodes for alloy production | Higher voltage → more power → faster melting, better temp range at high tiers |
| Reverberatory Furnace | Phase 2–3 | Pyrometallurgical smelting of copper/nickel sulfide concentrates | Flame heats charge from above; produces matte (Cu₂S/FeS) for converting |
| Cupola Furnace | Phase 1 | Melt pig iron + scrap to produce cast iron; simple coke-fired design | Early-phase option for cast iron; lower control precision than EAF but no electricity needed |
| Vacuum Induction Melting Furnace | Phase 3+ | Melt high-purity alloys under vacuum; removes gas impurities | Endgame metallurgy; produces premium alloys requiring MTier 4-5 components to build |

## 5. Chemical Extraction & Reactors

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Tank Leach Cell / Agitated Vessel | Phase 2 | Dissolve metal from ore/concentrate using acid/alkali/solution | First-stage hydrometallurgy; requires acid feed (H₂SO₄ or NaOH); produces pregnant leach solution |
| Heap Leach Pad + Sprayer System | Phase 2 | Percolate dilute acid through stacked ore for low-grade material recovery | Low throughput but processes large volumes of low-grade material; no power needed, just reagent |
| Pressure Leach Autoclave | MTier 1–3 (Phases 2–3) | Dissolve refractory ores at elevated temperature/pressure in sealed vessel | Tier = pressure rating; higher tiers handle hotter/harder-to-dissolve feeds |
| General-Purpose Chemical Reactor | MTier 1–3 (Phases 1–3) | Configurable batch reactor for acid/base reactions, oxidations, reductions | Versatile: Ostwald nitric acid chain, ammonia oxidation, Fischer-Tropsch. Tier = material compatibility range + temp/pressure control |
| Catalytic Converter / Fixed-Bed Reactor | Phase 2+ | Gas-phase reactions over solid catalyst (SO₂→SO₃, NH₃ oxidation) | Requires specific catalyst material input; produces heat as byproduct |
| Fluidized-Bed Reactor | MTier 2–3 (Phases 2–3) | Gas flows through suspended solid particles for high-contact reactions | Used for coal gasification, kyanite processing, some intermediate syntheses; good thermal management |

## 6. Solution Processing & Separation

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Vacuum Filter / Filter Press | Phase 2 | Separate solid precipitate from liquid under vacuum pressure | After precipitation steps; tier = filter area + vacuum level |
| Crystallizer / Evaporator | MTier 1–3 (Phases 2–3) | Concentrate solution by evaporation to produce crystals of purified salt | Cooling crystallizer → forced-circulation evaporator → vacuum crystallizer with auto-discharge at high tiers |
| Solvent Extraction Column | Phase 3 | Separate dissolved metals using immiscible organic solvents (e.g., Cu extraction from sulfate) | Requires specific extractant reagent; produces raffinate + loaded organic streams |
| Ion Exchange Unit | Phase 3 | Pass solution through resin beds to selectively bind target ions | For uranium, REE, trace metal recovery; resin regeneration requires acid feed |
| Precipitation Tank / Thickener | MTier 1–2 (Phases 2–3) | Controlled addition of precipitating agent to selectively remove a dissolved ion | Separates specific metals from mixed solution; tier = agitator control precision + sludge removal |
| Centrifuge / Decanter | Phase 3 | High-speed spinning to separate fine solids from liquids rapidly | Alternative to filter press for finer particles or continuous operation |

## 7. Electrochemical Processing

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Electrowinning Cell / Tankhouse | MTier 1–3 (Phases 2–4) | Deposit dissolved metal onto cathode using sustained DC current | Requires electrolyte feed + power. Tier = electrode surface area, voltage control, auto-cathode swapping at high tiers |
| Electrorefiner | Phase 3+ | Purify impure metal anode by controlled deposition on pure cathode | Copper, nickel, zinc purification from impure smelted product; requires high-quality power |
| Chlor-Alkali Membrane Cell | MTier 2–4 (Phases 2–3) | Split brine (NaCl solution) into Cl₂ gas + NaOH + H₂ via ion-exchange membrane | Requires specific membrane material at MTier 2+; tier = membrane quality + electrode area |
| AEM Water Electrolyzer | Phase 3 | Split water into pure H₂ and O₂ gases using anion-exchange membrane | Higher purity output than standard electrolyzer; produces fusion-grade hydrogen |

## 8. Polymer & Composite Processing

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Petrochemical Cracking Furnace | MTier 1–3 (Phases 2–3) | Thermally crack long-chain hydrocarbons into shorter monomers (ethylene, propylene) | Requires crude oil or FT synthetic feed; produces mixed hydrocarbon output requiring separation |
| Polymerization Reactor / Vessel | MTier 1–3 (Phases 2–3) | Polymerize monomers into plastics/resins with catalyst injection | Batch stirred-tank → continuous loop reactor → auto-controlled production at high tiers |
| Extruder / Pelletizer | Phase 2–3 | Melt and shape polymer output into pellets or continuous profiles | Finishing for plastics; tier = barrel length, heater zones, die precision |
| Injection Molding Press | Phase 3 | Form polymers into complex shapes under pressure in heated mold | Produces casings, connectors, components directly from polymer melt |
| Fiber Winder / Spinning Line | Phase 3+ | Draw polymer or glass fibers for composite reinforcement | Produces fiberglass or synthetic fiber feedstock for composite materials |
| Rubber Mixing Mill / Kneader | Phase 2 | Process natural/synthetic rubber with curatives and fillers | For gaskets, seals, belt materials; tier = roller gap precision + temp control |

## 9. Semiconductor Fabrication Chain

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Purification Column (polysilicon grade) | Phase 3 | Trichlorosilane distillation for electronic-grade silicon purification | Requires high-purity silica/ceramic internals; produces e-grade polysilicon feed |
| Czochralski Crystal Grower | Phase 3 | Pull single-crystal silicon ingot from molten polysilicon with seed crystal | Tier = crucible size, rotation control precision, inert atmosphere quality |
| Floating Zone Furnace | Phase 3+ | Purify silicon further without crucible contact via RF-heated zone melting | Higher purity than Czochralski; produces ultra-poly-silicon for specialized semiconductor applications |
| Wafer Saw / Multi-Wire Diamond Cutter | Phase 3 | Slice single-crystal ingot into thin wafers (~200 µm) | Diamond wire cutting; tier = blade precision, slice thickness control |
| Chemical-Mechanical Polisher (CMP) | Phase 3 | Polish wafer surface to nanometer roughness with slurry + pad | Prepares ultra-flat surface before lithography; requires specific abrasive slurries |
| Wet Etch Bath / Station | MTier 1–3 (Phases 3–4) | Remove material from wafer using controlled chemical etchants | Tier = etchant compatibility range, temp control precision, automated immersion timing |
| Thermal Oxidation / Diffusion Furnace | MTier 2–4 (Phases 3–4) | Grow SiO₂ layer or diffuse dopants into wafers at high temperature in gas atmosphere | Batch tube furnace → continuous strip furnace with multi-zone temp control → rapid thermal processor at high tiers |
| CVD / PVD Deposition Chamber | MTier 2–4 (Phases 3–4) | Deposit thin films of dielectric, metal, or conductive material onto wafers | Chemical vapor deposition or physical vapor deposition. Tier = film thickness precision, uniformity control, chamber volume |
| Photolithography Stepper / Aligner | Phase 4+ | Expose photoresist patterned through reticle/photomask onto wafer surface | Most complex single machine; requires precision optics + alignment sensors |
| Cleanroom Enclosure Module | Phase 3 | Provide particle-controlled environment for wafer fabrication steps | Infrastructure rather than productive machine; enables other cleanroom-dependent machines to operate |
| Semiconductor Packaging Line | Phase 4 | Die attach → wire bond → mold in package → final test | Three sub-steps on one line: die-attach station, wire-bonding machine, molding press. Produces packaged ICs |

## 10. Nuclear Fuel & Component Fabrication

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Uranium Conversion Line | Phase 2–3 | Convert yellowcake → UO₂ powder via aqueous chemistry, then press into pellets | Multi-stage: leach/purification tank → precipitation → pellet pressing station → sintering furnace |
| Fuel Pellet Sintering Furnace | Phase 3 | Fire pressed UO₂ pellets at high temperature for densification and strength | Requires refractory construction; produces green pellets → sintered fuel pellets |
| Cladding Tube Mill | Phase 3 | Form Zr-alloy tube from ingot via extrusion/piercing + pilger rolling | Produces hollow zirconium cladding for fuel rods; tier = pressure vessel quality, precision forming capability |
| Fuel Rod Assembly Line | MTier 1–3 (Phases 3–4) | Load sintered pellets into Zr-clad tubes, end-cap weld, helium leak-test each rod | Manual load/station → semi-auto pellet loader → fully automated assembly with inline inspection at high tiers |
| Zr/Hf Separation Plant | Phase 2–3 | Separate hafnium from zirconium via fractional distillation of chlorides + hydrometallurgical purification | Critical nuclear gate: Hf absorbs neutrons, must be removed for fuel-grade Zr |
| Hafnium Absorber Plate Liner | Phase 3 | Roll/form Hf metal into control-rod absorber plates (often with B₄C) | Co-product of Zr-Hf separation; produces neutron-absorbing components for fission reactors |
| Boron Carbide Press + Sintering Furnace | Phase 2–3 | Compact B₄C powder with binder, press, and sinter control rod absorbers | Powder metallurgy: mixing mill → isostatic press → sintering furnace |
| Lithium Breeder Blanket Panel Assembler | Phase 4+ | Assemble Li-containing breeder material into heat-exchange panel modules for tokamak | Endgame nuclear: produces first wall/blanket components for fusion reactor construction |
| Tungsten Plasma-Facing Armor Tile Molder | Phase 4+ | Form sintered W-tungsten tiles for tokamak inner-wall plasma-facing surfaces | Requires high-temperature pressing; produces armor-grade tungsten plates/tiles |
| Superconducting Coil Winding Machine | MTier 2–4 (Phases 3–4) | Wind NbTi/Nb₃Sn superconducting wire into precision magnet coils with insulation layers | Manual winder → automated tension-controlled winder → cryogenic-grade insulator applicator at high tiers |
| Precision Optics Fabrication Station | Phase 4+ | Manufacture optical concentrator elements for Hawking Radiation Engine (lenses, mirrors, interferometers) | Requires cleanroom + diamond-turning lathes; produces optics-grade components with nanometer surface accuracy |
| Extreme-Pressure Containment Vessel Assembler | Phase 4+ | Weld/assemble multi-layer pressure vessel shells for Hawking Engine containment | Shell forming → autoclave curing of composite layers → in-situ welding inspection at high tiers |
| Thermoelectric Conversion Array Module | Phase 4+ | Assemble thermocouple pairs (p-type/n-type semiconductor junctions) into power-conversion panels | Converts waste heat to electricity; produces Stirling-engine or Seebeck-effect heat-to-power modules for Hawking Engine |

## 11. Power Generation

> Full power system details are in [Power System](power-system.md). This catalog lists the unique generator types.

### Phase 1 (Early Game — Multiple Choice)
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Enhanced Steam Engine | MTier 1–3 (Phases 1–2) | Burn any solid fuel in water-cooled boiler for continuous power | Larger boiler, better heat recovery, automated ash removal at higher tiers. Replaces vanilla steam engine with multi-fuel support |
| Wind Turbine (Enhanced) | Phase 1 | Harness wind energy; output varies by season/weather | Vanilla turbine enhanced: tiered efficiency ratings, needs pole infrastructure |
| Solar Panel Array | MTier 1–3 (Phases 1–2) | Convert sunlight to electricity during daytime hours | Basic PV cells → high-efficiency multi-junction panels at higher tiers. Output varies by time/weather; no storage built in |
| Oil Gasifier / Producer-Gas Reactor | Phase 1–2 | Gasify coal or heavy oil residue into producer gas (CO + H₂) for engine fuel | Early diversification option when oil is available; bridges gap between solid-fuel and liquid-fuel power |
| Diesel Burner / Liquid-Fuel Engine | Phase 2 | Burn refined liquid fuel in combustion chamber for steady power output | First reliable high-output continuous power before fission; requires oil refining to produce liquid fuel |

### Phase 2–3 (Mid Game — Diversification)
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Biomass Digester / Biogas Reactor | Phase 2 | Anaerobic breakdown of organic matter → methane biogas for power generation | Alternative renewable; batch digester → continuous stirred-tank → pressurized reactor at higher tiers |
| Geothermal Tap / Heat Exchanger Station | Phases 2–3 | Extract heat from volcanic zones or deep geothermal reservoirs near hotspots | Location-dependent: only placeable near specific terrain features. Tier = depth of tap, heat extraction rate |
| Thermal Fission Reactor | MTier 1–4 (Phases 3–4) | Controlled nuclear fission using enriched uranium fuel pellets + continuous cooling | Core Phase 3 power. Graphite-moderated → Zr-clad + Hf control rods → advanced coolants at high tiers |
| Hydroelectric Dam Generator | Phase 3 | Use flowing water gradient to drive turbines | Location-dependent (near rivers/large bodies of water). Tier = dam height/capacity, turbine efficiency |
| Concentrated Solar Power Tower + Thermal Storage | Phase 3 | Mirrors focus sunlight onto receiver tower; heat stored in molten salt for night/power | Alternative to PV: solar→thermal→steam cycle with built-in thermal storage buffer |

### Phase 4 (Late Game — High-Tier Options)
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Fusion Tokamak Reactor | Phase 4 | Magnetic confinement of D-T plasma → massive energy release via fusion | Requires W armor, Nb₃Sn magnets, Li breeder blanket. Output dwarfs fission but construction is endgame-costly |
| Advanced Wind Array / Offshore Wind Farm | Phase 4 | High-capacity turbines for consistent large-scale power generation | Tier = turbine capacity per unit, array management sophistication |
| Tidal/Wave Generator | Phase 4 | Harness ocean/tidal energy in coastal locations | Location-dependent (coastal biome only). Tier = blade/float size, conversion efficiency. Steady but location-locked |

### Endgame
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Hawking Radiation Engine | Endgame | Simulated Hawking radiation from confined event horizon → near-infinite energy output | Ultimate power source. Requires all Phase 4 infrastructure to build; connected to Core simulation network for radiation tuning |

### Power Transmission & Grid Infrastructure — DEFERRED TO EXTENSION MOD

> **All items below are deferred** to the `power-transmission-override` extension mod. They remain here as design reference only.
> **No transmission towers, transformers, conductors, HVDC stations, or grid-stabilization devices are in scope for the core mod.**

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Steel Transmission Tower + High-Voltage Line | MTier 1–3 (Phases 2–4) | Long-distance bulk power transmission at high voltage | Basic steel tower → reinforced with composite insulators → ultra-high-tension at highest tiers. Conductors: tin-plated copper → pure copper → aluminum/steel composites → gold (endgame, minimal loss) |
| Step-Down Transformer / Substation | MTier 1–3 (Phases 2–3) | Convert high-voltage transmission to industrial-use voltage for factory machines | Iron-core → copper-wound with tap changers → digital monitoring + load balancer at highest tiers |
| Underground Power Cable Trench System | Phase 3+ | Bury power lines to free surface space; reduce exposure loss | Uses same conductor materials (copper/aluminum/composite in concrete conduit). No line-of-sight requirement for routing |
| HVDC Converter Station | Phase 4+ | Convert AC power to high-voltage DC for ultra-long-distance transmission with minimal losses | Required for fusion/Hawking Engine grid integration — these generators cannot feed Tier 2 AC grids |

### Energy Storage Systems (Core Mod)

> These items **are in scope** for the core mod because they are accumulator-style devices that connect to vanilla pole grids. They do not require any custom transmission infrastructure.

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Capacitor Bank (accumulation) | Phase 1 | Buffer short-term power fluctuations; provides burst power for machine startups | Upgrade path uses battery + circuit components per tier. Same function as vanilla accumulator but with multi-tier build. Tier = storage capacity + discharge rate |
| Battery Storage Unit | Phase 2+ | Longer-duration energy storage for load leveling, backup power during outages | Requires refined copper, processed chemicals (electrolyte); higher capacity and discharge rate per tier. MTier 3 adds smart-cell management via semiconductor monitoring |
| Dead-Battery Capacitor / Fuse Link | Phase 2 | Safety device that intentionally depletes to shut down a fission reactor core before meltdown | **Not reusable** — must be replaced after activation. Critical safety mechanism for fission reactors: provides the last-resort power cutoff when grid fails and active cooling is at risk. No upgrade path; single-tier safety item |
| Flywheel Energy Store | Phase 3+ | Mechanical kinetic energy storage with high round-trip efficiency | Alternative to batteries — no chemical degradation over time. Requires precision manufacturing (semiconductor components at MTier 2+, servo motors from Automation §5). Tier = rotational mass + bearing quality |

### Grid Stabilization Infrastructure — DEFERRED TO EXTENSION MOD

> All items below are **deferred** to the `power-transmission-override` extension mod.

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Reactive Power Compensator | Phase 2+ | Maintain voltage stability on AC lines; prevents brownouts when large loads start up | Required for high-capacity industrial clusters (electrochemical cells, EAF) |
| Surge Protector / Lightning Arrester | Phase 1+ | Divert power spikes to ground before they damage grid or equipment | Essential for fission reactor safety at every step-up/down transformer in the reactor's feed path |
| Frequency Regulator | Phase 3+ | Maintain stable AC frequency when load/generation balance shifts rapidly | Required when connecting variable renewables (wind, solar) to main grid |

### Power Generation + Transmission Infrastructure Summary — CORE MOD ONLY

> The items below are **in scope for the core mod**. All transmission and stabilization infrastructure is deferred.

| Infrastructure Type | Total Items | Tiered? | Key Capability Tiers |
|---------------------|-------------|---------|----------------------|
| Generators (Phases 1-4 + Endgame) | ~14 types | Yes (varies by type) | Steam engine MTier 1-3; fission reactor MTier 1-4; fusion Tokamak Phase 4 |
| Energy Storage Systems | 4 types (capacitor, battery, dead-battery fuse, flywheel) | 3/4 tiered | Capacitor bank MTier; battery storage MTier; flywheel MTier 2+ |
> **Deferred to extension mod:** Transmission towers + lines (3 variants), transformers / substations (1 type, MTier 1-3), grid stabilization devices (3 types), HVDC Converter Station (Phase 4+) |

## 12. Military Infrastructure

### Weapons & Turrets
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Kinetic Turret (Steel/Copper) | MTier 1–3 (Phases 1–3) | Automated lead-core bullet firing with copper-jacketed projectiles; basic targeting electronics | Larger caliber, faster rate of fire, better ammo capacity at higher tiers. Requires kinetic ammo production line |
| Ammunition Press / Loading Machine | Phase 1–2 | Combine lead core + copper jacket + steel case + propellant into finished bullets | Intermediate processing for kinetic ammo; tier = throughput speed and precision alignment |
| Incendiary Turret | MTier 1–3 (Phases 2–3) | Fire fuel/oxidizer incendiary rounds with ignition compound trigger | Larger payload, wider splash radius, better target tracking at higher tiers. Requires incendiary compound production |
| Explosive Mortar (HE) | MTier 1–3 (Phases 3–4) | Fire high-explosive shells with advanced detonator mechanism; indirect fire arc | Larger shell diameter, faster loading, GPS-assisted targeting at highest tiers. Requires nitric-acid-derived HE + precision detonator production |
| AP Cannon (Tungsten-Core Penetrator) | Phase 4+ | Fire tungsten-core rounds through specialized high-pressure barrel mechanism | Maximum damage against armored targets; requires full Phase 2 tungsten refining chain for AP ammo production |
| Laser/Beam Emitter Turret | Phase 4+ | Focus directed energy onto target using precision optics + power grid feed | Endgame defense: minimal ammo consumption (just power), needs dedicated power routing and cooling infrastructure |
| Plasma Discharge Emitter | Phase 4+ | Release concentrated plasma burst from magnetic containment field | Requires superconducting magnetic coils; damage scales with stored magnetic energy |
| Railgun / Coilgun Turret | Endgame | Accelerate ferromagnetic projectile using extreme electromagnetic force | Ultimate kinetic weapon; requires massive power draw, superconducting magnets, precision capacitor bank |

### Military Component Production (Support Machines)
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Incendiary Compound Mixer / Reactor | Phase 2–3 | Mix fuel/oxidizer compounds with ignition catalyst for incendiary rounds | Reuses general chemical reactor or dedicated small-scale mixer; requires specific reagents (from Phase 1-2 chemistry) |
| HE Explosive Formulation Tank + Nitration Station | Phase 3 | Synthesize nitric-acid-derived explosives via controlled nitration reactions under pressure/temperature control | Requires pressure-rated vessel + safety controls; tier = pressure rating, temperature control precision, safety interlocks |
| Precision Detonator Assembly Machine | Phase 3 | Assemble reliable detonation initiation components from explosive, primer, and electrical parts | Combines chemistry (explosive compounds) + electronics (trigger circuits); produces reliable firing mechanisms |
| Tungsten Core Forging Press | Phase 4+ | Forge tungsten-carbide penetrator cores under extreme pressure for AP rounds | Requires refractory tooling + hydraulic press at high MTier; intermediate product between raw tungsten and finished AP ammo |

## 13. Logistics & Material Handling

### Conveyor & Belt Systems (Multi-Tier)
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Basic Transport Belt | MTier 1–4 (Phases 1–4) | Move items along a fixed path at steady speed | Each tier increases speed and weight capacity. Material upgrades: basic rubber → reinforced polymer → alloy-reinforced at highest tiers |
| High-Speed Conveyor Belt Network | Phase 3–4 | Advanced belt segments with semiconductor-grade motor control for maximum throughput | Endgame logistics; requires advanced circuits/semiconductors; significantly faster than standard belts, supports heavier loads |
| Adjustable-Speed Belt Splitter / Merger | Phase 2+ | Split a single input belt into two outputs (or merge two inputs), with speed matching | Logic component for belt routing; tier = number of inputs/outputs, speed adjustment precision |
| Understacker / Topstacker Belt Jumper | Phase 1–2 | Cross one belt over or under another without item transfer | Layout tool; basic version from early game, upgraded versions at higher tiers with better speed handling |

### Infrastructure Buildings
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Electrified Freight Terminal (Rail Station) | MTier 1–3 (Phases 2–3) | Advanced rail station with electrified coupling, circuit-controlled demand dispatch, integrated buffer system | Basic switch yard → automated load/unload → AI-demand-dispatch at highest tiers. Requires advanced circuits + power regulation |
| Logistics Bot Hub | MTier 1–3 (Phases 2–3) | Central hub for assigning and managing logistics bots; provides battery/circuit upgrade points per tier | Larger storage capacity, faster bot dispatch, range extension per tier. Tier upgrades use batteries + circuits |
| Construction Bot Bay | MTier 1–4 (Phases 2–4) | Housing for construction bots; progressive tier upgrades expand build radius and item-carrying capacity | Each tier upgrade requires specific battery/circuit/semiconductor components. Higher tiers = faster building, heavier materials handled |
| High-Capacity Storage Silo / Tank | Phase 1+ | Bulk storage for solid or liquid materials; tier = capacity | Used for buffering intermediate products between processing stages |
| Belt Sorter / Insert/Remove Station | Phase 1–2 | Insert items into moving belts at precise points, remove specific items from belts | Logic component for automated factory routing; tier = insertion/removal speed, number of simultaneous operations |
| Material Handling Crane (Overhead) | Phase 3 | Lift and move heavy materials between buildings that cannot connect via belts | Industrial logistics: handles multi-block machines or large components; tier = lifting capacity, positioning precision |

### Advanced Automation & Robotics
| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Automated Guided Vehicle (AGV) Station | Phase 4+ | Autonomous vehicle that transports bulk materials between stations on programmed routes | Endgame logistics: replaces belt networks for long-distance, non-linear material transport. Requires semiconductor controls |
| Robotic Arm Assembly Cell | Phase 4+ | Programmable multi-axis arm for complex assembly operations not feasible with belts + inserters | Flexible manufacturing; can perform multiple tasks depending on programming/tier. Tier = degrees of freedom, payload capacity, control precision |

## 14. Fluid Handling & Transport

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Basic Storage Tank / Drum | Phase 1+ | Store bulk liquids or gases; tier = capacity and pressure rating | Buffering for chemical feeds, fuel storage, process fluid holding |
| Pressurized Pipe Network | MTier 1–3 (Phases 1–3) | Move fluids between machines under pressure; each tier handles different pressures/temperatures | Basic plastic → reinforced steel → corrosion-resistant alloy. Higher tiers = higher flow rate, more temperature/pressure tolerance |
| Motorized Fluid Pump Station | MTier 1–3 (Phases 2–3) | Actively move fluids against gravity or resistance; tier = pumping pressure, flow capacity | Required when gravity feed is insufficient or for long-distance fluid transport |
| Automated Flow Control Valve | Phase 2+ | Regulate and throttle fluid flow between connected pipes/machines | Precision control for process chemistry; tier = valve responsiveness, multi-port routing capability |
| Heat Exchanger Unit | MTier 1–3 (Phases 2–4) | Transfer heat between two fluid streams without mixing them | Used in cooling loops, preheating feed fluids, condenser applications. Tier = surface area, temperature differential range, material compatibility |
| Centrifugal Compressor / Vacuum Pump | Phase 3 | Compress gases to high pressure or create vacuum for process stages | Required for gas-phase reactions, distillation columns, and semiconductor processes; tier = pressure ratio, flow rate |

## 15. Polymer Processing & Composite Manufacturing

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Rubber/Kneading Mill | Phase 2 | Process natural/synthetic rubber with curatives and fillers for gaskets, seals, belt materials | Produces composite rubber feedstock for industrial applications; tier = roller precision, temp control |
| Sheet Extrusion / Rolling Press | Phase 2–3 | Form polymer melt into sheets or plates for structural/composite use | Alternative to extruder/pelletizer when flat-sheet output is needed for molding or laminate layup |
| Fiber Layup Station | Phase 3+ | Layer composite materials (fiberglass, carbon fiber) with resin matrix for structural panels | Produces lightweight high-strength materials needed for endgame construction components; requires fiber winding + resin mixing stations |

## 16. Waste Processing & Loopback (Circular Economy)

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Tailings Re-Processing Unit | Phase 2–3 | Extract residual valuable minerals from flotation/smelting tailings | Circular economy: recovers trace metals from waste streams; tier = detection sensitivity, separation precision. Reduces raw material needs over time |
| Waste-to-Fuel Converter / Incinerator | Phase 2+ | Burn non-recoverable waste/organic matter for energy or fuel gas production | Converts scrap/unwanted outputs into useful power or gas feedstock; tier = combustion efficiency, emissions control |
| Metal Recovery / Solvent Extraction Circuit | Phase 3 | Recover dissolved noble/catalyst metals (Au, Ag, Pt, Pd) from chemical processing waste streams | Recovers trace precious metals from process effluent; requires specific solvent reagents. Tier = extraction efficiency, selectivity |
| Sludge Dewatering & Stabilization Unit | Phase 2–3 | Process sludge/paste byproduct from solution processing into dry cake for disposal or further processing | Handles coproducts with no direct use; tier = dewatering pressure, drying temperature |

## 17. Research & Measurement Infrastructure (Phase 2+)

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Superconductivity Research Lab | Phase 2 | Produce superconductive states/critical current domain packs | Requires electronic-grade polysilicon + Nb₃Sn wire as bridge materials; produces research data for simulation network |
| Plasma Confinement Facility | Phase 2 | Measure ionized gas behavior and field dynamics; produce plasma domain packs | Requires Nb₃Sn wire + cryogenic infrastructure; produces high-field magnet test data |
| Nanofabrication Laboratory | Phase 2 | Atomic-scale materials research at cleanroom grade; produce nanofab domain packs | Requires HfO₂ dielectric cleanroom-grade material; produces nanostructure characterization data |
| Isotope Separation & Calibration Lab | Phase 2 | Nuclear interaction modeling via mass spectrometry and magnetic separation; produce isotope domain packs | Requires D₂O + enriched fuel stock; produces isotopic abundance analysis data |
| Reaction Dynamics Facility | Phase 2 | Reaction kinetics/equilibrium mapping with high-pressure reaction chamber; produce reaction dynamics domain packs | Requires rhenium-catalyst powder (from molybdenite); produces catalytic reaction pathway data |
| Quantum States Laboratory | Phase 2 | Atomic bonding/crystalline structure research at mK temperatures; produce quantum states domain packs | Requires high-purity cryogenic Ar/N₂ mixture; produces quantum state measurement data |
| Planetary Simulation Core (Hub) | Phase 3 | Coordinates distributed model runs across facilities; accepts domain datasets for planetary-scale simulation | Modular hub with 4 physical assemblies: Thermal Frame, Computation Cluster, Integration Bus, Calibration Reference Frame |
| Compute Campus Node | Phase 3 | Adds computational capacity to the Core network; processes intermediate simulation data | Satellite of the Core; tiered upgrades expand processing bandwidth |
| Memory/Archive Module | Phase 3 | Stores survey data, process data, model states, and simulation results for the Core network | Data storage satellite; tiered upgrades expand archival capacity |
| Regional Observation Facility | Phase 3 | Analyzes samples/operating data from remote locations; submits domain datasets to Core network | Remote data collection node; produces raw sensor feeds → processed datasets |

## 18. Automation & Control Systems

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Basic Sensor Array (temp/pressure/gas) | Phase 1–2 | Monitor machine status: temperature, pressure, gas composition around connected equipment | Diagnostic overlay; tier = number of monitored parameters, accuracy, alarm thresholds |
| PLC Controller Unit | MTier 1–3 (Phases 2–4) | Programmed logic controller for automated process control of connected machines and flows | Simple timer-based logic → PID control → neural-network-assisted optimization at high tiers. Tier upgrades expand I/O channels, memory, processing speed |
| Precision Actuator / Servo Motor | Phase 2–3 | Provide precise mechanical control for valves, gates, positioning stages in advanced processes | Enables automated process adjustment; tier = torque/force precision, response time, durability |
| Wired Industrial Control Network | MTier 1–3 (Phases 2–4) | Connect sensors, PLCs, and actuators into a coordinated control system for factory-wide automation | Simple relay logic → digital I/O network → real-time distributed control at highest tiers. Uses semiconductor components at high tiers |
| AI-Assisted Optimization Module | Phase 4+ | Analyze factory data patterns and auto-tune machine settings for optimal throughput/resource efficiency | Endgame automation: uses Core simulation findings to optimize production; tier = processing power, pattern recognition scope |

## Consolidated Multi-Tier Machine Summary

This table maps every machine category to its total tier count and which tiers matter most for gameplay. Machines are multi-tier where tier changes capability (not just cosmetic).

| Category | Total Unique Types | Tiered? | Key Tiers That Change Capability |
|----------|------------------|---------|---------------------------------|
| Extraction & Mining | 6 | Yes (drill, underground belt, deep bore) | Electric drill MT1–4; prospect scanner gates access to deeper deposits |
| Ore Preparation & Concentration | 10 | Partial (ball mill, magnetic drum, flotation bank) | Ball mill MT2–4 for throughput/media auto-replenishment; magnetic drum tier = field strength |
| Thermal Processing | 7 | Yes (roaster, kiln, sintering, pellet press) | Roaster tier = gas capture efficiency; kiln/sinter tier = temp control precision |
| Smelting & Reduction | 7 | Yes (EAF multi-tier primary) | EAF MT1–4: voltage, electrode auto-feed, power range |
| Chemical Extraction & Reactors | 6 | Partial (pressure leach, general reactor) | Pressure leach tier = pressure rating; reactor tier = material compatibility range + control precision |
| Solution Processing & Separation | 6 | Partial (crystallizer, filter press) | Crystallizer MT1–3: cooling → evaporator → vacuum auto-discharge |
| Electrochemical Processing | 4 | Yes (electrowinning, chlor-alkali) | Electrowinning MT1–3 = electrode area + auto-cathode swapping; membrane cell MT2+ = membrane quality |
| Polymer & Composite Processing | 6 | Partial (polymerization reactor) | Polymerization: batch → continuous → auto-controlled at high tiers |
| Semiconductor Fabrication | 12 | Yes (crystal grower, CVD/PVD, lithography) | Each step is multi-tier; cleanroom quality and precision scale across all |
| Nuclear Fuel & Component Fabrication | 13 | Partial (coil winder, fuel rod assembly) | Multi-stage lines: each sub-step has tier progression from manual → semi-auto → fully automated |
| Power Generation + Transmission | 20 (14 gen + 6 transmission) | Yes (steam engine primary multi-tier) | Steam engine tiers most impactful for early game; reactors scale linearly with tier power output |
| Military Infrastructure | 8 weapons + 5 support | Partial (turrets scale damage/capacity) | Turret tiers = caliber/range/damage; support machines scale throughput and precision |
| Logistics & Material Handling | 10 types + infrastructure | Yes (belts, freight terminal, storage) | Belt speed/weight capacity per tier; freight terminal tiers = automation level |
| Fluid Handling & Transport | 6 types | Partial (pipes, heat exchanger multi-tier) | Pipe network tiers most important for pressure/temperature tolerance across distances |
| Waste Processing & Loopback | 4 types | Partial (tailings unit) | Each scales recovery efficiency with tier |
| Research & Measurement Infrastructure | 10 facilities | Partial (Core satellites scale capacity) | Core L2/L3 are upgrades, not tiers per se; satellites tier by processing/storage capacity |
| Automation & Control Systems | 5 types | Yes (PLC multi-tier primary) | PLC MT1–3: timer → PID → neural-assisted optimization |

## Design Gate

A machine or variant should be approved only when its operation, input/output contract, progression role, and downstream product use are clear. A new machine family should correspond to a real process capability or a strong gameplay distinction, not simply a desire to give every reaction its own building. Tier progression for any machine type must pass this gate at each level — not all tiers need to be unique builds; some can be simple throughput upgrades if the capability change is meaningful.
