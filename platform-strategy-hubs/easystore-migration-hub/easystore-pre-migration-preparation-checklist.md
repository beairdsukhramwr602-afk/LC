# EasyStore Pre-Migration Preparation Checklist

EasyStore by JoomShaper migration preparation should begin with one practical assumption: the store is moving into a Joomla e-commerce extension environment, not into an isolated commerce system. Products, categories, customers, orders, coupons, inventory, tax, shipping, payments, checkout behavior, Joomla menus, templates, modules, content pages, and SP Page Builder layouts may all affect whether the migrated store is usable after launch.

A robust preparation process does not aim to resolve every implementation detail before migration begins. It identifies what the migration must preserve, what the Joomla site must support, what the merchant must configure after migration, and what requires deeper review before the migration path is considered straightforward.

### What Preparation Should Accomplish <a href="#what-preparation-should-accomplish" id="what-preparation-should-accomplish"></a>

Pre-migration preparation is not only administrative cleanup. It creates the reference point for judging whether EasyStore by JoomShaper can represent the future store correctly.

For this platform, preparation should accomplish five things.

#### Confirm the Joomla-based target environment <a href="#confirm-the-joomla-based-target-environment" id="confirm-the-joomla-based-target-environment"></a>

The merchant should confirm that the future store is intended to operate inside Joomla and that the Joomla environment is ready enough to support migration testing. EasyStore by JoomShaper is not evaluated in isolation. Product pages, category pages, menus, templates, modules, SP Page Builder layouts, account areas, checkout flow, and content paths may all shape the final store experience.

This does not mean every design decision must be final before migration starts. It does mean the implementation team should know where EasyStore data will appear and which Joomla structures are expected to support store discovery.

#### Clarify what belongs to EasyStore data <a href="#clarify-what-belongs-to-easystore-data" id="clarify-what-belongs-to-easystore-data"></a>

The source store may contain commerce records, CMS Pages, Blog Posts, landing pages, menu links, product guides, marketing sections, and extension-owned content. Not every piece of source material should become EasyStore product or category data.

Before migration, the merchant should separate commerce records from site content. Products, variants, categories, customers, orders, coupons, reviews, tax context, shipping context, and payment context should be reviewed as EasyStore-related data. Brand pages, buying guides, policy pages, campaign landing pages, and editorial content may need Joomla content planning or separate implementation work.

#### Identify what must be configured after migration <a href="#identify-what-must-be-configured-after-migration" id="identify-what-must-be-configured-after-migration"></a>

Some store behavior is better understood as target configuration rather than migrated data. Tax rates, shipping methods, payment gateways, checkout settings, email notifications, currency behavior, display choices, analytics, and some account behavior may require EasyStore or Joomla configuration after migration.

The preparation task is to identify which expected outcomes depend on migrated records and which depend on target setup. This prevents the Demo Migration from being judged against behavior that actually belongs to post-migration configuration.

#### Reveal custom or extension-owned meaning early <a href="#reveal-custom-or-extension-owned-meaning-early" id="reveal-custom-or-extension-owned-meaning-early"></a>

EasyStore by JoomShaper migrations become more sensitive when source behavior is controlled by custom fields, source extensions, third-party integrations, custom order statuses, product option logic, external identifiers, ERP references, subscription systems, membership rules, marketplace connectors, or bespoke Joomla development.

These details should be documented before the migration path is treated as straightforward. Some custom or extension-owned behavior may be handled through available settings or supported behavior. Other cases may need Advanced Data Mapping, Advanced Data Configure, Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, or broader Custom Service review.

#### Choose Demo Migration samples deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the records that reveal whether EasyStore by JoomShaper can preserve operating meaning. Random samples are rarely enough. The merchant should choose samples that expose product structure, variant behavior, category placement, customer identity, order history, discount logic, tax and shipping context, refunds, and Joomla storefront expectations.

The purpose is not to prove that every record is final during Demo Migration. The purpose is to reveal whether the migration assumptions are sound before Full Migration.

### Preparation Priority 1: Confirm the Joomla and EasyStore Foundation <a href="#preparation-priority-1-confirm-the-joomla-and-easystore-foundation" id="preparation-priority-1-confirm-the-joomla-and-easystore-foundation"></a>

Before reviewing source data, confirm that the target environment is conceptually ready. EasyStore by JoomShaper operates inside Joomla, so the target project should have a clear site foundation, even if design work is not complete.

