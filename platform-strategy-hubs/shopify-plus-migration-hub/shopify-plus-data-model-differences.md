# Shopify Plus Data Model Differences

Shopify Plus data modeling starts with the Shopify data foundation, then adds enterprise operating meaning around organization structure, B2B, Markets, multiple stores, integrations, permissions, and workflow ownership. Products, variants, collections, customers, orders, pages, Blog Posts, redirects, metafields, and apps remain central. The Plus-level difference is that many of those records may carry more business meaning than they would in a single-store Shopify migration.

That distinction matters because enterprise Source Platforms often store commerce logic in structures that do not translate cleanly into ordinary Shopify records. A Magento or Adobe Commerce source may use customer groups, websites, stores, store views, product attributes, price rules, shared catalogs, B2B accounts, and extension-owned data. A Custom Platform may use proprietary tables, ERP identifiers, custom checkout rules, role-based buyer permissions, or regional catalogs. Shopify Plus can support many enterprise outcomes, but migration planning must decide whether each source structure should become Shopify data, Shopify Plus setup, app configuration, Add-ons scope, Custom Service scope, or a redesigned target workflow.

### Shopify Plus Uses Shopify Data With Enterprise Governance <a href="#shopify-plus-uses-shopify-data-with-enterprise-governance" id="shopify-plus-uses-shopify-data-with-enterprise-governance"></a>

Shopify Plus is not a separate data platform detached from Shopify. The core data still follows Shopify concepts: products contain variants, collections group products, customers and orders hold buyer and transaction history, pages and Blog Posts support content, redirects help traffic continuity, and metafields or metaobjects extend structured information. Migration planning should therefore preserve the Shopify model rather than inventing a custom enterprise model inside Shopify Plus.

The enterprise layer changes how that model is governed. A product may need to support several markets, multiple storefronts, B2B availability, ERP SKU continuity, custom metafields, or app-managed merchandising. A customer may need to be separated from a company account, buyer role, location, payment term, or regional sales structure. A storefront may be one store using Markets or one of several expansion stores under an organization. These decisions are not cosmetic; they define how migrated data will be used after launch.

| Data area                  | Core Shopify meaning                             | Shopify Plus migration meaning                                                                                      |
| -------------------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Products and variants      | Sellable catalog structure.                      | Enterprise SKU logic, B2B availability, market-specific merchandising, ERP references, and product data governance. |
| Collections                | Product grouping for browsing and merchandising. | Regional, brand, channel, B2B, and campaign segmentation decisions.                                                 |
| Customers                  | Buyer profiles and order history.                | D2C buyers, B2B contacts, company relationships, buyer roles, and account ownership.                                |
| Orders                     | Historical transaction context.                  | Support, reconciliation, B2B order review, payment terms, fulfillment evidence, and integration reference value.    |
| Metafields and metaobjects | Structured custom data extensions.               | Product enrichment, content models, integration identifiers, B2B attributes, and enterprise operational context.    |
| Stores and organization    | Admin and storefront environments.               | Expansion stores, governance, permissions, security, billing, and validation ownership.                             |

The migration should not flatten these differences into simple record transfer. It should define the target meaning of every enterprise-critical source structure.

### Products, Variants, and Enterprise Catalog Meaning <a href="#products-variants-and-enterprise-catalog-meaning" id="products-variants-and-enterprise-catalog-meaning"></a>

Shopify products and variants remain the first catalog review layer. Source products with sizes, colors, units, bundles, kits, configurable options, subscription choices, or ERP-driven SKUs need to be interpreted against Shopify’s product and variant structure. Shopify Plus does not remove the need to make those decisions; it raises the stakes because catalog data may support more brands, markets, B2B catalogs, storefronts, and external systems.

A simple D2C catalog may migrate into products and variants with little additional interpretation. An enterprise catalog often requires deeper classification. Source attributes may be descriptive content, searchable specifications, variant-defining options, filter inputs, ERP identifiers, B2B eligibility markers, market-specific values, or app-owned logic. Treating all attributes as ordinary descriptions can weaken merchandising, search, integrations, and validation.

