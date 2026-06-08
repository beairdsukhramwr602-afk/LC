# ShopWired Constraints and Risks

ShopWired migration risk usually appears where source-store behavior depends on structures that are not simple product, customer, order, or page records. The target store may need to interpret variations, choices, extras, bundles, digital products, customer groups, trade pricing, quote behavior, checkout rules, delivery settings, payment methods, tax behavior, apps, API connections, webhooks, external channels, themes, and SEO fields through ShopWired’s hosted platform model.

These constraints do not automatically make ShopWired a weak target. They simply need early review. A hosted platform can provide a cleaner operating model than a custom or self-hosted stack, but it also means custom source behavior must fit supported ShopWired structures, target configuration, app-supported behavior, or Custom Service scope.

### Where Risk Concentrates in a ShopWired Migration <a href="#where-risk-concentrates-in-a-shopwired-migration" id="where-risk-concentrates-in-a-shopwired-migration"></a>

ShopWired risk is concentrated in the difference between source-store flexibility and target-platform interpretation. The risk is low when the source data is standard and the merchant’s target expectations fit ShopWired’s built-in features. Risk rises when the source store depends on unusual product configuration, customer-specific rules, custom checkout data, third-party apps, external integrations, or highly customized storefront behavior.

| Constraint area                          | Who it affects                                                   | Why it matters                                                                                                     | Earliest review priority                                                                                           |
| ---------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| Hosted-platform boundaries               | Store owners, developers, and operations teams                   | ShopWired is not a self-hosted platform where every source-side customization can be copied directly.              | Confirm which source behavior must become target configuration, app behavior, theme work, or Custom Service scope. |
| Variations, choices, extras, and bundles | Merchandisers, shoppers, and fulfillment teams                   | Product buying choices can lose price, stock, personalization, or fulfillment meaning if mapped too loosely.       | Sample complex products before Full Migration.                                                                     |
| B2B, trade, and customer groups          | Wholesale teams, B2B buyers, account managers, and finance teams | Groups may affect pricing, quote workflows, account terms, approval, tax, visibility, delivery, or payment access. | Confirm which customer rules are data, configuration, app behavior, or custom scope.                               |
| Orders, quotes, and subscriptions        | Customer service, operations, finance, and fulfillment teams     | Historical order or quote context may be incomplete if only totals and product names are reviewed.                 | Validate varied order and quote samples where relevant.                                                            |
| Checkout, payment, delivery, and tax     | Store owners, shoppers, operations teams, and finance teams      | Migrated history does not configure live checkout behavior.                                                        | Separate historical order review from target checkout setup and testing.                                           |
| Apps, API, webhooks, and integrations    | Technical teams and operations teams                             | App-owned records and external identifiers may sit outside standard migration structures.                          | Inventory installed apps and connected systems before scope is finalized.                                          |
| Themes, content, and SEO                 | Marketing teams, designers, SEO teams, and returning customers   | Storefront quality depends on menus, pages, metadata, redirects, theme presentation, and landing paths.            | Prepare priority content, URL, and theme-dependent samples.                                                        |
| Multi-channel selling                    | Marketplace, feed, fulfillment, and inventory teams              | Channel-specific product data, identifiers, and stock behavior may not be standard platform data.                  | Identify channel-owned fields, IDs, and sync expectations early.                                                   |

### Hosted-Platform Boundaries <a href="#hosted-platform-boundaries" id="hosted-platform-boundaries"></a>

ShopWired is a hosted platform. That is one of its strengths, but it also creates a boundary around migration expectations. A source store with custom server-side code, custom checkout scripts, direct database modifications, or unusual business logic cannot simply transfer that behavior into ShopWired as-is.

Risk increases when:

* the source store relies on custom code that changes product, cart, checkout, customer, or order behavior;
* custom fields are stored outside ordinary product, customer, or order structures;
* the merchant expects source-side admin workflows to be reproduced exactly;
* a source integration controls inventory, pricing, fulfillment, or customer access;
* the target launch depends on behavior that is not clearly supported by ShopWired settings, apps, API, theme work, or accepted custom scope.

Mitigation starts with classification. Each source behavior should be classified as migrated data, target configuration, theme work, app behavior, external-system work, accepted exclusion, or Custom Service review.

