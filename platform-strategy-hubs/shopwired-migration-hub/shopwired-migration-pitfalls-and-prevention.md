# ShopWired Migration Pitfalls and Prevention

ShopWired migration pitfalls usually appear when a project treats ShopWired as a simple destination for products, customers, and orders. That view misses the areas that give a ShopWired store its operational meaning: product variations, choices, extras, bundles, trade customers, customer fields, delivery rules, VAT/tax configuration, checkout behavior, apps, API connections, webhooks, and content/SEO paths.

A reliable migration plan should identify these risks before Full Migration and then validate them with representative records. The goal is not to make the project heavier than necessary. The goal is to prevent a store from passing record-count checks while failing customer experience, B2B workflow, operational readability, or launch readiness.

### Pitfall 1: Treating ShopWired as a Simple Product Import Destination <a href="#pitfall-1-treating-shopwired-as-a-simple-product-import-destination" id="pitfall-1-treating-shopwired-as-a-simple-product-import-destination"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The migration scope focuses on products, customers, and orders, but the team does not define how ShopWired should represent the store’s selling model. Products arrive in the admin area, yet the target store may not reflect choices, extras, bundles, stock-sensitive options, trade pricing, delivery rules, VAT treatment, custom fields, or app-supported workflows.

This creates a misleading pass. The store looks populated, but the commercial structure behind the data is not ready for review or launch.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Signal                                                    | Risk                                                                            |
| --------------------------------------------------------- | ------------------------------------------------------------------------------- |
| The project scope only lists basic entities.              | Platform-specific behavior may be ignored.                                      |
| Product choice behavior is reviewed late.                 | Selling logic may be lost after products appear.                                |
| B2B or trade behavior is described only as customer data. | Pricing, account rules, and checkout restrictions may be missed.                |
| Apps and external systems are not inventoried.            | App-owned records or integration-sensitive IDs may be excluded unintentionally. |

#### Prevention <a href="#prevention" id="prevention"></a>

Define the ShopWired migration thesis before accepting the scope. Decide which parts of the source store are data migration, which are target setup, which require Add-ons, which require Custom Service, and which are manual or third-party work.

A useful prevention step is to classify the store’s complexity across product structure, customer structure, checkout behavior, content, SEO, apps, and integrations before Demo Migration. That classification should influence the sample set.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

Before Demo Migration, create a risk sample that includes one simple product, one product with variations, one product with choices or extras, one trade customer, one discounted order, one important category, one SEO-sensitive URL, and one integration-sensitive record.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The project scope reflects ShopWired’s actual operating model, and platform-specific behavior has a defined handling path instead of being discovered only after records are migrated.

### Pitfall 2: Flattening Product Variations, Choices, Extras, or Bundles <a href="#pitfall-2-flattening-product-variations-choices-extras-or-bundles" id="pitfall-2-flattening-product-variations-choices-extras-or-bundles"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Products migrate as visible records, but the customer-facing buying flow loses meaning. A source option that controlled price, stock, image, weight, VAT, delivery, personalization, or fulfillment may become plain text. Bundles, kits, extras, product choices, or digital-product assumptions may appear as descriptions instead of functioning as purchase decisions.

The problem is not only cosmetic. If customers cannot select the intended option or if staff cannot fulfill the order correctly, the product has not truly passed migration validation.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Signal                                                                          | Risk                                                       |
| ------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Source options affect price, stock, image, SKU, tax, or delivery.               | Standard field mapping may not preserve selling behavior.  |
| Products use personalization, file upload, engraving, or customer-input fields. | Customer input may be lost or pushed into the wrong place. |
| Bundles, kits, grouped products, or product extras are used.                    | Add-on or custom handling may be needed.                   |
| Demo Migration samples include only simple products.                            | Product-choice risk remains hidden.                        |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Build a product-choice sample set before migration review. Confirm whether each source behavior should become ShopWired variations, choices, extras, bundles, app-supported behavior, Custom Service scope, manual rebuild, or accepted exclusion.

