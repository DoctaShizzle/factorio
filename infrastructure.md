# Infrastructure - Infrastructure and Placeable-Entity Catalog

*For: Project Prometheus Factorio Overhaul Mod*  
*Status: Family scope aligned; individual entities, tiers, construction inputs, and recipes remain provisional*

Related documents: [Minerals and Refining](minerals-and-refining.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Power System](power-system.md), [Design Coverage and Product-Tree Plan](plan.md), [Documentation Map](documentation-map.md). Related ADRs: [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md), [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md), [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md), [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md), [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md), [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md), [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md), [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md), [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md), [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md), [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md), [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md), [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md), [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md), [ADR-0036](adrs/ADR-0036-phase-2-minimum-fission-fuel-path.md), [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md), [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md), [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md), [ADR-0041](adrs/ADR-0041-phase-2-direct-use-fission-fuel.md), [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md), [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md), [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md), [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md), [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md), [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md), [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md), [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md), [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md), [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md), [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md), and [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md) for the Phase 2 Core fission-safety boundary.

Related closure ADRs: [ADR-0063](adrs/ADR-0063-select-depleted-uranium-oxide-reuse.md), [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md), [ADR-0065](adrs/ADR-0065-practical-phase-2-fission-readiness.md), [ADR-0066](adrs/ADR-0066-select-phase-2-nuclear-recovery-flows.md), and [ADR-0068](adrs/ADR-0068-continuous-nuclear-waste-disposal.md).

> **Scope**: Factorio 2.1 base game without a required DLC under [ADR-0069](adrs/ADR-0069-target-factorio-2-1-base-game.md). Core reuses useful vanilla prototypes and modifies recipes/progression where appropriate under [ADR-0070](adrs/ADR-0070-overhaul-vanilla-recipes-and-progression.md). The checklist and family register below define scope; detailed entries are capability and construction candidates unless explicitly selected.
>
> **Construction demand**: The high-level demand map distinguishes selected material families, candidate uses, and unresolved sources. Detailed material lists, numeric values, machine upgrades, and phase assignments in the category tables are hypotheses, not accepted bills of materials. Product identities, exact recipes, and research gates follow in Phases 6, 7, and 8.
>
> **Boundary**: Non-building products (vehicles, fuels, weapons/ammo, armor/equipment, modules, and research ingredients) belong in [Intermediate Products](intermediate-products.md). The ammo table in section 12 is a cross-domain candidate reference only and is excluded from infrastructure counts.
>
> **Document ownership**: The former Machine Systems design was subsumed into this catalog. Placeable machine families and capability progression are cataloged here; exact route-to-machine assignments remain deferred except where explicitly selected. The roadmap is [plan.md](plan.md).

---

## Equipment Principles

- A machine family should support multiple related processes where practical.
- Decide tiering per family; an untiered family is valid. Newly required tiers need a meaningful capability change rather than speed or capacity alone under [ADR-0075](adrs/ADR-0075-capability-based-machine-family-tiering.md). Existing vanilla throughput variants are not automatically new Prometheus capability tiers.
- Tier progression must change capability — not just speed. Higher tiers can handle more materials, higher pressures/temperatures, automate sub-tasks, or improve precision.
- Introduce specialized equipment when it changes the player's capability, input/output behavior, or meaningful constraints, not just to add a machine tier.
- Keep recipe eligibility, inputs, outputs, coproducts, catalysts, and required technology visible in the handbook and machine UI.
- Ordinary gas and fluid streams may be deliberately disposed of through separate powered, pollution-producing facilities under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md); do not silently delete them in production recipes. Nuclear-bearing streams retain radioactive fractions for recovery/conditioning; conditioned nuclear solids use continuous powered/material-consuming disposal with slight pollution and no storage cap under ADR-0068. Exact construction, recipes, throughput, and emissions remain open.
- Machine throughput, footprint, power, and capital complexity can differentiate routes, but should not obscure the primary tradeoffs of resource efficiency, pollution, and infrastructure.
- Exact build recipes and quantities for each tier remain provisional; this catalog defines candidate placeables and construction-demand hypotheses, not final build costs.

---

## Factorio-Style Infrastructure-Family Coverage Checklist

This checklist is a family-level 2.1 base-game scope review, not a complete prototype or recipe inventory. **Core candidate** means the capability may be implemented in Core but a separate entity is not selected. Exact unlocks and placing-item/entity splits remain open.

| Family to verify | Factorio-style examples | Current catalog coverage or handoff |
|---|---|---|
| Resource extraction and prospecting | Mining drills, pumpjack, offshore pump, scanners | Core; vanilla drills and pumps retained/modified, with specialist extraction/prospecting candidates in §1. The proposed underground extractor is not an underground transport belt. |
| Ore processing and production | Furnaces, chemical plants, refineries, assemblers, crushers, separators | Core; vanilla furnaces, assemblers, chemical plants, refineries, and centrifuges retained/modified where useful. Specialized capability candidates are in §§2-10 and 15. |
| Power generation and storage | Boilers, engines, turbines, solar, accumulators | Core selected power routes and vanilla boiler/engine/turbine boundaries are in §11; storage and other generator designs remain family-specific candidates. |
| Power distribution | Poles, lines, substations, transformers | Core retains the vanilla grid and adds compatible tiered poles under ADR-0010. Custom voltage/loss transmission and stabilization are extension candidates; ordinary vanilla substations remain Core. |
| Item transport and storage | Belts, underground belts, splitters, inserters, chests, roboports | Core retains/modifies the base-game families; §13 candidates must add distinct capability to justify a separate entity. |
| Rail transport | Rails, signals, stations, locomotives, wagons | Core retains/modifies vanilla rail geometry, signals, stops and wagons; powered rails and electric locomotives replace fueled traction under [ADR-0073](adrs/ADR-0073-core-electric-only-rail.md). Optional demand dispatch is Core under [ADR-0074](adrs/ADR-0074-core-demand-based-train-dispatch.md). Rolling-stock items belong in [Intermediate Products](intermediate-products.md). |
| Fluid transport and storage | Pipes, underground pipes, pumps, tanks, valves | Core retains/modifies vanilla pipes, pumps and tanks; extra valves and specialized handling in §14 are candidates. |
| Defense and military placeables | Gun, laser, flamethrower and artillery turrets; walls, gates, mines | Core retains/modifies the base-game families and adds plasma and railgun turrets under [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md). A rocket turret is not selected; Space Age is not required. |
| Factory support and alerts | Beacons, radars, lamps, programmable speakers, roboports | Core retains/modifies the base-game families. Separate repair or charging stations are candidates, not assumed extra entities; roboport charging is the baseline. |
| Research, observation, and endgame facilities | Labs, launch silo, domain labs, Core facilities | Core retains/modifies vanilla labs and launch capability; the six domain facilities, first-Core gate, and selected Array are in §17. Later satellite structures and exact entity splits remain candidates; a second victory is not selected. |
| Automation, control, and sensing | Circuit network, combinators, power switches, PLCs, alarms | Core retains/modifies vanilla circuit controls and connections; §18 PLC/sensor additions are candidates. No count of wire products is assumed from connection behavior. |
| Waste, recycling, and pollution handling | Flare, effluent clarifier, reprocessing, nuclear disposal | Core selected disposal and nuclear recovery capabilities are in §16. Other recovery and recycling machines remain candidates. |
| Terrain and construction utilities | Landfill, tiles, concrete, construction robots | Core retains/modifies useful vanilla terrain and construction systems; terrain behavior is owned by [Map and World Generation](map-world-generation.md) and non-building items by [Intermediate Products](intermediate-products.md). |
| Non-building constructables (excluded here) | Vehicles, fuel, weapons/ammo, armor/equipment, modules, packs | Their Core/vanilla/extension dispositions and product ownership are in [Intermediate Products](intermediate-products.md); items and their corresponding placeable entities must be counted separately. |

## Family Scope and Counting Register

The register assigns a scope to every named family in the detailed categories. Each category table below supplies its individual role, candidate phase, candidate tier/capability changes, and proposed inputs/outputs; the material map supplies source or gap status. A candidate phase or tier is not an approved unlock. **Core capability** means the function is required but does not imply a separate entity; **Core candidate** is not a required entity or recipe. Where several names appear in one row, they remain separate family candidates unless an alias is explicitly identified.

| Category / families | Disposition, role, phase, and expected product or service |
|---|---|
| 1. Vanilla drills, pumpjack, offshore pump | Core, vanilla retained/modified; Phase 1 extraction and water/oil, with later mineral/brine service open. Existing vanilla variants and any new capability tiers remain distinct. |
| 1. Underground extractor, deep drill, scanner, open-pit excavator, enhanced pump | Core candidates for buried/deep extraction, prospecting, bulk ore, or brine/offshore fluid service; individual Phase 1-3 timings and tiers in §1 are provisional. |
| 2. Crushers, mills, screens, washers, gravity/magnetic/electrostatic/contact separators, flotation | Core processing-family candidates, Phases 1-3; produce prepared ores/concentrates. Rougher and cleaner/scavenger cells are configurations of a flotation family unless a distinct entity is justified. Tiered and untiered examples remain provisional. |
| 3. Dryer, roaster, calciner, kiln, sintering, press, spray dryer | Core thermal/forming candidates, Phases 1-3; produce dried, roasted, calcined, sintered, or formed feed. A PTFE-free Phase 2 press configuration plus compatible thermal furnace is required for first PTFE construction materials under [ADR-0078](adrs/ADR-0078-assign-phase-2-ptfe-finishing-equipment.md); exact tier/entity split remains open. |
| 4. Blast/direct-reduction, converter, arc/submerged-arc, reverberatory, cupola, induction furnaces | Core metallurgical candidates, Phases 1-4; produce pig iron, DRI, steel, silicon, and other metal feed. The Phase 2 submerged-arc silicon capability is selected; other exact equipment splits and tiers are open. Phase 1 furnaces cannot require bauxite-derived alumina. |
| 5. Leach vessels and pads, autoclave, general, fixed-bed and fluidized-bed reactors | Core chemical process-family scope; produce leach solutions and chemical intermediates in the candidate phases shown in §5. No blanket tier roster or separate entity per operation is selected. |
| 6. Filter, crystallizer, extraction column, ion exchange, precipitation and decanting | Core separation candidates, Phases 2-3, for filtered, recovered, crystallized, and separated material streams. Their exact equipment, phase and tier splits are open; nuclear startup is not automatically gated on Phase 3 candidates. |
| 7. Electrowinning, electrorefining, chlor-alkali and water electrolysis | Core process-family candidates, Phases 2-4, for metals and chemical reagents; chlor-alkali coproducts supply selected HCl startup. Phase 2 copper supply must not depend solely on the Phase 3 electrorefiner candidate. Specific cell entities and tiers remain open. |
| 8. Cracking, polymerization, extrusion, molding and fiber processing | Core chemical and polymer candidates, Phases 2-3; produce monomers, resins, shapes and fibers. First PTFE polymerization uses the non-PTFE baseline; first finished PTFE uses §3, not the later extruder/molder. |
| 9. Purification, crystal growth, sawing, polishing, etching, thermal processing, deposition, lithography, cleanroom and packaging | Core semiconductor capabilities by Phase 2; exact separate entities and tiers are candidates, producing the selected wafer/chip/package families. The floating-zone row is removed, not an additional family. First vacuum equipment is independent of its own chip outputs. |
| 10. Uranium conversion/enrichment, pellet preparation, Zr/Hf separation, cladding, rod and absorber fabrication | Core Phase 2 capabilities for usable fission and CPU hafnium; equipment splits and tiers remain open. Fuel-pellet sintering and Zr/Hf separation are capability rows, not automatically separate entities. |
| 10. B₄C press, breeder-panel, tungsten-tile, coil-winding, optics and containment fabrication | Core candidates for specialist fabrication, Phases 2-4 as individually shown. Phase 2 bridge-facility construction needs any required magnet assembly before the Phase 3 winder candidate; Phase 3 Tokamak construction needs compatible forming, assembly, magnet and fuel capabilities without Phase 4-only specialists. Thermoelectric conversion is unselected, not the chosen Hawking converter. |
| 11. Boiler, steam engine, steam turbine, native poles | Core, vanilla retained; boiler/engine operate in Phases 1-2, turbine in Phase 2. All three are untiered; grid and pole behavior remain vanilla-compatible. |
| 11. PV, fission, LFP storage, tiered poles, later power routes/converters | Core selected capabilities; PV/fission/LFP begin in Phase 2, Tokamak/geothermal/PV/CSP in Phase 3, and Hawking/exergy/stellar solar in Phase 4. Exact entities, materials and tiers remain open. Stellar collection and beaming need a no-DLC implementation. |
| 11. Wind, advanced wind, tidal/wave, flywheel | Unselected supplementary Core candidates; phases and entities remain open. A capacitor bank and vanilla accumulator are overlapping storage concepts, not automatically two families. |
| 11. Custom transmission and grid stabilization | Optional extension candidates, not Core; no tiers or dependency are selected. The blackout-fuse safety item is not selected. |
| 12. Gun, laser, flamethrower, artillery, plasma and railgun turrets; walls/gates/mines | Core fixed-defense families; four turret families reuse base-game scope and two are added. Sustained power and ammunition capabilities are selected principles; phases, individual tiers, construction, and product inputs remain open. |
| 12. Ammunition loading, mixing, nitration, detonator assembly, tungsten-core forming | Core support-capability candidates in the phases shown in §12; produce ammunition components and finished munitions. Press and reactor operations may reuse §3 and §5 families; a distinct detonator-assembly entity and all tiers remain open. |
| 12. Rocket turret, anti-materiel weapon | Unselected separate weapon candidates, not additional Core turret families. The Space Age rocket turret is not a 2.1 base-game prototype; the anti-materiel concept is an optional extension candidate. |
| 13. Belts, splitters, inserters, storage and roboports | Core, vanilla retained/modified; Phase 1 onward as progression permits, transporting or storing items and supporting construction/logistics robots. Exact variants remain open. High-speed belt is a belt variant candidate, while belt-jumper crossings correspond to vanilla underground transport belts; bot hub and construction bay are roboport-family candidates unless distinct capabilities justify a split. |
| 13. Rails, signals, stops, powered rail, freight terminal | Core vanilla rail/signaling/station service plus selected electric traction; first intended train use requires an acyclic powered-rail path. The compact freight terminal is a later Core candidate, not required for normal automated loading or scheduling. |
| 13. Crane, AGV station and robotic arm | Core logistics/assembly candidates, Phases 3-4 as shown in §13; exact roles, entity splits, tiering, and sources are open. |
| 14. Tanks, pipes, pumps, valves, heat exchangers and vacuum/compression | Core fluid-service families, with vanilla tanks/pipes/pumps retained or modified. Required Phase 2 semiconductor vacuum must bootstrap without its own chips; individual compatibility mechanics, tiers and specialist entities are open. |
| 15. Rubber mill, sheet press and fiber layup | Core polymer-forming candidates, Phases 2-3, for elastomers, sheets and composite parts; tier counts and distinct entity splits are open. |
| 16. Tailings, waste-to-fuel, metal recovery and sludge conditioning | Core recovery/process candidates, Phases 2-3; exact outputs and separate entities are open. They do not replace the required ordinary gas/fluid or nuclear disposal paths. |
| 16. Gas flare, liquid clarifier, nuclear recovery, conditioning and deep disposal | Core required capabilities: the flare is available no later than Phase 2 silicon reduction; liquid handling must be viable when needed; nuclear handling exists by each corresponding first output. Ordinary gas/fluid release is powered and polluting, while conditioned nuclear-solid disposal is continuous, powered/material-consuming, slightly polluting, and uncapped. Nuclear capability/entity splits and construction remain open. |
| 17. Vanilla lab, six domain labs, Core and Array | Core lab and first-Core capabilities: vanilla research retained/modified; six distinct domain facilities and bridge mappings in Phase 2; first Core follows all six T2b2 domains and the Array. Its first compute uses packaged CPUs and its alignment uses Invar mechanical adjustment; the Array does not consume domain packs. Component item/entity splits are open. |
| 17. Compute campus, archive and observation | Core simulation-network candidates, Phase 3 onward; supply compute, storage and observations. Their necessity, entity splits, quantities and tiers are open. |
| 18. Sensors, PLC, actuator, wired control and optimization | Core control-family candidates, Phases 1-4 as individually shown; vanilla combinators and circuit connections remain available. Exact custom controller entities and tiers are open; ordinary process balance must not depend on custom control code. |

**Counting boundary:** Six selected turret families and six selected domain-facility families are separate family counts, not counts of new items, entities, tiers, recipes, or technologies. The remaining candidate names are not a normalized total: capability rows can share entities, and aliases and variants must not be added again. Total unique products, constructables, placeable entities, machine families, tiers/variants, recipes, and technologies are independently **TBD** until their identities are fixed in the relevant catalog and research phases. Do not add extension candidates or excluded entries to Core totals.

**Alias and discrepancy dispositions:**

