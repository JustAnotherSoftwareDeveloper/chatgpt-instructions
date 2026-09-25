# Type Registry

## Purpose
Define every supported Shopping Type and the complete delta owned by that Type.

A Type entry is the sole live definition of that Type. Adding or changing a Type should require editing this file only unless the generic hierarchy contract itself changes.

Apply registry entries only through the inheritance, Merge, and Override semantics in `product_hierarchy.md`.

---

# TYPE: Chef's Knife

Parent: Kitchen Knives

Inheritance: `Base -> Home & Kitchen -> Kitchen Knives -> Chef's Knife`

## Match
Use when:
- the target is a general-purpose chef's knife;
- the target is a gyuto-style knife serving the same primary general-purpose role;
- a named model is confidently known to be this product type even if the user does not explicitly say "chef's knife".

A Chef's Knife here includes general-purpose Western chef knives and gyuto-style knives serving the same primary-kitchen-knife role.

## Optimize
- primary-knife versatility;
- fit to the user's cutting motion, board, hand, food mix, and maintenance tolerance;
- geometry, profile, length, weight, and balance as an integrated tool.

This Type is the reference implementation for hierarchy Merge/Override behavior. It should contain only Chef's-Knife-specific deltas beyond inherited Kitchen Knife behavior.

## Shared domain behavior

### Functional/design family lens
Chef's Knives can use functional/design families as an analytical lens when those families are supported by the market, for example:
- robust Western/German-style rocker/generalist;
- thinner Western/French-profile generalist;
- Japanese laser-style gyuto;
- Japanese workhorse-style gyuto;
- hybrid/mass-market Japanese-style generalist;
- artisan/collector-oriented chef knife/gyuto.

These are examples, not fixed taxonomy or mandatory slots. Products may sit between families. The lens distinguishes primary-knife design philosophy from production/value track or price tier.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
In addition to inherited Kitchen Knife criteria, emphasize:

#### Primary-knife versatility
Coverage of the user's normal general-purpose prep without unnecessary specialist compromise.

#### Length and board fit
Blade length relative to board, workspace, storage, prep volume, and user control.

#### Profile and cutting motion
Belly/flatness/contact length and fit for rocking, push cutting, chopping, draw slicing, or mixed technique.

#### Heel clearance and handle interaction
Knuckle clearance, heel height, grip, choil/handle geometry, and board contact.

#### Tip utility
Precision/detail usefulness vs fragility/robustness.

#### Food release
Grind/geometry behavior with common foods; treat as food- and preference-dependent.

#### Weight and balance
Mass and balance relative to control, momentum, fatigue, and feedback.

#### Role fit
If another knife type materially better matches the actual primary use, do not force Chef's Knife merely because the Type was initially considered.

### Merge: Source Playbooks -> Discovery guidance
Favor sources that discuss the knife as a primary general-purpose tool and that expose actual tradeoffs across representative foods/tasks.

#### Desired comparison evidence
When available prefer sources that:
- compare multiple relevant knives under the same tester/method;
- show representative foods rather than one stunt task;
- discuss profile/board contact, wedging, food release, tip work, fatigue, and grip;
- report actual dimensions/weight/balance rather than relying on nominal marketing;
- revisit the knife after sharpening or longer use when edge/maintenance claims matter.

#### Seek evidence about
- actual blade length/height;
- profile and cutting-motion fit;
- heel/knuckle clearance;
- tip geometry;
- balance/weight/grip interaction;
- grind, wedging, and food release across representative foods;
- comfort/control through extended prep;
- edge/sharpening behavior;
- QC consistency;
- adjacent formats such as gyuto, santoku, nakiri, or Chinese cleaver when role fit is genuinely in question.

#### Useful query families
- `<model> profile rocking push cut heel height`
- `<model> 210mm dimensions balance weight`
- `<model> food release wedging onions potatoes carrots`
- `<model> chef knife gyuto long term review`
- `<model> sharpening thinning edge stability`
- `<model> QC warp grind handle`

Avoid sources that treat all 8-inch/210 mm knives as interchangeable or infer primary-knife fit from steel/prestige alone.

### Merge: Pricing -> Value interpretation
For a primary general-purpose knife, value should emphasize:
- geometry and cutting behavior across the user's common foods;
- profile/length/height fit;
- comfort and balance during repeated use;
- edge/maintenance behavior that matches the user;
- quality-control consistency and provenance;
- versatility sufficient to serve the intended primary-knife role.

