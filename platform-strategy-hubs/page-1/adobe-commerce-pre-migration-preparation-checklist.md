# Adobe Commerce Pre-Migration Preparation Checklist

Adobe Commerce preparation is strongest when the business defines the future store before migration is judged by transferred records. This platform can support stronger native structures for configurable product behavior, customer context, catalog visibility, route control, and layered storefront scope, but those strengths do not remove ambiguity on their own. They increase the importance of deciding how products should behave, how customers should encounter the catalog, how scope should be organized, how routes should be preserved, how surrounding ecosystem layers should be governed, and what kind of enterprise-weight commerce environment the business is actually trying to preserve after launch.

A strong preparation checklist is therefore not a generic cleanup exercise. It is a way to make the future store explicit early enough to reduce false confidence later. For Adobe Commerce, the most useful preparation work usually sits in ten areas: product model clarity, configurable behavior versus customizable options, customer-context and catalog-visibility logic, scope structure, route continuity, surrounding service and extension classification, customer continuity expectations, source-side clarity where the source is a Custom Cart, representative review design, and behavior-based launch-readiness definition.

### 1. Define the product model before mapping begins

The first preparation task is to decide how customers should make product decisions after migration. In Adobe Commerce, that usually means separating defined configurable product state from descriptive product information and from supporting customization behavior. This matters because the product page has to preserve a clear buyable outcome, not simply display migrated product records.

Before execution, the business should define:

* which product differences must remain selectable through configurable behavior
* which differences belong as descriptive product understanding rather than storefront choice
* which purchase-specific behaviors belong as supporting customization rather than defined product state
* which products carry the highest risk of product-model confusion
* which product scenarios should anchor the first representative review

This is one of the highest-value places to use a Demo Migration. A representative sample built around the most structurally difficult products usually reveals translation weakness faster than broad catalog transfer alone.

### 2. Separate configurable behavior from customizable options before the storefront inherits confusion

Adobe Commerce rewards a clearer distinction between defined product state and supporting purchase customization than many source stores maintain. Preparation should preserve that distinction deliberately rather than letting the source structure blur it inside the target.

Before execution, the business should define:

* which customer choices belong in configurable behavior because they determine the product state
* which customer-entered or purchase-specific inputs belong in customizable options
* which product pages are most likely to become unclear if those roles remain blurred
* which product families depend most on strong product understanding and choice clarity
* which high-value product journeys should be tested first

This is one of the clearest places where Adobe Commerce rewards disciplined translation. If the business does not decide what belongs in configurable behavior and what belongs in customizable options before execution, the storefront can become harder to shop even when the underlying records appear complete.

### 3. Define customer-context meaning before account and catalog logic become unreliable

Adobe Commerce can support stronger native customer-context structures, which makes this one of the most important preparation areas in the hub. Preparation should therefore define what kinds of customer distinction the future store actually needs and what those distinctions should change in the storefront.

Before execution, the business should define:

* which customer-context differences matter commercially
* whether visibility, account behavior, or buying conditions should differ by customer context
* which distinctions are still strategically justified
* which customer scenarios are most likely to create confusion if left vague
* which customer-facing conditions must remain clear after migration

This prevents the store from inheriting blurred customer-context logic where the records migrate but the commercial meaning becomes harder to trust.

### 4. Define catalog visibility and shared-catalog logic before product presence is mistaken for storefront correctness

In Adobe Commerce, product presence is not always the same as product availability in the intended commercial sense. If catalog exposure is meant to differ by customer context, then preparation should treat visibility as part of the future-state storefront model rather than as a background administrative detail.

Before execution, the business should define:

* which customer contexts should see which catalog conditions
* which catalog differences are commercially essential
* which visibility rules are still justified after migration
* which products or categories are most sensitive to visibility error
* which visibility-sensitive scenarios should be tested first

