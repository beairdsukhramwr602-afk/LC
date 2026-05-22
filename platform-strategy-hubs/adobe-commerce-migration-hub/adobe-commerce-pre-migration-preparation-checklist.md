# Adobe Commerce Pre-Migration Preparation Checklist

Adobe Commerce preparation should define the target structure before the migration process begins. This is especially important when the future store depends on company accounts, shared catalogs, customer groups, staged content, multiple scopes, URL rewrites, and enterprise workflows that must remain commercially reliable after launch.

A strong preparation checklist does not simply confirm that products, customers, orders, categories, and CMS Pages are available for migration. It clarifies how Adobe Commerce should govern those records after they arrive. Without that preparation, the Target Platform may look complete while company access, pricing visibility, campaign timing, customer grouping, or route behavior still does not match the business model.

This checklist is meant to help merchants prepare for an Adobe Commerce migration at a decision and planning level. It is not an Admin setup guide. The goal is to decide what must be preserved, what should be formalized inside Adobe Commerce, what requires closer review, and which examples should be tested early through Demo Migration.

### What Adobe Commerce Preparation Should Clarify <a href="#what-adobe-commerce-preparation-should-clarify" id="what-adobe-commerce-preparation-should-clarify"></a>

Adobe Commerce is often chosen because the business wants stronger governance over commercial structure. Preparation should therefore answer practical questions before execution pressure increases:

* how company accounts and company users should be represented
* which catalogs, products, prices, and customer contexts need controlled visibility
* how customer groups should interact with shared catalog behavior
* which campaigns, merchandising updates, or content changes need scheduled control
* what should differ by website, store, or store view
* which legacy URLs and customer journeys need focused continuity planning
* which extension-owned, custom-field, or integration-dependent behavior still matters
* which sample records should be reviewed first to prove the target is safe

The checklist is strongest when these decisions are made in business terms before they become technical exceptions during validation.

### 1. Define the Future Company Structure <a href="#id-1-define-the-future-company-structure" id="id-1-define-the-future-company-structure"></a>

The first preparation priority is usually the customer relationship model behind the storefront.

Before migration, identify:

* which customers should belong to which company accounts
* which company relationships represent parent, child, regional, distributor, dealer, or branch structures
* which company users need purchasing authority or account-level roles
* which source-side customer conventions carry company meaning informally
* which account relationships affect pricing, access, approval, credit, or order behavior

This matters because Adobe Commerce can support company accounts and company hierarchy, but those structures only help when the business has defined what each relationship should mean. If company logic is vague, the target may contain company records without preserving the customer relationship model that revenue teams depend on.

### 2. Clarify Shared Catalog Access and Pricing Rules <a href="#id-2-clarify-shared-catalog-access-and-pricing-rules" id="id-2-clarify-shared-catalog-access-and-pricing-rules"></a>

Shared catalogs should be prepared as commercial rules, not only as catalog records.

Define:

* which customers or companies should access each catalog
* which products should be included or excluded
* where pricing should differ by company, segment, or negotiated agreement
* which catalogs should remain public and which should be restricted
* whether source-side access workarounds should become shared catalog rules in Adobe Commerce

A shared catalog can be technically present but commercially wrong if the wrong company sees the wrong products or prices. Preparation should therefore describe access and pricing outcomes in plain business terms before the target structure is built or validated.

### 3. Review Customer Groups Together With Shared Catalog Logic <a href="#id-3-review-customer-groups-together-with-shared-catalog-logic" id="id-3-review-customer-groups-together-with-shared-catalog-logic"></a>

Customer groups should not be prepared as a separate administrative list when shared catalogs are involved.

Before migration, decide:

* what each customer group should still mean after migration
* whether group logic affects pricing, tax class, access, or visibility
* whether any inherited customer grouping should be simplified
* how customer groups should interact with shared catalog assignment
* where duplicate or conflicting segmentation should be removed before launch

This reduces the risk of preserving both shared catalogs and customer groups while allowing the relationship between them to become confusing, redundant, or commercially incorrect.

### 4. Identify Staged Content and Timed Merchandising Behavior <a href="#id-4-identify-staged-content-and-timed-merchandising-behavior" id="id-4-identify-staged-content-and-timed-merchandising-behavior"></a>

Adobe Commerce preparation should separate static content from timed commercial behavior.

Identify:

* campaigns that require scheduled content or merchandising changes
* catalog price rules or cart price rules that depend on timing
* products, categories, CMS Pages, or CMS Blocks that need scheduled updates
* campaign previews that business teams need before launch
* time-zone or store-scope expectations that could affect campaign behavior

This is important because Content Staging can support scheduled changes, preview, and campaign-based planning. If the business prepares only the current storefront state, the target may look acceptable at launch while failing to support the campaign model expected after launch.

