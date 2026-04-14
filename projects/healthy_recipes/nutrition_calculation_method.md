# nutrition_calculation_method.md

## Goal
Generate a "Nutrition Snapshot (per serving)" using a source-driven, calculator-assisted workflow:
- Authoritative nutrition data comes from ingredient-level sources when available.
- Calculator tools are execution aids and cross-checks, not authorities.
- Field-level exhaustion before NA; never snapshot-level failure.
- Source attribution is required per field or per tightly grouped row set.

---

## Definitions

### Required fields — core label (always attempt per serving)
- Calories
- Total fat
  - Saturated fat
  - Trans fat
  - Monounsaturated fat
  - Polyunsaturated fat
- Cholesterol
- Sodium
- Total carbohydrate
  - Dietary fiber
    - Soluble fiber
    - Insoluble fiber
  - Total sugars
  - Added sugars
- Protein

### Priority vitamins and minerals (always attempt when sourceable)
- Vitamin A
- Vitamin D
- Vitamin C
- Vitamin B12
- Folate (B9)
- Potassium
- Calcium
- Iron
- Magnesium

### Extended vitamins and minerals (attempt when reasonably sourceable)
- Vitamin E
- Vitamin K
- Thiamin (B1)
- Riboflavin (B2)
- Niacin (B3)
- Pantothenic acid (B5)
- Vitamin B6
- Choline
- Phosphorus
- Zinc
- Copper
- Manganese
- Selenium

Operational note:
- Manufacturer Nutrition Facts panels often omit fat sub-type rows, soluble/insoluble fiber, and many voluntary vitamins and minerals.
- When those fields are absent and no better source tier exists for the ingredient, treat them as unresolved rather than inferred.

If a field is not resolvable after source-tier escalation:
- Amount = NA
- %DV = --
- Core label rows: keep the row visible with NA; do not omit it.
- Vitamins and Minerals rows in the template tables: keep the row visible with NA; do not omit it.
- Fat sub-type rows (Trans fat, Monounsaturated fat, Polyunsaturated fat): keep visible; %DV is always -- regardless of whether amount is resolved.
- Fiber sub-type rows (Soluble fiber, Insoluble fiber): keep visible; %DV is always -- regardless of whether amount is resolved.
- A recipe-level nutrient row is numeric only if all included ingredient contributions for that nutrient are numeric in the same display unit/form.
- If any included ingredient remains unresolved for a nutrient after source-tier exhaustion, the recipe-level nutrient row becomes NA. Do not publish a partial sum.

### "Source"
Any database record, product page, package label text, or calculator tool that provides numeric per-serving or per-gram nutrient data for a specific ingredient.

---

## Source Hierarchy

### Tier 1: USDA FoodData Central — Foundation Foods
- Default for raw, generic, minimally processed, and commodity-style ingredients.
- URL: https://fdc.nal.usda.gov/
- Use Foundation Foods records preferentially over SR Legacy or FNDDS when a matching record exists.

### Tier 2: Official manufacturer Nutrition Facts sources
- Default for branded packaged foods.
- Acceptable sources in order of preference:
  1. Manufacturer product page (current, exact SKU)
  2. Manufacturer PDF / downloadable specification sheet
  3. Package label text if explicitly provided in source material
- Do not use a manufacturer source that is clearly outdated or does not match the exact product used.
- Field-level fallback within a single branded ingredient: if the matched Tier 2 source provides some required fields but omits others (e.g., lists macros but not Potassium), descend to the next tier only for the missing fields. Record the tier used per field or per tightly grouped field set in the Source basis column.

### Tier 3: USDA FoodData Central — Branded Foods
- Fallback for branded products when the official manufacturer source is absent, stale, or not readily accessible.
- URL: https://fdc.nal.usda.gov/

### Tier 4: USDA FoodData Central — FNDDS / SR Legacy / other USDA prepared-food entries
- For generic prepared foods, common mixed items, and institutional-style food records.
- Use when no better ingredient-level record exists.

