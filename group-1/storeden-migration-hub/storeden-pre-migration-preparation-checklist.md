# Storeden Pre-Migration Preparation Checklist

Storeden migration preparation should make the future store easier to test, configure, and launch. Because Storeden operates as a hosted cloud e-commerce platform within the TeamSystem Commerce environment, preparation should cover more than products, customers, and orders. Catalog structure, inventory behavior, marketplace selling, payment and logistics setup, storefront content, apps, APIs, ERP references, and SEO continuity all need early review.

The goal is not to document every record manually. The goal is to identify the data and workflows that carry business meaning so Demo Migration and Full Migration can be judged against real Storeden operating needs.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Preparation helps confirm whether the current store can move into Storeden through standard target structures, whether Add-ons should be considered for filtering, mapping, or data configuration, and whether Custom Service review is needed for custom logic or unsupported data.

A strong preparation file should answer four practical questions:

* Which products, customers, orders, content, and channels must remain usable after migration?
* Which target settings belong to Storeden configuration rather than migrated historical data?
* Which apps, APIs, TeamSystem integrations, marketplace connections, or external systems affect daily operations?
* Which records should be included in Demo Migration so the result can be evaluated properly?

### 1. Confirm the Target Storeden Environment <a href="#id-1-confirm-the-target-storeden-environment" id="id-1-confirm-the-target-storeden-environment"></a>

Before migration planning moves into data review, confirm the target Storeden environment and the business role it needs to support. Storeden is a hosted Target Platform, so migration quality depends on the target setup as well as the migrated records.

| Preparation item                 | What to confirm                                                                                                                              | Why it matters                                                                           |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Target account and store context | The target Storeden environment, access roles, store language, currency expectations, and operational ownership.                             | Prevents migration work from being reviewed against an incomplete or wrong target setup. |
| Commerce scope                   | Whether the store will use online storefront selling, marketplace selling, B2B workflows, logistics services, or connected business systems. | Defines which data and workflows require deeper migration planning.                      |
| Storefront structure             | Theme expectations, navigation, page structure, domain requirements, and priority content.                                                   | Helps separate data migration from theme and launch configuration.                       |
| Payment setup                    | Payment provider expectations, TS Pay relevance, and payment-status interpretation.                                                          | Historical payment labels do not configure live payment behavior by themselves.          |
| Shipping and logistics           | Shipping methods, tracking needs, fulfillment workflow, and logistics service expectations.                                                  | Historical shipping names may not recreate operational logistics behavior.               |
| App ecosystem                    | Apps, plugins, marketplace connectors, marketing tools, reporting tools, logistics tools, and other connected services.                      | App-owned data may need separate review rather than standard migration handling.         |
| TeamSystem or ERP connection     | ERP, accounting, invoicing, inventory, warehouse, or business-management dependencies.                                                       | External identifiers and workflow references can affect post-migration operations.       |

### 2. Prepare Product and Catalog Samples <a href="#id-2-prepare-product-and-catalog-samples" id="id-2-prepare-product-and-catalog-samples"></a>

Product preparation should focus on records that reveal how selling works, not only on the largest or newest products. Storeden catalog review should include simple products, complex products, variant products, attribute-heavy products, inventory-sensitive products, and marketplace-relevant products.

Include samples for:

* simple products with standard name, price, description, image, category, and stock values;
* products with variants, options, attributes, modifiers, SKU differences, or stock differences;
* products with special pricing, sale pricing, tax behavior, or shipping rules;
* products assigned to multiple categories, collections, tags, filters, or storefront paths;
* products with multiple images, image ordering requirements, or media that affects selling;
* products sold through marketplace channels;
* products connected to ERP, warehouse, inventory, accounting, or external IDs;
* products that should be excluded, filtered, renamed, remapped, or adjusted before migration.

| Product evidence                | Preparation value                                                                            |
| ------------------------------- | -------------------------------------------------------------------------------------------- |
| Product export or sample list   | Gives the migration review a clear view of product count, structure, and catalog complexity. |
| Variant and attribute examples  | Shows whether buying choices can be represented clearly in Storeden.                         |
| SKU and stock examples          | Helps confirm inventory continuity and external-system references.                           |
| Category and filter samples     | Shows how shoppers should find products after migration.                                     |
| Marketplace product examples    | Reveals channel-specific identifiers, titles, availability rules, or listing differences.    |
| Product image and media samples | Helps detect whether visual selling assets need separate handling.                           |

