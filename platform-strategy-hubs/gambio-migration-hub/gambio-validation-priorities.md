# Gambio Validation Priorities

Validation in a Gambio migration should prove that the migrated store works as a usable Gambio shop, not only that records appear in the administration area. Products should remain understandable to shoppers. Product options and variants should preserve buying meaning. Categories, filters, images, stock, downloadable products, reviews, and customer groups should support the way the business actually sells. Orders should remain useful for service and accounting reference. Storefront pages, SEO-sensitive paths, content areas, payment methods, shipping rules, taxes, languages, currencies, and integrations should align with the future Gambio operating model.

Gambio validation is especially important because the platform can be used in different operating models. A Gambio Cloud migration may place more emphasis on confirming data, settings, storefront readiness, and standard configuration. A self-hosted Gambio migration may also require deeper review of hosting, updates, extensions, custom code, theme behavior, and integration dependencies. The validation process should separate migrated data issues from Gambio configuration work, storefront implementation work, Add-on review, and Custom Service needs.

### What Validation Is Trying to Prove <a href="#what-validation-is-trying-to-prove" id="what-validation-is-trying-to-prove"></a>

A strong Gambio validation process answers three practical questions.

First, it checks whether source data has become meaningful inside Gambio. A product with variants should not only exist; its shopper-facing selections, prices, images, stock behavior, and order-line meaning should still make sense. A customer group should not only appear; it should support the pricing, B2B, tax, visibility, or segmentation assumptions the merchant expects.

Second, validation checks whether configuration-sensitive behavior is ready for launch. Payment methods, shipping rules, taxes, currencies, languages, order statuses, invoices, delivery notes, stock behavior, legal-display settings, and SEO settings may require target-side setup. These areas should not be mistaken for ordinary record migration.

Third, validation checks whether the Gambio implementation can support the storefront experience. Category pages, product pages, content pages, navigation, metadata, redirects, theme behavior, StyleEdit work, integrations, and custom modules may affect whether the migrated store is actually usable.

### Priority 1: Product and Catalog Structure <a href="#priority-1-product-and-catalog-structure" id="priority-1-product-and-catalog-structure"></a>

Product validation should begin with catalog meaning. A migrated Gambio product should preserve the information shoppers need to understand, compare, and purchase the item, while also preserving the information the merchant needs to manage it after launch.

#### What to validate <a href="#what-to-validate" id="what-to-validate"></a>

Review product names, descriptions, SKUs, prices, tax-related fields, images, categories, manufacturers, stock behavior, product status, special pricing, downloadable product behavior, reviews, and related products where relevant. Products should be checked in both the Gambio administration area and the customer-facing storefront.

For stores with larger catalogs, do not validate only the first few products. Choose products that represent the real structure of the source store: simple products, option-heavy products, products with several images, products in multiple categories, downloadable products, products with stock limits, discounted products, high-revenue products, and products that historically created support questions.

#### Strong validation samples <a href="#strong-validation-samples" id="strong-validation-samples"></a>

A strong product sample should include at least one product from each important catalog pattern. If the store sells apparel, choose products with size, color, image, and stock variation. If the store sells spare parts, choose products with model numbers, manufacturer relationships, technical attributes, and compatibility-related descriptions. If the store sells downloads, choose downloadable products and verify that the migrated result can support the expected purchasing and access workflow.

#### What often gets missed <a href="#what-often-gets-missed" id="what-often-gets-missed"></a>

Merchants often validate product presence but miss product usability. A product can appear in Gambio and still be weak if images are incomplete, categories are confusing, option selections do not match the source meaning, prices are not aligned, stock behavior is unclear, downloadable files are not reviewed, or product discovery depends on filters and attributes that were not checked.

### Priority 2: Product Options, Variants, Attributes, and Filters <a href="#priority-2-product-options-variants-attributes-and-filters" id="priority-2-product-options-variants-attributes-and-filters"></a>

Product options and attributes deserve separate validation because they can look similar in source data while serving different commercial roles inside the target store. Options and variants usually affect shopper selection and order line meaning. Attributes and filters often support comparison, discovery, specifications, or product information.

