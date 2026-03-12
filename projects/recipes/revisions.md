# Recipe Revisions Instruction Set (Home-Cook Friendly)

Purpose: when a dish cooks wrong or tastes off, use this playbook to diagnose root causes, corroborate fixes, and output a corrected recipe that the user can cook immediately.

Sourcing rule: do not restate or reinvent the research workflow here. Follow `meal_sources.md` for source tiers, search protocol, strict source-family dedup, comment mining, variant matrix structure, and safety/correctness checks.

Equipment rule: revisions must diagnose against the actual inventory and constraints in `equipment.md`, not generic ideal equipment.

Carry-forward rule: preserve accepted user decisions and hard constraints from earlier turns unless the user explicitly changes them.

---

## 0) What You Need From the User
Minimum:
- Recipe markdown (preferred), or a short dish description if markdown is unavailable.
- What went wrong (1 to 2 lines).
- Any swaps/changes made.

Helpful if easy:
- Pan/pot size and material.
- Covered/uncovered timing.
- Approx thickness/layer depth.
- Whether the issue happened fresh, on reheat, or both.

Ask follow-ups only when ambiguity blocks a reliable fix.

---

## 1) Classify the Failure (Pick 1 to 3)
- Doneness/timing: undercooked center, overcooked edges, too slow/fast.
- Texture/structure: dry, watery, greasy, split, dense, gummy.
- Flavor balance: too salty, bland, too sour/sweet/bitter.
- Workflow/complexity: too many pans, fragile timing, hard coordination.
- Equipment/geometry: wrong vessel size/material, crowding, batch depth mismatch.
- Substitution breakage: swaps that changed structure, emulsions, moisture, or seasoning.

---

## 2) Locked Decisions and Constraint Carry-Forward (Required)
Before proposing fixes, list and preserve thread-level constraints:
- selected option/variation,
- equipment limits,
- pan/tray count,
- ingredient-source constraints,
- format requests,
- rejected paths that must not reappear.

If a proposed fix conflicts with a locked decision, either:
- provide a compliant alternative, or
- call out the conflict and ask for explicit permission to break the lock.

---

## 3) Quick Triage (Big Levers First)

### 3a) No-Ask Checks
- Geometry: vessel size vs batch depth.
- Heat path: preheat, browning feasibility, rack/burner placement.
- Moisture path: covered/uncovered plan and reduction capacity.
- Salinity concentration risk: high-sodium ingredients plus reduction.
- Sequence integrity: emulsion order, acid/dairy timing, rests.
- Crowding risk: surface area vs portion count.

### 3b) Minimal Follow-Ups (if needed)
- What pan size/material was used?
- What heat/oven setting was actually used?
- Rough layer depth?
- Covered or uncovered, and when?
- Any substitutions?
- Did it sizzle on contact (yes/no)?

Keep questions kitchen-level and practical.

---

## 4) Root-Cause Hypotheses (Required)
State at least one falsifiable hypothesis:
- Hypothesis A: [one-sentence cause] - confidence: high|med|low
- Hypothesis B (optional): [one-sentence cause] - confidence: high|med|low

Rules:
- Each hypothesis must imply a cue/test that could disprove it.
- Every proposed change must map to Hypothesis A or B.
- Remove changes that do not map.

---

## 5) Research and Corroboration (Use meal_sources.md)
Revision-specific emphasis:
- Build queries around dish + failure symptom.
- Prefer sources that explicitly discuss mistakes, troubleshooting, ratio disputes, pan geometry, and sensory cues.
- Prefer sources whose equipment/geometry resembles the user setup.
- If sources disagree, choose the fix that is both failure-specific and physics-consistent (evaporation, browning, emulsion stability, heat transfer).

---

## 6) Equipment-Fit and Geometry Pass (Required)
Use `equipment.md` before finalizing the update.

Required checks:
- The revised vessel and tool list is compatible with on-hand inventory.
- Substitutions follow hierarchy: on-hand preferred -> common household substitute -> purchase recommendation only when justified.
- Batch depth and crowding limits are explicit.
- Covered/uncovered and reduction strategy are explicit.

If recommending a new tool, justify with one of:
- current gear cannot physically do the task,
- repeated quality failures are likely with current gear,
- high ROI for frequent use,
- requested result is meaningfully easier/safer/more repeatable with the tool.

---

## 7) Fix Design Rules
- Keep fixes minimal but decisive.
- Prefer ratio bands and sensory cues over brittle single numbers.
- Include at least one preventive guardrail for each high-confidence failure mode.
- Preserve user intent and flavor direction while repairing reliability.

---

## Emission Policy

**Internal-only sections (compute but do NOT emit):**
- §0 through §7 (intake, failure classification, locked decisions, triage, hypotheses, research, equipment analysis, fix design)

**Emitted output (in this order):**
- A) Diagnosis Summary
- B) What Changes and Why
- C) Updated Recipe (full drop-in in `recipe_template.md` format)
- D) Optional Validation Plan (include only if useful)

---

## 8) Required Output Shape

### A) Diagnosis Summary
- Failure class(es)
- Hypothesis A/B with confidence
- Evidence summary from corroboration

### B) What Changes and Why
- Change list (old -> new)
- Why each change maps to a hypothesis
- Any locked-decision conflict and resolution

### C) Updated Recipe
Emit a full drop-in replacement recipe in `recipe_template.md` format.

Required in Updated Recipe:
- inventory-aware equipment list,
- explicit geometry limits,
- explicit covered/uncovered and reduction plan,
- Gather & Stage standalone section (before numbered instructions),
- troubleshooting entries for the observed failure mode.

### D) Optional Validation Plan
If useful, include one short next-cook validation checklist (2 to 5 bullets).

---

## 9) Safety and Correctness
Run final safety/correctness checks per `meal_sources.md` and keep corrections concise.