This is one of the strongest Adobe-Commerce-specific preparation areas because the storefront can look populated while still failing commercially if the wrong catalog conditions are shown to the wrong customers.

### 5. Define scope structure before enterprise-weight flexibility becomes governance confusion

Adobe Commerce can support layered scope, but preparation should treat that as a business decision, not only as a platform capability. The important question is not only whether more than one storefront context can exist. It is whether the business has defined clearly how those contexts should differ and what each one should own.

Before execution, the business should define:

* which differences justify separation at the appropriate scope layer
* whether the future environment needs all of the currently imagined scope distinctions
* who owns products, content, continuity, and customer experience at each level
* which scope-sensitive storefront conditions are most likely to create confusion if left vague
* which storefront scenarios should be reviewed first where layered scope matters

Inherited architectural separation should be challenged rather than preserved automatically. A layered scope model should exist because it improves clarity, governance, or customer experience, not because it existed historically without review.

### 6. Define route continuity priorities before rewrite capability creates false confidence

Adobe Commerce has native URL rewrite and redirect capability, but continuity still depends on knowing which paths matter most after launch. Preparation should identify the storefront routes that carry the most commercial value before route decisions are treated as settled. This usually includes more than product paths alone. Category paths, content pages, and scope-sensitive storefront entry routes may all matter.

Before execution, the business should define:

* which legacy product, category, and content URLs matter most
* which routes shape trust or search visibility most strongly
* which paths should be preserved as closely as possible
* which routes can change safely without weakening continuity materially
* which continuity-sensitive paths should be tested first in a representative review

The most useful early continuity list is usually selective rather than exhaustive. High-value routes reveal more continuity risk than raw URL volume alone.

### 7. Classify extension-, service-, and ecosystem-driven behavior before deciding what should survive

Adobe Commerce stores can depend on more than native catalog and account structures. Search services, extensions, integrations, merchandising layers, experience tools, and surrounding commerce services may all carry real business meaning. Preparation should therefore identify what the store truly depends on rather than treating all surrounding behavior as equally important.

Before execution, the business should define:

* which ecosystem-driven outcomes are commercially non-negotiable
* which surrounding service layers affect buying behavior, discovery, trust, or operations
* which behaviors still matter materially to the customer journey
* which extension or service layers can be replaced safely
* which inherited surrounding logic should not be carried forward automatically

This is one of the most important Adobe Commerce preparation tasks because strong native structure becomes risky when the business preserves surrounding complexity without first deciding whether that behavior is still worth preserving.

### 8. Plan customer continuity according to source-to-target reality, not target preference alone

Customer continuity should be prepared as a source-to-target planning question, not as an assumption attached to Adobe Commerce simply because some source conditions can make continuity more realistic than on reset-first targets. In some migrations, continuity may be realistic. In others, first-login planning, password reset flow, and customer communication may still be the safer model.

Before execution, the business should define:

* what level of customer continuity is technically realistic from the source platform
* which customer groups are most sensitive to login disruption
* what the first-login experience should look like if continuity is not feasible
* which account scenarios need the earliest review
* what support and communication planning will be needed after launch

This is especially important where account continuity affects repeat buying, support load, or customer trust materially.

### 9. If the source is a Custom Cart, prepare the source-side structure before treating the target as safe

This is one of the most important preparation areas for the Adobe Commerce hub because Custom Cart can strengthen or weaken the safer path significantly depending on how well the source structure is understood. When the source is a Custom Cart, the migration is no longer a normal standard-cart translation. It becomes a source-side interpretation problem as much as a target-side mapping problem.

Before execution, the business should define:

* which source access methods are available, such as API, file, spreadsheet, semi-structured data, or direct storefront extraction
* what the real source entity structure looks like
* where important storefront meaning sits in custom fields, files, or non-standard logic
* which source-side product, customer-context, visibility, content, and route behaviors must still hold true after launch
* which parts of the source model already suggest the need for Custom Migration Service

