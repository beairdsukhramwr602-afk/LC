# Gambio Selecting the Right Migration Approach

Gambio migration approach should be chosen by looking at the future operating model, not only by counting products, customers, and orders. A store moving to Gambio Cloud may need a different level of preparation than a store moving to a self-hosted Gambio installation. A simple catalog with clear categories and predictable order history can often be handled differently from a store with customer-group pricing, B2B rules, complex product options, downloadable products, SEO-sensitive URLs, custom integrations, or source-specific checkout behavior.

The practical question is not whether Gambio can receive store data. The better question is how much interpretation is needed before that data becomes reliable inside Gambio’s catalog, storefront, customer, order, configuration, and integration layers.

### Why Approach Choice Depends on Gambio-Specific Burden <a href="#why-approach-choice-depends-on-gambio-specific-burden" id="why-approach-choice-depends-on-gambio-specific-burden"></a>

Gambio combines a shop system, storefront management, catalog administration, SEO configuration, payment and shipping setup, customer-group features, and hosting-model choices. This makes migration approach selection more sensitive than a simple record-transfer decision.

A clean migration path can become heavier when the source store contains hidden business logic. Product options may affect price, inventory, images, or shopper selection. Customer groups may determine visible prices, B2B rules, or commercial segmentation. Orders may include custom statuses, external identifiers, marketplace references, or special tax and shipping meaning. Storefront continuity may depend on SEO URLs, redirects, content pages, navigation, theme behavior, or integrations that are not ordinary product data.

The right approach should therefore match three areas of burden:

#### Data burden <a href="#data-burden" id="data-burden"></a>

Data burden comes from the source store’s product, customer, order, and content structure. A store with simple products, clear categories, stable customers, and ordinary order history creates less burden than a store with deep variants, customer-group rules, downloadable products, legacy option structures, fragmented categories, custom fields, or heavily modified source data.

#### Configuration burden <a href="#configuration-burden" id="configuration-burden"></a>

Configuration burden comes from Gambio settings that must be planned separately from migrated records. Payment methods, shipping rules, tax behavior, currencies, languages, stock settings, customer groups, invoice and delivery-note expectations, SEO configuration, and legal-display settings may need setup or review after migration.

#### Implementation burden <a href="#implementation-burden" id="implementation-burden"></a>

Implementation burden comes from the target environment. Gambio Cloud reduces some hosting and update responsibility, while self-hosted Gambio gives more control but increases responsibility for hosting, installation, maintenance, extensions, compatibility, and custom development. Storefront design, StyleEdit work, theme customization, integrations, and bespoke logic can also increase implementation burden.

### When Standard Service Is Usually Enough <a href="#when-standard-service-is-usually-enough" id="when-standard-service-is-usually-enough"></a>

Standard Service is usually the better fit when the source store is structurally clear and the merchant can self-perform the migration process on the Next-Cart website using standard service capability, 24/7 expert support, and any purchased Add-ons.

For Gambio, Standard Service is usually more appropriate when the migration has these characteristics:

| Standard Service signal                                                   | Why it matters for Gambio                                                            |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Products, categories, customers, and orders are organized and predictable | Core records can be migrated and checked without heavy interpretation.               |
| Product options or variants are simple                                    | Shopper selection, pricing, and order line meaning are easier to validate.           |
| Customer groups are not central to pricing or access logic                | The migration is less dependent on segmented commercial rules.                       |
| Tax, shipping, payment, language, and currency requirements are standard  | Most post-migration work is configuration review rather than custom interpretation.  |
| Storefront design is being rebuilt or adjusted separately                 | The migration can focus on the data foundation instead of design replication.        |
| The merchant can review Demo Migration results carefully                  | Standard Service depends on the customer’s ability to validate records and settings. |

Standard Service should not be treated as a low-effort shortcut. It works best when the merchant understands the source structure, can identify representative samples, and can distinguish migration issues from Gambio configuration or storefront implementation work.

#### Good Standard Service candidates <a href="#good-standard-service-candidates" id="good-standard-service-candidates"></a>

A small or mid-sized retail store with clean products, organized categories, ordinary customer records, and standard order history may be a good Standard Service candidate. The same is true for stores that do not rely heavily on customer-group pricing, custom checkout fields, source-specific option logic, unusual tax rules, or external operational systems.

Standard Service can also fit merchants who are moving into Gambio Cloud and expect a relatively standard Gambio setup, as long as the source data is clean and the merchant is prepared to configure the target shop settings after migration.

### When Managed Service Is Safer <a href="#when-managed-service-is-safer" id="when-managed-service-is-safer"></a>

