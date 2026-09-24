# Vendor Research Workflow

## Purpose
Own the generic workflow for research about brands, manufacturers, retailers, dealers/distributors, shopping sites, or vendor ecosystems rather than a specific product shortlist.

Use the resolved product context and shared evidence/specialized authorities.

## Hierarchy contribution surfaces
Active hierarchy authorities may Merge into or Override only named Vendor Research concerns using `product_hierarchy.md` semantics.

Stable concerns:
- **Vendor subtype** - §2.
- **Scope and vendor decision model** - §§3-4.
- **Discovery geometry** - §§5, 7.
- **Ecosystem segmentation** - §6.
- **Eligibility** - §8.
- **Finalist selection** - §9.
- **Vendor normalization** - §§10-12.
- **Subtype evidence additions** - §13.
- **Coverage / comparability** - §14.
- **Causal vendor analysis** - §15.
- **Synthesis / decision boundary** - §17.

Hierarchy contributions may add domain-specific vendor dimensions or replace workflow-owned ecosystem models, but may not redefine seller/offer states in `seller_instructions.md`, evidence standards in `research_sources.md`, or reusable criterion/value definitions.

## 1) Research mode
Apply the research mode selected by `research_sources.md`. Do not redefine Quick / Standard / Deep / Sparse triggers here.

## 2) Resolve vendor subtype
Classify the target as one or more of:
- brand/manufacturer;
- retailer/store/site;
- authorized dealer/distributor/service network;
- mixed ecosystem.

Do not collapse brand quality and retailer quality into one judgment.

## 3) Scope the user's goal
Capture or infer:
- product category/domain;
- region;
- value/budget posture;
- whether product quality, shopping channel, support/service, enthusiast reputation, aesthetics/identity, or all are in scope;
- hard channel constraints such as domestic service, authorized-only, direct-only, brick-and-mortar, marketplace avoidance.

## 4) Build an internal vendor research brief
Before deep evidence collection define:
- which vendor subtype(s) are being compared;
- what decision the user is actually making;
- hard eligibility gates;
- **3-5 primary vendor differentiators**;
- what evidence would establish each differentiator;
- known unknowns capable of changing the shortlist.

Do not let generic brand reputation substitute for subtype-specific evidence.

## 5) Discovery geometry
For a broad mature vendor ecosystem, default discovery target:
- **6-10 plausible vendor/brand entities**;
- at least **3 meaningful ecosystem/market segments** when they exist.

Use fewer when the ecosystem is genuinely narrow or the user restricts the set. Search wider when new segments keep appearing or the selected research mode calls for greater depth.

Discovery-only sources may enumerate entities but cannot establish quality/reputation by themselves.

## 6) Build an ecosystem map
For each meaningful vendor/brand family capture internally:
- entity type and business model;
- target customer/use case;
- category specialization/depth;
- price/value posture;
- distribution/service model;
- structural strength;
- structural weakness;
- representative lines/services;
- why the segment matters to the user's decision.

Do not use labels like "premium" or "specialist" without explaining what operationally differs.

## 7) Discovery challenge pass and stop condition
After the initial ecosystem map, run one challenge pass targeting:
- omitted niche/value/premium specialists;
- category-native vendors missed by generic search;
- credible criticism of likely finalists;
- channel/service structures that materially alter the comparison.

Discovery may stop when:
- the effective breadth target is met or a justified escape clause applies;
- major ecosystem segments under the active domain model are represented;
- the challenge pass yields no new finalist-worthy entity or material ecosystem segment.

## 8) Eligibility gates
Apply before deep comparison:
1. category relevance;
2. realistic regional availability/access;
3. business identity/legitimacy when channel trust is central;
4. lineup relevance to the user's use/value posture;
5. hard service/warranty/channel requirements;
6. obvious unresolved scam/relabel/provenance problems.

Use `seller_instructions.md` for retailer/dealer/channel states.

## 9) Finalist target
Deeply evaluate **3-5 vendor/brand finalists** in a broad mature ecosystem.

Use fewer when hard constraints or market sparsity justify it. Use more only when distinct vendor families genuinely survive and the user asks for broader mapping.

