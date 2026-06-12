# Adobe Commerce Constraints and Risks

Adobe Commerce migration risk is rarely caused by record volume alone. The larger risk is whether the source data, business rules, integrations, and operating model can be translated into Adobe Commerce without weakening catalog governance, buyer access, storefront scope, pricing logic, fulfillment behavior, or commercial controls.

Adobe Commerce is built for complex commerce operations. That strength also increases the number of places where a migration can look technically complete while still failing business validation. Products may exist but behave incorrectly by storefront. Company accounts may migrate but lose the permissions that let buyers place orders. Shared catalogs may be created but expose the wrong product set or price. Campaign content may transfer but lose its timing logic. URLs may resolve but fail to preserve high-value routes.

A strong migration plan therefore treats constraints as design inputs. The goal is not to avoid Adobe Commerce complexity. The goal is to decide which parts of that complexity must be preserved, rebuilt, simplified, or handled through a more tailored migration path.

### Constraint Summary for Adobe Commerce Migration <a href="#constraint-summary-for-adobe-commerce-migration" id="constraint-summary-for-adobe-commerce-migration"></a>

| Constraint area                      | Main risk                                                                                                                                | Planning response                                                                                                 |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| B2B company structure                | Buyers lose company roles, approval authority, credit behavior, quote access, purchase order logic, or payment and shipping permissions. | Audit company accounts, company users, administrators, hierarchy, and purchasing controls before migration.       |
| Shared catalogs                      | Company-specific visibility and pricing do not match the intended buyer experience.                                                      | Confirm shared catalog ownership, customer group assignment, product visibility, and custom pricing requirements. |
| Website, store, and store-view scope | Data appears correct globally but fails by region, language, storefront, or business channel.                                            | Map source storefronts and content variants to Adobe Commerce scope before interpreting records.                  |
| Product and attribute architecture   | Products transfer as records but do not support variants, filtering, navigation, pricing, or operational maintenance.                    | Review product types, child SKU relationships, attributes, and attribute sets before migration.                   |
| Content staging and campaigns        | Scheduled commercial changes become static content or lose timing context.                                                               | Separate current content from future-dated campaign logic and decide what must be recreated.                      |
| Inventory and fulfillment            | Stock quantities do not reflect sources, stocks, salable quantity, reservations, or sales-channel assignment.                            | Align inventory migration with the intended fulfillment model rather than a single quantity field.                |
| URL and SEO continuity               | Product, category, CMS Page, or custom routes change without proper rewrite and redirect planning.                                       | Audit high-value URLs, rewrite needs, route conflicts, and post-migration redirect behavior.                      |
| Extensions and custom logic          | Extension-owned fields, workflows, ERP identifiers, or bespoke rules are omitted or flattened.                                           | Classify extension and custom data early and route unsupported logic through Custom Service where needed.         |

### B2B Controls Can Be More Important Than Customer Records <a href="#b2b-controls-can-be-more-important-than-customer-records" id="b2b-controls-can-be-more-important-than-customer-records"></a>

Adobe Commerce B2B migration constraints often concentrate above the individual customer account. A buyer may have a valid email, address, and order history, but that does not prove the buyer can act correctly after migration.

Company accounts can carry legal identity, company administrators, company users, approval structures, credit settings, quote permissions, purchase order behavior, payment method availability, shipping method availability, customer group assignment, and shared catalog access. If those controls are not accounted for, migrated B2B customers may see the wrong catalog, lose quote access, bypass approval logic, fail checkout, or no longer match the commercial policy attached to their account.

The constraint becomes more serious when the source platform uses a different representation for wholesale customers. Some platforms store B2B accounts as customer tags, customer groups, custom fields, account manager assignments, ERP IDs, external credit records, contract-pricing tables, or app-owned metadata. Those structures may not have a one-to-one path into Adobe Commerce company accounts.

B2B readiness should be judged by relationship completeness, not only customer count. The migration plan should confirm which customers are individual retail buyers, which belong to companies, which users administer company accounts, which users require purchasing authority, and which company-level rules must be available before the migrated store can accept orders.

### Shared Catalogs Create Visibility and Pricing Risk <a href="#shared-catalogs-create-visibility-and-pricing-risk" id="shared-catalogs-create-visibility-and-pricing-risk"></a>

Shared catalogs can make Adobe Commerce migration more sensitive than a standard product-and-price transfer. In a simpler platform, product visibility and price may depend mostly on product status, category assignment, customer group, or channel settings. In Adobe Commerce B2B, a company may need access to a specific shared catalog that determines which products are visible and what prices apply.

