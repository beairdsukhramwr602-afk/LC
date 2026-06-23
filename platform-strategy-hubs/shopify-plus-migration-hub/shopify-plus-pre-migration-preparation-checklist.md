# Shopify Plus Pre-Migration Preparation Checklist

A Shopify Plus migration becomes safer when preparation defines the future operating model before migration execution begins. The work is not limited to collecting product, customer, order, page, or redirect exports. It also requires a clear view of companies, company locations, buyer contacts, catalog assignments, pricing rules, store governance, markets, custom data, integrations, and the samples that should be tested before the full migration path is trusted.

Shopify Plus is often selected because the business needs enterprise Shopify-family capability: B2B selling, controlled product and pricing access, organization-level governance, multiple stores or markets, custom data, deeper integrations, and stronger operational control. Those strengths only help when the migration team prepares around target behavior. A record can transfer correctly and still fail the business if the wrong buyer sees the wrong catalog, a company location loses payment terms, an external ID is missing, or a high-value URL is not preserved.

### Why Shopify Plus Preparation Starts Before Data Transfer <a href="#why-shopify-plus-preparation-starts-before-data-transfer" id="why-shopify-plus-preparation-starts-before-data-transfer"></a>

Shopify Plus preparation should begin by defining what the Target Platform must prove, not by gathering every possible export. For enterprise and B2B migrations, the most important questions are structural:

* Which business customers should become companies?
* Which branches, departments, buying units, or addresses should become company locations?
* Which contacts should be attached to each company or location, and what permissions should they have?
* Which catalogs, prices, product visibility rules, payment terms, tax settings, and checkout settings belong to each buyer context?
* Which stores, markets, domains, languages, currencies, and content areas own the future customer experience?
* Which apps, metafields, metaobjects, integrations, or external IDs must remain usable after migration?
* Which records and scenarios should be used in Demo Migration because they expose the most important Shopify Plus assumptions?

This preparation prevents a common enterprise migration problem: source data is available, but the target operating model is not settled. Shopify Plus can support a more sophisticated structure than a standard storefront, but the migration cannot infer every commercial decision from old fields, customer groups, tags, custom tables, or app behavior.

### Prepare Company and Company-Location Structure <a href="#prepare-company-and-company-location-structure" id="prepare-company-and-company-location-structure"></a>

B2B preparation should start with the company model. Shopify B2B uses companies and company locations to represent business customers, and those structures can affect pricing, products, store content, payments, delivery options, tax context, contacts, and checkout behavior. Preparation should identify which source-side customer records, accounts, branches, billing entities, shipping entities, departments, or ERP accounts should become Shopify Plus companies or company locations.

A useful preparation worksheet should capture:

| Preparation item                    | Why it matters                                                                                             |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Company name and external ID        | Supports account recognition, ERP/CRM continuity, reporting, and support lookup.                           |
| Company locations                   | Preserves branch, department, buyer group, address, tax, pricing, payment, and fulfillment meaning.        |
| Main contacts and buyer contacts    | Determines who can access the company or location after migration.                                         |
| Permissions                         | Controls whether contacts can only order or also administer location activity.                             |
| Payment terms and checkout settings | Affects whether B2B orders are submitted automatically, reviewed as drafts, or handled under agreed terms. |
| Tax IDs and exemptions              | Preserves location-level tax behavior where relevant.                                                      |
| Catalog assignments                 | Connects each company or location to the correct products and pricing.                                     |

The goal is not to force every Source Platform field into Shopify Plus. The goal is to decide what each source relationship means in the future operating model. If the Source Platform used customer groups, price lists, branch accounts, sales-rep assignments, ERP IDs, or custom fields to represent B2B structure, those details should be interpreted before migration samples are selected.

### Prepare Catalog, Pricing, and Product Visibility Evidence <a href="#prepare-catalog-pricing-and-product-visibility-evidence" id="prepare-catalog-pricing-and-product-visibility-evidence"></a>

