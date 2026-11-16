# Military System Design

*Status: Core defense roster and enemy/pollution boundary selected; detailed products and values remain open*
*Last updated: 2026-11-16*

Related documents: [Mod Overview](mod-overview.md), [Chemical Products and Processes](chemical-processes.md), [Intermediate Products](intermediate-products.md), [Minerals and Refining](minerals-and-refining.md), [Infrastructure](infrastructure.md), [Power System](power-system.md). Related ADRs: [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md), [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md), [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md), [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md), and [ADR-0072](adrs/ADR-0072-retain-vanilla-enemies-and-pollution.md).

## Summary

Vanilla enemies and pollution behavior provide the Core pressure baseline. Core retains vanilla fixed defenses and adds plasma and railgun turret families; capability-based ammunition and sustained defense power remain selected principles. Exact products, profiles, phases, and balance remain open.

## Purpose and Boundaries

- **In scope:** Candidate military-pressure behavior, defense progression, ammo and weapon product chains, space-platform integration, and core/extension boundaries.
- **Out of scope:** Validated enemy balance, attack-wave mechanics, AI group targeting, and detailed combat formulas; these require gameplay design and testing.
- **Source-of-truth boundaries:** Placeable defense entities belong in [Infrastructure](infrastructure.md); non-building product identities and supply paths belong in [Intermediate Products](intermediate-products.md); power behavior belongs in [Power System](power-system.md).

## Design Philosophy

The draft proposes two complementary pressure axes arising from industrial decisions:

1. **Pollution pressure** — dirty processes generate attacks that require defense infrastructure
2. **Space pressure** — inefficient processes demand far more footprint, forcing urgency about expansion

Both pressures give the player a reason to care about *how* they produce things, not just *what*. They are the economic consequences of industrial choices — the counterweight to whatever benefit the player gains from choosing a particular process path.

### Pollution Pressure

Pollution is an economic consequence of industrial processes, not a collection of special-case enemy mechanics. Dirty, high-throughput production defers costs into military consequences; cleaner routes trade for infrastructure, power, or process complexity.

**Key principle:** Military pressure should feel like an engineering problem (how do I design my factory to minimize defensive overhead?), not a combat challenge (can I build better turrets?).

### Reference Model and Core Scope

Core retains the base-game fixed-defense families and adds plasma and railgun turrets under [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md). Their specific progression remains open. Bob's Weapons Pack and Riftbreaker are references for ideas, not dependencies or replacement combat models.

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

## Core Pollution and Military Pressure

### Core Mechanics

Use the base game's enemy types and pollution response under [ADR-0072](adrs/ADR-0072-retain-vanilla-enemies-and-pollution.md). Process emissions may change ordinary pollution pressure, but Core does not add pollution-type-specific attack profiles, new enemy variants, or a separate pressure score. The separately accepted map-edge patrol concept remains with [Map and World Generation](map-world-generation.md).

### Pressure Consequences

Military pressure translates into two kinds of player-facing effects:

| Effect | Design role | Tradeoff lever |
|---|---|---|
| Attack frequency | Slow growth if ignored; factory must allocate capacity to defense | Encourages spreading pollution or reducing it at source |
| Attack intensity / unit composition | Drives need for progressive defense tech and ammo | Rewards investing in metallurgy/chemistry chains |

**Guardrail:** Military pressure should never make the player stop building their factory. It should influence *where* and *how* they build, and what defensive infrastructure they invest in. Attacks are a cost of doing business, not a wall that stops progress.

### Optional Pollution-Type Differentiation Candidate

This unapproved extension candidate would differentiate attack profiles by pollution type at a proposed high threshold (>1000 units/s). The threshold and effects are unvalidated and are not Core behavior.

| Pollution type | Attack profile at high threshold | Player-facing meaning |
|---|---|---|
| **General spread** (CO₂, heat, particulate) | Steady waves of standard biter/spitter units. Predictable pattern. | "The factory is loud. They come." — baseline pressure |
| **Acid emissions** (HCl, H₂SO₄ mists, SOₓ) | Spitters appear earlier and in higher proportion; acid attacks deal more damage to structures. | Acidic effluent accelerates enemy adaptation. Requires scrubber infrastructure or relocation. |
| **Heavy metal contamination** (Pb, Cd, Cr, etc.) | Worms burrow closer to base before emerging; ground units are armored variants with reduced turret effectiveness. | Toxic waste corrupts soil — enemies mutate toward the hazard zone. Requires containment, not distance alone. |