This creates two separate risks. First, product access can be wrong even when the catalog exists. A company may see products it should not see, fail to see contracted products, or lose access to a restricted assortment. Second, pricing can be wrong even when the product record and base price are correct, because the commercially relevant price may be company-specific or shared-catalog-specific.

Shared catalog planning should identify:

| Question                                                                                    | Why it matters                                                                             |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Which companies use public catalog access, shared catalog access, or both?                  | Visibility rules determine what buyers can browse and purchase.                            |
| Which products belong to each shared catalog?                                               | Product transfer alone does not prove buyer-specific assortment accuracy.                  |
| Which prices are base prices, customer group prices, tier prices, or shared catalog prices? | Pricing validation must test the buyer context that activates the price.                   |
| Which company assignments are required at launch?                                           | B2B buyers may be blocked or mispriced if company-to-catalog relationships are incomplete. |

For this reason, shared catalog migration often requires a narrower but deeper validation sample. It is better to prove a representative set of companies, products, and price rules than to confirm only that product records and customer records were created.

### Scope Mistakes Can Hide Until Storefront Review <a href="#scope-mistakes-can-hide-until-storefront-review" id="scope-mistakes-can-hide-until-storefront-review"></a>

Adobe Commerce scope is a frequent source of migration risk because websites, stores, and store views can change the meaning of data. A source platform may have multiple storefronts, language versions, regional sites, wholesale portals, or brand catalogs. Adobe Commerce may represent those differences through scope, categories, shared catalogs, customer groups, configuration, content assignment, or several mechanisms together.

A scope mistake is often hard to detect through record counts. The product may exist. The CMS Page may exist. The category may exist. The customer may exist. The failure appears only when a reviewer checks the correct website, store, store view, customer group, company account, language, or buyer context.

Common scope-related constraints include:

| Source condition                                          | Adobe Commerce risk                                                                                                |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Multilingual content stored as duplicated pages or fields | Content may land in the wrong store view or overwrite the default version.                                         |
| Separate regional stores with overlapping catalogs        | Product visibility, currency, language, tax, or configuration may not follow the intended website/store structure. |
| Wholesale and retail channels mixed in one source catalog | B2B and B2C visibility may need different Adobe Commerce mechanisms.                                               |
| Storefront-specific URLs or category paths                | SEO and navigation behavior may differ by scope.                                                                   |
| Global product fields used inconsistently                 | Attribute and content values may need scope-level cleanup before migration.                                        |

Scope mapping should happen before article-level or entity-level validation begins. Without that decision, reviewers may validate the wrong context and miss defects that affect only one storefront, language, company, or market.

### Product Architecture Can Turn Simple Catalogs Into Complex Migration Work <a href="#product-architecture-can-turn-simple-catalogs-into-complex-migration-work" id="product-architecture-can-turn-simple-catalogs-into-complex-migration-work"></a>

Adobe Commerce supports rich product modeling, but migration constraints appear when source catalog structure is incomplete, inconsistent, or too loosely defined. Products that are simple in the source platform may need to become configurable products, grouped products, bundle products, downloadable products, or carefully structured simple products in Adobe Commerce.

Variant logic is a common pressure point. If a source platform stores variation options as text labels rather than child SKUs, the migration plan may need to define how those options become Adobe Commerce relationships. If product attributes are inconsistent across categories, attribute sets may need preparation before products can be reviewed efficiently. If product fields power search, layered navigation, reports, promotions, merchandising, or integrations, the fields cannot be treated as decorative descriptions.

Product architecture risk usually rises when the catalog includes:

| Catalog pattern                                             | Risk                                                                                                 |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Products with many option combinations                      | Child SKU relationships, pricing, stock, images, and option labels can become difficult to validate. |
| Inconsistent attribute usage                                | Filtering, layered navigation, rules, and maintenance workflows may behave unpredictably.            |
| Multiple product families with different field requirements | Attribute sets may need planning before import.                                                      |
| App-owned product options or bundled logic                  | Standard field mapping may not preserve how buyers configure products.                               |
| Custom merchandising relationships                          | Related products, upsells, cross-sells, and category placement may need separate review.             |

When product architecture is weak in the source platform, the migration should not simply reproduce the weakness. It should decide whether Adobe Commerce should preserve the existing structure, normalize it, or route the affected areas through a more tailored service plan.

### Content Staging Can Be Lost If Campaign Timing Is Treated as Static Content <a href="#content-staging-can-be-lost-if-campaign-timing-is-treated-as-static-content" id="content-staging-can-be-lost-if-campaign-timing-is-treated-as-static-content"></a>

Adobe Commerce Content Staging creates a separate migration concern for merchants that rely on scheduled campaigns, seasonal changes, product updates, category changes, price-rule timing, CMS Page updates, or CMS block changes.

