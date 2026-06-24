# WooCommerce Data Model Differences

WooCommerce migration is a translation into a WordPress-connected commerce data model. Products, customers, orders, coupons, categories, tags, media, and content may look familiar across platforms, but their meaning changes once they depend on WooCommerce product types, WordPress taxonomies, post metadata, plugin-owned fields, checkout configuration, HPOS order storage, permalink rules, themes, builders, and integration workflows.

A successful WooCommerce migration therefore cannot be evaluated only by whether records appear in the Target Platform. It must prove that migrated data still supports the commercial job it performed in the Source Platform: customers can find the right products, choose valid options, see accurate prices and stock, place orders through the intended checkout flow, read historical order context, access accounts, follow important URLs, and keep operational data usable for staff and connected systems.

### Why WooCommerce Data-Model Differences Matter <a href="#why-woocommerce-data-model-differences-matter" id="why-woocommerce-data-model-differences-matter"></a>

WooCommerce is flexible because commerce data runs inside WordPress. That flexibility gives merchants control over content, URLs, plugins, checkout, custom fields, templates, media, and integrations. It also means that migration planning must separate ordinary WooCommerce records from WordPress site records and from extension-controlled data.

| Data layer     | WooCommerce interpretation                                                                        | Migration planning question                                                                       |
| -------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Product data   | Products may be simple, variable, grouped, external, or extension-controlled                      | Does each product type preserve the way the item is actually bought?                              |
| Variation data | Variation records can carry their own SKU, price, stock, image, dimensions, and purchasable state | Which source options should become true WooCommerce variations?                                   |
| Attribute data | Attributes can support variation, filtering, comparison, and product information                  | Which attributes drive buying, discovery, or display only?                                        |
| Taxonomy data  | Categories, tags, brands, and custom product taxonomies shape navigation and filtering            | Which taxonomy layer owns primary catalog structure?                                              |
| Order data     | Orders include line items, status, totals, taxes, shipping, payment labels, notes, and metadata   | Does historical order context remain readable and useful?                                         |
| WordPress data | CMS Pages, Blog Posts, users, media, menus, and URLs influence the commerce journey               | Which content and site records must remain connected to commerce?                                 |
| Plugin data    | Extensions may store business rules in metadata, custom tables, or external systems               | Is the data standard scope, Add-ons scope, Custom Service scope, or post-migration configuration? |

### WooCommerce Products Are WordPress-Commerce Records <a href="#woocommerce-products-are-wordpress-commerce-records" id="woocommerce-products-are-wordpress-commerce-records"></a>

WooCommerce products are not just generic catalog rows. They are commerce records that also live within the WordPress ecosystem. That means product data can be affected by post status, slug, media relationships, taxonomies, metadata, theme display, search behavior, product visibility, and plugins.

| Product element            | Data-model meaning in WooCommerce                                         | Review priority                                                                            |
| -------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Product title and slug     | Identifies the product and contributes to URL behavior                    | Confirm naming, duplicate handling, and permalink impact                                   |
| Short and full description | Supports product detail display, SEO, and merchandising                   | Check formatting, media embeds, shortcodes, and builder content                            |
| Product type               | Controls how the product is purchased or displayed                        | Confirm whether each item should be simple, variable, grouped, external, or plugin-handled |
| SKU                        | Supports product identity, lookup, inventory, reporting, and integrations | Check SKU uniqueness and variation-level SKU needs                                         |
| Images and galleries       | Connect products to WordPress media records                               | Confirm featured images, gallery order, alt text, and variation images                     |
| Stock status               | Affects purchasability and customer-facing availability                   | Check product-level and variation-level inventory meaning                                  |
| Visibility                 | Controls whether products appear in catalog, search, or hidden contexts   | Confirm hidden, private, draft, and catalog/search visibility assumptions                  |
| Metadata                   | Stores extra product context, plugin fields, and custom values            | Classify which metadata must be preserved, mapped, rebuilt, or excluded                    |

### Product Types Change Migration Meaning <a href="#product-types-change-migration-meaning" id="product-types-change-migration-meaning"></a>

