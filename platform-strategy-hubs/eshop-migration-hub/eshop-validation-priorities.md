# EShop Validation Priorities

Validation for an EShop migration should prove that the migrated store works as an EShop-powered Joomla commerce environment, not only that records arrived in the administration area. EShop can represent a wide range of catalog, sales, configuration, and Joomla implementation details, so validation must test whether the business meaning of the source store remains usable inside the Target Platform.

For EShop by Ossolution Team, the most important validation areas are products, categories, manufacturers, options, attributes, customer groups, customers, orders, discounts, coupons, vouchers, checkout fields, tax, shipping, payment, multilingual data, modules, themes, layout behavior, and Joomla routes. These areas should be reviewed together because a result can look correct in one layer while still failing commercially in another layer. A product can be present but not buyable. An option can display but not price correctly. An order can exist but lose the meaning of the selected options. A category can migrate but not support useful storefront discovery.

A strong validation process should therefore answer a practical question: **does the migrated EShop store preserve the meaning that merchants, shoppers, administrators, and implementation teams need after launch?**

### What Validation Is Trying to Prove <a href="#what-validation-is-trying-to-prove" id="what-validation-is-trying-to-prove"></a>

Validation is not a generic inspection step. It is the proof stage where the merchant decides whether the migration result is reliable enough to continue toward Full Migration, launch preparation, or additional service review.

In an EShop migration, validation should prove five things.

#### The catalog still supports shopping and management <a href="#the-catalog-still-supports-shopping-and-management" id="the-catalog-still-supports-shopping-and-management"></a>

The migrated catalog should be understandable to shoppers and manageable by the merchant. Products should retain the details needed for selection, pricing, stock review, shipping decisions, product comparison, and storefront organization. Categories, manufacturers, product images, labels, downloads, reviews, options, attributes, and custom fields should be checked as part of the same catalog system rather than as isolated records.

This is especially important because EShop separates several catalog meanings that some source platforms may combine. Options are shopper-facing selections. Attributes are product specifications used for comparison and information. Categories organize browsing. Manufacturers support another discovery or classification layer. Custom fields may carry project-specific product meaning. Validation should confirm that these roles remain clear after migration.

#### Sales history remains readable and useful <a href="#sales-history-remains-readable-and-useful" id="sales-history-remains-readable-and-useful"></a>

Customer and order records should preserve usable commercial history. A migrated order should show the customer, products, quantities, selected options, unit prices, totals, discounts, coupons, vouchers, tax, shipping, payment method, shipping method, comments, and order status in a way that makes sense for post-migration reference.

The validation question is not only whether the order count is correct. The better question is whether a store administrator can understand what the customer bought, how the order was priced, what adjustments were applied, how payment and shipping were recorded, and what status the order represents.

#### Configuration-sensitive behavior is separated from migrated records <a href="#configuration-sensitive-behavior-is-separated-from-migrated-records" id="configuration-sensitive-behavior-is-separated-from-migrated-records"></a>

Some EShop behavior depends on configuration rather than direct data migration. Tax classes, tax rates, geo zones, currencies, stock statuses, order statuses, shipping plugins, payment plugins, Catalog Mode, Shopping Cart Mode, quote behavior, and checkout settings may need target-side review.

Validation should separate three outcomes: data that migrated correctly, settings that must be configured in EShop, and requirements that need Add-on or Custom Service review. This prevents the merchant from treating every mismatch as a migration failure when some differences are actually target configuration decisions.

#### Joomla presentation supports the migrated store <a href="#joomla-presentation-supports-the-migrated-store" id="joomla-presentation-supports-the-migrated-store"></a>

Because EShop operates inside Joomla, validation should include the storefront and site implementation layer. Product pages, category pages, manufacturer pages, comparison pages, wishlist pages, shopping cart pages, checkout pages, customer pages, quote pages, menus, aliases, metadata, modules, themes, template overrides, and multilingual routing can affect whether migrated data is usable to shoppers.

A technically complete migration may still be incomplete from a launch perspective if shoppers cannot find products, compare product attributes, select options, understand pricing, complete checkout, or navigate account/order areas inside the Joomla site.