- Underground mining extractor and vanilla underground transport belt have different functions; retain the latter for belt crossings and do not claim one replaces the other.
- Enhanced blast furnace is a new or repurposed ironmaking capability, not a replacement for a nonexistent vanilla blast-furnace prototype; vanilla furnace reuse is open.
- Flotation banks, high-speed belts, roboport/bot-bay proposals, capacitor/accumulator storage, and military press/reactor support may share existing families as noted above; resolve any separate entity only against a distinct capability.
- Plasma Discharge Emitter and Railgun/Coilgun proposals are alternative descriptions of the selected plasma and railgun families, not two extra turrets. Their attack details remain open.
- A Phase 4 breeder-panel assembler or tungsten-tile molder is not the first Phase 3 Tokamak production capability. Phase 5 must verify earlier suitable forming and assembly paths.
- Candidate component lists below that conflict with an accepted phase or bootstrap boundary do not impose extra prerequisites. In particular, Phase 1 has no bauxite-derived alumina, first fission has no mandatory B₄C/superconductor, and first vacuum/PTFE equipment cannot require its own outputs.

---

## 1. Extraction & Mining

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Electric Mining Drill | MTier 1–4 (Phases 1–3) | Mine single mineral deposits from surface | Multi-tier: larger footprint, higher ore yield multiplier per tick at each tier |
| Underground Deposit Extractor (formerly Underground Mining Belt) | MTier 2–3 candidates (Phases 1–2) | Extract buried deposits onto a transport belt | New extraction capability candidate; not an alias for, or replacement of, the vanilla underground transport belt. Deposit eligibility and tiers remain open |
| Deep Borehole Drill | Phase 3 | Access Tier 3 polymineral deposits in situ | Broaches mixed feed at depth; lower yield per tick but no excavation pit needed |
| Prospect Scanner | Phase 2 | Reveal depth/grade of hidden mineral veins under terrain | Diagnostic tool, not productive; reveals deposit data for player planning |
| Open-Pit Excavator | Phase 3 | High-throughput surface mining of bulk materials (coal, stone, iron) | Large footprint, massive output — endgame mining alternative to electric drills |
| Offshore Pump (Enhanced) | Phases 1–4 | Extract brine from coastal deposits; crude oil from offshore | Multi-tier: each tier increases flow rate and unlocks new deposit types |

## 2. Ore Preparation & Concentration

Preparation machines may use different wear-resistant materials where a distinct hardness or processing capability warrants a tier. Tiering is family-specific; single-tier equipment and shared machines remain valid under ADR-0075.

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

Candidate thermal-machine tiers use **different refractory/structural materials per tier** where higher temperature or precision warrants a new capability. Tier count and whether a given family is tiered remain open.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Rotary Dryer** (MTier 1–2) | T1 Phase 1; T2 Phase 2 | T1: Steel shell + basic heating element (coal/gas burner). T2: Chrome-alloy shell + refractory brick lining (alumina/silica composite) — can handle wet concentrates without corrosion | T1 only dries clean, non-corrosive materials (sand, stone). T2 accepts *wet mineral concentrates* containing sulfide minerals — the first dryer that won't be corroded by acidic moisture from ore processing |
| **Roaster (Oxidizing)** (MTier 1–3) | T1 Phase 1; T2–3 Phase 2 | T1: Steel shell + basic refractory lining; modeled off-gases need separate handling. T2: Chrome-molybdenum hot-gas ducts + catalytic converter insert (Pt-group on alumina substrate) for off-gas capture. T3: Niobium-microalloyed thermal chamber + integrated gas scrubbing system | T1 has no integrated gas recovery: modeled off-gases need a useful consumer, bounded buffer or production control, or powered, pollution-producing disposal under [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md). If a Phase 1 recipe produces them, a viable handling path must be available by its first use without permanent accumulation. T2 proposes usable SO₂ capture for sulfuric acid. T3 proposes acid scrubbing and conversion of residual particulates to a usable sulfate byproduct. |
| **Calciner** | Phase 2 | Single-tier: steel vessel + high-grade refractory brick (alumina/silica/crome composite). Controlled atmosphere for thermal decomposition without oxidation. Used for limestone → lime + CO₂ and other calcination reactions. | No tier progression — this is a *specialized* process machine with one clear function. Material selection matters more than tier count |
| **Rotary Kiln** (MTier 2–3) | Phases 2–3 | T1: Steel shell + basic refractory lining + manual temperature control. Limited to <900°C. T2: Chrome-molybdenum pressure shell + niobium-microalloyed thermal insulation layer + semiconductor-grade temperature sensors. Can reach 1200°C with ±5°C precision. T3: Niobium-microalloyed vessel + tungsten-carbide internal wear protection + automated material feed system | T1 can only perform simple calcination (limestone → lime). T2 enables high-temperature sintering and roasting up to 1200°C; it does not perform metallurgical silicon reduction, which uses the dedicated Phase 2 submerged-arc furnace under [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md). T3 adds *continuous operation* for high-volume rotary-kiln processes |
| **Sintering Machine / Sinter Strand** | Phase 2 | Single-tier: steel frame + chrome-alloy heating elements + refractory mesh belt + cooling water jacket. Produces porous sintered ore pellets from fine-grained ores. | No tier progression — one specific function (agglomerating fines into furnace-ready lumps). Material is chosen once for the full lifetime of the machine |
| **Pellet Press / Briquette Machine** (MTier 1–3) | Phases 1–3 | T1: Steel frame + basic hydraulic press + replaceable tooling. Simple briquetting only. T2: Chrome-molybdenum press components + niobium-microalloyed pressure vessel + precision die system. Can press powders into dense, structurally sound pellets. T3: Tungsten-carbide pressing dies + tungsten-carbide guide rails + hydraulic servo control | T1 can only form *loose briquettes* — low mechanical strength, disintegrates under high pressure/temperature (unsuitable for blast furnace feed). T2 produces *dense structural pellets* — withstands blast furnace conditions. T3 adds *precise compaction*: controlled density variation within each pellet (e.g., harder outer shell, more reactive core) |
| **Spray Dryer** | Phase 2 | Single-tier: steel chamber + refractory lining + atomizer nozzle assembly + hot gas inlet. Atomizes liquid slurry into dry powder via hot gas contact. | No tier progression — specialist dewatering machine used between solution processing and crystallization steps |



## 4. Smelting & Reduction (Metallic Extraction)

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Enhanced Blast Furnace | MTier 1–3 candidates (Phases 1–2) | Carbon-reduced iron smelting from ore + coke/lignite → pig iron | New or repurposed ironmaking capability; vanilla has furnace families but no blast-furnace prototype to replace. Phase 1 uses basic refractory, not bauxite-derived alumina |
| Direct Reduction Furnace | Phase 2 | Produce DRI (direct reduced iron) from ore using reducing gas (H₂/CO mix) | Gas feed from gasifier or electrolysis; alternative to blast furnace path |
| Converter (BOF/LD) | MTier 1–3 (Phases 2–3) | Convert pig iron to steel by blowing oxygen to burn off excess carbon | Requires pig iron input + oxygen; tier = blow rate/temperature control |
| Electric-Arc Furnace (EAF) | MTier 1–4 (Phases 2–4) | Melt scrap metal or DRI with graphite electrodes for alloy production | Higher voltage → more power → faster melting, better temp range at high tiers |
| Submerged-Arc Silicon Furnace | Phase 2 | Carbothermic reduction of quartz/silica with carbon to metallurgical silicon | Dedicated facility under [ADR-0033](adrs/ADR-0033-phase-2-submerged-arc-silicon-reduction.md); construction materials, detailed design, and CO off-gas handling remain open |
| Reverberatory Furnace | Phase 2–3 | Pyrometallurgical smelting of copper/nickel sulfide concentrates | Flame heats charge from above; produces matte (Cu₂S/FeS) for converting |
| Cupola Furnace | Phase 1 | Melt pig iron + scrap to produce cast iron; simple coke-fired design | Early-phase option for cast iron; lower control precision than EAF but no electricity needed |
| Vacuum Induction Melting Furnace | Phase 3+ | Melt high-purity alloys under vacuum; removes gas impurities | Endgame metallurgy; produces premium alloys requiring MTier 4-5 components to build |

## 5. Chemical Extraction & Reactors

Chemical equipment may differ by pressure, temperature, or material compatibility when those differences create useful capabilities. Tiers and any corrosion, leak, or failure mechanics remain unselected; no family must be tiered by default.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Tank Leach Cell / Agitated Vessel** (MTier 1–3) | Phase 2 | T1: Carbon steel vessel + rubber liner. Can handle only mild acids (dilute H₂SO₄ <10%). Limited agitation speed. T2: Stainless steel 316L vessel + PTFE internal coating + niobium-microalloyed agitator shaft. Handles concentrated acids and elevated temperatures (80–120°C). T3: Niobium-microalloyed pressure vessel + tantalum-clad internals + semiconductor-grade pH/temperature control | T1 can only leach *moderately corrosive* ores (hematite, magnetite with dilute acid). T2 handles *concentrated acids at high temperature* — the tier where copper/nickel leaching becomes viable. T3 adds *automated process control*: real-time pH and temperature monitoring with auto-adjustment, producing consistent leach solutions without manual calibration |
| **Heap Leach Pad + Sprayer System** | Phase 2 | Single-tier: steel support structure + PTFE-lined containment basin + spray nozzle array. No power required — purely reagent-driven extraction of low-grade ores from stacked ore piles. | No tier progression — this is a *low-capital alternative* to tank leaching with much slower throughput but zero power cost. The player trades time/space for infrastructure cost |
| **Pressure Leach Autoclave** (MTier 1–3) | Phases 2–3 | T1: Thick-walled steel vessel + chrome-alloy internal seal + manual pressure gauge. Max pressure 15 bar, max temp 200°C. Can leach moderately refractory ores. T2: Niobium-microalloyed pressure shell + tantalum-clad interior surface + ceramic insulation layer. Handles up to 40 bar / 350°C — the range where complex sulfide ores (chalcopyrite, pentlandite) become economically leachable. T3: Tungsten-carbide wear-resistant internals + niobium-microalloyed safety relief system + automated pressure/temperature feedback control | T1 can only process *moderately refractory* ores. T2 handles *high-pressure/high-temperature refactory leaching* — this tier unlocks recovery from chalcopyrite and other hard-to-process sulfides (critical for copper/nickel production). T3 adds *safety automation*: automatic pressure relief, emergency cooling, and process interruption before catastrophic failure |
| **General-Purpose Chemical Reactor** (MTier 1–3) | Phases 1–3 | T1: Carbon steel vessel + rubber seals + manual stirring. Temperature range: ambient to 100°C (water bath heating only). Limited to mild reactions (neutralization, simple precipitation). T2: Stainless steel vessel + PTFE-lined interior + chrome-molybdenum heating jacket. Temperature range: -20°C to 300°C. Can run Ostwald nitric acid chain, ammonia oxidation. T3: Niobium-microalloyed pressure-rated vessel + HfO₂ insulated interior + semiconductor-grade PID controller. Handles exothermic reactions up to 500°C with precision thermal management | T1 limited to *mild chemistry*: pH adjustment, basic precipitation, simple neutralization. T2 unlocks *industrial-scale chemical synthesis*: Ostwald chain (NH₃ → HNO₃), ammonia oxidation, Fischer-Tropsch. T3 handles *exothermic/high-temperature reactions with precision control*: where temperature drift of even ±5°C changes product yield or creates safety hazards |
| **Catalytic Converter / Fixed-Bed Reactor** | Phase 2+ | Single-tier: steel vessel + refractory brick lining + catalyst loading bay (replaceable catalyst bed support). Requires specific catalyst material input per recipe. | No tier progression — this is a *catalyst-specific* reactor. The key variable is the catalyst material, not machine tier. Different catalysts enable different reactions in the same hardware |
| **Fluidized-Bed Reactor** (MTier 2–3) | Phases 2–3 | T1: Steel vessel + refractory distributor plate + basic gas inlet manifold. Limited particle size distribution control. T2: Chrome-molybdenum pressure shell + niobium-microalloyed gas distribution system + ceramic particle separator. Precise fluidization control with minimal particle loss. T3: Niobium-microalloyed thermal chamber + tungsten-carbide distributor nozzles + automated particle recirculation system | T1 provides *functional fluidization* with higher catalyst consumption per output cycle than T2+ tiers. T2 achieves *stable, controlled fluidization*: uniform gas-solid contact for efficient coal gasification or kyanite processing. T3 adds *automatic catalyst management*: recirculates and reclaims escaped particles, reducing catalyst consumption by ~60% |



## 6. Solution Processing & Separation

Solution-processing candidates include gravity settling, filtration, and chemical separation. Material compatibility and tiering remain open; Phase 2 battery and nuclear routes cannot depend solely on later specialist configurations.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Vacuum Filter / Filter Press** (MTier 1–3) | Phase 2 | T1: Steel frame + rubber filter cloth + basic vacuum pump connection. Single-layer filtration, periodic auto-cleaning every 50 output cycles (machine offline for 30 seconds). Filtration rate: low. T2: Stainless steel pressure frame + PTFE membrane filter layers + automated cake discharge mechanism. Multi-layer filtration with timed release. T3: Niobium-microalloyed pressure vessel + tungsten-carbide filter support surfaces + semiconductor-grade differential pressure sensor | T1 is *fully autonomous* but requires periodic self-cleaning downtime — the player must buffer output during clean cycles or accept interruptions. T2 enables *continuous filtration with automated discharge*: filter cakes release automatically on timer, allowing unattended operation of leach circuits. T3 adds *precision monitoring*: real-time differential pressure across filter layers signals clogging before production impact — critical for automated factory integration |
| **Crystallizer / Evaporator** (MTier 1–3) | Phases 2–3 | T1: Cooling crystallizer — carbon steel shell + copper cooling coil. Simple batch evaporation only. Limited to non-corrosive salts (sodium chloride from brine evaporation). T2: Forced-circulation evaporator — stainless steel vessel + chrome-molybdenum circulation pump + PTFE heat exchanger tubes. Handles corrosive salt solutions (zinc sulfate, copper sulfate from electrowinning raffinate). T3: Vacuum crystallizer — niobium-microalloyed pressure-rated body + HfO₂ thermal insulation layer + tungsten-carbide agitator bearings + automated product discharge | T1 can only process *non-corrosive feedstocks* — brine evaporation for salt production. Corrosive solutions require PTFE lining that T1 lacks. T2 handles *corrosive industrial salts*: concentrated metal sulfate/acetate solutions from leaching and electrowinning circuits. The tier where crystallization becomes an economically viable separation step. T3 enables *vacuum-assisted low-temperature crystallization*: product purity is significantly higher (no thermal degradation of heat-sensitive compounds) — the tier required for battery-grade salt production |
| **Solvent Extraction Column** | Phase 3 | Single-tier: PTFE-lined stainless steel column internals + niobium-microalloyed support structure + precision flow control valves. Separates dissolved metals using immiscible organic solvents (e.g., copper extraction from sulfate solution). | No tier progression — this is a *specialist separation machine* with one function per configuration. The player must choose the correct extractant reagent during construction to match the target metal pair |
| **Ion Exchange Unit** | Phase 3 | Single-tier: stainless steel vessel + ion-exchange resin bed (organic polymer) + silica support layer + acid regeneration system (PTFE-lined). For uranium, rare-earth element, and trace metal recovery from solution. Resin regeneration requires periodic acid feed. | No tier progression — *specialist* machine with one function per resin type. Material is selected once for the full lifetime of the unit. Reagent consumption (acid) scales with throughput, not tier |
| **Precipitation Tank / Thickener** (MTier 1–2) | Phases 2–3 | T1: Carbon steel vessel + rubber agitator seal + basic pH sensor (glass electrode in ceramic housing). Requires periodic manual insertion of "precipitant reagent" item every 30 output cycles. T2: Stainless steel pressure vessel + niobium-microalloyed mixing impeller + semiconductor-grade automatic dosing pump | T1 is *self-running* but requires periodic reagent delivery (player or inserter) — the tier where the player must build parallel logistics for this machine. T2 enables *automated precipitation control*: real-time pH monitoring with auto-dosing of precipitating agent, producing consistent product — required before scaling any hydrometallurgical circuit beyond pilot size |
| **Centrifuge / Decanter** | Phase 3 | Single-tier: niobium-microalloyed drum (tungsten-carbide bearing surfaces) + stainless steel housing + semiconductor-grade speed controller. High-speed spinning separates fine solids from liquids rapidly. Alternative to filter press for continuous operation with finer particles. | No tier progression — *specialist* dewatering machine used when filter press throughput is insufficient. Material selection (niobium/tungsten) is chosen once for corrosive/abrasive service |


## 7. Electrochemical Processing

