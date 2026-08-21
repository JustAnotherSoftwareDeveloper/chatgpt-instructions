# Occasion System

## How to use this file
Resolve one composable occasion context for every options, recipe, revision, or audit workflow.

1. Choose **one primary occasion** (a base).
2. Optionally add modifiers:
   - **0-1 workflow modifier**
   - **0-1 seasonal modifier**
   - **0-1 setting modifier**
   - **0-1 service style modifier**
   - **0-1 menu shape modifier**
3. Apply the base directives and all selected modifier directives together.
4. If any selected entry declares `special-instructions`, load and apply those instructions before drafting the deliverable.

Keep modifiers minimal. A workflow modifier changes how the recipe is designed/executed without consuming event/use-case context. Seasonal context likewise modifies a base rather than replacing it.

Examples:
- `general-cooking + workflow-meal-prep`
- `weeknight-dinner + workflow-meal-prep`
- `date-night + hot-weather`
- `party-10-25 + hot-weather + service-buffet + setting-outdoor`

## Entry schema
Every base/modifier may use:
- `optimize`
- `avoid`
- `assumptions`
- `options-directives`
- `recipe-directives`
- `common-modifiers`

Any entry may additionally define `special-instructions` when ordinary directives are not sufficient.

### Special-instructions hook
`special-instructions` is an optional extension mechanism. It may:
- load additional authority files;
- define workflow-specific research budgets;
- require/omit deliverable sections;
- add output-format rules;
- add revision/audit checks;
- define interaction defaults;
- define sticky thread behavior.

Rules:
- Most occasions should not need `special-instructions`; use ordinary directives whenever possible.
- Special instructions are binding only while the occasion/modifier that declares them is active.
- Special instructions do not replace the base occasion. They layer on top of it.
- A specialized authority loaded by `special-instructions` wins only for its topic.
- The user's explicit request and safety-critical rules still outrank occasion defaults.
- Never load a special-instruction file merely because project memory contains a prior occasion that used it.

## Composition and conflict resolution
Apply the resolved context in this order:
1. base occasion;
2. workflow modifier;
3. seasonal modifier;
4. setting modifier;
5. service modifier;
6. menu modifier.

Later modifiers may specialize an earlier directive but should not erase it silently. If directives materially conflict:
- prefer the user's explicit request;
- then prefer the more specific modifier for its own axis;
- otherwise preserve both by choosing a method that satisfies both;
- surface a tradeoff only when it materially affects the result.

### Yield and service composition
Yield and immediate service count are separate dimensions when necessary.
- Explicit user yield always wins.
- A modifier must never silently reduce a base occasion's required audience count.
- If the base audience minimum is larger than a workflow batch default, size for the base audience.
- If the base immediate service count is smaller than a workflow batch default, keep the batch yield and state how many portions are served immediately versus stored.
- Example: `date-night + workflow-meal-prep` may yield 10 meal portions while serving 2 now and storing 8.
- Example: `party-10-25 + workflow-meal-prep` must size for the actual party count rather than forcing 10 portions.

### Migration compatibility
Preserve prior taxonomy semantics when old chats/locked decisions are moved into this project.
- If an old thread stores `hot-weather`, `cold-weather`, or `grilling-season` as its base occasion, reinterpret it as `general-cooking` + the corresponding seasonal modifier unless another real base is recoverable from the thread.
- Do not silently reinterpret any other historical base as a different occasion.

---

# Modifiers (optional)

## Workflow modifiers (0-1)

### workflow-meal-prep
- optimize:
  - repeated servings and efficient batch preparation
  - freezer/reheat quality and portionability
  - make-ahead leverage and practical storage
  - nutrient-aware composition without sacrificing cuisine identity
- avoid:
  - recipes whose quality collapses after storage/reheat
  - fragile components that cannot be separated or refreshed
  - batch plans that exceed realistic vessel geometry
  - diet-gimmick substitutions that distort the dish
- assumptions:
  - portions: 10 meal-sized portions unless user/base audience requires another count
  - eating horizon: roughly 2 weeks
  - refrigerator: approximately 3-5 days of portions
  - freezer: remaining portions when freezer-compatible; quality-first horizon measured in months
  - service: stored, reheated, and eaten across repeated meals
  - equipment: use `equipment.md`; split into multiple vessels/batches when geometry requires it
