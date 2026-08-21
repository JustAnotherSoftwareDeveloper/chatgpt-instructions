# Meal Prep Personal Health and Tolerance Defaults

## Purpose
Configured personal food/tolerance defaults for the Meal Prep profile. These rules are active only when `meal-prep` is active.

This file is a preference/tolerance policy, not a diagnosis. The user's current-thread observations and explicit requests override non-safety defaults.

## Precedence
1. Current user request and explicit thread overrides.
2. Food safety and explicit allergen constraints.
3. Confirmed/repeated personal tolerance observations in this file.
4. Conservative risk-management defaults in this file.
5. General guidance in `meal_prep_health_guidelines.md`.

Do not apply this file in Standard profile.

---

## Hard/default avoids
Do not use as meaningful ingredients unless the user explicitly requests/accepts them:
- chocolate;
- onion;
- mushrooms.

### Trace-only exception
A minor background amount in a seasoning blend or prepared sauce may be acceptable unless the user requests zero tolerance.
- It must not be a flavor base, bulk ingredient, or texture contributor.
- Disclose meaningful trace exposure when known.
- When uncertain, treat the ingredient as excluded instead of gaming the threshold.

## Heat and grease
- Default heat: warm to medium.
- Extreme chile heat is opt-in.
- Avoid greasy/oil-slick outcomes and routine deep/shallow frying.

## Garlic and aromatics
- Garlic may be used, but do not make a recipe aggressively garlic-forward by default.
- Onion remains excluded as the aromatic base.
- Use alternatives that fit the cuisine: ginger, celery/fennel when appropriate, citrus zest, herbs, toasted spices, tomato paste, browned fond.
- Scallion greens/chives are not assumed safe substitutes; use only when explicitly accepted in the current thread.

## Protein preferences
### Poultry
- Poultry may appear as an ingredient.
- Do not default to poultry as the largest/main course protein unless requested.

### Freezer performance
- Do not default to a protein as the centerpiece if it predictably becomes watery, tough, rubbery, dry, or fishy after freeze/reheat.
- Delicate white fish, shrimp reheated from frozen, and other delicate seafood are common examples.
- This is a performance preference, not a nutritional judgment.

### Generally compatible
- Red meat is acceptable; use cut choice, portioning, and fat management rather than treating it as categorically undesirable.
- Beans/legumes are useful when well-cooked and sensibly portioned.

## Dairy
Default dairy-light.
- Prefer lower-lactose forms when dairy is useful: yogurt, aged cheese, lactose-free products.
- Avoid making lactose-heavy dairy the bulk base unless requested.
- Downrank regular milk-heavy, half-and-half-heavy, cream-heavy, evaporated/condensed-milk-heavy, ice-cream, or large fresh-soft-cheese builds by default.
- Small amounts used as accents are different from making dairy the structural base.

## Gluten grains and starches
Treat gluten grains as a soft blocker rather than a hard ban unless the user states otherwise.

Downrank as default backbone ingredients when an equally good alternative exists:
- wheat flour/bread flour;
- semolina;
- farro;
- bulgur;
- couscous;
- barley;
- rye;
- spelt;
- malt/malt extract/malt syrup;
- regular beer in cooking;
- wheat-based soy sauce when a suitable alternative performs equally well.

Preferred starch paths when cuisine/technique permit:
- white/jasmine/sushi rice and similar non-bran rice;
- potatoes;
- cornmeal/polenta;
- oats when tolerated;
- legumes or mixed-starch structures.

Whole grains are optional. Bran-heavy grains are a separate texture/tolerance concern even apart from gluten.

## Fiber/residue tolerance
Downrank bran-heavy/high-residue stacking by default:
- brown rice;
- wheat bran/wheat berries;
- farro/bulgur/barley;
- coarse whole-grain breads/cereals;
- large raw crucifer loads;
- thick vegetable skins;
- large seed/nut loads;
- raw greens as major bulk;
- dry chewy grain bowls with multiple additional rough-fiber components.

Prefer softer cooking, enough moisture, moderate portions, and fewer simultaneous high-residue components.

White rice, potatoes, polenta, oats when tolerated, and moderate well-cooked legumes are useful default anchors.

## Fava / broad bean safety flag
Treat fava/broad beans as a conditional hard stop unless G6PD deficiency has been ruled out or the user explicitly accepts the risk.

This applies when fava is a meaningful ingredient, including fresh/dried beans, purees, and mixed-legume dishes. If a traditional dish relies on fava, flag the conflict instead of silently substituting.

Do not generalize this into a broad ancestry-based blacklist.

## Personal-trigger watchlist policy
Potential trigger categories become active restrictions only when the user reports a repeated pattern, has a confirmed relevant diagnosis, or explicitly asks for stricter filtering.

Possible watchlist categories include:
- very high-fat meals;
- very salty meals;
- rough/high-residue foods during periods of worse tolerance;
- alcohol-heavy preparations;
- highly processed foods associated with repeat symptoms.

Do not convert watchlist items into permanent bans from weak evidence.

## Acid
Acid is allowed. Prefer adjustable late-stage acid when tolerance is uncertain rather than locking aggressive acidity into the base recipe.

## Cooking oil
Avocado oil is the default cooking-oil preference when neutral high-heat oil is appropriate.

## Meal-composition guardrail
Avoid combining multiple potentially difficult elements in one meal without a reason, especially:
- bran-heavy grain + legumes + raw vegetables;
- high insoluble fiber + high fat;
- rough grain + seeds/nuts + heavy sauce.

When one such element is central to the dish, simplify and soften the rest of the meal.

## User override behavior
The user may explicitly relax any non-safety preference in this file. Record that relaxation in the thread's locked-decisions ledger and do not silently restore the old default later.

## QA
Before emitting a Meal Prep option/recipe/revision:
- hard/default avoids absent unless overridden;
- trace exceptions disclosed when meaningful;
- onion not silently reintroduced through aromatic substitutions;
- poultry/freezer-fragile proteins not silently promoted to centerpiece;
- dairy/gluten/bran-heavy ingredients handled according to their soft-blocker status;
- fava safety flag respected;
- no broad speculative blacklist created;
- current-thread tolerance observations and overrides take precedence.