#### Custom and extension-owned data is classified correctly <a href="#custom-and-extension-owned-data-is-classified-correctly" id="custom-and-extension-owned-data-is-classified-correctly"></a>

If the source store includes custom fields, unsupported extension data, third-party identifiers, bespoke order structures, custom checkout fields, custom product logic, external integration data, or Custom Platform data, validation should confirm whether the result is acceptable under standard service capability or whether Custom Service review is needed.

The pass condition is not that every custom source behavior automatically appears in EShop. The pass condition is that the merchant understands which data has migrated, which behavior requires target configuration, and which requirements need custom migration logic adjustment or a broader service decision.

### Named Validation Priorities <a href="#named-validation-priorities" id="named-validation-priorities"></a>

The following priorities should guide EShop Demo Migration and Full Migration review.

| Validation priority              | What the review should prove                                                                                                                 | Strong samples to include                                                                                                                               |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure                | Products, categories, manufacturers, images, labels, reviews, and downloads remain meaningful in EShop.                                      | Simple products, image-rich products, downloadable products, products assigned to multiple categories, manufacturer-linked products, reviewed products. |
| Options and attributes           | Shopper selections and product specifications are not confused.                                                                              | Products with required options, priced options, multiple option types, comparison attributes, and attribute groups.                                     |
| Customer and order history       | Customers, groups, addresses, orders, totals, statuses, discounts, coupons, vouchers, tax, shipping, and payment references remain readable. | Recent orders, older orders, discounted orders, voucher/coupon orders, tax/shipping examples, orders with selected product options.                     |
| Configuration-sensitive behavior | Settings-dependent behavior is identified separately from migrated records.                                                                  | Tax-class products, geo-zone examples, currency examples, shipping method examples, payment method examples, stock-status examples.                     |
| Joomla storefront behavior       | Migrated records support usable Joomla storefront pages and navigation.                                                                      | Key products, top categories, manufacturer pages, comparison pages, cart/checkout flow, customer account pages, module-driven pages.                    |
| Multilingual content             | Translations remain complete and usable where multilingual behavior is part of the target plan.                                              | Translated products, categories, attributes, options, manufacturers, labels, downloads, lengths, weights, and messages.                                 |
| Custom or extension-owned data   | Non-standard source meaning is classified for acceptance, Add-on review, or Custom Service review.                                           | Products with custom fields, custom checkout fields, plugin-owned records, external identifiers, unusual order statuses, Custom Platform samples.       |

This table should guide review planning, but it should not replace actual inspection. Each priority needs representative examples from the merchant’s real store because EShop behavior can vary significantly depending on catalog structure, Joomla implementation, plugins, multilingual setup, and configuration choices.

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

Catalog validation should begin with products, but it should not stop at product names and prices. EShop catalog meaning depends on how products relate to categories, manufacturers, options, attributes, images, labels, downloads, reviews, pricing rules, stock settings, tax classes, dimensions, weights, shipping requirements, and publication state.

#### What to validate <a href="#what-to-validate" id="what-to-validate"></a>

Review whether products are present, readable, and commercially usable. Product titles, aliases, descriptions, SKUs, prices, images, categories, manufacturers, quantities, stock statuses, dimensions, weights, tags, related products, downloads, and published state should be checked where they matter to the selected migration path.

For products that use discounts, special prices, customer groups, quote mode, call-for-price behavior, minimum and maximum quantities, or shipping-specific settings, validation should include those records rather than relying only on ordinary products.

#### Strong validation samples <a href="#strong-validation-samples" id="strong-validation-samples"></a>

A strong EShop catalog sample should include:

* a simple product with ordinary price and image behavior
* a product with multiple product images
* a product assigned to an important category and manufacturer
* a product with required options
* a product with comparison attributes
* a product with discount or special pricing
* a product with customer group relevance
* a product with stock, threshold, minimum quantity, or maximum quantity behavior
* a downloadable product if downloads matter
* a product with custom fields or attachments if the source uses them

These samples reveal whether the catalog can actually support selling, comparison, browsing, and administration after migration.

#### What often gets missed <a href="#what-often-gets-missed" id="what-often-gets-missed"></a>