Whether such an extension would change existing unit behavior, add variants, or use these profiles at all remains open.

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
| **Elite/Armored variants** (extension candidate only) | AP Penetrator only | All other ammo types severely reduced | Must produce T3 ammo or rotate perimeter defense |

**Design principle:** No single ammo is universally optimal. Players must plan production quantities based on enemy composition in each zone, mirroring our core philosophy of "process choice" — which ammo you produce for a zone is a deliberate engineering decision, not just "which does highest DPS."

## Candidate Space Pressure — Process-Driven Expansion Urgency

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

## Enemy Scope

Core uses vanilla enemy units without new pollution-adapted variants under [ADR-0072](adrs/ADR-0072-retain-vanilla-enemies-and-pollution.md).

### Candidate Changes to Vanilla Units

New pollution-driven composition changes and armored variants are not Core behavior. They may be considered separately for an optional extension; no such extension is selected.

## Candidate Ammo and Weapon Intermediate Chains

This is where military meets industry — weapons and ammo are manufactured products requiring real supply chains, not craft-grid items. They connect back to chemistry and metallurgy.

### Capability-Based Ammunition (Accepted Principle; Contents Provisional)

*Capability-based progression is accepted. The listed ammo types, supply trees, tier placement, and recipe totals remain candidates.*

References below to armored variants, altered burrowing, or other non-vanilla enemy behavior are illustrative extension scenarios, not selected Core enemies.

| Tier | Ammo Type | Primary Feed Materials | Recipe Input Chain (key intermediates) | Industrial role |
|---|---|---|---|---|
| **T1** | Kinetic bullet (standard) | Lead core, copper jacket, steel case, gunpowder propellant | Candidate lead, copper, steel, and propellant paths; source access, processing, and the complete route remain open | Candidate early/mid turret ammunition; no specific ingredient list is selected. |
| **T2a** | Incendiary bullet | Fuel/oxidizer mix, magnesium ignition compound, steel casing | Candidate organic and magnesium feeds; dolomite is a possible magnesium source. Precursors, recovery, processing, and the complete route remain open | Candidate incendiary capability; specific targets and performance remain open. |
| **T2b** | Explosive (HE) bullet | Candidate explosive and initiating components, steel casing | Candidate chemical precursors and assembly; feed roles, compatibility, and the complete route remain open | Candidate heavy-target or area-effect capability; performance and supporting infrastructure remain open. |
| **T3** | Armor-piercing (AP) bullet | Tungsten core alloy, specialized propellant, copper sabot | Scheelite/Tungstenite → Caustic leach + purification → W powder + pressing/sintering + nitrocellulose/tungstenite + carbonized charcoal/calcined biomass | Engagement with heavily armored enemy variants at high pollution. Requires end-of-phase-2 metallurgy capability (tungsten processing). Capability shift: one shot pierces through multiple targets |
| **T4** | Penetration rocket (endgame candidate) | Tungsten or optional depleted-uranium material, booster, guidance module | Candidate dense-material use; any depleted-uranium metal preparation requires a separately qualified route. Exact materials and recipes remain open | Optional military reuse under [ADR-0063](adrs/ADR-0063-select-depleted-uranium-oxide-reuse.md), not a requirement for enriched fuel, thorium processing, or operating a reactor. Weapon scope and gate remain provisional |

