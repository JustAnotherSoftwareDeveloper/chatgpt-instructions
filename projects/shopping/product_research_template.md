# Product Research: {PRODUCT_OR_CATEGORY}

**Region / Currency / Condition:** {REGION=USA} / {CURRENCY=USD} / {CONDITION=New unless specified}  
**Key constraints:** {CONSTRAINTS_OR_N_A}  
**Mode:** {MODE=A_OR_B_OR_C}  
**Pricing in scope:** {PRICING_IN_SCOPE=Yes_or_No}  
**Research performed:** {RESEARCH_PERFORMED_YYYY_MM_DD_HH_MM_ET}  
{PRICES_CHECKED_LINE_OR_EMPTY}  
{PRICING_BASIS_LINE_OR_EMPTY}

<!-- TEMPLATE CONTRACT (do not render):
- ASCII-only punctuation and straight quotes.
- Omit entire sections when N/A (use *_FULL_BLOCK_OR_EMPTY placeholders).
- If fewer than 6 finalists are used, delete the unused finalist lines, decision-matrix rows, and finalist profile sections entirely (e.g., remove F4-F6 blocks).
- Any *_FULL_BLOCK_OR_EMPTY placeholder must include the full header + body (e.g., "## Pricing and Availability" + content) or be empty.
- Any SOURCES_*_FULL_BLOCK_OR_EMPTY placeholder must include its own "#### Group Name" header + bullet list, or be empty.
- PRICES_CHECKED_LINE_OR_EMPTY must be either empty or a full labeled line: "**Prices checked:** {YYYY-MM-DD hh:mm ET}  "
- PRICING_BASIS_LINE_OR_EMPTY must be either empty or a full labeled line: "**Pricing basis:** Comparable totals (tax-excluded) unless requested otherwise  "
- OPTIONAL_RECOMMENDATION_SNAPSHOT_TABLE_ROWS_BLOCK_OR_EMPTY must be either empty or one-or-more markdown table rows (start with "|" and include exactly 6 columns).
- F*_NOTABLE_RISKS_BLOCK_OR_EMPTY must include its own bold label(s) (e.g., "**Notable risks:**") or be empty.
- F*_BUYING_BLOCK_OR_EMPTY must include its own bold label(s) (e.g., "**Street price:**", "**Where to buy:**", "**Warranty/returns:**") or be empty.
- OPTIONAL_ADDITIONAL_CLAIMS_BLOCK_OR_EMPTY must be either empty or one-or-more complete claim blocks matching the "Claim/Evidence/Confidence/Recency" format below.
-->

---

## Executive Summary (5-8 sentences)

{EXEC_SUMMARY_5_TO_8_SENTENCES}

---

## Recommendation Snapshot

| **Slot** | **Pick** | **Why (short)** | **Top caveat** | **Confidence** | **Price band (if pricing in scope)** |
|---|---|---|---|---|---|
| **Recommended** | {RECOMMENDED_PICK} | {RECOMMENDED_WHY_SHORT} | {RECOMMENDED_CAVEAT} | {RECOMMENDED_CONFIDENCE_HML} | {RECOMMENDED_PRICE_BAND_OR_N_A} |
| **Runner-up** | {RUNNER_UP_PICK} | {RUNNER_UP_WHY_SHORT} | {RUNNER_UP_CAVEAT} | {RUNNER_UP_CONFIDENCE_HML} | {RUNNER_UP_PRICE_BAND_OR_N_A} |
{OPTIONAL_RECOMMENDATION_SNAPSHOT_TABLE_ROWS_BLOCK_OR_EMPTY}

---

## Finalists Evaluated

- {F1_NAME} ({F1_VARIANT}){F1_FLAGS_PREFIXED_OR_EMPTY}
- {F2_NAME} ({F2_VARIANT}){F2_FLAGS_PREFIXED_OR_EMPTY}
- {F3_NAME} ({F3_VARIANT}){F3_FLAGS_PREFIXED_OR_EMPTY}
- {F4_NAME} ({F4_VARIANT}){F4_FLAGS_PREFIXED_OR_EMPTY}
- {F5_NAME} ({F5_VARIANT}){F5_FLAGS_PREFIXED_OR_EMPTY}
- {F6_NAME} ({F6_VARIANT}){F6_FLAGS_PREFIXED_OR_EMPTY}

---

## Decision Matrix

