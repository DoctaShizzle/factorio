# Factorio Overhaul Concept V2
## Industrial Ecosystems and Process Engineering

---

# Executive Summary

This project is not intended to be:

- Factorio but larger
- Pyanodon's but harder
- GTNH but in Factorio
- Angel's with more ores

The goal is to create a coherent industrial ecosystem where every major mechanic supports a common vision.

The central design philosophy is:

> Progression should come from understanding and choosing industrial strategies rather than unlocking longer recipe chains.

The player should feel less like a factory builder and more like an industrial engineer.

---

# Grand Design Philosophy

Every major system should reinforce every other system:

- resource extraction
- refining
- metallurgy
- chemistry
- power generation
- pollution
- military pressure
- semiconductors
- endgame research

Every system should support the same industrial philosophy.

---

# Design Pillars

## Pillar 1: Multiple Industrial Processes
Every major product should have multiple viable production methods.

## Pillar 2: Tradeoffs Instead of Progression
Every product should have multiple viable production methods, each optimising different primary constraints.

### Primary Axes (the core tension)
- **Resource efficiency** — a la Angel's equilibrium
- **Pollution / military pressure** — a consequence axis, not a standalone one
- **Capital complexity** — infrastructure cost, not power or space

Almost every interesting conversation maps onto those three.

### Secondary Axes (useful but not central)
- Throughput
- Power consumption
- Floor space

Power and space matter, but they are levers — not the core tension.

## Pillar 3: Processes Instead of Recipes
The player should ask:

> Which process should I use?

instead of:

> Which recipe do I unlock next?

## Pillar 4: Refining Creates Options
Better refining should create additional options, not simply higher yields.

## Pillar 5: Pollution as an Optimisation Axis
Pollution is a strategic choice, not merely punishment.

## Pillar 6: Military Is Economic, Not Gimmicky
Avoid:
- "Special enemy X attacks thing Y"

Instead:

**Military is the price paid for industrial decisions.**

Dirty steel:
- throughput
- pollution → alien attacks

Clean steel:
- throughput
- alien attacks (but deferred/managed)

Pollution = **deferred military spending.**
This connects metallurgy, refining, power generation, and military into one system.

## Pillar 7: Equilibrium Over Disposal
Storage may exist.
Voiding may exist.
Neither should be required.

The optimal solution should be:

> equilibrium

rather than:

> disposal

---

## Pillar 8: Capabilities Over Numbers (NEW)
The player should unlock:
- prospecting
- flotation
- chemical refining
- semiconductor fabrication
- automation systems
- simulation infrastructure

rather than simply:
```
+20% efficiency
+50% throughput
Tier 5 machine
```

This is one of GTNH's greatest strengths. People remember:

> "I got a cleanroom."

Not:

> "My machine got 12% faster."

---

# Key Inspirations

## Satisfactory
- Situational optimisation
- Alternate recipes as tradeoffs
- No universally correct solution

## Angel's Refining
- Refinery equilibrium
- Self-balancing production systems
- Discoverability is the challenge, not complexity

## GTNH
- Memorable capability unlocks
- Real-world materials
- Industrial depth

## Dyson Sphere Program
- Grand purpose for industrial growth
- Computing and simulation as an endgame goal

---

# Grand Refining Design — Working Example: Chalcopyrite

## The Three Extraction Tiers (Retained)

### Tier 1: Surface Deposits
Iron Deposit, Copper Deposit, Coal Deposit. Single-ounce processing. Tutorial layer.

### Tier 2: Underground Mineral Deposits
Single-mineral deposits with extraction complexity. Hematite, Magnetite, Chalcopyrite, Bauxite, Galena/Sphalerite pairs.

### Tier 3: Ore Bodies (Late Game)
Multi-output "sushi belts" — e.g., VMS formation outputs chalcopyrite + pyrite + sphalerite + galena + trace precious metals simultaneously on one conveyor. Refining equilibrium becomes a mechanical necessity, not an aesthetic choice.

---

## Deep Dive: Chalcopyrite (CuFeS₂) — From Deposit to Products

### Step 1: Extraction
Chalcopyrite deposit produces raw ore that goes directly into the refinery. No smelting first.

**The challenge:** Every kilogram of chalcopyrite contains copper, iron, and sulfur in fixed ratios. You cannot extract one without producing the others. The question is *how much of each you recover* vs. what you must deal with as byproduct.

### Step 2: Three Production Methods

---

#### Method A: Froth Flotation (The Equilibrium Challenge)

**Process:** Crush ore → mix with water + collectors → bubble air through mixture → copper minerals attach to bubbles and float → skim off copper concentrate → the rest goes somewhere.

**Output from one unit of chalcopyrite:**
- Copper concentrate (~70% Cu recovery, 30% lost to tailings — not waste, but diluted)
- Iron-rich sludge (the non-floatable fraction — contains ~60% of original iron)
- Sulfur in tailings/sludge (part of recovered copper compounds, part locked in waste stream)

