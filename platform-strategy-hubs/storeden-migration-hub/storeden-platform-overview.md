# Storeden Platform Overview

Storeden is a hosted cloud e-commerce platform in the TeamSystem Commerce environment. It is built for merchants that need to manage catalog data, inventory, orders, storefront presentation, payments, logistics, apps, marketplace channels, and business-system connections from a managed commerce platform.

A migration to Storeden should be planned around how the new store will operate after launch. Product structure, variants, attributes, categories, stock, customers, orders, payment context, shipping context, storefront content, SEO values, marketplace data, apps, APIs, and external-system references all need to work inside Storeden’s hosted model.

The main planning question is whether the current store’s commercial behavior can be represented cleanly in Storeden. Straightforward products, customers, orders, and content may fit standard target structures, while custom product logic, marketplace-specific fields, app-owned data, ERP references, or unusual checkout behavior may need configuration, mapping, accepted exclusions, or Custom Service review.

### What Changes in a Migration to Storeden

Moving into Storeden changes how commerce data is managed, connected, and validated. The new store runs in a hosted environment, so migration planning should separate migrated records from target configuration, app behavior, channel setup, theme work, and integration logic.

| Migration area                | What changes in Storeden                                                                                                                        | Planning implication                                                                                               |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Hosted commerce operation     | Store data moves into a cloud commerce environment with platform-managed catalog, order, storefront, channel, and integration structures.       | Custom code or database behavior should be reviewed before it is treated as ordinary commerce data.                |
| Catalog and inventory         | Products may depend on categories, variants, attributes, SKUs, stock, pricing, images, visibility, and marketplace readiness.                   | Demo Migration samples should include complex products, not only simple catalog records.                           |
| Variants and attributes       | Options, modifiers, configurable products, or custom product fields may need different target handling.                                         | Buying choices should be checked from the storefront and from any important sales channel.                         |
| Orders and fulfillment        | Orders may include products, totals, customer context, payment labels, shipping methods, tracking, marketplace origin, and external references. | Historical order readability should be reviewed separately from live order workflow setup.                         |
| Payments, shipping, and tax   | Payment availability, TS Pay usage, logistics, tax behavior, and tracking depend on target configuration.                                       | Migrated historical labels do not automatically configure live checkout, payment, shipping, or logistics behavior. |
| Themes and storefront content | Storefront presentation depends on themes, page content, menus, banners, domain choices, and visual configuration.                              | Design and content continuity may require separate theme or content work.                                          |
| Apps and plugins              | Apps may support marketing, logistics, marketplaces, reporting, catalog behavior, or checkout-related workflows.                                | App-owned data should be identified before scope is finalized.                                                     |
| Marketplace channels          | Marketplace data can include channel-specific fields, product identifiers, availability rules, and synchronization expectations.                | Amazon, eBay, Facebook, AliExpress, or other channel records should be reviewed when they affect operations.       |
| API and business systems      | ERP, accounting, inventory, fulfillment, and TeamSystem ecosystem connections may depend on stable identifiers or workflow logic.               | Integration-sensitive data may need mapping, reconfiguration, or Custom Service review.                            |
| SEO and domains               | URL continuity, metadata, redirects, page names, category paths, and domain behavior affect launch quality.                                     | SEO-sensitive stores should prepare priority URL and metadata samples before migration acceptance.                 |

### Where Storeden Is Often a Strong Target

Storeden is often a strong target for merchants that want hosted commerce with multichannel selling, practical catalog control, order management, payment options, storefront themes, apps, and integration possibilities. It can be especially relevant when the business wants a cloud commerce environment connected to marketplaces, logistics, ERP, accounting, inventory, or TeamSystem workflows.

#### Merchants that want hosted commerce operations

Storeden can fit merchants that want to reduce responsibility for server maintenance, platform hosting, and low-level infrastructure work. The hosted model shifts attention toward catalog structure, storefront configuration, marketplace setup, payment and logistics choices, and post-migration validation.

This fit is strongest when the current store does not depend heavily on custom server-side behavior or unsupported database structures. If custom logic affects products, orders, checkout, marketplace data, or external systems, that logic should be reviewed before migration scope is finalized.

#### Catalogs that depend on inventory and product structure

Storeden can be a good target for merchants with structured product catalogs, categories, stock management needs, variant products, product attributes, images, and marketplace-aware selling requirements. The migration should preserve how the catalog is understood by shoppers, managers, and connected systems.

Product planning should include records where variants, attributes, SKUs, stock, pricing, category placement, images, shipping, or marketplace publication affect selling. These cases are more useful than simple products when judging the target migration result.

#### Sellers that use marketplaces and connected workflows

Storeden can support merchants that sell through more than one channel or depend on external business systems. Marketplace listings, logistics services, apps, APIs, ERP connections, accounting systems, warehouse tools, and TeamSystem ecosystem workflows can all influence the new store’s operating model.

These connections should be treated as migration scope questions. Product, customer, and order records may move into Storeden, while marketplace identifiers, external-system references, app-owned records, and automation rules may require separate mapping, reconfiguration, or Custom Service review.

#### Teams that want storefront flexibility without a custom stack

Storeden themes and storefront tools can support merchants that want a branded store without building and maintaining a fully custom commerce platform. This can work well when the target design can be achieved through theme work, content setup, navigation planning, and platform configuration.

