# Pricing Tiers Workflow

## Purpose
Own meaningful price-band, budget-tier, good-better-best, and "what does spending more buy?" analysis within a product market.

Use the resolved product context plus active `pricing.md`, `criteria.md`, `source_playbooks.md`, and evidence authorities.

This workflow constructs live market tiers. It does not define research modes, reusable price states, seller risk, or timeless dollar bands.

## 1) Research mode
Apply the research mode selected by `research_sources.md`. Do not redefine Quick / Standard / Deep / Sparse triggers here.

Pricing/availability is always in scope for this workflow.

## 2) Scope the market
Capture or infer:
- product context/use case;
- user budget ceiling/target if supplied;
- region/condition;
- must-have constraints;
- whether user wants broad market map, budget options, or explicit good/better/best.

A strict budget ceiling is a hard constraint unless user signals flexibility.

## 3) Market scan
For a mature market, default discovery target:
- **10-15 credible current products**;
- at least **4 makers/brands** when available;
- cover the credible entry point through premium/mainstream ceiling relevant to the request;
- include specialty/luxury territory only when it is a real part of the requested market.

Use fewer only when the market or hard constraints are genuinely narrow. Search wider when the market shows additional distinct segments or the selected research mode calls for greater depth.

Discovery sources may map products/prices but tier conclusions and representative picks require admissible evidence.

## 4) Build a market/design/value segment map
Before assigning tiers, identify the meaningful product families that explain the market.

For each segment capture internally:
- design/value philosophy;
- target buyer/use case;
- defining traits;
- primary strengths;
- structural compromises;
- price posture under `pricing.md`;
- representative products;
- whether the user should care about this segment.

Do not assume price itself defines the segment. Two products at the same price may represent different design philosophies, and one design family may span multiple prices.

## 5) Normalize price posture
Apply the price-state model and normal-price baseline procedure from `pricing.md` to products used in the tier map.

Tier placement should reflect the product's defensible normal/current market posture, not a misleading list price, one-off promotion, clearance event, or unverified anomaly.

Record temporary sale/clearance effects separately when they create a cross-tier value opportunity.

## 6) Initial tier geometry
Default to **3-5 provisional tiers**.

Do not start from round-number price bands. Derive provisional tiers from:
- observed market-price clusters after normalization;
- meaningful shifts in capability, quality, consistency, ownership burden, support, materials, specialization, craft, or prestige;
- market/design segment transitions;
- user budget anchors.

Possible tier names such as Budget, Value, Upgrade, Premium, Specialty are descriptive only, not mandatory slots.

## 7) Tier validity test
A normal tier is valid only when all are true:
1. at least **2 credible products** occupy that general price/value region, unless it is a legitimate sparse specialty/artisan/collector tier;
2. the region has a coherent buyer/value proposition;
3. the extra spend over the tier below buys at least one concrete material difference for a plausible buyer;
4. the boundary is not merely an aesthetically convenient round number;
5. the distinction remains coherent under the normalized price posture from `pricing.md` rather than depending entirely on one temporary promotion.

For each adjacent pair be able to state:
- approximate additional spend;
- concrete gain(s);
- mechanism/design/ownership reason for those gains where knowable;
- what does **not** materially improve;
- which buyer should stop at the lower tier vs move up.

If that explanation is weak or cosmetic, merge the tiers.

## 8) Refinement pass and stop condition
After provisional tiers are created, run one refinement/challenge pass aimed at:
- products near boundaries;
- omitted value/specialty segments;
- recurring-sale/clearance prices that distort placement;
- evidence that the apparent capability jump is not real;
- products whose design philosophy makes them poor representatives of a purely price-based tier.

Tier discovery may stop when:
- 3-5 valid tiers exist or the market justifies fewer;
- meaningful market/design segments are represented;
- every tier passes the validity test;
- the refinement pass yields no new segment or boundary-changing product likely to alter the tier map.

If fewer than 2 meaningful price/value clusters remain after refinement, collapse to 1-2 market regions and state that the category does not support useful tiering.

## 9) Representative candidates
Within each valid tier:
- apply hard user constraints before evaluation;
- normally choose **1 primary representative** plus **0-1 alternative** when the alternative represents a genuinely different design/tradeoff;
- evaluate recommendation-changing product conclusions using the active `criteria.md`, hierarchy-specialized authorities, `research_sources.md`, `reviews.md` when applicable, and `pricing.md`;
- do not choose multiple near-identical products merely to populate a tier.

Do not implicitly load or execute `product_research.md` merely to evaluate tier representatives.

A tier may have one representative in a narrow/sparse market.

Representative products should explain the tier, not merely happen to be priced within it.

## 10) User budgets
When user supplies a ceiling/target within a tier-analysis request:
- include credible options at/below it when available;
- explain if budget is below the reasonable market floor;
- distinguish best under $X from best value overall;
- include a stretch option only when the user appears flexible and the extra spend buys a concrete material gain.

Do not recommend a materially bad product just to satisfy a low tier.

## 11) Marginal-spend analysis
Apply the marginal-value reasoning in `pricing.md` to each adjacent tier.

For the tier workflow, turn that analysis into a concrete decision boundary:

`additional spend -> design/execution difference -> observed behavior/ownership effect -> buyer who benefits`

State what materially improves, what does not, and which buyer should move up. Do not redefine the reusable value categories or diminishing-returns concept here.

## 12) Diminishing returns
Identify the diminishing-return region using the definition and value logic in `pricing.md`, then explain how it manifests in this specific market.

## 13) Current offers and buying context
For representative picks:
- apply `pricing.md` for price-state interpretation and normal-price baseline;
- verify current price/availability;
- when buying guidance is included, apply the offer-comparison procedure and offer states from `seller_instructions.md`;
- apply `seller_instructions.md` to concrete offers.

When a temporary sale changes practical value, describe that effect without silently redefining the product's normal tier.

## 14) Cross-tier coherence
Before finalizing:
- no repeated product across tiers unless explicitly labeled bridge/sale-dependent/stretch;
- every adjacent tier passes the gain test;
- every pick fits its tier under the normalized price posture;
- meaningful design segments are not hidden by pure price labels;
- tiers with only arbitrary boundaries are removed.

## 15) Output
Use `pricing_tier_template.md`.

## Boundary
Reusable pricing/value definitions belong to `pricing.md`; research modes/evidence to `research_sources.md`; product evaluation to active criteria/hierarchy authorities; seller risk/offer comparison to `seller_instructions.md`; presentation to `pricing_tier_template.md`. This workflow owns tier construction, refinement, representative selection, and cross-tier synthesis only.