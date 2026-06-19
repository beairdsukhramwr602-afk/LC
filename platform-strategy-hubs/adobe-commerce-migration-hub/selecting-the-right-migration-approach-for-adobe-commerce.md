# Selecting the Right Migration Approach for Adobe Commerce

An Adobe Commerce migration approach should be selected by matching the target operating model to the right service responsibility. Adobe Commerce is often chosen for enterprise catalog structure, B2B company accounts, shared catalogs, scoped storefronts, advanced pricing visibility, Content Staging, custom modules, and integration-heavy operations. Those strengths make the migration approach a business-architecture decision, not only a transfer-volume decision.

A reliable approach should define what can move through a supported migration path, what needs additional filtering or mapping, what requires expert-led execution, what belongs in Custom Service, and what must be validated before launch. Entity Points capacity matters, but it does not measure the full complexity of B2B relationships, shared catalog behavior, staged content, integration dependencies, or custom commercial rules.

### Start with Enterprise Behavior, Not Only Entity Volume <a href="#start-with-enterprise-behavior-not-only-entity-volume" id="start-with-enterprise-behavior-not-only-entity-volume"></a>

Entity volume affects the service license and Entity Points Plan, but Adobe Commerce migration complexity is often created by business rules and operational dependencies. A source store with fewer records can still require a complex approach if it has company hierarchies, buyer roles, negotiated pricing, custom approval workflows, ERP-linked account IDs, staged campaigns, or storefront-specific content.

The first approach decision should separate data quantity from business behavior.

| Review area                     | Lower-complexity signal                                              | Higher-complexity signal                                                                                                           |
| ------------------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| B2B account model               | Customers are mostly individual accounts or simple wholesale groups. | Customers represent companies, departments, buyers, approvers, administrators, or role-based purchasing structures.                |
| Shared catalog and pricing      | Pricing is mostly global or customer-group based.                    | Product visibility, negotiated pricing, quote behavior, or contract terms vary by company or buyer group.                          |
| Storefront scope                | One website, one store, one store view, or a simple language setup.  | Multiple websites, stores, store views, regions, brands, languages, or scoped content and catalog values.                          |
| Catalog architecture            | Standard products and categories with limited custom relationships.  | Configurable, bundle, grouped, downloadable, virtual, custom-option, or heavily governed product families.                         |
| Content and campaign timing     | Static CMS Pages and ordinary content updates.                       | Content Staging, scheduled campaigns, launch-sensitive landing pages, or merchandising windows.                                    |
| Integrations and custom modules | Source data mostly uses native structures.                           | ERP, PIM, CRM, WMS, tax, payment, quote, subscription, loyalty, marketplace, or custom module data affects post-launch operations. |

The selected approach should match the highest-risk parts of the migration. A project may use Standard Service for supported entities, Add-ons for compatible filtering or mapping needs, Managed Service for execution support, and Custom Service for specific enterprise logic that requires bespoke handling.

### Use Standard Service When the Migration Path Is Structurally Compatible <a href="#use-standard-service-when-the-migration-path-is-structurally-compatible" id="use-standard-service-when-the-migration-path-is-structurally-compatible"></a>

Standard Service is usually the right starting point when the source data fits supported entities and the Target Store can accept those entities without significant custom interpretation. It is suitable when the customer wants to self-perform the migration process on the Next-Cart website, review Demo Migration results, and proceed to Full Migration after representative records behave correctly.

For Adobe Commerce, Standard Service can be appropriate when enterprise features are not part of the migrated launch scope, or when they will be configured separately in the Target Store without requiring custom source-data transformation. The store can still be commercially important or data-heavy; the key question is whether the migrated records fit the supported migration path and can be validated confidently.

Standard Service is most appropriate when:

* products, categories, customers, orders, reviews, CMS Pages, Blog Posts, and other selected entities fit a supported migration path;
* the Target Store website, store, and store-view structure is defined before migration configuration;
* product types, variants, attributes, and attribute sets can be validated through representative Demo Migration samples;
* B2B company accounts, shared catalogs, quotes, purchase approvals, and custom buyer permissions are not required in the migrated scope, or will be configured outside the migration scope;
* source pricing does not depend on unsupported negotiated-pricing logic or custom commercial rules;
* integration-owned identifiers are either not needed, supported in the approved scope, or can be recreated outside the migration;
* the customer has internal owners who can validate catalog, customer, order, content, URL, and storefront outcomes.

