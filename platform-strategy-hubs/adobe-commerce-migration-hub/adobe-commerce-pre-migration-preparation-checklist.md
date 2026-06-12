# Adobe Commerce Pre-Migration Preparation Checklist

Preparing for Adobe Commerce migration is not only a data export task. Adobe Commerce can carry company-level purchasing controls, shared catalog visibility, scheduled commercial changes, multi-storefront scope, rich product architecture, inventory source logic, URL rewrite behavior, and integration-dependent workflows. Those structures need to be understood before migration begins, otherwise the new store may receive records without the operating rules that make those records usable.

The strongest preparation work defines what must be preserved, what should be simplified, what needs custom handling, and what can be validated later through Demo Migration. For Adobe Commerce, preparation should produce evidence: company-account lists, shared catalog assignments, product-attribute decisions, source-to-scope mapping, URL priority lists, extension-data classifications, integration identifiers, and a clear service-path decision.

A prepared Adobe Commerce migration plan should answer one question before data is moved: will the target store be ready to represent the merchant’s commercial model, not just its database contents?

### Adobe Commerce Preparation Summary <a href="#adobe-commerce-preparation-summary" id="adobe-commerce-preparation-summary"></a>

| Preparation area                     | What to prepare                                                                                                                                             | Why it matters                                                                                               |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| B2B company structure                | Companies, administrators, users, roles, credit settings, quote permissions, purchase orders, payment methods, shipping methods, and approval requirements. | B2B migration can fail even when customer records exist if company-level purchasing controls are incomplete. |
| Shared catalogs                      | Company assignments, customer group relationships, product visibility, contracted products, and custom pricing requirements.                                | Shared catalogs determine what selected buyers can see and what prices they receive.                         |
| Website, store, and store-view scope | Source storefronts, languages, regions, brands, B2B/B2C channels, content variants, and configuration assumptions.                                          | Scope affects where catalog, content, customer, URL, and configuration decisions are reviewed.               |
| Product architecture                 | Product types, configurable relationships, child SKUs, bundles, downloadable products, attributes, attribute sets, and merchandising fields.                | Products must behave correctly in Adobe Commerce, not merely exist as imported records.                      |
| Inventory and fulfillment            | Source quantities, source locations, stock assignments, salable quantity expectations, backorder logic, and fulfillment rules.                              | Adobe Commerce inventory planning may require more than a single stock quantity field.                       |
| Content and staging                  | Current CMS Pages, CMS blocks, promotional content, scheduled campaigns, price rules, and future-dated changes.                                             | Scheduled commercial behavior may need recreation instead of simple content transfer.                        |
| URL and SEO continuity               | Product, category, CMS Page, and custom URL routes, plus high-value redirects and known route conflicts.                                                    | SEO preservation depends on deciding which routes must remain stable or redirect cleanly.                    |
| Extensions and integrations          | Extension-owned fields, ERP/PIM/CRM identifiers, payment and shipping dependencies, and custom workflow logic.                                              | Unsupported or outside-system logic may require Custom Service instead of standard field mapping.            |

### Define the Target Adobe Commerce Operating Model First <a href="#define-the-target-adobe-commerce-operating-model-first" id="define-the-target-adobe-commerce-operating-model-first"></a>

Adobe Commerce preparation should begin with the target operating model, not the export file. Merchants should decide how the new Adobe Commerce environment is expected to operate at launch: B2C only, B2B only, hybrid B2B/B2C, multi-brand, multi-region, multilingual, wholesale plus retail, or enterprise storefront with staged campaigns and external systems.

That decision controls the rest of preparation. A B2B-heavy store needs stronger company-account and shared-catalog preparation. A multi-region store needs careful website, store, and store-view mapping. A catalog with complex variants needs product-architecture review. A store connected to ERP, PIM, warehouse, tax, payment, and procurement systems needs integration identifier preservation.

Before migration begins, prepare a short operating-model brief with:

| Decision             | Required preparation evidence                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Storefront structure | Intended websites, stores, store views, languages, regional storefronts, and channel boundaries.                                       |
| Buyer model          | Retail customers, company buyers, company administrators, purchasing teams, approval users, and mixed-account behavior.                |
| Pricing model        | Base pricing, customer group pricing, tier pricing, shared catalog pricing, contract pricing, and promotional rules.                   |
| Catalog model        | Product types, variants, attribute sets, categories, merchandising attributes, visibility rules, and downloadable or bundled products. |
| Fulfillment model    | Inventory sources, stock assignment, sales channels, warehouses, backorders, and external fulfillment dependencies.                    |
| Integration model    | External identifiers, ERP/PIM/CRM relationships, payment and shipping dependencies, and custom workflow triggers.                      |

