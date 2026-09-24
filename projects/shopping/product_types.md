# Product Type Registry

## Purpose

This file defines the Shopping product inheritance registry.

Every node has:
- `id`
- `kind`: `base`, `class`, `category`, or `type`
- `parent`: another node ID, except `base`
- matching metadata sufficient to resolve requests conservatively
- optional hooks into reusable instruction authorities
- optional specialized authority files

The hierarchy is flexible:

`Base -> optional Class -> optional Category -> optional Type`

A node may skip intermediate levels. The most-specific justified node is the leaf; its parent chain defines effective inheritance.

---

## Resolution rules

1. Start from the user's explicit product wording and intent.
2. Resolve only as deeply as evidence supports.
3. Prefer an explicit named product kind over inferred generic keywords.
4. If multiple children are plausible and the distinction materially changes research, stop at their common parent or ask once when necessary.
5. Never invent a Category or Class merely because a deeper node exists.
6. Every non-base node must eventually reach `base` through `parent` pointers.
7. Cycles are invalid.

---

## Node contract

Use this schema conceptually:

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
  use: <instruction-set-id|null>
  override: <instruction-set-id|null>
research:
  add: []
authorities: []
```

Only include fields a node actually needs. Do not restate inherited behavior.

---

## Initial registry

The detailed taxonomy from the prior implementation is intentionally not migrated yet. It remains under `archive/product_types.md` as reference.

### base
- kind: base
- parent: none
- live instructions: `base.md`

New Class, Category, and Type nodes should be migrated deliberately from the archive after their inheritance boundaries are reviewed.
