# Shopware Pre-Migration Preparation Checklist

Shopware preparation is strongest when the business defines the future store before migration is judged by transferred records. This platform can support clearer storefront structure, native variant and property logic, sales-channel-specific exposure, SEO URL control, and stronger discovery behavior, but those strengths do not remove ambiguity on their own. They increase the importance of deciding how products should behave, how customers should find them, how channels should expose them, how routes should work, how extensions and custom fields should be governed, and what kind of commerce environment the business is actually trying to preserve after launch.

A strong preparation checklist is therefore not a generic cleanup exercise. It is a way to make the future store explicit early enough to reduce false confidence later. For Shopware, the most useful preparation work usually sits in ten areas: product model clarity, variants versus properties, sales-channel and visibility logic, discovery structure, route continuity, extension/custom-field classification, customer-group and continuity expectations, source-side clarity where the source is a Custom Cart, representative review design, and behavior-based launch-readiness definition.

### 1. Define the product model before mapping begins

The first preparation task is to decide how customers should make product decisions after migration. In Shopware, that usually means separating selectable variant behavior from descriptive product understanding and from filtering logic. This matters because the product page has to preserve a clear buyable outcome, not simply display migrated product records.

Before execution, the business should define:

* which product differences must remain selectable through variant behavior
* which differences belong as descriptive product understanding rather than storefront choice
* which product characteristics should support filtering or comparison rather than direct selection
* which products carry the highest risk of product-model confusion
* which product scenarios should anchor the first representative review

This is one of the highest-value places to use a Demo Migration. A representative sample built around the most structurally difficult products usually reveals translation weakness faster than broad catalog transfer alone.

### 2. Separate variants from properties before the storefront inherits confusion

Shopware rewards a clearer distinction between defined selectable product state and supporting property-based understanding than many source stores maintain. Preparation should preserve that distinction deliberately rather than letting the source structure blur it inside the target.

Before execution, the business should define:

* which customer choices belong in variants because they determine the buyable state
* which product characteristics belong in properties because they support understanding, filtering, or comparison
* which product pages are most likely to become unclear if those roles remain blurred
* which product families depend most on strong choice clarity and comparison quality
* which high-value product journeys should be tested first

This is one of the clearest places where Shopware rewards disciplined translation. If the business does not decide what belongs in variant behavior and what belongs in supporting property logic before execution, the storefront can become harder to shop even when the underlying records appear complete.

### 3. Define sales-channel meaning before product exposure becomes unreliable

Shopware treats sales channels as a structural storefront concept, which makes channel planning one of the most important preparation areas in the hub. Preparation should therefore define which customer-facing contexts the future store actually needs and what those contexts should change in the storefront.

Before execution, the business should define:

* which sales channels matter commercially
* which products should be visible in which storefront contexts
* which channel distinctions are still strategically justified
* which channel-sensitive scenarios are most likely to create confusion if left vague
* which storefront conditions must remain clear after migration

This prevents the store from inheriting blurred channel logic where products migrate successfully but the storefront exposure becomes harder to trust.

### 4. Define visibility behavior before product presence is mistaken for storefront correctness

In Shopware, product presence is not always the same as product visibility in the intended customer-facing sense. If storefront exposure is meant to differ by sales channel or context, then preparation should treat visibility as part of the future-state storefront model rather than as a background administrative detail.

Before execution, the business should define:

* which products or categories should be visible in each relevant storefront context
* which visibility differences are commercially essential
* which exposure rules are still justified after migration
* which products are most sensitive to visibility error
* which visibility-sensitive scenarios should be tested first

This is one of the strongest Shopware-specific preparation areas because the storefront can look populated while still failing commercially if the wrong products are exposed in the wrong contexts.

### 5. Prepare discovery structure as storefront behavior, not only catalog administration

Shopware preparation should treat categories, properties, filters, and search behavior as part of the customer journey. Many migrations preserve product and category records while still weakening discovery because the business prepared the catalog only as structure rather than as how customers actually find the right products.

Before execution, the business should define:

* which category paths matter most to customer discovery
* which properties materially support filtering or comparison
* which product-family relationships should remain clear after launch
* which discovery structures should be preserved, simplified, or rebuilt
* which search and filtering paths should be tested first in a representative review

This is especially important where search is not the whole storefront logic and where browse structure still shapes conversion materially.

### 6. Define route continuity priorities before native SEO capability creates false confidence

Shopware has native SEO URL behavior, but continuity still depends on knowing which paths matter most after launch. Preparation should identify the storefront routes that carry the most commercial value before route decisions are treated as settled. This usually includes more than product paths alone. Category routes, landing pages, and sales-channel-sensitive entry paths may all matter.

Before execution, the business should define:

* which legacy product, category, and content URLs matter most
* which routes shape trust or search visibility most strongly
* which paths should be preserved as closely as possible
* which routes can change safely without weakening continuity materially
* which continuity-sensitive paths should be tested first in a representative review

The most useful early continuity list is usually selective rather than exhaustive. High-value routes reveal more continuity risk than raw URL volume alone.

### 7. Classify extension-, custom-field-, and surrounding storefront behavior before deciding what should survive

Shopware stores can depend on more than native products, properties, and channels. Extensions, custom fields, advanced search logic, storefront components, merchandising tools, and surrounding customization may all carry real business meaning. Preparation should therefore identify what the store truly depends on rather than treating all surrounding behavior as equally important.

Before execution, the business should define:

