# X-Cart Pre-Migration Preparation Checklist

Preparing for an X-Cart migration means more than collecting product, customer, and order counts. X-Cart is a configurable e-commerce platform, so the quality of the migrated result depends on the target environment, product structure, theme and storefront setup, add-ons, custom modules, checkout configuration, SEO requirements, and connected systems.

A strong preparation process gives the Demo Migration useful evidence to test. It should identify what can be moved through standard structures, what needs filtering or mapping, what belongs to target setup, and what requires Custom Service because the migration depends on custom fields, custom modules, external identifiers, add-on-owned data, or custom migration logic adjustment.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Preparation should make the migration scope visible before the full dataset is moved. For X-Cart, that means confirming both the records to migrate and the target platform conditions that will interpret those records.

| Preparation goal                         | Why it matters in X-Cart                                                                                                                                          |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Confirm the target environment           | X-Cart behavior can depend on version, hosting, theme, add-ons, modules, and custom code.                                                                         |
| Select useful sample records             | Simple record samples can hide problems in options, variants, attributes, extra fields, categories, filters, orders, and SEO.                                     |
| Separate migrated data from target setup | Payment, shipping, tax, checkout, notifications, storefront presentation, and integrations need target configuration beyond data migration.                       |
| Identify add-on and module dependencies  | Add-ons and custom modules can own fields, rules, workflows, or display behavior that standard records do not fully explain.                                      |
| Define Custom Service signals early      | Custom fields, external identifiers, custom checkout logic, headless/API work, or unsupported module data should be reviewed before scope is treated as standard. |

### 1. Confirm the Target X-Cart Environment <a href="#id-1-confirm-the-target-x-cart-environment" id="id-1-confirm-the-target-x-cart-environment"></a>

The target X-Cart environment should be reviewed before Demo Migration. The same source data can behave differently depending on the target version, hosting, theme, add-ons, custom modules, and integration stack.

| Target detail             | What to prepare                                                                               | Why it matters                                                                                                         |
| ------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| X-Cart version or branch  | Intended target version, update status, and known legacy constraints                          | Version differences can affect modules, data structures, theme behavior, and compatibility.                            |
| Hosting environment       | Hosting type, PHP/database requirements, file access, storage, and performance expectations   | Large catalogs, images, imports, and admin operations can depend on the target environment.                            |
| Theme or storefront layer | Active theme, custom design requirements, responsive expectations, and template modifications | A successful data migration does not automatically reproduce the source storefront design.                             |
| Add-on and module stack   | Installed X-Cart add-ons, custom modules, and required business extensions                    | Add-on-owned behavior can affect products, prices, checkout, shipping, payments, promotions, search, and integrations. |
| Admin and user access     | Required administrative access, user roles, and permission expectations                       | User and role planning helps prevent access problems after migration.                                                  |
| Integration endpoints     | ERP, PIM, WMS, CRM, accounting, fulfillment, marketplace, or API connections                  | External systems may depend on identifiers, statuses, SKUs, or custom fields that must remain usable.                  |

### 2. Prepare Product and Catalog Samples <a href="#id-2-prepare-product-and-catalog-samples" id="id-2-prepare-product-and-catalog-samples"></a>

X-Cart product preparation should focus on records that reveal selling behavior. A sample made only of simple products is usually too weak for evaluating a real X-Cart migration.

Prepare examples that cover:

* simple products with standard prices, images, categories, inventory, and SEO values;
* products with multiple options, variants, or variations;
* products with attributes, extra fields, specifications, or custom fields;
* products with multiple images, downloadable files, or rich descriptions;
* products with inventory differences, low-stock behavior, backorder expectations, or SKU-level tracking;
* products with discounts, tax differences, shipping rules, or add-on-controlled pricing;
* products that rely on custom modules, product labels, badges, tabs, configurators, or non-standard fields;
* high-value products that must preserve URLs, metadata, and category placement.

The goal is not to prove that one simple product can appear in X-Cart. The goal is to prove that the target catalog can preserve the business meaning of products that customers actually buy and staff actually manage.

### 3. Prepare Category, Navigation, Search, and Filter Evidence <a href="#id-3-prepare-category-navigation-search-and-filter-evidence" id="id-3-prepare-category-navigation-search-and-filter-evidence"></a>

Product discovery is a separate preparation layer. Products can migrate correctly as records but still become hard to find if category placement, menus, filters, search fields, or SEO-sensitive paths are not planned.

| Discovery area             | Evidence to prepare                                                                                     |
| -------------------------- | ------------------------------------------------------------------------------------------------------- |
| Categories                 | Deep category branches, parent-child relationships, landing categories, and category descriptions.      |
| Navigation                 | Menus, storefront paths, important landing pages, and links from content to products or categories.     |
| Filters and faceted search | Attributes, extra fields, brands, price ranges, stock values, product types, or add-on-powered filters. |
| Search behavior            | Products that depend on SKU, title, keyword, brand, attribute, or custom-field search.                  |
| SEO-sensitive paths        | High-value product and category URLs, metadata, canonical expectations, and redirect priorities.        |

