# Wix Pre-Migration Preparation Checklist

Wix migration preparation should make the Target Platform testable before the migration result is accepted. Wix combines hosted site building, Wix Stores, Wix eCommerce services, apps, members, content tools, checkout settings, payments, shipping, tax, SEO, and optional Velo or API work. Preparation must therefore cover more than product, customer, and order counts.

A well-prepared Wix migration separates data that can be migrated, settings that must be configured in Wix, design or content work that must be rebuilt, and custom or app-owned behavior that may require Add-ons or Custom Service review. That separation gives Demo Migration and Full Migration a clear decision basis instead of relying on broad assumptions about what a hosted site-builder platform will recreate automatically.

### What Preparation Means for Wix <a href="#what-preparation-means-for-wix" id="what-preparation-means-for-wix"></a>

Preparation defines how the current store should operate inside Wix after migration. The practical test is not only whether records appear, but whether the target site can sell, display, organize, search, and support those records in a way the business can use.

| Preparation layer      | Wix-specific meaning                                                                                                             | What must be decided before migration                                                        |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Store and site context | Wix site, Wix Stores, eCommerce services, apps, plan, domain, storefront, checkout, and design expectations.                     | Which target environment is being prepared and which features must be active before testing. |
| Migrated records       | Products, customers, orders, CMS Pages, Blog Posts, images, eligible commerce data, and supported metadata.                      | Which records are in scope and which samples must prove the migration path.                  |
| Configured behavior    | Payments, tax, shipping, pickup, delivery, discounts, fulfillment, checkout behavior, menus, collection pages, and SEO settings. | Which outcomes depend on Wix setup rather than migrated data.                                |
| App or custom behavior | Wix apps, Velo logic, APIs, custom catalogs, service plugins, custom fields, app-owned records, and external systems.            | Which requirements need mapping, Add-ons, Custom Service, or accepted exclusions.            |

### Confirm the Target Wix Site Context <a href="#confirm-the-target-wix-site-context" id="confirm-the-target-wix-site-context"></a>

Before preparing record samples, confirm the Wix environment that will receive the migration. Wix behavior can depend on enabled business solutions, installed apps, site structure, checkout configuration, domain planning, and whether custom code or external systems are expected.

| Target context                   | What to prepare                                                                                                                            | Why it matters                                                                                 |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Wix Stores and commerce features | Confirm whether products, cart, checkout, orders, payments, tax, shipping, discounts, fulfillment, and inventory are required.             | Store records should be tested against the actual commerce setup, not a generic website shell. |
| Wix apps and business modules    | List bookings, events, subscriptions, memberships, restaurants, pricing plans, forms, chat, loyalty, email marketing, or third-party apps. | App-owned records may not behave like standard products, customers, or orders.                 |
| Site structure and design        | Identify product pages, collection pages, CMS Pages, Blog Posts, landing pages, menus, footer links, and mobile layout expectations.       | Data migration does not recreate every design, layout, or page-builder decision automatically. |
| Domain and launch context        | Prepare domains, subdomains, DNS timing, old URLs, redirect needs, and launch windows.                                                     | URL continuity and launch timing should be planned before Full Migration acceptance.           |
| Custom logic and integrations    | Document Velo code, APIs, custom catalog behavior, external payment, shipping, tax, ERP, CRM, PIM, WMS, analytics, or marketplace systems. | Custom behavior can change service path, mapping effort, validation scope, and launch risk.    |

### Prepare Product, Variant, and Catalog Evidence <a href="#prepare-product-variant-and-catalog-evidence" id="prepare-product-variant-and-catalog-evidence"></a>

Product preparation should represent how the store sells, not only how many products exist. Wix may need to interpret product names, descriptions, images, prices, inventory, SKUs, collections, product options, choices, variants, modifiers, ribbons, visibility, discounts, subscriptions, and shipping-related behavior.

