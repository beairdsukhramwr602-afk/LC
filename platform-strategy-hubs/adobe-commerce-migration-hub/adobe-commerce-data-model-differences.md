# Adobe Commerce Data Model Differences

Adobe Commerce migration planning is not only a transfer of products, customers, orders, categories, CMS Pages, and Blog Posts. The larger task is translating source store data into a Target Platform that can support enterprise storefront scope, B2B account relationships, governed catalog visibility, pricing rules, staged content, integrations, and operational ownership after launch.

A source record can look complete in the source store but still be incomplete for Adobe Commerce if it lacks the structure required for company purchasing, shared catalog assignment, store-view behavior, product governance, or downstream system continuity. Data model review should therefore ask how each source record is expected to behave in Adobe Commerce, not only whether the record can be migrated.

### Adobe Commerce Treats Data as Operational Structure <a href="#adobe-commerce-treats-data-as-operational-structure" id="adobe-commerce-treats-data-as-operational-structure"></a>

Many source platforms organize commerce data as relatively direct records: products, customers, orders, categories, pages, discounts, and configuration values. Adobe Commerce can use those records inside a more layered operating model.

| Source data area      | Adobe Commerce interpretation                                                                                             | Migration planning implication                                                      |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Products              | Product types, child SKUs, attributes, attribute sets, websites, categories, prices, inventory, and URL behavior          | Product data must support the intended catalog architecture, not only item display. |
| Customers             | Individual accounts, customer groups, addresses, order history, company relationships, and buying context                 | Customer data may need to preserve both identity and purchasing authority.          |
| Company accounts      | Company administrators, company users, roles, permissions, credit, quotes, purchase orders, and shared catalog assignment | B2B data may require company-level planning before migration configuration.         |
| Catalog visibility    | Product status, categories, websites, customer groups, shared catalogs, and company access                                | Buyers may see different products or prices depending on account context.           |
| Storefront scope      | Websites, stores, store views, language, currency, content, configuration, and catalog assignment                         | Multi-storefront data must be mapped to the correct scope instead of flattened.     |
| Content and campaigns | CMS Pages, CMS blocks, scheduled updates, promotion timing, and campaign dependencies                                     | Time-sensitive commercial content may require launch-aware validation.              |
| URLs                  | Product URL keys, category URL keys, CMS page paths, URL rewrites, redirects, and custom routes                           | SEO continuity depends on route interpretation, not only page existence.            |
| Inventory             | Sources, stocks, salable quantity, channel assignment, and fulfillment assumptions                                        | Stock data should match the intended Adobe Commerce fulfillment model.              |

A clean migration starts by separating simple records from records that carry business rules. Simple records can often follow standard mapping logic. Business-rule-heavy records may need Add-ons, Custom Service, or additional Target Store configuration before they behave correctly.

### Product Data Depends on Type, Relationship, and Attribute Logic <a href="#product-data-depends-on-type-relationship-and-attribute-logic" id="product-data-depends-on-type-relationship-and-attribute-logic"></a>

Adobe Commerce product migration can involve multiple product types, including simple, configurable, grouped, virtual, bundle, and downloadable products. A source product with options may need to become a configurable product connected to child simple products. A source item with kit-like behavior may need different handling if it is expected to behave like a bundle, grouped product, or custom product relationship in Adobe Commerce.

Configurable products are especially sensitive because storefront option selection depends on associated child SKUs. Size, color, material, pack quantity, or configuration options should not be treated as cosmetic fields when they control purchasable variants, inventory, images, prices, or integration identifiers.

Attributes and attribute sets create another layer of meaning. Adobe Commerce attributes can affect product display, search, layered navigation, comparison, merchandising, promotions, reports, imports, and administrative maintenance. Attribute sets group fields into product-family templates, which means a source field may need to become a structured Adobe Commerce attribute instead of a loose description value.

| Product structure       | What to review                                                                                               | Why it matters                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| Product type            | Whether source items should become simple, configurable, bundle, grouped, virtual, or downloadable products  | Product type controls how buyers select and purchase items.                         |
| Child SKU relationships | Variant SKUs, option labels, images, prices, stock, identifiers, and parent-child assignment                 | Broken relationships can make variants unavailable or operationally unusable.       |
| Attributes              | Display fields, searchable fields, filterable fields, rule inputs, integration identifiers, and admin fields | Attribute decisions affect storefront behavior and ongoing catalog governance.      |
| Attribute sets          | Product-family templates and required fields by catalog type                                                 | Poor attribute-set planning can make catalog maintenance difficult after migration. |
| Category assignment     | Navigation paths, merchandising structure, visibility, and store-scope relevance                             | Category errors can damage discovery, SEO, and buyer experience.                    |
| Related products        | Related items, upsells, cross-sells, accessories, and substitute-product relationships                       | Relationship loss can reduce conversion and operational continuity.                 |

