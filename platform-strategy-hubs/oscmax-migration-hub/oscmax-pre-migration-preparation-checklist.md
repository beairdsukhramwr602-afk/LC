# osCMax Pre-Migration Preparation Checklist

osCMax preparation starts with a practical reality: an osCMax store can look familiar because of its osCommerce roots, but its migration scope often depends on what has been added, changed, bundled, ported, or maintained over time. A clean product, customer, and order export is useful, but it does not prove that the store’s commercial behavior is fully understood.

Before migration begins, the merchant should separate three layers. The first layer is standard commerce data such as categories, products, customers, orders, reviews, coupons, and content. The second layer is osCMax package behavior such as templates, admin settings, image handling, modules, and contribution-driven features that may be expected by the business. The third layer is custom behavior: modified files, custom tables, old code, contribution ports, handcrafted reports, and abandoned functions that may not have a direct Target Platform equivalent.

A strong preparation phase provides enough evidence to confirm what belongs in Standard Service, what needs Managed Service coordination, what may fit Add-ons, and what should be reviewed through Custom Service. It also gives the merchant a more realistic launch plan. The goal is not to collect everything blindly; it is to collect the right evidence before Demo Migration exposes preventable gaps.

### Confirm the osCMax Version and Store History <a href="#confirm-the-oscmax-version-and-store-history" id="confirm-the-oscmax-version-and-store-history"></a>

The first preparation task is to identify the running osCMax version, the upgrade path, and the history of major changes. Version evidence matters because osCMax stores may come from different legacy lines, and older version assumptions can affect contribution compatibility, template structure, database fields, PHP behavior, image handling, and admin expectations.

A merchant should not rely only on memory or a storefront footer. The preparation package should include admin screenshots where available, database version references, hosting control panel notes, old release notes retained by the owner, and any internal maintenance log. When several clues disagree, treat that as a migration signal rather than an inconvenience. It may indicate partial upgrades, manual patching, an unofficial package, or old contribution code carried forward without a clean version trail.

Version history also helps define validation scope. A store that has stayed stable for years may still contain outdated assumptions that only appear when customer groups, shipping modules, image galleries, or promotional rules are tested. A store that has been updated repeatedly may have mixed database and file behavior. Both cases can be migrated, but they require different evidence.

| Preparation evidence           | Why it matters for osCMax                                      | Action before Demo Migration                                                    |
| ------------------------------ | -------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Admin version clues            | Identifies the likely osCMax line and old package assumptions. | Capture screenshots and compare with file/database evidence.                    |
| Hosting PHP/MySQL notes        | Reveals whether the store depends on old runtime behavior.     | Record current versions and planned Target Platform assumptions.                |
| Upgrade or maintenance history | Shows whether the store is clean, patched, or mixed.           | Flag uncertain areas for Managed Service or Custom Service review.              |
| Known contribution list        | Helps identify business behavior beyond core records.          | Group contributions by catalog, checkout, content, admin, and reporting impact. |

The practical preparation question is: can the migration team explain what kind of osCMax store is being migrated? Without that answer, the scope may look smaller than it really is.

### Audit Core Commerce Records Before Export <a href="#audit-core-commerce-records-before-export" id="audit-core-commerce-records-before-export"></a>

Core commerce records still matter. Categories, Products, Customers, Orders, Reviews, Coupons, CMS Pages, and Blog Posts are the baseline for migration planning. For osCMax, however, these records must be reviewed for both structure and meaning. A category is not only a category if templates, boxes, or navigation behavior give it a special storefront role. A product is not only a product if image behavior, attributes, options, specials, wholesale restrictions, or custom fields change how customers buy it.

Start with record counts, but do not stop there. Identify active and inactive products, discontinued products, products without images, products with unusual attributes, categories with no products, orphaned images, customer records without complete addresses, orders with unusual statuses, coupon records that no longer match current promotion rules, and content pages that are still indexed by search engines.

osCMax preparation should include representative samples. A Demo Migration sample should contain a simple product, a product with attributes, a product with multiple images, a product affected by specials or discounts, a customer with order history, an order with shipping and payment details, and any record type that depends on contribution behavior. A sample that only includes clean products can make the migration appear simpler than the live store.

| Data area  | Preparation check                                                                      | Risk if skipped                                               |
| ---------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Categories | Review hierarchy, inactive categories, and storefront navigation assumptions.          | Category structure may move while navigation meaning is lost. |
| Products   | Identify attributes, image behavior, specials, downloads, and custom fields.           | Products may appear correct but fail commercial validation.   |
| Customers  | Review groups, address data, account status, and wholesale or restricted-access logic. | Customer segmentation or access expectations may be missed.   |
| Orders     | Review statuses, payment/shipping references, tax, discounts, and admin notes.         | Historical order meaning may be incomplete after migration.   |
| CMS Pages  | Identify active informational pages, policy pages, and indexed landing pages.          | SEO and trust content may be omitted or recreated too late.   |

