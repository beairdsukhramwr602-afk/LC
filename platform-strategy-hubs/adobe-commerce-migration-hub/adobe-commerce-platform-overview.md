# Adobe Commerce Platform Overview

Adobe Commerce is an enterprise e-commerce Target Platform for businesses that need governed catalog control, B2B account structures, buyer-specific pricing, scoped storefronts, staged content operations, and integration-ready commerce processes. A migration to Adobe Commerce should be planned as a move into an operating environment, not only as a transfer of products, customers, orders, categories, and content records.

Adobe Commerce shares architectural roots with Magento Open Source, but migration planning should not treat it as a generic Magento destination. Adobe Commerce can introduce B2B company accounts, shared catalogs, quote and purchasing workflows, Content Staging, company-level permissions, and broader governance expectations. These capabilities can create strong long-term value, but they also require clearer source-data review, target-structure decisions, service-scope control, and business-led validation before launch.

A strong Adobe Commerce migration plan starts by separating three questions. Which source records can move into standard Adobe Commerce structures? Which target-side features must be configured before migrated data can behave correctly? Which source behaviors depend on custom fields, extensions, outside-system identifiers, unsupported source logic, or bespoke workflows that may require Add-ons or Custom Service review?

### What Adobe Commerce Means as a Target Platform <a href="#what-adobe-commerce-means-as-a-target-platform" id="what-adobe-commerce-means-as-a-target-platform"></a>

Adobe Commerce is usually selected when the target store needs more than a basic catalog and checkout. The platform can support sophisticated products, scoped storefronts, account-level buying relationships, catalog visibility control, commercial pricing governance, scheduled content, and enterprise integrations.

That power changes how migration scope should be evaluated. Product records, customer accounts, order history, CMS Pages, Blog Posts, categories, and redirects are still important, but they are not enough by themselves. The migration plan also needs to define how those records should behave in the Adobe Commerce target environment.

| Adobe Commerce area                  | What it means for the target store                                                                                                    | Migration planning implication                                                                                |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Website, store, and store-view scope | Different business contexts can have different catalog, content, language, currency, and configuration behavior.                      | Multi-region, multi-brand, multilingual, or multi-currency stores need scope decisions before Full Migration. |
| Product and catalog flexibility      | Simple, configurable, grouped, bundle, virtual, downloadable, and gift card products can carry different business meaning.            | Demo Migration samples should include complex catalog cases, not only simple products.                        |
| B2B company accounts                 | Business buyers can depend on company administrators, users, roles, permissions, addresses, and purchasing settings.                  | Customer migration must consider account relationships, not only individual customer records.                 |
| Shared catalogs                      | Product visibility and pricing can vary by company or buyer context.                                                                  | Pricing and catalog-access validation should use representative buyer accounts.                               |
| Quotes and purchasing workflows      | Buyers may use quote requests, purchase orders, approval behavior, payment restrictions, or shipping restrictions.                    | Order and customer validation should reflect the intended B2B buying model.                                   |
| Content Staging                      | Products, categories, rules, CMS content, and campaigns can be scheduled.                                                             | Launch timing should account for staged merchandising and promotional changes.                                |
| URL and SEO governance               | Products, categories, CMS Pages, redirects, rewrites, and custom routes affect customer continuity.                                   | High-value routes should be inventoried and validated before launch.                                          |
| Integrations and extensions          | Enterprise stores often connect with ERP, PIM, CRM, warehouse, tax, payment, shipping, analytics, marketplace, and marketing systems. | External identifiers and extension-owned data may require Add-ons or Custom Service review.                   |

Adobe Commerce migration planning therefore needs a behavior-first view of data. The question is not only whether records can be moved. The more important question is whether they will support the intended catalog, buyer, pricing, content, and integration behavior after migration.

### Why Adobe Commerce Requires Enterprise Migration Planning <a href="#why-adobe-commerce-requires-enterprise-migration-planning" id="why-adobe-commerce-requires-enterprise-migration-planning"></a>

