# Selecting the Right Migration Approach for ShopWired

Choosing a ShopWired migration approach should be based on how the store must operate after launch. Record volume matters, but it should not be the only decision factor. A small source store can require careful handling if it depends on complex product options, B2B pricing, custom fields, integrations, or app-owned behavior. A larger store can still fit a simpler path when its data structures are supported and validation responsibility is clear.

The right approach should explain five things: what can migrate as supported records, what must be configured in ShopWired, what requires Add-ons, what should be reviewed as Custom Service, and what Demo Migration must prove before Full Migration. When these decisions are made early, ShopWired migration planning becomes a controlled scope decision rather than a late-stage troubleshooting exercise.

### What the Approach Decision Should Control <a href="#what-the-approach-decision-should-control" id="what-the-approach-decision-should-control"></a>

A ShopWired migration approach should control execution responsibility, support level, scope assumptions, configuration needs, and validation depth. It should not be selected only from convenience or record count.

| Decision area                  | What to evaluate                                                                                                        | Why it matters                                                                                  |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Supported data fit             | Products, categories, brands, customers, orders, reviews, coupons, CMS Pages, and other eligible records.               | Confirms whether ordinary migration scope is realistic.                                         |
| Catalog complexity             | Variations, choices, extras, bundles, digital products, pre-orders, subscriptions, stock, pricing, tax, and SEO fields. | Determines whether the catalog needs simple transfer, mapping, configuration, or custom review. |
| B2B and trade behavior         | Customer groups, trade accounts, pricing, restricted products, quotes, account terms, and checkout behavior.            | Decides whether target setup and special validation are needed.                                 |
| App and integration dependency | Apps, custom fields, API connections, webhooks, feeds, ERP, POS, accounting, CRM, fulfillment, and marketplaces.        | Identifies data that may not be standard store data.                                            |
| Launch ownership               | Who prepares, configures, reviews, performs available actions, and validates final results.                             | Prevents service-path confusion during Demo Migration and Full Migration.                       |

The practical approach is the lightest path that still protects the outcome. Choosing too little support can expose the merchant to preventable launch risk. Choosing too much support can slow the project without adding value.

### When Standard Service Can Be Enough <a href="#when-standard-service-can-be-enough" id="when-standard-service-can-be-enough"></a>

Standard Service can be appropriate when the migration is within supported scope and the merchant can confidently prepare, review, configure, and validate the target store. For ShopWired, this usually means the catalog structure is clear, product options do not require unusual transformation, customer identity is clean, historical orders are readable, and target checkout settings can be configured by the merchant.

| Standard Service fit signal                                                    | What it usually means                                                                                                                  |
| ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| Products use straightforward structures.                                       | Product names, descriptions, images, prices, stock, categories, brands, and SEO fields can be reviewed without special interpretation. |
| Variations are ordinary and within expected limits.                            | Option names, values, combinations, SKUs, stock, images, and prices can be validated from representative samples.                      |
| Customers are clean enough to review by email identity.                        | Duplicate, shared, or changed email scenarios are not central to operations.                                                           |
| Historical orders are needed for reference, not complex workflow continuation. | Payment, delivery, discount, refund, tax, and note fields can remain readable without advanced transformation.                         |
| Target setup is merchant-owned.                                                | Payments, delivery, tax, emails, theme, apps, and account settings can be configured separately by the merchant.                       |

Standard Service is not a low-quality path. It is the correct path when the scope is supported and the merchant can handle preparation and validation. It becomes risky only when unsupported behavior is treated as ordinary data or when the merchant expects Next-Cart to manage decisions outside the selected scope.

### When Managed Service Is the Safer Path <a href="#when-managed-service-is-the-safer-path" id="when-managed-service-is-the-safer-path"></a>

Managed Service is useful when the migration remains within supported capability but the merchant needs stronger operational coordination. It can help when the scope is not custom, but the business needs guidance around sample selection, timing, configuration dependencies, and result review.

| Managed Service signal                                                   | Why extra coordination helps                                                                             |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| Catalog records are supported but numerous or varied.                    | More structured review is needed to keep products, categories, brands, images, stock, and SEO aligned.   |
| B2B or trade behavior is important but mostly target-side configuration. | The merchant needs clearer separation between migrated customer data and configured trade behavior.      |
| Demo Migration must test several risk categories.                        | Sample selection and review need coordination across products, customers, orders, SEO, and integrations. |
| Launch timing is tight.                                                  | Migration action timing, source-store changes, and validation responsibilities must be controlled.       |
| The merchant has limited migration review capacity.                      | A guided process reduces the chance that issues are discovered late.                                     |

Managed Service should not be used to disguise unsupported requirements. If the store depends on app-owned data, custom transformations, non-standard product behavior, external identifiers, or Custom Platform analysis, the requirement should be scoped through Custom Service instead.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons are useful when the migration remains within supported capability but needs filtering, mapping, or configuration. They should not be treated as a catch-all for unsupported app data or bespoke transformation.

