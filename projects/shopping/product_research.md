# product_research.md
# Product Research Workflow (top-level)

## 0) Purpose and when to invoke

### Purpose
Produce an evidence-backed assessment of one or more products (often a shortlist + recommendation), with:
- claim discipline (spec vs performance vs reliability vs subjective)
- explicit confidence tied to evidence quality and coverage
- correct routing for reviews and seller/listing sources

### Invoke this workflow when the user asks for
- "best option," "what should I buy," "compare these," "is X worth it," or any non-trivial purchase research
- or when invoked as a sub-workflow by `pricing_tiers.md` for finalist evaluation

---

## 1) Dependencies and ownership boundaries

### This workflow USES
- `product_types.md`
  - classify product class/type and apply risk posture/patterns
- `research_sources.md`
  - source admissibility + weighting, mode defaults (A/B/C), minimum source requirements, and conflict resolution
- `product_research_template.md`
  - required structured output for Mode A (and typically Mode B)

### Routing notes (do not duplicate rules)
- Review interpretation: route to `reviews.md` via `research_sources.md`.
- Listing/store pages (pricing/availability sources): route to `seller_instructions.md` via `research_sources.md`.

### This workflow DOES NOT OWN
- review-reading mechanics (`reviews.md`)
- seller/channel policy and tie-break logic (`seller_instructions.md`)
- source admissibility rules and minimums (`research_sources.md`)
- tiering logic (`pricing_tiers.md`)
- output formatting beyond populating `product_research_template.md`

---

## 2) Default mode and output contract

### Default mode
- Default research mode: `research_sources.md` Mode A unless the user explicitly signals otherwise.

### Mode linkage (important)
- If using Mode C due to sparse coverage, it must follow `research_sources.md` Mode C rules (with coverage limitations).

### Output contract
- Mode A (default): populate `product_research_template.md` (structured, complete).
- Mode B (quick validation): may use the template with reduced sections and explicit limitations, or free-form if the question is extremely narrow; must preserve claim discipline and routing.
- Mode C (sparse coverage): output may be free-form, but must:
  - state coverage limitations
  - cite admissible evidence sources
  - avoid overstated conclusions

---

## 3) Inputs and assumptions

### Inputs (from user; infer only if absent)
- Product target: category vs specific model(s).
- Hard constraints: compatibility, size, platform, ecosystem, must-have features.
- Budget: ceiling/target/range (optional).
- Purchase intent scope: "where to buy / current price" vs product suitability only.
- Preferences: brand constraints, performance vs reliability priority, aesthetics, noise/comfort, etc.

### Defaults
- Region/currency/condition defaults: USA/USD/new unless specified.
- If pricing is in scope: show comparable totals (tax-excluded) unless requested otherwise.

---

## 4) Step 1 - Route and classify (product_types.md)

1. Match product class/type using keywords first, then intent cues to refine.
2. Extract risk posture/patterns (examples):
   - firmware volatility
   - safety-critical
   - fitment-dependent
   - counterfeit-prone channel risk
   - high unit variance
3. Apply risk posture to planning:
   - if firmware volatility is high, prioritize recency/versioned sources per `research_sources.md`
   - if fitment-dependent, prioritize primary fitment specs and corroborated owner reports
   - if safety-critical, prioritize standards/regulatory and primary evidence

(Internal only: do not output classification/risk extraction unless the user asks.)

---

## 5) Step 2 - Scope switches (mode + pricing scope + comparable policy)

### 5.1 Select Mode A/B/C
- Default Mode A.
- Mode B when the user asks a narrow question about a known product or a small fixed comparison list.
- Mode C only when credible sources are genuinely limited; must include coverage limitations.

### 5.2 Pricing/availability scope switch (hard rule)
Pricing/availability is in scope if any of the following are true:
- invoked by `pricing_tiers.md`
- user asks "where to buy," "best price," "in stock," shipping/returns, or similar
- user gives a budget ceiling/target/range and expects purchasable options

Otherwise:
- pricing is out of scope unless the user asks for it
- you may provide a typical price band only if supported cleanly without seller deep-dives

### 5.3 Comparable introduction rules (hard rule)
- If the user provides a comparison list (X vs Y or a set of products): do not add candidates unless the user asks.
- If the user asks "is X worth it?" or "should I buy X?":
  - default: evaluate X directly
  - optionally add up to 2 comparables only if they materially clarify the decision
  - label them explicitly as "comparables," not forced replacements, unless evidence strongly supports recommending them instead
- If the user asks for "best in category": build a candidate pool and shortlist.

---

## 6) Step 3 - Discovery scan (discovery-only sources allowed; internal)

### Objective
- enumerate plausible candidates (if category-based)
- identify obvious disqualifiers
- map rough segmentation and price/feature clusters (only if needed for shortlisting)

### Discovery-only sources policy
Discovery-only sources:
- are allowed for candidate enumeration and rough clustering
- do not count toward evidence minimums
- must not support performance/reliability/safety conclusions
- should be omitted from the final evidence list
  - if included for transparency, list in a separate "Discovery-only (not evidence)" section

---

## 7) Step 4 - Deterministic narrowing (pool -> finalists)

### Purpose
Prevent runaway evaluation work.

