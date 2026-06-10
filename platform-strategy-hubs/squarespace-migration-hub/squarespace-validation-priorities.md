# Squarespace Validation Priorities

Validation for a Squarespace migration should prove that the target site works as a hosted website and commerce environment, not only that records appear in the admin area. Squarespace can combine store pages, product records, variants, inventory, categories, tags, CMS Pages, Blog Posts, customer or contact records, orders, transactions, checkout settings, extensions, and connected services in ways that affect the final migration outcome.

A useful validation process should test the records that carry business meaning. Product count, customer count, order count, and page count are helpful checks, but they do not prove that customers can find products, select the right variants, understand content, complete checkout, or that the business can read order history and continue using connected workflows.

### What Validation Should Prove in Squarespace <a href="#what-validation-should-prove-in-squarespace" id="what-validation-should-prove-in-squarespace"></a>

Squarespace validation should confirm that the migrated site supports the intended business model within the target platform’s hosted structure. The review should cover both the storefront experience and the back-office usefulness of migrated records.

| Validation priority                  | What to check                                                                                                                                | What a pass should prove                                                                                                   |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Product records                      | Product names, descriptions, prices, images, SKUs, variants, inventory, categories, tags, visibility, and SEO fields.                        | Products remain recognizable, organized, and sellable in the target store.                                                 |
| Variants and SKUs                    | Option combinations, SKU-level details, pricing, images, stock, and availability where relevant.                                             | Shoppers can select the intended product version without losing commercial meaning.                                        |
| Store pages and discovery            | Store pages, category/tag navigation, product lists, menus, search paths, and featured products.                                             | Customers can find products through expected browsing paths.                                                               |
| Customers, contacts, and subscribers | Customer records, contact details, subscriber context, addresses, and order links where supported.                                           | Audience and customer data remains useful and is not misread as full account logic where the platform does not support it. |
| Orders and transactions              | Order totals, line items, discounts, taxes, shipping labels, payment context, transaction references, fulfillment state, and customer links. | Historical commerce records remain readable for service, finance, and management.                                          |
| Checkout boundaries                  | Historical order labels versus live payment, shipping, tax, subscription, and checkout settings.                                             | The team does not confuse migrated history with configured live checkout behavior.                                         |
| CMS Pages and Blog Posts             | Important pages, posts, images, links, content blocks, page names, and navigation placement.                                                 | Content continuity is acceptable for launch and customer trust.                                                            |
| SEO and URLs                         | Page titles, descriptions, slugs, product/category URLs, redirects, and high-value search entry paths.                                       | Important search and customer-entry paths are included, redirected, rebuilt, or accepted as out of scope.                  |
| Extensions, APIs, and webhooks       | Extension-owned data, Commerce API dependencies, webhooks, connected services, and outside-system identifiers.                               | Connected-system expectations are classified instead of assumed.                                                           |

### Validate Products as Storefront Records <a href="#validate-products-as-storefront-records" id="validate-products-as-storefront-records"></a>

Product validation should start from the customer-facing storefront. A product can look acceptable as a record while still failing commercially if its options, images, stock, category placement, page visibility, or purchase path are incomplete.

Strong product samples should include:

* a simple physical product with standard price, description, image, SKU, and category placement;
* a product with multiple variants or option combinations;
* a product with SKU-level inventory or availability differences;
* a product with important images or image-ordering expectations;
* a product assigned to categories or tags that support browsing;
* a product with sale pricing, discounts, or promotional context where relevant;
* a digital product, service-style product, or subscription-related product if used;
* a product that depends on shipping, tax, or fulfillment assumptions;
* a product with important SEO title, description, slug, or historical URL value.

A product sample passes validation when the storefront experience supports the same buying decision the merchant expects customers to make after migration.

### Validate Variants, SKUs, Inventory, and Product Options <a href="#validate-variants-skus-inventory-and-product-options" id="validate-variants-skus-inventory-and-product-options"></a>

Squarespace product complexity often concentrates around variants and SKU-level behavior. Source platforms may use variants, options, modifiers, custom fields, grouped products, bundles, or app-controlled product structures that do not map one-to-one into Squarespace.

Validation should answer:

| Product-detail area  | Validation question                                                                                      |
| -------------------- | -------------------------------------------------------------------------------------------------------- |
| Variants             | Do option combinations appear clearly and support the intended purchase choice?                          |
| SKUs                 | Are SKU values preserved where they matter for fulfillment, inventory, reporting, or integrations?       |
| Inventory            | Does stock behavior match the target-store expectation for representative products?                      |
| Pricing              | Are base prices, variant prices, sale prices, or special prices represented acceptably?                  |
| Product images       | Do images support the product and variant choices where expected?                                        |
| Product availability | Are hidden, unavailable, out-of-stock, or limited products handled intentionally?                        |
| Product type         | Are physical, digital, service-style, or subscription-related products interpreted correctly where used? |

The main validation risk is accepting visible product records before confirming that the customer-facing purchase choice still works.

### Validate Categories, Tags, Store Pages, and Navigation <a href="#validate-categories-tags-store-pages-and-navigation" id="validate-categories-tags-store-pages-and-navigation"></a>

Squarespace product discovery can depend on store pages, categories, tags, menus, page sections, product lists, search behavior, and curated navigation. Products should not be validated only by admin presence.

Review top-level store pages, important categories, important tags, product listing pages, menu paths, product search behavior, featured products, homepage product sections, and important customer-entry paths from search, campaigns, or bookmarked links.

A discovery sample passes when a customer can reach representative products through the paths the merchant expects to use after launch.

### Validate Customers, Contacts, Subscribers, and Audience Records <a href="#validate-customers-contacts-subscribers-and-audience-records" id="validate-customers-contacts-subscribers-and-audience-records"></a>

Squarespace may treat audience, contact, customer, subscriber, and commerce-buyer data differently from the Source Platform. Validation should avoid assuming that every source customer group, login account, subscription status, or marketing record becomes the same type of target record.

| Sample type                                                  | What it proves                                                                                                          |
| ------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Standard customer with orders                                | Customer-to-order relationships remain understandable.                                                                  |
| Guest or one-time buyer                                      | Order history remains readable without overstating account continuity.                                                  |
| Customer with multiple addresses                             | Billing and shipping context remains interpretable where supported.                                                     |
| Newsletter or subscriber record                              | Marketing/audience status is handled intentionally.                                                                     |
| Donor, member, or appointment-related contact where relevant | Non-standard Squarespace audience meaning is identified.                                                                |
| Contact with outside-system ID                               | CRM, email, fulfillment, accounting, or channel references are preserved, mapped, excluded, or escalated intentionally. |

Validation should confirm whether the target record is useful in Squarespace, not whether it has the same label as the Source Platform.

### Validate Orders, Transactions, Discounts, and Fulfillment Context <a href="#validate-orders-transactions-discounts-and-fulfillment-context" id="validate-orders-transactions-discounts-and-fulfillment-context"></a>

Historical orders should remain useful after migration. In Squarespace, validation should check whether order history preserves enough context for customer service, finance, fulfillment, and management.

Validate orders that include standard paid orders, unpaid or canceled orders, refunded or partially refunded orders, fulfilled and unfulfilled states, multiple products or product variants, discounts or promo codes, shipping labels, tax values, payment and transaction context, customer notes, digital or subscription-related context, and external-system references where operationally important.

A historical order sample passes when the teams using the order after launch can understand what happened without returning to the source store for ordinary reference.

### Validate Checkout, Shipping, Payment, and Tax Boundaries <a href="#validate-checkout-shipping-payment-and-tax-boundaries" id="validate-checkout-shipping-payment-and-tax-boundaries"></a>

Checkout validation should separate migrated history from target setup. Historical orders may preserve payment labels, shipping labels, tax totals, and transaction context, but live checkout depends on Squarespace settings, payment provider configuration, shipping rules, tax settings, subscription settings, extensions, and target-site configuration.

