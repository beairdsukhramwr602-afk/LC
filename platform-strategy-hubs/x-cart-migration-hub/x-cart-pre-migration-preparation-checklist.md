# X-Cart Pre-Migration Preparation Checklist

Preparing for an X-Cart migration means preparing the data and the destination conditions that will interpret that data. X-Cart can hold ordinary commerce records, but the quality of the result depends on how products, product variations, classes and attributes, categories, images, inventory, users, memberships, orders, add-ons, checkout settings, shipping, tax, and SEO signals are represented before the migration begins.

Good preparation gives Demo Migration a realistic sample to test. Weak preparation usually creates a misleading result: product counts may look correct, while customer permissions, product choices, membership pricing, images, category relationships, or add-on-dependent data still need review. The strongest preparation work identifies what belongs to the migration scope, what belongs to target-side configuration, and what requires a service-path decision before Full Migration.

### Define the X-Cart Target Environment Before Reviewing Data <a href="#define-the-x-cart-target-environment-before-reviewing-data" id="define-the-x-cart-target-environment-before-reviewing-data"></a>

The target environment should be clear before source records are evaluated. A store moving into X-Cart needs more than a blank destination. It needs a known target version, administrative access, basic store settings, catalog assumptions, enabled add-ons, theme direction, checkout expectations, tax and shipping configuration, and any required localization or currency settings.

This preparation step prevents a common mistake: treating X-Cart as a simple import destination while the project actually depends on configured behavior. Product data can be migrated, but the way that data appears and functions depends on the target environment. Attributes, product variations, categories, images, memberships, checkout behavior, and add-on-supported features all need a prepared destination context.

| Target preparation area              | What to confirm before migration                                                                             | Why it matters in X-Cart                                                                                                |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Store version and environment        | Target X-Cart version, hosting, admin access, backup plan, and technical access.                             | Version and environment assumptions affect import/export review, add-on compatibility, and later troubleshooting.       |
| Catalog configuration                | Product structure, category hierarchy, attribute/class expectations, inventory handling, and image handling. | Migrated records need a destination structure that can preserve their commercial meaning.                               |
| User and customer setup              | Customer accounts, user roles, memberships, profile fields, and address expectations.                        | X-Cart customer data may involve more than basic name and email records.                                                |
| Add-on stack                         | Installed add-ons, required add-ons, abandoned add-ons, and source add-on dependencies.                      | Add-on-created behavior may need configuration, Custom Service, or post-migration implementation.                       |
| Checkout, payment, shipping, and tax | Target-side methods, tax rules, shipping rules, and checkout behavior.                                       | Historical orders can migrate as records, but live checkout behavior must be configured and tested on the target store. |
| SEO and storefront structure         | URL priorities, redirects, metadata, category landing pages, and content pages.                              | Search continuity depends on knowing which pages and URLs must be preserved, redirected, or rebuilt.                    |

The target environment does not need to be fully designed before Demo Migration, but it should be stable enough for the sample result to mean something. If the target catalog, membership structure, add-ons, or SEO plan changes after sampling, the migration result may need revalidation.

### Collect Source Data Evidence, Not Only Record Counts <a href="#collect-source-data-evidence-not-only-record-counts" id="collect-source-data-evidence-not-only-record-counts"></a>

Record counts are useful for estimating scope, but they are not enough for X-Cart preparation. A source store with 10,000 products may be simple if most products are ordinary records. A smaller store may be more complex if its products rely on variants, configurable options, membership-specific pricing, wholesale rules, custom fields, external identifiers, or add-on-managed behavior.

Preparation should collect evidence that shows how the source store actually works. That evidence should include exports, screenshots, sample records, admin configuration notes, URL examples, customer group examples, order examples, add-on lists, and known customizations. The goal is to identify the data that must remain usable inside X-Cart, not merely to count how many records exist.

| Source evidence                                   | Preparation question                                                                                               | Decision signal                                                                                |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Product export and representative product samples | Do products use variants, options, classes, attributes, inventory rules, images, or add-on fields?                 | Determines whether the catalog fits standard mapping or needs deeper review.                   |
| Category and navigation examples                  | Are categories simple groupings, storefront navigation tools, SEO landing pages, or access-control structures?     | Helps separate migrated category records from target-side menu and storefront configuration.   |
| Customer and user records                         | Are there ordinary customers only, or are there roles, memberships, profile fields, addresses, vendors, or admins? | Indicates whether customer records need profile, membership, or permission review.             |
| Order samples                                     | Do orders include statuses, payment labels, shipping context, tax lines, coupons, returns, or custom notes?        | Helps prove whether migrated order history remains readable and useful.                        |
| Add-on and customization inventory                | Which source functions are native, add-on-supported, custom-coded, or externally connected?                        | Determines whether Add-ons, Custom Service, target setup, or later implementation is required. |
| SEO and content evidence                          | Which URLs, metadata, content pages, and high-value product/category pages matter most?                            | Defines redirect priorities and post-migration storefront review.                              |