A source platform may store campaign timing in a theme, app, promotion scheduler, CMS workflow, custom table, or external planning system. If that timing is not visible in the supported migration scope, a migrated store may preserve the visible current content but lose the schedule that controls what should change later.

The practical constraint is not whether a CMS Page or promotion exists. The constraint is whether launch planning requires future-dated commercial behavior to be active, preserved, recreated, or intentionally excluded. Campaign-heavy merchants should separate:

| Content or rule state                                       | Migration decision                                                                |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Live content needed at launch                               | Include in the primary migration plan and validate storefront output.             |
| Scheduled content or price changes needed soon after launch | Plan recreation or tailored handling before launch.                               |
| Expired campaigns retained for reference                    | Decide whether historical content should migrate or remain archived externally.   |
| Campaign logic controlled by external systems               | Confirm whether Adobe Commerce should store it, integrate with it, or exclude it. |

Without that separation, content review can produce a false pass. Reviewers may approve what is visible today while missing scheduled changes that matter to commercial launch.

### Inventory Constraints Depend on Fulfillment Design <a href="#inventory-constraints-depend-on-fulfillment-design" id="inventory-constraints-depend-on-fulfillment-design"></a>

Adobe Commerce inventory planning can be more complex than transferring a quantity value. Inventory Management can involve sources, stocks, salable quantity, reservations, and sales-channel assignment. A source platform with a single stock field may not provide enough structure for a merchant that wants multi-location fulfillment, regional availability, pickup locations, warehouse routing, or separate B2B and B2C stock strategies.

Inventory risk is especially high when the source store uses custom warehouse fields, third-party fulfillment apps, ERP-controlled stock, external reservation systems, marketplace synchronization, or manual stock adjustments outside the commerce platform. In those cases, the visible stock number may be only an output of a broader operational process.

Before migration, inventory should be classified into three levels:

| Inventory level            | Migration question                                                                             |
| -------------------------- | ---------------------------------------------------------------------------------------------- |
| Product-level stock        | What stock value must buyers see at launch?                                                    |
| Source and stock structure | Which warehouses, locations, or sales channels should control availability?                    |
| Operational stock logic    | Which reservations, ERP processes, fulfillment rules, or external systems affect availability? |

A Standard Service path may be suitable when inventory can be represented through supported fields and the merchant has a clear target configuration. More complex fulfillment models may require Managed Service planning, Add-ons for supported configuration needs, or Custom Service when custom inventory logic or unsupported source data must be handled.

### SEO and URL Rewrite Risk Requires Route-Level Planning <a href="#seo-and-url-rewrite-risk-requires-route-level-planning" id="seo-and-url-rewrite-risk-requires-route-level-planning"></a>

Adobe Commerce can manage URL rewrites for products, categories, CMS Pages, and custom routes. That capability helps preserve SEO continuity, but it does not eliminate the need to plan routes carefully.

Migration risk appears when a source store has years of accumulated URL patterns, custom slugs, app-generated landing pages, localized URLs, category-path variations, discontinued products, redirected pages, or manually edited SEO routes. If those routes are not audited, the migrated store can launch with missing redirects, duplicate paths, broken category URLs, changed product URLs, or CMS Pages that no longer match high-value search-entry pages.

A useful URL review should separate:

| URL type                   | Review priority                                                                                            |
| -------------------------- | ---------------------------------------------------------------------------------------------------------- |
| High-traffic product URLs  | Preserve or redirect routes that directly affect revenue and search visibility.                            |
| High-traffic category URLs | Confirm category paths, layered-navigation expectations, and redirect behavior.                            |
| CMS Page URLs              | Preserve landing pages, brand pages, policy pages, and campaign pages that receive traffic.                |
| Custom routes              | Identify app-owned or manually created URLs that may not exist as ordinary products, categories, or pages. |
| Legacy redirects           | Decide which historical redirects must be recreated and which can be retired.                              |

URL preservation is not only a technical SEO task. It affects customer trust, paid campaign continuity, affiliate links, email campaigns, B2B procurement bookmarks, and internal sales team references.

### Extensions and Custom Logic Can Define the Real Migration Boundary <a href="#extensions-and-custom-logic-can-define-the-real-migration-boundary" id="extensions-and-custom-logic-can-define-the-real-migration-boundary"></a>

Adobe Commerce projects often involve extensions, custom modules, ERP integrations, PIM systems, CRM connections, payment customizations, tax services, warehouse integrations, middleware, marketplace feeds, or bespoke business rules. Some of that data may be visible in the source platform. Some may live outside the platform. Some may exist only as computed behavior.

