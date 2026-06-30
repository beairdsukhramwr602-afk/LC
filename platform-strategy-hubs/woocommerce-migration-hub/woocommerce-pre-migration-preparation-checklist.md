# WooCommerce Pre-Migration Preparation Checklist

WooCommerce preparation should gather evidence that proves the target store can preserve both commerce data and WordPress-connected buying context. Products, variations, attributes, orders, customers, coupons, checkout fields, media, URLs, tax values, shipping records, payment labels, plugin data, and custom fields may all depend on WooCommerce settings, WordPress structure, extensions, themes, and outside systems.

Good preparation is not only a credential checklist. It should clarify what can be migrated as supported WooCommerce data, what requires Add-ons, what needs Custom Service review, what belongs to target-side setup, and what should be accepted as an exclusion. Without that distinction, Demo Migration can become a record-count review instead of a meaningful test of product behavior, order readability, content continuity, and launch readiness.

### What WooCommerce Preparation Should Confirm First <a href="#what-woocommerce-preparation-should-confirm-first" id="what-woocommerce-preparation-should-confirm-first"></a>

Preparation should begin with the target operating role. WooCommerce can support a compact catalog, a content-led store, a plugin-powered checkout flow, a subscription or membership business, a wholesale catalog, a downloadable-product store, or a custom WordPress commerce environment. Each target role changes the evidence that must be prepared.

| Preparation question                                                                    | Why it matters                                                                           | Evidence to collect                                                                                       |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Is WooCommerce the main commerce engine or part of a broader WordPress site?            | Defines whether content, media, users, menus, and plugin records are migration-critical. | Site map, content inventory, product URL examples, active plugin list.                                    |
| Which products create most revenue or support key campaigns?                            | Keeps preparation focused on commercially important product behavior.                    | Top-selling products, variable products, sale items, downloadable items, subscription or bundle examples. |
| Which extensions affect products, checkout, pricing, customers, orders, or fulfillment? | Extension-owned data may not behave like ordinary WooCommerce fields.                    | Plugin list, custom tables, configuration screenshots, sample records, external-system references.        |
| Are orders stored under HPOS or legacy order storage?                                   | Order metadata and extension compatibility can affect validation and support use.        | WooCommerce order-storage setting, extension compatibility notes, order metadata examples.                |
| Which URLs and SEO fields must survive launch?                                          | Product and category discovery depends on clean routes, redirects, and metadata.         | Top traffic URLs, product/category slugs, CMS Pages, Blog Posts, SEO plugin fields, redirect list.        |
| What will keep changing before launch?                                                  | Determines later migration activity and revalidation needs.                              | Expected new Products, Customers, Orders, Blog Posts, coupons, media, and content updates.                |

This first review prevents the migration from being framed too narrowly. A store may look like a WooCommerce product/customer/order project, but its real launch quality may depend on content pages, product filters, media files, checkout fields, extension data, or URL continuity.

### Prepare Product and Variation Evidence <a href="#prepare-product-and-variation-evidence" id="prepare-product-and-variation-evidence"></a>

Product preparation should separate ordinary product records from buying logic. WooCommerce product quality depends on whether the source catalog can be interpreted through product types, attributes, variations, stock, categories, tags, tax classes, shipping data, product visibility, reviews, and extension-controlled behavior.

| Product area                                                                       | Preparation action                                                                                                                       | Why it matters                                                                              |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Simple products                                                                    | Confirm SKU, name, description, price, sale price, stock, image, category, tag, visibility, and tax/shipping class.                      | Establishes baseline product migration quality.                                             |
| Variable products                                                                  | Identify parent products, variation attributes, variation SKUs, variation prices, stock, images, default selections, and purchasability. | Prevents options from becoming display-only text or disconnected child records.             |
| Product attributes                                                                 | Decide which values should be global attributes, variation attributes, visible product facts, filters, or internal metadata.             | Supports filters, variations, comparison, admin consistency, and customer-facing selection. |
| Categories, tags, and brands                                                       | Clean duplicate values, unclear hierarchies, unused labels, and inconsistent naming.                                                     | Protects navigation, filters, merchandising, and SEO routes.                                |
| Product reviews                                                                    | Decide whether review text, rating, author, date, approval status, and product links are required.                                       | Keeps social proof tied to the correct product.                                             |
| Downloadable and virtual products                                                  | Prepare file access, download limits, shipping exclusion, customer access, and order examples.                                           | Prevents digital-product behavior from being treated as ordinary physical goods.            |
| Product add-ons, bundles, bookings, subscriptions, memberships, or wholesale logic | Identify extension ownership and whether active behavior must continue after launch.                                                     | Clarifies Add-ons, Custom Service, target setup, or exclusion decisions.                    |