- options-directives:
  - rank freezer/reheat reliability, batch geometry, portionability, make-ahead leverage, and flavor after reheating
  - apply configured general composition and personal food/tolerance defaults
  - preserve cuisine identity; prefer culinary technique over gimmick substitutions
  - include at least one storage/reheat/batch failure-mode guardrail when materially relevant
- recipe-directives:
  - volumetric dishes default to 10 x approximately 2-cup meal portions unless yield composition requires more/fewer
  - component meals use a practical protein + vegetable + starch (or equivalent) portion plan
  - non-volumetric foods use real meal-sized units/servings with a packaging plan
  - require a concrete fridge/freezer strategy when freezer-compatible
  - require a meaningful make-ahead pathway
  - require a first-class Reheat Plan with best method, cue, texture reset, and failure recovery
  - require batch geometry/scaling notes when batch size materially affects cooking
  - require a Nutrition Snapshot by default unless the user explicitly opts out
  - identify the top 3 sodium drivers + 2-4 concrete sodium levers
  - report sodium per 1000 kcal when Calories and Sodium are numeric
- common-modifiers:
  - common: hot-weather, cold-weather, setting-outdoor
- special-instructions:
  - load-files:
    - `meal_prep_health_guidelines.md` - general composition and cooking defaults
    - `meal_prep_personal_health.md` - configured personal ingredient/tolerance defaults
    - `meal_prep_nutrition.md` - numeric nutrition method and provenance
  - activation:
    - explicit references to the established/personalized Meal Prep workflow activate this modifier
    - phrases such as `meal prep`, `meal prep workflow`, `meal prep version`, `use my meal prep defaults`, or equivalent activate this modifier
    - a structurally unmistakable request for the established multi-portion freezer/storage/reheat/nutrition workflow may also activate it
    - `make this healthier`, `less sodium`, `higher protein`, `make extra`, or ordinary leftovers alone do not activate it
  - thread-state:
    - once activated, keep `workflow-meal-prep` active in the current conversation until the user removes it or clearly requests a one-off non-Meal-Prep result
    - record explicit overrides in the locked-decisions ledger
    - project/chat memory may provide recipe history, but must not activate this workflow or its personal constraints by itself
  - interaction:
    - ask at most 2 clarifying questions and only when missing information materially changes correctness
    - otherwise make reasonable assumptions
    - when the user is seeking ideas rather than a repeat, prefer meaningful novelty relative to the last 2-3 recipes in the same conversation
    - if the user provides a recipe/source link, treat it as primary input and triangulate material technique/safety disagreements with 1-3 additional independent sources when browsing is available
  - research-budget:
    - options: candidate pool 15-25; final evidence set 5-8 distinct source families
    - full recipe: candidate pool 10-14; final evidence set 5-7 distinct source families
    - revisions: candidate pool 8-15; final evidence set 5-7 distinct source families
    - all source-quality, deduplication, authenticity, regional-anchor, disagreement-resolution, comment-mining, no-inference, and safety rules still come from `meal_sources.md`
    - the user may request the larger default research budget from `meal_sources.md`
    - when a full recipe is sourced, aim for roughly 6-15 useful in-text footnote markers across externally grounded claims; do not cite ordinary kitchen basics merely to hit a count
    - if browsing is unavailable and sourcing was requested, clearly label an unsourced draft and omit invented footnotes/URLs and the Sources section
  - source-format:
    - when Sources are present, each numbered entry includes source name, URL, source type, supported region when known, and why it was used
    - mark baseline/secondary validation sources as `[secondary]` when applicable
    - raw URLs remain confined to Sources unless the user explicitly requests inline links
  - output-contract:
    - emitted personalized Meal Prep deliverables use plain Markdown and ASCII characters only
    - no emojis or Unicode punctuation
    - temperatures use `425 deg F`, not a degree symbol
    - use U.S. customary units by default; metric may appear when source-derived or precision-critical
    - raw URLs appear only in Sources unless the user explicitly requests inline links
  - food-safety-sourcing:
    - portion large batches into shallow containers or otherwise use a practical rapid-cooling plan rather than leaving a deep hot mass to cool slowly
    - refrigerate near-term portions promptly and freeze portions intended beyond the near-term refrigerator window
    - when a specific mixed-leftover reheat target is appropriate, use 165 deg F and corroborate specific food-safety time/temperature/storage claims with an authoritative source such as USDA/FDA/Cooperative Extension when browsing is available
    - keep safety guidance concise and never invent safety citations
  - revisions:
    - diagnose fresh-cook and stored/reheated performance when relevant
    - build an internal failure-tailored variant matrix comparing material drivers such as ratios, layer depth, covered/uncovered path, reduction endpoint, sequence, salinity, and storage/reheat state before selecting the fix
    - do not repair texture by silently violating a loaded personal constraint
    - updated full recipes retain the Nutrition Snapshot unless explicitly opted out
  - audit:
    - verify batch/portion realism, storage/freezer/reheat coherence, loaded personal constraints, general composition defaults, Nutrition Snapshot presence/provenance unless opted out, sodium requirements, and the ASCII/output contract
  - user-overrides:
    - any non-safety default may be overridden explicitly and the override remains sticky for the thread
    - examples: 6 portions, all-fridge/no-freezer, intentionally rich/traditional version, normally downranked ingredient, omit numeric nutrition, allow a normally avoided protein/starch