### 3. Prepare Category, Filter, and Storefront Discovery Evidence <a href="#id-3-prepare-category-filter-and-storefront-discovery-evidence" id="id-3-prepare-category-filter-and-storefront-discovery-evidence"></a>

Storeden catalog usability depends on how shoppers find products. Categories, filters, menus, search behavior, landing pages, product groups, and marketplace-facing structures can carry business meaning that is not visible from product count alone.

Prepare evidence for:

* main product categories and subcategories;
* product filters, attributes, tags, or grouping logic;
* menu and navigation expectations;
* landing pages or product-listing pages used for campaigns;
* high-value category URLs;
* marketplace category or channel assignment expectations;
* products that appear in more than one selling path;
* category structures that should be simplified or reorganized during migration.

If category or filter behavior affects conversion, it should be represented in Demo Migration. A target store with correct product records but weak discovery can still feel unfinished to shoppers and store managers.

### 4. Prepare Customer, Account, and B2B Context <a href="#id-4-prepare-customer-account-and-b2b-context" id="id-4-prepare-customer-account-and-b2b-context"></a>

Customer preparation should distinguish ordinary customer records from business accounts, B2B buyers, marketplace customers, newsletter subscribers, guest checkout records, and external CRM or ERP references. These records may not all carry the same meaning inside Storeden.

| Customer-related area | What to prepare                                                                                     | Review focus                                                                      |
| --------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Customer accounts     | Representative customer records, names, emails, addresses, order links, and account status.         | Confirms whether customer history remains understandable after migration.         |
| Guest buyers          | Orders tied to non-account customers or incomplete profiles.                                        | Prevents historical order review from depending on missing customer accounts.     |
| B2B context           | Company names, VAT/tax identifiers, price list relationships, customer groups, or negotiated terms. | Identifies where B2B logic exceeds ordinary customer migration.                   |
| Marketplace customers | Buyers originating from Amazon, eBay, Facebook, AliExpress, or other channels.                      | Clarifies whether marketplace origin should remain visible in historical records. |
| Marketing context     | Newsletter status, consent values, tags, segments, or external CRM references.                      | Separates customer migration from marketing-platform setup or consent handling.   |
| External IDs          | ERP, accounting, CRM, warehouse, loyalty, or support-system identifiers.                            | Helps determine whether mapping or Custom Service review is needed.               |

Password continuity should be handled cautiously. If the Source Platform stores passwords in a format that cannot be carried into Storeden safely or compatibly, customers may need to reset passwords after migration.

### 5. Prepare Order, Payment, Shipping, and Logistics Samples <a href="#id-5-prepare-order-payment-shipping-and-logistics-samples" id="id-5-prepare-order-payment-shipping-and-logistics-samples"></a>

Order preparation should include more than complete paid orders. Historical order quality depends on whether staff can understand what was purchased, who placed the order, how it was paid, how it was shipped, what status it reached, and whether any external systems depended on it.

Include examples of:

* paid, unpaid, canceled, refunded, partially refunded, fulfilled, and partially fulfilled orders;
* orders with discounts, coupons, taxes, shipping fees, or marketplace commissions;
* orders with multiple products, variant products, or bundled items;
* orders tied to guest customers, registered customers, B2B buyers, or marketplace buyers;
* orders with tracking numbers, carrier labels, logistics-service references, or fulfillment notes;
* orders with payment method labels, transaction references, TS Pay relevance, or gateway-specific data;
* orders connected to ERP, invoicing, accounting, warehouse, or customer-service systems.

Live payment and logistics behavior should be planned separately. Historical order labels can explain what happened in the previous store, but they do not automatically configure payment methods, TS Pay, shipping rates, fulfillment rules, or logistics services in Storeden.

### 6. Separate Migrated Data from Storeden Configuration <a href="#id-6-separate-migrated-data-from-storeden-configuration" id="id-6-separate-migrated-data-from-storeden-configuration"></a>

A common preparation mistake is treating historical records as if they configure the new store. Migrated products, customers, orders, and content provide store history and operating context. Storeden settings still need target-side setup and review.

