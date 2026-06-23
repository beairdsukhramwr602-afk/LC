# Adobe Commerce Migration Pitfalls and Prevention

Adobe Commerce migration pitfalls usually appear when transferred data no longer supports the enterprise rules that made the original commerce environment work. Products, customers, orders, categories, CMS Pages, and Blog Posts may be present in the Target Platform, but launch can still be unsafe if company accounts lose structure, shared catalogs expose the wrong prices, store-view values are flattened, staged content loses timing context, or integrations can no longer recognize migrated records.

Pitfall prevention should start before migration configuration and continue through Demo Migration review, service-path selection, Full Migration validation, launch readiness, and post-launch stabilization. The safest approach is to identify where Adobe Commerce applies target-side rules, then prove those rules with representative records and buyer scenarios before the new store becomes the active sales channel.

### How Adobe Commerce Migration Pitfalls Usually Develop <a href="#how-adobe-commerce-migration-pitfalls-usually-develop" id="how-adobe-commerce-migration-pitfalls-usually-develop"></a>

Adobe Commerce projects are rarely risky because one standard entity is missing. They become risky when relationships between entities are incomplete or interpreted too broadly. A product may need configurable-product associations, scoped attribute values, category assignments, inventory behavior, shared catalog visibility, and contract pricing before it can function commercially. A customer may need company membership, role context, customer group behavior, address structure, and order-history continuity before the buyer experience is trustworthy.

The highest-risk pitfall pattern is a migration that looks complete in Admin but fails under real buyer conditions. Prevention therefore needs operational tests: company administrators, company users, public shoppers, regional storefronts, restricted catalogs, negotiated pricing, content journeys, and integration-dependent records should all be validated through the paths they actually use.

### Pitfall 1: Treating Company Accounts as Ordinary Customers <a href="#pitfall-1-treating-company-accounts-as-ordinary-customers" id="pitfall-1-treating-company-accounts-as-ordinary-customers"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

Adobe Commerce B2B migrations can fail when company structure is reduced to individual customer records. A source store may contain buyer names, emails, addresses, and order history, but Adobe Commerce may also need company accounts, company administrators, company users, roles, permissions, quote behavior, purchase order behavior, payment restrictions, shipping restrictions, customer groups, and shared catalog assignments.

When this structure is not planned, buyers may exist in the Target Platform but fail to operate as the correct business account. A company administrator may lose control, an employee may gain access to settings they should not manage, or a buyer may be separated from the company account that controls pricing and purchasing rights.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Warning sign                                                                                  | What it suggests                                                                      |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Business buyers exist in the customer export, but company hierarchy is unclear.               | Customer records may be handled as individual accounts instead of B2B organizations.  |
| Company administrators and ordinary company users are not separately identified.              | Account ownership, role control, and approval responsibility may be misassigned.      |
| Quote, purchase order, payment, shipping, or approval rules are documented outside the store. | B2B operating rules may require Custom Service review or manual target configuration. |
| Shared catalog assignment is discussed only after customer migration.                         | Buyer visibility and pricing may be configured too late for reliable validation.      |

#### Prevention <a href="#prevention" id="prevention"></a>

Prepare a company-account inventory before migration. The inventory should separate companies, administrators, users, role assumptions, customer groups, shared catalog assignment, payment and shipping rules, quote or purchase order behavior, and representative order history.

If the source platform does not store company relationships in a structure that maps cleanly to Adobe Commerce, treat the requirement as a Custom Service planning item. Add-ons can support filtering, mapping, or configuration when source data is structured and available, but they do not replace planning for unsupported B2B relationships, custom account rules, or external business records.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

Select several representative companies before Demo Migration: one simple company account, one account with multiple users, one account with special pricing, and one account with quote or approval requirements. Validate each account as a buyer, not only as an Admin record.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

A representative company can sign in through the intended account path, access the correct users and permissions, see the intended catalog and prices, and complete the expected quote, purchase order, or checkout path without exposing controls to the wrong buyer.

