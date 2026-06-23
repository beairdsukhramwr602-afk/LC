# Magento Pre-Migration Preparation Checklist

Magento preparation should turn a source-store inventory into a clear Target Store plan. The goal is not only to collect products, customers, orders, CMS Pages, Blog Posts, media, and redirects. The stronger goal is to confirm how those records should behave inside Magento after migration.

Because Magento uses product types, attributes, attribute sets, website/store/store-view scope, URL rewrites, inventory configuration, customer groups, and extension-driven data, preparation should happen before Full Migration begins. A store can have clean record exports and still require additional decisions if product relationships, scoped values, search filters, inventory assumptions, or custom fields are not ready.

### Confirm the Magento Target Structure <a href="#confirm-the-magento-target-structure" id="confirm-the-magento-target-structure"></a>

Start by confirming the Magento structure that will receive the migrated data. The target hierarchy should be settled early because it affects products, categories, content, customer context, URLs, configuration, and validation.

| Preparation area | What to confirm                                                                                                                   | Why it matters                                                                                 |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Websites         | Whether the Target Store needs one website or separate websites for brands, regions, currencies, tax behavior, or business units. | Website structure can affect catalogs, customer context, configuration, and future operations. |
| Stores           | Whether products and categories should support one storefront or several storefront structures.                                   | Store structure affects navigation, catalog presentation, and operational ownership.           |
| Store views      | Whether language, localization, metadata, URLs, and content need store-view-specific values.                                      | Store views affect how localized and storefront-specific values should be mapped and reviewed. |
| Root categories  | Which category tree belongs to each storefront.                                                                                   | Category preparation affects navigation, discovery, merchandising, and URL planning.           |
| Target status    | Whether the Magento environment is staging, development, or launch-bound production.                                              | Environment status affects confidence in Demo Migration and Full Migration review.             |

Magento preparation should avoid vague target assumptions such as “migrate everything first and organize later.” Structural decisions made after migration can require repeated review, remapping, or additional cleanup.

### Prepare Catalog and Product Evidence <a href="#prepare-catalog-and-product-evidence" id="prepare-catalog-and-product-evidence"></a>

Catalog preparation is one of the most important Magento readiness tasks. Source stores often describe product choices differently from Magento. Variant-like data, kits, bundles, product options, downloadable items, virtual products, grouped offers, and custom-order inputs should be reviewed before choosing the target product model.

Prepare a product evidence set that includes:

* simple products without option complexity;
* configurable product candidates with separate SKUs, prices, images, or stock values;
* grouped, bundle, virtual, and downloadable product candidates where relevant;
* products with personalized options or customer-entered values;
* products with technical specifications, compatibility data, size/color matrices, or spare-part relationships;
* products controlled by apps, modules, ERP data, PIM data, or custom scripts;
* products with important images, media galleries, downloadable files, or rich descriptions.

Product evidence should include real examples, not only totals. A catalog with 2,000 simple products may be easier to prepare than a catalog with 200 products that combine configurable relationships, custom attributes, store-view values, and extension-owned data.

### Clean Attributes and Attribute Sets Before Mapping <a href="#clean-attributes-and-attribute-sets-before-mapping" id="clean-attributes-and-attribute-sets-before-mapping"></a>

Magento attributes can affect product pages, layered navigation, search, comparisons, promotions, administration, reporting, and integrations. Preparation should therefore classify source fields by purpose before mapping them into Magento.

| Source-field condition           | Preparation action                                                                                     |
| -------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Customer-facing product detail   | Preserve if it helps product evaluation and can be displayed cleanly.                                  |
| Search or filter value           | Normalize labels, units, casing, and value formats before migration.                                   |
| Operational/admin value          | Confirm whether staff still need it in Magento.                                                        |
| Promotion or merchandising value | Confirm that the value is reliable enough to support rules or campaigns.                               |
| External-system identifier       | Preserve intentionally if used by ERP, CRM, accounting, shipping, marketplace, or reporting workflows. |
| Obsolete or duplicated field     | Exclude, consolidate, or document before it becomes target clutter.                                    |
| Extension-owned or custom field  | Review whether standard mapping, an Add-on, or Custom Service is required.                             |

Attribute sets should also be planned before migration. Broad catalogs may need different attribute sets for apparel, parts, electronics, downloadable goods, B2B supplies, spare-part products, or technical-specification families. Poor attribute-set preparation can make the Target Store harder to maintain even if the data transfer succeeds.

### Prepare Categories, URLs, CMS Pages, and Blog Posts <a href="#prepare-categories-urls-cms-pages-and-blog-posts" id="prepare-categories-urls-cms-pages-and-blog-posts"></a>

Magento category and URL planning should be prepared before migration because discovery and SEO continuity depend on more than record presence. Products should be assigned to the right categories, category paths should support intended storefront navigation, and high-value URLs should be identified before migration review begins.