| Product behavior | Preferred review question                                                          | Handling decision                                                      |
| ---------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Variations       | Do option combinations preserve SKU, stock, price, image, weight, and VAT meaning? | Standard mapping, Add-on adjustment, or Custom Service review.         |
| Choices          | Does the shopper selection still work at purchase time?                            | Target configuration, supported migration handling, or manual rebuild. |
| Extras           | Are optional charges or add-ons represented clearly?                               | App/setup review, Add-on handling, or Custom Service scope.            |
| Personalization  | Can customers still provide required instructions?                                 | Target setting, app support, manual rebuild, or custom handling.       |
| Bundles and kits | Does the product still represent the intended grouped purchase?                    | App support, manual configuration, or Custom Service review.           |

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

Include a configurable apparel product, a product with optional extras, a personalized product, a bundle, and a stock-sensitive product in Demo Migration review. Validate each one from the storefront and the admin area.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative products remain sellable, and the customer-facing choice behavior supports the intended pricing, stock, image, fulfillment, and order-context meaning.

### Pitfall 3: Validating Products Without Validating Discovery <a href="#pitfall-3-validating-products-without-validating-discovery" id="pitfall-3-validating-products-without-validating-discovery"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Products exist in ShopWired, but customers cannot find them through the expected routes. Categories, subcategories, brands, search terms, filters, menus, featured sections, and high-value landing pages may not support the old customer journey or the intended target structure.

This pitfall often appears when product validation happens entirely in the admin area. Admin presence proves the product exists. It does not prove that the storefront supports discovery.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Signal                                                  | Risk                                                                 |
| ------------------------------------------------------- | -------------------------------------------------------------------- |
| Products belong to several categories.                  | Category placement may be incomplete or commercially weak.           |
| Brand-led browsing drives sales.                        | Products may be present but missing from brand paths.                |
| Filters or specifications influence purchase decisions. | Customers may struggle to narrow the catalog.                        |
| Menus or landing pages are curated manually.            | Customer-entry paths may not be recreated by entity migration alone. |
| Search behavior is important.                           | Product names and SKUs may not surface as expected.                  |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Validate discovery from the storefront. Use product samples across top categories, deep subcategories, brands, filters, search terms, featured products, and important landing pages. Separate category data from storefront navigation and content presentation.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

Review one top category, one deep subcategory, one brand page, one filter-heavy group, one SKU search, one product-name search, one homepage product area, and one SEO-sensitive landing page before accepting product validation.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Representative products can be found through the customer-facing paths that matter to sales, search, support, and merchandising.

### Pitfall 4: Treating B2B and Trade Customers as Ordinary Customers <a href="#pitfall-4-treating-b2b-and-trade-customers-as-ordinary-customers" id="pitfall-4-treating-b2b-and-trade-customers-as-ordinary-customers"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Customer records migrate, but B2B or trade behavior becomes incomplete. A trade customer may still exist by name and email, while pricing, account terms, approval status, customer-group logic, product visibility, payment access, delivery rules, tax handling, quotes, or account-specific fields are not configured or migrated.

This risk is especially important because B2B continuity depends on both data and rules. Migrating a customer record does not automatically recreate the commercial arrangement attached to that customer.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Signal                                                        | Risk                                                               |
| ------------------------------------------------------------- | ------------------------------------------------------------------ |
| The source store has wholesale, trade, or approved customers. | Customer migration may preserve identity but not trading behavior. |
| Customer groups affect pricing, product access, or checkout.  | Group labels alone may not preserve business rules.                |
| Quotes, account terms, or negotiated pricing are used.        | Workflow continuity may require configuration or custom handling.  |
| Custom customer fields carry account information.             | Staff may lose important account context.                          |
| Trade customers use different delivery or payment rules.      | Live checkout may fail even if accounts migrate.                   |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Separate customer identity from B2B behavior. Validate standard customers, guest buyers, customer groups, trade customers, quote-related customers, and customers with custom fields or external references. Decide which B2B rules are target configuration, migration scope, app behavior, manual setup, or Custom Service scope.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Use a validation table for trade accounts before Full Migration:

| Account area               | Required decision                                           |
| -------------------------- | ----------------------------------------------------------- |
| Customer identity          | Migrated as customer data.                                  |
| Trade status               | Configured, migrated where supported, or manually assigned. |
| Pricing                    | Target setup, Add-on handling, or Custom Service review.    |
| Quotes/account terms       | Rebuilt, excluded, app-supported, or custom scoped.         |
| Tax/payment/delivery rules | Configured and tested separately in ShopWired.              |

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Trade customer records remain interpretable, and account-specific commercial behavior is configured, migrated, rebuilt, excluded, or escalated intentionally.