The goal is not to preserve every source field exactly as it appeared. The goal is to land high-value catalog data in a form that supports Adobe Commerce storefront behavior and back-office workflows.

### Storefront Scope Changes Data Meaning <a href="#storefront-scope-changes-data-meaning" id="storefront-scope-changes-data-meaning"></a>

Adobe Commerce uses a hierarchy of websites, stores, and store views. That hierarchy can affect language, currency, catalog assignment, category trees, product visibility, configuration, content, pricing behavior, and customer experience.

A source platform may represent multiple brands, regions, languages, B2B portals, wholesale areas, or sales channels in ways that do not map one-to-one into Adobe Commerce. Some source distinctions may become websites. Others may become stores, store views, categories, customer groups, shared catalogs, or configuration rules.

Scope should be decided before detailed mapping. A product name may be global while descriptions vary by store view. A CMS Page may require translated versions. A category path may apply only to one website. A price may depend on customer group or shared catalog context rather than the product alone.

Scope mistakes are hard to detect through record counts. A store can have the expected number of products and pages while showing the wrong language, content, price, catalog, or URL structure in one storefront. Representative samples should include each important website, store, store view, brand, language, B2B segment, and regional context.

### Customer Data May Represent Individuals, Companies, and Purchasing Authority <a href="#customer-data-may-represent-individuals-companies-and-purchasing-authority" id="customer-data-may-represent-individuals-companies-and-purchasing-authority"></a>

In simpler migrations, customer data often means account identity, email, name, addresses, order history, and account status. Adobe Commerce can require a broader customer model, especially when B2B features are used.

A buyer may be an individual customer, a company administrator, a company user, or a contact whose purchasing authority depends on company-level rules. Company data may include legal business details, administrators, users, roles, credit, quote permissions, purchase order permissions, payment method permissions, shipping method permissions, customer group assignment, and shared catalog assignment.

| Customer layer       | What to verify                                                                           | Why it matters                                                                       |
| -------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Individual identity  | Email, name, addresses, account status, password strategy, order association             | Buyers need recognizable account continuity.                                         |
| Customer grouping    | Customer groups, tax class context, discount eligibility, storefront relevance           | Pricing, tax, and visibility may depend on group assignment.                         |
| Company relationship | Company account, administrator, users, hierarchy, and legal address                      | B2B purchasing context often exists above the individual account.                    |
| Purchasing controls  | Quotes, purchase orders, credit, payment methods, shipping methods, and role permissions | Buyers may be unable to order correctly if permissions are not preserved or rebuilt. |
| External identifiers | ERP IDs, CRM IDs, account manager references, dealer IDs, and contract references        | External systems may rely on identifiers that are not visible in storefront review.  |

A customer record can transfer correctly as an account while still failing operationally if it loses company assignment, buying role, shared catalog access, or integration identity. Those dependencies should be identified before treating customer migration as a standard account transfer.

### Shared Catalogs Turn Visibility and Pricing Into Buyer-Specific Logic <a href="#shared-catalogs-turn-visibility-and-pricing-into-buyer-specific-logic" id="shared-catalogs-turn-visibility-and-pricing-into-buyer-specific-logic"></a>

Shared catalogs can make Adobe Commerce product visibility and pricing buyer-specific. A product that exists in the Target Store may not be visible to every buyer. A price that appears correct for one customer may be incorrect for another company, customer group, or storefront scope.

Shared catalog planning should define which companies or customer groups can see which products, which prices apply, and how catalog access should differ across buyer segments. A source platform may store this logic as wholesale price lists, customer tags, account groups, dealer catalogs, contract pricing, hidden categories, custom fields, or ERP-driven rules.

Migration review should separate three questions:

1. Which products exist in Adobe Commerce?
2. Which buyers should be allowed to see those products?
3. Which price or purchasing rule should each buyer receive?

If those questions are blended, validation may only confirm that products migrated while missing the more important question of whether the correct buyers see the correct commercial offer.

### Pricing Data Can Be Public, Group-Based, Company-Based, or Rule-Driven <a href="#pricing-data-can-be-public-group-based-company-based-or-rule-driven" id="pricing-data-can-be-public-group-based-company-based-or-rule-driven"></a>

Adobe Commerce pricing can involve base prices, special prices, tier prices, customer-group pricing, shared catalog pricing, catalog price rules, cart price rules, coupon behavior, taxes, and integration-supplied pricing. Some projects only need straightforward product prices. Others require buyer-specific or time-sensitive commercial rules.