#### Confirm the future Joomla site model <a href="#confirm-the-future-joomla-site-model" id="confirm-the-future-joomla-site-model"></a>

The merchant should know whether the future store will be a compact product catalog, a content-rich product site, a brand-led storefront, a service-and-product website, or a more customized Joomla commerce implementation. This decision affects product presentation, navigation, CMS Pages, Blog Posts, landing pages, menu planning, and the level of storefront work needed outside the migration itself.

If the future Joomla site model is vague, migration results become harder to evaluate. A product may migrate correctly as data, but the merchant may still be unsure where it belongs in the site, how shoppers will reach it, or whether the page layout supports the intended buying journey.

#### Confirm EasyStore configuration readiness <a href="#confirm-easystore-configuration-readiness" id="confirm-easystore-configuration-readiness"></a>

The target EasyStore environment should be reviewed for the store settings that influence migrated data interpretation. This includes currency assumptions, checkout behavior, tax setup, shipping setup, payment setup, coupon behavior, inventory expectations, customer account handling, order status expectations, analytics expectations, and any store administration preferences that affect the launch plan.

Not every setting needs to be final before Demo Migration. However, the merchant should know which settings are expected to affect validation. Otherwise, a migration issue may be confused with an unfinished EasyStore configuration decision.

#### Separate data migration from site implementation <a href="#separate-data-migration-from-site-implementation" id="separate-data-migration-from-site-implementation"></a>

A migration can move supported commerce data, but Joomla site implementation may still require separate work. Menus, templates, modules, SP Page Builder sections, landing pages, internal links, redirects, design layouts, and content placement should be planned as part of the broader target project.

This distinction matters because the Demo Migration should be judged against the right expectation. If a page layout has not been built yet, the issue is not necessarily migration failure. If a product does not carry the right variant, category, image, or price meaning, the issue may be migration-related and should be reviewed through the migration path.

### Preparation Priority 2: Audit the Product Catalog as Selling Structure <a href="#preparation-priority-2-audit-the-product-catalog-as-selling-structure" id="preparation-priority-2-audit-the-product-catalog-as-selling-structure"></a>

Product preparation should focus on selling meaning, not only product count. The merchant should understand how source products are organized, how shoppers choose options, how stock is managed, how categories support discovery, and how product information appears on the storefront.

#### Review product types and commercial patterns <a href="#review-product-types-and-commercial-patterns" id="review-product-types-and-commercial-patterns"></a>

The product audit should identify the main commercial patterns in the source store. At minimum, review simple products, products with variants, products with multiple images, products in multiple categories, products with sale pricing, products with unusual shipping needs, products with inventory sensitivity, products with custom fields, and products that represent major revenue lines.

This helps the merchant avoid validating only easy products. A Demo Migration that includes only simple products may not reveal variant, inventory, image, category, price, or custom-field problems.

#### Confirm variant and option behavior <a href="#confirm-variant-and-option-behavior" id="confirm-variant-and-option-behavior"></a>

Variants and options deserve early review because they affect both shopper selection and order interpretation. A merchant should document whether product choices are based on size, color, material, package, subscription-like choices, add-ons, bundles, personalization, option-level price changes, option-level inventory, option-specific images, or custom product fields.

If the source platform uses product options in a way that does not cleanly match EasyStore behavior, the team should review whether standard mapping is enough or whether Advanced Data Mapping, Advanced Data Configure, or Custom Service should be considered.

#### Clean category, tag, brand, and collection logic <a href="#clean-category-tag-brand-and-collection-logic" id="clean-category-tag-brand-and-collection-logic"></a>

EasyStore by JoomShaper planning should include category and discovery structure. Categories, tags, brands, and collections can help customers browse and compare products, but only if the source structure is meaningful.

Before migration, identify duplicate categories, outdated categories, hidden categories, products assigned to the wrong sections, inconsistent tags, brand values that were used as filters, and collections that represent marketing groupings rather than permanent catalog structure. These findings do not always require data cleanup before migration, but they should be known before Demo Migration samples are selected.

#### Gather product evidence for review <a href="#gather-product-evidence-for-review" id="gather-product-evidence-for-review"></a>

Preparation should include examples, exports, screenshots, and notes that show how important products behave in the Source Platform. Useful evidence includes product detail screenshots, option screenshots, variant pricing examples, product image examples, category placement screenshots, inventory examples, shipping-related product fields, and examples of custom product fields or extension-owned product data.

