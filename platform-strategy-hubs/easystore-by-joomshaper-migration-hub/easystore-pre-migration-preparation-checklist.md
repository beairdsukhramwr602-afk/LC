# EasyStore Pre-Migration Preparation Checklist

EasyStore by JoomShaper migration preparation should begin before records are moved. Because EasyStore operates inside Joomla, the preparation work must cover both commerce data and the Joomla environment that will present, route, and support that data after migration.

A strong preparation process answers a practical question: what needs to be understood before Demo Migration so the result can be judged correctly? Product counts, customer counts, and order counts are not enough. The merchant should prepare catalog examples, Joomla site context, checkout assumptions, operational settings, custom-field evidence, extension dependencies, and service-path signals so the migration process can be tested against real business meaning.

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

### Preparation Priority 1: Confirm the Target Joomla and EasyStore Environment <a href="#preparation-priority-1-confirm-the-target-joomla-and-easystore-environment" id="preparation-priority-1-confirm-the-target-joomla-and-easystore-environment"></a>

The first preparation priority is confirming the target environment that will receive and display migrated data.

#### Check Joomla readiness <a href="#check-joomla-readiness" id="check-joomla-readiness"></a>

The target Joomla site should be ready enough for migration testing. The merchant or implementation team should confirm the Joomla version, administrator access, site structure direction, template direction, and any planned use of SP Page Builder, custom modules, or other Joomla extensions that will affect store presentation.

If the target Joomla site is still undecided, migration testing can become difficult to interpret. Products may migrate, but the merchant may not know where product pages should appear, how categories should be reached, or how the store should connect to menus and content paths.

#### Check EasyStore installation and configuration readiness <a href="#check-easystore-installation-and-configuration-readiness" id="check-easystore-installation-and-configuration-readiness"></a>

EasyStore by JoomShaper should be installed and accessible in the target environment before meaningful validation begins. Basic store settings should be reviewed so migrated data is not evaluated inside an incomplete or misleading setup.

At minimum, the team should understand the intended currency, store location assumptions, tax setup direction, shipping setup direction, payment setup direction, checkout expectations, account behavior, email notification expectations, and any payment or shipping integrations that must be configured separately.

#### Separate data migration from site implementation <a href="#separate-data-migration-from-site-implementation" id="separate-data-migration-from-site-implementation"></a>

A common planning mistake is expecting data migration to recreate the entire storefront experience. Migration can move supported commerce data according to the selected migration path and available behavior. Joomla menus, templates, landing pages, SP Page Builder layouts, custom modules, and design implementation may still require separate configuration or development.

This boundary should be documented before Demo Migration. It helps the merchant judge migrated data fairly while still planning the Joomla work needed for launch.

### Preparation Priority 2: Audit the Source Catalog as Selling Structure <a href="#preparation-priority-2-audit-the-source-catalog-as-selling-structure" id="preparation-priority-2-audit-the-source-catalog-as-selling-structure"></a>

The product catalog should be prepared as a selling system, not a spreadsheet of products.

#### Review product types and commercial meaning <a href="#review-product-types-and-commercial-meaning" id="review-product-types-and-commercial-meaning"></a>

The merchant should identify the main product types in the source store. Simple products, variant-heavy products, discounted products, image-rich products, products in multiple categories, products with special shipping requirements, and products with important inventory behavior should all be represented in the review.

For each group, the merchant should ask what a shopper must understand before buying and what the merchant must manage after launch. That usually includes product name, SKU, description, images, price, sale price, categories, tags, variants, inventory, shipping requirements, tax treatment, product status, and any custom product fields.

#### Review variants and option behavior <a href="#review-variants-and-option-behavior" id="review-variants-and-option-behavior"></a>

Variants need special attention because they affect shopper choice, pricing, inventory, order lines, and post-migration product management. The source store may represent options as variants, attributes, add-ons, custom fields, configurable products, option groups, or extension-specific structures.

Before migration, the merchant should identify products where option behavior is commercially important. These records should be included in Demo Migration so the team can confirm whether size, color, material, package, quantity, image, price, inventory, and order-line meaning remain understandable in EasyStore.

#### Clean obvious catalog disorder before testing <a href="#clean-obvious-catalog-disorder-before-testing" id="clean-obvious-catalog-disorder-before-testing"></a>

