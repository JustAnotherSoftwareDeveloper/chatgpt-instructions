# Product Hierarchy

## Purpose
Define the Shopping inheritance context used by every workflow and the merge/override semantics by which product context specializes generic workflow behavior.

Resolve one chain:

`Base -> optional Class -> optional Category -> optional Type`

Intermediate levels may be skipped when the natural hierarchy calls for it.

## Level semantics
### Base
Universal Shopping behavior. Always active.

### Class
A broad specialization justified only when it provides behavior reusable across multiple downstream product families.

Do not create a Class merely to organize names.

### Category
An optional intermediate specialization that factors behavior shared by multiple Types or is useful as a terminal research context.

A Category may inherit from Base or a Class.

### Type
The narrowest reusable product-kind specialization that materially changes research, evaluation, pricing, fit, or workflow behavior.

A Type is not a SKU, brand, color, minor form factor, marketing label, or arbitrary retailer category. A Type may inherit from Base, a Class, or a Category.

## Hierarchy contributions
Each active Class / Category / Type may contribute only the behavior it genuinely owns through one or more of these forms:

1. **Shared domain behavior** - product-domain rules that apply regardless of workflow.
2. **Shared-authority selections** - named sections from `criteria.md`, `source_playbooks.md`, `pricing.md`, or another shared authority when that authority explicitly supports hierarchy-specific sections.
3. **Workflow merges** - additive domain behavior for a named concern in the active generic workflow.
4. **Workflow overrides** - surgical replacement of one explicitly named inherited workflow rule or sub-contract for this product context.

A hierarchy level does not need to contribute to every workflow. Omit empty or artificial contribution sections.

## Specialized-authority structure
Executable behavior in a specialized Class / Category / Type authority must live under one of:
- **Shared domain behavior**;
- a named workflow **Merge**;
- a named workflow **Override**.

Purpose, explanatory, and Boundary sections may describe ownership, but must not introduce otherwise-unclassified executable behavior.

Do not create free-floating sections such as `Research emphasis`, `Research interpretation`, or `Pricing notes` when the instructions actually belong to a shared authority or named workflow contribution.

## Merge semantics
A **Merge** adds product-domain behavior to the inherited workflow concern without disabling inherited behavior.

Use Merge for additions such as:
- extra candidate/finalist fields;
- extra hard-gate checks;
- domain-specific decision questions;
- extra market distinctions;
- additional vendor dimensions;
- additional tier-validity checks;
- additional synthesis or user-fit reasoning.

Inherited behavior remains active unless a separate explicit Override replaces a specific rule.

## Override semantics
An **Override** replaces one named inherited rule or sub-contract because leaving that rule active would produce the wrong behavior for this product context.

Every Override must identify its target precisely enough to know what is replaced, for example:
- `Override: Product Research -> Market segmentation -> primary segmentation model`
- `Override: Pricing Tiers -> Tier construction -> linear-ladder assumption`
- `Override: Product Research -> Scope and decision model -> default primary differentiators`

Avoid broad targets when a narrower rule can be named. `Override: Product Research` or `Override: Pricing` is invalid because it does not identify the replaced concern.

An Override affects only its named target. Unmentioned inherited workflow behavior remains active.

Overrides may not weaken or replace rules owned by another canonical authority, including:
- research modes/evidence standards in `research_sources.md`;
- review interpretation in `reviews.md`;
- seller/channel risk in `seller_instructions.md`;
- reusable price-state/value definitions in `pricing.md`;
- reusable criterion definitions in `criteria.md`;
- source-discovery ownership/boundaries in `source_playbooks.md`;
- safety/legal constraints.

Prefer Merge. Use Override only when additive guidance would leave a materially wrong inherited rule active.

## Child-delta rule
Inheritance is the default. A child authority should contain only behavior that is new at that level.

- If a parent Shared rule or Merge should continue unchanged, the child says nothing.
- If a child adds behavior to the same workflow concern, use a Merge containing only the delta.
- If a child replaces the same named inherited target, use an Override.
- Do not restate parent criteria, identity checks, tier dimensions, vendor fields, or Quick Check questions merely to show that they still apply.