| Product sample                    | Evidence to collect                                                                                                     | What it proves during Demo Migration                                          |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Baseline product                  | Title, description, SKU, price, inventory, images, collection, visibility, SEO title, and slug.                         | Standard products remain readable, findable, and sellable.                    |
| Variant product                   | Options, choices, variant SKUs, price differences, inventory, images, unavailable combinations, and storefront display. | Shopper choices translate into usable Wix product behavior.                   |
| Product with modifiers or add-ons | Personalization, engraving, packaging, service choice, gift options, configurable extras, or price-changing inputs.     | The requirement is standard, Add-on-supported, custom, or excluded.           |
| Digital or service product        | Delivery method, access expectation, file handling, appointment, booking, event, or membership relationship.            | The selling model belongs in Wix Stores, a Wix app, or Custom Service review. |
| SEO-important product             | Existing URL, metadata, alt text, structured content, redirects, ad traffic, and ranking importance.                    | Migration planning protects product visibility and conversion paths.          |
| External-system product           | ERP/PIM/marketplace IDs, supplier references, inventory source, fulfillment rules, or sync status.                      | The target record can be reconciled after launch.                             |

Custom fields, hidden attributes, marketplace identifiers, supplier references, personalization notes, and app-specific values should be listed separately. They should not be assumed to migrate as ordinary product fields.

### Prepare Collections, Filters, Menus, and Storefront Discovery <a href="#prepare-collections-filters-menus-and-storefront-discovery" id="prepare-collections-filters-menus-and-storefront-discovery"></a>

Wix storefront discovery depends on how products are organized and displayed. Source categories may become collections, menus, gallery sections, landing pages, filters, redirects, or accepted structural changes. Preparation should show how shoppers are expected to find products after migration.

| Discovery area             | Evidence to prepare                                                                                                 | Wix readiness question                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Categories and collections | Source category tree, collection names, product assignments, visibility, priority URLs, and merchandising order.    | Should each structure become a Wix collection, menu item, landing page, or accepted change? |
| Filters and facets         | Size, color, brand, material, price, availability, custom attributes, and search filters.                           | Which filters can be represented in Wix and which need configuration or custom handling?    |
| Navigation                 | Header menus, footer menus, category links, product galleries, campaign pages, and collection pages.                | Can customers reach important products and sections without relying on old site paths?      |
| Product display            | Product gallery layout, collection sorting, badges, ribbons, labels, sale display, image order, and mobile display. | Does migrated data support the intended storefront experience?                              |
| Priority URLs              | Best-selling products, high-traffic categories, product-listing pages, landing pages, and campaign URLs.            | Which URLs require redirects, metadata review, or manual launch planning?                   |

### Prepare Customer, Contact, Member, and Account Data <a href="#prepare-customer-contact-member-and-account-data" id="prepare-customer-contact-member-and-account-data"></a>

Wix can involve customers, contacts, site members, subscribers, app participants, and CRM-style records. These identity layers should not be treated as one identical record type without review.

| Identity sample          | Evidence to prepare                                                                                  | Why it matters                                                                                       |
| ------------------------ | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Buyer with orders        | Name, email, billing/shipping addresses, order history, notes, tags, and customer status.            | Confirms historical commerce context remains understandable.                                         |
| Registered member        | Login expectation, member status, permissions, account fields, and content access.                   | Member behavior may depend on Wix settings or app workflows, not migration alone.                    |
| Marketing contact        | Consent, subscription status, segmentation, tags, notes, and CRM fields.                             | Marketing usability depends on more than customer email migration.                                   |
| App participant          | Booking, event, membership, restaurant, subscription, pricing plan, or form-submission relationship. | App-owned records may require separate review or configuration.                                      |
| B2B-like account         | Company name, tax ID, approval status, custom pricing, saved addresses, or account owner.            | Wix may require configuration, app support, or Custom Service review for non-standard account logic. |
| External-system identity | CRM ID, loyalty ID, ERP account code, marketplace buyer ID, or support-system reference.             | External references may need mapping or accepted exclusion decisions.                                |

The objective is usable identity meaning after migration. Customers should be understandable for service, order review, segmentation, and post-launch operations. Member access, custom roles, app participation, or account permissions should be reviewed separately from standard customer migration.

### Prepare Order, Transaction, and Fulfillment Samples <a href="#prepare-order-transaction-and-fulfillment-samples" id="prepare-order-transaction-and-fulfillment-samples"></a>