Prepare the following before migration:

* current category tree and intended Magento category tree;
* products that belong to multiple categories;
* storefront-specific or language-specific category names and metadata;
* high-priority product, category, CMS Page, and Blog Post URLs;
* redirects from earlier redesigns, platform changes, or campaign routes;
* pages with internal links, embedded media, custom layouts, or forms;
* SEO-sensitive metadata, URL keys, canonical expectations, and old route dependencies.

Redirect preparation should be practical. Not every legacy route deserves equal attention, but high-traffic product pages, category pages, CMS Pages, Blog Posts, brand pages, and campaign destinations should be reviewed before Full Migration.

### Prepare Customer, Order, and Commercial Context <a href="#prepare-customer-order-and-commercial-context" id="prepare-customer-order-and-commercial-context"></a>

Customer and order records should be prepared with business context, not only exported as lists. Magento customer groups, tax assumptions, pricing eligibility, discounts, order statuses, invoices, shipments, refunds, comments, and support references can affect how staff interpret migrated records.

Before migration, confirm:

* which customer groups should exist in Magento and what they mean;
* whether customer-group assignment affects pricing, tax class, discounts, approvals, or reporting;
* whether customer passwords can be migrated or must be reset according to the source and target behavior;
* which order statuses should be preserved, mapped, relabeled, or excluded;
* whether historical invoices, shipments, refunds, comments, payment references, or fulfillment references carry operational value;
* whether external customer, order, subscription, loyalty, or ERP identifiers must be preserved.

If customer segmentation or order history supports service, compliance, reporting, or integrations, it should be part of preparation. Otherwise, migrated records may exist in Magento without enough context for staff to use them confidently.

### Prepare Inventory and Fulfillment Assumptions <a href="#prepare-inventory-and-fulfillment-assumptions" id="prepare-inventory-and-fulfillment-assumptions"></a>

Inventory preparation should confirm the system of record and the target behavior expected after migration. A simple quantity value may not fully represent Magento selling availability, especially when the source store uses warehouses, ERP-managed stock, marketplace stock, drop shipping, regional availability, or backorder logic.

Prepare inventory details such as:

* source of truth for stock quantities;
* whether Magento will use one stock source or multiple inventory sources;
* products with backorders, low-stock thresholds, safety stock, preorder behavior, or fulfillment exceptions;
* stock differences by website, store, warehouse, market, or sales channel;
* whether inventory should migrate during the main transfer or be refreshed close to launch;
* how inventory should be reviewed during Demo Migration.

Inventory should be treated as launch-sensitive data. If stock changes frequently, preparation should identify whether Additional Migration Options or a closer-to-launch data refresh is needed to reduce freshness gaps, followed by renewed review of affected records.

### Identify Extensions, Custom Fields, and Integration Dependencies <a href="#identify-extensions-custom-fields-and-integration-dependencies" id="identify-extensions-custom-fields-and-integration-dependencies"></a>

Magento migrations often involve data shaped by extensions, apps, modules, custom database tables, ERP systems, PIM systems, CRM systems, shipping platforms, accounting systems, marketplaces, search tools, loyalty programs, or subscriptions. Preparation should identify these dependencies before migration scope is confirmed.

Create a dependency inventory for:

* extension-owned product, customer, order, pricing, content, review, subscription, loyalty, or shipping data;
* custom fields that must remain visible or usable in Magento;
* external IDs used by ERP, CRM, accounting, shipping, marketplace, analytics, or customer-service systems;
* custom order statuses, approval stages, fulfillment stages, or support workflows;
* bespoke product logic, pricing logic, shipping logic, checkout logic, or reporting logic;
* data from a Custom Platform source that does not map cleanly into Magento standard structures.

Add-ons can support defined filtering, mapping, or configuration needs within supported behavior. Custom Service should be reviewed when the migration involves unsupported extension data, Custom Platform handling, outside-system identifiers, bespoke transformation, custom logic, or a target behavior that requires custom migration logic adjustment.

### Prepare Access, Backups, and Environment Controls <a href="#prepare-access-backups-and-environment-controls" id="prepare-access-backups-and-environment-controls"></a>

Migration preparation should make the source and target environments reachable, stable, and recoverable. Access gaps can delay extraction, media transfer, troubleshooting, or validation.

| Item              | What to prepare                                                                                                    | Why it matters                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Source access     | Admin, database, API, file, media, and connector access required for the selected migration path.                  | Incomplete access can prevent full extraction or media transfer.               |
| Target access     | Magento admin, API, database, file, hosting, deployment, and media access when needed.                             | Target access affects configuration, import, troubleshooting, and review.      |
| Backups           | Recent source and target backups, including database and media files where relevant.                               | Backups reduce recovery risk if configuration or import work must be reversed. |
| Security controls | Firewall rules, IP allowlists, CAPTCHA, two-factor access, hosting restrictions, and maintenance windows.          | Security controls can block migration activity if not prepared.                |
| Ownership         | Contacts for source platform, Magento target environment, hosting, SEO, ERP, theme, fulfillment, and integrations. | Clear ownership speeds issue resolution.                                       |