If the current store depends on advanced search, faceted navigation, or a search/filter add-on, include those cases in the Demo Migration review. Search and discovery should not be judged by product count alone.

### 4. Prepare Customer, User, Group, and Account Samples <a href="#id-4-prepare-customer-user-group-and-account-samples" id="id-4-prepare-customer-user-group-and-account-samples"></a>

X-Cart customer data can include more than names and email addresses. Account usefulness may depend on addresses, groups, memberships, roles, newsletter status, B2B behavior, order history, and custom customer fields.

Prepare customer and user samples that include:

* customers with multiple billing and shipping addresses;
* customers with order history;
* customers assigned to groups, memberships, price levels, or B2B segments where used;
* users with administrative or staff roles where user migration is in scope;
* customers with newsletter, marketing, or contact-preference context;
* customer records with custom fields, external IDs, tax IDs, company names, or account notes;
* guest orders that must remain readable without a full registered account relationship.

Custom account fields and business-specific customer logic should be reviewed before migration scope is finalized. If customer meaning depends on modules or external systems, that dependency should be documented for Add-on or Custom Service review.

### 5. Prepare Order and Transaction Samples <a href="#id-5-prepare-order-and-transaction-samples" id="id-5-prepare-order-and-transaction-samples"></a>

Order preparation should cover operational variety, not only completed orders. Historical order readability matters for customer service, accounting, fulfillment review, returns, and internal reporting.

Strong order samples include:

| Order type                                         | Why it should be included                                                               |
| -------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Paid and unpaid orders                             | Confirms payment-status readability.                                                    |
| Shipped, partially shipped, and unfulfilled orders | Confirms fulfillment and shipping context.                                              |
| Refunded, canceled, returned, or disputed orders   | Confirms exception history remains understandable.                                      |
| Discounted or coupon-based orders                  | Confirms promotion and discount values are readable.                                    |
| Taxed orders                                       | Confirms tax values, tax labels, and totals remain clear.                               |
| Multi-item and option-heavy orders                 | Confirms line-item detail, selected options, SKUs, and product relationships.           |
| Orders with custom fields or external references   | Confirms ERP, accounting, fulfillment, or marketplace references are not lost silently. |
| Guest orders                                       | Confirms order readability when no registered account exists.                           |

Do not use migrated order history as proof that live checkout is ready. Payment gateways, shipping methods, taxes, checkout rules, notifications, invoices, and fraud/security behavior need separate target setup and testing.

### 6. Separate Historical Data from Live Configuration <a href="#id-6-separate-historical-data-from-live-configuration" id="id-6-separate-historical-data-from-live-configuration"></a>

Many X-Cart migration problems happen when historical values are mistaken for active configuration. Migrated labels can describe old orders, but they do not automatically configure how the new store will process future orders.

| Area                       | Historical migration question                                            | Target setup question                                                              |
| -------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Payment                    | Are old payment labels, statuses, and transaction references readable?   | Are the intended payment gateways configured and tested for new checkout?          |
| Shipping                   | Are old shipping methods, costs, tracking values, and carriers readable? | Are live shipping rules, carriers, rates, zones, and tracking behavior configured? |
| Tax                        | Are historical tax labels and totals preserved clearly?                  | Are tax rules, tax services, zones, and exemptions configured for future orders?   |
| Checkout                   | Are old order details understandable?                                    | Does the target checkout flow support the expected buyer experience?               |
| Notifications and invoices | Are historical records readable?                                         | Are templates, order emails, invoices, and admin workflows configured?             |
| Security and fraud tools   | Are historical payment contexts preserved where available?               | Are active fraud, payment, and security modules configured and tested?             |

This separation should be agreed before Demo Migration review. Otherwise, the migration may be judged against target setup work that has not been completed yet.

### 7. Prepare Content, Media, SEO, and URL Evidence <a href="#id-7-prepare-content-media-seo-and-url-evidence" id="id-7-prepare-content-media-seo-and-url-evidence"></a>

X-Cart is an e-commerce platform, but content and SEO still affect launch quality. Products, categories, pages, images, metadata, redirects, and storefront links should be prepared as part of migration readiness.

Prepare the following:

* product and category URLs with high traffic or ranking value;
* product and category SEO titles, descriptions, keywords, and slug expectations;
* static pages, CMS Pages, landing pages, and policy pages;
* Blog Posts if the source store includes blog content and the migration path supports it;
* image libraries, downloadable files, alt text, and media relationships;
* redirects for retired, changed, or high-value URLs;
* internal links between content, categories, and products;
* pages or content blocks controlled by themes, add-ons, modules, or custom templates.

SEO preparation should prioritize business-critical URLs instead of trying to review every URL with equal weight. The Demo Migration should prove that representative high-value paths can be handled correctly.

### 8. Inventory Add-ons, Modules, Custom Code, and Integrations <a href="#id-8-inventory-add-ons-modules-custom-code-and-integrations" id="id-8-inventory-add-ons-modules-custom-code-and-integrations"></a>

Add-ons, modules, custom code, and integrations can carry important business meaning outside standard product, customer, order, and page records. X-Cart preparation should identify these dependencies before service scope is treated as straightforward.

