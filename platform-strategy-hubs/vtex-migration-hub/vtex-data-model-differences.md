# VTEX Data Model Differences

VTEX data-model planning should start with a translation question: which source records will become usable VTEX commerce structures, and which records represent behavior that belongs to configuration, integration, implementation, or Custom Service scope? VTEX is a modular commerce environment, so data meaning is distributed across catalog, SKUs, specifications, pricing, promotions, checkout, orders, logistics, sellers, marketplace context, Master Data, search, storefront implementation, and external systems.

That makes VTEX different from platforms where product, customer, order, page, and URL data can be reviewed mostly as isolated records. A source product option may become a SKU, a specification, a storefront selection, a custom field, or a rebuild requirement. A source customer field may be ordinary profile context, Master Data, B2B-related information, CRM-owned identity, or integration metadata. A source order may preserve support value, but it does not automatically configure VTEX checkout, payment, fulfillment, marketplace, or logistics behavior.

The strongest VTEX migration scope is not the largest transfer. It is the scope that preserves useful data meaning while separating migrated records from VTEX setup, front-end implementation, integration ownership, Add-ons, and Custom Service requirements.

### VTEX Data Meaning Is Distributed Across Commerce Services <a href="#vtex-data-meaning-is-distributed-across-commerce-services" id="vtex-data-meaning-is-distributed-across-commerce-services"></a>

VTEX data should be interpreted through the service that will use it after launch. Catalog data may affect product display, search, pricing, promotions, SKU availability, logistics, and marketplace behavior. Order history may matter for service and reporting, but live order processing depends on checkout, payment, fulfillment, logistics, and operational configuration. Customer data may appear simple at first, while Master Data, segmentation, B2B context, CRM identifiers, or custom forms create separate decisions.

This distributed model changes migration review. A field that looked like an ordinary product attribute in the source store may be a specification in VTEX. A source variant may need SKU-level structure. A channel price may belong to pricing rules or price tables rather than the product record itself. A marketplace seller reference may not be ordinary catalog data. A content page may need storefront implementation or redirect planning rather than direct one-to-one migration.

| Source record or behavior        | VTEX interpretation question                                                                  | Migration implication                                                          |
| -------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Product option or variant        | Does it define a sellable SKU, a product specification, or storefront choice behavior?        | SKU and specification planning should happen before product scope is accepted. |
| Attribute or custom field        | Is it used for filtering, product detail, operations, integration, or customer workflow?      | Mapping depends on business use, not only field name similarity.               |
| Channel price or promotion       | Is it a base price, price table, sales-channel condition, coupon, or active promotion rule?   | Commercial behavior should be separated from historical price data.            |
| Customer extra field             | Is it profile data, Master Data, B2B context, CRM metadata, or integration-owned information? | Some values may need Add-ons, Custom Service, or external-system handling.     |
| Order status or fulfillment note | Is it historical support context or live OMS/logistics behavior?                              | Order migration should not be treated as target workflow configuration.        |

VTEX therefore requires meaning-first mapping. The migration plan should identify what each data area needs to do after launch before deciding whether a field should migrate, be configured, be rebuilt, be integrated, or be excluded.

### Catalog Translation Starts With Products, SKUs, Categories, Brands, and Specifications <a href="#catalog-translation-starts-with-products-skus-categories-brands-and-specifications" id="catalog-translation-starts-with-products-skus-categories-brands-and-specifications"></a>

The core VTEX catalog distinction is that products and SKUs are not the same planning object. A product represents the commercial item family, while SKUs represent sellable units or versions that can affect price, inventory, logistics, storefront choice, and purchasing behavior. Categories, brands, and specifications then help organize, describe, search, filter, and present those products.

Source platforms often use different structures. A Shopify variant, Magento configurable product, WooCommerce variable product, BigCommerce option, custom source table, or marketplace listing may not convert cleanly into VTEX without interpretation. The migration decision should ask whether the source choice controls purchasability, stock, price, fulfillment, display, or only descriptive information.

