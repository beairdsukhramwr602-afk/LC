# Adobe Commerce Migration Pitfalls and Prevention

Adobe Commerce migration failures usually do not come from a single missing product or customer record. The higher-risk failures appear when migrated data is technically present but no longer supports the commercial rules that made the original store work: company buyers lose the correct permissions, shared catalogs expose the wrong prices, staged campaigns are disconnected from launch timing, localized store views inherit generic content, or inventory availability no longer reflects fulfillment reality.

Prevention should begin before the Full Migration and continue through Demo Migration review, service-path selection, and final validation. The most reliable approach is to identify where Adobe Commerce applies target-side rules, then prove those rules with representative records before the store becomes the active sales channel.

### Pitfall 1: Treating B2B Company Accounts as Ordinary Customers <a href="#pitfall-1-treating-b2b-company-accounts-as-ordinary-customers" id="pitfall-1-treating-b2b-company-accounts-as-ordinary-customers"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

A migration may transfer customer names, emails, addresses, and order history while flattening the organization-level structure that Adobe Commerce uses for B2B commerce. Company administrators, company users, approval permissions, credit settings, purchase order behavior, quote access, payment methods, shipping methods, and shared catalog assignments can lose their intended relationship.

When this happens, buyers may exist in the target store but cannot operate as the correct business account. A purchasing manager may lose approval authority, an employee may gain access to settings they should not control, or a company may be assigned to the wrong customer group or shared catalog.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Warning sign                                                                                   | What it suggests                                                                         |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Customer exports contain business buyers but no clear company hierarchy or role information.   | Customer records are being treated as individual accounts rather than B2B organizations. |
| Company administrators are not clearly identified before migration.                            | User access and approval responsibility may be misassigned.                              |
| Quote, purchase order, credit, payment, or shipping permissions are not documented by company. | Commercial controls may not be reproducible in Adobe Commerce.                           |
| Shared catalog assignment is discussed only after customer import.                             | Catalog visibility and company permissions may be configured too late.                   |

#### Prevention <a href="#prevention" id="prevention"></a>

Prepare a company-account inventory before migration. The inventory should separate companies, company administrators, ordinary company users, company hierarchy where relevant, customer group or shared catalog assignment, quote permission, purchase order permission, credit assumptions, payment methods, shipping methods, and representative order history.

If the source platform does not store this information in a structure that maps cleanly to Adobe Commerce, treat it as a Custom Service planning item rather than a simple customer migration. Add-ons can help with filtering, mapping, or configuration where the source data is available and structured, but they do not replace planning for unsupported B2B relationships or custom business rules.

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

A distributor migrating to Adobe Commerce has one customer record for each buyer but keeps buyer roles in a sales-team spreadsheet. The safer plan is to include the spreadsheet in pre-migration review, define how company administrators and users should be created, and test several companies during Demo Migration before committing to Full Migration.

#### Pass Condition <a href="#pass-condition" id="pass-condition"></a>

A representative company can sign in through the intended account path, access the correct users and permissions, see the intended catalog and prices, and complete the expected quote, purchase order, or checkout path without exposing controls to the wrong buyer.

### Pitfall 2: Exposing the Wrong Products or Prices Through Shared Catalogs <a href="#pitfall-2-exposing-the-wrong-products-or-prices-through-shared-catalogs" id="pitfall-2-exposing-the-wrong-products-or-prices-through-shared-catalogs"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Adobe Commerce shared catalogs can control product visibility and custom pricing for different companies. A migration that transfers products and prices without preserving buyer segmentation can expose negotiated prices to the wrong audience, hide products from assigned buyers, or make private B2B products visible in a broader catalog.

This pitfall is especially dangerous because the Admin may appear populated while storefront behavior is wrong. The problem only becomes obvious when buyers sign in under different company contexts and compare what they can see, search, add to cart, and purchase.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Warning sign                                                                              | What it suggests                                                         |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| The same SKU has different prices for different customer groups, companies, or contracts. | Shared catalog planning is required before migration.                    |
| Product visibility differs by account, region, distributor, or buyer tier.                | Catalog assignment cannot be validated with one generic storefront test. |
| Private products appear in the public product export.                                     | Visibility rules may need filtering or custom handling.                  |
| Pricing rules are documented in contracts rather than source database fields.             | Additional mapping or Custom Service review may be required.             |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Create a shared-catalog matrix before migration. For each important buyer segment, define which companies should access which catalog, which products should be included, whether custom prices apply, and whether any products must remain hidden from guests or general customers.

