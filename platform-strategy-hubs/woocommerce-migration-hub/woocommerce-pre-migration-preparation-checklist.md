# WooCommerce Pre-Migration Preparation Checklist

WooCommerce migration preparation should begin with a clear inventory of what makes the store work as a WordPress-connected commerce site. Products, variations, orders, customers, coupons, checkout fields, media, URLs, tax values, shipping methods, payment labels, plugin records, and custom fields may all depend on WordPress structure, WooCommerce settings, extensions, themes, and external systems.

Good preparation does not only collect access credentials or export files. It defines which data must be migrated as standard commerce records, which values require Add-ons, which workflows require target configuration, which plugin-owned data needs Custom Service review, and which legacy records can be accepted as exclusions. This helps prevent a Demo Migration from becoming a surface-level record-count check instead of a meaningful proof of store behavior.

### What WooCommerce Preparation Should Confirm First <a href="#what-woocommerce-preparation-should-confirm-first" id="what-woocommerce-preparation-should-confirm-first"></a>

WooCommerce preparation should confirm the role of the target store before individual data fields are reviewed. A WooCommerce migration can support a simple product catalog, a content-heavy commerce site, a plugin-powered store, a subscription or membership business, a wholesale catalog, or a custom checkout workflow. Each case changes what must be sampled, mapped, and tested.

| Preparation question                                                             | Why it matters                                                                | Evidence to collect                                                                  |
| -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Is WooCommerce the main commerce engine or only part of a larger WordPress site? | Defines whether content, media, users, and plugin data are migration-critical | Store map, content inventory, product URL examples, plugin list                      |
| Which products generate revenue today?                                           | Prevents low-value catalog records from distracting from commercial behavior  | Top-selling products, variable products, sale items, subscriptions, bundles, add-ons |
| Which plugins affect checkout, pricing, products, customers, or orders?          | Plugin-owned data may not behave like ordinary WooCommerce records            | Active plugin list, custom tables, plugin fields, external-system references         |
| Are orders stored with HPOS or legacy order storage?                             | Order metadata and extension compatibility may affect validation              | WooCommerce settings, HPOS status, order plugin compatibility notes                  |
| Which URLs and SEO fields must survive launch?                                   | Product and category discovery depends on clean routes and redirects          | Top traffic URLs, product/category slugs, SEO plugin fields, redirect list           |
| What data will keep changing before launch?                                      | Determines follow-up migration and revalidation needs                         | Expected new Products, Customers, Orders, Blog Posts, coupons, and content updates   |

### Prepare Product and Variation Scope <a href="#prepare-product-and-variation-scope" id="prepare-product-and-variation-scope"></a>

Product preparation should separate simple records from products that carry buying logic. WooCommerce can store many product structures, but migration quality depends on whether the source product model has been classified correctly before Demo Migration.

| Product area                                                          | Preparation action                                                                                                             | Why it matters                                                         |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| Simple products                                                       | Confirm SKU, name, description, price, sale price, stock, images, categories, tags, status, visibility, and tax/shipping class | Establishes baseline product migration quality                         |
| Variable products                                                     | Identify parent products, variation attributes, variation SKUs, prices, stock, images, default selections, and purchasability  | Prevents options from becoming display-only text                       |
| Product attributes                                                    | Decide which values should be global attributes, variation attributes, visible product facts, or internal metadata             | Supports filters, variations, comparison, and admin consistency        |
| Categories, tags, and brands                                          | Clean duplicate values, unclear hierarchies, and unused labels                                                                 | Protects navigation, filters, merchandising, and SEO routes            |
| Reviews                                                               | Decide whether review content, author names, ratings, dates, and product links are required                                    | Keeps social proof connected to the correct products                   |
| Product add-ons and custom inputs                                     | Separate simple stored values from active pricing, validation, and order-output behavior                                       | Clarifies Add-ons, Custom Service, or target plugin setup              |
| Subscriptions, bookings, memberships, bundles, and composite products | Identify extension ownership and whether the active workflow must be preserved                                                 | Prevents plugin behavior from being mistaken for standard product data |

A useful product sample should include at least one simple product, one variable product, one discounted product, one out-of-stock or backorder case, one product with multiple images, one product with reviews, and any product governed by add-ons, subscriptions, bundles, bookings, memberships, or wholesale logic.

