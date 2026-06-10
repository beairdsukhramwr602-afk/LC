# VTEX Constraints and Risks

VTEX is a hosted enterprise SaaS commerce platform with a broad operating model. Migration risk usually appears when a source store is treated as a simple product, customer, and order transfer while the target environment depends on SKU structure, specifications, trade policies, pricing logic, Checkout behavior, OMS flows, marketplace roles, apps, APIs, Master Data, and external integrations.

A successful migration to VTEX depends on identifying which parts of the source store can be represented through standard VTEX structures, which parts must be configured in the target environment, and which parts require deeper mapping, accepted exclusions, or Custom Service review.

### Where Risk Concentrates in a VTEX Migration <a href="#where-risk-concentrates-in-a-vtex-migration" id="where-risk-concentrates-in-a-vtex-migration"></a>

VTEX risk is rarely limited to record counts. The same number of products or orders can produce very different migration complexity depending on how those records depend on SKUs, specifications, pricing rules, seller relationships, storefront behavior, and connected systems.

| Risk area                           | Why it matters in VTEX                                                                                                                                     | Earliest review priority                                                                                                              |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Product and SKU structure           | VTEX separates product identity from SKU-level sellable items, which can differ from simpler source catalog models.                                        | Review complex products, variants, SKUs, attachments, kits, services, and catalog examples before Full Migration.                     |
| Specifications and attributes       | Product and SKU specifications can drive catalog filtering, search, comparison, product presentation, and operational classification.                      | Confirm which source attributes become product specifications, SKU specifications, or accepted non-migrated details.                  |
| Pricing and trade policies          | Price tables, trade policies, promotions, sales channels, and customer segments can change how prices are interpreted.                                     | Separate migrated price data from target pricing configuration and commercial policy setup.                                           |
| Checkout and order behavior         | VTEX Checkout and `orderForm`behavior depend on target configuration, payment, shipping, promotions, customer data, and sales-channel context.             | Treat historical order readability and live checkout readiness as separate review areas.                                              |
| OMS and order flows                 | VTEX order status, fulfillment, invoicing, cancellation, and marketplace/seller workflows may not match the source platform directly.                      | Validate representative orders across statuses, fulfillment scenarios, and sales-channel origins.                                     |
| Marketplace and seller architecture | VTEX can involve marketplace, seller, and franchise-account relationships that carry operational meaning beyond ordinary orders.                           | Identify seller roles, marketplace order origin, seller SKUs, commissions, fulfillment responsibility, and external references early. |
| Master Data and customer context    | Customer, address, B2B, account, organization, and custom records may be distributed across commerce and Master Data structures.                           | Identify which customer-related data is core commerce data and which depends on Master Data, custom schemas, or integrations.         |
| Apps, APIs, and integrations        | VTEX projects often depend on apps, API workflows, ERP, PIM, WMS, OMS, CRM, payment, tax, and middleware systems.                                          | Inventory integration-owned fields, identifiers, automation rules, and records before defining scope.                                 |
| Storefront, search, CMS, and SEO    | FastStore, Store Framework, Legacy CMS Portal, Intelligent Search, menus, routes, content, redirects, and metadata can affect perceived migration quality. | Confirm target storefront architecture and SEO-sensitive URLs before acceptance criteria are set.                                     |

### Hosted SaaS Boundaries <a href="#hosted-saas-boundaries" id="hosted-saas-boundaries"></a>

VTEX’s hosted SaaS model changes how source-store behavior should be interpreted. A source platform may expose database tables, custom code, server-side modules, custom checkout logic, or theme-layer behavior that cannot be moved as-is into VTEX.

The constraint is not only technical access. It is also operational fit. A custom database relationship in the source store may need to become a VTEX catalog structure, Master Data record, app behavior, external integration, or Custom Service requirement. Custom code that previously changed checkout, pricing, shipping, customer segmentation, or fulfillment behavior should not be treated as ordinary data.