| Source pattern                                                              | VTEX data decision                                                               | Risk if misread                                                          |
| --------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Size, color, capacity, unit, package, or model choice                       | Usually review as SKU-defining information when it changes the sellable unit.    | Products may display but not offer the right purchasable choices.        |
| Material, compatibility, technical detail, care instruction, or measurement | Often review as product or SKU specification depending on use.                   | Filters, comparison, search, or product detail pages may lose structure. |
| Brand or manufacturer value                                                 | Review as VTEX brand data where it supports catalog management or discovery.     | Brand search, filtering, or merchandising may become inconsistent.       |
| Category path or collection                                                 | Review category organization separately from storefront navigation and SEO path. | Catalog grouping may migrate while customer discovery remains weak.      |
| Source tags, metafields, or app attributes                                  | Classify by business use before mapping.                                         | Noise may enter the catalog or important operational data may disappear. |

A VTEX catalog migration should be accepted only when representative products show usable product-to-SKU relationships, meaningful specifications, correct brand and category context, and clear handling for fields that do not belong in standard catalog records.

### Specifications Should Preserve Purpose, Not Just Values <a href="#specifications-should-preserve-purpose-not-just-values" id="specifications-should-preserve-purpose-not-just-values"></a>

Specifications are one of the easiest areas to mishandle in VTEX because source attributes often mix several purposes. Some values define SKU selection. Some describe the product. Some power filters. Some support compliance or operations. Some exist only because the source platform or app required them. Migrating all values mechanically can create clutter; dropping them can break discovery, merchandising, or integrations.

The right question is not “Can this field migrate?” The right question is “What should this value do in VTEX?” A source attribute used for storefront filtering should not be buried in a description. A value required by an external system may need preservation even if it should not appear to shoppers. A legacy field that no longer supports the business may be excluded rather than carried forward.

Useful specification review should classify values into four groups:

| Specification purpose                | Examples                                                             | Handling direction                                                               |
| ------------------------------------ | -------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Sellable choice                      | Size, voltage, pack count, color when it changes SKU selection.      | Review as SKU-related structure or SKU specification.                            |
| Product detail                       | Material, dimensions, compatibility, ingredients, technical notes.   | Preserve where it improves product pages, comparison, or search.                 |
| Discovery and filtering              | Category-specific values shoppers use to narrow results.             | Normalize carefully to avoid duplicate or noisy filters.                         |
| Operational or integration reference | ERP IDs, supplier codes, compliance flags, internal classifications. | Consider Add-ons, Custom Service, or external-system ownership depending on use. |

This purpose-based review protects the catalog from two opposite errors: losing structured values that matter and migrating old source-platform residue that makes VTEX harder to manage.

### Pricing, Promotions, Trade Policies, and Sales Channels Are Not Simple Product Fields <a href="#pricing-promotions-trade-policies-and-sales-channels-are-not-simple-product-fields" id="pricing-promotions-trade-policies-and-sales-channels-are-not-simple-product-fields"></a>

VTEX commercial data can involve base prices, price tables, sales-channel behavior, promotions, coupons, and contextual pricing rules. A source platform may store price data directly on products, inside customer-group rules, in scripts, in apps, in ERP records, in marketplace feeds, or in regional storefront settings. Those values should not be assumed to have one VTEX destination.

For migration planning, price data should be separated into historical, active, contextual, and external-system-owned values. Historical prices may help preserve order readability. Active prices may need to support launch. Channel-specific or customer-specific prices may require setup, mapping, or integration. Promotions and coupons may be records, rules, or business logic rather than simple data rows.

| Commercial data type                | VTEX planning question                                                                                     |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Base SKU price                      | Should this be the launch price, a historical reference, or an initial value controlled by another system? |
| Price table or customer-group price | Which segment, channel, or business context should the value serve?                                        |
| Promotion or coupon                 | Is the goal to preserve an active rule, historical order context, or only a record reference?              |
| Marketplace or seller price         | Who owns the price after launch, and does seller context affect availability?                              |
| External pricing identifier         | Is it needed for ERP, middleware, marketplace, reporting, or customer-service continuity?                  |

