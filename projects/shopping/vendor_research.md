# vendor_research.md
# Vendor Research Workflow (top-level — Workflow D)

## 0) Purpose and when to invoke

### Purpose
Produce an evidence-backed assessment of vendors, brands, manufacturers, retailers, shopping sites, dealer networks, or vendor ecosystems for a category or need. The goal is recommending the right vendor ecosystem or brand class, not selecting a specific product SKU.

### Invoke this workflow when the user asks for
- good brands for X
- reputable websites or stores for X
- which manufacturers to consider
- which microbrands are worth looking at
- what dealer ecosystem is best for this category
- a shortlist of vendors, retailers, or brand names rather than a shortlist of specific products

### Do not invoke when
- the user wants a specific product shortlist: use `product_research.md` (Workflow A)
- the user wants pricing tiers across products: use `pricing_tiers.md` (Workflow B)
- the user wants a quick sanity check on a single listing: use `product_research.md` (Workflow C)

---

## 1) Dependencies and ownership boundaries

### This workflow USES
- `product_types.md`
  - category/type tuning and risk posture
- `research_sources.md`
  - source admissibility, weighting, minimum variety, and entity overuse cap
- `seller_instructions.md`
  - policy clarity, legitimacy checks, return/warranty posture, and trust-tier classification when channel quality is relevant
- `vendor_research_template.md`
  - required output format
- `source_playbooks.md`
  - category-specific source discovery guidance (optional but recommended)

### This workflow DOES NOT OWN
- review interpretation rules (owned by `reviews.md` via `research_sources.md`)
- general evidence admissibility (owned by `research_sources.md`)
- seller risk tie-break policy (owned by `seller_instructions.md`)
- product-level evaluation methodology (owned by `product_research.md`)
- output formatting beyond populating `vendor_research_template.md`

---

## 2) Default mode and output contract

### Default mode
- Default research mode: `research_sources.md` Mode A unless the user explicitly signals otherwise.
- Mode C (sparse coverage) may apply when credible sources for a niche vendor ecosystem are limited; must include coverage limitations.

### Output contract
- Default: populate `vendor_research_template.md` (structured, complete).
- Mode C / sparse coverage: reduced format allowed, but must still state coverage limitations and maintain evidence vs discovery-only separation.
- Default recommendation payload:
  - 1 recommended vendor
  - 2-4 runner-ups
  - Exceptions: sparse market (fewer than 3 strong candidates), hard user constraints narrow the viable set, or user explicitly asks for only one answer.

---

## 3) Inputs and assumptions

### Inputs (from user; infer only if absent)
- Category or need: what the vendor should supply (e.g., mechanical watches, upholstered furniture, smart home hubs).
- Vendor scope: brand/manufacturer vs retailer/store vs dealer/distributor vs mixed.
- Region: default USA unless specified.
- Hard constraints: direct-only, domestic service required, brick-and-mortar preferred, avoid large marketplaces, etc.
- Budget posture: value-oriented vs enthusiast vs premium (optional; use to tune vendor segment focus).
- Aesthetic or identity preferences if mentioned.

### Defaults
- Region/currency/condition defaults: USA/USD/new unless specified.

---

## 4) Step 1 — Route and classify (product_types.md)

1. Match product class/type using keywords first, then intent cues to refine.
2. Extract risk posture inputs relevant to vendor evaluation (examples):
   - counterfeit-channel risk (is this a category where gray-market or relay brands are common?)
   - service/support criticality (does warranty or local service matter a lot?)
   - collector/enthusiast depth (is brand identity and community standing important?)
   - regional availability constraints
3. Use risk posture to tune vendor evaluation (e.g., if counterfeit risk is high, weight business legitimacy and policy clarity more heavily).

(Internal only: do not output classification unless the user asks.)

---

## 5) Step 2 — Scope switch (vendor type classification)

Classify which type of vendor research is being performed. State this classification in the output.

Types:
- **Brand/manufacturer research**: which brands or makers produce the best products in this category.
- **Retailer/store/site research**: which stores, websites, or online channels are the best places to shop for this category.
- **Dealer/distributor research**: which dealer networks, authorized distributors, or service channels are most reliable.
- **Mixed vendor ecosystem research**: a combination of the above (e.g., which brands are best AND which retailers carry them reliably).

The workflow handles any of these types or a mixed case. State which type is being evaluated so the output is unambiguous.

---

## 6) Step 3 — Discovery scan (discovery-only sources allowed; internal)

### Objective
- enumerate plausible vendors, brands, stores, or sites in the category
- identify obvious disqualifier patterns
- map rough segmentation clusters

### Discovery breadth requirements (before narrowing)
When the market supports it, the discovery pass must achieve:
- At least 8-12 plausible vendor entities identified before applying hard gates.
- At least 5 distinct vendor entities in the initial pool.
- Identification of obvious segmentation clusters, such as: value, enthusiast, premium, specialty, commodity, custom, direct-only, marketplace-heavy, niche-only, regional.
- If the market is genuinely too narrow to support that breadth, state so explicitly. Do not silently accept a thin pool.

### Discovery-only sources policy
- Discovery-only sources are allowed here for enumeration and market mapping.
- They do not count toward evidence minimums.
- They must not support vendor quality, reliability, or legitimacy conclusions.
- List separately from evidence sources in the output (Section 2 / source list hygiene rules from `research_sources.md` apply).

---

## 7) Step 4 — Deterministic narrowing (pool → finalists)

