# Magento Validation Priorities

Validation for a Magento migration should prove that migrated data can operate inside Magento’s catalog, scope, inventory, URL, customer, and order structures. Matching record counts are only a baseline. A Magento store can show the expected number of products, customers, or orders while still failing at product-type behavior, store-view visibility, attribute usability, salable quantity, URL continuity, customer-group context, or extension-dependent workflows.

A strong validation review should therefore combine entity-level checks with operational proof. Products should not only exist; they should behave as Magento products. Categories should not only be present; they should support navigation and catalog discovery. Customers and orders should not only be readable; they should remain useful for service, reporting, and business continuity. Any accepted gap should be documented before Full Migration, Recent Data Migration, or launch approval.

### What Magento Validation Should Prove <a href="#what-magento-validation-should-prove" id="what-magento-validation-should-prove"></a>

Magento validation should confirm whether the target store can support the intended launch experience. The review should cover both migrated records and the Magento structures that give those records meaning.

| Validation area                      | What should be proven                                                                                                                        | Why it matters                                                                                                                  |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Catalog and product types            | Simple, configurable, grouped, bundle, virtual, downloadable, and other relevant products behave as intended.                                | Magento product meaning depends on product type, child relationships, options, inventory handling, and storefront presentation. |
| Attribute and attribute-set logic    | Important attributes appear in the right places and support filtering, comparison, search, merchandising, or operational use where required. | Attribute data can be present but unusable if option values, attribute sets, or frontend settings are not aligned.              |
| Website, store, and store-view scope | Products, categories, content, URLs, prices, languages, and configuration-sensitive values are checked under the right scope.                | Magento scope can change what customers see across websites, stores, and store views.                                           |
| Category and navigation behavior     | Category assignments, root categories, menu behavior, and product visibility support the intended buyer journey.                             | A catalog can migrate correctly at record level while storefront discovery remains incomplete.                                  |
| Inventory and salable quantity       | Stock, sources, quantities, reservations, and availability behavior are reviewed for representative products.                                | Magento inventory validation must prove whether products are actually sellable, not only whether quantity fields exist.         |
| URLs and redirects                   | Product, category, CMS Page, and custom URL rewrite behavior supports SEO and user continuity.                                               | Incorrect URL handling can create crawl, ranking, redirect, and customer-access problems after launch.                          |
| Customers and orders                 | Customer profiles, addresses, groups, order items, statuses, totals, discounts, shipping, payment references, and notes remain readable.     | Customer service and operations teams need historical data to retain practical value.                                           |
| Extensions and custom data           | Extension-owned fields, custom module data, outside-system identifiers, and Custom Service items are checked separately.                     | Magento projects often fail at custom or extension boundaries, not at ordinary entity transfer.                                 |

Validation should not be treated as a single pass/fail count review. It should identify whether the migrated store is ready for launch, whether specific areas need configuration changes, and whether some issues should be handled through Add-ons, Custom Service, Re-Migration, or manual target-store setup.

### Catalog and Product-Type Validation <a href="#catalog-and-product-type-validation" id="catalog-and-product-type-validation"></a>

Magento catalog validation should start with products that represent the store’s real selling complexity. A simple product confirms basic product migration, but it does not prove that configurable, grouped, bundle, virtual, or downloadable products were interpreted correctly.

#### Product-type samples <a href="#product-type-samples" id="product-type-samples"></a>

The validation sample should include representative product types from the source store. Configurable products require particular attention because each option should remain tied to a separate simple product with its own SKU, inventory context, image behavior, and storefront selection logic. Bundle and grouped products should be checked for relationship meaning, purchasability, and buyer choice. Downloadable and virtual products should be reviewed for delivery expectations, non-physical fulfillment, and order interpretation.

A product-type review should answer three questions:

* does the product appear in Magento under the expected product type;
* does the product behave correctly on the storefront and in the Admin;
* do related child products, options, media, inventory values, and order lines remain understandable.

#### Product visibility and sellable state <a href="#product-visibility-and-sellable-state" id="product-visibility-and-sellable-state"></a>

Magento validation should include product status, visibility, website assignment, category assignment, price, media, inventory, and storefront availability. A migrated item can exist in the Admin while remaining hidden from buyers because visibility, website assignment, category placement, stock status, or scope configuration is incomplete.

The sample should include ordinary products, high-revenue products, variant-heavy products, out-of-stock products, recently updated products, and products with complex media or option structures. Products that drive merchandising, advertising, or SEO should be checked before lower-value records.

### Attribute, Attribute-Set, and Option Validation <a href="#attribute-attribute-set-and-option-validation" id="attribute-attribute-set-and-option-validation"></a>