Electrochemical candidates may differ in electrode material, membrane quality, control precision, and compatible service. Families may also remain untiered; their construction, capabilities, and required power interface remain open.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Electrowinning Cell / Tankhouse** (MTier 1–3 candidate) | Phases 2–4 | T1 candidate: lead-alloy anodes, copper starter sheets, carbon-steel frame, and limited electrode area. T2 candidate: stainless frame, alloy supports, and larger area. T3 candidate: niobium-alloy vessel, tantalum-bearing transport, and current-density monitoring. The source disagrees whether automatic cathode handling begins at T1, T2, or T3; exact capabilities remain open. | Candidate functions include metal deposition, unattended cathode handling, and selective recovery from mixed solutions. First usable automated handling, phase gates, tiering, and materials require validation; no specific candidate tier is selected. |
| **Electrorefiner** | Phase 3+ | Candidate single-tier equipment: stainless steel vessel + nickel-plated tank interior + titanium anode support structure. Purifies impure metal by controlled deposition — copper/nickel/zinc purification from impure smelted product. Inputs, process conditions, and output quality remain open. | Candidate specialist machine with configuration by material; exact power draw is open and no custom grid-quality mechanic is selected |
| **Chlor-Alkali Membrane Cell** (MTier 2–4) | Phases 2–3 | T2: Titanium anode (dimensionally stable anode coating) + polymer membrane cell body + copper busbar connections. Can split brine into Cl₂, NaOH, and H₂ but with standard membrane configuration (~1000 hours). Higher membrane replacement cost. T3: Niobium-microalloyed housing + reinforced polymer membrane (PTFE-reinforced) + niobium-tin shielding layers. Membrane lifetime extended to ~5000 hours. Better separation efficiency — less chlorine contamination of NaOH product stream. T4: Tungsten-carbide electrode support + niobium-microalloyed pressure vessel + semiconductor-grade cell voltage monitoring | T2 produces *chlorine-contaminated caustic soda* that requires secondary purification — the tier where basic chlor-alkali chemistry becomes viable but at significant ongoing membrane consumption cost (1 membrane per 5 cycles). Its H₂ and Cl₂ coproducts feed the HCl synthesis route under [ADR-0034](adrs/ADR-0034-select-chlor-alkali-coproducts-for-hcl-makeup.md); the NaOH sink and detailed coproduct balance remain open. T3 produces *high-purity sodium hydroxide* directly from the cell, eliminating the need for separate purification infrastructure. The tier where chlor-alkali becomes economically competitive with purchased NaOH, with reduced consumable cost (1 membrane per 20 cycles). T4 adds *precision monitoring and lowest consumable cost*: semiconductor-grade voltage tracking paired with premium "high-grade membrane" item per 50 output cycles |
| **AEM Water Electrolyzer** | Phase 3 | Single-tier: stainless steel vessel + alkaline electrolyte (KOH solution) + AEM (anion-exchange membrane) separator + copper/nickel electrode plates. Splits water into high-purity H₂ and O₂ gases. Fusion-grade hydrogen purity. | No tier progression — *specialist* fuel production machine. Material selection (membrane type) is critical to performance but doesn't vary by tier |


## 8. Polymer Chemistry & Primary Processing

These are candidate production machines that transform refined chemicals into polymers, plastics, and composite materials. Different chamber materials may support distinct processes; no blanket tier requirement is selected.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Petrochemical Cracking Furnace** (MTier 1–3) | Phases 2–3 | T1: Steel shell + basic refractory lining (alumina/silica). Limited to mild cracking (<500°C) — produces narrow product range (mostly ethylene). Cannot process mixed feedstocks. T2: Chrome-molybdenum pressure shell + catalytic catalyst bed housing (nickel-alloy support structure) + PTFE-lined hot-gas ducts. Can reach 700–800°C for deeper cracking — broader product distribution (ethylene, propylene, butane). Accepts mixed hydrocarbon feeds. T3: Niobium-microalloyed reaction chamber + tungsten-carbide internal wear surfaces + niobium-tin thermal insulation layer + semiconductor-grade temperature zone control | T1 produces *only ethylene* from a single feedstock (naphtha or FT naphtha). Limited product diversity constrains downstream chemistry options. T2 enables *propylene co-production*: the tier where both ethylene and propylene are available, unlocking PVC (from ethylene + chlorine) AND acrylonitrile/acrylic (from propylene + ammonia). Critical for enabling multiple polymer pathways. T3 adds *multi-zone temperature control*: different sections of the furnace operate at different temperatures, maximizing yield of target products — reducing waste feedstock by ~30% |
| **Polymerization Reactor / Vessel** (MTier 1–3 candidate) | Phase 2 baseline; later upgrades may extend into Phase 3 | T1 candidate: compatible stainless/metal pressure vessel, service-appropriate non-PTFE metal/graphite sealing, and basic temperature control. No PTFE liner or gasket in first construction. T2 candidate: PTFE-lined stainless vessel and improved agitator/monomer compatibility. T3 candidate: advanced alloy internals and precision process control. Exact materials and conditions remain open | T1 supports baseline polyethylene and initial PTFE production under [ADR-0064](adrs/ADR-0064-phase-2-ptfe-bootstrap.md), with PTFE-free upstream reagent/monomer equipment. Later upgrades may add PVC, HDPE, acrylic, and engineering-polymer capability; they are not required to make first PTFE |
| **Extruder / Pelletizer** | Phases 2–3 | Single-tier: chrome-molybdenum barrel + PTFE die assembly + niobium-microalloyed heating elements. Melt and shape polymer output into pellets or continuous profiles. Finishing for plastics production. Tier = barrel length, heater zones, die precision within a single tier range. | No tier progression — this is a *finishing machine* that accepts output from the Polymerization Reactor and formats it for storage or downstream use. Material selection matters only for chemical compatibility with processed polymer types |
| **Injection Molding Press** | Phase 3 | Single-tier: chrome-molybdenum mold assembly + niobium-microalloyed clamping mechanism + semiconductor-grade temperature controllers. Forms polymers into complex shapes under pressure in heated mold. Produces casings, connectors, components directly from polymer melt. | No tier progression — *specialist* shaping machine for high-precision plastic parts. Used when extrusion profiles are insufficient (requires specific component geometry) |
| **Fiber Winder / Spinning Line** | Phase 3+ | Single-tier: stainless steel fiber-drawing assembly + niobium-microalloyed heating elements + precision tension control system. Draws polymer or glass fibers for composite reinforcement. Produces fiberglass or synthetic fiber feedstock for composite materials. | No tier progression — *specialist* machine with one function per configuration. Polymer type selection (polyester vs nylon) is chosen at construction, determining final fiber strength and chemical resistance |

**Selected PTFE bootstrap:** Initial construction-grade PTFE forming uses a Phase 2-compatible configuration of the §3 Pellet Press / Briquette Machine family, followed by a compatible general-purpose §3 thermal furnace, under [ADR-0078](adrs/ADR-0078-assign-phase-2-ptfe-finishing-equipment.md). Both must use non-PTFE construction and tooling; the specific thermal configuration and process service remain open. Do not require the Extruder / Pelletizer's PTFE die, ordinary melt processing, tungsten-carbide specialist tooling, or the Phase 3 Injection Molding Press for first seals and linings. Nuclear equipment may use PTFE only after this complete startup path exists; stainless steel is not assumed compatible with every fluorine service.


## 9. Semiconductor Fabrication Chain

Semiconductor machines may have precision-based capability tiers; untiered families are also valid. Under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) and [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md), full cleanroom and advanced chipmaking capability through contemporary real-world practice belongs in Phase 2. Post-Core progression is reserved primarily for capabilities beyond current-day industry. Exact machine tiers, process routes, material grades, build inputs, and research gates remain open; the entries below are candidate implementations.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Purification Column (polysilicon grade)** | Phase 2 | Single-tier: high-purity silica/ceramic column internals + niobium-microalloyed reflux condenser. Trichlorosilane distillation for the pre-Core electronic-grade polysilicon precursor under [ADR-0032](adrs/ADR-0032-select-trichlorosilane-route-for-phase-2-polysilicon.md). | No tier progression — *specialist* purity machine. This is a candidate facility implementation for the Phase 2 contemporary cleanroom, wafer, chip, and packaging capability under ADR-0026; build materials remain open |
| **Czochralski Crystal Grower** (MTier 1–3) | Phase 2 (T1–T3 contemporary capability; exact tier gates open) | T1: Graphite crucible + basic inert atmosphere system + copper-wound heating coil. Maximum ingot diameter: 50 mm. Limited rotation control precision (~±10 RPM). Single-crystal growth possible but with moderate defect density. T2: Niobium-microalloyed graphite crucible liner + niobium-tin temperature control wiring + HfO₂ thermal insulation layer. Maximum ingot diameter: 150 mm. Rotation control ±1 RPM — enables doping uniformity required for conventional CPU-grade wafers. T3: Tungsten-carbide crucible support + semiconductor-grade inert atmosphere monitoring + automated seed crystal positioning | T1 produces *wafers with high defect density* — sufficient only for basic photovoltaic cells, not integrated circuits. The player can make solar-grade polysilicon crystals but cannot yet produce chips from them. T2 produces *conventional CPU-grade wafers*: larger diameter (150 mm) with controlled doping uniformity. T3 adds *automated growth control*: computer-controlled seed descent and rotation optimization, reducing manual calibration steps and improving yield |
| **Floating Zone Furnace** | Not selected | The separate entity is removed from this inventory; the purification column and crystal grower remain candidate capabilities. | Do not count as an additional family, entity, tier, or mandatory purification stage |
| **Wafer Saw / Multi-Wire Diamond Cutter** | MTier 1–3 (Phase 2 contemporary wafer preparation; exact tier gates open) | T1: Steel frame + basic diamond wire tensioning. Produces thick wafers. Recipe input: 2 ingots → 6 wafer blanks (lower yield per ingot). T2: Niobium-microalloyed cutting head + tungsten-carbide wire guide bearings + precision tension control system. Recipe input: 1 ingot → 5 wafer blanks (improved yield over T1). T3: Tungsten-carbide wire drive system + niobium-microalloyed coolant circulation + semiconductor-grade thickness measurement sensor. Recipe input: 1 ingot → 8 wafer blanks (highest yield). | T1 requires *more input ingots per output wafer* — the player must account for higher polysilicon consumption across the chain. T2 improves *material utilization*: fewer ingots needed per wafer, reducing bottleneck pressure across the production chain. Produces thinner, more uniform wafers suitable for both solar and basic electronics. T3 enables *sub-100 µm wafer production* — required for advanced multi-layer chip packaging where thin die are stacked vertically |
| **Chemical-Mechanical Polisher (CMP)** | Phase 2 (contemporary capability; exact process grades open) | Single-tier: niobium-microalloyed polishing chamber + tungsten-carbide platen + semiconductor-grade slurry delivery system. Polishes wafer surface to nanometer roughness with controlled abrasive slurry + pad. Prepares ultra-flat surface before lithography. | No tier progression — *specialist* finishing machine with one function per slurry type (different slurries for silicon, copper, dielectric polishing) |
| **Wet Etch Bath / Station** (MTier 1–3) | Phase 2 (T1–T3 contemporary capability; exact tier gates open) | T1: Plastic (HDPE) tank + rubber seals. Handles only mild etchants (dilute HF). Cannot process concentrated acids or elevated temperatures. Limited to basic wafer cleaning operations. T2: PTFE-lined stainless steel vessel + niobium-microalloyed heating jacket + semiconductor-grade pH/temperature control. Handles concentrated hydrofluoric acid, HNO₃/HF mixtures (piranha etch), and elevated temperatures up to 100°C. Etches silicon at controlled rates. T3: Niobium-microalloyed pressure-rated vessel + tungsten-carbide heating elements + automated chemical dosing system | T1 can perform *only basic cleaning* — insufficient for wafer preparation before lithography where nanometer-scale surface quality matters. Restricted to mild HF use only. T2 enables *controlled silicon etching*: the tier where conventional semiconductor patterning chemistry becomes viable (HNO₃/HF mixtures selectively etch crystalline silicon at known rates). T3 adds *automated chemical management*: precise dosing and concentration control ensures consistent etch rates — essential for production reliability |
| **Thermal Oxidation / Diffusion Furnace** (MTier 2–4) | Phase 2 (T2–T4 contemporary capability; exact tier gates open) | T2: Tube furnace design — niobium-microalloyed reaction tube + tungsten-carbon heating elements + precise oxygen/water vapor inlet system. Single-zone temperature control (~±10°C). Batch processing of single wafer loads. T3: Multi-zone tube furnace — niobium-microalloyed tube with separate zone controllers + semiconductor-grade thermocouple array + automated wafer loading mechanism. 5+ independently controlled temperature zones. Can process multiple wafers simultaneously with gradient-controlled oxidation profiles. T4: Rapid thermal processor — tungsten-carbide heating elements + niobium-microalloyed radiation shields + real-time infrared wafer temperature monitoring | T2 produces *single-wafer batches* with limited uniformity across the wafer surface — acceptable for conventional CPU production but inefficient at scale. Oxidation rate varies by position within the tube. T3 enables *multi-wafer batch processing*: independent zone control means different wafers can undergo different oxidation profiles simultaneously. T4 adds *rapid thermal processing*: heats/cools wafers in seconds rather than hours — the capability needed for advanced dopant diffusion where precise thermal time-temperature profiles create specific junction depths |
| **CVD / PVD Deposition Chamber** (MTier 2–4) | Phase 2 (T2–T4 contemporary capability; exact tier gates open) | T2: Basic deposition chamber — niobium-microalloyed reaction vessel + tungsten-carbide susceptor + RF/heating power supply. Can deposit basic dielectric layers (silicon dioxide, silicon nitride). Film thickness precision: ±10%. Limited to simple deposition processes. T3: Multi-process deposition chamber — niobium-microalloyed process chamber with switchable CVD/PVD tooling heads + semiconductor-grade gas delivery system + real-time film thickness monitoring. Can deposit metal layers (copper, aluminum), dielectric layers, and conductive layers. Film precision: ±2%. T4: Advanced deposition system — niobium-microalloyed ultra-clean deposition chamber + tungsten-carbide target materials + semiconductor-grade plasma source for PVD | T2 can deposit *basic insulating layers* (SiO₂ dielectric). T3 unlocks *metal deposition*: copper and aluminum wiring layers become available for conventional circuits, along with additional dielectric materials. T4 enables *advanced plasma-enhanced deposition*: higher quality films with better step coverage for advanced chip manufacturing |
| **Photolithography Stepper / Aligner** | Phase 2 (contemporary patterning, including advanced stepper capability; exact tier gates open) | Phase 2 patterning includes contemporary high-resolution stepper capability. The exact tool, process, and materials remain open; the candidate high-precision assembly includes electronic-grade polysilicon UV lens elements, precision ceramic positioning stages, semiconductor-grade position sensors, and an illumination system. | Contemporary conventional and high-resolution patterning are Phase 2 capabilities. The candidate stepper's exact specifications and build materials remain open. |
| **Cleanroom Module** | Phase 2 (full contemporary cleanroom capability; exact module tiers open) | Large modular facility (~4×4 tiles): HfO₂ particulate filtration panels + fluoropolymer duct lining (PTFE) + niobium-microalloyed structural frame + semiconductor-grade air-quality sensors. Six modular slots accept cleanliness components: T1–T2 support conventional CPU-grade wafers; T3 inserts produce high-clean substrates, and a full T3 fill produces ultra-clean wafers for advanced photolithography. | The cleanroom is a *buildable machine* rather than spatial prerequisite — players construct it as a large facility and fill modular slots to increase output cleanliness level. Different recipes require different cleanliness tiers as input items |

| **Semiconductor Packaging Line** | Phase 2 (contemporary conventional and advanced packaging; exact options open) | The line packages conventional CPU-grade dies. Candidate equipment includes a copper lead-frame feeder, gold-wire bonding station with a tungsten-carbide capillary tool, and plastic/molded-ceramic package press; die attach, wire bonding, and molding are its sub-steps. Advanced packaging adds higher-density die and package options. | No tier progression — *specialist* assembly line with one configuration per bond type (gold vs copper wire, plastic vs ceramic package). Material selection is made at construction |


## 10. Nuclear Fuel & Component Fabrication

Nuclear fabrication may require different containment, precision, and automation capabilities. Tiering and actual construction materials are family-specific; not every equipment candidate or bridge material is a baseline requirement.

The selected in-game Phase 2 fission and Phase 3 Tokamak routes need phase-compatible construction and fuel capabilities. Later-phase specialist machines listed below are candidates, not prerequisites for those earlier routes; equipment splits remain open and work-plan Phase 5 must verify viable paths.