### Tier 5: USDA yield / portion-correction sources
- Yield factors, drained-weight factors, edible-portion factors, cooked-yield factors.
- These are conversion aids, not primary nutrient authorities.
- Document any yield or drained-weight correction applied in Nutrition Assumptions.

### Tier 6: Public recipe calculators
- MyFoodData Recipe Nutrition Calculator: https://tools.myfooddata.com/recipe-nutrition-calculator
- HappyForks Recipe Analyzer: https://happyforks.com/analyzer
- Verywell Fit Recipe Nutrition Analyzer: https://www.verywellfit.com/recipe-nutrition-analyzer-4157076
- Use only as:
  - Fast-entry interfaces for summing ingredient-level data
  - Gap-fill helpers when a Tier 1-5 source is unavailable for a specific field
  - Cross-check tools to validate ingredient-level sums
- Calculator output does not outrank a cleaner ingredient-level source stack.
- If a calculator result materially diverges from the source-derived line-item total: prefer the source-derived total; note the mismatch in Nutrition Provenance only if it materially affected the displayed result.

### Tier 7: Premium / future path
- NCC / NCCDB or equivalent licensed research database.
- Mentioned as a future upgrade path; not required as a public default.

---

## No-Hard-Stop Rule

A workflow-level hard stop is not permitted.
- If the first public calculator tried fails or cannot produce a required field: escalate to the next listed Tier 6 tool.
- If all public calculators fail: continue with ingredient-level source derivation (Tiers 1-5).
- If one nutrient field is unresolvable for one or more ingredients: continue computing all other fields; set only the unresolvable field to NA.
- The entire Nutrition Snapshot section must never be dropped because a single tool failed or a single field could not be resolved.
- Only the specific unresolved field becomes NA after source-tier exhaustion for that field.

---

## Daily Values Reference

Use current FDA Daily Values (2020 revision, 2,000 kcal basis).

| Nutrient              | Daily Value            |
| --------------------- | ---------------------- |
| Total fat             | 78 g                   |
| Saturated fat         | 20 g                   |
| Trans fat             | no DV established      |
| Monounsaturated fat   | no FDA DV              |
| Polyunsaturated fat   | no FDA DV              |
| Cholesterol           | 300 mg                 |
| Sodium                | 2,300 mg               |
| Total carbohydrate    | 275 g                  |
| Dietary fiber         | 28 g                   |
| Soluble fiber         | no FDA DV              |
| Insoluble fiber       | no FDA DV              |
| Added sugars          | 50 g                   |
| Protein               | 50 g                   |
| Vitamin A             | 900 mcg RAE            |
| Vitamin C             | 90 mg                  |
| Vitamin D             | 20 mcg                 |
| Vitamin E             | 15 mg alpha-tocopherol |
| Vitamin K             | 120 mcg                |
| Thiamin (B1)          | 1.2 mg                 |
| Riboflavin (B2)       | 1.3 mg                 |
| Niacin (B3)           | 16 mg NE               |
| Pantothenic acid (B5) | 5 mg                   |
| Vitamin B6            | 1.7 mg                 |
| Folate (B9)           | 400 mcg DFE            |
| Vitamin B12           | 2.4 mcg                |
| Choline               | 550 mg                 |
| Potassium             | 4,700 mg               |
| Calcium               | 1,300 mg               |
| Phosphorus            | 1,250 mg               |
| Magnesium             | 420 mg                 |
| Iron                  | 18 mg                  |
| Zinc                  | 11 mg                  |
| Copper                | 0.9 mg                 |
| Manganese             | 2.3 mg                 |
| Selenium              | 55 mcg                 |

