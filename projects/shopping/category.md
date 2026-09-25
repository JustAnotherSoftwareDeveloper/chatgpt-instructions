# Category Registry

## Purpose
Define every supported Shopping Category and the complete delta owned by that Category.

A Category entry is the sole live definition of that Category. Adding or changing a Category should require editing this file only unless the generic hierarchy contract itself changes.

Apply registry entries only through the inheritance, Merge, and Override semantics in `product_hierarchy.md`.

---

# CATEGORY: Kitchen Knives

Parent: Home & Kitchen

Inheritance: `Base -> Home & Kitchen -> Kitchen Knives`

## Match
Use when:
- kitchen cutlery characteristics such as blade geometry, grind, steel/heat treatment, edge behavior, sharpening, maintenance, knife ergonomics, or provenance materially affect the purchase.

## Optimize
- cutting performance appropriate to use;
- durability and maintenance fit;
- geometry/steel/heat-treatment balance rather than spec-sheet prestige;
- trustworthy product identity and provenance.

## Shared domain behavior

### Do not steel-shop
Steel name alone is not a quality ranking.

Evaluate, as applicable:
- blade geometry/grind;
- heat-treatment/hardness execution;
- edge geometry/sharpening state;
- steel toughness/wear/corrosion/sharpening characteristics;
- QC consistency;
- user technique and maintenance.

A modest steel with excellent geometry/heat treatment can be a better cutting tool than a prestige steel with poor execution. Do not infer heat-treatment quality from nominal HRC alone.

### Geometry is first-class
Distinguish where evidence permits:
- spine/blade thickness;
- behind-the-edge thickness;
- primary grind shape;
- distal taper;
- edge angle/bevel geometry;
- blade height/profile;
- convex/hollow/flat characteristics.

Use these to reason about cutting resistance, wedging, food release, steering, robustness, sharpening/thinning, and suitability for dense foods.

Factory sharpness is not a substitute for underlying geometry.

### Edge tradeoff model
Do not optimize edge retention, toughness, or sharpenability in isolation.

Map the tradeoff to:
- cutting technique;
- food mix;
- cutting board;
- sharpening ability/willingness;
- tolerance for chipping, rolling, staining, or maintenance.

Harder/more wear-resistant edges may retain slicing performance longer but can demand more sharpening effort or offer less abuse tolerance depending on steel/geometry/heat treatment.

Tougher/softer constructions may tolerate rougher use and easier maintenance while requiring more frequent touch-up.

### Maintenance behavior
Maintenance differences can materially affect product fit when reactive/carbon/semi-stainless steel, unusual sharpening requirements, service access, or long-term thinning burden are involved.

Consider corrosion/reactivity, drying/oiling/patina needs, handle care, touch-up frequency, sharpening method/service, and long-term thinning where relevant.

### Sharpening and edge claims
Separate:
- factory edge;
- underlying geometry;
- steel/heat treatment;
- sharpening response;
- long-term edge retention.

One factory-edge test cannot establish long-term sharpening behavior.

When comparing edge-retention claims, check sharpening angle/finish, test medium/use conditions, hardness/heat treatment, geometry, and whether the knives serve the same purpose.

### QC and unit variation
Knife QC can vary by line, maker, batch, and production method.

Assess as relevant:
- blade straightness;
- grind symmetry/consistency;
- overgrinds/low spots;
- taper;
- edge condition;
- handle fit;
- spine/choil finish;
- cladding/core exposure;
- warping/twisting.

Do not inflate isolated cosmetic anecdotes into a dominant quality judgment.

### Marketing translation
Do not assume:
- forged > stamped;
- more Damascus layers improve cutting;
- decorative cladding predicts core execution;
- Japanese/German origin alone predicts geometry/quality;
- "professional" means suitable for this user;
- higher hardness automatically means better.

Translate marketing terms into observable user consequences.

### Japanese vs Western framing
Use these as broad traditions, not quality tiers. Modern products cross boundaries in geometry, hardness, profile, handles, maintenance, sharpening, and abuse tolerance.

Evaluate the actual model.

### Ergonomics and technique
Consider grip style, handle dimensions/material, weight/balance, spine/choil comfort, hand size, board size/height, cutting motion, and expected prep volume.

Subjective fit remains preference-dependent unless evidence shows a concrete ergonomic defect.

### Abuse boundaries
Bones/joints, frozen food, twisting/prying, edge-scraping, glass/stone/ceramic boards, and dishwasher use impose demands outside ordinary precision-knife use and can materially increase damage risk.

Do not recommend thin/hard precision geometry as if abuse-tolerant. Do not penalize a precision knife for tasks outside its intended role.

Board and technique can materially affect edge durability.

### Product identity and revision
Product identity, version, maker, or provenance can require explicit verification when:
- maker, steel, construction, or specifications changed across revisions;
- retailer-exclusive or regional variants create identity ambiguity;
- handcrafted/low-volume maker identity is a material part of value;
- relabel/private-label relationships materially affect what product is actually being evaluated;
- counterfeit/clone patterns make exact product identity uncertain.

Use `research_sources.md` to verify actual maker/manufacturer/line, exact length/steel/handle/region/revision, and which evidence applies to that identity.

Product identity/provenance and seller/channel risk are related but distinct. Apply `seller_instructions.md` only when the orchestrator's purchase-channel conditions make that authority active.

### Safety
Keep sharp-tool safety practical and proportional. Material/regulatory claims follow `research_sources.md`; ordinary handling does not require a safety lecture.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
Treat the knife as an interacting cutting system rather than a steel/spec list.

#### Geometry and grind
Blade thickness, behind-the-edge geometry, taper, grind shape, edge geometry, and resulting cutting resistance, wedging, food release, and robustness.

#### Steel and heat treatment
Steel family, hardness/heat treatment, and execution as they affect edge stability, wear, toughness, corrosion, and sharpenability. Do not infer knife quality from steel name alone.

#### Edge behavior
Useful edge retention, rolling/chipping resistance, touch-up response, and ease of restoring the edge for the intended user.

#### Toughness and abuse tolerance
Tolerance for hard contact, twisting, dense foods, poor boards, bones/frozen food, or misuse relevant to the user's habits.

#### Corrosion and care
Rust/staining sensitivity, drying/oiling/patina needs, handle care, and maintenance fit.

#### Ergonomics and balance
Handle geometry/material, grip options, spine/choil comfort, weight distribution, balance, and fatigue.

#### Construction and finish
Fit/finish, handle installation, grind consistency, edge condition, blade straightness, taper, and QC consistency.

#### Provenance and authenticity
Actual maker/manufacturer, line identity, authorized distribution, counterfeit/gray-market exposure, and whether marketing claims map to a known product.

### Merge: Source Playbooks -> Discovery guidance
Use multiple epistemic perspectives rather than many sources repeating the same steel/spec narrative.

#### Domain-native source archetypes
For Standard/Deep knife research, seek a useful mix from these roles when relevant:
- **maker/manufacturer documentation** for exact model/line identity;
- **metallurgy/materials specialist** for steel/heat-treatment/toughness/corrosion claims;
- **experienced sharpener or sharpening technical source** for edge behavior, sharpening response, thinning, and maintenance;
- **knife-focused reviewer/tester** for grind, geometry, profile, QC, balance, and direct knife comparisons;
- **culinary/test-kitchen practitioner** for real-food task behavior, fatigue, board interaction, and primary-tool fit;
- **serious owner/sharpening community** for QC variation, long-term edge/maintenance, service, and emerging issues;
- **authorized/specialist retailer** for exact variants, provenance, inspection/service offerings, and current market context.

No one archetype substitutes for all others.

#### Primary / documentary
Seek:
- maker/manufacturer specifications and line documentation;
- stated steel, hardness, dimensions, construction, origin, warranty;
- authorized-dealer listings for exact line/SKU details unavailable elsewhere.

