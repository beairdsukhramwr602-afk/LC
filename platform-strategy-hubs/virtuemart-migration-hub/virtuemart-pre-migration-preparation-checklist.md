# VirtueMart Pre-Migration Preparation Checklist

VirtueMart migration preparation should begin with the structure that will make the future Joomla store usable, not only with a count of products, customers, and orders. VirtueMart is a Joomla e-commerce extension with its own catalog, shopper, pricing, order, payment, shipment, calculation, and configuration layers. A reliable migration plan needs evidence for how those layers work in the Source Platform and how they should operate after migration.

VirtueMart 4.6.4 is the stable release baseline for migration planning. Older operational VirtueMart installations may still be used when their Joomla environment and extension stack remain functional, but older behavior should be confirmed before assuming it matches the current stable release. Joomla 6 or beta-version expectations should be verified separately before they influence migration planning.

### Why Preparation Matters Before Moving to VirtueMart <a href="#why-preparation-matters-before-moving-to-virtuemart" id="why-preparation-matters-before-moving-to-virtuemart"></a>

VirtueMart can support detailed Joomla-based commerce, but that flexibility makes preparation important. Products may depend on parent/child relationships, custom fields, shopper groups, pricing rules, downloadable files, media records, manufacturer data, categories, payment methods, shipment methods, tax rules, discounts, currencies, languages, order statuses, templates, modules, and plugin behavior.

A migration plan that only prepares exported records is too light for many VirtueMart projects. The merchant should know which source structures must become VirtueMart catalog data, which expectations must be configured in VirtueMart or Joomla, and which requirements need Add-on review or Custom Service before the migration process begins.

### 1. Confirm the VirtueMart and Joomla Target Environment <a href="#id-1-confirm-the-virtuemart-and-joomla-target-environment" id="id-1-confirm-the-virtuemart-and-joomla-target-environment"></a>

The first preparation step is to confirm the intended Joomla and VirtueMart versions. VirtueMart operates inside Joomla, so the target environment affects templates, modules, plugin compatibility, routing, language behavior, access control, and extension support.

For a new VirtueMart target store, the merchant should confirm the Joomla version, VirtueMart version, PHP and database environment, template framework, required modules, payment plugins, shipment plugins, language setup, currency setup, and required third-party extensions. If the project targets an older operational VirtueMart installation, the merchant should identify the exact version and avoid assuming current stable release behavior.

| Preparation item                | What to confirm                                                                              | Why it matters                                                                                                            |
| ------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Joomla version                  | The target Joomla version and supported hosting environment                                  | VirtueMart behavior depends on the Joomla site foundation, installed extensions, template layer, and compatibility stack. |
| VirtueMart version              | The intended VirtueMart version for the migration                                            | Stable release behavior, older-version behavior, and beta-version behavior should not be treated as interchangeable.      |
| Template and module layer       | The Joomla template, menu structure, module positions, and storefront layout requirements    | Migrated data may be correct but still fail as a storefront if the Joomla presentation layer is not prepared.             |
| Payment and shipment plugins    | The target payment and shipment methods and their configuration responsibilities             | Payment and shipment behavior usually depends on configuration and plugins, not only migrated records.                    |
| Multilingual and currency setup | Languages, translations, currencies, exchange-rate expectations, and country/region behavior | Language and currency behavior must be planned before validation can prove storefront readiness.                          |

### 2. Audit Product and Catalog Structure <a href="#id-2-audit-product-and-catalog-structure" id="id-2-audit-product-and-catalog-structure"></a>

VirtueMart catalog preparation should go beyond product names, descriptions, SKUs, and prices. The merchant should identify how source products are organized, how shoppers choose product variations, how stock is tracked, and how products are displayed in categories or menus.

#### Product types and catalog relationships <a href="#product-types-and-catalog-relationships" id="product-types-and-catalog-relationships"></a>

Products should be grouped into meaningful samples before Demo Migration. A strong sample set usually includes simple products, products with child products or variants, products with custom fields, products with multiple media files, products assigned to several categories, products with manufacturer data, products with tax or discount behavior, downloadable products, and products that represent the store’s highest-value revenue lines.

Parent/child product structures deserve particular attention. If the Source Platform treats variants as option combinations, standalone SKUs, child products, configurable products, or custom-field-driven selections, the migration plan should determine how those structures should appear in VirtueMart.

