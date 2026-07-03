# Squarespace Validation Priorities

Squarespace migration validation should prove that the target store is usable as a hosted content-first commerce site, not only that records appear in the admin. Products, orders, customers, contacts, pages, posts, media, URLs, redirects, and design-dependent storefront behavior must be checked together because Squarespace combines commerce data with site presentation and launch settings.

The best validation process separates migrated historical data from target-side configuration. A product record can migrate correctly while product-page display still needs template, section, image, collection, or merchandising work. An order can remain useful for history while payment, tax, shipping, fulfillment, and notification settings still need target-side setup. A page or post can exist while redirects, SEO metadata, navigation, and mobile presentation still need review.

### What Validation Should Prove for Squarespace <a href="#what-validation-should-prove-for-squarespace" id="what-validation-should-prove-for-squarespace"></a>

Validation should prove that the migrated store supports business decisions after migration. It should not try to confirm that Squarespace behaves exactly like the Source Platform.

| Validation question                                                   | What to prove                                                                                                                                         | Why it matters for Squarespace                                                                                                                 |
| --------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Did core commerce records migrate into usable Squarespace structures? | Products, variants, inventory, orders, transactions, contacts, and customer records should be readable and connected where supported.                 | Squarespace stores are simpler than many custom or plugin-heavy commerce stacks, so usable structure matters more than exact source imitation. |
| Did content and commerce remain aligned?                              | Store Pages, product pages, CMS Pages, Blog Posts, media, navigation, SEO fields, URLs, and redirects should support the intended customer journey.   | Squarespace is content-first, so launch quality depends heavily on presentation and path continuity.                                           |
| Are operational records understandable?                               | Historical orders, transactions, discounts, taxes, shipping values, refunds, fulfillment references, and external IDs should remain useful for staff. | Migrated history is often needed for customer support, reporting, and post-launch reconciliation.                                              |
| Are target-side settings separated from migrated data?                | Payment, checkout, tax, shipping, notifications, domains, template settings, and app behavior should be treated as configuration tasks.               | Validation becomes inaccurate when merchants expect migration output to complete live business setup.                                          |
| Are exceptions documented?                                            | Unsupported records, manual rebuilds, excluded fields, Add-ons, Custom Service outputs, and accepted differences should be clear.                     | Squarespace migrations often require practical decisions about what can move, what must be rebuilt, and what remains outside scope.            |

A pass should mean that the merchant can explain what migrated correctly, what must be configured in Squarespace, what needs correction, and what is intentionally excluded.

### Demo Migration Validation Priorities <a href="#demo-migration-validation-priorities" id="demo-migration-validation-priorities"></a>

Demo Migration should include records that reveal Squarespace-specific behavior. A sample made only from simple products or clean pages can miss the issues that matter most at launch.

| Sample group                | Include in the validation sample                                                                                                                                          | What the sample should prove                                                                              |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Products and Store Pages    | Physical products, service products, gift cards, digital downloads, products with variants, product images, inventory values, and category or collection placement.       | Whether product data lands in a usable structure and whether product presentation needs target-side work. |
| Orders and transactions     | Standard orders, refunded orders, subscription or payment-plan examples, subscriptions, tax lines, shipping lines, discounts, payment labels, and transaction references. | Whether historical order meaning remains readable for customer service, finance, and fulfillment review.  |
| Customers and contacts      | Registered customers, guest buyers, subscribers, donors, contacts with addresses, duplicate emails, and marketing preference examples if relevant.                        | Whether people records keep the right business meaning inside Squarespace.                                |
| Content and SEO             | CMS Pages, Blog Posts, images, slugs, titles, metadata, internal links, redirects, and key landing pages.                                                                 | Whether content continuity supports traffic, SEO, and customer navigation.                                |
| Integrations and exceptions | External IDs, fulfillment references, CRM fields, app-owned fields, unsupported records, custom data, and items expected to need Add-ons or Custom Service.               | Whether the migration scope has been classified accurately before Full Migration.                         |

