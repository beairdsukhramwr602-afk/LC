# CS-Cart Pre-Migration Preparation Checklist

CS-Cart preparation should begin with a simple question: what business structure should the Target Platform support after migration? For a basic online store, preparation may focus on products, categories, customers, orders, URLs, and storefront content. For a marketplace, B2B/B2C selling model, mobile marketplace, headless implementation, or customized e-commerce project, preparation must also clarify vendor ownership, storefront behavior, account roles, add-ons, themes, hosting responsibilities, and integration boundaries.

A CS-Cart migration is easier to plan when the source data already explains how the business works. If products belong to vendors, categories support marketplace navigation, customer accounts carry role or buyer context, orders involve seller responsibilities, or integrations control inventory and fulfillment, those relationships should be documented before migration begins. Otherwise, the migration process may move records without preserving the operating logic that made the source store usable.

Preparation is not about documenting every historical detail. It is about identifying the structures that must remain meaningful after the migration path is executed and choosing representative examples that can reveal whether CS-Cart is receiving the right data in the right context.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation helps the merchant make the CS-Cart migration reviewable. The goal is to give the migration process enough context so Demo Migration, Full Migration, Recent Data Migration, and later validation can be interpreted correctly.

For CS-Cart, preparation should answer five practical questions:

| Preparation question                                        | Why it matters for CS-Cart migration                                                                                                                                 |
| ----------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What type of target business is being built?                | A single-vendor online store, multi-vendor marketplace, B2B marketplace, mobile marketplace, or headless implementation creates different data interpretation needs. |
| Which records carry ownership or role meaning?              | Products, categories, customers, vendors, orders, payouts, approvals, and storefront content may need more than ordinary record transfer.                            |
| Which source behaviors are native, add-on-owned, or custom? | CS-Cart projects often depend on add-ons, themes, custom development, hosting choices, and integrations that should be separated before execution.                   |
| Which data must be cleaned before migration?                | Duplicated SKUs, unclear vendor assignments, obsolete categories, inconsistent customer roles, and historical workarounds can become harder to fix after migration.  |
| Which examples should be tested through Demo Migration?     | Representative samples make it easier to detect whether the Target Platform is preserving marketplace, catalog, customer, order, and storefront meaning.             |

Good preparation reduces rework. It also helps the merchant decide whether the migration can stay within standard service capability, whether Managed Service is safer, or whether Custom Service is required because the source structure or expected target result needs customization, modification, or custom migration logic adjustment.

### Numbered Preparation Priorities <a href="#numbered-preparation-priorities" id="numbered-preparation-priorities"></a>

#### 1. Define the CS-Cart target operating model <a href="#id-1-define-the-cs-cart-target-operating-model" id="id-1-define-the-cs-cart-target-operating-model"></a>

Start by deciding what CS-Cart is expected to become after migration. A merchant moving into CS-Cart may want a conventional online store, a multi-vendor marketplace, a B2B marketplace, a mobile marketplace, a headless storefront, or a custom e-commerce project. These models can share core data types, but they do not use them in the same way.

For example, product records in a single-vendor store mainly need catalog, price, inventory, media, and category meaning. In a marketplace context, those same products may also need vendor ownership, seller workflow, commission context, approval behavior, and order responsibility. In a B2B marketplace, customer accounts may need buyer-company, role, price, approval, or access meaning that ordinary customer data does not explain.

Before migration begins, document the intended target model in plain language:

* whether the Target Platform is a store, marketplace, B2B marketplace, mobile marketplace, headless site, or custom implementation
* whether vendors or sellers will own products, fulfill orders, or manage parts of the catalog
* whether customers are ordinary shoppers, business buyers, company users, sellers, administrators, or mixed-role accounts
* whether multiple storefronts, languages, currencies, regions, or channels must be considered
* whether hosting, deployment, maintenance, and development responsibilities are already decided

This step prevents the migration from being judged only by record counts. In CS-Cart, the same migrated product, customer, or order may be correct in one operating model and incomplete in another.

