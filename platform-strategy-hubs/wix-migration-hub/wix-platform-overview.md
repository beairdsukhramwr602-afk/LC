# Wix Platform Overview

Wix should be planned as a hosted site-builder commerce environment, not merely as a destination for product, customer, and order records. A migration into Wix can involve Wix Stores, product collections, product options, variants, inventory, orders, checkout setup, payment and shipping settings, discounts, contacts, members, CMS Pages, Blog Posts, media, SEO, redirects, apps, and custom development choices. These areas are connected in the target store, but they do not all move through migration in the same way.

The central planning distinction is that migrated data, Wix site setup, app configuration, and storefront implementation are related but separate responsibilities. Products and orders may be transferred into Wix, while page layout, live checkout behavior, payment providers, domain connection, site navigation, app workflows, and custom site behavior still need target-side configuration or separate implementation. A clean Wix migration plan identifies those boundaries before Demo Migration, not after launch pressure begins.

### Wix as a Hosted Site-Builder Commerce Platform <a href="#wix-as-a-hosted-site-builder-commerce-platform" id="wix-as-a-hosted-site-builder-commerce-platform"></a>

Wix combines site building and commerce in one hosted environment. That makes it different from a standalone cart, a self-hosted open-source platform, or a commerce backend attached to a separately managed content system. The target store is shaped by both commerce data and website experience: how products appear, how collections support discovery, how checkout is configured, how contacts and members are handled, and how site content, URLs, and apps support the business.

For migration planning, this means Wix should be evaluated as a site-commerce operating environment. The merchant is not only asking whether Products, Customers, Orders, CMS Pages, Blog Posts, Coupons, Reviews, or media can be moved. The merchant is also deciding whether Wix can represent the future operating model through supported store records, site pages, apps, CMS data, checkout settings, and integration choices.

| Wix layer                       | Migration significance                                                                                                                                                              |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Hosted site foundation          | Server, hosting, editor, and core site experience are managed by Wix, so source-code or server-level behavior must be translated into Wix-supported setup or custom implementation. |
| Wix Stores catalog              | Products, collections, options, choices, variants, media, inventory, and product visibility need Wix-specific interpretation.                                                       |
| Site-builder experience         | Pages, menus, sections, product pages, collection pages, mobile presentation, and site design are implementation concerns, not direct data transfer assumptions.                    |
| Business and commerce apps      | Bookings, events, restaurants, forms, pricing plans, loyalty, marketing, and other apps may own records outside ordinary store migration scope.                                     |
| Developer and integration layer | Wix APIs, CMS data, external databases, custom code, service plugins, and connected systems may affect what needs Add-ons or Custom Service review.                                 |
| Site URLs and domains           | Published URLs, primary domains, secondary URLs, multilingual versions, redirects, and SEO-sensitive paths need launch planning beyond record import.                               |

The most important result is practical: Wix migration quality should be measured by whether the migrated store can operate as a Wix site-commerce environment, not by whether a spreadsheet-like list of records appears complete.

### What Makes Wix Different During Migration <a href="#what-makes-wix-different-during-migration" id="what-makes-wix-different-during-migration"></a>

Wix changes where store behavior lives. On some Source Platforms, catalog rules, checkout logic, templates, customer accounts, content structures, SEO settings, and integration logic may exist in code, database tables, plugins, modules, or direct file access. In Wix, much of that behavior becomes platform configuration, editor-managed design, supported Wix commerce records, apps, CMS data, APIs, or custom implementation work.

That difference affects expectations. A product category from the source store may become a Wix collection, a menu path, a gallery section, a filterable product group, a page, or a redirect decision. A source customer account may need to be evaluated as a customer, contact, site member, subscriber, CRM record, or app-managed identity. A source checkout rule may become Wix checkout configuration, a service-plugin requirement, an app dependency, a Custom Service item, or an accepted exclusion.

| Source-store assumption                     | Wix planning interpretation                                                                                                               | Early review focus                                                                                                   |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Products move as simple catalog records.    | Wix products may depend on collections, options, choices, variants, media, inventory, visibility, and page display.                       | Product samples should include simple items, option-heavy items, inventory-sensitive items, and image-rich products. |
| Categories map directly to navigation.      | Wix discovery can involve collections, pages, menus, filters, product galleries, and SEO landing paths.                                   | Separate catalog grouping from storefront navigation and high-value URLs.                                            |
| Historical orders prove checkout readiness. | Order history is different from live payment, shipping, tax, fulfillment, and checkout setup.                                             | Validate historical order readability and test live Wix setup separately.                                            |
| Customers are one record type.              | Customers may intersect with contacts, members, CRM records, subscribers, app records, and consent.                                       | Classify the future use of buyer identity before migration scope is accepted.                                        |
| Design moves with store data.               | Wix presentation depends on target-site implementation inside Wix.                                                                        | Treat design parity, page layout, and mobile display as site implementation work.                                    |
| Custom code transfers directly.             | Wix is hosted, so custom behavior must be represented through supported Wix capabilities, apps, APIs, CMS data, or custom implementation. | Identify scripts, custom fields, external IDs, product configurators, and checkout logic early.                      |

