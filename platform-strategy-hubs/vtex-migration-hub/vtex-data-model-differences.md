# VTEX Data Model Differences

A VTEX migration changes the meaning of store data because VTEX is not organized as a flat product, customer, order, and content database. It is a connected commerce architecture where Catalog, SKUs, specifications, trade policies, pricing, promotions, marketplace operations, OMS, logistics, Master Data, apps, APIs, and storefront implementation all influence how migrated records behave after launch.

The central data-model question is not whether records can be transferred. It is whether the business meaning behind those records can be represented clearly in VTEX. A source-store option, product attribute, customer segment, seller assignment, order status, campaign rule, or custom checkout field may need a different target structure from the one used in the Source Platform.

### Why VTEX Data Meaning Is Different <a href="#why-vtex-data-meaning-is-different" id="why-vtex-data-meaning-is-different"></a>

VTEX separates commerce meaning across several operating layers. Catalog records define what can be sold. SKUs and specifications shape purchasable choices and discovery. Trade policies, pricing, and promotions determine commercial context. OMS and logistics shape order operations. Master Data, apps, APIs, and external systems may carry business-specific information that does not belong in standard product, customer, order, CMS Page, or Blog Post fields.

| Source-store concept | VTEX interpretation                                                                                                             | Migration planning implication                                                                        |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Product record       | Product definition connected to SKUs, categories, brands, specifications, images, and availability context.                     | Product samples must test structure, activation, and storefront usability, not only record count.     |
| Variant or option    | SKU, product specification, SKU specification, attachment, assembly option, service, kit, or custom logic depending on meaning. | Options must be classified by commercial purpose before mapping is approved.                          |
| Product attribute    | Specification, filter, product detail, SKU detail, custom field, app data, or excluded value.                                   | Attribute treatment should preserve discovery, operations, reporting, or integration value.           |
| Price or discount    | Price table, fixed price, promotion, coupon, trade-policy behavior, or external pricing logic.                                  | Price validation must include sales context, not only default visible price.                          |
| Customer segment     | Customer profile, B2B/business context, Master Data, trade policy, price access, or integration rule.                           | Customer data may need scope beyond name, email, and address fields.                                  |
| Marketplace record   | Seller, offer, SKU matching, commission, channel, order-flow, or integration context.                                           | Marketplace meaning should not be flattened into a generic product or order note.                     |
| Checkout field       | Supported checkout data, Master Data, app-owned data, custom behavior, or accepted exclusion.                                   | Custom checkout values should be classified by display, fulfillment, reporting, and integration need. |
| Storefront content   | CMS Page, Blog Post, menu, route, search/discovery, storefront component, or implementation workstream.                         | Content migration must align with the chosen VTEX storefront model.                                   |

This makes VTEX data-model planning especially important for merchants with complex product structures, channel-specific selling, marketplace or seller operations, B2B/B2C business models, ERP/PIM/WMS dependencies, custom checkout data, Master Data records, or storefront modernization goals.

### Product, SKU, Category, Brand, and Specification Model <a href="#product-sku-category-brand-and-specification-model" id="product-sku-category-brand-and-specification-model"></a>

VTEX catalog quality depends on the relationship between products and SKUs. A product describes the commercial item. A SKU represents the specific purchasable variation or physical unit. Categories, brands, and specifications then control organization, filtering, detail display, and activation readiness.

| Data area      | What must be preserved                                                                                                    | What can go wrong if it is flattened                                                               |
| -------------- | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Products       | Commercial identity, descriptions, brand, category placement, images, metadata, and visibility.                           | The catalog may look complete while discovery, merchandising, or product detail pages remain weak. |
| SKUs           | Purchasable variations, SKU codes, stock-sensitive units, images, prices, activation conditions, and external references. | Shoppers may see missing choices, inactive SKUs, wrong images, or unreliable inventory behavior.   |
| Categories     | Department/category/subcategory hierarchy and navigation meaning.                                                         | Internal source groupings may become shopper-facing paths that do not support search or browsing.  |
| Brands         | Brand identity used for discovery, filtering, merchandising, or reporting.                                                | Brand values may become plain text instead of usable catalog structure.                            |
| Specifications | Product and SKU properties used for filters, details, comparison, or operations.                                          | Attributes may lose their functional meaning if moved only into descriptions or custom fields.     |

