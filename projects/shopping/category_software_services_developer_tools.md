# Category Authority: Software / Services / Developer Tools

## Purpose
Own workflow specialization for software products, SaaS, hosted services, APIs, developer tools, and commercially evaluated open-source tools when the `Software / Services / Developer Tools` Category is active.

Use the Software / Services / Developer Tools sections of `criteria.md`, `source_playbooks.md`, and `pricing.md` alongside this file.

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
Apply the active Software / Services / Developer Tools criteria to verify, where material:
- supported platform/runtime/deployment model;
- required API/integration capability;
- license/usage terms compatible with intended use;
- required data export/residency/compliance posture;
- active support status for the exact product/version/plan;
- unacceptable mandatory cloud or proprietary dependency when explicitly constrained.

## Merge: Product Research -> Finalist extraction
Add where material:
- Developer / operator experience;
- Reliability / operational maturity;
- Security / governance posture;
- Licensing / commercial fit;
- Portability / lock-in;
- Project / ecosystem health;
- effective cost under the user's plausible usage scenario.

Apply `research_sources.md` to these fields.

# Pricing Tiers contributions

## Override: Pricing Tiers -> Tier construction -> single purchase-price ladder assumption
Replace a single unit-price ladder with a normalized **usage-and-entitlement cost surface** when software pricing cannot be meaningfully compared by one sticker price.

Use the representative-usage normalization defined in the Software / Services / Developer Tools section of `pricing.md`, then construct meaningful value regions from comparable effective cost and capability for those scenarios.

Preserve the generic requirements to normalize current price posture, validate coherent regions, and explain what additional spend buys. Do not force incomparable commercial models into one raw monthly-price ladder.

## Merge: Pricing Tiers -> Market segmentation
Represent parallel commercial models when they are real market structures: open-source/self-hosted, freemium/team, usage-metered, enterprise-contract, managed-service, or other materially different paths.

## Merge: Pricing Tiers -> Marginal-spend analysis
Identify whether extra spend buys scale, governance, support/SLA, security/compliance controls, collaboration, managed operations, reduced engineering labor, or mainly commercial packaging.

## Merge: Pricing Tiers -> Buying context
Surface commercial terms from `pricing.md` that create material non-linear cost, entitlement, commitment, or exit consequences for the user's scenario.

# Vendor Research contributions

## Merge: Vendor Research -> Ecosystem segmentation
When relevant distinguish commercial SaaS vendors, open-core companies, foundation/community-led projects, hyperscaler-managed variants, independent support vendors, and resellers/integrators. Keep project health and vendor health separate.

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
- sustained production adoption.

# Quick Check contributions

## Merge: Quick Check -> Target identity
Verify exact product/service, edition/plan, version, deployment model, license, region, and pricing basis when any change the answer.

## Merge: Quick Check -> Hard gates
Treat incompatible licensing, missing required integration/platform support, unacceptable export/deployment constraints, or unsupported versions as narrow hard failures when explicitly required.

## Merge: Quick Check -> Decision questions
Useful narrow questions include whether a claimed feature exists in the relevant plan/version, whether the pricing basis matches the user's usage, whether a current reliability/security issue changes the decision, and whether exit/export is realistically possible.

## Boundary
Criteria definitions remain in `criteria.md`; discovery in `source_playbooks.md`; evidence/version/comparability in `research_sources.md`; community interpretation in `reviews.md`; seller risk in `seller_instructions.md`; reusable value logic in `pricing.md`.
