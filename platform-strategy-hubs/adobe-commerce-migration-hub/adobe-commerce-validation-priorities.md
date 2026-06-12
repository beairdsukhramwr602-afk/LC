# Adobe Commerce Validation Priorities

Adobe Commerce validation should prove more than record transfer. A migrated store can contain the expected products, customers, orders, categories, and CMS Pages while still failing the business model if company users cannot access the right catalog, prices are visible to the wrong accounts, scoped storefront content appears in the wrong store view, staged campaigns are misaligned, inventory availability is misleading, or high-value URLs no longer resolve correctly.

The most reliable validation approach is to test Adobe Commerce as an operating environment. The review should combine entity counts, representative record checks, buyer-role testing, storefront behavior, Admin configuration review, integration readiness, and launch-path confirmation. The goal is not only to confirm that data exists, but to confirm that migrated data behaves correctly under the target rules that Adobe Commerce will enforce after launch.

### Validate Company Accounts Before Treating Customer Data as Complete <a href="#validate-company-accounts-before-treating-customer-data-as-complete" id="validate-company-accounts-before-treating-customer-data-as-complete"></a>

For Adobe Commerce B2B stores, customer validation begins with company structure. A company account can represent the buying organization, while individual customer records may represent administrators, purchasing users, approvers, billing contacts, or employees with different permissions. If validation stops at customer names and emails, it can miss the relationships that determine whether B2B buyers can actually purchase.

The validation sample should include active companies, pending or inactive companies where relevant, company administrators, ordinary company users, users assigned to approval flows, and accounts tied to different customer groups or shared catalogs. Each sample should confirm that the company identity, legal address, administrator relationship, user access, and commercial settings are coherent in the target store.

| Validation area     | What to prove                                                                                                               | Failure signal                                                                                       |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Company identity    | The company account, legal details, status, and administrator are correct.                                                  | A buyer exists as an individual customer but is no longer connected to the business account.         |
| Company users       | Users can sign in under the intended company context and have the right role or permission level.                           | Users can view account areas they should not access, or cannot perform expected purchasing tasks.    |
| Company hierarchy   | Parent-child or multi-division structures are represented in the target plan.                                               | Related companies are flattened into unrelated accounts or assigned inconsistent settings.           |
| Commercial settings | Credit, quote permission, purchase order permission, payment methods, and shipping methods match the approved target model. | Buyers can use the wrong payment method, cannot submit expected quotes, or bypass intended controls. |

This review should be performed with real representative records, not only test accounts created after migration. The strongest evidence comes from logging in as the intended buyer profile and confirming that the storefront, account area, catalog access, checkout options, and order path reflect the target rules.

### Validate Shared Catalog Visibility and Price Access <a href="#validate-shared-catalog-visibility-and-price-access" id="validate-shared-catalog-visibility-and-price-access"></a>

Shared catalogs require storefront validation because the Admin record alone does not prove customer-facing behavior. A company may be assigned to the intended customer group or shared catalog, but the practical question is whether the right buyer sees the right products and prices after signing in.

Validation should compare at least three buyer contexts: a company assigned to a custom shared catalog, a company assigned to a different catalog or price structure, and a non-assigned or general customer context where applicable. The review should confirm product visibility, category navigation, search results, product-page pricing, cart pricing, and checkout behavior.

| Buyer context                | Required proof                                                                | Why it matters                                                                           |
| ---------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Assigned B2B company         | The buyer sees the intended catalog selection and company-specific prices.    | Confirms migrated customer relationships and shared catalog configuration work together. |
| Different B2B segment        | The buyer sees only the catalog and pricing intended for that segment.        | Detects price leakage, overexposure, and incorrect customer group assignment.            |
| General customer or guest    | Restricted products and B2B prices are hidden when they should not be public. | Protects negotiated pricing and private product availability.                            |
| Internal sales-assisted user | The account can support quote or order workflows expected by the sales team.  | Confirms the target store supports operational use, not only storefront browsing.        |

Shared catalog validation should include edge cases: products in multiple catalogs, products excluded from one catalog but included in another, custom prices, tiered pricing assumptions, discontinued items, and items with special visibility rules. A small sample of simple products is not enough for an Adobe Commerce B2B launch decision.

### Validate Product Structure and Catalog Meaning <a href="#validate-product-structure-and-catalog-meaning" id="validate-product-structure-and-catalog-meaning"></a>