Do not pay a premium for specialization that undermines the user's primary use unless the user explicitly wants that specialization.

When researching live price tiers, let `pricing_tiers.md` discover current market clusters and meaningful breakpoints. Do not hard-code timeless dollar bands here.

## Product Research contributions

### Merge: Product Research -> Market segmentation
Use the Chef's-Knife functional/design family lens as a primary explanatory dimension in the generic market map where it is supported.

For represented families, capture the Chef-specific differences that matter to the decision: cutting style/use, geometry/profile/weight tendencies, structural compromise, maintenance/robustness posture, and relevance to the user's primary-knife needs.

Do not let the discovery pool contain many superficially different knives from one family while omitting a credible alternative design philosophy.

### Merge: Product Research -> Scope and decision model
For an underspecified ordinary Chef's Knife recommendation, use these working buyer assumptions unless contradicted:
- home cook;
- one primary general-purpose knife;
- approximately **8 in / 200-210 mm**;
- mixed ordinary cutting motion;
- wood or plastic cutting board;
- no bones, frozen food, prying, or dishwasher use;
- stainless or low-reactivity favored;
- moderate-to-low maintenance preference;
- functional value matters more than collector/artisan prestige.

These are workflow defaults, not claims about the user. Replace them immediately when the request or locked context says otherwise.

Normally prioritize these active criteria unless the user or inherited Kitchen Knife triggers change their role:
1. geometry/cutting behavior and primary-knife versatility;
2. profile/length/ergonomic fit;
3. maintenance/edge behavior appropriate to the user;
4. value at normal/current price.

Treat exact product identity/provenance as a verification requirement when material rather than an automatic primary differentiator.

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
- heavy rocking preference -> make Profile and cutting motion a primary differentiator;
- push-cut/chop dominant use -> make useful flat contact and predictable board contact a primary differentiator;
- large hands, pinch grip, or known clearance problems -> elevate Heel clearance and handle interaction;
- explicit laser/very-low-resistance preference -> elevate cutting resistance/thinness while keeping robustness tradeoffs visible;
- active sharpening/edge experimentation interest -> sharpening response, steel/heat treatment, and geometry may become primary differentiators;
- explicit artisan/collector intent -> activate Design / aesthetic / identity fit as a meaningful preference dimension.

### Merge: Product Research -> Hard gates and identity
Add only Chef's-Knife-specific fit checks beyond the inherited Kitchen Knife gates:
- primary-knife role mismatch;
- severe cutting-motion/profile mismatch;
- hard length/board/workspace mismatch;
- adjacent-product fallback when another knife form is clearly the better primary tool.

Consider adjacent forms only when the use case strongly supports them, for example:
- santoku for compact all-purpose preference;
- nakiri for vegetable-heavy flat/tall profile use where pointed tip is unnecessary;
- Chinese cleaver for users wanting a tall rectangular general-purpose blade and its technique;
- petty/utility for unusually small/light prep and active dislike of full-size knives;
- heavier cleaver/butcher tool for bone/abuse tasks outside normal Chef's Knife use.

Do not switch product forms casually. Resolve only to a named Type that actually exists in `type.md`. If the better adjacent format has no live Type entry yet, fall back to the `Kitchen Knives` Category context and evaluate the product form there; do not invent a Type or inherited rules that do not exist.

### Merge: Product Research -> Finalist extraction
For each serious Chef's Knife finalist in Standard/Deep research, add the following where evidence exists.

#### Role / identity
- market/design family;
- intended primary role.

#### Physical / geometry
- actual edge/blade length;
- heel height;
- weight;
- balance character;
- profile/belly/flat section;
- handle style/dimensions when material;
- spine/distal taper observations when trustworthy;
- behind-the-edge / grind / convexity-hollow-flat observations when trustworthy.

Do not pretend unavailable geometry measurements exist. Qualitative competent observations are acceptable when clearly labeled.

#### Cutting behavior
Evaluate across representative tasks where evidence exists:
- low-resistance cutting;
- dense-food wedging;
- food release/stiction;
- board contact/profile behavior;
- tip/detail work;
- slicing/portioning;
- fatigue/control over repeated prep.

#### Fit
- rocking suitability;
- push/chop suitability;
- mixed-technique versatility;
- heel/hand clearance;
- balance/weight preference fit;
- primary-knife role breadth.

