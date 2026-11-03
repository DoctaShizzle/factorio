# Military System - Design Proposal

*For: Factorio Overhaul Mod (Project Prometheus)*  
*Status: Vision / requirements phase*

Related documents: [Mod Overview](mod-overview.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Minerals and Refining](minerals-and-refining.md).

## Summary

This document defines the military and expansion-pressure system as drivers of player choice. Military pressure arises from two sources: pollution from industrial processes (generating attacks that require defense infrastructure) and space constraints from process selection (some paths demand far more footprint than others, forcing urgency about expansion). It establishes that these forces give weight to process selection — dirty production costs military consequences; inefficient production costs spatial ones. Ammo and weapon chains connect chemistry and metallurgy back into the industrial ecosystem.

**What it covers:** Design philosophy, dual drivers of military/expansion pressure (pollution and space), process-to-pressure model, ammo/weapon intermediate chains, defense infrastructure progression, vanilla space platform integration, and open decisions.

**What it does not cover:** Enemy unit balance numbers, base attack wave mechanics, AI group targeting, or detailed combat formulas — those are implementation details deferred to gameplay testing.

## Design Philosophy

The military and expansion systems exist to give weight to process selection. There are two independent pressure axes arising from industrial decisions:

1. **Pollution pressure** — dirty processes generate attacks that require defense infrastructure
2. **Space pressure** — inefficient processes demand far more footprint, forcing urgency about expansion

Both pressures give the player a reason to care about *how* they produce things, not just *what*. They are the economic consequences of industrial choices — the counterweight to whatever benefit the player gains from choosing a particular process path.

### Pollution Pressure

Pollution is an economic consequence of industrial processes, not a collection of special-case enemy mechanics. Dirty, high-throughput production defers costs into military consequences; cleaner routes trade for infrastructure, power, or process complexity.

**Key principle:** Military pressure should feel like an engineering problem (how do I design my factory to minimize defensive overhead?), not a combat challenge (can I build better turrets?).

### Industrial Choice Example

| Process | Pollution cost → Military pressure | Space cost → Expansion pressure |
|---|---|---|
| Sulfur burning (direct) vs. off-gas capture | Dirty process → more attacks; cleaner route needs scrubber infrastructure | Similar footprint — pollution is the primary tradeoff here |
| Coal gasification without scrubbers vs. with filtration | Captured emissions reduce spread → lower military pressure | Filter plant adds space overhead, but manageable |
| Electrolysis without brine purification vs. purified brine | Waste byproducts → higher local pollution → more attacks | Purification step is compact; not a major space driver |
| **High-efficiency dense process** (e.g., focused refining with coproduct recovery) | Low spread pressure | Small footprint, high throughput — gives the player **time and breathing room** to explore at their own pace |
| **Low-efficiency distributed process** (e.g., renewable-heavy or widely-scattered production) | Diffuse pollution but persistent low-level pressure | Requires **far more land and infrastructure** — creates spatial urgency that pushes exploration sooner than a dense process would |

Different industrial choices push the player toward expansion through different mechanisms:
- **Pollution-driven:** "I *need* to move my dirty processes further out (or clean them up) because attacks are getting worse."
- **Space-driven:** "My current layout is eating everything — I'm running out of room regardless of pollution, so I *need* to explore whether or not the military pressure is high."

Both create urgency for space. A player choosing efficient processes gets breathing room and can prioritize defense first. A player choosing spacious processes gets expansion urgency from space constraints alone.

## Pollution-to-Military Pressure Model

### Core Mechanics (Conceptual)

Pollution spreads from emitting sources in a radius. The density at any map location determines the military pressure score for that area:

- **High pollution zones** near production blocks generate stronger/more frequent attacks on nearby infrastructure
- **Pollution fades over distance and time** — large spread-out factories have lower local pressure than dense clusters, all else equal
- **Different pollution types may attract different attack profiles** — pending confirmation of whether this is useful or over-engineering

### Pressure Consequences