Magento attributes can shape product display, search, layered navigation, comparison, reports, promotions, and operational workflows. Validation should therefore review how attribute data behaves, not only whether values migrated.

| Attribute proof area   | Validation focus                                                                                                     | Failure signal                                                                                       |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Attribute sets         | Products are assigned to suitable attribute sets for their product families.                                         | Important fields are missing, irrelevant fields appear, or teams cannot manage products efficiently. |
| Option values          | Select, multiselect, dropdown, and swatch values are clean and consistent.                                           | Duplicate values, inconsistent labels, or broken variant/filter behavior appear.                     |
| Frontend display       | Customer-facing attributes appear only where they should.                                                            | Technical values appear publicly, or merchandising values are hidden.                                |
| Search and filtering   | Attributes intended for search, layered navigation, comparison, or sorting behave correctly.                         | Buyers cannot filter by critical product properties or see misleading filter options.                |
| Operational attributes | Internal identifiers, supplier values, warehouse values, or compliance fields remain usable where included in scope. | Staff or connected systems lose required reference values.                                           |

Attribute validation should be stricter for Magento than for simpler target platforms because Magento catalogs often use attributes as a core management layer. When the source store used custom fields, plugin fields, ERP identifiers, or merchandising properties, the validation sample should include those examples explicitly.

### Website, Store, and Store-View Scope Validation <a href="#website-store-and-store-view-scope-validation" id="website-store-and-store-view-scope-validation"></a>

Magento scope validation should prove that data appears in the correct website, store, and store-view context. A value that looks correct in the default Admin view may still be wrong for another website, language, catalog root, or localized store view.

Validation should check:

* website assignment for products and sales-channel expectations;
* store-level category roots and navigation structures;
* store-view names, language content, localized product text, localized category text, and localized CMS Pages;
* scope-specific URLs, metadata, prices, configuration-sensitive values, and visibility;
* whether data intentionally shared across scopes is not accidentally duplicated or split.

For a single-store Magento project, this review may be straightforward. For a multi-website or multilingual Magento project, scope validation should be one of the highest-priority launch checks. The pass condition is not that every scope has identical data. The pass condition is that each scope reflects the intended buyer experience.

### Category, Navigation, and Storefront Discovery Validation <a href="#category-navigation-and-storefront-discovery-validation" id="category-navigation-and-storefront-discovery-validation"></a>

Category validation should confirm whether Magento can use migrated category data to support discovery. Counts alone do not prove that navigation is usable.

The review should include root categories, category hierarchy, product assignments, category names, URL keys, metadata, image or content blocks where relevant, and menu behavior. Products that should appear in multiple categories should be checked for correct placement. Products that should remain hidden, inactive, or out of navigation should also be checked.

Magento validation should include buyer-facing discovery paths. A tester should be able to start from the storefront navigation, reach important categories, apply expected filters, open important product pages, and confirm that category-product relationships match the launch plan.

### Inventory, Stock, and Availability Validation <a href="#inventory-stock-and-availability-validation" id="inventory-stock-and-availability-validation"></a>

Inventory validation should prove whether migrated products can be sold correctly. Quantity fields are not enough. Magento Inventory Management can use sources, stocks, salable quantity, reservations, and website-level sales-channel mapping.

| Inventory check         | What to validate                                                                           | Why it matters                                                                    |
| ----------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| Single-source inventory | Product quantities and stock status match launch expectations.                             | Basic quantity transfer still needs storefront availability proof.                |
| Multi-source inventory  | Source assignment, source quantities, stock aggregation, and website mapping are reviewed. | Incorrect source or stock setup can make products unavailable or oversellable.    |
| Salable quantity        | Representative products show the expected available quantity to customers.                 | Magento can distinguish physical source quantity from salable quantity.           |
| Reservations            | Products affected by cart/order activity are reviewed where relevant.                      | Reservations can influence apparent availability during checkout and fulfillment. |
| Non-physical products   | Virtual and downloadable products follow expected inventory and fulfillment rules.         | Not every product should be validated as a physical stock item.                   |

Inventory validation should include simple products, configurable-product children, high-volume SKUs, out-of-stock SKUs, backorder-sensitive SKUs, and products connected to warehouse or fulfillment processes. If inventory is ultimately controlled by an ERP, WMS, marketplace, or custom integration, validation should also confirm whether the migrated values are intended as launch data, historical reference, or temporary placeholders before synchronization.

### URL, SEO, and Redirect Validation <a href="#url-seo-and-redirect-validation" id="url-seo-and-redirect-validation"></a>