### Pitfall 5: Approving Orders Without Operational Readability <a href="#pitfall-5-approving-orders-without-operational-readability" id="pitfall-5-approving-orders-without-operational-readability"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Orders migrate into ShopWired, but the history is not useful for the teams that need it. Payment labels, delivery labels, tax values, voucher context, refunds, partial fulfillment, quote references, customer notes, admin notes, external IDs, subscription context, or trade-account meaning may be incomplete or unclear.

Order validation fails when the record exists but cannot answer real post-migration questions: What did the customer buy? Was it paid? Was it fulfilled? Was there a refund? Which customer account was involved? Which delivery method was used? Was this a trade order? Which external system reference matters?

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Signal                                                                      | Risk                                           |
| --------------------------------------------------------------------------- | ---------------------------------------------- |
| Reviewers check only order count, date, and total.                          | Operational context may be missing.            |
| The source store uses custom order statuses or notes.                       | Staff may lose service or fulfillment context. |
| Orders include refunds, partial fulfillment, quotes, or manual adjustments. | Exception history may become unreadable.       |
| External systems depend on order or customer IDs.                           | Reconciliation may break after migration.      |
| B2B orders use special prices, tax, or delivery rules.                      | Historical order meaning may be incomplete.    |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate varied order samples with the teams that use them. Include customer service, finance, fulfillment, and operations users in the review when possible. Classify each order issue as migration correction, target setup, app/integration work, Custom Service review, manual cleanup, or accepted limitation.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Select at least one ordinary paid order, refunded order, canceled order, partially fulfilled order, discounted order, trade order, quote-related order, note-heavy order, and externally referenced order for review.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Historical orders preserve enough context for customer service, finance, fulfillment, and management to use the records without routine dependence on the source platform.

### Pitfall 6: Confusing Historical Checkout Data With Live Checkout Readiness <a href="#pitfall-6-confusing-historical-checkout-data-with-live-checkout-readiness" id="pitfall-6-confusing-historical-checkout-data-with-live-checkout-readiness"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Migrated orders contain payment, delivery, discount, and tax information, so the team assumes the target checkout is ready. In reality, live checkout depends on ShopWired payment methods, delivery zones and rates, collection rules, VAT/tax settings, offers, customer-group behavior, trade pricing, checkout apps, and target configuration.

Historical data can be readable while live checkout is still incomplete. Treating one as proof of the other creates launch risk.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Signal                                                                      | Risk                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------- |
| Payment labels appear in old orders but gateways are not tested.            | New customers may be unable to pay.                 |
| Delivery labels appear in history but delivery rates are not configured.    | New orders may calculate the wrong delivery cost.   |
| Tax values are visible in old orders but VAT/tax settings are not reviewed. | New orders may calculate incorrectly.               |
| Trade customers need different checkout access.                             | Account-specific checkout rules may fail at launch. |
| Custom checkout fields existed in the source store.                         | Required customer input may be missing.             |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Create two separate validation tracks: historical order readability and live checkout readiness. Do not approve checkout based on migrated history. Run target checkout tests across realistic customer types, delivery zones, payment methods, discounts, tax scenarios, and trade/account scenarios.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

After migrated orders are approved, place test orders as a standard retail customer and a trade customer. Test payment, delivery rate selection, VAT/tax behavior, voucher or offer behavior, order confirmation, and the resulting order record.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Historical checkout context is readable, and live ShopWired checkout behavior is configured and tested separately for the target selling model.

### Pitfall 7: Assuming Apps, API Connections, and Webhooks Will Resume Automatically <a href="#pitfall-7-assuming-apps-api-connections-and-webhooks-will-resume-automatically" id="pitfall-7-assuming-apps-api-connections-and-webhooks-will-resume-automatically"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The migration moves standard data, but connected workflows break. Apps, API integrations, webhooks, marketplace feeds, stock sync, accounting, CRM, fulfillment, POS, email marketing, reporting, or custom-field workflows may depend on IDs, fields, triggers, credentials, mappings, or target configuration that the migration does not automatically recreate.