Managed Service is safer when the migration still fits standard service capability, but the merchant wants Next-Cart-led execution. This can be useful when the source data is not unusually custom, but the merchant does not want to manage the migration process alone.

For Gambio, Managed Service often makes sense when the store has enough moving parts to benefit from guided execution but not enough bespoke logic to require Custom Service.

#### Managed Service is often useful when review coordination matters <a href="#managed-service-is-often-useful-when-review-coordination-matters" id="managed-service-is-often-useful-when-review-coordination-matters"></a>

A merchant may have clean data but still need help coordinating product samples, customer records, order examples, category checks, tax review, shipping review, payment context, and Demo Migration interpretation. Managed Service can be safer in that case because Next-Cart performs the migration using standard service capability and any purchased Add-ons.

#### Managed Service does not replace implementation planning <a href="#managed-service-does-not-replace-implementation-planning" id="managed-service-does-not-replace-implementation-planning"></a>

Managed Service should not be confused with custom development, theme implementation, or business-rule redesign. If the target Gambio store requires custom storefront work, bespoke data transformation, integration development, or non-standard migration logic, that requirement belongs in Custom Service review, not ordinary Managed Service expectations.

### When Custom Service Is Needed <a href="#when-custom-service-is-needed" id="when-custom-service-is-needed"></a>

Custom Service should be reviewed when the migration requires customization, modification, Tailored Add-ons, Custom Add-ons, Custom Platform handling, unsupported source structures, custom migration logic adjustment, or broader bespoke interpretation.

For Gambio, Custom Service becomes important when the source store’s operating meaning cannot be preserved through standard migration assumptions.

#### Custom Platform or heavily modified source data <a href="#custom-platform-or-heavily-modified-source-data" id="custom-platform-or-heavily-modified-source-data"></a>

If the Source Platform is a Custom Platform, the valid service-path implication is Custom Service review. The same applies when the source system has custom database structures, app-owned fields, third-party identifiers, ERP-owned catalog data, marketplace-specific references, or bespoke order relationships that are not part of standard supported behavior.

#### Complex customer-group and B2B logic <a href="#complex-customer-group-and-b2b-logic" id="complex-customer-group-and-b2b-logic"></a>

Gambio can support customer-group and B2B-oriented scenarios, but the migration must clarify what the source store actually means by groups, price lists, visibility rules, discounts, tax treatment, account approval, or buyer segmentation. If the source store uses custom B2B workflows or special pricing logic that does not map cleanly, Custom Service should be reviewed.

#### Product options, variants, and custom product data <a href="#product-options-variants-and-custom-product-data" id="product-options-variants-and-custom-product-data"></a>

Custom Service may be needed when source product options carry unusual pricing, inventory, image, SKU, bundle, or compatibility behavior. Product custom fields, external attributes, source-specific option logic, bundled products, configurable products, or non-standard downloadable product rules may require deeper mapping or custom migration logic adjustment.

#### Storefront, SEO, and integration dependencies <a href="#storefront-seo-and-integration-dependencies" id="storefront-seo-and-integration-dependencies"></a>

A store with high-value SEO URLs, custom route rules, marketplace connections, ERP integration, payment workflow dependencies, shipping automation, custom modules, or self-hosted code modifications may require Custom Service if the expected result depends on more than supported record migration.

### Where Add-ons May Help <a href="#where-add-ons-may-help" id="where-add-ons-may-help"></a>

Add-ons may help when the migration requires focused filtering, mapping, or configuration support that fits available Add-on capability. They should not be used as a substitute for broader Custom Service.

| Need                                                   | Possible Add-on relevance                                                                  | Boundary to watch                                                                              |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Excluding outdated or unnecessary records              | Data Filter Add-on may help when the filtering need is clear and supported.                | Complex conditional logic or business-rule redesign may need Custom Service.                   |
| Mapping source fields into supported target structures | Advanced Data Mapping may help when source-to-target field relationships are clear.        | Unsupported custom fields, app-owned data, or external identifiers may require Custom Service. |
| Adjusting supported configuration behavior             | Advanced Data Configure may help where target configuration needs fit standard capability. | Bespoke transformation or custom migration logic adjustment belongs in Custom Service.         |
| Handling customer-group or catalog segmentation        | Add-ons may help if the mapping is defined and supported.                                  | Custom B2B pricing, visibility, or approval workflows may exceed Add-on boundaries.            |

The key boundary is scope. Add-ons are focused service features. Custom Service is the broader path for modified, bespoke, unsupported, or Custom Platform requirements.

### What Demo Migration Should Clarify <a href="#what-demo-migration-should-clarify" id="what-demo-migration-should-clarify"></a>

