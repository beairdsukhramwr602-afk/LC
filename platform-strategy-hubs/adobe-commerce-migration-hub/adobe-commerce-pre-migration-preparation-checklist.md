# Adobe Commerce Pre-Migration Preparation Checklist

Adobe Commerce preparation should define how the Target Store must operate before data is moved. The platform can support enterprise storefront scope, B2B company relationships, shared catalogs, buyer-specific pricing, governed catalog visibility, Content Staging, integrations, inventory sources, URL rules, and complex product architecture. Those decisions affect whether migrated records are commercially usable after launch.

A strong preparation phase produces evidence for configuration, Demo Migration review, service-scope decisions, and final validation. For Adobe Commerce, that evidence should include company-account samples, shared catalog assignments, storefront-scope decisions, product-architecture examples, URL priorities, integration identifiers, content-timing notes, and a clear list of items that may require Add-ons or Custom Service review.

Preparation is not a promise that every business rule will transfer as standard data. It is the step that separates standard record movement from target-side configuration, Add-on-supported mapping, and custom handling before migration work becomes launch-sensitive.

### Preparation Priorities for Adobe Commerce <a href="#preparation-priorities-for-adobe-commerce" id="preparation-priorities-for-adobe-commerce"></a>

| Preparation area            | What to prepare                                                                                                                                                             | Why it matters                                                                                                        |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Target operating model      | B2B, B2C, hybrid, multi-brand, multi-region, wholesale, retail, distributor, marketplace, or integration-led expectations.                                                  | The operating model controls how migrated data should behave in Adobe Commerce.                                       |
| Storefront scope            | Websites, stores, store views, languages, regions, domains, brands, customer segments, and channel boundaries.                                                              | Scope decisions affect catalog visibility, content, URLs, pricing context, and validation samples.                    |
| B2B company data            | Companies, administrators, users, roles, permissions, credit settings, quote behavior, purchase order expectations, and approval flows.                                     | B2B success depends on buyer relationships and purchasing controls, not only customer records.                        |
| Shared catalogs and pricing | Company assignments, customer groups, product visibility, tier prices, negotiated prices, shared catalog pricing, and restricted assortments.                               | Buyers may see different products or prices depending on company, group, or storefront context.                       |
| Product architecture        | Product types, configurable relationships, child SKUs, bundles, grouped products, downloadable products, attributes, attribute sets, categories, and merchandising fields.  | Products must remain purchasable, searchable, maintainable, and usable in Adobe Commerce.                             |
| Inventory and fulfillment   | Stock sources, sales channels, salable quantity expectations, warehouses, reservations, backorders, and external fulfillment ownership.                                     | Quantity alone may not represent how Adobe Commerce should determine availability after launch.                       |
| Content and campaigns       | CMS Pages, CMS blocks, Blog Posts, promotional content, price rules, scheduled updates, campaign pages, and launch-sensitive content.                                       | Time-sensitive content may need recreation, configuration, or launch-specific validation rather than simple transfer. |
| URLs and SEO                | Product URLs, category URLs, CMS Page paths, Blog Post paths, URL rewrites, redirects, canonical routes, localized paths, and high-value landing pages.                     | SEO continuity depends on preserving or redirecting the routes that matter most.                                      |
| Extensions and integrations | Extension-owned fields, custom modules, ERP/PIM/CRM identifiers, payment and shipping dependencies, tax fields, warehouse references, subscription IDs, and reporting keys. | External systems may depend on values that are not obvious during storefront review.                                  |

### Define the Target Operating Model Before Mapping Data <a href="#define-the-target-operating-model-before-mapping-data" id="define-the-target-operating-model-before-mapping-data"></a>

Adobe Commerce preparation should begin with the intended Target Store model. A merchant should know whether the launch environment must support B2C commerce, B2B commerce, hybrid B2B/B2C operations, multiple brands, multiple regions, multiple languages, wholesale purchasing, distributor portals, staged campaigns, or enterprise integrations.

