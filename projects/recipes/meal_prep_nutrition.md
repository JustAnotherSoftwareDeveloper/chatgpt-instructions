# Meal Prep Nutrition Calculation Method

## Goal
Generate a reliable `Nutrition Snapshot (per serving)` for Meal Prep recipes using source-driven, calculator-assisted arithmetic.

Principles:
- Ingredient-level authoritative sources are preferred.
- Calculators are execution aids/cross-checks, not authorities.
- Never invent nutrient values.
- Exhaust source tiers per field before using `NA`.
- One unresolved nutrient does not invalidate the entire snapshot.
- Source attribution is required per row or tightly grouped row set.

**Default scope:** Full recipes in Meal Prep profile include the Nutrition Snapshot unless the user explicitly opts out. Standard-profile recipes do not inherit this requirement. This file also governs numeric nutrition whenever the user explicitly requests it.

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
- Vitamin E, Vitamin K
- Thiamin (B1), Riboflavin (B2), Niacin (B3), Pantothenic acid (B5), Vitamin B6
- Choline
- Phosphorus, Zinc, Copper, Manganese, Selenium

If a field remains unresolved after source-tier escalation:
- Amount = `NA`
- %DV = `--`
- Keep required rows visible.
- Do not publish a partial recipe-level sum that silently excludes unresolved ingredient contributions.

A recipe-level nutrient can be numeric only when every included ingredient contribution for that nutrient is numeric in compatible units/forms.

---

## Source hierarchy
### Tier 1 — USDA FoodData Central Foundation Foods
Default for raw/generic/minimally processed ingredients.
- Source: https://fdc.nal.usda.gov/

### Tier 2 — official manufacturer nutrition source
Default for branded packaged foods. Prefer exact current SKU:
1. manufacturer product page;
2. manufacturer PDF/spec sheet;
3. package label text explicitly provided.

Field-level fallback is allowed: use Tier 2 for declared fields and descend only for omitted fields.

### Tier 3 — USDA FoodData Central Branded Foods
Fallback for branded products when manufacturer data is unavailable/stale.
- Source: https://fdc.nal.usda.gov/

### Tier 4 — USDA FNDDS / SR Legacy / other prepared-food entries
For generic prepared/mixed foods without a better ingredient-level match.

### Tier 5 — USDA yield/portion corrections
Use for drained weight, edible portion, cooked yield, or similar conversion corrections. These modify quantities; they are not the primary nutrient authority.

### Tier 6 — public recipe calculators
- MyFoodData Recipe Nutrition Calculator: https://tools.myfooddata.com/recipe-nutrition-calculator
- HappyForks Recipe Analyzer: https://happyforks.com/analyzer
- Verywell Fit Recipe Nutrition Analyzer: https://www.verywellfit.com/recipe-nutrition-analyzer-4157076

Use only to:
- accelerate arithmetic;
- cross-check source-derived totals;
- fill a specific unresolved field when Tiers 1-5 fail.

Calculator output never outranks a cleaner ingredient-level source stack.

### Tier 7 — premium/future data source
A licensed research-grade database such as NCC/NCCDB may be used when available. It is an optional future upgrade path, not a public-workflow requirement.

---

## No-hard-stop rule
- Tool/calculator failure never causes the full Nutrition Snapshot to disappear.
- If one calculator fails, try another only when useful; otherwise continue with ingredient-level derivation.
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
Confirm recipe yield and what constitutes one serving. If ambiguous, choose a plausible meal-prep serving and disclose it in Nutrition Assumptions.

### B) Parse ingredients
For each ingredient:
- record recipe quantity;
- classify as generic whole ingredient, branded packaged product, generic prepared food, or custom sub-component;
- classify Added Sugars role:
  - Role A: discrete added sweetener without declared Added sugars -> its sugars count as added sugar;
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

### D) Normalize quantities and nutrient forms
Prefer exact grams when available; otherwise use precise source-native serving units.
- Only force gram conversion when arithmetic/source format requires it.
- For an ambiguous household-size ingredient (for example, `1 large [produce item]`), use the most typical U.S. retail size supported by the selected source and disclose the assumption in Nutrition Assumptions.

Normalize display forms:
- Vitamin A = mcg RAE
- Folate = mcg DFE
- Niacin = mg NE
- Vitamin E = mg alpha-tocopherol

Do not mix incompatible nutrient forms. If an authoritative conversion is unavailable, use `NA` for that ingredient/field.

### E) Apply yield/drained/edible corrections
Use documented yield factors when materially relevant and disclose them.

### F) Compute ingredient contributions
For each nutrient:
`ingredient quantity / source serving size * source nutrient per serving`

### G) Sum recipe totals
Only sum a nutrient when every included ingredient contribution is resolved numerically. Otherwise the recipe-level field is `NA`.

### H) Divide by servings
Per-serving nutrient = recipe total / servings.

### I) Populate `recipe_template.md` Nutrition Snapshot
Include Source basis for each row or tightly grouped set.

### J) Calculator use
If a calculator helps:
- feed it source-resolved quantities where practical;
- compare its result against source-derived arithmetic;
- prefer source-derived totals when materially different;
- cite the tool only if it materially contributed to displayed values.

---

## Sub-recipes and retained fractions
For sauces, marinades, dressings, rubs, fillings, or other custom components:
- calculate the component independently;
- roll the consumed fraction into the parent recipe;
- for marinade or other partial-retention cases, apply a documented retention assumption rather than pretending all liquid is consumed.

---

## Conflict resolution
- Generic ingredients: Tier 1 beats calculator output.
- Branded products: current exact Tier 2 beats Tier 3; Tier 3 beats Tier 6.
- Generic prepared foods: Tier 4 beats calculator guesses.
- Calculator mismatch: prefer ingredient-level source-derived arithmetic and note material mismatches only when they affected the display.

---

## Reporting format
Use the Meal Prep conditional Nutrition Snapshot in `recipe_template.md`.

Required conventions:
- `NA` = unresolved after source-tier exhaustion.
- `--` = %DV not displayed or amount is `NA`.
- Keep mandatory rows visible.
- Include a `Source basis` column.
- Include Nutrition Assumptions only when needed.
- Include Nutrition Provenance summarizing primary source stack and any calculator assistance.
- Never approximate silently.
