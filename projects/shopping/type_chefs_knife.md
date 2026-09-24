# Type Authority: Chef's Knife

## Purpose
Own behavior specific to Chef's Knives when the `Chef's Knife` Type is active.

Use Chef's Knife sections of `criteria.md`, `source_playbooks.md`, and `pricing.md`, plus inherited Kitchen Knife guidance.

A Chef's Knife here includes general-purpose Western chef knives and gyuto-style knives serving the same primary-kitchen-knife role.

This Type is the reference implementation for hierarchy workflow Merge/Override behavior.

# Shared domain behavior

## Default consumer model
For an underspecified ordinary Chef's Knife shopping request, assume unless contradicted:
- home cook;
- one primary general-purpose knife;
- approximately **8 in / 200-210 mm**;
- mixed ordinary cutting motion;
- wood or plastic cutting board;
- no bones, frozen food, prying, or dishwasher use;
- stainless or low-reactivity favored;
- moderate-to-low maintenance preference;
- functional value matters more than collector/artisan prestige.

These are working defaults, not claims about the user. Replace them immediately when the request or locked context says otherwise.

## Primary-knife role
Evaluate first as the user's main general-purpose knife for common vegetables/herbs, onions/garlic, boneless proteins, slicing/portioning, and normal detail work.

Do not force the Type when the real primary tasks are better served by another format.

## Length
Treat length as fit, not prestige.

Use ~200-210 mm / 8 in as the default starting point when unspecified, then adjust for:
- board size/workspace/storage;
- hand/control preference;
- prep volume;
- slicing capacity;
- explicit compact/long-blade preference.

Shorter may improve control in small kitchens; longer may improve capacity/slicing. Do not assume longer is more capable.

## Profile and cutting-motion triggers
### Heavy rocking
If the user explicitly rocks heavily or repeatedly references curved-profile preference:
- make profile/belly a **primary differentiator**;
- avoid very flat profiles likely to fight the technique.

### Push-cut / chop dominant
If the user primarily push-cuts/chops:
- make flat useful contact region and predictable board contact a **primary differentiator**;
- do not favor extra belly merely because it is common in Western chef knives.

### Mixed / unspecified
Use a moderate versatile profile as default and keep profile as a primary differentiator only when finalist differences are large enough to matter.

## Heel clearance and hand fit
Elevate heel height/handle interaction to a primary differentiator when:
- user has large hands or explicitly needs clearance;
- user pinch-grips and models differ materially at heel/choil;
- user reports knuckle-contact problems;
- compact/short-height knives are under consideration.

Otherwise treat as a normal ergonomic check.

## Tip utility
Evaluate precision/detail usefulness vs fragility. Fine tips can improve onion/detail/trimming work but may require more care. Robust tips trade some precision for durability.

Elevate tip behavior only when the user's food/tasks or finalist geometry makes it materially different.

## Grind / robustness triggers
### Precision/thin-cutting preference
If user explicitly wants laser-like cutting, very low resistance, or mostly careful vegetable/boneless prep:
- make thinness/cutting resistance a primary differentiator;
- keep abuse tolerance as an explicit caveat.

### Rough-use / abuse signals
If user expects bones, frozen food, prying, twisting, hard impact, very hard boards, or generally rough handling:
- make robustness/toughness a hard gate or primary differentiator;
- do not recommend fragile thin/hard geometry as the ordinary fit;
- consider whether Chef's Knife is even the correct Type for those tasks.

### Unspecified ordinary home use
Balance cutting resistance and robustness; do not optimize for an extreme laser or heavy workhorse by default.

## Reactivity / maintenance triggers
### User explicitly wants carbon/reactive steel
Remove the stainless/low-reactivity default. Evaluate care burden as an accepted tradeoff rather than an automatic negative.

### User wants very low maintenance / no sharpening interest
- elevate corrosion resistance, edge-service practicality, and easy professional sharpening/service access;
- strongly penalize unnecessary maintenance complexity;
- if user demands dishwasher-safe use, explain that ordinary quality Chef's Knives are a poor match for that requirement rather than pretending a normal recommendation still fits.

### User sharpens and values edge experimentation
Sharpening response, steel/heat treatment, and geometry can become primary differentiators.

## Weight and balance
Evaluate relative to control, fatigue, cutting style, and user preference.

Heavier can add momentum/stability; lighter can add agility/lower fatigue. Neither is universally better.

Elevate only when user expresses a preference or finalists differ enough to change handling materially.

## Handle and grip
Consider pinch-grip comfort, handle dimensions, Western vs wa consequences, balance shift, wet grip, and hotspots over expected prep duration.

Do not infer ergonomic superiority from premium handle materials.

## Artisan / collector trigger
If the user explicitly values artisan work, maker identity, craft, rare materials, aesthetics, collector standing, or low-volume production:
- activate Design / aesthetic / identity as a primary preference dimension;
- treat provenance and maker identity as material;
- do not dismiss craft/finish premiums as wasted money merely because raw cutting performance is similar.

If those signals are absent, functional value should dominate over collector/artisan premium under the default model.

## Chef's knife vs adjacent product forms
Consider redirecting to or adding an adjacent kitchen-knife format only when the use case strongly supports it:
- santoku for compact all-purpose preference;
- nakiri for vegetable-heavy flat/tall profile use where pointed tip is unnecessary;
- Chinese cleaver for users wanting a tall rectangular general-purpose blade and its technique;
- petty/utility for unusually small/light prep and active dislike of full-size knives;
- heavier cleaver/butcher tool for bone/abuse tasks outside normal Chef's Knife use.

Do not switch product forms casually.

Resolve only to a named Type that actually exists in `product_hierarchy.md`. If the better adjacent format has no live Type authority yet, fall back to the `Kitchen Knives` Category context and evaluate the product form there; do not invent a Type, specialized file, or inherited rules that do not exist.

## Fit questions: when to ask
Do not ask the full questionnaire.

Ask only when a missing variable would change the viable set or primary differentiators. Highest-value variables are:
- preferred length/board size;
- rocking vs push/chop vs mixed;
- stainless/low-maintenance vs reactive-steel willingness;
- sharpening/service posture;
- tolerance for thin/hard/chip-sensitive geometry;
- weight/balance preference;
- budget and whether craft/aesthetics are part of value.

If none blocks useful research, use the default consumer model and proceed.

# Product Research contributions

## Override: Product Research -> Market segmentation -> primary segmentation model
For Chef's Knives, use functional/design families as the primary Product Research market map rather than generic price tiers.

Test whether the current market contains meaningful families such as:
- robust Western/German-style rocker/generalist;
- thinner Western/French-profile generalist;
- Japanese laser-style gyuto;
- Japanese workhorse-style gyuto;
- hybrid/mass-market Japanese-style generalist;
- artisan/collector-oriented chef knife/gyuto.

These are analytical examples, not fixed taxonomy and not mandatory slots. Discover the families actually present. A product may sit between families.

For each represented family understand:
- intended cutting style/use;
- geometry/profile/weight tendencies;
- primary benefit;
- structural compromise;
- maintenance/robustness tendency;
- price/value posture;
- relevance to the user's needs.

Do not let the discovery pool contain many superficially different knives from one family while omitting a credible alternative design philosophy.

## Override: Product Research -> Scope and decision model -> default primary differentiators
For an ordinary underspecified Chef's Knife purchase, start with these primary differentiators unless the request or inherited trigger changes them:
1. geometry/cutting behavior and primary-knife versatility;
2. profile/length/ergonomic fit;
3. maintenance/edge behavior appropriate to the user;
4. value at normal/current price.

Treat exact product identity/provenance as a verification requirement when material rather than an automatic primary differentiator.

Promote QC/consistency to a primary differentiator only when the activation triggers in `category_kitchen_knives.md` apply. Promote provenance/channel concerns according to that Category authority and `seller_instructions.md` when the purchase channel is actually in scope.

Secondary dimensions become primary only through the triggers in this Type or inherited Category rules.

## Merge: Product Research -> Hard gates and identity
When Chef's Knife is active add:
- primary-knife role fit;
- cutting-motion/profile incompatibility when severe enough to be disqualifying;
- length/board/workspace mismatch when hard;
- abuse expectations that exceed ordinary chef-knife use;
- maintenance/reactivity constraints;
- adjacent-product fallback when another knife form is clearly the better role fit.

## Merge: Product Research -> Finalist extraction
For each serious Chef's Knife finalist in Standard/Deep research, add the following where evidence exists.

### Role / identity
- exact model/line/length/variant;
- maker/manufacturer and provenance;
- market/design family;
- intended primary role.

### Physical / geometry
- actual edge/blade length;
- heel height;
- weight;
- balance character;
- profile/belly/flat section;
- handle style/dimensions when material;
- spine/distal taper observations when trustworthy;
- behind-the-edge / grind / convexity-hollow-flat observations when trustworthy.

Do not pretend unavailable geometry measurements exist. Qualitative competent observations are acceptable when clearly labeled.

### Cutting behavior
Evaluate across representative tasks where evidence exists:
- low-resistance cutting;
- dense-food wedging;
- food release/stiction;
- board contact/profile behavior;
- tip/detail work;
- slicing/portioning;
- fatigue/control over repeated prep.

### Edge / steel / sharpening
- steel and hardness only when identity is trustworthy;
- edge stability/chipping/rolling signal;
- retention evidence with test/use context;
- sharpening response/service burden;
- thinning/long-term geometry maintenance when material.

### Ownership
- corrosion/reactivity;
- rough-use tolerance;
- handle/material care;
- QC pattern;
- warranty/service/sharpening ecosystem;
- known batch/revision variation.

### Fit
- rocking suitability;
- push/chop suitability;
- mixed-technique versatility;
- heel/hand clearance;
- balance/weight preference fit;
- maintenance fit.

### Value
- normal street-price posture;
- current reputable range when in scope;
- what the premium over nearby finalists actually buys;
- whether current sale temporarily changes the ranking.

## Merge: Product Research -> Comparison and evidence use
For recommendation-changing Chef's Knife differences, prefer:

`geometry/profile/heat treatment/weight/etc. -> cutting/edge/handling behavior -> tradeoff -> fit for user's foods/technique/maintenance`