A useful sample set should include at least one simple product, one variable product, one discounted product, one out-of-stock or backorder case, one product with multiple images, one product with reviews, and one product governed by an extension or custom field. The sample set should prove product meaning, not only product presence.

### Prepare Orders, Customers, Checkout Fields, and HPOS Context <a href="#prepare-orders-customers-checkout-fields-and-hpos-context" id="prepare-orders-customers-checkout-fields-and-hpos-context"></a>

WooCommerce order and customer preparation should focus on readability, relationships, and account continuity. Historical orders may include customer identity, line items, variation choices, taxes, shipping, discounts, payment labels, refunds, notes, checkout fields, extension metadata, and external references. Customer records may depend on WordPress users, guest orders, roles, addresses, memberships, and plugin-controlled account logic.

| Data area                      | Preparation action                                                                                                             | Validation sample                                                                     |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Customer accounts              | Review registered customers, guest orders, billing/shipping addresses, duplicate emails, roles, and account metadata.          | Registered customer with multiple orders, guest order, customer with changed address. |
| Orders                         | Review statuses, line items, products, variations, totals, coupons, taxes, shipping, payment labels, refunds, and notes.       | Paid order, refunded order, discounted order, variable-product order, guest order.    |
| Checkout fields                | Identify standard fields, custom fields, conditional fields, delivery instructions, VAT/tax IDs, gift messages, or B2B fields. | Order with each important custom field populated.                                     |
| Customer roles and memberships | Separate WordPress roles from WooCommerce customer status and extension-owned membership logic.                                | Wholesale user, member, subscriber, learner, donor, or role-based account.            |
| External IDs                   | Collect ERP, CRM, shipping, payment, marketplace, fulfillment, or accounting references.                                       | Order/customer with external references.                                              |
| HPOS/order storage             | Confirm current order-storage mode and extension compatibility.                                                                | Order lookup, admin order screen, metadata visibility, plugin field visibility.       |

If historical orders must support customer service after launch, sample selection should include real operational cases, not only recent clean orders. Refunded orders, partially fulfilled orders, orders with custom checkout fields, orders tied to inactive products, and orders created by extensions often expose migration risk earlier than ordinary paid orders.

### Prepare Checkout, Payment, Shipping, Tax, and Coupon Context <a href="#prepare-checkout-payment-shipping-tax-and-coupon-context" id="prepare-checkout-payment-shipping-tax-and-coupon-context"></a>

WooCommerce migration can preserve historical labels, amounts, and selected stored values, but active checkout behavior depends on target configuration. Payment gateways, tax rules, shipping zones, carrier services, coupon rules, pickup/delivery flows, fraud tools, and checkout-field logic should be prepared as target-side operating work unless the requirement concerns stored historical data.

| Area            | Prepare for migration                                                                     | Prepare outside migration                                                                   |
| --------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Payment         | Historical payment labels, transaction references where available, order payment context. | Live gateway setup, saved payment tokens, fraud rules, credentials, payment-method testing. |
| Shipping        | Historical shipping method labels, amounts, addresses, tracking references where stored.  | Shipping zones, carrier rates, fulfillment rules, pickup/delivery workflows.                |
| Tax             | Historical tax totals, tax labels, tax-inclusive or tax-exclusive order context.          | Active tax rates, tax service integrations, jurisdiction setup, tax display rules.          |
| Coupons         | Coupon records, usage history where supported, discount lines in orders.                  | Active promotion strategy, complex discount rules, third-party promotion logic.             |
| Checkout fields | Stored order/customer field values.                                                       | Active field placement, validation, conditional logic, checkout user experience.            |

This separation is important because historical data can be migrated correctly while live checkout is still not ready. Preparation should assign ownership for target-side setup before Full Migration, especially when checkout, tax, shipping, or payment behavior affects launch acceptance.

### Prepare WordPress Site, Media, URL, and SEO Dependencies <a href="#prepare-wordpress-site-media-url-and-seo-dependencies" id="prepare-wordpress-site-media-url-and-seo-dependencies"></a>

WooCommerce lives inside WordPress, so commerce preparation should include the site structures that affect buying, discovery, trust, and support. These elements should not be treated as unrelated CMS details when they shape product discovery or customer confidence.

