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

## 3) Research-brief / decision-model audit
For Standard/Deep Product or Vendor Research, check whether the execution had a coherent internal decision model:
- concrete purchase/vendor decision;
- user model and consequential assumptions;
- market scope;
- hard gates;
- normally 3-5 primary differentiators;
- evidence question for each primary differentiator;
- known unknowns capable of changing the recommendation.

Major issue when research appears source-led rather than decision-led: e.g. the answer evaluates whatever reviewers happened to discuss instead of the criteria the user's decision requires.

## 4) Discovery-contract audit
### Product Research
For an open mature market, check whether default discovery was achieved or a valid escape clause existed:
- 8-12 plausible candidates;
- >=4 makers/brands where supported;
- >=3 material market/design/value segments where they exist;
- challenge pass performed;
- normally 3-5 finalists after hard gates.

Also check:
- meaningful segments were **modeled**, not merely named;
- plausible candidates received minimum extraction before narrowing or had a clear hard-gate rejection;
- discovery was not dominated by one SEO/editorial/retailer ecosystem;
- finalist set represents relevant tradeoff/design families rather than near-duplicates.

### Pricing Tiers
Check:
- 10-15 credible current-product market scan where supported;
- >=4 makers where supported;
- market/design/value segments modeled before tiering;
- provisional 3-5 tier geometry;
- every tier passed the validity test;
- refinement/challenge pass performed;
- adjacent-tier gain test is concrete rather than round-number segmentation;
- normal/current street-price posture, not MSRP or one flash sale, anchors tier placement.

### Vendor Research
Check:
- 6-10 plausible vendor/brand entities where supported;
- >=3 meaningful ecosystem segments where they exist;
- ecosystem/business-model map built;
- challenge pass performed;
- normally 3-5 deep finalists.

### Quick Check
Check:
- scope stayed narrow;
- <=4 recommendation-changing questions;
- no more than 2 outside product comparables before escalation;
- broader-market research was not silently performed under Quick Check.

## 5) Hard-gate and criteria audit
Check:
- hard constraints applied before preference/value ranking;
- Product Research normally identified 3-5 primary differentiators;
- secondary criteria did not overwhelm the decision;
- explicit aesthetic/identity/craft priorities were not silently subordinated;
- dominated or already-disqualified candidates were not retained merely to fill slots.

## 6) Product identity / variant lock
Check:
- model, generation, size, region, configuration, and condition were clear enough for claims;
- evidence from materially different variants was not mixed;
- unresolved identity uncertainty was bounded.

## 7) Minimum-vs-full extraction audit
For open Product Research check:
- discovery candidates had enough minimum extraction to avoid fame/source-volume bias;
- finalists received full extraction appropriate to the active domain authority;
- one candidate was not rejected merely because fewer reviews/spec summaries were easy to find;
- important evidence gaps were distinguished from actual product weaknesses.

## 8) Evidence-packet audit
Apply `research_sources.md` by claim type.

Check material claims for:
- primary/official evidence for objective facts when available;
- independent empirical/specialist/practitioner support for recommendation-changing performance/quality claims;
- owner/community/long-term evidence when reliability, QC, maintenance, or real-world usability changes the decision;
- current seller evidence when price/availability/channel is material;
- independence rather than multiple artifacts from one narrative ecosystem.

For Standard/Deep work, check that the challenge pass deliberately sought contradiction, omissions, failure modes, or missing source families.

## 9) Candidate x criterion coverage audit
For finalist comparisons, inspect the internal logic as a matrix of finalist vs primary differentiator/hard gate.

Flag when:
- a winner has Strong evidence while a rival is merely Unknown and the answer treats Unknown as worse;
- a primary differentiator is Weak/Unknown for a finalist and could plausibly flip the recommendation;
- evidence coverage is badly asymmetric without investigation;
- the answer has many sources globally but insufficient evidence on the actual comparison cells that drive the recommendation.

Do not require equal source counts when one competent side-by-side source covers multiple finalists.

## 10) Comparability audit
For recommendation-changing cross-product comparisons check:
- same/equivalent product variant and role;
- methodology/test conditions;
- units/definitions;
- time horizon;
- evidence comparability classified sensibly as Direct / Directional / Not directly comparable.

Major issue when:
- small numeric differences from incompatible methods are used to rank products;
- measurements from different protocols are combined into a pseudo-score;
- one product is tested under easier/different conditions and treated as directly superior.

When evidence is only directional, conclusion language and confidence should also be directional.

## 11) Analytical-depth / causal reasoning audit
For each primary recommendation difference ask:
- What observed feature/behavior actually separates the finalists?
- Is there a supported mechanism/design/ownership explanation?
- What tradeoff accompanies the advantage?
- How does that tradeoff map to this user's use case?
- Is inferred mechanism clearly distinguished from observed evidence?

Strong synthesis often follows:

`feature/design -> mechanism -> behavior -> tradeoff -> user consequence -> recommendation effect`

Flag shallow analysis that merely repeats adjectives such as "premium," "better build," "faster," "more durable," or "better value" without explaining the decision-relevant consequence.

Do not require causal claims where evidence cannot support them; uncertainty is better than invented mechanism.

## 12) Market-model audit
Check whether the answer understands *why* market segments exist.

For each relevant segment, expect enough understanding of:
- target buyer/use case;
- defining technical/commercial traits;
- benefits;
- structural compromises;
- price posture;
- representative products/vendors;
- relevance to this user.

Flag a segment map that is merely Budget/Midrange/Premium labels with no different design/value proposition.