#### Categories, manufacturers, and discovery structure <a href="#categories-manufacturers-and-discovery-structure" id="categories-manufacturers-and-discovery-structure"></a>

Category preparation should include category depth, product placement, duplicate categories, orphaned products, manufacturer relationships, menu expectations, and SEO-sensitive category routes. VirtueMart categories can support storefront discovery, but Joomla menus and templates may also shape how categories appear to shoppers.

The merchant should identify the categories that matter most for organic traffic, paid campaign entry points, internal navigation, and customer buying behavior. These categories should be included in Demo Migration validation rather than relying only on random migrated records.

#### Media, downloads, and product content <a href="#media-downloads-and-product-content" id="media-downloads-and-product-content"></a>

Product media should be prepared as a quality issue, not just a file-transfer issue. The source store may contain main images, gallery images, downloadable files, PDFs, manuals, technical documents, videos, or externally hosted media references. The merchant should identify which media assets are required for selling and which can be recreated, replaced, or excluded.

Downloadable products require separate preparation because product access, file availability, order relationship, and customer expectations may depend on the source platform’s download logic. If downloadable products involve license keys, membership rules, subscriptions, or external delivery services, Custom Service review may be needed.

### 3. Prepare Custom Fields, Attributes, and Product Selection Logic <a href="#id-3-prepare-custom-fields-attributes-and-product-selection-logic" id="id-3-prepare-custom-fields-attributes-and-product-selection-logic"></a>

VirtueMart custom fields can carry important product meaning. They may represent product variation, shopper selection, additional information, display logic, technical specifications, related products, pricing modifiers, or plugin-driven behavior. A source product field that looks like a simple attribute may become operationally important in VirtueMart.

Preparation should separate fields into clear groups:

| Source field type          | Preparation question                                        | Likely migration concern                                                                                        |
| -------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Shopper-selectable options | Does the field affect what the customer buys?               | Selection logic, price changes, stock meaning, and order line readability need review.                          |
| Technical specifications   | Does the field help shoppers compare products?              | Product information may belong in product description, custom fields, specifications, or another display layer. |
| Pricing modifiers          | Does the field affect product price or discount behavior?   | Standard mapping may not preserve every pricing rule without review.                                            |
| Plugin-owned fields        | Was the field created by a source extension or custom code? | Custom Service may be needed if the field is not part of standard supported data.                               |
| Display-only notes         | Is the field informational only?                            | It may still matter for storefront clarity, search, or product comparison.                                      |

A good preparation file should list the field name, source location, sample product, business purpose, expected VirtueMart location, and whether the field affects price, stock, checkout, order history, or storefront display.

### 4. Document Shopper Groups, Pricing, Discounts, and Calculation Rules <a href="#id-4-document-shopper-groups-pricing-discounts-and-calculation-rules" id="id-4-document-shopper-groups-pricing-discounts-and-calculation-rules"></a>

VirtueMart stores often rely on shopper groups, customer-specific behavior, tax rules, discount rules, and calculation logic. These structures should be documented before migration because they influence what customers see, what they pay, and how orders are interpreted after launch.

#### Shopper groups and customer segmentation <a href="#shopper-groups-and-customer-segmentation" id="shopper-groups-and-customer-segmentation"></a>

The merchant should identify all shopper groups, their business purpose, and whether they control pricing, visibility, tax behavior, discounts, payment access, shipment access, or B2B/B2C segmentation. Customer records should be reviewed against those groups so the target store does not lose commercial context.

#### Pricing and discount behavior <a href="#pricing-and-discount-behavior" id="pricing-and-discount-behavior"></a>

Preparation should include base prices, sale prices, quantity-based pricing, customer-group pricing, coupons, discounts, tax-inclusive or tax-exclusive display expectations, and any source rules that modify totals at checkout. If the source store uses custom pricing plugins or external systems, standard migration assumptions may be too light.

#### Tax and calculation rules <a href="#tax-and-calculation-rules" id="tax-and-calculation-rules"></a>

VirtueMart calculation rules should be prepared with source evidence. The merchant should identify tax rates, tax categories, country and region behavior, tax display expectations, discount order, fee rules, and any rules that depend on shopper group, product type, country, shipment method, or payment method.

