# Squarespace Validation Priorities

Squarespace migration validation should prove that the target store works as a hosted content-led commerce site, not only that imported records appear in the admin. Product data, Store Pages, images, variants, inventory, customers, contacts, orders, transactions, site pages, blog content, URLs, redirects, checkout settings, and integrations all need to be reviewed according to what Squarespace is expected to support after launch.

A useful validation process separates migrated records from target configuration. Product names, descriptions, prices, images, and variants may migrate correctly while Store Page placement, navigation, templates, product display, checkout settings, tax rules, shipping rates, payments, notifications, and connected services still need Squarespace setup. Validation should therefore confirm both data usability and launch readiness without treating every target-side setting as a migration output.

### Squarespace Validation Thesis <a href="#squarespace-validation-thesis" id="squarespace-validation-thesis"></a>

Squarespace validation should prove that migrated records work inside the target website experience. A valid result is not only a matching product count, customer count, or order count. It is a Squarespace store where product pages, Store Pages, navigation, URLs, media, contacts, orders, checkout settings, and external-system boundaries have been reviewed against the intended launch plan.

The most effective validation sequence is layered: confirm record accuracy first, then confirm storefront presentation, then confirm operational readiness, then confirm unresolved exceptions. This prevents the merchant from accepting a technically complete migration that still needs significant target-side setup before launch.

| Validation layer    | What must be proven                                                                                                 | Failure signal                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Record accuracy     | Products, variants, inventory, contacts, orders, media, and SEO fields are present and correctly interpreted.       | Counts match, but values, identities, images, variants, or order details are wrong. |
| Site presentation   | Products appear on the right Store Pages, content supports discovery, and URLs or redirects are planned.            | Records exist but shoppers cannot browse, understand, or reach priority pages.      |
| Operating readiness | Checkout, payment, tax, shipping, fulfillment, notifications, domains, and integrations are configured or assigned. | Historical data exists but the store is not ready for live transactions.            |
| Exception control   | Unsupported fields, custom behavior, external-system records, and manual rebuild tasks are documented.              | The team discovers missing behavior only after launch preparation begins.           |

### What Squarespace Validation Must Prove <a href="#what-squarespace-validation-must-prove" id="what-squarespace-validation-must-prove"></a>

A Squarespace validation pass should show that the migrated store can support ordinary business work after migration: customers can find products, staff can identify orders, product pages are usable, content paths make sense, and exceptions are known before launch. Record totals are not enough. A merchant may have the expected number of products and still fail validation if variants cannot be selected correctly, content links break, inventory is unclear, or historical order details no longer help support staff answer customer questions.

| Validation area             | What must be proven                                                                                                                      | Why it matters for Squarespace                                                                                                |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Commerce records            | Products, variants, inventory, orders, transactions, contacts, and customer records are readable and connected where supported.          | Squarespace stores depend on clean supported structures rather than unlimited custom record modeling.                         |
| Site and content continuity | Store Pages, CMS Pages, Blog Posts, images, navigation, URLs, metadata, and redirects support the intended customer journey.             | Squarespace commerce usually sits inside a broader site experience, so content and storefront validation cannot be separated. |
| Historical order meaning    | Orders, line items, totals, taxes, shipping values, discounts, refunds, fulfillment notes, and payment references remain understandable. | Historical records are often needed for customer support, finance review, and operational reconciliation.                     |
| Target configuration        | Payment, tax, shipping, checkout, domain, notifications, email settings, and fulfillment behavior are identified as configuration work.  | A migration can preserve data without completing live commerce setup.                                                         |
| Exceptions and scope        | Unsupported structures, manual rebuilds, Add-ons, Custom Service outputs, and accepted exclusions are documented.                        | Squarespace validation should end with clear decisions, not unresolved assumptions.                                           |

The best result is a validation decision that names what passed, what needs target setup, what needs correction, what requires Custom Service review, and what has been intentionally excluded from the migration scope.