Military pressure translates into two kinds of player-facing effects:

| Effect | Design role | Tradeoff lever |
|---|---|---|
| Attack frequency | Slow growth if ignored; factory must allocate capacity to defense | Encourages spreading pollution or reducing it at source |
| Attack intensity / unit composition | Drives need for progressive defense tech and ammo | Rewards investing in metallurgy/chemistry chains |

**Guardrail:** Military pressure should never make the player stop building their factory. It should influence *where* and *how* they build, and what defensive infrastructure they invest in. Attacks are a cost of doing business, not a wall that stops progress.

## Space Pressure — Process-Driven Expansion Urgency

Process selection creates a second, independent axis of expansion urgency. Some industrial paths demand far more land and infrastructure than others, regardless of pollution. This means the rate and priority at which the player explores space depends on their chosen process mix.

### How Different Processes Drive Space Pressure

| Process characteristic | Factory footprint | Exploration urgency | Example tradeoff |
|---|---|---|---|
| **Dense, high-efficiency** (focused refining, coproduct recovery loops) | Small — outputs per tile are high | Low — you can stay in one area longer | Compact plant with internal recycling gives time to plan expansion on your terms |
| **Distributed, low-throughput** (renewable-heavy, scattered production) | Large — many parallel lines for modest output | High — map runs out of room regardless of military pressure | Solar/wind arrays or dispersed electrochemical cells require enormous footprint for equivalent throughput |
| **Modular but numerous** (many small machines vs. few large ones) | Medium-large — scaling means duplication | Medium — steady expansion pressure even without military force | Early-game processes that scale by copying rather than upgrading create spatial urgency |

### Interaction with Military Pressure

The two pressures combine in meaningful ways:

| Pollution state | Space constraint state | Player experience |
|---|---|---|
| Low | Low | **Breathing room.** Time to experiment, optimize, and explore voluntarily. The "happy path." |
| High | Low | **Defensive focus.** You can stay put — expand only for defense logistics. Military is the primary driver. |
| Low | High | **Spatial urgency.** Map pressure forces exploration even without military attacks. Space is the bottleneck. |
| High | High | **Squeeze play.** Both pressures hit at once. Expansion isn't optional — you must move or clean up to survive. |

### Implications for Process Design

This means:
- **Renewable-heavy paths** (solar, wind, etc.) should create genuine space pressure — enough that the player feels it as a driver for exploration, not just "more of the same."
- **Dense processes** (coal gasification with scrubbers, focused refining) give breathing room but carry pollution tradeoffs.
- **The endgame computational infrastructure** (Planetary Simulation Core, distributed facilities) benefits from players who chose space-efficient industrial paths — they get to build it at their own pace rather than racing expansion.
- **Space exploration itself becomes an engineering solution**, not just a reward for building enough rockets. You explore because your process choices *need* the resources, not just because the game tells you to go.

**Open question:** Space pressure is felt through gameplay experience — running out of room naturally — rather than displayed as a metric. This matches how vanilla Factorio and Bob's/Angel's communicate spatial urgency: the map runs out, your factories need to expand, there is no dashboard telling you when to go.

## Ammo and Weapon Intermediate Chains

This is where military meets industry — weapons and ammo are manufactured products requiring real supply chains, not craft-grid items. They connect back to chemistry and metallurgy.

### Candidate Ammo Categories

| Category | Primary feed materials | Industrial role | Progression tier |
|---|---|---|---|
| Kinetic (bullet) | Lead/core alloy, copper jacket, steel case, gunpowder/smoldder propellant | Early/mid defense — standard turret ammo | Starter range |
| Incendiary | Fuel/oxidizer mix, casing, ignition compound | Anti-spider and anti-light-armor suppression | Mid-tier unlock |
| Explosive (HE) | High-explosive core, detonator, steel casing | Heavy armor and hardened target engagement | Late-game defense |
| AP (armor-piercing) | Tungsten/core alloy, specialized propellant | Engagement with heavily armored enemy types | Late-game specialty |
| Nuclear | Enriched uranium/plutonium core | Endgame strategic capability (if nuclear branch exists) | Pending nuclear scope |

