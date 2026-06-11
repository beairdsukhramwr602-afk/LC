# Zen Cart Pre-Migration Preparation Checklist

Preparing for a Zen Cart migration means more than collecting products, customers, and orders. Zen Cart is a self-hosted PHP/MySQL e-commerce platform, so the target result depends on the target installation, server environment, version compatibility, catalog structure, product attributes, payment and shipping modules, order totals, templates, plugins, EZ-Pages, SEO settings, and any custom database behavior that supports the current store.

Good preparation makes the Demo Migration easier to interpret. It gives each reviewer a clear reason for checking selected products, categories, attributes, orders, customers, content pages, URLs, and module-related records. It also helps identify early whether the project fits standard service capability, needs Add-ons, or should move into Custom Service because customization or unsupported data handling is required.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

The goal of preparation is to make the future Zen Cart store testable. A migration can look complete from record totals while still failing to preserve the way the store sells, prices, discounts, ships, taxes, displays, and organizes products.

Before Demo Migration or Full Migration, preparation should clarify:

* which Zen Cart version and server environment will be used;
* which data types should be migrated from the Source Platform;
* which products, categories, customers, orders, content pages, and URLs are business-critical;
* which product attributes, option values, downloads, specials, coupons, gift certificates, and order totals affect selling or order history;
* which payment, shipping, tax, template, sidebox, and plugin behavior must be configured in the target store rather than treated as ordinary migrated records;
* which custom fields, custom tables, third-party modules, external identifiers, feeds, or integrations require separate review.

### Confirm the Target Zen Cart Environment <a href="#confirm-the-target-zen-cart-environment" id="confirm-the-target-zen-cart-environment"></a>

Zen Cart migration readiness starts with the target environment. Because Zen Cart is self-hosted, a clean migration result still depends on whether the target hosting, PHP version, database version, SSL setup, permissions, and installed modules can support the expected store.

| Preparation item                 | What to confirm                                                                                                                             | Why it matters                                                                                                                |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Target Zen Cart version          | The intended target version, release baseline, and whether the store is a fresh installation or an upgraded installation                    | Version differences can affect plugin compatibility, language files, templates, checkout behavior, and database expectations. |
| Hosting and server stack         | PHP, MySQL or compatible database, web server, SSL, cURL, email transport, memory limits, file permissions, and backup access               | A migrated store cannot be accepted confidently if the target environment is unstable or incomplete.                          |
| Admin access and technical roles | Who can access hosting, database tools, Zen Cart admin, file manager, FTP/SFTP, and backup systems                                          | Migration review often requires both admin-level data checks and technical environment checks.                                |
| Installed template               | Whether the target uses a default template, commercial template, custom template, or inherited override set                                 | Storefront presentation, sideboxes, product pages, and content placement can depend on template files and overrides.          |
| Plugin and module set            | Payment modules, shipping modules, order-total modules, SEO modules, import/export tools, image tools, feeds, analytics, and custom plugins | Plugin-owned behavior and plugin-owned data should not be assumed to migrate as core Zen Cart records.                        |
| Upgrade context                  | Whether the target project includes an old Zen Cart installation, database-only upgrade, or custom legacy modification                      | Upgrade work and migration work should be planned as separate responsibilities when both are present.                         |

### Prepare Product, Category, and Catalog Samples <a href="#prepare-product-category-and-catalog-samples" id="prepare-product-category-and-catalog-samples"></a>

Catalog preparation should show how products are organized, discovered, selected, priced, and purchased in the Source Platform. Simple products are useful, but they are not enough for Zen Cart preparation when the store depends on attributes, option values, linked products, specials, downloads, product types, manufacturer-like fields, tax classes, or category placement.

Prepare samples for:

* products in simple categories and deep category paths;
* products assigned to more than one category, if used;
* active, inactive, hidden, or unavailable products;
* products with model or SKU-like identifiers;
* products with manufacturers, brands, or supplier-style fields;
* products with stock quantity, weight, tax class, shipping behavior, or minimum/maximum quantity rules;
* products with specials, sale pricing, quantity discounts, or group pricing behavior;
* downloadable or digital products, if used;
* products whose images, additional images, descriptions, meta tags, or product URLs affect conversion.