#### What to validate <a href="#what-to-validate-1" id="what-to-validate-1"></a>

Check whether product options preserve the shopper-facing choices from the source store. Review option names, option values, required selections, price adjustments, stock implications, image expectations, SKU/model relationships, and how the chosen option appears in the order. Then validate attributes and filters separately by checking whether they help shoppers compare and discover products in category and search contexts.

| Validation area        | What to prove                                                                                       | Why it matters                                                     |
| ---------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Product options        | Shopper selections, required choices, option values, and price or stock effects are understandable. | Options affect purchase decisions and order-line meaning.          |
| Variants               | Size, color, package, model, or other variant structures preserve commercial meaning.               | Variants often control what the customer actually buys.            |
| Attributes             | Specifications, product facts, and comparison details remain readable.                              | Attributes support understanding and product comparison.           |
| Filters                | Category and product-discovery filters guide shoppers correctly.                                    | Filters affect how customers find products after launch.           |
| Order line option data | Orders show the purchased option or variant clearly.                                                | Customer service and fulfillment depend on readable order details. |

#### Strong validation samples <a href="#strong-validation-samples-1" id="strong-validation-samples-1"></a>

Choose products where options influence price, stock, image, shipping, or order fulfillment. Also choose products with attributes that matter for customer comparison, such as dimensions, material, compatibility, technical details, brand, or product type. If source options were created through a third-party app, custom field, or modified structure, include those products in Demo Migration validation and treat unclear results as a possible Add-on or Custom Service review signal.

#### What often gets missed <a href="#what-often-gets-missed-1" id="what-often-gets-missed-1"></a>

A frequent validation mistake is treating visible product choices as proof that option migration is complete. The stronger test is whether the choice works from product page to checkout to order history. If a customer selects a size or color, the storefront, basket, checkout, order confirmation, and order history should all preserve enough meaning for the merchant to fulfill the order correctly.

### Priority 3: Categories, Navigation, SEO, and Storefront Discovery <a href="#priority-3-categories-navigation-seo-and-storefront-discovery" id="priority-3-categories-navigation-seo-and-storefront-discovery"></a>

Gambio validation should test how shoppers find products, not only whether products exist. Category structure, filters, product placement, SEO URLs, redirects, metadata, content pages, navigation, and theme presentation can affect traffic, conversion, and customer trust after launch.

#### What to validate <a href="#what-to-validate-2" id="what-to-validate-2"></a>

Review the main category tree, product placement inside categories, category descriptions, metadata, high-value product URLs, important content pages, redirects, internal links, and storefront navigation. If the source store had strong organic search traffic, paid campaign landing pages, affiliate URLs, or bookmarked product pages, those paths should be checked carefully.

#### Strong validation samples <a href="#strong-validation-samples-2" id="strong-validation-samples-2"></a>

Use the store’s highest-traffic categories, highest-revenue products, important brand/manufacturer pages, landing pages, and content pages as validation samples. Also include deeper category pages and products that are not obvious from the main menu. A migration can appear correct when only top-level pages are reviewed, while deeper product discovery remains broken.

#### What often gets missed <a href="#what-often-gets-missed-2" id="what-often-gets-missed-2"></a>

Merchants often validate only administrative category records. In Gambio, the practical validation question is whether the customer-facing journey works. A category should have the right products, readable content, correct page behavior, useful filters, sensible metadata, and a route strategy that supports SEO continuity.

### Priority 4: Customer Groups, Customers, and Account Meaning <a href="#priority-4-customer-groups-customers-and-account-meaning" id="priority-4-customer-groups-customers-and-account-meaning"></a>

Customer validation should confirm that customer records are useful inside the future Gambio store. For simple B2C stores, this may mean names, email addresses, addresses, and order relationships. For B2B or segmented stores, validation must also include customer groups, pricing expectations, tax handling, account history, and buyer identity.

#### What to validate <a href="#what-to-validate-3" id="what-to-validate-3"></a>

