# ADR-0014: Use Capability-Based Ammunition Progression

*Status: Accepted*
*Decision date: 2026-11-12*
*Last updated: 2026-11-12*

Related documents: [Military System](../military-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md).

## Context

The Military System draft proposes weapon and ammo progression through distinct combat capabilities, with ammunition tied to chemistry and metallurgy rather than simple damage-number upgrades. It describes kinetic, incendiary, high-explosive, armor-piercing, and penetration-rocket ammunition, and associates them with industrial supply chains.

The source also proposes an enemy weakness/resistance matrix to make ammo selection depend on enemy composition. It attributes this idea to The Riftbreaker; whether that tactical mechanic fits the intended Factorio defense model remains open.

The source contains unresolved count differences: it calls the chain "5 tiers" across about 12 recipes, lists five ammo types as T1, T2a, T2b, T3, and T4 (four numbered tiers), and elsewhere describes about 12 recipes "across the four tiers." A separate weapon table includes T3a and T3b variants. These statements are preserved as conflicting proposals; this ADR does not choose a count.

The source also proposes that the T4 penetration rocket use enriched uranium and tungsten for a kinetic penetrator payload, not as a nuclear explosive. It would connect to the nuclear fuel cycle and a semiconductor guidance module. This scope and rationale remain unverified.

On 2026-11-12, the user accepted capability-based ammunition progression. That acceptance does not resolve the conflicting tier and recipe counts, approve every listed ammo type or supply chain, or adopt the enemy weakness/resistance matrix.

## Decision

**Accepted principle:** Make ammo progression a capability choice rather than a sequence of larger damage values. The listed shifts—kinetic to incendiary, incendiary to high-explosive, and high-explosive to armor-piercing—remain candidate examples; the endgame penetration rocket and its nuclear-grade materials are also unapproved specifics. An enemy weakness/resistance matrix is a separate, unapproved candidate mechanic. Ammo types, supply trees, and tier/recipe counts remain provisional.

## Options Considered

1. **Capability-based ammo.** Distinct ammunition types address different target or engagement profiles and require different industrial supply chains.
2. **Number-based ammo upgrades.** Successive ammo types primarily increase damage, with fewer tactical or production tradeoffs.
3. **Minimal military supply chains.** Retain mostly vanilla ammo and avoid making combat a major cross-domain production demand.

The source explicitly distinguishes its nuclear-material candidate from a nuclear explosive; no explosive-payload alternative was recorded.

## Rationale

The accepted principle connects defense to the wider chemistry and metallurgy progression and gives ammunition a capability role. Bob's Weapons Pack remains a scope reference; the source's statement that mid-game ammo should not require exotic materials is retained as a proposal, not a separately accepted constraint.

## Consequences

- Positive: Military products can exercise existing material and process capabilities and create deliberate production choices.
- Trade-offs: More ammo types create balancing and logistics demands; the source's tier and recipe totals cannot yet be used as approved targets.
- Follow-up: Reconcile the five-type/four-tier wording, T3a/T3b weapon variants, and approximate recipe totals during product coverage and catalog work. Keep each candidate's consumer and supply path explicit.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Intermediate Products](../intermediate-products.md), [Chemical Products and Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md).
- Related ADRs: [ADR-0012](ADR-0012-bound-core-military-scope.md).
- Supersedes / superseded by: None.

## Revisions

- 2026-11-12 — User accepted capability-based ammunition progression; exact ammo types, tier and recipe counts, supply chains, and enemy-matchup mechanics remain open.
