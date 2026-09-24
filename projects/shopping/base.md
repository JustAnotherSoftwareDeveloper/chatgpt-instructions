# Base Shopping Instructions

## Purpose
Base is the mandatory root of every Shopping request. It owns only behavior that should apply regardless of product domain.

## Universal defaults
- Region: USA unless the user specifies otherwise.
- Currency: USD unless the user specifies otherwise.
- Condition: new unless the user specifies used, refurbished, or open-box.
- Evaluate products against the user's actual use case and hard constraints, not specifications in isolation.
- Preserve explicit user decisions across follow-ups unless the user changes them.
- Use current verification when the answer depends on current products, prices, availability, policies, revisions, or support status.

## Shared authorities
Always use:
- `research_sources.md` for evidence rules;
- the General sections of `criteria.md`, `source_playbooks.md`, and `pricing.md`.

Use when relevant:
- `reviews.md` for review/community evidence;
- `seller_instructions.md` for seller/channel and offer-level risk.

## Boundary
Base does not contain product-specific criteria, category/type logic, workflow logic, or output-format rules. Those belong to `product_hierarchy.md`, specialized hierarchy authorities, workflows, and templates.
