# Audit Workflow

## Purpose
Audit recipe artifacts for template compliance, carry-forward, source quality, equipment/geometry, timing, internal consistency, and user-request compliance. Apply additional Meal Prep passes when that profile is active.

Authorities:
- profile/routing: `instructions.md`
- options: `options.md`
- full recipe: `recipe_template.md`
- revisions: `revisions.md`
- research: `meal_sources.md`
- occasion: `occasions.md`
- equipment: `equipment.md`
- tags: `tags.md`
- Meal Prep overlay: `meal_prep.md`, `meal_prep_health_guidelines.md`, `meal_prep_personal_health.md`, `meal_prep_nutrition.md`

Do not duplicate those files' full rules here; audit against them.

---

## 1) Output mode
Determine artifact type first:
- Options artifact
- Recipe artifact
- Revisions artifact
- Unknown/mixed: treat as recipe unless context clearly indicates otherwise

Then determine active profile:
- Standard
- Meal Prep

Audit output:
- issue list only; or
- corrected full re-emit when explicitly requested.

Default: issue list only.

---

## 2) Pre-audit intake
Recover:
- active profile;
- selected option/variation;
- equipment/pan limits;
- ingredient-source/brand constraints;
- format requests;
- rejected paths;
- profile overrides;
- explicit user constraints.

For Standard, verify Meal Prep-only constraints did not leak into the artifact.
For Meal Prep, recover the currently active personal/profile defaults and overrides.

---

## 3) Required passes
Run all applicable passes in order. Do not claim "no issues found" until every applicable pass is complete.

### Pass 1 — Template and profile compliance
#### Options
Check against `options.md`:
- required inputs populated;
- Profile field is correct;
- 5 to 8 shortlist entries and 5 to 10 runner-ups;
- each shortlist entry uses 3 to 5 valid tags and the required per-option fields;
- target length/shape is respected unless the user requested more detail;
- Watch is research-derived;
- Why it fits references occasion + equipment;
- Standard: no implicit Meal Prep constraints;
- Meal Prep: Why it fits also reflects meaningful Meal Prep constraints and profile extraction occurred internally;
- internal workflow sections are not emitted unless requested;
- if browsing occurred, Sources/footnotes resolve correctly;
- if browsing did not occur, the explicit no-browse sentence is present and Sources/footnotes are omitted.

#### Full recipe
Check `recipe_template.md` required Standard sections/order and formatting:
- Title & Overview
- Tags
- Yield & Timing
- Grocery List
- Equipment & Tools
- Ingredients
- Allergy & Dietary Notes
- Quick Overview
- Gather & Stage
- Instructions
- Common Issues
- Make-Ahead Notes
- Reheat Plan when profile/recipe requires it
- Troubleshooting
- Geometry/Scaling when relevant
- Nutrition Snapshot when profile/user requires it
- Special Notes when required
- Variations unless explicitly omitted by user/format
- Safety/Sources as applicable

Structural checks:
- 3 to 8 valid recipe tags from `tags.md`;
- Yield & Timing includes Active Prep, Inactive Prep / Hands-Off / Rest, Cook, Total, and Make-ahead;
- Grocery List has exact ingredient parity and no empty category headings;
- Equipment uses `equipment.md` names/substitutions;
- >= 4 numbered instruction steps;
- heat steps include heat/temp + time range + sensory cue;
- >= 2 recovery branches;
- final taste-adjust loop;
- Troubleshooting has 2 to 4 entries;
- Variations has 2 to 4 meaningful entries when present;
- ingredient parity across Grocery List / Ingredients / Instructions.

Meal Prep additionally requires unless explicitly overridden:
- profile yield/portioning, including 10 x approximately 2-cup portions for volumetric dishes by default;
- concrete 3-to-5-day fridge + remaining freezer plan when freezer-compatible;
- quality-first freezer horizon stated realistically;
- first-class Reheat Plan;
- batch geometry/scaling notes when batch size affects cooking;
- profile-compliant ingredients;
- Nutrition Snapshot by default unless explicitly opted out;
- top 3 sodium drivers + 2 to 4 sodium levers;
- sodium per 1000 kcal when Calories and Sodium are numeric;
- Meal Prep ASCII-only/`deg F` formatting contract.

If a Meal Prep diet toggle is materially relevant (for example sodium, protein, low-FODMAP, gluten, dairy/lactose), verify the toggle is coherent with the actual ingredients and method.

#### Revisions
Check against `revisions.md`:
- failure classification;
- locked/profile carry-forward;
- falsifiable hypothesis A (and B if used);
- every change maps to a hypothesis;
- Diagnosis Summary;
- What Changes and Why;
- full Updated Recipe in the same active profile;
- validation plan only when useful.

Meal Prep revisions additionally require:
- storage/freezer/reheat failure analysis when relevant;
- the internal failure-tailored variant matrix;
- Nutrition Snapshot in the Updated Recipe unless explicitly opted out.

---

### Pass 2 — Carry-forward and cross-profile isolation
For every recoverable constraint:
- selected option/variation preserved;
- equipment limits preserved;
- ingredient-source constraints preserved;
- format requests preserved;
- rejected paths absent;
- profile overrides preserved.

Critical profile isolation checks:
- Standard artifact must not silently apply `meal_prep_personal_health.md` or other Meal Prep-only defaults.
- Meal Prep artifact must not silently drop profile constraints or reset user overrides.
- Occasion directives remain active in both profiles.

Silent violation of an explicit lock/profile override is at least Major.

---

### Pass 3 — Source quality
Follow `meal_sources.md` quality requirements.

Source-family count:
- Standard: mode-specific counts from `meal_sources.md`.
- Meal Prep: counts from `meal_prep.md` unless Standard-depth counts were requested.

