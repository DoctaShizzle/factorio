# Mining, Refining & Metallurgy

*Factorio overhaul design reference · Brainstorming / requirements phase*

Related documents: [Material Chain Map](material-chain-map.md) · [Chemical Processes](chemical-processes.md)

## Current Direction

Mining and refining are separate progression systems. Mining determines the mineral feed entering the factory; refining capabilities determine which pure materials can be recovered from it.

The design takes geological breadth and material inspiration primarily from GTNH, while looking to Bob's/Angel's for accessible, reusable processing stages and recoverable output balancing. We should borrow useful ideas without copying either mod's exact material list, ratios, or recipes.

### Mining Tiers as Feed Profiles

- **Surface deposits:** Finite, single-mineral supplies mined with near-vanilla electric drills. Focus on the most important early-game minerals, including minerals that can yield iron, copper, and other foundational materials. A single mineral may still yield several pure materials after multi-step refining.
- **Underground deposits:** One dominant mineral with smaller quantities of trace minerals, reflecting geological variation rather than a universal recipe ratio.
- **Ore bodies:** Several main minerals mined together, with the mix varying by deposit. These provide complex feeds for later sorting and refining capabilities.

All three tiers supply minerals. They do not each require a separate refining ladder.

### Refining and Balance Requirements

- Reuse a learnable set of processing stages, such as mechanical separation, chemical treatment, and thermal or electrolytic processing. Use exceptions when the material chemistry warrants them.
- Early processing should provide useful primary materials and a manageable residue stream. Later capabilities can recover more of the value in that shared residue, including sulfur, iron, and rare metals.
- More advanced recovery may trade lower primary-metal yield per unit of raw mineral for greater trace-material recovery. The output strategies and their costs must be legible to players.
- Trace recovery must not require the primary metal to be consumed at the same rate. For example, gold recovery from a copper-bearing feed should not force copper to back up when copper demand is saturated. Finding a non-voiding way to handle or route the primary stream is an open design problem.
- Buffers are acceptable where they support normal production. Voiding should not be a required balancing mechanism, especially for finite mineral resources. Finite deposits also mean trace yields are bounded by the available feed.

This remains a working direction, not a validated process specification. The worked examples below predate this direction and are hypotheses to revise; they do not establish a requirement for exactly three routes per mineral. Detailed material candidates and dependencies are tracked in the [Material Chain Map](material-chain-map.md).

---

## Exploratory Refining Example — Chalcopyrite

## The Three Mining Tiers

### Tier 1: Surface Deposits

Finite, single-mineral deposits mined with near-vanilla electric drills. These provide an introductory supply of foundational minerals; each mineral may still yield multiple pure materials through refining.

### Tier 2: Underground Mineral Deposits

One dominant mineral with trace minerals. Composition varies by deposit, adding geological and refining choices.

### Tier 3: Ore Bodies (Late Game)

Several main minerals mined together, with composition varying between deposits. These create mixed feeds for shared sorting and refining processes; the specific handling and balancing mechanics remain to be designed.

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

## Grand Refining Design — The Mirroring Framework

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

## Grand Refining Summary — The Pattern

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

## Refining Philosophy

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

Buffers may support normal production, but permanent accumulation should not be the expected solution.

Voiding should not be required for balance, particularly when processing finite mineral deposits.

Industrial equilibrium is the goal, but trace recovery must not depend on consuming primary outputs at a matching rate. This is an open constraint for the refining design.

---

## Process Control: Physical, Not UI-Based

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
