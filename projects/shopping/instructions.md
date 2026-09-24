# Shopping Project Orchestrator

## 0) Purpose

This file is the single orchestration layer for the Shopping project.

Its responsibilities are limited to:
- selecting the requested deliverable/workflow;
- resolving the most-specific justified product node;
- building the inheritance chain from `base` through that node;
- loading reusable instruction authorities referenced by the chain;
- defining precedence and conflict handling;
- preserving resolved context across follow-up turns.

Domain-specific product logic belongs in `product_types.md` or the authority files it references. Output structure belongs in templates/workflow files.

---

## 1) Core inheritance model

Every shopping request begins with `base`.

Optional specialization may then add, in order:
- Class
- Category
- Type

The valid conceptual shape is:

`Base -> optional Class -> optional Category -> optional Type`

Intermediate levels are not mandatory. A Type may inherit directly from a Class or from Base. A Category may inherit directly from Base. A request may resolve only to Base.

Resolution rule:
- identify the deepest justified product node from `product_types.md`;
- walk its `parent` chain back to `base`;
- reverse that chain to obtain inheritance order;
- never invent an intermediate node merely to fill a taxonomy level;
- never force a deeper classification than the request supports.

The parent chain is authoritative. `kind: class|category|type` is metadata for readability and auditing, not a structural requirement that every level appear.

---

## 2) Canonical architecture files

- `base.md` - universal Shopping defaults inherited by every request.
- `product_types.md` - product-node registry, matching rules, parent relationships, and authority hooks.
- `criteria.md` - reusable evaluation-criteria instruction sets.
- `source_playbooks.md` - reusable category/domain source-discovery playbooks.
- `pricing.md` - reusable pricing/value instruction sets.
- `research_sources.md` - evidence admissibility, weighting, recency, breadth, and claim-to-evidence discipline.
- `reviews.md` - review interpretation and manipulation/astroturf detection.
- `seller_instructions.md` - seller/channel evaluation and purchase-risk policy.

Workflow and template files may be added or restored as the new architecture is implemented. The archived implementation under `archive/` is reference-only and must not be loaded as live project behavior.

---

## 3) Product-context resolution

For each request:
1. Start with `base`.
2. Resolve the most-specific justified node in `product_types.md`.
3. Walk `parent` pointers until `base`.
4. Validate the chain: no cycles, every parent exists, every node reaches `base`, and no unsupported intermediate levels are inferred.
5. Apply node instructions from least specific to most specific.
6. Load referenced reusable authorities and any explicit specialized authorities.
7. Apply the user's explicit constraints and current-thread locked decisions.

If classification is ambiguous and the ambiguity materially changes the answer, ask once. Otherwise stop at the deepest unambiguous parent rather than guessing a child.

---

## 4) Inheritance and merge semantics

Instruction fields are inherited unless a child explicitly changes them.

Default merge behavior:
- `add`: union/append child entries after inherited entries, deduplicated by stable ID.
- `remove`: explicitly remove an inherited entry; use sparingly and never to suppress safety-critical requirements.
- `use`: select a named instruction set when no inherited selection exists.
- `override`: replace an inherited selection intentionally.
- `authorities`: additive unless explicitly removed by a more-specific node for a non-safety reason.

When a reusable authority defines its own internal merge semantics, that authority governs its domain.

Safety/compliance requirements may become stricter through specialization but may not be weakened by ordinary inheritance.

---

## 5) Precedence

Apply behavior in this order:
1. Safety-critical constraints and legal/compliance limits.
2. User explicit constraints and locked decisions in the current thread.
3. Most-specific product-node instructions.
4. Less-specific product-node instructions, walking toward Base.
5. `base.md` defaults.
6. Workflow/output-format contracts.

For reusable authorities:
- `research_sources.md` owns evidence admissibility and weighting;
- `reviews.md` owns review interpretation;
- `seller_instructions.md` owns seller/channel risk;
- `criteria.md` owns reusable evaluation-criteria definitions;
- `pricing.md` owns reusable pricing/value strategies;
- `source_playbooks.md` owns source-discovery guidance only.

A product node may select, add, or specialize an authority's instruction set, but should not restate that authority's rules inline.

---

## 6) Routing

Until the new workflow layer is rebuilt, routing is intentionally minimal:
- Product research / comparison / recommendation -> research workflow.
- Pricing tiers / price bands -> pricing workflow.
- Vendor / brand / retailer ecosystem research -> vendor workflow.
- Specific-product sanity check -> quick-check workflow.
- Audit / QA -> audit workflow.

The new workflow files will consume one resolved product context. They must not independently reclassify the product unless the user changes the target.

---

## 7) Locked product context

Carry forward across follow-up turns:
- resolved leaf node and inheritance chain;
- exact product/variant/SKU when locked;
- compatibility constraints;
- budget/price constraints;
- retailer/channel constraints;
- accepted or rejected candidates;
- explicit user overrides;
- output-format constraints.

If the user changes the product target materially, resolve a new chain.

---

## 8) Archive boundary

`archive/` contains the previous Shopping implementation for migration/reference only.

Rules:
- do not route to archived files;
- do not treat archived rules as canonical;
- migrate useful behavior into the new authority structure deliberately;
- avoid copying duplicate rules into multiple live files.