A VTEX migration should not approve product mapping based only on matching product names and descriptions. It should confirm how products become purchasable SKUs, how specifications remain usable, how images attach to the correct level, and how category and brand structure support the intended storefront experience.

### Variant, Option, and Custom Product Behavior <a href="#variant-option-and-custom-product-behavior" id="variant-option-and-custom-product-behavior"></a>

Source platforms often use variants, options, modifiers, bundles, add-ons, custom fields, or extension data to represent product choices. VTEX may interpret those choices differently depending on whether they affect stock, price, fulfillment, customer input, or display.

| Source behavior                    | Likely VTEX review path                                                           | Decision question                                                                     |
| ---------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Color, size, or physical variation | SKU and SKU specification review.                                                 | Does each choice represent a distinct purchasable or stock-managed unit?              |
| Informational attribute            | Product specification, SKU specification, product detail, or excluded value.      | Does the value support filtering, display, comparison, reporting, or operations?      |
| Free customization input           | Attachment, Master Data, app behavior, or custom checkout/product behavior.       | Must the value be collected, stored, displayed, fulfilled, or sent to another system? |
| Component-based product            | Kit, assembly option, separate SKU relationship, app behavior, or Custom Service. | Do stock, price, or fulfillment depend on selected components?                        |
| Optional paid service              | Service relationship, separate product, app behavior, or custom logic.            | Does the service affect order handling, invoicing, fulfillment, or customer choice?   |
| Merchandising group                | Collection, category, search result, campaign rule, or storefront implementation. | Is the group permanent catalog structure or temporary merchandising logic?            |

The right mapping is determined by business meaning. Forcing every option into a SKU can make the catalog unnecessarily complex. Flattening true purchasable choices can damage buying, fulfillment, and reporting. When the source behavior is powered by custom code or unsupported third-party data, the requirement should be separated from ordinary field mapping and reviewed for Custom Service.

### Pricing, Promotions, Trade Policies, and Sales Channels <a href="#pricing-promotions-trade-policies-and-sales-channels" id="pricing-promotions-trade-policies-and-sales-channels"></a>

VTEX price meaning can depend on base prices, price tables, fixed prices, promotions, coupons, trade policies, sales channels, marketplace conditions, B2B/B2C context, and external systems. A source-store price is not always a single target value.

| Pricing situation              | VTEX data-model concern                                           | Required review                                                                                |
| ------------------------------ | ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Simple default price           | Product/SKU price in the expected selling context.                | Confirm default price displays correctly and matches the intended SKU.                         |
| Channel-specific price         | Price table, trade policy, or sales-channel behavior.             | Confirm the same SKU can show the right value in each commercial context.                      |
| Customer-specific or B2B price | Account, segment, price table, custom rule, or integration logic. | Confirm whether the value is migrated, configured, rebuilt, or supplied by an external system. |
| Promotion or coupon            | VTEX promotion/coupon configuration or excluded historical rule.  | Confirm whether the rule must continue after launch or only explain past orders.               |
| ERP/PIM-owned pricing          | External authority and synchronization logic.                     | Confirm which system owns price updates after migration.                                       |

Trade policies are especially important because they can influence product availability, commercial rules, and sales-channel behavior. A product that looks correct in one context may be unavailable, differently priced, or differently promoted in another. Data-model review should therefore include representative channel, marketplace, B2B, and promotion examples when those areas affect the merchant’s business.

### Customers, B2B Context, and Master Data <a href="#customers-b2b-context-and-master-data" id="customers-b2b-context-and-master-data"></a>

Customer migration in VTEX should distinguish basic identity from operating context. Names, emails, phones, addresses, and order relationships may be standard customer information. Business accounts, buyer roles, approval flows, price access, external identifiers, consent values, segmentation, or custom forms may require B2B configuration, Master Data, app review, integration mapping, or Custom Service.

