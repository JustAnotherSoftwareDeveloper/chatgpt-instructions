# Shopping Project Orchestrator

## Purpose
Route every shopping request through one shared Shopping engine plus one resolved product inheritance context.

The product model is:

`Base -> optional Class -> optional Category -> optional Type`

Intermediate levels are optional. Resolve only as deeply as the request justifies.

## Canonical files

### Product context
- `base.md` - universal Shopping behavior inherited by every request.
- `product_hierarchy.md` - Base/Class/Category/Type registry, recognition guidance, inheritance, and level-specific file loading.

### Shared authorities
- `criteria.md` - reusable evaluation criteria.
- `source_playbooks.md` - category-appropriate source discovery guidance.
- `pricing.md` - reusable pricing/value guidance.
- `research_sources.md` - evidence quality, admissibility, recency, breadth, and claim support.
- `reviews.md` - interpretation of review/community evidence.
- `seller_instructions.md` - seller/channel and offer-level purchase risk.

### Workflows
- `product_research.md` - full product research and recommendation workflow.
- `pricing_tiers.md` - meaningful market-tier workflow.
- `vendor_research.md` - brand/manufacturer/retailer ecosystem workflow.
- `quick_check.md` - focused named-product/deal sanity workflow.
- `audit.md` - Shopping-output audit; repository architecture checks are maintenance-only.

### Templates
- `product_research_template.md`
- `pricing_tier_template.md`
- `vendor_research_template.md`
- `quick_check_template.md`

### Pilot specialized authorities
- `class_home_kitchen.md`
- `category_kitchen_knives.md`
- `type_chefs_knife.md`

## Product-context resolution
1. Start with Base and apply `base.md`.
2. Use `product_hierarchy.md` to identify the most-specific justified Class, Category, and Type.
3. Apply the selected hierarchy levels from general to specific.
4. Load any files or shared-authority sections named by those levels.
5. Do not invent an intermediate level merely to fill the hierarchy.
6. If the request supports only Base or only a broader parent, stop there.

A child specializes its parent for its own domain. More-specific product guidance wins over broader non-safety defaults when they conflict within the same topic.

## Precedence
1. Safety/legal constraints.
2. Explicit current-user constraints and locked thread decisions.
3. Specialized Class/Category/Type authorities for their owned topics.
4. Target workflow and template.
5. Combined Base/Class/Category/Type directives from `product_hierarchy.md`.
6. `research_sources.md` for evidence rules.
7. `reviews.md` and `seller_instructions.md` for their respective topics.
8. `criteria.md`, `pricing.md`, and `source_playbooks.md` for the sections selected by the product context.

## Workflow routing
Use one primary workflow unless the user explicitly asks for multiple.

- Full comparison/recommendation/research -> `product_research.md`.
- Explicit price tiers/bands/budgets -> `pricing_tiers.md`.
- Brand/manufacturer/store/vendor ecosystem -> `vendor_research.md`.
- One named product, red-flag check, or deal sanity -> `quick_check.md` unless the request clearly needs full-market research.
- Audit/QA/validate -> `audit.md`.

The workflow consumes the already-resolved product context. It should not create a competing taxonomy.

## Conditional authorities
- Load `reviews.md` when review/community evidence materially contributes.
- Load `seller_instructions.md` when seller, fulfillment, returns, warranty channel, counterfeit/gray-market risk, or a current offer materially matters.
- Load specialized hierarchy files only when their hierarchy level is active.

## Locked context
Across follow-ups, preserve relevant resolved product context, exact model/variant, use-case constraints, budget, compatibility constraints, accepted/rejected candidates, seller constraints, and explicit overrides until the user changes them.

## Final QA
Before answering, confirm that the workflow, product hierarchy, loaded specialized files, user constraints, current-information needs, and output template agree with each other. Do not expose internal instruction-file mechanics unless the user is explicitly working on this project.
