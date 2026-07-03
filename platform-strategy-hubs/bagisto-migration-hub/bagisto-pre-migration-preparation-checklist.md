# Bagisto Pre-Migration Preparation Checklist

Bagisto preparation should begin before records are exported. A Bagisto project is not only a transfer of Products, Customers, Orders, CMS Pages, and store settings. It is a move into a Laravel-based commerce environment where product behavior, attributes, attribute families, channels, inventory sources, themes, extensions, APIs, and optional marketplace or B2B layers can determine whether migrated data remains usable after launch.

A well-prepared Bagisto migration separates clean commercial facts from behavior that must be recreated, configured, mapped, or rebuilt. Product names and order totals may be easy to identify. Product types, configurable choices, bundle logic, customer group pricing, tax settings, channel visibility, inventory distribution, URL rewrites, search behavior, and custom package data require deeper review. Without that review, a technically complete migration can still leave the new store difficult to operate.

The preparation checklist below keeps the work controlled. It follows the established sequence: confirm the Bagisto operating scope, prepare the data structures that must map cleanly, identify behavior that cannot be treated as ordinary records, choose the right service path, and use Demo Migration evidence before committing to Full Migration.

### What Preparation Means for Bagisto <a href="#what-preparation-means-for-bagisto" id="what-preparation-means-for-bagisto"></a>

Preparation for Bagisto means building a clear evidence base for how the current store operates and how that operation should be represented in Bagisto. It is not enough to ask whether products, customers, and orders can be moved. The more important question is whether each record can retain its commercial meaning when Bagisto applies its own product-type, attribute, channel, inventory, marketing, checkout, and extension logic.

Bagisto has strong native structures for catalog management, channel management, inventory sources, customer groups, CMS, marketing rules, taxes, data transfer, and configurable storefront behavior. That strength gives merchants flexibility, but it also makes preparation more important. A product that was simple in the current platform may need to become configurable, bundle, grouped, downloadable, virtual, booking, or a custom product type in Bagisto. A single stock field may need to be understood against Bagisto inventory sources. A generic customer segment may need to become a customer group with pricing or access implications.

Preparation should produce four types of evidence:

| Evidence type          | What it should clarify                                                                      | Why it matters in Bagisto                                             |
| ---------------------- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Data evidence          | Which records exist and which fields matter                                                 | Determines Standard Service scope and Entity Points exposure          |
| Behavior evidence      | How records affect buying, pricing, stock, and fulfillment                                  | Shows where configuration, Add-ons, or Custom Service may be required |
| Structure evidence     | How product types, attributes, categories, channels, and inventory sources relate           | Prevents flat migration that loses Bagisto-specific operating meaning |
| Customization evidence | Which extensions, APIs, themes, custom packages, or headless components influence the store | Identifies Custom Service triggers and post-migration rebuild needs   |

The preparation work should end with a decision-ready migration scope: what can be migrated directly, what needs configuration, what needs Add-ons, what must be reviewed under Custom Service, and what should be rebuilt outside the migration rather than copied from the old store.

### Confirm Bagisto Operating Scope Before Data Preparation <a href="#confirm-bagisto-operating-scope-before-data-preparation" id="confirm-bagisto-operating-scope-before-data-preparation"></a>

Before cleaning data, confirm the intended Bagisto operating scope. Bagisto can support relatively straightforward stores, but it can also support multi-channel commerce, custom product types, marketplace behavior, B2B structures, headless storefronts, API-driven integrations, and extension-based functionality. Preparation becomes much clearer when the future operating shape is known before field mapping begins.

Start by documenting the target selling model. A single-channel retail store needs different preparation from a marketplace, a B2B buying environment, or a store that uses a separate frontend through APIs. The same product and customer data may require different mapping decisions depending on whether Bagisto will operate as a conventional storefront, a multi-channel catalog, a marketplace environment, or a customized Laravel commerce build.

Useful preparation questions include:

| Planning question                                                             | Preparation implication                                                                                       |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Will the Bagisto store use one channel or multiple channels?                  | Product visibility, pricing, locale, currency, theme, and SEO assumptions must be reviewed by channel.        |
| Will inventory be managed through one location or multiple inventory sources? | Stock fields from the current platform may need distribution logic rather than direct one-field mapping.      |
| Will customer groups affect pricing, permissions, or segmentation?            | Customer data must be checked for group logic, price rules, and historical commercial meaning.                |
| Will the storefront be standard, themed, or headless?                         | CMS, navigation, URL behavior, theme assets, and API ownership must be scoped separately.                     |
| Will marketplace or B2B layers be used?                                       | Seller, vendor, company, quote, commission, catalog access, and approval data may need Custom Service review. |
| Will custom packages or extensions be preserved?                              | Extension-created records and custom database tables should be identified before Demo Migration.              |

This operating-scope review prevents a common preparation mistake: cleaning data for a simple store while the intended Bagisto build depends on advanced commerce behavior. If the target operating model is still uncertain, Demo Migration should be used to test representative structures rather than only ordinary products and recent orders.

### Prepare Products, Attributes, and Attribute Families <a href="#prepare-products-attributes-and-attribute-families" id="prepare-products-attributes-and-attribute-families"></a>

Bagisto catalog preparation should begin with product-type classification. Products should not be prepared only as names, SKUs, prices, and descriptions. Each product needs to be reviewed for the buying behavior it represents: simple purchase, configurable selection, digital delivery, bundle composition, grouped presentation, booking behavior, virtual delivery, or a custom product type.

A practical product preparation table should include:

| Field or behavior        | Preparation task                                                                           | Bagisto-specific concern                                                                       |
| ------------------------ | ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| SKU and product identity | Remove duplicates, confirm parent-child relationships, and define canonical SKU rules      | Configurable, grouped, and bundle products depend on stable product identity.                  |
| Product type             | Classify each product by selling behavior, not only by old platform label                  | Bagisto product types affect attributes, pricing, cart behavior, and validation.               |
| Attributes               | Identify which fields are searchable, filterable, required, comparable, or variant-forming | Attribute settings influence catalog usability, layered navigation, and product editing.       |
| Attribute families       | Group attributes by product family, category, or product class                             | Poor attribute-family planning creates admin confusion and inconsistent product maintenance.   |
| Options and variants     | Separate actual variants from free-form customization fields                               | Variant logic should map differently from comments, personalization, or custom request fields. |
| Media                    | Confirm image roles, gallery order, alt text, and missing assets                           | Product media can affect storefront quality even when core product data migrates correctly.    |
| Inventory                | Confirm stock status, quantities, backorder assumptions, and source assignment needs       | Bagisto inventory-source behavior may require target-side planning.                            |

Attribute preparation deserves particular care. Many legacy stores accumulate product fields that look similar but serve different purposes. One field may support search, another may support product comparison, another may drive variants, and another may only be old admin notes. Bagisto preparation should not treat all attributes as equal. Each attribute should be assigned a purpose before migration.

Attribute families should also be planned before Full Migration. If every product is forced into one broad family, Bagisto may become difficult to manage after launch. If too many narrow families are created, the merchant may inherit unnecessary admin complexity. A balanced attribute-family plan should reflect actual catalog maintenance: which products need the same fields, which fields are required, and which fields should be hidden, searchable, filterable, or used only internally.

### Prepare Categories, Channels, and Inventory Sources <a href="#prepare-categories-channels-and-inventory-sources" id="prepare-categories-channels-and-inventory-sources"></a>

Category preparation should connect structure with storefront behavior. Bagisto categories can affect navigation, product discovery, search patterns, SEO context, and channel presentation. A category tree copied from an older store may not be suitable if the new Bagisto build uses different channels, locales, themes, storefront menus, or content strategy.

Review each category for four questions:

1. Does the category still represent how customers browse?
2. Does it need channel-specific visibility?
3. Does it carry SEO or URL value that should be preserved?
4. Does it depend on product attributes or filters that must be prepared first?

