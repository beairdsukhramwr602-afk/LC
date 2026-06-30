# Magento Validation Priorities

Magento Open Source validation should prove that migrated data works inside the target Magento Open Source environment, not only that records exist. Record counts can confirm that expected entities arrived, but they do not prove that Magento Open Source can use those records correctly across catalog, storefront, admin, inventory, customer service, order history, SEO, and connected operations.

A Magento Open Source migration can look complete at a count level while still failing in product-type behavior, configurable product relationships, attribute usability, website/store/store-view scope, salable quantity, URL continuity, customer-group meaning, order readability, or extension-dependent workflows. Validation should therefore focus on practical readiness: whether the migrated result supports the buyer experience and operating model that the business expects after launch.

### What Magento Open Source Validation Should Prove <a href="#what-magento-open-source-validation-should-prove" id="what-magento-open-source-validation-should-prove"></a>

Magento Open Source validation should confirm that migrated records retain business meaning in the target Magento Open Source environment. The review should distinguish ordinary data presence from operational usability.

| Validation area                      | What should be proven                                                                                                                                        | Why it matters                                                                                                                             |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Product behavior                     | Simple, configurable, grouped, bundle, virtual, downloadable, and custom-option products behave as expected.                                                 | Magento Open Source product meaning depends on product type, associated products, SKUs, options, media, price, and inventory behavior.     |
| Attribute structure                  | Attributes, option values, attribute sets, labels, and frontend settings support the intended product management and storefront experience.                  | Attributes can exist but fail if they are assigned to the wrong set, hidden from buyers, duplicated, mislabeled, or unusable in filtering. |
| Website, store, and store-view scope | Products, categories, content, URLs, prices, visibility, and language values are correct under the intended scope.                                           | Magento Open Source values may differ by website, store, or store view, so the default admin view alone is not enough evidence.            |
| Category and navigation behavior     | Categories, root categories, product assignments, URL keys, visibility, and buyer discovery paths match the launch plan.                                     | A catalog can migrate successfully while navigation remains incomplete or misleading.                                                      |
| Inventory and availability           | Quantity, stock status, source assignment, stock assignment, salable quantity, and storefront availability behave correctly for representative products.     | Magento Open Source selling readiness depends on whether products can actually be found, selected, added to cart, and fulfilled.           |
| URL and SEO continuity               | Product, category, CMS Page, Blog Post, media, metadata, and redirect behavior protect priority paths where included in scope.                               | URL issues can affect search visibility, paid campaigns, analytics, internal links, and customer access.                                   |
| Customer and order context           | Customer profiles, addresses, customer groups, orders, statuses, totals, taxes, discounts, shipping, payment references, and comments remain understandable. | Support, accounting, and operations teams need historical records to retain practical value.                                               |
| Custom and extension data            | Custom fields, extension-owned records, outside-system identifiers, and Custom Service items are checked against approved scope.                             | Magento Open Source projects often fail at custom or extension boundaries rather than at ordinary entity transfer.                         |

A strong validation result should classify each finding as passed, expected Magento Open Source behavior, target configuration work, Add-on-related correction, Custom Service item, manual business decision, or launch blocker.

### Validate Product Types and Configurable Relationships <a href="#validate-product-types-and-configurable-relationships" id="validate-product-types-and-configurable-relationships"></a>

Magento Open Source product validation should start with products that represent real selling complexity. A simple product can confirm basic transfer, but it does not prove configurable, grouped, bundle, virtual, downloadable, or custom-option behavior.

Configurable products deserve careful review because the parent product and associated simple products must remain understandable together. Validation should check parent visibility, child SKUs, option labels, swatches, price behavior, images, stock behavior, category assignment, URL behavior, and order-line readability. The reviewer should confirm that buyers can choose options correctly and that staff can manage the parent-child relationship in Magento Open Source admin.

Bundle and grouped products should be checked for relationship meaning, purchasability, buyer choice, price behavior, inventory expectations, and order-line readability. Downloadable and virtual products should be reviewed for non-physical fulfillment context, file or service expectations, and order interpretation.

