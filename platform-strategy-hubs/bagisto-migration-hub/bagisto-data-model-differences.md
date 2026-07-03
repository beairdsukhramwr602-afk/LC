# Bagisto Data Model Differences

Bagisto migration is not a simple transfer of product, customer, and order tables into another ecommerce admin. Bagisto is built around Laravel-based commerce architecture, where catalog structure, product types, attributes, attribute families, categories, channels, locales, inventory sources, customer groups, CMS content, marketing rules, extensions, APIs, and custom packages can all shape how migrated data becomes usable after launch.

That architecture gives merchants a flexible Target Platform, but it also changes the meaning of many records. A field that looked like a simple product option in the current store may need to become an attribute, part of a configurable product, a bundle selection, a channel-specific setting, a custom package field, or a structure that requires Custom Service review. A customer segment may need to become a customer group, B2B company context, marketplace participant, or pricing boundary. An order may need invoices, shipments, refunds, transactions, tax meaning, and customer-service context to remain useful.

A strong Bagisto data-model plan starts by separating raw records from operating meaning. Raw records answer what exists. Operating meaning answers how the store sells, prices, filters, localizes, fulfills, reports, and integrates those records after migration.

### What Data Model Difference Means in Bagisto Migration <a href="#what-data-model-difference-means-in-bagisto-migration" id="what-data-model-difference-means-in-bagisto-migration"></a>

Data-model difference means that the same business fact may need a different target structure once it reaches Bagisto. Bagisto can manage ordinary ecommerce records, but its flexibility comes from structured catalog design, configuration ownership, extension behavior, and developer-controlled customization. Migration planning should therefore determine whether each piece of data belongs in native Bagisto structure, target configuration, an extension layer, a headless/API layer, or Custom Service handling.

This distinction is especially important because Bagisto often appeals to merchants who want more control than a closed SaaS platform allows. That control can support more tailored catalog management, channel separation, developer-owned features, and specialized commerce models. It also means that data decisions cannot be postponed until after Full Migration. If attributes, product types, channels, or customer groups are not designed before migration, the migrated store may contain the correct records but still fail to support filtering, pricing, storefront display, inventory control, or account access correctly.

| Migration question                      | Why it matters in Bagisto                                                                                            |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| What is a product in the current store? | It may become a simple, configurable, grouped, bundle, virtual, downloadable, or booking-style product structure.    |
| What is an attribute?                   | It may control filtering, variant selection, comparison, product families, admin maintenance, or storefront display. |
| What is a storefront context?           | It may require channel, locale, currency, inventory, content, or routing decisions.                                  |
| What is a customer segment?             | It may affect groups, pricing visibility, B2B access, approval rules, or marketplace roles.                          |
| What is historical order value?         | It may require totals, taxes, payments, shipments, invoices, refunds, notes, and customer-service context.           |
| What is custom behavior?                | It may require extension review, API alignment, custom package development, or Custom Service.                       |

The practical outcome is a translation plan, not a record list. Bagisto migration succeeds when the current store’s business meaning is rebuilt in the right Bagisto layer.

### Product Types, Attributes, and Attribute Families <a href="#product-types-attributes-and-attribute-families" id="product-types-attributes-and-attribute-families"></a>

Bagisto catalog migration depends heavily on how products are represented. Product names, SKUs, descriptions, prices, and images are only the base layer. The more important migration question is how products are sold and managed: whether buyers choose variants, compare specifications, download files, book services, buy bundles, select grouped items, or rely on structured product information for filtering.

Attributes and attribute families are central to that interpretation. If the current store uses inconsistent fields, merged descriptions, app-created specifications, or loosely managed options, Bagisto may need a cleaner attribute model before the catalog is migrated. A product specification stored inside description text is visible to a buyer, but it may not support filtering or structured maintenance. A custom field used only by staff may need a different treatment from an attribute that drives storefront choice. A variant option may need to become part of configurable-product logic rather than remain as a flat text value.

The preparation decision is not whether every detail can be moved. The better decision is whether each product detail should remain content, become an attribute, define a product family, control a variant, support filtering, or move into a custom field. Bagisto can support detailed catalog structure, but that structure needs clear ownership before migration.

