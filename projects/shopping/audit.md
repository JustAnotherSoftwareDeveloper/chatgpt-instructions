# Shopping Audit Workflow

## Purpose
Own QA of Shopping outputs. Repository-architecture checks are included only when the user is explicitly auditing or editing this project.

Audit diagnoses whether the prior output followed the active Shopping contracts. It does not automatically rerun the entire shopping workflow unless the user asks for a corrected result.

## 1) Shopping-output audit
Check all applicable areas.

### Routing
- Was the correct workflow used for the user's request?
- Did a one-product question incorrectly become full research, or vice versa?
- Did a vendor or pricing-tier request route correctly?

### Product context
- Was Base applied?
- Was the Class/Category/Type resolution justified by the request/product identity?
- Was the context too generic, over-specific, or carried incorrectly from a prior turn?
- Were the required specialized hierarchy files and shared sections applied?

### User constraints
- Were hard requirements distinguished from preferences?
- Were budget, compatibility, region, condition, use case, and accepted/rejected candidates preserved?
- Did the answer silently override an explicit user decision?

### Product identity / variant lock
- Were model, generation, size, region, configuration, and condition clear enough for the claims made?
- Did the output mix evidence from materially different variants?

### Discovery adequacy
For open-ended research:
- Was the market searched broadly enough to expose meaningful alternatives and segments?
- Was narrowing premature?
- Were weak candidates padded into the pool, or important classes of alternatives missed?

Do not judge adequacy by a fixed candidate count; judge whether the discovery was sufficient for the decision.

### Evidence adequacy
Apply `research_sources.md`:
- Did each material claim use an appropriate source type?
- Was there enough independent corroboration for purchase-changing claims?
- Was one narrative ecosystem or non-primary source over-relied upon?
- Were discovery-only sources improperly used as evidence?
- Were high-risk/high-consequence claims researched deeply enough?
- Were coverage limitations disclosed when evidence was sparse?

### Review/community handling
Apply `reviews.md`:
- Were anecdotes converted into unsupported prevalence claims?
- Were product issues separated from seller/channel contamination?
- Were version, time horizon, incentives, domain competence, and manipulation signals handled appropriately?
- Were preference-sensitive observations presented as preferences rather than universal defects?

### Seller / offer handling
When concrete offers were part of the answer, apply `seller_instructions.md`:
- Were seller of record, fulfillment, condition, exact variant, returns, warranty, provenance, and meaningful channel risks handled sufficiently?
- Was the cheapest offer treated as best without adequate risk comparison?
- Was product quality kept separate from seller quality?

### Pricing freshness and value logic
- Were current prices current enough for the recommendation?
- Were MSRP, normal street price, sale price, and anomalies distinguished where material?
- Did tier/value conclusions explain what extra spend buys rather than merely sort by price?

### Synthesis
- Does the recommendation actually follow from the evidence and active criteria?
- Are major tradeoffs visible?
- Is confidence proportionate to evidence quality?
- Was a forced winner declared where the decision is genuinely preference-dependent?

### Output contract
- Does the answer follow the active template at an appropriate level of detail?
- Did internal research/compliance scaffolding leak into a normal shopping response without being requested?

## 2) Audit severity
Classify findings by consequence rather than stylistic preference.

### Critical
The output could materially mislead the purchase decision because of wrong product identity, safety/legal failure, incompatible product, fabricated/currently false evidence, or a major unsupported conclusion.

### Major
A substantial research/routing/evidence gap could change the recommendation: premature narrowing, wrong workflow, major source dependence, missing seller risk, stale current-market facts, or omitted hard constraint.

### Minor
The answer is broadly sound but has a limited clarity, coverage, caveat, citation, or formatting defect unlikely to change the recommendation.

### Note
An improvement or observation that is not a defect.

## 3) Audit output
Default to a compact report:

1. Overall status: Pass / Pass with issues / Rework needed.
2. Findings grouped by Critical, Major, Minor, Notes; omit empty groups.
3. For each issue: what happened, why it matters, owning authority/workflow, and concrete fix.
4. Material uncertainties or missing evidence.
5. If requested, a corrected execution plan or corrected answer.

Do not reproduce internal file mechanics unless the user is explicitly auditing this project architecture.

## 4) Repository-maintenance audit
Only when explicitly auditing/editing the Shopping project, also check:
- `MAIN.md` remains pointer-only;
- `instructions.md` canonical map is complete and orchestrator remains thin;
- workflow routing is deterministic and first-match;
- every authority has one clear responsibility and appears in precedence;
- templates contain presentation contracts, not workflow logic;
- hierarchy parent/child boundaries are behavior-driven, not taxonomic decoration;
- specialized files are loaded only by active hierarchy entries;
- sibling authorities do not duplicate rules;
- references point to live files/sections;
- `archive/` is not treated as live ChatGPT Project context;
- legacy migration has not silently reintroduced obsolete pseudo-runtime or quota rules.

## Boundary
This file diagnoses compliance with the other authorities. It should reference their rules rather than restating their full logic. Architecture validation is not a normal per-shopping-request step.
