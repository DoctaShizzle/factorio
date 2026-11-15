# Power System Design

*Status: Draft — core distribution and Hawking option accepted; Phase 1/2 generation direction, Phase 2 UF6-based uranium fuel-cycle forms and Uraninite/fluorspar feed access, gas-centrifuge enrichment, fission fuel-rod requirement and distinct Zr/Hf separation-stage boundary, initial crystalline-silicon PV platform and LFP battery chemistry, Phase 2 fission-safety boundary, Core grid-diagnostics boundary, and Phase 3/4 route identities selected; detailed conversion, construction, and progression rules remain open*
*Last updated: 2026-11-15*

Related documents: [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Minerals and Refining](minerals-and-refining.md), [Infrastructure](infrastructure.md), [Endgame Vision](endgame-vision.md). Related ADRs: [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md), [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md), [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md), [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md), [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md), [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md), [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md), [ADR-0035](adrs/ADR-0035-powered-polluting-gas-fluid-disposal.md) for gas/fluid disposal power and pollution constraints, [ADR-0036](adrs/ADR-0036-phase-2-minimum-fission-fuel-path.md) and [ADR-0041](adrs/ADR-0041-phase-2-direct-use-fission-fuel.md) for superseded Phase 2 fuel boundaries, [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md) for the initial Phase 2 PV platform and fabrication boundary, [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md) for the initial Phase 2 battery chemistry, [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) for battery feed sources and starting-region access, [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md) for the uranium enrichment requirement, [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md) for the required Phase 2 rod assembly, [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md) for zirconium-alloy cladding and shared zircon access, [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) for the distinct Zr/Hf separation-stage boundary, [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) for the selected gas-centrifuge enrichment method, [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md) for the shared uranium-chain source of the thorium startup seed, [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) for the high-level UF6-based uranium fuel-cycle forms, [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) for the selected fluorspar feed and access timing, [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) for the selected Uraninite feed and access timing, [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) for the deferred numeric uranium-fuel target, [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md) for the same qualitative grade for the thorium startup seed, [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md) for required post-discharge reprocessing/recovery of spent uranium fuel, [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md) for the Core grid-diagnostics/stabilization boundary, and [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md) for the Phase 2 Core fission-safety boundary.

## Summary

This document is the current-state reference for generation routes, energy conversion, storage, fuel-density tradeoffs, and optional transmission. Detailed recipes, material quantities, performance, and progression gates remain open.

## Purpose and Boundaries

- **Core distribution (accepted):** Retain Factorio's vanilla pole grid and add compatible tiered power poles; exact pole tiers and statistics belong in [Infrastructure](infrastructure.md) and remain open.
- **Extension candidate:** A custom transmission system is outside core scope and remains an optional `power-transmission-override` proposal.
- **Progression decisions:** The phase sections below state current design; [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md) and [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) preserve the associated decision records.
- **In scope:** Candidate generator phases, fuel-density spectrum, infrastructure needs, power storage, and design questions.
- **Not specified:** Recipe ratios, exact MW/kWh values, machine consumption values, detailed fuel cycling, and electrical engineering formulas.

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
| Boiler → steam engine (vanilla-style combustion) | Burner-item fuels, including solid fuels and processed fuel items | Foundational early power path; the boiler burns fuel to make steam and the engine converts steam to electricity | Keep the steam engine untiered. Producer gas, biogas, and liquid fuels must be converted to burner items first; no direct gas- or liquid-fuel generator |

**Phase 1 design notes:**
- The core lesson of Phase 1: **fuel density matters.** Processed burner items can carry more energy per item than raw coal, teaching that *how* fuel is refined matters as much as *what* is burned.
- Pollution pressure from dirty combustion routes (unscrubbed sulfur, unfiltered off-gas) creates the first military-pressure driver — connecting power production to the military system.
- The boiler consumes burner items and produces steam; the steam engine consumes steam. Producer-gas and liquid-fuel streams remain fuel-processing outputs and must be converted to burner items before this power path. A gasifier or fuel processor is not itself a generator.
- Photovoltaic generation is not available in Phase 1. Phase 1 power remains combustion; PV and basic storage begin no earlier than Phase 2, once their material progression is available. The initial PV platform is crystalline silicon on a dedicated Phase 2 route; its silicon grade, process steps, and later efficiency upgrades remain open under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md). [Bob's Power](https://mods.factorio.com/mod/bobpower) is a precedent for tiered solar and storage; its direct fluid-burning generator path is not adopted.

### Phase 2: Fission (Mid Game)

*Requires Phase 2 Uraninite feed, conversion to uranium concentrate, UF6 conversion, gas-centrifuge enrichment and UO2 reconversion, pellet preparation, cladding, and fuel-rod assembly. The high-level chemical-form sequence is selected under [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), and Uraninite and fluorspar feed/access by the conversion unlock are selected under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) and [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md); uranium/fluorite recovery, reagent preparation, detailed chemistry, balances, and research gates remain open. Phase 2 tails handling is required under [ADR-0052](adrs/ADR-0052-require-phase-2-depleted-uf6-tails-handling.md); deconversion to uranium oxide and HF is selected under [ADR-0053](adrs/ADR-0053-select-depleted-uf6-deconversion.md); uranium oxide is recovered for later uranium use and HF for reuse in UF6 conversion under [ADR-0054](adrs/ADR-0054-select-depleted-uf6-output-fates.md); exact forms, conditioning, and process integration remain open. The numeric uranium-fuel enrichment target is deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) until detailed recipe and balance design.*