| Current-store pattern                     | Bagisto interpretation to review            | Migration consequence                                               |
| ----------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------- |
| Options stored as text or custom fields   | Attribute or configurable-product structure | Buyer selection and variant accuracy may change.                    |
| Specifications embedded in descriptions   | Product attributes or rich content          | Filtering and comparison may require restructuring.                 |
| Bundles, kits, or grouped items           | Bundle, grouped, or custom logic            | Relationship preservation may need deeper review.                   |
| Downloadable or virtual products          | Product-type-specific handling              | Fulfillment and access rules must remain meaningful.                |
| Booking-like products                     | Booking structure or custom treatment       | Availability and scheduling behavior may not be simple record data. |
| Product families with inconsistent fields | Attribute-family design                     | Admin maintenance and storefront consistency depend on cleanup.     |

Bagisto gives room to build a stronger catalog, but the migration should not carry old disorder into a new attribute model. It should preserve commercially important meaning while improving the structure needed for long-term operation.

### Categories, Channels, Locales, and Inventory Sources <a href="#categories-channels-locales-and-inventory-sources" id="categories-channels-locales-and-inventory-sources"></a>

Categories in Bagisto should be reviewed as navigation and merchandising structure, not only as product folders. A current store may have categories that were created for SEO landing pages, manual merchandising, internal catalog organization, seasonal navigation, marketplace feeds, or old menu behavior. Moving all category labels without reviewing their purpose can create a target catalog that is technically complete but difficult to browse, filter, or maintain.

Channels add another layer of meaning. A Bagisto implementation may use channels to separate storefront contexts, languages, currencies, domains, inventories, or business units. That makes channel planning part of data-model translation. A product may exist globally but appear differently by channel. A category may be visible in one context and not another. Content, pricing, currency, inventory, and customer expectations may differ across storefronts.

Inventory sources also require interpretation. A quantity field in the current store may not explain warehouse ownership, availability rules, back-order policy, pickup behavior, supplier logic, or fulfillment routing. If the new Bagisto build uses multiple inventory sources or channel-specific stock behavior, migration planning should decide whether current inventory data is sufficient or whether inventory must be normalized before launch.

A useful review separates three questions:

| Question                                                                       | Decision cue                                                                                                     |
| ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Does the category tree represent buyer navigation or back-office organization? | Buyer navigation should be validated in the storefront; internal grouping may need a different target structure. |
| Does the store require multiple channels, locales, or currencies?              | Channel planning should happen before product and content migration are treated as complete.                     |
| Does inventory mean simple quantity or fulfillment logic?                      | Multi-source inventory, back orders, and channel availability require validation beyond count matching.          |

When these layers are ignored, Bagisto migration may look successful in the admin area while buyer-facing discovery, localized selling, and stock behavior remain incomplete.

### Customer Groups, Orders, and Commercial History <a href="#customer-groups-orders-and-commercial-history" id="customer-groups-orders-and-commercial-history"></a>

Customer data in Bagisto should preserve identity, access, segmentation, and commercial context. Basic customer records are rarely the whole story. Customer groups can affect pricing, visibility, tax handling, promotional eligibility, B2B logic, approval rules, or account treatment. If the current platform uses tags, groups, customer roles, pricing lists, or manually managed labels, those structures need interpretation before migration.

Order history is similar. Order records are useful only when staff can understand what happened and act on it after launch. Bagisto order history may need order statuses, payment context, invoices, shipments, refunds, taxes, discounts, customer notes, addresses, transaction references, and fulfillment meaning. A migrated order that lacks enough operational context may satisfy a count check but fail customer-service needs.

Commercial history also includes customer reviews, coupons, cart rules, catalog rules, newsletter subscriptions, returns, and reporting context. These areas should not be treated as equal to ordinary records. Some can be migrated directly when supported. Others may require target configuration or Custom Service when the current store uses app-owned logic, custom discount engines, external loyalty data, subscription records, quote history, or B2B rules.