### Demo Migration Validation Priorities <a href="#demo-migration-validation-priorities" id="demo-migration-validation-priorities"></a>

Demo Migration should include samples that expose Squarespace-specific behavior. A small sample of ordinary products and simple orders may look correct while hiding the records that create actual launch risk. Squarespace samples should include content-led pages, Store Page relationships, product types, variants, images, URL slugs, customer/contact examples, order exceptions, and any custom or external-system data that may affect launch.

| Sample group                | Include in the sample                                                                                                                                                     | What the sample should prove                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Products and Store Pages    | Physical products, service products, digital products, gift cards, variants, product images, visible and hidden products, and products assigned to important Store Pages. | Whether commerce data lands in supported Squarespace structures and whether presentation needs target-side work.  |
| Orders and transactions     | Standard orders, refunded orders, discounted orders, tax/shipping examples, payment references, fulfillment examples, and subscription-related history if relevant.       | Whether historical business meaning remains readable for staff and finance review.                                |
| Customers and contacts      | Registered customers, guest buyers, contacts, subscribers, donors, duplicate emails, address records, and marketing preference examples where included.                   | Whether people records preserve their intended meaning instead of being flattened into one generic customer type. |
| Content and SEO             | CMS Pages, Blog Posts, product URLs, image-heavy pages, metadata, internal links, redirects, and priority landing pages.                                                  | Whether content continuity supports traffic, navigation, and search expectations.                                 |
| Exceptions and integrations | External IDs, CRM fields, fulfillment references, product feed values, app-owned fields, unsupported records, and custom data.                                            | Whether the migration path is correctly scoped before Full Migration.                                             |

Demo validation should classify each issue. A finding may be accepted Squarespace behavior, a target-configuration task, a migration correction, an Add-on requirement, a Custom Service review point, or an exclusion. Without this classification, teams can waste time trying to correct behavior that actually belongs to Squarespace setup or outside the supported migration scope.

Validation should create evidence that can be acted on. A pass condition should say what is acceptable, who owns unresolved work, and whether the issue affects launch. For example, missing source design behavior may be acceptable if it is a manual rebuild item, but missing product variants or broken priority URLs may block launch until corrected.

This distinction helps the merchant avoid over-reporting cosmetic differences while still catching defects that affect commerce, SEO continuity, customer service, and operational readiness.

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

Squarespace product validation should check how product data functions in context. Product records should be readable in the admin, but they also need to appear correctly on Store Pages, support the right product type, show images clearly, expose variants properly, and preserve the SEO fields that matter for discoverability.

| Product area         | Validation priority                                                                                                          | Pass condition                                                                                               |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Product identity     | Names, descriptions, SKUs, prices, sale prices, visibility, status, product type, and product identifiers.                   | Products are recognizable, searchable, and classified according to the approved scope.                       |
| Product types        | Physical, service, digital, and gift card products when present.                                                             | Each product type behaves according to supported Squarespace commerce behavior and accepted migration scope. |
| Variants and options | Variant names, option values, SKUs, prices, images, inventory values, and availability.                                      | Customers can select valid options, and staff can understand variant-level selling details.                  |
| Inventory            | Stock values, stock tracking assumptions, sold-out behavior, and products intentionally excluded from inventory tracking.    | Inventory is understandable and ready for post-migration management.                                         |
| Images and media     | Primary images, galleries, image order, alt text where relevant, image quality, downloadable files, and visual presentation. | Product pages are usable and do not create broken, misleading, or incomplete storefront display.             |
| Store Page placement | Store Pages, product groups, categories, navigation links, featured placements, and merchandise groupings.                   | Products appear in the expected selling paths.                                                               |
| SEO values           | URL slugs, product URLs, titles, descriptions, metadata, and redirect planning for important products.                       | High-value product paths remain discoverable or have a clear redirect plan.                                  |

Variant-heavy catalogs need deeper sampling. The validation set should include simple products, products with one option, products with multiple options, products with image-dependent variants, products with inventory differences, and products that represent the merchant’s most important revenue categories. A pass means the merchant can manage the product after migration, not simply that the product exists.