Adobe Commerce is built for businesses with more governance than a small retail store usually needs. A merchant may operate multiple websites, sell through different brands, separate B2B and B2C buying paths, apply different catalogs to different companies, localize storefront content, or depend on external systems for product, price, inventory, customer, and order operations.

These operating requirements make migration planning more sensitive to structure. A migrated product may look complete in the Admin, but still fail the business requirement if it is assigned to the wrong website, lacks the correct configurable relationship, misses a required attribute, uses an incorrect URL key, has an incorrect shared catalog assignment, or cannot support the intended inventory source behavior.

Adobe Commerce should also be distinguished from Adobe Commerce Cloud hosting or implementation decisions. Hosting, deployment pipelines, environments, and release process affect the overall project, but the migration scope should concentrate on data structures, target configuration dependencies, service boundaries, and validation responsibilities.

### Website, Store, and Store-View Scope <a href="#website-store-and-store-view-scope" id="website-store-and-store-view-scope"></a>

Adobe Commerce uses website, store, and store-view scope to control how storefronts, catalogs, configuration, language, currency, and content apply. This scope model is one of the earliest migration planning decisions because it can change how migrated values are interpreted.

A merchant may use separate websites for regions, brands, business models, tax contexts, base currencies, or customer-account separation. Stores can support different catalog navigation through root categories. Store views can support language, localized presentation, and translated content. Some values may be global, while other values belong to a website, store, or store view.

Source data should not be mapped into one universal target context without review. Product names, descriptions, URL keys, category assignments, CMS Pages, Blog Posts, pricing assumptions, customer visibility, and configuration-sensitive fields may need to be understood through the intended Adobe Commerce scope. Scope errors can create visible failures such as localized content appearing in the wrong storefront, products assigned to the wrong commercial context, duplicate URLs, missing translations, wrong currency assumptions, or confusing category navigation.

### Product Structure and Catalog Governance <a href="#product-structure-and-catalog-governance" id="product-structure-and-catalog-governance"></a>

Adobe Commerce product structure can carry operational meaning. Simple products may stand alone or support configurable products. Configurable products can present selectable options while each variation remains a separate simple product with its own SKU and inventory tracking. Grouped, bundle, virtual, downloadable, and gift card products can each require different interpretation during migration.

Attributes and attribute sets are also central. Attribute design affects filtering, product detail pages, configurable-product options, internal operations, merchandising, and integration behavior. A color, size, material, brand, compatibility value, or technical specification may be more than display content. It may determine how buyers find products, how product variants are selected, how data flows to external systems, and how internal teams manage the catalog.

Adobe Commerce planning should identify which source fields are ordinary product information and which fields support catalog logic. Product types, parent-child relationships, attribute sets, configurable attributes, custom options, categories, related products, cross-sells, up-sells, inventory-sensitive products, and integration identifiers should be represented in the Demo Migration sample.

### B2B Company Accounts and Buyer Relationships <a href="#b2b-company-accounts-and-buyer-relationships" id="b2b-company-accounts-and-buyer-relationships"></a>

Adobe Commerce B2B can represent business customers through company accounts, company administrators, users, roles, permissions, addresses, purchasing settings, and catalog access. This changes the meaning of customer migration. A buyer may not be only an individual account. The buyer may be part of a company hierarchy with permissions that affect access, pricing, payment, shipping, quote behavior, or purchasing approval.

If a source store uses wholesale accounts, dealer portals, distributor pricing, contract pricing, sales-representative relationships, approval workflows, or custom account fields, those structures should be reviewed before migration is scoped. Losing a company relationship can be more damaging than losing a display field because it can prevent a buyer from placing the correct order under the correct commercial rules.

For Adobe Commerce B2B projects, customer validation should include logged-in buyer scenarios. A company administrator, purchasing manager, ordinary buyer, and restricted user may need different access. Validation should confirm that these users see the right catalog, prices, addresses, payment methods, shipping options, quote permissions, and purchase behavior.

### Shared Catalogs, Pricing, and Commercial Visibility <a href="#shared-catalogs-pricing-and-commercial-visibility" id="shared-catalogs-pricing-and-commercial-visibility"></a>

