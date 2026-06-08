# ShopWired Validation Priorities

Validation for a ShopWired migration should prove that the target store works as a hosted commerce environment, not only that records appear in the admin area. Product count, customer count, and order count are useful checks, but they do not prove that variations, choices, extras, B2B rules, checkout behavior, apps, integrations, SEO fields, and storefront content have retained their business meaning.

ShopWired validation should be built around the source store’s real complexity. A simple retail catalog may need a focused sample review. A store with product personalization, bundles, trade pricing, quotes, customer groups, external inventory, app-owned records, or marketplace identifiers needs a broader proof framework before the migration can be accepted confidently.

### What Validation Is Really Trying to Prove <a href="#what-validation-is-really-trying-to-prove" id="what-validation-is-really-trying-to-prove"></a>

Validation should answer whether the migrated ShopWired store can support the merchant’s real selling model. The target result should be reviewed from both the admin and storefront perspectives. A product can exist in the admin but still fail validation if customers cannot select the right choices, find the product in the right category, see correct pricing, or complete checkout through the expected flow.

| Validation priority                      | What to check                                                                                                                 | What a pass should prove                                                                       |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Product meaning                          | Product names, SKUs, images, descriptions, categories, brands, stock, delivery settings, tax behavior, and SEO fields.        | Products remain recognizable, sellable, and correctly organized.                               |
| Variations, choices, extras, and bundles | Product options, personalization, optional add-ons, grouped or bundled buying, digital products, and stock-sensitive choices. | Shopper-facing purchase choices still work as intended.                                        |
| Product discovery                        | Categories, brands, menus, filters, search, featured areas, and channel visibility.                                           | Customers can find products through expected storefront paths.                                 |
| Customers and B2B records                | Accounts, addresses, groups, trade customers, quotes, account terms, and order links.                                         | Customer segmentation and account meaning remain usable.                                       |
| Historical orders                        | Products, totals, discounts, payment and delivery labels, tax values, fulfillment state, notes, and customer links.           | Orders remain readable for operations, finance, and customer service.                          |
| Checkout boundaries                      | Historical checkout data versus live target payment, delivery, tax, customer-group, and app settings.                         | The team does not confuse migrated history with configured live checkout.                      |
| Content and SEO                          | CMS Pages, menus, metadata, page names, redirects, high-value URLs, and theme-dependent content.                              | Important customer-entry paths are included, rebuilt, redirected, or accepted as out of scope. |
| Apps and integrations                    | App-owned records, API data, webhooks, marketplace fields, external IDs, and automation dependencies.                         | Connected-system data is migrated, mapped, rebuilt, excluded, or escalated intentionally.      |

### Validate Products as Customer-Facing Records <a href="#validate-products-as-customer-facing-records" id="validate-products-as-customer-facing-records"></a>

Product validation should include storefront review, not only admin review. In ShopWired, a product’s business meaning may depend on variations, choices, extras, bundles, categories, brands, stock, images, delivery settings, tax behavior, and SEO fields.

A strong product validation set should include:

* a simple product with ordinary price, image, category, and description;
* a product with variations such as size, color, or material;
* a product with choices or extras that affect the buying experience;
* a personalized or configurable product where customer input matters;
* a bundled, grouped, kit, or package product if used;
* a digital product or product with special fulfillment assumptions;
* a product assigned to multiple categories;
* a product connected to a brand-led browsing path;
* a stock-sensitive product or product controlled by external inventory;
* a product with important SEO fields or historical URL value.

A product sample passes validation when shoppers can understand, select, and purchase the product in the intended target context.

### Validate Variations, Choices, Extras, and Special Product Behavior <a href="#validate-variations-choices-extras-and-special-product-behavior" id="validate-variations-choices-extras-and-special-product-behavior"></a>

Product choice structures are one of the most important ShopWired validation areas. A migrated product can look correct at a summary level while losing important purchase behavior.

Validation should answer:

| Product-choice area     | Validation question                                                                     |
| ----------------------- | --------------------------------------------------------------------------------------- |
| Variations              | Do selectable dimensions such as size, color, material, or style appear correctly?      |
| Choices                 | Can shoppers select the intended options without losing pricing or fulfillment meaning? |
| Extras                  | Are optional upgrades, add-ons, or personalization charges represented acceptably?      |
| Bundles or kits         | Does the target store reflect the intended grouped buying behavior?                     |
| Digital products        | Are delivery, access, or fulfillment expectations represented correctly?                |
| Stock-sensitive options | Does the selected option reflect stock or availability expectations where relevant?     |
| Product images          | Do images support the selected product choices where expected?                          |

The main validation risk is flattening product choices into text. Text may preserve information, but it may not preserve buying behavior.

### Validate Categories, Brands, and Storefront Discovery <a href="#validate-categories-brands-and-storefront-discovery" id="validate-categories-brands-and-storefront-discovery"></a>

ShopWired validation should prove that products are findable in the ways customers will actually browse. Products should be reviewed through category pages, brand pages, menus, filters, search, featured sections, and channel-specific views where relevant.

Validation should include:

* top-level categories;
* deep subcategories;
* products assigned to multiple categories;
* brand-led browsing paths;
* filter-heavy product groups;
* search terms customers are likely to use;
* homepage or featured-product areas;
* channel-specific product visibility where relevant;
* high-value category or brand landing pages.

A common validation gap is checking whether products exist but not checking whether customers can reach them.

### Validate Customers, Groups, B2B, and Trade Behavior <a href="#validate-customers-groups-b2b-and-trade-behavior" id="validate-customers-groups-b2b-and-trade-behavior"></a>

Customer validation should include the account structures that matter to the merchant’s sales model. Ordinary retail customers and trade customers may need different validation samples.

Strong customer samples include:

| Customer sample                  | What it proves                                                                               |
| -------------------------------- | -------------------------------------------------------------------------------------------- |
| Standard registered customer     | Account details, addresses, and order links remain understandable.                           |
| Guest customer                   | Guest order history remains usable without being misread as full account behavior.           |
| Customer with multiple addresses | Billing and delivery relationships remain interpretable.                                     |
| Customer group member            | Segmentation is preserved where supported.                                                   |
| Trade or B2B customer            | Account context, pricing expectations, and order behavior can be reviewed.                   |
| Quote-related customer           | Quote and order relationships remain understandable where relevant.                          |
| Customer with external ID        | CRM, ERP, accounting, POS, marketplace, or fulfillment references are traceable if required. |

B2B validation should separate customer data from target configuration. A group label may migrate, but pricing, quotes, approval, account terms, payment access, delivery rules, and tax behavior may need target setup, app support, or Custom Service review.

### Validate Historical Orders, Quotes, and Subscription Context <a href="#validate-historical-orders-quotes-and-subscription-context" id="validate-historical-orders-quotes-and-subscription-context"></a>

Historical orders should be validated for operational readability. The people who rely on order records after migration should be able to understand what happened without returning to the source store for ordinary reference.

Validate samples with:

* paid and unpaid states;
* fulfilled and unfulfilled orders;
* refunded, canceled, or partially fulfilled orders;
* discounts, vouchers, credits, or manual adjustments;
* different payment and delivery method labels;
* tax-sensitive totals;
* customer and admin notes;
* B2B or trade orders;
* quote-related orders where relevant;
* subscription-like or recurring-order context if used;
* external-system or channel references where relevant.

A strong order sample passes when customer service, finance, fulfillment, and management users can understand the record well enough for post-migration reference.

### Validate Checkout, Delivery, Payment, and Tax Boundaries <a href="#validate-checkout-delivery-payment-and-tax-boundaries" id="validate-checkout-delivery-payment-and-tax-boundaries"></a>

