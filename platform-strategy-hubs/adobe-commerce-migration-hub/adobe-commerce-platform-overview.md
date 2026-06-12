# Adobe Commerce Platform Overview

Adobe Commerce is an enterprise e-commerce Target Platform for merchants that need governed catalog control, B2B account structures, scoped storefronts, custom pricing, staged content operations, integrations, and implementation flexibility. A migration to Adobe Commerce should be planned as a move into an operating environment where records, rules, storefront scope, account permissions, pricing visibility, content timing, and external systems may all influence how transferred data behaves after launch.

The platform shares a foundation with Magento Open Source, but the planning burden is not identical. Adobe Commerce adds enterprise and B2B capabilities that can change migration expectations: company accounts, company users, shared catalogs, negotiated buying workflows, purchase permissions, company credit, quotes, purchase orders, Content Staging, and broader governance requirements. These capabilities can be valuable, but they also make early planning more important. A product, customer, order, page, or URL is rarely just a transferred record when it affects company visibility, pricing rules, catalog access, staged campaigns, regional storefronts, or downstream business systems.

A strong Adobe Commerce migration plan starts by separating three questions. First, which source records can move into standard Adobe Commerce structures? Second, which target-side features must be configured before migrated data can behave correctly? Third, which source behaviors depend on custom fields, extensions, outside-system identifiers, unsupported source logic, or bespoke workflows that need Add-ons or Custom Service review before the service scope is finalized?

### What Makes Adobe Commerce Different as a Target Platform <a href="#what-makes-adobe-commerce-different-as-a-target-platform" id="what-makes-adobe-commerce-different-as-a-target-platform"></a>

Adobe Commerce is often selected when a store has outgrown a simple catalog-and-checkout model. The target environment can support sophisticated product structures, scoped storefronts, B2B account governance, account-specific catalog visibility, custom pricing, scheduled campaigns, and integration-heavy operations. These strengths create migration value only when the target operating model is defined before the migration is treated as complete.

| Adobe Commerce area             | What it means for the target store                                                                                                        | Migration planning implication                                                                                                |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Enterprise storefront scope     | Websites, stores, and store views can shape how content, configuration, and storefront values apply.                                      | Multi-brand, multi-region, multilingual, or multi-currency stores need scope decisions before Full Migration.                 |
| Product and catalog flexibility | Product types, attributes, attribute sets, categories, pricing, inventory, and related merchandising rules can carry operational meaning. | Representative product samples should include complex catalog cases, not only simple products.                                |
| B2B company accounts            | Business customers can be represented through company accounts, administrators, users, roles, approval status, and commercial settings.   | Customer migration must consider account structure, buyer identity, and business-account ownership, not only email addresses. |
| Shared catalogs                 | Different companies can see different catalog selections and pricing.                                                                     | Product visibility and custom pricing need planning before customer-facing validation.                                        |
| Quotes and purchase workflows   | B2B buyers may depend on quote requests, purchase orders, payment restrictions, shipping restrictions, or approval processes.             | Historical orders and live buying flows should be interpreted through the target buying model.                                |
| Content Staging                 | Adobe Commerce can schedule content updates for products, categories, price rules, CMS pages, and CMS blocks.                             | Migration timing should avoid breaking campaigns, scheduled launches, or merchandising changes.                               |
| URL and SEO governance          | Products, categories, CMS pages, and custom routes can depend on URL rewrites and redirects.                                              | High-value routes should be inventoried and validated before launch.                                                          |
| Extensions and integrations     | Adobe Commerce stores often connect with ERP, PIM, CRM, warehouse, tax, payment, shipping, analytics, marketplace, and marketing systems. | External identifiers, custom fields, and integration-owned behavior may require Add-ons or Custom Service review.             |

Adobe Commerce therefore requires more than a count of migrated products, customers, orders, categories, and CMS Pages. The migration plan must define what those records are expected to do after they reach the target store.

