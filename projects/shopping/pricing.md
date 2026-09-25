# Pricing Guidance

## Purpose
Define generic reusable product-value and pricing logic used by hierarchy registry entries and pricing workflows.

This file explains how to interpret price and value. It does not evaluate seller legitimacy, define current market tiers, choose final products, or own domain-specific value interpretation.

Domain-specific value logic belongs in the active entries of `class.md`, `category.md`, and `type.md` as named Pricing contributions under the composition rules in `product_hierarchy.md`.

## Hierarchy contribution surface
The canonical hierarchy target exposed by this authority is:
- `Pricing -> Value interpretation`

Registry entries may **Merge** domain-specific value interpretation into this target. The Merge is additive to the generic price-state, marginal-value, and diminishing-returns semantics below.

This authority exposes no hierarchy Override target. Registry entries may not replace the generic price-state model, deal-quality definitions, marginal-value semantics, diminishing-returns definition, or silently invent alternate Pricing contribution targets.

## 1) General Value
- Compare like-for-like products, conditions, configurations, and included accessories.
- Distinguish product quality, product value, seller quality, and temporary deal quality.
- Treat current pricing as time-sensitive when it materially affects the answer.
- Distinguish purchase price from meaningful ownership cost when consumables, required accessories, subscriptions, service, or maintenance matter.
- Explain what additional spend buys in concrete terms: capability, consistency, durability, support, materials, fit/finish, convenience, aesthetics, rarity, or other real differences.
- Do not populate a budget tier with a materially bad or unsuitable product merely because it fits the price.
- A cheaper product can be the better value even when it is not the highest-performing product; a more expensive product can be justified when its advantages align with the user's actual priorities.

## 2) Price-state model
When current price matters, classify observed prices instead of treating every listing as the product's price.

### MSRP / list price
Manufacturer/list anchor. Useful context, but not proof of normal market value.

### Normal street price
The price or narrow range at which reputable sellers commonly offer the exact product/condition outside unusual short-lived promotions.

### Current typical reputable range
The current cluster of comparable Acceptable offers under `seller_instructions.md`.

### Current low reputable offer
The best current Acceptable/Preferred offer after normalizing condition, bundle, shipping/fees, warranty/provenance, and material seller differences.

### Recurring-sale range
A lower price band that appears repeatedly enough to represent a realistic waiting opportunity rather than an exceptional one-off. Use only when supported by historical/current evidence; do not invent from MSRP discount percentages.

### Clearance / generation-exit price
A low price tied to discontinuation, replacement generation, liquidation, or inventory exit. Do not let clearance redefine the long-term tier/value position without saying so.

### Anomalous price
An outlier that may reflect coupon/member conditions, wrong variant, used/open-box condition, marketplace risk, pricing error, counterfeit/provenance risk, or exceptional promotion. Apply `seller_instructions.md` when concrete.

## 3) Establishing a normal price baseline
For meaningful deal/value judgments, prefer this sequence:
1. lock exact model/variant/condition;
2. inspect multiple current reputable offers where the market supports them;
3. distinguish stable cluster from outliers, membership/coupon prices, bundles, and clearance;
4. use manufacturer/list price only as secondary context;
5. use historical/recurring sale evidence when the question is "buy now or wait" or when current promotion may distort tier placement.

A normal-price baseline can be a range; do not force a single dollar estimate when market dispersion is real.

When only one legitimate seller exists, say the market is single-source rather than pretending to establish a competitive street price.

## 4) Deal-quality interpretation
For a concrete offer, judge against the relevant baseline:
- **Poor:** materially above normal reputable market without compensating bundle/service/value;
- **Normal/fair:** within ordinary reputable street range;
- **Good:** meaningfully below ordinary range with ordinary protections/provenance;
- **Exceptional:** unusually low relative to normal/recurring-sale range and verified as legitimate.

Do not attach fixed percentage labels across all categories. Use `seller_instructions.md`'s >=20% anomaly trigger for extra diligence, not as the definition of an exceptional deal.

## 5) Marginal-value reasoning
For any meaningful price gap between finalists ask:
- What concrete capability/quality/ownership improvement is purchased?
- Which users will notice/value it?
- What does **not** improve despite the price gap?
- Is the gain broad, narrow/specialized, aesthetic/craft-driven, or mainly prestige/rarity?
- Is the difference durable across normal pricing or only caused by today's sale?

## 6) Diminishing returns
Diminishing returns begin where successive price increases stop producing broad improvement in the user's primary functional/ownership criteria and increasingly buy secondary preference, refinement, fit/finish, craft, specialization, rarity, prestige, or collector value.

Do not imply spending past that point is irrational when the user values those attributes.

## Boundary
This file owns generic product pricing/value interpretation only. Domain-specific value interpretation belongs to active hierarchy registry entries; current offer risk and seller quality belong to `seller_instructions.md`; tier construction belongs to `pricing_tiers.md`; generic criterion semantics belong to `criteria.md`.
