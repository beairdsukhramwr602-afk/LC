# Squarespace Pre-Migration Preparation Checklist

Preparing for a migration to Squarespace should begin with the parts of the source store that must become usable inside a hosted website and commerce platform. Squarespace can be a strong Target Platform for content-led commerce, simple to moderate catalogs, service businesses, appointment-friendly storefronts, portfolio-led sellers, and merchants that want site management, store management, payments, shipping, taxes, marketing, and design in one hosted environment. The preparation work should confirm whether the source store’s products, variants, content, customers, orders, checkout settings, extensions, and integration requirements can be represented acceptably in that environment.

A good preparation process should make the migration testable before Full Migration. It should clarify which source records can move into standard Squarespace-supported structures, which items require target configuration, which content or design elements need rebuilding, and which app, API, webhook, custom field, or outside-system requirements need Add-ons or Custom Service review.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation is not only a file-collection step. It is the planning work that determines whether Squarespace is ready to receive the source store’s business meaning.

For Squarespace, preparation should clarify:

* which products, variants, SKUs, images, prices, categories, tags, and inventory records should move;
* whether source product types fit the target Squarespace product structure;
* which customer, contact, subscriber, donor, or member-like records carry business value;
* which historical orders and transactions need to remain readable;
* which checkout, shipping, payment, tax, discount, and fulfillment settings belong to target configuration rather than migrated data;
* which CMS Pages, Blog Posts, landing pages, galleries, menus, and design areas matter for launch quality;
* which URLs, metadata, redirects, and search-entry paths need review;
* which extensions, APIs, webhooks, outside-system identifiers, or automation workflows affect scope;
* whether the migration can remain within standard service capability or needs Add-ons, Managed Service, or Custom Service review.

### 1. Confirm the Target Squarespace Context <a href="#id-1-confirm-the-target-squarespace-context" id="id-1-confirm-the-target-squarespace-context"></a>

Before migration, confirm how the target Squarespace site will be used. A Squarespace site may be primarily content-led, commerce-led, service-led, event-led, membership-oriented, donation-oriented, or portfolio-led. That context changes which source records matter most.

| Evidence to gather                                   | Why it matters                                                                              |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Target Squarespace site plan and commerce capability | Determines which store, payment, shipping, tax, and commerce features are available.        |
| Target site version and template/design expectations | Helps separate data migration from template, layout, and design rebuild work.               |
| Store-page structure                                 | Clarifies where products, categories, and catalog browsing should appear.                   |
| Checkout, payment, shipping, and tax requirements    | Separates migrated order history from live checkout setup.                                  |
| Extensions and connected services                    | Identifies data or behavior that may be app-owned, reconfigured, excluded, or custom scope. |
| SEO and URL priorities                               | Protects high-value customer-entry paths and search continuity.                             |
| Team review responsibilities                         | Confirms who will review products, content, orders, checkout, SEO, and integrations.        |

Squarespace is a hosted platform, so preparation should focus on supported platform structures and target configuration rather than direct reproduction of a source store’s server-side behavior.

### 2. Prepare Product and Variant Samples <a href="#id-2-prepare-product-and-variant-samples" id="id-2-prepare-product-and-variant-samples"></a>

Squarespace product preparation should include representative product records, not only product totals. Products may depend on product type, variants, SKUs, images, prices, inventory, product descriptions, categories, tags, shipping behavior, digital delivery expectations, subscription expectations, and merchandising layout.

Prepare product samples that include:

* a simple physical product with ordinary price, SKU, image, inventory, and category assignment;
* a product with multiple variants such as size, color, style, or another selectable dimension;
* a product where each variant has its own SKU, price, image, or inventory value;
* a digital product or product with non-physical delivery expectations;
* a service-like, event-like, donation-like, or appointment-related selling case where relevant;
* a product with sale pricing, discounts, or campaign context;
* a product assigned to multiple categories or tags;
* a product with important SEO fields, page name, image, or historical URL value;
* a product connected to an external system, fulfillment process, marketplace, or inventory source.

A sample set should include the hardest product cases. A Demo Migration that includes only simple products may not reveal whether the target Squarespace store can represent the source catalog’s real selling behavior.

