# Recipe Template (Canonical)
# [Recipe Title]

This is the canonical full-recipe format for the shared recipe engine. Apply ordinary occasion directives from `occasions.md`, any conditional sections required by active `special-instructions`, and any narrow request-scoped authorities loaded by `instructions.md`.

Do not emit internal occasion-resolution labels or instruction-file commentary unless useful to the user.

## Title & Overview
[3 to 5 sentences: flavor, eating experience, origin/context when relevant, and make-ahead characteristics when relevant. If the dish has a common non-English name, include it and a useful transliteration when supported by research.]

When `workflow-meal-prep` is active:
- include 1 to 2 concise sentences on why the recipe works for repeated batch/storage/reheat use;
- include a concise qualitative explanation of why the meal composition fits the loaded general health/composition guidance;
- do not make medical claims or invent nutrition numbers.

When general health/composition guidance is loaded only because the user explicitly requested a healthier version, include the relevant qualitative rationale without implying that Meal Prep is active.

## Tags
Use lowercase, hyphen-separated tags from `tags.md` according to its count/selection rules.
- Recipe target: 3 to 8 tags.
- Example: `tags: [main, weeknight, quick, pasta, vegetarian]`

## Yield & Timing
- **Yield:** [servings; default to an ordinary home-cooking yield with useful leftovers unless user/occasion says otherwise]
- **Active Prep:** [time]
- **Inactive Prep / Hands-Off / Rest:** [time]
- **Cook:** [time]
- **Total:** [time]
- **Make-ahead:** [what holds, what freezes, thaw/reheat summary]

Apply active occasion assumptions and the yield/service composition rules in `instructions.md`.

When `workflow-meal-prep` is active, default yield/portioning and fridge/freezer horizon come from that workflow unless overridden. State the actual portioning plan rather than blindly using cups for every food.

## Grocery List
Every ingredient appears exactly once under the correct category. Omit empty categories.

### Produce
- [item]

### Pantry
- [item]

### Dairy & Eggs
- [item]

### Proteins
- [item]

### Spices & Oils
- [item]

## Equipment & Tools
Use `equipment.md` inventory names. Critical tools first; optional/substitutes second. Apply vessel material/color calibration and substitution hierarchy where relevant.

## Ingredients
List in use order.
- Use U.S. customary units by default.
- Include metric when source-derived or precision-critical.
- For small/precision-critical items such as salt, yeast, or leavener, include grams when useful.
- Mark advance prep with **[pre-prep]**.
- Specify drained/rinsed, salted/unsalted, cut size, and other state details when method-relevant.

## Allergy & Dietary Notes
Include only relevant items.
- **Contains:** [actual allergens/diet-relevant ingredients]
- **Easy swaps:** [swap -> texture/flavor impact -> technique change]
- **Hard swaps:** [swap -> why it breaks method -> alternative]
- **Cross-contact note:** [only if relevant]

When active special instructions or request-scoped authorities load dietary/composition guidance, include only useful concrete toggles. Examples include low-sodium, high-protein, low-FODMAP, gluten-free/lower-gluten, dairy/lactose, or current-thread constraints. Do not list irrelevant toggles merely because an authority is available.

## Quick Overview
4 to 8 tight bullets. Bold the label before each colon.
- **What you are making:** [final dish/eating experience]
- **Texture and doneness cues:** [key endpoints]
- **Workflow:** [order of operations; include parallel work when useful]
- **Make-ahead:** [what can happen early]
- **Primary risks:** [1 to 3 likely failure points]

When `workflow-meal-prep` is active also include:
- **Portioning:** [how the batch becomes individual meals]
- **Reheat:** [best reheat path + texture reset]

## Gather & Stage
Complete before Step 1.
- Measure and group ingredients by phase.
- Set out required equipment; line/grease/preheat as directed.
- Complete timing-sensitive **[pre-prep]**.
- **Checkpoint:** everything needed for Step 1 is ready.

## Instructions
Minimum 4 numbered steps. Avoid large paragraphs. Prefer cues first, clock second.

Formatting rules:
- Each numbered step has at least one bullet with sub-bullets.
- Across the recipe, include at least 2 conditional recovery branches: *If X -> do Y -> cue it's fixed.*
- Bold scan-critical cooking actions, heat settings, and temperatures; do not bold whole sentences.
- Italics may mark optional/conditional notes.
- Inline code may be used for exact settings/literals when useful.
- Every heat step includes heat/temp + time range + sensory cue.
- Specify size/thickness when timing depends on geometry.
- Final step includes a taste-adjust loop: acid -> salt -> heat -> herbs, adapted as appropriate to the dish.
- Apply any active occasion-specific output contract. `workflow-meal-prep` requires ASCII-only emitted deliverables and `deg F` temperatures.