This decision changes how the migration should be reviewed. A B2B-heavy store needs deeper company-account and shared-catalog preparation. A multi-region store needs scope mapping across websites, stores, and store views. A complex catalog needs product-architecture samples. An integration-heavy store needs external identifiers and ownership rules documented before Full Migration.

Prepare a short operating-model brief with these decisions:

| Operating decision   | Preparation evidence                                                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Storefront structure | Intended websites, stores, store views, languages, regions, brands, domains, and business channels.                                        |
| Buyer model          | Retail customers, company accounts, company administrators, purchasing users, approvers, and mixed-account behavior.                       |
| Pricing model        | Base pricing, customer group pricing, tier pricing, shared catalog pricing, negotiated pricing, quote expectations, and promotional rules. |
| Catalog model        | Product types, variants, bundles, grouped products, attributes, attribute sets, categories, visibility rules, and merchandising fields.    |
| Fulfillment model    | Inventory sources, stocks, warehouses, pickup locations, backorder rules, reservations, and external fulfillment systems.                  |
| Integration model    | ERP, PIM, CRM, WMS, payment, shipping, tax, analytics, marketplace, and reporting identifiers that must remain traceable.                  |

If the operating model is unclear, the migration may still move records, but reviewers will not have enough context to decide whether the result is commercially correct.

### Prepare B2B Company Accounts and Buyer Relationships <a href="#prepare-b2b-company-accounts-and-buyer-relationships" id="prepare-b2b-company-accounts-and-buyer-relationships"></a>

Adobe Commerce B2B preparation should separate individual customer records from company-level buying relationships. A company account can affect user access, buyer roles, purchasing permissions, credit controls, quote behavior, purchase order behavior, payment method availability, shipping method availability, shared catalog access, and pricing visibility.

Prepare a company-account inventory before migration configuration begins:

| Company preparation item                     | Question to answer                                                                                                                              |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Company identity                             | Which source accounts represent companies rather than individual retail buyers?                                                                 |
| Company administrator                        | Which user should administer each company account in Adobe Commerce?                                                                            |
| Company users                                | Which buyers belong to each company, branch, department, location, or purchasing team?                                                          |
| Roles and permissions                        | Which users can browse, request quotes, place orders, approve purchases, manage users, or administer the company account?                       |
| Credit and payment rules                     | Which companies have credit limits, payment terms, allowed payment methods, restricted payment methods, or purchase order expectations?         |
| Shipping controls                            | Which shipping methods are allowed, restricted, or company-specific?                                                                            |
| Customer group and shared catalog assignment | Which customer group or shared catalog should control visibility and pricing for each company?                                                  |
| External identifiers                         | Which company IDs, ERP account IDs, dealer IDs, procurement IDs, sales-representative IDs, or account-manager references must remain traceable? |

If the Source Platform does not have native company accounts, identify where B2B meaning is stored. It may appear as customer groups, customer tags, custom fields, app metadata, wholesale records, ERP account codes, price-list references, or notes. When these values are outside standard data, they may require Add-ons, Custom Add-ons, or Custom Service review.

### Prepare Shared Catalogs and Pricing Rules <a href="#prepare-shared-catalogs-and-pricing-rules" id="prepare-shared-catalogs-and-pricing-rules"></a>

Shared catalog preparation should happen before Demo Migration sample review. Product records can migrate correctly while buyer-specific visibility or pricing remains incomplete. Adobe Commerce shared catalogs may determine which products a company can see and what prices are available to that company.

Prepare shared catalog evidence with these items:

| Shared catalog item   | What to confirm                                                                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Shared catalog list   | Which shared catalogs are needed at launch?                                                                                                      |
| Company assignment    | Which companies, customer groups, or buyer segments belong to each shared catalog?                                                               |
| Product assignment    | Which products must be visible or hidden for each shared catalog?                                                                                |
| Pricing basis         | Which prices are base prices, customer-group prices, tier prices, negotiated prices, shared catalog prices, or externally owned contract prices? |
| Visibility exceptions | Which buyers need restricted, expanded, temporary, or region-specific access?                                                                    |
| Launch priority       | Which companies, catalogs, and products must be validated before go-live?                                                                        |

