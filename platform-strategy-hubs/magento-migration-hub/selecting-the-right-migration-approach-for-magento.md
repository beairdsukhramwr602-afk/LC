# Selecting the Right Migration Approach for Magento

The right Magento Open Source migration approach depends on how much of the source store’s structure must remain usable inside Magento after launch. A small store can still need careful handling if it relies on configurable products, custom attributes, store-view content, extension-owned fields, external IDs, or custom inventory workflows. A larger store can still follow a straightforward path when its data is supported, its structure is clean, and the merchant can validate the output responsibly.

Approach selection should start from Magento-specific evidence: product types, attributes, attribute sets, websites, stores, store views, URL requirements, inventory assumptions, customer groups, order history, extension dependencies, and launch-window timing. Record count matters, but it should not be the only factor. The better question is whether the selected service path can preserve enough structure and business meaning for Magento Open Source to operate as the target store.

### What Migration Approach Means for Magento Open Source <a href="#what-migration-approach-means-for-magento-open-source" id="what-migration-approach-means-for-magento-open-source"></a>

A Magento Open Source migration approach is a decision about scope, responsibility, customization, and validation. The merchant should know which records are expected to migrate, which target settings must be configured in Magento, which requirements can be handled through Add-ons, which requirements need Custom Service review, and which Demo Migration samples must pass before Full Migration.

| Work type                                      | Magento example                                                                                                                         | Service-path implication                                                                 |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Supported migrated records                     | Products, categories, customers, orders, coupons, reviews, images, CMS Pages, Blog Posts, and supported related fields.                 | May fit Standard Service or Managed Service depending on complexity and execution needs. |
| Supported filtering, mapping, or configuration | Excluding obsolete products, aligning supported fields, or adjusting supported data output.                                             | May fit Add-ons when the requirement stays within supported behavior.                    |
| Custom or unsupported requirements             | Extension-owned records, custom modules, custom fields, external IDs, bespoke product logic, or Custom Platform source data.            | Requires Custom Service review.                                                          |
| Magento-side setup                             | Theme, checkout, payment, shipping, tax rules, store configuration, extensions, indexers, cache, integrations, and deployment settings. | Must be prepared and validated outside ordinary data migration output.                   |

This separation keeps the approach realistic. Standard Service should not be overloaded with unsupported custom requirements. Managed Service should not be treated as a substitute for scope clarity. Add-ons should not be used as a synonym for Custom Service. Custom Service should not be invoked for every complex-feeling case if the real need is supported filtering, mapping, or configuration.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be suitable when the Magento Open Source migration scope is supported, the target structure is clear, and the merchant can prepare and validate the result without heavy coordination. It works best when products, categories, customers, orders, and content follow recognizable patterns; attribute and attribute-set needs are manageable; and custom module data is not central to the migration expectation.

<table data-search="false"><thead><tr><th>Standard Service readiness signal</th><th>Magento-specific reason</th></tr></thead><tbody><tr><td>Product types are ordinary and documented.</td><td>Simple, configurable, virtual, downloadable, grouped, or bundle expectations can be reviewed within supported scope when examples are clear.</td></tr><tr><td>Attributes are controlled.</td><td>Source fields are classified, normalized, and not treated as unlimited target clutter.</td></tr><tr><td>Website/store/store-view structure is simple.</td><td>The target hierarchy does not require extensive localized mapping or multi-store governance.</td></tr><tr><td>URLs and content needs are manageable.</td><td>Priority product, category, CMS Page, and Blog Post routes can be prepared and reviewed without custom handling.</td></tr><tr><td>Inventory is straightforward.</td><td>Stock expectations are clear enough for customer-led review.</td></tr><tr><td>Customer groups and order statuses are informational or simple.</td><td>Historical records remain useful without complex business-rule preservation.</td></tr><tr><td>Extension and integration dependencies are limited.</td><td>Standard records are enough for the accepted migration outcome.</td></tr></tbody></table>

Standard Service still requires serious validation. Magento’s flexibility can hide errors that do not appear in record counts. The merchant should be able to review Demo Migration samples, confirm product type behavior, inspect attributes, check URLs, review customers and orders, and decide whether Full Migration output is acceptable.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be safer when the Magento Open Source migration remains within supported behavior but the execution burden is high. The store may not need Custom Service, yet the merchant may need stronger coordination, sequencing, and guided review because the migration involves many data areas or launch-sensitive assumptions.

