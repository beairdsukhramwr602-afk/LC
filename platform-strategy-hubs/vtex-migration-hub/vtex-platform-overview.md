# VTEX Platform Overview

VTEX is a hosted enterprise commerce Target Platform for businesses that need structured catalog management, complex SKU handling, pricing governance, marketplace and seller operations, B2B or B2C selling models, storefront flexibility, and integration-heavy commerce workflows. It is a continuously updated SaaS platform, so migration planning should confirm the target VTEX account, storefront solution, enabled modules, app stack, trade policies, seller architecture, and external integrations before results are judged.

A migration to VTEX should be planned as more than moving products, customers, orders, and content into a hosted store. VTEX commerce outcomes depend on how catalog data becomes products and SKUs, how specifications support merchandising and discovery, how price tables and trade policies affect selling context, how Checkout and OMS interpret orders, how storefront technology presents migrated data, and how apps, APIs, Master Data, and external systems connect to daily operations.

For merchants coming from simpler platforms, the main change is depth. VTEX can support sophisticated commerce models, but that strength also increases the need for clean scope definition, representative Demo Migration samples, and careful validation. A record that exists in VTEX is not automatically ready for launch until it is active, discoverable, priced correctly, purchasable, operationally readable, and aligned with the intended storefront and integration model.

### What Changes in a Migration to VTEX <a href="#what-changes-in-a-migration-to-vtex" id="what-changes-in-a-migration-to-vtex"></a>

Moving into VTEX changes how store data is structured, governed, and proven after migration. The target environment is not only a database of migrated records; it is a commerce architecture where catalog, pricing, checkout, OMS, storefront, marketplace, apps, APIs, and integrations must work together.

| Migration area                      | What changes in VTEX                                                                                                                                                            | Planning implication                                                                                                                       |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Hosted SaaS operation               | The store runs inside a managed cloud commerce platform with platform-defined services, APIs, account structure, apps, and continuous updates.                                  | Custom code, direct database behavior, and self-hosted assumptions should be reviewed before they are treated as ordinary migration scope. |
| Catalog and SKUs                    | Products, SKUs, brands, categories, images, specifications, specification groups, SKU activation, attachments, services, kits, and collections can all affect target usability. | Demo Migration should include complex products and active SKUs, not only simple product records.                                           |
| Specifications and discovery        | Source attributes may need to become product specifications, SKU specifications, filters, facets, or merchandising values.                                                      | Attribute mapping should be judged by storefront discovery and product detail usability, not only by field presence.                       |
| Pricing and trade policies          | Base prices, fixed prices, computed prices, price tables, promotions, and trade policies can affect what different channels or customer contexts see.                           | Price validation should include the selling context, not only a single default product price.                                              |
| Checkout and orderForm behavior     | Cart, customer profile, address, seller, marketing, coupon, payment, shipping, and custom information may be interpreted through VTEX Checkout structures.                      | Historical order data should be separated from live checkout configuration and test-order readiness.                                       |
| Orders and OMS flows                | Orders may carry marketplace, seller, complete, or chain-flow meaning, plus status, payment, fulfillment, pickup, delivery, and back-office context.                            | Operations teams should validate whether historical orders remain readable and useful after migration.                                     |
| Marketplace and seller architecture | Seller relationships, received SKU suggestions, matching, offer cataloging, commissions, sales-channel mapping, and marketplace flows may affect the target model.              | Marketplace or seller data should be scoped as its own planning layer instead of being flattened into ordinary products and orders.        |
| Storefront solution                 | VTEX storefront behavior depends on the chosen storefront solution, such as FastStore, Store Framework, Legacy CMS Portal, or headless implementation.                          | Design, content, search, CMS, and URL continuity should be planned alongside data migration.                                               |
| Apps, APIs, and external systems    | VTEX IO apps, Master Data, ERP, PIM, WMS, payment, anti-fraud, marketplace, and headless integrations may hold business-critical references.                                    | Integration-sensitive fields and external IDs should be mapped, excluded intentionally, or routed to Custom Service review.                |

### Where VTEX Is Often a Strong Target <a href="#where-vtex-is-often-a-strong-target" id="where-vtex-is-often-a-strong-target"></a>

VTEX is often a strong target when the business needs enterprise commerce capability rather than a lightweight hosted storefront. It can be suitable for merchants that operate across channels, manage complex catalogs, use B2B and B2C selling models, coordinate sellers or marketplaces, or rely on connected business systems.

#### Enterprise and multi-channel commerce operations <a href="#enterprise-and-multi-channel-commerce-operations" id="enterprise-and-multi-channel-commerce-operations"></a>