WooCommerce product types create different target meanings for similar source records. A source product with options, add-ons, bundles, or external purchasing behavior should not be converted mechanically without understanding how customers are supposed to buy it after migration.

| Source-side pattern                                                                   | Possible WooCommerce interpretation                                | Risk if handled mechanically                                                       |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| One product with no purchasable options                                               | Simple product                                                     | Usually straightforward, but stock, tax, shipping, and media still need validation |
| Product with selectable options that change price, stock, SKU, image, or availability | Variable product with variations                                   | Options may be flattened into text instead of becoming purchasable choices         |
| Product family shown as related standalone items                                      | Grouped product or separate simple products                        | Relationship may be lost or wrongly merged                                         |
| Product sold through another site or quote path                                       | External/affiliate product or custom workflow                      | Checkout expectation may not match target behavior                                 |
| Product with paid add-ons or configurable inputs                                      | Product add-ons extension, custom fields, or Custom Service review | Add-on logic may be mistaken for native variations                                 |
| Subscription, booking, membership, bundle, or composite product                       | Extension-governed commerce behavior                               | Active commercial logic may sit outside standard migration scope                   |

### Variations and Attributes Require Separate Interpretation <a href="#variations-and-attributes-require-separate-interpretation" id="variations-and-attributes-require-separate-interpretation"></a>

WooCommerce variable products depend on the relationship between a parent product, attributes, and individual variations. A variation is not just a label. It can carry independent price, SKU, stock, image, weight, dimensions, purchasability, and sale behavior.

| Choice type                                                | Best WooCommerce treatment                              | What to validate                                                                    |
| ---------------------------------------------------------- | ------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Size/color choices that change purchasable SKU             | Variation attributes and variation records              | Parent product, variation values, SKU, price, stock, images, and default selections |
| Descriptive information that customers filter by           | Product attributes, taxonomy terms, or custom fields    | Attribute naming, value consistency, filter behavior, and display placement         |
| Optional personalization or paid add-on fields             | Extension-managed product add-ons or custom fields      | Whether field values affect price, fulfillment, order detail, or customer input     |
| Compatibility, dimensions, material, or technical specs    | Attributes or custom fields depending on target display | Whether values support filtering, comparison, or display only                       |
| Source modifiers that do not map to WooCommerce variations | Add-ons or Custom Service review                        | Whether bespoke transformation or extension-aware handling is required              |

The most common WooCommerce data-model mistake is treating every source option as the same kind of WooCommerce field. A purchasable variation, a filterable attribute, an add-on, a custom field, and a descriptive label may all look like “options” in the source store, but they should not be migrated into the same target structure.

### Categories, Tags, Brands, and Product Taxonomies Have Distinct Roles <a href="#categories-tags-brands-and-product-taxonomies-have-distinct-roles" id="categories-tags-brands-and-product-taxonomies-have-distinct-roles"></a>

WooCommerce uses WordPress-style taxonomies to organize product discovery. Product categories usually carry the main catalog hierarchy. Tags support flexible grouping. Brands may depend on WooCommerce or an extension. Custom product taxonomies may support filtering, compatibility, product type, vendor, industry, use case, or merchandising logic.

| Taxonomy type             | Typical WooCommerce role                                                    | Data-model review question                                                              |
| ------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Product categories        | Primary catalog hierarchy, navigation, merchandising, and SEO landing paths | Does the category tree match how customers browse?                                      |
| Product tags              | Loose grouping, campaign labels, secondary discovery                        | Are tags useful, or are they compensating for poor category/attribute structure?        |
| Product brands            | Brand-led discovery, filters, landing pages, and SEO                        | Is brand stored in a native field, taxonomy, attribute, or plugin-specific structure?   |
| Product attributes        | Structured product traits, variation choices, filters, and comparisons      | Which attributes should be global, local, visible, variation-enabled, or filterable?    |
| Custom product taxonomies | Plugin/theme/search/filter behavior                                         | Does the target store need the taxonomy for customer experience or internal admin only? |

Taxonomy cleanup is often as important as record transfer. Duplicated values, inconsistent casing, mixed languages, and overlapping category/tag/attribute usage can survive migration while producing poor filtering and weak navigation.