Stores with highly customized frontend behavior, unusual checkout flows, or implementation-specific theme logic should confirm whether those expectations belong to Storeden theme setup, apps, custom development, or accepted launch changes.

### Where Deeper Planning Is Usually Needed

Deeper planning is usually needed when the current store does more than hold standard products, customers, orders, and pages. Storeden complexity often concentrates around product structure, marketplace selling, integrations, checkout behavior, external IDs, apps, themes, domains, and SEO continuity.

#### Product variants, attributes, and marketplace-ready catalog data

Product options may not carry the same meaning in Storeden. A variant, modifier, configurable option, attribute, custom field, or marketplace-specific field may need a different target structure or separate handling.

Catalog review should include products that affect price, stock, SKU, image, category assignment, shipping, marketplace publication, or inventory synchronization. These records reveal whether the target catalog can support real buying and operational behavior.

#### Orders, payments, shipping, and tracking

Historical orders can carry payment labels, shipping methods, tracking information, customer details, order statuses, marketplace origin, and external-system references. These values may remain important for customer service, fulfillment, finance, and management after migration.

Live payment, TS Pay, shipping, logistics, tax, and tracking behavior still need target setup and testing. A readable order history does not prove that the new Storeden checkout and fulfillment workflow is ready for new orders.

#### Apps, plugins, ERP connections, and TeamSystem workflows

Apps and connected business systems can carry business meaning outside ordinary commerce records. This matters when product availability, pricing, invoicing, warehouse operations, fulfillment, accounting, reporting, or marketplace publication depends on an external system.

If ERP, accounting, fulfillment, marketplace, inventory, or TeamSystem-related dependencies affect daily operations, migration scope should identify which data is migrated, which behavior is reconfigured, and which requirements need Custom Service review.

#### Themes, URLs, domains, and SEO continuity

Storeden storefront presentation depends on theme behavior, content, navigation, domains, images, metadata, redirects, and page structure. A migration can move product and order data successfully while the new store still needs separate attention to SEO and storefront continuity.

SEO-sensitive stores should prepare priority product URLs, category URLs, marketplace landing paths, metadata, redirects, and domain expectations before launch planning moves too far.

### What Should Be Understood Early Before Moving into Storeden

Merchants should understand the difference between data that migrates, behavior that must be configured, and workflows that depend on apps or external systems. This distinction is especially important for a hosted commerce platform with marketplace and business-system connections.

The following points should be clear before migration scope is finalized:

* Storeden is a hosted Target Platform, so custom logic should be translated into supported structures, configuration, apps, integrations, or Custom Service scope.
* Product variants, attributes, SKUs, stock, category placement, images, and marketplace fields should be sampled when they affect selling.
* Orders should be reviewed for payment, shipping, tracking, marketplace, customer, tax, status, and external-reference context.
* Live checkout, payment, TS Pay, tax, logistics, shipping, and tracking behavior require target setup and testing separate from order-history migration.
* Apps, plugins, APIs, ERP systems, accounting tools, inventory systems, and marketplace connections may create mapping or reconfiguration work.
* Storefront design, themes, domains, URLs, redirects, and SEO values should be planned before launch acceptance.
* Demo Migration should include complex catalog, order, channel, and integration examples, not only simple records.

### Conclusion

Storeden can be a strong Target Platform for merchants that want hosted commerce with catalog control, inventory management, order handling, storefront themes, payment options, marketplace selling, apps, and integration possibilities. Migration planning should focus on how the current store’s business meaning will work inside Storeden’s hosted commerce model.

Before moving forward, review the records and workflows that carry the most commercial value: complex products, marketplace listings, important categories, orders with shipping and payment context, ERP or accounting references, connected apps, priority URLs, and storefront content. A focused Demo Migration can show whether the migration path is straightforward or whether Add-ons, mapping, configuration, or Custom Service review should be planned before Full Migration.

### FAQs

**Is Storeden a hosted or self-hosted platform?**

Storeden is a hosted cloud e-commerce platform. Migration planning should focus on how store data fits Storeden’s supported catalog, order, payment, shipping, storefront, app, marketplace, and integration structures.

**Is Storeden the same as TeamSystem Commerce?**

Storeden operates within the TeamSystem Commerce environment. For migration planning, the important point is that Storeden should be treated as a hosted commerce Target Platform with TeamSystem ecosystem connections, marketplace channels, apps, APIs, themes, and integration considerations.

**What makes Storeden different from a simple catalog target?**

Storeden migration planning may involve catalog and inventory data, variants, attributes, marketplace fields, orders, payments, logistics, themes, apps, APIs, ERP references, and external workflows. A clean migration should preserve business meaning, not only product names and prices.

**Do marketplace listings migrate automatically into Storeden?**

Marketplace data should be reviewed separately. Product records may migrate into Storeden, but channel-specific fields, identifiers, availability rules, and synchronization behavior may require mapping, reconfiguration, accepted exclusions, or Custom Service review.

**What should be sampled in a Storeden Demo Migration?**

A strong Demo Migration sample should include complex products, variants, attributes, categories, stock-sensitive records, marketplace-relevant items, varied orders, payment and shipping context, priority URLs, app-dependent records, and ERP or external-system references where they matter.
