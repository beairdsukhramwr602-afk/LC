# Selecting the Right Migration Approach for Adobe Commerce

An Adobe Commerce migration approach should be selected by matching enterprise operating requirements to the right level of service responsibility. Record volume matters, but Adobe Commerce decisions are often shaped more strongly by B2B company structures, shared catalogs, buyer-specific pricing, product architecture, website/store/store-view scope, Content Staging, inventory, integrations, extension-owned data, and custom business logic.

The right approach should explain what can move through a supported migration path, what needs Add-ons, what requires Managed Service involvement, what belongs in Custom Service, and how the Entity Points Plan should support the intended scope. It should also define how Demo Migration results will be used before Full Migration and when Additional Migration Options may be needed close to launch.

### Start with Adobe Commerce Operating Complexity <a href="#start-with-adobe-commerce-operating-complexity" id="start-with-adobe-commerce-operating-complexity"></a>

Adobe Commerce complexity usually comes from relationships, scope, and business rules rather than raw record totals. A smaller B2B store can require deeper review than a larger retail catalog if company accounts, shared catalogs, buyer permissions, quote behavior, or contract pricing must remain meaningful after launch. A larger store can be more straightforward when products, customers, orders, content, and URLs follow clean structures.

Use the first review to separate size from structural difficulty.

| Review area                    | Lower-complexity signal                                             | Higher-complexity signal                                                                                                                    |
| ------------------------------ | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Buyer model                    | Mainly retail customers and ordinary customer groups.               | Company accounts, company administrators, company users, roles, permissions, purchase approvals, quote workflows, or B2B account ownership. |
| Pricing and catalog visibility | Standard product pricing with limited customer-group variation.     | Shared catalogs, buyer-specific pricing, negotiated prices, restricted assortments, tier pricing, or ERP-owned pricing rules.               |
| Catalog model                  | Mostly simple and configurable products with consistent attributes. | Complex configurable, bundle, grouped, virtual, downloadable, or custom-option behavior tied to business rules.                             |
| Storefront scope               | One website, one store, and one store view.                         | Multiple websites, stores, store views, languages, brands, regions, domains, or scope-specific content and URLs.                            |
| Content and campaigns          | Static CMS Pages, Blog Posts, and ordinary promotional content.     | Scheduled campaigns, Content Staging expectations, launch-sensitive landing pages, or regional merchandising timelines.                     |
| Integrations and custom data   | Most records use native source structures.                          | ERP, PIM, CRM, WMS, tax, payment, procurement, marketplace, extension-owned, or custom-module data controls operational meaning.            |

The migration approach should match the highest-risk part of the store. Adobe Commerce can use Standard Service for compatible entities while using Add-ons or Custom Service for specific requirements that need additional handling.

### Use Standard Service When the Migration Path Is Structurally Compatible <a href="#use-standard-service-when-the-migration-path-is-structurally-compatible" id="use-standard-service-when-the-migration-path-is-structurally-compatible"></a>

Standard Service is usually the right starting point when the source data fits supported entities and the Adobe Commerce Target Store can accept those entities without bespoke interpretation. It works best when the customer can self-perform the migration process on the Next-Cart website, review Demo Migration results, and proceed to Full Migration after representative records behave correctly.

For Adobe Commerce, Standard Service can be appropriate when enterprise features are not part of the migrated launch scope, or when they will be configured separately in the Target Store without requiring custom source-data transformation. The store can still be commercially important or data-heavy; the key question is whether migrated records fit the supported migration path and can be validated confidently.

Standard Service is most appropriate when:

* products, categories, customers, orders, reviews, CMS Pages, Blog Posts, images, URLs, and other selected entities fit a supported migration path;
* the Target Store website, store, and store-view structure is defined before migration configuration;
* product types, variants, attributes, and attribute sets can be validated through representative Demo Migration samples;
* B2B company accounts, shared catalogs, quotes, purchase approvals, and custom buyer permissions are not required in the migrated scope, or will be configured separately outside migration scope;
* pricing does not depend on unsupported negotiated-pricing logic, contract-pricing rules, or custom commercial behavior;
* integration-owned identifiers are either not needed, supported in the approved scope, or can be recreated outside migration;
* the customer has internal owners who can validate catalog, customer, order, content, URL, storefront, and buyer-experience outcomes.

