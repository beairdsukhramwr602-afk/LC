# EShop Pre-Migration Preparation Checklist

Preparing for migration to EShop by Ossolution Team means preparing both the commerce data and the Joomla environment that will receive it. EShop is not only a product-and-order destination. It is a Joomla MVC-based e-commerce extension where catalog records, customer groups, checkout fields, tax rules, shipping methods, payment plugins, modules, templates, multilingual content, and custom development can all affect the final store.

The purpose of preparation is to make the Demo Migration meaningful. A weak preparation process collects record counts and waits to see what happens. A stronger process identifies which records prove the store’s real operating model: products with options, products with attributes, products assigned to customer groups, orders with coupons and vouchers, customers with different address patterns, multilingual records, quote-mode examples, downloadable products, and any data shaped by custom fields, plugins, or Joomla overrides.

Use this checklist to clarify what should be reviewed before migration, what evidence should be gathered, and which items may require Add-on review or Custom Service before execution.

### Preparation Priorities Before Migrating to EShop <a href="#preparation-priorities-before-migrating-to-eshop" id="preparation-priorities-before-migrating-to-eshop"></a>

A strong EShop migration starts by separating four layers of readiness: target environment readiness, source data readiness, configuration readiness, and implementation readiness. These layers should be reviewed together because EShop store behavior depends on how migrated records interact with Joomla configuration and EShop settings.

| Preparation layer                | What to clarify                                                                                                                                | Why it matters before migration                                                                                      |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Joomla and EShop environment     | Joomla version, EShop installation, extension compatibility, menus, modules, templates, and implementation responsibilities.                   | The migrated store must operate inside a working Joomla and EShop environment, not only appear as imported records.  |
| Catalog data                     | Products, categories, manufacturers, options, attributes, labels, downloads, reviews, product custom fields, pricing, stock, and images.       | Catalog structure determines whether products remain understandable, searchable, comparable, and buyable.            |
| Customer and sales data          | Customers, customer groups, addresses, orders, coupons, discounts, vouchers, checkout fields, quotes, order statuses, and comments.            | Historical records should remain useful for support, account review, operational reference, and customer continuity. |
| Configuration-sensitive behavior | Tax classes, tax rates, geo-zones, currencies, stock statuses, shipping methods, payment plugins, catalog mode, cart mode, and quote behavior. | Some behavior must be configured or validated in EShop rather than assumed from migrated records.                    |
| Joomla implementation layer      | Menus, aliases, metadata, modules, themes, layout overrides, multilingual records, and custom plugins.                                         | Storefront continuity depends on site implementation as well as migration output.                                    |

This preparation should not become an attempt to solve every implementation issue before migration. The goal is to identify what the migration must preserve, what the target store must be configured to support, and which unclear areas should be tested during Demo Migration.

### 1. Confirm the Target Joomla and EShop Environment <a href="#id-1-confirm-the-target-joomla-and-eshop-environment" id="id-1-confirm-the-target-joomla-and-eshop-environment"></a>

Before preparing data samples, confirm that the target Joomla site and EShop installation are ready enough to receive and review migrated data. The target environment should not be treated as an afterthought because EShop behavior is shaped by Joomla menus, modules, templates, themes, extensions, and configuration.

At minimum, the preparation process should confirm which Joomla version will be used, which EShop version is installed, which Joomla template or theme is planned, whether modules are already assigned, and whether any layout overrides or custom plugins are expected. If the target site is still being designed, the migration plan should still identify the expected storefront structure so Demo Migration results can be judged correctly.

#### Environment items to confirm <a href="#environment-items-to-confirm" id="environment-items-to-confirm"></a>

* Target Joomla version and EShop installation state.
* Administrative access needed to review migrated EShop data.
* Planned store mode, such as ordinary shopping behavior, Catalog Mode, quote-oriented selling, or a mixed model.
* Joomla menu structure for product, category, manufacturer, cart, checkout, customer, quote, and search areas.
* EShop theme, Joomla template, module placement, and any layout override expectations.
* Known custom plugins, payment plugins, shipping plugins, or third-party services that may affect store behavior.

If the target environment is incomplete, the migration can still be planned, but the team should be clear about which items will be validated immediately after Demo Migration and which items depend on later Joomla implementation work.

### 2. Inventory the Source Catalog Structure <a href="#id-2-inventory-the-source-catalog-structure" id="id-2-inventory-the-source-catalog-structure"></a>

