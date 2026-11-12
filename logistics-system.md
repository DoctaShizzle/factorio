# Logistics System Design

*Status: Draft — candidate logistics concepts; acceptance and behavior remain under review*
*Last updated: 2026-11-12*

Related documents: [Mod Overview](mod-overview.md), [Power System](power-system.md). The source draft also referenced the missing `machine-systems.md`; see [Documentation Map](documentation-map.md) for reconciliation.

## Summary

This draft proposes logistics as an engineering decision layer spanning physical transport (belts, trains, bots) and information flow (demand signalling, intelligent dispatching). Candidate concepts include a progression from primitive conveyors through freight terminals and demand-based rail networks to late-game "information logistics" — where the factory moves from shifting materials to orchestrating decisions. Proposals below are not approved requirements unless explicitly marked otherwise.

## Purpose and Boundaries

- **In scope:** Candidate design philosophy and progression for belts, rail, bots, freight terminals, demand-based dispatch, and information logistics.
- **Out of scope:** Specific item recipes for belt/machine variants, train timetable/track networking implementation details, and exact bot stat progression numbers.
- **Source-of-truth boundaries:** Product identities and recipes belong to the relevant product documents; power behavior belongs to [Power System](power-system.md). Missing machine-system ownership remains an open repository reference in [Documentation Map](documentation-map.md).

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

#### Train Dispatch — Candidate Coexistence of Both Modes

The source proposes that dedicated connections and demand-based dispatch are **not mutually exclusive** and could serve different use cases across the progression. Their coexistence and progression remain unapproved:

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

#### Electrified Trains — Candidate Model

The source proposes electrified trains as a first-class logistics option, with **rails as power conduits** that supply moving electric locomotives.

> **Core boundary:** [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md) now accepts the vanilla pole grid with compatible tiered poles. The voltage-tier and transmission-loss assumptions below are not part of that core decision. Powered rails and electrified trains remain unapproved candidates; custom voltage and loss mechanics, if pursued, require a separate extension design.

**Optional extension concepts — voltage tiers for powered rails:**

| Type | Tradeoff | Use case |
|---|---|---|
| Low-voltage powered rails | Simpler infrastructure, lower installation cost, but higher power loss over distance | Short-haul freight, nearby mine-to-factory lines |
| High-voltage powered rails | Requires transformer substations at intervals, higher per-segment cost, but much lower loss over long distances | Long-distance ore haulage, remote deposit extraction |

**Candidate design implications (not accepted core behavior):**
- Trains don't carry fuel — they draw power from the rail line, making them emission-free operators
- A powered rail network is itself a factory infrastructure investment, with losses tied to length and voltage tier (ties into the power system doc)
- Remote freight terminals need power fed to them via high-voltage rails + local step-down transformers, creating meaningful placement decisions
- Electric locomotives trade speed/efficiency against their own power draw rating — a heavy-haul locomotive pulls more but needs lower-voltage or denser power infrastructure

**Source-recorded proposals and unresolved choice:**
- **Non-electric trains:** Allowed for backwards-compatibility with existing blueprints and mod content. The design preference is to remove them if feasible — electric locomotives are the ideal state, tying logistics directly into the power infrastructure.
- **Power outages:** Candidate behavior is for trains to pause mid-line rather than lose dispatch state. Whether they resume automatically or require manual re-initiation remains open.
- **Powered rail construction:** Candidate behavior is for stations to act as power-distribution nodes. Its voltage and power-flow assumptions remain open pending alignment with the Power System.

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

## Design Principles

1. **Trains support integrated demand-based logistics.** Both dedicated connections and intelligent dispatch have a place across the progression.
2. **Freight terminals reduce station bloat at meaningful cost.** Early players pay space overhead; late-game earns compact alternatives.
3. **Construction bots become progressively better through industrial advancement.** Progression via materials, not arbitrary gates.
4. **Logistics bots remain flexibility tools, not bulk throughput tools.** Belts and trains dominate volume; bots handle complexity.
5. **Belts evolve alongside materials science.** Better infrastructure is earned through industrial progress.
6. **Information logistics becomes a late-game engineering discipline.** Moving decisions, not just items, connects to the endgame.
7. **Logistics rewards infrastructure design, not repetitive maintenance.** The player decides architecture; the system handles execution.
8. **Machine capability tiers are defined by build materials, not input material quality** (see research-progression.md "Machine Tiering Through Material"). Each assembler type has multiple tiers built from progressively better materials — higher tiers unlock recipes that lower-tier machines cannot perform because they must withstand higher temperatures, pressures, or precision requirements. Better raw deposits remain useful because easier purification cascades mean cheaper machine upgrades.
9. **Machine capability scales through building higher-tier variants, not just upgrading in-place.** A furnace can accept upgrade modules for limited improvement, but building a Tier 2 or Tier 3 furnace from scratch unlocks capabilities that upgrades cannot replicate.

