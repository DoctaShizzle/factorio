# Logistics System - Design Proposal

*For: Factorio Overhaul Mod (Project Prometheus)*  
*Status: Vision / requirements phase*

Related documents: [Mod Overview](mod-overview.md), [Power System](power-system.md), [Machine Systems](machine-systems.md).

## Summary

This document defines logistics as an engineering decision layer spanning physical transport (belts, trains, bots) to information flow (demand signalling, intelligent dispatching). It proposes a progression from primitive conveyors through freight terminals and demand-based rail networks to late-game "information logistics" — where the factory moves from shifting materials to orchestrating decisions.

**What it covers:** Design philosophy, transport layers (belt, rail, bot), demand-based dispatch, freight terminals, information logistics, and seven design principles.

**What it does not cover:** Specific item recipes for belt/machine variants, train timetable/track networking implementation details, or exact bot stat progression numbers.

## Design Philosophy

Logistics should create **engineering decisions**, not repetitive maintenance.

The player should spend time deciding:
- *How* resources move (belt type, train line, bot pool)
- *When* resources move (buffer sizing, demand thresholds, dispatch timing)
- *How* infrastructure scales (freight terminal vs. cheap station, dedicated vs. pooled trains)
- *Which* logistics technology to invest in (material tradeoffs, capacity headroom)

The player should **not** spend time:
- Rebuilding the same train blueprints for minor throughput changes
- Wiring complex dispatch logic for basic use cases
- Fighting repetitive loading/unloading station designs that dwarf production blocks

## Transport Layers and Progression

### Belt Evolution

Belts should evolve alongside materials science — earned through industrial progression, not given upfront.

| Stage | Candidate type | Design role | Tradeoff |
|---|---|---|---|
| Early | Primitive conveyors | Starter transport, low throughput | Cheap, small footprint, limited speed/capacity |
| Mid | Steel conveyors | Main factory backbone | Higher material cost, reliable general-purpose |
| Late | Advanced industrial conveyors | High-throughput corridors | Requires advanced materials/electronics |
| Endgame | High-speed logistics systems | Precision distribution, dense routing | Requires semiconductors/computation layer |

Key principle: **better infrastructure should be earned through industrial progress.** The exact tier names and stat curves remain open.

### Rail Logistics

#### Freight Terminals — Compact Late-Game Stations

**Problem:** Vanilla train loading/unloading consumes enormous space — stacks of inserters, buffers, balancers — making stations larger than the production blocks they serve.

**Solution:** A late-game Freight Terminal that is expensive but compact, with integrated buffering and built-in balancing.

| Cheap Station | Freight Terminal |
|---|---|
| Normal inserters + belts | Advanced materials + electronics + semiconductors |
| Large footprint (3×-5× production block) | Compact footprint (fits in ~1/3 the space) |
| Manual routing, frequent rebuilds | Integrated demand awareness or dedicated connections |
| Low throughput per tile | High throughput, easy scaling |

This preserves engineering choice: early factories *must* accept station bloat; late-game players earn a compact alternative at meaningful material cost.

#### Train Dispatch — Both Modes Are Valuable

Dedicated connections and demand-based dispatch are **not mutually exclusive**. Both serve different use cases across the progression:

**Mode A: Dedicated Connections (earlier unlock)**
- Explicit source → destination routes (inspired by Satisfactory)
- A train per connection, waits on the receiving station until material is needed
- Simpler to implement, more predictable, less computational overhead
- Useful for steady-state flows: ore to smelter, plates to rocket part factory

**Mode B: Intelligent Demand Dispatch (later unlock)**
- Stations advertise current inventory + requested inventory
- Available trains are automatically dispatched to where they're needed
- Requires advanced electronics, communication infrastructure, computational resources
- Useful for variable-demand or bottlenecked material flows

Both coexist. A player might run dedicated ore haulage lines *and* a demand-dispatched fleet for chemical feedstocks that fluctuate with plant equilibrium.

#### Electrified Trains — First-Class Citizens

