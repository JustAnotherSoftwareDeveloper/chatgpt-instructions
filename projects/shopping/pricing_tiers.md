# pricing_tiers.md
# Pricing Tiers Workflow (top-level)

## 0) Purpose and when to invoke

### Purpose
Generate a tiered shortlist (3–5 tiers by default) for a product category or request, with:
- evidence-backed picks
- price-realistic placement by tier
- consistent pricing presentation using **comparable totals** (tax-excluded) unless the user requests otherwise

### Invoke this workflow when the user asks for
- price tiers / “good-better-best”
- options under a budget ceiling
- a tiered shortlist (“budget vs midrange vs premium”)
- value vs upgrade tradeoffs

### Do not invoke when
- the user only wants a quick sanity-check on a single known product:
  - use `product_research.md` in Mode B (quick validation) instead

---

## 1) Dependencies and ownership boundaries

### This workflow USES
- `product_types.md`
  - classify product class/type and pull risk posture/patterns
- `research_sources.md`
  - admissibility + weighting rules, mode defaults (Mode A default), and routing rules
  - pricing/availability sources are handled under these rules
- `product_research.md`
  - authoritative evaluation workflow for finalists (evidence gathering and justification)
- `pricing_tier_template.md`
  - required output format

### Routing notes (do not duplicate rules)
- Review interpretation: route to `reviews.md` via `research_sources.md`.
- Listing/store pages (pricing/availability sources): route to `seller_instructions.md` via `research_sources.md`.

### This workflow DOES NOT OWN
- review-reading mechanics (`reviews.md`)
- seller/channel evaluation logic (`seller_instructions.md`)
- source admissibility rules (`research_sources.md`)
- product evaluation methodology details (`product_research.md`)
- output formatting beyond populating `pricing_tier_template.md`

---

## 2) Defaults and constraints

### Tier defaults
- Default: **3–5 tiers**
- Collapse to **1–2 tiers** only if the “extreme circumstances” trigger is met (Section 6).

### Pricing defaults
- Prices shown are **comparable totals** (tax-excluded) unless the user requests tax-included totals.
- Pricing/availability is inherently in scope for pricing tiers, but pricing sources must still follow `research_sources.md` routing.

### Source list hygiene
- Final **evidence sources list** must include evidence sources only.
- Discovery-only sources must be omitted from the evidence sources list.
  - If included for transparency, they must appear in a separate “Discovery-only (not evidence)” section.

---

## 3) Step 1 — Route and classify (product_types.md)

1. Match product class/type using **keywords first**, then intent cues to refine.
2. Extract risk posture inputs used downstream (examples):
   - risk_channel
   - risk_safety
   - risk_firmware
   - risk_fitment
   - other class/type patterns as defined in `product_types.md`
3. Identify user constraints:
   - hard budget ceiling vs target vs no budget
   - must-have constraints (platform, compatibility, size, etc.)
   - time sensitivity (need now vs can wait)

(Internal only: do not output classification/risk extraction unless the user asks.)

---

## 4) Step 2 — Initialize tier geometry (draft bands + tier intent)

1. Draft tier count (3–5) and tier intents:
   - Budget (acceptable baseline, avoid junk)
   - Value (best price/performance ratio)
   - Midrange upgrade (meaningful improvements)
   - Premium (best-in-class with explicit tradeoffs)
   - Specialty (only if the category supports a legitimate niche dimension)
2. If the user provides a ceiling or target:
   - anchor a tier to that constraint
   - ensure at least one tier stays under the ceiling when feasible
3. If no budget is provided:
   - create provisional bands to be refined after the discovery scan loop

---

## 5) Step 3 — Discovery scan (discovery-only sources allowed)

### Objective
Quickly identify:
- candidate models/products
- approximate price clusters and market segmentation
- obvious disqualifiers (wrong platform, missing must-haves)

### Discovery-only source policy
Discovery-only sources:
- are allowed for candidate enumeration and rough clustering only
- do not count toward evidence minimums in `research_sources.md`
- must not be used to support performance/reliability/safety conclusions
- must not appear in the evidence sources list (Section 2)
  - if retained, list separately as “Discovery-only (not evidence)”

### Output of discovery scan (internal)
- initial candidate pool
- observed price distribution (clusters)
- early disqualifier list

---

## 6) Step 4 — Tier loop refinement (price distribution → adjust bands)

