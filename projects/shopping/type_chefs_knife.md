# Type Authority: Chef's Knife

## Purpose
Own behavior specific to Chef's Knives when the `Chef's Knife` Type is active.

Use Chef's Knife sections of `criteria.md`, `source_playbooks.md`, and `pricing.md`, plus inherited Kitchen Knife guidance.

A Chef's Knife here includes general-purpose Western chef knives and gyuto-style knives serving the same primary-kitchen-knife role.

This Type is the reference implementation for hierarchy workflow Merge/Override behavior. It should contain only Chef's-Knife-specific deltas beyond inherited Kitchen Knife behavior.

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

## Profile and cutting motion
A more curved profile generally supports rocking; a flatter useful edge generally supports push cutting/chopping and more complete board contact.

Mixed-technique users usually benefit from a versatile middle ground unless their food mix or preferences strongly favor one extreme.

## Heel clearance and hand fit
Heel height, choil/handle geometry, grip, hand size, and board interaction can materially affect knuckle clearance and comfort.

Compact or short-height knives deserve closer fit scrutiny for users with large hands or known clearance problems.

## Tip utility
Fine tips can improve onion/detail/trimming work but may require more care. Robust tips trade some precision for durability.

## Grind and robustness
Very thin, low-resistance geometry can improve cutting performance in dense produce and careful boneless prep while reducing abuse margin.

More robust geometry can tolerate rougher use but may increase cutting resistance or wedging.

## Reactivity and maintenance
Reactive steels can offer desirable sharpening/edge characteristics but require care appropriate to the steel and finish. Stainless or low-reactivity constructions reduce corrosion burden but are not automatically better knives.

## Weight and balance
Heavier can add momentum/stability; lighter can add agility/lower fatigue. Neither is universally better.

## Handle and grip
Consider pinch-grip comfort, handle dimensions, Western vs wa consequences, balance shift, wet grip, and hotspots over expected prep duration.

Do not infer ergonomic superiority from premium handle materials.

## Artisan / collector value
Artisan work, maker identity, craft, rare materials, aesthetics, collector standing, or low-volume production can be legitimate value dimensions when the user cares about them.

If those signals are absent, functional primary-knife value should dominate over collector/artisan premium under the default model.

## Chef's knife vs adjacent product forms
Consider redirecting to or adding an adjacent kitchen-knife format only when the use case strongly supports it:
- santoku for compact all-purpose preference;
- nakiri for vegetable-heavy flat/tall profile use where pointed tip is unnecessary;
- Chinese cleaver for users wanting a tall rectangular general-purpose blade and its technique;
- petty/utility for unusually small/light prep and active dislike of full-size knives;
- heavier cleaver/butcher tool for bone/abuse tasks outside normal Chef's Knife use.

Do not switch product forms casually.

Resolve only to a named Type that actually exists in `product_hierarchy.md`. If the better adjacent format has no live Type authority yet, fall back to the `Kitchen Knives` Category context and evaluate the product form there; do not invent a Type, specialized file, or inherited rules that do not exist.

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

Promote QC/consistency only through the inherited Kitchen Knife activation rules. Promote provenance/channel concerns according to inherited Category guidance and `seller_instructions.md` when the purchase channel is actually in scope.

## Merge: Product Research -> Scope and decision model
Use the default consumer model unless the request supplies better information.

Highest-value Chef's-Knife variables are:
- preferred length/board/workspace;
- rocking vs push/chop vs mixed cutting motion;
- primary food/task mix;
- stainless/low-maintenance vs reactive-steel willingness;
- sharpening/service posture;
- tolerance for very thin/hard geometry;
- weight/balance preference;
- whether craft/aesthetics are part of value.

Apply these Chef-specific role changes when triggered:
- heavy rocking preference -> make profile/belly a primary differentiator;
- push-cut/chop dominant use -> make useful flat contact and predictable board contact a primary differentiator;
- large hands, pinch grip, or known clearance problems -> elevate heel/handle interaction;
- explicit laser/very-low-resistance preference -> elevate cutting resistance/thinness while keeping robustness tradeoffs visible;
- active sharpening/edge experimentation interest -> sharpening response, steel/heat treatment, and geometry may become primary differentiators;
- explicit artisan/collector intent -> activate design/aesthetic/identity as a meaningful preference dimension.

Inherited Kitchen Knife maintenance, QC, and abuse triggers remain active without restatement.

## Merge: Product Research -> Hard gates and identity
Add only Chef's-Knife-specific fit checks beyond the inherited Kitchen Knife gates:
- primary-knife role mismatch;
- severe cutting-motion/profile mismatch;
- hard length/board/workspace mismatch;
- adjacent-product fallback when another knife form is clearly the better primary tool.

## Merge: Product Research -> Finalist extraction
For each serious Chef's Knife finalist in Standard/Deep research, add the following where evidence exists.

### Role / identity
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

### Fit
- rocking suitability;
- push/chop suitability;
- mixed-technique versatility;
- heel/hand clearance;
- balance/weight preference fit;
- primary-knife role breadth.

Inherited Kitchen Knife finalist fields for edge/sharpening, QC, maintenance, provenance, and ownership remain active without duplication.

## Merge: Product Research -> Comparison and evidence use
For recommendation-changing Chef's Knife differences, emphasize the Chef-specific path from profile/length/geometry/weight to board interaction, cutting behavior, fatigue/control, and primary-knife fit.

Examples:
- thinner behind-the-edge geometry may reduce wedging in dense produce while lowering abuse margin;
- more belly may support rocking but reduce flat board contact for push chopping;
- increased heel height may improve clearance but change agility/feel depending on geometry and balance.

Do not claim a mechanism from steel name, HRC, choil photo, or marketing alone. Separate observation from inference.

## Merge: Product Research -> Synthesis / decision boundary
For the top two finalists explicitly know:
- which Chef-specific primary criterion most separates them;
- why the leading option fits this user's cutting motion, primary-task mix, ergonomics, or value model better;
- what user preference or assumption would flip the recommendation.

Inherited Kitchen Knife tradeoff language remains active.

# Pricing Tiers contributions

## Merge: Pricing Tiers -> Market segmentation
Keep the inherited Kitchen Knife production/execution/value-family model and add the Chef's-Knife functional/design families from Product Research.

The effective market map should therefore be able to distinguish **what kind of primary knife a product is** from **what production/value track it occupies**. Do not replace the inherited Category segmentation model merely to add this second dimension.

## Override: Pricing Tiers -> Tier construction -> linear-ladder assumption
Chef's Knife pricing may contain overlapping or parallel value tracks.

If the researched market supports it, represent parallel tracks/regions rather than forcing every knife onto one ascending quality ladder. Examples include:
- a function/performance-oriented production path;
- a higher-touch enthusiast or specialist-production path;
- an artisan/craft/collector path.

These tracks are not mandatory categories. Use them only when current evidence shows that one linear tier model would hide materially different reasons for spending more.

A more expensive knife on a craft track is not automatically a higher functional tier than a cheaper performance-oriented knife.

## Merge: Pricing Tiers -> Tier validity
Beyond the inherited Kitchen Knife validity checks, ask whether extra spend changes Chef-specific primary-tool behavior such as:
- cutting resistance across common foods;
- profile/board-contact fit;
- heel clearance, balance, or fatigue;
- versatility as the intended primary knife.

A higher-cost region that adds only inherited craft/collector value can still be legitimate, but should not be described as a superior functional Chef's-Knife tier.

## Merge: Pricing Tiers -> Marginal-spend analysis
For Chef's Knives, explicitly distinguish whether extra spend materially improves the user's general-purpose cutting/handling experience or mainly buys the inherited refinement/craft/collector dimensions.

## Merge: Pricing Tiers -> Diminishing-returns interpretation
Keep the inherited Kitchen Knife distinction between functional-return flattening and craft/preference escalation.

Add one Chef-specific question: where does additional spend stop materially improving this user's **primary-knife** cutting, fit, maintenance, and ownership criteria? Treat that point as the Chef's-Knife functional sweet spot, while preserving higher craft/refinement value when relevant.

# Vendor Research contributions

## Merge: Vendor Research -> Ecosystem segmentation
Within the inherited Kitchen Knife vendor ecosystem, distinguish where useful between vendors focused on:
- Western/generalist chef knives;
- Japanese/gyuto-focused production;
- artisan/low-volume primary knives;
- specialist retail/import channels with meaningful chef/gyuto curation.

Do not require every ecosystem to contain all of these.

## Merge: Vendor Research -> Vendor normalization
For Chef's-Knife brands/makers add only Type-specific dimensions:
- depth and coherence of chef/gyuto lineup;
- available lengths/profiles/handle systems;
- consistency of primary-knife geometry/execution across the line;
- whether reputation is model-specific or representative of the chef/gyuto lineup.

For specialist retailers add where material:
- depth of relevant chef/gyuto inventory rather than raw SKU count;
- ability to distinguish profile/geometry/cutting-motion use cases;
- handling of low-volume or batch-variable chef/gyuto knives.

Inherited Kitchen Knife provenance, importer, service, inspection, sharpening, and authorization dimensions remain active without restatement.

# Quick Check contributions

## Merge: Quick Check -> Hard gates
Add only Chef's-Knife-specific fit failures beyond inherited Kitchen Knife gates:
- primary-knife role mismatch;
- severe profile/cutting-motion mismatch;
- hard length/board/workspace mismatch.

## Merge: Quick Check -> Decision questions
When relevant, add one Chef-specific question: does this exact knife's length/profile/geometry fit the user's cutting motion, board, and intended primary-knife role?

Inherited Kitchen Knife identity, QC, maintenance, provenance, and deal checks remain active without restatement.

## Boundary
This file owns Chef's-Knife-specific shared behavior and explicit workflow deltas only. Shared metallurgy/sharpening/construction/provenance rules belong to `category_kitchen_knives.md`; reusable criteria/source/pricing definitions remain in their shared authorities; Merge/Override semantics and child-delta rules belong to `product_hierarchy.md`.