#### 2. Prepare product and catalog evidence <a href="#id-2-prepare-product-and-catalog-evidence" id="id-2-prepare-product-and-catalog-evidence"></a>

Products should be reviewed before migration because CS-Cart catalog quality depends on more than item presence. A product may need options, variations, attributes, files, images, downloadable content, shipping characteristics, vendor ownership, category placement, and storefront visibility.

Prepare product evidence that shows the real range of the catalog:

| Product area                   | What to prepare                                                                                                           | Why it matters                                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Core products                  | SKUs, names, descriptions, prices, images, inventory, status, and tax/shipping context                                    | Proves that ordinary product records can be interpreted correctly in CS-Cart.                                               |
| Product options and variations | Size, color, model, bundle, configuration, or selection behavior                                                          | Helps identify whether source product choices translate cleanly or require mapping or configuration review.                 |
| Product attributes             | Technical specifications, searchable fields, compatibility notes, dimensions, material, brand, or internal classification | Determines whether product information should become sellable structure, filterable data, content, or custom-field context. |
| Vendor-owned products          | Seller assignment, approval status, fulfillment responsibility, product ownership, and marketplace visibility             | Required when CS-Cart is being used as a marketplace or seller-managed catalog.                                             |
| Digital or special products    | Downloadable files, service products, subscriptions, licenses, restricted products, or nonstandard fulfillment            | Helps identify whether product behavior requires standard configuration, Add-on review, or Custom Service review.           |

The merchant should also decide which source catalog problems should not be carried forward. Duplicate SKUs, obsolete variants, inconsistent option names, unnecessary hidden products, and abandoned categories should be reviewed before migration because they can distort both pricing and validation.

#### 3. Map category, storefront, and navigation structure <a href="#id-3-map-category-storefront-and-navigation-structure" id="id-3-map-category-storefront-and-navigation-structure"></a>

Categories and navigation should be prepared as business structure, not only as menus. In CS-Cart, categories may support storefront browsing, marketplace organization, vendor product discovery, search/filter behavior, and SEO route continuity.

Before migration, prepare the following:

* source category tree and any hidden or inactive categories
* high-value category landing pages
* category descriptions, images, metadata, and route expectations
* vendor-specific or marketplace-specific category behavior
* category assignments for complex or high-value products
* legacy redirects, high-traffic URLs, and search-driven landing pages
* navigation menus that are manually curated rather than generated from categories

If the source store uses categories as internal filing rather than customer-facing navigation, decide what should change before moving into CS-Cart. If category depth, product assignment, or navigation logic is unclear, Demo Migration review may show products as present but commercially difficult to find.

#### 4. Document vendor, seller, and marketplace ownership <a href="#id-4-document-vendor-seller-and-marketplace-ownership" id="id-4-document-vendor-seller-and-marketplace-ownership"></a>

Marketplace preparation is one of the most important CS-Cart readiness tasks. A merchant planning to use CS-Cart as a marketplace should not treat vendors as an afterthought. Vendor ownership can affect product visibility, order routing, seller responsibilities, customer communication, commissions, approvals, fulfillment, and reporting.

Prepare a clear vendor ownership map:

| Marketplace element   | Questions to answer before migration                                                                                      |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Vendors or sellers    | Which sellers should exist after migration? Are they active, inactive, pending, or historical?                            |
| Product ownership     | Which products belong to which seller? Are any products shared, duplicated, or admin-owned?                               |
| Order responsibility  | Which orders require seller-level interpretation? Is fulfillment handled by seller, admin, warehouse, or outside system?  |
| Approval workflows    | Are products, sellers, payments, shipping methods, or storefront changes subject to approval?                             |
| Financial context     | Are commissions, fees, payouts, or seller balances expected to be preserved, reconstructed, or handled outside migration? |
| Communication context | Are seller/customer messages, internal notes, or issue histories part of the required migration outcome?                  |

Not every marketplace-related source field can automatically become a native CS-Cart record. Some marketplace logic may be configuration, add-on behavior, custom development, external-system data, or Custom Service work. The earlier this is separated, the easier it is to choose the right migration approach.

