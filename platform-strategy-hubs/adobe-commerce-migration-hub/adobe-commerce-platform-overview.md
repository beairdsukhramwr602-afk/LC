# Adobe Commerce Platform Overview

Adobe Commerce is an enterprise e-commerce Target Platform for merchants whose online store must support governed catalog control, B2B account structures, scoped storefronts, account-specific pricing, staged content operations, integrations, and implementation flexibility. A migration to Adobe Commerce should be planned as a move into a governed commerce operating environment, not only as a transfer of products, customers, orders, categories, and content records.

The platform shares architectural roots with Magento, but Adobe Commerce migration planning should not treat the Target Platform as a Magento duplicate. Adobe Commerce adds enterprise operating expectations around B2B company accounts, shared catalogs, quote and purchasing workflows, Content Staging, broader governance, and integration-heavy operations. These capabilities can create strong long-term value, but they also require clearer source-data review, target-structure planning, service-scope decisions, and validation responsibility before launch.

A strong Adobe Commerce migration plan starts by separating three questions. Which source records can move into standard Adobe Commerce structures? Which target-side features must be configured before migrated data can behave correctly? Which source behaviors depend on custom fields, extensions, outside-system identifiers, unsupported source logic, or bespoke workflows that may require Add-ons or Custom Service review?

### What Makes Adobe Commerce Different as a Target Platform <a href="#what-makes-adobe-commerce-different-as-a-target-platform" id="what-makes-adobe-commerce-different-as-a-target-platform"></a>

Adobe Commerce is commonly selected when a store has outgrown a simple catalog-and-checkout model. The target environment can support sophisticated product structures, scoped storefronts, B2B account governance, account-specific catalog visibility, governed pricing, scheduled campaigns, and enterprise integrations. These strengths are useful only when the merchant defines how the target store should operate before treating the migration result as final.

| Adobe Commerce area             | What it means for the target store                                                                                                        | Migration planning implication                                                                                    |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Enterprise storefront scope     | Websites, stores, and store views can control business context, catalog visibility, language, content, and configuration.                 | Multi-brand, multi-region, multilingual, or multi-currency stores need scope decisions before Full Migration.     |
| Catalog flexibility             | Product types, attributes, attribute sets, categories, pricing, inventory, and merchandising behavior can carry operational meaning.      | Representative samples should include complex catalog cases, not only simple products.                            |
| B2B company accounts            | Business customers can depend on company administrators, users, roles, permissions, approval behavior, and commercial settings.           | Customer migration must consider account structure and buying responsibility, not only email addresses.           |
| Shared catalogs                 | Different companies or buyer groups can see different product selections and prices.                                                      | Catalog visibility and pricing rules should be planned before customer-facing validation.                         |
| Quotes and purchasing workflows | B2B buyers may rely on quote requests, purchase orders, approval rules, payment restrictions, or shipping restrictions.                   | Historical orders and live buying paths should be interpreted through the intended target buying model.           |
| Content Staging                 | Products, categories, price rules, CMS Pages, CMS blocks, and campaigns can be scheduled.                                                 | Migration timing should account for scheduled launches, promotions, and merchandising changes.                    |
| URL and SEO governance          | Products, categories, CMS Pages, redirects, rewrites, and custom routes can affect organic traffic and customer continuity.               | High-value routes should be inventoried before launch validation.                                                 |
| Extensions and integrations     | Adobe Commerce stores often connect with ERP, PIM, CRM, warehouse, tax, payment, shipping, analytics, marketplace, and marketing systems. | External identifiers, custom fields, and integration-owned behavior may require Add-ons or Custom Service review. |

Adobe Commerce therefore requires more than a count of migrated entities. The migration plan must define what transferred records are expected to do after they reach the target store.

### Adobe Commerce Is Related to Magento but Has a Different Planning Burden <a href="#adobe-commerce-is-related-to-magento-but-has-a-different-planning-burden" id="adobe-commerce-is-related-to-magento-but-has-a-different-planning-burden"></a>

