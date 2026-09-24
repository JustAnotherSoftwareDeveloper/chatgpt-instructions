# Evaluation Criteria Authority

## Purpose

This file owns reusable evaluation-criteria definitions selected by Base and product nodes.

Product nodes reference criterion IDs rather than restating the criterion's meaning or evaluation rules.

---

## Criteria

### value
Evaluate whether the product's benefits justify its purchase price and meaningful ownership costs for the user's stated use case.

### reliability
Evaluate consistency, failure patterns, durability, and support implications using evidence appropriate to the product.

### compatibility
Evaluate hard compatibility constraints before soft preference criteria.

### usability
Evaluate friction in setup, normal operation, maintenance, and recovery from common failures.

---

## Inheritance behavior

- Parent-selected criteria are inherited.
- Child nodes may add criteria by stable ID.
- Child nodes may remove an inherited non-safety criterion only when genuinely inapplicable.
- Safety/compliance requirements introduced by any active authority may not be removed by ordinary product inheritance.

Additional criteria should be added here when they are reusable across multiple product nodes. Narrow one-off domain logic belongs in a registered specialized authority instead.

---

## Boundary

This file defines evaluation dimensions only. It does not classify products, decide which criteria Base or a node activates, determine source admissibility, define source-discovery playbooks, set pricing strategy, interpret reviews, or evaluate sellers.
