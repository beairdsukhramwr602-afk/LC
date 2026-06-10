# VTEX Pre-Migration Preparation Checklist

Preparation for a VTEX migration should make the target result easier to scope, test, and approve. VTEX is a hosted enterprise commerce platform with catalog, SKU, pricing, trade policy, checkout, OMS, marketplace, storefront, app, API, and integration layers that often need to be understood before migration results can be interpreted correctly.

A useful preparation phase separates three concerns: records that should migrate, target behavior that must be configured in VTEX, and external workflows that require separate integration or custom review. Without that separation, a Demo Migration may look acceptable by record count while important commercial behavior remains untested.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation should reduce ambiguity before Demo Migration or Full Migration. For VTEX, that means preparing representative data samples, confirming the target operating context, and identifying where standard migration handling may not be enough.

The goal is not to recreate every business rule before migration starts. The goal is to make sure the migration team and the merchant can recognize whether products, SKUs, prices, trade policies, orders, customers, storefront paths, marketplace relationships, apps, and integration references are moving into VTEX in a way that supports the intended operating model.

| Preparation area             | What to clarify before migration                                                                                             | Why it matters in VTEX                                                                                                      |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Target account context       | Account setup, enabled modules, storefront solution, sales channels, trade policies, apps, and integration stack.            | The same source data can behave differently depending on the VTEX account structure and enabled commerce layers.            |
| Catalog complexity           | Products, SKUs, specifications, categories, brands, images, stock, attachments, kits, collections, and product services.     | VTEX depends heavily on SKU-level structure and catalog configuration for sellability and storefront discovery.             |
| Pricing and commercial rules | Base prices, fixed prices, price tables, promotions, coupons, trade policies, and channel-specific pricing.                  | A product can exist in VTEX but still be commercially wrong if pricing and trade-policy context are missing.                |
| Orders and fulfillment       | OMS flows, seller context, marketplace context, statuses, payment labels, shipping methods, invoices, pickup, and delivery.  | Order history must remain readable for service, operations, finance, and fulfillment teams.                                 |
| Storefront and search        | FastStore, Store Framework, Legacy CMS Portal, headless storefronts, CMS content, search, facets, redirects, and SEO values. | Migrated records need to be discoverable and presented correctly in the intended storefront solution.                       |
| External systems             | ERP, PIM, WMS, accounting, payment, anti-fraud, marketplace, app, API, Master Data, and webhook dependencies.                | External references may carry business meaning that ordinary product, customer, or order fields do not preserve by default. |

### 1. Confirm the Target VTEX Account and Storefront Context <a href="#id-1-confirm-the-target-vtex-account-and-storefront-context" id="id-1-confirm-the-target-vtex-account-and-storefront-context"></a>

Before selecting samples or interpreting Demo Migration results, confirm how the target VTEX environment is expected to operate. VTEX is continuously updated as a SaaS platform, so planning should focus on the target account, enabled commerce modules, storefront solution, app stack, trade policies, marketplace setup, and integration requirements rather than a single static version number.

| Item to confirm                      | Preparation detail                                                                                                                                             |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Target account and workspace context | Confirm the VTEX account intended for migration review and whether separate workspaces or environments will be used for preparation, testing, or launch work.  |
| Storefront solution                  | Identify whether the target storefront uses FastStore, Store Framework, Legacy CMS Portal, a headless storefront, or another implementation approach.          |
| Commerce modules                     | Confirm catalog, pricing, promotions, checkout, payments, OMS, marketplace, seller, logistics, search, and B2B-related modules that affect launch readiness.   |
| Trade policies and sales channels    | List the sales channels, regions, customer groups, marketplaces, or B2B contexts that depend on trade-policy behavior.                                         |
| App stack                            | Identify VTEX IO apps, marketplace apps, storefront apps, search apps, payment apps, fulfillment apps, and business-process apps that affect migrated records. |
| Integration stack                    | List ERP, PIM, WMS, accounting, payment, anti-fraud, marketplace, CRM, data warehouse, and API-dependent systems.                                              |
| Custom data structures               | Identify Master Data entities, custom customer fields, custom checkout fields, external IDs, and implementation-specific references.                           |

This context should be ready before the Demo Migration is evaluated. Otherwise, the review may only confirm that records arrived, not that the records work in the intended VTEX operating model.

### 2. Prepare Catalog, SKU, Specification, and Category Samples <a href="#id-2-prepare-catalog-sku-specification-and-category-samples" id="id-2-prepare-catalog-sku-specification-and-category-samples"></a>

