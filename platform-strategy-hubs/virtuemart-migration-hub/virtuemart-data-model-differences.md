# VirtueMart Data Model Differences

VirtueMart migration is not only a record-transfer exercise. VirtueMart is a Joomla e-commerce extension with its own commerce structure, but it also depends on Joomla for menus, templates, modules, languages, users, permissions, plugins, and routing. A product, customer, order, price rule, or shipment method may therefore carry meaning from both the commerce component and the surrounding Joomla site.

VirtueMart 4.6.4 is the stable release baseline for migration planning. Older VirtueMart installations may remain operational, but older behavior should be reviewed against the intended target installation. Joomla 6 compatibility should be verified separately when the target environment depends on it.

A strong VirtueMart migration translates business meaning into VirtueMart’s product, category, custom field, shopper group, calculation rule, order, payment, shipment, multilingual, and Joomla presentation layers. The goal is not simply to show that products and orders exist after migration. The migrated data must still explain how the merchant sells, prices, groups, taxes, ships, invoices, displays, and manages the store.

### Core VirtueMart Structural Layers <a href="#core-virtuemart-structural-layers" id="core-virtuemart-structural-layers"></a>

VirtueMart organizes commerce through several connected layers. Some layers store records directly, such as products, categories, manufacturers, customers, shopper groups, coupons, orders, payment methods, and shipment methods. Other layers define how those records behave, such as custom fields, calculation rules, shopper fields, templates, plugins, modules, languages, currencies, and Joomla routes.

| VirtueMart layer              | What it controls                                                                                                                  | Migration meaning                                                                                          |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Product and catalog layer     | Products, categories, manufacturers, media, prices, stock, child products, reviews, and product display settings                  | Source catalog data must become sellable VirtueMart catalog structure, not only product rows.              |
| Custom field layer            | Product attributes, selectable options, specifications, plugin-driven values, and additional display or buying behavior           | Source options, attributes, and custom data must be classified before mapping.                             |
| Shopper layer                 | Shoppers, shopper groups, shopper fields, billing and shipping information, and registration/checkout data                        | Customer data must preserve account, group, address, and checkout meaning.                                 |
| Pricing and calculation layer | Taxes, discounts, price modifiers, calculation rules, shopper-group conditions, country/state restrictions, and currency behavior | Pricing logic may need configuration, mapping, or Custom Service review rather than direct record copying. |
| Order and invoice layer       | Order items, selected options, statuses, invoices, payment/shipment details, comments, and historical context                     | Order history must remain readable and operationally useful.                                               |
| Joomla presentation layer     | Menus, modules, templates, overrides, URLs, metadata, language associations, and plugin behavior                                  | Storefront continuity depends on Joomla implementation, not only VirtueMart records.                       |

These layers should be interpreted together. A migrated product may look complete in the VirtueMart administration area but still lose meaning if child products, custom fields, shopper group pricing, calculation rules, product images, language values, or product routes are incomplete.

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

VirtueMart product data is broader than product names and prices. A product can carry descriptive content, SKU/model values, images, media, availability, dimensions, weight, manufacturer relationships, category placement, inventory settings, reviews, ratings, related products, and ordering/display behavior. Product migration should preserve enough structure for the merchant to manage the item and for shoppers to understand what they are buying.

Source platforms often store catalog logic differently. A source store may use option sets, attributes, product families, variants, configurable products, grouped products, downloadable products, bundles, app-owned fields, or custom code. VirtueMart may represent parts of that structure through products, child products, custom fields, stock settings, downloadable media, categories, manufacturers, or plugin-supported behavior.

#### Categories and manufacturers define discovery context <a href="#categories-and-manufacturers-define-discovery-context" id="categories-and-manufacturers-define-discovery-context"></a>

VirtueMart categories are not merely folders. They affect storefront organization, product discovery, menu relationships, layout expectations, metadata, and sometimes how merchants think about pricing, tax, shipping, or product visibility. Nested category depth, duplicate categories, category descriptions, category images, and category-level display assumptions should be reviewed before migration.

Manufacturers add another discovery and reporting layer. Source platforms may treat brands, vendors, suppliers, or makers differently. When brand identity is important to the storefront or catalog management process, manufacturer mapping should preserve the intended meaning rather than flattening all brand-related data into product descriptions.

