# Magento Pre-Migration Preparation Checklist

Magento Open Source preparation should turn a source-store inventory into a target-operating plan. The work is not limited to collecting products, customers, orders, CMS Pages, Blog Posts, images, coupons, reviews, and redirects. The stronger preparation goal is to confirm how those records should behave inside Magento’s catalog structure, attribute system, website/store/store-view hierarchy, URL model, inventory setup, customer groups, order history, and extension ecosystem.

Magento is flexible, but that flexibility makes early evidence important. A merchant can have a clean source export and still need deeper decisions about configurable products, attribute sets, localized values, URL keys, custom options, extension-owned fields, external IDs, inventory freshness, and target-side configuration. Preparation should identify those decisions before Full Migration, not after the target store already contains difficult-to-review data.

### Define the Magento Open Source Target Structure <a href="#define-the-magento-open-source-target-structure" id="define-the-magento-open-source-target-structure"></a>

The first preparation task is to confirm the Magento Open Source structure that will receive the migrated data. Magento can support websites, stores, and store views, and those layers may affect catalog assignment, localization, configuration, URLs, content visibility, customer context, and validation. The merchant should not assume that one source storefront automatically maps into one flat Magento store.

| Preparation area  | What to confirm                                                                                                             | Why it matters                                                                                        |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Website structure | Whether the target needs one website or separate websites for brands, regions, currencies, tax contexts, or business units. | Website decisions can affect catalog scope, customer context, configuration, and future operations.   |
| Store structure   | Whether products and categories should support one storefront or several storefront experiences.                            | Store decisions affect navigation, root categories, merchandising, and operational ownership.         |
| Store views       | Whether language, localization, metadata, URLs, and content require store-view-specific values.                             | Store views affect localized names, descriptions, metadata, URL keys, and storefront-specific review. |
| Root categories   | Which category tree belongs to each storefront.                                                                             | Root category planning affects navigation, discovery, product assignment, and URL planning.           |
| Target readiness  | Whether the Magento environment is staging, development, or launch-bound production.                                        | The environment status affects confidence in Demo Migration and Full Migration review.                |

This target structure should be documented before catalog mapping begins. Structural decisions made after migration can require repeated cleanup, remapping, reindexing, or additional validation. Magento preparation is more reliable when the merchant knows which storefront context each product, category, page, URL, and localized value is expected to serve.

### Prepare Product-Type Evidence <a href="#prepare-product-type-evidence" id="prepare-product-type-evidence"></a>

Product preparation should begin with representative examples, not only product counts. Magento product type has migration significance because each type affects SKU behavior, inventory, pricing, product-page display, order lines, and maintenance. Source stores may use terms such as variant, option, bundle, kit, package, add-on, service, downloadable file, or custom product builder, but those terms do not automatically map to Magento product types.

Prepare a product evidence set that includes ordinary and difficult catalog patterns:

| Product sample                                                 | Why it matters before migration                                                                           |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Simple product with one SKU                                    | Establishes baseline mapping for name, SKU, price, tax class, images, categories, stock, and URL key.     |
| Product with size, color, material, or other SKU-level choices | Tests whether a configurable product with associated simple products is appropriate.                      |
| Kit, bundle, package, or build-your-own product                | Exposes whether bundle logic, grouped relationships, Custom Service, or target-side rebuilding is needed. |
| Virtual or service product                                     | Clarifies fulfillment, weight, shipping, tax, and order-history expectations.                             |
| Downloadable product                                           | Clarifies file, link, access, historical order, and post-purchase expectation handling.                   |
| Product with custom options or personalization                 | Clarifies whether values should be custom options, attributes, or custom-handled data.                    |
| Extension-controlled product                                   | Identifies module-owned behavior that may not belong to standard migration scope.                         |

Magento configurable products deserve special preparation. A configurable product may appear as one storefront product while each selectable variation is a separate simple product with its own SKU and inventory meaning. That means the merchant should prepare child SKU examples, variation attributes, stock values, images, price behavior, and order-line examples before approving the target catalog structure.

Product-type evidence should also include products that should not be migrated exactly as they exist in the source platform. Some legacy product builders, obsolete bundles, abandoned add-ons, or old app-generated options may be better rebuilt, simplified, excluded, or reviewed through Custom Service rather than copied into Magento as clutter.