Example skeleton:
1. [Phase]
   - [Main action]
     - [order/cut/geometry details]
     - **Heat/temp**, X to Y minutes, until [cue].
     - *While this runs: [parallel task].*
     - **Checkpoint:** [cue].
     - *If [symptom] -> [fix] -> [recovery cue].*

2. [Next phase]
   - [Main action]
     - [reduction/emulsion/texture details]
     - **Checkpoint:** [cue].

3. [Next phase]
   - [Main action]
     - [doneness cue]
     - **Checkpoint:** [cue].

4. Finish and taste-adjust
   - [combine/rest/finish]
     - [final texture cue]
     - Taste-adjust: acid -> salt -> heat -> herbs.
     - **Checkpoint:** [final endpoint].

### Optional Instruction Table
Use only when timing/parallel work benefits from a grid.

| Step | Task | Heat/Temp | Time Range | Sensory Cues | Tools/Notes |
|---:|---|---|---:|---|---|
| 1 |  |  |  |  |  |
| 2 |  |  |  |  |  |

## Common Issues
Short, non-duplicative bullets.
- **[Symptom]:** [Cause] -> [simple fix] -> [quick check]

## Make-Ahead Notes
Include as a standard full-recipe section; keep it concise when make-ahead is not a major concern.
- Fridge plan:
  - Stop after Step [#] / component [name]
  - Cool/store: [method/container]
  - Holds: [duration when reliably sourced or conservative]
  - Serve/reheat: [method + cue + texture reset]
- Freezer plan when appropriate:
  - Best freeze point
  - Portioning/packaging
  - Freeze quality horizon
  - Thaw path
  - Reheat + texture reset

When `workflow-meal-prep` is active, this section is required and must implement its actual 3-5-day fridge split plus remaining freezer plan when freezer-compatible, unless the user overrides freezer use.

## Reheat Plan
Required when an active occasion/special instruction requires first-class reheat handling; optional otherwise when useful.

`workflow-meal-prep` requires:
- **Best method:** [microwave/stovetop/oven/air fryer] -> [power/temp] -> [time range] -> until [cue]
- **Texture reset:** [how to restore sauce/crispness/moisture] -> [cue]
- **Acceptable alternate:** [if useful]
- *If [common reheat failure] -> [fix] -> [recovery cue].*

## Troubleshooting
2 to 4 entries total.
- [Symptom] -> [Likely cause] -> [Primary fix] -> [Recovery cue]

### Optional Troubleshooting Table
| Symptom | Likely Cause | Quick Fix |
|---|---|---|
| Too salty | reduced too far / salty inputs | dilute or add unsalted bulk; rebalance |
| Too watery | crowding / insufficient evaporation | reduce uncovered / widen vessel |
| Split emulsion | excess heat / addition too fast | cool slightly; re-emulsify gradually |

## Geometry Notes
Include when relevant. An active occasion may make this required.
- Pan/pot size:
- Target layer depth/thickness:
- Crowding rule:

`workflow-meal-prep`: required when batch size materially affects cooking.

## Scaling & Batch Size
Include when useful. An active occasion may make this required.
- Scaling notes
- Batch strategy
- Pan/vessel swaps
- Whether doubling requires multiple pans/batches rather than simply longer cook time

`workflow-meal-prep`: required when workflow/default yield differs materially from source recipes.

## Nutrition Snapshot (per serving)
Include when explicitly requested by the user or required by an active specialized authority.

`workflow-meal-prep` requires this section by default unless the user explicitly opts out. An ordinary recipe with a direct numeric nutrition request also uses this section and `meal_prep_nutrition.md`, but does **not** inherit Meal Prep batch, personal-health, freezer, or formatting defaults.

Numeric nutrition is governed exclusively by `meal_prep_nutrition.md` whenever that authority is loaded.

### Nutrition Label Core
| Nutrient | Amount per serving | %DV | Source basis |
|---|---:|---:|---|
| Calories | [x or NA] | -- | [...] |
| Total fat | [x g or NA] | [x% or --] | [...] |
| -- Saturated fat | [x g or NA] | [x% or --] | [...] |
| -- Trans fat | [x g or NA] | -- | [...] |
| -- Monounsaturated fat | [x g or NA] | -- | [...] |
| -- Polyunsaturated fat | [x g or NA] | -- | [...] |
| Cholesterol | [x mg or NA] | [x% or --] | [...] |
| Sodium | [x mg or NA] | [x% or --] | [...] |
| Total carbohydrate | [x g or NA] | [x% or --] | [...] |
| Dietary fiber | [x g or NA] | [x% or --] | [...] |
| -- Soluble fiber | [x g or NA] | -- | [...] |
| -- Insoluble fiber | [x g or NA] | -- | [...] |
| Total sugars | [x g or NA] | -- | [...] |
| Added sugars | [x g or NA] | [x% or --] | [...] |
| Protein | [x g or NA] | -- | [...] |

### Vitamins and Minerals
#### Fat-Soluble Vitamins
| Nutrient | Amount per serving | %DV | Source basis |
|---|---:|---:|---|
| Vitamin A | [x mcg RAE or NA] | [x% or --] | [...] |
| Vitamin D | [x mcg or NA] | [x% or --] | [...] |
| Vitamin E | [x mg or NA] | [x% or --] | [...] |
| Vitamin K | [x mcg or NA] | [x% or --] | [...] |

#### Water-Soluble Vitamins
| Nutrient | Amount per serving | %DV | Source basis |
|---|---:|---:|---|
| Vitamin C | [x mg or NA] | [x% or --] | [...] |
| Thiamin (B1) | [x mg or NA] | [x% or --] | [...] |
| Riboflavin (B2) | [x mg or NA] | [x% or --] | [...] |
| Niacin (B3) | [x mg NE or NA] | [x% or --] | [...] |
| Pantothenic acid (B5) | [x mg or NA] | [x% or --] | [...] |
| Vitamin B6 | [x mg or NA] | [x% or --] | [...] |
| Folate (B9) | [x mcg DFE or NA] | [x% or --] | [...] |
| Vitamin B12 | [x mcg or NA] | [x% or --] | [...] |
| Choline | [x mg or NA] | [x% or --] | [...] |

#### Minerals
| Nutrient | Amount per serving | %DV | Source basis |
|---|---:|---:|---|
| Potassium | [x mg or NA] | [x% or --] | [...] |
| Calcium | [x mg or NA] | [x% or --] | [...] |
| Phosphorus | [x mg or NA] | [x% or --] | [...] |
| Magnesium | [x mg or NA] | [x% or --] | [...] |
| Iron | [x mg or NA] | [x% or --] | [...] |
| Zinc | [x mg or NA] | [x% or --] | [...] |
| Copper | [x mg or NA] | [x% or --] | [...] |
| Manganese | [x mg or NA] | [x% or --] | [...] |
| Selenium | [x mcg or NA] | [x% or --] | [...] |

### Nutrition Assumptions
[Only when needed.]

### Nutrition Provenance
- Primary source stack: [...]
- Calculator assistance: [none or tool]
- Unresolved fields: [...]

## Special Notes
Optional unless an active occasion requires something here.
- Storage/reheat: [brief]
- Serving ideas: [brief]
- Sodium notes: [when sodium is materially relevant, identify the main drivers and practical levers without inventing numbers]

When `workflow-meal-prep` is active:
- **Sodium notes:** top 3 sodium drivers + 2 to 4 concrete levers, even when numeric nutrition contains `NA`.
- **Sodium density:** when Calories and Sodium are numeric, report sodium per 1000 kcal.

## Variations
Default full-recipe behavior: include 2 to 4 meaningful variants, each 1 to 2 sentences with no sub-bullets. Omit only when the user explicitly requests a stripped/companion format or variations would be nonsensical. Variations must not silently violate locked constraints or active specialized authorities.

## Safety & Correctness Notes
Optional; use only for relevant safety/correctness deviations and source them appropriately.

## Sources
Numbered sources matching in-text `[n]` markers. Do not invent sources.

Default full-recipe source entry format:
1. [Creator or Source Name - Title](https://example.com) [type: YouTube; region: TBD; why: firsthand method demo]
2. [Regional Site - Title](https://example.com) [type: blog; region: TBD; why: technique specifics]
3. [Forum Thread - Title](https://example.com) [type: forum; region: TBD; why: failure modes + corrections]
4. [Authoritative Reference - Title](https://example.com) [type: authoritative; region: TBD; why: safety/cooling/reheat fact]

Apply any active occasion-specific URL/output contract. `workflow-meal-prep` requires the richer source metadata specified in its `special-instructions`. Add a nutrition tool source only when that tool materially contributed to displayed nutrition values.

Do not place raw URLs elsewhere unless the user explicitly requested inline links.