Catalog preparation should go deeper than counting products. EShop has separate catalog concepts that can carry different meanings: products, categories, manufacturers, options, attributes, attribute groups, labels, downloads, reviews, tags, images, attachments, related products, discounts, specials, product custom fields, and product tabs.

The source catalog should be reviewed for the structures that matter most to shopper choice and merchant management. A product that looks simple in an export may depend on option-level pricing, downloadable files, customer group visibility, special prices, stock checkout settings, minimum and maximum quantities, quote mode, custom product fields, or source-specific product page layout.

#### Product evidence to gather <a href="#product-evidence-to-gather" id="product-evidence-to-gather"></a>

Prepare examples for each major product pattern in the source store:

| Product sample type                       | Why it should be included in preparation                                                                                     |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Simple product                            | Establishes the baseline for title, SKU, price, description, image, category, stock, and published state.                    |
| Option-heavy product                      | Tests shopper-facing selections such as size, color, format, package, add-ons, required choices, and price-changing options. |
| Attribute-heavy product                   | Tests specification and comparison information that should not be confused with selectable options.                          |
| Discount or special-price product         | Shows whether promotional pricing and customer group price assumptions need mapping or configuration review.                 |
| Product assigned to customer groups       | Reveals whether group-specific price, tax, or visibility behavior needs special attention.                                   |
| Downloadable product                      | Tests whether files, download relationships, and product delivery expectations require preparation beyond ordinary products. |
| Product with shipping rules               | Shows whether weight, dimensions, shipping requirement, shipping cost, or stock behavior matters.                            |
| Quote-mode or call-for-price product      | Clarifies whether the product is meant to be purchased directly, quoted, or displayed without ordinary cart behavior.        |
| Product with custom fields or attachments | Identifies data that may require Advanced Data Mapping, Advanced Data Configure, or Custom Service review.                   |

This evidence should be gathered before Demo Migration so the sample is not random. Random samples often miss the records that reveal migration complexity.

### 3. Separate Options from Attributes Before Mapping <a href="#id-3-separate-options-from-attributes-before-mapping" id="id-3-separate-options-from-attributes-before-mapping"></a>

One of the most important preparation tasks for EShop is to separate shopper-facing product options from product attributes. Options represent choices a shopper may need to make before adding a product to the cart. Attributes represent product information or specifications, often useful for comparison and detail display.

Many Source Platforms blur this distinction. Some call everything an attribute. Some use variants, modifiers, configurable products, custom fields, product add-ons, or app-created option sets. If the source structure is not clarified before migration, the Demo Migration may show products that technically exist but do not preserve buying meaning.

#### Questions to answer before Demo Migration <a href="#questions-to-answer-before-demo-migration" id="questions-to-answer-before-demo-migration"></a>

* Which source fields represent choices shoppers must select?
* Which source fields represent product specifications or comparison information?
* Do any choices affect price, stock, SKU, image, weight, or order line meaning?
* Are any choices required before add-to-cart?
* Are any product details stored in custom fields, app fields, extension tables, or free-form descriptions?
* Do historical orders record the selected options clearly enough for customer service review?

When options or attributes are source-specific, unsupported, or tied to custom logic, they should be flagged before execution. Advanced Data Mapping or Advanced Data Configure may help when the needed handling fits standard Add-on capability. Custom Service should be reviewed when the source structure requires bespoke interpretation or custom migration logic adjustment.

### 4. Prepare Categories, Manufacturers, Discovery, and Storefront Paths <a href="#id-4-prepare-categories-manufacturers-discovery-and-storefront-paths" id="id-4-prepare-categories-manufacturers-discovery-and-storefront-paths"></a>

EShop catalog discovery can involve categories, manufacturers, aliases, metadata, page headings, modules, search behavior, filters, and Joomla menus. Preparing this layer helps prevent a migrated catalog from becoming hard to navigate even if the product records are present.

The source store should be reviewed for category depth, duplicate categories, manufacturer relationships, product placement, category descriptions, high-value SEO paths, internal links, and landing pages. If the future EShop store will use product filter modules, product modules, category modules, manufacturer modules, search modules, or cart modules, the relevant data should be prepared with those display expectations in mind.

#### Discovery items to document <a href="#discovery-items-to-document" id="discovery-items-to-document"></a>

* Parent and child category structure.
* Category names, aliases, metadata, descriptions, and images where relevant.
* Manufacturer names and manufacturer-page expectations.
* Products assigned to multiple categories or manufacturers.
* Product tags, labels, reviews, and search/filter expectations.
* High-value product, category, manufacturer, and content URLs.
* Joomla menus or modules that will expose catalog areas after migration.