Merchants often review only visible product pages and miss hidden management details. Option values may appear but not affect price or selection as expected. Attributes may be migrated but placed in a way that does not support comparison. Manufacturer relationships may be present but not exposed in navigation. Product images may migrate without the intended ordering or completeness. Product custom fields may require separate review because they are not always equivalent across platforms.

For EShop, the options-versus-attributes distinction deserves special attention. If a source platform used one structure for both shopper choices and product specifications, the migrated result should be inspected carefully before it is accepted.

### Category, Manufacturer, and Discovery Validation <a href="#category-manufacturer-and-discovery-validation" id="category-manufacturer-and-discovery-validation"></a>

Discovery validation proves that shoppers can reach and understand the catalog inside the Joomla site. EShop supports categories, manufacturers, product search, filters, comparison, modules, and storefront pages. Joomla menus, aliases, metadata, themes, and modules can also affect discovery.

#### What to validate <a href="#what-to-validate-1" id="what-to-validate-1"></a>

Review category hierarchy, category names, descriptions, images, aliases, metadata, product assignments, and parent-child relationships. Manufacturer records should be checked for product relationships, display usefulness, and any storefront role they are expected to play. If the target store uses product filters, search modules, category modules, manufacturer modules, or custom landing pages, validate whether the migrated catalog supports those entry points.

#### Strong validation samples <a href="#strong-validation-samples-1" id="strong-validation-samples-1"></a>

The best samples are not always the largest categories. Include high-revenue categories, SEO-sensitive categories, deeply nested categories, categories with many products, categories with only a few important products, manufacturer-led product groups, and pages that shoppers commonly enter from search, ads, email, or internal links.

#### What often gets missed <a href="#what-often-gets-missed-1" id="what-often-gets-missed-1"></a>

A category can exist in EShop but still fail as a discovery path if product assignments, aliases, metadata, menu placement, or module output are not reviewed. Manufacturer data can also become a passive admin record if the target storefront does not expose it where shoppers expect it. Validation should connect migrated organization records to real navigation behavior.

### Options, Attributes, and Comparison Validation <a href="#options-attributes-and-comparison-validation" id="options-attributes-and-comparison-validation"></a>

Options and attributes are one of the most important EShop validation areas because they carry different kinds of product meaning.

#### What to validate <a href="#what-to-validate-2" id="what-to-validate-2"></a>

Options should be reviewed as buying choices. Check whether required options are required, whether option values appear correctly, whether pricing adjustments behave as expected, whether option selections appear in cart/order context, and whether option-heavy products remain understandable to shoppers.

Attributes should be reviewed as product information and comparison data. Check whether attribute groups, attribute names, and values appear in the right product context and whether they support comparison or specification review as intended.

#### Strong validation samples <a href="#strong-validation-samples-2" id="strong-validation-samples-2"></a>

Use products that expose the difference between selection and specification. For example, review products with size or color choices as option samples, and products with technical specifications, material details, dimensions, or compatibility information as attribute samples. Include products where options affect price, shipping, stock, or order line meaning if those structures exist in the source store.

#### What often gets missed <a href="#what-often-gets-missed-2" id="what-often-gets-missed-2"></a>

The most common validation mistake is treating options and attributes as interchangeable. If a shopper-facing choice becomes only an informational attribute, the product may no longer be buyable in the intended way. If a comparison attribute becomes an option, the storefront may ask shoppers to make unnecessary selections. Either mistake can make the migration look complete while damaging product usability.

### Customer, Customer Group, and Checkout Field Validation <a href="#customer-customer-group-and-checkout-field-validation" id="customer-customer-group-and-checkout-field-validation"></a>

Customer validation should prove more than the presence of names and emails. In EShop, customer groups, addresses, billing fields, delivery fields, checkout fields, and sales history can all affect post-migration usefulness.

#### What to validate <a href="#what-to-validate-3" id="what-to-validate-3"></a>

Review customer identity, email addresses, phone numbers, billing addresses, delivery addresses, account relationships, customer group assignment, and order connections. If the source store uses customer group pricing, customer group tax behavior, wholesale groups, member pricing, or segmented discounts, validate representative customers from each group.