This creates a hard boundary for migration planning. Supported entity transfer can move recognized data structures. It cannot automatically preserve every extension-owned workflow, every custom table, every external identifier, or every custom business rule unless those requirements are identified and included in the service plan.

Custom logic should be reviewed by asking:

| Custom area                     | Planning question                                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Extension-owned fields          | Are these fields standard records, supported custom fields, or extension-specific data?                        |
| External identifiers            | Which ERP, PIM, CRM, warehouse, marketplace, or accounting IDs must remain connected?                          |
| Checkout and payment logic      | Are there custom approval, payment, tax, shipping, or quote behaviors that affect orders?                      |
| B2B workflows                   | Do custom company rules, user permissions, or contract terms exist outside standard Adobe Commerce structures? |
| Reporting and compliance fields | Which fields must remain available for finance, audit, legal, or operational reporting?                        |

When custom logic matters to day-one operations, the risk is not solved by transferring more records. It is solved by deciding whether the requirement belongs in supported mapping, an Add-on, or Custom Service.

### How to Classify Adobe Commerce Migration Risk <a href="#how-to-classify-adobe-commerce-migration-risk" id="how-to-classify-adobe-commerce-migration-risk"></a>

Adobe Commerce constraints should be classified before service selection, not after the migration has already been configured. The classification does not need to be complex, but it must distinguish ordinary data preparation from structural or custom migration work.

| Risk level | Typical condition                                                                                                                          | Recommended planning response                                                                         |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| Low        | Standard product, customer, order, category, content, and URL needs with limited B2B or custom logic                                       | Confirm supported scope, run Demo Migration, and validate representative records.                     |
| Moderate   | Multi-store scope, configurable products, customer groups, meaningful URL preservation, or structured inventory needs                      | Prepare source data, define scope mapping, and consider Managed Service or relevant Add-ons.          |
| High       | Company accounts, shared catalogs, B2B permissions, staged campaigns, complex inventory, or integration-dependent data                     | Use a deeper planning review and validate buyer-context samples before Full Migration.                |
| Custom     | Unsupported source data, extension-owned records, outside-system identifiers, bespoke B2B workflows, or custom Adobe Commerce requirements | Route the affected work through Custom Service so the migration path reflects the actual requirement. |

This classification protects the migration plan from a common mistake: treating Adobe Commerce as a larger version of a simple catalog store. The platform can support advanced commerce operations, but only when the migration plan preserves the structures that make those operations work.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration constraints should be evaluated by business behavior, not just entity availability. The most important risks usually sit inside B2B authority, shared catalog access, storefront scope, catalog architecture, staged commercial activity, inventory design, URL continuity, and custom logic.

A successful migration plan identifies those constraints before migration execution begins. When the source data is simple and well-structured, a standard path may be enough. When buyer access, pricing, fulfillment, campaign timing, or integrations carry operational value, the plan should escalate deliberately through Managed Service, Add-ons, or Custom Service instead of forcing complex requirements into a simplified migration path.

Plan your Adobe Commerce migration around the buyer experience, commercial rules, and operational controls that must work after launch, then choose the service path that can preserve those requirements with enough validation depth.

### FAQs <a href="#faqs" id="faqs"></a>

**Why is Adobe Commerce migration risk higher for B2B stores?**

B2B stores often depend on company accounts, company users, approvals, quotes, purchase orders, credit settings, payment and shipping permissions, customer group assignment, and shared catalog access. If those relationships are not planned, customer records may migrate while purchasing authority and buyer-specific access fail.

**Are shared catalogs always a Custom Service requirement?**

No. Shared catalog needs should be reviewed first. If the required data and configuration fit supported migration and preparation paths, they may not require Custom Service. Custom Service becomes relevant when company-specific pricing, visibility, source data, or custom business rules fall outside the supported migration path.

**Can Adobe Commerce scope issues be found by checking record counts?**

Usually not. Record counts can confirm that products, customers, categories, or pages exist, but they cannot prove that the right content, catalog visibility, pricing, language, URL, or configuration appears in the right website, store, store view, company, or customer group context.

**What makes product data risky in Adobe Commerce migration?**

Risk increases when products rely on configurable relationships, child SKUs, attribute sets, layered navigation attributes, customer-group pricing, shared catalog pricing, bundled logic, app-owned options, or custom merchandising relationships. These structures affect storefront behavior and operations, not only product display.

**How should custom extension data be handled?**

Custom extension data should be identified before migration scope is finalized. Supported fields may fit standard mapping or Add-ons, while extension-owned records, custom tables, outside-system identifiers, and bespoke workflows may require Custom Service.