This preparation belongs before migration because discovery problems are often mistaken for migration errors after launch. Some issues are data issues, some are configuration issues, and some are Joomla implementation issues.

### 5. Prepare Customer, Customer Group, and Checkout Field Evidence <a href="#id-5-prepare-customer-customer-group-and-checkout-field-evidence" id="id-5-prepare-customer-customer-group-and-checkout-field-evidence"></a>

Customer preparation should identify more than names and email addresses. EShop customer records may include account information, billing and shipping addresses, customer groups, and checkout field values. Customer groups can affect discount, special price, tax, or selling behavior, so group meaning should be documented before migration.

Checkout fields also deserve early review. Billing and delivery fields may include required fields, optional fields, source-specific fields, or custom fields added to support business workflows. These fields can affect order readability, customer service, B2B review, delivery handling, or internal reporting.

#### Customer and checkout evidence to gather <a href="#customer-and-checkout-evidence-to-gather" id="customer-and-checkout-evidence-to-gather"></a>

* Customer groups and the business purpose of each group.
* Customers assigned to different groups.
* Customers with multiple addresses.
* Customers with incomplete, unusual, or legacy address formatting.
* Checkout fields used for billing and delivery.
* Custom checkout fields created by extensions, manual workflows, or business-specific requirements.
* Customer records connected to important historical orders.

If customer groups or checkout fields carry business logic rather than simple labels, they should be included in Demo Migration samples. Group and field names alone are not enough; the preparation should clarify what those groups and fields are expected to mean after migration.

### 6. Prepare Order Samples That Prove Commercial History <a href="#id-6-prepare-order-samples-that-prove-commercial-history" id="id-6-prepare-order-samples-that-prove-commercial-history"></a>

Order preparation should focus on operational usefulness. EShop order records can include product line items, product model, quantity, unit price, total price, selected options, subtotal, tax, shipping, coupon, voucher, final total, payment method, shipping method, comments, order status, customer details, payment details, and shipping details.

A meaningful Demo Migration should include orders that reveal these layers. It should not include only recent ordinary orders if the store has refunds, coupons, vouchers, quote behavior, customer group pricing, tax complexity, unusual shipping methods, failed or cancelled orders, or custom statuses.

#### Order samples to prepare <a href="#order-samples-to-prepare" id="order-samples-to-prepare"></a>

| Order sample                        | What it helps prove                                                                          |
| ----------------------------------- | -------------------------------------------------------------------------------------------- |
| Ordinary completed order            | Baseline order identity, customer link, line items, totals, and status meaning.              |
| Order with product options          | Whether selected shopper choices remain readable in historical order lines.                  |
| Order with coupon or discount       | Whether promotional context and totals remain interpretable.                                 |
| Order with voucher                  | Whether voucher-related value is preserved or needs review.                                  |
| Order with tax and shipping         | Whether tax, shipping cost, shipping method, and totals remain useful.                       |
| Order with different payment method | Whether payment method context is readable for historical reference.                         |
| Order with custom or unusual status | Whether source status meaning needs mapping, cleanup, or Custom Service review.              |
| Order with customer comment         | Whether operational notes and customer-entered information remain available where supported. |
| Quote-related order or request      | Whether quote-mode selling has implications for migration and validation.                    |

Historical order validation should not be confused with future checkout configuration. Old orders need to remain readable and commercially meaningful. Live checkout behavior still depends on EShop configuration, payment plugins, shipping plugins, tax settings, and target-site testing.

### 7. Document Tax, Geo-Zone, Currency, Shipping, and Payment Settings <a href="#id-7-document-tax-geo-zone-currency-shipping-and-payment-settings" id="id-7-document-tax-geo-zone-currency-shipping-and-payment-settings"></a>

Tax, shipping, payment, and currency behavior is configuration-sensitive in EShop. These areas should be documented before migration so the team can separate historical order context from target checkout setup.

Prepare evidence for countries, zones, geo-zones, tax rates, tax classes, currencies, stock statuses, order statuses, length units, weight units, and any special regional or customer group logic. Shipping methods should be reviewed by type, such as flat, price-based, item-based, free, weight-based, quantity-based, postcode-based, carrier-based, or custom methods. Payment methods should be reviewed by gateway, offline method, payment reference behavior, and expected order status behavior.

#### Configuration checklist <a href="#configuration-checklist" id="configuration-checklist"></a>

