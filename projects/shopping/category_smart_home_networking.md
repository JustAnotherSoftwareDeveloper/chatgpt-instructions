# Category Authority: Smart Home / Networking

## Purpose
Own workflow specialization for connected-home devices and prosumer/home networking when the `Smart Home / Networking` Category is active.

Use the Smart Home / Networking sections of `criteria.md`, `source_playbooks.md`, and `pricing.md` alongside this file.

# Product Research contributions

## Merge: Product Research -> Scope and decision model
When material, add:
- required ecosystem/controller and exposed capabilities;
- local-only vs cloud-tolerant operation;
- protocol/radio and hub/controller dependencies;
- installation/power/wiring constraints;
- privacy/security posture;
- subscription/account requirements;
- network topology/workload for infrastructure products;
- ownership horizon and tolerance for vendor EOL.

## Merge: Product Research -> Market segmentation
Map products by architecture when that explains the market better than price: local-first vs cloud-first, controller/ecosystem, managed vs standalone, wired vs wireless/backhaul model, consumer convenience vs configurable infrastructure, and similar real design families.

## Merge: Product Research -> Hard gates and identity
Apply the active Smart Home / Networking criteria to verify, where material:
- exact protocol/radio/controller compatibility;
- required feature exposure in the user's actual ecosystem;
- electrical/wiring/PoE/regional compatibility;
- required local operation or acceptable cloud/account dependence;
- active support/EOL state;
- exact hardware generation/revision when capabilities differ.

## Merge: Product Research -> Finalist extraction
Add where evidence exists:
- interoperability path and controller dependencies;
- local/cloud failure behavior;
- firmware/support lifecycle;
- API/integration quality;
- network-management or topology fit;
- subscription/account implications.

# Pricing Tiers contributions

## Merge: Pricing Tiers -> Market segmentation
Allow price/value regions to reflect system architecture and support model, not just faster radios or more devices.

## Merge: Pricing Tiers -> Marginal-spend analysis
Identify whether extra spend buys better radios/backhaul, management, local processing, interoperability, support lifecycle, lower subscription burden, or mainly ecosystem convenience.

# Vendor Research contributions

## Merge: Vendor Research -> Vendor normalization
Add where material:
- firmware/update cadence and regression handling;
- vulnerability disclosure/remediation record;
- EOL/support-policy clarity;
- local-vs-cloud posture;
- API/SDK/integration openness;
- protocol/interoperability track record;
- documentation and troubleshooting support.

# Quick Check contributions

## Merge: Quick Check -> Target identity
Verify hardware generation/revision, firmware train, region, radio/protocol variant, controller/ecosystem, and account/subscription tier when capability depends on them.

## Merge: Quick Check -> Hard gates
Treat missing required ecosystem feature exposure, wiring/radio incompatibility, unacceptable cloud dependency, or unsupported/EOL status as narrow failures when explicitly required.

## Merge: Quick Check -> Outside comparables / escalation
Escalate when the answer depends on redesigning the user's network/controller architecture rather than evaluating the named device in the existing system.

## Boundary
Criteria definitions remain in `criteria.md`; discovery in `source_playbooks.md`; evidence/comparability in `research_sources.md`; review interpretation in `reviews.md`; seller risk in `seller_instructions.md`; reusable value logic in `pricing.md`.