Adobe Commerce product validation should prove that catalog relationships work as intended. A product can appear correct in a grid while failing on the storefront because variants, attributes, category assignments, bundle options, downloadable files, or visibility settings were not interpreted correctly.

Representative validation should include simple products, configurable products with associated simple SKUs, grouped or bundle products where relevant, virtual or downloadable products if used, and products that rely on important attributes or attribute sets. Each sample should be checked in the Admin, on the storefront, in category navigation, in search, and through the cart path.

| Product evidence              | What to confirm                                                                                               | Common failure pattern                                                                                |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Configurable product          | Parent product, child SKUs, option labels, prices, inventory behavior, and storefront selection are coherent. | The parent product displays but child SKUs, options, or availability are wrong.                       |
| Attribute set                 | Product families use the intended attribute set and required attributes are populated.                        | Products inherit incomplete or inappropriate attributes after migration.                              |
| Category assignment           | Products appear in the intended navigation context and merchandising structure.                               | Products exist in Admin but disappear from storefront categories or appear in the wrong catalog area. |
| Search and layered navigation | Searchable and filterable values support expected buyer discovery.                                            | Attributes transfer as text but do not support useful filtering or search behavior.                   |
| Complex product options       | Bundles, grouped products, downloads, or virtual products behave as expected.                                 | The product page loads, but buying logic, files, or grouped selections fail.                          |

Catalog validation should separate transferred values from target behavior. It is not enough for an attribute value to exist. The merchant should confirm whether the value is visible, searchable, filterable, comparable, used in promotions, or needed by an integration.

### Validate Website, Store, and Store-View Scope <a href="#validate-website-store-and-store-view-scope" id="validate-website-store-and-store-view-scope"></a>

Adobe Commerce scope validation is essential for multi-brand, multi-region, multilingual, or multi-currency stores. Scope affects how data, content, and configuration are interpreted in the target environment. A record can be correct globally while still wrong for a specific website, store, or store view.

The validation sample should include every active storefront scope that matters at launch. Merchants should check localized product names and descriptions, category names, CMS Pages, Blog Posts, URL keys, meta data, currency context, tax context, and storefront configuration where relevant.

| Scope level | Validation priority                                                                 | Practical proof                                                                                     |
| ----------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Website     | Confirm regional, brand, currency, customer, catalog, or business-model separation. | Buyers enter the intended website and see the right commercial context.                             |
| Store       | Confirm catalog structure and navigation expectations.                              | Category trees, menus, product assignments, and merchandising structure align with the target plan. |
| Store view  | Confirm localized display values and language-specific content.                     | Product copy, category labels, CMS Pages, URL keys, and SEO values match the intended locale.       |

Scope validation should include negative tests. A localized page should not appear under the wrong language context. A product assigned to one website should not become available in another website unless that is intentional. A B2B catalog intended for one customer segment should not become visible through a broader storefront context.

### Validate Inventory Availability and Fulfillment Assumptions <a href="#validate-inventory-availability-and-fulfillment-assumptions" id="validate-inventory-availability-and-fulfillment-assumptions"></a>

Inventory validation should prove that buyers see accurate availability and that internal teams can trust stock behavior after launch. Adobe Commerce inventory planning may involve sources, stocks, sales-channel assignments, salable quantity, and reservations. These concepts can affect storefront availability and order acceptance.

Validation should include products with simple stock behavior, products assigned to multiple sources if used, out-of-stock products, backorder-sensitive products, configurable products with child SKU availability differences, and items that are fulfilled from different warehouses or regions.

| Inventory check                 | What to verify                                                      | Why it matters                                                                  |
| ------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Source assignment               | Products are assigned to the intended fulfillment sources.          | Prevents orders from routing against the wrong operational inventory model.     |
| Stock and sales channel         | Stocks support the intended website or sales-channel availability.  | Prevents products from being unavailable on the wrong storefront.               |
| Salable quantity                | Storefront availability reflects the intended purchasable quantity. | Prevents overselling or false out-of-stock states.                              |
| Configurable child availability | Variant-level stock affects parent-product choices correctly.       | Prevents shoppers from selecting unavailable options or missing available ones. |

Inventory validation should be coordinated with fulfillment, warehouse, ERP, or order-management teams when external systems control stock after launch. If inventory values are only placeholders before integration cutover, the validation report should state that clearly instead of treating placeholder stock as final proof.

### Validate URL Rewrites, Redirects, and SEO-Sensitive Routes <a href="#validate-url-rewrites-redirects-and-seo-sensitive-routes" id="validate-url-rewrites-redirects-and-seo-sensitive-routes"></a>