Order preparation should support customer service, finance, fulfillment, and operational review after migration. A useful sample includes more than successful paid orders.

| Order sample               | Evidence to collect                                                                                                        | What to verify later                                                                             |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Paid and fulfilled order   | Products, quantities, totals, discounts, tax, shipping, payment label, tracking, fulfillment status, and customer details. | Ordinary historical orders remain readable.                                                      |
| Refunded or canceled order | Status, refund amount, refund reason, payment label, fulfillment status, customer communication, and notes.                | Non-standard order states do not lose operational meaning.                                       |
| Discounted order           | Coupon code, discount label, promotion context, line-item totals, and order total.                                         | Historical discounts remain understandable even if live discounts must be configured separately. |
| Variant or modifier order  | Purchased choice, SKU, personalization note, price change, product name at purchase, and line-item metadata.               | Purchased product meaning remains clear.                                                         |
| App or channel order       | Booking, event, restaurant, subscription, marketplace, POS, or external-channel context.                                   | App-owned or channel-owned meaning receives separate review.                                     |
| External-reference order   | Invoice number, payment transaction ID, ERP order number, shipping reference, or accounting ID.                            | External reconciliation remains possible after migration.                                        |

Historical order records do not configure live Wix checkout. Payments, tax, shipping, pickup, delivery, fulfillment, discounts, and checkout behavior must be configured and tested in the target site.

### Separate Live Checkout Setup from Migrated History <a href="#separate-live-checkout-setup-from-migrated-history" id="separate-live-checkout-setup-from-migrated-history"></a>

A common preparation mistake is treating historical order migration as proof that the target store is ready to sell. The historical record and live checkout flow are different workstreams.

| Area            | Migration preparation                                                                    | Wix setup responsibility                                                                      |
| --------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Payments        | Preserve payment labels and transaction references where supported.                      | Configure payment providers and test live payment flow.                                       |
| Shipping        | Preserve historical method labels, tracking, and fulfillment notes where supported.      | Configure shipping regions, rates, pickup, delivery, carrier logic, and fulfillment behavior. |
| Tax             | Preserve historical tax values in order records where supported.                         | Configure tax calculation for new checkout activity.                                          |
| Discounts       | Preserve historical coupon or discount context where supported.                          | Recreate active coupons, promotions, or discount rules if still needed.                       |
| Checkout fields | Identify custom checkout fields, delivery notes, gift notes, terms, or app-owned fields. | Configure forms, checkout validation, or custom handling where supported.                     |
| Fulfillment     | Preserve historical fulfillment status and references where supported.                   | Configure fulfillment workflow, notifications, delivery options, and external-system sync.    |

### Prepare CMS Pages, Blog Posts, Media, and Site Content <a href="#prepare-cms-pages-blog-posts-media-and-site-content" id="prepare-cms-pages-blog-posts-media-and-site-content"></a>

Wix is often selected because it combines website management and commerce. Preparation should include content and design evidence, especially when SEO, landing pages, blog traffic, forms, images, videos, or branded page layouts matter.

| Content area         | Evidence to prepare                                                                                | Migration planning decision                                                        |
| -------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| CMS Pages            | Policy pages, landing pages, content pages, FAQs, buying guides, and page metadata.                | Which pages migrate, rebuild, redirect, or get excluded?                           |
| Blog Posts           | Titles, authors, categories, tags, dates, images, slugs, metadata, and internal links.             | Which blog structure should be preserved in Wix?                                   |
| Product-page content | Size guides, warranty blocks, product FAQs, embedded media, comparison tables, and instructions.   | Which content belongs inside product data, CMS Pages, apps, or manual design work? |
| Media                | Images, galleries, downloadable files, videos, alt text, filenames, and usage locations.           | Which assets must remain connected to products, pages, posts, or forms?            |
| Site layout          | Menus, footer links, homepage sections, campaign pages, mobile layout, and product-gallery design. | Which visual outcomes are migration scope and which are design/build work?         |

Design recreation should not be assumed to happen automatically through data migration. Preparation should state what is migrated, rebuilt, redesigned, redirected, or intentionally excluded.

