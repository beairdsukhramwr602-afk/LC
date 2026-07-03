# ShopWired Data Model Differences

Migrating to ShopWired means translating source-store data into a hosted commerce model with its own assumptions about products, variations, choices, extras, categories, brands, customers, customer groups, orders, checkout settings, themes, apps, APIs, and multi-channel behavior. The goal is not only to move records, but to preserve what those records mean in day-to-day selling.

A source product option may become a ShopWired variation, choice, extra, bundle relationship, personalization field, digital-product setup, or app-supported behavior depending on how it works in the source store. A customer group may represent a simple segment, a B2B pricing rule, a trade account, a quote workflow, or a checkout restriction. An order may need delivery, payment, tax, discount, fulfillment, and customer context to remain useful after migration.

Data-model planning should therefore focus on business meaning. The migrated store should prove that ShopWired can represent how the source store sells, organizes products, serves customers, reads historical orders, and connects to surrounding systems.

### How ShopWired Interprets Migrated Data <a href="#how-shopwired-interprets-migrated-data" id="how-shopwired-interprets-migrated-data"></a>

ShopWired is a hosted platform, so migrated data must fit the structures and configuration surfaces available in the target store. Some source data maps into standard ShopWired records. Some behavior belongs to target setup. Some app-owned, API-connected, channel-specific, or custom data may need separate review.

| Source-store meaning   | How it may be interpreted in ShopWired                                                                                 | What the migrated result must prove                                                                          |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Product identity       | Product name, SKU, price, description, images, categories, brands, stock, tax, delivery settings, and SEO fields.      | Products remain recognizable, sellable, and correctly organized in the target storefront.                    |
| Product choices        | Variations, choices, extras, personalization options, bundles, digital products, or app-supported behavior.            | Shoppers can select the right options without losing price, stock, fulfillment, or product meaning.          |
| Product discovery      | Categories, brands, menus, filters, search, featured products, and channel visibility.                                 | Products can be found through expected customer-facing paths.                                                |
| Customer records       | Customer accounts, addresses, groups, B2B/trade context, quotes, account limits, and order links.                      | Customer segmentation and account meaning remain useful after migration.                                     |
| Historical orders      | Products, totals, discounts, delivery and payment context, fulfillment state, notes, customer links, and order status. | Orders remain readable for service, operations, and reference.                                               |
| Checkout behavior      | Payment, delivery, tax, customer-group rules, checkout fields, account settings, and enabled apps.                     | Historical labels are not confused with live checkout configuration.                                         |
| Content and storefront | Pages, blog/content areas, menus, banners, themes, theme code, navigation, and SEO values.                             | Content and presentation requirements are either migrated, configured, rebuilt, or accepted as out of scope. |
| Apps and integrations  | App-owned records, API data, webhooks, marketplace/channel data, outside-system identifiers, and automation logic.     | Integration-dependent data is included, excluded, reconfigured, or escalated intentionally.                  |

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

ShopWired product data may include ordinary product records, but the important migration work is often in the surrounding structures. Products can depend on categories, brands, variations, choices, extras, images, SKUs, stock behavior, delivery settings, tax handling, digital-product behavior, bundle relationships, and SEO values.

A source catalog should not be judged only by product count. Two stores with the same number of products can have very different migration complexity if one uses simple products and the other depends on configurable choices, trade pricing, personalization, product bundles, or integration-managed stock.

#### Variations, Choices, and Extras <a href="#variations-choices-and-extras" id="variations-choices-and-extras"></a>

Variations, choices, and extras should be reviewed as separate meaning layers. They may look similar in a source export, but they can affect different parts of the buying experience.

* **Variations** can represent core product options such as size, color, material, or another selectable product dimension.
* **Choices** can support selectable product configuration where the customer chooses from defined values.
* **Extras** can represent add-on selections, optional upgrades, personalization, or supplementary charges depending on how the target store is configured.
* **Bundles and special products** may need separate review if the source store connects multiple products into one buying experience.
* **Digital products** may carry file, fulfillment, or access assumptions that should not be reduced to ordinary product descriptions.

The safest migration samples should include products where options affect price, stock, images, fulfillment, delivery, personalization, or customer choice. If these cases are not sampled, the migration can appear cleaner than it really is.

