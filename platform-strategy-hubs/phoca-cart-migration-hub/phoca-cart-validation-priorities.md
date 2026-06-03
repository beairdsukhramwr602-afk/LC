# Phoca Cart Validation Priorities

Phoca Cart validation should prove that the migrated store works as a Joomla-based e-commerce system, not only that, but also that records appear in the administration area. Products must remain sellable, categories must support discovery, customer and order records must remain useful, and configuration-sensitive behavior should match the intended Phoca Cart setup.

Phoca Cart 6.1.0 is the current official stable release, so validation should normally be planned against that release when it is the Target Platform. Older Phoca Cart installations may remain operational when their Joomla environment and extension stack still function, but their behavior should be checked against the exact version used in the migration project. A result that is valid for Phoca Cart 6.1.0 should not be assumed to apply automatically to every legacy installation.

### What Validation Should Prove in a Phoca Cart Migration <a href="#what-validation-should-prove-in-a-phoca-cart-migration" id="what-validation-should-prove-in-a-phoca-cart-migration"></a>

A strong validation process confirms whether migrated records preserve commercial meaning inside Phoca Cart, Joomla, and the surrounding extension environment. The validation effort should cover both data and behavior: product selection, price display, stock logic, cart behavior, tax calculation, shipping selection, payment flow, invoice context, customer group treatment, multilingual presentation, and storefront navigation.

The goal is not to check every record manually. The goal is to choose samples that reveal whether important structures survived the migration and whether configuration work is still required before launch.

| Validation area                  | What the result should prove                                                                                                            | Why it matters                                                                                                            |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure                | Products, categories, manufacturers, attributes, specifications, parameters, images, and downloads remain meaningful.                   | Shoppers must be able to understand and select products, while merchants must be able to manage the catalog after launch. |
| Pricing and customer benefits    | Prices, discounts, coupons, reward points, customer group prices, and related benefits behave as intended.                              | Commercial rules affect conversion, customer trust, and post-launch support.                                              |
| Orders and customers             | Customer profiles, addresses, order items, totals, statuses, tax, shipping, payment context, and invoice references remain readable.    | Historical data must support service, accounting reference, repeat buying, and operational continuity.                    |
| Storefront and Joomla context    | Menus, modules, templates, category pages, product pages, checkout paths, search, and route behavior align with the future Joomla site. | Correct data can still fail if shoppers cannot find or complete purchases.                                                |
| Configuration-sensitive behavior | Tax, shipping, payment, stock, multilingual, multicurrency, and checkout settings are reviewed against the target configuration.        | Many outcomes depend on settings and plugins, not migrated records alone.                                                 |

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

#### Validate representative product types <a href="#validate-representative-product-types" id="validate-representative-product-types"></a>

Product validation should begin with records that represent the actual catalog, not only the simplest products. A good sample should include standard products, products with attributes or options, products with specifications, products with multiple images, products assigned to important categories, digital products, discounted products, products with customer group price differences, and products with meaningful stock behavior.

Each sample should answer practical questions. Can the shopper identify the product? Are the name, alias, description, image, price, tax display, stock status, and purchasing controls correct? Does the product appear in the right category and module context? Does the product behave correctly when added to the cart?

#### Validate attributes, options, specifications, and parameters separately <a href="#validate-attributes-options-specifications-and-parameters-separately" id="validate-attributes-options-specifications-and-parameters-separately"></a>

Phoca Cart catalog meaning can involve several product-detail layers. Attributes and options may support shopper choice or commercial configuration. Specifications and parameters may support comparison, filtering, display, or structured product information. Treating these layers as the same thing can produce a store that looks complete but loses important buying context.

Validation should confirm whether each layer is visible, usable, and assigned to the correct products. For example, a product option that affects price or selection should not be validated only as descriptive text. A specification used for product comparison should not be validated only by checking the product edit screen. Filtered category pages, product detail pages, comparison behavior, and module output may all reveal problems that are not obvious from record counts.

#### Validate stock and downloadable products <a href="#validate-stock-and-downloadable-products" id="validate-stock-and-downloadable-products"></a>