### Prepare Order, Customer, and Account History <a href="#prepare-order-customer-and-account-history" id="prepare-order-customer-and-account-history"></a>

WooCommerce order and customer preparation should focus on readability and relationships. Historical orders are not only totals. They include customer identity, line items, variation choices, taxes, shipping, discounts, payment labels, refunds, notes, checkout fields, plugin metadata, and external references.

| Data area                      | Preparation action                                                                                                            | Validation sample                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Customer accounts              | Review registered customers, guest orders, billing/shipping addresses, duplicate emails, roles, and account metadata          | Customer with multiple orders, guest order, customer with changed address         |
| Orders                         | Review status, line items, products, variations, totals, coupons, taxes, shipping, payment labels, refunds, and notes         | Paid order, refunded order, discounted order, variable-product order, guest order |
| Checkout fields                | Identify standard fields, custom fields, conditional fields, delivery instructions, VAT/tax IDs, gift messages, or B2B fields | Order with each required custom field populated                                   |
| Customer roles and memberships | Separate WordPress roles from WooCommerce customer status and extension-owned memberships                                     | Wholesale user, member, subscriber, learner, donor, or role-based account         |
| External IDs                   | Collect ERP, CRM, shipping, payment, marketplace, fulfillment, or accounting IDs                                              | Order/customer with external references                                           |
| HPOS/order storage             | Confirm current WooCommerce order-storage mode and related extension compatibility                                            | Order lookup, admin order screen, metadata visibility                             |

If order history must support customer service after launch, sample selection should include real operational cases, not only recent clean orders. Older orders, refunded orders, partially fulfilled orders, orders with custom checkout fields, and orders tied to inactive products often expose migration risk earlier.

### Prepare Checkout, Payment, Shipping, Tax, and Coupon Context <a href="#prepare-checkout-payment-shipping-tax-and-coupon-context" id="prepare-checkout-payment-shipping-tax-and-coupon-context"></a>

WooCommerce migration can preserve historical labels and amounts, but active checkout behavior depends on target configuration, extensions, gateways, tax tools, shipping zones, carrier services, and custom validation. Preparation should separate historical order readability from live operational setup.

| Area            | Prepare for migration                                                                                 | Prepare outside migration                                                        |
| --------------- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Payment         | Historical payment labels, transaction references if available, order payment context                 | Live gateway setup, saved payment tokens, fraud rules, gateway credentials       |
| Shipping        | Historical shipping method labels, amounts, order shipping addresses, tracking references when stored | Live shipping zones, carrier rates, fulfillment rules, pickup/delivery workflows |
| Tax             | Historical tax totals, tax labels, tax-inclusive or tax-exclusive order context                       | Active tax rates, tax service integrations, jurisdiction setup                   |
| Coupons         | Coupon records, coupon usage history, discount lines in orders                                        | Active coupon strategy, complex promotion rules, third-party discount logic      |
| Checkout fields | Stored order/customer field values                                                                    | Active field placement, validation, conditional logic, checkout UX               |

### Prepare WordPress Site Dependencies <a href="#prepare-wordpress-site-dependencies" id="prepare-wordpress-site-dependencies"></a>

WooCommerce lives inside WordPress, so commerce preparation should include site structures that affect buying, discovery, trust, and customer support. These items should not be treated as unrelated CMS details when they shape the shopping path.

| Site element        | Preparation action                                                                                                              | Why it matters                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| CMS Pages           | Identify checkout-support pages, policy pages, landing pages, size guides, return pages, and product education pages            | These pages support purchase decisions and post-order trust                                     |
| Blog Posts          | Identify commerce-supporting posts, buying guides, product comparisons, and SEO posts                                           | Blog Posts may drive product traffic and consume Entity Points when migrated for the first time |
| Media               | Review featured images, galleries, downloadable files, embedded images, PDFs, and product-description assets                    | Broken media weakens product display and content credibility                                    |
| Menus and widgets   | Identify product/category links, footer policy links, account links, and campaign links                                         | Navigation can break even when products migrate correctly                                       |
| Themes and builders | Identify shortcodes, blocks, builder templates, custom product layouts, and embedded product widgets                            | Layout may depend on target theme/builder setup rather than migrated records alone              |
| SEO and redirects   | Collect product, category, page, post, and high-traffic URLs, slugs, meta titles, descriptions, canonical values, and redirects | Launch quality depends on route continuity and search visibility                                |