#### Product media has operational and storefront value <a href="#product-media-has-operational-and-storefront-value" id="product-media-has-operational-and-storefront-value"></a>

Product images, thumbnails, downloadable files, category images, manufacturer images, and other media records can affect customer trust, product comparison, and post-launch management. Source image galleries, option-specific images, external image paths, file naming conventions, and old CDN references should be reviewed. If a source store uses app-owned media relationships or variant-specific images, those relationships may need deeper mapping review.

#### Product reviews and ratings need context <a href="#product-reviews-and-ratings-need-context" id="product-reviews-and-ratings-need-context"></a>

Reviews and ratings may support customer confidence, but source platforms can store them with different moderation states, customer associations, dates, rating scales, and product relationships. A migrated review should be connected to the correct product and retain enough context to remain credible. When review history is incomplete, duplicated, app-owned, or not clearly tied to active products, validation should decide whether the result is usable.

### Parent and Child Product Meaning <a href="#parent-and-child-product-meaning" id="parent-and-child-product-meaning"></a>

Parent/child products are one of the most important VirtueMart data-model differences. Many source platforms describe product variation through options, variants, attributes, configurable products, or SKU-level child items. VirtueMart can use parent and child products, derived product patterns, and custom fields to express similar commercial meaning, but the structures are not automatically equivalent.

A parent product may provide shared catalog meaning: description, category placement, images, manufacturer, common display information, or grouping logic. Child products may carry selectable differences such as size, color, material, package size, stock, SKU, price, dimensions, weight, or media. If the source platform treats every variant as an independent product, VirtueMart planning may need to decide whether the target should preserve that independence or group those records under parent products.

#### Variant structure affects shopper choice <a href="#variant-structure-affects-shopper-choice" id="variant-structure-affects-shopper-choice"></a>

Variant migration should be judged by how shoppers select products, not only by how many product records appear. A color/size product should allow the shopper to choose a valid combination. A product with stock by option should preserve stock meaning at the level the merchant actually manages. A product with option-level price differences should preserve the price difference in a way that is visible and maintainable in VirtueMart.

When source option logic includes conditional options, dependent options, image swaps, price modifiers, bundles, subscriptions, custom calculators, or third-party configurators, standard product migration may not preserve the full behavior. Those cases should be reviewed for Advanced Data Mapping, Advanced Data Configure, or Custom Service depending on the required transformation.

#### Derived products require careful sample selection <a href="#derived-products-require-careful-sample-selection" id="derived-products-require-careful-sample-selection"></a>

Derived product patterns can look simple until the source catalog contains mixed inheritance behavior. Some child products may inherit most parent values. Others may override price, image, stock, dimensions, or description. Demo Migration samples should include simple products, parent/child products, multi-option products, child products with overridden values, and products with important stock or pricing differences.

### Custom Fields, Attributes, and Specifications <a href="#custom-fields-attributes-and-specifications" id="custom-fields-attributes-and-specifications"></a>

VirtueMart custom fields are not a single-purpose data bucket. They can support product specifications, shopper-selectable attributes, additional display values, plugin-triggered behavior, downloadable or related information, and layout-specific content. That makes custom fields powerful, but it also makes them easy to misunderstand during migration.

A source platform may use separate concepts for attributes, options, metafields, custom product fields, tags, technical specifications, product filters, add-on fields, or app-specific values. VirtueMart may not treat all of those as the same thing. Some values should become visible specifications. Some should become shopper-selectable custom fields. Some may belong in descriptions, categories, filters, manufacturer data, or custom logic. Some may require Custom Service if the source behavior is not a normal field-to-field mapping.

#### Display data and buying data should not be mixed carelessly <a href="#display-data-and-buying-data-should-not-be-mixed-carelessly" id="display-data-and-buying-data-should-not-be-mixed-carelessly"></a>

A technical specification such as material may help shoppers compare products. A selectable option such as size may determine what the customer buys. A hidden integration identifier may connect the product to an external ERP. These are different types of meaning. Treating them as equivalent custom fields can create a target store that appears complete but is difficult to buy from, filter, or operate.

#### Plugin-driven custom fields need deeper review <a href="#plugin-driven-custom-fields-need-deeper-review" id="plugin-driven-custom-fields-need-deeper-review"></a>

