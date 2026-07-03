# Pre-migration Preparation Checklist for Square

Square preparation should collect evidence that proves the migrated data will work inside Square’s selling environment. A useful checklist is not a long inventory of everything the merchant might export. It is a readiness plan that connects source data to Square’s item library, locations, inventory, orders, payments, customer profiles, Square Online presentation, integrations, and validation responsibility.

Preparation also needs to separate migrated records from target-side setup. Supported data migration can bring records into Square, but payment processing, POS hardware, staff permissions, fulfillment settings, live taxes, pickup and delivery workflows, shipping rules, domains, app configuration, and many Square Online presentation decisions still need to be prepared or confirmed directly in Square. When those responsibilities are unclear, Demo Migration may look successful while launch readiness remains weak.

### Define How Square Will Operate After Migration <a href="#define-how-square-will-operate-after-migration" id="define-how-square-will-operate-after-migration"></a>

The first preparation decision is how Square will be used after launch. Some merchants migrate to Square mainly for POS-connected catalog and customer/order history. Others plan to launch Square Online, unify in-person and online selling, simplify payment workflows, or replace a storefront-first Source Platform with a more operational environment. These goals change the evidence that should be prepared.

A merchant using Square only for catalog and historical records may need product, customer, and order examples. A merchant launching POS and Square Online together also needs location structure, inventory expectations, online product visibility, URLs, redirects, domain timing, pickup or delivery assumptions, and staff validation assignments. A merchant moving from a heavily customized storefront may need a custom-data inventory before any migration approach can be trusted.

| Square operating area  | Preparation question                                                            | Why it matters before migration                                                                                                         |
| ---------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| POS and staff workflow | Will staff sell through Square immediately after launch?                        | Product names, variations, modifiers, taxes, and inventory must make sense to the people using Square daily.                            |
| Square Online          | Is online selling part of launch scope?                                         | Product visibility, pages, URLs, redirects, media, domains, SEO fields, and fulfillment settings need separate preparation.             |
| Locations              | Which locations matter for sales, inventory, fulfillment, reporting, or pickup? | Inventory and availability can lose meaning if source quantities are flattened or assigned incorrectly.                                 |
| Historical orders      | What order history is needed for service, reporting, and customer lookup?       | Older order data may be useful even when it does not recreate live payment behavior.                                                    |
| Customer profiles      | Which customer records matter after launch?                                     | Duplicate contacts, guest buyers, missing emails, loyalty references, or B2B-style records may need review.                             |
| Integrations           | Which outside systems own important commerce data?                              | Accounting, CRM, loyalty, marketplace, restaurant, delivery, subscription, or inventory systems may create unsupported or custom scope. |

This operating definition keeps the checklist practical. The merchant is not preparing for Square in the abstract; the merchant is preparing for a specific Square launch scenario.

### Prepare Catalog Evidence for the Item Library <a href="#prepare-catalog-evidence-for-the-item-library" id="prepare-catalog-evidence-for-the-item-library"></a>

Square catalog preparation should begin with representative product examples, not only record totals. Product counts help estimate scope, but they do not show whether the source catalog will behave properly as Square items, item variations, categories, modifiers, images, taxes, discounts, and related catalog records.

Prepare examples that expose the actual catalog structure: simple products, variation-heavy products, products with multiple images, products with sale-time add-ons, discounted products, tax-sensitive products, products tied to important categories, and products that drive meaningful revenue. These examples help reveal whether source choices should become Square variations, modifiers, item options, target-side setup, Add-ons scope, Custom Service scope, or exclusions.

| Product evidence to prepare                                      | Square readiness value                                                     |
| ---------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Simple product with SKU, price, image, category, and tax status  | Confirms the basic item-library mapping path.                              |
| Product with size, color, unit, package, or flavor choices       | Tests whether choices should become item variations or item options.       |
| Product with sale-time add-ons or preparation choices            | Helps decide whether the source choice is closer to a Square modifier.     |
| Bundle, kit, package, subscription, or configurable product      | Exposes logic that may require target-side setup or Custom Service review. |
| Product with important images and SEO value                      | Connects catalog migration with Square Online and launch presentation.     |
| Product controlled by an app, plugin, module, or external system | Identifies data that may not belong to standard Square records.            |