Custom checkout fields should be reviewed separately. Billing and delivery field structures may not map cleanly from every source platform, especially if the source used app-added fields, custom checkout logic, or third-party integration data.

#### Strong validation samples <a href="#strong-validation-samples-3" id="strong-validation-samples-3"></a>

Include ordinary retail customers, customers with multiple addresses, customers assigned to special groups, customers with several orders, customers with discounted orders, customers with quote or wholesale relevance, and records with custom checkout fields.

#### What often gets missed <a href="#what-often-gets-missed-3" id="what-often-gets-missed-3"></a>

Customer records may look correct while group assignment, address structure, or checkout-field meaning is incomplete. The merchant should test whether customer service staff can use the migrated record to answer real questions: who bought the product, where it shipped, what group the customer belongs to, which fields were captured, and how the order should be interpreted.

### Order, Coupon, Voucher, Tax, and Status Validation <a href="#order-coupon-voucher-tax-and-status-validation" id="order-coupon-voucher-tax-and-status-validation"></a>

Order validation is one of the strongest tests of migration quality because an order combines many layers: product, option, customer, pricing, discount, tax, shipping, payment, status, and comments.

#### What to validate <a href="#what-to-validate-4" id="what-to-validate-4"></a>

Check order numbers, customer links, ordered products, product options, quantities, unit prices, totals, subtotal, tax, shipping, coupon, voucher, final total, payment method, shipping method, customer comments, payment details, shipping details, and order status.

If the source store used custom statuses, external fulfillment identifiers, payment gateway references, refund notes, or accounting-specific fields, validate whether those fields are included, transformed, omitted, or marked for Custom Service review.

#### Strong validation samples <a href="#strong-validation-samples-4" id="strong-validation-samples-4"></a>

Use orders that contain:

* one simple product
* multiple products
* products with selected options
* coupon discounts
* vouchers
* tax
* shipping cost
* different payment methods
* different shipping methods
* completed, pending, canceled, refunded, or failed status where applicable
* customer comments
* older historical data
* recent operational data

#### What often gets missed <a href="#what-often-gets-missed-4" id="what-often-gets-missed-4"></a>

Order validation often fails when merchants check totals but ignore line-item meaning. If a product option does not appear in the order, customer service may not know which version was purchased. If a coupon or voucher is missing, revenue history may be harder to interpret. If tax and shipping are present but not understandable, financial review becomes weaker. If order statuses do not translate clearly, historical order records may need mapping or configuration review.

### Tax, Shipping, Payment, and System Configuration Validation <a href="#tax-shipping-payment-and-system-configuration-validation" id="tax-shipping-payment-and-system-configuration-validation"></a>

EShop uses configuration-sensitive structures for many operational areas. Validation should clarify which elements are migrated as data and which must be configured in the target environment.

#### What to validate <a href="#what-to-validate-5" id="what-to-validate-5"></a>

Review countries, zones, geo zones, currencies, tax rates, tax classes, stock statuses, order statuses, length and weight units, shipping plugin behavior, payment plugin behavior, and checkout configuration. If the store depends on a specific shipping method, payment gateway, tax region, or currency behavior, validate examples that prove those assumptions.

#### Strong validation samples <a href="#strong-validation-samples-5" id="strong-validation-samples-5"></a>

Select products and orders that expose operational rules: taxable and non-taxable products, products assigned to different tax classes, orders from different zones, orders using different shipping methods, orders using different payment methods, products with weight or dimensions, and products with stock-sensitive behavior.

#### What often gets missed <a href="#what-often-gets-missed-5" id="what-often-gets-missed-5"></a>

Merchants often expect operational behavior to migrate like ordinary records. In practice, tax, shipping, payment, stock, currency, and checkout behavior may require target-side configuration even after data migration is complete. Validation should separate migration accuracy from configuration readiness.

### Multilingual and Multicurrency Validation <a href="#multilingual-and-multicurrency-validation" id="multilingual-and-multicurrency-validation"></a>

Multilingual validation matters when the merchant expects EShop to support multiple storefront languages. EShop multilingual behavior should be reviewed through actual translated records, not assumed from a default-language migration.

