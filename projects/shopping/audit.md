# Shopping Audit Workflow

## Purpose
Own QA of Shopping outputs and, only when explicitly requested, repository-maintenance QA.

Audit evaluates compliance with the active canonical contracts. It does **not** own or restate those contracts.

## 1) Audit mode
### Self-audit / pre-output audit
Use when auditing work still being produced in the current execution.

The audit may inspect internal research artifacts that actually exist in the current execution, such as research briefs, candidate records, coverage matrices, challenge-pass results, and robustness checks.

### Retrospective audit
Use when auditing a prior answer or artifact.

Judge only what is observable from:
- the prior answer;
- its cited/available sources;
- locked conversation context;
- targeted verification performed during the audit.

Do **not** claim that an unexposed internal step happened or failed merely because another workflow would normally require it. If a hidden process step cannot be verified from the prior artifact, mark it **Not verifiable from the artifact**.

When necessary to determine whether a material conclusion is supportable, perform targeted verification. Do not silently rerun the entire original shopping workflow unless the user asks for a corrected/rebuilt answer.

## 2) Resolve what should have applied
Identify:
- requested deliverable and correct workflow under `instructions.md`;
- resolved Base / Class / Category / Type under `product_hierarchy.md`;
- active specialized hierarchy authorities;
- research mode under `research_sources.md`;
- whether `reviews.md`, `seller_instructions.md`, `pricing.md`, or other shared authorities were materially active;
- active output template.

Preserve the user's hard constraints and locked decisions when judging the answer.

## 3) Apply canonical workflow contracts by reference
Audit the active workflow against its own contract rather than copying its thresholds here:
- Product Research -> `product_research.md`;
- Pricing Tiers -> `pricing_tiers.md`;
- Vendor Research -> `vendor_research.md`;
- Quick Check -> `quick_check.md`.

For self-audit, verify internal process requirements directly.

For retrospective audit, distinguish:
- observable compliance;
- observable violation;
- not verifiable from the artifact.

A missing user-visible research ledger is not evidence that the internal workflow step was skipped when the active template intentionally hides it.

## 4) Apply shared-authority contracts by reference
Check only the authorities that were materially active:
- `research_sources.md` for research mode, evidence admissibility, claim/source fit, independence, coverage, comparability, conflict handling, challenge pass, and stopping rules;
- `reviews.md` for review/community interpretation and pattern-strength language;
- `seller_instructions.md` for seller/channel classification, offer risk, provenance, and price-anomaly diligence;
- `pricing.md` for price-state definitions, normal-price baseline, deal/value interpretation, and diminishing returns;
- `criteria.md` for criterion meaning;
- `source_playbooks.md` for discovery guidance;
- active hierarchy-specialized files for domain-specific behavior.

Do not restate their numeric thresholds or definitions in this file. If a finding depends on one, cite/reference the owning authority.

## 5) Analytical-integrity checks
Independently of workflow bookkeeping, check whether the answer's reasoning is sound.

### Decision fit
- Did the answer solve the user's actual purchase decision rather than a generic category question?
- Were hard constraints applied before soft preference ranking?
- Did consequential assumptions remain visible enough to evaluate?

### Candidate fairness
- Was an important market/design family obviously omitted?
- Was a candidate disadvantaged merely because less information was easy to find?
- Were finalists meaningfully distinct rather than redundant near-duplicates?

### Evidence symmetry and comparability
- Are recommendation-changing claims supported for the products/vendors actually being compared?
- Is missing evidence distinguished from negative evidence?
- Are cross-product measurements or observations genuinely comparable under `research_sources.md`?
- Did the answer create false precision from incompatible methods or variants?

### Causal depth
For recommendation-changing differences, ask whether the answer connects observed differences to user consequences rather than repeating adjectives.

Where supportable, strong analysis should connect:
`feature/design/operating difference -> behavior -> tradeoff -> user consequence -> recommendation effect`

