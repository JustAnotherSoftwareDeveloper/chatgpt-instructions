# Category Authority: Automotive Accessories

## Purpose
Own behavior specific to vehicle accessories, upgrades, and add-ons when the `Automotive Accessories` Category is active.

Use the Automotive Accessories sections of `criteria.md`, `source_playbooks.md`, and `pricing.md` alongside this file.

# Shared domain behavior

## Fitment is exact, not approximate
Vehicle compatibility can depend on year, make, model, trim, body style, drivetrain, factory package, connector, mounting point, wheel/brake geometry, sensor package, or mid-year production change. Generic vehicle-class compatibility is not enough when those distinctions matter.

## Installation quality can determine product quality
A capable product can perform poorly or create secondary problems when installed incorrectly. Distinguish product design, installer execution, required calibration/programming, and vehicle-side constraints.

## Safety-criticality varies sharply
Treat accessories differently depending on whether failure is cosmetic/convenience-only or can affect visibility, braking, steering, restraint systems, load retention, electrical integrity, driver awareness, or other vehicle operation. Apply relevant standards/official evidence where the accessory class requires it.

## Vehicle-system interaction matters
Modern vehicles are integrated systems. Added electrical loads, CAN-bus interfaces, cameras/sensors, ADAS calibration, tire/wheel dimensions, suspension geometry, towing/load limits, and software coding can create consequences beyond the accessory itself.

# Product Research contributions

## Merge: Product Research -> Scope and decision model
When material, add:
- exact vehicle identity and factory configuration;
- installation method and user/installer capability;
- operational criticality;
- required standards/load ratings/certifications;
- vehicle-system interactions;
- reversibility and warranty/service implications;
- regional legal/inspection constraints when material.

## Merge: Product Research -> Candidate extraction
Add where material:
- exact fitment basis;
- installation complexity and required tools/programming;
- applicable load/electrical/physical limits;
- vehicle-specific owner evidence;
- return consequences if fitment proves wrong.

## Merge: Product Research -> Hard gates and identity
Add checks for:
- exact year/make/model/trim/package compatibility;
- required mounting/connector/clearance fit;
- applicable load, electrical, or operating limits;
- required standard/certification when the accessory class depends on it;
- compatibility with sensors, cameras, driver-assistance, factory audio/electronics, or other integrated systems when relevant.

## Merge: Product Research -> Comparison and evidence use
Prefer exact-vehicle or platform-specific evidence for fitment claims. Do not generalize successful installation on a superficially similar trim/year when the relevant mounting, electronics, dimensions, or factory package differ.

# Pricing Tiers contributions

## Merge: Pricing Tiers -> Tier validity
A higher tier should reflect meaningful differences such as verified fitment quality, materials/load capability, engineering/testing, installation simplicity, service/support, durability, or integration quality. Cosmetic branding alone does not establish a higher functional tier.

## Merge: Pricing Tiers -> Marginal-spend analysis
Include required installation hardware, professional labor/programming, calibration, and replacement/restoration costs when those are material to the real price step.

# Vendor Research contributions

## Merge: Vendor Research -> Vendor normalization
For manufacturers/brands add where material:
- fitment-database accuracy and update quality;
- platform-specific engineering depth;
- installation documentation;
- applicable testing/certification transparency;
- replacement-part/support continuity.

For retailers/installers add where material:
- fitment guarantee and dispute handling;
- installer competence for the relevant vehicle/system;
- return logistics for bulky or vehicle-specific items;
- calibration/programming capability where required.

# Quick Check contributions

## Merge: Quick Check -> Target identity
Lock the exact vehicle year/make/model/trim/body/package plus accessory revision/part number whenever fitment depends on them.

## Merge: Quick Check -> Hard gates
Treat a fitment mismatch, required-rating shortfall, or incompatible vehicle-system interaction as an immediate narrow failure.

## Merge: Quick Check -> Deal / where-to-buy
When the item is bulky, vehicle-specific, or installation-dependent, include return shipping/restocking, fitment guarantees, and installer/support consequences in the offer judgment.

## Boundary
Official standards/claims remain governed by `research_sources.md`; seller/offer risk by `seller_instructions.md`; review/community pattern interpretation by `reviews.md`; shared criterion/source/pricing definitions remain in their owning authorities.