Preparation does not require perfect cleanup, but obvious catalog disorder should be identified. Duplicate categories, abandoned products, missing images, inconsistent SKUs, conflicting tags, outdated sale pricing, unclear stock values, broken product descriptions, and overlapping option names can make Demo Migration harder to interpret.

The merchant should decide whether to clean the source before migration, filter records where applicable, or use migration as a controlled opportunity to move only the records that should exist in the target store. If filtering is required and fits available behavior, the Data Filter Add-on may be relevant. If the cleanup requires transformation or custom interpretation, Custom Service should be reviewed.

### Preparation Priority 3: Prepare Categories, Tags, Navigation, and Discovery Paths <a href="#preparation-priority-3-prepare-categories-tags-navigation-and-discovery-paths" id="preparation-priority-3-prepare-categories-tags-navigation-and-discovery-paths"></a>

EasyStore by JoomShaper supports product organization through categories and tags, but the final discovery experience also depends on Joomla site structure.

#### Review product organization before migration <a href="#review-product-organization-before-migration" id="review-product-organization-before-migration"></a>

The merchant should review category hierarchy, category naming, product placement, tag usage, brand or collection logic, and any source-specific navigation patterns. Categories and tags should be meaningful enough to support browsing, filtering, internal linking, and merchandising after migration.

If the source store contains years of category changes, inactive collections, campaign categories, or duplicate navigation paths, the merchant should decide what should continue into EasyStore and what should be retired.

#### Identify high-value storefront paths <a href="#identify-high-value-storefront-paths" id="identify-high-value-storefront-paths"></a>

Important product pages, category pages, campaign pages, menu links, and content paths should be listed before migration. These may include pages with organic search traffic, paid advertising links, partner referrals, bookmarked customer paths, internal sales references, or important brand content.

The migration plan should separate migrated store records from Joomla routing and redirect work. Product and category data may migrate, while URL continuity, menu placement, landing page recreation, and redirects may need Joomla or implementation-team handling.

#### Prepare CMS Pages and Blog Posts separately <a href="#prepare-cms-pages-and-blog-posts-separately" id="prepare-cms-pages-and-blog-posts-separately"></a>

CMS Pages and Blog Posts should be reviewed as content assets, not automatically treated as product data. Some source content may belong in Joomla articles, menu items, modules, or page-builder layouts rather than EasyStore records.

The merchant should identify which policy pages, buying guides, brand stories, blog content, landing pages, and help pages need to remain available after launch. This helps prevent a store that has migrated products but loses the content structure that helped shoppers understand and reach those products.

### Preparation Priority 4: Prepare Customer and Order Evidence <a href="#preparation-priority-4-prepare-customer-and-order-evidence" id="preparation-priority-4-prepare-customer-and-order-evidence"></a>

Customer and order history should be prepared around operational usefulness.

#### Review customer account expectations <a href="#review-customer-account-expectations" id="review-customer-account-expectations"></a>

The merchant should review what customer records must support after migration. This may include customer identity, contact details, account association, order history, billing and shipping information, repeat purchase support, customer service lookup, and any customer grouping or loyalty context that existed in the source store.

If the source store has duplicate customers, guest orders, merged accounts, external customer IDs, membership fields, wholesale rules, or third-party CRM references, those should be identified before migration. Some may be outside standard service capability and may require mapping or Custom Service review.

#### Choose representative order samples <a href="#choose-representative-order-samples" id="choose-representative-order-samples"></a>

Order samples should include more than ordinary paid orders. Useful samples may include recent orders, older orders, orders with multiple products, orders with variants, orders with discounts, orders with tax, orders with shipping charges, refunded orders, cancelled orders, failed or pending orders if relevant, and orders connected to important customers.

The merchant should also identify whether historical orders need to support customer service, accounting reference, fulfillment review, warranty questions, repeat buying, or reporting. These expectations influence how Demo Migration results should be reviewed.

#### Document custom order statuses and external references <a href="#document-custom-order-statuses-and-external-references" id="document-custom-order-statuses-and-external-references"></a>

Order history becomes harder to migrate cleanly when the source store uses custom statuses, fulfillment-system IDs, payment-provider references, subscription references, marketplace order numbers, ERP identifiers, or third-party shipping data.