### 5. Decide What Should Differ by Website, Store, and Store View <a href="#id-5-decide-what-should-differ-by-website-store-and-store-view" id="id-5-decide-what-should-differ-by-website-store-and-store-view"></a>

Adobe Commerce scope hierarchy should be designed intentionally before migration.

Clarify:

* what should differ by website
* what should differ by store
* what should differ by store view
* what should remain global
* which differences are required for real business reasons
* which differences exist only because the source structure grew inconsistently over time

This matters because scope can affect content, language, catalog behavior, URLs, configuration, pricing context, and customer experience. Preparation should prevent Adobe Commerce flexibility from turning into unnecessary complexity.

### 6. Identify the Highest-Risk Product, Catalog, and Customer Combinations <a href="#id-6-identify-the-highest-risk-product-catalog-and-customer-combinations" id="id-6-identify-the-highest-risk-product-catalog-and-customer-combinations"></a>

Adobe Commerce preparation should not treat every product sample equally.

Prioritize examples where product structure, catalog access, pricing visibility, and customer context interact. These usually include:

* product families with complex configuration or business-specific rules
* products whose visibility changes by customer or company context
* categories where access or pricing rules are commercially sensitive
* shared catalogs that expose negotiated pricing or restricted assortments
* customer accounts that represent high-value or high-risk buying scenarios

The goal is to select examples that reveal whether Adobe Commerce is preserving commercial behavior, not only whether products and categories migrated.

### 7. Classify Extension-Owned, Custom-Field, and Integration-Dependent Behavior <a href="#id-7-classify-extension-owned-custom-field-and-integration-dependent-behavior" id="id-7-classify-extension-owned-custom-field-and-integration-dependent-behavior"></a>

Adobe Commerce can support more native structure than many lighter platforms, but enterprise stores often still depend on extensions, custom fields, custom logic, or external systems.

Before migration, list the behavior that still matters, including:

* extension-owned pricing, visibility, approval, checkout, or merchandising behavior
* custom fields that carry business rules or external identifiers
* ERP, PIM, CRM, analytics, fulfillment, or finance connections that depend on migrated data
* custom workflows that affect companies, catalogs, orders, promotions, or reporting
* source-side logic that should become native Adobe Commerce structure where appropriate

If the behavior affects pricing, access, workflow, visibility, reporting, or external system continuity, it should be reviewed as a Custom Service concern rather than treated as ordinary field transfer.

### 8. Prioritize Legacy URLs and Destination Intent <a href="#id-8-prioritize-legacy-urls-and-destination-intent" id="id-8-prioritize-legacy-urls-and-destination-intent"></a>

Adobe Commerce includes URL rewrite support, but preparation should still define which routes deserve focused protection.

Prioritize:

* product URLs that carry organic traffic or conversion value
* category and landing paths that support discovery
* CMS Pages that carry trust, service, support, or brand value
* campaign URLs that still receive traffic
* routes whose destination meaning may change because of catalog access, product visibility, or staged content

The preparation question is not only whether a redirect can be created. The stronger question is whether the destination still supports the customer intent and business value of the old route.

### 9. Define the Customer-Account Continuity Expectation <a href="#id-9-define-the-customer-account-continuity-expectation" id="id-9-define-the-customer-account-continuity-expectation"></a>

Customer records and customer-account continuity should not be treated as the same thing.

Before migration, clarify:

* whether password continuity is realistically possible for the selected migration path
* what returning customers should expect at first login
* whether company users need separate communication or setup guidance
* which account-access scenarios could create support pressure after launch
* which customer groups or company relationships must be especially reliable on day one

This helps prevent the business from assuming that imported customer records automatically create a smooth returning-customer experience.

### 10. Mark Representative Demo Migration Samples Early <a href="#id-10-mark-representative-demo-migration-samples-early" id="id-10-mark-representative-demo-migration-samples-early"></a>

A Demo Migration is most useful when the sample is selected around risk, not convenience.

For Adobe Commerce, strong sample choices usually include:

* high-value company accounts and company users
* shared catalogs with sensitive access or pricing rules
* customer groups that interact with catalog behavior
* products and categories with scope-sensitive or catalog-sensitive behavior
* staged content or campaign examples that matter after launch
* high-value URLs and destination pages
* extension-owned or integration-dependent data that affects business interpretation

These samples should help the business decide whether the target structure is understandable, commercially safe, and worth expanding into full migration.

### A Practical Adobe Commerce Preparation Sequence <a href="#a-practical-adobe-commerce-preparation-sequence" id="a-practical-adobe-commerce-preparation-sequence"></a>

A useful preparation sequence for Adobe Commerce usually moves from commercial structure to evidence.

#### 1. Define company and account structure first <a href="#id-1-define-company-and-account-structure-first" id="id-1-define-company-and-account-structure-first"></a>

Start with the company accounts, users, relationships, permissions, and business-customer contexts that matter most.