The preparation output should be a scope inventory, not a raw export folder. Each record type should be tagged as straightforward, needs mapping, needs configuration review, or needs tailored review.

### Build a Contribution and Customization Inventory <a href="#build-a-contribution-and-customization-inventory" id="build-a-contribution-and-customization-inventory"></a>

The contribution inventory is the most important osCMax-specific preparation task. Many osCMax stores are valuable precisely because they accumulated enhancements over time. Those enhancements may affect catalog management, shipping, payment, image presentation, order entry, order export, customer restrictions, promotions, content boxes, or admin productivity. Some of that behavior may be irrelevant after migration. Some may need to be replaced by native Target Platform behavior. Some may require Custom Service because data or logic is stored outside standard records.

Do not list contributions only by name. Group them by business effect. A contribution that changes image popups belongs to storefront asset and media validation. A contribution that exports orders belongs to reporting and operations. A restricted content feature belongs to customer segmentation and content access. A special shipping table belongs to checkout and fulfillment logic. A template or menu enhancement belongs to storefront navigation.

For each contribution or modification, record four pieces of information: what business outcome it supports, where its data lives, whether it changes database structure, and whether the merchant still needs the same outcome after migration. This prevents the migration from preserving obsolete clutter while missing live business dependencies.

| Contribution category         | Typical osCMax evidence                                                          | Migration planning response                                                        |
| ----------------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Catalog and product behavior  | Attribute changes, image behavior, product display boxes, specials enhancements. | Confirm whether behavior becomes native configuration, Add-ons, or Custom Service. |
| Customer and access logic     | Wholesale forms, restricted articles, customer group rules.                      | Validate customer segmentation and account expectations.                           |
| Checkout and fulfillment      | Shipping tables, phone orders, payment-related adjustments.                      | Separate historical order data from live checkout configuration.                   |
| Admin and reporting           | Order exports, quick updates, unused-image tools.                                | Decide whether admin convenience must be rebuilt or can be retired.                |
| Template and interface assets | Template folders, button assets, custom boxes, menu behavior.                    | Preserve needed assets and validate storefront presentation separately.            |

The inventory should also identify abandoned features. A dead contribution may still leave database fields, files, or language entries behind. Those remnants can confuse migration planning if they are mistaken for active business requirements.

### Prepare Database, File, Template, and Asset Evidence <a href="#prepare-database-file-template-and-asset-evidence" id="prepare-database-file-template-and-asset-evidence"></a>

osCMax preparation requires database evidence and file evidence. The database shows records and configuration. The file tree shows custom code, templates, language files, images, modules, and older contribution assets. Both are needed because an osCMax store can depend on behavior that is not visible from admin exports alone.

The merchant should prepare a clean database export, a file copy, and a list of excluded sensitive credentials. The file copy should preserve the directory structure so templates, images, language files, buttons, boxes, and module files can be reviewed in context. Image folders are especially important. Older stores often contain unused images, multiple image conventions, or image subdirectories that must be interpreted before migration.

Template evidence deserves separate attention. osCMax storefront presentation may depend on template folders, custom CSS, navigation boxes, button assets, and layout assumptions that do not become Target Platform behavior automatically. Migration planning should separate content and asset preservation from full storefront redesign. Eligible data and defined migration needs can be handled through the appropriate migration scope, but the Target Platform theme, app stack, and design implementation remain separate planning areas unless specifically scoped through the right service path.

A useful file-evidence package includes:

* database export with table structure preserved;
* file copy with templates, images, language files, and modules retained;
* admin access for configuration confirmation;
* sample storefront URLs for key product, category, content, and checkout paths;
* notes on active templates and known custom files;
* notes on any functions the merchant no longer uses.

This evidence helps avoid two opposite mistakes: migrating only visible records while missing hidden dependencies, or trying to preserve every old file artifact even when it no longer supports the new operating model.

### Review Hosting, Runtime, Security, and Maintenance Conditions <a href="#review-hosting-runtime-security-and-maintenance-conditions" id="review-hosting-runtime-security-and-maintenance-conditions"></a>

Because osCMax is a self-hosted legacy-family platform, hosting evidence is part of migration preparation. The merchant should document current PHP version, database version, server environment, SSL setup, cron jobs if any, email sending behavior, image library behavior, and old security or maintenance notes. Runtime details matter because old code can work in the current environment while failing under modern assumptions.