### Orders Depend on WooCommerce and Storage Context <a href="#orders-depend-on-woocommerce-and-storage-context" id="orders-depend-on-woocommerce-and-storage-context"></a>

WooCommerce order data is both a commercial history record and an operational reference. It may include line items, customer association, billing and shipping addresses, coupons, taxes, shipping methods, payment method labels, statuses, refunds, notes, downloads, and metadata. With HPOS, order data can also involve dedicated order tables and compatibility considerations for extensions that interact with order records.

| Order element                  | Data-model meaning                                                              | Validation priority                                                           |
| ------------------------------ | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Order status                   | Operational stage, reporting category, and support context                      | Map source statuses to readable WooCommerce outcomes                          |
| Line items                     | Purchased products, quantities, variation choices, taxes, discounts, and totals | Confirm product associations, SKU visibility, and variation meaning           |
| Billing and shipping addresses | Customer service, fulfillment, tax, and historical order context                | Verify address structure and country/state formatting                         |
| Payment labels                 | Historical payment method context, not necessarily active gateway logic         | Confirm historical readability without implying payment reprocessing          |
| Shipping labels                | Historical fulfillment context, not necessarily active shipping-rate logic      | Confirm method names and cost breakdowns remain understandable                |
| Coupons and discounts          | Commercial adjustment history                                                   | Validate coupon codes, line-level discounts, and totals                       |
| Refunds and notes              | Support and accounting context                                                  | Confirm refunds, partial refunds, customer notes, and admin notes if in scope |
| Order metadata                 | Checkout fields, extension data, integration references, and operational notes  | Classify metadata by business value and target destination                    |

Historical order migration should not be judged only by whether the order count matches. Staff should be able to open sample orders and understand what was purchased, who purchased it, what was paid, how it was shipped, and what operational context still matters.

### Customer Data and Account Meaning Are Not the Same <a href="#customer-data-and-account-meaning-are-not-the-same" id="customer-data-and-account-meaning-are-not-the-same"></a>

A WooCommerce customer record may preserve identity, email, names, billing address, shipping address, order association, and account history. That does not automatically preserve the full customer experience. Login behavior, passwords, customer roles, memberships, wholesale access, subscriptions, downloads, loyalty points, or account-based pricing may depend on WordPress users, WooCommerce records, plugins, or external systems.

| Customer-related data          | Possible target meaning                                                    | Review question                                                  |
| ------------------------------ | -------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Customer profile               | WooCommerce customer/account record                                        | Is account access required or mainly historical?                 |
| WordPress user                 | Login identity, role assignment, author/member/subscriber status           | Which roles and capabilities should remain?                      |
| Billing and shipping addresses | Checkout convenience and historical order context                          | Are addresses complete and formatted correctly?                  |
| Customer role/group            | Membership, wholesale, B2B, loyalty, pricing, or access behavior           | Is the role native, plugin-owned, or external-system controlled? |
| Password behavior              | Login continuity or password-reset workflow                                | Is password continuity supported for the migration path?         |
| Customer metadata              | Marketing preferences, segmentation, external IDs, consent, or plugin data | Which fields are business-critical and where should they live?   |

### Coupons, Taxes, Shipping, Payments, and Checkout Fields Need Purpose-Based Review <a href="#coupons-taxes-shipping-payments-and-checkout-fields-need-purpose-based-review" id="coupons-taxes-shipping-payments-and-checkout-fields-need-purpose-based-review"></a>

WooCommerce checkout data combines migrated history, future configuration, and active store behavior. Historical orders may preserve tax, shipping, payment, discount, and checkout-field context, while active tax rules, shipping zones, payment gateways, fraud tools, and checkout fields often require configuration rather than direct data migration.

