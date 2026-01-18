# seller_instructions.md
# Seller & Purchase-Channel Evaluation (seller-only)

## 0) Scope and ownership

### Purpose
This file governs **where to buy** (seller/channel selection and purchase risk), not which product is best.

### Defaults
- Region: USA
- Currency: USD
- Condition: **New** unless the user explicitly requests refurbished/open-box/used.

### Key term: comparable total (default price basis)
For cross-seller comparison, this file uses **comparable total** by default:
- comparable total = item price + shipping + mandatory fees
- taxes are excluded unless explicitly requested (tax presentation varies across sellers)

### This file OWNS
- Comparable-total pricing method for comparison (tax-excluded by default)
- Seller-of-record vs fulfillment-party evaluation
- Trust tiering for channels/sellers
- Red-Flag Gate (scam/counterfeit/return-trap detection)
- Stock/ETA confidence checks (as purchase risk)
- Seller evidence packet requirements for downstream workflows
- Tie-break rules between offers (risk-adjusted comparable totals)

### This file DOES NOT OWN
- Review interpretation or credibility (owned by `reviews.md`)
- General source evaluation (owned by `research_sources.md`)
- Product evaluation methodology (owned by `product_research.md`)
- Tier construction logic (owned by `pricing_tiers.md`)
- Output templates (owned by `*_template.md` files)

### Who uses this file (hierarchy)
This is a **low-level policy module** used by:
- `product_research.md` (when providing “where to buy” options)
- `pricing_tiers.md` (when providing sellers per tier)
- `research_sources.md` (when a “source” is a seller listing or store page)

---

## 1) North star: risk-adjusted comparable total

### Comparable total (the decision basis)
Comparable total = item price + shipping + mandatory fees

Notes:
- If shipping/fees are hidden until late checkout, treat the offer as lower quality and document uncertainty.
- If the user explicitly requests tax-included totals, calculate and present them separately as “tax-included total (if available).”

### Tie-break rule (scaled, not vague)
When two offers are close in comparable totals, prefer the higher-trust channel.

Define the tie-break threshold using the **cheaper offer’s comparable total**:

Tie-break threshold = ROUND_TO_NEAREST_DOLLAR( MAX(10, MIN(25, 0.07 * cheaper_comparable_total)) )

Interpretation:
- Minimum premium: $10
- Typical scaling: ~7% of the cheaper total
- Maximum premium: $25

Decision rule:
- If the comparable totals are within the tie-break threshold, choose the higher-trust option.
- If outside the threshold, the cheaper option can win **only if** it passes the Red-Flag Gate and protections/returns are adequate for the item’s risk posture.

Override hook (for upstream workflows):
- Workflows may tighten acceptable channels when `risk_channel` or `risk_safety` is high (typically restricting low-trust sellers), but should not expand the price premium without stating the rationale.

---

## 2) Seller-of-record vs fulfillment (mandatory fields)

For each offer, record:
- **Seller-of-record**: who you pay; who is responsible for the transaction.
- **Fulfillment party**: who ships and handles delivery logistics.

On marketplaces, these can differ (e.g., “Sold by X, Fulfilled by Amazon”).
This distinction matters for:
- counterfeit/channel risk
- return routing and friction
- delivery/DOA handling

---

## 3) Candidate seller set (preference without exclusion)

### Default preference (commodity / widely-available products)
When the **exact model/variant** is available at similar comparable totals, prefer:
- Amazon (prefer sold by Amazon; otherwise FBA with clean seller signals)
- Walmart (prefer sold/shipped by Walmart)
- Target (prefer sold/shipped by Target)
- Best Buy (electronics)
- Home Depot / Lowe’s (home improvement / appliances)
- B&H / Adorama (photo/AV)

### Specialty and niche sellers (explicitly allowed)
Do not filter these out by default:
- Brand-direct storefronts (manufacturer websites)
- Reputable specialty retailers in a niche
- Legit independent storefronts (non-marketplace)

These require stronger policy clarity and a clean Red-Flag Gate result.

---

## 4) Trust tiers (channel quality)

Assign each offer a tier. Tiers drive tie-breaks and required diligence.

- **Tier 1: Big-box direct retail**
  - Platform is the seller-of-record (and fulfillment is controlled by the platform or its standard logistics).
- **Tier 2: Major marketplace with platform fulfillment**
  - Seller-of-record is third-party; fulfillment is handled by the major platform; platform-level buyer protections apply.
  - Record seller-of-record and fulfillment party (returns details are handled in the evidence packet requirements).
- **Tier 3: Reputable specialty retailer (direct)**
  - Seller-of-record is the specialist retailer; policies and warranty handling are clear.
- **Tier 4: Brand-direct (manufacturer)**
  - Seller-of-record is the manufacturer; checkout, returns, and warranty/RMA are clear.
- **Tier 5: Vetted independent storefront**
  - Seller-of-record is an independent merchant; must pass Red-Flag Gate; clear policies; normal payments.
