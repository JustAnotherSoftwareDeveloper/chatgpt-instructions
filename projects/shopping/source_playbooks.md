# Source Playbooks

## Purpose

This file owns reusable source-discovery playbooks selected by Base and product nodes.

A playbook answers where to search for category-appropriate information. It does not determine whether a discovered source is admissible evidence; `research_sources.md` owns admissibility, weighting, and claim-to-evidence use.

---

## Playbooks

### general-shopping
During discovery, search broadly across source families that may be relevant to the target, including:
- manufacturer/vendor documentation;
- standards, regulatory, certification, or recall sources when the category may involve them;
- specialist publications and method-based testing outlets;
- competent practitioners or domain experts;
- owner communities and long-term-use discussions;
- seller/listing sources when current price or availability is in scope.

Use this playbook to widen discovery only. Do not infer evidentiary weight from a source family's presence on this list.

---

## Inheritance behavior

- Parent-selected playbooks are inherited.
- Product nodes may add more-specific playbooks.
- More-specific playbooks specialize or widen discovery; they do not lower evidence standards.
- A child may remove an inherited playbook only when it is genuinely irrelevant to that branch.

Category playbooks from the previous implementation remain in `archive/source_playbooks.md` for deliberate migration.

---

## Boundary

This file owns source discovery strategy only. It does not decide which playbooks Base or a node activates. Evidence admissibility, claim matching, weighting, recency, and conflict resolution belong to `research_sources.md`; review interpretation belongs to `reviews.md`; seller legitimacy belongs to `seller_instructions.md`.