Adobe Commerce and Magento Open Source are related platforms, but they should not be collapsed into the same migration decision. Magento Open Source can be a flexible open-source commerce foundation. Adobe Commerce is positioned for merchants that need a broader enterprise operating model, including Adobe Commerce B2B capabilities, governed storefront operations, and enterprise-grade commercial workflows.

That distinction matters because an Adobe Commerce migration may need to preserve or prepare for capabilities that are not part of a simpler Target Platform plan. A merchant moving into Adobe Commerce may be planning company-specific catalogs, quote-based sales, account hierarchies, staged campaigns, custom approval flows, scoped storefronts, or integrated enterprise operations. Those expectations should be reflected in the migration scope before the service path is finalized.

The difference also affects validation. A customer record may appear complete in the Admin, but the practical test for an Adobe Commerce B2B store may be whether the right company user can access the right shared catalog, see the correct price, use the correct payment and shipping options, request a quote, and place an order under the intended approval rules.

### Enterprise Scope Shapes How Data Should Behave <a href="#enterprise-scope-shapes-how-data-should-behave" id="enterprise-scope-shapes-how-data-should-behave"></a>

Adobe Commerce uses websites, stores, and store views to control how storefronts, catalogs, configuration, language, currency, and content apply. This scope model is one of the earliest planning points because it can change how migrated values are interpreted after they arrive in the target store.

A merchant may use separate websites for regional operations, different brands, country-specific catalogs, business models, tax contexts, or currency requirements. Stores and store views can support different navigation structures, localized content, or language-specific storefront presentation. Some values may be global, while other values belong at website, store, or store-view level.

Source data should not be mapped blindly into one universal target context. Product names, descriptions, URL keys, category assignments, CMS Pages, Blog Posts, customer visibility, pricing assumptions, and configuration-sensitive values may need to be understood through the intended Adobe Commerce scope. Scope errors can create practical failures: localized content appearing in the wrong storefront, products assigned to the wrong commercial context, duplicate URLs, missing translations, incorrect pricing visibility, or confusing category navigation.

A migration plan for Adobe Commerce should define the target scope model before Full Migration. If the source store has multiple languages, regions, storefronts, brands, currencies, or customer segments, the Demo Migration sample should include those differences.

### B2B Features Make Customer Data More Complex <a href="#b2b-features-make-customer-data-more-complex" id="b2b-features-make-customer-data-more-complex"></a>

For B2B merchants, Adobe Commerce can represent business relationships through company accounts. A company account can include the business identity, company administrator, company users, role permissions, legal address, customer group or shared catalog assignment, credit settings, quote permission, purchase order permission, payment methods, and shipping methods.

That changes the meaning of customer migration. A customer is not always only an individual buyer. The customer may be a company administrator, a purchasing user, a billing contact, a member of a company hierarchy, or a buyer whose permissions depend on company-level settings. Losing those relationships can create more damage than losing a display field because they affect access, pricing, ordering rights, and approval workflows.

Adobe Commerce B2B planning should identify which source data represents individual contacts and which data represents account-level business relationships. Source platforms with wholesale accounts, dealer portals, contract pricing, purchase permissions, sales-representative assignments, or custom account fields often need deeper review before standard migration assumptions are made.

### Shared Catalogs and Pricing Visibility Need Early Definition <a href="#shared-catalogs-and-pricing-visibility-need-early-definition" id="shared-catalogs-and-pricing-visibility-need-early-definition"></a>

Shared catalogs are one of the clearest examples of why Adobe Commerce migration planning must go beyond record transfer. Shared catalogs can control which products and prices different companies or buyer groups see. If the source store has wholesale pricing, distributor pricing, contract pricing, private catalogs, customer-group visibility, or account-specific product access, the target plan should define how those rules should work in Adobe Commerce.

The risk is not only that a price fails to migrate. The higher risk is commercial exposure: the wrong buyer may see a restricted product, a private price may become visible to a broader audience, or a company may lose access to products it needs to purchase. These outcomes can damage customer trust and operational control even when the product records themselves look complete.

Planning should include representative buyer segments, company accounts, shared catalog assignments, restricted products, public products, private prices, and at least one negative test for buyers who should not see certain products or pricing. If the source platform stores this behavior through custom logic, external contracts, sales-team spreadsheets, or extension-owned data, the scope may require Custom Service review.

