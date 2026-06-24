# VTEX Platform Overview

VTEX is an enterprise SaaS Target Platform for businesses that need structured commerce operations across catalog, pricing, sales channels, marketplace, OMS, logistics, customer data, storefront implementation, apps, APIs, and external systems. A VTEX migration should therefore be planned as a platform transition, not only as a transfer of products, customers, orders, and content.

The practical value of VTEX comes from how its commerce layers work together. Products become usable through SKUs, specifications, categories, brands, images, attachments, assembly options, services, kits, collections, pricing, stock, trade policies, and storefront availability. Orders become operationally useful when OMS, sellers, logistics, fulfillment, invoices, payment references, and back-office integrations can still be understood. Customer data becomes usable when profiles, B2B or account context, consent, segmentation, Master Data, and external IDs are interpreted correctly.

For migration planning, the central question is not whether VTEX can receive store data. The more important question is whether the migrated data can support the intended operating model: direct-to-consumer selling, B2B, marketplace, seller-led commerce, multichannel sales, composable storefronts, or an integration-heavy commerce architecture.

### VTEX at a Glance <a href="#vtex-at-a-glance" id="vtex-at-a-glance"></a>

| Platform area                  | What VTEX changes                                                                                                                                            | Migration planning impact                                                                                                     |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Catalog                        | Products, SKUs, categories, brands, specifications, attachments, assembly options, services, kits, and collections may all affect sellability and discovery. | Product migration must be judged by buyer-facing and operations-facing behavior, not only by product-count parity.            |
| Pricing and sales context      | Prices, promotions, trade policies, sales channels, marketplace offers, and external pricing sources may decide what each audience can buy.                  | Price validation should include representative channels and customer contexts.                                                |
| Marketplace and sellers        | Marketplace, seller, offer, fulfillment, and commission logic can affect both catalog and order interpretation.                                              | Seller-led data should not be flattened into ordinary product and order records without scope review.                         |
| OMS and logistics              | Order history, status, fulfillment, invoice, pickup, delivery, and external operations references may carry business meaning.                                | Operations teams should validate order readability, not only order existence.                                                 |
| Master Data and custom records | Customer, account, app, and workflow data may live in Master Data or integration-owned structures.                                                           | Custom records and external IDs should be identified before migration scope is accepted.                                      |
| Storefront implementation      | FastStore, Store Framework, Legacy CMS Portal, or headless storefront choices affect how migrated data is displayed.                                         | Content, search, facets, URLs, redirects, and CMS behavior need storefront-aware review.                                      |
| Apps and integrations          | ERP, PIM, WMS, marketplace, payment, anti-fraud, analytics, middleware, and custom apps may own critical behavior.                                           | Integration-sensitive data may need Add-ons, Custom Service, or post-migration implementation outside standard data transfer. |

### Why VTEX Requires Platform-Level Migration Planning <a href="#why-vtex-requires-platform-level-migration-planning" id="why-vtex-requires-platform-level-migration-planning"></a>

VTEX is usually selected for operating models that need more structure than a simple hosted storefront. Its strength is the ability to coordinate catalog, pricing, seller context, checkout, order management, logistics, storefront experience, and integration workflows across one commerce environment.

That strength also increases planning responsibility. A product that appears in VTEX may still be incomplete if its SKU activation, specifications, pricing, trade policy availability, marketplace context, or storefront visibility is not ready. A customer record may still be incomplete if segmentation, B2B/account context, consent, Master Data, or external IDs are missing. An order may still be incomplete if finance, support, fulfillment, or marketplace teams cannot understand the migrated status and references.

