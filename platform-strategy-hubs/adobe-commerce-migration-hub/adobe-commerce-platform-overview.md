# Adobe Commerce Platform Overview

Adobe Commerce should be planned as an enterprise commerce operating environment, not only as a larger Magento-family storefront. A migration into Adobe Commerce can involve ordinary commerce records such as Products, Categories, Customers, Orders, Reviews, Coupons, CMS Pages, and Blog Posts, but the platform often adds a stronger layer of business governance: company accounts, buyer roles, shared catalogs, quote behavior, purchase-order rules, scoped storefronts, scheduled content, custom modules, and external-system dependencies.

That enterprise layer changes how migration planning should begin. The question is not simply whether source records can be moved. The stronger question is whether migrated records will support the commercial rules, buyer relationships, storefront scope, pricing logic, content operations, and integration responsibilities the business expects after launch.

Adobe Commerce shares a Magento-family foundation with Magento Open Source, so product types, attributes, attribute sets, website/store/store-view scope, categories, URLs, and extension-driven customization remain important. The distinction is that Adobe Commerce often introduces enterprise operating expectations on top of those structures. Migration planning should preserve the Magento-family data discipline while giving additional attention to B2B, governance, staging, scale, and organizational accountability.

### Adobe Commerce as an Enterprise Target Platform <a href="#adobe-commerce-as-an-enterprise-target-platform" id="adobe-commerce-as-an-enterprise-target-platform"></a>

Adobe Commerce is usually selected when the target store needs stronger operating control than a small catalog storefront. Merchants may need B2B account structures, contract-like catalog visibility, company-specific purchasing rules, multiple storefronts, localized content, governed merchandising, more formal approval workflows, and integrations with ERP, PIM, CRM, tax, warehouse, marketplace, analytics, or marketing systems.

These requirements turn migration into a business-structure exercise. Product data, customer records, order history, and content still matter, but they must be reviewed through the Adobe Commerce environment that will use them.

| Adobe Commerce area                  | Migration significance                                                                                    | Early planning decision                                                                                                                  |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Website, store, and store-view scope | Storefronts may represent regions, brands, languages, business models, or catalog contexts.               | Decide which values are global, website-level, store-level, or store-view specific.                                                      |
| Product types and attributes         | Product structure can affect variation behavior, filtering, search, merchandising, and integrations.      | Classify product types, attributes, and attribute sets before migration.                                                                 |
| B2B company accounts                 | Business customers may have company admins, users, permissions, credit, quotes, and purchase-order needs. | Decide whether source customer data is individual-account data, company data, or custom relationship data.                               |
| Shared catalogs and pricing          | Product visibility and prices may vary by buyer context.                                                  | Define whether source price lists, customer groups, or contract pricing need supported mapping, configuration, or Custom Service review. |
| Content Staging                      | Merchandising and content changes may be scheduled.                                                       | Separate migrated content from target-side campaign scheduling and governance.                                                           |
| Extensions and integrations          | Enterprise stores often depend on modules and external systems.                                           | Identify unsupported extension records, external IDs, and custom workflows early.                                                        |

Adobe Commerce can support sophisticated commerce operations, but migration quality depends on whether the target structures are defined before Full Migration. Without those decisions, data may arrive in Adobe Commerce but still fail the commercial model.

### The Magento-Family Foundation Still Matters <a href="#the-magento-family-foundation-still-matters" id="the-magento-family-foundation-still-matters"></a>

Adobe Commerce belongs to the Magento-family architecture. That means many migration concerns from Magento Open Source still apply: product types, attributes, attribute sets, categories, store hierarchy, URL rewrites, customer groups, order history, inventory assumptions, modules, and custom fields.

The mistake is treating the relationship as a reason to copy Magento Open Source planning unchanged. Adobe Commerce adds enterprise implications. A source product still needs correct Magento-family product typing, but it may also need buyer-specific visibility or shared catalog pricing. A customer record still needs accurate profile data, but it may also need company membership, account roles, purchasing permissions, or sales-representative context. A CMS Page may need to migrate, but content launch timing may also involve staged updates or campaign governance.

The relationship should therefore be used as a boundary control:

| Shared Magento-family concern                        | Adobe Commerce enterprise extension                                                                |
| ---------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Configurable products and associated simple products | Buyer-specific visibility, B2B pricing, account-based ordering, and enterprise validation samples. |
| Attributes and attribute sets                        | Catalog governance across departments, integrations, and PIM or ERP ownership.                     |
| Website/store/store-view scope                       | Multi-brand, multi-region, multi-language, and B2B/B2C storefront separation.                      |
| Customer groups                                      | Shared catalog assignment, company account behavior, pricing, tax, and commercial rules.           |
| URL rewrites and CMS content                         | SEO continuity plus campaign timing, staged content, and enterprise content approval.              |
| Extensions and custom data                           | Custom Service review when modules or outside systems own business-critical records.               |