This is one of the clearest places where technician-led source analysis becomes part of safe preparation rather than a later escalation.

### 10. Choose a representative review sample before full execution

A representative review sample should be designed before detailed execution begins. The goal is not broad coverage. The goal is early truth. Adobe Commerce preparation is strongest when the first sample includes the combinations most likely to expose weakness in product behavior, customer context, catalog visibility, route continuity, scope, and source-to-target translation.

A high-signal Adobe Commerce sample usually includes:

* configurable and high-value products
* product journeys where configurable and customizable behavior both matter
* customer-context scenarios where visibility or pricing meaning matters
* high-value route paths with strong commercial importance
* scope-sensitive storefront situations where layered context matters
* ecosystem- or extension-driven storefront behaviors that materially affect the customer journey
* any source-side complexity that becomes more pronounced when the source is a Custom Cart

This is usually the clearest point at which the business can decide whether the target model is ready for broader migration or still needs structural clarification.

### 11. Define launch-readiness in storefront and operating terms, not only in data terms

Preparation is not complete when the business knows which records should migrate. It is complete when the business can explain what must still work after launch. For Adobe Commerce, that usually means defining how customers reach the right products, make the right choices, encounter the right account and catalog conditions, move through the right routes, and continue to interact with a storefront the business can still explain and govern safely.

Before execution, the business should define:

* which storefront behaviors must remain unchanged
* which changes are acceptable if the future store becomes cleaner and more governable
* which scenarios represent pass or fail most clearly
* who reviews the result and approves readiness
* which unresolved questions must be answered before launch planning advances

This is the point where preparation becomes a realistic validation strategy rather than a hopeful execution plan.

### Conclusion

Adobe Commerce preparation is strongest when it makes the future store explicit before the migration is judged by transferred records. Product structure, configurable behavior, customizable options, customer context, catalog visibility, scope logic, route continuity, ecosystem-driven meaning, customer continuity, source-side Custom Cart pressure, and representative review design all need deliberate definition early enough to guide execution and validation with confidence.

The most useful preparation work usually identifies where customer-facing behavior and governability are most likely to weaken first. That is what turns a preparation checklist into something more valuable than pre-migration housekeeping. It becomes a way to decide whether the future store is being shaped deliberately enough to deserve trust before the migration scales.

A practical next step is to build a Demo Migration around those high-pressure areas rather than around the easiest records to move. Configurable products, customer-context-sensitive storefront conditions, route-critical browsing paths, scope-specific experiences, and surrounding commerce-service behavior usually reveal more about target readiness than broad low-risk samples do.

When those results still leave uncertainty, the most useful question is not whether more preparation items can be added to a list. It is whether the business has defined the future store clearly enough to support safe execution. That is where Live Chat becomes especially helpful. It can clarify whether the remaining uncertainty is mainly about ordinary readiness and validation, whether the execution burden points toward Managed Migration Service, or whether the source-to-target translation is non-standard enough to justify Custom Migration Service from the outset, especially when the source is a Custom Cart.

### FAQs

#### What should be prepared first in an Adobe Commerce migration?

Usually the highest-risk storefront behavior. That often means product structure, configurable versus customizable behavior, customer-context logic, catalog visibility, route continuity, scope structure, and any source-side complexity that could distort the target.

#### Why is Adobe Commerce preparation more than a data-cleanup task?

Because the main preparation challenge is not only moving records. It is defining how the future storefront should work, how customers should experience it, and how the business should govern it after launch.

#### Should Adobe Commerce preparation focus on every surrounding service or extension equally?

Usually no. Preparation is most useful when it starts by classifying which ecosystem-driven behaviors are commercially essential and which can change safely.

#### When does preparation usually point toward a more guided migration path?

Usually when product logic is still unclear, customer-context rules remain vague, scope structure is unresolved, continuity assumptions are still untested, surrounding service dependence is unclassified, or the source is a Custom Cart with non-standard structure.
