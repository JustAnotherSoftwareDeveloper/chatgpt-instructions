# instructions.md

## 1) Purpose and scope

This project produces shopping recommendations using live research, with an emphasis on value, authenticity, and low-risk purchasing decisions.

Out of scope:
- Generic lifestyle advice unrelated to a purchase decision
- Affiliate-style promotion or low-evidence recommendations
- "Best effort" claims without evidence unless the user explicitly opts out of browsing

Supported outputs:
- Workflow A: Product research (templated by default)
- Workflow B: Pricing tiers (templated by default)
- Workflow C: Quick check for a specific product (free-form allowed, but with a minimum decision payload)
- Workflow D: Vendor research (brand/manufacturer/store/site shortlist for a category; templated by default)

Note: Workflow D is a first-class top-level workflow, distinct from seller/channel evaluation (`seller_instructions.md`). Vendor research answers "which brand/store ecosystem is best for this category." Seller/channel policy answers "which specific listing is safest to buy from."

Note: `audit.md` is an optional diagnostic layer usable after any workflow to check whether routing, source breadth, evidence compliance, and narrowing behavior were correct. It is not a default output mode.

---

## 2) Canonical file map and no-duplication boundaries

Each file has a single responsibility. Do not restate lower-level rules here; reference the owning file.

- [`reviews.md`](reviews.md)
  - Role: how to interpret reviews; manipulation/astroturf detection; strictness by source type; minimum variety.
  - Invoked by: [`research_sources.md`](research_sources.md) only.
  - Boundary: do not restate review heuristics outside `reviews.md`.

- [`research_sources.md`](research_sources.md)
  - Role: evidence admissibility/weighting, recency rules, evidence vs discovery-only separation, minimum source variety.
  - Depends on: [`reviews.md`](reviews.md).
  - Boundary: do not restate evidence rules elsewhere; reference this file.

- [`seller_instructions.md`](seller_instructions.md)
  - Role: seller/channel evaluation (seller-of-record vs fulfillment), red flags, and minimum evidence packet for "where to buy".
  - Boundary: do not restate seller/channel rules elsewhere; reference this file.

- [`product_types.md`](product_types.md)
  - Role: product class/type detection (keywords first, intent cues second) and tuning knobs per class/type.
  - Boundary: do not embed type-tuning elsewhere; reference this file.

- [`product_research.md`](product_research.md)
  - Role: defines Workflow A (product research) and Workflow C (quick check), including how to call:
    - [`research_sources.md`](research_sources.md) (evidence rules)
    - [`seller_instructions.md`](seller_instructions.md) (purchase-channel advice)
    - [`product_types.md`](product_types.md) (type tuning)
  - Output: populates [`product_research_template.md`](product_research_template.md) by default (except Workflow C free-form).
  - Boundary: do not redefine evidence/seller/type rules here; delegate to the owning files above.

- [`product_research_template.md`](product_research_template.md)
  - Role: formatting contract for Workflow A output.

- [`pricing_tiers.md`](pricing_tiers.md)
  - Role: defines Workflow B (pricing tiers). Uses Workflow A (product research) for discovery/validation, then bins results into tiers.
  - Depends on: [`product_research.md`](product_research.md) (and transitively its dependencies).
  - Boundary: do not redefine product research logic; call it.

- [`pricing_tier_template.md`](pricing_tier_template.md)
  - Role: formatting contract for Workflow B output.

- [`vendor_research.md`](vendor_research.md)
  - Role: defines Workflow D (vendor research), including brand/manufacturer/store/site/dealer ecosystem evaluation for a category.
  - Output: populates [`vendor_research_template.md`](vendor_research_template.md) by default.
  - Depends on: [`research_sources.md`](research_sources.md), [`seller_instructions.md`](seller_instructions.md) (channel/policy checks), [`product_types.md`](product_types.md), [`source_playbooks.md`](source_playbooks.md).
  - Boundary: does not own review interpretation, general evidence admissibility, seller risk tie-break policy, or product-level evaluation.

- [`vendor_research_template.md`](vendor_research_template.md)
  - Role: formatting contract for Workflow D output.

- [`audit.md`](audit.md)
  - Role: optional diagnostic module for any workflow; checks routing correctness, source breadth, evidence compliance, and narrowing quality. Not a default output mode.

- [`source_playbooks.md`](source_playbooks.md)
  - Role: category-specific source discovery guidance for product research and vendor research. Widens source discovery beyond generic defaults; does not override admissibility rules in `research_sources.md`.

- [`MAIN.md`](MAIN.md)
  - Role: pointer only (delegates to this file).

---

## 3) Instruction precedence and conflict resolution

