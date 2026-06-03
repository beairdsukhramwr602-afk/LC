# VirtueMart Validation Priorities

VirtueMart migration validation should prove that migrated records remain commercially useful inside the target Joomla store. A product that appears in the administration area is not automatically ready for shoppers. A customer record that exists is not automatically useful for account continuity. An order total that matches the source does not always prove that taxes, discounts, payment context, shipment context, shopper group meaning, or line-item relationships remain understandable.

VirtueMart 4.6.4 is the stable release baseline for migration planning. Validation should still confirm the actual Joomla version, VirtueMart version, template layer, installed extensions, and target configuration used by the project, especially when the target store uses an older operational installation or a version combination that differs from the stable release baseline.

### What Validation Is Trying to Prove <a href="#what-validation-is-trying-to-prove" id="what-validation-is-trying-to-prove"></a>

Validation is not a visual spot check. It is a proof process that confirms whether the migrated store can support catalog management, customer service, order reference, pricing review, tax and shipment interpretation, storefront navigation, and launch readiness.

For VirtueMart, validation has to cover both commerce data and Joomla implementation context. Commerce data includes products, categories, manufacturers, media, custom fields, shopper groups, shopper fields, customers, orders, calculation rules, coupons, payment methods, shipment methods, currencies, countries, and order statuses. Joomla implementation context includes menus, modules, templates, overrides, language setup, aliases, metadata, routes, access behavior, and any custom extensions that affect product pages, checkout, or administration.

A strong validation result should answer five practical questions:

1. Can shoppers understand and buy the migrated products?
2. Can the merchant manage catalog, customer, and order records confidently after launch?
3. Can historical orders still support customer service, finance review, and operational reference?
4. Can storefront routes, menus, modules, templates, and language behavior support the new store experience?
5. Can the remaining gaps be solved through configuration, data cleanup, Add-on review, or Custom Service review before Full Migration?

### Priority 1: Product and Catalog Structure <a href="#priority-1-product-and-catalog-structure" id="priority-1-product-and-catalog-structure"></a>

Product validation should begin with the catalog records that carry the most selling meaning. In VirtueMart, product data may include product names, aliases, SKUs, descriptions, prices, manufacturers, categories, media, inventory, dimensions, weights, tax context, availability, related products, downloadable-file assumptions, and publication status.

#### What to validate <a href="#what-to-validate" id="what-to-validate"></a>

Validate products that represent the real catalog, not only simple records. The sample should include ordinary products, high-revenue products, products with multiple images, products assigned to several categories, products with stock behavior, products with manufacturer context, products with special pricing, and products that depend on custom fields or child-product relationships.

Category validation should confirm hierarchy, category names, aliases, descriptions, metadata, image use, published state, ordering, and product assignment. Manufacturer validation should confirm whether brand or manufacturer meaning remains available where the merchant expects it.

#### Strong validation samples <a href="#strong-validation-samples" id="strong-validation-samples"></a>

Strong samples include one simple product, one product with several media files, one product in multiple categories, one manufacturer-linked product, one inventory-sensitive product, one sale or discounted product, one downloadable or file-associated product if relevant, and one product that drives a high-value landing page.

#### What often gets missed <a href="#what-often-gets-missed" id="what-often-gets-missed"></a>

Merchants often validate that product names and prices exist but miss category assignment, alias behavior, manufacturer references, image ordering, metadata, inventory state, product ordering, related products, and whether the product can actually be found through the storefront routes and modules used by the target Joomla site.

### Priority 2: Parent, Child, Variant, and Custom Field Behavior <a href="#priority-2-parent-child-variant-and-custom-field-behavior" id="priority-2-parent-child-variant-and-custom-field-behavior"></a>

VirtueMart product relationships require careful validation because shopper-facing choice can depend on parent products, child products, custom fields, plugin-driven custom field behavior, option-like structures, and derived product assumptions. A migration can preserve visible product records while still weakening how buyers choose size, color, package, material, format, download type, or other commercial options.

