# [Theme] Options List

## Purpose
Generate a short, scannable shortlist of recipe ideas that:
- obeys default health constraints and avoidances (per `healthy_excludes.md`, unless the user overrides),
- is grounded in authentic, cross-checked research (per `meal_sources.md`),
- and is formatted for fast decision-making (this file).

---

## Authoritative references (do not restate)
- Health constraints, ingredient exclusions, GI guidance, sodium levers, and cooking-method defaults:
  - `healthy_excludes.md`
- Research, sourcing, authenticity checks, disagreement reconciliation, comment-mining, and safety/correctness discipline:
  - `meal_sources.md`
- Tag vocabulary (if present):
  - `tags.md`

This file defines the options-stage interface: required inputs, internal workflow outputs, and options-specific formatting rules.

---

## Emission policy (critical)

### Internal-only workflow sections (compute but DO NOT emit)
These sections are required for correctness and should be completed internally, but must NOT appear in the final user-visible output:
- Constraint extraction (required)
- Research execution (binding)
- Research outputs (required)

Rules:
- You must complete the internal-only sections before writing the Shortlist, because they drive ranking, phrasing, and the Watch lines.
- In the final output, do not include the internal-only section headers or their contents.
- If the user asks to see internal-only sections, include them only if explicitly requested.

### Final output sections (emit in this order)
1. Required inputs (filled before research)
2. Shortlist (Top 5 to 8)
3. Runner-Ups (5 to 10)
4. Pick First / If You Want...
5. Optional: Comparative Matrix (only if triggered)
6. Sources (only if external browsing was performed; otherwise omit)

---

## Required inputs (fill before research)

### Title & Goal
[2-3 sentences: what you want, time window, equipment preferences, vibe/flavor direction, and what "healthy" means here (qualitative). State that options are sourced broadly with authenticity priority.]

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

---

## Internal-only workflow sections (do not emit)

### Constraint extraction (required)
Summarize the constraints that will shape the shortlist.
- User musts (2-6 bullets):
- User avoids (2-6 bullets):
- Health defaults applied (2-6 bullets):
- Health defaults overridden (if any):
- Options-stage directives (must shape option proposals):
  - e.g., sodium-aware by default; heat as a toggle; veg-forward; make-ahead path required
- Notes to carry forward to the recipe step (only if the user is likely to pick a full recipe next):

### Research execution (binding)
Execute research strictly per `meal_sources.md`.

No protocol restatement here. The only requirement this file adds is:
- The shortlist must be demonstrably informed by the Research outputs below.

### Research outputs (required)
These are the distilled outputs of `meal_sources.md` that directly feed the shortlist.
Failure modes and guardrails must primarily come from comment-mining and cross-recipe comparisons, not just the source author's main recipe text.

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
- Notes to carry forward to the recipe step (from constraint extraction + notable source constraints):
  - 1)
  - 2)

---

## Options-stage non-negotiables (formatting)

### Structure and headers (readability)
- Keep the section headers as written in the FINAL output sections list.
- Leave at least one blank line between sections.
- Each Shortlist option must be its own block and separated by a blank line.

### URL and citation rules
- Do NOT embed raw URLs in the Shortlist, Runner-Ups, or chooser rules.
- Use numeric footnote markers like [1] only.
- Put URLs only in the Sources section (plain URLs; one per line; strip tracking params when practical).
- Never invent links.
- If external browsing is not available: write "No external browsing performed; sources omitted."
  - Then omit footnotes and omit the Sources section entirely.

### Units policy (options-stage)
- Avoid quantities in options unless essential.
- If you include quantities, use U.S. customary units.
- Add metric in parentheses only if pulled directly from a source.

### Bolding rules (selective)
- Bold the option name.
- Bold field labels (e.g., Description:, Watch:, Why it fits:).
- Optionally bold one key endpoint or decision per option (e.g., broil 3-5 min, reduce sauce, sheet-pan finish).
- Do not bold whole sentences.

---

## Shortlist (Top 5 to 8)

### Shortlist rules (options-stage specific)
- Each option must cite one primary source [n].
- The shortlist as a whole should be supported by the full source set from `meal_sources.md`.
  - Multiple options may map to the same source as needed, but research must still be cross-checked across the 5-7 sources.
- Each option must contain:
  - a Description line (1-2 sentences; plain-language; no jargon),
  - a Watch line derived from Research outputs (failure mode or guardrail),
  - a Why it fits line tying back to the goal plus at least one constraint (user must/avoid or health default).
- The Watch line must reference one of the listed failure modes/guardrails verbatim or near-verbatim (not generic filler).
- Do not mention every constraint in every option. Mention only what materially differentiates it.

### Distinctness guardrails
Default (broad prompts):
- Include at least 3 distinct formats across the shortlist.
- No more than 2 options in the same format.
- No more than 2 options sharing the same primary protein/center-of-plate.

If the Title & Goal or constraints strongly narrow the space (e.g., "all sheet-pan," "all bowls," "all party bites"):
- Treat that constraint as fixed.
- Diversify across at least 3 of these axes:
  - protein/center-of-plate
  - sauce/base style
  - cooking method within format
  - flavor profile
  - holding strategy
  - make-ahead strategy

### Per-option template (target 6 lines; max 7)
Formatting requirement: use a level-4 header per option and leave a blank line between options.

#### 1) **[Option Name]** [tags: 3-5; format: ...; active: ~X min (est); effort: low|med|high]
**Description:** [1-2 sentences: what it is and what it eats like.]
**Flavor profile:** richness [light|med|rich]; acidity [low|med|high]; heat [none|low|med|high]; notes: [2-4 descriptors]; texture: [1-2 descriptors]
**Make-ahead:** [what]. **Hold/Reheat:** [how + cue] (use "Hold" for party/grazing contexts)
**Watch:** [1 failure mode or guardrail from Research outputs]. **Why it fits:** [tie to goal + 1+ constraint]
**Source:** [Blog|YT|IG|Forum|Authoritative]. [n]

Tag guidance:
- Use 3-5 tags max.
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
4-7 chooser rules routing to specific options (1-2 options per rule).
Chooser rules should reflect constraints when relevant.
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
- Use the matrix when there are >= 6 shortlist options, OR
- when the selected constraints imply holding/coordination tradeoffs.

Keep it compact; do not add new claims here.

| Option | Format | Active (est) | Effort | Make-ahead | Hold/Reheat | Biggest watch | Why it fits |
|---:|---|---:|---|---|---|---|---|
| 1 |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |

---

## Sources
Rules:
- Plain URLs only, one per line.
- Each URL number must match the in-text [n] markers used above.

1. https://example.com/
2. https://example.com/
