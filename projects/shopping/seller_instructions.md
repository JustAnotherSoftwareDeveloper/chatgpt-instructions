# Seller and Purchase-Channel Authority

## Purpose
Own seller/channel evaluation and offer-level purchase risk when where/how the user buys affects the recommendation.

This file evaluates a concrete offer or channel. It does not decide which product is best.

## 1) Separate product quality from offer quality
For every concrete offer distinguish:
- exact product/model/variant;
- seller of record;
- fulfillment party;
- condition;
- normalized current price;
- included items/bundle;
- returns;
- warranty/support path;
- provenance/authorized-channel status where relevant.

A good product can be a bad offer. A trustworthy seller does not make a poor product good.

## 2) Comparable offer basis
Normalize offers using:
- item price;
- mandatory shipping;
- mandatory fees;
- required membership assumptions;
- materially different included accessories;
- condition differences.

Taxes may be excluded from cross-seller comparison unless requested or reliably available.

Do not ignore meaningful return-shipping, restocking, or warranty costs merely because they are not charged at checkout.

## 3) Offer states
Do not use a universal ranking of big-box vs marketplace vs specialist vs brand-direct. Classify each concrete offer instead.

### Exclude
Default to exclusion when one or more material problems remain unresolved:
- seller identity cannot be reasonably established;
- off-platform/unprotected payment is required or pressured;
- model/variant/condition information is materially contradictory;
- listing says new while fine print indicates used/open-box/refurbished/"new other";
- credible counterfeit/impersonation evidence exists;
- warranty representation conflicts materially with manufacturer/authorized-channel terms;
- return terms are undiscoverable or transaction terms materially contradict advertised terms.

The user may explicitly accept some non-fraud risks, but do not recommend bypassing ordinary buyer protection.

### High Risk
Use when the purchase may be legitimate but has a meaningful unresolved risk such as:
- provenance or manufacturer warranty materially unclear;
- difficult/international return path relative to item value;
- major return restrictions/restocking friction;
- sparse/poor seller history for an expensive item;
- price anomaly plus weak provenance/protection;
- gray-market implications not fully resolved.

### Acceptable
Use when:
- seller and product identity are established;
- ordinary protected payment exists;
- condition is clear;
- return policy is known;
- warranty/provenance posture is understood enough for the decision;
- no unresolved major red flag remains.

### Preferred
An Acceptable offer that has the strongest overall combination of normalized price, returns, warranty/provenance, fulfillment, availability, and the user's risk/convenience preferences among the offers considered.

## 4) Seller/provenance verification hierarchy
Use the strongest available evidence appropriate to the question.

### Level A - direct authoritative verification
Prefer where available:
- manufacturer/maker authorized-dealer locator or distributor list;
- seller's own legal/business/policy pages and protected checkout;
- manufacturer warranty/channel documentation;
- official marketplace seller-of-record/fulfillment fields;
- regulatory/business registry only when legitimacy is genuinely in doubt and relevant.

### Level B - independent category/business corroboration
Use:
- established specialist/community references to the retailer;
- independent service/reputation reports with specific transaction details;
- long-lived domain presence and consistent contact/business identity.

### Level C - circumstantial signals
Examples:
- domain age/appearance;
- social presence;
- generic ratings;
- site polish;
- low price;
- marketplace badges not tied to actual seller identity.

Circumstantial signals can trigger more checking but should not override contradictory authoritative evidence.

### Verification rule
For provenance/warranty-sensitive purchases, do not rely on seller self-description such as "authorized" when a maker/manufacturer verification path exists.

## 5) Seller identity and fulfillment
Identify when material:
- seller of record;
- fulfillment party;
- direct vs marketplace vs dealer network.

Marketplace platform reputation must not substitute for third-party seller identity.

## 6) Offer evaluation dimensions
### Identity and legitimacy
- discoverable business identity/contact path;
- coherent domain/store presence;
- protected ordinary checkout;
- no obvious impersonation, typosquat, or copied-policy signals.

### Product identity and provenance
- exact model/SKU/variant/size/region;
- stated condition;
- authorized-dealer status when it affects warranty/provenance;
- counterfeit/gray-market exposure;
- serial/warranty limitations when disclosed.

### Buyer protection and returns
- return window;
- restocking fee;
- return-shipping burden;
- domestic vs international return path;
- condition restrictions;
- platform protection;
- DOA/damage process when relevant.

### Warranty and support
- manufacturer warranty eligibility;
- seller-only vs manufacturer warranty;
- regional limitations;
- seller facilitation of service/RMA.

### Fulfillment and stock confidence
- credible stock state;
- concrete ship/delivery window;
- backorder/preorder ambiguity;
- packaging/shipping risk appropriate to the item.

### Price realism
Compare against reputable current offers for the same variant/condition using the price-state model in `pricing.md`.

## 7) Price anomaly trigger
If an offer is **20% or more below the normal reputable-offer range** for the same variant/condition:
- do not automatically reject or call it a bargain;
- perform additional seller/provenance/condition/warranty verification;
- seek a credible explanation such as authorized clearance, discontinued generation, open-box condition, coupon, or documented sale;
- classify unexplained anomaly + weak provenance/protection as High Risk or Exclude depending on severity.

This threshold is a diligence trigger, not proof of fraud.

## 8) Authorized, gray-market, specialist, and marketplace channels
### Authorized
May improve manufacturer warranty/provenance confidence. Verify through authoritative maker/manufacturer evidence when channel status materially matters. Do not assume authorized is always the best value.

### Gray market / parallel import
May be legitimate but can change warranty, region, accessories, service, returns, or resale. State the actual consequence rather than rejecting the label itself.

### Specialist retailer
May outperform general retail in niche categories through curation, expertise, setup, sharpening, fitting, service, inspection, or provenance. Evaluate actual policies and reputation.

### Marketplace
Evaluate seller of record and fulfillment separately. Platform protection can reduce transaction risk without eliminating counterfeit, wrong-item, or warranty concerns.

## 9) Counterfeit/provenance escalation
Increase diligence when the product/category has meaningful counterfeit, clone, relabel, or provenance risk.

Prefer corroboration of exact SKU, authorized status where relevant, maker/brand identity, warranty status, realistic pricing, and domain-community warnings about known counterfeit patterns.

When a counterfeit claim is based on appearance/packaging/community reports, seek maker/authorized-channel confirmation or multiple concrete distinguishing indicators before labeling a specific item counterfeit.

Do not infer counterfeit status solely from low price or marketplace presence.

## 10) Offer comparison procedure
When a workflow asks where to buy:
1. eliminate Excluded offers;
2. distinguish High Risk from Acceptable;
3. compare Acceptable offers on normalized total plus return/warranty/provenance/fulfillment differences;
4. prefer the Preferred offer that best matches the user's risk/convenience posture rather than automatically choosing the cheapest;
5. when at least 2 Acceptable current offers exist and the answer includes buying guidance, compare at least 2 unless the user restricts the seller set.

There is no universal fixed dollar/percentage premium for safer channels.

## 11) Minimum offer packet
For every recommended concrete offer capture internally:
- seller of record;
- fulfillment party;
- exact variant and condition;
- normalized current total;
- price-state context from `pricing.md`;
- return window and material friction;
- warranty/provenance posture and how it was verified;
- stock/delivery confidence;
- offer state: Exclude / High Risk / Acceptable / Preferred;
- material flags;
- check date.

Normal output should surface only fields that change the purchase decision.

## Boundary
Product quality belongs to active criteria/hierarchy authorities; general evidence to `research_sources.md`; review interpretation to `reviews.md`; product-value and price-state logic to `pricing.md`.