### Prepare SEO, URL, Redirect, and Domain Evidence <a href="#prepare-seo-url-redirect-and-domain-evidence" id="prepare-seo-url-redirect-and-domain-evidence"></a>

SEO preparation should start before migration because Wix URL behavior, page hierarchy, product slugs, collection paths, redirects, metadata, and domain setup may differ from the Source Platform.

| SEO area                    | Evidence to prepare                                                                               | Planning reason                                                                    |
| --------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Product URLs                | High-traffic products, slugs, metadata, alt text, ranking-sensitive pages, and ad landing URLs.   | Product visibility depends on data accuracy and redirect planning.                 |
| Category or collection URLs | Source category paths, product-listing pages, collection pages, and merchandising landing pages.  | Source categories may not become identical Wix URLs.                               |
| Blog and content URLs       | Blog Posts, CMS Pages, author pages, tag pages, metadata, and old permalink structure.            | Content migration can affect organic traffic if URLs and metadata are not planned. |
| Redirect map                | Old-to-new URL expectations for priority products, collections, pages, posts, and campaign pages. | Redirect planning reduces avoidable launch disruption.                             |
| Domain setup                | Primary domain, subdomains, DNS timing, launch windows, and analytics/search-console ownership.   | Domain work is launch readiness, not proof that data migrated correctly.           |

### Inventory Apps, Velo, APIs, and External Systems <a href="#inventory-apps-velo-apis-and-external-systems" id="inventory-apps-velo-apis-and-external-systems"></a>

Apps and custom behavior can carry business meaning that is not visible in standard product, customer, or order exports. Wix preparation should identify these dependencies early so they do not appear only after Demo Migration.

| Dependency type                    | Examples to document                                                                                                              | Migration implication                                                                                       |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Wix apps or source app equivalents | Bookings, Events, Restaurants, Pricing Plans, subscriptions, loyalty, forms, reviews, chat, email marketing, or third-party apps. | App-owned records may require separate scope review, target setup, or accepted exclusions.                  |
| Velo or custom code                | Custom collections, dynamic pages, form submissions, business rules, validations, calculations, or automation logic.              | Custom logic may require Custom Service when migration behavior must be adjusted.                           |
| APIs and external systems          | ERP, CRM, accounting, PIM, WMS, fulfillment, shipping, tax, analytics, marketplace, or advertising systems.                       | External identifiers and sync rules may need mapping, target setup, or post-launch reconciliation.          |
| Service plugins                    | Custom fees, custom shipping rates, payment services, checkout/cart validation, or custom catalog integration.                    | Service-plugin behavior should be treated as implementation scope, not assumed migration output.            |
| Custom fields                      | Product, customer, order, contact, member, or content fields that affect operations.                                              | Supported mapping, Add-ons, Custom Service, or accepted exclusions should be decided before Full Migration. |

### Choose Demo Migration Samples Deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration should test records most likely to reveal whether the Wix migration path fits the business. A shallow sample can make migration look cleaner than it will be in production.

| Sample type             | Strong Wix sample                                                                                            | What it proves                                                    |
| ----------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| Product                 | A product with options, variants, SKU, inventory, images, SEO values, and collection assignment.             | Catalog behavior translates into usable Wix product structure.    |
| Collection              | A category or collection with filters, navigation, priority URL needs, and merchandising purpose.            | Shoppers can browse and find products after migration.            |
| Customer/contact/member | A buyer with contact fields, consent status, tags, member context, and order history.                        | Identity meaning remains usable in Wix.                           |
| Order                   | An order with variants, discounts, tax, payment label, shipping, tracking, and external references.          | Historical order records remain readable for operations.          |
| Content                 | A CMS Page, Blog Post, or landing page with images, metadata, links, and old URL value.                      | Content and SEO handling are clear before launch.                 |
| App or custom record    | A record tied to bookings, events, subscriptions, memberships, Velo, service plugins, or an external system. | App-owned or custom behavior is classified before Full Migration. |

### Identify Add-ons, Custom Service, and Accepted Exclusions <a href="#identify-add-ons-custom-service-and-accepted-exclusions" id="identify-add-ons-custom-service-and-accepted-exclusions"></a>

