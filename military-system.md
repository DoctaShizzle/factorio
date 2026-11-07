# Military System - Design Proposal

*For: Factorio Overhaul Mod (Project Prometheus)*  
*Status: Resolved — market research complete*

Related documents: [Mod Overview](mod-overview.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Minerals and Refining](minerals-and-refining.md), [Infrastructure](infrastructure.md).

## Summary

This document defines the military and expansion-pressure system as drivers of player choice. Military pressure arises from two sources: pollution from industrial processes (generating attacks that require defense infrastructure) and space constraints from process selection (some paths demand far more footprint than others, forcing urgency about expansion). It establishes that these forces give weight to process selection — dirty production costs military consequences; inefficient production costs spatial ones. Ammo and weapon chains connect chemistry and metallurgy back into the industrial ecosystem.

**What it covers:** Design philosophy, dual drivers of military/expansion pressure (pollution and space), enemy taxonomy and scaling model, ammo/weapon intermediate chains with full supply trees, turret progression and new families, pollution-to-military-pressure mechanics, vanilla space platform integration, extension pack boundaries, and resolved open decisions.

**What it does not cover:** Enemy unit balance numbers, base attack wave mechanics, AI group targeting, or detailed combat formulas — those are implementation details deferred to gameplay testing.

## Design Philosophy

The military and expansion systems exist to give weight to process selection. There are two independent pressure axes arising from industrial decisions:

1. **Pollution pressure** — dirty processes generate attacks that require defense infrastructure
2. **Space pressure** — inefficient processes demand far more footprint, forcing urgency about expansion

Both pressures give the player a reason to care about *how* they produce things, not just *what*. They are the economic consequences of industrial choices — the counterweight to whatever benefit the player gains from choosing a particular process path.

### Pollution Pressure

Pollution is an economic consequence of industrial processes, not a collection of special-case enemy mechanics. Dirty, high-throughput production defers costs into military consequences; cleaner routes trade for infrastructure, power, or process complexity.

**Key principle:** Military pressure should feel like an engineering problem (how do I design my factory to minimize defensive overhead?), not a combat challenge (can I build better turrets?).

### Market Research: How Other Overhaul Mods Handle Military Systems

A survey of major Factorio overhaul mods reveals fundamentally different philosophies on the military/combat layer:

| Mod | Philosophy | Turret System | Ammo/Weapons | Enemy Types | Pollution Scaling |
|---|---|---|---|---|---|
| **Bob's Weapons Pack** ✅ *Reference* | Capability-based progression. Better weapons = different ammo types requiring supply chains. Damage is secondary to capability shift. | Extends vanilla machine turrets with tiered ammo; adds handgun, shotgun, and rocket variants with industrial recipes. No new turret families. | Kinetic → incendiary → explosive → AP → penetration rounds. Each requires distinct chemical/metallurgical chains. Lead/copper/steel for basic; nitric acid + glycerol for HE; tungsten for AP. | Vanilla units only (biter/spitter/worm). Enemy density scales with pollution spread. | Linear: total pollution emitted × time = attack intensity curve. Simple radius-based spread from emitting sources. |
| **GregTech New Horizons** ✅ *Reference* | Deep industrial integration. Combat is an end-use for late-game materials. Guns are crafted through machining tiers. Armor plates use exotic alloys. | Custom gun system (not vanilla turrets). Handgun → rifle → auto-rifle → heavy weapons. Each tier requires specific machined parts and alloy grades. Ammo follows weapon tiers. | Hundreds of ammo variants tied to GT material processing. Penetration armor also uses steel/alloy plates. High complexity, high depth. | Minecraft mobs only — no native Factorio-style biter ecology. Combat happens in Overworld through exploration. | Not applicable (GTNH doesn't replicate vanilla pollution mechanics). |
| **Angel's Addons** | Minimal military. Focus is purely on production complexity (more mining depth, more refining stages). Vanilla enemy/biter logic with amplified pollution spread but no new content. | Vanilla only. No weapons or ammo changes. Defense is about perimeter distance and turret count. | Vanilla only. | Vanilla units only. | Amplified vanilla spread — larger pollution clouds due to denser early-game factories. |
| **Pyanodon's Grand Suite** | Modular expansion. Adds turrets in specific categories (flamethrower, laser-like weapons) connected to late-game chemistry/metallurgy but keeps vanilla turrets primary. | Extends vanilla with 2-3 new turret families at late game. Ammo connects to existing chemical chains. | Selective — only key ammo types get industrial recipes. The rest remain vanilla or craft-grid items. | Vanilla units + biomes-specific variants. Focus on variety of challenge, not density. | Moderate amplification. Pollution matters but is softened by the mod's generally forgiving pace. |
| **Bob's Military / Combat Mechanics Overhaul** (optional) | Hard mode layers. Enhances vanilla AI with smarter targeting, fortified bases, extended weapon tiers. Requires external combat overhaul dependency. | Extends Bob's Weapons Pack progression further — sniper, anti-materiel rifle levels at very late tiers. | New materials feed into new ammo (railgun projectile via electromagnetic acceleration concept, etc.) | Adds pollution-adapted variants and armored enemy forms at high pollution thresholds. | Multi-zone: near-factory gets waves of regular units; distant areas get elite variants that are harder to fight through. |
| **The Riftbreaker** ✅ *Mechanical Reference* | Element-based tactical depth. Different ammo types deal different damage elements (Fire, Ice, Plasma, Radiation) each with specific enemy weaknesses. Weapon mods change fire rate/ammo consumption tradeoffs. Drone defense for perimeter security. Energy shield connects to power grid. Modular weapon system where the same base frame accepts interchangeable components that change its stats. Ammo selection is a tactical decision, not just "bigger numbers." | Six damage element families (Fire, Ice, Plasma, Radiation, Corrosive, Cryo) each with unique effectiveness profiles against enemy types. Melee + energy + liquid + projectile categories. Each weapon has mod slots for tradeoff customization. Ammo types map to elements: incendiary ammo = Fire element, cryo rounds = Ice, etc. | Enemy composition shifts based on biome/element exposure — different areas have enemies weak/strong to different elements. Player must carry multiple ammo types for different engagements. No pollution mechanic; defense is about player positioning + turret placement + drone deployment. Combat is mech-centric (player operates a mech suit), not factory-based. | Not applicable — combat is third-person shooter, not tower defense. Enemy weakness to damage types drives ammo selection as tactical gameplay, not engineering challenge. |

**Design Decision:** We adopt **Bob's Weapons Pack as the primary reference model** for three reasons:

1. It extends *vanilla* turrets rather than replacing them, keeping defense accessible and familiar while adding industrial depth.
2. Its ammo progression creates *capability shifts* (different ammo types = different engagement profiles) rather than just damage numbers.
3. The weapon-to-material connection is tight but bounded — each new ammo type ties to exactly one new chemical or metallurgical chain, not dozens.
4. It uses vanilla enemy ecology, which keeps the "enemy" side of the design simple while letting the *industrial* side (ammo/weapon chains) be the complexity driver.

**The Riftbreaker as secondary reference for tactical depth:** While we're not adopting its combat model (third-person shooter vs. tower defense), several of its systems offer useful mechanical inspiration:

- **Damage element taxonomy** → Could inform whether different ammo types have effectiveness modifiers against specific enemy classes (biters vs. spitters vs. worms) rather than just raw damage differences.
- **Modular weapon tradeoffs** → The idea that the same base can have multiple stat configurations (fire rate vs. ammo consumption, range vs. capacity) is a compelling way to add depth without adding new items.
- **Energy shield on power grid** → Defense infrastructure connecting to power network creates meaningful load management decisions.

GTNH is an excellent reference for late-game industrial integration but is not a model we're following — it replaces the combat layer entirely. Angel's approach (vanilla only) is our minimum baseline, and Pyanodon's selective depth gives us confidence that a bounded weapon/ammo system is viable.

**Decision:** Enemy design stays vanilla-based with no new enemy types. The military system's complexity comes from the *industrial supply chains behind defense*, not from enemy variety or AI complexity. This keeps combat approachable while keeping industry demanding.

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

## Pollution-to-Military Pressure Model — Resolved

### Core Mechanics (Resolved)

Pollution spreads from emitting sources in a radius. The density at any map location determines the military pressure score:

- **High pollution zones** near production blocks generate stronger/more frequent attacks on nearby infrastructure
- **Pollution fades over distance and time** — large spread-out factories have lower local pressure than dense clusters, all else equal
- **Different pollution types attract different attack profiles** at high thresholds (see below)
- **Mechanics are radius-based:** Bob's Weapons Pack proved this model works well; no complex time-decay curves or zone thresholds needed

### Pressure Consequences

Military pressure translates into two kinds of player-facing effects:

| Effect | Design role | Tradeoff lever |
|---|---|---|
| Attack frequency | Slow growth if ignored; factory must allocate capacity to defense | Encourages spreading pollution or reducing it at source |
| Attack intensity / unit composition | Drives need for progressive defense tech and ammo | Rewards investing in metallurgy/chemistry chains |

**Guardrail:** Military pressure should never make the player stop building their factory. It should influence *where* and *how* they build, and what defensive infrastructure they invest in. Attacks are a cost of doing business, not a wall that stops progress.

### Pollution Type Differentiation — Resolved: Yes (Mid-Game Depth)

**Decision:** At high pollution thresholds (>1000 units/s), differentiate attack profiles by pollution type. This gives players *why* to care about process choice, not just *that* dirty processes are bad.

| Pollution type | Attack profile at high threshold | Player-facing meaning |
|---|---|---|
| **General spread** (CO₂, heat, particulate) | Steady waves of standard biter/spitter units. Predictable pattern. | "The factory is loud. They come." — baseline pressure |
| **Acid emissions** (HCl, H₂SO₄ mists, SOₓ) | Spitters appear earlier and in higher proportion; acid attacks deal more damage to structures. | Acidic effluent accelerates enemy adaptation. Requires scrubber infrastructure or relocation. |
| **Heavy metal contamination** (Pb, Cd, Cr, etc.) | Worms burrow closer to base before emerging; ground units are armored variants with reduced turret effectiveness. | Toxic waste corrupts soil — enemies mutate toward the hazard zone. Requires containment, not distance alone. |

This differentiation stays at the *attack profile* level (which unit types appear and what they do), not at the *enemy variety* level (no new sprites). It rewards players who invested in scrubbers and filtration with different gameplay challenges rather than just "less attacks."

### Damage Element Effectiveness vs Enemy Classes — Adopted from The Riftbreaker

**Decision:** Ammo effectiveness is determined by an enemy weakness/resistance matrix, not raw damage numbers. This makes ammo selection an engineering decision: *which ammo should I produce for the enemy composition in this zone?*

| Ammo Type | Physical | Fire | Explosive | Kinetic Penetration |
|---|---|---|---|---|
| **Kinetic (T1)** | 100% | 75% | 50% | 85% |
| **Incendiary (T2a)** | 60% | 200% | 40% | 30% |
| **HE Explosive (T2b)** | 70% | 50% | 200% | 100% |
| **AP Penetrator (T3)** | 90% | 60% | 80% | 300% |

**Enemy class resistance profiles:**

| Enemy Class | Weak To | Resistant To | Engagement Advice |
|---|---|---|---|
| **Biters** (ground melee) | HE Explosive, AP Penetrator | Incendiary (thick carapace blocks flame) | Stock T2b/T3 ammo for biter-heavy zones; T1 only in safe areas |
| **Spitters** (ranged acid) | Incendiary (acid shell ignites), Kinetic (light body armor) | HE Explosive (splash wastes shots on small targets) | Stock T2a near spitter nests; use dispersed turret placement to avoid acid splash damage |
| **Worms** (burrowing ambush) | Incendiary (burns when emerging), HE Explosive (ground shockwave) | AP Penetrator (burrowed = evades kinetic energy) | Stock T2a/T2b near expansion frontier; sensor drones essential for early warning |
| **Elite/Armored variants** (high pollution zones) | AP Penetrator only | All other ammo types severely reduced | Must produce T3 ammo or rotate perimeter defense |

**Design principle:** No single ammo is universally optimal. Players must plan production quantities based on enemy composition in each zone, mirroring our core philosophy of "process choice" — which ammo you produce for a zone is a deliberate engineering decision, not just "which does highest DPS."

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

**Decision:** Space pressure is felt through gameplay experience only — running out of room naturally — with **no dashboard display**. This matches vanilla Factorio and Bob's/Angel's design philosophy. The tension comes from the player's own realization that they need to explore, which creates stronger emotional engagement than any metric could. Optional QOL mod integration (Milestones) can give players who want visibility a manual progress tracker, but the game itself never announces "you're running out of space — go explore now."

## Enemy Design — Resolved: Vanilla-Based Only

**Decision:** Use vanilla Factorio enemy units exclusively. No new enemy types, no custom biomes with unique fauna, no pollution-adapted mutant variants.

### Why Not New Enemy Types?

- **Scope explosion:** Every new enemy unit requires sprites/animations/attacks/deaths/loot tables — all time sinks. With 800-1200 items and ~4000 recipes already planned, military content must stay bounded.
- **Vanilla covers engagement profiles:** Biter (ground melee), spitter (ranged acid), worm (burrowing ambush) provide three distinct tactical challenges mapping to our ammo progression.
- **Bob's Weapons Pack proves this model works:** Deep military complexity comes from the *industrial supply chains behind defense*, not enemy variety.

### Which Vanilla Units Are Affected?

All standard biter/spitter/worm units are affected by pollution pressure. Enemy composition shifts at high pollution thresholds (more spitters and worms appear earlier), but these remain vanilla sprites with vanilla stats — only attack frequency and spawn density change.

## Ammo and Weapon Intermediate Chains — Resolved

This is where military meets industry — weapons and ammo are manufactured products requiring real supply chains, not craft-grid items. They connect back to chemistry and metallurgy.

### Resolved Ammo Categories — Full Supply Trees

*Aligned with Bob's Weapons Pack progression: 5 tiers matching the mod's industrial phases.*

| Tier | Ammo Type | Primary Feed Materials | Recipe Input Chain (key intermediates) | Industrial role |
|---|---|---|---|---|
| **T1** | Kinetic bullet (standard) | Lead core, copper jacket, steel case, gunpowder propellant | Galena → roasted/smeled lead ingot + chalcopyrite flotation → electrolytic Cu + hematite → pig iron → EAF steel sulfur combustion + charcoal → carbonized biomass/coal coke → ground powder | Early/mid defense — standard turret ammo. All players need this from Phase 1 onward. |
| **T2a** | Incendiary bullet | Fuel/oxidizer mix, magnesium ignition compound, steel casing | Oil refining → hydrocarbon fraction + chlor-alkali NaOH → hydrogenation FT synth glycerol or coconut palm oil + spodumene/carnotite → MgO calcined + sintered igniter pellet | Anti-spider and anti-light-armor suppression. First "capability shift" — incendiary burns through armor where kinetic fails. |
| **T2b** | Explosive (HE) bullet | High-explosive core, detonator compound, steel casing | Chlor-alkali → NaOH + H₂ → Haber-Bosch NH₃ + Ostwald chain → concentrated HNO₃ + FT glycerol or coconut palm oil → nitroglycerin precursor + galena lead → lead azide initiator (or cheaper ammonium nitrate alternative) | Heavy armor and hardened target engagement. Tunnels through spitter carapace. Requires dedicated chemical intermediate infrastructure — high barrier to entry |
| **T3** | Armor-piercing (AP) bullet | Tungsten core alloy, specialized propellant, copper sabot | Scheelite/Tungstenite → Caustic leach + purification → W powder + pressing/sintering + nitrocellulose/tungstenite + carbonized charcoal/calcined biomass | Engagement with heavily armored enemy variants at high pollution. Requires end-of-phase-2 metallurgy capability (tungsten processing). Capability shift: one shot pierces through multiple targets |
| **T4** | Penetration rocket (endgame) | Enriched uranium/tungsten payload, solid fuel booster, guidance module | Uraninates → acid leach → purification → conversion + enrichment cascade or thorium monazite → Th-cycle fuel Zr-Cl₄ chlorination → metal reduction → Zr cladding for casing + fission reactor → enriched U/W penetrator core | Endgame strategic capability. For fortress-level enemy encampments only. Ties to full nuclear fuel cycle + semiconductor guidance module from cleanroom fabrication |

**Design Decision:** The ammo chain stays bounded to **5 tiers across ~12 core recipes**. No exotic materials are required for mid-game ammo — every component ties to existing chemistry/metallurgy chains already defined in other documents.

### Weapon Progression Logic — Resolved: Capability Shifts Over Numbers

Weapon tiers follow Bob's Weapons Pack philosophy:

| Tier | Weapon Type | Ammo Used | Design role |
|---|---|---|---|
| T1 | Handgun (pistol) | Kinetic bullet | Starter weapon. Low capacity, low damage, no armor penetration. |
| T2a | Machine gun | Kinetic / Incendiary | Mid-range turret/ammo support. Requires lead/copper processing unlocked in Phase 1-2 bridge. |
| T2b | Flamethrower turret / incendiary launcher | Incendiary | Anti-spitter capability. First genuine capability shift over kinetic ammo. |
| T3a | Rocket launcher (man-portable) | Penetration rocket variant | Heavy anti-bunker capability. Requires nuclear/fission pathway or advanced metallurgy. |
| T3b | Explosive artillery shell | HE explosive | Siege capability against enemy strongholds. Late-phase unlocked through chemical depth. |
| T4 | Anti-materiel rifle / heavy cannon | AP penetrator + HE dual-compatible | Endgame precision weapon. Pierces through fortified structures and heavily armored enemies. |

**Capability shifts (not just damage numbers):**
- Kinetic → Incendiary: Burns through armor instead of relying on kinetic penetration.
- Incendiary → HE: One-shot high damage vs. single heavy targets (spitter nests, worm burrows).
- HE → AP: Pierces through multiple targets in a line.

## Turret Progression — Resolved

**Decision:** Extend vanilla turrets with tiered ammunition support. No new turret families in the core mod.

| Turret Family | Vanilla Equivalent | Tiered Ammo Support | Industrial Gate |
|---|---|---|---|
| Gun turret | Vanilla gun turret | T1 kinetic → T3 AP penetrator | Basic steel + lead/copper processing |
| Laser turret | Vanilla laser turret | None (self-contained energy weapon) | Semiconductor targeting module (T2) + precision optics chain |
| Flamethrower turret | Flamethrower (firewall) | T2a incendiary fuel | Petrochemical cracking or oil refining capability |
| Rocket turret | Vanilla rocket turret | T3 HE shell → T4 penetration rocket | Explosive compound chain / nuclear fuel cycle |

**Design Decision:** No new vanilla-derived turret families. This matches Bob's Weapons Pack's proven model — extend existing turrets with tiered ammo rather than creating new machine types that would inflate the ~80 machine scope target and complicate balance.

### Material Sources (Mapped to Infrastructure)

| Component | Mineral source | Refining chain | Infrastructure (infra.md §) |
|---|---|---|---|
| Lead core | Galena (Tier 2 underground), Pb/Zn polymineral | Roaster → smelter → refined lead ingot | infra.md §4 Smelting, §3 Thermal |
| Copper jacketing | Chalcopyrite, malachite | Froth flotation → electrolysis → high-purity cathode Cu | infra.md §2 Flotation, §7 Electrochemical |
| Steel casings (base alloy) | Hematite (Tier 1 surface) | Blast furnace → converter → steel EAF | infra.md §4 Smelting |
| Gunpowder propellant | Sulfur (Tier 1 surface) + charcoal/carbonized biomass | Simple carbonization + sulfur refinement | infra.md §3 Thermal |
| Nitric acid (HE component) | Chlor-alkali: NaOH → ammonia (Haber-Bosch) → Ostwald chain | Tank reactor → catalytic converter | infra.md §5 Reactors, §6 Solution Proc. |
| Glycerol/explosive precursor | Coconut palm oil (vegetable glycerol) or FT synthetic intermediate | Esterification/cracking plant | infra.md §8 Polymer/Composite |
| Tungsten for AP cores | Scheelite/Tungstenite (Tier 2 underground), W in BIF/polymineral | Caustic leach → purification → powder metallurgy pressing | infra.md §5 Reactors, §8 Polymer |
| Lead-acid propellant oxidizer | Potassium/sodium chlorates from trona/halite brine evaporation | Crystallization/evaporator → decomposition furnace | infra.md §6 Solution Proc. |

**Design Decision:** The ammo chain stays bounded to **~12 core recipes** across the four tiers, matching Bob's Weapons Pack scope. No exotic materials are required for mid-game ammo — every component ties to existing chemistry/metallurgy chains already defined in other documents.

## Defense Infrastructure Progression

Defense itself should follow the mod's progression philosophy — earned through industrial capability, not just tech tree advancement.

| Stage | Defense type | Driven by |
|---|---|---|
| Early | Passive barriers, basic turrets with kinetic ammo | Basic steel, lead, simple chemistry |
| Mid | Active defense grids, incendiary/explosive ammo supply | Chemical intermediates, alloy production, precision manufacturing |
| Late | Distributed defense network, automated targeting, specialized ammo | Semiconductors, automation tools |
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

### Sustained Defense Power Load — Adopted from The Riftbreaker

**Decision:** All turrets and defense infrastructure draw sustained power, not just one-time build cost. Defense creates ongoing grid load that directly ties military back to our power-system.md design.

| Turret Type | Tier 1 Power (kW) | Tier 2 Power (kW) | Tier 3 Power (kW) | Notes |
|---|---|---|---|---|
| Gun Turret | 5 kW | 7 kW | 10 kW | Scaling with ammo type complexity; AP-capable turrets draw more for targeting electronics |
| Laser Turret | N/A | 15 kW | 25 kW | Power-scaled by beam intensity tier |
| Flamethrower Turret | 8 kW | 12 kW | 18 kW | Pump and mixing mechanisms require continuous power |
| Rocket Turret | 10 kW | 15 kW | 30 kW | Scaling with missile rack capacity and guidance electronics |

**Engineering tension:** "Can my grid handle this many turrets running?" creates the same kind of design problem we have for factories. Players must plan defense load alongside production load, choose between defensive density and production expansion, or invest in energy storage/power infrastructure upgrades as a military-support decision.

### Late-Game Drone Defense — Adopted from The Riftbreaker

**Decision:** Two drone types (patrol attack + sensor early-warning) connected to our semiconductor/automation supply chain. Integrated into the military infrastructure catalog as late-game defense products.

| Drone Type | Tier/Phase | Operations | Supply Chain Requirement | Design Role |
|---|---|---|---|---|
| **Patrol Drone (Attack)** | Phase 3+ | Autonomous patrol of designated perimeter zones; auto-targets nearby enemies within range | Semiconductor guidance module + precision power cell (lithium battery from electrochemical chain) + tungsten micro-penetrator ammo | Fills gaps between stationary turret coverage; handles small infiltration waves that would overwhelm fixed positions. Battery life = operational radius × time |
| **Sensor Drone (Early Warning)** | Phase 3+ | Scans area for burrowing threats and enemy composition analysis; broadcasts warning data to nearby turrets | Semiconductor guidance module + cryogenic sensor array (superconducting materials from Nb₃Sn wire chain) + precision optics | Reveals hidden worm burrows before they emerge; identifies incoming enemy class composition so players can switch turret ammo types proactively. Essential near expansion frontier |

**Design principle:** Drones are engineered systems, not magical upgrades — each connects to real supply chains from earlier in the mod. Drone defense complements but doesn't replace stationary turrets; it extends coverage where fixed placement is impractical (perimeter gaps, expansion zones).

## Open Decisions — All Resolved

| Decision | Resolution | Rationale |
|---|---|---|
| **Attack mechanics detail** ✅ | Radius-based density model consistent with Bob's Weapons Pack. No complex time-decay curves or zone thresholds needed. | Simple, predictable, proven by extensive playtesting in Bob's ecosystem. |
| **Enemy unit variety** ✅ | Vanilla units only. No new enemy types, no pollution-adapted variants. All biter/spitter/worm types affected by pollution scaling but remain vanilla sprites with vanilla stats. | Scope bounded. Complexity comes from *supply chains behind defense*, not enemy variety. Bob's Weapons Pack model works well. |
| **Defense turrets** ✅ | Extend existing vanilla turrets with tiered ammo support only. No new turret families in the core mod. Flamethrower uses incendiary fuel, rocket turret uses HE/ap shells, gun turret upgrades from kinetic to AP. | Matches Bob's Weapons Pack. Avoids inflating ~80 machine scope target and simplifies balance. |
| **Nuclear ammo scope** ✅ | T4 penetration rocket uses enriched uranium/tungsten payload — connects to full nuclear fuel cycle + semiconductor guidance module. Not true "nuclear explosive" ammo; it's a kinetic penetrator with nuclear-grade materials for density/payload purposes. | Ties military to nuclear chain without requiring actual nuclear weapons. Fits the industrial integration philosophy. |
| **Pollution type differentiation** ✅ | Yes — at high thresholds (>1000 units/s), differentiate attack profiles: general spread (baseline waves), acid emissions (earlier spitters, more structure damage), heavy metal (worms burrow closer, armored ground variants). | Gives players *why* to care about process choice. Stays at attack profile level only — no new sprites or enemy types. |
| **Defense automation via connected control** ✅ | No native combat automation in core mod. Defense logistics are handled by vanilla logistics/bots + manual turret aiming. Optional extension pack (`logistics-advanced-trains` or `difficulty-advanced`) may add automated targeting integrations as opt-in QOL. | Combat automation is a UX layer, not an industrial system. Keep it out of core scope; defer to extensions if requested. |

## Extension Pack Scope — Clarified

Military content for extension packs follows the core mod's design but adds depth for specific audiences:

| Extension | Military Content Added | Notes |
|---|---|---|
| **difficulty-advanced** | Extended weapon tiers (sniper, anti-materiel rifle levels at very late tiers), smarter enemy AI, fortified base types. Requires Combat Mechanics Overhaul dependency. | Adds pressure; not new industrial systems. |
| **difficulty-extreme** | Pollution multipliers ×3–5×, aggressive biter scaling, pollution-adapted elite variants with armor/acid resistance. Resource scarcity on combat-critical materials (lead, tungsten). | Hardcore players who want military to be the bottleneck. |
| **endgame-simulation-hard** | More complex debug requirements for information-formed entities in the simulation network; harder fleet management. Combat-adjacent but tied to endgame complexity. | Players who want the endgame to challenge them militarily too. |

## Summary of Design Decisions

Here's a quick reference of everything that was decided:

| Decision | Resolution |
|---|---|
| Reference model | Bob's Weapons Pack (primary), Angel's minimum baseline, GTNH for late-game integration ideas |
| Enemy types | Vanilla biter/spitter/worm only — no new sprites |
| Ammo tiers | 5 tiers (T1–T4), ~12 core recipes bounded to existing chains |
| Turret approach | Extend vanilla turrets with tiered ammo — no new families |
| Pollution scaling | Radius-based density model, pollution-type differentiation at high thresholds |
| Defense automation | Core mod: none. Extensions may add QOL integrations as opt-in. |
| Nuclear ammo | T4 penetrator rocket uses nuclear materials but is kinetic, not explosive |

## Status

**Resolved.** Market research complete. All open design decisions have been answered. This document is ready to be used as the foundation for implementing military content in Phase C of the plan (recipe/infrastructure mapping). The extension pack scope is also defined so implementation work can branch into core vs. opt-in content.