### Process
Start set:
- If user provided products: start with that set (plus optional comparables per Section 5.3).
- If category-based: start with the discovery pool.

Apply hard gates (in order):
1. Must-have constraints (platform, compatibility, size, non-negotiables)
2. Variant lock gate (Section 8)
3. Obvious risk posture exclusions (from `product_types.md` patterns)
4. Rough tier/segment fit (only if user provided a budget or the category needs segmentation)

Finalists target:
- Prefer 3-6 finalists total for broad category research.
- For narrow comparisons, finalists may equal the user-provided list size.

If fewer finalists remain:
- proceed, but include a note if this is due to constraints or sparse market coverage

---

## 8) Step 5 - Variant lock (SKU/variant normalization; early hard gate)

Before deep evidence gathering:
- identify and lock the exact model/variant/SKU naming used in sources
- ensure sources reference the same variant (capacity, generation, region, revision)

If variant cannot be confidently locked:
- constrain claims to what is variant-invariant
- explicitly label uncertainty
- avoid performance/compatibility assertions tied to unknown variants

---

## 9) Step 6 - Define evaluation criteria and claim map

Driven by class/type patterns in `product_types.md`.

Define criteria buckets:
- Objective specs/compatibility (hard gates)
- Performance (measured claims when relevant)
- Reliability/durability (real-world signals)
- Safety/compliance (when applicable)
- UX/software/firmware behavior (when applicable)
- Total cost factors (consumables, subscriptions, accessories, warranty)

For each bucket:
- define "acceptable" thresholds where possible
- define required evidence types per `research_sources.md` claim-type minimums

---

## 10) Step 7 - Evidence plan and collection (research_sources.md)

- Apply `research_sources.md` mode defaults and minimums (Mode A by default).
- Explicitly separate:
  - admissible evidence sources (included/excluded and weighted)
  - discovery-only sources (non-evidence)
- Spec conflicts resolve via primary/standards first; retailer specs are secondary.
  - Fallback rule: if primary/standards are not available for a disputed spec, require at least two independent non-retailer sources and label the spec as "uncertain" if they do not agree.

---

## 11) Step 8 - Per-finalist evidence gathering and normalization

For each finalist:
- collect and normalize:
  - specs and compatibility (primary first)
  - performance evidence (methodology-aware)
  - reliability signals (breadth, timeframe, failure modes)
  - firmware/software notes (versioning/recency-sensitive)
  - warranty/support posture (channel-dependent when listings are used)
- apply:
  - `reviews.md` for interpreting reviews/manipulation signals
  - `research_sources.md` for weighting and conflict resolution
- maintain claim-to-evidence mapping:
  - key claim -> supporting sources (entities) -> confidence

---

## 12) Step 9 - Pricing/availability and channel validation (conditional; via routing)

If pricing is in scope (Section 5.2):
- gather pricing/availability from admissible sources under `research_sources.md`
- compute comparable totals consistently (tax-excluded)
- ensure listing/store pages route to `seller_instructions.md` for legitimacy and red-flag gating

If pricing is out of scope:
- do not force seller work
- optionally provide a "typical price band" only when supported cleanly

---

## 13) Step 10 - Synthesis, ranking, and recommendation

- compare finalists using:
  - hard gates first (objective specs/compatibility)
  - then evidence-backed differentiators (reliability/performance/UX)
- resolve conflicts explicitly (revision drift, methodology, sample bias, incentives)
- produce:
  - recommended pick(s) and who they are best for
  - runner-up(s) and their tradeoffs
  - explicit "why not" for excluded finalists

### Confidence scale (use consistently)
- High: strong triangulation across high-quality sources + low coverage gaps
- Medium: adequate triangulation with some gaps or mixed signals
- Low: sparse/low-quality evidence, high uncertainty, or strong version sensitivity

---

## 14) Step 11 - Output assembly

- Mode A (default): populate `product_research_template.md`.
- Mode B: reduced scope output:
  - answer the narrow question first
  - include only relevant sections
  - explicitly list limitations and what was not checked
- Mode C: free-form output allowed, but must:
  - state what was verified vs uncertain
  - include coverage limitations
  - cite admissible evidence sources
  - separate admissible evidence sources from any discovery-only links (if discovery-only links are included)
  - avoid overstated conclusions

---

## 15) Quality gates (pre-output)

- Evidence compliance:
  - `research_sources.md` minimums met for Mode A, or explicit downgrade + coverage limitations.
- Claim discipline:
  - no performance/reliability claims without appropriate evidence types.
- Variant correctness:
  - variant lock completed or uncertainty explicitly bounded.
- Routing correctness:
  - review interpretation via `reviews.md`; seller legitimacy via `seller_instructions.md` when listings are used.
- Clarity:
  - recommendation explicit, tradeoffs clear, confidence stated.

---

## 16) Optional knobs and overrides

- Retailer constraints (allowed; still apply routing/seller risk logic).
  - Retailer constraints do not change admissibility/weighting rules or minimum evidence requirements in `research_sources.md`.
- Used/refurbished (adjust risk and warranty/returns assumptions explicitly)
- Fastest shipping (treat ETA as a constraint when pricing in scope)
- "Only one answer" preference (still provide brief rationale + nearest alternative)
