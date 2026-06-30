# VTEX Pre-Migration Preparation Checklist

VTEX preparation should prove that the target environment can interpret migrated data inside a connected enterprise commerce operation. A useful checklist is not a generic export list. It is an evidence plan that connects source records with VTEX catalog structure, SKUs, specifications, pricing, promotions, customer records, orders, marketplace context, logistics, Master Data, storefront implementation, and external systems.

Preparation also needs to separate migrated data from VTEX-side implementation. Products, customers, orders, CMS Pages, Blog Posts, and related records may be migrated when supported, but storefront architecture, app configuration, integrations, live payment setup, logistics rules, seller operations, search behavior, promotions, and custom business processes may still require VTEX configuration or implementation work. When that separation is unclear, Demo Migration can look acceptable while launch readiness remains weak.

### Define the Target VTEX Operating Model <a href="#define-the-target-vtex-operating-model" id="define-the-target-vtex-operating-model"></a>

The first preparation task is to define how VTEX will operate after launch. Some merchants use VTEX primarily as a commerce platform with strong catalog and checkout capabilities. Others use VTEX as part of a marketplace operation, B2B environment, headless storefront, multi-region architecture, or integration-heavy enterprise stack. Each scenario changes what should be prepared before migration.

The team should identify which operating layers are part of launch and which are future scope. A project involving only supported product and order history requires a different preparation package from a project involving marketplace sellers, Master Data, PIM-owned enrichment, ERP-owned pricing, external inventory, headless storefront routing, or B2B account structures.

| VTEX operating layer         | Preparation question                                                                                                          | Why it matters before migration                                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Catalog and SKUs             | Which source product structures must become usable VTEX products, SKUs, categories, brands, and specifications?               | The migration must preserve sellable meaning, not only product names and counts.  |
| Pricing and promotions       | Which prices, price tables, coupons, discounts, or campaign rules are migrated data, and which are target-side configuration? | Commercial logic can be flattened if pricing ownership is not clarified.          |
| Marketplace and sellers      | Are seller relationships, received SKUs, offers, commissions, or marketplace order context part of the expectation?           | Marketplace data may require custom interpretation or separate configuration.     |
| Customers and B2B            | Are customer profiles, segmentation, corporate accounts, buyer relationships, or custom fields required?                      | Customer meaning can extend beyond ordinary contact records.                      |
| Orders and fulfillment       | What historical order context must remain readable for service, finance, operations, or support?                              | Order history must be useful without being confused with live checkout setup.     |
| Master Data and integrations | Which custom entities, external IDs, app data, or integration-owned fields matter after launch?                               | Standard record migration may not preserve custom operational meaning.            |
| Storefront and content       | Which pages, URLs, metadata, search behavior, navigation, and content assets affect launch continuity?                        | Headless or composable storefront work must not be mistaken for record migration. |

This operating model gives the rest of the checklist a clear purpose. The merchant is not preparing for VTEX in general; the merchant is preparing for a specific VTEX launch scenario.

### Prepare Catalog, SKU, and Specification Evidence <a href="#prepare-catalog-sku-and-specification-evidence" id="prepare-catalog-sku-and-specification-evidence"></a>

Catalog preparation is usually the highest-value VTEX readiness task because source products often need to be interpreted through VTEX products, SKUs, categories, brands, and specifications. A source platform may treat variants, attributes, options, custom fields, bundles, collections, personalization choices, or channel-specific catalog values differently from VTEX. Preparation should expose those differences before migration execution.

A strong catalog sample set should include simple products and structurally difficult products. The team should prepare products with multiple SKUs, category-sensitive specifications, different images by SKU, search/facet values, brand relationships, stock differences, price variations, discontinued products, and commercial edge cases. Products tied to apps, PIM systems, ERP records, marketplace sellers, or custom source fields should be marked clearly.

| Catalog evidence            | What to prepare                                                                           | Readiness value                                                            |
| --------------------------- | ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Baseline product            | Product name, description, category, brand, SKU, image, price, and stock.                 | Confirms the ordinary migration path.                                      |
| Multi-SKU product           | Size, color, model, package, region, or other sellable choices.                           | Tests whether source options become usable VTEX SKUs.                      |
| Specification-heavy product | Values used for filters, comparison, compliance, merchandising, or search.                | Confirms structured product meaning is not buried in descriptions.         |
| Category-sensitive product  | Products tied to category-specific attributes or navigation logic.                        | Tests whether category placement and specification behavior stay aligned.  |
| Marketplace-linked product  | Seller, offer, received SKU, external ID, or marketplace-specific value.                  | Clarifies whether marketplace context belongs in migration scope.          |
| Custom or app-owned product | Custom fields, app values, bundle rules, personalization choices, or external references. | Identifies Add-ons, Custom Service, exclusion, or target-side setup needs. |