Demo Migration should clarify whether the selected approach is strong enough before Full Migration. For Gambio, the Demo Migration should test examples that represent the real store, not only the simplest records.

#### Catalog proof <a href="#catalog-proof" id="catalog-proof"></a>

The Demo Migration should include simple products, option-heavy products, products with multiple images, products in multiple categories, downloadable products if used, products with special pricing, stock-sensitive products, and records with important attributes or filters. The goal is to prove that shoppers can understand the product and that the merchant can manage it after migration.

#### Customer and order proof <a href="#customer-and-order-proof" id="customer-and-order-proof"></a>

The sample should include normal customers, customer-group examples, guest or registered account examples where relevant, recent orders, older orders, orders with discounts, tax, shipping, payment context, variant selections, and unusual statuses. Order history should remain useful for service, accounting reference, and operational review.

#### Storefront and SEO proof <a href="#storefront-and-seo-proof" id="storefront-and-seo-proof"></a>

The Demo Migration should help the merchant check whether categories, product pages, content pages, metadata, URLs, redirects, navigation, and storefront expectations are aligned with the Gambio implementation plan. If SEO continuity is important, high-value pages and paths should be reviewed early.

#### Configuration proof <a href="#configuration-proof" id="configuration-proof"></a>

The Demo Migration should identify which issues are data issues, which are Gambio configuration issues, which require Add-on review, and which require Custom Service review. This distinction prevents the merchant from expecting migrated records to solve settings that must be configured inside Gambio.

### Signs the Chosen Approach Is Too Light <a href="#signs-the-chosen-approach-is-too-light" id="signs-the-chosen-approach-is-too-light"></a>

The chosen approach is probably too light if the Demo Migration reveals repeated ambiguity rather than isolated cleanup issues.

Common warning signs include:

* Product options appear but do not preserve shopper-facing meaning.
* Category, filter, or product-discovery behavior is difficult to interpret.
* Customer groups do not reflect expected pricing or segmentation meaning.
* Orders appear but discounts, tax, shipping, payment context, or statuses are unclear.
* Downloadable products, stock behavior, or special pricing cannot be validated confidently.
* Important storefront URLs, metadata, content pages, or redirects are not planned.
* Source custom fields or external identifiers are central to operations.
* The source store depends on marketplace, ERP, payment, shipping, or self-hosted custom code behavior.
* The merchant cannot separate migration issues from Gambio configuration or implementation work.

When these signals appear, the safer action is to review the migration path, Add-on needs, Managed Service suitability, or Custom Service scope before moving into Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Gambio migration approach depends on how much interpretation the source store requires and how much responsibility the target operating model creates. Standard Service can fit clean, supported, well-understood data. Managed Service can be safer when the merchant wants Next-Cart-led execution within standard service capability. Custom Service should be reviewed when the source includes Custom Platform data, unsupported structures, custom fields, bespoke B2B rules, extension-owned data, integration dependencies, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

Use Demo Migration results to test whether the selected approach is strong enough for the real store. If product options, customer groups, order history, SEO paths, downloadable products, tax, shipping, payment, integrations, or self-hosted customization introduce uncertainty, review the migration path through Live Chat before Full Migration so service responsibilities and Add-on boundaries are clear.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for migrating to Gambio?**

Standard Service may be enough when the source data is clean, the selected migration path supports the needed data types, and the merchant can self-perform the migration process on the Next-Cart website with 24/7 expert support. It is less suitable when the source store depends on custom fields, bespoke product logic, complex B2B rules, or unsupported extension data.

**When should Managed Service be considered for Gambio migration?**

Managed Service should be considered when the migration fits standard service capability but the merchant wants Next-Cart to perform the migration. It is useful when the store has enough catalog, customer, order, or configuration complexity to benefit from Next-Cart-led execution without requiring bespoke migration logic.

**When does Gambio migration require Custom Service?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported custom fields, third-party identifiers, complex product option logic, customer-group pricing rules, self-hosted custom code, integration-owned data, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

**Can Add-ons help with Gambio migration?**

Yes. Add-ons may help with focused filtering, mapping, or configuration needs when those needs fit available Add-on capability. They should not be treated as a replacement for Custom Service when the migration requires broader customization, unsupported data handling, or bespoke transformation.

**What should Demo Migration prove before Full Migration to Gambio?**

Demo Migration should prove that products, options, categories, customer groups, orders, discounts, tax, shipping, payment context, downloadable products, stock behavior, SEO-sensitive pages, and storefront expectations can be interpreted correctly in the target Gambio environment.
