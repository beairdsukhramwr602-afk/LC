# OsCommerce Pre-Migration Preparation Checklist

Preparing for a migration to osCommerce should start with evidence, not assumptions. osCommerce can support detailed catalog structures, customer groups, order history, modules, CMS content, SEO fields, and open-source customization, but the migration outcome depends on how clearly the source store is understood before data is moved.

Preparation is especially important when the source store is old, heavily customized, related to osCommerce lineage, or dependent on add-ons. A clean source with predictable products, categories, customers, orders, and CMS Pages may be straightforward to sample. A legacy or extension-heavy store needs stronger evidence before the migration path can be treated as stable.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation should make the target scope testable. The goal is not to configure every osCommerce setting before migration, but to identify the records, relationships, and business rules that must be represented in the target store.

A useful preparation process should clarify:

* the actual source platform, version, database structure, and add-on footprint;
* which records should migrate and which records should be left behind or filtered;
* how products, attributes, properties, categories, brands, stock, and SEO fields should be interpreted;
* whether customer groups, B2B logic, or account behavior require special review;
* which order samples prove historical readability;
* which modules, extensions, custom tables, and outside-system identifiers affect scope;
* which URLs, CMS Pages, and storefront content must be checked after migration;
* whether Standard Service, Add-ons, Managed Service, or Custom Service review is the safer path.

### 1. Confirm the Source Platform, Version, and Codebase <a href="#id-1-confirm-the-source-platform-version-and-codebase" id="id-1-confirm-the-source-platform-version-and-codebase"></a>

The first preparation priority is confirming what the source store actually is. A store may be described as osCommerce, but its real structure may come from an old version, a fork, a customized codebase, or years of add-on changes.

Prepare the following evidence:

| Evidence to gather                               | Why it matters                                                                                                      |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Source platform name and version                 | Confirms whether the source is a standard osCommerce installation, an older version, a fork, or a related platform. |
| Database backup or schema notes                  | Reveals custom tables, modified fields, old add-on tables, and non-standard relationships.                          |
| List of installed add-ons or modules             | Helps identify extension-owned product, customer, order, SEO, checkout, payment, shipping, or integration data.     |
| Notes from prior developers or maintainers       | Helps explain custom fields, manual workarounds, and modifications that are not visible in exports.                 |
| Target osCommerce version and target environment | Confirms the intended v4 target context, hosting assumptions, and compatibility expectations.                       |

If the source is old, forked, or heavily modified, preparation should not assume that a standard field-to-field migration will preserve meaning. Custom Service review may be needed when non-standard structures carry business data.

### 2. Prepare the Product and Catalog Evidence <a href="#id-2-prepare-the-product-and-catalog-evidence" id="id-2-prepare-the-product-and-catalog-evidence"></a>

Products are usually the first area merchants check, but product preparation should go beyond product count. osCommerce catalog meaning can involve categories, brands, images, attributes, properties, product groups, stock, suppliers, SEO fields, and storefront visibility.

Prepare product samples that include:

* simple products with ordinary price and category assignment;
* products with multiple images and image metadata;
* products with brands or manufacturer-style context;
* products with selectable options or attributes;
* products with properties, specifications, or filterable technical details;
* products that belong to multiple categories;
* products with sale, new, featured, or visibility behavior;
* products with stock-sensitive options or warehouse/supplier relationships;
* downloadable, bundled, grouped, or otherwise special products;
* products with high-value SEO fields or historical URLs.

The sample set should expose the real catalog model. If only simple products are sampled, the migration can appear cleaner than the full catalog actually is.

### 3. Map Categories, Brands, Navigation, and Discovery <a href="#id-3-map-categories-brands-navigation-and-discovery" id="id-3-map-categories-brands-navigation-and-discovery"></a>

osCommerce storefront discovery may depend on categories, brands, filters, search, sales channels, menus, and content pages. Preparation should identify how shoppers currently find products and which browsing paths must be preserved or rebuilt.

Prepare:

| Area                                  | Preparation task                                                                                                                       |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Category hierarchy                    | Export or document top-level categories, subcategories, hidden categories, landing categories, and multi-category product assignments. |
| Brand or manufacturer browsing        | Identify whether brands carry SEO, filtering, or merchandising value.                                                                  |
| Search and filters                    | Note filterable specifications, properties, attributes, and custom search behavior.                                                    |
| Sales channels or storefront contexts | Identify whether products appear differently across storefronts, languages, currencies, or sales channels.                             |
| Menu and landing-page structure       | List important category pages, CMS Pages, and navigation links that shape customer journeys.                                           |

