# Military System Design

*Status: Draft — ammunition and sustained-defense-power principles accepted; military scope, product details, and values remain open*
*Last updated: 2026-11-12*

Related documents: [Mod Overview](mod-overview.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Minerals and Refining](minerals-and-refining.md), [Infrastructure](infrastructure.md), [Power System](power-system.md). Related decisions: [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md), [ADR-0013](adrs/ADR-0013-military-pressure-model.md), [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md), [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md), [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md).

> **Decision status:** The source marked multiple choices "Resolved" or "Adopted" without approval records. The user has since accepted capability-based ammunition progression and sustained power for defense, rejected military drones in favor of fixed defenses, and requested bounded, layer-based electrical turret additions. These outcomes and the still-open details are recorded in the linked ADRs. Do not treat candidate product counts, families, or values as approved unless explicitly noted.

## Summary

This draft proposes military and expansion pressure as consequences of industrial choices. Candidate pressure axes are pollution, which can create defensive demand, and process footprint, which can create spatial urgency. Candidate ammo and defense chains connect chemistry, metallurgy, power, and logistics. These directions and their approval state are recorded in the linked ADRs; detailed values remain provisional.

## Purpose and Boundaries

- **In scope:** Candidate military-pressure behavior, defense progression, ammo and weapon product chains, space-platform integration, and core/extension boundaries.
- **Out of scope:** Validated enemy balance, attack-wave mechanics, AI group targeting, and detailed combat formulas; these require gameplay design and testing.
- **Source-of-truth boundaries:** Placeable defense entities belong in [Infrastructure](infrastructure.md); non-building product identities and supply paths belong in [Intermediate Products](intermediate-products.md); power behavior belongs in [Power System](power-system.md).

## Design Philosophy

The military and expansion systems exist to give weight to process selection. There are two independent pressure axes arising from industrial decisions:

1. **Pollution pressure** — dirty processes generate attacks that require defense infrastructure
2. **Space pressure** — inefficient processes demand far more footprint, forcing urgency about expansion

Both pressures give the player a reason to care about *how* they produce things, not just *what*. They are the economic consequences of industrial choices — the counterweight to whatever benefit the player gains from choosing a particular process path.

### Pollution Pressure

Pollution is an economic consequence of industrial processes, not a collection of special-case enemy mechanics. Dirty, high-throughput production defers costs into military consequences; cleaner routes trade for infrastructure, power, or process complexity.

**Key principle:** Military pressure should feel like an engineering problem (how do I design my factory to minimize defensive overhead?), not a combat challenge (can I build better turrets?).

### Reference Model and Core Scope — Candidate

The source proposes Bob's Weapons Pack as the primary reference, with a vanilla-based enemy roster and industrial supply chains as the main source of military complexity. The user requested a bounded, layer-based turret roster with more power-based options; plasma and railgun turrets are proposals alongside the existing laser turret, not an accepted roster. Their progression and core-versus-extension placement remain open. Riftbreaker is a secondary source of mechanical ideas, not a proposed combat-model replacement. The comparative research and rationale are preserved in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md).

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

## Candidate Pollution-to-Military Pressure Model

### Candidate Core Mechanics

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

### Candidate Pollution-Type Differentiation

**Candidate direction — see [ADR-0013](adrs/ADR-0013-military-pressure-model.md):** At a proposed high threshold (>1000 units/s), differentiate attack profiles by pollution type. The threshold and effects are unvalidated.

| Pollution type | Attack profile at high threshold | Player-facing meaning |
|---|---|---|
| **General spread** (CO₂, heat, particulate) | Steady waves of standard biter/spitter units. Predictable pattern. | "The factory is loud. They come." — baseline pressure |
| **Acid emissions** (HCl, H₂SO₄ mists, SOₓ) | Spitters appear earlier and in higher proportion; acid attacks deal more damage to structures. | Acidic effluent accelerates enemy adaptation. Requires scrubber infrastructure or relocation. |
| **Heavy metal contamination** (Pb, Cd, Cr, etc.) | Worms burrow closer to base before emerging; ground units are armored variants with reduced turret effectiveness. | Toxic waste corrupts soil — enemies mutate toward the hazard zone. Requires containment, not distance alone. |