Electrified trains should be a first-class logistics option (inspired by Satisfactory's approach), not an afterthought. The core concept: **rails as power conduits.** Powered rail segments carry electrical current that electric locomotives draw from directly while moving.

**Voltage tier options for powered rails:**

| Type | Tradeoff | Use case |
|---|---|---|
| Low-voltage powered rails | Simpler infrastructure, lower installation cost, but higher power loss over distance | Short-haul freight, nearby mine-to-factory lines |
| High-voltage powered rails | Requires transformer substations at intervals, higher per-segment cost, but much lower loss over long distances | Long-distance ore haulage, remote deposit extraction |

**Key design implications:**
- Trains don't carry fuel — they draw power from the rail line, making them emission-free operators
- A powered rail network is itself a factory infrastructure investment, with losses tied to length and voltage tier (ties into the power system doc)
- Remote freight terminals need power fed to them via high-voltage rails + local step-down transformers, creating meaningful placement decisions
- Electric locomotives trade speed/efficiency against their own power draw rating — a heavy-haul locomotive pulls more but needs lower-voltage or denser power infrastructure

**Design decisions:**
- **Non-electric trains:** Allowed for backwards-compatibility with existing blueprints and mod content. The design preference is to remove them if feasible — electric locomotives are the ideal state, tying logistics directly into the power infrastructure.
- **Power outages:** Trains pause mid-line (like Satisfactory), not collapse into chaos (unlike LTN where signal loss cascades). A brief outage doesn't destroy a dispatch network's state. However, this is a difficulty question — whether trains resume automatically or need manual re-initiation after power returns remains open.
- **Powered rail construction:** Stations act as power distribution nodes (inspired by Satisfactory). Trains draw voltage from the station they're coupled to; powered rail segments between stations carry current accordingly. This means each station needs power fed to it, creating meaningful placement and infrastructure decisions.

### Bot Progression

#### Construction Bots — Progressively Better Through Industrial Advancement

Construction bots are a successful system that players love; **do not nerf them.** Instead, make them progressively improve through industrial advancement:

| Stage | Characteristics | Driven by |
|---|---|---|
| Early | Slow, fragile, limited inventory | Basic electronics + simple batteries |
| Mid | Faster, larger inventory, improved energy capacity | Better materials + upgraded power cells |
| Late | Advanced navigation, long range, highly efficient | Semiconductors + precision manufacturing |

Progression should come from **better materials and electronics**, not arbitrary research gates.

#### Logistics Bots — Flexibility Tools, Not Bulk Movers

Logistics bots have a natural limitation: they are poor at extreme throughput. This is *good* by design.

**Intended role:**
- Maintenance and trace material distribution
- Complex assembly chain support (catalysts, specialty products)
- Low-volume/high-complexity logistics (Angel-style trace mineral routes)

**Not intended for:**
- Bulk ore movement (belts + trains should dominate)
- Large-scale plate/fluid distribution
- Replacing train networks

The division of labor is deliberate: belts and trains handle bulk; bots handle complexity.

## Information Logistics — Late-Game Discipline

This may be the most distinctive logistics concept in the mod's design. Most factory games focus on **item logistics** (moving things) and **fluid logistics** (pumping things). This mod introduces a third layer: **information logistics** (orchestrating decisions).

### Progression of What the Factory "Moves"

| Civilization Stage | What Moves | Mechanism |
|---|---|---|
| Early | Items, fluids | Belts, pipes, basic trains |
| Industrial | Materials, resources | Advanced freight networks, automated dispatching |
| Computational | Information, predictions | Industrial control networks, demand signalling, process optimization |

### Example: From Static Routing to Decision Orchestration

Instead of:
> *"Train A always goes from Mine X to Refinery Y."*

The system becomes:
> *"Nickel inventory has fallen below target. → Dispatch train."*
> *"Oxygen demand has increased. → Redirect production."*
> *"Refinery equilibrium has changed. → Reconfigure supply priorities."*

### Why This Matters

Information logistics creates a **direct connection** between semiconductors, computation, logistics, and the endgame. Computational infrastructure becomes useful *before* the endgame — the player is not just building bigger factories, but **smarter** ones.

## Seven Design Principles

1. **Trains support integrated demand-based logistics.** Both dedicated connections and intelligent dispatch have a place across the progression.
2. **Freight terminals reduce station bloat at meaningful cost.** Early players pay space overhead; late-game earns compact alternatives.
3. **Construction bots become progressively better through industrial advancement.** Progression via materials, not arbitrary gates.
4. **Logistics bots remain flexibility tools, not bulk throughput tools.** Belts and trains dominate volume; bots handle complexity.
5. **Belts evolve alongside materials science.** Better infrastructure is earned through industrial progress.
6. **Information logistics becomes a late-game engineering discipline.** Moving decisions, not just items, connects to the endgame.
7. **Logistics rewards infrastructure design, not repetitive maintenance.** The player decides architecture; the system handles execution.

## Open Decisions

- Exact belt tier names and throughput stat curves
- Train electrification model and its connection to the power system
- How freight terminal demand signalling integrates with the computational network
- Bot stat progression numbers and the specific material requirements per stage
- Whether a "connection manager" UI exists for dedicated train routes, or if it's purely automated
- How fluid logistics evolves (do pipes also have tiers? temperature/pressure matter?)
- Interaction between information logistics and the PLC automation system