### 3. Prepare Categories, Tags, Navigation, and Discovery Paths <a href="#id-3-prepare-categories-tags-navigation-and-discovery-paths" id="id-3-prepare-categories-tags-navigation-and-discovery-paths"></a>

Squarespace product discovery may depend on store pages, categories, tags, site navigation, product blocks, page sections, search behavior, collection-style pages, and design layout. A product can migrate as a record but still fail commercially if customers cannot find it or understand where it belongs.

Prepare:

| Area                             | Preparation task                                                                                       |
| -------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Product categories               | Identify product grouping, browsing structure, and any category pages that affect customer navigation. |
| Tags or labels                   | Confirm whether tags are only internal organization or customer-facing discovery support.              |
| Store pages                      | Identify the product pages or catalog areas that should receive migrated products.                     |
| Menus and navigation             | Prepare the paths customers use to reach products, policies, service pages, and checkout.              |
| Product blocks and page sections | Identify places where product display is controlled by page design rather than only product data.      |
| Search-sensitive landing pages   | List pages that receive traffic or help customers choose products.                                     |

Review discovery from the storefront perspective. The target site should prove that representative products can be reached through expected customer paths, not only that they exist in the store manager.

### 4. Prepare Customer, Contact, Subscriber, and Audience Data <a href="#id-4-prepare-customer-contact-subscriber-and-audience-data" id="id-4-prepare-customer-contact-subscriber-and-audience-data"></a>

Squarespace may combine commerce, website, email, marketing, donor, member, subscriber, appointment, or contact-related contexts depending on how the target site is used. Migration preparation should identify which people-related records are ordinary customers and which represent a broader audience or external system.

Prepare samples that include:

* customers with order history;
* customers with multiple addresses where relevant;
* guest checkout records where available;
* subscribers, newsletter contacts, or audience records if they matter to the business;
* donors, members, appointment clients, or service customers where relevant;
* customers linked to discounts, subscriptions, memberships, campaigns, or outside systems;
* customers with external CRM, email marketing, accounting, fulfillment, or analytics identifiers.

Do not assume every source contact type becomes the same target record type. Contact, subscriber, customer, donor, and member-like data should be classified before migration scope is finalized.

### 5. Prepare Order and Transaction Samples <a href="#id-5-prepare-order-and-transaction-samples" id="id-5-prepare-order-and-transaction-samples"></a>

Historical order and transaction data should remain useful after migration. For Squarespace, order records may need product lines, totals, discounts, payment labels, shipping labels, tax values, fulfillment status, customer details, notes, refunds, digital delivery context, subscription or donation context, and outside-system references.

Prepare order samples that include:

* paid and unpaid orders;
* fulfilled and unfulfilled orders;
* refunded, canceled, or partially fulfilled orders;
* orders with discounts, coupons, sale prices, or manual adjustments;
* orders with varied shipping and payment labels;
* orders with tax-sensitive totals;
* orders connected to digital products, services, donations, appointments, subscriptions, or membership-like behavior where relevant;
* orders with customer notes or internal notes;
* orders connected to fulfillment, accounting, CRM, email, analytics, or marketplace systems.

Historical order preparation should focus on readability. Live checkout behavior should be prepared separately through target Squarespace configuration.

### 6. Separate Migrated History from Live Checkout Setup <a href="#id-6-separate-migrated-history-from-live-checkout-setup" id="id-6-separate-migrated-history-from-live-checkout-setup"></a>

A common preparation error is treating migrated historical checkout data as live checkout readiness. Past payment, shipping, discount, and tax values can help preserve order history, but live checkout depends on Squarespace settings, payment configuration, shipping rules, tax configuration, fulfillment setup, discounts, and enabled extensions.

Prepare separate notes for:

| Checkout area         | Preparation question                                                                                                                                |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Payment               | Which historical payment labels should remain readable, and which live payment methods must be configured?                                          |
| Shipping              | Which historical shipping labels should remain readable, and which live shipping rules, rates, pickup, or delivery expectations must be configured? |
| Tax                   | Which historical tax values should remain readable, and which target tax settings must be prepared?                                                 |
| Discounts             | Which past discounts should remain understandable, and which active promotions must be rebuilt?                                                     |
| Fulfillment           | Which fulfillment states should remain readable, and which operational processes must be configured after migration?                                |
| Special checkout data | Are source checkout fields ordinary order notes, customer data, app-owned data, or custom scope?                                                    |