These details should be documented before execution. If they are expected to appear or behave in a specific way inside EasyStore by JoomShaper, the project may need Advanced Data Mapping, Advanced Data Configure, or Custom Service review.

### Preparation Priority 5: Document Checkout, Tax, Shipping, Payment, and Coupon Rules <a href="#preparation-priority-5-document-checkout-tax-shipping-payment-and-coupon-rules" id="preparation-priority-5-document-checkout-tax-shipping-payment-and-coupon-rules"></a>

Checkout-related preparation should distinguish between historical data, target settings, and live operational behavior.

#### Prepare tax and shipping assumptions <a href="#prepare-tax-and-shipping-assumptions" id="prepare-tax-and-shipping-assumptions"></a>

The merchant should document current tax regions, tax rates, shipping zones, shipping methods, delivery methods, free shipping rules, product-based shipping behavior, weight or dimension requirements, and region-specific rules that matter after launch.

Some of this information may be stored as source configuration rather than migratable records. Some may need to be recreated inside EasyStore settings. Some may need deeper review if the source uses custom code, extensions, or third-party services to calculate rates or taxes.

#### Prepare payment and checkout expectations <a href="#prepare-payment-and-checkout-expectations" id="prepare-payment-and-checkout-expectations"></a>

Payment migration should not be confused with payment gateway configuration. Historical order payment context may be useful for reference, but live payment processing depends on target gateway setup, credentials, configuration, and EasyStore-supported payment behavior.

The merchant should document expected payment methods, order-status behavior, manual payment needs, refund expectations, checkout fields, guest checkout expectations, and any third-party checkout dependencies. The Demo Migration should then be reviewed with a clear understanding of what data can be migrated and what must be configured in the target store.

#### Prepare coupon and discount examples <a href="#prepare-coupon-and-discount-examples" id="prepare-coupon-and-discount-examples"></a>

Coupons and discounts often carry business meaning that is easy to overlook. The merchant should identify active coupons, expired coupons that matter historically, free shipping coupons, sale-price behavior, product-specific discounts, order-level discounts, and any source-specific promotion rules.

Representative coupon and discount examples should be included in Demo Migration review where supported. If the source store uses complex promotion engines or third-party discount logic, the expected outcome should be reviewed before assuming standard migration can preserve the full rule behavior.

### Preparation Priority 6: Inventory Extensions, Custom Fields, and Custom Source Data <a href="#preparation-priority-6-inventory-extensions-custom-fields-and-custom-source-data" id="preparation-priority-6-inventory-extensions-custom-fields-and-custom-source-data"></a>

Custom and extension-owned data should be identified before the migration approach is chosen.

#### Build a source behavior inventory <a href="#build-a-source-behavior-inventory" id="build-a-source-behavior-inventory"></a>

The merchant should list the source extensions, apps, plugins, custom fields, custom tables, custom checkout fields, ERP links, CRM links, fulfillment services, marketplace connectors, analytics scripts, membership systems, subscription services, and custom Joomla or source-platform development that affects the store.

The inventory should explain what each item does, which records it affects, and whether the information must appear in EasyStore after migration. The important question is not whether a feature exists in the source. The important question is whether the business requires that meaning to survive migration.

#### Identify custom data that should not be treated as standard <a href="#identify-custom-data-that-should-not-be-treated-as-standard" id="identify-custom-data-that-should-not-be-treated-as-standard"></a>

Custom fields and extension-owned records may appear near standard products, customers, or orders, but that does not make them standard migration data. Examples may include product badges, supplier IDs, marketplace sync fields, customer membership flags, wholesale labels, subscription references, delivery instructions, custom invoice fields, or external fulfillment identifiers.

If these fields are important, the merchant should prepare examples and expected outcomes. Clear mapping needs may fit Advanced Data Mapping. Data configuration or value adjustment may fit Advanced Data Configure. Unsupported structures, Custom Platform data, or bespoke logic should be reviewed under Custom Service.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

The preparation sequence should move from platform readiness to data meaning, then from data meaning to service-path confirmation.

#### Step 1: Confirm the target Joomla and EasyStore setup <a href="#step-1-confirm-the-target-joomla-and-easystore-setup" id="step-1-confirm-the-target-joomla-and-easystore-setup"></a>

