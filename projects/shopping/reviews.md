# reviews.md

## Scope

This file defines how to evaluate and synthesize "reviews" as evidence.

It covers:
- Review source types and the unique value each provides
- Filters to exclude or discount low-quality, manipulated, or agenda-driven content
- Strictness rules that vary by source type (publication vs influencer vs crowdsourced)
- Minimum requirements for source counts and source variety (risk-based)
- How to extract claims and aggregate them into defensible conclusions

This file does NOT define:
- Global source tiers across all research (see `research_sources.md`)
- Seller/vendor risk rules (see `seller_instructions.md`)
- Category tuning knobs (see `product_types.md`)
- Output templates (the minimal reviews-only mode is intentionally free-form)

## Goals

When using review evidence, optimize for:
- Authenticity over volume
- Independence (avoid copied/collapsed “consensus”)
- Correct domain competence (reviewer is qualified for *this* category)
- Incentive- and agenda-aware synthesis
- Practical decision value (what breaks, what frustrates, what’s worth paying for)

---

## Review source types (what each is good for, what to look for)

### Type A: Official / primary sources (not “reviews,” but critical evidence)
Examples:
- Manufacturer spec sheets, manuals, firmware notes, support bulletins
- Standards/certification bodies (UL/ETL, USB-IF, Wi-Fi Alliance, Bluetooth SIG)
- Regulatory filings (FCC ID exhibits where relevant)

Unique value:
- Hard constraints: feature existence, supported standards, documented limitations
- Compatibility boundaries and “gotchas” buried in manuals
- Warranty terms and support policy language (when clear)

What to look for:
- Exact model/SKU and regional variants
- Port/codec/standard support, power requirements, dimensional drawings
- Firmware/update notes that admit known issues or fixes

Limitations:
- Marketing bias is inherent; performance/value claims require independent corroboration

---

### Type B: Respected publications (institutional testing + editorial standards)
Examples:
- Consumer Reports, Wirecutter/NYT, Ars Technica, Car and Driver, Rtings, PCMag,
  Tom’s Hardware (category dependent)

Unique value:
- Comparable baselines across products
- Methodology that is usually more repeatable and accountable
- Better chance of catching systemic issues (design flaws, heat, durability, regressions)

What to look for:
- Explicit methodology and test conditions
- Comparative context (what competitors were included and why)
- Disclosure of affiliate relationships and sample sourcing
- Category track record (domain fit)

Common failure modes:
- Shallow coverage outside their expertise
- “Roundups” that drift into affiliate-style listicles

---

### Type C: Respected individuals (specialist reviewers / journalists / engineers)
Examples:
- Category specialists with consistent testing approaches
- Journalists with deep beats (networking, cameras, AV)
- Influencers who show measurements, comparisons, and long-term use

Unique value:
- Depth and nuance; better coverage of edge cases and real-world constraints
- Faster discovery of new issues (firmware regressions, silent revisions)
- Often better “operator insight” than publications in narrow niches

What to look for:
- Stable methodology or consistent comparison set
- Clear disclosure (sponsorships, affiliate links, “provided by brand”)
- Evidence of competence (correct terminology, correct mental model)
- Willingness to state negatives and uncertainty

Common failure modes:
- Engagement incentives (hot takes, outrage, certainty theater)
- Sponsored content that quietly narrows comparisons

---

### Type D: Crowdsourced reviews (high-variance, high authenticity potential)
Examples:
- Verified-purchase retailer reviews
- Owner forums/subreddits, long-term threads
- Repair/RMA experiences and recurring defect reports

Unique value (why you want these even when messy):
- Best signal for reliability distribution and QA variance:
  - “How often does this fail?” and “what fails first?”
- Real-world friction:
  - setup pain, buggy apps, confusing controls, latency and CEC issues, connectivity instability
- Detection of silent revisions:
  - “same model name, different internals” often appears first in owner communities
- Counterweight against polished narratives:
  - recurring patterns expose issues marketing and early reviews miss

What to look for:
- Specificity: model/SKU, firmware version, environment, timeline (“after 6 months…”)
- Repeated, specific failure modes across unrelated users
- Evidence artifacts: photos, logs, screenshots, measurements, teardown pics

