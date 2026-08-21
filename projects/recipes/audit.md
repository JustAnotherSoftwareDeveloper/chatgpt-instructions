# Audit Workflow

## Purpose
Audit recipe artifacts for template compliance, carry-forward, source quality, equipment/geometry, timing, internal consistency, user-request compliance, occasion-directive compliance, and active special-instruction compliance.

Authorities:
- orchestration/precedence: `instructions.md`
- occasions/special-instruction hooks: `occasions.md`
- options: `options.md`
- full recipe: `recipe_template.md`
- revisions: `revisions.md`
- research: `meal_sources.md`
- equipment: `equipment.md`
- tags: `tags.md`
- special authorities: only those loaded by the resolved occasion context

Do not duplicate authority files' full rules here; audit against them.

---

## 1) Output mode
Determine artifact type first:
- Options artifact
- Recipe artifact
- Revisions artifact
- Unknown/mixed: treat as recipe unless context clearly indicates otherwise

Then resolve/recover the active occasion context:
- base occasion;
- workflow modifier;
- setting modifier;
- service modifier;
- menu modifier;
- loaded `special-instructions`.

Audit output:
- issue list only; or
- corrected full re-emit when explicitly requested.

Default: issue list only.

---

## 2) Pre-audit intake
Recover:
- resolved occasion context;
- selected option/variation;
- equipment/pan limits;
- ingredient-source/brand constraints;
- format requests;
- rejected paths;
- overrides to occasion/special-instruction defaults;
- explicit user constraints.

Verify that no inactive special-instruction authority leaked into the artifact. When an active occasion loads specialized authorities, recover their current-thread overrides before auditing.

---

## 3) Required passes
Run all applicable passes in order. Do not claim "no issues found" until every applicable pass is complete.

### Pass 1 - Template, occasion, and special-instruction compliance
#### Options
Check against `options.md`:
- required inputs populated;
- base occasion and modifiers are correctly resolved;
- 5 to 8 shortlist entries and 5 to 10 runner-ups;
- each shortlist entry uses 3 to 5 valid tags and required per-option fields;
- target length/shape is respected unless user requested more detail;
- Watch is research-derived;
- Why it fits references relevant occasion directives + equipment;
- if special instructions are active, Why it fits reflects at least one material special-instruction constraint;
- internal workflow sections are not emitted unless requested;
- if browsing occurred, Sources/footnotes resolve correctly;
- if browsing did not occur, the exact no-browse sentence is present and Sources/footnotes are omitted;
- active occasion output-format rules are followed.

#### Full recipe
Check `recipe_template.md` required sections/order and formatting:
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
- Reheat Plan when occasion/special-instruction/recipe requires it
- Troubleshooting
- Geometry/Scaling when relevant or required
- Nutrition Snapshot when user/active special instruction requires it
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

Occasion checks:
- base optimize/avoid directives are reflected;
- workflow/setting/service/menu directives are reflected without silently erasing each other;
- required hold/service/transport/make-ahead guidance exists when the occasion calls for it;
- any active `special-instructions` requirements are present.

When `workflow-meal-prep` is active, additionally require unless explicitly overridden:
- 10 x approximately 2-cup portions for volumetric dishes by default, or equivalent real meal portions for other formats;
- concrete 3-5-day fridge + remaining freezer plan when freezer-compatible;
- quality-first freezer horizon stated realistically;
- first-class Reheat Plan;
- batch geometry/scaling notes when batch size affects cooking;
- loaded personal/composition constraints;
- Nutrition Snapshot by default unless explicitly opted out;
- top 3 sodium drivers + 2 to 4 sodium levers;
- sodium per 1000 kcal when Calories and Sodium are numeric;
- ASCII-only/`deg F` output contract.

If a loaded dietary toggle is materially relevant, verify it is coherent with actual ingredients and method.

#### Revisions
Check against `revisions.md`:
- failure classification;
- occasion + locked-decision carry-forward;
- falsifiable hypothesis A (and B if used);
- every change maps to a hypothesis;
- Diagnosis Summary;
- What Changes and Why;
- full Updated Recipe under the same occasion context;
- validation plan only when useful;
- any occasion-required failure analysis or special revision hook completed.

When `workflow-meal-prep` is active, additionally require:
- storage/freezer/reheat failure analysis when relevant;
- internal failure-tailored variant matrix;
- Nutrition Snapshot in Updated Recipe unless explicitly opted out.

---

### Pass 2 - Carry-forward and special-instruction isolation
For every recoverable constraint:
- base occasion preserved;
- workflow/setting/service/menu modifiers preserved;
- selected option/variation preserved;
- equipment limits preserved;
- ingredient-source constraints preserved;
- format requests preserved;
- rejected paths absent;
- occasion/special-instruction overrides preserved.