| Generator type | Fuel source | Design role | Key tradeoff |
|---|---|---|---|
| Uranium fission reactor | Uraninite -> uranium concentrate -> UF6 conversion -> gas-centrifuge enrichment -> enriched UF6 -> UO2 pellets clad and assembled into fuel rods under [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) | Dense, sustained power through uranium conversion, enrichment, and fuel fabrication | High construction and fuel-cycle cost; requires Uraninite and fluorspar feeds under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) and [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md), cladding supply, rod fabrication, cooling, Phase 2 depleted-UF6 deconversion to uranium oxide and HF under [ADR-0053](adrs/ADR-0053-select-depleted-uf6-deconversion.md), uranium-oxide recovery and HF reuse under [ADR-0054](adrs/ADR-0054-select-depleted-uf6-output-fates.md), and post-discharge spent-fuel reprocessing/recovery under [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md); exact outputs, fates, and conditioning remain open |
| Thorium breeder reactor (separate option) | Th-232 feed plus a uranium-derived fissile startup seed from the shared Phase 2 uranium preparation/enrichment chain under [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md); the separate solid-oxide seed-and-blanket architecture is selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md): a ThO2-bearing fertile blanket remains distinct from the uranium-derived seed, and bred U-233 returns as oxide fuel rods | Distinct, more complex long-horizon fission cycle | Thorium-232 is fertile, not fissile. Startup fuel, breeding, reprocessing, and rod fabrication add process complexity; the seed uses the same qualitative enrichment grade as uranium fuel under [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), while the numeric target remains deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md); the exact seed compound, isotope composition, item identity, quantity, detailed breeding/reprocessing balance, and waste handling remain open. See [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md) and the [World Nuclear Association thorium overview](https://world-nuclear.org/information-library/current-and-future-generation/thorium) |
| Solar photovoltaic (crystalline-silicon PV) + LFP battery storage | Sunlight; dedicated Phase 2 PV production route based on the selected silicon supply direction; LFP cells for battery storage | Clean, fuel-free supplement with day/night variability | PV and battery storage begin in Phase 2; PV does not depend on post-Core CPU wafer/chip or cleanroom fabrication. The starting region guarantees apatite-rich phosphorite and lithium-bearing brine; spodumene remains an alternative and may be regional under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). Exact silicon grade, cell process, feed-recovery routes, cell/pack design, unlocks, capacity, and tiers remain open under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md), [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md), and [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) |

**Current phase direction:** Introduce fission in Phase 2 as two distinct uranium and thorium-cycle options. Retain the steam-turbine conversion path through Phase 2 to use fission heat-exchanger steam; retire steam-turbine generation after Phase 2. Phase 1 combustion remains usable. PV begins no earlier than Phase 2 and remains a clean, space-intensive option rather than a Phase 1 bypass. Its initial crystalline-silicon platform uses a dedicated route independent of post-Core CPU wafer/chip or cleanroom fabrication under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md).

Both Phase 2 fission options require cladding and fuel-rod assembly before their fuel can be used in a reactor under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md). Zirconium-alloy cladding and shared early/mid-Phase-2 zircon access for CPU hafnium and fission cladding are selected under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md); the shared route requires a distinct Zr/Hf separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md). Enriched UO2 pellets remain the uranium rod-fabrication input under [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md), and gas-centrifuge enrichment is selected under [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md). The high-level Uraninite -> uranium concentrate -> UF6 -> centrifuge -> UO2 sequence and separate depleted-UF6 tails stream are selected under [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md) and [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md); fluorspar feed/access by the UF6-conversion unlock is selected under [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md). Uranium/fluorite recovery, reagent preparation, detailed conversion chemistry, balances, and research gates remain open. Phase 2 tails handling is required under [ADR-0052](adrs/ADR-0052-require-phase-2-depleted-uf6-tails-handling.md), with deconversion to uranium oxide and HF selected under [ADR-0053](adrs/ADR-0053-select-depleted-uf6-deconversion.md); uranium-oxide recovery for later use and HF reuse in UF6 conversion are selected under [ADR-0054](adrs/ADR-0054-select-depleted-uf6-output-fates.md); exact forms, conditioning, and integration remain open. The numeric uranium-fuel enrichment target is deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) until detailed recipe and balance design; under [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), the thorium startup seed uses the same qualitative grade, so the eventual numeric target applies to both. The thorium route retains its selected startup-seed and U-233 breeding/reprocessing model under [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md); its startup seed comes from the shared uranium chain under [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md), while the seed-and-blanket architecture is selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md); the seed's exact compound, isotope composition, item identity, quantity, and preparation, detailed routes, balances, and waste remain open; its same-grade relationship to uranium fuel is selected under [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), while the numeric target remains open under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md). Separation chemistry and equipment, output forms and grades, alloying and fabrication routes, quantities, material balances, and research gates remain open.

