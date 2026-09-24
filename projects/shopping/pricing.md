# Pricing Authority

## Purpose

This file owns reusable pricing and value-analysis strategies selected by Base and product nodes.

---

## Base pricing strategy

### general-value
- Compare like-for-like configurations and conditions.
- Distinguish purchase price from meaningful total cost of ownership when relevant.
- Treat current price and availability as time-sensitive facts that require current verification.
- Do not recommend a materially worse or riskier product merely to satisfy an arbitrary lower price tier.
- Explain what additional spend actually unlocks and where diminishing returns begin when evidence supports it.

`base.md` selects `general-value`.

---

## Inheritance behavior

`pricing.strategy` is a single inherited property.

- Base starts with `general-value`.
- If a Class defines another strategy, it replaces the Base strategy for that branch.
- A Category may replace the inherited strategy.
- A Type may replace the inherited strategy.
- The closest node to the resolved leaf that defines `pricing.strategy` wins.

Do not combine multiple pricing strategies implicitly. If a domain needs composite pricing behavior, define that composite as one named strategy here or load a specialized authority.

Category/type-specific pricing logic belongs here when reusable; narrow specialized economics may live in a dedicated authority referenced by the product node.

---

## Boundary

This file owns product pricing/value strategy. Seller legitimacy, return risk, fulfillment, and offer-channel trust belong to `seller_instructions.md`; product classification belongs to `product_types.md`.
