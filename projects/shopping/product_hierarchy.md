# Product Hierarchy

## Purpose
Define the Shopping inheritance model, registry contract, and Merge/Override semantics by which product context specializes generic Shopping behavior.

Resolve one chain:

`Base -> optional Class -> optional Category -> optional Type`

Intermediate levels may be skipped when the natural hierarchy calls for it.

Actual supported nodes live only in:
- `class.md` for Classes;
- `category.md` for Categories;
- `type.md` for Types.

This file defines how those nodes work. It is not a second registry of supported products.

## Level semantics
### Base
Universal Shopping behavior. Always active through `base.md`.

### Class
A broad specialization justified only when it provides behavior reusable across multiple downstream product families.

Do not create a Class merely to organize names.

### Category
An optional intermediate specialization that factors behavior shared by multiple Types or is useful as a terminal research context.

A Category may inherit from Base or a Class.

### Type
The narrowest reusable product-kind specialization that materially changes research, evaluation, pricing, fit, or workflow behavior.

A Type is not a SKU, brand, color, minor form factor, marketing label, or arbitrary retailer category. A Type may inherit from Base, a Class, or a Category.

## Registry contract
Each node is defined completely in exactly one entry in the registry matching its level.

Every entry must provide:
- a unique canonical node name in its heading;
- `Parent`;
- an explicit `Inheritance` chain from Base through the node;
- enough `Match` guidance to resolve the node without another registry;
- only the domain behavior and contributions genuinely owned by that level.

An entry may also provide `Optimize`, Boundary, explanatory, or other non-executable metadata when useful.

### Atomic-addition rule
Adding a supported node should normally require one edit only:
- add a Class to `class.md`;
- add a Category to `category.md`;
- add a Type to `type.md`.

Do not duplicate the supported-node list in `instructions.md`, this file, shared authorities, or workflow files.

If adding a node requires changing generic hierarchy semantics, workflow contribution surfaces, or another canonical contract, make that separate architectural change explicitly rather than encoding a hidden dependency.

### Retrieval-friendly identity
Each registry entry must be self-identifying. Use the canonical heading form:
- `# CLASS: <name>`;
- `# CATEGORY: <name>`;
- `# TYPE: <name>`.

Keep `Parent` and `Inheritance` adjacent to the heading so a retrieved entry retains its routing context even when the rest of the registry is not in context.

## Hierarchy contributions
Each active Class / Category / Type may contribute only behavior it genuinely owns through one or more of these forms:

1. **Shared domain behavior** - product-domain rules that apply regardless of workflow.
2. **Shared-authority contributions** - additive or explicitly targeted specialization of an extensible concern owned by `criteria.md`, `source_playbooks.md`, `pricing.md`, or another shared authority.
3. **Workflow Merges** - additive domain behavior for a named concern in the active generic workflow.
4. **Workflow Overrides** - surgical replacement of one explicitly named inherited workflow rule or sub-contract for this product context.

A hierarchy level does not need to contribute to every authority or workflow. Omit empty or artificial contribution sections.

## Specialized-entry structure
Executable behavior in a Class / Category / Type registry entry must live under one of:
- **Shared domain behavior**;
- **Shared-authority contributions** using a named Merge or Override target;
- a named workflow **Merge**;
- a named workflow **Override**.

Purpose, Match, Optimize, Inheritance, explanatory, and Boundary sections may describe routing or ownership, but must not introduce otherwise-unclassified executable behavior.

Do not create free-floating sections such as `Research emphasis`, `Research interpretation`, or `Pricing notes` when the instructions actually belong to a shared authority or named workflow contribution.

## Merge semantics
A **Merge** adds product-domain behavior to the inherited named concern without disabling inherited behavior.

Use Merge for additions such as:
- additional criteria/evaluation dimensions;
- domain-specific source-discovery guidance;
- domain-specific value interpretation;
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

An Override affects only its named target. Unmentioned inherited behavior remains active.

