# BigCommerce Platform Overview

BigCommerce is a hosted commerce platform for merchants that want managed platform operations while still needing structured catalog, pricing, storefront, and integration planning. As a Target Platform, it is usually selected for a balance of SaaS governance, API-accessible commerce data, and stronger product and storefront structure than very lightweight hosted systems.

A BigCommerce migration should not be assessed by record counts alone. Product options, variants, modifiers, category trees, customer groups, price lists, channels, redirects, custom fields, metafields, apps, and external-system identifiers can all affect how source data should be interpreted before it becomes useful in the Target Platform.

### Where BigCommerce Fits in Platform Migration Planning <a href="#where-bigcommerce-fits-in-platform-migration-planning" id="where-bigcommerce-fits-in-platform-migration-planning"></a>

BigCommerce is often considered when a business wants to reduce infrastructure ownership without flattening commerce complexity. It can support merchants that need hosted operations, governed catalog management, structured product choices, customer segmentation, price-list planning, API-based integrations, and storefront or channel expansion.

This creates a different migration profile from both simpler SaaS platforms and open-source systems. BigCommerce removes many hosting and maintenance concerns, but it still requires careful interpretation of how the store sells. The most important planning question is not whether products, customers, orders, categories, CMS Pages, Blog Posts, and related records can be moved. The more important question is whether their commercial meaning will still work after landing in BigCommerce.

| BigCommerce planning area        | Why it matters during migration                                                                                |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Product choices                  | Source options may need to become variants, modifiers, custom fields, or custom logic.                         |
| Category and discovery structure | Category trees, assignments, navigation, and SEO-sensitive paths affect how shoppers find products.            |
| Pricing and customer context     | Customer groups, price lists, negotiated pricing, and B2B-like expectations require commercial interpretation. |
| Storefront and channel planning  | Channel assignment and Multi-Storefront assumptions affect what appears in each customer-facing context.       |
| Redirect and content continuity  | Redirects, pages, Blog Posts, and high-value URLs need customer-journey and search-intent planning.            |
| Custom data and integrations     | Metafields, custom fields, apps, and external IDs may carry operational meaning outside ordinary records.      |

### BigCommerce as a Hosted but Structured Target Platform <a href="#bigcommerce-as-a-hosted-but-structured-target-platform" id="bigcommerce-as-a-hosted-but-structured-target-platform"></a>

BigCommerce should be understood as hosted commerce with meaningful data-structure decisions. It is not only a simpler destination for merchants leaving self-hosted platforms, and it is not only an alternative to other SaaS systems. Its migration value depends on how well the business can define the product, pricing, storefront, and integration behavior that should survive the move.

For merchants coming from highly customized systems, BigCommerce can reduce operational burden, but custom logic does not automatically become native BigCommerce behavior. For merchants coming from lighter hosted platforms, BigCommerce may provide more structure, but only if the migration plan uses that structure intentionally.

The strongest BigCommerce migrations usually begin with a clear distinction between records and behavior. Records describe what exists. Behavior explains how the store sells, prices, filters, displays, redirects, segments, and integrates those records.

### Product Choice and Catalog Meaning <a href="#product-choice-and-catalog-meaning" id="product-choice-and-catalog-meaning"></a>

BigCommerce catalog planning requires careful separation between products, variants, variant options, modifiers, custom fields, and metafields. These structures can appear similar from a source-store perspective, but they do not always preserve the same buying behavior.

A source platform may use options for size and color, personalization text, add-on services, bundled selections, warranty choices, engraving details, file uploads, or configuration rules. Some of those choices may belong as sellable variations. Others may be better treated as modifier-style purchase choices, custom fields, or Custom Service logic when the source behavior is not representable through standard migration handling.

This is why product-choice classification is one of the earliest BigCommerce planning tasks. A migration that moves product names, SKUs, prices, descriptions, and images can still fail if the option logic does not match how customers actually buy.

### Categories, Storefront Discovery, and SEO Continuity <a href="#categories-storefront-discovery-and-seo-continuity" id="categories-storefront-discovery-and-seo-continuity"></a>

Categories in BigCommerce should be planned as discovery and storefront-structure assets, not only as folders. They influence navigation, merchandising, shopper flow, and often SEO continuity.

Source stores may contain category trees that reflect merchandising strategy, legacy platform constraints, outdated internal naming, search-oriented landing pages, or campaign structures. During migration, the business should decide which categories should be preserved, which should be simplified, and which need redirect support because they carry search traffic or external links.

For larger stores, category assignment can also interact with storefront or channel expectations. A product might belong to multiple discovery paths, appear differently across storefront contexts, or need a cleaner category tree before launch.

### Pricing, Customer Groups, and Price Lists <a href="#pricing-customer-groups-and-price-lists" id="pricing-customer-groups-and-price-lists"></a>

BigCommerce migration planning should treat pricing as commercial logic, not just product data. Standard price, sale price, bulk pricing, customer groups, price lists, negotiated pricing, and app-controlled pricing may all create different obligations during migration.

Customer groups and price lists are especially important when the source store has wholesale, B2B-like, distributor, regional, loyalty, or negotiated pricing behavior. The migration plan should identify which prices are public, which are segmented, which depend on customer membership, and which are managed by an external system.

If pricing context is unclear, BigCommerce may appear correct in the catalog while still producing the wrong buying outcome for important customers.

