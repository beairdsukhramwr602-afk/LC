# Wix Constraints and Risks

Wix migration risk comes from the way Wix functions as a hosted site-builder commerce Target Platform that combines hosted site building, commerce services, apps, content, members, contacts, checkout, orders, SEO, integrations, and developer extension points. A source store may contain data and behavior that cannot be copied into Wix as identical structures. The risk is not only missing records. It is loss of business meaning when products, orders, customer accounts, content, URLs, app records, or custom workflows are interpreted too narrowly.

A Wix risk review should separate standard migration records from target setup, app configuration, site implementation, Add-ons, Custom Service, and accepted exclusions. That separation prevents merchants from assuming that source design, checkout logic, app behavior, integration syncs, or custom code move automatically with catalog and order data.

### Core Wix Migration Risk Areas <a href="#core-wix-migration-risk-areas" id="core-wix-migration-risk-areas"></a>

| Risk area             | What can go wrong                                                                                                | Prevention focus                                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Hosted architecture   | Source code, server logic, database behavior, or checkout customization cannot be copied directly.               | Translate custom behavior into Wix-supported setup, apps, Velo/API work, service plugins, or Custom Service review. |
| Product model         | Options, choices, variants, modifiers, bundles, subscriptions, bookings, or app-owned products may lose meaning. | Classify product structures before Demo Migration and test difficult products.                                      |
| Checkout and orders   | Historical order readability is confused with live checkout readiness.                                           | Validate order history separately from payment, tax, shipping, discount, cart, and checkout setup.                  |
| Customers and members | Customer, contact, member, subscriber, CRM, and app meanings are treated as one record type.                     | Define each customer-related meaning and test account expectations.                                                 |
| Site and content      | CMS Pages, Blog Posts, media, menus, design sections, and landing pages are assumed to move like products.       | Inventory content, media, internal links, priority pages, and site rebuild needs.                                   |
| SEO and URLs          | Product, page, collection, Blog Post, and redirect behavior differs from the source platform.                    | Prepare priority URL mapping before launch.                                                                         |
| Apps and integrations | App-owned records, Velo/API logic, service plugins, and external-system data are missed.                         | Identify dependencies before scope is confirmed.                                                                    |

### Hosted Site-Builder Constraints <a href="#hosted-site-builder-constraints" id="hosted-site-builder-constraints"></a>

Wix is a hosted platform. That is useful for merchants that want managed infrastructure, but it creates constraints for migrations from open-source, plugin-heavy, or custom-coded stores.

| Source expectation                            | Wix constraint                                                                                                         | Risk if ignored                                                                       |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Direct database transfer preserves everything | Wix uses supported platform structures, APIs, apps, and configuration rather than merchant-controlled database tables. | Custom tables or hidden metadata may not appear in the target business process.       |
| Theme or template moves with data             | Wix presentation depends on the target site editor, templates, sections, widgets, apps, and mobile layout.             | Storefront may look incomplete even when data migration succeeded.                    |
| Custom checkout scripts transfer directly     | Wix checkout behavior must use supported settings, apps, APIs, or service plugins.                                     | Fees, validation rules, payment logic, or delivery behavior may not match the source. |
| Source extensions are equivalent to Wix apps  | Apps differ in data ownership, configuration, and exportability.                                                       | App records may be excluded, simplified, or require Custom Service review.            |

This risk should be discussed before Demo Migration, not after the merchant expects identical behavior.

### Product, Variant, Modifier, and Catalog Risks <a href="#product-variant-modifier-and-catalog-risks" id="product-variant-modifier-and-catalog-risks"></a>

Wix product migration risk increases when a source catalog has more than simple products, prices, images, and descriptions.

| Catalog pattern                   | Wix risk                                                                                            | Recommended check                                                           |
| --------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Standard products                 | Basic fields may migrate cleanly but still need display, SEO, collection, and media validation.     | Sample simple products and priority collections.                            |
| Options and variants              | Option choices may not preserve price, SKU, stock, image, or fulfillment meaning.                   | Test variant-bearing products with operational attributes.                  |
| Modifiers and personalization     | Paid fields, engraving, file upload, or custom instructions may not behave as source product logic. | Classify as supported field, app behavior, Add-on, or Custom Service.       |
| Bundles, kits, composite products | Buying logic may depend on source extensions.                                                       | Decide whether target simplification is acceptable.                         |
| External catalog source           | Wix may require custom catalog or integration planning.                                             | Review catalog ownership, identifiers, sync direction, and checkout impact. |

A product record should not be considered validated until product discovery and purchase behavior are also checked.

### Checkout, Cart, Payment, Shipping, Tax, Discount, and Order Risks <a href="#checkout-cart-payment-shipping-tax-discount-and-order-risks" id="checkout-cart-payment-shipping-tax-discount-and-order-risks"></a>

Wix distinguishes historical order data from live checkout configuration. Migration can preserve order history while still requiring target-side setup before launch.

| Area                     | Risk                                                                                                              | Prevention                                                                                       |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Cart and checkout        | Source-store cart rules, validation, custom fields, and fees may not transfer as records.                         | Identify checkout behavior that requires Wix settings, apps, service plugins, or Custom Service. |
| Payments                 | Historical payment labels do not configure live payment providers.                                                | Configure target payment providers and test transactions separately.                             |
| Shipping and fulfillment | Source delivery rules, pickup, rates, tracking, and fulfillment services may not map one-to-one.                  | Separate migrated order data from target shipping and fulfillment setup.                         |
| Tax                      | Historical tax amounts do not prove target tax calculation readiness.                                             | Validate tax configuration for live selling separately.                                          |
| Discounts                | Source promotion engines can differ from Wix discount behavior.                                                   | Test simple and complex discount examples.                                                       |
| Orders                   | Line items, totals, statuses, refunds, notes, and fulfillment context may lose readability if metadata is missed. | Sample both simple and operationally complex orders.                                             |

