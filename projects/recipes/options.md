# Options List Template (Canonical)

## Purpose
Generate a short, scannable shortlist that:
- obeys occasion directives from `occasions.md`;
- is grounded in authentic, cross-checked research per `meal_sources.md`;
- obeys the active profile selected by `instructions.md`;
- is formatted for fast decision-making.

When `meal-prep` is active, also apply `meal_prep.md`, `meal_prep_health_guidelines.md`, and `meal_prep_personal_health.md`.

---

## Emission policy

### Internal-only workflow sections
Compute before drafting but do not emit unless explicitly requested:
- Active profile confirmation
- Occasion selection
- Occasion directive extraction
- Meal Prep constraint extraction (Meal Prep only)
- Research execution
- Research outputs

### Final output sections
1. Required inputs
2. Shortlist (Top 5 to 8)
3. Runner-Ups (5 to 10)
4. Pick First / If You Want...
5. Optional Comparative Matrix
6. Sources (only if external browsing was performed)

---

## Required inputs

### Title & Goal
[2-3 sentences: desired food, time window, equipment preferences, vibe/flavor direction, target occasion, and active profile when relevant.]

### Context & Constraints
- Profile: [standard | meal-prep]
- Serves:
- Time:
  - Active:
  - Total:
- Target eating model:
- Anti-target model:
- Effort tolerance: [low | med | high]
- Skill level: [novice | comfortable | advanced]
- Equipment on hand: [default `equipment.md` inventory; list only exceptions/additions]
- Allergies / avoidances:
- Heat tolerance: [mild | medium | hot]
- Make-ahead preference: [none | partial | components day-before | full day-before OK]
- Notes / assumptions:

For Meal Prep, include batch/portion/freezer requirements here when they materially differ from the profile defaults.

---

## Internal workflow

### Active profile confirmation
- Profile:
- Why active:
- Thread overrides to profile defaults:

### Occasion selection
Select one base + optional modifiers per `occasions.md`.

### Occasion directive extraction
- Optimize (2-6 bullets)
- Avoid (2-6 bullets)
- Assumptions to honor
- Options-directives
- Recipe-directives to carry forward

### Meal Prep constraint extraction (only when active)
Summarize without emitting:
- Batch/portion target
- Fridge/freezer strategy
- Freezer/reheat constraints
- General composition defaults applied
- Personal defaults applied
- Personal/profile defaults overridden
- Notes to carry forward to full recipe

Do not replace occasion directives with Meal Prep constraints; apply both.

### Research execution
Follow `meal_sources.md` for quality, deduplication, authenticity, disagreement handling, regional anchors, and comment mining.

Research budget:
- Standard: use `meal_sources.md` mode-specific targets.
- Meal Prep: use the profile budget in `meal_prep.md` unless the user requests Standard-depth source counts.

### Research outputs
- Recurring failure modes (>= 3)
- Guardrails / corrective adjustments (>= 3)
- Key disagreements and reconciliation
- Notes to carry forward to recipe step

In Meal Prep, at least one failure-mode/guardrail should address storage, freezing, reheating, batch geometry, or portioning when materially relevant.

### Breadth scan before ranking
Search at least 3 materially different buckets:
- obvious dish/category;
- adjacent cuisines/regional analogs;
- target eating experience;
- equipment fit;
- occasion fit;
- Meal Prep only: freezer/reheat/constraint fit.

---

## Formatting rules
- Preserve section headers and order.
- Each shortlist option is its own block separated by a blank line.
- No raw URLs in shortlist/runner-ups/chooser rules.
- Use numeric footnote markers `[n]` for sourced claims.
- URLs belong only in Sources.
- Never invent links.
- If no external browsing occurred, omit footnotes and Sources; do not fabricate placeholders.
- Avoid quantities unless essential.
- Use U.S. customary units by default.
- Bold option names and field labels; do not bold whole sentences.

---

## Shortlist (Top 5 to 8)
Each option must include:
- one primary source `[n]` when browsing occurred;
- what the dish is;
- what it eats like;
- what distinguishes it from the other options;
- a familiar comparison when useful;
- one research-derived Watch item;
- Why it fits, tied to occasion directives and equipment;
- Meal Prep only: Why it fits must also address at least one meaningful profile constraint such as freezer/reheat reliability, portionability, batch geometry, or configured food constraints.

Source-family counts:
- Standard: follow `meal_sources.md`.
- Meal Prep: follow `meal_prep.md`.

### Distinctness guardrails
For broad prompts:
- at least 3 distinct formats;
- no more than 2 options in the same format;
- no more than 2 sharing the same primary protein/center-of-plate.

When the user constrains format, diversify across at least 3 of:
- protein/center-of-plate;
- sauce/base style;
- method;
- flavor profile;
- holding strategy;
- make-ahead strategy;
- Meal Prep: freezer/reheat strategy.

### Per-option template
#### 1) **[Option Name]** [tags: 3-5; format: ...; active: ~X min (est); effort: low|med|high]
**Description:** [what it is + eating experience + distinctiveness + familiar comparison when needed]
**Flavor profile:** richness [light|med|rich]; acidity [low|med|high]; heat [none|low|med|high]; notes: [2-4]; texture: [1-2]
**Make-ahead:** [what]. **Hold/Reheat:** [how + cue]
**Watch:** [research-derived failure mode/guardrail]. **Why it fits:** [goal + occasion + equipment + Meal Prep constraint if active]
**Source:** [Blog|YT|IG|Forum|Authoritative]. [n]

Tag guidance: 3-5 tags from `tags.md`.

---

## Runner-Ups (5 to 10)
One-liners only. Each needs a hook plus a key technique/protein or why it was bumped.
Only footnote runner-ups traceable to the researched source pool.

---

## Pick First / If You Want...
Use 4-7 chooser rules routing to specific options.
Recommended axes:
- Fastest path to food
- Lowest coordination load
- Best make-ahead / holding
- Minimal cleanup
- Most impressive for effort
- Most crowd-friendly
- Easiest allergy/avoidance-friendly with trivial swaps
- Meal Prep only: best freezer/reheat performance

---

## Optional Comparative Matrix
Use when there are >= 6 shortlist options or when occasion/profile constraints create meaningful holding, freezer, or coordination tradeoffs.

| Option | Format | Active (est) | Effort | Make-ahead | Hold/Reheat | Biggest watch | Why it fits |
|---:|---|---:|---|---|---|---|---|
| 1 |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |

---

## Sources
Plain URLs only, one per numbered entry, matching in-text `[n]` markers.