**Physical configuration:** Determined by **collector type** and **bubble density**:
| Collector | Copper recovery | Iron capture | Sulfur handling |
|-----------|----------------|-------------|-----------------|
| Xanthate  | High (~70%)    | Medium      | Moderate        |
| Thiol     | Lower (~55%)   | High (~80%) | Better capture  |
| Composite  | Balanced (~65%)| Balanced    | Balanced        |

**Equilibrium challenge:** Higher copper recovery means more iron sludge to process. You can't just "store it." You must design a **secondary line** for the iron-rich byproduct, or accept that your output ratios are dictated by whichever byproduct you *can* handle at scale.

**Tradeoffs:**
- ✅ Low capital complexity (standard flotation tank, simple machinery)
- ✅ High copper yield if optimized correctly
- ❌ Massive iron co-product — must be integrated into your steel/cement lines
- ❌ Sulfur management required (can be sold to acid production!)
- ⚠️ Requires water infrastructure

**This is the "default" path.** Every player discovers this first. It works. But it creates a byproduct problem that forces the factory to expand. The equilibrium challenge is *designed into the ore*.

---

#### Method B: Hydrometallurgical Leaching (The Infrastructure Path)

**Process:** Crush ore → soak in acidic solution → copper dissolves → electrolysis or cementation → pure copper recovered.

**Output from one unit of chalcopyrite:**
- Pure copper (>95% recovery, direct to wire manufacturing)
- Acid waste stream (contains dissolved iron + residual acid — needs treatment or neutralization)
- Unreacted sulfide residue (can potentially be processed by Froth Flotation Method A!)

**Physical configuration:** Determined by **leaching agent**:
| Agent | Recovery speed | Copper purity | Acid consumption | Byproduct complexity |
|-------|---------------|--------------|------------------|---------------------|
| FeCl₃ (ferric chloride) | Fast | Medium-high | Low | Moderate — recyclable |
| H₂SO₄ + oxidant | Slower | Very high | High | Complex — needs neutralization |
| Thiosulfate (advanced) | Slowest | Highest | None | Minimal — green chemistry |

**Equilibrium challenge:** Acid waste. If you're not producing or consuming acid elsewhere in your factory, this path creates a disposal problem. But if you *are* producing sulfuric acid (from the sulfur captured in Method A), that acid feeds here. **The two methods are designed to interlock.**

**Tradeoffs:**
- ✅ Higher copper purity (directly usable in semiconductors later)
- ✅ Can chain with Method A: leach the flotation residue for additional recovery
- ❌ Requires acid production infrastructure *before* you can run at full capacity
- ❌ High power consumption (electrolysis step)
- ⚠️ Acid handling adds safety complexity

**This is the "ambitious" path.** It only works if your factory is already complex enough to handle acid streams. But it opens high-value downstream paths.

---

#### Method C: Pyrometallurgical Smelting (The Dirty Path)

**Process:** Heat ore → copper sulfide melts and separates → converter removes remaining sulfur → blister copper.

**Output from one unit of chalcopyrite:**
- Blister copper (~98% purity, with some iron/sulfur contamination)
- Massive SO₂ off-gas (pollution + potential resource — can be captured for acid production!)
- Slag byproduct (iron silicate — usable in cement/construction!)

**Physical configuration:** Determined by **fuel type** and **off-gas handling**:
| Fuel | Pollution | Copper purity | Efficiency | Infrastructure |
|------|-----------|--------------|------------|----------------|
| Coal | Very high | Medium | High | Simple (just a furnace) |
| Coke | High | High | Higher | Moderate |
| Oxygen-enriched blast | Medium | Very high | Highest | Complex (needs O₂ plant) |

**Equilibrium challenge:** SO₂ off-gas is both pollution *and* resource. If you capture it → sulfuric acid → Method B. If you vent it → alien attacks (pollution = deferred military spending). The factory must either **consume its own byproduct** or **pay the military price**.

**Tradeoffs:**
- ✅ High throughput — processes ore fastest of all methods
- ✅ Slag can be integrated into cement production (byproduct synergy)
- ❌ Most polluting — immediate alien attention
- ❌ Requires oxygen infrastructure for clean operation
- ⚠️ Copper purity may need additional refining

**This is the "industrial scale" path.** It's fast, dirty, and forces pollution decisions. Perfect for early-to-mid game expansion when military pressure hasn't become critical yet.

---

### Step 3: Equilibrium — How This Creates a System

The three methods are **designed to interlock**, not compete independently:

```
Method A (Froth Flotation)                    Method B (Leaching)
         │                                            │
Copper concentrate ──→ Coppering ──→ Pure copper ──→ Semiconductor-grade Cu
Iron sludge ──→ Steel lines ──→ Product X           Residue
Sulfur in tailings ──→ Acid plant ──→ H₂SO₄ ──→ Feeds Method B ←┘

Method C (Smelting)
         │
Blister copper → Additional refining → Semiconductor-grade Cu
SO₂ off-gas → Acid plant → H₂SO₄ → Feeds Method B
Slag → Cement production → Construction materials
```