| Planning question                                                 | Why it matters in VTEX                                                                                                                    |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| What does the target commerce model need to support?              | VTEX can support B2C, B2B, marketplace, multichannel, and composable storefront operations, but each model changes validation priorities. |
| Which catalog structures control buying behavior?                 | SKUs, specifications, attachments, services, kits, and collections may determine product selection and sellability.                       |
| Which pricing rules must remain commercially meaningful?          | Trade policies, promotions, price tables, sales channels, and marketplace pricing may not behave like simple source-store prices.         |
| Which operational systems must recognize migrated records?        | ERP, PIM, WMS, OMS, payment, marketplace, and middleware references may decide whether the migrated store can operate.                    |
| Which data belongs to VTEX and which belongs to external systems? | Some records should be migrated, while others should be mapped, excluded, reconstructed, or handled through Custom Service.               |

### Where VTEX Is Often a Strong Target <a href="#where-vtex-is-often-a-strong-target" id="where-vtex-is-often-a-strong-target"></a>

VTEX is often a strong Target Platform when the business needs enterprise SaaS commerce with governed catalog operations, multichannel selling, complex pricing, marketplace structures, and integration depth. It is most effective when the merchant is prepared to define how target data should behave inside VTEX rather than expecting a one-to-one copy of the previous platform.

| Strong-fit signal                   | What it means for migration                                                                                                                 |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| SKU-rich catalog operations         | Demo Migration should include complex SKUs, required specifications, images, pricing, stock, and storefront availability.                   |
| Structured merchandising            | Categories, brands, specifications, filters, facets, search, and collections should be reviewed as business logic, not decorative metadata. |
| Channel and trade-policy complexity | Sales context should be validated across the channels and audiences that matter for launch.                                                 |
| Marketplace or seller operations    | Seller, offer, fulfillment, commission, and marketplace references may require dedicated review.                                            |
| B2B or mixed B2B/B2C commerce       | Customer/account data, pricing visibility, buyer roles, approval expectations, and external IDs may require deeper scoping.                 |
| Integration-heavy operations        | ERP, PIM, WMS, marketplace, payment, analytics, middleware, and custom apps should be mapped before migration acceptance.                   |

### Where VTEX Needs Careful Scoping <a href="#where-vtex-needs-careful-scoping" id="where-vtex-needs-careful-scoping"></a>

VTEX can still be a suitable Target Platform when the project includes conditional complexity, but those conditions need to be handled early. The migration becomes harder when the Source Platform contains custom product options, unusual bundles, marketplace logic, direct database dependencies, extension-owned data, or storefront behavior that is not represented by ordinary commerce entities.

| Conditional area                               | What should be clarified before migration                                                                                                                         |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product options and custom buying flows        | Decide whether the target needs SKU specifications, attachments, assembly options, services, kits, accepted exclusions, or Custom Service review.                 |
| Advanced pricing and promotions                | Confirm whether prices, campaigns, coupons, discounts, trade policies, or marketplace pricing are migration scope, configuration scope, or external-system scope. |
| Marketplace and seller data                    | Separate seller catalog, order, fulfillment, commission, and offer requirements from ordinary catalog migration.                                                  |
| Master Data and app-owned fields               | Identify which custom records must migrate, which only need reference preservation, and which need later implementation.                                          |
| Storefront redesign or headless implementation | Treat storefront rendering, CMS behavior, search, URL paths, redirects, and content placement as separate readiness layers.                                       |
| External workflow dependencies                 | Confirm whether ERP, PIM, WMS, payment, anti-fraud, analytics, marketplace, and middleware records depend on migrated IDs or custom fields.                       |

### Migration Scope Signals for VTEX <a href="#migration-scope-signals-for-vtex" id="migration-scope-signals-for-vtex"></a>

A VTEX migration should classify each requirement by migration ownership. Some requirements fit Standard Service, some can be handled through Add-ons, some need Managed Service coordination, and some require Custom Service because the target result depends on custom interpretation or implementation-specific logic.