### Pitfall 2: Exposing the Wrong Products or Prices Through Shared Catalogs <a href="#pitfall-2-exposing-the-wrong-products-or-prices-through-shared-catalogs" id="pitfall-2-exposing-the-wrong-products-or-prices-through-shared-catalogs"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Shared catalog errors can create serious commercial risk. Adobe Commerce can control which products and prices are visible to specific companies or buyer segments. If migration planning transfers products and prices without preserving buyer segmentation, negotiated prices may become visible to the wrong audience, assigned buyers may lose access to private catalogs, or B2B-only products may appear publicly.

This pitfall is often missed during Admin-only review. The product grid may look complete, but the storefront may behave differently for guest users, general customers, company buyers, distributors, wholesalers, or region-specific accounts.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Warning sign                                                                                | What it suggests                                                                  |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| The same SKU has different prices for different companies, groups, or contracts.            | Shared catalog planning is required before migration.                             |
| Product visibility differs by account, region, distributor, buyer tier, or sales agreement. | Validation must test multiple buyer contexts, not one generic storefront session. |
| Private products appear in a broad product export.                                          | Visibility rules may need filtering, mapping, or custom handling.                 |
| Pricing rules are documented in contracts, ERP records, or sales-team spreadsheets.         | Source data alone may not contain enough information for direct migration.        |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Create a shared-catalog matrix before migration. For each important buyer segment, define which companies should access which catalog, which products should be included, whether custom prices apply, and which products or prices must remain hidden from guests or general customers.

Validation should include positive and negative tests. A buyer assigned to a shared catalog should see the expected products and prices. A buyer outside that catalog should not see restricted products, private categories, negotiated prices, or checkout conditions that do not belong to that segment.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

Choose one public product, one restricted product, one contract-priced SKU, and one product assigned to multiple catalogs. Test each SKU as a guest, a retail customer, a regular company buyer, and a company buyer with negotiated pricing.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Products, prices, category visibility, search results, cart totals, and checkout behavior match the intended company context across representative buyer segments.

### Pitfall 3: Flattening Website, Store, or Store-View Scope <a href="#pitfall-3-flattening-website-store-or-store-view-scope" id="pitfall-3-flattening-website-store-or-store-view-scope"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Adobe Commerce scope affects business-model separation, catalog structure, localized display values, URLs, SEO fields, content, configuration, pricing context, and buyer experience. Migration failures appear when scoped values are imported globally, localized values collapse into default values, products appear in the wrong website, or CMS Pages and Blog Posts lose the storefront context that made them useful.

A store may look correct in one language, region, or brand while failing in another. This is especially risky for multi-brand, multi-region, multilingual, or multi-currency commerce operations.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Warning sign                                                                                         | What it suggests                                                       |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| The source store has multiple languages, regions, brands, domains, currencies, or customer segments. | Scope mapping must be planned explicitly.                              |
| Product descriptions, category labels, URLs, or metadata differ by storefront.                       | Store-view values need targeted validation.                            |
| CMS Pages, Blog Posts, landing pages, or promotions differ by region.                                | A global import may damage content meaning.                            |
| Products should be available in one website but not another.                                         | Scope leakage could create catalog, compliance, or merchandising risk. |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Define the intended Adobe Commerce website, store, and store-view structure before migration. Assign products, categories, CMS Pages, Blog Posts, URL keys, metadata, customer context, and content assumptions to the correct scope.

Demo Migration samples should include launch-critical examples from every meaningful scope. A default-language product sample is not enough when the store depends on localized descriptions, regional categories, country-specific catalog visibility, or different brand storefronts.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

Build a scope sample set that includes one product, one category, one CMS Page, one Blog Post, and one high-value URL from each major language, region, or brand storefront. Confirm both Admin values and storefront display.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Each website, store, and store view displays the correct catalog, content, URLs, metadata, buyer context, and storefront behavior without leaking localized, regional, or brand-specific data into the wrong scope.

### Pitfall 4: Importing Products Without Preserving Buying Logic <a href="#pitfall-4-importing-products-without-preserving-buying-logic" id="pitfall-4-importing-products-without-preserving-buying-logic"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Adobe Commerce product records can carry buying logic, not only catalog information. Configurable products depend on child SKUs. Bundle, grouped, virtual, and downloadable products each require different structure. Attributes and attribute sets influence storefront display, search, filtering, comparison, merchandising, reporting, promotions, and operational review.

