# CS-Cart Pre-Migration Preparation Checklist

CS-Cart preparation should begin with the business structure the Target Platform must support after migration. A simple single-seller store, a marketplace with vendors, a B2B-like buying model, and a customized commerce project can all require different evidence even when the migrated records look similar at first glance.

Preparation is not paperwork for its own sake. It is the control layer that keeps Products, Categories, Customers, Orders, CMS Pages, Blog Posts, vendor records, storefront content, and configuration-sensitive data from being moved without context. A CS-Cart migration becomes easier to review when the merchant can explain how products should be organized, who owns marketplace records, which add-ons affect business logic, which source behaviors should not be carried forward, and which examples must be tested through Demo Migration.

The strongest preparation package does not need to describe every old setting. It should identify the structures that define launch quality: catalog meaning, category placement, vendor responsibility, customer/account context, order history, route continuity, and the boundary between standard data, Add-ons, and Custom Service needs.

### What CS-Cart Preparation Should Prove <a href="#what-cs-cart-preparation-should-prove" id="what-cs-cart-preparation-should-prove"></a>

Pre-migration preparation should prove that the merchant understands the target operating model, not only the source database. CS-Cart can support conventional selling and Multi-Vendor marketplace operation, so the same source record may have different importance depending on the intended launch model.

For a straightforward store, preparation may focus on product completeness, category structure, customer accounts, order history, URLs, and storefront content. For a marketplace, the preparation scope must also identify vendors, vendor administrators, vendor-owned products, seller responsibility, product approval behavior, payout or accounting references, and order ownership. For a customized implementation, preparation must separate native platform data from add-on-owned records, custom source fields, external identifiers, theme behavior, and integration logic.

| Preparation proof            | Why it matters in CS-Cart                                                                                       | Evidence to prepare                                                                    |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Target operating model       | Defines whether records support a store, marketplace, B2B-like environment, or custom implementation.           | Short target-model statement, launch priorities, ownership map.                        |
| Catalog interpretation       | Products can carry options, features, categories, images, stock, files, and status meaning.                     | Product samples, category tree, feature/option examples, variation examples.           |
| Vendor ownership             | Multi-Vendor projects depend on seller responsibility, vendor administrators, and vendor-owned catalog context. | Vendor list, vendor-product samples, vendor admin examples, seller order samples.      |
| Account and customer context | Customer data may include buyer groups, account roles, addresses, and historical order relationships.           | Customer groups, buyer examples, address samples, account-role notes.                  |
| Custom and add-on boundaries | Add-ons, custom fields, and external systems may hold data that standard migration cannot interpret by default. | Add-on inventory, custom field list, integration map, external ID samples.             |
| Validation samples           | Demo Migration must include records that reveal the hardest translation issues.                                 | Representative sample set for Products, Customers, Orders, vendors, URLs, and content. |

Preparation should also identify what not to migrate. Old test products, abandoned categories, duplicate customer accounts, obsolete vendor profiles, unused add-on fields, and broken redirects can make the Target Platform harder to validate. Carrying everything forward may feel safer, but CS-Cart launch quality depends on useful structure, not maximum historical clutter.

### Define the Target Operating Model <a href="#define-the-target-operating-model" id="define-the-target-operating-model"></a>

Start by describing how the CS-Cart store should operate after launch. The answer should be specific enough to guide migration decisions. A merchant that wants a normal online store needs different preparation from a merchant that wants independent vendors to manage catalog entries, shipping methods, sales, orders, earnings, and payout balance.

For a single-seller store, preparation should clarify product ownership, category strategy, storefront navigation, customer account usage, order-history needs, and content migration expectations. For a marketplace, preparation should clarify whether vendors already exist in the Source Platform, whether sellers own products, whether vendor administrators exist, and whether historical orders must retain seller-level meaning. For a B2B-oriented store, preparation should clarify customer groups, company relationships, pricing expectations, access rules, and quote or approval assumptions.

A target operating model should answer these questions before migration execution:

* Will the Target Platform operate as a single-seller store, Multi-Vendor marketplace, B2B-like store, hybrid marketplace, or custom commerce environment?
* Which records require ownership meaning beyond simple record presence?
* Which target behaviors are native CS-Cart configuration, which depend on Add-ons, and which require Custom Service review?
* Which historical records must stay usable for customer support, accounting review, vendor accountability, or reporting?
* Which parts of the old platform should be cleaned, simplified, or intentionally excluded?

This step prevents later confusion. A product migrated without vendor ownership may look complete in a product list but still fail marketplace readiness. A customer migrated without group or account context may exist in the Target Platform but lose the commercial meaning required for B2B or segmented pricing. An order imported without vendor, payment, tax, or fulfillment context may be visible but weak for support.

