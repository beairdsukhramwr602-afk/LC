# Phoca Cart Validation Priorities

Phoca Cart validation should prove that the migrated store works as a Joomla-native commerce environment, not only that records appear in the administration area. Products must remain sellable, categories must support discovery, customer and order records must remain useful, and configuration-sensitive behavior should match the target Phoca Cart setup.

The strongest validation process combines record review with behavior review. Product data, customer history, tax, shipping, payment, invoice context, storefront paths, modules, templates, languages, currencies, and extension-owned data should be checked together because Phoca Cart sits inside a Joomla site rather than outside it.

### What Validation Should Prove in a Phoca Cart Migration <a href="#what-validation-should-prove-in-a-phoca-cart-migration" id="what-validation-should-prove-in-a-phoca-cart-migration"></a>

Validation should confirm whether commercial meaning survived the migration. A complete product count is not enough if attributes no longer affect selection, specifications no longer support comparison, customer group prices are no longer clear, reward points are disconnected, or orders no longer show the business context behind totals.

Validation should also confirm whether the Joomla storefront can use the migrated records. Phoca Cart can rely on Joomla menus, modules, template overrides, plugins, aliases, access levels, languages, and layout decisions. A store can pass a database-level review while still failing the buying path.

| Validation area             | What should be proven                                                                                                                                              | Why it matters                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| Catalog structure           | Products, categories, manufacturers, attributes, options, specifications, images, downloadable products, stock behavior, and related products remain meaningful.   | Shoppers need clear product selection, and merchants need manageable catalog records after launch.    |
| Commercial rules            | Prices, discounts, coupons, reward points, cart discounts, customer group prices, tax treatment, shipping logic, and payment context can be interpreted correctly. | Revenue, trust, and support quality depend on more than product names and totals.                     |
| Customer and order history  | Customers, addresses, customer groups, order items, statuses, invoices, delivery notes, payment labels, shipping charges, and tax amounts remain readable.         | Historical records must support service, accounting reference, fulfillment review, and repeat buying. |
| Joomla storefront behavior  | Menus, aliases, category paths, product paths, modules, templates, template overrides, search, filters, and cart paths behave as expected.                         | Correct records still fail if shoppers cannot find or purchase products.                              |
| Localization and extensions | Languages, currencies, zones, custom plugins, modules, integrations, and custom data are identified and validated.                                                 | International and customized stores often fail in relationships that basic samples do not expose.     |

A useful validation result answers three questions: what works as expected, what needs configuration, and what requires a different service path before launch.

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

Product validation should begin with representative product types. Simple products are useful, but they rarely expose the full risk in a Phoca Cart migration. Samples should include products with attributes, options, specifications, images, downloads, stock rules, discounts, customer group prices, manufacturers, related products, and category relationships.

A product should be checked from the administration area and storefront. The administration check confirms whether migrated values are present. The storefront check confirms whether shoppers can identify, compare, select, and purchase the product.

| Product sample                            | Validation focus                                                                                   | Pass signal                                                                     |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Simple product                            | Name, alias, SKU or reference, description, image, price, tax display, stock, category assignment. | Product is visible, understandable, purchasable, and placed correctly.          |
| Product with attributes or options        | Selection controls, price changes, stock impact, required choices, display order.                  | Shopper choices behave as intended and order line items retain selected values. |
| Product with specifications or parameters | Technical details, comparison/filter relevance, structured display.                                | Product details remain useful for discovery and evaluation.                     |
| Discounted product                        | Discount price, cart discount, coupon compatibility, customer group visibility.                    | Promotional behavior matches the expected selling rule.                         |
| Downloadable product                      | Purchase path, order status dependency, access expectation, customer history.                      | Downloadable-product behavior is realistic for the target setup.                |
| Product in multiple categories            | Category assignment, path behavior, module visibility, duplicate-route risk.                       | Product remains discoverable without confusing storefront paths.                |

Attributes, options, specifications, and parameters should not be treated as interchangeable. An option may affect shopper choice or price. A specification may support comparison. A parameter may influence display or classification. Validation should confirm the role of each layer before approval.

Stock validation should include available stock, low stock, out-of-stock products, stock status labels, products affected by options, and any product where inventory should limit purchasing. For stores using POS or physical-store workflows, stock review should be connected to the intended post-launch operating model rather than validated as a static number only.

### Customer, Order, and Commercial Rule Validation <a href="#customer-order-and-commercial-rule-validation" id="customer-order-and-commercial-rule-validation"></a>

Customer validation should include more than name and email. Phoca Cart stores may use customer groups, Joomla user identity, customer group prices, reward points, discounts, addresses, order history, access levels, and account behavior. A migrated customer can look correct while losing the commercial treatment that made the record useful.

Order validation should go beyond totals. Historical orders should remain readable as business evidence: what was purchased, which options were selected, which customer group applied, which tax and shipping charges appeared, which payment method was used, and which invoice or delivery-note context matters.

