# J2Commerce 6 Pre-Migration Preparation Checklist

J2Commerce 6 preparation should begin with a clear view of the target environment. This is not only a migration into another Joomla e-commerce component. It is a move into a native Joomla 6 commerce architecture with PHP 8.3+, modern frontend behavior, a new plugin and event model, REST API support, Bootstrap 5 and UIkit 3 storefront rendering options, and a different extension ecosystem from legacy J2Store.

A strong preparation process separates three questions before migration begins: whether the Joomla 6 environment is ready, whether the source data can be interpreted correctly, and whether the desired J2Commerce 6 result depends on configuration, plugin replacement, storefront implementation, or custom migration logic adjustment. Without that separation, a Demo Migration can look successful at the record level while still leaving unresolved questions about checkout, product variants, order history, plugin behavior, multilingual content, or integration readiness.

### 1. Confirm the Target Environment Before Preparing Data <a href="#id-1-confirm-the-target-environment-before-preparing-data" id="id-1-confirm-the-target-environment-before-preparing-data"></a>

J2Commerce 6 requires a modern Joomla foundation. Before reviewing products or orders, confirm that the target site is intended to run on Joomla 6 and meets the technical and implementation expectations for J2Commerce 6.

#### Confirm Joomla 6 and server readiness <a href="#confirm-joomla-6-and-server-readiness" id="confirm-joomla-6-and-server-readiness"></a>

J2Commerce 6 is not a drop-in continuation of the older J2Store v4 operating model. It is built for Joomla 6, PHP 8.3+, native Joomla MVC, and modern JavaScript. Preparation should therefore include the target hosting environment, database expectations, PHP version, Joomla version, template compatibility, and extension strategy.

The merchant or implementation team should confirm:

* the target Joomla 6 site is available or planned clearly;
* PHP, database, and server requirements are aligned with the J2Commerce 6 target;
* the target template is compatible with the chosen frontend framework;
* Joomla system plugins and required supporting services are reviewed;
* staging, backup, and rollback practices are available before testing migration results.

This step is especially important when the merchant is coming from J2Store v4, an older Joomla site, or a heavily customized Joomla implementation. The migration plan should not assume that source-site compatibility automatically means target-site readiness.

#### Decide whether the target uses Bootstrap 5, UIkit 3, or a custom frontend approach <a href="#decide-whether-the-target-uses-bootstrap-5-uikit-3-or-a-custom-frontend-approach" id="decide-whether-the-target-uses-bootstrap-5-uikit-3-or-a-custom-frontend-approach"></a>

J2Commerce 6 supports Bootstrap 5 and UIkit 3 frontend rendering. That choice affects how product lists, product detail pages, cart, checkout, modules, and storefront presentation should be tested after migration.

The target frontend decision should be made before validation samples are selected. A store using a Bootstrap 5 Joomla template should be validated under Bootstrap 5 rendering. A store using YOOtheme or another UIkit-based approach should be validated under UIkit 3 rendering. If the project expects a custom frontend approach, layout overrides, or deeper template work, that should be identified before migration planning is treated as straightforward.

### 2. Identify the Source Scenario <a href="#id-2-identify-the-source-scenario" id="id-2-identify-the-source-scenario"></a>

Preparation differs depending on where the merchant is migrating from. A J2Store v4 source, another Joomla commerce extension, WooCommerce, VirtueMart, HikaShop, or a Custom Platform source may all require different evidence and different expectations.

#### If the source is J2Store v4 <a href="#if-the-source-is-j2store-v4" id="if-the-source-is-j2store-v4"></a>

For J2Store v4 sources, preparation should include both data and migration traceability. The J2Commerce 6 migrator is designed to copy data into new J2Commerce tables while preserving the original J2Store tables. A dry-run and idmap-style tracking can help identify what migrates and what requires review.

Before running the migration process, gather:

* a list of active product types and variant structures;
* apps and plugins used for checkout, shipping, payment, discounts, products, subscriptions, bookings, downloads, or custom behavior;
* custom fields and non-standard data stored in the source;
* customer groups, addresses, tax profiles, shipping methods, zones, and geo-zones;
* order statuses, order comments, payment references, and fulfillment context;
* examples of products, orders, customers, and coupons that reveal source complexity.

The key preparation question is not simply whether J2Store v4 records exist. It is whether each important J2Store behavior has a J2Commerce 6 equivalent, replacement plugin, configuration path, or Custom Service requirement.

#### If the source is not J2Store v4 <a href="#if-the-source-is-not-j2store-v4" id="if-the-source-is-not-j2store-v4"></a>

For non-J2Store sources, preparation should focus on how source records will be interpreted inside J2Commerce 6 rather than on the built-in v4 migrator. This includes product structure, customer and order history, checkout data, coupons, tax/shipping/payment context, and third-party identifiers.