Treat performance claims as claims, not proof.

#### Knife-specialist / technical
Seek sources that discuss actual grind, geometry, profile, balance, fit/finish, sharpening behavior, metallurgy, heat treatment, toughness, edge retention, corrosion, and QC.

Prioritize makers/sharpeners/technical specialists when they show concrete evidence and clear context.

#### Culinary / practitioner
Seek experienced cooks/testers comparing knives in representative prep tasks: fatigue, grip, food release, wedging, board interaction, repeated use, profile, tip utility, and control.

Professional preference is useful but not automatically representative of home users.

#### Owner / community
Seek serious knife/sharpening communities and long-term owners discussing QC variation, chipping/rolling, corrosion, handle issues, counterfeit listings, service, sharpening difficulty, and revision/batch differences.

#### Repair/service
Where relevant seek:
- sharpening/thinning professionals;
- maker warranty/service guidance;
- reports on rehandling, repair, grind correction, or difficult service cases.

#### Market / seller
Seek reputable knife specialists and maker-direct sources to establish:
- exact variant/provenance;
- normal street pricing;
- recurring sales where visible;
- authorized/distributor relationships;
- value-added services such as inspection or sharpening.

#### Useful query families
- `<model> grind geometry choil spine review`
- `<model> sharpening edge retention chipping`
- `<model> long term owner QC warp overgrind`
- `<model> vs <adjacent model> gyuto chef knife`
- `<maker/line> counterfeit authorized dealer`
- `<model> food release wedging carrot onion potato`
- `<model> price history sale discontinued`

#### Source traps
Actively watch for:
- ranking primarily by steel name;
- nominal hardness treated as proof of heat-treatment quality;
- Damascus/layer count/"Japanese steel"/"forged" standing in for cutting performance;
- retailer-generated comparisons favoring inventory;
- factory sharpness conflated with geometry or long-term edge behavior;
- edge retention conflated with toughness/sharpenability;
- many review sites repeating maker copy;
- a single choil photo or nominal spine thickness treated as a complete geometry model;
- enthusiast preference norms presented as universal culinary requirements.

### Merge: Pricing -> Value interpretation
Separate functional cutting-tool value from luxury/collector value.

Functional price drivers may include:
- grind/geometry execution;
- steel and heat-treatment execution;
- quality-control consistency;
- distal taper/profile work;
- handle materials and ergonomics;
- fit/finish;
- country/labor/manufacturing method;
- sharpening/service ecosystem;
- warranty/support/provenance.

Preference-heavy price drivers may include:
- decorative finishes and Damascus patterning;
- rare/exotic handle materials;
- artisan labor and low-volume production;
- maker reputation;
- collector demand, scarcity, or prestige.

Do not treat those premiums as defects when the user values craft, aesthetics, maker identity, or collecting. Do not present them as functional performance gains when they are not.

Steel name and layer count are not sufficient explanations for price or value.

A lower-priced knife with excellent geometry and execution may outperform a more expensive prestige knife in ordinary cutting. Conversely, better fit/finish, QC, comfort, craft, or maintenance fit may justify higher spend even when raw cutting performance is similar.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
Promote knife-specific concerns into workflow roles only when triggered:
- make maintenance a **primary differentiator** when the user requests low/zero maintenance, reactive/carbon/semi-stainless steel is under consideration, sharpening/service burden differs materially, the user does not sharpen and service access/cost differs, or long-term thinning burden is materially different;
- make QC/consistency a **primary differentiator** when the recurring-signal threshold in `reviews.md` is met for material defects, maker/line variation is known to be meaningful, the buyer cannot easily inspect/return, or premium pricing depends heavily on execution/finish;
- make robustness/toughness a **hard gate or primary differentiator** when the user's expected use includes bones/joints, frozen food, twisting/prying, edge scraping, very hard boards, dishwasher use, or similarly rough handling.

Otherwise keep those dimensions secondary unless they change fit among finalists.

### Merge: Product Research -> Candidate extraction
For plausible knife candidates, add where material:
- intended knife role;
- broad geometry/grind character;
- steel/heat-treatment identity only when trustworthy;
- edge/maintenance posture;
- robustness/abuse posture;
- QC/revision/provenance warning;
- likely sharpening/service burden.

Do not eliminate a candidate merely because precise enthusiast measurements are unavailable; distinguish unknown evidence from a negative product trait.

### Merge: Product Research -> Hard gates and identity
Add knife-specific checks where material:
- knife role matches the actual cutting task;
- expected abuse does not exceed the geometry/edge system's reasonable tolerance;
- maintenance/reactivity burden fits the user's hard requirements;
- exact steel/length/handle/revision is sufficiently established for variant-sensitive claims;
- counterfeit/relabel ambiguity is bounded when product identity itself is uncertain.

### Merge: Product Research -> Finalist extraction
For serious knife finalists, add where evidence exists:
- geometry/grind/taper observations;
- edge behavior and sharpening response;
- robustness/chipping/rolling context;
- corrosion/reactivity and care;
- QC/batch variation;
- handle/grip/balance behavior;
- provenance/version confidence;
- long-term thinning/service implications when material.

### Merge: Product Research -> Comparison and evidence use
For recommendation-changing differences, prefer the knife-specific chain:

`geometry / profile / heat treatment / edge system / construction -> cutting / edge / handling behavior -> tradeoff -> fit for foods, technique, board, maintenance`

Do not infer this chain from steel name, nominal HRC, a choil photo, or marketing alone.

### Merge: Product Research -> Synthesis / decision boundary
When the comparison is close, state whether the practical boundary is driven by:
- cutting geometry/performance;
- robustness;
- maintenance/sharpening;
- ergonomics/technique;
- QC/provenance;
- craft/aesthetics/value.

Avoid universal "better knife" language when the real difference is user fit.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Market segmentation
Add knife-specific production/execution/value families to the generic market map where they are supported, such as:
- broad mass-market production;
- enthusiast/specialist production with stronger geometry/execution focus;
- higher-touch or low-volume production;
- artisan/hand-finished work;
- collector/luxury territory where craft, rarity, maker identity, or materials dominate.

These are analytical examples, not mandatory permanent buckets. Discover the actual market structure and allow families to overlap in price.

Use these families to explain how spend changes within or across the knife market rather than treating Budget/Midrange/Premium labels as the market structure itself.

### Merge: Pricing Tiers -> Tier validity
A higher knife tier/region should be justified by one or more concrete changes such as:
- geometry/grind execution;
- heat-treatment/edge execution in context;
- QC consistency;
- taper/profile/finish work;
- ergonomics/handle execution;
- sharpening/service/provenance support;
- artisan labor/craft/rarity when that is the actual value proposition.

Steel name, Damascus layer count, origin label, nominal HRC, or "forged" marketing alone do not validate a higher tier.

### Merge: Pricing Tiers -> Marginal-spend analysis
For each meaningful step up, identify whether extra money primarily buys:
- functional cutting/handling improvement;
- consistency/QC;
- finish/ergonomics;
- service/provenance;
- craft/maker labor;
- aesthetics/materials;
- rarity/collector value.

Do not disguise craft/collector spend as proportional functional improvement.

### Merge: Pricing Tiers -> Diminishing-returns interpretation
For Kitchen Knives, distinguish where useful between:
- **functional-return flattening** - additional spend produces smaller gains in cutting/ownership performance;
- **craft/preference escalation** - spend can continue buying finish, maker labor, aesthetics, materials, rarity, or collector value after functional returns flatten.

Apply the reusable definition from `pricing.md`. Do not describe the second track as irrational when the user values it.

## Vendor Research contributions

