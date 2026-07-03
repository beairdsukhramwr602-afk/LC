# Zen Cart Pre-Migration Preparation Checklist

Preparing for Zen Cart migration means preparing both data and operating context. Zen Cart is a self-hosted commerce environment, so a clean migration result depends on more than moving Products, Customers, Orders, and content records. The target installation, hosting stack, database access, modules, templates, product attributes, content pages, URLs, and legacy customizations all influence whether migrated data can be reviewed and used with confidence.

Strong preparation gives the Demo Migration a clear purpose. Instead of checking whether a few records appeared, the team can confirm whether the target Zen Cart store preserves catalog meaning, customer identity, order readability, pricing context, storefront continuity, and the boundaries between migrated records and target-side configuration.

### Confirm the Target Zen Cart Environment <a href="#confirm-the-target-zen-cart-environment" id="confirm-the-target-zen-cart-environment"></a>

Zen Cart readiness starts with the target environment because the platform is normally operated on merchant-controlled hosting. A migration can complete successfully from a data-transfer perspective and still be hard to validate if the target installation is unstable, incomplete, incompatible with expected modules, or inaccessible to the people who need to review the result.

Before Demo Migration, confirm the intended Zen Cart version, hosting stack, database access, SSL status, file permissions, backup process, email transport, and administrative access. These details are not background technical trivia. They determine whether product images can display, whether downloadable files can be protected, whether admin review can happen smoothly, whether orders can be inspected, and whether the target store is stable enough for a meaningful Full Migration decision.

| Preparation area     | What to confirm                                                                                         | Why it matters                                                                                                          |
| -------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Zen Cart version     | Target version, fresh installation or upgraded installation, and compatibility expectations             | Version and upgrade context can affect database behavior, modules, templates, language files, and plugin compatibility. |
| Hosting access       | Control panel, database access, FTP or SFTP, file permissions, SSL, backups, and error logs             | Migration review often requires both admin checks and technical checks.                                                 |
| Admin responsibility | Who can configure modules, templates, taxes, shipping, payment, and store settings                      | Next-Cart can migrate supported data, but target-side configuration still needs accountable ownership.                  |
| Launch baseline      | Whether the target is a clean store, a partially configured store, or an existing Zen Cart installation | Existing configuration can affect validation and may require more careful revalidation after migration.                 |

A prepared environment reduces false migration issues. If product images fail because file permissions are wrong, or checkout tests fail because payment modules are not configured, the team may misread target setup gaps as migration defects. Environment preparation prevents that confusion.

### Prepare Catalog and Attribute Evidence <a href="#prepare-catalog-and-attribute-evidence" id="prepare-catalog-and-attribute-evidence"></a>

Zen Cart catalog preparation should identify how the source store sells products, not just how many products exist. Product names, SKUs, prices, descriptions, images, categories, manufacturers, inventory, tax classes, and status values are basic checks. Attribute behavior is the deeper issue because Zen Cart product attributes may represent option names, option values, price adjustments, weight adjustments, downloads, and customer-selectable product choices.

Do not prepare only the simplest products. Select samples that expose the real catalog structure. Include a plain product, an attribute-heavy product, a downloadable product if relevant, a product with price adjustments, a product assigned to more than one category, a discounted product, a product affected by quantity pricing, and a product that depends on image or content placement.

| Sample type                   | Include when                                                              | Review focus                                                                                                              |
| ----------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Simple product                | The catalog includes ordinary physical items                              | Name, SKU, price, status, stock, description, images, category placement.                                                 |
| Attribute-heavy product       | Size, color, add-ons, configuration, or choice-based selling is important | Option names, option values, required selections, price adjustments, display order, and order readability.                |
| Downloadable product          | Digital delivery exists in the source store                               | File association, product type expectations, access rules, and post-order customer experience.                            |
| Discounted or special product | Pricing relies on specials, sales, group pricing, or quantity discounts   | Whether migrated price data remains understandable inside Zen Cart and whether live discount behavior needs target setup. |
| Multi-category product        | Products appear through multiple navigation paths                         | Category links, product discovery, URL behavior, and duplicate assumptions.                                               |

