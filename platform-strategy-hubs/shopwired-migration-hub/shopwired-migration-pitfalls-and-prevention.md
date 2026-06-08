# ShopWired Migration Pitfalls and Prevention

ShopWired migration problems usually appear when source-store behavior is treated as ordinary data even though it depends on product choices, B2B rules, checkout settings, apps, integrations, content, theme behavior, or outside-system workflows. A hosted platform can be a strong target, but migration planning must respect the difference between migrated data, target configuration, app behavior, integration setup, and custom scope.

Pitfall prevention should focus on early evidence. The safest ShopWired migrations identify what fits standard platform structures, what needs target setup, what belongs to apps or external systems, what can be handled through Add-ons, and what should move into Custom Service review before Full Migration.

### Pitfall 1: Treating ShopWired Like a Self-Hosted Custom Platform <a href="#pitfall-1-treating-shopwired-like-a-self-hosted-custom-platform" id="pitfall-1-treating-shopwired-like-a-self-hosted-custom-platform"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The source store’s custom code, database changes, checkout scripts, or unusual business rules are expected to move into ShopWired directly. This creates unrealistic migration expectations because ShopWired is a hosted platform with supported structures, settings, apps, themes, API surfaces, and integration options.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

* The source store depends on custom server-side code.
* Custom database tables carry product, customer, order, checkout, or integration data.
* The merchant expects source admin workflows to be reproduced exactly.
* Custom checkout fields or business rules are not documented.
* The target outcome depends on behavior that has not been confirmed as a ShopWired setting, app, theme change, integration, or custom scope.

#### Prevention <a href="#prevention" id="prevention"></a>

Classify each source behavior before migration. Decide whether it is migrated data, target configuration, theme work, app behavior, outside-system setup, accepted exclusion, or Custom Service scope. Do not assume that custom source behavior can be copied directly into the hosted target environment.

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

Before Full Migration, list custom fields, custom checkout behavior, app-owned data, external-system IDs, and source-side custom code. For each item, assign a target handling decision.

#### Pass Condition <a href="#pass-condition" id="pass-condition"></a>

The migration scope reflects ShopWired’s hosted-platform model, and custom source behavior has been configured, rebuilt, excluded, or escalated intentionally.

### Pitfall 2: Flattening Product Variations, Choices, Extras, or Bundles <a href="#pitfall-2-flattening-product-variations-choices-extras-or-bundles" id="pitfall-2-flattening-product-variations-choices-extras-or-bundles"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Products migrate as visible records, but customer-facing buying choices lose their meaning. Variations, choices, extras, personalization fields, bundles, digital-product behavior, stock-sensitive options, or add-on charges may be flattened into descriptions or omitted from the functional buying flow.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

* Source options affect price, stock, image, delivery, tax, weight, or fulfillment.
* Products use personalization or custom input fields.
* Bundles, kits, grouped products, or digital products are used.
* Extras or optional upgrades create additional charges.
* Demo Migration samples include only simple products.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Choose product samples that expose real product-choice complexity. Validate products from the storefront, not only from the admin area. Confirm whether source product choices should become ShopWired variations, choices, extras, bundles, app-supported behavior, or Custom Service scope.

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

Include a product with variations, a product with extras, a personalized product, a bundled product, a stock-sensitive product, and a product with important SEO fields in Demo Migration review.

#### Pass Condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Products remain sellable and customer-facing choices still support the intended price, stock, delivery, fulfillment, and buying behavior.

### Pitfall 3: Migrating Products Without Validating Discovery <a href="#pitfall-3-migrating-products-without-validating-discovery" id="pitfall-3-migrating-products-without-validating-discovery"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Products appear in ShopWired, but customers cannot find them through the expected browsing paths. Categories, brands, filters, menus, featured sections, search behavior, and channel visibility may not reflect the source-store experience.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

* Products belong to multiple categories.
* Brand-led browsing is important.
* Filters or specifications drive product selection.
* Menus or landing pages are manually curated.
* Some products should appear differently across customer groups or channels.
* Product validation happens only in the admin panel.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Validate product discovery from the storefront. Test categories, brands, filters, search terms, menus, landing pages, and channel-specific visibility where relevant.

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

Review a top category, deep subcategory, brand page, filter-heavy product group, search query, and high-value landing page after Demo Migration.

#### Pass Condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Representative products can be found through the customer-facing discovery paths the merchant expects to use after launch.

### Pitfall 4: Treating B2B and Trade Customers as Ordinary Customer Records <a href="#pitfall-4-treating-b2b-and-trade-customers-as-ordinary-customer-records" id="pitfall-4-treating-b2b-and-trade-customers-as-ordinary-customer-records"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Customer accounts migrate, but B2B or trade behavior is lost. Customer groups may no longer control pricing, quote workflows, approval, account terms, tax handling, visibility, payment methods, or delivery rules.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

