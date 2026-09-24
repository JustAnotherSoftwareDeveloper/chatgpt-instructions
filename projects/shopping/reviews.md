# Review Interpretation Authority

## Purpose

This file owns how Shopping research interprets review evidence, including manipulation/astroturf risk and the difference between isolated anecdotes and repeated owner signal.

`research_sources.md` remains responsible for whether a review source is admissible and how much evidentiary weight it receives overall.

The previous detailed implementation is preserved at `archive/reviews.md` and will be migrated deliberately; archived rules are not active implicitly.

---

## Initial live contract

When this authority is active:
- treat reviews as evidence with incentives, selection effects, and platform-specific bias;
- prefer repeated patterns across independent sources over vivid single anecdotes;
- distinguish product-quality complaints from seller/shipping/channel complaints;
- give greater weight to reviews with concrete ownership context, version/model specificity, and reproducible observations;
- treat suspiciously repetitive, generic, or coordinated review language cautiously;
- do not use review volume alone as proof of quality.

---

## Boundary

This file interprets review content only. It does not decide when review analysis is activated. General source admissibility and claim mapping belong to `research_sources.md`; seller/channel risk belongs to `seller_instructions.md`; product taxonomy and criteria selection belong elsewhere.
