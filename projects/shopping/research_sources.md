# research_sources.md
# Research Source Evaluation (admissibility + weighting) — policy module

## 0) Scope, ownership, and module links

### Purpose
This file defines how to **find, filter, admit, and weight** sources used to support claims during product research and pricing-tier work.

### This file OWNS
- Source taxonomy (what kinds of sources exist, what they are best for)
- A two-step procedure: **admissibility** then **weighting**
- Minimum source count and source variety requirements (defaulting to Mode A)
- Claim-type evidence minimums (what evidence is acceptable for what claims)
- Recency / versioning rules (when “newer matters,” and why)
- Conflict resolution rules (how to handle disagreements between sources)
- Requirements for attribution (mapping claims to supporting sources)

### This file DOES NOT OWN
- How to read/interpret review content or detect manipulation rhetoric:
  - Owned by `reviews.md`
- Seller/channel legitimacy, return-trap risk, counterfeit channel risk:
  - Owned by `seller_instructions.md`
- Workflow steps and output formatting:
  - Owned by `product_research.md`, `pricing_tiers.md`, and templates

### Mandatory routing links
- If a source is a **review** (any kind): apply `reviews.md` for review-reading rules.
- If a source is a **seller listing / store page**: apply `seller_instructions.md` for seller/channel legitimacy and purchase risk.

---

## 1) Definitions: source, entity, and “distinct”

These definitions exist to make minimum source requirements enforceable.

- **Source (artifact):** a specific document/page/video/post/thread.
- **Entity (publisher/author):** the party responsible for the source (manufacturer, publication, creator, forum user, retailer).
- **Distinct sources rule:** “N distinct sources” means **N distinct entities** by default.
  - Multiple URLs from the same entity do not count as distinct sources.
  - Syndicated or duplicated content counts **once** (the original entity).

---

## 2) Operating modes (default: Mode A)

Modes scale diligence without changing the core principles.

### Mode A: Full research (DEFAULT)
Use when:
- comparing multiple products or making a purchase recommendation
- building pricing tiers
- the user asks for “best,” “top picks,” “shortlist,” or “compare”

Default minimums:
- **7 distinct entities** (Section 7), meeting source variety requirements.

### Mode B: Quick validation (specific product / narrow question)
Use when:
- a specific product is already chosen and you’re sanity-checking (fit, compatibility, known issues)
- the user asks a narrow verification question

Default minimums:
- **3–5 distinct entities**, still respecting claim-type evidence minimums.
- Must include primary/spec evidence when the claim is about objective specs.

### Mode C: Sparse coverage / niche
Use when:
- credible sources are genuinely limited

Default minimums:
- Use the best available sources, but explicitly add a **Coverage limitations** note:
  - what couldn’t be verified
  - what would change the conclusion if found

Note:
- Mode selection belongs to workflows; this file defines the standards per mode.
- If not specified, assume Mode A.

---

## 3) Procedure: admissibility first, then weighting

### Step 1: Admissibility
Create:
- `Included sources` (admissible)
- `Excluded sources` (inadmissible) with a one-line reason

### Step 2: Weighting
Assign a confidence weight to each included source using Section 6.

Rule:
- Weighting cannot “rescue” an inadmissible source.

---

## 4) Core principles

- Prefer **primary** and **method-based** sources when they exist.
- Triangulate: do not rely on a single non-primary source for meaningful conclusions.
- Keep claims appropriately scoped to evidence strength.
- Separate:
  - **Objective claims** (specs, compatibility, standards) from
  - **Empirical claims** (performance, reliability, durability) from
  - **Subjective claims** (comfort, taste, preference).

---

## 5) Source taxonomy (what each source type is best for)

If a source is a review, apply `reviews.md` for review-reading rules.
If a source is a seller listing/store page, apply `seller_instructions.md` for legitimacy and purchase risk.

### A) Primary documents (manufacturer / vendor-primary)
Examples:
- manuals, datasheets, spec sheets, compatibility lists, firmware notes, warranty terms

Best for:
- objective specs, compatibility constraints, supported features, warranty terms

Caveat:
- Primary sources are authoritative for what the manufacturer claims/supports, not necessarily for real-world performance.

