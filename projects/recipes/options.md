# Options List Template (Canonical)

## Purpose
Generate a short, scannable shortlist that:
- obeys the resolved occasion context from `occasions.md`;
- is grounded in authentic, cross-checked research per `meal_sources.md`;
- obeys any specialized authorities loaded by the active occasion or explicit user request;
- is formatted for fast decision-making.

---

## Emission policy

### Internal-only workflow sections
Compute before drafting but do not emit unless explicitly requested:
- Occasion context resolution
- Occasion directive extraction
- Specialized-authority extraction (only when active)
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
[2-3 sentences: desired food, time window, equipment preferences, vibe/flavor direction, and occasion/use case when relevant. If a health/composition authority materially shapes ranking, describe the practical goal in plain language without naming internal files or resolver state.]

### Context & Constraints
- Occasion / use case: [plain-language only; omit when not meaningful]
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

Do not expose internal base/modifier IDs in this user-visible section unless the user explicitly asks to inspect occasion resolution.

When `workflow-meal-prep` is active, include batch/portion/freezer requirements here only when they materially differ from workflow defaults.

---

## Internal workflow

### Occasion context resolution
Resolve per `occasions.md`:
- Base occasion:
- Workflow modifier:
- Seasonal modifier:
- Setting modifier:
- Service modifier:
- Menu modifier:
- Why each modifier is active:
- Thread overrides to occasion defaults:

Use `general-cooking` when no specialized base is justified. Preserve exact legacy `meal-prep-batch` as the simple batch-cooking base rather than converting it to `workflow-meal-prep`.

### Occasion directive extraction
Combine the base and modifiers without silently discarding constraints.
- Optimize (2-6 bullets)
- Avoid (2-6 bullets)
- Assumptions to honor
- Options-directives
- Recipe-directives to carry forward
- If modifiers are used, validate that each belongs to the correct axis.
- Resolve audience/yield versus batch-yield semantics per `instructions.md`.

### Specialized-authority extraction (only when active)
For each selected occasion/modifier with `special-instructions`, or each explicit request-scoped authority:
- Files loaded
- Interaction rules
- Research-budget overrides
- Output/format rules relevant to options
- User overrides to those defaults
- Notes to carry forward to a full recipe

For `workflow-meal-prep`, this must include:
- batch/portion target;
- fridge/freezer strategy;
- freezer/reheat constraints;
- general composition defaults applied;
- personal defaults applied;
- personal/workflow defaults overridden.

For request-scoped health/composition guidance, apply only the requested health goal; do not activate Meal Prep batch/storage/personal defaults. For request-scoped numeric nutrition, carry the nutrition requirement forward without changing option ranking unless the user supplied a nutrient target.

Do not replace base or seasonal/setting/service/menu directives with workflow constraints; apply all selected axes.

### Research execution
Follow `meal_sources.md` for quality, deduplication, authenticity, disagreement handling, regional anchors, no-inference, safety, and comment mining.

Research budget:
- default: use `meal_sources.md` mode-specific targets;
- if an active occasion declares a research-budget override, use that count while retaining all `meal_sources.md` quality rules.

### Research outputs
- Recurring failure modes (>= 3)
- Guardrails / corrective adjustments (>= 3)
- Key disagreements and reconciliation
- Notes to carry forward to recipe step

When `workflow-meal-prep` is active, at least one failure-mode/guardrail should address storage, freezing, reheating, batch geometry, or portioning when materially relevant.

### Breadth scan before ranking
Search at least 3 materially different buckets:
- obvious dish/category;
- adjacent cuisines/regional analogs;
- target eating experience;
- equipment fit;
- occasion fit;
- active specialized-authority fit when relevant.

Do not finalize until at least 3 materially different buckets have actually been explored.

Optional idea buckets when the search space is repetitive: quick skillet, sheet-pan/roast, grill/smoker, braise/stew, stir-fry, filled items, one-pot pasta/risotto, breads/doughs, sauces/condiments, sandwiches/tacos/wraps, no-cook assemblies, party bites, boards/grazing.

---

## Formatting rules
- Preserve section headers and order.
- Each shortlist option is its own block separated by a blank line.
- Target about 6 lines per shortlist option; maximum 7 unless the user requests more detail.
- No raw URLs in shortlist/runner-ups/chooser rules.
- Use numeric footnote markers `[n]` for sourced claims.
- URLs belong only in Sources.
- Never invent links.
- If no external browsing occurred, write exactly: `No external browsing performed; sources omitted.` Then omit footnotes and omit the Sources section.
- Avoid quantities unless essential.
- Use U.S. customary units by default.
- Bold option names and field labels; do not bold whole sentences.
- Apply any active occasion-specific output contract. `workflow-meal-prep` uses the ASCII-only contract in `occasions.md`.

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
- when specialized authorities materially shape selection, Why it fits must also address at least one relevant constraint.

Avoid vague cultural-label-only descriptions. Describe the actual dish, eating experience, and meaningful differentiator.

Source-family counts:
- default: follow `meal_sources.md`;
- active occasion research-budget overrides take precedence for counts only.

### Distinctness guardrails
For broad prompts:
- at least 3 distinct formats;
- no more than 2 options in the same format;
- no more than 2 sharing the same primary protein/center-of-plate.

When the user/occasion strongly constrains format, diversify across at least 3 of:
- protein/center-of-plate;
- sauce/base style;
- method;
- flavor profile;
- holding strategy;
- make-ahead strategy;
- storage/reheat strategy when relevant.

### Per-option template
#### 1) **[Option Name]** [tags: 3-5; format: ...; active: ~X min (est); effort: low|med|high]
**Description:** [what it is + eating experience + distinctiveness + familiar comparison when needed]
**Flavor profile:** richness [light|med|rich]; acidity [low|med|high]; heat [none|low|med|high]; notes: [2-4]; texture: [1-2]
**Make-ahead:** [what]. **Hold/Reheat:** [how + cue; use Hold terminology for party/grazing contexts]
**Watch:** [research-derived failure mode/guardrail]. **Why it fits:** [goal + resolved occasion/use case + equipment + material specialized constraint if applicable]
**Source:** [Blog|YT|IG|Forum|Authoritative]. [n]

Tag guidance: 3-5 tags from `tags.md`.

---

## Runner-Ups (5 to 10)
One-liners only. Each needs a hook plus a key technique/protein or why it was bumped.
Only footnote runner-ups traceable to the researched source pool. In no-browse mode, runner-ups are unsourced brainstorm additions and receive no footnotes.

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
- Best fit for an active workflow constraint (for personalized Meal Prep: freezer/reheat performance)

---

## Optional Comparative Matrix
Use when there are >= 6 shortlist options or when occasion/specialized constraints create meaningful holding, storage, or coordination tradeoffs.

| Option | Format | Active (est) | Effort | Make-ahead | Hold/Reheat | Biggest watch | Why it fits |
|---:|---|---:|---|---|---|---|---|
| 1 |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |

---

## Sources
**Default:** plain URLs only, one per numbered entry, matching in-text `[n]` markers.

If an active occasion defines richer source metadata, follow it. `workflow-meal-prep` preserves source name, raw URL, source type, supported region when known, and why the source was used. Raw URLs remain confined to this section unless the user requests inline links.
