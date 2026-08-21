# Recipe Template (Canonical)
# [Recipe Title]

This is the canonical full-recipe format for both profiles. Apply sections marked **Meal Prep only** only when `meal-prep` is active. Do not emit profile labels or internal instructions unless useful to the user.

## Title & Overview
[3 to 5 sentences: flavor, eating experience, origin/context when relevant, and make-ahead characteristics when relevant. If the dish has a common non-English name, include it and a useful transliteration when supported by the research.]

**Meal Prep only:** include 1 to 2 concise sentences on why the recipe fits the profile (batch/storage/reheat/composition) without making medical claims or inventing nutrition numbers.

## Tags
Use lowercase, hyphen-separated tags from `tags.md` according to its count/selection rules.
- Recipe target: 3 to 8 tags.
- Example: `tags: [main, weeknight, quick, pasta, vegetarian]`

## Yield & Timing
- **Yield:** [servings]
- **Active Prep:** [time]
- **Inactive Prep / Hands-Off / Rest:** [time]
- **Cook:** [time]
- **Total:** [time]
- **Make-ahead:** [what holds, what freezes, thaw/reheat summary]

**Meal Prep only:** default yield/portioning and fridge/freezer horizon come from `meal_prep.md` unless overridden. State the actual portioning plan rather than blindly writing cups.

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
- Mark advance prep with **[pre-prep]**.
- Specify drained/rinsed, salted/unsalted, cut size, and other state details when method-relevant.

## Allergy & Dietary Notes
Include only relevant items.
- **Contains:** [actual allergens/diet-relevant ingredients]
- **Easy swaps:** [swap -> texture/flavor impact -> technique change]
- **Hard swaps:** [swap -> why it breaks method -> alternative]
- **Cross-contact note:** [only if relevant]

**Meal Prep only:** when useful, include concrete toggles that follow `meal_prep_health_guidelines.md` and `meal_prep_personal_health.md`, such as low-sodium, high-protein, low-FODMAP, gluten-free/lower-gluten, dairy/lactose, or other current-thread constraints. Do not list irrelevant toggles merely because the profile exists.

## Quick Overview
4 to 8 tight bullets. Bold the label before each colon.
- **What you are making:** [final dish/eating experience]
- **Texture and doneness cues:** [key endpoints]
- **Workflow:** [order of operations; include parallel work when useful]
- **Make-ahead:** [what can happen early]
- **Primary risks:** [1 to 3 likely failure points]
- **Meal Prep only - Portioning:** [how the batch becomes individual meals]
- **Meal Prep only - Reheat:** [best reheat path + texture reset]

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

**Meal Prep only:** this section is required and must implement the actual profile portioning/fridge/freezer plan unless the user overrides freezer use.

## Reheat Plan
**Required in Meal Prep; optional in Standard when useful.**
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
Include when relevant; **required in Meal Prep when batch size materially affects cooking.**
- Pan/pot size:
- Target layer depth/thickness:
- Crowding rule:

## Scaling & Batch Size
Include when useful; **required in Meal Prep when profile/default yield differs materially from source recipes.**
- Scaling notes
- Batch strategy
- Pan/vessel swaps
- Whether doubling requires multiple pans/batches rather than simply longer cook time

## Nutrition Snapshot (per serving)
**Meal Prep default full-recipe section.** Include unless the user explicitly opts out of numeric nutrition. Governed exclusively by `meal_prep_nutrition.md`. Omit this entire section in Standard unless the user explicitly requests nutrition.

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
Optional in Standard. In Meal Prep, sodium notes are required.
- Storage/reheat: [brief]
- Serving ideas: [brief]
- **Meal Prep sodium notes:** top 3 sodium drivers + 2 to 4 concrete levers, even when numeric nutrition contains `NA`.
- **Meal Prep sodium density:** when Calories and Sodium are numeric, report sodium per 1000 kcal.

## Variations
Default full-recipe behavior: include 2 to 4 meaningful variants, each 1 to 2 sentences with no sub-bullets. Omit only when the user explicitly requests a stripped/companion format or variations would be nonsensical. Variations must not silently violate locked constraints or Meal Prep personal defaults.

## Safety & Correctness Notes
Optional; use only for relevant safety/correctness deviations and source them appropriately.

## Sources
Numbered sources matching in-text `[n]` markers. Do not invent sources.

Standard full-recipe source entry format:
1. [Creator or Source Name - Title](https://example.com) [type: YouTube; region: TBD; why: firsthand method demo]
2. [Regional Site - Title](https://example.com) [type: blog; region: TBD; why: technique specifics]
3. [Forum Thread - Title](https://example.com) [type: forum; region: TBD; why: failure modes + corrections]
4. [Authoritative Reference - Title](https://example.com) [type: authoritative; region: TBD; why: safety/cooling/reheat fact]

**Meal Prep only:** follow the URL/ASCII contract in `meal_prep.md`. Each source entry should still identify source name, URL, source type, supported region when known, and why it was used. Add a nutrition tool source only when that tool materially contributed to displayed nutrition values.

Do not place raw URLs elsewhere unless the user explicitly requested inline links.