Check customer names, emails, billing addresses, shipping addresses, account status, customer group assignment, order relationships, and any segmentation that affects pricing or service. If the source store used guest checkout, account approval, wholesale groups, tax-exempt customers, dealer pricing, or country-specific customer handling, select samples that reveal those structures.

#### Strong validation samples <a href="#strong-validation-samples-3" id="strong-validation-samples-3"></a>

A strong sample includes ordinary retail customers, repeat customers, customers with multiple addresses, B2B or wholesale customers, customers from different countries or tax regions, and customers connected to important order history. If customer groups affect pricing or visibility, test those groups with products that depend on the rule.

#### What often gets missed <a href="#what-often-gets-missed-3" id="what-often-gets-missed-3"></a>

A customer record may look correct while its commercial context is missing. If customer group assignment, price visibility, tax handling, or order relationship is wrong, the migrated customer data may be unreliable for support, repeat purchase, or B2B operations.

### Priority 5: Order History, Discounts, Tax, Shipping, and Payment Context <a href="#priority-5-order-history-discounts-tax-shipping-and-payment-context" id="priority-5-order-history-discounts-tax-shipping-and-payment-context"></a>

Order validation should prove that historical orders remain understandable. Gambio order history does not need to recreate every source-platform behavior, but it should preserve enough meaning for customer service, accounting reference, operational review, and merchant confidence.

#### What to validate <a href="#what-to-validate-4" id="what-to-validate-4"></a>

Review order numbers, customer relationships, billing and shipping addresses, purchased products, option selections, quantities, unit prices, totals, discounts, tax, shipping charges, payment method context, order statuses, comments, and historical timestamps. If the source store used marketplace orders, ERP references, fulfillment references, custom statuses, partial refunds, vouchers, or unusual discounts, include those in validation samples.

#### Strong validation samples <a href="#strong-validation-samples-4" id="strong-validation-samples-4"></a>

A useful order sample should include recent orders, older orders, orders with product options, orders from important customer groups, orders with discounts or coupons, orders with shipping and tax differences, cancelled or refunded orders if relevant, and orders that represent the merchant’s main operational patterns.

#### What often gets missed <a href="#what-often-gets-missed-4" id="what-often-gets-missed-4"></a>

Merchants often stop validation after checking order count and total value. That is not enough. A migrated order should tell a readable story: who bought, what they bought, which option they chose, what they paid, what discount or tax applied, how the order was shipped or paid, and what status the order carried.

### Priority 6: Configuration-Sensitive Store Behavior <a href="#priority-6-configuration-sensitive-store-behavior" id="priority-6-configuration-sensitive-store-behavior"></a>

Some Gambio behavior depends on configuration rather than migrated records. Validation should distinguish between a data issue and a setting that must be configured in the target environment.

#### What to validate <a href="#what-to-validate-5" id="what-to-validate-5"></a>

Review payment methods, shipping methods, tax classes, tax zones, currencies, languages, stock settings, order statuses, invoice and delivery-note expectations, legal-display settings, email behavior, and any required integrations. For Gambio Cloud, confirm what is handled by the cloud environment and what still requires merchant setup. For self-hosted Gambio, confirm hosting, update, extension, and compatibility expectations with the implementation team.

| Configuration area       | Validation question                                                         | Likely interpretation if incorrect                                              |
| ------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Payment methods          | Are expected payment methods available and configured?                      | Usually a target configuration or plugin setup issue.                           |
| Shipping rules           | Do shipping methods match zones, weights, prices, or business rules?        | May require configuration review or Custom Service if source logic is bespoke.  |
| Taxes                    | Do tax classes, rates, geo-zones, and customer contexts behave as expected? | Usually configuration review; custom tax logic may need deeper review.          |
| Languages and currencies | Are storefront labels, product content, and currency expectations coherent? | May require multilingual/multicurrency setup and source mapping review.         |
| Stock behavior           | Does stock availability match the merchant’s selling rules?                 | May require data cleanup, configuration review, or product-level sample review. |

