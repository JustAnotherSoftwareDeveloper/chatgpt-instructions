# 20260311_audit.md
# Audit Workflow

**Single responsibility:** audit workflow, severity model, issue reporting format, and corrected re-emit behavior for all healthy recipe artifacts (options lists, full recipes, and revised recipes).

**Boundary:** this file does not restate sourcing rules (`meal_sources.md`), equipment inventory (`equipment.md`), health constraints (`healthy_excludes.md`), or template formats (`healthy_options.md`, `healthy_template.md`, `revisions.md`). It references those files by name and applies them as pass-specific criteria. Do not duplicate their rules here.

---

## 1) Triggers and Output Modes

### Trigger phrases
See `healthy_instructions.md` §3 routing section for the canonical trigger phrase list. All routing for the audit deliverable is governed there.

### Artifact-type detection (required first step)
Before running any pass, identify what is being audited:
- **Options artifact**: submission conforms to `healthy_options.md` shortlist structure.
- **Recipe artifact**: submission conforms to `healthy_template.md` structure.
- **Revisions artifact**: submission contains a diagnosis + updated recipe per `revisions.md`.
- **Unknown / mixed**: treat as recipe artifact by default; state the assumption in the output.

### Output modes
Choose based on explicit user request:
- **Issue list only**: output all issues in severity order; do not re-emit the artifact.
- **Corrected re-emit**: apply fixes and output the full corrected artifact in canonical format.
- Default (no explicit preference stated): issue list only.

---

## 2) Pre-Audit Intake

Before running any pass, recover the thread constraint set from conversation history:
- Selected option or variation (if locked)
- Equipment limits and pan/tray count
- Health constraint overrides stated by the user (overrides to `healthy_excludes.md` defaults)
- Ingredient-source constraints (brands, origins, exclusions including hard avoids from `healthy_excludes.md`)
- Format requests (ordering, naming, length, special sections)
- Rejected paths that must not reappear (techniques, ingredients, formats)
- Any explicit user overrides or exceptions to defaults

Record which constraints are recoverable. Flag any that are ambiguous. These drive Pass 2.

---

## 3) Required Audit Passes

Run all passes in order. Do not skip a pass. Record "no issues found" only after completing the checks.

---

### Pass 1 — Template Compliance

Verify the artifact satisfies all required structural rules for its type.

**Options artifact** — check against `healthy_options.md`:
- Required inputs section is present and all fields are filled (Title & Goal, Context & Constraints including Serves, Time, Equipment on hand, Allergies/avoidances, etc.).
- Shortlist contains 5 to 8 entries; Runner-Ups contains 5 to 10.
- Each shortlist entry conforms to the per-option template in `healthy_options.md`:
  - Level-4 header with option name, tags (3–5), format, active time estimate, and effort level.
  - **Description** line addresses all 4 required sub-points: what the dish is, what it eats like, what makes it distinct from the other shortlisted options, and one familiar comparison when the dish may be unfamiliar.
  - **Flavor profile** line is present with richness, acidity, heat, notes, and texture fields.
  - **Make-ahead** and **Hold/Reheat** lines are present.
  - **Watch** line is derived from Research outputs (a specific failure mode or guardrail); not generic filler.
  - **Why it fits** line references at least one health constraint or user constraint (from constraint extraction) and equipment-fit.
  - **Source** field is present per option.
- Pick First / If You Want section is present.
- Internal-only workflow sections (Constraint extraction, Research execution, Research outputs) are **not** visible in the final output unless the user explicitly requested them.
- Sources section is present only if external browsing was performed; absent (not placeholder) if no browsing occurred.