### Prepare Product Attribute and Option Evidence <a href="#prepare-product-attribute-and-option-evidence" id="prepare-product-attribute-and-option-evidence"></a>

Zen Cart uses product attributes, option names, and option values to represent many shopper selections. This makes product-attribute preparation one of the most important readiness steps for stores migrating from platforms that use variants, configurable products, modifiers, product options, or custom product fields.

| Attribute sample               | What to include                                                                       | What to check later                                                                            |
| ------------------------------ | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Required choices               | Products where a shopper must choose size, color, material, format, or another option | The product should not be purchasable without the required selection.                          |
| Price-changing options         | Attributes that increase or reduce price                                              | Cart and order totals should reflect the selected option correctly.                            |
| Download attributes            | Digital products or products with file delivery behavior                              | Download availability should be reviewed separately from product presence.                     |
| Text or custom input           | Products where shoppers enter text, personalization, or notes                         | The selected or entered value should remain understandable in cart and order context.          |
| Option images or display logic | Attributes with image, dropdown, radio, checkbox, or layout implications              | The storefront should display options in a usable way after target setup.                      |
| Stock-sensitive choices        | Options that affect availability, quantity, or fulfillment decisions                  | The team should verify whether the target structure can represent the expected stock behavior. |

### Prepare Customer, Address, Newsletter, and Group Samples <a href="#prepare-customer-address-newsletter-and-group-samples" id="prepare-customer-address-newsletter-and-group-samples"></a>

Customer preparation should include more than customer counts. Zen Cart customer records can include account information, billing addresses, shipping addresses, newsletter status, customer group behavior, order relationships, and email history relevance.

Prepare examples for:

* customers with one billing address and one shipping address;
* customers with multiple addresses;
* guest or account-based order cases, where available from the Source Platform;
* newsletter or subscription status when it matters operationally;
* customer group, wholesale, approval, or pricing behavior if used;
* customers with recent orders, refunded orders, discounted orders, or high-value order history;
* customers with special notes, external IDs, loyalty references, or CRM/accounting references.

If customer groups, wholesale rules, or approval workflows are not ordinary supported data in the migration path, they should be reviewed before they are treated as expected target behavior.

### Prepare Order, Order Total, Coupon, and Gift Certificate Samples <a href="#prepare-order-order-total-coupon-and-gift-certificate-samples" id="prepare-order-order-total-coupon-and-gift-certificate-samples"></a>

Orders should be prepared with enough variety to prove historical readability. In Zen Cart, order meaning can depend on statuses, comments, products, selected attributes, addresses, taxes, discounts, coupons, gift certificates, payment labels, shipping labels, and order-total line items.

| Order sample                                              | Why it matters                                                                                                     |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Standard paid order                                       | Confirms ordinary customer, product, address, payment, shipping, tax, and total readability.                       |
| Order with selected attributes                            | Confirms shopper selections remain understandable in order history.                                                |
| Discounted order                                          | Confirms coupon, discount, special, group pricing, or order-total context is not flattened into a confusing total. |
| Gift certificate or store-credit order                    | Confirms special value flows are identified before scope is finalized.                                             |
| Refunded, canceled, pending, or partially fulfilled order | Confirms order statuses and operational labels remain meaningful.                                                  |
| Order with comments or admin notes                        | Confirms service history and review context are preserved where supported.                                         |
| Order with unusual tax or shipping logic                  | Confirms historical tax, shipping, and order-total context can be reviewed after migration.                        |

Historical order labels do not configure live Zen Cart payment, shipping, tax, or order-total modules. Those target modules need separate setup and testing.

### Separate Migrated Records from Live Module Configuration <a href="#separate-migrated-records-from-live-module-configuration" id="separate-migrated-records-from-live-module-configuration"></a>

Zen Cart module behavior should be prepared as target configuration work, not only migration data. Payment, shipping, tax, order-total, coupon, gift-certificate, email, and checkout behavior can affect the live store even when historical records migrate correctly.