* Countries, zones, and geo-zones used by the source store.
* Tax classes and tax rates assigned to products or customer groups.
* Currencies and exchange-rate expectations.
* Stock statuses, out-of-stock status, stock checkout behavior, and threshold behavior.
* Order statuses and the business meaning of each status.
* Shipping methods, carrier integrations, regional rules, free shipping conditions, weight rules, quantity rules, postcode rules, and custom logic.
* Payment gateways, offline payment methods, payment references, gateway statuses, and refund expectations.

These settings may not all be migrated as direct records. Some may need to be configured in EShop, tested after migration, or reviewed through Custom Service if the source behavior depends on custom rules or third-party systems.

### 8. Prepare Multilingual and Multicurrency Requirements <a href="#id-8-prepare-multilingual-and-multicurrency-requirements" id="id-8-prepare-multilingual-and-multicurrency-requirements"></a>

EShop multilingual behavior should be prepared carefully because the way translations are represented in the target may differ from the Source Platform. EShop can support multilingual content across store records, but the migration plan must identify which records require translation and how source translations are structured.

Preparation should include translated products, categories, manufacturers, options, attributes, attribute groups, labels, downloads, messages, custom fields, lengths, and weights where relevant. If the source store uses separate records per language, language-specific URLs, third-party translation extensions, or custom translation tables, those structures should be identified before migration.

Multicurrency expectations should also be reviewed. The source store may store historical order currency, display prices in multiple currencies, or depend on exchange-rate logic. The preparation should clarify whether currency data is needed for historical reference, live storefront display, or both.

### 9. Inventory Joomla Modules, Themes, Layout Overrides, and Custom Development <a href="#id-9-inventory-joomla-modules-themes-layout-overrides-and-custom-development" id="id-9-inventory-joomla-modules-themes-layout-overrides-and-custom-development"></a>

Because EShop operates inside Joomla, the source and target implementation layers should be reviewed before migration. This does not mean Next-Cart migrates or rebuilds every Joomla layout element by default. It means the migration plan should identify which site-level elements influence the expected store result.

Relevant items include EShop themes, Joomla templates, product/category/manufacturer/cart/search modules, menu assignments, template overrides, layout overrides, custom plugins, payment plugins, shipping plugins, user plugins, membership integrations, search plugins, notify plugins, and newsletter integrations.

#### Customization signals to flag early <a href="#customization-signals-to-flag-early" id="customization-signals-to-flag-early"></a>

* Source data stored by custom Joomla extensions or third-party plugins.
* Product custom fields that are not standard source fields.
* Checkout fields that affect order handling or internal workflows.
* Custom payment, shipping, quote, notify, user, membership, or search plugins.
* Layout overrides that change how product, category, cart, checkout, or customer pages display data.
* External identifiers from ERP, CRM, fulfillment, marketplace, subscription, or accounting systems.
* Data relationships that are not visible in ordinary source exports.

When these items affect the expected migration result, they should be reviewed before execution. Some may be implementation tasks outside migration. Others may require Advanced Data Mapping, Advanced Data Configure, Tailored Add-ons, Custom Add-ons, or Custom Service.

### 10. Choose Demo Migration Samples Deliberately <a href="#id-10-choose-demo-migration-samples-deliberately" id="id-10-choose-demo-migration-samples-deliberately"></a>

Demo Migration should be used to test meaning, not only record movement. For EShop, that means selecting samples that expose catalog complexity, sales-history meaning, configuration-sensitive behavior, multilingual content, and Joomla display dependencies.

A strong sample set should include ordinary records and edge cases. Ordinary records confirm the baseline. Edge cases reveal whether the migration plan understands the store’s real operating structure.

| Sample group         | Include examples that test                                                                                                                                                                                                               |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products             | Simple products, option-heavy products, attribute-heavy products, discounted products, downloadable products, quote-mode products, products with shipping rules, products with customer group behavior, and products with custom fields. |
| Catalog organization | Parent/child categories, manufacturers, labels, reviews, tags, multiple category assignments, category aliases, metadata, and search/filter expectations.                                                                                |
| Customers            | Customers from different customer groups, customers with multiple addresses, customers with incomplete addresses, and customers connected to important orders.                                                                           |
| Orders               | Orders with options, coupons, discounts, vouchers, tax, shipping, multiple payment methods, custom statuses, comments, billing details, and shipping details.                                                                            |
| Configuration        | Tax classes, geo-zones, currencies, stock statuses, order statuses, shipping methods, payment methods, and checkout field behavior.                                                                                                      |
| Joomla/site context  | Menus, aliases, modules, themes, layout overrides, multilingual records, and high-value routes that affect storefront review.                                                                                                            |

