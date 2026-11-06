# Factorio Overhaul - Design Overview

*Industrial Ecosystems and Process Engineering — Project Prometheus*

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
| Manufactured intermediates | Alloys, batteries, semiconductor components, nuclear assemblies, and endgame components | [Intermediate Products](intermediate-products.md) |
| Power | Generator phases, fuel density, grid tiers, transmission losses, conductor choices, diagnostics, and waste handling | [Power System](power-system.md) |
| Endgame | Distributed computational civilization; simulation milestones from planetary model → industrial model → information-based beings → general-physics discovery | [Endgame Vision](endgame-vision.md), [Research and Progression](research-progression.md) |
| Machines | Reusable equipment families mapped to industrial operations and progression | [Machine Systems](machine-systems.md) |
| Military | Pollution pressure, ammo/weapon chains, defense infrastructure, process tradeoffs | [Military System](military-system.md) |
| Logistics | Transport layers, demand-based dispatch, freight terminals, information flow | [Logistics System](logistics-system.md) |

### Mining and Refining

All mining tiers provide mineral or resource feeds; they do not each create a separate refining ladder. Surface deposits are finite and simple, underground deposits have a dominant mineral plus traces, and polymineral deposits combine several major minerals. Reusable process templates keep the system learnable while material-specific exceptions are allowed where chemistry warrants them.

### Chemistry and Materials

Chemical chains should connect resource processing to metallurgy, construction, electronics, and the endgame. Each required product needs a straightforward route. Advanced alternatives should unlock later and offer visible tradeoffs. Candidate lists remain provisional until each product has an end use and is approved for the design.

### Endgame Hook

**Build a planetary digital twin by constructing a computational civilization that models an entire simulated world.** The simulation starts with basic physical systems and grows to model populations of information-formed entities — beings composed of structured data, not artificial intelligence. Completing the planetary-scale network unlocks general-physics discovery, extending the player beyond known physics.

The Planetary Simulation Core anchors a distributed network of memory archives, compute campuses, and research/observation facilities — not an AI housed in a building, but a real computational infrastructure dependent on the full industrial ecosystem built earlier.

### Pollution and Military Pressure

Pollution is an economic consequence of industrial choices, not a collection of special-case enemy mechanics. Dirty, high-throughput production may defer costs into military pressure; cleaner routes trade for infrastructure, power, or process complexity.

### Fluids and Process Infrastructure

Fluid transport may distinguish pipe diameter, material compatibility, temperature, pressure, and pump capacity. These are exploratory ideas; they should be retained only where they create transparent engineering choices rather than connection busywork.

### Handbook and Progression

The handbook should reveal the industrial journey early, explain why processes differ, and separate real-world facts from gameplay simplifications. Informatron is a candidate information layer serving as a general reference for background info and lore across all mod systems — mining, chemistry, metallurgy, power, endgame physics — giving players context that enriches the experience without dictating choices.

Research progression follows three phases: conventional science packs (~40–50% of game) → transitional domain packs + conventional (the bridge where conventional industry hits the physics wall) → simulation-gated research (final third, ~100 hours). Conventional packs persist as an alternative path for capabilities that don't require new physics. Fixed capability progression is preferred over random challenge objectives; quest/progression integration remains to be researched.

Phase 4 power generation (Hawking Radiation Engine) is available *during* simulation construction, gated only by building a basic Planetary Simulation Core — not completing it.

## Inspirations and Guardrails

- **GTNH:** geological breadth, real materials, memorable capabilities, and prospecting.
- **Bob's/Angel's:** reusable refining stages and process balancing at an approachable scale.
- **Satisfactory:** situation-dependent alternate production choices.
- **Dyson Sphere Program:** a large computational objective that gives purpose to factory growth.
- **Factorio:** legible logistics, automation, and spatial factory design.

Avoid mandatory upgrades without a new capability, arbitrary complexity, a single correct production route, required voiding, and mechanics whose state cannot be diagnosed clearly.

## Open Design Questions (Active Work Queue)

Items below are the current prioritized design work that needs resolution. Each is a gap that blocks further domain-level detail work until addressed. **This is a task tracker — resolved items should be removed here, not kept as historical notes.** When a question is answered, record the resolution in the appropriate domain document and delete the entry from this list.

### Exhaustive Product Catalog— *Priority 1*
**You've stated this explicitly as your design work; the gap is that the catalog itself isn't yet written.** This is not optional before deep-diving domain documents — it's the skeleton everything else hangs on. Without a complete material pipeline, every process document is building on assumptions.

Sub-gaps to fill in order:
- **Minerals & deposits (mineral-catalog.md?):** Complete list of ore/deposit types with their class (surface/underground/polymineral), location strategy, and what each deposit produces. This connects directly to the Map & World Generation gap.
- **Refined outputs (pure raw materials):** What comes out of your processing stages — ingots, concentrates, refined chemicals, etc. Each needs a clear input-from and output-to so it's not just "it exists in the chain."
- **Intermediate products:** Materials that are inputs to other recipes but have no direct machine use — alloys, acids, reagents, semiconductor precursors, battery chemistries, nuclear assemblies, etc. This is where your chemical-processes.md connects to intermediate-products.md.
- **End products (Phase 3/4 components):** Items that feed the simulation network or represent final capabilities — not "everything in the mod" but things that matter for progression momentum and endgame construction.