Channel preparation is equally important. A current store may have one storefront, but Bagisto may be used with multiple channels for different brands, regions, currencies, locales, or catalogs. If that is planned, products and categories should be prepared with channel assignment in mind. Migration should not assume that all products belong everywhere by default.

Inventory-source preparation should clarify whether stock is a simple value or a distribution decision. Some stores only need one inventory source. Others need warehouse, location, marketplace, supplier, or fulfillment distinctions. If the current platform stores only a flat stock number, Bagisto may require a target-side rule for assigning stock into one or more inventory sources. If the current platform already has multi-location behavior, the preparation task is to determine whether that behavior can be mapped, configured, or recreated.

A useful preparation output is a catalog structure matrix:

| Structure area    | Ready for migration when                                                         | Watch condition                                      | Escalation condition                                             |
| ----------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------------- |
| Categories        | Names, hierarchy, status, SEO value, and product assignment are clear            | Old categories exist only for discontinued campaigns | Category behavior differs by channel, locale, or theme           |
| Channels          | Target channels, currencies, locales, themes, and catalog visibility are defined | Current store has hidden regional assumptions        | Multi-channel logic affects price, visibility, inventory, or SEO |
| Inventory sources | Stock ownership and source assignment rules are defined                          | Current stock data is incomplete or inconsistent     | Multi-location or supplier logic requires custom handling        |

This preparation helps keep Bagisto implementation realistic. It prevents the catalog from being moved as a static tree when the target store needs channel-aware and inventory-aware structure.

### Prepare Customers, Orders, CMS, and Commercial Rules <a href="#prepare-customers-orders-cms-and-commercial-rules" id="prepare-customers-orders-cms-and-commercial-rules"></a>

Customers and Orders require preparation beyond record counts. Bagisto can store customer accounts, customer groups, customer reviews, orders, invoices, shipments, refunds, transactions, marketing rules, CMS content, URL rewrites, search terms, newsletters, and other operational records. The preparation question is not only whether the records exist; it is whether the current platform’s commercial meaning can be preserved in Bagisto.

Customer preparation should identify account status, group assignment, address quality, newsletter consent, review history, pricing relationships, and any B2B or marketplace dependencies. If customer groups are used for pricing or access, those groups should be documented before Demo Migration. If group names are inconsistent or duplicated, clean them before mapping.

Order preparation should preserve the facts a merchant needs after launch: order numbers, dates, customers, products, quantities, discounts, tax, shipping, payment references, invoices, shipments, refunds, order statuses, and order comments. Historical orders often include logic from old payment, tax, shipping, discount, or fulfillment systems. Not all of that logic should become live Bagisto configuration, but the historical record should remain understandable.

CMS and marketing preparation should cover pages, content blocks, menus, email templates, URL rewrites, search terms, search synonyms, sitemaps, cart rules, catalog rules, campaigns, and newsletters where relevant. These records influence continuity after launch. Missing CMS Pages may break landing pages. Weak URL rewrite preparation may damage SEO continuity. Unreviewed cart and catalog rules may create discount mismatches.

| Area      | Preparation focus                                                              | Practical output                                     |
| --------- | ------------------------------------------------------------------------------ | ---------------------------------------------------- |
| Customers | Accounts, groups, addresses, consent, reviews, B2B or marketplace links        | Customer mapping table and group normalization notes |
| Orders    | Statuses, totals, taxes, discounts, invoices, shipments, refunds, transactions | Historical order interpretation map                  |
| CMS       | Pages, menus, content blocks, email templates, search and URL behavior         | Content and SEO continuity checklist                 |
| Marketing | Cart rules, catalog rules, campaigns, newsletters                              | Promotion-retention and rebuild decision list        |

This section of preparation is where merchants should decide what must be preserved as history and what should become live Bagisto configuration. A coupon used three years ago may need to remain visible in order history but does not necessarily need to become an active cart rule. A customer group may need to keep past order meaning even if the new pricing structure changes after launch.

