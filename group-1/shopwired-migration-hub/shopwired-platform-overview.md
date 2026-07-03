# ShopWired Platform Overview

ShopWired is a hosted e-commerce platform for merchants that want a managed store environment with built-in selling features, themes, apps, payment and delivery configuration, B2B capabilities, multi-channel selling, and developer-facing integration options. For migration planning, ShopWired should be understood as a SaaS Target Platform where the target store structure, available settings, theme behavior, installed apps, and plan-level capabilities shape what the migrated result can become.

Moving to ShopWired is not only a transfer of products, customers, orders, and content. The target store needs to interpret source data through ShopWired’s catalog model, product variations, choices, extras, bundles, digital products, stock behavior, categories, brands, checkout settings, customer groups, B2B or trade features, order records, tax and delivery logic, themes, SEO fields, apps, APIs, and multi-channel connections.

A good migration outcome depends on whether the source store’s commercial meaning can be reconstructed inside ShopWired’s hosted structure. Some source data can map naturally into platform features. Some behavior belongs to target configuration. Some app-owned, custom, or external-system data needs deeper review before it can be included in the migration scope.

### What Changes in a Migration to ShopWired <a href="#what-changes-in-a-migration-to-shopwired" id="what-changes-in-a-migration-to-shopwired"></a>

A migration to ShopWired changes the operating model as well as the data model. The store moves into a hosted environment where product setup, storefront design, checkout behavior, apps, integrations, and business-to-business features are controlled through the ShopWired platform and its supported customization surfaces.

| Migration area                       | What changes in ShopWired                                                                                                                                           | Planning implication                                                                                                      |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure                    | Products may depend on categories, brands, variations, choices, extras, bundles, digital products, images, SKUs, stock, tax, delivery settings, and SEO fields.     | Product samples should include complex catalog cases, not only simple products.                                           |
| Variations and choices               | Source variants, options, modifiers, add-ons, or custom fields may need to be interpreted through ShopWired variations, choices, extras, or app-supported behavior. | Buying choices should be validated in the storefront so purchase behavior is not reduced to plain description text.       |
| Categories and brands                | Product discovery may depend on category assignment, brand pages, filters, menus, and search behavior.                                                              | Migrated products should be checked from the customer-facing storefront, not only from the admin product list.            |
| Customers and B2B behavior           | Customers may include account records, groups, trade pricing, account limits, quotes, B2B approval, or customer-specific terms where used.                          | Customer migration should preserve account meaning and identify which B2B rules are data, configuration, or custom scope. |
| Orders and history                   | Orders can carry customer data, products, totals, discounts, delivery context, payment context, fulfillment state, and notes.                                       | Historical order readability should be validated separately from live checkout readiness.                                 |
| Checkout, delivery, payment, and tax | Live checkout depends on ShopWired settings, available payment gateways, delivery rates, tax rules, and enabled apps.                                               | Migrated historical labels do not automatically configure live selling behavior.                                          |
| Themes and content                   | Storefront presentation depends on themes, theme code, pages, menus, banners, navigation, blog or content areas, and SEO settings.                                  | Design and content continuity may require separate review from data migration.                                            |
| Apps, API, webhooks, and channels    | Apps, integrations, multi-channel selling, API connections, and webhook behavior can carry operational meaning outside ordinary store records.                      | App-owned and external-system data should be identified before scope is finalized.                                        |

### Where ShopWired Is Often a Strong Target <a href="#where-shopwired-is-often-a-strong-target" id="where-shopwired-is-often-a-strong-target"></a>

ShopWired is often a strong target for merchants that want a hosted commerce platform with practical selling tools, B2B options, theme customization, app-based extensions, and structured administration without managing their own infrastructure. It can be especially suitable when the merchant wants a more controlled environment than a self-hosted platform, but still needs deeper commerce features than a very simple website builder.

#### Hosted commerce with practical operational control <a href="#hosted-commerce-with-practical-operational-control" id="hosted-commerce-with-practical-operational-control"></a>

ShopWired can be a strong fit for merchants that want a hosted platform where product, order, customer, delivery, payment, tax, content, and design settings are managed inside the platform. This reduces the burden of server management while still allowing merchants to configure core commerce behavior.