Examples:
- thinner behind-the-edge geometry may reduce wedging in dense produce while lowering abuse margin;
- more belly may support rocking but reduce flat board contact for push chopping;
- harder/wear-resistant edge systems may extend retention while raising sharpening/chipping sensitivity depending on geometry/heat treatment.

Do not claim a mechanism from steel name, HRC, choil photo, or marketing alone. Separate observation from inference.

## Merge: Product Research -> Synthesis / decision boundary
For the top two finalists explicitly know:
- which primary criterion most separates them;
- whether the evidence is directly or directionally comparable;
- why the #1 fits this user's technique/maintenance/value model better;
- what user preference or assumption would flip the recommendation.

Use technique, maintenance, food mix, robustness preference, and value as the main decision-boundary vocabulary when applicable.

# Pricing Tiers contributions

## Override: Pricing Tiers -> Market segmentation -> primary segmentation model
For Chef's Knives, combine two views before tier construction:

1. **Functional/design family** - the effective Product Research families above.
2. **Production/value track** inherited from Kitchen Knives - production scale, execution/QC, artisan labor, craft/collector value.

Do not force a single price-based market ladder when similarly priced knives pursue fundamentally different functional or craft value propositions.

## Override: Pricing Tiers -> Tier construction -> linear-ladder assumption
Chef's Knife pricing may contain overlapping or parallel value tracks.

