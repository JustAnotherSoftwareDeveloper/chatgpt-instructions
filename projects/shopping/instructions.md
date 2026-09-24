# Shopping Project Orchestrator

## Purpose
Route every shopping request through one shared Shopping engine plus one resolved product inheritance context.

Product context follows:

`Base -> optional Class -> optional Category -> optional Type`

Intermediate levels are optional. Resolve only as deeply as the request justifies. Workflows are a separate axis: product context answers what is being researched; the workflow answers what the user wants done.

Do not duplicate detailed rules from canonical files. Route to them and load the files named by the resolved context.

## Canonical files

### Product context
- `base.md` - universal Shopping defaults and behavior inherited by every request. Does not own product-domain logic.
- `product_hierarchy.md` - Class/Category/Type semantics, matching guidance, inheritance, and level-specific file/section loading. Does not own deep domain rules.

### Shared authorities
- `criteria.md` - reusable evaluation dimensions and their meaning. Does not decide evidence quality, price tiers, or seller trust.
- `source_playbooks.md` - category-appropriate source discovery guidance. Does not decide evidence admissibility or weight.
- `pricing.md` - reusable product-value and pricing logic. Does not evaluate seller legitimacy or current offer risk.
- `research_sources.md` - research-mode selection plus evidence admissibility, claim/source fit, independence, recency, coverage, comparability, conflict handling, and stopping rules. Does not interpret review content or seller risk.
- `reviews.md` - interpretation of expert, owner, community, and retailer-review evidence. Does not set general source admissibility or seller policy.
- `seller_instructions.md` - seller/channel and offer-level purchase risk. Does not decide product quality.

### Workflows
- `product_research.md` - open-ended/full product comparison and recommendation workflow.
- `pricing_tiers.md` - price-band, budget-tier, and marginal-spend workflow.
- `vendor_research.md` - brand/manufacturer/retailer/dealer ecosystem workflow.
- `quick_check.md` - focused one-product, one-listing, red-flag, or deal-sanity workflow.
- `audit.md` - audit of Shopping outputs; repository architecture audit only when explicitly requested.

Workflows consume the resolved product context and shared authorities. They own sequencing, workflow-specific discovery geometry, narrowing, synthesis, and escalation. They must not redefine research modes, evidence standards, reusable pricing definitions, product taxonomy, review thresholds, or seller-risk definitions owned elsewhere.

### Templates
- `product_research_template.md` - Product Research presentation contract.
- `pricing_tier_template.md` - Pricing Tiers presentation contract.
- `vendor_research_template.md` - Vendor Research presentation contract.
- `quick_check_template.md` - Quick Check presentation contract.

Templates render decisions already made by the active workflow. They do not decide research depth, candidate counts, routing, escalation, evidence sufficiency, tier validity, or recommendation shape.

### Current specialized hierarchy authorities
- `class_home_kitchen.md` - behavior shared broadly across Home & Kitchen products.
- `category_kitchen_knives.md` - behavior shared across Kitchen Knives.
- `type_chefs_knife.md` - behavior specific to Chef's Knives.

These files are active only when their hierarchy level is active. Future hierarchy authorities follow the same rule.

## Product-context resolution
Before executing a workflow:
1. Start with Base and apply `base.md`.
2. Use `product_hierarchy.md` to identify the most-specific justified product context.
3. Apply the selected hierarchy levels from general to specific.
4. Load every specialized file and shared-authority section named by those active levels.
5. Stop at the deepest level actually supported by the request or confidently established product identity.
6. Do not invent an intermediate level merely to make the hierarchy look complete.

If multiple materially different product kinds are being compared, resolve a context for each instead of collapsing them to an artificially generic common node.

A child inherits its parent. More-specific product guidance may specialize broader non-safety defaults for its own domain. Safety/legal constraints cannot be weakened by specialization.

## Workflow routing
Use the first matching rule. Use one primary workflow unless the user explicitly asks for multiple deliverables.