| Record type        | Validation questions                                                                     | Evidence to review                                                                                         |
| ------------------ | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Customer profile   | Is the customer connected to the correct Joomla account and Phoca Cart customer context? | Customer details, login identity, addresses, group membership, order history.                              |
| Customer group     | Does the group still affect prices, discounts, tax handling, or access as expected?      | Group assignment, group price samples, storefront display, cart behavior.                                  |
| Order record       | Can support staff understand what happened historically?                                 | Order number, date, status, items, selected options, totals, tax, shipping, payment label, invoice output. |
| Coupon or discount | Does the rule belong to history, active selling, or configuration review?                | Coupon code, date range, customer group, product/category restrictions, cart behavior.                     |
| Reward points      | Are points historically meaningful and commercially usable after launch?                 | Customer point balance, earned points, redeemed points, order connection.                                  |

Coupons, discounts, reward points, and customer group prices should be tested through both static record review and storefront/cart behavior where applicable. A discount that appears in administration but behaves incorrectly in the cart is not launch-ready. A migrated coupon that applies to the wrong customer group, product, currency, or date range can create immediate revenue risk.

### Tax, Shipping, Payment, and Checkout Validation <a href="#tax-shipping-payment-and-checkout-validation" id="tax-shipping-payment-and-checkout-validation"></a>

Tax, shipping, and payment behavior is often configuration-sensitive. Historical orders may show past tax amounts, shipping charges, and payment labels, but those records do not automatically prove that future checkout behavior is configured correctly in the target Phoca Cart installation.

Tax validation should include representative products, customer groups, countries, regions, zones, tax rates, billing addresses, shipping addresses, and invoice output. If the source store used custom tax logic or third-party tax behavior, validation should separate what can be represented in normal Phoca Cart settings from what requires custom review.

Shipping validation should focus on the shipping methods that will be used after launch. Samples should include important destinations, weight or price thresholds, product-type restrictions, customer group behavior, free-shipping rules, and order totals that affect method availability.

Payment validation should include payment method visibility, checkout messages, order status handling, transaction reference behavior, and customer-facing confirmation. Payment plugins may need configuration, credentials, callback settings, or gateway-specific testing beyond migrated data.

| Checkout scenario            | Why it should be tested                                           | Expected proof                                                                        |
| ---------------------------- | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Guest checkout               | Reveals account and address assumptions.                          | Shopper can complete checkout without unexpected account friction.                    |
| Registered customer checkout | Tests Joomla user and Phoca Cart customer relationship.           | Customer identity, addresses, group treatment, and order history behave consistently. |
| Discounted order             | Tests coupon, cart discount, reward, and tax interactions.        | Discount appears correctly and totals remain understandable.                          |
| Regional order               | Tests tax, zone, shipping, currency, and payment availability.    | Checkout behavior matches the target market rule.                                     |
| Order with options           | Tests product choice preservation through cart and order history. | Selected options remain visible in order confirmation and administration.             |

Checkout validation should continue through order completion. Cart behavior alone is not enough if order status, invoice output, email messages, or payment references fail after submission.

### Storefront, Joomla, and Presentation Validation <a href="#storefront-joomla-and-presentation-validation" id="storefront-joomla-and-presentation-validation"></a>

Phoca Cart validation must include Joomla-facing presentation because customers interact with storefront paths, not database tables. Menus, modules, templates, template overrides, aliases, metadata, search, filters, comparison lists, wish lists, and category layouts can affect whether migrated data becomes usable.

Important validation samples should include high-traffic categories, top products, discounted products, products shown through modules, products using filters, checkout paths, account paths, multilingual paths, and SEO-sensitive URLs. Stores using custom templates, Joomla modules, or Phoca Cart template overrides need layout review in addition to data review.

| Storefront element      | Validation focus                                                                             | Pass signal                                                    |
| ----------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Category pages          | Product listing, filters, pagination, aliases, metadata, route behavior.                     | Customers can browse and refine products without broken paths. |
| Product pages           | Layout, image output, price display, options, specifications, reviews, structured details.   | Product detail pages support buying decisions.                 |
| Modules                 | Cart, currency, product, category, search, filter, comparison, wish list, or custom modules. | Modules render expected data in the intended Joomla positions. |
| Templates and overrides | Product layout, category layout, checkout layout, invoice or email presentation.             | Custom presentation does not hide or distort migrated values.  |
| SEO paths               | Aliases, canonical expectations, redirects, metadata, structured data where used.            | High-value paths have continuity or a redirect plan.           |

Presentation validation should not be limited to the default template. The future site theme, module positions, menu structure, and template overrides should be used whenever possible because these are the conditions shoppers will experience after launch.

### Multilingual, Multicurrency, Extension, and Custom Data Validation <a href="#multilingual-multicurrency-extension-and-custom-data-validation" id="multilingual-multicurrency-extension-and-custom-data-validation"></a>

Phoca Cart supports multilingual and multicurrency use, but those capabilities increase validation complexity. A store can pass in the default language and still fail for translated product names, category aliases, module output, checkout labels, currency display, invoice output, emails, or region-specific payment and shipping behavior.

