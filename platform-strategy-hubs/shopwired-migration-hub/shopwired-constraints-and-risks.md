# ShopWired Constraints and Risks

ShopWired migration risk usually appears when a source store contains behavior that looks like simple data but actually depends on platform configuration, app logic, theme behavior, or external-system relationships. Products may migrate but lose option meaning. Customers may migrate but split order history across emails. Orders may migrate but not explain trade terms, custom fields, or fulfillment context. Content may migrate but lose search or navigation value. Apps and integrations may be visible in the source store but not transferable as ordinary records.

The purpose of risk review is not to make ShopWired look difficult. It is to separate what can be migrated, what must be configured in ShopWired, what should be rebuilt in the storefront, what requires Add-ons, and what needs Custom Service review. That separation helps merchants avoid assuming that a populated target store is the same as a launch-ready store.

### ShopWired Risk Review Framework <a href="#shopwired-risk-review-framework" id="shopwired-risk-review-framework"></a>

A strong ShopWired risk review follows the chain from assumption to consequence. The merchant should understand not only that a risk exists, but why it exists, how it affects operations, and what evidence proves it has been controlled.

| Risk area                  | Common assumption                                         | Practical consequence                                                                        | Mitigation direction                                                                                             |
| -------------------------- | --------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Hosted platform boundaries | Old storefront behavior can be copied directly            | Custom code, unsupported app data, or source-specific logic may not transfer                 | Classify each behavior as data, configuration, theme work, app setup, integration work, or Custom Service review |
| Product configuration      | All source options are equivalent to ShopWired variations | Price, stock, SKU, image, VAT, bundle, or personalization behavior may be misrepresented     | Sample complex products and choose the correct ShopWired structure                                               |
| B2B and trade logic        | Customer groups are ordinary customer records             | Pricing, approval, visibility, quote, payment, and tax behavior may be incomplete            | Build B2B samples and separate data from trade configuration                                                     |
| Historical orders          | Order transfer proves operational continuity              | Past orders may be readable while checkout, payment, delivery, and tax remain unconfigured   | Validate history separately from new-order testing                                                               |
| Content and SEO            | Pages and products are enough to preserve traffic         | URLs, redirects, metadata, menus, landing pages, and theme sections may be incomplete        | Prioritize high-value content and search paths                                                                   |
| Apps and integrations      | Connected workflows restart automatically                 | External IDs, webhooks, stock feeds, accounting, marketplace, or fulfillment links may break | Inventory dependencies and assign a handling path                                                                |

The safest planning stance is to treat each source behavior as unclassified until it is assigned to a clear handling path. If a behavior drives pricing, stock, visibility, tax, checkout, fulfillment, reporting, search, or B2B access, it deserves more than a field-level mapping decision.

### Hosted Platform and Custom Code Constraints <a href="#hosted-platform-and-custom-code-constraints" id="hosted-platform-and-custom-code-constraints"></a>

ShopWired is a hosted commerce platform. That gives merchants a managed environment with commerce, checkout, themes, apps, API access, and operational features, but it also creates boundaries. A source store may contain custom templates, server-side code, database tables, checkout scripts, plugins, modules, or direct database relationships that cannot be copied into ShopWired as they are.

This matters most when the source store’s business behavior depends on technical customization rather than ordinary commerce records. A custom pricing table, a bespoke product configurator, an external-stock script, a checkout-field rule, or a plugin-owned subscription process may appear to customers as normal storefront behavior. In migration planning, it must be reviewed as implementation logic.

| Source behavior                                 | ShopWired risk                                                          | Required review                                                                         |
| ----------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Custom code controlling product display         | Product may migrate without the rules that shaped the buying experience | Decide whether ShopWired configuration, theme work, an app, or Custom Service is needed |
| Direct database fields from a self-hosted store | Fields may not exist in supported ShopWired structures                  | Classify as mapped field, custom field, excluded data, or tailored transformation       |
| Checkout scripts or custom form fields          | Historical orders may not prove live checkout readiness                 | Separate order-history preservation from checkout configuration and testing             |
| Plugin or module records                        | Data may be stored outside ordinary product, customer, or order exports | Obtain app/plugin exports or escalate to Custom Service review                          |
| Custom workflows tied to external IDs           | Operational traceability may be lost                                    | Preserve reference IDs through mapping, custom fields, or integration planning          |