Catalog preparation is central to Shopify Plus readiness. B2B catalogs determine the products and pricing B2B customers can access, and Shopify Plus supports direct catalog assignment to companies and company locations. That makes catalog planning more than merchandising. It is part of buyer eligibility, product visibility, pricing governance, quantity logic, and commercial trust.

Before migration, the business should prepare evidence for:

* company-specific or location-specific product visibility;
* negotiated pricing, wholesale price lists, regional price differences, or customer-group pricing;
* products that are hidden from some buyers but visible to others;
* quantity rules, volume pricing, or minimum-purchase expectations;
* products shared by B2B and direct-to-consumer customers with different prices or availability;
* priority catalogs that must be tested during Demo Migration;
* products that should be excluded, retired, or reorganized instead of copied literally.

Catalog evidence should be practical. A list of catalogs is not enough. The migration team needs representative companies, company locations, buyer contacts, products, prices, and checkout scenarios. If the source pricing logic depends on external systems, custom rules, or manual overrides, the preparation stage should decide whether the logic belongs in Shopify Plus catalogs, supported mapping, an Add-on, an integration rebuild, or Custom Service.

### Prepare Buyer Access and Customer Account Expectations <a href="#prepare-buyer-access-and-customer-account-expectations" id="prepare-buyer-access-and-customer-account-expectations"></a>

Customer preparation for Shopify Plus should separate retail customer continuity from B2B buyer access. A direct-to-consumer customer record and a B2B contact can look similar as customer data, but they do not carry the same operational meaning. A B2B contact may need company-location context, permissions, payment terms, assigned catalogs, tax settings, draft-order review behavior, and access to order history for a buying unit.

Preparation should answer:

* Which buyers need access at launch?
* Which customers should remain ordinary direct-to-consumer customers?
* Which contacts belong to more than one company or company location?
* Which contacts should have ordering-only permission and which should have location-admin responsibility?
* Which account-access changes require customer communication before launch?
* Which order history, billing context, or support context must remain understandable after migration?

This is especially important when the Source Platform uses shared logins, sales-agent ordering, manual approvals, customer-group permissions, or custom account portals. Those behaviors should be classified as supported target setup, app/integration work, or Custom Service scope before migration execution creates false confidence.

### Prepare Store, Market, and Governance Decisions <a href="#prepare-store-market-and-governance-decisions" id="prepare-store-market-and-governance-decisions"></a>

Shopify Plus can support broader operating models, but preparation should define how the business intends to use them. A merchant might operate one blended B2B and direct-to-consumer store, a dedicated B2B store, multiple regional stores, brand-specific storefronts, or markets with different domains, languages, currencies, product availability, and pricing expectations.

The preparation stage should identify:

| Decision area               | Preparation question                                                                                         |
| --------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Store model                 | Will B2B and direct-to-consumer sales share one store, use separate stores, or follow a hybrid model?        |
| Organization governance     | Which teams own products, content, pricing, catalogs, redirects, apps, and launch decisions across stores?   |
| Markets and localization    | Which regions, languages, currencies, domains, and market-specific experiences must be preserved or rebuilt? |
| Brand or channel separation | Which records belong to each brand, storefront, sales channel, or customer audience?                         |
| Operational ownership       | Who approves migrated samples, pricing behavior, buyer access, and redirects before launch?                  |

These decisions influence migration scope. They affect which records are moved where, how duplicate-looking records are interpreted, how URL and content continuity is handled, and which validation samples are meaningful. If governance is unclear, the migration may appear complete while teams disagree about which store, market, or workflow owns the result.

### Prepare Product, Variant, and Custom Data Samples <a href="#prepare-product-variant-and-custom-data-samples" id="prepare-product-variant-and-custom-data-samples"></a>

Product preparation should focus on high-risk meaning, not only catalog size. Shopify products can use options and variants, variant-level inventory, product taxonomy, collections, metafields, category metafields, and metaobjects. Shopify Plus merchants may also have product data shaped by B2B pricing, Combined Listings scenarios, custom storefront logic, ERP identifiers, app-managed fields, or integration-dependent attributes.

Useful product preparation includes:

* products with many options, variants, or SKU-level operational differences;
* products that appear in different B2B catalogs with different visibility or pricing;
* products sold to both B2B and direct-to-consumer customers;
* category-specific attributes that affect filtering, comparison, merchandising, feeds, or SEO;
* metafields or metaobjects that carry specifications, part numbers, downloadable documents, release dates, compliance details, or buying rules;
* products that depend on source-side bundles, personalization, custom configurations, or extension-owned logic;
* products tied to ERP, PIM, fulfillment, subscription, or marketplace identifiers.

A preparation checklist should classify each high-risk product pattern into supported migration mapping, Add-on scope, Custom Service review, or post-migration setup handled outside the data migration. This prevents custom information from being migrated into fields that exist but are not operationally useful.

### Prepare App, Integration, and External Identifier Inventory <a href="#prepare-app-integration-and-external-identifier-inventory" id="prepare-app-integration-and-external-identifier-inventory"></a>

Shopify Plus migrations often involve surrounding systems that carry business meaning beyond storefront data. ERP, CRM, PIM, WMS, tax, payment, subscription, loyalty, B2B quoting, marketplace, analytics, automation, and middleware systems may all depend on identifiers, statuses, flags, custom fields, or workflow assumptions.

Preparation should identify:

* external customer, company, company-location, product, variant, order, and fulfillment IDs;
* app-owned fields and records that do not belong to Shopify standard data;
* integration-specific statuses, flags, notes, or mapping keys;
* custom fields required by ERP, CRM, support, reporting, fulfillment, or tax workflows;
* source-side app behavior that must be rebuilt, replaced, or intentionally retired;
* owners who can validate whether a migrated value remains usable by the receiving system.

Unsupported app data or integration-owned business logic should not be treated as ordinary field transfer. If the source meaning depends on custom fields, bespoke transformations, Custom Platform source logic, or custom migration logic adjustment, the preparation stage should flag it for Custom Service rather than relying on standard record movement.

### Prepare URL, Content, and SEO Evidence <a href="#prepare-url-content-and-seo-evidence" id="prepare-url-content-and-seo-evidence"></a>

Shopify Plus preparation should include traffic and content continuity before migration execution begins. This is especially important for merchants with large catalogs, localized pages, B2B-gated content, high-value collections, content-led landing pages, wholesale portals, blogs, or multiple domains and markets.

The business should prepare:

* priority product, collection, CMS Pages, Blog Posts, and landing-page URLs;
* source URLs that drive revenue, search visibility, paid campaign traffic, partner links, or customer account access;
* localized or market-specific URL patterns;
* pages that should be gated, redirected, recreated, consolidated, or retired;
* content that depends on apps, theme sections, custom blocks, or platform-specific layouts;
* redirect ownership by store, domain, language, market, or buyer context.

Preparation should not attempt to solve every SEO decision inside the platform hub. The important Shopify Plus task is to identify which URLs and content paths are commercially sensitive and which samples must be included in migration review because they reveal store, market, or access-control assumptions.

### Design a Useful Demo Migration Sample <a href="#design-a-useful-demo-migration-sample" id="design-a-useful-demo-migration-sample"></a>

A Demo Migration is most useful when the sample is designed around Shopify Plus risk areas. A random product or customer sample may prove that data can appear in Shopify, but it may not prove whether the Target Platform can represent the business correctly.

A strong Shopify Plus sample should include:

| Sample type                         | What it should test                                                                           |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| Multi-location company              | Parent company, location records, contacts, permissions, tax, payment, and checkout behavior. |
| Catalog-sensitive buyer             | Product visibility, pricing, quantity rules, and assignment logic.                            |
| B2B plus direct-to-consumer product | Whether the same product behaves correctly for different buyer contexts.                      |
| Custom-data product                 | Metafields, metaobjects, category attributes, external IDs, or app-owned fields.              |
| Market or store-specific URL        | Redirects, content ownership, localization, or domain assumptions.                            |
| Integration-critical record         | ERP, CRM, fulfillment, tax, support, or reporting identifiers.                                |