Pricing migration should identify the source of truth for each pricing layer. A public retail price may come from the source store. Contract pricing may come from an ERP. Shared catalog prices may need Target Store configuration. Promotional pricing may depend on date ranges, customer groups, or campaign logic.

Pricing review should also identify which values must be migrated, which should be recreated in Adobe Commerce, and which should remain governed by an external system after launch. Preserving incorrect historical pricing logic can be more damaging than intentionally rebuilding it in the target operating model.

### Content and Campaign Data May Have Timing Dependencies <a href="#content-and-campaign-data-may-have-timing-dependencies" id="content-and-campaign-data-may-have-timing-dependencies"></a>

Adobe Commerce content can include CMS Pages, CMS blocks, banners, landing pages, promotional content, category content, and campaign-related changes. Adobe Commerce projects may also involve Content Staging or scheduled commercial changes, depending on the implementation.

A source page is not always just a page. It may support a campaign, a seasonal offer, a localized storefront, a B2B information flow, a landing-page URL, or a merchandising schedule. Content migration should identify which pages and blocks are evergreen, which are launch-critical, which are campaign-sensitive, and which should be rebuilt instead of migrated.

Campaign timing matters because launch readiness may depend on what should be visible on the target store at launch, not merely what exists in the database. A staged promotion, scheduled category update, or time-sensitive landing page should be validated against business timing and storefront scope.

### Orders Carry Operational and Historical Context <a href="#orders-carry-operational-and-historical-context" id="orders-carry-operational-and-historical-context"></a>

Order migration in Adobe Commerce should preserve enough history for customer service, reporting reference, account review, and operational continuity. However, historical orders may not behave exactly like newly placed Adobe Commerce orders because payment captures, fulfillment events, refunds, invoices, shipments, and external integrations may have occurred in the source environment.

Order data review should identify which order details are needed for business continuity and which workflows will be active only for new orders after launch. Historical orders should be evaluated for customer account association, billing and shipping addresses, product references, totals, taxes, discounts, order statuses, and external IDs.

When B2B is involved, order context can also depend on company account, buyer identity, purchase order behavior, quote history, approval workflow, or ERP reference. Those relationships may require Custom Service or implementation-side handling if they are stored outside standard supported structures.

### Inventory Should Match the Target Fulfillment Model <a href="#inventory-should-match-the-target-fulfillment-model" id="inventory-should-match-the-target-fulfillment-model"></a>

Inventory data can look simple when the source store has one stock quantity per product. Adobe Commerce can be more complex, especially when multiple inventory sources, stocks, sales channels, reservations, pickup locations, warehouses, fulfillment integrations, or ERP-managed stock are involved.

Migration planning should distinguish between migrated stock values and the target fulfillment model. A quantity can be migrated, but that does not automatically define where stock belongs, which website can sell it, how reservations are handled, or whether an external system will overwrite values after launch.

The most important inventory question is whether the Target Store needs a simple stock baseline, a multi-source stock structure, or an integration-managed stock model. That answer affects preparation, migration configuration, validation samples, and launch timing.

### URL and SEO Data Need Route-Level Review <a href="#url-and-seo-data-need-route-level-review" id="url-and-seo-data-need-route-level-review"></a>

Adobe Commerce URL behavior can include product URL keys, category URL keys, CMS page paths, generated URL rewrites, custom rewrites, canonical behavior, redirects, and scoped URL differences. A source URL may not map cleanly to a target URL if the category structure, store scope, product visibility, or CMS page structure changes.

URL review should prioritize high-value pages rather than treating every URL equally. Priority product pages, category pages, CMS Pages, landing pages, search-visible pages, campaign URLs, and externally linked URLs should be tested before launch.

A migrated record can be present while the public route changes. That is why URL and SEO review belongs in data-model planning as well as validation. Source URL meaning should be captured before configuration decisions make later route correction harder.

### Extension and Integration Data May Sit Outside Standard Entities <a href="#extension-and-integration-data-may-sit-outside-standard-entities" id="extension-and-integration-data-may-sit-outside-standard-entities"></a>

Adobe Commerce projects often involve extensions, ERP systems, PIM systems, CRM systems, OMS tools, search services, tax services, payment services, shipping systems, marketing automation tools, and analytics platforms. Some data belongs to the commerce platform. Some belongs to connected systems. Some exists only as extension-owned or custom fields.

Standard migration coverage should not be assumed for extension-owned records, custom database tables, outside-system identifiers, custom workflows, or implementation-specific logic. Those items should be classified before migration begins.

