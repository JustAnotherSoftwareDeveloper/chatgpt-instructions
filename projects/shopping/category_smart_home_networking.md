# Category Authority: Smart Home / Networking

## Purpose
Own behavior specific to connected-home devices and prosumer/home networking when the `Smart Home / Networking` Category is active.

Use the Smart Home / Networking sections of `criteria.md`, `source_playbooks.md`, and `pricing.md` alongside this file.

# Shared domain behavior

## Evaluate the system, not the box
A connected device is part of a system of radios/protocols, controllers, network infrastructure, apps/APIs, cloud services, firmware, and other endpoints. A good standalone spec sheet does not establish reliable system behavior.

Protocol support or certification is evidence of conformance to a standard, not proof that every desired feature works across every ecosystem. Distinguish protocol compatibility, controller/platform support, exposed feature set, automation behavior, and real interoperability.

## Local/cloud dependency is architectural
Establish which functions are local, cloud-dependent, account-dependent, subscription-gated, or degraded when the internet/vendor service is unavailable. Treat cloud dependency, remote access, telemetry, and data retention as product architecture, not incidental software details.

## Lifecycle is product quality
Firmware quality, update cadence, security response, API continuity, hardware revision support, and explicit or implicit end-of-life behavior can materially change ownership value. A device that works today but depends on an unstable cloud/API lifecycle may be a poor long-horizon fit.

## Networking context matters
For networking products, reason from topology and workload: wired backhaul, radio environment, client mix, coverage geometry, roaming, VLAN/SSID needs, PoE, WAN speed, latency sensitivity, and management model. Do not rank routers/APs from headline PHY rates alone.

For smart-home endpoints, distinguish endpoint quality from failures caused by the surrounding controller, mesh, Wi-Fi, DNS, or cloud path when evidence permits.

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
Map products by architecture where it explains the market better than price: local-first vs cloud-first, controller/ecosystem, managed vs standalone, wired vs wireless/backhaul model, consumer convenience vs configurable infrastructure, and similar real design families.

## Merge: Product Research -> Hard gates and identity
Add checks where material for:
- exact protocol/radio/controller compatibility;
- required feature exposure in the user's actual ecosystem, not merely nominal protocol support;
- electrical/wiring/PoE/regional compatibility;
- required local operation or acceptable cloud/account dependence;
- active security/support status and known EOL state;
- exact hardware generation/revision when firmware or capabilities differ.

## Merge: Product Research -> Finalist extraction
Add where material:
- local/cloud failure behavior;
- interoperability path and controller dependencies;
- firmware maturity/regression history;
- security/update/EOL posture;
- API/integration quality;
- network-management depth or radio/topology behavior;
- subscription and data-export implications.

## Merge: Product Research -> Comparison and evidence use
Prefer evidence chains such as:

`protocol / topology / controller / firmware architecture -> observed interoperability, latency, stability, or manageability -> failure mode/tradeoff -> user consequence`

Do not infer real interoperability from logo lists or peak throughput from advertised link rates.

# Pricing Tiers contributions

## Merge: Pricing Tiers -> Market segmentation
Allow price/value regions to separate by system architecture and support model, not just faster radios or more devices. Managed infrastructure, local-first automation, subscription-backed convenience, and hardware-only/value ecosystems may be distinct tracks.

## Merge: Pricing Tiers -> Marginal-spend analysis
For meaningful step-ups, identify whether extra spend buys better radios/backhaul, more capable management, local processing, interoperability, longer support, security/lifecycle quality, lower subscription burden, or simply ecosystem/brand convenience.

# Vendor Research contributions

## Merge: Vendor Research -> Vendor normalization
For connected-device/network vendors add where material:
- firmware/update cadence and regression handling;
- vulnerability disclosure and remediation record;
- EOL/support-policy clarity;
- local-vs-cloud posture and cloud continuity;
- API/SDK/integration openness;
- protocol certification/interoperability track record;
- documentation and support quality for configuration/troubleshooting.

# Quick Check contributions

## Merge: Quick Check -> Target identity
When capability depends on it, verify hardware generation/revision, firmware train, region, radio/protocol variant, controller/ecosystem, and subscription/account tier.

## Merge: Quick Check -> Hard gates
Treat missing required ecosystem feature exposure, wiring/radio incompatibility, unacceptable cloud dependency, or unsupported/EOL status as narrow hard failures when the user's requirement is explicit.

## Merge: Quick Check -> Outside comparables / escalation
Escalate when the narrow judgment depends on redesigning the user's network/controller architecture rather than evaluating the named device in the existing system.

## Boundary
Evidence admissibility and security-claim support remain in `research_sources.md`; community interpretation in `reviews.md`; concrete seller/offer risk in `seller_instructions.md`; reusable criteria/source/pricing definitions remain in their shared authorities.