#### What to validate <a href="#what-to-validate-1" id="what-to-validate-1"></a>

Validate whether parent and child product relationships remain understandable. Confirm whether child products show the correct prices, SKUs, media, inventory, and shopper-facing selections. Review custom fields for both display meaning and functional meaning. A custom field that only adds descriptive information is different from a custom field that controls selection, price, variant behavior, cart behavior, or extension logic.

#### Strong validation samples <a href="#strong-validation-samples-1" id="strong-validation-samples-1"></a>

Use products that expose different relationship patterns. A useful set includes a parent product with several children, a product with required selection behavior, a product with optional add-ons, a product with custom-field pricing, a product with custom-field display content, and a product whose source behavior was created by an extension or custom code.

#### What often gets missed <a href="#what-often-gets-missed-1" id="what-often-gets-missed-1"></a>

The most common mistake is treating every custom field as a label or note. In VirtueMart, custom fields can be part of the buying experience, the display experience, the pricing structure, or the extension layer. If validation does not distinguish those meanings, the migrated catalog can appear complete while still being functionally weaker than the source store.

### Priority 3: Shopper Groups, Shopper Fields, and Customer Meaning <a href="#priority-3-shopper-groups-shopper-fields-and-customer-meaning" id="priority-3-shopper-groups-shopper-fields-and-customer-meaning"></a>

VirtueMart can use shopper groups and shopper fields to carry business rules, segmentation, pricing context, tax assumptions, registration behavior, and customer classification. Customer validation should therefore prove more than name, email, and address presence.

#### What to validate <a href="#what-to-validate-2" id="what-to-validate-2"></a>

Validate customer records, addresses, account status, shopper group assignment, custom shopper fields, billing and shipping information, and order relationships. Confirm whether important B2B, wholesale, retail, member, tax-exempt, regional, or access-sensitive customer groups remain meaningful after migration.

Shopper fields should be reviewed for required fields, optional fields, address fields, registration context, and checkout relevance. If the source store used custom customer fields or external customer identifiers, those records should be checked before assuming the migration is complete.

#### Strong validation samples <a href="#strong-validation-samples-2" id="strong-validation-samples-2"></a>

Select customers from different groups, customers with multiple addresses, customers with order history, customers with incomplete or unusual source fields, and customers affected by B2B or segmented pricing. Include both recent and older customer accounts when historical behavior matters.

#### What often gets missed <a href="#what-often-gets-missed-2" id="what-often-gets-missed-2"></a>

Customer validation often misses shopper group meaning, custom shopper fields, address formatting, tax-relevant data, and whether historical order relationships remain easy to interpret from the customer record. These gaps can affect support workflows even when the customer list itself looks accurate.

### Priority 4: Order History, Statuses, and Operational Reference <a href="#priority-4-order-history-statuses-and-operational-reference" id="priority-4-order-history-statuses-and-operational-reference"></a>

Order validation should prove that historical orders remain useful, not only that order IDs were created. VirtueMart order records can involve customers, addresses, products, line items, custom-field selections, quantities, prices, discounts, taxes, shipment methods, payment methods, currencies, comments, order statuses, invoices, and plugin-provided references.

#### What to validate <a href="#what-to-validate-3" id="what-to-validate-3"></a>

Validate line items, product references, selected options or child products, quantities, totals, tax amounts, shipment charges, payment references, coupon or discount context, billing and shipping addresses, order statuses, status history, order comments, and invoice-related expectations. Confirm whether historical order information remains readable enough for customer service and finance review.

If the source store used custom order statuses, external fulfillment references, payment gateway metadata, or plugin-owned shipment data, those details should be reviewed carefully. Some information may need configuration review, Add-on review, or Custom Service review rather than ordinary record validation.

#### Strong validation samples <a href="#strong-validation-samples-3" id="strong-validation-samples-3"></a>