When pricing or visibility is controlled by ERP, PIM, sales-team spreadsheets, contract systems, or custom extensions, document that dependency early. Standard product and customer migration cannot preserve rules that do not exist as standard exportable commerce data.

### Map Websites, Stores, and Store Views Before Export <a href="#map-websites-stores-and-store-views-before-export" id="map-websites-stores-and-store-views-before-export"></a>

Adobe Commerce scope affects where data appears and how it behaves. Websites, stores, and store views may influence language, region, currency, content, catalog visibility, customer behavior, configuration, URL structure, and validation responsibility. Source platforms may represent the same business differences through markets, channels, domains, apps, duplicated stores, customer groups, tags, or custom logic.

Create a scope map before migration:

| Source condition                  | Adobe Commerce planning decision                                                                                            |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Multiple domains                  | Decide whether each domain maps to a website, store, store view, or URL configuration.                                      |
| Multiple languages                | Decide which product values, category values, CMS Pages, Blog Posts, metadata, and URLs need store-view-specific handling.  |
| Multiple regions                  | Decide how regional catalogs, prices, taxes, shipping rules, and content should be represented.                             |
| B2B and B2C separation            | Decide whether separation belongs in websites, customer groups, shared catalogs, categories, permissions, or configuration. |
| Brand or business-unit separation | Decide whether each brand requires separate catalog, content, URL, pricing, or validation samples.                          |
| External channel ownership        | Decide which data is managed by Adobe Commerce and which remains controlled by ERP, PIM, marketplace, or other systems.     |

Scope mistakes can be difficult to fix after data has been migrated. A product may exist, but with the wrong language, wrong category, wrong URL, wrong price visibility, or wrong buyer access in a specific storefront context.

### Prepare Product Architecture and Catalog Governance <a href="#prepare-product-architecture-and-catalog-governance" id="prepare-product-architecture-and-catalog-governance"></a>

Adobe Commerce product preparation should include the selling model behind each important product type. A source item may become a simple product, configurable product, bundle product, grouped product, virtual product, downloadable product, or a custom-handled structure depending on how buyers select, purchase, receive, and maintain it.

Prepare representative catalog samples for:

* configurable products with child SKUs, option labels, images, prices, stock values, and identifiers;
* bundle, grouped, virtual, and downloadable products where relevant;
* products with personalized options, custom options, or customer-entered values;
* products with technical specifications, compatibility data, product-family logic, or regulated attributes;
* products with localized names, descriptions, metadata, media, or store-view-specific values;
* products controlled by PIM, ERP, marketplace feeds, subscriptions, extensions, or custom modules;
* products that appear in shared catalogs, customer-specific assortments, or restricted B2B visibility groups.

Attributes and attribute sets should also be prepared before mapping. Adobe Commerce attributes may affect product display, layered navigation, search, comparison, rules, reporting, imports, integrations, and administrative maintenance. Attribute sets should group product-family fields in a way that supports ongoing catalog governance, not only initial migration.

### Prepare Content, Campaign Timing, and URL Continuity <a href="#prepare-content-campaign-timing-and-url-continuity" id="prepare-content-campaign-timing-and-url-continuity"></a>

Adobe Commerce preparation should separate evergreen content from launch-sensitive or scheduled commercial content. CMS Pages, CMS blocks, Blog Posts, landing pages, banners, promotion pages, price rules, and campaign assets may need timing-aware review if they affect launch campaigns, seasonal merchandising, B2B announcements, or region-specific storefronts.

Prepare a content and SEO inventory with:

* high-value product, category, CMS Page, Blog Post, and landing-page URLs;
* URL rewrites, redirects, canonical expectations, localized paths, and historical campaign routes;
* internal links, embedded media, downloadable files, forms, and custom layouts;
* CMS blocks and reusable content used across multiple storefronts;
* pages that require store-view-specific language, region, customer segment, or B2B visibility;
* scheduled campaign content that should be recreated, configured, or manually validated in Adobe Commerce.

Not every old route deserves equal attention, but high-traffic and revenue-sensitive URLs should be documented before Full Migration. URL and content preparation should give reviewers a route-level checklist rather than a vague instruction to inspect the storefront later.

### Prepare Inventory, Fulfillment, and Operational Ownership <a href="#prepare-inventory-fulfillment-and-operational-ownership" id="prepare-inventory-fulfillment-and-operational-ownership"></a>

Inventory preparation should confirm the system of record and the target behavior expected after migration. A single quantity value may not fully represent Adobe Commerce availability when the business uses multiple sources, reservations, warehouses, pickup locations, regional selling rules, backorders, ERP-managed stock, marketplace stock, or external fulfillment systems.

Prepare inventory details such as:

* stock source of truth and the timing of the final inventory update;
* source-to-stock and source-to-sales-channel relationships;
* products with backorders, preorder behavior, low-stock thresholds, safety stock, or allocation rules;
* SKUs managed by ERP, WMS, marketplace, supplier feeds, or custom fulfillment workflows;
* products where availability differs by website, store, warehouse, customer segment, region, or channel;
* sample SKUs for Demo Migration inventory review.

Inventory should be treated as launch-sensitive data. If stock changes frequently, preparation should identify whether Additional Migration Options or a closer-to-launch data refresh is needed to reduce freshness gaps, followed by renewed review of affected products and orders.

### Classify Extensions, Custom Fields, and Integration Dependencies <a href="#classify-extensions-custom-fields-and-integration-dependencies" id="classify-extensions-custom-fields-and-integration-dependencies"></a>

Adobe Commerce migrations often involve data shaped by extensions, custom modules, ERP systems, PIM systems, CRM systems, shipping platforms, accounting systems, marketplaces, tax systems, search tools, loyalty programs, subscriptions, procurement systems, or reporting workflows. Preparation should identify these dependencies before migration scope is confirmed.

Classify each non-standard item before migration:

| Classification       | Meaning                                                                                                      | Likely handling                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| Standard field       | The value fits a standard source and target field.                                                           | Standard Service may be enough, depending on migration path support.              |
| Mappable field       | The value exists in supported data but needs field-level mapping or configuration.                           | Add-ons such as Advanced Data Mapping or Advanced Data Configure may be relevant. |
| Filtered scope       | Only selected records or selected conditions should migrate.                                                 | Data Filter Add-on may be relevant.                                               |
| Extension-owned data | The value is stored by an extension, custom module, app, or unsupported source structure.                    | Custom Service review is usually safer.                                           |
| External-system data | The value is owned by ERP, PIM, CRM, WMS, marketplace, tax, subscription, procurement, or reporting systems. | Custom Service or implementation-side coordination may be required.               |
| Custom logic         | The requirement depends on transformation, rule conversion, custom behavior, or bespoke workflow.            | Custom Service should be reviewed before migration begins.                        |

This classification helps prevent late surprises. When the requirement is identified before Demo Migration, the migration scope can be adjusted earlier. When it is found after Full Migration, the project may need rework, remapping, or additional service review.

### Prepare Access, Backups, and Migration Windows <a href="#prepare-access-backups-and-migration-windows" id="prepare-access-backups-and-migration-windows"></a>

Adobe Commerce preparation should also make the environments reachable, stable, and recoverable. Enterprise stores often involve multiple teams, hosting controls, security reviews, firewall rules, integration owners, and launch windows. Missing access or unclear ownership can delay extraction, media transfer, import troubleshooting, or validation.