### Adobe Commerce and Magento Open Source Should Not Be Treated as Identical <a href="#adobe-commerce-and-magento-open-source-should-not-be-treated-as-identical" id="adobe-commerce-and-magento-open-source-should-not-be-treated-as-identical"></a>

Adobe Commerce and Magento Open Source are related, but they should not be collapsed into the same migration decision. Magento Open Source can be a flexible open-source commerce foundation. Adobe Commerce is positioned for merchants that need a broader enterprise feature set, including Adobe Commerce B2B capabilities and Adobe Commerce-only operational features.

That distinction matters because an Adobe Commerce migration may need to preserve or prepare for capabilities that are not part of a simpler Magento Open Source target. A merchant moving into Adobe Commerce may be planning company-specific catalogs, quote-based sales, account hierarchies, staged campaigns, custom approval flows, scoped storefronts, or integrated enterprise operations. Those expectations should be reflected in the migration scope.

The difference also affects validation. A migrated customer record may look complete in the Admin, but the real test for an Adobe Commerce B2B store may be whether the right company user can access the right shared catalog, see the correct price, use the correct payment and shipping options, request a quote, and place an order under the intended approval rules.

### The Enterprise Scope Model Shapes Migration Decisions <a href="#the-enterprise-scope-model-shapes-migration-decisions" id="the-enterprise-scope-model-shapes-migration-decisions"></a>

Adobe Commerce uses a hierarchy of websites, stores, and store views. This scope model is one of the earliest planning points for migration because it can affect how values are stored, displayed, and governed.

A merchant may use separate websites for regional operations, different brands, country-specific catalogs, business models, tax contexts, or currency requirements. Stores and store views can support different navigation structures, languages, localized content, or storefront presentation. Some values may be global, while other values belong at website, store, or store-view level.

This means source data should not be mapped blindly into one universal target context. Product names, descriptions, URL keys, category assignments, CMS Pages, Blog Posts, customer visibility, pricing assumptions, and configuration-sensitive values may need to be understood through the intended Adobe Commerce scope. Scope errors can produce practical failures: localized content appearing in the wrong storefront, products assigned to the wrong catalog context, duplicate URLs, missing translations, incorrect pricing visibility, or confusing category navigation.

A migration plan for Adobe Commerce should define the target scope model before the merchant uses Full Migration as the final transfer. If the source store has multiple languages, regions, storefronts, brands, currencies, or customer groups, the target structure should be validated through a Demo Migration sample that includes those differences.

### B2B Features Make Customer Data More Than Contact Records <a href="#b2b-features-make-customer-data-more-than-contact-records" id="b2b-features-make-customer-data-more-than-contact-records"></a>

For B2B merchants, Adobe Commerce can represent business relationships through company accounts. A company account can include the business identity, company administrator, company users, legal address, customer group or shared catalog assignment, credit settings, quote permission, purchase order permission, payment methods, and shipping methods.

That changes the meaning of customer migration. A customer is not always only an individual buyer. The customer may be a company administrator, a purchasing user, a billing contact, a member of a company hierarchy, or a buyer whose permissions depend on company-level settings. Losing that relationship can create more damage than losing a display field, because it can affect access, pricing, ordering rights, and approval workflows.

Adobe Commerce B2B planning should therefore identify which source data represents individual contacts and which data represents account-level business relationships. Source platforms with wholesale accounts, dealer portals, contract pricing, purchase permissions, sales-representative assignments, or custom account fields often need deeper review before assumptions are made about standard migration coverage.

### Shared Catalogs and Pricing Visibility Require Early Definition <a href="#shared-catalogs-and-pricing-visibility-require-early-definition" id="shared-catalogs-and-pricing-visibility-require-early-definition"></a>

Shared catalogs are one of the clearest examples of why Adobe Commerce migration planning must address behavior, not only data. A shared catalog can determine which products and prices are visible to assigned companies. Custom shared catalogs can create company-specific buying experiences, and catalog access may depend on customer group assignment.

