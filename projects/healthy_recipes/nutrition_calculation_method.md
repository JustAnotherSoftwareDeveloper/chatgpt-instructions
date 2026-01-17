# nutrition_calculation_method.md

## Goal
Generate a "Nutrition Snapshot (per serving)" for a recipe with:
- Calculators that are easy to execute (no login, low friction).
- A single-calculator primary path plus fallbacks (order of operations).
- No two-calculator matching requirement.
- "Added sugar" and "Potassium" are NOT required fields (they are optional if available).
- Clear independence definition (for when fallbacks are used).
- An up-front conversion/coverage check so we do not waste time on a calculator that cannot produce the needed fields.

## Definitions

### Required fields (always attempt)
Report per serving:
- calories
- protein g
- fiber g
- fat g (sat g)
- sodium mg

### Optional fields (include only if calculator provides them)
- added sugar g
- potassium mg
- magnesium mg
- calcium mg
- iron mg
- zinc mg
(Additional micronutrients may be included if consistently present in the chosen calculator output.)

### "Calculator"
A public recipe nutrition tool that:
- allows ingredient + quantity entry
- outputs per-serving nutrition
- can be executed without requiring an account

### Independence
Independence is only relevant when we must fall back or mix sources.
Two calculators are considered "independent" if:
- they are operated by different organizations AND
- they are not obvious white-label embeds of the same calculator engine AND
- they are not merely different pages on the same site sharing the same output pipeline

Independence DOES NOT require a different underlying nutrient database (that is usually unknowable and would make execution brittle).

## Order of Operations (Calculator Priority)

### Calculator A (default): MyFoodData Recipe Nutrition Calculator
- Why: Easy, free, supports many nutrients (including sodium, potassium, and "added sugars" fields in its nutrition label UI).
- Execution notes:
  - It supports "100 grams" style serving sizes and custom grams by multiplying quantities.
  - It states that missing data "--" is treated as 0 in its totals, which can undercount some nutrients in edge cases. Treat any displayed "--" field as NA in our report (do not convert it to 0 unless the UI explicitly outputs a numeric 0).

URL:
- https://tools.myfooddata.com/recipe-nutrition-calculator

### Calculator B (fallback): HappyForks Recipe Analyzer
- Why: Extremely low friction (paste ingredient lines), outputs a broad nutrient panel including minerals (potassium, sodium, calcium, magnesium, iron, zinc are typically present), and marks missing values with "~".
- Execution notes:
  - If a nutrient is missing (shown as "~"), record NA for that nutrient (do not infer).
  - This tool may not provide "added sugar" as a distinct field; treat Added sugar as NA unless explicitly present.

URL:
- https://happyforks.com/analyzer

### Calculator C (fallback): Verywell Fit Recipe Nutrition Analyzer
- Why: Common, no-login, generally stable for basic label fields.
- Execution notes:
  - Use this primarily for core macros + sodium when A/B are blocked.
  - Minerals coverage may be limited; treat missing fields as NA.

URL:
- https://www.verywellfit.com/recipe-nutrition-analyzer-4157076

## Up-Front Field Conversion and Coverage Check (Mandatory)

Before using any calculator:

1) Confirm serving definition
- The recipe MUST declare:
  - total yield (servings count) and
  - what constitutes a serving (e.g., "1 of 20 bites")

2) Confirm ingredient measurability
For each ingredient line:
- Prefer grams provided explicitly.
- If grams are not present, convert to grams BEFORE entering into any calculator.
- If a conversion is ambiguous (e.g., "1 large onion"), choose the most typical US retail size and document the assumption in a short "Nutrition Assumptions" note.

3) Calculator coverage check
- Choose the first calculator in the priority list that can output ALL required fields.
- If a calculator cannot output a required field (or returns "--" / "~" / blank for it), move to the next calculator.
- If no calculator can provide a required field, set that field to NA and proceed with the rest (do not block the entire snapshot).

4) Field availability check for optional nutrients
- Optional nutrients are only reported if the chosen calculator provides explicit numeric values.
- If not present, record NA for that optional nutrient (do not infer).

## Calculation Procedure

1) Select calculator via Order of Operations + Coverage Check.

2) Enter ingredients
- Use grams whenever the calculator permits.
- If only volume measures are accepted, use the pre-converted gram equivalent by selecting a "grams" serving size if available, or by selecting the closest listed serving and scaling quantity.

3) Set servings
- Set the calculator servings to match the recipe yield.

4) Record outputs
- Record required fields first.
- Then record optional fields that are present and numeric.

5) Field-by-field source attribution (required)
For each nutrient field, record which calculator produced it.
- If all fields came from one calculator, the whole Nutrition Snapshot can cite a single source.
- If you had to mix calculators because one lacked a subset of fields, cite per-field (or group fields by calculator).

## Reporting Format in Recipe Output

### Nutrition Snapshot (per serving)
Include only numeric fields; do not add ranges unless the calculator itself provides a range.

If a field is missing:
- Use "NA" exactly.

Example (per serving):
- calories: 142
- protein g: 3.9
- fiber g: 3.6
- fat g (sat g): 5.3 (0.6)
- sodium mg: 2
- potassium mg: NA
- added sugar g: NA
- magnesium mg: 53
- calcium mg: 48
- iron mg: 1.1
- zinc mg: 0.75

### Nutrition Assumptions (only when needed)
If any ingredient required an ambiguous conversion or substitution to fit a calculator:
- Add a short bullet list immediately below the snapshot, describing only the assumptions that materially affect nutrition.

## Source Policy
- Always cite the calculator used (link in recipe Sources).
- If field-by-field mixing occurred, cite both calculators.

## Notes / Rationale
This method is intentionally execution-forward:
- It prioritizes producing a usable label without blocking on cross-calculator agreement.
- It prevents silent nonsense by forcing a coverage check and using NA when a field cannot be produced.
- It defines independence narrowly enough to be practical.