### Customer, Contact, Member, and CRM Risks <a href="#customer-contact-member-and-crm-risks" id="customer-contact-member-and-crm-risks"></a>

Wix can represent customer-related data across customers, contacts, members, subscribers, app participants, CRM-style records, and external-system identifiers. Treating these as one entity creates risk.

| Customer-related meaning | Risk                                                                                  | Review action                                                               |
| ------------------------ | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Commerce customer        | Order history may not connect to the expected target customer context.                | Validate order-customer relationships and guest order handling.             |
| Site member              | Login/account expectations may not be the same as customer migration.                 | Confirm whether accounts, member permissions, and login flows are in scope. |
| Contact or subscriber    | Marketing, consent, tags, segments, and CRM context may have platform-specific rules. | Separate contact migration from customer/order validation.                  |
| App participant          | Bookings, events, memberships, pricing plans, and forms may own their own records.    | Identify app-owned data before scope is finalized.                          |
| External profile         | ERP, CRM, loyalty, or support systems may depend on stable IDs.                       | Preserve or map identifiers where required.                                 |

### Site Content, Design, URL, and SEO Risks <a href="#site-content-design-url-and-seo-risks" id="site-content-design-url-and-seo-risks"></a>

Wix migration quality can be undermined by content and SEO gaps even when commerce data appears complete.

| Site area                | Risk                                                                                      | Prevention                                                                   |
| ------------------------ | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| CMS Pages                | Page structures, sections, embeds, forms, and layouts may need rebuild work.              | Inventory priority pages and decide what migrates, rebuilds, or retires.     |
| Blog Posts               | Dates, authors, categories, tags, media, internal links, and metadata may need sampling.  | Validate blog samples separately from products.                              |
| Media                    | Image references may appear in products but fail in pages or Blog Posts.                  | Sample media across commerce and content contexts.                           |
| URLs and redirects       | Source paths may change across product, collection, page, and blog areas.                 | Prepare redirect mapping for high-value URLs.                                |
| SEO metadata             | Titles, descriptions, canonical behavior, structured data, and internal links may differ. | Validate search-sensitive pages before launch.                               |
| Design and mobile layout | Target pages may require Wix-specific layout decisions.                                   | Treat design parity as implementation scope, not automatic migration output. |

### Apps, Velo, Service Plugins, and Integration Risks <a href="#apps-velo-service-plugins-and-integration-risks" id="apps-velo-service-plugins-and-integration-risks"></a>

Apps and custom development can turn an ordinary Wix migration into a scoped technical project. The most common risk is assuming app behavior is standard data.

| Dependency       | Risk                                                                                                                   | Scope response                                                                       |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Wix apps         | Records may be owned by the app rather than standard Wix Stores data.                                                  | Confirm app data availability, accepted exclusions, or Custom Service needs.         |
| Velo/API logic   | Business behavior may depend on code, collections, or external calls.                                                  | Document logic before migration and classify it as implementation or Custom Service. |
| Service plugins  | Custom fees, shipping rates, cart/checkout validation, payment services, or catalog integrations affect live commerce. | Test behavior separately from historical order migration.                            |
| External systems | ERP, PIM, CRM, WMS, tax, payment, shipping, or accounting systems may rely on IDs and statuses.                        | Inventory fields, references, sync timing, and ownership.                            |

### Add-ons, Custom Service, Entity Points, and Follow-Up Risk <a href="#add-ons-custom-service-entity-points-and-follow-up-risk" id="add-ons-custom-service-entity-points-and-follow-up-risk"></a>

Add-ons should be used for specific migration needs, such as advanced mapping, filtering, configuration, or supported data handling. They are not a substitute for Custom Service, target site design, app implementation, or custom development.

Custom Service is relevant when Wix risk depends on non-standard source structures, app-owned records, custom catalogs, Velo/API behavior, service-plugin logic, or external-system workflows that require tailored evaluation.

Entity Points should be planned around eligible records that are migrated for the first time. New Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the merchant performs another migration action. New eligible records may consume Entity Points when migrated for the first time, even when the merchant performs a new migration for the same migration path.

Additional Migration Options can create renewed Wix risk when later products, customers, orders, Blog Posts, content, media, URLs, app data, or integration fields are added after the initial migration. Follow-up activity should be validated against the same Wix constraints rather than treated as a simple replay.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix migration risk is manageable when the merchant understands the difference between migrated data, hosted platform behavior, target configuration, app setup, site implementation, Add-ons, Custom Service, and accepted exclusions. The highest-risk projects are not always the largest stores. They are stores where custom catalog logic, checkout behavior, app-owned data, SEO-sensitive content, or external systems are discovered too late.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the biggest risk when migrating to Wix?**

The biggest risk is assuming that source behavior, design, apps, checkout logic, and integrations transfer automatically with products, customers, and orders. Wix requires target-specific setup and validation.

**Are Wix checkout risks the same as order migration risks?**

No. Historical order data and live checkout configuration are separate concerns. Orders can migrate for reference while payments, shipping, tax, discounts, cart rules, and checkout behavior still need target setup.

**When should a Wix migration use Custom Service review?**

Custom Service should be reviewed when the source depends on custom catalogs, Velo/API behavior, service plugins, app-owned records, unusual product structures, or external-system workflows that cannot be handled through standard scope or specific Add-ons.

**Can Additional Migration Options create new Wix risks?**

Yes. Follow-up migration activity can introduce new records, content, URLs, app dependencies, or integration fields that require renewed validation before launch or after launch.