#### What to validate <a href="#what-to-validate-6" id="what-to-validate-6"></a>

Check translated categories, products, product custom fields, messages, attributes, attribute groups, options, manufacturers, labels, downloads, lengths, and weights where relevant. Review whether translated titles, descriptions, aliases, metadata, option names, attribute labels, and storefront messages appear correctly.

Currency validation should check whether currency records, display expectations, pricing context, and order history remain understandable. If multicurrency behavior depends on configuration or external services, validate what belongs to migration and what belongs to target setup.

#### Strong validation samples <a href="#strong-validation-samples-6" id="strong-validation-samples-6"></a>

Use products and categories that exist in each important language, not only the default language. Include option-heavy products, attribute-heavy products, manufacturer-linked products, and checkout/order examples that expose language or currency assumptions.

#### What often gets missed <a href="#what-often-gets-missed-6" id="what-often-gets-missed-6"></a>

A multilingual store can appear acceptable in the default language while translated names, aliases, metadata, messages, or option labels are incomplete. If the merchant uses multilingual SEO, localized navigation, or language-specific product presentation, validation should include real shopper paths in each language.

### Joomla Modules, Themes, Layouts, and Routes Validation <a href="#joomla-modules-themes-layouts-and-routes-validation" id="joomla-modules-themes-layouts-and-routes-validation"></a>

EShop data becomes useful only when it is displayed correctly inside the Joomla site. Modules, themes, layouts, template overrides, menus, aliases, metadata, and routes can affect how migrated data appears.

#### What to validate <a href="#what-to-validate-7" id="what-to-validate-7"></a>

Review product pages, category pages, manufacturer pages, comparison pages, wishlist pages, cart pages, checkout pages, customer pages, and quote pages. Check whether search, filter, product, category, manufacturer, and cart modules display the migrated data as intended. Confirm that menus, aliases, metadata, page titles, and page headings support the expected storefront paths.

If the site uses custom theme files, template overrides, custom modules, or developer-built plugins, validation should identify whether those dependencies are implementation tasks or migration concerns.

#### Strong validation samples <a href="#strong-validation-samples-7" id="strong-validation-samples-7"></a>

Use high-value product URLs, category URLs, manufacturer paths, cart and checkout flows, account pages, search/filter results, module-driven landing pages, and translated routes if multilingual behavior matters.

#### What often gets missed <a href="#what-often-gets-missed-7" id="what-often-gets-missed-7"></a>

The most common mistake is validating only the administration area. A record can exist in EShop while the frontend page, module output, route, alias, metadata, or template display is not ready. For launch planning, storefront validation is not optional.

### What Makes a Strong Validation Sample <a href="#what-makes-a-strong-validation-sample" id="what-makes-a-strong-validation-sample"></a>

A strong validation sample is not a random subset of products and orders. It should be deliberately chosen to expose the store’s most important structures.

Good samples usually include:

* high-revenue products
* simple products
* option-heavy products
* attribute-heavy products
* products with customer group pricing or discounts
* products with tax, shipping, weight, or stock sensitivity
* products in important categories and manufacturers
* translated products and categories
* customers from different groups
* orders with options, coupons, vouchers, tax, shipping, payment methods, comments, and different statuses
* records with custom fields or plugin-owned meaning
* storefront paths that matter for traffic, SEO, campaigns, or support workflows

The goal is to find issues early. A Demo Migration sample that only includes ordinary records can create false confidence.

### What Often Gets Missed <a href="#what-often-gets-missed-8" id="what-often-gets-missed-8"></a>

The most common missed issues in EShop validation are not always missing records. They are meaning gaps:

* product options appear but do not preserve shopper selection behavior
* attributes migrate but do not support comparison or specification review
* customer groups appear but do not preserve pricing or tax relevance
* orders exist but selected options, statuses, coupons, vouchers, comments, or tax/shipping context are hard to interpret
* checkout fields exist but do not carry the source meaning the merchant expects
* tax, shipping, payment, and stock behavior needs target configuration but is mistaken for migrated data
* translated content is incomplete outside the default language
* Joomla modules, aliases, metadata, routes, and template output are not validated
* custom fields, custom plugins, external identifiers, or extension-owned records are assumed to be standard data

