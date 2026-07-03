# Cafe24 Pre-Migration Preparation Checklist

Cafe24 migration preparation should make the future store easier to interpret before data starts moving. A Cafe24 project can involve more than product, customer, and order transfer because storefront design, modules, apps, APIs, webhooks, payment and shipping behavior, analytics, and integration services may all affect how the migrated store operates after launch.

The goal of preparation is not to configure every part of the Target Platform in advance. The goal is to identify what must be preserved, what should be rebuilt differently, what depends on Cafe24 configuration, and what requires deeper review before the migration process is treated as straightforward.

A strong preparation checklist should answer a practical question: when the Demo Migration is reviewed, will the merchant know what a good Cafe24 result is supposed to look like?

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Cafe24 preparation is most useful when it separates ordinary records from the operating context around those records. Products, categories, customers, and orders may be present after migration, but the result still needs to make sense inside Cafe24’s storefront, design, app, API, payment, shipping, and data ecosystem.

Preparation should help the merchant define:

| Preparation area                    | Why it matters before migration                                                                                                                                                     |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Storefront and market structure     | Cafe24 may be used for market-specific storefronts, design experiences, or selling contexts that need clear ownership before data is interpreted.                                   |
| Product and category meaning        | Product records, options, categories, display logic, and merchandising structure need to support how buyers will browse and purchase after launch.                                  |
| Design and module dependency        | Smart Design, Smart Themes, modules, web components, and scripts may shape what customers see beyond the migrated records themselves.                                               |
| App-owned behavior                  | Discount apps, shipping fee apps, payment gateway apps, and other app behavior can affect outcomes that standard record migration should not be expected to recreate automatically. |
| API, webhook, and data dependencies | API-connected systems, Data Bridge workflows, analytics feeds, and webhooks may control business outcomes outside ordinary article-level data.                                      |
| Order and customer context          | Order history must remain useful for service, accounting, fulfillment, and customer review, not merely appear as copied historical records.                                         |
| Custom source interpretation        | Custom Platform sources, modified source platforms, custom fields, or third-party data need to be explained before they can be translated safely.                                   |

The preparation work should give Next-Cart and the merchant a shared understanding of the expected result. Without that shared understanding, Demo Migration may show records that appear complete while still missing the context needed for launch decisions.

### Numbered Preparation Priorities <a href="#numbered-preparation-priorities" id="numbered-preparation-priorities"></a>

#### 1. Define the role of Cafe24 in the future operating model <a href="#id-1-define-the-role-of-cafe24-in-the-future-operating-model" id="id-1-define-the-role-of-cafe24-in-the-future-operating-model"></a>

Before migration, the merchant should clarify what Cafe24 is expected to become after launch. Some stores move to Cafe24 mainly for hosted e-commerce operations and storefront management. Others depend on Cafe24 because of its app ecosystem, design structure, APIs, Data Bridge, webhooks, or market-specific selling plans.

The preparation question is not only “what data should move?” It is “what role should Cafe24 play in the business after migration?”

A merchant should identify whether Cafe24 will be used as:

* the primary storefront and order-management environment
* a market-specific storefront for a certain region or buyer audience
* a storefront that depends on design customization and modules
* an app-connected commerce environment
* a store connected to external fulfillment, analytics, marketing, or operational systems
* a Target Platform that must receive data from a custom or heavily modified Source Platform

This role definition helps prevent later confusion. A simple storefront migration requires different preparation than a Cafe24 migration where apps, APIs, shipping behavior, payment gateways, and design modules are central to the expected result.

#### 2. Document storefront, language, market, and selling-context requirements <a href="#id-2-document-storefront-language-market-and-selling-context-requirements" id="id-2-document-storefront-language-market-and-selling-context-requirements"></a>

Cafe24 preparation should identify how the future storefront should be organized for customers. If the merchant serves multiple audiences, countries, brands, campaigns, or selling contexts, those expectations should be written down before migration begins.

The merchant should prepare notes on:

* which storefront or market contexts matter after launch
* whether product visibility differs by audience, market, or campaign
* which categories, landing pages, or content pages are business-critical
* which URLs, navigation paths, or search-engine results should be protected
* whether design or module behavior changes how products and content appear
* whether any language, currency, payment, or shipping expectation affects the migration outcome

This preparation does not require final design completion. It requires a clear enough target structure to judge whether migrated data fits Cafe24’s future storefront experience.

