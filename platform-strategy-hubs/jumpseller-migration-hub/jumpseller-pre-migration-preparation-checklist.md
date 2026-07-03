# Jumpseller Pre-Migration Preparation Checklist

Preparing for a migration to Jumpseller means more than exporting products, customers, orders, CMS Pages, and Blog Posts. Jumpseller is a hosted e-commerce Target Platform with its own catalog structure, checkout settings, payment and shipping configuration, theme layer, content model, apps, sales channels, integrations, languages, redirects, and administrative controls. The preparation work should make those target-side expectations clear before migration begins.

The goal is to reduce ambiguity. A source store may contain data that looks familiar but behaves differently after migration. Product options may control sellable variants, visible specifications, filters, inventory, or personalization. Categories may not match storefront navigation. Customer groups may carry pricing, tax, or access rules that need interpretation. Orders may include custom statuses, payment references, fulfillment details, abandoned-order data, or external-system identifiers. Preparation should identify these meanings early so the Demo Migration can test the right samples and the final migration scope does not depend on assumptions.

### Confirm the Migration Path and Target Store Role <a href="#confirm-the-migration-path-and-target-store-role" id="confirm-the-migration-path-and-target-store-role"></a>

The first preparation task is to confirm that Jumpseller is the intended Target Platform and to define what the target store is expected to do after migration. Some projects use Jumpseller as a cleaner hosted replacement for a self-hosted store. Others need Jumpseller to support multilingual selling, social sales channels, subscription or appointment-style selling, digital products, customer login, product reviews, app integrations, or specific fulfillment workflows.

This distinction matters because the migration plan should separate source data movement from target-store readiness. Migrated data can support the new store only when the intended Jumpseller plan, theme, payment methods, shipping rules, language setup, and apps can support the business model.

| Preparation priority         | Evidence to gather                                                                                                                                                               | Why it matters                                                                                                           |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Target store purpose         | Define whether Jumpseller will replace the full live store, support a simplified catalog, support a regional store, or serve as a new sales channel                              | The target purpose affects catalog depth, content scope, redirect priorities, and validation samples                     |
| Required target capabilities | List required product, checkout, customer, language, payment, shipping, tax, content, and app behaviors                                                                          | Plan-sensitive or app-dependent features should be confirmed before migration is treated as straightforward              |
| Target plan assumptions      | Confirm required Jumpseller capabilities such as languages, administrator accounts, stock locations, product filtering, customer login, code editing, and reviews where relevant | A migration can be technically successful but operationally weak if the selected plan does not support required behavior |
| Launch expectations          | Define whether the target store must be ready for immediate launch, phased review, or post-migration configuration work                                                          | The level of readiness affects how much configuration, content review, and validation must happen before go-live         |

A useful readiness test is simple: after migration, can the store team explain how products will be sold, how customers will buy, how orders will be handled, and how important pages and URLs will work inside Jumpseller? If the answer is unclear, preparation should continue before relying on a full migration run.

### Prepare Product and Variant Evidence <a href="#prepare-product-and-variant-evidence" id="prepare-product-and-variant-evidence"></a>

Product preparation should identify how the source catalog is built and how each product type should behave in Jumpseller. Source platforms often mix product attributes, options, variants, modifiers, downloadable files, custom fields, personalization inputs, bundles, product kits, subscription rules, and app-owned product data. These meanings should be classified before migration.

Start with a catalog inventory, not only a product count. Group products by behavior: simple products, products with color and size options, products with many variant combinations, digital products, products with attachments, products with custom fields, products with personalization requirements, products with stock-tracked variants, and products controlled by apps or external systems.