A migration path should not be selected until this operating model is clear enough to distinguish standard records from business-critical rules.

### Prepare B2B Company Accounts and Buyer Relationships <a href="#prepare-b2b-company-accounts-and-buyer-relationships" id="prepare-b2b-company-accounts-and-buyer-relationships"></a>

Adobe Commerce B2B preparation must go beyond a customer export. Company accounts can carry purchasing structure, administrators, users, credit settings, approval requirements, quote permission, purchase order permission, payment method availability, shipping method availability, customer group assignment, and shared catalog access. If those relationships are not prepared, migrated buyers may be able to log in but still fail to purchase correctly.

Prepare a company-account inventory with the following fields where applicable:

| Company preparation item                     | Preparation question                                                                                      |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Company identity                             | Which source accounts represent companies rather than individual retail customers?                        |
| Company administrator                        | Which user should administer each company account after migration?                                        |
| Company users                                | Which buyers belong to each company, department, branch, or purchasing unit?                              |
| Role and approval logic                      | Which users can browse, request quotes, create orders, approve purchases, or administer other users?      |
| Credit and payment controls                  | Which companies have credit terms, credit limits, allowed payment methods, or restricted payment methods? |
| Shipping controls                            | Which shipping methods are allowed or restricted for each company?                                        |
| Customer group and shared catalog assignment | Which group or shared catalog should govern buyer visibility and pricing?                                 |
| External identifiers                         | Which company, buyer, ERP, account manager, or procurement IDs must remain traceable?                     |

If the source platform does not have native company accounts, identify how B2B data is represented. It may be stored as customer tags, groups, roles, custom fields, notes, app metadata, wholesale tables, contract-price records, or external ERP data. That classification determines whether the migration can stay inside a standard service path or requires Custom Service planning.

### Prepare Shared Catalog Visibility and Pricing <a href="#prepare-shared-catalog-visibility-and-pricing" id="prepare-shared-catalog-visibility-and-pricing"></a>

Shared catalogs require separate preparation because product existence does not prove buyer access. A company may need to see a restricted product assortment, receive company-specific pricing, or be blocked from public catalog behavior. If shared catalog decisions are left until after migration, validation becomes difficult because reviewers cannot tell whether a visibility issue is a migration defect or an unfinished business rule.

Prepare shared catalog evidence before migration begins:

| Shared catalog item   | What to confirm                                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------- |
| Catalog list          | Which shared catalogs are needed at launch?                                                       |
| Company assignment    | Which companies belong to each shared catalog or related customer group?                          |
| Product assignment    | Which products must be visible in each shared catalog?                                            |
| Custom pricing        | Which prices are shared-catalog-specific, customer-group-specific, tier-based, or contract-based? |
| Visibility exceptions | Which buyers or companies need restricted, expanded, or temporary catalog access?                 |
| Launch priority       | Which companies and catalogs must be validated first after Demo Migration?                        |

When shared catalog data originates outside the source store, such as in ERP or contract-pricing systems, document that dependency early. A standard product and customer transfer cannot preserve pricing logic that never existed inside the source platform’s exportable commerce data.

### Map Websites, Stores, and Store Views Before Export <a href="#map-websites-stores-and-store-views-before-export" id="map-websites-stores-and-store-views-before-export"></a>

Adobe Commerce scope preparation should happen before entity mapping. Websites, stores, and store views can affect product visibility, content, configuration, customer behavior, language, region, and buyer experience. A source platform may represent these same differences through multiple stores, domains, markets, channels, languages, apps, or duplicated content.

Create a scope map before migration:

| Source condition              | Adobe Commerce planning decision                                                                                        |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Multiple domains              | Decide whether each domain maps to a website, store, store view, or URL configuration.                                  |
| Multiple languages            | Decide which content and catalog values belong to each store view.                                                      |
| Regional storefronts          | Decide whether regions require separate websites, stores, currency behavior, tax assumptions, or catalog visibility.    |
| Wholesale and retail channels | Decide whether B2B and B2C should be separated by website, store, customer group, shared catalog, or another mechanism. |
| Brand-specific stores         | Decide how brand categories, content, URLs, and product assignments should be scoped.                                   |
| Duplicated product fields     | Decide which values are global and which need store-view-level variation.                                               |