### Content Staging and Campaign Timing Affect Launch Planning <a href="#content-staging-and-campaign-timing-affect-launch-planning" id="content-staging-and-campaign-timing-affect-launch-planning"></a>

Adobe Commerce can support staged content and scheduled commercial changes. Merchants may use scheduled updates for product pages, category changes, price rules, CMS Pages, CMS blocks, campaigns, seasonal launches, or merchandising windows. These features are valuable for enterprise operations but can make migration timing more sensitive.

A migration that transfers current data without reviewing scheduled changes may produce an incomplete launch result. A target store may contain the visible version of a product or page but not the staged version needed for an upcoming campaign. Conversely, a staged promotion may be configured in the target store while migrated data is still being validated.

Planning should identify active campaigns, near-term scheduled updates, launch-sensitive pages, promotion windows, pricing changes, category updates, and content dependencies. This helps the merchant decide whether standard migration timing is sufficient or whether additional planning is needed around launch readiness and post-migration adjustments.

### Integrations Influence What Must Be Preserved <a href="#integrations-influence-what-must-be-preserved" id="integrations-influence-what-must-be-preserved"></a>

Adobe Commerce is often part of a larger commerce stack. Enterprise merchants may connect the target store to ERP, PIM, CRM, warehouse, tax, payment, shipping, analytics, marketplace, marketing, support, or business intelligence systems. Those integrations may depend on identifiers, custom fields, status values, pricing references, account codes, SKU rules, order attributes, or customer segmentation logic.

A migration that preserves storefront-visible records but loses integration identifiers can still create operational failure. Products may appear on the storefront while warehouse synchronization breaks. Customers may exist in the target store while ERP account matching fails. Orders may transfer for historical reference while fulfillment, reporting, or support systems can no longer interpret them correctly.

Integration-sensitive fields should be identified before migration scope is finalized. When the values exist in standard source fields and only need mapping or configuration, Add-ons may be relevant. When they rely on unsupported structures, extension-owned data, external systems, bespoke logic, or transformation rules that are outside standard coverage, Custom Service review is usually safer.

### What Should Be Decided Before Migration Starts <a href="#what-should-be-decided-before-migration-starts" id="what-should-be-decided-before-migration-starts"></a>

Adobe Commerce planning should convert platform complexity into practical decisions before the migration is configured. The goal is not to document every future business rule in detail. The goal is to identify the target behaviors that must be correct for the migrated store to function after launch.

| Planning question                                                                             | Why it matters                                                                                          |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Which websites, stores, and store views will exist at launch?                                 | Scope affects product values, category structure, content, URLs, currency, language, and configuration. |
| Which source customer records represent companies, company users, or individual buyers?       | B2B account relationships may require more planning than standard customer transfer.                    |
| Which products or prices vary by company, customer group, contract, region, or buyer segment? | Shared catalogs and price visibility must be validated by buyer context.                                |
| Which source fields are needed by integrations or internal operations?                        | External systems may depend on identifiers that are not obvious in storefront review.                   |
| Which staged campaigns, promotions, or content updates matter near launch?                    | Launch timing can affect what data version should be validated.                                         |
| Which custom fields, extensions, or outside-system records are business-critical?             | Unsupported or bespoke structures may require Custom Service planning.                                  |
| Which sample records should be included in Demo Migration review?                             | Representative samples help reveal scope, B2B, catalog, content, and integration issues early.          |

These decisions also help define the appropriate service path. Standard Service may fit a relatively clean Adobe Commerce migration where source data maps predictably to supported structures. Managed Service may fit when the merchant wants Next-Cart to perform migration execution and coordinate the process under an agreed scope. Add-ons may support filtering, mapping, or data configuration needs. Custom Service should be considered when the migration depends on unsupported source structures, complex B2B relationships, extension-owned data, outside-system identifiers, or bespoke transformation logic.

### How Adobe Commerce Changes Migration Validation <a href="#how-adobe-commerce-changes-migration-validation" id="how-adobe-commerce-changes-migration-validation"></a>