**Phase 2 design notes:**
- Fission power density should be **orders of magnitude higher** than combustion, creating massive spatial relief for the factory. However, the *fabrication cost* of a reactor (stainless steel pressure vessel, zirconium cladding, graphite moderator, control rods with hafnium/boron absorbers) is substantial.
- Fission heat must pass through the Phase 2 heat-to-steam path; exact heat-exchanger and coolant details remain open. Core excludes blackout-induced meltdown gameplay and a dedicated emergency-safety device under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md).
- Phase 2 fission converts heat through steam turbines. The exact turbine removal point is after Phase 2, not before fission is introduced.
- The baseline uranium route requires enriched UO2 pellets under [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md), then Phase 2 cladding and rod assembly. Both fission options depend on those fabrication capabilities under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); the shared zircon path includes a distinct Zr/Hf separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md). Fuel-form details, zirconium-alloy grade, zircon feed preparation/conversion, separation chemistry/equipment, alloying and rod-forming routes, combined supply quantities, conversion/reprocessing steps, material balances, equipment assignments, and research gates remain open.
- Neither uranium nor thorium fuel is a first-Core prerequisite; a fission path is required only when selected to supply power. The thorium startup model is selected in ADR-0023, with the seed sourced from the shared uranium chain under ADR-0047; the solid-oxide seed-and-blanket architecture is selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md); exact seed details and the fuel-route balance remain open.
- Exact normal operating controls, monitoring, coolant routing, reactor tiers, and research gates remain open; the Core boundary does not add a separate blackout-failure loop.
- Fission creates **breathing room from military pressure** if operated cleanly. No combustion pollution means fewer attacks, giving the player a choice: dense power without the military consequence.

### Phase 3: Fusion (Late Game)

*Requires fusion fuel infrastructure; connects to the deepest mining and chemistry of the mod.*

| Generator type | Fuel source | Design role | Key tradeoff |
|---|---|---|---|
| Tokamak-class D-T fusion reactor | Deuterium (from water electrolysis/concentration) + tritium (bred from a lithium blanket) | Selected Phase 3 route; a Tokamak is itself a magnetic-confinement design | Deep industrial chain and large construction cost; fuel availability depends on tritium breeding and blanket operation |
| Geothermal generation | Heat from a geothermal reservoir | Selected Phase 3 route; location-dependent, non-fusion baseload | Steady output where suitable sites exist; map placement and extraction limits remain open |
| Solar PV scale-up | Sunlight; progressively improved photovoltaic materials | Selected Phase 3 route continuing early photovoltaic generation | Clean and fuel-free, but land- and storage-intensive; later material tiers remain proposed |
| Concentrated solar thermal + storage | Sunlight concentrated into stored high-temperature heat; sodium/potassium nitrate salts are a material candidate for storage | Selected additional Phase 3 route; dispatchable thermal generation | Requires a non-steam high-temperature converter; overlaps PV's space trade-off, while the salt blend and site design remain open |

