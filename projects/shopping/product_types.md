# Product Classification Registry

## Purpose

This file owns Shopping product classification and the inheritance registry.

A resolved product node determines which reusable instruction sets and registered specialized authorities are inherited. Product-domain rule implementations belong in the referenced authority files, not inline here.

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

### Level semantics

Hierarchy levels exist to capture reusable inherited behavior, not to mirror a retailer catalog.

- **Base**: universal Shopping behavior that applies regardless of product domain.
- **Class**: broad specialization that earns its existence by providing reusable behavior across multiple downstream product families.
- **Category**: optional intermediate specialization that factors shared behavior out of multiple Types or provides a useful terminal research context of its own.
- **Type**: the narrowest reusable product-kind specialization. It should represent a materially distinct research/evaluation behavior, not a SKU, brand, color, minor form factor, or marketing label.

Do not create a Class or Category merely for taxonomic neatness. If an intermediate node does not own meaningful shared hook selections or provide useful fallback classification, omit it.

Do not create a Type when the parent already provides the same effective instructions and the distinction would not materially change research behavior.

---

## Resolution model

Classification has two distinct concepts:

- **direct candidate matching**: deciding which nodes the request itself supports;
- **structural fallback**: backing up to an ancestor when several matched descendants remain materially ambiguous.

A structural parent does not need direct matching metadata in order to serve as a fallback ancestor.

### Direct candidate matching

For each materially distinct product target:
1. Start from explicit product wording, known product identity, and stated use-case intent.
2. Apply `match.excludes` first; an exclusion vetoes that node for the current target.
3. Prefer candidates in this order:
   - explicit canonical/alias product-kind match;
   - exact specific multi-word keyword/phrase match;
   - multiple independent specific keyword matches;
   - one specific keyword supported by a discriminating cue.
4. `match.cues` may disambiguate or strengthen a candidate but should not normally create a leaf candidate by themselves.
5. Generic or collision-prone words must not select a narrow node without additional support.
6. A known named model/SKU may resolve to a node when its product identity is established confidently, even if the user's wording omits the generic product-kind term.
7. A node with no usable matching metadata may be a structural ancestor but must not originate as a direct candidate.

Do not use opaque numeric scoring. The ordered evidence tiers above are the canonical comparison rule.

### Choosing among candidates

- If one supported candidate is a descendant of another supported candidate on the same chain, prefer the more specific descendant when its match evidence is at least as strong.
- If candidates on different branches remain plausible and the distinction materially changes research behavior, use their deepest common ancestor as a structural fallback when that ancestor is informative enough for the request.
- A structural fallback ancestor may be used even when it has no direct `match` metadata; this is fallback traversal, not direct selection.
- If the only common ancestor is too generic to answer correctly, ask once for the missing distinction.
- If ambiguity does not materially change the answer, use the deepest safe common ancestor and state the assumption only when useful.
- If no non-Base node is justified, resolve to `base`.

Never invent an intermediate Class or Category merely to complete the hierarchy.

For a request comparing materially different kinds of products, resolve a separate inheritance chain for each target rather than collapsing them to a generic shared ancestor.

---

## Graph validity

Every non-base node must:
- reference an existing parent;
- obey the allowed parent-kind relationships above;
- eventually reach `base`;
- participate in no cycle.

Node IDs are globally unique within this registry.

---

## Node contract

Use stable lowercase `snake_case` IDs.

Conceptual schema:

```yaml
id: <stable-id>
kind: class|category|type
parent: <node-id>
match:
  names: []
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

Only include fields a node needs.

`match` is required only when the node may originate as a direct candidate. A structural-only node may omit it.

Matching fields:
- `names`: canonical product-kind names and unambiguous aliases;
- `keywords`: specific product terms or phrases used for direct candidate matching;
- `cues`: secondary intent/context signals used mainly for disambiguation;
- `excludes`: terms or contexts that disqualify an otherwise plausible match.

Hook semantics:
- `criteria.add/remove` references IDs defined in `criteria.md`.
- `source_playbooks.add/remove` references IDs defined in `source_playbooks.md`.
- `pricing.strategy` references one strategy ID defined in `pricing.md`; the closest node defining a strategy wins.
- `authorities.add` references specialized authority files that are already registered as canonical live authorities in `instructions.md`. Authorities are additive.

All hook references must resolve before execution. Missing IDs/files are architecture errors; do not silently ignore them and do not substitute archived definitions.

Nodes should contain only matching metadata and hook selections. If a node needs substantial domain logic, create or use a specialized authority, register that authority in `instructions.md`, then reference it through `authorities.add`.

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