Standard Service should not be stretched to cover unclear enterprise behavior. If company structure, shared catalog visibility, account-specific pricing, Content Staging, custom modules, or integration-owned data must survive as operational logic, those requirements should be reviewed before assuming a standard approach is safe.

### Use Managed Service When Compatible Work Needs Expert-Led Execution <a href="#use-managed-service-when-compatible-work-needs-expert-led-execution" id="use-managed-service-when-compatible-work-needs-expert-led-execution"></a>

Managed Service is better when the migration path is compatible but the customer wants Next-Cart to handle more of the migration process, coordination, review, or execution support. The need for Managed Service often comes from project governance, launch timing, internal bandwidth, stakeholder coordination, or validation complexity rather than from unsupported data alone.

Adobe Commerce projects often involve several decision owners. Catalog teams may own product structure and attribute behavior. B2B sales teams may own company accounts, buyer access, and shared catalog expectations. Marketing may own CMS Pages, staged content, redirects, and campaign landing pages. Operations may own inventory, fulfillment, and back-office continuity. Finance and IT may own ERP, tax, reporting, and order-history expectations.

Managed Service is a strong fit when:

* the customer wants Next-Cart to manage migration execution instead of self-performing each step;
* the data is structurally supported, but the project needs stronger sequencing, coordination, or review support;
* several departments must approve the migrated result before launch;
* Demo Migration samples need careful selection across B2B, catalog, pricing, scope, content, URL, and integration cases;
* the source store remains active while the Target Store is reviewed;
* internal teams need help organizing validation findings and deciding whether the scope is ready for Full Migration;
* the project has a launch window, stakeholder dependency, or business freeze period that requires tighter process control.

Managed Service is not automatically the same as Custom Service. A project can need Managed Service because the process is complex, even when the data is compatible. A project can also require Custom Service even if the customer is willing to perform available migration actions manually, because the issue is unsupported logic rather than execution ownership.

### Use Add-ons for Compatible Filtering, Mapping, or Configuration Needs <a href="#use-add-ons-for-compatible-filtering-mapping-or-configuration-needs" id="use-add-ons-for-compatible-filtering-mapping-or-configuration-needs"></a>

Add-ons are optional service features that adjust how compatible migration data is filtered, mapped, or configured. They are not the same as Managed Service, and they are not a substitute for Custom Service when the requirement depends on unsupported source logic or bespoke enterprise behavior.

In Adobe Commerce planning, Add-ons are useful when the core migration path is compatible but the customer needs more control over scope, field alignment, or target behavior.

| Need                                      | Likely service feature             | Adobe Commerce example                                                                                                                                   |
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
* source quote, contract, purchase order, dealer, distributor, or wholesale portal behavior must remain meaningful after migration;
* product relationships, product options, bundles, downloadable products, or product-rule behavior depend on unsupported structures;
* Content Staging, campaign scheduling, catalog rules, or merchandising timelines require special interpretation;
* order history includes custom operational fields needed by finance, fulfillment, ERP, tax, support, or reporting teams;
* outside-system identifiers must be preserved for ERP, PIM, CRM, WMS, tax, payment, subscription, loyalty, marketplace, or reporting systems;
* custom modules or extensions own business-critical data that standard migration cannot interpret safely.

Custom Service should be scoped before it is promised. Some needs are narrow, such as preserving a specific ERP account ID or mapping a known custom field. Others are broad, such as converting a source wholesale portal into Adobe Commerce company structures, shared catalogs, and buyer permissions. The service plan should define what can be migrated, what should be configured in Adobe Commerce, what needs implementation-side work, what should remain historical reference, and what should be excluded.

#### Separate Custom Service from Expert Handle <a href="#separate-custom-service-from-expert-handle" id="separate-custom-service-from-expert-handle"></a>