Product validation should answer these questions:

* does each priority product appear under the expected Magento Open Source product type;
* do associated products, option labels, SKUs, images, prices, and stock values preserve useful meaning;
* can buyers find, select, add to cart, and understand the product;
* can staff manage the product in the target Magento Open Source environment without losing essential operating context;
* do order records involving the product remain readable after migration.

The sample should include high-revenue products, variant-heavy products, products with unusual options, out-of-stock products, products assigned to multiple categories or websites, recently changed products, and products that support campaigns or SEO traffic.

### Validate Attributes, Attribute Sets, and Option Values <a href="#validate-attributes-attribute-sets-and-option-values" id="validate-attributes-attribute-sets-and-option-values"></a>

Magento Open Source catalogs often depend on attributes as a central management layer. Attribute validation should therefore review behavior, not only field existence.

| Attribute proof area          | Validation focus                                                                                                                  | Failure signal                                                                                     |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Attribute sets                | Products are assigned to suitable attribute sets for their product families.                                                      | Important fields are missing, irrelevant fields appear, or product management becomes inefficient. |
| Option values                 | Dropdown, multiselect, swatch, and select values remain clean and consistent.                                                     | Duplicate labels, broken swatches, inconsistent values, or confusing filter options appear.        |
| Storefront display            | Customer-facing values appear where they support product understanding.                                                           | Technical values appear publicly, or important merchandising values are hidden.                    |
| Search and layered navigation | Attributes intended for filtering, search, comparison, sorting, or merchandising behave correctly.                                | Buyers cannot filter by important product properties, or filters contain misleading options.       |
| Operational fields            | Supplier values, external IDs, compliance fields, warehouse references, or internal fields remain usable where included in scope. | Staff or connected systems lose data needed for daily operations.                                  |

Validation should be stricter when the source store uses custom fields, source-specific option labels, extension-owned attributes, ERP or PIM identifiers, technical merchandising fields, or values that drive filtering and search. Attribute issues should be separated from target theme or configuration issues so the right correction owner is clear.

### Validate Website, Store, and Store-View Scope <a href="#validate-website-store-and-store-view-scope" id="validate-website-store-and-store-view-scope"></a>

Magento Open Source scope validation should prove that migrated data appears in the correct website, store, and store-view context. A value that looks correct in one scope can be missing, translated differently, priced differently, assigned differently, or hidden in another scope.

Validation should check:

* website assignment for products and sales-channel expectations;
* store-level category roots and navigation behavior;
* store-view names, languages, localized product text, localized category text, CMS Pages, and Blog Posts;
* scope-specific URL keys, metadata, visibility, price, product descriptions, and content values;
* whether values intentionally shared across scopes remain shared;
* whether values intended to differ by scope remain distinct;
* whether products that should be available in selected stores are visible and purchasable there.

For a single-store Magento Open Source project, this review may be brief. For a multi-website, multi-store, or multilingual project, scope validation should be a launch-critical proof step. The pass condition is not identical data everywhere. The pass condition is that each scope reflects the intended buyer experience and operating model.

### Validate Categories, Navigation, and Storefront Discovery <a href="#validate-categories-navigation-and-storefront-discovery" id="validate-categories-navigation-and-storefront-discovery"></a>

Category validation should confirm that Magento Open Source can use migrated category data to support discovery. Counts alone do not prove that navigation is usable.

The review should include root categories, category hierarchy, product assignments, category names, URL keys, metadata, category images, landing content, menu behavior, and visibility rules where relevant. Products that should appear in multiple categories should be checked for correct placement. Products that should remain hidden, inactive, or outside navigation should also be checked.

A practical validation path should start from storefront navigation, reach important categories, apply expected filters, open priority product pages, and confirm that category-product relationships match the launch plan. If buyers cannot reach key products through normal paths, the issue should be treated as a discovery problem even when product records exist.

### Validate Inventory, Stock, and Sellable Behavior <a href="#validate-inventory-stock-and-sellable-behavior" id="validate-inventory-stock-and-sellable-behavior"></a>