Demo validation should produce a decision, not only a list of observations. Findings should be classified as accepted Squarespace behavior, target-side setup, migration correction, Add-on need, Custom Service review, or exclusion.

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

Squarespace product validation should check both data accuracy and storefront usability. A migrated product is not launch-ready until the merchant can confirm how it appears, how it is organized, and whether customers can buy it correctly.

| Product area                  | Validation priority                                                                                                                | Pass condition                                                                                      |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Product identity              | Product names, SKUs, descriptions, prices, sale prices, visibility, status, and product type should match migration scope.         | Products are searchable, recognizable, and correctly classified in the target store.                |
| Product types                 | Physical products, service products, gift cards, and downloads should be checked separately when present.                          | Each product type behaves according to Squarespace-supported behavior and accepted migration scope. |
| Variants and options          | Option names, choices, variant SKUs, prices, stock values, images, and availability should be reviewed on representative products. | Customers can select valid combinations and staff can identify variant-level details.               |
| Inventory                     | Stock values, sold-out behavior, variant inventory, and products intentionally excluded from inventory tracking should be clear.   | Inventory is understandable and ready for post-migration management.                                |
| Images and media              | Primary images, galleries, image order, alt text where applicable, download files, and media quality should be checked.            | Product pages are visually usable and media does not create broken or misleading presentation.      |
| Collections and merchandising | Store Pages, categories, collections, product groups, navigation links, and featured product placement should be reviewed.         | Products appear in the expected selling paths and key merchandise groups.                           |
| SEO fields                    | Product slugs, titles, descriptions, canonical expectations, and redirects should be checked for important products.               | High-value product paths remain discoverable and customer-facing links are planned.                 |

Variant-heavy catalogs need deeper sampling. Validation should include products with one option, products with multiple options, products with image-dependent variants, products with inventory differences, and products that represent the merchant’s most important revenue categories.

### Customer, Contact, Member, and Profile Validation <a href="#customer-contact-member-and-profile-validation" id="customer-contact-member-and-profile-validation"></a>

Squarespace may represent people as customers, contacts, subscribers, donors, members, or profiles depending on the original store and the target configuration. Validation should confirm business meaning, not only record count.

| People record area         | What to validate                                                                                                   | Pass condition                                                                                          |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Customer identity          | Email addresses, names, phone numbers, billing addresses, shipping addresses, duplicate handling, and order links. | Staff can identify customers and connect them to relevant order history.                                |
| Contacts and subscribers   | Contact lists, subscriber status, donors, marketing preferences, and opt-in meaning where included.                | Marketing or CRM-like records are not confused with ordinary commerce customers.                        |
| Member and account meaning | Members, account access, customer login expectations, permissions, and gated-content assumptions.                  | The merchant understands what migrated and what requires Squarespace configuration or separate rebuild. |
| Guest buyers               | Guest orders and buyer records without full accounts.                                                              | Guest purchase history remains understandable without creating false account expectations.              |
| External references        | CRM IDs, loyalty references, donor IDs, fulfillment IDs, or other third-party references included in scope.        | Important identifiers remain visible, mapped, or documented for operational use.                        |

A people-record pass should not be based only on matching totals. It should show that staff can answer practical questions: who bought, who subscribed, who donated, which orders belong to which person, and which records need separate app or Custom Service handling.

### Order, Transaction, Subscription, and Fulfillment Validation <a href="#order-transaction-subscription-and-fulfillment-validation" id="order-transaction-subscription-and-fulfillment-validation"></a>

Squarespace order validation should focus on historical readability and operational continuity. It should not be confused with configuring live checkout, payment capture, tax calculation, shipping rates, or fulfillment rules.