### 5. Prepare Customer, Address, and Order History Samples <a href="#id-5-prepare-customer-address-and-order-history-samples" id="id-5-prepare-customer-address-and-order-history-samples"></a>

Customer and order preparation should focus on operating meaning. Historical records may be used for customer service, warranty questions, repeat purchases, accounting reference, delivery disputes, revenue review, and support history. A migrated order that only preserves an order number and total is often not enough.

#### Customer and address data <a href="#customer-and-address-data" id="customer-and-address-data"></a>

Customer samples should include registered customers, guest customers if supported by the source, B2B customers, customers in special shopper groups, customers with multiple addresses, international customers, and customers with recent orders. Address data should be checked for country, state/region, postal code, company fields, VAT/tax identifiers, phone numbers, and delivery notes where relevant.

#### Order history and status meaning <a href="#order-history-and-status-meaning" id="order-history-and-status-meaning"></a>

Order samples should include simple orders, multi-product orders, discounted orders, taxed orders, shipped orders, refunded or cancelled orders where available, downloadable-product orders, international orders, orders using different payment methods, orders using different shipment methods, and orders that contain variant or custom-field selections.

Order statuses should be documented with their business meaning. If the source platform uses custom statuses or workflow-specific status labels, the merchant should decide whether those statuses can be mapped into VirtueMart meaningfully or require deeper review.

### 6. Prepare Payment, Shipment, Currency, and Multilingual Requirements <a href="#id-6-prepare-payment-shipment-currency-and-multilingual-requirements" id="id-6-prepare-payment-shipment-currency-and-multilingual-requirements"></a>

Payment, shipment, currency, and language behavior often depends on configuration and plugins. These areas should not be treated as ordinary migrated records.

#### Payment methods <a href="#payment-methods" id="payment-methods"></a>

The merchant should identify each payment method, gateway, offline payment workflow, payment status behavior, transaction reference, and post-order handling expectation. If the source platform stores gateway-specific identifiers or plugin-owned metadata, those details may require Custom Service review.

#### Shipment methods <a href="#shipment-methods" id="shipment-methods"></a>

Shipment preparation should document flat rates, weight-based rates, country or region restrictions, free shipping conditions, carrier integrations, pickup options, shipment tracking, delivery notes, and rules that depend on shopper group, product type, cart value, or destination.

#### Currency and multilingual behavior <a href="#currency-and-multilingual-behavior" id="currency-and-multilingual-behavior"></a>

For multilingual or multicurrency stores, the merchant should identify source languages, translated product content, translated categories, translated custom fields, translated checkout labels, currency display rules, exchange-rate expectations, default language, default currency, and any records that are incomplete in one language. Multilingual validation should use real shopper paths, not only admin-side record checks.

### 7. Prepare Joomla Storefront, Template, Module, and SEO Dependencies <a href="#id-7-prepare-joomla-storefront-template-module-and-seo-dependencies" id="id-7-prepare-joomla-storefront-template-module-and-seo-dependencies"></a>

VirtueMart lives inside Joomla, so storefront preparation should include the Joomla site layer. Menus, modules, templates, overrides, route behavior, metadata, canonical expectations, internal links, landing pages, and search visibility may affect whether the migrated store feels complete.

The merchant should list high-value product URLs, category URLs, landing pages, menu items, internal links, module positions, template overrides, checkout entry paths, account pages, and SEO-sensitive redirects. The migration should not assume that source storefront layout, module placement, or design behavior automatically transfers into Joomla and VirtueMart.

### 8. Identify Custom Platform, Extension-Owned, and Integration Data <a href="#id-8-identify-custom-platform-extension-owned-and-integration-data" id="id-8-identify-custom-platform-extension-owned-and-integration-data"></a>

Custom Platform sources, extension-owned data, ERP references, marketplace connectors, loyalty systems, membership systems, subscription tools, payment gateway metadata, fulfillment integrations, or custom Joomla development should be identified before execution.

The preparation question is simple: can the expected result be handled through standard service capability, supported behavior, and applicable Add-ons, or does it require custom migration logic adjustment? Custom Service should be reviewed when the source includes unsupported data structures, bespoke relationships, third-party identifiers, custom fields beyond standard mapping, or transformation requirements that standard capability cannot cover.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