Magento URL validation should be handled as a launch-risk area. Product URLs, category URLs, CMS Page URLs, canonical behavior, store-view paths, and URL rewrites can affect both customer access and organic search continuity.

Validation should include high-value product URLs, category URLs, landing pages, CMS Pages, localized URLs, and URLs used in advertising, email, affiliates, marketplaces, or external systems. When a source URL cannot be preserved exactly, the launch plan should confirm the intended redirect, accepted difference, or manual SEO action.

A useful URL validation sample should include:

* products with changed names or URL keys;
* categories with deep hierarchy;
* products assigned to multiple categories;
* CMS Pages or landing pages that drive organic or campaign traffic;
* localized or store-view-specific URL paths;
* custom routes created for campaigns or legacy content.

The pass condition is practical continuity: important old paths should resolve as intended, important new paths should be indexable and customer-friendly, and known differences should be documented before launch.

### Customer, Customer-Group, and Order Validation <a href="#customer-customer-group-and-order-validation" id="customer-customer-group-and-order-validation"></a>

Customer validation should confirm whether accounts remain usable and meaningful in Magento. The review should include names, emails, addresses, phone numbers, customer-group assignment, account status where relevant, newsletter or communication values where included in scope, and any external identifiers needed by support or connected systems.

Customer groups deserve special attention because they can affect discounts and tax class. A migrated customer may appear complete but still lose commercial meaning if the group assignment, price expectation, tax behavior, or segmentation context changes.

Order validation should confirm historical readability. Magento order review should include customer links, guest orders, order items, configurable-product order lines, statuses, dates, totals, discounts, tax, shipping, payment references, comments, invoices, shipments, credit memos, and any custom fields included in scope.

| Order sample                                       | Why it should be reviewed                                                                     |
| -------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Recent completed orders                            | Confirms ordinary customer-service continuity.                                                |
| Canceled, refunded, or partially fulfilled orders  | Confirms that exception cases remain understandable.                                          |
| Orders with discounts, tax, or shipping complexity | Confirms commercial context, not only item lines.                                             |
| Orders involving configurable or bundle products   | Confirms product relationship readability in history.                                         |
| Guest orders and registered-customer orders        | Confirms customer linkage differences.                                                        |
| Orders with external references                    | Confirms ERP, payment, fulfillment, marketplace, or support-system continuity where included. |

Historical orders do not need to become newly executable transactions. They need to remain readable, searchable, and useful for customer service, accounting reference, and operational history according to the migration scope.

### CMS Pages, Blog Posts, Media, and Content Validation <a href="#cms-pages-blog-posts-media-and-content-validation" id="cms-pages-blog-posts-media-and-content-validation"></a>

Content validation should confirm that migrated CMS Pages, Blog Posts, media references, metadata, links, and formatting remain usable in Magento. Content-heavy stores should not validate content as an afterthought, because pages and posts often carry SEO traffic, policy information, buying guidance, landing-page value, or customer-support context.

Validation should check representative content pages by business value, not only by count. Important examples include home or landing content, policy pages, buying guides, brand pages, high-traffic Blog Posts, embedded images, internal links, metadata, and pages with forms, scripts, widgets, or extension-dependent content.

When content uses target-store themes, page builders, widgets, or extensions, validation should separate migrated content from target rendering. Some content differences may require manual rebuild, theme configuration, Custom Service review, or post-migration editorial work.

### Extension, Custom Service, and Integration Validation <a href="#extension-custom-service-and-integration-validation" id="extension-custom-service-and-integration-validation"></a>

Magento stores frequently depend on extensions, custom modules, custom tables, or connected systems. Validation should explicitly separate standard migrated entities from custom or extension-dependent behavior.

Custom Service validation should include agreed custom fields, extension-owned data, outside-system identifiers, custom business rules, custom product relationships, custom order fields, ERP/PIM/WMS references, marketplace references, subscription or loyalty data, and any bespoke mapping logic included in scope.

Add-ons should be validated according to what they were selected to do. A Data Filter Add-on should be checked against the intended inclusion or exclusion rule. Advanced Data Mapping should be checked against the expected field, status, option, or relationship result. Advanced Data Configure should be checked against the intended target configuration outcome. These checks should remain separate from Custom Service validation because Add-ons and Custom Service solve different planning problems.

If a required integration is not active yet, validation should still document what can be proven now and what must be retested after the integration is connected. No Magento launch should rely on assumed integration behavior when the relevant source data, target field, external identifier, or API-dependent workflow has not been checked.

