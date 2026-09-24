# Research Source Authority

## Purpose
Own evidence admissibility, claim/source fit, independence, recency, coverage, conflict handling, uncertainty, and claim-to-evidence discipline for Shopping research.

This file governs evidence quality. It does not define category-specific discovery, review-content interpretation, seller/channel risk, workflow steps, or output formatting.

## 1) Evidence model
### Source artifact vs source entity
- A **source artifact** is a specific page, document, video, post, thread, dataset, or listing.
- A **source entity** is the responsible publisher/author/organization/creator.

Multiple artifacts from the same entity may be useful, but they do not create independent corroboration by themselves.

Collapse syndicated, mirrored, paraphrased, or citation-ring content to the underlying information origin when assessing independence.

### Discovery vs evidence
Discovery sources may help:
- identify candidates;
- map terminology;
- locate primary documents;
- discover market segments or known issues.

Discovery alone does not make a source suitable evidence for a conclusion.

Do not use search snippets, affiliate roundups, copied lists, or unverified marketplace text as evidence merely because they were useful for discovery.

## 2) Admissibility before weight
Evaluate whether a source is usable for the claim before deciding how much weight to give it.

A source may be inadmissible for one claim and useful for another. Examples:
- manufacturer documentation may be excellent for supported dimensions but weak evidence of real-world durability;
- owner reports may be useful for recurring failure modes but not authoritative for official specifications;
- seller listings may establish current offer terms but should not override primary product documentation.

Weighting cannot rescue a source that is fundamentally mismatched to the claim.

## 3) Source families and best uses
### Primary / official
Examples:
- manufacturer manuals, datasheets, compatibility lists, warranty terms, support bulletins, release notes;
- standards, certification, regulatory, recall, and official registry sources.

Best for:
- objective specifications;
- documented compatibility and support boundaries;
- warranty/policy language;
- safety/compliance/recall facts.

Limit:
- manufacturer marketing is not independent evidence of comparative performance, reliability, or value.

### Method-based publications / specialists
Best for:
- measured or repeatable performance;
- structured comparisons;
- documented tests;
- category-specific evaluation where methodology is visible.

Assess whether the test conditions actually match the claim and user use case.

### Domain experts / experienced practitioners
Best for:
- nuanced tradeoffs;
- technical interpretation;
- maintenance/service realities;
- hands-on behavior difficult to reduce to benchmarks.

Require demonstrated competence, specificity, and clear context. Expertise does not eliminate incentive or preference bias.

### Owner/community evidence
Best for:
- long-term reliability and wear;
- unit variation and QC patterns;
- workflow friction;
- edge cases and compatibility reality;
- newly emerging issues;
- preference-sensitive experience.

Use patterns and specificity, not isolated anecdotes or raw star averages.

Review/community interpretation is governed by `reviews.md`.

### Seller / listing evidence
Best for:
- current price;
- stock/availability;
- included accessories/condition;
- shipping, return, and offer-specific terms.

Seller/channel interpretation is governed by `seller_instructions.md`.

A seller listing should not be the sole support for a disputed technical product claim when better sources are available.

## 4) Match evidence to claim type
### Objective specifications / compatibility
Prefer primary or official documentary evidence.

If primary evidence is unavailable or ambiguous, corroborate with independent technically competent sources and state uncertainty if material.

### Measured / repeatable performance
Prefer transparent method-based testing or technically competent sources that disclose enough conditions to interpret the result.

Do not combine unlike measurements as if they were directly comparable.

### Reliability / durability / QC
Prefer a mix of:
- long-term testing where available;
- broad, independent owner/community signal;
- repair/service evidence where relevant;
- official acknowledgements, bulletins, warranty changes, or recalls when applicable.

Do not infer a numerical failure rate from self-selected online reports unless a credible dataset actually supports one.

### Safety / compliance
Prefer authoritative standards, regulatory, certification, recall, and primary documentation.

Community reports can identify a possible issue but are not proof of regulatory or safety status.

### Subjective fit / comfort / taste / aesthetics
Use diverse, context-rich hands-on or owner perspectives.

Scope conclusions to preferences: "better for X" is usually more defensible than universal "best" claims.

### Current price / availability / policy
Use recent, directly observed seller or primary sources. Time-stamp mentally or in output when the fact is likely to change quickly.

## 5) Research depth by decision risk
Do not use fixed URL quotas. Gather enough independent evidence to cover the material claim types and decision risks.

### Quick / narrow
Appropriate for a focused factual or one-product sanity question with low ambiguity.