#### Categories, Brands, and Product Discovery <a href="#categories-brands-and-product-discovery" id="categories-brands-and-product-discovery"></a>

ShopWired product discovery can depend on categories, brands, menu placement, filters, search behavior, merchandising sections, and channel-specific visibility. A product may migrate successfully as a product record but still fail commercially if it is not visible in the right category, brand, or browsing path.

Category and brand migration should preserve storefront meaning. If the source store uses brand-led browsing, curated categories, SEO landing pages, or filter-heavy product structures, validation should test how customers reach those products after migration.

### Customer and B2B Meaning <a href="#customer-and-b2b-meaning" id="customer-and-b2b-meaning"></a>

ShopWired customer data can be more than basic account records. Customer groups, B2B or trade accounts, quotes, account limits, company context, approval workflows, payment terms, and customer-specific pricing may affect how the target store treats buyers.

A customer group should not be treated as a label unless it is only used as a label. In many stores, customer grouping controls real business behavior. That behavior may be ordinary target configuration, app-supported behavior, custom scope, or data that should not migrate directly.

| Customer area                  | Meaning risk                                                                                | Review priority                                                          |
| ------------------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Registered customers           | Account details may move, but login continuity and customer expectations need review.       | Validate representative accounts with addresses and order links.         |
| Customer groups                | Groups may control price, tax, visibility, approval, credit, or payment access.             | Confirm whether groups are data, configuration, or custom behavior.      |
| B2B and trade customers        | Trade pricing, quotes, account terms, and approval may depend on target settings or apps.   | Sample real B2B buyers and quote/order workflows.                        |
| Addresses                      | Billing and delivery addresses may have different relationships in the target store.        | Validate customers with multiple addresses and varied order history.     |
| Customer-specific external IDs | ERP, CRM, accounting, or sales-channel identifiers may be outside standard customer fields. | Decide whether IDs need mapping, preservation, or Custom Service review. |

### Order and Historical Transaction Meaning <a href="#order-and-historical-transaction-meaning" id="order-and-historical-transaction-meaning"></a>

Historical orders in ShopWired should remain readable. They may need product names, SKUs, quantities, prices, totals, discounts, delivery method labels, payment method labels, customer details, fulfillment state, order notes, tax values, and status information to remain useful after migration.

The key distinction is between historical order context and live target configuration. A migrated order may show that a source customer paid by a certain method or selected a certain delivery service. That does not mean the live ShopWired checkout has been configured to accept the same payment method or calculate the same delivery rules.

A strong order sample set should include:

* paid and unpaid orders;
* fulfilled and unfulfilled orders;
* discounted or coupon-based orders;
* orders with multiple delivery methods or payment methods;
* B2B or quote-related orders where relevant;
* orders with notes, special instructions, or customer communication;
* refunded, canceled, or partially fulfilled orders where applicable;
* orders connected to external systems or sales channels.

Order validation should answer whether the merchant can understand and use the migrated order history after launch.

### Checkout, Delivery, Payment, and Tax Meaning <a href="#checkout-delivery-payment-and-tax-meaning" id="checkout-delivery-payment-and-tax-meaning"></a>

Checkout behavior is not only data migration. In ShopWired, live checkout behavior depends on target settings, payment providers, delivery configuration, tax rules, customer groups, B2B settings, enabled apps, and any custom requirements.

Source checkout fields may need different treatment depending on their purpose:

| Source checkout element | Likely target interpretation                                                  | Planning concern                                               |
| ----------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Payment method label    | Historical order label or target payment setup.                               | Do not confuse old order context with live payment readiness.  |
| Delivery method label   | Historical order label or target delivery configuration.                      | Live delivery settings need separate testing.                  |
| Tax total               | Historical value or target tax-rule behavior.                                 | New orders depend on target tax settings.                      |
| Custom checkout field   | Note, customer field, order field, app-owned data, or custom scope.           | Confirm whether the field has business or fulfillment meaning. |
| B2B checkout rule       | Customer-group setting, quote workflow, payment restriction, or custom logic. | Review customer group and B2B behavior before scope is locked. |

Migrating checkout-related data should preserve historical meaning where possible, while target checkout configuration should be planned and tested separately.