| Dependency type                 | Examples to document                                                                                            | Why it matters                                                                |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| X-Cart add-ons                  | Search, filters, reviews, promotions, shipping, payments, marketing, B2B, subscriptions, marketplace, analytics | Add-ons can create fields, rules, display behavior, or workflow dependencies. |
| Custom modules                  | Bespoke product logic, checkout changes, customer rules, admin fields, reporting, external sync                 | Custom module data or behavior usually needs Custom Service review.           |
| Theme customization             | Custom templates, layout changes, banners, page sections, product tabs, custom category pages                   | Data migration does not automatically reproduce visual or template behavior.  |
| APIs and external systems       | ERP, PIM, WMS, CRM, accounting, fulfillment, email marketing, marketplace, analytics                            | External IDs and sync assumptions may need mapping or custom handling.        |
| Headless or Storefront API work | Custom frontend, external checkout, custom product pages, API-driven catalog display                            | Data must remain usable by the frontend or integration layer after migration. |

For each dependency, prepare the business purpose, affected data types, required fields, whether the behavior must continue after launch, and whether it can be reconfigured in X-Cart or needs Custom Service review.

### 9. Choose Demo Migration Samples Deliberately <a href="#id-9-choose-demo-migration-samples-deliberately" id="id-9-choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the hardest representative cases, not the easiest records. A useful X-Cart sample set should include records that expose catalog, order, account, storefront, SEO, and integration meaning.

| Sample type                | Include when possible                                                                                                                  |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Product sample             | Simple product, option-heavy product, variant/variation product, custom-field product, stock-sensitive product, SEO-sensitive product. |
| Category and filter sample | Deep category, filtered listing, high-value category page, search-dependent product group.                                             |
| Customer sample            | Registered customer, guest customer, customer group member, multiple-address account, custom-field account.                            |
| Order sample               | Paid, unpaid, shipped, refunded, discounted, taxed, option-heavy, guest, and externally referenced orders.                             |
| Content and SEO sample     | Static page, policy page, landing page, priority product URL, category URL, redirect case.                                             |
| Add-on or module sample    | Record affected by app, add-on, custom module, search/filter system, payment/shipping logic, or external integration.                  |
| Integration sample         | Record with ERP, PIM, WMS, CRM, accounting, fulfillment, marketplace, or analytics reference.                                          |

If the Demo Migration passes only on simple products and basic orders, it should not be treated as strong evidence for a complex X-Cart migration.

### 10. Identify Add-on and Custom Service Signals Early <a href="#id-10-identify-add-on-and-custom-service-signals-early" id="id-10-identify-add-on-and-custom-service-signals-early"></a>

Preparation should identify which requirements can stay within standard service capability, which may use Add-ons, and which move into Custom Service because customization is required.

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. For X-Cart, Add-on review is often relevant when the project needs selected record migration, supported field mapping, or supported data modification before migration.

Custom Service should be reviewed when the migration depends on:

* Custom Platform source handling;
* unsupported add-on or module data;
* custom product, customer, order, or content fields;
* custom checkout, pricing, payment, shipping, tax, or promotion behavior;
* custom module logic or source-code customization;
* external identifiers required by ERP, PIM, WMS, CRM, accounting, fulfillment, marketplace, or analytics systems;
* headless, Storefront API, or API-driven storefront behavior;
* Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

The purpose is not to make the project more complex than necessary. It is to prevent hidden requirements from being discovered only after Demo Migration or during launch preparation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

X-Cart preparation should make the target environment, data structure, add-on stack, storefront expectations, checkout boundaries, SEO priorities, and integration dependencies visible before migration execution. The stronger the preparation, the more meaningful the Demo Migration becomes.

Before starting Demo Migration, prepare representative records across products, options, variants, categories, filters, customers, orders, content, URLs, add-ons, modules, and integrations. If those records include the cases that matter most to the business, the migration result can be reviewed against real operating needs instead of surface-level record counts.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first for an X-Cart migration?**

Start with the target X-Cart environment: version, hosting, theme, add-ons, custom modules, and integration requirements. After that, prepare representative product, customer, order, content, SEO, and integration samples for Demo Migration.

**Which product samples are most useful for X-Cart preparation?**

Use products that reveal real catalog complexity: options, variants, variations, attributes, extra fields, images, stock behavior, custom fields, category placement, search/filter relevance, and SEO-sensitive URLs.

**Should payment, shipping, and tax setup be prepared before migration?**

Yes. Historical payment, shipping, and tax values may migrate as part of order history, but live payment gateways, shipping methods, tax rules, checkout behavior, invoices, and notifications require target setup and testing.

**Why should add-ons and custom modules be inventoried before Demo Migration?**

Add-ons and custom modules can control product fields, pricing, checkout behavior, search, shipping, payment, reporting, marketing, or integrations. If they are not identified early, the Demo Migration may miss data or behavior that is essential after launch.

**When should Custom Service be considered for X-Cart migration preparation?**

Custom Service should be considered when the migration depends on unsupported add-on or module data, custom fields, custom source-code logic, Custom Platform source handling, external identifiers, API-driven behavior, or custom migration logic adjustment.
