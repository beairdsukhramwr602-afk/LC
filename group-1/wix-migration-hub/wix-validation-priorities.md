# Wix Validation Priorities

Wix migration validation should prove that the target site can operate as a hosted website-and-commerce environment, not only that records appear in the Wix dashboard. Wix combines Wix Stores, Wix eCommerce services, site content, members, contacts, apps, Velo/API logic, service plugins, custom catalogs, SEO controls, domains, and external systems. Validation therefore needs to test business meaning across storefront display, product choice behavior, checkout readiness, historical order readability, customer/contact context, content continuity, and integration expectations.

Validation should happen after Demo Migration and again after Full Migration. Demo Migration validation decides whether the mapping, scope, and target expectations are safe enough to continue. Full Migration validation decides whether the target site is ready for launch, handoff, or final correction before traffic moves to Wix.

### What Wix Validation Must Prove <a href="#what-wix-validation-must-prove" id="what-wix-validation-must-prove"></a>

A Wix validation plan should confirm three different outcomes: migrated records are present, migrated records keep their business meaning, and target Wix configuration supports live operations. These outcomes are related, but they are not interchangeable.

| Validation layer           | What to prove                                                                                                                | Why it matters for Wix                                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Record presence            | Products, customers, orders, CMS Pages, Blog Posts, media, and eligible supporting records are visible where expected.       | Count checks alone can miss broken options, app-owned records, order context, and site-navigation issues. |
| Business meaning           | Products, customer/contact records, orders, content, URLs, and app-related data still represent the same commercial purpose. | Wix may store or display similar data differently from the Source Platform.                               |
| Storefront usability       | Shoppers can find products, select options, enter checkout, understand prices, and receive the intended store experience.    | Wix is a site-builder commerce platform, so visual and navigation context can affect migration quality.   |
| Administrative readability | Staff can read orders, customer history, fulfillment details, payment labels, notes, discounts, and source references.       | Historical data must remain useful even when live checkout settings are configured separately.            |
| Launch readiness           | Payment, shipping, tax, domain, redirect, SEO, app, and integration checks are complete before go-live.                      | Migrated history does not automatically configure future transaction behavior.                            |

A clean validation outcome should identify what passed, what needs target setup, what needs an Add-on, what requires Custom Service review, and what is accepted as outside migration scope.

### Demo Migration Validation Priorities <a href="#demo-migration-validation-priorities" id="demo-migration-validation-priorities"></a>

Demo Migration validation should use representative records, not only easy records. Wix migrations can look clean when simple products and straightforward orders are sampled, while complex product choices, content paths, member data, app behavior, or service-plugin requirements remain untested.

| Sample group              | Include these records                                                                                                                    | Pass condition                                                                                                      |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Simple products           | Products with ordinary title, SKU, price, image, description, collection, inventory, and SEO values.                                     | Product data appears correctly and can be found through the expected storefront path.                               |
| Complex products          | Products with options, choices, variants, modifiers, multiple images, price differences, stock differences, or personalization fields.   | Shopper selections preserve price, SKU, stock, image, fulfillment, or order-detail meaning where supported.         |
| Collections and discovery | Products assigned to old categories, collections, filters, menus, landing pages, or product groups.                                      | Merchandising and navigation paths remain understandable in Wix.                                                    |
| Orders                    | Paid, pending, canceled, refunded, discounted, taxed, shipped, and guest orders.                                                         | Staff can read line items, totals, taxes, shipping, payment labels, fulfillment context, notes, and customer links. |
| Customers and members     | Registered customers, contacts, site members, subscribers, app participants, and guest buyers.                                           | The target meaning of each record is clear and not collapsed into the wrong identity type.                          |
| Content and SEO           | CMS Pages, Blog Posts, images, internal links, high-value slugs, metadata, and redirects.                                                | Important content remains reachable, readable, and SEO-sensitive paths have a migration or redirect plan.           |
| App or custom behavior    | Records tied to Wix apps, Velo/API logic, service plugins, custom catalogs, external payment, external shipping, or third-party systems. | The item is classified as standard scope, Add-on scope, Custom Service review, target setup, or accepted exclusion. |

