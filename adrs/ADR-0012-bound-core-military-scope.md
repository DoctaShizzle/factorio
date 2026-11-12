# ADR-0012: Bound Core Military Scope to Industrial Defense

*Status: Proposed*
*Decision date: Unknown*
*Last updated: 2026-11-12*

Related documents: [Military System](../military-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md).

## Context

The Military System draft records Bob's Weapons Pack as its primary reference, with vanilla enemies and industrial supply chains as the intended source of depth. It also contains an unverified proposal to extend vanilla turrets with tiered ammunition rather than add new core turret families. The source labels these choices resolved, but gives no decision date or independent approval evidence. On 2026-11-12, the user clarified that a vanilla-only turret roster was not their decision and proposed additional electrical turret families.

The source's comparative research is retained here because it informed that direction:

- **Bob's Weapons Pack:** Capability-based progression, where ammunition changes engagement capability rather than only damage. The source describes kinetic, incendiary, explosive, armor-piercing, and penetration rounds, each tied to chemical or metallurgical chains such as lead/copper/steel, nitric acid and glycerol, or tungsten. It extends vanilla machine turrets, adds handgun, shotgun, and rocket variants with industrial recipes, and retains vanilla biter, spitter, and worm units whose pressure scales with pollution.
- **GregTech New Horizons:** Deep industrial integration through machined weapon parts, alloy grades, armor plates, and hundreds of ammunition variants. The source contrasts this with a custom handgun-to-heavy-weapon system and Minecraft mob combat through exploration, rather than a Factorio-style biter ecology or pollution model.
- **Angel's Addons:** Minimal military content; its focus is additional mining and refining depth. The source notes vanilla enemies, amplified pollution spread, and no new weapons or ammo chains.
- **Pyanodon's Grand Suite:** A modular, selective approach, with flamethrower/laser-like categories and two or three late-game turret families; only selected ammo chains are industrialized. The source notes vanilla units plus biome-specific variants and moderately amplified but comparatively forgiving pollution pressure.
- **Bob's Military / Combat Mechanics Overhaul:** An optional harder-combat layer with later sniper and anti-materiel weapons, smarter targeting, fortified bases, specialized materials, pollution-adapted enemies, and multi-zone pressure (regular nearby waves and harder distant variants). It can add scarcity to combat-critical lead and tungsten and concepts such as electromagnetic-acceleration railgun projectiles; the source notes its external combat-overhaul dependency.
- **The Riftbreaker:** Secondary mechanical inspiration for six damage elements (Fire, Ice, Plasma, Radiation, Corrosive, and Cryo), enemy weaknesses, and ammo mapped to elements. Its source systems also include melee, energy, liquid, and projectile weapons; configurable weapon mods trade fire rate against ammo use or range against capacity; enemy composition varies with biome/element exposure; and perimeter drones and energy shields add defense options. It has no pollution mechanic; defense depends on positioning, turrets, and drones. The user cites Riftbreaker's railgun turret and an Asgard-like beam concept as high-level inspiration for a long-range electrical defense role; neither is an implementation specification. Its mech-based third-person combat model is explicitly not the proposed Project Prometheus model.

## Decision

**Revised proposal; not accepted:** Keep a bounded industrial-defense scope and retain vanilla enemies as a candidate baseline, but do not restrict the turret roster to vanilla families. The user proposes expanding electrical defense beyond the existing laser turret with a plasma turret and a railgun turret. The plasma candidate fires an artillery-like plasma orb with a relatively large splash radius. The railgun candidate has a very-long-range beam/shot that damages enemies along its path with a small-to-medium splash around the beam, potentially reaching maximum visible or targetable range. Both should have substantial power draw as a balancing cost. The roster should remain bounded across progression layers: enrich power-based options without opening an unrestricted set of new turret families. The exact layer boundaries and number of additions are not decided.

The earlier blanket proposal to add no new core turret families is preserved as historical source material, not as a user-approved decision; this revision supersedes that restriction as a statement of user intent. Exact tier and phase placement, core-versus-extension scope, attack behavior, ammunition or consumable model, power profile, and balance values remain open. Other source proposals—including enemy scope and combat automation—remain unverified and are not changed by this revision.

## Options Considered

1. **Keep turret families strictly vanilla.** The source's earlier proposal relies on tiered ammunition for depth; this was not a user-approved constraint.
2. **Add a bounded, layer-based electrical turret progression.** Retain the existing laser turret and consider plasma and railgun families alongside industrially meaningful ammunition. This is the user's current direction; acceptance and exact scope remain open.
3. **Add broad custom military content.** Custom enemies, many turret families, or a replacement combat model could increase tactical variety but would expand art, balance, implementation, and scope requirements.
4. **Keep military content minimal.** Retain vanilla combat with little or no new supply-chain depth, as in the source's Angel's Addons comparison.

## Rationale

The source argues that new enemy types would expand art, animation, attack, death, loot, and balance work on top of a planned 800-1200 items and about 4000 recipes; these are source estimates, not normalized counts. It maps biters to ground melee, spitters to ranged acid attacks, and worms to burrowing ambushes, and claims Bob's model demonstrates that familiar enemies can support industrial depth. This remains relevant to bounding enemy scope, but does not establish a vanilla-only turret requirement. A small, layer-bounded set of role-distinct electrical turret candidates would align defense with the modpack's electrical orientation, while substantial power demand would make them a grid-planning tradeoff. Their implementation cost and balance still need evaluation. GTNH informs material integration, while Riftbreaker informs selected mechanics rather than the overall combat model.

## Consequences

- Positive if accepted: Military progression remains connected to the industrial product tree and adds distinct electrical-defense roles without requiring a new enemy roster.
- Positive if accepted: High power draw makes plasma and railgun defenses meaningful consumers in the electrical system.
- Trade-offs: New turret families add implementation and balance work; excessive draw or area effects could make defense punitive.
- Follow-up: Reconcile the ammo-tier and recipe-count statements in [Military System](../military-system.md), align power assumptions with [ADR-0015](ADR-0015-sustained-power-for-defense.md), and verify every retained proposal against product and infrastructure coverage.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md).
- Related ADRs: [ADR-0013](ADR-0013-military-pressure-model.md), [ADR-0014](ADR-0014-capability-based-ammunition.md), [ADR-0015](ADR-0015-sustained-power-for-defense.md), [ADR-0016](ADR-0016-late-game-defense-drones.md).
- Supersedes / superseded by: The blanket no-new-core-turret-family clause is superseded as a statement of user intent; this ADR remains Proposed overall.

## Open Questions

- [ ] Which proposed electrical turret families belong in core, and which—if any—belong in extensions?
- [ ] How many additions fit the intended progression layers without expanding the roster beyond its bounded scope?
- [ ] What are their progression tiers, phases, ranges, splash behavior, and ammunition or consumable requirements?
- [ ] Should their balancing power cost be sustained draw, firing bursts, stored energy per shot, or a combination? What values are appropriate?
- [ ] Is the candidate vanilla enemy roster still the intended baseline? The user clarification here addressed turret scope only.

## Revisions

- 2026-11-12 — Clarified that the user had not decided on a vanilla-only turret roster; added plasma and railgun electrical-turret proposals with high power draw, and marked tiering, scope, and balance details open.
- 2026-11-12 — Recorded the user's preference for bounded, layer-based turret additions with greater emphasis on power-based options; the roster remains proposed.