This distinction is especially important for merchants moving from Adobe Commerce, Magento Open Source, Shopify Plus, or custom platforms where pricing may be distributed across customer groups, catalogs, apps, scripts, price lists, or external systems. VTEX can support sophisticated commercial operations, but migration scope should not promise that every old pricing behavior becomes launch-ready by transferring product fields.

### Customer, B2B, and Master Data Planning Requires Identity Discipline <a href="#customer-b2b-and-master-data-planning-requires-identity-discipline" id="customer-b2b-and-master-data-planning-requires-identity-discipline"></a>

Customer migration into VTEX should be planned around buyer identity, account context, and business use. Basic profile data may include names, emails, phones, addresses, and order associations. More complex source environments may include B2B permissions, company records, account hierarchies, tax identifiers, customer groups, loyalty data, CRM references, form submissions, custom fields, or segmentation attributes.

Master Data introduces an additional planning layer because custom records may support workflows that are not ordinary customer profiles. A source custom field could be a harmless note, a required business identifier, a B2B approval value, a CRM synchronization key, or a form-driven customer-service record. The correct handling depends on whether the value must be visible, searchable, editable, synchronized, reported, or used by another workflow.

| Customer-related source data   | VTEX meaning to confirm                                                                        |
| ------------------------------ | ---------------------------------------------------------------------------------------------- |
| Standard customer profile      | Whether supported fields preserve enough buyer lookup and order context.                       |
| Company or B2B account context | Whether it is launch-critical, externally managed, or part of VTEX-side setup.                 |
| Custom profile field           | Whether it belongs in migrated profile data, Master Data, Custom Service, or external systems. |
| Loyalty or CRM identifier      | Whether downstream systems need the same identifier after launch.                              |
| Form or workflow record        | Whether the record should migrate, be rebuilt, remain external, or be excluded.                |

Identity discipline prevents a common VTEX mistake: treating every customer-related value as a profile field. The merchant should define what staff, customers, integrations, and reporting processes need from customer data after launch before accepting the migration scope.

### Orders, Checkout, Payments, OMS, and Logistics Have Separate Meanings <a href="#orders-checkout-payments-oms-and-logistics-have-separate-meanings" id="orders-checkout-payments-oms-and-logistics-have-separate-meanings"></a>

Historical orders can be migrated for support, reporting context, and customer history, but they should not be confused with live VTEX checkout, payment, OMS, fulfillment, or logistics setup. A source order may include line items, taxes, discounts, payment references, fulfillment status, invoices, shipping methods, marketplace seller information, delivery dates, cancellation reasons, refunds, custom fields, and external IDs. Each value should be reviewed for historical readability and business continuity.

Live operational behavior is different. Checkout behavior, payment provider configuration, fraud tools, carrier setup, warehouse logic, pickup points, shipping rates, SLA expectations, and order orchestration require VTEX configuration and validation. Migrating order history does not make those workflows ready.

| Order-related area         | Historical migration role                                         | Target-side setup role                                                                      |
| -------------------------- | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Order line items           | Preserve what the customer purchased and at what price.           | Confirm future SKU, catalog, and checkout behavior separately.                              |
| Payment references         | Help staff interpret past transactions.                           | Configure and test live providers, payment methods, and settlement behavior separately.     |
| Fulfillment status         | Preserve service context where supported.                         | Configure logistics, carriers, warehouses, pickup points, and fulfillment rules separately. |
| Seller or marketplace data | Preserve context when needed for support or reporting.            | Define seller, marketplace, offer, and order routing behavior separately.                   |
| External order IDs         | Preserve reconciliation or integration references where required. | Confirm external systems can continue matching records after launch.                        |

