# ShopWired Pre-Migration Preparation Checklist

Preparing for a migration to ShopWired should begin with the structures that carry business meaning in the source store. Product count, customer count, and order count are useful for estimating scale, but they do not explain how the store actually sells. ShopWired migration readiness depends on product configuration, categories, brands, variations, choices, extras, customer groups, B2B rules, order context, checkout requirements, apps, integrations, content, SEO, and theme expectations.

Preparation should make the migration testable before Full Migration. The goal is to identify which source records can move into standard ShopWired structures, which behavior belongs to target configuration, which records depend on apps or outside systems, and which requirements need Add-ons or Custom Service review.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation should reduce uncertainty before the migration path is finalized. For ShopWired, this means identifying the source-store structures that must be represented inside a hosted platform environment.

A useful preparation process should clarify:

* which products, customers, orders, categories, brands, and content should migrate;
* how source variants, modifiers, product options, add-ons, personalization fields, and bundles should be interpreted;
* whether B2B or trade behavior is ordinary customer data, target configuration, app-supported behavior, or custom scope;
* which order samples prove historical readability;
* which checkout, delivery, payment, and tax settings belong to target setup rather than migrated data;
* which apps, APIs, webhooks, marketplaces, and outside systems affect migration scope;
* which content pages, URLs, metadata, menus, and theme-controlled areas matter most;
* whether Standard Service, Add-ons, Managed Service, or Custom Service review is the safer path.

### 1. Confirm the Target ShopWired Store Context <a href="#id-1-confirm-the-target-shopwired-store-context" id="id-1-confirm-the-target-shopwired-store-context"></a>

Before migration, confirm the intended target ShopWired setup. The target store context affects what data structures, apps, and settings can be used after migration.

Prepare the following information:

| Evidence to gather                            | Why it matters                                                                                             |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Target ShopWired plan and enabled features    | Determines which platform capabilities, B2B features, apps, and settings are available.                    |
| Target admin access and permissions           | Ensures the migration can be reviewed and configured by the right people.                                  |
| Installed or planned ShopWired apps           | Helps separate migrated data from app configuration or app-owned behavior.                                 |
| Theme and design expectations                 | Clarifies whether storefront presentation is expected to migrate, be rebuilt, or be configured separately. |
| Payment, delivery, and tax setup requirements | Prevents historical order labels from being mistaken for live checkout readiness.                          |
| Channel and integration requirements          | Identifies external systems that may need ID preservation, mapping, or reconfiguration.                    |

ShopWired is a hosted platform, so preparation should focus on how the target store will use supported structures, settings, apps, and integration surfaces.

### 2. Prepare Product and Catalog Samples <a href="#id-2-prepare-product-and-catalog-samples" id="id-2-prepare-product-and-catalog-samples"></a>

Product preparation should include more than a list of product names and prices. ShopWired product meaning can involve variations, choices, extras, bundles, digital products, categories, brands, images, stock behavior, delivery settings, tax settings, product visibility, and SEO fields.

Prepare product samples that include:

* simple products with ordinary price, description, image, and category assignment;
* products with variations such as size, color, or material;
* products with choices, extras, personalization fields, or optional upgrades;
* products with bundles, kits, or grouped buying behavior;
* digital products or products with special fulfillment assumptions;
* products assigned to multiple categories;
* products connected to brands or manufacturer-style browsing;
* products with stock-sensitive options or external inventory references;
* products with special delivery, tax, or pricing behavior;
* products with important SEO fields, page names, or historical URLs.

The sample set should include products that expose complexity. If the Demo Migration includes only simple products, it may not reveal whether ShopWired can represent the store’s real product model.

### 3. Map Categories, Brands, Navigation, and Discovery <a href="#id-3-map-categories-brands-navigation-and-discovery" id="id-3-map-categories-brands-navigation-and-discovery"></a>

Product discovery should be prepared as a separate review area. A product can migrate correctly as a record but still be difficult to find if categories, brands, filters, search, menus, or channel visibility are incomplete.

Prepare:

| Area                       | Preparation task                                                                                                            |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Category hierarchy         | Document top-level categories, subcategories, hidden categories, landing categories, and multi-category product assignment. |
| Brand structure            | Identify whether brands affect browsing, SEO, filtering, or merchandising.                                                  |
| Product filters and search | List the product characteristics customers use to narrow or compare products.                                               |
| Menus and landing pages    | Identify navigation paths that are important to customer journeys.                                                          |
| Channel visibility         | Confirm whether products should appear differently across channels or connected sales surfaces.                             |