Common failure modes:
- Manipulation/astroturfing; must filter
- Negative-reporting bias; treat prevalence carefully

---

## Definitions

### Distinct source (what counts)
A **distinct source** is an independent origin of information, not merely a different URL.

Counts as distinct:
- A publication or individual performing their own testing or long-term use
- A separate owner population on a separate platform (retailer vs forum vs subreddit)
- Primary documentation from the manufacturer or a standards body

Does NOT count as distinct:
- Syndicated/rehosted copies of the same review
- Multiple posts of the same reviewer on different platforms
- “Press event” or embargo-day coverage where many outlets repeat the same briefing
- Citation rings / listicles that paraphrase one another without original work
- Retailer pages that display the same syndicated review corpus (treat as non-distinct unless review populations are actually different)

Rule:
- When in doubt, treat it as non-distinct for minimum-source counting, but it may still be cited for convenience.

### Claim criticality (drives sourcing strictness)
- **Low-stakes / narrow claim**: “Does it support X?” “Is port Y present?” “Does it fit dimension Z?”
- **Purchase decision claim**: “Is it good value?” “Should I buy this?” “Which is better?”
- **High-impact risk claim**: safety, reliability, long-term durability, expensive categories, high variance categories

---

## Strictness model (different standards by source type)

Do NOT apply identical standards to all sources.

### Type B (respected publications)
Minimum bar:
- Domain fit + some stated methodology
- Clear separation of measured facts vs opinion
Discount if:
- Affiliate-framed roundup with no testing
- Category mismatch (generalist outlet reviewing niche gear without competence)

### Type C (respected individuals)
Minimum bar:
- Demonstrated category competence + incentive transparency
- At least one concrete comparator or repeatable claim
Discount if:
- Strong sponsorship framing without critique
- Broad claims without evidence (“destroys the competition”)

### Type D (crowdsourced)
Minimum bar:
- Specificity + plausibility
- Used primarily for patterns/failure modes/usability friction
Discount if:
- Vague praise/complaint with no details
- Strong manipulation signatures
Note:
- Writing style alone (including “AI-ish tone”) is a weak signal; prioritize duplication/coordination signals.

### Type A (official/primary)
Minimum bar:
- Authoritative for feature existence and documented constraints
Never use alone for:
- Performance, reliability, or value judgments

---

## Filters (exclude vs discount) — expanded categories

Apply filters before weighting. Each filter has:
- **Exclude triggers**: remove the source/item from evidence
- **Discount triggers**: keep but reduce weight substantially

### Filter 1: Affiliate listicles / blogspam
Exclude if:
- No author identity/credentials; no original work; no methodology
- Pure rankings and adjectives; no falsifiable claims
- Aggressive CTAs; “best X” content across many unrelated categories
Discount if:
- Contains correct specs but no original evaluation

### Filter 2: SEO content farms and review laundering
Exclude if:
- Paraphrases other reviews with no primary evidence, tests, or original media
- “Consensus narration” without attribution (“people say…”) or with circular citations
Discount if:
- The only unique content is lightly rewritten summaries

### Filter 3: AI-generated / semi-automated content
Exclude if:
- Hallucinated/contradictory specs; mismatched ports/standards/sizes
- Repetitive filler; generic prose; inconsistent conclusions
Discount if:
- AI is plausible but claims are narrowly scoped and independently corroborated
Type D note:
- For crowdsourced items, exclude only when clearly synthetic/duplicated; otherwise treat as discountable noise.

### Filter 4: Syndication / non-independence (collapsed consensus)
Exclude as “independent evidence” if:
- It is a rehost, press-release rewrite, or affiliate mirror of the same work
Rule:
- You may cite it for convenience, but it does not count toward “distinct sources.”

### Filter 5: Astroturfing / coordinated manipulation
Exclude individual items if:
- Duplicated phrasing across accounts; synthetic account behavior
- Incentivized reviews without clear disclosure
Discount dataset if:
- Rating bursts suggest coordination
- Star rating diverges sharply from detailed written reports
Rule:
- If manipulation is plausible, ignore star averages as evidence.

### Filter 6: Domain competence mismatch (operational gate)
Apply a hard gate when all three are true:
- No demonstrated track record in the category, AND
- Strong technical claims are made, AND
- Methodology/context is not provided
Action:
- Discount strongly or exclude for those technical claims.

