# Zen Cart Validation Priorities

Zen Cart validation should prove that migrated data works inside a self-hosted PHP/MySQL e-commerce store, not only that records appear in the admin area. A successful result should preserve the business meaning of products, categories, attributes, customers, orders, modules, content, templates, URLs, and custom data in the actual target environment.

Zen Cart stores often depend on configuration, templates, plugins, payment modules, shipping modules, tax behavior, order totals, sideboxes, EZ-Pages, and custom database work. Validation should therefore compare data accuracy with storefront behavior, admin usability, and launch readiness.

### What Zen Cart Validation Should Prove <a href="#what-zen-cart-validation-should-prove" id="what-zen-cart-validation-should-prove"></a>

Validation should answer whether the migrated store can be managed, browsed, searched, ordered from, and supported after launch. Record counts are useful as a first check, but they do not prove that Zen Cart can represent the current store’s catalog, checkout context, customer history, or content structure correctly.

| Validation area                                 | What must be proven                                                                                                            | Why it matters in Zen Cart                                                             |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| Target environment                              | The store runs on the intended Zen Cart version, PHP version, database setup, SSL configuration, and hosting environment.      | Environment mismatches can make a valid data migration appear broken after launch.     |
| Catalog structure                               | Categories, products, product types, product status, prices, images, and sort behavior are usable in the storefront and admin. | Zen Cart catalog quality depends on both database records and storefront presentation. |
| Product attributes                              | Option names, option values, attribute pricing, stock behavior, and customer-facing choices remain meaningful.                 | Attribute issues can change buying behavior even when products appear correctly.       |
| Customers and addresses                         | Customer accounts, address books, contact details, newsletter status, and account usability are readable.                      | Customer service and repeat purchasing depend on usable account records.               |
| Orders and order totals                         | Historical orders preserve products, totals, taxes, discounts, payment labels, shipping labels, statuses, and comments.        | Order history must support customer service, finance review, and operational lookup.   |
| Payment, shipping, tax, and order-total context | Historical labels are readable, while live modules are configured separately in the target store.                              | Migrated history does not automatically activate live checkout behavior.               |
| Coupons and gift certificates                   | Promotional records and balances are preserved where they are within supported scope.                                          | Promotions often affect customer service, loyalty, and launch acceptance.              |
| Content and navigation                          | EZ-Pages, informational pages, sideboxes, menus, links, and navigation paths are usable.                                       | Zen Cart storefront quality depends on content and layout areas beyond products.       |
| Templates and plugins                           | Theme behavior, overrides, installed plugins, custom modules, and add-on data are reviewed separately from standard records.   | Many Zen Cart stores use customized presentation or plugin-owned functionality.        |
| SEO and URLs                                    | Slugs, canonical paths, redirects, image paths, metadata, and priority URLs behave acceptably.                                 | SEO-sensitive stores can lose value if URL and metadata validation is too light.       |

### Validate the Target Environment First <a href="#validate-the-target-environment-first" id="validate-the-target-environment-first"></a>

Zen Cart validation should begin with the target environment because self-hosted stores depend on hosting, PHP, database, SSL, file permissions, and version compatibility. A store can contain correct migrated records while still failing because the target environment is not ready.

Confirm that the target Zen Cart installation is accessible, secure, and aligned with the intended version. Review PHP and database compatibility, SSL behavior, admin access, storefront access, image handling, email behavior, and any required file or directory permissions before treating data issues as migration defects.

Validation should also confirm whether the target store is a clean installation, an upgraded installation, or an existing customized store. Each case changes how templates, plugins, configuration, and custom database structures should be interpreted.

### Validate Catalog, Category, and Product Structure <a href="#validate-catalog-category-and-product-structure" id="validate-catalog-category-and-product-structure"></a>

Catalog validation should compare products as shoppers and administrators use them. The review should include category placement, product names, descriptions, prices, images, status, sort order, manufacturers where applicable, product types, meta fields, and storefront display.

A strong catalog sample should include:

* simple products with ordinary prices and images;
* products assigned to multiple or deeply nested categories;
* inactive or hidden products if they need to remain preserved;
* products with sale pricing, special pricing, or promotional context;
* products with multiple images or image naming dependencies;
* products using non-standard product types;
* products that depend on plugins, custom fields, or custom templates.

The pass condition is not only that products exist. Products should be findable, readable, assignable to the right categories, manageable in the admin, and understandable from the storefront.

### Validate Product Attributes and Option Values <a href="#validate-product-attributes-and-option-values" id="validate-product-attributes-and-option-values"></a>

Product attributes are one of the most important Zen Cart validation areas. A product choice from another platform may become an option name, option value, attribute, price adjustment, required selection, stock-related behavior, or custom field inside Zen Cart.

Validation should include products where attributes affect real buying decisions. Check whether choices display clearly, whether required options behave correctly, whether price changes are understandable, whether attribute images or downloads are preserved where applicable, and whether admin users can manage the result.