### Store Pages, Content, and SEO Validation <a href="#store-pages-content-and-seo-validation" id="store-pages-content-and-seo-validation"></a>

Squarespace validation must treat content and commerce as connected. A product can migrate correctly while the surrounding customer path remains incomplete because the Store Page, page layout, media, navigation, redirects, metadata, or internal links still need work. This matters especially for merchants that use Squarespace for editorial pages, portfolios, services, blog-driven discovery, landing pages, or brand storytelling.

Important validation samples should include the homepage, top navigation paths, high-traffic product pages, high-revenue product pages, CMS Pages, Blog Posts, content blocks, image-heavy pages, and any page that sends visitors toward checkout. Reviewers should confirm that migrated content is not only present, but also placed in a usable customer journey.

| Content and SEO area | What to validate                                                                                                                     | Pass condition                                                                              |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| Store Pages          | Product placement, page assignment, visible products, page titles, navigation placement, and merchandising logic.                    | Store Pages lead customers to the expected products without confusing gaps.                 |
| CMS Pages            | Page titles, body content, images, internal links, embedded media, calls to action, and formatting.                                  | Key pages remain useful and do not require unexpected rebuild work.                         |
| Blog Posts           | Titles, body content, authorship or dates where relevant, images, internal links, categories or tags where included, and SEO values. | Blog content remains readable and supports search or content continuity goals.              |
| URLs and redirects   | Product URLs, page URLs, blog URLs, old source paths, redirect rules, and domain launch steps.                                       | Priority traffic paths are protected or assigned to a redirect/remediation plan.            |
| Metadata             | SEO titles, descriptions, slugs, alt text where relevant, and high-value search snippets.                                            | Important pages retain or receive discoverability signals appropriate for the target store. |

A content validation pass should not promise exact visual parity with the old site. It should prove that priority content works in Squarespace, that URL changes are controlled, and that manual design or content rebuild work is assigned before launch.

### Customer, Contact, Member, and Subscriber Validation <a href="#customer-contact-member-and-subscriber-validation" id="customer-contact-member-and-subscriber-validation"></a>

Squarespace people records need validation by meaning. Depending on the source and target configuration, a person may be a buyer, guest customer, registered customer, contact, mailing-list subscriber, donor, member, or profile-like record. If these roles are treated as one simple customer total, the migration may appear successful while marketing, service, and account expectations remain unclear.

| People record area       | What to validate                                                                                                           | Pass condition                                                                                       |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Customer identity        | Email addresses, names, phone numbers, billing addresses, shipping addresses, duplicate handling, and order relationships. | Staff can identify customers and connect them to relevant order history.                             |
| Guest buyers             | Guest orders and buyer details without full account expectations.                                                          | Guest purchase history remains usable without implying account migration that was not in scope.      |
| Contacts and subscribers | Contact records, mailing list membership, subscriber status, donor records, and marketing preferences where included.      | Marketing or CRM-like records are not confused with ordinary commerce customers.                     |
| Members and accounts     | Membership status, gated-content assumptions, account access expectations, and permission-based access where relevant.     | The merchant understands what moved and what requires Squarespace configuration or separate rebuild. |
| External references      | CRM IDs, loyalty IDs, donor IDs, fulfillment IDs, or other identifiers included in scope.                                  | Important identifiers remain visible, mapped, or documented for operational use.                     |

A strong pass condition is practical: staff should be able to answer who bought, who subscribed, who donated, which orders belong to which person, which records require follow-up configuration, and which customer-related data falls outside standard migration behavior.

### Order, Transaction, Refund, and Fulfillment Validation <a href="#order-transaction-refund-and-fulfillment-validation" id="order-transaction-refund-and-fulfillment-validation"></a>

