# VirtueMart Validation Priorities

VirtueMart validation should prove that the migrated store can operate as a Joomla-connected commerce environment, not simply that records arrived in a database. VirtueMart stores often rely on Joomla menus, modules, template overrides, plugins, shopper groups, custom fields, calculation rules, shipment methods, payment methods, language records, and extension-level configuration. A record count alone cannot confirm that those relationships remain usable.

The main validation question is whether the target store preserves the commercial meaning of the original store. Products must still be purchasable in the correct forms. Categories must still support discovery. Prices, tax logic, shipment options, shopper groups, and custom fields must still create the expected buying experience. Orders must remain understandable as business history. Joomla storefront paths must continue to guide visitors to the correct content and product pages.

| Validation area    | What needs to be proven                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Product structure  | Products, child products, variants, custom fields, media, and inventory still represent the intended selling model. |
| Commercial rules   | Shopper groups, prices, discounts, taxes, and calculation rules still support the expected buyer experience.        |
| Checkout context   | Shipment and payment records are understandable and live checkout configuration is planned separately when needed.  |
| Joomla storefront  | Menus, modules, templates, overrides, aliases, and SEO-sensitive paths still support navigation and discovery.      |
| Historical records | Customers and orders remain useful for service, reporting, compliance, and account history.                         |
| Custom scope       | Plugin-owned, extension-owned, or custom-developed records are identified before approval.                          |

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

VirtueMart product validation should begin with the product structures that carry the most business meaning. Simple products are useful as a baseline, but they are not enough. Review products with custom fields, child products, variants, parent-child relationships, manufacturer relationships, media galleries, downloadable files, stock behavior, prices, and category assignments.

A strong validation sample includes ordinary products, high-revenue products, products with many fields, products with multiple price behaviors, products assigned to several categories, products with translated content, products connected to manufacturers, and products that previously depended on extensions or custom templates. These examples reveal whether the target store understands product meaning rather than only copying visible names and descriptions.

| Product sample                      | Why it matters in VirtueMart validation                                                 |
| ----------------------------------- | --------------------------------------------------------------------------------------- |
| Simple product                      | Confirms basic product identity, descriptions, images, prices, and category assignment. |
| Product with custom fields          | Confirms selling options, specifications, variant-like behavior, and display logic.     |
| Child product                       | Confirms parent-child relationships and product selection behavior.                     |
| Product with multiple prices        | Confirms shopper group pricing, currency behavior, or calculation logic.                |
| Product with manufacturer           | Confirms brand/manufacturer relationships remain usable.                                |
| Multilingual product                | Confirms translated titles, descriptions, aliases, and metadata remain aligned.         |
| Downloadable or media-heavy product | Confirms files, media paths, previews, and access expectations are handled.             |

Validation should not stop at the product edit screen. The storefront view, category page, search result, filter behavior, product detail page, cart addition, and checkout path should all be checked. A product may appear correct in administration while failing in a template override, module position, menu path, or checkout flow.

### Shopper Group, Price, and Calculation Rule Validation <a href="#shopper-group-price-and-calculation-rule-validation" id="shopper-group-price-and-calculation-rule-validation"></a>

VirtueMart often uses shopper groups and calculation rules to control pricing, tax behavior, discounts, and buyer-specific conditions. These areas deserve separate validation because they affect the commercial outcome of the migration. If the source store used customer groups, wholesale roles, regional pricing, tax overrides, discounts, or special rules, representative examples must be included in validation.

The target store should show whether each buyer type sees the right catalog access, prices, discounts, taxes, and purchase options. Where the source store used logic that does not map directly to the target configuration, the validation process should identify whether the requirement belongs in configuration, Add-ons, or Custom Service.

| VirtueMart rule area   | Validation question                                                                              |
| ---------------------- | ------------------------------------------------------------------------------------------------ |
| Shopper groups         | Do group memberships still support the intended pricing, visibility, and buying rules?           |
| Prices                 | Are base prices, group prices, currency assumptions, and historical order values understandable? |
| Calculation rules      | Do taxes, discounts, fees, and price modifiers need mapping, configuration, or custom handling?  |
| Coupons and promotions | Are historical coupon records and live promotion requirements separated correctly?               |
| Currencies             | Are currency values, display expectations, and store configuration reviewed before approval?     |

A useful validation result should distinguish migrated history from live operating behavior. Historical orders can preserve past payment, tax, and shipment information, but active checkout behavior usually depends on current VirtueMart configuration, installed plugins, and target-store settings.