| Data source                | Typical examples                                                                                                                | Planning response                                                        |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Standard platform entities | Products, customers, orders, categories, CMS Pages, Blog Posts where supported                                                  | Review standard mapping and validation expectations.                     |
| Add-on-sensitive data      | Filtered scopes, adjusted field mapping, configured values, selected records                                                    | Consider Add-ons when supported options match the requirement.           |
| Custom Service candidates  | Unsupported extension data, custom tables, outside-system identifiers, bespoke logic, company-specific workflows                | Scope with Next-Cart before assuming standard migration coverage.        |
| Implementation-owned setup | Theme behavior, checkout configuration, payment configuration, shipping configuration, B2B feature setup, external integrations | Prepare or rebuild in the Target Store outside the data transfer itself. |

This separation keeps migration planning realistic. Data migration can preserve records and relationships, but it does not automatically recreate every extension, business workflow, theme behavior, or integration process.

### Entity Points Measure Capacity, Not Data-Model Complexity <a href="#entity-points-measure-capacity-not-data-model-complexity" id="entity-points-measure-capacity-not-data-model-complexity"></a>

Entity Points help estimate and purchase counted data capacity for the selected migration path. They do not measure whether Adobe Commerce data is simple or complex. Two stores can have similar counted data volume but very different migration complexity if one has company accounts, shared catalogs, scoped storefronts, custom attributes, external IDs, or extension-owned workflows.

Adobe Commerce planning should therefore use Entity Points for capacity awareness while using data-model review to identify structural complexity. When the source store contains unsupported structures, custom logic, or records that need bespoke handling, the planning question is not only how many records exist. The planning question is how those records should behave in the Target Store.

### Data Model Review Should Lead to a Clear Migration Scope <a href="#data-model-review-should-lead-to-a-clear-migration-scope" id="data-model-review-should-lead-to-a-clear-migration-scope"></a>

Adobe Commerce data-model review should produce a practical scope decision before migration execution. The clearest output is a list of what will be migrated through supported structures, what requires Add-ons, what requires Custom Service, what will be configured directly in the Target Store, and what should be excluded or rebuilt.

#### Scope decisions to make before configuration <a href="#scope-decisions-to-make-before-configuration" id="scope-decisions-to-make-before-configuration"></a>

* Which product types and parent-child relationships must be preserved.
* Which attributes should become structured Adobe Commerce attributes.
* Which customer groups, companies, company users, and buyer roles must be represented.
* Which shared catalogs, price rules, or buyer-specific visibility rules are required.
* Which websites, stores, and store views must be represented.
* Which CMS Pages, Blog Posts, blocks, campaign pages, and landing pages are launch-critical.
* Which URL routes and redirects are high priority.
* Which inventory values are migrated and which are governed by external systems.
* Which custom fields, extension records, external identifiers, or integrations require Custom Service review.

A clear scope protects both migration quality and validation quality. The target result can only be validated properly when the intended Adobe Commerce behavior is defined before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce changes migration planning because records often carry operational meaning beyond their basic entity type. Products may depend on product type, attributes, and scope. Customers may depend on company relationships and purchasing authority. Catalog visibility may depend on shared catalogs. Content and pricing may depend on timing, storefront scope, and governance rules.

The strongest Adobe Commerce migration plans treat data-model review as a translation step. Source data should be evaluated according to how it must behave in the Target Store, which parts can follow supported migration paths, which parts need Add-ons, and which parts require Custom Service or implementation-side configuration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Adobe Commerce data migration the same as Magento data migration?**

No. Adobe Commerce shares important architectural roots with Magento, but Adobe Commerce projects often add enterprise B2B, shared catalog, staging, governance, and integration requirements that change migration planning and validation.

**Do company accounts migrate like normal customer records?**

Not always. Individual customer records and company account structures can have different meanings. Company administrators, company users, roles, permissions, credit, purchase orders, quotes, and shared catalog assignments may require separate planning.

**Are shared catalogs just category assignments?**

No. Shared catalogs can control product visibility and pricing for specific companies or customer groups. They should be reviewed as buyer-specific commercial logic, not only as catalog navigation.

**Do Entity Points show whether the Adobe Commerce data model is complex?**

No. Entity Points help estimate counted data capacity. They do not measure structural complexity, customization, B2B relationships, integration dependency, or validation difficulty.

**Should all extension data be migrated automatically?**

No. Extension-owned data, custom database tables, outside-system identifiers, and bespoke workflows should be reviewed before migration. Some items may require Custom Service, Target Store configuration, or implementation-side rebuilding.

**What is the most important data-model decision before Adobe Commerce migration?**

The most important decision is how source data should behave in the Target Store. Record transfer matters, but Adobe Commerce success depends on whether catalog, customer, company, pricing, content, scope, and integration relationships work as intended after migration.
