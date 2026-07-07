# ShopWired Pre-Migration Preparation Checklist

ShopWired migration preparation should turn the source store into a set of testable business assumptions. Product count, customer count, and order count help estimate scale, but they do not explain whether the store is ready to operate on ShopWired after migration. Preparation needs to show how products are bought, how customer accounts behave, how orders remain readable, how B2B rules should work, and which settings, apps, or external systems need work outside data transfer.

A strong preparation process also avoids a common misunderstanding: migrated records do not automatically recreate the source store’s selling logic. ShopWired can support structured catalog, customer, checkout, trade, content, SEO, app, and API workflows, but the merchant must confirm which source behavior belongs to migrated data, target setup, an Add-on, or Custom Service review. The goal is not to gather every possible detail. The goal is to gather the right evidence before Demo Migration and Full Migration decisions are made.

### What ShopWired Preparation Should Prove <a href="#what-shopwired-preparation-should-prove" id="what-shopwired-preparation-should-prove"></a>

Preparation should prove that the target store can represent the business model, not simply receive records. For ShopWired, the most important evidence usually sits in product option structure, category and brand navigation, customer identity, B2B or trade account behavior, historical order readability, checkout configuration, app dependency, and SEO continuity.

| Preparation area           | What it should prove                                                                                                        | Why it matters                                                                   |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Catalog structure          | Products, categories, brands, images, descriptions, pricing, and stock can be interpreted correctly.                        | Catalog records are the foundation for storefront discovery and checkout.        |
| Product buying logic       | Variations, choices, extras, bundles, digital products, pre-orders, or subscriptions are classified correctly.              | Similar-looking product options can require different handling in ShopWired.     |
| Customer and trade records | Customer identity, customer types, addresses, notes, custom fields, trade accounts, and order relationships are understood. | Customer records and trade behavior affect service, pricing, and account access. |
| Historical orders          | Past orders remain useful for support, finance, fulfillment, refunds, and management.                                       | Order history is operational evidence, not only a record archive.                |
| Target setup               | Payments, delivery, tax, email, regional, theme, and account settings are separated from migrated data.                     | A correct migration can still fail launch if target settings are not ready.      |
| Integrations               | Apps, API workflows, feeds, webhooks, and outside systems are classified before scope is finalized.                         | External dependencies often decide whether Custom Service review is needed.      |
| SEO and content            | Priority URLs, metadata, CMS Pages, blog posts, menus, redirects, and landing pages are documented.                         | Storefront continuity depends on both migrated data and target presentation.     |

This preparation evidence should be visible before the merchant relies on Demo Migration results. Demo Migration should test the difficult cases, not only the clean records.

### 1. Confirm the Target Store Context <a href="#id-1-confirm-the-target-store-context" id="id-1-confirm-the-target-store-context"></a>

Start by confirming how the target ShopWired store is expected to operate. The target plan, enabled features, app stack, theme direction, B2B requirements, checkout configuration, and integration expectations influence what can be migrated directly and what must be configured separately.

| Target context to confirm           | Preparation question                                                                | Output needed before migration                                         |
| ----------------------------------- | ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| ShopWired plan and enabled features | Which catalog, B2B, app, checkout, and API capabilities will the target store use?  | A list of required features and any features that are not yet enabled. |
| Admin access and permissions        | Who can review products, customers, orders, apps, checkout, SEO, and settings?      | Named owners for validation and configuration.                         |
| Theme and page expectations         | Which storefront areas are data-driven and which are theme or content rebuild work? | A separation of migration scope from design implementation.            |
| Payment, delivery, and tax setup    | Which settings must be configured before test orders can prove launch readiness?    | A launch-readiness checklist independent from order-history migration. |
| App and integration stack           | Which apps, feeds, API connections, or external systems must keep working?          | A dependency map with handling decisions.                              |

The key output is a realistic operating context. Without it, preparation can become a record-count exercise and miss the decisions that determine launch quality.