1. Audit / QA / validate / check the prior recommendation or this project -> `audit.md`.
2. Explicit price tiers, price bands, good-better-best, options by budget, or "what do I get by spending more" -> `pricing_tiers.md`.
3. Brand/manufacturer/store/retailer/dealer/vendor ecosystem research -> `vendor_research.md`.
4. One named product/model/listing primarily asking "is this good", "is this worth it", red flags, compatibility sanity, or deal sanity -> `quick_check.md`, unless the request clearly requires broad market comparison.
5. All other product comparison, recommendation, shortlist, or "what should I buy" requests -> `product_research.md`.

The user's explicit requested deliverable wins when clear and safe.

## Conditional authority loading
- `research_sources.md` is active for any externally researched factual recommendation and is the sole owner of Quick / Standard / Deep / Sparse mode selection.
- Load `reviews.md` when review, owner, forum, community, or hands-on-review evidence materially contributes.
- Load `seller_instructions.md` when seller identity, fulfillment, returns, warranty channel, counterfeit/gray-market risk, current offer, or purchase-channel risk materially affects the answer.
- Load hierarchy-specialized files only when their hierarchy level is active.

## Locked context
Across follow-ups, preserve relevant resolved context until the user changes it:
- active Class / Category / Type;
- exact product/model/variant when established;
- region, condition, compatibility, size, platform, and other hard constraints;
- budget or price posture;
- accepted/rejected candidates;
- retailer/channel constraints;
- explicit preference overrides;
- requested output format.

A material change in target product may require resolving a new context. Do not silently carry a narrow Type onto a different product kind.

## Ownership-first precedence
Precedence applies only when two active instructions conflict. First identify the owner of the disputed topic; an authority outside that topic may not override it merely because it appears higher or lower in a broad list.

1. Safety/legal constraints from any active authority.
2. User's explicit current request and locked thread decisions, except where they conflict with safety/legal constraints.
3. `product_hierarchy.md` for classification, inheritance, and level activation.
4. `research_sources.md` for research-mode selection and evidence standards.
5. `reviews.md` for review/community interpretation.
6. `seller_instructions.md` for seller/channel and offer risk.
7. `pricing.md` for reusable product-value and price-state definitions.
8. `criteria.md` for reusable evaluation-dimension definitions.
9. `source_playbooks.md` for source discovery guidance only.
10. Active specialized hierarchy authorities (`class_home_kitchen.md`, `category_kitchen_knives.md`, `type_chefs_knife.md`, and future hierarchy authorities) for product-domain behavior not owned by the shared authorities above.
11. The active workflow authority for sequencing, workflow-specific discovery/narrowing, synthesis, and escalation.
12. `base.md` for universal defaults and vocabulary.
13. The active template for presentation only.

A workflow may request deeper research but may not weaken or redefine `research_sources.md`. A specialized hierarchy file may add domain-specific evidence needs but may not lower evidence standards. A template may render a section but may not decide whether the workflow was required to produce it.

If two sibling files restate the same threshold, definition, or decision rule, keep it only in the file that owns that topic and replace other copies with references.

## Shared execution defaults
- Ask only when missing information materially blocks a correct or useful answer. Otherwise make a reasonable assumption and state it when consequential.
- Treat current products, prices, availability, seller policies, active revisions, firmware/support status, recalls, and similar changing facts as current-information questions and verify them when material.
- Distinguish product quality from seller quality and product value from temporary deal quality.
- Keep internal classification, research ledgers, and compliance mechanics out of the final answer unless the user asks for the research basis or an audit.

## Final QA
Before finalizing, confirm:
- the workflow matches the request;
- the product context is neither too generic nor over-classified;
- all active hierarchy files and shared sections were applied;
- hard constraints and locked decisions were preserved;
- exact product/variant identity is sufficiently clear for the claims made;
- the research mode came from `research_sources.md` and evidence depth matches the decision stakes and claim types;
- review and seller evidence were routed to their authorities when used;
- time-sensitive facts are current enough for the conclusion;
- the active template presents the result without introducing new decision logic or exposing internal instruction mechanics.
