# Magento Pre-Migration Preparation Checklist

Preparing for a Magento migration is not only a matter of exporting source-store data. Magento is a structured Target Platform where product types, attributes, attribute sets, website and store-view scope, customer groups, URL rewrites, inventory configuration, extensions, and custom code can affect how migrated data behaves after launch. Preparation should therefore create enough evidence to decide what can move through a standard migration path, what requires target-store configuration, what can be handled through Add-ons, and what should be reviewed through Custom Service.

A strong preparation process gives the migration team representative data, confirms the intended Magento structure, exposes unsupported or extension-owned logic early, and prevents Full Migration from becoming the first serious test of catalog behavior. The goal is not to make the source store perfect. The goal is to make migration assumptions explicit before data is moved at scale.

### Confirm the Magento Target Structure Before Data Transfer <a href="#confirm-the-magento-target-structure-before-data-transfer" id="confirm-the-magento-target-structure-before-data-transfer"></a>

Magento preparation should begin with the target-store structure. Products, categories, attributes, configuration settings, and localized values may apply at different levels of the website, store, and store-view hierarchy. If that hierarchy is still undecided, migrated data may land in the wrong scope or require avoidable rework after launch.

| Preparation area          | What to confirm before migration                                                          | Why it matters in Magento                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Websites                  | Whether the target store needs one website or multiple websites.                          | Website scope can affect top-level configuration and sales-channel planning.                      |
| Stores                    | Whether separate stores need different root categories or menus.                          | Store structure affects category and navigation planning.                                         |
| Store views               | Whether languages, regional views, or localized storefronts require separate store views. | Store-view scope can affect translated names, descriptions, URL keys, labels, and display values. |
| Catalog sharing           | Whether storefronts share the same catalog foundation or need different selections.       | Shared and separated catalog assumptions affect product visibility and category planning.         |
| Currency and localization | Which values are target configuration decisions rather than migrated records.             | Some localized behavior belongs to target configuration, not source-data transfer.                |

If the target structure is still uncertain, the migration should not be planned only around entity counts. A smaller store with multilingual scope may require more preparation than a larger single-store catalog because scope affects how many values must be mapped, inherited, overridden, or validated.

### Review Product Types and Catalog Relationships <a href="#review-product-types-and-catalog-relationships" id="review-product-types-and-catalog-relationships"></a>

Magento product preparation should focus on how products are supposed to behave after migration, not only on how many product rows exist in the source store. A source catalog may contain simple products, variants, kits, bundles, digital products, service products, grouped offers, custom options, or extension-driven product logic. Each case should be evaluated against the target Magento product model.

Before migration, prepare representative product samples for each major catalog pattern:

* simple products with standard price, quantity, images, categories, and descriptions;
* variant-style products with size, color, material, capacity, or other option values;
* products that should become configurable products with associated simple products;
* grouped or bundled selling patterns;
* downloadable or virtual products if the business sells digital files, memberships, services, or non-shipped items;
* products with custom options, personalization, engraving, add-on services, or conditional selections;
* products with related products, upsells, cross-sells, or other merchandising relationships;
* products with different visibility, status, tax class, pricing, or inventory behavior.

The preparation file should not only list product examples. It should explain why each sample is representative. For example, one configurable product with two colors is not enough if the live catalog also includes products with size/color combinations, swatches, disabled child SKUs, child-level inventory, and store-view-specific descriptions.

### Clean and Classify Attributes Before Mapping <a href="#clean-and-classify-attributes-before-mapping" id="clean-and-classify-attributes-before-mapping"></a>

Attributes deserve separate preparation because Magento attributes can support more than product display. They can affect product detail pages, search, layered navigation, comparison, promotions, reports, and product creation through attribute sets. Poor attribute preparation often creates target-store clutter: duplicated values, inconsistent filters, weak search behavior, confusing product pages, and hard-to-maintain attribute sets.

Attribute preparation should classify each source field before mapping:

| Attribute category         | Preparation question                                                                         | Recommended action                                                                                    |
| -------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Customer-facing attributes | Should shoppers see this value on the product page, filters, comparison, or search?          | Clean labels, normalize values, and decide whether the attribute should support navigation or search. |
| Operational attributes     | Does staff need this value for fulfillment, reporting, merchandising, or internal workflows? | Preserve where useful, but avoid exposing it unnecessarily on the storefront.                         |
| Variant-driving attributes | Does this value define configurable product choices such as size or color?                   | Normalize values before migration and test configurable products carefully.                           |
| Legacy attributes          | Does this field come from an old plugin, retired workflow, or obsolete source configuration? | Exclude, archive, or review before creating target clutter.                                           |
| Extension-owned attributes | Does the attribute depend on a source extension or custom module?                            | Review through Add-ons or Custom Service when standard mapping is not enough.                         |

Attribute cleanup should happen before Full Migration whenever possible. Inconsistent values such as `Blue`, `blue`, `Navy Blue`, `Navy`, and `Color: Navy` may look minor in a spreadsheet, but they can create poor layered navigation and weak catalog quality after migration. The target plan should define naming conventions, option values, storefront labels, filter usage, and attribute-set placement before the migration path is finalized.

### Prepare Category, Navigation, and URL Evidence <a href="#prepare-category-navigation-and-url-evidence" id="prepare-category-navigation-and-url-evidence"></a>

Magento category preparation should connect data structure to storefront discovery. Categories are not only containers for products. They can influence navigation, product discovery, merchandising, SEO, and store-specific root-category structure.

Before migration, prepare:

* the current source category tree;
* the intended Magento root categories and navigation structure;
* examples of products assigned to multiple categories;
* categories that should be excluded, merged, renamed, redirected, or rebuilt;
* category descriptions, images, metadata, and URL keys that should be preserved;
* obsolete seasonal, campaign, or hidden categories that should not be treated as active navigation;
* expected category behavior for each website, store, or store view.

URL preparation should happen at the same time as category preparation. Magento can use URL rewrites for product, category, CMS page, and custom routes. If URL continuity matters, the migration plan should include current source URLs, intended target URLs, redirect expectations, high-value pages, and launch validation priorities.

A URL plan is especially important when the source store has long-standing organic traffic, paid landing pages, affiliate URLs, indexed category pages, localized URLs, or URLs generated by platform-specific routing rules. The preparation should identify which URLs must be preserved exactly, which can redirect, and which can be retired without business risk.

### Prepare Customer and Order Context <a href="#prepare-customer-and-order-context" id="prepare-customer-and-order-context"></a>

Customer and order preparation should preserve business meaning without assuming that every historical behavior can become live target functionality. Customers may carry addresses, groups, tax implications, discount eligibility, company relationships, marketing consent, account status, password limitations, and external identifiers. Orders may carry historical payment, shipping, tax, discount, currency, status, fulfillment, and integration references.

For Magento migration planning, prepare customer and order samples that show:

* registered customers and guest-checkout records;
* customers with multiple addresses;
* customer groups that affect discounts, tax class, wholesale rules, or service workflows;
* B2B, reseller, member, or VIP account examples if relevant;
* orders with multiple products, discounts, taxes, shipping fees, refunds, cancellations, or partial fulfillment;
* orders with external IDs from ERP, shipping, marketplace, accounting, CRM, or customer service systems;
* records that should remain readable historically but do not need to power live checkout behavior.

Customer groups should be prepared as commercial context, not only as labels. If a group affects pricing, taxation, promotion, approval, or downstream operations, the migration plan should define how that meaning will be preserved or rebuilt in the target store.

### Review Inventory and Fulfillment Assumptions <a href="#review-inventory-and-fulfillment-assumptions" id="review-inventory-and-fulfillment-assumptions"></a>

Magento inventory preparation depends on the target inventory model. A single-warehouse store may need a simpler setup than a merchant with multiple warehouses, pickup locations, drop shippers, regional fulfillment rules, or separate stock availability by website.

Before migration, confirm:

* whether the target store will use a single source or multiple sources;
* whether stock should be mapped by website, warehouse, region, or fulfillment location;
* how source quantities relate to salable quantities;
* whether backorders, minimum quantity rules, stock status, or low-stock thresholds matter;
* whether inventory should be migrated for all products or only active saleable products;
* whether external inventory systems will overwrite migrated quantities after launch.

