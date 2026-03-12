# Recipe Revisions Instruction Set (Home-Cook Friendly)

**Purpose:** When a dish cooks wrong or tastes off, use this playbook to (1) diagnose, (2) verify whether others hit the same failure mode, (3) reconcile similar recipes, (4) propose practical, evidence-based fixes, and (5) produce an updated recipe.

**Assumption:** You will attach a Markdown copy of the recipe. If you only have a short description, proceed and ask minimal, answerable follow-ups only if needed.

**Sourcing rule:** Do NOT restate or reinvent the research workflow here. Follow `meal_sources.md` for source tiers, search protocol, authenticity signals, comment mining, variant matrix structure, safety/correctness checks, and attribution format.

**Constraint rule:** Revisions must remain compatible with `healthy_excludes.md` unless the user explicitly requests a deviation.

---

## 0) What You Provide (Super Short)
Minimum:
- **Recipe file:** attach the Markdown (preferred).
  - If not available: one-sentence description of the dish + what went wrong.
- **What went wrong (1–2 lines):** e.g., "dry and bland," "center undercooked," "sauce split."
- **Any swaps/changes:** e.g., "used low-sodium broth," "baked in 9x13 metal pan," "halved recipe."

Helpful (only if easy):
- Pan/pot size + material
- Covered/uncovered (and when)
- Approx thickness / layer depth
- Whether the issue happened fresh, on reheat, or both

> If we truly need more info, we only ask simple, kitchen-level questions (see 2b).

---

## 1) Classify the Problem (Pick 1–3)
- **Doneness/Timing:** undercooked center, overcooked edges, took longer/shorter than stated
- **Texture/Structure:** dry/tough, watery/thin, greasy, gummy/dense, grainy, split, curdled
- **Flavor Balance:** too salty, flat/bland, too sour/bitter/sweet, harsh aftertaste
- **Workflow/Complexity:** too many pans, fussy timing, hard to coordinate
- **Equipment/Scaling:** pan size/material mismatch, doubled batch, crowded pan
- **Allergy/Swaps:** substitution broke texture or flavor

---

## 1a) Locked Decisions and Constraint Carry-Forward (Required)
Before proposing fixes, list and preserve thread-level constraints:
- selected option/variation,
- equipment limits,
- pan/tray count,
- ingredient-source constraints,
- format requests,
- rejected paths that must not reappear,
- health constraint overrides the user stated (to `healthy_excludes.md` defaults).

Health constraint baseline: hard avoids (tilapia, catfish, chocolate) and safety rules carry forward unconditionally. Soft avoids and preference defaults carry forward unless the user has explicitly overridden them in this thread.

If a proposed fix conflicts with a locked decision or unoveridden health constraint, either:
- provide a compliant alternative, or
- call out the conflict and ask for explicit permission to break the lock.

---

## 2) Quick Triage (Big Levers First)

### 2a) No-Ask Checks (from your Markdown or description)
We check:
- **Geometry:** vessel size vs batch thickness; rack position if oven
- **Heat path:** preheat present; browning steps are plausible
- **Moisture management:** whether reduction/evaporation was possible (covered vs uncovered)
- **Salty inputs:** cheese, soy, broth, brined items, salted butter; reduction risk
- **Crowding:** portion count vs surface area; steaming risk
- **Sequence integrity:** acid/dairy order, emulsion steps, rest times

### 2b) If needed, minimal follow-ups
Ask the smallest set that resolves ambiguity:
- Pan size & material?
- Oven/stove settings actually used?
- Approx thickness / layer depth?
- Covered or uncovered (and when)?
- Any substitutions?
- Did the pan feel crowded (yes/no)?
- Did it sizzle on contact (yes/no)?

Do not ask for BTUs, exact salt %, oven calibration reports, flour protein %, or anything else a home cook cannot reasonably know.

---

## 3) Root-Cause Hypotheses (Required)
Before prescribing changes, state:
- **Hypothesis A:** [one sentence cause] — **confidence:** [high|med|low]
- **Hypothesis B (optional):** [one sentence cause] — **confidence:** [high|med|low]