This separation protects launch planning. A migrated order can look acceptable while the target store still needs live checkout configuration and testing.

### 7. Prepare Content, CMS Pages, Blog Posts, and Design Evidence <a href="#id-7-prepare-content-cms-pages-blog-posts-and-design-evidence" id="id-7-prepare-content-cms-pages-blog-posts-and-design-evidence"></a>

Squarespace is often chosen for its website and content experience, so content preparation matters as much as commerce preparation. Products can migrate correctly while the site still needs page layout, menus, blocks, sections, galleries, images, forms, policy pages, campaign pages, or brand content rebuilt.

Prepare:

* CMS Pages that should move or be rebuilt;
* Blog Posts that should remain available;
* landing pages that support sales, campaigns, services, events, donations, or memberships;
* policy pages such as shipping, returns, privacy, terms, delivery, and contact information;
* gallery, portfolio, or image-heavy pages that affect brand presentation;
* menus, footer links, button paths, and customer navigation;
* forms, email capture areas, appointment links, donation paths, or membership entry points where relevant;
* important images, alt text, page titles, descriptions, and layout expectations.

Content should be prioritized by business value. Pages that affect traffic, trust, sales, customer support, service booking, donations, or campaign conversion should be prepared before lower-value legacy pages.

### 8. Prepare SEO, URLs, and Redirect Evidence <a href="#id-8-prepare-seo-urls-and-redirect-evidence" id="id-8-prepare-seo-urls-and-redirect-evidence"></a>

Squarespace migration planning should include URL continuity and search-entry paths. A hosted site migration can change page structure, product routes, collection paths, blog URLs, image paths, or landing-page organization.

Prepare SEO evidence for:

| SEO area                    | What to prepare                                                               |
| --------------------------- | ----------------------------------------------------------------------------- |
| High-value product URLs     | Products with organic traffic, backlinks, campaigns, or customer recognition. |
| Category or collection URLs | Browsing paths that should remain understandable after migration.             |
| CMS Page URLs               | Pages that receive traffic or support customer trust.                         |
| Blog Post URLs              | Posts with search value, referral traffic, or evergreen support value.        |
| Metadata                    | Priority titles, descriptions, slugs, and image alt text.                     |
| Redirect expectations       | Legacy URLs that should point to appropriate target pages.                    |
| Navigation paths            | Menus and internal links that guide customers to important pages.             |

SEO preparation should not attempt to preserve every low-value path equally. It should identify the pages where continuity matters most.

### 9. Inventory Extensions, APIs, Webhooks, and Connected Services <a href="#id-9-inventory-extensions-apis-webhooks-and-connected-services" id="id-9-inventory-extensions-apis-webhooks-and-connected-services"></a>

Squarespace migrations can involve more than native records. Extensions, APIs, webhooks, email marketing tools, CRM systems, accounting systems, shipping services, appointment systems, donation tools, memberships, analytics, fulfillment services, and other connected systems may carry business meaning outside standard migration data.

Prepare an integration inventory:

| Connected area                     | What to confirm                                                                                                         |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Squarespace extensions             | Whether the extension owns data, changes checkout, affects shipping, supports marketing, or only needs reconfiguration. |
| Commerce API usage                 | Whether product, order, transaction, or inventory IDs need preservation or mapping.                                     |
| Webhooks                           | Whether external workflows need to be rebuilt or reconnected.                                                           |
| Email and CRM tools                | Whether subscriber, contact, customer, or consent data should migrate or be reconnected.                                |
| Accounting and fulfillment systems | Whether historical IDs, order references, tax values, or shipping data must remain traceable.                           |
| Analytics and advertising          | Whether tracking continuity, campaign pages, or product feeds need separate setup.                                      |
| App-owned data                     | Whether data should be migrated, rebuilt, excluded, or reviewed through Custom Service.                                 |