Depleted-uranium military uses remain optional candidates, not an accepted weapon roster or guaranteed material sink. Fission operation never requires ammunition consumption; surplus depleted oxide has the continuous disposal route owned by [Power System](power-system.md#phase-2-startup-and-material-handling). Depleted oxide is not automatically metal or qualified reactor fuel.

**Open scope — see [ADR-0014](adrs/ADR-0014-capability-based-ammunition.md):** The source says **5 tiers across ~12 core recipes**, but elsewhere says four tiers and lists T1, T2a, T2b, T3, and T4. The user accepted the capability-based principle, not either conflicting count or every listed type and recipe.

### Candidate Weapon Progression Logic — Capability Shifts Over Numbers

Weapon tiers follow Bob's Weapons Pack philosophy:

| Tier | Weapon Type | Ammo Used | Design role |
|---|---|---|---|
| T1 | Handgun (pistol) | Kinetic bullet | Starter weapon. Low capacity, low damage, no armor penetration. |
| T2a | Machine gun | Kinetic / Incendiary | Mid-range turret/ammo support. Requires lead/copper processing unlocked in Phase 1-2 bridge. |
| T2b | Flamethrower turret / incendiary launcher | Incendiary | Anti-spitter capability. First genuine capability shift over kinetic ammo. |
| T3a | Rocket launcher (man-portable) | Penetration rocket variant | Candidate advanced-metallurgy/electronics capability; optional depleted-uranium material use does not require reactor operation. Exact scope and gate remain open. |
| T3b | Explosive artillery shell | HE explosive | Siege capability against enemy strongholds. Late-phase unlocked through chemical depth. |
| T4 | Anti-materiel rifle / heavy cannon | AP penetrator + HE dual-compatible | Endgame precision weapon. Pierces through fortified structures and heavily armored enemies. |

**Capability shifts (not just damage numbers):**
- Kinetic → Incendiary: Burns through armor instead of relying on kinetic penetration.
- Incendiary → HE: One-shot high damage vs. single heavy targets (spitter nests, worm burrows).
- HE → AP: Pierces through multiple targets in a line.

## Core Turret Scope and Candidate Progression

**Selected scope — see [ADR-0071](adrs/ADR-0071-bound-core-defense-roster.md):** Retain base-game gun, laser, flamethrower, and artillery defense families and add plasma and railgun turret families to Core. Roles and gates below are candidates, not approved recipes or tier counts. Space Age's rocket turret is not a base-game family and is not selected for Core.

| Turret Family | Relationship to Vanilla | Candidate Role / Progression | Industrial / Balance Gate |
|---|---|---|---|
| Gun turret | Vanilla | T1 kinetic → T3 AP ammunition | Basic steel + lead/copper processing |
| Laser turret | Existing vanilla electrical family | Electrical baseline; tier-specific output and grid demand need validation | Semiconductor targeting module (T2) + precision optics chain |
| Plasma turret | New electrical candidate | Artillery-like plasma orb with a relatively large splash radius | Substantial power draw proposed; tier, range, ammunition/consumables, and values TBD |
| Railgun turret | New electrical candidate | Very-long-range beam/shot damages enemies along its path with small-to-medium splash, potentially to maximum visible or targetable range | Substantial power draw proposed; attack model, tier, ammunition/consumables, and values TBD |
| Flamethrower turret | Vanilla | T2a incendiary fuel | Petrochemical cracking or oil refining capability |
| Artillery turret | Vanilla base-game family | Long-range fixed artillery; exact progression open | Artillery shells and industrial supply path remain open |
| Rocket turret | Space Age-only vanilla counterpart; not selected in Core | Separate candidate, not an alias for the railgun | No nuclear-cycle or enriched-fuel requirement is selected |

Both added electrical families require substantial power as a balancing cost. Whether their draw is sustained, firing bursts, stored energy per shot, or a combination remains open; see [ADR-0015](adrs/ADR-0015-sustained-power-for-defense.md).

### Candidate Material Sources (Mapped to Infrastructure)

The following links are hypotheses, not established routes or required starting resources. Validate feed access, process compatibility, and actual consumers before approving them.

| Component | Mineral source | Refining chain | Infrastructure (infra.md §) |
|---|---|---|---|
| Lead core | Galena (Tier 2 underground), Pb/Zn polymineral | Roaster → smelter → refined lead ingot | infra.md §4 Smelting, §3 Thermal |
| Copper jacketing | Chalcopyrite, malachite | Froth flotation → electrolysis → high-purity cathode Cu | infra.md §2 Flotation, §7 Electrochemical |
| Steel casings (base alloy) | Hematite (Tier 1 surface) | Blast furnace → converter → steel EAF | infra.md §4 Smelting |
| Gunpowder propellant | Sulfur (Tier 1 surface) + charcoal/carbonized biomass | Simple carbonization + sulfur refinement | infra.md §3 Thermal |
| Nitric acid (candidate HE component) | Industrial-gas and reagent feeds are candidates | Source and process chain remain open | infra.md §5 Reactors, §6 Solution Proc. |
| Glycerol/explosive precursor | Coconut palm oil (vegetable glycerol) or FT synthetic intermediate | Esterification/cracking plant | infra.md §8 Polymer/Composite |
| Tungsten for AP cores | Scheelite/Tungstenite (Tier 2 underground), W in BIF/polymineral | Caustic leach → purification → powder metallurgy pressing | infra.md §5 Reactors, §8 Polymer |
| Candidate oxidizer | Evaporite or brine-derived feed candidates | Material identity, suitability, and processing remain open | infra.md §6 Solution Proc. |

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

## Candidate Integration with a Space-Platform Objective

The space-platform objective is not an approved second victory condition. Space Age platforms are not part of the selected no-DLC base; any separate space implementation and objective remain open. Candidate considerations:

- **Rocket fuel** connects to chemical chains — sulfuric acid processing from oil or coal routes can feed into hydrazine/monopropellant production
- **Rocket parts** connect to intermediate product chains — aluminum alloys, titanium structures, semiconductor sensors for guidance systems
- **Ammo for defending the launch site** — late-game military pressure around the space platform area needs dedicated defense logistics

The proposed aspirations are:
1. **Project Prometheus:** Build the distributed planetary computing network (the mod's signature endgame)
2. **Space platform completion:** Use the mod's industrial ecosystem to produce rocket fuel and parts through new chains, if the objective is included

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

Vanilla deployable combat-robot capsules are outside Core and may be offered by an extension under ADR-0071. New patrol-attack and sensor/early-warning drone concepts remain rejected under [ADR-0016](adrs/ADR-0016-late-game-defense-drones.md). An optional advanced military extension may also consider spider-bot vehicles and power-suit additions; exact scope, unlocks, and supply paths remain open.

## Open Design Decisions

- Decide the electrical turret progression: tier and phase placement, ammunition or energy model, range and splash behavior, and power draw profile and values.
- Reconcile the ammo categories, T3a/T3b weapon variants, and five-tier/four-tier statements before catalog enumeration.
- If an enemy/pollution extension is pursued, validate its proposed behavior and pollution units independently of Core.
- Decide whether space pressure is entirely implicit and whether any external quality-of-life integration is in scope.
- Define the optional advanced military extension scope for spider-bot and power-suit additions.
- Align sustained defense power demand with the accepted core power model; reconcile the differing laser-turret estimates in this document and [Infrastructure](infrastructure.md).

Phase 5 coverage must trace the selected defense capabilities and power demands; ammunition identities, recipes, and research gates follow in Phases 6–8. The proposed space-platform objective is not an approved second victory condition.

## Candidate Extension Pack Scope

The following extension concepts are source proposals only; none is approved.

Military content for extension packs follows the core mod's design but adds depth for specific audiences:

| Extension | Military Content Added | Notes |
|---|---|---|
| **difficulty-advanced** | Extended weapon tiers (sniper, anti-materiel rifle levels at very late tiers), optional spider-bot vehicle and power-suit equipment additions, smarter enemy AI, fortified base types. Requires Combat Mechanics Overhaul dependency. | Candidate additions only; scope and dependency need validation. |
| **difficulty-extreme** | Pollution multipliers ×3–5×, aggressive biter scaling, pollution-adapted elite variants with armor/acid resistance. Resource scarcity on combat-critical materials (lead, tungsten). | Hardcore players who want military to be the bottleneck. |
| **endgame-simulation-hard** | More complex debug requirements for information-formed entities in the simulation network; harder fleet management. Combat-adjacent but tied to endgame complexity. | Players who want the endgame to challenge them militarily too. |

## Current Status and Next Work

This is not a complete military specification. The Core roster, vanilla enemy/pollution boundary, capability-based ammunition, and sustained-defense-power principles are selected. Detailed ammunition, weapon, power-load, and extension tables remain candidates, not final catalog entries, build recipes, or balance values.

Next, trace military product families during Phase 5 coverage and defer final product identities, recipes, and research to Phases 6–8 of [the plan](plan.md). Resolve the ammo-tier and recipe-count conflict before product enumeration.