| Attribute scenario            | Validation priority                                                            | Pass condition                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Required options              | Confirm that the shopper cannot accidentally bypass required choices.          | Required choices behave as intended in the storefront.                                                  |
| Price-adjusting attributes    | Compare product total changes after option selection.                          | The displayed and calculated price remains understandable.                                              |
| Multiple option groups        | Review products with size, color, material, configuration, or similar choices. | Option groups appear in a logical order and do not collapse into confusing text.                        |
| Attribute images or downloads | Check any product where files, images, or downloads are tied to selections.    | Files and related assets remain accessible where supported.                                             |
| Custom option behavior        | Review any non-standard selector, plugin, or coded product configurator.       | Custom behavior is either preserved, reconfigured, scoped for Custom Service, or excluded deliberately. |

### Validate Customers, Addresses, and Account Meaning <a href="#validate-customers-addresses-and-account-meaning" id="validate-customers-addresses-and-account-meaning"></a>

Customer validation should check more than names and email addresses. Zen Cart customer data can include address books, billing and shipping details, newsletter flags, account status, group-related behavior, order relationships, and customer-service history.

Review customers with multiple addresses, historical orders, different account statuses, guest or non-guest behavior where applicable, and any group or pricing relationship. If the current store uses external CRM, loyalty, subscription, membership, or B2B account logic, confirm whether those relationships are standard Zen Cart data, plugin-owned data, or Custom Service scope.

A pass means customer records are readable, associated with the correct orders, and usable for the intended post-migration customer-service process.

### Validate Orders, Order Totals, and Historical Checkout Context <a href="#validate-orders-order-totals-and-historical-checkout-context" id="validate-orders-order-totals-and-historical-checkout-context"></a>

Order validation should prove that historical order records remain useful after migration. Review orders with different statuses, taxes, discounts, coupons, gift certificates, payment labels, shipping labels, order comments, product attributes, refunds where available, and multiple-address or special-case behavior if present.

Zen Cart order totals can carry important meaning through subtotal, shipping, tax, discount, coupon, gift certificate, low-order fee, handling fee, or other configured total lines. These values should be checked carefully because a record-count match does not prove that historical totals are readable or operationally acceptable.

Historical labels and totals should not be confused with live module readiness. A migrated order may show a payment or shipping label from the previous store, while the active Zen Cart payment, shipping, tax, and order-total modules still require separate target configuration and testing.

### Validate Payment, Shipping, Tax, and Module Boundaries <a href="#validate-payment-shipping-tax-and-module-boundaries" id="validate-payment-shipping-tax-and-module-boundaries"></a>

Payment, shipping, tax, and order-total modules affect live checkout behavior. Migration validation should separate historical data acceptance from target checkout setup.

| Area                          | Historical validation                                                                    | Live target check                                                                 |
| ----------------------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Payment                       | Confirm payment method labels and transaction references remain readable where migrated. | Configure and test the active payment module separately.                          |
| Shipping                      | Confirm historical shipping method labels, costs, and delivery context remain readable.  | Configure active shipping modules, zones, rates, and carrier behavior separately. |
| Tax                           | Review tax lines and order totals for historical readability.                            | Configure target tax zones, rates, and calculation behavior separately.           |
| Order totals                  | Compare subtotal, shipping, tax, discount, coupon, gift certificate, and total lines.    | Confirm target order-total modules behave as expected for new checkout sessions.  |
| Coupons and gift certificates | Confirm migrated promotional records and balance-related data where supported.           | Test new promotional behavior through Zen Cart configuration.                     |

The pass condition is clear separation: migrated history is understandable, and live checkout configuration is reviewed as a target-store readiness task.

### Validate Content, EZ-Pages, Sideboxes, and Storefront Navigation <a href="#validate-content-ez-pages-sideboxes-and-storefront-navigation" id="validate-content-ez-pages-sideboxes-and-storefront-navigation"></a>

Zen Cart storefront quality often depends on content and layout areas that are not ordinary products. EZ-Pages, informational pages, sideboxes, banners, menus, category navigation, header/footer links, and template-controlled blocks should be reviewed from the shopper’s view.

Validation should include pages and navigation paths that affect trust, compliance, SEO, and conversion, such as About, Contact, Shipping, Returns, Privacy, Terms, category landing pages, and high-traffic informational pages. If content came from another CMS or page builder, confirm whether it migrated as clean content, plain HTML, linked pages, or custom scope.

The result passes when important navigation paths work and content appears in places customers can realistically find and use.

### Validate Templates, Plugins, Custom Fields, and Custom Tables <a href="#validate-templates-plugins-custom-fields-and-custom-tables" id="validate-templates-plugins-custom-fields-and-custom-tables"></a>

Zen Cart stores frequently use templates, overrides, plugins, modules, and custom database structures. These elements can affect product display, checkout behavior, customer groups, order processing, SEO, inventory, integrations, and admin workflows.

Standard validation should identify whether custom or plugin-owned data is present. It should not assume that every plugin table, custom field, or coded workflow is part of the default migration result.

Use the following review pattern:

| Customization area    | What to check                                                                        | Likely interpretation                                                            |
| --------------------- | ------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| Template overrides    | Product pages, category pages, checkout pages, sideboxes, and content areas.         | Presentation may require theme or template work outside ordinary data migration. |
| Plugins and modules   | Payment, shipping, SEO, inventory, discounts, export/import, feeds, and admin tools. | Plugin-owned data may require Custom Service review.                             |
| Custom fields         | Product, customer, order, or content fields added outside the standard model.        | Supported mapping may use Add-ons; bespoke behavior moves into Custom Service.   |
| Custom tables         | Records created by custom modules, integrations, or older modifications.             | Custom Service review is required when the data must be migrated.                |
| External integrations | ERP, accounting, warehouse, CRM, marketplace, email, or analytics references.        | Mapping, reconfiguration, or Custom Service review may be needed.                |

### Validate URLs, SEO, Images, and Redirects <a href="#validate-urls-seo-images-and-redirects" id="validate-urls-seo-images-and-redirects"></a>

SEO validation should focus on the pages that carry the most organic search, paid traffic, referral traffic, or customer-service value. Review product URLs, category URLs, EZ-Page URLs, image paths, metadata, redirects, canonical behavior, and indexed landing pages.

If the previous store used custom URL rewriting, SEO plugins, legacy paths, or non-standard image structures, review those samples separately. Zen Cart URL behavior depends on the target configuration, plugin choices, rewrite rules, and hosting setup.

A pass means priority pages are reachable, important metadata is preserved where supported, image references work, and redirect requirements are either configured, assigned for implementation, or deliberately excluded.

### Design Strong Demo Migration Samples <a href="#design-strong-demo-migration-samples" id="design-strong-demo-migration-samples"></a>

Demo Migration validation is only useful when the sample set reflects real Zen Cart complexity. A sample made only of simple products and ordinary orders can pass while important launch risks remain hidden.

A strong sample set should include:

| Sample type                                         | Why it matters                                                                       |
| --------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Product with multiple attributes                    | Confirms option names, option values, price adjustments, and shopper-facing choices. |
| Deep category sample                                | Confirms storefront navigation, category assignment, and SEO-sensitive paths.        |
| Product with images and metadata                    | Confirms image handling and page-level SEO review.                                   |
| Customer with multiple addresses                    | Confirms account and address-book usability.                                         |
| Order with discounts, tax, shipping, and attributes | Confirms order totals and historical checkout context.                               |
| Coupon or gift certificate sample                   | Confirms promotional data expectations where supported.                              |
| EZ-Page or key content page                         | Confirms non-product content migration quality.                                      |
| Plugin or custom-field sample                       | Reveals whether Add-ons or Custom Service review is needed.                          |

### Interpreting Validation Results <a href="#interpreting-validation-results" id="interpreting-validation-results"></a>

A passing Demo Migration should show that Zen Cart can represent the store’s important data in a usable way. A partial result does not automatically mean the migration failed; it may show that the target store needs configuration, Add-ons, template work, plugin review, or Custom Service.

Use validation findings to separate issues into clear categories:

* data that migrated correctly;
* target configuration that still needs setup;
* storefront or template work that must be handled outside the data layer;
* unsupported plugin or custom data that should be reviewed through Custom Service;
* filtering, mapping, or configuration needs that may fit Add-ons;
* accepted exclusions that should be documented before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Zen Cart validation should prove that the migrated store is usable in a real self-hosted environment. Products, categories, attributes, customers, orders, order totals, modules, content, templates, plugins, URLs, images, and custom data should be reviewed through the way administrators and customers will actually use the store.

Before approving Full Migration, use Demo Migration results to confirm the most complex catalog, order, module, content, and customization cases. If validation shows gaps in filtering, mapping, configuration, plugin-owned data, custom fields, or custom tables, clarify whether the issue belongs to Add-ons, target-store setup, template work, accepted exclusions, or Custom Service before launch planning continues.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first after a Zen Cart Demo Migration?**

Start with target environment readiness, then review catalog structure, product attributes, customer records, historical orders, order totals, payment and shipping labels, EZ-Pages, URLs, and any plugin or custom data that affects daily operations.

**Why are product attributes so important in Zen Cart validation?**

Zen Cart uses product attributes and option values to represent shopper-facing choices. If attributes are incomplete or poorly structured, customers may see confusing selections, incorrect price adjustments, missing required choices, or unusable product configurations.

**Does a correct order count prove that order migration is successful?**

No. Order validation should also check products, statuses, totals, taxes, discounts, coupons, gift certificates, payment labels, shipping labels, comments, and customer relationships. Order records must remain useful for customer service and business review.

**Should live payment and shipping modules be tested during data validation?**

They should be checked separately from migrated historical data. Migrated order labels help preserve history, while active payment, shipping, tax, and order-total modules require target-store configuration and testing before launch.

**When should Zen Cart validation move into Custom Service review?**

Custom Service review is appropriate when required results depend on custom database tables, plugin-owned data, bespoke product behavior, custom checkout logic, non-standard integrations, or custom migration logic adjustment beyond standard service capability.