This distinction helps keep Adobe Commerce content accurate. Adobe Commerce is not only “Magento with more features.” It is a migration target where the Magento-family data model often has to serve enterprise governance.

### Storefront Scope and Business Structure <a href="#storefront-scope-and-business-structure" id="storefront-scope-and-business-structure"></a>

Adobe Commerce scope decisions should be made early because they can change how migrated records behave. A merchant may use separate websites for brands, countries, business units, B2B and B2C channels, base currencies, tax contexts, or customer-account separation. Stores can control catalog navigation through root categories. Store views often support languages and localized presentation.

Source stores do not always separate these concepts the same way. A source platform may store language values in a translation plugin, brand values in categories, regional prices in custom fields, customer visibility in an app, and B2B permissions in a separate system. If those values are migrated without an Adobe Commerce scope plan, the result can look complete while still being commercially wrong.

Scope planning should answer practical questions:

| Scope question                                                      | Why it matters                                                                                              |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Which websites will exist at launch?                                | Website structure can affect account separation, commercial context, currency, and configuration.           |
| Which stores and root categories support each storefront?           | Navigation and catalog organization may differ by business line or region.                                  |
| Which store views require localized values?                         | Product names, descriptions, URLs, metadata, CMS Pages, and Blog Posts may need language-specific handling. |
| Which values are global and which are scoped?                       | Incorrect inheritance can overwrite localized or business-specific data.                                    |
| Which Source Platform structures are not true Adobe Commerce scope? | Categories, tags, customer groups, or custom fields may be misread as websites or store views.              |

A migration plan should not let all records fall into a default scope unless the business has intentionally chosen that structure.

### Catalog Governance and Product Meaning <a href="#catalog-governance-and-product-meaning" id="catalog-governance-and-product-meaning"></a>

Adobe Commerce catalog governance starts with product meaning. Simple, configurable, grouped, bundle, virtual, downloadable, and gift-card products can each carry different migration implications. Configurable products are especially important because the visible parent product and its associated simple products must preserve SKU, option, price, image, and inventory meaning in a way buyers and administrators can use.

Attributes and attribute sets also need governance. Attributes may support product pages, search, layered navigation, product comparison, promotions, reporting, or integration logic. In an enterprise environment, a poorly migrated attribute can cause more than cosmetic clutter. It can weaken buyer discovery, PIM alignment, ERP references, quote accuracy, marketplace exports, or internal maintenance.

Catalog planning should distinguish display data from operational data:

| Source field type               | Adobe Commerce planning question                                                                |
| ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Product specifications          | Should the value be customer-facing, searchable, filterable, comparable, or internal only?      |
| Variant-driving options         | Should the value support configurable products or another product structure?                    |
| B2B price or availability flags | Do they belong to shared catalogs, customer groups, custom logic, or external systems?          |
| ERP/PIM/marketplace IDs         | Should they map into supported fields, be preserved through Add-ons, or require Custom Service? |
| Old or duplicate attributes     | Should they be cleaned, merged, excluded, or retained for historical reference?                 |

Adobe Commerce migration should not maximize the number of fields migrated. It should preserve the fields that support the target catalog governance model.

### B2B Company Accounts and Buyer Relationships <a href="#b2b-company-accounts-and-buyer-relationships" id="b2b-company-accounts-and-buyer-relationships"></a>

B2B is often the clearest Adobe Commerce distinction from Magento Open Source. Company accounts can introduce company administrators, users, roles, permissions, company credit, purchase-order behavior, quote permissions, payment restrictions, shipping restrictions, and shared catalog relationships. These structures change the meaning of customer migration.

A source customer may not equal a company account. A wholesale customer group may not equal a buyer hierarchy. A dealer price list may not equal a shared catalog. A sales representative field may not equal a native Adobe Commerce company assignment. These differences should be reviewed before migration scope is accepted.

For Adobe Commerce B2B migration planning, prepare representative examples:

| B2B example                                                       | Migration value                                             |
| ----------------------------------------------------------------- | ----------------------------------------------------------- |
| Company with one administrator and multiple buyers                | Tests account hierarchy and user relationship expectations. |
| Company assigned to buyer-specific pricing or product visibility  | Tests shared catalog or customer-group implications.        |
| Customer with quote or purchase-order workflow                    | Exposes target-side configuration and validation needs.     |
| Company with credit or restricted payment/shipping methods        | Separates historical data from live commercial setup.       |
| Source B2B record controlled by custom fields or external CRM/ERP | Identifies Custom Service or integration review needs.      |

B2B migration success is not proven by customer record counts. It is proven when the buyer can sign in, see the correct catalog and pricing, use the intended permissions, and support the business purchasing process after launch.