| Site element                       | Preparation action                                                                                                               | Why it matters                                                                                       |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| CMS Pages                          | Identify checkout-support pages, policy pages, landing pages, size guides, return pages, and product education pages.            | These pages support purchase decisions and post-order trust.                                         |
| Blog Posts                         | Identify buying guides, product comparisons, SEO posts, campaign posts, and support content.                                     | Blog Posts may drive product traffic and may consume Entity Points when migrated for the first time. |
| Media                              | Review featured images, galleries, downloadable files, embedded images, PDFs, and product-description assets.                    | Broken media weakens product display and content credibility.                                        |
| Menus, widgets, and internal links | Identify product/category links, footer policy links, account links, campaign links, and embedded product references.            | Navigation can break even when products migrate correctly.                                           |
| Themes and builders                | Identify shortcodes, blocks, builder templates, custom product layouts, and embedded product widgets.                            | Layout may depend on target theme or builder setup rather than migrated records alone.               |
| SEO and redirects                  | Collect product, category, page, post, and high-traffic URLs, slugs, meta titles, descriptions, canonical values, and redirects. | Launch quality depends on route continuity and search visibility.                                    |

WooCommerce preparation should therefore include both commerce records and the WordPress paths around them. A product can migrate correctly while a landing page, redirect, product link, embedded image, or menu path still weakens the customer journey.

### Prepare Plugin, Extension, and Custom Data Scope <a href="#prepare-plugin-extension-and-custom-data-scope" id="prepare-plugin-extension-and-custom-data-scope"></a>

WooCommerce stores often rely on extensions and plugins for business behavior. Preparation should classify plugin data before migration so the project does not discover late that essential behavior is stored outside ordinary WooCommerce records.

| Dependency type                                                                                        | Preparation question                                                                              | Likely handling path                                                              |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Plugin display settings                                                                                | Does the plugin only affect layout or presentation?                                               | Target setup or manual rebuild, usually not migrated data.                        |
| Supported extra fields                                                                                 | Are the values ordinary supported fields that need better mapping or filtering?                   | Add-ons may fit if the requirement stays within supported behavior.               |
| Custom checkout fields                                                                                 | Are stored values needed for historical order readability, live checkout behavior, or both?       | Add-ons, Custom Service, or target setup depending on data ownership.             |
| Custom tables                                                                                          | Does the plugin store important records outside ordinary WooCommerce/WordPress tables?            | Custom Service review when records are business-critical.                         |
| Subscriptions, bookings, memberships, bundles, composite products, product add-ons, or wholesale rules | Is the requirement stored history, active workflow behavior, or target configuration?             | Custom Service, target setup, accepted exclusion, or external integration review. |
| External-system references                                                                             | Do ERP, CRM, PIM, accounting, marketplace, shipping, or fulfillment IDs need to remain connected? | Custom Service review or external-system planning.                                |

Add-ons and Custom Service should remain separate during preparation. Add-ons help with bounded filtering, mapping, and supported configuration adjustments. Custom Service should be considered when the requirement depends on unsupported structures, plugin-owned records, custom fields, external identifiers, bespoke transformation, or custom migration logic adjustment.

### Prepare Access, Backups, and Target WooCommerce Setup <a href="#prepare-access-backups-and-target-woocommerce-setup" id="prepare-access-backups-and-target-woocommerce-setup"></a>

Access preparation should protect both migration execution and validation. The merchant should know who can access the source store, target WordPress/WooCommerce admin, hosting, database exports, media files, redirect tools, DNS, analytics, Search Console, SEO plugins, payment gateway records, shipping tools, and relevant integrations.

| Access or setup area | Preparation requirement                                                                                                           |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Source store         | Admin access, export access, database or file backups where available, media access, plugin list, order/customer/product samples. |
| Target WooCommerce   | WordPress admin access, WooCommerce setup, user roles, theme or builder decisions, plugin installation plan, staging environment. |
| Hosting and files    | Backup plan, media transfer plan, file permissions, downloadable-product files, performance expectations.                         |
| SEO and analytics    | URL lists, redirect tools, SEO metadata exports, analytics/search data, priority landing pages.                                   |
| Operations           | Payment gateway setup, tax/shipping configuration, fulfillment tools, email notifications, customer-account settings.             |

The target store should be prepared enough for Demo Migration review. It does not need every final design detail before migration testing, but it should not be an empty or unstable environment where product display, order review, media checks, and URL validation cannot be judged.