Merchants with heavily customized source platforms should identify which business outcomes must continue after migration. The migration plan should then separate supported VTEX structures, target configuration, integration work, and customization needs.

### Product, SKU, and Specification Constraints <a href="#product-sku-and-specification-constraints" id="product-sku-and-specification-constraints"></a>

VTEX catalog planning depends heavily on the relationship between products, SKUs, brands, categories, specifications, attachments, services, kits, and collections. A source store with simple variants may migrate differently from a source store where attributes drive pricing, search filters, compatibility, bundling, configuration, or marketplace publication.

#### Product-to-SKU translation risk <a href="#product-to-sku-translation-risk" id="product-to-sku-translation-risk"></a>

A common risk is assuming that source variants automatically become correct VTEX SKUs. VTEX expects the sellable item to be represented clearly at SKU level. Product-level identity, SKU-level options, stock, price, images, specifications, and fulfillment behavior should be reviewed together.

Risk increases when the source platform uses configurable products, custom option logic, product bundles, grouped products, subscription logic, service add-ons, personalization fields, or non-standard attribute relationships. These cases need representative Demo Migration samples before the merchant accepts the target catalog model.

#### Specification and filtering risk <a href="#specification-and-filtering-risk" id="specification-and-filtering-risk"></a>

Specifications can influence product presentation, navigation, filtering, search relevance, comparison, and operational classification. If source attributes are flattened, omitted, or mapped to the wrong level, the catalog may appear migrated but lose practical shopping or management value.

A strong review should confirm whether key attributes belong at product level, SKU level, filter level, search level, content level, or integration level. When attribute transformation requires custom mapping beyond standard behavior, the requirement belongs in Custom Service review.

### Pricing, Promotions, and Trade Policy Constraints <a href="#pricing-promotions-and-trade-policy-constraints" id="pricing-promotions-and-trade-policy-constraints"></a>

VTEX can represent pricing through structures that may be more complex than the source store’s default price fields. Price tables, list prices, promotional logic, trade policies, sales channels, seller arrangements, and customer-segment behavior can all affect what shoppers see and what orders record.

Historical price values and live pricing behavior should be separated. A migrated product price does not prove that trade policies, customer-specific price rules, marketplace prices, campaign behavior, or B2B pricing logic are ready.

| Pricing-related item | Risk if ignored                                                                                                  | Mitigation                                                                                       |
| -------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Price tables         | Source pricing may not align with target price-table logic.                                                      | Prepare samples for base price, sale price, customer-specific price, and channel-specific price. |
| Trade policies       | A price or catalog item may behave differently by sales channel or commercial policy.                            | Confirm which trade policies govern each major selling scenario.                                 |
| Promotions           | Discounts, coupons, campaigns, and conditions may require target configuration rather than migration as history. | Separate historical discount labels from active promotion setup.                                 |
| B2B pricing          | Customer-group, organization, or negotiated pricing can depend on external rules or Master Data.                 | Review B2B pricing requirements before treating the project as a standard catalog migration.     |
| Marketplace pricing  | Seller or marketplace price logic may not follow the same source rules.                                          | Include marketplace examples in Demo Migration and integration review.                           |

### Checkout and OMS Constraints <a href="#checkout-and-oms-constraints" id="checkout-and-oms-constraints"></a>

VTEX Checkout and OMS behavior should not be reduced to historical order migration. Checkout readiness involves cart behavior, payment methods, shipping options, promotions, customer data, sales-channel context, tax behavior, and storefront integration. OMS readiness involves statuses, fulfillment, invoicing, cancellation, returns, marketplace context, and integration triggers.

#### Historical orders are not live checkout proof <a href="#historical-orders-are-not-live-checkout-proof" id="historical-orders-are-not-live-checkout-proof"></a>

A migrated order history can show customers, products, totals, discounts, payments, shipping labels, taxes, statuses, and fulfillment context. It does not prove that new orders will flow correctly through Checkout and OMS.

