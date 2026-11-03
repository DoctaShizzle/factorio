# Intermediate Products - Design Map

*For: Factorio Overhaul Mod*
*Status: Candidate inventory / requirements phase*

Related documents: [Minerals and Refining](minerals-and-refining.md) - mined feeds and mineral-derived products; [Chemical Products and Processes](chemical-processes.md) - reactions and chemical feeds; [Machine Systems](machine-systems.md) - candidate equipment families.

## Scope

This document tracks manufactured materials and components that sit downstream of mineral refining and chemistry. It does not duplicate ore rosters or specify full chemical recipes. A material belongs here when it is an alloy, functional compound, fabricated component, or assembly that unlocks a meaningful industrial capability.

The lists are candidates, not a promise that every product is mandatory. Favor a bounded number of recognizable capability unlocks over many near-identical intermediates.

## Metallurgy and Structural Products

| Product | Candidate inputs / route | Industrial role |
| --- | --- | --- |
| Pig iron | Hematite or magnetite feed, coke, flux; blast furnace | Early ironmaking intermediate for steel |
| Direct-reduced iron (DRI) | Iron oxide feed plus hydrogen reduction | Lower-carbon ironmaking route; feeds steelmaking |
| Carbon steel | Pig iron/DRI and scrap; basic oxygen or electric-arc steelmaking | Main structural metal and factory machinery |
| Stainless steel | Steel plus chromium and nickel | Corrosion-resistant chemical plant, pipe, and reactor equipment |
| Niobium microalloyed steel | Steel plus ferroniobium from columbite-tantalite | High-strength structures and pressure-bearing plant components |
| Tool steel | Steel plus carbon and selected tungsten/vanadium additions | Durable drills, cutters, and machine parts |
| Invar / low-expansion alloy | Iron-nickel alloy | Precision tooling and temperature-stable components |
| Titanium alloy | Titanium plus aluminum/vanadium or steel additions | High-strength, corrosion-resistant late-game structures |
| Aluminum alloys | Aluminum plus selected alloying elements | Lightweight structures, heat exchangers, and transport components |

Chromium and niobium have confirmed roles in steelmaking. The gameplay distinction can be capability-based: stainless steel unlocks corrosive service, while niobium microalloyed steel enables high-strength structural parts.

## Battery and Electrochemical Products

Chemical routes for the feed compounds belong in [Chemical Products and Processes](chemical-processes.md); this table covers their use in manufactured products.

| Product | Candidate inputs | Industrial role |
| --- | --- | --- |
| Lithium battery salts | Lithium carbonate or hydroxide | Cathode precursor and electrolyte supply |
| Cobalt and manganese cathode compounds | Cobalt sulfate and manganese compounds | Higher-performance battery chemistries |
| Graphite anode material | Purified natural or synthetic graphite | Battery electrodes and electrical components |
| Battery cells / packs | Cathode, anode, electrolyte, casing, current collectors | Grid buffering, mobile equipment, and process backup |

Battery chemistry choices may trade material intensity, energy storage, lifetime, and manufacturing complexity. Specific cell chemistries remain open; avoid adding every real battery formulation.

## Electronics and Semiconductor Products

| Product | Candidate inputs / route | Industrial role |
| --- | --- | --- |
| Metallurgical silicon | Quartz reduction with carbon | Starting material for silicon purification |
| Electronic-grade polysilicon | Chlorosilane purification and deposition | Feedstock for wafer growth |
| Silicon wafers | Single-crystal growth, slicing, polishing, doping | Semiconductor fabrication substrate |
| Photolithography materials | Specialty organic chemistry | Patterning during wafer fabrication |
| High-k dielectric compounds | Hafnium- or aluminum-based precursors and deposition | Advanced transistor insulation |
| Copper / tantalum-nitride interconnect stack | Ultra-pure copper and tantalum compounds | Reliable chip wiring and diffusion barrier |
| Tantalum capacitor powder and capacitors | Refined tantalum and capacitor fabrication | Compact, reliable electronics for control and computing |
| Packaged integrated circuits | Fabricated dies, packaging materials, electrical contacts | Automation, PLCs, and advanced factory equipment |

Tantalum's circuit role should be distinct from its mineral recovery: concentrate it from niobium-tantalum feeds, refine it, then use it for capacitor products and selected chip components.

## Nuclear Materials and Assemblies

There is no single universal reactor bill of materials. These are candidate capabilities for the mod's fission and fusion systems; select a coherent reactor family rather than combining every real-world option.

### Fission

