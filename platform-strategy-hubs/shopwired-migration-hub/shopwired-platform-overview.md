# ShopWired Platform Overview

ShopWired is a hosted commerce platform for merchants that want managed storefront operations with structured product management, customer and order administration, delivery and payment settings, B2B/trade features, apps, API access, and website content tools. For migration planning, its value is not simply that store records can be moved into another hosted system. The important question is whether the source store’s commercial logic can be expressed inside ShopWired’s supported catalog, account, checkout, content, and integration model.

A ShopWired migration should therefore be planned as a translation exercise. Products are not only names, descriptions, prices, and images. They may depend on categories, brands, variations, choices, extras, bundles, stock behavior, VAT or sales-tax treatment, delivery eligibility, search visibility, filters, product-page presentation, and app-supported extensions. Customers are not only contact records. They may represent registered users, guest buyers, trade customers, newsletter subscribers, pricing relationships, custom fields, and order-history associations. Orders are not only historical totals. They carry customer identity, billing and delivery context, payment information, discounts, refunds, status, fulfilment evidence, and sometimes downstream accounting or warehouse meaning.

The strongest ShopWired migration outcomes happen when those meanings are classified before the move. Straightforward records can be migrated directly. Platform settings should be configured in the target store. App-owned or external-system behavior should be reviewed separately. Custom fields, unusual option structures, B2B pricing rules, or integration identifiers may need deeper scope review instead of being treated as ordinary records.

### ShopWired Migration Thesis <a href="#shopwired-migration-thesis" id="shopwired-migration-thesis"></a>

ShopWired is best understood as a hosted commerce target with practical operational depth. It is not a blank technical framework, and it is not a simple brochure-store builder. It provides a managed commerce environment where merchants can operate products, categories, customers, orders, delivery, payment, VAT or sales tax, discounts, B2B/trade features, content, SEO, apps, and integrations through the platform.

That identity creates the central migration thesis: moving to ShopWired is successful when the source store’s selling model can be re-expressed through ShopWired’s platform structures without carrying over unnecessary legacy workarounds. A store with simple products, clear categories, ordinary customers, standard orders, and manageable checkout rules may move cleanly. A store with complex configurators, ERP-owned pricing, deeply customized checkout logic, channel-specific identifiers, or app-owned operational records needs earlier separation between migration, configuration, and Custom Service scope.

| Planning question                        | Why it matters in ShopWired                                                                             | What a good answer clarifies                                                                           |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| How are products actually purchased?     | ShopWired has specific structures for variations, choices, extras, bundles, and other product behavior. | Whether source options become supported product structures, target settings, Add-ons, or custom logic. |
| How is product discovery built?          | Categories, brands, menus, filters, search, and SEO all affect whether migrated products are usable.    | Which relationships and storefront paths must be recreated, validated, or redesigned.                  |
| How are customers segmented?             | ShopWired separates ordinary customer records from trade or B2B behavior where used.                    | Which customer data can migrate directly and which rules require configuration or review.              |
| What does order history need to prove?   | Historical orders support service, accounting, customer context, and fulfilment reference.              | Which order fields, statuses, totals, notes, refunds, and customer links must remain readable.         |
| Which behavior belongs to live checkout? | Delivery, payments, VAT/tax, offers, and checkout rules are target-store setup areas.                   | Which items are historical data and which must be configured before launch.                            |
| Which systems sit outside the store?     | Apps, APIs, webhooks, accounting, fulfilment, and marketplace tools may own critical data.              | Which identifiers, custom fields, or external records need Custom Service review.                      |

### What Changes When Moving to ShopWired <a href="#what-changes-when-moving-to-shopwired" id="what-changes-when-moving-to-shopwired"></a>

A migration to ShopWired changes both the data model and the operating model. Source data must land in a hosted platform where the store is managed through ShopWired’s administrative structures, supported feature set, theme system, app ecosystem, and API surfaces.

The biggest shift is that some source-side implementation details should not be copied literally. A legacy cart may have used custom fields to imitate product options. A self-hosted store may have relied on custom database tables for trade pricing. A simpler storefront builder may have placed product specification data in page content instead of product fields. An older system may have mixed customer records, newsletter records, and guest checkout data without clear identity rules. Those structures need interpretation before they are moved.