### Filter 7: Version/SKU ambiguity
Exclude if:
- Review cannot be tied to exact model/SKU/trim/year where variants matter
Discount if:
- It is “probably” the right variant but not confirmed

### Filter 8: Unrealistic certainty / sales framing / “certainty theater”
Exclude/discount if:
- Absolute language substitutes for evidence (“objectively the best,” “no downsides”)
- Claims are broader than the presented evidence supports
Discount strongly if:
- The piece avoids tradeoffs, failure modes, and limitations entirely

### Filter 9: Methodology opacity (for measurable claims)
Exclude/discount if:
- Measurable claims (battery, throughput, latency, brightness) are made without conditions/tests
Rule:
- For Type B/C, measurable claims require at least minimal method disclosure.

### Filter 10: Sample bias and time-horizon mismatch
Discount if:
- Review is day-1 only when the issue class is long-term (battery, wear, firmware stability)
- Crowdsourced reports are drawn from a skewed population (single thread, single retailer)
Rule:
- Use long-term evidence for long-term risk claims.

### Filter 11: “Hidden constraints” omission (competence signal)
Discount if:
- The reviewer consistently fails to discuss known, common constraints for the category
Examples:
- AV: ARC/eARC quirks, lip-sync, CEC weirdness
- Networking: interference, firmware regressions, topology sensitivity
- Cars: trim differences, long-term maintenance, recall handling

### Filter 12: Agenda filters (split into two distinct filters)

#### Filter 12A: Financial agenda / incentive distortion
Exclude/discount if:
- Sponsorship/affiliate relationships are undisclosed or misleadingly buried
- Comparisons are selectively constrained to weak alternatives
- Content reads like sales enablement (pricing pushes, urgency language)
Rule:
- Not automatically disqualifying, but must be discounted unless corroborated independently.

#### Filter 12B: Non-financial agenda / narrative framing distortion (including subtle canaries)
Exclude/discount if:
- Content injects ideological framing unrelated to product evaluation
- Uses recurring “canary” language that signals narrative alignment over analysis
Rule:
- Testable claims can be retained only if independently corroborated.
- Rhetorical framing is ignored and often triggers a discount to the entire source.

### Filter 13: Channel contamination (counterfeit / wrong-item / refurb-as-new / fulfillment issues)
Problem:
- Review evidence often mixes product defects with seller/channel failures.

Signals:
- Reports of missing parts, opened packaging, wrong model shipped
- “Refurbished sold as new” language
- Counterfeit accusations or inconsistent build quality tied to marketplace sellers
- Failures strongly correlated with third-party marketplace channels

Action:
- Do not treat these as product-quality evidence until you separate:
  - product defect vs channel defect
- Route channel-defect conclusions to `seller_instructions.md` logic.

---

## Filter strictness matrix (default action by source type)

Legend:
- EX = Exclude
- DS = Discount strongly
- D  = Discount
- N/A = Not applicable / usually not a meaningful criterion

| Filter category                               | Type A | Type B | Type C | Type D |
|----------------------------------------------|--------|--------|--------|--------|
| Affiliate listicles / blogspam               | N/A    | DS     | DS     | N/A    |
| SEO laundering / paraphrase-only             | N/A    | DS     | DS     | D      |
| AI-generated / hallucinated specs            | EX     | EX     | EX     | DS     |
| Non-independence / syndication               | DS     | DS     | DS     | DS     |
| Astroturfing / coordination                  | N/A    | D      | D      | EX/DS  |
| Domain competence mismatch (for tech claims) | N/A    | DS     | DS     | D      |
| Version/SKU ambiguity                         | DS     | DS     | DS     | D      |
| Certainty theater / sales framing            | N/A    | D      | DS     | D      |
| Methodology opacity (measurable claims)      | N/A    | DS     | DS     | N/A    |
| Time-horizon mismatch                         | N/A    | D      | D      | D      |
| Hidden constraints omission                   | N/A    | D      | D      | N/A    |
| Financial agenda distortion                   | N/A    | D      | DS     | N/A    |
| Non-financial agenda distortion               | N/A    | D      | D      | D      |
| Channel contamination                          | D      | D      | D      | D      |