### Prepare Product, Category, and Catalog Evidence <a href="#prepare-product-category-and-catalog-evidence" id="prepare-product-category-and-catalog-evidence"></a>

CS-Cart catalog preparation should begin with representative product evidence. Product data is not only names, descriptions, prices, and images. It may include SKU/code values, stock quantity, status, list price, categories, options, features, downloadable files, product variations, shipping characteristics, tax context, vendor assignment, and storefront visibility.

Prepare a sample set that includes ordinary products and difficult products. The sample should include high-value products, products with multiple options, products with features used for filtering, products with variation-like behavior, hidden or disabled products, downloadable products, vendor-owned products, out-of-stock products, and products assigned to multiple categories. These records reveal whether the source structure can translate into CS-Cart without losing meaning.

Categories require separate review because CS-Cart catalog structure depends on category assignment. Every product should have a category path that makes sense to customers and administrators. Category preparation should include root categories, child categories, hidden categories, high-traffic landing pages, category metadata, category images, manually curated navigation, and any categories that exist only for internal filing.

| Catalog area                   | Preparation task                                                                                  | Common issue to avoid                                                        |
| ------------------------------ | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Core product data              | Review SKU/code, names, descriptions, prices, stock, status, list price, and images.              | Treating visible product presence as proof of catalog readiness.             |
| Product features               | Identify technical specifications, searchable facts, filterable values, and marketing attributes. | Mixing features with free-form descriptions or inconsistent values.          |
| Product options and variations | Document size, color, model, bundle, add-on choice, or configuration behavior.                    | Assuming all source product-choice structures map cleanly without review.    |
| Category tree                  | Export or document parent-child categories and major landing pages.                               | Carrying obsolete, duplicate, or internal categories into launch navigation. |
| Vendor products                | Identify seller-owned catalog records and marketplace visibility rules.                           | Migrating products without seller responsibility.                            |
| Special products               | Review downloadable products, attached files, restricted products, or custom fulfillment items.   | Expecting platform behavior to transfer as ordinary data.                    |

Catalog cleanup decisions should be made before migration whenever possible. Duplicate SKUs, inconsistent option names, unused categories, conflicting feature values, and abandoned products can distort Demo Migration review. When cleanup cannot be completed first, mark those issues clearly so validation does not confuse source-data quality problems with migration errors.

### Document Vendor and Marketplace Ownership <a href="#document-vendor-and-marketplace-ownership" id="document-vendor-and-marketplace-ownership"></a>

Vendor preparation is central when CS-Cart is being used as a marketplace. Vendors are not just customer accounts with a label. They can represent independent companies, separate administration access, product ownership, shipping responsibility, sales visibility, order responsibility, earnings context, and payout balance. If the Source Platform contains marketplace data, the merchant should document how that data should become usable in CS-Cart.

Begin with the vendor list. Identify active vendors, inactive vendors, pending vendors, historical sellers, duplicate vendor records, merged vendor accounts, and vendors that should not appear after launch. Then connect vendors to products, orders, administrators, storefront pages, shipping methods, commissions, fees, payouts, and support context where relevant.

| Marketplace element         | Evidence to collect                                                            | Why it matters                                                                 |
| --------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Vendor accounts             | Active, inactive, pending, and historical seller examples.                     | Determines which marketplace participants should exist in the Target Platform. |
| Vendor administrators       | User accounts associated with each vendor.                                     | Needed when seller administration access matters after launch.                 |
| Vendor-owned products       | Product samples tied to sellers.                                               | Prevents catalog records from becoming admin-owned by default.                 |
| Vendor order context        | Orders with seller responsibility, fulfillment, payment, or dispute relevance. | Keeps order history useful for marketplace support and accountability.         |
| Vendor financial references | Commission, fee, payout, earning, balance, or accounting examples.             | Identifies data that may require Custom Service or external-system handling.   |
| Vendor approval behavior    | Seller approval, product approval, onboarding, and visibility requirements.    | Separates migrated records from target configuration and governance rules.     |

Not every marketplace requirement is a standard migration field. Some seller logic may belong to CS-Cart configuration, Add-ons, external systems, or Custom Service. Preparing vendor evidence early helps avoid a common mistake: moving product and order records first, then discovering that the marketplace operating model is incomplete.

### Clarify Customers, User Groups, and Account Meaning <a href="#clarify-customers-user-groups-and-account-meaning" id="clarify-customers-user-groups-and-account-meaning"></a>

Customer preparation should focus on how accounts will be used after migration. CS-Cart projects may include retail shoppers, business buyers, vendor administrators, customer groups, user groups, and other account relationships. Moving customer names and email addresses is not enough when account context affects pricing, access, ordering, support, or marketplace administration.