Custom Service defines the scope of custom handling. Expert Handle defines whether Next-Cart performs migration actions and related execution work on the customer’s behalf. An Adobe Commerce project can require Custom Service without expert-managed execution, or it can combine Custom Service with Expert Handle when the agreed plan includes both custom handling and Next-Cart-led execution.

This distinction prevents two planning mistakes: assuming every custom requirement includes full migration management, or assuming customer-led execution can resolve unsupported enterprise data logic without custom review.

### Plan Entity Points Around Scope and Launch Value <a href="#plan-entity-points-around-scope-and-launch-value" id="plan-entity-points-around-scope-and-launch-value"></a>

The Entity Points Plan should reflect the selected entities and expected migration scope. For Adobe Commerce, entity planning should be tied to launch value, business continuity, and validation ownership, not only the desire to carry every historical record.

Entity planning should classify data into four groups.

| Entity group                | Recommended treatment                                                                                                                                                                                  |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Core launch data            | Products, categories, customers, orders, images, URLs, CMS Pages, Blog Posts, reviews, and other entities required for launch should be included when compatible and valuable.                         |
| Useful but selective data   | Old orders, inactive products, legacy customers, expired campaign content, retired categories, or obsolete pages may be filtered by business value.                                                    |
| Structurally uncertain data | Company relationships, shared catalog data, source pricing rules, external IDs, custom fields, custom module records, or extension-owned data should be reviewed before inclusion.                     |
| Low-value legacy noise      | Duplicate attributes, obsolete campaign pages, unused categories, broken media, retired custom fields, and outdated operational records should often be excluded or archived outside the Target Store. |

Entity Points are capacity planning, not complexity scoring. A large standard catalog may need a higher Entity Points Plan but still fit Standard Service. A smaller project with company-specific pricing, custom B2B workflows, integration identifiers, and unsupported data may require Custom Service review even with fewer counted records.

### Use Demo Migration to Confirm the Approach <a href="#use-demo-migration-to-confirm-the-approach" id="use-demo-migration-to-confirm-the-approach"></a>

Demo Migration should test whether the selected approach is realistic before Full Migration. For Adobe Commerce, a useful sample should not be random. It should include the records most likely to expose enterprise behavior, scope, product architecture, pricing visibility, content timing, URL continuity, and integration issues.

The sample should include expected outcomes such as:

* a company account or B2B buyer record if B2B behavior is in scope;
* products that represent shared catalog visibility, customer-group pricing, or negotiated-pricing expectations;
* configurable, bundle, grouped, downloadable, virtual, custom-option, and high-value simple products where relevant;
* product attributes that affect filters, search, comparison, rules, storefront display, or operational reporting;
* store-view-specific product, category, CMS Page, Blog Post, or URL behavior;
* orders with discounts, taxes, refunds, cancellations, payment references, shipping fees, unusual statuses, or external identifiers;
* CMS Pages, campaign landing pages, localized pages, and launch-sensitive content;
* priority product, category, CMS Page, Blog Post, and redirect samples for SEO review;
* inventory examples that represent single-source, multi-source, externally managed, or launch-critical stock expectations;
* records connected to source extensions, custom modules, or integration-owned identifiers.

Demo Migration should decide whether the selected approach is still valid. If sample records pass, the project can move toward Full Migration with clearer confidence. If samples expose unsupported structures, unclear target configuration, or mismatched expectations, the service plan should be adjusted before the cost of correction increases.

### Plan Additional Migration Options for Launch Timing <a href="#plan-additional-migration-options-for-launch-timing" id="plan-additional-migration-options-for-launch-timing"></a>

Adobe Commerce projects often run while the source store remains active. New customers, orders, company updates, product changes, price changes, inventory updates, content edits, URL changes, or campaign updates may appear after an earlier migration run. These changes should be planned through the available Additional Migration Options under the service license, not treated as informal manual fixes.

Additional Migration Options are relevant when:

* the live source store continues receiving orders close to launch;
* new products, customers, reviews, CMS Pages, Blog Posts, or company-related updates appear after Full Migration;
* pricing, product attributes, store-view content, URLs, or catalog structure are adjusted after earlier testing;
* mapping decisions are corrected after Demo Migration or stakeholder review;
* target configuration changes make an earlier migrated result unsuitable;
* launch timing requires the Target Store to be refreshed closer to cutover;
* extension-related records are excluded first and added later after Custom Service review.

The key planning question is which additional action fits the business need: continuing the migration with the last used configuration, continuing with a new configuration, or performing a new migration. The choice should consider target cleanup, duplicate risk, Entity Points capacity, validation effort, launch timing, and whether the changed scope affects B2B, shared catalog, content, URL, or integration behavior.

### Match the Approach to the Real Decision <a href="#match-the-approach-to-the-real-decision" id="match-the-approach-to-the-real-decision"></a>

The strongest Adobe Commerce migration approach separates standard transfer, guided execution, optional Add-ons, custom review, capacity planning, launch timing, and validation responsibility before Full Migration begins.

| Migration situation                                                                                                                                            | Recommended approach                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Compatible source data, clear Target Store structure, and customer confidence in self-performing migration steps                                               | Standard Service with careful Demo Migration review.                                                  |
| Compatible source data, enterprise coordination needs, limited internal capacity, or launch-sensitive review                                                   | Managed Service with defined validation responsibility.                                               |
| Compatible data requiring selective movement or field alignment                                                                                                | Standard Service or Managed Service with Add-ons such as Data Filter Add-on or Advanced Data Mapping. |
| Company-account modeling, shared catalog behavior, custom pricing logic, extension-owned records, external IDs, custom modules, or Custom Platform source data | Custom Service review before approving scope.                                                         |
| Active source store with new records or updates expected before launch                                                                                         | Plan the appropriate Additional Migration Option as part of launch readiness.                         |
| Changed mapping, corrected target configuration, revised scope, or intentional replacement of earlier migrated results                                         | Choose the additional action deliberately, with cleanup and validation expectations.                  |

A reliable Adobe Commerce migration plan does not force every requirement into one service path. It identifies which parts are structurally compatible, which parts need optional filtering or mapping, which parts require custom review, and which parts must be validated before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting an Adobe Commerce migration approach should begin with the operating model the Target Store must support: B2B company accounts, shared catalogs, scoped storefronts, product architecture, Content Staging, integrations, custom modules, URL continuity, and launch timing. Standard Service, Managed Service, Custom Service, Add-ons, Entity Points, and Additional Migration Options each answer different planning needs.

The right approach is the one that correctly separates compatible migration work, guided execution, optional filtering or mapping, custom review, capacity planning, launch updates, and final verification responsibility before Full Migration begins.

### FAQs <a href="#faqs" id="faqs"></a>

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for an Adobe Commerce migration?**

Standard Service can be enough when the selected migration path is supported, the Target Store structure is prepared, and Demo Migration confirms that representative records behave correctly. B2B, shared catalog, custom pricing, integration, or custom module requirements should be reviewed before assuming Standard Service is enough.

**When should an Adobe Commerce project use Managed Service?**

Managed Service is appropriate when the migration path is compatible but the customer wants Next-Cart to handle more of the process, coordination, execution support, or review workflow. It is especially useful when multiple business teams must approve the migrated result before launch.

**Are Add-ons the same as Custom Service?**

No. Add-ons help with filtering, mapping, or data configuration for compatible migration work. Custom Service is used when the requirement involves unsupported structures, custom logic, extension-owned data, Custom Platform source context, or bespoke handling.

**Does Entity Points capacity measure Adobe Commerce complexity?**

No. Entity Points help determine the required Entity Points Plan for the selected migration scope. They do not fully measure B2B logic, shared catalog behavior, staged content, integrations, custom modules, or bespoke data handling.

**Should Additional Migration Options be planned before launch?**

They should be considered when the source store remains active, new records are expected before launch, or configuration and mapping decisions may change after earlier migration runs. The selected action should match the business need and validation scope.

**Does Custom Service automatically mean Next-Cart performs the whole migration?**

No. Custom Service defines custom handling scope. Expert Handle or Managed Service determines whether Next-Cart performs migration actions and related execution work on the customer’s behalf.