Aim to verify the few claims that can change the answer, using the strongest source type for each.

### Standard purchase research
Appropriate for ordinary recommendations and comparisons.

Cover, where material:
- primary/documentary facts;
- independent performance or expert evidence;
- real-world ownership/reliability signal;
- current market evidence when price/availability matters.

Use multiple independent source entities across the important claim types. Do not pad the research with low-value sources to hit a count.

### Deep / high-consequence
Increase breadth and triangulation when the decision involves one or more of:
- high cost relative to the category/user;
- long ownership horizon;
- safety or significant compatibility risk;
- counterfeit/gray-market exposure;
- high unit variation or known revision risk;
- enthusiast/luxury purchases where execution and provenance matter;
- contradictory or sparse evidence;
- explicit user request for deep research.

Deep research should reduce dependence on any single non-primary source and intentionally seek disagreement, long-term evidence, and domain-native expertise.

### Sparse coverage
When credible evidence is genuinely limited:
- use the strongest available evidence;
- do not manufacture breadth with weak sources;
- explicitly state what could not be verified;
- narrow the conclusion and confidence accordingly;
- identify what evidence would most change the answer when useful.

## 6) Independence and narrative concentration
Do not confuse multiple links with multiple independent perspectives.

Treat as non-independent or partially dependent when appropriate:
- syndicated articles;
- copied tests;
- embargo-day coverage repeating the same briefing;
- multiple channels/accounts from the same reviewer;
- publications in the same editorial network repeating one analysis;
- many community comments deriving from one viral claim rather than independent experience.

For meaningful conclusions, avoid letting one non-primary entity or one narrative ecosystem dominate when independent alternatives exist.

## 7) Recency and versioning
Classify material claims by temporal sensitivity.

### High temporal sensitivity
Examples:
- current price and availability;
- firmware/app behavior;
- software compatibility;
- support/EOL status;
- seller policies;
- active revisions or silent component changes;
- recalls and current certification status.

Prefer recent, version-aware evidence.

### Low temporal sensitivity
Examples:
- stable physical geometry;
- mature material properties;
- historical construction methods;
- long-established ownership characteristics that have not changed by revision.

Prefer quality and applicability over superficial recency.

When sources disagree, check model year, generation, SKU, region, firmware, component revision, test conditions, and source date before treating the disagreement as substantive.

## 8) Conflict handling
When credible sources disagree:
1. Identify the exact claim in dispute.
2. Check product/variant/version equivalence.
3. Compare source type and methodology appropriate to that claim.
4. Look for different test conditions, use patterns, time horizons, incentives, sample bias, or revision drift.
5. Seek an additional independent source when the disagreement matters to the recommendation.
6. If unresolved, narrow the claim and present the uncertainty instead of forcing a consensus.

Do not average incompatible claims into a false middle.

## 9) Claim-to-evidence discipline
For every recommendation-changing claim, know internally:
- what the claim is;
- which source entities support or challenge it;
- what kind of evidence they provide;
- how current/variant-specific the evidence is;
- how confident the claim should be.

The normal final answer does not need to expose a formal claim ledger. Provide citations or a concise research basis appropriate to the output. Expose deeper claim/source mapping when the user requests the basis or invokes `audit.md`.

## 10) Confidence
Use confidence as a summary of evidence quality and coverage, not rhetorical certainty.

### High
Strong claim/source fit, independent corroboration where needed, correct variant/version, and no material unresolved gaps.

### Medium
Useful evidence with meaningful gaps, mixed signals, limited long-term coverage, or some version/market uncertainty.

### Low
Sparse or weak evidence, unresolved contradictions, uncertain product identity, strong temporal sensitivity without current verification, or major missing claim types.

Confidence may vary by claim within the same product.

## 11) Research integrity rules
- Do not fabricate sources, quotes, measurements, owner patterns, or current prices.
- Do not cite a source for a claim it does not actually support.
- Do not convert repeated anecdotes into a known prevalence rate.
- Do not treat affiliate status alone as disqualifying; evaluate original work, methodology, incentives, and corroboration.
- Do not treat primary/vendor claims as independent validation of themselves.
- Do not let a source playbook lower these evidence standards.
- If browsing/current verification is unavailable when a material current fact is required, state the limitation and avoid pretending the fact was checked.

## Boundary
`source_playbooks.md` owns where to look; `reviews.md` owns interpretation of review/community content; `seller_instructions.md` owns seller/channel and offer risk; workflows decide how research is sequenced and synthesized.