| Product preparation area    | What to gather                                                                        | Why it matters                                                                    |
| --------------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Simple products             | Representative products with standard price, image, category, and inventory behavior  | Establishes the baseline migration result.                                        |
| Variant-heavy products      | Products with important options, variant prices, option images, or option-level stock | Reveals whether shopper selection and order line meaning remain understandable.   |
| Category-sensitive products | Products assigned to multiple categories, tags, brands, or collections                | Shows whether discovery and storefront organization remain useful.                |
| Products with custom data   | Source fields created by extensions, custom code, imports, or manual workarounds      | Helps identify whether Add-on review or Custom Service is needed.                 |
| High-value products         | Best sellers, campaign products, seasonal products, or revenue-critical items         | Ensures validation covers commercially important records, not only easy examples. |

This table can be used as the core product sample checklist for Demo Migration planning.

### Preparation Priority 3: Review Customer and Order History Before Migration <a href="#preparation-priority-3-review-customer-and-order-history-before-migration" id="preparation-priority-3-review-customer-and-order-history-before-migration"></a>

Customer and order preparation should focus on operational usefulness. Historical data may be needed for support, repeat orders, finance checks, refund reference, warranty review, fulfillment questions, or customer account continuity.

#### Confirm customer identity and account expectations <a href="#confirm-customer-identity-and-account-expectations" id="confirm-customer-identity-and-account-expectations"></a>

Review how customers are identified in the source store. Important fields may include name, email address, billing address, shipping address, phone number, company information, account status, customer group, newsletter preference, membership field, tax identifier, or source-specific customer attributes.

Not every source attribute will necessarily map as a standard EasyStore customer field. If customer meaning depends on custom fields, external identifiers, loyalty data, B2B fields, membership records, or app-owned metadata, those areas should be reviewed before migration assumptions are finalized.

#### Review order history as business evidence <a href="#review-order-history-as-business-evidence" id="review-order-history-as-business-evidence"></a>

Order history should be prepared with real use cases in mind. A useful order sample set should include recent orders, older orders, orders with multiple products, orders with variant products, orders with discounts, refunded orders, cancelled orders if relevant, tax examples, shipping examples, different payment states, and orders associated with important customers.

The goal is not to migrate every historical nuance into an identical operating workflow. The goal is to preserve enough meaning for the merchant to understand what the customer bought, what they paid, how totals were calculated, how the order was fulfilled, and how the order should be interpreted after migration.

#### Identify custom order and fulfillment meaning <a href="#identify-custom-order-and-fulfillment-meaning" id="identify-custom-order-and-fulfillment-meaning"></a>

Some source platforms or extensions store important order information outside ordinary order fields. Examples include external fulfillment IDs, ERP references, marketplace order IDs, custom status labels, staff notes, payment gateway references, fraud review flags, subscription references, return authorization data, or delivery scheduling fields.

If this information is important after migration, it should be documented early. Some details may be supported by standard migration behavior, some may require mapping review, and some may require Custom Service if the data structure is custom, unsupported, external, or dependent on bespoke source logic.

### Preparation Priority 4: Document Storefront, Joomla, and SEO Dependencies <a href="#preparation-priority-4-document-storefront-joomla-and-seo-dependencies" id="preparation-priority-4-document-storefront-joomla-and-seo-dependencies"></a>

EasyStore by JoomShaper migrations need storefront preparation because the final store experience depends on more than migrated records. Joomla menus, page layouts, templates, modules, content paths, product routes, category routes, and internal links may shape how shoppers reach the catalog.

#### Identify high-value routes and entry points <a href="#identify-high-value-routes-and-entry-points" id="identify-high-value-routes-and-entry-points"></a>

The merchant should identify pages and URLs that matter for traffic, revenue, customer service, or campaigns. This may include best-selling product pages, important category pages, campaign landing pages, content pages that lead to products, CMS Pages, Blog Posts, account pages, checkout entry points, and support pages that link to store items.

This list helps separate two different tasks: preserving commerce data and planning storefront continuity. If important routes change, redirects and navigation updates should be planned as part of the Joomla implementation.

#### Review Joomla menus and page-builder dependencies <a href="#review-joomla-menus-and-page-builder-dependencies" id="review-joomla-menus-and-page-builder-dependencies"></a>

