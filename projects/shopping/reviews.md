# Review Interpretation Authority

## Purpose
Own interpretation of expert reviews, individual reviewers, owner reviews, retailer reviews, forums, and community evidence after `research_sources.md` establishes that the source can contribute.

## 1) Review evidence is useful for
- hands-on performance/usability;
- long-term ownership behavior;
- recurring failure or QC patterns;
- setup/maintenance friction;
- preference-sensitive fit;
- edge cases not captured by primary documentation.

Do not treat raw sentiment or star averages as direct measurements of product quality.

## 2) Evaluate review evidence on these dimensions
### Identity
Tie the review to the correct model/generation/size/region/firmware/revision when those distinctions matter. Ambiguous identity invalidates variant-sensitive claims.

### Domain competence
Use a reviewer for the claims they are competent to make. Generalists may be useful for usability but weak for niche technical conclusions.

### Method and specificity
Prefer concrete use/test conditions, direct comparators, measurements or reproducible observations when applicable, exact failure modes, and ownership duration appropriate to the claim.

### Independence and incentives
Consider affiliate links, sponsorships, free samples, retailer/manufacturer relationships, selective comparison sets, and disclosure quality.

Incentives do not automatically invalidate original evidence; they increase the need for transparent support and independent corroboration.

### Time horizon
Match the horizon to the claim. Day-one reviews are weak evidence for durability, long-term wear, repeated sharpening behavior, battery aging, or software stability.

### Corroboration
Independent recurring observations matter more than one vivid anecdote.

## 3) Source-specific handling
### Method-based publications
Use when category competence, methodology, and comparative context are visible. Discount shallow affiliate roundups, category mismatch, and conclusions broader than test conditions.

### Specialist individuals / creators
Use for depth and niche expertise when they show competence, comparison context, concrete evidence, incentives, downsides, and uncertainty. Discount certainty theater or sponsored framing unsupported by shown experience.

### Owner / retailer reviews
Use for defects, QC variance, longevity, workflow friction, and maintenance burden. Weight detailed first-hand reports far above generic praise/complaints.

### Forums / communities
Use for niche expertise, troubleshooting, long-term experience, emerging issues, and hidden constraints. Separate first-hand reports from speculation, repetition, folklore, and preference norms.

## 4) Exclude vs discount
### Exclude for the affected claim when
- review is the wrong model/variant for a variant-sensitive claim;
- content is copied/syndicated and contributes no independent evidence;
- technical claim comes from a source with neither competence nor method/context;
- the review contains materially contradictory/hallucinated product facts that undermine identity;
- undisclosed incentive/manufacturer control makes a source falsely appear independent and the claim cannot be independently salvaged.

### Strongly discount when
- methodology is opaque for a measurable claim;
- ownership horizon is too short for the claim;
- strong sponsorship/affiliate framing narrows comparison without justification;
- reviewer repeatedly omits category-critical constraints;
- coordination/astroturf signals are plausible;
- content is mostly paraphrase/SEO aggregation rather than original work.

### Do not automatically discount solely because
- the source uses affiliate links but performs substantial original work;
- a sample was provided and clearly disclosed;
- tone is enthusiastic/negative while underlying observations remain concrete;
- prose seems "AI-ish" without duplication, factual, or behavioral evidence of manipulation.

## 5) Pattern thresholds
These thresholds classify **signal strength**, not prevalence.

### Isolated report
One first-hand report with no independent corroboration.

### Recurring signal
Treat an issue/behavior as recurring only when:
- at least **3 independent first-hand reports** describe substantially the same phenomenon; and
- at least one is true:
  - reports span **2 or more independent platforms/populations**;
  - credible evidence artifacts exist (photos, logs, measurements, consistent physical symptoms);
  - a competent independent reviewer reproduces the issue.

### Strong / widespread signal
Use stronger language only when at least one is true:
- **10 or more independent reports** distributed across multiple threads/platforms/populations;
- a competent independent reviewer reproduces the failure mode in a way consistent with owner reports;
- manufacturer/service action acknowledges the issue through a bulletin, repair program, revision, recall, warranty change, or similar response.

Never convert these thresholds into a failure percentage without representative denominator data.

Preferred wording:
- isolated report;
- recurring owner reports;
- consistent cross-source pattern;
- widespread discussion but unclear prevalence;
- official acknowledgement.

## 6) Pattern diagnostic record
When a recurring/strong issue materially affects a recommendation, normalize the pattern internally instead of merely counting mentions.

Capture where available:
- exact symptom/failure behavior;
- affected model/variant/revision;
- severity and user consequence;
- ownership age / use duration / use intensity;
- operating/environmental conditions;
- whether reports appear genuinely independent or trace to one original story;
- evidence artifacts/reproduction;
- seller/channel contamination possibility;
- whether the issue changes across revisions/firmware/batches;
- manufacturer/service acknowledgement or corrective action;
- current status: active, uncertain, mitigated, fixed, revision-specific, or obsolete.

A recurring pattern whose conditions do not resemble the user's use case may be less decision-relevant than a rarer but directly applicable issue.

## 7) Narrative-origin check
Before calling multiple posts independent, determine whether they are:
- separate first-hand experiences;
- reposts/quotes of one original incident;
- reactions to one viral story;
- summaries of the same reviewer/test;
- separate reports with independently described symptoms/timelines.

Do not count social amplification as independent corroboration.

## 8) Hidden-constraint check
For domain-specialist reviews, assess whether the source recognizes category-critical constraints.

A reviewer who repeatedly ignores known constraints may still contribute narrow observations but should be downweighted for broad conclusions.

Examples include:
- compatibility/fitment boundaries;
- maintenance requirements;
- revision differences;
- relevant operating conditions;
- category-specific failure modes;
- user technique or environment that materially changes behavior.

Specialized hierarchy authorities define which hidden constraints matter in each domain.

## 9) Method-horizon match
For each review-derived conclusion ask:
- Was the product used long enough for this claim?
- Were the conditions representative of the behavior being claimed?
- Was there a relevant comparator?
- Is the observation directly comparable to evidence for competing products?

Examples:
- a one-week review can establish ergonomics but not multi-year durability;
- a factory-edge test can describe out-of-box sharpness but not long-term sharpening behavior;
- one firmware version may not establish current software behavior.

## 10) Channel contamination
Separate product behavior from seller/channel failures such as:
- wrong item/variant;
- opened/used sold as new;
- missing accessories;
- suspected counterfeit;
- shipping damage;
- seller return/RMA problems.

Do not count these as product-quality failures until the distinction is reasonably clear. Route channel conclusions to `seller_instructions.md`.

## 11) Preference vs defect
Distinguish:
- objective defect/inconsistency;
- measurable tradeoff;
- maintenance expectation;
- technique mismatch;
- personal preference;
- community norm.

Preserve the observation and map it to the user's preferences rather than converting it into universal quality.

## 12) Review synthesis
When review evidence materially affects the recommendation:
- summarize the recurring pattern rather than individual drama;
- state conditions/time horizon/revision when they matter;
- state disagreement or selection bias when material;
- distinguish established from plausible;
- connect the pattern to a concrete user consequence;
- distinguish symptom evidence from hypothesized cause unless the mechanism is established.

Normal output should not include a manipulation report unless it changes the decision. `audit.md` may expose deeper handling.

## Boundary
`research_sources.md` owns general admissibility, coverage, independence, comparability, and confidence; `seller_instructions.md` owns seller/channel risk; hierarchy authorities own domain interpretation.