A Demo Migration should include records that expose the store’s real structure. Random samples may show that records can move, but they often fail to prove whether the migrated result is operationally meaningful.

| Sample area      | Recommended examples                                                                                                     | What the sample should prove                                                            |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- |
| Products         | Simple products, parent/child products, custom-field-heavy products, downloadable products, products with several images | Product meaning, selection behavior, media handling, file access, and admin usability.  |
| Categories       | High-traffic categories, deep categories, categories used in menus, categories with many assigned products               | Storefront discovery, product placement, URL expectations, and navigation readiness.    |
| Customers        | Shopper-group customers, international customers, repeat customers, customers with multiple addresses                    | Customer segmentation, address accuracy, account readability, and shopper history.      |
| Orders           | Discounted orders, taxed orders, refunded/cancelled orders, orders with different payment and shipment methods           | Order line meaning, totals, statuses, payment/shipment context, and support usefulness. |
| Custom data      | Plugin-owned fields, external IDs, custom statuses, integration references                                               | Whether Add-on review or Custom Service review is needed.                               |
| Storefront paths | Product URLs, category URLs, menu paths, checkout entry points, account pages                                            | Joomla/VirtueMart navigation, SEO continuity, and customer-facing readiness.            |

### What to Escalate Before Execution <a href="#what-to-escalate-before-execution" id="what-to-escalate-before-execution"></a>

Escalation is appropriate when the source data contains meaning that cannot be interpreted confidently through standard supported behavior. The merchant should raise these issues before Full Migration rather than discovering them after the target store is populated.

Escalate early when:

* product selection logic depends on custom fields, source extensions, or bespoke pricing behavior;
* shopper groups control pricing, tax, visibility, payment, or shipment access;
* tax, discount, payment, or shipment rules depend on multiple conditions;
* order history includes custom statuses, external identifiers, or plugin-owned details;
* multilingual or multicurrency data is incomplete, inconsistent, or source-specific;
* Joomla templates, modules, overrides, or routes must preserve specific storefront behavior;
* source data comes from a Custom Platform or heavily modified system;
* the target project depends on beta, unsupported, or not-yet-confirmed Joomla/VirtueMart compatibility.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VirtueMart preparation should produce a clear operating picture before migration begins. Products, custom fields, shopper groups, calculation rules, orders, payment methods, shipment methods, multilingual content, templates, modules, and SEO-sensitive routes all deserve review because they shape the final Joomla commerce experience.

A strong preparation process does not make the migration heavier than necessary. It identifies where standard service capability is enough, where Add-ons may help, and where Custom Service should be reviewed before the migration process creates avoidable rework.

Use Demo Migration to test representative VirtueMart structures before Full Migration. If product custom fields, shopper groups, calculation rules, payment or shipment behavior, multilingual data, Custom Platform records, or Joomla storefront dependencies carry important business meaning, review the migration path through Live Chat so the preparation work matches the selected service approach.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared before migrating to VirtueMart?**

Prepare the Joomla and VirtueMart target versions, catalog structure, product custom fields, shopper groups, customer records, order samples, calculation rules, payment methods, shipment methods, multilingual content, currencies, templates, modules, and SEO-sensitive routes. The preparation should show how the store is expected to operate after migration, not only which records should be transferred.

**Why are VirtueMart custom fields important before migration?**

VirtueMart custom fields can carry product variation, pricing, specification, display, plugin, or shopper-selection meaning. If the source store uses similar fields differently, they should be reviewed before migration so the target product structure remains understandable and sellable.

**Should old VirtueMart versions be prepared differently?**

Older operational VirtueMart installations should be reviewed against their exact Joomla version, VirtueMart version, extension stack, template layer, and customizations. Current stable behavior should not be assumed for every legacy installation.

**What makes a good VirtueMart Demo Migration sample?**

A good sample includes simple products, parent/child products, custom-field-heavy products, downloadable products, important categories, shopper-group customers, international customers, discounted or taxed orders, orders with different payment and shipment methods, and records that expose custom or plugin-owned behavior.

**When should Custom Service be reviewed before migrating to VirtueMart?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported extension data, custom fields beyond standard mapping, external identifiers, bespoke pricing logic, custom shipment or payment behavior, multilingual restructuring, or custom migration logic adjustment requirements.