The goal is not to make every source structure fit Square exactly. The goal is to decide what should migrate, what should be configured in Square, what should be handled with Add-ons, and what should be reviewed for Custom Service.

### Prepare Inventory and Location Inputs <a href="#prepare-inventory-and-location-inputs" id="prepare-inventory-and-location-inputs"></a>

Inventory preparation is one of the most important Square readiness tasks because Square inventory meaning depends on sellable item variations and locations. A source store may store inventory as one global quantity, warehouse-specific stock, channel availability, marketplace stock, backorder status, preorder state, or custom app data. Square preparation should clarify which of those values should matter after migration.

For a single-location merchant, the task may be straightforward: confirm current stock for key item variations and validate that migrated quantities match the expected target result. For a multi-location merchant, preparation should be more careful. A source warehouse may not equal a Square location. A fulfillment center may not be the same as a storefront. A product may be available online but not in-store, or sellable in one location but not another.

Prepare a location map before migration if location-level inventory matters. The map should explain which source stock values belong to which Square locations, which values should be excluded, and which products should not carry inventory expectations at launch. If the source platform cannot provide reliable location-level evidence, the migration plan should not pretend that location-level inventory can be validated with confidence.

Good inventory preparation includes:

* item variations with clear SKUs or stable identifiers;
* current quantities for representative stock-managed products;
* examples of out-of-stock, low-stock, and non-stock-managed items;
* location or warehouse fields if they exist;
* products sold online only, in-store only, or through multiple channels;
* bundle, kit, or component-stock examples;
* notes on preorder, backorder, negative stock, or availability rules.

Inventory should be prepared as operating evidence. A record-count comparison is not enough if staff cannot trust what Square shows for sellable items after launch.

### Prepare Customer and Order Examples <a href="#prepare-customer-and-order-examples" id="prepare-customer-and-order-examples"></a>

Square customer and order preparation should focus on usefulness after migration. Customer records are valuable when staff can look up buyers, connect them to order history, support repeat sales, and understand contact context. Order records are valuable when they remain readable for service, accounting reference, reporting, refund review, or operational history.

Prepare customer examples that show the real condition of the source data. Include customers with complete profiles, guest buyers, duplicate emails, missing phone numbers, multiple addresses, multiple orders, loyalty references, account notes, customer-group-like behavior, or custom fields. These examples reveal whether Square customer profiles can support the expected business use or whether some source-account behavior should be treated as out-of-scope, target-side setup, or Custom Service review.

Order examples should include more than clean completed orders. Prepare refunded orders, partially fulfilled orders, orders with discounts, taxes, shipping, service charges, tips, payment references, external identifiers, multiple line items, cancelled statuses, and recent orders. Square order history should be tested for readability and practical reference value. It should not be confused with configuring live Square payment processing or recreating every source checkout rule.

| Record type | Examples to prepare                                                                                       | Planning value                                            |
| ----------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Customers   | Guest buyers, repeat buyers, duplicates, missing contact fields, customers with custom notes or tags.     | Confirms whether profiles will be useful after migration. |
| Orders      | Recent orders, refunded orders, discounted orders, tax-sensitive orders, orders with external references. | Confirms historical readability and support value.        |
| Payments    | Payment labels, transaction references, refunds, service charges, tips where available.                   | Separates historical context from live payment setup.     |
| Fulfillment | Pickup, shipping, delivery, partial fulfillment, cancelled or returned orders.                            | Exposes whether order status meaning needs review.        |

This preparation helps avoid a common Square mistake: approving order counts while missing whether the order history is understandable to staff.

### Prepare Square Online, URL, and SEO Inputs <a href="#prepare-square-online-url-and-seo-inputs" id="prepare-square-online-url-and-seo-inputs"></a>

Square Online preparation should be handled separately from catalog preparation. A successful catalog migration can still leave the online store unfinished if product visibility, pages, navigation, URLs, redirects, domains, SEO fields, images, and fulfillment settings are not prepared.

Start by identifying whether Square Online is part of the launch. If it is not, preparation can focus on catalog and operational data. If it is, prepare high-value storefront evidence: product URLs, category or collection URLs, important CMS Pages, Blog Posts, media assets, metadata, high-traffic landing pages, navigation notes, domain plans, redirect priorities, and pages that should be recreated rather than migrated.

