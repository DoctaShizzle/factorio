# Technical Architecture — Project Prometheus Modpack

*Status: Draft — packaging, dependencies, scope estimates, and performance claims are unverified proposals.*  
*Last updated: 2026-11-12*

Related documents: [Mod Overview](mod-overview.md), [Infrastructure](infrastructure.md), [Power System](power-system.md), [Logistics System](logistics-system.md), and [Product Taxonomy](product-taxonomy.md).

> The estimates and technical claims below are retained from an earlier planning draft. They are not hard limits or accepted targets unless linked to an approved ADR or current design owner. Validate implementation-facing claims against the supported Factorio version and representative benchmarks before using them to constrain scope.

## Candidate Deployment Model: Single Installable Mod + Extension Packs

One candidate is a primary installable mod that bundles required internal modules, with **optional extension packs** for additional content. Packaging and extension boundaries have not been selected.

### Candidate Core Bundle

```
project-prometheus/                        # Proposed single installable mod
├── core/                                  # Proposed shared backbone
│   ├── items, recipes, tech tree          # Shared vocabulary
│   ├── research grid                      # Three-phase progression
│   └── handbook/informatron               # Information layer, lore
├── minerals/                              # Candidate mineral deposits & refining module
├── chemistry/                             # Candidate chemical processes & intermediates module
├── machines/                              # Candidate equipment-family module
├── power/                                 # Candidate generation and compatible tiered poles
├── endgame/                              # Candidate simulation-network components
└── military/                              # Candidate pollution, ammunition, and defense module
```

**Analogy to Space Exploration:** This proposal uses an SE-like separation of internal modules for development while presenting one installable experience. The analogy does not establish that the packaging model is technically feasible or accepted.

### Candidate Extension Packs (Opt-In)

Optional installable mods that layer on top of the core pack. Players choose which to install based on preferred playstyle.

```
project-prometheus/
└── extensions/                            # Optional extension packs — player chooses what to install
    ├── difficulty-advanced/
    ├── difficulty-extreme/
    ├── chemistry-harsh-reactions/
    ├── machinery-advanced-bots/
    ├── power-nuclear-waste/
    ├── logistics-advanced-trains/
    ├── endgame-simulation-hard/
    └── worldgen-altered-geography/
```

| Extension | Role | Description | Target Player |
|---|---|---|---|
| **difficulty-advanced** | Hard mode | Harder enemy AI, advanced weapon tech trees. Requires Combat Mechanics Overhaul (external). | Players wanting military depth |
| **difficulty-extreme** | Extreme mode | Resource scarcity, aggressive biter scaling, fortified bases, pollution multipliers | Hardcore players |
| **chemistry-harsh-reactions** | Complexity layer | Tighter catalyst windows, more extreme conditions. Makes chemistry feel like real process engineering with less margin for error | Players who want the chemistry layer to challenge them |
| **machinery-advanced-bots** | Deep dive | Smarter pathfinding, multi-item batch handling, predictive scheduling for bots | Bot enthusiasts |
| **power-nuclear-waste** | System addition | Spent fuel reprocessing, containment storage, long-lived isotope decay chains | Players who care about nuclear power |
| **logistics-advanced-trains** | Deep dive | Dynamic routing algorithms, predictive scheduling, multi-modal transfer optimization | Train enthusiasts |
| **endgame-simulation-hard** | Hard mode | More information-formed entities to debug, harder network scaling, more complex fidelity requirements | Players who want the endgame to challenge them |
| **worldgen-altered-geography** | Alternative start | Different continent shapes, unusual mineral concentrations, varied early-game resource distribution | Players who want different starting conditions |

**How extensions interact:** Extensions can stack (install multiple). Some have explicit dependencies on each other or external mods. A player who wants the full experience installs all; a sandbox player installs none. There is no single "correct" combination.

### Candidate Rationale for Core Architecture

