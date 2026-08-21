# Meal Prep Nutrition Calculation Method

## Goal
Generate a reliable `Nutrition Snapshot (per serving)` using source-driven, calculator-assisted arithmetic when this authority is loaded by an active occasion special instruction.

Principles:
- Ingredient-level authoritative sources are preferred.
- Calculators are execution aids/cross-checks, not authorities.
- Never invent nutrient values.
- Exhaust source tiers per field before using `NA`.
- One unresolved nutrient does not invalidate the entire snapshot.
- Source attribution is required per row or tightly grouped row set.

**Activation:** `occasions.md` loads this file through `workflow-meal-prep` `special-instructions`. Full recipes under that workflow include the Nutrition Snapshot unless the user explicitly opts out. Outside that workflow, use this file only when the user explicitly requests numeric nutrition or another active occasion explicitly loads it.

---

## Required fields
### Core label rows
Always attempt:
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

### Priority vitamins/minerals
Always attempt when sourceable:
- Vitamin A
- Vitamin D
- Vitamin C
- Vitamin B12
- Folate (B9)
- Potassium
- Calcium
- Iron
- Magnesium

### Extended vitamins/minerals
Attempt when reasonably sourceable:
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

Operational rules:
- Manufacturer Nutrition Facts panels often omit fat sub-types, soluble/insoluble fiber, and many voluntary vitamins/minerals. Treat absent fields as unresolved unless a lower source tier resolves them.
- If a field remains unresolved after source-tier escalation: Amount = `NA`; %DV = `--`.
- Keep required rows visible even when `NA`.
- Fat sub-type rows and fiber sub-type rows always use `%DV = --`.
- A recipe-level nutrient may be numeric only when every included ingredient contribution for that nutrient is numeric in compatible units/forms.
- If any included ingredient remains unresolved for a nutrient after source-tier exhaustion, the recipe-level row becomes `NA`; do not publish a partial sum.

---

## Source hierarchy
### Tier 1 - USDA FoodData Central Foundation Foods
Default for raw/generic/minimally processed ingredients.
- Source: https://fdc.nal.usda.gov/

### Tier 2 - official manufacturer nutrition source
Default for branded packaged foods. Prefer exact current SKU:
1. manufacturer product page;
2. manufacturer PDF/spec sheet;
3. package label text explicitly provided.

Do not use a manufacturer source that is clearly outdated or mismatched.

Field-level fallback is allowed: if Tier 2 provides some required fields but omits others, descend only for missing fields. Record the tier used per field or tightly grouped field set.

### Tier 3 - USDA FoodData Central Branded Foods
Fallback for branded products when manufacturer data is unavailable/stale.
- Source: https://fdc.nal.usda.gov/

### Tier 4 - USDA FNDDS / SR Legacy / other prepared-food entries
For generic prepared/mixed foods without a better ingredient-level match.

### Tier 5 - USDA yield/portion corrections
Use for drained weight, edible portion, cooked yield, or similar conversion corrections. These modify quantities; they are not primary nutrient authorities.

### Tier 6 - public recipe calculators
- MyFoodData Recipe Nutrition Calculator: https://tools.myfooddata.com/recipe-nutrition-calculator
- HappyForks Recipe Analyzer: https://happyforks.com/analyzer
- Verywell Fit Recipe Nutrition Analyzer: https://www.verywellfit.com/recipe-nutrition-analyzer-4157076

Use only to:
- accelerate arithmetic;
- cross-check source-derived totals;
- fill a specific unresolved field when Tiers 1-5 fail.

Calculator output never outranks a cleaner ingredient-level source stack.

### Tier 7 - premium/future data source
A licensed research-grade database such as NCC/NCCDB may be used when available. It is an optional future upgrade path, not a public-workflow requirement.

---

## No-hard-stop rule
- Tool/calculator failure never causes the full Nutrition Snapshot to disappear.
- If the first public calculator tried fails and calculator use is still useful, escalate to another Tier 6 tool.
- If calculators fail, continue with ingredient-level derivation from Tiers 1-5.
- If one nutrient remains unresolved, set only that nutrient to `NA` and continue.
- Do not fabricate missing micronutrients simply to complete the table.

---

## Daily Values
Use current FDA Daily Values on a 2,000 kcal basis:

| Nutrient | Daily Value |
|---|---:|
| Total fat | 78 g |
| Saturated fat | 20 g |
| Cholesterol | 300 mg |
| Sodium | 2300 mg |
| Total carbohydrate | 275 g |
| Dietary fiber | 28 g |
| Added sugars | 50 g |
| Protein | 50 g |
| Vitamin A | 900 mcg RAE |
| Vitamin C | 90 mg |
| Vitamin D | 20 mcg |
| Vitamin E | 15 mg alpha-tocopherol |
| Vitamin K | 120 mcg |
| Thiamin (B1) | 1.2 mg |
| Riboflavin (B2) | 1.3 mg |
| Niacin (B3) | 16 mg NE |
| Pantothenic acid (B5) | 5 mg |
| Vitamin B6 | 1.7 mg |
| Folate (B9) | 400 mcg DFE |
| Vitamin B12 | 2.4 mcg |
| Choline | 550 mg |
| Potassium | 4700 mg |
| Calcium | 1300 mg |
| Phosphorus | 1250 mg |
| Magnesium | 420 mg |
| Iron | 18 mg |
| Zinc | 11 mg |
| Copper | 0.9 mg |
| Manganese | 2.3 mg |
| Selenium | 55 mcg |

