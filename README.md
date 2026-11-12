# Project Prometheus — Factorio Overhaul Mod

*A deep industrial ecosystem where you are an industrial engineer, not a factory builder following longer recipe chains.*

## The Premise

Build a coherent industrial civilization from scratch — mining, refining, chemistry, metallurgy, power, semiconductors — then construct a **planetary simulation network** that models the world itself and unlocks the ability to push beyond known physics.

The arc: *"Starting from dirt and ore, layering process after process, until building something planetary-scale."* — named for Prometheus, who brought fire to the world against divine odds.

## Design North Star

> *Realism is valuable when it creates meaningful engineering decisions. The goal is not to simulate industry exhaustively; it is to help players think like industrial engineers.*

### Pillars

| Pillar | Meaning |
|---|---|
| **Multiple processes** | Major products have viable alternatives that create real choices |
| **Tradeoffs over upgrades** | Resource efficiency, pollution, complexity — not just raw numbers |
| **Processes over recipes** | "Which process should I use?" instead of "What's the next unlock?" |
| **Refining creates options** | More capability reveals alternate routes, not just higher yields |
| **Equilibrium over disposal** | No required voiding or permanent accumulation |
| **Capabilities over numbers** | Prospecting, cleanrooms, simulation infrastructure are progression goals |
| **Knowledge before capability** | The handbook explains every step before it can be built |

## What's Covered by This Mod?

| Domain | Scope | Document |
|---|---|---|
| Minerals & refining | Deposit classes, process templates, mineral recovery | [Minerals and Refining](minerals-and-refining.md) |
| Chemistry | Industrial reactions, coproducts, catalysts | [Chemical Products and Processes](chemical-processes.md) |
| Non-building products | Construction materials, components, fuels, vehicles, weapons and ammunition, personal equipment and modules, research ingredients, and endgame products | [Intermediate Products](intermediate-products.md) |
| Power | Candidate generation progression with multiple late-game routes; Hawking is one accepted Phase 4 option, and the vanilla grid gains tiered poles | [Power System](power-system.md) |
| Endgame | Planetary simulation network, general-physics discovery | [Endgame Vision](endgame-vision.md) |
| Machines | Reusable equipment families across industrial stages | [Machine Systems](machine-systems.md) |
| Military | Pollution pressure, ammo chains, defense infrastructure | [Military System](military-system.md) |
| Logistics | Belts, trains, demand-based dispatch, information flow | [Logistics System](logistics-system.md) |
| Research | Three-phase progression (conventional → domain packs → simulation-gated) | [Research and Progression](research-progression.md) |

## Key Design Decisions (Current State)

- **Title:** *Project Prometheus* (recommended; see [mod-overview.md](mod-overview.md) for candidates)
- **Progression shape:** Conventional science (~40–50% game) → domain packs + conventional bridge → simulation-gated research (final ~100 hours)
- **Endgame goal:** Build a planetary simulation network that models information-formed entities (structured-data beings, not AI) and unlocks general-physics discovery
- **Phase 4 power:** Hawking Radiation Engine is one accepted option. Its gate remains open, and at least one alternative Phase 3/4 route must be developed.
- **Research items:** Science-pack-style buildings producing "readings and results" — same mechanic as vanilla science packs, re-themed

## How to Dive In

1. Read **[mod-overview.md](mod-overview.md)** for the full design philosophy, system map, inspirations, guardrails, and open decisions (with links to each domain doc)
2. Pick a domain that interests you — each linked document tracks its own open decisions separately
3. Use the [Domain-Specific Decisions](mod-overview.md#domain-specific-decisions-link-out) section at the bottom of mod-overview.md to navigate to which docs need work

## Inspirations

- **GTNH** — geological breadth, real materials, memorable capabilities
- **Bob's/Angel's** — reusable refining stages, process balancing
- **Satisfactory** — situation-dependent alternate production choices
- **Dyson Sphere Program** — a large computational objective giving purpose to factory growth
- **Factorio** — legible logistics, automation, and spatial factory design

## Guardrails

Avoid: mandatory upgrades without new capability, arbitrary complexity, a single correct production route, required voiding, mechanics whose state cannot be diagnosed clearly.

## Status

Broad design proposal. System details live in linked documents. See [mod-overview.md](mod-overview.md) for the full list of open decisions by domain.