### Content Staging, Merchandising, and Launch Timing <a href="#content-staging-merchandising-and-launch-timing" id="content-staging-merchandising-and-launch-timing"></a>

Adobe Commerce Content Staging can affect how teams think about launch timing. Products, categories, cart price rules, catalog price rules, CMS Pages, CMS Blocks, and widgets may be part of scheduled merchandising or content campaigns. Migration should not assume that content transfer automatically recreates campaign governance.

A source store may have scheduled promotions, seasonal landing pages, future product launches, campaign banners, or content revisions managed by apps or editorial workflows. Migration planning should classify those expectations. Some content should migrate as records. Some should be rebuilt or scheduled in Adobe Commerce. Some may need manual review because the source workflow does not have a direct target equivalent.

Launch planning should therefore distinguish:

| Content or merchandising item     | Planning treatment                                                                        |
| --------------------------------- | ----------------------------------------------------------------------------------------- |
| Ordinary CMS Pages and Blog Posts | Migrate where supported and validate content, URLs, and metadata.                         |
| Scheduled promotions              | Decide whether rules migrate, need target-side setup, or require manual campaign rebuild. |
| Seasonal landing pages            | Validate URL continuity, content blocks, media, and launch timing.                        |
| Page-builder or app-owned content | Review for supported scope, manual rebuild, or Custom Service.                            |
| Campaign governance               | Treat as target-side workflow planning, not just data transfer.                           |

Content staging adds value when the merchant can use it intentionally. It becomes a risk when teams assume that source scheduling logic has moved simply because content records exist in the target store.

### Integrations and Enterprise Ownership <a href="#integrations-and-enterprise-ownership" id="integrations-and-enterprise-ownership"></a>

Adobe Commerce projects often depend on systems outside the storefront. ERP may own product IDs, customer accounts, invoices, or inventory. PIM may own attributes and product content. CRM may own company relationships or sales assignments. Tax and shipping systems may own checkout decisions. Marketplace, analytics, loyalty, subscription, or marketing tools may own records that look like commerce data but are not native platform data.

Migration planning should identify the data owner before deciding the migration path. If the source platform only displays a value that is owned by another system, moving the display field may not preserve the business process. If a module created the data, the standard export may not include it. If a custom integration writes values into private fields, those values may need Custom Service review or separate implementation work.

The planning distinction is simple:

| Requirement                                               | Better classification                                 |
| --------------------------------------------------------- | ----------------------------------------------------- |
| Supported record requires filtering or mapping adjustment | Add-ons may help within supported behavior.           |
| Supported record requires configuration-aware treatment   | Add-ons or target-side configuration may be relevant. |
| Extension-owned or app-owned records must be preserved    | Custom Service review.                                |
| Outside-system identifiers must remain operational        | Custom Service or integration review.                 |
| Live integration must be connected after migration        | Target-side implementation, not migrated data alone.  |

Adobe Commerce gives merchants the flexibility to support complex operating models, but that flexibility only helps when data ownership and integration responsibility are explicit.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration planning should start with the enterprise operating model the target store must support. Product records, customer profiles, orders, categories, CMS Pages, Blog Posts, and URLs remain important, but they are only part of the picture. The migration plan must also account for B2B company accounts, shared catalogs, storefront scope, configurable-product relationships, attributes and attribute sets, content staging, integrations, custom modules, and validation responsibility.

A strong Adobe Commerce migration is not the broadest possible transfer. It is a controlled move into an enterprise commerce environment where migrated records, target configuration, service scope, and business validation support the same commercial model after launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**How is Adobe Commerce different from Magento Open Source for migration planning?**

Adobe Commerce shares the Magento-family foundation, but migration planning usually needs stronger attention to enterprise features such as B2B company accounts, shared catalogs, quote and purchase-order workflows, Content Staging, governance, and integrations.

**Does every Adobe Commerce migration require B2B planning?**

No. Some Adobe Commerce stores are primarily B2C or content-led. B2B planning becomes important when the source business uses company accounts, wholesale buyers, dealer pricing, sales-assisted purchasing, quote workflows, or account-specific catalog access.

**Why is storefront scope important in Adobe Commerce migration?**

Website, store, and store-view scope can affect catalog assignment, localized content, URLs, currency, configuration, and buyer context. Migrating data into the wrong scope can make the target store look complete but behave incorrectly.

**Can Add-ons handle Adobe Commerce custom data?**

Add-ons can help with supported filtering, mapping, or configuration needs. Unsupported extension data, custom fields, outside-system identifiers, bespoke transformations, and complex B2B or integration logic require Custom Service review.

**What should be validated first after an Adobe Commerce Demo Migration?**

Start with representative catalog, scope, customer, company, shared catalog, URL, and integration-sensitive examples. The goal is to prove that records support Adobe Commerce behavior, not only that record counts match.