Standard Service should not be stretched to cover unclear enterprise behavior. If company structure, shared catalog visibility, account-specific pricing, Content Staging, custom modules, or integration-owned data must survive as operational logic, those requirements should be reviewed before assuming a standard approach is safe.

### Use Managed Service When Compatible Work Needs Expert-Led Execution <a href="#use-managed-service-when-compatible-work-needs-expert-led-execution" id="use-managed-service-when-compatible-work-needs-expert-led-execution"></a>

Managed Service is better when the migration path is compatible but the customer wants Next-Cart to handle more of the migration process, coordination, review, or execution support. The need for Managed Service often comes from project governance, launch timing, internal bandwidth, stakeholder coordination, or validation complexity rather than from unsupported data alone.

Adobe Commerce projects often involve several decision owners. Catalog teams may own product structure and attribute behavior. B2B sales teams may own company accounts, buyer access, quotes, purchase approvals, and shared catalog expectations. Marketing may own CMS Pages, staged content, redirects, and campaign landing pages. Operations may own inventory, fulfillment, and back-office continuity. Finance and IT may own ERP, tax, reporting, payment, and order-history expectations.

Managed Service is a strong fit when:

* the customer wants Next-Cart to manage migration execution instead of self-performing each step;
* the data is structurally supported, but the project needs stronger sequencing, coordination, or review support;
* several departments must approve the migrated result before launch;
* Demo Migration samples need careful selection across B2B, catalog, pricing, scope, content, URL, inventory, and integration cases;
* the source store remains active while the Target Store is reviewed;
* internal teams need help organizing validation findings and deciding whether the scope is ready for Full Migration;
* the project has a launch window, stakeholder dependency, or business freeze period that requires tighter process control.

Managed Service is not automatically the same as Custom Service. A project can need Managed Service because the process is complex, even when the data is compatible. A project can also require Custom Service even if the customer is comfortable performing available migration actions manually, because the issue is unsupported logic rather than execution ownership.

### Use Add-ons for Compatible Filtering, Mapping, or Configuration Needs <a href="#use-add-ons-for-compatible-filtering-mapping-or-configuration-needs" id="use-add-ons-for-compatible-filtering-mapping-or-configuration-needs"></a>

Add-ons are optional service features that adjust how compatible migration data is filtered, mapped, or configured. They are not the same as Managed Service, and they are not a substitute for Custom Service when the requirement depends on unsupported source logic or bespoke enterprise behavior.

In Adobe Commerce planning, Add-ons are useful when the core migration path is compatible but the customer needs more control over scope, field alignment, or target behavior.

| Need                                      | Relevant option                    | Adobe Commerce example                                                                                                                                   |
| ----------------------------------------- | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Narrow the migrated scope                 | Data Filter Add-on                 | Migrate selected order date ranges, customer groups, product statuses, categories, content groups, or launch-relevant historical records.                |
| Align supported fields more precisely     | Advanced Data Mapping              | Map compatible source values into Adobe Commerce product attributes, customer fields, order references, content fields, or integration reference fields. |
| Adjust compatible target behavior         | Advanced Data Configure            | Apply agreed configuration behavior for selected migrated records when compatible with the approved migration path.                                      |
| Modify an Add-on beyond standard coverage | Tailored Add-ons or Custom Add-ons | Adapt filtering, mapping, or configuration handling when the standard Add-on does not fully match the Adobe Commerce requirement.                        |

Add-ons work best when the requirement is defined. They should not be used as a catch-all for company-account modeling, shared catalog rule conversion, custom module interpretation, unsupported quote workflows, external-system ownership, or bespoke pricing logic. Those requirements should be reviewed under Custom Service.

### Review Custom Service When Adobe Commerce Needs Bespoke Handling <a href="#review-custom-service-when-adobe-commerce-needs-bespoke-handling" id="review-custom-service-when-adobe-commerce-needs-bespoke-handling"></a>

Custom Service should be reviewed when the migration depends on structures, relationships, or business logic that are not safe to treat as standard entity transfer. Adobe Commerce projects often need this review when the source store uses custom B2B logic, company-specific pricing, extension-owned records, custom tables, external identifiers, custom checkout behavior, quote workflows, purchase approval structures, or integration-driven commercial rules.

Custom Service may be needed when:

* a Custom Platform source context is involved;
* source customer records must become company accounts, buyer roles, account administrators, or approval structures;
* shared catalog visibility or company-specific pricing depends on custom source logic;
* source quote, contract, purchase order, dealer, distributor, wholesale, or procurement behavior must remain meaningful after migration;
* product relationships, product options, bundles, downloadable products, or product-rule behavior depend on unsupported structures;
* Content Staging, campaign scheduling, catalog rules, or merchandising timelines require special interpretation;
* order history includes custom operational fields needed by finance, fulfillment, ERP, tax, support, or reporting teams;
* outside-system identifiers must be preserved for ERP, PIM, CRM, WMS, tax, payment, subscription, loyalty, marketplace, procurement, or reporting systems;
* custom modules or extensions own business-critical data that standard migration cannot interpret safely.

Custom Service should be scoped before it is promised. Some needs are narrow, such as preserving a specific ERP account ID or mapping a known custom field. Others are broad, such as translating a source wholesale portal into Adobe Commerce company structures, shared catalogs, and buyer permissions. The service plan should define what can be migrated, what should be configured in Adobe Commerce, what needs implementation-side work, what should remain historical reference, and what should be excluded.

### Plan Entity Points Around Scope and Launch Value <a href="#plan-entity-points-around-scope-and-launch-value" id="plan-entity-points-around-scope-and-launch-value"></a>

The Entity Points Plan should reflect the selected entities and expected migration scope. For Adobe Commerce, entity planning should be tied to launch value, business continuity, and validation ownership, not only the desire to carry every historical record.

| Entity group                | Recommended treatment                                                                                                                                                                                  |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Core launch data            | Products, categories, customers, orders, images, URLs, CMS Pages, Blog Posts, reviews, and other entities required for launch should be included when compatible and valuable.                         |
| Useful but selective data   | Old orders, inactive products, legacy customers, expired campaign content, retired categories, or obsolete pages may be filtered by business value.                                                    |
| Structurally uncertain data | Company relationships, shared catalog data, source pricing rules, external IDs, custom fields, custom module records, or extension-owned data should be reviewed before inclusion.                     |
| Low-value legacy noise      | Duplicate attributes, obsolete campaign pages, unused categories, broken media, retired custom fields, and outdated operational records should often be excluded or archived outside the Target Store. |

Entity Points are capacity planning, not complexity scoring. A large standard catalog may need a higher Entity Points Plan but still fit Standard Service. A smaller project with company-specific pricing, custom B2B workflows, integration identifiers, and unsupported data may require Custom Service review even with fewer counted records.

New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated for the first time under the service license. Records already counted through the service license should not consume Entity Points again merely because the customer uses later additional migration activity for the same migration path.

### Use Demo Migration to Confirm the Approach <a href="#use-demo-migration-to-confirm-the-approach" id="use-demo-migration-to-confirm-the-approach"></a>

Demo Migration should test the selected approach before Full Migration. For Adobe Commerce, useful samples should not be random. They should include records most likely to expose B2B, catalog, pricing, scope, URL, content, inventory, integration, and custom-data issues.

Strong Demo Migration samples include:

* a configurable product with associated simple products, option labels, child SKUs, stock behavior, images, categories, and scoped values;
* products that appear differently by website, store, store view, customer group, or shared catalog;
* a company account with administrator, users, roles, permissions, and company-specific buying expectations;
* shared catalog samples that prove product visibility and pricing logic for important buyer groups;
* customers and orders with taxes, discounts, shipping fees, invoices, refunds, quote context, purchase order references, unusual statuses, or external IDs;
* CMS Pages, Blog Posts, landing pages, campaign content, and redirects that need SEO and launch review;
* representative inventory cases for single-source or multi-source expectations;
* records connected to source extensions, custom fields, procurement systems, or external systems.

Demo Migration should decide whether the selected approach is still valid. If samples pass, the project can move toward Full Migration with clearer confidence. If samples reveal unsupported structures, unclear target configuration, or mismatched expectations, the service plan should be adjusted before scale increases the cost of correction.

### Plan Additional Migration Options for Adobe Commerce Launch Timing <a href="#plan-additional-migration-options-for-adobe-commerce-launch-timing" id="plan-additional-migration-options-for-adobe-commerce-launch-timing"></a>

Adobe Commerce projects often run while the Source Platform remains active. New products, customers, orders, reviews, CMS Pages, Blog Posts, company-account updates, pricing changes, mapping corrections, or target configuration changes may appear after an earlier migration run. These changes should be planned through Additional Migration Options when they affect the service license and migration path.