This pitfall is common when integration ownership is unclear. A merchant may expect connected services to work immediately because the main data is present, while each integration still needs setup and testing.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Signal                                                                     | Risk                                                        |
| -------------------------------------------------------------------------- | ----------------------------------------------------------- |
| External systems depend on product, customer, order, or stock IDs.         | ID continuity may not be preserved without custom planning. |
| Webhooks trigger fulfillment, accounting, CRM, or email workflows.         | Automation may not fire after target setup.                 |
| App-owned records affect products, checkout, B2B, subscriptions, or forms. | Standard migration scope may not include required data.     |
| Marketplace or feed fields differ from ordinary product fields.            | Channel output may become incomplete.                       |
| API credentials and ownership are not assigned.                            | Reconnection work may be delayed until launch.              |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Build an integration inventory before Full Migration. For each connected system, document the data it owns, the records it reads, the IDs it depends on, the target setup owner, and the validation action needed after migration.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

Use this integration review format:

| Connected system | Data dependency                                       | Handling path                          | Validation proof                                  |
| ---------------- | ----------------------------------------------------- | -------------------------------------- | ------------------------------------------------- |
| Accounting       | Orders, tax, refunds, customer IDs.                   | Reconnect and reconcile sample orders. | Export or sync test confirms readable records.    |
| Fulfillment      | Products, SKUs, stock, delivery method, order status. | Map SKUs and test order flow.          | Test order reaches fulfillment workflow.          |
| CRM/email        | Customers, consent, groups, custom fields.            | Reconnect and map fields.              | Sample customer appears with usable context.      |
| Marketplace/feed | Product identifiers, attributes, categories, stock.   | Validate feed output.                  | Sample products publish with required attributes. |

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Connected-system expectations are explicit, and app-owned or integration-sensitive data is not mistaken for ordinary migrated platform data.

### Pitfall 8: Leaving SEO, Content, and Theme-Dependent Areas Until Launch <a href="#pitfall-8-leaving-seo-content-and-theme-dependent-areas-until-launch" id="pitfall-8-leaving-seo-content-and-theme-dependent-areas-until-launch"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Products, customers, and orders migrate, but important customer-entry paths are incomplete. CMS Pages, Blog Posts, menus, banners, landing pages, product blocks, category content, brand content, metadata, redirects, images, file assets, and theme-controlled areas may not be included in the acceptance review.

The store may function technically but feel incomplete to customers or lose important organic, referral, campaign, or support traffic.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Signal                                                       | Risk                                                  |
| ------------------------------------------------------------ | ----------------------------------------------------- |
| Organic search traffic is important.                         | URL and metadata issues may affect discovery.         |
| Category, brand, CMS, or blog pages rank or receive traffic. | Non-product pages may be missed.                      |
| Menus and landing pages guide customer journeys.             | Products may be present but journeys are broken.      |
| Theme sections contain sales, trust, or B2B content.         | Data migration may not recreate presentation content. |
| Redirect planning starts after product approval.             | High-value paths may be handled too late.             |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Prepare a priority content and URL list before validation. Separate what should migrate as data from what should be rebuilt as theme/content work. Validate high-value paths, not every historical URL with equal effort.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

Prioritize product URLs, category URLs, brand pages, policy pages, delivery pages, B2B information pages, contact pages, landing pages, Blog Posts, campaign URLs, menu links, and metadata for the first validation pass.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Important content and SEO paths are migrated, redirected, rebuilt, or formally accepted as outside scope before launch.

### Pitfall 9: Treating Additional Migration Options as a Substitute for Review <a href="#pitfall-9-treating-additional-migration-options-as-a-substitute-for-review" id="pitfall-9-treating-additional-migration-options-as-a-substitute-for-review"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

The team uses Additional Migration Options and assumes the result no longer needs careful validation. Options that clear, preserve, map, or adapt data can be useful, but they change the target result and should be reviewed with the same seriousness as any other scope decision.

The risk is not the option itself. The risk is using an option without defining what the target result should look like.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

