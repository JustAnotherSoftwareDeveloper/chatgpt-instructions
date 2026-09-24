# Base Shopping Instructions

## Purpose

`base` is the mandatory root of every Shopping inheritance chain.

It defines universal defaults and activates the instruction sets that every shopping request starts with. It does not own evidence-policy details or product-domain specialization.

---

## Universal defaults

- Region: USA unless the user specifies otherwise.
- Currency: USD unless the user specifies otherwise.
- Condition: new unless the user specifies used, refurbished, or open-box.
- Preserve explicit user constraints over non-safety defaults.
- Ask for clarification only when the missing information materially changes correctness; otherwise make and state a reasonable assumption.

---

## Base instruction activation

Base always activates:

### Evaluation criteria
From `criteria.md`:
- `value`
- `reliability`
- `compatibility`
- `usability`

### Source discovery
From `source_playbooks.md`:
- `general-shopping`

### Pricing strategy
From `pricing.md`:
- `general-value`

### Evidence authority
- `research_sources.md` is always active for evidence admissibility, weighting, recency, breadth, and claim-to-evidence discipline.

Conditional authorities:
- load `reviews.md` when review evidence is used;
- load `seller_instructions.md` when seller/channel, current offer, return/warranty, or purchase-risk advice is in scope.

Product nodes in `product_types.md` may add criteria, add/remove discovery playbooks, replace the inherited pricing strategy with a more-specific named strategy, and load specialized live authorities.

---

## Boundary

This file does not define product taxonomy, category-specific criteria, source-evidence rules, review heuristics, seller-risk mechanics, category-specific pricing logic, or output formats. Those belong to their canonical authorities.