### Prepare Demo Migration Samples and Launch-Window Decisions <a href="#prepare-demo-migration-samples-and-launch-window-decisions" id="prepare-demo-migration-samples-and-launch-window-decisions"></a>

Demo Migration should test the records that carry WooCommerce meaning. A narrow sample of clean products and recent orders is not enough when the store depends on variations, extension fields, custom checkout values, content paths, media, or URL continuity.

| Sample type                  | What it should prove                                                                                              |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Simple product               | Baseline WooCommerce product fields migrate cleanly.                                                              |
| Variable product             | Attributes, variations, prices, stock, images, and purchasability remain meaningful.                              |
| Extension-influenced product | Add-ons, subscriptions, bundles, bookings, memberships, or wholesale behavior is classified correctly.            |
| Order with custom fields     | Checkout values, metadata, line items, taxes, shipping, payment labels, refunds, and notes remain readable.       |
| Customer with history        | Account details, addresses, roles, and order links remain coherent.                                               |
| Content and URL sample       | Product pages, categories, CMS Pages, Blog Posts, media, SEO fields, redirects, and internal links remain usable. |
| HPOS-sensitive order sample  | Order lookup, metadata visibility, and extension-related order information can be reviewed.                       |

Launch-window planning should also define what happens if the source store continues to change. If new Products, Customers, Orders, Blog Posts, coupons, or media are created after the first migration run, the team should plan whether to continue migration activity, continue with a new configuration, or perform a new migration. New eligible entities may consume Entity Points when migrated for the first time, while already recorded entities should not consume Entity Points again solely because another migration action occurs on the same migration path.

### Turning Preparation Into Scope Evidence <a href="#turning-preparation-into-scope-evidence" id="turning-preparation-into-scope-evidence"></a>

WooCommerce preparation should end with a scope decision, not a pile of exports. The merchant should know which data is standard migration scope, which needs Add-ons, which needs Custom Service review, which belongs to target setup, and which should be excluded.

| Prepared evidence                     | Scope decision it supports                                                          |
| ------------------------------------- | ----------------------------------------------------------------------------------- |
| Product and variation samples         | Whether product structure fits supported WooCommerce migration behavior.            |
| Order/customer samples                | Whether historical readability and account continuity can be validated.             |
| Checkout and HPOS evidence            | Whether custom fields, metadata, and storage assumptions need special review.       |
| Plugin and custom-data inventory      | Whether Add-ons, Custom Service, setup, integration work, or exclusions are needed. |
| Content, media, URL, and SEO evidence | Whether WordPress-connected commerce continuity is in scope.                        |
| Launch-window update plan             | Whether Additional Migration Options and Entity Points planning are required.       |

The practical goal is to make Demo Migration decisive. Preparation should give reviewers enough evidence to approve the approach, request Add-ons, escalate to Custom Service, accept exclusions, or adjust the target setup before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WooCommerce preparation is strongest when it treats the store as commerce inside WordPress, not as a simple product/order export. Products, variations, attributes, orders, customers, checkout fields, HPOS, coupons, reviews, plugins, custom data, media, URLs, SEO, and content paths all need evidence before the migration approach can be trusted.

A well-prepared WooCommerce migration separates migrated data from target setup, keeps Add-ons and Custom Service distinct, uses Demo Migration to test meaningful samples, and plans later migration activity before launch. That preparation gives the merchant a clearer path from source data to a usable WooCommerce store.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a WooCommerce migration?**

Start by defining the target store role. A simple catalog, content-led store, subscription business, plugin-powered checkout, wholesale catalog, or custom WordPress commerce environment will each require different evidence.

**Why are variable products important in WooCommerce preparation?**

Variable products depend on attributes, variations, prices, stock, images, and purchasability. If those relationships are not sampled before Demo Migration, product options may migrate as incomplete or unusable records.

**Should WooCommerce plugin data be treated as standard migration scope?**

No. Plugin data should be classified first. Some plugin values may fit supported mapping or Add-ons, while custom tables, extension-owned records, active workflow behavior, and external-system references may require Custom Service review or target setup.

**How should HPOS affect WooCommerce preparation?**

HPOS should prompt order-storage and metadata review. The team should confirm current order-storage mode, extension compatibility, order lookup behavior, and whether important order metadata remains visible after migration.

**How should Additional Migration Options be planned for WooCommerce?**

Plan them when the source store continues changing before launch. New Products, Customers, Orders, Blog Posts, coupons, or media may need later migration and revalidation, while already recorded entities should not consume Entity Points again solely because another migration action occurs on the same migration path.