- **Tier 6: High-risk marketplace / opaque overseas channel**
  - Seller-of-record is unclear/opaque or protections are weak; allowed only as explicit last resort and must be labeled higher-risk.

---

## 5) Red-Flag Gate (hard stops, caps, yellow flags)

Run this gate before comparing prices. If a hard stop triggers, exclude unless the user explicitly accepts the risk.
Do not recommend circumventing buyer protections (e.g., off-platform payment).

### Hard stops (exclude by default)
- Payment methods are wire/crypto/Zelle/gift cards only (no credit card / PayPal equivalents).
- Off-platform ordering pressure (e.g., “contact us on WhatsApp/email to complete purchase”).
- No discoverable return policy prior to purchase, or policy conflicts with checkout terms.
- No real business identity: missing physical address and credible contact path; obvious typosquat domain; copied “About/Policies.”
- Foreign return trap: return address outside the US for items > $30, unless user explicitly accepts.
  - Exception: brand-direct or reputable specialty sellers may have non-US return logistics; require explicit pre-purchase clarity and user acceptance.
- Product identity mismatch: SKU/model/variant inconsistency; “compatible with” instead of exact item; images don’t match listing claims.
- Counterfeit/gray-market indicators: “international warranty only,” “no manufacturer warranty,” serial removed/obscured, suspicious “OEM” claims where OEM is implausible.
- Condition bait-and-switch: listed as “new” but fine print indicates open-box/renewed/“new other.”

### Score caps (allowed but penalized; must be called out)
If kept, cap seller confidence at 60/100 and document why:
- Seller is very new/low history and the item is high-ticket.
- Pattern of wrong-item / DOA / missing parts in recent seller feedback.
- Returns require unusual steps or unclear processing timelines.
- Price anomaly > 20% below typical market with no credible explanation.

### Yellow flags (note; do not exclude automatically)
- Unclear fulfillment origin, but no other scam signals.
- Sparse policy language, but still discoverable and internally consistent.
- Mixed feedback focused on shipping/packaging rather than the product itself (channel contamination).

---

## 6) Risk posture escalations (inputs from other files)

This file reacts to upstream signals; it does not originate them.

Upstream risk posture signals may include:
- risk_channel: low/medium/high
- risk_safety: low/medium/high
- risk_shipping: low/medium/high
- risk_fitment: low/medium/high

Default escalation rules:
- If risk_channel=high (counterfeit-prone): prefer Tier 1–4; require stricter identity + warranty evidence for Tier 2–5; Tier 6 only with explicit user acceptance.
- If risk_safety=high: prefer channels with clear compliance/warranty language and low-friction returns.
- If risk_shipping=high: prefer strong DOA handling and generous return terms; deprioritize sellers with packaging/DOA complaints.
- If risk_fitment=high: prioritize easy returns, long windows, low/no restocking fees, and domestic returns.

General rule:
- As comparable total increases, require proportionally stronger evidence of legitimate policies, domestic returns, and buyer protections.

---

## 7) Stock, fulfillment confidence, and ETA

Treat stock/ETA as purchase risk. If it’s unclear, penalize the offer.

“In stock” baseline (default):
- A concrete delivery window or ship date is visible before purchase completion.

Deprioritize:
- “Ships in weeks,” backorders, preorders (unless the user explicitly wants that)
- vague “in stock soon” language

---

## 8) Minimum seller evidence packet (required per shortlisted offer)

For each seller offer in a shortlist, capture:

A) Seller identity and channel facts
- Seller-of-record
- Fulfillment party
- Trust tier

B) Product identity
- Exact model/SKU/variant (capacity/color/region), sufficient to confirm it is the same item across sellers

C) Pricing (comparable total)
- Comparable total and what it includes (item + shipping + mandatory fees)
- Any membership assumptions or checkout-only pricing

D) Returns and protections
- Return window (days)
- Restocking fee (if any)
- Who pays return shipping
- Return address country (US vs non-US)
- Warranty handling (manufacturer vs seller; US warranty vs international if stated)

E) Flags
- Any hard stop/cap/yellow flags encountered and why they matter

F) Timestamp
- Prices and availability checked: YYYY-MM-DD hh:mm ET

---

## 9) Scoring rubric (optional; for justification and tie-breaks)

Use scoring only as a transparency tool; do not let scoring override hard stops.

Default weights:
- Comparable total: 35
- Returns & buyer protection: 25
- Trust tier & seller legitimacy: 20
- Stock/ETA confidence: 10
- Channel risk signals (counterfeit/gray-market/DOA trend): 10

---

## 10) Output requirements when invoked by workflows

When downstream workflows include seller guidance, they must provide:
- At least 2 seller options when feasible
- Comparable totals
- Seller-of-record and fulfillment party
- Trust tier
- Key return/warranty facts
- Any relevant flags and whether an offer is capped/excluded
- Timestamp

No product-quality claims. No review interpretation. Seller/channel only.
