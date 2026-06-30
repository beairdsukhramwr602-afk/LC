# Adobe Commerce Pre-Migration Preparation Checklist

Adobe Commerce preparation should begin with the target operating model, not with a raw export list. The platform can support enterprise B2B and B2C commerce, company accounts, shared catalogs, buyer-specific pricing, multiple websites and store views, governed catalog architecture, staged content, inventory ownership, ERP/PIM/CRM integrations, and complex launch sequencing. Those capabilities are valuable only when the migration plan knows which records must become usable, which rules must be configured in Adobe Commerce, and which requirements need Add-ons or Custom Service review.

A useful checklist therefore collects evidence. It should show how the business sells, how buyers are structured, how catalogs and prices are governed, how storefront scope works, which content and URLs matter, which integrations own data, which records are standard migration scope, and which outcomes must be proven during Demo Migration and final validation.

### Preparation Starts With the Adobe Commerce Operating Model <a href="#preparation-starts-with-the-adobe-commerce-operating-model" id="preparation-starts-with-the-adobe-commerce-operating-model"></a>

Adobe Commerce readiness depends on the business model the target store must support after launch. A retail-only store with a large catalog has different preparation needs from a hybrid B2B/B2C business, a distributor portal, a multi-brand enterprise store, or a regional storefront network. The same record types may exist in each project, but their business meaning changes.

The preparation brief should answer these questions before mapping decisions begin:

| Operating decision   | Evidence to prepare                                                                                                                            | Why it matters                                                                                                          |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Buyer model          | B2C customers, B2B companies, company administrators, purchasing users, approvers, sales representatives, and buyer segments.                  | Adobe Commerce may need to preserve relationships, permissions, and account context rather than only customer profiles. |
| Storefront structure | Websites, stores, store views, regions, languages, brands, currencies, domains, and content ownership.                                         | Scope affects catalog visibility, localized content, configuration, URL behavior, and validation responsibility.        |
| Catalog model        | Product types, configurable relationships, bundles, grouped products, attributes, attribute sets, categories, media, and merchandising fields. | Catalog records must remain maintainable and commercially usable in the target environment.                             |
| Pricing model        | Customer groups, tier prices, shared catalog pricing, negotiated pricing, promotions, contract prices, and external price ownership.           | Price visibility can be buyer-specific and may require configuration or custom review.                                  |
| Integration model    | ERP, PIM, CRM, WMS, tax, payment, shipping, analytics, procurement, marketplace, and reporting dependencies.                                   | External identifiers and system-owned data often determine whether standard migration is enough.                        |

This brief should be short but specific. It does not need to document every configuration detail. It needs to state what Adobe Commerce must make operational after migration.

### Prepare B2B Company and Buyer Evidence <a href="#prepare-b2b-company-and-buyer-evidence" id="prepare-b2b-company-and-buyer-evidence"></a>

For Adobe Commerce B2B, company relationships need separate preparation from individual customer data. Company accounts can involve administrators, users, roles, approval behavior, purchase orders, company credit, sales representatives, customer groups, shared catalogs, allowed payment methods, allowed shipping methods, and account status. Treating these as ordinary customer fields weakens the migration scope.

Prepare representative company-account evidence before Demo Migration:

| Company preparation item                    | What to gather                                                                                                              |
| ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Company identity                            | Legal name, business email, account status, VAT/TAX ID, reseller ID, billing/legal address, and source account identifiers. |
| Company administrator                       | The user who should administer the company account and whether that user also exists as an individual customer.             |
| Company users                               | Buyers, branch users, purchasing teams, approvers, and employees connected to the company.                                  |
| Roles and permissions                       | Which users can buy, approve, manage users, request quotes, use purchase orders, or administer the account.                 |
| Credit and purchasing rules                 | Credit limits, purchase order expectations, payment method restrictions, shipping method restrictions, and quote behavior.  |
| Customer group or shared catalog assignment | How the company should receive catalog visibility, price lists, or buyer-specific assortments.                              |
| External identifiers                        | ERP account IDs, dealer IDs, procurement IDs, CRM IDs, sales representative IDs, or reporting keys.                         |

If the Source Platform does not have native company accounts, B2B meaning may be hidden in customer groups, wholesale tags, custom fields, third-party apps, ERP references, spreadsheets, or account notes. Those inputs should be classified before migration. Supported fields may fit mapping or configuration; unsupported structures, custom B2B logic, or outside-system identifiers may require Custom Service review.

### Prepare Shared Catalog, Pricing, and Visibility Inputs <a href="#prepare-shared-catalog-pricing-and-visibility-inputs" id="prepare-shared-catalog-pricing-and-visibility-inputs"></a>

Shared catalogs and buyer-specific pricing are central Adobe Commerce preparation areas when B2B is in scope. Product records may migrate accurately while company-specific visibility, contract pricing, restricted assortments, tier pricing, and customer-group behavior remain incomplete.

Prepare pricing and visibility inputs in a way that reviewers can test:

| Pricing or visibility input | Preparation question                                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Shared catalog list         | Which shared catalogs are required for launch?                                                                            |
| Company assignment          | Which companies, customer groups, or buyer segments belong to each catalog?                                               |
| Product assignment          | Which products should appear or remain hidden for each group?                                                             |
| Price source                | Which prices are base prices, tier prices, negotiated prices, shared catalog prices, or externally owned contract prices? |
| Exceptions                  | Which buyers have special access, temporary visibility, region-specific catalogs, or restricted purchasing?               |
| Launch priority             | Which companies and catalogs must be validated before go-live?                                                            |

When pricing is controlled outside Adobe Commerce, preparation should identify the authoritative system. ERP, PIM, procurement platforms, spreadsheets, sales-team files, or custom modules may own price logic that cannot be treated as standard product price data. The migration plan should define whether those values are migrated, configured, excluded, or reviewed as custom scope.

### Prepare Product Architecture and Catalog Governance <a href="#prepare-product-architecture-and-catalog-governance" id="prepare-product-architecture-and-catalog-governance"></a>

Adobe Commerce catalog preparation should preserve product meaning, not simply product count. The source catalog should be sampled by product type, attribute structure, visibility, category assignment, inventory behavior, images, URLs, and business value.

A strong sample set includes:

| Product sample                  | Why it matters                                                                                                           |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Simple product                  | Confirms baseline SKU, price, media, category, attribute, and visibility behavior.                                       |
| Configurable product            | Tests parent/child relationship, selectable options, associated simple products, child SKUs, and inventory expectations. |
| Bundle or grouped product       | Exposes source structures that may not map cleanly without preparation.                                                  |
| Virtual or downloadable product | Tests non-physical product behavior, delivery expectations, and customer/order context.                                  |
| High-value B2B product          | Confirms buyer-specific catalog visibility and price expectations.                                                       |
| Product with custom attributes  | Shows whether source fields are supported, need mapping, need configuration, or require Custom Service review.           |
| Product with localized values   | Tests store-view scope, translated content, images, and URL paths.                                                       |

Attribute and attribute-set preparation is especially important. Source platforms may treat product details as options, metafields, custom fields, specifications, tags, or app data. Adobe Commerce may require a clearer distinction between sellable options, searchable attributes, filterable attributes, merchandising fields, and custom data that should not be migrated without review.

### Prepare Storefront Scope, Content, and Campaign Timing <a href="#prepare-storefront-scope-content-and-campaign-timing" id="prepare-storefront-scope-content-and-campaign-timing"></a>

Adobe Commerce projects often involve multiple websites, stores, and store views. Scope affects where catalog values appear, which language or region receives content, how URLs are structured, which domains matter, and which stakeholders must approve launch.

Prepare a scope map before export:

| Scope input      | What to document                                                                                      |
| ---------------- | ----------------------------------------------------------------------------------------------------- |
| Websites         | Brands, regions, legal entities, currencies, or sales channels that require website-level separation. |
| Stores           | Catalog groupings, storefront experiences, or channel-specific presentation.                          |
| Store views      | Languages, localized content, regional copy, translated attributes, and customer-facing variants.     |
| Domains and URLs | Old paths, new paths, localized paths, URL rewrites, redirects, and high-value SEO pages.             |
| Content assets   | CMS Pages, CMS blocks, Blog Posts, landing pages, campaign pages, banners, forms, and media.          |
| Content timing   | Scheduled campaigns, staged updates, promotional launches, seasonal pages, and embargoed content.     |

Content Staging and campaign behavior should be handled carefully. Source content may exist as pages, blocks, app-managed landing pages, page-builder layouts, scripts, or scheduled promotions. Some content can migrate as records, some should be rebuilt in Adobe Commerce, and some may require design or implementation work outside standard migration scope.

### Prepare Inventory, Fulfillment, and Order Context <a href="#prepare-inventory-fulfillment-and-order-context" id="prepare-inventory-fulfillment-and-order-context"></a>

Inventory and fulfillment preparation should define ownership. Adobe Commerce may be used with internal stock management, multi-source inventory, warehouse systems, ERP, WMS, dropshipping logic, or external fulfillment providers. A quantity export does not always explain salable quantity, reservations, source allocation, backorders, or channel availability.

Prepare inventory examples for:

* simple products with ordinary stock;
* configurable children with separate quantities;
* products available in some websites or regions but not others;
* products with backorder or preorder expectations;
* products controlled by ERP, WMS, warehouse, marketplace, or fulfillment integrations;
* bundle or grouped products with component-related availability;
* items where stock should be excluded and rebuilt after migration.

Order history also needs preparation beyond order count. Include orders with refunds, invoices, shipments, taxes, discounts, purchase order references, quotes, company-account context, customer-group context, store-view scope, payment details, shipping details, external IDs, and unusual statuses. Historical orders should be readable and useful after migration, but they should not be confused with live payment, shipping, tax, or fulfillment configuration.

### Identify Integration, Extension, and Custom Data Boundaries <a href="#identify-integration-extension-and-custom-data-boundaries" id="identify-integration-extension-and-custom-data-boundaries"></a>

Adobe Commerce migration risk often appears in data owned by external systems or custom extensions. Preparation should identify where business meaning lives before deciding whether the requirement belongs to Standard Service, Managed Service, Add-ons, Custom Service, target-side setup, or exclusion.