Stock validation should include products with available stock, low stock, out-of-stock behavior, and any products where stock should affect purchasing. If stock calculation depends on attributes, options, or product variations, validation should include those combinations rather than only the parent product.

For digital or downloadable products, validation should confirm whether the product remains purchasable, whether download-related information is preserved where supported, and whether customer access expectations are realistic after migration. Download behavior often combines data, configuration, access, and order status, so it should not be treated as a simple product field.

### Customer, Order, and Commercial Rule Validation <a href="#customer-order-and-commercial-rule-validation" id="customer-order-and-commercial-rule-validation"></a>

#### Validate customer groups and customer benefits <a href="#validate-customer-groups-and-customer-benefits" id="validate-customer-groups-and-customer-benefits"></a>

Customer group behavior deserves specific validation because it can affect prices, discounts, reward points, tax handling, access, and purchasing experience. A migrated customer may look correct but still belong to the wrong group or lose the commercial treatment that mattered in the source store.

Validation should include customers from different groups, customers with historical orders, customers with different billing or shipping addresses, and customers affected by customer group prices or reward points. The result should show whether customer data can support future service and whether the shopper experience reflects the intended business rules.

#### Validate order history beyond totals <a href="#validate-order-history-beyond-totals" id="validate-order-history-beyond-totals"></a>

Order validation should not stop at order number, date, and total. A useful Phoca Cart order record should preserve enough context to support customer service, accounting review, fulfillment questions, and internal reference.

Strong samples include orders with multiple products, products with options or attributes, discounts, coupons, reward points, taxes, shipping charges, different payment methods, different order statuses, refunds or cancellations if present, and customer group effects. Order line items should still show what was purchased, how it was priced, which tax and shipping context applied, and whether the historical status remains understandable.

#### Validate coupons, discounts, reward points, and pricing rules <a href="#validate-coupons-discounts-reward-points-and-pricing-rules" id="validate-coupons-discounts-reward-points-and-pricing-rules"></a>

Discount behavior can be difficult to validate from static records alone. Coupons, discounts, customer group prices, reward points, specials, and other pricing rules should be tested through both administration review and storefront/cart behavior where applicable.

A discount that appears in the administration area but does not behave correctly in the cart is not launch-ready. A migrated coupon that works for the wrong customer group, currency, product, or date range may create business risk. Validation should distinguish between migrated historical discount data and active promotional rules that must be configured or reviewed before launch.

### Tax, Shipping, Payment, and Checkout Validation <a href="#tax-shipping-payment-and-checkout-validation" id="tax-shipping-payment-and-checkout-validation"></a>

#### Validate tax and regional behavior <a href="#validate-tax-and-regional-behavior" id="validate-tax-and-regional-behavior"></a>

Tax validation should include representative locations, tax rates, tax classes, product types, customer groups, billing addresses, shipping addresses, and any regions that matter commercially. Phoca Cart tax behavior may depend on configuration as much as data, especially when the store uses country, zone, geo-zone, customer group, or product-specific rules.

Validation should prove whether expected tax appears in the cart, checkout, order detail, invoice, and order history context. Where the source store used custom or third-party tax behavior, the result may need configuration review or Custom Service review rather than ordinary validation sign-off.

#### Validate shipping and payment plugins <a href="#validate-shipping-and-payment-plugins" id="validate-shipping-and-payment-plugins"></a>

Shipping and payment validation should focus on the methods that will be used after launch, not every theoretical method available to Phoca Cart. Each selected method should be checked for availability, display name, restrictions, price behavior, tax interaction, and order-status effect.

Shipping samples should include different order weights, prices, destinations, product types, and customer groups where those factors affect availability or rates. Payment samples should include the expected checkout flow, payment status, order status, customer-facing messages, and any transaction reference behavior that matters after migration.

#### Validate checkout and account paths <a href="#validate-checkout-and-account-paths" id="validate-checkout-and-account-paths"></a>

Checkout validation should confirm that the path from product page to cart to checkout to order completion works for the intended shopper profiles. Guest checkout, registered customer checkout, customer group behavior, billing/shipping address handling, coupon application, payment method selection, shipping method selection, and confirmation messaging should all be checked.

