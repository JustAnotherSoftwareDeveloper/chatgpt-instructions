# [Recipe Title]

## Title & Overview
[Write 3 to 5 sentences on flavor and what the dish is like to eat. Include origin/context if relevant. Also include 1 to 2 sentences on why this is generally healthy (qualitatively) and why it is make-ahead friendly. Keep it appetizing and concise. Avoid health numbers unless verified per nutrition_calculation_method.md.]

## Tags
[List 3 to 8 tags. Use lowercase, hyphen-separated tags from `tags.md` when available.]
- Prefer: 1 to 2 course/cuisine tags, 0 to 1 diet tag (only if user asked), 1 method tag, 1 time/effort tag, 0 to 2 key-ingredient tags.
- Example: `tags: [main, weeknight, quick-and-easy, pasta, vegetarian]`

## Yield & Timing
- **Yield:** [servings; default: yields leftovers unless user requests otherwise]
- **Active Prep:** [time]
- **Inactive Prep / Hands-Off / Rest:** [time]
- **Cook:** [time]
- **Total:** [time]
- **Make-ahead:** [what holds X days; what freezes Y months; how to thaw and reheat]

## Grocery List
Rule: Every ingredient appears exactly once in Grocery List under the correct category.
Use the aisle/category taxonomy from `recipe_template.md` (or your canonical grocery taxonomy file) if it is stricter than the headings below.

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
[List critical gear and helpful alternates; be specific about sizes/materials.]
- [e.g., 12-in stainless skillet; 5 to 6 qt Dutch oven; sheet pan 13x18; fine-mesh sieve]
- [optional or substitute tools]

## Ingredients
[List in use order. Use U.S. units; include metric in parentheses only if taken from a source.
For small or precision-critical items, provide grams in parentheses.
Mark advance-prep items with **[pre-prep]**.
Specify drained/rinsed where relevant (canned beans, canned fish).
Specify salted vs unsalted where relevant (broth/stock, butter).]
- [ingredient, amount] **[pre-prep]**
- [ingredient, amount]
- [ingredient, amount]

## Allergy & Dietary Notes
[Only include what is relevant for this recipe. Be concrete; do not be exhaustive.]
- **Contains:** [e.g., dairy, wheat/gluten, egg, soy, nuts, sesame, fish/shellfish, alcohol]
- **Easy swaps (keep technique intact):**
  - [Swap] -> [Impact on texture/flavor] -> [Any technique change]
- **Hard swaps (not recommended / major change):**
  - [Swap] -> [Why it breaks the method] -> [If you must, what to do instead]
- **Diet toggles (optional; only if relevant to the dish):**
  - Low-sodium: [concrete swaps + technique notes]
  - High-protein: [concrete swaps + technique notes]
  - Low-FODMAP: [concrete swaps + technique notes]
  - Gluten-free: [concrete swaps + technique notes]
  - Dairy-free: [concrete swaps + technique notes]
- **Cross-contact note (optional):**
  - [If relevant, e.g., shared fryer, store-bought sauces, spice blends]

## Quick Overview
[4 to 8 bullets. For each bullet, the main point before the colon must be bolded. Keep bullets tight and action-oriented.]
- **What you are making:** [1 sentence; what the final dish is and how it should eat]
- **Texture and doneness cues:** [1 sentence; the most important "until..." endpoints]
- **Workflow:** [1 sentence; order of operations; include at least one "While X cooks, do Y"]
- **Make-ahead:** [1 sentence; what can be done ahead and what improves with resting/chilling]
- **Reheat plan:** [1 sentence; best method + cue its ready; how to restore texture]
- **Primary risks:** [1 sentence; 1 to 3 likely failure points]

## Instructions
[Main flow is numbered steps: 1., 2., 3., 4. (minimum). Avoid big paragraphs; keep to bullets and short sentences.
Prefer cues first, clock second. The final step should always include a taste-adjust loop.
Do NOT repeat template rules or meta-instructions in the final recipe output.]

Formatting and nesting rules
- Main flow is numbered steps: 1., 2., 3., 4., and onward.
- Each numbered step must include nesting:
  - At least 1 bullet with sub-bullets.
  - Across the whole recipe, include at least 2 branch sub-bullets in the form: *If X -> do Y -> cue it's fixed.*
