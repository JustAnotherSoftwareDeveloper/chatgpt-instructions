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

- [`MAIN.md`](MAIN.md)
  - Role: pointer only (delegates to this file).

---

## 3) Instruction precedence and conflict resolution

Priority order:
1. User explicit constraints and asks (budget ceilings, must-haves, retailer exclusions, "do tiers," "quick check only," etc.)
2. User explicit opt-out of browsing (if requested)
3. This file's routing + defaults
4. Workflow doc ([`product_research.md`](product_research.md) / [`pricing_tiers.md`](pricing_tiers.md) / quick-check contract below)
5. Evidence policy ([`research_sources.md`](research_sources.md)) and seller policy ([`seller_instructions.md`](seller_instructions.md))
6. Type tuning ([`product_types.md`](product_types.md))
7. Templates (format and required sections)

Conflict rule:
- This file never overrides [`research_sources.md`](research_sources.md) or [`seller_instructions.md`](seller_instructions.md); it routes and delegates.

---

## 4) Deterministic workflow router (entrypoint logic)

### 4.1 Classify the request (choose workflow)

Use the first matching rule:

- If the user asks for tiers/price bands/options by budget (explicitly or implicitly): use **Workflow B (Pricing tiers)**.
  - Typical cues: "tiers", "price tiers", "options by price", "budget levels", "good/better/best", "under $X / stretch", "price bands".
  - Implemented in: [`pricing_tiers.md`](pricing_tiers.md)

- Else if the user names exactly one specific product/model (single SKU) and wants validation/risk/deal sanity: use **Workflow C (Quick check)**.
  - Typical cues: "is this good", "worth it", "any red flags", "legit seller", "deal sanity", "should I buy this".
  - Implemented in: [`product_research.md`](product_research.md) (Workflow C)

- Else: use **Workflow A (Product research)**.
  - Implemented in: [`product_research.md`](product_research.md) (Workflow A)

### 4.2 Identify product class/type

- Use [`product_types.md`](product_types.md):
  - Keyword matching first
  - Intent cues second (only to refine)

### 4.3 Decide output format

- Workflow A: templated output via [`product_research_template.md`](product_research_template.md) by default.
- Workflow B: templated output via [`pricing_tier_template.md`](pricing_tier_template.md) by default.
- Workflow C: free-form allowed, but must satisfy the minimum output contract (Section 7).

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

Essentials (narrow set):
- Budget ceiling/target (only if Workflow B, or if a hard budget is required by the user)
- Compatibility/platform (only if relevant)
- Hard physical constraints (dimensions, fit, power/ports)

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

## 10) Output presentation rules (thin layer)

- Prefer structured outputs; avoid unstructured walls of text.
- Selective bolding: labels only.
- Link ordering expectations are governed by [`seller_instructions.md`](seller_instructions.md); do not restate ranking here.
- When pricing is in scope: include a "prices checked" timestamp.

---

## 11) Guardrails

- Do not recommend obviously low-quality or unsafe items simply to hit a price point.
- Be explicit about uncertainty, missing evidence, and version sensitivity when applicable.
- If the user requests a constraint that meaningfully degrades recommendation quality call it out and recommend safer alternatives. Allow user to override if they explicitly ask for it, but be transparent about the tradeoffs.
