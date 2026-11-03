# Machine Systems - Design Map

*For: Factorio Overhaul Mod*  
*Status: Candidate machine families / requirements phase*

Related documents: [Minerals and Refining](minerals-and-refining.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), and [Power System](power-system.md).

## Purpose

This document maps industrial operations to candidate machine families. It is not a machine-by-machine implementation specification and does not commit every listed family to a unique entity. The aim is to support many material routes with a small, learnable set of reusable equipment, while reserving specialized machines for genuine capability changes.

## Equipment Principles

- A machine family should support multiple related processes where practical.
- Introduce specialized equipment when it changes the player's capability, input/output behavior, or meaningful constraints, not just to add a machine tier.
- Keep recipe eligibility, inputs, outputs, coproducts, catalysts, and required technology visible in the handbook and machine UI.
- Allow a process line to throttle when products or coproducts have no legitimate destination. Do not rely on voiding.
- Machine throughput, footprint, power, and capital complexity can differentiate routes, but should not obscure the primary tradeoffs of resource efficiency, pollution, and infrastructure.
- Exact machine names, recipe assignments, capacities, and research gates remain provisional until the route catalog is approved.

## Candidate Machine Families

| Industrial stage | Candidate machine family | Operations | Design role |
| --- | --- | --- | --- |
| Extraction | Electric mining drill; later underground/Orefield miner | Mine finite surface patches, selected underground deposits, or mixed Orefield feeds | Progress from simple single-mineral mining to prospecting and controlled mixed-feed extraction |
| Preparation | Crusher, grinder, screen, washer, classifier | Crush, grind, size, wash, and liberate mineral grains | Reusable first stages across most feed types |
| Mechanical concentration | Gravity separator, magnetic separator | Separate by density or magnetic properties | Low-reagent process choices for appropriate ores and mineral sands |
| Flotation concentration | Flotation cell / separator | Reagent-assisted separation of fine mineral particles | Main flexible route for selected sulfide and fine-grained feeds |
| Thermal treatment | Dryer, roaster, calciner | Remove moisture, oxidize sulfides, or drive thermal transformations | Shared thermal capability with gas capture and emissions choices |
| Smelting and reduction | Blast furnace, reduction furnace, converter, electric-arc furnace | Produce impure metals, reduce oxides, convert pig iron, and make alloys | Core metallurgy with fuel, power, quality, and emissions tradeoffs |
| Chemical extraction | Leach tank / chemical reactor | Dissolve selected materials using acids, alkalis, or other reagents | Reusable hydrometallurgical route; route-specific chemistry stays in the chemical document |
| Solution processing | Filter, precipitation tank, crystallizer, solvent-extraction unit | Separate, precipitate, crystallize, and purify dissolved products | Handles reagent loops and high-purity material routes |
| Electrochemical recovery | Electrolyzer, electrowinner, electrorefiner | Split brines, recover metals from solution, or purify impure metal | Distinct electrical capability; power quality and sustained load matter |
| Product finishing | Dryer, powder former, casting machine, rolling/press equipment | Dry, calcine, cast, or shape refined products | Finishes useful materials without requiring a separate machine for every product |
| Polymer processing | Petrochemical reactor, polymerization vessel | Crack feedstocks and polymerize monomers into plastics/resins | Shared chemical plant families with selectable catalyst/process recipes |
| Semiconductor fabrication | Purification column, crystal grower, wafer saw/polisher, cleanroom fab, packaging line | Purify silicon, grow crystals, make wafers, pattern circuits, and package dies | Late-game capability chain; dedicated equipment is justified by purity and cleanroom needs |
| Nuclear fuel and component fabrication | Fuel conversion/fabrication line; component foundry | Turn approved fuel materials and specialty metals into assemblies | Optional late-game branch; detailed reactor design and fuel-cycle scope remain open |
| Power transmission | Local poles, high-voltage lines, transformers/substations | Distribute and transform power between voltage tiers | See [Power System](power-system.md); grid diagnostics are required |
| Fluid transport | Pipes, pumps, tanks, valves, heat exchangers | Move, buffer, pressurize, cool, or condition process fluids | See the fluid-system concept in [Mod Overview](mod-overview.md); detailed mechanics are open |
| Automation | PLC, sensors, actuators, wired network | Monitor and control connected machines and process flows | Optional advanced plant automation; basic balance must work without custom code |

## Candidate Progression Shape

- **Early:** electric drills, basic preparation, simple furnaces, basic fluid handling, and accessible chemical vessels.
- **Middle:** prospecting, flotation, dedicated leaching/solution processing, stronger metallurgy, industrial electrolysis, and reliable circuit control.
- **Late:** high-purity refining, residue recovery, multiblock or high-throughput equipment where needed, cleanrooms, wafer fabrication, advanced fuel/component fabrication, and PLCs.

This is a capability outline, not a locked technology tree. Each stage should add a new operation, route, or diagnostic capability rather than a generic speed tier.

## Route-to-Machine Matrix (To Be Filled)

For every approved route, record:

| Route / product | Input machines | Core process machine | Finishing / recovery | Special constraints |
| --- | --- | --- | --- | --- |
| Candidate | To be selected | To be selected | To be selected | Inputs, catalysts, coproduct destinations, power, pollution |

Do not fill this matrix with speculative exact recipes until the mineral, chemical, and intermediate-product candidates are approved.

## Open Design Questions

- Which operations can reuse vanilla machines, and which deserve a new machine family?
- Should chemical reactors be one configurable family or a few process-specific types (for example, catalytic gas versus liquid-phase reactors)?
- Which routes need multiblocks for meaningful scale, and which can scale by adding ordinary machines?
- How are products, gases, liquids, tailings, slags, and catalyst residues routed without making basic setups fragile?
- Which processes genuinely need catalyst slots, pressure/temperature constraints, or maintenance?
- What is the smallest useful PLC and sensor/actuator set, and which functions remain optional?
- How are machine status, throughput, power draw, and blocked outputs diagnosed in-game?

## Design Gate

A machine or variant should be approved only when its operation, input/output contract, progression role, and downstream product use are clear. A new machine family should correspond to a real process capability or a strong gameplay distinction, not simply a desire to give every reaction its own building.
