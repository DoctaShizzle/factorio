# Endgame Vision - Distributed Planetary Computing

*For: Factorio Overhaul Mod*  
*Status: Vision / requirements phase*

Related documents: [Mod Overview](mod-overview.md), [Intermediate Products](intermediate-products.md), and [Power System](power-system.md).

## North Star

The endgame is the creation of computational capacity capable of running a planetary-scale industrial simulation. The goal is not one giant megastructure. It is a network of specialized facilities spread across the map, each dependent on the industrial ecosystem built earlier.

The player should feel that the simulation network is the culmination of mining, refining, metallurgy, chemistry, power, electronics, logistics, and factory control.

## Candidate Facility Chain

```text
Purified mineral feeds
        -> semiconductor-grade silicon and specialty materials
        -> wafer fabrication
        -> processor fabrication and packaging
        -> regional supercomputer facilities
        -> distributed simulation cluster
        -> planetary research center
```

This is a conceptual dependency chain, not a fixed sequence of buildings. Facilities may be distributed, duplicated, or connected by logistics and power infrastructure according to the final design.

## What the Network Needs

| Capability | Candidate industrial dependencies |
| --- | --- |
| Semiconductor fabrication | Electronic-grade silicon, dopants, photoresist chemistry, specialty gases, ultra-pure copper and barrier metals, cleanroom capability |
| Processor production | Fabricated wafers, advanced interconnects, packaging materials, precision manufacturing |
| Regional compute | Packaged processors, cooling, stable power, data/network infrastructure |
| Simulation cluster | Multiple compute sites, high-capacity power, thermal management, synchronization/control systems |
| Planetary research | Distributed simulation capacity, research facilities, continued supply of advanced components |

Specific material recipes belong in the [Intermediate Products](intermediate-products.md) map; chemical syntheses and purification reactions belong in [Chemical Products and Processes](chemical-processes.md).

## Design Principles

- **Distributed, not monolithic:** the final achievement spans multiple facilities and locations.
- **Capability milestones:** unlock cleanrooms, wafer fabrication, advanced packaging, and simulation infrastructure rather than a sequence of generic numerical upgrades.
- **Cross-chain demand:** the endgame should pull distinct materials from mining/refining, chemistry, metallurgy, and power systems.
- **Meaningful placement:** regional facilities should create logistics, cooling, power, and land-use decisions.
- **Legible progress:** the handbook and factory UI should show the network's outstanding dependencies and completed capabilities.
- **No arbitrary disposal:** excess and coproducts remain governed by the same balanceability rules as the rest of the mod.

## Open Design Decisions

- What exactly does a planetary simulation accomplish in gameplay: unlock technologies, enable factory automation, complete a final research project, or some combination?
- Is there a single final milestone, or a staged set of regional commissioning goals?
- How much of the compute network must be physically distributed to make the spatial requirement meaningful without becoming arbitrary busywork?
- What are the power, cooling, and network constraints, and which are core versus optional optimization?
- How will PLCs and simulation infrastructure interact without making a general-purpose control language mandatory for victory?
- What is the endgame's intended playtime contribution within the broader 300+ hour overhaul ambition?

The final victory condition and exact recipes are deliberately not fixed yet. They should be designed after the industrial material roster and capability progression are stable.