**Phase 3 design notes:**
- **Selected minimum roster:** Tokamak, geothermal generation, and continued solar PV. Concentrated solar thermal with storage is an additional selected route. Their exact construction chains, relative outputs, and unlocks remain open.
- “Magnetic confinement” is a category that includes the Tokamak, not a second generator. The design does not count a generic magnetic-confinement or inertial-fusion concept as another Phase 3 option. Tokamaks and stellarators are magnetic-confinement approaches; see the [World Nuclear Association fusion overview](https://world-nuclear.org/information-library/current-and-future-generation/nuclear-fusion-power).
- Fusion fuel is **effectively infinite**: deuterium from water, tritium bred from lithium. The constraint is not fuel supply but *infrastructure*.
- The fusion chain touches more parts of the mod than any other single capability: mining (tungsten, niobium/tantalum, lithium), chemistry (deuterium concentration, lithium processing), metallurgy (superconducting alloys, plasma-facing tungsten), and semiconductor electronics (magnet control systems).
- Fusion should be **the ultimate spatial relief** — a small footprint delivering enormous power. However, building the first fusion reactor should feel like a major project rivaling the endgame Core in scope.

### Phase 3–4 Power Conversion Boundary (Selected Architecture; Details Open)

Steam-based conversion ends after Phase 2. Phase 3/4 heat sources use closed non-steam conversion systems; this is a design boundary, not a claim that high-temperature heat cannot produce steam in engineering. The selected converter families match the source temperature and connect to distinct material chains:

| Converter | Selected application | Material and process hooks | Trade-offs and limits |
|---|---|---|---|
| Closed supercritical-CO₂ Brayton cycle | High-grade heat from the Tokamak and concentrated-solar receiver/storage | A sealed, pressurized CO₂ loop drives a compact turbine/recuperator rather than a water-steam turbine. Hot-side parts can connect to nickel/chromium/cobalt superalloys, refractory linings, and high-pressure heat-exchanger alloys. MIT's reactor-cycle analysis treats the cycle as suitable for high-temperature heat sources above roughly 500°C. | Requires a sufficiently hot source, high-pressure containment, and demanding seals/heat exchangers. CO₂ is a recirculated working fluid, not a fuel. |
| Binary organic Rankine cycle (ORC) | Lower- or medium-temperature geothermal heat | Geothermal brine heats a separate sealed, lower-boiling working fluid (for example, an isobutane- or pentane-family fluid); only that vapor passes through the expander. Titanium or stainless-steel heat exchangers connect to corrosion-resistant materials and existing hydrocarbon chemistry. | It is non-steam, but still a closed vapor-expansion cycle; the chosen fluid brings flammability, leakage, and environmental trade-offs. DOE describes binary geothermal plants as using a secondary fluid that never contacts the geothermal turbine. |
| Thermophotovoltaic (TPV) receiver | Phase 4 Hawking route, after radiation is absorbed into a controlled high-temperature emitter | Thermal infrared photons generate electricity directly in bandgap-matched III–V cells, with a tungsten emitter and reflective spectral-return surfaces. The material hooks include gallium, indium, arsenic, and tungsten, linking late power conversion to semiconductor and refractory chains. | Laboratory TPV cells have exceeded 40% efficiency at emitter temperatures of 1,900–2,400°C; this is an emerging technology, not a mature utility-scale plant. A controlled emitter spectrum and cell cooling are required; do not assume direct conversion of unfiltered Hawking radiation. |

Other Phase 3/4 routes do not need a heat engine: solar PV and the stellar-scale collector use photovoltaic conversion, with the energy beam serving only as transmission; the cross-universe route uses a speculative direct field coupler rather than a thermal cycle. Exact working fluids, alloy grades, storage salts, efficiencies, cooling systems, and converter construction chains remain open. Sources: [MIT supercritical-CO₂ cycle analysis](https://dspace.mit.edu/handle/1721.1/17746), [DOE geothermal binary-cycle overview](https://www.energy.gov/hgeo/geothermal/geothermal-electricity-generation), and [Nature thermophotovoltaic demonstration](https://doi.org/10.1038/s41586-022-04473-y).

### Phase 4: Near-Realistic Sci-Fi Endgame Power Generation

*The relationship between Phase 4 generation and an active Planetary Simulation Core, including its unlock gate, remains open.*

The Phase 4 roster includes three selected route identities; see the table below. The Subspace Capacitor is not selected; see [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md). Detailed mechanics, research gates, relationship to the Core, and whether each route is optional or required remain open.

| Generator concept | Principle | Design role | Key tradeoff |
|---|---|---|---|
| Hawking Radiation Engine | Contained micro-black hole emitting Hawking radiation; harvested via a controlled thermal emitter | Selected as one of three Phase 4 options. TPV is the selected conversion direction after radiation is absorbed and spectrally matched to a high-temperature emitter; finite lifetime and a Core role remain proposals | Large construction demand, source spectrum, emitter temperature, containment, and lifetime are unresolved; the black-hole source itself is speculative |
| Cross-universe exergy-gradient tap | A controlled boundary couples to an external non-equilibrium energy reservoir; work is extracted while entropy rises on the source side | Selected Phase 4 route identity; the usable source is the cross-boundary energy gradient, not “entropy” as a fuel | Must define a finite or constrained source, boundary stability, and consequences in the donor universe; not established physics. It uses a direct field-coupling concept, not a heat engine |
| Stellar-scale solar collection + energy beam | Large-scale solar collectors generate electricity; a beam transfers it to remote receivers | Selected Phase 4 route identity; the collector is photovoltaic generation at stellar scale, while the beam is transmission | Space-based collection and receiver infrastructure are complex. Space Exploration's [Energy Beam](https://spaceexploration.miraheze.org/wiki/Energy_Beam) sends energy to receivers as heat and includes distance losses; the beam is not a separate generator |

**Reserve concepts for review, not counted toward the three-route minimum:**
- **Rotating black-hole energy extraction:** tap a rotating black hole's spin rather than its Hawking radiation. It is a distinct theoretical mechanism but shares extreme black-hole containment and overlaps the Hawking route thematically.
- **Antimatter annihilation:** a high-density energy carrier used in science fiction, but not a net primary source if the factory must spend more energy creating it than it later recovers. It only becomes a distinct power route if its source and energy balance are defined.

**Hawking Radiation Engine — provisional implementation concept:**
- **Construction phase (massive power investment):** Player builds an optical concentrator array (precision glass/mirror elements from optics chain) that collapses a concentrated radiation field into a micro-singularity. This requires enormous input power to achieve the threshold for radiation-pressure collapse. Ironic cycle: you need more power to build it than it produces initially — but once stable, output exceeds construction draw.
- **Operational phase (finite but extendable):** The contained micro-black hole emits Hawking radiation at a predictable spectrum (computed by the Planetary Simulation Core). The selected conversion direction absorbs that radiation into a controlled high-temperature emitter for TPV cells; the spectrum and thermal-management model remain unvalidated. The black hole's mass decreases over time as it radiates — its operational lifetime is finite, inversely proportional to initial mass.
- **Feeding matter to extend life:** Player can feed concentrated matter/fuel into the singularity (mass → energy via E=mc²). This extends operational life but costs resources: you trade material inputs for power output at a predictable rate. Different fuel types have different mass-energy yields, connecting back to the fuel-density spectrum.
- **Smaller = faster evaporation:** The physics is unforgiving here — smaller initial black hole has higher Hawking temperature (more efficient thermal conversion) but evaporates much faster. Player chooses: compact fast-burning engine vs. massive slow-dying one. This creates a meaningful size-vs-lifetime tradeoff with real engineering consequences.
- **Simulation's role:** Computes Hawking radiation spectrum for thermal converter optimization, models collapse dynamics during construction to prevent containment breach, predicts remaining lifetime based on feeding schedule.

**Candidate player education — informatron/guidebook entries:**
- The Phase 4 candidate may have a **dedicated physics page** in the player's guidebook (informatron or equivalent). It would explain the underlying science at increasing levels of depth:
  - **Fission entry:** How nuclear binding energy works, why splitting heavy nuclei releases energy, mass defect → E=mc², chain reactions, why the selected uranium route uses enrichment, and how requirements vary by reactor design
  - **Fusion entry:** How light nuclei fusion overcomes Coulomb barrier, binding energy curve peak near iron-56, why extreme temperature/pressure needed, magnetic confinement principles, the D-T reaction
  - **Phase 4 option:** Hawking radiation as a result of quantum field theory in curved spacetime, with an accessible explanation of particle pairs near an event horizon.
- The guidebook doesn't assume prior physics knowledge but rewards players who engage with the deeper explanations. Early-game summaries explain *what* happens; advanced entries explain *why* — accessible to any player willing to read.

**Open design details for Phase 4:**
- The generator would be player-built rather than found as a pre-made power source.
- The Planetary Simulation Core would provide operational or construction value beyond a research unlock.
- Simulation would inform construction or operation without replacing material constraints.
- The generator would be optional and would not be required for victory.

Hawking is accepted as one Phase 4 option under [ADR-0011](adrs/ADR-0011-hawking-radiation-endgame-generator.md); the boundary between advanced fusion and Phase 4, route gates, and alignment with [Endgame Vision](endgame-vision.md) remain open.

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
| 2 (fission) | Enriched UO2 fuel rods | Uraninite -> uranium concentrate -> UF6 conversion using fluorspar, with feeds/access selected under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md) and [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md) -> gas-centrifuge enrichment under [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) -> pellet preparation -> Phase 2 cladding and rod assembly; recovery, conversion chemistry, equipment, and balance remain open | Extreme — orders of magnitude above combustion fuels |
| 2 (fission, optional) | Bred U-233 | Thorium oxide seed-and-blanket cycle | Extreme — alternative long-horizon fuel |
| 3 (fusion) | Deuterium + tritium (D-T) | Water concentration → deuterium; lithium breeder → tritium | Extreme — near-infinite supply, requiring infrastructure not fuel extraction |

**Key insight:** The progression from Phase 1 to Phase 2 is a **~10,000x density jump**. This makes the spatial relief of nuclear power profound and should be communicated through factory-scale comparison (one reactor replacing dozens of generators). Phase 3's advantage is not just more power — it's *sustainable* dense power with effectively infinite fuel.

## Infrastructure Hooks per Generator Class

### Combustion Generators
- **Boiler → steam engine:** The boiler burns a burner item to produce steam; the untiered steam engine consumes steam to generate electricity. This follows the vanilla conversion boundary.
- **Gas and liquid fuel preparation:** Producer gas, biogas, and liquid fuels are not fed directly to generators. Any power-bound stream must first be converted to a burner item; the gasifier or fuel processor is not a generator.
- **Phase 2 steam turbine:** Retained through Phase 2 as the fission heat-to-electricity converter, then retired from the progression.

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
| Uranium Conversion Line | Conversion → gas-centrifuge enrichment under [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md) → UO2 powder → Phase 2 pellet preparation; feed/conversion chemistry and equipment split remain open (infra.md §10) | Tier 1 grid for chemical pumps, heaters, agitators | Parallel chain from minerals-and-refining through chemistry; enriched UO2 is required under [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md) |
| Fuel Pellet Sintering Furnace | infra.md §10; candidate refractory construction | Phase 2 pellet-preparation capability; exact equipment assignment and power draw remain open | Produces enriched UO2 pellets as an intermediate for the required rod-assembly route; an integrated process or different equipment split remains possible |
| Cladding Tube Mill | infra.md §10: candidate zirconium-alloy tube extrusion + pilger rolling | Phase 2 minimum capability for both fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); zirconium-alloy family and shared zircon access selected under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md); a distinct Zr/Hf separation stage is required under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) | Produces fuel-rod cladding; exact feed recovery/conversion, separation chemistry and equipment, alloy grade and fabrication route, supply quantities, and build details remain open |
| Fuel Rod Assembly Line (MTier 1-3) | infra.md §10: candidate manual load → semi-auto → fully automated with inline inspection | Phase 2 minimum capability for both fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); exact tier timing and research gates remain open | Candidate steps are pellet loading → end-cap welding → leak-testing; tier capabilities and inspection details remain open |
| Zr/Hf Separation Plant | infra.md §10: candidate implementation of the distinct separation stage selected under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md) | Exact equipment and grid requirement remain open | Separates the shared zircon path into zirconium-bearing and hafnium-bearing streams for cladding and CPU/fission uses; chemistry, output forms, yields, and dedicated-entity status remain open |

