# Architecture Decision Records

ADRs preserve significant decision history separately from current-state design documents. Current design lives in the owning domain document listed in [documentation-map.md](../documentation-map.md).

## Naming and status

- Name files `ADR-NNNN-short-title.md`, assigning the next unused sequential number.
- Never reuse an ADR number. Keep superseded records and link them to their replacements.
- Use the structure in [the ADR template](../templates/adr.md).
- Preserve known historical dates; state `Unknown` if the date cannot be established.

## Index

| ADR | Decision | Status |
|---|---|---|
| [ADR-0001](ADR-0001-geological-biome-layout.md) | Geological Biome Layout | Accepted |
| [ADR-0002](ADR-0002-geology-led-exploration.md) | Geology-Led Exploration | Accepted |
| [ADR-0003](ADR-0003-single-oil-type.md) | Use a Single Oil Type | Accepted; light/heavy variation rejected |
| [ADR-0004](ADR-0004-map-edge-pressure.md) | Sparse Military Patrols at the Map Edge | Accepted |
| [ADR-0005](ADR-0005-map-scale-and-discovery-distances.md) | Default Map Scale and Discovery Distances | Accepted with distance validation outstanding |
| [ADR-0006](ADR-0006-capability-based-intermediate-scope.md) | Scope Intermediate Products by Capability | Accepted |
| [ADR-0007](ADR-0007-rhenium-reaction-dynamics-bridge.md) | Rhenium Catalyst as a Reaction Dynamics Bridge | Accepted; six-bridge count and facility mapping selected; route validation outstanding |
| [ADR-0008](ADR-0008-factorio-product-family-coverage.md) | Map Factorio Product Families Before Cataloging | Accepted; item-level coverage and version-specific inventory deferred |
| [ADR-0009](ADR-0009-endgame-assembly-proposals.md) | Preserve Former Phase A2 Endgame Assembly Proposals | Accepted as a historical record; recipe values remain unapproved |
| [ADR-0010](ADR-0010-core-power-distribution-scope.md) | Retain the Vanilla Grid with Tiered Power Poles | Accepted; exact tiers and pole properties open |
| [ADR-0011](ADR-0011-hawking-radiation-endgame-generator.md) | Add a Hawking Radiation Engine as a Phase 4 Power Option | Accepted option; at least one alternative Phase 3/4 route required |
| [ADR-0012](ADR-0012-bound-core-military-scope.md) | Bound Core Military Scope to Industrial Defense | Proposed; bounded, layer-based electrical direction; roster and scope open |
| [ADR-0013](ADR-0013-military-pressure-model.md) | Use Pollution and Space as Complementary Military Pressures | Proposed; model and thresholds require validation |
| [ADR-0014](ADR-0014-capability-based-ammunition.md) | Use Capability-Based Ammunition Progression | Accepted principle; types, tiers, and recipe counts open |
| [ADR-0015](ADR-0015-sustained-power-for-defense.md) | Give Defense Infrastructure a Sustained Power Load | Accepted principle; profiles and values require validation |
| [ADR-0016](ADR-0016-late-game-defense-drones.md) | Reject Late-Game Military Drones | Rejected; fixed defense, with optional spider-bot/power-suit extension scope open |
| [ADR-0017](ADR-0017-phase-2-core-and-bridge-prerequisites.md) | Set Phase 2 Core and Bridge Prerequisites | Accepted |
| [ADR-0018](ADR-0018-phase-3-and-4-power-route-roster-and-conversion.md) | Select Phase 3/4 Power Routes and Non-Steam Conversion | Accepted; implementation details and progression gates open |
| [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md) | Set Phase 1/2 Power Progression | Accepted; exact fuel processing, storage progression, and balance remain open |
| [ADR-0020](ADR-0020-seven-distinct-domain-pack-tiers.md) | Use Seven Distinct Domain-Pack Tiers | Accepted; exact pack content and higher Core gates open |
| [ADR-0021](ADR-0021-phase-2-material-and-solar-boundaries.md) | Set Phase 2 Material and Solar Boundaries | Accepted; exact solar route and material recipes open |
| [ADR-0022](ADR-0022-phase-2-bridge-mappings-and-core-dependencies.md) | Finalize Phase 2 Bridge Mappings and Core Dependencies | Accepted; semiconductor timing partially superseded by ADR-0025 |
| [ADR-0023](ADR-0023-thorium-startup-seed-and-breeding-model.md) | Set the Thorium Startup-Seed and Breeding Model | Accepted; breeding/reprocessing balance and waste handling open |
| [ADR-0024](ADR-0024-include-chemical-process-concepts-in-core-scope.md) | Include Current Chemical-Process Concepts in Core Scope | Accepted; product and reaction validation remains open |
| [ADR-0025](ADR-0025-phase-2-cpu-supply-and-superconducting-core-compute.md) | Set Phase 2 CPU Availability and Superconducting Core Compute Progression | Accepted; manufacturing routes, stages, and upgrade gate remain open |
| [ADR-0026](ADR-0026-phase-2-contemporary-semiconductor-capability.md) | Place Contemporary Cleanroom and Advanced Chipmaking in Phase 2 | Accepted; material routes, equipment tiers, and research gates remain open |
| [ADR-0027](ADR-0027-phase-2-contemporary-chipmaking-material-stack.md) | Require a Contemporary Semiconductor Material Stack in Phase 2 | Accepted; source routes, grades, and recipes remain open |
| [ADR-0028](ADR-0028-phase-2-core-cpu-material-dependencies.md) | Require the Material Stack in the Initial Core CPU Path | Accepted; exact products, routes, grades, and gates remain open |
| [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) | Assign Phase 2 Mineral Feed Families for the Core CPU Chain | Accepted; extraction/refining routes, grades, yields, and access timing remain open |
| [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) | Require Limited Early Access to Semiconductor Feed Deposits | Accepted; quantities, placement, distances, and yields remain open |