| Order area                     | Validation priority                                                                                                   | Pass condition                                                                                                  |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Order identity                 | Order numbers, dates, statuses, customer links, email addresses, and source references.                               | Staff can recognize and search historical orders accurately.                                                    |
| Line items                     | Product names, variant choices, quantities, prices, discounts, taxes, shipping lines, and order totals.               | Order details make business sense and totals reconcile within accepted differences.                             |
| Transactions                   | Payment labels, transaction references, donation payments, refund references, and financial notes where included.     | Finance and support teams can interpret historical payment context.                                             |
| Subscriptions or payment plans | Subscription orders, payment-plan history, recurring-order references, renewal expectations, and accepted exclusions. | The merchant understands what is historical data, what is live billing setup, and what needs separate handling. |
| Fulfillment                    | Fulfillment statuses, tracking references, shipping services, external fulfillment IDs, and staff notes.              | Fulfillment history is understandable without implying the target store has rebuilt every external workflow.    |
| Refunds and adjustments        | Refunded orders, partial refunds, canceled orders, exchanges, discounts, and manual adjustments.                      | Exceptions are readable and support staff can explain the order history.                                        |

Validation should include both ordinary orders and exception orders. A sample with only clean paid orders is not enough for launch confidence.

### Checkout, Payment, Tax, Shipping, and Discount Validation <a href="#checkout-payment-tax-shipping-and-discount-validation" id="checkout-payment-tax-shipping-and-discount-validation"></a>

Checkout-related validation should separate migrated historical values from live target settings. Many launch problems happen when these two categories are mixed.

| Area      | Migrated-history validation                                                                          | Target-side validation                                                                                       |
| --------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Checkout  | Historical checkout fields and notes should remain understandable where included.                    | Live checkout form, required fields, customer emails, and policies must be configured in Squarespace.        |
| Payments  | Payment method labels and transaction references should be readable in historical orders.            | Payment providers, capture behavior, payout setup, and test transactions require target-side setup.          |
| Tax       | Historical tax lines should be checked for readability and total reconciliation.                     | Tax rules, regions, exemptions, and calculation behavior must be configured and tested separately.           |
| Shipping  | Historical shipping methods, costs, tracking references, and fulfillment notes should remain useful. | Shipping zones, rates, carriers, pickup options, and fulfillment settings must be configured in Squarespace. |
| Discounts | Historical discount codes and order-level discount values should be understandable.                  | Active promotions, discount rules, eligibility, and coupon timing should be configured in the target store.  |

This separation prevents a valid migration output from being treated as a failed migration because live store setup is incomplete.

### Content, Design, URL, and SEO Validation <a href="#content-design-url-and-seo-validation" id="content-design-url-and-seo-validation"></a>

Squarespace validation must include content and presentation because the platform is often chosen for design-led sites. A migration can move records but still require target-side decisions about page layout, navigation, sections, and launch presentation.

| Content area              | What to validate                                                                                              | Pass condition                                                                                   |
| ------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| CMS Pages                 | Page titles, body content, media, slugs, page hierarchy, navigation placement, and important calls to action. | Key pages are present, readable, and ready for layout review.                                    |
| Blog Posts                | Titles, dates, authors where supported, body content, media, categories or tags, slugs, and SEO fields.       | Blog content remains usable and high-value posts retain path strategy.                           |
| Media                     | Image files, galleries, downloads, embedded media, alt text where applicable, and broken references.          | Content pages and product pages do not rely on missing or broken assets.                         |
| Templates and sections    | Layout-dependent pages, landing pages, forms, promotional sections, and mobile presentation.                  | The merchant knows which presentation work is target-side design work rather than migrated data. |
| URLs and redirects        | Product URLs, page URLs, blog URLs, collection paths, redirects, canonical expectations, and internal links.  | High-value traffic paths have a clear redirect and SEO validation plan.                          |
| Domains and launch timing | Domain connection, SSL behavior, redirect timing, sitemap expectations, and go-live sequence.                 | Launch steps are separated from migration output and validated before final switch.              |

A content validation pass should identify which pages are ready, which require manual styling, which require redirects, and which should be excluded or rebuilt.

### Apps, APIs, External Systems, and Unsupported Data Validation <a href="#apps-apis-external-systems-and-unsupported-data-validation" id="apps-apis-external-systems-and-unsupported-data-validation"></a>

Squarespace migrations can involve app-owned data, API-supported records, and external systems. Validation should make unsupported or custom-dependent records visible before launch.

