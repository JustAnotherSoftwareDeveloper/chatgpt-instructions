# Product Hierarchy

## Purpose
Define the Shopping inheritance context used by every workflow.

Resolve one chain:

`Base -> optional Class -> optional Category -> optional Type`

Each active level inherits its parent and may:
- add ordinary product-domain directives;
- select named sections from shared authorities;
- load one or more specialized files when deeper behavior is needed.

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
The narrowest reusable product-kind specialization that materially changes research, evaluation, pricing, or fit behavior.

A Type is not a SKU, brand, color, minor form factor, marketing label, or arbitrary retailer category. A Type may inherit from Base, a Class, or a Category.

## Resolution guidance
1. Use explicit product wording or a confidently established named-model identity first.
2. Prefer the deepest entry whose product meaning is actually supported.
3. Do not force a Type merely because one exists; broader parent contexts are valid terminal resolutions.
4. Do not invent missing intermediate levels. If a Type naturally inherits directly from a Class or Base, use that relationship.
5. If two plausible entries are on the same inheritance chain, choose the more specific one only when the request or product identity supports it.
6. If materially different branches remain plausible and the distinction changes the research, ask one focused question or stay at the deepest safe common parent.
7. For multiple materially different product targets, resolve each independently.

## Inheritance behavior
Apply active levels from general to specific.

A child:
- inherits applicable parent guidance;
- adds domain-specific behavior;
- may specialize a broader non-safety default within its own topic;
- should not restate detailed parent rules.

If an entry names shared-authority sections, apply those sections in addition to inherited sections. If it names specialized files, load those files while the level is active.

Keep hierarchy entries concise. Substantial domain knowledge belongs in specialized authority files.

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
Add new Classes, Categories, and Types only after identifying the shared behavior they own and the parent they naturally inherit from. Do not migrate the legacy taxonomy mechanically.
