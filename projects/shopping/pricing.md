# Pricing Authority

## Purpose

This file owns reusable pricing and value-analysis instruction sets selected by product nodes and pricing workflows.

---

## Base pricing strategy

### general-value
- Compare like-for-like configurations and conditions.
- Distinguish purchase price from meaningful total cost of ownership when relevant.
- Treat current price and availability as time-sensitive facts that require current verification.
- Do not recommend a materially worse or riskier product merely to satisfy an arbitrary lower price tier.
- Explain what additional spend actually unlocks and where diminishing returns begin when evidence supports it.

---

## Inheritance behavior

- Base provides `general-value`.
- A product node may `use` a pricing strategy when no more-specific strategy is inherited.
- A product node may `override` an inherited strategy when its economics are materially different.
- Category/type-specific pricing logic should live here or in a specialized authority, not inline in `product_types.md`.

Detailed pricing behavior from the prior Shopping implementation remains under `archive/` for deliberate migration.