Confirm Joomla access, EasyStore readiness, basic store settings, intended template direction, SP Page Builder involvement, menu direction, account behavior, and launch expectations. This creates the environment context for migration testing.

#### Step 2: Audit the source store by business meaning <a href="#step-2-audit-the-source-store-by-business-meaning" id="step-2-audit-the-source-store-by-business-meaning"></a>

Review products, variants, categories, tags, customers, orders, coupons, reviews, tax context, shipping context, payment context, CMS Pages, Blog Posts, and custom data. The audit should focus on how these records are used by shoppers, administrators, customer service, fulfillment, and reporting.

#### Step 3: Mark what is standard, configurable, or custom <a href="#step-3-mark-what-is-standard-configurable-or-custom" id="step-3-mark-what-is-standard-configurable-or-custom"></a>

Classify each important requirement into one of three groups: supported migration data, EasyStore or Joomla configuration, or custom/extension-owned behavior requiring deeper review. This prevents migration expectations from becoming too broad or unclear.

#### Step 4: Choose Demo Migration samples <a href="#step-4-choose-demo-migration-samples" id="step-4-choose-demo-migration-samples"></a>

Select records that reveal structure. The sample set should include ordinary records and edge cases. It should not be limited to clean or easy products.

#### Step 5: Review service-path signals before Full Migration <a href="#step-5-review-service-path-signals-before-full-migration" id="step-5-review-service-path-signals-before-full-migration"></a>

Use the preparation findings and Demo Migration results to confirm whether Standard Service, Managed Service, Add-ons, or Custom Service best match the migration burden.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should include records that make the EasyStore by JoomShaper result measurable. The sample should not be chosen only for convenience.

| Sample area                    | Recommended examples                                                                                               | What the sample should prove                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| Products                       | Simple products, variant-heavy products, image-rich products, discounted products, products in multiple categories | Products remain sellable, understandable, organized, and manageable in EasyStore.                    |
| Categories and tags            | Main categories, deep categories, high-traffic categories, important tags                                          | Product discovery can be planned through EasyStore organization and Joomla navigation.               |
| Customers                      | Registered customers, guest-related records if relevant, duplicate-prone customers, important repeat buyers        | Customer identity and history remain useful after migration.                                         |
| Orders                         | Recent orders, older orders, refunded orders, discounted orders, variant orders, orders with tax and shipping      | Historical orders remain readable for service, reporting, fulfillment reference, and account review. |
| Coupons and discounts          | Active coupons, free shipping coupons, sale-price examples, source-specific discount examples                      | Promotion data can be interpreted correctly or flagged for configuration review.                     |
| Joomla and storefront context  | Key product routes, category paths, menu links, landing pages, CMS Pages, Blog Posts                               | Data migration and Joomla site implementation expectations are separated clearly.                    |
| Custom or extension-owned data | Custom product fields, external IDs, third-party fields, unusual order statuses, unsupported source behavior       | Mapping, Add-on, or Custom Service needs are identified before Full Migration.                       |

A strong sample set should include records the merchant actually cares about after launch. If a record would create a launch problem when handled incorrectly, it belongs in Demo Migration review.

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

Custom Platform sources and custom source structures require earlier evidence. The merchant should not wait for Full Migration to discover that key source data is outside ordinary supported behavior.

#### What to prepare for Custom Platform sources <a href="#what-to-prepare-for-custom-platform-sources" id="what-to-prepare-for-custom-platform-sources"></a>

For a Custom Platform source, prepare exports, database structure notes if available, screenshots, field definitions, source admin examples, sample records, and expected target outcomes. The evidence should show how products, customers, orders, categories, URLs, discounts, and custom fields currently behave.

Custom Platform handling points to Custom Service. The review should clarify whether the migration requires custom migration logic adjustment, bespoke transformation, Tailored Add-ons, Custom Add-ons, or broader project-specific handling.

#### What to prepare for custom fields and unsupported source behavior <a href="#what-to-prepare-for-custom-fields-and-unsupported-source-behavior" id="what-to-prepare-for-custom-fields-and-unsupported-source-behavior"></a>

For custom fields, prepare a list of field names, field meanings, affected records, sample values, and target expectations. For unsupported extension data, prepare screenshots, exports, extension names, and examples of how the information is used operationally.

