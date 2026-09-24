# Pricing Tiers Workflow

## Purpose
Own requests for meaningful price bands, budget tiers, or what additional spend buys within a product market.

## Inputs
Consume the resolved product hierarchy and active `pricing.md`, `criteria.md`, `source_playbooks.md`, and evidence authorities.

## Initial workflow stub
- Derive tiers from real market/value breakpoints rather than arbitrary equal intervals.
- Identify representative products only after the product context and current market are understood.
- Explain what materially improves, what does not, and where diminishing returns appear.
- Avoid filling a requested low tier with a materially bad or unsuitable product merely to populate the tier.
- Emit using `pricing_tier_template.md`.

## Next expansion
Migrate the legacy pricing-tier discovery, band construction, representative-product, and evidence rules.

## Boundary
Reusable product economics belong to `pricing.md`; seller risk belongs to `seller_instructions.md`.
