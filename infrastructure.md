# Infrastructure - Candidate Infrastructure and Placeable-Entity Catalog

*For: Project Prometheus Factorio Overhaul Mod*  
*Status: Candidate inventory; scope, counts, and construction-demand hypotheses await Phase 3 alignment*

Related documents: [Minerals and Refining](minerals-and-refining.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Power System](power-system.md), [Design Coverage and Product-Tree Plan](plan.md), [Documentation Map](documentation-map.md). Related proposals: [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) and [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md).

> **Scope**: Candidate catalog of placeable production, power, logistics, fluid, defense, research, waste, and control infrastructure across the planned progression. The current rough estimate of ~100-120 entries is not a normalized count of placeable entities, machine families, support systems, or tier variants; Phase 3 will reconcile it.
>
> **Construction demand**: Material and build notes are hypotheses for Phase 3 alignment. Exact build recipes and quantities follow product and recipe work in Phases 5-6; research gates follow Phase 7.
>
> **Boundary**: Non-building products (vehicles, fuels, weapons/ammo, armor/equipment, modules, and research ingredients) belong in [Intermediate Products](intermediate-products.md). The ammo table in section 12 is a cross-domain candidate reference only and is excluded from infrastructure counts.
>
> **Document ownership**: The former Machine Systems design was subsumed into this catalog. Candidate placeable machine families and progression are cataloged here; exact route-to-machine assignments remain deferred until process routes and product coverage are ready. The current work roadmap is [plan.md](plan.md); no separate `session-plan.md` source is present.

---

## Equipment Principles

- A machine family should support multiple related processes where practical.
- A prior proposal called for multiple build-material tiers on every frequently built machine type; this catalog also lists single-tier exceptions. Whether to tier a family remains capability-driven and unresolved.
- Tier progression must change capability — not just speed. Higher tiers can handle more materials, higher pressures/temperatures, automate sub-tasks, or improve precision.
- Introduce specialized equipment when it changes the player's capability, input/output behavior, or meaningful constraints, not just to add a machine tier.
- Keep recipe eligibility, inputs, outputs, coproducts, catalysts, and required technology visible in the handbook and machine UI.
- Allow a process line to throttle when products or coproducts have no legitimate destination. Do not rely on voiding.
- Machine throughput, footprint, power, and capital complexity can differentiate routes, but should not obscure the primary tradeoffs of resource efficiency, pollution, and infrastructure.
- Exact build recipes and quantities for each tier remain provisional; this catalog defines candidate placeables and construction-demand hypotheses, not final build costs.

---

## Factorio-Style Infrastructure-Family Coverage Checklist

This is a completeness checklist, not a commitment to add every vanilla or modded entity. Examples describe gameplay families, not a version-specific prototype inventory. During Phase 3, assign each family a project scope disposition: core, vanilla retained/modified/replaced, extension, or out of scope.

| Family to verify | Factorio-style examples | Current catalog coverage or handoff |
|---|---|---|
| Resource extraction and prospecting | Mining drills, pumps, deposit scanners | Candidate inventory in Category 1. |
| Ore processing and production | Crushers, separators, furnaces, reactors, refineries, assemblers | Categories 2-10 and 15 cover specialized production; disposition for general-purpose crafting/assembly remains to be recorded. |
| Power generation and storage | Boilers, generators, solar, accumulators, batteries | Core candidates in Category 11. |
| Power distribution | Poles, lines, transformers, substations | Custom transmission and grid-stabilization systems are extension-only; baseline vanilla pole-network treatment remains to be verified. |
| Item transport and storage | Belts, splitters, inserters, chests, logistics bots, roboports | Category 13 has candidate belts, sorting/insertion, hubs, and storage; exact vanilla retained/replaced coverage remains to be reconciled. |
| Rail transport | Track, signals, stations, locomotives, wagons | Freight terminal is in Category 13; track/signal coverage and rolling-stock scope need a disposition. Non-building rolling stock belongs in [Intermediate Products](intermediate-products.md). |
| Fluid transport and storage | Pipes, pumps, tanks, valves | Candidate inventory in Category 14. |
| Defense and military placeables | Turrets, walls, gates, mines, repair/supply entities | Category 12 covers turret and support candidates; other placeable-defense families need a disposition with [Military System](military-system.md). |
| Factory support and alerts | Beacons, radars, lamps, programmable speakers, repair/charging stations | These placeable support families need an explicit disposition, including whether vanilla entities are retained or replaced. |
| Research, observation, and endgame facilities | Labs, observation or satellite facilities, launch/endgame sites | Category 17 and provisional endgame pathways; science packs and other non-building outputs belong in [Intermediate Products](intermediate-products.md). |
| Automation, control, and sensing | Sensors, combinators, circuit networks, PLCs, alarms | Candidate inventory in Category 18; explicit vanilla circuit-network entities and wires need a disposition. |
| Waste, recycling, and pollution handling | Tailings recovery, reprocessing, incinerators | Candidate inventory in Category 16; other pollution-handling entities need a scope check. |
| Terrain and construction utilities | Landfill, tiles, concrete, construction robotics | Construction Bot Bay is in Category 13; terrain behavior belongs in [Map and World Generation](map-world-generation.md), while construction products belong in [Intermediate Products](intermediate-products.md). Placeable types still need a disposition. |
| Non-building constructables (excluded here) | Vehicles, fuel, weapons/ammo, armor/equipment, modules, research packs | Product identities belong in [Intermediate Products](intermediate-products.md); domain behavior remains with the relevant system documents. |

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

## 2. Ore Preparation & Concentration

All preparation machines are player-built and should be multi-tiered with **different materials per tier** — especially wear-resistant surfaces that change the machine's material class. Crushing/grinding is abrasive by nature: each tier introduces a new hardness class of cutting/grinding surface.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Jaw Crusher** (MTier 1–3) | Phases 1–2 | T1: Steel frame + cast-iron jaw plates. Limited to soft ores (hematite, malachite). T2: Tungsten-carbide jaw plates + chrome-molybdenum wear liners. Can process hard sulfide ores (chalcopyrite, galena) without rapid jaw plate degradation. T3: Tungsten-carbide jaw inserts + niobium-microalloyed frame structure + automated feed regulation | T1 produces *large, inconsistent fragments* (~50 mm+) — too coarse for downstream grinding efficiency. T2 handles *hard ores*: tungsten-carbide surfaces resist wear from sulfide minerals, producing uniform ~10 mm output. T3 adds *controlled gap adjustment*: auto-regulates discharge opening to maintain consistent particle size regardless of ore hardness variation |
| **Cone Crusher** | Phase 2 | Single-tier: steel frame + manganese-steel crushing cone + tungsten-carbide bowl liner. Produces more uniform ~5 mm output than jaw crusher, used for secondary crushing stage. | No tier progression — this is a *complementary* machine to the jaw crusher with one specific function (secondary size reduction). Material selection matters more than tiers |
| **Ball/Rod Mill** (MTier 2–4) | Phases 2–3 | T1: Steel drum lining + basic steel grinding media. Limited to soft ores only — drum wear rate exceeds usable throughput for hard materials. T2: Chrome-molybdenum drum lining + tungsten-carbide grinding media segments. Can process medium-hard ores at acceptable wear rates. T3: Niobium-microalloyed pressure drum + tungsten-carbide liner system + automated media replenishment mechanism. High throughput with continuous operation. T4: Titanium-alloy rotating assembly + semiconductor-grade vibration monitoring + automated charging/discharging | T1 only works for *soft ores* — hard ore causes rapid drum wear that exceeds economic lifetime. T2 can process *sulfide concentrates* at acceptable wear rates (media and liner life >500 hours). T3 enables *continuous operation*: auto-replenishment of worn grinding media without shutdown — critical before scaling any high-volume concentration process. T4 adds *precision monitoring*: vibration sensors detect bearing wear before catastrophic failure, with automated feed reduction to prevent damage |
| **Roller Mill** | Phase 3 | Single-tier: steel frame + tungsten-carbide roller surfaces + chrome-alloy adjustment mechanism. Compression grinding for hard minerals with better energy efficiency than ball mill. | No tier progression — specialist machine for *hard mineral processing only*. Replaces ball mill when ore hardness exceeds economic milling capacity |
| **Vibrating Screen / Classifier** (MTier 1–3) | Phases 1–2 | T1: Steel frame + basic wire mesh screen panels. Single-stage screening only. T2: Chrome-molybdenum vibrating mechanism + tungsten-carborde screen mounting hardware. Two-stage classification with adjustable cutoff sizes. T3: Niobium-microalloyed structural frame + semiconductor-grade vibration frequency controller + automated multi-port discharge | T1 produces *single-size fraction output* — all material either passes through or doesn't, no intermediate sorting. T2 enables *multi-size classification*: separates ground ore into 3+ size fractions for different downstream processes (coarse to roaster, fine to flotation). T3 adds *dynamic screening control*: auto-adjusts vibration frequency based on feed rate, preventing screen blinding and maintaining throughput |
| **Mineral Washer** | Phase 1–2 | Single-tier: steel tank + water inlet/outlet system + agitator mechanism. Simple agitation-based removal of surface clays from raw concentrates before flotation. | No tier progression — early-stage prep machine with one function. Low technical complexity; no capability change across tiers |

### Density & Magnetic Separation

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Spiral Concentrator** | Phase 2 | Single-tier: steel frame + chrome-alloy spiral trough surface. Gravity-based density separation — no reagents, no power required. Works on chromite, platinum-group minerals, gold in mineral sands. | No tier progression — this is a *low-capital gravity concentrator*. Its capability is fixed by the geometry of the spiral; it concentrates what the deposit allows but cannot separate fine particle ranges or weakly magnetic minerals |
| **Jigging Machine** | Phase 2 | Single-tier: steel frame + sieve plate assembly + air-driven piston mechanism. Pulsed-water gravity separation for coarse particles (>0.5 mm). Higher capacity than spiral concentrator but coarser cut point. | No tier progression — *complementary* to the spiral concentrator with different particle size range. Material selection matters only for wear resistance |
| **Magnetic Drum Separator** (MTier 1–3) | Phases 1–3 | T1: Basic electromagnet (copper-wire coil, iron core) + steel housing. Can extract strongly magnetic minerals (magnetite, chromite) from gangue. Limited field strength — cannot separate weakly paramagnetic ores. T2: Superconducting magnet winding (NbTi wire) + cryogenic cooling jacket (LN₂ circuits) + HfO₂ dielectric insulation. Much stronger field — can extract *weakly magnetic minerals* (ilmenite, some chromium deposits). T3: Niobium-microalloyed separation chamber + niobium-tin shielding layers + precision electromagnetic control | T1 extracts *only strongly magnetic* materials — magnetite is recovered but ilmenite and chromite traces pass through to tailings (loss of valuable secondary materials). T2 enables *paramagnetic recovery*: can separate weakly magnetic minerals that T1 would miss, effectively doubling the material recovery rate from titanomagnetite deposits. T3 adds *tunable field strength*: variable magnetic force allows one machine to process different deposit types by adjusting separation threshold — the tier where a single separator serves multiple mineral feed streams |
| **Electrostatic Separator** | Phase 3 | Single-tier: high-voltage electrode assembly + niobium-microalloyed insulation chambers + tungsten-carbide separating surfaces. Separates conductive vs. non-conductive minerals by charge in high-voltage field. Used for ilmenite/rutile separation from zircon concentrates. | No tier progression — this is a *high-voltage specialist* with fixed capability. The player must choose the right electrode configuration during construction to match the target mineral pair |
| **Friction/Contact Separator** | Phase 3 | Single-tier: niobium-microalloyed rotating drum + tungsten-carbide contact surfaces + semiconductor-grade particle detection sensors. Fine separation by friction coefficient — complements magnetic/electrostatic separators for specific mineral pairs. | No tier progression — specialist separator used only when magnetic and electrostatic methods are insufficient. Material selection (tungsten carbide) is critical for wear resistance |


### Froth Flotation

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Rougher Flotation Cell | Phase 2 | Bulk concentration of sulfide ores (chalcopyrite, sphalerite, galena) | Requires collector + frother reagents; produces rough concentrate |
| Cleaner/Scavenger Flotation Bank | MTier 1–3 (Phases 2–3) | Re-process rougher tailings or re-clean concentrates for higher grade | Bank = multiple cells in series; tier = cell count + air control precision |

## 3. Thermal Processing

All thermal machines must be tiered with **different refractory/structural materials per tier** — this is the Bob principle: higher temperature = different material class, not just "bigger." The tier progression mirrors real industrial capability: from simple masonry kilns to precision-controlled high-temperature reactors.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Rotary Dryer** (MTier 1–2) | Phase 1–2 | T1: Steel shell + basic heating element (coal/gas burner). T2: Chrome-alloy shell with refractory brick lining (alumina/silica composite) — can handle wet concentrates without corrosion | T1 only dries clean, non-corrosive materials (sand, stone). T2 accepts *wet mineral concentrates* containing sulfide minerals — the first dryer that won't be corroded by acidic moisture from ore processing |
| **Roaster (Oxidizing)** (MTier 1–3) | Phases 1–2 | T1: Steel shell + basic refractory lining. Off-gas vented to atmosphere (pollution). T2: Chrome-molybdenum hot-gas ducts + catalytic converter insert (Pt-group on alumina substrate) for off-gas capture. T3: Niobium-microalloyed thermal chamber + integrated gas scrubbing system | T1 vents all SO₂ and process gases as pollution — player must choose between efficiency and environmental impact. T2 *captures off-gas*: produces usable SO₂ feedstock for sulfuric acid production. T3 adds *acid scrubbing*: captures residual particulates and can convert them to saleable sulfate byproduct (circular economy) |
| **Calciner** | Phase 2 | Single-tier: steel vessel + high-grade refractory brick (alumina/silica/crome composite). Controlled atmosphere for thermal decomposition without oxidation. Used for limestone → lime + CO₂ and other calcination reactions. | No tier progression — this is a *specialized* process machine with one clear function. Material selection matters more than tier count |
| **Rotary Kiln** (MTier 2–3) | Phases 2–3 | T1: Steel shell + basic refractory lining + manual temperature control. Limited to <900°C. T2: Chrome-molybdenum pressure shell + niobium-microalloyed thermal insulation layer + semiconductor-grade temperature sensors. Can reach 1200°C with ±5°C precision. T3: Niobium-microalloyed vessel + tungsten-carbide internal wear protection + automated material feed system | T1 can only perform simple calcination (limestone → lime). T2 enables *high-temperature sintering and roasting* — the temperature needed for metallurgical silicon reduction and other pyrometallurgical processes. T3 adds *continuous operation*: auto-feed with no manual loading, required before scaling up any high-volume thermal process |
| **Sintering Machine / Sinter Strand** | Phase 2 | Single-tier: steel frame + chrome-alloy heating elements + refractory mesh belt + cooling water jacket. Produces porous sintered ore pellets from fine-grained ores. | No tier progression — one specific function (agglomerating fines into furnace-ready lumps). Material is chosen once for the full lifetime of the machine |
| **Pellet Press / Briquette Machine** (MTier 1–3) | Phases 1–3 | T1: Steel frame + basic hydraulic press + replaceable tooling. Simple briquetting only. T2: Chrome-molybdenum press components + niobium-microalloyed pressure vessel + precision die system. Can press powders into dense, structurally sound pellets. T3: Tungsten-carbide pressing dies + tungsten-carbide guide rails + hydraulic servo control | T1 can only form *loose briquettes* — low mechanical strength, disintegrates under high pressure/temperature (unsuitable for blast furnace feed). T2 produces *dense structural pellets* — withstands blast furnace conditions. T3 adds *precise compaction*: controlled density variation within each pellet (e.g., harder outer shell, more reactive core) |
| **Spray Dryer** | Phase 2 | Single-tier: steel chamber + refractory lining + atomizer nozzle assembly + hot gas inlet. Atomizes liquid slurry into dry powder via hot gas contact. | No tier progression — specialist dewatering machine used between solution processing and crystallization steps |



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