Magento Open Source inventory validation should prove selling readiness. Quantity values by themselves are incomplete evidence because buyers interact with availability, salable quantity, stock status, website assignment, source assignment, and checkout behavior.

Review representative products for:

* stock status and storefront availability;
* quantity and salable quantity behavior;
* product-level stock settings;
* configurable-product parent and child stock behavior;
* website assignment and sales-channel expectations;
* source and stock assignment where multi-source inventory is used;
* out-of-stock products, backorder expectations, low-stock cases, and disabled products;
* products connected to warehouse, ERP, marketplace, or fulfillment workflows.

Inventory review should be especially careful when the Magento Open Source target Magento Open Source environment uses multiple sources, external fulfillment systems, reservations, or source selection behavior. The validation question is not only whether stock data moved. The question is whether Magento Open Source can sell, reserve, display, and support inventory in the way the business expects.

### Validate URLs, Redirects, and SEO-Sensitive Records <a href="#validate-urls-redirects-and-seo-sensitive-records" id="validate-urls-redirects-and-seo-sensitive-records"></a>

Magento Open Source URL validation should focus on priority paths and revenue-sensitive records. Full manual review of every path is rarely practical, but the sample should include high-traffic products, categories, CMS Pages, Blog Posts, campaign landing pages, brand pages, policy pages, and pages with strong search or advertising value.

The review should check:

* URL keys for products, categories, CMS Pages, and Blog Posts;
* canonical or preferred paths where relevant to the launch plan;
* redirect behavior for priority old URLs;
* metadata for important products, categories, and content pages;
* internal links between migrated content and catalog pages;
* media paths and embedded images;
* localized URLs where store views are used;
* whether acceptable Magento Open Source path differences have been documented.

Not every source URL should be expected to remain identical. Magento Open Source may structure paths differently depending on configuration and target design. Validation should decide which differences are acceptable, which need target configuration, and which must be corrected because they affect revenue, search, campaigns, analytics, or customer access.

### Validate Customers, Customer Groups, and Order History <a href="#validate-customers-customer-groups-and-order-history" id="validate-customers-customer-groups-and-order-history"></a>

Customer validation should confirm that accounts remain recognizable and useful. Review names, emails, addresses, phone numbers, customer-group assignment, account status where relevant, newsletter or communication values where included in scope, and external identifiers needed by support or connected systems.

Customer groups require special attention because they can affect segmentation, tax class, discounts, wholesale handling, reporting assumptions, and customer-service interpretation. A migrated customer may look complete but lose commercial meaning if the group assignment or related pricing context changes.

Order validation should prove historical readability. Magento Open Source order samples should include customer links, guest orders, order items, configurable-product order lines, statuses, dates, totals, discounts, taxes, shipping fees, payment references, comments, invoices, shipments, credit memos, cancellations, refunds, and any custom fields included in scope.

| Order sample                                               | Why it should be reviewed                                                                                 |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Recent completed orders                                    | Confirms ordinary customer-service continuity.                                                            |
| Canceled, refunded, or partially fulfilled orders          | Confirms exception cases remain understandable.                                                           |
| Orders with discounts, taxes, or shipping complexity       | Confirms commercial context, not only item lines.                                                         |
| Orders involving configurable, bundle, or grouped products | Confirms product relationship readability in history.                                                     |
| Guest orders and registered-customer orders                | Confirms customer linkage differences.                                                                    |
| Orders with external references                            | Confirms ERP, payment, fulfillment, marketplace, accounting, or support-system continuity where included. |

Historical orders do not need to become newly executable checkout events. They need to remain readable, searchable, and useful for customer service, accounting reference, reporting, and operational history according to the approved migration scope.

### Validate CMS Pages, Blog Posts, Media, and Content <a href="#validate-cms-pages-blog-posts-media-and-content" id="validate-cms-pages-blog-posts-media-and-content"></a>

Content validation should confirm that CMS Pages, Blog Posts, media references, metadata, internal links, and formatting remain useful in the target Magento Open Source environment. Content-heavy Magento Open Source migrations should not treat content as secondary because pages and posts often support SEO traffic, policy compliance, buying guidance, brand positioning, campaign landing pages, and customer-support workflows.