Master Data is important because some information does not belong naturally inside standard customer, product, order, CMS Page, or Blog Post fields. It may support custom records, forms, customer context, external-system references, operational workflows, or app behavior.

| Customer or business data   | Possible VTEX interpretation                                         | Migration implication                                                                      |
| --------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Basic customer profile      | Standard customer identity and address data.                         | Validate identity, address, and order relationship continuity.                             |
| B2B company or organization | B2B configuration, Master Data, app data, or custom structure.       | Confirm whether company-level meaning must be migrated, configured, or rebuilt.            |
| Buyer role or permission    | B2B rule, app behavior, Master Data, or external-system rule.        | Do not assume user permissions can move as simple customer fields.                         |
| Negotiated condition        | Price table, trade policy, external pricing, or custom rule.         | Validate access and pricing behavior by business context.                                  |
| Custom customer field       | Supported field, Master Data, app-owned data, or accepted exclusion. | Decide whether the field must be visible, searchable, reported, or sent to an integration. |

A merchant with B2B/B2C complexity should not validate only individual customer records. It should test whether customer context still supports ordering, pricing, visibility, reporting, and account-service workflows.

### Orders, OMS, Logistics, Sellers, and Marketplace Context <a href="#orders-oms-logistics-sellers-and-marketplace-context" id="orders-oms-logistics-sellers-and-marketplace-context"></a>

Historical order migration should preserve business readability. The goal is not to recreate live OMS workflow from old orders. The goal is to keep past transactions useful for customer service, finance, fulfillment review, reporting, and operational continuity.

| Order context      | Meaning to preserve                                                                                         | Validation focus                                                                 |
| ------------------ | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Direct store order | Customer, purchased items, totals, tax, payment label, shipping label, status, and fulfillment context.     | Confirm the order is readable and connected to the right customer and products.  |
| Marketplace order  | Marketplace origin, seller relationship, channel context, commission or fulfillment meaning where relevant. | Confirm marketplace meaning is not reduced to a generic note.                    |
| Seller order       | Seller identity, fulfillment responsibility, status, tracking, and back-office reference.                   | Confirm seller context remains visible or otherwise handled in the target model. |
| B2B order          | Business account, buyer, pricing context, approval or account information where relevant.                   | Confirm B2B meaning is not lost in order history.                                |
| Integrated order   | ERP, WMS, OMS, invoice, payment, marketplace, or external reference values.                                 | Confirm identifiers are migrated, mapped, excluded, or handled separately.       |

Live payment, shipping, logistics, tax, invoicing, pickup, delivery, fulfillment, marketplace, and seller workflows are target configuration and validation responsibilities. Historical orders can explain past transactions, but they do not prove live order operations are ready.

### Checkout, orderForm, Payment, Shipping, and Custom Fields <a href="#checkout-orderform-payment-shipping-and-custom-fields" id="checkout-orderform-payment-shipping-and-custom-fields"></a>

VTEX checkout behavior is closely tied to the orderForm. Depending on implementation, it can include cart items, customer profile, address, client preferences, shipping data, payment data, seller data, marketing data, coupons, and custom information.

Source checkout fields should be classified by purpose before migration scope is accepted.

| Custom checkout or operational value | Data-model question                                                       | Likely handling path                                                             |
| ------------------------------------ | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Display-only value                   | Must it appear for customer service or shopper review?                    | Supported field, order note, Master Data, or accepted exclusion.                 |
| Fulfillment value                    | Does warehouse, seller, or service team need it?                          | Order context, Master Data, integration field, or custom logic.                  |
| Reporting value                      | Does the business filter, export, or report on it?                        | Structured field, Master Data, or BI/integration handling.                       |
| Integration value                    | Does ERP, WMS, payment, anti-fraud, CRM, or marketplace logic require it? | External identifier mapping, API/integration handling, or Custom Service.        |
| Future checkout value                | Must it be collected again after launch?                                  | Target checkout configuration, app behavior, storefront work, or Custom Service. |

Historical payment and shipping labels should be separated from live provider setup. A migrated order can show a past payment method or shipping method, but live payment authorization, anti-fraud review, gift card behavior, shipping-rate logic, pickup, delivery, and fulfillment workflows still need target setup and testing.