Catalog preparation should also mark which records are launch-critical. A store can have thousands of low-risk products, but a smaller group may carry most revenue, SEO value, or support volume. Those records should lead Demo Migration review.

### Prepare Customer and Order Review Samples <a href="#prepare-customer-and-order-review-samples" id="prepare-customer-and-order-review-samples"></a>

Customer and order preparation should preserve commercial meaning. Customers are not only names and email addresses. Addresses, customer groups, newsletter flags, account status, and historical identity may matter for service, segmentation, and post-launch communication. Orders are even more sensitive because they carry historical records of what was sold, how it was selected, what taxes and shipping were recorded, what discounts were applied, and what the customer expected.

Prepare order samples that include different statuses, payment labels, shipping labels, tax values, order comments, coupons, gift certificates, product attributes, downloads, and refunds or adjustments if available. The aim is not to reproduce live checkout logic from historical records. The aim is to ensure historical orders remain readable and useful after migration.

| Order sample                          | Why it should be included                                                       |
| ------------------------------------- | ------------------------------------------------------------------------------- |
| Completed order with simple products  | Confirms basic customer, product, total, and status readability.                |
| Order with attributes                 | Proves selected options remain visible and meaningful in order history.         |
| Discounted order                      | Confirms coupons, gift certificates, or discount labels remain understandable.  |
| Tax or shipping-sensitive order       | Helps separate migrated historical values from target-side module setup.        |
| Download-related order                | Confirms digital product history and customer access expectations are reviewed. |
| Order with comments or status history | Preserves customer-service context after Full Migration.                        |

A good order sample set helps prevent one of the most common launch problems: assuming order totals validate the whole commercial model. Historical totals may migrate as records, while live tax, shipping, payment, coupon, and order-total behavior still requires Zen Cart configuration and testing.

### Prepare Storefront Content, URLs, and SEO Evidence <a href="#prepare-storefront-content-urls-and-seo-evidence" id="prepare-storefront-content-urls-and-seo-evidence"></a>

Zen Cart storefront continuity can involve EZ-Pages, define pages, sideboxes, navigation menus, product/category metadata, image paths, redirects, and URL expectations. These elements influence discoverability, conversion, and customer trust. They should be prepared before migration rather than discovered after the target store is populated.

Collect the pages and URLs that matter most: top product URLs, category URLs, high-traffic content pages, legal or policy pages, homepage-linked content, internal navigation destinations, and pages with strong search visibility. If the source platform uses a different URL structure, decide which URLs must be preserved, redirected, rebuilt, or validated separately.

CMS Pages and Blog Posts should be scoped carefully. A content record may migrate as text, title, metadata, or path information, but target-side display depends on Zen Cart content structures, templates, menus, and layout configuration. Content preparation should define what must be migrated, what must be recreated, and what should be redirected.

A practical content checklist includes:

* priority category URLs and product URLs;
* policy, shipping, returns, and contact pages;
* high-value informational pages;
* metadata and page titles that support search continuity;
* image references and embedded links;
* navigation dependencies that may need target-side setup;
* redirect priorities for discontinued or changed paths.

### Identify Modules, Plugins, Templates, and Customizations <a href="#identify-modules-plugins-templates-and-customizations" id="identify-modules-plugins-templates-and-customizations"></a>

Zen Cart migrations often become complicated when historical business behavior lives outside standard records. Payment modules, shipping modules, tax modules, order-total modules, SEO modules, feed modules, reporting plugins, custom admin fields, modified templates, language overrides, custom files, and custom database tables can all affect the real migration scope.

Before Demo Migration, list every module and customization that affects catalog management, checkout, orders, pricing, URLs, customer data, reporting, fulfillment, or integrations. For each item, decide whether it is target-side configuration, supported migrated data, Add-on scope, or Custom Service scope.

