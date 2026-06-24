# Wix Platform Overview

Wix is a hosted site-builder and commerce environment where the target store is shaped by both website configuration and commerce configuration. A migration into Wix is therefore not only a transfer of products, customers, and orders. The target result can also depend on Wix Stores, Wix eCommerce services, site pages, design sections, collections, cart and checkout behavior, payment and shipping settings, tax configuration, discounts, members, contacts, apps, CMS content, Blog Posts, SEO settings, redirects, and integration choices.

For migration planning, Wix should be treated as a managed website-and-commerce Target Platform. It can be a strong destination for merchants that want a hosted storefront, easier site ownership, practical product selling, content-led commerce, apps, and business tools in one environment. It also requires careful expectation-setting when the source store depends on custom code, unusual checkout logic, advanced product configuration, app-owned records, strict design parity, specialized B2B behavior, or external-system workflows.

The most important planning distinction is simple: migrated data, Wix site setup, app configuration, and storefront implementation are related, but they are not the same task. A clean Wix migration plan defines which records can move through the Migration Service, which target settings must be configured in Wix, which pages or design areas need rebuild work, and which app or integration requirements require Add-ons, Tailored Add-ons, Custom Add-ons, or Custom Service review.

### Wix as a Site-Builder Commerce Target Platform <a href="#wix-as-a-site-builder-commerce-target-platform" id="wix-as-a-site-builder-commerce-target-platform"></a>

Wix combines hosted site building with commerce services. The same target environment can include storefront pages, product pages, collections, cart, checkout, orders, payment settings, shipping and fulfillment settings, discounts, business apps, members, contacts, Blog Posts, CMS Pages, media, SEO controls, and integrations. That combination is what makes Wix different from a standalone cart migration.

| Platform layer                  | What it means in Wix                                                                                                                                   | Migration planning value                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| Hosted site foundation          | The target website is managed inside Wix rather than a merchant-controlled server or source-code repository.                                           | Custom source behavior must be translated into Wix-supported setup, apps, Velo/API work, or Custom Service scope. |
| Commerce layer                  | Wix Stores and Wix eCommerce services support catalog, cart, checkout, orders, payments, discounts, tax, fulfillment, and related commerce operations. | Product and order migration should be reviewed together with target checkout and store setup.                     |
| Site-builder layer              | Layout, product pages, collection pages, menus, landing pages, mobile display, and content sections depend on Wix site design.                         | Source theme parity should not be assumed as part of data migration.                                              |
| Business apps                   | Apps can support bookings, events, restaurants, memberships, forms, loyalty, marketing, reviews, and other workflows.                                  | App-owned records may need separate review, accepted exclusions, Add-ons, or Custom Service.                      |
| Developer and integration layer | Velo, APIs, service plugins, custom catalogs, external payment services, shipping integrations, and connected systems may affect business behavior.    | Integration identifiers and custom workflow requirements should be discovered before scope is confirmed.          |

A Wix migration succeeds when these layers are planned as one target operating environment, not when record counts alone appear complete.

### What Makes Wix Different During Migration <a href="#what-makes-wix-different-during-migration" id="what-makes-wix-different-during-migration"></a>

Wix changes where store behavior is controlled. On some Source Platforms, product logic, checkout behavior, templates, content structures, customer accounts, SEO rules, and integrations may exist in database tables, themes, plugins, custom modules, or direct code. In Wix, those behaviors usually become platform settings, app configuration, site-editor decisions, supported Wix data structures, APIs, service plugins, or custom development choices.

| Source-store expectation                 | Wix interpretation                                                                                                                        | What should be checked early                                                                                       |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Products move as database records        | Products must make sense inside Wix Stores or the relevant Wix catalog context.                                                           | Product types, options, choices, variants, modifiers, SKU values, media, inventory, price, and storefront display. |
| Categories map exactly to old navigation | Product discovery may rely on collections, pages, galleries, filters, menus, and site sections.                                           | Category/collection mapping, shopper paths, filter behavior, and priority landing pages.                           |
| Checkout logic follows order history     | Historical order records do not configure live cart, checkout, payment, tax, shipping, fulfillment, or custom validation.                 | Target checkout readiness, payment providers, shipping rules, tax setup, pickup/delivery, and service plugins.     |
| Customers are one simple record type     | Commerce customers may intersect with contacts, members, subscribers, app records, consent, CRM data, and marketing lists.                | Which customer meanings must migrate, which are target configuration, and which are app-owned.                     |
| Source design moves with data            | Wix storefront presentation depends on the target site, editor, template, widgets, apps, and content rebuild.                             | Which design expectations belong to site implementation rather than Migration Service scope.                       |
| Custom code transfers directly           | Wix is hosted, so custom behavior must be rebuilt or represented through supported Wix capabilities, Velo, APIs, apps, or Custom Service. | Custom functions, scripts, product configurators, checkout rules, and external-system dependencies.                |

This distinction matters because Wix can preserve many business records while still requiring target configuration before launch. Migration quality should be judged by whether Wix can operate correctly after migration, not only by whether records appear in the dashboard.