### Customer and Order Validation <a href="#customer-and-order-validation" id="customer-and-order-validation"></a>

Customer validation should review both Joomla user identity and VirtueMart shopper context. A customer may have Joomla login credentials, VirtueMart addresses, shopper group membership, order history, billing details, shipping details, and communication records. Validation should confirm that the target store preserves account meaning in a way that staff can use.

Order validation should focus on business readability. Staff should be able to understand what was purchased, who bought it, which prices and taxes were recorded, what shipment and payment context applied, whether coupons or discounts were involved, and how order status history should be interpreted. Exact live payment or shipment plugin behavior should not be assumed from historical order data.

| Record type        | Validation focus                                                                     |
| ------------------ | ------------------------------------------------------------------------------------ |
| Joomla user        | Login identity, user status, group assignment, and account continuity.               |
| VirtueMart shopper | Billing details, shipping details, shopper group, and buyer profile context.         |
| Order record       | Items, quantities, prices, taxes, discounts, totals, addresses, statuses, and notes. |
| Shipment history   | Past shipment method names and order context.                                        |
| Payment history    | Past payment method names and order context.                                         |
| Staff usage        | Ability to search, review, and support customer/order history after migration.       |

Validation should include recent orders, old orders, refunded or adjusted orders, multi-item orders, orders with coupons, orders using different shipment methods, and orders from different customer groups. These examples expose whether the migrated history is useful rather than merely present.

### Joomla Storefront and SEO Validation <a href="#joomla-storefront-and-seo-validation" id="joomla-storefront-and-seo-validation"></a>

VirtueMart operates inside Joomla, so storefront validation must include Joomla routes and presentation dependencies. Menus, aliases, modules, templates, overrides, SEF URLs, metadata, redirects, category paths, product paths, and landing pages can all affect discoverability and conversion. A technically migrated product can still fail if the storefront path that exposes it is broken.

Validation should cover the product page, category page, menu-driven catalog entry points, search and filter paths, module-based product blocks, cart entry, checkout flow, and important SEO-sensitive URLs. Stores using custom Joomla templates or VirtueMart layout overrides should review representative pages rather than relying only on administration screens.

| Storefront dependency | What to validate                                                                           |
| --------------------- | ------------------------------------------------------------------------------------------ |
| Joomla menus          | Catalog entry points, product/category routes, alias behavior, and navigation paths.       |
| Template overrides    | Product page layout, category page layout, cart layout, and checkout display.              |
| Modules               | Featured products, related products, category lists, cart modules, and promotional blocks. |
| Metadata and SEF URLs | Titles, aliases, metadata, canonical expectations, and redirect-sensitive paths.           |
| Search and filters    | Product discovery, category navigation, and filtering behavior.                            |

Where route behavior changes, validation should separate acceptable target-store differences from launch-blocking SEO or navigation failures. Not every old URL structure needs to be copied exactly, but high-value paths and conversion-critical routes must be handled deliberately.

### Multilingual, Extension, and Custom Data Validation <a href="#multilingual-extension-and-custom-data-validation" id="multilingual-extension-and-custom-data-validation"></a>

VirtueMart stores may include multilingual product data, translated categories, multilingual checkout labels, currency behavior, Joomla language associations, third-party plugins, custom fields, integration records, template customizations, or custom-developed tables. These areas should be validated with representative examples before approval.

Multilingual validation should include product pages, category pages, cart labels, checkout context, metadata, menu paths, and aliases in each important language. Currency validation should confirm whether values are historical records, display rules, or live exchange/configuration behavior. Custom data validation should identify whether the target migration scope includes the records directly or whether custom handling is required.

| Complex area           | Validation signal                                                                                |
| ---------------------- | ------------------------------------------------------------------------------------------------ |
| Multilingual catalog   | Translations, aliases, metadata, menu paths, and category/product relationships remain coherent. |
| Multicurrency display  | Currency values and display expectations are reviewed separately from live configuration.        |
| Third-party plugins    | Plugin-owned fields or workflows are not treated as standard VirtueMart records without review.  |
| Custom development     | Custom tables, scripts, and integrations are documented before approval.                         |
| Template customization | Layout behavior is checked in storefront pages, not only in administration screens.              |

When these areas are present, validation should include enough samples to reveal patterns. One translated product or one custom-field product rarely proves that the full store structure is safe.

### Demo Migration Review Priorities <a href="#demo-migration-review-priorities" id="demo-migration-review-priorities"></a>