Demo Migration should not be approved because most records look correct. It should be approved only when the sample proves the difficult parts of the Wix migration are understood.

### Product and Catalog Validation <a href="#product-and-catalog-validation" id="product-and-catalog-validation"></a>

Product validation should confirm more than product count. Wix products must make sense as storefront records, catalog records, search results, product-page content, collection items, checkout items, and order-line references.

| Product area                  | What to validate                                                                                              | Common Wix-specific failure pattern                                                                           |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Product identity              | Name, SKU, slug, visibility, status, product URL, and duplicate handling.                                     | Products exist but cannot be found through the expected storefront or old SKU logic.                          |
| Product content               | Description, rich text, short content, images, galleries, labels, ribbons, and SEO fields.                    | Text or media migrates but loses formatting, image order, alt context, or product-page presentation.          |
| Pricing and inventory         | Base price, sale price, taxable status, stock quantity, stock status, weight, and fulfillment-related fields. | Price or stock appears correct at product level but fails for variants or options.                            |
| Product options and choices   | Shopper-selectable options such as size, color, material, style, personalization, and paid choices.           | Options display visually but do not preserve SKU, stock, price, image, or order-detail meaning.               |
| Variants and modifiers        | Variant-level SKU, price, stock, image, availability, and modifier behavior.                                  | A complex source product is simplified into a product that no longer supports the original purchase decision. |
| Collections and merchandising | Collection assignment, product groups, filters, search, sort order, product galleries, and landing pages.     | Category data migrates but shopper discovery paths are not rebuilt in Wix.                                    |
| Custom catalogs               | Products or sellable items supplied through external catalogs, apps, or service plugins.                      | A record looks like a product but belongs to external catalog or Custom Service logic.                        |

The strongest product validation samples include simple products, variable products, products with option-specific values, products with many images, products attached to important collections, and products affected by apps or external systems.

### Checkout, Cart, Order, Payment, Shipping, and Tax Validation <a href="#checkout-cart-order-payment-shipping-and-tax-validation" id="checkout-cart-order-payment-shipping-and-tax-validation"></a>

Wix order history and live checkout readiness should be validated separately. Migrated historical orders can preserve operational history, but they do not configure payment providers, shipping rates, tax rules, checkout validation, fulfillment workflows, discounts, or service-plugin behavior for future transactions.

| Area                     | Historical validation                                                                                                                                                               | Live-readiness validation                                                                                         |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Cart and checkout        | Confirm whether historical checkout context or abandoned-checkout data is included, excluded, or separately scoped.                                                                 | Test target checkout flow, required fields, validation, payment, shipping, tax, discounts, and buyer messages.    |
| Orders                   | Validate order number/reference, status, date, customer link, guest order behavior, line items, totals, discounts, taxes, shipping, payment label, fulfillment, refunds, and notes. | Confirm future orders will be created correctly through Wix checkout after target settings are configured.        |
| Payments                 | Confirm historical payment labels, transaction references, payment state, and refund context where available.                                                                       | Confirm payment providers and external payment services are configured and tested in Wix.                         |
| Shipping and fulfillment | Confirm shipping method labels, shipping totals, addresses, tracking references, fulfillment notes, and delivery context.                                                           | Confirm shipping rates, pickup/delivery rules, fulfillment services, and shipping service plugins are configured. |
| Taxes                    | Confirm tax totals, tax labels, inclusive/exclusive meaning, and historical order readability.                                                                                      | Confirm Wix tax configuration reflects target launch requirements.                                                |
| Discounts and coupons    | Confirm migrated discount values, coupon references, campaign labels, and order-level promotion history.                                                                            | Confirm active discount rules and campaign behavior are recreated or configured in Wix where needed.              |

