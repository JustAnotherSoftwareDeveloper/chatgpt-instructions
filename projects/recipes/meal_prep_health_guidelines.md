# Meal Prep Health Guidelines

## Purpose
General, non-medical composition and cooking defaults loaded by the `workflow-meal-prep` occasion modifier through `occasions.md` `special-instructions`.

This file is not globally active. Apply it while `workflow-meal-prep` is active, or narrowly when the user explicitly requests general health-oriented recipe composition under `instructions.md`.

The user's explicit request wins over these defaults unless food safety is involved.

## Baseline composition
Aim for meals that are:
- protein-forward enough to function as complete meals;
- fiber-appropriate rather than fiber-maximized;
- vegetable-forward when compatible with the dish;
- added-sugar-minimized;
- sodium-aware;
- fat-managed rather than greasy;
- flavorful through technique rather than diet gimmicks.

Default to at least 2 distinct vegetables when the dish supports it. If the dish definition makes that unreasonable, provide an optional vegetable side/add-on rather than distorting the dish.

## Macronutrient structure
- Avoid mains that are mostly starch + fat with token protein.
- Prefer mixed meals containing meaningful protein plus appropriate carbohydrate/fiber and fat.
- Refined starches can be useful when they improve tolerance, texture, or freezer performance; do not moralize about them.
- Use legumes where they fit and tolerate storage/reheat well.
- Whole grains are optional, not mandatory.
- Omega-3-supportive ingredients are a positive when they fit the dish, but they are opt-in rather than mandatory.

## Blood-sugar-aware composition (qualitative, non-medical)
- Prefer mixed meals with meaningful protein, fat, and fiber over refined-carbohydrate-only meals.
- Refined starches such as white rice may be useful, but default to using them as a supporting base rather than the entire meal structure when the dish permits.
- Avoid sugar-sweetened sauces/glazes as the primary flavor driver.
- When starch is substantial, pair it with adequate protein and appropriate fat/fiber when compatible with the dish and tolerance constraints.
- Do not improve theoretical macro balance by creating an excessively rough/high-residue meal; fiber tolerance and overall meal composition still govern.

## Fiber and texture
Do not assume more fiber is always better. Evaluate:
- fiber type;
- preparation;
- portion size;
- moisture;
- total residue load across the meal.

Prefer when tolerance matters:
- softer-cooked vegetables;
- well-cooked legumes in moderate portions;
- oats when appropriate;
- stews, braises, saucy bowls, and other moist integrated formats;
- cohesive starches such as potatoes, rice, or polenta when they fit the cuisine.

Downrank by default when the meal stacks several rough/high-residue elements:
- bran-heavy grain + legumes + raw vegetables;
- whole grain + large seed/nut load + high-fat dressing;
- brown rice + beans + raw greens;
- barley/farro/bulgur + legumes + a heavy/high-sodium sauce;
- chewy dry grain bowls with minimal moisture.

Avoid high-fat + high-insoluble-fiber pairings by default unless clearly mitigated. If whole grains are requested, mitigate with softer/wetter cooking, moderate portions, enough moisture, measured fat, and fewer competing rough-fiber components.

## Fat quality and management
- Prefer measured fat additions over free-pouring.
- Prefer mono- and polyunsaturated-fat-forward ingredients where culinarily appropriate.
- Whole-food fat sources are useful when they improve flavor/texture.
- Keep saturated-fat-heavy additions bounded by default without stripping the dish of identity.
- Default to roughly 1 to 3 major fat sources when each serves a distinct culinary purpose (cooking medium, emulsion, finish, garnish). If using more, justify the distinct purpose and avoid redundant stacking.
- Use emulsification, pan sauces, yogurt, blended legumes/vegetables, or other techniques to produce richness without an oily mouthfeel.

## Sodium
Sodium is a design constraint, not a universal hard cap.

When numeric nutrition is available, report:
- sodium per serving;
- sodium per 1000 kcal.

Without reliable nutrition data, do not invent a number.