**Recipe artifact** — check against `healthy_template.md`:
- Required sections present and in canonical order: Title & Overview, Tags, Yield & Timing, Grocery List, Equipment & Tools, Ingredients, Allergy & Dietary Notes, Quick Overview, Gather & Stage, Instructions, Common Issues, Make-Ahead Notes, Reheat Plan, Troubleshooting, (Variations if present), Nutrition Snapshot (per serving), Sources.
- Tags: 3 to 8 tags; lowercase, hyphen-separated; drawn from `tags.md` vocabulary where applicable.
- Yield & Timing: all five time fields present (Active Prep, Inactive Prep / Hands-Off, Cook, Total, Make-ahead).
- Grocery List: every ingredient appears exactly once under a correct category; no category present but empty.
- Equipment & Tools: uses `equipment.md` §1 item names; lists critical tools first; pan-color and glass-vs-metal calibration notes present when relevant.
- **Gather & Stage** section is present as a standalone section immediately before the numbered instructions, with a Checkpoint bullet; numbered instruction steps begin at 1; minimum 4 numbered steps total; every heat step includes heat level or oven temp + time range + sensory cue; minimum 2 branch sub-bullets in *If X → do Y → cue it's fixed* form across the recipe; Taste-adjust loop present in the final step.
- **Reheat Plan** section is present (first-class section, not merged into Make-Ahead Notes); includes best method, texture reset cue, and at least one reheat failure branch.
- **Nutrition Snapshot (per serving)** section is present and uses the table format from `healthy_template.md`; Nutrition Label Core and Vitamins and Minerals tables (Fat-Soluble Vitamins, Water-Soluble Vitamins, Minerals) are all present; all core label rows including fat sub-type rows and fiber sub-type rows, and all vitamin/mineral rows are present (NA is acceptable; rows must not be omitted); Source basis column is populated per row or per tightly grouped row set; Nutrition Provenance subsection is present; no invented numbers; no stale two-calculator requirement; no workflow-level hard stop; NA is used only for amounts unresolvable after source-tier escalation; -- is used for %DV when not displayed; calculator output does not outrank a cleaner ingredient-level source stack; branded-food handling follows Tier 2 (manufacturer) -> Tier 3 (USDA Branded) -> Tier 6 (calculator) fallback order; within a single branded ingredient, field-level fallback is permitted (Tier 2 for declared fields, lower tier for omitted fields) and must be recorded in Source basis; Added sugars follows the Role A/B/C/D derivation rules in `nutrition_calculation_method.md` step B — value is not inferred from Total sugars for Role D or ambiguous ingredients; follows `nutrition_calculation_method.md`.
- **Diet toggles** in Allergy & Dietary Notes section present when relevant.
- Troubleshooting: 2 to 4 entries; arrow format (Symptom → Likely cause → Primary fix → Recovery cue).
- Variations: 2 to 4 entries, each 1 to 2 sentences; no sub-bullets.

**Revisions artifact** — check against `revisions.md`:
- Failure classification stated (§1; 1 to 3 failure classes from the taxonomy).
- Locked decisions and health constraint carry-forward listed before proposed changes (§2).
- Root-cause hypotheses present with confidence levels (§3; minimum Hypothesis A; each implies a falsifiable test).
- Every proposed change maps explicitly to Hypothesis A or B; unmapped changes are flagged.
- Diagnosis Summary + What Changes and Why sections are both present (§8A and §8B).
- Updated Recipe is a full drop-in in `healthy_template.md` format and contains: inventory-aware equipment list, explicit geometry limits, explicit covered/uncovered and reduction plan, Gather & Stage section, Reheat Plan, Nutrition Snapshot, and troubleshooting entries for the observed failure mode.

---

### Pass 2 — Carry-Forward

Verify all locked thread constraints recovered in §2 are preserved in the artifact.

For each constraint, check:
- **Selected option/variation**: the artifact is consistent with the chosen option; variations the user rejected do not reappear as core methods.
- **Equipment limits and pan/tray count**: no item in Equipment & Tools exceeds on-hand inventory per `equipment.md` §1 without a §3-compliant substitution documented inline.
- **Health constraint defaults (`healthy_excludes.md`)**: hard avoids (tilapia, catfish, chocolate) do not appear anywhere in the artifact, including Variations; poultry is not used as the main course protein unless the user explicitly requested it; health orientation defaults are honored unless the user stated an override.
- **User-stated health overrides**: any constraint the user explicitly relaxed is applied and the relaxation is traceable.
- **Ingredient-source constraints**: user-specified brands, origins, or exclusions are honored; no silent substitution.
- **Format requests**: section ordering, naming conventions, and output length match user-stated preferences.
- **Rejected paths**: techniques, ingredients, or formats the user explicitly rejected do not reappear anywhere in the artifact, including Variations.

Any silent deviation from a locked constraint is at minimum a Major issue.

---

### Pass 3 — Source Quality

Verify the sources section against `meal_sources.md`.