A pass condition for this area should state that historical orders are readable and future checkout has been tested through Wix target configuration. One does not prove the other.

### Customer, Contact, Member, and CRM Validation <a href="#customer-contact-member-and-crm-validation" id="customer-contact-member-and-crm-validation"></a>

Wix can involve customers, contacts, site members, subscribers, CRM-style records, marketing consent, form participants, app users, and external-system identifiers. Validation should separate these meanings before approving the migration.

| Identity area         | What to validate                                                                                                  | Pass condition                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Customers             | Customer names, emails, billing addresses, shipping addresses, order links, and purchase history.                 | Staff can connect customer records to migrated orders without confusion.                                   |
| Contacts              | Contact records, phone numbers, email values, notes, labels, segmentation, and CRM-style context where supported. | Commerce contacts are not mistaken for full site-member accounts unless that is intended.                  |
| Members               | Login/account status, member profiles, role-like meaning, subscriber status, and app membership relationships.    | Member-related behavior is classified as migrated data, target setup, app data, or Custom Service review.  |
| Guest buyers          | Orders placed without a customer account.                                                                         | Guest orders remain readable and do not create misleading account expectations.                            |
| Marketing and consent | Newsletter status, opt-in fields, tags, communication preferences, and campaign data.                             | Consent and marketing fields are treated carefully and not assumed to transfer as active campaign logic.   |
| External IDs          | CRM, ERP, shipping, accounting, marketplace, or loyalty identifiers.                                              | External references remain available where needed for reconciliation or are listed as accepted exclusions. |

Customer validation should include both ordinary customers and edge cases: guest buyers, repeat buyers, customers with multiple addresses, members with non-commerce context, subscribers, and customers linked to apps or external systems.

### CMS Pages, Blog Posts, Media, URLs, and SEO Validation <a href="#cms-pages-blog-posts-media-urls-and-seo-validation" id="cms-pages-blog-posts-media-urls-and-seo-validation"></a>

Wix migration quality can depend heavily on site content and search continuity. Product records may be correct while landing pages, Blog Posts, internal links, redirects, images, or SEO fields remain incomplete.

| Site and SEO area            | What to validate                                                                                              | Pass condition                                                               |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| CMS Pages                    | Page title, body content, images, buttons, forms, embedded assets, internal links, and page purpose.          | Important pages are migrated, rebuilt, redirected, or intentionally retired. |
| Blog Posts                   | Post title, body, publication date, author context, categories, tags, images, internal links, and SEO values. | Blog content remains readable and high-value posts are not orphaned.         |
| Media                        | Product images, page images, galleries, files, alt text, image references, and reused media.                  | Images load correctly in product, page, and blog contexts.                   |
| Product and collection URLs  | Product slugs, collection paths, landing pages, and navigation links.                                         | High-value commerce URLs have matching target URLs or redirect handling.     |
| SEO fields                   | Titles, descriptions, canonical expectations, headings, indexability, and structured data expectations.       | SEO-sensitive records have a planned target representation.                  |
| Redirects and internal links | Old-to-new redirects, menu links, footer links, blog links, campaign links, and product references.           | Priority shopper and search paths resolve correctly after migration.         |
| Domain and launch routing    | Domain connection, SSL, primary domain, preview URLs, staging expectations, and launch timing.                | Domain work is separated from data migration and tested before launch.       |

A Wix content validation pass should not require perfect source design parity. It should require a clear decision for each important content area: migrated as data, rebuilt in Wix, redirected, replaced, or retired.

### Apps, Velo, Service Plugins, Custom Catalogs, and External Systems <a href="#apps-velo-service-plugins-custom-catalogs-and-external-systems" id="apps-velo-service-plugins-custom-catalogs-and-external-systems"></a>

Apps and custom logic often determine whether a Wix migration can operate after launch. Validation should identify where the target result depends on Wix apps, Velo/API work, service plugins, custom catalogs, or external systems rather than standard migrated records.