Shared catalogs are a central Adobe Commerce planning point for B2B and wholesale operations. They can control product visibility and custom pricing for different companies. If the source store has account-specific products, private catalogs, customer-group pricing, contract pricing, dealer discounts, region-based availability, or sales-team price rules, Adobe Commerce migration planning should define how those behaviors should work in the target store.

The risk is not only that a price does not migrate. The larger risk is commercial exposure or buyer disruption. A restricted product may become visible to the wrong buyer, a private price may appear to a broader audience, or a company may lose access to products needed for purchasing. These problems can damage customer trust even when product records appear complete.

Planning should include representative companies, buyer roles, shared catalog assignments, customer groups, public products, restricted products, private prices, and at least one negative test for buyers who should not see specific products or pricing.

### Content, Campaign Timing, and URL Continuity <a href="#content-campaign-timing-and-url-continuity" id="content-campaign-timing-and-url-continuity"></a>

Adobe Commerce migration planning should account for content and route behavior, not only catalog and customer data. CMS Pages, CMS blocks, Blog Posts, product URLs, category URLs, redirects, rewrites, and custom landing pages can affect navigation, SEO continuity, paid campaigns, support documentation, and customer trust.

Content Staging adds another timing dimension. Products, categories, catalog price rules, cart price rules, CMS Pages, CMS blocks, and campaigns may be scheduled. A migration near a campaign launch, seasonal merchandising change, catalog refresh, or B2B price update should define which version of content and commercial data should be reviewed.

URL continuity should be handled deliberately. High-value product, category, CMS, Blog Post, and campaign URLs should be identified before launch. Redirect behavior should be validated against customer-facing routes, not only the existence of redirect records.

### Integrations, Extensions, and Custom Data <a href="#integrations-extensions-and-custom-data" id="integrations-extensions-and-custom-data"></a>

Adobe Commerce stores often depend on integrations and extensions. ERP, PIM, CRM, warehouse, tax, payment, shipping, analytics, loyalty, marketplace, and marketing systems may depend on specific product identifiers, customer identifiers, order fields, inventory values, status logic, or custom attributes.

Some migration requirements can be handled through Add-ons when the data exists in supported fields and the need fits filtering, mapping, or configuration scope. Custom Service review becomes more important when the requirement depends on extension-owned tables, unsupported source structures, custom modules, external-system reconciliation, bespoke transformation logic, or business workflows that cannot be inferred from standard records.

These boundaries should be defined early. Otherwise, a migrated Adobe Commerce store can look acceptable in the Admin while integrations fail because hidden identifiers, custom fields, or external-system dependencies were not included in the migration scope.

### What Should Be Decided Before Migration Starts <a href="#what-should-be-decided-before-migration-starts" id="what-should-be-decided-before-migration-starts"></a>

Adobe Commerce planning should convert platform complexity into practical migration decisions before configuration begins. The goal is to identify target behaviors that must be correct after migration.

| Planning question                                                                             | Why it matters                                                                                                           |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Which websites, stores, and store views will exist at launch?                                 | Scope affects product values, category structure, content, URLs, language, currency, and configuration.                  |
| Which source customer records represent companies, company users, or ordinary buyers?         | B2B account relationships may require more planning than standard customer transfer.                                     |
| Which products or prices vary by company, contract, region, customer group, or buyer segment? | Shared catalogs and pricing visibility must be validated by buyer context.                                               |
| Which product types and attribute sets carry operational meaning?                             | Catalog behavior may depend on parent-child relationships, configurable attributes, and internal product classification. |
| Which source fields are needed by integrations or internal operations?                        | External systems may depend on identifiers that are not obvious during storefront review.                                |
| Which staged campaigns, promotions, or content updates matter near launch?                    | Launch timing can affect which data version should be migrated and validated.                                            |
| Which custom fields, extensions, or outside-system records are business-critical?             | Unsupported or bespoke structures may require Custom Service planning.                                                   |
| Which sample records should be included in Demo Migration review?                             | Representative samples help reveal scope, B2B, catalog, content, pricing, and integration issues early.                  |