| Source catalog pattern                             | Shopify Plus planning question                                                                          |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Configurable product with many source attributes   | Which attributes define Shopify variants, which become metafields, and which should remain external?    |
| Source customer-group product visibility           | Should visibility be handled through B2B catalogs, store separation, apps, or custom handling?          |
| Regional product names or descriptions             | Should the target use Markets/localization, separate stores, translation workflows, or content rebuild? |
| ERP SKU or product ID                              | Should the identifier be preserved as SKU, metafield, app data, or integration reference?               |
| Bundle, kit, subscription, or configurable package | Should it use Shopify/app setup, Custom Service review, or manual target configuration?                 |
| Enterprise product enrichment                      | Should structured data become metafields, metaobjects, app data, or theme/content setup?                |

Product migration is strongest when each source field has a clear target purpose. The goal is not to force every enterprise source field into Shopify’s native product form. The goal is to preserve the information that must remain usable in the Shopify Plus operating model.

### Collections, Navigation, and Storefront Segmentation <a href="#collections-navigation-and-storefront-segmentation" id="collections-navigation-and-storefront-segmentation"></a>

Collections are not the same as every source platform’s categories. Some Source Platforms use categories as database hierarchy, storefront navigation, merchandising pages, SEO landing pages, reporting groups, or access-control structures. Shopify collections can support product grouping and storefront merchandising, but the migration plan should decide whether each source grouping should become a Shopify collection, navigation item, page, redirect target, market-specific experience, B2B catalog rule, or excluded historical structure.

Shopify Plus adds segmentation questions. A merchant may operate separate stores for brands or regions. Another merchant may use one store with Markets and localized content. A B2B merchant may need product availability by company or catalog rather than by public collection alone. These target choices affect how category and collection data should be prepared.

| Source grouping meaning        | Better Shopify Plus interpretation                                 |
| ------------------------------ | ------------------------------------------------------------------ |
| Public customer browsing path  | Shopify collection, navigation, and storefront review.             |
| SEO landing page               | Collection, page, redirect, metadata, or content rebuild decision. |
| Regional storefront grouping   | Markets/localization or expansion-store planning.                  |
| B2B-only access grouping       | B2B catalog or app/custom handling.                                |
| Internal reporting group       | Metafield, tag, app data, or exclusion from public storefront.     |
| Legacy category no longer used | Filtered migration or cleanup before target launch.                |

The key difference is meaning. The same source category can have several functions. Shopify Plus planning should preserve the functions that matter after launch, not just the category names.

### B2B Companies Are Not Ordinary Customers <a href="#b2b-companies-are-not-ordinary-customers" id="b2b-companies-are-not-ordinary-customers"></a>

B2B is one of the most important Shopify Plus data-model differences. In ordinary Shopify migration, customer records usually represent buyer profiles with contact information and order history. In Shopify Plus B2B, a business buyer may need to exist inside a company structure with locations, catalogs, payment terms, buyer access, company-specific pricing, and staff ownership.

A Source Platform may represent B2B in many ways: customer groups, company accounts, quote workflows, account hierarchies, contract catalogs, shared catalogs, tax-exempt buyers, sales representative relationships, ERP account IDs, approval permissions, or custom fields. These should not be migrated blindly as ordinary customer tags or notes unless that outcome is intentionally accepted.

| Source B2B structure       | Shopify Plus target question                                                                |
| -------------------------- | ------------------------------------------------------------------------------------------- |
| Customer group             | Is it a segment, a company attribute, pricing context, catalog rule, or historical label?   |
| Company account            | Should it become a Shopify B2B company and location, or require Custom Service review?      |
| Buyer role or permission   | Can Shopify B2B support the access model, or is external setup needed?                      |
| Contract pricing           | Is the pricing supported by B2B catalogs, app configuration, or custom handling?            |
| ERP account identifier     | Should it be stored as metafield, app data, integration reference, or custom field mapping? |
| Quote or approval workflow | Is it Shopify-side setup, app workflow, or unsupported source behavior?                     |

This separation prevents a major migration error: counting customer records as migrated while losing the commercial architecture that made those customers usable for B2B selling.

### Markets, Localization, and Multi-Store Structures <a href="#markets-localization-and-multi-store-structures" id="markets-localization-and-multi-store-structures"></a>

