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
- Treat the freezer plan as quality-first storage measured in months, not merely a way to bridge the 2-week eating window.
- Treat freezer performance and reheat quality as first-class design constraints.
- Include at least one meaningful make-ahead pathway (for example sauce/base prep, chop kit, marinade, par-cooked starch, or freezer portioning).
- For batch-oriented recipes, include a concrete freeze point, portion/packaging plan, thaw path, best reheat method, and texture-reset step.
- Prefer recipes that portion cleanly and tolerate repeated storage/reheat without becoming watery, greasy, grainy, rubbery, or mushy.
- Do not force cup-based portions onto foods that are not naturally portioned by volume.

### Portioning
- Volumetric dishes such as soups, stews, chilis, pasta-ish bowls, and similar foods: default to **10 x approximately 2-cup meal portions**.
- Component meals: define protein + vegetable + starch portions or another practical per-meal assembly broadly equivalent to a real meal.
- Non-volumetric items: define 10 meal-sized units/servings and a packaging strategy.
- A meal-prep portion is a real meal, not a snack, unless requested otherwise.

## Interaction defaults
- Ask at most 2 clarifying questions, and only when missing information materially changes correctness. Otherwise make reasonable assumptions.
- Optional novelty guardrail: when the user is seeking ideas rather than a specific repeat, prefer meaningful novelty relative to the last 2 to 3 recipes in the same conversation.
- If the user provides a recipe/source link, treat it as primary input and triangulate material technique/safety disagreements with 1 to 3 additional independent sources when browsing is available.

## Meal-prep research budget
All source-quality and research-method rules remain governed by `meal_sources.md`.

For Meal Prep, the evidence set may use the historical Meal Prep budget when the extra work of freezer/reheat/nutrition validation would otherwise create disproportionate research overhead:
- Options: candidate pool 15-25; final evidence set 5-8 distinct source families.
- Full recipe: candidate pool 10-14; final evidence set 5-7 distinct source families.
- Revisions: candidate pool 8-15; final evidence set 5-7 distinct source families.

Deep-research behaviors still apply: independent evidence, source-family deduplication, disagreement resolution, regional anchors where applicable, and failure-mode/comment mining. The user may request the larger Standard research budget at any time.

When a full recipe is sourced, aim for roughly 6 to 15 useful in-text footnote markers across externally grounded claims. Do not footnote ordinary kitchen basics merely to hit a count.

If browsing is unavailable and the user explicitly requested research/sourcing/citations, clearly label the result as an unsourced draft, omit invented footnotes/URLs, and omit the Sources section.

## Output contract
Meal Prep preserves the former Healthy-project formatting contract:
- plain Markdown;
- ASCII characters only in the emitted deliverable;
- no emojis or Unicode punctuation;
- temperatures written as `425 deg F`, not with a degree symbol;
- U.S. customary units by default, with metric when source-derived or precision-critical;
- no raw URLs outside the Sources section unless the user explicitly asks for inline links.

These are Meal Prep output rules only; they must not leak into Standard profile unless the user requests them.

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
- **Nutrition Snapshot by default**, governed by `meal_prep_nutrition.md`, unless the user explicitly opts out of numeric nutrition;
- top 3 sodium drivers + 2 to 4 concrete sodium levers;
- sodium per 1000 kcal when numeric nutrition is available;
- personal-health/tolerance checks;
- freezer/reheat troubleshooting for likely failure modes.

## Food-safety sourcing
- Keep cooling/storage/reheat guidance practical and concise.
- When making specific food-safety time/temperature/storage claims, corroborate with an authoritative source such as USDA/FDA/Cooperative Extension when browsing is available.
- Do not invent safety citations.

## Revisions
In Meal Prep profile, revisions must diagnose both fresh-cook performance and stored/reheated performance when relevant. Preserve profile overrides and do not fix a texture problem by silently violating a personal constraint.

For failure-driven comparisons, preserve the former Healthy workflow's internal variant-matrix step: compare the material failure drivers (ratios, layer depth, covered/uncovered path, reduction endpoint, sequence, salinity, storage/reheat state) across sources before selecting the fix.

## Audit
In Meal Prep profile, `audit.md` must additionally verify:
- batch/portion realism;
- storage/freezer/reheat coherence;
- personal constraint compliance;
- general meal-composition defaults unless overridden;
- Nutrition Snapshot presence by default unless explicitly opted out;
- Nutrition Snapshot provenance/structure when present;
- Meal Prep ASCII/formatting contract.

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