## Seasonal modifiers (0-1)

### hot-weather
- optimize:
  - minimal oven use and lighter profiles
  - quick cooking and cold components
- avoid:
  - long simmering and heavy bakes by default
- assumptions:
  - servings: unchanged from base
  - service: food may sit out intermittently
  - duration: 60-180 minutes
  - equipment: grill and no-cook options are preferred when available
- options-directives:
  - prioritize no-cook, grill, quick sear, big salads, and cold sauces
- recipe-directives:
  - include a keep-the-kitchen-cool workflow and safe holding notes
- common-modifiers:
  - common: setting-outdoor, service-grazing-table

### cold-weather
- optimize:
  - warm comfort and warm-hold tolerance
  - leftovers that improve
- avoid:
  - delicate chilled dishes by default
- assumptions:
  - servings: unchanged from base
  - service: served warm, reheating likely
  - duration: flexible
  - equipment: oven and stove are usually acceptable
- options-directives:
  - prioritize soups, stews, braises, baked pastas, and roasts
- recipe-directives:
  - include reheat guidance and day-two notes
- common-modifiers:
  - common: workflow-meal-prep, menu-one-warm-anchor, service-buffet

### grilling-season
- optimize:
  - grill as the primary heat source
  - sides that hold well outdoors
- avoid:
  - heavy indoor cooking while guests are outside
- assumptions:
  - servings: unchanged from base
  - service: outdoor-friendly, often self-serve
  - duration: 90-180 minutes
  - equipment: grill plus basic staging space
- options-directives:
  - propose grillable main plus 2 sturdy sides plus 1 sauce as the default shape
- recipe-directives:
  - include grill timing cues, resting plan, and serve sequence
- common-modifiers:
  - common: setting-outdoor, service-buffet

## Setting modifiers (0-1)

### setting-outdoor
- optimize:
  - outdoor resilience and low fuss service
  - stable textures in heat and wind
- avoid:
  - fragile plated dishes
  - melt-prone items without a cooling plan
- assumptions:
  - servings: unchanged from base
  - service: mixed standing and sitting
  - duration: food may sit out 30-90 minutes
  - equipment: covered trays, shade, and basic serving tools
- options-directives:
  - prioritize grillables, sturdy sides, covered trays, and dips as backups
- recipe-directives:
  - include outdoor service notes on coverage, shade, and timing
- common-modifiers:
  - pairs well with: service-grazing-table, menu-one-warm-anchor

## Service style modifiers (0-1)

### service-buffet
- optimize:
  - fast line speed and easy self-serve
  - low mess and clear portioning
- avoid:
  - integrated drippy sauces in the main serving pan
- assumptions:
  - servings: unchanged from base
  - service: self-serve with obvious serving tools
  - duration: 45-120 minutes of service
  - equipment: serving utensils and stable serving vessels
- options-directives:
  - prioritize foods that spoon or tong cleanly
  - keep sauces on the side by default
- recipe-directives:
  - include portioning guidance and serving-vessel notes
- common-modifiers:
  - pairs well with: menu-one-warm-anchor

### service-grazing-table
- optimize:
  - long-duration nibbling with minimal host intervention
  - mostly room-temp stable items
- avoid:
  - too many hot items competing for attention
