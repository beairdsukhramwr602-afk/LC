# Magento Validation Priorities

Magento validation should prove that migrated records work inside Magento’s catalog, scope, inventory, URL, customer, order, and content structures. Record counts are useful supporting evidence, but they do not prove that the migrated Target Store is ready for launch.

A Magento store can show the expected number of products, customers, orders, categories, CMS Pages, or Blog Posts while still failing at product-type behavior, attribute usability, store-view visibility, salable quantity, URL continuity, customer-group context, content rendering, or extension-dependent workflows. Validation should therefore focus on whether the Target Store can support the customer experience and operational workflows the business needs after launch.

Magento validation should be representative, evidence-based, and business-aware. The strongest review checks the records most likely to expose platform-specific issues before launch-critical decisions are made.

### What Magento Validation Should Prove <a href="#what-magento-validation-should-prove" id="what-magento-validation-should-prove"></a>

Magento validation should confirm whether migrated data retains useful meaning inside the Target Store. The review should check not only whether records exist, but whether Magento can use those records correctly across storefront, admin, operations, and launch workflows.

| Validation area                      | What should be proven                                                                                                                                         | Why it matters                                                                                                            |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Product behavior                     | Simple, configurable, grouped, bundle, virtual, downloadable, and other relevant products behave as expected.                                                 | Magento product meaning depends on product type, child relationships, options, inventory, media, and storefront behavior. |
| Attribute structure                  | Attributes, option values, attribute sets, and frontend settings support display, search, filtering, comparison, merchandising, or operations where required. | Attribute data can be present but unusable if values, sets, labels, or storefront settings are not aligned.               |
| Website, store, and store-view scope | Products, categories, content, URLs, prices, language values, and visibility are checked under the correct scope.                                             | A value that looks correct in the default admin view may be wrong for another website, store, language, or store view.    |
| Category and navigation behavior     | Categories, root categories, product assignments, menu behavior, and storefront discovery paths match the launch plan.                                        | A catalog can migrate at record level while navigation and buyer discovery remain incomplete.                             |
| Inventory and availability           | Quantity, stock status, salable behavior, sources, and storefront availability are reviewed for representative products.                                      | Magento inventory validation must prove whether products can be sold correctly, not only whether quantity fields exist.   |
| URLs and SEO-sensitive paths         | Product, category, CMS Page, Blog Post, media, metadata, and redirect behavior support continuity where included in scope.                                    | URL and metadata issues can affect customers, search engines, paid campaigns, internal links, and analytics after launch. |
| Customer and order context           | Customer profiles, addresses, groups, orders, statuses, totals, taxes, shipping, discounts, and payment references remain understandable.                     | Support and operations teams need historical data to retain practical value.                                              |
| Extension and custom data            | Custom fields, extension-owned data, outside-system identifiers, and agreed Custom Service items are checked separately.                                      | Magento projects often fail at custom or extension boundaries, not at ordinary entity transfer.                           |

Validation should classify findings into practical outcomes: passed, expected Magento difference, target configuration work, mapping concern, Add-on-related issue, Custom Service item, manual business decision, or launch-blocking issue.

### Validate Product Types and Catalog Behavior <a href="#validate-product-types-and-catalog-behavior" id="validate-product-types-and-catalog-behavior"></a>

Magento product validation should start with records that represent the store’s real selling complexity. A simple product can prove basic transfer, but it does not prove that configurable products, grouped products, bundle products, downloadable products, virtual products, custom options, or child-SKU relationships were interpreted correctly.

#### Product-type samples <a href="#product-type-samples" id="product-type-samples"></a>

The validation sample should include each product type that matters to the launch. Configurable products deserve particular attention because the parent product, child simple products, option labels, SKUs, images, prices, stock behavior, and storefront selection logic all need to remain understandable.

Bundle and grouped products should be checked for relationship meaning, purchasability, buyer choice, and order-line readability. Downloadable and virtual products should be reviewed for non-physical fulfillment expectations, delivery context, and order interpretation.

A product-type review should answer three questions:

* does the product appear in Magento under the expected product type;
* does the product behave correctly on the storefront and in the admin area;
* do related child products, options, media, inventory values, prices, and order lines preserve useful meaning.

#### Product visibility and sellable state <a href="#product-visibility-and-sellable-state" id="product-visibility-and-sellable-state"></a>

Magento validation should include product status, visibility, website assignment, category assignment, price, media, inventory, and storefront availability. A migrated product can exist in the admin area while remaining hidden from buyers because visibility, website assignment, category placement, stock status, or scope configuration is incomplete.