If the researched market supports it, represent parallel tracks/regions rather than forcing every knife onto one ascending quality ladder. Examples include:
- a function/performance-oriented production path;
- a higher-touch enthusiast or specialist-production path;
- an artisan/craft/collector path.

These tracks are not mandatory categories. Use them only when current evidence shows that one linear tier model would hide materially different reasons for spending more.

A more expensive knife on a craft track is not automatically a higher functional tier than a cheaper performance-oriented knife.

## Merge: Pricing Tiers -> Tier validity
For Chef's Knives, a meaningful higher-cost region must identify what the premium actually buys, such as:
- lower cutting resistance or more deliberate geometry;
- more consistent QC/execution;
- profile/taper/finish refinement;
- ergonomics/handle work;
- edge/heat-treatment execution in context;
- service/provenance;
- maker labor/craft;
- aesthetics/materials;
- rarity/collector value.

Do not validate a higher region merely because of prestige steel, Damascus, country of origin, or maker reputation.

## Merge: Pricing Tiers -> Marginal-spend analysis
For each relevant step up or competing track, label the premium primarily as one or more of:
- functional performance;
- robustness/ownership;
- consistency/QC;
- refinement/ergonomics;
- service/provenance;
- craft/maker labor;
- aesthetics/materials;
- rarity/collector value.