| Dependency type          | Validation focus                                                                                                                           | Pass condition                                                                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| Wix apps                 | Bookings, events, restaurants, memberships, pricing plans, loyalty, forms, reviews, donations, subscriptions, and other app-owned records. | App-owned data is classified as supported migration, target setup, Add-on scope, Custom Service, or accepted exclusion.                 |
| Velo/API logic           | Custom code, calculated fields, custom product behavior, forms, workflows, validation, and external data connections.                      | Required custom behavior has a documented Wix implementation path or exclusion.                                                         |
| Service plugins          | Custom fees, shipping rates, checkout/cart validation, external payment services, and custom catalog integration.                          | Live behavior is tested separately from historical data migration.                                                                      |
| External systems         | ERP, CRM, PIM, WMS, marketplace, accounting, tax, shipping, payment, email, analytics, and loyalty systems.                                | Identifiers, sync points, ownership, and post-migration reconciliation requirements are documented.                                     |
| Custom catalogs          | Sellable items managed outside standard Wix Stores structures.                                                                             | Catalog ownership and checkout integration are reviewed before launch approval.                                                         |
| Custom fields and tables | Source metadata, custom records, app tables, and business-specific values.                                                                 | Values are either migrated through supported fields, handled through Add-ons, reviewed under Custom Service, or excluded intentionally. |

The validation standard should be direct: standard migrated records should be checked inside Wix; custom behavior should be checked through the feature, app, integration, or service-plugin path that will actually run the target store.

### Add-ons and Custom Service Validation <a href="#add-ons-and-custom-service-validation" id="add-ons-and-custom-service-validation"></a>

Add-ons and Custom Service should be validated by output, not by assumption. The validation question is whether the expected result exists in Wix and supports the intended business use.

| Scope area          | What to validate                                                                                                                | Boundary to preserve                                                                                                                           |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Standard Add-ons    | Specific configured extensions to normal migration behavior, such as selected extra data handling or mapping.                   | Add-ons solve defined migration needs; they are not a substitute for full custom implementation.                                               |
| Tailored Add-ons    | Store-specific migration enhancements agreed for the Wix path.                                                                  | The expected output should be checked against the agreed migration outcome, not broad site rebuild expectations.                               |
| Custom Add-ons      | Highly specific migration handling for selected records or fields.                                                              | Custom Add-ons should not be treated as full Custom Service unless the scope says so.                                                          |
| Custom Service      | Non-standard Wix migration needs, custom records, app-owned data, external systems, Velo/API logic, or unusual target behavior. | Custom Service review clarifies scope; it does not automatically mean Next-Cart performs every target build, design, app, or integration task. |
| Accepted exclusions | Data or behavior outside migration scope.                                                                                       | Exclusions should be named clearly so validation does not treat them as defects.                                                               |

A validation checklist should include every Add-on and Custom Service item agreed during planning. If a required output cannot be validated in Wix, it should stay open until the missing value, behavior, setup, or exclusion is resolved.

### Entity Points and Additional Migration Options Validation <a href="#entity-points-and-additional-migration-options-validation" id="entity-points-and-additional-migration-options-validation"></a>

Entity Points validation should focus on eligible record scope and duplicate counting. New Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when migrated for the first time, even when the customer performs a new migration for the same migration path.

| Validation topic        | What to check                                                                             | Pass condition                                                                                 |
| ----------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Eligible records        | Product, Customer, Order, and Blog Posts records included in the Wix migration scope.     | Counts match the agreed scope and service license logic.                                       |
| First-time migration    | Newly added eligible records after the previous migration step.                           | New eligible records are counted only when they are migrated for the first time.               |
| Duplicate protection    | Records already counted through the service license.                                      | Previously counted records are not counted again only because another migration action occurs. |
| Follow-up activity      | Additional Migration Options after Demo Migration, Full Migration, or launch preparation. | New data, updated records, and changed target configuration are revalidated before acceptance. |
| Content and SEO effects | New Blog Posts, product URLs, redirects, and internal links after follow-up activity.     | Follow-up migration does not create unresolved content or SEO gaps.                            |

