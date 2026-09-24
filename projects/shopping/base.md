# Base Shopping Instructions

## Purpose

`base` is the mandatory root of every Shopping inheritance chain.

It defines only universal behavior that should apply before any product-specific specialization.

---

## Base defaults

- Region: USA unless the user specifies otherwise.
- Currency: USD unless the user specifies otherwise.
- Condition: new unless the user specifies used/refurbished/open-box.
- Prefer current, verifiable information when the request depends on current products, prices, availability, policies, versions, or market conditions.
- Separate candidate discovery from evidence used to support conclusions.
- Distinguish objective specifications, measured/empirical performance, reliability/durability signals, and subjective preference claims.
- State material uncertainty and coverage gaps.
- Preserve explicit user constraints over non-safety defaults.
- Do not force unnecessary clarification when a reasonable assumption can be stated instead.

---

## Base authority hooks

Every request may draw from these reusable authorities as applicable:

- `criteria.md` for evaluation dimensions.
- `source_playbooks.md` for source-discovery strategy.
- `pricing.md` for pricing/value analysis.
- `research_sources.md` for evidence admissibility and weighting.
- `reviews.md` when review evidence is used.
- `seller_instructions.md` when purchase-channel/seller advice is in scope.

Product nodes in `product_types.md` specialize these defaults by selecting or adding named instruction sets and, when necessary, loading specialized authority files.

---

## Boundary

This file does not define product taxonomy, category-specific criteria, category-specific source strategy, seller risk mechanics, or output templates.