| Product preparation area           | What to prepare                                                                                                                  | Sample to include in Demo Migration                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Simple products                    | Names, descriptions, SKUs, prices, images, visibility, categories, stock, SEO fields, and status                                 | A normal active product and an inactive or hidden product if the source uses visibility states |
| Products with options and variants | Option names, option values, SKU differences, price differences, images, stock, weight, and availability logic                   | A product where variant choice changes SKU, price, stock, and image                            |
| Dense variant products             | Products with many option combinations or unusual option matrices                                                                | The product with the largest or most operationally important variant structure                 |
| Custom product fields              | Field names, field values, display expectations, filtering expectations, and whether the field affects purchase behavior         | A product where custom fields are important to shopper decisions or staff handling             |
| Special product workflows          | Downloads, subscriptions, appointments, services, bundles, kits, product builders, personalized products, or app-driven products | A product whose source behavior is not ordinary product-and-variant selling                    |

Product samples should include successful and difficult cases. A Demo Migration made only from simple products can hide the real catalog burden. The best samples include products that reveal option, variant, image, price, stock, category, and custom-field translation issues before the full migration is planned.

### Prepare Category, Navigation, and Discovery Structure <a href="#prepare-category-navigation-and-discovery-structure" id="prepare-category-navigation-and-discovery-structure"></a>

Jumpseller categories help organize products, but source categories are not always the same as storefront navigation. Older stores often use categories as menus, collections, brand pages, SEO landing pages, merchandising groups, filters, or campaign structures. Preparation should separate what needs to remain as product organization from what needs to be rebuilt as navigation or storefront presentation.

Create two maps before migration: one for product category assignment and one for storefront navigation. They may overlap, but they should not be assumed to be identical. High-value category URLs, brand pages, and campaign landing pages should also be identified because they may require redirect planning, content review, or theme-level decisions.

| Area to prepare       | Questions to answer                                                                                 | Why it matters                                                                                        |
| --------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Category hierarchy    | Which categories should exist in Jumpseller, which should be simplified, and which are legacy-only? | A copied category tree can make the target store harder to browse if the source structure is outdated |
| Product assignments   | Which products belong in each important category?                                                   | Category presence is not enough if products appear in the wrong departments                           |
| Navigation menus      | Which categories, pages, collections, and content areas should appear in menus?                     | Storefront navigation often needs separate planning from category migration                           |
| Filters and discovery | Which product values should be visible, searchable, or filterable?                                  | Source attributes may not automatically become useful target filters                                  |
| SEO landing paths     | Which category or collection pages receive meaningful search traffic?                               | These URLs may need redirect and destination-quality review                                           |

The strongest preparation outcome is not a perfect copy of the old hierarchy. It is a target catalog structure that supports realistic shopper browsing, search, filtering, and merchandising inside Jumpseller.

### Prepare Customer, Account, and Password Expectations <a href="#prepare-customer-account-and-password-expectations" id="prepare-customer-account-and-password-expectations"></a>

Customer preparation should clarify how customer records will be used after migration. Some customer records exist mainly to preserve order history. Others are needed for future login, repeat purchasing, customer service, marketing segmentation, tax handling, B2B-style account review, or language-specific communication.

Prepare a customer field inventory before migration. Include names, emails, phone numbers, billing and shipping addresses, customer categories or groups, tax identifiers, preferred language, marketing consent, account status, and any custom source fields. If the source store uses customer groups to control pricing, payment access, shipping eligibility, discounts, or tax behavior, those rules should be documented separately because a label migration does not automatically preserve business logic.

Password expectations should be handled cautiously. Customers may not be able to keep using old passwords after a move into a hosted SaaS target, depending on source hash behavior, target compatibility, and the selected continuity approach. Preparation should define the customer-login plan before launch so customer communication and support expectations are not handled as a last-minute issue.

| Customer preparation area       | Evidence to gather                                                                                       | Review priority                                                                         |
| ------------------------------- | -------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Core customer records           | Names, emails, phones, addresses, account status, and duplicate records                                  | Confirm that customer identity remains readable and usable                              |
| Customer categories or groups   | Group names, business rules, pricing rules, tax rules, payment/shipping restrictions, or marketing uses  | Separate labels from rules that may need configuration or Custom Service review         |
| Password and login expectations | Source password behavior, customer-login requirement, reset communication needs, and launch support plan | Avoid assuming legacy passwords will work automatically                                 |
| Language and consent fields     | Preferred language, marketing consent, newsletter acceptance, and regional communication needs           | Preserve communication context where it matters operationally                           |
| Tax and billing identifiers     | Tax IDs, company fields, invoice fields, and billing requirements                                        | Confirm whether target checkout and customer records support required billing workflows |