- assumptions:
  - servings: unchanged from base
  - service: self-serve, snack-forward
  - duration: 60-120 minutes
  - equipment: boards, small bowls, tongs, napkins
- options-directives:
  - prioritize boards, dips, spreads, and sturdy salads
  - limit to one warm anchor item by default
- recipe-directives:
  - include a staging plan for what goes out first and what comes later
- common-modifiers:
  - pairs well with: menu-board-and-bites, menu-one-warm-anchor

### service-passed-bites
- optimize:
  - bite-size items that hold briefly on a tray
  - steady replenishment in waves
- avoid:
  - items that crumble, leak, or become unpleasant when lukewarm
- assumptions:
  - servings: unchanged from base
  - service: 2-3 waves of bites
  - duration: 45-120 minutes
  - equipment: trays, picks, napkins
- options-directives:
  - prioritize sturdy bites, skewers, and thick dips with carriers
- recipe-directives:
  - include wave timing and batch sizing for each wave
- common-modifiers:
  - pairs well with: menu-board-and-bites

## Menu shape modifiers (0-1)

### menu-board-and-bites
- optimize:
  - board-forward energy with minimal cooking
  - balance of salt, acid, crunch, and something creamy
- avoid:
  - redundant items that crowd the board without adding contrast
- assumptions:
  - servings: unchanged from base
  - service: self-serve, grazing-friendly
  - duration: 60-120 minutes
  - equipment: boards, bowls, knives, spreaders
- options-directives:
  - include acid, crunch, and an optional warm element for contrast
- recipe-directives:
  - include an assembly checklist and timing for room-temperature service
- common-modifiers:
  - pairs well with: service-grazing-table

### menu-one-warm-anchor
- optimize:
  - one hearty warm dish plus supporting cold or room-temp items
  - low coordination during service
- avoid:
  - multiple hot items that require simultaneous attention
- assumptions:
  - servings: unchanged from base
  - service: anchor served warm, supports are cold or room-temp
  - duration: anchor holds well 45-90 minutes
  - equipment: one warming method plus serving vessels
- options-directives:
  - propose one anchor plus 2 supporting sides or snacks
- recipe-directives:
  - include hold and refresh strategy for the anchor
- common-modifiers:
  - pairs well with: service-buffet, service-grazing-table

### menu-dessert-forward
- optimize:
  - stable, portionable desserts with easy self-serve
- avoid:
  - melt-prone desserts without a cooling plan
  - plated-only desserts by default
- assumptions:
  - servings: unchanged from base
  - service: self-serve, grab-and-go portions
  - duration: 60-180 minutes
  - equipment: cutting board, knife, liners, napkins
- options-directives:
  - prioritize bars, cookies, tray cakes, and one optional centerpiece dessert
- recipe-directives:
  - include cutting plan and room-temp storage notes
- common-modifiers:
  - pairs well with: service-grazing-table, service-buffet

---

# General / everyday occasions

## general-cooking
- optimize:
  - direct fit to the user's requested dish and eating experience
  - reliable execution without inventing event-specific constraints
- avoid:
  - adding arbitrary time, service, holding, transport, or crowd assumptions
- assumptions:
  - servings: use explicit user yield; otherwise ordinary home-cooking yield with useful leftovers
  - service: ordinary home meal unless context says otherwise
  - duration: driven by the dish and user constraints
  - equipment: use `equipment.md`
- options-directives:
  - preserve broad format/cuisine diversity when the prompt is broad
  - rank for request fit, technique reliability, and equipment compatibility
- recipe-directives:
  - use the canonical recipe workflow with no extra event-specific service requirements
- common-modifiers:
  - common: workflow-meal-prep, hot-weather, cold-weather, grilling-season

## weeknight-dinner
- optimize:
  - minimal active time and low coordination load
  - reliable results with familiar techniques
- avoid:
  - multi-component timing dependencies that require simultaneous attention
  - recipes requiring lengthy inactive waits that delay eating
- assumptions:
  - servings: 2-4 (adjust to user request)
  - service: family-style or plated, informal
  - duration: active time 20-40 minutes; total 30-60 minutes (longer OK if mostly hands-off)
  - equipment: standard home kitchen
- options-directives:
  - prioritize one-pan, one-pot, and sheet-pan formats
  - include at least one quick-turnaround option (under 30 min active)
