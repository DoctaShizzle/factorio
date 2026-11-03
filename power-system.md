# Power System - Design Proposal

*For: Factorio Overhaul Mod*  
*Status: Concept / requirements phase*

## Design Intent

Power should be a factory-design decision, not a global infinite bus. Local generation, industrial clustering, conductor choice, and transmission infrastructure should matter, while diagnostics make losses and limits understandable.

Power and floor space are secondary optimization axes in the overall design. They should create meaningful tradeoffs without becoming opaque punishment or maintenance busywork.

## Candidate Grid Model

### Transmission Tiers

- **Low-voltage distribution:** local wiring for small loads and early factories, with limited reach and capacity.
- **High-voltage transmission:** long-distance lines for large or remote loads, with conversion stations between local and transmission networks.
- **Transformation stations:** step voltage up for transmission and down for industrial consumers; placement and capacity are factory layout choices.

Exact voltages, distances, and conversion ratios remain undecided. The model should teach a useful voltage/current/resistance analogy without requiring players to perform electrical engineering calculations by hand.

### Conductor Materials

Candidate conductor materials can trade cost, capacity, transmission loss, and physical placement:

| Conductor | Candidate role |
| --- | --- |
| Tin | Cheap early/local wiring with lower capacity |
| Copper | Reliable general-purpose conductor |
| Aluminum | Lightweight, long-distance transmission option |
| Gold | High-performance specialist conductor for late-game precision or compact high-load networks |

These roles are initial design hypotheses; the final list should follow the approved material roster and avoid making rare metals mandatory for ordinary factory power.

### Transmission Losses and Factory Layout

Transmission losses should depend on line length, conductor properties, voltage tier, and load. This should make remote power generation and industrial clusters situationally valuable, not universally superior. Generators may be placed near large process loads to avoid long-haul loss, while high-voltage lines can connect separated facilities when their infrastructure cost is worthwhile.

## Diagnostics and Onboarding

Power diagnostics are a core feature, not a later polish task. A pole, transformer, or line overlay should make it easy to inspect:

- Voltage tier and current load
- Connected capacity and remaining headroom
- Estimated loss per segment and cumulative transmission loss
- The limiting segment or reason a consumer is underpowered

The interface should use clear units and concise messages. Early onboarding should explain local versus long-distance distribution, the voltage analogy, why transformers exist, and common failure causes. Numerical examples are illustrative only until the power model is tuned.

## Connections to Other Systems

- Steel and alloy choices provide conductor options.
- Electrolysis, electric furnaces, cleanrooms, and semiconductor fabrication create distinct load profiles.
- High-demand process clusters can motivate local generation or dedicated transmission.
- The endgame network needs reliable power and may justify specialized low-loss distribution as an optional capability.

## Design Guardrails

- Explain every limit and loss in the UI; avoid hidden grid failures.
- Make early power simple to establish and diagnose.
- Let infrastructure and factory layout solve power problems; do not require PLC programming for basic grid stability.
- Use PLCs for optional advanced control, load shedding, and power-plant coordination.
- Treat exact voltage tiers, loss formulas, conductor stats, and machine behavior as open design decisions until tested together.

## Reference Inspiration

GTNH demonstrates that voltage tiers and current capacity can create engineering choices; its opaque failure diagnosis is the caution. The overhaul should preserve the meaningful constraints and make grid state legible at a glance.