### Product Variation, Choice, Extra, and Bundle Constraints <a href="#product-variation-choice-extra-and-bundle-constraints" id="product-variation-choice-extra-and-bundle-constraints"></a>

Product configuration is one of the most important ShopWired risk areas. Source platforms may use variants, product options, modifiers, personalization fields, add-ons, bundles, custom attributes, or app-controlled choices in different ways. Those structures may not map one-to-one into ShopWired.

Risk increases when product choices:

* affect price, stock, image, weight, delivery, tax, or fulfillment;
* include personalization or custom text fields;
* create add-on charges or optional upgrades;
* depend on product bundles or grouped buying;
* control downloadable-product access;
* come from an app or custom database table;
* appear differently across sales channels.

Mitigation requires product samples that expose real choice complexity. If Demo Migration only includes simple products, it may hide the most important product-translation risks.

### Category, Brand, and Discovery Constraints <a href="#category-brand-and-discovery-constraints" id="category-brand-and-discovery-constraints"></a>

Migrating products into ShopWired does not automatically prove that customers can find them. Product discovery may depend on categories, brands, filters, menus, search, product visibility, featured areas, and channel-specific display.

Risk increases when:

* the source store has deep category trees;
* products belong to multiple categories;
* brand-led browsing matters;
* filters or specifications drive customer decisions;
* categories double as SEO landing pages;
* product visibility differs across customer groups or channels;
* source navigation was manually curated.

Mitigation should include storefront discovery checks, not only product-admin checks. The migration should prove that representative products can be found through the same customer-facing logic the merchant expects after launch.

### B2B, Trade, Quote, and Customer-Group Constraints <a href="#b2b-trade-quote-and-customer-group-constraints" id="b2b-trade-quote-and-customer-group-constraints"></a>

ShopWired can be relevant for B2B and trade selling, but B2B data is often not just ordinary customer data. Trade pricing, account terms, quotes, approval flows, credit limits, customer-specific payment methods, tax treatment, and delivery rules may involve target configuration, apps, or custom handling.

Risk increases when:

* customer groups affect price or visibility;
* quote workflows are used;
* trade accounts require approval;
* different customers see different products or prices;
* payment, delivery, or tax behavior differs by group;
* account limits, customer-specific discounts, or negotiated terms must be preserved;
* B2B behavior depends on custom code or third-party apps.

Mitigation should start with customer and order samples that represent the actual B2B model. A retail customer sample is not enough for a trade-focused migration.

### Order, Quote, and Subscription Constraints <a href="#order-quote-and-subscription-constraints" id="order-quote-and-subscription-constraints"></a>

Historical orders should remain useful after migration. For ShopWired, order meaning may involve customer records, product lines, discounts, payment and delivery labels, tax values, fulfillment state, notes, refunds, quote history, subscription context, or external-system references.

Risk increases when:

* the source store uses quotes or recurring/subscription-like behavior;
* order statuses are custom or operationally important;
* orders include special instructions, custom fields, or fulfillment notes;
* payment and delivery methods vary significantly;
* discounts, vouchers, credits, or trade terms affect order meaning;
* external systems rely on old order IDs or customer IDs;
* historical orders are needed for service or compliance.

Mitigation should validate varied order samples. Historical order readability should be judged by the teams that use the records after launch, not only by record-count comparison.

### Checkout, Delivery, Payment, and Tax Constraints <a href="#checkout-delivery-payment-and-tax-constraints" id="checkout-delivery-payment-and-tax-constraints"></a>

Live checkout behavior is a target configuration issue. Migrating historical payment, delivery, and tax labels does not configure ShopWired payment gateways, delivery rates, tax behavior, customer-group rules, or checkout fields.

Risk increases when:

* checkout fields were customized in the source store;
* shipping depends on zones, rates, weights, carriers, order value, customer groups, or external fulfillment systems;
* tax behavior depends on region, product type, customer group, or B2B status;
* the store uses quotes, purchase orders, manual payment, or account terms;
* source checkout behavior was controlled by custom code or third-party apps.

Mitigation should separate historical order validation from target checkout testing. The migration can preserve past checkout context where supported, but the target store must still be configured and tested for new orders.

### App, API, Webhook, and Integration Constraints <a href="#app-api-webhook-and-integration-constraints" id="app-api-webhook-and-integration-constraints"></a>