### B) Standards / regulatory / certification bodies (when applicable)
Examples:
- standards bodies, certification registries, recall databases, safety guidance

Best for:
- safety/compliance claims, recall status, certification verification

### C) Respected publications (method-based outlets)
Examples:
- outlets known for test methodology, measurements, or structured evaluation

Best for:
- performance comparisons, measured claims, repeatable evaluations, editorially controlled testing

### D) Respected individuals (journalists/experts/creators)
Examples:
- individuals with clear domain competence and transparent methodology

Best for:
- nuanced tradeoffs, hands-on insights, edge cases, category expertise
- useful when method-based publications do not cover the category well

### E) Crowdsourced owner reports (owner-centric)
Examples:
- verified-purchase retailer/platform reviews
- owner groups where posts are predominantly first-hand ownership reports

Best for (unique value):
- reliability patterns, unit variance, long-term durability, firmware regressions, fitment reality, common failure modes
- “what breaks,” “what’s annoying,” and “what changed over time”

Caveat:
- Treat as signal aggregation, not proof. Use breadth and consistency to increase confidence.

### F) Forums / communities (discussion-centric)
Examples:
- enthusiast forums, subreddit threads, Q&A communities

Best for:
- troubleshooting patterns, long-term ownership notes, niche edge cases
- often the fastest signal for newly emerging issues

Caveat:
- Higher noise and more speculation than owner-centric sources; require triangulation and be explicit about uncertainty.

### G) Retailer listings / store pages (seller sources)
Best for:
- price, availability, shipping terms, return policy facts (where clearly stated), and identifying exact variants/SKUs

Mandatory:
- Apply `seller_instructions.md` for seller/channel legitimacy and purchase-risk handling.

---

## 6) Weighting framework (soft confidence weights)

Weight affects prioritization and confidence, not admissibility.
Use a simple qualitative weight: **High / Medium / Low**.

Primary dimensions (apply to included sources):
- **Method transparency**
  - Are measurements/test methods described?
- **Independence / incentives clarity**
  - Are sponsorships, affiliate incentives, or relationships disclosed and bounded?
- **Specificity / reproducibility**
  - Model numbers, versions, conditions, and concrete observations
- **Domain competence**
  - Is the entity credible for this category (avoid generalists for niche testing)?
- **Breadth**
  - sample size, coverage across units/conditions (especially for crowdsourced reliability)
- **Temporal relevance**
  - is the claim sensitive to version changes? (Section 9)
- **Triangulation consistency**
  - aligns with other high-quality sources (or conflicts with them)

Guidance:
- High weight typically requires either:
  - primary/standards evidence for objective claims, or
  - method-based testing with clear methodology for empirical claims, or
  - broad, consistent crowdsourced signals for reliability/durability claims.

---

## 7) Minimum sources and variety requirements (Mode A default)

### Mode A minimums (DEFAULT)
Require **7 distinct entities** with variety constraints.

#### 7.1 Primary / standards requirement (when available)
- **At least 1** primary document OR standards/certification source **when available/applicable**.

Fallback if not available:
- Substitute **2** additional independent non-primary entities, and include a Coverage limitations note explaining what primary/standards evidence was unavailable.

#### 7.2 Empirical methodology requirement
- **At least 1** method-based publication OR respected individual with transparent methodology.

#### 7.3 Real-world signal requirement (default)
- **At least 2** crowdsourced/community entities from **different platforms**.

Substitution rule (when real-world sources are scarce or low-value for the claim type):
- For spec-driven or purely objective decisions, replace the real-world signal requirement with:
  - additional primary/standards sources (preferred), or
  - additional method-based publications, and document why crowdsourced signal was not useful/available.

#### 7.4 Seller sources requirement (conditional; only when price/availability is in scope)
Require seller sources only when **price/availability is in scope**, such as:
- pricing tiers workflow
- explicit purchase intent (“where should I buy,” “best price,” “in stock,” “return policy”)
- the user asks for current pricing

If in scope:
- **At least 2** seller entities for price/availability
- seller evaluation must follow `seller_instructions.md`

If not in scope:
- seller sources are optional and should not be forced.

Remaining sources:
- any admissible categories, but must be distinct entities.

