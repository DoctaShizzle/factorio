# Technical Architecture — Project Prometheus Modpack

*Design-time reference for modpack structure, dependencies, and deployment model.*

## Deployment Model: SE Pattern (Core-Installable + Extension Packs)

One primary installable mod that bundles all required sub-mods. Beyond that, **optional extension packs** provide additional content players can choose to install or skip.

### Core Modpack (Always Installed — Non-Negotiable)

```
project-prometheus/                        # Single installable mod — everything below is required
├── core/                                  # Shared backbone — cannot function without any sub-mod
│   ├── items, recipes, tech tree          # Shared vocabulary
│   ├── research grid                      # Three-phase progression
│   └── handbook/informatron               # Information layer, lore
├── minerals/                              # Required — mineral deposits & refining
├── chemistry/                             # Required — chemical processes & intermediates
├── machines/                              # Required — machine/equipment families across all domains
├── power/                                 # Required — generators, transmission, grid tiers
├── endgame/                               # Required — simulation network components
└── military/                              # Required — pollution pressure, ammo chains, defense infrastructure
```

**Analogy to Space Exploration:** Like how SE requires `alien-biomes`, `robot-attrition`, `aai-industry` as co-installed sub-mods that all ship together — you don't pick and choose which domains to install. They're architecturally split for manageability, but all required for the mod to function.

### Extension Packs (Opt-In)

Optional installable mods that layer on top of the core pack. Players choose which to install based on preferred playstyle.

```
project-prometheus/
└── extensions/                            # Optional extension packs — player chooses what to install
    ├── difficulty-advanced/
    ├── difficulty-extreme/
    ├── chemistry-harsh-reactions/
    ├── machinery-advanced-bots/
    ├── power-nuclear-waste/
    ├── logistics-advanced-trains/
    ├── endgame-simulation-hard/
    └── worldgen-altered-geography/
```

| Extension | Role | Description | Target Player |
|---|---|---|---|
| **difficulty-advanced** | Hard mode | Harder enemy AI, advanced weapon tech trees. Requires Combat Mechanics Overhaul (external). | Players wanting military depth |
| **difficulty-extreme** | Extreme mode | Resource scarcity, aggressive biter scaling, fortified bases, pollution multipliers | Hardcore players |
| **chemistry-harsh-reactions** | Complexity layer | Tighter catalyst windows, more extreme conditions. Makes chemistry feel like real process engineering with less margin for error | Players who want the chemistry layer to challenge them |
| **machinery-advanced-bots** | Deep dive | Smarter pathfinding, multi-item batch handling, predictive scheduling for bots | Bot enthusiasts |
| **power-nuclear-waste** | System addition | Spent fuel reprocessing, containment storage, long-lived isotope decay chains | Players who care about nuclear power |
| **logistics-advanced-trains** | Deep dive | Dynamic routing algorithms, predictive scheduling, multi-modal transfer optimization | Train enthusiasts |
| **endgame-simulation-hard** | Hard mode | More information-formed entities to debug, harder network scaling, more complex fidelity requirements | Players who want the endgame to challenge them |
| **worldgen-altered-geography** | Alternative start | Different continent shapes, unusual mineral concentrations, varied early-game resource distribution | Players who want different starting conditions |

**How extensions interact:** Extensions can stack (install multiple). Some have explicit dependencies on each other or external mods. A player who wants the full experience installs all; a sandbox player installs none. There is no single "correct" combination.

### Rationale for Core Architecture

- **Cross-domain interdependency:** Every subsystem feeds the endgame simulation network. No single domain is optional.
- **Split into sub-mods for development workflow, not user choice:** A developer works on chemistry independently without touching power. This avoids Bob's dependency-conflict problem (where `bobmods-logistics` must match `bobmods-petrochem` versions) while giving users one install button.
- **Extension packs solve the "I just want to play factory" problem:** Not everyone wants military content. Extensions let you serve both audiences without splitting the core design into two separate mods.

### Scope Targets

| Metric | Target | Notes |
|---|---|---|
| **New items** | 800–1200 total | Comprehensive but bounded. Your product catalog will be selective. |
| **New recipes** | ~2500-4000 | Multi-route products inflate count; use single "good" routes where tradeoffs aren't meaningful. |
| **Fluid recipe density** | Batch similar processes | Avoid a unique fluid recipe per minor variation. Group chemically similar fluids into shared intermediates. |
| **New entities (machines)** | ~50-80 machine types | Reuse equipment families from your machine-systems doc across domains. |
| **Tech tree size** | 800–1500+ techs | Three-phase research with domain packs = large grid, but manageable. |

## Dependency Strategy

### Required Dependencies (Mandatory)

*Zero third-party mods required.* The core modpack bundles everything needed:

| Component | Source | Notes |
|---|---|---|
| **Informatron** | Included with core modpack | Shipped automatically as a core sub-mod. All players get it regardless of extension choices. |
| **Blueprint Library** | Vanilla (Factorio 1.1+) | Baked into base game — no dependency needed. |

### Optional Dependencies (If Adopting Specific Mechanics)

*These are only mandatory if you adopt the specific mechanic they provide.*

| Dependency | Required For Extension... | Notes |
|---|---|---|
| **Combat Mechanics Overhaul** | `difficulty-advanced` | Wall-blocking projectiles required for extended military content. Only installed when that extension is selected. |