* The store has wholesale, trade, account-based, or approved customers.
* Customer groups affect price, tax, product access, or checkout behavior.
* Quotes or negotiated terms are used.
* Trade customers have different payment or delivery rules.
* B2B behavior depends on apps or custom fields.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Separate customer records from B2B behavior. Validate trade customers, quotes, account terms, group pricing, approval rules, and checkout restrictions as business rules, not just imported account labels.

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Include one standard customer, one guest customer, one customer group member, one trade customer, one quote-related customer, and one customer with external-system references in Demo Migration review.

#### Pass Condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Customer accounts remain interpretable, and any B2B or trade behavior is configured, migrated, excluded, rebuilt, or escalated intentionally.

### Pitfall 5: Accepting Orders Without Operational Context <a href="#pitfall-5-accepting-orders-without-operational-context" id="pitfall-5-accepting-orders-without-operational-context"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Orders migrate into ShopWired, but the history is not useful for customer service, finance, fulfillment, or management. Payment labels, delivery labels, tax values, discounts, notes, fulfillment state, refunds, quotes, subscription context, or external references may be incomplete.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

* The source store has custom order states or fulfillment rules.
* Orders include refunds, partial fulfillment, quotes, subscriptions, or manual adjustments.
* Notes or custom fields carry operational meaning.
* Payment and delivery methods vary by customer group or region.
* External systems depend on order IDs or customer IDs.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate varied orders across the real order lifecycle. Include ordinary retail orders, B2B orders, discounted orders, refunded or canceled orders, partially fulfilled orders, quote-related records, and externally referenced orders where relevant.

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Ask customer service, finance, and fulfillment users to review migrated order samples and confirm whether the order history is understandable without returning to the source store.

#### Pass Condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Historical orders preserve enough context to support post-migration service, fulfillment, finance, and management review.

### Pitfall 6: Confusing Migrated Checkout History with Live Checkout Readiness <a href="#pitfall-6-confusing-migrated-checkout-history-with-live-checkout-readiness" id="pitfall-6-confusing-migrated-checkout-history-with-live-checkout-readiness"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

The target store shows historical payment, delivery, and tax values, so the team assumes live checkout is ready. In reality, live checkout depends on ShopWired payment gateways, delivery rates, tax settings, customer-group rules, apps, and target configuration.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

* Payment and delivery labels appear in old orders, but target settings have not been tested.
* Tax configuration has not been reviewed.
* Customer groups need different checkout behavior.
* Custom checkout fields were used in the source store.
* B2B or quote workflows affect payment or delivery rules.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Separate historical order validation from live checkout testing. Migrated order history can preserve past context, but target checkout must be configured and tested for new orders.

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

After validating migrated orders, run separate target checkout tests for ordinary retail customers, B2B customers, payment methods, delivery methods, tax behavior, coupons, and quote/account-term scenarios where relevant.

#### Pass Condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Historical checkout context is readable, and live checkout behavior is configured and tested separately in the target store.

### Pitfall 7: Assuming Apps, API Connections, or Webhooks Will Resume Automatically <a href="#pitfall-7-assuming-apps-api-connections-or-webhooks-will-resume-automatically" id="pitfall-7-assuming-apps-api-connections-or-webhooks-will-resume-automatically"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The migration moves ordinary store data, but connected workflows break because apps, API connections, webhooks, marketplaces, accounting tools, fulfillment systems, or external inventory systems were not reviewed as part of the target operating model.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

* External systems depend on product, customer, order, or inventory IDs.
* Webhooks trigger fulfillment, accounting, CRM, or email workflows.
* Marketplace or feed data includes channel-specific fields.
* App-owned records affect checkout, quotes, subscriptions, product display, or B2B behavior.
* The merchant expects connected services to work immediately after migration.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Create an integration inventory before Full Migration. Classify each connected system as reconfigured, rebuilt, mapped, excluded, or escalated. Validate integration-sensitive records if IDs or workflow continuity matter.

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

For each app, API connection, webhook, marketplace, ERP, CRM, POS, accounting, fulfillment, email, inventory, or reporting system, document whether it owns data and how it will be handled after migration.

#### Pass Condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Connected-system expectations are explicit, and app-owned or integration-sensitive data is not mistaken for standard platform data.

### Pitfall 8: Leaving SEO, Content, and Theme Review Until Launch <a href="#pitfall-8-leaving-seo-content-and-theme-review-until-launch" id="pitfall-8-leaving-seo-content-and-theme-review-until-launch"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Products and orders migrate successfully, but important content, menus, URLs, metadata, redirects, banners, theme sections, and landing pages are incomplete. The store may function at a data level while losing search continuity or customer trust.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

* Organic search traffic is important.
* Product, category, brand, or content URLs have ranking value.
* Menus and landing pages guide customer journeys.
* Theme-controlled sections carry product or campaign content.
* B2B, delivery, returns, or support pages matter to conversion.
* Content is treated as separate from migration quality.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Prepare high-value content and SEO samples before migration validation. Confirm which content should migrate, which should be rebuilt, which needs redirects, and which theme-controlled areas need separate work.

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

