# Wix Pre-Migration Preparation Checklist

Wix migration preparation should make the target store testable before the migration result is accepted. Because Wix combines hosted website building, Wix Stores commerce, apps, member features, content tools, checkout settings, payments, shipping, tax, SEO, and optional Velo or API work, preparation should cover more than product, customer, and order counts.

The goal is to identify what must become migrated data, what must be configured in Wix, what belongs to apps or external systems, and what should be reviewed through Demo Migration before Full Migration. A prepared Wix migration is easier to estimate, easier to validate, and less likely to expose late launch gaps.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Preparation should create a clear view of how the current store should operate inside Wix after migration. The most useful preparation work connects source records to real target outcomes: products must be sellable, options and variants must behave as expected, collections must support browsing, customers and members must remain understandable, orders must be readable, and content or SEO changes must be intentional.

For Wix, preparation should separate three types of work:

| Preparation area             | What it means for Wix                                                                                                     | Why it matters                                                                                 |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Migrated records             | Products, customers, orders, CMS Pages, Blog Posts, and eligible commerce data that should move into the Target Platform. | These records form the measurable migration scope and should be sampled before Full Migration. |
| Target configuration         | Wix plan, store setup, checkout, payments, shipping, tax, domains, site menus, collections, filters, and app settings.    | Configuration affects whether migrated records can be used correctly after launch.             |
| Custom or connected behavior | Velo logic, APIs, custom app data, external systems, third-party apps, custom fields, and unsupported source behavior.    | These items can require mapping, accepted exclusions, or Custom Service review.                |

### 1. Confirm the Target Wix Site Context <a href="#id-1-confirm-the-target-wix-site-context" id="id-1-confirm-the-target-wix-site-context"></a>

Before preparing data samples, confirm the target Wix environment that will receive the migration. Wix behavior can depend on the selected site type, installed apps, enabled commerce features, payment and shipping setup, domain planning, and whether custom code or external integrations are expected.

| Target context                         | What to confirm                                                                                                                                                     | Migration impact                                                                                        |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Wix site and commerce setup            | Whether the target site uses Wix Stores and which related business apps are needed.                                                                                 | Store data should be reviewed against the actual Wix commerce environment, not a generic website shell. |
| Product and store feature availability | Whether the target setup supports the needed product types, variants, inventory behavior, discounts, subscriptions, bookings, memberships, or other selling models. | Feature mismatch can turn a normal migration into configuration, app, or Custom Service work.           |
| Checkout setup                         | Payment methods, Wix Payments or external payment providers, tax, shipping, pickup, delivery, and checkout rules.                                                   | Historical order labels do not automatically configure live checkout behavior.                          |
| Content and design context             | Template, site structure, navigation, product pages, CMS Pages, Blog Posts, landing pages, and mobile expectations.                                                 | A data migration can pass technically while storefront continuity remains incomplete.                   |
| App and Velo context                   | Installed apps, custom code, API usage, automations, external systems, and data collections.                                                                        | App-owned or custom behavior should be identified before scope is finalized.                            |
| SEO and domain context                 | Domains, URL slugs, redirects, metadata, priority product/category/page URLs, and search visibility needs.                                                          | URL and metadata planning reduces avoidable launch disruption.                                          |

### 2. Prepare Product and Catalog Samples <a href="#id-2-prepare-product-and-catalog-samples" id="id-2-prepare-product-and-catalog-samples"></a>

Product samples should represent how the store sells, not only how many products exist. Wix Stores may need to interpret product names, descriptions, images, pricing, inventory, SKUs, collections, product options, choices, variants, modifiers, ribbons, visibility, discounts, subscriptions, and shipping-related behavior.

Prepare examples from the most important product patterns:

| Product sample                     | What to include                                                                                         | Why it matters                                                                              |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Simple products                    | Title, description, price, images, SKU, inventory, collection, visibility, and SEO values.              | Confirms baseline product readability and storefront placement.                             |
| Variant products                   | Options, choices, variants, variant pricing, SKUs, stock, images, and unavailable combinations.         | Shows whether buying choices are represented correctly in Wix.                              |
| Products with modifiers or add-ons | Any source behavior that changes price, personalization, packaging, service choice, or product details. | Some source modifiers may not map cleanly to standard Wix product behavior.                 |
| Digital or non-physical products   | Delivery expectation, product type, files, access method, or fulfillment handling.                      | Confirms whether the selling model belongs in Wix Stores, another Wix app, or custom scope. |
| Subscription or recurring products | Subscription terms, billing expectation, product association, and customer-facing meaning.              | Recurring commerce should be reviewed separately from ordinary product migration.           |
| High-value products                | Best sellers, complex bundles, SEO-important products, or products tied to ads or marketplaces.         | These records should be included in Demo Migration review.                                  |