Mitigation begins with a customization inventory. The inventory should list what the old store did, where that behavior lived, who used it, and whether the expected ShopWired outcome is data migration, configuration, theme setup, integration work, Add-on scope, Custom Service review, or accepted exclusion.

### Product Variation, Choice, Extra, and Bundle Constraints <a href="#product-variation-choice-extra-and-bundle-constraints" id="product-variation-choice-extra-and-bundle-constraints"></a>

Product configuration is one of the highest-impact ShopWired risk areas. Source platforms often use different structures for variants, modifiers, add-ons, personalization, bundles, kits, downloadable products, subscription products, quote-only products, and product-specific delivery or tax behavior. These structures may not map one-to-one into ShopWired.

Risk increases when product choices affect price, SKU, stock, image, weight, GTIN, MPN, VAT, delivery, fulfillment, or customer instructions. It also increases when a source product uses more option complexity than the target structure can express safely, when options come from an app, or when a bundle or configurator calculates output dynamically.

| Warning sign                                      | Why it matters                                                       | Prevention action                                                   |
| ------------------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Product options affect stock or SKU               | Incorrect mapping can create wrong inventory or fulfillment behavior | Include variation-heavy products in Demo Migration samples          |
| Options add charges or upgrades                   | Basket and order totals may not explain the purchase correctly       | Decide whether choices, extras, apps, or custom handling are needed |
| Personalization fields collect text or files      | Customer instructions may disappear from operational views           | Validate order-admin, email, and fulfillment visibility             |
| Bundles reduce inventory across multiple products | A single product migration may not preserve relationship logic       | Review bundle/app behavior before treating the product as standard  |
| Options control VAT, weight, or delivery          | Tax and fulfillment outcomes may be wrong                            | Test products with special VAT, weight, and delivery implications   |

Mitigation should use realistic product sampling. A Demo Migration that includes only simple products can pass while hiding the most important ShopWired translation risks. The sample set should include the products that are hardest to sell correctly, not only the products that are easiest to migrate.

### Category, Brand, Filter, and Discovery Constraints <a href="#category-brand-filter-and-discovery-constraints" id="category-brand-filter-and-discovery-constraints"></a>

Migrating product records does not prove that customers can find products in ShopWired. Discovery may depend on categories, brands, filters, menus, internal search, product visibility, featured areas, product sorting, SEO landing pages, and manually curated navigation.

Risk increases when the source store uses deep category trees, products in multiple categories, brand-led browsing, filter-heavy selection, product specifications, category pages with organic traffic, or customer-group visibility. The danger is not only missing data; it is a store that contains the right products but makes them harder to discover.

| Discovery element      | Failure mode                                                | Validation signal                                                          |
| ---------------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------- |
| Categories             | Products land in unexpected hierarchy or weak landing pages | Priority products can be found through expected category paths             |
| Brands                 | Manufacturer or label browsing loses value                  | Brand pages or filters support the expected product discovery journey      |
| Filters/specifications | Customers cannot narrow technical products properly         | High-value filters work on representative catalog samples                  |
| Menus                  | Navigation does not reflect selling priorities              | Main and footer menus lead to important product/category/page destinations |
| Search                 | Internal search returns weaker or incomplete results        | Test common product, SKU, brand, and compatibility queries                 |
| Visibility rules       | Retail or trade users see the wrong products                | Review public, logged-in, and trade-customer scenarios                     |

Mitigation should include storefront discovery checks, not only product-admin checks. The merchant should test the product paths customers actually use: category browsing, brand browsing, search queries, menu links, landing pages, and priority product filters.

### B2B, Trade, Quote, and Customer-Group Constraints <a href="#b2b-trade-quote-and-customer-group-constraints" id="b2b-trade-quote-and-customer-group-constraints"></a>