#### 5. Clarify customer, account, and buyer-role meaning <a href="#id-5-clarify-customer-account-and-buyer-role-meaning" id="id-5-clarify-customer-account-and-buyer-role-meaning"></a>

Customer data should be prepared according to how buyers will use the target store. A CS-Cart migration may involve ordinary retail customers, business buyers, marketplace sellers, vendor users, administrators, company accounts, or customer groups with different pricing and access expectations.

Prepare representative account examples:

* ordinary retail customer with order history
* repeat buyer with saved addresses and customer group context
* business buyer with company, department, or approval expectations
* seller or vendor account if marketplace functionality is involved
* account with special pricing, tax handling, shipping behavior, or payment expectations
* inactive, duplicate, guest, or merged accounts that may need cleanup

The preparation goal is to identify what a migrated customer must be able to do after launch. Login, address review, order history access, product visibility, vendor access, pricing display, and account role behavior should not be assumed from the presence of a customer record alone.

#### 6. Prepare order and fulfillment history for review <a href="#id-6-prepare-order-and-fulfillment-history-for-review" id="id-6-prepare-order-and-fulfillment-history-for-review"></a>

Order history is often where hidden operational dependencies appear. In CS-Cart, orders may need customer context, product snapshots, vendor ownership, payment status, shipment status, taxes, discounts, coupons, fulfillment responsibility, and notes. Marketplace and B2B cases can make this more sensitive because the order may represent several roles, sellers, or workflows.

Before migration, identify order samples that include:

* ordinary completed orders
* orders with discounts, coupons, taxes, refunds, returns, or partial fulfillment
* marketplace orders involving one seller and multiple sellers
* B2B or wholesale orders with customer-specific pricing or payment terms
* orders affected by shipping method, carrier, warehouse, or vendor workflow
* orders with internal notes, customer notes, external references, or imported IDs
* recent orders that may affect Recent Data Migration planning

The merchant should also decide which historical order details are required for customer service, accounting, fulfillment review, or reporting. If some order information is controlled by ERP, accounting, shipping, tax, or vendor systems, that ownership should be documented before migration.

#### 7. Identify add-ons, themes, custom development, and hosting dependencies <a href="#id-7-identify-add-ons-themes-custom-development-and-hosting-dependencies" id="id-7-identify-add-ons-themes-custom-development-and-hosting-dependencies"></a>

CS-Cart projects often involve add-ons, themes, custom development, managed hosting, on-premises deployment, partner work, or marketplace extensions. These layers can affect the target result even when the core data migration is accurate.

Prepare an inventory of the target-side and source-side dependencies:

| Dependency layer   | What to document                                                                                       | Migration implication                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Add-ons            | Features that control pricing, checkout, vendors, shipping, search, SEO, payments, or catalog behavior | Determines whether migrated data requires post-migration configuration or Add-on review.       |
| Themes             | Product page layouts, category templates, banners, navigation, content blocks, and mobile presentation | Helps separate data migration from storefront presentation work.                               |
| Custom development | Custom fields, workflows, source scripts, special checkout behavior, vendor rules, or API logic        | Often requires Custom Service review when the expected result is not standard target behavior. |
| Hosting/deployment | Cloud, on-premises, managed hosting, server access, staging environment, and launch environment        | Affects test readiness, performance review, deployment timing, and launch coordination.        |
| External systems   | ERP, CRM, accounting, shipping, tax, warehouse, marketplace channels, and analytics systems            | Clarifies which systems own data truth and what must be reconnected after migration.           |

This inventory should not become a generic technical checklist. It should focus on dependencies that affect migrated data meaning, target configuration, validation, and launch readiness.

#### 8. Clean source data before execution <a href="#id-8-clean-source-data-before-execution" id="id-8-clean-source-data-before-execution"></a>

Source cleanup is most useful when it removes ambiguity that would otherwise be carried into CS-Cart. The merchant does not need to perfect every record, but should address problems that affect target usability.

Common cleanup areas include:

* duplicate products, SKUs, vendors, or customer accounts
* obsolete categories, hidden products, and abandoned landing pages
* inconsistent option names, attribute values, or product types
* inactive sellers, unresolved seller approvals, or abandoned vendor records
* unclear customer groups, tax treatment, account roles, or B2B pricing rules
* order statuses that do not reflect real business state
* broken image references, missing product media, and outdated downloadable files
* custom fields that mix internal notes with customer-facing information

Cleanup decisions should be documented. If records are intentionally retained for history, reporting, customer service, or compliance, they should not be removed simply because they look old. The goal is to distinguish useful history from migration noise.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

The preparation work can be organized into a staged sequence so the merchant does not try to solve every issue at once.

| Step | Preparation task                                        | Practical outcome                                                                                                                            |
| ---- | ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Define the target CS-Cart model                         | Confirms whether the migration supports a store, marketplace, B2B/B2C model, headless implementation, mobile marketplace, or custom project. |
| 2    | Inventory source data and business roles                | Identifies which products, vendors, customers, orders, categories, and integrations carry operational meaning.                               |
| 3    | Separate native data from configured or custom behavior | Clarifies what can be migrated as records, what must be configured in CS-Cart, and what may need Custom Service.                             |
| 4    | Clean obvious source ambiguity                          | Reduces duplicate, obsolete, inconsistent, or abandoned records before they distort target review.                                           |
| 5    | Select Demo Migration samples                           | Creates a representative sample set that can reveal whether target interpretation is correct.                                                |
| 6    | Confirm Add-on and integration dependencies             | Prevents the migration result from being blamed for behavior owned by extensions or external systems.                                        |
| 7    | Define launch-critical validation outcomes              | Establishes what must be proven before Full Migration, launch, or Recent Data Migration planning.                                            |

This sequence keeps preparation tied to migration decisions. It also helps avoid premature customization: some issues can be resolved through cleanup, mapping, target configuration, or Add-ons, while others clearly belong in Custom Service review.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should be prepared as an evidence stage. A useful CS-Cart Demo Migration sample should reveal how the Target Platform interprets catalog, marketplace, customer, order, storefront, and integration-sensitive data.

| Sample type                | Include examples that show                                                                                       | Why it matters                                                                             |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Core catalog products      | Simple products, variation-heavy products, attribute-rich products, products with images, and high-value SKUs    | Proves basic product usability and catalog interpretation.                                 |
| Marketplace products       | Products owned by different sellers, seller-restricted items, inactive seller products, and admin-owned products | Shows whether vendor ownership and product responsibility can be reviewed.                 |
| Categories and routes      | Deep categories, high-traffic categories, SEO-sensitive routes, and manually curated navigation pages            | Reveals whether storefront browsing and URL continuity can be evaluated.                   |
| Customer accounts          | Retail buyers, business buyers, customer groups, guest orders, repeat customers, and marketplace seller users    | Tests whether account meaning survives migration.                                          |
| Orders                     | Completed, discounted, refunded, marketplace, multi-seller, B2B, recent, and integration-sensitive orders        | Shows whether order history remains useful for customer service and operations.            |
| Add-on or custom behavior  | Records affected by extensions, custom fields, scripts, checkout logic, shipping rules, or payment handling      | Helps determine whether standard capability is enough or Custom Service review is needed.  |
| External-system references | ERP IDs, fulfillment references, marketplace channel IDs, vendor codes, or accounting-related identifiers        | Clarifies whether outside-system context must be preserved, mapped, or handled separately. |

A weak Demo Migration sample includes only clean, simple, recent records. A strong sample includes the cases that would cause launch risk if they were misunderstood.

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

If the Source Platform is a Custom Platform or heavily modified platform, preparation should begin with source interpretation. Custom source data may contain business meaning that is not visible in standard exports.

Before execution, prepare:

* source database structure or export schema where available
* custom product, customer, order, vendor, and fulfillment fields
* outside-system identifiers and integration references
* custom pricing, approval, checkout, or seller workflows
* source-side scripts, modules, extensions, or custom code that shaped the data
* examples of expected target behavior after migration
* documentation showing which fields are still active and which are historical

