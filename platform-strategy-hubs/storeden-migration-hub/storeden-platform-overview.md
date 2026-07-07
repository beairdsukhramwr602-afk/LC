# Storeden Platform Overview

Storeden, now positioned inside the TeamSystem Commerce environment, is best understood as a cloud commerce operating platform for merchants that need more than a simple storefront. Its migration significance comes from the combination of catalog management, product inventory, order handling, integrated payments, logistics, themes, apps, marketplace channels, API/developer resources, and TeamSystem ecosystem connections in one managed environment.

That combination changes how migration should be planned. Storeden is not only a place where Products, Customers, Orders, Categories, CMS content, and SEO values are copied. It is a target operating model where migrated records need to support catalog administration, stock control, storefront presentation, marketplace selling, payment and shipping configuration, logistics tracking, and possible connections to TeamSystem or other external business systems.

The strongest Storeden migration plan starts by separating three layers: data that can be migrated, platform behavior that must be configured, and business workflows that may need apps, integrations, or Custom Service review. This distinction prevents a common mistake: assuming that a successful record transfer automatically recreates the old store’s selling model.

### Storeden Migration Thesis <a href="#storeden-migration-thesis" id="storeden-migration-thesis"></a>

A migration to Storeden should be evaluated as a move into managed multichannel commerce. The target is not only a new storefront. It is a cloud environment where products, inventory, orders, payments, logistics, marketplaces, apps, and integrations may all influence how the store operates after launch.

For simpler stores, that can make Storeden a practical target because the business can move core commerce data into a managed system and configure the new store around current needs. For more complex stores, Storeden can still be a strong target, but the project needs clearer scoping. Product behavior, marketplace fields, app-owned data, B2B logic, external IDs, storefront content, and order-history expectations must be reviewed before they are treated as standard migration output.

| Migration question                              | Why it matters in Storeden                                                                                                               | Planning response                                                                       |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| What data must remain operational after launch? | Products, stock, orders, customers, categories, and content only matter if they support actual selling and management workflows.         | Identify the records that affect buying, fulfillment, customer service, and reporting.  |
| What behavior belongs to Storeden setup?        | Payments, logistics, marketplace connections, themes, apps, and some operational rules are configured in the target environment.         | Separate migrated history from target configuration and launch testing.                 |
| What behavior comes from external systems?      | ERP, accounting, marketplace, POS, logistics, inventory, and TeamSystem workflows may carry identifiers or rules outside the storefront. | Map ownership and decide whether migration, configuration, or Custom Service is needed. |
| What can be simplified?                         | A move into Storeden may be a chance to retire source-specific workarounds.                                                              | Preserve business meaning, not every old implementation detail.                         |

### What Changes When Moving to Storeden <a href="#what-changes-when-moving-to-storeden" id="what-changes-when-moving-to-storeden"></a>

Storeden changes the migration conversation because it concentrates commerce administration in a hosted environment. The target store can manage catalog data, inventory, storefront presentation, payments, shipping/logistics, orders, marketplace channels, apps, and integrations, but each of those areas has a different migration meaning.

Core records can be migrated into Storeden, while live behavior normally depends on target setup. A migrated product may exist in the catalog, but category placement, stock expectations, marketplace readiness, storefront visibility, and image display still need review. A migrated order may remain useful for customer service and finance, but that does not prove the new payment, shipping, and logistics workflow is ready for future orders.

| Area         | What Storeden changes                                                                                           | What should be validated                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Catalog      | Products become part of a managed catalog and inventory workflow.                                               | Product names, SKUs, descriptions, prices, images, categories, variants, attributes, stock, and visibility.              |
| Inventory    | Stock is not just a historical field; it affects availability and operational confidence.                       | Whether imported stock values, variants, and warehouse or logistics assumptions match target operations.                 |
| Orders       | Historical orders support service, finance, fulfillment reference, and management review.                       | Totals, customer context, payment labels, shipping labels, statuses, discounts, taxes, tracking, and marketplace origin. |
| Payments     | Integrated payment options and TS Pay-related setup belong to target configuration.                             | Whether payment labels in old orders are readable and whether live payment methods are configured separately.            |
| Logistics    | Shipping and tracking behavior can depend on target logistics configuration and carrier choices.                | Delivery methods, tracking expectations, fulfillment states, and post-launch order flow.                                 |
| Storefront   | Themes, navigation, content, and responsive display need target-side presentation work.                         | Product pages, category pages, menus, CMS pages, banners, images, metadata, and priority URLs.                           |
| Marketplaces | Marketplace selling may depend on channel-specific identifiers, categories, publication rules, and stock logic. | Amazon, eBay, Facebook, AliExpress, or other channel records that influence catalog and order workflows.                 |
| Integrations | TeamSystem ecosystem, API, ERP, accounting, inventory, and fulfillment workflows may own business meaning.      | External IDs, synchronization rules, app-owned records, reporting dependencies, and custom data.                         |

