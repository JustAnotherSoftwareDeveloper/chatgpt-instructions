# Product Research Workflow

## Purpose
Own open-ended product research, comparison, shortlist construction, and purchase recommendation behavior.

Use the product context already resolved by `instructions.md`: Base plus active Class/Category/Type sections and specialized files.

## 1) Scope the decision
Capture or infer only what changes the viable set or recommendation:
- intended use;
- hard compatibility/size/platform/material constraints;
- budget ceiling/target or price posture;
- region/condition if non-default;
- preferences that should break ties;
- whether current price/availability/where-to-buy is in scope.

Ask only when one missing fact blocks useful research. Otherwise proceed with a stated assumption when consequential.

## 2) Research mode
Default to **Standard** from `research_sources.md`.

Use **Quick** only for a narrow fixed comparison or tightly scoped factual check that still belongs here.

Escalate to **Deep** when `research_sources.md` triggers apply.

Use **Sparse** only because credible evidence is unavailable.

## 3) Fixed comparison sets
If the user names a fixed set:
- evaluate that set;
- do not run open-market discovery as if the user asked "what should I buy";
- add at most **1-2 outside comparables** only when they materially clarify value or expose a major tradeoff, and label them explicitly as comparables.

## 4) Open-market discovery
For a mature open market, default discovery target:
- **8-12 plausible products** before hard-gate narrowing;
- at least **4 makers/brands** when the market supports it;
- at least **3 materially different market/design/value segments** when such segmentation exists.

Discovery sources may enumerate candidates without qualifying as evidence.

Do not pad the pool with weak candidates solely to hit a number.

### Discovery escape clauses
Use fewer candidates when:
- hard constraints make the market genuinely narrow;
- the product market is genuinely sparse;
- the request concerns a constrained ecosystem or regional niche;
- user supplied a fixed set.

Search wider when:
- a new segment keeps appearing;
- the first pool is dominated by one retailer/editorial ecosystem;
- Deep research is active;
- the user asks for exhaustive coverage.

## 5) Discovery challenge pass and stop condition
After the initial pool is built, perform one challenge pass aimed at finding:
- an omitted market/design segment;
- a credible alternative to likely finalists;
- a product family favored by domain-native specialists but missed by generic discovery;
- a recurring disqualifier pattern.

Discovery may stop when:
1. the default breadth target is met or a justified escape clause applies;
2. known hard constraints have been applied conceptually;
3. the challenge pass yields no new candidate or segment likely to survive hard gates and change the finalist set.

## 6) Apply hard gates in order
Before deep research, remove/deprioritize candidates in this order:
1. wrong product identity/type/variant;
2. hard compatibility/use/fit constraints;
3. strict budget or region/availability constraint;
4. unacceptable safety/channel/maintenance requirement explicitly set by the user or active authority;
5. objectively dominated candidates when another candidate is at least as suitable on all material primary criteria and meaningfully better on one, with comparable availability/risk.

Only then rank remaining products on preferences and value.

## 7) Lock product identity
Before variant-sensitive evidence, establish exact model/variant/generation/size/region/condition as needed.

If identity cannot be locked:
- constrain claims to variant-invariant facts;
- state material uncertainty;
- do not mix materially different variants into one evidence profile.

## 8) Build the evaluation model
Use active `criteria.md`, `pricing.md`, and hierarchy authorities.

Classify active criteria internally as:
- hard gate;
- primary differentiator;
- secondary/tie-breaker;
- preference/identity dimension.

Normally select **3-5 primary differentiators**. Do not give every criterion equal importance.

Do not create arbitrary numeric scores unless the user explicitly asks and the weights can be defended.

## 9) Narrow to finalists
For broad mature markets, target **3-5 serious finalists** after hard gates.

Use up to **6** only when distinct tradeoff families genuinely survive.

Use fewer when:
- hard constraints narrow the market;
- only a few credible products exist;
- the user explicitly wants fewer;
- the fixed comparison set is smaller.

Do not retain dominated or unsuitable products merely to fill slots.

## 10) Evidence collection
Apply the selected `research_sources.md` mode.

For each material recommendation-changing claim, gather the appropriate evidence type.

Use `reviews.md` when review/community evidence contributes.
Use `seller_instructions.md` when concrete offer/channel evidence contributes.

Evidence collection may stop only when the `research_sources.md` stop condition is satisfied.

## 11) Normalize finalists
For each finalist establish as applicable:
- exact identity/configuration;
- hard-constraint fit;
- primary differentiator performance;
- meaningful weaknesses/failure modes;
- reliability/QC confidence;
- usability/maintenance fit;
- ownership-cost/value posture;
- current price/availability/channel when in scope;
- best-fit user;
- avoid/choose-another-user profile.

## 12) Resolve disagreements
When credible evidence conflicts:
- verify variant/revision/test-condition equivalence;
- compare methods and competence;
- seek additional independent evidence if the conflict can change the recommendation;
- narrow the claim or lower confidence if unresolved.

Do not manufacture consensus.

## 13) Synthesis defaults
For open-ended market research:
- give **1 primary recommendation** when evidence supports a clear fit;
- normally give **2-3 alternatives** representing genuinely different tradeoffs/user profiles;
- do not force a single winner when the choice is primarily preference-dependent; state the decision boundary instead.

For each included product state:
- why choose it;
- primary drawback/tradeoff;
- who it best fits;
- relevant value/seller caveat;
- material uncertainty if any.

## 14) Current pricing and sellers
If the user provides a budget or asks about current price, deal quality, availability, or where to buy:
- verify current pricing;
- normalize offers fairly;
- apply `seller_instructions.md`;
- distinguish normal product value from temporary deal quality.

If pricing is not material, do not turn research into a seller hunt.

## 15) Output
Use `product_research_template.md`.

Keep research ledgers, source-count mechanics, and internal classification out of normal output unless requested or audited.

## Pre-output quality gate
Confirm:
- correct research mode;
- discovery target met or justified escape clause;
- challenge pass completed for Standard/Deep open-market research;
- hard gates applied before preference ranking;
- 3-5 primary differentiators identified;
- finalist count follows defaults or has a reason not to;
- variant identity is sufficiently locked;
- material claims satisfy evidence packets and stop condition;
- product and seller judgments are separated;
- current facts are current enough;
- recommendation reflects user priorities, not generic prestige.

## Boundary
Product context comes from `product_hierarchy.md`; evidence from `research_sources.md`; review handling from `reviews.md`; seller risk from `seller_instructions.md`; value logic from `pricing.md`; presentation from `product_research_template.md`.