This differentiation stays at the *attack profile* level (which unit types appear and what they do), not at the *enemy variety* level (no new sprites). It rewards players who invested in scrubbers and filtration with different gameplay challenges rather than just "less attacks."

### Candidate Damage-Effectiveness Matrix

**Candidate mechanic — see [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md), with the Riftbreaker comparison in [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md):** Ammo effectiveness could use an enemy weakness/resistance matrix rather than raw damage numbers. Adoption remains open.

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
| **Worms** (burrowing ambush) | Incendiary (burns when emerging), HE Explosive (ground shockwave) | AP Penetrator (burrowed = evades kinetic energy) | Stock T2a/T2b near expansion frontier; prioritize fixed defenses |
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

**Candidate direction — see [ADR-0013](adrs/ADR-0013-military-pressure-model.md):** Space pressure would be communicated through gameplay rather than an in-game dashboard. Whether this should remain entirely implicit, or use optional external quality-of-life support, remains open.

## Candidate Enemy Scope

**Candidate direction — see [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md):** Use vanilla Factorio enemy units without new enemy types or pollution-adapted variants. Acceptance remains unverified.

### Candidate Changes to Vanilla Units

The source proposes that pollution affect vanilla biter, spitter, and worm pressure, including earlier changes in enemy composition, while retaining vanilla sprites and stats. This conflicts with the pollution-type proposal for armored ground variants and other profile changes; reconcile the conflict in [ADR-0013](adrs/ADR-0013-military-pressure-model.md) before treating either behavior as intended.

## Candidate Ammo and Weapon Intermediate Chains

This is where military meets industry — weapons and ammo are manufactured products requiring real supply chains, not craft-grid items. They connect back to chemistry and metallurgy.

### Capability-Based Ammunition (Accepted Principle; Contents Provisional)

*Capability-based progression is accepted. The listed ammo types, supply trees, tier placement, and recipe totals remain candidates.*

| Tier | Ammo Type | Primary Feed Materials | Recipe Input Chain (key intermediates) | Industrial role |
|---|---|---|---|---|
| **T1** | Kinetic bullet (standard) | Lead core, copper jacket, steel case, gunpowder propellant | Galena → roasted/smeled lead ingot + chalcopyrite flotation → electrolytic Cu + hematite → pig iron → EAF steel sulfur combustion + charcoal → carbonized biomass/coal coke → ground powder | Early/mid defense — standard turret ammo. All players need this from Phase 1 onward. |
| **T2a** | Incendiary bullet | Fuel/oxidizer mix, magnesium ignition compound, steel casing | Oil refining → hydrocarbon fraction + chlor-alkali NaOH → hydrogenation FT synth glycerol or coconut palm oil + spodumene/carnotite → MgO calcined + sintered igniter pellet | Anti-spider and anti-light-armor suppression. First "capability shift" — incendiary burns through armor where kinetic fails. |
| **T2b** | Explosive (HE) bullet | High-explosive core, detonator compound, steel casing | Chlor-alkali → NaOH + H₂ → Haber-Bosch NH₃ + Ostwald chain → concentrated HNO₃ + FT glycerol or coconut palm oil → nitroglycerin precursor + galena lead → lead azide initiator (or cheaper ammonium nitrate alternative) | Heavy armor and hardened target engagement. Tunnels through spitter carapace. Requires dedicated chemical intermediate infrastructure — high barrier to entry |
| **T3** | Armor-piercing (AP) bullet | Tungsten core alloy, specialized propellant, copper sabot | Scheelite/Tungstenite → Caustic leach + purification → W powder + pressing/sintering + nitrocellulose/tungstenite + carbonized charcoal/calcined biomass | Engagement with heavily armored enemy variants at high pollution. Requires end-of-phase-2 metallurgy capability (tungsten processing). Capability shift: one shot pierces through multiple targets |
| **T4** | Penetration rocket (endgame) | Enriched uranium/tungsten payload, solid fuel booster, guidance module | Uraninates → acid leach → purification → conversion + enrichment cascade or thorium monazite → Th-cycle fuel Zr-Cl₄ chlorination → metal reduction → Zr cladding for casing + fission reactor → enriched U/W penetrator core | Endgame strategic capability. For fortress-level enemy encampments only. Ties to full nuclear fuel cycle + semiconductor guidance module from cleanroom fabrication |

