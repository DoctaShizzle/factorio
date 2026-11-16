# ADR-0072: Retain Vanilla Enemies and Pollution Behavior in Core

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Military System](../military-system.md), [Map and World Generation](../map-world-generation.md), and [Mod Overview](../mod-overview.md).

## Context

The military draft conflicted between vanilla enemies and pollution-adapted armored variants or pollution-specific attack profiles. [ADR-0013](ADR-0013-military-pressure-model.md) recorded these as proposals rather than an approved model.

## Decision

Use vanilla enemy types and vanilla pollution behavior in Core. Do not require new enemy variants or custom pollution-type-dependent attack behavior. Different industrial emissions can still affect ordinary vanilla pollution pressure.

New enemies and/or additional pollution-dependent behavior may be considered in optional extensions, but no such extension or mechanic is selected. This decision does not remove the separately accepted map-edge patrol concept in [ADR-0004](ADR-0004-map-edge-pressure.md); its world-generation implementation remains to be validated.

## Options Considered

1. **Vanilla enemies and native pollution behavior.** Selected for Core.
2. **Vanilla enemy types with custom pollution-dependent attacks.** Not selected for Core.
3. **New pollution-adapted enemy variants.** Not selected for Core; possible extension work remains open.

## Rationale

The user chose a familiar Core pressure baseline while preserving optional room for a different enemy or pollution model.

## Consequences

- Positive: The conflicting enemy and pollution assumptions no longer determine Core scope.
- Trade-offs: Pollution-type-specific gameplay and new enemy variations are not Core capabilities.
- Follow-up work: align military and map descriptions, then validate emissions and ordinary pressure through playtesting.

## Affected Design and Related Decisions

- Design documents: [Military System](../military-system.md), [Map and World Generation](../map-world-generation.md), and [Mod Overview](../mod-overview.md).
- Related ADRs: [ADR-0004](ADR-0004-map-edge-pressure.md), [ADR-0012](ADR-0012-bound-core-military-scope.md), and [ADR-0013](ADR-0013-military-pressure-model.md).
- Supersedes / superseded by: Resolves the Core enemy and pollution-model conflict preserved in ADR-0013; the separately accepted map-edge direction remains in force.