| Dependency type            | Preparation question                                                                                                | Likely handling path                                                                             |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Payment or shipping module | Does the source value need to be readable in historical orders, or must the module be configured for live checkout? | Historical labels may migrate; live behavior requires target setup and testing.                  |
| Order-total module         | Does it create custom discount, fee, tax, reward, or surcharge meaning?                                             | Supported history may migrate; custom logic may require Custom Service review.                   |
| SEO or URL module          | Does it control slugs, redirects, metadata, or canonical behavior?                                                  | Supported fields may migrate; bespoke URL rules may need Custom Service or target configuration. |
| Template override          | Does it control product display, sideboxes, content placement, or checkout presentation?                            | Usually target-side design/configuration, not ordinary migrated data.                            |
| Custom field or table      | Does it store business-critical product, customer, order, or integration data?                                      | Custom Service when unsupported extraction, mapping, or placement is required.                   |

This inventory should be honest. Treating custom behavior as ordinary migration scope creates late-stage surprises and unrealistic launch assumptions.

### Prepare Add-ons, Custom Service, and Entity Points Scope <a href="#prepare-add-ons-custom-service-and-entity-points-scope" id="prepare-add-ons-custom-service-and-entity-points-scope"></a>

Preparation should separate three different questions: what supported data should move, what bounded migration adjustments are needed, and what requires custom handling. Add-ons help with specific supported needs such as filtering, mapping, or data configuration. Custom Service is for unsupported records, custom fields, modified tables, bespoke transformations, Custom Platform handling, or custom migration logic adjustment.

Entity Points planning should be practical rather than abstract. New eligible Products, Customers, Orders, and Blog Posts consume Entity Points when first migrated beyond what the service license already counts. Records already counted through the service license do not consume Entity Points again simply because another action occurs on the same migration path. The preparation task is to estimate scope clearly enough that the migration plan does not change unexpectedly after Demo Migration.

| Scope question                                     | Preparation output                                                                                                       |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Which records are included in the service license? | Baseline Products, Customers, Orders, CMS Pages, Blog Posts, and other selected entities where applicable.               |
| Which records are new eligible records?            | Entity Points estimate for eligible Products, Customers, Orders, and Blog Posts not already counted through the license. |
| Which records need filtering?                      | Data Filter Add-on review.                                                                                               |
| Which fields need supported mapping?               | Advanced Data Mapping review.                                                                                            |
| Which values need supported configuration?         | Advanced Data Configure review.                                                                                          |
| Which data is unsupported or custom?               | Custom Service review before Full Migration.                                                                             |

Clear scope planning protects the launch timeline. It also prevents Add-ons from being treated as vague fixes for unsupported behavior.

### Use Demo Migration as a Preparation Checkpoint <a href="#use-demo-migration-as-a-preparation-checkpoint" id="use-demo-migration-as-a-preparation-checkpoint"></a>

Demo Migration should test the preparation work. A weak Demo Migration only confirms that records appear. A strong Demo Migration asks whether the chosen samples prove that Zen Cart can represent the store’s important business meaning.

Use Demo Migration to review:

* product attributes and option values;
* category placement and linked products;
* image display and downloadable-product handling;
* customers with multiple addresses or account history;
* orders with statuses, comments, discounts, taxes, shipping, payment labels, and selected attributes;
* CMS Pages, Blog Posts, EZ-Pages, or content records where supported;
* high-priority product, category, and content URLs;
* records affected by plugins, custom fields, external IDs, or modified tables.

If Demo Migration reveals a setup gap, fix the target configuration. If it reveals a supported data mapping gap, review Add-ons. If it reveals unsupported records or custom logic needs, review Custom Service. If additional records accumulate after Demo Migration or the scope changes, review the appropriate Additional Migration Options before Full Migration.

### Prepare a Responsibility Matrix Before Demo Migration <a href="#prepare-a-responsibility-matrix-before-demo-migration" id="prepare-a-responsibility-matrix-before-demo-migration"></a>

