# BigCommerce Pre-Migration Preparation Checklist

BigCommerce preparation should prove that source data can become usable BigCommerce commerce data, not only that the source store can be exported. BigCommerce is a hosted SaaS Target Platform with structured catalog resources, product variants and variant options, product modifiers, custom fields, metafields, category assignments, channel assignments, price lists, customers, orders, redirects, content pages, and app-connected behavior. Preparation should therefore focus on the evidence that explains how those structures should behave after migration.

A useful BigCommerce checklist is not a generic access-and-backup list. It should clarify what the merchant expects BigCommerce to own, what should remain part of target-side setup, what depends on apps or external systems, and what needs Add-ons or Custom Service review. The merchant should enter Demo Migration with representative examples, not vague assumptions about products, customers, orders, pricing, or redirects.

### Define the BigCommerce Operating Target <a href="#define-the-bigcommerce-operating-target" id="define-the-bigcommerce-operating-target"></a>

Preparation starts by defining how the business intends to use BigCommerce after launch. Some merchants choose BigCommerce for a structured SaaS catalog and storefront. Others care about multi-channel selling, variant-heavy products, customer-group pricing, B2B-like purchasing needs, headless storefront architecture, app-connected operations, or stronger checkout and order-management workflow. Each operating target changes what should be prepared before migration.

A merchant moving from a smaller hosted platform may mainly need clean product, customer, order, category, and redirect evidence. A merchant moving from Magento, Adobe Commerce, WooCommerce, Shopify Plus, or a custom system may need deeper preparation around product options, price lists, custom fields, metafields, customer groups, content, channels, apps, and external identifiers.

| BigCommerce operating target             | Preparation focus                                                                                    | Why it matters                                                                                         |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Standard storefront migration            | Products, variants, categories, customers, orders, images, redirects, and pages.                     | Confirms that ordinary commerce records can be reviewed cleanly in BigCommerce.                        |
| Variant-heavy catalog                    | Options, variants, modifiers, SKUs, images, inventory, and product rules.                            | Prevents product choices from becoming confusing or incomplete after migration.                        |
| Multi-channel selling                    | Channel assignments, storefront context, product visibility, and catalog scope.                      | BigCommerce channel behavior can change which records must be reviewed for each storefront or channel. |
| Segmented pricing                        | Price lists, customer groups, bulk pricing, promotions, and source pricing rules.                    | Pricing can be business-critical and should not be treated as simple product-price transfer.           |
| Content and SEO continuity               | Product URLs, category URLs, redirects, CMS Pages, Blog Posts, metadata, and navigation.             | Online traffic and customer landing paths may depend on more than product records.                     |
| App- or integration-dependent operations | Apps, external IDs, ERP/CRM/accounting references, reviews, subscriptions, feeds, and custom fields. | Unsupported or app-owned records may need Custom Service, external setup, or exclusion.                |

This operating target should guide every later preparation step. Without it, the merchant may collect too much generic data while missing the few examples that would reveal the real migration risk.

### Prepare Catalog and Product-Choice Evidence <a href="#prepare-catalog-and-product-choice-evidence" id="prepare-catalog-and-product-choice-evidence"></a>

BigCommerce catalog preparation should begin with representative product samples. Product counts are useful for scope, but they do not show whether the source catalog can be interpreted as BigCommerce products, variants, variant options, modifiers, custom fields, images, category assignments, and channel assignments.

The preparation set should include simple products, variant-heavy products, products with modifiers or shopper-entered choices, products with custom fields, products with metafield-like data, products assigned to multiple categories, products sold in different channels, discounted products, price-list examples, image-heavy products, and products that depend on apps or source-side custom logic.

| Product evidence to prepare                                                 | BigCommerce question it should answer                                                          |
| --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Simple product with SKU, price, category, image, and inventory              | Can the basic catalog structure move cleanly?                                                  |
| Product with size, color, material, or package choices                      | Should source options become variants, variant options, or another BigCommerce structure?      |
| Product with engraving, customization, gift wrap, or shopper-entered fields | Is the choice closer to a modifier or a target-side setup need?                                |
| Product with bulk pricing or quantity discounts                             | Is pricing a supported record, Add-on need, Custom Service need, or target-side pricing setup? |
| Product assigned to several categories or storefronts                       | Does category and channel assignment need explicit review?                                     |
| Product with external IDs, custom fields, or app-owned metadata             | Does the value belong to supported mapping, Add-ons, Custom Service, or an external system?    |