Rules:
- Hypotheses must be **falsifiable**: each must imply a specific cue/test that could disprove it.
- Every proposed change must map to Hypothesis A or B.
- If a change does not map cleanly, it does not belong in the minimal update.

---

## 4) Research and Corroboration (Use meal_sources.md)
Follow `meal_sources.md` end-to-end. Revision-specific emphasis:
- Build queries around the **failure mode** (symptom keywords) in addition to the dish name.
- Prefer sources that explicitly discuss **mistakes, troubleshooting, corrections, ratio debates, pan geometry, and sensory cues**.
- Treat video/social as valid when it contains replicable steps and/or high-signal Q&A; corroborate key fixes before prescribing.
- When sources disagree, use this decision protocol:
  1) Prefer sources addressing the **same failure mode** explicitly.
  2) Prefer sources whose **equipment + geometry** match (pan size, thickness, covered/uncovered).
  3) Prefer the approach that is **physics-consistent** with the symptom and the method (evaporation path, browning feasibility, emulsion stability).

---

## 5) Reconcile With a Variant Matrix (Use meal_sources.md)
Use the `meal_sources.md` variant matrix approach, but tailor rows to the failure:
- Add rows for the most likely failure drivers (layer depth, covered/uncovered, reduction endpoint, emulsification order, salinity inputs).
- Prefer **ratio bands** over single point numbers.
- Record the "why" for each proposed change in one line (geometry, moisture, browning, emulsion stability).

---

## 6) Geometry and Moisture Sanity Checklist (Required Before Final Output)
Confirm and make explicit in your revised recipe:
- Vessel type and size are specified (and reasonable for the batch).
- Layer depth is stated or bounded (e.g., "no deeper than ~1 inch").
- Covered/uncovered plan is explicit (including when the lid/foil comes off).
- Evaporation/reduction path exists for sauces (wide enough pan; uncovered finish).
- Crowding risk is addressed (batching or wider vessel if needed).

---

## 7) Safety and Correctness Pass (Use meal_sources.md)
Follow `meal_sources.md` safety and technique-correctness checks.
- If citing food-safety facts (cooling, storage, minimum internal temperatures), include at least one authoritative reference (USDA/FDA) in the Updated Recipe Sources section.
- Verify all temperature and timing claims are physically plausible and consistent with the stated method.
- Flag and fix steps that are clearly wrong unless strong multi-source evidence supports them.
- Keep safety corrections concise; do not overload the recipe with safety caveats.

---

## 8) Fix Design Rules
- Keep fixes minimal but decisive.
- Prefer ratio bands and sensory cues over brittle single numbers.
- Include at least one preventive guardrail for each high-confidence failure mode.
- Preserve user intent, flavor direction, and health constraint compliance while repairing reliability.
- Do not introduce ingredients that conflict with `healthy_excludes.md` hard avoids or the user's locked constraints.

---

## Emission Policy

**Internal-only sections (compute but DO NOT emit):**
- §0 through §8 (intake, failure classification, locked decisions, triage, hypotheses, research, variant matrix, geometry, safety, fix design)

**Emitted output (in this order):**
- A) Diagnosis Summary
- B) What Changes and Why
- C) Updated Recipe (full drop-in in `healthy_template.md` format)
- D) Optional Validation Plan (include only if useful)

---

## 9) Required Output Shape

### A) Diagnosis Summary
- Failure class(es)
- Hypothesis A/B with confidence
- Evidence summary from corroboration

### B) What Changes and Why
- Change list (old -> new)
- Why each change maps to a hypothesis
- Any locked-decision or health-constraint conflict and resolution

### C) Updated Recipe
Emit a full drop-in replacement recipe in `healthy_template.md` format.

Required in Updated Recipe:
- inventory-aware equipment list (per `equipment.md` §1),
- explicit geometry limits,
- explicit covered/uncovered and reduction plan,
- Gather & Stage standalone section (before numbered instructions),
- Reheat Plan section,
- Nutrition Snapshot (per serving) per `nutrition_calculation_method.md`,
- troubleshooting entries for the observed failure mode.

### D) Optional Validation Plan
If useful, include one short next-cook validation checklist (2 to 5 bullets).