| Validation track                   | What it proves                                                                                                    |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Historical payment labels          | Past payment context remains readable in migrated orders.                                                         |
| Live payment setup                 | The target Squarespace store can accept payment through configured providers.                                     |
| Historical shipping labels         | Past delivery context remains understandable.                                                                     |
| Live shipping setup                | Shipping rates, zones, pickup/delivery options, or fulfillment settings are configured and tested.                |
| Historical tax values              | Past tax context remains visible where supported.                                                                 |
| Live tax behavior                  | New orders calculate tax using target settings and business requirements.                                         |
| Discounts and promos               | Historical discounts are readable and live promotional behavior is tested separately.                             |
| Subscription or recurring behavior | Subscription-related expectations are validated through target capability, extension behavior, or accepted scope. |

A migration should not be approved for launch merely because historical order data appears acceptable. Live checkout still needs separate target review.

### Validate CMS Pages, Blog Posts, Images, and Content Structure <a href="#validate-cms-pages-blog-posts-images-and-content-structure" id="validate-cms-pages-blog-posts-images-and-content-structure"></a>

Squarespace is often chosen for content-led sites, so content validation can be as important as commerce validation. A store migration may move product and order records while the site still needs page, layout, navigation, image, or blog review before it feels complete.

Validate important CMS Pages, Blog Posts, product landing pages, policy pages, delivery and returns pages, support pages, contact pages, high-value campaign pages, images, embedded media, internal links, page names, menu placement, and content that supports trust, conversion, or customer support.

Content validation should be prioritized by business value. A high-traffic landing page, product guide, or support page deserves more attention than low-value archive content.

### Validate SEO, URLs, Redirects, and Search Entry Paths <a href="#validate-seo-urls-redirects-and-search-entry-paths" id="validate-seo-urls-redirects-and-search-entry-paths"></a>

SEO validation should focus on important customer-entry paths. Squarespace target pages may not preserve every source URL exactly, so high-value URLs, slugs, metadata, and redirects should be reviewed intentionally.

Strong SEO samples include:

* high-traffic product URLs;
* high-traffic category or collection-style URLs;
* important CMS Pages;
* important Blog Posts;
* page titles and descriptions;
* product and page slugs;
* image text where relevant;
* redirect expectations for changed URLs;
* URLs with backlinks, ads, email campaigns, or saved customer links.

A search-sensitive migration passes only when important URLs are migrated, redirected, rebuilt, or accepted as out of scope with a clear decision.

### Validate Extensions, APIs, Webhooks, and Connected Services <a href="#validate-extensions-apis-webhooks-and-connected-services" id="validate-extensions-apis-webhooks-and-connected-services"></a>

Squarespace stores may depend on extensions, Commerce APIs, webhooks, payment providers, shipping services, email tools, CRM systems, fulfillment providers, accounting systems, inventory tools, or other connected services. These areas should be validated as scope outcomes, not assumed to resume automatically.

For each important connected service, classify the outcome:

| Classification | Meaning                                                                                              |
| -------------- | ---------------------------------------------------------------------------------------------------- |
| Migrated       | Required data appears acceptably in Squarespace.                                                     |
| Mapped         | Required references or fields are preserved through supported mapping.                               |
| Reconfigured   | The behavior belongs to target setup rather than migrated data.                                      |
| Rebuilt        | The workflow or feature must be recreated after migration.                                           |
| Excluded       | The data or workflow is intentionally outside migration scope.                                       |
| Escalated      | Custom Service review is needed because the data, identifier, or workflow requires bespoke handling. |

This classification is especially important when external systems depend on product IDs, SKUs, customer IDs, order IDs, transaction references, inventory data, or webhook-triggered workflows.

### Strong Validation Samples for Squarespace <a href="#strong-validation-samples-for-squarespace" id="strong-validation-samples-for-squarespace"></a>

A strong Squarespace validation set should test content, commerce, and connected-system meaning together.

| Sample category  | Strong sample choice                                                                                       | What it proves                                         |
| ---------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| Product          | Product with variants, SKU, images, inventory, category/tag placement, price, and SEO fields.              | Product meaning survives target translation.           |
| Store page       | Product listing or store page with important navigation value.                                             | Product discovery remains usable.                      |
| Customer/contact | Buyer, subscriber, or contact with orders and audience meaning.                                            | Contact and commerce meaning is interpreted correctly. |
| Order            | Order with product variants, payment, shipping, tax, discount, fulfillment, and customer context.          | Historical order context remains readable.             |
| CMS Page         | Important informational, policy, support, or conversion page.                                              | Content continuity supports launch readiness.          |
| Blog Post        | Post with traffic, links, images, or campaign value.                                                       | Blog continuity is intentionally handled.              |
| SEO path         | Product, page, or post URL with search or campaign value.                                                  | Priority URL continuity is testable.                   |
| Connected record | Record with external ID, extension dependency, API use, webhook need, or fulfillment/accounting reference. | Integration expectations are handled intentionally.    |