#### 3. Clean and classify product data before migration <a href="#id-3-clean-and-classify-product-data-before-migration" id="id-3-clean-and-classify-product-data-before-migration"></a>

Products should be reviewed before migration so Cafe24 does not inherit avoidable catalog confusion. Product data often contains a mix of sellable structure, display information, internal notes, discontinued records, SEO fields, app-owned references, and source-specific workarounds.

The merchant should identify:

* active products that should move
* products that should be excluded, archived, or reviewed separately
* categories and product groupings that should remain meaningful
* product options, variants, attributes, specifications, and labels that affect buying decisions
* product images and media that are required for launch readiness
* SEO titles, descriptions, slugs, or URL references that should be preserved or redirected
* app-owned or custom product data that may need Custom Service review

This is especially important if the Source Platform has accumulated duplicate products, inconsistent categories, inconsistent SKUs, or promotional products that are no longer part of the live business.

#### 4. Clarify category, navigation, and discovery expectations <a href="#id-4-clarify-category-navigation-and-discovery-expectations" id="id-4-clarify-category-navigation-and-discovery-expectations"></a>

Cafe24 category and navigation preparation should focus on how customers find products after migration. Source categories do not always translate into the ideal Cafe24 navigation structure. Some source stores use categories as merchandising groups, SEO landing pages, internal reporting buckets, or temporary campaign pages.

Before migration, the merchant should decide:

* which source categories should remain as categories
* which category structures should be simplified
* which campaign or seasonal categories should be retired
* which navigation paths are important for buyers
* which category URLs or landing pages matter for SEO continuity
* which products should appear in multiple discovery paths
* which menu, module, or theme behavior may need separate configuration

A clean category plan improves Demo Migration review because the reviewer can judge whether the product catalog is discoverable, not merely whether product records arrived.

#### 5. Identify customer, account, and communication context <a href="#id-5-identify-customer-account-and-communication-context" id="id-5-identify-customer-account-and-communication-context"></a>

Customer migration preparation should define what customer records need to support after launch. Basic customer identity may not be enough if customer records affect account access, marketing segmentation, order review, membership handling, loyalty context, or app-connected customer behavior.

The merchant should prepare:

* customer groups or segments that matter after launch
* records that should not move because they are obsolete, test accounts, or duplicates
* customer addresses and contact information that should be reviewed for quality
* marketing opt-in or communication context that should be handled carefully
* account history needed for customer service
* customer references used by external systems
* custom customer fields or app-owned customer data that require review

The preparation goal is to know whether customer data is simple identity information or part of a broader customer-management process.

#### 6. Review order history for operational usefulness <a href="#id-6-review-order-history-for-operational-usefulness" id="id-6-review-order-history-for-operational-usefulness"></a>

Order records should be prepared with the future support and reporting needs in mind. A Cafe24 migration should not treat order history as valuable merely because it exists. The useful question is which historical order information the business needs after launch and how that history should be interpreted.

The merchant should review:

* order date range needed in the Target Platform
* order statuses that should remain understandable
* payment and shipping context needed for service review
* tax, discount, coupon, and refund references that matter historically
* product-line details needed for reorder or customer-service use
* source statuses or fulfillment notes that may not translate directly
* external order references owned by ERP, accounting, marketplace, shipping, or fulfillment systems

If external systems own part of the order truth, preparation should identify those systems before migration. Otherwise, Cafe24 may receive records that look complete but do not explain the business workflow behind them.

#### 7. Inventory apps, design dependencies, and custom storefront behavior <a href="#id-7-inventory-apps-design-dependencies-and-custom-storefront-behavior" id="id-7-inventory-apps-design-dependencies-and-custom-storefront-behavior"></a>

Cafe24 supports an ecosystem around apps, design, modules, web components, scripts, APIs, Data Bridge, and webhooks. Preparation should identify which parts of the source store depend on similar outside layers and which Cafe24-side behavior must be configured separately.

The merchant should list:

* discount, promotion, loyalty, or pricing behavior controlled by apps or scripts
* shipping fee logic or carrier behavior controlled outside ordinary product/order data
* payment gateway or checkout behavior that affects launch readiness
* design elements that shape product pages, category pages, and content presentation
* JavaScript, embedded widgets, tracking scripts, or third-party storefront behavior
* API-connected systems that read from or write to the store
* webhooks, data feeds, analytics, or Data Bridge-type workflows that must be rebuilt or reconnected