| Requirement type                                                                                                                        | Typical handling signal                                                                                      |
| --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Core products, customers, orders, CMS Pages, Blog Posts, and related standard entities                                                  | Usually suitable for Standard Service when source data is accessible and target behavior is straightforward. |
| Additional fields, filters, selected mappings, or supported adjustments                                                                 | May be suitable for Add-ons when the requirement stays within supported migration logic.                     |
| Complex coordination, sample design, stakeholder review, or launch-risk management                                                      | Often suitable for Managed Service when the merchant needs more guided execution.                            |
| Custom records, non-standard app data, marketplace-specific interpretation, external workflow dependencies, or target-structure changes | Should be reviewed for Custom Service.                                                                       |
| New records added after the initial migration scope                                                                                     | Should be reviewed through Additional Migration Options and revalidated before acceptance.                   |

### What Demo Migration Should Prove for VTEX <a href="#what-demo-migration-should-prove-for-vtex" id="what-demo-migration-should-prove-for-vtex"></a>

Demo Migration is especially important for VTEX because simple sample records may hide the real migration challenge. The sample set should include records that represent the actual business model, not only the cleanest products or newest orders.

| Sample type                       | What it should prove                                                                                           |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Complex product/SKU examples      | SKU structure, images, categories, specifications, pricing, stock, activation, and storefront discoverability. |
| Pricing and trade-policy examples | Correct commercial behavior across representative channels, audiences, or sales contexts.                      |
| Marketplace/seller examples       | Seller, offer, fulfillment, marketplace, and order-context readability.                                        |
| Customer and Master Data examples | Customer profile completeness, segmentation, consent, B2B/account context, custom fields, and external IDs.    |
| Order examples                    | Historical order readability across status, payment, fulfillment, invoice, logistics, and support use cases.   |
| Storefront/content examples       | CMS Pages, Blog Posts, URLs, redirects, metadata, search, facets, and priority landing paths.                  |
| Integration-sensitive examples    | ERP, PIM, WMS, marketplace, payment, middleware, app, and API reference continuity.                            |

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX is a strong Target Platform for merchants that need enterprise SaaS commerce, structured catalog and SKU operations, trade-policy control, marketplace or seller architecture, OMS and logistics depth, storefront flexibility, Master Data, and integration-heavy workflows. Its migration value depends on whether the target environment preserves business meaning, not only whether records arrive.

Before moving to Full Migration, use Demo Migration to test the records that define the real operating model: complex SKUs, required specifications, price and trade-policy examples, marketplace or seller records, B2B/account data, historical orders, Master Data, storefront paths, CMS Pages, Blog Posts, redirects, and integration references. If the sample results show unsupported custom logic, external dependencies, or target-structure gaps, review Add-ons, Managed Service, or Custom Service before finalizing the migration approach.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is VTEX a good Target Platform for simple stores?**

VTEX can support simple selling, but it is usually strongest when the business needs enterprise SaaS commerce, structured catalog operations, multichannel sales, marketplace context, B2B or mixed selling models, and integration depth. A simpler hosted platform may be easier when the business only needs a basic product catalog and checkout flow.

**What makes VTEX migration more complex than a basic hosted-store migration?**

VTEX migration can involve products, SKUs, specifications, attachments, assembly options, services, kits, collections, trade policies, pricing, marketplace records, OMS context, logistics, Master Data, storefront implementation, apps, APIs, and external integrations. These layers need to be reviewed together because they affect whether the migrated store can operate normally.

**Does migrating products to VTEX automatically make them sellable?**

No. Product records still need correct SKU structure, required specifications, images, pricing, stock, activation, category placement, trade-policy availability, and storefront visibility. Demo Migration should include complex product examples to confirm sellability.

**Should marketplace or seller data be treated as ordinary product and order data?**

No. Marketplace and seller data can include seller relationships, offers, received SKU suggestions, commissions, fulfillment context, sales-channel mapping, and external marketplace references. These details should be scoped separately when they affect daily operations.

**What should be confirmed before judging a VTEX Demo Migration?**

Demo Migration should prove that representative products, SKUs, prices, trade policies, customers, orders, sellers, storefront paths, search behavior, CMS Pages, Blog Posts, URLs, apps, APIs, Master Data, and integration references work in the intended target context. Record counts alone are not enough.