- recipe-directives:
  - include pause points and hold notes when applicable
  - include next-day or make-ahead notes by default
- common-modifiers:
  - common: workflow-meal-prep, cold-weather, hot-weather

---

# Two-person occasions (core)

## date-night
- optimize:
  - special feel with controllable timing and doneness
  - clean finish and a strong final flourish
- avoid:
  - high-risk timing where quality collapses if held more than a few minutes
- assumptions:
  - servings: 2
  - service: plated, served promptly
  - duration: active time 45-75 minutes
  - equipment: standard home kitchen
- options-directives:
  - prioritize sear plus pan sauce, composed salad, and one finish element
  - include at least one make-ahead component when possible
- recipe-directives:
  - include a short service plan covering rest, sauce finish, and plating order
- common-modifiers:
  - common: menu-one-warm-anchor

## cozy-night-in
- optimize:
  - comfort and forgiveness
  - leftovers that reheat well
- avoid:
  - fragile textures as the main value proposition
- assumptions:
  - servings: 2
  - service: bowls or family-style, relaxed pacing
  - duration: active time 20-45 minutes, total can be longer
  - equipment: standard home kitchen
- options-directives:
  - prioritize braises, soups, stews, baked pastas, and one-pot comfort foods
- recipe-directives:
  - include hold and reheat notes
  - include pause points where the cook can stop for 15-30 minutes
- common-modifiers:
  - common: workflow-meal-prep, menu-one-warm-anchor, cold-weather

## movie-night
- optimize:
  - low mess eating with minimal utensils
  - food that stays good over 45-90 minutes
- avoid:
  - drippy or splattery formats by default
- assumptions:
  - servings: 2
  - service: couch eating, handheld or bowl food
  - duration: 45-90 minutes of snacking
  - equipment: standard home kitchen
- options-directives:
  - prioritize trays, dips, sturdy handhelds, and oven bakes
- recipe-directives:
  - include a serve window and a keep-warm or keep-crisp strategy
- common-modifiers:
  - common: service-grazing-table, menu-board-and-bites

## cook-together
- optimize:
  - interactive assembly and shared workflow
  - modular steps that split cleanly between two people
- avoid:
  - single-person bottlenecks and constant monitoring
- assumptions:
  - servings: 2
  - service: assembled as you go or assembled at the table
  - duration: active time 45-90 minutes
  - equipment: standard home kitchen
- options-directives:
  - prioritize modular assembly formats such as dumplings, tacos, pizzas, and buildable bowls
- recipe-directives:
  - include split roles suggestions and a clear assembly sequence
- common-modifiers:
  - common: menu-board-and-bites

---

# Small social occasions (4-8)

## small-gathering-4-8
- optimize:
  - low host stress with make-ahead leverage
  - food that holds 30-60 minutes without collapsing
- avoid:
  - single small-pan bottlenecks that do not scale to 8
- assumptions:
  - servings: 4-8
  - service: family-style or casual self-serve
  - duration: 60-120 minutes
  - equipment: standard home kitchen
- options-directives:
  - propose one anchor plus one easy side plus one optional snack or dessert
- recipe-directives:
  - include make-ahead, hold, and reheat plan
  - include scaling notes when the base recipe is not naturally 6-8 servings
- common-modifiers:
  - common: workflow-meal-prep, service-grazing-table, menu-one-warm-anchor

## dinner-with-friends-4-8
- optimize:
  - meal-forward cohesion and predictable timing to the table
  - a clear main plus supporting sides
- avoid:
  - too many components competing for attention
- assumptions:
  - servings: 4-8
  - service: mostly seated, not plated-fussy
  - duration: 90-150 minutes total experience
  - equipment: standard home kitchen
- options-directives:
  - prioritize one main plus one side plus one bright or crunchy element
- recipe-directives:
  - include a simple service plan and a sequencing checklist
- common-modifiers:
  - common: service-buffet, menu-one-warm-anchor

---

# Large social occasions (10-25), adults in their 30s

## party-10-25
- optimize:
  - self-serve friendliness and resilience over 1-2 hours
  - minimal host attention once guests arrive
- avoid:
  - constant stovetop babysitting or plated timing dependencies
- assumptions:
  - servings: 10-25
  - service: mixed standing and sitting, grazing common
  - duration: 90-180 minutes
  - equipment: serving vessels and a keep-warm option if using a warm anchor