Additional Migration Options should trigger revalidation, not blind approval. Products, customers, orders, Blog Posts, coupons, URLs, app records, and integration references added after the original validation sample may introduce new issues even if the first migration passed.

### Wix Validation Checklist <a href="#wix-validation-checklist" id="wix-validation-checklist"></a>

A practical Wix validation checklist should move from record checks to shopper-path checks, staff workflow checks, content/SEO checks, and integration checks.

| Validation stage  | Required checks                                                                                                                       | Owner decision                                                                |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Record review     | Products, collections, customers, contacts, members, orders, CMS Pages, Blog Posts, media, and eligible records.                      | Confirm records are present and meaningful.                                   |
| Storefront review | Product pages, collection pages, menus, filters, search, cart entry, option selection, images, prices, inventory, and mobile display. | Confirm shoppers can browse and choose products correctly.                    |
| Checkout review   | Payment, shipping, tax, discounts, custom fees, validation, checkout fields, and fulfillment behavior.                                | Confirm future transactions are configured separately from historical orders. |
| Admin review      | Order history, customer links, guest orders, statuses, refunds, notes, payment labels, shipping context, and external IDs.            | Confirm staff can operate and reconcile records.                              |
| Content review    | CMS Pages, Blog Posts, landing pages, internal links, media, menus, SEO metadata, redirects, and high-value URLs.                     | Confirm site and search continuity.                                           |
| Custom review     | Apps, Velo, service plugins, custom catalogs, custom fields, external systems, Add-ons, and Custom Service outputs.                   | Confirm scope, setup, exclusions, or remaining work.                          |
| Follow-up review  | Additional Migration Options, new eligible records, changed data, and target configuration changes.                                   | Confirm revalidation before final acceptance.                                 |

The checklist should be used twice: once after Demo Migration to decide whether the migration plan is safe, and again after Full Migration to decide whether the Wix site is launch-ready.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix validation should prove that migrated data works inside the target site, storefront, checkout, order history, content structure, SEO plan, apps, and integrations. A successful Wix migration is not validated by record counts alone. It is validated when shoppers can use the site, staff can operate the store, content and URLs remain controlled, custom or app-dependent records are classified correctly, and follow-up migration activity is rechecked before acceptance.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be checked first after a Wix Demo Migration?**

Start with representative records: simple and complex products, variant or option-heavy products, important collections, guest and registered customer records, different order statuses, discounted or refunded orders, CMS Pages, Blog Posts, media, and any app or custom records that could affect launch quality.

**Does migrated order history prove Wix checkout is ready?**

No. Historical orders and live checkout setup are different validation areas. Order history should be checked for readability, totals, line items, status, payment labels, shipping, tax, refunds, and notes. Live checkout should be tested through Wix payment, shipping, tax, discount, validation, and fulfillment settings.

**How should Wix apps and custom behavior be validated?**

Validate them through the function they control. App-owned records, Velo/API logic, service plugins, custom catalogs, external payment services, shipping rules, and third-party systems should be classified as standard scope, Add-on scope, Custom Service review, target setup, or accepted exclusion.

**Do Add-ons replace Custom Service for Wix validation?**

No. Add-ons should be validated against specific migration outputs. They are not a substitute for Custom Service, custom development, target design work, app configuration, or integration implementation when those are required.

**When should Additional Migration Options be revalidated for Wix?**

Revalidate whenever later migration activity introduces new products, customers, orders, Blog Posts, content changes, URL changes, app records, custom fields, or integration references. New eligible records may affect Entity Points when migrated for the first time, while records already counted through the service license should not be counted again only because another migration action occurs.