All chemical reactors must be tiered with **different pressure/temperature/material compatibility ratings per tier**. Higher tier = the machine can handle more extreme process conditions, not just "bigger." This is where material selection creates real engineering decisions: wrong tier choice leads to corrosion, leaks, or catastrophic failure.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Tank Leach Cell / Agitated Vessel** (MTier 1–3) | Phase 2 | T1: Carbon steel vessel + rubber liner. Can handle only mild acids (dilute H₂SO₄ <10%). Limited agitation speed. T2: Stainless steel 316L vessel + PTFE internal coating + niobium-microalloyed agitator shaft. Handles concentrated acids and elevated temperatures (80–120°C). T3: Niobium-microalloyed pressure vessel + tantalum-clad internals + semiconductor-grade pH/temperature control | T1 can only leach *moderately corrosive* ores (hematite, magnetite with dilute acid). T2 handles *concentrated acids at high temperature* — the tier where copper/nickel leaching becomes viable. T3 adds *automated process control*: real-time pH and temperature monitoring with auto-adjustment, producing consistent leach solutions without manual calibration |
| **Heap Leach Pad + Sprayer System** | Phase 2 | Single-tier: steel support structure + PTFE-lined containment basin + spray nozzle array. No power required — purely reagent-driven extraction of low-grade ores from stacked ore piles. | No tier progression — this is a *low-capital alternative* to tank leaching with much slower throughput but zero power cost. The player trades time/space for infrastructure cost |
| **Pressure Leach Autoclave** (MTier 1–3) | Phases 2–3 | T1: Thick-walled steel vessel + chrome-alloy internal seal + manual pressure gauge. Max pressure 15 bar, max temp 200°C. Can leach moderately refractory ores. T2: Niobium-microalloyed pressure shell + tantalum-clad interior surface + ceramic insulation layer. Handles up to 40 bar / 350°C — the range where complex sulfide ores (chalcopyrite, pentlandite) become economically leachable. T3: Tungsten-carbide wear-resistant internals + niobium-microalloyed safety relief system + automated pressure/temperature feedback control | T1 can only process *moderately refractory* ores. T2 handles *high-pressure/high-temperature refactory leaching* — this tier unlocks recovery from chalcopyrite and other hard-to-process sulfides (critical for copper/nickel production). T3 adds *safety automation*: automatic pressure relief, emergency cooling, and process interruption before catastrophic failure |
| **General-Purpose Chemical Reactor** (MTier 1–3) | Phases 1–3 | T1: Carbon steel vessel + rubber seals + manual stirring. Temperature range: ambient to 100°C (water bath heating only). Limited to mild reactions (neutralization, simple precipitation). T2: Stainless steel vessel + PTFE-lined interior + chrome-molybdenum heating jacket. Temperature range: -20°C to 300°C. Can run Ostwald nitric acid chain, ammonia oxidation. T3: Niobium-microalloyed pressure-rated vessel + HfO₂ insulated interior + semiconductor-grade PID controller. Handles exothermic reactions up to 500°C with precision thermal management | T1 limited to *mild chemistry*: pH adjustment, basic precipitation, simple neutralization. T2 unlocks *industrial-scale chemical synthesis*: Ostwald chain (NH₃ → HNO₃), ammonia oxidation, Fischer-Tropsch. T3 handles *exothermic/high-temperature reactions with precision control*: where temperature drift of even ±5°C changes product yield or creates safety hazards |
| **Catalytic Converter / Fixed-Bed Reactor** | Phase 2+ | Single-tier: steel vessel + refractory brick lining + catalyst loading bay (replaceable catalyst bed support). Requires specific catalyst material input per recipe. | No tier progression — this is a *catalyst-specific* reactor. The key variable is the catalyst material, not machine tier. Different catalysts enable different reactions in the same hardware |
| **Fluidized-Bed Reactor** (MTier 2–3) | Phases 2–3 | T1: Steel vessel + refractory distributor plate + basic gas inlet manifold. Limited particle size distribution control. T2: Chrome-molybdenum pressure shell + niobium-microalloyed gas distribution system + ceramic particle separator. Precise fluidization control with minimal particle loss. T3: Niobium-microalloyed thermal chamber + tungsten-carbide distributor nozzles + automated particle recirculation system | T1 provides *functional fluidization* with higher catalyst consumption per output cycle than T2+ tiers. T2 achieves *stable, controlled fluidization*: uniform gas-solid contact for efficient coal gasification or kyanite processing. T3 adds *automatic catalyst management*: recirculates and reclaims escaped particles, reducing catalyst consumption by ~60% |



## 6. Solution Processing & Separation

All solution processing machines handle corrosive chemicals in suspension or precipitation — material compatibility is the primary tier driver. The progression mirrors real hydrometallurgy: from simple gravity settling to precision chemical separation.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Vacuum Filter / Filter Press** (MTier 1–3) | Phase 2 | T1: Steel frame + rubber filter cloth + basic vacuum pump connection. Single-layer filtration, periodic auto-cleaning every 50 output cycles (machine offline for 30 seconds). Filtration rate: low. T2: Stainless steel pressure frame + PTFE membrane filter layers + automated cake discharge mechanism. Multi-layer filtration with timed release. T3: Niobium-microalloyed pressure vessel + tungsten-carbide filter support surfaces + semiconductor-grade differential pressure sensor | T1 is *fully autonomous* but requires periodic self-cleaning downtime — the player must buffer output during clean cycles or accept interruptions. T2 enables *continuous filtration with automated discharge*: filter cakes release automatically on timer, allowing unattended operation of leach circuits. T3 adds *precision monitoring*: real-time differential pressure across filter layers signals clogging before production impact — critical for automated factory integration |
| **Crystallizer / Evaporator** (MTier 1–3) | Phases 2–3 | T1: Cooling crystallizer — carbon steel shell + copper cooling coil. Simple batch evaporation only. Limited to non-corrosive salts (sodium chloride from brine evaporation). T2: Forced-circulation evaporator — stainless steel vessel + chrome-molybdenum circulation pump + PTFE heat exchanger tubes. Handles corrosive salt solutions (zinc sulfate, copper sulfate from electrowinning raffinate). T3: Vacuum crystallizer — niobium-microalloyed pressure-rated body + HfO₂ thermal insulation layer + tungsten-carbide agitator bearings + automated product discharge | T1 can only process *non-corrosive feedstocks* — brine evaporation for salt production. Corrosive solutions require PTFE lining that T1 lacks. T2 handles *corrosive industrial salts*: concentrated metal sulfate/acetate solutions from leaching and electrowinning circuits. The tier where crystallization becomes an economically viable separation step. T3 enables *vacuum-assisted low-temperature crystallization*: product purity is significantly higher (no thermal degradation of heat-sensitive compounds) — the tier required for battery-grade salt production |
| **Solvent Extraction Column** | Phase 3 | Single-tier: PTFE-lined stainless steel column internals + niobium-microalloyed support structure + precision flow control valves. Separates dissolved metals using immiscible organic solvents (e.g., copper extraction from sulfate solution). | No tier progression — this is a *specialist separation machine* with one function per configuration. The player must choose the correct extractant reagent during construction to match the target metal pair |
| **Ion Exchange Unit** | Phase 3 | Single-tier: stainless steel vessel + ion-exchange resin bed (organic polymer) + silica support layer + acid regeneration system (PTFE-lined). For uranium, rare-earth element, and trace metal recovery from solution. Resin regeneration requires periodic acid feed. | No tier progression — *specialist* machine with one function per resin type. Material is selected once for the full lifetime of the unit. Reagent consumption (acid) scales with throughput, not tier |
| **Precipitation Tank / Thickener** (MTier 1–2) | Phases 2–3 | T1: Carbon steel vessel + rubber agitator seal + basic pH sensor (glass electrode in ceramic housing). Requires periodic manual insertion of "precipitant reagent" item every 30 output cycles. T2: Stainless steel pressure vessel + niobium-microalloyed mixing impeller + semiconductor-grade automatic dosing pump | T1 is *self-running* but requires periodic reagent delivery (player or inserter) — the tier where the player must build parallel logistics for this machine. T2 enables *automated precipitation control*: real-time pH monitoring with auto-dosing of precipitating agent, producing consistent product — required before scaling any hydrometallurgical circuit beyond pilot size |
| **Centrifuge / Decanter** | Phase 3 | Single-tier: niobium-microalloyed drum (tungsten-carbide bearing surfaces) + stainless steel housing + semiconductor-grade speed controller. High-speed spinning separates fine solids from liquids rapidly. Alternative to filter press for continuous operation with finer particles. | No tier progression — *specialist* dewatering machine used when filter press throughput is insufficient. Material selection (niobium/tungsten) is chosen once for corrosive/abrasive service |


## 7. Electrochemical Processing

Electrochemical machines require **precision power delivery and corrosion-resistant materials** — each tier introduces new electrode materials, membrane quality, and control precision. This is one of the most material-rich categories because every tier adds a different conductive/insulative combination.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Electrowinning Cell / Tankhouse** (MTier 1–3) | Phases 2–4 | T1: Lead-acid alloy anodes + copper cathode starter sheets + carbon steel frame. Electrode surface area: limited. Power delivery: basic DC (rectifier input only). No auto-cathode mechanism — manual removal required. T2: Stainless steel frame + chrome-molybdenum anode support structure + niobium-microalloyed busbar connections. Larger electrode surface area. Auto-cathode swapping mechanism at MTier 3+. T3: Niobium-microalloyed pressure vessel + tantalum-bearing cathode transport system + semiconductor-grade current density monitoring | T1 produces *only one metal type* with periodic auto-cathode cycling — throughput is lower than T2+ tiers. Cannot process mixed-metal electrolytes without cross-contamination. T2 enables *continuous operation*: auto-cathode swapping allows unattended deposition of pure metal on replacement sheets. Electrode surface area triples at this tier. T3 adds *current density control*: real-time monitoring and adjustment of amperage per cell — the capability that unlocks electrowinning of alloys and selective metal recovery from mixed solutions (critical for recovering cobalt/nickel from leach solutions) |
| **Electrorefiner** | Phase 3+ | Single-tier: stainless steel vessel + nickel-plated tank interior + titanium anode support structure. Purifies impure metal by controlled deposition — copper/nickel/zinc purification from impure smelted product. No tier progression; quality determined by input purity and power stability, not machine construction. | No tier progression — *specialist* machine with one function per configuration. Material selection (anode/cathode geometry and tank chemistry) is chosen once at construction. Power quality matters more than machine tier |
| **Chlor-Alkali Membrane Cell** (MTier 2–4) | Phases 2–3 | T2: Titanium anode (dimensionally stable anode coating) + polymer membrane cell body + copper busbar connections. Can split brine into Cl₂, NaOH, and H₂ but with standard membrane configuration (~1000 hours). Higher membrane replacement cost. T3: Niobium-microalloyed housing + reinforced polymer membrane (PTFE-reinforced) + niobium-tin shielding layers. Membrane lifetime extended to ~5000 hours. Better separation efficiency — less chlorine contamination of NaOH product stream. T4: Tungsten-carbide electrode support + niobium-microalloyed pressure vessel + semiconductor-grade cell voltage monitoring | T2 produces *chlorine-contaminated caustic soda* that requires secondary purification — the tier where basic chlor-alkali chemistry becomes viable but at significant ongoing membrane consumption cost (1 membrane per 5 cycles). T3 produces *high-purity sodium hydroxide* directly from the cell, eliminating the need for separate purification infrastructure. The tier where chlor-alkali becomes economically competitive with purchased NaOH, with reduced consumable cost (1 membrane per 20 cycles). T4 adds *precision monitoring and lowest consumable cost*: semiconductor-grade voltage tracking paired with premium "high-grade membrane" item per 50 output cycles |
| **AEM Water Electrolyzer** | Phase 3 | Single-tier: stainless steel vessel + alkaline electrolyte (KOH solution) + AEM (anion-exchange membrane) separator + copper/nickel electrode plates. Splits water into high-purity H₂ and O₂ gases. Fusion-grade hydrogen purity. | No tier progression — *specialist* fuel production machine. Material selection (membrane type) is critical to performance but doesn't vary by tier |


## 8. Polymer Chemistry & Primary Processing

These are the *production* machines that transform refined chemicals into polymers, plastics, and composite materials. They must be tiered with **different reaction chamber materials** per tier — higher temperature/pressure polymerization requires different metallurgy.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Petrochemical Cracking Furnace** (MTier 1–3) | Phases 2–3 | T1: Steel shell + basic refractory lining (alumina/silica). Limited to mild cracking (<500°C) — produces narrow product range (mostly ethylene). Cannot process mixed feedstocks. T2: Chrome-molybdenum pressure shell + catalytic catalyst bed housing (nickel-alloy support structure) + PTFE-lined hot-gas ducts. Can reach 700–800°C for deeper cracking — broader product distribution (ethylene, propylene, butane). Accepts mixed hydrocarbon feeds. T3: Niobium-microalloyed reaction chamber + tungsten-carbide internal wear surfaces + niobium-tin thermal insulation layer + semiconductor-grade temperature zone control | T1 produces *only ethylene* from a single feedstock (naphtha or FT naphtha). Limited product diversity constrains downstream chemistry options. T2 enables *propylene co-production*: the tier where both ethylene and propylene are available, unlocking PVC (from ethylene + chlorine) AND acrylonitrile/acrylic (from propylene + ammonia). Critical for enabling multiple polymer pathways. T3 adds *multi-zone temperature control*: different sections of the furnace operate at different temperatures, maximizing yield of target products — reducing waste feedstock by ~30% |
| **Polymerization Reactor / Vessel** (MTier 1–3) | Phases 2–3 | T1: Carbon steel vessel + rubber agitator seal + basic temperature control. Limited to low-pressure polymerization (LDPE from ethylene). Cannot produce high-pressure polymers or engineering resins. T2: Stainless steel pressure-rated vessel + PTFE-lined interior + chrome-molybdenum agitator shaft. Can handle medium-pressure polymerization (HDPE, PVC, PMMA acrylic). Temperature range: 80–200°C. T3: Niobium-microalloyed pressure chamber + tantalum-sealed reactor internals + semiconductor-grade PID controller. High-pressure capability up to 50 bar — produces engineering polymers (Nylon 6,6 precursors, epoxy resins) | T1 produces *only low-pressure polyethylene* (LDPE). Limited to the simplest polymer chemistry — PVC and most other plastics are unavailable until MTier 2. This is a genuine *polymer selection gate*. T2 unlocks *PVC production*: medium-pressure ethylene + chlorine polymerization becomes viable, which is the foundation of fluid infrastructure materials in the mod (pipe lining, conduit insulation). Also produces HDPE and acrylic. T3 enables *engineering polymers*: epoxy resins for composite manufacturing, nylon precursors for fiber production, high-performance plastics required by later-game factories. This tier is when polymer processing transitions from "making pipes" to "building advanced materials" |
| **Extruder / Pelletizer** | Phases 2–3 | Single-tier: chrome-molybdenum barrel + PTFE die assembly + niobium-microalloyed heating elements. Melt and shape polymer output into pellets or continuous profiles. Finishing for plastics production. Tier = barrel length, heater zones, die precision within a single tier range. | No tier progression — this is a *finishing machine* that accepts output from the Polymerization Reactor and formats it for storage or downstream use. Material selection matters only for chemical compatibility with processed polymer types |
| **Injection Molding Press** | Phase 3 | Single-tier: chrome-molybdenum mold assembly + niobium-microalloyed clamping mechanism + semiconductor-grade temperature controllers. Forms polymers into complex shapes under pressure in heated mold. Produces casings, connectors, components directly from polymer melt. | No tier progression — *specialist* shaping machine for high-precision plastic parts. Used when extrusion profiles are insufficient (requires specific component geometry) |
| **Fiber Winder / Spinning Line** | Phase 3+ | Single-tier: stainless steel fiber-drawing assembly + niobium-microalloyed heating elements + precision tension control system. Draws polymer or glass fibers for composite reinforcement. Produces fiberglass or synthetic fiber feedstock for composite materials. | No tier progression — *specialist* machine with one function per configuration. Polymer type selection (polyester vs nylon) is chosen at construction, determining final fiber strength and chemical resistance |


## 9. Semiconductor Fabrication Chain