### Mode B minimums (quick validation)
Require **3–5 distinct entities**, typically:
- 1 primary/spec source (if objective claims are involved)
- 1 credible empirical source (publication or respected individual)
- 1 crowdsourced/community signal when reliability/real-world issues are relevant
- seller sources only if “where to buy / current price” is in scope

### Mode C minimums (sparse coverage)
Use the strongest available sources.
Mandatory: include a **Coverage limitations** note.

---

## 8) Claim types and evidence minimums (no single-source rule)

### General rule: no single-source conclusions
Do not base meaningful conclusions on a single non-primary source.

Explicit exceptions:
- **Objective specs / compatibility:** primary documents can be sufficient when unambiguous
- **Safety/compliance / recalls:** standards/regulatory/recall databases can be sufficient when directly applicable

Additional boundary:
- A single **seller listing/store page** is never sufficient for an objective spec claim unless corroborated by primary documents (or multiple independent primary-like sources where primary is unavailable).

### Claim types

#### A) Objective specs / compatibility
Minimum evidence:
- Prefer primary documents first.
- Retailer listings may support spec facts only when consistent across multiple reputable sellers and not contradicted by primary sources.

#### B) Performance claims (measured or repeatable)
Minimum evidence:
- Prefer method-based publications.
- If absent, require multiple independent sources with transparent methodology and scope the claim conservatively.

#### C) Reliability / durability
Minimum evidence:
- Require broad crowdsourced/community signals (diverse platforms) plus any long-term testing when available.
- Prefer sources that mention timeframe, usage intensity, and versions (firmware/app) when relevant.

#### D) Safety / compliance
Minimum evidence:
- Standards/regulatory/certification/recall + primary documents.
- Crowdsourced signals are allowed only as early-warning, not as proof.

#### E) Subjective experience (comfort, taste, preference)
Minimum evidence:
- Use diverse crowdsourced signals plus transparent reviewers.
- Avoid single-source “best” claims; scope as “likely fit for X preferences.”

---

## 9) Recency and versioning rules (clarified)

Recency matters differently by category and claim type.

### Temporal sensitivity concept
Classify the claim as:
- **High temporal sensitivity**
  - firmware/app-driven behavior, platform compatibility, subscription/service changes, active product revisions
- **Low temporal sensitivity**
  - stable physical characteristics, long-established materials, mature categories without frequent revisions

Rules:
- For high temporal sensitivity claims:
  - prioritize recent sources and sources that mention **versions/revisions**
  - deweight older sources unless they remain version-relevant
- For low temporal sensitivity claims:
  - prioritize methodology quality and breadth over recency

When sources disagree, check:
- model revisions, firmware/app versions, silent component swaps, and regional variants.

---

## 10) Conflict resolution rules (when sources disagree)

When sources disagree, first classify the conflict:
- **Spec conflict:** resolve via primary documents/standards sources
- **Performance conflict:** compare methodology, test conditions, and measurement rigor
- **Reliability conflict:** compare sample sizes, timeframes, usage intensity, and versioning

Required step:
- State the most plausible reason(s) for disagreement (revision drift, methodology, sample bias, incentives).

If unresolved:
- Narrow the claim, present uncertainty explicitly, and avoid overstating confidence.

---

## 11) Attribution requirements (claim-to-evidence mapping)

For any non-trivial conclusion, map claims to evidence:
- Identify which source(s) support each key claim.
- Avoid “citation dumping” without showing what each source contributed.
- If a claim is weakly supported, say so.

Minimum fields to capture (templates decide formatting):
- Source entity name
- Source type (taxonomy category)
- Publish date if available; access date if needed
- What claim it supports (one line)

---

## 12) Interface contract for higher-level workflows

Workflows invoking this module should provide:
- product class/type context (from `product_types.md`) when available
- whether the task is Mode A/B/C (or allow default Mode A)
- whether price/availability is in scope (to trigger conditional seller-source requirements)

This module provides back to workflows:
- included/excluded source lists (with reason for exclusions)
- weighted confidence guidance (High/Medium/Low per source)
- minimum source compliance status (met vs not met)
- conflict notes and any coverage limitations