Critical isolation checks:
- no special-instruction authority is applied unless its declaring occasion/modifier is active;
- active special instructions are not silently dropped;
- project/chat memory alone did not activate a special instruction;
- base occasion directives remain active alongside workflow directives.

Silent violation of an explicit lock or active special instruction is at least Major.

---

### Pass 3 - Source quality
Follow `meal_sources.md` quality requirements.

Source-family count:
- default: mode-specific counts from `meal_sources.md`;
- if active occasion special instructions override counts, use those counts only while preserving all quality requirements.

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

Nutrition provenance from a loaded nutrition authority is separate from recipe-source counts.

Invented citation = Critical.

---

### Pass 4 - Equipment, geometry, and occasion fit
Check `equipment.md`:
- listed tools exist or have compliant substitutions;
- pan/material calibration applied;
- crowding/layer depth explicit where important;
- covered/uncovered and evaporation plan explicit;
- vessel capacity matches yield;
- avoid-unless-necessary/retired gear justified;
- ceramic nonstick not used for inappropriate high-heat searing/broiling.

Also verify geometry supports the resolved occasion: serving count, holding plan, travel plan, and any batch workflow must be physically realistic.

When `workflow-meal-prep` is active:
- default batch does not exceed realistic vessel surface area/capacity;
- doubling is not implemented by merely extending cook time when batching is required;
- portion count matches stated batch plan.

---

### Pass 5 - Timing, holding, storage, and reheat plausibility
Check:
- Active Prep + Inactive / Hands-Off + Cook is approximately consistent with Total; flag discrepancies greater than about 10 minutes unless overlapping/parallel timing explains them;
- step times plausible for heat, geometry, and portion size;
- parallel tasks fit active-prep estimate;
- sensory cues align with ranges;
- rests present when materially needed;
- hold/service windows are plausible for the selected occasion.

When storage/reheat instructions are present or required:
- fridge/freezer plan internally coherent;
- freeze point makes culinary sense;
- thaw path matches food format;
- reheat method/time matches portion size and starting state;
- texture-reset step addresses likely degradation;
- Make-Ahead Notes and Reheat Plan do not contradict each other.

---

### Pass 6 - Internal contradiction
Verify:
- every ingredient used is listed and every listed ingredient is used;
- Grocery List parity and no duplicates;
- heat/temperature references do not conflict;
- yield fits vessel capacity;
- troubleshooting does not contradict instructions;
- allergen/Contains line matches ingredients;
- variations do not violate locks;
- Common Issues and Troubleshooting agree;
- occasion directives do not contradict serving/hold/storage instructions;
- active special-instruction sections agree with the base recipe and each other.

When `workflow-meal-prep` is active:
- storage/freezer/reheat instructions agree;
- loaded diet/personal toggles are coherent with base ingredients;
- no loaded hard/default avoid reappears in a variation unless explicitly overridden;
- Nutrition Snapshot serving definition matches recipe yield/portioning.

---

### Pass 7 - User, occasion, and special-instruction compliance
Verify:
- every direct user request is satisfied or explicitly acknowledged;
- rejected ingredients/techniques/formats absent;
- occasion optimize/avoid axes are reflected in method/serving choices;
- selected modifiers are justified;
- requested research depth met;
- make-ahead preference honored;
- every active special instruction was applied;
- inactive special instructions did not leak.

When `workflow-meal-prep` is active:
- batch/portioning matches the workflow or explicit override;
- `meal_prep_health_guidelines.md` followed unless overridden;
- `meal_prep_personal_health.md` followed unless overridden;
- freezer/reheat quality treated as design constraint;
- sodium drivers/levers handled as required;
- nutrition methodology follows `meal_prep_nutrition.md` unless explicitly opted out;
- ASCII-only output contract followed.

---

### Pass 8 - Nutrition provenance (when Nutrition Snapshot is present/required)
If `meal_prep_nutrition.md` is the active nutrition authority, check:
- Nutrition Snapshot is present when required unless explicitly opted out;
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
| **Major** | High reliability risk, silent occasion/special-instruction/lock violation, or major structural inconsistency. |
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
4. Re-emit the complete artifact using the same resolved occasion context unless the user changed it.
5. Do not emit internal audit chain-of-thought/workflow notes.
6. Append one summary line: `[N Critical, N Major, N Minor fixes applied; N Minor issues noted but not applied.]`

---

## Completion checklist
- artifact type identified;
- occasion context identified;
- special-instruction hooks resolved;
- thread locks recovered;
- all applicable passes completed;
- special-instruction isolation checked;
- issues severity-ordered;
- corrected artifact uses same occasion context unless user changed it;
- nutrition pass completed when applicable.