Notes:
- This is a default-action guide; override only when evidence artifacts are unusually strong (e.g., logs, photos, reproducible tests).
- For Type A, most filters are about misuse: do not treat marketing claims as performance evidence.

---

## Minimum evidence requirements (risk-based: sources and variety)

### Baseline (low-stakes / narrow claims)
Minimum:
- **4 distinct sources**
- **2 source types** (A/B/C/D)
- At least **1 non-official** source (B/C/D) unless the claim is purely documentary

### Standard (purchase decisions and reliability assertions)
Minimum:
- **7 distinct sources**
- At least **3 of the 4 source types** when feasible
  - A is usually required for specs/compatibility boundaries
  - D is usually required for reliability/usability risk
  - At least one of B or C should be present for comparative evaluation
Exception:
- If credible Type D evidence is not meaningfully available, proceed with A + B/C, explicitly downgrade confidence, and state the missing evidence.
Independence:
- At least **3 sources must be clearly independent** (see “distinct source” definition)

### High-impact (expensive, high-variance, or safety-adjacent categories)
Minimum:
- **9–12 distinct sources**
- Strong preference for cross-type triangulation (A + (B/C) + D is typical)

### Constrained markets (niche or new products)
Hard floor:
- **4 distinct sources**, **2 types**, and **one non-official** source (B/C/D)
Requirement:
- Explicit confidence downgrade and a statement of missing evidence and how to resolve it

---

## Crowdsourced “pattern detection” rubric (avoid treating noise as signal)

### Recurring issue (actionable risk signal)
Require:
- **>= 3 independent reports** describing substantially the same symptom, AND
- at least **one** of:
  - reports span **>= 2 platforms**, OR
  - reports include **evidence artifacts** (photos/logs/screenshots)

### Widespread issue (strong risk signal)
Require:
- **>= 10 reports** or sustained discussion across multiple threads/platforms, OR
- an official acknowledgement (firmware notes, support bulletin, recall), OR
- a respected publication/individual corroborates the failure mode

### Channel-contaminated issue (do not treat as product defect yet)
If many reports are tied to third-party marketplace sellers or packaging anomalies:
- classify as channel contamination and route to `seller_instructions.md`

Rule:
- Do not estimate “failure rates” from crowdsourced posts. Use language like:
  - “recurring pattern,” “widespread reports,” “unclear prevalence,” “channel-contaminated.”

---

## Agenda salvage rules (how to keep useful claims without swallowing the narrative)

When a source triggers Filter 12A or 12B:
- Only retain **testable/objective** claims (ports, standards, benchmarks, documented constraints).
- Do NOT retain broad interpretive conclusions unless corroborated by independent sources.
- Require at least **one corroborating source** clearly outside the same narrative ecosystem.

---

## Extracting claims (turn review content into evidence)

For each meaningful claim, capture:
- Claim statement
- Claim type: Objective / Semi-objective / Subjective
- Context: model/SKU, firmware, environment, timeframe
- Evidence basis: measured / observed / asserted
- Confounds: setup variability, unit variance, user error likelihood

Rule:
- Do not convert subjective claims into a single “truth.” Represent them as conditional preferences.

---

## Weighting and aggregation (how to form conclusions)

- Type A: high for documented constraints; low for performance/value
- Type B/C: high when methodology + comparators exist; otherwise medium if calibrated
- Type D: high for repeated failure modes/support friction; low for comparative performance without context

Triangulation:
- For important decision claims, require at least **2 independent sources**, ideally across types.
- If not available, mark as uncertain and state what would resolve it.

---

## What to deliver to callers (low-level contract)

No fixed output template is required, but any conclusion based on reviews must include:
- What was evaluated (exact model/SKU and key variants if applicable)
- Key consensus points (2–6 bullets)
- Key negatives / failure modes (explicit)
- Confidence labels per major claim: Confirmed / Likely / Mixed / Unclear
- Any incentive/agenda caveats that materially affect trust
- What remains unverified and how to verify it

---

## Integration notes

- `research_sources.md` should deep-link here for: review authenticity, weighting, aggregation, agenda filtering, and pattern detection.
- Other workflows should reference `research_sources.md` rather than duplicating this file.
- When review evidence indicates channel contamination, route the conclusion to `seller_instructions.md`.