| Dependency type               | Validation priority                                                                                                                                            | Pass condition                                                                                          |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| API-supported records         | Products, inventory, orders, contacts, transactions, profiles, and webhooks should be checked against supported target behavior.                               | Data that can be represented in Squarespace is readable and connected where expected.                   |
| Third-party sales channels    | Imported orders, external references, and channel-specific fields should be checked if included.                                                               | Staff can distinguish Squarespace-native history from imported channel history.                         |
| External systems              | CRM, fulfillment, inventory, accounting, subscription, donation, booking, email marketing, and analytics systems should be reviewed for retained dependencies. | The merchant knows which systems need reconnection, manual configuration, or Custom Service review.     |
| Unsupported source structures | Custom product builders, advanced bundles, complex memberships, gated content, custom checkout logic, and source-only workflows.                               | Unsupported behavior is documented as exclusion, manual rebuild, Add-on scope, or Custom Service scope. |
| Custom fields and identifiers | External IDs, staff notes, custom attributes, custom metadata, and operational references.                                                                     | Important custom references are mapped, retained, or clearly excluded.                                  |

Validation should not hide unsupported behavior. It should expose it early enough for the merchant to choose a realistic launch plan.

### Add-ons and Custom Service Output Validation <a href="#add-ons-and-custom-service-output-validation" id="add-ons-and-custom-service-output-validation"></a>

When a Squarespace migration includes Add-ons or Custom Service, validation should confirm the specific output promised by that scope. It should not assume that an Add-on or Custom Service automatically rebuilds the whole website.

| Scope type           | What to validate                                                                                                            | Boundary to preserve                                                                                            |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Add-ons              | Filtered records, additional mapping, content/SEO handling, metadata handling, or other supported bounded outputs.          | Add-ons do not replace Custom Service, custom development, design rebuild, payment setup, or app configuration. |
| Custom Service       | Tailored extraction, mapping, custom handling, special validation, or unsupported-record treatment defined for the project. | Custom Service should be validated against the agreed scope, not against every possible source-store feature.   |
| Accepted exclusions  | Records or behaviors intentionally excluded from migration.                                                                 | Exclusions should be documented so they do not appear later as missing-data defects.                            |
| Manual rebuild items | Design, template, app, subscription, membership, form, booking, or integration work outside migration scope.                | Target-side rebuild work should be tracked separately from migration validation.                                |

A pass requires clear evidence that each special handling item was checked against its own acceptance criteria.

### Entity Points and Validation Scope <a href="#entity-points-and-validation-scope" id="entity-points-and-validation-scope"></a>

Entity Points should be validated against migration scope, not only against store totals. Squarespace projects can include products, customers, orders, Blog Posts, CMS Pages, and supporting records, so validation should check what was counted, what moved, and what was excluded.

| Scope area             | Validation check                                                                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Products               | Confirm that migrated product records match the agreed product scope, including product-type and variant-heavy examples.                         |
| Customers and contacts | Confirm which customer-like records were included and which subscriber, donor, member, or marketing records were excluded or handled separately. |
| Orders                 | Confirm that migrated order history matches the agreed date range, status rules, and exclusion logic.                                            |
| Blog Posts             | Confirm that migrated Blog Posts match the agreed content scope. New Blog Posts consume Entity Points when migrated for the first time.          |
| CMS Pages              | Confirm whether pages were migrated, rebuilt manually, excluded, or handled through Add-ons or Custom Service.                                   |
| Exclusions             | Confirm that obsolete products, outdated pages, test orders, inactive contacts, and unsupported data were excluded intentionally.                |

Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when they are migrated for the first time. This remains true even when the customer performs a new migration for the same migration path.

### Additional Migration Options and Revalidation <a href="#additional-migration-options-and-revalidation" id="additional-migration-options-and-revalidation"></a>

Additional Migration Options matter when new activity occurs after an earlier migration action. Validation should define what must be rechecked so late-stage changes do not create hidden launch risk.

