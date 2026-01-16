# 20260115_options.md
# Options List Template (Canonical)

## Purpose
Generate a short, scannable shortlist of recipe ideas that:
- obeys **Occasion directives** (from `occasions.md`),
- is grounded in **authentic, cross-checked research** (per `meal_sources.md`),
- and is formatted for fast decision-making (this file).

---

## Authoritative references (do not restate)
- Research, sourcing, authenticity checks, disagreement reconciliation, comment-mining, and safety/correctness discipline:
  - `meal_sources.md`
- Occasion selection, modifiers, and directive schema (optimize/avoid/assumptions/options-directives/recipe-directives):
  - `occasions.md`
- Tag vocabulary (if present):
  - `tags.md`

This file defines the **options-stage interface**: required inputs, required outputs, and options-specific formatting rules.

---

## Required inputs (fill before research)

### Title & Goal
[2–3 sentences: what you want, time window, equipment preferences, vibe/flavor direction, and the target occasion.]

### Context & Constraints
- Serves:
- Time:
  - Active:
  - Total:
- Effort tolerance: [low | med | high]
- Skill level: [novice | comfortable | advanced]
- Equipment on hand:
- Allergies / avoidances:
- Heat tolerance: [mild | medium | hot]
- Make-ahead preference: [none | partial | components day-before | full day-before OK]
- Notes / assumptions:

### Occasion selection (binding)
Select one base + optional modifiers **per `occasions.md`**.
- Occasion base:
- Occasion modifiers (optional):
  - setting:
  - service:
  - menu:

---

## Occasion directive extraction (required)
Summarize the selected occasion entry from `occasions.md` into a constraint set used to rank options.
Do not paste the full occasion block.

- Optimize (2–6 bullets):
- Avoid (2–6 bullets):
- Assumptions to honor:
- Options-directives (must shape option proposals):
- Recipe-directives (carry-forward notes only; do not bloat shortlist):
- Modifier validation note (only if used):
  - confirm selected modifiers are actual modifiers (setting/service/menu), not seasonal bases

---

## Research execution (binding)
Execute research **strictly per `meal_sources.md`**.

No protocol restatement here. The only requirement this file adds is:
- The shortlist must be demonstrably informed by the Research Outputs section below.

---

## Research outputs (required)
These are the distilled outputs of `meal_sources.md` that directly feed the shortlist.
Failure modes and guardrails must primarily come from **comment-mining** and **cross-recipe comparisons**, not just the source author’s main recipe text.

- Recurring failure modes (>= 3):
  - 1)
  - 2)
  - 3)
- Guardrails / corrective adjustments (>= 3):
  - 1)
  - 2)
  - 3)
- Key disagreements discovered (temps/times/ratios/sequence) and how reconciled (brief):
  - 1)
  - 2)
- Notes to carry forward to the recipe step (from recipe-directives + notable source constraints):
  - 1)
  - 2)

---

## Options-stage non-negotiables (formatting)
- Do NOT embed raw URLs in the Shortlist, Runner-Ups, or chooser rules.
- Use numeric footnote markers like [1] only.
- Put URLs only in the Sources section (plain URLs; one per line; strip tracking params when practical).
- Never invent links.
- If external browsing is not available: write "No external browsing performed; sources omitted."
  - Then omit footnotes and omit the Sources section entirely.

Units policy (options-stage):
- Avoid quantities in options unless essential.
- If you include quantities, use U.S. customary units.
- Add metric in parentheses **only if pulled directly from a source**.

---

## Shortlist (Top 5 to 8)

### Shortlist rules (options-stage specific)
- Each option is **5 lines max** (target 5; never exceed 6).
- Each option must cite **one primary source** [n].
- The shortlist as a whole should be supported by the full source set from `meal_sources.md`.
  - Multiple options may map to the same source as needed, but research must still be cross-checked across the 5–7 sources.
- Each option must contain:
  - a “Watch” line derived from Research Outputs (failure mode or guardrail),
  - a “Why it fits” line explicitly referencing at least **one** Occasion directive (optimize/avoid/assumptions/options-directives).
- The “Watch” line must reference one of the listed failure modes/guardrails **verbatim or near-verbatim** (not generic filler).
- Do not mention every constraint in every option. Mention only what materially differentiates it.

### Distinctness guardrails
Default (broad prompts):
- Include at least **3 distinct formats** across the shortlist.
- No more than **2** options in the same format.
- No more than **2** options sharing the same primary protein/center-of-plate.

If the Title & Goal or Occasion directives constrain the space (e.g., “grazing table,” “cocktail bites,” “bring-over,” “all sheet-pan,” “all pasta”):
- Treat that constraint as fixed.
- Diversify across at least 3 of these axes:
  - protein/center-of-plate
  - sauce/base style
  - cooking method within format
  - flavor profile
  - holding strategy
  - make-ahead strategy

### Per-option template (target 5 lines; max 6)
- **[Option Name]** [tags: 3–5; format: ...; active: ~X min (est); effort: low|med|high]
  Flavor profile: richness [light|med|rich]; acidity [low|med|high]; heat [none|low|med|high]; notes: [2–4 descriptors]; texture: [1–2 descriptors]
  Make-ahead: [what]. Hold/Reheat: [how + cue] (use “Hold” for party/grazing contexts)
  Watch: [1 failure mode or guardrail from Research Outputs]. Why it fits: [tie to goal + 1+ occasion directive]
  Source [Blog|YT|IG|Forum|Authoritative]. [n]

Tag guidance:
- Use 3–5 tags max.
- If tags.md exists, select from it; do not invent a new taxonomy mid-list.

Idea buckets (for diversity or pivoting; optional):
- quick skillet, sheet-pan/roast, grill/smoker, braise/stew, stir-fry, filled items, one-pot pasta/risotto, breads/doughs, sauces/condiments, sandwiches/tacos/wraps, no-cook assemblies, party bites, boards/grazing.

---

## Runner-Ups (5 to 10)
One-liners only. Each must include:
- a hook, and
- either a key technique, main protein/center-of-plate, or why it was bumped.

Footnote only if a runner-up is actually sourced.
- [One-liner...]
- ...

---

## Pick First / If You Want...
4–7 chooser rules routing to specific options (1–2 options per rule).
Chooser rules should reflect Occasion directives when relevant.
- Fastest path to food:
- Lowest coordination load:
- Best make-ahead / holding:
- Minimal cleanup:
- Most impressive for the effort:
- Most crowd-friendly:
- Easiest allergy/avoidance-friendly with trivial swaps (if relevant):

---

## Optional: Comparative Matrix
Use when a table clarifies selection.

Trigger rules:
- Use the matrix when there are **>= 6** shortlist options, OR
- when the selected occasion implies holding/coordination tradeoffs (e.g., party-10