| Store area            | Source-store assumption that may not transfer cleanly                                             | ShopWired planning interpretation                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Products              | Every source variant, modifier, add-on, or personalized input can become the same type of option. | Determine whether the behavior belongs to variations, choices, extras, bundles, product fields, app behavior, or Custom Service. |
| Categories and brands | Source navigation can be recreated by importing category labels alone.                            | Rebuild discovery through category hierarchy, brand assignment, menus, filters, search, and SEO review.                          |
| Customers             | Every email or account record has the same operational meaning.                                   | Separate registered customers, guest buyer records, newsletter subscribers, trade customers, and custom fields.                  |
| Orders                | Historical order import automatically proves operational continuity.                              | Validate billing email links, totals, statuses, refunds, fulfilment information, notes, and customer-service readability.        |
| Checkout              | Source payment, delivery, tax, and discount behavior moves as data.                               | Treat live checkout as target configuration; migrate historical labels only where they support order context.                    |
| Storefront content    | Product and page content automatically preserves presentation.                                    | Review themes, menus, content pages, image handling, SEO fields, redirects, and landing-page expectations.                       |
| Integrations          | Connected app behavior is included in ordinary migration scope.                                   | Identify app-owned data, API dependencies, webhooks, external IDs, and Custom Service needs early.                               |

### Where ShopWired Often Creates Migration Value <a href="#where-shopwired-often-creates-migration-value" id="where-shopwired-often-creates-migration-value"></a>

ShopWired is often valuable for merchants that want a hosted platform with practical commerce depth and a more guided operating environment than a self-managed codebase. The platform can support stores that need structured catalog management, product purchase options, delivery and payment controls, B2B/trade functionality, and operational integrations without requiring the merchant to maintain hosting, security, and database infrastructure directly.

#### Hosted commerce management with operational depth <a href="#hosted-commerce-management-with-operational-depth" id="hosted-commerce-management-with-operational-depth"></a>

A strong ShopWired fit usually begins with the merchant’s operating preference. If the business wants a managed commerce environment rather than a self-hosted stack, ShopWired can reduce infrastructure responsibility while preserving practical control over products, orders, customers, checkout settings, taxes, content, SEO, apps, and integrations.

The migration implication is important: hosted convenience does not remove the need for migration planning. It changes where planning effort sits. Instead of asking how to preserve every source-side implementation, the project should ask how each source behavior should be represented in ShopWired’s supported structures.

#### Product catalogs that need more than a flat product model <a href="#product-catalogs-that-need-more-than-a-flat-product-model" id="product-catalogs-that-need-more-than-a-flat-product-model"></a>

ShopWired can suit stores with meaningful catalog structure: categories, brands, product options, variations, choices, extras, stock details, digital products, bundles, product filters, and SEO-sensitive product pages. This makes it stronger for merchants whose catalog cannot be reduced to a plain list of products.

For migration work, the key question is not simply whether products migrate. The key question is whether the customer can still choose, compare, filter, personalize, add to basket, and buy products in a way that matches the business model. A product sample set should include the most complex products, not only ordinary items.

#### Trade, B2B, and account-based selling <a href="#trade-b2b-and-account-based-selling" id="trade-b2b-and-account-based-selling"></a>

ShopWired can be attractive to merchants with trade or B2B requirements because the platform includes B2B-related areas such as trade customers, trade prices, trade settings, quotes, and account-based selling tools. These features make the platform relevant for merchants that need more than a retail-only checkout model.

Migration planning must still separate record migration from rule recreation. Customer records, billing details, and order history may migrate as data. Trade pricing bands, individual prices, approval flows, delivery/payment restrictions, and quote behavior may require target configuration, app setup, or Custom Service review depending on how the source store works.

#### Stores that need integration without full self-hosted control <a href="#stores-that-need-integration-without-full-self-hosted-control" id="stores-that-need-integration-without-full-self-hosted-control"></a>

ShopWired provides API access, webhooks, apps, and external service connections. That supports merchants that need accounting, fulfilment, stock, marketing, payment, delivery, multi-channel, or reporting workflows, but do not want to build every operational layer directly.

For migration, integration readiness should be checked separately from data transfer. A product, customer, or order can be moved into ShopWired while the operational connection that uses that record still needs API credentials, webhook setup, external identifiers, or app configuration after migration.

### Planning Areas That Need Early Review <a href="#planning-areas-that-need-early-review" id="planning-areas-that-need-early-review"></a>

ShopWired’s strength as a hosted commerce platform also creates boundaries. The source store must be evaluated against the platform’s supported structures before the project is treated as straightforward. The following areas deserve early attention because they often determine whether the migration is simple, configuration-heavy, or custom-scope dependent.