Custom Platform sources, unsupported application data, bespoke product logic, external database relationships, ERP-owned identifiers, or source-specific integrations should be reviewed through Custom Service before the migration approach is considered stable.

### 3. Prepare Product and Catalog Evidence <a href="#id-3-prepare-product-and-catalog-evidence" id="id-3-prepare-product-and-catalog-evidence"></a>

J2Commerce 6 catalog preparation should prove that products can become usable commercial records inside the new target structure. A product is not fully prepared just because the source export contains product names, SKUs, prices, and descriptions.

#### Review product structure <a href="#review-product-structure" id="review-product-structure"></a>

Identify the products that represent the main catalog patterns. The preparation set should include simple products, variant-heavy products, downloadable products, products with custom fields, products with multiple images, products in multiple categories, products with coupons or discounts, products affected by tax rules, and products with inventory sensitivity.

For each product pattern, confirm:

* SKU, name, description, price, sale or discount behavior;
* category and manufacturer relationships;
* variant or option structure;
* inventory behavior and stock status meaning;
* downloadable files or customer uploads if relevant;
* custom fields and custom filters;
* images, gallery order, and variant-image expectations;
* SEO aliases, metadata, and structured discovery expectations.

#### Separate variants, options, filters, and custom fields <a href="#separate-variants-options-filters-and-custom-fields" id="separate-variants-options-filters-and-custom-fields"></a>

Source platforms often use the same label for different kinds of product meaning. One source may use options for shopper selections, another may use attributes for specifications, and another may use custom fields for both internal and customer-facing data. Preparation should distinguish these meanings before migration.

| Product structure | Preparation question                                                                         | Why it matters in J2Commerce 6                                                                     |
| ----------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Variants          | Does each purchasable combination need its own price, image, SKU, stock, or option behavior? | Variant handling affects shopper selection, order line meaning, inventory, and storefront display. |
| Options           | Are options required for purchase, cosmetic selection, or pricing changes?                   | Option logic affects add-to-cart behavior and order interpretation.                                |
| Custom fields     | Are fields descriptive, operational, searchable, or integration-owned?                       | Some fields may need mapping, configuration review, or Custom Service.                             |
| Custom filters    | Which product values drive discovery or AJAX filtering?                                      | Filters affect storefront navigation and validation.                                               |
| Images            | Are images shared, ordered, variant-linked, or source-specific?                              | Product trust and variant selection depend on correct image behavior.                              |

This preparation prevents product migration from becoming a record-copy exercise. It clarifies what the migrated catalog must allow shoppers and administrators to do.

### 4. Prepare Customer, Address, and Account Data <a href="#id-4-prepare-customer-address-and-account-data" id="id-4-prepare-customer-address-and-account-data"></a>

Customer preparation should focus on commercial usefulness. J2Commerce 6 can represent customers, addresses, guest checkout, profiles, order history, and user-account relationships, but the migration plan must know which relationships matter.

#### Identify account patterns <a href="#identify-account-patterns" id="identify-account-patterns"></a>

Review source customers by type rather than by count only. Include registered customers, guest orders, customers with multiple addresses, customers with repeated orders, customers connected to coupons or discounts, and customers affected by group pricing or tax rules.

The source evidence should answer:

* whether customer accounts are linked to Joomla users or source-specific account records;
* how guest checkout records should appear after migration;
* whether billing and shipping addresses are stored separately;
* whether customer group meaning affects price, tax, access, or order interpretation;
* whether customer records contain custom fields or integration identifiers.

#### Prepare customer group and B2B context <a href="#prepare-customer-group-and-b2b-context" id="prepare-customer-group-and-b2b-context"></a>

If the store uses customer groups, wholesale pricing, purchase-order workflows, tax exemptions, or B2B rules, prepare examples before Demo Migration. These structures should not be validated only with ordinary retail customers.

Customer group behavior often affects more than one article field. It may influence product price, discount eligibility, tax behavior, payment method access, and reporting expectations. If the source rules are app-owned or custom-coded, the project may need Add-on review or Custom Service rather than ordinary data mapping.

### 5. Prepare Order, Coupon, Tax, Shipping, and Payment Evidence <a href="#id-5-prepare-order-coupon-tax-shipping-and-payment-evidence" id="id-5-prepare-order-coupon-tax-shipping-and-payment-evidence"></a>

Order preparation should make historical order data interpretable after migration. A useful migrated order is not only an order number and total. It should preserve enough context for customer service, accounting reference, fulfillment review, and operational continuity.

#### Select representative orders <a href="#select-representative-orders" id="select-representative-orders"></a>

Prepare order samples that include:

* simple orders and multi-product orders;
* variant products and downloadable products;
* guest checkout and registered-customer orders;
* coupons, vouchers, or discount examples;
* tax profiles, geo-zone-sensitive orders, and different customer locations;
* shipping methods, free shipping, carrier methods, or table-rate behavior;
* payment methods and payment status differences;
* refunds, cancellations, failed orders, or custom statuses if relevant;
* customer comments, administrator comments, and order history notes.

#### Separate migrated data from target configuration <a href="#separate-migrated-data-from-target-configuration" id="separate-migrated-data-from-target-configuration"></a>

Tax, shipping, payment, currency, checkout, and email behavior often require target configuration even when related historical data is migrated. The preparation file should list what is expected to be migrated, what must be configured in J2Commerce 6, and what requires replacement plugin selection or custom review.

| Area                  | Prepare before migration                                                         | Review after migration                                                                         |
| --------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Taxes                 | Tax profiles, geo-zones, customer tax context, product tax classes               | Whether totals and tax meaning remain understandable in orders and checkout configuration.     |
| Shipping              | Shipping methods, zones, carrier rules, free-shipping logic, table-rate examples | Whether available target shipping plugins and configuration can support the intended behavior. |
| Payments              | Payment gateways, payment references, payment states, offline methods            | Whether legacy plugins need replacement and order payment context remains useful.              |
| Coupons and discounts | Coupon codes, discount rules, eligibility, expiration, customer restrictions     | Whether discount meaning is preserved or needs configuration review.                           |
| Currency              | Source currencies, exchange-rate assumptions, display behavior                   | Whether multi-currency setup and live-rate expectations are configured correctly.              |

### 6. Prepare Plugin, App, API, and Integration Inventory <a href="#id-6-prepare-plugin-app-api-and-integration-inventory" id="id-6-prepare-plugin-app-api-and-integration-inventory"></a>

J2Commerce 6 has a modern extension model and a broader integration surface, but preparation must identify which source behaviors depend on old plugins, apps, custom code, or external systems.

#### Inventory source extensions and target replacements <a href="#inventory-source-extensions-and-target-replacements" id="inventory-source-extensions-and-target-replacements"></a>

List every source extension or integration that affects product data, checkout, shipping, payment, taxes, customer groups, order handling, reporting, marketing, subscriptions, marketplaces, uploads, downloads, or fulfillment.

For each item, identify:

* whether it creates records that need migration;
* whether it changes checkout or order behavior;
* whether it has a J2Commerce 6 equivalent or replacement;
* whether its data is visible in standard exports;
* whether it requires configuration, plugin installation, or Custom Service review.

Old J2Store payment and shipping plugins should not be assumed compatible with J2Commerce 6. Replacement planning belongs before migration validation, not after a failed checkout test.

#### Clarify API and external-system expectations <a href="#clarify-api-and-external-system-expectations" id="clarify-api-and-external-system-expectations"></a>

J2Commerce 6 includes REST API capabilities and modern integration hooks. That does not mean every source integration migrates automatically. ERP, warehouse, BI, marketplace, marketing, AI/MCP, reporting, and custom application flows should be listed as operational requirements.

If the source store uses external identifiers or integration-owned records, those identifiers should be prepared as part of the source evidence. Missing identifiers can make migrated records appear correct while breaking downstream workflows.

### 7. Prepare Storefront, Search, SEO, and Content Context <a href="#id-7-prepare-storefront-search-seo-and-content-context" id="id-7-prepare-storefront-search-seo-and-content-context"></a>

J2Commerce 6 storefront preparation should cover more than product records. The future store experience may depend on menus, modules, templates, aliases, metadata, product structured data, Smart Search indexing, product filters, category routes, checkout accessibility, and frontend framework choice.

#### Identify high-value storefront paths <a href="#identify-high-value-storefront-paths" id="identify-high-value-storefront-paths"></a>

Prepare a list of important URLs and entry paths, including:

* top product pages;
* top category pages;
* landing pages that drive paid or organic traffic;
* checkout and cart paths;
* customer account paths;
* downloadable product pages;
* content pages linked to products;
* pages affected by search, filters, or structured data.

This list helps the Demo Migration and post-migration validation test customer experience, rather than only administration records.

#### Prepare module and template dependencies <a href="#prepare-module-and-template-dependencies" id="prepare-module-and-template-dependencies"></a>

If the source store uses mini-cart modules, product listing modules, related-products modules, currency modules, menu modules, layout overrides, or custom template code, document those dependencies before migration. Some storefront work may belong to Joomla implementation rather than data migration. Other dependencies may need Custom Service if source data must be transformed to support the target layout.

### 8. Build Demo Migration Samples Deliberately <a href="#id-8-build-demo-migration-samples-deliberately" id="id-8-build-demo-migration-samples-deliberately"></a>

