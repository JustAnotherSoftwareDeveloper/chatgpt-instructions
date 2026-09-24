# product_types.md

## Purpose and scope

This file defines a two-level taxonomy for product research:

- **Product Classes**: broad, domain-generic buckets that define default research behavior.
- **Product Types**: refinements within a class that adjust defaults via inheritance.

Designed to be used by:
- `instructions.md` (routing)
- `product_research.md` (deep research workflow)
- `pricing_tiers.md` (tiered recommendations workflow)

This file OWNS:
- Class/type taxonomy and stable IDs
- Generic defaults by class
- A compact pattern library (cross-cutting behavior bundles)
- Classification and inheritance rules (how to apply class + type + patterns)

This file DOES NOT OWN:
- Source credibility rules or evidence standards (`research_sources.md`, `reviews.md`)
- Seller/channel risk policy (`seller_instructions.md`)
- Tier construction rules (`pricing_tiers.md`)
- Output format/templates (`product_research_template.md`, `pricing_tier_template.md`)

---

## How callers should use this file

### Type matching (keywords-first, cues as guidance)
1) Score candidate Types by **keyword match** first.
2) Use **intent cues** only to:
   - break ties between keyword-matched Types, and/or
   - disambiguate collision-prone terms (e.g., “camera”).
3) If no Type has sufficient keyword match, route by Class.
4) If ambiguous, default to `misc_general.misc_durable`.

Collision rule:
- If the matched keywords include a collision-prone term (e.g., “camera”, “monitor”, “adapter”), require:
  - at least one additional disambiguating keyword from the Type’s keyword list, OR
  - a matching intent cue.
- Do not route on a single collision-prone keyword alone.

### Application order
Apply tuning in this order:
- Class defaults
- Class `patterns_applied`
- Type overrides (inheritance)
- Type `patterns_applied`

### Conflict resolution (when rules disagree)
Apply the more conservative rule in this order:
1) Safety and compliance
2) Fitment/compatibility
3) Fraud/counterfeit/channel risk
4) Reliability and durability
5) Performance and preference

---

## Inheritance rules (prevents duplication)

### Type record requirements
Each Type record MUST include:
- `parent`
- `patterns_applied` (may be empty: `[]`)
- `intent_cues` (may be empty: `[]`; use sparingly)
- `keywords` (must not be empty; avoid ultra-generic terms)

Everything else is inherited from the parent Class unless explicitly overridden.

### Merge semantics (authoritative)

#### required_checks
- `required_checks_final = UNION(class.required_checks, all_pattern.required_checks_add, type.required_checks_add)`

#### risk flags (Option A: monotonic “minimum risk”)
Risk values: `low < medium < high`

- Start with Class minimums.
- Apply Pattern minimums.
- Apply Type minimums.
- Final risk is the maximum (most conservative) per flag:

- `risk_final[flag] = MAX(class.risk_min[flag], patterns.risk_min[flag], type.risk_min[flag])`

Types and patterns MAY raise risk minimums. They MUST NOT lower them.

#### evidence bias (soft preference)
Evidence bias is a soft prioritization hint (ordering preference), not an admissibility rule.
Admissibility and credibility are owned by `research_sources.md` (which deep-links to `reviews.md`).

- `evidence_bias_up`: prioritize when available
- `evidence_bias_down`: do not treat as primary when stronger options exist

Effective bias is the union across Class + Patterns + Type. If the same item appears in both lists, treat it as neutral.

#### tiering posture
Tiering fields inherit. Types may override tiering hints.

#### patterns_applied
Patterns accumulate: Class patterns + Type patterns.

---

## Shared tuning knobs (the “API”)

### Required checks (canonical list)
- `compatibility_platform` (OS/ecosystem/interfaces)
- `compatibility_standards` (protocols/codecs/certifications/spec compliance)
- `fitment_dimensions` (size/clearance/weight/ergonomics)
- `power_and_charging` (voltage/wattage/battery/connectors)
- `materials_build` (materials, ingress rating, durability claims)
- `software_firmware` (versions, update policy, regressions)
- `privacy_security` (data collection, cloud dependence, permissions)
- `warranty_returns` (warranty terms, return friction)
- `total_cost_of_ownership` (consumables, subscriptions, replacements, maintenance)
- `safety_compliance` (certifications, recalls, hazard flags)
- `shipping_damage_assessment` (fragility, DOA risk, packaging patterns)

### Risk flags (values: `low`, `medium`, `high`)
- `risk_variance` (unit-to-unit variability)
- `risk_firmware` (software/firmware/app quality; for services: vendor-driven change risk)
- `risk_safety` (hazard potential)
- `risk_channel` (counterfeit/refurb-as-new, marketplace risk)
- `risk_privacy` (data exposure, cloud lock-in, surveillance)
- `risk_fitment` (returns due to fit/comfort/incompatibility)
- `risk_shipping` (damage-in-transit, DOA, fragile packaging)

### Evidence bias (normalized fields)
- `evidence_bias_up: [evidence_primary_docs, evidence_respected_publications, evidence_respected_individuals, evidence_crowdsourced]`
- `evidence_bias_down: [...]`

### Tiering posture (hints; not strict rules)
- `tier_count_hint` (3 or 5 typical)
- `tier_floor_warning` (short statement)
- `tier_unlocks` (list of common “pay more to get” unlocks)

---

## Intent cues (routing guidance)

Use intent cues only when they are true discriminators (keep cue usage minimal).

Common cue buckets (referenced by Types below):
- `cue_smart_home_ecosystem`: matter/thread/homekit/alexa/google home, hub, automations
- `cue_security_surveillance`: doorbell, indoor/outdoor cam, motion detection, recording/subscription
- `cue_networking_infrastructure`: router/mesh/ap/switch/vlan/qos/ssid/nas
- `cue_photo_video_creation`: lens/sensor/af/low light/video specs/color workflows
- `cue_power_delivery`: usb-c pd/pps/wattage/gan, chargers, power banks, adapters
- `cue_maker_diy`: soldering/components/dev boards/measurement tools

---

## Pattern library (compact)

Patterns are small, composable bundles that:
- add required checks
- raise minimum risks
- adjust evidence bias (soft preference)

Pattern fields:
- `required_checks_add: [...]`
- `risk_min: { flag: level, ... }`
- `evidence_bias_up: [...]`
- `evidence_bias_down: [...]`
- `notes`