Managed Service can be useful when the merchant has a large catalog, many configurable products, heavy image and URL review, multiple store views, many customer/order records, limited internal bandwidth, or a tight launch window. It can also help when the merchant wants Next-Cart-led execution support while the merchant remains responsible for final result verification and target-side configuration.

| Managed Service fit                     | Magento scenario                                                                                                         |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Supported scope with many review points | Products, categories, customers, orders, images, content, URLs, and reviews are supported but need coordinated handling. |
| Complex but supported catalog           | Configurable products, attribute sets, product images, category assignments, and URL keys require structured review.     |
| Multi-store or localized content        | Store-view-specific names, descriptions, metadata, and pages need careful validation.                                    |
| Launch timing is sensitive              | New source orders, customers, or inventory changes may need close-to-launch action planning.                             |
| Internal migration bandwidth is limited | The merchant needs more execution support while still validating the result.                                             |

Managed Service does not make unsupported data supported. If the requirement involves custom module tables, extension-owned entities, bespoke transformations, external-system logic, or Custom Platform behavior, Custom Service should be evaluated even if Managed Service is also useful for execution support.

### When Add-ons Are the Right Fit <a href="#when-add-ons-are-the-right-fit" id="when-add-ons-are-the-right-fit"></a>

Add-ons are appropriate when the requirement is specific, bounded, and still within supported migration behavior. They are useful when the merchant needs better filtering, mapping, or data configuration but does not need unsupported custom data handling.

For Magento Open Source, Add-ons can help when the source store includes outdated data, inconsistent field naming, selected records that should be excluded, or supported fields that need more careful target placement. The requirement should be stated as a concrete acceptance rule.

| Add-on need          | Magento example                                                                                                       | Boundary check                                                                                 |
| -------------------- | --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Data filtering       | Exclude obsolete products, inactive customers, old orders, unused Blog Posts, or test CMS Pages.                      | Filtering should not remove records needed for support, SEO, or reporting.                     |
| Advanced mapping     | Align supported product fields, customer fields, order fields, or content fields to appropriate Magento destinations. | Mapping cannot recreate unsupported module behavior.                                           |
| Data configuration   | Adjust supported output to improve target usability for product, category, customer, or content review.               | Configuration must remain within supported migration capability.                               |
| Bounded special need | Handle a clear, supported migration output preference.                                                                | Unsupported extension data, custom fields, or external IDs may require Custom Service instead. |

The Add-on decision should be practical. If the merchant asks to migrate supported products but exclude discontinued SKUs, an Add-on may fit. If the merchant asks to preserve data created by a custom pricing module, Custom Service review is more appropriate.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when the Magento Open Source migration requires custom evaluation or custom migration logic beyond supported behavior. Magento stores frequently contain extension-owned records, custom modules, custom attributes with special handling, external IDs, direct database customizations, ERP or PIM dependencies, search customizations, loyalty systems, subscriptions, marketplace references, and bespoke workflows.

The trigger is not size alone. The trigger is whether the data or behavior has a supported Magento destination under the chosen migration scope. A small custom catalog can need Custom Service if core selling behavior depends on unsupported fields. A large but clean catalog may not.

| Custom Service trigger                                                                   | Why it changes the approach                                                         |
| ---------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Extension-owned product, customer, order, pricing, loyalty, subscription, or review data | Standard records may not contain the data that drives the business process.         |
| Custom module tables or custom database columns                                          | The data may require bespoke extraction, transformation, or target placement.       |
| External identifiers used by ERP, PIM, CRM, accounting, marketplace, or shipping systems | Losing IDs can break reporting, reconciliation, fulfillment, or support continuity. |
| Custom product builders, bundles, or configurable logic                                  | Standard product mapping may not preserve the selling behavior.                     |
| Nonstandard order statuses, approval stages, or fulfillment workflows                    | Historical order interpretation may need custom preservation.                       |
| Custom Platform source behavior                                                          | Source structures may need custom analysis before Magento mapping can be trusted.   |

Custom Service should be scoped through examples. The merchant should provide representative products, attributes, orders, customers, custom fields, extension records, external IDs, and expected target outcomes. Without examples, the discussion becomes abstract and the risk of under-scoping increases.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should function as the evidence gate for Magento Open Source. It should not only preview record counts. It should show whether the selected approach preserves Magento-specific meaning and reveals whether the service path is too light, too heavy, or correctly scoped.

