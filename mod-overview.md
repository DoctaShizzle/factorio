# Factorio Overhaul - Design Overview

*Industrial Ecosystems and Process Engineering*  
*Status: Broad design proposal; system details live in linked documents*

## Summary

This document defines the mod's north star, core pillars, and intended scope. It establishes the mission (an industrial ecosystem where extraction, refining, metallurgy, chemistry, power, pollution, military pressure, semiconductors, and endgame research support one another) and the player identity — an industrial engineer choosing and balancing processes, not a factory builder following longer recipe chains.

**Scope:** Design philosophy, system map, key pillars (multiple processes, tradeoffs over upgrades, capabilities over numbers), inspirations and guardrails, and decisions still open. All system-specific details live in the eight linked documents below.

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
| Endgame | Distributed computational civilization; simulation milestones from planetary model → industrial model → agent-based civilization → general-physics discovery | [Endgame Vision](endgame-vision.md), [Research and Progression](research-progression.md) |
| Machines | Reusable equipment families mapped to industrial operations and progression | [Machine Systems](machine-systems.md) |
| Military | Pollution pressure, ammo/weapon chains, defense infrastructure, process tradeoffs | [Military System](military-system.md) |
| Logistics | Transport layers, demand-based dispatch, freight terminals, information flow | [Logistics System](logistics-system.md) |

### Mining and Refining

All mining tiers provide mineral or resource feeds; they do not each create a separate refining ladder. Surface deposits are finite and simple, underground deposits have a dominant mineral plus traces, and polymineral deposits combine several major minerals. Reusable process templates keep the system learnable while material-specific exceptions are allowed where chemistry warrants them.

### Chemistry and Materials

Chemical chains should connect resource processing to metallurgy, construction, electronics, and the endgame. Each required product needs a straightforward route. Advanced alternatives should unlock later and offer visible tradeoffs. Candidate lists remain provisional until each product has an end use and is approved for the design.

### Endgame Hook

**Build a planetary digital twin by constructing a computational civilization that models an entire simulated world.** The simulation starts with basic physical systems and grows to model agent-like entities that think and make decisions. Completing the planetary-scale network unlocks general-physics discovery, extending the player beyond known physics.

The Planetary Simulation Core anchors a distributed network of memory archives, compute campuses, and research/observation facilities — not an AI housed in a building, but a real computational infrastructure dependent on the full industrial ecosystem built earlier.

### Pollution and Military Pressure

Pollution is an economic consequence of industrial choices, not a collection of special-case enemy mechanics. Dirty, high-throughput production may defer costs into military pressure; cleaner routes trade for infrastructure, power, or process complexity.

### Programmable Automation

A general-purpose PLC system is a candidate capability: connected sensors and actuators, a constrained in-game programming interface, and tools for testing and debugging. It may automate complex plant balancing, but basic factory stability must remain achievable with ordinary routing and circuit logic. Language, API, and scope are undecided.

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

## Decisions Still Open

### General (Unrelated to Domain-Specific Documents)

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
- **[Research and Progression](research-progression.md):** Exact technology roster (which gates on what simulation level), simulation fidelity tier design and upgrades, hybrid research path availability, final victory condition specifics, playtime allocation within 300+ hours.