The preparation file set should be practical. It does not need to document every record manually. It should identify the record types and edge cases that will determine whether the migration result is commercially usable.

### Prepare Product Variations, Attributes, and Catalog Samples <a href="#prepare-product-variations-attributes-and-catalog-samples" id="prepare-product-variations-attributes-and-catalog-samples"></a>

Product preparation is the center of many X-Cart migrations. Official X-Cart materials distinguish catalog management areas such as products, product variations, product variants, categories, classes and attributes, product images, stock, bulk editing, and related catalog add-ons. That means a product is not just a row of title, SKU, description, and price. It may include multiple layers of customer choice, descriptive attributes, inventory behavior, images, category membership, and add-on-supported rules.

Preparation should identify the product structures that deserve Demo Migration sampling. A strong sample includes common products, best-selling products, complex products, products with images, products with variation logic, products with detailed attributes, products in multiple categories, and products affected by add-ons or external systems.

| Catalog area                   | What to prepare                                                                                                                | What the sample should prove                                                       |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Simple products                | Ordinary SKU, title, description, price, stock, images, and categories.                                                        | Basic product records migrate cleanly and display correctly.                       |
| Product variations or variants | Parent/child relationships, option-like choices, SKU differences, price differences, stock differences, and image differences. | Customer-facing buying choices remain understandable and operational.              |
| Classes and attributes         | Attribute groups, descriptive values, filterable/comparison data, and product-specific attributes.                             | Descriptive catalog data remains usable rather than becoming disconnected text.    |
| Images and media               | Main image, gallery images, image naming, missing images, and externally hosted image references.                              | Product pages are visually complete and do not rely on broken source links.        |
| Inventory and pricing          | Stock values, wholesale pricing, membership pricing, price modifiers, discounts, and special cases.                            | Commercial conditions that affect purchasing are identified before Full Migration. |
| Add-on-influenced products     | Product builders, fitment data, subscriptions, bundles, custom options, or other add-on-created fields.                        | Unsupported or custom behavior is escalated before it becomes a launch issue.      |

A useful product sample should contain the difficult products, not only the cleanest products. If the sample avoids complex variations, membership pricing, special attributes, or add-on fields, the Demo Migration may pass too easily and hide the real migration risk.

### Prepare Categories, Content, and SEO Signals Together <a href="#prepare-categories-content-and-seo-signals-together" id="prepare-categories-content-and-seo-signals-together"></a>

Categories in an X-Cart migration should be reviewed as both data records and storefront discovery structures. Categories may affect product browsing, URL planning, metadata, navigation, and landing-page value. If categories are migrated without considering how the target storefront will use them, the data may be present but not useful.

SEO preparation should focus on continuity rather than cosmetic metadata transfer. Product URLs, category URLs, important content pages, page titles, descriptions, slugs, redirects, and high-traffic pages should be identified before migration. The preparation should also mark which URLs must be preserved exactly, which can redirect, and which should be rebuilt because the target store uses a different structure.

A practical SEO preparation sheet should include:

* highest-value product URLs;
* highest-value category URLs;
* important content pages and landing pages;
* metadata fields that must be reviewed after migration;
* known redirects already used on the source store;
* URLs generated by custom modules or add-ons;
* pages with backlinks, traffic, paid campaigns, or search ranking value;
* product and category samples that must be checked after Demo Migration.

SEO preparation should not be postponed until after Full Migration. Redirect planning and URL review become harder when the source structure has already been replaced, especially for older stores, stores with custom URL rules, or stores where categories and products have changed over time.

### Prepare Customers, Users, Memberships, and Orders <a href="#prepare-customers-users-memberships-and-orders" id="prepare-customers-users-memberships-and-orders"></a>

X-Cart preparation should separate ordinary customer data from user-management behavior. Official X-Cart materials include account types, roles, memberships, customer profile fields, address books, and membership-specific commercial behavior. That makes customer preparation more important than a simple contact export.