Classify each connected service as migrated, mapped, reconfigured, rebuilt, excluded, or escalated for Custom Service review.

### 10. Choose Demo Migration Samples Deliberately <a href="#id-10-choose-demo-migration-samples-deliberately" id="id-10-choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the records that carry the most business meaning. For Squarespace, that usually includes product structure, content structure, order readability, SEO paths, and connected-system data.

| Sample type                                                           | Why it matters                                                                       |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Product with variants                                                 | Tests variant, SKU, inventory, image, and price interpretation.                      |
| Digital, service-like, donation-like, or subscription-related product | Tests whether special selling meaning is preserved, rebuilt, or excluded.            |
| Category or tag path                                                  | Tests storefront discovery and product grouping.                                     |
| Customer/contact sample                                               | Tests customer, subscriber, donor, member-like, or audience meaning where relevant.  |
| Varied order                                                          | Tests payment, shipping, tax, discount, fulfillment, notes, and transaction context. |
| CMS Page or Blog Post                                                 | Tests content structure, page quality, and publishing continuity.                    |
| High-value URL                                                        | Tests SEO and redirect planning.                                                     |
| Extension or API-dependent record                                     | Tests app-owned, webhook, or outside-system handling.                                |

If the sample set does not include Squarespace-relevant complexity, Demo Migration may give a false sense of readiness.

### 11. Identify Add-on and Custom Service Signals Early <a href="#id-11-identify-add-on-and-custom-service-signals-early" id="id-11-identify-add-on-and-custom-service-signals-early"></a>

Some Squarespace migrations fit standard service capability. Others need filtering, mapping, configuration, custom handling, or integration-aware review before Full Migration.

Consider Add-ons when the need stays within supported service capability:

* use the Data Filter Add-on when only selected eligible records should migrate;
* use Advanced Data Mapping when supported source fields need controlled mapping into supported Squarespace target fields;
* use Advanced Data Configure when migrated values need supported modification before reaching the Target Platform.

Custom Service review should be considered when:

* the Source Platform or Target Platform is Custom Platform;
* source product structures require non-standard transformation;
* custom fields or outside-system identifiers must be preserved;
* extension-owned, API-connected, webhook-triggered, or app-owned data must be migrated or mapped;
* content, SEO, or URL behavior requires bespoke treatment beyond supported configuration;
* checkout, shipping, payment, tax, donation, membership, appointment, or subscription-related behavior is custom;
* tailored migration behavior goes beyond Standard Add-on capability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace preparation should make the target result testable before Full Migration begins. Products, variants, SKUs, customers, contacts, orders, transactions, content, URLs, checkout settings, extensions, APIs, webhooks, and outside-system data should be prepared as connected parts of a hosted site and commerce environment.

Build Demo Migration samples from the records that carry the most business meaning. If those samples reveal unsupported product behavior, app-owned data, custom fields, important URL risks, content rebuild requirements, or outside-system dependencies, resolve the requirement through target configuration, Add-ons, or Custom Service review before continuing.

### FAQs <a href="#faqs" id="faqs"></a>

**What should I prepare first for a Squarespace migration?**

Start with the target Squarespace context, product and variant samples, content and URL priorities, customer/contact records, order samples, checkout requirements, and connected services. These areas show whether the migration is straightforward or needs deeper review.

**Should I prepare both content and commerce data?**

Yes. Squarespace often combines website content and commerce in the same target experience. CMS Pages, Blog Posts, menus, images, product pages, policies, landing pages, and SEO paths can be as important as product and order records.

**Do historical orders prove that checkout is ready?**

No. Historical orders can preserve past payment, shipping, tax, discount, and fulfillment context, but live checkout depends on target Squarespace settings and enabled services.

**Why should extensions and APIs be reviewed before migration?**

Extensions, APIs, webhooks, and connected services may own data or workflow behavior outside ordinary product, customer, order, or content records. They should be classified before scope is finalized.

**When should Custom Service review be considered for Squarespace?**

Custom Service review should be considered when the migration involves Custom Platform data, app-owned records, custom fields, outside-system identifiers, non-standard product transformation, API or webhook dependencies, or bespoke content and URL handling beyond Standard Add-on capability.