A product can exist in Admin but fail commercially if option labels, associated SKUs, custom options, downloadable files, bundle selections, category assignments, visibility settings, inventory behavior, or attribute configuration is wrong.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Warning sign                                                                                                     | What it suggests                                                               |
| ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| The source catalog includes variants, kits, bundles, grouped items, subscriptions, downloads, or custom options. | Product-type translation needs deeper planning.                                |
| Attribute names are inconsistent across product families.                                                        | Attribute set design may need cleanup before migration.                        |
| Filtering, search, merchandising, or reports depend on custom product fields.                                    | Attribute configuration must be validated, not only transferred values.        |
| Products appear in multiple catalogs or business channels.                                                       | Category, visibility, shared catalog, and scope rules need coordinated review. |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Build a catalog test set before migration. Include simple products, configurable products with child SKUs, bundle or grouped products where used, virtual or downloadable products where used, products with important attributes, products in multiple categories, and products with visibility or pricing exceptions.

Review storefront behavior as well as Admin presence. For each representative product, confirm option selection, price display, stock behavior, category placement, search behavior, layered navigation, cart behavior, quote behavior where relevant, and order creation.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

For every major product family, choose a best-selling product and a structurally difficult product. Include at least one product whose buying path depends on B2B price visibility, inventory behavior, or custom attributes.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Representative products can be found, selected, priced, added to cart or quote, purchased, and reviewed operationally with the intended options, relationships, categories, attributes, and inventory behavior intact.

### Pitfall 5: Missing Content Staging and Campaign Timing <a href="#pitfall-5-missing-content-staging-and-campaign-timing" id="pitfall-5-missing-content-staging-and-campaign-timing"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Adobe Commerce operations may depend on scheduled content, seasonal merchandising, campaign landing pages, future category changes, promotional timing, or staged product and pricing updates. Migration risk appears when launch-current content and future content are treated as the same transfer requirement.

If staged or future-facing content is not separated, teams may launch with outdated pages, expose campaign assets too early, lose scheduled updates, or assume future changes were migrated when they were actually outside the selected scope.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Warning sign                                                                              | What it suggests                                               |
| ----------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| The store relies on seasonal campaigns, scheduled promotions, or future price changes.    | Staging review should be included in migration planning.       |
| Marketing and merchandising teams already prepared campaign pages before launch.          | Current-state migration may not cover future content needs.    |
| CMS Pages, blocks, categories, or products are tied to campaign calendars.                | Content timing must be separated from static content transfer. |
| Teams disagree about whether future campaigns should be migrated, recreated, or deferred. | Launch scope is not stable enough for safe validation.         |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Separate current launch data from scheduled future changes. Decide whether future campaign content, scheduled price changes, staged CMS Pages, staged blocks, category changes, or promotion rules should be migrated, recreated, deferred, or handled after launch.

When staged content depends on business rules that are not stored as ordinary content records, raise the requirement early. Custom Service may be needed when timing logic, rule relationships, or campaign structures require bespoke handling.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Before Full Migration, ask marketing and merchandising teams to mark each campaign asset as launch-critical, future-scheduled, manual setup, or out of scope. Include only launch-critical and explicitly approved future records in migration validation.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Launch-current content appears at the right time, future commercial changes are clearly assigned to a migration, configuration, or manual setup path, and no scheduled content appears unexpectedly before or after launch.

### Pitfall 6: Losing Inventory and Fulfillment Meaning <a href="#pitfall-6-losing-inventory-and-fulfillment-meaning" id="pitfall-6-losing-inventory-and-fulfillment-meaning"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Adobe Commerce inventory behavior may involve sources, stocks, sales-channel assignments, salable quantity, backorder behavior, reservations, and external fulfillment systems. Migration risk appears when quantities transfer but no longer support the intended storefront availability or operational fulfillment model.

