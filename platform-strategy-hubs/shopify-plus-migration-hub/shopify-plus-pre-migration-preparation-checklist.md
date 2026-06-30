# Shopify Plus Pre-Migration Preparation Checklist

Shopify Plus preparation should start with enterprise operating evidence, not only exported store records. A Shopify Plus migration often involves the same core Shopify data areas as a standard Shopify store, but the readiness burden changes when the target environment includes organization-level administration, multiple stores, B2B companies, catalogs, Markets, localized storefronts, custom data, integrations, and enterprise approval workflows.

The preparation goal is to define how the Shopify Plus environment should operate after launch. Products, variants, collections, customers, orders, CMS Pages, Blog Posts, redirects, metafields, metaobjects, app data, and integration references should be prepared as part of a larger operating model. When the target environment includes several brands, regions, channels, B2B and D2C audiences, or ERP-connected workflows, migration readiness depends on whether the team can explain how each source structure should land in Shopify Plus.

### Confirm the Shopify Plus Operating Model <a href="#confirm-the-shopify-plus-operating-model" id="confirm-the-shopify-plus-operating-model"></a>

Before preparing entity files, define the intended Shopify Plus structure. Shopify Plus can support organization-level management, multiple stores, B2B selling, international markets, user controls, automation, and enterprise app architecture, but migration planning should not assume that these areas are automatically created from source data.

Start with a practical operating map:

| Operating area              | Preparation question                                                                             | Why it matters for Shopify Plus                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| Organization and stores     | Will the target use one store, multiple expansion stores, or separate B2B/D2C stores?            | Data scope, redirects, content, users, integrations, and validation responsibility may differ by store.                |
| B2B model                   | Will B2B use companies, locations, catalogs, price lists, payment terms, or restricted products? | Source customer groups and wholesale logic may need interpretation before migration.                                   |
| Markets and localization    | Which countries, currencies, languages, domains, and localized content matter at launch?         | International structure affects URLs, pricing expectations, catalog visibility, and storefront review.                 |
| Catalog governance          | Which product structures are shared, localized, market-specific, or channel-specific?            | Large catalogs can fail when variants, metafields, collections, and product status are prepared only globally.         |
| Integration ownership       | Which systems own product, customer, order, inventory, pricing, tax, or fulfillment truth?       | ERP, PIM, OMS, WMS, CRM, subscription, loyalty, and marketplace systems may control records beyond standard migration. |
| Administration and security | Which teams need access to stores, organization settings, data review, and launch tasks?         | Enterprise validation often fails when approval ownership is unclear.                                                  |

This operating map should be created before deciding whether the migration is simple, managed, or custom. Shopify Plus complexity is usually not only data volume. It is often the number of stores, buyer types, markets, integrations, and governance decisions that must work together.

### Prepare Store and Organization Evidence <a href="#prepare-store-and-organization-evidence" id="prepare-store-and-organization-evidence"></a>

Shopify Plus readiness should include a target-store inventory. A merchant may migrate into one primary store, several expansion stores, separate B2B and D2C stores, regional storefronts, or a phased rollout where some stores launch later. Each option changes preparation.

Prepare a store-level plan that identifies:

* target store names, purposes, brands, regions, or audiences;
* whether each store is new, existing, duplicated, or replacing an earlier storefront;
* which data belongs to each store;
* which products, collections, content, customers, orders, and redirects should be shared, separated, or excluded;
* which users or teams will review each store;
* which integrations connect to each store;
* which stores require B2B, Markets, Shopify Flow, custom apps, or external-system testing;
* which stores are part of launch and which are later phases.

This preparation prevents a common Shopify Plus mistake: treating multi-store rollout as a single-store migration with extra records. A store-level plan makes it clear which migrated data belongs where and which review team owns the outcome.

### Prepare Catalog, Variants, and Product Governance <a href="#prepare-catalog-variants-and-product-governance" id="prepare-catalog-variants-and-product-governance"></a>

Shopify Plus catalog preparation should separate product structure from enterprise governance. A source catalog may include configurable products, variants, bundles, kits, subscriptions, custom options, product relationships, regional assortments, wholesale-only items, product restrictions, technical specifications, and PIM-controlled attributes. These structures cannot be prepared only as product counts.

Prepare catalog samples that expose the real target needs:

| Catalog sample                                       | Shopify Plus readiness value                                                                                    |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Simple product                                       | Confirms baseline product, image, collection, and status handling.                                              |
| Variant-heavy product                                | Tests option and variant structure, SKU, price, inventory, image, and fulfillment behavior.                     |
| Market-specific product                              | Reveals whether product availability, pricing, content, or URL expectations change by country or region.        |
| B2B-specific product                                 | Tests catalog visibility, company pricing, and restricted buying assumptions.                                   |
| Bundle, kit, subscription, or build-your-own product | Identifies app, setup, or Custom Service requirements.                                                          |
| Product with rich specifications                     | Clarifies whether data belongs in product fields, metafields, metaobjects, theme sections, or external systems. |
| PIM- or ERP-controlled product                       | Shows which identifiers and update rules must remain connected after migration.                                 |