Apply hard gates in order to narrow from the discovery pool to finalists (target 4-8 finalists where the market supports it):

1. **Category relevance**: does the vendor meaningfully sell in the category, or is it peripheral?
2. **Region availability**: can the user realistically buy from or through this vendor in their region?
3. **Business legitimacy**: does the vendor have a real, discoverable business identity? (Apply `seller_instructions.md` legitimacy checks when relevant.)
4. **Lineup relevance**: does the vendor's lineup in this category match the user's need?
5. **Obvious red-flag exclusion**: relabel/relay operations, known scam patterns, poor reputation with no countervailing evidence.
6. **Policy clarity**: are return policies, warranty terms, and service paths discoverable and not obviously trapping?
7. **Practical fit**: does the vendor's posture (price, channel, region) fit the request?

If fewer finalists remain after hard gates:
- proceed with what is available
- include a note if this is due to constraints or sparse market coverage

---

## 8) Step 5 — Define evaluation criteria

Apply vendor-level criteria buckets (adjust weighting by category type and user needs):

- **Category specialization**: does the vendor specialize in this category, or is it one of hundreds they carry?
- **Lineup quality / consistency**: is the vendor's product lineup strong and consistent, or uneven?
- **Trust / legitimacy / business clarity**: is this a real, credible business with clear identity, policies, and contact paths?
- **Support / warranty / returns posture**: how well does the vendor handle post-purchase issues? (Route to `seller_instructions.md` for policy evaluation.)
- **Channel quality**: is the vendor's distribution channel appropriate, or does it involve gray-market, relay, or confusing ownership structures?
- **Enthusiast / expert reputation**: is the vendor respected by credible experts, forums, and communities in the category?
- **Design / aesthetic / collector / identity fit**: does the vendor's brand identity, aesthetic direction, or community standing match the user's preference? Treat this as a first-class dimension when the user's request makes it relevant.
- **Price posture / value posture**: does the vendor's typical price positioning match the user's budget and value expectations?
- **Availability / regional practicality**: is the vendor accessible and competitive in the user's region?

---

## 9) Step 6 — Evidence plan and collection (research_sources.md)

Apply `research_sources.md` mode defaults, minimums, and the entity overuse cap.

Vendor-specific evidence mix requirement:
- At least **1 vendor-controlled / primary source** when relevant (brand site, official documentation, published warranty terms).
- At least **1 independent specialist / expert / method-based source** when relevant (category-specialist publication, trusted reviewer with domain expertise).
- At least **2 owner/community entities from different platforms** when reputation and reliability are in scope (not both from the same forum or same retailer review section).
- Seller/channel evidence when buying guidance is relevant (apply `seller_instructions.md`).

Use `source_playbooks.md` when available to find category-appropriate sources beyond generic defaults.

Keep evidence vs discovery-only strictly separated.

---

## 10) Step 7 — Per-vendor evidence normalization

For each finalist vendor, normalize:
- What they are (brand, retailer, dealer network, etc.)
- What they sell in this category (specific lineup, segment, price tier)
- Where they are strong (category depth, reputation, support, design language)
- What kind of buyer they are best for
- Pricing posture (budget, value, enthusiast, premium, luxury)
- Support / warranty / returns / business clarity (route to `seller_instructions.md` for channel-level evaluation)
- Notable risks (limited line, bad return track record, high gray-market presence in channels, limited domestic service)
- Why a buyer might not choose this vendor (honest "why not")

---

## 11) Step 8 — Synthesis and recommendation

Compare finalists using:
- hard eligibility gates (legitimacy, availability, lineup fit) first
- then evidence-backed differentiators (reputation, support, specialist depth, identity fit)

Produce:
- 1 recommended vendor (who they are best for; why recommended)
- 2-4 runner-ups (tradeoffs; who each is best for)
- "Who each is best for" annotations
- Excluded vendor classes and why (e.g., "relabel/relay brands excluded due to unclear lineage")
- Exceptions to the 2-4 runner-up default:
  - sparse market (fewer than 3 strong candidates after hard gates)
  - hard user constraints narrow the viable set
  - user explicitly asks for only one answer

### Confidence scale (use consistently; mirrors product_research.md)
- High: strong triangulation across high-quality sources + low coverage gaps
- Medium: adequate triangulation with some gaps or mixed signals
- Low: sparse/low-quality evidence, high uncertainty, or niche market with limited independent coverage

---

## 12) Step 9 — Output assembly

- Default: populate `vendor_research_template.md`.
- Mode C / sparse coverage: reduced format allowed, but must include:
  - coverage limitations statement
  - evidence vs discovery-only separation

---

## 13) Quality gates (pre-output)

- Evidence compliance: `research_sources.md` minimums met (Mode A default), or explicit downgrade with Coverage limitations.
- Entity diversity: no overreliance on one non-primary entity per the entity overuse cap in `research_sources.md`.
- Vendor-vs-seller boundary: this output recommends vendor ecosystems / brand classes; it does not make per-listing purchase decisions (those belong to `seller_instructions.md`).
- Clear recommendation: 1 recommended vendor + tradeoffs + confidence stated.
- Discovery breadth: achieved 8-12 vendor candidates before narrowing, or stated why the market is too narrow.

---

## 14) Optional overrides

- Region limits (USA-only, domestic service required, etc.)
- Direct-only (brand-direct storefronts only)
- Avoid large marketplaces
- Brick-and-mortar preference or showroom preference
- Only online
- Only brands with domestic service centers
- "Only one answer" preference