This inventory helps prevent unrealistic expectations. Migration can move and translate supported data, but app behavior, design logic, API workflows, and external system responsibilities must be planned separately.

#### 8. Separate standard migration needs from Add-on and Custom Service needs <a href="#id-8-separate-standard-migration-needs-from-add-on-and-custom-service-needs" id="id-8-separate-standard-migration-needs-from-add-on-and-custom-service-needs"></a>

Preparation should identify which requirements fit standard migration capability and which require additional service planning. This is especially important when source data includes filters, mapping needs, custom fields, source modifications, or external identifiers.

The merchant should flag:

* data filtering needs that should use the Data Filter Add-on
* field or value mapping needs that may use Advanced Data Mapping
* data value changes that may use Advanced Data Configure
* requirements that exceed Standard Add-on settings or supported behavior
* Tailored Add-on or Custom Add-on needs
* Custom Platform source interpretation
* custom migration logic adjustment
* app-owned data, third-party data, or outside-system identifiers

Using a Standard Add-on within its available settings and supported behavior does not automatically make the project Custom. Requirements that need customization, modification, Tailored Add-ons, Custom Add-ons, Custom Platform handling, or custom migration logic adjustment should be reviewed through Custom Service.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

Cafe24 preparation is easier when the merchant works from business context to data details, then from data details to validation samples.

| Step | Preparation action                                   | Practical outcome                                                                                                                           |
| ---- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Define the future Cafe24 operating role              | Clarifies whether the migration is a simple storefront move, an app-connected move, a market-specific launch, or a more customized project. |
| 2    | Map storefront and market expectations               | Identifies the storefront, category, content, language, market, or buyer-context decisions that affect migration review.                    |
| 3    | Clean product and category data                      | Reduces duplicate, obsolete, or confusing catalog structure before it reaches the Target Platform.                                          |
| 4    | Review customer and order records                    | Confirms which customer and order information is useful for post-launch service, reporting, and support.                                    |
| 5    | Inventory apps, design logic, APIs, and integrations | Separates data migration from configuration, reconnection, and Custom Service needs.                                                        |
| 6    | Identify Add-on or Custom Service requirements       | Prevents filtering, mapping, custom fields, external identifiers, or custom logic from being discovered too late.                           |
| 7    | Choose Demo Migration samples                        | Ensures the sample migration can reveal whether Cafe24 is being prepared correctly.                                                         |
| 8    | Resolve escalation items before Full Migration       | Avoids entering Full Migration with unresolved business logic, custom source interpretation, or external system dependencies.               |

This sequence helps the merchant avoid a common preparation mistake: reviewing data only after it has already been migrated. The better approach is to decide what the migrated result should prove before the sample is created.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should not use only easy records. For Cafe24, a useful Demo Migration sample should include records that expose storefront, catalog, customer, order, app, API, and integration questions early.

| Sample type                      | What to include                                                                                                                      | Why it matters                                                                              |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| Representative products          | Simple products, products with options, products with images, SEO fields, categories, and important product-detail content           | Shows whether product meaning remains clear inside Cafe24.                                  |
| Category and navigation examples | Top categories, nested categories, campaign categories, SEO-sensitive pages, and high-traffic paths                                  | Shows whether buyers can find products and whether important routes need redirect planning. |
| Customer records                 | Ordinary customers, segmented customers, accounts with order history, duplicate-prone accounts, and records tied to external systems | Shows whether customer data supports service and communication needs after migration.       |
| Order history                    | Recent orders, older orders, orders with discounts, refunds, shipping differences, payment references, and special statuses          | Shows whether historical orders remain useful for service and operational review.           |
| Design-sensitive records         | Products or pages that depend on rich content, special layout, media, scripts, or theme behavior                                     | Shows where design or module configuration affects the perceived migration result.          |
| App-sensitive records            | Products, customers, or orders affected by discount, shipping, payment, loyalty, analytics, or marketing apps                        | Shows which outcomes require app configuration or separate review.                          |
| Integration-sensitive records    | Records connected to ERP, accounting, fulfillment, marketplace, tax, CRM, analytics, API, webhook, or Data Bridge workflows          | Shows whether the migration depends on external ownership beyond Cafe24 records.            |
| Custom source examples           | Custom fields, modified source records, outside-system identifiers, third-party data, or non-standard database structures            | Shows whether Custom Service review is needed before broader execution.                     |

A strong Demo Migration sample should make review harder in a useful way. If the sample includes only clean products and ordinary customers, it may hide the very issues that will matter during launch.

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