### 2. Prepare Product Samples by Selling Behavior <a href="#id-2-prepare-product-samples-by-selling-behavior" id="id-2-prepare-product-samples-by-selling-behavior"></a>

ShopWired product preparation should start with how products are purchased. A source catalog may contain simple items, variant-heavy products, personalization fields, add-ons, bundles, digital goods, pre-order items, subscription-like products, or products with special delivery and tax behavior. These should not be grouped together as ordinary products just because they all appear in the source catalog.

A useful product sample set should include records that expose each meaningful selling pattern:

| Product sample                         | What to inspect                                                                                                        | Why it should be sampled                                                             |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Simple product                         | Name, description, images, price, stock, category, brand, and SEO fields.                                              | Establishes baseline product migration quality.                                      |
| Variation product                      | Option names, option values, variation combinations, SKU, stock, image, weight, price, GTIN, MPN, and tax differences. | Proves whether variant-level attributes survive with usable meaning.                 |
| Product with choices or extras         | Optional add-ons, personalization, file upload, text input, gift wrapping, or upgrade fields.                          | Prevents buyer-option behavior from being mistaken for standard variation data.      |
| Bundle or kit                          | Component logic, grouped buying behavior, stock assumptions, and presentation.                                         | Clarifies whether the result is supported, app-based, manual setup, or custom scope. |
| Digital or special fulfillment product | Download, fulfillment, delivery, availability, or access expectation.                                                  | Identifies non-standard delivery assumptions before launch.                          |
| SEO-sensitive product                  | Existing URL, page title, metadata, image naming, and redirect requirement.                                            | Protects high-value product search traffic.                                          |

The sample set should include the hardest products, not only the most common products. If a catalog depends on complex combinations or option behavior, those records must appear in Demo Migration samples before the migration path is trusted.

### 3. Map Categories, Brands, Filters, and Discovery Paths <a href="#id-3-map-categories-brands-filters-and-discovery-paths" id="id-3-map-categories-brands-filters-and-discovery-paths"></a>

Product discovery needs its own preparation work. A product can migrate successfully as a record but still become difficult to buy if the target category, brand, filter, search, or menu structure is incomplete. ShopWired preparation should document how shoppers find products and how administrators merchandise them.

Prepare a discovery map that includes:

* top-level categories and subcategories;
* hidden, seasonal, or campaign-specific categories;
* brand pages or manufacturer-style browsing;
* products assigned to more than one category;
* product filters or search attributes used to narrow decisions;
* important menus, landing pages, and collection-style paths;
* redirects for high-value category, brand, or product URLs.

| Discovery item          | Evidence to collect                                                          | Validation question                                                 |
| ----------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Category hierarchy      | Current tree, product assignments, hidden areas, and priority landing pages. | Can shoppers reach representative products through expected paths?  |
| Brand structure         | Brand names, brand URLs, metadata, and browsing purpose.                     | Are brands only labels, or do they drive discovery and SEO?         |
| Filters and search      | Attributes customers use to narrow product choices.                          | Will shoppers still find products when catalog data is reorganized? |
| Menus and landing pages | Navigation paths, promotional pages, policy pages, and buying guides.        | Does the target storefront preserve important customer journeys?    |

This work should be reviewed from the shopper’s perspective. Admin records can look correct while storefront discovery is still weak.

### 4. Prepare Customer, B2B, and Trade Evidence <a href="#id-4-prepare-customer-b2b-and-trade-evidence" id="id-4-prepare-customer-b2b-and-trade-evidence"></a>

Customer preparation should identify account meaning, not just customer volume. ShopWired customer records can be created through account registration, guest checkout, admin-created orders, or admin-created customer accounts. Customer identity and order relationships depend heavily on email behavior, so duplicate, shared, changed, or inconsistent emails should be reviewed before migration.

Prepare samples for:

* ordinary registered customers;
* guest customers with historical orders;
* customers with multiple addresses;
* customers with customer custom fields;
* customers with internal notes or marketing preferences;
* customers connected to external CRM, ERP, accounting, or support systems;
* customers whose order history depends on email consistency;
* trade or wholesale customers;
* customer accounts with special pricing, restricted access, quote behavior, or payment terms.

| Customer scenario                       | What to clarify                                                                                          | Likely handling implication                                          |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Guest buyer later creates an account    | Whether the email address links past orders to the account.                                              | Review customer identity and order visibility.                       |
| Duplicate customer emails in the source | Which record should represent the buyer.                                                                 | Clean source data or define merge expectations.                      |
| Trade customer                          | Whether the behavior is customer data, target configuration, app-supported trade logic, or custom scope. | Confirm B2B setup before launch.                                     |
| Custom customer fields                  | Whether fields are supported, app-owned, or externally referenced.                                       | Use mapping, configuration, or Custom Service review as appropriate. |

For trade and B2B cases, prepare exact examples. A general statement such as “we have wholesale customers” is not enough. The preparation should show which customers need different prices, different visibility, different payment terms, different delivery rules, quote handling, or approval behavior.

### 5. Prepare Historical Orders as Operational Evidence <a href="#id-5-prepare-historical-orders-as-operational-evidence" id="id-5-prepare-historical-orders-as-operational-evidence"></a>

Historical order migration should keep past transactions readable for the teams that use them. A useful order sample set includes different payment states, delivery methods, discounts, refunds, cancellations, fulfillment states, notes, taxes, B2B orders, quote-related orders, and external-system references.

| Order sample                | What to inspect                                                                                 | Why it matters                                                            |
| --------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Standard paid order         | Products, customer, address, payment label, delivery label, totals, tax, and fulfillment state. | Confirms baseline historical readability.                                 |
| Refunded or canceled order  | Refund labels, cancellation reason, totals, and customer-service context.                       | Prevents financial history from becoming unclear.                         |
| Discounted order            | Voucher, offer, credit, manual discount, or adjustment information.                             | Confirms promotion history remains interpretable.                         |
| B2B or trade order          | Account terms, trade pricing, quote relationship, delivery expectations, and notes.             | Preserves commercial context for account management.                      |
| Integration-sensitive order | ERP, accounting, fulfillment, marketplace, or POS reference.                                    | Determines whether external IDs require mapping or Custom Service review. |

Live checkout should not be judged from historical order samples alone. Historical orders show what happened before; payment gateways, delivery rates, taxes, checkout rules, and transactional emails still need target configuration and testing.

### 6. Separate Migrated Data from Target Configuration <a href="#id-6-separate-migrated-data-from-target-configuration" id="id-6-separate-migrated-data-from-target-configuration"></a>

A strong ShopWired preparation checklist should clearly separate what migrates from what must be set up inside the target store. This prevents launch confusion when record migration succeeds but checkout, tax, delivery, email, or customer-account behavior is not ready.

| Area                    | Migrated-data question                                         | Target-configuration question                                                                    |
| ----------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Payments                | Should historical payment names and statuses remain readable?  | Which live payment gateways must be configured and tested?                                       |
| Delivery                | Should past delivery labels remain readable on orders?         | Which delivery zones, rates, inclusions, exclusions, or collection options must be set up?       |
| Tax and VAT             | Should historical tax totals and labels remain understandable? | Which target VAT, sales tax, tax zones, or custom rates are required?                            |
| Customer accounts       | Should customer records and order history migrate?             | Which account pages, passwords, login flow, and theme settings must be tested?                   |
| Trade rules             | Which trade customers and order history must migrate?          | Which trade pricing, restricted categories, account terms, or approval rules must be configured? |
| Email and notifications | Which customer and order records should exist?                 | Which transactional emails, templates, and sender settings must be configured?                   |

If this separation is not clear, the merchant may misread a successful migration as a complete launch setup.

### 7. Inventory Apps, APIs, Webhooks, and Outside Systems <a href="#id-7-inventory-apps-apis-webhooks-and-outside-systems" id="id-7-inventory-apps-apis-webhooks-and-outside-systems"></a>

