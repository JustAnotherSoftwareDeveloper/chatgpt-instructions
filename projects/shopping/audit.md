# Shopping Audit Workflow

## Purpose
Own QA of Shopping outputs. Repository-architecture checks apply only when explicitly auditing/editing this project.

Audit compares execution against the active Shopping contracts. It does not rerun the whole shopping task unless the user asks for correction.

## 1) Routing and context
Check:
- correct workflow selected;
- Base applied;
- Class/Category/Type resolution justified;
- required specialized files/shared sections loaded;
- narrow context not incorrectly carried to another product;
- hard user constraints and locked decisions preserved.

## 2) Research-mode audit
Identify which mode should have applied under `research_sources.md`: Quick / Standard / Deep / Sparse.

Check:
- was the selected depth appropriate to the task?
- if research fell below the normal evidence budget, was there a valid escape clause or genuine sparse-coverage reason?
- was Sparse used only because credible evidence was unavailable, not merely to save work?

Do not fail an answer merely because it used a different raw source count when claim coverage and stop conditions were satisfied.

## 3) Discovery-contract audit
### Product Research
For an open mature market, check whether default discovery was achieved or a valid escape clause existed:
- 8-12 plausible candidates;
- >=4 makers/brands where supported;
- >=3 material market/design/value segments where they exist;
- challenge pass performed;
- normally 3-5 finalists after hard gates.

### Pricing Tiers
Check:
- 10-15 credible current-product market scan where supported;
- >=4 makers where supported;
- provisional 3-5 tier geometry;
- every tier passed the validity test;
- refinement/challenge pass performed;
- adjacent-tier gain test is concrete rather than round-number segmentation.

### Vendor Research
Check:
- 6-10 plausible vendor/brand entities where supported;
- >=3 meaningful ecosystem segments where they exist;
- challenge pass performed;
- normally 3-5 deep finalists.

### Quick Check
Check:
- scope stayed narrow;
- <=4 recommendation-changing questions;
- no more than 2 outside product comparables before escalation;
- broader-market research was not silently performed under Quick Check.

## 4) Hard-gate and criteria audit
Check:
- hard constraints applied before preference/value ranking;
- Product Research normally identified 3-5 primary differentiators;
- secondary criteria did not overwhelm the decision;
- explicit aesthetic/identity/craft priorities were not silently subordinated;
- dominated or already-disqualified candidates were not retained merely to fill slots.

## 5) Product identity / variant lock
Check:
- model, generation, size, region, configuration, and condition were clear enough for claims;
- evidence from materially different variants was not mixed;
- unresolved identity uncertainty was bounded.

## 6) Evidence-packet audit
Apply `research_sources.md` by claim type.

Check material claims for:
- primary/official evidence for objective facts when available;
- independent empirical/specialist/practitioner support for recommendation-changing performance/quality claims;
- owner/community/long-term evidence when reliability, QC, maintenance, or real-world usability changes the decision;
- current seller evidence when price/availability/channel is material;
- independence rather than multiple artifacts from one narrative ecosystem.

For Standard/Deep work, check that the challenge pass deliberately sought contradiction, omissions, failure modes, or missing source families.

## 7) Research stop-condition audit
Research is complete only if:
- normal coverage packet was met or exception documented;
- material recommendation-changing claims had appropriate evidence;
- identity was locked/bounded;
- material conflicts were resolved/bounded;
- challenge pass produced no new information likely to change eligibility, finalists, recommendation, tier placement, seller judgment, or material caveat.

Flag both under-research and pointless source accumulation.

## 8) Review/community audit
Apply `reviews.md`.

Check:
- isolated anecdotes were not called recurring;
- `Recurring signal` met >=3 independent first-hand reports plus the cross-platform/artifact/reproduction condition;
- `Strong/widespread` language met the >=10 distributed reports, independent reproduction, or official-acknowledgement condition;
- no prevalence percentage was inferred without representative denominator data;
- version/time horizon/domain competence/incentives/manipulation were handled;
- product defects were separated from channel contamination;
- preference-sensitive observations were not universalized.

## 9) Seller / offer audit
When concrete offers were included, apply `seller_instructions.md`.

Check each recommended offer has a defensible state:
- Exclude / High Risk / Acceptable / Preferred.

Check:
- seller of record and fulfillment;
- exact variant/condition;
- normalized total;
- return/warranty/provenance posture;
- stock/delivery confidence;
- price-anomaly trigger when >=20% below normal reputable range;
- at least 2 Acceptable offers compared when buying guidance was given and the market supported them.

Ensure cheapest != automatically best and product quality != seller quality.

## 10) Pricing-tier audit
Check:
- tier exists because of real market/value proposition, not round number;
- ordinary tier normally has >=2 credible products unless legitimate specialty sparsity applies;
- each adjacent tier states additional spend, concrete gain, what does not materially improve, and who should move up;
- diminishing-return region is tied to primary functional/ownership criteria rather than vague luxury language;
- current prices are fresh enough.

## 11) Chef's Knife pilot audit
When Chef's Knife is active, check:
- default consumer model used only when user context did not override it;
- technique/maintenance/abuse/artisan triggers changed criterion priority appropriately;
- default primary criteria were not treated as immutable when explicit user needs differed;
- steel name/prestige did not substitute for geometry/heat treatment/edge/fit evidence;
- role-fit redirection occurred only when another knife format materially better matched the use case.

## 12) Output-contract audit
Check active template:
- required sections present;
- comparison table used when required;
- normal recommendation/alternative counts followed or valid exception existed;
- material uncertainties disclosed;
- internal hierarchy/research-mode/source-count mechanics did not leak unless requested/audited.

## 13) Severity
### Critical
Could materially mislead purchase because of wrong identity, incompatibility/safety failure, fabricated/currently false evidence, or major unsupported conclusion.

### Major
Gap could change recommendation: wrong workflow, premature narrowing, missing hard constraint, failed evidence packet/stop condition, major source dependence, seller risk, stale market facts.

### Minor
Broadly sound with limited clarity, coverage, caveat, citation, or formatting defect unlikely to change recommendation.

### Note
Improvement that is not a defect.

## 14) Audit output
Default:
1. Overall status: Pass / Pass with issues / Rework needed.
2. Findings grouped by Critical / Major / Minor / Notes; omit empty groups.
3. For each issue: what happened, why it matters, owning file, concrete fix.
4. Material missing evidence/uncertainty.
5. Corrected plan/answer only when requested.

## 15) Repository-maintenance audit
Only when explicitly auditing/editing this project, also check:
- `MAIN.md` pointer-only;
- `instructions.md` thin and canonical map complete;
- first-match routing deterministic;
- every authority has one responsibility and precedence position;
- templates own presentation, not workflow logic;
- hierarchy boundaries are behavior-driven;
- specialized files load only from active hierarchy entries;
- no sibling rule duplication;
- references point to live files/sections;
- `archive/` not treated as deployable ChatGPT Project context;
- no pseudo-runtime machinery reintroduced;
- numeric defaults have triggers/stop conditions/escape clauses rather than becoming blind quotas.

## Boundary
Audit diagnoses compliance with other authorities and references their contracts rather than duplicating full implementations.