Customer preparation should identify whether the source store contains ordinary retail customers only or whether it includes customer groups, memberships, wholesale buyers, admin users, vendor-like roles, custom profile fields, special pricing, access rules, or custom account operating rules. Some information may migrate as customer data. Some may need mapping. Some may need target-side configuration or Custom Service review.

| User/order area        | Preparation evidence                                                                                  | Migration planning implication                                                                 |
| ---------------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Customer profiles      | Names, emails, addresses, phone numbers, profile fields, account status, and opt-in data.             | Confirms which customer fields are supported and which fields need mapping or review.          |
| Memberships and groups | Membership levels, pricing rules, restricted access, discounts, tax/payment limits, and coupon logic. | Distinguishes migrated customer identity from target-side commercial behavior.                 |
| User roles             | Admins, vendors, staff roles, permission-like structures, and custom roles.                           | May require target-side setup or Custom Service if permissions are not standard customer data. |
| Orders                 | Statuses, payment labels, shipping methods, tax lines, coupons, order notes, returns, and refunds.    | Preserves order history as readable business evidence, not as live checkout configuration.     |
| External identifiers   | ERP IDs, accounting IDs, marketplace IDs, fulfillment IDs, and CRM references.                        | May require mapping or Custom Service if they must remain connected after migration.           |

Order preparation should also define how much historical order data is necessary. Some merchants need complete history for service, reporting, accounting, warranty, or customer support. Others need recent orders and customer purchase context. The decision affects scope, validation effort, Entity Points planning where eligible records are migrated for the first time, and post-migration review.

### Inventory Add-ons, Customizations, and External Systems <a href="#inventory-add-ons-customizations-and-external-systems" id="inventory-add-ons-customizations-and-external-systems"></a>

Add-ons and customizations create some of the most important preparation signals for X-Cart. A source store may appear ordinary until the migration review reveals that key behavior lives in an add-on, custom module, custom database field, external integration, or source-code modification.

The add-on inventory should not be a casual list of installed extensions. It should classify each dependency by business role. A payment add-on, a shipping add-on, a product configurator, a loyalty add-on, an SEO add-on, and a marketplace integration create very different migration questions.

| Dependency type                                    | Preparation action                                                                | Likely handling path                                                                            |
| -------------------------------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Add-on stores display-only data                    | Identify whether the data must migrate or can be recreated on the target store.   | May require target setup rather than migration scope.                                           |
| Add-on creates product/customer/order fields       | Export sample records and identify where the fields appear in business processes. | May require mapping, Add-ons, or Custom Service depending on support.                           |
| Add-on controls pricing, access, or checkout logic | Document rules, examples, and affected customer/product/order records.            | Usually needs target-side configuration and possibly Custom Service review.                     |
| External system stores identifiers                 | Collect ID fields, source tables, exports, and integration documentation.         | May require mapping or Custom Service if identifiers must remain attached.                      |
| Custom code changes source behavior                | Identify modified files, custom tables, custom fields, and custom calculations.   | Strong Custom Service signal; standard migration should not assume automatic behavior transfer. |

Preparation should also separate migrated data from recreated behavior. For example, a historical order record can preserve the shipping method name, but live shipping rate calculation depends on the target shipping setup. A customer can be migrated with profile details, but a membership-specific discount may need target configuration. A product can be migrated with attributes, but a custom product builder may need implementation beyond data migration.

### Prepare the Demo Migration Sample Deliberately <a href="#prepare-the-demo-migration-sample-deliberately" id="prepare-the-demo-migration-sample-deliberately"></a>

Demo Migration should be designed as a diagnostic sample. It should not be limited to clean products and ordinary customers. The sample should include records that reveal whether the migration approach is strong enough for the real store.

A strong X-Cart Demo Migration sample should include:

* one simple product with ordinary fields;
* one product with variations or legacy variant-like behavior;
* one product with meaningful classes and attributes;
* one product with multiple images and category relationships;
* one product affected by wholesale pricing, membership pricing, or a special rule where relevant;
* one customer with ordinary data and addresses;
* one customer connected to a membership, group, or custom profile field;
* several orders with different statuses, payment labels, shipping labels, tax context, coupons, and notes;
* one SEO-sensitive product URL and one SEO-sensitive category URL;
* at least one record influenced by an add-on, custom field, or external identifier if the source store depends on that behavior.