%DV display rules:
- Calories: never show %DV; use -- always.
- Total sugars: never show %DV; use -- always.
- Trans fat: no DV established by FDA; use -- always.
- Monounsaturated fat: no FDA DV; use -- always.
- Polyunsaturated fat: no FDA DV; use -- always.
- Soluble fiber: no FDA DV; use -- always.
- Insoluble fiber: no FDA DV; use -- always.
- Protein: use -- unless the display context explicitly supports showing it.
- All other nutrients: compute and show when the amount is numeric; round to nearest whole percentage.
- If the amount is NA: %DV = -- (do not compute from NA).
- Formula: %DV = (amount / Daily Value) x 100, rounded to nearest whole number.

---

## Workflow

### A. Confirm serving definition
- Confirm total recipe yield (servings count).
- Confirm what constitutes one serving (e.g., "1 of 16 portions, approx. 85 g each").
- If serving size is ambiguous: choose the most typical consumer portion and document it in Nutrition Assumptions.

### B. Parse recipe into ingredient rows
- List each ingredient with its quantity as stated in the recipe.
- Identify whether each ingredient is a simple whole ingredient, a branded packaged product, or a custom sub-component (sauce, rub, filling, etc.).
- Also classify each ingredient by its role in the recipe for the purpose of Added sugars derivation:
  - Role A (discrete added sweetener without a declared Added sugars value): ingredient is used primarily to sweeten the recipe and is itself the sweetener source — honey, maple syrup, sugar, brown sugar, powdered sugar, agave, molasses, corn syrup, flavored syrups. If the field source does not provide a separate Added sugars value, all sugar contributed by Role A ingredients counts as added sugars.
  - Role B (unsweetened whole food): plain vegetables, plain fruit, plain legumes, plain grains, plain dairy (milk, plain yogurt, plain kefir), plain eggs, plain meat, plain fish, plain nuts, plain seeds, water, plain vinegar, plain citrus juice, other items where sugars are intrinsic. No added sugars contribution from Role B ingredients.
  - Role C (ingredient with declared Added sugars): any ingredient whose Tier 2 or Tier 3 Nutrition Facts source explicitly states an Added sugars value, including sweetened sauces, flavored yogurt, granola, bars, and other packaged foods. Use the declared Added sugars value directly; do not infer. Role C takes precedence over Role A whenever a declared Added sugars value exists.
  - Role D (processed/packaged ingredient without declared added sugars): use NA for the Added sugars row for this ingredient; do not infer from Total sugars.
- If an ingredient's role is ambiguous, treat it as Role D and set Added sugars to NA for that ingredient.

### C. Match each ingredient to the best source tier
- For each ingredient row, start at the highest-priority tier appropriate to that ingredient type, then descend only as needed:
  - Simple whole ingredient -> start at Tier 1.
  - Branded packaged ingredient -> start at Tier 2.
  - Generic prepared or mixed food without a brand-specific source -> start at Tier 4.
  - Yield / drained / edible corrections -> apply Tier 5 only as a correction layer after a primary nutrient source has been selected.
- Record which tier was used for each ingredient.
- Field-level fallback: if the matched tier provides some nutrient fields but not others, descend to the next tier only for the missing fields. Do not re-match the whole ingredient row.
- If no tier yields a match for a specific nutrient field: set that field to NA for that ingredient and continue with remaining fields.

### D. Normalize quantity only as far as needed for that source
- Prefer exact grams when already present in the recipe.
- Otherwise use source-native serving units if the source provides a precise serving mapping (e.g., "1 medium egg", "1 cup cooked oats").
- Only force gram conversion when needed for arithmetic or when the source requires it.
- Ambiguous conversions (e.g., "1 large onion") must use the most typical US retail size and be disclosed in Nutrition Assumptions.
- Before any arithmetic, normalize nutrient units/forms to the display basis used in healthy_template.md and the Daily Values Reference.
- Use these display bases for form-sensitive nutrients: Vitamin A = mcg RAE; Folate (B9) = mcg DFE; Niacin (B3) = mg NE; Vitamin E = mg alpha-tocopherol.
- Do not mix unlike nutrient forms or unlike units within the same row.
- If a source reports a nutrient in a different form or unit and the exact conversion is not available from the source or another authoritative reference, set that nutrient to NA for that ingredient instead of coercing it.