- Bold actual substance and settings the cook scans for (examples; not exhaustive):
  - Bold cooking verbs and actions such as: **Bake**, **Roast**, **Simmer**, **Saute**, **Boil**, **Sear**, **Brown**, **Deglaze**, **Whisk**, **Fold**, **Reduce**, **Rest**, **Blend**, **Chill**, **Freeze**.
  - Bold heat and temperature phrases: **medium heat**, **medium-high heat**, **low heat**, **425 deg F**.
  - Optionally bold one key endpoint phrase per step (keep it to one).
  - Do not bold whole sentences; bold phrases only.
- Use italics for optional/conditional notes that can be skipped.
- Use inline code only for exact literals/settings when needed: `425 deg F`, `medium-high`, `1/2-in`.

Heat-step minimum detail
- Whenever heat is involved, include: heat level or oven temp, a time range, and at least one sensory cue.
- Prefer: "X to Y minutes, until [cue]" rather than exact minutes.
- When cook time depends on size, specify thickness/size in the same step.

Step skeleton
1. [Phase title]
   - [Main bullet: what to do]
     - [Sub-bullets: prep details affecting cook time (size/thickness), order of additions]
     - [Sub-bullets: **Heat**/**Oven** + time range + cue; include the "until..." endpoint]
     - *[While this runs: parallel task]*
     - **Checkpoint:** You are ready to proceed when [cue].
     - *If [symptom], then [primary fix]; cue it's fixed.*

2. [Next phase title]
   - [Main bullet]
     - [Sub-bullets: **Heat**/**Oven** + time range + cue]
     - [Sub-bullets: reduction/consistency test if relevant (what it should look like)]
     - **Checkpoint:** You are ready to proceed when [cue].
     - *If [symptom], then [primary fix]; cue it's fixed.*