### Prepare Plugin, Extension, and Custom Data Scope <a href="#prepare-plugin-extension-and-custom-data-scope" id="prepare-plugin-extension-and-custom-data-scope"></a>

WooCommerce stores often rely on extensions and plugins for business behavior. Preparation should classify plugin data before migration so the project does not discover late that essential behavior is stored outside standard product, customer, and order records.

| Plugin/data pattern                                                                               | Preparation classification               | Likely handling                                         |
| ------------------------------------------------------------------------------------------------- | ---------------------------------------- | ------------------------------------------------------- |
| Clear extra product, customer, order, or content fields                                           | Field mapping scope                      | Add-ons or supported mapping                            |
| Product add-ons, personalization, or custom inputs                                                | Stored value plus active behavior review | Add-ons, target plugin setup, or Custom Service         |
| Subscriptions, bookings, memberships, deposits, bundles, composite products, or wholesale pricing | Extension-owned commerce behavior        | Custom Service review or accepted exclusion             |
| Custom database tables                                                                            | Non-standard storage                     | Custom Service review                                   |
| ERP, CRM, PIM, WMS, marketplace, accounting, analytics, or email tools                            | External-system ownership                | Integration mapping or accepted outside-migration setup |
| Shortcodes, blocks, builder fields, or theme templates                                            | Presentation dependency                  | Target theme/builder planning and validation            |

### Prepare Add-ons, Custom Service, and Exclusions <a href="#prepare-add-ons-custom-service-and-exclusions" id="prepare-add-ons-custom-service-and-exclusions"></a>

Preparation should identify scope boundaries before the Demo Migration. This prevents merchants from expecting every plugin behavior, custom workflow, or external integration to transfer as part of standard data movement.

| Need                                                               | Better classification                  | Preparation evidence                                                    |
| ------------------------------------------------------------------ | -------------------------------------- | ----------------------------------------------------------------------- |
| Extra field values with clear source and target meaning            | Add-ons                                | Field list, examples, target destination, sample records                |
| Data filtering, extra URL handling, or supported metadata handling | Add-ons or target configuration        | Rules, examples, expected output                                        |
| Plugin-owned active behavior or custom table relationships         | Custom Service review                  | Plugin name, field/table evidence, workflow examples, business priority |
| Live payment/shipping/tax/fraud/fulfillment behavior               | Target configuration or external setup | Current provider list, target setup plan, accepted exclusions           |
| Low-value historical data with unclear use                         | Accepted exclusion                     | Business decision and launch impact assessment                          |

Custom Service should be considered when WooCommerce migration requires custom interpretation, custom table handling, extension-specific transformation, non-standard checkout logic, or integration-owned workflow preservation. Custom Service does not automatically mean Next-Cart performs the entire store build or live operational setup.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration should prove WooCommerce migration behavior through representative samples. A shallow sample can make migration look successful while missing the records that carry real store complexity.

| Sample type      | Include examples that test                                                                                                                                                |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product samples  | Simple products, variable products, sale products, out-of-stock products, add-on products, downloadable products, subscription/booking/membership/bundle cases if present |
| Order samples    | Guest orders, registered-customer orders, refunded orders, discounted orders, tax/shipping/payment examples, custom checkout fields, orders with variation line items     |
| Customer samples | Multiple-address customers, customers with order history, customers with roles/memberships, customers with external IDs                                                   |
| Content samples  | Product pages, categories, CMS Pages, Blog Posts, embedded media, internal links, SEO fields, redirects                                                                   |
| Plugin samples   | Product add-ons, custom fields, subscriptions, bookings, memberships, wholesale values, custom tables, external references                                                |
| URL samples      | High-traffic product/category/page/post paths and routes that changed during redesign or platform planning                                                                |

### Prepare Entity Points and Follow-Up Migration Planning <a href="#prepare-entity-points-and-follow-up-migration-planning" id="prepare-entity-points-and-follow-up-migration-planning"></a>

Entity Points planning should be tied to migration scope and launch timing. WooCommerce stores often continue receiving new products, customers, orders, Blog Posts, media updates, coupon changes, and plugin data while migration work is underway.

