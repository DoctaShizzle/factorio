# Map & World Generation - Design Proposal

*For: Factorio Overhaul Mod (Project Prometheus)*  
*Status: **Committed** — all open items resolved, ready for mineral-catalog.md integration.*

## Summary

This document defines how the game world is generated to support this mod's geological discovery pillar, resource clustering strategy, and military pressure scaling. World generation is the foundation that drives all downstream industrial planning — it determines what resources are available, where they're found, and when/where exploration becomes necessary.

**What it covers:** Terrain generation model, mineral/resource clustering strategy, oil/water placement, map edge behavior, progressive resource discovery, biomes vs. random deposits, and how world gen connects to military pressure scaling.

**What it does not cover:** Specific ore density values or exact deposit spacing (tuning data); enemy spawn logic (covered in Military System doc).

## Design Philosophy

World generation is **not a screen.** In this mod, the map drives play before any factory is built — it creates goals, forces exploration decisions, and ensures that player's industrial journey is shaped by *where they are* on the planet, not just *what they've researched.

### Key Principles

1. **Resource clustering drives natural exploration.** Resources are not evenly distributed; finding everything you need requires planning expansion routes and choosing where to invest early infrastructure.
2. **Geographic resource clusters should be large enough to justify dedicated mining operations but small enough that exhaustion becomes a real pressure.** This creates the "expand outward" loop without map edge being unreachable dead ends.
3. **World gen supports geological discovery as a core pillar.** Players *learn* to read the world — prospecting, analyzing deposits, predicting what's nearby based on adjacent geology patterns.
4. **Military pressure and expansion interact meaningfully.** Dirty factories attract enemies; expanding into "clean" territory is a real strategy but has long-term opportunity costs (you're moving away from the good ore bodies).

## Terrain & Biome Generation

### Approach: Clusters within Broad Biomes

Rather than fully random ore placement or rigid fixed biomes, terrain generation uses **broad geological biomes** with **resource clusters within them:**

- **Broad geology types** determine what mineral categories can appear in a region (e.g., sedimentary basins → oil + salt; shield regions → iron + nickel; volcanic zones → sulfur + precious metals).
- **Within each biome, resource clusters generate as deposits** with spacing based on rarity and economic viability. Common resources = dense clusters; rare resources = sparse, distant clusters.

This avoids "you'll find everything near your base" while also avoiding "every 100m² is a different ore type" (GTNH's cognitive load problem). The player sees the biome → understands what *types* of deposits to expect → prospects for the specific ones they need.

### Locked Biome-to-Resource Mapping

The following biomes are committed for world generation. Each biome has **max 3 characteristic resources** to keep cognitive load bounded — exotic materials require discovery beyond your home biome.

| Biome | Characteristic Resources | Industrial Use |
|-------|-------------------------|---------------|
| Sedimentary basin | Oil, salt/limestone, phosphorite | Chemical feedstocks, electrolysis brine, fertilizer precursors |
| Shield region (ancient igneous) | Iron formations, copper-nickel sulfides | Core metal supply — smelting, metallurgy foundation |
| Mountain range (uplifted) | Polymineral ore bodies, high-grade veins, coal/seams | Late-game resource richness; difficult extraction; machine tiering opportunity |
| Volcanic zone | Sulfur, precious metals (placer/gold), rare mineral traces | Advanced chemistry, catalyst production, early Phase 2 bridge materials |
| Coastal/shelf ⚠ hybrid | Saltwater brines, evaporites (borders all biomes at water edges) | Chemical processing; geological continuity anchor — touches every biome type |

⚠ Coastal is a **hybrid biome**: it exists only where water meets land and overlays the adjacent biome's resource table with its own additions. This creates natural transition zones that reward players for exploring coastlines without requiring separate map regions.

### Geological Continuity Rules

The following biome adjacencies are fixed in world generation:

1. **Sedimentary ↔ Shield:** Always border each other. If you find oil, iron formations are within 3–5km.
2. **Shield ↔ Mountain:** Always connected by mountain uplift at shield edges.
3. **Mountain ↔ Volcanic:** Always border. Polymineral mountains always have volcanic zones nearby for catalyst access.
4. **Coastal ↔ All others:** Water creates natural bridges between biomes — coastlines are the primary exploration corridors.

These rules create a **discoverable adjacency graph** that players internalize over time: *"If I see sedimentary rock, there should be oil within 2km, and if I follow that deposit chain outward, iron is probably another 3km beyond it."* The patterns feel earned through exploration rather than handed to the player.

### Map Scale Recommendation

Given the 300+ hour ambition and Bob's/Angel-level complexity:

- **Default map size:** At least vanilla's "very large" setting (x4 default), ideally x5–x6.
- **Minimum exploration needed before base exhaustion:** Players should be able to establish a sustainable industrial base within ~2km of their starting location, but need to reach 5–10km for Phase 2 bridge materials.
- **Map edge distance:** Should require at minimum 30–50km of continuous expansion from base origin. This matches the timeframe when military pressure has scaled significantly and the player needs advanced defense + logistics infrastructure.

## Resource Clustering Strategy

### How Resources Generate

Resources generate as **clusters of deposits** rather than scattered individual patches:

| Cluster Size | Example | Player Experience |
|--------------|---------|-----------------|
| Small (local) | Iron ore within ~500m of base | Starter resources; early Phase 1 viability |
| Medium (reachable) | Oil + salt cluster within ~2km | Phase 1/2 transition materials without heavy exploration |
| Large (requires dedicated haulage) | Polymineral mountain range at 3–8km | Justifies building train networks, freight terminals, or dedicated logistics lines |
| Rare (requires significant investment) | Niobium + tantalum deposit at 15+ km | Late-game Phase 2 material; rewards advanced rail/logistics capability |

### Prospecting Mechanic (Connecting to Map Gen)

Players should be able to **read the map** to some degree — not by placing a "prospecting tool" on every tile, but through:

- **Surface indicators:** Certain ground colors, mineral outcrops, or terrain features hint at what's below. A deposit rich in one mineral may show visible surface traces that reward careful observation.
- **Geological continuity:** Deposits within the same biome share characteristics — if you find oil nearby, it's reasonable to expect salt or evaporites within a ~2km radius. This teaches "if X is here, look for Y there."

**Open decision:** Should this be explicit (informatron entry: "If you see sedimentary rock formations, check for oil deposits") or implicit (players learn through experience)? The former supports "knowledge before capability" but risks reducing it to pattern-matching. The latter creates more emergent discovery but higher initial friction.

### Progression-Driven Resource Discovery

Resources introduce **progressively** throughout the game — not all at once:

| Phase | Resource Introduction | Player Expectation |
|-------|----------------------|-------------------|
| Phase 1 (Conventional) | Surface deposits + shallow underground within ~2km of base. Common metals (iron, copper, aluminum), coal, oil near water features. | "I can build a complete starter factory from resources nearby." |
| Phase 2 (Domain Science) | Deeper deposits, polymineral formations at 3–10km. Rare earth elements, specific industrial minerals (niobium, tantalum, phosphorite). New resource types unlocked by prospecting/analyzing earlier deposits. | "I need to expand; the things I haven't found yet are worth the logistics cost." |
| Phase 3 (Simulation-Gated) | Deep geology revealed by simulation models — the Planetary Simulation Core predicts where high-value deposits exist based on regional geological data. Players can use simulation output to guide exploration efficiently, but must invest time/resources in actual prospecting. | "The simulation tells me *where* to look; I still need to get there and prove it." |

This progressive discovery directly supports the **Material Scope Boundaries** gap (#2 in mod-overview.md): players never see "100 new ores at once"; they discover them as their industrial needs drive exploration.

## Oil & Water Placement Strategy

### Rejecting Vanilla's Fixed Edge Wells

Vanilla's oil always spawns only at map edges is a fundamental constraint of the vanilla game's design that doesn't work for a 300h overhaul where players *need* oil near base to reach Phase 1/2 transition. Instead:

- **Oil deposits generate in sedimentary basin biomes** within the playable area. They should be sparse but not edge-only.
- **Water sources (rivers, lakes) generate independently** based on terrain elevation and biome type. Players don't need oil *and* water at the same location necessarily — this is solved through logistics, not forced co-location.
- **Rare deep-water wells or geothermal hotspots** may appear as rare map features but should not be required for any essential process.

### Oil Density & Quality Variation

Some regions may have high-viscosity crude that requires different processing than light sweet crude — creating a second layer of resource strategy:
- High-viscosity oil = more processing steps, lower yield per barrel, but perhaps more abundant in deposits.
- Light sweet oil = easier to refine, higher yield, but rarer as a deposit type.

**Open decision:** Is this worth the implementation complexity? It adds meaningful geological diversity and creates "do I invest in heavy-oil refining capability, or do I search for light crude?" — which is exactly the kind of decision the design wants. But it also requires more chemistry entries in chemical-processes.md that may not be necessary.

## Map Edge Behavior

### Military Pressure at Expansion Boundaries

As players expand outward, military pressure should interact with map edges meaningfully:

- **Pollution from factories creates a "pressure gradient" radiating outward.** Close factories attract more attacks; distant ones attract fewer. But this doesn't mean "run forever from enemies."
- **Map edge has increasing enemy density** (not infinite spawn zones — enemies are drawn to pollution, but if the map ends and no new factories are found nearby, they stop expanding). This rewards expansion with breathing room but makes the journey costly over time.
- **"Clean" territory:** A player who expands far enough from their industrial base into minimally polluted wilderness finds a quiet zone — but it's far from good ore bodies. This creates the genuine tradeoff: **safe space vs. resource-rich space.**

### Map Edge as Strategic Choice, Not Punishment

The map should never feel like "the game is forcing me to do X." The edge exists so that:
- Expanding players get breathing room from military pressure (they can outrun it if they invest in clean power early).
- But expanding far enough becomes an economic calculation — the further they go, the more expensive their logistics become.

## Connections to Other Design Gaps

### Map & World Gen ↔ Military Pressure

This doc's resource clustering directly interacts with the Combat & Warfare gap (#6 in mod-overview.md):
- Dirty factories near base → constant pressure → player considers clean power (military relief).
- Expanding into "clean" territory costs time and logistics investment.
- The military system should reward players who chose cleaner infrastructure earlier, but punish them for ignoring it entirely (not both options are equally good at every point in the game).

### Map & Gen ↔ Material Scope Boundaries Gap (#2)

Progressive resource introduction ensures that material scope is controlled not by an arbitrary cap on ore types, but by **when** they become relevant to the player. The map generates everything; players discover what they need as their industrial chain demands it. This directly addresses the cognitive complexity problem — no wall of "60 new materials"; just "your next research step needs something a bit further away."

### Map & World Gen ↔ Product Catalog Gap (#3)

The mineral catalog (mineral-catalog.md) must align with what generates on the map:
- Each deposit type in the catalog should correspond to at least one biome or terrain feature.
- Deposit density/spawn rates should support the "explore 5–10km for Phase 2 materials" timeline established here.
- The product catalog skeleton (minerals → refined → intermediates → end products) is *driven* by what generates on the map, not reversed.

## Open Decisions (Prioritized)

| Decision | Status | Notes |
|----------|--------|-------|
| **Biome-to-resource mapping** | ✅ Committed | Exactly **4 core biomes + 1 hybrid** (coastal = sedimentary/shelf overlap). Each has max **3 characteristic resources** to keep cognitive load bounded and force exploration for anything exotic. See table below for locked mapping. |
| **Prospecting mechanic** | ✅ Committed | **Hybrid approach.** Informatron gives *principles* (e.g., "sedimentary formations suggest nearby hydrocarbon deposits") — not coordinates or exact material calls. Players discover specifics through experience. Honors "knowledge before capability" without reducing discovery to pattern-matching. |
| **Oil quality variation** | ❌ Rejected | One oil type per biome. The diversity from "different oils" is already handled by the 5-tier machine system: MTier 3+ machines can process heavier crude that lower-tier machines physically cannot refine. No need for parallel chemistry entries or dual oil routes. |
| **Map edge interaction with military pressure** | ✅ Committed | Enemies don't stop at edges — they thin to a **sparse patrol layer (~10% base density)**. This creates real breathing room reward for expansion while keeping the map as a place, not a hard wall. Military pressure is lowest at edges; logistics cost is highest there. The tradeoff (safe but far vs. dangerous but close) is realized. |
| **Geological continuity rules** | ✅ Committed | Biome adjacency is **fixed**: sedimentary borders shield regions; volcanic zones always border mountain ranges; coastal biomes touch all others at water edges. Players learn discoverable patterns: "if I see X, Y is within a 2–3km radius." These are implicit rules players internalize through exploration — not explicit handbook hints. |
| **Default map size** | ✅ Committed | **x5 default** with x4/x6 selectable at world creation. This anchors the 5–15km Phase 2 + 20–40km rare material distances committed elsewhere.

## Draft Progression — Recommended

For this mod's ambition (300+ hours, Bob's/Angel complexity level):

- Map is at least vanilla's **very large** setting, with default scale at **x5**.
- Starting region has all Phase 1 essentials (iron, coal, copper, stone) within ~500m.
- Phase 2 bridge materials are spread across a 5–15km radius around base origin — requiring investment in logistics infrastructure to reach consistently.
- Rare endgame Phase 2/3 materials are at 20–40km distance from any known deposit cluster, rewarding advanced prospecting + rail/logistics capability.