| Data area            | What must remain meaningful                                                    | Common loss pattern                                                    |
| -------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| Customers            | Login identity, addresses, group membership, segmentation, access context      | Tags move but pricing/access meaning disappears.                       |
| Orders               | Status, totals, taxes, payment, shipment, invoice, refund, and service context | Historical orders exist but cannot support support-team review.        |
| Discounts            | Rule intent, eligibility, dates, conditions, usage meaning                     | Old promotion labels move without executable target logic.             |
| Reviews              | Product association, customer association, approval status, display meaning    | Reviews lose connection to the correct product or visibility rule.     |
| B2B/marketplace data | Company, buyer, vendor, role, quote, commission, or approval meaning           | Complex commercial structure is flattened into ordinary customer data. |

The migration should prioritize the records that staff use to serve buyers, reconcile orders, understand pricing, and maintain account relationships. Those records need meaning, not just presence.

### CMS, SEO, Marketing, and Search Meaning <a href="#cms-seo-marketing-and-search-meaning" id="cms-seo-marketing-and-search-meaning"></a>

CMS content in Bagisto migration includes more than pages. It can include content blocks, navigational content, email templates, campaign-related content, URL rewrites, sitemap behavior, search terms, synonyms, and rich snippets. These structures affect discoverability, conversion, and continuity after launch.

A current store may use CMS pages for policy content, landing pages, buying guides, SEO pages, brand pages, or support content. Some pages may be directly migratable. Others may depend on old theme layouts, page-builder blocks, embedded scripts, app widgets, or custom templates. During Bagisto migration, the content plan should separate text content from layout behavior, SEO intent, media handling, internal links, and target routing.

Marketing and search data also need interpretation. Cart rules and catalog rules are not merely historical promotions; they express pricing logic, eligibility, customer targeting, product conditions, and commercial timing. Search terms and synonyms can reveal how buyers find products. URL rewrites and redirects protect continuity. If these elements are treated as secondary, the new Bagisto store may preserve catalog records but lose search visibility, internal findability, and promotion behavior.

A practical Bagisto content-data review should confirm:

| Review area                   | What to validate                                                                           |
| ----------------------------- | ------------------------------------------------------------------------------------------ |
| CMS pages                     | Content accuracy, internal links, media paths, target placement, and layout dependencies.  |
| URL rewrites                  | Old-to-new URL preservation, redirect coverage, canonical intent, and SEO-sensitive pages. |
| Sitemaps and rich snippets    | Whether target configuration supports discovery and structured presentation.               |
| Search terms and synonyms     | Whether buyer search behavior remains supported after catalog restructuring.               |
| Cart and catalog rules        | Whether old conditions can be rebuilt in Bagisto or need different target logic.           |
| Email templates and campaigns | Whether customer communication content remains accurate after platform change.             |

The goal is not to preserve every old content artifact unchanged. The goal is to keep the business purpose behind content, SEO, search, and marketing structures usable after migration.

### Extensions, APIs, Headless Builds, and Custom Development Data <a href="#extensions-apis-headless-builds-and-custom-development-data" id="extensions-apis-headless-builds-and-custom-development-data"></a>

Bagisto’s Laravel foundation and developer ecosystem make extensibility a major part of its migration value. At the same time, extensibility creates data-model boundaries. Data owned by an app, extension, custom package, API integration, headless storefront, mobile app, POS connection, or marketplace/B2B layer should not be assumed to map like native products, customers, or orders.

Custom packages may store additional fields, tables, relationships, permissions, or operational states. API integrations may use external identifiers that are essential for ERP, PIM, CRM, accounting, shipping, tax, fulfillment, or marketplace systems. Headless builds may require product data, content data, pricing data, customer access, and checkout context to be consumable through an API layer rather than only visible inside Bagisto administration.

This is where Add-ons and Custom Service must remain separate. Add-ons can support bounded filtering, mapping, configuration, or tailored handling within a defined migration path. Custom Service is the right review path when the migration depends on unsupported records, extension-owned data, custom database structures, custom fields, app-specific relationships, custom package behavior, external identifiers, or bespoke transformation logic.