#### Strong validation samples <a href="#strong-validation-samples-5" id="strong-validation-samples-5"></a>

Configuration samples should include orders from different tax or shipping zones, products with stock limits, customers from different groups, products with special prices, and transactions that depend on different payment or shipping methods. The goal is not to test every possible setting but to prove that the critical settings match the future operating model.

#### What often gets missed <a href="#what-often-gets-missed-5" id="what-often-gets-missed-5"></a>

A common mistake is expecting migrated data to solve configuration behavior. Payment setup, shipping setup, taxes, currencies, languages, email behavior, and legal-display settings may need post-migration configuration even when records migrated correctly.

### Priority 7: Storefront Design, Content Pages, and Implementation Context <a href="#priority-7-storefront-design-content-pages-and-implementation-context" id="priority-7-storefront-design-content-pages-and-implementation-context"></a>

Gambio storefront validation should include the visible store experience. Product and order data can migrate correctly while the storefront still requires layout, content, navigation, or SEO work.

#### What to validate <a href="#what-to-validate-6" id="what-to-validate-6"></a>

Review homepage entry paths, category pages, product pages, content pages, menu structure, footer links, product images, responsive behavior, StyleEdit or theme adjustments, content manager pages, metadata, internal links, and redirects. If the source store used custom templates, third-party modules, or self-hosted modifications, confirm whether those expectations belong to migration, implementation, or Custom Service review.

#### Strong validation samples <a href="#strong-validation-samples-6" id="strong-validation-samples-6"></a>

Choose pages that represent real customer journeys: homepage to category to product to checkout, content page to product, search result to product, brand/manufacturer page to product, and landing page to checkout. Also test mobile behavior where layout or image presentation matters.

#### What often gets missed <a href="#what-often-gets-missed-6" id="what-often-gets-missed-6"></a>

Merchants sometimes treat storefront appearance as separate from migration validation. It is separate from record migration, but not separate from launch readiness. The final store must connect migrated data with a working storefront experience.

### Priority 8: Integrations, Interfaces, and Customization Dependencies <a href="#priority-8-integrations-interfaces-and-customization-dependencies" id="priority-8-integrations-interfaces-and-customization-dependencies"></a>

Gambio may connect to external systems, marketplaces, payment providers, shipping services, ERP tools, analytics, email platforms, or custom modules. Validation should identify which dependencies are part of migration, which belong to target configuration, and which require implementation or Custom Service review.

#### What to validate <a href="#what-to-validate-7" id="what-to-validate-7"></a>

Review externally important identifiers, marketplace references, ERP product IDs, payment references, shipping references, custom fields, modified database structures, self-hosted custom code, and extension-owned data. Confirm whether those values are expected to migrate, remain in source records, be rebuilt through integration work, or be handled through Custom Service.

#### Strong validation samples <a href="#strong-validation-samples-7" id="strong-validation-samples-7"></a>

Select products, customers, and orders that depend on integrations. Include marketplace-origin orders, ERP-managed products, products with external IDs, shipping-automation examples, payment-provider examples, and records created by custom code or extensions.

#### What often gets missed <a href="#what-often-gets-missed-7" id="what-often-gets-missed-7"></a>

The most common integration validation failure is assuming that visible data proves operational continuity. A reference number may migrate, but the external workflow may not be recreated. Validation should focus on what the merchant actually needs after launch: searchable records, service reference, fulfillment continuity, integration rebuild, or custom transformation.

### What Makes a Strong Validation Sample <a href="#what-makes-a-strong-validation-sample" id="what-makes-a-strong-validation-sample"></a>

A strong validation sample is representative, not convenient. It should include records that reveal how the store really works.

For Gambio, the sample should include:

* simple products and option-heavy products
* products with multiple images, stock rules, special prices, reviews, or downloadable files
* categories that matter for navigation, filters, and SEO
* customers from important customer groups
* orders with different statuses, discounts, tax, shipping, payment, and product-option combinations
* content pages, high-value URLs, and storefront paths that affect traffic or conversion
* records with integration references, external identifiers, or source-specific custom fields
* multilingual or multicurrency examples where relevant