ShopWired may be a strong option for merchants with trade or B2B needs, but B2B migration is rarely just customer migration. Trade customers, pricing bands, individual trade prices, global discounts, quote records, account approval, product/category visibility, delivery access, offline payment, account terms, and tax treatment can all carry business logic.

Risk increases when the source store uses customer groups to control commercial outcomes. A group label may look simple in the database, but the business may use it to determine whether a customer can buy certain products, receive special pricing, request quotes, use purchase orders, access delivery methods, or receive tax treatment.

| B2B constraint                                          | Consequence if missed                                                               | Mitigation                                                                  |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Trade accounts handled separately from retail customers | Trade users may lose expected access or pricing                                     | Build separate trade-customer samples and review approval/account status    |
| Pricing bands or customer-specific pricing              | Customers may see incorrect prices                                                  | Compare source and ShopWired pricing examples across customer types         |
| Quote workflows                                         | Sales teams may lose negotiation context                                            | Validate quote history, notes, statuses, and follow-up process expectations |
| Trade-only products or categories                       | Public users may see restricted products, or trade users may miss required products | Test public, logged-in retail, and trade-customer visibility                |
| Offline payment or account terms                        | Checkout may not support expected B2B payment behavior                              | Configure and test payment options separately from order migration          |
| B2B tax treatment                                       | Tax/VAT output may be inaccurate                                                    | Review tax settings, customer type, product type, and regional rules        |

Mitigation requires B2B-specific evidence. Retail product and customer samples cannot prove trade readiness. A trade-focused migration should validate customers, products, pricing, quotes, orders, payment access, tax behavior, and visibility rules through realistic examples.

### Order, Quote, Subscription, and Historical Context Constraints <a href="#order-quote-subscription-and-historical-context-constraints" id="order-quote-subscription-and-historical-context-constraints"></a>

Historical orders are valuable because they support service, customer account history, reporting, reconciliation, compliance, and operational continuity. They are also a common source of false confidence. Migrated orders may preserve past context but do not recreate checkout settings, delivery rates, payment gateways, taxes, quote workflows, or subscription behavior for future purchases.

Risk increases when orders include custom statuses, special instructions, customer-specific pricing, refunds, returns, partial fulfillment, quotes, subscription context, delivery exceptions, payment references, external IDs, or custom fields. These details may be essential for customer service even if they are not used for new checkout processing.

| Order condition                     | Risk                                                      | Review method                                                          |
| ----------------------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------- |
| Custom order statuses               | Operational state may become unclear                      | Map status meaning and validate examples with service/operations users |
| Quotes or quote-derived orders      | Negotiation history may be incomplete                     | Sample quote records, notes, totals, and converted orders              |
| Subscriptions or recurring behavior | Historical record may not equal active subscription logic | Identify app/configuration requirements separately                     |
| Refunds, cancellations, returns     | Financial history may be hard to interpret                | Validate totals, notes, labels, and adjustment visibility              |
| Custom fields or instructions       | Fulfillment details may be lost                           | Check order-admin views and downstream fulfillment needs               |
| External IDs                        | Accounting, ERP, or warehouse traceability may break      | Preserve mapping fields or external-reference records where required   |

Mitigation should separate two questions: can old orders be understood, and can new orders be processed correctly? Both are important, but they are different proof requirements.

### Checkout, Delivery, Payment, VAT, and Sales Tax Constraints <a href="#checkout-delivery-payment-vat-and-sales-tax-constraints" id="checkout-delivery-payment-vat-and-sales-tax-constraints"></a>

Checkout-related risk appears when merchants expect historical order labels to configure future checkout behavior. ShopWired checkout readiness depends on target setup: payment gateways, offline payment, delivery zones, delivery rates, delivery restrictions, collection options, checkout settings, VAT features, VAT zones, custom VAT rates, US sales tax settings, trade rules, and relevant checkout apps.