3. [Next phase title]
   - [Main bullet]
     - [Sub-bullets: **Heat**/**Oven** + time range + cue; doneness cue for any protein]
     - **Checkpoint:** You are ready to proceed when [cue].

4. Finish and taste-adjust
   - [Main bullet: combine/rest as needed]
     - [Sub-bullets: final texture cue; whether to stop early if reheating later]
     - Taste-adjust loop: acid -> salt -> heat -> herbs.
     - **Checkpoint:** Final dish is [key endpoint cue].

### Optional: Instruction Table
[Use when timing/parallel tasks benefit from a grid. Keep cues concrete.]

| Step | Task | Heat/Temp | Time Range | Sensory Cues | Tools/Notes |
|---:|---|---|---:|---|---|
| 1 | [task] | [heat/temp] | [range] | [cue] | [notes] |
| 2 | [task] | [heat/temp] | [range] | [cue] | [notes] |

## Common Issues
[Short bullets for things that commonly go wrong + simple fixes/checks. Keep tight; do not duplicate Troubleshooting below.]
- **[Symptom]:** [Cause] -> [Simple fix] -> [Quick check]
- **[Symptom]:** [Cause] -> [Simple fix] -> [Quick check]

## Make-Ahead Notes
[Call out what can be done 1 to 3 days ahead; what freezes; thaw + reheat cues.]
- Fridge plan:
  - Stop after Step [#]: [how to cool/store; container guidance]
  - Holds: [X days]
  - Serve/Reheat: [method] until [cue]; then [texture reset + re-season note]
- Freezer plan:
  - Best freeze point: Step [#] or component [name]
  - Portioning: [portion size and container guidance]
  - Freeze: [Y months]
  - Thaw: [method]
  - Reheat: [method] until [cue]; then [texture reset + re-season note]

## Reheat Plan
[First-class reheat guidance. Keep concrete and cue-driven. If multiple reheat methods are viable, name the "best" and list 1 to 2 acceptable alternates.]
- **Best method:** [microwave / stovetop / oven / air fryer] -> [power/temp] -> [time range] -> until [cue]
- **Texture reset:** [how to restore crispness/sauce/creaminess] -> [cue]
- *If [common reheat failure], then [fix] -> [cue it's fixed].*

## Troubleshooting
[2 to 4 bullets total. Use the arrow format below.]
- [Symptom] -> [Likely cause] -> [Primary fix] -> [Recovery cue]
- [Symptom] -> [Likely cause] -> [Primary fix] -> [Recovery cue]

## Troubleshooting Table
[Optional. Use when it clarifies common failure modes.]

| Symptom | Likely Cause | Quick Fix |
|---|---|---|
| [Too salty] | [Over-salted or reduced too far] | [Add unsalted starch; splash of water/stock; acid to balance] |
| [Too watery] | [Crowded pan / insufficient reduction] | [Reduce uncovered; finish hotter; small slurry if appropriate] |
| [Split emulsion] | [Too hot / fat added too fast] | [Whisk in tsp warm water off heat; re-emulsify slowly] |

## Geometry Notes
[Include when relevant.]
- Pan/pot size used:
- Target thickness / layer depth:
- Crowding rule:

## Scaling & Batch Size
[Optional. How to halve/double; how geometry changes time; pan alternatives; burner/oven constraints.]
- Scaling notes:
- Batch strategy:
- Pan swaps:

## Nutrition Snapshot (per serving)
[Follow nutrition_calculation_method.md.

Rules:
- Never invent numbers.
- Select calculator via Order of Operations + Coverage Check.
- Report required fields first; include optional fields only if the chosen calculator provides explicit numeric values.
- Use "NA" exactly for missing/ambiguous fields, or when a calculator shows "--" or "~" for that field.
- Field-by-field source attribution is required (single-calculator is fine; multi-calculator mixing must be explicit).
- Include "Nutrition Assumptions" only when needed (ambiguous conversions/substitutions that materially affect nutrition).]

- calories: [x or NA]
- protein g: [x or NA]
- fiber g: [x or NA]
- fat g (sat g): [x (x) or NA]
- sodium mg: [x or NA]
- added sugar g: [x or NA] (optional)
- potassium mg: [x or NA] (optional)
- magnesium mg: [x or NA] (optional)
- calcium mg: [x or NA] (optional)
- iron mg: [x or NA] (optional)
- zinc mg: [x or NA] (optional)

Nutrition Assumptions (only when needed)
- [assumption]
- [assumption]

Field sources (required)
- [field group] -> [calculator name]
- [field group] -> [calculator name]

## Special Notes
[Optional. Keep brief.]
- Storage & reheat: [brief; include temps for safe reheating only when explicitly citing a safety source]
- Serving ideas: [brief list of sides, sauces, garnishes]
- Sodium notes: [top 3 sodium drivers + 2 to 4 concrete levers, even if nutrition is NA]

## Variations
[Include 2 to 4 variations that make it feel like a meaningfully different dish or use-case. Avoid micro-toggles.
Each variation must be 1 to 2 sentences in a single short paragraph (no sub-bullets).]
1. **[Variation name]:** [1 to 2 sentence description; call out the key change and how it changes the eating experience; include citations if derived from sources]
2. **[Variation name]:** [1 to 2 sentence description]
3. **[Variation name]:** [1 to 2 sentence description]

## Safety & Correctness Notes
[Optional. Only if needed. Document deviations from a traditional source for safety/correctness; explain "why" briefly.]

## Sources
[Add numbered sources that match any in-text footnotes. Use Markdown links for text + URL.
Do not place raw URLs outside this section; cite with [n] in-text.]
1. [Creator or Source Name - Title](https://example.com) [type: YouTube; region: TBD; why: firsthand method demo]
2. [Regional Site - Title](https://example.com) [type: blog; region: TBD; why: technique specifics]
3. [Forum Thread - Title](https://example.com) [type: forum; region: TBD; why: failure modes + corrections]
4. [Authoritative Reference - Title](https://example.com) [type: authoritative; region: TBD; why: safety/cooling/reheat fact]
5. [Nutrition Calculator - Tool Name](https://example.com) [type: tool; why: nutrition snapshot]

In-text citation examples to use above where appropriate
- Bake at 425 deg F for 18 to 22 minutes for 1-in pieces [2].
- Bloom the spice paste 30 to 45 seconds until shiny, not browned [1 @2:41].