Customer readiness is especially important when the store depends on repeat buyers, wholesale accounts, language-specific service, or legally required billing information.

### Prepare Order, Payment, Fulfillment, and Inventory Samples <a href="#prepare-order-payment-fulfillment-and-inventory-samples" id="prepare-order-payment-fulfillment-and-inventory-samples"></a>

Order history should remain readable and useful after migration. It should help store staff understand what customers bought, how they paid, where items were shipped, what taxes and discounts applied, and how fulfillment was handled. Source stores often use custom statuses, payment modules, shipment records, refund states, invoices, abandoned-order logic, manual orders, or external fulfillment systems. These should be documented before migration.

Prepare order samples across the major operational states, not only completed orders. Include paid, pending, canceled, refunded, fulfilled, partially fulfilled, abandoned, manual, and special-case orders where relevant. If the source store uses custom statuses, document what each status means to the business.

Inventory preparation should focus on stock meaning, not only stock numbers. A product may have stock at product level, variant level, warehouse level, supplier level, ERP level, or app level. If Jumpseller stock locations or app integrations will be used, prepare the expected stock structure before migration.

| Operational area     | What to prepare                                                                                             | Demo Migration sample                                                                                    |
| -------------------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Order status meaning | Source statuses and what staff use them for                                                                 | Paid, pending, canceled, refunded, fulfilled, partially fulfilled, and abandoned samples where available |
| Payment context      | Payment method names, transaction references, payment status, offline payments, and gateway-specific fields | Orders from the most common and most sensitive payment methods                                           |
| Fulfillment context  | Shipping method, tracking, fulfillment status, pickup/delivery rules, and partial fulfillment if used       | Orders with different fulfillment paths and shipping destinations                                        |
| Inventory logic      | Product stock, variant stock, low-stock rules, stock locations, warehouse expectations, and ERP-owned stock | Products with stock differences by variant and any location-dependent stock expectation                  |
| External identifiers | ERP IDs, invoice IDs, marketplace IDs, fulfillment-provider IDs, or accounting references                   | Records where outside-system IDs are needed after migration                                              |

Historical orders should be judged by interpretability. They do not need to reproduce every old admin workflow, but staff should be able to read the migrated record and understand the order’s business meaning.

### Prepare Checkout, Payment, Shipping, and Tax Requirements <a href="#prepare-checkout-payment-shipping-and-tax-requirements" id="prepare-checkout-payment-shipping-and-tax-requirements"></a>

Checkout preparation is critical because checkout behavior is target-side configuration, not simply migrated data. Source checkout fields, delivery instructions, tax identifiers, invoice fields, phone requirements, legal consent, pickup options, or local billing requirements may not automatically become Jumpseller checkout behavior.

Create a checkout requirement list before migration. Identify which fields are required for legal, tax, fulfillment, customer-service, or marketing reasons. Then separate required data from optional data. Also confirm which payment gateways, shipping methods, taxes, zones, and delivery rules must be configured in Jumpseller before the target store can be validated.

| Checkout preparation area | Evidence to gather                                                                                                    | Why it matters                                                                     |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Required checkout fields  | Tax ID, company name, invoice details, delivery instructions, phone, pickup preferences, custom notes, consent fields | Required fields affect legal compliance, fulfillment, and customer support         |
| Payment methods           | Source payment providers, local gateways, offline methods, payment-status meanings, and replacement needs             | Historical payment labels and future payment configuration are different tasks     |
| Shipping methods          | Zones, rates, carriers, pickup rules, free-shipping rules, weight rules, destination limits, and app dependencies     | Shipping configuration must be tested separately from order migration              |
| Tax and invoicing         | Tax rates, customer tax groups, invoice fields, billing rules, and regional requirements                              | Tax and billing behavior may require target configuration or Custom Service review |
| Checkout limitations      | Source checkout scripts, custom checkout layout, payment-step modifications, or special validation rules              | Hosted checkout boundaries can affect whether source behavior can be reproduced    |