These issues should be classified before launch so the merchant can decide whether they require configuration review, data cleanup, Add-on review, Custom Service review, or additional implementation work.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation results should be interpreted consistently. Not every issue has the same meaning.

| Result category             | What it means                                                                                                                                                                                                                             | Recommended response                                                                                                          |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Pass                        | The migrated result preserves the required meaning for the reviewed sample.                                                                                                                                                               | Continue reviewing other representative samples and prepare for the next migration step.                                      |
| Needs configuration review  | The data is present, but EShop or Joomla settings must be adjusted.                                                                                                                                                                       | Review target-side tax, shipping, payment, stock, order status, checkout, module, menu, theme, or multilingual configuration. |
| Needs data cleanup          | The issue comes from inconsistent, duplicate, incomplete, or unclear source data.                                                                                                                                                         | Clean source records or clarify source meaning before relying on Full Migration results.                                      |
| Needs Add-on review         | The requirement may fit filtering, mapping, or configuration support through available Add-ons.                                                                                                                                           | Review whether Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure can support the desired result.          |
| Needs Custom Service review | The requirement involves Custom Platform data, unsupported extension data, custom fields, bespoke transformation, third-party identifiers, plugin-owned behavior, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment. | Review the requirement through Custom Service before treating it as launch-ready.                                             |
| Not launch-ready            | The issue affects shopper experience, order interpretation, customer service, operational reliability, or storefront continuity.                                                                                                          | Do not proceed to launch until the issue is resolved, revalidated, or deliberately accepted.                                  |

This interpretation step protects the merchant from two mistakes: accepting a weak migration result too quickly, or escalating a simple configuration issue as if it were a custom migration problem.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EShop validation should prove that the migrated store is commercially understandable, operationally useful, and ready to function inside Joomla. The most important areas are products, categories, manufacturers, options, attributes, customer groups, customers, orders, coupons, vouchers, tax, shipping, payment, checkout fields, multilingual content, modules, themes, layouts, aliases, metadata, and custom or plugin-owned data.

A strong review does not rely on record counts alone. It uses representative samples to test how catalog meaning, order history, configuration-sensitive behavior, and Joomla presentation work together. When a validation issue appears, the merchant should classify it carefully as configuration review, data cleanup, Add-on review, Custom Service review, or a launch-blocking problem.

Use Demo Migration results to validate the EShop migration against real products, customers, orders, options, attributes, customer groups, checkout fields, multilingual records, and Joomla storefront paths. If validation reveals custom fields, unsupported extension data, plugin-owned behavior, third-party identifiers, Custom Platform data, or transformation needs, use Live Chat to review whether the selected migration path, Add-ons, or Custom Service should be adjusted before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first after migrating to EShop?**

Start with the records that prove the store can operate: important products, categories, options, attributes, customers, customer groups, orders, discounts, tax, shipping, payment references, and checkout fields. Then review Joomla storefront paths, modules, aliases, metadata, theme output, and multilingual content if they affect the target store.

**Why are product options and attributes separate validation priorities?**

In EShop, options and attributes carry different meanings. Options are shopper-facing selections that can affect purchasing, while attributes describe product specifications and support comparison. Confusing them can make products look complete while still damaging buying behavior or product information.

**Should tax, shipping, and payment behavior be treated as migrated data?**

Not always. Some tax, shipping, payment, currency, stock, and checkout behavior depends on EShop configuration or plugin setup in the target environment. Validation should separate migrated records from target-side configuration and custom requirements.

**How should multilingual EShop data be validated?**

Review actual translated products, categories, options, attributes, manufacturers, labels, downloads, messages, aliases, metadata, and storefront paths. A default-language pass is not enough when the target store depends on multilingual selling or localized SEO.

**When should validation lead to Custom Service review?**

Custom Service should be reviewed when validation reveals Custom Platform data, unsupported extension data, product custom fields, custom checkout fields, plugin-owned behavior, third-party identifiers, bespoke transformations, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment needs beyond standard service capability.