### Storeden as a Managed Commerce Environment <a href="#storeden-as-a-managed-commerce-environment" id="storeden-as-a-managed-commerce-environment"></a>

Storeden’s hosted model can reduce the need to maintain infrastructure, but it also limits the assumption that source implementation details can move unchanged. A self-hosted source store may rely on custom code, database tables, theme scripts, modules, or direct server behavior. Storeden expects those functions to be represented through platform configuration, apps, integrations, accepted changes, or reviewed custom handling.

This matters most when the source store has grown around operational shortcuts. A product field may actually drive marketplace publishing. A custom customer field may control B2B pricing. An order note may contain warehouse instructions. A plugin may own product-feed logic. A theme script may create a checkout experience that cannot be treated as data.

A good Storeden migration does not copy these behaviors blindly. It identifies which parts belong to migrated records, which parts belong to target setup, and which parts need a reviewed handling path.

### Catalog, Inventory, and Product Structure <a href="#catalog-inventory-and-product-structure" id="catalog-inventory-and-product-structure"></a>

The catalog is often the most important Storeden planning area because it affects storefront browsing, marketplace selling, inventory confidence, and operations. Products need to be reviewed not only as records, but as buying structures.

Simple products usually need names, descriptions, prices, SKUs, images, categories, visibility, stock, SEO values, and URLs reviewed. Variant or attribute-heavy products need deeper testing because option meaning may change when the source store’s product logic is represented in Storeden. Marketplace-aware products add another layer: channel identifiers, feed attributes, availability rules, and category requirements may matter as much as the storefront product page.

| Product structure              | Migration significance                                                              | Review focus                                                                                             |
| ------------------------------ | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Simple products                | Usually the easiest catalog records to interpret.                                   | Name, SKU, price, stock, images, description, category, status, SEO value.                               |
| Variant products               | Buying choices affect price, stock, SKU, image, and fulfillment.                    | Variant combinations, attribute names, stock values, images, and storefront selection behavior.          |
| Attribute-rich products        | Attributes may support filtering, comparison, marketplaces, or internal operations. | Which attributes must remain visible, searchable, mapped, or used by external systems.                   |
| Marketplace-ready products     | Channel publication may depend on identifiers and required fields.                  | Marketplace category, channel-specific fields, availability, product feed expectations, and stock rules. |
| Integration-sensitive products | ERP, inventory, accounting, or warehouse systems may depend on IDs or SKU logic.    | External IDs, SKU stability, stock synchronization, price ownership, and update workflow.                |

### Orders, Payments, Logistics, and Customer Context <a href="#orders-payments-logistics-and-customer-context" id="orders-payments-logistics-and-customer-context"></a>

Storeden order migration should distinguish between historical readability and live operational readiness. Historical orders need to remain useful for customer service, finance, fulfillment review, and management reporting. Live order behavior requires Storeden setup for payment, logistics, shipping, tax, tracking, notifications, and fulfillment workflow.

The difference is practical. A migrated order may show the original payment method and shipping method, but that does not configure the payment method for new purchases. A tracking value may be readable, but that does not prove the target logistics workflow is connected. A customer can be associated with old orders, but account access, customer segmentation, marketing consent, or B2B behavior may require separate target review.

| Record type       | What migration can preserve                                                                                                                 | What target setup must still prove                                                                                          |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Historical orders | Order number, products, totals, customer details, payment labels, shipping labels, statuses, discounts, taxes, notes, and tracking context. | New checkout, payment capture, shipping calculation, carrier/logistics behavior, notifications, and fulfillment processing. |
| Customers         | Contact details, account-related values, addresses, and order association where supported.                                                  | Login behavior, segmentation, B2B permissions, marketing tools, customer groups, or app-managed account logic.              |
| Payment context   | Historical payment method labels or transaction references where available.                                                                 | Active payment method configuration, TS Pay or other payment setup, testing, and reconciliation expectations.               |
| Logistics context | Historical shipping method, delivery information, tracking, or fulfillment labels.                                                          | Live shipping method setup, carrier connection, tracking updates, and operational workflow.                                 |

### Storefront, Content, SEO, and Channel Presentation <a href="#storefront-content-seo-and-channel-presentation" id="storefront-content-seo-and-channel-presentation"></a>

Storeden themes and storefront tools make the target store manageable, but storefront presentation should not be treated as a data-only task. Source themes, page-builder layouts, custom scripts, banners, menus, and navigation logic usually need target-side review. The migration can support product and content continuity, but the new store still needs a deliberate presentation plan.

SEO continuity is also part of this planning. Priority product URLs, category URLs, CMS pages, blog posts, metadata, redirects, image alt context, and internal links should be sampled before launch. Marketplace selling adds another presentation layer because channel product content may not be identical to storefront content.

