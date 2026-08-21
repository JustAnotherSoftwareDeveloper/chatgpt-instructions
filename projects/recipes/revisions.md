# Recipe Revisions Instruction Set

## Purpose
Diagnose a recipe failure, corroborate the likely cause, and emit a corrected recipe that preserves the active profile and locked user decisions.

Shared authorities:
- research/sourcing: `meal_sources.md`;
- equipment/geometry: `equipment.md`;
- final recipe format: `recipe_template.md`;
- profile selection/precedence: `instructions.md`.

When `meal-prep` is active, also apply:
- `meal_prep.md`;
- `meal_prep_health_guidelines.md`;
- `meal_prep_personal_health.md`;
- `meal_prep_nutrition.md` for the default full-recipe Nutrition Snapshot unless explicitly opted out.

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

Ask only when ambiguity blocks a reliable fix. Meal Prep additionally follows the max-2-question rule in `meal_prep.md`.

---

## 1) Classify the failure
Pick 1 to 3:
- Doneness/timing
- Texture/structure
- Flavor balance
- Workflow/complexity
- Equipment/geometry/scaling
- Substitution breakage
- **Meal Prep only:** storage/freezer/reheat degradation
- **Meal Prep only:** profile-constraint conflict (a substitution preserved compliance but broke the dish)

---

## 2) Locked decisions and profile carry-forward
Before proposing fixes, recover and preserve:
- active profile;
- selected option/variation;
- equipment limits and pan/tray count;
- ingredient-source/brand constraints;
- format requests;
- rejected paths;
- user-stated profile overrides.

In Meal Prep, also preserve current-thread overrides to personal/health defaults. Do not silently re-enable a default the user already relaxed or remove one they explicitly reinforced.

If a proposed fix conflicts with a lock:
- provide a compliant alternative; or
- clearly identify the conflict and ask only if permission is genuinely required.

---

## 3) Quick triage
Check before research:
- vessel size vs batch depth;
- heat path/preheat/browning feasibility;
- covered/uncovered evaporation path;
- reduction and salinity concentration;
- sequence integrity (acid/dairy/emulsion/rests);
- crowding/surface area;
- substitutions and ingredient state.

**Meal Prep only:** also check:
- whether the fresh recipe was good but storage/reheat broke it;
- freeze point and packaging;
- thaw method;
- reheat power/temp and portion size;
- sauce/starch moisture migration;
- whether components should have been stored separately;
- whether batch scaling changed geometry.

---

## 4) Root-cause hypotheses
State internally at least one falsifiable hypothesis:
- Hypothesis A: [cause] - confidence high|med|low
- Hypothesis B (optional): [cause] - confidence high|med|low

Each hypothesis must imply a cue/test that could disprove it. Every proposed change must map to A or B; remove unrelated "improvements" from the minimal fix.

---

## 5) Research and corroboration
Follow `meal_sources.md` end-to-end.
- Query dish + failure symptom.
- Prefer explicit troubleshooting, mistakes, corrections, ratio debates, geometry, and sensory cues.
- Prefer sources with equipment/geometry matching the user's setup.
- Reconcile disagreements using failure specificity + physics consistency.

Research budget:
- Standard: `meal_sources.md` revisions target.
- Meal Prep: `meal_prep.md` revisions target unless user requests Standard-depth counts.

For Meal Prep reheat/freezer failures, specifically seek evidence on the stored/reheated state, not only fresh preparation.

### Meal Prep internal variant matrix
When Meal Prep is active, build a failure-tailored comparison matrix internally before selecting the fix. Include the drivers that matter to the observed failure, such as:
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

## 6) Equipment, geometry, and moisture pass
Required:
- on-hand-compatible vessel/tools;
- explicit batch depth/crowding limits;
- covered/uncovered plan;
- reduction/evaporation path;
- realistic vessel capacity.

**Meal Prep only:** explicitly test whether the profile batch size requires multiple pans/batches rather than extending cook time in one crowded vessel.

---

## 7) Safety and correctness pass
Follow `meal_sources.md` safety/correctness rules before finalizing.
- Verify time/temperature claims are physically plausible for the stated geometry.
- When making specific food-safety time/temperature/storage claims, use an authoritative source when browsing is available.
- Keep safety corrections concise and relevant to the actual failure.

---

## 8) Fix design
- Keep fixes minimal but decisive.
- Prefer ratio bands and sensory cues over brittle point estimates.
- Add a preventive guardrail for each high-confidence failure.
- Preserve cuisine/flavor intent.
- Preserve user/profile constraints unless explicitly overridden.

For Meal Prep:
- fix both fresh and reheat performance when both matter;
- do not solve storage problems with a component that violates configured personal defaults;
- update fridge/freezer/reheat instructions whenever the diagnosis changes them;
- recalculate numeric nutrition whenever changed quantities materially alter the snapshot, unless the user explicitly opted out of nutrition.

---

## Emission policy
Internal-only: intake, classification, locks, triage, hypotheses, research, variant matrix, equipment analysis, safety pass, fix design.

Emit in this order:

### A) Diagnosis Summary
- Failure class(es)
- Hypothesis A/B with confidence
- Concise corroboration/evidence summary

### B) What Changes and Why
- old -> new changes;
- why each maps to a hypothesis;
- any lock/profile conflict and resolution.

### C) Updated Recipe
Full drop-in replacement using `recipe_template.md` under the same active profile.

Required regardless of profile:
- inventory-aware equipment;
- geometry/crowding limits when relevant;
- explicit moisture/reduction plan;
- Gather & Stage;
- troubleshooting entries for the observed failure.

Additional Meal Prep requirements:
- profile-compliant ingredients;
- portion/batch strategy;
- Make-Ahead Notes;
- first-class Reheat Plan;
- freezer guidance when used;
- Nutrition Snapshot by default unless explicitly opted out;
- Meal Prep ASCII/formatting contract.

### D) Optional Validation Plan
2 to 5 next-cook checks when useful.

---

## Final QA
- Active profile unchanged unless user changed it.
- All locked decisions preserved.
- Each modification maps to a hypothesis.
- No new contradiction between ingredients, instructions, storage, and reheat.
- Standard revision does not leak Meal Prep personal constraints.
- Meal Prep revision satisfies current profile constraints and storage/reheat behavior.
- Meal Prep variant matrix completed internally.
- Meal Prep Nutrition Snapshot present unless explicitly opted out.
