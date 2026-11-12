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
| Infrastructure | Candidate placeable buildings, machine families, construction demands, and infrastructure categories | [Infrastructure](infrastructure.md) |
| Power | Vanilla grid retained with compatible tiered poles; Phase 1 combustion, Phase 2-or-later PV, Phase 2 uranium/thorium fission, and at least three selected routes in each of Phases 3 and 4 | [Power System](power-system.md) |
| Endgame | Planetary simulation network, general-physics discovery | [Endgame Vision](endgame-vision.md) |
| Military | Pollution pressure, ammo chains, defense infrastructure | [Military System](military-system.md) |
| Logistics | Belts, trains, demand-based dispatch, information flow | [Logistics System](logistics-system.md) |
| Research | Three-phase progression (conventional → domain packs → simulation-gated) | [Research and Progression](research-progression.md) |

## Current Design Direction and Accepted Decisions

- **Title:** *Project Prometheus* is the recommended working title; see [mod-overview.md](mod-overview.md) for alternatives.
- **Progression shape:** A conventional → domain-pack bridge → simulation-gated arc is the current direction. Seven distinct domain-pack tiers and the first-Core gate are selected in [ADR-0020](adrs/ADR-0020-seven-distinct-domain-pack-tiers.md) and [ADR-0017](adrs/ADR-0017-phase-2-core-and-bridge-prerequisites.md); exact pack inputs, higher gates, and timing remain open.
- **Endgame direction:** Build a distributed planetary simulation network that models information-formed entities (structured-data beings, not AI); final victory and unlock conditions remain open.
- **Power progression:** Phase 1/2 boundaries are recorded in [ADR-0019](adrs/ADR-0019-phase-1-and-2-power-progression.md), and Phase 3/4 routes and converters in [ADR-0018](adrs/ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md); the solar boundary and thorium startup model are in [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md) and [ADR-0023](adrs/ADR-0023-thorium-startup-seed-and-breeding-model.md). See [Power System](power-system.md) for current design.
- **Research items:** Six domain facilities and their one-to-one bridge mappings are selected; exact pack inputs, facility bills of materials, and research mechanics remain open.

## How to Dive In

1. Read **[mod-overview.md](mod-overview.md)** for the full design philosophy, system map, inspirations, guardrails, and open decisions (with links to each domain doc)
2. Pick a domain that interests you — each linked document tracks its own open decisions separately
3. Use [Open Items by Domain](mod-overview.md#open-items-by-domain) to find unresolved work owned by each design document.

## Inspirations

- **GTNH** — geological breadth, real materials, memorable capabilities
- **Bob's/Angel's** — reusable refining stages, process balancing
- **Satisfactory** — situation-dependent alternate production choices
- **Dyson Sphere Program** — a large computational objective giving purpose to factory growth
- **Factorio** — legible logistics, automation, and spatial factory design

## Guardrails

Avoid: mandatory upgrades without new capability, arbitrary complexity, a single correct production route, required voiding, mechanics whose state cannot be diagnosed clearly.

## Status

Phase 1 documentation migration is complete. Phase 2 material-trunk decisions are being reconciled; see [plan.md](plan.md) for accepted decisions, remaining high-impact questions, and the gate before Phase 3. The project remains a broad design proposal, with system details and open decisions in the linked owner documents.