Review product discovery from a shopper’s perspective. The target store should be judged by whether customers can find representative products, not only by whether those products exist in the admin area.

### 4. Prepare Customer, B2B, and Trade Samples <a href="#id-4-prepare-customer-b2b-and-trade-samples" id="id-4-prepare-customer-b2b-and-trade-samples"></a>

Customer preparation should identify account structures that affect pricing, visibility, checkout, quotes, approval, or order handling. ShopWired can support customer and B2B use cases, but the migration plan must separate customer records from target rules and app-supported behavior.

Prepare customer samples that include:

* ordinary registered customers;
* guest customers with orders;
* customers with multiple billing or delivery addresses;
* customers assigned to groups;
* trade or wholesale customers;
* quote-related customers if quotes are used;
* customers with negotiated pricing or account terms;
* customers with special payment, delivery, tax, or visibility behavior;
* customers connected to external CRM, ERP, accounting, marketplace, or fulfillment systems.

For each B2B or trade sample, clarify whether the behavior is a customer record, a customer group setting, a target configuration, an app-supported workflow, or a custom requirement.

### 5. Prepare Order, Quote, and Subscription Samples <a href="#id-5-prepare-order-quote-and-subscription-samples" id="id-5-prepare-order-quote-and-subscription-samples"></a>

Historical order migration should preserve operational readability. The best order samples show how the business actually uses order history after launch.

Prepare orders that include:

* paid and unpaid states;
* fulfilled and unfulfilled states;
* refunded, canceled, or partially fulfilled orders;
* discounts, vouchers, credits, or manual adjustments;
* different delivery and payment methods;
* tax-sensitive totals;
* customer and admin notes;
* B2B or trade orders;
* quote-related orders where relevant;
* subscription-like or recurring-order context if used;
* orders connected to external systems or sales channels.

The purpose is to confirm whether migrated historical orders remain useful for customer service, finance, fulfillment, and management. Live checkout should still be configured and tested separately.

### 6. Separate Historical Checkout Data from Target Checkout Setup <a href="#id-6-separate-historical-checkout-data-from-target-checkout-setup" id="id-6-separate-historical-checkout-data-from-target-checkout-setup"></a>

ShopWired checkout readiness depends on target settings. Preparing historical order samples is not the same as preparing live checkout configuration.

Prepare separate notes for:

| Checkout area                    | Preparation question                                                                                      |
| -------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Payment methods                  | Which historical labels should remain readable, and which live gateways must be configured?               |
| Delivery methods                 | Which past delivery labels should remain readable, and which live delivery rates or zones must be set up? |
| Tax rules                        | Which historical tax values should remain readable, and which target tax settings must be configured?     |
| Customer-group checkout behavior | Do trade customers, B2B accounts, or restricted buyers need different checkout rules?                     |
| Custom checkout fields           | Are fields ordinary order notes, customer data, app-owned records, or custom scope?                       |
| Quotes or account terms          | Are quote/payment-term workflows target configuration, app-supported behavior, or custom requirement?     |

This separation prevents a common launch issue: order history looks acceptable, but the target store is not ready to accept new orders.

### 7. Inventory Apps, APIs, Webhooks, and Outside Systems <a href="#id-7-inventory-apps-apis-webhooks-and-outside-systems" id="id-7-inventory-apps-apis-webhooks-and-outside-systems"></a>

Apps and integrations should be reviewed before migration scope is finalized. ShopWired stores may depend on apps, API connections, webhooks, marketplaces, accounting tools, fulfillment systems, inventory systems, payment providers, email tools, CRM systems, or reporting tools.

Prepare an integration inventory:

| Integration area                                  | What to confirm                                                                                |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Apps                                              | Whether the app owns data, controls display, changes checkout, or only provides configuration. |
| API connections                                   | Whether product, customer, order, or inventory IDs need to remain traceable.                   |
| Webhooks                                          | Whether workflows must resume after migration or be rebuilt.                                   |
| Marketplaces and feeds                            | Whether channel-specific product fields, stock, pricing, or identifiers matter.                |
| Accounting, ERP, CRM, POS, or fulfillment systems | Whether outside-system references need mapping, preservation, or Custom Service review.        |
| Email, review, loyalty, or marketing tools        | Whether customer, order, or consent-related records are part of migration scope.               |

Classify each integration as reconfigured, rebuilt, mapped, excluded, or escalated for Custom Service review.

### 8. Prepare SEO, Content, and Theme Evidence <a href="#id-8-prepare-seo-content-and-theme-evidence" id="id-8-prepare-seo-content-and-theme-evidence"></a>