If the store uses custom checkout fields, account fields, privacy consent behavior, or special order messages, those items should be validated separately. Some fields may be migrated as data, while others may need configuration in the target Phoca Cart installation.

### Storefront, Joomla, and Presentation Validation <a href="#storefront-joomla-and-presentation-validation" id="storefront-joomla-and-presentation-validation"></a>

#### Validate menus, modules, templates, and routes <a href="#validate-menus-modules-templates-and-routes" id="validate-menus-modules-templates-and-routes"></a>

Phoca Cart operates inside Joomla, so storefront validation should include the Joomla layer. Product pages, category pages, manufacturer pages, cart pages, checkout pages, account pages, modules, menus, templates, and internal links should be reviewed as part of the migration result.

Validation should include high-traffic routes, important category paths, campaign landing pages, product URLs, internal links, and navigation elements that shoppers rely on. If the source store had strong organic search visibility, metadata, aliases, canonical behavior, structured data, and redirects should be reviewed before launch.

#### Validate multilingual and multicurrency behavior <a href="#validate-multilingual-and-multicurrency-behavior" id="validate-multilingual-and-multicurrency-behavior"></a>

Multilingual and multicurrency validation should use real shopper paths rather than isolated field checks. Translated product names, category names, labels, checkout messages, emails, modules, menus, and currency display should be reviewed in combination.

A product may look correct in the default language but fail in a translated storefront. A currency may display correctly on a product page but not in the cart, checkout, invoice, or order history. Representative samples should include products, categories, cart behavior, checkout, order confirmation, and customer account views in each important language or currency.

#### Validate invoices, emails, and operational output <a href="#validate-invoices-emails-and-operational-output" id="validate-invoices-emails-and-operational-output"></a>

Invoice, email, and operational output validation should confirm whether the store can communicate and document orders correctly. Phoca Cart can be used in environments where invoices, order emails, customer messages, and administrative notifications matter for daily operations.

Validation should check whether customer-facing and merchant-facing messages include the right order details, totals, tax, shipping, payment method, customer data, and language where relevant. If the source store used heavily customized emails or invoice templates, those should be treated as implementation items rather than assumed migration outputs.

### What Makes a Strong Validation Sample <a href="#what-makes-a-strong-validation-sample" id="what-makes-a-strong-validation-sample"></a>

A strong validation sample includes records that expose business meaning. It should not be limited to the newest records, the cleanest records, or the products easiest to migrate.

| Sample type                                                        | Why it should be included                                                                 |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Simple product                                                     | Confirms baseline product creation, price, image, category, and add-to-cart behavior.     |
| Attribute- or option-heavy product                                 | Tests shopper selection, price changes, stock behavior, and order line meaning.           |
| Digital or downloadable product                                    | Reveals whether access and post-purchase expectations are realistic.                      |
| Product with customer group price or reward behavior               | Confirms commercial rules tied to customer identity.                                      |
| Product in multiple categories or modules                          | Tests storefront discovery and Joomla presentation context.                               |
| Order with tax, shipping, payment, discount, and status complexity | Confirms whether historical orders remain operationally useful.                           |
| Customer from a non-default group                                  | Tests customer segmentation, price visibility, and account behavior.                      |
| Multilingual or multicurrency record                               | Reveals whether translation and currency behavior remain consistent beyond default views. |
| Legacy Phoca Cart record                                           | Checks whether older operational versions require version-specific interpretation.        |
| Custom or extension-owned record                                   | Identifies whether Add-on review or Custom Service review is needed.                      |

### What Often Gets Missed <a href="#what-often-gets-missed" id="what-often-gets-missed"></a>

Migration review often fails when validation is limited to administration record counts. In a Phoca Cart migration, important problems may appear only after the product is opened on the storefront, added to the cart, combined with a customer group, viewed in a translated language, checked against a currency, or tested through a shipping and payment flow.