If Cafe24 is the Target Platform and the Source Platform is a Custom Platform or heavily modified system, preparation should start with source interpretation. The migration cannot safely translate data when the source meaning is undocumented.

The merchant should prepare:

* source database or export structure notes
* definitions for custom fields and custom tables
* explanation of outside-system identifiers
* examples of app-owned or third-party data
* mapping notes for non-standard product, customer, order, or content structures
* custom checkout, pricing, shipping, payment, or fulfillment behavior
* records that prove how the source system actually works

Custom Platform source cases should be reviewed through Custom Service. The issue is not only technical extraction. The issue is understanding what the source data means, which parts belong in Cafe24, which parts need configuration, and which parts require custom migration logic adjustment.

### What Should Be Escalated Before Execution <a href="#what-should-be-escalated-before-execution" id="what-should-be-escalated-before-execution"></a>

Some issues should be raised before Full Migration because they can change the migration approach, Add-on plan, or Custom Service requirement.

| Escalation signal                                                                         | Why it should be reviewed early                                                                                                           |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Product options, categories, or attributes have no consistent structure                   | The migrated catalog may appear complete but remain difficult to browse, configure, or validate.                                          |
| Storefront design or modules control important product or content behavior                | Data migration alone may not recreate the intended customer experience.                                                                   |
| Discount, shipping, or payment behavior is app-owned                                      | These outcomes may require configuration, app review, or Custom Service rather than standard data movement.                               |
| API, webhook, Data Bridge, analytics, or integration workflows affect business operations | External ownership must be identified before launch readiness can be judged.                                                              |
| Customer or order records depend on outside-system identifiers                            | The migration may need mapping or custom logic to preserve useful references.                                                             |
| The merchant wants only selected records to move                                          | Filtering should be planned before execution through the Data Filter Add-on or Custom Service if requirements exceed standard capability. |
| Source data includes custom fields, modified structures, or third-party data              | These cases may require Custom Service review before migration scope is reliable.                                                         |
| Demo Migration samples do not include high-risk records                                   | The sample may produce false confidence and leave launch-critical issues hidden.                                                          |

Escalation is not a failure. It is how the merchant avoids discovering avoidable problems after Full Migration has already started.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Cafe24 preparation should make the expected migration result visible before execution. The merchant should understand how storefront structure, product and category meaning, customer and order context, design dependencies, apps, APIs, integrations, custom fields, and external systems affect the future Cafe24 store.

The strongest preparation work produces clear Demo Migration samples and clear decision points. It shows what can be handled through standard migration capability, what may need Add-ons, what requires configuration outside migration, and what should be reviewed through Custom Service before broader execution.

Before starting Full Migration to Cafe24, use Demo Migration and Live Chat to review representative products, categories, customers, orders, storefront routes, app-sensitive records, integration-sensitive data, and custom source examples. The goal is to confirm that the migration plan reflects how the future Cafe24 store is expected to operate, not only that records can be moved.

### FAQs <a href="#faqs" id="faqs"></a>

**Should Cafe24 preparation start with product data or storefront structure?**

It should start with the future operating role of the Cafe24 store, then move into product and storefront detail. Product cleanup is important, but the merchant first needs to know how Cafe24 will support the future storefront, market, design, app, and integration model.

**What should be included in a Cafe24 Demo Migration sample?**

The sample should include ordinary records and high-risk records: products with options, important categories, SEO-sensitive pages, customer records with history, orders with payment or shipping context, app-sensitive records, integration-sensitive data, and any custom source examples that may need deeper review.

**Do Cafe24 apps migrate automatically with store data?**

No. App-owned behavior, scripts, API workflows, Data Bridge connections, webhooks, analytics feeds, payment gateway behavior, and shipping fee logic should be reviewed separately. Some records may migrate, but the behavior around those records may need configuration, reconnection, or Custom Service review.

**When should Add-ons be planned for Cafe24 migration?**

Add-ons should be planned when the merchant needs filtering, mapping, or data configuration beyond straightforward record transfer. The Data Filter Add-on, Advanced Data Mapping, and Advanced Data Configure can help when requirements fit their available settings and supported behavior. Requirements beyond that should be reviewed through Custom Service.

**When does Cafe24 preparation require Custom Service review?**

Custom Service review is needed when the migration involves customization, modification, Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, custom fields, third-party data, outside-system identifiers, app-owned data, or source behavior that standard migration capability cannot interpret safely.