These decisions help define the appropriate service path later in the hub. Standard Service may fit cleaner Adobe Commerce migrations where source data maps predictably to supported structures. Managed Service may fit when the merchant wants Next-Cart to perform migration execution under an agreed scope. Add-ons may support filtering, mapping, or data configuration needs. Custom Service should be considered when the migration depends on unsupported B2B relationships, extension-owned data, custom fields, external identifiers, or bespoke transformation logic.

### How Adobe Commerce Changes Migration Validation <a href="#how-adobe-commerce-changes-migration-validation" id="how-adobe-commerce-changes-migration-validation"></a>

Adobe Commerce validation should prove more than whether migrated data exists. It should prove whether migrated data behaves correctly in the target business model. The validation sample should include complex products, scoped storefront values, localized content, company accounts, shared catalogs, restricted products, customer-group behavior, priority URLs, CMS Pages, Blog Posts, inventory-sensitive items, integration-dependent records, and any custom-scope items included in the service.

For B2B stores, validation should include logged-in buyer behavior. Different company users may see different catalogs, prices, payment methods, shipping options, quote permissions, or purchase order behavior. A single generic storefront test is not enough for an Adobe Commerce B2B migration.

Final verification remains the customer’s responsibility. Next-Cart can support the migration according to the selected Migration Service and agreed scope, but the merchant must confirm that the migrated result matches business expectations before launch.

### When Adobe Commerce Is a Strong Target Platform <a href="#when-adobe-commerce-is-a-strong-target-platform" id="when-adobe-commerce-is-a-strong-target-platform"></a>

Adobe Commerce is usually a strong Target Platform when the merchant needs enterprise commerce structure and has the operational readiness to manage it. Strong-fit scenarios often include complex catalogs, multiple storefront scopes, B2B account management, account-specific pricing, quote or purchase workflows, staged campaigns, custom merchandising rules, and integration-heavy operations.

Adobe Commerce can be excessive when the business needs only a simple product catalog, basic checkout, minimal customization, and low operational overhead. The platform is most valuable when the business needs the structure it provides and can validate that structure before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce is best understood as an enterprise commerce operating environment rather than a simple destination for store records. Its value comes from governed catalog behavior, B2B account structures, scoped storefronts, controlled pricing, staged content, and integration readiness. Those same strengths increase the importance of source-data review, target-structure planning, service-scope clarity, representative Demo Migration samples, and business-led validation.

A successful Adobe Commerce migration starts with a clear operating model: how the target store should organize catalogs, companies, prices, storefronts, content, integrations, and launch responsibilities. Once those expectations are defined, the migration can be scoped, tested, and validated with fewer surprises.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Adobe Commerce the same as Magento?**

No. Adobe Commerce shares Magento-derived architecture, but it should not be planned as a generic Magento target. Adobe Commerce adds enterprise commerce capabilities and operating expectations, including B2B company accounts, shared catalogs, Content Staging, governed pricing, and broader integration planning.

**Do all Adobe Commerce migrations require Custom Service?**

No. Some Adobe Commerce migrations can fit Standard Service or Managed Service when source data maps cleanly to supported structures. Custom Service becomes more important when the migration depends on unsupported B2B relationships, extension-owned data, custom fields, external identifiers, bespoke workflows, or transformation rules outside standard coverage.

**Why are company accounts important in Adobe Commerce migration planning?**

Company accounts can control buyer relationships, roles, permissions, shared catalog access, pricing visibility, quote behavior, purchase order use, payment methods, and shipping methods. Treating company buyers as ordinary customer records can break B2B purchasing after launch.

**Should Adobe Commerce validation focus only on the Admin panel?**

No. Admin review is useful, but Adobe Commerce validation should also test storefront behavior, buyer permissions, shared catalog visibility, pricing, URLs, scoped content, checkout behavior, and integration-sensitive records. The migrated data must behave correctly for the intended business users.

**When should Add-ons be considered for Adobe Commerce?**

Add-ons may be relevant when the migration needs filtering, mapping, or data configuration beyond a default setup. They are appropriate when source data is available and the requirement fits Add-on scope. Unsupported business logic, custom platform behavior, extension-owned data, or outside-system dependencies may require Custom Service instead.
