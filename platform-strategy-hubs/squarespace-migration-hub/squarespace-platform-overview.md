# Squarespace Platform Overview

Squarespace is a hosted content-first website and commerce environment where the target store is shaped by both site presentation and commerce configuration. A migration into Squarespace is therefore not only a transfer of products, customers, and orders. The target result can also depend on Store Pages, product pages, templates, page sections, Blog Posts, media, categories, tags, URLs, SEO settings, redirects, domains, checkout settings, payment and shipping setup, tax configuration, discount behavior, inventory, fulfillment, subscriptions or payment plans, contacts, and integration choices.

For migration planning, Squarespace should be treated as a managed website-and-commerce Target Platform. It can be a strong destination for merchants that want a polished hosted site, content-led selling, relatively simple commerce operations, curated storefront presentation, and less technical platform ownership. It also requires careful expectation-setting when the source store depends on complex catalog architecture, advanced B2B workflows, unusual checkout rules, deep app ecosystems, custom database behavior, strict theme parity, or integration-owned records that do not have a direct Squarespace equivalent.

The most important planning distinction is simple: migrated data, Squarespace site setup, commerce configuration, design implementation, and integration work are related, but they are not the same task. A clean Squarespace migration plan defines which records can move through the Migration Service, which target settings must be configured inside Squarespace, which pages or design areas need rebuild work, and which custom or unsupported requirements require Add-ons, Tailored Add-ons, Custom Add-ons, accepted exclusions, or Custom Service review.

### Squarespace as a Content-First Commerce Target Platform <a href="#squarespace-as-a-content-first-commerce-target-platform" id="squarespace-as-a-content-first-commerce-target-platform"></a>

Squarespace combines hosted website building with commerce features. The same target environment can include site pages, Store Pages, product listings, product detail pages, checkout, orders, payment settings, shipping settings, tax settings, discounts, customer/contact records, Blog Posts, media, SEO controls, redirects, domains, and third-party integrations. That combination is what makes Squarespace different from a standalone cart migration.

| Platform layer             | What it means in Squarespace                                                                                                                   | Migration planning value                                                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Hosted site foundation     | The target website is managed inside Squarespace rather than a merchant-controlled server, plugin stack, or source-code repository.            | Custom source behavior must be translated into Squarespace-supported setup, integrations, rebuild work, or Custom Service scope. |
| Content-first presentation | Site pages, templates, sections, images, navigation, product display, mobile presentation, and visual layout are central to the target result. | Source design parity should not be assumed as part of data migration.                                                            |
| Commerce layer             | Squarespace commerce supports products, Store Pages, inventory, checkout, orders, payments, shipping, tax, discounts, and fulfillment context. | Product and order migration should be reviewed together with target commerce configuration.                                      |
| Content and SEO layer      | Blog Posts, CMS Pages, media, slugs, redirects, metadata, domains, and internal links can affect launch continuity.                            | SEO-sensitive migrations need content and URL planning before Full Migration.                                                    |
| Integration layer          | Commerce APIs, third-party systems, sales channels, analytics, marketing tools, and fulfillment systems may affect operations.                 | Integration identifiers and unsupported records should be discovered before scope is confirmed.                                  |

A Squarespace migration succeeds when these layers are planned as one target operating environment, not when record counts alone appear complete.

### What Makes Squarespace Different During Migration <a href="#what-makes-squarespace-different-during-migration" id="what-makes-squarespace-different-during-migration"></a>

Squarespace changes where store behavior is controlled. On many Source Platforms, product logic, checkout behavior, templates, content structures, customer records, SEO rules, and integrations may live in database tables, themes, plugins, custom modules, or direct code. In Squarespace, those behaviors usually become platform settings, design decisions, supported commerce records, Store Page configuration, integration setup, or custom work outside the standard data-transfer path.