Checks:
- Mode-specific source-family minimum is met: options mode = 5–8 families; recipe mode = 5–7; revisions mode = 5–7.
- Required source-type mix is present: 2+ Tier 1 individual creators (distinct people/handles), 1+ long-form blog/personal site, 1+ video/social source, 1+ discussion/feedback-loop source (forum thread or substantial comment section with troubleshooting).
- Regional Anchor source is present when the dish has clear regional or cultural provenance.
- Strict dedup rules followed: cross-posts, same creator across platforms, same domain/author, same publication network, or template-shared content each count as one family — not multiple.
- No invented citations or non-verifiable URLs.
- All in-text footnote markers [n] resolve to a numbered Sources section entry; no orphaned markers.
- Baseline recipe sites are marked [secondary]; none is used as the sole basis for a dish's flavor profile or cultural framing.
- If browsing was not available: sources section is absent (options artifact) or citations/URLs are properly omitted (recipe/revisions); no fabricated sources appear.
- Nutrition tool citations appear in Sources (marked `type: tool`) only when the tool materially contributed to the displayed Nutrition Snapshot; omission is correct when ingredient-level sources covered all fields without calculator assistance.

Flag any invented or unverifiable citation as Critical.

---

### Pass 4 — Equipment Fit and Geometry

Verify all equipment decisions against `equipment.md`.

Checks:
- Every tool listed in Equipment & Tools exists in `equipment.md` §1 inventory, or has a §3-compliant substitution documented inline.
- Substitution hierarchy followed: on-hand preferred → common household substitute → purchase recommendation only when justified by §4 criteria (cannot physically perform task, repeated quality failures likely, high ROI for frequent use, or result is meaningfully easier/safer/more repeatable).
- Pan-color and material calibration rules applied (§Baking Vessels): dark metal in place of light → reduce oven temp ~25°F or check doneness 5 min early; glass in place of metal → expect slower edge browning, longer heat retention, may need 5–10 extra minutes.
- Batch depth and crowding limits are explicit when the method creates crowding risk (surface area vs. portion count).
- Covered/uncovered and reduction plan are explicit when the method requires evaporation or moisture management.
- Vessel capacity is consistent with stated yield: Instant Pot 6 QT max fill line; stand mixer bowl ~5 QT; bread maker 2 lb loaf max.
- Any tool with status `avoid-unless-necessary` or `retired` in `equipment.md` §1 has an explicit justification for its inclusion.
- Ceramic nonstick items are not specified for high-heat searing or broiling steps (hard constraint per `equipment.md`).

---

### Pass 5 — Timing Plausibility

Verify all stated times are internally consistent and physically plausible.

Checks:
- Active Prep + Inactive / Hands-Off + Cook ≈ Total (within ±10 minutes; flag discrepancies larger than this).
- Time ranges in each instructional step are plausible for the stated method, heat level, vessel size, and portion count.
- Parallel tasks flagged in instructions (While X cooks, do Y) are achievable within the stated Active Prep time.
- Sensory cues align with the stated time range: a "2 to 3 minute" step must not claim a cue that typically requires 8 to 10 minutes.
- Make-ahead hold times: refrigerator holds are within commonly accepted safe storage windows for the product type; freeze durations are plausible for the product type.
- Reheat Plan times: temperatures and time ranges are consistent with the method stated and the portion quantity described.
- Rest times for proteins and baked goods are present where they materially affect the final texture or carryover cooking.

---

### Pass 6 — Internal Contradiction

Check the artifact for intra-document conflicts.

Checks:
- **Ingredient list vs. Instructions**: every ingredient used in the instructions appears in the Ingredients list; every item in the Ingredients list is used somewhere in the instructions.
- **Ingredients vs. Grocery List**: every ingredient appears exactly once in the Grocery List under a plausible category; no duplicates; no missing items; no item in Grocery List that is absent from Ingredients.
- **Temperature and heat references**: oven temp stated in Equipment & Tools or Yield & Timing matches oven temp in instructions; no two steps specify conflicting temps for the same phase.
- **Yield vs. vessel capacity**: stated yield is achievable in the listed vessel without exceeding known crowd or fill limits.
- **Troubleshooting vs. Instructions**: troubleshooting entries do not contradict the method they supplement.
- **Allergy & Dietary Notes**: "Contains" list is consistent with the actual Ingredients list; no undisclosed allergen present in ingredients but absent from the Contains field.
- **Diet toggles vs. Ingredients**: if diet toggles in Allergy & Dietary Notes describe a swap, that swap must be coherent with the base recipe's ingredient list.
- **Common Issues vs. Troubleshooting**: the two sections do not flatly contradict each other on the same symptom.
- **Variations**: no variation silently contradicts a locked thread constraint or a core method the user selected; no variation introduces a hard-avoid ingredient from `healthy_excludes.md`.
- **Reheat Plan vs. Make-Ahead Notes**: the two sections do not contradict each other on storage windows, reheat temperatures, or method.