* which extension-driven outcomes are commercially non-negotiable
* which custom fields or surrounding storefront behaviors affect buying behavior, discovery, trust, or operations
* which behaviors still matter materially to the customer journey
* which extension or custom-field layers can be replaced safely
* which inherited surrounding logic should not be carried forward automatically

This is one of the most important Shopware preparation tasks because stronger storefront structure becomes risky when the business preserves surrounding complexity without first deciding whether that behavior is still worth preserving.

### 8. Define customer-group and account expectations before customer conditions become vague

Shopware customer-group structures can materially affect storefront conditions such as price and related customer-facing behavior. Preparation should therefore define where customer experience depends on more than order history and profile data alone.

Before execution, the business should define:

* which customer-group differences matter commercially after launch
* whether storefront conditions should differ meaningfully by customer group
* which customer scenarios are most likely to create confusion if left vague
* what the intended account experience should look like after migration
* which customer-related behaviors must remain clear after launch

This prevents the store from inheriting blurred customer meaning where records migrate but the practical storefront experience becomes harder to trust.

### 9. If the source is a Custom Cart, prepare the source-side structure before treating the target as safe

This is one of the most important preparation areas for the Shopware hub because Custom Cart can strengthen or weaken the safer path significantly depending on how well the source structure is understood. When the source is a Custom Cart, the migration is no longer a normal standard-cart translation. It becomes a source-side interpretation problem as much as a target-side mapping problem.

Before execution, the business should define:

* which source access methods are available, such as API, file, spreadsheet, semi-structured data, or direct storefront extraction
* what the real source entity structure looks like
* where important storefront meaning sits in custom fields, files, or non-standard logic
* which source-side product, visibility, discovery, content, and route behaviors must still hold true after launch
* which parts of the source model already suggest the need for Custom Migration Service

This is one of the clearest places where technician-led source analysis becomes part of safe preparation rather than a later escalation.

### 10. Choose a representative review sample before full execution

A representative review sample should be designed before detailed execution begins. The goal is not broad coverage. The goal is early truth. Shopware preparation is strongest when the first sample includes the combinations most likely to expose weakness in variant behavior, property logic, channel exposure, discovery quality, route continuity, and source-to-target translation.

A high-signal Shopware sample usually includes:

* variant-heavy and high-value products
* products where variants and properties both matter materially
* category, filter, and route paths with the most commercial value
* sales-channel scenarios where visibility meaning matters
* extension- or custom-field-driven storefront behaviors that materially affect the customer journey
* customer-group scenarios where storefront conditions matter materially
* any source-side complexity that becomes more pronounced when the source is a Custom Cart

This is usually the clearest point at which the business can decide whether the target model is ready for broader migration or still needs structural clarification.

### 11. Define launch-readiness in storefront and operating terms, not only in data terms

Preparation is not complete when the business knows which records should migrate. It is complete when the business can explain what must still work after launch. For Shopware, that usually means defining how customers reach the right products, make the right choices, use the right filtering and discovery paths, encounter the right storefront exposure, and continue to interact with a store the business can still explain and govern safely.

Before execution, the business should define:

* which storefront behaviors must remain unchanged
* which changes are acceptable if the future store becomes cleaner and more governable
* which scenarios represent pass or fail most clearly
* who reviews the result and approves readiness
* which unresolved questions must be answered before launch planning advances

This is the point where preparation becomes a realistic validation strategy rather than a hopeful execution plan.

### Conclusion

Shopware preparation is strongest when it makes the future store explicit before the migration is judged by transferred records. Product structure, variants, properties, channel visibility, discovery logic, route continuity, extension-driven meaning, customer-group conditions, source-side Custom Cart pressure, and representative review design all need deliberate definition early enough to guide execution and validation with confidence.

The most useful preparation work usually identifies where customer-facing behavior and governability are most likely to weaken first. That is what turns a preparation checklist into something more valuable than pre-migration housekeeping. It becomes a way to decide whether the future store is being shaped deliberately enough to deserve trust before the migration scales.

A practical next step is to build a Demo Migration around those high-pressure areas rather than around the easiest records to move. Variant-heavy products, filtering and route-sensitive paths, sales-channel-sensitive storefront exposure, discovery-critical journeys, and the extension or custom-field logic that carries the most commercial or operational weight usually reveal more about target readiness than broad low-risk samples do.

When those results still leave uncertainty, the most useful question is not whether more preparation items can be added to a list. It is whether the business has defined the future store clearly enough to support safe execution. That is where Live Chat becomes especially helpful. It can clarify whether the remaining uncertainty is mainly about ordinary readiness and validation, whether the execution burden points toward Managed Migration Service, or whether the source-to-target translation is non-standard enough to justify Custom Migration Service from the outset, especially when the source is a Custom Cart.

### FAQs

#### What should be prepared first in a Shopware migration?

Usually the highest-risk storefront behavior. That often means product structure, variants versus properties, sales-channel visibility, discovery logic, route continuity, customer-group conditions, and any source-side complexity that could distort the target.

#### Why is Shopware preparation more than a data-cleanup task?

Because the main preparation challenge is not only moving records. It is defining how the future storefront should work, how customers should experience it, and how the business should govern it after launch.

#### Should Shopware preparation focus on every extension equally?

Usually no. Preparation is most useful when it starts by classifying which extension-driven, custom-field-driven, and surrounding storefront behaviors are commercially essential and which can change safely.

#### When does preparation usually point toward a more guided migration path?

Usually when product logic is still unclear, sales-channel exposure remains vague, discovery behavior is unresolved, continuity assumptions are still untested, surrounding extension dependence is unclassified, or the source is a Custom Cart with non-standard structure.