For personalized Meal Prep full recipes, identify the top 3 sodium drivers and provide 2 to 4 practical levers, such as:
- low-sodium stock/broth;
- reducing soy/bouillon/cured ingredients;
- draining/rinsing canned foods;
- no-salt-added tomato products;
- moving salty components to optional finishes;
- using acid, herbs, browning, toasted spices, or aromatics for impact instead of simply adding more salt.

Useful qualitative classification when numbers are reliably computed:
- low: under 500 mg/serving;
- moderate: 500-900 mg/serving;
- high: over 900 mg/serving.

These are project guidance, not medical thresholds.

## Added sugar
- Avoid sugar-forward sauces/glazes by default.
- Small amounts of sugar are acceptable when technically useful for balance, browning, fermentation, or cuisine identity; when it is not obvious, briefly explain the functional reason.
- Do not replace ordinary small sugar quantities with odd sweeteners solely to make a dish appear healthier.

## Preferred cooking methods
Favor methods with strong flavor and good batch performance:
- sear + deglaze + simmer;
- roast/bake/air-fry style cooking;
- braise/pressure-cook for suitable proteins and legumes;
- sauces, pickles, herbs, spice blooming, browning, and acid adjustment;
- moist integrated dishes that remain coherent after reheating.

Downrank by default:
- deep frying for routine batch meals;
- cream-heavy sauces as the entire base;
- sugar-forward glazes;
- bland dump-and-bake methods without corrective technique;
- formats known to degrade badly after freezing/reheating when Meal Prep is active.

## Technique realism
- Design for a competent home kitchen and the actual inventory in `equipment.md`.
- Do not assume restaurant-only equipment, line-cook throughput, or unexplained professional technique.
- When a technically demanding step is justified, provide practical cues, recovery branches, and an on-hand-equipment path.
- Flavor is non-negotiable: use browning, toasting, deglazing, spice blooming, herbs, zest, acid adjustment, and texture contrast rather than stripping the dish down to hit a health label.

## Freezer and reheat quality
When batch/freezer use is part of the active workflow, prefer foods that:
- remain cohesive after freezing;
- do not separate excessively;
- can be reheated without drying out or becoming rubbery;
- have a clear texture-reset strategy.

When a traditionally delicate component freezes poorly, either:
- store/freeze it separately;
- add it fresh at serving;
- or clearly explain the quality tradeoff if the user wants the original format.

## Health substitutions: do not be weird
Do not silently replace defining ingredients with diet substitutes that change the soul of the dish (for example, cauliflower rice everywhere, fat-free cheese, or unconventional sweeteners).

If a substitution materially changes dish identity:
- use it only when requested or strongly justified;
- label it as a variation/alternative;
- state the flavor/texture tradeoff.

## Ingredient realism
Specialty ingredients are allowed if realistically purchasable in the U.S. For central specialty ingredients:
- state what to look for;
- give a generic source category (international market, butcher, spice shop, reputable online retailer) when useful;
- provide a mainstream substitute when feasible without destroying technique;
- when the specialty ingredient defines the whole dish and a viable mainstream path exists, offer that path as a variation rather than silently changing the original.

## Allowed deviations
These are defaults, not a mandate to deform the dish.
- If the user explicitly asks for a richer, sweeter, hotter, or more traditional direction, honor it unless safety is involved.
- If a defining traditional method conflicts with a default and the user wants the traditional direction, preserve the dish and note the tradeoff briefly when useful.
- If a health-oriented substitution would materially harm the dish and no good compensating technique exists, prefer a transparent tradeoff over a gimmick substitution.

## QA
Before finalizing a deliverable when this authority is active, check:
- real meal-sized portions when the request is a meal;
- meaningful protein where appropriate;
- appropriate vegetables/fiber for the dish;
- mixed-meal structure rather than refined-carb-only structure when compatible with the dish;
- no unnecessary sugar/fat/sodium stacking;
- top sodium drivers + levers present when required by `workflow-meal-prep`;
- flavor preserved through culinary technique;
- freezer/reheat performance considered when batch/freezer use is active;
- no gimmick substitutions unless requested;
- equipment/technique remains realistic for the home kitchen.