### Storefront, Search, CMS Pages, Blog Posts, and URL Meaning <a href="#storefront-search-cms-pages-blog-posts-and-url-meaning" id="storefront-search-cms-pages-blog-posts-and-url-meaning"></a>

VTEX storefront meaning depends on the target storefront solution, search configuration, CMS approach, route strategy, and implementation decisions. Product and content records may migrate successfully while still failing storefront expectations if discovery, URLs, menus, images, filters, or page structure are not aligned with the new storefront.

| Storefront-related data | Migration meaning                                                                          | Review point                                                                                    |
| ----------------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------- |
| Product discovery       | Category hierarchy, brands, specifications, filters, search, and collections.              | Confirm migrated catalog data supports browsing and search.                                     |
| CMS Pages               | Static or campaign content that may need target CMS interpretation.                        | Confirm whether content migrates as structured pages, rebuilt content, or implementation scope. |
| Blog Posts              | Editorial content, metadata, author/date context, tags, and URL expectations.              | Confirm whether Blog Posts are part of migration scope and how they should display.             |
| Menus and navigation    | Storefront structure, department/category paths, content links, and merchandising choices. | Confirm navigation is target storefront work, migrated data, or a combination.                  |
| URLs and redirects      | SEO-sensitive paths, canonical expectations, landing pages, and priority redirects.        | Confirm high-value paths remain reachable and mapped to the right target destination.           |

Content migration should be planned around the selected VTEX storefront implementation. A source theme, page builder, or custom layout should not be treated as ordinary content data unless its target representation is defined.

### Apps, APIs, Master Data, and External-System Ownership <a href="#apps-apis-master-data-and-external-system-ownership" id="apps-apis-master-data-and-external-system-ownership"></a>

VTEX projects often depend on apps, APIs, Master Data, marketplace connectors, ERP, PIM, WMS, OMS, CRM, payment providers, anti-fraud providers, analytics tools, search systems, and custom middleware. These dependencies may own data that appears to be store content but actually functions as business logic.

| Dependency type                         | Typical data meaning                                                                           | Planning decision                                                                   |
| --------------------------------------- | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| VTEX app or storefront app              | App settings, merchandising, checkout behavior, search, storefront logic, or integration data. | Decide whether the app data migrates, is reconfigured, or is excluded.              |
| Master Data                             | Custom records, customer context, forms, operational references, or integration values.        | Decide whether supported mapping is enough or Custom Service is needed.             |
| ERP/PIM/WMS/OMS                         | Product, inventory, pricing, fulfillment, invoice, order, or synchronization authority.        | Confirm which system owns each value after migration.                               |
| Marketplace connector                   | Seller, offer, SKU matching, commission, channel, and synchronization data.                    | Decide whether marketplace context is migrated, configured, rebuilt, or integrated. |
| External payment or anti-fraud provider | Payment labels, risk status, gift card, or transaction context.                                | Separate historical order labels from live provider setup.                          |
| Custom API or middleware                | Custom workflows, data transformations, and external identifiers.                              | Review for Custom Service when ordinary mapping cannot preserve required behavior.  |

Add-ons can support mapping, filtering, value transformation, or supported configuration work when the requirement fits available service capability. Custom Service is the correct path when VTEX needs custom migration logic, unsupported structures, Custom Platform interpretation, or source-specific behavior that cannot be represented through normal mapping.

### Entity Points and VTEX Data Scope <a href="#entity-points-and-vtex-data-scope" id="entity-points-and-vtex-data-scope"></a>

Entity Points should be reviewed against actual migrated scope, not against platform complexity alone. A VTEX project may involve many decisions around specifications, trade policies, marketplace context, Master Data, integrations, and storefront behavior, but only eligible migrated records consume Entity Points according to the service license and Entity Points Plan.

New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when they are migrated for the first time, including when the customer performs a new migration for the same migration path.

This distinction matters in VTEX because some work is data migration, some work is target configuration, and some work is custom or integration planning. Entity Points clarify record scope, but they do not replace the need to classify complex VTEX data meaning.