| Later change                                    | Revalidation priority                                                                                          |
| ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| New products or product updates                 | Recheck product fields, variants, inventory, images, Store Pages, SEO fields, and collection placement.        |
| New customers, contacts, subscribers, or donors | Recheck identity, duplicates, marketing preference meaning, addresses, and order relationships.                |
| New orders or transactions                      | Recheck order history, line items, totals, payment labels, tax, shipping, discounts, fulfillment, and refunds. |
| New Blog Posts or content updates               | Recheck slugs, SEO fields, images, internal links, categories or tags, and redirects.                          |
| Late checkout or domain setup                   | Recheck that live store settings and migrated history are not being confused.                                  |
| Integration changes                             | Recheck external IDs, app connections, fulfillment references, CRM fields, and accepted exclusions.            |

Additional Migration Options should always be paired with validation. A later migration action is only useful if the merchant confirms that new or changed records still support launch requirements.

### Full Migration Acceptance Checklist <a href="#full-migration-acceptance-checklist" id="full-migration-acceptance-checklist"></a>

Before approving the Squarespace migration, the merchant should review the target store using a checklist that reflects both commerce and content behavior.

| Acceptance area                  | Pass condition                                                                                                                                                  |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products and Store Pages         | Important products, product types, variants, inventory, images, Store Pages, and merchandising paths are correct or have documented target-side tasks.          |
| Customers and contacts           | Customer, contact, subscriber, donor, member, and guest-buyer records have the expected business meaning.                                                       |
| Orders and transactions          | Historical orders, transactions, refunds, fulfillment references, discounts, tax, and shipping details are readable and reconciled within accepted differences. |
| Content and media                | CMS Pages, Blog Posts, images, downloads, internal links, navigation, and mobile display are checked for launch-critical pages.                                 |
| URLs and SEO                     | High-value paths, redirects, metadata, canonical expectations, and internal links have been reviewed.                                                           |
| Checkout and operations          | Payment, tax, shipping, fulfillment, notifications, policies, and domains are treated as target-side setup and tested separately.                               |
| Integrations and custom handling | Add-ons, Custom Service outputs, external systems, unsupported records, and accepted exclusions are checked against agreed scope.                               |
| Follow-up changes                | Additional Migration Options and revalidation needs are planned if new records or content changes occur before launch.                                          |

Acceptance should be based on representative records and critical workflows. It should not rely only on record counts or a quick visual check of the homepage.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace validation should prove that the target store can support real post-migration work. Products, orders, customers, contacts, content, media, URLs, redirects, SEO fields, and integrations must be reviewed together because Squarespace combines commerce records with site presentation and hosted launch settings.

The strongest validation process begins with Demo Migration, classifies findings clearly, checks special records and edge cases, and repeats the right checks after Full Migration. When Add-ons, Custom Service, Entity Points, or Additional Migration Options are involved, each should have its own acceptance criteria so the merchant knows what passed, what needs target-side setup, and what remains outside migration scope.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should I validate first after a Squarespace Demo Migration?**

Start with representative products, customers, contacts, orders, Store Pages, CMS Pages, Blog Posts, media, URLs, redirects, and SEO fields. The goal is to identify whether the target store structure is usable before Full Migration.

**Should checkout, payment, tax, and shipping be judged as migration output?**

Historical values in migrated orders should be checked for readability, but live checkout, payment providers, tax settings, shipping rules, notifications, and policies are target-side configuration tasks that need separate testing in Squarespace.

**How should Squarespace product variants be validated?**

Validate products with different option structures, variant SKUs, prices, images, inventory values, and availability. Variant-heavy products should be sampled separately from simple products because they expose different migration risks.

**How should Add-ons or Custom Service be validated?**

Validate them against the agreed scope. Add-ons should prove the specific bounded output they were selected for. Custom Service should prove the tailored extraction, mapping, handling, or validation defined for the project.

**Do Additional Migration Options require another validation round?**

Yes. When later products, customers, orders, Blog Posts, content changes, SEO updates, or integration changes are migrated or handled, the affected areas should be revalidated before launch.