**Open scope — see [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md):** The source says **5 tiers across ~12 core recipes**, but elsewhere says four tiers and lists T1, T2a, T2b, T3, and T4. The user accepted the capability-based principle, not either conflicting count or every listed type and recipe.

### Candidate Weapon Progression Logic — Capability Shifts Over Numbers

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

## Candidate Turret Progression

**Proposed direction — see [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md):** Keep the turret roster bounded across progression layers, with greater emphasis on electrical options; do not assume it is vanilla-only. Plasma and railgun turrets are candidates, not an approved roster. Their layer and tier placement, and core-versus-extension scope, remain open.

| Turret Family | Relationship to Vanilla | Candidate Role / Progression | Industrial / Balance Gate |
|---|---|---|---|
| Gun turret | Vanilla | T1 kinetic → T3 AP ammunition | Basic steel + lead/copper processing |
| Laser turret | Existing vanilla electrical family | Electrical baseline; tier-specific output and grid demand need validation | Semiconductor targeting module (T2) + precision optics chain |
| Plasma turret | New electrical candidate | Artillery-like plasma orb with a relatively large splash radius | Substantial power draw proposed; tier, range, ammunition/consumables, and values TBD |
| Railgun turret | New electrical candidate | Very-long-range beam/shot damages enemies along its path with small-to-medium splash, potentially to maximum visible or targetable range | Substantial power draw proposed; attack model, tier, ammunition/consumables, and values TBD |
| Flamethrower turret | Vanilla | T2a incendiary fuel | Petrochemical cracking or oil refining capability |
| Rocket turret | Vanilla | T3 HE shell → T4 penetration rocket | Explosive compound chain / nuclear fuel cycle |

Both proposed electrical families should require substantial power as a balancing cost. Whether this is sustained draw, firing bursts, stored energy per shot, or a combination remains open; see [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md). The source's earlier rationale for avoiding new turret families remains historical context, not an approved user decision.

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

**Candidate scope — see [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md):** A later source statement says **~12 core recipes across four tiers**, conflicting with the five-tier wording above. The recipe and tier counts remain open.

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

### Sustained Defense Power Load (Accepted Principle; Values Provisional)

**Accepted principle — see [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md):** Defense infrastructure imposes sustained power demand. The values below are source proposals, not validated requirements; the plasma and railgun power profiles are also unresolved.

| Turret Type | Tier 1 Power (kW) | Tier 2 Power (kW) | Tier 3 Power (kW) | Notes |
|---|---|---|---|---|
| Gun Turret | 5 kW | 7 kW | 10 kW | Scaling with ammo type complexity; AP-capable turrets draw more for targeting electronics |
| Laser Turret | N/A | 15 kW | 25 kW | Power-scaled by beam intensity tier |
| Plasma Turret | TBD | TBD | TBD | Substantial draw proposed; tier placement, peak-versus-sustained profile, and values remain open |
| Railgun Turret | TBD | TBD | TBD | Substantial draw proposed; tier placement, firing profile, and values remain open |
| Flamethrower Turret | 8 kW | 12 kW | 18 kW | Pump and mixing mechanisms require continuous power |
| Rocket Turret | 10 kW | 15 kW | 30 kW | Scaling with missile rack capacity and guidance electronics |