Do not require a causal mechanism when evidence only supports an observation; flag invented mechanism instead.

### Decision boundary / robustness
- Is it clear why the leading option beats its nearest credible rival for this user?
- Is it clear what preference/assumption would flip the choice when the decision is close?
- Does the conclusion rest excessively on one weak, disputed, or non-comparable claim?

## 6) Product identity and current-state checks
Check where material:
- exact model/variant/generation/size/region/condition;
- no silent mixing of materially different revisions;
- current price/availability/policy/support facts fresh enough for the conclusion;
- historical/stable evidence not penalized merely for age when still applicable.

## 7) Review/community checks
When review/community evidence affects the conclusion, apply `reviews.md` and check for obvious misuse such as:
- anecdote presented as pattern;
- repeated retellings counted as independent reports;
- wrong model/revision or ownership horizon;
- seller/shipping problems counted as product defects;
- preference treated as universal quality;
- prevalence inferred without representative denominator data.

Use the exact pattern-strength requirements from `reviews.md`; do not duplicate them here.

## 8) Seller / offer checks
When a concrete seller or offer is recommended, apply `seller_instructions.md`.

Check that the answer separates:
- product quality;
- product value;
- seller/channel quality;
- temporary deal quality.

Verify that material seller/provenance/return/warranty claims are supported through the evidence hierarchy owned by `seller_instructions.md`.

## 9) Pricing checks
When price/value materially affects the answer, apply `pricing.md` and, if active, `pricing_tiers.md`.

Check for obvious errors such as:
- MSRP treated as normal street price without support;
- flash sale/clearance silently treated as permanent market position;
- incomparable variants/conditions/bundles treated as like-for-like;
- extra spend described as value without a concrete user-relevant gain.

## 10) Output-contract check
Apply only the active template.

Check:
- required presentation blocks supplied by the workflow were rendered clearly;
- internal research mechanics were not exposed unless requested/audited;
- the template did not introduce new research or decision logic;
- material uncertainty was not hidden by formatting confidence.

## 11) Severity
### Critical
Could materially mislead the purchase because of wrong identity, incompatibility/safety failure, fabricated/currently false evidence, or a major unsupported conclusion.

### Major
Could change the recommendation or purchase decision: wrong workflow/context, missing hard constraint, failed evidence/comparability requirement, omitted major market family, seller/provenance risk, stale/mis-modeled price, or materially shallow/fragile synthesis.

### Minor
Broadly sound with a limited clarity, coverage, caveat, citation, or formatting defect unlikely to change the recommendation.

### Note
Useful improvement that is not a defect.

## 12) Audit output
Default:
1. Overall status: Pass / Pass with issues / Rework needed.
2. Findings grouped by Critical / Major / Minor / Notes; omit empty groups.
3. For each issue: what happened, why it matters, owning file/contract, concrete fix.
4. Material missing evidence or uncertainty.
5. For retrospective audits, label process-only items that cannot be verified as such rather than inventing a pass/fail.
6. Provide a corrected answer/plan only when requested.

## 13) Repository-maintenance audit
Only when explicitly auditing/editing this project, also check:
- `MAIN.md` is pointer-only;
- `instructions.md` canonical map and first-match routing are complete;
- every rule has one clear owner;
- sibling files reference canonical rules instead of copying thresholds/definitions;
- research-mode selection exists only in `research_sources.md`;
- reusable pricing definitions exist only in `pricing.md`;
- templates own presentation only;
- workflows own sequencing/synthesis only and cannot weaken shared-authority standards;
- hierarchy boundaries are behavior-driven;
- specialized files load only from active hierarchy entries;
- references point to live files/sections;
- `archive/` is not treated as deployable ChatGPT Project context;
- no pseudo-runtime machinery is introduced;
- numeric defaults have triggers/stop conditions/escape clauses in their owning file.

## Boundary
Audit owns audit mode, observability rules, analytical-integrity diagnosis, severity, and audit presentation. It references all other contracts rather than reimplementing them.
