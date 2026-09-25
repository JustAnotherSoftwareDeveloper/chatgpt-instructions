# Evaluation Criteria

## Purpose
Define generic reusable evaluation dimensions and criterion-role semantics that hierarchy registry entries and workflows may apply without restating their meaning.

Criteria identify what should be evaluated. They do not define evidence standards, source discovery, price tiers, review interpretation, seller risk, workflow sequencing, product taxonomy, or domain-specific criterion additions.

Domain-specific evaluation dimensions belong in the active entries of `class.md`, `category.md`, and `type.md` as named Criteria contributions under the composition rules in `product_hierarchy.md`.

## Hierarchy contribution surface
The canonical hierarchy target exposed by this authority is:
- `Criteria -> Evaluation dimensions`

Registry entries may **Merge** additional domain-specific evaluation dimensions into this target. The Merge is additive to the generic dimensions and role semantics below.

This authority exposes no hierarchy Override target. Registry entries may not replace generic criterion-role semantics or silently invent alternate Criteria contribution targets.

## How workflows use criteria
Classify active criteria internally as one of:
- **Hard gate** - failure disqualifies the candidate.
- **Primary differentiator** - likely to change the recommendation among viable candidates.
- **Secondary / tie-breaker** - useful after primary differentiators are resolved.
- **Preference / identity dimension** - ranking depends mainly on user taste, aesthetics, craft, community identity, or another explicitly subjective priority.

The active workflow decides how many criteria should occupy each role. Active hierarchy entries may add domain criteria or specialize their workflow role only through explicit contributions; they do not silently replace these generic role semantics.

## General
### Constraint fit
Whether the product satisfies non-negotiable compatibility, size, platform, use-case, safety, availability, or other hard requirements.

### Functional performance
How well the product performs the job the user actually needs, including relevant operating conditions. Do not substitute headline specifications for demonstrated/practical performance.

### Reliability and durability
Expected consistency, failure modes, wear behavior, repair/replacement burden, and confidence in long-term ownership. Separate recurring patterns from isolated anecdotes and unknown prevalence.

### Usability and ergonomics
Setup burden, control quality, comfort, workflow friction, accessibility, maintenance interaction, and day-to-day fit.

### Compatibility and ecosystem fit
Physical, electrical, software, accessory, consumable, platform, or workflow compatibility where relevant.

### Maintainability and serviceability
Cleaning, routine maintenance, repairability, parts/consumables, sharpening/service needs, update/support posture, and realistic user upkeep.

### Ownership cost
Purchase price plus meaningful required accessories, consumables, subscriptions, maintenance, service, and replacement costs. Do not invent immaterial TCO components.

### Design / aesthetic / identity fit
Use as a first-class criterion when appearance, design language, collector appeal, craft, brand identity, enthusiast credibility, or emotional value is explicit or strongly implied.

### Value
Quality/usefulness received for money across the active criteria and ownership horizon. Value is not synonymous with lowest price.

## Boundary
Product classification, inheritance, and hierarchy composition belong to `product_hierarchy.md`; supported domain nodes and domain-specific criterion additions belong to `class.md`, `category.md`, and `type.md`; evidence belongs to `research_sources.md`; discovery to `source_playbooks.md`; pricing/value to `pricing.md`; review handling to `reviews.md`; seller risk to `seller_instructions.md`; workflow-specific prioritization/counts to the active workflow.