### Prepare Extension, API, Headless, and Custom Package Evidence <a href="#prepare-extension-api-headless-and-custom-package-evidence" id="prepare-extension-api-headless-and-custom-package-evidence"></a>

Bagisto’s Laravel foundation gives merchants and developers significant room for customization. That flexibility is valuable, but it also means preparation must identify which parts of the current store are ordinary data and which parts are behavior created by extensions, custom packages, APIs, themes, headless components, or external systems.

Do not prepare extension-related data by guessing. Build an evidence list. For each extension or custom component, document what it does, which records it creates, which database tables or fields it owns, whether it affects checkout or catalog behavior, whether it connects to an external system, and whether the behavior must continue in Bagisto.

Important areas to check include:

| Dependency type                 | Preparation task                                                                                        | Likely handling                                                                         |
| ------------------------------- | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Payment and shipping extensions | Identify configuration, transaction references, carrier rules, and checkout behavior                    | Usually target configuration, sometimes Custom Service for historical or custom records |
| Product-type extensions         | Identify custom fields, pricing logic, product relationships, or cart behavior                          | Often Custom Service if behavior must be preserved                                      |
| Theme and frontend code         | Identify layout dependencies, menus, scripts, content placement, and responsive behavior                | Usually target-side implementation, not raw data migration                              |
| API integrations                | Identify external identifiers, sync ownership, and update direction                                     | Requires integration planning and validation outside simple record transfer             |
| Headless storefront             | Identify API payloads, frontend routes, search behavior, CMS consumption, and deployment responsibility | Requires separate validation of migrated data and frontend usage                        |
| Marketplace or B2B modules      | Identify seller, company, quote, role, approval, commission, or catalog-access data                     | Often Custom Service if records must be migrated                                        |

If extension-created data is important, determine whether it fits Bagisto’s supported structures, can be handled through Add-ons, or requires Custom Service. Add-ons can support bounded filtering, mapping, or configuration within supported migration behavior. Custom Service is appropriate when unsupported records, custom fields, extension-created tables, custom packages, or bespoke transformation logic must be handled.

This distinction should be made before Full Migration. Waiting until after migration to discover that key checkout, seller, quote, or product-type behavior depended on custom code usually creates avoidable launch pressure.

### Prepare Service Scope, Entity Points, and Demo Migration Samples <a href="#prepare-service-scope-entity-points-and-demo-migration-samples" id="prepare-service-scope-entity-points-and-demo-migration-samples"></a>

Service scope should be prepared from evidence, not optimism. A Bagisto migration can look simple when only core records are counted, but the scope can change once product types, attribute families, channels, inventory sources, CMS records, marketing rules, APIs, headless behavior, marketplace layers, or custom packages are reviewed.

Entity Points should be used as a scope-sizing signal for eligible new Products, Customers, Orders, and Blog Posts. The important duplicate rule is simple: eligible new records consume Entity Points when they are first migrated, while records already counted through the service license do not consume again merely because another action occurs on the same migration path. This rule helps merchants understand size, but it should not be mistaken for a full complexity measure. A small catalog with complex configurable products and custom attributes may need more planning than a larger catalog with simple products.

Demo Migration sampling should reflect real Bagisto complexity. Do not choose only clean records. Include:

* simple and configurable products;
* products with multiple attributes and attribute-family differences;
* bundle, grouped, downloadable, virtual, or booking products where relevant;
* products assigned to important categories and channels;
* records with inventory-source implications;
* customers from different customer groups;
* orders with discounts, taxes, shipping, invoices, shipments, refunds, and transaction references;
* CMS Pages, URL rewrites, search terms, and marketing rules where they affect continuity;
* records touched by extensions, APIs, marketplace layers, B2B logic, or custom packages.

| Demo sample type          | Why it matters                                          | Pass signal                                                                           |
| ------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Product complexity sample | Tests type, attribute, variant, and pricing translation | Product can be edited, displayed, filtered, and purchased correctly                   |
| Channel/inventory sample  | Tests visibility and stock ownership                    | Product appears in the right channel with correct availability                        |
| Customer/order sample     | Tests account and history continuity                    | Customer and order history remain commercially understandable                         |
| CMS/SEO sample            | Tests content and discovery continuity                  | Pages, URLs, search behavior, and key content remain usable                           |
| Custom dependency sample  | Tests escalation need                                   | Unsupported behavior is clearly assigned to configuration, Add-ons, or Custom Service |

