# Selecting the Right Migration Approach for BigCommerce

Selecting the right migration approach for BigCommerce depends on how much structure the Target Platform must preserve, not only how many records need to move. A store with a moderate record count can still require stronger planning when product choices, segmented pricing, storefront scope, redirects, app data, or external identifiers carry business meaning.

BigCommerce is a hosted commerce platform, but many migrations into BigCommerce involve more than a simple transfer of products, customers, orders, and content. Products may need variants, variant options, modifiers, custom fields, metafields, price-list behavior, customer-group logic, category placement, channel assignment, CMS Pages, Blog Posts, redirects, and app-related context to remain useful after migration. The right Migration Service should match that interpretation burden.

### What Migration Approach Means for BigCommerce <a href="#what-migration-approach-means-for-bigcommerce" id="what-migration-approach-means-for-bigcommerce"></a>

Migration approach determines how much responsibility, guidance, configuration support, and custom handling should be included before Full Migration begins. For BigCommerce, the approach should be chosen after reviewing how the future store will represent catalog choices, customer segments, storefront boundaries, pricing behavior, URL continuity, and custom data.

A lighter approach can work when the Source Platform is supported, the target BigCommerce structure is already clear, and the customer can review the Demo Migration confidently. A more guided approach is safer when the customer wants Next-Cart to carry more execution responsibility or when BigCommerce structure needs closer coordination. Custom Service becomes necessary when the migration requires bespoke transformation, Custom Platform handling, app-aware interpretation, custom field handling, outside-system identifiers, or custom migration logic adjustment.

The best approach is the one that prevents ambiguity from being discovered only after Full Migration.

### Why BigCommerce Approach Choice Depends on Structure <a href="#why-bigcommerce-approach-choice-depends-on-structure" id="why-bigcommerce-approach-choice-depends-on-structure"></a>

BigCommerce migration complexity often sits in how commerce behavior is represented. Product, category, customer, order, content, and URL data may appear straightforward until the migration must preserve how buyers actually browse, select, price, and purchase.

| BigCommerce area                                          | Approach impact                                                                                                                       |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Product options, variants, variant options, and modifiers | Determines whether product-choice logic can be mapped predictably or needs deeper interpretation.                                     |
| Customer groups, price lists, and bulk pricing            | Affects whether segmented commercial rules can be validated through standard handling or require additional configuration review.     |
| Categories, category trees, and product assignments       | Determines whether discovery, merchandising, and storefront structure are simple enough for standard migration or need guided review. |
| Channels and storefront scope                             | Adds risk when products, content, routes, or currencies must behave differently across storefront contexts.                           |
| Redirects, CMS Pages, and Blog Posts                      | Affects SEO continuity and whether URL evidence needs more deliberate handling.                                                       |
| Custom fields, metafields, apps, and external IDs         | Often determines whether Add-ons are enough or Custom Service is required.                                                            |

When these areas are documented and sample-tested, Standard Service or Managed Service may be enough. When their meaning is unclear, Custom Service should be considered earlier rather than after failed validation.

### Standard Service for BigCommerce <a href="#standard-service-for-bigcommerce" id="standard-service-for-bigcommerce"></a>

Standard Service is suitable when the migration path is supported, the BigCommerce target structure is known, and the customer team can manage review and acceptance with normal guidance.

Standard Service is often a strong fit when:

* product choices can be represented predictably through BigCommerce products, variants, variant options, modifiers, or product fields;
* category and category-tree expectations are already defined;
* customer groups, price lists, and bulk-pricing rules are documented clearly enough for validation;
* channels or storefront scope are simple or already mapped;
* CMS Pages, Blog Posts, and redirects are not unusually complex;
* app data, custom fields, metafields, and external identifiers are limited or non-critical;
* the customer team can review the Demo Migration and Full Migration thoroughly;
* the project does not require custom migration logic adjustment.

Standard Service should not be selected only because the store appears small. A smaller BigCommerce migration can still need stronger handling if product-choice rules, price-list behavior, storefront scope, or app data has important business meaning.

### Managed Service for BigCommerce <a href="#managed-service-for-bigcommerce" id="managed-service-for-bigcommerce"></a>

Managed Service is appropriate when BigCommerce is the right Target Platform, but the customer wants Next-Cart to carry more of the migration execution responsibility. It is useful when the project remains within standard service capability, yet the internal team does not want to manage the migration process alone.

Managed Service is often a good fit when:

* the customer wants more operational guidance through Demo Migration and Full Migration;
* the project includes several areas that need careful review, such as products, variants, modifiers, customer groups, price lists, categories, channels, and redirects;
* internal stakeholders can provide business decisions, access, and validation, but should not manage each migration step independently;
* migration success depends on coordinated review rather than bespoke transformation;
* the project does not require custom migration logic adjustment.

Managed Service is not the same as Custom Service. Managed Service changes execution responsibility; Custom Service changes how special data, custom behavior, unsupported structures, or bespoke migration requirements are handled.

### Custom Service for BigCommerce <a href="#custom-service-for-bigcommerce" id="custom-service-for-bigcommerce"></a>

Custom Service is the safer path when BigCommerce migration success depends on customization, modification, or bespoke handling beyond standard service capability.

Custom Service should be considered when:

* the Source Platform is a Custom Platform;
* product-choice logic does not map cleanly into BigCommerce products, variants, variant options, modifiers, or product fields;
* custom fields, metafields, or app-owned data need interpretation or transformation;
* customer groups, price lists, storefront assignments, or pricing rules require special handling;
* external IDs must remain aligned with ERP, CRM, fulfillment, marketplace, review, subscription, loyalty, tax, shipping, or analytics systems;
* selective migration or filtering requires defined inclusion and exclusion logic;
* legacy URLs, redirects, CMS Pages, Blog Posts, or route structures require custom treatment;
* the project needs custom migration logic adjustment.