Order validation should focus on historical readability and operational continuity. Migrated order history should help the merchant support customers, reconcile sales history, and understand past transactions. It should not be mistaken for live checkout configuration, payment capture setup, tax calculation, shipping-rate configuration, or fulfillment automation.

| Order area            | Validation priority                                                                                               | Pass condition                                                                                                  |
| --------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Order identity        | Order numbers, dates, statuses, customer links, email addresses, and source references.                           | Staff can search and recognize historical orders accurately.                                                    |
| Line items            | Product names, variant choices, quantities, prices, discounts, taxes, shipping lines, and totals.                 | Order details make business sense and reconcile within accepted differences.                                    |
| Transactions          | Payment references, transaction labels, donation payments, refund references, and financial notes where included. | Finance and support teams can understand transaction context without assuming payment capture can be recreated. |
| Refunds and returns   | Refund status, refunded amounts, return notes, and support-facing history.                                        | Staff can interpret past support situations accurately.                                                         |
| Fulfillment           | Fulfillment status, shipping references, tracking information, fulfillment notes, and external identifiers.       | Historical fulfillment context remains useful for service and reconciliation.                                   |
| Live setup separation | Payments, tax, shipping, notifications, checkout rules, and fulfillment integrations.                             | Configuration tasks are tested separately from migrated history.                                                |

Validation should include ordinary orders and exception orders. Refunds, partial fulfillments, discounted orders, tax-heavy orders, international shipping orders, and external fulfillment examples often reveal problems that clean order samples do not.

### Checkout, Tax, Shipping, and Notification Validation <a href="#checkout-tax-shipping-and-notification-validation" id="checkout-tax-shipping-and-notification-validation"></a>

A Squarespace migration can preserve products and history without making the target store ready to transact. Payment processors, tax settings, shipping rules, checkout fields, discount behavior, order notifications, fulfillment processes, and domain launch settings must be configured and tested in Squarespace. Validation should distinguish data migration success from operational launch readiness.

| Configuration area | What to test                                                                                                       | Pass condition                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Payments           | Payment processor setup, test purchase flow, order capture, transaction labels, and refund handling.               | The merchant can place and review test orders according to launch needs.              |
| Tax                | Tax settings, taxable products, exempt assumptions, regional rules, and order totals.                              | Tax behavior is configured and tested separately from migrated historical tax values. |
| Shipping           | Shipping zones, rates, carrier logic, fulfillment expectations, pickup or delivery needs, and free-shipping rules. | Customers can receive accurate shipping options for intended launch regions.          |
| Discounts          | Coupon or discount behavior, sale prices, order-level discounts, and product-level discounts.                      | Promotional logic is understood and configured where supported.                       |
| Notifications      | Order confirmations, shipping notifications, staff alerts, email templates, and customer-facing messages.          | Customers and staff receive the right communications during test flows.               |

These checks should be completed before the store is accepted for launch. They are not replacements for migration validation; they are operational tests that prove migrated data can support real commerce activity.

### Integration, API, and External-System Validation <a href="#integration-api-and-external-system-validation" id="integration-api-and-external-system-validation"></a>

Many Squarespace stores depend on connected systems even when the target platform appears simple. Inventory feeds, fulfillment services, accounting tools, analytics, CRM systems, email platforms, payment processors, donor systems, membership tools, scheduling systems, or product feeds may hold identifiers and workflows that affect post-launch operations.

Validation should identify which external references were migrated, which systems must be reconnected, which workflows must be rebuilt, and which behaviors are outside the migration scope. API access and app availability should be treated as planning boundaries, not as proof that every source behavior can be recreated inside Squarespace.