### Channels, Multi-Storefront, and Storefront Governance <a href="#channels-multi-storefront-and-storefront-governance" id="channels-multi-storefront-and-storefront-governance"></a>

BigCommerce can support storefront and channel planning beyond a single simple storefront. This can be valuable for merchants that operate multiple brands, regions, customer segments, languages, or selling contexts.

That flexibility introduces governance decisions. The business should define which products, categories, prices, content, URLs, customer experiences, and integrations are shared and which are storefront-specific. Without those decisions, migration can create duplicate or inconsistent storefront behavior that becomes difficult to manage after launch.

Multi-Storefront planning should not be treated as a cosmetic expansion feature. It affects how data is assigned, reviewed, and validated.

### Custom Fields, Metafields, Apps, and External Systems <a href="#custom-fields-metafields-apps-and-external-systems" id="custom-fields-metafields-apps-and-external-systems"></a>

BigCommerce exposes several ways to preserve additional commerce context, including custom fields, metafields, API-accessible catalog data, apps, and integrations. These capabilities can improve migration flexibility, but they also require discipline.

A source store may contain important business meaning in plugin fields, app data, extension tables, theme logic, ERP identifiers, CRM records, review platforms, subscription systems, fulfillment rules, tax tools, personalization engines, or merchandising integrations. Some of that information can be mapped into supported structures. Some may require Add-ons for mapping, filtering, or data configuration. Some may require Custom Service when the data or behavior sits outside standard supported handling.

A strong BigCommerce migration separates visible storefront data from operational data before choosing the migration scope.

### BigCommerce Migration Context <a href="#bigcommerce-migration-context" id="bigcommerce-migration-context"></a>

BigCommerce is best understood as a hosted commerce platform with structured catalog, pricing, storefront, and integration behavior. It can reduce infrastructure responsibility compared with self-hosted systems, but it still requires careful decisions about how product choices, customer segmentation, storefront scope, redirects, and custom data should be represented after migration.

That distinction matters because a BigCommerce migration can look simple at record level while still carrying meaningful business interpretation. Product modifiers, custom fields, category trees, channel assignments, customer groups, and price lists should be reviewed as operating structures, not as decorative fields. Stores moving from highly customized systems should also separate what can be represented through standard BigCommerce behavior from what needs Add-ons or Custom Service.

The correct BigCommerce framing is hosted commerce with structured product, pricing, storefront, redirect, custom-data, and integration implications.

### Early Planning Signals for BigCommerce Migration <a href="#early-planning-signals-for-bigcommerce-migration" id="early-planning-signals-for-bigcommerce-migration"></a>

A merchant considering BigCommerce should review several signals before confirming migration scope.

| Signal                        | What to confirm before migration                                                                    |
| ----------------------------- | --------------------------------------------------------------------------------------------------- |
| Option-heavy catalog          | Which source choices become variants, modifiers, fields, or custom logic.                           |
| Segmented pricing             | Whether customer groups, price lists, promotions, or external pricing rules must be preserved.      |
| Multi-storefront intent       | Which products, categories, prices, URLs, and content differ by storefront or channel.              |
| SEO-sensitive structure       | Which category, product, brand, content, and campaign URLs require redirect planning.               |
| App or integration dependency | Which behaviors come from external systems rather than standard store records.                      |
| Custom identifiers            | Whether external IDs must remain available for ERP, CRM, analytics, fulfillment, or reconciliation. |

These signals help determine whether Standard Service is enough or whether Managed Service, Add-ons, or Custom Service should be considered after reviewing Demo Migration evidence.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce can be a strong Target Platform for merchants that want hosted commerce governance without losing important product, category, pricing, storefront, redirect, and integration structure. Its migration value is strongest when the business understands how the source store sells, not only which records need to move.

A successful BigCommerce migration should preserve commercial meaning across product choices, category discovery, customer segmentation, pricing logic, storefront assignment, URLs, custom data, apps, and external systems. When these areas are reviewed early, the Target Platform is more likely to support the business model rather than simply contain imported records.

Run a Demo Migration with representative products, option-heavy items, customer groups, price-list scenarios, category structures, storefront/channel examples, high-value URLs, and custom-data dependencies. If the result shows uncertainty around mapping, filtering, configuration, validation, or unsupported behavior, review whether Managed Service, Add-ons, or Custom Service should be included in the migration path.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is BigCommerce only suitable for simple hosted-store migrations?**

No. BigCommerce is hosted, but its migration planning can be structurally demanding when the source store has complex product choices, customer groups, price lists, storefront/channel needs, redirects, custom fields, metafields, apps, or external integrations.

**Why do product options matter so much in a BigCommerce migration?**

Source product options may represent different types of behavior. Some are true sellable variations, while others are modifier-style choices, personalization fields, add-ons, configuration rules, or custom logic. Each type needs a suitable BigCommerce representation.

**Does BigCommerce Multi-Storefront change migration planning?**

Yes. Multi-Storefront or channel planning can affect product assignment, category structure, pricing context, content, URLs, customer experience, and validation responsibility. It should be planned before migration rather than treated as a post-launch detail.

**When should Custom Service be considered for BigCommerce?**

Custom Service should be considered when the source store depends on Custom Platform data, unsupported app or extension data, custom fields, outside-system identifiers, platform limitations, custom migration logic adjustment, or bespoke transformation beyond standard supported behavior and selected Add-ons.