When a child Overrides the **same named target** as its parent, the parent's target is replaced for that branch. Therefore:
- use Merge, not Override, when the child wants the inherited target plus extra behavior;
- if a true replacement is intended, the child Override must be complete enough for that target and must not silently rely on parent content it just replaced.

## Effective-workflow inheritance
Apply active hierarchy levels from general to specific:

`Base -> Class -> Category -> Type`

For the active workflow:
1. start from the generic workflow contract;
2. apply the active Class contributions;
3. apply the active Category contributions;
4. apply the active Type contributions.

At each level:
- apply any explicit Override to its named target;
- then apply Merge instructions to the resulting effective concern.

A more-specific Override wins over a less-specific Override only for the same named target. It does not erase sibling rules, unrelated merges, or other workflow sections.

A hierarchy authority should not silently mutate a workflow through unlabeled prose. Product-domain behavior that applies across workflows belongs under Shared domain behavior; workflow-specific behavior belongs under a named Merge or Override for that workflow.

## Resolution guidance
1. Use explicit product wording or a confidently established named-model identity first.
2. Prefer the deepest entry whose product meaning is actually supported.
3. Do not force a Type merely because one exists; broader parent contexts are valid terminal resolutions.
4. Do not invent missing intermediate levels. If a Type naturally inherits directly from a Class or Base, use that relationship.
5. If two plausible entries are on the same inheritance chain, choose the more specific one only when the request or product identity supports it.
6. If materially different branches remain plausible and the distinction changes the research, ask one focused question or stay at the deepest safe common parent.
7. For multiple materially different product targets, resolve each independently.

## Inheritance behavior
A child:
- inherits applicable parent guidance;
- may add shared domain behavior;
- may select additional shared-authority sections;
- may Merge into named workflow concerns;
- may Override explicit inherited workflow rules within its product domain;
- should not restate detailed parent or shared-authority rules merely for emphasis.

If an entry names shared-authority sections, apply those sections in addition to inherited sections. If it names specialized files, load those files while the level is active.

Keep hierarchy entries concise. Substantial domain knowledge and workflow contributions belong in specialized authority files.

---

## Base
Always active.

Apply:
- `base.md`.

---

## Class: Home & Kitchen
Parent: Base

Use when:
- the purchase is primarily household or kitchen equipment, tools, furnishings, or durable goods and Home/Kitchen-specific ownership concerns materially affect the decision.

Optimize:
- practical household fit;
- durable everyday ownership;
- ergonomics, maintenance, storage, and material suitability where relevant.

Apply:
- Home & Kitchen section of `criteria.md`;
- Home & Kitchen section of `source_playbooks.md`;
- Home & Kitchen section of `pricing.md`.

Load:
- `class_home_kitchen.md`.

---

## Category: Kitchen Knives
Parent: Home & Kitchen

Use when:
- kitchen cutlery characteristics such as blade geometry, grind, steel/heat treatment, edge behavior, sharpening, maintenance, knife ergonomics, or provenance materially affect the purchase.

Optimize:
- cutting performance appropriate to use;
- durability and maintenance fit;
- geometry/steel/heat-treatment balance rather than spec-sheet prestige;
- trustworthy product identity and provenance.

Apply:
- Kitchen Knives section of `criteria.md`;
- Kitchen Knives section of `source_playbooks.md`;
- Kitchen Knives section of `pricing.md`.

Load:
- `category_kitchen_knives.md`.

---

## Type: Chef's Knife
Parent: Kitchen Knives

Use when:
- the target is a general-purpose chef's knife;
- the target is a gyuto-style knife serving the same primary general-purpose role;
- a named model is confidently known to be this product type even if the user does not explicitly say "chef's knife".

Optimize:
- primary-knife versatility;
- fit to the user's cutting motion, board, hand, food mix, and maintenance tolerance;
- geometry, profile, length, weight, and balance as an integrated tool.

Apply:
- Chef's Knife section of `criteria.md`;
- Chef's Knife section of `source_playbooks.md`;
- Chef's Knife section of `pricing.md`.

Load:
- `type_chefs_knife.md`.

## Expansion rule
Add new Classes, Categories, and Types only after identifying:
- the shared behavior they own;
- the parent they naturally inherit from;
- which workflow concerns, if any, genuinely need Merge or Override behavior.

Do not migrate the legacy taxonomy mechanically and do not add workflow contributions merely to fill a template.