| Area            | Migrated-data concern                                         | Configuration or Custom Service concern                                                   |
| --------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Coupons         | Historical coupon codes, discount amounts, order associations | Active coupon rules, restrictions, usage limits, and expiry logic                         |
| Taxes           | Historical tax totals, labels, rates, and order breakdowns    | Active tax configuration, tax classes, nexus logic, and external tax apps                 |
| Shipping        | Historical shipping method labels and costs                   | Active shipping zones, methods, rates, carrier integrations, and fulfillment rules        |
| Payments        | Historical payment method labels and transaction references   | Active gateway configuration, credentials, token behavior, and payment workflows          |
| Checkout fields | Custom values attached to customers or orders                 | Field display, validation, conditional logic, storage destination, and HPOS compatibility |

### Plugin and Extension Data Must Be Classified Before Migration <a href="#plugin-and-extension-data-must-be-classified-before-migration" id="plugin-and-extension-data-must-be-classified-before-migration"></a>

WooCommerce stores often depend on plugins for subscriptions, bookings, memberships, product add-ons, bundles, composite products, wholesale pricing, loyalty points, payment workflows, fulfillment, invoices, customer segmentation, B2B features, search, reviews, and analytics. Some plugin outputs may be stored in postmeta, usermeta, order metadata, custom tables, or external systems.

| Plugin-data pattern                                     | Likely handling                                             | Why it matters                                                             |
| ------------------------------------------------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------- |
| Display-only product metadata                           | Standard scope or Add-ons depending on field structure      | Preserves product information without necessarily driving behavior         |
| Custom checkout/order fields                            | Add-ons or Custom Service depending on storage and behavior | Affects order readability, admin workflows, and customer support           |
| Subscription, booking, membership, or wholesale records | Custom Service review may be needed                         | Active relationships and future behavior may not be ordinary data records  |
| Custom tables                                           | Custom Service review                                       | Data may not be accessible through standard product/order/customer mapping |
| External IDs and integration references                 | Add-ons or Custom Service depending on transformation needs | Keeps ERP, CRM, PIM, WMS, accounting, or analytics continuity possible     |
| Active app logic                                        | Configuration, extension setup, or Custom Service           | Data transfer alone cannot recreate active rules or workflows              |

### CMS Pages, Blog Posts, Media, URLs, and SEO Remain Connected to Commerce <a href="#cms-pages-blog-posts-media-urls-and-seo-remain-connected-to-commerce" id="cms-pages-blog-posts-media-urls-and-seo-remain-connected-to-commerce"></a>

WooCommerce data lives within a WordPress site, so commerce migration can be affected by content and route decisions. CMS Pages, Blog Posts, product landing pages, category descriptions, menus, widgets, media attachments, internal links, product embeds, related content, SEO metadata, redirects, and permalink structures can all influence the customer journey.

| Content-commerce element | Data-model concern                                                    | Migration planning implication                                                 |
| ------------------------ | --------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| CMS Pages                | Checkout pages, policy pages, landing pages, product guides, FAQs     | Preserve pages that support buying and compliance                              |
| Blog Posts               | Content-led discovery and internal linking                            | Preserve links, images, embedded products, and high-value posts where relevant |
| Media                    | Product images, galleries, downloadable files, embedded assets        | Validate attachment relationships, alt text, filenames, and gallery order      |
| Menus and widgets        | Navigation and product discovery                                      | Confirm target theme/builder handling and menu destinations                    |
| Permalinks and redirects | Product, category, tag, page, and post routes                         | Map high-value routes and validate redirects after migration                   |
| SEO metadata             | Titles, descriptions, canonical values, schema fields, index settings | Determine which SEO fields are standard, plugin-owned, or Custom Service scope |

### Entity Points and WooCommerce Data Scope <a href="#entity-points-and-woocommerce-data-scope" id="entity-points-and-woocommerce-data-scope"></a>

Entity Points planning should reflect which eligible records are migrated for the first time. New Product, Customer, Order, and Blog Posts records consume Entity Points when they are first migrated. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when migrated for the first time, including when the customer performs a new migration for the same migration path.