Custom Service does not automatically mean Next-Cart performs full migration management. Migration management depends on the final service plan. The Custom Service boundary is about the customization or bespoke handling needed to make the migrated BigCommerce store meaningful.

### How Add-ons Fit Into the BigCommerce Approach <a href="#how-add-ons-fit-into-the-bigcommerce-approach" id="how-add-ons-fit-into-the-bigcommerce-approach"></a>

Add-ons can support a BigCommerce migration when the project needs optional filtering, mapping, or configuration support within supported service behavior. They should not be used as a substitute for Custom Service.

A Data Filter Add-on can be useful when the customer wants to migrate only selected products, customers, orders, categories, reviews, CMS Pages, Blog Posts, or historical records. Advanced Data Mapping or Advanced Data Configure can be useful when certain fields, mapped values, or target settings need more deliberate handling.

Add-ons are usually appropriate for bounded service enhancements. Custom Service is more appropriate when the project involves Custom Platform handling, source-side logic transformation, app-specific data interpretation, custom field rebuilding, outside-system identifiers, or custom migration logic adjustment.

### Entity Points and BigCommerce Scope Planning <a href="#entity-points-and-bigcommerce-scope-planning" id="entity-points-and-bigcommerce-scope-planning"></a>

Entity Points planning should account for the BigCommerce records that need to be migrated and accepted, especially Products, Customers, Orders, and Blog Posts. The key planning question is not only whether the Entity Points Plan has enough capacity, but whether the scoped records represent the business data the customer actually needs in the Target Platform.

If additional migration activity occurs later for the same service license, Entity Points should be evaluated according to whether the records are new to that service license record. Records that were already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when migrated for the first time.

This matters for BigCommerce when new products, customers, orders, or Blog Posts are added after an earlier migration step, or when the customer decides to include a broader historical scope after reviewing the Demo Migration.

### Demo Migration as the Approach Decision Point <a href="#demo-migration-as-the-approach-decision-point" id="demo-migration-as-the-approach-decision-point"></a>

A Demo Migration should test the BigCommerce cases most likely to affect approach selection. It should not only prove that records can appear in the Target Platform; it should show whether the migration approach is strong enough for the actual store structure.

For BigCommerce, Demo Migration samples should include:

* products with variants, variant options, modifiers, and custom fields;
* products that depend on price lists, bulk pricing, or customer-group behavior;
* categories and category-tree structures that matter for discovery and merchandising;
* products or content assigned to different channels or storefront contexts;
* CMS Pages, Blog Posts, and redirects that protect SEO-sensitive paths;
* customers and orders with important pricing, tax, shipping, discount, payment, or fulfillment context;
* app-owned data, metafields, external IDs, and integration-dependent records;
* Custom Platform records when the Source Platform is unsupported.

If the Demo Migration confirms that the chosen structure is clear and reviewable, Standard Service or Managed Service may be sufficient depending on the desired execution responsibility. If it exposes unresolved interpretation, the approach should be strengthened before Full Migration.

### How Additional Migration Options Affect Approach Planning <a href="#how-additional-migration-options-affect-approach-planning" id="how-additional-migration-options-affect-approach-planning"></a>

Additional Migration Options may become relevant when the customer needs to continue migration activity after an earlier migration step, use a different configuration, or perform a new migration for the same migration path. In BigCommerce, this should be planned around changed records, new records, and renewed validation needs.

Additional Migration Options should not be treated as a substitute for readiness, Demo Migration review, or Full Migration validation. If product options, price lists, category assignments, redirects, channel scope, custom fields, metafields, or app-dependent data changed after the earlier migration activity, those changes still need review in BigCommerce.

The safer approach is to treat follow-up migration activity as a reason to re-check the affected BigCommerce structures, not as proof that the store is ready for launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right BigCommerce migration approach should match the store’s structural burden. Standard Service can work well when the migration path is supported, the BigCommerce model is already clear, and the customer can validate the outcome confidently. Managed Service is stronger when the project still fits standard service capability but the customer wants Next-Cart to carry more execution responsibility. Custom Service becomes the safer path when product-choice logic, price lists, channels, redirects, custom fields, apps, external IDs, Custom Platform data, or bespoke transformation affects migration success.

Use the Demo Migration to decide whether the selected approach is strong enough. If the sample results expose unclear product choices, segmented pricing, storefront scope, route continuity, app-owned behavior, or custom data interpretation, clarify the service path before Full Migration rather than trying to repair the approach after launch risk appears.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a BigCommerce migration?**

Standard Service may be enough when the Source Platform is supported, the target BigCommerce structure is clear, and the customer can validate products, variants, modifiers, categories, customer groups, price lists, channels, redirects, customers, orders, and content confidently.

**When should a BigCommerce migration use Managed Service?**

Managed Service is useful when the project fits standard service capability but the customer wants Next-Cart to carry more migration execution responsibility while the internal team focuses on business decisions and validation.

**When does BigCommerce require Custom Service?**

Custom Service should be considered when the migration requires Custom Platform handling, custom field interpretation, app-aware data handling, external identifier preservation, selective transformation, storefront-specific handling, or custom migration logic adjustment.

**Do Add-ons replace Custom Service for BigCommerce?**

No. Add-ons support bounded filtering, mapping, or configuration needs. Custom Service is required when the project needs broader customization, bespoke transformation, Custom Platform handling, app-specific interpretation, or custom migration logic adjustment.

**Should Additional Migration Options change the service approach?**

They can affect the review scope. If follow-up migration activity introduces new or changed products, customers, orders, Blog Posts, price rules, redirects, channels, or custom data, the customer should revalidate those BigCommerce structures before relying on the migrated store.