---

### Pass 7 — User-Request and Health-Constraint Compliance

Verify explicit user requests are satisfied, rejected paths are absent, and health defaults are honored.

Checks:
- Every direct user request in the current thread is reflected in the artifact, or its absence is acknowledged with a reason.
- No excluded ingredient, technique, equipment item, or flavor direction reappears anywhere, including Variations.
- Health constraint defaults from `healthy_excludes.md` are honored: hard avoids absent, sodium-aware choices present (top sodium drivers identified or sodium levers included), fat management approach consistent with healthy_excludes.md §4d, make-ahead path present (required default), batch size consistent with defaults (10 portions unless user states otherwise).
- If the user stated health overrides: those overrides are applied and the deviation is acknowledged.
- If the user requested deep research, the sources section reflects the mode-appropriate source-family minimum; a shallow evidence base is a Major issue.
- Make-ahead preference is reflected in Make-Ahead Notes; a mismatch between the stated preference and the section's content is at least a Minor issue.
- Nutrition Snapshot is present in recipe artifacts; uses the table format from `healthy_template.md`; NA is used only for amounts that could not be resolved after source-tier escalation (not omitted or approximated without attribution); -- is used for %DV when not displayed; nutrition data provenance is internally consistent with the displayed rows.

---

## 4) Severity Model

| Severity     | Definition                                                                                                                                                                                            |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Critical** | Likely causes a cook failure, creates a safety risk, violates a hard health constraint (hard avoids, food safety), or directly violates an explicit user constraint. Fix is mandatory before re-emit. |
| **Major**    | High risk of reliability failure, strong inconsistency, silent health-constraint violation, or silent user-constraint violation. Fix is strongly recommended.                                         |
| **Minor**    | Clarity gap, suboptimal phrasing, or low-failure-risk inconsistency. Fix improves output quality but does not block cooking.                                                                          |

A single root cause may produce multiple visible symptoms. Group related symptoms under one issue ID when they share a single fix.

---

## 5) Issue Format

For each issue, record:

```
ISSUE-[N]
Severity:       [Critical | Major | Minor]
Pass:           [Pass 1 – 7 and label, e.g., "Pass 4 — Equipment Fit"]
Location:       [Section > subsection or step; e.g., "Instructions > Step 2 > time range"]
Problem:        [1–2 sentences: what is wrong; what was found vs. what was expected.]
Why it matters: [1 sentence: the likely consequence if unfixed.]
Required fix:   [Specific and actionable; reference the authority file section when the fix rule lives there.]
```

Do not use vague language ("unclear", "could be improved"). Name the specific value, field, or rule that is violated.

---

## 6) Corrected Re-Emit Rules

When the user requests a corrected re-emit:

1. Apply all Critical fixes without exception.
2. Apply all Major fixes without exception.
3. Apply Minor fixes only when they do not reduce clarity, change the dish's method intent, or conflict with a locked constraint.
4. Re-emit the full artifact in canonical format per its target template (`healthy_options.md`, `healthy_template.md`, or `revisions.md`).
5. Do not include audit chain-of-thought, the issue list, pre-audit intake notes, or any internal-only workflow sections in the re-emitted artifact.
6. After the re-emitted artifact, append exactly one summary line: `[N Critical, N Major, N Minor fixes applied; N Minor issues noted but not applied.]`

---

## 7) Audit Completion Checklist

Before finalizing audit output:
- [ ] Artifact type identified and stated.
- [ ] Thread constraints and health constraint defaults recovered (§2 Pre-Audit Intake).
- [ ] All 7 passes completed; none skipped.
- [ ] Each issue has: ID, severity, pass label, location, problem, why-it-matters, required fix.
- [ ] Issues ordered: Critical first, Major second, Minor last.
- [ ] If re-emit requested: corrected artifact is full, in canonical format, and contains no audit artifacts.
- [ ] Fix summary line appended after re-emit.

---

**Boundary reminder:** sourcing rules live in `meal_sources.md`; equipment inventory and fit rules live in `equipment.md`; health constraint defaults live in `healthy_excludes.md`; template structure requirements live in `healthy_options.md`, `healthy_template.md`, and `revisions.md`. This file applies those rules as audit criteria — it does not restate them.