If the target store will use SP Page Builder, custom templates, custom modules, or specialized Joomla layouts, the implementation team should identify which parts of the storefront will be rebuilt or configured outside the data migration. Product and category data can support the new storefront, but page composition, layout sections, menu placement, and content relationships may require Joomla-side work.

Preparation should therefore document whether the old store’s content and layout are being replicated, simplified, redesigned, or replaced. Without this clarity, stakeholders may expect the migration to recreate presentation behavior that belongs to the Joomla implementation layer.

#### Map content responsibilities <a href="#map-content-responsibilities" id="map-content-responsibilities"></a>

Some content should become EasyStore product or category information. Other content may belong in Joomla articles, CMS Pages, Blog Posts, landing pages, menu items, template sections, or modules. Preparation should define where important content belongs so it is not forced into the wrong data type.

This is especially important for stores where product education, guides, comparisons, FAQs, blog content, or service pages influence conversion. The migration should preserve store data while the Joomla content plan supports the customer journey around that data.

### Preparation Priority 5: Clarify Checkout, Tax, Shipping, Payment, Coupon, and Refund Behavior <a href="#preparation-priority-5-clarify-checkout-tax-shipping-payment-coupon-and-refund-behavior" id="preparation-priority-5-clarify-checkout-tax-shipping-payment-coupon-and-refund-behavior"></a>

Configuration-sensitive behavior should be documented before migration because many launch problems come from assuming that settings behave like ordinary records. EasyStore can manage store operations, but the merchant still needs to understand which behaviors are migrated as data, which are configured in the target, and which require deeper review.

#### Prepare tax and shipping examples <a href="#prepare-tax-and-shipping-examples" id="prepare-tax-and-shipping-examples"></a>

The merchant should collect representative tax and shipping examples from the source store. Useful examples include domestic orders, international orders if applicable, orders with shipping discounts, orders with free shipping, product-specific shipping behavior, region-based tax, tax-exempt examples, and orders where tax or shipping differs from the standard rule.

These examples help the merchant evaluate whether migrated order history remains understandable and whether target configuration supports future checkout behavior.

#### Prepare coupon and discount examples <a href="#prepare-coupon-and-discount-examples" id="prepare-coupon-and-discount-examples"></a>

Coupons and discounts should be reviewed for rule meaning. A simple coupon code may be straightforward. More complex cases may involve minimum order totals, customer group restrictions, product-specific discounts, category-specific discounts, usage limits, free shipping, date limits, automatic discounts, or extension-owned promotional logic.

If the source promotion behavior is complex, the merchant should document which rules need to exist after launch and which historical discount details only need to remain readable in migrated orders.

#### Prepare payment and refund context <a href="#prepare-payment-and-refund-context" id="prepare-payment-and-refund-context"></a>

Payment and refund records should be reviewed for operational meaning. The merchant should identify payment gateways, payment statuses, transaction references, refund examples, partial refund examples, failed payment examples if relevant, and any payment behavior controlled by a third-party extension or gateway integration.

Payment gateway setup itself is usually a target configuration and operational readiness task, not merely a record migration question. If payment references, refund logic, or status mapping are critical, representative examples should be included in validation.

### Preparation Priority 6: Inventory Extensions, Custom Fields, and Non-Standard Data <a href="#preparation-priority-6-inventory-extensions-custom-fields-and-non-standard-data" id="preparation-priority-6-inventory-extensions-custom-fields-and-non-standard-data"></a>

The source store may include data or behavior created by extensions, plugins, custom code, third-party services, external databases, ERP systems, marketing tools, membership systems, marketplace connectors, or custom Joomla development. These areas should be inventoried before migration because they may not appear clearly in a standard export.

#### Build an extension and custom-data inventory <a href="#build-an-extension-and-custom-data-inventory" id="build-an-extension-and-custom-data-inventory"></a>

Create a list of source extensions and custom data areas that affect products, customers, orders, shipping, tax, checkout, discounts, content, search, SEO, analytics, integrations, or fulfillment. For each item, identify whether it creates data, changes behavior, only affects display, or connects to an external system.

This inventory does not need to be overly technical, but it should be specific enough to support service-path review.