**The equilibrium chain:**
1. Run Froth Flotation → get iron sludge + sulfur tailings
2. Send iron sludge to steel lines, sulfur to acid plant
3. Acid feeds Leaching process → higher purity copper
4. Smelting gives high throughput but SO₂ also feeds acid plant
5. Slag from smelting feeds cement production

**The key insight:** No single method works optimally in isolation. **Every method creates byproducts that the factory must absorb.** The player's challenge is designing a factory where *all outputs find a home*. That's equilibrium, not disposal.

---

# Grand Refining Design — The Mirroring Framework

## Why Mirroring?

If each mineral has completely different process structures, players face n³ combinations and cognitive overload. The three methods must follow the same structural pattern so players transfer mental models between minerals.

### The Mirroring Pattern (established by chalcopyrite)

Every mineral has exactly three production methods following the same structure:

| | Method A: Physical Separation | Method B: Chemical Processing | Method C: Thermal Processing |
|---|---|---|---|
| **Approach** | "Default, balanced" — accessible early, creates equilibrium challenge | "Ambitious, high-value" — requires prior infrastructure, yields superior output | "Industrial scale" — fast, dirty, pollution tradeoff |
| **Byproduct type** | Mixed co-products (must be integrated into factory) | Chemical waste stream (acid/neutralization needed) | Gas emission + solid slag (pollution or resource) |
| **Interlock point** | Tailings → acid plant | Requires acid from other method | SO₂/slag → acid/cement |
| **Purity tier** | Medium → needs further refining | High → direct use possible | Variable → may need secondary processing |

Players only need to learn **one pattern**. When they see a new mineral, the methods should feel familiar.

---

## Example 2: Hematite (Fe₂O₃) — Iron Refining

### Step 1: Extraction
Hematite is an iron oxide deposit. High purity *by nature* — already partially refined. The challenge is **selective reduction** — turning oxide back into metallic iron while managing co-products.

### Step 2: Three Production Methods

#### Method A: Direct Reduction Blast Furnace (The Equilibrium Challenge)

**Process:** Crush hematite → mix with coke and limestone → blast furnace reduces ore to molten pig iron.

**Output per unit of hematite:**
- Pig iron (~93% pure, ~7% carbon + impurities — needs further refining to steel)
- Silica-rich slag (co-product from limestone + gangue — usable in cement/construction!)
- CO/CO₂ off-gas (reducing atmosphere — capture as fuel gas or vent as pollution)

**Physical configuration:** Determined by **coke quality** and **blast temperature**:
| Setting | Iron recovery | Purity | Pollution | Infrastructure |
|---------|--------------|--------|-----------|----------------|
| Standard coke, ambient blast | Medium (~80%) | Low | High | Simple |
| High-grade coke, hot blast | High (~92%) | Medium | Medium | Moderate (pre-heating) |
| Oxygen-enriched, automated feed | Very high (~96%) | High | Lower | Complex (needs O₂ plant + automation) |

**Equilibrium challenge:** Slag volume. Every ton of pig iron produces ~0.4 tons of slag. You **must** have a cement/construction line to absorb it. If not → disposal problem = equilibrium failure.

**Tradeoffs:**
- ✅ High throughput, proven industrial process
- ✅ Slag integrates with cement production (Method C synergy)
- ❌ Requires coke infrastructure *before* running at capacity
- ❌ Pig iron purity limits downstream use — needs basic oxygen furnace for steel
- ⚠️ CO/CO₂ management: vent = pollution, capture = fuel resource

**This is the "default" path.** Every player discovers this first.

---

#### Method B: Hydrogen Reduction (The Clean Path)

**Process:** Crush hematite → expose to hydrogen gas at controlled temperature → direct reduction to sponge iron + water vapor.

**Output per unit of hematite:**
- Sponge iron / DRI (~95% pure metallic iron)
- Water vapor (from reduction reaction: Fe₂O₃ + 3H₂ → 2Fe + 3H₂O)
- Trace element residue (silica, manganese — minor co-product)

**Physical configuration:** Determined by **hydrogen source**:
| Source | Purity | Infrastructure cost | Carbon footprint |
|--------|--------|-------------------|------------------|
| Electrolytic H₂ (from water) | Very high | High (needs electrolysis + power) | None if clean power |
| Steam methane reforming (natural gas) | Medium | Moderate | Moderate — produces CO₂ |
| Byproduct H₂ (from chlor-alkali process!) | Good | Low (already exists in factory) | Marginal |

**Equilibrium challenge:** Hydrogen source matters deeply. Clean H₂ from elsewhere makes this the **cleanest iron path**. But it requires hydrogen infrastructure *before* large-scale DRI production.