This preparation helps separate three cases: data that can be migrated through available behavior, data that can be handled with Add-on support, and data that requires Custom Service.

### What to Escalate Before Execution <a href="#what-to-escalate-before-execution" id="what-to-escalate-before-execution"></a>

Some findings should be reviewed before the migration process continues.

#### Escalate unclear platform readiness <a href="#escalate-unclear-platform-readiness" id="escalate-unclear-platform-readiness"></a>

If the target Joomla site, EasyStore setup, template direction, menu structure, or SP Page Builder involvement is not ready enough for testing, the team should resolve those assumptions before judging Demo Migration.

#### Escalate catalog structures that carry hidden selling logic <a href="#escalate-catalog-structures-that-carry-hidden-selling-logic" id="escalate-catalog-structures-that-carry-hidden-selling-logic"></a>

Products with bundles, option-level pricing, option-level inventory, digital delivery rules, subscription references, membership conditions, supplier-controlled data, or custom display behavior should be reviewed before assuming standard product migration is enough.

#### Escalate checkout and operational behavior that depends on configuration or custom logic <a href="#escalate-checkout-and-operational-behavior-that-depends-on-configuration-or-custom-logic" id="escalate-checkout-and-operational-behavior-that-depends-on-configuration-or-custom-logic"></a>

Tax, shipping, payment, checkout, coupon, refund, and order-status behavior should be escalated when the merchant expects source-specific rules to continue after migration but those rules are not clearly represented as supported migrated data.

#### Escalate custom or third-party data that affects launch quality <a href="#escalate-custom-or-third-party-data-that-affects-launch-quality" id="escalate-custom-or-third-party-data-that-affects-launch-quality"></a>

Custom fields, external identifiers, ERP references, marketplace data, CRM fields, fulfillment references, source extension tables, or Custom Platform data should be escalated when the merchant expects them to affect the EasyStore result.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for EasyStore by JoomShaper migration means preparing both store data and Joomla context. The merchant should know what the future Joomla store is expected to do, which EasyStore records must carry commercial meaning, which content and route decisions belong to Joomla implementation, and which source behaviors require mapping, configuration, Add-on, or Custom Service review.

The strongest preparation work produces a clear Demo Migration sample set. That sample should prove product sellability, variant meaning, category organization, customer readability, order usefulness, coupon and discount interpretation, checkout-related assumptions, and the boundary between migrated data and Joomla configuration. When these areas are prepared before execution, the migration process becomes easier to test, explain, and correct.

Before running Full Migration to EasyStore by JoomShaper, use Demo Migration and Live Chat to confirm whether your source data, Joomla setup, EasyStore configuration, Add-ons, and service approach match the result you expect. If the source includes custom fields, unsupported extension data, Custom Platform records, unusual checkout logic, or source-specific order meaning, confirm those requirements before treating the migration as standard.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to EasyStore by JoomShaper?**

Start with the target Joomla and EasyStore environment. Confirm Joomla access, EasyStore readiness, intended store settings, menu direction, template or SP Page Builder involvement, and the basic structure of the future store. Without that context, migrated data can be difficult to evaluate.

**Should product cleanup happen before Demo Migration?**

Obvious catalog problems should be identified before Demo Migration. The merchant may choose to clean source data first, migrate only selected records where filtering fits available behavior, or use Demo Migration to expose the issues that need cleanup. The key is to avoid judging unclear source data as a target-platform migration problem.

**Which records should be included in an EasyStore by JoomShaper Demo Migration sample?**

The sample should include simple products, variant-heavy products, image-rich products, important categories, representative customers, recent and older orders, discounted orders, refunded orders if available, tax and shipping examples, coupons, and records affected by custom fields or extensions.

**Are tax, shipping, and payment settings migrated as ordinary data?**

Not always. Some tax, shipping, payment, checkout, email, and gateway behavior may need to be configured inside EasyStore or Joomla after migration. Historical order context may migrate differently from live operational settings. These areas should be documented and reviewed before Full Migration.

**When should Custom Service be reviewed during preparation?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported extension data, custom fields, third-party identifiers, bespoke product logic, unusual order structures, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment that goes beyond standard service capability.