The team should decide which source values become Shopify products, options, variants, collections, tags, metafields, metaobjects, app configuration, theme content, or excluded data. For Shopify Plus, this decision often needs participation from merchandising, operations, wholesale, localization, and integration teams.

### Prepare B2B Companies, Customers, and Account Context <a href="#prepare-b2b-companies-customers-and-account-context" id="prepare-b2b-companies-customers-and-account-context"></a>

B2B readiness is one of the main differences between Shopify and Shopify Plus preparation. Source customer groups, companies, account hierarchies, buyer roles, wholesale catalogs, price lists, credit terms, tax exemptions, sales-rep assignments, and approval workflows may not be ordinary customer fields. Some can be represented through Shopify B2B structures. Some require Shopify setup, app configuration, integration work, Add-ons, or Custom Service review.

Prepare B2B evidence before Demo Migration:

| B2B evidence                   | Planning question                                                                       |
| ------------------------------ | --------------------------------------------------------------------------------------- |
| Company accounts               | Which source records represent companies rather than individual customers?              |
| Company locations              | Do billing, shipping, branch, franchise, or department records need separate treatment? |
| Buyers and contacts            | Which people should be associated with companies or locations?                          |
| Catalogs and pricing           | Which products, price lists, discounts, or restrictions apply to each customer group?   |
| Payment terms and tax settings | Which values are target-side setup, integration-managed, or migration scope?            |
| Sales-rep and ERP references   | Which identifiers must remain available for operations or reporting?                    |

D2C customer preparation should still include normal customer and order samples, but Shopify Plus B2B adds another layer: buyer identity may involve company context, not only a customer profile. If the source platform stores B2B data through custom fields, extensions, modules, ERP tables, or sales-team processes, prepare examples for Custom Service review instead of assuming they can be migrated as standard customer data.

### Prepare Markets, Localization, Domains, and Redirects <a href="#prepare-markets-localization-domains-and-redirects" id="prepare-markets-localization-domains-and-redirects"></a>

Shopify Plus migrations often involve international selling or multi-region operations. Preparation should clarify which structures belong to Shopify Markets, which belong to separate stores, and which belong to external systems or manual launch work.

Prepare a market and localization inventory:

* countries and regions served at launch;
* primary and secondary markets;
* currencies and pricing assumptions;
* languages and translation sources;
* domains, subdomains, and subfolders;
* localized product content, CMS Pages, Blog Posts, policies, and navigation;
* duties, import tax, and international shipping expectations;
* regional product availability;
* market-specific redirects and SEO-critical URLs;
* country or language-specific apps, feeds, and integrations.

A redirect plan should be prepared at the same time as market planning. Shopify URL behavior and market structure can affect how legacy URLs resolve. High-value source URLs, localized paths, campaign pages, product pages, category pages, CMS Pages, and Blog Posts should be mapped to accepted Shopify destinations before launch.

### Prepare Orders, Fulfillment, and Operational History <a href="#prepare-orders-fulfillment-and-operational-history" id="prepare-orders-fulfillment-and-operational-history"></a>

Shopify Plus order preparation should distinguish historical reference from live operations. Migrated orders can support service, reporting, and customer history review, but they do not configure fulfillment workflows, payment processing, Shopify checkout behavior, tax logic, return flows, or integration rules.

Prepare order samples that include:

* ordinary completed orders;
* refunded, cancelled, partially fulfilled, and returned orders;
* B2B orders with company context;
* cross-border orders with currencies, duties, or regional shipping assumptions;
* orders with discounts, gift cards, tax differences, tips, or custom charges;
* orders connected to ERP, OMS, WMS, accounting, subscription, or loyalty systems;
* orders with external identifiers needed by support or finance teams;
* recent orders created during the migration window.

For enterprise operations, order validation should include the teams that rely on historical records: support, finance, fulfillment, wholesale, regional operations, and integration owners. A migrated order that appears acceptable to a content team may still be insufficient for accounting or customer service if key external references are missing.

### Prepare Apps, Integrations, Custom Data, and Automation <a href="#prepare-apps-integrations-custom-data-and-automation" id="prepare-apps-integrations-custom-data-and-automation"></a>

Shopify Plus readiness must identify which business logic belongs to migration output and which belongs to target-side implementation. Enterprise stores often depend on apps, custom apps, Shopify Flow, ERP, PIM, OMS, WMS, CRM, loyalty platforms, subscription systems, personalization tools, tax services, shipping systems, marketplaces, analytics, and custom reporting.