Create a priority list of product URLs, category URLs, brand pages, CMS Pages, policy pages, metadata, menus, landing pages, and theme-controlled sections before accepting migration results.

#### Pass Condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Important content and SEO paths are migrated, redirected, rebuilt, or formally accepted as outside scope.

### Pitfall 9: Choosing a Service Approach That Is Too Light <a href="#pitfall-9-choosing-a-service-approach-that-is-too-light" id="pitfall-9-choosing-a-service-approach-that-is-too-light"></a>

#### What Goes Wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

The migration begins under a standard assumption, but source review or Demo Migration reveals custom product-choice logic, app-owned records, B2B rules, outside-system identifiers, custom checkout fields, or integration workflows that were not included in scope.

#### Early Warning Signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

* Complex product samples fail to preserve buying behavior.
* Customer groups migrate but B2B rules are unclear.
* App-owned data is missing from migrated results.
* Outside-system IDs are needed but not mapped.
* Custom checkout fields carry fulfillment or customer-service meaning.
* Demo Migration excludes the hardest records.

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Use Demo Migration to test the source store’s most complex records. Escalate custom, app-owned, integration-owned, or unsupported requirements before Full Migration. Use Add-ons for supported filtering, mapping, or data configuration needs, and use Custom Service for bespoke migration behavior.

#### Recommendation Example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

If Demo Migration shows missing extras, quote data, custom checkout fields, or external IDs, classify each issue as target configuration, Add-on-supported adjustment, accepted exclusion, or Custom Service review.

#### Pass Condition <a href="#pass-condition-8" id="pass-condition-8"></a>

The chosen service approach matches the actual migration complexity, and unresolved custom or app-owned requirements are not pushed into launch review.

### Pitfall 10: Validating Only Record Counts <a href="#pitfall-10-validating-only-record-counts" id="pitfall-10-validating-only-record-counts"></a>

#### What Goes Wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

The migration is accepted because product, customer, order, or content counts match expectations. Later, the team discovers that product choices do not work, B2B customers lost meaning, historical orders are incomplete, SEO paths are missing, or apps and integrations need additional work.

#### Early Warning Signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

* Validation focuses on totals rather than representative records.
* Product samples do not include variations, choices, extras, or bundles.
* Customer samples exclude B2B or trade accounts.
* Order samples exclude refunds, discounts, notes, or fulfillment complexity.
* SEO/content and integrations are not part of acceptance review.

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Validate by business meaning, not only by count. Use sample groups that represent the actual store: complex products, B2B customers, varied orders, high-value URLs, content pages, app-owned records, and integration-sensitive identifiers.

#### Recommendation Example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

Build a validation checklist that includes record totals and representative records. A count match should be treated as one signal, not as final acceptance.

#### Pass Condition <a href="#pass-condition-9" id="pass-condition-9"></a>

The migrated ShopWired store is accepted based on usable products, customers, orders, content, SEO, checkout boundaries, apps, and integrations, not only matching totals.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Most ShopWired migration pitfalls can be prevented when the source store is reviewed as a working business system. Product choices, B2B rules, order context, checkout behavior, apps, integrations, content, SEO, theme presentation, and hosted-platform boundaries all affect whether the target store will be usable after migration.

Before approving Full Migration or launch readiness, review the failure patterns most relevant to the source store. If any pitfall appears in source review or Demo Migration, resolve the scope through target configuration, Add-ons, Custom Service review, or an accepted exclusion before treating the migration as complete.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the most common ShopWired migration pitfall?**

The most common pitfall is treating hosted-platform migration as a simple data copy. Product choices, B2B rules, checkout behavior, apps, integrations, SEO, and content often need separate interpretation or configuration.

**Can product counts match while the migration still has problems?**

Yes. Product counts can match while variations, choices, extras, bundles, categories, brands, stock behavior, or SEO fields are incomplete or no longer support the intended buying experience.

**Why should B2B behavior be reviewed separately?**

B2B behavior can depend on customer groups, trade pricing, quotes, approval rules, payment terms, delivery rules, tax treatment, apps, or custom logic. Those areas may not be preserved by ordinary customer migration alone.

**Do apps and integrations migrate automatically?**

No. Apps, API connections, webhooks, marketplaces, accounting tools, fulfillment systems, and other outside services should be reviewed separately. Some may be reconfigured, rebuilt, mapped, excluded, or escalated to Custom Service.

**When should a ShopWired pitfall trigger Custom Service review?**

Custom Service review should be considered when the issue involves Custom Platform data, app-owned records, outside-system identifiers, custom checkout fields, non-standard product transformation, B2B custom logic, or tailored migration behavior beyond Standard Add-on capability.
