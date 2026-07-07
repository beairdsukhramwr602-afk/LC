# Squarespace Pre-Migration Preparation Checklist

Squarespace preparation should begin with a clear decision about what the new store is expected to become. Squarespace is a hosted, content-led commerce platform, so preparation is not limited to product, customer, and order exports. The merchant also needs to prepare Store Pages, content pages, media, SEO fields, URL slugs, domains, checkout settings, fulfillment settings, contact records, and any external systems that still affect customer or operational continuity after launch.

A strong preparation phase protects Demo Migration quality. It helps the merchant decide which records should move, which records should be excluded, which site areas need manual rebuilding, which settings must be configured directly in Squarespace, and which requirements should be reviewed as Add-ons or Custom Service before Full Migration. Preparation should make the migration easier to validate, not merely easier to start.

### Confirm the Squarespace Store Role <a href="#confirm-the-squarespace-store-role" id="confirm-the-squarespace-store-role"></a>

Before exporting data or requesting migration setup, define how Squarespace will operate after launch. Squarespace may become the merchant’s primary storefront, a content site with commerce attached, a portfolio site with selected products, a service-business site with payment needs, a digital product shop, or a compact store that depends heavily on content presentation.

This decision matters because the same product data can support very different launch outcomes. A product may migrate with its name, price, image, and SKU intact, but the final customer experience still depends on Store Page placement, product-page presentation, navigation, checkout readiness, domain timing, and SEO continuity. Preparation should therefore connect commerce records with site structure from the start.

| Preparation question                                                         | Why it matters                                                                                                           | Required decision                                                                                        |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| Will Squarespace be the main store or a content site with commerce attached? | Commerce records and site presentation must be planned together.                                                         | Decide how Store Pages, product pages, navigation, content pages, and checkout will support launch.      |
| Which parts of the previous store are still useful?                          | Outdated products, obsolete pages, inactive customers, and old posts can create unnecessary noise.                       | Decide what should migrate, be excluded, redirected, archived, or rebuilt manually.                      |
| Is launch mainly a data move, a redesign, or a business-model change?        | Migration cannot automatically rebuild templates, content strategy, checkout behavior, or operating procedures.          | Separate migration scope from site build, copywriting, design, configuration, and business-process work. |
| Are external systems still part of the workflow?                             | CRM, fulfillment, accounting, tax, shipping, subscription, donation, booking, or email tools may hold important records. | Decide which records belong in Squarespace and which records remain external.                            |

This early framing prevents Squarespace from being treated like a generic cart replacement. It gives Demo Migration a meaningful success standard: not only whether records moved, but whether the migrated records support the way the new Squarespace site is expected to sell.

### Prepare Product and Store Page Data <a href="#prepare-product-and-store-page-data" id="prepare-product-and-store-page-data"></a>

Squarespace product preparation should consider both commerce data and storefront presentation. Products may be physical, service, gift card, or digital products, and product records may include names, descriptions, images, visibility, tags, SEO options, URLs, URL slugs, Store Page IDs, product attributes, and variants. This means preparation should not stop at a spreadsheet of titles and prices.

The merchant should review how each product is meant to appear inside Squarespace. Store Pages, product-page URLs, product images, product visibility, product descriptions, product options, variant SKUs, inventory, SEO titles, SEO descriptions, and media order can all affect whether a migrated catalog is usable after launch. A clean product export is helpful, but a clean merchandising plan is just as important.

| Product area         | What to prepare                                                                                                                     | Demo Migration sample to include                                                                               |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Product types        | Classify physical products, service products, digital downloads, gift cards, and any unusual selling model.                         | At least one product from each important type.                                                                 |
| Product details      | Clean names, descriptions, SKUs, prices, sale prices, weights, visibility, tags, SEO titles, SEO descriptions, URLs, and URL slugs. | Products with normal fields and products with missing or unusual values.                                       |
| Variants and options | Review option names, choices, SKU combinations, price differences, inventory differences, and variant images.                       | Simple products, single-option products, and multi-option products with meaningful variants.                   |
| Product media        | Prepare main images, galleries, alt text expectations, file quality, image order, and product-specific media rules.                 | Products with multiple images, products with old image naming, and products where image order affects selling. |
| Store Pages          | Decide which Store Pages should receive which products and how they relate to navigation and customer browsing.                     | A key Store Page or product group that matters for launch.                                                     |