Adobe Commerce validation should prove more than whether data exists. It should prove whether migrated data behaves correctly in the target business model. The validation sample should include complex products, scoped storefront values, localized content, company accounts, shared catalogs, restricted products, customer-group behavior, priority URLs, CMS Pages, Blog Posts, inventory-sensitive items, integration-dependent records, and any custom-scope items included in the service.

For B2B stores, validation should include logged-in buyer behavior. A company administrator, purchasing user, and ordinary buyer may need different access. They may see different catalogs, prices, payment methods, shipping options, quote permissions, or purchase order workflows. A single generic storefront test is not enough for an Adobe Commerce B2B migration.

Final verification remains the customer’s responsibility. Next-Cart can support the migration according to the selected service model and agreed scope, but the merchant must confirm that the migrated result matches business expectations before launch and after any selected Additional Migration Options.

### When Adobe Commerce Is a Strong Target Platform <a href="#when-adobe-commerce-is-a-strong-target-platform" id="when-adobe-commerce-is-a-strong-target-platform"></a>

Adobe Commerce is usually a strong Target Platform when the merchant needs enterprise commerce structure and has the operational readiness to manage it. Strong-fit scenarios often include complex catalogs, multiple storefront scopes, B2B account management, account-specific pricing, quote or purchase workflows, staged campaigns, custom merchandising rules, and integration-heavy operations.

Adobe Commerce can be excessive when the merchant needs only a simple product catalog, basic checkout, minimal customization, and low operational overhead. In those cases, the platform may introduce governance and implementation responsibilities that outweigh its value. Fit analysis belongs in the next article, but the platform overview should make one point clear: Adobe Commerce is most valuable when the business needs the structure it provides and can validate that structure before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce is best understood as an enterprise commerce operating environment rather than a simple destination for store records. Its value comes from governed catalog behavior, B2B account structures, scoped storefronts, controlled pricing, staged content, and integration readiness. Those same strengths increase the importance of source-data review, target-structure planning, service-scope clarity, representative Demo Migration samples, and business-led validation.

A successful Adobe Commerce migration starts with a clear operating model: how the target store should organize catalogs, companies, prices, storefronts, content, integrations, and launch responsibilities. Once those expectations are defined, the migration can be scoped, tested, and validated with fewer surprises.

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Is Adobe Commerce the same as Magento?**

No. Adobe Commerce shares a Magento-derived architecture, but it should not be planned as a generic Magento target. Adobe Commerce adds enterprise commerce capabilities and operational expectations, including B2B company accounts, shared catalogs, Content Staging, governed pricing, and broader integration planning.

**Do all Adobe Commerce migrations require Custom Service?**

No. Some Adobe Commerce migrations can fit Standard Service or Managed Service when the source data maps cleanly to supported structures. Custom Service becomes more important when the migration depends on unsupported B2B relationships, extension-owned data, custom fields, external identifiers, bespoke workflows, or transformation rules outside standard coverage.

**Why are company accounts important in Adobe Commerce migration planning?**

Company accounts can control buyer relationships, roles, permissions, shared catalog access, pricing visibility, quote behavior, purchase order use, payment methods, and shipping methods. Treating company buyers as ordinary customer records can break B2B purchasing after launch.

**Should Adobe Commerce validation focus only on the Admin panel?**

No. Admin review is useful, but Adobe Commerce validation should also test storefront behavior, buyer permissions, shared catalog visibility, pricing, URLs, scoped content, checkout behavior, and integration-sensitive records. The migrated data must behave correctly for the intended business users.

**When should Add-ons be considered for Adobe Commerce?**

Add-ons may be relevant when the migration needs filtering, mapping, or data configuration beyond a default setup. They are appropriate when the source data is available and the requirement fits Add-on scope. Unsupported business logic, custom platform behavior, extension-owned data, or outside-system dependencies may require Custom Service instead.

**How should Additional Migration Options be considered for Adobe Commerce?**

Additional Migration Options matter when source-store activity continues after the initial Full Migration or when the merchant needs a later migration action within the purchased service license. Adobe Commerce merchants should validate any additional migration result against the same scope, B2B, catalog, URL, content, and integration expectations used for launch readiness.