A useful Demo Migration should include:

<table data-search="false"><thead><tr><th>Sample area</th><th>Decision it should support</th></tr></thead><tbody><tr><td>Simple product</td><td>Confirms baseline product, category, image, price, tax, URL, and stock mapping.</td></tr><tr><td>Configurable product</td><td>Confirms parent/child SKU structure, variation attributes, images, prices, and inventory meaning.</td></tr><tr><td>Bundle or grouped product</td><td>Reveals whether product relationships require supported mapping, target setup, or Custom Service.</td></tr><tr><td>Product with custom options</td><td>Tests whether option behavior remains readable and useful.</td></tr><tr><td>Attribute-heavy product</td><td>Confirms attribute labels, values, sets, filters, and storefront/admin usefulness.</td></tr><tr><td>Store-view-specific product or page</td><td>Tests localization, metadata, URL keys, and content assignment.</td></tr><tr><td>Customer group example</td><td>Confirms whether source segmentation maps cleanly or needs another path.</td></tr><tr><td>Refunded or discounted order</td><td>Tests order history, selected options, totals, tax, payment labels, and support value.</td></tr><tr><td>Extension-owned field or external ID</td><td>Determines whether Add-ons, Custom Service, target setup, or exclusion is needed.</td></tr></tbody></table>

If Demo Migration shows that product relationships collapse, attribute values become noisy, store-view values appear in the wrong context, URL behavior is unclear, customer groups lose meaning, order history is unreadable, or custom records have no supported target destination, the approach should be corrected before Full Migration.

### Entity Points and Magento Scope Planning <a href="#entity-points-and-magento-scope-planning" id="entity-points-and-magento-scope-planning"></a>

Entity Points help plan eligible migration volume, but they do not measure Magento complexity by themselves. Products, Customers, Orders, and Blog Posts may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path, even if a later action replaces the previous target result.

For Magento Open Source, Entity Points should be considered together with data structure and service needs. A product count does not show whether the catalog includes configurable products, bundle logic, many child SKUs, custom attributes, store-view values, extension fields, or external IDs. An order count does not show whether historical records include complex options, refunds, invoices, shipments, custom statuses, or integration references.

| Scope signal     | What it helps estimate                           | What it does not prove                                                                                    |
| ---------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Product count    | Catalog volume and possible Entity Points usage. | Product-type complexity, attribute governance, image behavior, inventory meaning, or URL readiness.       |
| Customer count   | Buyer-record volume.                             | Customer-group meaning, duplicate quality, loyalty references, B2B-like assumptions, or external IDs.     |
| Order count      | Historical order volume.                         | Payment labels, refunds, shipments, invoices, selected options, status interpretation, or ERP references. |
| Blog Posts count | Content volume when relevant.                    | Whether content routes, metadata, internal links, media, and redirects are launch-ready.                  |

Entity Points should support planning, not replace service-path judgment. The selected approach should still be based on supported behavior, customization needs, execution responsibility, and validation evidence.

### Later Migration Actions and Launch Timing <a href="#later-migration-actions-and-launch-timing" id="later-migration-actions-and-launch-timing"></a>

Magento launch timing often requires decisions after an initial migration run. The source store may continue receiving new products, orders, customers, reviews, coupons, CMS Pages, Blog Posts, inventory updates, or URL changes while the target store is being reviewed.

The merchant may need to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration. These actions should be understood by expected outcome, not treated as old feature labels or backend mechanics.

| Later action                              | Magento planning implication                                                                                       |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Continue with the last used configuration | Validate newly added source records and selected regression samples from earlier migrated data.                    |
| Continue with a new configuration         | Validate the changed fields, filters, mapping choices, and affected record types.                                  |
| Perform a new migration                   | Review the refreshed target result and confirm whether earlier migrated target data has been replaced as expected. |

The selected service arrangement should also define responsibility. In Standard Service and Custom Service without Expert Handle, the customer performs available migration actions and verifies the result. In Managed Service and Custom Service with Expert Handle, Next-Cart can perform migration actions based on the customer’s request and agreed scope, while the customer remains responsible for final verification and migration outcome. Customers of any service arrangement can still access and perform available migration actions manually if they choose.

For Magento, later actions require careful validation because changes can affect product relationships, attributes, store-view content, URLs, customers, orders, inventory, and extension-dependent fields. A later action should never be treated as a shortcut around review.