Verify:
- independent source families and strict dedup;
- required 2+ Tier 1 creators + blog + video/social + discussion/feedback-loop mix;
- regional anchor when applicable;
- multilingual/origin-language search when applicable;
- comment-mined failures and guardrails completed for deep research;
- baseline/secondary sources not defining cuisine identity alone;
- no fabricated/unverifiable citations;
- in-text markers resolve;
- target deliverable source formatting is followed;
- no Sources section when no browsing occurred.

For Meal Prep nutrition, recipe-source counts do not substitute for nutrition provenance. `meal_prep_nutrition.md` governs nutrient data separately.

Invented citation = Critical.

---

### Pass 4 — Equipment, geometry, and batch fit
Check `equipment.md`:
- listed tools exist or have compliant substitutions;
- pan/material calibration applied;
- crowding/layer depth explicit where important;
- covered/uncovered and evaporation plan explicit;
- vessel capacity matches yield;
- avoid-unless-necessary/retired gear justified;
- ceramic nonstick not used for inappropriate high-heat searing/broiling.

Meal Prep additionally:
- profile batch does not exceed realistic vessel surface area/capacity;
- doubling is not implemented by merely extending cook time when batching is required;
- portion count matches the stated batch plan.

---

### Pass 5 — Timing, storage, and reheat plausibility
Check:
- Active Prep + Inactive / Hands-Off + Cook is approximately consistent with Total; flag discrepancies greater than about 10 minutes unless overlapping/parallel timing explains them;
- step times plausible for heat, geometry, and portion size;
- parallel tasks fit active-prep estimate;
- sensory cues align with ranges;
- rests present when materially needed.

Meal Prep additionally:
- fridge/freezer plan internally coherent;
- freeze point makes culinary sense;
- thaw path matches food format;
- reheat method/time matches portion size and starting state;
- texture-reset step actually addresses likely degradation;
- Make-Ahead Notes and Reheat Plan do not contradict each other.

---

### Pass 6 — Internal contradiction
Verify:
- every ingredient used is listed and every listed ingredient is used;
- Grocery List parity and no duplicates;
- heat/temperature references do not conflict;
- yield fits vessel capacity;
- troubleshooting does not contradict instructions;
- allergen/Contains line matches ingredients;
- variations do not violate locks;
- Common Issues and Troubleshooting agree.

Meal Prep additionally:
- storage/freezer/reheat instructions agree with each other;
- diet/personal toggles are coherent with base ingredients;
- no Meal Prep hard/default avoid reappears in a variation unless explicitly overridden;
- Nutrition Snapshot serving definition matches recipe yield/portioning.

---

### Pass 7 — User, occasion, and profile compliance
Verify:
- every direct user request is satisfied or explicitly acknowledged;
- rejected ingredients/techniques/formats absent;
- occasion optimize/avoid axes are reflected in method/serving choices;
- requested research depth met;
- make-ahead preference honored.

Meal Prep additionally:
- batch/portioning matches `meal_prep.md` or explicit override;
- general composition follows `meal_prep_health_guidelines.md` unless overridden;
- personal defaults follow `meal_prep_personal_health.md` unless overridden;
- freezer/reheat quality is treated as a design constraint;
- sodium drivers/levers handled as required;
- nutrition methodology follows `meal_prep_nutrition.md` unless nutrition was explicitly opted out;
- ASCII-only output contract followed.

---

### Pass 8 — Meal Prep nutrition provenance (Meal Prep only unless user opted out)
Check:
- Nutrition Snapshot is present in full recipes/updated recipes unless explicitly opted out;
- all mandatory core rows present;
- vitamins/minerals tables present as required by `recipe_template.md`;
- `NA` used only after source-tier exhaustion;
- `--` used for non-displayed %DV and `NA` rows;
- Source basis populated per row/tightly grouped set;
- branded-food hierarchy follows manufacturer -> USDA Branded -> calculator fallback;
- field-level fallback documented where used;
- Added sugars follows Role A/B/C/D logic;
- no partial nutrient sums silently exclude unresolved ingredients;
- serving count matches recipe yield;
- Nutrition Provenance present;
- calculator does not outrank better ingredient-level data;
- calculator/tool appears in Sources only if it materially contributed to displayed nutrition values.

Invented nutrition values = Critical.

---

## 4) Severity
| Severity | Definition |
|---|---|
| **Critical** | Likely cook failure, safety risk, fabricated source/nutrition data, or direct violation of an explicit hard constraint. |
| **Major** | High reliability risk, silent profile/lock violation, or major structural inconsistency. |
| **Minor** | Clarity/format/low-risk inconsistency that improves quality but does not block cooking. |

Group symptoms that share one root cause/fix.

---

## 5) Issue format
For each issue:

```text
ISSUE-[N]
Severity:       [Critical | Major | Minor]
Pass:           [Pass N - label]
Location:       [section/step]
Problem:        [specific mismatch]
Why it matters: [likely consequence]
Required fix:   [specific correction + authority]
```

Avoid vague language.

---

## 6) Corrected re-emit
When requested:
1. Apply all Critical fixes.
2. Apply all Major fixes.
3. Apply Minor fixes unless they reduce clarity or violate intent/locks.
4. Re-emit the complete artifact using the correct shared template + active profile.
5. Do not emit internal audit chain-of-thought/workflow notes.
6. Append one summary line: `[N Critical, N Major, N Minor fixes applied; N Minor issues noted but not applied.]`

---

## Completion checklist
- artifact type identified;
- profile identified;
- thread locks recovered;
- all applicable passes completed;
- cross-profile isolation checked;
- issues severity-ordered;
- corrected artifact uses same profile unless user changed it;
- Meal Prep nutrition pass completed unless explicitly opted out.