For migration planning, the key question is not only whether products and customers can be transferred. The key question is whether the right companies and buyers will see the right catalog and price after the target store is configured. If shared catalogs are introduced, rebuilt, or redesigned during migration, source customer groups, wholesale tiers, price lists, product assignments, and negotiated pricing rules need to be reconciled with the Adobe Commerce target model.

This is also where Add-ons and Custom Service should be considered carefully. Optional Add-ons may support filtering, mapping, or configuration work when the required behavior fits the service scope. Custom Service may be needed when pricing logic, account relationships, unsupported source behavior, outside-system identifiers, or extension-owned data requires bespoke handling beyond a standard migration path.

### Content Staging Adds Timing to Migration Planning <a href="#content-staging-adds-timing-to-migration-planning" id="content-staging-adds-timing-to-migration-planning"></a>

Adobe Commerce includes Content Staging for scheduled updates. Scheduled updates can affect products, categories, price rules, CMS pages, and CMS blocks. This makes campaign timing part of migration planning for stores that rely on launches, promotions, seasonal updates, brand refreshes, or synchronized merchandising windows.

A migration performed during active campaign preparation can create avoidable confusion if staged updates are not identified. Merchants should know which content is live, which updates are scheduled, which promotions are time-sensitive, and which CMS Pages or catalog changes must be validated close to launch.

Content Staging is not simply a content feature. In a migration context, it can affect the timing of what needs to be transferred, what needs to be recreated, what should be excluded, and what should be validated in the target store. For campaign-sensitive merchants, a clean migration plan should include staging windows, promotion calendars, and high-priority content records before launch decisions are finalized.

### Catalog Architecture Still Matters in Adobe Commerce <a href="#catalog-architecture-still-matters-in-adobe-commerce" id="catalog-architecture-still-matters-in-adobe-commerce"></a>

Adobe Commerce supports multiple product types and structured catalog behavior. Simple products, configurable products, grouped products, virtual products, bundle products, downloadable products, and Adobe Commerce-specific product capabilities can each affect how a source catalog should be interpreted. Configurable products are especially important because storefront options rely on associated simple products with distinct SKUs.

Attributes and attribute sets also require planning. Attributes can affect product pages, search, layered navigation, comparison, reporting, promotions, and internal operations. Attribute sets act as templates for different product families. If source attributes are inconsistent, duplicated, overloaded, or poorly named, migration can transfer the problem into the target store and make filtering, merchandising, or product maintenance harder after launch.

Adobe Commerce catalog planning should identify product families, attribute sets, variant structures, bundle logic, grouped products, downloadable content, category assignments, inventory expectations, and SEO-sensitive product URLs. A small set of representative products should be tested before larger assumptions are accepted.

### Integrations and Custom Logic Influence What Counts as Complete <a href="#integrations-and-custom-logic-influence-what-counts-as-complete" id="integrations-and-custom-logic-influence-what-counts-as-complete"></a>

Adobe Commerce is often part of a larger commerce stack. Product information may come from a PIM. Inventory may depend on warehouse systems. Customer and company data may synchronize with CRM or ERP systems. Orders may be sent to fulfillment, accounting, marketplace, tax, shipping, analytics, or marketing platforms. Storefront behavior may depend on extensions, custom modules, APIs, or theme logic.

For migration planning, integration dependency changes the definition of success. A product that appears correctly in Adobe Commerce may still fail the business process if the SKU, external ID, attribute value, stock source, customer account reference, or order identifier no longer works with another system. A customer may migrate correctly but lose contract-pricing meaning if source-specific account data is not mapped or recreated. A URL may exist but fail SEO continuity if redirects are not planned.

Before Full Migration, merchants should identify which fields, identifiers, and workflows are essential to downstream systems. Unsupported source data, extension-owned records, or custom integration logic should be reviewed early, especially when the source platform is a Custom Platform or a heavily customized legacy environment.