| Planning area                 | Preparation action                                                                                                            |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Initial scope                 | Confirm which Products, Customers, Orders, Blog Posts, and other relevant records will be counted through the service license |
| New eligible records          | Track new Product, Customer, Order, and Blog Posts records that may consume Entity Points when migrated for the first time    |
| Duplicate-consumption control | Do not count records again only because another migration action is performed                                                 |
| Follow-up review              | Recheck new products, orders, customers, Blog Posts, coupons, URLs, and plugin fields before launch                           |
| Scope boundary                | Separate standard records, Add-ons, Custom Service candidates, configuration tasks, and exclusions                            |

Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when migrated for the first time, including when a new migration is performed for the same migration path.

### WooCommerce Preparation Readiness Matrix <a href="#woocommerce-preparation-readiness-matrix" id="woocommerce-preparation-readiness-matrix"></a>

| Area           | Ready signal                                                                                       | Not-ready signal                                                                               | Recommended action                                                |
| -------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Products       | Product types, variations, attributes, images, prices, stock, and categories are clear             | Add-ons, bundles, subscriptions, bookings, or custom fields are undocumented                   | Expand product sample and classify extension scope                |
| Orders         | Statuses, line items, taxes, shipping, payment labels, refunds, notes, and metadata are understood | Order meaning depends on plugins, custom checkout fields, HPOS-sensitive data, or external IDs | Prepare order sample and storage review                           |
| Customers      | Account links, addresses, roles, and order history are clear                                       | Membership, wholesale, subscription, role, or external account data is unclear                 | Separate standard customer data from plugin-owned account meaning |
| Checkout       | Historical field values and active configuration are separated                                     | Live payment/shipping/tax/fraud behavior is expected to transfer as data                       | Define target setup and accepted exclusions                       |
| WordPress site | Pages, posts, media, menus, URLs, redirects, and SEO fields are inventoried                        | Product traffic depends on unreviewed content or builder output                                | Prepare content and URL sample                                    |
| Plugins        | Plugin-owned fields and custom tables are documented                                               | Required behavior is hidden in extensions or custom code                                       | Decide Add-ons, Custom Service, configuration, or exclusion       |
| Launch timing  | New records and follow-up activity are tracked                                                     | Final scope is assumed to match the first migration run                                        | Plan Additional Migration Options review                          |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WooCommerce preparation should make the store’s commerce meaning visible before migration begins. Products, variations, orders, customers, checkout fields, plugins, media, URLs, SEO fields, and WordPress site dependencies should be reviewed according to their role in the buying journey and store operation.

A strong preparation plan separates standard migration scope, Add-ons, Custom Service needs, target configuration, external-system setup, accepted exclusions, Entity Points, and follow-up migration planning. This gives Demo Migration a real proof role and reduces the risk of discovering critical WooCommerce behavior only after Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should a WooCommerce store prepare before migration?**

A WooCommerce store should prepare product and variation samples, customer and order samples, checkout field examples, plugin and extension lists, media and URL inventories, SEO priorities, HPOS/order-storage context, integration references, and a clear distinction between standard migration scope, Add-ons, Custom Service needs, configuration tasks, and exclusions.

**Should WordPress content be included in WooCommerce preparation?**

Yes, when that content supports commerce. CMS Pages, Blog Posts, policy pages, product guides, media, menus, widgets, redirects, and SEO fields may affect product discovery, checkout trust, customer support, and launch continuity.

**Why do plugins matter so much in WooCommerce preparation?**

Plugins may own product add-ons, subscriptions, bookings, memberships, wholesale pricing, checkout fields, custom tables, SEO fields, forms, external IDs, or integration workflows. These records may need Add-ons, target configuration, Custom Service review, or accepted exclusion decisions.

**Does preparing WooCommerce orders only mean exporting order records?**

No. Order preparation should include status meaning, line items, variation details, taxes, shipping, payment labels, refunds, notes, custom checkout fields, customer links, metadata, HPOS/order-storage behavior, and external references.

**How should Additional Migration Options be considered during preparation?**

Additional Migration Options should be considered when the WooCommerce store continues changing before launch. New products, customers, orders, Blog Posts, coupons, URLs, and plugin fields may need renewed review, while records already counted through the service license should not consume Entity Points again only because another migration action is performed.