A strong Wix plan does not promise one-to-one behavior transfer. It explains which parts of the source store should become migrated data, which parts should become Wix setup, and which parts require app or custom evaluation.

### Core Commerce Areas in a Wix Migration <a href="#core-commerce-areas-in-a-wix-migration" id="core-commerce-areas-in-a-wix-migration"></a>

Wix commerce planning should begin with the areas that store operators and shoppers depend on every day: catalog structure, product discovery, checkout behavior, order history, buyer identity, and fulfillment context. Each area needs a different review path.

Products should be tested for selling meaning, not only for presence. A product with options and variants may carry price, SKU, weight, inventory, or media differences that matter in Wix. Collections should be reviewed for both catalog organization and storefront discovery. Orders should be reviewed as historical records, not as proof that future Wix checkout is configured. Customer data should be reviewed according to buyer lookup, member access, CRM continuity, marketing consent, or app dependency.

| Commerce area                    | Wix migration question                                                                                                                     | Planning implication                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Products                         | Do product names, descriptions, prices, SKUs, media, visibility, options, choices, variants, and inventory make sense in Wix?              | Demo Migration samples must include products that expose option and variant behavior.                         |
| Collections and discovery        | Do collections support the intended product grouping, navigation, filters, landing paths, and customer browsing experience?                | Category migration should not be approved until discovery paths are reviewed.                                 |
| Cart and checkout                | Which behavior is migrated history, and which behavior must be configured in Wix?                                                          | Payment, shipping, tax, pickup, delivery, discount, and checkout settings need target-side validation.        |
| Orders                           | Are historical orders readable with line items, totals, shipping, payment context, fulfillment status, and customer links where supported? | Order migration should support lookup and service continuity without being confused with live checkout setup. |
| Customers, contacts, and members | Which source records should become commerce customers, CRM contacts, site members, subscribers, or app-related records?                    | Buyer identity should be classified before scope is accepted.                                                 |
| Apps and integrations            | Which business workflows depend on apps, external systems, custom fields, or Wix development capabilities?                                 | Unsupported or app-owned data may need Add-ons, Custom Service, target setup, or exclusion.                   |

The planning goal is not to make Wix behave exactly like the source store. The goal is to preserve business value in a Wix-appropriate form.

### Site Content, Design, and SEO in Wix <a href="#site-content-design-and-seo-in-wix" id="site-content-design-and-seo-in-wix"></a>

Wix is often chosen because the website experience matters as much as the store catalog. That makes content, media, page structure, and SEO part of migration planning from the beginning. A merchant moving into Wix may expect product pages, collection pages, landing pages, Blog Posts, policy pages, galleries, forms, menus, internal links, and design sections to continue supporting the business after launch.

These areas should be planned separately from ordinary commerce records. CMS Pages and Blog Posts may migrate where they are part of supported scope, but page layout, editor sections, animations, form behavior, custom widgets, embedded scripts, and site design usually need target-side implementation. URL and SEO planning also needs special attention because a content-rich source site may have high-value landing pages and internal links that are not obvious from product data alone.

| Site area    | Wix migration concern                                                                                                     | Practical decision                                                           |
| ------------ | ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| CMS Pages    | Informational, policy, landing, and service pages may carry SEO and conversion value.                                     | Decide which pages migrate, which are rebuilt in Wix, and which are retired. |
| Blog Posts   | Blog content may include authorship, dates, tags, categories, media, internal links, and metadata.                        | Test Blog Posts separately from product migration.                           |
| Media        | Product images, page images, galleries, downloadable files, videos, and alt text may live in different source structures. | Validate media in both catalog and page contexts.                            |
| Site design  | Layout, templates, mobile presentation, menus, and page sections are Wix implementation concerns.                         | Define design expectations as target setup, not automatic data migration.    |
| URLs and SEO | Product slugs, page slugs, redirects, metadata, internal links, multilingual URLs, and domains affect launch continuity.  | Inventory high-value URLs before migration and revalidate before launch.     |

A Wix migration can preserve commerce data while still leaving the site experience unfinished. The launch plan should therefore include both data validation and site-readiness validation.

### Apps, CMS Data, Velo, and External Systems <a href="#apps-cms-data-velo-and-external-systems" id="apps-cms-data-velo-and-external-systems"></a>

Wix sites may rely on business apps, CMS collections, custom code, APIs, and external systems. These can carry business meaning that is not part of ordinary commerce records. Examples include booking data, event registrations, restaurant ordering behavior, membership plans, forms, loyalty data, custom CMS collections, external database connections, CRM fields, marketing tags, custom product displays, or checkout-adjacent integrations.

These dependencies should be identified before service-path decisions are made. Some records may fit supported migration scope. Some needs may be handled by Add-ons when the requirement stays within supported filtering, mapping, or configuration. Some requirements require Custom Service because they involve unsupported records, custom fields, external identifiers, bespoke transformation, custom migration logic, or app-owned data. Some workflows belong to Wix setup or third-party app configuration rather than migration.