The validation sample should include high-value pages, policy pages, landing pages, buying guides, brand pages, high-traffic Blog Posts, embedded images, internal links, metadata, and content that depends on forms, widgets, page builders, scripts, or extensions.

When content depends on themes, widgets, page builders, or extensions, validation should separate migrated content from target rendering. Some differences may require theme configuration, manual rebuild, Custom Service review, or post-migration content work rather than treating every display issue as a migration failure.

### Validate Add-ons, Custom Service Items, and Extension Data Separately <a href="#validate-add-ons-custom-service-items-and-extension-data-separately" id="validate-add-ons-custom-service-items-and-extension-data-separately"></a>

Magento Open Source validation should separate standard migrated entities from Add-ons, Custom Service items, extension-owned data, and connected-system identifiers. Mixing these categories makes findings harder to resolve.

Add-ons should be validated according to their approved purpose:

* a Data Filter Add-on should be checked against the intended inclusion or exclusion rule;
* Advanced Data Mapping should be checked against the expected field, option, status, relationship, or target value;
* Advanced Data Configure should be checked against the intended compatible target-configuration outcome;
* Tailored Add-ons or Custom Add-ons should be checked against the approved adjustment.

Custom Service validation should focus on agreed custom fields, extension-owned records, outside-system identifiers, bespoke mapping rules, custom product relationships, custom order fields, ERP/PIM/WMS references, marketplace references, subscription or loyalty data, and Custom Platform interpretation where included in scope.

This separation protects launch decisions. Add-ons shape compatible migration work. Custom Service handles bespoke requirements, unsupported structures, custom logic, Custom Platform context, and outside-system continuity.

### Build a Representative Magento Open Source Validation Sample <a href="#build-a-representative-magento-open-source-validation-sample" id="build-a-representative-magento-open-source-validation-sample"></a>

A Magento Open Source validation sample should be small enough to review carefully and broad enough to expose structural risk. It should include records that represent the actual launch burden, not only clean examples that are likely to pass.

Include examples such as:

* a simple product with ordinary category and inventory behavior;
* a configurable product with associated simple products and distinct child SKUs;
* a bundle or grouped product if the catalog uses those product types;
* a downloadable or virtual product if the store sells non-physical items;
* products assigned to more than one website, store, store view, or category;
* products with important custom attributes, swatches, option values, or attribute-set behavior;
* products affected by multi-source inventory, warehouse logic, or external stock systems;
* high-value category, product, CMS Page, Blog Post, and landing-page URLs;
* customers from different customer groups;
* guest and registered-customer orders;
* refunded, canceled, discounted, or partially fulfilled orders;
* CMS Pages, Blog Posts, media-heavy content, and SEO-sensitive pages;
* extension-owned records, custom fields, or external IDs included in scope.

The sample should be documented before validation starts. If a problem appears outside the sample, expand the sample intentionally rather than replacing it with random spot checks.

### Revalidate After Additional Migration Options <a href="#revalidate-after-additional-migration-options" id="revalidate-after-additional-migration-options"></a>

Additional Migration Options may become relevant when the Source Platform remains active, new records appear after an earlier migration run, configuration or mapping decisions change, or the business intentionally needs a different migrated result before launch. These options should not be treated as a shortcut around validation.

After additional migration activity, revalidate the affected Magento Open Source areas:

| Follow-up situation                                                            | Revalidation priority                                                                                                                           |
| ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| New products, customers, orders, or Blog Posts are migrated for the first time | Confirm Entity Points capacity, record presence, relationships, storefront behavior, and historical readability for the new records.            |
| The last used configuration is continued                                       | Confirm that newly migrated records follow the previously approved mapping, filtering, and configuration expectations.                          |
| A new configuration is used                                                    | Recheck mapping-sensitive fields, attributes, store scope, URLs, inventory, customer groups, orders, and Add-on outcomes.                       |
| A new migration is performed for the same migration path                       | Confirm cleanup expectations, duplicate risk, Entity Points impact for newly migrated records, and validation ownership before launch approval. |
| Target configuration changes after testing                                     | Retest the records most affected by the change rather than relying on the earlier sample result.                                                |