Catalog preparation is one of the most important VTEX migration tasks. VTEX treats products and SKUs as distinct concepts, and the target result must support product presentation, sellable SKU structure, specification meaning, category placement, search discovery, pricing, inventory, and storefront availability.

Prepare samples that represent the real catalog rather than only the simplest products.

| Sample type                        | What to include                                                                                                            | Why it matters                                                                                    |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Simple product                     | Product name, description, brand, category, image, SKU, price, and stock.                                                  | Establishes the baseline migration result for ordinary catalog records.                           |
| Multi-SKU product                  | Several SKU variations with different attributes, images, prices, stock, and availability.                                 | Shows whether source variants translate correctly into VTEX SKU structure.                        |
| Specification-heavy product        | Product and SKU specification values used for filtering, search, merchandising, comparison, or compliance.                 | Confirms whether source attributes preserve useful storefront and operational meaning.            |
| Category-sensitive product         | Product placed in important departments, categories, subcategories, collections, or merchandising structures.              | Helps detect category and navigation issues before launch planning.                               |
| Stock-sensitive product            | Product with inventory differences by SKU, warehouse, fulfillment rule, or channel if relevant.                            | Prevents acceptance of products that exist but cannot be sold correctly.                          |
| Attachment or configurable product | Product that depends on attachments, assembly options, services, personalization, bundles, kits, or special configuration. | Identifies requirements that may need custom interpretation rather than standard variant mapping. |
| Marketplace-relevant product       | Product with seller, marketplace, channel, external ID, or offer-related context.                                          | Separates ordinary catalog migration from marketplace or seller workflow planning.                |

Catalog samples should include products that are commercially important, structurally complex, and operationally sensitive. A Demo Migration that only uses simple products may not reveal SKU, specification, pricing, search, or channel issues.

### 3. Prepare Pricing, Promotion, and Trade Policy Evidence <a href="#id-3-prepare-pricing-promotion-and-trade-policy-evidence" id="id-3-prepare-pricing-promotion-and-trade-policy-evidence"></a>

VTEX pricing can depend on base prices, fixed prices, price tables, promotions, coupons, trade policies, sales channels, customer context, and marketplace behavior. Before migration, identify where source-store pricing is simple and where it reflects business rules.

| Pricing or commercial rule     | Preparation detail                                                                                                            |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Base prices                    | Prepare examples of ordinary product and SKU prices.                                                                          |
| Fixed prices                   | Include SKUs where price differs from the general base-price expectation.                                                     |
| Price tables                   | Identify customer-specific, channel-specific, B2B, regional, or marketplace-related price tables.                             |
| Trade policies                 | List trade policies that affect catalog availability, pricing, payment, logistics, region, seller, or sales-channel behavior. |
| Promotions and coupons         | Prepare examples of active, expired, conditional, category-specific, customer-specific, or order-value promotions.            |
| Discounts in historical orders | Identify orders where discounts must remain understandable after migration.                                                   |
| External pricing systems       | List ERP, PIM, marketplace, or custom pricing dependencies that may control prices outside the source platform.               |

Historical discount labels and migrated order totals do not prove that live VTEX pricing and promotion behavior is configured. Preparation should make that boundary clear before testing begins.

### 4. Prepare Customer, B2B, Master Data, and Consent Evidence <a href="#id-4-prepare-customer-b2b-master-data-and-consent-evidence" id="id-4-prepare-customer-b2b-master-data-and-consent-evidence"></a>

Customer data in VTEX can involve more than customer names, emails, and addresses. B2B commerce, customer profiles, custom fields, approval flows, account relationships, buyer roles, consent preferences, and Master Data entities may affect how customers are understood after migration.

Prepare customer samples across ordinary and complex scenarios.

| Customer or data area   | What to prepare                                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Ordinary customers      | Name, email, phone, addresses, customer profile fields, and order relationships.                                                         |
| B2B accounts            | Company account context, buying organization, user roles, approval requirements, price eligibility, and shared addresses where relevant. |
| Customer segmentation   | Groups, tags, lists, trade-policy-related eligibility, or marketing segmentation used in commerce decisions.                             |
| Consent and preferences | Marketing permissions, privacy preferences, newsletter status, and communication preferences where available and relevant.               |
| Master Data             | Custom entities, custom fields, business records, relationship data, and external identifiers used by operations or integrations.        |
| External customer IDs   | CRM, ERP, accounting, loyalty, marketplace, or customer-service identifiers that must remain traceable.                                  |