| Add-on need             | ShopWired example                                                                                                                              | Correct interpretation                                              |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Data Filter             | Migrate selected products, customers, orders, coupons, reviews, or CMS Pages based on date, status, category, or other supported criteria.     | The merchant wants eligible records narrowed before migration.      |
| Advanced Data Mapping   | Map supported source values to supported target values, such as customer groups, order statuses, product attributes, or other eligible fields. | The record is supported, but value interpretation needs control.    |
| Advanced Data Configure | Modify supported values before they reach ShopWired.                                                                                           | The transformation stays within supported configuration capability. |

For ShopWired, Add-ons are especially useful when the source store has mixed catalog quality, legacy categories, customer segments, order statuses, or field values that should not be moved exactly as-is. They are less appropriate when the issue is app-owned logic, external-system dependency, or unsupported product behavior.

### When Custom Service Should Be Reviewed <a href="#when-custom-service-should-be-reviewed" id="when-custom-service-should-be-reviewed"></a>

Custom Service should be reviewed when the migration depends on unsupported structures, app-owned data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment. It is not simply a more expensive version of ordinary migration. It is a review path for requirements that need direct analysis.

| Custom Service signal                                                                                     | Why standard handling may not be enough                                         |
| --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Product options do not fit ordinary variations, choices, extras, or supported configuration.              | The buying logic may need transformation or rebuild guidance.                   |
| Bundles, kits, subscriptions, pre-orders, or personalized products carry business-critical rules.         | Standard product records may not preserve the operational behavior.             |
| Customer, trade, or pricing rules depend on custom fields or external systems.                            | The data may need mapping, enrichment, or bespoke handling.                     |
| Orders contain external IDs, accounting references, fulfillment references, or marketplace workflow data. | Historical readability may depend on fields not handled as ordinary order data. |
| Apps create records or logic that the merchant expects to preserve.                                       | App-owned data is not automatically the same as platform-native data.           |
| A Custom Platform is involved.                                                                            | Data structures must be inspected before scope and mapping can be trusted.      |

Custom Service decisions should be example-led. The merchant should provide representative products, customer records, orders, app exports, custom fields, external identifiers, and expected output. Without examples, the discussion remains too abstract to decide scope reliably.

### How Demo Migration Should Decide the Path <a href="#how-demo-migration-should-decide-the-path" id="how-demo-migration-should-decide-the-path"></a>

Demo Migration should test whether the chosen approach is strong enough. It should not be evaluated only by whether a few records appear in ShopWired. It should answer whether the target store can represent the real business model.

| Demo Migration sample                            | Decision it should support                                                                                                        |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| Simple product                                   | Confirms baseline product, image, category, brand, price, stock, and SEO handling.                                                |
| Variation-heavy product                          | Confirms option names, option values, combinations, SKUs, stock, images, weight, GTIN, MPN, and tax behavior.                     |
| Product with choices, extras, or personalization | Shows whether the product can be configured, mapped, or needs Custom Service review.                                              |
| B2B or trade customer                            | Confirms customer identity, account expectations, pricing assumptions, and order history visibility.                              |
| Complex historical order                         | Confirms discounts, refunds, payment labels, delivery labels, taxes, notes, fulfillment, and external references remain readable. |
| Content or SEO page                              | Confirms CMS Pages, blog posts, metadata, menus, and redirect assumptions are realistic.                                          |
| App or integration-dependent record              | Shows whether external IDs, custom fields, API relationships, or app-owned data are in scope.                                     |

If Demo Migration exposes a mismatch, the correct response is to adjust scope before Full Migration. The selected path should change when evidence changes.

### Entity Points and Scope Planning <a href="#entity-points-and-scope-planning" id="entity-points-and-scope-planning"></a>

Entity Points help estimate eligible migration volume. They do not decide whether a ShopWired migration is simple or complex. Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path. New eligible records may consume Entity Points when migrated for the first time.

For ShopWired, Entity Points should be reviewed alongside structure and complexity.

| Scope signal     | What Entity Points help estimate                 | What they do not prove                                                                              |
| ---------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| Product count    | Potential eligible product volume.               | Whether variations, choices, extras, bundles, images, stock, tax, and SEO meaning fit.              |
| Customer count   | Potential eligible customer volume.              | Whether email identity, trade accounts, custom fields, and order relationships are clean.           |
| Order count      | Potential eligible order volume.                 | Whether payment, delivery, tax, refund, discount, note, and external-system context remains useful. |
| Blog Posts count | Potential eligible content volume when relevant. | Whether URLs, redirects, metadata, theme placement, and content presentation are launch-ready.      |

A store with few records can need Custom Service if its data is structurally unusual. A store with many records can use a supported path if the data is clean and validation is well prepared.

### Later Migration Actions and Launch Timing <a href="#later-migration-actions-and-launch-timing" id="later-migration-actions-and-launch-timing"></a>