VTEX can fit businesses that need a hosted commerce foundation for multiple sales contexts. This can include retail, marketplace, B2B, B2C, regional, brand, franchise, or seller-driven operations where catalog, pricing, checkout, fulfillment, and storefront behavior need more structure than a simple store setup provides.

The fit is strongest when the merchant is prepared to define how products, SKUs, prices, trade policies, promotions, channels, and fulfillment flows should work in the target account. The migration should support the intended operating model, not only reproduce old record lists.

#### SKU-rich catalogs and structured merchandising <a href="#sku-rich-catalogs-and-structured-merchandising" id="sku-rich-catalogs-and-structured-merchandising"></a>

VTEX can be a strong target for catalogs that depend on SKU-level selling, specifications, category hierarchy, brands, images, collections, filters, and search behavior. This is especially important when shoppers need to compare options, narrow results through facets, or buy specific variations with accurate pricing and stock.

A good migration plan should identify product samples where SKU activation, specifications, images, pricing, stock, and storefront availability all matter. These samples reveal whether catalog meaning has been translated correctly into VTEX.

#### B2B, marketplace, and seller-driven models <a href="#b2b-marketplace-and-seller-driven-models" id="b2b-marketplace-and-seller-driven-models"></a>

VTEX can support more advanced selling models than a single direct-to-consumer catalog. B2B accounts, customer segmentation, seller relationships, marketplace flows, sales-channel behavior, commissions, and offer management can all influence the target migration outcome.

These models require early scoping because their data meaning often lives across more than one area of the platform. Customer records, product records, pricing rules, order flows, seller relationships, and external system references may need to be reviewed together.

#### Integration-heavy commerce environments <a href="#integration-heavy-commerce-environments" id="integration-heavy-commerce-environments"></a>

VTEX can be a strong target for businesses that rely on ERP, PIM, WMS, accounting, payment, anti-fraud, marketplace, logistics, analytics, or headless systems. Its API and app ecosystem can support complex operating environments, but integrations must be planned as part of the migration context.

External IDs, app-owned data, Master Data records, custom fields, and integration references should not be assumed to migrate as standard commerce data. They need to be identified before the merchant uses Demo Migration results to make launch decisions.

### Where Deeper Planning Is Usually Needed <a href="#where-deeper-planning-is-usually-needed" id="where-deeper-planning-is-usually-needed"></a>

Deeper planning is usually needed when the Source Platform has custom commerce logic, complex product structures, channel-specific pricing, marketplace flows, B2B rules, app-owned data, or external-system dependencies. These areas can make VTEX a powerful target, but they also increase migration interpretation work.

#### Product and SKU translation <a href="#product-and-sku-translation" id="product-and-sku-translation"></a>

Source products may not map cleanly to VTEX products and SKUs. A source variation, configurable product, bundle, kit, add-on, modifier, custom option, or product service may need different treatment inside VTEX.

Planning should identify whether the target result needs simple SKU representation, SKU specifications, product specifications, attachments, assembly options, services, kits, or accepted exclusions. The correct decision depends on how shoppers buy the product and how managers operate it after launch.

#### Pricing, promotions, and trade policies <a href="#pricing-promotions-and-trade-policies" id="pricing-promotions-and-trade-policies"></a>

VTEX pricing can depend on price tables, trade policies, fixed prices, computed prices, promotions, coupons, channel rules, and customer context. A migration that preserves only default prices may miss commercially important behavior.

Stores with B2B pricing, regional pricing, marketplace pricing, customer-group pricing, contract pricing, or channel-specific promotion logic should prepare representative examples before migration scope is finalized.

#### Orders, sellers, marketplaces, and fulfillment context <a href="#orders-sellers-marketplaces-and-fulfillment-context" id="orders-sellers-marketplaces-and-fulfillment-context"></a>

VTEX order interpretation can involve OMS flows, sellers, marketplace context, pickup or delivery behavior, payment status, fulfillment status, invoices, tracking, and back-office integration. Historical orders need to remain understandable for customer service, finance, and operations.

Order validation should therefore include varied statuses, payment scenarios, fulfillment scenarios, seller contexts, and marketplace examples where relevant. Matching totals alone is not enough for a complex VTEX migration.

#### Storefront, search, CMS, and URL continuity <a href="#storefront-search-cms-and-url-continuity" id="storefront-search-cms-and-url-continuity"></a>