| Product | Candidate inputs / route | Role and design hook |
| --- | --- | --- |
| Uranium oxide fuel | Uranium concentrate, conversion, and fuel fabrication | Main fission fuel path; enrichment and recycling are optional progression decisions |
| Optional thorium fuel cycle | Thorium-bearing monazite, irradiation/breeding, and U-233 fuel fabrication | Alternative long-horizon fuel capability, not a simple direct thorium burn recipe |
| Zirconium-alloy cladding | Zircon concentrate, Zr/Hf separation, alloying | Low-neutron-absorption fuel-rod cladding; high-purity zirconium is the goal |
| Hafnium absorber components | Hafnium separated from zirconium-bearing feed | Neutron-absorbing control material; a valuable co-product rather than waste |
| Boron-carbide absorber parts | Boron compounds and carbon | Alternative neutron absorber for control assemblies |
| Reactor structural steel | Stainless and specialty steels | Pressure vessels, heat exchangers, and chemical handling |
| Graphite moderator | Purified graphite | Moderator option for selected reactor designs |

The educational process choice is unusually clean: zircon and hafnium commonly occur together, yet nuclear cladding favors zirconium with hafnium minimized, while hafnium is useful as a neutron absorber.

### Fusion

| Product | Candidate inputs / route | Role and design hook |
| --- | --- | --- |
| Deuterium-tritium fuel | Deuterium from water; tritium from a lithium-breeding loop | Fusion fuel cycle; tritium is produced and recovered, not mined as an ore |
| Lithium breeder blanket | Lithium-bearing feed processed into a ceramic or liquid breeder material | Neutron blanket breeds tritium and transfers heat |
| Tungsten plasma-facing armor | Refined tungsten fabricated into tiles/components | Handles intense plasma-facing heat loads in candidate designs |
| Nb3Sn / NbTi superconducting conductors | Niobium with tin or titanium, wire processing, cryogenic systems | High-field magnets for plasma confinement |
| Fusion structural and shielding materials | Stainless steel, copper, selected neutron-multiplier materials | Magnet support, heat removal, and shielding; final selection depends on reactor design |

Beryllium can serve as a neutron multiplier in some blanket concepts, but it should be an optional, well-motivated branch rather than an assumed universal fusion input. ITER's current blanket plan uses tungsten armor; alternative plasma-facing materials can remain documented variants rather than parallel mandatory chains.

## Distributed Computational Endgame

The endgame remains a network of industrial capabilities rather than one megastructure:

```text
Electronic-grade silicon -> wafer fabrication -> packaged processors
                                             -> computing clusters
Specialty metals and gases -> advanced packaging / interconnects
Precision optics + cryogenics -> simulation links and high-performance systems
                                             -> planetary research network
```

A packaged processor is a component, not the victory condition. The player builds geographically distributed wafer, processor, supercomputer, and research facilities that turn industrial capacity into simulation capacity.

## Provisional Recipe Pathways

This is a recipe-family inventory, not a finalized recipe book. It records the candidate transformation and output use, but not numeric quantities, crafting times, machine counts, or unlock requirements. Chemical inputs and reactions are specified in [Chemical Products and Processes](chemical-processes.md); candidate equipment is mapped in [Machine Systems](machine-systems.md). All entries remain candidates until approved.

### Recipe Pathways: Metallurgy

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Pig iron | Iron concentrate + carbon reductant + flux -> pig iron + slag/off-gas | Steelmaking feed |
| Direct-reduced iron | Iron oxide feed + hydrogen -> DRI + water | Lower-carbon steelmaking feed |
| Carbon steel | Pig iron/DRI + scrap + carbon/oxygen adjustment -> steel + slag | Main structural material |
| Stainless steel | Steel + chromium + nickel -> stainless steel | Corrosion-resistant plant, pipes, and vessels |
| Niobium microalloyed steel | Steel + ferroniobium -> high-strength steel | Pressure-bearing and high-strength structures |
| Tool steel | Steel + carbon + selected tungsten/vanadium additions -> tool steel | Durable cutters, drills, and machine parts |
| Invar | Iron + nickel -> low-expansion alloy | Precision tooling and temperature-stable parts |
| Titanium alloy | Titanium + selected alloy additions -> titanium alloy | Lightweight, high-strength structures |
| Aluminum alloy | Aluminum + selected alloy additions -> aluminum alloy | Lightweight structures and heat exchangers |