The Target Store should not be treated as ready only because it is accessible. It should also be stable enough for Demo Migration review, configured enough to represent the intended structure, and protected by backups or recovery options.

### Build the Demo Migration Review Set <a href="#build-the-demo-migration-review-set" id="build-the-demo-migration-review-set"></a>

Demo Migration preparation should select representative examples that expose Magento-specific behavior. The sample set should not include only simple products or easy records.

A strong review set includes:

* products from each major product type or selling pattern;
* configurable product candidates with representative option combinations;
* products with important attributes, attribute sets, images, and category assignments;
* products with localized values, store-view values, URL keys, and metadata;
* categories and navigation paths with high customer value;
* customer groups and customers with meaningful account context;
* orders with discounts, taxes, shipping, refunds, cancellations, comments, or external references;
* inventory examples with stock-sensitive selling behavior;
* CMS Pages, Blog Posts, and high-value content records;
* custom fields, extension-owned data, Custom Platform data, or outside-system identifiers.

Demo Migration results should be compared against the intended Magento behavior. Some differences may reflect legitimate target-side structure. Other differences may reveal mapping gaps, target configuration needs, Add-on requirements, Custom Service scope, or preparation items that must be settled before Full Migration.

### Decide What Must Be Ready Before Full Migration <a href="#decide-what-must-be-ready-before-full-migration" id="decide-what-must-be-ready-before-full-migration"></a>

Preparation is complete when the migration team can clearly explain what should migrate, how Magento should represent it, which examples will be reviewed, which risks remain, and which service-scope decisions are required.

| Readiness category                      | Examples                                                                                                                                                 | Recommended action                                      |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| Blocking before Full Migration          | Missing access, no backup, undecided target hierarchy, unclear product model, unsupported custom data, unreviewed high-value URL plan.                   | Resolve before Full Migration.                          |
| Should be settled before Full Migration | Attribute labels, attribute sets, category plan, customer-group meaning, inventory source of truth, representative Demo Migration samples.               | Resolve unless there is an agreed reason to proceed.    |
| Can continue during validation          | Minor content cleanup, low-risk product copy, small redirect refinements, non-critical merchandising adjustments.                                        | Track without blocking the main transfer.               |
| Requires service-scope review           | Custom fields, unsupported extension data, outside-system identifiers, Custom Platform behavior, bespoke transformation, unusual product or order logic. | Review for Add-ons, Managed Service, or Custom Service. |

A Magento migration should not proceed into Full Migration only because the record list is ready. It should proceed when the target structure, critical mapping assumptions, sample evidence, access, backup, and service-scope decisions are clear enough to support confident review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento preparation should create a practical migration operating plan before execution begins. The strongest preparation work confirms catalog structure, product behavior, attributes, attribute sets, store scope, URLs, customer and order context, inventory assumptions, extension dependencies, custom data, access, backups, and representative Demo Migration samples.

When these decisions are prepared before Full Migration, the Target Store is easier to review, service scope is easier to control, and Magento-specific issues can be identified before they create launch risk.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Should the Magento Target Store be fully configured before migration?**

The Target Store should be configured enough to support the intended migration structure, especially websites, stores, store views, categories, attributes, product types, access requirements, and review workflows. Some storefront polish can continue later, but core structure should not remain undecided before Full Migration.

**What Magento preparation usually takes the most time?**

Catalog structure and attributes often require the most preparation because they affect product behavior, layered navigation, search, product creation, and review quality. Multi-store scope, URL planning, inventory behavior, and extension-owned data can also require significant preparation.

**Do all source attributes need to be migrated into Magento?**

No. Attributes should be cleaned and classified before mapping. Useful customer-facing and operational attributes should be preserved appropriately, while obsolete, duplicated, legacy, or extension-dependent values should be reviewed before they create target clutter.

**When should Add-ons be considered during Magento preparation?**

Add-ons should be considered when the migration needs defined filtering, mapping, or configuration support beyond the standard path. If the need involves unsupported extension data, outside-system identifiers, Custom Platform handling, custom logic, or bespoke transformation, Custom Service may be more appropriate.

**Why prepare Demo Migration samples before migration begins?**

Representative samples help test Magento-specific outcomes early. They make it easier to identify product-model issues, attribute problems, scoped-value gaps, URL concerns, customer/order context issues, inventory assumptions, and custom-data requirements before Full Migration.