Product preparation should also identify source behaviors that are not ordinary product data. Bundles, product personalization, custom forms, engraving fields, wholesale pricing, advanced subscriptions, marketplace feeds, donation logic, external inventory rules, and app-managed product fields may need accepted exclusion, manual setup, Add-ons, or Custom Service review.

### Prepare Customers, Contacts, Members, and Subscriber Records <a href="#prepare-customers-contacts-members-and-subscriber-records" id="prepare-customers-contacts-members-and-subscriber-records"></a>

Squarespace preparation should separate commerce customers from broader site contacts. A previous platform may combine customers, newsletter subscribers, donors, members, booking participants, account users, CRM profiles, or form contacts in one record set. Squarespace may treat these meanings differently, especially when contact records, marketing preferences, address books, customer history, and donor or subscriber identity are involved.

The merchant should decide which people-related records are needed for the new store and why. A customer who placed an order, a subscriber who receives email campaigns, a donor associated with a donation record, and a member with access expectations are not the same migration problem. Treating all of them as ordinary customer records can create confusion after launch.

| Record type                | Preparation focus                                                                                                 | Reason to prepare early                                                          |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Customers                  | Names, emails, billing addresses, shipping addresses, phone numbers, order-history links, and customer notes.     | Customer records must match order-history and customer-service expectations.     |
| Contacts and subscribers   | Marketing contacts, newsletter subscribers, inquiry contacts, donor contacts, and CRM-style records.              | Not every contact is necessarily a commerce customer.                            |
| Members and account access | Login expectations, member-only content, customer accounts, subscriptions, courses, appointments, or gated pages. | Access control may require Squarespace setup or external-system handling.        |
| Guest buyers               | Orders tied to email addresses without target account login.                                                      | Guest order history should be validated separately from account-based customers. |
| External IDs               | CRM, fulfillment, accounting, tax, loyalty, donation, or customer-service identifiers.                            | External systems may need original identifiers after launch.                     |

Customer preparation should include privacy and retention review. Records that are no longer needed should not be moved automatically. The merchant should confirm which records are legally and operationally appropriate to preserve, especially when a previous platform includes inactive customers, marketing-only contacts, or historical profiles that no longer serve the business.

### Prepare Historical Order, Transaction, and Fulfillment Data <a href="#prepare-historical-order-transaction-and-fulfillment-data" id="prepare-historical-order-transaction-and-fulfillment-data"></a>

Order preparation should distinguish migrated history from live commerce configuration. Historical orders can support customer service, accounting review, warranty lookup, refund research, and operational continuity, but they do not recreate live checkout, payment processing, tax calculation, shipping rules, fulfillment automation, subscription renewal, or email workflows.

Squarespace order planning should include line items, product references, quantities, discounts, tax, shipping, totals, customer links, transactions, fulfillment details, refund context, and any external identifiers that staff need after launch. The goal is not only to move orders, but to make order history understandable to the team that will use Squarespace after migration.

| Order area     | What to prepare                                                                                      | What to check during Demo Migration                                                         |
| -------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Order status   | Source statuses, fulfillment states, payment states, cancellation states, and refund states.         | Whether migrated labels are understandable for operations teams.                            |
| Line items     | Product names, variant selections, SKU references, quantities, discounts, tax, shipping, and totals. | Orders with variants, discounts, refunds, shipping fees, tax lines, and manual adjustments. |
| Customer links | Registered customer orders, guest orders, duplicate emails, and historical address changes.          | Whether orders remain associated with the expected customer or email.                       |
| Transactions   | Payment labels, transaction references, refunds, charge states, and gateway identifiers.             | Whether transaction details are useful as historical reference.                             |
| Fulfillment    | Tracking numbers, carriers, shipment splits, fulfillment notes, and external fulfillment IDs.        | Whether fulfillment details remain readable after migration.                                |

Recurring payment behavior, saved payment methods, fraud rules, automated emails, and fulfillment automation should be prepared as target-side or external-system work. They should not be assumed to move simply because order history is included in the migration scope.