### pattern_firmware_dependent
- required_checks_add: [`software_firmware`, `compatibility_platform`]
- risk_min: { risk_firmware: high }
- evidence_bias_up: [`evidence_crowdsourced`, `evidence_respected_publications`]
- evidence_bias_down: []
- notes: treat version/SKU/firmware as a first-class variable when feasible

### pattern_safety_sensitive
- required_checks_add: [`safety_compliance`, `warranty_returns`]
- risk_min: { risk_safety: high }
- evidence_bias_up: [`evidence_primary_docs`, `evidence_respected_publications`]
- evidence_bias_down: []
- notes: crowdsourced is early-warning, not proof of compliance

### pattern_fitment_sensitive
- required_checks_add: [`fitment_dimensions`, `warranty_returns`]
- risk_min: { risk_fitment: high }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- notes: demand measurable fitment criteria when possible

### pattern_privacy_sensitive
- required_checks_add: [`privacy_security`, `software_firmware`]
- risk_min: { risk_privacy: high, risk_firmware: high }
- evidence_bias_up: [`evidence_primary_docs`, `evidence_respected_publications`, `evidence_crowdsourced`]
- evidence_bias_down: []
- notes: confirm what data is collected, stored, and shared in practice

### pattern_counterfeit_prone
- required_checks_add: [`warranty_returns`]
- risk_min: { risk_channel: high }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- notes:
  - channel contamination handling is owned by `seller_instructions.md`
  - caller must consult `seller_instructions.md` when this pattern is applied

### pattern_tco_sensitive
- required_checks_add: [`total_cost_of_ownership`]
- risk_min: {}
- evidence_bias_up: [`evidence_crowdsourced`, `evidence_respected_publications`]
- evidence_bias_down: []
- notes: emphasize consumables, subscriptions, maintenance, and price hikes

### pattern_weather_exposed
- required_checks_add: [`materials_build`]
- risk_min: { risk_variance: medium }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- notes: prefer multi-season ownership signals over “new out of box” impressions

### pattern_fragile_shipping
- required_checks_add: [`shipping_damage_assessment`, `warranty_returns`]
- risk_min: { risk_shipping: high }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- notes: identify DOA/packaging patterns and return friction

### pattern_professional_dependency
- required_checks_add: [`warranty_returns`]
- risk_min: { risk_variance: medium }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_respected_individuals`]
- evidence_bias_down: []
- notes: treat downtime and support as first-class costs

---

## Class catalog (generic)

Class fields:
- includes / excludes
- decision drivers
- required_checks
- risk_min
- evidence_bias_up/down
- tiering_posture
- patterns_applied
- types (list of Type IDs)

### consumer_electronics
- includes: TVs, audio, smart-home, wearables, consumer cameras, consumer power/charging, consumer accessories
- excludes: general-purpose computers and networking infrastructure (default to `computing_it`)
- decision drivers: reliability, compatibility, performance, value
- required_checks: [`compatibility_platform`, `compatibility_standards`, `warranty_returns`]
- risk_min: { risk_firmware: medium, risk_channel: medium, risk_variance: medium, risk_safety: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_respected_individuals`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: avoid ecosystems with poor support and unreliable software
  - tier_unlocks: reliability, performance headroom, support/update policy
- patterns_applied: []
- types:
  - ce_display_devices
  - ce_audio_devices
  - ce_personal_audio
  - ce_cameras_imaging
  - ce_smart_home
  - ce_power_charging
  - ce_cables_adapters_mounts
  - ce_wearables
  - ce_gaming_hardware
  - ce_home_security_devices