A ShopWired migration plan should also define what happens when the source store continues changing after Demo Migration or after an initial Full Migration. The merchant may need to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration.

| Later action                                            | When it fits                                                                           | Validation requirement                                                                 |
| ------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | New eligible records have appeared and the previous configuration remains correct.     | Validate new products, customers, orders, content, and any changed totals or statuses. |
| Continue the Migration with a new configuration         | Filters, mapping, or configuration decisions need to change.                           | Validate the changed field behavior and affected record types, not only new records.   |
| Perform a new migration                                 | The target result should be replaced or the previous run is no longer the right basis. | Revalidate core catalog, customers, orders, SEO, settings, and launch timing.          |

The service path should clarify who performs the action and who validates the result. Under Standard Service and Custom Service without Expert Handle, the customer performs available migration actions and verifies the result. Under Managed Service and Custom Service with Expert Handle, Next-Cart can perform migration actions based on the customer’s request and agreed scope, while the customer remains responsible for final result verification and migration outcome.

### Choosing Between the Main Paths <a href="#choosing-between-the-main-paths" id="choosing-between-the-main-paths"></a>

The approach decision should be practical. It should protect the merchant from avoidable risk while avoiding unnecessary service weight. Use the following decision map as a final check.

| If the ShopWired migration looks like this                                                                      | Stronger path to consider                                              |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Supported records, clean catalog, ordinary customers, readable order history, and merchant-led setup.           | Standard Service.                                                      |
| Supported records but higher coordination pressure, launch timing pressure, or limited validation capacity.     | Managed Service.                                                       |
| Supported records need filtering, mapping, or supported value configuration.                                    | Add-ons.                                                               |
| Unsupported, custom, app-owned, external-system, Custom Platform, or bespoke transformation requirements exist. | Custom Service.                                                        |
| Scope is unclear because samples are weak.                                                                      | Strengthen Demo Migration samples before committing to Full Migration. |

A reliable choice can be summarized in four statements: which records will migrate, which ShopWired settings must be configured separately, which Add-ons or Custom Service requirements are in scope, and which sample results must pass before Full Migration.

### Signals That the Chosen Approach Is Too Light <a href="#signals-that-the-chosen-approach-is-too-light" id="signals-that-the-chosen-approach-is-too-light"></a>

A ShopWired migration approach is too light when it treats business logic as ordinary record movement. The warning signs usually appear in product options, B2B behavior, customer identity, app dependencies, external identifiers, or target setup.

| Warning signal                                                                | Likely response                                                                                          |
| ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Complex products were not included in Demo Migration.                         | Add variation, choices, extras, bundle, stock, tax, image, and SEO samples.                              |
| B2B rules are described generally but not sampled.                            | Provide trade customers, pricing examples, account terms, restricted products, and related orders.       |
| Custom fields are important but not classified.                               | Decide whether they are supported mapping, app-owned data, external references, or Custom Service scope. |
| Payment, delivery, and tax setup is assumed to come from order history.       | Separate historical readability from target configuration.                                               |
| API, webhook, feed, ERP, POS, or marketplace dependencies are not documented. | Build an integration map and review external ID needs.                                                   |
| Entity Points are used as the only scope measure.                             | Review data meaning and structural complexity alongside volume.                                          |

These signs should be handled before Full Migration. Launch is the wrong moment to discover that the chosen approach did not match the store’s operating model.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right ShopWired migration approach is the path that matches the store’s actual business structure. Standard Service may be enough for supported, merchant-led migrations. Managed Service is useful when coordination pressure is higher but the scope remains supported. Add-ons help when eligible records need filtering, mapping, or configuration. Custom Service is needed when unsupported, custom, app-owned, external-system, or bespoke transformation requirements affect the result.

A strong decision depends on evidence. The merchant should use preparation work and Demo Migration samples to prove product options, B2B behavior, customer identity, historical order readability, SEO continuity, app dependencies, Entity Points planning, and launch timing before committing to Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for a ShopWired migration?**

Standard Service may be enough when the migration stays within supported scope, product structures are clear, customer and order data are manageable, target settings can be configured by the merchant, and the merchant can validate results confidently.

**When should Managed Service be considered?**

Managed Service is useful when the scope remains supported but the merchant needs stronger coordination, sample review, execution support, timing control, or help managing validation across catalog, customers, orders, SEO, and integrations.

**How are Add-ons different from Custom Service?**

Add-ons adjust supported filtering, mapping, or configuration. Custom Service handles unsupported structures, app-owned data, custom fields, external identifiers, Custom Platform handling, bespoke transformation, or custom migration logic adjustment.

**Do Entity Points decide which ShopWired migration approach is right?**

No. Entity Points help plan eligible migration volume. The right approach also depends on product structure, B2B rules, customer identity, order readability, app dependencies, external systems, target setup, and Demo Migration evidence.