### Prepare Checkout, Payment, Tax, Shipping, Discount, and Fulfillment Settings <a href="#prepare-checkout-payment-tax-shipping-discount-and-fulfillment-settings" id="prepare-checkout-payment-tax-shipping-discount-and-fulfillment-settings"></a>

Target-side commerce settings should be prepared separately from migrated data. A merchant can move product, customer, and order history while still needing to configure how the new Squarespace store accepts payment, calculates tax, offers shipping, applies discounts, sends transactional emails, manages fulfillment, and handles checkout restrictions.

This distinction is important because configuration gaps can be mistaken for migration defects. A product may be present, an order may be readable, and customer records may be available, while the store is still not ready to sell because payment, shipping, tax, checkout, or fulfillment settings are incomplete.

| Setting area | Preparation requirement                                                                                               | Why it is separate from migration                                                  |
| ------------ | --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Payments     | Identify payment processors, payment methods, currencies, refund needs, and transaction-history expectations.         | Payment processing must be configured in the Target Platform or connected systems. |
| Tax          | Review taxable products, tax-exempt customers, regional tax rules, and historical tax lines.                          | Tax calculation behavior is operational configuration, not ordinary order history. |
| Shipping     | Prepare zones, carrier rules, local pickup, free shipping thresholds, package assumptions, and fulfillment workflows. | Shipping logic must be configured and tested after data migration.                 |
| Discounts    | Review coupons, promotions, expired campaigns, automatic discounts, and source-platform rules.                        | Discounts may need recreation or adjustment depending on supported behavior.       |
| Fulfillment  | Identify manual fulfillment, external fulfillment partners, tracking formats, and notification needs.                 | Fulfillment behavior often depends on integrations or target-side setup.           |

The preparation standard should be practical: document the setting, decide whether it belongs in migration scope, decide whether it must be rebuilt manually, and select Demo Migration samples that expose whether historical data remains useful.

### Prepare Content, Media, SEO, URLs, and Domains <a href="#prepare-content-media-seo-urls-and-domains" id="prepare-content-media-seo-urls-and-domains"></a>

Squarespace preparation should protect the content and URL layer because commerce often sits inside a broader site experience. Product pages, Store Pages, Blog Posts, CMS Pages, image assets, internal links, navigation labels, metadata, redirects, and domain timing can affect launch quality as much as product data.

The merchant should collect current URLs before migration begins. Product URLs, category or collection URLs, content-page URLs, Blog Post URLs, high-traffic landing pages, indexed pages, and campaign URLs should be reviewed. Decide which pages should be migrated, which should be rebuilt, which should be redirected, and which should be retired.

| SEO and content area       | What to prepare                                                                                          | Launch risk if skipped                                                      |
| -------------------------- | -------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Product URLs and slugs     | Current product URLs, desired Squarespace slugs, important product-page redirects.                       | Search traffic and bookmarked product links may break.                      |
| Store Pages and navigation | Store Page structure, menus, landing pages, product groupings, and browsing paths.                       | Products may exist but be difficult for customers to find.                  |
| CMS Pages and Blog Posts   | Page content, post content, authorship expectations, dates, images, internal links, and metadata.        | Content continuity may be lost even when product records migrate correctly. |
| Media assets               | Product images, galleries, downloadable files, alt text expectations, image quality, and file ownership. | Pages may look incomplete or fail to support the intended presentation.     |
| Domains and redirects      | Domain timing, URL mapping, redirect rules, analytics, and launch cutover needs.                         | Launch can lose traffic, tracking continuity, or customer trust.            |

SEO preparation should not be treated as a final-day task. URL decisions affect Demo Migration review because sample products and content should reveal whether slugs, links, images, metadata, and redirects can support the intended launch.

### Prepare Templates, Design, Navigation, and Site-Builder Dependencies <a href="#prepare-templates-design-navigation-and-site-builder-dependencies" id="prepare-templates-design-navigation-and-site-builder-dependencies"></a>

Squarespace migration planning should separate data movement from site presentation. Template layout, page sections, design choices, navigation, mobile presentation, embedded blocks, forms, calendars, galleries, booking elements, donation flows, and custom code may influence the final experience but are not equivalent to transferable commerce records.