A weak sample tests only clean records. A strong sample tests the records most likely to expose the truth.

### What Often Gets Missed <a href="#what-often-gets-missed-8" id="what-often-gets-missed-8"></a>

The most common Gambio validation gaps are not caused by missing record counts. They are caused by incomplete interpretation.

Important missed areas include:

* product options that appear but do not preserve buying meaning
* attributes and filters that do not support product discovery
* customer groups that exist but do not support pricing or segmentation expectations
* orders that lack readable discount, tax, shipping, payment, or option context
* downloadable products that are not tested through the intended workflow
* SEO URLs, redirects, metadata, and content pages that are not reviewed
* payment, shipping, tax, language, currency, and legal-display settings assumed to be migrated behavior
* self-hosted customizations or integrations treated as ordinary data
* Cloud and self-hosted responsibilities treated as identical

These gaps should be classified before Full Migration. Some require data cleanup. Some require target configuration. Some require Add-on review. Some require Custom Service review.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation results should lead to a clear next action. They should not be treated as a vague pass/fail exercise.

| Result category             | What it means                                                                                                                                                                                                   | Recommended next action                                                                       |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Pass                        | The sampled records and behavior are correct enough for the expected migration stage.                                                                                                                           | Continue with the current migration plan.                                                     |
| Needs configuration review  | Data appears usable, but Gambio settings, plugins, shipping, payment, tax, language, currency, or storefront configuration need adjustment.                                                                     | Configure the target environment and retest the affected samples.                             |
| Needs data cleanup          | Source records contain duplication, missing values, unclear categories, weak product structure, or inconsistent order/customer data.                                                                            | Clean or clarify source data before relying on Full Migration results.                        |
| Needs Add-on review         | Filtering, mapping, or supported configuration needs are clear and may fit available Add-on capability.                                                                                                         | Review whether Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure applies. |
| Needs Custom Service review | The issue involves Custom Platform data, unsupported custom fields, extension-owned data, custom code, bespoke B2B rules, integrations, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment. | Review Custom Service scope before Full Migration.                                            |
| Not launch-ready            | The migrated result cannot yet support the expected store operation or customer experience.                                                                                                                     | Pause launch planning until the gap is resolved and retested.                                 |

This classification helps prevent overreaction. Not every validation issue means migration failure. Some issues are normal target setup work. Others reveal that the chosen migration approach is too light.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio validation should prove that the migrated store can operate reliably inside the chosen Gambio model. Products, options, categories, customer groups, orders, discounts, tax, shipping, payment context, content pages, SEO paths, storefront behavior, integrations, and hosting-model expectations should be tested as connected parts of the future store.

Use Demo Migration and post-migration review to separate data issues from configuration, implementation, Add-on, and Custom Service questions. If validation reveals unclear product options, customer-group rules, order meaning, storefront paths, integration dependencies, self-hosted customization, or Custom Platform source data, review the migration path through Live Chat before Full Migration or launch so the next action is clear.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first after migrating to Gambio?**

Start with products, product options, categories, customer groups, and representative orders. These areas usually reveal whether the migrated data preserves the store’s commercial meaning before deeper configuration or storefront review begins.

**Why are product options important in Gambio validation?**

Product options affect what shoppers choose and what merchants fulfill. They should be checked from the product page through checkout and order history so option names, values, pricing, stock, and order-line meaning remain understandable.

**Should Gambio configuration be validated separately from migrated data?**

Yes. Payment methods, shipping rules, tax behavior, languages, currencies, stock settings, legal-display settings, and storefront configuration may require target-side setup even when the migrated records are correct.

**How should customer groups be validated in a Gambio migration?**

Validate customer group assignment, pricing expectations, tax or B2B context, and order relationships. If customer groups affect commercial rules, test them with products and orders that depend on those rules.

**When should validation results lead to Custom Service review?**

Custom Service should be reviewed when validation issues involve Custom Platform data, unsupported custom fields, extension-owned data, self-hosted custom code, complex B2B rules, integration identifiers, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.