### Recommended Client-Side QOL Mods (Not Dependencies)

*These are useful but client-side — recommend in documentation, never require:*

| Mod | Purpose | Why Recommend It |
|---|---|---|
| **FNEI / What Is It Really Used For** | Recipe lookup across 2000+ recipes | Essential QOL with your product catalog density. |
| **Even Distribution Lite** | Smart belt insertion (early-game) | Reduces friction during first 30 minutes of a new playthrough. |
| **Bottleneck Lite** | Production bottleneck detection | Your multi-route system makes bottleneck identification non-obvious. |
| **Milestones** | Progress tracking with mod presets | Good for endgame milestone visibility. |
| **GTFO / Squeak Through** | Pull items from full inventories | Small quality-of-life that compounds over long playthroughs. |

**Explicitly NOT recommended:** LTN (Logistic Train Network). Your logistics-system.md already proposes native demand-based dispatch as a built-in mechanic. Building it in-house avoids LTN's known shortcomings (signal instability, large factory crashes) and keeps the design coherent with your electrified rail vision.

## Performance Design Constraints

### Bob's Machine Type Overhead — Industry Benchmark

Bob's mods add ~300 new items and ~250 new recipes, but the **unique entity types** are the real performance concern: each new machine type requires a separate Lua state initialization. The cost scales as `unique_machine_types × active_machines`. This is why Bob's factory performance drops noticeably above 50–100km² of buildout even with stable production.

**Design implication for Project Prometheus:** Your ~50–80 entity target already accounts for this. Do not exceed ~80 unique machine types across the entire modpack. Reuse equipment families from your machine-systems doc aggressively — every new machine type is a permanent per-tick cost, not just a one-time load cost.

### Logistics Graph — The Hidden Killer

**What it is:** Every belt connected to another belt forms one "logistics network." Factorio periodically runs a search algorithm across this entire network to answer: "what items are here, where do they need to go, and which machine wants what?"

**Why it explodes:** Complexity grows as `N × M²` where N = machines in one network and M = item types tracked. With vanilla (~100 machines tracking 5 items) = trivial. With Prometheus multi-route design (200 machines tracking 30 chemical intermediates) = **180,000 graph operations per cycle**.

**Mitigation by design:**
- **Network partitioning:** Keep belt-connected factories to <15 tracked item types per network. Your multi-route system should naturally encourage this — different routes feed into different factory zones that don't share many items.
- **Limit bot pool tracking:** Restrict logistics bot item pools to ~15-20 tracked items (vs vanilla's 5). With 30+ new chemicals, a single pool tracking all of them is expensive.
- **Avoid cross-domain belt connections:** Don't let every chemical plant feed into the same belt network if they don't share >8 item types. Physical separation = performance isolation.

### Fluid Complexity — Critical Performance Constraint

**Rule: Batch similar chemical processes where possible; avoid creating a unique fluid recipe per minor variation.**

- Oil processing chains with petroleum create the heaviest per-tick overhead due to continuous recipe recalculations.
- Group chemically similar fluids into shared intermediates rather than creating individual recipes for every variant.
- Example: Instead of separate recipes for "diluted acid A," "diluted acid B," and "diluted acid C" — use a generic "diluted acid" fluid that differentiates only through recipe inputs/outputs, not distinct fluid types.
- **Your product catalog design should explicitly flag which fluids are "shared intermediates" vs. "unique process-specific fluids."**

### Save File Size Trajectory (Estimated)

| Phase | Estimated Size | Primary Drivers |
|---|---|---|
| Early game | 5–15 MB | Baseline, small explored area |
| Mid-game (industrial expansion) | 20–80 MB | Entity growth, recipe complexity metadata |
| Late-game (simulation network buildout) | 100–400+ MB | Massive entity counts, logistics graph explosion |
| Full simulation network | 300–600+ MB | Distributed compute campuses, freight terminals, bot pools |

**Key size drivers per unit:**
- Entities: ~100–500 bytes each (50,000 entities = 5–25 MB alone)
- Logistics graph: hidden cost, scales with item types × connected machines
- Explored area: 10km² compresses to ~100–500 MB in save
- Tech grid: 2–7 MB for 800–1500+ techs
- New items/recipes: +15–30 MB baseline metadata

### Mitigation Strategies

| Strategy | When to Apply | How |
|---|---|---|
| **Bound item count** | During product catalog design | Cap at 800–1200 new items; be selective, not exhaustive. |
| **Batch fluid recipes** | During chemistry process design | Group chemically similar fluids into shared intermediates. |
| **Lazy-load distant areas** | During endgame implementation | Don't keep simulation network chunks in memory when the player isn't visiting them (SE pattern). |
| **Design against graph explosion** | Throughout all phases | Partition factory zones by domain; limit tracked items per belt network to <15. |

### Performance Red Lines

- **~450k entities:** Hard limit where Factorio becomes unplayable regardless of UPS. Your distributed endgame infrastructure must stay within bounds.
- **Save stability degrades past ~150 MB:** Saves become slower to load, chunk loading noticeably delayed. Unavoidable in Factorio's architecture but manageable with design bounds.

## Open Technical Decisions

### Deferred — Revisit During Implementation

- **Extension boundaries (core vs. optional):** Structure is defined in the extension pack table above. Finalize content assignment when populating the GitHub kanban board during implementation phase.