| Square Online input              | Why it matters                                                                                  |
| -------------------------------- | ----------------------------------------------------------------------------------------------- |
| Product URLs                     | Helps validate redirects, indexed pages, and customer landing paths.                            |
| Category or collection URLs      | Clarifies whether source grouping was catalog structure, navigation, SEO content, or all three. |
| CMS Pages and Blog Posts         | Identifies content that should migrate, be recreated, redirected, or retired.                   |
| Metadata and media               | Supports presentation and search continuity where supported.                                    |
| Navigation and menu notes        | Prevents category migration from being mistaken for storefront structure.                       |
| Domain and launch timing         | Keeps technical cutover separate from data migration approval.                                  |
| Fulfillment display expectations | Connects online presentation with pickup, delivery, shipping, and availability setup.           |

Square Online readiness should be validated as a launch task, not assumed from product migration. The merchant should know which online elements are migrated, which must be configured in Square, and which require separate design, SEO, or operational decisions.

### Identify Integrations, Custom Data, and Unsupported Expectations <a href="#identify-integrations-custom-data-and-unsupported-expectations" id="identify-integrations-custom-data-and-unsupported-expectations"></a>

Square migrations often become complicated when the source store depends on apps, plugins, modules, custom fields, external systems, or private workflows that do not appear in standard commerce exports. Preparation should identify those dependencies before Demo Migration, not after Full Migration.

List every system that influences products, customers, orders, inventory, loyalty, reviews, subscriptions, appointments, restaurant workflows, delivery, marketplace listings, accounting, CRM, ERP, reporting, tax calculation, shipping, or marketing automation. For each system, identify the data owner, the business purpose, and whether the data is expected in Square after migration.

The preparation should then classify the requirement:

| Requirement type                                                                              | Better planning path                                                                       |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Supported data that needs filtering                                                           | Consider a Data Filter Add-on when the filter is clear and within supported behavior.      |
| Supported data that needs more careful field alignment                                        | Consider Advanced Data Mapping when the mapping target is supported.                       |
| Supported data that needs configuration adjustment                                            | Consider Advanced Data Configure when the configuration remains within supported behavior. |
| Unsupported fields, app records, external identifiers, or bespoke transformation              | Review for Custom Service.                                                                 |
| Target-side settings, payment setup, POS hardware, Square Online layout, or app configuration | Prepare as Square setup, not migrated data.                                                |

This classification keeps Add-ons and Custom Service separate. Add-ons help with supported filtering, mapping, and configuration needs. Custom Service handles custom or unsupported requirements, bespoke transformations, Custom Platform handling, external-system complexity, or custom migration logic adjustment.

### Prepare Access, Backups, and Migration Inputs <a href="#prepare-access-backups-and-migration-inputs" id="prepare-access-backups-and-migration-inputs"></a>

Access preparation should be practical and secure. The merchant should know which source admin access, Square access, exports, media files, URLs, approved credentials, or connection inputs are needed for the selected service path. Backups and export copies should be retained where available so the team can compare what existed before migration with what appears in Square.

Prepare access for the areas that affect the Square scope:

* Source Platform admin or export access;
* Square account access needed for migration and target review;
* product, customer, order, category, image, content, and URL exports where available;
* media files or image libraries when images are not reliably available through normal export;
* integration exports or reports when app-owned records matter;
* domain, redirect, SEO, or content records when Square Online is part of launch;
* sample screenshots or reports that show how important source records should be interpreted.

Access preparation should also identify what the merchant must configure directly in Square. Live payments, staff permissions, device setup, POS hardware, receipt settings, tax settings, shipping, pickup, delivery, loyalty, marketing, Square Online design, domains, and connected apps may affect launch even when migrated records are correct.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

Demo Migration should be treated as a structured evidence gate for Square. The sample set should be small enough to review carefully and diverse enough to reveal whether the chosen approach preserves Square-specific meaning.

A strong Square sample set includes:

| Sample                                   | What it should reveal                                                             |
| ---------------------------------------- | --------------------------------------------------------------------------------- |
| Simple item                              | Baseline item-library mapping, pricing, SKU, category, and image behavior.        |
| Variation-heavy item                     | Whether options become usable sellable variations.                                |
| Modifier-like product                    | Whether sale-time choices are handled correctly or need another path.             |
| Location-sensitive inventory item        | Whether stock meaning survives Square location assumptions.                       |
| Customer with multiple orders            | Whether profile and order associations remain useful.                             |
| Refunded or discounted order             | Whether historical order detail is readable.                                      |
| Square Online URL or content example     | Whether online launch assumptions need separate preparation.                      |
| Custom field or integration-owned record | Whether the requirement belongs to Add-ons, Custom Service, or target-side setup. |

