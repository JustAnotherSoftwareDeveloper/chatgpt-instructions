# Meal Prep Profile

## Purpose
This file defines the Meal Prep profile layered on the shared Recipes engine. It does not replace cuisine research, occasions, equipment rules, options/recipe formatting, revisions, or auditing.

Meal Prep optimizes for repeated servings, practical batch preparation, storage/freezing, reheat quality, nutrient-aware composition, and the configured personal food/tolerance defaults.

## Activation
Profile selection is governed by `instructions.md`. Do not activate this profile merely because the user requests one healthy change, one batch-size change, or one dietary adjustment.

When active, consult:
- `meal_prep_health_guidelines.md` for general composition defaults;
- `meal_prep_personal_health.md` for configured personal tolerances/avoidances;
- `meal_prep_nutrition.md` for numeric nutrition.

## Baseline meal-prep behavior
Unless the user overrides:
- Target 10 meal-sized portions.
- Plan roughly a 2-week eating horizon.
- Reserve approximately 3 to 5 days of portions for refrigeration and freeze the remainder when the dish is freezer-compatible.
- Treat freezer performance and reheat quality as first-class design constraints.
- Include at least one meaningful make-ahead pathway.
- For batch-oriented recipes, include a concrete freeze point, portion/packaging plan, thaw path, best reheat method, and texture-reset step.
- Prefer recipes that portion cleanly and tolerate repeated storage/reheat without becoming watery, greasy, grainy, rubbery, or mushy.
- Do not force cup-based portions onto foods that are not naturally portioned by volume.

### Portioning
- Volumetric dishes: default to 10 meal portions, commonly around 2 cups each when that represents a real meal.
- Component meals: define protein + vegetable + starch portions or another practical per-meal assembly.
- Non-volumetric items: define 10 meal-sized units/servings and a packaging strategy.
- A meal-prep portion is a real meal, not a snack, unless requested otherwise.

## Meal-prep research budget
All source-quality and research-method rules remain governed by `meal_sources.md`.

For Meal Prep, the evidence set may use the historical Meal Prep budget when the extra work of freezer/reheat/nutrition validation would otherwise create disproportionate research overhead:
- Options: candidate pool 15-25; final evidence set 5-8 distinct source families.
- Full recipe: candidate pool 10-14; final evidence set 5-7 distinct source families.
- Revisions: candidate pool 8-15; final evidence set 5-7 distinct source families.

Deep-research behaviors still apply: independent evidence, source-family deduplication, disagreement resolution, regional anchors where applicable, and failure-mode/comment mining. The user may request the larger Standard research budget at any time.

## Meal-prep constraints applied to option selection
When ranking options, consider:
- freezer/reheat reliability;
- batch geometry and equipment fit;
- portionability;
- make-ahead leverage;
- whether the dish can remain flavorful after reheating;
- health/composition defaults and personal constraints from the profile files;
- occasion directives from `occasions.md`.

Do not allow Meal Prep requirements to erase cuisine identity. Prefer culinary technique over gimmick diet substitutions.

## Full-recipe additions
When Meal Prep is active, `recipe_template.md` must additionally include:
- explicit portioning/batch plan;
- first-class Reheat Plan;
- concrete fridge/freezer strategy;
- Nutrition Snapshot when required by `meal_prep_nutrition.md`;
- sodium drivers/levers when relevant;
- personal-health/tolerance checks;
- freezer/reheat troubleshooting for likely failure modes.

## Revisions
In Meal Prep profile, revisions must diagnose both fresh-cook performance and stored/reheated performance when relevant. Preserve profile overrides and do not fix a texture problem by silently violating a personal constraint.

## Audit
In Meal Prep profile, `audit.md` must additionally verify:
- batch/portion realism;
- storage/freezer/reheat coherence;
- personal constraint compliance;
- general meal-composition defaults unless overridden;
- Nutrition Snapshot provenance/structure when present or required.

## User overrides
The user can override any non-safety Meal Prep default. Record the override in the locked-decisions ledger and preserve it for the thread.

Examples:
- 6 portions instead of 10;
- all-fridge, no freezer;
- intentionally rich/traditional version;
- use a normally downranked ingredient;
- omit numeric nutrition;
- allow a normally avoided protein or starch.

Do not argue with explicit preference overrides; apply them and, when useful, note the practical tradeoff.