### Demo Migration, Full Migration, Recent Data Migration, and Re-Migration Checks <a href="#demo-migration-full-migration-recent-data-migration-and-re-migration-checks" id="demo-migration-full-migration-recent-data-migration-and-re-migration-checks"></a>

Validation should be staged. Demo Migration should prove whether representative samples behave correctly before the merchant commits to Full Migration. Full Migration should prove that the complete selected scope moved as expected. Recent Data Migration should confirm that records created or updated after the Full Migration are added correctly before launch. Re-Migration should be considered when configuration, mapping, scope, or target setup changes make the prior result unsuitable.

| Stage                 | Validation priority                               | Acceptance question                                                                                                    |
| --------------------- | ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Demo Migration        | Representative complexity, not only easy records. | Do the selected samples prove that Magento can support the intended catalog, customer, order, URL, and scope behavior? |
| Full Migration        | Complete selected entity scope.                   | Did the full selected dataset migrate according to the approved service license and configuration decisions?           |
| Recent Data Migration | New or changed data after Full Migration.         | Are recent products, customers, orders, updates, and other in-scope records captured before launch?                    |
| Re-Migration          | Corrected configuration or mapping.               | Has the changed setup produced a result that is better aligned with the approved launch plan?                          |

Each stage should have a clear acceptance decision. Validation should not continue indefinitely without classifying findings as pass, target configuration work, manual business decision, Add-on-related adjustment, Custom Service item, or accepted difference.

### Building a Magento Validation Sample <a href="#building-a-magento-validation-sample" id="building-a-magento-validation-sample"></a>

A Magento validation sample should be small enough to review carefully and broad enough to expose structural risk. The sample should include records that represent the actual launch burden, not only clean records that are likely to pass.

Include examples such as:

* a simple product with ordinary category and inventory behavior;
* a configurable product with child simple products and distinct SKUs;
* a bundle or grouped product if the catalog uses those product types;
* a downloadable or virtual product if the store sells non-physical items;
* products assigned to more than one website, store, store view, or category;
* products with important custom attributes or attribute-set behavior;
* products affected by multi-source inventory or external stock systems;
* high-value category and landing-page URLs;
* customers from different customer groups;
* guest and registered-customer orders;
* refunded, canceled, discounted, or partially fulfilled orders;
* CMS Pages, Blog Posts, media-heavy content, and SEO-sensitive pages;
* extension-owned or custom fields included in scope.

The sample should be documented before validation starts. If a problem appears outside the sample, the sample should be expanded intentionally rather than replaced by random spot checks.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento validation should prove operational readiness, not only data presence. The strongest review checks whether migrated records behave correctly within Magento product types, attribute sets, website/store/store-view scope, inventory logic, URL rewrites, customer groups, order history, content structures, and custom or extension-dependent workflows. When validation findings are classified early, the merchant can decide whether to adjust target configuration, use Add-ons, request Custom Service review, perform Recent Data Migration, run Re-Migration, or accept a documented difference before launch.

Review Magento validation priorities with Next-Cart before launch to confirm which samples, service responsibilities, Add-ons, Custom Service items, Recent Data Migration steps, and Re-Migration decisions should be included in the final migration plan.

### FAQs <a href="#faqs" id="faqs"></a>

**Is matching Magento record counts enough to approve a migration?**

No. Record counts are only a starting point. Magento validation should also prove product-type behavior, attribute usability, store-scope accuracy, inventory availability, URL continuity, customer-group meaning, order readability, content rendering, and custom or extension-dependent outcomes.

**Which Magento products should be validated first after Demo Migration?**

Start with products that represent real catalog complexity: configurable products with child SKUs, bundle or grouped products, high-value simple products, products assigned to multiple categories or websites, products with custom attributes, products with important URLs, and products affected by inventory or extension logic.

**Why should Magento store-view validation be handled separately?**

Store views can carry language, URL, content, and scope-specific values. A product or page may look correct in the default view while another store view has missing text, incorrect metadata, wrong visibility, or an unintended URL path.

**How should Magento inventory be validated?**

Inventory should be validated by sellable behavior. Check quantities, stock status, sources, stocks, salable quantity, website assignment, and representative checkout behavior for simple products, configurable-product children, out-of-stock products, and products connected to warehouse or fulfillment workflows.

**What happens if Magento validation reveals custom or extension-owned data gaps?**

The finding should be classified before launch. Some gaps may require target configuration, Advanced Data Mapping, Advanced Data Configure, a Data Filter Add-on, Custom Service review, Re-Migration, or manual business acceptance depending on whether the issue involves standard entities, optional configuration, or custom migration logic adjustment.