This area was underdeveloped in the previous refined version. It matters because merchants often choose Squarespace for presentation quality. If design and navigation expectations are not prepared, the migration may look successful from a data standpoint but still feel incomplete to the business.

| Site-builder dependency | What to document                                                                                                | Preparation decision                                                                          |
| ----------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Page layout             | Product-page expectations, Store Page layout, landing pages, campaign pages, and content sections.              | Decide what will be rebuilt manually and what only requires migrated content.                 |
| Navigation              | Menus, footer links, category-like browsing paths, internal links, and important customer journeys.             | Decide how migrated content and products will be reachable after launch.                      |
| Blocks and embeds       | Forms, calendars, maps, videos, third-party widgets, newsletter blocks, donation blocks, or booking components. | Decide which items are target-side setup, external-system work, or Custom Service candidates. |
| Design dependencies     | Template-specific layouts, custom CSS, image cropping, mobile behavior, and brand presentation.                 | Decide what belongs to site build rather than migration output.                               |
| Custom code             | Tracking scripts, custom scripts, integration snippets, and special display behavior.                           | Decide whether to recreate, replace, exclude, or review through Custom Service.               |

Good preparation does not require rebuilding the whole site before migration. It requires identifying which parts of the launch depend on data and which parts depend on Squarespace configuration or site-building work.

### Prepare Apps, APIs, External Systems, and Unsupported Data <a href="#prepare-apps-apis-external-systems-and-unsupported-data" id="prepare-apps-apis-external-systems-and-unsupported-data"></a>

Squarespace stores can depend on external systems even when the native store appears simple. Email marketing, CRM, fulfillment, accounting, tax, booking, donation, subscription, analytics, customer support, review, loyalty, and marketplace systems may own records or workflows that are not ordinary product, customer, or order data.

The merchant should list every system that currently touches commerce records or customer experience. For each system, identify the data owner, the business reason for preserving it, whether it has an export, whether Squarespace has a direct equivalent, and whether the need is a supported migration adjustment or a Custom Service candidate.

| External dependency                 | What to review                                                                                 | Possible handling                                                                                |
| ----------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| CRM and marketing                   | Contacts, segments, tags, consent, subscription status, campaign lists.                        | Supported records, manual export/import, external-system continuation, or Custom Service review. |
| Fulfillment and shipping            | Warehouse IDs, carrier data, fulfillment status, tracking numbers, external order IDs.         | Historical preservation, target-side configuration, or integration rebuild.                      |
| Accounting and tax                  | Tax lines, invoices, transaction references, tax-exempt rules, reconciliation IDs.             | Historical order support or external-system continuity.                                          |
| Subscriptions and memberships       | Renewal logic, billing schedules, gated access, membership status, saved payment expectations. | Target setup, external tool, accepted exclusion, or Custom Service review.                       |
| Reviews, loyalty, and custom fields | Review history, rewards, points, custom product/customer/order attributes.                     | Add-ons if supported; Custom Service when unsupported or bespoke.                                |

Unsupported data should not be hidden inside a general checklist. If it matters to the business, it should be documented before service selection and before Demo Migration samples are chosen.

### Prepare Demo Migration Samples, Entity Points, and Launch Controls <a href="#prepare-demo-migration-samples-entity-points-and-launch-controls" id="prepare-demo-migration-samples-entity-points-and-launch-controls"></a>

Demo Migration samples should be selected to test the areas that actually matter for Squarespace. A weak sample includes only ordinary products and simple orders. A stronger sample includes records that expose product type, variant, media, Store Page, customer/contact, order, transaction, content, URL, and external-system assumptions.

Entity Points planning should be practical. Eligible Product, Customer, Order, and Blog Posts records should be estimated before migration when they affect scope. Records already counted through the service license should not be treated as newly consuming Entity Points again simply because the merchant later performs another migration action on the same migration path.