The sample should be small enough to review carefully and strong enough to expose the migration assumptions that matter most. When the Demo Migration sample avoids hard cases, it can create confidence in the wrong areas.

### Prepare Scope Decisions for Add-ons and Custom Service <a href="#prepare-scope-decisions-for-add-ons-and-custom-service" id="prepare-scope-decisions-for-add-ons-and-custom-service"></a>

Preparation should separate supported configuration from customization. Add-ons can support filtering, mapping, and supported data configuration, such as narrowing a migration scope, mapping specific fields, or configuring supported data behavior. Custom Service is different. It applies when the migration requires customization, modification, Custom Platform handling, unsupported structures, app-owned data, bespoke transformation, outside-system identifiers, or custom migration logic adjustment.

A Shopify Plus preparation checklist should classify findings into three groups:

| Finding                                                                                                                                          | Likely handling                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Supported product, customer, order, content, or redirect data                                                                                    | Standard Service scope, depending on the selected migration path and supported entities. |
| Filtering, mapping, or supported configuration needs                                                                                             | Add-ons, when the requested work fits supported behavior.                                |
| B2B custom logic, app-owned structures, unsupported source data, external identifiers, bespoke transformation, or Custom Platform source context | Custom Service review.                                                                   |

This classification improves planning accuracy before Article 6 service-path selection. It also prevents Add-ons from being used as a generic substitute for Custom Service.

### Prepare for Later Migration Activity Without Relying on It <a href="#prepare-for-later-migration-activity-without-relying-on-it" id="prepare-for-later-migration-activity-without-relying-on-it"></a>

Shopify Plus merchants may continue receiving new products, customers, orders, company updates, catalog changes, pricing changes, or content updates while migration planning is still underway. Additional Migration Options can help handle later migration activity when platform-specific data changes after an earlier migration action, but they should not be treated as a reason to delay preparation.

The preparation stage should record which areas are likely to change before launch:

* new or modified products and variants;
* new customers, companies, company locations, or contacts;
* new orders or account activity;
* catalog assignments, prices, quantity rules, or volume pricing;
* CMS Pages, Blog Posts, redirects, or high-value URLs;
* metafields, metaobjects, app-owned values, or integration identifiers.

When Entity Points are mentioned in planning conversations, the rule must remain accurate: Entity Points consumption depends on whether migrated entities are new to the service-license record, not merely on whether the customer performs later migration activity. Already recorded entities do not consume Entity Points again solely because a follow-up migration option is used.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify Plus preparation is strongest when it turns enterprise complexity into reviewable evidence before migration execution. Companies, company locations, buyer contacts, catalogs, pricing, store governance, markets, products, custom data, integrations, URLs, and Demo Migration samples should all be prepared around the business behavior the Target Platform must support.

A well-prepared Shopify Plus migration does not rely on record counts alone. It defines which relationships, prices, access rules, storefront paths, and operational identifiers must remain meaningful after launch, then uses Demo Migration and later validation to prove those outcomes before the business depends on them.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating into Shopify Plus?**

Start with the target operating model: companies, company locations, buyer contacts, permissions, catalogs, pricing behavior, store structure, and the high-risk workflows that must be represented correctly in Shopify Plus.

**Why is catalog preparation so important for Shopify Plus?**

Catalogs can control product availability and pricing for companies and company locations. If catalog evidence is incomplete, migrated products can look correct while important buyers see the wrong products, prices, or quantity rules.

**Should Shopify Plus preparation focus mainly on product data?**

No. Product structure matters, but Shopify Plus readiness often depends more on company relationships, buyer access, catalog assignments, payment terms, custom data, integration identifiers, and store governance.

**When should Shopify Plus preparation escalate to Custom Service?**

Custom Service should be considered when the migration involves Custom Platform source logic, unsupported B2B structures, app-owned records, external-system identifiers, bespoke transformations, custom fields, or custom migration logic adjustment.

**Can Additional Migration Options replace preparation work?**

No. Additional Migration Options can support later migration activity when data changes, but they do not replace company, catalog, pricing, custom-data, URL, and validation-sample preparation before launch.
