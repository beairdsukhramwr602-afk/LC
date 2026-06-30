# Selecting the Right Migration Approach for BigCommerce

The right BigCommerce migration approach depends on how much of the source store can become supported BigCommerce data without losing business meaning. A simple product catalog may fit a straightforward path. A variant-heavy catalog, segmented pricing structure, multi-channel setup, custom fields, app-owned records, external identifiers, or SEO-sensitive redirect plan may require stronger preparation, Add-ons, Managed Service, or Custom Service review.

Service-path choice should not begin with store size alone. BigCommerce complexity often comes from product choices, pricing rules, channel assignments, storefront continuity, customer segmentation, integrations, and target-side configuration. A large store can still follow a manageable path when the data is supported and reviewable. A smaller store can need Custom Service when app or custom data is central to operations.

### What Migration Approach Means for BigCommerce <a href="#what-migration-approach-means-for-bigcommerce" id="what-migration-approach-means-for-bigcommerce"></a>

A BigCommerce migration approach is a decision about scope, responsibility, support level, and validation depth. The approach should define which records should move into BigCommerce, which target-side settings must be configured in BigCommerce, which Add-ons are needed for supported adjustments, which requirements need Custom Service, and which Demo Migration samples must pass before Full Migration.

| Work type                          | BigCommerce example                                                                                                      | Service-path implication                                                                 |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Supported migrated records         | Products, categories, customers, orders, images, content pages, redirects, and supported related fields.                 | May fit Standard Service or Managed Service depending on execution and validation needs. |
| Supported adjustments              | Filtering, mapping, or configuration changes for supported product, customer, order, content, or redirect data.          | May require Add-ons.                                                                     |
| Custom or unsupported requirements | App-owned data, custom fields, external identifiers, bespoke pricing logic, feed data, or special transformation.        | Requires Custom Service review.                                                          |
| Target-side setup                  | Storefront theme, checkout settings, payment setup, tax rules, shipping settings, apps, channels, and live integrations. | Must be configured and tested in BigCommerce rather than treated as migrated records.    |

The right path protects the merchant from two opposite mistakes: choosing too light a path for complex business data, or escalating every platform-specific detail to Custom Service when a supported Add-on or target-side setup task is enough.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the BigCommerce scope is supported, the source data is clean, and the merchant can prepare inputs and validate the result confidently. This usually means products, categories, customers, orders, images, pages, redirects, and related fields can be migrated without bespoke transformation or unsupported app-data handling.

Standard Service is strongest when product choices are simple or clearly structured, pricing is not heavily segmented, channel expectations are limited, customer data is mostly standard, and the merchant can review Demo Migration samples without intensive coordination.

| Standard Service readiness signal                                               | BigCommerce-specific reason                                                   |
| ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Products have clear SKUs, options, variants, images, and categories.            | Catalog review can focus on supported BigCommerce product structures.         |
| Modifiers or shopper customization are limited or easy to identify.             | The catalog is less likely to need special interpretation.                    |
| Pricing is mostly base price, sale price, or simple supported discount context. | Advanced price-list or B2B pricing complexity is limited.                     |
| Channels are simple or not part of launch complexity.                           | Product visibility and storefront scope are easier to validate.               |
| Customers and orders are ordinary historical records.                           | Buyer lookup and order history can be checked through representative samples. |
| Redirects and content scope are clear.                                          | SEO continuity can be reviewed without custom content transformation.         |

Standard Service becomes risky when the merchant cannot explain how source product options, pricing, channels, or app data should appear in BigCommerce. A supported record type does not automatically mean every source behavior is supported.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be safer when the data is mostly supported but the execution path needs coordination, sequencing, and expert handling. This can happen when the merchant has a large catalog, many product options, important redirects, high-value order history, launch-sensitive SEO, multi-channel visibility, or limited internal capacity for migration execution.

Managed Service can reduce operational strain, but it does not convert unsupported app records into standard migration scope. It is best understood as a stronger execution and coordination path for supported or clearly scoped data. If unsupported records or bespoke transformations are involved, Custom Service may still be required.

| Managed Service fit                     | BigCommerce scenario                                                                                     |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Supported scope with many review points | Products, variants, categories, images, customers, orders, pages, and redirects need coordinated review. |
| High-value SEO continuity               | Redirects, product URLs, category URLs, pages, and metadata require careful launch sequencing.           |
| Variant-heavy catalog                   | Product choices are supported but need disciplined sample review.                                        |
| Multi-channel or pricing sensitivity    | Channel assignments, price lists, or customer group pricing require structured validation.               |
| Limited merchant bandwidth              | The merchant wants Next-Cart-led execution support while retaining final result verification.            |

Managed Service should be chosen for execution support and review discipline, not as a substitute for scope clarity. The merchant still needs acceptance criteria and representative samples.

### When Add-ons Can Solve the Need <a href="#when-add-ons-can-solve-the-need" id="when-add-ons-can-solve-the-need"></a>

Add-ons are useful when the requirement is supported, bounded, and specific. They help with filtering, mapping, or data configuration within supported behavior. They are not a replacement for Custom Service when the requirement involves unsupported records, external systems, bespoke transformations, or app-owned data that BigCommerce does not receive as ordinary migration data.