Catalog preparation should not try to force every source behavior into ordinary product migration. Its purpose is to decide which values migrate as supported records, which need supported mapping or filtering, which require Custom Service, and which should be rebuilt or configured in VTEX.

### Prepare Pricing, Promotion, and Channel Inputs <a href="#prepare-pricing-promotion-and-channel-inputs" id="prepare-pricing-promotion-and-channel-inputs"></a>

VTEX preparation should treat commercial rules as a separate readiness area because pricing and promotions may depend on source logic that is not visible in ordinary product exports. Base prices, price tables, promotional rules, coupons, customer-specific pricing, regional behavior, marketplace pricing, and B2B conditions should be reviewed before the migration approach is chosen.

Prepare examples that show ordinary pricing and exception pricing. Include active and expired promotions where historical review matters, customer- or segment-specific pricing where applicable, SKU-level price differences, channel-specific values, marketplace pricing assumptions, and any external system that owns price authority. If the source platform depends on an ERP, PIM, pricing engine, marketplace connector, or custom promotion module, the preparation package should identify who owns that value after migration.

| Commercial input                      | Preparation detail                                                             | Planning decision                                                                 |
| ------------------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| Base price                            | Normal SKU prices and currency assumptions.                                    | Confirms baseline migrated price expectations.                                    |
| Price tables or differentiated prices | Customer group, B2B, regional, channel, or marketplace price examples.         | Decides whether values are migrated, configured, or custom-scoped.                |
| Promotions and coupons                | Active, historical, category-specific, customer-specific, or cart-level rules. | Separates historical promotional data from live campaign setup.                   |
| Tax and display assumptions           | Source tax behavior, display expectations, and order-history tax examples.     | Prevents historical tax context from being mistaken for target tax configuration. |
| External price owner                  | ERP, PIM, pricing engine, marketplace connector, or custom script.             | Identifies integration responsibility and Custom Service signals.                 |

Commercial preparation should produce acceptance examples. The team should know which migrated values must be visible, which values are only historical references, and which commercial rules must be configured directly in VTEX.

### Prepare Customer, B2B, and Master Data Context <a href="#prepare-customer-b2b-and-master-data-context" id="prepare-customer-b2b-and-master-data-context"></a>

Customer preparation for VTEX should go beyond names, emails, phone numbers, and addresses. Enterprise environments often carry customer segmentation, B2B account relationships, custom fields, consent values, external identifiers, CRM references, loyalty details, and Master Data entities that influence service, marketing, pricing, or reporting.

The team should prepare representative customer samples: ordinary customers, repeat buyers, guest customers, customers with multiple addresses, customers linked to many orders, duplicate records, B2B buyers, corporate accounts, customers with custom fields, and customers tied to external systems. When Master Data or external systems are involved, the preparation package should identify the entity, source owner, target expectation, sample record, and validation owner.

| Customer or data context           | Preparation question                                                      | Likely handling path                                                                    |
| ---------------------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Standard customer profile          | Are supported contact and address fields sufficient?                      | Standard Service or Managed Service may be enough.                                      |
| Customer segmentation              | Is the segment needed for pricing, promotions, service, or reporting?     | Supported mapping, Add-ons, target setup, or Custom Service depending on structure.     |
| B2B account context                | Are company, buyer, approval, or role relationships expected?             | Requires careful scope review and may need Custom Service or target-side configuration. |
| Master Data entity                 | Is the record a standard customer/order/product field or a custom entity? | Custom Service review is likely if the entity must migrate.                             |
| External identifier                | Does ERP, CRM, WMS, marketplace, or accounting continuity depend on it?   | Custom Service or supported mapping depending on destination and behavior.              |
| Consent or privacy-sensitive value | Is the value required, valid, and legally usable after migration?         | Requires merchant-side governance and careful validation.                               |

This step prevents customer data from being approved by count alone. The result should support service, segmentation, account lookup, order review, and any approved business process that depends on customer meaning.