Demo Migration should test the records that can expose the highest risk. It should not rely solely on the newest, simplest, or cleanest products and orders.

#### Recommended sample set <a href="#recommended-sample-set" id="recommended-sample-set"></a>

| Sample type              | Include examples that reveal                                                                  | What the Demo Migration should answer                                        |
| ------------------------ | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Products                 | Simple products, variants, downloadable products, multi-image products, custom-field products | Are products sellable, understandable, searchable, and manageable?           |
| Categories and discovery | Main categories, nested categories, manufacturer pages, filters, aliases, metadata            | Can shoppers find products in the intended storefront structure?             |
| Customers                | Registered customers, guest customers, multiple-address customers, group-based customers      | Are customer identities and account relationships meaningful?                |
| Orders                   | Multi-item orders, variant orders, tax/shipping/payment examples, refunds, status changes     | Is history useful for support, accounting reference, and operational review? |
| Plugins and integrations | Payment, shipping, tax, reporting, API, and external-system examples                          | Do plugin replacements or custom integrations need further review?           |
| Storefront               | Bootstrap/UIkit pages, cart, checkout, modules, search, structured data                       | Does the customer-facing experience match target expectations?               |

### 9. Escalate Before Execution When the Source Is Not Standard <a href="#id-9-escalate-before-execution-when-the-source-is-not-standard" id="id-9-escalate-before-execution-when-the-source-is-not-standard"></a>

Preparation should determine whether the project can remain within standard service capability or requires deeper handling before execution.

#### Escalation signals <a href="#escalation-signals" id="escalation-signals"></a>

Review Custom Service before proceeding when the source includes:

* Custom Platform data;
* unsupported extension data;
* old plugin data without a direct J2Commerce 6 equivalent;
* app-owned or third-party records;
* custom product, customer, checkout, or order fields;
* source-specific product logic;
* external identifiers required by ERP, fulfillment, BI, marketplace, or reporting systems;
* multilingual restructuring beyond ordinary language mapping;
* storefront behavior that depends on custom code;
* Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

Advanced Data Mapping or Advanced Data Configure may help when mapping or configuration needs fit the standard Add-on capability. Broader transformation, unsupported data handling, custom logic, or Custom Platform interpretation belongs under Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Commerce 6 preparation should demonstrate that the target Joomla 6 store is ready, that the source data is understandable, and that the expected result can be validated beyond basic record presence. The strongest preparation work identifies product and variant patterns, customer and order meaning, plugin replacement needs, tax/shipping/payment configuration, storefront framework choices, API expectations, and Demo Migration samples before execution begins.

For merchants moving from J2Store v4, preparation should also account for dry-run interpretation, idmap traceability, and the possibility that legacy plugin behavior may need to be replaced rather than transferred directly. For merchants moving from other Source Platforms, the main question is whether source records, custom fields, external identifiers, and operational rules can be translated into J2Commerce 6 without losing business meaning.

Before starting a Full Migration to J2Commerce 6, use Demo Migration samples to test catalog structure, checkout behavior, customer and order history, plugin replacement, storefront rendering, and configuration-sensitive data. If important source behavior depends on Custom Platform data, unsupported extensions, old plugin logic, third-party identifiers, or bespoke transformations, review the migration path through Live Chat so the right Standard Service, Managed Service, Custom Service, and Add-on boundaries are clear before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to J2Commerce 6?**

Confirm the target Joomla 6 environment first. J2Commerce 6 depends on a modern Joomla 6 foundation, PHP 8.3+, target template choices, and the correct frontend rendering approach. Data preparation should begin after the target environment and version direction are clear.

**Should J2Store v4 merchants prepare differently from other merchants?**

Yes. J2Store v4 merchants should prepare dry-run evidence, idmap interpretation, plugin replacement notes, product and variant samples, customer and order examples, and any custom fields or app-owned behavior. The migration should confirm what the v4 migrator can handle and what needs separate review.

**Do old J2Store payment and shipping plugins need preparation?**

Yes. Existing J2Store payment and shipping plugins should not be assumed to work directly in J2Commerce 6. Prepare a list of legacy plugins and identify whether each has a J2Commerce 6 replacement, a configuration path, or a Custom Service requirement.

**What product samples should be used for Demo Migration?**

Use products that reveal real catalog structure: simple products, variant products, downloadable products, products with multiple images, products with custom fields, products affected by discounts or tax rules, and products that depend on important inventory or storefront behavior.

**When should Custom Service be reviewed before J2Commerce 6 migration?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported extension data, custom fields, old plugin data without a target equivalent, external identifiers, source-specific product logic, multilingual restructuring, or any transformation that requires custom migration logic adjustment beyond standard service capability.