This scope map also protects validation. Reviewers should know which website, store, store view, company account, customer group, and catalog context to use when approving migrated data.

### Prepare Product Types, Attributes, and Attribute Sets <a href="#prepare-product-types-attributes-and-attribute-sets" id="prepare-product-types-attributes-and-attribute-sets"></a>

Adobe Commerce product preparation should focus on target behavior. The source catalog may contain products, variants, options, bundles, downloads, subscriptions, add-ons, personalization fields, or custom product builders. Those structures need to be interpreted before migration so the target store does not end up with technically imported products that are difficult to filter, price, maintain, or purchase.

Prepare catalog decisions in three layers.

#### Product-type decisions <a href="#product-type-decisions" id="product-type-decisions"></a>

Identify which source products should become simple, configurable, grouped, bundle, virtual, downloadable, or another supported Adobe Commerce product structure. Pay special attention to source variants. Configurable products depend on child simple products with distinct SKUs, so weak source SKU discipline can create migration and validation problems.

#### Attribute and attribute-set decisions <a href="#attribute-and-attribute-set-decisions" id="attribute-and-attribute-set-decisions"></a>

Review whether source fields should become product attributes, merchandising fields, filterable values, searchable values, comparison values, reporting fields, or non-catalog metadata. Attribute sets should be planned before large product batches are migrated, especially when the catalog spans unrelated product families.

#### Category and visibility decisions <a href="#category-and-visibility-decisions" id="category-and-visibility-decisions"></a>

Prepare category paths, navigation visibility, product assignments, and cross-storefront visibility rules. Do not treat categories only as labels. In Adobe Commerce, category structure affects browsing, navigation, merchandising, URL planning, and reviewer expectations.

A useful product-preparation worksheet should include:

| Catalog item                  | Required decision                                                         |
| ----------------------------- | ------------------------------------------------------------------------- |
| Product type                  | Which Adobe Commerce product type should represent the source product?    |
| Parent-child relationship     | Which simple products belong under each configurable product?             |
| SKU integrity                 | Are child SKUs unique, complete, and ready for post-migration operations? |
| Attribute set                 | Which attribute set should govern each product family?                    |
| Search and layered navigation | Which attributes should influence discovery and filtering?                |
| Category placement            | Which categories should contain each product at launch?                   |
| Store-view variation          | Which product fields vary by language, storefront, region, or brand?      |

### Prepare Inventory and Fulfillment Assumptions <a href="#prepare-inventory-and-fulfillment-assumptions" id="prepare-inventory-and-fulfillment-assumptions"></a>

Adobe Commerce inventory preparation should not assume that every source quantity becomes one stock field. Inventory Management can involve sources, stocks, sales channels, salable quantity, reservations, and fulfillment assumptions. A merchant moving from a simpler platform may need to decide whether Adobe Commerce should represent one warehouse, multiple warehouses, store pickup locations, supplier feeds, regional stock, or external fulfillment systems.

Prepare these inventory decisions before migration:

| Inventory question                                            | Why it matters                                                                                         |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| How many physical or logical inventory sources exist?         | Source count affects whether inventory should be mapped as one quantity or multiple source quantities. |
| Which sources support which sales channels?                   | Stock assignment can affect what is saleable by website or channel.                                    |
| Are backorders, safety stock, or reservations relevant?       | Available-to-sell behavior may differ from raw quantity.                                               |
| Does a fulfillment system control final inventory truth?      | External systems may need identifier preservation and staged synchronization.                          |
| Should historical order quantities influence inventory setup? | Order history is not the same as current stock availability.                                           |

If inventory truth lives outside the source platform, such as in ERP, WMS, POS, or marketplace systems, prepare the integration dependency rather than treating the source store as authoritative.

### Prepare Content, Campaigns, and Staged Updates <a href="#prepare-content-campaigns-and-staged-updates" id="prepare-content-campaigns-and-staged-updates"></a>

Adobe Commerce content preparation should separate current publishable content from timed commercial behavior. CMS Pages, CMS blocks, landing pages, category content, promotional banners, price rules, and campaign assets may exist in the source platform, but Adobe Commerce Content Staging introduces a separate question: what should exist now, and what future-dated change should be scheduled, recreated, or excluded from migration?

Create a content and staging inventory with:

| Content or campaign item     | Preparation decision                                                                       |
| ---------------------------- | ------------------------------------------------------------------------------------------ |
| CMS Pages and CMS blocks     | Which content should migrate as current live content?                                      |
| Category and product content | Which descriptions, images, merchandising text, and SEO fields need scope-level variation? |
| Scheduled promotions         | Which future campaigns must be recreated rather than imported as static content?           |
| Price rules                  | Which active or future price rules are required for launch?                                |
| Landing pages                | Which campaign pages need URL preservation, redirect planning, or redesign?                |
| Retired content              | Which outdated pages should be excluded or redirected?                                     |

Do not migrate every historical campaign artifact by default. Prioritize content that affects launch, SEO continuity, merchandising, buyer trust, or active commercial commitments.

### Prepare URLs, Redirects, and SEO-Critical Routes <a href="#prepare-urls-redirects-and-seo-critical-routes" id="prepare-urls-redirects-and-seo-critical-routes"></a>

URL preparation should produce a prioritized route list before migration. Adobe Commerce URL rewrites can preserve or redirect product, category, CMS Page, and custom routes, but merchants still need to decide which URLs matter most and where they should resolve in the new store.

Prepare a URL worksheet with:

| URL group                     | Preparation action                                                             |
| ----------------------------- | ------------------------------------------------------------------------------ |
| Top product URLs              | Confirm whether each route should be preserved or redirected.                  |
| Top category URLs             | Map old category paths to new navigation paths.                                |
| CMS Pages and landing pages   | Decide whether pages migrate, merge, redirect, or retire.                      |
| Custom routes                 | Identify routes created by extensions, landing-page builders, or integrations. |
| Multistore URLs               | Confirm route behavior by website, store, store view, language, and domain.    |
| Known duplicates or conflicts | Decide canonical routes before migration.                                      |

High-value SEO routes should be validated during Demo Migration. Lower-value or obsolete routes can be handled through redirect strategy rather than full content preservation.

### Prepare Extensions, Integrations, and Custom Logic <a href="#prepare-extensions-integrations-and-custom-logic" id="prepare-extensions-integrations-and-custom-logic"></a>

Adobe Commerce projects often depend on extensions, custom modules, middleware, ERP/PIM/CRM systems, payment providers, shipping logic, tax systems, procurement platforms, and external reporting. Some data may be visible in the Admin but owned by an extension or outside system. Some identifiers may not affect storefront display but are critical for ongoing operations.

Before migration, classify each non-standard field or workflow:

| Classification                    | Example                                                                                                | Likely handling                                                                           |
| --------------------------------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Standard entity field             | Product name, base price, customer email, category name.                                               | Standard Service may be enough if the field is supported for the selected migration path. |
| Mapping or configuration need     | Source value needs target attribute, category, status, or customer-group alignment.                    | Add-ons such as Advanced Data Mapping or Advanced Data Configure may be appropriate.      |
| Filter or selective-transfer need | Only selected products, customers, categories, or orders should be transferred.                        | Data Filter Add-on may be appropriate.                                                    |
| Extension-owned data              | Custom product builder fields, loyalty data, B2B app data, marketplace fields, custom checkout states. | Usually requires Custom Service evaluation.                                               |
| Outside-system identifier         | ERP customer ID, PIM product ID, WMS location ID, procurement account ID.                              | May require Custom Service or integration-aware planning.                                 |
| Custom workflow logic             | Approval behavior, order routing, contract-pricing rules, external validation, bespoke API behavior.   | Requires Custom Service evaluation and possibly post-migration implementation planning.   |

Add-ons should be used for supported filtering, mapping, and configuration requirements. Custom Service should be considered when the migration depends on bespoke structures, unsupported extension data, outside-system identifiers, Custom Platform interpretation, or custom logic that cannot be handled by standard service configuration.

### Prepare the Service Path and Entity Points Plan <a href="#prepare-the-service-path-and-entity-points-plan" id="prepare-the-service-path-and-entity-points-plan"></a>

Adobe Commerce preparation should end with a service-path decision. The number of products, customers, orders, categories, CMS Pages, Blog Posts, and other supported entities affects the Entity Points Plan. But entity count is not the only planning factor. B2B controls, shared catalogs, scoped content, staged updates, extension data, inventory sources, and external identifiers can be more important than volume.

Use this decision table before purchasing or confirming the service license:

| Migration condition                                                                                                                                               | Recommended planning direction                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Standard catalog, customers, orders, categories, and content with supported fields and limited custom logic.                                                      | Standard Service may be appropriate.                                       |
| Merchant wants Next-Cart to perform or supervise more of the migration process within a supported path.                                                           | Managed Service may be appropriate, depending on the agreed service scope. |
| Migration requires selective transfer, field mapping, or data configuration within supported service capabilities.                                                | Review Add-ons before treating the request as custom development.          |
| B2B company structure, shared catalogs, custom pricing, extension-owned data, or outside-system identifiers must be preserved beyond supported standard handling. | Custom Service evaluation is required.                                     |
| A recent migration has already completed and new source activity must be synchronized before launch.                                                              | Recent Data Migration may be needed.                                       |
| A previous migration must be performed again after additional preparation, cleanup, mapping, or configuration changes.                                            | Re-Migration may be needed.                                                |

Preparation should also identify who will perform each responsibility: the merchant, Next-Cart under the agreed service model, implementation partner, Adobe Commerce developer, agency, ERP/PIM team, or internal operations team. Custom Service does not automatically mean Next-Cart executes the full migration project; responsibility depends on the final agreed plan.

### Preparation Pass Conditions <a href="#preparation-pass-conditions" id="preparation-pass-conditions"></a>

Adobe Commerce preparation is complete enough to start migration when the project can pass these checks:

| Pass condition                                    | Evidence                                                                                                                                |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Target operating model is defined                 | B2B/B2C model, storefront structure, catalog model, fulfillment model, and integration responsibilities are documented.                 |
| Company and shared catalog requirements are known | Company accounts, users, roles, credit rules, quote/purchase order needs, catalog assignments, and custom pricing needs are identified. |
| Scope mapping is complete                         | Source storefronts, languages, regions, brands, and channels have target website/store/store-view decisions.                            |
| Product architecture is ready                     | Product types, child SKUs, attributes, attribute sets, categories, and visibility rules are prepared.                                   |
| Inventory assumptions are documented              | Sources, stocks, sales-channel assignment, salable quantity expectations, and external inventory dependencies are known.                |
| URLs are prioritized                              | Product, category, CMS Page, landing-page, and custom route priorities are ready for redirect planning.                                 |
| Custom logic is classified                        | Add-ons and Custom Service needs are separated before migration begins.                                                                 |
| Demo Migration review path is clear               | Reviewers know which entities, buyer contexts, storefront scopes, URLs, and sample records must be checked first.                       |

When these conditions are not met, starting migration too early usually creates rework. The better choice is to finish preparation, run a smaller Demo Migration sample, and use the result to confirm the target structure before continuing toward Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration preparation is the control layer for the entire project. It determines whether source data can become a working Adobe Commerce operating model with correct B2B access, shared catalog visibility, scoped storefront behavior, product architecture, inventory logic, SEO continuity, and integration traceability.

A well-prepared Adobe Commerce migration does not attempt to move every record immediately. It first defines the target structure, classifies complex requirements, separates Add-ons from Custom Service needs, and gives Demo Migration a clear validation path.

Start Adobe Commerce migration planning by documenting the target operating model, company and shared catalog requirements, scope structure, product architecture, inventory assumptions, URL priorities, and custom-data dependencies before selecting the final service path.

### FAQs <a href="#faqs" id="faqs"></a>

**Do Adobe Commerce company accounts need special preparation before migration?**

Yes. Company accounts can involve administrators, users, credit settings, quote access, purchase orders, payment and shipping permissions, customer group assignment, and shared catalog access. Preparing only customer emails and addresses is not enough for many B2B migrations.

**Should shared catalogs be prepared before or after migration?**

Shared catalog requirements should be prepared before migration. Company assignment, product visibility, and custom pricing decisions affect both migration planning and validation. Waiting until after data transfer can make pricing or visibility issues harder to diagnose.

**What should be prepared for Adobe Commerce scope mapping?**

Prepare the source storefronts, domains, languages, regional stores, wholesale or retail channels, brand-specific stores, and content variations. Each should have a target website, store, store-view, customer-group, shared-catalog, or configuration decision before validation begins.

**Does Adobe Commerce preparation require a full extension audit?**

It requires enough extension and custom-logic review to identify data that is not part of standard supported entities. Extension-owned fields, ERP identifiers, custom checkout states, contract-pricing rules, or app-specific records may require Custom Service evaluation.

**When should Recent Data Migration or Re-Migration be considered?**

Recent Data Migration should be considered when the source store continues receiving new records after the main migration. Re-Migration should be considered when the migration must be performed again after cleanup, mapping changes, configuration changes, or a corrected target setup.
