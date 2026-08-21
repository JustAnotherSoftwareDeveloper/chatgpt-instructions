# Recipe Revisions Instruction Set

## Purpose
Diagnose a recipe failure, corroborate the likely cause, and emit a corrected recipe that preserves the resolved occasion context, active specialized authorities, and locked user decisions.

Shared authorities:
- research/sourcing: `meal_sources.md`;
- occasions/special-instruction hooks: `occasions.md`;
- equipment/geometry: `equipment.md`;
- final recipe format: `recipe_template.md`;
- orchestration/precedence: `instructions.md`.

Load additional authorities only when the active occasion/modifier declares them through `special-instructions` or the user's revision request explicitly invokes their topic.

When `workflow-meal-prep` is active, load:
- `meal_prep_health_guidelines.md`;
- `meal_prep_personal_health.md`;
- `meal_prep_nutrition.md` for the default full-recipe Nutrition Snapshot unless explicitly opted out.

An ordinary revision with an explicit numeric nutrition request may load `meal_prep_nutrition.md` alone without activating personalized Meal Prep. An ordinary revision explicitly asking to make the dish healthier may load `meal_prep_health_guidelines.md` alone.

---

## 0) Intake
Minimum:
- recipe markdown or concise dish description;
- what went wrong;
- any swaps/changes made.

Helpful when available:
- pan/pot size/material;
- covered/uncovered timing;
- layer depth/thickness;
- whether the failure occurred fresh, after refrigeration, after freezing, or on reheat.

Ask only when ambiguity blocks a reliable fix. Apply any active occasion interaction rules; `workflow-meal-prep` permits at most 2 clarifying questions.

---

## 1) Classify the failure
Pick 1 to 3:
- Doneness/timing
- Texture/structure
- Flavor balance
- Workflow/complexity
- Equipment/geometry/scaling
- Substitution breakage
- Storage/freezer/reheat degradation (when relevant)
- Occasion/specialized-authority conflict (a compliant change broke the dish or service goal)

---

## 2) Locked decisions and occasion carry-forward
Before proposing fixes, recover and preserve:
- base occasion;
- workflow/seasonal/setting/service/menu modifiers;
- selected option/variation;
- equipment limits and pan/tray count;
- ingredient-source/brand constraints;
- format requests;
- rejected paths;
- user-stated overrides to occasion/specialized-authority defaults;
- request-scoped constraints explicitly established for the revision/thread.

If a proposed fix conflicts with a lock:
- provide a compliant alternative; or
- clearly identify the conflict and ask only if permission is genuinely required.

Do not silently drop or introduce an occasion modifier during revision.

---

## 3) Quick triage
Check before research:
- vessel size vs batch depth;
- heat path/preheat/browning feasibility;
- covered/uncovered evaporation path;
- reduction and salinity concentration;
- sequence integrity (acid/dairy/emulsion/rests);
- crowding/surface area;
- substitutions and ingredient state;
- active occasion directives that affect seasonality, hold/service, transport, or storage.

When storage/reheat is part of the artifact or failure, also check:
- whether the fresh recipe was good but storage/reheat broke it;
- freeze point and packaging;
- thaw method;
- reheat power/temp and portion size;
- sauce/starch moisture migration;
- whether components should have been stored separately;
- whether batch scaling changed geometry.

`workflow-meal-prep` makes this stored/reheated-state analysis mandatory when relevant.

---

## 4) Root-cause hypotheses
State internally at least one falsifiable hypothesis:
- Hypothesis A: [cause] - confidence high|med|low
- Hypothesis B (optional): [cause] - confidence high|med|low

Each hypothesis must imply a cue/test that could disprove it. Every proposed change must map to A or B; remove unrelated improvements from the minimal fix.

---

## 5) Research and corroboration
Follow `meal_sources.md` end-to-end.
- Query dish + failure symptom.
- Prefer explicit troubleshooting, mistakes, corrections, ratio debates, geometry, and sensory cues.
- Prefer sources with equipment/geometry matching the user's setup.
- Reconcile disagreements using failure specificity + physics consistency.

Research budget:
- default: use `meal_sources.md` revisions target;
- if an active occasion declares a research-budget override, use that count while retaining all `meal_sources.md` quality rules.