| Item              | What to prepare                                                                                                           | Why it matters                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Source access     | Admin, API, database, file, media, export, and connector access required for the selected migration path.                 | Incomplete access can prevent full extraction or media transfer.               |
| Target access     | Adobe Commerce admin, API, database, file, hosting, deployment, and media access when needed.                             | Target access affects configuration, import, troubleshooting, and review.      |
| Backups           | Recent source and target backups, including database and media files where relevant.                                      | Backups reduce recovery risk if configuration or import work must be reversed. |
| Security controls | Firewall rules, IP allowlists, two-factor access, CAPTCHA, hosting restrictions, and maintenance windows.                 | Security controls can block migration activity if not prepared.                |
| Ownership         | Contacts for source platform, Target Store, hosting, SEO, ERP, PIM, CRM, fulfillment, tax, payment, and integrations.     | Clear ownership speeds issue resolution.                                       |
| Launch timing     | Freeze windows, content deadlines, catalog update windows, inventory refresh timing, and B2B buyer-communication windows. | Timing decisions affect data freshness and review scope.                       |

The Target Store should not be treated as ready only because it is accessible. It should also be stable enough for Demo Migration review, configured enough to represent the intended structure, and protected by backups or recovery options.

### Build Demo Migration Review Samples <a href="#build-demo-migration-review-samples" id="build-demo-migration-review-samples"></a>

Demo Migration is most useful when the sample set reflects Adobe Commerce risk. Random records may show whether data can transfer, but they may not prove that complex business behavior is represented correctly.

Prepare sample groups before running or reviewing Demo Migration:

| Sample group               | Include examples of                                                                                                                     |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| B2B buyers                 | Company administrator, company user, restricted buyer, quote user, purchase order user, and retail customer if hybrid.                  |
| Shared catalog behavior    | Allowed buyer, restricted buyer, company-specific product visibility, and buyer-specific pricing.                                       |
| Product architecture       | Configurable product, child SKU, bundle or grouped product, downloadable product, custom-option product, and high-value simple product. |
| Scope behavior             | Different website, store, store view, language, region, brand, or channel contexts.                                                     |
| Content and campaign pages | CMS Pages, CMS blocks, Blog Posts, campaign pages, localized pages, and launch-critical pages.                                          |
| URLs and SEO               | Priority product URL, category URL, CMS Page path, Blog Post path, redirect, and localized route.                                       |
| Inventory and fulfillment  | Multi-source product, backorder product, externally managed SKU, and launch-critical SKU.                                               |
| Custom or integration data | ERP ID, PIM ID, CRM account reference, warehouse code, custom field, extension-owned value, or external reporting key.                  |

The sample list should be used to evaluate whether the selected service path can support the migration scope. If sample records reveal unsupported structures, missing relationships, or unhandled custom logic, adjust the plan before Full Migration.

### Decide Which Items Need Add-ons or Custom Service Review <a href="#decide-which-items-need-add-ons-or-custom-service-review" id="decide-which-items-need-add-ons-or-custom-service-review"></a>

Adobe Commerce preparation should end with a clear service-scope classification. Not every issue requires Custom Service, and not every field mapping should become a custom project. The preparation output should identify which needs fit standard migration configuration, which need Add-ons, and which need Custom Service review.

Use this decision pattern:

| Requirement                                                                                                                                                                                         | Planning direction                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Standard products, customers, orders, categories, CMS Pages, and Blog Posts within supported migration path coverage.                                                                               | Prepare for Standard Service or Managed Service depending on execution responsibility. |
| Supported fields that need more precise mapping or configuration.                                                                                                                                   | Review Advanced Data Mapping or Advanced Data Configure.                               |
| Selected records, date ranges, categories, order statuses, buyer segments, or other scoped migration needs.                                                                                         | Review Data Filter Add-on.                                                             |
| Standard migration plus Next-Cart-led execution and operational assistance.                                                                                                                         | Review Managed Service or Expert Handle scope.                                         |
| Company-account structures, shared-catalog requirements, extension-owned data, external identifiers, custom fields, unsupported source behavior, or transformation logic outside standard coverage. | Review Custom Service before Full Migration.                                           |