### Merge: Vendor Research -> Ecosystem segmentation
When relevant distinguish among:
- actual makers/manufacturers;
- brands relying partly or heavily on OEM/ODM/private-label production;
- importers/distributors;
- specialist knife retailers;
- sharpening/service-oriented retailers;
- artisan/low-volume makers;
- marketplaces/general retailers where channel risk or curation differs materially.

Do not collapse maker quality, distributor role, and retailer quality into one "brand reputation" concept.

### Merge: Vendor Research -> Vendor normalization
For knife manufacturers/brands add where material:
- actual maker/OEM/private-label relationship;
- design/heat-treatment/manufacturing control where knowable;
- line architecture by geometry/use rather than steel prestige alone;
- QC/batch consistency;
- revision cadence;
- sharpening/service ecosystem;
- importer/distributor relationships;
- continuity in the category.

For knife retailers/dealers add where material:
- category-native curation competence;
- exact variant/provenance accuracy;
- authorized/import relationships;
- inspection/QC services;
- sharpening/setup/thinning services;
- ability to explain geometry/use rather than merely repeat steel specs;
- return handling for unit-variation problems.

## Quick Check contributions

### Merge: Quick Check -> Target identity
For a named knife verify only the variant fields needed for the question, commonly:
- length;
- steel/core/cladding when variant-sensitive;
- handle/version;
- region/import version;
- revision or maker relationship when it changed;
- stated condition for a listing.

### Merge: Quick Check -> Hard gates
If the user's stated hard requirements conflict with the shared knife maintenance or abuse boundaries, treat that conflict as a hard failure for the exact target rather than expanding into full Product Research.

### Merge: Quick Check -> Decision questions
Useful knife-specific narrow questions include:
- Is this the exact steel/length/handle/revision being discussed?
- Does its geometry/profile fit the user's stated technique/tasks?
- Is there a recurring QC/chipping/warping issue that changes the narrow judgment?
- Does this seller/channel create provenance or warranty risk?

Use only the subset relevant to the request.

### Merge: Quick Check -> Deal / where-to-buy
When a concrete knife listing is in scope, add product/channel provenance checks appropriate to counterfeit, gray-market, regional-version, artisan-maker, or specialist-retailer risk without treating marketplace presence or low price alone as proof of a problem.