| Target configuration area | Preparation question                                                                                                               |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Payment modules           | Which payment methods should be active after launch, and are the required credentials, extensions, and compatibility checks ready? |
| Shipping modules          | Which carriers, zones, rates, table rates, free-shipping rules, or custom shipping methods must be configured?                     |
| Tax settings              | Which tax zones, tax classes, rates, and pricing-includes-tax assumptions must be reviewed?                                        |
| Order-total modules       | Which discounts, fees, coupons, gift certificates, group pricing, shipping, tax, and total-line behavior must be active?           |
| Checkout behavior         | Which checkout expectations depend on modules, template behavior, customer approval, address rules, or custom code?                |
| Email behavior            | Which order emails, customer emails, transport method, HTML templates, and sender settings should be checked before launch?        |

### Prepare Content, EZ-Pages, Navigation, Sideboxes, and Template Evidence <a href="#prepare-content-ez-pages-navigation-sideboxes-and-template-evidence" id="prepare-content-ez-pages-navigation-sideboxes-and-template-evidence"></a>

Zen Cart storefront continuity depends on more than product records. Content pages, EZ-Pages, define pages, sideboxes, header and footer links, category menus, product listing layout, language files, and template overrides can all affect how the target store feels after migration.

Prepare evidence for:

* EZ-Pages and important informational CMS Pages;
* page titles, meta tags, and navigation placement;
* sideboxes used for categories, information links, specials, featured products, manufacturers, search, or custom content;
* define pages, store policies, contact pages, privacy pages, terms pages, and other operational content;
* header, footer, menu, category, and product-listing expectations;
* template overrides, custom layout files, commercial templates, or custom theme behavior;
* image paths, additional product images, banners, logos, and media placement.

Blog Posts should be prepared only when the current store uses a plugin, external blog, or custom content structure that must be included in migration scope.

### Prepare SEO, URL, Domain, and Redirect Evidence <a href="#prepare-seo-url-domain-and-redirect-evidence" id="prepare-seo-url-domain-and-redirect-evidence"></a>

Zen Cart stores often depend on product URLs, category URLs, page URLs, meta tags, relative URL behavior, SSL/domain setup, and SEO-related plugins. SEO preparation should identify the URLs and metadata that matter most before migration acceptance.

Prepare:

* priority product URLs;
* priority category URLs;
* important EZ-Page or CMS Page URLs;
* page titles, product meta titles, descriptions, and keywords where used;
* existing redirect rules;
* old-to-new URL expectations;
* canonical URL or SEO plugin behavior;
* SSL and domain assumptions;
* URLs from ads, search results, email campaigns, feeds, or external links.

A target product may be present and still fail SEO acceptance if its URL, metadata, redirect, or storefront path is not reviewed.

### Inventory Plugins, Modules, Custom Tables, and External Integrations <a href="#inventory-plugins-modules-custom-tables-and-external-integrations" id="inventory-plugins-modules-custom-tables-and-external-integrations"></a>

Zen Cart stores often rely on plugins, custom modules, modified files, custom database tables, import/export utilities, reporting extensions, SEO tools, feeds, analytics, ERP tools, shipping tools, or accounting integrations. These should be inventoried before Demo Migration.

| Dependency type                           | What to collect                                                                              | Service implication                                                                                   |
| ----------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Plugin-owned data                         | Plugin name, version, data tables, fields, admin screens, and business purpose               | Unsupported plugin data is reviewed through Custom Service.                                           |
| Custom database fields                    | Field names, table names, sample records, and where the values appear in admin or storefront | Custom field handling is reviewed through Custom Service when not supported by standard data mapping. |
| Modified core or template files           | File list, modified behavior, override locations, and target expectations                    | File or template behavior is separate from ordinary data migration.                                   |
| Import/export utilities                   | Feed format, identifiers, scheduled jobs, and external systems                               | External workflow preservation may require separate planning.                                         |
| ERP, PIM, accounting, or shipping systems | External IDs, sync direction, field ownership, and required target references                | Integration-sensitive references may require Custom Service review.                                   |
| SEO, feed, or analytics tools             | URL rules, metadata fields, tracking IDs, feed IDs, and plugin settings                      | Records and configuration should be reviewed separately.                                              |