### Clean Attributes and Attribute Sets Before Mapping <a href="#clean-attributes-and-attribute-sets-before-mapping" id="clean-attributes-and-attribute-sets-before-mapping"></a>

Magento attributes can support product pages, search, layered navigation, comparison, merchandising, administration, reporting, and integrations. Attribute sets determine which attributes belong to different product families. Because of that, attributes should be treated as catalog governance, not as a dumping ground for every source field.

Prepare a source-field inventory and classify each field by purpose:

| Source-field purpose             | Preparation decision                                                                                             |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Customer-facing specification    | Preserve when the value helps buyers evaluate the product and can be displayed cleanly.                          |
| Search or filter value           | Normalize labels, units, casing, spelling, and value format before migration when possible.                      |
| Product comparison value         | Confirm whether the value is consistent enough to support comparison.                                            |
| Merchandising or promotion value | Confirm whether the value can support rules, campaigns, or product grouping.                                     |
| Administrative value             | Preserve only if staff still need it inside Magento.                                                             |
| External-system identifier       | Preserve intentionally when ERP, PIM, CRM, accounting, marketplace, shipping, or reporting workflows require it. |
| Obsolete or duplicated field     | Exclude, consolidate, or document before it becomes target clutter.                                              |
| Extension-owned or custom field  | Decide whether supported mapping, an Add-on, Custom Service, or external-system handling is required.            |

Attribute-set preparation should be practical. A broad catalog may need separate attribute sets for apparel, parts, electronics, downloadable products, spare parts, service products, technical components, or industry-specific product families. Too few attribute sets can make staff maintain irrelevant fields. Too many can fragment governance and make future imports harder.

The preparation outcome should identify which attributes are global, which values need store-view review, which attributes should be filterable or searchable, which values need normalization, and which fields should not become visible customer-facing attributes.

### Prepare Categories, URLs, CMS Pages, and Blog Posts <a href="#prepare-categories-urls-cms-pages-and-blog-posts" id="prepare-categories-urls-cms-pages-and-blog-posts"></a>

Magento preparation should treat discovery and route continuity as migration planning, not as post-migration cleanup. Products can migrate correctly while navigation, URL keys, redirects, CMS Pages, Blog Posts, and high-value landing routes remain underprepared.

Before migration, prepare:

* the current category tree and intended Magento category tree;
* root category assignments for each storefront where relevant;
* products assigned to multiple categories;
* storefront-specific or language-specific category names and metadata;
* priority product, category, CMS Page, and Blog Post URLs;
* old redirects from prior redesigns, domain changes, or campaign routes;
* pages with embedded media, internal links, custom layouts, forms, or scripts;
* SEO-sensitive metadata, URL keys, canonical expectations, and route dependencies.

Magento Open Source preparation should distinguish content that can be migrated as supported records from content that depends on extensions, custom modules, page builders, theme logic, or external CMS behavior. CMS Pages and Blog Posts should not be assumed to behave the same way as source-platform pages if the source content was built by an app, plugin, module, or custom frontend.

| URL or content asset       | Preparation value                                                                 |
| -------------------------- | --------------------------------------------------------------------------------- |
| High-traffic product URLs  | Protects revenue and search continuity for important product pages.               |
| High-traffic category URLs | Helps preserve discovery paths and category-level SEO value.                      |
| CMS Pages                  | Identifies trust, policy, landing, and informational pages that matter at launch. |
| Blog Posts                 | Clarifies whether content should migrate, be rebuilt, redirected, or excluded.    |
| Redirect history           | Prevents old campaign or search routes from being forgotten.                      |
| Internal links             | Reveals whether migrated content will still point to correct target routes.       |

Redirect preparation should be prioritized. Not every old route deserves the same review, but valuable product, category, content, brand, and campaign routes should be identified before Full Migration.

### Prepare Customer Groups, Customers, and Order Context <a href="#prepare-customer-groups-customers-and-order-context" id="prepare-customer-groups-customers-and-order-context"></a>

Magento customer and order preparation should preserve business meaning, not just record presence. Customer groups can affect discounts, tax class, segmentation, reporting, or operational treatment. Source platforms may store buyer roles, tags, wholesale markers, tax-exempt flags, loyalty status, CRM references, or membership data in ways that do not equal Magento customer groups.

Prepare customer examples that show the actual source condition:

| Customer example                 | Why it matters                                                                        |
| -------------------------------- | ------------------------------------------------------------------------------------- |
| Standard registered customer     | Confirms baseline contact, address, and account-history handling.                     |
| Guest buyer                      | Confirms order history remains readable without creating false account expectations.  |
| Customer with multiple addresses | Tests billing, shipping, country, region, and localization behavior.                  |
| Customer with group-like status  | Clarifies whether customer group, custom field, or Custom Service handling is needed. |
| Duplicate customer records       | Reveals cleanup or acceptance decisions before migration.                             |
| Customer with external ID        | Protects ERP, CRM, accounting, loyalty, marketplace, or support references.           |

Order preparation should include ordinary and exception orders. The merchant should prepare orders with configurable products, custom options, bundles, discounts, taxes, shipping methods, payment labels, invoices, shipments, refunds, comments, cancellations, and external references. Historical orders should remain useful for support and reporting, but they should not be confused with live Magento checkout, tax, shipping, or payment configuration.

Before migration, decide which historical details must be readable in Magento and which source behaviors belong to target-side configuration or custom handling. This is especially important for stores with nonstandard order statuses, custom fulfillment workflows, marketplace references, subscriptions, loyalty data, or ERP reconciliation requirements.

### Prepare Inventory and Fulfillment Assumptions <a href="#prepare-inventory-and-fulfillment-assumptions" id="prepare-inventory-and-fulfillment-assumptions"></a>

Inventory preparation should identify the system of record and the freshness requirement. Magento inventory behavior may involve SKU-level stock, stock status, sources, stocks, salable quantity, backorders, reservations, low-stock thresholds, and external systems. A simple product quantity is not enough for many Magento Open Source stores.

Prepare inventory evidence for:

* simple products with stock;
* child SKUs under configurable products;
* bundle or grouped-product examples;
* backordered, low-stock, out-of-stock, or preorder-like products;
* source warehouse, store, supplier, or marketplace stock fields;
* products controlled by ERP, PIM, warehouse, marketplace, or fulfillment integrations;
* stock values that should be refreshed close to launch.

| Inventory decision                         | Why it matters                                                                                       |
| ------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| Which system owns stock                    | Prevents the migration from carrying a stale snapshot when an external system controls availability. |
| Whether quantity should migrate            | Some stores need stock moved; others prefer fresh inventory setup near launch.                       |
| Whether multiple sources matter            | Source/stock planning affects fulfillment confidence and salable availability.                       |
| How configurable products are validated    | Child simple products may carry the inventory meaning.                                               |
| How backorders or reservations are handled | Availability behavior may need target-side configuration and testing.                                |

Inventory is launch-sensitive. If products, orders, and stock continue changing after an initial migration run, the plan should define whether later migration activity will be used to update newly added records and how affected stock and catalog samples will be revalidated.

### Identify Extensions, Custom Modules, and Integration Dependencies <a href="#identify-extensions-custom-modules-and-integration-dependencies" id="identify-extensions-custom-modules-and-integration-dependencies"></a>

Magento Open Source stores commonly depend on extensions, custom modules, theme-level behavior, direct database customizations, ERP systems, PIM systems, CRMs, accounting systems, marketplaces, search tools, loyalty systems, subscriptions, review systems, shipping platforms, or analytics. These dependencies should be identified before migration scope is accepted.

Create a dependency inventory that answers four questions:

| Dependency question                                    | What to document                                                                                                                   |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| Which system owns the data?                            | Extension, custom module, source platform, ERP, PIM, CRM, marketplace, accounting, or another outside system.                      |
| What business process uses it?                         | Product maintenance, pricing, customer service, fulfillment, reporting, SEO, merchandising, compliance, or integration continuity. |
| Does Magento Open Source have a supported destination? | Native record, supported field, Add-on candidate, Custom Service candidate, target-side setup, or exclusion.                       |
| What proof is needed after migration?                  | Sample product, order, customer, URL, field, integration reference, or workflow check.                                             |

Add-ons and Custom Service must remain separate. Add-ons can support defined filtering, mapping, or configuration needs within supported behavior. Custom Service should be reviewed when the migration involves unsupported extension data, Custom Platform handling, outside-system identifiers, custom fields, bespoke transformation, or custom migration logic adjustment.