Semiconductor machines are tiered with **increasing precision capabilities** — each tier introduces new fabrication capabilities, not just throughput. The materials progression mirrors the real semiconductor industry: from basic processing to nanometer-scale precision. Bridge products (polysilicon, HfO₂ dielectric) appear as infrastructure needs here, giving them real-world factory applications beyond endgame assembly.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Purification Column (polysilicon grade)** | Phase 3 | Single-tier: high-purity silica/ceramic column internals + niobium-microalloyed reflux condenser. Trichlorosilane distillation for electronic-grade silicon purification. | No tier progression — *specialist* purity machine. Silica quality and ceramic grade determine maximum achievable purity; built once at correct specification |
| **Czochralski Crystal Grower** (MTier 1–3) | Phase 3 | T1: Graphite crucible + basic inert atmosphere system + copper-wound heating coil. Maximum ingot diameter: 50 mm. Limited rotation control precision (~±10 RPM). Single-crystal growth possible but with moderate defect density. T2: Niobium-microalloyed graphite crucible liner + niobium-tin temperature control wiring + HfO₂ thermal insulation layer. Maximum ingot diameter: 150 mm. Rotation control ±1 RPM — enables doping uniformity required for semiconductor-grade wafers. T3: Tungsten-carbide crucible support + semiconductor-grade inert atmosphere monitoring + automated seed crystal positioning | T1 produces *wafers with high defect density* — sufficient only for basic photovoltaic cells, not integrated circuits. The player can make solar-grade polysilicon crystals but cannot yet produce chips from them. T2 produces *semiconductor-grade wafers*: larger diameter (150 mm) with controlled doping uniformity — the tier where crystalline silicon transitions from solar to electronics use. T3 adds *automated growth control*: computer-controlled seed descent and rotation optimization, reducing manual calibration steps and improving yield |
| **Floating Zone Furnace** | *(removed)* | Consolidated into existing purification column → crystal grower chain. One purification stage is sufficient. | No tier progression — *specialist* purification step used between purification column and crystal growing when higher purity is required |
| **Wafer Saw / Multi-Wire Diamond Cutter** | MTier 1–3 (Phase 3) | T1: Steel frame + basic diamond wire tensioning. Produces thick wafers. Recipe input: 2 ingots → 6 wafer blanks (lower yield per ingot). T2: Niobium-microalloyed cutting head + tungsten-carbide wire guide bearings + precision tension control system. Recipe input: 1 ingot → 5 wafer blanks (improved yield over T1). T3: Tungsten-carbide wire drive system + niobium-microalloyed coolant circulation + semiconductor-grade thickness measurement sensor. Recipe input: 1 ingot → 8 wafer blanks (highest yield). | T1 requires *more input ingots per output wafer* — the player must account for higher polysilicon consumption across the chain. T2 improves *material utilization*: fewer ingots needed per wafer, reducing bottleneck pressure across the production chain. Produces thinner, more uniform wafers suitable for both solar and basic electronics. T3 enables *sub-100 µm wafer production* — required for advanced multi-layer chip packaging where thin die are stacked vertically |
| **Chemical-Mechanical Polisher (CMP)** | Phase 3 | Single-tier: niobium-microalloyed polishing chamber + tungsten-carbide platen + semiconductor-grade slurry delivery system. Polishes wafer surface to nanometer roughness with controlled abrasive slurry + pad. Prepares ultra-flat surface before lithography. | No tier progression — *specialist* finishing machine with one function per slurry type (different slurries for silicon, copper, dielectric polishing) |
| **Wet Etch Bath / Station** (MTier 1–3) | Phases 3–4 | T1: Plastic (HDPE) tank + rubber seals. Handles only mild etchants (dilute HF). Cannot process concentrated acids or elevated temperatures. Limited to basic wafer cleaning operations. T2: PTFE-lined stainless steel vessel + niobium-microalloyed heating jacket + semiconductor-grade pH/temperature control. Handles concentrated hydrofluoric acid, HNO₃/HF mixtures (piranha etch), and elevated temperatures up to 100°C. Etches silicon at controlled rates. T3: Niobium-microalloyed pressure-rated vessel + tungsten-carbide heating elements + automated chemical dosing system | T1 can perform *only basic cleaning* — insufficient for wafer preparation before lithography where nanometer-scale surface quality matters. Restricted to mild HF use only. T2 enables *controlled silicon etching*: the tier where actual semiconductor patterning chemistry becomes viable (HNO₃/HF mixtures selectively etch crystalline silicon at known rates). Critical capability gate — without this tier, no lithography or deposition steps are possible. T3 adds *automated chemical management*: precise dosing and concentration control ensures consistent etch rates — essential for production reliability |
| **Thermal Oxidation / Diffusion Furnace** (MTier 2–4) | Phases 3–4 | T2: Tube furnace design — niobium-microalloyed reaction tube + tungsten-carbon heating elements + precise oxygen/water vapor inlet system. Single-zone temperature control (~±10°C). Batch processing of single wafer loads. T3: Multi-zone tube furnace — niobium-microalloyed tube with separate zone controllers + semiconductor-grade thermocouple array + automated wafer loading mechanism. 5+ independently controlled temperature zones. Can process multiple wafers simultaneously with gradient-controlled oxidation profiles. T4: Rapid thermal processor — tungsten-carbide heating elements + niobium-microalloyed radiation shields + real-time infrared wafer temperature monitoring | T2 produces *single-wafer batches* with limited uniformity across the wafer surface — acceptable for early-stage prototyping but inefficient for production. Oxidation rate varies by position within the tube. T3 enables *multi-wafer batch processing*: independent zone control means different wafers can undergo different oxidation profiles simultaneously. Production throughput doubles. T4 adds *rapid thermal processing*: heats/cools wafers in seconds rather than hours — the capability needed for advanced dopant diffusion where precise thermal time-temperature profiles create specific junction depths |
| **CVD / PVD Deposition Chamber** (MTier 2–4) | Phases 3–4 | T2: Basic deposition chamber — niobium-microalloyed reaction vessel + tungsten-carbide susceptor + RF/heating power supply. Can deposit basic dielectric layers (silicon dioxide, silicon nitride). Film thickness precision: ±10%. Limited to simple deposition processes. T3: Multi-process deposition chamber — niobium-microalloyed process chamber with switchable CVD/PVD tooling heads + semiconductor-grade gas delivery system + real-time film thickness monitoring. Can deposit metal layers (copper, aluminum), dielectric layers, and conductive layers. Film precision: ±2%. T4: Advanced deposition system — niobium-microalloyed ultra-clean deposition chamber + tungsten-carbide target materials + semiconductor-grade plasma source for PVD | T2 can deposit *only basic insulating layers* (SiO₂ dielectric) — the first layer needed for transistor isolation but insufficient for interconnects. Cannot deposit metal films. T3 unlocks *metal deposition*: copper and aluminum wiring layers become available — the tier where actual circuit fabrication begins. Can also deposit additional dielectric materials (high-k dielectrics like HfO₂ for advanced insulation). T4 enables *advanced plasma-enhanced deposition*: higher quality films with better step coverage, required for sub-micron feature deposition in advanced chip manufacturing |
| **Photolithography Stepper / Aligner** | Phase 4+ | Single-tier: the most complex single machine in the mod. Requires cleanroom enclosure module to operate. Composed of: electronic-grade polysilicon lens elements (silicon optics for UV), precision ceramic positioning stages (niobium-microalloyed), semiconductor-grade position sensors, and illumination system. Exposes photoresist patterned through reticle/photomask onto wafer surface. | No tier progression — this is a *single-tier ultra-precision machine*. Every component must be at the highest specification simultaneously; no "upgrade path" exists because the limiting factor is always the most precise component present |
| **Cleanroom Module** | Phase 3+ | Single-tier (large modular facility, ~4×4 tiles): HfO₂ particulate filtration panels + fluoropolymer duct lining (PTFE) + niobium-microalloyed structural frame + semiconductor-grade air quality sensors. Has 6 modular insertion slots. Each slot accepts cleanroom component tier: T1-T2 inserts (steel/copper) produce "basic-clean wafers." T3 inserts (niobium/tantalum) produce "high-clean substrates." Full 6-slot fill with T3 components produces "ultra-clean wafers" required for advanced photolithography. | The cleanroom is a *buildable machine* rather than spatial prerequisite — players construct it as a large facility and fill modular slots to increase output cleanliness level. Different recipes require different cleanliness tiers as input items |

| **Semiconductor Packaging Line** | Phase 4 | Single-tier: copper lead frame feeder + gold wire bonding station (tungsten-carbide capillary tool) + plastic/molded ceramic package molding press. Produces packaged integrated circuits from fabricated dies. Three sub-steps on one continuous line: die-attach station → wire-bonding machine → molding press. | No tier progression — *specialist* assembly line with one configuration per bond type (gold vs copper wire, plastic vs ceramic package). Material selection is made at construction |


## 10. Nuclear Fuel & Component Fabrication

All nuclear fabrication machines handle materials with extreme value density and safety sensitivity — each tier introduces different containment, precision, and automation capabilities. Bridge products (zirconium, hafnium, Nb₃Sn wire) appear as infrastructure needs here, giving them real-world factory applications beyond endgame assembly.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Uranium Conversion Line** | Phases 2–3 | Single-tier: stainless steel 316L vessels (UF₆ corrosion-resistant) + PTFE gaskets/linings + graphite crucibles. Multi-stage: leach/purification tank → precipitation → pellet pressing station → sintering furnace. Converts yellowcake concentrate to UO₂ powder and pressed pellets. | No tier progression — *specialist* nuclear facility with one function per configuration. Material selection (stainless 316L + PTFE) is chosen once for the full corrosive service lifetime |
| **Fuel Pellet Sintering Furnace** | Phase 3 | Single-tier: refractory construction (high-purity alumina/silica brick) + niobium-microalloyed heating elements. Fires pressed UO₂ pellets at high temperature (~1700°C) for densification and strength. | No tier progression — *specialist* thermal processing machine. Temperature capability determines fuel pellet quality; built once at correct specification |
| **Cladding Tube Mill** | Phase 3 | Single-tier: stainless steel tube-forming equipment + niobium-microalloyed pressure testing chamber. Forms Zr-alloy tube from ingot via extrusion/piercing + pilger rolling. Produces hollow zirconium cladding for fuel rods. Tier = pressure vessel quality and precision forming capability within single tier range. | No tier progression — *specialist* metal-forming machine. Zirconium alloy selection determines neutron transparency; built once at correct specification |
| **Fuel Rod Assembly Line** (MTier 1–3) | Phases 3–4 | T1: Manual load/station design — steel frame + basic alignment fixtures + operator-fed pellet loading mechanism. Low throughput; each pellet loaded by manual operation with quality inspection between stations. T2: Semi-automated pellet loader — stainless steel automated feeder + niobium-microalloyed alignment jig + helium leak-test station (PTFE-sealed test chamber). Automated loading reduces labor cost by ~70%. Fully automatic end-cap welding station. T3: Fully automated assembly with inline inspection — niobium-microalloyed structural frame + semiconductor-grade radiographic inspection system + automated quality rejection sorting | T1 processes *single-rod batches per cycle* — limited throughput compared to multi-rod higher tiers. T2 achieves *semi-automated production*: consistent rod quality with helium leak-test verification of each assembled rod before leaving the line. Throughput increases ~7× over manual. End-cap welding eliminates manual seal work (critical for nuclear safety). T3 adds *automated quality assurance*: radiographic inspection verifies pellet spacing, cladding integrity, and weld quality on every single rod — eliminating manual sampling. Required before building more than a handful of fission reactors |
| **Zr/Hf Separation Plant** | Phases 2–3 | Single-tier: stainless steel processing vessels + PTFE-lined separation columns + niobium-microalloyed structural support. Processes zircon ore concentrate → produces zirconium ingot (primary output) as a single recipe with hafnium powder as a by-product item. Separates co-produced elements via fractional chlorination. **Simplified from multi-step distillation to single-recipe-by-product model.** | No tier progression — *specialist* separation machine. Material selection (corrosion-resistant alloys for ZrCl₄ service) is chosen once at construction |
| **Hafnium Absorber Plate Liner** | Phase 3 | Single-tier: stainless steel forming equipment + tungsten-carbide cutting tools. Rolls/form Hf metal into control-rod absorber plates (often with B₄C). Co-product of Zr-Hf separation — produces hafnium-based components for fission reactor construction. | No tier progression — *specialist* material-forming machine with one function per plate thickness/design |
| **Boron Carbide Press + Sintering Furnace** | Phases 2–3 | Single-tier: tungsten-carbide pressing dies + niobium-microalloyed sintering furnace. Powder metallurgy: mixing mill → isostatic press → sintering furnace for B₄C control rod absorbers. | No tier progression — *specialist* powder metallurgy line with one function per absorber design |
| **Lithium Breeder Blanket Panel Assembler** | Phase 4+ | Single-tier: niobium-microalloyed structural frame + tungsten-carbide welding equipment + semiconductor-grade dimensional control system. Assembles Li-containing breeder material into heat-exchange panel modules for tokamak. Endgame nuclear: produces first wall/blanket components for fusion reactor construction. | No tier progression — *specialist* endgame assembly machine with one function per panel design |
| **Tungsten Armor Tile Molder** | Phase 4+ | Single-tier: high-temperature pressing equipment (niobium-microalloyed furnace) + tungsten-carbide mold inserts + semiconductor-grade thermal profiling. Forms sintered W-tungsten tiles for tokamak inner-wall plasma-facing surfaces. Requires extreme temperature pressing; produces armor-grade tungsten plates/tiles. | No tier progression — *specialist* refractory forming machine with one function per tile geometry |
| **Superconducting Coil Winding Machine** (MTier 2–4) | Phases 3–4 | T2: Manual winder design — steel frame + niobium-tin tension control mechanism. Limited to small-diameter coils. Operator-controlled winding tension with manual termination points. T3: Automated tension-controlled winder — stainless steel frame + niobium-microalloyed drive system + PTFE-insulated tensioning arms + automated layer insulation applicator (HfO₂ dielectric). Consistent tension across full coil length. Eliminates hot spots from uneven winding. T4: Cryogenic-grade insulator applicator — niobium-microalloyed fully enclosed winding chamber + automated cryogenic-compatible insulation application system + semiconductor-grade position feedback for sub-millimeter wire placement precision | T2 produces *inconsistent coils*: manual tension control creates localized stress points that can crack insulation during cryogenic cooldown. Acceptable for prototype magnets but not production use. T3 produces *production-quality coils* with uniform winding tension and automated inter-layer insulation — the tier where superconducting magnet fabrication transitions from experimental to industrial. T4 enables *cryogenic-grade precision*: sub-millimeter wire placement accuracy required for high-field fusion magnets where even 0.5 mm displacement changes magnetic field distribution significantly |
| **Precision Optics Fabrication Station** | Phase 4+ | Single-tier: cleanroom enclosure (HfO₂ particulate filtration + fluoropolymer duct) + diamond-turning lathes (tungsten-carbide tooling) + niobium-microalloyed vibration isolation table. Produces optical substrate components for endgame Extreme-Energy Core construction. Requires electronic-grade polysilicon blanks as input material. | No tier progression — *specialist* ultra-precision machine with one function per optical element type |
| **Extreme-Pressure Containment Vessel Assembler** | Phase 4+ | Single-tier: niobium-microalloyed structural frame + tungsten-carbide shell-forming tools + automated welding systems (semiconductor-grade process control) + autoclave curing chambers (refractory-lined). Welds/assembles multi-layer pressure vessel shells for Hawking Engine containment. Shell forming → autoclave curing of composite layers → in-situ welding inspection at high tiers. | No tier progression — *specialist* endgame assembly machine with one function per vessel design |
| **Thermoelectric Conversion Array Module** | Phase 4+ | Single-tier: cleanroom-compatible assembly station (HfO₂ particulate filtration + fluoropolymer duct) + semiconductor-grade thermocouple junction bonding equipment (niobium-microalloyed frame). Assembles p-type/n-type semiconductor thermocouple pairs into power-conversion panels. Converts waste heat to electricity via Seebeck effect. | No tier progression — *specialist* semiconductor assembly machine with one function per thermocouple material pair |


## 11. Power Generation

> Full power system details are in [Power System](power-system.md). This catalog lists generator, distribution, and storage families.
>
> **Progression discrepancy:** This candidate inventory places fission in Phases 3-4 and fusion in Phase 4+, while [Power System](power-system.md) places them in Phases 2 and 3. Preserve both source values until the progression is reconciled in Phase 3.

### Power Generation (Candidate Core Generators — Tiered Builds)

Generators must be tiered with **different structural materials per tier** — higher power output requires higher-grade pressure vessels, heat exchangers, and containment. Each tier also increases the machine's fuel/efficiency profile.

