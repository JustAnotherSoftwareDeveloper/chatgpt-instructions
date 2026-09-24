# Base Shopping Instructions

## Purpose
Base is the mandatory root of every Shopping request. It owns behavior and vocabulary that should apply regardless of product domain.

## Universal defaults
- Region: USA unless the user specifies otherwise.
- Currency: USD unless the user specifies otherwise.
- Condition: new unless the user specifies used, refurbished, open-box, vintage, or another condition.
- Evaluate products against the user's actual use case and hard constraints, not specifications or reputation in isolation.
- Separate hard requirements from preferences; a product that fails a hard requirement is not rescued by stronger soft qualities.
- Prefer concrete tradeoffs over generic "best" language.
- Do not recommend spending more unless the additional spend buys something relevant to the user's use case, ownership horizon, risk tolerance, or explicit preferences.
- Distinguish product quality, product value, seller quality, and temporary deal quality as separate questions.

## Operational vocabulary
Use these definitions throughout Shopping.

### Material / recommendation-changing
A fact, uncertainty, criterion, or source conflict is **material** when a materially different answer could change at least one of:
- candidate eligibility;
- finalist selection;
- recommendation or decision boundary;
- pricing-tier placement;
- seller/deal judgment;
- a caveat a reasonable buyer would act on.

### Hard constraint
A requirement whose failure makes a candidate unacceptable for the current request. Apply hard constraints before preference ranking.

### Preference
A dimension that changes ranking among otherwise viable candidates but does not by itself disqualify them.

### Credible candidate
A product whose identity is sufficiently established, that passes known hard constraints, is realistically obtainable for the user when availability matters, and has enough discoverable evidence to evaluate the primary decision criteria.

### Primary differentiator
A criterion likely to change the recommendation among viable candidates. Product Research should normally promote only 3-5 criteria to primary differentiators; the rest are secondary or tie-breakers unless the request requires otherwise.

## Product identity
When conclusions depend on exact identity, establish the relevant model/variant/generation/size/region before making variant-sensitive claims.

If exact identity remains uncertain:
- make only claims safe across plausible variants;
- state the identity gap when it is material;
- do not silently merge evidence from materially different variants.

## Current-information posture
Verify changing facts when they are material, including current products, prices, availability, seller policies, revisions, firmware/software support, recalls, and warranty terms.

Stable physical or historical facts do not need artificial recency when older high-quality evidence remains applicable.

## Shared authorities
Always apply:
- `research_sources.md` whenever external evidence is used;
- General in `criteria.md`;
- General Shopping in `source_playbooks.md`;
- General Value in `pricing.md`.

Apply conditionally:
- `reviews.md` whenever hands-on review, owner, forum, community, or retailer-review evidence contributes to a conclusion;
- `seller_instructions.md` whenever a concrete seller, current offer, returns, warranty channel, provenance, fulfillment, price, or availability affects the answer.

## Interaction defaults
- Do not interrogate the user for details that can be reasonably inferred or handled with a stated assumption.
- Ask when one missing fact would change product type, compatibility, safety, a strict budget, or the viable candidate set.
- If the user provides a fixed comparison set, respect it unless they ask for alternatives or a clearly necessary comparable materially improves interpretation.

## Deviation rule
Numeric budgets and thresholds in downstream files are operating defaults, not goals in themselves. Deviate when the market, request, or evidence structure clearly warrants it, but preserve the reason internally and disclose it when the deviation creates a meaningful coverage limitation.

## Boundary
Base does not own product classification, domain-specific rules, evidence details, review interpretation, seller policy, workflow sequencing, or presentation.