ShopWired migration preparation should include the pages and storefront elements that affect launch quality. Product data can migrate while the store still needs content, menus, metadata, theme presentation, or redirect planning.

Prepare:

* high-value product URLs;
* high-value category and brand URLs;
* CMS Pages and landing pages;
* blog or content pages where relevant;
* menus and navigation paths;
* metadata for important pages;
* image alt text where important;
* redirect expectations;
* banners, homepage content, and campaign pages;
* theme-controlled sections that affect product or category presentation;
* B2B information pages, delivery policies, returns pages, or support pages.

Prioritize pages that affect search traffic, customer trust, conversion, support, or B2B account use.

### 9. Choose Demo Migration Samples Deliberately <a href="#id-9-choose-demo-migration-samples-deliberately" id="id-9-choose-demo-migration-samples-deliberately"></a>

Demo Migration should test risk, not hide it. A strong ShopWired sample set should include records that represent the store’s real business model.

| Sample type                  | Why it matters                                                                             |
| ---------------------------- | ------------------------------------------------------------------------------------------ |
| Complex product              | Tests variations, choices, extras, bundles, images, stock, delivery, tax, and SEO fields.  |
| Category or brand path       | Tests product discovery and storefront navigation.                                         |
| B2B or trade customer        | Tests customer group, pricing, quote, approval, and account behavior expectations.         |
| Varied order                 | Tests payment, delivery, tax, fulfillment, notes, discounts, and historical readability.   |
| Content or SEO page          | Tests CMS, metadata, page-name, navigation, and redirect planning.                         |
| App-dependent record         | Tests whether app-owned data is included, excluded, reconfigured, or escalated.            |
| Integration-sensitive record | Tests external IDs, marketplace/channel fields, API dependencies, or workflow assumptions. |

If a sample does not include the source store’s hardest cases, Demo Migration may give a false sense of readiness.

### 10. Identify Add-on and Custom Service Signals Early <a href="#id-10-identify-add-on-and-custom-service-signals-early" id="id-10-identify-add-on-and-custom-service-signals-early"></a>

Some ShopWired migrations fit standard service capability. Others reveal filtering, mapping, configuration, app, custom, or integration requirements that should be handled before Full Migration.

Consider Add-ons when the need stays within supported service capability:

* use the Data Filter Add-on when only selected eligible records should migrate;
* use Advanced Data Mapping when supported source and target fields need controlled mapping;
* use Advanced Data Configure when migrated data values need supported modification before reaching the target store.

Custom Service review should be considered when:

* the Source Platform or Target Platform is Custom Platform;
* source product configuration requires non-standard transformation;
* app-owned data must be migrated or preserved;
* outside-system identifiers must remain traceable;
* B2B, quote, account-term, checkout, delivery, payment, or tax behavior is custom;
* API/webhook workflows need migration-aware handling;
* tailored migration behavior goes beyond Standard Add-on capability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired preparation should make the migration outcome testable before Full Migration begins. Products, variations, choices, extras, B2B customers, orders, checkout rules, apps, integrations, SEO, content, and themes should be prepared as connected parts of the target store, not isolated records.

Before proceeding, build a Demo Migration sample set that reflects the store’s real complexity. If the sample reveals unsupported app data, custom B2B logic, integration identifiers, product-choice transformation needs, or checkout fields that do not fit standard service capability, resolve the requirement through configuration, Add-ons, or Custom Service review before continuing.

### FAQs <a href="#faqs" id="faqs"></a>

**What should I prepare first for a ShopWired migration?**

Start with the target ShopWired context, product structures, B2B/customer group rules, order samples, checkout requirements, app inventory, integrations, and high-value content or URLs. These areas determine whether the migration is straightforward or needs deeper review.

**Should every product be included in Demo Migration?**

No. Demo Migration should use representative samples. Include products with variations, choices, extras, bundles, stock-sensitive behavior, delivery settings, tax behavior, and SEO fields so the sample exposes real complexity.

**Why are B2B customer samples important?**

B2B customers may depend on trade pricing, quotes, approval, account terms, payment access, delivery rules, tax treatment, or visibility settings. Those behaviors may require target configuration, app support, or Custom Service review.

**Do I need to prepare apps and integrations before migration?**

Yes. Apps, API connections, webhooks, marketplaces, accounting systems, fulfillment tools, and outside systems may own data or identifiers that standard migration does not automatically include.

**When should I request Custom Service review before migrating to ShopWired?**

Request Custom Service review when the migration involves Custom Platform data, app-owned records, outside-system identifiers, custom B2B rules, custom checkout fields, non-standard product transformation, or tailored behavior beyond Standard Add-on capability.
