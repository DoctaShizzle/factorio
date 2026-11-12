# Factorio Overhaul - Design Overview

*Industrial Ecosystems and Process Engineering — Project Prometheus*

*Status: Working design overview; detailed systems and unapproved proposals remain with their domain owners.*  
*Last updated: 2026-11-12*

This document records cross-domain intent and the active design queue. The phase order is maintained in [plan.md](plan.md); accepted decisions and historical rationale are linked to their owning design documents and ADRs.

## The Story That Unfolds

You start with a pickaxe, raw ore, and the knowledge that something bigger awaits. You build factories. Then you refine them. Then you push past what your own industrial civilization can discover on its own.

**At the end of the journey: you build a planetary simulation network capable of modeling an entire world — and the beings within it.** These are not artificial intelligence, but information-formed entities that perceive, decide, and interact with their modeled reality. By demonstrating mastery over every domain of industrial capability, you earn access to general-physics discovery — extending humanity's reach beyond what conventional science alone could achieve.

This is a story about *understanding the universe well enough to push past its limits.* The industrial ecosystem isn't decoration for the endgame; it's the prerequisite for reaching it.

## Summary

This document defines the mod's design philosophy, core pillars, and intended scope. All system-specific details live in the linked documents below.

## Mission

Build a coherent industrial ecosystem where extraction, refining, metallurgy, chemistry, power, pollution, military pressure, semiconductors, and endgame research support one another.

The player should feel less like a factory builder following longer recipe chains and more like an industrial engineer choosing and balancing processes.

## Design North Star

> Realism is valuable when it creates meaningful engineering decisions. The goal is not to simulate industry exhaustively; it is to help players think like industrial engineers.

### Pillars

- **Multiple processes:** major products should have viable alternatives where those alternatives create real choices.
- **Tradeoffs over linear upgrades:** prioritize resource efficiency, pollution/military pressure, and capital complexity. Throughput, power, and space are useful secondary constraints.
- **Processes over recipes:** present the question "Which process should I use?" rather than only "Which recipe unlocks next?"
- **Refining creates options:** additional capability reveals recoverable materials and alternate routes, not just higher yields.
- **Equilibrium over disposal:** buffers may help production, but required voiding or permanent accumulation is not an acceptable solution.
- **Capabilities over numbers:** prospecting, flotation, chemical refining, cleanrooms, programmable control, and simulation infrastructure are memorable progression goals.
- **Knowledge before capability:** show the industrial journey in the handbook before every step can be built; unlock implementation gradually.

### Material Description Guideline

All material, product, and facility names must include a clear description that answers two questions for non-scientists: **what happens** (concrete physical property or behavior) followed by **why it matters** (the implication). This follows the pattern used by Satisfactory and Space Exploration — accessible without sacrificing accuracy.

Structure for every material/product description: *"At [extreme/condition], [material] does [unexpected thing]. It [enables/solves] [capability]." *Examples from Phase 2 products:*

- **Electronic-grade polysilicon:** *"Silicon purified to a level where every impurity matters — one wrong atom in a billion changes how it conducts electricity. At this purity, silicon doesn't just conduct or insulate; you can choose which state it's in by adding the right trace element."*
- **Nb₃Sn superconducting wire:** *"When cooled below a threshold, this alloy carries electric current with zero resistance — and generates magnetic fields strong enough to confine plasma at temperatures hotter than the sun's core. It's one of the few materials that can survive both."*

Apply this standard to all materials, products, facilities, and recipes across every domain document.

### Mod Title (hold until endgame locked)

The name should reflect the core hook/fantasy so the title itself telegraphs what the player is doing — not just what they do, but *why it matters*. Brainstormed directions:

| Candidate | Tone | Why it works / falls short |
|---|---|---|
| *Industrial Evolution* | Descriptive | Safe, readable, but "Evolution" is overused for anything incremental. Doesn't make anyone lean in. |
| *Industrial Genesis* | Evocative + grounded | Stronger than above. Connects to the first-industry fantasy, but still reads a bit textbook-ish. |
| *Genesis Protocol* | System-focused, cool | "Protocol" leans heavily toward computation/rules. If the endgame is computational civilization, this maps well — but it obscures the industrial/physical side that's 80% of the gameplay. |
| **Project Prometheus** *(recommended)* | Mythological + grounded | **Prometheus brought fire to the world against divine odds.** The player's arc — starting from dirt and ore, layering process after process, until building something planetary-scale — maps directly onto that metaphor. "Project" keeps it engineering-quality rather than pure mythology. It stays on your mind after you hear it. |
| *Synthetic Dawn* | Poetic, abstract | Evocative but nobody looks at it and knows what they're playing. Could be any sci-fi base-builder. Loses the industrial anchor entirely. |

**Recommendation: Project Prometheus.** If one name does half the job of explaining the fantasy to a newcomer, it's worth choosing early — *once* the endgame is locked so the metaphor aligns with the actual ending state.

## Intended Scope

The ambition is a long overhaul playthrough, potentially 300+ hours, with complexity between Bob's/Angel's and Pyanodon's. That duration should come from geological discovery, process choice, logistics, cross-chain planning, and capability progression, not recipe inflation alone. The mineral roster and shared process vocabulary should remain bounded and learnable.

## Industrial System Map

| System | Design role | Working document |
| --- | --- | --- |
| Mineral catalog | Candidate deposits, mineral feeds, recoverable materials, and common route patterns | [Minerals and Refining](minerals-and-refining.md) |
| Chemistry | Named industrial reactions, coproducts, alternative pathways, catalysts, and chemical intermediates | [Chemical Products and Processes](chemical-processes.md) |
| Non-building product catalog | Construction materials and components, fuels, vehicles, weapons and ammunition, personal equipment and modules, research ingredients, and endgame products; includes a Factorio-family completeness checklist | [Intermediate Products](intermediate-products.md); see [Infrastructure](infrastructure.md) for placeable entities |
| Power | Generation candidates and power-related scope; the core retains the vanilla grid with compatible tiered poles, while custom voltage/loss systems remain extension candidates | [Power System](power-system.md) |
| Endgame | Distributed computational civilization; simulation milestones from planetary model → industrial model → information-based beings → general-physics discovery | [Endgame Vision](endgame-vision.md), [Research and Progression](research-progression.md) |
| Infrastructure | Infrastructure mapped to industrial operations, progression, logistics and military | [Infrastructure](infrastructure.md) |
| Military | Pollution pressure, ammo/weapon chains, defense infrastructure, process tradeoffs | [Military System](military-system.md) |
| Logistics | Transport layers, demand-based dispatch, freight terminals, information flow | [Logistics System](logistics-system.md) |
| Technical architecture | Modpack structure, dependencies, performance constraints, extension packs | [Technical Architecture](technical-architecture.md) |

### Mining and Refining

All mining tiers provide mineral or resource feeds; they do not each create a separate refining ladder. Surface deposits are finite and simple, underground deposits have a dominant mineral plus traces, and polymineral deposits combine several major minerals. Reusable process templates keep the system learnable while material-specific exceptions are allowed where chemistry warrants them.

### Chemistry and Materials

Chemical chains should connect resource processing to metallurgy, construction, electronics, and the endgame. Each required product needs a straightforward route. Advanced alternatives should unlock later and offer visible tradeoffs. Candidate lists remain provisional until each product has an end use and is approved for the design.

### Endgame Hook

**Current direction:** build a planetary digital twin through a distributed computational civilization that models an entire world, including populations of information-formed entities — beings composed of structured data, not artificial intelligence. General-physics discovery is a candidate endgame outcome; whether it is the win condition or opens further gameplay remains unresolved.

The Planetary Simulation Core anchors a distributed network of memory archives, compute campuses, and research/observation facilities — not an AI housed in a building, but a real computational infrastructure dependent on the full industrial ecosystem built earlier.

### Pollution and Military Pressure