| Review area                               | Why it needs attention                                                                                                                                          | Typical migration decision                                                               |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Product options and variations            | ShopWired differentiates product option structures, and complex products may carry price, stock, image, weight, tax, or identifier meaning at the option level. | Map into supported structures, simplify where acceptable, or review custom behavior.     |
| Category, brand, and navigation structure | Discovery depends on more than imported product titles.                                                                                                         | Rebuild product relationships, menus, filters, and priority landing paths.               |
| Trade/B2B records                         | Trade behavior may mix customer data, pricing logic, customer access, delivery/payment rules, and quote workflows.                                              | Separate migrated records from target setup and Custom Service scope.                    |
| Orders and customer identity              | ShopWired assigns customer records by email and distinguishes registered and not registered records.                                                            | Validate order-to-customer linkage and historical readability.                           |
| Checkout operations                       | Delivery, payment, tax, discounts, and platform checkout settings are live target-store behavior.                                                               | Configure and test separately from historical record migration.                          |
| Content and SEO                           | Pages, blog content, images, menus, redirects, and SEO tags can affect traffic and conversion after launch.                                                     | Prioritize high-value content and URL samples before launch.                             |
| Apps and external systems                 | Operational data can live outside ordinary store entities.                                                                                                      | Classify app data, external IDs, and API/webhook dependencies before scope is finalized. |

### Service-Path Implications at a High Level <a href="#service-path-implications-at-a-high-level" id="service-path-implications-at-a-high-level"></a>

ShopWired does not require every migration to be custom. Many stores can use a structured migration path when products, categories, customers, orders, CMS Pages, and related data fit ordinary supported fields. The planning issue is knowing when the store remains ordinary and when the platform-specific details change the service path.

Standard Service is most suitable when source data maps cleanly into supported ShopWired structures and the merchant accepts that live checkout, delivery, tax, payment, theme, and app setup are target-side configuration work. Managed Service becomes more relevant when the merchant needs more guidance, validation support, or phased handling across complex records. Add-ons can support bounded migration requirements such as selective filtering, mapping, or supported configuration choices. Custom Service should be considered when unsupported app data, custom fields, external identifiers, bespoke product logic, or unusual B2B behavior need migration logic beyond ordinary supported scope.

The important point is that service-path planning should come from the ShopWired fit assessment. A store with complex products, trade pricing, and integration dependencies may still be a good ShopWired candidate, but it should not be planned as a simple direct transfer.

### Benchmark-Level ShopWired Readiness Signals <a href="#benchmark-level-shopwired-readiness-signals" id="benchmark-level-shopwired-readiness-signals"></a>

A ShopWired migration is ready for deeper execution planning when the merchant can answer the platform-specific questions below with evidence rather than assumptions.

| Readiness signal       | Strong evidence                                                                 | Weak evidence                                               |
| ---------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Product model clarity  | Complex source products have been sampled and mapped to ShopWired structures.   | Only simple products have been checked.                     |
| B2B/trade clarity      | Trade customers, pricing expectations, and quote behavior are classified.       | All customers are assumed to be ordinary accounts.          |
| Checkout separation    | Payment, delivery, tax, and discount setup are treated as target configuration. | Source checkout rules are assumed to migrate automatically. |
| Historical order value | Required order fields and customer links are defined.                           | Order migration is treated only as a totals archive.        |
| SEO continuity         | Priority URLs, redirects, metadata, and landing pages are identified.           | SEO review is postponed until after launch.                 |
| Integration ownership  | Apps, APIs, webhooks, and outside-system IDs are inventoried.                   | Integrations are treated as background details.             |

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired is a strong migration target when the merchant wants a hosted commerce platform with practical catalog, customer, order, checkout, B2B, content, app, and integration capabilities. Its value is strongest when the source store’s business model can be translated into supported ShopWired structures without assuming that legacy implementation details must be copied exactly.

The main planning work is to classify what should migrate as data, what should be configured in the target store, what belongs to apps or external systems, and what needs Custom Service review. Product options, trade/B2B rules, checkout behavior, customer identity, historical orders, SEO assets, and integrations should be reviewed early because they determine whether the migration can proceed through an ordinary path or requires deeper service planning.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is ShopWired a good target for stores with product variations and options?**

Yes, when source product choices can be represented through ShopWired-supported structures such as variations, choices, extras, bundles, or related product behavior. Complex configurators, dynamic pricing, and personalized purchase logic should be sampled before migration scope is confirmed.

**Does ShopWired work well for B2B or trade sellers?**

It can, especially when trade customers, pricing rules, quote expectations, customer visibility, and checkout rules are clear enough to configure or review. B2B data should not be treated as ordinary customer data without checking which rules are migrated records, target settings, app behavior, or custom scope.

**Can source checkout rules be migrated directly into ShopWired?**

Historical order values can preserve context, but live checkout behavior depends on ShopWired payment, delivery, tax, discount, and checkout configuration. Those settings should be configured and tested separately from data migration.

**When does a ShopWired migration need Custom Service review?**

Custom Service review is usually needed when the source store depends on unsupported app data, custom fields with operational meaning, external identifiers, bespoke product logic, advanced B2B rules, or integration-owned records that do not fit ordinary supported migration scope.

**What should be validated first in a ShopWired migration?**

The first validation samples should include complex products, customer and trade customer cases, representative historical orders, high-value categories or brands, checkout-related assumptions, SEO-sensitive pages, and any app or integration dependencies that affect operations.
