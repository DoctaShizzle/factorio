# ADR-0044: Extend Shared Phase 2 Zircon Supply to Fission Cladding

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), and [Plan](../plan.md).

## Context

[ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects zircon as the hafnium-bearing feed family for the standard late-Phase-2 CPU path. [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) requires limited early/mid-Phase-2 zircon access for that CPU use. [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) makes cladding and fuel-rod assembly prerequisites for both Phase 2 fission options. The user selected zirconium alloy as the cladding material family and chose to share early zircon supply with the CPU path rather than add a separate fission-specific feed.

## Decision

1. Select zirconium-alloy cladding as the material family for baseline Phase 2 fission fuel rods. The exact alloy grade and composition remain open.
2. Extend the early/mid-Phase-2 zircon access requirement to cover both the CPU hafnium chain and fission-cladding demand. This is a shared feed-family/access requirement; it does not require the same physical deposit to supply both uses.
3. Keep the existing zircon feed family as the common source. The candidate Zr/Hf separation path may supply zirconium for cladding and hafnium as a coproduct, but its process route, equipment configuration, yields, and product grades are not selected here.
4. Validate that the accessible Phase 2 zircon supply can support both uses when production quantities and material balances are established. Exact quantities, locations, grades, yields, alloying inputs, and research gates remain open; richer deposits may remain regional or rare under ADR-0030.

## Options Considered

1. **Share the early/mid-Phase-2 zircon access requirement across CPU hafnium and fission cladding.** Selected; it uses the existing feed family and keeps both uses on one resource-access trunk, with total supply sufficiency to be validated during balancing.
2. **Require a separate fission-specific zircon source or access tier.** Not selected; it would add a distinct world-generation or resource-progression requirement without a demonstrated need for a separate feed family.
3. **Defer the expanded zircon access requirement until material balances are known.** Not selected; it would leave the new Phase 2 fission prerequisite without a stated resource-access boundary.

## Rationale

Using zirconium alloy for fuel-rod cladding reuses a feed family already required before the late-Phase-2 CPU gate. Extending its early/mid-Phase-2 access requirement makes the new fission dependency explicit without inventing a second ore family or prematurely fixing quantities and deposit placement.

## Consequences

- Positive: the Phase 2 fission cladding route has an explicit material family and shares zircon access with the CPU hafnium chain.
- Trade-offs: CPU hafnium and fission cladding now compete for zircon-bearing supply; the existing CPU-oriented access guarantee must be checked against their combined demand.
- Follow-up work: validate zircon recovery and Zr/Hf separation, alloying and tube fabrication, total accessible supply, and timing against the CPU and fission unlocks.

## Affected Design and Related Decisions

- Design documents: [Map and World Generation](../map-world-generation.md), [Minerals and Refining](../minerals-and-refining.md), [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Intermediate Products](../intermediate-products.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0029](ADR-0029-phase-2-semiconductor-mineral-feed-families.md) selects zircon as the hafnium-bearing CPU feed; [ADR-0030](ADR-0030-early-access-to-semiconductor-feed-deposits.md) sets early/mid-Phase-2 zircon and columbite-tantalite access for the CPU chain; [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md) requires Phase 2 cladding and fuel-rod assembly.
- Supersedes / superseded by: No prior decision is superseded. Extends ADR-0030's zircon-access scope to include the Phase 2 fission-cladding demand and resolves the cladding-family follow-up in ADR-0043.