Product samples should also include source fields that may not have an obvious Wix destination. Custom fields, option rules, hidden attributes, product badges, marketplace IDs, personalization notes, supplier references, and app-specific values should be listed separately instead of assumed to migrate as ordinary product data.

### 3. Prepare Collections, Categories, Filters, and Storefront Discovery Evidence <a href="#id-3-prepare-collections-categories-filters-and-storefront-discovery-evidence" id="id-3-prepare-collections-categories-filters-and-storefront-discovery-evidence"></a>

Wix storefront discovery depends on how products are organized and displayed. Source categories may become Wix collections, menus, product galleries, filters, landing pages, or other storefront structures. The preparation work should show how shoppers are expected to browse and find products after launch.

| Discovery element    | Evidence to prepare                                                                             | What to check in Wix                                                                            |
| -------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Source categories    | Category names, hierarchy, product assignments, URL importance, and visibility rules.           | Whether each structure should become a collection, menu path, page section, or accepted change. |
| Product filters      | Filter values, attributes, sizes, colors, brands, prices, availability, or custom filter logic. | Whether Wix filtering supports the expected browsing behavior.                                  |
| Menus and navigation | Main menu, footer menu, product listing links, landing pages, and promotional paths.            | Whether shoppers can reach key products and collections after migration.                        |
| Product galleries    | Store pages, category pages, featured sections, and collection displays.                        | Whether product organization works visually in the target site.                                 |
| Priority URLs        | High-traffic category, collection, product, and landing-page URLs.                              | Whether redirects or URL changes need to be planned.                                            |

### 4. Prepare Customer, Contact, Member, and Account Evidence <a href="#id-4-prepare-customer-contact-member-and-account-evidence" id="id-4-prepare-customer-contact-member-and-account-evidence"></a>

Wix can involve several related identity layers: customers, contacts, members, subscribers, account holders, and app-specific participant records. These should not be treated as one identical data type without review.

Prepare representative records that show:

* ordinary buyers with order history;
* registered customers or members with account context;
* newsletter subscribers and marketing-consent status;
* contacts with phone, address, company, tags, notes, or segmentation values;
* customers tied to subscriptions, bookings, memberships, events, restaurants, or other Wix app workflows;
* B2B-like records with company details, tax identifiers, special pricing, or approval rules;
* external CRM, email marketing, loyalty, or accounting identifiers.

The preparation objective is to preserve usable identity meaning. A migrated customer record should be understandable for order review, service follow-up, segmentation, and post-launch operation. If member access, custom roles, app participation, or account permissions matter, those requirements should be reviewed separately from standard customer migration.

### 5. Prepare Order and Transaction Samples <a href="#id-5-prepare-order-and-transaction-samples" id="id-5-prepare-order-and-transaction-samples"></a>

Order preparation should cover the records that customer service, finance, fulfillment, and store management will rely on after migration. A useful order sample set should include more than successful paid orders.

| Order sample                                      | What to include                                                                                                    | Why it matters                                                         |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| Paid and fulfilled orders                         | Products, quantities, totals, taxes, discounts, customer details, shipping, payment label, and fulfillment status. | Confirms ordinary historical order readability.                        |
| Refunded, canceled, or partially fulfilled orders | Status, totals, refund context, shipping context, and customer communication needs.                                | Shows whether complex historical order states remain understandable.   |
| Orders with discounts or coupons                  | Coupon codes, discount names, totals, and promotion context.                                                       | Historical discount labels may not recreate live discount rules.       |
| Orders with variants or modifiers                 | Purchased choices, SKU, product name at purchase, price differences, and personalization details.                  | Confirms whether purchased product meaning remains clear.              |
| Orders from channels or apps                      | Marketplace, POS, booking, restaurant, event, subscription, or app-related context.                                | App or channel-owned order meaning may need separate review.           |
| Orders with external references                   | Payment IDs, invoice numbers, shipping labels, ERP records, accounting IDs, or fulfillment IDs.                    | External references may affect post-launch service and reconciliation. |

Historical order migration should be reviewed separately from live checkout configuration. Order records can preserve past transaction context, but payment providers, tax settings, shipping rates, pickup, delivery, fulfillment, discounts, and checkout behavior must be configured and tested in Wix.