| Custom or extension area    | Preparation question                                                                        | Likely service implication                                                  |
| --------------------------- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Custom product fields       | Do these fields need to appear in EasyStore records or only remain as reference data?       | May need Advanced Data Mapping, Advanced Data Configure, or Custom Service. |
| Extension-owned order data  | Is the data part of customer service, fulfillment, finance, or compliance review?           | May require mapping review or Custom Service.                               |
| External identifiers        | Are IDs from ERP, marketplace, payment, fulfillment, or CRM systems needed after migration? | Often requires deeper review before execution.                              |
| Bespoke source logic        | Does source behavior depend on custom code or non-standard relationships?                   | Usually a Custom Service signal.                                            |
| Custom Platform source data | Is the source structure outside standard supported platform assumptions?                    | Custom Service should be reviewed.                                          |

Custom Service should be considered when the migration requires custom migration logic adjustment, unsupported extension data handling, Custom Platform interpretation, third-party data, Tailored Add-ons, Custom Add-ons, or broader bespoke transformation.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

Preparation works best when it follows a sequence. The merchant does not need to perfect every data issue before migration, but the most important unknowns should be identified before Demo Migration.

#### Step 1: Confirm the target operating model <a href="#step-1-confirm-the-target-operating-model" id="step-1-confirm-the-target-operating-model"></a>

Confirm why EasyStore by JoomShaper is the Target Platform and how Joomla will support the future store. Decide whether the target site will prioritize a simple catalog, a content-rich storefront, a brand-led experience, a service-and-product model, or a more customized Joomla commerce project.

#### Step 2: Review the source catalog structure <a href="#step-2-review-the-source-catalog-structure" id="step-2-review-the-source-catalog-structure"></a>

Identify product types, category structure, tags, brands, collections, variants, images, prices, inventory, custom product fields, and important product examples. Flag complex products before the Demo Migration sample is selected.

#### Step 3: Review customers and order history <a href="#step-3-review-customers-and-order-history" id="step-3-review-customers-and-order-history"></a>

Identify important customer records and order samples. Include orders with discounts, taxes, shipping, refunds, variant products, multiple products, different statuses, and payment states.

#### Step 4: Review storefront and content dependencies <a href="#step-4-review-storefront-and-content-dependencies" id="step-4-review-storefront-and-content-dependencies"></a>

List important URLs, menus, landing pages, CMS Pages, Blog Posts, product routes, category routes, internal links, SP Page Builder sections, templates, and modules that affect the customer journey.

#### Step 5: Review configuration-sensitive behavior <a href="#step-5-review-configuration-sensitive-behavior" id="step-5-review-configuration-sensitive-behavior"></a>

Document tax, shipping, payment, checkout, coupon, refund, inventory, analytics, notification, and account behavior that may need target configuration or service review.

#### Step 6: Inventory custom and extension-owned data <a href="#step-6-inventory-custom-and-extension-owned-data" id="step-6-inventory-custom-and-extension-owned-data"></a>

Identify custom fields, extension-owned data, third-party identifiers, ERP references, marketplace references, fulfillment references, external systems, and Custom Platform source data.

#### Step 7: Select Demo Migration samples deliberately <a href="#step-7-select-demo-migration-samples-deliberately" id="step-7-select-demo-migration-samples-deliberately"></a>

Choose samples that test meaning, not only record movement. The sample set should include easy records, difficult records, commercially important records, and records that reveal configuration or custom-data assumptions.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should be used as a proof tool. A weak sample only checks whether records appear. A strong sample checks whether records still make sense inside EasyStore by JoomShaper and the surrounding Joomla site structure.

| Sample type                | What to include                                                                               | What the sample should prove                                           |
| -------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Simple product             | A standard product with price, image, category, and inventory                                 | Baseline product migration is readable and sellable.                   |
| Variant-heavy product      | Product with important options, variant pricing, option images, or stock behavior             | Shopper choice and product management remain understandable.           |
| Category-sensitive product | Product assigned to important categories, tags, brands, or collections                        | Discovery structure is usable after migration.                         |
| Important customer         | Customer with complete profile and order history                                              | Account and history context remain useful.                             |
| Complex order              | Order with multiple products, variants, discount, tax, shipping, payment context, or refund   | Historical order meaning remains readable.                             |
| Content-connected path     | Product or category reached through Joomla content, menu, landing page, or internal link      | Storefront planning accounts for site navigation and customer journey. |
| Custom-data record         | Product, customer, or order with custom fields, extension-owned data, or external identifiers | Service-path review captures non-standard data before Full Migration.  |

A strong Demo Migration sample should be intentionally uneven. It should include ordinary records and difficult records. If all selected samples are simple, the test may not reveal the migration issues that matter most.

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