A Demo Migration that only proves ordinary records is not enough for a Bagisto project with advanced architecture. The sample should be representative enough to support a real Full Migration decision.

### Prepare Follow-Up Migration Controls Before Launch <a href="#prepare-follow-up-migration-controls-before-launch" id="prepare-follow-up-migration-controls-before-launch"></a>

Follow-up migration planning should be defined before launch, not after a problem appears. Bagisto projects often include a period of target-side configuration, theme work, integration development, or validation after the first migration test. During that period, the old store may continue to receive new orders, customers, products, CMS changes, or promotional updates.

Additional Migration Options should be selected based on what changed after the last run:

| Option                                                  | Use when                                                                                | Bagisto preparation concern                                                             |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | New records need to be migrated and the mapping remains valid                           | Confirm that product types, attributes, channels, and inventory rules have not changed. |
| Continue the Migration with a new configuration         | The migration path needs adjusted mapping, filtering, or configuration                  | Recheck affected records before applying the new configuration.                         |
| Perform a new migration                                 | The target build, source scope, or business rules changed enough to require a clean run | Avoid layering inconsistent assumptions onto the Bagisto target store.                  |

The preparation team should also assign ownership for freeze windows, final record updates, SEO review, integration testing, theme readiness, inventory validation, and launch approval. If ownership is unclear, the project may pass technical migration checks but still fail operational readiness.

A strong Bagisto preparation process ends with a launch-readiness packet: scope decision, data cleanup notes, mapping tables, Demo Migration sample plan, Add-ons and Custom Service decisions, Entity Points scope notes, target configuration responsibilities, Additional Migration Options plan, and sign-off criteria.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Bagisto migration preparation should turn a broad commerce move into a controlled operating-model decision. Products, Customers, Orders, CMS Pages, categories, attributes, channels, inventory sources, customer groups, marketing rules, extensions, APIs, and custom packages need to be reviewed before migration execution begins.

The strongest preparation work separates records from behavior. Records may migrate through supported paths. Behavior may require Bagisto configuration, Add-ons, Custom Service, or a target-side rebuild. When that distinction is made before Demo Migration, the project can use test evidence to confirm scope instead of discovering gaps late in launch planning.

Bagisto rewards careful preparation because its architecture is flexible. That flexibility is most valuable when product types, attributes, attribute families, channels, inventory sources, CMS content, commercial rules, and custom dependencies are prepared as connected decisions rather than isolated fields.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to Bagisto?**

Start with the intended Bagisto operating scope. Confirm whether the target store will use simple catalog behavior, multiple product types, multiple channels, inventory sources, marketplace features, B2B functions, headless storefronts, APIs, or custom packages. That decision shapes every later preparation task.

**Why are attributes and attribute families important in Bagisto preparation?**

Bagisto uses attributes and attribute families to structure product information. If they are prepared poorly, products may migrate but become difficult to manage, filter, compare, edit, or display consistently after launch.

**Should all extensions and custom behavior be migrated into Bagisto?**

No. Some behavior should be replaced by Bagisto configuration or rebuilt using target-side extensions or custom development. Extension-created records, custom fields, custom tables, and bespoke transformation needs should be reviewed for Custom Service rather than treated as ordinary data.

**How should Demo Migration samples be chosen for Bagisto?**

Choose representative records, not only clean records. Include complex product types, important attributes, customer groups, discounted orders, inventory cases, CMS and SEO examples, and records affected by extensions, APIs, marketplace layers, B2B logic, or custom packages.

**When should Additional Migration Options be planned?**

Plan them before launch. They matter when the old store continues to change after the first migration run or when the Bagisto configuration changes during preparation, testing, or target-side implementation.