| Signal                                                            | Risk                                                                 |
| ----------------------------------------------------------------- | -------------------------------------------------------------------- |
| An option is selected because it sounds generally useful.         | The expected target effect may be unclear.                           |
| Target data already exists before migration.                      | Clearing or preserving behavior may affect acceptance.               |
| Redirects, IDs, images, or order numbers are sensitive.           | The option may have downstream SEO or operational effects.           |
| The team does not update validation after changing configuration. | The final result may differ from the reviewed Demo Migration result. |

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Use Additional Migration Options only with a defined reason and validation plan. Document what the option should change, which records it affects, and how the target result will be checked.

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

If an option affects target data cleanup, URL handling, order-number behavior, or media handling, add specific validation samples for the affected products, orders, pages, redirects, and target records.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Each selected option has a defined purpose, a relevant validation sample, and an accepted target outcome.

### Pitfall 10: Revalidating Later Migration Runs Too Lightly <a href="#pitfall-10-revalidating-later-migration-runs-too-lightly" id="pitfall-10-revalidating-later-migration-runs-too-lightly"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

After the main migration, the store continues to change. New products, customers, orders, categories, content, or configuration changes may be migrated later, but the team assumes the earlier validation pass still covers the changed scope.

Later runs can introduce new defects if source data changes, target setup changes, mapping changes, or a different configuration is used.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

| Signal                                                                 | Risk                                                            |
| ---------------------------------------------------------------------- | --------------------------------------------------------------- |
| The team says to continue the migration without defining what changed. | New data may be accepted without proof.                         |
| Mapping or filtering changes after Demo Migration.                     | The target outcome may differ from the earlier reviewed result. |
| Product or customer structures change during the launch window.        | New complexity may not be represented in the original sample.   |
| Entity Points are not reviewed for repeated paid execution.            | The project may underestimate cost or consumption impact.       |

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Define the later migration action clearly. If the project continues with the last used configuration, validate the new records and changed operational areas. If the project continues with a new configuration or performs a new migration, revalidate the changed mapping, filtering, and target handling with representative samples.

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

Before a later migration run, record what changed in the source store, what changed in target setup, whether mapping changed, whether filters changed, whether Entity Points may be consumed again, and which samples must be rechecked.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Later migration activity is reviewed according to its actual scope, and changed data or configuration is not accepted merely because the earlier migration pass looked correct.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired migration pitfalls are usually caused by accepting surface-level completion too early. Products, customers, and orders may be present while the store still has unresolved issues in product-choice behavior, B2B rules, order readability, checkout setup, integrations, SEO, content, Additional Migration Options, or later migration runs.

The best prevention strategy is not a longer checklist for its own sake. It is a sharper acceptance model: representative samples, storefront checks, admin review, integration ownership, live checkout testing, and explicit pass conditions. When every important area has a handling path, ShopWired migration review becomes a launch-readiness process rather than a record-count exercise.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the most common ShopWired migration pitfall?**

The most common pitfall is approving migrated records without checking whether the store’s selling behavior still works. Product variations, choices, extras, trade behavior, checkout rules, apps, and SEO paths often require deeper validation than simple count matching.

**Why do product variations and choices need special attention?**

They can affect price, stock, SKU, image, weight, VAT, fulfillment, personalization, and customer selection. If those meanings are flattened or placed in the wrong structure, the product may exist but no longer sell correctly.

**Should B2B and trade customers be validated separately?**

Yes. Trade customers should be reviewed for account identity and commercial behavior. Pricing, payment terms, delivery rules, visibility, quotes, tax behavior, and custom fields may require target setup, app support, Add-ons, or Custom Service.

**Can migrated historical orders prove that live checkout is ready?**

No. Historical orders prove readability of past transactions. Live checkout readiness requires separate tests for payment methods, delivery rates, VAT/tax behavior, offers, customer groups, trade accounts, and checkout-related apps.

**How should apps and integrations be handled during ShopWired migration?**

They should be inventoried and assigned handling paths. App-owned records, API-dependent IDs, webhooks, marketplace fields, stock sync, accounting, CRM, fulfillment, and reporting workflows may require setup, mapping, testing, or Custom Service review.

**Do later migration runs need fresh validation?**

Yes. Continuing the migration or performing a new migration can introduce new records, changed mappings, or different target behavior. The changed scope should be sampled and validated before acceptance.