Custom customer structures should be reviewed early. If B2B relationships, Master Data records, or custom fields carry business logic, they may not behave like ordinary customer fields in a standard migration path.

### 5. Prepare Order, Seller, Marketplace, and Fulfillment Samples <a href="#id-5-prepare-order-seller-marketplace-and-fulfillment-samples" id="id-5-prepare-order-seller-marketplace-and-fulfillment-samples"></a>

VTEX order review should cover the way historical orders will be read and interpreted inside the OMS context. Orders may include payment labels, shipping methods, invoices, fulfillment status, pickup or delivery behavior, seller context, marketplace context, external references, and customer relationships.

Prepare orders that show different operational scenarios.

| Order sample                 | What it should demonstrate                                                                       |
| ---------------------------- | ------------------------------------------------------------------------------------------------ |
| Standard completed order     | Product lines, customer, totals, payment label, shipping method, status, and fulfillment result. |
| Canceled or refunded order   | Whether order state and financial meaning remain understandable after migration.                 |
| Partially fulfilled order    | Fulfillment complexity, item-level handling, shipping status, and operational readability.       |
| Marketplace order            | Marketplace origin, seller context, commission or channel references, and order-flow meaning.    |
| Seller order                 | Seller-side context, fulfillment responsibility, and operational separation where applicable.    |
| Pickup or delivery order     | Logistics distinction, shipping method, address, pickup point, and fulfillment expectation.      |
| Discounted order             | Promotions, coupons, price adjustments, and final totals.                                        |
| External-system-linked order | ERP, WMS, accounting, payment, anti-fraud, marketplace, or service references.                   |

Order preparation should also identify what does not need to migrate. Some operational workflows may be better reconfigured in VTEX rather than recreated as historical order data.

### 6. Separate Migrated History from Live Checkout Setup <a href="#id-6-separate-migrated-history-from-live-checkout-setup" id="id-6-separate-migrated-history-from-live-checkout-setup"></a>

One common preparation mistake is treating historical order data as proof that live checkout is ready. These are separate concerns. Migrated orders may preserve historical payment labels, shipping labels, discounts, customer addresses, and fulfillment context, while live checkout still requires VTEX configuration and testing.

| Live behavior area              | Preparation question                                                                                                                                                    |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Checkout `orderForm`            | Are custom fields, marketing data, customer profile data, seller information, shipping selections, coupons, and payment information expected in the live checkout flow? |
| Payments                        | Which payment methods, payment conditions, payment integrations, gift card providers, anti-fraud providers, or provider protocols must be configured?                   |
| Shipping and logistics          | Which delivery methods, pickup options, carriers, warehouses, fulfillment rules, and logistics integrations must be active for launch?                                  |
| Taxes and totals                | Which tax rules, regional requirements, customer contexts, or sales-channel rules influence final totals?                                                               |
| Coupons and promotions          | Which discounts must be configured as live commercial rules rather than only shown in historical order records?                                                         |
| Marketplace and seller checkout | Which seller selection, channel mapping, commission, or marketplace behavior must be tested through live orders?                                                        |
| Custom checkout fields          | Which checkout fields or data capture requirements are ordinary supported fields, and which require custom review?                                                      |

Migration acceptance should not depend on historical order labels alone. Live test orders should prove checkout, payment, shipping, tax, promotion, and order routing behavior before launch.

### 7. Prepare Storefront, CMS, Search, URL, and SEO Evidence <a href="#id-7-prepare-storefront-cms-search-url-and-seo-evidence" id="id-7-prepare-storefront-cms-search-url-and-seo-evidence"></a>

VTEX storefront behavior depends on the chosen storefront solution, content structure, search configuration, navigation, category experience, product detail pages, URL strategy, metadata, redirects, and SEO requirements. Data migration should be reviewed alongside storefront planning, not treated as a replacement for it.

| Storefront or SEO area     | What to prepare                                                                                                                              |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Storefront solution        | Confirm FastStore, Store Framework, Legacy CMS Portal, headless storefront, or custom frontend expectations.                                 |
| Product detail pages       | Prepare high-value product examples with images, specifications, price visibility, availability, related content, and buying flow.           |
| Category and listing pages | Include important department, category, subcategory, collection, and landing-page paths.                                                     |
| Search and facets          | Prepare terms, filters, facets, autocomplete expectations, suggested terms, and merchandising-sensitive search cases.                        |
| CMS and content            | Identify CMS Pages, Blog Posts, campaign pages, brand pages, buying guides, landing pages, and content blocks that affect conversion or SEO. |
| URLs and redirects         | Prepare priority product URLs, category URLs, content URLs, redirect rules, and expected route changes.                                      |
| SEO metadata               | Gather titles, descriptions, canonical expectations, image alt text, sitemap concerns, and high-value organic landing pages.                 |

