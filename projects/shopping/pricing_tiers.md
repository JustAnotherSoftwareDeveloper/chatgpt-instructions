# Pricing Tiers Workflow

## Purpose
Own the generic meaningful price-band, budget-tier, good-better-best, and "what does spending more buy?" workflow within a product market.

Use the resolved product context plus active `pricing.md`, `criteria.md`, `source_playbooks.md`, and evidence authorities.

This workflow constructs live market tiers. It does not define research modes, reusable price states, seller risk, or timeless dollar bands.

## Hierarchy contribution surfaces
Active hierarchy authorities may Merge into or Override only named Pricing Tiers concerns using `product_hierarchy.md` semantics.

Stable concerns:
- **Market scope** - §2.
- **Market scan / discovery geometry** - §3.
- **Market segmentation** - §4.
- **Price normalization** - §5.
- **Tier construction** - §6.
- **Tier validity** - §7.
- **Refinement / stopping** - §8.
- **Representative selection** - §9.
- **Budget interpretation** - §10.
- **Marginal-spend analysis** - §11.
- **Diminishing-returns interpretation** - §12.
- **Buying context** - §13.
- **Cross-tier coherence** - §14.

Hierarchy contributions may specialize workflow-owned tier behavior but may not redefine reusable price-state/value definitions in `pricing.md`, seller-risk states in `seller_instructions.md`, or evidence standards in `research_sources.md`.

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

If an active hierarchy Override replaces the assumption that the market can be represented as one linear ladder, use the effective domain model instead while preserving the generic requirement to explain what additional spend buys.

## 7) Tier validity test
A normal tier is valid only when all are true:
1. at least **2 credible products** occupy that general price/value region, unless it is a legitimate sparse specialty/artisan/collector tier;
2. the region has a coherent buyer/value proposition;
3. the extra spend over the relevant lower-cost alternative buys at least one concrete material difference for a plausible buyer;
4. the boundary is not merely an aesthetically convenient round number;
5. the distinction remains coherent under the normalized price posture from `pricing.md` rather than depending entirely on one temporary promotion.

For each relevant adjacent or competing value region be able to state:
- approximate additional spend;
- concrete gain(s);
- mechanism/design/ownership reason for those gains where knowable;
- what does **not** materially improve;
- which buyer should stop at the lower-cost option vs move up.

If that explanation is weak or cosmetic, merge or otherwise simplify the effective tier structure unless a hierarchy override establishes a legitimate parallel value track.

## 8) Refinement pass and stop condition
After provisional tiers/regions are created, run one refinement/challenge pass aimed at:
- products near boundaries;
- omitted value/specialty segments;
- recurring-sale/clearance prices that distort placement;
- evidence that the apparent capability jump is not real;
- products whose design philosophy makes them poor representatives of a purely price-based tier.

Tier discovery may stop when:
- the effective tier/region structure is valid under the active hierarchy model;
- meaningful market/design segments are represented;
- every tier/region passes the effective validity test;
- the refinement pass yields no new segment or boundary-changing product likely to alter the map.

If fewer than 2 meaningful price/value regions remain after refinement, collapse to one market region and state that the category does not support useful tiering.

## 9) Representative candidates
Within each valid tier/region:
- apply hard user constraints before evaluation;
- normally choose **1 primary representative** plus **0-1 alternative** when the alternative represents a genuinely different design/tradeoff;
- evaluate recommendation-changing product conclusions using the active `criteria.md`, hierarchy-specialized authorities, `research_sources.md`, `reviews.md` when applicable, and `pricing.md`;
- do not choose multiple near-identical products merely to populate a tier.

Do not implicitly load or execute `product_research.md` merely to evaluate tier representatives.

A tier may have one representative in a narrow/sparse market.

Representative products should explain the tier/region, not merely happen to be priced within it.

## 10) User budgets
When user supplies a ceiling/target within a tier-analysis request:
- include credible options at/below it when available;
- explain if budget is below the reasonable market floor;
- distinguish best under $X from best value overall;
- include a stretch option only when the user appears flexible and the extra spend buys a concrete material gain.

Do not recommend a materially bad product just to satisfy a low tier.

## 11) Marginal-spend analysis
Apply the marginal-value reasoning in `pricing.md` to each relevant step up or competing higher-cost path.

For the tier workflow, turn that analysis into a concrete decision boundary:

`additional spend -> design/execution difference -> observed behavior/ownership effect -> buyer who benefits`

State what materially improves, what does not, and which buyer should spend more. Do not redefine the reusable value categories or diminishing-returns concept here.

## 12) Diminishing returns
Identify the diminishing-return region using the definition and value logic in `pricing.md`, then explain how it manifests in this specific market under any active hierarchy override.

A hierarchy contribution may specialize the **domain manifestation** of diminishing returns, but not redefine the shared meaning in `pricing.md`.

## 13) Current offers and buying context
For representative picks:
- apply `pricing.md` for price-state interpretation and normal-price baseline;
- verify current price/availability;
- when buying guidance is included, apply the offer-comparison procedure and offer states from `seller_instructions.md`;
- apply `seller_instructions.md` to concrete offers.

When a temporary sale changes practical value, describe that effect without silently redefining the product's normal tier/region.

## 14) Cross-tier coherence
Before finalizing:
- no repeated product across tiers/regions unless explicitly labeled bridge/sale-dependent/stretch;
- every meaningful step up passes the effective gain test;
- every pick fits its tier/region under the normalized price posture;
- meaningful design/value tracks are not hidden by pure price labels;
- arbitrary boundaries are removed;
- parallel tracks introduced by a hierarchy override remain explicitly distinct rather than being forced into false rank order.

## 15) Output
Use `pricing_tier_template.md`.

## Pre-output quality gate
Confirm:
- active Pricing Tiers hierarchy Merges/Overrides were applied to their named concerns;
- no hierarchy contribution redefined shared price-state, seller-risk, or evidence rules;
- market segmentation and tier construction follow the effective domain model;
- representative selection reflects active domain merges;
- marginal-spend and diminishing-return conclusions distinguish functional gains from preference/craft/prestige gains where the active hierarchy requires it;
- current prices are fresh enough for the result.

## Boundary
Reusable pricing/value definitions belong to `pricing.md`; research modes/evidence to `research_sources.md`; product evaluation to active criteria/hierarchy authorities; seller risk/offer comparison to `seller_instructions.md`; Merge/Override semantics to `product_hierarchy.md`; presentation to `pricing_tier_template.md`. This file owns the generic Pricing Tiers workflow and its named contribution surfaces.