ShopWired preparation should include an integration inventory before service scope is finalized. Apps, custom fields, product feeds, marketplace connections, accounting tools, CRM systems, fulfillment tools, stock systems, analytics, and API workflows can all affect what the migration needs to preserve.

| Dependency                             | Questions to ask                                                                                       | Preparation output                                                     |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| ShopWired apps                         | Does the app create data, display data, change checkout, affect stock, or only configure presentation? | App handling decision: reconfigure, exclude, map, sample, or escalate. |
| API workflows                          | Which product, customer, order, stock, or category records are read or updated externally?             | Identifier and endpoint dependency notes.                              |
| Webhooks                               | Which workflows must continue after migration?                                                         | Rebuild or reactivation plan.                                          |
| Marketplace and feeds                  | Which channel-specific fields, stock, prices, or identifiers matter?                                   | Field and ID preservation requirements.                                |
| ERP, POS, accounting, CRM, fulfillment | Which systems rely on historical IDs, order numbers, SKUs, customer emails, or custom fields?          | Mapping or Custom Service review signals.                              |

The inventory should classify each dependency as supported configuration, Add-on scope, Custom Service review, manual rebuild, or post-migration setup. This prevents app-owned data from being assumed to migrate as standard store data.

### 8. Prepare SEO, Content, and Storefront Evidence <a href="#id-8-prepare-seo-content-and-storefront-evidence" id="id-8-prepare-seo-content-and-storefront-evidence"></a>

ShopWired preparation should cover more than catalog records. CMS Pages, blog posts, menus, landing pages, redirects, metadata, product URLs, category URLs, brand URLs, images, downloadable files, and theme-controlled content can affect traffic, trust, and conversion.

Prepare evidence for:

* priority product, category, and brand URLs;
* CMS Pages, policy pages, landing pages, and buying guides;
* blog posts or content assets that drive search traffic;
* menus and link lists;
* metadata for important pages;
* image files and alt text where important;
* redirects for discontinued or changed URLs;
* campaign pages, homepage sections, banners, and promotional content;
* account, delivery, returns, trade, and support pages;
* page elements that depend on theme settings rather than migrated records.

A practical approach is to rank content by business risk. High-traffic, high-conversion, legal, customer-service, and B2B pages should be prepared first because they affect launch confidence more than low-value archived pages.

### 9. Build the Demo Migration Sample Set Deliberately <a href="#id-9-build-the-demo-migration-sample-set-deliberately" id="id-9-build-the-demo-migration-sample-set-deliberately"></a>

Demo Migration should be designed to answer readiness questions. It should include representative records that expose catalog, customer, order, SEO, app, and integration complexity.

| Demo sample                                      | What it should prove                                                                                              |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| Simple product                                   | Baseline product fields, images, category, brand, price, and stock.                                               |
| Variation-heavy product                          | Whether options, combinations, SKUs, stock, images, weight, GTIN, MPN, and tax behavior remain usable.            |
| Product with choices, extras, or personalization | Whether buyer-facing option behavior needs configuration, Add-on handling, or Custom Service review.              |
| B2B or trade customer                            | Whether customer identity, account role, pricing expectation, and order visibility are clear.                     |
| Complex order                                    | Whether discounts, refunds, delivery labels, payment labels, tax, notes, and fulfillment context remain readable. |
| Priority content or URL                          | Whether CMS, blog, page metadata, menu, and redirect expectations are realistic.                                  |
| App or integration-dependent record              | Whether external IDs, custom fields, app-owned records, or API workflows need special handling.                   |

A weak sample set produces weak confidence. If Demo Migration proves only simple records, it does not prove the real store is ready for Full Migration.

### 10. Identify Add-on, Custom Service, and Timing Signals Early <a href="#id-10-identify-add-on-custom-service-and-timing-signals-early" id="id-10-identify-add-on-custom-service-and-timing-signals-early"></a>