**Tradeoffs:**
- ✅ Highest purity iron — direct feed to specialty steel alloys
- ✅ Near-zero pollution (if H₂ source is clean)
- ❌ Requires hydrogen production infrastructure *first*
- ❌ Lower throughput than blast furnace (temperature limits)
- ⚠️ Sponge iron must flow directly to steel line — no storage (oxidizes)

**This is the "ambitious, clean" path.** Only works if your factory has already invested in clean hydrogen.

---

#### Method C: Plasma Reduction (The Industrial Scale Path)

**Process:** Feed crushed hematite into plasma arc furnace (>3000°C) → complete reduction to molten iron → tap directly.

**Output per unit of hematite:**
- High-quality molten iron (~96% pure, minimal carbon contamination — superior to blast furnace pig iron)
- Captured gas emissions (fully contained — can be scrubbed for CO₂ capture!)
- Minimal slag (silica + impurities float and skim as high-grade construction aggregate)

**Physical configuration:** Determined by **plasma power source**:
| Power source | Operation cost | Purity | Sustainability |
|-------------|---------------|--------|----------------|
| Coal/steam generators | Low cost, high pollution | Medium | Poor |
| Nuclear reactor power | High capital, low running cost | Very high | Clean |
| Solar/wind + storage | Variable | Medium-high | Fully renewable |

**Equilibrium challenge:** Power intensity. Plasma consumes ~5× electricity of blast furnace per ton. You need **dedicated power infrastructure sized for sustained high load**. Power plant placement becomes the bottleneck.

**Tradeoffs:**
- ✅ Highest single-step purity (no secondary refining needed)
- ✅ Minimal slag — highest resource efficiency of all iron methods
- ✅ Contained emissions = no alien attack trigger (if scrubbed)
- ❌ Extremely high power demand — requires dedicated generation
- ⚠️ Connects directly to power grid overhaul (grid stability critical)

**This is the "industrial scale, clean energy" path.** Clean iron costs capital complexity, not pollution.

---

### Step 3: Hematite Equilibrium — Interlock Chain

```
Method A (Blast Furnace)                     Method B (H₂ Reduction)
         │                                            │
Pig iron ──→ Basic Oxygen Furnace → Steel            Sponge iron → Direct to specialty steel line
Slag ──→ Cement production                          Water vapor → Condense / vent
CO/CO₂ gas ──→ Fuel capture → feeds power plants     H₂ source? ← (electrolysis / chlor-alkali)

Method C (Plasma Reduction)
         │
High-purity molten iron → Direct to steel line
Captured CO₂ → Carbon products or sequestration
Power demand → Dedicated solar/nuclear array
```

**The equilibrium chain:**
1. Blast Furnace Method A early → pig iron + slag + CO gas
2. Slag feeds cement production
3. CO gas captured → supplemental fuel for power plants
4. Later, H₂ reduction line with electrolytic hydrogen
5. Sponge iron flows directly to specialty steel — no BOF needed
6. Plasma replaces blast furnace once nuclear/solar capacity is available

**Mirroring with chalcopyrite:** Same three-method pattern:
- Method A (Blast Furnace) = Froth Flotation → equilibrium via byproduct integration
- Method B (H₂ Reduction) = Leaching → high value, needs prior infrastructure
- Method C (Plasma) = Smelting → scale + pollution tradeoff

**Iron is simpler than copper chemically.** Methods mirror but interlocks are more straightforward — intentional. Iron comes earlier in progression.

---

## Example 3: Bauxite (Al₂O₃·xH₂O) — Aluminum Refining

### Step 1: Extraction
Bauxite is an aluminum ore formed by intense tropical weathering of aluminosilicate rocks. Contains alumina, silica, iron oxides, trace titanium. **Cannot be smelted directly** — Al-O bond too strong. Requires chemical processing first (Bayer process) then electrolysis.

### Step 2: Three Production Methods

#### Method A: Bayer Process + Hall-Héroult Electrolysis (The Equilibrium Challenge)

**Process:** Crush bauxite → dissolve in hot sodium hydroxide under pressure → filter out "red mud" → precipitate pure alumina → electrolytic aluminum deposition.

**Output per unit of bauxite:**
- Aluminum metal (~98% purity, needs further refining for some uses)
- Red mud (waste — iron oxide + silica residue, ~1-2 tons per ton of alumina)
- Sodium hydroxide consumption (must be replenished)
- Fine aluminum dust emissions (capturable but requires infrastructure)

**Physical configuration:** Determined by **red mud management**:
| Management strategy | Aluminum yield | Factory impact | Complexity |
|-------------------|--------------|---------------|------------|
| Process into construction aggregate (sinter) | Slightly lower | Creates building material product line | Moderate |
| Recover rare earth elements (if present) | Higher total value | Requires RE recovery infrastructure | High |
| Neutralize for steel industry (red mud is basic — replaces limestone in BOF) | Standard | Iron-smelting synergy | Moderate |