### Signals That the Selected Approach Is Too Light <a href="#signals-that-the-selected-approach-is-too-light" id="signals-that-the-selected-approach-is-too-light"></a>

A Magento Open Source approach is too light when it treats structural complexity as ordinary record transfer. The warning signs usually appear before Full Migration if the sample set is chosen carefully.

<table data-search="false"><thead><tr><th>Warning signal</th><th>Likely response</th></tr></thead><tbody><tr><td>Product relationships cannot be classified clearly.</td><td>Rework product-type scope or consider Custom Service.</td></tr><tr><td>Attribute values are inconsistent, duplicated, or poorly governed.</td><td>Clean source values, revise mapping, or use Add-ons where supported.</td></tr><tr><td>Store-view content appears in the wrong context.</td><td>Revisit target structure and store-view mapping.</td></tr><tr><td>URL keys, redirects, or content routes are launch-critical but unplanned.</td><td>Strengthen preparation and validation before Full Migration.</td></tr><tr><td>Customer groups or historical order statuses drive business rules.</td><td>Review whether supported mapping is enough or Custom Service is needed.</td></tr><tr><td>Inventory depends on external systems or multi-source assumptions.</td><td>Separate migration snapshot, target setup, and integration responsibility.</td></tr><tr><td>Extension or custom module data is business-critical.</td><td>Do not rely on Add-ons unless the requirement remains supported; review Custom Service.</td></tr></tbody></table>

The approach should be adjusted when these signals appear. Continuing with a weak path usually creates more work during launch review because the team must separate migration defects from unsupported expectations and target-side setup gaps.

### Choosing the Practical Path <a href="#choosing-the-practical-path" id="choosing-the-practical-path"></a>

The practical Magento Open Source path is the lightest approach that still protects the business outcome. Standard Service can be enough when supported records and customer-led validation are realistic. Managed Service is safer when supported scope needs stronger execution coordination. Add-ons are useful for supported filtering, mapping, or configuration needs. Custom Service is required when unsupported, custom, extension-owned, external-system, or bespoke transformation requirements must be evaluated.

A service-path decision is ready when the merchant can state:

* which records are expected to migrate into Magento;
* which Magento settings, extensions, or workflows must be configured directly in the target environment;
* which Add-ons or Custom Service requirements are in scope;
* which Demo Migration samples must pass before Full Migration;
* which later migration actions may be needed before launch;
* who performs the migration actions and who verifies the final result.

If those statements are unclear, the service path is not ready. Magento Open Source migration rewards careful scope discipline because the platform can represent complex commerce structures, but only when the migration plan understands which structures must be preserved, reinterpreted, configured, customized, or left out.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento Open Source migration approach selection should be grounded in the target store’s actual operating needs. Standard Service, Managed Service, Add-ons, and Custom Service each have a role, but none should be chosen from volume alone. Product types, attributes, attribute sets, websites, stores, store views, URLs, content, inventory, customer groups, order history, extensions, custom data, Entity Points, later migration actions, and Demo Migration evidence all affect the practical path.

The right approach is the one that preserves supported Magento meaning without overpromising unsupported behavior. When the merchant separates migrated records from target-side setup, Add-ons, Custom Service, external systems, and validation responsibility, the migration becomes easier to execute and safer to approve.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for Magento Open Source?**

Standard Service may be enough when records are supported, product types are clear, attributes are controlled, store scope is simple, URLs are prepared, inventory expectations are manageable, and the merchant can validate Demo Migration and Full Migration results responsibly.

**When should Managed Service be considered?**

Managed Service is useful when the migration remains within supported capability but execution coordination is important. Large catalogs, many configurable products, localized content, URL review, many orders, or limited internal bandwidth can make Managed Service safer.

**How are Add-ons different from Custom Service for Magento?**

Add-ons adjust supported filtering, mapping, or configuration. Custom Service handles unsupported extension data, custom fields, external identifiers, bespoke transformations, Custom Platform behavior, or custom migration logic adjustment.

**Do Entity Points decide whether a Magento migration is complex?**

No. Entity Points help plan eligible migration volume. Complexity depends on product structure, attributes, scope, URLs, inventory, customer groups, orders, extensions, custom data, and validation burden.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that representative Magento records work as expected: product types, configurable relationships, attributes, categories, URLs, customers, orders, inventory, content, and any custom or extension-owned examples that affect scope.