### 6. Separate Checkout Configuration from Migrated Order History <a href="#id-6-separate-checkout-configuration-from-migrated-order-history" id="id-6-separate-checkout-configuration-from-migrated-order-history"></a>

A common Wix preparation mistake is assuming historical order data proves the live store is ready to sell. These are different workstreams.

| Area              | Migration preparation                                                                         | Target setup responsibility                                                                      |
| ----------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Payments          | Preserve historical payment labels and transaction references where supported.                | Configure Wix Payments or other payment providers and test live payment flow.                    |
| Shipping          | Preserve historical shipping labels, methods, tracking, or fulfillment notes where supported. | Configure shipping regions, rates, pickup, delivery, fulfillment methods, and carrier logic.     |
| Tax               | Preserve historical tax values in order records where supported.                              | Configure tax rules and test tax calculation for new checkout activity.                          |
| Discounts         | Preserve order-level discount context where supported.                                        | Recreate active coupon or promotion behavior in Wix if still needed.                             |
| Customer accounts | Preserve customer or contact meaning where supported.                                         | Configure member access, account behavior, forms, roles, or app-specific permissions.            |
| App workflows     | Identify orders tied to apps, subscriptions, bookings, events, restaurants, or memberships.   | Configure the relevant Wix app workflow and review whether historical app data belongs in scope. |

### 7. Prepare CMS Pages, Blog Posts, Content, and Design Evidence <a href="#id-7-prepare-cms-pages-blog-posts-content-and-design-evidence" id="id-7-prepare-cms-pages-blog-posts-content-and-design-evidence"></a>

Wix is often selected for its combined website and commerce environment. Migration preparation should therefore include content and design evidence, especially when the source store depends on editorial pages, blog traffic, landing pages, menus, forms, images, videos, or SEO-sensitive content.

Prepare:

* priority CMS Pages, landing pages, and policy pages;
* Blog Posts, authors, categories, tags, publication dates, images, and SEO values;
* product-page content blocks, size guides, FAQs, warranty pages, or buying guides;
* menus, footer links, homepage sections, promotional landing pages, and campaign pages;
* media files, alt text, embedded videos, downloadable files, and image galleries;
* forms, member-only content, booking pages, event pages, restaurant pages, or other Wix-app content;
* mobile layout expectations and visual differences that matter for launch acceptance.

Content preparation should identify which material is migrated, rebuilt, redesigned, redirected, or intentionally excluded. Design recreation should not be assumed to happen automatically through data migration.

### 8. Prepare SEO, URL, Redirect, and Domain Evidence <a href="#id-8-prepare-seo-url-redirect-and-domain-evidence" id="id-8-prepare-seo-url-redirect-and-domain-evidence"></a>

SEO preparation should start before migration because Wix URL structure, page hierarchy, product slugs, collection paths, redirects, metadata, and domain setup may differ from the Source Platform.

| SEO area                    | Evidence to prepare                                                                               | Planning reason                                                                    |
| --------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Priority product URLs       | Best-selling or high-traffic product URLs, metadata, image alt text, and ranking-sensitive pages. | These records should be sampled in Demo Migration and redirect planning.           |
| Category or collection URLs | Source category paths, landing pages, and product-listing pages.                                  | Source categories may not become identical Wix URLs.                               |
| Blog and content URLs       | Blog Posts, CMS Pages, authors, tags, and legacy permalink structures.                            | Content migration can affect organic traffic if URLs and metadata are not planned. |
| Redirect map                | Old-to-new URL expectations for important pages.                                                  | Redirect planning helps preserve traffic continuity.                               |
| Domain setup                | Primary domain, subdomains, DNS expectations, and launch timing.                                  | Domain work is part of launch readiness, not proof that data migrated correctly.   |

### 9. Inventory Apps, Velo, APIs, and External Systems <a href="#id-9-inventory-apps-velo-apis-and-external-systems" id="id-9-inventory-apps-velo-apis-and-external-systems"></a>

Apps and custom behavior can carry business meaning that is not visible in standard product, customer, or order exports. Wix preparation should identify these dependencies early so they are not discovered only after Demo Migration.

