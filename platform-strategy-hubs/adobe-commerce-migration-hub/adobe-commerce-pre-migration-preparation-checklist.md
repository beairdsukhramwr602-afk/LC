# Adobe Commerce Pre-Migration Preparation Checklist

Adobe Commerce preparation should define how the Target Store must operate before data is moved. The platform can represent enterprise storefront scope, B2B company relationships, shared catalogs, governed pricing, Content Staging, integrations, inventory sources, URL rules, and complex product architecture. Those decisions affect whether migrated records are usable after launch.

A strong preparation phase produces evidence that can guide configuration, Demo Migration review, service-path selection, and final validation. For Adobe Commerce, that evidence should include company-account samples, shared catalog assignments, storefront-scope decisions, product-architecture examples, URL priorities, integration identifiers, content-timing notes, and a clear list of items that may require Add-ons or Custom Service review.

Preparation is not a guarantee that every business rule will migrate automatically. It is the step that separates standard data transfer from target-side configuration, Add-on-supported mapping, and custom handling before migration begins.

### Preparation Priorities for Adobe Commerce <a href="#preparation-priorities-for-adobe-commerce" id="preparation-priorities-for-adobe-commerce"></a>

| Preparation area            | What to prepare                                                                                                                                                             | Why it matters                                                                                                        |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Target operating model      | B2B, B2C, hybrid, multi-brand, multi-region, wholesale, retail, marketplace, or integration-led operating expectations.                                                     | The target operating model controls how migrated data should behave in Adobe Commerce.                                |
| Storefront scope            | Websites, stores, store views, languages, regions, domains, brands, customer segments, and channel boundaries.                                                              | Scope decisions affect catalog visibility, content, URLs, pricing context, and validation samples.                    |
| B2B company data            | Companies, administrators, users, roles, permissions, credit settings, payment rules, shipping rules, quote behavior, and purchase order expectations.                      | B2B success depends on buyer relationships and purchasing controls, not only customer records.                        |
| Shared catalogs and pricing | Company assignments, customer groups, product visibility, tier prices, contracted prices, and restricted assortments.                                                       | Buyers may see different products or prices depending on company, group, or storefront context.                       |
| Product architecture        | Product types, configurable relationships, child SKUs, bundles, grouped products, downloadable products, attributes, attribute sets, categories, and merchandising fields.  | Products must remain purchasable, maintainable, searchable, and usable in Adobe Commerce.                             |
| Inventory and fulfillment   | Stock sources, sales channels, salable quantity expectations, warehouses, reservations, backorders, and external fulfillment ownership.                                     | Quantity alone may not represent how Adobe Commerce should determine availability after launch.                       |
| Content and campaigns       | CMS Pages, CMS blocks, Blog Posts, promotional content, price rules, scheduled updates, campaign pages, and launch-sensitive content.                                       | Time-sensitive content may need recreation, configuration, or launch-specific validation rather than simple transfer. |
| URLs and SEO                | Product URLs, category URLs, CMS Page paths, Blog Post paths, URL rewrites, redirects, canonical routes, localized paths, and high-value landing pages.                     | SEO continuity depends on preserving or redirecting the routes that matter most.                                      |
| Extensions and integrations | Extension-owned fields, custom modules, ERP/PIM/CRM identifiers, payment and shipping dependencies, warehouse references, tax fields, subscription IDs, and reporting keys. | External systems may depend on values that are not obvious during storefront review.                                  |

### Define the Target Operating Model Before Mapping Data <a href="#define-the-target-operating-model-before-mapping-data" id="define-the-target-operating-model-before-mapping-data"></a>

Adobe Commerce preparation should begin with the intended Target Store model. A merchant should know whether the launch environment is expected to support B2C commerce, B2B commerce, hybrid B2B/B2C operations, multiple brands, multiple regions, multiple languages, wholesale purchasing, distributor portals, staged campaigns, or enterprise integrations.

This decision changes how the migration should be reviewed. A B2B-heavy store needs deeper company-account and shared-catalog preparation. A multi-region store needs scope mapping across websites, stores, and store views. A complex catalog needs product-architecture samples. An integration-heavy store needs external identifiers and ownership rules documented before Full Migration.

Prepare a short operating-model brief with these decisions:

| Operating decision   | Preparation evidence                                                                                                                     |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Storefront structure | Intended websites, stores, store views, languages, regions, brands, domains, and business channels.                                      |
| Buyer model          | Retail customers, company accounts, company administrators, purchasing users, approvers, and mixed-account behavior.                     |
| Pricing model        | Base pricing, customer group pricing, tier pricing, shared catalog pricing, contract pricing, quote expectations, and promotional rules. |
| Catalog model        | Product types, variants, bundles, grouped products, attributes, attribute sets, categories, visibility rules, and merchandising fields.  |
| Fulfillment model    | Inventory sources, stocks, warehouses, pickup locations, backorder rules, reservations, and external fulfillment systems.                |
| Integration model    | ERP, PIM, CRM, WMS, payment, shipping, tax, analytics, marketplace, and reporting identifiers that must remain traceable.                |

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
| Credit and payment rules                     | Which companies have credit limits, terms, allowed payment methods, restricted payment methods, or purchase order expectations?                 |
| Shipping controls                            | Which shipping methods are allowed, restricted, or company-specific?                                                                            |
| Customer group and shared catalog assignment | Which customer group or shared catalog should control visibility and pricing for each company?                                                  |
| External identifiers                         | Which company IDs, ERP account IDs, dealer IDs, procurement IDs, sales-representative IDs, or account-manager references must remain traceable? |

If the source platform does not have native company accounts, identify where B2B meaning is stored. It may appear as customer groups, customer tags, custom fields, app metadata, wholesale records, ERP account codes, price-list references, or notes. When these values are outside standard source data, they may require Add-ons, Custom Add-ons, or Custom Service review.

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

| Source condition              | Adobe Commerce planning decision                                                                                        |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Multiple domains              | Decide whether each domain maps to a website, store, store view, or URL configuration.                                  |
| Multiple languages            | Decide which product values, category values, CMS Pages, Blog Posts, and metadata belong to each store view.            |
| Regional storefronts          | Decide whether regions require separate websites, stores, currencies, catalogs, tax assumptions, or content variants.   |
| Wholesale and retail channels | Decide whether B2B and B2C should be separated by website, store, customer group, shared catalog, or another mechanism. |
| Brand-specific storefronts    | Decide how brand catalogs, brand categories, localized content, and brand URLs should appear in the Target Store.       |
| Customer-segment differences  | Decide whether visibility belongs to shared catalogs, customer groups, configuration, or custom rules.                  |

Scope mapping should also identify which sample records are required for validation. A single product, customer, category, or page sample is rarely enough when the launch environment has multiple storefront contexts.

### Prepare Product Architecture and Attribute Governance <a href="#prepare-product-architecture-and-attribute-governance" id="prepare-product-architecture-and-attribute-governance"></a>

Adobe Commerce catalog preparation should define how source products should become maintainable target products. Product type, attribute structure, attribute set design, SKU relationships, category assignment, inventory behavior, pricing rules, and merchandising fields all affect daily store operations.

Prepare representative samples for each product structure that matters:

| Product structure                | Preparation evidence                                                                                                                       |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Simple products                  | SKU, name, price, stock, URL key, category assignment, image, tax class, status, visibility, and required attributes.                      |
| Configurable products            | Parent SKU, child SKUs, option labels, option values, attribute relationships, images, prices, stock behavior, and category visibility.    |
| Bundle or grouped products       | Component SKUs, quantities, price behavior, purchasability, inventory assumptions, and storefront display.                                 |
| Downloadable or virtual products | File delivery, license behavior, fulfillment expectation, order history meaning, and customer access requirements.                         |
| Attributes                       | Required fields, filterable fields, searchable fields, comparison fields, operational fields, integration fields, and display-only fields. |
| Attribute sets                   | Product-family grouping, required-field logic, admin maintenance needs, and validation samples.                                            |
| Categories                       | Navigation paths, storefront scope, URL behavior, merchandising position, and parent-child relationships.                                  |

Do not treat every source field as an Adobe Commerce attribute by default. Some fields are display content. Some control search, filters, rules, pricing, reporting, or integration behavior. Others may be obsolete. Attribute governance should reduce clutter while preserving operational meaning.

### Prepare Inventory and Fulfillment Assumptions <a href="#prepare-inventory-and-fulfillment-assumptions" id="prepare-inventory-and-fulfillment-assumptions"></a>