A migration plan should not wait until validation to discover that the target checkout cannot collect required information or support an expected payment/shipping flow. These requirements belong in preparation.

### Prepare Content, Theme, SEO, and Redirect Evidence <a href="#prepare-content-theme-seo-and-redirect-evidence" id="prepare-content-theme-seo-and-redirect-evidence"></a>

Jumpseller migration planning should include storefront content as well as commerce records. Products and orders may migrate correctly, while content pages, legal pages, blog content, SEO metadata, media, menus, theme components, and redirects still require review.

Prepare a content inventory that includes CMS Pages, Blog Posts, legal pages, landing pages, high-value category pages, brand pages, images, downloadable files, and embedded media. Identify which pages should remain active, which should be rewritten, which should be redirected, and which can be retired.

Theme preparation should focus on what must be represented in Jumpseller, not on copying the old theme. Source storefront design, page-builder modules, custom templates, widgets, app blocks, or checkout layout should be reviewed as target-side design and configuration work. If code editing, Liquid customization, or third-party design work is expected, the target plan and implementation responsibility should be confirmed before migration.

| Storefront area                 | What to prepare                                                                                                         | Review priority                                                                           |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| CMS Pages and legal pages       | Page titles, body content, status, SEO fields, language versions, and permalink needs                                   | Confirm that business-critical content remains accessible and accurate                    |
| Blog Posts and content archives | Post titles, dates, categories, authors where relevant, images, and links                                               | Preserve useful content without importing obsolete clutter                                |
| High-value URLs                 | Product, category, page, blog, brand, and campaign URLs with traffic or backlinks                                       | Build a priority redirect list rather than trying to treat every historical URL equally   |
| Theme expectations              | Source page types, homepage sections, product-page elements, collection layout, menus, badges, widgets, and custom code | Decide what should be rebuilt in Jumpseller rather than expected to migrate automatically |
| Media and files                 | Product images, page images, downloadable files, PDFs, documents, and embedded assets                                   | Confirm that content remains visible and connected where shoppers need it                 |

SEO preparation should be priority-based. High-value URLs and content paths deserve focused redirect and destination review. Low-value historical paths can be handled differently if they no longer support the live business.

### Prepare Multilingual, Multicurrency, and Regional Selling Requirements <a href="#prepare-multilingual-multicurrency-and-regional-selling-requirements" id="prepare-multilingual-multicurrency-and-regional-selling-requirements"></a>

Jumpseller can support multilingual and multicurrency selling, but a migration should not assume that every translated or regional source element will automatically appear in the right place. Language preparation should cover products, categories, pages, menus, checkout labels, customer language preference, SEO fields, email content, and app or theme text where relevant.

Currency preparation should separate display, payment, accounting, tax, and order-history meaning. A source store may show prices in multiple currencies, accept payments in specific currencies, record exchange rates, or use country-specific payment and shipping behavior. These meanings should be reviewed before migration.

| Regional preparation area | What to prepare                                                                             | What to validate later                                                                           |
| ------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Active languages          | Languages used in products, categories, pages, menus, checkout, email, and customer records | Representative product, page, category, navigation, and checkout samples in each active language |
| Translation completeness  | Missing source translations, mixed-language fields, untranslated metadata, and old content  | Target pages and product records do not create partial-language storefront experiences           |
| Currency requirements     | Active currencies, default currency, payment currency, rounding, tax, and country behavior  | Prices, payments, and order history are understandable in the intended operating context         |
| Regional shipping and tax | Country zones, local delivery options, tax IDs, invoice rules, and local gateways           | Customers in key regions can complete realistic purchase scenarios                               |

Multilingual preparation should be realistic. If source translations are incomplete or inconsistent, migration may preserve those gaps. The target plan should decide whether to migrate, clean, rewrite, or retire weak translations.