Common misses include option-level price changes, missing product images, misassigned customer groups, inactive coupons, incorrect reward behavior, tax rules that apply in the wrong region, shipping methods hidden from valid orders, payment methods that produce unexpected statuses, broken Joomla routes, module output that does not match the catalog, and invoice/email templates that do not reflect the final order correctly.

Older Phoca Cart installations add another layer of validation risk. A legacy source or target may contain data structures, customizations, template overrides, or extensions that do not behave like Phoca Cart 6.1.0. Version-specific evidence should be reviewed before treating a result as launch-ready.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation should lead to an action, not only a pass/fail label. A failed sample may mean the source data needs cleanup, the target store needs configuration, an Add-on should be reviewed, Custom Service is required, or the launch should be paused until a structural issue is resolved.

| Result category             | Meaning                                                                                                                                   | Recommended action                                                                           |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Pass                        | The sample preserves business meaning and behaves correctly in the target Phoca Cart environment.                                         | Approve the sample and include similar records in broader review.                            |
| Needs configuration review  | The data is present, but tax, shipping, payment, checkout, multilingual, storefront, or module behavior depends on target configuration.  | Adjust Phoca Cart or Joomla settings, then retest the affected samples.                      |
| Needs data cleanup          | Source records are inconsistent, incomplete, duplicated, or commercially unclear.                                                         | Clean source data or define the intended target treatment before Full Migration.             |
| Needs Add-on review         | Filtering, mapping, or configuration needs may fit an available Add-on.                                                                   | Review Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure as appropriate. |
| Needs Custom Service review | Custom Platform data, unsupported extension data, custom fields, legacy structures, or bespoke transformation affect the expected result. | Review the migration path through Custom Service before proceeding.                          |
| Not launch-ready            | The result would create shopper confusion, order risk, operational gaps, or incorrect commercial behavior.                                | Pause launch planning until the issue is corrected and revalidated.                          |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Phoca Cart validation should prove that migrated data works inside the chosen Joomla and Phoca Cart environment. A record that appears in the administration area is not enough. Products must be understandable, options and attributes must support buying decisions, categories and modules must support discovery, customer and order records must remain useful, and tax, shipping, payment, invoice, email, multilingual, and storefront behavior must be reviewed against the target configuration.

Phoca Cart 6.1.0 should be used as the reference point for current release behavior when it is the intended Target Platform. Older operational installations should be validated according to their exact Phoca Cart version, Joomla version, template layer, extension stack, and customizations.

Use Demo Migration results to validate representative products, customers, orders, customer groups, commercial rules, storefront paths, and configuration-sensitive behavior before Full Migration. If validation reveals unsupported extension data, custom fields, legacy structures, Custom Platform source data, or bespoke transformation needs, review the migration path through Live Chat before treating the store as launch-ready.

### FAQs <a href="#faqs" id="faqs"></a>

**Why is Phoca Cart validation more than checking record counts?**

Phoca Cart operates inside Joomla and depends on catalog structure, customer groups, cart behavior, tax, shipping, payment, modules, templates, and configuration. Record counts can confirm that data moved, but they do not prove that products are sellable, orders are useful, or the storefront works correctly.

**Which products should be selected for Demo Migration validation?**

Use products that reveal structure: simple products, option-heavy products, products with attributes or specifications, downloadable products, discounted products, products with customer group prices, products with stock behavior, and products assigned to important categories or modules.

**Should older Phoca Cart versions be validated differently?**

Yes. Older Phoca Cart installations may still operate when their Joomla version and extension stack remain functional, but their behavior may not match Phoca Cart 6.1.0. Validation should confirm the exact Phoca Cart version, Joomla version, template layer, extensions, and customizations involved.

**What should be checked in order validation?**

Order validation should include line items, selected options, quantities, totals, discounts, coupons, reward points, tax, shipping, payment context, order statuses, customer details, invoice references, and any comments or historical fields needed for customer service and operations.

**When should validation trigger Custom Service review?**

Custom Service should be reviewed when validation reveals Custom Platform source data, unsupported extension data, custom fields, bespoke product logic, legacy version differences, third-party identifiers, custom Joomla development, Tailored Add-ons, Custom Add-ons, or any transformation that requires custom migration logic adjustment.