Validation should include positive and negative tests. A buyer assigned to a shared catalog should see the expected products and prices. A buyer outside that catalog should not see private prices or restricted products. Testing only one company account is insufficient for Adobe Commerce B2B stores.

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A manufacturer sells the same SKU to wholesalers, franchisees, and direct customers at different prices. The recommended approach is to prepare representative companies for each segment, confirm shared catalog assignment during Demo Migration, and validate logged-in storefront behavior before Full Migration.

#### Pass Condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Products, prices, search results, category visibility, cart totals, and checkout behavior match the intended company context across all representative buyer segments.

### Pitfall 3: Losing Website, Store, or Store-View Meaning <a href="#pitfall-3-losing-website-store-or-store-view-meaning" id="pitfall-3-losing-website-store-or-store-view-meaning"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Adobe Commerce uses websites, stores, and store views to control business-model separation, catalog structure, localized display values, and configuration scope. Migration failures occur when source data is imported at the wrong scope, when localized values collapse into global defaults, or when products and categories become available in storefronts where they should not appear.

The store may look correct in one language or region while failing in another. Product names, descriptions, category labels, CMS Pages, Blog Posts, URL keys, metadata, prices, tax context, and content blocks can drift if scope is not planned before migration.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Warning sign                                                                      | What it suggests                             |
| --------------------------------------------------------------------------------- | -------------------------------------------- |
| The source store has multiple languages, regions, brands, domains, or currencies. | Scope mapping must be planned explicitly.    |
| Product descriptions differ by language or storefront.                            | Store-view values may need targeted mapping. |
| Categories or CMS Pages differ by region.                                         | A single global import may be unsafe.        |
| URL keys and metadata vary by language.                                           | SEO validation must be scope-specific.       |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Map the intended target scope before migration. Identify each Adobe Commerce website, store, and store view that must exist at launch, then assign product data, category data, CMS Pages, Blog Posts, URLs, metadata, customer context, and configuration assumptions to the correct scope.

Do not use a generic sample set for validation. Every business-critical scope should have representative products, categories, customers, orders, URLs, and content reviewed after Demo Migration. When the source platform does not separate scoped data cleanly, Advanced Data Mapping, Advanced Data Configure, or Custom Service review may be needed depending on the source structure and required outcome.

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A merchant has English and French storefronts with different category names, product copy, and SEO URLs. The safer migration plan is to validate both store views separately, not only the default language, and confirm localized URL behavior before launch.

#### Pass Condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Each website, store, and store view displays the correct catalog, content, URL keys, metadata, buyer context, and storefront behavior without leaking localized or regional data into the wrong scope.

### Pitfall 4: Importing Products Without Preserving Buying Logic <a href="#pitfall-4-importing-products-without-preserving-buying-logic" id="pitfall-4-importing-products-without-preserving-buying-logic"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Adobe Commerce product records can carry buying logic, not just catalog information. Configurable products depend on associated simple SKUs. Bundle, grouped, virtual, and downloadable products each require their own structure. Attributes and attribute sets influence storefront display, search, filtering, comparison, reports, promotions, and operational review.

A product can exist in Admin but fail on the storefront if child SKUs, option labels, required attributes, category assignments, downloadable files, bundle selections, or visibility settings were not interpreted correctly.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Warning sign                                                                                                   | What it suggests                                                   |
| -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| The source catalog has variants, kits, bundles, grouped products, subscriptions, downloads, or custom options. | Product-type translation needs deeper planning.                    |
| Attribute names are inconsistent across product families.                                                      | Attribute set design may need cleanup before migration.            |
| Filtering and search depend on custom product fields.                                                          | Attribute configuration must be validated, not only values.        |
| Products appear in multiple catalogs or business channels.                                                     | Category, visibility, and scope rules may need coordinated review. |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Build a catalog test set before migration. Include simple products, configurable products with child SKUs, bundle or grouped products if used, virtual or downloadable products if used, products with important attributes, products in multiple categories, and products with visibility or pricing exceptions.