### Merge: Product Research -> Comparison and evidence use
For recommendation-changing Chef's Knife differences, emphasize the Chef-specific path from profile/length/geometry/weight to board interaction, cutting behavior, fatigue/control, and primary-knife fit.

Examples:
- thinner behind-the-edge geometry may reduce wedging in dense produce while lowering abuse margin;
- more belly may support rocking but reduce flat board contact for push chopping;
- increased heel height may improve clearance but change agility/feel depending on geometry and balance.

### Merge: Product Research -> Synthesis / decision boundary
For the top two finalists explicitly know:
- which Chef-specific primary criterion most separates them;
- why the leading option fits this user's cutting motion, primary-task mix, ergonomics, or value model better;
- what user preference or assumption would flip the recommendation.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Market segmentation
Add the Chef's-Knife functional/design family lens to the inherited Kitchen Knife production/execution/value-family view.

The effective market map should be able to distinguish **what kind of primary knife a product is** from **what production/value track it occupies**.

### Override: Pricing Tiers -> Tier construction -> linear-ladder assumption
Chef's Knife pricing may contain overlapping or parallel value tracks.

If the researched market supports it, represent parallel tracks/regions rather than forcing every knife onto one ascending quality ladder. Examples include:
- a function/performance-oriented production path;
- a higher-touch enthusiast or specialist-production path;
- an artisan/craft/collector path.

These tracks are not mandatory categories. Use them only when current evidence shows that one linear tier model would hide materially different reasons for spending more.

A more expensive knife on a craft track is not automatically a higher functional tier than a cheaper performance-oriented knife.

### Merge: Pricing Tiers -> Tier validity
Beyond the inherited Kitchen Knife validity checks, ask whether extra spend changes Chef-specific primary-tool behavior such as:
- cutting resistance across common foods;
- profile/board-contact fit;
- heel clearance, balance, or fatigue;
- versatility as the intended primary knife.

A higher-cost region that adds only craft/collector value can still be legitimate, but should not be described as a superior functional Chef's-Knife tier.

### Merge: Pricing Tiers -> Marginal-spend analysis
For Chef's Knives, explicitly distinguish whether extra spend materially improves the user's general-purpose cutting/handling experience or mainly buys refinement/craft/collector dimensions.

### Merge: Pricing Tiers -> Diminishing-returns interpretation
Add one Chef-specific question: where does additional spend stop materially improving this user's **primary-knife** cutting, fit, maintenance, and ownership criteria?

Treat that point as the Chef's-Knife functional sweet spot while preserving higher craft/refinement value when relevant under the generic pricing authority and inherited Kitchen Knife guidance.

## Vendor Research contributions

### Merge: Vendor Research -> Ecosystem segmentation
Within the Kitchen Knife vendor ecosystem, distinguish where useful between vendors focused on:
- Western/generalist chef knives;
- Japanese/gyuto-focused production;
- artisan/low-volume primary knives;
- specialist retail/import channels with meaningful chef/gyuto curation.

Do not require every ecosystem to contain all of these.

### Merge: Vendor Research -> Vendor normalization
For Chef's-Knife brands/makers add only Type-specific dimensions:
- depth and coherence of chef/gyuto lineup;
- available lengths/profiles/handle systems;
- consistency of primary-knife geometry/execution across the line;
- whether reputation is model-specific or representative of the chef/gyuto lineup.

For specialist retailers add where material:
- depth of relevant chef/gyuto inventory rather than raw SKU count;
- ability to distinguish profile/geometry/cutting-motion use cases;
- handling of low-volume or batch-variable chef/gyuto knives.

## Quick Check contributions

### Merge: Quick Check -> Hard gates
Add only Chef's-Knife-specific fit failures beyond the inherited Kitchen Knife gates:
- primary-knife role mismatch;
- severe profile/cutting-motion mismatch;
- hard length/board/workspace mismatch.

### Merge: Quick Check -> Decision questions
When relevant, add one Chef-specific question: does this exact knife's length/profile/geometry fit the user's cutting motion, board, and intended primary-knife role?

## Boundary
This entry owns Chef's-Knife-specific shared design-family context and hierarchy deltas only. Generic criterion semantics belong to `criteria.md`; generic value interpretation to `pricing.md`; generic discovery semantics to `source_playbooks.md`; shared knife rules to the `Kitchen Knives` Category entry; Merge/Override semantics and child-delta rules to `product_hierarchy.md`.