**Equilibrium challenge:** Red mud. Every ton of processed bauxite creates 1-2 tons of strongly alkaline red mud. Storage = failure. Voiding = failure. Factory must either:
1. Sell red mud to steel lines as limestone substitute (ties aluminum to iron)
2. Sinter into construction materials (ties to cement/construction chain)
3. Extract rare earth elements from specific bauxite deposits (late-game capability unlock)

**Tradeoffs:**
- ✅ First path to aluminum — opens lightweight alloys for endgame infrastructure
- ✅ Bayer process is well-understood; reliable if managed correctly
- ❌ Red mud byproduct *must* be integrated into another industrial chain
- ❌ NaOH consumption creates dependency on chlor-alkali process!
- ⚠️ Al-O bond requires electrolysis — connects to power system overhaul

**This is the "default" path.** Bayer is how aluminum is made in the real world. Forces red mud integration and NaOH supply chain design.

---

#### Method B: Hall-Héroult Cell Optimization (The High-Value Path)

**What makes Method B different from A?** Bayer gives you *aluminum* by chemically processing alumina. Hall-Héroult is about **how you configure the electrolysis cell itself** — and it matters for purity, energy efficiency, and byproducts.

This is a **configuration within the Bayer process**, not fully independent. It mirrors the pattern through cell design choices:

| Cell design | Aluminum purity | Energy efficiency | Anode type | Byproduct complexity |
|-----------|----------------|-------------------|-----------|---------------------|
| Standard carbon anode, batch | Medium (~98%) | Baseline | Consumed — produces CO₂ | Standard |
| Inert anode (advanced) | High (~99.5%) | +15% | Not consumed — no CO₂ | Cleaner but needs advanced materials |
| Low-temperature eutectic (mid-game unlock) | Very high (>99.8%) | Variable | N/A | Needs fluoride management |

**Equilibrium challenge:** Continuous power and steady alumina feed. Aluminum cannot be batch-mode — requires **continuous flow** from Bayer process. The constraint isn't disposal; it's sustained industrial capacity.

This creates **forced coupling**: Bayer produces alumina, Hall-Héroult converts it to metal. Together they form one industrial unit. The "choice" is cell configuration (purity vs efficiency).

**Tradeoffs:**
- ✅ Purest aluminum output — direct feed for semiconductor/industrial applications
- ✅ Inert anode needs platinum group metals ← links back to chalcopyrite refining!
- ❌ Forcibly coupled with Bayer process — no independent existence
- ⚠️ Continuous power requirement — most sensitive process to grid stability
- ⚠️ Fluoride management required (electrolyte salts)

**Deliberate exception to mirroring:** Aluminum has fewer independent routes because Al-O chemistry is less forgiving. We document this as an intentional deviation.

---

#### Method C: Carbothermal Reduction (The Bridge Path)

**Process:** Mix alumina with carbon → heat in inert atmosphere (~2000-2500°C) → reduce to aluminum suboxide vapor → condense.

**Output per unit of bauxite:**
- Aluminum metal (~92% purity, oxygen contamination — needs secondary refining)
- CO/CO₂ gas (capture as fuel or vent as pollution)
- Unreacted alumina residue (recyclable back into Bayer process!)

**Physical configuration:** Determined by **temperature and atmosphere control**:
| Condition | Purity | Temperature needed | Infrastructure |
|-----------|--------|-------------------|----------------|
| Electric arc furnace (~2000°C) | Medium (~92%) | High but achievable | Moderate |
| Induction furnace + vacuum (~2500°C) | High (~97%) | Very high | Complex (vacuum seals, refractory) |
| Solar concentrator + insulated reactor | Variable | Extreme | Specialized (solar tower/reflector) |

**Equilibrium challenge:** Purity vs independence tradeoff. Carbothermal produces aluminum too contaminated for most uses — but it's the **only** path that doesn't require Bayer infrastructure. Trades purity for independence.

This creates a **bridge capability**: early players who need aluminum *now* before building Bayer can use carbothermal as stopgap. Factory self-corrects toward Bayer+Hall-Héroult as capability grows.

**Tradeoffs:**
- ✅ No prerequisite infrastructure — standalone
- ✅ Good early-to-mid game bridge technology
- ❌ Lowest purity of all aluminum paths
- ❌ CO gas must be captured or vented (pollution tradeoff)
- ⚠️ Unreacted alumina recycling required — ties back to Bayer

**This is the "bridge" path.** Not the end state — a temporary solution that pushes players toward real process. In well-designed factories, carbothermal usage naturally phases out.

---

### Step 3: Bauxite Equilibrium — Interlock Chain

```
Method A (Bayer) + Hall-Héroult electrolysis              Method C (Carbothermal)
         │                                            │
Alumina ──→ Aluminum (~98% purity)                      Aluminum (~92% → secondary refine)
Red mud ──→ Steel lines (caustic substitute)            CO/CO₂ gas → Fuel capture or vent
NaOH consumption ← (chlor-alkali dependency)             Unreacted alumina → Recycle to Bayer ←┘

Hall-Héroult cell config:
Standard → cheaper, lower purity                         Inert anode needs: platinum group metals ← chalcopyrite refining!
```

