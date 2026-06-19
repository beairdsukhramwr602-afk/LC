# Magento Pre-Migration Preparation Checklist

Magento preparation should turn platform assumptions into migration-ready evidence before data is moved at scale. Magento can support complex catalog architecture, scoped values, configurable products, attribute sets, URL rewrites, inventory rules, customer groups, and extension-driven behavior. Those strengths also make preparation more important than a simple source-data export.

A prepared Magento migration defines how the Target Store should be structured, which source-store patterns must be preserved, which values need cleanup, which records require special handling, and which samples should be reviewed during Demo Migration. Strong preparation reduces avoidable rework, improves configuration decisions, and helps separate standard migration needs from Add-on, Managed Service, or Custom Service requirements.

### Confirm the Target Store Structure <a href="#confirm-the-target-store-structure" id="confirm-the-target-store-structure"></a>

Magento preparation should begin with the intended Target Store structure. Website, store, and store-view decisions can affect configuration, catalog visibility, localized values, root categories, URLs, currency behavior, and validation scope. If these decisions remain unclear, migrated data may appear correct at the record level while behaving incorrectly in the storefront.

| Preparation area | What to confirm                                                                           | Why it matters in Magento                                                                                  |
| ---------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Websites         | Whether the Target Store needs one website or multiple websites.                          | Website scope can affect configuration, catalog availability, price behavior, and sales-channel planning.  |
| Stores           | Whether different storefronts need separate root categories or navigation structures.     | Store structure affects catalog organization and storefront experience.                                    |
| Store views      | Whether languages, regional views, or localized storefronts require separate store views. | Store-view scope can affect names, descriptions, URL keys, metadata, attribute labels, and display values. |
| Catalog sharing  | Whether storefronts share one catalog foundation or require separated selections.         | Shared and separated catalog assumptions affect visibility, category planning, and validation samples.     |
| Localization     | Which values belong to migrated data and which belong to target configuration.            | Some currency, language, tax, and regional behavior may need configuration rather than direct transfer.    |

Target structure should be decided before treating Entity Points capacity as the main planning measure. A smaller multilingual Magento store can require more preparation than a larger single-store catalog because scoped values must be mapped, inherited, overridden, and validated correctly.

### Prepare Representative Catalog Samples <a href="#prepare-representative-catalog-samples" id="prepare-representative-catalog-samples"></a>

Magento catalog preparation should focus on product behavior, not only product count. A source catalog may include simple products, variant-style products, kits, bundles, grouped offers, downloadable items, service products, custom options, personalization logic, merchandising relationships, or extension-controlled product behavior.

Prepare examples that show each important catalog pattern:

* simple products with standard price, quantity, images, categories, and descriptions;
* variant-style products with size, color, material, capacity, or other option values;
* products that should become configurable products with associated simple products;
* grouped products, bundled products, kits, packs, or build-your-own selling patterns;
* downloadable or virtual products for digital files, memberships, services, or non-shipped items;
* products with custom options, personalization, engraving, add-on services, or conditional selections;
* products with related products, upsells, cross-sells, replacement products, or accessory relationships;
* products with different visibility, status, tax class, price, or inventory behavior.

Each sample should explain why it matters. One configurable product with two color options is not enough when the live catalog also includes size/color combinations, swatches, disabled child SKUs, child-level inventory, localized descriptions, and category-specific merchandising rules.

#### Separate product structure from product cleanup <a href="#separate-product-structure-from-product-cleanup" id="separate-product-structure-from-product-cleanup"></a>

Preparation should identify whether catalog issues are migration-structure problems or source-data quality problems. A product that needs configurable-product mapping is a structural preparation item. A product with inconsistent descriptions, missing images, duplicate option labels, or outdated category placement is a cleanup item. Both affect migration quality, but they require different decisions before Full Migration.

### Clean and Classify Attributes <a href="#clean-and-classify-attributes" id="clean-and-classify-attributes"></a>

Attributes require focused preparation because Magento attributes can support product display, search, layered navigation, comparison, promotions, product creation, reporting, and internal operations. Poor attribute preparation can create duplicated values, noisy filters, confusing product pages, weak search behavior, and hard-to-maintain attribute sets.