### Recipe Pathways: Batteries

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Lithium cathode precursor | Lithium carbonate/hydroxide + selected transition-metal compounds -> cathode precursor | Battery cathode material |
| Cobalt/manganese cathode compounds | Leach and purify cobalt/manganese-bearing feed -> sulfate or oxide compounds | Higher-performance battery chemistries |
| Graphite anode material | Purified graphite -> grind/classify and coat or shape | Battery anode |
| Battery cell | Cathode + anode + electrolyte + separator + casing -> cell | Electrical storage |
| Battery pack | Cells + casing + control electronics -> pack | Grid buffering and mobile equipment |

### Semiconductor and Electronics Products

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Electronic-grade polysilicon | Metallurgical silicon -> chlorosilane purification/deposition -> polysilicon | Wafer feedstock |
| Silicon wafer | Polysilicon -> single-crystal growth -> slicing/polishing/doping | Semiconductor substrate |
| Patterned wafer | Wafer + photoresist + specialty process gases -> patterned wafer | Circuit fabrication |
| Copper/tantalum-nitride interconnect | Ultra-pure copper + tantalum compound -> deposited interconnect stack | Chip wiring and diffusion barrier |
| Tantalum capacitor | Refined tantalum -> capacitor powder/anode + dielectric and packaging | Compact electronics |
| Packaged integrated circuit | Fabricated die + contacts + package -> packaged IC | PLCs, factory automation, and computation |

### Recipe Pathways: Nuclear Materials

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Uranium oxide fuel pellet | Uranium concentrate -> fuel conversion -> UO2 powder -> pressed/sintered pellet | Fission fuel assembly |
| Thorium-cycle fuel | Thorium-bearing feed -> optional breeding/conversion route -> U-233-bearing fuel | Optional alternative fission cycle |
| Zirconium-alloy cladding | Zircon concentrate -> Zr/Hf separation -> zirconium sponge/alloy -> cladding | Fuel-rod cladding |
| Hafnium absorber | Hafnium-bearing separation stream -> refined hafnium -> absorber component | Neutron-control assembly |
| Boron-carbide absorber | Boron compound + carbon -> B4C component | Alternative neutron-control assembly |
| Reactor steel assembly | Stainless/specialty steel -> fabricated vessel, heat exchanger, and support parts | Reactor plant construction |
| Lithium breeder blanket | Lithium-bearing material -> ceramic/liquid breeder form -> blanket module | Fusion tritium breeding and heat transfer |
| Tungsten armor tile | Refined tungsten -> formed/finished plasma-facing tile | Fusion chamber protection |
| Nb3Sn or NbTi conductor | Niobium + tin or titanium -> superconducting alloy -> wire/cable | High-field fusion magnets |

### Distributed Computing Endgame

| Candidate output | Provisional recipe pathway | Product use |
| --- | --- | --- |
| Processor cluster | Packaged ICs + boards + cooling and power components -> compute rack | Regional computation |
| Supercomputer facility | Compute racks + high-capacity power/cooling + network equipment -> facility | Large-scale simulation |
| Simulation cluster node | Supercomputer facility + synchronization and precision links -> network node | Distributed simulation |
| Planetary research center | Regional cluster nodes + precision optics + research infrastructure -> center | Endgame objective network |

## Design Checks

- Every listed product should unlock a capability, satisfy a distinct industrial demand, or connect two existing systems.
- Keep chemical transformations and intermediate fluids in the chemistry document; keep alloys, compounds-in-use, components, and assemblies here.
- Nuclear product routes must be optional where they represent particular reactor designs; do not imply that all fission or fusion systems require the same materials.
- Show real material use in the handbook, while labeling gameplay ratios, simplified fuel cycles, and fictional applications as design abstractions.
- Build the downstream list incrementally against actual recipe needs; do not restore the superseded 65-83 item target.

## Reference Sources

- [USGS niobium and tantalum statistics](https://www.usgs.gov/centers/national-minerals-information-center/niobium-and-tantalum-statistics-and-information)
- [USGS chromium statistics](https://www.usgs.gov/centers/national-minerals-information-center/chromium-statistics-and-information)
- [USGS zirconium and hafnium statistics](https://www.usgs.gov/centers/national-minerals-information-center/zirconium-and-hafnium-statistics-and-information)
- [US Department of Energy: Nuclear Fuels](https://www.energy.gov/ne/nuclear-fuels)
- [US Nuclear Regulatory Commission: Fuel Cycle](https://www.nrc.gov/materials/new-fuels)
- [ITER Blanket](https://www.iter.org/machine/blanket)
- [ITER Superconducting Magnets](https://www.iter.org/machine/magnets)