A good order sample includes a simple order, a multi-product order, an order with child products or custom fields, an order with a coupon or discount, an order with tax, an order with shipment charges, an order with a gateway payment reference, an order with a changed status, a refunded or cancelled order if relevant, and an order from an important customer group.

#### What often gets missed <a href="#what-often-gets-missed-3" id="what-often-gets-missed-3"></a>

Merchants often check order totals but miss how the total was created. Tax lines, discount lines, shipment charges, payment method names, status history, comments, invoice context, and product-option selections should be reviewed because they determine whether old orders remain useful after launch.

### Priority 5: Calculation Rules, Tax, Discount, Payment, and Shipment Context <a href="#priority-5-calculation-rules-tax-discount-payment-and-shipment-context" id="priority-5-calculation-rules-tax-discount-payment-and-shipment-context"></a>

VirtueMart calculation rules can shape taxes, discounts, pricing behavior, and shopper-group-specific outcomes. Payment and shipment methods can also carry restrictions, fees, countries, currencies, shopper group conditions, plugin settings, and operational meaning.

#### What to validate <a href="#what-to-validate-4" id="what-to-validate-4"></a>

Validate whether tax and discount meaning is readable in migrated records and whether target rules are configured to support future transactions. Review country, state, region, currency, shopper group, shipment, and payment assumptions. Confirm whether payment and shipment method names remain meaningful for historical orders, even when live gateway or carrier behavior must be configured separately in VirtueMart.

Validation should separate historical reference from live operating behavior. Migrated data may preserve useful order context, while tax rules, shipment methods, payment gateways, and checkout behavior still require configuration in the target store.

#### Strong validation samples <a href="#strong-validation-samples-4" id="strong-validation-samples-4"></a>

Include orders with different tax outcomes, discounts, coupons, shipment methods, payment methods, currencies, customer groups, and geographic regions. Include at least one order where payment or shipment context affects customer service or accounting reference.

#### What often gets missed <a href="#what-often-gets-missed-4" id="what-often-gets-missed-4"></a>

The most common gap is assuming migrated historical records prove that live checkout is configured. A historical payment method appearing in an order does not prove the payment gateway is ready for new transactions. A shipment label or charge in an old order does not prove live shipping rules are configured correctly.

### Priority 6: Multilingual, Multicurrency, and Regional Behavior <a href="#priority-6-multilingual-multicurrency-and-regional-behavior" id="priority-6-multilingual-multicurrency-and-regional-behavior"></a>

VirtueMart stores may depend on multilingual content, translated product fields, translated categories, translated custom fields, multiple currencies, country and region rules, and localized storefront presentation. These areas should be validated with representative examples rather than assumed from the default language.

#### What to validate <a href="#what-to-validate-5" id="what-to-validate-5"></a>

Validate product names, descriptions, categories, custom field labels, manufacturer context, menu items, modules, metadata, currency display, pricing context, checkout language, and regional tax or shipment assumptions. Confirm whether translated values are present where they are expected and whether default-language fallback behavior is acceptable.

#### Strong validation samples <a href="#strong-validation-samples-5" id="strong-validation-samples-5"></a>

Use at least one product, category, custom field, customer-facing module, menu path, and order context in each important language or currency. If the store uses region-sensitive tax or shipment rules, validate records from those regions as well.

#### What often gets missed <a href="#what-often-gets-missed-5" id="what-often-gets-missed-5"></a>

Many migration reviews validate only the default language. That can hide missing translated descriptions, untranslated custom field labels, broken menu paths, incorrect currency display, or inconsistent checkout text. Multilingual validation should include storefront behavior, not only administration records.

### Priority 7: Joomla Storefront, Routes, Templates, and Modules <a href="#priority-7-joomla-storefront-routes-templates-and-modules" id="priority-7-joomla-storefront-routes-templates-and-modules"></a>