| Dependency type                   | Migration interpretation                                                              |
| --------------------------------- | ------------------------------------------------------------------------------------- |
| Standard Bagisto fields           | Usually appropriate for standard mapping when supported and clean.                    |
| Add-on-level mapping or filtering | Useful when supported data needs bounded selection, adjustment, or configuration.     |
| Extension-owned records           | Requires review because ownership and structure may differ from native Bagisto data.  |
| API identifiers                   | Must be preserved when external systems depend on them.                               |
| Headless storefront data          | Must be validated through the API/front-end consumption path, not only admin records. |
| Custom package data               | Usually requires Custom Service if it changes schema, behavior, or business logic.    |

The safest approach is to classify each dependency before migration. Unsupported behavior should not be hidden inside a generic data export; it should become an explicit scope decision.

### Turning Data Differences Into Migration Scope <a href="#turning-data-differences-into-migration-scope" id="turning-data-differences-into-migration-scope"></a>

Bagisto data-model differences should become a migration scope map. The scope map tells the migration team which records are standard, which structures need mapping decisions, which elements require configuration, which need Add-ons, and which need Custom Service. Without that map, complex projects often discover too late that important business meaning lived outside ordinary export columns.

A useful scope map should include product types, attribute families, categories, channels, locales, currencies, inventory sources, customers, customer groups, orders, invoices, shipments, refunds, CMS pages, URL rewrites, rules, reviews, integrations, extensions, API identifiers, and custom package data. It should also identify what will be tested during Demo Migration and what must be validated after Full Migration.

The most important decision is not whether Bagisto can hold the data. The decision is whether the migrated data will support the target store’s operating model. A merchant moving into Bagisto for open-source control, Laravel extensibility, marketplace plans, B2B requirements, multi-channel selling, or headless architecture should define those expectations before migration begins.

| Scope category                                  | Typical handling                                            |
| ----------------------------------------------- | ----------------------------------------------------------- |
| Clean native records                            | Standard migration path when supported and consistent.      |
| Structured but inconsistent catalog data        | Mapping review, cleanup, or Advanced Data Mapping.          |
| Channel, locale, or inventory-specific behavior | Target configuration and validation planning.               |
| Rule-based pricing or promotions                | Rebuild or configuration review, not blind record transfer. |
| Extension or custom package data                | Custom Service review when unsupported or schema-specific.  |
| External integration identifiers                | Preservation plan and post-migration reconciliation.        |

When these categories are clear, Bagisto migration becomes a controlled translation from the current store’s operating model into the Target Platform. When they are unclear, migrated records may be present but commercially incomplete.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Bagisto data-model differences matter because the platform’s value comes from structured commerce architecture, not from flat record storage. Products, attributes, categories, channels, inventory sources, customers, orders, CMS content, rules, extensions, APIs, and custom packages each have a role in how the target store sells and operates.

A reliable Bagisto migration identifies which data can move as native records, which data needs configuration, which data needs mapping support, and which data requires Custom Service. The strongest migration plans preserve business meaning first and record counts second.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Bagisto product attributes matter so much during migration?**

Product attributes can control filtering, comparison, variant selection, product families, and admin maintenance. If attributes are migrated as loose text or poorly organized fields, the catalog may appear complete but become difficult to browse, filter, or manage.

**Can product options from another platform become Bagisto configurable products automatically?**

Not always. Product options, variants, bundles, and grouped items may represent different selling logic in different platforms. They should be reviewed before migration so the Bagisto structure reflects how buyers actually choose and purchase products.

**Do channels and inventory sources affect Bagisto data migration?**

Yes. Channels, locales, currencies, and inventory sources can change product visibility, pricing presentation, stock behavior, and content ownership. They should be planned before migrated records are judged complete.

**When does Bagisto data require Custom Service?**

Custom Service should be considered when the migration includes unsupported records, extension-owned data, custom package fields, custom database structures, external-system identifiers, app-specific relationships, or bespoke transformation requirements.

**How should Demo Migration be used for Bagisto data-model review?**

Demo Migration should include representative products, attributes, variants, customer groups, orders, content, rules, and custom-dependent records. The sample should prove that important business meaning survives in the intended Bagisto layer.