| Generator Type | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Enhanced Steam Engine** (MTier 1–3) | Phases 1–2 | T1: Steel boiler vessel + basic copper heating coils + cast-iron firebox. Multi-fuel support for any combustible solid (coal, coke, charcoal). Simple water feed system. Power output: baseline. Heat recovery: minimal (~60% thermal efficiency). Manual ash removal required. T2: Chrome-molybdenum pressure vessel upgrade + niobium-microalloyed heat exchange surfaces + automated ash removal mechanism. Improved heat transfer surface area. Higher thermal efficiency (~75%). Semi-automated water/feedwater system. T3: Niobium-microalloyed pressure-rated boiler + tungsten-carbide heating element inserts + semiconductor-grade steam quality monitoring | T1 is a *basic boiler*: burns any solid fuel but with low thermal efficiency and significant manual maintenance (ash removal). Acceptable for early game when scale is small. Heat loss is high, making it expensive to run at large scale. T2 adds *improved heat transfer*: niobium-microalloyed surfaces increase surface area for heat exchange, significantly improving fuel utilization. Auto ash removal eliminates one major maintenance bottleneck. The tier where steam engines become economically viable as a sustained power source. T3 enables *steam quality monitoring*: real-time monitoring of steam temperature/pressure at the outlet — prevents sending wet steam (which damages downstream turbines) into factory processes that require dry steam |
| **Solar Panel Array** (MTier 1–3) | Phases 1–2 | T1: Steel mounting frame + glass panel surface (silica + soda-ash flux) + basic copper wiring. Basic silicon photovoltaic cells (metallurgical-grade). Low conversion efficiency (~8%). No tracking mechanism — fixed orientation toward sun. T2: Aluminum alloy mounting brackets (lightweight, corrosion-resistant) + semiconductor-grade silicon solar cells (polysilicon-derived, ~15% efficiency) + tantalum capacitor charge controller. Higher-efficiency PV cells require electronic-grade polysilicon purification infrastructure. T3: Multi-junction photovoltaic stack (gallium-arsenide top cell from gallium/arsenic, silicon middle cell, germanium bottom cell from germanium trace recovery) — ~25% conversion efficiency | T1 produces *low power density*: only 8% of incident solar energy converted to electricity. Requires large physical footprint for meaningful output. Acceptable in early game when space is abundant and solar supplementation (not primary power). The tier where the player can still use basic metallurgical-grade silicon cells without needing cleanroom infrastructure. T2 requires *cleanroom-dependent polysilicon* for higher-efficiency cells — the first generator tier that connects to semiconductor fabrication. 15% efficiency reduces required panel count by nearly 3× over T1. This is where solar transitions from "nice-to-have supplement" to "viable sustained power source." T3 requires *gallium, arsenic, and germanium* from trace recovery — the tier that validates the entire rare/trace material recovery chain. Multi-junction cells achieve near-commercial terrestrial efficiencies (~25%), making solar farms genuinely competitive with combustion generation |
| **Wind Turbine (enhanced)** | Phase 1 | Single-tier: steel tower structure + copper generator winding + basic bearing assembly. Enhanced vanilla turbine with tiered efficiency ratings. Needs pole infrastructure for power delivery. Output varies by season/weather. | No tier progression — this is a *location-dependent renewable* with one structural design. Material is selected once at construction; no meaningful upgrade path exists because wind physics (height, blade length, generator diameter) are fixed at build time |
| **Oil Gasifier / Producer-Gas Reactor** | Phases 1–2 | Single-tier: steel vessel + basic refractory lining + controlled air/steam inlet system. Gasifies coal or heavy oil residue into producer gas (CO + H₂) for steam engine fuel. Early diversification option when oil is available. Bridges gap between solid-fuel and liquid-fuel power. | No tier progression — *specialist* gas production machine with one function per feedstock type (coal vs. oil residue) |
| **Diesel Burner / Liquid-Fuel Engine** | Phase 2 | Single-tier: steel combustion chamber + copper cooling jacket + chrome-alloy injector nozzles. Burns refined liquid fuel in combustion chamber for steady power output. First reliable high-output continuous power before fission; requires oil refining to produce liquid fuel. | No tier progression — *specialist* combustion engine with one function per fuel type (diesel vs. FT synthetic) |
| **Biomass Digester / Biogas Reactor** | Phase 2 | Single-tier: steel digestion vessel + PTFE-lined interior (anaerobic seal) + ceramic gas collection system. Anaerobic breakdown of organic matter → methane biogas for power generation. Alternative renewable; batch digester → continuous stirred-tank → pressurized reactor at higher tiers. | No tier progression — *specialist* biological processing machine with one function per feedstock composition |
| **Geothermal Tap / Heat Exchanger Station** | Phases 2–3 | Single-tier: titanium heat exchanger plates (corrosive brine/steam resistance) + niobium-microalloyed pressure housing. Extracts heat from volcanic zones or deep geothermal reservoirs near hotspots. Tier = depth of tap, heat extraction rate within single design range. Location-dependent: only placeable near specific terrain features. | No tier progression — *specialist* location-dependent facility with one structural design |
| **Thermal Fission Reactor** (MTier 1–4) | Phases 3–4 | T1: Steel pressure vessel + graphite moderator blocks + basic copper cooling circuit. Simple control system (manual rod adjustment). No automatic safety features beyond operator intervention. Moderate power output, requires frequent manual monitoring. T2: Zirconium-clad fuel channels (from cladding tube mill) + hafnium control rod segments (from separation plant) + stainless steel primary coolant loop. Automatic control rods with basic servo response to temperature. First tier with *real nuclear safety infrastructure*: the tier where fission transitions from experimental power source to viable industrial generator. Beryllium neutron multiplier reflector for improved fuel efficiency. T3: Niobium-microalloyed reactor core basket + tungsten-reinforced steam generator tubes + semiconductor-grade instrumentation (temperature, pressure, neutron flux monitoring) | Automated safety shutdown system with multiple redundant sensors. Fully automated control rod positioning based on real-time conditions. The tier where fission becomes a *set-and-forget* power source — no longer requiring operator attention. T4: Advanced coolant compatibility upgrade — compatible with liquid metal coolants (sodium-potassium alloy) or high-pressure gas coolants (helium). Higher power density and thermal efficiency. Accepts higher-enrichment fuel for extended operation between refueling cycles. Requires advanced nuclear fabrication infrastructure from Phase 3+  <br><br>  T1 is a *prototype fission reactor*: manual control, no automatic safety systems, limited burn-up before refueling. High operator attention requirement makes it impractical as a primary power source. Best used as an experimental test facility or supplementary power while Phase 2 capabilities are still developing. T2 adds *real nuclear safety infrastructure*: zirconium cladding (neutron-transparent fuel containment), hafnium control rods (automatic neutron absorption), beryllium reflector (improved fuel efficiency). This is the tier where fission becomes a legitimate power option — no longer experimental but requiring monitoring and manual intervention. T3 adds *full automation*: automated safety shutdown, continuous instrumentation, and real-time control rod adjustment make this a true industrial power plant with zero operator attention required for normal operation. The transition from "we built a reactor" to "we have nuclear power." T4 enables *advanced coolants* that significantly increase thermal efficiency (~45% vs ~30% for water-cooled), allowing the same fuel input to produce more electricity while reducing cooling water demand |
| **Hydroelectric Dam Generator** | Phase 3 | Single-tier: reinforced concrete structure (cement from calcite/limestone) + steel turbine housing + copper generator winding. Location-dependent (near rivers/large bodies of water). Tier = dam height/capacity, turbine efficiency within single design range. | No tier progression — *specialist* location-dependent facility with one structural design |
| **Concentrated Solar Power Tower + Thermal Storage** | Phase 3 | Single-tier: steel tower structure + niobium-microalloyed receiver coating (high-temperature solar absorption) + molten salt thermal storage tanks (stainless steel, PTFE-lined). Mirrors focus sunlight onto receiver tower; heat stored in molten salt for night/power. Alternative to PV: solar→thermal→steam cycle with built-in thermal storage buffer. | No tier progression — *specialist* CSP facility with one design per site geometry |
| **Fusion Tokamak Reactor** | Phase 4+ | Single-tier (ultimate power milestone item): ~60 Nb₃Sn magnet coil spools, ~80 tungsten armor tiles, lithium-beryllium breeder panel frames, cryogenic insulation layers. See [Power System](power-system.md) and [Endgame Vision](endgame-vision.md); exact assembly recipe remains open. | No tier progression — this is a *single-tier endgame megastructure* requiring the full industrial ecosystem to build. It is not meant to have multiple tiers; it IS the highest tier |
| **Hawking Radiation Engine** | Phase 4 option | The accepted concept is a confined event horizon with Hawking-radiation heat conversion. Power output, assembly scope, and research gate remain open. The source's `all Phase 4 generators + Core L3` gate conflicts with the current basic-Core proposal in [Research and Progression](research-progression.md); neither gate is finalized, and at least one alternative Phase 3/4 route is required. | No tier progression in the source proposal; exact role and progression remain open |
| **Advanced Wind Array / Offshore Wind Farm** | Phase 4 | Single-tier: niobium-microalloyed tower structure (corrosion-resistant offshore) + titanium blade mounting hubs + semiconductor-grade wind direction tracking system. High-capacity turbines for consistent large-scale power generation. Tier = turbine capacity per unit, array management sophistication within single design range. | No tier progression — *specialist* offshore installation with one structural design |
| **Tidal/Wave Generator** | Phase 4 | Single-tier: titanium-alloy marine-grade construction (corrosion-resistant for seawater service) + niobium-microalloyed turbine housing. Harness ocean/tidal energy in coastal locations. Tier = blade/float size, conversion efficiency within single design range. Location-dependent (coastal biome only). Steady but location-locked. | No tier progression — *specialist* marine installation with one structural design |

### Power Poles and Local Distribution (Core Mod — Tiered Builds)

The accepted direction retains the vanilla electrical network and adds compatible tiered power-pole buildables. The user cited tiered-pole approaches in Space Exploration and Bob's/Angel's as inspiration; exact features are not yet verified or selected. Pole tiers do not imply custom voltage levels, transmission losses, or a replacement grid.

| Constructable Family | Tier/Phase | Scope and Candidate Progression |
|----------------------|------------|----------------------------------|
| Existing vanilla pole grid | Vanilla baseline | Retain the existing network and pole behavior. |
| Tiered power poles | Tier count, phase, and materials TBD | Add compatible pole variants. Coverage area, wire reach, connection limits, construction materials, and whether variants coexist with or replace one another remain to be designed. |


### Power Transmission & Grid Infrastructure — Candidate Extension Scope

> A full custom transmission model remains an optional `power-transmission-override` proposal. The accepted core direction in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) keeps the vanilla grid and adds compatible tiered poles; custom voltage and loss mechanics are not part of that decision. The entries below remain candidate references.

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Steel Transmission Tower + High-Voltage Line | MTier 1–3 (Phases 2–4) | Long-distance bulk power transmission at high voltage | Basic steel tower → reinforced with composite insulators → ultra-high-tension at highest tiers. Conductors: tin-plated copper → pure copper → aluminum/steel composites → gold (endgame, minimal loss) |
| Step-Down Transformer / Substation | MTier 1–3 (Phases 2–3) | Convert high-voltage transmission to industrial-use voltage for factory machines | Iron-core → copper-wound with tap changers → digital monitoring + load balancer at highest tiers |
| Underground Power Cable Trench System | Phase 3+ | Bury power lines to free surface space; reduce exposure loss | Uses same conductor materials (copper/aluminum/composite in concrete conduit). No line-of-sight requirement for routing |
| HVDC Converter Station | Phase 4+ | Convert AC power to high-voltage DC for ultra-long-distance transmission with minimal losses | Optional custom-transmission extension candidate; not a core prerequisite under the accepted vanilla-grid direction. Whether a future custom grid needs it remains open |

### Energy Storage Systems (Core Mod)

> These items **are in scope** for the core mod because they are accumulator-style devices that connect to vanilla pole grids. They do not require any custom transmission infrastructure.

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Capacitor Bank (accumulation) | Phase 1 | Buffer short-term power fluctuations; provides burst power for machine startups | Upgrade path uses battery + circuit components per tier. Same function as vanilla accumulator but with multi-tier build. Tier = storage capacity + discharge rate |
| Battery Storage Unit | Phase 2+ | Longer-duration energy storage for load leveling, backup power during outages | Requires refined copper, processed chemicals (electrolyte); higher capacity and discharge rate per tier. MTier 3 adds smart-cell management via semiconductor monitoring |
| Dead-Battery Capacitor / Fuse Link | Phase 2 | Safety device that intentionally depletes to shut down a fission reactor core before meltdown | **Not reusable** — must be replaced after activation. Critical safety mechanism for fission reactors: provides the last-resort power cutoff when grid fails and active cooling is at risk. No upgrade path; single-tier safety item |
| Flywheel Energy Store | Phase 3+ | Mechanical kinetic energy storage with high round-trip efficiency | Alternative to batteries — no chemical degradation over time. Requires precision manufacturing (semiconductor components at MTier 2+, servo motors from Automation §5). Tier = rotational mass + bearing quality |

### Grid Stabilization Infrastructure — Candidate Extension Scope

> The source proposal places these items in the optional `power-transmission-override` extension; this disposition remains unverified in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md).

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Reactive Power Compensator | Phase 2+ | Maintain voltage stability on AC lines; prevents brownouts when large loads start up | Required for high-capacity industrial clusters (electrochemical cells, EAF) |
| Surge Protector / Lightning Arrester | Phase 1+ | Divert power spikes to ground before they damage grid or equipment | Essential for fission reactor safety at every step-up/down transformer in the reactor's feed path |
| Frequency Regulator | Phase 3+ | Maintain stable AC frequency when load/generation balance shifts rapidly | Required when connecting variable renewables (wind, solar) to main grid |

### Power Generation + Energy Storage Infrastructure Summary — Candidate Core Scope

> The accepted core distribution direction is vanilla-grid-compatible tiered poles. Generator and storage entries remain candidate scope; custom transmission and stabilization remain extension proposals.

| Infrastructure Type | Total Items | Tiered? | Key Capability Tiers |
|---------------------|-------------|---------|----------------------|
| Generators (Phases 1-4 + Endgame) | ~14 types | Yes (varies by type) | Steam engine MTier 1-3; fission reactor MTier 1-4; fusion Tokamak Phase 4 |
| Core power-pole families | Vanilla poles plus tiered variants; count TBD | Yes; exact tiers TBD | Compatible with the vanilla network; pole statistics and material progression remain open |
| Energy Storage Systems | 4 types (capacitor, battery, safety shutdown controller, flywheel) | 3/4 tiered | Capacitor bank MTier; battery storage MTier; flywheel MTier 2+ |
> **Source-proposed extension scope:** Custom transmission towers + lines (3 variants), transformers / substations (1 type, MTier 1-3), grid stabilization devices (3 types), HVDC Converter Station (Phase 4+). These counts and scope labels remain provisional.

## 12. Military Infrastructure

**Candidate direction — see [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md):** The turret roster is not assumed to be vanilla-only. Plasma and railgun turrets are proposed electrical additions to the existing family candidates; their tiering, phase, and core-versus-extension placement remain open. Military products belong in [Military System](military-system.md) and [Intermediate Products](intermediate-products.md).

### A. Turret Systems (Core Candidates — Tiered Builds)

Candidate turret tiers should use distinct structural materials and weapon mechanisms where appropriate, rather than only stat increases. Ammo-driven lines may progress from kinetic through incendiary, explosive, and penetration capabilities; electrical candidates add role-based progression through laser, plasma, and railgun defenses. Exact tiering and phase placement remain open.

| Turret Type | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Gun Turret (Tiered Ammo Support)** (MTier 1–3) | Phases 1–4 | T1: Steel housing + basic copper wiring + iron barrel. Fires kinetic ammo only (lead core, copper jacket, steel case). Rate of fire: moderate. Magazine capacity: small. Simple mechanical loading mechanism — reliable but limited ammunition options. T2: Stainless steel housing upgrade + nickel-alloy trigger mechanism + chrome-molybdenum reinforced barrel. Accepts incendiary ammo (fuel/oxidizer mix + magnesium ignition compound) in addition to kinetic. Rate of fire +30%. Larger magazine capacity. Semi-automatic feeding replaces manual mechanical action. T3: Niobium-microalloyed structural frame + tungsten-carbide barrel lining (erosion-resistant for AP penetrator firing) + niobium-tin targeting computer wiring + tantalum-ceramic trigger assembly | Accepts armor-piercing tungsten-core ammunition. Rate of fire +50% over T1. Maximum magazine capacity. Semiconductor-guided targeting improves first-round accuracy against fast/burrowed targets. This tier is the *industrial capability gate* for military defense — requires steel (Phase 1), stainless steel (Phase 2 chemical infrastructure), tungsten carbide (Phase 3 refining), and electronics (Phase 3 semiconductor) |
| **Laser Turret (Electrical; MTier 1–3)** | Phases 2–4 | T1: Steel housing + basic optics (glass lens elements from silica) + copper power wiring. Low-power beam (~50 kW). Requires semiconductor targeting module at T2+ to operate effectively — below that tier, the laser is more of a precision welder than a weapon. T2: Niobium-microalloyed heat sink frame + electronic-grade polysilicon lens elements (UV-transmitting silicon optics for higher beam intensity) + HfO₂ thermal management panels (heat dissipation for sustained firing). Medium-power beam (~200 kW). Can fire continuously without overheating. Semiconductor targeting module required. T3: Tungsten-carbide optical housing + niobium-microalloyed precision alignment mechanism + advanced thermal interface materials from Phase 3 bridge products | High-power beam (~500 kW). Laser burn-through effective against lightly armored targets. Precision tracking system locks onto fast-moving targets (biters, spitters) at range. This turret's progression mirrors the *cleanroom capability* — you cannot build a T2+ laser without polysilicon optics, which requires semiconductor fabrication |
| **Plasma Turret (Electrical; new candidate)** | TBD | Construction materials, power components, and any consumables remain TBD | Fires a plasma-energy orb with artillery-like delivery and a relatively large splash radius. Substantial power draw proposed for balance; phase, tiers, range, recipe, and power profile remain open |
| **Railgun Turret (Electrical; new candidate)** | TBD | Construction materials, power components, and ammunition/energy model remain TBD | Very-long-range beam/shot damages enemies along its path with small-to-medium splash around the beam, potentially to maximum visible or targetable range. Substantial power draw proposed; phase, tiers, range, recipe, and power profile remain open |
| **Flamethrower Turret / Incendiary Launcher** (MTier 1–3) | Phases 2–3 | T1: Steel body + basic fuel reservoir (copper piping, rubber hoses) + ignition compound chamber. Small payload capacity, short range (~30 m). Simple manual trigger mechanism. Early game incendiary option before chemical infrastructure is established. T2: Stainless steel fuel storage tank (corrosion-resistant for chemically active fuels) + PTFE hose lining (compatible with petrochemical fuels) + precision ignition chamber (nickel-alloy igniter assembly). Larger payload (~100 m³ fuel storage). Effective range extended to ~60 m. Auto-ignition system replaces manual trigger. T3: Niobium-microalloyed pressure vessel body + cryogenic-compatible sealing gaskets (for liquid fuel at low temperatures) + semiconductor-grade flow control valve (adjustable spread pattern via PLC signal) | Larger payload (~250 m³ storage), extended range to ~100 m, adjustable spray cone angle. Can be automated via industrial control network for perimeter defense. This turret's progression mirrors *petrochemical infrastructure* — you need the polymer processing chain (PVC pipes, rubber seals, tank lining materials) to build each successive tier |
| **Rocket Turret (Tiered Ammo Support)** (MTier 1–3) | Phases 3–4 | T1: Steel launcher frame + basic guidance mechanism (simple gyroscope). Fires HE explosive shells only. Limited range (~80 m). Single rocket bay. Mechanical targeting system with manual correction. Early game anti-bunker capability. T2: Stainless steel launcher housing + niobium-microalloyed structural reinforcement for heavier projectile handling + semiconductor-grade target acquisition system. Accepts penetration rockets (enriched uranium/tungsten payload) at T3+. Extended range (~150 m). Dual rocket bays for sustained fire. T3: Niobium-microalloyed pressure-rated launcher + tungsten-carbide recoil dampeners + advanced semiconductor guidance module + HfO₂ thermal management for post-firing cooling | Rocket range extended to ~250 m. Triple rocket bay with automated reload from storage silo. Precision-guided targeting can track fortified encampments across the map. This turret requires the *full nuclear fuel cycle* at T3 — enriched uranium or tungsten penetrator, solid fuel booster, and semiconductor guidance module make it an endgame military capability |