Validation should clearly separate migrated historical data from live target setup. Past payment and delivery labels may migrate for order readability, but live checkout depends on ShopWired payment gateways, delivery rules, tax settings, customer groups, apps, and configuration.

| Validation track                 | What it proves                                                                                                |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Historical payment labels        | Past orders remain understandable.                                                                            |
| Live payment setup               | The target store can accept payment through configured methods.                                               |
| Historical delivery labels       | Past delivery context remains readable.                                                                       |
| Live delivery setup              | The target store can apply delivery rates, zones, rules, or carrier behavior as configured.                   |
| Historical tax values            | Past tax context remains visible where supported.                                                             |
| Live tax rules                   | New orders calculate tax according to target settings.                                                        |
| Customer-group checkout behavior | B2B, trade, or restricted customers receive the intended target behavior.                                     |
| Custom checkout fields           | Fields are classified as order notes, customer data, app-owned records, accepted exclusions, or custom scope. |

This distinction prevents a misleading pass. A migration can preserve historical checkout context while the target store still requires configuration before launch.

### Validate Content, SEO, and Theme-Dependent Storefront Areas <a href="#validate-content-seo-and-theme-dependent-storefront-areas" id="validate-content-seo-and-theme-dependent-storefront-areas"></a>

ShopWired storefront quality depends on content and presentation as well as commerce records. CMS Pages, menus, banners, theme-controlled sections, metadata, URLs, redirects, image text, and landing pages should be reviewed where they affect customer experience or search continuity.

Validation should cover:

* high-value product URLs;
* high-value category and brand URLs;
* CMS Pages and landing pages;
* blog or content pages where relevant;
* metadata for priority pages;
* menus and navigation paths;
* homepage or campaign sections;
* policy, delivery, returns, B2B, or support pages;
* image alt text where important;
* redirects for important legacy URLs;
* theme presentation that affects product or category display.

Not every old page needs equal review. Priority should go to pages that affect search, conversion, customer trust, B2B onboarding, support, or launch quality.

### Validate Apps, API, Webhooks, and Integration Data <a href="#validate-apps-api-webhooks-and-integration-data" id="validate-apps-api-webhooks-and-integration-data"></a>

Apps and integrations should be validated as scope outcomes. If a source store relied on apps, API connections, webhooks, marketplaces, accounting systems, fulfillment tools, or external inventory, the migration should clarify what happened to that data or workflow.

For each important app or integration, classify the outcome:

| Classification | Meaning                                                                                 |
| -------------- | --------------------------------------------------------------------------------------- |
| Migrated       | The required data is included and appears acceptably in ShopWired.                      |
| Mapped         | Data is preserved through supported mapping or agreed field treatment.                  |
| Reconfigured   | The behavior belongs to target setup rather than migrated data.                         |
| Rebuilt        | The feature or workflow must be recreated after migration.                              |
| Excluded       | The data is intentionally out of scope and accepted as such.                            |
| Escalated      | Custom Service review is needed because the data or workflow requires bespoke handling. |

This classification avoids vague acceptance. It creates a concrete decision for app-owned and integration-sensitive areas.

### Strong Validation Samples for ShopWired <a href="#strong-validation-samples-for-shopwired" id="strong-validation-samples-for-shopwired"></a>

A strong validation sample should expose real complexity. It should not be limited to records that are easiest to migrate.

| Sample category              | Strong sample choice                                                                                | What it proves                                  |
| ---------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Product                      | Product with variations, choices, extras, images, categories, stock, delivery, tax, and SEO fields. | Product meaning survives target translation.    |
| Category or brand            | Deep category or brand page with customer-facing browsing value.                                    | Discovery remains usable.                       |
| B2B customer                 | Trade customer with group, quote, pricing, or account-term expectations.                            | Customer segmentation remains interpretable.    |
| Order                        | Order with payment, delivery, tax, discount, fulfillment, notes, and customer context.              | Historical order meaning remains readable.      |
| Content page                 | Important CMS Page, policy page, or landing page.                                                   | Storefront content continuity is accounted for. |
| SEO path                     | Product, category, brand, or content URL with traffic or backlink value.                            | Priority URL continuity is testable.            |
| App-owned record             | Record controlled by an app or platform extension.                                                  | Extension scope is understood.                  |
| Integration-sensitive record | Record with ERP, CRM, POS, accounting, fulfillment, marketplace, or channel ID.                     | External references are handled intentionally.  |