The target store should not be judged only from admin product records. Preparation should make it possible to check whether customers can find the right products in the intended storefront paths.

### 4. Prepare Customer, Account, and Group Samples <a href="#id-4-prepare-customer-account-and-group-samples" id="id-4-prepare-customer-account-and-group-samples"></a>

Customer data can affect more than account history. In osCommerce, customer groups, addresses, guest status, reviews, language, credit or trade behavior, and B2B logic can influence how customers are interpreted.

Prepare customer samples that include:

* ordinary registered customers;
* guest customers with completed orders;
* customers with multiple billing or shipping addresses;
* customers assigned to special groups;
* wholesale, trade, tax-exempt, approved, or restricted-access accounts where applicable;
* customers with reviews or product activity;
* customers with varied order histories;
* customers with language or currency context where relevant.

Password expectations should be set early. Password continuity depends on source and target compatibility. If passwords cannot be preserved in a way that supports customer login, first-login reset planning and customer communication should be part of readiness planning.

### 5. Prepare Order and Historical Workflow Samples <a href="#id-5-prepare-order-and-historical-workflow-samples" id="id-5-prepare-order-and-historical-workflow-samples"></a>

Order migration should preserve historical readability. Preparation should identify order examples that represent how the business actually uses order history.

Include orders with:

* different order statuses;
* paid, unpaid, refunded, canceled, and partially fulfilled states;
* discounts, coupons, store credit, or manual adjustments;
* multiple payment and shipping methods;
* tax-sensitive totals;
* customer and admin comments;
* tracking numbers or shipment history;
* invoices, packing slips, or transaction references;
* guest and registered-customer orders;
* multi-currency or multilingual context where relevant.

Do not confuse historical order preservation with live checkout readiness. Migrated order labels can help the team read past transactions, but target payment, shipping, tax, and checkout settings must still be configured and tested separately.

### 6. Inventory Modules, Extensions, and Custom Data <a href="#id-6-inventory-modules-extensions-and-custom-data" id="id-6-inventory-modules-extensions-and-custom-data"></a>

Modules and add-ons can change the meaning of products, customers, orders, checkout, SEO, reports, B2B workflows, marketplaces, and integrations. Preparation should classify each extension according to its migration relevance.

| Module or custom area                                          | What to confirm                                                                                               |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Payment modules                                                | Whether historical labels only need preservation, or whether payment-specific data must migrate.              |
| Shipping modules                                               | Whether rates, carriers, zones, labels, or tracking records are data, configuration, or integration behavior. |
| B2B or customer-group modules                                  | Whether groups affect price, visibility, tax, approval, or account access.                                    |
| SEO modules                                                    | Whether URLs, metadata, canonicals, redirects, or sitemap behavior are module-owned.                          |
| Marketplace, accounting, ERP, CRM, POS, or shipping connectors | Whether outside-system identifiers must remain traceable.                                                     |
| Custom tables or fields                                        | Whether they contain business data that standard migration cannot interpret automatically.                    |

If module-owned or custom data must be included in the migration, the requirement should be reviewed before service scope is finalized.

### 7. Prepare SEO, CMS, and Storefront Content <a href="#id-7-prepare-seo-cms-and-storefront-content" id="id-7-prepare-seo-cms-and-storefront-content"></a>

Content and search continuity can affect the perceived quality of an osCommerce migration as much as product records. Prepare a priority list instead of treating every historical page equally.

Prepare:

* high-value product URLs;
* high-value category and brand URLs;
* CMS Pages;
* landing pages;
* metadata for important pages;
* canonical or redirect expectations;
* images with important alt text or SEO context;
* menus and navigation links;
* banners or homepage content that should be rebuilt or reviewed;
* email templates if they affect customer communication.

The goal is to know which pages matter most before Demo Migration review. This helps the team judge whether SEO fields, page names, CMS content, and redirect planning are acceptable.

### 8. Confirm Hosting, Access, and Technical Responsibility <a href="#id-8-confirm-hosting-access-and-technical-responsibility" id="id-8-confirm-hosting-access-and-technical-responsibility"></a>