This label should explain the value proposition, not score it.

## Override: Pricing Tiers -> Diminishing-returns interpretation -> domain manifestation
Use the shared definition from `pricing.md`, but explicitly distinguish:
- the point where **functional Chef's Knife returns** flatten for the user's primary criteria;
- any continuing **craft/refinement/collector value** that remains real but preference-dependent.

The output may therefore identify a functional sweet spot while separately recognizing higher craft-value regions.

# Vendor Research contributions

## Merge: Vendor Research -> Ecosystem segmentation
For Chef's Knives, where material distinguish vendors by the part of the primary-knife market they actually serve:
- Western/generalist production brands;
- Japanese/gyuto-focused production brands or makers;
- artisan/low-volume makers;
- importers/distributors bridging maker and US buyer;
- specialist knife retailers with meaningful curation/service.

Do not require every vendor ecosystem to contain all of these.

## Merge: Vendor Research -> Vendor normalization
For Chef's-Knife brands/makers add where material:
- depth and coherence of chef/gyuto lineup;
- available lengths/profiles/handle systems;
- consistency of geometry/execution across the line;
- whether reputation is model-specific or genuinely representative of the lineup;
- artisan availability/continuity when low-volume;
- practical US distribution/service.

For specialist retailers add where material:
- depth of relevant chef/gyuto inventory rather than raw SKU count;
- ability to distinguish profile/geometry/use cases;
- inspection/QC practices;
- sharpening/thinning/setup services;
- import/provenance clarity;
- handling of low-volume or batch-variable knives.

# Quick Check contributions

## Merge: Quick Check -> Target identity
For a named Chef's Knife verify only the fields needed for the narrow question, commonly:
- exact length;
- steel/core/cladding revision when variant-sensitive;
- handle style/version;
- region/import variant;
- model generation or maker relationship;
- condition/listing identity.

## Merge: Quick Check -> Hard gates
When relevant add:
- length/board/workspace mismatch;
- cutting-motion/profile mismatch;
- maintenance/reactivity mismatch;
- thin/hard geometry vs known rough use;
- primary-knife role mismatch.

## Merge: Quick Check -> Decision questions
Useful narrow Chef's Knife questions include:
- Is this exact variant the knife the user thinks it is?
- Does its profile/geometry fit the user's cutting motion and foods?
- Does maintenance/edge behavior fit the user?
- Is a QC/provenance/seller issue material enough to change the judgment?

Use only the subset needed; do not turn Quick Check into the full finalist record.

## Merge: Quick Check -> Deal / where-to-buy
When a concrete offer is in scope, pay particular attention to exact length/handle/steel revision, authorized/import status when relevant, low-volume provenance, and specialist-retailer services that may justify a price difference.

# Research emphasis
Prioritize evidence revealing actual dimensions/profile, grind/cutting behavior, QC, steel/heat-treatment/edge behavior in context, balance/ergonomics, maintenance expectations, current value, and representative-food behavior.

De-emphasize steel marketing, decorative finish, brand prestige, or factory sharpness unless explicitly relevant.

## Boundary
This file owns Chef's-Knife-specific shared behavior and explicit workflow Merges/Overrides. Shared metallurgy/sharpening/construction/provenance rules belong to `category_kitchen_knives.md`; reusable criteria/source/pricing definitions remain in their shared authorities; Merge/Override semantics belong to `product_hierarchy.md`.