This review is not only technical hygiene. It affects migration planning. Old PHP calls, outdated libraries, hand-edited files, unsupported modules, or brittle server assumptions may explain why the store behaves in a way that is not obvious from the database. When these issues exist, they should be treated as scope evidence rather than post-launch surprises.

Hosting and maintenance review also helps decide what should not be carried forward. A legacy store may contain old patches, obsolete utilities, abandoned payment modules, or outdated admin conveniences. If the merchant is moving to a modern Target Platform, some of those functions should be replaced or retired instead of reproduced.

| Hosting or maintenance signal   | What it may indicate                                      | Preparation response                                                 |
| ------------------------------- | --------------------------------------------------------- | -------------------------------------------------------------------- |
| Old PHP or database version     | Legacy code dependency or outdated contribution behavior. | Record environment details and flag potential Custom Service review. |
| Hand-edited core files          | Business logic may live outside normal records.           | Compare file changes with active business requirements.              |
| Old payment or shipping modules | Checkout behavior may not map directly.                   | Validate historical order data separately from live target setup.    |
| Template-specific assets        | Storefront behavior depends on file structure.            | Include assets in validation plan, not only in design planning.      |
| Missing maintenance history     | Store behavior may be undocumented.                       | Expand Demo Migration samples and validation responsibilities.       |

The strongest preparation outcome is a store that can be explained operationally: what the data is, what the old store does with it, what must continue, and what can change.

### Prepare SEO, Content, and Storefront Continuity Evidence <a href="#prepare-seo-content-and-storefront-continuity-evidence" id="prepare-seo-content-and-storefront-continuity-evidence"></a>

osCMax preparation should include storefront continuity evidence before the migration scope is locked. Older osCMax stores may contain content and navigation elements that are not obvious from product and order exports. The merchant should identify policy pages, information pages, landing pages, category pages that attract organic traffic, and storefront boxes or menus that customers use to navigate the store. These items may not all become migrated records, but they still influence launch readiness.

SEO preparation should start with current URLs, indexed pages, metadata, redirects, and priority landing pages. If the old store uses contribution-driven URLs, custom category paths, template-managed links, or manually maintained content blocks, those patterns should be documented before migration. The migration project should distinguish between migrated data and SEO work that must be handled through target-side configuration, redirects, content review, or separate implementation.

Content evidence also matters for customer trust. Shipping information, payment instructions, return terms, wholesale contact pages, downloadable-product instructions, and account-related notices can affect conversion after launch. If these pages are hidden in template files or custom boxes, they may be overlooked by a database-only review. A complete preparation checklist should therefore combine database evidence with storefront screenshots and URL lists.

| Storefront evidence                | Why it matters                                             | Preparation output                                        |
| ---------------------------------- | ---------------------------------------------------------- | --------------------------------------------------------- |
| Priority category and product URLs | Protects SEO-sensitive navigation and redirect planning.   | URL list with page purpose and target handling note.      |
| Content and policy pages           | Preserves trust, compliance, and customer-service context. | CMS Pages inventory with keep, rewrite, or retire status. |
| Custom boxes or menus              | May represent template behavior, not standard records.     | Screenshot and file-location notes for later validation.  |
| Metadata and page titles           | Supports search continuity review.                         | Export or crawl sample for high-value pages.              |
| Downloadable-product instructions  | Affects customer expectations after migration.             | Sample products and customer-facing instructions.         |

The preparation decision should be explicit: which storefront elements are part of data migration, which are part of target configuration, which are content tasks, and which are no longer needed. Without that separation, launch teams often discover that records migrated correctly while the storefront still feels incomplete.

### Identify What Should Be Retired Instead of Migrated <a href="#identify-what-should-be-retired-instead-of-migrated" id="identify-what-should-be-retired-instead-of-migrated"></a>

A strong osCMax preparation checklist should not treat every legacy artifact as valuable. Old stores often carry unused contribution files, obsolete admin utilities, outdated image handlers, inactive modules, abandoned templates, old language entries, and content that no longer supports the business. Migrating everything without judgment can make the new store harder to validate and can preserve technical debt that the merchant intended to leave behind.

Retirement decisions should be made before Full Migration, not during launch pressure. The merchant should classify each questionable item as active, historical-only, replaceable, obsolete, or unknown. Active items should be validated. Historical-only items may need to remain visible in order records or customer records but not become live storefront behavior. Replaceable items may be handled by native Target Platform features or target-side apps. Obsolete items should be excluded or ignored where appropriate. Unknown items should be sampled during Demo Migration or reviewed through Managed Service or Custom Service if they may affect business continuity.