| WooCommerce scope area  | Entity Points relevance                                                | Practical review question                                                              |
| ----------------------- | ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Products and variations | Product records may be counted according to migration scope            | Which product records are new and eligible for first-time migration?                   |
| Customers               | Customer records can affect service-license and Entity Points planning | Are new customer records being added after initial scope calculation?                  |
| Orders                  | Order history can be a major scope driver                              | Are new orders being added and migrated for the first time?                            |
| Blog Posts              | Content-led WooCommerce stores may include Blog Posts scope            | Are new Blog Posts being migrated for the first time?                                  |
| Plugin-owned records    | May not map directly to standard Entity Points categories              | Should the work be classified as Add-ons, Custom Service, configuration, or exclusion? |

### WooCommerce Data-Model Decision Matrix <a href="#woocommerce-data-model-decision-matrix" id="woocommerce-data-model-decision-matrix"></a>

| Decision area    | Standard mapping signal                                                                                           | Add-ons signal                                                        | Custom Service signal                                                                                             |
| ---------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Products         | Simple or variable product data with clear categories, attributes, prices, stock, images, and SKUs                | Extra field mapping, filtering, or supported configuration refinement | Bespoke product structures, custom tables, nonstandard source behavior, or plugin-controlled product logic        |
| Orders           | Historical orders with readable line items, totals, customer links, taxes, shipping, payment labels, and statuses | Extra metadata mapping or field handling                              | Custom order logic, plugin records, unsupported order schemas, or special HPOS-sensitive interpretation           |
| Customers        | Customer profiles, addresses, and order associations are clear                                                    | Extra customer metadata or segmentation mapping                       | Membership, wholesale, subscription, loyalty, or external account behavior needs custom review                    |
| Content and URLs | CMS Pages, Blog Posts, media, slugs, and redirects are clear                                                      | Extra URL, metadata, or field handling                                | Theme/builder reconstruction, shortcode logic, custom routes, or SEO-plugin transformation needs bespoke handling |
| Integrations     | External IDs are preserved as reference fields                                                                    | Mapping is needed for known integration identifiers                   | Active ERP, CRM, PIM, WMS, payment, fulfillment, or marketplace logic must be interpreted or rebuilt              |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WooCommerce data-model review should focus on business meaning, not record presence alone. Products, variations, attributes, categories, customers, orders, coupons, checkout fields, media, URLs, and WordPress content may all migrate successfully as records while still failing to support the intended storefront or operational workflow.

A strong WooCommerce migration plan identifies which structures are standard WooCommerce data, which require Add-ons, which depend on configuration after migration, and which require Custom Service review. The most important review areas are variable-product logic, attribute purpose, customer and order meaning, plugin-owned records, HPOS-sensitive order context, checkout metadata, SEO-sensitive routes, and integration references.

Use representative samples during Demo Migration and Full Migration review. If a sample product, order, customer, checkout field, plugin record, or URL cannot be explained clearly in the Target Platform, the data model needs refinement before the migration result can be treated as reliable.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is WooCommerce data-model review different from generic WordPress migration review?**

WooCommerce adds commerce meaning to WordPress records. Products, variations, orders, customers, coupons, checkout fields, stock, prices, and payment or shipping context need commerce validation, while generic WordPress migration mainly focuses on content, media, users, URLs, and site structure.

**Are WooCommerce variations the same as source product options?**

Not always. A WooCommerce variation is a purchasable child option that can carry its own SKU, price, stock, image, and availability. Some source options should become variations, while others may belong in attributes, add-ons, custom fields, or Custom Service review.

**Does migrating orders mean active checkout and payment logic also moves?**

No. Migrated orders preserve historical context. Active checkout fields, payment gateways, tax rules, shipping methods, fraud tools, and fulfillment workflows usually need configuration, extension setup, Add-ons, or Custom Service review depending on the requirement.

**Why does plugin-owned WooCommerce data need special review?**

Plugins can store business-critical data in metadata, custom tables, or external systems. Product add-ons, subscriptions, bookings, memberships, wholesale pricing, loyalty points, checkout fields, and integration records may not behave like ordinary product, customer, or order data.

**How should Entity Points be reviewed for WooCommerce migration?**

Entity Points should be reviewed around eligible records migrated for the first time, such as new Product, Customer, Order, and Blog Posts records. Records already counted through the service license do not consume Entity Points again simply because another migration action is performed.