Catalog preparation should define which source choices affect sellable variants and which choices affect shopper customization, pricing, display, filtering, reporting, inventory, or external integrations. That distinction will affect Article 6-style service-path decisions, but the preparation work must happen earlier so the service path is based on evidence.

### Prepare Pricing, Customer Group, and Promotion Inputs <a href="#prepare-pricing-customer-group-and-promotion-inputs" id="prepare-pricing-customer-group-and-promotion-inputs"></a>

BigCommerce preparation should not treat pricing as a single product price when the source store uses customer groups, wholesale pricing, tiered pricing, bulk discounts, price lists, coupons, catalog price rules, or app-driven promotions. Even when basic prices migrate cleanly, advanced pricing behavior may require separate planning.

Prepare examples that show how pricing is actually used. Include ordinary retail prices, sale prices, quantity discounts, customer-group-specific prices, wholesale examples, tax-sensitive examples, and any external pricing references used for ERP, B2B, marketplace, or sales-team workflows.

| Pricing input                     | Preparation decision                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------- |
| Base product prices               | Confirm expected product-level pricing in BigCommerce.                                |
| Sale prices or promotional prices | Decide whether they migrate as fields, configuration, or target-side promotion setup. |
| Bulk pricing rules                | Confirm whether supported data is clear enough for migration and validation.          |
| Price lists                       | Identify whether segmented pricing is part of migration scope or target setup.        |
| Customer-group pricing            | Confirm whether source customer segmentation should affect target pricing behavior.   |
| Coupon and discount records       | Separate historical discount data from active promotional setup.                      |
| External pricing identifiers      | Classify as supported mapping, Add-on, Custom Service, or external integration work.  |

Pricing evidence should be reviewed with business owners, not only technical staff. A small pricing mismatch can create larger commercial consequences than a minor content mismatch.

### Prepare Channel, Storefront, and Visibility Inputs <a href="#prepare-channel-storefront-and-visibility-inputs" id="prepare-channel-storefront-and-visibility-inputs"></a>

BigCommerce channel preparation matters when the merchant sells through more than one storefront, marketplace, region, brand, or headless experience. A source store may use store views, sales channels, marketplace listings, language-specific storefronts, regional catalogs, or app-managed feeds. These may not map automatically to BigCommerce channel behavior.

Prepare a channel map when channel scope matters. The map should identify which source records belong to which target channel or storefront context, which products should be visible or hidden, which categories matter by channel, which price or customer-group rules are channel-sensitive, and which content or redirects belong to each storefront experience.

| Channel preparation item                     | Why it matters                                                                |
| -------------------------------------------- | ----------------------------------------------------------------------------- |
| List of active storefronts or sales channels | Prevents all records from being reviewed as if they belong to one storefront. |
| Product-channel assignment examples          | Confirms whether products should appear in each target channel.               |
| Channel-specific categories or navigation    | Separates catalog organization from storefront discovery.                     |
| Regional or language-specific URLs           | Supports redirect and SEO planning.                                           |
| Marketplace or feed-managed records          | Identifies external-system dependencies.                                      |
| Headless storefront dependencies             | Clarifies which presentation behavior is outside ordinary migrated records.   |

If channel logic is unclear, the migration may move records correctly while the merchant still cannot validate whether the right records are available in the right storefront context.

### Prepare Customer and Order Examples <a href="#prepare-customer-and-order-examples" id="prepare-customer-and-order-examples"></a>

Customer and order preparation should focus on how BigCommerce will support buyer lookup, order history, operational review, and post-launch customer service. Customer counts do not reveal whether the migrated result will preserve useful identity, segmentation, order association, pricing context, or support history.

Prepare customer examples that include complete profiles, guest buyers, repeat buyers, duplicate emails, customers with multiple addresses, customers assigned to groups, customers with custom fields, customers with external CRM or ERP identifiers, and customers with important order history. If the source platform contains B2B-like account structures, company-level permissions, wholesale roles, or sales-rep assignments, those should be identified before scope is finalized.

Order examples should include ordinary completed orders and exception cases: refunded orders, cancelled orders, discounted orders, orders with coupons, orders with tax adjustments, orders with shipping charges, orders tied to customer groups, orders with external payment references, orders with custom statuses, and orders created through apps or marketplaces.