Prepare customer evidence in segments. Include ordinary retail customers, wholesale or B2B customers, customers with multiple addresses, customers with historical orders, customer group examples, vendor administrator accounts, inactive customers, and accounts that should be merged or excluded. If the Source Platform contains company accounts, approval status, credit terms, tax exemption, custom profile fields, or external customer IDs, those fields should be reviewed before the migration path is finalized.

Customer data should also be checked for quality issues. Duplicate emails, shared accounts, missing addresses, outdated customer groups, test customers, invalid phone numbers, and inconsistent names can make validation harder. Decide whether to clean those issues in the Source Platform, handle them through supported mapping/configuration, or document them as known source conditions.

| Account preparation area | What to review                                                                            | Migration planning value                                                      |
| ------------------------ | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Retail customers         | Names, emails, addresses, newsletter status, and order relationships.                     | Confirms basic customer continuity.                                           |
| Customer groups          | Wholesale, VIP, regional, tax, access, or price-related group examples.                   | Shows whether group meaning must be mapped or configured.                     |
| Vendor administrators    | Seller admin accounts and their vendor associations.                                      | Required when Multi-Vendor access matters after launch.                       |
| B2B-like accounts        | Company references, approval status, tax exemption, credit terms, or role behavior.       | May require mapping, Add-ons, target configuration, or Custom Service review. |
| Custom profile fields    | Internal IDs, membership flags, source-specific account metadata, or external references. | Helps separate standard customer migration from custom field handling.        |

The merchant should define which account relationships must be validated through Demo Migration. If customer groups, vendor administrator accounts, or B2B-like fields are important, include examples in the sample set. Otherwise the migration may appear successful while commercial account behavior remains unproven.

### Inventory Add-ons, Custom Fields, and Integrations <a href="#inventory-add-ons-custom-fields-and-integrations" id="inventory-add-ons-custom-fields-and-integrations"></a>

CS-Cart preparation should distinguish between data that belongs to core migration scope and behavior that depends on add-ons, custom fields, integrations, themes, or custom source development. This distinction matters because a migration can move supported records, but it does not automatically reproduce every source-side extension, storefront behavior, external sync, or custom database structure.

Create an inventory of source add-ons, target add-ons, modified templates, custom fields, external systems, API connections, ERP references, fulfillment integrations, marketplace modules, payment/shipping dependencies, reporting exports, SEO modules, and custom checkout logic. For each item, decide whether it stores data, changes display behavior, controls business rules, or simply improves administration.

| Dependency type          | Preparation question                                                              | Likely handling                                                                      |
| ------------------------ | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Add-on-owned fields      | Does the add-on store data that must be preserved?                                | Review as supported mapping, Add-on need, or Custom Service.                         |
| Custom product fields    | Are the fields commercial, operational, or internal only?                         | Map if supported, configure if bounded, or review as custom data.                    |
| External identifiers     | Do ERP, PIM, POS, shipping, or accounting systems require stable IDs?             | Preserve or transform through Custom Service when standard handling is insufficient. |
| Theme behavior           | Is the value content/data, or a visual/interface behavior?                        | Separate migration from design and frontend implementation.                          |
| Integration logic        | Does the source rely on external sync for stock, orders, vendors, or fulfillment? | Document ownership and reconnect outside ordinary data movement.                     |
| Custom checkout behavior | Does it affect pricing, payment, shipping, tax, or approval?                      | Review as target configuration, Add-on, or Custom Service need.                      |

This inventory prevents scope confusion. A field may be visible in the old storefront but not be part of ordinary product data. A marketplace commission rule may exist in an add-on or external system. A theme may display content that is stored somewhere else. A target-side add-on may need configuration after migration. Clear dependency notes make Demo Migration easier to interpret and make service-path decisions more accurate.

### Choose Representative Demo Migration Samples <a href="#choose-representative-demo-migration-samples" id="choose-representative-demo-migration-samples"></a>

Demo Migration should include records that expose the hardest CS-Cart questions, not only easy records that are likely to succeed. The sample set should prove whether the target structure can preserve catalog meaning, vendor responsibility, customer/account context, order readability, route continuity, and custom-field expectations.

A useful CS-Cart Demo Migration sample should include ordinary products, complex products, vendor-owned products, category-sensitive products, customers with groups or multiple addresses, vendor administrators, recent and historical orders, orders with vendor responsibility, CMS Pages, Blog Posts, URLs, and records tied to add-ons or external identifiers. The merchant should also include known problem records, because they reveal whether the migration plan can handle real source conditions.

