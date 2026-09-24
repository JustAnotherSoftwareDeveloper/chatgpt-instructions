# Product Research Workflow

## Purpose
Own open-ended product research, comparison, shortlist construction, and purchase recommendation behavior.

Use the product context already resolved by `instructions.md`: Base plus any active Class, Category, Type, shared-authority sections, and specialized files.

This workflow does not own product classification, evidence standards, review interpretation, seller policy, reusable pricing logic, or output formatting.

## 1) Scope the decision
Capture or infer only what materially changes the candidate set or recommendation:
- intended use;
- hard compatibility/size/platform/material constraints;
- budget ceiling, target, or price posture if relevant;
- region/condition if non-default;
- preferences that should meaningfully break ties;
- whether current price/availability/where-to-buy is in scope.

Ask only when one missing fact blocks useful research. Otherwise proceed with a stated assumption when consequential.

## 2) Respect fixed comparison sets
If the user names a fixed set of products:
- evaluate that set;
- do not silently replace it with a broader market search;
- add an outside comparable only when the user asks or when one nearby alternative materially clarifies the decision, and label it as a comparable rather than pretending it was part of the original set.

If the user asks an open-ended "what should I buy" question, perform market discovery before choosing finalists.

## 3) Discovery pass
Use the active sections of `source_playbooks.md` to identify the meaningful market alternatives and segments.

Discovery should be broad enough to avoid premature narrowing, but not padded with weak products for quota compliance.

For a mature open market, normally seek:
- multiple credible brands/makers or product families;
- the major market segments or design philosophies relevant to the user;
- obvious disqualifiers and category traps;
- enough candidates to understand where the real tradeoffs are.

If the market or constraints are narrow, use the available credible set and state that limitation only when it matters.

Discovery-only sources may shape the pool but cannot support recommendation-changing claims unless they independently qualify under `research_sources.md`.

## 4) Apply hard gates before deep research
Remove or deprioritize candidates that fail material hard requirements such as:
- compatibility;
- physical fit;
- budget ceiling when strict;
- availability/region constraints;
- required features;
- unacceptable maintenance/safety/channel constraints explicitly stated by the user.

Do not waste deep evidence collection on candidates already disqualified by hard constraints.

## 5) Lock product identity
Before using variant-sensitive evidence, establish exact model/variant/generation/size/region/condition as needed.

If identity cannot be locked:
- constrain claims to variant-invariant facts;
- state the uncertainty when decision-relevant;
- avoid mixing materially different variants into one evidence profile.

## 6) Build the evaluation model
Use active sections of `criteria.md`, `pricing.md`, and specialized hierarchy files.

Prioritize criteria based on the user's actual use case. Do not create an arbitrary weighted score unless the user explicitly wants scoring and the weights can be defended.

Identify internally:
- hard gates;
- primary differentiators;
- preference-sensitive dimensions;
- ownership/risk dimensions;
- price/value dimensions.

## 7) Plan and gather evidence
Apply `research_sources.md` to the material claim types.

Use research depth proportional to:
- purchase consequence/cost;
- ownership horizon;
- safety/compatibility risk;
- uncertainty and disagreement;
- counterfeit/provenance risk;
- user request for depth.

When review/community evidence contributes, apply `reviews.md`.

When seller/current-offer evidence contributes, apply `seller_instructions.md`.

Do not collect sources merely to hit a numeric quota. Gather enough independent, claim-appropriate evidence to support the decision.

## 8) Narrow to serious finalists
After discovery and hard gates, focus deep comparison on a manageable set of credible finalists.

For a broad mature market, a few serious finalists are usually enough to expose the meaningful tradeoffs. Use more only when the market structure or user's request genuinely requires it.

Do not keep nominal finalists that are clearly dominated or unsuitable merely to make the comparison look broad.

## 9) Normalize each finalist
For each serious finalist, understand as applicable:
- exact identity and configuration;
- hard-constraint fit;
- functional strengths;
- meaningful weaknesses/failure modes;
- reliability/QC confidence;
- usability/maintenance fit;
- product-domain criteria from active hierarchy authorities;
- ownership-cost/value posture;
- current price/availability and channel quality when in scope;
- what kind of user it best fits;
- what kind of user should avoid it.

Keep key claim-to-evidence relationships internally per `research_sources.md`.

## 10) Resolve disagreement rather than hiding it
When credible evidence conflicts:
- check variant/revision/test-condition differences;
- compare methods and source competence;
- seek additional independent evidence if the disagreement can change the recommendation;
- narrow the claim or lower confidence if unresolved.

Do not manufacture a consensus.

## 11) Synthesize the recommendation
Lead with the decision, not the research process.

Default for an open-ended market request:
- one primary recommendation when evidence supports a clear fit;
- a small set of alternatives that represent genuinely different tradeoffs or user profiles.

Do not force a winner when the choice is preference-dependent; explain the decision boundary instead.

For each recommended/alternative product, communicate:
- why it fits;
- the most important drawback;
- who should choose it;
- relevant price/value or seller caveats;
- confidence/uncertainty when material.

## 12) Current pricing and sellers
If the user asks for a budget, current price, availability, deal quality, or where to buy:
- verify current pricing;
- normalize offers enough for fair comparison;
- route seller/channel evaluation through `seller_instructions.md`;
- distinguish normal product value from a temporary sale/deal.

If pricing is not material to the request, do not turn the workflow into a seller hunt.

## 13) Output
Use `product_research_template.md`.

Keep internal research compliance, source ledgers, excluded-source lists, and detailed claim maps out of the normal answer unless the user requests the research basis or invokes `audit.md`.

## Pre-output quality gate
Confirm:
- the market was searched broadly enough for the request;
- hard constraints were applied before soft comparisons;
- finalists are exact enough for the claims made;
- major recommendation-changing claims have appropriate evidence;
- product vs seller quality is separated;
- pricing is current enough when it changes the decision;
- the recommendation reflects user priorities rather than generic category prestige.

## Boundary
Product context comes from `product_hierarchy.md`; evidence standards from `research_sources.md`; review interpretation from `reviews.md`; seller/channel risk from `seller_instructions.md`; reusable value logic from `pricing.md`; presentation from `product_research_template.md`.