| Area              | Migrated-data role                                                                                 | Storeden configuration role                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Products          | Preserves product information, variants, stock, images, and catalog relationships where supported. | Controls storefront publication, visibility, channel behavior, and merchandising choices.    |
| Orders            | Preserves order history and commercial context.                                                    | Does not configure future payment, shipping, fulfillment, or logistics behavior.             |
| Payments          | Preserves historical payment labels and references where supported.                                | Payment providers and TS Pay behavior must be set up and tested in the target environment.   |
| Shipping          | Preserves historical shipping names, fees, and tracking context where supported.                   | Live shipping methods, logistics services, rates, and carrier behavior require target setup. |
| Tax               | Preserves historical tax amounts or labels where available.                                        | Live tax rules and invoice behavior require target configuration and review.                 |
| Marketplaces      | May preserve product or order context connected to a channel.                                      | Active channel publication and synchronization need app or marketplace configuration.        |
| Apps and APIs     | May preserve selected identifiers or data fields when supported.                                   | App behavior, API connections, webhooks, and automation workflows need separate setup.       |
| Storefront design | May preserve pages, content, images, and SEO values where supported.                               | Theme layout, menus, domain behavior, and visual presentation require target-side work.      |

### 7. Prepare Content, Theme, Domain, URL, and SEO Evidence <a href="#id-7-prepare-content-theme-domain-url-and-seo-evidence" id="id-7-prepare-content-theme-domain-url-and-seo-evidence"></a>

Storeden migration planning should include storefront content and search visibility when they affect launch quality. Products and orders can migrate correctly while content, navigation, domains, redirects, or metadata remain incomplete.

Prepare:

* key CMS Pages, landing pages, and storefront content;
* Blog Posts if they exist and are within migration scope;
* page titles, SEO descriptions, slugs, and priority metadata;
* high-value product URLs and category URLs;
* redirect requirements from the old store to the new Storeden structure;
* menu, footer, banner, and navigation expectations;
* theme or visual layout requirements that should not be confused with migrated data;
* image alt text and media that affect SEO or product conversion.

SEO preparation should prioritize important URLs instead of attempting to review every page manually. Products, categories, landing pages, and revenue-driving content should receive the most attention.

### 8. Inventory Apps, APIs, Marketplace Channels, and TeamSystem Integrations <a href="#id-8-inventory-apps-apis-marketplace-channels-and-teamsystem-integrations" id="id-8-inventory-apps-apis-marketplace-channels-and-teamsystem-integrations"></a>

Storeden’s app ecosystem, developer surfaces, marketplace channels, and TeamSystem connections can strongly affect migration scope. These dependencies should be listed before Demo Migration samples are selected.

| Dependency type           | Examples to inventory                                                                                               | Migration planning question                                                                                   |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Apps and plugins          | Marketing apps, logistics apps, marketplace connectors, reporting tools, promotions, feeds, or storefront features. | Does the app store data that needs to migrate, or does it need reconfiguration after migration?               |
| Marketplace channels      | Amazon, eBay, Facebook, AliExpress, or other selling channels.                                                      | Are channel identifiers, listing data, availability rules, or order origins required after migration?         |
| API integrations          | Product sync, inventory sync, order export, fulfillment automation, or external dashboards.                         | Which identifiers and fields must remain stable for connected workflows?                                      |
| ERP and accounting        | TeamSystem ecosystem tools, invoicing, finance, warehouse, stock, or business-management systems.                   | Do records need external IDs, mapping, or workflow-specific treatment?                                        |
| Logistics and fulfillment | Shipping providers, tracking services, warehouse systems, fulfillment rules, or carrier integrations.               | Which historical values should be migrated, and which live workflows must be configured?                      |
| Marketing and CRM         | Email platforms, customer segments, consent systems, loyalty, support, or CRM records.                              | Which customer or contact fields belong in migration scope, and which remain outside Storeden data migration? |

Unsupported app-owned data, external-system identifiers, custom API behavior, bespoke sync logic, or tailored marketplace requirements should be reviewed through Custom Service when they cannot be handled through standard service capability or a Standard Add-on.

### 9. Choose Demo Migration Samples Deliberately <a href="#id-9-choose-demo-migration-samples-deliberately" id="id-9-choose-demo-migration-samples-deliberately"></a>

Demo Migration should be designed to test the records that carry risk. A small sample made only of simple records may look successful while hiding catalog, channel, order, integration, or SEO issues.

