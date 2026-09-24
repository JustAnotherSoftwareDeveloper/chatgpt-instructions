# Shopping Project Orchestrator

## 0) Purpose

This file is the single orchestration layer for the Shopping project.

It owns only:
- workflow-intent routing;
- product-context resolution orchestration;
- inheritance-chain construction;
- authority loading;
- cross-authority precedence;
- locked-context carry-forward.

It does not own product-domain criteria, source-discovery rules, evidence policy, review interpretation, seller policy, pricing strategy details, or output templates. Those belong to the canonical authority files below.

---

## 1) Canonical live files

- `base.md` - universal Shopping defaults and Base-level authority activation. Boundary: no product taxonomy or domain-specific research rules.
- `product_types.md` - product-node registry, matching/classification rules, parent relationships, and authority hooks. Boundary: nodes reference instruction sets; they do not restate those authorities' rules.
- `criteria.md` - reusable evaluation-criteria definitions. Boundary: no taxonomy, sourcing, pricing, or seller policy.
- `source_playbooks.md` - reusable source-discovery playbooks. Boundary: discovery guidance only; evidence admissibility belongs to `research_sources.md`.
- `pricing.md` - reusable pricing/value strategies. Boundary: no seller-legitimacy policy or product taxonomy.
- `research_sources.md` - evidence admissibility, weighting, recency, breadth, and claim-to-evidence discipline. Boundary: review-reading mechanics and seller risk are delegated.
- `reviews.md` - interpretation of review evidence and manipulation/astroturf detection. Boundary: no seller policy or general evidence-admissibility rules.
- `seller_instructions.md` - seller/channel evaluation and purchase-risk policy. Boundary: no product-quality evaluation.

`archive/` is migration/reference material, not a live authority set. Archived files are excluded from the canonical map, precedence, routing, and normal duplication checks unless a migration task explicitly targets them.

No workflow-specific authority or template files are live yet in this scaffold. Section 6 therefore classifies workflow intent only; it must never fall back to `archive/`.

---

## 2) Core inheritance model

Every resolved product context begins with `base`.

Optional specialization may then add, in order:
- Class;
- Category;
- Type.

Conceptual shape:

`Base -> optional Class -> optional Category -> optional Type`

Intermediate levels may be skipped. A request may resolve only to Base. The parent graph and allowed parent-kind relationships are defined in `product_types.md`.

The parent chain is authoritative. Classification identifies the deepest justified node; inheritance is obtained by walking that node's parents back to Base and reversing the chain.

A request may contain multiple materially distinct product targets. Resolve one product context per target when their deepest justified nodes differ. Do not collapse a cross-category comparison to a generic common ancestor merely to force a single context.

---

## 3) Product-context resolution

For each product target:
1. Ask `product_types.md` to resolve the deepest justified node.
2. Walk its `parent` pointers to `base`.
3. Validate that every referenced parent exists, the chain reaches Base, allowed kind relationships are respected, and no cycle exists.
4. Reverse the chain to obtain inheritance order.
5. Apply Base first, then each specialization from least specific to most specific.
6. Load the reusable instruction sets and specialized authorities referenced by the effective chain.
7. Apply current-thread user constraints and locked decisions subject to safety/legal limits.

If classification ambiguity materially changes the research approach, ask once. Otherwise stop at the deepest unambiguous resolvable node instead of guessing a child.

If the user materially changes a product target, resolve a new context for that target.

---

## 4) Inheritance and merge semantics

Construction order is always Base -> leaf. This is separate from runtime precedence.

At each node:
- additive collections (`criteria`, `source_playbooks`) inherit parent entries;
- `remove` deletes inherited non-safety entries at that node;
- `add` then appends/deduplicates stable IDs;
- `pricing.strategy` is a single inherited property: the closest node that defines it wins;
- `authorities` are additive; a child may load additional specialized authorities but must not silently disable an inherited authority.

If an inherited specialized authority is genuinely invalid for a child, fix the taxonomy boundary rather than using routine child suppression.

Safety/compliance requirements may become stricter through specialization but may not be weakened by ordinary inheritance or removal.

Reusable authority files own the meaning and internal behavior of the IDs they define. Product nodes select those IDs; they do not duplicate their implementation.

---

## 5) Runtime precedence and authority ownership

Do not confuse inheritance construction with conflict precedence.

Apply runtime priority as follows:
1. Safety-critical and legal/compliance constraints.
2. User-explicit constraints and locked decisions in the current thread, except where they conflict with item 1.
3. The canonical authority for the topic in dispute.
4. The effective product context produced by Base -> leaf inheritance, where more-specific node selections override less-specific selections according to Section 4.
5. Workflow/output presentation requirements, which govern deliverable structure but may not weaken evidence, safety, seller-risk, or other domain authorities.

Authority ownership:
- `research_sources.md` owns evidence admissibility, weighting, recency, breadth, and claim mapping;
- `reviews.md` owns review interpretation;
- `seller_instructions.md` owns seller/channel risk;
- `criteria.md` owns reusable evaluation-criteria definitions;
- `pricing.md` owns reusable pricing/value strategies;
- `source_playbooks.md` owns discovery guidance only;
- `product_types.md` owns classification and hook selection, not the rules inside the referenced authorities.

---

## 6) Deterministic workflow-intent routing

Use first-match logic. More-specific intents come before the general default.

1. Audit / QA / validate architecture or an artifact -> `audit` intent.
2. Explicit tiers / price bands / options by budget -> `pricing-tiers` intent.
3. Brand / manufacturer / store / retailer / vendor ecosystem research -> `vendor-research` intent.
4. One named product/model where the user primarily wants validation, red flags, or deal sanity -> `quick-check` intent.
5. All other shopping research/comparison/recommendation requests -> `product-research` intent.

An explicit user request for a workflow intent wins over inference unless safety or the request itself makes that workflow impossible.

During the current architecture-only scaffold phase, these are intent IDs, not references to archived workflow files. Execute using Base + resolved product context + live authorities and the user's requested presentation. When new workflow authorities/templates are added, add them to Section 1 and route these IDs to them explicitly.

---

## 7) Locked product context

Carry forward across follow-up turns, per product target:
- resolved leaf node and inheritance chain;
- exact product/variant/SKU when locked;
- compatibility and physical constraints;
- budget/price constraints;
- retailer/channel constraints;
- accepted or rejected candidates;
- explicit user overrides;
- requested output-format constraints.

Do not silently reclassify a locked target. Re-resolve only when the user changes it materially or new evidence shows the prior classification was wrong.

---

## 8) Archive boundary

`archive/` contains the previous Shopping implementation for migration/reference only.

Rules:
- never route to archived files;
- never treat archived rules as canonical;
- never use archive as a fallback for missing live behavior;
- migrate useful behavior deliberately into the correct live authority;
- preserve archived historical files unchanged except archive-specific metadata such as `archive/README.md`.

---

## 9) Architecture QA

Before finalizing structural edits, verify:
- every non-base node reaches Base through exactly one parent chain;
- parent-kind relationships are valid under `product_types.md`;
- every referenced criterion, playbook, pricing strategy, and specialized authority exists in the live project;
- no live file depends on an archived file;
- authority ownership is not duplicated across live files;
- routing remains deterministic and first-match;
- new workflow/template files, when introduced, are added to the canonical map and precedence model.