### Choose Demo Migration Samples Deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration samples should expose the parts of the store most likely to fail if preparation is shallow. Do not rely only on the newest products or the largest category.

| Sample type        | Strong example                                                                                                                           |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Product sample     | Attribute-heavy product with price-changing options, images, stock, tax class, category assignment, and SEO metadata.                    |
| Category sample    | Deep category path with visible products, linked products, and storefront navigation importance.                                         |
| Customer sample    | Customer with multiple addresses, newsletter status, group behavior, and varied order history.                                           |
| Order sample       | Order with selected attributes, coupon or gift certificate context, tax, shipping, payment label, status, comments, and total breakdown. |
| Content sample     | EZ-Page, define page, policy page, or important CMS Page connected to navigation.                                                        |
| SEO sample         | Priority product, category, or content URL that must resolve or redirect acceptably.                                                     |
| Plugin sample      | Record that depends on a plugin, custom field, external ID, or custom database table.                                                    |
| Integration sample | Record used by accounting, ERP, PIM, shipping, feed, analytics, or reporting workflows.                                                  |

### Identify Add-on and Custom Service Signals Early <a href="#identify-add-on-and-custom-service-signals-early" id="identify-add-on-and-custom-service-signals-early"></a>

Preparation should identify whether the project can stay within standard service capability or needs additional service review.

Add-ons are relevant when the migration needs supported filtering, mapping, or data-configuration help. The Data Filter Add-on can help when only selected eligible records should be migrated. Advanced Data Mapping can help when supported field mapping needs adjustment. Advanced Data Configure can help when supported data values need modification before they reach the Target Platform.

Custom Service is used when customization or modification work is required. For Zen Cart, Custom Service should be reviewed when the migration involves Custom Platform source interpretation, unsupported plugin data, custom fields, custom tables, custom product-attribute transformation, unusual order-total logic, custom checkout/payment/shipping/tax behavior, external identifiers, custom URL transformation, or integration-sensitive data that cannot be handled as ordinary supported records.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Zen Cart preparation should make the migration result easier to prove, not simply easier to start. A well-prepared project identifies the target environment, catalog structure, product attributes, customer and order examples, modules, plugins, templates, content, URLs, and custom data before Demo Migration begins.

Before proceeding, gather representative samples from the records and workflows that define the store’s real selling behavior. A focused Demo Migration can then show whether the Zen Cart migration path is straightforward, whether Add-ons are enough for filtering or mapping needs, or whether Custom Service should be reviewed before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first for a Zen Cart migration?**

Start with the target Zen Cart version, server environment, hosting access, database access, SSL status, template, plugin list, and active payment, shipping, tax, and order-total modules. These items determine whether the migrated data can be reviewed in a stable target store.

**Which product samples are most important for Zen Cart?**

Include products with categories, attributes, option values, price-changing choices, downloads, images, tax classes, stock behavior, specials, and SEO metadata. Attribute-heavy products are especially important because they reveal whether the source product structure translates cleanly into Zen Cart.

**Should payment and shipping modules be prepared before migration?**

Yes. Historical payment and shipping labels can be migrated for order history where supported, but live payment and shipping behavior depends on target module configuration. The target store should have a clear checkout, payment, shipping, tax, and order-total setup plan before launch validation.

**Why should plugins and custom tables be inventoried?**

Plugins and custom database structures can hold business-critical data that is not part of Zen Cart core records. If those fields, tables, or workflows must move into the Target Platform, they should be reviewed early because unsupported plugin or custom data is handled through Custom Service.

**What should be included in a Zen Cart Demo Migration sample?**

A useful Demo Migration sample should include complex products, categories, attributes, customers, addresses, orders with totals and selected options, coupons or gift certificates if used, EZ-Pages or CMS Pages, priority URLs, plugin-dependent records, and external-system references where they affect operations.