VirtueMart sits inside Joomla, so storefront validation must include Joomla structure. Products and categories may exist correctly while menus, modules, templates, layout overrides, aliases, metadata, redirects, and SEO-sensitive routes still need review.

#### What to validate <a href="#what-to-validate-6" id="what-to-validate-6"></a>

Validate key product pages, category pages, search/discovery paths, module positions, menu items, breadcrumbs, aliases, metadata, canonical assumptions, redirects, mobile rendering, template overrides, and checkout/account routes. If the target store uses custom templates or VirtueMart overrides, check whether migrated records render properly inside those layouts.

#### Strong validation samples <a href="#strong-validation-samples-6" id="strong-validation-samples-6"></a>

Choose high-traffic product URLs, category URLs, menu-driven landing pages, campaign pages, internal links, product modules, category modules, cart/checkout paths, and account pages. Include both desktop and mobile checks when storefront experience matters.

#### What often gets missed <a href="#what-often-gets-missed-6" id="what-often-gets-missed-6"></a>

Storefront validation often stops inside the VirtueMart administration area. That is not enough. A launch-ready migration should prove that shoppers can find products, view correct information, select the right product configuration, move through cart and checkout paths, and return to account or order areas without route or layout confusion.

### Priority 8: Custom Extensions, Custom Platform Sources, and External Identifiers <a href="#priority-8-custom-extensions-custom-platform-sources-and-external-identifiers" id="priority-8-custom-extensions-custom-platform-sources-and-external-identifiers"></a>

Custom extensions, modified VirtueMart behavior, custom Joomla development, external databases, ERP systems, fulfillment systems, marketplace connectors, or third-party payment and shipment data can carry meaning that is not visible in ordinary exports. These areas require explicit validation when they affect the expected target result.

#### What to validate <a href="#what-to-validate-7" id="what-to-validate-7"></a>

Validate whether custom fields, custom tables, extension-owned records, external IDs, ERP references, fulfillment references, gateway metadata, custom order states, custom checkout fields, and bespoke product logic are included, excluded, mapped, or reserved for Custom Service review. Do not assume unsupported data is covered by standard migration unless the selected migration path and final service plan confirm it.

#### Strong validation samples <a href="#strong-validation-samples-7" id="strong-validation-samples-7"></a>

Select records that depend on external systems or custom behavior. Good samples include products updated by integrations, orders sent to fulfillment systems, customers linked to external identifiers, products with custom tables, and orders with gateway or carrier references that the merchant needs after launch.

#### What often gets missed <a href="#what-often-gets-missed-7" id="what-often-gets-missed-7"></a>

Custom data can remain invisible until after launch. A product, customer, or order may look correct while missing the external identifier that a warehouse, ERP, or support process depends on. Validation should identify these dependencies before Full Migration.

### What Makes a Strong Validation Sample <a href="#what-makes-a-strong-validation-sample" id="what-makes-a-strong-validation-sample"></a>

A strong validation sample is not random. It represents the store’s real complexity and exposes the migration questions that could affect launch readiness.

| Sample type                                            | Why it matters in VirtueMart validation                                                        |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| High-revenue products                                  | Proves that important catalog records are accurate and sellable.                               |
| Parent/child products                                  | Tests product relationship logic, variant meaning, pricing, stock, and media behavior.         |
| Custom-field products                                  | Shows whether display, pricing, selection, or plugin-driven product meaning remains intact.    |
| Shopper-group customers                                | Tests customer segmentation, pricing context, tax assumptions, and order relationships.        |
| Orders with tax, discounts, payment, and shipment data | Proves whether historical records remain useful for support and finance review.                |
| Multilingual or multicurrency examples                 | Shows whether language, currency, and regional assumptions survive migration.                  |
| Joomla storefront paths                                | Tests menus, modules, templates, routes, aliases, metadata, redirects, and shopper navigation. |
| Custom or integration-dependent records                | Identifies whether Add-on review or Custom Service review is needed before Full Migration.     |

