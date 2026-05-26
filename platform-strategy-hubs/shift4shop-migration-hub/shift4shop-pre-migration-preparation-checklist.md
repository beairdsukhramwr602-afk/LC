# Shift4Shop Pre-Migration Preparation Checklist

Preparation for a Shift4Shop migration should make the target outcome easier to interpret before the migration process begins. Shift4Shop can support a hosted ecommerce store with product management, order management, SEO, marketing, inventory, shipping, payment-related workflows, themes, integrations, and support resources. That range is useful only when the source data is organized in a way that can become clear, testable Shift4Shop behavior after migration.

The goal is not to document every field in the Source Platform. The goal is to identify the records, rules, pages, relationships, and operational details that decide whether the migrated store will be usable. A store with simple products and standard customers may need light preparation. A wholesale, hybrid B2B/B2C, option-heavy, integration-shaped, or content-heavy store needs a more deliberate readiness pass before full execution.

A strong preparation checklist turns vague expectations into reviewable evidence. It defines which products reveal catalog complexity, which customers reveal pricing or account rules, which orders reveal operational history, which URLs deserve protection, which data belongs to outside systems, and which requirements should be escalated before a Demo Migration is used as evidence.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation exists to reduce interpretation risk. Without preparation, migrated data may appear complete while important business meaning is still missing. Products may exist without the right buying choices. Customers may exist without wholesale treatment. Orders may exist without enough payment, shipping, discount, or fulfillment context. CMS Pages or Blog Posts may move while high-value routes and page meaning become unclear.

For Shift4Shop, preparation should answer five practical questions:

1. Which source records represent ordinary ecommerce data?
2. Which source records carry business rules, account treatment, pricing logic, or staff workflow meaning?
3. Which storefront pages, product pages, and URLs are commercially important enough to protect deliberately?
4. Which source behaviors depend on apps, modules, custom fields, external systems, or older platform assumptions?
5. Which sample records should be used in Demo Migration so the result exposes real migration risk instead of only easy records?

These answers help the merchant, Next-Cart, and the Target Platform plan the migration path with fewer assumptions. They also make Demo Migration more useful because the sample can show how Shift4Shop handles the store’s actual operating patterns.

### 1. Confirm the Target Store Role Before Reviewing Data <a href="#id-1-confirm-the-target-store-role-before-reviewing-data" id="id-1-confirm-the-target-store-role-before-reviewing-data"></a>

Start by defining what Shift4Shop is expected to do after launch. A store moving into Shift4Shop may be a direct replacement for the current storefront, a cleanup opportunity, a B2B or wholesale operating base, a hybrid B2B/B2C destination, or a hosted platform move intended to reduce dependency on custom maintenance.

The target role affects preparation. A merchant that wants to preserve the current business model should prepare evidence for every workflow that must continue. A merchant that wants to simplify the store should separate data that must be preserved from data that can be cleaned, retired, consolidated, or handled differently after migration.

Document the target role in plain business terms before reviewing records. Useful statements include:

* whether the store sells mainly B2C, B2B, wholesale, or both
* whether customer groups or customer-specific pricing must continue
* whether the catalog relies on options, variants, bundles, kits, downloads, personalization, or technical specifications
* whether SEO continuity is a major launch requirement
* whether order history is needed mainly for customer reference, staff operations, accounting, fulfillment, or compliance review
* whether third-party integrations will continue after migration

This early decision keeps preparation from becoming a raw data inventory. It makes each preparation task answer a business question.

### 2. Classify the Catalog by Selling Behavior <a href="#id-2-classify-the-catalog-by-selling-behavior" id="id-2-classify-the-catalog-by-selling-behavior"></a>

Catalog preparation should separate products by how they behave, not only by category or count. Shift4Shop product records need enough structure for customers to find, understand, configure, price, and buy products correctly. Products that look similar in a spreadsheet may carry very different migration implications.

Create a catalog inventory that identifies:

* simple products with ordinary price, image, inventory, and description data
* products with options, selectable choices, or variation-like behavior
* products with wholesale packs, minimum quantities, quantity pricing, or customer-type pricing
* products with technical specifications, compatibility information, extra fields, or long-form product content
* downloadable or digital products
* products with reviews, Q\&A-style content, attachments, videos, or rich media
* products that depend on source extensions, apps, modules, or custom database fields
* inactive, discontinued, hidden, draft, or legacy products that should not be treated the same as active catalog items

The preparation consequence is direct: representative catalog samples should be selected from each important behavior group. If Demo Migration only uses simple products, it cannot prove whether Shift4Shop will preserve the meaning of the products that actually carry migration risk.

### 3. Document Category, Navigation, and Product Discovery Requirements <a href="#id-3-document-category-navigation-and-product-discovery-requirements" id="id-3-document-category-navigation-and-product-discovery-requirements"></a>