After Demo Migration, review each sample against its intended purpose. If a sample looks incomplete, determine whether the issue is source-data quality, target configuration, unsupported data, missing Add-on review, or a Custom Service requirement.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

Preparation does not need to be chaotic. The work should move from identity and environment, to catalog structure, to sales history, to configuration, to custom behavior, and finally to Demo Migration sample selection.

1. Confirm the target Joomla and EShop environment.
2. Inventory products, categories, manufacturers, options, attributes, downloads, labels, reviews, and product custom fields.
3. Separate shopper-facing options from product attributes and specifications.
4. Document customer groups, customers, addresses, and checkout fields.
5. Select order samples that show products, options, totals, discounts, coupons, vouchers, tax, shipping, payment methods, statuses, comments, and customer context.
6. Document taxes, geo-zones, currencies, stock statuses, order statuses, shipping plugins, and payment plugins.
7. Review multilingual, multicurrency, module, theme, layout override, and custom development requirements.
8. Identify which items are ordinary migration expectations, which require target configuration, which may use Add-ons, and which should be reviewed through Custom Service.
9. Run Demo Migration with representative samples.
10. Use Demo Migration results to decide whether the migration path is ready for Full Migration or needs cleanup, configuration review, Add-on review, or Custom Service review.

This sequence gives the merchant and migration team a practical way to judge the source store before execution instead of discovering preventable issues during launch preparation.

### What to Escalate Before Execution <a href="#what-to-escalate-before-execution" id="what-to-escalate-before-execution"></a>

Some findings should be escalated before Demo Migration or Full Migration because they may change the service approach, sample design, or expected result.

Escalate early when the source store includes Custom Platform data, unsupported extension data, product custom fields that need bespoke interpretation, checkout fields that need transformation, custom product option behavior, custom customer group pricing, unusual tax or geo-zone logic, custom order statuses, plugin-owned payment or shipping data, multilingual restructuring, ERP or CRM identifiers, quote workflows, membership integrations, marketplace connectors, or custom Joomla development that affects store output.

Escalation does not automatically mean the project is too complex. It means the migration should not be planned as an ordinary record movement. The earlier those requirements are identified, the easier it is to decide whether Standard Service, Managed Service, Add-ons, or Custom Service is the right fit.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for EShop migration means proving that the future Joomla store has enough structure to receive meaningful commerce data. Products, categories, manufacturers, options, attributes, customers, customer groups, orders, coupons, vouchers, taxes, shipping, payments, multilingual records, modules, themes, and custom fields should be reviewed before migration because they shape what the result must preserve.

The best preparation work does not try to make every source store perfect. It identifies the records that matter, the settings that need configuration, the samples that should be tested, and the custom behaviors that require early review. That makes Demo Migration more useful and reduces the risk of discovering structural gaps only after Full Migration.

Before starting migration to EShop, prepare representative product, customer, order, configuration, multilingual, and Joomla implementation samples, then use Demo Migration and Live Chat to confirm whether the selected migration path can meet the expected result through Standard Service, Managed Service, purchased Add-ons, or Custom Service.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to EShop?**

Start with the target Joomla and EShop environment, then review the source catalog. EShop migration depends heavily on how products, categories, options, attributes, customer groups, checkout fields, taxes, shipping, payments, modules, and themes will work inside the target Joomla site.

**Why are product options and attributes important before EShop migration?**

Options and attributes serve different purposes in EShop. Options are shopper-facing choices, while attributes describe product information or comparison details. If the source store mixes these concepts, they should be clarified before Demo Migration so products remain understandable and buyable.

**What order should the samples be selected for Demo Migration?**

Choose orders that prove commercial meaning: orders with product options, coupons, discounts, vouchers, tax, shipping, different payment methods, custom statuses, customer comments, billing details, shipping details, and customer group context. Ordinary orders alone may not reveal the important migration issues.

**Should taxes, shipping methods, and payment gateways be prepared as data or configuration?**

Both historical context and target configuration should be reviewed. Historical orders should remain readable with their tax, shipping, and payment information, while live checkout behavior must be configured and tested inside EShop using the correct plugins and settings.

**When should Custom Service be reviewed before EShop migration?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported extension data, custom product or checkout fields, plugin-owned data, multilingual restructuring, custom order structures, external identifiers, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment beyond standard service capability.