For migration planning, this means the target result should be evaluated against ShopWired’s supported structures and settings. The goal is not to reproduce a source store’s custom infrastructure exactly, but to translate the important commerce meaning into the target platform’s model.

#### Catalogs with meaningful product choices <a href="#catalogs-with-meaningful-product-choices" id="catalogs-with-meaningful-product-choices"></a>

ShopWired supports product structures that can include variations, choices, extras, categories, brands, digital products, bundles, stock behavior, and product-level presentation details. This makes it relevant for merchants whose products need more than a flat title, image, price, and description.

The key migration question is whether source options, modifiers, variants, specifications, and special product behavior can be expressed in the right ShopWired structures. Product samples should include real complexity before the migration is accepted.

#### B2B, trade, and account-based selling <a href="#b2b-trade-and-account-based-selling" id="b2b-trade-and-account-based-selling"></a>

ShopWired can be relevant for merchants with business-to-business needs, trade customers, customer groups, quotes, account-based terms, or different pricing and checkout expectations for different customer types. These features can make the platform a stronger target than simpler hosted storefront builders.

The migration still needs careful planning. B2B behavior may be partly data, partly platform configuration, partly app-supported behavior, and partly custom requirement. Customer group and trade samples should be reviewed early if they affect pricing, visibility, quote handling, order flow, or checkout access.

#### Multi-channel and integration-oriented stores <a href="#multi-channel-and-integration-oriented-stores" id="multi-channel-and-integration-oriented-stores"></a>

ShopWired can support stores that sell across more than one channel or depend on connected services. Apps, API access, webhooks, marketplace connections, payment providers, delivery integrations, and other external systems can all affect how the target store operates.

A migration should separate platform data from integration behavior. Product, customer, and order records may migrate into ShopWired, while channel connections, external identifiers, app-owned records, and automation logic may need separate configuration or Custom Service review.

### Where Deeper Planning Is Usually Needed <a href="#where-deeper-planning-is-usually-needed" id="where-deeper-planning-is-usually-needed"></a>

ShopWired’s hosted model can make store management more straightforward, but it also means the target result must fit supported platform behavior. Risk increases when the source store depends on custom code, unusual product models, app-owned records, external integrations, or business logic that does not map neatly into ShopWired.

#### Product variations, extras, and custom options <a href="#product-variations-extras-and-custom-options" id="product-variations-extras-and-custom-options"></a>

Source platforms often represent product choices differently. A source variant may become a ShopWired variation, a choice, an extra, a product field, a bundle relationship, or an app-dependent behavior. If the meaning is not reviewed, customer-facing product selection can become inaccurate.

Deeper planning is usually needed when options affect price, stock, image, fulfillment, personalization, quote behavior, delivery rules, or availability. Product samples should include the most complex buying scenarios, not only ordinary products.

#### B2B, quote, and trade-customer behavior <a href="#b2b-quote-and-trade-customer-behavior" id="b2b-quote-and-trade-customer-behavior"></a>

B2B data needs careful separation between migrated records and target configuration. A customer record may migrate, but customer group behavior, account pricing, quote workflows, approval rules, tax handling, and payment terms may require configuration or custom review.

If the source store uses complex B2B logic, migration planning should identify which parts are ordinary customer data, which parts can be configured in ShopWired, which parts depend on apps, and which parts need Custom Service review.

#### Checkout, delivery, tax, and payment rules <a href="#checkout-delivery-tax-and-payment-rules" id="checkout-delivery-tax-and-payment-rules"></a>

Historical order data and live checkout behavior should not be confused. Migrated orders can preserve historical labels and values, but live checkout depends on ShopWired’s target settings, payment gateways, delivery zones or rates, tax configuration, and enabled apps.

Stores with unusual shipping rules, regional tax needs, trade-customer checkout rules, custom payment flows, or multi-location fulfillment should review these requirements before Full Migration.

#### Themes, storefront content, and SEO <a href="#themes-storefront-content-and-seo" id="themes-storefront-content-and-seo"></a>

ShopWired themes and content structures control how the target store looks and how customers move through it. A migration can place product and content data into the target store while the presentation still needs theme work, menu configuration, page review, image adjustment, or SEO planning.