#### Waste Handling & Maintenance (infra.md §10 cross-reference)
- Candidate only: actively cooled spent-fuel storage pools. Whether this is the storage form, whether cooling or backup power is required, and whether it is a constructable remain open
- Post-discharge reprocessing/recovery for spent uranium fuel is required in Phase 2 under [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md); recovered outputs, residues, and implementation remain open. Plutonium extraction and any military-ammunition link are not selected
- Core fission-safety scope excludes blackout-induced meltdown gameplay and a dedicated Dead-Battery Capacitor / Fuse Link under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md); exact normal controls and heat-management details remain open.

### Fusion Generators

The Tokamak needs a heat-to-electricity system; it does not deliver raw plasma as grid power. The selected non-steam direction is a closed supercritical-CO₂ Brayton cycle for high-grade heat. The reactor's achievable outlet temperature and the converter's materials and construction requirements remain open.

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

The component list is a candidate design, not a current recipe requirement; exact inputs and quantities remain open.

**Operational details:**
- **Feeding matter to extend life:** Player feeds concentrated matter/fuel into the singularity (mass → energy via E=mc²). Each fuel type has different mass-energy yield connecting back to the [fuel-density spectrum](#fuel-density-spectrum-reference-guide) table.
- **Size vs. lifetime tradeoff:** Smaller initial black hole has higher Hawking temperature (more efficient thermal conversion via Thermoelectric Array) but evaporates faster. Player chooses: compact fast-burning engine vs. massive slow-dying one.
- **Simulation's role:** Planetary Simulation Core computes Hawking radiation spectrum for Thermal Converter optimization, models collapse dynamics during construction to prevent containment breach, predicts remaining lifetime based on feeding schedule.

## Open Design Decisions (Power Production)

- **Which Phase 3/4 non-steam conversion details remain?** The selected directions are closed supercritical-CO₂ Brayton for high-grade heat, binary organic Rankine for geothermal heat, and TPV for the Hawking-route emitter. Exact source conditions, materials, working fluids, performance, and construction details remain open.
- **Which Phase 2 fission operating details remain?** The Core excludes blackout-induced meltdown gameplay and a dedicated emergency-safety device under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md); exact normal heat-transfer, coolant, controls, monitoring, tiering, and research/construction gates remain open.
- **Which fuel-processing routes produce burner items?** The vanilla boiler/steam-engine path is selected, but the exact item forms and processing paths for producer gas, biogas, and liquid fuels remain open.
- **What fission fuel-cycle details remain open?** Phase 2 cladding and fuel-rod assembly are required for both fission options under [ADR-0043](adrs/ADR-0043-phase-2-fission-fuel-rod-fabrication.md); zirconium-alloy cladding and shared early/mid-Phase-2 zircon access are selected under [ADR-0044](adrs/ADR-0044-phase-2-shared-zircon-supply-for-fission-cladding.md), and the shared route includes a distinct Zr/Hf separation stage under [ADR-0045](adrs/ADR-0045-phase-2-zirconium-hafnium-separation-stage.md). The uranium route requires enriched UO2 under [ADR-0042](adrs/ADR-0042-require-enriched-phase-2-uranium-fuel.md), with gas-centrifuge enrichment selected under [ADR-0046](adrs/ADR-0046-select-phase-2-uranium-centrifuge-enrichment.md), its high-level concentrate/UF6/enrichment/UO2 sequence under [ADR-0048](adrs/ADR-0048-select-phase-2-uf6-uranium-fuel-cycle.md), Uraninite feed/access under [ADR-0050](adrs/ADR-0050-select-phase-2-uraninite-uranium-feed.md), and fluorspar feed/access under [ADR-0049](adrs/ADR-0049-select-phase-2-fluorspar-feed-for-uf6-conversion.md); the same uranium chain supplies the thorium seed under [ADR-0047](adrs/ADR-0047-share-phase-2-uranium-chain-with-thorium-seed.md); the solid-oxide seed-and-blanket architecture is selected under [ADR-0055](adrs/ADR-0055-select-phase-2-thorium-oxide-seed-blanket-architecture.md). Uranium/fluorite recovery, reagent preparation, detailed conversion chemistry, exact oxide/HF forms, conditioning, and process integration for the output fates selected under [ADR-0054](adrs/ADR-0054-select-depleted-uf6-output-fates.md), separation chemistry and equipment, alloy grade, combined supply quantities, exact seed compound/isotope composition, quantity, preparation, detailed recycling/reprocessing routes, U-233 recovery and production implementation, material balances, waste handling, equipment assignments, and research gates remain open; its qualitative grade is shared with uranium fuel under [ADR-0056](adrs/ADR-0056-share-uranium-fuel-enrichment-grade-with-thorium-seed.md), with the numeric target deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md). The numeric uranium-fuel enrichment target is deferred under [ADR-0051](adrs/ADR-0051-defer-phase-2-uranium-enrichment-target.md) until detailed recipe and balance design.
- **How does fusion connect to the endgame network?** Is fusion itself an endgame milestone, or is it parallel to (or prerequisite for) the Planetary Simulation Core?
- **What are the remaining solar material and storage gates?** The initial Phase 2 platform is crystalline silicon on a dedicated route that does not depend on post-Core CPU wafer/chip or cleanroom fabrication under [ADR-0038](adrs/ADR-0038-select-phase-2-crystalline-silicon-pv.md); initial Phase 2 battery cells use LFP cathode chemistry under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md), with feed sources and starting-region access selected under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). Exact silicon grade, PV process and equipment, lithium/phosphate recovery routes and grades, spodumene placement/access timing, battery cell/pack design, unlocks, capacities, later tiers, site design, and efficiency values remain open. The Phase 3 PV scale-up and additional CSP-with-storage route are selected.
- **How should geothermal sites work?** The Phase 3 geothermal route and binary ORC direction are selected, but site placement, resource limits, working fluid, and heat-exchanger design remain open.
- **How much does each generator class contribute to military pressure?** Clean combustion (scrubbed) vs. dirty combustion; fission's thermal pollution; fusion's zero-emission profile — these affect the player's decision calculus.
- **What recovered outputs and residual-waste handling does the uranium spent-fuel branch need?** The Phase 2 post-discharge reprocessing/recovery branch is required under [ADR-0057](adrs/ADR-0057-require-phase-2-reprocessing-for-spent-uranium-fuel.md); recovered streams, reuse/fates, residuals, process, storage, equipment, and research gate remain open. Do not infer plutonium recovery or a military-ammunition link; this is distinct from depleted-UF6 tails handling and the thorium U-233 cycle.
- **Which construction and research gates apply to the selected routes?** Route identities are selected, but exact Core dependencies, progression order, and whether each route is optional or required remain open.
- **Where does advanced fusion end and Phase 4 begin?** Hawking is accepted as one Phase 4 option, but its boundary and the Simulation Core dependency still need alignment with [Endgame Vision](endgame-vision.md).
- **How should power-route gates use the Core?** Core Level 2/3 and route-specific gates remain open. The first-Core gate is recorded in [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md); the six bridge mappings are selected in [ADR-0022](adrs/ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md).