The review sample should include ordinary products, high-revenue products, variant-heavy products, out-of-stock products, recently updated products, products assigned to multiple categories, and products with complex media or option structures. Products that drive merchandising, advertising, or SEO should be checked before lower-value records.

### Validate Attributes, Attribute Sets, and Option Values <a href="#validate-attributes-attribute-sets-and-option-values" id="validate-attributes-attribute-sets-and-option-values"></a>

Magento attributes can shape product display, layered navigation, search, comparison, sorting, merchandising, reporting, promotions, and operational workflows. Validation should therefore check attribute behavior, not only attribute presence.

| Attribute proof area   | Validation focus                                                                                                                          | Failure signal                                                                                     |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Attribute sets         | Products are assigned to suitable attribute sets for their product families.                                                              | Important fields are missing, irrelevant fields appear, or product management becomes inefficient. |
| Option values          | Select, multiselect, dropdown, and swatch values are clean and consistent.                                                                | Duplicate labels, inconsistent values, broken swatches, or misleading filter options appear.       |
| Frontend display       | Customer-facing attributes appear only where they should.                                                                                 | Technical values appear publicly, or merchandising values are hidden from shoppers.                |
| Search and filtering   | Attributes intended for search, layered navigation, comparison, or sorting behave correctly.                                              | Buyers cannot filter by critical product properties or see confusing filter choices.               |
| Operational attributes | Supplier values, external identifiers, warehouse values, compliance fields, or internal references remain usable where included in scope. | Staff or connected systems lose values needed for operations after launch.                         |

Attribute validation should be stricter for Magento than for simpler Target Platforms because Magento catalogs often use attributes as a core management layer. When the source store uses custom fields, plugin fields, ERP identifiers, PIM values, merchandising properties, or source-specific option labels, representative samples should be reviewed explicitly.

### Validate Website, Store, and Store-View Scope <a href="#validate-website-store-and-store-view-scope" id="validate-website-store-and-store-view-scope"></a>

Magento scope validation should prove that data appears in the correct website, store, and store-view context. A value that looks right in one scope may be missing, translated differently, priced differently, assigned differently, or hidden in another scope.

Validation should check:

* website assignment for products and sales-channel expectations;
* store-level category roots and navigation structures;
* store-view names, languages, localized product text, localized category text, CMS Pages, and Blog Posts;
* scope-specific URLs, URL keys, metadata, prices, visibility, and configuration-sensitive values;
* whether data intentionally shared across scopes is not accidentally duplicated, split, or overwritten;
* whether products that should be available in selected stores are actually visible and purchasable in those stores.

For a single-store Magento project, this review may be straightforward. For a multi-website, multi-store, or multilingual Magento project, scope validation should be one of the highest-priority launch checks. The pass condition is not that every scope has identical data. The pass condition is that each scope reflects the intended buyer experience and business operating model.

### Validate Categories, Navigation, and Storefront Discovery <a href="#validate-categories-navigation-and-storefront-discovery" id="validate-categories-navigation-and-storefront-discovery"></a>

Category validation should confirm whether Magento can use migrated category data to support discovery. Counts alone do not prove that navigation is usable.

The review should include root categories, category hierarchy, product assignments, category names, URL keys, metadata, category images, landing content, menu behavior, and visibility rules where relevant. Products that should appear in multiple categories should be checked for correct placement. Products that should remain hidden, inactive, or outside navigation should also be checked.

Magento validation should include buyer-facing discovery paths. A reviewer should be able to start from storefront navigation, reach important categories, apply expected filters, open priority product pages, and confirm that category-product relationships match the launch plan.

### Validate Inventory, Stock, and Availability <a href="#validate-inventory-stock-and-availability" id="validate-inventory-stock-and-availability"></a>

Inventory validation should prove whether migrated products can be sold correctly. Quantity fields are not enough. Magento inventory behavior can involve stock status, sources, stocks, salable quantity, reservations, website assignment, backorder expectations, and external stock synchronization.

| Inventory check                 | What to validate                                                                                             | Why it matters                                                                               |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| Single-source inventory         | Product quantities, stock status, and storefront availability match launch expectations.                     | Basic quantity transfer still needs sellable-state proof.                                    |
| Multi-source inventory          | Source assignment, stock assignment, and website-level availability are checked for representative products. | Products may have quantity but still fail availability expectations in the storefront.       |
| Configurable products           | Parent visibility and child-product stock behavior support buyer selection.                                  | A configurable product can display incorrectly if child product availability is not aligned. |
| Out-of-stock behavior           | Hidden, visible, backorder, or notify behavior matches the launch plan.                                      | Inventory settings can affect merchandising and customer expectations.                       |
| External inventory dependencies | ERP, warehouse, marketplace, or fulfillment identifiers remain usable where included in scope.               | Connected systems may depend on values that are not visible in ordinary storefront checks.   |