Custom Platform cases should be reviewed through Custom Service. That review helps determine whether the migration requires custom migration logic adjustment, Advanced Data Mapping, Advanced Data Configure, Tailored Add-ons, Custom Add-ons, or broader bespoke handling.

### What Should Be Escalated Before Execution <a href="#what-should-be-escalated-before-execution" id="what-should-be-escalated-before-execution"></a>

Some findings should be escalated before the merchant proceeds with migration execution because they may affect service fit, scope, timeline, or validation expectations.

| Escalation signal                                               | Why it should be reviewed early                                                                          |
| --------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Vendor ownership is unclear                                     | Marketplace products and orders may migrate without reliable seller context.                             |
| Product options or attributes are inconsistent                  | The target catalog may become searchable but commercially confusing.                                     |
| Customer groups or B2B roles are undocumented                   | Buyer access, pricing, tax treatment, and account behavior may be difficult to validate.                 |
| Order history depends on external systems                       | Payment, fulfillment, tax, accounting, or seller context may not be fully represented in source exports. |
| Add-ons control important behavior                              | Target results may depend on configuration or extension behavior rather than record migration alone.     |
| Custom source fields carry business meaning                     | Standard migration capability may not know how to interpret source-specific logic.                       |
| Launch requires headless, mobile, or custom storefront behavior | Data migration must be coordinated with storefront implementation and integration testing.               |
| Recent source activity is high                                  | Recent Data Migration planning may be needed to reduce the freshness gap before launch.                  |

Escalation does not always mean the platform is a poor fit. It means the migration plan should be adjusted before execution, rather than corrected under launch pressure.

### Conclusion <a href="#conclusion" id="conclusion"></a>

CS-Cart preparation should make the future operating model visible before migration starts. A merchant should know whether the Target Platform is expected to operate as a standard store, marketplace, B2B/B2C environment, mobile marketplace, headless implementation, or custom e-commerce project. That decision shapes how products, vendors, customers, orders, categories, add-ons, integrations, and custom fields should be prepared.

The strongest preparation does not try to document everything equally. It identifies the records and workflows that prove the business will still work after migration: products that reveal catalog complexity, vendors that reveal marketplace ownership, customers that reveal buyer roles, orders that reveal operational context, and integrations that reveal system ownership.

Before starting a CS-Cart migration, use Demo Migration and Live Chat to review representative product, vendor, customer, order, storefront, add-on, and integration samples. If the source structure includes custom fields, marketplace workflows, external identifiers, or heavily modified behavior, confirm whether the requirement should move into Custom Service before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Should source data be cleaned before migrating to CS-Cart?**

Yes, source data should be cleaned where ambiguity affects target usability. Duplicate SKUs, unclear vendor assignments, obsolete categories, inconsistent options, abandoned customer groups, and inaccurate order statuses can make the CS-Cart result harder to validate. Historical data that is needed for service, reporting, or compliance should be preserved intentionally rather than removed casually.

**What should be included in a CS-Cart Demo Migration sample?**

A strong sample should include ordinary products, complex products, vendor-owned products, important categories, high-value URLs, representative customers, marketplace or B2B accounts, order-history examples, records affected by add-ons, and integration-sensitive data. The sample should reveal whether CS-Cart can preserve business meaning, not only whether records appear.

**Do add-ons need to be installed before migration?**

Not always. Some add-ons affect post-migration configuration or storefront behavior rather than the migration process itself. However, if an Add-on controls pricing, vendors, shipping, search, checkout, payments, or required data fields, its role should be documented before execution so the migrated data can be interpreted correctly.

**When does CS-Cart preparation require Custom Service review?**

Custom Service review is needed when the migration involves customization, modification, Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, custom fields, source-specific workflows, third-party data, outside-system identifiers, or integration-dependent behavior beyond standard migration capability.

**How should marketplace vendors be prepared before migration?**

Vendors should be reviewed as business owners, not just contact records. The merchant should identify active sellers, inactive sellers, product ownership, order responsibility, approval workflows, seller communication needs, commission or payout context, and any external systems that control vendor-related data.