Source checkout data can help preserve history, but it does not configure new behavior. A migrated order may show that a customer previously used a delivery method or paid through a gateway, but future checkout still needs working payment credentials, delivery rules, tax settings, and testing.

| Setup area               | Common risk                                                    | Pass condition                                                                         |
| ------------------------ | -------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Payment methods          | Historical labels exist but live gateways are not configured   | Test successful, failed, refund, and offline-payment scenarios where relevant          |
| Delivery rates and zones | Old delivery names do not recreate target delivery logic       | Test zones, rates, product weights, order values, customer groups, and exclusions      |
| VAT and sales tax        | Old tax values are readable but future rules are incorrect     | Validate representative products, regions, B2B customers, delivery tax, and exemptions |
| Checkout fields          | Custom source fields are not captured in target order views    | Confirm where fields appear in admin, emails, and fulfillment workflows                |
| Trade checkout           | B2B customers cannot use expected payment or delivery behavior | Test logged-in trade accounts with realistic baskets                                   |
| Checkout apps            | Source app behavior is missing                                 | Reconfigure, replace, rebuild, exclude, or escalate before launch                      |

Mitigation should include full checkout testing after configuration. Product, customer, and order migration can be technically correct while checkout is still not launch-ready.

### App, API, Webhook, and Integration Constraints <a href="#app-api-webhook-and-integration-constraints" id="app-api-webhook-and-integration-constraints"></a>

ShopWired supports apps, API access, webhooks, product feeds, stock tools, accounting integrations, fulfillment services, marketing tools, and other connected workflows. The risk is assuming that source app data and integrations automatically transfer because similar capabilities exist in ShopWired.

Apps and external systems often own data outside ordinary store records. A subscription app may own subscription state. A feed app may own channel-specific product data. An ERP may own stock authority. A fulfillment platform may rely on source order IDs. A marketing system may store segmentation data outside the store. API and webhook workflows may need authentication, pagination handling, rate-limit planning, error handling, and fresh endpoint configuration.

| Dependency                   | Risk if assumed standard                                     | Handling path                                                       |
| ---------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------- |
| App-owned product data       | Product display or purchasing logic may be incomplete        | App export, Add-on review, manual rebuild, or Custom Service review |
| Accounting or ERP references | Reconciliation may break after launch                        | Preserve IDs, mapping files, custom fields, or integration logic    |
| Stock synchronization        | Stock authority may conflict between systems                 | Decide which system owns stock and test update direction            |
| Fulfillment automation       | Orders may not route correctly                               | Rebuild webhook/API process and validate representative orders      |
| Marketplace feeds            | Channel-specific listings may be weaker than source listings | Review feed fields, category mapping, images, variants, and pricing |
| Email and marketing tools    | Subscriber or segment logic may be incomplete                | Export, map, reconfigure, or accept exclusions intentionally        |

Mitigation requires an integration inventory before launch planning is treated as stable. Every connected workflow should have one of five outcomes: reconfigure, map, rebuild, exclude, or escalate to Custom Service review.

### Theme, Content, SEO, and Storefront Presentation Constraints <a href="#theme-content-seo-and-storefront-presentation-constraints" id="theme-content-seo-and-storefront-presentation-constraints"></a>

ShopWired migration can preserve valuable content data, but storefront presentation depends on theme setup, template areas, menus, images, content blocks, SEO settings, redirects, canonical behavior, breadcrumbs, and manually curated page structure. A source store may have important sales content embedded in templates, banners, product tabs, landing pages, or custom page modules.

Risk increases when organic traffic matters, when source URLs have backlinks, when category and brand pages rank, when product descriptions are highly structured, when B2B onboarding pages support sales, or when menus and landing pages guide customers through complex catalogs.