| Demo sample category | Why it belongs in the sample                                             | What should be checked afterward                                                           |
| -------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| Complex product      | Reveals variation, attribute, image, and inventory handling.             | Customer choices, SKU logic, stock, images, and product-page clarity.                      |
| Membership customer  | Reveals whether customer identity and commercial segmentation are clear. | Profile fields, addresses, membership labels, and target-side pricing/access expectations. |
| Representative order | Reveals whether historical order data remains readable.                  | Statuses, line items, taxes, shipping labels, payment labels, coupons, and notes.          |
| SEO-sensitive URL    | Reveals redirect and metadata planning needs.                            | Slug, metadata, page relationship, redirect requirement, and post-migration priority.      |
| Add-on/custom record | Reveals whether standard migration is enough.                            | Whether the data appears, is missing, or requires Custom Service or target setup.          |

Demo Migration should produce a decision, not just a preview. If the sample exposes missing custom fields, broken variation logic, incomplete images, unclear membership behavior, or order-history confusion, the project should pause for scope clarification before Full Migration.

### Prepare Service-Scope Questions Before Choosing the Migration Path <a href="#prepare-service-scope-questions-before-choosing-the-migration-path" id="prepare-service-scope-questions-before-choosing-the-migration-path"></a>

Preparation should lead to a clear service-scope conversation. Standard Service, Managed Service, Add-ons, and Custom Service solve different problems. The preparation evidence should identify which path is appropriate instead of forcing the decision from record counts alone.

Standard Service may fit when the source data is supported and the target X-Cart structure is ready. Managed Service may be safer when the migration remains within standard capability but the merchant wants more structured execution. Add-ons may help with filtering, mapping, or data configuration within supported behavior. Custom Service should be reviewed when requirements depend on custom fields, unsupported add-on data, source-code changes, bespoke transformations, external identifiers, or custom migration logic adjustment.

| Preparation finding                                                             | What it usually means                                         | Service-scope response                                            |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------- |
| Ordinary products, categories, customers, and orders                            | Core records fit a supported migration path.                  | Standard Service may be enough if validation confirms the result. |
| Large catalog with complex sample review needs                                  | Migration may be standard but operationally demanding.        | Managed Service may help with execution and coordination.         |
| Need to migrate only selected data or align supported fields                    | Scope or mapping control is needed inside supported behavior. | Relevant Add-ons may be reviewed.                                 |
| Add-on data or custom fields control business behavior                          | Standard records alone will not preserve the store meaning.   | Custom Service review is needed.                                  |
| Data will change after Demo Migration or configuration will shift before launch | Follow-up handling and revalidation must be planned.          | Additional Migration Options may be relevant.                     |

This scope review should also include Entity Points planning where eligible Products, Customers, Orders, or Blog Posts are migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because later migration activity occurs on the same migration path, but new eligible records can matter when planning follow-up activity.

### Conclusion <a href="#conclusion" id="conclusion"></a>

X-Cart migration preparation should make the target environment, source data, catalog structure, customer logic, order history, add-ons, integrations, SEO priorities, and service-scope questions visible before Full Migration. The goal is not to over-document the store. The goal is to collect enough evidence to test the records and behaviors that matter most.

A prepared X-Cart project has a useful target environment, representative product and customer samples, documented add-on and customization dependencies, clear SEO priorities, and a Demo Migration sample that can expose real issues. When those inputs are ready, service-path decisions become more accurate and validation becomes more reliable.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for an X-Cart migration?**

Start with the target environment, source export access, representative product samples, customer and order samples, add-on inventory, and SEO-priority URLs. These items reveal whether the migration is a clean supported transfer or whether mapping, Add-ons, Managed Service, or Custom Service should be reviewed.

**Why are product variations and attributes important before migration?**

They determine whether products remain understandable and purchasable after migration. Product titles and SKUs may transfer correctly while buying choices, inventory differences, images, or descriptive attributes still need review.

**Should add-ons be documented before Demo Migration?**

Yes. Add-ons may create fields, rules, pricing behavior, customer logic, storefront content, or external-system relationships that are not ordinary product, customer, or order data. Documenting them early helps identify whether the requirement belongs to standard migration, target setup, Add-ons, or Custom Service.

**How much order history should be prepared for migration?**

The answer depends on business need. Customer support, accounting, warranty, reporting, and repeat-purchase context may require deeper history. A smaller scope can work when older order data is no longer operationally useful, but the decision should be made before Full Migration.

**When should Additional Migration Options be planned for X-Cart?**

Plan them when data is likely to change after Demo Migration, when target configuration may change before launch, or when the store needs follow-up migration activity after the first Full Migration. They should be paired with revalidation because later activity can affect products, customers, orders, URLs, and configured behavior.
