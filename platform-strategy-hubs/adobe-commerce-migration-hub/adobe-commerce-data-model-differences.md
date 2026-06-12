# Adobe Commerce Data Model Differences

Adobe Commerce migration planning must look beyond whether products, customers, orders, categories, and CMS Pages can be transferred. The deeper question is whether the source data can support the way Adobe Commerce expects commerce operations to work after migration.

That distinction matters because Adobe Commerce can combine a flexible catalog model with scoped storefronts, B2B company accounts, shared catalogs, staged campaigns, customer-group pricing, inventory sources, URL rewrite behavior, and extension-owned workflows. A source record that looks complete in another platform may still be incomplete for Adobe Commerce if it lacks the structure needed for catalog governance, buyer access, commercial visibility, or downstream integrations.

### Adobe Commerce Turns Records Into Operating Structures <a href="#adobe-commerce-turns-records-into-operating-structures" id="adobe-commerce-turns-records-into-operating-structures"></a>

Many source platforms store commerce information as relatively flat records: product, customer, order, category, page, discount, and setting. Adobe Commerce can use those records inside a more layered operating model.

| Source data area       | Adobe Commerce interpretation                                                                                                            | Migration planning implication                                                                           |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Products and variants  | Product types, child SKUs, attributes, attribute sets, pricing, websites, categories, inventory, and URL behavior                        | Product records must be translated into usable catalog architecture, not only imported as item listings. |
| Customers              | Individual accounts, customer groups, company administrators, company users, addresses, tax/discount context, and storefront scope       | Customer migration may need to preserve both identity and buying context.                                |
| B2B accounts           | Company accounts, company users, roles, credit, quotes, purchase orders, payment and shipping permissions, and shared catalog assignment | Wholesale or contract-buyer data may require company-level planning before migration.                    |
| Catalog visibility     | Categories, product assignments, shared catalogs, customer groups, and storefront scope                                                  | Product visibility may depend on buyer identity, company assignment, and target configuration.           |
| Promotions and content | Catalog price rules, cart price rules, CMS Pages, CMS blocks, scheduled updates, and campaign timing                                     | Time-sensitive commercial data may need staging-aware validation, not only record transfer.              |
| URLs                   | Product rewrites, category rewrites, CMS page rewrites, custom rewrites, and redirects                                                   | SEO continuity depends on route interpretation and rewrite planning.                                     |
| Inventory              | Sources, stocks, salable quantity, reservations, and channel assignment                                                                  | Stock migration must reflect the intended fulfillment model, not just a single quantity field.           |

A clean Adobe Commerce migration therefore starts by identifying which source records are simple data objects and which records carry operational meaning that must be reconstructed, mapped, configured, or intentionally excluded.

### Product Data Depends on Type, Relationship, and Attribute Logic <a href="#product-data-depends-on-type-relationship-and-attribute-logic" id="product-data-depends-on-type-relationship-and-attribute-logic"></a>

Adobe Commerce product migration is rarely a one-field-to-one-field exercise. A source product can become a simple product, configurable product, grouped product, virtual product, bundle product, downloadable product, or another supported commercial structure depending on what the item represents and how buyers should purchase it.

Configurable products are especially important because storefront options depend on associated simple products. A color-and-size product in a source platform may look like a single product with option values, but in Adobe Commerce those purchasable variations often need child SKUs with their own inventory, pricing, images, identifiers, and attribute values. If the source platform stores variants loosely, the migration plan must decide how variation options become Adobe Commerce product relationships.

Attributes and attribute sets add another layer. Adobe Commerce attributes can affect product pages, search, layered navigation, comparison, reports, promotions, and administrative maintenance. Attribute sets act as templates for product families. A source field called “material,” “brand,” “condition,” “wholesale flag,” or “season” may be harmless in the source platform but operationally important in Adobe Commerce if it affects filtering, merchandising, customer-group rules, external integrations, or product maintenance.

Product migration should therefore classify source product data by purpose:

| Product data type    | Meaning in Adobe Commerce                                                               | Planning question                                                                          |
| -------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Identity fields      | SKU, name, product type, URL key, status, visibility                                    | Which fields must remain stable for buyers, operations, and integrations?                  |
| Variant fields       | Configurable options, child SKU attributes, option labels, images, stock, price         | Does each buyer-selectable option need its own simple product relationship?                |
| Attribute fields     | Display, search, layered navigation, reporting, rules, integrations                     | Which attributes should become structured Adobe Commerce attributes instead of loose text? |
| Pricing fields       | Base price, special price, tier price, customer-group relevance, shared catalog pricing | Which prices are public, group-specific, company-specific, or rule-driven?                 |
| Merchandising fields | Category assignment, related products, upsells, cross-sells, visibility, featured logic | Which relationships must be recreated to preserve discovery and conversion behavior?       |