### What Merchants Should Clarify Before Choosing Adobe Commerce <a href="#what-merchants-should-clarify-before-choosing-adobe-commerce" id="what-merchants-should-clarify-before-choosing-adobe-commerce"></a>

Adobe Commerce is strongest when the target project needs enterprise structure and the merchant is prepared to define that structure. It can be excessive for merchants that only need a simple catalog, basic checkout, limited content, and minimal operational ownership.

Before committing to Adobe Commerce as the Target Platform, merchants should clarify the expected operating model:

| Planning question                                                | Why it matters                                                                                              |
| ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Will the store serve B2B buyers, B2C buyers, or both?            | Company accounts, customer groups, shared catalogs, and checkout rules may affect migration scope.          |
| Will different companies need different catalogs or prices?      | Shared catalog and custom-pricing assumptions should be defined before migration.                           |
| Will the business use multiple websites, stores, or store views? | Scope planning affects content, categories, URLs, products, pricing, and configuration-sensitive values.    |
| Are campaigns or promotions scheduled around launch?             | Content Staging and price-rule timing may affect when records should move and how they are validated.       |
| Which source fields are owned by extensions or custom code?      | Unsupported data may require Add-ons, accepted exclusions, or Custom Service review.                        |
| Which external systems depend on migrated identifiers?           | ERP, PIM, CRM, warehouse, marketplace, tax, payment, shipping, and analytics systems may need continuity.   |
| Which records must be proven through Demo Migration?             | Representative samples should include B2B, catalog, scope, pricing, inventory, URL, and content complexity. |

These questions help decide whether the migration can follow a standard supported migration path, whether planning support through Managed Service is appropriate, or whether parts of the project should be reviewed under Custom Service before the service license is finalized.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce is a strong Target Platform for merchants that need enterprise-grade catalog control, B2B account governance, scoped storefronts, shared catalog pricing, scheduled content operations, and integration flexibility. Its value comes from structure and control, but those strengths also raise the migration planning standard.

A successful Adobe Commerce migration should prove that transferred records can support the intended operating model: companies can buy under the right permissions, catalogs show the right products and prices, storefront scope behaves correctly, product structures remain usable, high-value URLs preserve route continuity, and business systems can still rely on the data they need.

Start by reviewing the Adobe Commerce target structure, B2B requirements, shared catalog assumptions, storefront scope, campaign timing, and integration dependencies before estimating the migration path. When source behavior depends on custom fields, unsupported logic, extension-owned data, or company-specific pricing rules, include those examples in the Demo Migration and raise them for Add-ons or Custom Service review before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Adobe Commerce the same as Magento Open Source for migration planning?**

No. Adobe Commerce and Magento Open Source share a related foundation, but Adobe Commerce can include enterprise and B2B capabilities that change migration planning. Company accounts, shared catalogs, Content Staging, governed buying workflows, and enterprise integrations can create requirements that do not exist in a simpler Magento Open Source target.

**Why does B2B data require special planning in Adobe Commerce?**

B2B data may include company accounts, company administrators, company users, roles, shared catalog access, quote permissions, purchase orders, payment methods, shipping methods, credit settings, and customer group assignments. These relationships can affect buying access and pricing behavior after migration.

**Should shared catalogs be configured before or after migration?**

The shared catalog strategy should be defined before migration assumptions are finalized. Product records and customers may transfer successfully, but company-specific visibility and pricing depend on target-side shared catalog configuration and customer or company assignment.

**Does Content Staging automatically migrate with all content?**

No assumption should be made without scope review. Content Staging introduces scheduled updates and campaign timing. Merchants should identify live content, scheduled updates, campaign-sensitive records, and launch-critical CMS Pages or catalog changes before migration.

**When should Custom Service be reviewed for an Adobe Commerce migration?**

Custom Service should be reviewed when the source store has unsupported data structures, company-specific pricing logic, custom B2B workflows, extension-owned fields, outside-system identifiers, custom integration requirements, or a Custom Platform source that cannot be represented safely through a standard supported migration path alone.