%DV display:
- Calories: `--`
- Total sugars: `--`
- Trans fat: `--`
- Monounsaturated fat: `--`
- Polyunsaturated fat: `--`
- Soluble fiber: `--`
- Insoluble fiber: `--`
- Protein: `--` unless the context explicitly supports a %DV
- If amount is `NA`, %DV is `--`
- Otherwise `%DV = amount / DV * 100`, rounded to nearest whole percent.

---

## Workflow
### A) Define serving
Confirm recipe yield and what constitutes one serving. If ambiguous, choose the most plausible serving for the active occasion and disclose it in Nutrition Assumptions.

### B) Parse ingredients
For each ingredient:
- record recipe quantity;
- classify as generic whole ingredient, branded packaged product, generic prepared food, or custom sub-component;
- classify Added Sugars role:
  - Role A: discrete added sweetener without declared Added sugars -> all sugar contributed by the sweetener counts as added sugar;
  - Role B: unsweetened whole food -> no added-sugar contribution;
  - Role C: product with declared Added sugars -> use declared value;
  - Role D: processed/packaged item without declared Added sugars -> Added sugars = `NA` for that ingredient.
- Ambiguous role defaults to Role D.

### C) Match source tier
- Generic whole ingredient -> Tier 1 first.
- Branded product -> Tier 2 first.
- Generic prepared/mixed food -> Tier 4 first.
- Apply Tier 5 only as a correction layer.
- Descend per missing field rather than rematching the whole ingredient unnecessarily.
- If no tier yields a match for a nutrient field, set that field to `NA` for that ingredient and continue.

### D) Normalize quantities and nutrient forms
Prefer exact grams when already present; otherwise use precise source-native serving units.
- Only force gram conversion when arithmetic/source format requires it.
- For an ambiguous household-size ingredient, use the most typical U.S. retail size supported by the selected source and disclose the assumption in Nutrition Assumptions.

Normalize display forms:
- Vitamin A = mcg RAE
- Folate = mcg DFE
- Niacin = mg NE
- Vitamin E = mg alpha-tocopherol

Do not mix incompatible nutrient forms. If an authoritative conversion is unavailable, use `NA` for that ingredient/field.

### E) Apply yield/drained/edible corrections
Use documented Tier 5 yield factors when materially relevant and disclose them.

### F) Compute ingredient contributions
For each nutrient:
`ingredient quantity / source serving size * source nutrient per serving`

Only compute contributions normalized to the display unit/form.

### G) Sum recipe totals
Only sum a nutrient when every included ingredient contribution is resolved numerically. Otherwise the recipe-level field is `NA`.

### H) Divide by servings
Per-serving nutrient = recipe total / servings.

### I) Populate `recipe_template.md` Nutrition Snapshot
Include Source basis for each row or tightly grouped set and compute %DV using the table above.

### J) Calculator use
If a calculator helps:
- feed it source-resolved ingredient quantities where practical;
- compare its result against source-derived arithmetic;
- prefer source-derived totals when materially different;
- if a calculator fills a specific Tier 1-5 gap, use it only when units/forms can be normalized exactly;
- cite the tool only if it materially contributed to displayed values.

---

## Sub-recipes and retained fractions
For sauces, marinades, dressings, rubs, fillings, or other custom components:
- calculate the component independently using the same workflow;
- roll the consumed fraction into the parent recipe;
- for marinade or other partial-retention cases, apply a documented retention assumption rather than pretending all liquid is consumed.

---

## Conflict resolution
- Generic ingredients: Tier 1 beats calculator output.
- Branded products: current exact Tier 2 beats Tier 3; Tier 3 beats Tier 6.
- Generic prepared foods: Tier 4 beats calculator guesses.
- Calculator mismatch: prefer ingredient-level source-derived arithmetic and note material mismatches only when they affected the display.

---

## Source policy
- Source attribution is required per displayed nutrient row or tightly grouped row set.
- Cite the source tier or specific source (for example USDA Foundation FDC identifier, manufacturer label, or named calculator).
- Tool citations appear in Sources only when the tool materially contributed to the Nutrition Snapshot.
- Nutrition source attribution is governed by this file; generic recipe-source rules in `meal_sources.md` do not govern nutrient data selection.

---

## Reporting format
Use the Nutrition Snapshot table format in `recipe_template.md`.

Required conventions:
- `NA` = unresolved after source-tier exhaustion.
- `--` = %DV not displayed or amount is `NA`.
- Keep mandatory rows visible.
- Include a `Source basis` column.
- Include Nutrition Assumptions only when needed.
- Include Nutrition Provenance summarizing primary source stack and any calculator assistance.
- Never approximate silently.