### Prepare Orders, Logistics, and Operational History <a href="#prepare-orders-logistics-and-operational-history" id="prepare-orders-logistics-and-operational-history"></a>

Historical orders should be prepared as operational evidence, not as proof that live VTEX checkout and fulfillment are configured. Migrated order history may support customer service, finance review, reconciliation, and reporting, but live payment, shipping, tax, promotions, OMS behavior, logistics, seller handling, and notifications still require VTEX-side setup and testing.

Prepare order examples that expose the real source history. Include completed orders, canceled orders, refunded orders, partially fulfilled orders, discounted orders, tax-sensitive orders, orders with multiple shipments, marketplace orders, seller-related orders, B2B orders, payment-reference examples, and orders with external IDs. If the source uses an external OMS, ERP, WMS, payment gateway, marketplace connector, or fulfillment system, identify which values must remain visible after migration and which must be reconnected through implementation work.

| Order evidence                    | What to prepare                                                           | What it should prove                                                 |
| --------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Ordinary completed order          | Line items, totals, customer link, payment reference, fulfillment status. | Historical readability and baseline order transfer.                  |
| Refunded or canceled order        | Refund values, cancellation reason, status history, payment references.   | Exception history remains understandable.                            |
| Discounted or tax-sensitive order | Coupons, promotions, tax values, shipping, fees, adjustments.             | Financial context remains reviewable.                                |
| Marketplace or seller order       | Seller references, offer context, fulfillment owner, marketplace status.  | Marketplace meaning is migrated, excluded, or separately configured. |
| Integration-linked order          | ERP, OMS, WMS, CRM, accounting, or support identifiers.                   | External continuity requirements are scoped correctly.               |

Preparation should define the difference between historical order usability and live VTEX operation. That distinction reduces false launch confidence.

### Prepare Storefront, Search, URL, and Content Inputs <a href="#prepare-storefront-search-url-and-content-inputs" id="prepare-storefront-search-url-and-content-inputs"></a>

VTEX storefront preparation should be handled separately from catalog preparation. Products and SKUs can migrate while storefront implementation, routing, search, facets, navigation, content pages, CMS behavior, redirects, and SEO-sensitive URLs still require target-side work.

The team should prepare top product URLs, category URLs, search and filter examples, priority landing pages, CMS Pages, Blog Posts, metadata examples, redirect priorities, navigation notes, product-page expectations, and pages tied to campaigns or organic search. For headless or composable storefronts, route behavior and frontend ownership should be clarified before migration validation begins.

| Storefront input             | Preparation purpose                                                   |
| ---------------------------- | --------------------------------------------------------------------- |
| Priority URLs                | Protect traffic and customer landing paths during launch.             |
| Category and search examples | Confirm that specifications and categories support discovery.         |
| CMS Pages and Blog Posts     | Decide what migrates, what is rebuilt, and what is redirected.        |
| Metadata and content assets  | Support search continuity and page-quality review where supported.    |
| Redirect plan                | Prevent URL continuity from being deferred until launch week.         |
| Storefront ownership         | Separate migrated data from frontend implementation and routing work. |
| Search/facet examples        | Confirm that structured values support discovery after migration.     |

Storefront preparation should result in a practical launch map: what the migration provides, what VTEX configuration provides, what the frontend team builds, and what SEO or content owners must validate.

### Identify Apps, APIs, External Systems, and Custom Scope <a href="#identify-apps-apis-external-systems-and-custom-scope" id="identify-apps-apis-external-systems-and-custom-scope"></a>

VTEX migrations often depend on systems outside the core source store. ERP, PIM, WMS, OMS, CRM, accounting, tax, fraud, search, marketplace, loyalty, subscription, personalization, analytics, and middleware systems may own data that the merchant expects to see in VTEX. Preparation should identify those dependencies before Demo Migration.

Each dependency should be recorded with its business purpose, data owner, source fields, target expectation, sample records, and required handling path. The classification should separate supported migration, Add-ons, Custom Service, exclusion, manual rebuild, and VTEX-side setup.