| Dependency type    | Preparation requirement                                                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| ERP or accounting  | Account IDs, product IDs, tax codes, invoices, credit terms, price lists, order references, and reconciliation keys.      |
| PIM                | Product attributes, media ownership, localized descriptions, category assignments, and enrichment workflows.              |
| CRM or sales tools | Company owner, sales representative, account status, buyer notes, segmentation, and customer lifecycle data.              |
| WMS or fulfillment | Warehouse IDs, source codes, salable quantity logic, stock reservations, shipping restrictions, and fulfillment statuses. |
| B2B procurement    | Punchout, buyer approval, purchase order, quote, or procurement-system identifiers.                                       |
| Custom modules     | Custom fields, workflow rules, business logic, storefront behavior, or backend records not present in standard exports.   |

The practical rule is simple: Add-ons help with supported filtering, mapping, or configuration. Custom Service handles unsupported extension data, bespoke transformation, custom fields, outside-system identifiers, Custom Platform handling, or custom migration logic beyond supported behavior.

### Prepare Demo Migration Samples and Acceptance Criteria <a href="#prepare-demo-migration-samples-and-acceptance-criteria" id="prepare-demo-migration-samples-and-acceptance-criteria"></a>

Demo Migration should use samples that reveal Adobe Commerce complexity early. Random records are not enough. The sample set should test the operating model, product architecture, B2B relationships, pricing visibility, scope, content, inventory, URLs, orders, and custom data.

| Demo sample                        | What it should prove                                                                             |
| ---------------------------------- | ------------------------------------------------------------------------------------------------ |
| Configurable product with children | Parent/child SKU structure, options, images, price, category, and stock behavior.                |
| Company account                    | Administrator, users, group assignment, shared catalog access, and purchasing context.           |
| Shared catalog product             | Product visibility and buyer-specific pricing logic.                                             |
| Multi-store or localized product   | Store-view values, translated content, image behavior, and URL scope.                            |
| Complex order                      | Taxes, discounts, invoices, refunds, shipping, payment, PO or quote reference, and external IDs. |
| CMS or campaign page               | Content ownership, URL behavior, staging/timing expectations, and launch review.                 |
| Integration-owned record           | Whether the value is supported, mapped, configured, custom, excluded, or rebuilt.                |

Acceptance criteria should state what counts as pass, correction, accepted limitation, custom review, or target-side setup. Without that classification, Demo Migration can become a visual check rather than a real migration decision gate.

### Prepare Launch Timing and Later Migration Activity <a href="#prepare-launch-timing-and-later-migration-activity" id="prepare-launch-timing-and-later-migration-activity"></a>

Adobe Commerce migrations often happen while the Source Platform remains live. New products, customers, orders, reviews, CMS Pages, Blog Posts, B2B account changes, pricing updates, and configuration corrections may appear between the first migration run and launch.

Preparation should define whether the business expects to continue migration activity with the last used configuration, continue with a new configuration, or perform a new migration for the same migration path. The choice affects target cleanup, validation responsibility, duplicate control, Entity Points capacity, and launch sequencing.

New Product, Customer, Order, and Blog Posts records may consume Entity Points when they are migrated for the first time. Records already counted through the service license should not consume Entity Points again simply because another migration action occurs on the same migration path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce preparation should create a usable evidence package before migration begins. The merchant should define the operating model, B2B company relationships, shared catalog and pricing requirements, catalog architecture, storefront scope, content and campaign timing, inventory ownership, integration boundaries, Demo Migration samples, acceptance criteria, and launch-window needs.

The strongest preparation separates standard migrated records from Adobe Commerce configuration, Add-ons, Custom Service review, target-side setup, and later migration activity. That clarity protects the migration plan from late-stage uncertainty and gives reviewers a practical basis for approving Demo Migration and Full Migration results.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for an Adobe Commerce migration?**

Start with the target operating model. Decide whether the store must support B2C, B2B, hybrid selling, multiple websites, multiple store views, shared catalogs, buyer-specific pricing, staged content, or enterprise integrations. That decision controls which evidence matters most.

**Why does Adobe Commerce preparation need more than a product export?**

Adobe Commerce product usability depends on product types, attributes, attribute sets, categories, store scope, inventory ownership, customer-group context, shared catalogs, pricing rules, media, URLs, and integrations. A product export does not explain all of those relationships.

**How should B2B data be prepared?**

Prepare company accounts, company administrators, users, roles, permissions, shared catalog assignments, customer groups, quote or purchase order expectations, credit settings, allowed payment and shipping methods, and external account identifiers where relevant.

**When should Custom Service be reviewed before migration?**

Custom Service should be reviewed when the expected outcome depends on unsupported extension data, custom fields, external system identifiers, bespoke transformations, Custom Platform handling, or custom migration logic beyond supported behavior.

**Should Demo Migration samples be random?**

No. Demo Migration should test the records most likely to expose Adobe Commerce complexity: configurable products, B2B companies, shared catalog products, localized store-view values, complex orders, campaign content, URL paths, and integration-owned data.