This issue is easy to miss if validation checks only whether a quantity exists. Buyers care whether products can be purchased accurately. Operations teams care whether orders can be fulfilled from the right source and synchronized with the right system.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Warning sign                                                                     | What it suggests                                                                               |
| -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Inventory is managed by ERP, WMS, POS, marketplace, or fulfillment integrations. | Migration planning must define what is transferred and what is system-controlled after launch. |
| Multiple warehouses, regions, or fulfillment sources are used.                   | Source and stock assumptions need target-side review.                                          |
| Backorders, preorder behavior, or special availability rules are important.      | Availability logic may require configuration beyond data transfer.                             |
| Configurable product availability depends on child SKU stock.                    | Parent-child availability must be tested, not assumed.                                         |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Identify which inventory data should be migrated, which data should be configured in Adobe Commerce, and which data should be controlled by external systems after launch. Include inventory-sensitive products in the Demo Migration and final validation samples.

Test source assignment, stock assignment, salable quantity, storefront availability, checkout acceptance, quote behavior where relevant, and order creation. When inventory behavior depends on external systems, validate system ownership and identifier continuity before launch.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

Select products from every important fulfillment pattern: single-source stock, multi-source stock, backorder-sensitive products, configurable products with child SKU availability, and products controlled by an external fulfillment system.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Storefront availability, cart behavior, quote or checkout acceptance, and internal inventory review align with the intended fulfillment model for representative products and buyer contexts.

### Pitfall 7: Breaking URLs, SEO Paths, and Priority Content Journeys <a href="#pitfall-7-breaking-urls-seo-paths-and-priority-content-journeys" id="pitfall-7-breaking-urls-seo-paths-and-priority-content-journeys"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Adobe Commerce migrations can weaken organic traffic, paid campaign continuity, partner links, internal navigation, and customer trust when important URLs are not planned and validated. Product pages, category pages, CMS Pages, Blog Posts, campaign pages, localized landing pages, redirects, canonical behavior, metadata, and internal links can all carry business value.

URL risk is higher when the source store has localized paths, legacy URL rewrites, custom route structures, blog extensions, campaign landing pages, or a long history of SEO changes.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Warning sign                                                                           | What it suggests                                                  |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| High-traffic product, category, blog, or CMS URLs exist in search or campaign reports. | A priority URL list is required.                                  |
| The source store uses custom URL rewrites or SEO extensions.                           | Redirect and route behavior may need custom review.               |
| Localized URLs differ by store view.                                                   | SEO validation must be scope-specific.                            |
| Blog content comes from an extension or external content system.                       | Blog migration may need Custom Service or separate configuration. |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Create a priority URL list before migration. Include high-revenue product pages, high-traffic categories, evergreen CMS Pages, Blog Posts, localized landing pages, campaign URLs, pages with backlinks, and internal navigation paths.

After migration, validate both content presence and URL behavior. A page that exists under a different path may still require redirect planning. If source-store activity continues before launch, include affected URLs in the selected Additional Migration Options and revalidate them before go-live.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

Use analytics, advertising, search, and sales data to build a priority URL list. Validate the top product, category, CMS Page, Blog Post, and campaign URLs in every major store view before launch.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Priority URLs resolve to the intended target pages, redirects behave correctly, localized paths stay within the correct scope, internal links are usable, and high-value content journeys remain intact.

### Pitfall 8: Treating Extension, Integration, or Custom-Module Data as Standard Store Data <a href="#pitfall-8-treating-extension-integration-or-custom-module-data-as-standard-store-data" id="pitfall-8-treating-extension-integration-or-custom-module-data-as-standard-store-data"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Adobe Commerce projects often depend on extensions, integrations, custom modules, ERP records, CRM records, PIM identifiers, subscription systems, loyalty platforms, tax services, fulfillment systems, payment gateways, or analytics infrastructure. Migration risk increases when these records are assumed to behave like standard products, customers, orders, categories, CMS Pages, or Blog Posts.

The data may be commercially important but not directly transferable through a standard migration scope. It may require mapping, enrichment, target-side configuration, external-system alignment, or Custom Service review.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Warning sign                                                                                       | What it suggests                                                          |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Important data comes from extensions, custom modules, or external systems.                         | Standard entity migration may not cover the full operational requirement. |
| ERP, CRM, PIM, WMS, POS, marketplace, loyalty, or subscription identifiers must remain stable.     | Identifier continuity needs explicit planning.                            |
| Business teams rely on reports, tags, flags, statuses, or custom fields outside standard entities. | Custom fields may require mapping or custom handling.                     |
| The target implementation uses different modules than the source store.                            | Record meaning may need transformation, not direct transfer.              |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Separate standard store data from extension, integration, and custom-module data before migration. Define which records are in standard scope, which need Add-ons, which require target-side configuration, and which require Custom Service.