Order migration should be accepted when representative historical orders remain understandable. It should not be used as evidence that VTEX operations are configured for new transactions.

### Marketplace and Seller Data Need Ownership Decisions <a href="#marketplace-and-seller-data-need-ownership-decisions" id="marketplace-and-seller-data-need-ownership-decisions"></a>

VTEX marketplace planning requires careful ownership decisions. A merchant may operate as a seller, marketplace, or hybrid environment. Source data may contain seller IDs, vendor records, offer data, marketplace commissions, external marketplace references, channel-specific prices, inventory ownership, fulfillment ownership, or split order behavior. These values should not be flattened into ordinary product or order records without review.

The key question is whether marketplace information should exist as migrated history, active VTEX setup, integration-owned data, or excluded context. A seller reference in historical orders may be useful for support. Active seller onboarding, offer synchronization, commission logic, fulfillment ownership, and seller performance workflows may belong to VTEX configuration or connected systems rather than standard migration.

Marketplace data should be classified by purpose:

| Marketplace purpose                          | Likely planning direction                                                           |
| -------------------------------------------- | ----------------------------------------------------------------------------------- |
| Historical seller context on orders          | Preserve where supported if it supports service or reporting.                       |
| Active seller catalog and offers             | Review setup, integration, or Custom Service needs.                                 |
| Seller-specific price, stock, or fulfillment | Define ownership before migration approval.                                         |
| Marketplace commissions or governance rules  | Treat as business logic requiring setup, integration, or custom evaluation.         |
| External marketplace identifiers             | Preserve only when needed for reconciliation, reporting, or integration continuity. |

This ownership review is especially important when migrating from marketplace-oriented platforms, multi-vendor systems, ERP-connected catalogs, or heavily integrated source environments.

### Storefront, CMS Pages, Blog Posts, Search, and URLs Should Be Separated From Core Data Transfer <a href="#storefront-cms-pages-blog-posts-search-and-urls-should-be-separated-from-core-data-transfer" id="storefront-cms-pages-blog-posts-search-and-urls-should-be-separated-from-core-data-transfer"></a>

VTEX storefront implementation may involve headless front ends, CMS components, search behavior, merchandising, redirects, and SEO continuity. A product can migrate into VTEX while the storefront experience remains incomplete. A CMS Page may carry content value but not have a direct one-to-one relationship with the target storefront implementation. Blog Posts may matter for organic traffic, but their handling depends on scope and platform setup.

For data-model planning, content and URL records should be evaluated by business role rather than record type alone. A source category URL may be a catalog path, a search landing page, a merchandising page, or an SEO asset. A content page may be a policy page, buying guide, campaign landing page, or custom layout. A search rule may be platform-native, app-owned, or implementation-specific.

| Source asset                | VTEX planning question                                                                        |
| --------------------------- | --------------------------------------------------------------------------------------------- |
| Product URL                 | Should it redirect, remain equivalent, or be rebuilt through storefront routing?              |
| Category or collection page | Is it catalog organization, navigation, search experience, SEO content, or merchandising?     |
| CMS Page                    | Should it migrate as content, be recreated in the storefront, redirected, or retired?         |
| Blog Post                   | Is it within migration scope, SEO scope, content strategy, or a separate CMS decision?        |
| Search/filter logic         | Is it driven by specifications, search configuration, app behavior, or custom implementation? |

This separation prevents a common launch issue: approving product migration while customer-facing discovery, content, and URL behavior remain unresolved.

### External Systems and Custom Data Decide the Real Migration Boundary <a href="#external-systems-and-custom-data-decide-the-real-migration-boundary" id="external-systems-and-custom-data-decide-the-real-migration-boundary"></a>

VTEX migrations often involve ERP, CRM, PIM, OMS, WMS, marketplace middleware, payment providers, loyalty systems, tax systems, analytics, customer-service tools, and custom storefront applications. These systems may own product identifiers, prices, inventory, customer attributes, order references, seller data, fulfillment information, or custom records.