Multilingual validation should include product pages, category pages, modules, cart, checkout, account paths, order confirmation, and key transactional messages where relevant. Multicurrency validation should include product display, cart totals, order totals, invoice context, discounts, tax, and shipping charges.

Extension-owned and custom data should be classified before approval. Phoca Cart stores may contain plugin-owned payment or shipping data, POS-related records, invoice customizations, custom fields, template overrides, import/export routines, ERP connectors, feed plugins, custom modules, or bespoke Joomla development. These items should not be silently approved as standard scope if they require mapping, transformation, or custom handling.

| Complex area                 | Validation question                                                                            | Decision outcome                                                             |
| ---------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Multilingual records         | Do important products, categories, modules, and checkout paths work in each major language?    | Approve language scope, request configuration, or expand validation samples. |
| Multicurrency behavior       | Do prices, discounts, tax, shipping, orders, and invoices remain consistent across currencies? | Approve target settings or review currency-specific rules.                   |
| Payment and shipping plugins | Are plugin-owned records and order references understandable?                                  | Confirm configuration scope or require custom review.                        |
| POS or invoice customization | Does target behavior preserve operational output?                                              | Confirm supported behavior or scope Custom Service.                          |
| Custom modules or overrides  | Does presentation depend on custom Joomla logic?                                               | Validate in the target template or define rebuild work.                      |

A validation pass should never hide custom complexity. When data belongs to unsupported extensions, custom code, plugin-specific tables, or undocumented business logic, the result should identify the required service path before approval.

### Turning Validation Results Into Launch Decisions <a href="#turning-validation-results-into-launch-decisions" id="turning-validation-results-into-launch-decisions"></a>

Validation should produce a decision, not a loose list of observations. Each issue should be assigned to one of four categories: acceptable difference, target configuration, Add-on review, or Custom Service review. This prevents minor display differences from being treated like blockers and prevents structural mismatches from being treated like ordinary cleanup.

| Validation result                                        | Meaning                                       | Recommended action                                                                                                                |
| -------------------------------------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Records are correct and behavior works                   | Migration result is acceptable for that area. | Approve the sample and document the pass condition.                                                                               |
| Records are present but behavior depends on settings     | Target configuration needs adjustment.        | Configure Phoca Cart, Joomla, modules, templates, tax, shipping, payment, or language settings.                                   |
| Standard scope is correct but extra processing is needed | A supported Add-on may fit the requirement.   | Review Add-ons such as filtering, mapping, or related supported adjustments where applicable.                                     |
| Data meaning is custom or unsupported                    | Standard processing is not enough.            | Review Custom Service for unsupported data, custom logic, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment. |
| Demo Migration does not expose real complexity           | Sample set is too weak.                       | Expand samples before approving Full Migration.                                                                                   |

A strong validation report should name the sample, describe the expected result, record the actual result, classify the issue, assign the next action, and state whether the area is ready for Full Migration. Phoca Cart validation is successful when records, configuration, storefront behavior, and service-path decisions are aligned before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Phoca Cart validation should prove that the migrated store can operate as a Joomla-native commerce environment. Product counts, customer totals, and order totals are only the starting point. The important question is whether catalog meaning, commercial rules, customer history, checkout behavior, Joomla storefront paths, multilingual behavior, and extension-owned data remain usable together.

The best validation work uses representative samples, tests administration and storefront behavior, separates migrated history from target configuration, and turns findings into clear launch decisions. When a Phoca Cart migration includes complex product rules, customer groups, reward points, tax regions, shipping plugins, payment plugins, modules, template overrides, POS workflows, or custom data, validation should identify whether the issue belongs to configuration, Add-ons, or Custom Service before launch approval.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first after a Phoca Cart migration?**

Start with products, categories, customer records, orders, tax, shipping, payment context, and storefront paths. Then expand into attributes, options, specifications, discounts, reward points, customer groups, multilingual behavior, modules, templates, and custom data.

**Is it enough to compare record counts between the source store and Phoca Cart?**

No. Record counts only show whether records exist. Validation should also prove that product choices, customer groups, order details, pricing rules, checkout behavior, Joomla paths, and storefront presentation remain usable.

**Why should Phoca Cart validation include Joomla menus and modules?**

Phoca Cart runs inside Joomla, so shoppers may reach products through menus, modules, category pages, search, filters, template layouts, and aliases. Data can be correct while the storefront path is still broken.

**How should Demo Migration samples be selected for Phoca Cart?**

Samples should represent real complexity: products with attributes and options, products with specifications, discounted products, customer group examples, orders with tax and shipping context, multilingual records, module-driven pages, and custom or plugin-owned data.

**When should validation lead to Custom Service review?**

Custom Service should be reviewed when validation exposes unsupported extension data, custom Phoca Cart logic, undocumented Joomla tables, bespoke checkout behavior, POS dependencies, invoice customization, or custom migration logic requirements.