### B. Ammo Products — Manufactured Intermediate Items (Cross-Domain Reference)

*These are non-building products, not machines. This candidate reference is excluded from infrastructure counts; product identity and pathway ownership belong in [Intermediate Products](intermediate-products.md) and [Military System](military-system.md).*

| Product | Tier | Primary Feed Materials | Recipe Input Chain (key intermediates) | Infrastructure Source (infra.md §) |
|---------|------|----------------------|--------------------------------------|-----------------------------------|
| **Kinetic Bullet (T1)** | T1 | Lead core, copper jacket, steel case, gunpowder propellant | Galena → roasted/smeled lead ingot + chalcopyrite flotation → electrolytic Cu + hematite → pig iron → EAF steel + sulfur combustion + charcoal → carbonized biomass/coal coke → ground powder | §4 Smelting, §2 Flotation, §7 Electrochemical, §3 Thermal |
| **Incendiary Bullet (T2a)** | T2a | Fuel/oxidizer mix, magnesium ignition compound, steel casing | Oil refining → hydrocarbon fraction + chlor-alkali NaOH → hydrogenation FT synth glycerol or coconut palm oil + spodumene/carnotite → MgO calcined + sintered igniter pellet | §8 Polymer/Composite, §5 Reactors, §6 Solution Proc. |
| **Explosive HE Shell (T2b)** | T2b | High-explosive core, detonator compound, steel casing | Chlor-alkali → NaOH + H₂ → Haber-Bosch NH₃ + Ostwald chain → concentrated HNO₃ + FT glycerol or coconut palm oil → nitroglycerin precursor + galena lead → lead azide initiator (or cheaper ammonium nitrate alternative) | §5 Reactors, §6 Solution Proc., §8 Polymer/Composite |
| **Armor-Piercing Round (T3)** | T3 | Tungsten core alloy, specialized propellant, copper sabot | Scheelite/Tungstenite → Caustic leach + purification → W powder + pressing/sintering + nitrocellulose/tungstenite + carbonized charcoal/calcined biomass | §5 Reactors, §8 Polymer/Composite, §4 Smelting |
| **Penetration Rocket (T4)** | T4 | Enriched uranium/tungsten payload, solid fuel booster, guidance module | Uraninates → acid leach → purification → enrichment cascade or thorium monazite → Th-cycle fuel + Zr-Cl₄ chlorination → metal reduction → Zr cladding for casing + fission reactor → enriched U/W penetrator core | §10 Nuclear Fuel Fabrication, §6 Solution Proc. |

### C. Military Component Support Machines (Core Mod)

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Ammunition Press / Loading Machine | Phase 1–2 | Combine lead core + copper jacket + steel case + propellant into finished kinetic bullets | Intermediate processing for T1 ammo; tier = throughput speed and precision alignment. Reuses pellet press/briquette machine family from Thermal Processing §3 with tooling swap. |
| Incendiary Compound Mixer / Reactor | Phase 2–3 | Mix fuel/oxidizer compounds with ignition catalyst for incendiary rounds | Reuses general chemical reactor or dedicated small-scale mixer; tier = mixing precision, temperature control. No unique build required — use existing reactor infrastructure from §5. |
| HE Explosive Formulation Tank + Nitration Station | Phase 3 | Synthesize nitric-acid-derived explosives via controlled nitration reactions under pressure/temperature control | Requires pressure-rated vessel + safety controls; tier = pressure rating, temperature control precision, safety interlocks. Uses pressure leach autoclave family from §5 with specialized internals. |
| Precision Detonator Assembly Machine | Phase 3 | Assemble reliable detonation initiation components from explosive, primer, and electrical parts | Combines chemistry (explosive compounds) + electronics (trigger circuits); produces reliable firing mechanisms. Tier = assembly precision + testing reliability. |
| Tungsten Core Forging Press | Phase 4+ | Forge tungsten-carbide penetrator cores under extreme pressure for AP rounds | Requires refractory tooling + hydraulic press at high MTier; intermediate product between raw tungsten and finished AP ammo. Uses pellet press/briquette family from §3 with specialized dies. |

### D. Advanced Weapon Concepts — Previous Extension Proposals

*The plasma and railgun concepts below were previously listed as extension-only. They may overlap with the new electrical turret candidates in section A; retain them for traceability, but do not count them as separate products until their relationship and scope are reconciled. The anti-materiel concept remains an extension candidate.*

| Machine Name | Tier/Phase | Operations | Design Notes | Previous Extension Proposal / Current Scope |
|-------------|-----------|------------|--------------|-------------------|
| Plasma Discharge Emitter | Phase 4+ (previously EXT) | Earlier proposal: release a concentrated plasma burst from magnetic containment; requires superconducting magnetic coils | Possible overlap with the new plasma-orb turret; reconcile burst versus projectile behavior. Substantial power draw is proposed for the new candidate; values remain TBD. | Previously proposed for `difficulty-advanced` or `power-nuclear-waste`; current scope unresolved |
| Railgun / Coilgun Turret | Endgame (previously EXT) | Earlier proposal: accelerate a ferromagnetic projectile using extreme electromagnetic force | Possible overlap with the new beam/line-attack proposal; reconcile projectile versus beam behavior. Massive power draw, superconducting magnets, and a precision capacitor bank remain source proposals, not confirmed requirements. | Previously proposed for `difficulty-extreme` or dedicated `military-endgame`; current scope unresolved |
| Anti-Materiel Rifle / Heavy Cannon | T4 (EXT) | Pierces through fortified structures and heavily armored enemies with AP penetrator + HE dual-compatible ammo | Extended weapon tier for ground combat; requires tungsten refining chain from Phase 3. | `difficulty-advanced` extension candidate |

The prior blanket proposal to avoid new core turret families is retained in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) as unapproved source history; it is not the current user proposal. The source's ~80-machine scope assertion is a candidate estimate, not a normalized count.

### E. Defense Infrastructure Progression

Defense follows the mod's progression philosophy — earned through industrial capability, not just tech tree advancement.

| Stage | Defense type | Driven by | Industrial Gate |
|---|---|---|---|
| Early (Phase 1) | Passive barriers, basic turrets with kinetic ammo | Basic steel, lead, simple chemistry | Hematite mining + sulfur refining → basic gun turret + T1 kinetic ammo |
| Mid (Phase 2–3) | Active defense grids, incendiary/explosive ammo supply | Chemical intermediates, alloy production, precision manufacturing | Petrochemical cracking OR oil refining → incendiary compounds; Ostwald chain → HE explosives |
| Late (Phase 3–4) | Distributed defense network, AP penetrator capability, automated targeting | Semiconductors, tungsten processing, advanced automation | Tungsten refining (scheelite/Tungstenite) → AP rounds; cleanroom → semiconductor guidance modules |
| Endgame (optional) | Strategic deterrence via penetration rockets, advanced weapon extensions | Full nuclear fuel cycle + fusion materials chain | Enriched uranium/tungsten payload + semiconductor guidance module from Tier 4 cleanroom fabrication |

**Note:** Defense automation is not built into the core mod. Defense logistics are handled by vanilla logistics/bots + manual turret aiming. Optional extension packs may add automated targeting integrations as opt-in QOL features (see [technical-architecture.md](technical-architecture.md)).

## 13. Logistics & Material Handling

All logistics infrastructure must be tiered with **different structural and control materials per tier**. The progression mirrors the industrial automation arc: basic steel → electronics-enabled automation → semiconductor-grade precision control. Belt tiers reflect material evolution (rubber → polymer → alloy), while buildings reflect control system evolution (mechanical → electronic → semiconductor).

### Conveyor & Belt Systems (Multi-Tier)

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Basic Transport Belt** (MTier 1–4) | Phases 1–4 | T1: Steel roller frame + basic rubber belt material. Simple mechanical drive. Speed: baseline (1×). Weight capacity: low (~20 kg/item). T2: Chrome-alloy roller housings + reinforced polymer belt (from HDPE processing). Improved wear resistance and flexibility. Speed: 1.5×. Weight capacity: medium (~40 kg/item). Belt material accepts moderate chemical exposure without degradation. T3: Niobium-microalloyed drive motor housing + high-performance polymer belt (fluoropolymer-reinforced). Corrosion-resistant belt surface for use in chemical processing areas where acidic spills are likely. Speed: 2×. Weight capacity: high (~80 kg/item). Can transport heavy Phase 2 intermediates without sagging or deformation. T4: Tungsten-carbide roller bearings + alloy-reinforced composite belt (niobium-microalloyed structural layer + semiconductor motor controller for variable speed control). Maximum throughput configuration with active speed management per segment | Speed: 2.5×. Weight capacity: very high (~120 kg/item). Smart speed control allows individual segments to throttle for downstream balancing without splitters — essential in large factories where belt congestion is the bottleneck. Belt evolution mirrors materials science progression (rubber → polymer → alloy-reinforced), matching design principle that infrastructure tiers reflect build materials, not input quality |
| **High-Speed Conveyor Belt Network** | Phase 3–4 | Single-tier: semiconductor-grade motor controller (packaged ICs × 5 per segment) + niobium-microalloyed drive assembly + high-performance fluoropolymer belt. Advanced belt segments with maximum throughput speed. Requires advanced circuits/semiconductors. Significantly faster than standard belts, supports heavier loads. | No tier progression — this is a *specialist* endgame logistics component that replaces Basic Transport Belt entirely in areas where maximum throughput is required. Material selection matters more than tier count |
| **Adjustable-Speed Belt Splitter / Merger** (MTier 1–3) | Phase 2+ | T1: Steel frame + basic mechanical speed-matching mechanism (manual belt tension adjustment). Splits one input belt into two outputs at equal speed. Two inputs max, one output max. Fixed routing ratio (50/50). T2: Stainless steel housing + nickel-alloy motorized tensioning arms + semiconductor-speed sensor array. Automatic speed matching — can split 1:3 or 3:1 asymmetrically. Four-way splitting available at MTier 2+. Accepts different input/output belt speeds without jamming. T3: Niobium-microalloyed drive assembly + tungsten-carbide tensioning bearings + intelligent load-balancing algorithm | Dynamic routing ratio control (adjustable 10/90 to 90/10). Automatic load balancing across multiple outputs — if one downstream line is full, automatically shifts more throughput to the other output. The tier where belt routing transitions from *static infrastructure* to *adaptive system* |
| **Understacker / Topstacker Belt Jumper** | Phase 1–2 | Single-tier: steel frame + rubber isolation pads (vibration dampening) + basic alignment mechanism. Cross one belt over or under another without item transfer. Basic version from early game, upgraded versions at higher tiers with better speed handling. | No tier progression — this is a *layout tool* with one function per geometry type. Different models exist for different crossing angles, not different tiers |


### Infrastructure Buildings (Tiered)

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Electrified Freight Terminal (Rail Station)** (MTier 1–3) | Phases 2–3 | T1: Steel platform + basic electrified coupling mechanism (copper wiring, iron contacts). Manual load/unload. Basic buffer system — simple spring-mounted platform extension to absorb incoming train momentum. No automation beyond manual switch throwing. T2: Stainless steel platform structure + niobium-microalloyed electromagnetic coupling mechanism + semiconductor-grade demand sensing system (tantalum-capped load cells at each berth position). Automated load/unload triggered by item availability at adjacent storage. AI-demand dispatch available at MTier 3+. T3: Niobium-microalloyed structural frame + tungsten-carbide coupling pins + integrated buffer system with active pneumatic damping (chrome-alloy cylinders, PTFE-sealed pistons) | Full automation of freight handling: train arrives → demand sensors check adjacent storage → automated loading/unloading based on real-time buffer levels → train departs when buffer target is reached. Maximum throughput — can handle the largest trains in the game without manual intervention. The tier where logistics transitions from *player-managed* to *factory-managed* |
| **Logistics Bot Hub** (MTier 1–3) | Phases 2–3 | T1: Steel housing + basic battery storage compartment (lead-acid batteries, copper wiring) + simple circuit controller. Limited storage capacity (~500 items). Fast bot dispatch but short range. Basic item sorting logic (first-come-first-served). T2: Stainless steel housing upgrade + lithium-ion battery bank (lithium compounds + cobalt/manganese cathode compounds) + advanced circuit controller (packaged ICs, tantalum capacitors). Storage capacity ~1500 items. Extended range via higher-power signal transmitter (niobium-tin antenna wiring). Smart item routing based on item type priority. T3: Niobium-microalloyed structural frame + semiconductor-grade AI routing processor + HfO₂-insulated power regulation unit | Storage capacity ~4000 items. Maximum dispatch range — bots reach every facility in the player's factory network. AI-assisted request prioritization reduces bot travel time by ~40% compared to T2 logic. Can manage hundreds of simultaneous requests without queue bottlenecks. This tier is when logistics bots transition from *convenient convenience* to *essential factory backbone* |
| **Construction Bot Bay** (MTier 1–4) | Phases 2–4 | T1: Steel housing + basic battery charger (lead-acid, copper wiring) + simple construction controller. Build radius: small (~30 m). Can only build light items (steel frames, basic machines). Maximum simultaneous constructions: 2. Slow building speed. No heavy item handling capability. T2: Stainless steel housing + niobium-microalloyed structural frame + lithium-ion battery bank + advanced circuit controller. Build radius: medium (~60 m). Can build medium-weight items (EAF, chemical reactors, most Phase 2 machines). Maximum simultaneous constructions: 5. Speed increases ~1.5× over T1. Can handle basic Phase 2 intermediate products in construction. T3: Niobium-microalloyed frame upgrade + semiconductor-grade planning system + HfO₂ insulated power distribution | Build radius: large (~120 m). Can build heavy items (multi-block machines, all cleanroom equipment, nuclear fuel facilities). Maximum simultaneous constructions: 15. Speed ~3× over T1. Advanced item placement logic reduces construction waste from misaligned builds. This tier unlocks the full range of Phase 2–3 machinery for automated construction. T4: Tungsten-carbide reinforced bay structure + niobium-microalloyed advanced planning AI + cryogenic-compatible power storage  <br><br>  Build radius: very large (~200 m). Can build *every* item in the mod including endgame infrastructure (Core assemblies, satellite facilities, Hawking Engine components). Maximum simultaneous constructions: 30. Speed ~5× over T1. Fully autonomous site preparation: can clear terrain, level ground, and begin construction from blueprints without manual input. The tier where construction bots transition from *construction aid* to *full factory builder* |
| **High-Capacity Storage Silo / Tank** | Phase 1+ | Single-tier per material type. Tier = capacity only (not a capability change). T1: Steel silo for solid bulk storage (~5000 items) or stainless steel tank for liquid bulk storage (~200,000 units). T2–T4 increase capacity by ~2× per tier with no new material classes — each tier adds more of the same base materials (more steel plates, more PTFE lining for tanks). | No capability change across tiers — pure scaling. Used for buffering intermediate products between processing stages when individual machine throughput is insufficient. Material selection (steel vs stainless) is chosen once at construction based on stored material type |
| **Belt Sorter / Insert/Remove Station** (MTier 1–3) | Phases 1–2 | T1: Steel frame + basic copper wiring sensor array. Insertion/removal speed: moderate (~4 items/sec per operation). Number of simultaneous operations: 1 (can insert to or remove from one belt at a time). Cannot handle heavy Phase 2 intermediate products. T2: Stainless steel housing + nickel-alloy sensor mechanism + niobium-microalloyed control board. Insertion/removal speed: fast (~8 items/sec per operation). Number of simultaneous operations: 3 (can insert to two belts while removing from one simultaneously). Can handle heavy Phase 2 products without jamming or misalignment. T3: Niobium-microalloyed drive assembly + tungsten-carbide sensor contacts + semiconductor-grade item recognition system | Insertion/removal speed: very fast (~16 items/sec per operation). Number of simultaneous operations: 8 (can manage up to 8 belt connections simultaneously with independent routing logic). Smart item type filtering — can selectively insert/remove based on specific item types within mixed belts. The tier where belt sorting transitions from *manual wire-based* to *intelligent automated routing* |
| **Material Handling Crane (Overhead)** | Phase 3 | Single-tier: niobium-microalloyed structural track (ceiling-mounted rail system) + tungsten-carbide hoist mechanism + semiconductor-grade positioning system. Lifts and moves heavy materials between buildings that cannot connect via belts. Industrial logistics for multi-block machines or large components. Tier = lifting capacity, positioning precision within single design range. | No tier progression — *specialist* heavy-lift machine with one function per lift capacity. Material selection (niobium/tungsten) is critical for structural integrity at rated load |