### E. Apply yield / drained / edible corrections when materially relevant
- Use Tier 5 correction factors for ingredients where drained weight, cooked yield, or edible portion materially changes the nutrient contribution.
- Document any correction applied in Nutrition Assumptions.

### F. Compute per-ingredient nutrient contributions
- For each ingredient: (ingredient quantity / source serving size) x source nutrient per serving = ingredient contribution.
- Only compute and carry forward contributions that have been normalized to the row's display unit/form.
- Sum contributions across all ingredients for each nutrient field.

### G. Sum recipe totals
- Total recipe nutrient = sum of all normalized per-ingredient contributions for that nutrient only when every included ingredient has a numeric value for that nutrient.
- If one or more included ingredients remain unresolved for that nutrient after source-tier exhaustion, set the recipe-level nutrient to NA.
- Do not publish partial sums that silently exclude unresolved ingredient contributions.

### H. Divide by servings
- Per-serving nutrient = total recipe nutrient / servings count.

### I. Populate the Nutrition Snapshot tables
- Enter values into the Nutrition Label Core and Vitamins and Minerals tables per the format in healthy_template.md.
- Compute %DV per the Daily Values Reference above.
- Source basis column: state the dominant source tier or specific source name for each nutrient row or tightly grouped row set.

### J. Calculator use (optional accelerator / cross-check)
- If a calculator tool accelerates steps F-H: enter source-resolved ingredient quantities, not raw recipe text, where the source provides grams.
- If a calculator tool cross-checks: compare its per-serving totals to source-derived totals; prefer source-derived if they diverge materially.
- If a calculator tool fills a gap for a specific field where no Tier 1-5 source was found: use it only if the tool output matches the row's display unit/form or can be normalized exactly; record the tool as the source basis for that field.
- Tool citations appear in Sources (type: tool) only when the tool materially contributed to the displayed Nutrition Snapshot.

---

## Sub-Recipe and Custom Component Handling

For sauces, marinades, rubs, dressings, mixed fillings, and batch-prepped subcomponents:
- Compute the sub-component's nutrition independently using steps A-H above.
- Roll the sub-component's per-serving contribution into the parent recipe as an ingredient-level contribution.
- Do not rely on a public recipe calculator to correctly infer custom sub-recipe losses or retained portions.
- For retained-portion adjustments (e.g., marinade where only a fraction is consumed): apply the retention fraction before rolling up and document the assumption in Nutrition Assumptions.

---

## Conflict Resolution

### Generic whole ingredients
Prefer USDA Foundation Foods (Tier 1) over calculator output (Tier 6) when both are available.

### Branded packaged foods
- If Tier 2 and Tier 3 directly conflict and the Tier 2 source is clearly current and exact-match: prefer Tier 2.
- Otherwise: prefer Tier 3 over Tier 6.

### Generic prepared foods
Prefer USDA FNDDS or prepared-food entries (Tier 4) over public calculator guesses (Tier 6).

### Calculator mismatch
Prefer source-derived totals over calculator output when they diverge materially. Document the mismatch briefly in Nutrition Provenance only if it materially affected the displayed result.

---

## Source Policy
- Source attribution is required per displayed nutrient row or per tightly grouped row set.
- Cite the source tier or specific source (e.g., "USDA Foundation FDC #123456", "manufacturer label", "HappyForks").
- Tool citations appear in Sources (type: tool) only when the tool materially contributed to the Nutrition Snapshot.
- Nutrition source attribution is governed by this file; generic recipe-source rules in meal_sources.md do not govern the nutrition section.

---

## Reporting Format
Follow the table format in healthy_template.md (Nutrition Label Core + Vitamins and Minerals tables + Nutrition Provenance).
- NA = amount could not be resolved after source-tier escalation.
- -- = %DV is not shown for this nutrient or amount is NA.
- Keep Source basis column entries compact.
- Do not invent values; do not approximate without attribution.