Adobe Commerce URL validation should focus on route continuity, not only page existence. Products, categories, CMS Pages, and custom routes can depend on URL rewrites and redirects. A migrated store can have complete content but still lose traffic if important URLs fail, duplicate, redirect incorrectly, or point to the wrong target page.

The validation set should include high-traffic product URLs, category URLs, CMS Pages, campaign landing pages, localized URLs, and known legacy routes from the Source Platform. Merchants should test direct access, storefront navigation, canonical behavior where relevant, redirect behavior, and search-engine-sensitive metadata.

| URL group                   | Required validation                                              | Failure to watch for                                                              |
| --------------------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Product URLs                | Product pages resolve to the correct item and storefront scope.  | Product URL opens a duplicate page, wrong store view, or 404.                     |
| Category URLs               | Category routes preserve navigation value and assigned products. | Category exists but URL or product listing does not match the intended structure. |
| CMS Pages and landing pages | Important informational and campaign pages resolve correctly.    | Page content exists but high-value legacy URL is lost.                            |
| Redirects                   | Old URLs redirect to the correct new destination when required.  | Redirect chains, missing 301s, incorrect destinations, or language-scope errors.  |

URL validation should be performed before launch and repeated after final cutover if Recent Data Migration, Re-Migration, or last-minute catalog/content changes affect routes.

### Validate Content Staging and Campaign-Sensitive Records <a href="#validate-content-staging-and-campaign-sensitive-records" id="validate-content-staging-and-campaign-sensitive-records"></a>

For Adobe Commerce stores using Content Staging, validation must account for timing. Scheduled updates can affect products, categories, price rules, CMS Pages, and CMS blocks. A campaign-sensitive migration can look correct when reviewed at one moment but fail when a scheduled update becomes active.

Validation should identify which records are live, which are scheduled, which are part of upcoming campaigns, and which should not migrate as active content. Merchants should review scheduled product changes, category changes, promotional rules, CMS Pages, and CMS blocks with the marketing or merchandising owner who understands the campaign calendar.

| Staging area         | Validation question                                                  | Launch concern                                                                 |
| -------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Product updates      | Are scheduled product changes aligned with the migration timeline?   | A product may launch with outdated price, visibility, or copy.                 |
| Category updates     | Are navigation and campaign category changes scheduled correctly?    | Seasonal or campaign categories may appear too early, too late, or not at all. |
| Price rules          | Are promotion windows and eligibility rules correct?                 | Discounts may activate incorrectly or miss the intended launch period.         |
| CMS Pages and blocks | Are campaign pages and content blocks active in the intended window? | Landing pages or promotional content may be missing during launch.             |

If staging data is recreated manually or configured after migration, the validation record should distinguish between migrated data, target-side configuration, and post-migration merchandising setup.

### Validate Orders, Customer History, and Commercial Interpretation <a href="#validate-orders-customer-history-and-commercial-interpretation" id="validate-orders-customer-history-and-commercial-interpretation"></a>

Historical orders are often used as proof that migration succeeded, but Adobe Commerce validation should also check whether order history remains understandable for service, accounting, customer support, sales teams, and B2B account managers. The target store may not reproduce every source workflow exactly, especially where source logic came from extensions, ERP systems, custom checkout rules, or unsupported platform behavior.

Order validation should include completed orders, canceled orders, refunded orders, orders with discounts, orders with tax, orders with shipping rules, B2B orders, quote-originated orders where relevant, purchase-order-related orders where relevant, and orders tied to company accounts. The goal is to confirm that the historical record is coherent and usable, not to force old orders to behave like new Adobe Commerce orders.

For B2B stores, order history should be reviewed under the company context. The merchant should confirm whether the right users can access the right historical orders, whether order details remain understandable, and whether internal teams can trace customer, company, product, price, tax, and fulfillment context.

### Validate Add-ons, Custom Service Scope, and External Dependencies <a href="#validate-add-ons-custom-service-scope-and-external-dependencies" id="validate-add-ons-custom-service-scope-and-external-dependencies"></a>

Validation should not assume that every source behavior belongs to standard migration coverage. Adobe Commerce projects often include extension-owned data, custom attributes, external identifiers, B2B logic, ERP references, PIM relationships, contract pricing, tax rules, warehouse identifiers, loyalty data, marketplace data, or other operational dependencies. These should be reviewed against the agreed service scope.