Document outside-system identifiers and operational dependencies early. If the business must preserve ERP IDs, CRM IDs, subscription IDs, loyalty references, quote references, or fulfillment IDs, validate whether those identifiers are available, transferable, and usable in the Target Platform.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

Create a dependency register that lists each extension, integration, custom module, external identifier, and owner. Mark whether each dependency is migrated, mapped through Add-ons, configured manually, reviewed under Custom Service, or excluded from launch scope.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Commercially important custom, extension, and integration-dependent records are either migrated, mapped, configured, deferred, or excluded through an explicit decision, and downstream systems can still recognize the records they depend on.

### Pitfall 9: Using Entity Points as a Complexity Score <a href="#pitfall-9-using-entity-points-as-a-complexity-score" id="pitfall-9-using-entity-points-as-a-complexity-score"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

Entity Points help define counted data capacity for the purchased service license. They do not measure Adobe Commerce complexity, B2B readiness, integration risk, custom-module difficulty, validation depth, or launch safety. A store can fit within an Entity Points Plan and still require Managed Service, Add-ons, or Custom Service because the migration outcome depends on complex business rules.

This pitfall occurs when teams treat capacity as proof that the migration approach is simple. For Adobe Commerce, the harder questions often concern data relationships, buyer visibility, pricing behavior, scope, integration continuity, and validation readiness.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

| Warning sign                                                                                              | What it suggests                                          |
| --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| The plan focuses only on product, customer, order, and content counts.                                    | Capacity is being confused with migration complexity.     |
| B2B, pricing, integrations, and custom modules are discussed after purchase.                              | Service scope may be under-planned.                       |
| Stakeholders expect every business rule to be handled because the Entity Points Plan has enough capacity. | Outcome expectations need clarification before execution. |
| Validation samples are chosen by record volume rather than business importance.                           | Risk-based validation is missing.                         |

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Use Entity Points for counted data capacity and use service planning for complexity. Adobe Commerce planning should separately review B2B structures, shared catalogs, pricing visibility, scoped storefront behavior, custom fields, integrations, and validation requirements.

When the migration requires filtering, mapping, or configuration, review Add-ons. When the requirement involves unsupported source structures, custom modules, outside-system identifiers, bespoke transformation, or Custom Platform behavior, review Custom Service.

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

Estimate Entity Points separately from migration complexity. Then create a second planning view for B2B requirements, shared catalogs, scoped data, integrations, custom fields, Add-ons, Custom Service, and validation samples.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

The Entity Points Plan supports the expected counted data capacity, while service scope separately covers Adobe Commerce complexity, Add-ons, Custom Service requirements, validation expectations, and launch-readiness work. Records already counted through the service license do not consume Entity Points again simply because another migration action is performed; new eligible Product, Customer, Order, or Blog Posts records may consume Entity Points when migrated for the first time.

### Pitfall 10: Waiting Until Launch to Handle New or Changed Data <a href="#pitfall-10-waiting-until-launch-to-handle-new-or-changed-data" id="pitfall-10-waiting-until-launch-to-handle-new-or-changed-data"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

Adobe Commerce projects often continue while the source store remains active. New products, new customers, new orders, changed categories, updated prices, changed company assignments, new campaign pages, and updated integrations may appear after Demo Migration or even after Full Migration preparation.

The pitfall is assuming that one successful migration review covers every later change. For Adobe Commerce, later changes may affect buyer visibility, shared catalog pricing, store-view content, inventory behavior, URLs, integration identifiers, and B2B account context.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

| Warning sign                                                                                    | What it suggests                                                   |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| The source store will continue taking orders before launch.                                     | Follow-up migration planning is needed.                            |
| Product, customer, pricing, catalog, company, or content updates continue after Demo Migration. | Validation samples must be refreshed before go-live.               |
| Teams expect Additional Migration Options to solve every late change automatically.             | Follow-up activity still needs scope review and revalidation.      |
| New records include products, customers, orders, or Blog Posts.                                 | Entity Points treatment must be understood before launch planning. |

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Plan follow-up migration handling before launch. Define which changes are expected after Demo Migration, which changes must be included before go-live, which records require revalidation, and which changes should be configured manually or deferred.