Custom Platform sources and custom source structures require earlier evidence. The merchant should not wait for Full Migration to discover that key source data is outside ordinary supported behavior.

#### What to prepare for Custom Platform sources <a href="#what-to-prepare-for-custom-platform-sources" id="what-to-prepare-for-custom-platform-sources"></a>

For a Custom Platform source, prepare exports, database structure notes if available, screenshots, field definitions, source admin examples, sample records, and expected target outcomes. The evidence should show how products, customers, orders, categories, URLs, discounts, and custom fields currently behave.

Custom Platform handling points to Custom Service. The review should clarify whether the migration requires custom migration logic adjustment, bespoke transformation, Tailored Add-ons, Custom Add-ons, or broader project-specific handling.

#### What to prepare for custom fields and unsupported source behavior <a href="#what-to-prepare-for-custom-fields-and-unsupported-source-behavior" id="what-to-prepare-for-custom-fields-and-unsupported-source-behavior"></a>

For custom fields, prepare a list of field names, field meanings, affected records, sample values, and target expectations. For unsupported extension data, prepare screenshots, exports, extension names, and examples of how the information is used operationally.

This preparation helps separate three cases: data that can be migrated through available behavior, data that can be handled with Add-on support, and data that requires Custom Service.

### What to Escalate Before Execution <a href="#what-to-escalate-before-execution" id="what-to-escalate-before-execution"></a>

Some findings should be reviewed before execution because they may change the service approach, Add-on needs, mapping assumptions, or Custom Service requirements.

Escalate early when the source store includes:

* Custom Platform source data.
* Unsupported extension-owned product, customer, order, checkout, or content data.
* Custom product fields that must remain usable after migration.
* Complex variant structures with option-level pricing, stock, images, or unusual relationships.
* Order history with custom statuses, external fulfillment references, ERP identifiers, marketplace identifiers, or custom payment references.
* Checkout, tax, shipping, coupon, refund, or payment behavior controlled by custom logic.
* Joomla-specific content or route dependencies that affect launch readiness.
* Requirements for Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

Escalation does not mean the migration cannot proceed. It means the merchant should not assume the project is a simple standard migration until the unusual structure is reviewed.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparation for EasyStore by JoomShaper migration should make the future Joomla store easier to evaluate. The merchant should understand the target Joomla environment, source product structure, variant behavior, customer and order meaning, storefront dependencies, configuration-sensitive behavior, and custom-data signals before relying on migration results.

A well-prepared migration does not treat EasyStore as a destination for record counts only. It treats products, customers, orders, categories, storefront paths, checkout behavior, and Joomla site structure as connected parts of the future store. That preparation gives Demo Migration results practical meaning and reduces the risk of discovering structural problems too late.

Before running Full Migration to EasyStore by JoomShaper, use Demo Migration to test the records that carry the most business meaning. If the source store includes custom fields, extension-owned data, Custom Platform source data, complex variants, unusual order structures, or configuration-sensitive checkout behavior, review those areas through Live Chat so the right Standard Service, Managed Service, Custom Service, and Add-on boundaries are clear before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to EasyStore by JoomShaper?**

Start by confirming the future Joomla site model and the EasyStore configuration expectations. Then review product structure, variants, categories, customers, orders, storefront routes, checkout behavior, tax, shipping, payment, coupon, refund, and custom-data areas.

**Should the Joomla site be ready before migration starts?**

The full Joomla implementation does not always need to be finished, but the target site model should be clear. Menus, templates, SP Page Builder layouts, CMS Pages, Blog Posts, and storefront routes may affect how migrated data is evaluated.

**What product samples should be used for Demo Migration?**

Use simple products, variant-heavy products, products with multiple images, products in important categories, discounted products, inventory-sensitive products, and products with custom fields or extension-owned data. The sample should test selling meaning, not only product presence.

**Why should order history be reviewed before migration?**

Order history may be needed for customer service, repeat purchase support, refund reference, warranty review, finance checks, or fulfillment questions. Orders with discounts, taxes, shipping, payment references, refunds, custom statuses, or variant products should be included in sample review.

**When should Custom Service be reviewed before migrating to EasyStore by JoomShaper?**

Custom Service should be reviewed when the source store includes Custom Platform data, unsupported extension-owned data, custom fields, external identifiers, bespoke product or order logic, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment beyond standard service capability.