SEO-sensitive stores should prepare high-value product, category, brand, content, and landing-page samples. The goal is to confirm that important page names, metadata, redirects, and customer-entry paths are accounted for before launch.

#### Apps, API, webhooks, and outside systems <a href="#apps-api-webhooks-and-outside-systems" id="apps-api-webhooks-and-outside-systems"></a>

ShopWired stores may rely on apps, APIs, webhooks, external marketplaces, accounting systems, fulfillment services, payment systems, email tools, or other integrations. Those systems may carry identifiers, workflow history, automation rules, or app-owned data that standard commerce migration does not automatically include.

If an integration owns business-critical data or the target store must preserve outside-system references, scope should be reviewed before the migration is treated as straightforward.

### What Should Be Understood Early Before Moving into ShopWired <a href="#what-should-be-understood-early-before-moving-into-shopwired" id="what-should-be-understood-early-before-moving-into-shopwired"></a>

Before migrating to ShopWired, the merchant should understand which parts of the source store are ordinary commerce records and which parts are platform configuration, theme work, app behavior, integration logic, or custom data. This distinction helps avoid unrealistic expectations and makes Demo Migration review more useful.

The following points should be understood early:

* **ShopWired is a hosted platform.** Migration planning should fit ShopWired’s supported structures and configuration model rather than assuming the target can reproduce all source custom code directly.
* **Product choices need careful interpretation.** Variations, choices, extras, bundles, personalization, digital products, and stock behavior should be sampled when they affect buying.
* **B2B behavior should be separated from customer records.** Customers may migrate, but trade pricing, quotes, approval, account terms, and special checkout behavior may require target configuration or custom review.
* **Historical orders and live checkout are different concerns.** Migrated order history can preserve past context, while payment, delivery, tax, and checkout readiness must be configured and validated in the target.
* **Themes and content affect the final result.** Product records can migrate correctly while menus, pages, banners, SEO fields, or storefront presentation still need review.
* **Apps and integrations may change scope.** App-owned records, API connections, webhooks, outside-system identifiers, and channel-specific data should be identified before migration scope is finalized.
* **Demo Migration samples should include real complexity.** Complex products, B2B customers, varied orders, high-value URLs, CMS Pages, app-dependent records, and integration-sensitive examples should be part of early review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired can be a strong Target Platform for merchants that want a hosted e-commerce environment with practical catalog tools, themes, apps, B2B capabilities, checkout configuration, and integration options. Its migration success depends on translating the source store’s real business meaning into ShopWired’s supported structures rather than treating every source field as a direct copy.

Before moving forward, review the source store’s product choices, customer groups, B2B behavior, order history, checkout requirements, theme/content needs, SEO priorities, apps, and integrations. A focused Demo Migration can show whether the migration path is straightforward or whether Add-ons, deeper mapping, or Custom Service review should be planned before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Is ShopWired a hosted or self-hosted platform?**

ShopWired is a hosted e-commerce platform. Migration planning should account for the target platform’s supported structures, settings, themes, apps, and integration surfaces rather than assuming the merchant can directly reproduce every source-side custom implementation.

**What makes ShopWired different from a simple product-data target?**

ShopWired stores can depend on product variations, choices, extras, bundles, digital products, categories, brands, B2B settings, checkout configuration, themes, apps, APIs, and multi-channel behavior. Migration quality depends on preserving those meanings, not only moving product names and prices.

**Can B2B or trade customer data migrate into ShopWired?**

Customer records may migrate where supported, but B2B behavior should be reviewed separately. Trade pricing, quotes, approval rules, account terms, customer-specific visibility, and checkout behavior may be target configuration, app-supported behavior, or Custom Service scope.

**Does migrating historical orders configure checkout automatically?**

No. Historical order data and live checkout configuration are different. Payment, delivery, tax, and checkout settings must be configured and tested in the target ShopWired store even when historical order labels migrate successfully.

**What should I include in a Demo Migration sample for ShopWired?**

Include products with variations, choices, extras, or bundles; B2B or trade customers; varied order states; important categories and brands; CMS Pages; high-value URLs; app-dependent records; and any data connected to APIs, webhooks, marketplaces, or outside systems.