### What Often Gets Missed <a href="#what-often-gets-missed" id="what-often-gets-missed"></a>

Common validation gaps include:

* products that exist but have broken or flattened buying choices;
* variations that appear but no longer affect price, stock, image, or fulfillment as expected;
* extras or personalization fields lost as plain text;
* B2B customers migrated without pricing, quote, or account-rule review;
* historical orders accepted without delivery, payment, tax, note, or fulfillment context;
* past payment and delivery labels mistaken for live checkout setup;
* CMS Pages and menus excluded from launch review;
* SEO URLs and metadata sampled too late;
* app-owned records assumed to be ordinary platform data;
* API, webhook, marketplace, accounting, fulfillment, or inventory references ignored until connected workflows fail.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation should lead to a decision. Each issue should be classified so the team knows whether to continue, configure, map, filter, escalate, or reject the result.

| Result                                    | Meaning                                                                                         | Next decision                                                                       |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Pass                                      | The sample behaves acceptably and no material migration issue is found.                         | Continue reviewing the next sample group.                                           |
| Pass with configuration note              | Migrated data is acceptable, but target settings, apps, theme, or content work is still needed. | Assign the item to target setup or launch preparation.                              |
| Needs mapping or configuration adjustment | Data exists but does not carry the right target meaning.                                        | Review Advanced Data Mapping or Advanced Data Configure where supported.            |
| Needs filtering clarification             | Records migrated that should not move, or expected records were not selected.                   | Review Data Filter Add-on logic where appropriate.                                  |
| Needs Custom Service review               | Custom, app-owned, integration-owned, or unsupported data cannot be handled safely as standard. | Escalate before Full Migration or launch acceptance.                                |
| Not accepted                              | The result does not support business use.                                                       | Do not approve the migration result until the gap is resolved or formally accepted. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired validation should prove that the migrated target store can support real selling behavior. Products, variations, choices, extras, categories, brands, B2B customers, orders, checkout boundaries, content, SEO, apps, API connections, webhooks, and integrations should be reviewed as connected parts of the target store.

Use Demo Migration and post-migration review to test records that expose real business complexity. If validation shows gaps in product choices, customer groups, B2B behavior, order context, SEO, app-owned data, or integration identifiers, resolve them through configuration, Add-ons, Custom Service review, or accepted exclusions before approving Full Migration or launch readiness.

### FAQs <a href="#faqs" id="faqs"></a>

**What should I validate first after migrating to ShopWired?**

Start with complex products, customer groups, B2B or trade customers, varied orders, high-value URLs, CMS Pages, app-owned records, and integration-sensitive identifiers. These samples reveal more than simple record totals.

**Is matching the product count enough to approve a ShopWired migration?**

No. Product count only confirms presence. Validation should also prove that variations, choices, extras, categories, brands, stock, SEO fields, and storefront discovery remain usable.

**Why should B2B records be validated separately?**

B2B records can depend on customer groups, pricing, quotes, approval, payment access, delivery rules, account terms, and tax behavior. Those behaviors may be target configuration, app-supported behavior, or Custom Service scope.

**Do migrated orders prove that ShopWired checkout is ready?**

No. Migrated order history can preserve past payment and delivery context, but live checkout readiness depends on target payment, delivery, tax, app, and customer-group settings.

**How should app-owned or integration-owned data be validated?**

Each app or integration should be classified as migrated, mapped, reconfigured, rebuilt, excluded, or escalated. If the data needs bespoke handling, Custom Service review should be considered before Full Migration is accepted.