If the final inventory source of truth will be connected after migration, validation should document what can be proven immediately and what must be retested after the integration is active.

### Validate URLs, Redirects, Metadata, and SEO-Sensitive Records <a href="#validate-urls-redirects-metadata-and-seo-sensitive-records" id="validate-urls-redirects-metadata-and-seo-sensitive-records"></a>

Magento URL validation should focus on paths with business value and continuity risk. URL counts do not prove that priority paths remain safe. A few broken high-value URLs can create more launch risk than many low-value differences.

Validation should include:

* priority product URLs;
* priority category URLs;
* CMS Page and Blog Post URLs;
* localized or store-view-specific URLs;
* URL keys and generated paths;
* redirects for high-value legacy URLs where included in scope;
* canonical, metadata, and internal-link expectations where relevant;
* marketing, paid campaign, affiliate, email, or analytics-sensitive landing pages.

Some URL differences are expected when moving to Magento because the Target Platform may generate or structure paths differently. The validation task is to decide which differences are acceptable, which need target configuration, and which must be corrected before launch because they affect revenue, SEO, campaigns, or customer access.

### Validate Customers, Customer Groups, and Orders <a href="#validate-customers-customer-groups-and-orders" id="validate-customers-customer-groups-and-orders"></a>

Customer validation should confirm whether accounts remain recognizable and useful in Magento. The review should include names, emails, addresses, phone numbers, customer-group assignment, account status where relevant, newsletter or communication values where included in scope, and any external identifiers needed by support or connected systems.

Customer groups deserve special attention because they can affect discounts, tax class, segmentation, wholesale behavior, B2B-like workflows, and reporting assumptions. A migrated customer may appear complete but still lose commercial meaning if the group assignment or price/tax context changes.

Order validation should confirm historical readability. Magento order review should include customer links, guest orders, order items, configurable-product order lines, statuses, dates, totals, discounts, taxes, shipping, payment references, comments, invoices, shipments, credit memos, and any custom fields included in scope.

| Order sample                                         | Why it should be reviewed                                                                     |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Recent completed orders                              | Confirms ordinary customer-service continuity.                                                |
| Canceled, refunded, or partially fulfilled orders    | Confirms exception cases remain understandable.                                               |
| Orders with discounts, taxes, or shipping complexity | Confirms commercial context, not only item lines.                                             |
| Orders involving configurable or bundle products     | Confirms product relationship readability in history.                                         |
| Guest orders and registered-customer orders          | Confirms customer linkage differences.                                                        |
| Orders with external references                      | Confirms ERP, payment, fulfillment, marketplace, or support-system continuity where included. |

Historical orders do not need to become newly executable transactions. They need to remain readable, searchable, and useful for customer service, accounting reference, reporting, and operational history according to the approved migration scope.

### Validate CMS Pages, Blog Posts, Media, and Content <a href="#validate-cms-pages-blog-posts-media-and-content" id="validate-cms-pages-blog-posts-media-and-content"></a>

Content validation should confirm that migrated CMS Pages, Blog Posts, media references, metadata, links, and formatting remain usable in Magento. Content-heavy stores should not validate content as an afterthought, because pages and posts often carry SEO traffic, policy information, buying guidance, landing-page value, and customer-support context.

Validation should check representative content by business value, not only by count. Important examples include home or landing content, policy pages, buying guides, brand pages, high-traffic Blog Posts, embedded images, internal links, metadata, and pages with forms, scripts, widgets, or extension-dependent content.

When content depends on themes, page builders, widgets, or extensions, validation should separate migrated content from target rendering. Some content differences may require manual rebuild, theme configuration, Custom Service review, or post-migration editorial work.

### Validate Add-ons, Custom Service Items, and Extension Data Separately <a href="#validate-add-ons-custom-service-items-and-extension-data-separately" id="validate-add-ons-custom-service-items-and-extension-data-separately"></a>

Magento stores frequently depend on extensions, custom modules, custom tables, or connected systems. Validation should explicitly separate standard migrated entities from custom or extension-dependent behavior.

Add-ons should be validated according to what they were selected to do:

* a Data Filter Add-on should be checked against the intended inclusion or exclusion rule;
* Advanced Data Mapping should be checked against the expected field, option, status, relationship, or target value;
* Advanced Data Configure should be checked against the intended compatible target-configuration outcome;
* Tailored Add-ons or Custom Add-ons should be checked against the approved adjustment, not against assumptions outside scope.