Pollution is an economic consequence of industrial choices, not a collection of special-case enemy mechanics. Dirty, high-throughput production may defer costs into military pressure; cleaner routes trade for infrastructure, power, or process complexity.

### Fluids and Process Infrastructure

Fluid transport may distinguish pipe diameter, material compatibility, temperature, pressure, and pump capacity. These are exploratory ideas; they should be retained only where they create transparent engineering choices rather than connection busywork.

### Handbook and Progression

The handbook should reveal the industrial journey early, explain why processes differ, and separate real-world facts from gameplay simplifications. Informatron is a candidate information layer serving as a general reference for background info and lore across all mod systems — mining, chemistry, metallurgy, power, endgame physics — giving players context that enriches the experience without dictating choices.

The current research direction uses three phases: conventional science → a conventional/domain-pack bridge → simulation-gated research. Seven distinct domain-pack tiers and the first-Core gate (all six domains at T2b2 plus the Unified Metrology Reference Array) are selected in [ADR-0020](adrs/ADR-0020-seven-distinct-domain-pack-tiers.md) and [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md). Exact pack inputs, higher Core gates, technology assignments, and final timing remain open. Conventional packs may persist for capabilities that do not require new physics. Fixed capability progression is preferred over random challenge objectives; quest/progression integration remains to be researched.

The Hawking Radiation Engine is one accepted Phase 4 power option, not the sole route. At least three distinct options in each of Phases 3 and 4, including concentrated solar thermal in Phase 3, are selected in [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md). Phase 1/2 boundaries, the Phase 2-or-later PV floor, and the thorium startup-seed model are recorded in [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md), [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md), and [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md). Construction and research gates, relative output, and the Core relationship remain open.

## Inspirations and Guardrails

- **GTNH:** geological breadth, real materials, memorable capabilities, and prospecting.
- **Bob's/Angel's:** reusable refining stages and process balancing at an approachable scale.
- **Satisfactory:** situation-dependent alternate production choices.
- **Dyson Sphere Program:** a large computational objective that gives purpose to factory growth.
- **Factorio:** legible logistics, automation, and spatial factory design.

Avoid mandatory upgrades without a new capability, arbitrary complexity, a single correct production route, required voiding, and mechanics whose state cannot be diagnosed clearly.

## Open Design Questions (Active Work Queue)

Items below are cross-domain open questions, not an approval list. Phase order and gates live in [plan.md](plan.md); not every question blocks every domain detail. Record resolutions in the owning design document and, when significant, a linked ADR; remove resolved items from this active queue.

### Exhaustive Product Catalog— *Priority 1*
The full catalog has not yet been enumerated. The agreed work order is to verify the gap analysis and align infrastructure before building complete coverage and then enumerating products, recipes, and research; see [plan.md](plan.md).

Sub-gaps to fill in order:
- **Minerals & deposits:** Complete list of ore/deposit types with their class (surface/underground/polymineral), location strategy, and outputs belongs in [Minerals and Refining](minerals-and-refining.md), coordinated with [Map and World Generation](map-world-generation.md). `mineral-catalog.md` was only a placeholder filename, not a separate source.
- **Refined outputs (pure raw materials):** What comes out of your processing stages — ingots, concentrates, refined chemicals, etc. Each needs a clear input-from and output-to so it's not just "it exists in the chain."
- **Intermediate products:** Materials that are inputs to other recipes but have no direct machine use — alloys, acids, reagents, semiconductor precursors, battery chemistries, nuclear assemblies, etc. This is where your chemical-processes.md connects to intermediate-products.md.
- **End products (Phase 3/4 components):** Items that feed the simulation network or represent final capabilities — not "everything in the mod" but things that matter for progression momentum and endgame construction.

**Candidate chemistry guardrail:** Batch similar chemical processes where possible and avoid creating a unique fluid for every minor variation; group chemically similar fluids where this preserves meaningful process choices. The source draft's performance claims about particular fluid chains are unbenchmarked and are not treated as verified engine constraints; see [Technical Architecture](technical-architecture.md).