### Content, Theme, and SEO Meaning <a href="#content-theme-and-seo-meaning" id="content-theme-and-seo-meaning"></a>

ShopWired storefront data may include pages, blog or content areas, menus, banners, theme-controlled content, metadata, page names, redirects, and other SEO-related values. Some source content can migrate as content records. Some design behavior may need theme work. Some SEO behavior may require redirect planning or manual review.

Content migration should focus on the customer journey. A page that carries search traffic, brand trust, support information, size guides, delivery policies, or B2B instructions may matter more than a low-value historical page.

SEO planning should prioritize:

* important product URLs;
* important category URLs;
* brand or collection-style pages;
* CMS Pages and landing pages;
* meta titles and descriptions;
* page names or slugs;
* image alt text where important;
* redirect expectations;
* content that supports checkout, returns, delivery, or B2B terms.

### Apps, API, Webhooks, and Integration Data <a href="#apps-api-webhooks-and-integration-data" id="apps-api-webhooks-and-integration-data"></a>

ShopWired can support apps, API access, webhooks, multi-channel selling, and external integrations. These areas can affect migration because important business data may live outside ordinary product, customer, and order records.

Integration-sensitive data can include:

* marketplace identifiers;
* ERP, CRM, POS, accounting, or fulfillment IDs;
* subscription or quote-related data;
* product feed data;
* custom app records;
* automation rules;
* webhook-triggered workflows;
* external inventory references;
* customer-specific pricing or account terms stored outside standard records.

These should be classified before scope is finalized. Some integration behavior can be reconfigured after migration. Some data can be mapped. Some app-owned or external-system records may need Custom Service review.

### What Migrated Data Must Prove in ShopWired <a href="#what-migrated-data-must-prove-in-shopwired" id="what-migrated-data-must-prove-in-shopwired"></a>

A successful ShopWired migration should prove that the target data supports the intended business process, not only that expected records exist.

The migrated result should prove that:

* products are sellable and assigned to the correct categories, brands, and visibility contexts;
* variations, choices, extras, bundles, and digital products carry the intended buying meaning;
* customer accounts, groups, B2B/trade context, addresses, and order links remain interpretable;
* historical orders preserve enough payment, delivery, tax, discount, fulfillment, and customer context to be useful;
* checkout-related history is not mistaken for live target configuration;
* content, SEO fields, menus, and high-value URLs are included, rebuilt, or accepted as out of scope;
* apps, APIs, webhooks, multi-channel data, and outside-system identifiers have been reviewed intentionally;
* custom or unsupported structures have been mapped, excluded, or escalated before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired migration quality depends on translating source data into the right hosted-platform structures. Products, variations, choices, extras, customers, B2B rules, orders, checkout context, content, SEO values, apps, and integrations all carry business meaning that can be lost if they are treated as flat fields.

Use Demo Migration samples to test the data that carries the most meaning: complex products, B2B customers, quote or trade cases, varied orders, high-value URLs, content pages, app-dependent records, and integration-sensitive identifiers. If those samples do not translate clearly into ShopWired, mapping, configuration, Add-ons, or Custom Service review should be considered before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Why can product options change meaning when moving to ShopWired?**

Source platforms represent options, variants, modifiers, add-ons, and personalization differently. In ShopWired, those structures may need to become variations, choices, extras, bundles, digital-product behavior, app-supported data, or custom scope depending on how they affect buying.

**Are B2B customer groups just customer labels?**

Not always. B2B or trade groups can affect pricing, quote behavior, approval, account terms, payment access, delivery rules, or visibility. Their meaning should be reviewed before migration scope is finalized.

**Does migrating orders into ShopWired configure payment and delivery settings?**

No. Migrated order history can preserve past payment and delivery labels where supported, but live payment, delivery, tax, and checkout behavior must be configured and tested in the target ShopWired store.

**What happens to app-owned or integration-owned data?**

App-owned or integration-owned data should be reviewed separately from ordinary products, customers, and orders. It may be reconfigured, mapped, excluded, rebuilt, or reviewed through Custom Service depending on the requirement.

**What should a ShopWired Demo Migration prove?**

A Demo Migration should prove that complex products, customer groups, B2B cases, varied orders, SEO samples, content pages, app-dependent records, and integration-sensitive data can be interpreted acceptably inside ShopWired.