### Advanced Automation & Robotics

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Automated Guided Vehicle (AGV) Station** | Phase 4+ | Single-tier: semiconductor control board (packaged ICs × 15) + niobium-microalloyed chassis + tungsten-carbide drive wheels + HfO₂-insulated power management. Autonomous vehicle that transports bulk materials between stations on programmed routes. Replaces belt networks for long-distance, non-linear material transport. | No tier progression — *specialist* endgame logistics component with one design per route configuration |
| **Robotic Arm Assembly Cell** | Phase 4+ | Single-tier: niobium-microalloyed structural frame + tungsten-carbide joint bearings + semiconductor-grade servo motors (packaged ICs × 20) + advanced control processor. Programmable multi-axis arm for complex assembly operations not feasible with belts + inserters. Flexible manufacturing; can perform multiple tasks depending on programming/tier. | No tier progression — *specialist* flexible-manufacturing cell with one design per payload capacity |


## 14. Fluid Handling & Transport

All fluid machines are built in networked layouts (pipes laid between machines), so every type needs multi-tier progression with **different build recipes per tier**. Capability changes — not just capacity — drive the tiers.

### Storage Tanks

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Storage Tank / Drum** (MTier 1–3) | Phase 1+ | T1: Steel drum + basic rubber gaskets. T2: Stainless steel vessel + PTFE internal lining (corrosive liquids). T3: Titanium-alloy tank + cryogenic insulation panels (LN₂/liquid gas storage) | T1 stores only inert or mildly corrosive fluids. T2 accepts acids, bases, organic solvents without degradation. T3 handles cryogenic temperatures (<77 K) — enables liquid gas buffer storage |

### Piping & Flow Control

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Pressurized Pipe Network** (MTier 1–3) | Phases 1–3 | T1: Steel pipe segments + rubber O-ring seals. T2: Reinforced steel pipe + chrome-alloy flanges. T3: Stainless steel or PTFE-lined sections (corrosive = PTFE; high-temp = SS 316L) | T1 handles only clean water and non-corrosive fluids. T2 accepts pressurized steam and hot process fluids. T3 adds *fluid compatibility gating*: wrong material choice causes leaks — real engineering decision |
| **Motorized Fluid Pump Station** (MTier 1–3) | Phases 2–3 | T1: Steel pump housing + rubber impeller + copper motor winding. T2: Stainless steel internals + PTFE seals + niobium-microalloyed pressure chamber. T3: Titanium-alloy impeller + HfO₂ corrosion-resistant coating + tantalum-bearing shaft | T1 can only pump horizontal or downward (gravity-assisted). T2 pumps vertically at moderate flow. T3 handles *abrasive slurries* without impeller wear — required before connecting to Tailings Re-Processing Units |
| **Automated Flow Control Valve** (MTier 1–3) | Phase 2+ | T1: Steel valve body + manual adjustment knob (no automation). T2: Stainless steel internals + servo motor actuator + copper-wire feedback loop (PLC controllable). T3: PTFE-lined valve seat + niobium-microalloyed actuator housing + semiconductor-grade position sensor | T1 requires manual adjustment. T2 responds to PLC signals for automated flow regulation. T3 adds *multi-port routing*: can split or merge fluid streams automatically, enabling dynamic reagent distribution |

### Heat Transfer & Compression

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Heat Exchanger Unit** (MTier 1–3) | Phases 2–4 | T1: Copper tube bundle + aluminum fin plates + steel shell. T2: Stainless steel tubes + titanium fin plates (chemical isolation between streams). T3: Titanium tube bundle + niobium-microalloyed shell + HfO₂ thermal interface coating | T1 works for standard water cooling/heating loops. T2 enables *fluid isolation*: two streams never mix even if tube integrity partially fails — critical for separating toxic fluid from clean cooling water. T3 handles full temperature span: cryogenic to 500°C+ |
| **Centrifugal Compressor / Vacuum Pump** (MTier 1–3) | Phase 3 | T1: Steel housing + nickel-alloy impeller blades + copper motor (compression up to 4:1 only). T2: Stainless steel casing + titanium impeller + PTFE-sealed bearings (up to 10:1, reactive gases). T3: Niobium-microalloyed housing + tungsten-carbide bearing surfaces + semiconductor-grade pressure sensors (deep vacuum <0.001 atm, up to 50:1 compression) | T1 cannot create vacuum — only slight pressure boosting. T2 creates *partial vacuum* — required for distillation columns and chemical extraction steps. T3 creates *deep vacuum* — mandatory for semiconductor CVD/PVD processes and controlled atmospheric reactions |

**Tiering principle:** Fluid handling tiers matter because *compatibility is the gating mechanic*. Building PTFE-lined pipe for corrosive acids vs. SS pipe for hot steam are real choices with different material costs.

## 15. Rubber Processing, Polymer Forming & Composite Fabrication

All polymer machines must be tiered with **capability changes per tier** — not just throughput. Polymer processing introduces new materials (plastics, composite resins) that feed both mid-phase factories and endgame construction components.

### Rubber Processing

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Rubber/Kneading Mill** (MTier 1–3) | Phase 2 | T1: Steel rollers + basic electric motor (copper winding, steel bearings). Handles natural rubber only. T2: Chrome-molybdenum roller surface + niobium-microalloyed housing + precision temperature control via nickel-alloy thermocouple. Handles synthetic rubber compounds with curatives. T3: Titanium alloy core rollers + semiconductor-grade PID controller + tantalum-sealed drive motor | T1 only processes raw natural/synthetic rubber feedstock (limited to basic formulations). T2 can mix in *curatives and fillers* — the capability that produces finished elastomer compounds for gaskets, seals, and belt materials. T3 adds *continuous production*: no batch stop/start, steady compound output rate |

### Sheet Extrusion & Composite Layup

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Sheet Extrusion / Rolling Press** (MTier 1–3) | Phases 2–3 | T1: Steel roller housing + basic heating elements. Produces thick sheets only (minimum 10 mm). T2: Chrome-alloy rollers with precision gap control + PTFE release surface. Can produce thin sheets for laminates (sub-1 mm). T3: Niobium-microalloyed thermal chamber + semiconductor temperature sensors + vacuum-assisted layer bonding | T1 produces only thick structural plates. T2 can produce *thin gauge sheets* — required for composite laminate layup. T3 adds *vacuum-assisted lamination*: produces layered composites directly, eliminating the need for a separate bonding step |
| **Fiber Layup Station** (MTier 1–3) | Phase 3+ | T1: Steel frame + basic resin mixing pumps (copper motor, steel housings). Manual fiber placement. T2: Stainless steel mixing tanks with PTFE lining + precision pump controller + ceramic fiber guide rollers. Semi-automated fiber winding. T3: Niobium-microalloyed structural frame + semiconductor-grade tension control system + robotic fiber delivery arm | T1 is *manual* — a single operator places fibers by hand (low speed, low consistency). T2 adds *semi-automated winding*: consistent fiber orientation and tension, but still requires operator oversight. T3 is *fully automated*: programmable layup patterns (cross-hatch, unidirectional, helical), producing aerospace-grade composite panels |

**Tiering principle:** Polymer processing tiers gate on *compound formulation capability*, not speed. You cannot produce functional composites without the right mill tier.

## 16. Waste Processing & Loopback (Circular Economy)

All waste machines are player-built and should be multi-tiered with **capability changes per tier**. This category is intentionally under-featured in early game — it represents late-game circular economy sophistication, not an early concern.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Tailings Re-Processing Unit** (MTier 1–3) | Phases 2–3 | T1: Steel vessel + basic magnetic separator (copper-wire electromagnet). Recovers only strongly magnetic minerals (iron traces — negligible value). T2: Stainless steel processing chamber + chrome-alloy separation media + precision sensor array (silicon-based) for mineral detection. Recovers weakly magnetic and paramagnetic minerals. T3: Niobium-microalloyed pressure vessel + tantalum-bearing grinding media + semiconductor-grade spectral analysis sensor | T1 recovers only iron traces — economically useless but mechanically functional. T2 adds *paramagnetic recovery* — can extract chromium, manganese, cobalt from processed tailings (meaningful secondary income). T3 adds *spectral identification*: automatically classifies remaining mineral content and optimizes separation parameters — the tier where circular economy becomes genuinely profitable |
| **Waste-to-Fuel Converter / Incinerator** (MTier 1–3) | Phase 2+ | T1: Steel vessel + basic refractory lining (alumina/silica brick). Low-temperature combustion only. Produces producer gas with particulate content — requires "gas filter" item per 20 output cycles for clean output. T2: Chrome-molybdenum pressure shell + catalytic converter insert (Pt-group supported on alumina substrate) for complete gasification. High-temperature conversion (>900°C). T3: Niobium-microalloyed reaction chamber + refractory ceramic insulation + automated ash removal system | T1 is *fully auto-running* but requires parallel filter-production to maintain gas quality — the player must invest in infrastructure to keep this machine fed. T2 achieves *complete gasification*: all organic waste fully converts to clean producer gas (CO + H₂) with no residual solids. T3 adds *automated maintenance*: self-cleaning refractory and automated ash removal — essential for continuous operation |
| **Metal Recovery / Solvent Extraction Circuit** | Phase 3 | Single-tier capability: PTFE-lined stainless vessel + activated carbon filter beds (from coal/graphite) + ion-exchange resin + precision pump. Recovers dissolved noble/catalyst metals from process effluent. Gold, silver, platinum-group. | No tier progression — this is a *specialist* facility that should be built once per factory network. Capability scales with the size of activated carbon inventory and flow rate |
| **Sludge Dewatering & Stabilization Unit** (MTier 1–2) | Phases 2–3 | T1: Steel centrifuge bowl + rubber seals + steel frame. Basic mechanical dewatering only. T2: Stainless steel bowl + nickel-alloy drive mechanism + PTFE sealing. High-speed spin with chemical flocculant injection capability | T1 mechanically removes bulk water from sludge — output is still wet paste that must be dried or processed further. T2 adds *chemical stabilization*: injects flocculant to bind fine particles, producing a dry cake suitable for either disposal or fuel conversion |

**Tiering principle:** Waste processing tiers gate on *recovery quality*, not capacity. Early tiers recover only worthless traces; later tiers unlock economically meaningful secondary material recovery.

## 17. Research & Measurement Infrastructure (Phase 2+)

| Machine Name | Tier/Phase | Build Materials (per tier) | Capability Change |
|-------------|-----------|---------------------------|-------------------|
| **Superconductivity Research Lab** | Phase 2 | T1: steel frame + copper coils + rubber seals | Magnetic field strength, sample temperature range |
| | | T2: stainless steel frame + Nb₃Sn wire + tantalum shielding | Higher critical current domain packs; wider temp range |
| **Plasma Confinement Facility** | Phase 2 | T1: steel vessel + copper magnets + ceramic liner | Max plasma temp, confinement time, measurement precision |
| | | T2: nickel-alloy vessel + Nb₃Sn wire coils + beryllia liner | Higher field strengths; more diagnostics channels |
| **Nanofabrication Laboratory** | Phase 2 | T1: steel cleanroom frame + copper HVAC + glass panels | Particle count tolerance, deposition precision, sample size |
| | | T2: stainless structure + HfO₂-coated surfaces + filtered air | Sub-micron feature resolution; multi-layer processing |
| **Isotope Separation & Calibration Lab** | Phase 2 | T1: steel separators + copper sensors + rubber gaskets | Isotope resolution, separation efficiency, sample throughput |
| | | T2: corrosion-resistant alloy + D₂O cooling + tantalum shielding | Higher mass resolution; enriched isotope production |
| **Reaction Dynamics Facility** | Phase 2 | T1: steel pressure chamber + nickel alloys + graphite seals | Max pressure/temperature, catalyst compatibility range |
| | | T2: rhenium-clad internals + high-temp alloys + inert sealing | Higher temp operations; exotic catalyst testing |
| **Quantum States Laboratory** | Phase 2 | T1: steel cryostat + copper thermal links + glass viewport | Base temperature (K range), measurement sensitivity |
| | | T2: multi-layer insulation + superconducting shields + mK temps | Quantum coherence measurement; crystalline structure analysis |
| **Planetary Simulation Core — Thermal Frame** | Phase 3+ | T1: steel frame + copper thermal links | Max simulation resolution, thermal model fidelity |
| | | T2: high-temp alloy frame + tungsten thermal paths | Higher temp range in simulation |
| **Planetary Simulation Core — Computation Cluster** | Phase 3+ | T1: electronic-grade polysilicon PCBs + copper interconnects | Compute nodes, memory bandwidth |
| | | T2: semiconductor-grade silicon + Nb₃Sn optical interconnects | Exponential compute increase; distributed processing |
| **Planetary Simulation Core — Integration Bus** | Phase 3+ | T1: copper bus + ceramic insulators + steel connectors | I/O channels, data throughput to/from facilities |
| | | T2: semiconductor-grade materials + fiber optics | Higher channel count; faster domain dataset transfer |
| **Planetary Simulation Core — Calibration Reference Frame** | Phase 3+ | T1: precision steel frame + copper leveling sensors | Calibration accuracy, reference stability |
| | | T2: invar alloy frame + laser interferometry | Sub-micron calibration; long-term drift compensation |
| **Compute Campus Node** | Phase 3 | T1: polysilicon processors + copper cooling + standard memory | Processing bandwidth, concurrent simulation tasks |
| | | T2: semiconductor-grade chips + Nb₃Sn thermal + expanded RAM | Higher bandwidth; more simultaneous model runs |
| **Memory/Archive Module** | Phase 3 | T1: magnetic storage drums + steel chassis + copper wiring | Storage capacity, read/write speed |
| | | T2: solid-state semiconductor memory + stainless housing | Order-of-magnitude capacity increase; faster retrieval |
| **Regional Observation Facility** | Phase 3 | T1: sensor array (steel/copper) + basic processor + solar power | Sensor types count, range, data quality |
| | | T2: advanced sensors (semiconductor-grade) + PLC control + battery backup | Higher resolution sensing; automated operation |

## 18. Automation & Control Systems

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| **Basic Sensor Array** | Phase 1–2 | T1: steel housing + copper wiring + basic thermocouples | Parameters monitored (temp/pressure/gas), accuracy range, alarm count |
| | | T2: stainless housing + semiconductor sensors + rubber isolation | More parameter types (flow rate, vibration, humidity), ±5% → ±1% accuracy |
| | | T3: titanium housing + multi-sensor fusion + EMI shielding | Subsurface monitoring, predictive maintenance signals |
| **PLC Controller Unit** | Phase 2–4 | T1: steel enclosure + basic microcontroller + relay outputs | Timer-based logic (on/off delays), max I/O channels, scan speed |
| | | T2: aluminum enclosure + PID processor + solid-state relays | Proportional-integral-derivative control, analog input/output expansion |
| | | T3: shielded enclosure + neural-assisted processor + fiber comms | Machine learning optimization, predictive adjustments, networked coordination |
| **Precision Actuator / Servo Motor** | Phase 2–3 | T1: steel housing + copper windings + rubber seals | Torque range, positional accuracy (±5%), duty cycle |
| | | T2: aluminum housing + semiconductor drivers + magnetic bearings | Higher torque density, ±0.1° accuracy, variable speed control |
| **Wired Industrial Control Network** | Phase 2–4 | T1: copper cabling + relay-based switching + steel junction boxes | Wiring capacity (10 stations), latency, error correction type |
| | | T2: fiber optic backbone + digital I/O modules + redundant paths | Higher bandwidth, real-time distributed control, fault tolerance |
| | | T3: semiconductor-processed network + AI routing + self-healing topology | Autonomous reconfiguration, predictive maintenance signaling |
| **AI-Assisted Optimization Module** | Phase 4+ | T1: Core-connected processor + polysilicon PCBs + standard memory | Pattern recognition scope (local vs. global), optimization targets (throughput, energy, waste) |
| | | T2: semiconductor-grade compute + expanded RAM + redundant cores | Multi-objective optimization, cross-factory coordination, autonomous tuning |