- **Cross-domain interdependency:** Every subsystem feeds the endgame simulation network. No single domain is optional.
- **Split into sub-mods for development workflow, not user choice:** A developer works on chemistry independently without touching power. This avoids Bob's dependency-conflict problem (where `bobmods-logistics` must match `bobmods-petrochem` versions) while giving users one install button.
- **Extension packs solve the "I just want to play factory" problem:** Not everyone wants military content. Extensions let you serve both audiences without splitting the core design into two separate mods.

### Scope Estimates (Unvalidated)

| Metric | Draft estimate | Notes |
|---|---|---|
| **New items** | 800–1200 total | Unvalidated estimate; catalog scope is not capped by this draft. |
| **New recipes** | ~2500–4000 | Unvalidated estimate; route counts depend on meaningful tradeoffs and the approved product tree. |
| **Fluid recipe density** | Batch similar processes | Candidate guardrail; group similar fluids where this preserves meaningful process choices. |
| **New entities (machines)** | ~50–80 machine types | Unvalidated estimate; candidate families are cataloged in [Infrastructure](infrastructure.md). |
| **Tech tree size** | 800–1500+ technologies | Unvalidated estimate; the roster and progression gates remain open. |

## Candidate Dependency Strategy

### Proposed Required Dependencies

The draft proposes no third-party mod dependencies and a self-contained core bundle; packaging and dependency compatibility have not been verified.

| Component | Source | Notes |
|---|---|---|
| **Informatron** | Included with core modpack | Shipped automatically as a core sub-mod. All players get it regardless of extension choices. |
| **Blueprint Library** | Vanilla (Factorio 1.1+) | Baked into base game — no dependency needed. |

### Proposed Optional Dependencies

These dependencies would only be required if the associated optional mechanics were adopted.

| Dependency | Required For Extension... | Notes |
|---|---|---|
| **Combat Mechanics Overhaul** | `difficulty-advanced` | Wall-blocking projectiles required for extended military content. Only installed when that extension is selected. |

### Candidate Client-Side QOL Recommendations

The following tools were suggested as optional recommendations, not approved dependencies:

| Mod | Purpose | Why Recommend It |
|---|---|---|
| **FNEI / What Is It Really Used For** | Recipe lookup across 2000+ recipes | Essential QOL with your product catalog density. |
| **Even Distribution Lite** | Smart belt insertion (early-game) | Reduces friction during first 30 minutes of a new playthrough. |
| **Bottleneck Lite** | Production bottleneck detection | Your multi-route system makes bottleneck identification non-obvious. |
| **Milestones** | Progress tracking with mod presets | Good for endgame milestone visibility. |
| **GTFO / Squeak Through** | Pull items from full inventories | Small quality-of-life that compounds over long playthroughs. |

**Candidate integration position:** [Logistics System](logistics-system.md) proposes native demand-based dispatch. The earlier rationale favored keeping dispatch coherent with the electrified-rail vision and cited LTN signal instability and large-factory crashes; those claims are unverified, and external logistics integrations remain an open decision.

## Performance Hypotheses to Validate

The following formulas, benchmarks, thresholds, and size estimates are inherited draft claims. No supporting source or benchmark is recorded here; none should be treated as a Factorio engine fact or hard design constraint until verified.

### Candidate Machine-Type Cost Hypothesis

The source draft claims Bob's mods add ~300 new items and ~250 new recipes, and that unique entity types dominate performance because each machine type requires a separate Lua state initialization. It further claims cost scales as `unique_machine_types × active_machines` and explains performance drops above 50–100 km² of buildout. The figures, formula, and causal explanation are unverified.

**Candidate implication:** The draft proposed ~50–80 machine types and an ~80-type cap, with reusable families as a mitigation. Neither the cap nor the stated per-tick cost is accepted or benchmarked; family reuse remains a qualitative design option.

### Candidate Logistics-Graph Hypothesis

The source draft describes connected belts as one "logistics network" and asserts that Factorio periodically searches it to determine item locations and destinations. This model has not been verified against the supported Factorio version.

It further hypothesizes complexity of `N × M²`, where N is machines in a network and M is tracked item types, estimating ~100 machines × 5 items as trivial and 200 machines × 30 items as **180,000 graph operations per cycle**. These figures and the complexity model are unvalidated.