Custom Service validation should include agreed custom fields, extension-owned data, outside-system identifiers, custom business rules, custom product relationships, custom order fields, ERP/PIM/WMS references, marketplace references, subscription or loyalty data, and any bespoke mapping logic included in scope.

These checks should remain separate because Add-ons and Custom Service solve different planning problems. Add-ons shape compatible migration work. Custom Service handles bespoke requirements, Custom Platform context, unsupported structures, custom logic, or outside-system continuity.

### Build a Representative Magento Validation Sample <a href="#build-a-representative-magento-validation-sample" id="build-a-representative-magento-validation-sample"></a>

A Magento validation sample should be small enough to review carefully and broad enough to expose structural risk. The sample should include records that represent the actual launch burden, not only clean records that are likely to pass.

Include examples such as:

* a simple product with ordinary category and inventory behavior;
* a configurable product with child simple products and distinct SKUs;
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
* extension-owned or custom fields included in scope.

The sample should be documented before validation starts. If a problem appears outside the sample, the sample should be expanded intentionally rather than replaced by random spot checks.

### Classify Findings Before Launch Decisions <a href="#classify-findings-before-launch-decisions" id="classify-findings-before-launch-decisions"></a>

Magento validation findings should be classified before launch readiness is approved. Unclassified findings create confusion because they mix true migration issues, expected Magento differences, target configuration needs, content decisions, business acceptance decisions, and custom-scope questions.

| Finding type                | Typical meaning                                                                                                                 | Recommended action                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Passed                      | The sample works as expected in Magento.                                                                                        | Document the result and continue validation.                              |
| Expected Magento difference | The Target Platform stores, displays, or manages data differently from the source store.                                        | Confirm that the business accepts the difference.                         |
| Target configuration work   | Magento setup, theme, extension, inventory, store-view, or URL configuration needs adjustment.                                  | Resolve in the Target Store, then retest the affected samples.            |
| Add-on-related issue        | Filtering, mapping, or configuration output does not match the selected Add-on expectation.                                     | Review the Add-on rule or mapping decision and retest.                    |
| Custom Service item         | The issue involves unsupported structures, custom logic, extension-owned data, or outside-system identifiers.                   | Review against the approved Custom Service scope before launch.           |
| Manual business decision    | The data is technically present, but the business must decide whether to rebuild, exclude, archive, or accept it.               | Record the decision and assign ownership.                                 |
| Launch blocker              | The issue affects customer experience, buying paths, fulfillment, support, SEO, or operational continuity at unacceptable risk. | Do not approve launch until the blocker is resolved or formally accepted. |

Additional Migration Options may become relevant when source-store activity continues after an earlier migration run, when configuration or mapping decisions change, or when the business intentionally needs a different migrated result before launch. The selected option should be validated with the same Magento-specific sample logic rather than treated as a shortcut around review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento validation should prove operational readiness, not only data presence. The strongest review checks whether migrated records behave correctly inside Magento product types, attribute sets, websites, stores, store views, inventory structures, URL rules, customer groups, order history, content areas, and custom or extension-dependent workflows.

A launch-ready Magento migration result should show that representative records work, expected platform differences are understood, launch-blocking issues are resolved, and unresolved items have clear ownership. Final approval should depend on evidence that the Target Store can support customer experience, operations, SEO-sensitive areas, and business continuity after launch.

### FAQs <a href="#faqs" id="faqs"></a>

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Is matching Magento record counts enough to approve a migration?**

No. Record counts are only supporting evidence. Magento validation should also prove product-type behavior, attribute usability, store-scope accuracy, inventory availability, URL continuity, customer-group meaning, order readability, content usability, and custom or extension-dependent outcomes.

**Which Magento products should be validated first?**

Start with products that represent real catalog complexity: configurable products with child SKUs, bundle or grouped products, high-value simple products, products assigned to multiple categories or websites, products with custom attributes, products with important URLs, and products affected by inventory or extension logic.

**Why should Magento store-view validation be handled separately?**

Store views can carry language, URL, content, metadata, visibility, and scope-specific values. A product or page may look correct in the default view while another store view has missing text, incorrect metadata, wrong visibility, or an unintended URL path.

**How should Magento inventory be validated?**

Inventory should be validated by sellable behavior. Check quantities, stock status, source assignment, stock assignment, salable quantity, website assignment, and representative storefront behavior for simple products, configurable-product children, out-of-stock products, and products connected to warehouse or fulfillment workflows.

**What happens if validation reveals custom or extension-owned data gaps?**

The finding should be classified before launch. Some gaps may require target configuration, Advanced Data Mapping, Advanced Data Configure, a Data Filter Add-on, Custom Service review, manual business acceptance, or exclusion from launch scope depending on the approved service plan.