### Core Commerce Areas in a Wix Migration <a href="#core-commerce-areas-in-a-wix-migration" id="core-commerce-areas-in-a-wix-migration"></a>

Wix commerce planning should start with the records and behaviors that shoppers and store operators use every day. Product data, cart and checkout behavior, order history, customer identity, and fulfillment context each need a different type of review.

| Commerce area                    | Wix migration focus                                                                                                                               | Planning implication                                                                            |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Products                         | Product names, descriptions, prices, SKUs, options, variants, modifiers, media, inventory, visibility, and SEO values.                            | Product samples should include both simple and operationally difficult products.                |
| Collections and discovery        | Collections, category-like structures, filters, sorting, menus, galleries, widgets, and product landing pages.                                    | A product can migrate correctly but still be hard to find if discovery paths are not rebuilt.   |
| Cart and checkout                | Cart contents, checkout fields, discounts, tax, payment, shipping, validation, and custom checkout behavior.                                      | Live checkout must be configured and tested separately from historical order migration.         |
| Orders                           | Purchased items, totals, discounts, taxes, shipping, payment labels, fulfillment, refunds, tracking, notes, and customer context where supported. | Historical readability matters, but it does not prove that future transactions are configured.  |
| Customers, contacts, and members | Customer records, site members, contacts, email consent, account behavior, CRM context, and app-related customer data.                            | The target meaning of each customer-related record should be separated before migration.        |
| Discounts and promotions         | Coupons, discounts, promotion logic, and campaign behavior.                                                                                       | Simple discount records may differ from complex source promotion engines or app-managed offers. |
| Fulfillment and delivery         | Shipping rates, pickup, delivery, fulfillment services, tracking, and external shipping tools.                                                    | Configuration and integrations often need target-side setup, not only migrated records.         |

The overview-level rule is that Wix commerce is both data and configuration. Product and order history migration should be paired with a target readiness plan for checkout, shipping, tax, payment, fulfillment, and storefront discovery.

### Site Content, Design, and SEO in Wix <a href="#site-content-design-and-seo-in-wix" id="site-content-design-and-seo-in-wix"></a>

Wix is often selected because the website experience matters alongside commerce. That makes content, design, media, and SEO part of the migration conversation from the beginning. However, those areas should not be treated as if they move in the same way as products or orders.

| Site area    | What can affect migration quality                                                                                 | Practical planning point                                                                                       |
| ------------ | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| CMS Pages    | Informational pages, landing pages, service pages, policy pages, and structured content.                          | Decide which pages should migrate, which should be rebuilt, and which should be retired.                       |
| Blog Posts   | Blog content, authorship, dates, categories, tags, media, internal links, and SEO metadata.                       | Blog continuity should be sampled separately from product migration.                                           |
| Media        | Product images, page images, galleries, embedded files, alt text, and image references.                           | Media should be checked in both product and content contexts.                                                  |
| Site design  | Templates, sections, editor layout, mobile presentation, product pages, collection pages, menus, and widgets.     | Source design should be converted into Wix implementation expectations, not assumed as a direct data transfer. |
| URLs and SEO | Product slugs, page slugs, redirects, metadata, canonical behavior, structured data, internal links, and domains. | High-value URLs should be inventoried before Demo Migration and launch planning.                               |

For merchants with search traffic, content-heavy sites, or brand-sensitive storefronts, URL and content review should begin before Full Migration. Wix can be a strong site-commerce environment, but launch quality depends on planned site structure, not only migrated commerce records.

### Apps, Service Plugins, Velo, and External Systems <a href="#apps-service-plugins-velo-and-external-systems" id="apps-service-plugins-velo-and-external-systems"></a>

Many Wix stores rely on more than Wix Stores alone. Apps, Velo, APIs, service plugins, and external systems can shape how the site sells, collects information, validates checkout, charges buyers, fulfills orders, or syncs business records.

| Dependency type                        | Examples                                                                                                                             | Migration implication                                                                        |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| Wix apps and business tools            | Forms, bookings, events, restaurants, memberships, loyalty, reviews, marketing, pricing plans, donations, and other app experiences. | App-owned records may not behave like standard product, customer, or order records.          |
| Service plugins                        | Custom fees, shipping rates, checkout and cart validation, external payment services, and custom catalog integrations.               | Functional behavior should be scoped separately from historical data migration.              |
| Velo/API work                          | Custom logic, custom flows, integrations, automations, and specialized site behavior.                                                | Custom behavior may require Custom Service or target implementation work.                    |
| External systems                       | ERP, PIM, CRM, accounting, WMS, fulfillment, marketplace, marketing, analytics, and middleware platforms.                            | External IDs and workflow dependencies should be identified before migration acceptance.     |
| Custom catalogs or specialized selling | Services, custom items, bookings, project work, bundles, or non-standard selling models.                                             | Product-like records may need target interpretation rather than direct one-to-one migration. |

This is where Wix planning often moves beyond standard migration assumptions. When apps or external systems own business meaning, the migration plan should define whether the requirement belongs to Standard Service, an Add-on, a Tailored Add-on, a Custom Add-on, Custom Service, or separate target-site implementation.

