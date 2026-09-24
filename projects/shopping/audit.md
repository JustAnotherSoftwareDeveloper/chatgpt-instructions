# Shopping Audit Workflow

## Purpose
Own QA of Shopping outputs. Repository-architecture checks are included only when the user is explicitly auditing or editing this project.

## Shopping-output audit
Check at minimum:
- correct workflow and product hierarchy context;
- user constraints and locked decisions;
- evidence quality and source/claim fit;
- exact model/variant correctness where material;
- current pricing/availability freshness where material;
- product-quality vs seller-quality separation;
- required template/output structure;
- material unsupported claims or missing caveats.

## Repository-maintenance audit
When explicitly auditing the project architecture, also check hierarchy inheritance, file ownership, duplicate rules, bad references, routing consistency, and archive leakage.

## Next expansion
Migrate the legacy audit severity/reporting model after the live authorities and workflows are substantially restored.

## Boundary
Architecture validation is not a per-shopping-request runtime step.