Live checkout behavior should be tested separately in the target environment. This is especially important when the source store uses custom checkout fields, unusual payment rules, shipping restrictions, tax logic, store pickup, split fulfillment, marketplace-originated orders, or B2B purchasing flows.

#### OMS flow mismatch <a href="#oms-flow-mismatch" id="oms-flow-mismatch"></a>

Order statuses rarely translate perfectly between platforms. A source order status may combine payment, fulfillment, cancellation, fraud review, invoicing, or marketplace state in one label. VTEX may represent those states differently inside OMS and connected workflows.

Validation should focus on whether the migrated order remains understandable to customer service, fulfillment, finance, and management teams. If order behavior must trigger external systems, the integration logic should be reviewed before launch.

### Marketplace, Seller, and Multichannel Constraints <a href="#marketplace-seller-and-multichannel-constraints" id="marketplace-seller-and-multichannel-constraints"></a>

VTEX can support marketplace and seller models that carry more complexity than a single-store catalog. Migration risk increases when products, SKUs, orders, prices, stock, commissions, fulfillment responsibility, or customer communication depend on marketplace roles.

A seller SKU is not always the same as a marketplace product record. A marketplace order may need seller context, fulfillment responsibility, payment breakdown, shipping arrangement, commission logic, and external references. If these details are flattened into ordinary products and orders, the target store may lose operational meaning.

Projects involving marketplace architecture should identify the intended target model before migration. The plan should distinguish first-party commerce, marketplace operator behavior, seller participation, external marketplace channels, and connected integration workflows.

### Master Data, Customer, and B2B Constraints <a href="#master-data-customer-and-b2b-constraints" id="master-data-customer-and-b2b-constraints"></a>

Customer-related data in VTEX can involve commerce profiles, addresses, organizations, cost centers, approval rules, customer clusters, segmentation, and Master Data records. B2B or account-based selling can add more dependency on organizational structure than ordinary customer migration.

Risk increases when the source store has customer groups, company accounts, tax IDs, role-based purchasing, quote workflows, purchase limits, negotiated terms, custom customer fields, CRM references, or external account IDs. These details should not be assumed to fit ordinary customer fields.

| Customer-related data       | Constraint                                                                                            | Review action                                                                                         |
| --------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Customer profiles           | Names, emails, addresses, and contact records may be simpler than the target business model requires. | Validate ordinary customer records and address behavior first.                                        |
| Customer groups or segments | Source customer groups may not equal VTEX customer clusters or B2B structures.                        | Decide whether the segment should become configuration, Master Data, or integration-managed behavior. |
| Company accounts            | B2B buyers may require organization, role, tax, approval, or purchasing rules.                        | Review B2B requirements before finalizing migration scope.                                            |
| Custom fields               | Source customer fields may not have a direct target field.                                            | Map supported fields; route custom structures to Custom Service review.                               |
| External IDs                | CRM, ERP, tax, loyalty, or accounting references may be required after launch.                        | Preserve or map external identifiers when they support operational continuity.                        |

### App, API, and Integration Constraints <a href="#app-api-and-integration-constraints" id="app-api-and-integration-constraints"></a>

VTEX projects often depend on apps, APIs, middleware, ERP, PIM, WMS, tax services, payment providers, shipping services, CRM systems, and marketplace connectors. These systems may own data or behavior that appears inside the storefront but does not belong to standard product, customer, or order records.

Migration planning should identify which system owns each important field. For example, product enrichment may come from a PIM, inventory may come from WMS, customer terms may come from ERP, promotions may come from VTEX configuration, and order routing may depend on integration middleware.

When app-owned, API-owned, or integration-owned data must be preserved, transformed, or reconnected, the requirement should be reviewed for Custom Service. Standard migration should not be expected to reproduce external automation or third-party workflow logic without explicit planning.