| **Finalist** | **Constraint fit** | **Performance ceiling** | **Reliability confidence** | **UX/firmware risk** | **Safety/compliance** | **Total cost factors** | **Overall value** |
|---|---|---|---|---|---|---|---|
| {F1_NAME} | {F1_CONSTRAINT_FIT_PASS_PARTIAL_FAIL} | {F1_PERF_CEILING} | {F1_RELIABILITY_HML} ({F1_RELIABILITY_REASON_1_WORD}) | {F1_UX_FIRMWARE_RISK_LOW_MED_HIGH_OR_N_A} | {F1_SAFETY_PASS_UNKNOWN_N_A} | {F1_TOTAL_COST_FACTORS} | {F1_OVERALL_VALUE_HML} |
| {F2_NAME} | {F2_CONSTRAINT_FIT_PASS_PARTIAL_FAIL} | {F2_PERF_CEILING} | {F2_RELIABILITY_HML} ({F2_RELIABILITY_REASON_1_WORD}) | {F2_UX_FIRMWARE_RISK_LOW_MED_HIGH_OR_N_A} | {F2_SAFETY_PASS_UNKNOWN_N_A} | {F2_TOTAL_COST_FACTORS} | {F2_OVERALL_VALUE_HML} |
| {F3_NAME} | {F3_CONSTRAINT_FIT_PASS_PARTIAL_FAIL} | {F3_PERF_CEILING} | {F3_RELIABILITY_HML} ({F3_RELIABILITY_REASON_1_WORD}) | {F3_UX_FIRMWARE_RISK_LOW_MED_HIGH_OR_N_A} | {F3_SAFETY_PASS_UNKNOWN_N_A} | {F3_TOTAL_COST_FACTORS} | {F3_OVERALL_VALUE_HML} |
| {F4_NAME} | {F4_CONSTRAINT_FIT_PASS_PARTIAL_FAIL} | {F4_PERF_CEILING} | {F4_RELIABILITY_HML} ({F4_RELIABILITY_REASON_1_WORD}) | {F4_UX_FIRMWARE_RISK_LOW_MED_HIGH_OR_N_A} | {F4_SAFETY_PASS_UNKNOWN_N_A} | {F4_TOTAL_COST_FACTORS} | {F4_OVERALL_VALUE_HML} |
| {F5_NAME} | {F5_CONSTRAINT_FIT_PASS_PARTIAL_FAIL} | {F5_PERF_CEILING} | {F5_RELIABILITY_HML} ({F5_RELIABILITY_REASON_1_WORD}) | {F5_UX_FIRMWARE_RISK_LOW_MED_HIGH_OR_N_A} | {F5_SAFETY_PASS_UNKNOWN_N_A} | {F5_TOTAL_COST_FACTORS} | {F5_OVERALL_VALUE_HML} |
| {F6_NAME} | {F6_CONSTRAINT_FIT_PASS_PARTIAL_FAIL} | {F6_PERF_CEILING} | {F6_RELIABILITY_HML} ({F6_RELIABILITY_REASON_1_WORD}) | {F6_UX_FIRMWARE_RISK_LOW_MED_HIGH_OR_N_A} | {F6_SAFETY_PASS_UNKNOWN_N_A} | {F6_TOTAL_COST_FACTORS} | {F6_OVERALL_VALUE_HML} |

---

## Why This Recommendation

{BUCKET_SPECS_COMPAT_FULL_BLOCK_OR_EMPTY}

{BUCKET_PERFORMANCE_FULL_BLOCK_OR_EMPTY}

{BUCKET_RELIABILITY_FULL_BLOCK_OR_EMPTY}

{BUCKET_UX_FIRMWARE_FULL_BLOCK_OR_EMPTY}

{BUCKET_SAFETY_COMPLIANCE_FULL_BLOCK_OR_EMPTY}

{BUCKET_TOTAL_COST_FULL_BLOCK_OR_EMPTY}

---

## Finalist Profiles

### {F1_NAME} ({F1_VARIANT})

{F1_DESC_1_TO_2_SENTENCES}

**Strengths:**
- {F1_STRENGTH_BULLET_1}
- {F1_STRENGTH_BULLET_2}

**Weaknesses:**
- {F1_WEAKNESS_BULLET_1}
- {F1_WEAKNESS_BULLET_2}

**Best for:**
- {F1_BEST_FOR_BULLET_1}

**Avoid if:**
- {F1_AVOID_IF_BULLET_1}

{F1_NOTABLE_RISKS_BLOCK_OR_EMPTY}

{F1_BUYING_BLOCK_OR_EMPTY}

---

### {F2_NAME} ({F2_VARIANT})

{F2_DESC_1_TO_2_SENTENCES}

**Strengths:**
- {F2_STRENGTH_BULLET_1}
- {F2_STRENGTH_BULLET_2}

**Weaknesses:**
- {F2_WEAKNESS_BULLET_1}
- {F2_WEAKNESS_BULLET_2}

**Best for:**
- {F2_BEST_FOR_BULLET_1}

**Avoid if:**
- {F2_AVOID_IF_BULLET_1}

{F2_NOTABLE_RISKS_BLOCK_OR_EMPTY}

{F2_BUYING_BLOCK_OR_EMPTY}

---

### {F3_NAME} ({F3_VARIANT})

{F3_DESC_1_TO_2_SENTENCES}

**Strengths:**
- {F3_STRENGTH_BULLET_1}
- {F3_STRENGTH_BULLET_2}

**Weaknesses:**
- {F3_WEAKNESS_BULLET_1}
- {F3_WEAKNESS_BULLET_2}

**Best for:**
- {F3_BEST_FOR_BULLET_1}

**Avoid if:**
- {F3_AVOID_IF_BULLET_1}

{F3_NOTABLE_RISKS_BLOCK_OR_EMPTY}

{F3_BUYING_BLOCK_OR_EMPTY}