| Presentation layer  | Common assumption                                    | Better Storeden planning view                                                                        |
| ------------------- | ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Theme               | The old design should move with the data.            | Theme setup, visual configuration, and content placement are separate from data migration.           |
| Navigation          | Categories will automatically recreate discovery.    | Category hierarchy, menu placement, filters, and product visibility must be checked together.        |
| CMS content         | Pages can be moved without layout review.            | Content should be checked for formatting, internal links, media, metadata, and target page behavior. |
| SEO                 | Product names and URLs are enough.                   | Priority URLs, slugs, titles, descriptions, redirects, and internal linking need launch validation.  |
| Marketplace content | Storefront product data is enough for every channel. | Channel-specific data may require mapping, cleanup, or post-migration configuration.                 |

### Apps, APIs, and TeamSystem Ecosystem Connections <a href="#apps-apis-and-teamsystem-ecosystem-connections" id="apps-apis-and-teamsystem-ecosystem-connections"></a>

Storeden’s app, plug-in, API, developer-resource, and TeamSystem ecosystem positioning makes integration planning important. Some connected workflows can be reconfigured after migration. Others may carry business-critical identifiers or data that must be scoped before migration begins.

Examples include ERP IDs, accounting references, POS links, warehouse item codes, marketplace listing identifiers, fulfillment service fields, invoice references, external customer IDs, and reporting tags. These values may not behave like standard commerce entities. When they are required for continuity, they should be reviewed as integration-sensitive data, not assumed to migrate automatically.

This is also where the boundary between Add-ons and Custom Service matters. Add-ons can support bounded filtering, mapping, configuration, or supported output adjustments. Custom Service is the review path for unsupported app data, plug-in data, API-owned records, custom fields, Custom Platform behavior, external IDs, bespoke transformations, or custom migration logic adjustment.

### Where Storeden Usually Fits Best <a href="#where-storeden-usually-fits-best" id="where-storeden-usually-fits-best"></a>

Storeden is often strongest when the merchant wants a managed cloud commerce platform with multichannel reach and practical operational support. It fits stores that want to reduce infrastructure burden while keeping serious attention on catalog management, inventory, orders, payments, logistics, marketplace channels, storefront presentation, apps, and business-system connections.

It is less straightforward when the source store depends on exact source-code preservation, unusual checkout logic, unsupported app records, complex custom product builders, undocumented marketplace automation, or external-system behavior that has not been mapped.

| Strong Storeden fit                         | Why it works                                                                         | What still needs planning                                                                                 |
| ------------------------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Merchant moving into hosted commerce        | The business wants managed infrastructure and a centralized commerce environment.    | Source custom logic must be translated into Storeden setup, apps, integrations, or reviewed custom scope. |
| Catalog and inventory-led retailer          | Storeden’s catalog and inventory emphasis aligns with product administration needs.  | Variants, attributes, categories, marketplace fields, stock, and SKU logic need representative testing.   |
| Multichannel seller                         | Storeden’s marketplace and channel positioning supports store-plus-channel planning. | Marketplace identifiers, feeds, category rules, and order origin must be reviewed.                        |
| TeamSystem-connected business               | Storeden can sit near TeamSystem ecosystem workflows.                                | External IDs, accounting, ERP, payment, logistics, and reporting dependencies must be mapped.             |
| Merchant rebuilding storefront presentation | Themes and content tools can support a clean target storefront.                      | Old design behavior, page layouts, internal links, and SEO continuity need target validation.             |

### Conclusion <a href="#conclusion" id="conclusion"></a>

A Storeden migration should be planned as a move into TeamSystem Commerce’s managed, multichannel operating environment. The central question is not whether records can be moved into a new store. The central question is whether the migrated records, target configuration, apps, marketplace connections, payment setup, logistics workflow, storefront presentation, and external-system dependencies will support the business after launch.

Storeden is a strong target when a merchant wants hosted commerce, structured catalog and inventory management, multichannel selling, order management, payment and logistics configuration, themes, apps, and ecosystem connections. It needs deeper planning when the source store depends on custom code, source-only product logic, app-owned data, marketplace automation, integration-sensitive IDs, B2B rules, or exact design preservation.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Storeden mainly a storefront platform or an operating platform?**

Storeden should be treated as an operating platform. The storefront matters, but migration planning also needs catalog, inventory, orders, payments, logistics, marketplaces, apps, and external-system connections.

**Does Storeden migration include payment and logistics setup?**

Migrated records may preserve payment and shipping context from historical data, but live payment, shipping, logistics, tax, and fulfillment behavior must be configured and tested in Storeden.

**Can marketplace data be treated as ordinary product data?**

Not always. Marketplace selling can depend on listing identifiers, channel categories, required fields, product-feed rules, availability logic, and order-origin context. These should be reviewed separately from ordinary storefront product fields.

**When does a Storeden migration need Custom Service review?**

Custom Service should be reviewed when unsupported app data, plug-in data, API-owned records, custom fields, Custom Platform behavior, external IDs, bespoke transformations, or custom migration logic adjustment carry business value.

**What is the most important Storeden readiness signal?**

The strongest signal is that representative products, customer records, orders, content, marketplace cases, integration-sensitive fields, and priority URLs can be validated in the target store without relying on unsupported assumptions.