#### 2. Define shared catalog and pricing logic next <a href="#id-2-define-shared-catalog-and-pricing-logic-next" id="id-2-define-shared-catalog-and-pricing-logic-next"></a>

Clarify how product access, catalog assignment, and pricing visibility should work for the most important company contexts.

#### 3. Align customer groups with catalog control <a href="#id-3-align-customer-groups-with-catalog-control" id="id-3-align-customer-groups-with-catalog-control"></a>

Review group meaning together with shared catalog behavior so segmentation does not become redundant or contradictory.

#### 4. Identify staged content and campaign behavior <a href="#id-4-identify-staged-content-and-campaign-behavior" id="id-4-identify-staged-content-and-campaign-behavior"></a>

Separate launch-state content from timed merchandising, promotional, and CMS behavior that needs scheduled control.

#### 5. Design scope hierarchy around real business need <a href="#id-5-design-scope-hierarchy-around-real-business-need" id="id-5-design-scope-hierarchy-around-real-business-need"></a>

Decide which differences belong at website, store, or store-view level before the hierarchy becomes difficult to validate.

#### 6. Prioritize routes, account continuity, and custom behavior <a href="#id-6-prioritize-routes-account-continuity-and-custom-behavior" id="id-6-prioritize-routes-account-continuity-and-custom-behavior"></a>

Identify the URLs, account scenarios, extensions, custom fields, and integrations that would create the most visible business risk if misunderstood.

#### 7. Build a representative Demo Migration sample <a href="#id-7-build-a-representative-demo-migration-sample" id="id-7-build-a-representative-demo-migration-sample"></a>

Choose sample data that proves the hardest commercial questions first, especially company, shared catalog, customer-group, staging, scope, route, and custom-behavior cases.

### How a Custom Platform Source Changes Adobe Commerce Preparation <a href="#how-a-custom-platform-source-changes-adobe-commerce-preparation" id="how-a-custom-platform-source-changes-adobe-commerce-preparation"></a>

When the Source Platform is a Custom Platform, Adobe Commerce preparation usually needs a more detailed interpretation layer.

Company relationships, pricing rules, customer grouping, catalog access, content timing, custom attributes, route behavior, and integration identifiers may sit in non-standard structures that do not align directly with Adobe Commerce. In those cases, preparation should include:

* clearer classification of source-side company and customer meaning
* earlier review of pricing and visibility logic
* separation between native Adobe Commerce structures and custom source behavior
* tighter sample selection for Demo Migration and later validation
* review of whether custom migration logic adjustment or bespoke handling is needed

A Custom Platform source into Adobe Commerce should normally be reviewed through Custom Service because the migration depends on interpreting and rebuilding source-side meaning, not only moving standard records.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce preparation is strongest when the business defines the target model before judging the migration result. Companies, shared catalogs, customer groups, Content Staging, scope hierarchy, URL rewrites, account continuity, and custom enterprise behavior all need clear decisions because they determine whether the migrated store will behave correctly after launch.

The safest preparation work does not try to inspect everything equally. It identifies the commercial structures that matter most, decides how Adobe Commerce should represent them, and builds representative samples that can prove whether the target is ready for full migration.

Before moving deeper into execution, prepare the company accounts, shared catalogs, customer-group rules, staged-content cases, scope decisions, high-value routes, and custom behaviors that carry the most business risk. If those areas are still difficult to classify, use Demo Migration evidence and Live Chat to clarify whether the issue is routine Adobe Commerce planning, migration-path complexity, or a Custom Service requirement.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating into Adobe Commerce?**

Usually the first priority is the future company and account structure, followed by shared catalog access, pricing rules, customer-group interaction, staged content, scope hierarchy, high-value routes, and representative Demo Migration samples.

**Why are shared catalogs such an important preparation topic?**

Shared catalogs can control product access and custom pricing for specific company contexts. If the business has not defined who should see which catalog and which prices, the target can look complete while exposing the wrong commercial outcome.

**Should Adobe Commerce preparation focus mainly on product data?**

No. Product data still matters, but Adobe Commerce preparation is often more sensitive around company relationships, shared catalogs, customer groups, staged content, scope hierarchy, account continuity, URL destinations, and enterprise behavior connected to extensions or integrations.

**How should staged content be prepared before migration?**

The business should identify campaigns, scheduled content, price rules, CMS Pages, CMS Blocks, products, and categories whose timing matters after launch. These examples should be reviewed as timed behavior rather than only as static content.

**When does Adobe Commerce preparation usually point toward Custom Service?**

Custom Service review is usually needed when the Source Platform is a Custom Platform, when important behavior depends on custom fields or extensions, when outside-system identifiers must be preserved, or when pricing, visibility, workflow, or catalog logic needs custom migration logic adjustment beyond standard service capability.
