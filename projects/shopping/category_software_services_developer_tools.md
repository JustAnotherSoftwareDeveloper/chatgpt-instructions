# Category Authority: Software / Services / Developer Tools

## Purpose
Own behavior specific to software products, SaaS, hosted services, APIs, developer tools, and commercially evaluated open-source tools when the `Software / Services / Developer Tools` Category is active.

Use the Software / Services / Developer Tools sections of `criteria.md`, `source_playbooks.md`, and `pricing.md` alongside this file.

# Shared domain behavior

## The product is an ongoing dependency
Evaluate the current version/service plus its operating model: release cadence, support lifecycle, reliability, security response, compatibility evolution, data/control-plane dependencies, and the cost of changing course later.

## Licensing and pricing are product behavior
Seat rules, usage meters, feature gates, overages, minimum commits, support tiers, cloud egress, self-hosting restrictions, source-available/open-source terms, and enterprise negotiation can materially change fit. Do not reduce software value to a posted monthly sticker price.

## Lock-in must be concrete
Evaluate lock-in through actual migration friction: proprietary data formats, API dependence, workflow coupling, deployment architecture, identity/integration dependencies, export completeness, switching downtime, and retraining. Do not use "lock-in" as a vague negative label.

## Developer experience can be primary product quality
For developer-facing tools, API/CLI design, documentation, SDK quality, local development ergonomics, debugging/observability, upgrade behavior, issue response, and ecosystem maturity can materially affect engineering cost and reliability.

## Operational trust requires history
For hosted products, assess incident transparency, uptime history, change management, security advisories, and support behavior. A current feature list does not establish operational maturity.

# Product Research contributions

## Merge: Product Research -> Scope and decision model
When material, add:
- deployment model and operating environment;
- required integrations/APIs/platforms;
- team size and expected usage shape;
- compliance/data-residency/security requirements;
- licensing constraints;
- migration/export requirements;
- support/SLA posture;
- expected growth and cost-scaling path.

## Merge: Product Research -> Market segmentation
Map meaningful families such as hosted vs self-hosted, open-source core vs proprietary, integrated suite vs composable specialist, usage-priced vs seat-priced, managed convenience vs infrastructure control, and enterprise-governed vs developer-led adoption when those distinctions explain tradeoffs.

## Merge: Product Research -> Hard gates and identity
Add checks for:
- supported platform/runtime/deployment model;
- required API/integration capability;
- license/usage terms compatible with intended use;
- required data export/residency/compliance posture;
- active support status for the exact product/version/plan;
- unacceptable mandatory cloud or proprietary dependency when explicitly constrained.

## Merge: Product Research -> Finalist extraction
Add where material:
- API/CLI/docs quality;
- upgrade/migration behavior;
- incident/reliability history;
- security/advisory response;
- issue-tracker/project health;
- support/SLA practicality;
- exportability and switching cost;
- effective cost under the user's plausible usage scenario.

## Merge: Product Research -> Comparison and evidence use
Prefer production-use evidence and reproducible benchmarks for workload claims. Distinguish project popularity from maintainership health, benchmark wins from representative workload fit, and documented capability from marketing roadmap promises.

# Pricing Tiers contributions

## Override: Pricing Tiers -> Tier construction -> single purchase-price ladder assumption
Replace a single unit-price ladder with a normalized **usage-and-entitlement cost surface** when software pricing cannot be meaningfully compared by one sticker price.

Before constructing tiers/regions, define one or more representative usage scenarios from the user's context or clearly stated assumptions, then normalize each candidate for:
- seats/users;
- usage/compute/storage/requests or other meters;
- required feature/support tier;
- required deployment model;
- recurring add-ons or minimum commitments.

Construct meaningful value regions from comparable effective cost and capability under those scenarios. Preserve the generic requirement to explain what additional spend buys; do not force incomparable pricing models into one raw monthly-price ladder.

## Merge: Pricing Tiers -> Market segmentation
Represent parallel commercial models when they are real market structures: open-source/self-hosted, freemium/team, usage-metered, enterprise-contract, managed-service, or other materially different paths.

## Merge: Pricing Tiers -> Marginal-spend analysis
Identify whether extra spend buys scale, governance, support/SLA, security/compliance controls, collaboration, managed operations, reduced engineering labor, or merely commercial packaging/negotiation leverage.

## Merge: Pricing Tiers -> Buying context
Call out pricing-model traps such as sharp overage curves, required higher tiers for one critical feature, minimum commits, expensive egress/export, or discounts that depend on long contractual commitments.

# Vendor Research contributions

## Merge: Vendor Research -> Ecosystem segmentation
When relevant distinguish commercial SaaS vendors, open-core companies, foundation/community-led projects, hyperscaler-managed variants, independent support vendors, and resellers/integrators. Do not collapse project health and vendor health into one concept.

## Merge: Vendor Research -> Vendor normalization
Add where material:
- roadmap/changelog transparency;
- incident and security-disclosure behavior;
- pricing-model stability;
- licensing/governance history;
- API/backward-compatibility discipline;
- data portability;
- support quality by customer tier;
- open-source/community health and maintainer concentration;
- evidence of sustained production adoption.

# Quick Check contributions

## Merge: Quick Check -> Target identity
Verify exact product/service, edition/plan, version, deployment model, license, region, and pricing basis when any of these change the answer.

## Merge: Quick Check -> Hard gates
Treat incompatible licensing, missing required integration/platform support, unacceptable export/deployment constraints, or unsupported versions as narrow hard failures when explicitly required.

## Merge: Quick Check -> Decision questions
Useful narrow questions include whether a claimed feature exists in the relevant plan/version, whether the pricing basis matches the user's usage, whether a current reliability/security issue materially changes the decision, and whether exit/export is realistically possible.

## Boundary
Security/compliance claims remain subject to `research_sources.md`; community/issue evidence interpretation to `reviews.md`; concrete reseller/offer risk to `seller_instructions.md`; reusable criteria/source/pricing concepts remain in their shared authorities.