| Record type              | Examples to prepare                                                                                | Planning value                                              |
| ------------------------ | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Customers                | Repeat buyers, guest buyers, customer groups, duplicates, custom fields, external IDs.             | Confirms identity, segmentation, and lookup expectations.   |
| Orders                   | Completed, refunded, discounted, tax-sensitive, high-value, marketplace, and custom-status orders. | Confirms historical readability and operational usefulness. |
| Payments and refunds     | Payment labels, transaction references, refunds, adjustments, and external processor references.   | Separates historical context from live payment setup.       |
| Fulfillment and shipping | Multiple shipment examples, pickup/delivery assumptions, shipping methods, and status examples.    | Confirms whether source status logic needs interpretation.  |

This sample set should be used during Demo Migration review. It should not be postponed until Full Migration because customer and order issues can be hard to interpret after the full data set is moved.

### Prepare Content, URL, Redirect, and SEO Inputs <a href="#prepare-content-url-redirect-and-seo-inputs" id="prepare-content-url-redirect-and-seo-inputs"></a>

BigCommerce preparation should treat SEO and storefront continuity as a structured input set. Products and categories may migrate, but URL behavior, redirects, CMS Pages, Blog Posts, metadata, navigation, and content blocks still need review. A source category may have been an admin grouping, a public collection page, a campaign landing page, and an SEO asset at the same time.

Prepare the high-value URLs first. The merchant should identify top product URLs, top category URLs, important CMS Pages, Blog Posts, policy pages, landing pages, filtered collection pages, and URLs with meaningful traffic or backlinks. Those URLs should be connected to redirect expectations and target content decisions.

| SEO or content input | Preparation decision                                                                 |
| -------------------- | ------------------------------------------------------------------------------------ |
| Product URLs         | Decide whether equivalent BigCommerce product URLs and redirects are needed.         |
| Category URLs        | Decide whether categories, navigation, and redirect planning match the source value. |
| CMS Pages            | Decide whether content should migrate, be rebuilt, redirected, or retired.           |
| Blog Posts           | Decide whether they are in scope and whether Entity Points planning is relevant.     |
| Metadata             | Identify title, description, and other SEO fields that matter for priority pages.    |
| Navigation           | Separate category migration from menu and storefront experience setup.               |
| Redirect list        | Prepare source-to-target mapping for priority URLs.                                  |

Content and redirect preparation should include ownership. Some tasks are migration scope. Some are BigCommerce-side setup. Some are SEO strategy work. Some may need Custom Service when source content is app-owned, page-builder-dependent, or structurally different from BigCommerce content resources.

### Identify Apps, Integrations, Custom Fields, and External Data <a href="#identify-apps-integrations-custom-fields-and-external-data" id="identify-apps-integrations-custom-fields-and-external-data"></a>

BigCommerce migration preparation should identify which source records come from the platform itself and which come from apps, extensions, custom code, integrations, or external systems. Hosted SaaS platforms can look simple on the surface while important business behavior lives in apps, private fields, APIs, external feeds, or connected systems.

Create a dependency inventory for apps and systems that affect products, reviews, subscriptions, bundles, loyalty, ERP, accounting, CRM, inventory, marketplaces, tax, shipping, search, recommendations, content, B2B workflows, personalization, or pricing. For each dependency, record the business purpose, sample records, expected target behavior, and likely handling path.

| Dependency type                                   | Preparation path                                                                         |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Supported field requiring filtering               | Add-on may be suitable when the requirement stays within supported behavior.             |
| Supported field requiring mapping                 | Advanced Data Mapping or related Add-on may be suitable.                                 |
| Supported data requiring configuration adjustment | Add-on may be suitable when no bespoke migration logic is needed.                        |
| App-owned records or unsupported fields           | Custom Service review is usually needed.                                                 |
| External IDs or system references                 | Custom Service review may be needed when identifiers must remain usable.                 |
| Live app configuration                            | Treat as target-side setup or third-party integration work, not ordinary migration data. |

This classification protects the scope. Add-ons are for supported filtering, mapping, or configuration needs. Custom Service is for customization, unsupported data, app records, bespoke transformation, external-system complexity, or custom migration logic adjustment.

### Prepare Access, Exports, Backups, and Demo Migration Samples <a href="#prepare-access-exports-backups-and-demo-migration-samples" id="prepare-access-exports-backups-and-demo-migration-samples"></a>

