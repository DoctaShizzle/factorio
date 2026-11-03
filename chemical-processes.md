# Chemical Products and Processes

*For: Factorio Overhaul Mod*  
*Status: Design reference / requirements phase*

Related documents: [Material Chain Map](material-chain-map.md) for deposits, minerals, and refining; [Intermediate Products](intermediate-products.md) for alloys, components, and manufactured materials.

## Purpose and Boundaries

Chemistry is an industrial decision layer, not a catalog of reactions for its own sake. Use real process names and useful intermediates to teach how industrial chains connect, while simplifying kinetics and plant design into understandable factory choices.

- Give every required product one clear, reliable happy path.
- Add alternatives when they create meaningful differences in resource recovery, pollution, infrastructure, or product quality.
- Reveal advanced options through capability unlocks; keep future processes visible in the handbook before they are buildable.
- Keep reaction chains and chemical products here. Track solid alloys, components, and assemblies in the [Intermediate Products](intermediate-products.md) document.
- Treat recipe ratios and simplified reactions as gameplay abstractions, and distinguish them from universal real-world assays in educational text.

## Core Chemical Chains

These four chains are the initial chemistry scope. Each needs a readable first route; alternatives are added only when they earn their complexity.

| Chain | Straightforward route | Later choice / capability | Connects to |
| --- | --- | --- | --- |
| Sulfuric acid | Sulfur or sulfide off-gas -> sulfur dioxide -> contact process -> acid | Capture and clean off-gas; catalyst and purity tradeoffs | Leaching, metal recovery, batteries, semiconductor processing |
| Chlor-alkali | Purified brine -> electrolysis -> chlorine + sodium hydroxide + hydrogen | Brine purification, cell configuration, coproduct balancing | Bayer alumina refining, metal leaching, PVC, hydrogen reduction |
| Plastics and polyethylene | Oil -> petrochemical feed -> ethylene -> polymerization -> plastic | Alternate cracking feeds and catalyst/polymer grades | Construction, fluid infrastructure, electronics |
| Cement and lime | Limestone -> calcination -> lime + carbon dioxide -> clinker/cement | Fuel choice, emissions capture, slag and residue use | Construction, steelmaking, endgame infrastructure |

These are process families, not final recipes. Exact inputs, yields, and machine counts remain open.

## Later Chemical Candidates

| Candidate | Real process idea | Potential gameplay role |
| --- | --- | --- |
| Ammonia / nitric acid | Haber-Bosch followed by Ostwald oxidation | Fertilizer, explosives, and catalyst-dependent nitrogen chemistry |
| Nylon and engineering polymers | Benzene-derived intermediates to adipic acid and polyamide | Alternative materials for machinery and advanced infrastructure |
| Titanium chemistry | Chlorination to TiCl4 followed by magnesium reduction (Kroll process) | A high-capital, high-purity metal capability; detailed route also appears in the refining design |
| Nuclear fuel chemistry | Uranium conversion and oxide fuel fabrication; optional thorium-to-U-233 cycle | A later fission capability if nuclear power is part of the mod; see [Intermediate Products](intermediate-products.md) |
| Fusion fuel handling | Deuterium supply and tritium extraction/recycling from a lithium breeder loop | Late-game chemical separation linked to fusion infrastructure |

Before promoting a candidate into the core scope, verify that it connects to existing chains, unlocks a capability, creates a meaningful tradeoff, and has enough educational value to justify its footprint.

## Chemical Product Index

This is a candidate index of chemical products and intermediates. It is not a commitment to implement every entry.

| Family | Candidate products / intermediates |
| --- | --- |
| Sulfur | Sulfur dioxide, sulfur trioxide, sulfuric acid, sulfates |
| Brine and electrolysis | Brine, chlorine, sodium hydroxide, hydrogen |
| Nitrogen | Ammonia, nitric acid, nitrate salts |
| Carbon and mineral chemicals | Coke, producer gas, carbon dioxide, activated carbon, calcium carbide, acetylene |
| Petrochemistry | Naphtha, ethylene, propylene, benzene, hydrogen |
| Polymers and resins | HDPE/LDPE, PVC, nylon 6,6, epoxy, fluoropolymer |
| Semiconductor chemistry | Trichlorosilane, photoresist precursors, WF6, SF6, NF3, deposition and etch gases |
| Nuclear and fusion chemistry | Uranium oxide fuel intermediates, lithium-bearing breeder material, deuterium, recovered tritium |

## Process Equipment and Catalysts

Choose equipment around process needs rather than introducing a unique machine for every reaction. Candidate families include catalytic gas reactors, electrolysis cells, stirred liquid reactors, thermal furnaces, and polymerization vessels. A machine family may support multiple recipes when the operation is similar.

Catalysts are physical process inputs or machine components where they create a legible choice. Different catalysts can shift selectivity, yield, purity, or operating cost. Some real catalysts deactivate and need regeneration or replacement; do not make all catalysts consumable by default.

## Balance and Factory Control

- Route templates should have stable output proportions across compatible feed profiles; the material identities vary with the feed.
- Every coproduct needs a useful downstream route, an optional recovery path, a bounded operating buffer, or feed throttling when demand is saturated.
- Avoid recipes whose intended operation depends on voiding useful products. Short buffers are acceptable; permanent accumulation is a warning to revisit ratios or applications.
- Smart routing and circuits should support stable operation. PLCs may automate complex plant control, but should not be required for basic balance.
- Show inputs, outputs, coproducts, and known uses in the handbook so players can understand a route before building it.

## Educational Content

Each handbook entry should briefly distinguish the real industrial process from the simplified game recipe. Explain what the process makes, why an alternative exists, and which details are abstracted for play. Use trustworthy references for the facts; do not present invented yields, catalyst lifetimes, or universal ore assays as real data.

## Inspiration

- **GregTech / GTNH:** memorable named reactions, real intermediates, and capability milestones; avoid its complexity wall and exhaustive reaction count.
- **Bob's / Angel's:** recognizable processing patterns and accessible chains; improve clarity around route choice and coproduct balancing.
- **Dyson Sphere Program:** keep chemistry connected to the factory's larger computational endgame rather than making it a detached subgame.

The target is meaningful industrial understanding with a bounded set of repeatable process patterns, not a fixed number of recipes or hours of playtime.