Preparation should also classify service-path signals before Full Migration. Add-ons are appropriate when supported migration behavior needs filtering, mapping, or configuration. Custom Service should be reviewed when unsupported, custom, app-owned, external-system, or bespoke transformation needs affect the result.

| Signal                                                  | Likely path to review | Example                                                                                                  |
| ------------------------------------------------------- | --------------------- | -------------------------------------------------------------------------------------------------------- |
| Only selected eligible records should migrate.          | Add-on                | Migrate specific products, customers, orders, or date ranges.                                            |
| Supported fields need controlled mapping.               | Add-on                | Map customer groups, product attributes, or status values where supported.                               |
| Supported values need configured transformation.        | Add-on                | Adjust supported field values before they reach the target store.                                        |
| App-owned or custom product behavior must be preserved. | Custom Service        | Personalization logic, bundle behavior, or app-created options cannot be represented as standard fields. |
| External IDs must remain operational.                   | Custom Service        | ERP, POS, accounting, fulfillment, or marketplace systems rely on source identifiers.                    |
| The source or target environment is Custom Platform.    | Custom Service        | Data structures must be inspected before mapping can be trusted.                                         |

Later migration timing should also be prepared. If the source store remains active after Demo Migration, the merchant should decide whether they may need to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration. Each action should have an owner, timing rule, and validation set.

### Practical Preparation Checklist <a href="#practical-preparation-checklist" id="practical-preparation-checklist"></a>

Use this checklist after gathering evidence. It is not a replacement for detailed review, but it helps confirm whether the migration is ready to move into execution.

| Readiness question                            | Pass condition                                                                                                                 |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Have complex products been sampled?           | Variations, choices, extras, bundles, stock, pricing, images, tax, and SEO-sensitive products are represented.                 |
| Is product discovery mapped?                  | Categories, brands, filters, search, menus, and priority landing pages are documented.                                         |
| Are B2B and trade cases clear?                | Trade customers, pricing expectations, account terms, quotes, restricted access, and special checkout behavior are classified. |
| Are historical orders useful after migration? | Representative orders prove payment, delivery, tax, discount, refund, fulfillment, note, and external-system readability.      |
| Is target setup separated from migrated data? | Payments, delivery, tax, emails, account pages, trade settings, and theme areas have target-side owners.                       |
| Are apps and integrations classified?         | Each dependency is marked as reconfigure, map, exclude, rebuild, Add-on, or Custom Service review.                             |
| Is Demo Migration designed to test risk?      | The sample set includes the records most likely to reveal mismatch.                                                            |
| Is launch timing planned?                     | Later migration actions and validation responsibilities are clear.                                                             |

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired migration preparation should create evidence, not just a task list. The merchant should know which records are expected to migrate, which target settings must be configured separately, which product and customer structures need special attention, and which app or integration dependencies affect scope.

A strong preparation process makes Demo Migration useful. It gives Next-Cart and the merchant the right samples to test product options, B2B rules, customer identity, order readability, SEO continuity, content handling, Add-ons, Custom Service needs, Entity Points planning, and launch timing before Full Migration decisions become difficult to reverse.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a ShopWired migration?**

Start with the records and settings that carry business meaning: complex products, customer and trade scenarios, historical orders, checkout requirements, app dependencies, integrations, priority URLs, and Demo Migration samples.

**Should payment, delivery, and tax settings be treated as migrated data?**

No. Historical payment, delivery, and tax labels may need to remain readable on past orders, but live payment gateways, delivery rates, tax rules, and related checkout settings must be configured and tested in ShopWired.

**How should B2B or trade customers be prepared?**

Prepare exact customer and order examples. Clarify whether trade behavior is ordinary customer data, target configuration, app-supported behavior, Add-on scope, or Custom Service scope.

**How should Demo Migration samples be chosen?**

Choose samples that expose risk: variation-heavy products, personalization or extras, B2B customers, complex orders, priority URLs, app-dependent records, and integration-sensitive data. Simple samples alone are not enough.