## Engineering Complexity Patterns — Game-Wide Logistics Design

These patterns create meaningful engineering decisions across all phases. They are design patterns adapted from successful overhaul games, integrated into this mod's industrial ecosystem theme.

#### Coproduct/Waste Management

Not all production chains produce only useful output. Some recipes generate coproducts alongside the primary product:
- **Recycle path:** Feed coproduct back into another chain — creates routing puzzles that reward cross-domain awareness
- **Convert path:** Add a secondary processing step to transform coproduct into something else useful — adds depth but increases infrastructure cost
- **Manage loss:** Accept material loss and optimize around it — faster to set up but resource-inefficient

This forces process strategy choice, not just machine placement. The player asks "how do I handle the waste?" as much as "which process should I use?"

#### Feedback Loops (Kickstart Required)

Some recipes require a small amount of their own lower-tier output as a catalyst seed. The player must:
1. Produce an initial batch manually (slower, less efficient)
2. Set up the feedback loop
3. Transition to self-sustaining production

This creates a satisfying "it's alive" moment and prevents the "just build enough and move on" mentality — you have to *design* the startup procedure.

#### Catalyst Degradation / Replacement Cycles

Catalysts wear out over time in certain processes — they are consumed slowly or lose effectiveness. This creates **maintenance rhythm**, not "build one and forget it" factories:
- The player must design a parallel "catalyst production line" alongside their main production
- Decide on replacement frequency: faster degradation = more efficient main process but higher maintenance burden
- Manage shutdown windows to swap catalysts without losing too much output

This fits the Prometheus industrial fantasy perfectly — the factory is a living system with wear-and-tear, not a static machine.

**Open decision:** How severe should catalyst degradation be? Light (replace every few hours of in-game time) vs. heavy (every 10–20 minutes)? This determines whether it's a manageable rhythm or a constant chore.

#### Complex Logistics Ratios

Even though only ~30 intermediates feed into research directly, each traces back through substantial input trees with deliberate logistical difficulty:
- **Mismatched flow ratios** (e.g., 1:20 solid inputs) force separate routes that merge late — prevents spaghetti factories from scaling linearly
- **Mixed solid+fluid inputs** require piping infrastructure to join belt networks — creates natural spatial boundaries between production zones
- **Three+ inputs from different origins** create convergence-point hubs that become natural organizational centers

#### Machine Tiering Through Building, Not Just Upgrading

Machine capability scales through **building higher-tier variants** from scratch, not just slotting in modules:
- A basic machine can accept upgrade modules for limited improvement (throughput boost, power reduction), but these have caps — a Tier 1 furnace can never match a Tier 3 furnace's maximum throughput
- Building a new machine unlocks capabilities that upgrades cannot replicate (new recipe access, higher material grade processing)
- This creates retrofit engineering pressure: can you fit upgrades in your existing footprint, or do you need to tear it down and rebuild?

## Open Decisions

- Exact belt tier names and throughput stat curves
- Whether powered rails belong in core or an extension. Any custom voltage/loss mechanics remain outside the accepted core-power direction in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md)
- How freight terminal demand signalling integrates with the computational network
- Bot stat progression numbers and the specific material requirements per stage
- Whether a "connection manager" UI exists for dedicated train routes, or if it's purely automated
- How fluid logistics evolves (do pipes also have tiers? temperature/pressure matter?)
- Interaction between information logistics and the PLC automation system
- Catalyst degradation severity — light (manageable rhythm) vs. heavy (constant maintenance pressure)
- Upgrade module caps — how far can modules push a machine before building a new tier becomes necessary?