Shared-authority Overrides are allowed only when the owning shared authority exposes a replaceable sub-contract or default. They may not replace that authority's canonical vocabulary, safety/evidence semantics, or ownership boundary merely because the registry entry is more specific.

Overrides may not weaken or replace rules owned by another canonical authority, including:
- research modes/evidence standards in `research_sources.md`;
- review interpretation in `reviews.md`;
- seller/channel risk in `seller_instructions.md`;
- generic price-state/value definitions in `pricing.md`;
- generic criterion-role/meaning semantics in `criteria.md`;
- generic source-discovery ownership/boundaries in `source_playbooks.md`;
- safety/legal constraints.

Prefer Merge. Use Override only when additive guidance would leave a materially wrong inherited rule active.

## Child-delta rule
Inheritance is the default. A child entry should contain only behavior that is new at that level.

- If a parent Shared rule or Merge should continue unchanged, the child says nothing.
- If a child adds behavior to the same concern, use a Merge containing only the delta.
- If a child replaces the same named inherited target, use an Override.
- Do not restate parent criteria, identity checks, tier dimensions, vendor fields, source guidance, pricing guidance, or Quick Check questions merely to show that they still apply.

When a child Overrides the **same named target** as its parent, the parent's target is replaced for that branch. Therefore:
- use Merge, not Override, when the child wants the inherited target plus extra behavior;
- if a true replacement is intended, the child Override must be complete enough for that target and must not silently rely on parent content it just replaced.

## Effective-context inheritance
Apply active hierarchy levels from general to specific:

`Base -> Class -> Category -> Type`

For each applicable shared authority and the active workflow:
1. start from the generic authority/workflow contract;
2. apply the active Class contributions;
3. apply the active Category contributions;
4. apply the active Type contributions.

At each level and named concern:
- apply any explicit Override to its named target;
- then apply Merge instructions to the resulting effective concern.

A more-specific Override wins over a less-specific Override only for the same named target. It does not erase sibling rules, unrelated merges, or other workflow/authority sections.

A registry entry should not silently mutate a workflow or shared authority through unlabeled prose. Product-domain behavior that applies across workflows belongs under Shared domain behavior; authority-specific behavior belongs under Shared-authority contributions; workflow-specific behavior belongs under a named Merge or Override for that workflow.

## Resolution guidance
1. Use explicit product wording or a confidently established named-model identity first.
2. Search the three registries for the deepest entry whose product meaning is actually supported.
3. Do not force a Type merely because one exists; broader parent contexts are valid terminal resolutions.
4. Do not invent missing intermediate levels. If a Type naturally inherits directly from a Class or Base, use that relationship.
5. If two plausible entries are on the same inheritance chain, choose the more specific one only when the request or product identity supports it.
6. If materially different branches remain plausible and the distinction changes the research, ask one focused question or stay at the deepest safe common parent.
7. For multiple materially different product targets, resolve each independently.
8. After resolving the deepest node, follow its declared `Inheritance` chain and apply each matching registry entry general -> specific.
9. A named Class/Category/Type that does not exist in the corresponding registry is not a live hierarchy node. Do not invent it.

## Inheritance validation
A node's declared metadata must be internally consistent:
- `Parent` must be Base or a live node in the appropriate registry;
- `Inheritance` must begin with Base, end with the node itself, and contain the declared Parent immediately before the node;
- inheritance chains must be acyclic;
- a child may skip Class or Category when the natural hierarchy calls for it.

If registry metadata conflicts, do not guess silently. For instruction-set audit treat it as a structural defect; during ordinary shopping work stay at the deepest unambiguous valid parent.

## Expansion rule
Add new Classes, Categories, and Types only after identifying:
- the shared behavior they own;
- the parent they naturally inherit from;
- which shared-authority or workflow concerns, if any, genuinely need Merge or Override behavior.

Do not migrate legacy taxonomy mechanically and do not add contributions merely to fill a template.