Preparation should reveal whether standard migration scope is enough or whether additional service planning is needed.

| Need identified during preparation | Likely handling                         | Reasoning                                                                                                 |
| ---------------------------------- | --------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Supported data filtering           | Data Filter Add-on                      | Selected-record migration may be enough when source data is too broad or outdated.                        |
| Supported field alignment          | Advanced Data Mapping                   | Source fields can be aligned to supported Wix destinations when the behavior is within supported mapping. |
| Supported value adjustment         | Advanced Data Configure                 | Data values can be adjusted before migration when the requirement remains within supported configuration. |
| Unsupported app records            | Custom Service or accepted exclusion    | App-owned behavior may not fit standard Wix commerce data.                                                |
| Velo, API, or service-plugin logic | Custom Service or target implementation | Custom logic should not be treated as ordinary data migration.                                            |
| Design recreation                  | Target-site build or accepted exclusion | Site design, layout, and interactions often require build work outside data migration.                    |
| External-system sync               | Custom Service or integration setup     | External IDs and sync rules may need custom handling or separate system configuration.                    |

### Plan Follow-Up Migration Timing <a href="#plan-follow-up-migration-timing" id="plan-follow-up-migration-timing"></a>

If source-store activity continues after Demo Migration, preparation should define how later changes will be reviewed. Additional Migration Options should be planned around what changed and whether those changes affect Wix setup, validation, or service scope.

Entity Points should be reviewed correctly: new Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because another migration action is performed for the same migration path. New eligible records may consume Entity Points when migrated for the first time.

| Follow-up area            | What to track                                                                      | Why it matters                                                                      |
| ------------------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| New products              | New SKUs, variants, images, prices, inventory, collections, and SEO fields.        | Product changes may require renewed catalog validation.                             |
| New customers or contacts | New buyers, members, subscribers, consent fields, tags, and addresses.             | Identity changes may affect customer/account review.                                |
| New orders                | Order statuses, discounts, tax, shipping, payment labels, and external references. | Operational review may need to cover new transaction patterns.                      |
| New Blog Posts            | New posts, authors, categories, tags, images, slugs, and metadata.                 | Content and SEO review may need extension.                                          |
| Configuration changes     | Payment, shipping, tax, domain, app, Velo, API, or service-plugin changes.         | Configuration changes may require preparation and testing outside record migration. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

A prepared Wix migration connects source records to real target use. Products should be sellable, collections should support browsing, customers and members should remain understandable, orders should be readable, checkout setup should be tested separately from historical order migration, and content or SEO outcomes should be planned before launch.

Before Demo Migration, collect samples that represent the store’s actual complexity. If those samples reveal filtering, mapping, data configuration, app-owned behavior, Velo logic, service-plugin dependency, external-system identifiers, or unsupported custom records, review Add-ons, Custom Service, or accepted exclusions before Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Wix migration?**

Start with the target Wix site context: Wix Stores setup, required apps, checkout expectations, payment and shipping needs, domain plan, content priorities, and the product and order samples that represent the store’s real operating model.

**Which product samples should be included before Demo Migration?**

Include simple products, products with options and variants, inventory-sensitive products, products with modifiers or custom fields, best sellers, SEO-important products, and any records tied to subscriptions, apps, service plugins, or external systems.

**Should CMS Pages and Blog Posts be prepared before migration?**

Yes. Wix often combines site and store operations, so CMS Pages, Blog Posts, landing pages, menus, media, metadata, internal links, and redirects should be prepared before launch decisions depend on the migrated result.

**Does migrated order history configure Wix checkout?**

No. Historical order data can preserve past order context, but Wix checkout, payment providers, shipping, tax, pickup, delivery, discounts, fulfillment, and service-plugin behavior must be configured and tested in the target site.

**When should Custom Service be considered for a Wix migration?**

Custom Service should be considered when the migration depends on Custom Platform interpretation, unsupported app data, Velo or API-specific behavior, custom migration logic adjustment, service-plugin dependency, complex custom fields, or external-system identifiers that must be preserved in a specific way.