**Selected Phase 2 readiness:** First fission has usable automation, hafnium metal preparation/basic absorber forming, and normally item-fed rod production under ADR-0065. Ordinary shielding must bootstrap nuclear equipment without its own depleted-oxide output. Required recovery and nuclear-solid handling are in Category 16; optional precision upgrades must not gate these minimum capabilities.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Uranium Conversion Line** | Phase 2 minimum path; advanced equipment split open | Candidate service-compatible metal vessels, PTFE gaskets/linings, and graphite/refractory process parts; compatibility depends on the selected chemistry. Implements Uraninite/concentrate -> UF6 -> gas-centrifuge enrichment -> enriched UF6 -> UO2/pellet preparation under [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), with separate tails handling. First PTFE comes from the independent bootstrap under ADR-0064 | Supplies uranium rods and the shared-chain thorium startup seed; both retain the shared qualitative enrichment grade and deferred numeric target. Qualified recovered uranium returns through the front end, and both UF6 branches need fluorine recovery/conditioning under ADR-0066. Exact chemistry, seed preparation, equipment split, and pellet integration remain open |
| **Fuel Pellet Sintering Furnace** | Phase 2 minimum pellet-preparation capability; separate entity not selected | Candidate refractory construction (high-purity alumina/silica brick) + niobium-microalloyed heating elements. A dedicated furnace is one possible way to produce UO2 pellets as a rod-assembly intermediate; an integrated process or other equipment split remains possible. | No tier progression selected — dedicated machine status, build materials, process conditions, and power requirements remain open |
| **Cladding Tube Mill** | Phase 2 minimum capability for both fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md) | Candidate single-tier equipment: stainless steel tube-forming equipment + niobium-microalloyed pressure testing chamber. Zirconium-alloy cladding is selected under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md), with early/mid-Phase-2 zircon access shared with the CPU hafnium chain. A distinct Zr/Hf separation stage is required under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md); feed preparation/conversion, separation chemistry, alloy grade, downstream alloying and forming routes, build materials, and tier remain open. | No tier progression selected — *specialist* metal-forming machine; alloy choice determines neutron transparency |
| **Fuel Rod Assembly Line** (MTier 1–3 candidate) | Usable Phase 2 minimum for both options under ADR-0043/0065; later tier timing open | T1 candidate: steel frame, basic alignment/loading/welding fixtures, and standard item-fed batch operation. T2 candidate: improved feeders/alignment and helium leak-test equipment. T3 candidate: inline inspection and rejection sorting. Exact construction and inspection requirements remain open | Baseline rods can be supplied through normal factory automation without per-pellet player actions. Later variants may improve handling, batch capability, testing, or inspection; they do not introduce the first usable fuel supply |
| **Zr/Hf Separation Plant** | Distinct stage required in the shared Phase 2 zircon path under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md); exact gate and dedicated-entity status remain open | Candidate equipment: stainless steel processing vessels + PTFE-lined separation columns + niobium-microalloyed structural support. Represents the distinct separation stage between zircon-feed preparation/conversion and downstream zirconium-alloy or hafnium uses. Separation chemistry, output forms and grades, equipment configuration, yields, and recipe split remain open. | A dedicated separation machine is one candidate implementation; the route-stage requirement does not select a separate entity or tier progression |
| **Hafnium Absorber Plate Liner** | Phase 2 baseline; Phase 3 precision upgrades are candidates | Candidate steel/stainless forming equipment with Phase 2-compatible tooling; first construction cannot need its own absorbers. Shared Zr/Hf separation must be followed by suitable hafnium metal preparation, not direct use of chipmaking HfO2. Later precision tooling/materials remain open | Basic absorber forming is available before first fission under ADR-0065. Exact grade, forming method, dedicated-entity status, and upgrades remain open; neither tungsten-carbide specialist tooling nor boron carbide is a universal baseline prerequisite |
| **Boron Carbide Press + Sintering Furnace** | Phases 2–3 | Single-tier: tungsten-carbide pressing dies + niobium-microalloyed sintering furnace. Powder metallurgy: mixing mill → isostatic press → sintering furnace for B₄C control rod absorbers. | No tier progression — *specialist* powder metallurgy line with one function per absorber design |
| **Lithium Breeder Blanket Panel Assembler** | Phase 4+ specialist candidate | Candidate equipment for Li-containing breeder/heat-exchange panels; actual materials and process remain open | A Phase 3-compatible blanket fabrication and assembly path must exist for the selected Tokamak route without this Phase 4 specialist |
| **Tungsten Armor Tile Molder** | Phase 4+ specialist candidate | Candidate equipment for sintered tungsten plasma-facing tiles; actual materials and process remain open | A Phase 3-compatible refractory forming/sintering path must exist for the selected Tokamak route without this Phase 4 specialist |
| **Superconducting Coil Winding Machine** (MTier 2–4) | Phases 3–4 | T2: Manual winder design — steel frame + niobium-tin tension control mechanism. Limited to small-diameter coils. Operator-controlled winding tension with manual termination points. T3: Automated tension-controlled winder — stainless steel frame + niobium-microalloyed drive system + PTFE-insulated tensioning arms + automated layer insulation applicator (HfO₂ dielectric). Consistent tension across full coil length. Eliminates hot spots from uneven winding. T4: Cryogenic-grade insulator applicator — niobium-microalloyed fully enclosed winding chamber + automated cryogenic-compatible insulation application system + semiconductor-grade position feedback for sub-millimeter wire placement precision | T2 produces *inconsistent coils*: manual tension control creates localized stress points that can crack insulation during cryogenic cooldown. Acceptable for prototype magnets but not production use. T3 produces *production-quality coils* with uniform winding tension and automated inter-layer insulation — the tier where superconducting magnet fabrication transitions from experimental to industrial. T4 enables *cryogenic-grade precision*: sub-millimeter wire placement accuracy required for high-field fusion magnets where even 0.5 mm displacement changes magnetic field distribution significantly |
| **Precision Optics Fabrication Station** | Phase 4+ | Single-tier: cleanroom enclosure (HfO₂ particulate filtration + fluoropolymer duct) + diamond-turning lathes (tungsten-carbide tooling) + niobium-microalloyed vibration isolation table. Produces optical substrate components for endgame Extreme-Energy Core construction. Requires electronic-grade polysilicon blanks as input material. | No tier progression — *specialist* ultra-precision machine with one function per optical element type |
| **Extreme-Pressure Containment Vessel Assembler** | Phase 4+ | Single-tier: niobium-microalloyed structural frame + tungsten-carbide shell-forming tools + automated welding systems (semiconductor-grade process control) + autoclave curing chambers (refractory-lined). Welds/assembles multi-layer pressure vessel shells for Hawking Engine containment. Shell forming → autoclave curing of composite layers → in-situ welding inspection at high tiers. | No tier progression — *specialist* endgame assembly machine with one function per vessel design |
| **Thermoelectric Conversion Array Module** | Phase 4+ candidate | Candidate cleanroom-compatible assembly station (HfO₂ particulate filtration + fluoropolymer duct) + semiconductor-grade thermocouple junction bonding equipment (niobium-microalloyed frame). Assembles p-type/n-type semiconductor thermocouple pairs into power-conversion panels. Converts waste heat to electricity via Seebeck effect. | Unselected specialist-machine candidate; the Hawking route instead uses the selected thermophotovoltaic direction under [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) |


## 11. Power Generation

> Full power system details are in [Power System](power-system.md). This catalog lists generator, distribution, and storage families.
>
> **Selected power direction:** Introduce fission in Phase 2 and fusion in Phase 3; keep steam turbines through the end of Phase 2. Phase 3/4 route identities and non-steam converter families are recorded in [Power System](power-system.md). Exact materials, fuel fabrication, thermal-storage design, converter dimensions, and progression gates remain open.

### Power Generation (Candidate Core Generators)

The selected Phase 3 route identities are Tokamak fusion, geothermal, and solar PV, with concentrated solar thermal and storage as an additional route. Phase 4 includes Hawking radiation, cross-universe exergy-gradient extraction, and stellar-scale solar collection with beamed transmission. These route decisions do not approve the candidate material lists or recipes below. Other generator families listed here remain supplementary candidates unless selected in [Power System](power-system.md).

Tiering is family-specific; not every generator needs tiers. The vanilla boiler, steam engine, and steam turbine remain untiered in this direction. Candidate reactor and solar tiers remain subject to later review.

**Fission baseline and safety boundary:** ADR-0065 requires usable, normally automated first fission with Phase 2 hafnium controls. [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md) excludes blackout-induced meltdown gameplay and a dedicated emergency-safety item. Detailed tiers, control mechanisms, coolant choices, and research gates remain open.

| Generator Type | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Boiler** (vanilla retained) | Phase 1–2 | Uses burner-item fuel and water to produce steam; no Prometheus tier progression proposed | Not a generator by itself; fuel-item behavior remains vanilla |
| **Steam Engine** (vanilla retained) | Phase 1–2 | Consumes steam from a boiler; no direct fuel input or custom tiers | Early power remains available through Phase 2, but requires more space and support infrastructure than fission |
| **Steam Turbine** (vanilla retained) | Phase 2 only | Converts high-temperature steam from fission heat exchangers | Use through the end of Phase 2, then retire from the progression; no custom tiers proposed |
| **Solar Panel Array** (MTier 1–3 candidate) | Phase 2 introduction; later tier phases remain open | T1: steel frame, glass surface, basic conductors, and crystalline-silicon cells from a dedicated PV route based on the selected Phase 2 silicon supply direction; exact grade and process steps remain open. Candidate later upgrades may use higher-purity silicon, aluminum mounting brackets, and compound-semiconductor cells; exact routes and gates remain open. | PV begins no earlier than Phase 2. The initial cell route does not depend on CPU wafer/chip fabrication or post-Core-only capability under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md); its own cleanliness and equipment needs remain open. |
| **Wind Turbine** (candidate) | Phase and scope open | Candidate single-tier steel tower, copper generator winding, and basic bearing assembly; proposed weather-dependent output and pole connection remain unvalidated. | Location-dependent renewable candidate; no wind route or tier progression is selected. Phase 1 power remains combustion under [Power System](power-system.md). |
| **Geothermal Tap / Heat Exchanger Station** | Phase 3 selected route identity; constructable candidate | Single-tier source proposal: titanium heat-exchanger plates and niobium-microalloyed pressure housing; exact materials and extraction method remain open. Extracts heat from geothermal sites; location and resource limits remain open. | Selected Phase 3 geothermal route; constructable scope, site placement, and extraction limits remain open under [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) |
| **Thermal Fission Reactor** (MTier 1–4 candidate) | Usable Phase 2 baseline; later tier count/timing open | Baseline construction candidates: steel vessel, suitable moderator/cooling components, Phase 2 hafnium absorber controls, ordinary shielding, and the required zirconium-alloy fuel rods under ADR-0043/0044. Exact configuration remains open. Later variants may use improved alloys, instrumentation, reflector options, or coolant compatibility | First fission is a normally automated industrial power source under ADR-0065, with ordinary fuel feeding and no compulsory rod-adjustment babysitting. Later variants add capability rather than first usability. Boron carbide, beryllium reflectors, superconducting wiring, Phase 3 specialist equipment, and advanced inspection are not universal startup prerequisites. No blackout-meltdown loop or dedicated safety item; exact controls, grades, efficiencies, quantities, and gates remain open |
| **Concentrated Solar Power Tower + Thermal Storage** | Phase 3 selected additional route | Single-tier construction candidate: steel tower, high-temperature receiver, and molten nitrate-salt thermal storage (sodium/potassium compounds are a material candidate; exact blend remains open). Mirrors focus sunlight onto the receiver; stored heat feeds the selected closed supercritical-CO₂ Brayton direction rather than a steam turbine. Alloys and assembly chain remain open. | Dispatchable solar-thermal option; site geometry, storage duration, conversion performance, and constructable scope remain open |
| **Fusion Tokamak Reactor** | Phase 3 selected route identity; constructable candidate | Single-tier construction candidate from the source inventory: Nb₃Sn magnet coils, tungsten armor, lithium-beryllium breeder panels, and cryogenic insulation. See [Power System](power-system.md) and [Endgame Vision](endgame-vision.md); exact assembly recipe and phase-compatible construction chain remain open. | Phase 3 fusion route; selected non-steam converter direction is closed supercritical-CO₂ Brayton for high-grade heat |
| **Hawking Radiation Engine** | Phase 4 selected route (one of three) | The accepted concept is a confined event horizon; the selected conversion direction is thermophotovoltaic recovery from a controlled high-temperature emitter. Power output, assembly scope, emitter spectrum, and research gate remain open. The first-Core gate is recorded in [Research and Progression](research-progression.md) and [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md); Core Level 2/3 and route-specific research gates remain open. | No tier progression is selected; exact role and progression remain open |
| **Cross-Universe Exergy-Gradient Tap** | Phase 4 selected route identity | Conceptual boundary couples to a constrained external non-equilibrium source; a direct field-coupling converter is the current design direction. No construction materials or recipe are selected. | Speculative source and boundary-control mechanics remain undefined |
| **Stellar-Scale Solar Collector + Energy Beam** | Phase 4 selected route identity | Space-based photovoltaic collectors generate electricity; an energy beam transmits it to remote receivers. The collector, not the beam, is the generator. Scale, materials, and receiver details remain open. | Distinct from terrestrial solar PV by location, scale, and transmission; exact implementation remains open |
| **Advanced Wind Array / Offshore Wind Farm** | Phase 4 | Single-tier: niobium-microalloyed tower structure (corrosion-resistant offshore) + titanium blade mounting hubs + semiconductor-grade wind direction tracking system. High-capacity turbines for consistent large-scale power generation. Tier = turbine capacity per unit, array management sophistication within single design range. | No tier progression — *specialist* offshore installation with one structural design |
| **Tidal/Wave Generator** | Phase 4 | Single-tier: titanium-alloy marine-grade construction (corrosion-resistant for seawater service) + niobium-microalloyed turbine housing. Harness ocean/tidal energy in coastal locations. Tier = blade/float size, conversion efficiency within single design range. Location-dependent (coastal biome only). Steady but location-locked. | No tier progression — *specialist* marine installation with one structural design |

**Fuel-processing boundary:** Producer gas, biogas, and liquid-fuel streams are not direct generator inputs. If retained as power fuels, they must first be converted to burner items for the vanilla boiler/steam-engine path. Gasification and fuel preparation are not generator families.

**Non-steam conversion direction:** High-grade Tokamak and concentrated-solar heat use a closed supercritical-CO₂ Brayton cycle; geothermal uses a binary organic Rankine cycle; the Hawking route uses a thermophotovoltaic receiver. Phase 3/4 solar uses direct photovoltaic conversion, and the cross-universe route uses a direct field-coupling concept. Detailed materials, working fluids, values, and constructables remain open in [Power System](power-system.md).

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

### Energy Storage Systems

> Phase 2 LFP is the selected initial battery chemistry under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md) and [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md); cell/pack construction, capacity, and progression remain open. Other storage entries are candidates unless explicitly selected. They do not require custom transmission. A dedicated reactor-safety fuse is not required under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md).

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Capacitor Bank (accumulation) | Phase 1 | Buffer short-term power fluctuations; provides burst power for machine startups | Candidate early buffer; tier inputs and any dependency on later battery cells remain open. Same function as vanilla accumulator. |
| Battery Storage Unit | Phase 2 | Longer-duration energy storage for load leveling and general grid backup; not a fission-safety dependency | LFP cathode chemistry is selected under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md); feed sources and starting-region access are set under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). Recovery routes, complete cell/pack construction, and capacity progression remain open |
| Dead-Battery Capacitor / Fuse Link | Not selected | Unapproved safety-device proposal | No dedicated consumable safety item is required in Phase 2 Core under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md); do not treat it as an approved constructable or research gate |
| Flywheel Energy Store | Phase 3+ | Mechanical kinetic energy storage with high round-trip efficiency | Candidate alternative to batteries; precision components, servo-motor source, machine tiers, and performance remain open |

### Grid Stabilization Infrastructure — Optional Extension Candidates (Not Core)

> [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md) keeps custom grid stabilization out of Core. The entries below are unapproved concepts for a future optional extension; no phase, behavior, or research gate is selected.

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Reactive Power Compensator | Optional extension candidate | Hypothetical voltage support in a future custom-grid model | Not a Core requirement or part of the accepted vanilla-grid behavior |
| Surge Protector / Lightning Arrester | Optional extension candidate | Hypothetical transient-protection mechanic in a future custom-grid model | Not a Core requirement or fission-safety dependency |
| Frequency Regulator | Optional extension candidate | Hypothetical load/generation balancing in a future custom-grid model | Not a Core requirement for variable-renewable generation |

### Power Generation + Energy Storage Infrastructure Summary — Candidate Core Scope

> The accepted core distribution direction is vanilla-grid-compatible tiered poles. Generator and storage entries remain candidate scope; custom transmission and stabilization remain extension proposals.

| Infrastructure Type | Total Items | Tiered? | Key Capability Tiers |
|---------------------|-------------|---------|----------------------|
| Power-generation and conversion families | Candidate count not normalized | Family-specific | Boiler/steam engine untiered; Phase 2 fission with steam turbines until phase end; selected Phase 3 Tokamak, geothermal, solar PV, and CSP; selected Phase 4 Hawking, cross-universe exergy tap, and stellar-scale solar; sCO₂ Brayton, binary ORC, and TPV conversion directions |
| Core power-pole families | Vanilla poles plus tiered variants; count TBD | Yes; exact tiers TBD | Compatible with the vanilla network; pole statistics and material progression remain open |
| Energy Storage Systems | Candidate categories; count not normalized | Family-specific | LFP chemistry is selected; exact storage lineup, capacity, and progression remain open; no fission safety device is selected under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md) |
> **Source-proposed extension scope:** Custom transmission towers + lines (3 variants), transformers / substations (1 type, MTier 1-3), grid stabilization devices (3 types), HVDC Converter Station (Phase 4+). These counts and scope labels remain provisional.

## 12. Military Infrastructure

**Selected scope — see [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md):** Core retains the base-game fixed-defense families and adds plasma and railgun turrets. Their exact tiering, phase, behavior, and inputs remain open. Military products belong in [Military System](military-system.md) and [Intermediate Products](intermediate-products.md).

### A. Selected Core Turret Families and Candidate Variants