New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated for the first time. Records already counted through the service license should not consume Entity Points again merely because the customer performs later additional migration activity for the same migration path.

### Classify Findings Before Launch Decisions <a href="#classify-findings-before-launch-decisions" id="classify-findings-before-launch-decisions"></a>

Magento Open Source validation findings should be classified before launch readiness is approved. Unclassified findings create confusion because they mix migration issues, expected Magento Open Source differences, target configuration needs, content decisions, Add-on concerns, custom-scope questions, and business acceptance decisions.

| Finding type                            | Typical meaning                                                                                                                        | Recommended action                                                                   |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Passed                                  | The sample works as expected in Magento Open Source.                                                                                   | Document the result and continue validation.                                         |
| Expected Magento Open Source difference | The Target Platform stores, displays, or manages data differently from the source store.                                               | Confirm that the business accepts the difference.                                    |
| Target configuration work               | Magento Open Source setup, theme, extension, inventory, store-view, or URL configuration needs adjustment.                             | Resolve in the target Magento Open Source environment, then retest affected samples. |
| Add-on-related issue                    | Filtering, mapping, or configuration output does not match the selected Add-on expectation.                                            | Review the Add-on rule or mapping decision and retest.                               |
| Custom Service item                     | The issue involves unsupported structures, extension-owned data, custom logic, Custom Platform context, or outside-system identifiers. | Review against the approved Custom Service scope before launch.                      |
| Manual business decision                | The data is technically present, but the business must decide whether to rebuild, exclude, archive, or accept it.                      | Record the decision and assign ownership.                                            |
| Launch blocker                          | The issue affects customer experience, buying paths, fulfillment, support, SEO, or operational continuity at unacceptable risk.        | Do not approve launch until the blocker is resolved or formally accepted.            |

Final approval should depend on evidence. A launch-ready result should show that representative Magento Open Source records behave correctly, known differences are understood, launch blockers are resolved, and unresolved items have clear ownership.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento Open Source validation should prove operational readiness, not only migrated data presence. The strongest review checks whether records behave correctly inside Magento Open Source product types, configurable relationships, attribute sets, websites, stores, store views, inventory structures, URL behavior, customer groups, order history, content areas, and custom or extension-dependent workflows.

A Magento Open Source migration result is ready for launch only when representative samples work, expected platform differences are accepted, follow-up migration activity has been revalidated, and launch-sensitive issues have owners. That evidence helps the business approve the target Magento Open Source environment with confidence rather than relying on counts alone.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is matching Magento Open Source record counts enough to approve a migration?**

No. Record counts are supporting evidence only. Magento Open Source validation should also prove product-type behavior, attribute usability, store-scope accuracy, inventory availability, URL continuity, customer-group meaning, order readability, content usability, and custom or extension-dependent outcomes.

**Which Magento Open Source products should be validated first?**

Start with products that represent real catalog complexity: configurable products with child SKUs, bundle or grouped products, high-value simple products, products assigned to multiple categories or websites, products with custom attributes, products with important URLs, and products affected by inventory or extension logic.

**Why should Magento Open Source store-view validation be handled separately?**

Store views can carry language, URL, content, metadata, visibility, and scope-specific values. A product or page may look correct in the default view while another store view has missing text, incorrect metadata, wrong visibility, or an unintended URL path.

**How should Magento Open Source inventory be validated?**

Inventory should be validated through sellable behavior. Check quantities, stock status, source assignment, stock assignment, salable quantity, website assignment, configurable-product children, out-of-stock products, and products connected to warehouse or fulfillment workflows.

**What should be revalidated after Additional Migration Options are used?**

Revalidate the affected Magento Open Source records and relationships, especially products, attributes, store scope, URLs, inventory, customers, orders, Blog Posts, Add-on outputs, custom fields, and extension-dependent data. New eligible records should be checked as first-time migrated records, while records already counted through the service license should not consume Entity Points again only because later additional migration activity occurs for the same migration path.