## Consolidated Multi-Tier Machine Summary

This table summarizes candidate family coverage and tiering. Counts remain provisional and do not consistently distinguish placeable entities, machine families, support systems, and tier variants; Phase 3 will normalize them.

| Category | Candidate Entries (Provisional) | Tiered? | Key Tiers That Change Capability |
|----------|------------------|---------|---------------------------------|
| Extraction & Mining | 6 | Yes (drill, underground belt, deep bore) | Electric drill MT1–4; prospect scanner gates access to deeper deposits |
| Ore Preparation & Concentration | 13 listed machine entries | Partial (ball mill, magnetic drum, flotation bank) | Ball mill MT2–4 for throughput/media auto-replenishment; magnetic drum tier = field strength |
| Thermal Processing | 7 | Yes (roaster, kiln, sintering, pellet press) | Roaster tier = gas capture efficiency; kiln/sinter tier = temp control precision |
| Smelting & Reduction | 7 | Yes (EAF multi-tier primary) | EAF MT1–4: voltage, electrode auto-feed, power range |
| Chemical Extraction & Reactors | 6 | Partial (pressure leach, general reactor) | Pressure leach tier = pressure rating; reactor tier = material compatibility range + control precision |
| Solution Processing & Separation | 6 | Partial (crystallizer, filter press) | Crystallizer MT1–3: cooling → evaporator → vacuum auto-discharge |
| Electrochemical Processing | 4 | Yes (electrowinning, chlor-alkali) | Electrowinning MT1–3 = electrode area + auto-cathode swapping; membrane cell MT2+ = membrane quality |
| Polymer Chemistry & Primary Processing | ~6 candidate families | Partial (polymerization reactor) | Polymerization: batch → continuous → auto-controlled at high tiers |
| Semiconductor Fabrication | 12 | Yes (crystal grower, CVD/PVD, lithography) | Each step is multi-tier; cleanroom quality and precision scale across all |
| Nuclear Fuel & Component Fabrication | 13 | Partial (coil winder, fuel rod assembly) | Multi-stage lines: each sub-step has tier progression from manual → semi-auto → fully automated |
| Power Generation (core mod) | ~14 generator families | Yes (steam engine primary multi-tier) | Steam engine tiers most impactful for early game; reactors scale linearly with tier power output |
| Core Power Pole Distribution | Vanilla network plus tiered pole variants (count TBD) | Yes; details TBD | Compatible pole progression; custom voltage and transmission losses remain outside the accepted core scope |
| Energy Storage (core mod) | 4 system types | 3/4 tiered | Capacitor bank, battery storage, and flywheel have tier progression; safety shutdown device is single-tier |
| Custom Power Transmission & Grid Stabilization (extension) | Extension reference inventory; count not normalized | Deferred from core | Custom voltage, conductor, transformer, and stabilization candidates remain separate from core poles |
| Military Infrastructure (placeables only) | 6 turret-family candidates (4 source-listed + plasma and railgun) + 5 support-machine entries; two earlier extension concepts may overlap | Partial (ammunition-driven turret tiers; electrical-family tiering TBD; support machines scale throughput) | Candidate turret families vary by ammunition capability or electrical role, range, area/line effect, and power demand; exact tier model remains open |
| Logistics & Material Handling | ~10 types + infrastructure (provisional) | Yes (belts, freight terminal, storage) | Belt speed/weight capacity per tier; freight terminal tiers = automation level |
| Fluid Handling & Transport | 6 types | Partial (pipes, heat exchanger multi-tier) | Pipe network tiers most important for pressure/temperature tolerance across distances |
| Rubber Processing, Polymer Forming & Composite Fabrication | ~6 candidate families | Partial (mill, sheet forming, layup station) | Rubber compounding and composite-forming capability changes |
| Waste Processing & Loopback | 4 types | Partial (tailings unit) | Each scales recovery efficiency with tier |
| Research & Measurement Infrastructure | ~10 facilities; component count not normalized | Partial (Core satellites scale capacity) | Core L2/L3 are upgrades, not tiers per se; satellites tier by processing/storage capacity |
| Automation & Control Systems | 5 types | Yes (PLC multi-tier primary) | PLC MT1–3: timer → PID → neural-assisted optimization |

**Count and ownership notes:** Category 2 has 13 listed entries (6 preparation, 5 density/magnetic separation, and 2 flotation). The five ammunition products in section 12.B are excluded from infrastructure counts. The former power aggregate of 20 (14 generators plus 6 transmission entries) mixed core and extension scope; the transmission count remains provisional and is not a core-mod total.

## Design Gate

A machine or variant should be approved only when its operation, input/output contract, progression role, and downstream product use are clear. A new machine family should correspond to a real process capability or a strong gameplay distinction, not simply a desire to give every reaction its own building. Tier progression for any machine type must pass this gate at each level — not all tiers need to be unique builds; some can be simple throughput upgrades if the capability change is meaningful.

## Open Design Decisions

- Which operations reuse vanilla machines, and which require new or modified families?
- Should chemical reactors be one configurable family or a small number of process-specific families?
- Which routes need multiblock or high-throughput equipment, and which should scale with ordinary machines?
- Which routes require catalyst slots, pressure or temperature constraints, or maintenance? Route-specific requirements belong with the mineral and chemical process owners.
- What is the smallest useful PLC and sensor/actuator set, and which controls remain optional? Basic process balance must not depend on custom code.
- What must the handbook and machine UI expose for recipe eligibility, inputs, outputs, coproducts, catalysts, and research requirements? What baseline diagnostics cover status, throughput, power draw, and blocked outputs?
- The archived route-to-machine matrix was empty. Populate exact assignments only after the relevant product and process routes are approved.

---

## Construction Materials Index — Per-Category Material Requirements

> **Purpose:** This section maps what specific materials every infrastructure category needs to build its machines, tiers, and support items. It demonstrates that infrastructure demands touch nearly the entire mineral/chemical roster — not just the endgame assembly chain. Every material in the catalog should earn its place through either: (a) an endgame assembly dependency, or (b) an infrastructure requirement from the tables below.
>
> **Format:** Each table lists which refined materials, alloys, chemicals, and intermediates are consumed per-tier or as unique components. Quantities are relative ("×" = multiple units), not finalized.

### Category 1 — Extraction & Mining (~6 buildings)

| Building | MTier 1 / T1 Materials | MTier 2+ / T2+ Materials | Late-Game Tier Materials |
|---|---|---|---|
| Electric Mining Drill | Steel plates (structural frame), copper wire (motors/wiring), iron gears, basic rubber (belts/seals) | Stainless steel housing (corrosion resistance), niobium-microalloyed steel plate (load-bearing frame at MTier 3+), tantalum capacitors (control circuitry) | Titanium-alloy reinforced drill head, tungsten-carbide cutting teeth, ceramic bearing inserts |
| Underground Mining Belt | Steel pipe + iron plates (belt mechanism), basic rubber | Stainless steel (corrosive environments), plastic stacks | — |
| Deep Borehole Drill | Steel frame, copper motor winding | Tungsten-reinforced drilling bit, high-strength alloy housing | Vacuum-sealed drill head components (cryogenic insulation) |
| Open-Pit Excavator | Massive steel frame (~50× steel plates), hydraulic piston assemblies (stainless steel cylinders) | Niobium-microalloyed structural plate (higher load capacity), advanced sealing gaskets (FKM/cryogenic rubber) | — |

**Materials consumed:** Steel, stainless steel, niobium microalloy, copper, tungsten carbide, titanium alloy, tantalum capacitors, basic plastics, FKM rubber. ~9 materials from the catalog.

### Category 2 — Ore Preparation & Concentration (~13 listed machine entries)

| Building | Materials per Tier | Notes |
|---|---|---|
| Jaw Crusher (MTier 1–3) | T1: steel plates + iron shaft + basic bearings. T2: tungsten-carbide jaw plates. T3: refractory steel housing + ceramic bearing upgrades | Tungsten only enters at MTier 2+ via carbide teeth |
| Ball/Rod Mill (MTier 2–4) | T1: steel cylinder lining + cast iron grinding media auto-replenish. T2: tungsten-carbide liner inserts. T3: niobium-microalloyed pressure vessel + ceramic seals. T4: titanium-alloy rotating assembly with automatic media feed | MTier 4 is the only tier that introduces a completely different material class (Ti alloy for light-weight high-speed) |
| Magnetic Drum Separator (MTier 1–3) | T1: basic electromagnet + steel housing. T2: superconducting magnet winding (NbTi wire, limited early phase). T3: cryogenic cooling jacket + HfO₂ dielectric insulation | **First consumer of NbTi wire beyond endgame — bridges Phase 2 infrastructure to bridge materials** |
| Flotation Cells (Rougher/Cleaner) | Rubber impeller/rotor, polyurethane liner plates, steel vessel frame, PVC pipe for reagent feed | Primarily polymer + basic metal consumption |
| Spiral Concentrator / Jigging Machine | Steel frame, chrome-plated separation surfaces | Chrome from chromite — early infrastructure link to alloy steelmaking |
| Electrostatic Separator (Phase 3) | HfO₂ high-voltage insulator panels, precision ceramic feedthroughs, mu-metal shielding plates | Uses hafnium-oxide dielectric and niobium-tin wiring |

**Materials consumed:** Steel grades (structural, tungsten-carbide, refractory), Niobium-tin wire (early consumer!), chrome alloy, HfO₂ dielectric, tantalum capacitors. ~8 materials. **Key insight: magnetic drum separator is the first infrastructure item consuming superconducting material, even before endgame.**

### Category 3 — Thermal Processing (~7 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| Roaster (MTier 1–3) | T1: basic steel refractory + chrome-alloy hearth. T2: nickel-alloy hot gas ducts (corrosion resistant). T3: high-grade refractory steel + catalytic converter insert for off-gas treatment | Nickel from pentlandite — early alloy connection to military phase |
| Rotary Kiln (MTier 2–3) | Steel shell, chrome-molybdenum refractory lining, graphite electrode support frame | Molybdenum from scheelite/pentlandite traces |
| Sintering Machine | High-temp steel mesh, refractory brick (aluminum oxide + silica composite), cooling water jacket (copper tubing) | Aluminum oxide ceramics and copper heat transfer |
| Pellet Press / Briquette Machine | Tungsten-carbide dies at MTier 3+ | First infrastructure link to tungsten tooling |

**Materials consumed:** Steel, nickel alloy, chrome-molybdenum alloy, aluminum oxide ceramics, copper tubing, tungsten carbide. ~6 materials. **Petroleum coke and coal serve as fuels, not construction materials.**

### Category 4 — Smelting & Reduction (~7 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| EAF (MTier 1–4) | T1: basic steel vessel + graphite electrodes. T2: nickel-alloy electrode holders. T3: niobium-microalloyed pressure vessel + refractory brick lining (alumina/silica composite). T4: vacuum-induction capability (requires HfO₂ insulation + tungsten-heated coils) | Each tier adds a new material class — this is the most tier-rich machine in the catalog |
| Blast Furnace (MTier 1–3) | Steel shell, chrome-alloy hearth, refractory brick (alumina), silica lining | Chrome from chromite, alumina from bauxite |
| Converter (BOF/LD) | Nickel-chrome alloy refractory lining, graphite nozzle inserts | Links to steelmaking (chromium + nickel consumption) |
| Induction Melting Furnace (Phase 3+) | HfO₂ crucible liner, tungsten heating element, niobium-microalloyed pressure chamber (refractory-lined electromagnetic induction vessel) | **Another early bridge-material consumer** — produces high-purity alloys requiring precise electromagnetic stirring and refractory progression. 'Vacuum' capability removed: Factorio has no ambient-pressure mechanic. |

**Materials consumed:** Steel grades, nickel alloy, chrome alloy, graphite, alumina ceramics, HfO₂ dielectric, tungsten carbide, niobium microalloy. ~8 materials. **VIM furnace is the first dedicated bridge-material consumer in core industry.**

### Category 5 — Chemical Extraction & Reactors (~6 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| Pressure Leach Autoclave (MTier 1–3) | T1: basic steel + rubber lining (chemical resistant). T2: stainless steel 316L vessel (chloride-resistant grade) + PTFE gaskets. T3: niobium-microalloyed pressure shell + tantalum-clad internals | **Stainless steel is a major infrastructure consumer — every high-pressure chemical machine needs it at MTier 2+** |
| General-Purpose Chemical Reactor | Carbon steel vessel, glass-lined interior (silica coating), rubber/PTFE seals | Glass lining consumes silica and flux materials |
| Fluidized-Bed Reactor (MTier 2–3) | High-temp steel shell, refractory brick (alumina/silica), ceramic distributor plate | Alumina ceramics from bauxite refining |

**Materials consumed:** Steel grades, stainless steel, PTFE plastics, tantalum cladding, alumina ceramics. ~5 materials. **Stainless steel is heavily used here — one of the top infrastructure consumers.**

### Category 6 — Solution Processing & Separation (~6 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| Solvent Extraction Column | Fiberglass reinforcement layers, PTFE internal lining, stainless steel shell | Polymer + chemical-resistant metal combo |
| Ion Exchange Unit | Resin media (organic polymer), stainless vessel, silica support bed | Silica from quartz — direct mineral link to infrastructure |
| Centrifuge / Decanter | High-strength steel rotor, tantalum bearings (corrosion-resistant), precision motor (copper winding) | **First infrastructure use of tantalum beyond electronics** |

**Materials consumed:** Fiberglass, PTFE, stainless steel, silica, tantalum. ~5 materials.

### Category 7 — Electrochemical Processing (~4 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| Electrowinning Cell (MTier 1–3) | Lead-acid alloy anodes, copper cathodes, PTFE separator sheets, stainless steel frame | **Lead from galena — early infrastructure link to mining** |
| Chlor-Alkali Membrane Cell (MTier 2–4) | T2: titanium anode + polymer membrane. T3: niobium-tin shielding wire. T4: HfO₂ dielectric upgrade kit | Nb₃Sn wire enters here as shielding material — early bridge consumer again |
| Electrorefiner | Copper anode/cathode assemblies, nickel-plated tanks | Links back to refining output |

**Materials consumed:** Lead alloy, copper, PTFE, stainless steel, Nb₃Sn wire, HfO₂ dielectric. ~6 materials. **Nb₃Sn is a recurring early bridge consumer across multiple categories.**

### Category 8 — Polymer Chemistry & Primary Processing (~6 candidate families)

| Building | Materials per Tier | Notes |
|---|---|---|
| Cracking Furnace (MTier 1–3) | High-temp alloy vessel, nickel-based catalyst bed housing, refractory insulation | Nickel from pentlandite traces |
| Polymerization Reactor | Carbon steel shell, stainless inner liner, PTFE agitator seals | Steel + stainless combo |
| Injection Molding Press | Chrome-molybdenum barrel, hardened steel mold inserts, tungsten-carbide guide pins | **Another tungsten link: tooling durability** |

**Materials consumed:** Nickel alloy, chrome-molybdenum alloy, PTFE plastics. ~3 materials. **Primarily polymer consumption — infrastructure needs the chemicals it processes.**

### Category 9 — Semiconductor Fabrication Chain (~12 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Czochralski Crystal Grower | High-purity graphite crucible (from purified graphite), alumina/silica thermal insulation, NbTi temperature control wiring | Phase 3 |
| Wafer Saw | Diamond blade segments, silicon carbide guide rails | Phase 3 |
| CVD/PVD Chamber | Niobium-microalloyed wall panels (corrosion resistance to process gases), HfO₂ dielectric windows, tantalum target material for sputtering | Phase 3–4 |
| Photolithography Stepper | Electronic-grade polysilicon lens elements (silicon optics for UV transmission), precision ceramic stages (alumina), Nb₃Sn superconducting motor windings for vibration isolation | Phase 4+ |
| Cleanroom Enclosure | HfO₂ particulate filtration panels, fluoropolymer duct lining, niobium-microalloyed structural frame | Phase 3 |
| Packaging Line | Copper lead frames (from refined copper), gold bonding wire (from native gold processing), plastic/molded ceramic packages | Phase 4 |

**Materials consumed:** Graphite (purified), alumina ceramics, NbTi/Nb₃Sn wiring, HfO₂ dielectric, niobium microalloy, tantalum, electronic-grade polysilicon, gold, copper. ~9 materials. **Semiconductor chain itself is a massive material sink — most of the Phase 2 bridge products are consumed here directly.**