| Sample type                                | Why to include it                                                                       |
| ------------------------------------------ | --------------------------------------------------------------------------------------- |
| Product with variants and images           | Confirms option, SKU, image, inventory, and product-page behavior.                      |
| Product with SEO-sensitive URL             | Confirms slug, metadata, redirect, and search-continuity expectations.                  |
| Customer with multiple orders              | Confirms customer/order relationship and readable history.                              |
| Guest order                                | Confirms email-based order history is understandable.                                   |
| Refunded or discounted order               | Confirms payment, refund, discount, tax, and total history remains useful.              |
| Important CMS Page or Blog Post            | Confirms content preservation and redirect planning.                                    |
| Record with custom or external-system data | Confirms whether Add-ons, Custom Service, manual work, or accepted exclusion is needed. |

Launch controls should include a freeze or update plan for products, customers, orders, and content that may change after Demo Migration. Additional Migration Options should be considered when the source store will keep operating during the migration window and the merchant needs a later update before or after launch.

### Squarespace Preparation Checklist <a href="#squarespace-preparation-checklist" id="squarespace-preparation-checklist"></a>

Use the checklist as a final readiness screen before Full Migration.

| Area                    | Readiness question                                                                                                                        |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Store role              | Has the merchant defined whether Squarespace is the main store, content site with commerce, or compact storefront?                        |
| Products                | Are product types, variants, images, SKUs, visibility, SEO fields, URLs, and Store Page relationships prepared?                           |
| Customers and contacts  | Are customers, contacts, subscribers, donors, members, guest buyers, and external IDs separated by business meaning?                      |
| Orders and transactions | Are statuses, line items, refunds, discounts, tax, shipping, transactions, fulfillment, and customer links represented in samples?        |
| Checkout settings       | Are payment, tax, shipping, discounts, fulfillment, notifications, and checkout behavior prepared outside migration scope where required? |
| Content and SEO         | Are CMS Pages, Blog Posts, images, internal links, metadata, domains, URLs, and redirects prepared?                                       |
| Site presentation       | Are templates, navigation, page layouts, blocks, embeds, and custom code separated from migrated data?                                    |
| External systems        | Are CRM, marketing, fulfillment, accounting, tax, subscription, donation, loyalty, review, and support systems reviewed?                  |
| Service scope           | Are Add-ons, Custom Service, Entity Points, and Additional Migration Options identified before Full Migration?                            |
| Demo Migration          | Are sample records selected to test the highest-risk Squarespace outcomes?                                                                |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace preparation should produce a clear launch plan, not just a set of exports. Products, Store Pages, contacts, customers, orders, transactions, content, URLs, media, design dependencies, checkout settings, and external systems should be reviewed together because Squarespace combines commerce with site presentation.

The strongest preparation work separates what can be migrated from what must be configured, rebuilt, excluded, or reviewed separately. That distinction helps the merchant choose the right service path, evaluate Demo Migration evidence correctly, and avoid mistaking unfinished site setup for migration failure.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to Squarespace?**

Start by defining the role of the new Squarespace site. Decide whether it will be the main store, a content-led site with commerce, a service-business site, or a compact storefront. That decision shapes product scope, Store Page planning, content review, checkout setup, SEO preservation, and validation samples.

**Does Squarespace preparation only require product and order exports?**

No. Product and order exports are only part of the preparation. A Squarespace migration should also review Store Pages, product URLs, content pages, Blog Posts, images, contacts, members, subscribers, domains, redirects, checkout settings, fulfillment settings, and external systems.

**How should products be prepared for Squarespace migration?**

Products should be prepared with their type, name, description, SKU, price, images, visibility, tags, SEO data, URL slug, Store Page relationship, variants, and inventory expectations. Products that depend on custom options, bundles, subscriptions, personalization, or external logic should be reviewed separately.

**What order data should be included in Demo Migration samples?**

Demo Migration samples should include ordinary orders, guest orders, orders with variants, refunded orders, discounted orders, orders with tax and shipping lines, orders with fulfillment data, and orders linked to important customers. These samples help confirm that historical records remain useful after migration.

**When should Custom Service be reviewed before migrating to Squarespace?**

Custom Service should be reviewed when the source store includes unsupported fields, custom product logic, external IDs, third-party system records, bespoke content relationships, subscription or membership behavior, custom checkout fields, or data that does not fit supported migration behavior.