When storage/reheat is part of the failure, seek evidence on the stored/reheated state, not only fresh preparation.

### Special-instruction variant matrix
When an active occasion requires a variant matrix, build it internally before selecting the fix.

`workflow-meal-prep` requires a failure-tailored comparison including material drivers relevant to the observed failure, such as:
- yield/batch size;
- vessel/layer depth/crowding;
- time/temperature;
- covered vs uncovered path;
- reduction endpoint;
- key ingredient ratios;
- salinity inputs;
- emulsion/acid/dairy sequence;
- freeze point/thaw/reheat state when relevant.

Prefer ratio bands and recurring patterns over one source's point estimate. Record why the chosen path best matches the user's geometry and failure mode. Do not emit the matrix unless requested.

---

## 6) Equipment, geometry, moisture, and occasion pass
Required:
- on-hand-compatible vessel/tools;
- explicit batch depth/crowding limits;
- covered/uncovered plan;
- reduction/evaporation path;
- realistic vessel capacity;
- compatibility with active seasonal/service/setting/transport directives;
- yield/service composition consistent with `instructions.md`.

When `workflow-meal-prep` is active, explicitly test whether the batch requires multiple pans/batches rather than extending cook time in one crowded vessel.

---

## 7) Safety and correctness pass
Follow `meal_sources.md` safety/correctness rules before finalizing.
- Verify time/temperature claims are physically plausible for the stated geometry.
- When making specific food-safety time/temperature/storage claims, use an authoritative source when browsing is available.
- Keep safety corrections concise and relevant to the actual failure.
- Apply any stronger safety-sourcing rule declared by the active occasion.

---

## 8) Fix design
- Keep fixes minimal but decisive.
- Prefer ratio bands and sensory cues over brittle point estimates.
- Add a preventive guardrail for each high-confidence failure.
- Preserve cuisine/flavor intent.
- Preserve user/occasion/specialized-authority constraints unless explicitly overridden.

When `workflow-meal-prep` is active:
- fix both fresh and reheat performance when both matter;
- do not solve storage problems with a component that violates loaded personal defaults;
- update fridge/freezer/reheat instructions whenever the diagnosis changes them;
- recalculate numeric nutrition whenever changed quantities materially alter the snapshot, unless the user explicitly opted out of nutrition.

When numeric nutrition is request-scoped outside Meal Prep, recalculate only because nutrition remains in scope; do not add Meal Prep storage/personal constraints.

---

## Emission policy
Internal-only: intake, classification, locks, triage, hypotheses, research, any required variant matrix, equipment/occasion analysis, safety pass, fix design.

Emit in this order:

### A) Diagnosis Summary
- Failure class(es)
- Hypothesis A/B with confidence
- Concise corroboration/evidence summary

### B) What Changes and Why
- old -> new changes;
- why each maps to a hypothesis;
- any lock/occasion/specialized-authority conflict and resolution.

### C) Updated Recipe
Full drop-in replacement using `recipe_template.md` under the same resolved occasion context.

Required regardless of occasion:
- inventory-aware equipment;
- geometry/crowding limits when relevant;
- explicit moisture/reduction plan;
- Gather & Stage;
- troubleshooting entries for the observed failure;
- all ordinary recipe directives from the active base/modifiers.

Additional requirements come from active `special-instructions` and request-scoped authorities.

For `workflow-meal-prep`, require:
- loaded-constraint-compliant ingredients;
- portion/batch strategy;
- Make-Ahead Notes;
- first-class Reheat Plan;
- freezer guidance when used;
- Nutrition Snapshot by default unless explicitly opted out;
- personalized Meal Prep ASCII/output contract.

### D) Optional Validation Plan
2 to 5 next-cook checks when useful.

---

## Final QA
- Occasion context unchanged unless the user changed it.
- `general-cooking` used when no specialized base is justified.
- All locked decisions preserved.
- Every modification maps to a hypothesis.
- No new contradiction between ingredients, instructions, seasonality, service/holding, storage, and reheat.
- Every active special instruction and request-scoped authority was applied narrowly.
- No inactive specialized authority leaked into the revision.
- Yield and immediate service count remain coherent.
- When `workflow-meal-prep` is active, variant matrix completed internally and Nutrition Snapshot present unless explicitly opted out.