Inventory preparation should also identify which products should not be treated like ordinary physical inventory. Downloadable, virtual, bundle, grouped, made-to-order, preorder, dropshipped, or externally fulfilled products may require separate handling. The migration should not assume that every quantity in the source store has the same operational meaning in Magento.

### Identify Extension-Owned and Custom Data Early <a href="#identify-extension-owned-and-custom-data-early" id="identify-extension-owned-and-custom-data-early"></a>

Magento projects often involve extensions, custom modules, themes, integrations, or external systems. Some of these affect storefront behavior without owning transferable data. Others create custom fields, custom tables, customer attributes, product attributes, checkout rules, loyalty records, subscription records, quote data, marketplace IDs, reward points, or other information that may not fit a standard migration path.

Preparation should create an extension and customization inventory with practical business context:

| Item to review        | Preparation detail                                                                    | Likely migration implication                                                             |
| --------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Source extensions     | Name, purpose, owned fields, owned tables, and business use.                          | May require exclusion, Add-ons, manual rebuild, or Custom Service review.                |
| Target extensions     | Whether the target extension already exists and how it expects data.                  | Migration may depend on target-side configuration before testing.                        |
| Custom fields         | Field name, entity type, expected usage, and whether staff or customers rely on it.   | Standard mapping may be enough for some fields; custom logic may require Custom Service. |
| External identifiers  | IDs used by ERP, PIM, WMS, marketplace, accounting, CRM, or support tools.            | Should be preserved when they are needed for post-launch operations.                     |
| Custom business logic | Rules for pricing, checkout, fulfillment, permissions, personalization, or reporting. | Usually requires scope review rather than automatic transfer assumptions.                |

Custom Service should be considered when migration depends on unsupported structures, custom modules, source-specific business rules, outside-system identifiers, extension-owned records, or a Custom Platform source context. Add-ons may help with filtering, mapping, or data configuration, but they should not be described as a substitute for custom logic review.

### Secure Access, Backups, and Environment Readiness <a href="#secure-access-backups-and-environment-readiness" id="secure-access-backups-and-environment-readiness"></a>

Magento preparation also requires operational readiness. The migration cannot be validated properly if the target environment is unstable, incomplete, inaccessible, or missing required configuration.

Before Demo Migration or Full Migration, confirm:

* admin access for both source and Magento target stores;
* database, file, API, or connector access required for the approved migration path;
* target-store version, hosting environment, and deployment access if technical review is needed;
* media-folder access and image-handling expectations;
* backup coverage for the source store and target store;
* maintenance-window expectations for final migration activity;
* cache, indexing, and deployment responsibilities in the target environment;
* theme and extension installation status if migrated records depend on target behavior;
* payment, shipping, tax, email, and checkout configuration boundaries.

Backups should be verified before any material target-side change. Cache and index planning should also be understood, because Magento storefront behavior can appear incomplete when caches or indexes do not reflect recently changed catalog data. Preparation should identify who is responsible for target-side operational tasks so migration validation does not get confused with unfinished implementation work.

### Prepare a Demo Migration Review Set <a href="#prepare-a-demo-migration-review-set" id="prepare-a-demo-migration-review-set"></a>

Demo Migration is most valuable when the merchant prepares a review set before running it. A random sample can confirm that records move, but it may miss the patterns that matter most for a Magento launch.

A strong Magento Demo Migration review set should include:

* simple, configurable, grouped, bundle, virtual, and downloadable products where relevant;
* products with rich attributes, custom options, images, metadata, categories, and related products;
* products assigned to multiple categories or websites;
* multilingual or store-view-specific content;
* customer records from different customer groups;
* customers with multiple addresses;
* orders with taxes, discounts, shipping, refunds, cancellations, and unusual statuses;
* high-value URLs and SEO-sensitive product or category pages;
* inventory examples that represent the intended stock model;
* records connected to extensions, integrations, or custom fields.

The review set should include expected outcomes. For example, a configurable product sample should specify the expected parent product, associated simple products, visible options, child SKU inventory behavior, category placement, and store-view labels. Without expected outcomes, validation becomes subjective and late-stage corrections become harder to prioritize.

