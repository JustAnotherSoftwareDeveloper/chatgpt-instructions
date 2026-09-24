# Evaluation Criteria Authority

## Purpose

This file owns reusable evaluation-criteria instruction sets selected by product nodes.

Criteria are named, reusable units. Product nodes should reference criteria IDs rather than duplicating the criterion's meaning and evaluation rules.

---

## Base criteria

### value
Evaluate whether the product's benefits justify its total purchase and ownership cost for the user's stated use case.

### reliability
Evaluate expected consistency, failure patterns, durability, and support implications using evidence appropriate to the product.

### compatibility
Evaluate hard compatibility constraints before soft preference criteria.

### usability
Evaluate friction in setup, normal operation, maintenance, and recovery from common failures.

---

## Inheritance behavior

- Criteria selected by a parent are inherited.
- Child nodes may `add` criteria.
- Child nodes may explicitly `remove` a non-safety criterion when genuinely inapplicable.
- Safety/compliance criteria introduced by any active authority may not be removed by ordinary product inheritance.

Additional criterion sets will be migrated from the archived Shopping implementation as Classes, Categories, and Types are rebuilt.