**Engineering tension:** "Can my grid handle this many turrets running?" creates the same kind of design problem we have for factories. Players must plan defense load alongside production load, choose between defensive density and production expansion, or invest in energy storage/power infrastructure upgrades as a military-support decision.

### Optional Advanced Military Extension: Spider-Bot and Power-Suit Additions

The user rejected military drones and specified fixed defenses. An optional, more advanced military extension may consider a spider-bot vehicle and power-suit equipment additions. This direction is distinct from drone defense; exact scope, product families, unlocks, and supply paths remain open. The rejected drone proposal and its supply-chain details are preserved in [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md).

## Decision Records and Open Items

The former source table marked these choices resolved. User review has since established the outcomes below; candidate details remain provisional where noted:

| Topic | Record | Current status |
|---|---|---|
| Core enemy and turret scope; combat automation boundary | [ADR-0012](adrs/ADR-0012-bound-core-military-scope.md) | Proposed; bounded, layer-based electrical direction recorded; roster and scope open |
| Pollution and space pressure | [ADR-0013](adrs/ADR-0013-military-pressure-model.md) | Proposed; thresholds and feedback need validation |
| Ammo progression and nuclear-material use | [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md) | Capability-based principle accepted; type, tier, supply-chain, and recipe-count details remain open |
| Sustained defense power load | [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md) | Principle accepted; profiles and values need validation |
| Military drones; advanced player equipment | [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md) | Military drones rejected; optional spider-bot and power-suit extension direction recorded |

Other open questions:

- Confirm which military scope and pressure-model proposals belong in core.
- Decide the electrical turret progression: tier and phase placement, core-versus-extension scope, ammunition or energy model, range and splash behavior, and power draw profile and values.
- Reconcile the ammo categories, T3a/T3b weapon variants, and five-tier/four-tier statements before catalog enumeration.
- Reconcile the no-new-enemy-variant proposal with the heavy-metal pollution table's armored ground variants.
- Validate pollution units and the proposed `>1000 units/s` threshold against the implementation model.
- Decide whether space pressure is entirely implicit and whether any external quality-of-life integration is in scope.
- Define the optional advanced military extension scope for spider-bot and power-suit additions.
- Align sustained defense power demand with the accepted core power model; reconcile the differing laser-turret estimates in this document and [Infrastructure](infrastructure.md).

## Candidate Extension Pack Scope

The following extension concepts are source proposals only; none is approved.

Military content for extension packs follows the core mod's design but adds depth for specific audiences:

| Extension | Military Content Added | Notes |
|---|---|---|
| **difficulty-advanced** | Extended weapon tiers (sniper, anti-materiel rifle levels at very late tiers), optional spider-bot vehicle and power-suit equipment additions, smarter enemy AI, fortified base types. Requires Combat Mechanics Overhaul dependency. | Candidate additions only; scope and dependency need validation. |
| **difficulty-extreme** | Pollution multipliers ×3–5×, aggressive biter scaling, pollution-adapted elite variants with armor/acid resistance. Resource scarcity on combat-critical materials (lead, tungsten). | Hardcore players who want military to be the bottleneck. |
| **endgame-simulation-hard** | More complex debug requirements for information-formed entities in the simulation network; harder fleet management. Combat-adjacent but tied to endgame complexity. | Players who want the endgame to challenge them militarily too. |

## Current Status and Next Work

This is a candidate design, not a complete military specification. Capability-based ammunition and sustained defense power are accepted principles; the turret roster remains proposed, and military drones are rejected. The detailed ammunition, weapon, power-load, and extension tables remain candidate content, not final catalog entries, build recipes, or balance values. The rejected drone roles and supply chains are preserved in [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md).

Next, reconcile military scope with the Phase 3 infrastructure inventory, include or exclude military product families during Phase 4 coverage, and defer final product identities and recipes to Phases 5 and 6 of [the plan](plan.md). Preserve the source's ammo-tier and recipe-count conflict until it is explicitly resolved.