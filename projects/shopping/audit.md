# audit.md
# Audit Workflow / Diagnostic Module (optional)

## 0) Purpose and scope

### Purpose
This file defines an optional diagnostic and quality-audit layer for shopping workflows. Use it to inspect whether routing, source breadth, evidence compliance, and narrowing behavior were correct in a prior workflow output.

This is **not** a normal output mode. It is an optional layer invoked when:
- the user wants to verify or debug the quality of a prior recommendation
- the workflow output seems thin, premature, or inconsistently sourced
- a workflow output is being reviewed for correctness, reproducibility, or bias

### What audit can be invoked on
- Workflow A: Product research
- Workflow B: Pricing tiers
- Workflow C: Quick check
- Workflow D: Vendor research

### What audit is NOT
- Not a workflow that produces shopping recommendations.
- Not a tool to re-run the full workflow from scratch.
- It diagnoses the output with structured questions; it does not replace the source workflow.

---

## 1) Invocation

Invoke this module when:
- the user explicitly asks to audit, review, or debug a prior output
- the user asks "why did you pick these?", "did you check enough sources?", "was that the right route?"
- the AI or user suspects a quality problem with a prior recommendation (thin discovery, wrong routing, premature narrowing, source overuse)

This module does not replace any workflow. It runs as an overlay.

---

## 2) Required audit fields

For any audited output, assess and report on all applicable fields:

### 2.1 Routing and classification
- Which workflow was used (A/B/C/D)?
- Was the routing decision correct given the user's request? If not, which workflow should have been used?
- Was a quick-check hard override applicable but missed?
- Was a vendor-research trigger present that should have routed to Workflow D?
- Was a pricing-tier trigger present that should have routed to Workflow B?

### 2.2 Product/vendor type classification
- What product class/type or vendor category was identified?
- Were the risk posture patterns from `product_types.md` applied correctly?
- Did the risk posture warrant high-intensity escalation (per `product_research.md` Section 15)?

### 2.3 Mode selection
- Which research mode was used (Mode A / B / C)?
- Was Mode B or C used where Mode A should have been used?
- Was mode selection appropriate given the complexity, cost, and risk of the request?
- Note: Mode B is not defined for Workflow D (vendor research); only Mode A and Mode C apply. For Workflow D audits, skip the Mode B check and verify only whether Mode C was used where Mode A should have been used.

### 2.4 Pricing scope
- Was pricing / availability in scope for this output?
- If yes, was `seller_instructions.md` invoked?
- Were comparable totals used consistently?

### 2.5 Discovery breadth
- How many candidates were in the initial pool before hard gates?
- Were the minimum breadth targets met (8-12 candidates for broad category; 5 distinct brands/manufacturers)?
- Were segmentation clusters identified?
- If the market was stated as too narrow, was that reasonable and stated explicitly?

### 2.6 Finalist count and selection
- How many finalists reached the evaluation stage?
- Were enough finalists evaluated given the breadth target (5-8 for product research; 4-8 for vendor research)?
- If fewer, was the reduction clearly justified by constraints or market sparsity?

### 2.7 Recommendation count
- How many recommendations (1 recommended + N runner-ups) were produced?
- Were 2-4 runner-ups included where the market and constraints supported it?
- If fewer runner-ups were included, was the reduction justified?

### 2.8 Evidence compliance
- How many distinct entities were used?
- Was the entity minimum met for the mode used?
  - Mode A: 7 distinct entities
  - Mode B: 3-5 distinct entities
  - Mode C: best available (Coverage limitations required)
- Was the entity overuse cap respected (no single non-primary entity with more than 2 artifacts or 25% of weight)?
- Were the required source variety rules satisfied?
  - Primary/standards present?
  - Method-based source present?
  - 2+ community/owner platforms from different sources?
  - Seller/channel sources present (if pricing in scope)?
- Was any downgrade (Mode A to B or C) documented explicitly?

### 2.9 Source diversity
- Were sources from varied narrative ecosystems (not all from one publication family, not all from one brand community)?
- Was `source_playbooks.md` consulted if the category has known source patterns?

### 2.10 Entity overuse
- Did any single non-primary entity contribute more than 2 evidence artifacts or 25% of total evidentiary weight?
- Was this cap waived explicitly? If waived, was a Coverage limitations note included?

### 2.11 Primary and standards evidence
- Was primary (manufacturer/vendor) evidence present for objective spec claims?
- Were standards/regulatory sources used where applicable (safety, compliance, recall)?
- If primary/standards were unavailable, were two additional independent non-primary entities substituted?

### 2.12 Method-based evidence
- Was at least one method-based publication or expert with transparent methodology used?
- If absent, is there a legitimate reason (niche market, category lacks method-based publications)?

### 2.13 Community and owner-signal diversity
- Were at least 2 distinct community/owner platforms represented?
- Were both from different platforms (not two sections of the same site)?

### 2.14 Discovery-only influence
- Did discovery-only sources materially shape the candidate pool?
- If yes, was this disclosed? Was a discovery ledger provided?
- Were discovery-only sources incorrectly included in the evidence list?

### 2.15 Unresolved uncertainties
- What material claims remain uncertain or inadequately supported?
- Are these gaps disclosed in the output?
- What evidence would change the conclusion?

---

## 3) Audit output format

### Compact audit report structure

**Audit of:** {WORKFLOW_A_B_C_OR_D} output for "{QUERY_OR_CATEGORY}"  
**Audit date:** {AUDIT_DATE_YYYY_MM_DD}

---

**Routing:**
- Workflow used: {WORKFLOW}
- Correct routing: {YES_OR_NO_WITH_REASON}
- Hard override applicable but missed: {YES_NO_OR_N_A}

**Classification:**
- Product/vendor type: {TYPE}
- Risk posture applied: {YES_NO_OR_N_A}
- High-intensity escalation warranted: {YES_NO}

**Mode:**
- Mode used: {A_B_OR_C}
- Mode appropriate: {YES_OR_NO_WITH_REASON}

**Discovery breadth:**
- Candidate pool size (before hard gates): {COUNT_OR_UNKNOWN}
- Minimum met (8-12 / 5 brands): {YES_NO_OR_NOT_APPLICABLE}
- Segmentation clusters identified: {YES_NO_OR_NOT_APPLICABLE}

**Finalist count:** {COUNT} (target: 5-8 for product; 4-8 for vendor)

**Recommendation count:** 1 recommended + {RUNNER_UP_COUNT} runner-ups (target: 2-4 unless exception)

**Evidence compliance:**
- Distinct entities: {COUNT} (minimum: {MIN_FOR_MODE})
- Primary/standards present: {YES_NO_OR_N_A}
- Method-based present: {YES_NO}
- Community platforms: {COUNT} (need 2+ distinct)
- Entity overuse cap respected: {YES_NO_OR_WAIVED}
- Downgrade documented: {YES_NO_OR_N_A}

**Discovery-only disclosed:** {YES_NO_OR_N_A}

**Unresolved uncertainties:**
- {UNCERTAINTY_1_OR_NONE}

**What evidence would change the conclusion:**
- {EVIDENCE_GAP_1_OR_NONE}

**Overall audit verdict:**
- {PASS_OR_ISSUES_FOUND}: {BRIEF_SUMMARY}