### Data-Model Decision Matrix for VTEX <a href="#data-model-decision-matrix-for-vtex" id="data-model-decision-matrix-for-vtex"></a>

A practical VTEX data-model decision should test how each data area behaves after interpretation, not just whether it exists in the target environment.

| Decision area                  | Accept standard mapping when                                                                            | Consider Add-ons when                                                                  | Escalate to Custom Service when                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Product/SKU structure          | Source products, variants, categories, brands, images, and basic specifications map clearly.            | Field mapping, filtering, or value adjustments are needed within supported capability. | Product choices depend on custom configurators, unsupported structures, or source-specific logic.                       |
| Pricing and promotions         | Basic values and supported pricing context can be represented clearly.                                  | Rule-related data needs supported adjustments or selective handling.                   | Pricing depends on custom code, external authority, or unsupported channel/account logic.                               |
| Customers and B2B              | Customer identity and addresses fit supported customer migration scope.                                 | Selected custom fields or segments need supported mapping.                             | Company hierarchy, buyer permissions, negotiated rules, or app-owned data require custom interpretation.                |
| Orders and marketplace context | Historical orders remain readable with customer, product, total, payment, shipping, and status context. | Order fields or external references need supported adjustments.                        | Seller, marketplace, fulfillment, invoice, or integration meaning cannot be represented through standard order history. |
| Master Data and apps           | Data is not migration-critical or can be excluded safely.                                               | Supported custom field/value treatment is enough.                                      | Master Data, app-owned records, or custom APIs carry business-critical logic.                                           |
| Storefront and URLs            | CMS Pages, Blog Posts, and priority URLs have clear target representation.                              | Metadata, filtering, or structured content adjustment fits Add-ons.                    | Source layouts, page-builder structures, routing, or storefront behavior must be rebuilt.                               |

This matrix also helps define Demo Migration samples. The sample set should include difficult records from each major data area, not only clean products and customers.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX data-model planning should focus on preserving business meaning. Products must become usable products, SKUs, specifications, and discovery structures. Pricing must make sense across trade policies, sales channels, promotions, and account context. Orders must remain readable within OMS, seller, marketplace, and fulfillment history. Customers may need profile, B2B, Master Data, and integration interpretation. Storefront content, URLs, apps, APIs, and external systems may carry business logic that ordinary entity counts do not reveal.

A strong VTEX migration scope uses representative records to prove the hardest parts of the model before Full Migration. Complex products, SKU specifications, trade-policy pricing, seller or marketplace orders, B2B context, Master Data, custom checkout fields, integration identifiers, CMS Pages, Blog Posts, and priority URLs should be reviewed early enough to decide whether Standard Service is enough, Add-ons are appropriate, or Custom Service is required.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is product-to-SKU translation important in VTEX?**

VTEX separates product meaning from SKU meaning. A product describes the item, while the SKU represents the purchasable variation or physical unit. If source variants, options, or child products are mapped incorrectly, shoppers may see incomplete choices, wrong prices, inactive SKUs, or unreliable inventory behavior.

**Do source product attributes always become VTEX specifications?**

No. Some source attributes may become product specifications, SKU specifications, filters, descriptions, custom fields, app-owned data, Master Data, or excluded values. The correct treatment depends on whether the attribute affects discovery, purchase choices, operations, reporting, or integrations.

**How should source-store price rules be reviewed for VTEX?**

Price rules should be reviewed by commercial meaning. A simple default price is different from a value that depends on price tables, customer segment, B2B account, marketplace channel, promotion, coupon, or trade policy. Complex pricing may need mapping, value adjustment, target configuration, external-system planning, or Custom Service review.

**Are historical orders the same as VTEX OMS setup?**

No. Historical orders help preserve past transaction context, but OMS setup controls how new VTEX orders move through payment approval, invoicing, fulfillment, delivery, pickup, seller, marketplace, and integration workflows. Both should be validated separately.

**When does VTEX app, API, or Master Data information need Custom Service?**

Custom Service is required when app-owned data, Master Data, external-system identifiers, custom API behavior, marketplace connector logic, B2B structures, or unsupported third-party data cannot be represented through standard service capability or available Add-ons.