Additional Migration Options can support follow-up migration activity, but they do not remove the need to review Adobe Commerce-specific impact. Company assignments, shared catalog visibility, pricing, scoped content, URL behavior, inventory, integrations, and Custom Service outputs should be revalidated after relevant late changes.

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

Create a launch-delta checklist covering new products, customers, orders, Blog Posts, CMS Pages, company records, shared catalog changes, pricing updates, URL changes, inventory changes, and integration identifiers. Use it to decide what must be included and retested before go-live.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Late changes are assigned to the appropriate migration, configuration, manual, or deferred path; affected Adobe Commerce structures are revalidated; and Entity Points are applied only to new eligible records when they are migrated for the first time.

### Adobe Commerce Pitfall Prevention Checklist <a href="#adobe-commerce-pitfall-prevention-checklist" id="adobe-commerce-pitfall-prevention-checklist"></a>

Before launch, confirm that the migration plan answers these questions:

* Are company accounts, company users, roles, and permissions represented accurately?
* Are shared catalogs, buyer-specific prices, customer groups, and restricted products tested through real buyer contexts?
* Are website, store, and store-view values preserved where scope matters?
* Are configurable products, product options, attributes, attribute sets, categories, and inventory behavior validated on the storefront?
* Are Content Staging assumptions, campaign timing, CMS Pages, Blog Posts, URLs, and redirects reviewed before launch?
* Are extension, integration, custom-module, and external-system dependencies separated from standard store data?
* Are Add-ons and Custom Service requirements documented before Full Migration?
* Are Additional Migration Options tied to specific late changes and revalidation needs?
* Are Entity Points used for counted data capacity, not as a shortcut for complexity assessment?

### When to Escalate Before Full Migration <a href="#when-to-escalate-before-full-migration" id="when-to-escalate-before-full-migration"></a>

Escalation should happen before Full Migration when a requirement affects the meaning of migrated data, not only when a record fails to transfer. Adobe Commerce usually needs earlier review when the project includes complex B2B rules, custom shared catalog behavior, unusual pricing structures, heavily scoped storefronts, staged campaigns, external identifiers, custom modules, or source data that does not map cleanly to the Target Platform.

Use Add-ons when the requirement fits structured filtering, mapping, or configuration support. Use Custom Service review when the requirement depends on unsupported source structures, custom modules, external business records, bespoke transformation, Custom Platform output, or implementation-specific logic that cannot be handled as a standard configuration choice.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration pitfalls are preventable when the team validates business behavior, not only transferred records. The safest migration plan tests company accounts, shared catalogs, buyer-specific prices, scoped storefront data, catalog relationships, content timing, inventory, URLs, integrations, custom data, Entity Points assumptions, Add-ons, Custom Service needs, and follow-up migration activity before launch decisions are finalized.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are Adobe Commerce migration pitfalls mostly technical problems?**

No. Many Adobe Commerce migration pitfalls are business-structure problems. The technical transfer can succeed while company accounts, shared catalogs, buyer-specific pricing, scoped content, integrations, or custom records still need review.

**Does a successful Demo Migration prove Adobe Commerce is launch-ready?**

No. Demo Migration is a proof point, not final launch approval. Adobe Commerce still needs validation across B2B accounts, shared catalogs, scoped storefronts, products, URLs, inventory, integrations, and any late source-store changes.

**Can Add-ons prevent Adobe Commerce migration pitfalls?**

Add-ons can help when the requirement fits structured filtering, mapping, or configuration support. They do not replace Custom Service when the issue depends on unsupported source structures, custom modules, external records, or bespoke transformation.

**Do Entity Points measure Adobe Commerce migration complexity?**

No. Entity Points help define counted data capacity for the service license. They do not measure B2B complexity, shared catalog behavior, scoped storefront risk, integration dependency, Custom Service needs, or validation effort.

**When should Custom Service be considered for Adobe Commerce?**

Custom Service should be considered when the migration depends on custom B2B behavior, non-standard pricing logic, extension-owned data, custom modules, external identifiers, Custom Platform output, or data transformation that cannot be handled through standard migration scope or Add-ons.