### Decide What Should Not Migrate <a href="#decide-what-should-not-migrate" id="decide-what-should-not-migrate"></a>

Preparation is also the right time to decide what should be excluded. Migrating every legacy value can create a worse Magento store: noisy attributes, obsolete categories, inactive products, broken media, duplicate customers, retired CMS pages, old promotional URLs, unused custom fields, and extension leftovers can all make the target store harder to operate.

Before Full Migration, classify questionable data into four groups:

| Data type                                      | Recommended decision                               |
| ---------------------------------------------- | -------------------------------------------------- |
| Valuable and structurally compatible           | Include in the approved migration scope.           |
| Valuable but needs mapping or filtering        | Review through Add-ons or target configuration.    |
| Valuable but structurally custom               | Review through Custom Service before approval.     |
| Obsolete, duplicated, or source-specific noise | Exclude, archive, or rebuild manually when needed. |

This decision is especially important for long-running Magento source stores, legacy Magento 1 stores, customized open-source platforms, and stores moving from heavily modified systems. A successful target store is not measured only by how much data moved. It is measured by whether the migrated data is usable, maintainable, searchable, and commercially meaningful inside Magento.

### Preparation Checklist Before Full Migration <a href="#preparation-checklist-before-full-migration" id="preparation-checklist-before-full-migration"></a>

Use the following checklist to determine whether the Magento migration is ready to move from planning and Demo Migration into Full Migration.

| Checklist area      | Ready condition                                                                                                                     |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Target structure    | Websites, stores, store views, root categories, and localization expectations are confirmed.                                        |
| Product model       | Representative product samples have been reviewed against Magento product types and relationship behavior.                          |
| Attributes          | Attribute labels, option values, storefront use, filter use, and attribute-set assumptions are cleaned or approved.                 |
| Categories and URLs | Category structure, URL keys, redirect expectations, and high-value pages are documented.                                           |
| Customers           | Customer groups, addresses, external identifiers, and commercial account meaning are understood.                                    |
| Orders              | Historical order readability and operational limitations are accepted before Full Migration.                                        |
| Inventory           | Single-source or multi-source stock assumptions are confirmed.                                                                      |
| Extensions          | Extension-owned data and custom fields are identified and assigned to exclusion, Add-ons, manual rebuild, or Custom Service review. |
| Access and backups  | Required access is available and source/target backup expectations are clear.                                                       |
| Demo review         | Demo Migration samples have been tested against expected outcomes.                                                                  |
| Launch boundary     | Data migration responsibilities are separated from theme, checkout, payment, shipping, tax, and post-launch implementation tasks.   |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento migration preparation should create a clear operating picture before data moves at scale. The most important preparation work is not a generic export checklist. It is the disciplined review of target scope, product structure, attributes, customer groups, inventory behavior, URLs, extensions, access, backups, and validation samples.

A well-prepared Magento migration reduces avoidable rework because the target store has already been interpreted as Magento: a scoped, configurable, extensible commerce system where migrated records must become usable storefront and operational data.

Plan your Magento migration with Next-Cart to confirm the right migration scope, identify Add-ons or Custom Service needs early, and validate representative source data before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Should I clean Magento attributes before migration?**

Yes, especially when attributes will affect product pages, search, layered navigation, comparison, promotions, or staff workflows. Inconsistent names and option values can create confusing filters and poor catalog quality after migration.

**Do I need to prepare store views before migrating multilingual data to Magento?**

Yes. Store views should be planned before migration when translated names, descriptions, labels, URLs, or localized storefront values need to be preserved in the target store.

**Should every source extension field be migrated to Magento?**

No. Extension-owned fields should be reviewed for business value and structural compatibility. Some fields can be mapped, some should be excluded, and some may require Custom Service when they depend on custom logic or unsupported structures.

**What samples should I check in Demo Migration for Magento?**

Choose samples that represent the real catalog and operational complexity: configurable products, rich attributes, store-view content, customer groups, order history, URLs, inventory cases, and extension-related data.

**Are backups part of migration preparation?**

Yes. Backups and access readiness should be confirmed before material migration activity or target-side changes. They help protect the source and target stores and reduce operational risk during testing and launch preparation.