A category record is not the same as a working storefront navigation model. Before migration, document how customers currently find products and how that discovery structure should work in Shift4Shop.

Review:

* main category hierarchy
* subcategory depth
* products assigned to multiple categories
* menu structure and footer links
* filtered navigation, compatibility finders, or search-driven discovery
* high-value landing pages that support product discovery
* category descriptions, banners, images, SEO titles, and meta descriptions
* product collections or grouping logic from the Source Platform

If the Source Platform used custom navigation, plugin-driven filters, page-builder category content, or search rules, identify those dependencies early. They may not be ordinary category data. Some discovery behavior may require configuration after migration, Advanced Data Mapping, Advanced Data Configure, or Custom Service when the expected result depends on custom logic rather than standard category records.

### 4. Separate Customer Identity from Customer Treatment <a href="#id-4-separate-customer-identity-from-customer-treatment" id="id-4-separate-customer-identity-from-customer-treatment"></a>

Customer preparation should distinguish contact identity from commercial treatment. Names, email addresses, billing addresses, and shipping addresses are only the visible layer. For many Shift4Shop migrations, the more important question is how the buyer should be treated after login or checkout.

Prepare a customer-context inventory that identifies:

* ordinary retail customers
* wholesale or B2B customers
* customer groups, customer types, VIP levels, or account segments
* tax-exempt customers or buyers with special tax handling
* customers with minimum order expectations or quantity-based pricing
* customers linked to sales reps, account managers, CRM records, or external identifiers
* customers with store-credit, loyalty, reward, or discount history
* customers whose treatment depends on source notes, tags, custom fields, approval states, or third-party data

Shift4Shop preparation should make clear which customer information must become usable platform behavior and which information only needs to be retained for reference. If the expected treatment depends on non-standard source logic, custom fields, external identifiers, or a rule that cannot be represented through standard service capability, it should be escalated before execution.

### 5. Review Pricing, Coupon, Discount, and Wholesale Logic <a href="#id-5-review-pricing-coupon-discount-and-wholesale-logic" id="id-5-review-pricing-coupon-discount-and-wholesale-logic"></a>

Pricing preparation is necessary because price-related records often behave like rules rather than static values. A migrated price is useful only if it reaches the correct customer, product, quantity, date, or checkout condition.

Prepare examples of:

* base product prices
* sale prices and special prices
* quantity pricing or tiered pricing
* wholesale pricing
* customer-type or customer-group pricing
* coupons and promotion rules
* free shipping conditions
* minimum order conditions
* discounts limited by product, category, customer, date, or order value
* legacy promotions that should not continue after launch

Mark each pricing rule as active, historical, reference-only, or launch-critical. This prevents old discounts from receiving the same attention as current revenue logic. It also helps decide whether the migration can rely on standard migration capability, whether a Standard Add-on can support the required filtering, mapping, or configuration, or whether the requirement belongs in Custom Service.

### 6. Prepare Order History for Operational Use <a href="#id-6-prepare-order-history-for-operational-use" id="id-6-prepare-order-history-for-operational-use"></a>

Order history should be prepared according to how staff and customers will use it after migration. Some merchants need historical orders mainly for customer-service reference. Others need staff to understand payment method, fulfillment state, tax, discounts, shipping, returns, invoices, marketplace references, or account-management context.

Before migration, classify orders by operational meaning:

* ordinary completed orders
* pending, canceled, refunded, partially refunded, or failed orders
* orders with unusual payment methods or manual payment handling
* orders with complex shipping, freight, pickup, dropshipping, or multi-package fulfillment
* orders with coupons, discounts, store credit, rewards, or custom fees
* orders tied to wholesale accounts, sales reps, purchase orders, quotes, invoices, or external systems
* subscription-like, repeat-order, or membership-related order history
* orders with staff notes, customer notes, internal status changes, or custom fields

The purpose is not to make every historical order behave like a new order. The purpose is to decide what level of order interpretation the business requires after migration. If staff cannot understand migrated order history, the migration may pass a record-count check while still failing daily operations.

### 7. Identify Content, CMS Pages, Blog Posts, and High-Value Routes <a href="#id-7-identify-content-cms-pages-blog-posts-and-high-value-routes" id="id-7-identify-content-cms-pages-blog-posts-and-high-value-routes"></a>

Storefront content should be prepared separately from product and category data. Shift4Shop can support ecommerce pages, themes, SEO-oriented storefronts, and marketing content, but source content may include page-builder layouts, embedded forms, custom scripts, old landing pages, educational articles, policy pages, and route structures that do not translate as simple text.

Prepare a content inventory that identifies:

* CMS Pages that must remain active at launch
* Blog Posts that still attract traffic or support customers
* policy pages such as shipping, returns, privacy, warranty, and wholesale terms
* buying guides, technical resources, size guides, compatibility guides, or product education pages
* campaign landing pages and seasonal pages
* high-traffic URLs and high-value SEO routes
* pages with embedded forms, scripts, apps, videos, calculators, or custom layouts
* outdated pages that can be retired or redirected

For each important route, decide whether the goal is exact preservation, content migration with a new layout, redirect coverage, or retirement. This prevents preparation from treating all content as equal when only some pages have launch or SEO value.

### 8. Map Integrations, External Systems, and Custom Fields <a href="#id-8-map-integrations-external-systems-and-custom-fields" id="id-8-map-integrations-external-systems-and-custom-fields"></a>

Shift4Shop migration planning should identify which source data is owned by the ecommerce platform and which data is shaped by external systems. Integration-owned data is often the reason a migration looks simple at the record level but becomes complex during validation.

Document dependencies such as:

* payment gateways and payment references
* shipping carriers, rate logic, labels, tracking, freight, or pickup workflows
* tax services
* inventory systems, warehouse systems, ERP, POS, or marketplace channels
* email marketing and customer-segmentation tools
* reviews, loyalty, reward, subscription, financing, or B2B-specific apps
* custom product fields, custom customer fields, custom order fields, and internal notes
* API-based workflows or scripts that read from the current store

For each dependency, decide whether the data should migrate, remain external, be reconnected after launch, be transformed into reference information, or be reviewed as a Custom Service requirement. Do not assume integration-owned data will become native Shift4Shop behavior without review.

### 9. Clean Up Source Data Without Destroying Review Evidence <a href="#id-9-clean-up-source-data-without-destroying-review-evidence" id="id-9-clean-up-source-data-without-destroying-review-evidence"></a>

Pre-migration cleanup can improve the target result, but careless cleanup can remove evidence needed for planning. The right approach is to classify data before deleting, merging, or rewriting it.

Useful cleanup decisions include:

* remove duplicate products only after deciding which record should remain canonical
* mark inactive products clearly instead of mixing them with active catalog items
* normalize product names, SKUs, options, and categories where obvious inconsistencies exist
* confirm that customer emails, addresses, and account records are usable
* separate test orders from real order history
* identify old coupons, expired promotions, and legacy customer groups
* flag discontinued pages and old URLs that need redirect decisions

Do not use cleanup to hide complexity from Demo Migration. If a problem is important enough to affect launch, include a representative example in the sample set. Preparation should make the migration result easier to judge, not artificially easier to pass.

### 10. Prepare Legacy Source Context Without Letting It Control the Target Plan <a href="#id-10-prepare-legacy-source-context-without-letting-it-control-the-target-plan" id="id-10-prepare-legacy-source-context-without-letting-it-control-the-target-plan"></a>

Some source records, exports, URLs, documentation, or internal notes may still use 3DCart language because Shift4Shop is the rebranded version of 3DCart. This context can matter during preparation when it helps identify older records, legacy URLs, past export formats, historical platform assumptions, or support references.

Treat that context as source evidence, not as the target planning frame. The destination should be evaluated as Shift4Shop. Older assumptions should be checked against current Shift4Shop behavior when they affect data structure, platform capabilities, storefront architecture, integrations, or support expectations.

This is especially important when older documentation describes a source workflow in platform-era terms that no longer reflect how the merchant wants the target store to operate after migration.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

A practical Shift4Shop preparation sequence should move from business intent to migration evidence.

1. Define the target store role and launch priorities.
2. Classify the catalog by selling behavior, not only by product count.
3. Document categories, navigation, product discovery, and SEO-critical routes.
4. Separate customer identity from customer treatment.
5. Review wholesale, quantity, customer-type, coupon, and discount logic.
6. Classify order history by staff and customer-service use.
7. Inventory CMS Pages, Blog Posts, policy pages, and high-value content.
8. Identify integration-owned data, custom fields, and outside-system identifiers.
9. Decide what should be cleaned, retained, retired, filtered, mapped, configured, or escalated.
10. Build a Demo Migration sample set that includes ordinary records and high-risk records.

The sequence should not be treated as a technical setup procedure. It is a readiness framework that helps the migration process produce a result the merchant can evaluate with confidence.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration is most useful when the sample is representative and revealing. A random sample may prove that common records can move, but it may miss the records that decide whether Shift4Shop is ready for launch.

A strong Shift4Shop Demo Migration sample should include:

* at least one simple product and one complex product
* products with options, variations, technical specifications, or rich product-page content
* products with wholesale, quantity, or customer-type pricing where relevant
* active categories and one category with important SEO or navigation value
* ordinary retail customers and customers with group, wholesale, tax, or account treatment
* orders with standard checkout history and orders with discounts, shipping complexity, payment context, or staff notes
* CMS Pages or Blog Posts with commercial or SEO importance
* source records that rely on custom fields, extensions, integrations, or legacy source assumptions
* one or more high-value URLs where redirect or route behavior matters

The sample should produce useful evidence. If every sample record is easy, Demo Migration may look successful while the full migration still contains unresolved risks.

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

If the Source Platform is a Custom Platform, a heavily customized hosted store, a modified open-source installation, or a system shaped by private database structures, prepare the custom data layer before execution. Custom Platform sources require Custom Service because standard service capability cannot assume a stable source data model.

Useful preparation includes:

* source schema samples or export examples
* definitions for custom product, customer, order, content, and integration fields
* explanations of what each custom field means operationally
* examples of records where custom data changes pricing, visibility, fulfillment, SEO, or staff workflow
* mapping expectations for what should become native Shift4Shop data, reference information, or custom migration output
* API, database, or export-access constraints that may affect review

The goal is to make custom data understandable before migration logic is planned. Without that explanation, custom fields can be moved as text while the behavior they supported is lost.

### What Should Be Escalated Before Execution <a href="#what-should-be-escalated-before-execution" id="what-should-be-escalated-before-execution"></a>

Escalate requirements before execution when they cannot be judged through ordinary record migration. Common escalation signals include:

* customer-specific pricing, wholesale logic, or buyer treatment that depends on custom fields or outside systems
* catalog behavior that uses custom product types, bundles, kits, personalization, compatibility rules, or extension-owned logic
* route and SEO requirements that need deliberate preservation or redirect planning
* order history that must preserve custom operational states, fulfillment context, invoices, staff notes, or external references
* integration-owned data expected to appear as usable Target Platform behavior
* filtered migration requirements where only selected records should move
* mapping requirements where source fields do not naturally align with Shift4Shop-supported structures
* data-configuration requirements where values must be changed during migration
* Custom Platform source data, private database structures, or non-standard exports

Standard Add-ons can help when the need fits available settings and supported behavior for filtering, mapping, or configuration. Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, Custom Platform handling, and broader bespoke handling belong in Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for a Shift4Shop migration is not mainly about creating longer spreadsheets. It is about deciding which parts of the source store carry business meaning and making that meaning visible before migration execution. Catalog behavior, customer treatment, pricing rules, order interpretation, storefront content, SEO routes, integrations, and custom data should all be reviewed through the question of how they need to work in Shift4Shop after launch.

A well-prepared migration gives Demo Migration a stronger purpose. Instead of showing only that records can appear in the Target Platform, it helps reveal whether the target store can preserve the commercial, operational, and storefront logic that matters most.

Before starting the migration process, prepare a representative record set and use Demo Migration to test the parts of the store that carry the highest business meaning. If the sample exposes unclear mapping, filtering, configuration, custom-field, or integration requirements, use Live Chat to confirm whether the requirement fits standard service capability, a Standard Add-on, or Custom Service before moving into broader execution.

### FAQs <a href="#faqs" id="faqs"></a>

**Should every product be cleaned before migrating to Shift4Shop?**

No. Clean obvious duplicates, outdated records, and inconsistent values where the business decision is clear, but do not remove evidence needed to evaluate migration complexity. Complex products should be included in the review sample, not hidden from it.

**What customer information should be prepared for a Shift4Shop migration?**

Prepare more than names and email addresses. Customer groups, wholesale treatment, tax status, quantity pricing, account notes, approval context, CRM identifiers, and custom fields should be reviewed if they affect how buyers should be treated after migration.

**How should we choose Demo Migration samples?**

Choose samples that reveal real store behavior. Include simple records, high-revenue products, option-heavy products, wholesale or customer-type pricing examples, important customer groups, operationally meaningful orders, key CMS Pages or Blog Posts, and high-value URLs.

**Do entered entity counts filter which records migrate?**

No. Entered Product, Customer, Order, and Blog counts are used for Entity Points calculation and plan selection. They are not migration filters. All scanned records are migrated by default unless filtering is configured through the Data Filter Add-on or custom handling where required.

**When should custom fields be reviewed before migration?**

Custom fields should be reviewed whenever they affect product meaning, customer treatment, pricing, order interpretation, fulfillment, SEO, integration workflows, or staff operations. If those fields require custom migration logic adjustment or cannot be handled through standard service capability, the requirement belongs in Custom Service.

**Should old 3DCart references be removed before planning a Shift4Shop migration?**

Not automatically. Older 3DCart references can help explain source records, exports, URLs, or internal documentation. They should be treated as source context and checked against current Shift4Shop behavior where they affect the target plan.