| Asset type                     | Risk                                                    | Prevention                                                                    |
| ------------------------------ | ------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Product/category URLs          | Ranking signals and customer bookmarks may be disrupted | Build a priority URL and redirect list before launch                          |
| Metadata and SEO tags          | Search snippets and page relevance may weaken           | Validate priority product, category, brand, page, and blog metadata           |
| Landing pages                  | High-value commercial pages may be missed               | Classify pages by traffic, revenue, B2B role, or trust importance             |
| Menus and links                | Customers cannot find migrated content                  | Test main menu, footer, category links, internal links, and landing-page CTAs |
| Theme-controlled sales content | Important content may not be in ordinary data records   | Identify what must be rebuilt in the ShopWired theme or content areas         |
| Images and media               | Product or page context may degrade                     | Validate image assignment, ordering, alt context, and page display            |

Mitigation should prioritize business-critical content rather than trying to recreate every old visual detail. The right goal is continuity of discovery, trust, search visibility, and conversion support, not automatic duplication of the old storefront.

### When Constraints Require Add-ons or Custom Service Review <a href="#when-constraints-require-add-ons-or-custom-service-review" id="when-constraints-require-add-ons-or-custom-service-review"></a>

Not every constraint requires Custom Service. Some needs are handled through ShopWired configuration, theme setup, existing apps, or bounded Add-ons. Custom Service review becomes important when the migration outcome depends on unsupported source data, custom fields, app-owned records, external identifiers, bespoke transformation, or tailored migration behavior.

| Requirement                                             | Likely direction                              | Decision signal                                                                       |
| ------------------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------------------------------- |
| Supported field mapping or filtering                    | Add-on review                                 | The output is bounded and fits a supported migration enhancement                      |
| Complex attribute or custom-field handling              | Add-on or Custom Service review               | Decide whether values are standard fields, custom fields, or custom transformation    |
| Source app data                                         | Custom Service review                         | The data may not exist in ordinary product, customer, or order exports                |
| External-system ID preservation                         | Custom Service review or mapping deliverable  | Operational continuity depends on traceability                                        |
| Custom B2B pricing, quote, or account logic             | Custom Service review                         | The requirement is business logic, not just customer data                             |
| Custom checkout, tax, delivery, or fulfillment behavior | Custom Service review or target configuration | The behavior must be recreated, configured, or tested outside ordinary data migration |

A clear scope decision prevents two planning errors: underestimating the work by calling everything standard data, or overcomplicating the project by treating every non-basic request as custom development. Each constraint should be classified by evidence.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired migration constraints are manageable when they are identified as operating assumptions, not late-stage surprises. The most important risk areas are hosted-platform boundaries, product configuration, B2B and trade logic, historical order meaning, checkout setup, content and SEO continuity, apps, API workflows, integrations, and custom data.

Before Full Migration, the merchant should have representative samples, a customization inventory, a product-configuration review, B2B and order-history examples, a checkout configuration plan, a content and URL priority list, and an integration handling map. If standard migration scope cannot preserve the required business meaning, the issue should be resolved through configuration, Add-ons, Custom Service review, or an explicit exclusion before launch planning continues.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the biggest constraint when migrating to ShopWired?**

The biggest constraint is assuming source-store behavior can be copied directly into ShopWired. Product options, B2B rules, checkout behavior, custom fields, apps, integrations, and theme-controlled content must fit supported structures or be reviewed separately.

**Can complex product options create ShopWired migration risk?**

Yes. Options that affect SKU, price, stock, image, VAT, delivery, fulfillment, bundles, personalization, or app behavior can create risk if they are mapped as simple text fields or ordinary variants without review.

**Are B2B customers migrated the same way as retail customers?**

Not always. B2B migration may involve trade accounts, pricing bands, customer-specific prices, quotes, product visibility, account terms, payment methods, and tax behavior. These areas may need configuration or Custom Service review.

**Do migrated orders prove that ShopWired checkout is ready?**

No. Migrated orders can preserve historical checkout context, but live checkout depends on payment gateways, delivery zones and rates, VAT or sales tax setup, customer-group rules, trade behavior, and app configuration.

**When should ShopWired constraints be escalated to Custom Service review?**

Escalate when the required outcome depends on unsupported custom fields, app-owned records, external identifiers, custom product transformation, B2B or quote logic, custom checkout behavior, or tailored migration behavior beyond standard scope.