### Category 10 — Nuclear Fuel & Component Fabrication (~13 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Uranium Conversion Line | Stainless steel vessels (corrosion-resistant to UF₆), PTFE gaskets/linings, graphite crucibles | Phase 2–3 |
| Cladding Tube Mill | Zirconium ingot stock, hafnium-segmented cutting tools (Hf is the co-product — clever: the tool consumes the element you're separating from) | Phase 3 |
| Fuel Rod Assembly Line | Stainless steel fixtures, helium sealing components (cryogenic-compatible rubber) | Phase 3–4 |
| Superconducting Coil Winder | NbTi/Nb₃Sn wire (direct consumption), HfO₂ insulation layers, aluminum formers | Phase 3–4 |
| Precision Optics Station | Electronic-grade polysilicon substrate blanks (for optical test equipment) | Phase 4 |
| Tungsten Armor Tile Molder | Tungsten powder + rhenium additive (0.5% Re improves W ductility at high temp), graphite mold inserts | Phase 4+ |

**Materials consumed:** Stainless steel, zirconium, hafnium, Nb₃Sn wire, HfO₂ dielectric, polysilicon, tungsten, rhenium, graphite. ~9 materials. **Fusion infrastructure is a direct consumer of bridge products + tungsten.**

### Category 11 — Power and Distribution Infrastructure

| Generator / Constructable Type | T1 Materials | Mid-Phase Materials | Late-Phase Materials |
|---|---|---|---|
| Enhanced Steam Engine (MTier 1–3) | Steel vessel, copper heating coils, basic seals | Refractory steel upgrades, nickel-alloy pressure valves | — |
| Solar Panel Array (MTier 1–3) | Steel frame, glass panels (silica + soda-ash flux), aluminum mounting brackets | High-purity silicon cells (metallurgical Si → refined), tantalum capacitor regulators at MTier 3 | Multi-junction semiconductor stack (GaAs from gallium + arsenic — precious metal link!) |
| Wind Turbine (enhanced) | Steel tower, copper generator winding, basic bearings | Niobium-microalloyed structural plate for larger rotor blades | Titanium-alloy lightweight hub assembly |
| Fission Reactor (MTier 1–4) | T1: steel pressure vessel + graphite moderator blocks. T2: zirconium-clad fuel channels, hafnium control rod segments. T3: stainless steel primary coolant loop, beryllium neutron multiplier reflector. T4: niobium-microalloyed reactor core basket + tungsten-reinforced steam generator tubes | **The single largest infrastructure consumer across nuclear phase** — uses zirconium, hafnium, graphite, boron carbide, stainless steel, niobium alloy, tungsten   | N/A |
| Fusion Tokamak (Phase 4) | Nb₃Sn magnet coils (dominant material), tungsten armor tiles, lithium-beryllium breeder panel frames, cryogenic insulation layers | **Massive bridge-product consumer**: ~60 Nb₃Sn spools, ~80 W armor plates per tokamak   | N/A |
| Hawking Engine (Phase 4 option) | All Phase 4 materials + Core integration bus connection | See [Power System](power-system.md) and [Endgame Vision](endgame-vision.md); exact Core integration and research gate remain open | N/A |
| Tiered power poles (core) | Materials and tier details TBD | TBD | TBD |

**Materials consumed:** Steel grades, copper, aluminum, silicon, tantalum, niobium alloy, zirconium, hafnium, boron carbide, beryllium, tungsten, Nb₃Sn wire, lithium compounds. ~13 generator materials; tiered-pole material demand remains to be established. **Fission reactor alone is one of the heaviest infrastructure sinks.**

### Category 12 — Military Infrastructure (placeable defense and support systems)

| Turret/Machine | Key Materials | Phase |
|---|---|---|
| Gun Turret tiers | Steel (structural), copper wiring, lead (early), nickel alloy (MTier 3+ trigger mechanism) | Phases 1–4 |
| Laser Turret | Semiconductors (targeting module), precision optics (polysilicon lens), HfO₂ thermal management panels | Phase 2–4 |
| Flamethrower Turret | Steel body, PTFE hose lining, rubber seals, fuel storage tank (stainless steel) | Phase 2–3 |
| Rocket Turret | Tungsten-carbide penetrator housing, enriched uranium guidance modules, explosive compound tanks | Phase 3–4 |
| Ammunition Press / Loading Machine | Steel frame, tungsten-carbide die inserts, copper electrical contacts, lead feedstock | Phase 1–2 |
| HE Formulation Tank | Stainless steel vessel (nitric acid resistant), PTFE seals, glass lining (silica) | Phase 3+ |

**Materials consumed:** Steel grades, copper, tungsten carbide, HfO₂ dielectric, polysilicon optics, PTFE plastics, stainless steel. ~7 materials.

### Category 13 — Logistics & Material Handling (~10 buildings + infrastructure)

| Building | Key Materials per Tier | Phase |
|---|---|---|
| High-Speed Conveyor Belt (Phase 3+) | Reinforced polymer belt (from HDPE/plastic processing), steel rollers, tantalum capacitor motor controller | Phase 3 |
| Electrified Freight Terminal | Steel frame, semiconductor control board, NbTi power regulation wiring, cryogenic-compatible seals | Phase 2–3 |
| Logistics/Construction Bot Hub | Steel housing, battery storage units (lithium/cobalt), advanced circuit controllers, niobium-microalloyed structural upgrades at MTier 4 | Phases 2–3; MTier 4 uses Ti alloy frame |
| AGV Station / Robotic Arm Cell | Packaged ICs (~10 per cell), superconducting cable connections, precision servo motors (copper + tantalum bearings) | Phase 4+ |

**Materials consumed:** Steel, HDPE plastic, tantalum capacitors, NbTi wiring, lithium compounds, cobalt, niobium microalloy, packaged ICs. ~8 materials. **Logistics at high tiers pulls from semiconductor and battery supply chains.**

### Category 14 — Fluid Handling & Transport (~6 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Pressurized Pipe (MTier 1–3) | T1: basic steel/plastic. T2: reinforced steel + rubber gaskets. T3: stainless steel (chemical transport) or PTFE-lined (corrosive fluids) | Phases 1–4 |
| Heat Exchanger Unit | Copper tubes, aluminum fins (MTier 1+), titanium heat exchanger plates at MTier 3+ (for seawater/brine cooling) | Phase 2+ |
| Centrifugal Compressor | High-strength steel housing, nickel-alloy impeller blades, PTFE seals | Phase 3 |

**Materials consumed:** Steel grades, copper, aluminum, titanium, nickel alloy, PTFE. ~6 materials. **Titanium enters via heat exchangers for corrosive brine/cooling — a natural industrial application.**

### Category 15 — Rubber Processing, Polymer Forming & Composite Fabrication (~6 candidate families)

| Building | Key Materials | Phase |
|---|---|---|
| Rubber Mill | Steel rollers, rubber feedstock (circular: processes the same polymer it needs for construction), electric motor (copper) | Phase 2 |
| Fiber Layup Station | Fiberglass winding equipment (ceramic guides), precision resin mixing pumps (PTFE-lined stainless) | Phase 3+ |

**Materials consumed:** Steel, rubber, ceramic guides, PTFE. ~4 materials. **Primarily polymer + steel consumption.**

### Category 16 — Waste Processing & Loopback (~4 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Tailings Re-Processing Unit | Stainless steel processing vessel, ceramic centrifuge bowls, precision sensor elements (silicon-based) | Phase 2–3 |
| Metal Recovery Circuit | Solvent extraction columns (PTFE-lined stainless), activated carbon filter beds (from coal/graphite), ion-exchange resin | Phase 3+ |

**Materials consumed:** Stainless steel, ceramics, silicon sensors, PTFE, activated carbon. ~5 materials. **Activates the "every output should have a use" principle — precious metal recovery from process effluent.**

### Category 17 — Research & Measurement Infrastructure (~10 facilities)

| Building | Key Materials | Phase |
|---|---|---|
| Domain Labs (×6) | Each lab needs research-facility prerequisite materials (detailed in intermediate-products.md and endgame-vision.md; exact count remains open) | Phase 2 |
| Planetary Simulation Core | See endgame-vision.md — Thermal Frame, Computation Cluster, Integration Bus, Calibration Frame | Phase 3 |
| Satellite facilities (compute/memory/observation) | Packaged ICs (dominant), Nb₃Sn cable, thermal interface materials, HfO₂ panels | Phase 3 |

**Materials consumed:** Research-facility prerequisite materials (count unresolved), packaged ICs, Nb₃Sn wire, and HfO₂ dielectric. Approximately 10 candidate materials from research/endgame construction alone.

### Provisional Endgame Assembly and Facility Pathways

These are candidate construction-demand hypotheses, not approved recipes. They were moved from [Intermediate Products](intermediate-products.md) because the outputs are endgame assemblies or facilities; their classification and material demand remain subject to infrastructure alignment.

| Candidate output | Provisional pathway | Intended role |
|---|---|---|
| Processor cluster / compute rack assembly (item/entity form unresolved) | Packaged ICs + boards + cooling and power components -> compute rack | Regional computation |
| Supercomputer facility | Compute racks + high-capacity power/cooling + network equipment -> facility | Large-scale simulation |
| Simulation cluster node | Supercomputer facility + synchronization and precision links -> network node | Distributed simulation |
| Planetary research center | Regional cluster nodes + precision optics + research infrastructure -> center | Endgame objective network |

Former Phase A2 component quantities, satellite recipes, and Hawking Engine subcomponents are preserved as unapproved proposals in [ADR-0009](adrs/ADR-0009-endgame-assembly-proposals.md).

### Category 18 — Automation & Control Systems (~5 buildings)

| Building | Key Materials per Tier | Phase |
|---|---|---|
| PLC Controller (MTier 1–3) | T1: basic copper wiring + silicon chip controllers. T2: niobium-microalloyed shielding + tantalum capacitors. T3: packaged ICs + semiconductor-grade interconnects | Phases 2–4 |
| Precision Actuator/Servo Motor | Copper winding, tantalum bearings, precision steel gears (tool-steel from tungsten/vanadium additions) | Phase 2–3 |
| Industrial Control Network | Fiber optic cable (silica glass core), ceramic connector housings, niobium-tin signal shielding at MTier 3+ | Phases 2–4 |

**Materials consumed:** Copper, silicon chips, niobium microalloy, tantalum, tool steel, silica glass. ~6 materials. **Tantalum bearings are the subtle link — precision motors in automated plants need corrosion/erosion resistance.**

---

## Materials Consumption Summary by Infrastructure Category

This table shows which material groups each category draws from. It answers: **"Which of our ~50 refined materials actually get used?"**

| Material Group | Categories That Consume It | Total Categories Affected |
|---|---|---|
| **Steel grades** (structural, refractory) | 1,2,3,4,5,7,8,9,10,11,12,13,14,15,16,17,18 | **17/18** — nearly universal |
| **Stainless steel** | 1,4,5,6,7,9,10,12,16 | **9** — major infrastructure consumer |
| **Copper** (refined) | 1,4,9,10,11,12,14,18 | **8** — motors, wiring, heat transfer |
| **Niobium microalloy** | 1,3,5,7,9,11,13,18 | **8** — high-strength structural + EMI shielding |
| **Tungsten carbide** | 2,3,4,12,14 | **5** — tooling wear resistance |
| **Titanium alloy** | 1,9,11,14,16 | **5** — lightweight high-strength + corrosive environments |
| **HfO₂ dielectric** | 2,4,7,9,10,12 | **6** — insulation/dielectric across infrastructure |
| **Nb₃Sn wire** (bridge product) | 2,5,7,9,11,17 | **6** — superconducting applications beyond endgame |
| **Electronic-grade polysilicon** (bridge product) | 9,10,11,12 | **4** — optics, sensors, semiconductor chain |
| **Tantalum** (capacitors + bearings) | 1,5,6,7,8,11,13,18 | **8** — corrosion-resistant electronics + precision motors |
| **PTFE/plastics** (chemical resistance) | 5,6,7,8,9,10,12,14,15,16 | **10** — one of the widest-use categories |
| **Nickel alloy** | 3,4,8,10,11,14 | **6** — corrosion/heat resistance |
| **Chrome/molybdenum alloys** | 2,3,8,9,11 | **5** — tooling + heat-resistant structural |
| **Zirconium** | 10,11 | **2** — nuclear-specific but high-volume per unit |
| **Hafnium** | 4,10,11 | **3** — neutron absorber, co-product of zirconium |
| **Graphite/purified carbon** | 4,5,10,11,16 | **5** — electrodes, moderators, refractory |
| **Boron carbide** | 10,11 | **2** — neutron absorber (nuclear-specific) |
| **Lithium compounds** | 11,13 | **2** — energy storage + fusion breeder |
| **Lead alloy** | 7,12 | **2** — electrochemical anodes + ammunition |
| **Gold** (pure) | 9,10,11 | **3** — semiconductor bonding wire, precision contacts |
| **Aluminum alloys** | 11,14 | **2** — heat exchangers, lightweight structural |
| **Beryllium** | 11 | **1** — neutron reflector (nuclear-specific) |
| **Rhenium** | 10 | **1** — tungsten ductility additive (fusion armor) |
| **Silicon** (metallurgical grade) | 9,11 | **2** — solar cells, semiconductor foundation |

---

## Analysis: Materials Coverage

**Total materials consumed across all infrastructure:** approximately 38 of the ~50 refined-material candidates currently have a proposed or verified infrastructure consumer. The remaining ~12 includes open placements and candidate uses whose source/process needs validation; this approximate count must be reconciled during Phase 3. They may:
- Only apply to extension mods (e.g., advanced battery chemistries beyond Li-ion)
- Serve as bridge/recoverable trace materials with no direct infrastructure use (but still have research or chemical consumer value)
- Need a creative placement before final approval

**Key findings:**

1. **Endgame assemblies alone only consume ~15 materials.** Infrastructure demands cover nearly 40 of the ~50 candidates. The gap is bridged by: (a) mid-phase industrial machines that need Phase 2+ capabilities, and (b) advanced automation/logistics/turret tiers.

2. **Nb₃Sn wire is a surprising infrastructure consumer.** It's not just endgame — magnetic drum separators, chlor-alkali shielding, cleanroom motors, and fission reactors all need superconducting wiring at mid-tier. This gives Phase 2 a *purpose beyond just the Core.*

3. **Stainless steel is the single most-used alloy** (9 categories). Every facility handling chemicals, heat, or corrosive fluids needs it. This validates the chromium + nickel pathway from the start.

4. **Tantalum appears in an unexpected range of applications** (8 categories): capacitors for control circuits, bearings for precision motors, shielding for EMI-sensitive equipment, cladding for chemical vessels. This is one material that earns its existence through breadth-of-use rather than a single high-volume endpoint.

5. **Infrastructure creates natural "phase gates":** A player cannot build a Phase 3 semiconductor facility without first producing hafnium-oxide dielectric, niobium microalloy, and tungsten carbide — all mid-phase materials that require specific refining chains. These are real engineering constraints, not artificial tech-tree walls.

---

## Extended Catalog: Pure-Material Infrastructure-Use Validation

The following ~12 candidates have either an open infrastructure placement or a proposed use whose source/process needs validation. This is not a claim that none has a proposed consumer: gallium and germanium already appear in the candidate solar-cell pathway in Category 11. Beryllium is assigned as a fission-reactor reflector in Category 11 and is retained here as a resolved cross-reference, not an open gap.

| Material | Potential Infrastructure Role or Validation Need | Validation Status |
|---|---|---|
| Gallium | Validate the source/refining path for the proposed GaAs solar-cell contacts; a separate thermometer or sensor use remains optional | Medium — candidate solar use appears in Category 11; source path unverified |
| Germanium | Validate the trace-recovery path for the proposed multijunction solar-cell use; wafer testing and fiber-optic doping remain alternatives | Medium — candidate solar use appears in Category 11; source path unverified |
| Selenium / Tellurium | Photovoltaic cell variants (CdTe panels); thermoelectric module junction pairs for Hawking Engine thermal converter | High — already noted for Thermal Gradient Converter |
| Yttrium | Superconducting compound additive (YBCO-type research materials) | Medium — niche but connects to superconductivity lab |
| Cerium / Lanthanum | Photocatalyst components, optical glass polishing compounds | Low-Medium — plausible but may not earn dedicated infrastructure slot |
| Phosphorus / Phosphate compounds | Battery electrolyte additive (LiFePO₄ cathode chemistry option); flame retardant for polymer processing | Medium — phosphate could enable a secondary battery chemistry choice |
| Boron compounds (non-B₄C forms) | Glass/ceramic manufacturing; optical fiber dopant | Medium — borosilicate glass needs boron oxide precursor |
| Magnesium | Light alloy additive (Al-Mg structural plates); Kroll process reagent for titanium reduction | Medium — already used in aluminum alloys + Ti processing |
| Beryllium | Neutron reflector/multiplier for fission reactors | Resolved cross-reference — assigned in Category 11; not an open gap |
| Vanadium | Steel alloy additive (already counted as microalloy); redox flow battery electrolyte option | Medium — redox battery is a creative energy storage path |
| Indium | Transparent conductive film precursor (ITO coating for cleanroom optics) | Low-Medium — niche but real semiconductor application |
| Cadmium | CdTe solar cell variant; neutron-absorbing compound (replaces some boron applications) | Medium — potential extension mod candidate |

These materials are **recoverable from processing residues** (coal → Ge, copper anode slimes → Te/Se, monazite → Ce/La/Y). They don't need dedicated ore deposits — they earn their place through trace-recovery capabilities that the player discovers as they expand their refining sophistication.