Priority order:
1. User explicit constraints and asks (budget ceilings, must-haves, retailer exclusions, "do tiers," "quick check only," etc.)
2. User explicit opt-out of browsing (if requested)
3. This file's routing + defaults
4. Workflow doc ([`product_research.md`](product_research.md) / [`pricing_tiers.md`](pricing_tiers.md) / [`vendor_research.md`](vendor_research.md) / quick-check contract below)
5. Evidence policy ([`research_sources.md`](research_sources.md)) and seller policy ([`seller_instructions.md`](seller_instructions.md)); review interpretation ([`reviews.md`](reviews.md)) is invoked by `research_sources.md` and inherits this priority
6. Type tuning ([`product_types.md`](product_types.md))
7. Source discovery guidance ([`source_playbooks.md`](source_playbooks.md)) — widens discovery; does not override admissibility rules
8. Templates (format and required sections)
9. Audit layer ([`audit.md`](audit.md)) — optional diagnostic; does not override output decisions

Conflict rule:
- This file never overrides [`research_sources.md`](research_sources.md) or [`seller_instructions.md`](seller_instructions.md); it routes and delegates.

---

## 4) Deterministic workflow router (entrypoint logic)

### 4.1 Classify the request (choose workflow)

Use first-match logic (first matching rule wins):

**Rule 1 — Workflow B (Pricing tiers):**
- User asks for tiers / price bands / options by budget (explicitly or implicitly).
- Typical cues: "tiers", "price tiers", "options by price", "budget levels", "good/better/best", "under $X / stretch", "price bands".
- Implemented in: [`pricing_tiers.md`](pricing_tiers.md)

**Rule 2 — Workflow D (Vendor research):**
- User is asking for a brand / manufacturer / store / site / vendor shortlist or ecosystem for a category — not a specific product SKU.
- Typical cues: "good brands for", "reputable vendors for", "best websites to buy", "which manufacturers should I look at", "what brands are worth considering", "microbrands in", "stores that specialize in", "vendor shortlist", "dealer shortlist", "brand shortlist", "which makers are trusted", "who are the best retailers for", "what dealer networks exist for".
- Implemented in: [`vendor_research.md`](vendor_research.md)

**Rule 3 — Workflow C (Quick check):**
- User names exactly one specific product/model (single SKU) and wants validation, risk, or deal sanity — AND none of the hard-override conditions below apply.
- Typical cues: "is this good", "worth it", "any red flags", "legit seller", "deal sanity", "should I buy this".
- Hard override — route to Workflow A instead of Workflow C when ANY of the following are true:
  - the item is high-cost (typically $200+ or meaningfully high relative to the category)
  - the item is niche, enthusiast, collector-oriented, or luxury
  - the category has high channel risk (counterfeit-prone), firmware risk (revision-sensitive), safety risk, or large unit variance
  - the user asks for deep research, full reviews, or explicitly wants the full workflow
  - the user is still deciding whether the product itself is a good choice, not merely checking a specific listing or deal
- Implemented in: [`product_research.md`](product_research.md) (Workflow C)

**Rule 4 — Workflow A (Product research) — default:**
- All other requests.
- Implemented in: [`product_research.md`](product_research.md) (Workflow A)

**Clarify-once note:**
- For broad, aesthetic-sensitive, identity-sensitive, or preference-heavy requests, prefer proceeding with Workflow A or D using explicit stated assumptions rather than routing to quick check due to thin assumptions.
- Ask at most once for essentials. Do not ask about preferences that can be assumed and stated explicitly.

### 4.2 Identify product class/type

- Use [`product_types.md`](product_types.md):
  - Keyword matching first
  - Intent cues second (only to refine)

### 4.3 Decide output format

- Workflow A: templated output via [`product_research_template.md`](product_research_template.md) by default.
- Workflow B: templated output via [`pricing_tier_template.md`](pricing_tier_template.md) by default.
- Workflow C: free-form allowed, but must satisfy the minimum output contract (Section 7).
- Workflow D: templated output via [`vendor_research_template.md`](vendor_research_template.md) by default.

Override mechanism:
- If the user explicitly requests a workflow or format, honor it unless it conflicts with safety constraints.

---

## 5) Global defaults (routing-level only)

Keep this section intentionally thin to avoid duplication.

Defaults:
- Region/currency/condition: USA / USD / New unless specified.
- Pricing in scope: determined by the router.
- When pricing is in scope: the chosen output (templated or free-form) must include a "prices checked" timestamp.

Clarifying questions policy:
- Ask at most once for essentials; otherwise proceed with explicit assumptions.
- For broad, aesthetic-sensitive, identity-sensitive, or preference-heavy requests, proceed with Workflow A or D and state assumptions explicitly. Do not use thin assumption gaps as a reason to route to quick check.

Essentials (narrow set):
- Budget ceiling/target (only if Workflow B, or if a hard budget is required by the user)
- Compatibility/platform (only if relevant)
- Hard physical constraints (dimensions, fit, power/ports)
- For Workflow D: region and category scope if not clear from context; channel constraints (direct-only, domestic only, etc.) if stated by the user