## Design Intent

Candidate design intent: generator choice, fuel, and proximity to loads should create factory-layout decisions. Custom conductor choices, transmission behavior, and loss diagnostics remain optional extension concepts under [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md) and must not be assumed for Core.

Power and floor space are secondary optimization axes in the overall design. They should create meaningful tradeoffs without becoming opaque punishment or maintenance busywork.

## Candidate Grid Model — DEFERRED TO EXTENSION MOD

> All subsections below are **deferred** to the proposed `power-transmission-override` extension described in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md). They remain unapproved design references only. **No materials, recipes, or infrastructure items for these concepts should be planned or added to the core mod.** Revisit them only if the extension is approved.

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

### Generator-to-Voltage Mapping (Optional Custom-Transmission Extension Candidate)

> The following voltage tiers and generator requirements are source proposals for an optional custom-transmission extension. They are not core behavior: the accepted core direction retains the vanilla grid and adds compatible tiered poles, without custom voltage levels or transmission losses.

The optional custom-grid extension would assign minimum voltage-tier requirements to generator output:

| Phase | Generator Type | Min Voltage Tier | Notes |
|-------|---------------|------------------|-------|
| 1-2 | Vanilla Boiler + Steam Engine (untiered) | Tier 0 | Boiler burns burner items; engine consumes steam |
| 1 | Wind Turbine (Enhanced) | Tier 0 | Output varies by season/weather; same range limitations as steam |
| 1-3 | Solar Panel Array (candidate tiers) | Tier 0 | Output depends on time/day cycle; pair with storage |
| 3 | Geothermal Tap / Heat Exchanger Station | Tier 1 required | Location-dependent (geothermal sites; placement remains open) |
| 2 | Thermal Fission Reactor (MTier 1-4) | Tier 1 min, Tier 2 recommended | Output so large that Tier 0 grid cannot handle it at MTier 3+; step-up transformer mandatory |
| 2 | Steam Turbine (vanilla retained) | Tier 1 min | Converts fission heat-exchanger steam through Phase 2; retired afterward |
| 3 | Fusion Tokamak Reactor | Tier 2 min (Tier 3 optimal) | Massive output; non-steam conversion is proposed |
| Endgame | Hawking Radiation Engine | Tier 3 mandatory | Requires ultra-high-voltage DC infrastructure |