Access preparation should include the source platform, the BigCommerce store, relevant exports, API credentials where applicable, product media, URL lists, customer/order samples, app exports, and any external system reports needed to interpret the source data. Backups and export copies should be retained so the team can compare source state with target result.

Demo Migration should be planned as a proof exercise, not only a preview. The sample set should include records that reveal BigCommerce-specific questions:

| Demo Migration sample                           | What it should prove                                             |
| ----------------------------------------------- | ---------------------------------------------------------------- |
| Simple product                                  | Basic product, category, image, price, and inventory mapping.    |
| Variant-heavy product                           | Whether options and variants behave as expected.                 |
| Modifier-like product                           | Whether shopper customization needs a different handling path.   |
| Product with custom fields or metafields        | Whether supported mapping is enough or Custom Service is needed. |
| Product with price list or bulk pricing context | Whether advanced pricing assumptions need additional scope.      |
| Channel-specific product                        | Whether visibility or channel assignment should be reviewed.     |
| Customer with group or custom field             | Whether customer identity and segmentation are preserved.        |
| Refunded or discounted order                    | Whether historical order meaning remains readable.               |
| Priority URL or content page                    | Whether redirects and content continuity need additional work.   |

The Demo Migration result should determine whether the selected path is sufficient. If the samples show that product choices, pricing, redirects, or app-owned data cannot be reviewed cleanly, the plan should be corrected before Full Migration.

### Plan the Migration Window and Later Migration Actions <a href="#plan-the-migration-window-and-later-migration-actions" id="plan-the-migration-window-and-later-migration-actions"></a>

BigCommerce preparation should account for the time between the first migration run and launch. Source stores often continue receiving orders, customers, product updates, inventory changes, content changes, and price adjustments during the launch window. The merchant should know whether later migration activity is expected and what it should affect.

When later activity is needed, use the current action language. The merchant may need to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration. The correct action depends on whether the goal is to add newly created source records, apply changed settings or mapping, or replace the earlier target result with a refreshed migration.

| Launch-window condition                                              | Preparation implication                                                                                                             |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| New source orders and customers appear after Demo Migration          | Plan how those records will be moved and validated.                                                                                 |
| Product, pricing, or URL mapping changes after review                | Determine whether continuing with a new configuration is needed.                                                                    |
| Earlier migrated target data should be replaced                      | Plan for a new migration and broader revalidation.                                                                                  |
| Only new eligible records are being added                            | Confirm Entity Points expectations for newly migrated entities.                                                                     |
| Previously recorded entities appear again on the same migration path | Preserve the rule that already recorded entities do not consume Entity Points again merely because another migration action occurs. |

This planning keeps launch timing from becoming a late-stage surprise. The goal is to define what should move, what should remain stable, and what must be revalidated.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce preparation should collect evidence that explains how the source store should become a working BigCommerce environment. The merchant should prepare catalog samples, product-option examples, pricing inputs, channel scope, customers, orders, content, redirects, app dependencies, access, exports, backups, Demo Migration samples, and launch-window expectations before treating the migration scope as ready.

A strong preparation package reduces uncertainty before Full Migration. It clarifies what should migrate, what belongs to BigCommerce-side setup, what can be handled through Add-ons, what requires Custom Service review, and what must be validated before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a BigCommerce migration?**

Start by defining how BigCommerce will operate after launch. Catalog structure, product options, pricing, channels, redirects, customers, orders, apps, and integrations determine which evidence matters most.

**Why are product samples more important than product counts?**

Counts show volume, but samples reveal meaning. Representative products show whether options, variants, modifiers, custom fields, images, price rules, category assignments, and channel assignments can be reviewed correctly in BigCommerce.

**Should pricing be prepared separately from product data?**

Yes. Base prices, sale prices, bulk pricing, price lists, customer-group pricing, coupons, and app-driven promotions may have different handling paths. Pricing evidence should be reviewed before service-path decisions are finalized.

**When should apps and integrations be reviewed?**

Apps and integrations should be reviewed before Demo Migration. App-owned data, external IDs, ERP references, loyalty records, subscriptions, reviews, and marketplace fields can affect whether Add-ons, Custom Service, target-side setup, or external integration work is needed.

**How should later migration activity be planned before launch?**

Define whether the goal is to continue from the last used configuration, continue with a new configuration, or perform a new migration. The action should match the business outcome and define what must be validated afterward.