| Source-store expectation                 | Squarespace interpretation                                                                                                                      | What should be checked early                                                                                                                              |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products move as database records        | Products must make sense inside Squarespace product and Store Page structures.                                                                  | Product types, variants, SKUs, prices, images, categories, tags, visibility, inventory, and product-page display.                                         |
| Categories map exactly to old navigation | Product discovery may depend on Store Pages, navigation, categories, tags, summary blocks, pages, and site layout.                              | Category/tag mapping, shopper paths, landing pages, menu structure, and priority collection pages.                                                        |
| Checkout behavior follows order history  | Historical order records do not configure live checkout, payment, shipping, tax, discounts, or fulfillment rules.                               | Target checkout readiness, payment providers, shipping settings, tax setup, discount rules, fulfillment settings, and subscription/payment-plan behavior. |
| Customers are one simple account type    | Customer and contact meaning can vary by commerce history, email records, newsletter or marketing context, subscriptions, and integrations.     | Which customer/contact meanings must migrate and which belong to target configuration or external tools.                                                  |
| Source design moves with data            | Squarespace storefront presentation depends on the target site, template, page sections, Store Pages, content blocks, media, and styling.       | Which design expectations belong to site implementation rather than Migration Service scope.                                                              |
| Custom code transfers directly           | Squarespace is hosted, so custom behavior usually requires supported features, external integrations, manual rebuild, or Custom Service review. | Custom checkout rules, product configurators, membership flows, B2B logic, scripts, and external-system dependencies.                                     |

This distinction matters because Squarespace can preserve many business records while still requiring target configuration before launch. Migration quality should be judged by whether Squarespace can operate correctly after migration, not only by whether records appear in the dashboard.

### Core Commerce Areas in a Squarespace Migration <a href="#core-commerce-areas-in-a-squarespace-migration" id="core-commerce-areas-in-a-squarespace-migration"></a>

Squarespace commerce planning should start with the records and behaviors that shoppers and store operators use every day. Product data, Store Pages, checkout behavior, order history, inventory, customer context, and fulfillment each need a different type of review.

| Commerce area             | Squarespace migration focus                                                                                                                                      | Planning implication                                                                                               |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Products                  | Product names, descriptions, prices, SKUs, product types, variants, images, visibility, categories, tags, inventory, and SEO values.                             | Product samples should include both ordinary products and products with operationally important variants or media. |
| Product types             | Physical products, service products, gift cards, digital downloads, and subscription or payment-plan contexts may behave differently.                            | Source product models should be grouped by how Squarespace will sell or display them.                              |
| Store Pages and discovery | Store Pages, product detail pages, categories, tags, navigation, summary blocks, filters, and landing pages shape product discovery.                             | A product can migrate correctly but still be hard to find if storefront paths are not rebuilt.                     |
| Cart and checkout         | Checkout fields, discounts, taxes, payment, shipping, inventory behavior, fulfillment, and payment-provider setup.                                               | Live checkout must be configured and tested separately from historical order migration.                            |
| Orders                    | Purchased items, totals, discounts, taxes, shipping, payment references, fulfillment status, transactions, refunds, notes, and customer context where supported. | Historical readability matters, but it does not prove that future transactions are configured.                     |
| Customers and contacts    | Customer records, contacts, email identities, marketing context, account expectations, subscriptions, and integration identifiers.                               | The target meaning of each customer-related record should be separated before migration.                           |
| Inventory and fulfillment | Variant-level stock, inventory adjustment, tracking, fulfillment status, shipping tools, and external fulfillment systems.                                       | Inventory should be validated in both migrated records and target operating workflow.                              |

The overview-level rule is that Squarespace commerce is both data and configuration. Product and order history migration should be paired with a target readiness plan for checkout, payment, shipping, tax, fulfillment, product display, and storefront discovery.

### Site Content, Design, and SEO in Squarespace <a href="#site-content-design-and-seo-in-squarespace" id="site-content-design-and-seo-in-squarespace"></a>

Squarespace is often selected because the website experience matters alongside commerce. That makes content, design, media, and SEO part of the migration conversation from the beginning. However, those areas should not be treated as if they move in the same way as products or orders.