### Weapon Progression Logic

Weapon tiers should follow the mod's broader philosophy — **capabilities over numbers**:

- Better weapons don't just do more damage; they use different ammunition types requiring different supply chains
- Switching from kinetic to incendiary ammo isn't a linear upgrade — it requires building fuel-mixing infrastructure and obtaining specific chemical intermediates
- This ties defense investment into the player's broader factory: investing in your munitions supply is an industrial decision, not just "spend tech points"

### Material Sources (from other docs)

- **Tungsten armor/cores** — refined from wolframite/scheelite deposits, requires high-purity processing → connects to mineral refining
- **Explosive compounds** — nitric acid (from chlor-alkali/Ostwald chain or Haber-Bosch nitrogen fix), glycerol, or synthetic intermediates → connects to chemical processes
- **Propellants/smoulder** — sulfur combustion + charcoal/coal carbonization products → connects to core chemistry
- **Copper jacketing** — electrolytic copper from chalcopyrite or malachite routes → connects to refining

## Defense Infrastructure Progression

Defense itself should follow the mod's progression philosophy — earned through industrial capability, not just tech tree advancement.

| Stage | Defense type | Driven by |
|---|---|---|
| Early | Passive barriers, basic turrets with kinetic ammo | Basic steel, lead, simple chemistry |
| Mid | Active defense grids, incendiary/explosive ammo supply | Chemical intermediates, alloy production, precision manufacturing |
| Late | Distributed defense network, automated targeting, specialized ammo | Semiconductors, computation layer, PLC integration |
| Endgame (optional) | Strategic deterrence systems | Advanced nuclear or fusion capabilities |

### Defense as Factory Design

A mature defensive posture requires:

- **Perimeter planning** — turrets consume power, space, and ammunition; placement is a factory layout decision
- **Supply chain integration** — ammo production needs its own logistics (raw materials → chemical/mechanical lines → forward magazines)
- **Power infrastructure** — defense grids add sustained load to local power networks
- **Pollution tradeoff awareness** — expanding the factory frontier often pushes operations into higher-pressure zones

## Integration with Vanilla: Space Platform Completion

The mod should support completion of the vanilla space platform victory condition (rocket fuel, rockets, rocket parts) as one possible endgame path alongside the Project Prometheus endgame. Key considerations:

- **Rocket fuel** connects to chemical chains — sulfuric acid processing from oil or coal routes can feed into hydrazine/monopropellant production
- **Rocket parts** connect to intermediate product chains — aluminum alloys, titanium structures, semiconductor sensors for guidance systems
- **Ammo for defending the launch site** — late-game military pressure around the space platform area needs dedicated defense logistics

This gives players two endgame aspirations:
1. **Project Prometheus:** Build the distributed planetary computing network (the mod's signature endgame)
2. **Space platform completion:** Achieve the vanilla victory using the mod's industrial ecosystem to produce rocket fuel and parts through new chains

## Open Decisions

- **Attack mechanics detail:** How exactly does pollution translate to wave frequency/intensity? Radius-based density model, time-decay curves, zone thresholds?
- **Enemy unit variety:** Should the mod add new enemy types (e.g., pollution-adapted units), or reuse vanilla units with different compositions?
- **Defense turrets:** Extend existing vanilla turrets with new ammo types, or introduce new turret families tied to industrial capability (e.g., electric arc turret requiring advanced conductivity)?
- **Nuclear ammo scope:** If nuclear fuel chain exists in the mod, does nuclear ammunition belong in the military system?
- **Pollution type differentiation:** Should different pollution sources generate qualitatively different military pressure (e.g., acid emissions attract different responses than CO2 spread)? Or is total pollution count sufficient?
- **Defense automation via PLCs:** Can connected sensors and automated targeting integrate with existing combat logic, or does this require a separate control system?