| Demo Migration sample                          | Why it should be included                                              |
| ---------------------------------------------- | ---------------------------------------------------------------------- |
| Simple product                                 | Confirms ordinary catalog fields and baseline product display.         |
| Variant or attribute-heavy product             | Tests product choices, SKUs, images, stock, and price behavior.        |
| Inventory-sensitive product                    | Checks stock meaning and external inventory references.                |
| Marketplace-relevant product                   | Reveals channel-specific identifiers, titles, or listing expectations. |
| Complex category or filter example             | Tests storefront discovery and product grouping.                       |
| Registered customer and guest buyer            | Checks customer/account readability and order relationship handling.   |
| B2B or company customer sample                 | Tests whether business-account meaning needs deeper review.            |
| Paid, refunded, canceled, and fulfilled orders | Shows whether historical order states remain understandable.           |
| Order with tracking or logistics data          | Confirms shipping and fulfillment context.                             |
| Priority CMS Page or Blog Post                 | Tests content continuity where content migration matters.              |
| Priority product or category URL               | Supports SEO and redirect planning.                                    |
| App, API, ERP, or TeamSystem-linked record     | Reveals whether external identifiers or custom handling are needed.    |

### 10. Identify Add-on and Custom Service Signals Early <a href="#id-10-identify-add-on-and-custom-service-signals-early" id="id-10-identify-add-on-and-custom-service-signals-early"></a>

Preparation should identify where standard migration is likely enough and where additional handling should be discussed before Full Migration. This prevents late-stage surprises after Demo Migration review.

Add-ons may be relevant when the requirement fits supported filtering, mapping, or data configuration needs. For example, the Data Filter Add-on can help when only selected eligible records should migrate. Advanced Data Mapping can help when supported field relationships need mapping review. Advanced Data Configure can help when supported data values should be adjusted before reaching Storeden.

Custom Service is appropriate when customization, modification, bespoke handling, unsupported app data, Custom Platform source interpretation, custom migration logic adjustment, or external-system requirements exceed standard service capability or Standard Add-on behavior. Tailored Add-ons and Custom Add-ons are also handled through Custom Service because customization is required.

| Signal found during preparation                                         | Likely implication                                                                          |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Clean supported products, customers, orders, categories, and content    | Standard Service may be enough if the customer can self-perform and validate the migration. |
| Customer wants Next-Cart-led execution within standard capability       | Managed Service may be safer when the migration does not require customization.             |
| Selected records should migrate instead of all eligible records         | Data Filter Add-on should be reviewed where supported.                                      |
| Supported fields need mapping review                                    | Advanced Data Mapping should be considered.                                                 |
| Supported values should be adjusted before migration                    | Advanced Data Configure should be considered.                                               |
| Custom Platform source or unusual source data                           | Custom Service is required for source interpretation and custom handling.                   |
| Unsupported app, marketplace, ERP, API, or external-system data         | Custom Service review is needed.                                                            |
| Custom checkout, B2B, marketplace, logistics, pricing, or sync behavior | Custom Service review is needed because custom migration logic adjustment may be required.  |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden preparation should make the migration result easier to interpret before launch. The strongest preparation focuses on the records and workflows that define how the business sells: catalog structure, inventory, variants, customers, orders, marketplace channels, payments, shipping, logistics, storefront content, SEO, apps, APIs, and TeamSystem or ERP connections.

Before starting Full Migration, prepare a focused Demo Migration sample that includes both ordinary and complex records. If the sample exposes filtering, mapping, configuration, app-owned data, marketplace identifiers, external-system references, or custom workflow requirements, review Add-ons or Custom Service before treating the migration path as straightforward.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first for a Storeden migration?**

Start with the target Storeden environment, product catalog structure, inventory behavior, customer and order samples, marketplace channels, payment and shipping expectations, and any apps or TeamSystem integrations that affect daily operations.

**Which product samples should be included before Demo Migration?**

Include simple products, variant products, attribute-heavy products, inventory-sensitive products, products with images and categories, marketplace-relevant products, and products connected to ERP, accounting, warehouse, or external-system identifiers.

**Should payment and shipping settings be prepared before migration?**

Yes. Historical payment and shipping labels can be migrated where supported, but live payment, TS Pay, shipping, logistics, tax, tracking, and fulfillment behavior need Storeden-side configuration and testing.

**Should SEO and URLs be prepared before migration?**

Yes. Priority product URLs, category URLs, metadata, redirects, domains, CMS Pages, Blog Posts, and landing pages should be prepared before launch planning. SEO-sensitive stores should not wait until after Full Migration to review URL continuity.

**When should Add-ons or Custom Service be identified?**

Add-ons should be identified when filtering, mapping, or supported data configuration is needed. Custom Service should be identified when the migration involves Custom Platform data, unsupported app or marketplace data, custom fields, external-system identifiers, or custom migration logic adjustment.