### Transmission Infrastructure Catalog (Optional Custom-Transmission Extension Candidate)

The inventory below is also extension-only candidate material; it does not replace the accepted core pole family.

| Machine | Voltage Tier(s) | Power Role | Grid Integration Notes |
|--------------------|-----------------|------------|------------------------|
| Wooden Distribution Pole + Line (Phase 1) | Tier 0 only | Short-range distribution from early generators | ~50 tile max reach; replaces vanilla pole. Cannot cross voltage tiers. Build: treated wood + basic copper wire. |
| Steel Transmission Tower + High-Voltage Line (MTier 1–3) | Tiers 1–2 | Long-distance bulk power transmission | MTier 1: basic steel tower, copper conductors (~25 kW/tile). MTier 2: reinforced with composite insulators (~100 kW/tile). MTier 3: ultra-high-tension towers supporting gold-alloy endgame conductor. |
| Step-Down Transformer / Substation (MTier 1–3) | Crosses any tier boundary | Converts high-voltage → industrial-use voltage for factory machines | MTier 1 = adjacent-tier only; MTier 2 = one-gap bridging; MTier 3 = all-tier conversion with active load balancing. |
| Underground Power Cable Trench System (Phase 3+) | Tiers 1–2 | Bury power lines to free surface space; reduce exposure loss | Uses same conductor materials (copper/aluminum/composite in concrete conduit). Recommended for dense factory zones where overhead towers would block expansion or visual clarity. |
| HVDC Converter Station (Phase 4+) | Tier 3 | AC→DC conversion for ultra-long-distance transmission with minimal losses | Optional custom-transmission extension candidate; not a core prerequisite under the accepted vanilla-grid direction. Whether a future custom grid needs it remains open. |