osCommerce gives merchants open-source control, but the target store still needs a technical operating model. Migration preparation should confirm who will manage the environment before the store goes live.

Confirm:

* target hosting responsibility;
* PHP and database readiness;
* access to the target admin and database where required;
* backup and restore expectations;
* who will install, configure, and maintain modules;
* who will manage themes and code changes;
* who will test upgrades and security updates;
* who will review checkout, payment, shipping, and tax settings.

This preparation prevents migration from being treated as the only launch requirement. A migrated store still needs a maintained target environment.

### 9. Choose Demo Migration Samples Deliberately <a href="#id-9-choose-demo-migration-samples-deliberately" id="id-9-choose-demo-migration-samples-deliberately"></a>

Demo Migration samples should reveal risk, not hide it. A weak sample set can make a difficult migration look simple.

A strong osCommerce Demo Migration sample set should include:

| Sample type                   | Why it should be included                                                                   |
| ----------------------------- | ------------------------------------------------------------------------------------------- |
| Complex products              | Tests attributes, properties, product groups, images, brands, stock, and SEO fields.        |
| Deep categories               | Tests hierarchy, multi-category assignment, and product discovery.                          |
| Customer groups               | Tests pricing, account, B2B, tax, visibility, or segmentation meaning.                      |
| Varied orders                 | Tests status history, payment/shipping labels, comments, discounts, invoices, and tracking. |
| CMS Pages and high-value URLs | Tests content continuity, metadata, page names, and SEO planning.                           |
| Module-dependent records      | Tests whether extension-owned data has been included, excluded, or escalated correctly.     |
| Legacy or custom records      | Tests whether older-version or modified-source structures can be interpreted safely.        |

### 10. Identify Add-on and Custom Service Signals Early <a href="#id-10-identify-add-on-and-custom-service-signals-early" id="id-10-identify-add-on-and-custom-service-signals-early"></a>

Some osCommerce migrations remain straightforward after preparation. Others reveal scope signals that should be handled before Full Migration.

Consider Add-ons when the goal is filtering, supported mapping, or supported data configuration:

* use the Data Filter Add-on when only selected eligible records should migrate;
* use Advanced Data Mapping when supported source and target fields need configurable mapping;
* use Advanced Data Configure when migrated data values need supported modification before reaching the target store.

Custom Service review should be considered when the requirement involves:

* a Custom Platform source or target;
* old or forked osCommerce-related structures;
* custom database tables;
* custom code;
* extension-owned records;
* outside-system identifiers;
* non-standard B2B, checkout, payment, shipping, tax, or order logic;
* tailored migration behavior beyond Standard Add-on capability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

osCommerce preparation should make the migration testable before the main data move. The source version, catalog structure, customer groups, orders, modules, content, SEO priorities, hosting environment, and custom data should be understood early enough to shape the Demo Migration and service scope. Without that preparation, a migration can appear successful at the record-count level while still missing the structures that make the target store usable.

Before starting Full Migration, prepare a sample set that reflects real business complexity and review the Demo Migration results carefully. If the sample exposes unsupported custom data, module-owned records, old-version behavior, or transformation needs beyond standard service capability, resolve the scope through Add-ons or Custom Service review before continuing.

### FAQs <a href="#faqs" id="faqs"></a>

**What should I prepare first for an osCommerce migration?**

Start by confirming the source platform, version, database structure, installed modules, and custom changes. This determines whether the migration can be treated as a standard osCommerce migration or whether legacy, forked, or custom data needs additional review.

**Should I prepare every product as a Demo Migration sample?**

No. Demo Migration samples should be representative, not exhaustive. Include products that expose real complexity, such as attributes, properties, product groups, multiple categories, images, brands, stock behavior, downloadable products, and SEO fields.

**Why should customer groups be reviewed before migration?**

Customer groups can affect pricing, tax, approval, visibility, payment access, shipping access, or B2B behavior. If they are migrated as labels only, the target store may lose important customer treatment rules.

**Are SEO URLs part of pre-migration preparation?**

Yes. High-value product, category, brand, and CMS Page URLs should be identified before migration validation. Redirect and metadata planning is easier when priority URLs are known early.

**When should I request Custom Service review before migrating to osCommerce?**

Request Custom Service review when the source includes Custom Platform data, old or forked osCommerce structures, custom database tables, extension-owned records, outside-system identifiers, or tailored business logic that standard service capability cannot safely interpret.