Add-ons may be used for filtering, mapping, or data configuration where the required adjustment fits the service scope. Custom Service should be considered when the migration depends on unsupported source behavior, custom logic, Custom Platform handling, extension-owned structures, outside-system identifiers, or bespoke target-side interpretation. Validation should confirm whether these items were included, excluded, recreated manually, or intentionally deferred.

A clear validation record should identify each exception and its status:

| Exception type                       | Validation decision                                                     | Required documentation                                            |
| ------------------------------------ | ----------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Included in standard migration scope | Confirm the record moved and behaves as expected.                       | Sample IDs, before/after screenshots, and owner approval.         |
| Covered by Add-ons                   | Confirm the filtered, mapped, or configured result matches the request. | Add-on scope, tested examples, and acceptance criteria.           |
| Requires Custom Service              | Confirm bespoke handling was scoped and reviewed.                       | Custom requirement summary, target behavior, and approval status. |
| Out of scope or deferred             | Confirm the merchant understands the limitation.                        | Exclusion note, workaround, owner acceptance, and launch impact.  |

### Build a Validation Evidence Set Before Launch <a href="#build-a-validation-evidence-set-before-launch" id="build-a-validation-evidence-set-before-launch"></a>

A launch decision should be based on evidence, not impressions. For Adobe Commerce, the evidence set should include representative examples from each major operating area: B2C customers if applicable, company accounts, company users, shared catalogs, product families, complex products, localized storefronts, inventory-sensitive items, URLs, CMS Pages, promotions, orders, and integration-dependent records.

A practical validation set should include:

* source and target record IDs for every sample;
* screenshots or exports showing before-and-after values;
* storefront tests from the buyer perspective;
* Admin checks from the operations perspective;
* owner signoff for catalog, B2B, marketing, SEO, operations, and finance areas where relevant;
* a list of exceptions, deferred items, and accepted limitations;
* confirmation of whether Recent Data Migration or Re-Migration is needed before launch.

When the source store continues receiving orders or customer updates during validation, the team should decide whether Recent Data Migration is needed to bring newly created records into the target store. If the target store needs to be reset or the migration repeated after configuration changes, Re-Migration should be planned deliberately rather than treated as an informal cleanup step.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce validation should prove that the target store can operate under the intended business model. For simple stores, that may mean confirming catalog, customer, order, page, and URL completeness. For enterprise or B2B stores, the standard is higher: company users, shared catalog access, pricing visibility, staged campaigns, scoped storefront behavior, inventory availability, order history, integrations, and exceptions must all be tested against the target operating plan.

A strong Adobe Commerce validation process uses representative records, buyer-role testing, Admin review, storefront checks, and documented evidence before launch. When validation exposes unsupported logic, missing relationships, or configuration-dependent behavior, those findings should be resolved through the correct service path before Full Migration is treated as launch-ready.

Need help validating an Adobe Commerce migration? Review your company accounts, shared catalogs, product structures, storefront scope, URLs, inventory assumptions, and exception list with Next-Cart before launch so the final migration can be judged by operational readiness, not only transferred record counts.

### FAQs <a href="#faqs" id="faqs"></a>

**Is record count matching enough to validate an Adobe Commerce migration?**

No. Record counts are useful, but Adobe Commerce validation also needs behavior checks. Company access, shared catalog visibility, storefront scope, product relationships, inventory availability, URL continuity, staged content, and order history should be reviewed with representative records.

**What should be validated first for a B2B Adobe Commerce store?**

Start with company accounts, company administrators, company users, shared catalog assignment, pricing visibility, quote or purchase-order permissions where used, and buyer login behavior. These areas determine whether business buyers can actually use the target store after migration.

**How should shared catalog validation be handled?**

Test at least one company assigned to each important shared catalog or pricing model. Confirm that each buyer sees the intended products, prices, search results, category navigation, and checkout options, and also confirm that restricted products or prices are not visible to the wrong audience.

**Why is scope validation important in Adobe Commerce?**

Adobe Commerce uses websites, stores, and store views. Content, configuration, product values, URLs, language values, and storefront behavior may depend on scope. Multi-brand, multi-region, multilingual, or multi-currency stores should validate each relevant scope before launch.

**When should Recent Data Migration or Re-Migration be considered during validation?**

Recent Data Migration should be considered when the Source Platform continues receiving new orders, customers, or other records after the main transfer. Re-Migration should be considered when the target store needs to be reset or the migration repeated after configuration or scope changes.