The goal is not to preserve every source field exactly as it appeared. The goal is to make sure high-value product data lands in Adobe Commerce in a form that supports the target catalog, storefront behavior, and operational workflows.

### Scope Changes the Meaning of Storefront Data <a href="#scope-changes-the-meaning-of-storefront-data" id="scope-changes-the-meaning-of-storefront-data"></a>

Adobe Commerce uses a hierarchy of websites, stores, and store views. That hierarchy affects how products, categories, content, configuration, pricing behavior, language, currency, and storefront presentation may be organized.

A source platform may have separate stores, regional storefronts, language versions, sales channels, microsites, wholesale portals, or duplicated catalogs. Adobe Commerce may represent some of those differences through websites, stores, store views, categories, customer groups, shared catalogs, configuration, or a combination of several structures.

That means scope must be decided before source data is interpreted. A product title may be global, while a description may differ by store view. A CMS Page may need a translated version. A category path may apply only to one storefront. A price may belong to a customer group or shared catalog rather than to the product itself. A configuration value may be global in the source but website-specific in Adobe Commerce.

Scope mistakes can be difficult to detect if migration validation only checks whether records exist. A store can appear complete while showing the wrong language, catalog, content, URL, pricing, or visibility in one storefront. Representative validation samples should include every important storefront scope, especially when the merchant operates across regions, brands, languages, B2B/B2C channels, or customer segments.

### Customer Data May Represent Individuals, Companies, and Buying Authority <a href="#customer-data-may-represent-individuals-companies-and-buying-authority" id="customer-data-may-represent-individuals-companies-and-buying-authority"></a>

In a simple retail migration, customer data often means account identity, email, name, addresses, order history, and subscription or marketing preferences where supported. Adobe Commerce can require a broader interpretation, especially for B2B operations.

A customer can be an individual buyer, a company administrator, a company user, a contact within a company hierarchy, or a buyer whose access depends on company-level rules. Company account data can include legal business identity, administrator details, company users, roles, credit configuration, quote permissions, purchase order permissions, payment method permissions, shipping method permissions, customer group assignment, and shared catalog assignment.

That changes the definition of a successful customer migration. A customer record may transfer correctly as an account but still fail operationally if it loses the company relationship that controls purchasing. A company may exist but buyers may not see the correct shared catalog. A buyer may retain an address but lose the approval workflow required to place orders. A customer group may move but no longer represent the same discount or tax class logic.

Customer data review should separate four layers:

| Customer layer       | What to verify                                                                            | Why it matters                                                                          |
| -------------------- | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Individual identity  | Email, name, password strategy, addresses, account status                                 | Buyers must be able to access and recognize their accounts.                             |
| Commercial grouping  | Customer groups, tax class context, discount eligibility                                  | Pricing and tax behavior can depend on group assignment.                                |
| Company relationship | Company account, administrator, company users, hierarchy, legal address                   | B2B buying authority may exist above the individual customer record.                    |
| Purchasing control   | Quotes, purchase orders, credit, payment methods, shipping methods, shared catalog access | Buyers may need permissions and company-specific rules before they can order correctly. |

When the source platform has wholesale accounts, dealer accounts, account managers, contract customers, approval workflows, purchase limits, custom buyer fields, or ERP-linked customer IDs, those relationships should be reviewed before assuming they fit a standard supported migration path.

### Shared Catalogs Turn Product Visibility Into Buyer-Specific Commerce Logic <a href="#shared-catalogs-turn-product-visibility-into-buyer-specific-commerce-logic" id="shared-catalogs-turn-product-visibility-into-buyer-specific-commerce-logic"></a>

Shared catalogs are one of the clearest Adobe Commerce data-model differences. Product visibility and price may depend on company assignment and catalog configuration, not only product status or category placement.

A source system may store wholesale pricing as customer tags, price lists, customer groups, custom fields, source extensions, ERP rules, or manually maintained spreadsheet logic. Adobe Commerce can represent company-specific catalog access and custom pricing through shared catalogs. That means migration planning must determine whether source wholesale logic should become customer groups, shared catalogs, tier pricing, advanced pricing, catalog rules, custom configuration, or a Custom Service review item.

The key planning risk is semantic mismatch. A source “dealer tier” might represent a discount percentage, a contract price list, a restricted product catalog, a tax class, a payment method rule, a sales-representative assignment, or several of these at once. Mapping that value blindly into a single Adobe Commerce field can make the account look correct while breaking what the buyer can actually see or purchase.

For shared catalog planning, merchants should identify:

| Source signal           | Possible Adobe Commerce interpretation                                                                  | Review priority |
| ----------------------- | ------------------------------------------------------------------------------------------------------- | --------------- |
| Wholesale tier          | Customer group, shared catalog assignment, pricing rule, or company classification                      | High            |
| Contract price list     | Shared catalog custom pricing, advanced pricing, external pricing integration, or Custom Service review | High            |
| Restricted product list | Shared catalog product selection, category permissions, or custom access logic                          | High            |
| Account manager field   | Company account reference, CRM integration field, or custom attribute                                   | Medium          |
| Buyer approval status   | Company status, role, purchase order workflow, or custom approval logic                                 | High            |

Shared catalog data should be validated with real companies, real buyers, representative products, and expected price/visibility outcomes. A small sample of ordinary retail customers is not sufficient for an Adobe Commerce B2B target.

### Content and Promotion Data Can Include Timing, Not Just Current State <a href="#content-and-promotion-data-can-include-timing-not-just-current-state" id="content-and-promotion-data-can-include-timing-not-just-current-state"></a>

Adobe Commerce Content Staging adds time as a migration planning dimension. Scheduled updates can apply to products, categories, catalog price rules, cart price rules, CMS Pages, and CMS blocks. For merchants using launches, seasonal campaigns, merchandising calendars, price changes, or content refreshes, the current live record may not be the only relevant state.

A source platform may have unpublished pages, scheduled promotions, future price changes, seasonal categories, campaign landing pages, hidden products, or third-party promotion rules. Adobe Commerce planning should determine whether those records are migrated, recreated, excluded, or rebuilt manually in the target Admin.

The most important distinction is between present-state data and future-state data. Migrating only visible records may be appropriate for some stores. For campaign-sensitive Adobe Commerce projects, however, future scheduled content and promotion behavior can affect launch readiness. A promotion that was scheduled in the source may need to be recreated as a rule or staged update. A CMS block that supports a campaign may need a launch-specific version. A category scheduled for a sale may need separate validation from the standard category tree.

Content and promotion review should answer three questions before migration execution:

| Question                                                                                    | Reason                                                                            |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Which records are live, inactive, archived, scheduled, or campaign-specific?                | Migration scope should match launch requirements, not just database availability. |
| Which promotion rules depend on customer groups, companies, products, categories, or dates? | Rules may need configuration or validation beyond simple data transfer.           |
| Which CMS Pages, CMS blocks, and campaign URLs are SEO- or revenue-sensitive?               | These records need stronger route, content, and timing validation.                |

If scheduled updates or campaign rules are complex, merchants should not assume they are automatically equivalent across platforms. The safer approach is to define the target behavior first, then decide whether the migration path, Add-ons, manual setup, or Custom Service review is the correct handling route.

### Inventory Data Must Match the Target Fulfillment Model <a href="#inventory-data-must-match-the-target-fulfillment-model" id="inventory-data-must-match-the-target-fulfillment-model"></a>

Adobe Commerce Inventory Management can use sources, stocks, salable quantity, and reservations. That model is different from a simple source quantity field. A source platform might have one stock number per SKU, multiple warehouse quantities, supplier stock, marketplace inventory, store pickup inventory, or ERP-controlled availability.

A single source quantity can be acceptable for a simple target inventory model. It is not enough when Adobe Commerce needs to represent multiple warehouses, regional fulfillment, channel-specific availability, safety stock, backorder expectations, or external inventory ownership. In those cases, source inventory should be evaluated against the intended target fulfillment model before migration assumptions are accepted.

Inventory migration planning should distinguish:

| Inventory concern              | Why it affects Adobe Commerce migration                                                   |
| ------------------------------ | ----------------------------------------------------------------------------------------- |
| Source quantity                | Basic stock transfer may be sufficient only for simple operations.                        |
| Source location                | Multi-source fulfillment may require source and stock planning.                           |
| Channel availability           | Different websites or sales channels may need different salable inventory assumptions.    |
| External inventory system      | ERP, warehouse, marketplace, or supplier-controlled stock may need identifier continuity. |
| Reservations and live ordering | Migration timing should avoid inventory confusion during active sales periods.            |

The target store should be validated with products that represent common and edge-case inventory behavior, including configurable child SKUs, out-of-stock items, backorder-sensitive products, and items tied to warehouse or external-system logic.

### URLs and Identifiers Carry Operational Continuity <a href="#urls-and-identifiers-carry-operational-continuity" id="urls-and-identifiers-carry-operational-continuity"></a>

Adobe Commerce URL rewrites can support product, category, CMS page, and custom routes. In migration planning, URLs are not just display fields. They preserve buyer access, search-engine continuity, campaign links, analytics history, marketplace references, email links, and integration assumptions.