Storefront readiness should include both customer-facing presentation and discoverability. Products that exist in VTEX still need to appear in the right paths, search results, facets, landing pages, and checkout context.

### 8. Inventory Apps, APIs, ERP/PIM/WMS, and External Systems <a href="#id-8-inventory-apps-apis-erp-pim-wms-and-external-systems" id="id-8-inventory-apps-apis-erp-pim-wms-and-external-systems"></a>

VTEX projects often depend on more than migrated records. Apps, APIs, Master Data, VTEX IO extensions, ERP, PIM, WMS, accounting, payment, anti-fraud, marketplace, analytics, search, CRM, and headless frontend dependencies may carry business meaning that should be scoped before migration.

Create an inventory that separates data, configuration, integration behavior, and custom logic.

| Dependency type             | What to document                                                                                                 | Migration planning implication                                                                                |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| VTEX IO apps                | App name, purpose, related records, fields, storefront impact, and whether the app owns important data.          | App-owned data may require separate review or Custom Service if it is not part of standard supported records. |
| Master Data                 | Entity names, fields, relationships, external IDs, and operational use.                                          | Custom Master Data structures may need mapping, custom logic, or accepted exclusions.                         |
| ERP integration             | Product, price, inventory, order, invoice, customer, and fulfillment dependencies.                               | External IDs and synchronization rules should be reviewed separately from record migration.                   |
| PIM integration             | Product enrichment, attributes, media, categories, specifications, and approval workflows.                       | Catalog meaning may come from the PIM rather than the source commerce database alone.                         |
| WMS and logistics           | Warehouse IDs, carrier rules, fulfillment workflows, pickup or delivery requirements, and tracking references.   | Fulfillment readiness may require target configuration and integration testing.                               |
| Payment and anti-fraud      | Provider references, authorization states, gift cards, fraud checks, transaction IDs, and operational reporting. | Historical payment data and live payment configuration should be separated.                                   |
| Marketplace connectors      | Seller IDs, offers, SKU suggestions, matching rules, commissions, and sales-channel mapping.                     | Marketplace and seller behavior may require custom review beyond product migration.                           |
| Headless or custom frontend | API dependencies, route expectations, content sources, cart behavior, and account/profile behavior.              | Storefront implementation may be separate from migration scope.                                               |

This inventory should identify which dependencies must be migrated, reconfigured, rebuilt, validated separately, or routed to Custom Service.

### 9. Choose Demo Migration Samples Deliberately <a href="#id-9-choose-demo-migration-samples-deliberately" id="id-9-choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the parts of the VTEX migration that carry the most business risk. Sample selection should not be random and should not rely only on high-volume records.

| Demo Migration sample               | Include when                                                                                               | What it should prove                                                      |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Complex SKU product                 | Variants, required specifications, images, stock, price, category, or availability affect selling.         | SKU structure remains usable, active, discoverable, and purchasable.      |
| Price table or trade-policy product | Sales channel, B2B, regional, customer, or marketplace pricing matters.                                    | Price behavior can be interpreted correctly in the target context.        |
| Promotion or coupon example         | Discounts influence order totals, customer eligibility, or campaign reporting.                             | Historical and live promotion expectations are separated correctly.       |
| B2B customer or account             | Company context, buyer roles, account relationships, approvals, or special prices matter.                  | Customer meaning goes beyond ordinary profile fields.                     |
| Marketplace or seller order         | Seller context, marketplace flow, commission, received SKU, or channel mapping matters.                    | Seller and marketplace meaning is not flattened into ordinary order data. |
| OMS status variation                | Orders include cancellation, refund, partial fulfillment, delivery, pickup, or external status references. | Operations can interpret historical order status after migration.         |
| Storefront/search sample            | Product discovery depends on category, search, facets, collection, landing page, or route behavior.        | Migrated records are visible and meaningful to shoppers.                  |
| App or Master Data sample           | App-owned fields, custom entities, external IDs, or API references affect business processes.              | Standard migration scope is enough, or Custom Service review is needed.   |
| Priority URL sample                 | SEO value or customer access depends on product/category/content URL continuity.                           | Redirect and metadata planning is visible before launch.                  |