### Prepare Apps, API, Webhooks, and External-System Dependencies <a href="#prepare-apps-api-webhooks-and-external-system-dependencies" id="prepare-apps-api-webhooks-and-external-system-dependencies"></a>

Jumpseller stores may depend on apps, sales channels, payment providers, shipping providers, invoicing systems, dropshipping tools, marketing apps, analytics, feeds, API connections, webhooks, or external inventory systems. A migration should identify which dependencies affect native store records and which remain outside the migration scope.

Prepare an integration inventory before migration. Include every source-side app, plugin, connector, feed, ERP, invoicing platform, fulfillment provider, marketplace, analytics script, customer-service widget, marketing automation tool, and custom API process that affects products, customers, orders, stock, content, or checkout.

| Dependency type                   | What to prepare                                                                           | Service implication                                                                          |
| --------------------------------- | ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Native Jumpseller app replacement | Target-side app name, expected behavior, data requirement, and setup responsibility       | Usually target configuration unless migrated data must be transformed for the app            |
| Source app-owned data             | Data tables, fields, exports, API access, and business use                                | Custom Service review when the data is not part of standard source records                   |
| External identifiers              | ERP IDs, marketplace IDs, fulfillment IDs, invoice IDs, customer IDs, or product feed IDs | Custom Service review when identifiers must be preserved, mapped, or transformed             |
| Webhooks and API processes        | Events, endpoints, data payloads, external systems, and operational purpose               | Custom Service review when migration must preserve or restructure integration-dependent data |
| Tracking and scripts              | Analytics, pixels, widgets, chat tools, marketing scripts, and theme embeds               | Usually target theme/app setup, but migration should not imply automatic transfer            |

The preparation goal is to avoid confusing native migration data with surrounding operational systems. If app-owned records or outside-system identifiers are important after launch, they should be identified before service selection and Demo Migration interpretation.

### Design the Demo Migration Sample Set <a href="#design-the-demo-migration-sample-set" id="design-the-demo-migration-sample-set"></a>

Demo Migration should test the most important and most difficult source data, not just a convenient small sample. For Jumpseller, a strong sample set should include ordinary records, edge cases, and records tied to target-side constraints.

| Sample area               | Include                                                                                                                          | Why it matters                                                                      |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Products                  | Simple products, variant-heavy products, products with images, products with custom fields, digital or special workflow products | Reveals catalog translation and shopper-selection issues                            |
| Categories and navigation | Top-level category, nested category, SEO landing category, and menu-dependent category                                           | Tests category structure and storefront discovery assumptions                       |
| Customers                 | Customer with full addresses, customer category/group, preferred language, marketing consent, and password expectation           | Tests account meaning and post-launch customer communication                        |
| Orders                    | Paid, pending, canceled, refunded, fulfilled, partially fulfilled, abandoned, and manual samples where available                 | Tests historical readability and status interpretation                              |
| Inventory                 | Variant-level stock, low-stock examples, location-dependent stock, and external inventory examples                               | Tests whether stock meaning survives target interpretation                          |
| Content and redirects     | High-value CMS Page, Blog Post, legal page, product URL, category URL, and redirected page                                       | Tests content continuity and SEO planning                                           |
| Multilingual records      | Product, category, page, menu, and customer samples in each active language                                                      | Tests translation completeness and target-language behavior                         |
| App/integration records   | Records with external IDs, app-owned fields, or API/webhook dependencies                                                         | Tests whether standard migration scope is enough or Custom Service review is needed |

A weak Demo Migration sample creates false confidence. A strong sample exposes the decisions that need to be made before full migration.

### Identify Add-on and Custom Service Signals Before Migration <a href="#identify-add-on-and-custom-service-signals-before-migration" id="identify-add-on-and-custom-service-signals-before-migration"></a>

Preparation should also identify when the project needs Add-ons or Custom Service review. These decisions should not be postponed until after a failed validation round if the source evidence already shows special requirements.