This discipline protects both scope and quality. It prevents unnecessary Custom Service requests for features no one uses, but it also prevents the opposite mistake: retiring something that still supports checkout, fulfillment, customer segmentation, or reporting. The preparation phase should produce a clear keep/replace/retire list for contribution behavior and storefront assets.

### Define Demo Migration Samples and Validation Responsibilities <a href="#define-demo-migration-samples-and-validation-responsibilities" id="define-demo-migration-samples-and-validation-responsibilities"></a>

A Demo Migration should be designed around osCMax complexity, not random record volume. The sample should include records that test the assumptions behind the migration scope. If the store uses standard products, simple categories, and basic orders, the sample can remain straightforward. If the store depends on customer restrictions, special images, modified shipping, order export behavior, or content boxes, the sample should include those cases.

Validation responsibilities should also be assigned before the Demo Migration begins. The merchant should know who will check product attributes, images, categories, customers, orders, content pages, discounts, shipping references, payment labels, SEO-sensitive URLs, and storefront asset expectations. Migration execution and service-path guidance can support the process, but the merchant must confirm business meaning because only the merchant can decide whether the migrated result represents the old operation accurately.

The Demo Migration outcome should produce three decisions. First, what is ready for Full Migration under the current configuration? Second, what needs adjusted mapping, filtering, or configuration through Add-ons? Third, what requires Custom Service or target-side replacement because it depends on contribution-owned data, custom tables, or bespoke legacy logic?

| Sample type                        | What it proves                                                    | Escalation signal                                    |
| ---------------------------------- | ----------------------------------------------------------------- | ---------------------------------------------------- |
| Simple product                     | Baseline product mapping and category assignment.                 | Basic records are incomplete or misclassified.       |
| Product with attributes and images | Attribute meaning, asset handling, and product presentation data. | Options or images require manual interpretation.     |
| Customer with order history        | Account, address, and order relationship preservation.            | Customer context separates from historical orders.   |
| Promotional or restricted record   | Whether legacy commercial logic has a target equivalent.          | Logic is stored outside standard fields.             |
| Content or navigation page         | CMS Pages and SEO-sensitive content continuity.                   | Content exists only through template or custom code. |

A prepared Demo Migration prevents vague launch decisions. It creates evidence for the Full Migration plan.

### Align Preparation With Service Scope <a href="#align-preparation-with-service-scope" id="align-preparation-with-service-scope"></a>

Preparation should end with a practical service-scope reading. Clean core records with limited contribution dependency may stay within Standard Service or Managed Service. Bounded needs such as filtering, field mapping, or supported configuration adjustments may fit Add-ons. Contribution-owned records, custom tables, custom fields, bespoke transformations, unsupported record types, old code behavior, or Custom Platform requirements should be reviewed through Custom Service.

Entity Points should be considered when eligible new Products, Customers, Orders, and Blog Posts are first migrated. They should not be treated as a fit score or as a measure of osCMax complexity. A store with modest record counts can still require Custom Service if the important business behavior lives in custom contribution data.

Additional Migration Options should be planned only where follow-up migration has real value. For example, if Demo Migration confirms core data but the merchant later adjusts mapping or configuration, a follow-up action may use the last configuration or a new configuration depending on the case. If the merchant changes the migration scope materially, a new migration may be more appropriate. The preparation task is to make that choice deliberate rather than accidental.

### Conclusion <a href="#conclusion" id="conclusion"></a>

osCMax preparation is strongest when it treats the store as a layered legacy system: core osCommerce-like data, osCMax package behavior, contribution behavior, custom modifications, templates, assets, and hosting history. A merchant who prepares only exports may miss the very logic that makes the store operational. A merchant who prepares evidence around version line, modules, templates, files, database structure, and validation samples creates a realistic basis for Demo Migration, Full Migration, Add-ons, Managed Service, and Custom Service decisions.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating from osCMax?**

Start with version evidence, database export, file copy, admin access, template information, contribution inventory, hosting details, and representative Demo Migration samples. These items explain both the records and the behavior around them.

**Why are files needed if the main data is in the database?**

Files may contain templates, modules, image conventions, language definitions, buttons, boxes, and custom code. In an osCMax store, important business behavior may depend on file-level changes as much as database records.

**Should every old contribution be recreated on the Target Platform?**

No. Each contribution should be reviewed by business outcome. Some can be replaced by native target behavior, some may fit Add-ons, some may require Custom Service, and some should be retired because they no longer support the future store.

**How should Demo Migration samples be chosen for osCMax?**

Choose samples that represent real complexity: products with attributes and images, customers with order history, records affected by promotions or restrictions, content pages, and any data affected by old modules or custom logic.