Candidate turret tiers should use distinct structural materials and weapon mechanisms where appropriate, rather than only stat increases. Ammo-driven lines may progress from kinetic through incendiary, explosive, and penetration capabilities; electrical candidates add role-based progression through laser, plasma, and railgun defenses. Exact tiering and phase placement remain open.

References to burrowed or otherwise altered enemy targets are extension illustrations, not selected Core enemy behavior.

| Turret Type | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Gun Turret (Tiered Ammo Support)** (MTier 1–3) | Phases 1–4 | T1: Steel housing + basic copper wiring + iron barrel. Fires kinetic ammo only (lead core, copper jacket, steel case). Rate of fire: moderate. Magazine capacity: small. Simple mechanical loading mechanism — reliable but limited ammunition options. T2: Stainless steel housing upgrade + nickel-alloy trigger mechanism + chrome-molybdenum reinforced barrel. Accepts incendiary ammo (fuel/oxidizer mix + magnesium ignition compound) in addition to kinetic. Rate of fire +30%. Larger magazine capacity. Semi-automatic feeding replaces manual mechanical action. T3: Niobium-microalloyed structural frame + tungsten-carbide barrel lining (erosion-resistant for AP penetrator firing) + niobium-tin targeting computer wiring + tantalum-ceramic trigger assembly | Accepts armor-piercing tungsten-core ammunition. Rate of fire +50% over T1. Maximum magazine capacity. Semiconductor-guided targeting improves first-round accuracy against fast/burrowed targets. The source proposes steel, stainless steel, tungsten carbide, and electronics as progression materials; contemporary semiconductor capability is Phase 2, while the actual turret materials and gates remain open. |
| **Laser Turret (Electrical; MTier 1–3 candidate)** | Phases 2–4 candidate | T1: proposed steel housing, glass optics, copper wiring, and ~50 kW output. T2: proposed niobium-alloy heat sink, polysilicon optical elements, HfO₂ panels, semiconductor targeting, and ~200 kW output. T3: proposed tungsten-carbide housing, precision alignment, thermal interfaces, and ~500 kW output. The source's proposed UV-transmitting silicon optics require validation; optical materials and construction remain open. | Candidate variants improve output, cooling, and tracking. Exact phases, tiers, power profiles, optics, and inputs are not selected; no additional Phase 3 bridge product is implied. |
| **Plasma Turret (Core electrical family)** | TBD | Construction materials, power components, and any consumables remain TBD | An artillery-like plasma orb with splash is a candidate attack; substantial power is required, while attack model, phase, tiers, range, recipe, and profile remain open |
| **Railgun Turret (Core electrical family)** | TBD | Construction materials, power components, and ammunition/energy model remain TBD | A long-range line attack with splash is a candidate; substantial power is required, while attack model, phase, tiers, range, recipe, and profile remain open |
| **Flamethrower Turret / Incendiary Launcher** (MTier 1–3) | Phases 2–3 | T1: Steel body + basic fuel reservoir (copper piping, rubber hoses) + ignition compound chamber. Small payload capacity, short range (~30 m). Simple manual trigger mechanism. Early game incendiary option before chemical infrastructure is established. T2: Stainless steel fuel storage tank (corrosion-resistant for chemically active fuels) + PTFE hose lining (compatible with petrochemical fuels) + precision ignition chamber (nickel-alloy igniter assembly). Larger payload (~100 m³ fuel storage). Effective range extended to ~60 m. Auto-ignition system replaces manual trigger. T3: Niobium-microalloyed pressure vessel body + cryogenic-compatible sealing gaskets (for liquid fuel at low temperatures) + semiconductor-grade flow control valve (adjustable spread pattern via PLC signal) | Larger payload (~250 m³ storage), extended range to ~100 m, adjustable spray cone angle. Can be automated via industrial control network for perimeter defense. This turret's progression mirrors *petrochemical infrastructure* — you need the polymer processing chain (PVC pipes, rubber seals, tank lining materials) to build each successive tier |
| **Artillery Turret** | Core vanilla family; phase and tiers open | Vanilla fixed artillery with construction and progression to be aligned | Long-range fixed defense; the placing entity and its ammunition are counted separately |
| **Rocket Turret (unselected candidate)** | Not selected for Core | Candidate steel launcher, guidance, and explosive ammunition; tungsten or optional depleted uranium are unapproved payload possibilities | The Space Age rocket turret is not a base-game prototype. No enriched-uranium, reactor-operation, or nuclear-cycle dependency is selected |


### B. Ammo Products — Manufactured Intermediate Items (Cross-Domain Reference)

*These are non-building products, not machines. This candidate reference is excluded from infrastructure counts; product identity and pathway ownership belong in [Intermediate Products](intermediate-products.md) and [Military System](military-system.md).*

| Product | Tier | Primary Feed Materials | Recipe Input Chain (key intermediates) | Infrastructure Section |
|---------|------|----------------------|--------------------------------------|-----------------------------------|
| **Kinetic Bullet (T1)** | T1 | Lead core, copper jacket, steel case, gunpowder propellant | Galena → roasted/smeled lead ingot + chalcopyrite flotation → electrolytic Cu + hematite → pig iron → EAF steel + sulfur combustion + charcoal → carbonized biomass/coal coke → ground powder | §4 Smelting, §2 Flotation, §7 Electrochemical, §3 Thermal |
| **Incendiary Bullet (T2a)** | T2a | Fuel/oxidizer mix, magnesium ignition compound, steel casing | Candidate organic and magnesium feeds; dolomite is a possible magnesium source. Precursors, recovery, processing, and the complete route remain open | §8 Polymer/Composite, §5 Reactors, §6 Solution Proc. |
| **Explosive HE Shell (T2b)** | T2b | Candidate explosive and initiating components, steel casing | Candidate chemical precursors and assembly; feed roles, compatibility, and the complete route remain open | §5 Reactors, §6 Solution Proc., §8 Polymer/Composite |
| **Armor-Piercing Round (T3)** | T3 | Tungsten core alloy, specialized propellant, copper sabot | Scheelite/Tungstenite → Caustic leach + purification → W powder + pressing/sintering + nitrocellulose/tungstenite + carbonized charcoal/calcined biomass | §5 Reactors, §8 Polymer/Composite, §4 Smelting |
| **Penetration Rocket (T4)** | T4 candidate | Tungsten or optional depleted-uranium material, booster, guidance module | Candidate dense-material use; any depleted-uranium metal preparation must be separately qualified. No enriched-fuel, thorium-cycle, or operating-reactor prerequisite is selected; exact recipes and military scope remain open | Military System owns the candidate; ADR-0063 permits optional depleted-uranium use, not a mandatory sink |

### C. Military Component Support Machines (Core Mod)

| Machine Name | Tier/Phase | Operations | Design Notes |
|-------------|-----------|------------|--------------|
| Ammunition Press / Loading Machine | Phase 1–2 | Combine lead core + copper jacket + steel case + propellant into finished kinetic bullets | Intermediate processing for T1 ammo; tier = throughput speed and precision alignment. Reuses pellet press/briquette machine family from Thermal Processing §3 with tooling swap. |
| Incendiary Compound Mixer / Reactor | Phase 2–3 | Mix fuel/oxidizer compounds with ignition catalyst for incendiary rounds | Reuses general chemical reactor or dedicated small-scale mixer; tier = mixing precision, temperature control. No unique build required — use existing reactor infrastructure from §5. |
| HE Explosive Formulation Tank + Nitration Station | Phase 3 | Synthesize nitric-acid-derived explosives via controlled nitration reactions under pressure/temperature control | Requires pressure-rated vessel + safety controls; tier = pressure rating, temperature control precision, safety interlocks. Uses pressure leach autoclave family from §5 with specialized internals. |
| Precision Detonator Assembly Machine | Phase 3 | Assemble reliable detonation initiation components from explosive, primer, and electrical parts | Combines chemistry (explosive compounds) + electronics (trigger circuits); produces reliable firing mechanisms. Tier = assembly precision + testing reliability. |
| Tungsten Core Forging Press | Phase 4+ | Forge tungsten-carbide penetrator cores under extreme pressure for AP rounds | Requires refractory tooling + hydraulic press at high MTier; intermediate product between raw tungsten and finished AP ammo. Uses pellet press/briquette family from §3 with specialized dies. |

### D. Advanced Weapon Concepts — Previous Extension Proposals

*These alternative descriptions refer to the selected plasma and railgun families in section A, not extra turret families. Their detailed attacks and inputs remain candidates. The anti-materiel concept remains an extension candidate.*

| Machine Name | Tier/Phase | Operations | Design Notes | Previous Extension Proposal / Current Scope |
|-------------|-----------|------------|--------------|-------------------|
| Plasma Discharge Emitter | Phase TBD | Candidate concentrated plasma burst from magnetic containment; superconducting coils are an unselected material proposal | Alternative description of the Core plasma family; burst/projectile behavior and values remain open | Core family under ADR-0071 |
| Railgun / Coilgun Turret | Phase TBD | Candidate acceleration of a ferromagnetic projectile | Alternative description of the Core railgun family; projectile/beam behavior and material inputs remain open | Core family under ADR-0071 |
| Anti-Materiel Rifle / Heavy Cannon | T4 (EXT) | Pierces through fortified structures and heavily armored enemies with AP penetrator + HE dual-compatible ammo | Extended weapon tier for ground combat; requires tungsten refining chain from Phase 3. | `difficulty-advanced` extension candidate |

The electrical turret families are Core under ADR-0071; their detailed designs remain open. The ~80-machine estimate is unnormalized and is not a catalog count.

### E. Defense Infrastructure Progression

These are candidate progression examples, not selected ammunition recipes, deposit requirements, or technology gates. Vanilla defense remains available under the selected Core roster.

| Stage | Defense type | Driven by | Industrial Gate |
|---|---|---|---|
| Early (Phase 1) | Passive barriers, basic turrets with kinetic ammo | Basic steel, lead, simple chemistry | Hematite mining + sulfur refining → basic gun turret + T1 kinetic ammo |
| Mid (Phase 2–3) | Active defense grids, incendiary/explosive ammo supply | Chemical intermediates, alloy production, precision manufacturing | Petrochemical cracking OR oil refining → incendiary compounds; Ostwald chain → HE explosives |
| Late (Phase 3–4) | Distributed defense network, AP penetrator capability, automated targeting | Semiconductors, tungsten processing, advanced automation | Tungsten refining (scheelite/Tungstenite) → AP rounds; cleanroom → semiconductor guidance modules |
| Endgame (optional) | Strategic deterrence via penetration rockets, advanced weapon extensions | Advanced metallurgy and electronics; optional depleted-uranium material use | Candidate tungsten or depleted-uranium payload and guidance; no required reactor operation or enriched fuel. Military scope, exact materials, and gates remain open |

**Note:** Retain ordinary vanilla automatic turret operation and logistics. Additional targeting automation beyond the selected fixed-defense behavior is not specified; optional integrations remain unapproved.

## 13. Logistics & Material Handling

Logistics families may use different materials where they add meaningful capability; no blanket tier requirement is selected. Vanilla belt-speed variants remain available or modifiable without automatically becoming distinct Prometheus capability tiers.

### Conveyor & Belt Systems (Candidate Variants)

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Basic Transport Belt** (MTier 1–4) | Phases 1–4 | T1: Steel roller frame + basic rubber belt material. Simple mechanical drive. Speed: baseline (1×). Weight capacity: low (~20 kg/item). T2: Chrome-alloy roller housings + reinforced polymer belt (from HDPE processing). Improved wear resistance and flexibility. Speed: 1.5×. Weight capacity: medium (~40 kg/item). Belt material accepts moderate chemical exposure without degradation. T3: Niobium-microalloyed drive motor housing + high-performance polymer belt (fluoropolymer-reinforced). Corrosion-resistant belt surface for use in chemical processing areas where acidic spills are likely. Speed: 2×. Weight capacity: high (~80 kg/item). Can transport heavy Phase 2 intermediates without sagging or deformation. T4: Tungsten-carbide roller bearings + alloy-reinforced composite belt (niobium-microalloyed structural layer + semiconductor motor controller for variable speed control). Maximum throughput configuration with active speed management per segment | Speed: 2.5×. Weight capacity: very high (~120 kg/item). Smart speed control allows individual segments to throttle for downstream balancing without splitters — essential in large factories where belt congestion is the bottleneck. Belt evolution mirrors materials science progression (rubber → polymer → alloy-reinforced), matching design principle that infrastructure tiers reflect build materials, not input quality |
| **High-Speed Conveyor Belt Network** | Phase 3–4 | Single-tier: semiconductor-grade motor controller (packaged ICs × 5 per segment) + niobium-microalloyed drive assembly + high-performance fluoropolymer belt. Advanced belt segments with maximum throughput speed. Requires advanced circuits/semiconductors. Significantly faster than standard belts, supports heavier loads. | No tier progression — this is a *specialist* endgame logistics component that replaces Basic Transport Belt entirely in areas where maximum throughput is required. Material selection matters more than tier count |
| **Adjustable-Speed Belt Splitter / Merger** (MTier 1–3) | Phase 2+ | T1: Steel frame + basic mechanical speed-matching mechanism (manual belt tension adjustment). Splits one input belt into two outputs at equal speed. Two inputs max, one output max. Fixed routing ratio (50/50). T2: Stainless steel housing + nickel-alloy motorized tensioning arms + semiconductor-speed sensor array. Automatic speed matching — can split 1:3 or 3:1 asymmetrically. Four-way splitting available at MTier 2+. Accepts different input/output belt speeds without jamming. T3: Niobium-microalloyed drive assembly + tungsten-carbide tensioning bearings + intelligent load-balancing algorithm | Dynamic routing ratio control (adjustable 10/90 to 90/10). Automatic load balancing across multiple outputs — if one downstream line is full, automatically shifts more throughput to the other output. The tier where belt routing transitions from *static infrastructure* to *adaptive system* |
| **Understacker / Topstacker Belt Jumper** | Phase 1–2 | Single-tier: steel frame + rubber isolation pads (vibration dampening) + basic alignment mechanism. Cross one belt over or under another without item transfer. Basic version from early game, upgraded versions at higher tiers with better speed handling. | No tier progression — this is a *layout tool* with one function per geometry type. Different models exist for different crossing angles, not different tiers |


### Infrastructure Buildings (Candidate Variants)

The freight-terminal and bot-bay rows below are candidates, not requirements for basic vanilla automated station loading, dispatch, or roboport operation. The proposed bot-bay weight restrictions and manual construction do not restrict vanilla construction bots. A terminal may integrate with demand dispatch, but dispatch does not require that terminal. Powered rail and optional demand-based dispatch are Core under ADR-0073/0074; exact terminal design and tiers remain open.

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

Pipes and other fluid machines support networked layouts. A family may remain untiered; any new progression tier must add a meaningful capability rather than only capacity.

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
| **Centrifugal Compressor / Vacuum Pump** (MTier 1–3 candidate configurations) | Phase 2 process-compatible compression/vacuum baseline; Phase 3 specialist upgrades optional | Baseline candidates: Phase 2-compatible metal housing, mechanical pumping components, copper motor, suitable seals, and conventional pressure control. First semiconductor-vacuum equipment cannot require chips whose fabrication needs that equipment. Later corrosion-resistant, precision-control, and higher-performance variants remain candidates | Provide process-appropriate Phase 2 vacuum for contemporary CVD/PVD under [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md), with compression and vacuum configurations distinguished; a centrifugal compressor alone is not assumed to provide every vacuum service. Exact pump types, pressure targets, tiers, and recipes remain open; required semiconductor vacuum is not Phase 3-gated |

**Tiering principle:** Candidate fluid-handling tiers should add a meaningful compatibility or processing capability. Whether material-specific fluid gating or leak mechanics exist remains open.

## 15. Rubber Processing, Polymer Forming & Composite Fabrication

Polymer-forming families may have capability-based tiers, but untiered or shared machines remain valid. They support plastics, elastomers, and composite materials.

### Rubber Processing

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Rubber/Kneading Mill** (MTier 1–3) | Phase 2 | T1: Steel rollers + basic electric motor (copper winding, steel bearings). Handles natural rubber only. T2: Chrome-molybdenum roller surface + niobium-microalloyed housing + precision temperature control via nickel-alloy thermocouple. Handles synthetic rubber compounds with curatives. T3: Titanium alloy core rollers + semiconductor-grade PID controller + tantalum-sealed drive motor | T1 only processes raw natural/synthetic rubber feedstock (limited to basic formulations). T2 can mix in *curatives and fillers* — the capability that produces finished elastomer compounds for gaskets, seals, and belt materials. T3 adds *continuous production*: no batch stop/start, steady compound output rate |