### Transmission Losses and Factory Layout Rules (Optional Extension Candidate)

> The loss values and layout rules below apply only if a custom-transmission extension is designed and selected. They are not accepted core mechanics or requirements.

The source proposal models transmission loss as a function of line length, conductor properties, voltage tier, and load:

| Tier | Loss per 100 tiles (standard) | Loss per 100 tiles (optimized) |
|------|-------------------------------|--------------------------------|
| 0 (tin-plated copper) | ~8% | ~4% (upgrade to pure copper) |
| 0–1 (copper, no transformer) | ~7% | — |
| 1–2 (aluminum wire) | ~2.5% | ~1.5% (aluminum-steel composite) |
| 3 HVDC (gold alloy) | — | ~0.5% |

**Candidate extension layout implications:**
- If selected, place high-output generators (fission at MTier 3+, fusion) near their primary load clusters to avoid expensive step-up/step-down sequences
- Under this model, use Tier 2–3 transmission only beyond ~200 tile distance; the threshold is unvalidated
- Under this model, an HVDC Converter Station would be required for remote power sources more than 1 km from the main grid; this is not a core requirement
- Transformer placement could create strategic choke points: clustering transformers at factory edges frees interior space but risks cascading failures

## Power Storage and Stabilization

Energy-storage construction, capacity, and progression remain open. Core grid diagnostics and stabilization are bounded by [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md): Core uses native network feedback and does not require custom grid devices.

### Energy Storage Systems

| Machine / Entity | Phase | Role | Key Design Notes |
|-----------------|-------|------|-----------------|
| Capacitor Bank (accumulation) | Phase 1 | Buffer short-term power fluctuations | Candidate early buffer; exact capacity and tiering remain open |
| Battery Storage Unit | Phase 2 | Longer-duration energy storage for load leveling and general grid backup; not a fission-safety dependency | LFP cathode chemistry is selected under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md); feed sources and starting-region access are selected under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md). Recovery routes, full cell/pack design, capacity, and progression remain open |
| Dead-Battery Capacitor / Fuse Link | Not selected | Unapproved safety-device proposal | No dedicated consumable safety item is required in Phase 2 Core under [ADR-0059](adrs/ADR-0059-exclude-blackout-meltdown-gameplay-from-phase-2-core-fission.md) |
| Flywheel Energy Store | Phase 3+ | Mechanical kinetic energy storage with high round-trip efficiency | Alternative to batteries; requires precision manufacturing (semiconductor components at high tiers) but no chemical degradation |

### Grid Stabilization — Optional Extension Candidates (Not Core)

| Machine / System | Phase | Role | Key Design Notes |
|-----------------|-------|------|-----------------|
| Reactive Power Compensator | Optional extension candidate | Hypothetical voltage support in a future custom-grid model | Not a Core requirement or part of the accepted vanilla-grid behavior |
| Surge Protector / Lightning Arrester | Optional extension candidate | Hypothetical transient-protection mechanic in a future custom-grid model | Not a Core requirement or fission-safety dependency |
| Frequency Regulator | Optional extension candidate | Hypothetical load/generation balancing in a future custom-grid model | Not a Core requirement for variable-renewable generation |

## Diagnostics and Onboarding

Core relies on Factorio's native electrical network and standard machine feedback. Custom voltage, line-loss, fault-propagation, and load-analysis diagnostics are not Core features under [ADR-0058](adrs/ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md); any such system remains an unapproved optional-extension candidate. Documentation may explain the selected grid and generators without adding custom grid mechanics.

## Connections to Other Systems

- Steel and alloy choices provide conductor options.
- Electrolysis, electric furnaces, cleanrooms, and semiconductor fabrication create distinct load profiles.
- High-demand process clusters can motivate local generation or dedicated transmission.
- The endgame network needs reliable power and may justify specialized low-loss distribution as an optional capability.

## Design Guardrails

- Core should preserve the vanilla network's feedback; any future custom limit or loss mechanic must be explicit and explainable.
- Make early power simple to establish and diagnose.
- Let the vanilla grid and factory layout solve Core power problems; custom diagnostics, stabilization, and programmable grid behavior are not Core prerequisites. Advanced grid mechanics remain optional extension candidates.
- Treat mechanics and values for any future custom-grid extension as unselected; Core uses the vanilla network and accepted tiered poles.

## Reference Inspiration

GTNH may inform future optional-grid research about voltage and capacity trade-offs; no such model is selected for Core. Its opaque failure diagnosis remains a caution if an extension is proposed.