Shopify Plus merchants often move from platforms with websites, store views, locales, regions, brands, domains, or market-specific catalogs. These source structures must be interpreted carefully because Shopify Plus can support international selling through Markets and can also support multiple stores or expansion stores. The right target model depends on governance, content ownership, operational teams, product availability, currency, tax, shipping, and regional brand strategy.

A source store view may not equal a Shopify market. A regional domain may not require a separate Shopify Plus store. A language version may belong to translation/localization setup rather than a separate migrated content tree. A source website may represent a brand, geography, channel, or old implementation choice that should not be copied mechanically.

| Source structure            | Possible Shopify Plus interpretation                                                  |
| --------------------------- | ------------------------------------------------------------------------------------- |
| Store view or language view | Localization and translation setup, or separate storefront if governance requires it. |
| Country-specific domain     | Market, domain strategy, redirect plan, or expansion-store decision.                  |
| Regional catalog            | Product availability rules, Markets setup, B2B catalog, app logic, or separate store. |
| Multi-brand source site     | Expansion store, separate store, collections, or brand-specific content architecture. |
| Localized CMS pages         | Pages, Blog Posts, translations, metaobjects, redirects, or manual content rebuild.   |
| Regional pricing            | Markets pricing, B2B catalog pricing, app configuration, or external system logic.    |

The data model question is therefore not only where records go. It is which target operating structure the migrated records should support.

### Metafields, Metaobjects, and Custom Data Governance <a href="#metafields-metaobjects-and-custom-data-governance" id="metafields-metaobjects-and-custom-data-governance"></a>

Metafields and metaobjects are important tools for Shopify Plus migrations, but they should not become a dumping ground for every source field. Metafields extend existing Shopify resources such as products, customers, variants, orders, or other objects. Metaobjects create structured objects with multiple fields that can be referenced by metafields, used in themes, or managed as content/data entries.

For Shopify Plus, custom data planning should be more disciplined because enterprise source platforms often have large volumes of attributes, specifications, custom fields, ERP IDs, market flags, B2B labels, merchandising content, and app-owned records. Some fields are useful for customer-facing content. Some are needed for integrations. Some are historical. Some are obsolete. Some require validation rules or theme setup. Some should not migrate at all.

| Custom data type             | Possible handling path                                                         |
| ---------------------------- | ------------------------------------------------------------------------------ |
| Product specifications       | Product metafields, category metafields, metaobjects, or app data.             |
| Rich reusable content blocks | Metaobjects, pages, Blog Posts, theme sections, or manual content rebuild.     |
| ERP/CRM/PIM identifiers      | Metafields, app-owned fields, integration reference, or Custom Service review. |
| B2B account context          | Company setup, customer metafields, app data, or custom handling.              |
| Source extension data        | Custom Service review if unsupported by standard migration behavior.           |
| Historical reporting fields  | Exclusion, archive, metafield, or external reporting decision.                 |

The best Shopify Plus data model is not the one with the most migrated custom fields. It is the one where every custom field has a defined target owner, display behavior, validation expectation, and business purpose.

### Orders, Payments, Fulfillment, and Workflow Context <a href="#orders-payments-fulfillment-and-workflow-context" id="orders-payments-fulfillment-and-workflow-context"></a>

Order migration into Shopify Plus should preserve historical meaning, not imply that every source workflow is recreated. Source orders may include payment labels, shipping methods, discounts, tax context, fulfillment states, partial shipments, refunds, quotes, invoices, purchase order references, ERP IDs, or sales representative data. Some of that context may be readable as historical order information. Some may belong to Shopify setup, app configuration, external integrations, or Custom Service review.

This distinction becomes more important for Plus merchants because historical orders may support customer service, B2B account review, wholesale reordering, financial reconciliation, ERP matching, and fulfillment analysis. However, migrated order history does not configure live Shopify checkout, payment processors, tax logic, fulfillment routing, purchase order workflows, or B2B payment terms.