## Boundary
Chef's-Knife-specific primary-tool behavior belongs to the `Chef's Knife` Type entry in `type.md`; broader household behavior to the `Home & Kitchen` Class entry in `class.md`; generic evidence and source semantics remain in their owning authorities.

---

# CATEGORY: Major Appliances

Parent: Home & Kitchen

Inheritance: `Base -> Home & Kitchen -> Major Appliances`

## Match
Use when:
- the purchase is an ordinary freestanding or built-in major household appliance such as refrigeration, laundry, dishwashing, or cooking equipment;
- installation, serviceability, parts access, delivery, repair economics, or long ownership horizon materially affect the decision.

Do not use this Category for whole-building mechanical/electrical/plumbing systems that require system design, such as central HVAC, whole-home water treatment, or similar infrastructure, unless a future hierarchy entry explicitly covers them.

## Optimize
- core task performance;
- exact installation fit;
- serviceability and parts/network support;
- ownership-horizon reliability rather than feature count.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
In addition to applicable Home & Kitchen criteria, consider:

#### Installation fit
Exact dimensions, clearances, access path, hookups, venting, and configuration needed for the installation.

#### Core task performance
The appliance's actual cleaning, cooling, cooking, drying, washing, capacity, noise, or other category-native performance under representative use.

#### Serviceability and parts access
Parts availability, diagnostic/repair practicality, technician availability, service-network depth, and expected downtime burden.

#### Ownership-horizon reliability
Recurring component/model-family failure patterns and repair economics over the expected ownership period.

#### Resource efficiency
Energy/water use and operating cost where material, interpreted alongside capacity/performance rather than as an isolated badge.

#### Delivery / installation burden
Delivery, installation, haul-away, damage handling, and related ownership friction when material.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek:
- manufacturer installation manuals, parts diagrams, service/warranty terms, exact model specifications, and revision notices;
- ENERGY STAR or comparable efficiency registries where applicable;
- UL/NSF or category-relevant certification sources where material;
- CPSC/official recall records.

#### Method / test
Seek standardized testing for the appliance family's actual job: cleaning, cooling stability, capacity, energy/water use, noise, cycle performance, temperature behavior, or other relevant outputs.

#### Practitioner / repair
Seek appliance technicians and repair/service sources with exact model, family, or component-platform experience.

#### Owner / community
Seek long-term owner populations for model/family failures, noise/usability, and post-review-window behavior. When delivery/install/service experience matters, also seek those populations separately so `reviews.md` can interpret channel contamination correctly.

#### Market / seller
Seek delivery/install/haul-away terms, damaged-unit exchange process, regional service coverage, and retailer coordination with manufacturer warranty.

#### Useful query families
- `<model> service manual parts diagram`
- `<model> repair technician common failure`
- `<model> long term reliability <major component or failure mode>`
- `<model> installation clearance dimensions`
- `<model> energy noise test`

#### Source traps
De-prioritize:
- chain-retailer brand-comparison articles without original model-level evidence;
- brand-wide reliability sources that do not identify relevant appliance families;
- review pages where delivery/install and product experience cannot be distinguished when reliability is the research question;
- feature-count listicles without ownership-horizon evidence.

### Merge: Pricing -> Value interpretation
Interpret appliance value over the realistic ownership horizon, not just checkout price.

Material value drivers may include:
- core category performance and usable capacity;
- energy/water use where meaningful;
- noise and everyday ergonomics;
- parts availability, repairability, and service-network access;
- warranty execution and platform continuity;
- installation requirements and delivery complexity.

Count required installation kits, accessories, delivery/haul-away, and realistic service burden when they materially change effective cost. Do not pay a reliability premium based only on broad brand reputation without model/family evidence.

Treat added electronics/features as value only when the user benefits enough to justify the added complexity and ownership exposure.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- exact installation envelope, access path, hookups, and venting;
- household capacity/use pattern;
- service-area practicality and expected ownership horizon;
- noise, energy, and water priorities;
- tolerance for repair downtime;
- delivery, removal, and installation needs.

### Merge: Product Research -> Hard gates and identity
Apply the active Major Appliances criteria to establish, where material:
- exact model/suffix and regional configuration;
- installation dimensions, clearances, access, and hookups;
- required capacity or configuration;
- explicit serviceability requirements;
- active recall or support constraints affecting the exact model.

### Merge: Product Research -> Finalist extraction
Add where evidence exists:
- core category performance;
- model/family reliability signal and ownership horizon;
- parts and repair access;
- install/delivery burden;
- measured resource/noise behavior where relevant;
- warranty and practical service path;
- complexity that materially changes ownership burden.

Apply `research_sources.md` and `reviews.md` to these fields.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Tier validity
Require meaningful gains under the active Major Appliances criteria. Feature count, finish, or added complexity alone do not establish a higher functional tier.

### Merge: Pricing Tiers -> Marginal-spend analysis
Include material installation, delivery, operating-resource, and service consequences in the real step-up cost.

### Merge: Pricing Tiers -> Buying context
Account for delivery, haul-away, installation, damaged-unit exchange, and service facilitation when they materially change the purchase proposition.

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
For appliance manufacturers/brands add where material:
- parts/platform continuity;
- service-network practicality;
- warranty execution;
- model-family support history;
- documentation/diagnostic support.

For appliance retailers/dealers add where material:
- delivery damage/error handling;
- installation competence and subcontracting model;
- haul-away/exchange logistics;
- warranty/service coordination;
- regional service reach.

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify exact model suffix, regional configuration, dimensions, and any generation/revision relevant to the narrow question.

### Merge: Quick Check -> Hard gates
Apply installation/access/hookup, explicit serviceability, and active-recall constraints before judging value.

### Merge: Quick Check -> Deal / where-to-buy
Include delivery/install/haul-away costs and damaged-unit/large-item return handling when they can erase an apparent price advantage.

## Boundary
Generic evidence, review, seller, criterion, discovery, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Furniture / Home Decor

Parent: Home & Kitchen

Inheritance: `Base -> Home & Kitchen -> Furniture / Home Decor`

## Match
Use when:
- furniture construction, dimensions, comfort, materials, finish, spatial fit, delivery, repairability, or aesthetics materially affect the purchase.

## Optimize
- construction and ergonomic fit;
- room/access fit;
- durable ownership and repairability;
- aesthetics/design when they matter to the user.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
In addition to applicable Home & Kitchen criteria, consider:

#### Construction / materials
Frame, joinery, substrate, veneer/solid/composite use, upholstery/foam/hardware, finish, and how construction maps to wear, stability, and repairability.

#### Spatial fit
Room/access dimensions, clearance, circulation, modular configuration, and delivery path.

#### Ergonomic fit
Seat/table/storage dimensions, support, reach, load, and intended-duration comfort where relevant.

#### Finish / visual consistency
Color, finish, texture, proportion, design language, and production variation when appearance is material.

#### Repairability / restoration
Replaceable hardware/components, refinishing/reupholstery feasibility, and expected long-term maintainability.

#### Delivery / damage burden
Packaging, freight damage, assembly, room-of-choice/white-glove service, claim handling, and large-item return logistics when material.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek exact dimensions/configurations, materials/construction disclosures, care instructions, warranty, delivery/return terms, and relevant GREENGUARD/FSC/formaldehyde-related certifications when material.

#### Practitioner / expert
Seek interior designers for spatial/aesthetic fit and furniture makers, upholsterers, or repair/restoration professionals for construction, repairability, finish, joinery, and long-horizon ownership questions.

#### Owner / community
Seek real setup photos and long-term ownership reports for scale, finish/color variation, wear, comfort, and assembly. Separately seek freight/delivery and claim-handling experiences when buying-channel quality matters.

#### Market / seller
For bulky products seek delivery service level, freight/room-of-choice/white-glove options, assembly, return pickup/restocking, made-to-order terms, and damage-resolution documentation.

#### Useful query families
- `<model> frame construction joinery materials`
- `<brand/model> long term wear sagging finish`
- `<brand> delivery damage claim return`
- `<model> dimensions seat depth owner photos`
- `<brand> furniture repair restoration`

#### Source traps
De-prioritize:
- style/lifestyle coverage with no construction or ownership evidence;
- sources using material names without construction context;
- retailer photography as the only real-world scale/color source;
- mixed product/freight complaint pages when the question requires one of those signals specifically.

### Merge: Pricing -> Value interpretation
Separate construction/ownership value from design/craft/brand value.

Functional price drivers may include:
- frame/joinery/material execution;
- comfort/ergonomics;
- finish/QC consistency;
- repairability/refinishability;
- modularity/customization;
- durable hardware/upholstery;
- delivery/assembly/service quality.

Design authorship, custom work, special materials, and artisan execution can justify premiums when the user values them, but do not present visual similarity or brand name alone as evidence of longer life.

For bulky items include material delivery, assembly, damage-claim, return-pickup, and restocking costs in practical value.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- exact room and access dimensions;
- user ergonomics/load/use pattern;
- required material/finish/style constraints;
- repairability and expected ownership horizon;
- assembly/delivery tolerance;
- sensitivity to finish/color variation.

### Merge: Product Research -> Hard gates and identity
Apply the active Furniture / Home Decor criteria to verify, where material:
- room/access/clearance fit;
- required load or ergonomic fit;
- modular/configuration identity;
- non-negotiable material/finish requirements;
- delivery feasibility.

### Merge: Product Research -> Finalist extraction
Add where evidence exists:
- Construction / materials;
- Spatial fit and Ergonomic fit;
- Finish / visual consistency;
- Repairability / restoration;
- Delivery / damage burden;
- long-horizon wear patterns.

Apply `reviews.md` to owner/review evidence for these fields.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Market segmentation
Allow distinct value families such as flat-pack/value production, mass-market assembled furniture, higher-quality production furniture, design-led premium, custom/semi-custom, and artisan work when the market supports them. These may overlap in price.

### Merge: Pricing Tiers -> Tier validity
Require a coherent gain under the active Furniture / Home Decor criteria or a clearly identified design/craft proposition. Brand name and visual similarity alone do not validate the premium.

### Merge: Pricing Tiers -> Marginal-spend analysis
State whether extra spend primarily buys usable life, ergonomics, construction, repairability, finish consistency, customization, design/craft value, or logistics/service.

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
Add where material:
- construction transparency and material accuracy;
- finish/color consistency;
- spare hardware/component support;
- damage-claim and replacement behavior;
- threshold vs room-of-choice vs white-glove delivery model;
- assembly service;
- return logistics/cost for large items;
- made-to-order lead-time reliability.

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify exact size/configuration, material/finish, upholstery option, modular component set, and made-to-order vs stocked status when these change the judgment.

### Merge: Quick Check -> Hard gates
Check room/access dimensions, ergonomic/load requirements, and delivery feasibility before treating style or price as decisive.

### Merge: Quick Check -> Deal / where-to-buy
Include freight, assembly, return pickup/restocking, and damage-claim handling when they materially change an apparent deal.

## Boundary
Generic criterion, discovery, evidence, review, seller, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Cookware

Parent: Home & Kitchen

Inheritance: `Base -> Home & Kitchen -> Cookware`

## Match
Use when:
- the target is cookware or a cooking vessel/surface whose behavior depends materially on construction, thermal behavior, cooking surface, kitchen compatibility, maintenance, or repeated-use durability.

Do not route powered countertop appliances here merely because they are kitchen equipment.

## Optimize
- task-appropriate cooking behavior;
- construction/lifecycle rather than marketing materials alone;
- ergonomic and kitchen compatibility;
- maintenance and material/coating fit.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
In addition to applicable Home & Kitchen criteria, consider:

#### Construction / thermal behavior
Material stack/body construction as it affects responsiveness, heat distribution/retention, warping resistance, weight, and cooking behavior.

#### Cooking-surface behavior
Release/sticking, browning/searing, durability, coating/seasoning lifecycle, and suitability to intended foods/techniques.

#### Handle / hardware ergonomics
Attachment, balance, grip, heat transfer, lid/handle usability, and durability.

#### Kitchen compatibility
Cooktop/base fit, induction behavior where relevant, oven/broiler limits, dishwasher/utensil constraints, dimensions, and storage.

#### Maintenance / lifecycle
Seasoning, polishing, coating wear, cleaning restrictions, replacement parts/surfaces, and realistic service life.

#### Material / coating constraints
Food-contact material composition, coatings/linings, intended-use temperature limits, and user-specific material restrictions when they materially affect fit, including explicit PTFE/PFAS-related constraints when relevant.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek manufacturer construction/material documentation, dimensions, handle attachment, cooktop compatibility, oven/broiler limits, care instructions, and warranty.

When material/coating composition or food-contact safety is a decision question, seek authoritative documentation appropriate to the claim. For PTFE/PFAS-related constraints, explicitly seek exact coating/composition disclosures and relevant regulatory or authoritative safety material rather than relying on broad "non-toxic", "PFOA-free", or similar marketing.

#### Method / test
Seek repeatable cooking tests for heat distribution/responsiveness, searing/browning, sticking/release, pouring, handle temperature, warping, coating/surface durability, and cleanup after repeated use.

#### Practitioner / expert
Seek professional cooks, instructors, food-science/cookware testers, and repair/refinishing specialists for task-specific use questions.

#### Owner / community
Cast iron/carbon steel and similar enthusiast communities are useful discovery sources for seasoning, restoration, maintenance, warping, handle/hardware longevity, and long-term surface behavior.

#### Useful query families
- `<model> heat distribution responsiveness cooking test`
- `<model> warping handle rivet durability`
- `<model> nonstick coating long term`
- `<model> PTFE PFAS coating material disclosure`
- `<model> induction oven limit manual`
- `<model> seasoning restoration long term`

#### Source traps
De-prioritize:
- celebrity/influencer endorsements with no original cooking tests;
- sources organized primarily around layer count or metal-name prestige;
- testing based on one narrow cooking task when the research question is broader;
- brand material/safety marketing without discoverable underlying documentation.

### Merge: Pricing -> Value interpretation
Interpret value through task fit, construction, lifecycle, and maintenance.

Higher spend may buy:
- better thermal execution or warping resistance;
- more durable handles/hardware;
- better QC and finish;
- longer-lived cooking surfaces;
- broader cooktop/oven compatibility;
- easier parts/service/refinishing;
- craft/aesthetic value.

Do not use layer count, metal prestige, celebrity branding, or nominal oven temperature alone as proof of value. A replaceable/wear-prone coating may have a different rational ownership horizon from durable stainless or restorable seasoned surfaces.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- cooking tasks and batch size;
- stovetop/oven/broiler constraints;
- desired heat response/retention behavior;
- weight/handle/ergonomic limits;
- tolerance for seasoning, hand washing, polishing, or coating replacement;
- explicit material/coating restrictions;
- dishwasher/storage constraints.

### Merge: Product Research -> Candidate extraction
Add where material:
- construction relevant to thermal behavior;
- cooking-surface system;
- handle/hardware ergonomics;
- oven and cooktop compatibility;
- maintenance posture;
- likely lifecycle/replaceability of wear surfaces.

### Merge: Product Research -> Hard gates and identity
Apply the active Cookware criteria to verify, where material:
- cooktop compatibility and usable base size;
- required oven/broiler limits;
- unacceptable maintenance/coating/material constraints;
- weight/handle limitations when explicit;
- exact line/construction when similarly named variants differ materially.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Tier validity
Require meaningful gains under the active Cookware criteria. Layer count, exotic material labels, celebrity branding, or decorative finish alone do not establish proportional functional value.

### Merge: Pricing Tiers -> Marginal-spend analysis
State whether extra spend buys better thermal execution, lower warping risk, stronger handles/hardware, longer surface life, easier service/replacement, better ergonomics, broader compatibility, or primarily finish/craft/brand value.

### Merge: Pricing Tiers -> Diminishing-returns interpretation
Apply the generic pricing authority while separating functional cooking gains from finish, craft, prestige, or collection value once task fit and construction are already strong.

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
Add where material:
- construction consistency across lines;
- coating/surface lifecycle reputation;
- handle/hardware and replacement-part support;
- warranty exclusions that matter in ordinary use;
- continuity of lids, handles, or other replaceable components;
- repair/refinishing/reseasoning support where applicable.

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify exact size, line, construction, surface/coating generation, handle/lid variant, and regional model when those change compatibility or performance.

### Merge: Quick Check -> Hard gates
Check cooktop/oven compatibility, usable dimensions, maintenance requirements, and explicit material/coating constraints before judging value.

### Merge: Quick Check -> Decision questions
Useful narrow questions include whether the construction suits the user's cooking task, whether the wear surface has an acceptable expected life, and whether maintenance burden fits the user.

## Boundary
Generic criterion, material/safety evidence, discovery, review, seller, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Smart Home / Networking

Parent: Base

Inheritance: `Base -> Smart Home / Networking`

## Match
Use when:
- connected-device protocols, controllers, local/cloud architecture, network topology, firmware lifecycle, security posture, or interoperability materially affect the purchase.

## Optimize
- real interoperability in the user's system;
- resilient architecture and lifecycle support;
- network/topology fit where relevant;
- security/update posture.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
#### Real interoperability
Whether the required features work through the user's actual protocols, controllers, platforms, APIs, and device topology rather than merely appearing on a compatibility/logo list.

#### Local / cloud resilience
Which functions survive internet/vendor-cloud interruption, which require an account/subscription, and what local fallback exists.

#### Lifecycle support
Firmware quality, update cadence, end-of-life posture, API continuity, and support for installed hardware generations.

#### Security posture
Relevant vulnerability history, remediation behavior, authentication/update design, exposure model, and security track record.

#### Network / topology fit
For infrastructure products, fit to wired/wireless backhaul, coverage geometry, client/workload mix, VLAN/SSID/PoE needs, management model, and radio environment.

#### Integration quality
Automation reliability, API/SDK quality, event/state exposure, configuration depth, and troubleshooting visibility where relevant.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek manufacturer compatibility matrices, manuals, firmware/release notes, SDK/API documentation, support/EOL policies, and Matter/Thread/Zigbee/Z-Wave or other relevant certification registries.

For networking hardware seek exact hardware-revision specifications, supported management features, PoE/radio/port capabilities, and software-support lifecycle.

#### Method / test
Seek lab or technically transparent testing for throughput, range, roaming, latency, radio behavior, power, reliability, and interoperability. For security questions seek independent technical/security research and vulnerability records in addition to vendor material.

#### Practitioner / community
Seek network engineers, smart-home integrators, Home Assistant/platform communities, and technically strong owner forums for multi-device integration, firmware regressions, controller quirks, and long-running deployments.

#### Useful query families
- `<model> firmware regression release notes`
- `<model> home assistant integration local api`
- `<model> matter thread zigbee certification`
- `<model> cve security advisory`
- `<model> roaming latency throughput test`
- `<vendor> end of life support policy`

#### Source traps
De-prioritize:
- compatibility pages containing only protocol logos when feature-level interoperability is the question;
- vendor-only security material when independent security evidence exists;
- throughput pages centered on advertised PHY/link rates rather than tested behavior;
- reviews that do not identify the hardware/firmware revision when that distinction is material.

### Merge: Pricing -> Value interpretation
Connected-device value includes the system and lifecycle, not just hardware capability.

Account for:
- required hubs/controllers/subscriptions;
- local processing vs cloud/account dependence;
- support/EOL horizon;
- interoperability and API/integration quality;
- network-management capability and hardware headroom where relevant;
- security/update track record.

A cheaper device can become poor value if it requires recurring service fees, creates ecosystem lock-in, or has a short support life. Conversely, do not assume local-first or enterprise-like configurability is worth paying for when the user values simple managed convenience.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- required ecosystem/controller and exposed capabilities;
- local-only vs cloud-tolerant operation;
- protocol/radio and hub/controller dependencies;
- installation/power/wiring constraints;
- privacy/security posture;
- subscription/account requirements;
- network topology/workload for infrastructure products;
- ownership horizon and tolerance for vendor EOL.

### Merge: Product Research -> Market segmentation
Map products by architecture when that explains the market better than price: local-first vs cloud-first, controller/ecosystem, managed vs standalone, wired vs wireless/backhaul model, consumer convenience vs configurable infrastructure, and similar real design families.

### Merge: Product Research -> Hard gates and identity
Apply the active Smart Home / Networking criteria to verify, where material:
- exact protocol/radio/controller compatibility;
- required feature exposure in the user's actual ecosystem;
- electrical/wiring/PoE/regional compatibility;
- required local operation or acceptable cloud/account dependence;
- active support/EOL state;
- exact hardware generation/revision when capabilities differ.

### Merge: Product Research -> Finalist extraction
Add where evidence exists:
- interoperability path and controller dependencies;
- local/cloud failure behavior;
- firmware/support lifecycle;
- API/integration quality;
- network-management or topology fit;
- subscription/account implications.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Market segmentation
Allow price/value regions to reflect system architecture and support model, not just faster radios or more devices.

### Merge: Pricing Tiers -> Marginal-spend analysis
Identify whether extra spend buys better radios/backhaul, management, local processing, interoperability, support lifecycle, lower subscription burden, or mainly ecosystem convenience.

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
Add where material:
- firmware/update cadence and regression handling;
- vulnerability disclosure/remediation record;
- EOL/support-policy clarity;
- local-vs-cloud posture;
- API/SDK/integration openness;
- protocol/interoperability track record;
- documentation and troubleshooting support.

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify hardware generation/revision, firmware train, region, radio/protocol variant, controller/ecosystem, and account/subscription tier when capability depends on them.

### Merge: Quick Check -> Hard gates
Treat missing required ecosystem feature exposure, wiring/radio incompatibility, unacceptable cloud dependency, or unsupported/EOL status as narrow failures when explicitly required.

### Merge: Quick Check -> Outside comparables / escalation
Escalate when the answer depends on redesigning the user's network/controller architecture rather than evaluating the named device in the existing system.

## Boundary
Generic criterion, discovery, evidence/comparability, review, seller, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Audio / Headphones / Speakers

Parent: Base

Inheritance: `Base -> Audio / Headphones / Speakers`

## Match
Use when:
- acoustic performance, tuning, listening preference, fit/comfort, room interaction, active/wireless behavior, or measurement methodology materially affect the purchase.

## Optimize
- evidence-appropriate acoustic performance;
- tuning and fit for the actual listener/use;
- active-system ownership quality where applicable;
- preference-aware decision boundaries.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
#### Acoustic performance
Frequency response, distortion/output limits, directivity, isolation, latency, or other relevant acoustic/electroacoustic behavior.

#### Tuning / preference fit
Whether the product's voicing and presentation match the listener's preferences and use.

#### Fit / comfort / placement
Headphone seal, comfort, clamp and placement sensitivity; or speaker positioning, room interaction, listening distance, and dispersion fit.

#### Active-system quality
For wireless/active products: firmware/app behavior, battery aging, connectivity/codecs, ANC/transparency, and update/support history.

#### Serviceability
Replaceable pads/cables/batteries/components, repair access, and long-term support where material.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek manufacturer technical specifications, manuals, firmware notes, codec/connectivity documentation, replaceable-component/service information, and relevant Bluetooth/codec certification sources.

#### Measurement / method
Seek published methodology and data for frequency response, distortion, output/compression, directivity, latency, isolation/ANC, battery, or other relevant metrics. When small cross-product differences matter, intentionally seek common-method measurements.

#### Listening / practitioner
Seek reviewers with disclosed listening conditions, comparison references, and enough use context to identify what was actually heard or experienced. Acoustic engineers, experienced reviewers, studio practitioners, and trained listeners can be useful source families.

#### Owner / community
Seek headphone/speaker communities for fit/comfort, pad wear, long-term failures, firmware, battery aging, and preference-sensitive ownership experience.

#### Useful query families
- `<model> frequency response distortion measurement`
- `<model> comfort pad seal long term`
- `<model> firmware battery issue`
- `<model> directivity room placement`
- `<model> vs <model> same rig measurement`

#### Source traps
De-prioritize:
- measurement sources that do not disclose the rig/method when exact comparisons matter;
- short-listen/unboxing content for long-horizon ownership questions;
- sources that give preference claims without enough listener/use context;
- listening-only sources when the research question specifically requires a measurable quantity.

### Merge: Pricing -> Value interpretation
Separate technical/acoustic value from tuning preference and luxury/craft value.

Higher spend may buy:
- lower distortion or greater clean output in demanding use;
- more controlled acoustics/directivity;
- better fit/comfort/build;
- better active features/connectivity;
- replaceable parts/serviceability;
- premium materials/finish.

Do not price-rank one deliberate tuning target over another as universally superior. As gross technical limitations diminish, user fit, room/system interaction, and preference may dominate small measured improvements.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- listening use and environment;
- source/device chain and required connectivity/codecs;
- preferred or tolerated tuning traits;
- fit/comfort constraints;
- portability/isolation/mic needs;
- room/placement constraints for speakers;
- active/wireless software and battery ownership concerns.

### Merge: Product Research -> Market segmentation
Map meaningful design families such as open vs closed, passive vs active, wired vs wireless, nearfield vs room speaker, portable vs stationary, ANC/convenience vs fidelity-oriented, and distinct tuning philosophies when these explain tradeoffs better than price.

### Merge: Product Research -> Finalist extraction
Add where evidence exists:
- Acoustic performance;
- Tuning / preference fit;
- Fit / comfort / placement;
- isolation/ANC/mic/connectivity behavior when relevant;
- active firmware/app/battery history;
- serviceability and replaceable components.

Apply `research_sources.md` and `reviews.md` to these fields.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Tier validity
Require meaningful gains under the active Audio criteria. A different tuning preference, luxury finish, or brand cachet alone does not establish a universally higher functional tier.

### Merge: Pricing Tiers -> Marginal-spend analysis
State whether extra spend primarily buys measurable acoustic capability, fit/build, active features, serviceability, aesthetic/craft value, or a different tuning target.

### Merge: Pricing Tiers -> Diminishing-returns interpretation
Apply the generic pricing authority while making preference and system/room fit explicit when they dominate small incremental technical gains.

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
For audio brands add where material:
- tuning philosophy consistency across lines;
- measurement/execution track record;
- replacement-component availability;
- warranty/repair practicality;
- firmware/app support for active products.

For retailers add where material:
- demo/audition access;
- return policy for subjective fit/tuning;
- open-box constraints for headphones;
- trade-in or service capability when relevant.

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify exact revision, region, wired/wireless variant, connector/configuration variant, and current firmware/app state when they change the answer.

### Merge: Quick Check -> Decision questions
Useful narrow questions include whether the target's tuning/fit suit the user, whether the source/device chain supports it correctly, and whether a current firmware/battery/comfort issue changes the judgment.

## Boundary
Generic criterion, discovery, evidence/comparability, subjective review, seller, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Automotive Accessories

Parent: Base

Inheritance: `Base -> Automotive Accessories`

## Match
Use when:
- exact vehicle fitment, installation, integrated vehicle-system behavior, load/rating limits, or vehicle-specific evidence materially affect the purchase.

## Optimize
- exact fitment and integration;
- appropriate installation burden;
- operationally appropriate ratings/requirements;
- vehicle-platform-specific evidence.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
#### Exact vehicle fitment
Compatibility with the actual year/make/model/trim/body/package and relevant connectors, mounts, clearances, sensors, or factory systems.

#### Installation / integration burden
Required mechanical/electrical work, programming/calibration, special tools, reversibility, and installer competence.

#### Operational criticality
Consequences of failure and any category-relevant ratings, standards, load limits, or official requirements.

#### Vehicle-system interaction
Effects on factory electronics, sensors/cameras, driver-assistance systems, wheel/tire or suspension geometry, loads, and other integrated vehicle behavior.

#### Durability in vehicle conditions
Heat, vibration, weather, contamination, repeated load, and other relevant operating stresses.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek OEM vehicle documentation, manufacturer fitment guides, exact part numbers, installation manuals, load/rating documentation, and category-relevant DOT/SAE/ECE/NHTSA or other official material where applicable.

#### Method / installation
Seek exact-vehicle or platform-specific installation verification. For performance questions, seek relevant measured tests such as load, stopping, output, temperature, or other category-native methods.

#### Practitioner / community
Seek professional mechanics/installers and make/model-specific owner communities for trim/package differences, connector/mounting issues, calibration, and recurring install problems.

#### Useful query families
- `<part number> <year make model trim> fitment`
- `<model> install calibration programming`
- `<model> <vehicle platform> forum fitment`
- `<product> load rating standard certification`
- `<product> sensor camera compatibility`

#### Source traps
De-prioritize:
- generic vehicle-class fitment pages when exact trim/package fit matters;
- installation reports that do not identify the relevant year/trim/interface;
- retailer fitment widgets as the only source path for consequential compatibility;
- performance pages that omit installation/test context.

### Merge: Pricing -> Value interpretation
Evaluate the installed system cost rather than the boxed accessory alone when installation is material.

Account for:
- vehicle-specific hardware/adapters;
- professional installation/programming/calibration;
- fitment-return risk;
- maintenance/replacement parts;
- whether higher spend buys verified engineering, load capability, integration, durability, or support.

A low sticker price is not good value if exact fitment is uncertain or required installation erases the savings.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- exact vehicle identity and factory configuration;
- installation method and user/installer capability;
- operational criticality;
- required standards/load ratings/certifications;
- vehicle-system interactions;
- reversibility and warranty/service implications;
- regional legal/inspection constraints when material.

### Merge: Product Research -> Candidate extraction
Add where material:
- exact fitment basis;
- installation complexity and required tools/programming;
- applicable load/electrical/physical limits;
- vehicle-specific owner evidence availability;
- return consequences if fitment proves wrong.

### Merge: Product Research -> Hard gates and identity
Apply the active Automotive Accessories criteria to verify, where material:
- exact year/make/model/trim/package compatibility;
- required mounting/connector/clearance fit;
- applicable load, electrical, or operating limits;
- required standard/certification;
- compatibility with sensors, cameras, driver-assistance, factory audio/electronics, or other integrated systems.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Tier validity
Require meaningful differences under the active Automotive Accessories criteria such as fitment quality, engineering/testing, load capability, integration, installation simplicity, durability, or support. Cosmetic branding alone does not establish a higher functional tier.

### Merge: Pricing Tiers -> Marginal-spend analysis
Include required installation hardware, professional labor/programming, calibration, and material replacement/restoration costs in the real price step.

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
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

## Quick Check contributions

### Merge: Quick Check -> Target identity
Lock the exact vehicle year/make/model/trim/body/package plus accessory revision/part number whenever fitment depends on them.

### Merge: Quick Check -> Hard gates
Treat a fitment mismatch, required-rating shortfall, or incompatible vehicle-system interaction as an immediate narrow failure.

### Merge: Quick Check -> Deal / where-to-buy
When the item is bulky, vehicle-specific, or installation-dependent, include return shipping/restocking, fitment guarantees, and installer/support consequences in the offer judgment.

## Boundary
Generic criterion, fitment/performance evidence, owner/install interpretation, seller/offer, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Software / Services / Developer Tools

Parent: Base

Inheritance: `Base -> Software / Services / Developer Tools`

## Match
Use when:
- the purchase/selection is software, SaaS, a hosted service, API, developer tool, or commercially evaluated open-source product and lifecycle, licensing, reliability, integration, portability, or usage-based economics materially affect the decision.

## Optimize
- workflow/capability fit;
- operational and project/vendor maturity;
- licensing and effective cost under realistic usage;
- portability and manageable dependency risk.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
#### Capability fit
Required features, workflows, APIs, integrations, platform/runtime support, deployment model, and operational limits.

#### Developer / operator experience
Documentation, API/CLI design, local development, debugging/observability, upgrade ergonomics, automation, and day-to-day workflow friction.

#### Reliability / operational maturity
Incident history, uptime behavior, release/change management, support response, and production-use maturity.

#### Security / governance posture
Security advisories and response, access controls, auditability, data handling/residency, and other user-required governance capabilities.

#### Licensing / commercial fit
License rights/restrictions, seat/usage rules, feature gates, support tiers, minimum commitments, and expected cost scaling.

#### Portability / lock-in
Export completeness, migration path, proprietary formats/APIs, deployment coupling, switching downtime, and realistic exit cost.

#### Project / ecosystem health
Maintainer/vendor continuity, issue and release activity, ecosystem maturity, extension/integration health, and concentration risk where relevant.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek official docs, API/SDK references, changelogs/release notes, status/incident history, security advisories, licensing terms, pricing/usage documentation, SLA/support terms, data-export/migration docs, and public roadmaps when materially relied upon.

#### Technical / empirical
Seek reproducible benchmarks, code-level evaluations, architecture analysis, independent security assessments, and migration/production writeups with enough environment detail to judge applicability.

#### Practitioner / project health
Seek engineers with documented production use, public issue trackers, GitHub/project history, maintainer discussions, Stack Overflow/domain communities, and postmortems for operational and developer-experience signal.

#### Useful query families
- `<tool> changelog breaking changes migration`
- `<tool> production experience incident`
- `<tool> benchmark methodology <workload>`
- `<tool> pricing overage seat usage export`
- `<tool> security advisory cve`
- `<project> github issues release cadence maintainers`

#### Source traps
De-prioritize:
- vendor competitive-comparison pages when independent comparison is available;
- anonymous aggregate software-review pages without useful detail;
- benchmark pages that omit workload/environment details;
- feature-announcement coverage without current docs/changelog verification paths;
- popularity-only pages when project health is the research question.

### Merge: Pricing -> Value interpretation
Use a representative usage scenario rather than sticker price when commercial models differ.

Account for:
- seats/users;
- usage/compute/storage/request meters;
- required feature/support tier;
- deployment/hosting cost;
- minimum commits and overages;
- required add-ons;
- migration/export/egress costs when material;
- engineering/operator time saved or created.

Treat lock-in cost concretely through migration friction, not as a generic penalty. A higher-priced managed product can be better value when it materially reduces engineering/operations burden; a lower-cost or open-source option can be better when the user can absorb that work and values control.

Do not compare free/community, team, usage-metered, and enterprise plans as if posted monthly prices represented equivalent capability or scale.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- deployment model and operating environment;
- required integrations/APIs/platforms;
- team size and expected usage shape;
- compliance/data-residency/security requirements;
- licensing constraints;
- migration/export requirements;
- support/SLA posture;
- expected growth and cost-scaling path.

### Merge: Product Research -> Market segmentation
Map meaningful families such as hosted vs self-hosted, open-source core vs proprietary, integrated suite vs composable specialist, usage-priced vs seat-priced, managed convenience vs infrastructure control, and enterprise-governed vs developer-led adoption when those distinctions explain tradeoffs.

### Merge: Product Research -> Hard gates and identity
Apply the active Software / Services / Developer Tools criteria to verify, where material:
- supported platform/runtime/deployment model;
- required API/integration capability;
- license/usage terms compatible with intended use;
- required data export/residency/compliance posture;
- active support status for the exact product/version/plan;
- unacceptable mandatory cloud or proprietary dependency when explicitly constrained.

### Merge: Product Research -> Finalist extraction
Add where material:
- Developer / operator experience;
- Reliability / operational maturity;
- Security / governance posture;
- Licensing / commercial fit;
- Portability / lock-in;
- Project / ecosystem health;
- effective cost under the user's plausible usage scenario.

Apply `research_sources.md` to these fields.

## Pricing Tiers contributions

### Override: Pricing Tiers -> Tier construction -> linear-ladder assumption
Replace a single unit-price ladder with a normalized **usage-and-entitlement cost surface** when software pricing cannot be meaningfully compared by one sticker price.

Use the representative-usage normalization defined in this Category's Pricing contribution, then construct meaningful value regions from comparable effective cost and capability for those scenarios.

Preserve the generic requirements to normalize current price posture, validate coherent regions, and explain what additional spend buys. Do not force incomparable commercial models into one raw monthly-price ladder.

### Merge: Pricing Tiers -> Market segmentation
Represent parallel commercial models when they are real market structures: open-source/self-hosted, freemium/team, usage-metered, enterprise-contract, managed-service, or other materially different paths.

### Merge: Pricing Tiers -> Marginal-spend analysis
Identify whether extra spend buys scale, governance, support/SLA, security/compliance controls, collaboration, managed operations, reduced engineering labor, or mainly commercial packaging.

### Merge: Pricing Tiers -> Buying context
Surface commercial terms from this Category's Pricing contribution that create material non-linear cost, entitlement, commitment, or exit consequences for the user's scenario.

## Vendor Research contributions

### Merge: Vendor Research -> Ecosystem segmentation
When relevant distinguish commercial SaaS vendors, open-core companies, foundation/community-led projects, hyperscaler-managed variants, independent support vendors, and resellers/integrators. Keep project health and vendor health separate.

### Merge: Vendor Research -> Vendor normalization
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

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify exact product/service, edition/plan, version, deployment model, license, region, and pricing basis when any change the answer.

### Merge: Quick Check -> Hard gates
Treat incompatible licensing, missing required integration/platform support, unacceptable export/deployment constraints, or unsupported versions as narrow hard failures when explicitly required.

### Merge: Quick Check -> Decision questions
Useful narrow questions include whether a claimed feature exists in the relevant plan/version, whether the pricing basis matches the user's usage, whether a current reliability/security issue changes the decision, and whether exit/export is realistically possible.

## Boundary
Generic criterion, discovery, evidence/version/comparability, community interpretation, seller, and pricing semantics remain in their owning shared authorities.

---

# CATEGORY: Watches

Parent: Base

Inheritance: `Base -> Watches`

## Match
Use when:
- the target is a watch and movement/serviceability, finishing/craft, provenance, acquisition channel, collector value, or long-term ownership materially affect the purchase.

Do not generalize this Category to unrelated luxury or collector goods.

## Optimize
- explicit separation of functional, craft, and collector value;
- movement/mechanism and serviceability where applicable;
- finishing/provenance evidence;
- ownership fit rather than prestige alone.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
#### Functional / tool performance
Timekeeping, robustness, wearability, water/use constraints, and practical ownership performance.

#### Movement / mechanism quality
Actual movement/caliber/source, execution/modification, serviceability, parts access, and maintenance implications where applicable.

#### Finishing / craft
Case, dial, hands, bracelet/strap, clasp, tactile execution, alignment, movement finishing, design authorship, and handwork where relevant.

#### Provenance / authenticity
Reference identity, production/revision history, condition/service history for pre-owned watches, and confidence in authenticity/origin.

#### Service ecosystem
Service access, parts policy, expected service burden, manufacturer/independent support, and long-horizon practicality.

#### Collector / identity fit
Historical relevance, maker/brand significance, scarcity, enthusiast reception, design identity, and emotional/collector appeal when the user values them.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek exact reference/caliber specifications, manufacturer service/warranty documentation, official product history where relevant, and COSC or equivalent certification sources for claims that depend on them.

#### Specialist / technical
Seek dedicated horology publications, watchmakers, movement teardown/service sources, and reviewers who document finishing, movement architecture, accuracy, wearability, and direct comparisons.

#### Owner / collector
Seek long-term ownership communities for service experience, bracelet/clasp wear, QC, real-world accuracy, comfort, and sustained collector reception. Include discussion spanning different ownership horizons when collector reception matters.

#### Channel / provenance
For pre-owned/vintage research, seek established dealers, auction catalog documentation, authentication/service specialists, and provenance/condition records appropriate to the watch.

#### Useful query families
- `<reference> caliber movement service`
- `<reference> accuracy long term owner`
- `<reference> case bracelet finishing review`
- `<reference> service cost parts availability`
- `<reference> authenticity condition guide`

#### Source traps
De-prioritize:
- generalist luxury listicles;
- retailer editorial as the only brand-evaluation source;
- sources using prestige or "in-house" language without movement detail;
- short social-hype content without ownership or technical context;
- used/vintage price sources that omit condition/provenance.

### Merge: Pricing -> Value interpretation
Maintain separate value lenses where useful:
- **functional/tool value** - practical performance, robustness, serviceability, wearability;
- **craft/finishing value** - design, materials, finishing, handwork, movement execution;
- **collector/identity value** - provenance, history, scarcity, maker/brand significance, enthusiast appeal.

Do not require a craft- or collector-driven premium to produce proportional functional improvement. Conversely, do not treat prestige language or scarcity alone as proof of quality.

Include expected service burden and acquisition-channel/warranty consequences when material to ownership value. For pre-owned/vintage watches, condition and service history can be as important to value as the nominal reference.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When material, add:
- functional/tool use vs dress/design/collector intent;
- size/wearability and bracelet/strap fit;
- movement/service preferences;
- accuracy/water-resistance requirements;
- new/used/vintage posture;
- provenance/authentication tolerance;
- importance of finishing, brand history, rarity, or collector appeal.

### Merge: Product Research -> Market segmentation
Map meaningful families by watch philosophy rather than prestige alone: practical/tool, design-led, enthusiast mechanical, high-finish/luxury, independent/artisan, vintage/collector, and other real structures discovered in the market.

### Merge: Product Research -> Finalist extraction
Add where evidence exists:
- Functional / tool performance;
- Movement / mechanism quality;
- Finishing / craft;
- Provenance / authenticity;
- Service ecosystem;
- Collector / identity fit;
- relevant acquisition-channel implications.

Apply `research_sources.md`, `reviews.md`, and `seller_instructions.md` to these fields.

## Pricing Tiers contributions

### Override: Pricing Tiers -> Tier construction -> linear-ladder assumption
Replace a single ascending functional-value ladder when the watch market clearly contains parallel value tracks.

Construct parallel price/value regions using this Category's value lenses: functional/tool value, craft/finishing value, and collector/identity value. A watch may participate in more than one track.

Preserve the generic requirements for normalized price posture, coherent regions, and concrete marginal-spend explanations. Do not require craft- or collector-driven premiums to demonstrate proportional functional improvement.

### Merge: Pricing Tiers -> Tier validity
Validate expensive regions using the relevant active Watches value lens rather than prestige language alone.

### Merge: Pricing Tiers -> Marginal-spend analysis
State which active Watches value lens explains each material part of the step-up and what the buyer actually receives for the additional spend.

### Merge: Pricing Tiers -> Diminishing-returns interpretation
Apply the generic pricing authority while identifying functional-return flattening separately from continued craft/collector escalation.

## Vendor Research contributions

### Merge: Vendor Research -> Ecosystem segmentation
When relevant distinguish manufacturers/maisons, independent makers, authorized dealers, independent dealers, pre-owned specialists, auction houses, and authentication/service specialists. Keep their roles distinct.

### Merge: Vendor Research -> Vendor normalization
For brands/makers add where material:
- movement sourcing/control and serviceability;
- finishing/QC consistency;
- service network and parts policy;
- distribution model and continuity.

For dealers/pre-owned specialists add where material:
- authorization status;
- authentication/provenance process;
- condition grading accuracy;
- service-history disclosure;
- warranty/return terms;
- dispute resolution for authenticity or condition.

## Quick Check contributions

### Merge: Quick Check -> Target identity
Verify exact reference, production/revision period, movement/caliber, size/material/bracelet configuration, condition, box/papers/service history when material, and seller/channel type.

### Merge: Quick Check -> Deal / where-to-buy
For independent-dealer, pre-owned, vintage, or auction offers, add authentication/provenance, condition, service history, manufacturer-vs-seller warranty, fees, and return recourse before judging the apparent discount.

### Merge: Quick Check -> Decision questions
Useful narrow questions include whether the reference/movement is correctly identified, whether condition/service history explains the price, and which active Watches value lens actually drives the premium.

## Boundary
Generic classification semantics belong to `product_hierarchy.md`; criterion, discovery, evidence, community, seller/channel, and pricing semantics remain in their owning shared authorities.