Additional Migration Options can be relevant when:

* the live source store continues receiving orders close to launch;
* new products, customers, reviews, CMS Pages, or Blog Posts appear after Full Migration;
* company records, customer groups, shared catalog assignments, pricing references, or buyer data are adjusted after testing;
* mapping decisions are corrected after Demo Migration or stakeholder review;
* target configuration changes make an earlier migrated result unsuitable;
* SEO URLs, redirects, campaign pages, or content paths require revised handling;
* extension-related records are excluded first and added later after Custom Service review.

The key planning question is not whether another migration action can occur. The key question is which follow-up action fits the business need: continuing with the approved configuration, continuing with a revised configuration, or performing a new migration for the same migration path. The choice should consider target cleanup, duplicate risk, Entity Points capacity, validation effort, and launch timing.

### Match the Approach to the Real Decision <a href="#match-the-approach-to-the-real-decision" id="match-the-approach-to-the-real-decision"></a>

The strongest Adobe Commerce migration approach separates standard transfer, guided execution, optional Add-ons, custom review, capacity planning, launch timing, and validation responsibility before Full Migration begins.

| Migration situation                                                                                                                          | Recommended approach                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Compatible source data, clear target structure, and confidence in customer-led execution                                                     | Standard Service with careful Demo Migration review.                                |
| Compatible source data, larger scope, limited internal capacity, or launch coordination needs                                                | Managed Service with defined validation ownership.                                  |
| Compatible data requiring selective movement or field alignment                                                                              | Standard Service or Managed Service with Add-ons.                                   |
| B2B company structures, shared catalogs, custom pricing logic, extension-owned data, external IDs, Custom Platform context, or bespoke logic | Custom Service review before approving scope.                                       |
| Active source store with new records expected before launch                                                                                  | Plan the appropriate Additional Migration Options and renewed review.               |
| Changed mapping, corrected target configuration, or intentionally different target output                                                    | Choose the follow-up action deliberately, with cleanup and validation expectations. |

An Adobe Commerce migration approach should not be selected from record totals alone. It should reflect the Target Store’s real operating model: B2B structure, catalog architecture, scope, pricing, URLs, inventory, integrations, custom logic, service responsibility, and launch timing.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Choosing the right Adobe Commerce migration approach means matching the Target Store’s enterprise burden to the right combination of Standard Service, Managed Service, Add-ons, Custom Service, Entity Points planning, Demo Migration review, Full Migration execution, and Additional Migration Options when they are needed.

When the approach is selected carefully, Adobe Commerce migration becomes easier to control. Compatible entities can move through the supported migration path, custom requirements can be scoped before they create launch risk, and validation can focus on whether the Target Store is ready to support the intended buyer experience.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for an Adobe Commerce migration?**

Standard Service can be enough when the source data fits a supported migration path, the Adobe Commerce target structure is clear, and the customer can review Demo Migration results confidently. It becomes less suitable when B2B company structures, shared catalogs, custom pricing, extension-owned data, or enterprise launch coordination require additional service responsibility.

**When should an Adobe Commerce project use Managed Service?**

Managed Service is useful when the data is broadly compatible but the customer wants Next-Cart to handle more migration execution, coordination, review support, or launch-window handling. It is an execution-responsibility decision, not proof that the data itself is custom.

**When does Adobe Commerce need Custom Service?**

Custom Service should be reviewed when unsupported structures, B2B relationships, shared catalog rules, custom pricing logic, extension-owned records, custom fields, Custom Platform behavior, external IDs, or integration-dependent data must be preserved beyond standard supported behavior.

**Do Add-ons replace Custom Service for Adobe Commerce?**

No. Add-ons help with compatible filtering, mapping, or configuration needs. Custom Service is needed when Adobe Commerce requirements depend on bespoke source logic, custom modules, unsupported B2B structures, or enterprise data relationships that need custom review.

**How should Additional Migration Options be planned for Adobe Commerce?**

Additional Migration Options should be planned when the source store remains active, mapping changes after testing, or new records appear before launch. Any follow-up activity should be followed by renewed review of the affected Adobe Commerce records, especially products, company data, shared catalog assignments, pricing references, URLs, customers, orders, inventory, and custom data.