### Wix Migration Planning Boundaries <a href="#wix-migration-planning-boundaries" id="wix-migration-planning-boundaries"></a>

A clear Wix overview should prevent one common misunderstanding: not every desired target-store behavior is a migration deliverable. Some work belongs to data migration, some belongs to Wix configuration, some belongs to site design, and some belongs to app or integration implementation.

| Work area                  | Usually migration-related                                                                                       | Usually target setup or implementation                                                                           |
| -------------------------- | --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Product records            | Product data, variants/options where supported, product images, prices, inventory, collections, and SEO values. | Product page layout, storefront sections, merchandising widgets, and manual collection presentation.             |
| Customer and order records | Customer data and historical order information where supported.                                                 | Member-area behavior, marketing automation, saved payment behavior, loyalty, or app-controlled account flows.    |
| Content records            | CMS Pages, Blog Posts, media, and selected metadata where in scope.                                             | Visual page rebuild, layout refinement, dynamic-page implementation, and unsupported source design parity.       |
| Checkout and fulfillment   | Historical labels and selected order context.                                                                   | Live checkout, payment providers, shipping rules, tax configuration, fulfillment workflows, and cart validation. |
| Custom or app data         | Records that can be identified, mapped, and migrated through supported scope.                                   | App reinstall/configuration, Velo code, service plugin behavior, and external-system workflow rebuild.           |

This boundary protects project quality. It helps merchants understand why a Demo Migration should test both data output and target operating assumptions.

### What Merchants Should Understand Before Choosing Wix <a href="#what-merchants-should-understand-before-choosing-wix" id="what-merchants-should-understand-before-choosing-wix"></a>

Before choosing Wix as the Target Platform, merchants should understand the platform through operational questions rather than record counts alone.

| Question                                                                            | Why it matters                                                                                                                      |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Can the core product model be represented in Wix?                                   | Options, variants, modifiers, inventory, media, SKUs, and custom product inputs can affect shopper experience and store operations. |
| Can shoppers find products after migration?                                         | Collections, filters, menus, product galleries, landing pages, and site sections determine discoverability.                         |
| Are customer, contact, member, and subscriber meanings separated?                   | Treating all customer-related records as one object can hide CRM, membership, consent, and app-data requirements.                   |
| Is historical order readability enough, or is live checkout behavior also required? | Order migration and target checkout setup solve different problems.                                                                 |
| Which apps or integrations own business-critical behavior?                          | Apps, service plugins, APIs, Velo code, and external systems can change scope and acceptance criteria.                              |
| Which URLs and pages must retain search value?                                      | SEO-sensitive migrations need URL, redirect, metadata, and content review before launch.                                            |
| Does the project require only data migration, or also target-site implementation?   | Wix often combines commerce migration with storefront/content/design decisions.                                                     |

These questions should be answered early because they influence sample selection, timeline expectations, Add-ons, Custom Service review, and launch readiness.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix can be a strong Target Platform for merchants that want a hosted site-and-commerce environment with practical store management, content tools, app flexibility, checkout, orders, payment and shipping setup, SEO controls, and business-service extensibility. It is especially useful when the target project values a combined website and commerce experience rather than a purely standalone cart.

A successful Wix migration depends on clear separation between migrated data, Wix target setup, site/content implementation, and app or integration requirements. The best early proof comes from a focused Demo Migration that includes complex products, important collections, customer/contact/member examples, varied orders, CMS Pages, Blog Posts, SEO-sensitive URLs, and any app or external-system records that could affect day-to-day operations.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Wix a hosted or self-hosted Target Platform?**

Wix is a hosted Target Platform. Merchants do not manage the underlying server or database in the same way they would with a self-hosted platform, so migration planning should focus on Wix-supported structures, target configuration, apps, service plugins, Velo/API work, and integrations.

**Is Wix the same as a standard shopping cart platform?**

No. Wix combines site building and commerce services. Products, checkout, orders, customers, CMS Pages, Blog Posts, apps, media, SEO, members, contacts, and storefront design can all affect the target result. That makes Wix migration broader than a simple cart record transfer.

**Can product variants migrate cleanly to Wix?**

Many product-option and variant structures can be planned for Wix, but complex products should be sampled before Full Migration. Variant-level price, stock, SKU, media, weight, modifiers, and custom inputs should be reviewed because these details affect both shopper experience and store management.

**Will the source store design migrate directly into Wix?**

A source design should not be treated as a direct theme-code migration into Wix. The target storefront depends on the Wix site, editor setup, templates, page design, product pages, collection pages, widgets, mobile presentation, apps, and content work. Design continuity should be planned separately from data migration.

**What should be checked before committing to Wix migration?**

Review complex products, customer/contact/member meaning, order-history expectations, checkout configuration, important collections, CMS Pages, Blog Posts, priority URLs, SEO metadata, apps, service plugins, Velo/API dependencies, and external-system identifiers. These areas show whether the Wix target can support the required operating model.