| Site area                   | What can affect migration quality                                                                                         | Practical planning point                                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| CMS Pages                   | Informational pages, landing pages, service pages, policy pages, portfolio-style content, and structured pages.           | Decide which pages should migrate, which should be rebuilt, and which should be retired.                               |
| Blog Posts                  | Blog content, authorship, dates, categories, tags, media, excerpts, internal links, and SEO metadata.                     | Blog continuity should be sampled separately from product migration.                                                   |
| Media                       | Product images, page images, galleries, downloadable files, alt text, and embedded media references.                      | Media should be checked in both product and content contexts.                                                          |
| Site design                 | Templates, page sections, mobile presentation, product layouts, Store Pages, menus, headers, footers, and content blocks. | Source design should be converted into Squarespace implementation expectations, not assumed as a direct data transfer. |
| URLs and SEO                | Product slugs, page slugs, redirects, metadata, canonical expectations, internal links, and domain launch timing.         | SEO-sensitive stores need URL and redirect planning before launch.                                                     |
| Domains and launch controls | Domain connection, SSL, DNS, site visibility, password settings, and launch timing.                                       | These are target-side launch tasks, not proof that migrated records are complete.                                      |

A Squarespace project should define content and SEO priorities early. For many merchants, product data is only one part of the platform move; page continuity, brand presentation, media quality, and URL handling can be equally important.

### APIs, Integrations, and Unsupported Data <a href="#apis-integrations-and-unsupported-data" id="apis-integrations-and-unsupported-data"></a>

Squarespace provides commerce APIs and integration options, but it is still a managed hosted platform. Source stores that rely on custom database tables, plugins, marketplace extensions, private checkout workflows, or specialized external systems may need more than a standard record migration.

| Requirement area             | Squarespace planning question                                                                                               | Likely handling                                                                                              |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Commerce APIs                | Are products, orders, inventory, transactions, profiles, or contacts expected to sync with another system?                  | Confirm API-supported objects, identifiers, and external-system expectations before scope is finalized.      |
| Third-party channels         | Did the source store rely on marketplaces, POS, fulfillment tools, email marketing, accounting, CRM, or analytics systems?  | Identify which records belong to migration and which require target-side integration setup.                  |
| Custom catalog logic         | Does the source store use bundles, configurable products, subscriptions, memberships, courses, rentals, or B2B price lists? | Review whether supported Squarespace structures, Add-ons, accepted exclusions, or Custom Service are needed. |
| Checkout customization       | Are custom checkout fields, conditional rules, shipping restrictions, tax exceptions, or payment behavior required?         | Treat these as target configuration or custom review, not automatic order-history migration.                 |
| Design or content automation | Did source templates, dynamic content, scripts, or integrations generate storefront behavior?                               | Rebuild or integration planning may be needed outside standard data transfer.                                |

Add-ons should be chosen for specific migration needs. They are not a substitute for Custom Service, custom development, or target-site build work. Custom Service should be reviewed when the required Squarespace result depends on unsupported objects, complex transformations, integration-owned records, or business rules that cannot be handled through a standard migration path.

### Squarespace Migration Planning Boundaries <a href="#squarespace-migration-planning-boundaries" id="squarespace-migration-planning-boundaries"></a>

A Squarespace platform overview should help merchants understand boundaries before they choose the target. The biggest planning mistakes usually happen when data movement, store setup, design implementation, and operational launch work are treated as one automatic step.

| Boundary              | Included in migration planning                                                                                                   | Not automatically included                                                           |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Data migration        | Products, customers/contacts where supported, orders, inventory-related data, CMS Pages, Blog Posts, and other selected records. | Recreating every source behavior exactly as it worked before.                        |
| Store setup           | Target payment, shipping, tax, discounts, checkout, fulfillment, inventory, and store settings.                                  | Proof that historical order records alone configure future checkout.                 |
| Design implementation | Store Pages, page sections, product display, navigation, media placement, and mobile presentation planning.                      | Direct transfer of source themes, templates, plugins, scripts, or custom code.       |
| SEO continuity        | Priority URL review, metadata review, redirects, internal links, media references, and domain-launch coordination.               | Guarantee that every source URL or SEO behavior has a direct Squarespace equivalent. |
| Integrations          | External-system identifiers, API expectations, fulfillment references, and third-party workflow review.                          | Automatic recreation of external systems or their business logic.                    |

