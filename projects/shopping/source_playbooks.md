# Source Playbooks

## Purpose

This file owns reusable source-discovery playbooks selected by product nodes.

A playbook answers where to look for category-appropriate evidence. It does not determine whether a discovered source is admissible evidence; `research_sources.md` owns that decision.

---

## Base playbook

### general-shopping
Use a broad source mix appropriate to the claim types involved:
- primary manufacturer/vendor documentation for objective specifications;
- standards/regulatory/certification sources when relevant;
- method-based publications or competent specialists for empirical performance;
- owner/community evidence for reliability, long-term use, and edge cases;
- seller/listing sources only for pricing, availability, and purchase-channel facts.

Avoid allowing one publication family or one narrative ecosystem to dominate the research basis.

---

## Inheritance behavior

- `general-shopping` is available from Base.
- Product nodes may add more-specific playbooks.
- More-specific playbooks specialize discovery; they do not lower evidence standards.
- A child may explicitly remove an inherited playbook only when it is genuinely irrelevant.

Detailed category playbooks from the prior Shopping project remain in `archive/source_playbooks.md` for deliberate migration.
