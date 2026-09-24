# Product Type Registry

## Purpose

This file owns Shopping product classification and the inheritance registry.

A resolved product node determines which reusable instruction sets and specialized authorities are inherited. Product-domain rule implementations belong in the referenced authority files, not inline here.

---

## Structural model

Every product context starts at `base` and may specialize through:

`Base -> optional Class -> optional Category -> optional Type`

Each non-base node has exactly one parent. Multiple inheritance is not allowed.

Allowed parent relationships:
- Class -> Base only.
- Category -> Base or Class.
- Type -> Base, Class, or Category.

Skipped levels are valid. Same-kind chains such as Class -> Class, Category -> Category, or Type -> Type are invalid.

A request may resolve to Base, a Class, a Category, or a Type. Never force the deepest nominal level merely because a child exists.

---

## Resolution rules

For each materially distinct product target:
1. Start from explicit product wording and intent.
2. Prefer an explicitly named product kind over generic keyword inference.
3. Resolve only as deeply as the request supports.
4. If multiple children are plausible and choosing among them materially changes research behavior, either stop at the deepest common resolvable parent or ask once when a narrower answer is necessary.
5. Never invent an intermediate Class or Category merely to complete the hierarchy.
6. If a node has no matching metadata, it may serve as a structural parent but must not be selected directly from a request.
7. Every non-base node must eventually reach `base` through its parent chain.
8. Cycles and missing parents are invalid.

For a request comparing materially different kinds of products, resolve a separate inheritance chain for each target rather than collapsing them to a generic shared ancestor.

---

## Node contract

Use stable lowercase `snake_case` IDs.

Conceptual schema:

```yaml
id: <stable-id>
kind: class|category|type
parent: <node-id>
match:
  keywords: []
  cues: []
  excludes: []
criteria:
  add: []
  remove: []
source_playbooks:
  add: []
  remove: []
pricing:
  strategy: <instruction-set-id|null>
authorities:
  add: []
```

Only include fields a node needs. `match` is required only when the node may be selected directly from user wording.

Hook semantics:
- `criteria.add/remove` references IDs defined in `criteria.md`.
- `source_playbooks.add/remove` references IDs defined in `source_playbooks.md`.
- `pricing.strategy` references one strategy ID defined in `pricing.md`; the closest node defining a strategy wins.
- `authorities.add` references live specialized authority files. Authorities are additive.

All hook references must resolve to live project files/IDs. Archived files and IDs are not valid dependencies.

Nodes should contain only matching metadata and hook selections. If a node needs substantial domain logic, create or use a specialized authority and reference it through `authorities.add`.

---

## Base node

### base
- kind: base
- parent: none
- live instructions: `base.md`

The detailed legacy taxonomy remains in `archive/product_types.md` for migration reference only. New Class, Category, and Type nodes should be introduced deliberately after their inheritance boundaries are reviewed.

---

## Boundary

This file owns classification, parent relationships, graph validity, and selection of instruction-set IDs. It does not own the implementation of criteria, source discovery, pricing, evidence policy, review interpretation, seller policy, or specialized domain rules.