This classification should be documented before service purchase or before the migration configuration is finalized. It helps keep Adobe Commerce preparation practical: enough detail to avoid under-scoping, but not so much that every business preference is treated as a custom requirement.

### Preparation Checklist Before Full Migration <a href="#preparation-checklist-before-full-migration" id="preparation-checklist-before-full-migration"></a>

Use the final checklist to decide whether the Adobe Commerce migration is ready to proceed.

| Readiness item         | Pass condition                                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Operating model        | B2B, B2C, hybrid, regional, brand, storefront, and integration expectations are documented.                                          |
| Storefront scope       | Websites, stores, store views, languages, domains, and buyer segments are mapped.                                                    |
| Company accounts       | Company administrators, company users, roles, permissions, credit behavior, quote behavior, and purchase order needs are identified. |
| Shared catalogs        | Company assignment, product visibility, and buyer-specific pricing samples are ready for review.                                     |
| Product architecture   | Product types, configurable relationships, attributes, attribute sets, categories, and merchandising fields are sampled.             |
| Content and URLs       | High-value CMS Pages, Blog Posts, campaign pages, URL rewrites, redirects, and localized paths are documented.                       |
| Inventory              | Stock ownership, stock-source behavior, launch timing, and inventory samples are prepared.                                           |
| Integrations           | ERP, PIM, CRM, WMS, tax, payment, shipping, marketplace, and reporting identifiers are classified.                                   |
| Service scope          | Standard migration items, Add-on needs, and Custom Service candidates are separated.                                                 |
| Access and recovery    | Access, backups, security controls, ownership contacts, and migration windows are ready.                                             |
| Demo Migration samples | Representative B2B, catalog, scope, content, inventory, URL, and custom-data examples are selected.                                  |

A migration should not proceed into Full Migration only because records are ready to transfer. It should proceed when the target structure, critical mapping assumptions, sample evidence, access, backups, and service-scope decisions are clear enough to support confident review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce preparation should create an enterprise migration operating plan before execution begins. The strongest preparation work confirms B2B company structure, shared catalogs, storefront scope, buyer-specific pricing, product architecture, attributes, content timing, URLs, inventory, integrations, extension data, custom fields, access, backups, and representative Demo Migration samples.

When these decisions are prepared before Full Migration, the Target Store is easier to review, service scope is easier to control, and Adobe Commerce-specific issues can be identified before they create launch risk.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for an Adobe Commerce migration?**

Start with the Target Store operating model. Confirm whether the launch depends on B2B, B2C, hybrid commerce, multiple websites, multiple store views, shared catalogs, buyer-specific pricing, or enterprise integrations. Those decisions affect every later preparation task.

**Why do company accounts and shared catalogs need early preparation?**

They control buyer access, purchasing authority, product visibility, and pricing. Customer records can migrate while company-level behavior remains incomplete if administrators, users, roles, permissions, shared catalog assignment, or negotiated pricing are not prepared.

**Should Content Staging and campaign data be migrated as standard content?**

Evergreen content may fit standard content handling, but scheduled campaign behavior usually needs launch-aware review. Campaign timing, CMS blocks, price rules, landing pages, and region-specific visibility should be documented before migration configuration.

**When should Add-ons be considered during Adobe Commerce preparation?**

Add-ons should be considered when supported data needs defined filtering, mapping, or configuration assistance. Custom Service should be reviewed when requirements involve unsupported extension data, external-system identifiers, custom modules, Custom Platform behavior, bespoke transformation, or custom logic.

**How do Additional Migration Options affect Adobe Commerce preparation?**

Additional Migration Options matter when data continues changing after the main migration activity. Preparation should identify which new products, customers, orders, CMS Pages, Blog Posts, pricing updates, inventory-sensitive records, or buyer assignments may need follow-up handling and renewed review.