A strong Demo Migration sample set should include records that are complex, commercially important, operationally sensitive, and integration-dependent. Simple samples can confirm baseline movement, but they rarely prove VTEX readiness.

### 10. Identify Add-on and Custom Service Signals Early <a href="#id-10-identify-add-on-and-custom-service-signals-early" id="id-10-identify-add-on-and-custom-service-signals-early"></a>

Preparation should identify whether the migration can remain within standard service capability or whether additional service planning is needed. This does not mean every complex case becomes custom work, but it does mean the right signals should be raised before Full Migration.

| Signal found during preparation                                                                                      | Likely review path                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Only selected eligible records should migrate                                                                        | Review the Data Filter Add-on where available. Estimated entity numbers are not migration filters.                                                                |
| Supported field mapping needs controlled adjustment                                                                  | Review Advanced Data Mapping if the mapping fits available platform capability.                                                                                   |
| Supported values need modification before reaching VTEX                                                              | Review Advanced Data Configure if the change fits available service capability.                                                                                   |
| Custom Platform source                                                                                               | Custom Service.                                                                                                                                                   |
| Custom product configurators, non-standard bundles, custom SKU logic, or special assembly behavior                   | Custom Service because custom migration logic adjustment or tailored data interpretation is required.                                                             |
| Complex price table, trade-policy, promotion, or B2B pricing transformation                                          | Custom Service when the requirement goes beyond supported mapping or configuration.                                                                               |
| Marketplace/seller architecture, received SKU logic, offer matching, commissions, or external marketplace workflows  | Custom Service review because the data carries marketplace workflow meaning.                                                                                      |
| Master Data custom entities, app-owned fields, external IDs, or custom checkout `orderForm` fields                   | Custom Service review when standard supported structures do not cover the requirement.                                                                            |
| ERP/PIM/WMS/accounting/payment/anti-fraud/headless dependencies                                                      | Custom Service review when external-system relationships must be preserved, transformed, or reconnected.                                                          |
| Storefront rebuild, headless implementation, FastStore/Store Framework transition, or complex CMS/SEO transformation | Separate implementation or Custom Service review depending on whether the requirement affects migration logic, content transformation, or storefront build scope. |

Add-ons should be considered for filtering, mapping, and data configuration needs within available capability. Custom Service is the path for customization, modification, Custom Platform handling, app-owned data, external-system dependencies, tailored behavior, and custom migration logic adjustment.

### Conclusion <a href="#conclusion" id="conclusion"></a>

A VTEX migration is easier to scope when preparation reflects the platform’s real operating layers. Catalog records, SKUs, specifications, pricing, trade policies, checkout data, orders, seller context, storefront behavior, apps, Master Data, and external-system references should be prepared as connected business evidence, not isolated exports.

Before running Demo Migration, gather representative samples that show how the current store actually works. Include complex SKUs, pricing rules, B2B customers, marketplace or seller orders, storefront paths, SEO-sensitive URLs, and integration-dependent records. Then use the Demo Migration result to confirm what can stay within standard service capability, what needs Add-on support, and what belongs in Custom Service review.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to VTEX?**

Start by confirming the target VTEX account context, storefront solution, trade policies, marketplace or seller setup, app stack, and integration dependencies. Then prepare representative catalog, customer, order, pricing, storefront, and external-system samples.

**Which catalog samples are most useful for VTEX preparation?**

The most useful samples are products with multiple SKUs, required specifications, category dependencies, images, stock, price differences, attachments, kits, services, marketplace context, or trade-policy-specific behavior. These records reveal more than simple products.

**Should pricing and trade policies be prepared before Demo Migration?**

Yes. VTEX pricing can depend on base prices, fixed prices, price tables, promotions, coupons, and trade policies. Preparing examples early helps determine whether the expected result fits standard mapping, Add-on support, or Custom Service review.

**Does migrating historical orders configure live VTEX checkout?**

No. Historical orders can preserve payment, shipping, discount, fulfillment, and customer context, but live checkout, payments, tax, shipping, logistics, promotions, and `orderForm`behavior require target configuration and live testing.

**When should Custom Service be considered for VTEX preparation?**

Custom Service should be considered when the migration involves Custom Platform source data, custom SKU logic, non-standard product structures, complex B2B account logic, marketplace or seller workflow data, custom Master Data, app-owned records, custom checkout fields, or external-system relationships that require tailored handling.
