# Pricing Authority

## Purpose

This file owns reusable pricing and value-analysis strategies selected by Base and product nodes.

---

## Strategies

### general-value
- Compare like-for-like configurations and conditions.
- Distinguish purchase price from meaningful total cost of ownership when relevant.
- Treat current price and availability as time-sensitive facts that require current verification.
- Do not recommend a materially worse or riskier product merely to satisfy an arbitrary lower price tier.
- Explain what additional spend actually unlocks and where diminishing returns begin when evidence supports it.

---

## Inheritance behavior

`pricing.strategy` is a single inherited property.

- If a Class defines a strategy, it replaces the inherited strategy for that branch.
- A Category may replace the inherited strategy.
- A Type may replace the inherited strategy.
- The closest node to the resolved leaf that defines `pricing.strategy` wins.

Do not combine multiple pricing strategies implicitly. If a domain needs composite pricing behavior, define that composite as one named strategy here or load a registered specialized authority.

Category/type-specific pricing logic belongs here when reusable; narrow specialized economics may live in a dedicated registered authority referenced by the product node.

---

## Boundary

This file owns product pricing/value strategy definitions and their inheritance semantics. It does not decide which strategy Base or a product node selects. Seller legitimacy, return risk, fulfillment, and offer-channel trust belong to `seller_instructions.md`; product classification belongs to `product_types.md`.