### hobbyist_electronics
- includes: maker boards, components, soldering tools, measurement gear, DIY kits, niche electronics
- excludes: consumer “plug and play” devices
- decision drivers: correctness/spec compliance, documentation quality, reliability, safety, value
- required_checks: [`compatibility_standards`, `power_and_charging`, `warranty_returns`]
- risk_min: { risk_variance: medium, risk_safety: medium, risk_channel: medium, risk_firmware: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_primary_docs`, `evidence_respected_individuals`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: ultra-cheap tools/components often fail silently
  - tier_unlocks: accuracy, safety margins, documentation, durability
- patterns_applied: []
- types:
  - he_microcontrollers_sbc
  - he_components_passives
  - he_power_supplies_converters
  - he_soldering_rework_tools
  - he_test_measurement
  - he_kits_prototyping
  - he_fpga_radio_specialty

### computing_it
- includes: computers, networking infrastructure, storage, peripherals, productivity hardware
- decision drivers: reliability, compatibility, performance, support lifecycle, value
- required_checks: [`compatibility_platform`, `software_firmware`, `warranty_returns`]
- risk_min: { risk_firmware: medium, risk_variance: medium, risk_channel: medium, risk_safety: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_respected_individuals`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: “cheap now, unstable later” is common
  - tier_unlocks: support lifecycle, stability, performance per watt
- patterns_applied: [pattern_professional_dependency]
- types:
  - it_laptops
  - it_desktops
  - it_monitors
  - it_networking
  - it_storage
  - it_input_devices
  - it_audio_video_peripherals
  - it_webcams_conferencing
  - it_docks_adapters
  - it_printers_scanners

### software_services
- includes: SaaS, subscriptions, licenses, cloud services, developer tools
- decision drivers: total cost, lock-in, reliability/uptime, privacy/security, support
- required_checks: [`total_cost_of_ownership`, `privacy_security`, `warranty_returns`]
- risk_min: { risk_firmware: high, risk_privacy: medium, risk_variance: low, risk_channel: low, risk_safety: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_primary_docs`, `evidence_respected_individuals`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: “cheap” can hide lock-in and operational costs
  - tier_unlocks: better support/SLA, better controls, better integrations
- patterns_applied: [pattern_tco_sensitive]
- types:
  - sw_saas_b2c
  - sw_saas_b2b
  - sw_developer_tools
  - sw_cloud_infrastructure
  - sw_security_privacy_tools
  - sw_one_time_license

### home_kitchen
- includes: cookware, kitchen tools, small appliances, storage/organization, cleaning tools
- decision drivers: durability, usability, safety, value
- required_checks: [`materials_build`, `warranty_returns`]
- risk_min: { risk_variance: medium, risk_channel: medium, risk_safety: medium, risk_firmware: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: avoid unsafe low-end for heat/blade appliances
  - tier_unlocks: durability, ease of cleaning, safer controls
- patterns_applied: []
- types:
  - hk_cookware
  - hk_cutlery
  - hk_small_appliances
  - hk_coffee_tea
  - hk_food_storage
  - hk_kitchen_tools_gadgets
  - hk_cleaning_tools

### appliances_large
- includes: major appliances and installed home systems
- decision drivers: reliability, serviceability, warranty, total cost, energy use
- required_checks: [`warranty_returns`, `total_cost_of_ownership`, `shipping_damage_assessment`]
- risk_min: { risk_variance: high, risk_shipping: high, risk_safety: medium, risk_firmware: low, risk_privacy: low, risk_fitment: low, risk_channel: low }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_crowdsourced`, `evidence_primary_docs`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: service network matters more than marginal features
  - tier_unlocks: reliability, repairability, warranty, parts availability
- patterns_applied: [pattern_tco_sensitive, pattern_fragile_shipping]
- types:
  - la_refrigeration
  - la_laundry
  - la_dishwashers
  - la_cooking_ranges_ovens
  - la_hvac_related
  - la_water_heating

### home_improvement
- includes: tools, building materials, fixtures, electrical/plumbing components, home maintenance
- decision drivers: safety, durability, standards/spec compliance, value
- required_checks: [`safety_compliance`, `compatibility_standards`, `warranty_returns`]
- risk_min: { risk_safety: medium, risk_channel: medium, risk_variance: medium, risk_firmware: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_primary_docs`, `evidence_respected_individuals`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: avoid unsafe low-end on anything electrical/structural
  - tier_unlocks: safety margins, durability, better warranties
- patterns_applied: []
- types:
  - hi_hand_tools
  - hi_power_tools
  - hi_fasteners_hardware
  - hi_paint_finishes
  - hi_electrical
  - hi_plumbing
  - hi_lighting_fixtures
  - hi_flooring
  - hi_safety_gear
  - hi_storage_shelving

### automotive
- includes: accessories, electronics, maintenance tools/fluids, fitment-specific add-ons
- decision drivers: fitment/compatibility, safety, durability, value
- required_checks: [`fitment_dimensions`, `warranty_returns`, `safety_compliance`]
- risk_min: { risk_fitment: high, risk_safety: medium, risk_channel: medium, risk_variance: medium, risk_firmware: low, risk_privacy: low, risk_shipping: low }
- evidence_bias_up: [`evidence_crowdsourced`, `evidence_respected_publications`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: unknown-origin safety-critical accessories are false economy
  - tier_unlocks: fitment confidence, durability, better support
- patterns_applied: [pattern_fitment_sensitive]
- types:
  - auto_fitment_accessories
  - auto_roof_racks_cargo
  - auto_electronics_dashcams
  - auto_power_charging
  - auto_maintenance_tools
  - auto_emergency_safety
  - auto_fluids_consumables

### furniture_home
- includes: furniture, decor, storage solutions, lighting that does not require electrical code compliance
- decision drivers: durability, comfort, fitment, aesthetics, value
- required_checks: [`fitment_dimensions`, `materials_build`, `warranty_returns`, `shipping_damage_assessment`]
- risk_min: { risk_fitment: high, risk_shipping: high, risk_variance: medium, risk_channel: low, risk_safety: low, risk_firmware: low, risk_privacy: low }
- evidence_bias_up: [`evidence_crowdsourced`, `evidence_respected_publications`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: high-use items punish cheap frames/foam
  - tier_unlocks: comfort retention, durability, better materials
- patterns_applied: [pattern_fitment_sensitive, pattern_fragile_shipping]
- types:
  - fh_seating
  - fh_sleep_mattress_bed
  - fh_desks_tables
  - fh_storage_shelving
  - fh_lighting_decor

### clothing
- includes: apparel, outerwear, accessories (non-footwear)
- decision drivers: fit/comfort, materials, durability, care, value
- required_checks: [`fitment_dimensions`, `materials_build`, `warranty_returns`]
- risk_min: { risk_fitment: high, risk_variance: medium, risk_channel: medium, risk_shipping: low, risk_safety: low, risk_firmware: low, risk_privacy: low }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: inconsistent sizing and weak materials drive returns
  - tier_unlocks: better fabrics, better construction, fit consistency
- patterns_applied: [pattern_fitment_sensitive]
- types:
  - cl_casual
  - cl_workwear
  - cl_formal
  - cl_outerwear
  - cl_activewear
  - cl_underwear_socks
  - cl_accessories

### footwear
- includes: shoes, boots, sandals
- decision drivers: fit/comfort, durability, use-case performance, value
- required_checks: [`fitment_dimensions`, `materials_build`, `warranty_returns`]
- risk_min: { risk_fitment: high, risk_variance: medium, risk_channel: medium, risk_shipping: low, risk_safety: low, risk_firmware: low, risk_privacy: low }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: comfort and durability collapse at the bottom end
  - tier_unlocks: outsole durability, support, better uppers, fit consistency
- patterns_applied: [pattern_fitment_sensitive]
- types:
  - fw_sneakers_casual
  - fw_athletic_performance
  - fw_boots_work
  - fw_boots_outdoor
  - fw_dress_shoes
  - fw_sandals_slides

### health_beauty_personal_care
- includes: grooming, oral care, skincare, haircare, personal devices
- decision drivers: safety, efficacy, comfort, ecosystem costs, value
- required_checks: [`warranty_returns`, `total_cost_of_ownership`, `safety_compliance`]
- risk_min: { risk_safety: medium, risk_variance: medium, risk_channel: medium, risk_privacy: low, risk_firmware: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: unknown-brand devices can be unsafe and unreliable
  - tier_unlocks: comfort, durability, better consumable ecosystems
- patterns_applied: []
- types:
  - hb_grooming_electric
  - hb_oral_care
  - hb_skincare
  - hb_haircare_tools
  - hb_personal_health_devices
  - hb_fragrance

### pets
- includes: pet supplies, grooming, habitat, toys, health-related accessories
- decision drivers: safety, durability, pet acceptance, value
- required_checks: [`materials_build`, `warranty_returns`]
- risk_min: { risk_safety: medium, risk_variance: medium, risk_channel: low, risk_firmware: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: unsafe materials and weak construction dominate low-end
  - tier_unlocks: durability, safer materials, easier cleaning
- patterns_applied: []
- types:
  - pet_beds_crates
  - pet_toys_enrichment
  - pet_grooming
  - pet_feeders_waterers
  - pet_litter_habitat
  - pet_training_tools

### media_entertainment
- includes: books, games, physical media, collectibles, hobby kits (non-electronic)
- decision drivers: authenticity (if collectible), condition, value, compatibility (format)
- required_checks: [`warranty_returns`, `compatibility_platform`]
- risk_min: { risk_channel: medium, risk_variance: low, risk_shipping: low, risk_safety: low, risk_firmware: low, risk_privacy: low, risk_fitment: low }
- evidence_bias_up: [`evidence_crowdsourced`, `evidence_primary_docs`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: counterfeit and condition issues dominate the low end
  - tier_unlocks: authenticity confidence, better condition, provenance
- patterns_applied: []
- types:
  - me_books
  - me_tabletop_games_puzzles
  - me_video_games_physical
  - me_collectibles
  - me_hobby_kits

### office
- includes: office supplies and productivity peripherals (overlap with computing is allowed)
- decision drivers: reliability, usability, value
- required_checks: [`warranty_returns`, `compatibility_platform`]
- risk_min: { risk_variance: medium, risk_firmware: medium, risk_channel: low, risk_safety: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_respected_publications`, `evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: cheap peripherals can waste time (hidden cost)
  - tier_unlocks: ergonomics, reliability, better support
- patterns_applied: [pattern_professional_dependency]
- types:
  - of_stationery_supplies
  - of_productivity_peripherals
  - of_print_scan
  - of_conferencing
  - of_organization_storage

### travel_general
- includes: travel-specific convenience, organization, comfort, adapters
- excludes: apparel/footwear (route to clothing/footwear + context cues)
- decision drivers: portability, durability, compatibility (regions), value
- required_checks: [`warranty_returns`, `fitment_dimensions`]
- risk_min: { risk_shipping: medium, risk_channel: medium, risk_variance: low, risk_safety: low, risk_firmware: low, risk_privacy: low, risk_fitment: low }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: low-quality travel gear fails at the worst time
  - tier_unlocks: durability, materials, multi-region compatibility
- patterns_applied: []
- types:
  - tr_power_adapters_converters
  - tr_packing_organizers
  - tr_toiletry_containers_kits
  - tr_travel_comfort_sleep
  - tr_travel_security
  - tr_day_bags_small
  - tr_portable_hygiene

### outdoors
- includes: camping/hiking utility, weather-exposed durable goods
- excludes: apparel/footwear (route to clothing/footwear + outdoor context)
- decision drivers: durability, safety, weather resistance, usability, value
- required_checks: [`materials_build`, `warranty_returns`]
- risk_min: { risk_variance: medium, risk_safety: medium, risk_shipping: medium, risk_channel: low, risk_firmware: low, risk_privacy: low, risk_fitment: low }
- evidence_bias_up: [`evidence_crowdsourced`, `evidence_respected_publications`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: environment amplifies failures
  - tier_unlocks: weather resistance, durability, safer designs
- patterns_applied: [pattern_weather_exposed]
- types:
  - od_shelter_sleep_systems
  - od_cooking_fuel
  - od_hydration_water_treatment
  - od_lighting_navigation
  - od_portable_power
  - od_tools_utility
  - od_coolers_storage
  - od_safety_first_aid

### misc_general
- includes: anything not captured above
- decision drivers: value, reliability, fitment as applicable
- required_checks: [`warranty_returns`]
- risk_min: { risk_variance: medium, risk_channel: medium, risk_safety: low, risk_firmware: low, risk_privacy: low, risk_fitment: low, risk_shipping: low }
- evidence_bias_up: [`evidence_crowdsourced`]
- evidence_bias_down: []
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: unknown category: stay conservative
  - tier_unlocks: reliability, warranty, support
- patterns_applied: []
- types:
  - misc_consumable
  - misc_durable
  - misc_gift_item

---

## Type catalog (fully defined, inheritance-first)

Format (all fields required unless marked optional):
- `parent` (required)
- `patterns_applied` (required; may be `[]`)
- `intent_cues` (required; may be `[]`; keep minimal)
- `keywords` (required; must avoid ultra-generic collision terms)
- `required_checks_add` (optional)
- `risk_min` (optional)
- `evidence_bias_up` (optional)
- `evidence_bias_down` (optional)
- `tiering_posture` (optional override)

Keyword guidance:
- Avoid single ambiguous terms as keywords (e.g., “camera”, “device”, “monitor”).
- Prefer disambiguating phrases or adjacent technical terms (e.g., “mirrorless”, “doorbell camera”, “VLAN”).
- Use multi-word phrases when they prevent collisions.

### consumer_electronics

#### ce_display_devices
- parent: consumer_electronics
- patterns_applied: [pattern_firmware_dependent, pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["tv", "television", "oled", "mini led", "hdr", "dolby vision", "refresh rate", "panel"]
- required_checks_add: [fitment_dimensions]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: low-end panels and slow OS stacks drive long-term regret
  - tier_unlocks: motion/brightness, processing, firmware stability

#### ce_audio_devices
- parent: consumer_electronics
- patterns_applied: [pattern_firmware_dependent]
- intent_cues: []
- keywords: ["soundbar", "home theater", "receiver", "avr", "subwoofer", "bookshelf speakers"]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: weak DSP/software and poor support are persistent problems
  - tier_unlocks: clarity, connectivity, calibration/support

#### ce_personal_audio
- parent: consumer_electronics
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["headphones", "earbuds", "in ear", "over ear", "anc", "bluetooth codec", "multipoint"]
- required_checks_add: [compatibility_platform]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: comfort and connection stability often poor at the bottom
  - tier_unlocks: ANC, tuning, microphones, reliability

#### ce_cameras_imaging
- parent: consumer_electronics
- patterns_applied: [pattern_professional_dependency]
- intent_cues: [cue_photo_video_creation]
- keywords: ["mirrorless", "dslr", "lens", "sensor", "autofocus", "low light", "stabilization", "bitrate"]
- required_checks_add: [total_cost_of_ownership]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: weak lenses/sensors are hard limits
  - tier_unlocks: AF, low light, lens ecosystem, workflow features

#### ce_smart_home
- parent: consumer_electronics
- patterns_applied: [pattern_firmware_dependent, pattern_privacy_sensitive]
- intent_cues: [cue_smart_home_ecosystem]
- keywords: ["smart hub", "matter", "thread", "zigbee", "z-wave", "homekit", "alexa", "automation"]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: unstable apps and cloud lock-in dominate low-end
  - tier_unlocks: interoperability, reliability, privacy controls

#### ce_power_charging
- parent: consumer_electronics
- patterns_applied: [pattern_safety_sensitive, pattern_counterfeit_prone]
- intent_cues: [cue_power_delivery]
- keywords: ["usb c pd", "pps", "gan charger", "power bank", "wireless charger", "magsafe", "wattage"]
- required_checks_add: [power_and_charging, compatibility_standards]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: unsafe chargers are unacceptable false economy
  - tier_unlocks: safety margins, efficiency, compatibility

#### ce_cables_adapters_mounts
- parent: consumer_electronics
- patterns_applied: [pattern_fitment_sensitive, pattern_counterfeit_prone]
- intent_cues: []
- keywords: ["hdmi cable", "displayport", "usb cable", "thunderbolt", "dock", "hub", "vesa mount", "tv mount"]
- required_checks_add: [compatibility_standards, fitment_dimensions]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: noncompliant cables/adapters cause hidden failures
  - tier_unlocks: standards compliance, durability

#### ce_wearables
- parent: consumer_electronics
- patterns_applied: [pattern_firmware_dependent, pattern_privacy_sensitive]
- intent_cues: []
- keywords: ["smartwatch", "fitness tracker", "heart rate", "sleep tracking", "health tracking"]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: inaccurate sensors and bad apps render devices useless
  - tier_unlocks: sensors, battery, app quality

#### ce_gaming_hardware
- parent: consumer_electronics
- patterns_applied: [pattern_firmware_dependent, pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["controller", "gamepad", "latency", "wireless controller", "capture card"]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: latency and compatibility issues dominate low-end
  - tier_unlocks: lower latency, ergonomics, compatibility

#### ce_home_security_devices
- parent: consumer_electronics
- patterns_applied: [pattern_firmware_dependent, pattern_privacy_sensitive, pattern_weather_exposed]
- intent_cues: [cue_security_surveillance]
- keywords: ["doorbell camera", "security camera", "motion detection", "cloud recording", "local recording", "floodlight camera"]
- required_checks_add: [materials_build]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: privacy and reliability failures are high-cost
  - tier_unlocks: detection, storage options, privacy controls

### hobbyist_electronics

#### he_microcontrollers_sbc
- parent: hobbyist_electronics
- patterns_applied: [pattern_counterfeit_prone]
- intent_cues: [cue_maker_diy]
- keywords: ["arduino", "esp32", "raspberry pi", "microcontroller", "dev board", "gpio"]
- required_checks_add: [compatibility_platform, compatibility_standards]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: poor documentation and bad clones waste time
  - tier_unlocks: docs, toolchains, IO support

#### he_components_passives
- parent: hobbyist_electronics
- patterns_applied: [pattern_counterfeit_prone]
- intent_cues: [cue_maker_diy]
- keywords: ["resistor", "capacitor", "mosfet", "ic", "sensor module", "breakout board"]
- required_checks_add: [compatibility_standards]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: mislabeled or counterfeit components are common
  - tier_unlocks: traceability, spec compliance, consistency

#### he_power_supplies_converters
- parent: hobbyist_electronics
- patterns_applied: [pattern_safety_sensitive, pattern_counterfeit_prone]
- intent_cues: [cue_power_delivery, cue_maker_diy]
- keywords: ["bench power supply", "dc dc converter", "buck converter", "boost converter", "power supply", "ac dc adapter", "dc power adapter"]
- required_checks_add: [power_and_charging, safety_compliance]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: unsafe supplies can damage projects and be hazardous
  - tier_unlocks: protections, stability, safety margins

#### he_soldering_rework_tools
- parent: hobbyist_electronics
- patterns_applied: [pattern_safety_sensitive, pattern_tco_sensitive]
- intent_cues: [cue_maker_diy]
- keywords: ["soldering iron", "hot air rework", "rework station", "solder tips", "flux", "fume extractor"]
- required_checks_add: [total_cost_of_ownership]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: unstable temperature control ruins work
  - tier_unlocks: control accuracy, tip ecosystem, durability

#### he_test_measurement
- parent: hobbyist_electronics
- patterns_applied: [pattern_professional_dependency]
- intent_cues: [cue_maker_diy]
- keywords: ["multimeter", "oscilloscope", "logic analyzer", "signal generator", "probes"]
- required_checks_add: [compatibility_standards, safety_compliance]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: inaccurate tools cause false conclusions
  - tier_unlocks: accuracy, safety ratings, probes/features

#### he_kits_prototyping
- parent: hobbyist_electronics
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: [cue_maker_diy]
- keywords: ["breadboard", "jumper wires", "prototyping kit", "perfboard", "standoffs"]
- required_checks_add: [materials_build]
- tiering_posture:
  - tier_count_hint: 3
  - tier_floor_warning: low-quality kits waste time
  - tier_unlocks: instructions, parts quality

#### he_fpga_radio_specialty
- parent: hobbyist_electronics
- patterns_applied: [pattern_professional_dependency, pattern_counterfeit_prone]
- intent_cues: [cue_maker_diy]
- keywords: ["fpga", "sdr", "software defined radio", "rf", "gnu radio", "ham radio"]
- required_checks_add: [compatibility_platform, compatibility_standards]
- tiering_posture:
  - tier_count_hint: 5
  - tier_floor_warning: poor docs/tooling destroy ROI
  - tier_unlocks: toolchains, support, specs

### computing_it

#### it_laptops
- parent: computing_it
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["laptop", "notebook", "ultrabook", "workstation laptop"]
- required_checks_add: [total_cost_of_ownership]

#### it_desktops
- parent: computing_it
- patterns_applied: []
- intent_cues: []
- keywords: ["desktop", "tower", "mini pc", "small form factor"]

#### it_monitors
- parent: computing_it
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["computer monitor", "ultrawide monitor", "vesa", "displayport", "panel type"]
- required_checks_add: [compatibility_standards, fitment_dimensions]

#### it_networking
- parent: computing_it
- patterns_applied: [pattern_firmware_dependent]
- intent_cues: [cue_networking_infrastructure]
- keywords: ["router", "mesh wifi", "access point", "switch", "vlan", "qos", "ssid"]
- risk_min: { risk_firmware: high }

#### it_storage
- parent: computing_it
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["ssd", "nvme", "external drive", "backup drive", "nas", "nas storage", "raid", "drive bays", "zfs", "synology", "truenas"]
- required_checks_add: [compatibility_standards]

#### it_input_devices
- parent: computing_it
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["keyboard", "mouse", "trackball", "ergonomic mouse", "mechanical keyboard"]

#### it_audio_video_peripherals
- parent: computing_it
- patterns_applied: [pattern_firmware_dependent]
- intent_cues: []
- keywords: ["microphone", "audio interface", "capture card", "dac", "driver software"]
- risk_min: { risk_firmware: high }
- required_checks_add: [compatibility_platform]

#### it_webcams_conferencing
- parent: computing_it
- patterns_applied: [pattern_firmware_dependent]
- intent_cues: []
- keywords: ["webcam", "conference camera", "speakerphone", "noise suppression"]
- risk_min: { risk_firmware: high }
- required_checks_add: [compatibility_platform]

#### it_docks_adapters
- parent: computing_it
- patterns_applied: [pattern_counterfeit_prone, pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["usb c dock", "thunderbolt dock", "usb c hub", "power delivery", "display output"]
- required_checks_add: [compatibility_standards, power_and_charging]

#### it_printers_scanners
- parent: computing_it
- patterns_applied: [pattern_firmware_dependent, pattern_tco_sensitive]
- intent_cues: []
- keywords: ["laser printer", "inkjet printer", "scanner", "toner", "ink subscription"]
- risk_min: { risk_firmware: high }

### software_services

#### sw_saas_b2c
- parent: software_services
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["subscription", "premium plan", "pro plan", "monthly", "annual"]

#### sw_saas_b2b
- parent: software_services
- patterns_applied: [pattern_tco_sensitive, pattern_privacy_sensitive]
- intent_cues: []
- keywords: ["seats", "admin console", "sso", "audit logs", "enterprise plan"]

#### sw_developer_tools
- parent: software_services
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["developer tools", "ci", "cd", "linter", "formatter", "ide plugin"]

#### sw_cloud_infrastructure
- parent: software_services
- patterns_applied: [pattern_tco_sensitive, pattern_privacy_sensitive]
- intent_cues: []
- keywords: ["cloud hosting", "managed database", "object storage", "kubernetes", "egress fees"]

#### sw_security_privacy_tools
- parent: software_services
- patterns_applied: [pattern_privacy_sensitive]
- intent_cues: []
- keywords: ["vpn", "password manager", "endpoint security", "privacy tool"]

#### sw_one_time_license
- parent: software_services
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["perpetual license", "one time purchase", "lifetime license"]

### home_kitchen

#### hk_cookware
- parent: home_kitchen
- patterns_applied: []
- intent_cues: []
- keywords: ["stainless steel pan", "cast iron", "nonstick pan", "dutch oven", "saucepan"]

#### hk_cutlery
- parent: home_kitchen
- patterns_applied: [pattern_safety_sensitive, pattern_tco_sensitive]
- intent_cues: []
- keywords: ["chef knife", "paring knife", "knife set", "sharpening stone", "honing rod"]
- required_checks_add: [total_cost_of_ownership]

#### hk_small_appliances
- parent: home_kitchen
- patterns_applied: [pattern_safety_sensitive, pattern_firmware_dependent]
- intent_cues: []
- keywords: ["air fryer", "blender", "toaster oven", "pressure cooker", "smart appliance"]
- required_checks_add: [power_and_charging]

#### hk_coffee_tea
- parent: home_kitchen
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["espresso machine", "coffee grinder", "drip coffee maker", "pod machine", "electric kettle"]

#### hk_food_storage
- parent: home_kitchen
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["food storage containers", "airtight containers", "glass containers", "lid seal"]
- required_checks_add: [materials_build]

#### hk_kitchen_tools_gadgets
- parent: home_kitchen
- patterns_applied: []
- intent_cues: []
- keywords: ["kitchen scale", "instant read thermometer", "spatula", "tongs", "microplane"]

#### hk_cleaning_tools
- parent: home_kitchen
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["dish brush", "scrubber", "cleaning brush", "replaceable head"]

### appliances_large

#### la_refrigeration
- parent: appliances_large
- patterns_applied: [pattern_tco_sensitive, pattern_fragile_shipping]
- intent_cues: []
- keywords: ["refrigerator", "freezer", "ice maker", "counter depth"]

#### la_laundry
- parent: appliances_large
- patterns_applied: [pattern_tco_sensitive, pattern_fragile_shipping]
- intent_cues: []
- keywords: ["washer", "dryer", "front load", "top load"]

#### la_dishwashers
- parent: appliances_large
- patterns_applied: [pattern_fragile_shipping]
- intent_cues: []
- keywords: ["dishwasher", "third rack", "quiet dba"]

#### la_cooking_ranges_ovens
- parent: appliances_large
- patterns_applied: [pattern_fragile_shipping, pattern_safety_sensitive]
- intent_cues: []
- keywords: ["range", "oven", "cooktop", "induction", "gas range"]

#### la_hvac_related
- parent: appliances_large
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["thermostat", "air conditioner", "heat pump", "air handler", "ventilation"]

#### la_water_heating
- parent: appliances_large
- patterns_applied: [pattern_tco_sensitive, pattern_safety_sensitive]
- intent_cues: []
- keywords: ["water heater", "tankless", "boiler", "gas water heater", "electric water heater"]

### home_improvement

#### hi_hand_tools
- parent: home_improvement
- patterns_applied: [pattern_professional_dependency]
- intent_cues: []
- keywords: ["wrench", "socket set", "screwdriver", "pliers", "ratchet"]

#### hi_power_tools
- parent: home_improvement
- patterns_applied: [pattern_safety_sensitive, pattern_tco_sensitive]
- intent_cues: []
- keywords: ["drill", "impact driver", "circular saw", "battery platform", "cordless tool"]

#### hi_fasteners_hardware
- parent: home_improvement
- patterns_applied: []
- intent_cues: []
- keywords: ["screws", "anchors", "fasteners", "hinges", "brackets"]

#### hi_paint_finishes
- parent: home_improvement
- patterns_applied: []
- intent_cues: []
- keywords: ["paint", "primer", "stain", "polyurethane", "sealant"]

#### hi_electrical
- parent: home_improvement
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["outlet", "breaker", "wiring", "switch", "electrical panel", "gfci"]
- required_checks_add: [compatibility_standards]

#### hi_plumbing
- parent: home_improvement
- patterns_applied: []
- intent_cues: []
- keywords: ["faucet", "valve", "pipe fitting", "toilet", "shutoff valve"]

#### hi_lighting_fixtures
- parent: home_improvement
- patterns_applied: [pattern_firmware_dependent]
- intent_cues: []
- keywords: ["light fixture", "recessed lighting", "led driver", "dimmer", "smart lighting"]
- required_checks_add: [compatibility_standards]

#### hi_flooring
- parent: home_improvement
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["flooring", "laminate", "luxury vinyl", "tile", "underlayment"]
- required_checks_add: [materials_build]

#### hi_safety_gear
- parent: home_improvement
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["respirator", "gloves", "goggles", "hearing protection"]

#### hi_storage_shelving
- parent: home_improvement
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["garage shelving", "storage rack", "wall shelving", "load rating"]

### automotive

#### auto_fitment_accessories
- parent: automotive
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["floor mats", "seat cover", "cargo liner", "vehicle specific"]

#### auto_roof_racks_cargo
- parent: automotive
- patterns_applied: [pattern_fitment_sensitive, pattern_safety_sensitive]
- intent_cues: []
- keywords: ["crossbars", "roof rack", "cargo box", "fit kit", "vehicle fitment"]

#### auto_electronics_dashcams
- parent: automotive
- patterns_applied: [pattern_firmware_dependent, pattern_privacy_sensitive]
- intent_cues: []
- keywords: ["dash cam", "parking mode", "hardwire kit", "cloud upload"]

#### auto_power_charging
- parent: automotive
- patterns_applied: [pattern_safety_sensitive, pattern_counterfeit_prone]
- intent_cues: []
- keywords: ["car charger", "12v usb c", "inverter", "fuse tap"]

#### auto_maintenance_tools
- parent: automotive
- patterns_applied: [pattern_professional_dependency]
- intent_cues: []
- keywords: ["obd2", "torque wrench", "jack stands", "code reader"]

#### auto_emergency_safety
- parent: automotive
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["jump starter", "tire inflator", "emergency kit", "roadside kit"]

#### auto_fluids_consumables
- parent: automotive
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["engine oil", "coolant", "air filter", "cabin filter", "wiper fluid"]

### furniture_home

#### fh_seating
- parent: furniture_home
- patterns_applied: [pattern_fitment_sensitive, pattern_fragile_shipping]
- intent_cues: []
- keywords: ["sofa", "chair", "recliner", "sectional", "seat depth"]

#### fh_sleep_mattress_bed
- parent: furniture_home
- patterns_applied: [pattern_fitment_sensitive, pattern_fragile_shipping]
- intent_cues: []
- keywords: ["mattress", "bed frame", "mattress topper", "firmness"]

#### fh_desks_tables
- parent: furniture_home
- patterns_applied: [pattern_fitment_sensitive, pattern_fragile_shipping]
- intent_cues: []
- keywords: ["desk", "standing desk", "table", "desktop size"]

#### fh_storage_shelving
- parent: furniture_home
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["bookshelf", "cabinet", "dresser", "storage dimensions"]

#### fh_lighting_decor
- parent: furniture_home
- patterns_applied: [pattern_fragile_shipping]
- intent_cues: []
- keywords: ["lamp", "mirror", "wall art", "decor"]

### clothing

#### cl_casual
- parent: clothing
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["t shirt", "jeans", "hoodie", "casual shirt"]

#### cl_workwear
- parent: clothing
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["workwear pants", "durable pants", "work shirt", "reinforced"]

#### cl_formal
- parent: clothing
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["suit", "dress shirt", "blazer", "formalwear"]

#### cl_outerwear
- parent: clothing
- patterns_applied: [pattern_weather_exposed, pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["rain jacket", "parka", "insulated jacket", "shell jacket"]

#### cl_activewear
- parent: clothing
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["base layer", "performance fabric", "moisture wicking"]

#### cl_underwear_socks
- parent: clothing
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["underwear", "socks", "waistband", "seamless"]

#### cl_accessories
- parent: clothing
- patterns_applied: []
- intent_cues: []
- keywords: ["belt", "hat", "scarf", "gloves"]

### footwear

#### fw_sneakers_casual
- parent: footwear
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["sneakers", "casual shoes", "insole", "arch support"]

#### fw_athletic_performance
- parent: footwear
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["running shoes", "training shoes", "stability", "cushioning"]

#### fw_boots_work
- parent: footwear
- patterns_applied: [pattern_fitment_sensitive, pattern_safety_sensitive]
- intent_cues: []
- keywords: ["work boots", "safety toe", "slip resistant", "ankle support"]

#### fw_boots_outdoor
- parent: footwear
- patterns_applied: [pattern_weather_exposed, pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["hiking boots", "waterproof boots", "gore tex", "trail"]

#### fw_dress_shoes
- parent: footwear
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["dress shoes", "oxfords", "loafers", "leather upper"]

#### fw_sandals_slides
- parent: footwear
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["sandals", "slides", "footbed", "strap fit"]

### health_beauty_personal_care

#### hb_grooming_electric
- parent: health_beauty_personal_care
- patterns_applied: [pattern_tco_sensitive, pattern_safety_sensitive]
- intent_cues: []
- keywords: ["trimmer", "electric shaver", "clipper", "replacement blades"]

#### hb_oral_care
- parent: health_beauty_personal_care
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["electric toothbrush", "water flosser", "brush heads", "oral irrigator"]

#### hb_skincare
- parent: health_beauty_personal_care
- patterns_applied: []
- intent_cues: []
- keywords: ["cleanser", "moisturizer", "serum", "sunscreen", "retinol"]

#### hb_haircare_tools
- parent: health_beauty_personal_care
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["hair dryer", "straightener", "curling iron", "heat protectant"]

#### hb_personal_health_devices
- parent: health_beauty_personal_care
- patterns_applied: [pattern_privacy_sensitive]
- intent_cues: []
- keywords: ["blood pressure monitor", "pulse oximeter", "digital thermometer", "smart scale", "ecg device"]
- risk_min: { risk_privacy: high }

#### hb_fragrance
- parent: health_beauty_personal_care
- patterns_applied: []
- intent_cues: []
- keywords: ["cologne", "perfume", "fragrance", "eau de parfum"]

### pets

#### pet_beds_crates
- parent: pets
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["pet crate", "pet bed", "carrier size", "crate dimensions"]

#### pet_toys_enrichment
- parent: pets
- patterns_applied: []
- intent_cues: []
- keywords: ["chew toy", "puzzle feeder", "enrichment toy", "durable toy"]

#### pet_grooming
- parent: pets
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["pet brush", "deshedding", "shampoo", "grooming tool"]

#### pet_feeders_waterers
- parent: pets
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["pet fountain", "automatic feeder", "food safe", "water filter"]

#### pet_litter_habitat
- parent: pets
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["litter box", "litter system", "odor control", "replacement filters"]

#### pet_training_tools
- parent: pets
- patterns_applied: []
- intent_cues: []
- keywords: ["leash", "harness", "training collar", "treat pouch"]

### media_entertainment

#### me_books
- parent: media_entertainment
- patterns_applied: []
- intent_cues: []
- keywords: ["hardcover", "paperback", "edition", "box set"]

#### me_tabletop_games_puzzles
- parent: media_entertainment
- patterns_applied: []
- intent_cues: []
- keywords: ["board game", "tabletop game", "card game", "jigsaw puzzle"]

#### me_video_games_physical
- parent: media_entertainment
- patterns_applied: []
- intent_cues: []
- keywords: ["disc", "cartridge", "physical copy", "region locked"]
- required_checks_add: [compatibility_platform]

#### me_collectibles
- parent: media_entertainment
- patterns_applied: [pattern_counterfeit_prone]
- intent_cues: []
- keywords: ["limited edition", "signed", "graded", "authenticity", "provenance"]
- risk_min: { risk_channel: high }

#### me_hobby_kits
- parent: media_entertainment
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["model kit", "hobby kit", "instructions", "parts fit"]

### office

#### of_stationery_supplies
- parent: office
- patterns_applied: []
- intent_cues: []
- keywords: ["pens", "notebook", "paper", "stationery"]

#### of_productivity_peripherals
- parent: office
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["footrest", "desk mat", "monitor arm", "ergonomic", "desk organizer"]

#### of_print_scan
- parent: office
- patterns_applied: [pattern_firmware_dependent, pattern_tco_sensitive]
- intent_cues: []
- keywords: ["office printer", "document scanner", "toner cost", "ink cost"]
- risk_min: { risk_firmware: high }

#### of_conferencing
- parent: office
- patterns_applied: [pattern_firmware_dependent]
- intent_cues: []
- keywords: ["speakerphone", "conference mic", "conference camera", "driver software"]
- risk_min: { risk_firmware: high }

#### of_organization_storage
- parent: office
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["filing", "drawer organizer", "shelf organizer", "dimensions"]

### travel_general

#### tr_power_adapters_converters
- parent: travel_general
- patterns_applied: [pattern_safety_sensitive, pattern_counterfeit_prone]
- intent_cues: []
- keywords: ["travel adapter", "plug adapter", "voltage converter", "universal adapter"]
- required_checks_add: [power_and_charging, compatibility_standards]

#### tr_packing_organizers
- parent: travel_general
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["packing cubes", "compression bag", "organizer dimensions"]

#### tr_toiletry_containers_kits
- parent: travel_general
- patterns_applied: [pattern_fitment_sensitive, pattern_tco_sensitive]
- intent_cues: []
- keywords: ["toiletry kit", "travel bottles", "tsa compliant", "leakproof"]

#### tr_travel_comfort_sleep
- parent: travel_general
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["travel pillow", "sleep mask", "earplugs", "neck pillow"]

#### tr_travel_security
- parent: travel_general
- patterns_applied: [pattern_counterfeit_prone]
- intent_cues: []
- keywords: ["travel lock", "luggage lock", "tracker", "anti theft"]

#### tr_day_bags_small
- parent: travel_general
- patterns_applied: [pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["sling bag", "day bag", "small backpack", "packable bag"]

#### tr_portable_hygiene
- parent: travel_general
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["sanitizer", "travel wipes", "portable hygiene", "refill packs"]

### outdoors

#### od_shelter_sleep_systems
- parent: outdoors
- patterns_applied: [pattern_weather_exposed, pattern_fitment_sensitive]
- intent_cues: []
- keywords: ["tent", "sleeping bag", "sleeping pad", "r value", "waterproof rating"]

#### od_cooking_fuel
- parent: outdoors
- patterns_applied: [pattern_safety_sensitive, pattern_weather_exposed]
- intent_cues: []
- keywords: ["camp stove", "isobutane", "fuel canister", "backpacking stove"]

#### od_hydration_water_treatment
- parent: outdoors
- patterns_applied: [pattern_safety_sensitive, pattern_weather_exposed]
- intent_cues: []
- keywords: ["water filter", "water purification", "hydration bladder", "microfilter"]

#### od_lighting_navigation
- parent: outdoors
- patterns_applied: [pattern_weather_exposed]
- intent_cues: []
- keywords: ["headlamp", "lantern", "gps", "battery life", "ip rating"]

#### od_portable_power
- parent: outdoors
- patterns_applied: [pattern_safety_sensitive, pattern_weather_exposed]
- intent_cues: []
- keywords: ["portable power station", "solar charger", "camp battery", "inverter"]

#### od_tools_utility
- parent: outdoors
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["multitool", "utility tool", "field repair"]

#### od_coolers_storage
- parent: outdoors
- patterns_applied: [pattern_fitment_sensitive, pattern_weather_exposed]
- intent_cues: []
- keywords: ["cooler", "ice retention", "insulated", "volume liters"]

#### od_safety_first_aid
- parent: outdoors
- patterns_applied: [pattern_safety_sensitive]
- intent_cues: []
- keywords: ["first aid kit", "emergency kit", "tourniquet", "outdoor safety"]

### misc_general

#### misc_consumable
- parent: misc_general
- patterns_applied: [pattern_tco_sensitive]
- intent_cues: []
- keywords: ["replacement", "refill", "cartridge", "filter", "blade"]

#### misc_durable
- parent: misc_general
- patterns_applied: []
- intent_cues: []
- keywords: ["durable good", "household item"]

#### misc_gift_item
- parent: misc_general
- patterns_applied: []
- intent_cues: []
- keywords: ["gift", "present", "novelty", "stocking stuffer"]