### Sheet Extrusion & Composite Layup

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Sheet Extrusion / Rolling Press** (MTier 1–3) | Phases 2–3 | T1: Steel roller housing + basic heating elements. Produces thick sheets only (minimum 10 mm). T2: Chrome-alloy rollers with precision gap control + PTFE release surface. Can produce thin sheets for laminates (sub-1 mm). T3: Niobium-microalloyed thermal chamber + semiconductor temperature sensors + vacuum-assisted layer bonding | T1 produces only thick structural plates. T2 can produce *thin gauge sheets* — required for composite laminate layup. T3 adds *vacuum-assisted lamination*: produces layered composites directly, eliminating the need for a separate bonding step |
| **Fiber Layup Station** (MTier 1–3) | Phase 3+ | T1: Steel frame + basic resin mixing pumps (copper motor, steel housings). Manual fiber placement. T2: Stainless steel mixing tanks with PTFE lining + precision pump controller + ceramic fiber guide rollers. Semi-automated fiber winding. T3: Niobium-microalloyed structural frame + semiconductor-grade tension control system + robotic fiber delivery arm | T1 is *manual* — a single operator places fibers by hand (low speed, low consistency). T2 adds *semi-automated winding*: consistent fiber orientation and tension, but still requires operator oversight. T3 is *fully automated*: programmable layup patterns (cross-hatch, unidirectional, helical), producing aerospace-grade composite panels |

**Tiering principle:** A polymer-processing tier may be justified by compound formulation capability rather than speed. Exact tier requirements and composite routes remain open.

## 16. Waste Processing & Loopback (Circular Economy)

Candidate recovery machines are player-built and may gain **capability changes per tier**. Advanced circular recovery can develop later, but ordinary gas/fluid disposal must be available when needed under ADR-0035. Nuclear recovery, conditioning, packaging, and continuous deep disposal are Core Phase 2 requirements by first corresponding output under ADR-0066/0068; later specialist recovery machines are not their sole implementation. Exact entity/family split and tiers remain open.

| Machine Name | Tier/Phase | Build Materials by Tier | Capability Change Per Tier |
|-------------|-----------|------------------------|---------------------------|
| **Tailings Re-Processing Unit** (MTier 1–3) | Phases 2–3 | T1: Steel vessel + basic magnetic separator (copper-wire electromagnet). Recovers only strongly magnetic minerals (iron traces — negligible value). T2: Stainless steel processing chamber + chrome-alloy separation media + precision sensor array (silicon-based) for mineral detection. Recovers weakly magnetic and paramagnetic minerals. T3: Niobium-microalloyed pressure vessel + tantalum-bearing grinding media + semiconductor-grade spectral analysis sensor | T1 recovers only iron traces — economically useless but mechanically functional. T2 adds *paramagnetic recovery* — can extract chromium, manganese, cobalt from processed tailings (meaningful secondary income). T3 adds *spectral identification*: automatically classifies remaining mineral content and optimizes separation parameters — the tier where circular economy becomes genuinely profitable |
| **Waste-to-Fuel Converter / Incinerator** (MTier 1–3) | Phase 2+ | T1: Steel vessel + basic refractory lining (alumina/silica brick). Low-temperature combustion only. Produces producer gas with particulate content — requires "gas filter" item per 20 output cycles for clean output. T2: Chrome-molybdenum pressure shell + catalytic converter insert (Pt-group supported on alumina substrate) for complete gasification. High-temperature conversion (>900°C). T3: Niobium-microalloyed reaction chamber + refractory ceramic insulation + automated ash removal system | T1 is *fully auto-running* but requires parallel filter-production to maintain gas quality — the player must invest in infrastructure to keep this machine fed. T2 achieves *complete gasification*: all organic waste fully converts to clean producer gas (CO + H₂) with no residual solids. T3 adds *automated maintenance*: self-cleaning refractory and automated ash removal — essential for continuous operation |
| **Metal Recovery / Solvent Extraction Circuit** | Phase 3 | Single-tier capability: PTFE-lined stainless vessel + activated carbon filter beds (from coal/graphite) + ion-exchange resin + precision pump. Recovers dissolved noble/catalyst metals from process effluent. Gold, silver, platinum-group. | No tier progression — this is a *specialist* facility that should be built once per factory network. Capability scales with the size of activated carbon inventory and flow rate |
| **Sludge Dewatering & Stabilization Unit** (MTier 1–2) | Phases 2–3 | T1: Steel centrifuge bowl + rubber seals + steel frame. Basic mechanical dewatering only. T2: Stainless steel bowl + nickel-alloy drive mechanism + PTFE sealing. High-speed spin with chemical flocculant injection capability | T1 mechanically removes bulk water from sludge — output is still wet paste that must be dried or processed further. T2 adds *chemical stabilization*: injects flocculant to bind fine particles, producing a dry cake with candidate fuel-conversion or other handling paths. Ordinary solid outputs still require a consumer, recovery path, bounded buffer, or production control; this is not a radioactive-waste voider. |
| **Nuclear Fuel Reprocessing / Recovery Capability** | Phase 2 by first spent-fuel output; entity split open | Phase 2-compatible containment and process equipment with ordinary-shielding startup. Integration with other nuclear equipment versus separate entities remains open; a Phase 3 Metal Recovery Circuit is not the exclusive implementation | Separate uranium and thorium/U-233 recovery interfaces under ADR-0066; return qualified materials/reagents to their selected routes and retain radioactive rejects for conditioning |
| **Nuclear-Solid Conditioning / Packaging Capability** | Phase 2 by first residual or surplus-depleted-oxide output; entity split open | Suitable matrix preparation, sealing, and shielded package fabrication; exact construction remains open. Ordinary shielding is always available, with stabilized depleted-oxide shielding as an alternative | Powered/material-consuming immobilization and packaging under ADR-0068 after required recovery; no direct spent-rod or untreated-effluent deletion and no ongoing uranium requirement for thorium packaging |
| **Nuclear Deep-Disposal Plant** | Phase 2 by first conditioned-package output; exact equipment split open | Continuous treatment/disposal with construction and operating costs, including power and conditioning/packaging materials; exact build, throughput, and inputs remain open | No tracked lifetime storage cap or permanent-cell expansion under ADR-0068. Throughput limits operation; slight operating pollution represents abstracted underground leakage. Loss of power/materials pauses processing, without a new permanent containment-power or blackout-failure loop. Not a generic solid voider |

**Tiering principle:** Candidate tailings-recovery tiers may improve recovery quality and selectivity. This does not postpone the selected Phase 2 nuclear back end or make its baseline deliberately unusable. Nuclear capability rows do not establish final machine-family, entity, tier, or product counts.

## 17. Research & Measurement Infrastructure (Phase 2+)