VirtueMart custom fields may be supported by plugins or custom extensions. When a source store uses a custom configurator, subscription plugin, bundled-product behavior, special calculator, or external data feed, the migrated value may need more than ordinary field mapping. The correct question is whether VirtueMart should store a value, recreate a behavior, preserve a display field, or connect to a custom extension after migration.

### Shopper Groups, Shopper Fields, and Customer Meaning <a href="#shopper-groups-shopper-fields-and-customer-meaning" id="shopper-groups-shopper-fields-and-customer-meaning"></a>

VirtueMart customer meaning is shaped by shoppers, shopper groups, shopper fields, billing and shipping information, Joomla user accounts, and checkout/registration behavior. A customer record is not only a name and email address. It may carry group membership, address history, tax context, B2B classification, price-display rules, payment/shipment eligibility, or checkout field values.

Shopper groups are especially important. They can influence prices, discounts, calculation rules, product access, payment methods, shipment methods, and price display. If the source platform uses customer groups, wholesale roles, B2B tiers, tax-exempt customers, membership levels, or special buyer segments, those groups should be reviewed before migration. A group name alone is not enough; the business rules attached to that group determine the migration meaning.

#### Shopper fields can affect checkout and account quality <a href="#shopper-fields-can-affect-checkout-and-account-quality" id="shopper-fields-can-affect-checkout-and-account-quality"></a>

VirtueMart shopper fields collect customer, billing, shipping, registration, and checkout data. Source platforms may have custom checkout fields, company fields, tax ID fields, VAT fields, delivery instructions, membership numbers, or external account identifiers. Some values can be mapped as supported fields. Others may require custom fields, configuration, or Custom Service review.

A migrated customer profile should be validated against real customer-service needs. The merchant should be able to identify the customer, understand the account or group context, review addresses, interpret past orders, and determine whether any special tax, shipping, or pricing treatment applies.

### Prices, Currencies, Taxes, Discounts, and Calculation Rules <a href="#prices-currencies-taxes-discounts-and-calculation-rules" id="prices-currencies-taxes-discounts-and-calculation-rules"></a>

VirtueMart pricing is connected to calculation rules. Tax, discounts, shopper groups, countries, states, currencies, products, categories, and time-sensitive conditions may all affect the final price a shopper sees. Source platforms often store tax and discount logic differently, so pricing migration should distinguish between historical order totals, product base prices, current price rules, tax configuration, and promotional logic.

#### Historical price data is not the same as active pricing behavior <a href="#historical-price-data-is-not-the-same-as-active-pricing-behavior" id="historical-price-data-is-not-the-same-as-active-pricing-behavior"></a>

An old order total shows what happened in the past. It does not automatically recreate the rule that produced the total. A product discount may be a migrated promotional record, a manual sale price, a source app rule, or a historical value no longer active. A tax amount in an old order may be useful for order history but separate from the tax rules that need to operate after launch.

Migration planning should identify which pricing values must be migrated as records, which current rules must be configured in VirtueMart, and which historical order values should remain as reference information only.

#### Calculation rules require condition review <a href="#calculation-rules-require-condition-review" id="calculation-rules-require-condition-review"></a>

VirtueMart calculation rules can be conditional. Conditions may involve shopper groups, products, categories, countries, states, currencies, dates, and other shop configuration. A source rule that looks like a simple discount may carry hidden conditions. A tax rule may depend on shipping destination, billing country, product type, or customer status. These relationships should be documented before migration and validated with representative products and orders.

### Payment and Shipment Method Meaning <a href="#payment-and-shipment-method-meaning" id="payment-and-shipment-method-meaning"></a>

Payment and shipment methods in VirtueMart are method-based and plugin-sensitive. A source platform may store shipping rates, payment gateways, carrier rules, restrictions, payment statuses, or processor identifiers in a different structure. VirtueMart may require payment and shipment methods to be configured in the target environment even when historical orders are migrated.

Payment and shipment methods can also be restricted by country, shopper group, order value, currency, category, coupon use, or plugin parameters. That means a payment method record is not enough. The availability conditions and plugin behavior must make sense in the target store.

#### Historical method labels require interpretation <a href="#historical-method-labels-require-interpretation" id="historical-method-labels-require-interpretation"></a>

