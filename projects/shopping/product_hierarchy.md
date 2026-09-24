# Product Hierarchy

## Purpose
This file defines the Shopping inheritance context used by every workflow.

Resolve one chain:

`Base -> optional Class -> optional Category -> optional Type`

Each active level inherits its parent and may add ordinary directives, select shared-authority sections, and load a specialized file when the level needs deeper behavior. Intermediate levels may be skipped when the hierarchy genuinely calls for it.

## Entry shape
Each hierarchy entry may define:
- Parent
- Use when
- Optimize / Avoid / Assumptions
- Apply - named sections from shared authorities
- Load - specialized files for that level

Keep entries concise. Detailed domain rules belong in the named specialized authority, not here.

## Base
Always active.

Apply `base.md`.

---

## Class: Home & Kitchen
Parent: Base

Use when:
- the purchase is primarily household or kitchen equipment, tools, or durable goods.

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
- kitchen cutlery characteristics such as blade geometry, steel/heat treatment, edge behavior, sharpening, maintenance, or knife ergonomics materially affect the purchase.

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
- the target is a general-purpose chef's knife or equivalent chef-knife/gyuto-style primary kitchen knife;
- a named model is clearly this product type even if the user does not say "chef's knife" explicitly.

Apply:
- Chef's Knife section of `criteria.md`;
- Chef's Knife section of `source_playbooks.md`;
- Chef's Knife section of `pricing.md`.

Load:
- `type_chefs_knife.md`.

## Next expansion
Add new Classes, Categories, and Types only after their inheritance boundary is understood. Do not migrate the legacy taxonomy mechanically.
