# Class Registry

## Purpose
Define every supported Shopping Class and the complete delta owned by that Class.

A Class entry is the sole live definition of that Class. Adding or changing a Class should require editing this file only unless the generic hierarchy contract itself changes.

Apply registry entries only through the inheritance, Merge, and Override semantics in `product_hierarchy.md`.

---

# CLASS: Home & Kitchen

Parent: Base

Inheritance: `Base -> Home & Kitchen`

## Match
Use when:
- the purchase is primarily household or kitchen equipment, tools, furnishings, or durable goods and Home/Kitchen-specific ownership concerns materially affect the decision.

## Optimize
- practical household fit;
- durable everyday ownership;
- ergonomics, maintenance, storage, and material suitability where relevant.

## Shared domain behavior

### Household-use framing
Evaluate products for the user's actual home environment rather than defaulting to commercial/professional assumptions.

Professional-grade features may be valuable, but can also add:
- size/weight;
- maintenance;
- noise/heat;
- storage burden;
- cost;
- complexity that does not benefit the household use case.

Conversely, frequent/high-volume home use can justify professional or enthusiast equipment when the benefits are real.

### Durability and maintenance
Consider the interaction between:
- expected use frequency/intensity;
- materials/construction;
- cleaning requirements;
- replaceable parts or consumables;
- realistic user maintenance;
- storage conditions;
- warranty/serviceability where meaningful.

Do not call something durable solely because it is heavy, expensive, metal, or marketed as professional.

### Ergonomics and household fit
When relevant, account for:
- user size/strength/grip;
- counter, drawer, cabinet, and storage constraints;
- setup/cleanup frequency;
- shared-household use;
- whether the item stays visible or is stored between uses.

A technically superior product can be the worse household choice if it is unpleasant enough to maintain, store, clean, or use that the user avoids it.

### Materials and food-contact claims
When material composition, coatings, food contact, or safety claims affect the decision:
- prefer authoritative/primary evidence for factual safety/compliance claims under `research_sources.md`;
- distinguish actual exposure/use conditions from generic fear or marketing;
- do not infer safety from "natural", "non-toxic", "professional", or similar marketing language alone.

### Aesthetics and visible objects
For products that live on counters, walls, open shelving, or dining areas, treat aesthetics as a legitimate criterion when the user cares about it.

Do not assume appearance is superficial merely because functional testing exists.

## Shared-authority contributions

### Merge: Criteria -> Evaluation dimensions
In addition to applicable General criteria, consider:
- household-use durability/frequency;
- home ergonomics rather than default professional assumptions;
- cleaning/maintenance burden;
- storage/footprint;
- food-contact/material concerns when material;
- replaceable parts/consumables;
- visible-object aesthetics when the user cares.

### Merge: Source Playbooks -> Discovery guidance
#### Primary / documentary
Seek material/specification, care/cleaning, warranty, parts/consumables, and safety/compliance documentation where relevant.

#### Method/test
Seek credible household-use testing, durability testing, cleaning/maintenance comparison, and actual-use ergonomics.

#### Practitioner / expert
Depending on product, seek cooks, instructors, repair professionals, tradespeople, appliance technicians, or other domain practitioners.

#### Owner / community
Seek long-term cleaning, maintenance, storage, durability, and household-use experience.

#### Source traps
De-prioritize:
- professional/commercial sources that do not address home-use constraints;
- lifestyle content making material/safety claims without underlying authoritative references;
- content that treats weight, price, metal construction, or "professional" branding as the main durability evidence.

### Merge: Pricing -> Value interpretation
In addition to General Value, account for:
- usable ownership life;
- maintenance burden and replaceable parts/consumables;
- durability under realistic household use;
- storage/space costs when material;
- whether professional-grade features create real home value or merely cost/complexity;
- whether aesthetics/craft are an explicit part of the user's value definition.

Avoid assuming "buy it for life" is automatically economical; long life matters only if the product remains useful, maintainable, and suitable.

## Product Research contributions

### Merge: Product Research -> Scope and decision model
When household fit is material, add:
- storage/footprint constraints;
- cleanup/setup frequency;
- shared-household users;
- realistic duty cycle;
- maintenance willingness;
- whether commercial/pro features create value or burden in the home.

### Merge: Product Research -> Finalist extraction
Where relevant add:
- cleaning friction;
- storage burden;
- consumables/replaceable parts;
- household-use durability;
- serviceability/warranty practicality;
- whether the product is likely to remain convenient enough to use regularly.

### Merge: Product Research -> Synthesis / decision boundary
When two products are close technically, explicitly account for household ownership friction. Do not let small performance advantages dominate when setup, cleanup, storage, noise, maintenance, or shared-use friction would materially change real use.

## Pricing Tiers contributions

### Merge: Pricing Tiers -> Tier validity
A higher Home & Kitchen tier is more meaningful when extra spend buys household-relevant gains such as:
- longer usable ownership life;
- lower cleaning/maintenance burden;
- better serviceability/parts support;
- genuinely better ergonomics or capacity;
- lower recurring consumable burden;
- materially better fit/finish or visible-object aesthetics when valued.

Do not treat "professional" positioning, added mass, or extra complexity as an automatic higher-value tier.

### Merge: Pricing Tiers -> Marginal-spend analysis
Include household ownership consequences in the step-up analysis:

`additional spend -> household capability/convenience/durability difference -> recurring ownership effect -> buyer who benefits`

## Vendor Research contributions

### Merge: Vendor Research -> Vendor normalization
Where material add:
- replacement-parts/consumables availability;
- domestic warranty/service practicality;
- repair/service network quality;
- continuity of product lines/consumables;
- retailer handling of large/fragile/difficult returns;
- category competence around installation, setup, or maintenance.

## Quick Check contributions

### Merge: Quick Check -> Hard gates
When material, include:
- physical/storage fit;
- cleaning/maintenance tolerance;
- required consumables/parts;
- household electrical/plumbing/installation compatibility;
- shared-user usability.

### Merge: Quick Check -> Decision questions
For household products, one narrow question may be whether a technically capable product creates enough setup, cleanup, storage, or maintenance friction to make it a poor real-world fit.

## Boundary
This Class contains only behavior genuinely reusable across multiple Home & Kitchen categories. More-specific behavior belongs to the active Category or Type registry entry; universal Shopping behavior belongs to `base.md`; hierarchy composition semantics belong to `product_hierarchy.md`.
