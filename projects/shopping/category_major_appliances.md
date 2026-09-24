# Category Authority: Major Appliances

## Purpose
Own behavior specific to installed or bulky household appliances when the `Major Appliances` Category is active.

Use the Major Appliances sections of `criteria.md`, `source_playbooks.md`, and `pricing.md` alongside this file. Inherit Home & Kitchen behavior.

# Shared domain behavior

## Ownership horizon dominates feature count
For refrigerators, laundry, dishwashers, ranges, and similar durable appliances, evaluate the machine across years of use. Serviceability, parts access, technician availability, recurring failure modes, and repair economics can outweigh incremental feature count.

## Installation is part of product fit
Exact dimensions, clearances, door swing, hookups, electrical/plumbing requirements, venting, floor/load constraints, and delivery path can be hard constraints. Nominal width class is not enough when the installation is tight.

## Reliability evidence is model- and family-sensitive
Do not project a brand-level reputation onto every model. Separate model/family design issues, component-platform issues, service-network complaints, installer/delivery failures, and isolated unit defects where evidence permits.

## Complexity can create ownership cost
Connected features, dispensers, extra pumps/valves, specialty cycles, integrated screens, and other complexity may add real utility but also more failure surfaces. Treat added complexity as a tradeoff, not automatically a defect or benefit.

# Product Research contributions

## Merge: Product Research -> Scope and decision model
When material, add:
- exact installation envelope and hookup/venting constraints;
- household capacity/use pattern;
- service-area availability and ownership horizon;
- noise/energy/water priorities;
- tolerance for repair downtime;
- delivery/removal/install needs.

## Merge: Product Research -> Hard gates and identity
Add checks for:
- exact dimensions/clearances and access path;
- electrical/plumbing/venting compatibility;
- regional configuration;
- required capacity or special installation constraints;
- materially inadequate service support for the user's location when serviceability is a hard requirement.

## Merge: Product Research -> Finalist extraction
Add where material:
- recurring model/family failure modes and ownership horizon;
- parts availability and repair access;
- authorized/independent service depth;
- install/delivery complexity;
- measured energy/water/noise/performance evidence;
- feature complexity that materially changes service risk;
- warranty scope and practical service path.

## Merge: Product Research -> Comparison and evidence use
Separate product reliability from delivery/installer/service-network experience. Prefer model/family-specific repair and standardized test evidence over generic brand reputation when the evidence supports that distinction.

# Pricing Tiers contributions

## Merge: Pricing Tiers -> Tier validity
A higher appliance tier should be justified by concrete gains such as better core performance, lower noise/energy use, materially better construction, useful capacity/ergonomics, stronger serviceability, longer support/parts access, or genuinely valuable features. Feature count and finish alone do not validate a higher functional tier.

## Merge: Pricing Tiers -> Marginal-spend analysis
Include installed ownership consequences: purchase price, required installation/accessories, energy/water differences where material, expected repair/service burden, and whether premium complexity raises or lowers long-horizon value.

## Merge: Pricing Tiers -> Buying context
Account for delivery, haul-away, installation, damaged-unit exchange, and service facilitation when those materially change the effective purchase proposition.

# Vendor Research contributions

## Merge: Vendor Research -> Vendor normalization
For appliance manufacturers/brands add where material:
- parts availability and platform continuity;
- authorized and independent service coverage;
- warranty execution rather than paper length alone;
- recurring model-family reliability patterns;
- documentation/diagnostic support.

For appliance retailers/dealers add where material:
- delivery damage/error handling;
- installation competence and subcontracting model;
- haul-away/exchange logistics;
- ability to coordinate warranty/service;
- regional service reach.

# Quick Check contributions

## Merge: Quick Check -> Target identity
Verify exact model suffix, regional configuration, dimensions, finish only when it changes the SKU, and any generation/revision relevant to known issues.

## Merge: Quick Check -> Hard gates
Check installation envelope, hookup/venting, delivery path, regional serviceability when required, and any active recall constraint material to the exact model.

## Merge: Quick Check -> Deal / where-to-buy
For concrete offers, include delivery/install/haul-away costs and damaged-unit/large-item return handling when they can erase an apparent price advantage.

## Boundary
Home-wide ownership behavior remains in `class_home_kitchen.md`; evidence standards in `research_sources.md`; seller/offer classification in `seller_instructions.md`; shared criterion/source/pricing definitions remain in their owning authorities.