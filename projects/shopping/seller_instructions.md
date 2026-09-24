# Seller and Purchase-Channel Authority

## Purpose
Own seller/channel evaluation and offer-level purchase risk when where/how the user buys materially affects the recommendation.

This file evaluates a concrete offer or channel. It does not decide which product is best.

## 1) Separate product quality from offer quality
For every concrete offer, distinguish:
- the product/model/variant itself;
- seller of record;
- fulfillment party;
- condition;
- current price and included items;
- returns/warranty path;
- provenance/authorized-channel status where relevant.

A good product can be a bad offer. A trustworthy seller does not make a poor product good.

## 2) Comparable offer basis
When comparing seller offers, normalize enough to make the comparison fair.

Use, when available:
- item price;
- mandatory shipping;
- mandatory fees;
- required membership assumptions;
- included accessories/bundles that materially differ;
- condition differences.

Taxes may be excluded from cross-seller comparison unless the user asks for tax-inclusive totals or reliable location-specific tax is available.

Do not hide meaningful return shipping, restocking, or warranty costs merely because they are not charged at checkout.

## 3) Seller identity and fulfillment
Identify, when material:
- who receives the payment / is seller of record;
- who fulfills/ships the item;
- whether the transaction occurs directly, through a marketplace, or through an authorized dealer network.

Marketplace platform reputation must not be substituted for third-party seller identity.

## 4) Evaluate offers on dimensions, not a universal seller ranking
There is no fixed rule that big-box, marketplace, specialist, or brand-direct is always better.

Evaluate:
### Identity and legitimacy
- discoverable business identity and contact path;
- coherent domain/store presence;
- no obvious impersonation, typosquat, or copied-policy signals.

### Product identity and provenance
- exact model/SKU/variant/size/region;
- stated condition;
- authorized-dealer status when it affects warranty/provenance;
- counterfeit or gray-market exposure where relevant;
- serial/warranty limitations when disclosed.

### Buyer protection and returns
- return window;
- restocking or return-shipping burden;
- domestic vs difficult international returns when material;
- condition restrictions;
- marketplace/platform protection;
- DOA/damage process for fragile or expensive goods.

### Warranty and support
- manufacturer warranty eligibility;
- seller-only warranty vs manufacturer support;
- regional/international warranty limitations;
- whether the seller meaningfully facilitates service/RMA.

### Fulfillment and stock confidence
- credible in-stock status;
- expected ship/delivery window;
- backorder/preorder ambiguity;
- packaging/shipping risk appropriate to the item.

### Price realism
- compare against normal current market pricing;
- unusually low prices require more identity/provenance verification rather than automatic rejection or acceptance.

## 5) Red flags
Exclude or clearly warn on offers with material unresolved problems such as:
- off-platform payment pressure or payment methods that remove normal buyer protection;
- seller identity that cannot be reasonably established;
- contradictory model/variant/condition information;
- no discoverable return policy for a meaningful purchase;
- new-condition listing whose fine print indicates used/open-box/refurbished status;
- suspected counterfeit or misleading "OEM" identity;
- warranty representation that conflicts with manufacturer/authorized-channel terms;
- a price anomaly combined with weak provenance or protection;
- returns that are impractical relative to the item's value/risk without being clearly disclosed.

Do not recommend bypassing normal buyer protections to obtain a lower price.

## 6) Authorized, gray-market, and specialist channels
Treat channel type as a tradeoff, not a moral label.

### Authorized channel
May offer stronger manufacturer warranty/provenance confidence, but may cost more.

### Gray market / parallel import
May be legitimate but can change warranty, region, included accessories, service, resale, or return risk. State the actual consequence rather than using "gray market" as a blanket rejection.

### Specialist retailer
May be particularly strong in enthusiast/niche categories because of expertise, curation, service, sharpening/setup, or access to makers. Evaluate actual policies and reputation rather than assuming major retail is safer/better.

### Marketplace
Assess seller-of-record and fulfillment separately. Platform protection can reduce transaction risk without eliminating counterfeit, wrong-item, or warranty concerns.

## 7) Counterfeit-prone or provenance-sensitive products
Increase diligence when the product/category has meaningful counterfeit, clone, relabel, or provenance risk.

Prefer corroboration of:
- exact SKU/model;
- authorized-dealer status where relevant;
- maker/brand identity;
- warranty status;
- realistic pricing;
- specialist/community warnings about known counterfeit patterns.

Do not infer counterfeit status solely from low price or marketplace presence.

## 8) Offer recommendation
When the workflow asks where to buy:
- prefer the best risk-adjusted offer, not automatically the cheapest;
- explain material differences in price, returns, warranty, provenance, or fulfillment;
- include more than one seller option when useful and genuinely competitive;
- do not force a second seller merely to satisfy a quota.

The acceptable premium for a safer/easier channel is context-dependent. Consider product cost, return likelihood, counterfeit risk, warranty value, item fragility, and user preference rather than applying a fixed dollar or percentage formula.

## 9) Current-offer evidence
For a concrete recommendation, capture internally as applicable:
- seller of record;
- fulfillment party;
- exact product/variant and condition;
- current normalized price;
- return window/friction;
- warranty/provenance posture;
- stock/delivery confidence;
- material flags;
- when the offer was checked.

Normal output should surface only the fields that change the purchase decision. `audit.md` may inspect the deeper offer basis.

## Boundary
Product quality belongs to active criteria and hierarchy authorities; general evidence standards belong to `research_sources.md`; review interpretation belongs to `reviews.md`; reusable product-value logic belongs to `pricing.md`.