The review should prove storefront behavior, not only Admin presence. For each representative product, confirm option selection, price display, stock behavior, category placement, search behavior, layered navigation, cart behavior, and order creation.

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

A fashion merchant migrating to Adobe Commerce has configurable products for size and color. The recommended approach is to test parent products and child SKUs together, confirm option labels and inventory behavior, and validate that filters still support buyer discovery after migration.

#### Pass Condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Representative products can be found, filtered, configured, added to cart, purchased, and reviewed in Admin with the intended product structure and buyer-facing behavior intact.

### Pitfall 5: Ignoring Content Staging and Scheduled Commercial Changes <a href="#pitfall-5-ignoring-content-staging-and-scheduled-commercial-changes" id="pitfall-5-ignoring-content-staging-and-scheduled-commercial-changes"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Adobe Commerce can support scheduled updates for products, categories, price rules, CMS Pages, and CMS blocks through Content Staging. Migration risk appears when a merchant has future promotions, seasonal content, campaign pages, scheduled price changes, or launch calendars that are not represented in the migration plan.

If staged content is ignored, the target store may launch with correct current content but lose future campaign timing. Alternatively, future prices or content may appear too early, too late, or without the intended relationship to categories and promotions.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Warning sign                                                                 | What it suggests                                     |
| ---------------------------------------------------------------------------- | ---------------------------------------------------- |
| The business relies on seasonal campaigns or scheduled promotions.           | Staging review should be part of migration planning. |
| Price rules or content changes are prepared before launch.                   | Current-state migration alone may not be enough.     |
| CMS Pages or blocks are tied to campaign calendars.                          | Content needs timing and placement review.           |
| Teams disagree about whether future campaigns should be migrated or rebuilt. | Launch scope is not yet stable.                      |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Separate current launch data from scheduled future changes. Decide whether future campaign content, scheduled price changes, staged CMS Pages, or promotion rules should be migrated, recreated, deferred, or handled after launch. Document ownership clearly so marketing, merchandising, and technical teams do not assume different launch states.

If scheduled rules or staged content require bespoke handling, treat them as a Custom Service review item. Standard content transfer may not preserve the full commercial timing model unless the source structure and target requirements are compatible.

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

A retailer plans a Black Friday campaign shortly after replatforming. The recommended approach is to freeze the launch-state catalog, separately document future campaign assets and pricing rules, and test staged changes in the target environment before the campaign window.

#### Pass Condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Launch-state content appears correctly at go-live, and any scheduled updates included in scope have verified timing, affected entities, preview behavior, and rollback expectations.

### Pitfall 6: Misreading Inventory Availability After Migration <a href="#pitfall-6-misreading-inventory-availability-after-migration" id="pitfall-6-misreading-inventory-availability-after-migration"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Adobe Commerce Inventory Management can involve sources, stocks, sales-channel assignments, salable quantity, and reservations. A migration that transfers stock numbers without validating inventory behavior can show misleading availability, block legitimate purchases, allow overselling, or assign products to the wrong fulfillment context.

Inventory issues can be hidden during static Admin review. They often appear only when a buyer views the product page, selects a variant, adds the item to cart, or places an order under a specific website or sales channel.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Warning sign                                                                                            | What it suggests                                           |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| The merchant uses multiple warehouses, pickup locations, regional stock, or channel-specific inventory. | Source and stock mapping must be reviewed.                 |
| Configurable products have child SKUs with different availability.                                      | Parent availability cannot be validated alone.             |
| Backorders, low-stock rules, or reservations matter operationally.                                      | Storefront behavior and order flow must be tested.         |
| Inventory comes from an ERP, warehouse system, or marketplace connector.                                | Post-migration synchronization should be part of the plan. |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Prepare inventory validation samples before migration. Include in-stock products, out-of-stock products, low-stock products, products assigned to different fulfillment locations, configurable products with mixed child availability, and products synchronized from outside systems.