Source platforms may use different URL structures, category paths, product handles, slugs, IDs, redirect rules, or canonical URL behavior. Adobe Commerce may require URL keys, rewrites, redirects, and route decisions that preserve high-value paths while fitting the target architecture.

External identifiers matter in the same way. ERP IDs, PIM IDs, CRM IDs, marketplace IDs, tax-system IDs, fulfillment IDs, and legacy order references may not be visible to customers, but they can be essential to operations. A migration that preserves storefront data while losing hidden identifiers can still disrupt fulfillment, reporting, customer service, accounting, or integration reconciliation.

Route and identifier planning should prioritize:

* high-value product and category URLs;
* CMS Pages and campaign landing pages;
* old-to-new redirect expectations;
* canonical URL assumptions;
* SKU and order-reference continuity;
* customer and company external IDs;
* product, inventory, and account identifiers used by integrations.

Unsupported source identifiers, extension-owned records, or integration-specific fields should be reviewed early. Depending on scope, these may require Advanced Data Mapping, Advanced Data Configure, other Add-ons, accepted exclusions, or Custom Service review.

### How to Decide What Requires Standard Mapping, Add-ons, or Custom Service Review <a href="#how-to-decide-what-requires-standard-mapping-add-ons-or-custom-service-review" id="how-to-decide-what-requires-standard-mapping-add-ons-or-custom-service-review"></a>

Not every Adobe Commerce data-model difference requires Custom Service. Some differences are normal target-platform interpretation work. Others require optional Add-ons. The highest-risk cases are source-specific behaviors that do not have a clean equivalent in the supported migration path.

| Data-model situation                                                                                                                               | Likely handling direction                                                                                 |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Standard products, customers, orders, categories, and CMS Pages with clean field structure                                                         | Standard Service may be sufficient if the supported migration path covers the required entities.          |
| Attributes, groups, filters, or field-level transformations need additional handling within supported scope                                        | Add-ons such as Advanced Data Mapping, Advanced Data Configure, or Data Filter Add-on may be appropriate. |
| Source data includes company-specific pricing, unsupported B2B relationships, extension-owned records, outside-system identifiers, or custom logic | Custom Service review may be needed before the service license is finalized.                              |
| Merchant wants execution support, planning review, or coordinated handling but the data model is still within supported scope                      | Managed Service may be the better operating choice.                                                       |
| Source platform is unsupported, heavily customized, or behaves as a Custom Platform                                                                | Custom Service review should clarify feasibility, scope, responsibility, and exclusions.                  |

The practical standard is simple: if the source value has commercial, operational, or integration meaning that Adobe Commerce must preserve, it should be identified before the main migration run, represented in Demo Migration samples where possible, and assigned to a clear handling route.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce data migration is not only a transfer of records. It is a translation of source commerce meaning into an enterprise target model that can include scoped storefronts, structured catalogs, company accounts, shared catalogs, staged campaigns, inventory sources, URL rewrites, and external-system dependencies.

The strongest migration plans identify where source data is descriptive, where it is behavioral, and where it is tied to pricing, access, fulfillment, compliance, reporting, or integrations. That separation prevents Adobe Commerce from becoming a technically complete target store that fails to support the merchant’s actual operating model.

Before confirming the migration path, prepare representative source examples for products, attributes, companies, customer groups, shared catalogs, scheduled content, inventory, URLs, and integration identifiers. Use those examples during Demo Migration review to decide what fits the supported migration path, what should be handled through Add-ons, and what needs Custom Service review.

### FAQs <a href="#faqs" id="faqs"></a>

**Why does Adobe Commerce data migration require more planning than simpler target platforms?**

Adobe Commerce can attach operational meaning to records through scope, product types, attributes, company accounts, shared catalogs, customer groups, staged content, inventory sources, URL rewrites, and integrations. A record may transfer successfully while still failing to support the intended business behavior.

**Are Adobe Commerce shared catalogs just another product category structure?**

No. Shared catalogs can control product visibility and pricing for assigned companies. They should be planned as buyer-specific commercial logic, not as ordinary category migration.

**Should every source customer become a company account in Adobe Commerce?**

No. Individual retail buyers, company administrators, company users, and wholesale accounts should be separated during planning. Company accounts are appropriate when the target store needs B2B purchasing structure, buyer roles, company-level settings, or shared catalog assignment.

**Can source attributes be migrated as plain text fields?**

Some can, but high-value attributes should be reviewed for target use. Attributes that affect search, layered navigation, product pages, promotions, reporting, integrations, or product maintenance should be structured carefully in Adobe Commerce.

**When should data-model differences be raised for Custom Service review?**

Custom Service review is appropriate when required behavior depends on unsupported source data, extension-owned records, outside-system identifiers, company-specific pricing logic, custom B2B relationships, or other bespoke logic that cannot be safely handled as normal field mapping.