| Add-on need                  | BigCommerce example                                                                                             | Boundary check                                                                                             |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Filter records               | Move selected products, customers, orders, pages, Blog Posts, or inactive records according to agreed criteria. | The filter should be clear and should not remove records needed for service, reporting, or SEO continuity. |
| Map supported fields         | Align source fields with supported BigCommerce destinations.                                                    | Mapping cannot create unsupported BigCommerce behavior.                                                    |
| Configure supported output   | Adjust supported data handling to improve BigCommerce usability.                                                | Configuration must remain within migration capability.                                                     |
| Handle bounded special needs | Apply a specific supported adjustment to products, categories, URLs, customers, or orders.                      | If custom logic or unsupported records are involved, Custom Service is safer.                              |

Good Add-on requests are written as precise acceptance criteria. Weak Add-on requests use broad language such as “make it match our old store” without defining the supported fields or behavior.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when the BigCommerce migration requirement goes beyond supported standard behavior. The trigger is not the merchant’s size. The trigger is custom data, unsupported source structures, bespoke transformation, app records, external identifiers, Custom Platform handling, or custom migration logic adjustment.

BigCommerce custom needs often appear around product options, custom fields, metafields, pricing, ERP data, subscriptions, reviews, marketplace feeds, B2B-like structures, customer segmentation, loyalty records, and headless or app-connected storefront behavior.

| Custom Service trigger                                                                          | Why it changes the approach                                                       |
| ----------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Source product options do not fit cleanly into variants, variant options, or modifiers.         | The catalog may need bespoke interpretation before BigCommerce can use it.        |
| App-owned subscriptions, loyalty, bundles, reviews, feeds, or marketplace records are expected. | The data may not belong to standard platform records.                             |
| Custom fields or external identifiers must remain usable for ERP, CRM, accounting, or support.  | Supported mapping may not preserve business meaning.                              |
| Advanced pricing logic depends on custom or external rules.                                     | Price lists or bulk pricing may not fully represent the source behavior.          |
| Source content depends on page builders, scripts, or custom storefront logic.                   | BigCommerce content and redirects may require special handling or manual rebuild. |
| A Custom Platform is part of the source or target situation.                                    | Source structures may need direct analysis before mapping can be trusted.         |

Custom Service should be scoped through examples. The merchant should provide representative products, customers, orders, content records, custom fields, app exports, external identifiers, and expected outcomes. Without examples, custom discussion stays too abstract to produce a reliable service path.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should decide whether the selected BigCommerce approach is strong enough. It should not be treated as a basic preview of record counts. The sample set should prove that BigCommerce-specific data meaning survives the migration.

| Demo Migration sample                    | Decision it should support                                         |
| ---------------------------------------- | ------------------------------------------------------------------ |
| Simple product                           | Baseline product, category, image, price, and inventory mapping.   |
| Variant-heavy product                    | Whether options and variants behave correctly.                     |
| Modifier-like product                    | Whether shopper customization needs another path.                  |
| Product with custom fields or metafields | Whether mapping is supported or Custom Service is needed.          |
| Price-list or bulk-pricing example       | Whether pricing expectations are supported, configured, or custom. |
| Channel-specific product                 | Whether channel assignment and visibility need review.             |
| Customer with group or custom field      | Whether customer identity and segmentation are preserved.          |
| Discounted or refunded order             | Whether historical order context remains readable.                 |
| Priority URL or content page             | Whether SEO and redirect expectations need adjustment.             |

The approach is too light if Demo Migration cannot explain product choices, pricing, channel scope, customer segmentation, redirects, or app-owned data. The correct response is to adjust scope before Full Migration, not to hope that the full run will solve the mismatch.

### Entity Points and BigCommerce Scope Planning <a href="#entity-points-and-bigcommerce-scope-planning" id="entity-points-and-bigcommerce-scope-planning"></a>

Entity Points help plan selected entity volume, but they do not prove that source data fits BigCommerce. Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path. New eligible records may consume Entity Points when migrated for the first time.

For BigCommerce, Entity Points should be reviewed alongside structure and complexity. A small source store may need Custom Service if it depends on app-owned fields, external IDs, custom pricing, or storefront logic. A larger store may fit Standard Service or Managed Service when the records are supported and the merchant can validate them.

| Scope signal     | What it helps estimate                           | What it does not prove                                                                          |
| ---------------- | ------------------------------------------------ | ----------------------------------------------------------------------------------------------- |
| Product count    | Catalog volume and possible Entity Points usage. | Whether variants, modifiers, custom fields, images, categories, and channels map correctly.     |
| Customer count   | Buyer-record volume.                             | Whether groups, custom fields, duplicates, external IDs, and buyer relationships remain useful. |
| Order count      | Historical order volume.                         | Whether refunds, discounts, payment context, fulfillment, and custom statuses remain readable.  |
| Blog Posts count | Content volume when relevant.                    | Whether URLs, redirects, metadata, and content presentation are launch-ready.                   |