Open decisions:
- **Coverage source:** [plan.md](plan.md) assigns the canonical product-coverage ledger to Phase 4; detailed process and domain design remains in the owning documents. Its exact schema is still open.
- **Alternative routes:** The current plan calls for multiple routes only where they create meaningful tradeoffs; a single good route is acceptable otherwise.

### Victory Condition & Game End State — *Priority 2*
What "completing" the planetary digital twin *looks like* and what it *unlocks* is still open. The leading candidate: **general-physics discovery** — pushing beyond known physics after demonstrating mastery of every industrial domain. But the specifics need defining.

Open questions:
- Is the game winnable or endless sandbox with milestones?
- What's the final moment if won? A visual event in-game? Launching something? Activating the simulation network?
- Does "general-physics discovery" mean new research categories, new physics capabilities (e.g., matter manipulation), or a final event/sequence?
- If not won, what replaces "launch rockets" as the north star once the simulation is complete?

This intersects with Endgame Feedback Loop in [research-progression.md](research-progression.md), but this section owns the decision; that section handles implementation details.

### Open Technology Roster — *Priority 3*
**The full technology roster hasn't been defined yet.** This blocks all domain documents because every tech tree depends on knowing what materials and capabilities exist. See the WIP matrix and classification rules in [research-progression.md](research-progression.md) for working structure.

### Combat & Warfare System
"Pollution pressure" and ammo chains are sketched but the enemy itself is underspecified:
- **What are the enemies?** Mutant creatures? Indigenous life reacting to industrial encroachment? Something thematically aligned with Prometheus?
- **How does pollution scale into attacks?** Distance-based (closer factories = more attacks)? Frequency-based (dirty production → constant pressure vs. clean → occasional raids)?
- **Military defense vs. industrial capability.** Does better ammo require advanced chemistry, or is there a separate supply chain?

## Open Items by Domain

Each domain document tracks its own open decisions at the bottom of that doc — use these links for detailed decision tracking during deep-dive work.

| Document | Key Open Decisions |
|---|---|
| [Minerals and Refining](minerals-and-refining.md) | Final mineral roster, real deposit classes, assays, material recovery assignments; aluminum/alumina are Phase 2 or later, and basic salt/brine access is early Phase 2 |
| [Chemical Products and Processes](chemical-processes.md) | Validate product and reaction entries, routes, and catalysts; all process-family concepts currently documented are in Core scope under ADR-0024 |
| [Intermediate Products](intermediate-products.md) | Validate selected bridge-product routes and facility bills of materials; pre-Core supply for candidate packaged ICs and positioning stages; specific battery chemistry selection |
| [Power System](power-system.md) — Production | Exact combustion-fuel items, uranium/thorium fuel routes and balance, the first Phase 2 PV-cell route, construction/research gates, fusion/endgame connection, and military-pressure contribution per generator class; Phase 3/4 route identities are selected |
| [Power System](power-system.md) — Distribution | Compatible tiered-pole levels and stats; custom voltage, conductor-loss, and grid-stabilization mechanics remain optional extension candidates, not core requirements |
| [Endgame Vision](endgame-vision.md) | Pre-Core source for candidate Core electronics and positioning materials; Array support inputs; higher Core gates, final milestone structure, and compute distribution |
| [Research and Progression](research-progression.md) | Seven distinct tiers per domain and the T2b2 first-Core gate are selected; exact pack items/recipes, later Core gates, technology roster, and timing remain open |
| [Infrastructure](infrastructure.md) | Machine-family tier coverage, vanilla-versus-new entity dispositions, and exact construction assignments remain provisional; Phase 2 polysilicon precursor purification and the Phase 2-or-later PV boundary are aligned; former Machine Systems content is subsumed here |
| [Technical Architecture](technical-architecture.md) | Candidate packaging and extension model, unvalidated scope estimates, dependencies, and performance hypotheses; none are hard limits until verified |