VTEX storefront outcomes depend on the target storefront solution and implementation choices. Product data may migrate correctly while category navigation, search facets, banners, content pages, product detail layout, URLs, redirects, metadata, and landing pages still require separate planning.

SEO-sensitive stores should prepare priority product URLs, category URLs, content URLs, metadata, redirects, and discovery paths before launch decisions are made.

#### Apps, Master Data, APIs, and external systems <a href="#apps-master-data-apis-and-external-systems" id="apps-master-data-apis-and-external-systems"></a>

Apps, Master Data, APIs, ERP, PIM, WMS, accounting, payment, anti-fraud, marketplace, and headless integrations can hold data that is not part of ordinary product, customer, order, or content migration. These dependencies may decide whether a migrated store can operate normally after launch.

If external identifiers, custom records, app-owned fields, integration references, or custom checkout fields are business-critical, they should be scoped separately. Requirements that need custom interpretation or custom migration logic adjustment are handled through Custom Service.

### What Should Be Understood Early Before Moving into VTEX <a href="#what-should-be-understood-early-before-moving-into-vtex" id="what-should-be-understood-early-before-moving-into-vtex"></a>

VTEX migration planning should clarify the target commerce model before the migration result is accepted. The same product, customer, order, or page can carry different meaning depending on the target catalog structure, pricing model, storefront solution, seller setup, and integration environment.

The following points should be understood early:

* VTEX is a continuously updated SaaS commerce platform, so planning should confirm the target account, storefront solution, modules, trade policies, app stack, and integrations.
* Product validation should include SKUs, specifications, categories, brands, images, stock, activation, and storefront availability.
* Pricing validation should include price tables, fixed or computed prices, promotions, coupons, and trade-policy behavior where they affect selling.
* Customer validation may need to include B2B account context, customer profile fields, addresses, preferences, consent, and Master Data records.
* Order validation should include OMS flow meaning, sellers, marketplace context, payment state, fulfillment state, pickup or delivery behavior, and back-office references.
* Live checkout, payment, tax, shipping, logistics, and orderForm behavior require target setup and test orders; historical order migration does not prove live checkout readiness.
* Storefront validation should include product detail pages, category browsing, search, facets, content, CMS behavior, URLs, redirects, metadata, and priority landing paths.
* App, API, Master Data, ERP, PIM, WMS, marketplace, payment, anti-fraud, and headless dependencies should be mapped before they are treated as migrated or excluded.
* Demo Migration should include high-value complex examples, not only clean or simple records.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX can be a strong Target Platform for merchants that need hosted enterprise commerce, structured SKU management, sophisticated pricing, B2B or B2C selling models, marketplace and seller architecture, storefront flexibility, and integration depth. Its migration value depends on whether the new environment can preserve the business meaning behind the data, not only whether records are transferred.

Before moving to Full Migration, use Demo Migration to test the records that define the real business model: complex SKUs, required specifications, price tables, trade policies, B2B customers, marketplace or seller orders, checkout-sensitive records, storefront discovery paths, priority URLs, and integration references. If those samples reveal custom logic, external dependencies, or target-structure gaps, discuss Add-ons or Custom Service through Live Chat before finalizing the migration approach.

### FAQs <a href="#faqs" id="faqs"></a>

**Is VTEX a hosted or self-hosted platform?**

VTEX is a hosted SaaS commerce platform. Migration planning should treat it as a managed cloud Target Platform with platform-defined catalog, checkout, order, marketplace, storefront, app, API, and integration structures rather than as a self-hosted database or open-source cart.

**What makes VTEX different from a simpler hosted store?**

VTEX can involve products, SKUs, specifications, price tables, trade policies, promotions, checkout orderForm behavior, OMS flows, sellers, marketplaces, storefront solutions, apps, APIs, Master Data, and external integrations. A good migration plan checks how these layers work together after the data is moved.

**Does migrating products to VTEX automatically make them sellable?**

No. Product records still need the right SKU structure, required specifications, images, pricing, stock, activation, category placement, trade-policy availability, and storefront visibility. Demo Migration should include complex product examples to confirm sellability.

**Should marketplace or seller data be treated as ordinary product and order data?**

No. Marketplace and seller data can include seller relationships, offers, received SKU suggestions, commissions, sales-channel mapping, order-flow meaning, and external marketplace references. These details should be scoped separately when they affect daily operations.

**What should be confirmed before judging a VTEX Demo Migration?**

The review should confirm whether representative products, SKUs, prices, trade policies, customers, orders, sellers, storefront paths, search behavior, URLs, apps, APIs, Master Data, and integration references work in the intended target context. Record counts alone are not enough.