ShopWired stores may depend on apps, API connections, webhooks, marketplaces, accounting systems, fulfillment tools, email services, payment providers, stock systems, or channel-specific feeds. These systems can own data that does not live in ordinary store records.

Risk increases when:

* external systems use product, customer, or order IDs that must remain traceable;
* marketplace listings contain channel-specific product fields;
* stock or fulfillment is synchronized from outside ShopWired;
* app-owned records affect product display, checkout, subscription, quote, or customer behavior;
* webhooks trigger operational workflows;
* the merchant expects connected services to resume automatically after migration.

Mitigation requires an integration inventory. Each connected app or system should be classified as reconfigured, rebuilt, mapped, excluded, or escalated to Custom Service review.

### Theme, Content, and SEO Constraints <a href="#theme-content-and-seo-constraints" id="theme-content-and-seo-constraints"></a>

ShopWired storefront presentation depends on themes, theme code, menus, pages, content areas, images, banners, metadata, URLs, redirects, and SEO settings. Migration can move content data while still leaving presentation, navigation, and search continuity incomplete.

Risk increases when:

* the source store has important landing pages;
* organic search traffic is important;
* product/category/brand URLs have ranking or backlink value;
* menus and homepage sections are manually curated;
* theme-controlled sections carry product or sales content;
* product images, alt text, or metadata are important;
* the merchant expects the new storefront to match source layout closely.

Mitigation should focus on priority content and URLs. Not every old page deserves equal review, but high-value product, category, brand, policy, B2B, and landing pages should be sampled before launch.

### When Risk Increases Enough for Custom Service Review <a href="#when-risk-increases-enough-for-custom-service-review" id="when-risk-increases-enough-for-custom-service-review"></a>

Not every ShopWired constraint requires Custom Service. Some needs can be handled through target configuration, Standard Add-ons, or post-migration storefront setup. Custom Service review becomes more important when standard service capability or available Add-ons cannot safely preserve the required business meaning.

Custom Service review should be considered when:

* the Source Platform or Target Platform is Custom Platform;
* source product choices require non-standard transformation;
* app-owned data must be migrated, mapped, or preserved;
* outside-system identifiers must remain traceable;
* B2B, quote, customer-group, or account-term logic is custom;
* checkout, delivery, payment, or tax behavior depends on custom fields or external logic;
* historical orders include custom data that must remain usable;
* the target outcome requires tailored migration behavior beyond Standard Add-on capability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired migration risks are manageable when the source store’s real operating structure is reviewed early. The main constraints usually involve hosted-platform boundaries, product-choice complexity, B2B and trade behavior, order and quote context, checkout configuration, apps and integrations, SEO, content, and theme presentation. These areas should be identified before the migration path is treated as straightforward.

Before Full Migration, prepare samples that expose the store’s real complexity and review Demo Migration results against those samples. If the result shows unsupported app data, custom checkout fields, B2B logic, outside-system identifiers, or product-choice transformation needs, resolve the scope through configuration, Add-ons, or Custom Service review before launch planning continues.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the biggest risk when migrating to ShopWired?**

The biggest risk is assuming that source-store behavior can be copied directly into a hosted platform. Product choices, B2B rules, checkout behavior, apps, integrations, and theme-controlled content must fit ShopWired’s supported structures or be reviewed separately.

**Can complex product options create migration risk?**

Yes. Source variants, modifiers, personalization fields, bundles, and add-ons may need to become ShopWired variations, choices, extras, bundles, or app-supported behavior. If they affect price, stock, delivery, or fulfillment, they should be sampled early.

**Are B2B customers migrated the same way as ordinary customers?**

Not always. B2B records may involve trade pricing, customer groups, quotes, approval, account terms, payment access, delivery rules, or tax treatment. Those behaviors may require configuration or Custom Service review.

**Do migrated orders prove that checkout is ready?**

No. Migrated order history can preserve past payment and delivery context, but live checkout depends on target ShopWired payment, delivery, tax, customer-group, and app settings.

**When should a ShopWired migration move into Custom Service review?**

Custom Service review should be considered when the migration involves Custom Platform data, app-owned records, outside-system identifiers, custom checkout fields, non-standard product transformation, B2B custom logic, or tailored migration behavior beyond Standard Add-on capability.
