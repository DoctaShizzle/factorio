# Map and World Generation

*For: Project Prometheus*
*Status: Current design with open validation items*
*Owner: World generation*
*Last updated: 2026-11-13*

Related documents: [Mod Overview](mod-overview.md), [Minerals and Refining](minerals-and-refining.md), and [Military System](military-system.md). Decision history is recorded in [ADR-0001](adrs/ADR-0001-geological-biome-layout.md), [ADR-0002](adrs/ADR-0002-geology-led-exploration.md), [ADR-0003](adrs/ADR-0003-single-oil-type.md), [ADR-0004](adrs/ADR-0004-map-edge-pressure.md), [ADR-0005](adrs/ADR-0005-map-scale-and-discovery-distances.md), [ADR-0021](adrs/ADR-0021-phase-2-material-and-solar-boundaries.md), [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md) for the selected semiconductor feed families, [ADR-0030](adrs/ADR-0030-early-access-to-semiconductor-feed-deposits.md) for zircon/columbite-tantalite access timing, [ADR-0031](adrs/ADR-0031-starting-region-access-to-cpu-feed-families.md) for starting-region access to quartz and copper, [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md) for the required battery feeds, and [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md) for their selected sources and starting-region access.

## Summary

World generation makes geology a driver of resource availability, exploration, logistics, and military exposure. Broad geological biomes contain clustered deposits; players learn where resources are likely to occur and travel to obtain materials needed for later capabilities.

## Purpose and Boundaries

This document owns terrain, biome/resource placement, geological adjacency, prospecting principles, and the relationship between map geography and exploration. It does not own mineral recovery and refining routes, military attack mechanics, or final deposit-density and spacing values; those belong to [Minerals and Refining](minerals-and-refining.md), [Military System](military-system.md), or later tuning.

The current design has no trade system or economy: materials are extracted and refined by the player. This supports the project's industrial journey from raw resources to planetary-scale construction, echoing the Prometheus narrative of bringing fire against divine odds.

## Current Design

### Geological Biomes

Use broad geological regions with resource clusters rather than fully random placement or a separate biome for every resource. Each of four core biomes has at most three characteristic resource groups. Coastal/shelf areas are a hybrid overlay, not a fifth core biome.

| Biome | Characteristic resources | Intended industrial role |
|---|---|---|
| Sedimentary basin | Oil, salt/limestone, phosphorite | Chemical feedstocks, brine processing, and fertilizer precursors |
| Shield region (ancient igneous) | Iron formations, copper-nickel sulfides | Core metal supply for smelting and metallurgy |
| Mountain range (uplifted) | Polymineral ore bodies, high-grade veins, coal/seams | Richer but more difficult extraction; potential machine-tiering demand |
| Volcanic zone | Sulfur, precious metals (placer/gold), rare mineral traces | Advanced chemistry, catalysts, and early Phase 2 materials |
| Coastal/shelf (hybrid overlay) | Saltwater brines and evaporites, added to the adjacent biome's resources | Chemical processing and a transition between coastal and inland geology |

Coastal/shelf geology occurs where water meets land and overlays the adjacent biome's resource profile. It is intended to connect to every core biome through coastlines, rewarding coastal exploration without requiring a separate map region. No biome is intended to provide everything: for example, sedimentary basins provide chemical feedstocks rather than core metals, while mountain ranges have polymineral resources but lack salt/limestone.

### Geological Continuity

Biome adjacency is structured rather than arbitrary:

1. Sedimentary basins border shield regions.
2. Shield regions connect to mountain uplift.
3. Mountain ranges border volcanic zones.
4. Coastal areas can meet each of the core biome types.

The adjacency pattern should let players form useful expectations from visible geology without revealing exact deposit coordinates. The source design gives several distance estimates, but their differences are not resolved; see [ADR-0001](adrs/ADR-0001-geological-biome-layout.md) and [ADR-0005](adrs/ADR-0005-map-scale-and-discovery-distances.md).

### Resource Clustering and Progression

Deposits appear in clusters, with size and spacing intended to support dedicated mining while allowing exhaustion to become a pressure. Clusters must not make exhaustion the only reason to explore. These examples are design targets, not tuned generation values:

| Cluster scale | Source example | Intended player experience |
|---|---|---|
| Local | Iron within about 500 m of the starting area | Supports Phase 1 startup |
| Reachable | Oil and salt/brine within about 2 km | Supports the Phase 1/2 transition; salt/brine is available by early Phase 2 without heavy exploration |
| Regional | Polymineral mountain range about 3–8 km away | Justifies dedicated rail or freight logistics |
| Rare | Larger niobium/tantalum deposits at 15 km or farther | Rewards advanced prospecting and logistics; limited zircon/columbite-tantalite access is available earlier under ADR-0030 |

Resource introduction is progressive:

| Phase | Current intent |
|---|---|
| Phase 1 (conventional) | Surface and shallow deposits provide starter resources. The source design names iron, coal, copper, stone, and oil as early needs. Under ADR-0031, the starting region also provides quartz and at least one copper-bearing feed for the later CPU chain. Other starting-area guarantees remain open apart from the Phase 2 LFP feeds specified under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md); aluminum is not a Phase 1 material. |
| Phase 2 (domain science) | Early Phase 2 provides reachable salt/brine for simple extraction and evaporation; chlor-alkali remains a Phase 2 process. Aluminum enters no earlier than Phase 2. Limited zircon and columbite-tantalite supply is accessible by early/mid Phase 2 under ADR-0030; richer rare-earth and industrial-mineral deposits, including niobium/tantalum, may remain deeper and regional. Under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md), apatite-rich phosphorite supplies phosphate and lithium-bearing brine supplies the starting-region lithium source; spodumene remains an alternative and may be regional. The required feeds must be reachable by the LFP storage unlock under [ADR-0039](adrs/ADR-0039-phase-2-lfp-battery-storage.md); exact quantities, placement, and recovery routes remain open. Exploration and logistics expand the available resource base. |
| Phase 3 (simulation-gated) | Simulation models can predict likely locations of high-value deposits from regional geological data; players still prospect and travel to confirm and exploit them. |

The standard late-Phase-2 CPU path depends on quartz, zircon, columbite-tantalite, and copper-bearing deposits under [ADR-0029](adrs/ADR-0029-phase-2-semiconductor-mineral-feed-families.md). Quartz and at least one copper-bearing feed must be accessible in the starting region under [ADR-0031](adrs/ADR-0031-starting-region-access-to-cpu-feed-families.md); limited zircon and columbite-tantalite supplies must be reachable by early/mid Phase 2 under [ADR-0030](adrs/ADR-0030-early-access-to-semiconductor-feed-deposits.md), while richer deposits may remain regional or rare. Exact quantities, copper source, biome placement, distances, cluster sizes, and prospecting requirements remain open.

The design intent is that geological need, rather than exhaustion alone, motivates exploration: the starting region provides a foundation, while later capabilities require resources associated with other regions. Deposit exhaustion remains a possible source of pressure, not a substitute for this progression.

### Prospecting

Prospecting should teach principles, not reveal exact answers. Handbook/Informatron content may explain relationships such as sedimentary formations suggesting hydrocarbon deposits, while ground colors, mineral outcrops, other terrain features, and experience help players discover specific locations. Simulation-assisted predictions are a late-game aid, not a replacement for prospecting.

### Oil and Water

Oil deposits occur in sedimentary basins within the playable area rather than being restricted to map edges. Water sources generate independently according to terrain and biome; oil and water need not be co-located because logistics can connect them. Deep-water wells or geothermal hotspots may exist as rare features but must not be required for essential processes.

The core design uses one oil type. A proposal for distinct light and heavy crude types was rejected; the source rationale assigns crude-processing capability differences to machine tiers instead. See [ADR-0003](adrs/ADR-0003-single-oil-type.md).

### Expansion and Military Pressure

Pollution from industry creates a pressure gradient: nearby factories face more military pressure, while cleaner or more distant territory can offer lower pressure at increased logistics cost. Clean production, better equipment, and expansion are intended to help players manage pressure without making either process or location uniformly best. The committed map-edge concept is a sparse patrol layer at roughly 10% of base density: enemies do not stop at the edge, but pressure is lowest there. This is a world-generation boundary behavior; attack composition and combat mechanics remain with [Military System](military-system.md). See [ADR-0004](adrs/ADR-0004-map-edge-pressure.md).

### Scale and Geographic Targets

The selected default map scale is x5, with x4 and x6 selectable at world creation. Earlier and later sections of the source contain competing distances for starting resources, Phase 2 materials, rare deposits, and map edges. The values in the cluster and progression tables above preserve useful examples; the canonical target ranges and feasibility still require review. See [ADR-0005](adrs/ADR-0005-map-scale-and-discovery-distances.md).

## Requirements and Dependencies

- Each deposit type in the mineral catalog should have a biome or terrain association.
- The mineral and product catalogs must align with resource availability and the intended exploration progression.
- Resource placement must reward geological observation without making exact locations automatic.
- Biome availability, resource scarcity, pollution, and logistics should create meaningful choices without making required progression impossible.
- Exact densities, deposit spacing, and technical implementation values remain tuning work.

## Open Decisions

| Question | Status | Impact / dependency |
|---|---|---|
| Which distance values are authoritative for Phase 1, Phase 2, rare deposits, biome adjacency, and the map edge? | Open | Map scale, travel burden, and logistics; reconcile source values listed in ADR-0005. |
| Which additional resources beyond quartz and at least one copper-bearing feed must be guaranteed near the starting area? | Open | Starting viability and mineral scope; CPU-feed access is set by [ADR-0031](adrs/ADR-0031-starting-region-access-to-cpu-feed-families.md). |
| Which lithium and phosphate recovery routes, grades, quantities, and exact deposit placements should support Phase 2 LFP storage? | Open | Brine and apatite-rich phosphorite are starting-region sources, with spodumene as a possible regional alternative under [ADR-0040](adrs/ADR-0040-phase-2-lfp-feed-sources-and-access.md); processing routes and detailed deposit placement remain open. |
| How should cluster depletion interact with the principle that geology, not exhaustion alone, drives exploration? | Open | Resource pressure and progression pacing. |
| Are the committed biome and adjacency rules feasible and desirable in the intended map-generation implementation? | To validate | Technical implementation and player navigation. |

## References

- [Minerals and Refining](minerals-and-refining.md) — deposit feeds, recovery, refining, and pure materials.
- [Military System](military-system.md) — pollution pressure and enemy behavior.
- [Mod Overview](mod-overview.md) — design pillars, scope, and cross-domain requirements.
- Decision history: [ADR index](adrs/README.md).