| Sample type           | Include when                                                                     | What to check after Demo Migration                                                            |
| --------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Complex products      | Options, features, variations, files, images, or stock behavior affects selling. | Product usability, category placement, selectable choices, and storefront visibility.         |
| Vendor-owned records  | Marketplace operation matters.                                                   | Vendor assignment, seller context, product ownership, and order responsibility.               |
| Customer groups       | Pricing, access, tax, or buyer segmentation matters.                             | Group assignment, account context, addresses, and order links.                                |
| Historical orders     | Customer support or reporting depends on order history.                          | Order readability, customer link, product link, payment/shipping context, and vendor context. |
| Route-sensitive pages | SEO and launch continuity matter.                                                | Product/category URLs, CMS Pages, Blog Posts, redirects, and metadata.                        |
| Custom-field records  | External IDs, special account fields, or internal references matter.             | Whether custom data appears, maps, or requires Custom Service.                                |

Demo Migration should not be treated as a random preview. It is a controlled evidence test. If the sample set is too simple, the merchant may only learn that easy records can migrate. If the sample set includes marketplace and custom-sensitive records, the merchant can decide whether preparation is strong enough for Full Migration.

### Prepare for Full Migration and Follow-Up Changes <a href="#prepare-for-full-migration-and-follow-up-changes" id="prepare-for-full-migration-and-follow-up-changes"></a>

Full Migration preparation should include a launch timing plan and a follow-up data plan. CS-Cart projects often continue to receive new products, customers, orders, vendor changes, and content edits while migration planning is underway. The merchant should decide how those updates will be handled after the first migration result is reviewed.

Before Full Migration, confirm whether the Source Platform will be frozen, partially frozen, or still active. Identify who is allowed to add products, approve vendors, modify categories, process orders, change customer groups, update CMS Pages, or edit Blog Posts during the migration window. This reduces the risk of reviewing one dataset while the source store continues to change.

Additional Migration Options become relevant when the merchant needs to handle changed data after an earlier migration result. The merchant may continue with the last used configuration, continue with a new configuration, or perform a new migration when the source or target assumptions have changed enough to require a different path. For CS-Cart, the decision should be based on whether the same mapping remains valid for vendor ownership, categories, customer groups, route logic, and custom-field handling.

| Follow-up situation                                                         | Recommended interpretation                                                                               |
| --------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| New orders or customers appear after Full Migration preparation             | Continuing with the last used configuration may be enough if the structure is unchanged.                 |
| Product categories, customer groups, or vendor assignments were corrected   | A new configuration may be needed so the updated structure is handled properly.                          |
| Target setup, marketplace model, or custom-field plan changed significantly | A new migration may be safer than extending an outdated configuration.                                   |
| Demo Migration exposed missing marketplace or custom data                   | Review whether the issue needs Add-ons, Custom Service, or target-side implementation before continuing. |

Preparation should end with a clear readiness decision. If the merchant can explain the target model, provide representative samples, separate standard data from custom behavior, and assign validation owners, CS-Cart migration planning is ready to move forward. If those pieces are missing, the best next action is not to guess. It is to strengthen the evidence before execution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

CS-Cart pre-migration preparation should make the Target Platform reviewable. The merchant should define the target operating model, prepare product and catalog evidence, document vendor and marketplace ownership, clarify customer and account meaning, inventory add-ons and custom dependencies, and choose Demo Migration samples that represent real launch complexity.

The goal is not to make the source store perfect. The goal is to make the migration scope understandable enough that Demo Migration, Full Migration, Add-ons, Custom Service review, and any follow-up migration decision can be judged with confidence.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should I prepare first for a CS-Cart migration?**

Start with the target operating model. Decide whether CS-Cart will be used as a single-seller store, Multi-Vendor marketplace, B2B-like store, or custom commerce environment. That decision affects how Products, Customers, Orders, vendor records, content, and configuration-sensitive data should be prepared.

**Do I need to clean the source catalog before migrating to CS-Cart?**

Clean the source catalog when poor structure would make the Target Platform harder to validate. Duplicate SKUs, obsolete categories, inconsistent option names, and unclear product features should be corrected or documented before Demo Migration.

**What vendor information should be prepared for a marketplace migration?**

Prepare vendor accounts, vendor administrator examples, vendor-owned products, seller-related orders, approval expectations, and any commission, fee, payout, or accounting references that must remain meaningful after migration.

**Should add-ons and custom fields be reviewed before Demo Migration?**

Yes. Add-ons and custom fields may store business-critical data or control behavior that standard migration does not interpret by default. They should be separated into native data, supported mapping/configuration, target-side implementation, or Custom Service review.

**How should I choose Demo Migration samples for CS-Cart?**

Choose samples that represent real complexity: complex products, vendor-owned products, customer groups, vendor administrator accounts, historical orders, route-sensitive content, and records with custom fields or external identifiers.