- options-directives:
  - propose one warm anchor plus 2-4 grazing components as the default shape
- recipe-directives:
  - include hold and warm strategy
  - include refill triggers and a simple replenishment plan
  - include portion guidance
- common-modifiers:
  - common: workflow-meal-prep, service-grazing-table, service-buffet, menu-one-warm-anchor, setting-outdoor

## cocktail-party-10-25
- optimize:
  - bite-size foods with minimal utensils
  - high snack density and quick replenishment
- avoid:
  - foods requiring cutting or that leak and crumble
- assumptions:
  - servings: 10-25
  - service: standing and circulating
  - duration: 90-180 minutes
  - equipment: trays, picks, napkins, and staging space
- options-directives:
  - prioritize sturdy bites, skewers, and thick dips with carriers
- recipe-directives:
  - include per-person bite estimate
  - include wave timing notes and batch sizing for each wave
- common-modifiers:
  - common: service-passed-bites, menu-board-and-bites, setting-outdoor

## open-house-10-25
- optimize:
  - arrivals in waves with food that is always ready
  - long-duration holding without quality collapse
- avoid:
  - plans that require everything to finish at one moment
- assumptions:
  - servings: 10-25
  - service: grazing with periodic refresh
  - duration: 2-4 hours
  - equipment: staging area plus a rewarm option if using warm items
- options-directives:
  - prioritize room-temp stable items plus one warm item that can be refreshed repeatedly
- recipe-directives:
  - include refresh cycle cadence and batch sizing guidance
  - include swap strategy for trays and dips
- common-modifiers:
  - common: workflow-meal-prep, service-grazing-table, menu-one-warm-anchor, setting-outdoor

---

# Logistics-heavy occasions

## bring-over
- optimize:
  - travel resilience with minimal on-site dependency
  - predictable serving at destination
- avoid:
  - dishes that require specialty equipment at destination
- assumptions:
  - servings: variable
  - service: served at destination with limited setup
  - duration: 30-90 minutes from pack to serve
  - equipment: cooking happens at home; destination equipment unknown
- options-directives:
  - prioritize room-temp excellent dishes or dishes with simple reheat paths
  - prioritize sturdy containers and low-spill formats
- recipe-directives:
  - include packing, transport, and reheat or serve instructions that are explicit and brief
- common-modifiers:
  - common: workflow-meal-prep, hot-weather, cold-weather, setting-outdoor

## picnic
- optimize:
  - room-temp stability and low mess
  - easy packing and minimal utensils
- avoid:
  - cold-chain risk without explicit cooler planning
- assumptions:
  - servings: variable
  - service: no reheating, minimal utensils
  - duration: 60-180 minutes
  - equipment: cooler optional but not assumed
- options-directives:
  - prioritize wraps and sandwiches, sturdy salads, baked items, fruit, and crunchy snacks
- recipe-directives:
  - include pack order, serve notes, and keep-cold guidance when needed
- common-modifiers:
  - common: hot-weather, setting-outdoor

## tailgate
- optimize:
  - hearty handheld eating and warm-hold with minimal gear
  - robust flavors and easy serving
- avoid:
  - foods requiring cutting or fussy plating
- assumptions:
  - servings: variable
  - service: handheld, self-serve
  - duration: 90-180 minutes
  - equipment: coolers, foil pans, and limited heat source are common
- options-directives:
  - prioritize dips, tray bakes, chili-like anchors, and sturdy handhelds
- recipe-directives:
  - include a keep-warm plan using foil, thermos, cooler, or warmers
- common-modifiers:
  - common: workflow-meal-prep, service-buffet, menu-one-warm-anchor, setting-outdoor

## limited-infrastructure
- optimize:
  - forgiving technique with minimal tools
  - prep-ahead leverage and simple execution
- avoid:
  - recipes requiring precise temperatures or many separate components
- assumptions:
  - servings: variable
  - service: simple family-style or self-serve
  - duration: flexible
  - equipment: cooking happens on-site with limited or unknown tools
- options-directives:
  - prioritize one-pot and one-pan meals, foil packets, simple roasts, and modular meals
- recipe-directives:
  - include fallbacks for missing tools and simplified workflow alternatives
- common-modifiers:
  - common: workflow-meal-prep, menu-one-warm-anchor