Demo Migration is most useful when the sample set exposes real VirtueMart complexity. A small sample of simple products and straightforward orders may create false confidence. The review sample should include records that test the store’s actual selling model.

| Sample to include                                     | Reason                                                |
| ----------------------------------------------------- | ----------------------------------------------------- |
| Product with custom fields and child products         | Tests product relationship and variant-like behavior. |
| Product with shopper group pricing                    | Tests commercial rule handling.                       |
| Product with manufacturer, media, and categories      | Tests catalog relationships and storefront display.   |
| Order with tax, shipment, payment, and coupon context | Tests historical order readability.                   |
| Customer with shopper group and multiple addresses    | Tests buyer identity and account continuity.          |
| Multilingual product/category                         | Tests translated content, aliases, and metadata.      |
| Extension-owned or custom record                      | Tests whether special handling is needed.             |

Approval should be based on representative behavior, not on isolated record counts. If the Demo Migration shows product, customer, order, route, or rule problems, those findings should be converted into scope decisions before Full Migration.

### Turning Validation Into Launch Readiness <a href="#turning-validation-into-launch-readiness" id="turning-validation-into-launch-readiness"></a>

Validation should end with a clear decision: approve the current approach, request configuration changes, add required Add-ons, escalate special handling through Custom Service, or revise the launch plan. A good validation report records what was checked, what passed, what failed, what still needs configuration, and what cannot be treated as standard scope.

| Validation result                              | Launch decision                                                                               |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Core records and relationships pass            | Continue toward Full Migration and launch preparation.                                        |
| Records migrate but storefront behavior fails  | Review Joomla menus, templates, modules, overrides, and SEO paths.                            |
| Rule-based behavior does not translate cleanly | Review shopper groups, prices, calculation rules, taxes, shipping, and payment configuration. |
| Custom or plugin-owned records appear          | Confirm whether Custom Service is required.                                                   |
| Samples are too simple                         | Expand Demo Migration review before approving the approach.                                   |

The final readiness decision should be practical. The store is ready only when staff can operate the target VirtueMart environment, customers can find and buy products through the expected paths, and unresolved exceptions are documented with the right service path.

The final validation record should be specific enough for another stakeholder to understand the approval decision. It should name the sample products, customer groups, orders, URLs, languages, currencies, plugins, and custom fields that were checked. It should also document which issues were corrected, which require target configuration, which are accepted differences, and which require Add-ons or Custom Service before launch.

For VirtueMart, acceptance evidence should be organized around business outcomes. Customers need to find products, choose the right options, see appropriate prices, add items to cart, complete checkout, and receive a coherent order result. Staff need to search customers, read orders, understand payment and shipment history, review taxes and discounts, and maintain catalog records after launch. SEO and storefront teams need to confirm that important routes, metadata, modules, and templates support the new environment.

If validation produces only screenshots or record counts, it is too weak for a complex VirtueMart store. The stronger standard is proof by scenario: a wholesale customer viewing a grouped price, a multilingual product reached through the expected menu path, an order with tax and shipment context, a child-product option with stock behavior, and a custom-field product that exposes whether the approach is strong enough for Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VirtueMart validation should prove operational continuity across Joomla structure and VirtueMart commerce logic. Product records, customer data, orders, prices, taxes, shipment and payment context, shopper groups, custom fields, child products, multilingual content, storefront routes, modules, templates, and extension-owned data all influence launch readiness.

A reliable validation process uses representative samples, tests storefront behavior, separates migrated history from live configuration, and turns findings into clear scope decisions before Full Migration. That approach reduces launch risk and helps the target store remain usable, searchable, and commercially understandable.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are record counts not enough for VirtueMart validation?**

Record counts cannot prove that product relationships, custom fields, shopper groups, prices, taxes, shipment methods, payment context, Joomla menus, modules, templates, and multilingual paths still work together.

**Which VirtueMart products should be checked first?**

Start with products that carry the most business meaning: child products, products with custom fields, products with group pricing, products with multiple categories, multilingual products, media-heavy products, and high-revenue products.

**Should historical payment and shipment data behave like live checkout settings?**

No. Historical order data helps staff understand past transactions, while live checkout behavior depends on current VirtueMart configuration, installed plugins, and target-store settings.

**When should Custom Service be considered during validation?**

Custom Service should be considered when validation finds plugin-owned, integration-owned, custom-developed, or heavily modified data that does not fit standard VirtueMart migration behavior.