Entity Points should support planning, not replace service-path evaluation.

### Later Migration Actions and Launch Timing <a href="#later-migration-actions-and-launch-timing" id="later-migration-actions-and-launch-timing"></a>

BigCommerce launch timing can require additional migration activity after Demo Migration or after an initial Full Migration run. The merchant may need to continue the migration with the last used configuration, continue with a new configuration, or perform a new migration. The chosen action should match the business outcome.

* Continuing with the last used configuration is usually relevant when the source store keeps receiving new eligible records and the configuration remains acceptable.
* Continuing with a new configuration is relevant when filters, mapping, or configuration choices need to change.
* Performing a new migration is relevant when the earlier target result should be replaced with a refreshed result.

The service path should clarify who performs the action and who validates the result. Under Standard Service and Custom Service without Expert Handle, the customer performs available migration actions and verifies the result. Under Managed Service and Custom Service with Expert Handle, Next-Cart can perform migration actions based on the customer’s request and agreed scope, while the customer remains responsible for final result verification and migration outcome.

For BigCommerce, later migration actions most often affect new products, customers, orders, Blog Posts, redirects, pricing changes, channel assignment changes, or revised mapping decisions. Each action should trigger the right validation set.

### Signals That the Chosen Approach Is Too Light <a href="#signals-that-the-chosen-approach-is-too-light" id="signals-that-the-chosen-approach-is-too-light"></a>

A BigCommerce approach is too light when it treats platform-specific complexity as ordinary record transfer. The warning signs usually appear in catalog meaning, pricing, channel scope, redirects, customer segmentation, or app data.

| Warning signal                                                                                        | Likely response                                                    |
| ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Product choices cannot be classified as variants, variant options, modifiers, setup, or custom scope. | Rework catalog scope before selecting the final path.              |
| Price lists, customer-group pricing, or bulk pricing are business-critical but not sampled.           | Add pricing samples and review Add-ons or Custom Service needs.    |
| Channel assignments or product visibility differ by storefront.                                       | Strengthen channel preparation and validation.                     |
| Redirects, CMS Pages, or Blog Posts are high-value but loosely scoped.                                | Treat content and SEO continuity as launch-critical evidence.      |
| Custom fields, metafields, app data, or external IDs are central to operations.                       | Review Custom Service rather than assuming ordinary field mapping. |
| Demo Migration uses only simple products and clean orders.                                            | Expand the sample set before Full Migration.                       |
| Source data continues changing near launch without a later-action plan.                               | Define timing, migration action, ownership, and revalidation.      |

These signals should be handled before Full Migration. Waiting until launch makes it harder to distinguish migration issues from target-side BigCommerce setup gaps.

### Choosing the Practical Path <a href="#choosing-the-practical-path" id="choosing-the-practical-path"></a>

The practical BigCommerce approach is the lightest path that still protects the business outcome. Standard Service may be enough when supported records and customer-led validation are realistic. Managed Service is safer when supported scope requires stronger coordination. Add-ons are appropriate when supported records need filtering, mapping, or configuration. Custom Service is necessary when unsupported, custom, app-owned, external-system, or bespoke transformation needs must be evaluated.

A reliable approach can be summarized in four statements:

* which records should migrate into BigCommerce;
* which BigCommerce settings, apps, channels, or storefront behaviors must be configured separately;
* which Add-ons or Custom Service requirements are in scope;
* which Demo Migration samples must pass before Full Migration.

If those statements are clear, the approach is usually ready to proceed. If they are unclear, the merchant should refine scope before treating service-path selection as complete.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce migration approach selection should be grounded in how the merchant expects BigCommerce to operate after launch. Standard Service, Managed Service, Add-ons, and Custom Service each have a role, but none should be chosen from record counts alone. The right approach accounts for catalog structure, variants, modifiers, price lists, channels, customers, orders, redirects, content, apps, Entity Points, later migration actions, and Demo Migration evidence.

A practical service path protects both migration execution and business validation. It should explain what migrates, what must be configured in BigCommerce, what needs Add-ons, what requires Custom Service, and what must be proven before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for a BigCommerce migration?**

Standard Service may be enough when the BigCommerce scope is supported, product structures are clear, pricing and channels are manageable, customers and orders are straightforward, redirects and content are scoped, and the merchant can validate the result confidently.

**When should Managed Service be considered?**

Managed Service is useful when the migration remains within supported capability but needs stronger execution support, coordination, sample review, launch sequencing, or help managing catalog, redirect, pricing, or channel validation pressure.

**How are Add-ons different from Custom Service?**

Add-ons adjust supported filtering, mapping, or configuration. Custom Service handles unsupported records, app-owned data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

**Do Entity Points decide whether a BigCommerce migration is complex?**

No. Entity Points help estimate eligible migration volume. Complexity depends on data meaning, such as variants, modifiers, custom fields, price lists, channels, redirects, customer segmentation, and app-owned records.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that representative BigCommerce records work as expected: products, variants, modifiers, pricing examples, customer records, order samples, redirects, content, channel assignments, and any custom or integration-owned examples where relevant.