**The equilibrium chain:**
1. Carbothermal Method C early game for quick aluminum (bridge technology)
2. Build Bayer + Hall-Héroult as primary line mid-game
3. Red mud → steel lines (method interlock with hematite processing!)
4. Platinum group catalysts from chalcopyrite → enable clean inert anodes ← cross-mineral link!
5. Aluminum alloys → lightweight endgame infrastructure

**Key interlocks between minerals:**
- Red mud (bauxite) → steel production (iron industry) ← **mineral cross-connect**
- Platinum group metals (chalcopyrite) → inert anodes for electrolysis ← **mineral cross-connect**
- Aluminum alloys → lightweight endgame infrastructure ← **progression link**

---

# Grand Refining Summary — The Pattern

## Mirrored Methods Across All Minerals

| | Method A: Physical Separation | Method B: Chemical Processing | Method C: Thermal/Industrial |
|---|---|---|---|
| **Chalcopyrite** | Froth Flotation (equilibrium challenge) | Leaching (high value, needs acid) | Smelting (fast + dirty) |
| **Hematite** | Blast Furnace (equilibrium challenge) | H₂ Reduction (clean path) | Plasma Reduction (scale) |
| **Bauxite** | Bayer Process (equilibrium challenge) | Hall-Héroult cell opt. (purest) | Carbothermal (bridge tech) |

Note: Bauxite's Method B is a sub-optimization rather than independent method — deliberate exception for aluminum chemistry.

## Three Equilibrium Problem Types

Every mineral creates one of three types of equilibrium challenges:
1. **Solid byproduct integration** (all minerals): Slag/red mud must find home in another chain
2. **Gas management** (chalcopyrite, hematite): CO₂/SO₂ vented (pollution) or captured (resource)
3. **Continuous flow requirement** (aluminum > chalcopyrite > iron): Some processes cannot run in batches

## The Interlock Web

No mineral operates independently. Byproducts from one always feed another:
- Chalcopyrite sulfur → sulfuric acid → feeds hematite leaching & bauxite Bayer process
- Hematite slag (iron residue) → steel lines (as limestone substitute in BOF)
- Bauxite red mud (alkaline waste) → steel production as caustic agent
- Platinum group metals from chalcopyrite → inert anodes for Hall-Héroult electrolysis
- Aluminum alloy infrastructure → lightweight structures for endgame network

**The factory is not a collection of parallel processes. It's a single connected organism.** You cannot optimize one mineral in isolation — the global equilibrium depends on cross-chain coordination.
- **Iron/slag products** → construction infrastructure for endgame network

One deposit. Four industrial chains. All connected through the equilibrium challenge.

---

---

# Refining Philosophy

The factory begins at the refinery, not at the smelter.

Mine Ore
→ Smelt Plate

becomes:

Extract Minerals
→ Process Streams
→ Separate Materials
→ Optimise Refinery
→ Manufacture Products

## Byproduct Philosophy

Storage is not a solution.

Voiding is not a solution.

Industrial equilibrium is the solution.

---

# Process Control: Physical, Not UI-Based

Ore + Process Configuration → Preferred Output Mix

## How Players Configure Processes (Avoid Sliders)

**Sliders feel gamey. Configuration should be physical — via factory design.**

### Option A: Catalyst Choices
Example — Copper Flotation:
- Catalyst A: maximize copper recovery
- Catalyst B: maximize nickel recovery
- Catalyst C: maximize precious-metal recovery

Each catalyst produces the same raw stream but emphasizes different outputs.

### Option B: Machine Configuration
Different recipes for different modes — like Angel's process control but more discoverable.

### Option C: Process Module Slots
Like inserters/underground belts as tangible machine parts:
- Recovery Module → higher yield, lower throughput
- Purity Module → cleaner separation, higher power
- Throughput Module → raw capacity over efficiency

> Configuration through factory design. Not through UI menus.

---

# Industrial Knowledge as Progression

## Knowledge Should Unlock Earlier Than Capability

Information unlocks **before** the player can implement it.

Early game, a player opens the handbook and sees:
```
Iron Industry
- Primitive Blast Furnace
- Oxygen Furnace
- Hydrogen Reduction
- Plasma Reduction
```
The player **cannot build them yet.** But they know they exist.

This creates **anticipation** — similar to GTNH, but with a crucial difference:

GTNH often says: > "Here's the next thing."

Our handbook should say: > "Here's the entire industrial journey."

### The Principle: Don't Hide Complexity. Reveal It Gradually.
- ✅ Reveal future systems
- ✅ Explain their purpose
- ✅ Explain tradeoffs
- ❌ Hide them until hours later

---

# Semiconductor Philosophy