Inventory preparation should identify how Adobe Commerce should decide whether a product is available to sell. A source store may provide one stock quantity, while the Target Store may need source-level inventory, stock assignments, website-level salability, warehouse logic, pickup locations, backorders, reservations, or ERP-managed stock.

Prepare inventory evidence with these questions:

| Inventory question                                              | Why it matters                                                                                        |
| --------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Is inventory managed inside the store or by an external system? | External ownership can change whether migrated quantities are launch baselines or ongoing truth.      |
| Does the business use one warehouse or multiple sources?        | Multiple sources may require additional configuration and validation samples.                         |
| Which products allow backorders or special ordering?            | Availability behavior can differ from raw quantity.                                                   |
| Which channels can sell each stock source?                      | Stock assignment may depend on website, region, brand, or fulfillment policy.                         |
| Which SKUs are launch-critical?                                 | High-priority products should be validated before go-live.                                            |
| Will inventory be refreshed close to launch?                    | Late source-store activity may require an Additional Migration Option or separate operational update. |

If inventory data is overwritten by ERP, WMS, supplier feeds, marketplace systems, or implementation-side scripts, document those systems before migration scope is finalized. Migrating quantities without ownership context can create false confidence.

### Prepare Content, Campaigns, and Staging Requirements <a href="#prepare-content-campaigns-and-staging-requirements" id="prepare-content-campaigns-and-staging-requirements"></a>

Adobe Commerce content preparation should distinguish stable content from launch-sensitive or time-sensitive content. CMS Pages, CMS blocks, Blog Posts, banners, campaign pages, category descriptions, product content, catalog price rules, cart price rules, and scheduled updates may all influence launch readiness.

Classify content into four groups:

| Content group                   | Preparation action                                                                              |
| ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Evergreen content               | Prepare for migration and standard validation.                                                  |
| Launch-critical content         | Prioritize in Demo Migration review and pre-launch checks.                                      |
| Time-sensitive campaign content | Decide whether timing should be recreated, configured, or manually rebuilt in the Target Store. |
| Legacy or expired content       | Exclude, archive, or deprioritize if it is not needed for launch.                               |

Content Staging adds another planning question: whether the merchant needs the current visible state only or also future scheduled states. If the future state must be preserved, the project may need custom handling or implementation-side recreation, depending on where the scheduled logic exists in the source data.

### Prepare URL and SEO Priority Lists <a href="#prepare-url-and-seo-priority-lists" id="prepare-url-and-seo-priority-lists"></a>

URL preparation should focus on business value and continuity risk, not only total page count. Adobe Commerce migration can involve product URL keys, category URL keys, CMS Page paths, Blog Post paths, URL rewrites, redirect chains, canonical routes, localized routes, brand routes, and campaign landing pages.

Prepare a URL priority list with these groups:

| URL group                     | Preparation focus                                                               |
| ----------------------------- | ------------------------------------------------------------------------------- |
| Top organic landing pages     | Preserve or redirect routes that carry search traffic.                          |
| Revenue-driving product pages | Confirm product URL keys, category paths, redirects, and canonical behavior.    |
| Priority category pages       | Validate navigation, category URLs, metadata, and high-value redirects.         |
| B2B portal routes             | Confirm company-specific access paths, restricted pages, and buyer-facing URLs. |
| CMS Pages and Blog Posts      | Confirm static content paths, localized routes, and old-to-new redirect needs.  |
| Campaign landing pages        | Decide whether pages should migrate, redirect, expire, or be recreated.         |

A URL list should include the current source URL, desired Target Store URL, redirect requirement, language or region context, page type, and launch priority. This creates a validation baseline for Article 7 and launch readiness checks in Section 7.

### Prepare Extension, Integration, and Custom Data Classifications <a href="#prepare-extension-integration-and-custom-data-classifications" id="prepare-extension-integration-and-custom-data-classifications"></a>

Adobe Commerce projects often depend on data that standard storefront review cannot reveal. External identifiers, custom modules, extension-owned fields, app-specific records, ERP references, PIM product IDs, warehouse codes, CRM account IDs, tax fields, subscription references, loyalty values, dealer IDs, contract numbers, marketplace references, and reporting keys may all matter after launch.

Classify each non-standard item before migration:

| Classification       | Meaning                                                                                               | Likely handling                                                                   |
| -------------------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Standard field       | The value fits a standard source and target field.                                                    | Standard Service may be enough, depending on migration path support.              |
| Mappable field       | The value exists in supported data but needs field-level mapping or configuration.                    | Add-ons such as Advanced Data Mapping or Advanced Data Configure may be relevant. |
| Filtered scope       | Only selected records or selected conditions should migrate.                                          | Data Filter Add-on may be relevant.                                               |
| Extension-owned data | The value is stored by an extension, custom module, app, or unsupported source structure.             | Custom Service review is usually safer.                                           |
| External-system data | The value is owned by ERP, PIM, CRM, warehouse, marketplace, tax, subscription, or reporting systems. | Custom Service or implementation-side coordination may be required.               |
| Custom logic         | The requirement depends on transformation, rule conversion, custom behavior, or bespoke workflow.     | Custom Service should be reviewed before migration begins.                        |

This classification helps prevent late surprises. When the requirement is identified before Demo Migration, the migration scope can be adjusted earlier. When it is found after Full Migration, the project may need rework, remapping, or additional service review.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

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
| Selected records, date ranges, categories, order statuses, or other scoped migration needs.                                                                                                         | Review Data Filter Add-on.                                                             |
| Standard migration plus Next-Cart-led execution and operational assistance.                                                                                                                         | Review Managed Service or Expert Handle scope.                                         |
| Company-account structures, shared-catalog requirements, extension-owned data, external identifiers, custom fields, unsupported source behavior, or transformation logic outside standard coverage. | Review Custom Service before Full Migration.                                           |

This classification should be documented before service purchase or before the migration configuration is finalized. It helps keep Adobe Commerce preparation practical: enough detail to avoid under-scoping, but not so much that every business preference is treated as a custom requirement.

### Preparation Checklist Before Full Migration <a href="#preparation-checklist-before-full-migration" id="preparation-checklist-before-full-migration"></a>

Before Full Migration, confirm that the preparation package includes:

* target operating-model brief;
* website, store, and store-view scope map;
* company-account and buyer-role inventory;
* shared catalog and pricing assignment notes;
* representative product-architecture samples;
* attribute and attribute-set decisions;
* inventory and fulfillment assumptions;
* content and campaign classification;
* URL and SEO priority list;
* integration and external-identifier inventory;
* extension, custom field, and custom logic classification;
* Demo Migration review sample list;
* Add-on and Custom Service review notes;
* final validation ownership and reviewer list.

If any of these items are incomplete, the migration may still begin, but the risk of post-migration ambiguity increases. The strongest Adobe Commerce migration plans make the target operating model visible before the result needs to be judged.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce preparation should turn enterprise complexity into reviewable migration inputs. Company accounts, shared catalogs, storefront scope, product architecture, inventory ownership, campaign timing, URLs, integrations, and custom data should be documented before migration configuration is treated as stable.

A well-prepared Adobe Commerce migration gives the customer and Next-Cart a clearer basis for service-path selection, Demo Migration review, Full Migration readiness, and final validation. The goal is not only to move records into Adobe Commerce, but to make sure those records can support the commercial model the Target Store is expected to operate.

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Does every Adobe Commerce migration need Custom Service?**

No. Some Adobe Commerce migrations fit standard supported structures, especially when products, customers, orders, categories, content, and URLs can be mapped without unsupported source logic or custom transformation. Custom Service becomes more important when company-account behavior, shared catalog logic, extension-owned data, external identifiers, or bespoke workflows must be preserved beyond standard coverage.

**Should B2B company accounts be prepared before Demo Migration?**

Yes. Company accounts, users, roles, permissions, shared catalog assignments, and pricing visibility should be prepared early because they influence how customer and catalog samples are reviewed. Without that context, Demo Migration may show migrated records without proving buyer usability.

**Are shared catalogs the same as product migration?**

No. Product migration confirms that product records exist in the Target Store. Shared catalog preparation confirms which companies or buyer groups should see specific products and prices. Both layers need review for Adobe Commerce B2B projects.

**Can URL planning wait until after Full Migration?**

It should not. Priority URLs, redirects, localized paths, product routes, category routes, CMS Page paths, and Blog Post paths should be prepared before launch validation. Late URL planning increases SEO and customer-continuity risk.

**What should be included in the Demo Migration sample set?**

The sample set should include records that represent Adobe Commerce risk: B2B company users, shared catalog visibility, complex products, scoped storefronts, priority URLs, content pages, inventory cases, and custom or integration-sensitive values.