After Demo Migration, validate storefront availability, cart behavior, checkout behavior, Admin quantity, salable quantity, and integration expectations. If outside systems control inventory after launch, confirm which system owns the final stock state and when synchronization should resume.

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A merchant with separate regional warehouses migrates to Adobe Commerce and plans to connect an ERP after launch. The recommended approach is to freeze the migration stock snapshot, validate source and stock assignment, and define when ERP synchronization should resume so the target store does not overwrite or duplicate availability logic.

#### Pass Condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Representative products show accurate availability in the storefront, behave correctly in cart and checkout, and align with the intended fulfillment and synchronization model after launch.

### Pitfall 7: Breaking SEO Routes and Redirect Continuity <a href="#pitfall-7-breaking-seo-routes-and-redirect-continuity" id="pitfall-7-breaking-seo-routes-and-redirect-continuity"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Adobe Commerce supports URL rewrites for products, categories, CMS Pages, and custom routes. Migration problems appear when historical URLs are not mapped, store-view URL keys are collapsed, category paths change without redirects, or custom routes from the source platform are ignored.

A catalog may be migrated successfully while search visibility and external links suffer because important URLs no longer resolve. For large Adobe Commerce stores, route continuity is not a cosmetic concern; it can affect revenue, advertising efficiency, customer bookmarks, and organic search performance.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Warning sign                                                                          | What it suggests                                         |
| ------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| The source store has long-standing product, category, CMS Page, or landing-page URLs. | Redirect planning is required before launch.             |
| URLs differ by language, brand, region, or store view.                                | Store-view-specific URL validation is needed.            |
| Custom landing pages or campaign routes exist outside standard catalog paths.         | Custom rewrite planning may be necessary.                |
| The launch plan changes category hierarchy or product URL keys.                       | Redirect rules should be reviewed before Full Migration. |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Export high-value source URLs before migration. Prioritize product URLs, category URLs, CMS Pages, Blog Posts, campaign pages, landing pages, and routes with organic traffic, paid traffic, backlinks, or customer-service dependency. Map each important source URL to its intended Adobe Commerce destination and test redirects before launch.

For multilingual or multi-store businesses, validate routes per store view. A redirect that works in one language or website does not prove that all scoped routes are safe.

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A merchant changes category hierarchy during migration. The recommended approach is to preserve a high-value URL map, configure redirects for changed paths, and test representative product, category, CMS Page, and campaign URLs before launch.

#### Pass Condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Important source URLs resolve to the intended Adobe Commerce destinations with correct storefront scope, correct language or regional context, and no avoidable broken routes.

### Pitfall 8: Treating Extension or Custom Logic as Standard Data <a href="#pitfall-8-treating-extension-or-custom-logic-as-standard-data" id="pitfall-8-treating-extension-or-custom-logic-as-standard-data"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Many Adobe Commerce projects rely on custom modules, third-party extensions, ERP integrations, PIM feeds, marketplace connectors, tax services, payment workflows, shipping rules, loyalty programs, subscriptions, quote extensions, or approval logic that lives outside ordinary product, customer, order, and CMS data.

If extension-owned or custom logic is treated as standard migration data, the target store may receive records without the behavior needed to use them. Fields can transfer without workflows, IDs can lose external meaning, and integrations can overwrite migrated values after launch.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Warning sign                                                                                             | What it suggests                                                    |
| -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Important information is stored in custom tables, extension fields, ERP IDs, PIM IDs, or middleware.     | Custom Service review is likely required.                           |
| Business teams describe behavior that is not visible in standard Admin fields.                           | Data alone may not reproduce the process.                           |
| The source platform uses custom modules for pricing, approval, fulfillment, subscriptions, or B2B rules. | Target behavior must be designed, not assumed.                      |
| External systems will reconnect after migration.                                                         | Identifier mapping and synchronization ownership must be confirmed. |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Inventory every system and extension that contributes to the customer, catalog, pricing, order, fulfillment, tax, payment, or content model. For each dependency, decide whether the data should be migrated, remapped, rebuilt, ignored, or handled by a post-migration integration process.