## 10) Brand / manufacturer normalization record
For each manufacturer/brand finalist, establish where material:
- actual entity relationship: manufacturer, OEM/ODM customer, private-label/rebrand, artisan maker, licensing brand, or mixed;
- category specialization and how central the domain is to the company/maker;
- product-line architecture and target segments;
- design/manufacturing control where evidence exists;
- revision cadence;
- QC / consistency;
- support/service/parts model;
- distribution model;
- domestic/regional practicality;
- continuity in the category;
- best-fit buyer and reason to choose another brand.

Do not infer all SKUs from the flagship product or overall brand reputation.

## 11) Retailer / store / site normalization record
For each retailer finalist, establish where material:
- business identity and category specialization;
- authorized relationships/provenance posture;
- product-data accuracy and variant clarity;
- inventory sourcing/condition clarity;
- curation quality rather than raw catalog size;
- pre-sale expertise/advice quality when it is a value proposition;
- value-added services where relevant;
- returns/restocking/return-shipping posture;
- warranty facilitation/RMA behavior;
- fulfillment/order accuracy signal;
- regional practicality;
- exact seller/channel state under `seller_instructions.md` when recommending where to buy.

A specialist retailer can be superior to a large general retailer when category expertise, provenance, service, or curation materially benefits the buyer. Do not assume scale equals trust or expertise.

## 12) Dealer / distributor / service-network record
Where relevant establish:
- authorization and brand relationships;
- territory/coverage;
- parts/service access;
- technician/service competence where evidence exists;
- warranty handling;
- inventory/access to exact products;
- business continuity/reputation;
- user friction for service/returns.

Apply any active hierarchy Merge additions to the relevant normalization record rather than replacing generic fields unless an explicit Override says a particular generic field/model is wrong for the domain.

## 13) Evidence requirements by subtype
Apply `research_sources.md` for all general evidence sufficiency, independence, research-mode, and stopping rules.

Add only these vendor-specific requirements where material:

### Brand/manufacturer
Establish primary lineup/support/warranty facts and enough independent domain/owner evidence to support claims about category competence, QC, service, or reputation.

### Retailer/store/site
Establish business identity/category expertise, exact-product accuracy, returns/warranty/service posture, and seller/channel state under `seller_instructions.md`.

### Dealer/distributor/service network
Establish authorization/product access, service/coverage, warranty handling, parts/service availability, regional practicality, and continuity/reputation.

### Mixed ecosystem
Evaluate manufacturer/brand quality and buying-channel quality separately, then explain the interaction.

## 14) Coverage and comparability
For each vendor finalist maintain internal coverage on the effective primary vendor differentiators using `research_sources.md`.

Do not call one vendor better simply because more information exists about it.

When comparing service/QC/reputation claims, check that evidence refers to comparable product families, regions, and time periods.

## 15) Causal vendor analysis
For recommendation-changing differences, explain the operational chain where supportable:

`business/design/distribution model -> observable behavior/service/lineup consequence -> user benefit/tradeoff`

Distinguish documented business structure from inferred consequences.

## 16) Evidence completion
Apply the evidence coverage, comparability, challenge-pass, and stop-condition contracts in `research_sources.md`.

Use `reviews.md` for review/community reputation claims and `seller_instructions.md` for concrete channel/offer judgments.

## 17) Synthesis defaults
Lead with the effective ecosystem map and the most useful shortlist.

Default output:
- **1 primary vendor/brand recommendation** when a clear fit exists;
- **2-3 alternatives** representing different strengths/buyer profiles;
- no forced winner when specialization means different vendors are legitimately best for different buyers.

For the primary recommendation, state the nearest-rival boundary: why it wins for this user and what would make the closest rival preferable.

State material coverage limitations when reputation is sparse or highly anecdotal.

## 18) Output
Use `vendor_research_template.md`.

## Pre-output quality gate
Confirm:
- active Vendor Research hierarchy Merges/Overrides were applied to their named concerns;
- ecosystem segmentation reflects the active domain model;
- normalization records include all material domain-specific additions;
- no hierarchy contribution redefined seller states or general evidence rules;
- manufacturer/brand quality and purchase-channel quality remain distinct.

## Boundary
Research modes/general evidence belong to `research_sources.md`; offer-level seller risk to `seller_instructions.md`; classification and Merge/Override semantics to `product_hierarchy.md`; presentation to `vendor_research_template.md`. This file owns the generic Vendor Research workflow and its named contribution surfaces.