### What Often Gets Missed <a href="#what-often-gets-missed" id="what-often-gets-missed"></a>

Common Squarespace validation gaps include:

* product records exist but variant or SKU behavior is incomplete;
* products are visible in the admin but not easy to find through store pages, categories, tags, or menus;
* inventory values are present but not reviewed against real selling expectations;
* contacts or subscribers are treated as full customer accounts without checking target meaning;
* order history is accepted without payment, transaction, shipping, tax, discount, or fulfillment context;
* migrated order labels are mistaken for live checkout readiness;
* CMS Pages and Blog Posts are reviewed too late;
* high-value URLs and redirects are not tested before launch;
* extensions, APIs, webhooks, and outside-system identifiers are assumed to continue automatically;
* validation relies on record counts rather than representative business samples.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

Validation should produce a decision for each issue. A finding should not remain vague.

| Result                                    | Meaning                                                                                                              | Next decision                                                                       |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Pass                                      | The sample behaves acceptably in Squarespace.                                                                        | Continue reviewing the next sample group.                                           |
| Pass with configuration note              | Migrated data is acceptable, but target settings, design, extensions, or content work remains.                       | Assign the item to target setup or launch preparation.                              |
| Needs mapping or configuration adjustment | Data exists but does not carry the right target meaning.                                                             | Review Advanced Data Mapping or Advanced Data Configure where supported.            |
| Needs filtering clarification             | Records migrated that should not move, or expected records were not selected.                                        | Review Data Filter Add-on logic where appropriate.                                  |
| Needs Custom Service review               | Custom, extension-owned, API-connected, integration-owned, or unsupported data cannot be handled safely as standard. | Escalate before Full Migration or launch acceptance.                                |
| Not accepted                              | The result does not support business use.                                                                            | Do not approve the migration result until the gap is resolved or formally accepted. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace validation should prove that the migrated site supports the intended commerce and content experience inside a hosted platform. Products, variants, SKUs, inventory, categories, tags, customers, contacts, orders, transactions, CMS Pages, Blog Posts, SEO paths, checkout boundaries, extensions, APIs, webhooks, and connected services should be reviewed as connected parts of the target result.

Use Demo Migration and post-migration review to test the records that carry the most business meaning. If validation shows gaps in product variants, customer/contact interpretation, order context, content continuity, URL handling, extension data, API-connected records, or outside-system identifiers, resolve the issue through target configuration, Add-ons, Custom Service review, or accepted exclusions before approving Full Migration or launch readiness.

### FAQs <a href="#faqs" id="faqs"></a>

**What should I validate first after migrating to Squarespace?**

Start with representative products, variants, SKUs, inventory, store pages, customers or contacts, varied orders, important CMS Pages, Blog Posts, high-value URLs, and records connected to extensions, APIs, webhooks, or outside systems.

**Is matching the product count enough to approve a Squarespace migration?**

No. Product count only confirms presence. Validation should also prove that product variants, SKUs, inventory, categories, tags, images, SEO fields, and customer-facing product discovery remain usable.

**Why should content be validated separately for Squarespace?**

Squarespace is often used as both a website and commerce platform. CMS Pages, Blog Posts, menus, images, landing pages, and SEO paths can affect launch quality even when products and orders migrate correctly.

**Do migrated orders prove that Squarespace checkout is ready?**

No. Migrated order history can preserve past payment, shipping, tax, transaction, and discount context, but live checkout readiness depends on target Squarespace payment, shipping, tax, subscription, and extension settings.

**How should extension or API-connected data be validated?**

Classify each extension, API, webhook, or connected service as migrated, mapped, reconfigured, rebuilt, excluded, or escalated. If the data or identifier needs bespoke handling, Custom Service review should be considered before Full Migration is accepted.