| Requirement type                                                                                    | Better planning path                                                                |
| --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Supported data that needs filtering                                                                 | Consider a Data Filter Add-on when the filter is clear and supported.               |
| Supported fields that need careful destination alignment                                            | Consider Advanced Data Mapping when the target field is supported.                  |
| Supported output that needs bounded configuration                                                   | Consider Advanced Data Configure when behavior remains within supported capability. |
| Custom entities, app data, external IDs, bespoke transformations, or unsupported records            | Review for Custom Service.                                                          |
| Storefront implementation, VTEX apps, integrations, payments, logistics, and live operational setup | Prepare as target-side implementation or configuration.                             |

The key boundary is practical: Add-ons adjust supported filtering, mapping, or configuration; Custom Service is for unsupported, custom, external-system, or bespoke migration requirements.

### Prepare Demo Migration Samples and Review Ownership <a href="#prepare-demo-migration-samples-and-review-ownership" id="prepare-demo-migration-samples-and-review-ownership"></a>

Demo Migration should be designed to test VTEX meaning, not only record presence. The sample set should include ordinary records and the records most likely to expose structural gaps. Each sample should have an owner who can approve the result from a business perspective.

| Sample area                  | Reviewer                              | What the sample should prove                                                              |
| ---------------------------- | ------------------------------------- | ----------------------------------------------------------------------------------------- |
| Catalog and SKUs             | Catalog or merchandising owner        | Products, SKUs, categories, brands, specifications, images, and stock remain usable.      |
| Pricing and promotions       | Commercial or pricing owner           | Migrated commercial values are understandable and target-side setup needs are known.      |
| Customers and B2B            | CRM, support, or account owner        | Profiles, addresses, segmentation, and business context remain useful.                    |
| Orders and logistics         | Operations, finance, or support owner | Historical orders remain readable for service and reconciliation.                         |
| Master Data and integrations | Technical or data owner               | Custom entities, external IDs, and integration values are scoped correctly.               |
| Storefront and SEO           | Frontend, content, or SEO owner       | URLs, content, search, navigation, and launch-sensitive pages have a clear handling plan. |

A sample should fail the preparation gate if nobody can explain what success looks like. VTEX readiness depends on owner-approved evidence, not only migration output.

### Plan the Launch Window and Later Migration Activity <a href="#plan-the-launch-window-and-later-migration-activity" id="plan-the-launch-window-and-later-migration-activity"></a>

Many merchants keep the source store active while VTEX is prepared. New products, customers, orders, Blog Posts, content updates, price changes, marketplace records, or integration updates may appear after the first migration run. Preparation should define how later migration activity will be handled before launch.

The team should decide whether later activity should continue with the last used configuration, continue with a new configuration, or require a new migration. The choice affects what needs to be revalidated. A configuration change may require renewed review of fields, filters, mappings, or affected records. A new migration may require broader target review if earlier migrated data is replaced.

Entity Points should be understood correctly during this planning. New eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Eligible entities already recorded through the service license do not consume Entity Points again only because another migration action occurs on the same migration path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX preparation should create a practical evidence package for an enterprise commerce environment. The merchant should prepare catalog and SKU samples, pricing and promotion examples, customer and B2B context, Master Data expectations, historical order samples, storefront and URL inputs, integration dependencies, Demo Migration samples, ownership assignments, and launch-window decisions.

A strong preparation process makes the difference between a record transfer and a controlled VTEX migration. It shows what should migrate, what should be configured in VTEX, what needs Add-ons, what requires Custom Service review, and what must be validated before Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a VTEX migration?**

Start with the target operating model. Clarify whether VTEX will support ordinary catalog migration, marketplace operations, B2B, headless storefronts, complex integrations, or custom Master Data. That decision determines which evidence matters most.

**Why are catalog and SKU samples so important for VTEX?**

VTEX catalog meaning depends on products, SKUs, categories, brands, and specifications. Representative samples reveal whether source products become usable VTEX records or whether mapping, configuration, custom handling, or manual setup is needed.

**Should storefront readiness be prepared separately from product migration?**

Yes. Product and SKU migration can support storefront work, but URLs, routing, search, facets, navigation, CMS Pages, Blog Posts, metadata, and frontend implementation require separate planning and validation.

**When should Master Data or external systems be reviewed?**

They should be reviewed before Demo Migration if they contain customer context, custom entities, external IDs, integration values, segmentation, marketplace data, or operational fields that the business expects to use after launch.

**How should later migration activity be planned for VTEX?**

Define whether the next action should continue with the last used configuration, continue with a new configuration, or perform a new migration. Then decide which products, customers, orders, Blog Posts, fields, mappings, and launch-critical samples must be revalidated.