| Source order context      | Shopify Plus migration interpretation                                     |
| ------------------------- | ------------------------------------------------------------------------- |
| Payment reference         | Historical context, not live payment setup.                               |
| Fulfillment method        | Historical readability plus target fulfillment setup review.              |
| Refund or cancellation    | Historical support and reconciliation context.                            |
| Purchase order number     | B2B order context, metafield/app data, or custom handling.                |
| ERP order ID              | Integration reference, custom field mapping, or Custom Service review.    |
| Quote or approval history | Historical note, app workflow, B2B setup, or unsupported custom behavior. |

A reliable Shopify Plus migration should make order history useful without confusing history with live operational configuration.

### Apps, Integrations, and External-System Data <a href="#apps-integrations-and-external-system-data" id="apps-integrations-and-external-system-data"></a>

Shopify Plus merchants often depend on ERP, PIM, OMS, CRM, subscription, loyalty, reviews, tax, shipping, fraud, analytics, marketplace, personalization, and automation systems. Some source data may belong to those systems rather than the commerce platform itself. Migration planning should identify which data is native source commerce data and which data is app-owned or externally owned.

This matters because Shopify Plus can support deep app and integration ecosystems, but app configuration and integration implementation are not the same as ordinary data migration. A source field that looks like product data may actually be PIM-owned. A customer field may be CRM-owned. A loyalty balance may belong to a loyalty app. A subscription status may belong to a subscription platform. An ERP ID may need to remain stable for post-launch synchronization.

| Dependency               | Data-model question                                                                                              |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| ERP                      | Which product, customer, company, order, and inventory IDs must remain stable?                                   |
| PIM                      | Which product attributes are authoritative and should become Shopify fields, metafields, or external references? |
| OMS / fulfillment system | Which order and fulfillment states are historical vs operational?                                                |
| CRM                      | Which customer fields are buyer profile data vs CRM-owned relationship data?                                     |
| Subscription app         | Which subscription records belong to app migration or target-side setup?                                         |
| Loyalty/review app       | Which records are supported, exported, manually rebuilt, or excluded?                                            |

The practical rule is simple: if data is business-critical but not part of supported Shopify migration behavior, it should be reviewed as Add-ons, Custom Service, app migration, integration work, or target-side setup rather than assumed to transfer automatically.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify Plus data model differences are not only about Shopify fields. They are about enterprise meaning attached to Shopify data. Products, variants, collections, customers, orders, pages, Blog Posts, redirects, metafields, metaobjects, apps, and organization-level structures must be interpreted through B2B, Markets, multi-store governance, external integrations, and validation ownership.

A successful Shopify Plus migration distinguishes ordinary Shopify data from Plus-level operating structures. It identifies what should migrate, what should be configured in Shopify Plus, what belongs to apps or integrations, what requires Add-ons, and what needs Custom Service review. That distinction protects the target store from becoming a shallow copy of the source platform instead of a usable enterprise Shopify environment.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are Shopify Plus data model differences separate from Shopify data model differences?**

They are related but not separate. Shopify Plus uses the Shopify data foundation, but Plus migrations usually attach more enterprise meaning to the same records through B2B, Markets, multiple stores, custom data, integrations, permissions, and workflow governance.

**Should source B2B customer groups become Shopify customer tags?**

Not automatically. A source customer group may represent pricing, company structure, buyer access, tax status, segmentation, or a historical label. The target meaning should be reviewed before deciding whether it belongs in B2B companies, catalogs, customer segments, metafields, apps, or Custom Service scope.

**Can metafields solve every custom data requirement?**

No. Metafields are useful for structured custom data, but unsupported app records, external-system logic, bespoke transformations, and workflow behavior may require Custom Service, app migration, integration work, or target-side setup.

**How should multi-store source data be interpreted for Shopify Plus?**

Multi-store source data should be mapped to the intended target operating structure. It may become one Shopify Plus store with Markets, multiple stores, expansion stores, localized content, B2B catalogs, or a mix of target-side setup and migration scope.

**What is the biggest data-model risk in Shopify Plus migration?**

The biggest risk is treating enterprise source structures as ordinary Shopify records. Products, customers, orders, and content may migrate, but the business meaning behind B2B, Markets, integrations, permissions, pricing, and workflows can be lost if not scoped separately.