Old orders may show PayPal, bank transfer, UPS, or standard shipping. Those labels may be sufficient for customer-service reference, but they do not guarantee that the corresponding gateway or shipment plugin is installed, configured, and behaving in the target store. Historical method data and live checkout configuration should be validated separately.

#### Plugin-provided details may not be standard records <a href="#plugin-provided-details-may-not-be-standard-records" id="plugin-provided-details-may-not-be-standard-records"></a>

Some payment and shipment plugins store transaction IDs, tracking values, carrier responses, labels, fraud checks, status changes, or customer-facing instructions. If those details matter after migration, they should be reviewed early. Plugin-owned data may require Custom Service when it is outside standard service capability or depends on custom migration logic adjustment.

### Order, Invoice, and Status Meaning <a href="#order-invoice-and-status-meaning" id="order-invoice-and-status-meaning"></a>

VirtueMart order history should remain useful after migration. Important order meaning includes the customer, billing and shipping address, purchased products, selected options or child products, prices, discounts, taxes, shipping charges, payment method, shipment method, currency, order status, comments, invoice references, and historical timestamps.

Order statuses are not always equivalent across platforms. A source status such as completed, paid, shipped, fulfilled, processing, or refunded may not map cleanly to VirtueMart status meaning. If the source store uses custom statuses, fulfillment integration statuses, marketplace statuses, or payment-gateway statuses, those should be reviewed before migration.

#### Invoices and documents depend on target configuration <a href="#invoices-and-documents-depend-on-target-configuration" id="invoices-and-documents-depend-on-target-configuration"></a>

Invoices, delivery notes, order emails, and documents may be generated by VirtueMart configuration, templates, extensions, or external systems. Migrating order history does not automatically recreate every old document or every source-system template. If the merchant needs specific invoice references, document numbers, tax display, payment instructions, or email history, those requirements should be identified before execution.

### Multilingual and Multicurrency Meaning <a href="#multilingual-and-multicurrency-meaning" id="multilingual-and-multicurrency-meaning"></a>

VirtueMart multilingual behavior depends on the Joomla language environment and VirtueMart language structure. Source platforms may store translated product names, descriptions, categories, custom fields, metadata, URLs, and checkout labels differently. The target store should be validated by language, not only by default-language records.

Multicurrency behavior also deserves separate interpretation. A source store may store base currency, order currency, display currency, exchange rates, payment currency, and rounded totals. VirtueMart migration should preserve order currency context where supported and confirm how target display currencies and rates are configured.

#### Translation completeness is part of data quality <a href="#translation-completeness-is-part-of-data-quality" id="translation-completeness-is-part-of-data-quality"></a>

A translated product should not only have a translated title. Category placement, custom fields, specifications, descriptions, metadata, menu links, and route behavior may all need language-specific review. Missing translations may not break the store technically, but they can reduce customer trust and create inconsistent storefront experiences.

#### Currency behavior affects both catalog and order history <a href="#currency-behavior-affects-both-catalog-and-order-history" id="currency-behavior-affects-both-catalog-and-order-history"></a>

Product prices, order totals, payment references, tax values, shipping charges, and discounts may interact with currency logic. If the source platform used live conversion, manual rates, payment-specific currency rules, or multi-region pricing, those assumptions should be documented before migration.

### Joomla Storefront, SEO, Template, and Route Meaning <a href="#joomla-storefront-seo-template-and-route-meaning" id="joomla-storefront-seo-template-and-route-meaning"></a>

VirtueMart storefront meaning is shaped by Joomla menus, modules, templates, overrides, metadata, routing, and SEO configuration. Source categories and products must become usable pages in the target storefront. A migrated product that is technically present may still be hard to find if menu routes, category relationships, modules, or SEO settings are not planned.

#### Templates and overrides can change what data means visually <a href="#templates-and-overrides-can-change-what-data-means-visually" id="templates-and-overrides-can-change-what-data-means-visually"></a>

VirtueMart templates and overrides can control how product fields, prices, custom fields, stock messages, manufacturer values, reviews, related products, payment options, and shipment information appear. If a source store depends on a custom layout, equivalent presentation may require Joomla template work or implementation review outside the migrated data itself.

#### Routes and metadata affect discovery continuity <a href="#routes-and-metadata-affect-discovery-continuity" id="routes-and-metadata-affect-discovery-continuity"></a>