Use Custom Service when the required outcome depends on custom logic, unsupported extension data, outside-system identifiers, Custom Platform behavior, or bespoke transformation. Use Add-ons only when the requirement is a defined filtering, mapping, or data configuration enhancement within the approved migration plan.

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A B2B merchant stores contract pricing references in an ERP and displays them in Adobe Commerce through custom integration. The recommended approach is to document the ERP identifier relationship, confirm whether contract prices should be migrated or resynchronized, and validate representative buyers only after integration ownership is clear.

#### Pass Condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Every critical extension, custom field, outside-system identifier, and integration-owned process has a defined migration or reconstruction decision, and representative target records behave correctly after the relevant systems are connected or intentionally excluded.

### Prevention Priorities Before Launch <a href="#prevention-priorities-before-launch" id="prevention-priorities-before-launch"></a>

Adobe Commerce pitfall prevention works best when each risk is tied to a concrete pre-launch proof. The checklist below should be reviewed before Full Migration and again before launch approval.

| Prevention priority       | Required proof                                                                                          | Escalation signal                                                                          |
| ------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| B2B company structure     | Representative companies, administrators, users, permissions, and commercial settings behave correctly. | Company data exists but buyer access or account behavior is unclear.                       |
| Shared catalogs           | Assigned and non-assigned buyers see the intended products and prices.                                  | Pricing or visibility differs by company but no shared-catalog matrix exists.              |
| Scope                     | Each website, store, and store view displays the correct catalog, content, URLs, and buyer context.     | Localized or regional data appears only in generic global review.                          |
| Product structure         | Complex products can be selected, configured, purchased, and managed correctly.                         | Product records exist but variant, bundle, download, or attribute behavior is untested.    |
| Staged commercial content | Launch-state and scheduled-state content are separated and tested.                                      | Future campaigns or price changes are mixed into migration scope without timing decisions. |
| Inventory behavior        | Availability, sources, stocks, salable quantity, and synchronization expectations are validated.        | Stock numbers transfer but fulfillment logic is not proven.                                |
| URL continuity            | High-value URLs redirect or resolve correctly by storefront context.                                    | URL testing is delayed until after launch.                                                 |
| Custom logic              | Extension data, custom fields, and outside-system identifiers have explicit handling decisions.         | Critical behavior exists outside standard data but is treated as routine transfer.         |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration pitfalls are preventable when the migration plan treats the platform as a rule-driven commerce environment rather than a destination for copied records. The most important risks concentrate around B2B account behavior, shared catalog visibility, scoped storefront meaning, complex catalog structure, staged commercial timing, inventory interpretation, URL continuity, and custom logic.

A strong launch decision requires more than imported data. It requires proof that representative buyers, products, catalogs, content, inventory states, routes, and integrations behave correctly under Adobe Commerce rules.

Plan your Adobe Commerce migration with Next-Cart to identify risk areas early, select the right service path, and validate the target store before launch.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do Adobe Commerce B2B migrations need extra pitfall planning?**

Adobe Commerce B2B stores can depend on company accounts, company users, shared catalogs, quote permissions, purchase orders, payment and shipping controls, and credit settings. These relationships can fail even when ordinary customer records are present, so B2B behavior needs targeted planning and validation.

**Are shared catalog problems usually data issues or configuration issues?**

They can be both. Product, customer, and price data must be available, but Adobe Commerce also needs the correct company, customer group, and shared catalog configuration. Storefront testing under different buyer contexts is the safest way to catch visibility and pricing errors.

**Should scheduled campaigns be included in an Adobe Commerce migration?**

Only when they are part of the approved migration scope and can be tested safely. Launch-state data and future scheduled changes should be separated so that current content does not overwrite planned campaigns and future campaigns do not appear too early.

**When should Custom Service be considered for Adobe Commerce pitfalls?**

Custom Service should be considered when required behavior depends on custom modules, unsupported extension data, external identifiers, Custom Platform behavior, ERP or PIM relationships, bespoke pricing rules, or transformations that cannot be handled as standard entity transfer or defined Add-ons.

**What is the most reliable way to catch Adobe Commerce migration pitfalls before launch?**

Use representative test cases that reflect the real business model: B2B companies, shared catalog segments, complex products, scoped storefronts, staged content, inventory exceptions, high-value URLs, and integration-dependent records. Static record counts are useful, but they do not prove Adobe Commerce behavior.