Semiconductors are not the theme.
They are the culmination.

Early Game:
- Extraction
- Refining
- Metallurgy

Mid Game:
- Chemistry
- Catalysts
- Process optimisation

Late Game:
- Silicon purification
- Specialty gases
- Cleanrooms
- Wafer fabrication

End Game:
- Processors
- Computational clusters
- Simulation hardware

---

# Endgame Vision: Distributed Network

The final objective is creating computational capacity.

### NOT a single megastructure (DSP already did that)

**A network across the map:**

```
Wafer Fab
→ CPU Fab
→ Supercomputer Facility
→ Simulation Cluster
→ Planetary Research Center
```

spread across the terrain. This is more Factorio-like and more scalable.

The "Planetary Simulation Engine" is a **network** — not a building.

---

# Things To Avoid

- Recipe inflation
- Mandatory upgrades
- Single correct answers
- Artificial complexity
- Reliance on storage
- Reliance on voiding
- Stitched-together design

---

# The True North Star

> The goal is not to simulate industry.
>
> The goal is to make the player think like an industrial engineer.
>
> Realism is valuable only when it creates meaningful engineering decisions.

This single sentence explains almost every decision we've made so far:
- why we like Angel's equilibrium
- why we dislike mandatory storage
- why we like DSP's end goal
- why we want real minerals
- why we don't want heat-pipe busywork
- why GTNH's strongest moments are capability unlocks

---

---

# Programmable Logic Controllers (NEW — FROM FAMILY IDEAS)

## Vision: A General-Purpose Factory Control Language

A programmable controller for industrial automation. Not a circuit-logic toy, not a constrained template builder — a general-purpose control system embedded in Factorio.

### What It Does

Players write programs that:
- Read sensor data from any connected machine (flow rate, temperature, pressure, tank levels, item throughput)
- Control machines dynamically (start/stop pumps, open/close valves, adjust machine modes, cycle between recipes)
- Implement feedback loops autonomously (tank full → redirect flow → throttle production)
- Enable true "smart factories" that self-regulate based on factory state

### Why General-Purpose?

Constraint-based systems work until they don't. A player who can only do pre-built templates will hit the edge of those templates within hours of a serious factory. The moment they want "split this flow 60/40 if both tanks are above X but prioritize Y when Z happens" — templates fail.

A general-purpose control language gives players **expressive freedom**. Yes, it raises the learning curve. But this is an overhaul mod aimed at industrial engineers, not casual builders. The target audience **wants** to write code that controls their factory.

### Implementation Surface (Target Design)

- **PLC unit** — the hardware controller, with memory/slot limits scaling as a progression element
- **Text-based programming language** — in-game editor, not external files. Syntax designed for industrial logic: conditionals, loops, variables, functions, time/delay primitives
- **Sensor API** — read values from connected machines (fluid levels, temperatures, throughput counters, machine states)
- **Control API** — write commands to connected machines (start/stop, mode switches, valve positions)
- **Network connectivity** — wired connections + wireless range option. Programmed logic can't magically reach across the map without infrastructure
- **Debug tools** — watch variables in real-time, set breakpoints, step execution, log sensor snapshots
- **Modular architecture** — subroutines/functions for reusable control patterns (PID-like controllers, state machines)

### Language Design Considerations

Options to consider:
1. **Custom DSL** — purpose-built language with industrial semantics (like Structured Text / IEC 61131-3 subset). Easier to constrain and optimize, harder for programmers who want flexibility.
2. **Embedded Lua/Python** — use Factorio's existing scripting or a lightweight embedded VM. Leverages familiar languages, gives full expressiveness, but adds implementation overhead.
3. **Hybrid** — core control primitives in a simple DSL + optional advanced functions in a scriptable language

### MVP Stage

Even with general-purpose ambition, there's a practical minimum:
- Core PLC hardware unit
- Basic text editor with syntax highlighting
- 5-7 sensor inputs (fluid level, temperature, machine status)
- 5-7 control outputs (start/stop, mode toggle, valve open/close)
- Variables and conditionals (if/then/else)
- Loops with configurable delay
- Local network connectivity (wired only)

MVP scope: enough to write programs that actually solve real problems (production balancing, overflow protection, auto-startup sequences). Not just a proof of concept — genuinely useful.

### Full Vision

Beyond MVP:
- Custom data types and arrays
- Named functions/subroutines with parameters
- Interrupt handling for fault detection
- PID control loops for temperature/pressure regulation
- Wireless communication between PLCs (for distributed systems)
- Time-series data logging and visualization
- Simulation mode (test programs without affecting running factories)

### Connection to Design Pillars

**Pillar 3: Processes Instead of Recipes**
The PLC automates *industrial processes*, not conveyor logic. A player can write a program that manages refinery equilibrium automatically — the core mechanic becomes designing and programming the controller, not just placing machines.