## 13) Research stop-condition audit
Research is complete only if:
- normal coverage packet was met or exception documented;
- material recommendation-changing claims had appropriate evidence;
- finalist x primary-criterion coverage was Adequate/Strong or unresolved gaps were bounded;
- identity was locked/bounded;
- material conflicts were resolved/bounded;
- challenge pass produced no new information likely to change eligibility, finalists, recommendation, tier placement, seller judgment, or material caveat.

Flag both under-research and pointless source accumulation.

## 14) Review/community audit
Apply `reviews.md`.

Check:
- isolated anecdotes were not called recurring;
- `Recurring signal` met >=3 independent first-hand reports plus the cross-platform/artifact/reproduction condition;
- `Strong/widespread` language met the >=10 distributed reports, independent reproduction, or official-acknowledgement condition;
- no prevalence percentage was inferred without representative denominator data;
- multiple posts were not all reactions/reposts of one original story;
- pattern record considered model/revision, severity, ownership horizon, operating conditions, channel contamination, and current/fixed status when material;
- preference-sensitive observations were not universalized.

## 15) Seller / offer audit
When concrete offers were included, apply `seller_instructions.md`.

Check each recommended offer has a defensible state:
- Exclude / High Risk / Acceptable / Preferred.

Check:
- seller of record and fulfillment;
- exact variant/condition;
- normalized total and price-state context;
- return/warranty/provenance posture;
- provenance/authorized claims verified through the strongest available evidence rather than seller self-description alone when material;
- stock/delivery confidence;
- price-anomaly trigger when >=20% below normal reputable range;
- at least 2 Acceptable offers compared when buying guidance was given and the market supported them.

Ensure cheapest != automatically best and product quality != seller quality.

## 16) Pricing / price-baseline audit
Check:
- MSRP is not treated as normal street price without evidence;
- normal street/current typical/current low/recurring sale/clearance/anomaly are distinguished when material;
- a flash sale does not silently redefine long-term tier placement;
- deal quality is judged against an appropriate baseline;
- price differences are normalized for variant, condition, bundle, fees, warranty/provenance, and material seller differences.

## 17) Pricing-tier audit
Check:
- tier exists because of real market/value proposition, not round number;
- ordinary tier normally has >=2 credible products unless legitimate specialty sparsity applies;
- each adjacent tier states additional spend, concrete gain, mechanism/ownership reason where supportable, what does not materially improve, and who should move up;
- diminishing-return region is tied to primary functional/ownership criteria rather than vague luxury language;
- current prices are fresh enough.

## 18) Vendor-depth audit
For manufacturer/brand research check whether material questions were addressed:
- actual manufacturer/OEM/private-label/artisan relationship;
- product-line architecture and category specialization;
- revision cadence/QC consistency;
- support/service/parts model;
- distribution/provenance model;
- regional practicality and category continuity.

For retailer research check:
- authorized/provenance relationships;
- category curation/data accuracy;
- value-added services where relevant;
- returns/warranty facilitation;
- fulfillment/order-quality signal.

Flag pure reputation-list answers that do not explain operational differences.

## 19) Chef's Knife pilot audit
When Chef's Knife is active, check:
- default consumer model used only when user context did not override it;
- relevant market/design families considered rather than a pool of near-identical knives;
- technique/maintenance/abuse/artisan triggers changed criterion priority appropriately;
- Standard/Deep finalists used the Chef's Knife finalist record where evidence existed;
- cutting claims include representative task/food context rather than one stunt test;
- geometry/profile/edge/QC/maintenance/fit/value were normalized deeply enough to compare finalists;
- steel name/prestige did not substitute for geometry/heat treatment/edge/fit evidence;
- causal knife reasoning separates observed behavior from inferred mechanism;
- role-fit redirection occurred only when another knife format materially better matched the use case.

## 20) Nearest-rival / robustness audit
For substantial Standard/Deep recommendations check:
- #1 was compared explicitly against the closest credible rival;
- the decision identifies the primary differentiator that actually separates them;
- the answer states what user preference/assumption would flip the choice;
- the recommendation was stress-tested against its most fragile assumption/evidence gap.

Flag a recommendation that is presented as robust while resting on one weak or non-comparable claim.

## 21) Output-contract audit
Check active template:
- required sections present;
- comparison table used when required;
- market map included for substantial open-market research when useful;
- nearest-rival boundary included for substantial Standard/Deep research;
- normal recommendation/alternative counts followed or valid exception existed;
- material uncertainties disclosed;
- internal hierarchy/research-mode/source-count/coverage mechanics did not leak unless requested/audited.

## 22) Severity
### Critical
Could materially mislead purchase because of wrong identity, incompatibility/safety failure, fabricated/currently false evidence, or major unsupported conclusion.

### Major
Gap could change recommendation: wrong workflow, premature narrowing, missing hard constraint, failed evidence/coverage/comparability/stop condition, shallow causal synthesis, omitted market family, seller risk, stale/mis-modeled market price.

### Minor
Broadly sound with limited clarity, coverage, caveat, citation, or formatting defect unlikely to change recommendation.

### Note
Improvement that is not a defect.

## 23) Audit output
Default:
1. Overall status: Pass / Pass with issues / Rework needed.
2. Findings grouped by Critical / Major / Minor / Notes; omit empty groups.
3. For each issue: what happened, why it matters, owning file, concrete fix.
4. Material missing evidence/uncertainty.
5. Corrected plan/answer only when requested.

## 24) Repository-maintenance audit
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
- numeric defaults have triggers/stop conditions/escape clauses rather than becoming blind quotas;
- internal depth structures are instruction artifacts, not user-visible bureaucracy.

## Boundary
Audit diagnoses compliance with other authorities and references their contracts rather than duplicating full implementations.