# ADR-0059: Exclude Blackout-Meltdown Gameplay from Phase 2 Core Fission

*Status: Accepted*
*Decision date: 2026-11-15 (pragmatic default under delegated Phase 2 direction)*
*Last updated: 2026-11-15*

Related documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), [Plan](../plan.md), and [Documentation Map](../documentation-map.md).

## Context

Phase 2 fission uses a heat-to-steam power path. Draft proposals additionally describe continuously powered emergency cooling, backup batteries or an expendable Dead-Battery Capacitor / Fuse Link, blackout-triggered temperature escalation, and possible meltdown. No prior ADR selected that failure model or required the safety device.

The user asked for autonomous Phase 2 decisions to favor semi-realistic, non-annoying defaults and directed a pragmatic choice when unavailable. The normal heat-transfer path is necessary for generation; a separate blackout failure loop is not necessary to preserve that path.

## Decision

Phase 2 Core fission requires the normal heat-transfer path to produce steam for the selected turbine route. It does not require separately powered emergency cooling, a dedicated backup-power loop, a consumable Dead-Battery Capacitor / Fuse Link, or blackout-triggered meltdown gameplay.

This boundary does not select the exact coolant loop, heat-exchanger design, operating controls, instrumentation, shutdown behavior, reactor tiers, construction details, or research gates. Those remain open.

## Options Considered

1. **Managed emergency-safety loop.** Require active backup cooling and shutdown measures, with a visible escalation and recoverable meltdown threat after power loss; not selected for Core.
2. **Normal heat-transfer operation without blackout-meltdown gameplay.** Retain the thermal conversion needed for power generation without a separate emergency-power failure loop or dedicated safety item; selected.

## Rationale

The selected boundary preserves the physical thermal-conversion path while avoiding a hidden or punitive failure chain. It is the pragmatic, low-annoyance default consistent with the user's delegated direction.

## Consequences

- Core fission needs a heat-transfer design, but not a blackout-induced meltdown mechanic or dedicated expendable safety device.
- General-purpose battery storage may support ordinary grid continuity, but no storage capacity or battery device is required as a reactor-safety system.
- Previously described reactor tiers, controls, monitoring, and safety features remain proposals unless separately selected.
- Exact normal operating, coolant, construction, and research details remain open.

## Affected Design and Related Decisions

- Design documents: [Power System](../power-system.md), [Infrastructure](../infrastructure.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0019](ADR-0019-phase-1-and-2-power-progression.md), [ADR-0043](ADR-0043-phase-2-fission-fuel-rod-fabrication.md), and [ADR-0058](ADR-0058-keep-custom-power-diagnostics-and-stabilization-out-of-core.md).
- Supersedes / superseded by: Clarifies the Phase 2 Core fission-safety scope; no earlier ADR selected the blackout-meltdown model.