**Pillar 8: Capabilities Over Numbers**
"I built a programmable control system for my chemical plant." This is a genuine capability milestone.

**Pillar 10: Configured Through Factory Design**
The PLC connects to machines physically (wired infrastructure), making automation a tangible engineering decision, not an abstract setting.

---

# Chemical Processes (NEW — FROM FAMILY IDEAS)

Like GregTech and Bob/Angels, real chemical processes should be **educational as well as mechanical**.

Players should encounter:
- Multiple pathways to the same product (e.g., different ways to make polyethylene / plastics)
- Named reactions with real chemistry
- Intermediates that mirror actual industrial chemistry
- Discovery of "oh, this is how they actually make it in real life" moments

Chemical depth should serve the design pillars — not exist for its own sake.

Each chemical process reveals:
1. The real-world chemistry
2. Multiple viable production routes
3. Tradeoffs between them (efficiency, infrastructure, pollution)

---

# Power System Overhaul (NEW — FROM FAMILY IDEAS)

Satisfactory and Factorio's global infinite power grid is unrealistic. GTNH's voltage/ampere system adds meaningful dimension.

## Vision: Grid-Based Power, Not Global Bus

**No more connect-everything-to-the-nearest-wire.**

### Transmission Tiers
- **Low-voltage wiring** — limited distance, small loads (early game / local use)
- **High-voltage lines** — long-distance transmission with losses
- **Transformation stations** — step-up / step-down between voltage tiers

### Conductor Variety (GTNH-inspired)
Different metals = different conductivity:
- **Copper** — good conductivity, standard high-voltage
- **Tin** — lower capacity, cheaper
- **Gold** — superior conductivity for late-game precision distribution
- **Aluminum** — lightweight, long-distance overhead lines

### Power Losses
Distance-based losses make generator placement matter:
- Power plants can't just be "placed anywhere"
- Industrial clusters need their own generation
- Long-haul transmission is expensive and wasteful
- Local generation becomes a strategic choice

This turns power into an **engineering problem**, not a checkbox.

### UX Requirements (CRITICAL — this is what makes or breaks the system)

The most frustrating part of GTNH's power was diagnosing failures. We solve that with transparency:

**Hover diagnostics on poles/lines:**
```
400A @ 1000V
Loss: 2.3% per tile (copper, low-voltage)
Total drop: 87V over 38 tiles
Capacity remaining: 92%
```

**Onboarding requirement:**
Dedicated page/tutorial explaining:
- Why power grids exist (vs Factorio's "connect anything anywhere")
- Voltage = pressure analogy
- Resistance + distance = loss
- How to read the diagnostics overlay
- Common failure modes and how to fix them

The player should feel smart for solving a power problem — not confused by it.

This is the difference between GTNH's power system (opaque frustration) and this design (transparent complexity).

---

# Fluid System Overhaul (NEW — FROM FAMILY IDEALS)

Bob/Angels attempted this but the systems felt bolted-on. Our approach:

## Pipe Diameter & Material Matters

### Diameter Tiers
- Narrow pipes → lower throughput (m³/h equivalent)
- Wide pipes → higher throughput, more material cost

### Material Properties
Different pipe materials can handle:
- **Temperature ranges** — some fluids break standard pipes
- **Chemical resistance** — corrosive fluids degrade certain materials
- **Pressure ratings** — high-flow systems need reinforced piping

### Pumps as Mechanical Components
- Add pumps with rated throughput (m³/h)
- Pressure drops across long pipe runs
- Pump placement affects flow rates

This turns fluid logistics into a tangible engineering challenge rather than "just connect it and hope."

---

# Questbook / Handhook Mechanic (NEW — FROM FAMILY IDEAS)

Informatron exists as our handbook base but **lacks quest/progression mechanics**. GTNH-style capability unlocking requires custom work.

## Research Direction: Can we modify Informatron?

- [ ] Investigate Informatron's addon/plugin API
- [ ] Determine if "capability unlock" entries are feasible on top of it
- [ ] If not feasible, plan a fork or separate mod

## Design for the Mod

The questbook should:
1. Show the **full industrial journey** (not hidden chapters)
2. Provide **capability unlocks** when tasks are completed — new recipes, systems, processes become available
3. Maintain **information availability before capability** — consistent with Pillar 9
4. Use Informatron as the display layer, quest mechanics as an extension

## Key Distinction from Existing Quest Mods

Existing mods (e.g., `factorio-quest-system`) generate **random challenge objectives**. Ours is **fixed progression**:
- Completing Task A unlocks Process B
- Not "here's a random challenge" but "here's the next step in your industrial education"

---

# Mission Statement

> Build a coherent industrial ecosystem where extraction, refining, metallurgy, chemistry, power generation, pollution, military pressure, semiconductors, and the endgame all emerge from the same design philosophy.

Or more simply:

> Angel's equilibrium, GTNH's ambition, Satisfactory's meaningful choices, Dyson Sphere Program's vision, and Factorio's clarity.