Old product URLs, category URLs, metadata, aliases, canonical behavior, and internal links may carry search and customer-navigation value. Migration should identify high-value routes before execution. Redirects and menu planning may be needed when source paths cannot be preserved exactly.

### Extension-Owned and Custom Source Data <a href="#extension-owned-and-custom-source-data" id="extension-owned-and-custom-source-data"></a>

VirtueMart stores often rely on extensions, plugins, template overrides, custom code, import/export routines, ERP connectors, payment/shipment plugins, analytics tools, or custom admin workflows. Some of these structures produce visible data. Others only produce behavior.

Custom Platform sources, unsupported extension data, external identifiers, bespoke product relationships, third-party order metadata, custom checkout logic, custom calculation behavior, and plugin-owned records should not be assumed to fit standard migration behavior. Custom Service should be reviewed when the expected VirtueMart result depends on custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, or broader bespoke interpretation.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

A completed VirtueMart migration should prove that the target store preserves operating meaning, not only record count.

| Proof area                        | What the migrated result should show                                                                                                    |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure                 | Products, categories, manufacturers, media, and product relationships are understandable and manageable.                                |
| Variant and custom field behavior | Parent/child products, selectable values, specifications, and plugin-supported fields preserve buying and display meaning.              |
| Shopper context                   | Customer records, shopper groups, shopper fields, addresses, and account/order relationships remain useful.                             |
| Pricing and calculation behavior  | Prices, taxes, discounts, currencies, and calculation rules are either correctly migrated, correctly configured, or flagged for review. |
| Order history                     | Orders, statuses, comments, selected options, payment/shipment context, invoice references, and totals remain readable.                 |
| Storefront continuity             | Product pages, category pages, menus, modules, routes, metadata, and template expectations support customer navigation.                 |
| Custom behavior                   | Extension-owned data, Custom Platform source logic, external identifiers, and bespoke relationships are identified rather than hidden.  |

### Conclusion <a href="#conclusion" id="conclusion"></a>

VirtueMart migration quality depends on translating commercial meaning into a Joomla-native commerce structure. Products, child products, custom fields, shopper groups, calculation rules, payment and shipment methods, orders, invoices, languages, currencies, templates, modules, and routes all contribute to whether the target store is usable after migration.

The most important data-model question is not whether source records can be moved into VirtueMart. The stronger question is whether those records still explain how the merchant sells, prices, taxes, ships, displays, and supports the store. When source data includes complex product structures, shopper-group rules, plugin-owned behavior, multilingual content, custom fields, or Custom Platform relationships, those areas should be reviewed before Full Migration.

Use Demo Migration results to confirm that VirtueMart preserves the meaning behind product structures, shopper groups, calculation rules, order history, and storefront routes. If the result exposes unsupported custom fields, unclear plugin-owned data, non-standard calculation logic, or Custom Platform source behavior, use Live Chat to confirm whether Advanced Data Mapping, Advanced Data Configure, Managed Service, or Custom Service should be part of the final migration plan.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do VirtueMart product structures need special review during migration?**

VirtueMart can use parent products, child products, custom fields, categories, manufacturers, media, and calculation rules to express catalog meaning. Source product variants or options may not map cleanly unless their buying, pricing, stock, and display behavior are reviewed.

**Are VirtueMart custom fields the same as product attributes from another platform?**

Not always. VirtueMart custom fields can represent selectable product values, visible specifications, plugin-supported behavior, downloadable or related information, or custom display logic. Source attributes should be classified before mapping so buying behavior is not confused with descriptive information.

**Can shopper groups be migrated like ordinary customer groups?**

Shopper groups may affect prices, tax rules, payment methods, shipment methods, product access, and price display. They should be reviewed as business-rule context, not only as customer labels.

**Do payment and shipment methods migrate as complete live checkout behavior?**

Historical payment and shipment labels may be migrated for order-reference purposes where supported, but live checkout behavior usually depends on VirtueMart method configuration, plugins, restrictions, and target-store setup. Those settings should be validated separately.

**How should multilingual VirtueMart data be checked after migration?**

Validation should include translated product names, descriptions, categories, custom fields, metadata, menu paths, and storefront routes. A default-language pass is not enough for a multilingual VirtueMart store.