The six domain facilities produce research packs using the one-to-one bridge mappings in [Research and Progression](research-progression.md#candidate-domain-science-pack-design). The T1/T2 rows below are candidate equipment configurations, not approved facility bills, research-pack tiers, or additional bridge requirements.

| Machine Name | Tier/Phase | Build Materials (per tier) | Capability Change |
|-------------|-----------|---------------------------|-------------------|
| **Superconductivity Research Lab** | Phase 2 | T1: steel frame + copper coils + rubber seals | Magnetic field strength, sample temperature range; selected bridge: electronic-grade polysilicon |
| | | T2: stainless steel frame + Nb₃Sn wire + tantalum shielding | Higher critical current domain packs; wider temp range |
| **Plasma Confinement Facility** | Phase 2 | T1: steel vessel + copper magnets + ceramic liner | Max plasma temp, confinement time, measurement precision; selected bridge: Nb₃Sn wire |
| | | T2: nickel-alloy vessel + Nb₃Sn wire coils + beryllia liner | Higher field strengths; more diagnostics channels |
| **Nanofabrication Laboratory** | Phase 2 | T1: steel cleanroom frame + copper HVAC + glass panels | Particle count tolerance, deposition precision, sample size; selected bridge: HfO₂ dielectric |
| | | T2: stainless structure + HfO₂-coated surfaces + filtered air | Sub-micron feature resolution; multi-layer processing |
| **Isotope Separation & Calibration Lab** | Phase 2 | T1: steel separators + copper sensors + rubber gaskets | Isotope resolution, separation efficiency, sample throughput; selected bridge: D₂O |
| | | T2: corrosion-resistant alloy + D₂O cooling + tantalum shielding | Higher mass resolution; enriched isotope production |
| **Reaction Dynamics Facility** | Phase 2 | T1: steel pressure chamber + nickel alloys + graphite seals | Max pressure/temperature, catalyst compatibility range; selected bridge: rhenium-catalyst powder |
| | | T2: rhenium-clad internals + high-temp alloys + inert sealing | Higher temp operations; exotic catalyst testing |
| **Quantum States Laboratory** | Phase 2 | T1: steel cryostat + copper thermal links + glass viewport | Base temperature (K range), measurement sensitivity; selected bridge: cryogenic argon/nitrogen mixture |
| | | T2: multi-layer insulation + superconducting shields + mK temps | Quantum coherence measurement; crystalline structure analysis |
| **Planetary Simulation Core — Thermal Frame** | Phase 3+ | T1: steel frame + copper thermal links | Max simulation resolution, thermal model fidelity |
| | | T2: high-temp alloy frame + tungsten thermal paths | Higher temp range in simulation |
| **Planetary Simulation Core — Computation Cluster** | First Core at the Phase 2/3 transition; later upgrades open | Initial computation uses conventional CPU-grade packaged processors, with supporting components open | Compute nodes and memory bandwidth; Josephson/SFQ computation is a later post-activation upgrade |
| | | T2: semiconductor-grade silicon + Nb₃Sn optical interconnects | Exponential compute increase; distributed processing |
| **Planetary Simulation Core — Integration Bus** | Phase 3+ | T1: copper bus + ceramic insulators + steel connectors | I/O channels, data throughput to/from facilities |
| | | T2: semiconductor-grade materials + fiber optics | Higher channel count; faster domain dataset transfer |
| **Planetary Simulation Core — Calibration Reference Frame** | First Core at the Phase 2/3 transition; later upgrades open | Invar iron-nickel frame with mechanical fine adjustment and the Unified Metrology Reference Array; other inputs open | Phase 2-compatible non-semiconductor alignment under ADR-0076; later interferometry remains a candidate |
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

This table preserves source-proposed category entry estimates and tier examples for reference only. They are not normalized totals or approved tier rosters: entries mix families, support capabilities, components, and variants. Use the family register and independent counting boundary above instead.

| Category | Candidate Entries (Provisional) | Tiered? | Key Tiers That Change Capability |
|----------|------------------|---------|---------------------------------|
| Extraction & Mining | 6 source entries | Candidate, family-specific | Electric drill and underground extractor are distinct from transport belts; scanner/deep-access gates remain open |
| Ore Preparation & Concentration | 13 listed machine entries | Partial (ball mill, magnetic drum, flotation bank) | Ball mill MT2–4 for throughput/media auto-replenishment; magnetic drum tier = field strength |
| Thermal Processing | 7 | Yes (roaster, kiln, sintering, pellet press) | Roaster tier = gas capture efficiency; kiln/sinter tier = temp control precision |
| Smelting & Reduction | 7 | Yes (EAF multi-tier primary) | EAF MT1–4: voltage, electrode auto-feed, power range |
| Chemical Extraction & Reactors | 6 | Partial (pressure leach, general reactor) | Pressure leach tier = pressure rating; reactor tier = material compatibility range + control precision |
| Solution Processing & Separation | 6 | Partial (crystallizer, filter press) | Crystallizer MT1–3: cooling → evaporator → vacuum auto-discharge |
| Electrochemical Processing | 4 | Yes (electrowinning, chlor-alkali) | Electrowinning MT1–3 = electrode area + auto-cathode swapping; membrane cell MT2+ = membrane quality |
| Polymer Chemistry & Primary Processing | ~6 candidate families | Partial (polymerization reactor) | Polymerization: batch → continuous → auto-controlled at high tiers |
| Semiconductor Fabrication | 12 | Candidate, family-specific | Precision and cleanroom capability may vary by family; tiers and gates remain open |
| Nuclear Fuel & Component Fabrication | 13 | Candidate, family-specific | Normally automated Phase 2 fuel handling is required; later variants and entity splits remain open |
| Power Generation (core mod) | Candidate families; count TBD | Tiering is family-specific | Boiler/steam engine untiered; Phase 2 fission with steam turbines; Phase 3/4 route identities selected, with non-steam conversion families as recorded in Power System |
| Core Power Pole Distribution | Vanilla network plus tiered pole variants (count TBD) | Yes; details TBD | Compatible pole progression; custom voltage and transmission losses remain outside the accepted core scope |
| Energy Storage | Candidate families; count TBD | Family-specific; tiering open | Phase 2 LFP battery chemistry is selected; other storage options remain candidates and the dedicated safety device is not selected |
| Custom Power Transmission & Grid Stabilization (extension) | Extension reference inventory; count not normalized | Deferred from core | Custom voltage, conductor, transformer, and stabilization candidates remain separate from core poles |
| Military Infrastructure (placeables only) | 6 selected Core turret families: 4 base-game + plasma and railgun; support entries may reuse other families | Family-specific; exact tiers open | Rocket turret is not selected for Core; historical plasma/railgun descriptions are aliases, not additional families |
| Logistics & Material Handling | ~10 source entries + infrastructure (provisional) | Candidate, family-specific | Speed-only variants do not establish a new capability tier; normal automated stations do not require a freight terminal |
| Fluid Handling & Transport | 6 types | Partial (pipes, heat exchanger multi-tier) | Pipe network tiers most important for pressure/temperature tolerance across distances |
| Rubber Processing, Polymer Forming & Composite Fabrication | ~6 candidate families | Partial (mill, sheet forming, layup station) | Rubber compounding and composite-forming capability changes |
| Waste Processing & Loopback | 4 types | Candidate, family-specific | Recovery improvements may justify tiers; required Phase 2 nuclear handling does not depend on later upgrades |
| Research & Measurement Infrastructure | ~10 facilities; component count not normalized | Partial (Core satellites scale capacity) | Core L2/L3 are upgrades, not tiers per se; satellites tier by processing/storage capacity |
| Automation & Control Systems | 5 types | Yes (PLC multi-tier primary) | PLC MT1–3: timer → PID → neural-assisted optimization |

**Count and ownership notes:** Category 2 has 13 listed entries (6 preparation, 5 density/magnetic separation, and 2 flotation). The five ammunition products in section 12.B are excluded from infrastructure counts. The former power aggregate of 20 (14 generators plus 6 transmission entries) mixed core and extension scope; the transmission count remains provisional and is not a core-mod total.

## Design Gate

A machine or variant should be approved only when its operation, input/output contract, progression role, and downstream product use are clear. A new machine family should correspond to a real process capability or a strong gameplay distinction, not simply a desire to give every reaction its own building. A newly required progression tier must change capability; a speed-only variant is not itself a new capability tier under ADR-0075.

## Open Design Decisions

- Which operations reuse vanilla machines, and which require new or modified families?
- Should chemical reactors be one configurable family or a small number of process-specific families?
- Which routes need multiblock or high-throughput equipment, and which should scale with ordinary machines?
- Which routes require catalyst slots, pressure or temperature constraints, or maintenance? Route-specific requirements belong with the mineral and chemical process owners.
- What is the smallest useful PLC and sensor/actuator set, and which controls remain optional? Basic process balance must not depend on custom code.
- What must the handbook and machine UI expose for recipe eligibility, inputs, outputs, coproducts, catalysts, and research requirements? What baseline diagnostics cover status, throughput, power draw, and blocked outputs?
- The archived route-to-machine matrix was empty. Populate exact assignments only after the relevant product and process routes are approved.

---

## High-Level Construction Demand and Supply Status

This is a material-family demand map, not a Phase 5 coverage proof or a construction bill of materials. **Selected** identifies a capability or material family accepted in an ADR; **candidate** identifies a possible use or feed without approving it. A named deposit is not a demonstrated extraction, refining, fabrication, or research path. Phase 5 must close the gaps before catalog freeze; quantities and recipes remain in Phases 6-7.

| Material / product family | Intended constructable or capability use | Upstream source or explicit gap |
|---|---|---|
| Iron, carbon and structural steel | Core machines, frames, rail, poles, and ordinary tooling; specific build inputs open | Hematite/magnetite and coal/graphite are candidate feeds in [Minerals and Refining](minerals-and-refining.md); Phase 1 ironmaking and basic refractory paths need verification. |
| Iron-nickel Invar and precision mechanical parts | **Selected:** first-Core alignment frame and mechanical adjustment | Iron and nickel must be accessible pre-Core; hematite and pentlandite are candidate feeds, not selected sources or starting-area guarantees. **Gap:** nickel recovery, alloying, mechanical fabrication, access, and exact item form must be demonstrated under ADR-0076. |
| Copper and electrical conductors | Core motors, wiring, electrical grid, rail supply, and CPU interconnects | Malachite, chalcopyrite, or pentlandite are eligible CPU copper feeds under ADR-0029; one copper feed is available in the starting region. **Gap:** establish a suitable Phase 2 CPU refining path without relying solely on the Phase 3 electrorefiner candidate; constructable grades remain open. |
| Chromium/nickel stainless and corrosion-resistant alloys | Candidate chemical vessels, fluid equipment, and thermal structures | Chromite and pentlandite are candidate feeds; recovery and alloying are open. Service compatibility is not established by the word “stainless.” |
| Manganese, vanadium, molybdenum and tool/alloy steels | Candidate wear surfaces, structural alloys, and processing tools | Pyrolusite/hematite, magnetite/ilmenite, and molybdenite/scheelite are respective feed candidates. **Gap:** routes, grades, and actual construction uses are not selected. |
| Cobalt and magnesium | Candidate high-temperature alloys, battery variants, light alloys and chemical reagents | Pentlandite/malachite and dolomite/chromite are respective feed candidates. **Gap:** recovery and final uses remain open; neither cobalt nor nickel is required for initial LFP chemistry. |
| Refractory brick, silica/glass and ceramics | Furnaces, chemical service, optics, and insulators; product-specific material choices open | Quartz/silica, clay-like/basic refractory materials, and calcite are candidate sources. **Gap:** establish Phase 1 refractory without bauxite-derived alumina; bauxite-derived alumina/aluminum starts in Phase 2 under ADR-0021. |
| Diamond and silicon-carbide abrasives | Candidate wafer cutters, polishing and precision tooling | Synthetic diamond and silicon carbide from carbon/silica are possible concepts, not selected routes. **Gap:** source, fabrication, equipment eligibility, and whether either is required remain open. |
| Aluminum/alumina | Candidate Phase 2+ ceramics, PV supports, heat exchangers, and packaging | Bauxite is a candidate feed; Bayer/electrolytic production is a process candidate. No Phase 1 bauxite-alumina construction input is permitted. |
| Metallurgical silicon and electronic-grade polysilicon | **Selected:** Phase 2 silicon precursor bridge and standard CPU chain; a separate Phase 2 PV route | Quartz -> Phase 2 submerged-arc reduction -> trichlorosilane purification/deposition is selected for the electronic precursor; exact feed preparation, reagents, grades and PV-specific processing remain open. |
| Hafnium/HfO₂ and zirconium alloy | **Selected:** CPU dielectric, nanofabrication bridge, Phase 2 hafnium absorber capability, and fission cladding | Shared early/mid-Phase-2 zircon access and a distinct Zr/Hf separation stage are selected. **Gap:** separation chemistry, metal preparation, absorber/tube forming, independent demand, and material balances remain open. |
| Tantalum/TaN | **Selected:** standard CPU interconnect material; candidate capacitors, bearings and vessel parts | Columbite-tantalite is the selected CPU feed with early/mid-Phase-2 access. **Gap:** recovery, TaN/capacitor fabrication and candidate non-CPU uses remain open. |
| Niobium, tin, Nb₃Sn and NbTi | **Selected:** Nb₃Sn Plasma Confinement bridge; candidate magnets, coils, and other equipment | Columbite-tantalite and cassiterite are selected niobium/tin feeds by first bridge use. Wire fabrication, shared demand, and NbTi's titanium and processing path remain open; the additional machine uses are not requirements. |
| Rhenium | **Selected:** Reaction Dynamics bridge catalyst; candidate high-temperature alloys and fusion parts | Rhenium-bearing molybdenite is selected by first bridge use without a starting-region guarantee. **Gap:** recovery, catalyst fabrication, coproduct handling, and any extra alloy use remain open. |
| Tungsten and tungsten carbide | Candidate wear tooling, refractory parts, and Tokamak plasma-facing components | Scheelite is a candidate tungsten feed; carbon is a candidate carbide input. **Gap:** recovery, forming/sintering, and Phase 3-compatible fusion construction are not proven; Phase 4 tile presses cannot be the first path. |
| Titanium and titanium alloys | Candidate chemical/thermal equipment, heat exchangers, magnets and structures | Ilmenite/rutile-bearing deposits are candidates; titanium reduction, alloying, and uses require validation. |
| Lead, zinc, silver and gold | Candidate electrochemical electrodes, ammunition, contacts and chip packaging | Galena, sphalerite, and native gold are candidate feeds. Metal recovery and which contacts, electrodes, or packages are actually required remain open. |
| Platinum-group metals | Candidate catalysts, coatings, and reaction hardware | Cooperite-bearing or associated platinum-group minerals are candidates. **Gap:** viable extraction, refining, catalyst preparation, and actual equipment demand are unverified. |
| Lithium and phosphate | **Selected:** Phase 2 LFP storage; lithium blanket/fusion materials also have an intended Phase 3 role | Lithium-bearing brine and apatite-rich phosphorite are starting-region feeds under ADR-0040; spodumene is an alternative. **Gap:** Phase 2 recovery and suitable cell materials cannot depend solely on a Phase 3 crystallizer candidate; cell/blanket fabrication and usable quantities remain open. |
| Boron and beryllium | Candidate glass/ceramic additives, alternative absorber, reflector, or fusion multiplier | Borax/borate and beryl are candidate feeds. These are not universal first-fission requirements; recovery, specific use, and phase remain open. |
| Water, air, deuterium and cryogenic gases | **Selected:** D₂O and cryogenic Ar/N₂ domain bridges; candidate cooling and fusion support | Water/brine and air are possible sources. **Gap:** pre-Core isotope enrichment and gas separation paths and coproduct handling must be demonstrated; exact methods remain open. |
| Tritium and fusion fuel | **Selected:** Phase 3 D-T Tokamak route with lithium breeding | Deuterium/water and lithium feeds are intended upstream inputs. **Gap:** a first-tritium/startup supply and viable breeding/recovery loop are not selected; a reactor cannot be assumed to breed its own initial fuel. |
| Uranium, thorium and fluorine | **Selected:** optional Phase 2 uranium and thorium fission routes and PTFE fluorine startup | Uraninite, monazite and fluorspar are selected feed families with their respective access deadlines; uranium uses the UF6/centrifuge/UO₂ sequence, thorium a separate oxide seed-and-blanket. Recovery, conditioning, and detailed chemistry remain open. Neither fission route is a first-Core prerequisite. |
| PTFE, rubber, plastics and composite binders | **Selected:** Phase 2 PTFE construction-product capability; other seals, belts and casings are candidates | Fluorspar and Phase 2 chemical/petrochemical feeds supply a PTFE-free monomer/polymerization path. First press and thermal finishing use non-PTFE equipment under ADR-0078. **Gap:** establish any required early rubber without making its first source depend on rubber-built equipment; oil/coal and other elastomer/resin routes, compatibility, and exact forms remain open. |
| Sulfur and organic/biofeedstocks | Candidate acids, fuels, resins, solvents and military chemical inputs | Native sulfur, sulfide ores, crude oil, coal and biomass are source candidates. **Gap:** extraction and chemical routes remain open; tropical plants or a new agriculture system are not mandatory sources. |
| Sodium, potassium, chlorine, acids and industrial gases | **Selected:** chlor-alkali coproducts supply HCl startup; other fluid, storage, and reagent uses are candidates | Salt/brine is reachable by early Phase 2; water, air and evaporite feeds are candidates. **Gap:** coproduct balances, reagent grades, and any nitrate-salt thermal storage formula remain open. |
| Packaged CPUs, memory and electronics | **Selected:** conventional packaged CPUs supply the first-Core Computation Cluster; other electronics and later superconducting compute are candidates | The standard CPU chain requires silicon wafers, lithography chemistry, HfO₂, Cu/TaN and packaging materials; quartz, zircon, columbite-tantalite and an eligible copper feed are selected. **Gap:** complete equipment, lithography/package inputs, assembly and acyclic vacuum bootstrap require Phase 5 verification. |
| Domain bridges and Array support | Six selected bridge materials enable the six Phase 2 domain facilities; the physical Array is required before first Core | See [Intermediate Products](intermediate-products.md#research-facility-prerequisite-materials) for selected bridges. **Gap:** exact Array materials and a pre-Core neutron-reference source remain open; enriched fission fuel is prohibited and domain packs are not physical ingredients. |
| Cooling fluids, CO₂, organic working fluids and thermal-storage media | Selected later Brayton/ORC conversion families and CSP storage; exact construction and media are open | Water/air, carbonate sources, brine/evaporites and hydrocarbons are candidates. **Gap:** compatible material and fluid routes, converter equipment and balances need validation; do not assume steam turbines after Phase 2. |
| Gallium, germanium, indium, cadmium, selenium, tellurium and arsenic | Candidate advanced PV/TPV materials and electronics | Bauxite, coal, sphalerite, native gold, arsenopyrite and refining residues are candidate sources where appropriate. **Gap:** element-specific recovery and selected consumers are unverified; none is automatically required for the initial Phase 2 PV or Hawking TPV construction. |
| Yttrium, cerium, lanthanum and other rare earths | Candidate superconducting, optical and catalyst uses | Monazite/bastnaesite and related concentrates are candidates. **Gap:** separation, usable product forms, and actual consumers remain open. |
| Neutron-reference material and noble gases | Candidate Array instrumentation, leak testing, and specialized measurement | **Gap:** neither the reference material nor its supply is selected; any reference must be pre-Core and not require enriched fission fuel. Noble-gas acquisition, including any helium supply, and specific uses remain open. |
| Ordinary and nuclear waste-handling materials | Powered gas/fluid release; nuclear recovery, conditioning, packaging and continuous disposal by first output | Process coproducts and spent fuel supply the streams; ordinary shielding must bootstrap packaging. **Gap:** exact conditioning matrices, operating materials, facilities, rates, and independent-demand handling remain open. |

## Construction Materials Index — Per-Category Candidate Uses

The following source details preserve possible roles and material associations for each category. Every “materials consumed,” “first consumer,” tier number, quantity, and category count in these tables is an **unverified hypothesis**, not proof of an approved requirement or a viable route. The demand map above gives selected boundaries and gaps; a proposed material earns a final catalog entry only through a validated use or terminal role.

### Category 1 — Extraction & Mining (~6 buildings)

| Building | MTier 1 / T1 Materials | MTier 2+ / T2+ Materials | Late-Game Tier Materials |
|---|---|---|---|
| Electric Mining Drill | Steel plates (structural frame), copper wire (motors/wiring), iron gears, basic rubber (belts/seals) | Stainless steel housing (corrosion resistance), niobium-microalloyed steel plate (load-bearing frame at MTier 3+), tantalum capacitors (control circuitry) | Titanium-alloy reinforced drill head, tungsten-carbide cutting teeth, ceramic bearing inserts |
| Underground Deposit Extractor | Steel pipe + iron plates (extractor mechanism), basic rubber | Stainless steel (corrosive environments), plastic stacks | — |
| Deep Borehole Drill | Steel frame, copper motor winding | Tungsten-reinforced drilling bit, high-strength alloy housing | Vacuum-sealed drill head components (cryogenic insulation) |
| Open-Pit Excavator | Massive steel frame (~50× steel plates), hydraulic piston assemblies (stainless steel cylinders) | Niobium-microalloyed structural plate (higher load capacity), advanced sealing gaskets (FKM/cryogenic rubber) | — |

**Materials consumed:** Steel, stainless steel, niobium microalloy, copper, tungsten carbide, titanium alloy, tantalum capacitors, basic plastics, FKM rubber. ~9 materials from the catalog.

### Category 2 — Ore Preparation & Concentration (~13 listed machine entries)

| Building | Materials per Tier | Notes |
|---|---|---|
| Jaw Crusher (MTier 1–3) | T1: steel plates + iron shaft + basic bearings. T2: tungsten-carbide jaw plates. T3: refractory steel housing + ceramic bearing upgrades | Tungsten only enters at MTier 2+ via carbide teeth |
| Ball/Rod Mill (MTier 2–4) | T1: steel cylinder lining + cast iron grinding media auto-replenish. T2: tungsten-carbide liner inserts. T3: niobium-microalloyed pressure vessel + ceramic seals. T4: titanium-alloy rotating assembly with automatic media feed | MTier 4 is the only tier that introduces a completely different material class (Ti alloy for light-weight high-speed) |
| Magnetic Drum Separator (MTier 1–3) | T1: basic electromagnet + steel housing. T2: superconducting magnet winding (NbTi wire, limited early phase). T3: cryogenic cooling jacket + HfO₂ dielectric insulation | Candidate NbTi use; tier materials, timing, and any early source path remain unverified |
| Flotation Cells (Rougher/Cleaner) | Rubber impeller/rotor, polyurethane liner plates, steel vessel frame, PVC pipe for reagent feed | Primarily polymer + basic metal consumption |
| Spiral Concentrator / Jigging Machine | Steel frame, chrome-plated separation surfaces | Chrome from chromite — early infrastructure link to alloy steelmaking |
| Electrostatic Separator (Phase 3) | HfO₂ high-voltage insulator panels, precision ceramic feedthroughs, mu-metal shielding plates | Uses hafnium-oxide dielectric and niobium-tin wiring |

**Candidate material mentions:** Steel grades, tungsten carbide, NbTi or niobium-tin wire, chrome alloy, HfO₂ dielectric, and tantalum capacitors. The claimed first superconducting consumer and the approximate count are unverified.

### Category 3 — Thermal Processing (~7 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| Roaster (MTier 1–3) | T1: basic steel refractory + chrome-alloy hearth. T2: nickel-alloy hot gas ducts (corrosion resistant). T3: high-grade refractory steel + catalytic converter insert for off-gas treatment | Pentlandite is a candidate nickel feed; recovery, timing, and this alloy use remain open |
| Rotary Kiln (MTier 2–3) | Steel shell, chrome-molybdenum refractory lining, graphite electrode support frame | Scheelite-associated molybdenite is a candidate feed; recovery is open |
| Sintering Machine | High-temp steel mesh, refractory brick (aluminum oxide + silica composite), cooling water jacket (copper tubing) | Aluminum oxide ceramics and copper heat transfer |
| Pellet Press / Briquette Machine | Tungsten-carbide dies at MTier 3+ | First infrastructure link to tungsten tooling |

**Materials consumed:** Steel, nickel alloy, chrome-molybdenum alloy, aluminum oxide ceramics, copper tubing, tungsten carbide. ~6 materials. **Petroleum coke and coal serve as fuels, not construction materials.**

### Category 4 — Smelting & Reduction (~7 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| EAF (MTier 1–4) | T1: basic steel vessel + graphite electrodes. T2: nickel-alloy electrode holders. T3: niobium-microalloyed pressure vessel + refractory brick lining (alumina/silica composite). T4: vacuum-induction capability (requires HfO₂ insulation + tungsten-heated coils) | Each tier adds a new material class — this is the most tier-rich machine in the catalog |
| Blast Furnace (MTier 1–3 candidate) | Phase 1: basic non-bauxite-alumina refractory; later candidate steel shell, chrome-alloy hearth and alumina/silica lining | Alumina from bauxite is Phase 2 or later; exact furnace material and chrome source remain open |
| Converter (BOF/LD) | Nickel-chrome alloy refractory lining, graphite nozzle inserts | Links to steelmaking (chromium + nickel consumption) |
| Induction Melting Furnace (Phase 3+) | HfO₂ crucible liner, tungsten heating element, niobium-microalloyed pressure chamber (refractory-lined electromagnetic induction vessel) | Candidate high-purity alloy processing, including an enclosed-vacuum configuration; no global ambient-pressure mechanic is implied. Materials, source paths, and entity split remain open. |

**Candidate material mentions:** Steel grades, nickel alloy, chrome alloy, graphite, alumina ceramics, HfO₂ dielectric, tungsten carbide, and niobium microalloy. Their count and any claim that the VIM furnace is the first bridge-material consumer remain unverified.

### Category 5 — Chemical Extraction & Reactors (~6 buildings)

| Building | Materials per Tier | Notes |
|---|---|---|
| Pressure Leach Autoclave (MTier 1–3) | T1: basic steel + rubber lining (chemical resistant). T2: stainless steel 316L vessel (chloride-resistant grade) + PTFE gaskets. T3: niobium-microalloyed pressure shell + tantalum-clad internals | Candidate stainless-steel use; service compatibility and each family's materials remain open |
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
| Cracking Furnace (MTier 1–3) | High-temp alloy vessel, nickel-based catalyst bed housing, refractory insulation | Pentlandite is a candidate nickel feed; recovery remains open |
| Polymerization Reactor | Baseline compatible metal vessel and non-PTFE seals; PTFE lining only in later variants | Phase 2 first PTFE under ADR-0064, with PTFE-free upstream and construction-product finishing |
| Injection Molding Press | Chrome-molybdenum barrel, hardened steel mold inserts, tungsten-carbide guide pins | **Another tungsten link: tooling durability** |

**Materials consumed:** Nickel alloy, chrome-molybdenum alloy, PTFE plastics. ~3 materials. **Primarily polymer consumption — infrastructure needs the chemicals it processes.**

### Category 9 — Semiconductor Fabrication Chain (~12 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Czochralski Crystal Grower | High-purity graphite crucible (from purified graphite), alumina/silica thermal insulation, NbTi temperature control wiring | Phase 2 contemporary wafer growth for the CPU line; any post-Core upgrade must exceed current-day capability |
| Wafer Saw | Diamond blade segments, silicon carbide guide rails | Phase 2 contemporary wafer preparation for the CPU line; any post-Core upgrade must exceed current-day capability |
| CVD/PVD Chamber | Niobium-microalloyed wall panels (corrosion resistance to process gases), HfO₂ dielectric windows, tantalum target material for sputtering | Phase 2 baseline and contemporary advanced deposition; beyond-current-day processes, if selected, are post-Core |
| Photolithography Stepper | Candidate polysilicon lens elements, precision ceramic stages (alumina), and Nb₃Sn motor windings for vibration isolation; the proposed silicon UV-optics suitability is unverified | Phase 2 current-day patterning capability; exact optical materials and tool design remain open |
| Cleanroom Enclosure | HfO₂ particulate filtration panels, fluoropolymer duct lining, niobium-microalloyed structural frame | Phase 2 full contemporary cleanroom capability; exact module tiers open |
| Packaging Line | Copper lead frames (from refined copper), gold bonding wire (from native gold processing), plastic/molded ceramic packages | Phase 2 contemporary CPU and advanced packaging capability; exact options open |

**Candidate material groups:** Graphite (purified), alumina ceramics, NbTi/Nb₃Sn wiring, HfO₂ dielectric, niobium microalloy, tantalum, electronic-grade polysilicon, gold, and copper (~9 candidate groups; not a validated or complete bill of materials). The chain has selected Phase 2 material demand under [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md); demand volumes, grades, and construction allocations remain to be validated.

Under [ADR-0027](adrs/ADR-0027-phase-2-contemporary-chipmaking-material-stack.md), the required Phase 2 production-material families are silicon wafers, lithography chemistry, HfO₂ dielectric, Cu/TaN interconnect, and package materials. All five are required by the standard late-Phase-2 CPU path for initial Core supply under [ADR-0028](adrs/ADR-0028-phase-2-core-cpu-material-dependencies.md); mineral feed-family assignments for silicon, hafnium, tantalum, and copper are selected under [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md). The candidate facility/build materials above are not a complete or accepted bill of materials; exact grades, processing routes, equipment allocation, and quantities remain open.

Conventional CPU-grade packaged processors are available by late Phase 2 under [ADR-0025](adrs/ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md). Full contemporary cleanroom and advanced chipmaking capability belongs in Phase 2 under [ADR-0026](adrs/ADR-0026-phase-2-contemporary-semiconductor-capability.md); post-Core progression is primarily for capabilities beyond current-day industry. Exact semiconductor routes, machine tiers, material grades, construction materials, recipes, and research gates remain open. Phase 3 basic-PV cell capability remains a later upgrade route; the initial Phase 2 crystalline-silicon platform is selected under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md), while its grade, process steps, and equipment remain open.

### Category 10 — Nuclear Fuel & Component Fabrication (~13 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Uranium Conversion Line | Candidate service-compatible metal vessels, PTFE seals/linings, graphite/refractory parts; compatibility must follow chemistry | Phase 2 front end under ADR-0048, with independent PTFE startup under ADR-0064; shared-chain thorium seed, separate tails deconversion, qualified recovered-uranium return, and fluorine conditioning from both UF6 branches under ADR-0066. Detailed chemistry, equipment split, seed preparation, and numerical balances remain open |
| Cladding Tube Mill | Zirconium-alloy cladding stock and forming tools; exact materials remain open | Phase 2 minimum capability for both fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); alloy family and shared early/mid-Phase-2 zircon access are selected under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md), and a distinct Zr/Hf separation stage is required under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md). Feed recovery/conversion, separation chemistry, alloying, quantities, and build details remain open |
| Fuel Rod Assembly Line | Candidate fixtures and sealing components; detailed materials remain open | Normally item-fed Phase 2 baseline under ADR-0043/0065; later handling/inspection upgrades remain candidates |
| Hafnium Absorber Plate Liner | Phase 2-compatible forming equipment/tooling; suitable hafnium metal from the shared Zr/Hf path | Phase 2 baseline before first fission under ADR-0065; Phase 3 precision upgrades are optional candidates |
| Superconducting Coil Winder | NbTi/Nb₃Sn wire (direct consumption), HfO₂ insulation layers, aluminum formers | Phase 3–4 |
| Precision Optics Station | Electronic-grade polysilicon substrate blanks (for optical test equipment) | Phase 4 |
| Tungsten Armor Tile Molder | Tungsten powder + rhenium additive (0.5% Re improves W ductility at high temp), graphite mold inserts | Phase 4+ |