The sample should include both ordinary and difficult records. Ordinary records prove the baseline. Difficult records reveal whether the migration approach can support the store’s real operating model.

### What Often Gets Missed <a href="#what-often-gets-missed-8" id="what-often-gets-missed-8"></a>

Several gaps appear repeatedly in VirtueMart validation. They do not always show up in record counts, but they can affect launch quality.

Common missed areas include custom field behavior, parent/child relationship meaning, shopper group assignment, shopper fields, calculation rules, order status meaning, payment and shipment references, invoice context, multilingual labels, currency display, Joomla menu routes, module output, template overrides, and extension-owned data.

Validation also fails when configuration and migration are confused. Migrated data can preserve historical reference, but live checkout, payment gateways, shipment rules, tax rules, email behavior, and storefront presentation often still require target-side configuration.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation results should be classified by the kind of action required before launch.

| Result category             | What it means                                                                                                                            | Recommended action                                                             |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Pass                        | The sample behaves correctly and supports the expected migration outcome.                                                                | Continue validation with other representative samples.                         |
| Needs configuration review  | The data is present, but target settings, templates, routes, tax, shipment, payment, or checkout behavior need review.                   | Adjust VirtueMart or Joomla configuration before judging the migration result. |
| Needs data cleanup          | Source data quality problems are affecting the migrated result.                                                                          | Clean the source data or adjust the migration scope before Full Migration.     |
| Needs Add-on review         | Supported filtering, mapping, or configuration needs may require a Standard Add-on.                                                      | Review Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure.  |
| Needs Custom Service review | Custom Platform data, unsupported extension data, bespoke logic, external identifiers, or custom migration logic adjustment is involved. | Review Custom Service before Full Migration.                                   |
| Not launch-ready            | The result does not preserve essential operating meaning or storefront behavior.                                                         | Do not proceed to launch until the underlying issue is resolved.               |

A failed validation sample should not automatically be treated as a migration failure. Some issues indicate configuration gaps, source data quality problems, unsupported custom data, or service-path mismatch. The correct response depends on the type of issue found.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VirtueMart validation should prove that migrated data still supports selling, administration, customer service, order review, storefront navigation, and launch planning. The most important checks are usually product relationships, custom fields, shopper groups, calculation rules, payment and shipment context, multilingual behavior, Joomla routes, template output, and custom extension data.

Use Demo Migration and post-migration review to test the records that carry the most business meaning, not only the easiest records to count. If validation shows that parent/child products, custom fields, shopper groups, calculation rules, multilingual records, storefront routes, or extension-owned data require deeper handling, contact Next-Cart through Live Chat before Full Migration so the right Standard Service, Managed Service, Custom Service, and Add-on boundaries can be confirmed.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first after migrating to VirtueMart?**

Start with products, product relationships, customers, orders, shopper groups, calculation rules, payment and shipment context, and key storefront routes. These areas show whether the migration preserved operating meaning rather than only record presence.

**Why are VirtueMart custom fields important during validation?**

Custom fields can affect display, product selection, pricing, child-product behavior, plugin logic, or shopper-facing information. They should be validated according to their business purpose, not treated as generic notes.

**Should historical VirtueMart orders be tested beyond totals?**

Yes. Order totals are only part of validation. Line items, selected options, customer references, taxes, discounts, shipment details, payment method context, statuses, comments, and invoice expectations should also be reviewed.

**How should multilingual VirtueMart data be validated?**

Validate important products, categories, custom field labels, menu paths, modules, metadata, currency display, and checkout text in each important language. Default-language validation alone can miss gaps in translated storefront behavior.

**What happens if validation finds custom extension data that did not migrate as expected?**

Custom extension data should be reviewed before Full Migration. If the expected result requires unsupported extension handling, external identifiers, bespoke transformation, or custom migration logic adjustment, Custom Service should be reviewed.