Create a dependency inventory before selecting the final migration approach:

| Dependency type            | Preparation decision                                                                    |
| -------------------------- | --------------------------------------------------------------------------------------- |
| Native Shopify fields      | Confirm whether source values map to supported Shopify structures.                      |
| Metafields and metaobjects | Define target custom-data structures before migration when they carry business meaning. |
| Shopify apps               | Decide whether migrated data must be interpreted by an app after launch.                |
| Custom apps and APIs       | Identify external identifiers, ownership, and synchronization rules.                    |
| Shopify Flow or automation | Decide which workflows must be rebuilt or tested after migration.                       |
| ERP/PIM/OMS/WMS/CRM        | Confirm which system is the source of truth for each field or workflow.                 |
| Unsupported source data    | Prepare examples for Custom Service review.                                             |

This inventory also clarifies Add-ons vs Custom Service. Add-ons can help with bounded filtering, mapping, or configuration within supported behavior. Custom Service is needed when unsupported records, app-owned data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment are required.

### Prepare Demo Migration Samples and Review Owners <a href="#prepare-demo-migration-samples-and-review-owners" id="prepare-demo-migration-samples-and-review-owners"></a>

Demo Migration for Shopify Plus should be treated as a structured enterprise review, not a quick preview. The sample set should prove whether the target structure works across the most important Plus dimensions.

A strong sample set includes:

| Sample area                     | What it should prove                                                                            |
| ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Product with variants           | Options, variants, SKUs, images, price, and inventory remain usable.                            |
| B2B company and buyer           | Company, buyer, catalog, pricing, and account context are correctly represented where in scope. |
| Market-specific product or page | Localization, availability, URL, and content assumptions are understood.                        |
| High-value URL                  | Redirect destination is accepted and testable.                                                  |
| Order with exceptions           | Refunds, fulfillment, discounts, tax, payment context, and external references remain readable. |
| Custom-data record              | Metafield, metaobject, app, or custom identifier handling is validated.                         |
| Integration-owned record        | Data ownership and post-migration synchronization expectations are clear.                       |
| Expansion-store sample          | Store-specific data assignment and review responsibility are confirmed.                         |

Assign review owners before Demo Migration. Shopify Plus launches usually involve several teams, and a sample can fail if no one knows who is responsible for approving B2B, localization, integration, SEO, or fulfillment evidence.

### Plan the Migration Window and Later Migration Activity <a href="#plan-the-migration-window-and-later-migration-activity" id="plan-the-migration-window-and-later-migration-activity"></a>

Enterprise Shopify Plus projects often continue operating source stores while migration review is in progress. The preparation plan should define how new products, customers, companies, orders, CMS Pages, Blog Posts, and URL changes will be handled between the first migration run and launch.

Use current migration-action language only for practical launch timing. The team may need to continue migration activity with the previous configuration, continue with a new configuration, or perform a new migration if the target result needs to be refreshed. The preparation decision should focus on what data should be affected, whether the configuration changes, who performs the action, and what must be revalidated afterward.

Entity Points should be interpreted consistently. Newly migrated eligible entities may consume Entity Points when first migrated. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify Plus migration preparation is an enterprise readiness exercise. The team should prepare organization and store structure, catalog governance, B2B companies and buyers, Markets and localization, customer and order history, apps, integrations, custom data, Demo Migration samples, review ownership, and launch-window timing before treating Full Migration as ready.

The strongest preparation work turns source complexity into clear target decisions. It identifies which data can migrate through supported behavior, which settings must be configured in Shopify Plus, which requirements need Add-ons, which expectations require Custom Service review, and which outcomes must be proven before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Shopify Plus migration?**

Start with the Shopify Plus operating model: organization structure, stores, B2B needs, Markets, integrations, and review ownership. Entity files are easier to prepare once the target structure is clear.

**How is Shopify Plus preparation different from Shopify preparation?**

Shopify Plus preparation usually has more enterprise governance: multiple stores, B2B companies, regional markets, organization users, custom apps, automation, external systems, and approval workflows. The same core data types may exist, but the planning burden is broader.

**Should B2B data be treated as ordinary customer data?**

No. Companies, locations, buyers, catalogs, pricing, payment terms, and external references should be prepared separately from ordinary customer profiles. Some B2B behavior may require Shopify setup, integration work, Add-ons, or Custom Service review.

**When should Custom Service be considered during preparation?**

Custom Service should be considered when the source contains unsupported records, app-owned data, custom fields, external-system identifiers, bespoke transformations, Custom Platform structures, or custom migration logic adjustment needs.

**Why should Demo Migration samples be assigned to specific reviewers?**

Shopify Plus validation often spans merchandising, B2B, localization, SEO, fulfillment, finance, and integration teams. Assigned reviewers prevent important samples from being approved without the right operational expertise.