**Materials consumed:** Stainless steel, zirconium, hafnium, Nb₃Sn wire, HfO₂ dielectric, polysilicon, tungsten, rhenium, graphite. ~9 materials. **Fusion infrastructure is a direct consumer of bridge products + tungsten.**

### Category 11 — Power and Distribution Infrastructure

| Generator / Constructable Type | T1 Materials | Mid-Phase Materials | Late-Phase Materials |
|---|---|---|---|
| Boiler (vanilla retained) | Burner-item fuel and water produce steam | No Prometheus tier progression selected | — |
| Steam Engine (vanilla retained; untiered) | Consumes boiler steam | No Prometheus tier progression selected | — |
| Steam Turbine (vanilla retained through Phase 2) | Converts high-temperature fission steam | Retire after Phase 2 | — |
| Solar Panel Array (MTier 1–3 candidate) | Phase 2 introduction; later tiers and phase gates remain open | T1: steel frame, glass surface, basic conductors, and crystalline-silicon cells from a dedicated PV route based on the selected Phase 2 silicon supply direction; exact grade and cell processing remain open | Candidate upgrades use aluminum mounting brackets and progressively higher-purity or compound-semiconductor cells; exact materials and gates remain open. The initial route does not require CPU wafer/chip fabrication or post-Core-only capability under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md) |
| Wind Turbine (candidate; phase and scope open) | Steel tower, copper generator winding, basic bearings | Niobium-microalloyed structural plate for larger rotor blades | Titanium-alloy lightweight hub assembly |
| Fission Reactor family (Phase 2 introduction; uranium and thorium options) | Usable normally automated baseline with Phase 2 hafnium controls, required zirconium-alloy rods, suitable vessel/cooling, and ordinary-shielding construction | Later alloy, instrumentation, reflector, and coolant upgrades remain candidates. Boron carbide, beryllium, superconducting wiring, and advanced inspection are not universal first-fission inputs under ADR-0065 | Exact tier count, materials, quantities, and gates remain open |
| Fusion Tokamak (Phase 3 selected route; constructable candidate) | Nb₃Sn magnet coils (dominant material), tungsten armor tiles, lithium-beryllium breeder panel frames, cryogenic insulation layers | **Major bridge-product consumer**: source estimate is ~60 Nb₃Sn spools and ~80 W armor plates per tokamak; phase-compatible construction chain remains open   | N/A |
| Hawking Engine (Phase 4 option) | All Phase 4 materials + Core integration bus connection | See [Power System](power-system.md) and [Endgame Vision](endgame-vision.md); exact Core integration and research gate remain open | N/A |
| Tiered power poles (core) | Materials and tier details TBD | TBD | TBD |

**Materials consumed:** Steel grades, copper, aluminum, silicon, tantalum, niobium alloy, zirconium, hafnium, boron carbide, beryllium, tungsten, Nb₃Sn wire, lithium compounds. ~13 generator materials; tiered-pole material demand remains to be established. **Fission reactor alone is one of the heaviest infrastructure sinks.**

### Category 12 — Military Infrastructure (placeable defense and support systems)

| Turret/Machine | Key Materials | Phase |
|---|---|---|
| Gun Turret tiers | Steel (structural), copper wiring, lead (early), nickel alloy (MTier 3+ trigger mechanism) | Phases 1–4 |
| Laser Turret | Semiconductors (targeting module), precision optics (polysilicon lens), HfO₂ thermal management panels | Phase 2–4 |
| Flamethrower Turret | Steel body, PTFE hose lining, rubber seals, fuel storage tank (stainless steel) | Phase 2–3 |
| Artillery, plasma and railgun families | Candidate construction and ammunition/energy materials remain open | Core family scope selected; phases, tiers and exact inputs TBD |
| Rocket Turret | Candidate launcher, guidance and ammunition materials only; no enriched-uranium requirement | Not selected for Core |
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
| Centrifugal Compressor / Vacuum Pump | Phase 2-compatible pumping/compression construction and conventional controls; exact configurations open | Required semiconductor vacuum in Phase 2 under ADR-0026; later specialist upgrades optional, with no first-pump dependency on its own semiconductor output |

**Materials consumed:** Steel grades, copper, aluminum, titanium, nickel alloy, PTFE. ~6 materials. **Titanium enters via heat exchangers for corrosive brine/cooling — a natural industrial application.**

### Category 15 — Rubber Processing, Polymer Forming & Composite Fabrication (~6 candidate families)

| Building | Key Materials | Phase |
|---|---|---|
| Rubber Mill | Steel rollers, candidate rubber components and feedstock, electric motor (copper) | Phase 2 candidate; the first required rubber source and equipment cannot assume this mill's own output |
| Fiber Layup Station | Fiberglass winding equipment (ceramic guides), precision resin mixing pumps (PTFE-lined stainless) | Phase 3+ |

**Materials consumed:** Steel, rubber, ceramic guides, PTFE. ~4 materials. **Primarily polymer + steel consumption.**

### Category 16 — Waste Processing & Loopback (~4 buildings)

| Building | Key Materials | Phase |
|---|---|---|
| Tailings Re-Processing Unit | Stainless steel processing vessel, ceramic centrifuge bowls, precision sensor elements (silicon-based) | Phase 2–3 |
| Metal Recovery Circuit | Solvent extraction columns (PTFE-lined stainless), activated carbon filter beds (from coal/graphite), ion-exchange resin | Phase 3+ |
| Gas Flare Stack | Construction materials and recipe requirements remain open | Available no later than Phase 2 silicon reduction; exact gate and any earlier availability remain open |
| Liquid Effluent Clarifier | Construction materials and recipe requirements remain open | Before the first liquid-disposal use; exact phase gate open |
| Nuclear Fuel Reprocessing / Recovery Capability | Phase 2-compatible containment/process equipment; ordinary-shielding startup; entity split open | Phase 2 by first spent-fuel output under ADR-0066 |
| Nuclear-Solid Conditioning / Packaging Capability | Suitable matrix/sealing and ordinary shielding; depleted-oxide shielding is an alternative | Phase 2 by first corresponding output under ADR-0068 |
| Nuclear Deep-Disposal Plant | Powered/material-consuming continuous disposal with slight operating pollution; no tracked storage cap | Phase 2 by first conditioned package under ADR-0068; exact equipment split, throughput, inputs, and emission rate open |

**Materials consumed:** Stainless steel, ceramics, silicon sensors, PTFE, and activated carbon are recovery-route candidates; disposal-facility and nuclear-package materials remain open. Ordinary gas/fluid release follows ADR-0035; nuclear-bearing fractions require recovery/conditioning and continuous nuclear-solid disposal under ADR-0068, not direct generic disposal.

### Category 17 — Research & Measurement Infrastructure (~10 facilities)

| Building | Key Materials | Phase |
|---|---|---|
| Domain Labs (×6) | Six selected bridge materials map one-to-one to the facilities; complete bills remain open. See [Intermediate Products](intermediate-products.md#research-facility-prerequisite-materials). | Phase 2 |
| Planetary Simulation Core | See [Endgame Vision](endgame-vision.md) — Thermal Frame, Computation Cluster, Integration Bus, Calibration Frame | First Core at the Phase 2/3 transition |
| Satellite facilities (compute/memory/observation) | Packaged ICs (dominant), Nb₃Sn cable, thermal interface materials, HfO₂ panels | Phase 3 |

**Materials consumed:** Research-facility prerequisite materials (count unresolved), packaged ICs, Nb₃Sn wire, and HfO₂ dielectric. Approximately 10 candidate materials from research/endgame construction alone.

### Provisional Endgame Assembly and Facility Pathways

These are candidate construction-demand hypotheses, not approved recipes. The outputs are endgame assemblies or facilities; their item/entity classification and material demand remain for Phase 5 coverage and later catalog design.

| Candidate output | Provisional pathway | Intended role |
|---|---|---|
| Processor cluster / compute rack assembly (item/entity form unresolved) | Packaged ICs + boards + cooling and power components -> compute rack | Regional computation |
| Supercomputer facility | Compute racks + high-capacity power/cooling + network equipment -> facility | Large-scale simulation |
| Simulation cluster node | Supercomputer facility + synchronization and precision links -> network node | Distributed simulation |
| Planetary research center | Regional cluster nodes + precision optics + research infrastructure -> center | Endgame objective network |

Component quantities, satellite recipes, and mandatory Hawking Engine subcomponents are not selected; exact requirements remain open.

### Category 18 — Automation & Control Systems (~5 buildings)

| Building | Key Materials per Tier | Phase |
|---|---|---|
| PLC Controller (MTier 1–3) | T1: basic copper wiring + silicon chip controllers. T2: niobium-microalloyed shielding + tantalum capacitors. T3: packaged ICs + semiconductor-grade interconnects | Phases 2–4 |
| Precision Actuator/Servo Motor | Copper winding, tantalum bearings, precision steel gears (tool-steel from tungsten/vanadium additions) | Phase 2–3 |
| Industrial Control Network | Fiber optic cable (silica glass core), ceramic connector housings, niobium-tin signal shielding at MTier 3+ | Phases 2–4 |

**Materials consumed:** Copper, silicon chips, niobium microalloy, tantalum, tool steel, silica glass. ~6 materials. **Tantalum bearings are the subtle link — precision motors in automated plants need corrosion/erosion resistance.**

---

## Unverified Candidate Material Mentions by Category

This source summary preserves proposed material mentions and rough category tallies only. It mixes candidate, selected, and extension uses; neither its counts nor its statements establish actual consumption, production paths, or final coverage. Use the high-level demand map above for current status.

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

## Candidate Material-Use Observations

The source estimated approximately 38 infrastructure material uses from a roster of about 50 candidates. That estimate is unverified and is not a normalized count or coverage result. Material placements and source/process gaps may:
- Only apply to extension mods (e.g., advanced battery chemistries beyond Li-ion)
- Serve as bridge/recoverable trace materials with no direct infrastructure use (but still have research or chemical consumer value)
- Need a creative placement before final approval

**Key findings:**

1. **Endgame and ordinary industry may use overlapping materials.** The source's ~15 and ~40 estimates are not established consumption totals; validate actual uses rather than adding materials to meet either figure.

2. **Nb₃Sn wire has candidate infrastructure consumers beyond endgame.** Selected bridge use and candidate separator, electrochemical, cleanroom, and fusion uses must be checked against their actual construction rows. Baseline fission does not require superconducting wiring under ADR-0065; niobium-microalloyed steel is not a superconducting conductor.

3. **Stainless steel appears in several candidate applications.** Neither its category count nor a universal early requirement is validated; service compatibility varies.

4. **Tantalum has a selected CPU-interconnect role and other candidate applications:** capacitors, bearings, shielding, and vessel cladding. Their number and acceptance remain open.

5. **Semiconductor infrastructure creates material demand:** Contemporary cleanroom and chipmaking capability belongs in Phase 2. Hafnium-oxide dielectric, niobium alloys, and tungsten carbide are candidate construction materials; exact equipment materials and gates remain open.

---

## Extended Catalog: Pure-Material Infrastructure-Use Validation

The following source candidates have an open infrastructure placement or a proposed use whose source/process needs validation. Gallium and germanium appear in candidate later solar-cell concepts; beryllium is an optional reflector/multiplier candidate, not a universal fission prerequisite.

| Material | Potential Infrastructure Role or Validation Need | Validation Status |
|---|---|---|
| Gallium | Validate the source/refining path for the proposed GaAs solar-cell contacts; a separate thermometer or sensor use remains optional | Medium — candidate solar use appears in Category 11; source path unverified |
| Germanium | Validate the trace-recovery path for the proposed multijunction solar-cell use; wafer testing and fiber-optic doping remain alternatives | Medium — candidate solar use appears in Category 11; source path unverified |
| Selenium / Tellurium | Candidate photovoltaic cell variants (CdTe panels) or thermoelectric applications; selected Hawking conversion is TPV, with materials open | Candidate uses and source paths require validation |
| Yttrium | Superconducting compound additive (YBCO-type research materials) | Medium — niche but connects to superconductivity lab |
| Cerium / Lanthanum | Photocatalyst components, optical glass polishing compounds | Low-Medium — plausible but may not earn dedicated infrastructure slot |
| Phosphorus / Phosphate compounds | Required feed family for the selected Phase 2 LFP battery cathode under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md); apatite-rich phosphorite and starting-region access are selected under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md); other polymer uses remain candidates | Source and access selected; phosphate recovery and processing route remain open |
| Boron compounds (non-B₄C forms) | Glass/ceramic manufacturing; optical fiber dopant | Medium — borosilicate glass needs boron oxide precursor |
| Magnesium | Light alloy additive (Al-Mg structural plates); Kroll process reagent for titanium reduction | Medium — already used in aluminum alloys + Ti processing |
| Beryllium | Candidate neutron reflector/multiplier | Optional use and beryl recovery require validation; not required for baseline first fission |
| Vanadium | Steel alloy additive (already counted as microalloy); redox flow battery electrolyte option | Medium — redox battery is a creative energy storage path |
| Indium | Transparent conductive film precursor (ITO coating for cleanroom optics) | Low-Medium — niche but real semiconductor application |
| Cadmium | CdTe solar cell variant; neutron-absorbing compound (replaces some boron applications) | Medium — potential extension mod candidate |

Possible trace-recovery sources include coal for Ge, copper-refining residues for Te/Se, and monazite-bearing concentrates for rare-earth candidates. Actual deposit profiles, separation routes, and consumers remain unverified; no dedicated deposit or universal coproduct is implied.