### Storefront, Search, CMS, and SEO Constraints <a href="#storefront-search-cms-and-seo-constraints" id="storefront-search-cms-and-seo-constraints"></a>

VTEX storefront planning can involve FastStore, Store Framework, Legacy CMS Portal, headless implementations, search configuration, menus, content, landing pages, product listing pages, redirects, metadata, analytics, and domain behavior. Product and order data may migrate correctly while storefront continuity still requires separate planning.

SEO and storefront risk is highest when the source store has valuable organic traffic, complex category routes, editorial landing pages, custom product URLs, international paths, marketplace landing pages, or custom frontend behavior. These elements should be reviewed before Full Migration acceptance criteria are defined.

A migration plan should distinguish data migration from storefront implementation. Product records, CMS Pages, Blog Posts, metadata, images, redirects, menus, and theme behavior should each have separate acceptance expectations.

### When Risk Increases Enough for Custom Service Review <a href="#when-risk-increases-enough-for-custom-service-review" id="when-risk-increases-enough-for-custom-service-review"></a>

Custom Service review is appropriate when the migration needs customization, modification, bespoke mapping, unsupported data handling, or custom migration logic adjustment. In VTEX projects, that often appears when the source store depends on custom product relationships, non-standard SKUs, complex specifications, advanced B2B structures, marketplace/seller records, app-owned data, Master Data schemas, API-owned workflows, or external-system identifiers.

Add-ons can help when the requirement fits supported filtering, mapping, or data configuration behavior. For example, the Data Filter Add-on can support selected-record migration where appropriate, Advanced Data Mapping can support supported mapping adjustments, and Advanced Data Configure can support supported data-value changes. Tailored Add-ons, Custom Add-ons, and Add-on modification are handled through Custom Service because customization is required.

The key decision is whether the requirement is a supported adjustment or a custom migration behavior. Supported filtering, mapping, or configuration can stay within Add-on review. Bespoke structures, unsupported app data, external workflow reconstruction, or target behavior that requires migration logic adjustment should move into Custom Service review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX migration risk is highest when enterprise commerce behavior is mistaken for ordinary record movement. Products, SKUs, specifications, prices, trade policies, Checkout, OMS, marketplace roles, Master Data, apps, APIs, integrations, storefronts, and SEO each influence whether the migrated result is useful after launch.

Before committing to Full Migration, review the areas where the source store carries operational meaning beyond standard records. A focused Demo Migration should include complex catalog items, varied orders, customer and B2B examples, marketplace or seller samples, SEO-sensitive URLs, and integration-sensitive records so the merchant can identify whether standard migration, Add-ons, or Custom Service review is the right path.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the biggest constraint in a VTEX migration?**

The biggest constraint is usually not the number of records. It is how product, SKU, pricing, trade policy, Checkout, OMS, marketplace, Master Data, app, API, and integration behavior must be represented inside VTEX.

**Why do SKUs require special review in VTEX?**

VTEX relies on clear product and SKU structure for sellable items. If source variants, options, attributes, bundles, or configurable products do not translate cleanly, the catalog may appear complete but fail to support real selling, filtering, stock, or pricing behavior.

**Does migrating historical orders prove VTEX Checkout is ready?**

No. Historical order migration and live checkout readiness are separate. Checkout behavior depends on target configuration, payment methods, shipping rules, promotions, customer context, sales channels, and storefront integration.

**When should marketplace or seller data be reviewed separately?**

Marketplace or seller data should be reviewed separately when product listings, seller SKUs, fulfillment responsibility, commissions, marketplace order origin, inventory, or external references affect operations after launch.

**When should a VTEX migration move into Custom Service review?**

Custom Service review is appropriate when the project requires custom migration logic adjustment, unsupported app or integration data, complex B2B structures, non-standard SKU transformation, marketplace/seller-specific handling, Master Data customization, or preservation of external-system workflows.