Open decisions:
- **Where does this catalog live?** As a single document, distributed across domain docs with cross-references, or a master list file with domain-specific deep dives?
- **Does every intermediate product need multiple routes?** No. Only products that create meaningful tradeoffs get multiple processes. Many can have one good route. Use the Material Scope Boundaries criteria to gate this.
- **What's the catalog format?** A table by pipeline stage (mineral → refined → intermediate → end)? By domain? Something else that makes it useful during design work?

### Endgame Feedback Loop — *Priority 2*
**"Modeling an entire world" is conceptually rich but mechanically underspecified at the strategic level. What does this mean as gameplay decisions?**

Your planetary simulation network has a stronger endgame hook than GTNH ("craft everything") or SE ("launch into space"), but you need to articulate what players actually *do* that feels satisfying — not as UI details, but as a strategic loop.

Open decisions:
- **What is the gameplay verb of Phase 3/4?** Not "build a big thing." What decision-making keeps players engaged for 100 hours? Feeding factories? Running models? Debugging information-formed entities? Competing objectives?
- **How does pre-simulation industrial work feed into simulation play?** If the answer is "the factories I built before become part of a bigger system," that's good — but needs articulation to guide remaining domain work.
- **What's the endgame tension or choice?** GTNH's endgame has no tension (you can craft everything). SE has logistics as its only tension. Your endgame needs something equally intrinsic to the mechanic itself.
- **Does completing the simulation win the game or open new gameplay?** This intersects with Victory Condition gap above — but is more specific: what does "completing" mean, and what happens after?

### Victory Condition & Game End State — *Priority 3*
We've deferred "Does completing the planetary digital twin unlock further gameplay?" without resolving it:
- Is the game winnable or endless sandbox with milestones?
- What's the final moment if won? A visual event in-game? Launching something? Activating the simulation network?
- If not won, what replaces "launch rockets" as the north star once the simulation is complete?

### Combat & Warfare System — Open
"Pollution pressure" and ammo chains are sketched but the enemy itself is underspecified:
- **What are the enemies?** Mutant creatures? Indigenous life reacting to industrial encroachment? Something thematically aligned with Prometheus?
- **How does pollution scale into attacks?** Distance-based (closer factories = more attacks)? Frequency-based (dirty production → constant pressure vs. clean → occasional raids)?
- **Military defense vs. industrial capability.** Does better ammo require advanced chemistry, or is there a separate supply chain?

### Mod Compatibility & Scope Boundaries — Open
This is a Factorio mod that exists in an ecosystem:
- Standalone or compatible with vanilla tech tree? Replaces Bob's and Angel's?
- How does massive complexity impact save file size and performance?

## Decisions Still Open

### General (Unresolved)

- **Mod title/name:** *Project Prometheus* is the current leaning. Final call should wait until endgame fantasy is set in stone.
- **Final victory condition specifics:** Is completing the planetary digital twin *itself* the win condition? Or does it unlock further gameplay (new physics discoveries, space expansion)? What exactly "completes" — building all facilities to a certain capacity, achieving a fidelity threshold, or running a specific final model?

### Domain-Specific Decisions (Link Out)

Below is a summary of open design decisions tracked in each domain document. Use these links for detailed decision tracking during deep-dive work.

- **[Minerals and Refining](minerals-and-refining.md):** Final mineral roster, real deposit classes, assays, material recovery assignments; process template consistency across routes.
- **[Chemical Products and Processes](chemical-processes.md):** Approved chemical inventory and reaction routes; catalyst requirements for key reactions.
- **[Intermediate Products](intermediate-products.md):** Specific battery chemistry selection (not every formulation), coherent fission reactor family choice (don't combine every real-world option).
- **[Power System](power-system.md) — Production:** Exact combustion generators for Phase 1, U-235 vs Pu-239 fission paths, fusion-endgame connection, renewable generation explicit presence, military pressure contribution per generator class, waste handling depth for fission.
- **[Power System](power-system.md) — Transmission:** Voltage tiers and exact values, conductor stats/loss formulas, loss modeling approach, diagnostics UI specifics, onboarding structure.
- **[Endgame Vision](endgame-vision.md):** Simulation fidelity tiers (basic → accurate → predictive model), final milestone structure (single vs. staged), compute distribution requirements, power/cooling/network constraints for Core, PLC interaction without mandating general-purpose coding.
- **[Research and Progression](research-progression.md):** ✅ Six domains locked (Superconductivity, Plasma Confinement, Nanofabrication, Isotope Separation/Particle Physics, Reaction Dynamics, Quantum States). Domain pack tier structure T1→T2a→T2b1→T2b2→T3a→T3b→T3c. Progressive revelation schedule (5 waves). Core requirements per stage. Technology roster pending mineral/chemical stabilization.