Add-ons are useful when the requirement is about filtering, mapping, or data configuration within supported service capability. The Data Filter Add-on can help when only selected records should migrate. Advanced Data Mapping can help when supported source fields need clearer target mapping. Advanced Data Configure can help when data values should be adjusted before migration.

Custom Service is the correct path when the requirement involves customization, unsupported data, bespoke transformation, Custom Platform handling, custom migration logic adjustment, app-owned records, outside-system identifiers, or source structures that standard service capability cannot interpret safely.

| Preparation signal                                                                              | Likely review path             | Why it matters                                                                        |
| ----------------------------------------------------------------------------------------------- | ------------------------------ | ------------------------------------------------------------------------------------- |
| Only selected products, customers, orders, CMS Pages, or Blog Posts should migrate              | Data Filter Add-on review      | Estimated entity quantities are not migration filters                                 |
| Source fields need supported mapping into Jumpseller fields or custom fields                    | Advanced Data Mapping review   | Mapping should preserve operational meaning, not just field names                     |
| Data values need cleanup or controlled modification before migration                            | Advanced Data Configure review | Some normalization should happen before records enter the Target Platform             |
| Standard Add-on behavior must be modified                                                       | Custom Service review          | Tailored Add-ons are handled through Custom Service because customization is required |
| Custom Platform source, custom database, app-owned records, or outside-system IDs are important | Custom Service review          | These data structures need source-specific interpretation                             |
| Product, checkout, inventory, or integration behavior requires bespoke transformation           | Custom Service review          | Standard service capability should not be assumed when business logic is custom       |

Preparation should make the service path easier to choose. It should not force a premature decision, but it should clearly identify the evidence that will shape that decision.

### Conclusion <a href="#conclusion" id="conclusion"></a>

A strong Jumpseller migration starts with evidence. Product options, category structure, customer accounts, order statuses, checkout fields, inventory, content, redirects, languages, apps, and integrations should be understood before the migration process begins. That preparation protects the project from treating a hosted SaaS target as if it could automatically reproduce every source-side workflow, extension, theme, checkout, or database behavior.

Before moving forward, prepare a sample set that represents both normal records and difficult records. Use the Demo Migration to test how Jumpseller interprets those samples, then review any filtering, mapping, configuration, app-owned data, Custom Platform, or custom migration logic adjustment signals with Next-Cart through Live Chat before committing to the final migration scope.

### FAQs <a href="#faqs" id="faqs"></a>

**Should I prepare only product, customer, and order counts before migrating to Jumpseller?**

No. Counts help with planning, but they do not explain whether the source store can operate correctly in Jumpseller. Preparation should also cover product options, variants, custom fields, categories, navigation, checkout fields, shipping, payment, taxes, content, redirects, languages, inventory, apps, and integrations.

**Do estimated entity numbers control which records will migrate?**

No. Estimated entity numbers support pricing and Entity Points planning. They are not migration filters. If only selected records should move into Jumpseller, filtering should be planned separately, such as through the Data Filter Add-on where appropriate.

**What product samples should be included in a Jumpseller Demo Migration?**

Include simple products, variant-heavy products, products with stock or price differences by option, products with custom fields, products with important images, and any product type that depends on source-specific behavior. The sample should reveal catalog complexity, not avoid it.

**Should categories and navigation be prepared separately?**

Yes. Source categories may not match storefront menus, landing pages, filters, or SEO paths. Prepare a category map and a navigation map separately so the target store is organized for real shoppers, not just for record migration.

**What should I prepare for customer accounts and passwords?**

Prepare customer identity fields, addresses, customer categories or groups, language preferences, marketing consent, billing fields, and login expectations. Password continuity should not be assumed automatically; the launch plan should define whether customers need reset or reactivation communication.

**When does Jumpseller preparation point toward Custom Service?**

Custom Service review is appropriate when the source includes Custom Platform data, custom databases, unsupported app data, outside-system identifiers, bespoke product or checkout logic, source-specific inventory behavior, or any requirement that needs custom migration logic adjustment.