| Attribute category         | Preparation question                                                                             | Recommended action                                                                                |
| -------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Customer-facing attributes | Should shoppers see this value on product pages, filters, comparison, or search?                 | Clean labels, normalize values, and decide how the attribute should appear.                       |
| Operational attributes     | Does staff need this value for fulfillment, reporting, merchandising, or internal workflows?     | Preserve where useful, but avoid exposing it unnecessarily on the storefront.                     |
| Variant-driving attributes | Does this value define configurable product options such as size, color, capacity, or material?  | Normalize option values before migration and test representative configurable products carefully. |
| Legacy attributes          | Does the field come from an old plugin, retired process, or obsolete source-store configuration? | Exclude, archive, or review before creating target clutter.                                       |
| Extension-owned attributes | Does the value depend on a source extension, app, module, or custom workflow?                    | Review through Add-ons or Custom Service when standard mapping is not enough.                     |

Attribute cleanup should happen before Full Migration whenever possible. Inconsistent values such as `Blue`, `blue`, `Navy Blue`, `Navy`, and `Color: Navy` may look minor in a spreadsheet, but they can weaken layered navigation and catalog quality after migration. The target plan should define labels, option values, filter behavior, storefront visibility, search usage, and attribute-set placement before the migration path is finalized.

#### Review attribute sets before creating the Target Store catalog <a href="#review-attribute-sets-before-creating-the-target-store-catalog" id="review-attribute-sets-before-creating-the-target-store-catalog"></a>

Attribute sets should match the way the merchant creates and maintains products. A single generic attribute set may be easier to plan initially, but it can make long-term product management harder. Too many attribute sets can also create maintenance overhead. Preparation should define which product families genuinely need separate attribute sets and which fields can remain shared.

### Prepare Category, Navigation, and URL Evidence <a href="#prepare-category-navigation-and-url-evidence" id="prepare-category-navigation-and-url-evidence"></a>

Magento category preparation should connect data structure to storefront discovery. Categories are not only containers for products. They can affect navigation, product discovery, merchandising, SEO, and store-specific root-category structure.

Prepare the following before migration:

* current source category tree;
* intended Magento root categories and navigation structure;
* products assigned to multiple categories;
* categories that should be excluded, merged, renamed, redirected, or rebuilt;
* category descriptions, images, metadata, and URL keys that should be preserved;
* obsolete seasonal, campaign, or hidden categories that should not be treated as active navigation;
* expected category behavior for each website, store, or store view.

URL evidence should be collected with category evidence. Magento can use URL rewrites for products, categories, CMS Pages, and custom routes. If URL continuity matters, prepare current source URLs, intended target URLs, redirect expectations, high-value pages, and launch validation priorities.

A URL plan is especially important when the source store has long-standing organic traffic, paid landing pages, affiliate URLs, indexed category pages, localized URLs, or platform-specific routing rules. Preparation should identify which URLs must be preserved exactly, which can redirect, and which can be retired without business risk.

### Prepare Customer and Order Context <a href="#prepare-customer-and-order-context" id="prepare-customer-and-order-context"></a>

Customer and order preparation should preserve business meaning without assuming that every historical behavior will become live target functionality. Customers may include addresses, groups, tax implications, discount eligibility, company relationships, marketing consent, account status, password limitations, and external identifiers. Orders may include payment, shipping, tax, discount, currency, status, fulfillment, refund, cancellation, and integration references.

Prepare samples that include:

* registered customers and guest-checkout records;
* customers with multiple addresses;
* customer groups that affect discounts, tax class, wholesale rules, or service workflows;
* B2B, reseller, member, or VIP account examples if relevant;
* orders with multiple products, discounts, taxes, shipping fees, refunds, cancellations, or partial fulfillment;
* orders with external IDs from ERP, shipping, marketplace, accounting, CRM, or customer service systems;
* records that should remain readable historically but do not need to power live checkout behavior.

Customer groups should be treated as commercial context, not only labels. If a group affects pricing, taxation, promotions, approvals, or downstream operations, the migration plan should define how that meaning will be preserved, rebuilt, or validated in Magento.