| Dependency type                | Wix planning treatment                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Wix app records                | Confirm whether records are supported, rebuilt in the target app, handled separately, or excluded.                  |
| CMS collections                | Determine whether the data is commerce content, site content, custom data, or app-owned structure.                  |
| Velo/API behavior              | Review whether custom logic affects catalog, checkout, pages, members, CRM, or integrations.                        |
| External databases and systems | Identify external IDs, sync direction, ownership, and post-migration reconnection requirements.                     |
| Service plugins                | Distinguish live checkout, payment, shipping, tax, fulfillment, and custom flow requirements from migrated history. |

Wix can be flexible, but flexibility does not remove the need for scope discipline. Custom behavior must be discovered, classified, and validated rather than assumed to migrate as normal store data.

### Wix Migration Planning Boundaries <a href="#wix-migration-planning-boundaries" id="wix-migration-planning-boundaries"></a>

A Wix migration plan should separate four kinds of work: migrated records, target configuration, site implementation, and custom or integration work. When these boundaries are blurred, the merchant may approve a data migration that still leaves the target store incomplete.

| Workstream                 | Examples                                                                                                       | How to handle it                                                              |
| -------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Migrated records           | Products, collections, customers, orders, Coupons, Blog Posts, CMS Pages, images, URLs, and supported fields.  | Define supported scope and validate representative samples.                   |
| Wix configuration          | Payments, shipping, tax, checkout settings, notifications, fulfillment, apps, domains, and site permissions.   | Prepare and test directly in Wix.                                             |
| Site implementation        | Layout, menus, page design, product-page presentation, content sections, mobile display, and brand experience. | Treat as target build work, not data migration.                               |
| Custom or integration work | Velo logic, app-owned data, external IDs, custom fields, API workflows, and unsupported source structures.     | Review for Add-ons, Custom Service, integration setup, or accepted exclusion. |

This boundary-setting is especially important for merchants moving from custom-coded carts, WooCommerce/WordPress sites, Shopify apps, or content-heavy CMS platforms. Wix may be the right Target Platform, but the migration plan should not imply that every source-side behavior is transferred through the same path.

### What Merchants Should Understand Before Choosing Wix <a href="#what-merchants-should-understand-before-choosing-wix" id="what-merchants-should-understand-before-choosing-wix"></a>

Wix is a strong Target Platform when the merchant wants hosted site-commerce ownership and is willing to operate inside Wix-supported structures. It is especially useful when the future store should combine products, pages, content, media, checkout, basic customer management, and business apps without requiring self-hosted infrastructure.

Wix requires more caution when the source store depends on strict custom-code parity, advanced product configurators, unusual checkout rules, large-scale B2B workflows, deep external-system dependency, or highly customized content architecture. These conditions do not automatically disqualify Wix, but they change the migration approach. The merchant may need better source-data samples, tighter Demo Migration review, target setup planning, Add-ons, Custom Service, or a decision to simplify selected source behavior.

A practical Wix decision should therefore answer three questions:

| Decision question                                                                | Why it matters                                                                  |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Can the core business operate inside Wix-supported commerce and site structures? | This confirms whether Wix is a suitable target operating environment.           |
| Which source behaviors should be migrated, rebuilt, configured, or excluded?     | This prevents unsupported expectations from being treated as migration defects. |
| What must be proven before launch?                                               | This turns the platform decision into a validation plan.                        |

The strongest Wix migration plans are realistic about what Wix should own. They protect valuable products, content, URLs, customer context, and order history while keeping design, checkout, apps, and custom logic in the right workstream.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix is a hosted site-builder commerce Target Platform where migration planning must connect commerce records with site structure, content, apps, URLs, and target-side setup. It can be a strong destination for merchants that want practical site-commerce ownership without self-hosted infrastructure. It becomes more conditional when the source store depends on custom code, app-owned records, complex product behavior, strict design parity, advanced checkout logic, or external systems.

A successful Wix migration is not proven by product and order counts alone. It is proven when the target Wix store can present products clearly, preserve useful customer and order context, support important content and URLs, run through configured checkout and fulfillment settings, and operate through the apps or custom work that the business actually needs.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Wix a hosted or self-hosted Target Platform?**

Wix is hosted. The merchant does not manage the server or source-code environment in the same way as a self-hosted open-source platform. Migration planning should therefore separate supported data transfer from Wix setup, apps, site implementation, and custom development choices.

**Is Wix the same as a standard store platform?**

No. Wix combines website building and commerce. Product data, site pages, media, menus, checkout settings, apps, CMS data, and URLs can all affect the launch result.

**Can product variants migrate cleanly to Wix?**

They can when the source product structure aligns with Wix options, choices, variants, SKUs, inventory, and pricing behavior. Complex configurators, add-ons, bundles, or custom product logic need separate review.

**Will the source store design migrate directly into Wix?**

Not automatically. Store design, layouts, menus, mobile presentation, and content sections usually need Wix-side implementation. Migration can support the data and assets, but it should not be treated as a complete design transfer.

**What should be checked before committing to Wix migration?**

Check product complexity, collection and navigation expectations, customer/contact/member meaning, historical order needs, checkout configuration, CMS Pages, Blog Posts, high-value URLs, apps, custom fields, and external-system dependencies.