This classification prevents a common preparation mistake: describing custom or extension-owned data as if it were an ordinary product, customer, or order field. The earlier the dependency is named, the easier it is to choose the correct service path and validation plan.

### Prepare Access, Backups, and Demo Migration Samples <a href="#prepare-access-backups-and-demo-migration-samples" id="prepare-access-backups-and-demo-migration-samples"></a>

Preparation should also cover practical inputs. The merchant should know which source access, Magento access, exports, media folders, database copies, URL lists, credentials, or integration reports are needed for the selected migration path. Backups and export copies should be retained so the team can compare what existed before migration with what appears in Magento.

Prepare access and evidence for:

* source admin access or export files;
* Magento target access and target environment status;
* database backup or export copy where available;
* product, category, customer, order, coupon, review, CMS Page, Blog Post, and media exports;
* URL and redirect lists;
* extension/module inventories;
* attribute and attribute-set references;
* inventory reports;
* customer group lists;
* custom field samples;
* representative screenshots or reports for important source behavior.

Demo Migration samples should be chosen for decision value. Include a simple product, configurable product, bundle-like product, product with custom options, localized product, priority category, high-value URL, customer group example, repeat customer, refunded or discounted order, extension-owned field, external ID, and inventory-sensitive SKU where relevant.

The purpose of Demo Migration is not only to preview data. It should prove whether the chosen preparation and service path can preserve Magento-specific meaning before Full Migration.

### Plan Launch-Window Migration Activity <a href="#plan-launch-window-migration-activity" id="plan-launch-window-migration-activity"></a>

Magento preparation should account for changes that happen between the first migration run and launch. Source stores often continue selling while the target store is being reviewed. Products, customers, orders, CMS Pages, Blog Posts, reviews, coupons, inventory, and URLs may change during that window.

The launch-window plan should identify whether the merchant expects to:

| Later migration need                                         | Preparation implication                                                                                                             |
| ------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| Add new source records created after the first migration run | Plan continuation and validation of newly added records.                                                                            |
| Continue with changed mapping, filtering, or configuration   | Validate the affected fields, filters, samples, and related records again.                                                          |
| Replace the earlier target result                            | Prepare for a new migration and a broader target review.                                                                            |
| Keep the same migration path and already recorded entities   | Preserve the rule that already recorded entities do not consume Entity Points again merely because another migration action occurs. |

Article-level preparation should not over-explain internal mechanics. The merchant needs to know the expected business outcome: whether new source records should be added, whether changed configuration should be applied, whether the target should be replaced, and what must be revalidated before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento Open Source preparation succeeds when the merchant gathers evidence for how the target store should actually operate. Product types, attributes, attribute sets, websites, stores, store views, categories, URLs, CMS Pages, Blog Posts, customers, customer groups, orders, inventory, extensions, custom modules, integrations, access, backups, Demo Migration samples, and launch-window activity all affect whether Full Migration can be reviewed confidently.

The strongest preparation package separates supported records from target-side setup, Add-ons, Custom Service, external systems, and excluded expectations. That discipline reduces rework, improves service-path selection, and gives the merchant a better chance of validating Magento Open Source as a usable target environment rather than a populated but uncertain database.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Magento Open Source migration?**

Start with the target structure, product-type evidence, and attribute strategy. Magento migration decisions depend heavily on how products, attributes, websites, stores, store views, categories, inventory, and URLs should behave after migration.

**Why are Magento product samples more important than product counts?**

Product counts show volume, but samples reveal structure. A configurable product, bundle-like product, downloadable product, localized product, or extension-controlled product can require different preparation even if the total catalog is small.

**Should all source fields become Magento attributes?**

No. Source fields should be classified by purpose. Values that help shoppers, administrators, search, filters, comparison, merchandising, reporting, or integrations may deserve attributes. Obsolete, duplicate, unsupported, or extension-owned fields may need exclusion, Add-ons, Custom Service, or external-system handling.

**When should inventory be prepared separately from catalog data?**

Inventory should be prepared separately when stock changes frequently, configurable child SKUs carry inventory meaning, multiple sources or warehouses matter, backorders are used, or an external system controls availability.

**How should extension or custom-module data be handled before migration?**

Create a dependency inventory. Supported filtering, mapping, or configuration may fit Add-ons. Unsupported extension records, custom fields, outside-system identifiers, bespoke transformations, or custom migration logic should be reviewed for Custom Service.