Migration scope should identify system ownership before data is moved. If the source export contains a value that will be overwritten by an ERP after launch, the merchant should decide whether that value matters for migration. If an external ID must continue linking orders, customers, or products across systems, preserving it may be critical. If a custom record supports a workflow that VTEX does not natively represent as standard commerce data, Custom Service may be needed.

| External or custom data type | Scope decision                                                               |
| ---------------------------- | ---------------------------------------------------------------------------- |
| ERP product or order ID      | Preserve if required for reconciliation or synchronization.                  |
| PIM attribute set            | Map only the values needed for VTEX catalog, specifications, or search.      |
| CRM customer identifier      | Preserve if customer-service or marketing workflows depend on it.            |
| WMS or fulfillment reference | Decide whether it belongs to history, integration setup, or custom handling. |
| App or middleware data       | Review supported migration behavior before assuming it can transfer.         |

Add-ons may help when the requirement involves supported filtering, mapping, or configuration. Custom Service should be considered when the requirement involves unsupported data, custom records, bespoke transformation, Custom Platform handling, or custom migration logic adjustment beyond supported behavior.

### Data Scope Should Be Accepted Through Usable VTEX Outcomes <a href="#data-scope-should-be-accepted-through-usable-vtex-outcomes" id="data-scope-should-be-accepted-through-usable-vtex-outcomes"></a>

A VTEX data model review should end with usable outcomes, not only entity totals. Products should become meaningful catalog and SKU structures. Specifications should support the intended use. Customer data should preserve useful identity context. Orders should remain readable. Marketplace and seller information should have a defined owner. Content and URLs should support launch continuity where included. Custom and integration data should be mapped, scoped, excluded, or escalated intentionally.

Entity Points can help plan selected Product, Customer, Order, and Blog Posts volume where relevant, but they do not prove data-model fit. A small VTEX migration can still require Custom Service if it depends on Master Data, seller logic, complex pricing, external identifiers, or headless storefront records. A larger migration can remain manageable if the records are supported, well structured, and validated through representative samples.

The right VTEX data scope should make the future target operation clearer. It should not carry every source field forward merely because the field exists.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX data model differences matter because migrated records enter a modular commerce environment rather than a flat storefront database. Products, SKUs, specifications, prices, promotions, customers, orders, logistics, marketplace context, Master Data, storefront content, URLs, and external-system references should be interpreted by how they will function in VTEX after launch.

A strong VTEX migration plan separates supported migrated records from target-side setup, implementation work, Add-ons, Custom Service needs, and external-system ownership. That separation helps the merchant preserve meaningful business data without promising that every source behavior will automatically become a configured VTEX operation.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are SKUs so important in VTEX migration?**

SKUs often control sellable versions, price, inventory, availability, logistics, and storefront choices. If source product options are not translated into usable VTEX SKU and specification structures, products may migrate but still fail commercial or operational expectations.

**Do all source attributes become VTEX specifications?**

No. Source attributes should be reviewed by purpose. Some belong as specifications, some define SKUs, some belong to content or integrations, and some should be excluded because they no longer support the target operation.

**Can source promotions and price rules migrate as product fields?**

Usually not. Promotions, coupons, price tables, sales-channel conditions, and external pricing logic should be reviewed separately from base product prices. Some values may be migrated as references, while active commercial behavior may require VTEX setup or integration work.

**Are historical orders the same as VTEX OMS setup?**

No. Historical orders preserve past purchase context where supported. Live order processing, checkout behavior, payment providers, fulfillment rules, logistics, and OMS workflows require separate VTEX setup and validation.

**When does VTEX data require Custom Service?**

Custom Service should be considered when the migration involves unsupported records, Master Data structures, custom fields, external-system identifiers, marketplace logic, bespoke transformation, Custom Platform handling, or custom migration logic adjustment beyond supported behavior.