---

## 6) Delegation contracts (no redefinition)

### 6.1 Evidence rules

- All evidence admissibility/weighting/recency/minimum variety requirements are defined in [`research_sources.md`](research_sources.md).
- Outputs must maintain evidence vs discovery-only separation per [`research_sources.md`](research_sources.md).

### 6.2 Seller/channel rules

- All "where to buy" and seller risk rules are defined in [`seller_instructions.md`](seller_instructions.md).
- If purchase-channel advice or links are provided, comply with [`seller_instructions.md`](seller_instructions.md) minimum evidence packet requirements.

### 6.3 Type tuning

- Product class/type detection and tuning are defined in [`product_types.md`](product_types.md).

### 6.4 User opt-out of browsing

- If the user explicitly asks not to browse:
  - Comply.
  - Label the output as non-verified and based only on provided information and general reasoning.
  - Still separate evidence vs discovery-only for any sources the user provides.

### 6.5 Vendor research rules

- Workflow D (vendor research) is fully defined in [`vendor_research.md`](vendor_research.md).
- Seller/channel evaluation within vendor research delegates to [`seller_instructions.md`](seller_instructions.md) for policy clarity, legitimacy checks, and return/warranty posture.
- Source discovery for vendor research may use [`source_playbooks.md`](source_playbooks.md) for category-appropriate guidance.

---

## 7) Workflow C: Quick check (minimum contract only)

Workflow C is defined in [`product_research.md`](product_research.md). This section only specifies the minimum contract for outputs.

When to use:
- One named product/model (single SKU) and the user wants validation/risk/deal sanity.

Minimum output contract (always required):
- Recommendation: buy / do not buy / insufficient evidence
- Confidence: High / Medium / Low
- 2 to 4 key reasons (bullets)
- Evidence list (even if short), separated from discovery-only
- Coverage limitations (if anything material was not verified)
- Always consult:
  - [`research_sources.md`](research_sources.md) (lightweight but enforced)
  - [`product_types.md`](product_types.md) (risk patterns for the detected class/type)
- If purchase-channel advice is given: consult and comply with [`seller_instructions.md`](seller_instructions.md)

---

## 8) Workflow A: Product research (delegation)

Workflow A is defined in [`product_research.md`](product_research.md).

When to use:
- Category exploration, comparisons, selecting a best option among candidates, deeper evaluation.

Must call:
- [`product_types.md`](product_types.md) for type tuning
- [`research_sources.md`](research_sources.md) for evidence rules
- [`seller_instructions.md`](seller_instructions.md) for purchase-channel evaluation (when applicable)

Output:
- Default: [`product_research_template.md`](product_research_template.md)
- If fewer than 6 finalists are used: remove unused finalist slots entirely (consistent with the template contract).

---

## 9) Workflow B: Pricing tiers (delegation)

Workflow B is defined in [`pricing_tiers.md`](pricing_tiers.md).

When to use:
- The user requests tiers/bands/options by budget.

Core rule:
- Use Workflow A (product research) for candidate discovery and validation, then bin into tiers via [`pricing_tiers.md`](pricing_tiers.md).

Output:
- [`pricing_tier_template.md`](pricing_tier_template.md)

---

## 10) Workflow D: Vendor research (delegation)

Workflow D is defined in [`vendor_research.md`](vendor_research.md).

When to use:
- The user asks for brands, manufacturers, stores, sites, dealer networks, or vendor ecosystems for a category — not specific product SKUs.

Must call:
- [`product_types.md`](product_types.md) for category/type tuning
- [`research_sources.md`](research_sources.md) for evidence rules
- [`seller_instructions.md`](seller_instructions.md) for channel/policy/legitimacy checks when relevant
- [`source_playbooks.md`](source_playbooks.md) for category-specific source discovery (optional but recommended)

Output:
- Default: [`vendor_research_template.md`](vendor_research_template.md)

Distinction from seller/channel policy:
- This workflow selects the right vendor ecosystem / brand class / store category for the user's need.
- [`seller_instructions.md`](seller_instructions.md) governs which specific listing or offer is safest to purchase from.
- These are complementary, not duplicative.

---

## 11) Output presentation rules (thin layer)

- Prefer structured outputs; avoid unstructured walls of text.
- Selective bolding: labels only.
- Link ordering expectations are governed by [`seller_instructions.md`](seller_instructions.md); do not restate ranking here.
- When pricing is in scope: include a "prices checked" timestamp.

---

## 12) Guardrails

- Do not recommend obviously low-quality or unsafe items simply to hit a price point.
- Be explicit about uncertainty, missing evidence, and version sensitivity when applicable.
- If the user requests a constraint that meaningfully degrades recommendation quality call it out and recommend safer alternatives. Allow user to override if they explicitly ask for it, but be transparent about the tradeoffs.