**Candidate mitigations:** The earlier proposal suggested fewer than 15 tracked items per belt network, ~15–20 items per bot pool, and avoiding shared cross-domain networks with more than eight item types. Treat these thresholds as hypotheses, not limits.

### Candidate Fluid-Complexity Guardrail

The design proposal is to batch similar chemical processes and avoid creating a unique fluid for every minor variation. This aligns with the process-design guardrail in [Chemical Products and Processes](chemical-processes.md); its runtime impact remains unbenchmarked.

- The source draft claims petroleum processing creates the heaviest per-tick overhead due to continuous recipe recalculations; this claim is unverified.
- Group chemically similar fluids into shared intermediates rather than creating individual recipes for every variant.
- Example: Instead of separate recipes for "diluted acid A," "diluted acid B," and "diluted acid C" — use a generic "diluted acid" fluid that differentiates only through recipe inputs/outputs, not distinct fluid types.
- **Your product catalog design should explicitly flag which fluids are "shared intermediates" vs. "unique process-specific fluids."**

### Save-File Size Estimates (Unvalidated)

| Phase | Estimated Size | Primary Drivers |
|---|---|---|
| Early game | 5–15 MB | Baseline, small explored area |
| Mid-game (industrial expansion) | 20–80 MB | Entity growth, recipe complexity metadata |
| Late-game (simulation network buildout) | 100–400+ MB | Massive entity counts, logistics graph explosion |
| Full simulation network | 300–600+ MB | Distributed compute campuses, freight terminals, bot pools |

**Draft per-unit estimates (unvalidated):**
- Entities: ~100–500 bytes each (50,000 entities = 5–25 MB alone)
- Logistics graph: hidden cost, scales with item types × connected machines
- Explored area: 10km² compresses to ~100–500 MB in save
- Tech grid: 2–7 MB for 800–1500+ techs
- New items/recipes: +15–30 MB baseline metadata

### Candidate Mitigation Strategies

| Strategy | When to Apply | How |
|---|---|---|
| **Bound item count** | During product catalog design | Cap at 800–1200 new items; be selective, not exhaustive. |
| **Batch fluid recipes** | During chemistry process design | Group chemically similar fluids into shared intermediates. |
| **Lazy-load distant areas** | During endgame implementation | Don't keep simulation network chunks in memory when the player isn't visiting them (SE pattern). |
| **Design against graph explosion** | Throughout all phases | Partition factory zones by domain; limit tracked items per belt network to <15. |

### Unvalidated Performance Thresholds — Not Hard Limits

- **~450k entities:** The source draft calls this a hard limit at which Factorio becomes unplayable regardless of UPS; no supporting benchmark is recorded.
- **~150 MB saves:** The source draft claims stability and load times degrade beyond this size; no supporting benchmark is recorded.

## Accepted Cross-Domain Constraint

- **Core power distribution:** Retain the vanilla power system and add compatible tiered poles, as recorded in [ADR-0010](adrs/ADR-0010-core-power-distribution-scope.md). Exact pole tiers and statistics remain open. Custom voltage tiers, transmission losses, HVDC, and grid-stabilization mechanics are extension candidates, not accepted core requirements.

## Open Technical Decisions

- **Packaging and module structure:** Decide whether to ship one installable mod with internal modules, separate required core mods, or another structure.
- **Core versus extension scope:** The extension table is a proposal, not a finalized boundary. Assign content after the product and system scopes are agreed.
- **Game-version and dependency strategy:** Verify the target Factorio version, mod APIs, included libraries, and whether any third-party dependency is needed.
- **Scope estimates:** Reconcile item, recipe, entity, and technology counts against the approved catalog; do not enforce the draft figures as caps.
- **Performance constraints:** Benchmark representative production, logistics, save, and entity loads before setting thresholds.
- **Power extension scope:** If custom voltage, conductors, transformers, HVDC, or stabilization are retained, define them as optional extension content in [Power System](power-system.md); they are not part of the accepted core grid direction.
- **Logistics integrations:** Decide whether to support external dispatch mods in addition to the native dispatch proposal in [Logistics System](logistics-system.md).