| Dependency type                    | Examples to document                                                                                                                    | Migration implication                                                                           |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Wix apps or equivalent source apps | Bookings, Events, Restaurants, Pricing Plans, Subscriptions, loyalty, email marketing, chat, forms, reviews, or third-party store apps. | App-owned records may require separate scope review or manual setup.                            |
| Velo or custom code                | Custom collections, page logic, form submissions, dynamic pages, custom checkout-adjacent behavior, or automation logic.                | Custom logic is handled through Custom Service when migration behavior must be adjusted.        |
| APIs and external systems          | ERP, CRM, accounting, PIM, WMS, fulfillment, shipping, tax, analytics, marketplace, or advertising systems.                             | External identifiers and sync rules may need mapping or reconfiguration.                        |
| Custom fields                      | Product, customer, order, contact, member, or content fields that affect operations.                                                    | Unsupported or custom field mapping may require Advanced Data Mapping or Custom Service review. |
| Automations and notifications      | Email workflows, order alerts, customer segmentation, abandoned-cart behavior, or fulfillment messages.                                 | These usually require target setup rather than data migration alone.                            |

### 10. Choose Demo Migration Samples Deliberately <a href="#id-10-choose-demo-migration-samples-deliberately" id="id-10-choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the records most likely to reveal whether the Wix migration path fits the business. A shallow sample can make the migration look cleaner than it will be in production.

| Sample type             | Strong Wix sample                                                                                      | What it proves                                                                    |
| ----------------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| Product                 | A product with multiple options, choices, variants, SKU, inventory, image differences, and SEO values. | Whether catalog behavior translates into usable Wix product structure.            |
| Collection              | A category or collection with important filters, navigation, and priority URL needs.                   | Whether shoppers can browse and find products after migration.                    |
| Customer/contact/member | A buyer with account context, contact details, consent status, tags, and order history.                | Whether identity meaning remains usable in Wix.                                   |
| Order                   | An order with variants, discounts, tax, payment label, shipping, tracking, and external references.    | Whether historical order records remain readable for operations.                  |
| Content                 | A CMS Page, Blog Post, or landing page with images, metadata, links, and old URL value.                | Whether content and SEO handling need extra planning.                             |
| App or custom record    | A record tied to bookings, events, subscriptions, memberships, Velo, or an external system.            | Whether app-owned or custom behavior belongs in standard scope or Custom Service. |

### 11. Identify Add-on and Custom Service Signals Early <a href="#id-11-identify-add-on-and-custom-service-signals-early" id="id-11-identify-add-on-and-custom-service-signals-early"></a>

Preparation should also reveal whether standard migration scope is enough or whether additional service planning is needed.

Add-ons can help when filtering, mapping, or data configuration needs fit supported behavior. The Data Filter Add-on can support selected-record migration where appropriate. Advanced Data Mapping can help align supported fields between the Source Platform and Wix. Advanced Data Configure can support supported data value adjustments before migration.

Custom Service is the correct path when the requirement involves custom migration logic adjustment, Custom Platform source interpretation, unsupported app data, Velo or API-specific handling, custom field transformation beyond supported mapping, bespoke product-option behavior, non-standard checkout-related meaning, or external-system identifiers that must be preserved in a specific way.

### Conclusion <a href="#conclusion" id="conclusion"></a>

A prepared Wix migration gives the Demo Migration and Full Migration a clear decision basis. The strongest preparation connects records to actual Wix use: products must be sellable, options and variants must make sense, collections must support browsing, customers and members must remain understandable, orders must be readable, and content or SEO outcomes must be planned before launch.

Before starting Demo Migration, collect the product, order, customer, content, app, API, and SEO samples that best represent the store’s real operating complexity. If those samples reveal filtering, mapping, data configuration, custom app behavior, Velo logic, or external-system dependency, review the need for Add-ons or Custom Service before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first for a Wix migration?**

Start with the target Wix site context, including Wix Stores setup, required apps, checkout expectations, payment and shipping needs, domain plans, and the product and content samples that represent the store’s real operating model.

**Which product samples should be included before Demo Migration?**

Include simple products, products with options and variants, inventory-sensitive products, products with custom fields or modifiers, best sellers, SEO-important products, and any records tied to subscriptions, apps, or external systems.

**Should CMS Pages and Blog Posts be prepared before migration?**

Yes. Wix is often used as a website-and-commerce platform, so CMS Pages, Blog Posts, landing pages, menus, media, metadata, and redirects should be prepared before launch planning depends on the migrated result.

**Does migrated order history configure Wix checkout?**

No. Historical order data can preserve past order context, but Wix checkout, payments, shipping, tax, pickup, delivery, discounts, and fulfillment behavior must be configured and tested in the target site.

**When should Custom Service be considered for a Wix migration?**

Custom Service should be considered when the migration depends on Custom Platform interpretation, unsupported app data, Velo or API-specific behavior, custom migration logic adjustment, complex custom fields, or external-system identifiers that must be preserved in a specific way.