1. Adjust tier boundaries based on:
   - observed price clusters
   - meaningful feature jumps that match tier intents
2. Repeat discovery scan + refinement **once** if needed to stabilize bands.

### Extreme circumstances trigger (collapse to 1–2 tiers)
After the discovery scan + one refinement loop, if any of the following are true:
- fewer than **4 credible candidates total**, OR
- fewer than **2 meaningful price clusters**, OR
- the category does not meaningfully differentiate by price

Then:
- collapse to **1–2 tiers**
- include a Coverage limitations note in the final output

---

## 7) Step 5 — Narrow to tier finalists (pre-evaluation gate)

### Purpose
Avoid over-invoking `product_research.md` across too many candidates.

### Method
For each tier:
- narrow to a finalist set (target **2–3 candidates per tier**) using:
  - must-have constraints
  - objective specs from primary sources when easy to obtain
  - gross risk posture exclusions (as defined in `product_types.md`)
  - tier band fit based on discovery pricing

Notes:
- This step may eliminate candidates but must not produce deep performance/reliability conclusions.
- If a tier cannot sustain 2–3 finalists due to market sparsity, keep the best available finalists and document constraints.

---

## 8) Step 6 — Evaluate finalists using product_research.md (authoritative)

For each tier’s finalists:
1. Invoke `product_research.md` as the authoritative evaluation method, including:
   - admissible evidence gathering per `research_sources.md` (Mode A default unless overridden)
   - review interpretation via routing to `reviews.md`
   - pricing/availability sources via `research_sources.md` routing (listing/store pages route to `seller_instructions.md`)
2. Select tier winners based on:
   - constraints fit (hard requirements first)
   - evidence strength and claim discipline (spec vs performance vs reliability vs subjective)
   - risk posture escalations from `product_types.md`
   - tier intent and price realism

Clarification:
- Step 6 may collect pricing evidence opportunistically while evaluating candidates.
- Step 7 performs the standardized final pricing/availability normalization for output.

---

## 9) Step 7 — Pricing/availability normalization (via research_sources routing)

For each final pick:
1. Obtain current pricing/availability from admissible sources under `research_sources.md`.
2. Ensure listing/store pages are evaluated through routing to `seller_instructions.md`.
3. Present prices consistently as:
   - comparable totals (tax-excluded) unless the user requests tax-included totals
4. Include a typical street price range when feasible (based on multiple admissible pricing sources).

---

## 10) Step 8 — Cross-tier normalization and redundancy rules

### No-overlap rule (default)
- Do not repeat the same product across tiers.

### Single-overlap exception (allowed only if explicitly framed)
A product may appear in more than one tier only if:
- it is intentionally labeled as a:
  - bridge option, OR
  - sale-dependent pick, OR
  - stretch pick
AND:
- the overlap happens **only once** (a single deliberate cross-tier placement)

### Tier separation check
- If Value and Midrange picks collapse into the same price band, adjust:
  - tier bands, OR
  - picks, OR
  - both

### Exclusions
Explicitly identify categories of products excluded and why (examples):
- relabel/drop-ship patterns
- outdated generations when replacements exist
- unacceptable firmware/software track record
- weak warranty/support
- excessive channel risk

---

## 11) Step 9 — Output assembly (pricing_tier_template.md)

Populate `pricing_tier_template.md` with:
- tier intents and tier price bands
- picks per tier:
  - why pick / why skip
  - key constraints and compatibility caveats
  - pricing shown as comparable totals
  - warranty/support notes when relevant (channel-dependent, routed via seller policy)
- decision guide:
  - minimum viable specs
  - pitfalls and what to avoid
  - when it’s worth spending more
- what was excluded and why
- evidence sources list and timestamp
- optional: separate “Discovery-only (not evidence)” list (if needed for transparency)

Required pricing label:
- “Prices shown are comparable totals (tax-excluded) unless requested otherwise.”

---

## 12) Quality gates (pre-output)

Before finalizing:
- Budget compliance:
  - at least one option under any stated ceiling when feasible; otherwise state infeasibility explicitly.
- Evidence compliance:
  - `research_sources.md` minimums met (Mode A default), or an explicit Mode B/C downgrade with Coverage limitations.
- Pricing correctness:
  - comparable totals used consistently; discovery-only sources are not treated as evidence.
- Redundancy:
  - overlap only under the single-overlap rule with explicit labeling.
- Claims discipline:
  - no performance/reliability claims without properly weighted admissible evidence.