### Review Inventory and Fulfillment Assumptions <a href="#review-inventory-and-fulfillment-assumptions" id="review-inventory-and-fulfillment-assumptions"></a>

Magento inventory preparation depends on the target inventory model. A single-warehouse store may need a simpler setup than a merchant with multiple warehouses, pickup locations, drop shippers, regional fulfillment rules, or separate stock availability by website.

Before migration, confirm:

* whether the Target Store will use a single source or multiple sources;
* whether quantity, stock status, salable quantity, backorders, reservations, or safety-stock logic must be preserved or reconfigured;
* whether inventory behavior differs by website, warehouse, sales channel, or fulfillment location;
* whether source-store stock data comes from the e-commerce platform, ERP, warehouse management system, marketplace, or custom integration;
* whether inventory values should migrate as live operational data or be refreshed closer to launch.

Inventory should not be prepared only as a numeric field. Stock data affects selling availability, fulfillment confidence, customer expectations, and launch timing. If inventory is controlled outside the source store, the migration plan should identify the system of record and the correct timing for inventory synchronization.

### Identify Extensions, Custom Fields, and Outside-System Dependencies <a href="#identify-extensions-custom-fields-and-outside-system-dependencies" id="identify-extensions-custom-fields-and-outside-system-dependencies"></a>

Magento preparation should identify data that may not belong to the standard platform data model. Many source stores rely on extensions, apps, plugins, modules, custom database tables, scripts, third-party systems, and operational workflows that affect how data is displayed or used.

Prepare a dependency inventory covering:

* source extensions or modules that create product, customer, order, content, pricing, shipping, checkout, subscription, loyalty, review, or marketplace data;
* custom fields that must remain visible or usable in Magento;
* third-party identifiers used by ERP, CRM, accounting, shipping, marketplace, search, PIM, or customer-service systems;
* custom order statuses, fulfillment stages, approval flows, or B2B account structures;
* custom URLs, landing pages, forms, content blocks, or embedded scripts;
* source behaviors that are not visible in exported records but affect storefront or admin workflows.

Standard Add-ons can support defined filtering, mapping, or configuration needs. Custom Service should be reviewed when the migration involves unsupported extension data, Custom Platform handling, outside-system identifiers, bespoke transformation, custom logic, or source behavior that cannot be represented through standard migration configuration.

### Prepare Access, Backups, and Migration Environment Details <a href="#prepare-access-backups-and-migration-environment-details" id="prepare-access-backups-and-migration-environment-details"></a>

Technical preparation should make the migration environment safe, reachable, and stable. Missing access, unstable environments, blocked connectors, incomplete credentials, or unplanned maintenance windows can delay Demo Migration, Full Migration, or issue investigation.

Confirm the following before migration work begins:

| Preparation item      | What to prepare                                                                                  | Why it matters                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Source-store access   | Admin, database, API, file, media, or connector access required for the selected migration path. | Incomplete access can prevent full data extraction or media transfer.          |
| Target-store access   | Magento admin, database, file, API, hosting, and deployment access when required.                | Target access affects configuration, import, troubleshooting, and validation.  |
| Backups               | Recent source and target backups, including database and media files where relevant.             | Backups reduce recovery risk if configuration or import work must be reversed. |
| Maintenance timing    | Known freeze windows, sales events, catalog updates, or technical maintenance periods.           | Timing affects freshness, additional migration planning, and launch readiness. |
| Environment status    | Whether the target environment is staging, development, or launch-bound production.              | Environment status affects validation confidence and go-live planning.         |
| Security restrictions | Firewall rules, IP allowlists, CAPTCHA, two-factor access, or hosting limitations.               | Access restrictions can block migration operations or delay support review.    |

Access preparation should also include a responsible contact for each environment. When several teams control hosting, ERP, theme development, SEO, or fulfillment integrations, issue resolution is slower if ownership is unclear.

### Build the Demo Migration Review Set <a href="#build-the-demo-migration-review-set" id="build-the-demo-migration-review-set"></a>

Demo Migration should test representative Magento outcomes, not only confirm that records can move. The review set should include enough samples to expose product behavior, scoped values, category placement, images, URLs, customer/order context, inventory behavior, and extension-sensitive records.

Recommended Demo Migration samples include:

* products from each major product type or selling pattern;
* configurable products with representative option combinations;
* products with important attributes, attribute sets, media, and category assignments;
* localized product names, descriptions, URL keys, and metadata if store views are involved;
* priority categories and navigation paths;
* customer groups and customer records with meaningful account context;
* orders with discounts, taxes, shipping, refunds, cancellations, or external references;
* inventory examples that represent stock-sensitive selling behavior;
* CMS Pages, Blog Posts, and high-value content records;
* records tied to custom fields, extensions, modules, or outside-system identifiers.

Demo Migration results should be reviewed against the migration objective, not only against source-store screenshots. Some differences may be expected because Magento structures data differently. Other differences may indicate preparation gaps, mapping issues, target configuration needs, Add-on requirements, or Custom Service scope.

### Decide What Must Be Ready Before Full Migration <a href="#decide-what-must-be-ready-before-full-migration" id="decide-what-must-be-ready-before-full-migration"></a>

Not every preparation item must be perfect before Full Migration, but launch-critical assumptions should be settled before large-scale transfer begins. The preparation phase should clearly separate blocking items from items that can continue during validation or launch planning.

| Readiness category                      | Examples                                                                                                                                    | Recommended decision                                                               |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Blocking before Full Migration          | Undecided target structure, missing source access, unclear product model, unsupported custom data, no backup, unreviewed critical URL plan. | Resolve before Full Migration.                                                     |
| Should be settled before Full Migration | Attribute labels, category structure, priority samples, customer group meaning, inventory source of truth, Demo Migration review set.       | Resolve unless there is an agreed reason to proceed.                               |
| Can continue during validation          | Minor content cleanup, low-risk product copy, non-critical merchandising adjustments, some redirect refinements.                            | Track after migration without blocking data transfer.                              |
| Requires service-scope review           | Extension-owned data, bespoke transformation, Custom Platform logic, outside-system identifiers, unusual product or order logic.            | Review for Add-ons, Managed Service, or Custom Service before committing to scope. |

Preparation is complete when the migration team can explain what should migrate, how Magento should represent it, what evidence will be reviewed, which risks have been accepted, and which items require additional service planning.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento preparation should create a clear operating plan before migration execution. The most important work is not only collecting records, but confirming target structure, catalog behavior, scoped values, URLs, customer and order context, inventory assumptions, extension dependencies, access, backups, and representative Demo Migration samples.

A well-prepared Magento migration gives the customer and Next-Cart a stronger basis for choosing the right service scope, reviewing Demo Migration evidence, deciding whether Add-ons or Custom Service are needed, and validating the Target Store before launch.

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Should the Magento Target Store be fully configured before migration?**

The Target Store should be configured enough to support the intended migration structure, especially websites, stores, store views, categories, attributes, product types, and access requirements. Some storefront polish can continue later, but core structure should not remain undecided before Full Migration.

**What Magento preparation usually takes the most time?**

Catalog structure and attributes often require the most preparation because they affect product behavior, layered navigation, search, product creation, and validation. Multi-store scope, URL planning, inventory behavior, and extension-owned data can also require significant review.

**Do all source attributes need to be migrated into Magento?**

No. Attributes should be cleaned and classified before mapping. Useful customer-facing and operational attributes should be preserved appropriately, while obsolete, duplicated, legacy, or extension-dependent values should be reviewed before they create target-store clutter.

**When should Add-ons be considered during Magento preparation?**

Add-ons should be considered when the migration needs defined filtering, mapping, or configuration support beyond the standard path. If the need involves unsupported extension data, outside-system identifiers, custom logic, or bespoke transformation, Custom Service may be more appropriate.

**Why prepare Demo Migration samples before the migration begins?**

Representative samples help test Magento-specific outcomes early. They make it easier to detect product-model issues, attribute problems, scoped-value gaps, URL concerns, customer/order context issues, inventory assumptions, and custom-data requirements before Full Migration.

**Who is responsible for final Magento migration verification?**

The customer is responsible for final result verification and migration outcome, regardless of service model. Next-Cart can support migration execution, configuration, troubleshooting, or Custom Service work based on the selected scope, but the customer must confirm that the Target Store is correct for business use.