| External-system area              | What to validate                                                                                                       | Pass condition                                                                          |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Product and inventory identifiers | SKUs, external product IDs, feed IDs, fulfillment IDs, and inventory references.                                       | External systems can recognize migrated records or have a mapping plan.                 |
| Orders and fulfillment            | Order references, tracking values, fulfillment status, shipping labels, and third-party export requirements.           | Staff can continue support and reconciliation using recognized order details.           |
| CRM and marketing                 | Contact IDs, subscriber status, tags, donor indicators, marketing preferences, and segmentation fields where included. | Marketing or CRM work does not lose essential record meaning.                           |
| Analytics and reporting           | Order totals, transaction references, product IDs, campaign URLs, and conversion paths.                                | Reporting expectations are documented and not assumed to transfer automatically.        |
| Unsupported app data              | App-owned records, custom fields, custom workflows, and external-only logic.                                           | Add-ons and Custom Service review points are separated from ordinary supported records. |

The outcome should be an integration readiness list. Some items will be migrated, some will be configured in Squarespace, some will require external reconnection, and some may require Custom Service or accepted exclusion.

### Validation After Additional Migration Options <a href="#validation-after-additional-migration-options" id="validation-after-additional-migration-options"></a>

Additional Migration Options can affect the target store after the initial migration. New products, customers, orders, Blog Posts, content updates, URL changes, and changed source records may alter inventory, redirects, order history, content relationships, SEO values, customer identities, and integration references. Validation should therefore be repeated for the business areas touched by follow-up migration activity.

When new eligible Product, Customer, Order, or Blog Posts records are migrated for the first time, they may consume Entity Points according to the service license. If a record has already been counted through the license, migrating that same recorded entity again does not consume additional Entity Points simply because another migration action occurs on the same migration path.

| Follow-up area                   | Revalidation priority                                                                                   | Pass condition                                                               |
| -------------------------------- | ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| New products or updated products | Store Page placement, images, variants, inventory, pricing, visibility, slugs, and SEO values.          | New or changed products are usable and do not break existing customer paths. |
| New customers or contacts        | Identity, addresses, subscriber status, marketing preferences, order links, and duplicates.             | People records remain understandable after the update.                       |
| New orders or order updates      | Order identity, totals, line items, transactions, refunds, fulfillment status, and external references. | Order history remains usable after continued migration activity.             |
| New Blog Posts or content        | URLs, redirects, media, internal links, metadata, and navigation placement.                             | Content additions do not create broken paths or search-risk gaps.            |
| Scope changes                    | Add-ons, Custom Service outputs, exclusions, and accepted differences.                                  | Scope decisions remain documented after follow-up activity.                  |

Follow-up validation should be scoped. It does not require retesting the entire store every time, but it should retest the areas affected by the new or changed data.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace validation should prove that migrated data, site content, commerce configuration, and operational context work together well enough for launch. The strongest validation process does not stop at record counts. It checks products in Store Pages, variants in inventory, contacts by meaning, order history by usefulness, checkout by real test behavior, content by customer path, SEO by priority URLs, integrations by operational dependency, and follow-up migration activity by the areas it changes.

A Squarespace migration is ready when the merchant can identify what migrated correctly, what requires target setup, what needs correction, what requires Add-ons or Custom Service review, and what has been intentionally excluded.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first after a Squarespace Demo Migration?**

Start with representative products, Store Pages, variants, inventory, customers or contacts, orders, transactions, key CMS Pages, Blog Posts, product URLs, and redirects. The sample should include complex records, not only clean examples.

**Does migrated order history prove Squarespace checkout is ready?**

No. Historical order data and live checkout configuration are separate. Payments, tax, shipping, discounts, notifications, fulfillment, and checkout settings should be configured and tested in Squarespace.

**Why should Squarespace validation include pages and Blog Posts?**

Squarespace commerce is closely tied to site content, Store Pages, media, navigation, SEO fields, and URLs. Product and order data can pass while content paths or search continuity still need work.

**How should customers and contacts be checked?**

Validate people records by business meaning. Buyers, guest customers, contacts, subscribers, donors, members, address records, and marketing preferences should not be treated as one simple customer count.

**What should be rechecked after Additional Migration Options are used?**

Recheck the affected products, customers, orders, Blog Posts, content, URLs, redirects, inventory, SEO values, integration references, and service-scope decisions touched by the follow-up migration activity.