This boundary-setting protects the migration from unrealistic expectations. It also helps merchants decide whether Standard Service is enough, whether Managed Service is appropriate, whether Add-ons are needed, or whether Custom Service review should happen before launch planning.

### What Merchants Should Understand Before Choosing Squarespace <a href="#what-merchants-should-understand-before-choosing-squarespace" id="what-merchants-should-understand-before-choosing-squarespace"></a>

Squarespace can be a good target when the merchant wants a hosted website, polished presentation, content and commerce in one environment, and a simpler operating model than heavily customized open-source or enterprise platforms. It is less suitable when the source business depends on highly specialized commerce architecture that must be reproduced exactly.

| Planning question                                                                                    | Why it matters                                                                               |
| ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Is the target priority a polished hosted site with commerce, or a highly customized commerce engine? | Squarespace is strongest when content presentation and practical commerce are the core goal. |
| Can the source catalog fit Squarespace-supported product structures?                                 | Complex product models may require review, simplification, Add-ons, or Custom Service.       |
| Are historical orders needed for reference, reporting, customer service, or integrations?            | The expected use of order history affects validation and acceptance criteria.                |
| Which pages, Blog Posts, images, and URLs are business-critical?                                     | Content and SEO planning can matter as much as product migration.                            |
| Which checkout, fulfillment, payment, tax, or shipping behaviors must be rebuilt in the target?      | These are target operating requirements, not only migrated records.                          |
| Which integrations or external systems must continue after launch?                                   | API and third-party workflow planning can change scope and timeline.                         |
| Does the project require only data migration, or also target-site implementation?                    | Squarespace migrations often combine commerce data with site/content/design decisions.       |

These questions should be answered early because they influence Demo Migration sample selection, launch expectations, Add-ons, Custom Service review, and the overall migration path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace can be a strong Target Platform for merchants that want a hosted, content-first website with integrated commerce, practical product management, polished page presentation, checkout, orders, payment and shipping setup, SEO controls, Blog Posts, media, and selected integrations. It is especially useful when the target project values a combined website and storefront experience rather than a purely standalone cart architecture.

A successful Squarespace migration depends on clear separation between migrated data, target commerce setup, site/content implementation, design decisions, SEO continuity, and integration requirements. The best early proof comes from a focused Demo Migration that includes representative products, variant cases, Store Pages, customers or contacts, varied orders, CMS Pages, Blog Posts, SEO-sensitive URLs, and any records or external references that could affect day-to-day operations.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Squarespace a hosted or self-hosted Target Platform?**

Squarespace is a hosted Target Platform. Merchants do not manage the underlying server, database, plugin stack, or source code in the same way they would with a self-hosted platform, so migration planning should focus on Squarespace-supported records, target configuration, site setup, integrations, and Custom Service review where needed.

**Is Squarespace the same as a standard shopping cart platform?**

No. Squarespace combines site building and commerce. Products, Store Pages, orders, customers, contacts, CMS Pages, Blog Posts, media, SEO, redirects, domains, templates, and integrations can all affect the target result. That makes Squarespace migration broader than a simple cart record transfer.

**Can product variants migrate cleanly to Squarespace?**

Many variant structures can be planned for Squarespace, but complex products should be sampled before Full Migration. Variant-level SKU, price, stock, image, product type, fulfillment behavior, and storefront display should be reviewed because these details affect both shopper experience and store management.

**Will the source store design migrate directly into Squarespace?**

A source design should not be treated as a direct theme-code migration into Squarespace. The target storefront depends on the Squarespace site, template, page sections, Store Pages, navigation, content blocks, media placement, and mobile presentation. Design continuity should be planned separately from data migration.

**What should be checked before committing to Squarespace migration?**

Review complex products, variants, product types, customer/contact meaning, order-history expectations, checkout configuration, Store Pages, CMS Pages, Blog Posts, priority URLs, SEO metadata, redirects, domain launch timing, integrations, subscriptions or payment-plan expectations, and unsupported custom behavior. These areas show whether the Squarespace target can support the required operating model.