Zen Cart preparation should finish with a responsibility matrix. The matrix does not need to be complicated, but it should state who owns each type of finding before Demo Migration begins. Without this step, validation feedback can become circular: the migration specialist reviews data, the developer reviews template behavior, the storeowner reviews commercial meaning, and the operations team reviews live checkout setup, but no one knows which issue belongs to which owner.

A practical matrix should divide findings into migration data, target configuration, target implementation, and business approval. Migration data includes records and fields covered by the selected Migration Service scope. Target configuration includes Zen Cart modules, tax zones, shipping rules, payment settings, order-total settings, admin options, and storefront configuration. Target implementation includes plugins, template overrides, custom PHP changes, external integrations, and custom fields. Business approval includes whether products, orders, customers, content, and SEO-sensitive pages remain usable for launch.

| Finding type                                  | Best owner                                 | Why it matters before Demo Migration                            |
| --------------------------------------------- | ------------------------------------------ | --------------------------------------------------------------- |
| Missing supported entity or field             | Migration specialist                       | Confirms whether the selected migration scope is complete.      |
| Attribute or option behavior is unclear       | Catalog owner with migration review        | Prevents product-choice problems from being discovered late.    |
| Checkout, shipping, or payment behavior fails | Target store owner or developer            | Separates live configuration from migrated order history.       |
| Plugin-owned data is required                 | Technical owner with Custom Service review | Prevents unsupported data from being assumed as standard scope. |
| Template hides migrated fields                | Developer or theme owner                   | Avoids misclassifying display issues as data defects.           |
| URL or content continuity is incomplete       | SEO or content owner                       | Protects discoverability and customer-trust pages.              |

The responsibility matrix also improves communication after Demo Migration. When a finding appears, the team can classify it immediately instead of debating whether it is a data problem, target setup problem, or custom requirement. That classification is essential for choosing between standard correction, Data Filter Add-on, Advanced Data Mapping, Advanced Data Configure, Custom Service, target-side implementation, or Additional Migration Options.

Preparation is complete only when the source evidence, target configuration checklist, Demo Migration samples, and responsibility matrix all point to the same migration plan. If any of those items are missing, the next step should be preparation, not Full Migration approval.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Zen Cart pre-migration preparation should make the target store testable before Full Migration. The team needs more than entity totals. It needs environment readiness, catalog and attribute samples, customer and order review cases, content and URL priorities, module and plugin inventory, customization evidence, Add-on requirements, Custom Service signals, and Entity Points planning.

The best preparation separates migrated history from target-side configuration. Products, Customers, Orders, CMS Pages, Blog Posts, and supported records can be migrated, but modules, templates, live checkout behavior, hosting stability, and custom logic must be prepared and validated separately. When that separation is clear, Demo Migration becomes a reliable decision checkpoint instead of a superficial preview.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Zen Cart migration?**

Start with the target Zen Cart environment, admin access, hosting access, and backup plan. Then prepare catalog, customer, order, content, URL, module, plugin, and customization evidence for Demo Migration review.

**Why are product attributes important before migrating to Zen Cart?**

Attributes can carry customer-selectable choices, price changes, download behavior, and order-history meaning. Preparing attribute-heavy samples helps confirm whether product behavior remains understandable in the target store.

**Should payment and shipping modules be migrated as data?**

Historical payment and shipping labels may appear in orders, but live payment and shipping behavior is target-side configuration. The two should be validated separately.

**When should Custom Service be reviewed before Full Migration?**

Review Custom Service when the source store includes unsupported custom fields, custom tables, plugin-owned data, bespoke transformations, external identifiers, or custom migration logic adjustment requirements.

**How should Demo Migration affect preparation?**

Demo Migration should confirm whether selected high-value samples preserve business meaning. If the result exposes setup, mapping, customization, or scope gaps, resolve those before Full Migration.