Demo Migration should answer whether the approach is light enough, too light, or mis-scoped. If important samples fail because of unsupported data, custom fields, app-managed records, or Square Online assumptions, preparation should be updated before Full Migration.

### Plan the Migration Window and Later Migration Actions <a href="#plan-the-migration-window-and-later-migration-actions" id="plan-the-migration-window-and-later-migration-actions"></a>

Square preparation should account for what happens between the first migration run and launch. Many merchants keep the source store open while products, orders, customers, and inventory continue changing. If new data is expected, the migration plan should define whether the merchant may need to continue migration activity later, continue with a new configuration, or perform a new migration into a refreshed target environment.

This planning should stay practical. The merchant does not need backend mechanics. The merchant needs to know what business outcome is expected:

| Later migration expectation                                      | Preparation decision                                                                                                       |
| ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| New source records appear after the first migration              | Plan how those records will be reviewed and validated in Square.                                                           |
| Migration settings need adjustment after Demo Migration          | Decide whether continuing with a new configuration is the right action.                                                    |
| The earlier target result should be replaced                     | Plan for a new migration and define what should no longer remain from the previous result.                                 |
| The same migration path continues with already recorded entities | Remember that already recorded entities do not consume Entity Points again simply because another migration action occurs. |

These choices affect timing, responsibility, and validation. They should be understood before launch, especially when Square Online, inventory, orders, or customer history will be visible to staff and customers immediately after cutover.

### Final Readiness Check Before Full Migration <a href="#final-readiness-check-before-full-migration" id="final-readiness-check-before-full-migration"></a>

Before Full Migration, the Square preparation package should answer five questions.

First, does the team know how Square will operate after launch? POS-only, Square Online, multi-location inventory, payment-connected order history, or integrated workflows each require different evidence.

Second, are the catalog examples strong enough to test Square item-library meaning? Simple product counts do not reveal variation, modifier, image, category, discount, tax, and inventory behavior.

Third, are customer and order examples diverse enough to test real business use? A clean completed order is not enough if refunds, discounts, external references, customer duplicates, or guest buyers matter.

Fourth, has Square Online been prepared separately from catalog transfer? Pages, URLs, redirects, domains, navigation, media, SEO fields, and fulfillment presentation should not be assumed from product migration.

Fifth, are Add-ons, Custom Service, Entity Points, and later migration actions understood only where relevant? Service-path decisions should be grounded in actual examples rather than vague concerns.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Square preparation is strongest when it gathers the evidence needed to prove operating readiness. The merchant should prepare catalog samples, inventory and location inputs, customer and order examples, Square Online content and URL plans, integration notes, access, backups, Demo Migration samples, service-path assumptions, and launch-window expectations. The checklist should reduce uncertainty before Full Migration by showing what should migrate, what should be configured in Square, what needs Add-ons, what requires Custom Service review, and what must be validated before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Square migration?**

Start by defining how Square will be used after launch. POS use, Square Online, locations, inventory, historical orders, customer profiles, payment context, and integrations determine which evidence matters most.

**Why are product samples more useful than product counts?**

Product counts show volume, but samples reveal Square meaning. A representative sample can show whether source choices should become item variations, modifiers, categories, Square-side setup, Add-ons scope, or Custom Service scope.

**Should Square Online preparation be separate from catalog preparation?**

Yes. Catalog migration can provide items, images, categories, and product data, but Square Online readiness also depends on pages, visibility, URLs, redirects, domains, navigation, SEO fields, and fulfillment presentation.

**When should integrations or custom data be reviewed?**

They should be reviewed before Demo Migration. App-owned data, external identifiers, loyalty records, marketplace data, subscriptions, custom fields, or bespoke reporting logic can affect whether Standard Service, Add-ons, or Custom Service is appropriate.

**How should later migration activity be planned before launch?**

If the source store keeps changing after an initial migration run, define whether the goal is to continue from the previous setup, continue with a new configuration, or perform a new migration into a refreshed target environment. The decision should be tied to validation responsibility and launch timing.