---

### {F4_NAME} ({F4_VARIANT})

{F4_DESC_1_TO_2_SENTENCES}

**Strengths:**
- {F4_STRENGTH_BULLET_1}
- {F4_STRENGTH_BULLET_2}

**Weaknesses:**
- {F4_WEAKNESS_BULLET_1}
- {F4_WEAKNESS_BULLET_2}

**Best for:**
- {F4_BEST_FOR_BULLET_1}

**Avoid if:**
- {F4_AVOID_IF_BULLET_1}

{F4_NOTABLE_RISKS_BLOCK_OR_EMPTY}

{F4_BUYING_BLOCK_OR_EMPTY}

---

### {F5_NAME} ({F5_VARIANT})

{F5_DESC_1_TO_2_SENTENCES}

**Strengths:**
- {F5_STRENGTH_BULLET_1}
- {F5_STRENGTH_BULLET_2}

**Weaknesses:**
- {F5_WEAKNESS_BULLET_1}
- {F5_WEAKNESS_BULLET_2}

**Best for:**
- {F5_BEST_FOR_BULLET_1}

**Avoid if:**
- {F5_AVOID_IF_BULLET_1}

{F5_NOTABLE_RISKS_BLOCK_OR_EMPTY}

{F5_BUYING_BLOCK_OR_EMPTY}

---

### {F6_NAME} ({F6_VARIANT})

{F6_DESC_1_TO_2_SENTENCES}

**Strengths:**
- {F6_STRENGTH_BULLET_1}
- {F6_STRENGTH_BULLET_2}

**Weaknesses:**
- {F6_WEAKNESS_BULLET_1}
- {F6_WEAKNESS_BULLET_2}

**Best for:**
- {F6_BEST_FOR_BULLET_1}

**Avoid if:**
- {F6_AVOID_IF_BULLET_1}

{F6_NOTABLE_RISKS_BLOCK_OR_EMPTY}

{F6_BUYING_BLOCK_OR_EMPTY}

---

{PRICING_SECTION_FULL_BLOCK_OR_EMPTY}

{AVOID_TRAPS_SECTION_FULL_BLOCK_OR_EMPTY}

## Evidence (Evidence Only)

### Sources (grouped; evidence only)

{SOURCES_PRIMARY_FULL_BLOCK_OR_EMPTY}

{SOURCES_STANDARDS_FULL_BLOCK_OR_EMPTY}

{SOURCES_PUBLICATIONS_FULL_BLOCK_OR_EMPTY}

{SOURCES_INDIVIDUALS_FULL_BLOCK_OR_EMPTY}

{SOURCES_CROWDSOURCED_FULL_BLOCK_OR_EMPTY}

{SOURCES_PRICING_FULL_BLOCK_OR_EMPTY}

---

### Claims-to-Evidence Map (Required)

- **Claim:** {CLAIM_1}  
  **Evidence:** {CLAIM_1_EVIDENCE_SOURCE_SHORTNAMES}  
  **Confidence:** {CLAIM_1_CONFIDENCE_HML}  
  **Recency/version note (if applicable):** {CLAIM_1_RECENCY_NOTE_OR_N_A}

- **Claim:** {CLAIM_2}  
  **Evidence:** {CLAIM_2_EVIDENCE_SOURCE_SHORTNAMES}  
  **Confidence:** {CLAIM_2_CONFIDENCE_HML}  
  **Recency/version note (if applicable):** {CLAIM_2_RECENCY_NOTE_OR_N_A}

- **Claim:** {CLAIM_3}  
  **Evidence:** {CLAIM_3_EVIDENCE_SOURCE_SHORTNAMES}  
  **Confidence:** {CLAIM_3_CONFIDENCE_HML}  
  **Recency/version note (if applicable):** {CLAIM_3_RECENCY_NOTE_OR_N_A}

- **Claim:** {CLAIM_4}  
  **Evidence:** {CLAIM_4_EVIDENCE_SOURCE_SHORTNAMES}  
  **Confidence:** {CLAIM_4_CONFIDENCE_HML}  
  **Recency/version note (if applicable):** {CLAIM_4_RECENCY_NOTE_OR_N_A}

- **Claim:** {CLAIM_5}  
  **Evidence:** {CLAIM_5_EVIDENCE_SOURCE_SHORTNAMES}  
  **Confidence:** {CLAIM_5_CONFIDENCE_HML}  
  **Recency/version note (if applicable):** {CLAIM_5_RECENCY_NOTE_OR_N_A}

{OPTIONAL_ADDITIONAL_CLAIMS_BLOCK_OR_EMPTY}

---

### Confidence meaning

- High: strong triangulation across high-quality sources + low coverage gaps
- Medium: adequate triangulation with some gaps or mixed signals
- Low: sparse/low-quality evidence, high uncertainty, or strong version sensitivity

---

{DISCOVERY_ONLY_SECTION_FULL_BLOCK_OR_EMPTY}

{COVERAGE_LIMITATIONS_SECTION_FULL_BLOCK_OR_EMPTY}

{ASSUMPTIONS_SECTION_FULL_BLOCK_OR_EMPTY}
