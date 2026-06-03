# J2Commerce 6 Data Model Differences

Migrating to J2Commerce 6 is not only a transfer of products, customers, and orders into another Joomla component. It is a translation into a newer native Joomla 6 commerce model, where product structure, variant behavior, customer records, order history, checkout rules, tax profiles, shipping methods, payment context, storefront rendering, API access, and plugin behavior may be organized differently from the Source Platform.

This matters because data that appears complete in an administration screen can still lose business meaning if it is interpreted through the wrong target structure. A product can exist but fail to represent its variants correctly. An order can appear but may lack the details needed for support or accounting reference. A customer can migrate but no longer connect cleanly to addresses, guest checkout history, or user-account behavior. A payment method or shipping method can be present as historical context, but still require configuration or replacement inside the target environment.

For J2Commerce 6, the central data-model question is: **what does each source record need to become inside a native Joomla 6 commerce architecture so the store remains understandable, operable, and launch-ready?**

### Core Structural Layers in J2Commerce 6 <a href="#core-structural-layers-in-j2commerce-6" id="core-structural-layers-in-j2commerce-6"></a>

J2Commerce 6 should be understood as a Joomla 6-native e-commerce component rather than a compatibility layer around the older J2Store v4 structure. The target model includes commercial records, Joomla site relationships, plugin/event behavior, frontend rendering choices, and integration surfaces that must work together.

| Structural layer                 | What it represents in J2Commerce 6                                                                                                                                                          | Migration interpretation                                                                                               |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Commerce component data          | Products, variants, categories, manufacturers, vendors, customers, addresses, orders, coupons, tax profiles, shipping methods, payment methods, currencies, countries, zones, and inventory | Source commerce records must be mapped into the target commerce structure, not only copied into visible fields.        |
| Joomla 6 site layer              | Menus, modules, templates, layouts, Smart Search, Schema.org output, user accounts, language handling, and Joomla webservices                                                               | Store data must make sense inside Joomla site behavior, discovery, navigation, and user experience.                    |
| Frontend framework layer         | Bootstrap 5, UIkit 3, or another implementation approach using the target storefront framework system                                                                                       | Product lists, product detail pages, cart, checkout, and account pages need rendering validation after data migration. |
| Plugin and app ecosystem         | Payment plugins, shipping plugins, app plugins, report plugins, system plugins, task plugins, console commands, and event subscribers                                                       | Legacy behavior should be translated into v6-compatible plugin or configuration expectations.                          |
| Integration and automation layer | REST API, webservices, reporting, scheduled tasks, action logs, possible MCP/API workflows, and third-party systems                                                                         | Migrated records may need to support external workflows beyond the storefront.                                         |
| Migration traceability layer     | For J2Store v4 sources, dry-run review, idmap records, and original source-table preservation                                                                                               | The meaning of migrated records should be traceable when the v4 migrator is part of the project.                       |

These layers should not be treated as separate topics during planning. In J2Commerce 6, a product may affect catalog display, variant selection, image behavior, inventory, checkout, tax, shipping, REST API usage, and storefront rendering. A strong migration plan identifies these relationships before judging whether the data model has been successfully translated.

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

Product migration to J2Commerce 6 should preserve how the business sells, not merely the names of the source product list. The product model may include products, variants, categories, manufacturers, vendors, custom fields, custom filters, downloadable files, images, inventory, coupons, discounts, and product discovery behavior.

#### Products become structured commercial records <a href="#products-become-structured-commercial-records" id="products-become-structured-commercial-records"></a>

A migrated product should answer practical questions for both shoppers and merchants. What is being sold? Which options can be selected? Which price applies? Which image should appear? Is the product in stock? Is it downloadable? Does it belong to a category, manufacturer, vendor, or filtered product list? Does it appear correctly in search, structured data, and API-connected workflows?

In a simpler source store, many of these relationships may be straightforward. In a mature source store, product meaning may be distributed across options, custom fields, app-controlled values, product attributes, external inventory systems, source-specific discount logic, or frontend-only display rules. Those details need to be deliberately translated into the target J2Commerce 6 structure.

#### Variants need more than option names <a href="#variants-need-more-than-option-names" id="variants-need-more-than-option-names"></a>

J2Commerce 6 places significant emphasis on modern variant behavior. Variant data should be validated as purchasing logic, not just as text labels. A product with color and size options may need distinct pricing, stock, images, SKU behavior, product-list rendering, detail-page behavior, and order-line interpretation.

The v6 sources describe flexible product variant handling and variant image swap behavior. That makes variant translation especially important. If the Source Platform has option-linked images, option-level inventory, variant-specific SKUs, bundled choices, or display-only options, the migration must clarify which parts can be represented as target variant behavior and which parts require configuration, Add-on review, or Custom Service review.

#### Categories, manufacturers, vendors, filters, and discovery carry navigation meaning <a href="#categories-manufacturers-vendors-filters-and-discovery-carry-navigation-meaning" id="categories-manufacturers-vendors-filters-and-discovery-carry-navigation-meaning"></a>

Categories and manufacturers are not just labels. They shape how shoppers browse the store, how menus are built, how product lists are filtered, and how search engines understand site structure. J2Commerce 6 also introduces a more modern product discovery experience through product categories, manufacturers, custom filters, Smart Search, and Schema. org-structured data.

A source category tree may need cleanup before migration if it contains duplicate categories, outdated seasonal categories, inconsistent manufacturer names, hidden navigation categories, or category structures created only to support an old template. The migration result should make product discovery clearer in the target store rather than preserving old clutter without purpose.

#### Product images and downloadable files affect trust and fulfillment <a href="#product-images-and-downloadable-files-affect-trust-and-fulfillment" id="product-images-and-downloadable-files-affect-trust-and-fulfillment"></a>

Product imagery is part of commercial meaning. J2Commerce 6’s modern image handling and product gallery expectations make image validation a core part of data-model translation. A migrated product should retain the correct main image, gallery images, variant-linked images where relevant, and image order where it matters to the shopper journey.

Downloadable files also need careful interpretation. A downloadable product is not just a product with a file attached. It may involve access rights, order completion behavior, customer download history, file availability, and post-purchase fulfillment expectations. If the source store handles downloads via custom apps, membership rules, or manual delivery, that behavior should be reviewed before assuming that ordinary product migration is sufficient.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

Customer data in J2Commerce 6 should preserve account identity, address usefulness, order history relationships, guest checkout context, and any customer-group or profile behavior that affects store operations.

#### Customers, addresses, and profiles must remain connected <a href="#customers-addresses-and-profiles-must-remain-connected" id="customers-addresses-and-profiles-must-remain-connected"></a>

A useful migrated customer record should connect the person or business to their addresses, orders, account history, and relevant store permissions. If the source store distinguishes billing and shipping addresses, guest checkout records, registered accounts, customer profiles, company details, tax identifiers, or multiple address entries, those details should be reviewed as part of customer meaning.

Customer records are often reused after launch for support, repeat orders, B2B review, marketing segmentation, and account-service requests. A migration that moves names and emails but weakens the connection between customers, addresses, and orders creates operational friction even when record counts match.

#### Guest checkout needs interpretation <a href="#guest-checkout-needs-interpretation" id="guest-checkout-needs-interpretation"></a>

J2Commerce 6 includes guest checkout behavior. Guest data can be easy to misread during migration because a guest order may include customer-like information without a persistent registered account. The target result should preserve the useful customer and order context without incorrectly converting every guest into a full account or losing address data needed for historical reference.

The right interpretation depends on the source structure. Some platforms store guest customers as normal customer records with flags. Others store guest details only on the order. Custom Platform sources may have no clean distinction. That distinction should be clarified before migration and validated after Demo Migration.

#### Customer groups and B2B meaning require precision <a href="#customer-groups-and-b2b-meaning-require-precision" id="customer-groups-and-b2b-meaning-require-precision"></a>

Customer groups, user group pricing, tax exemptions, purchase-order workflows, and B2B rules can create meaning that is not visible in basic customer exports. If the source store uses groups for wholesale pricing, loyalty status, tax handling, account approval, or restricted payment methods, those rules should be treated as business logic, not ordinary customer labels.

In J2Commerce 6, customer-group meaning may affect pricing, payment expectations, tax behavior, and order interpretation. Any source group logic that depends on custom code, app plugins, ERP identifiers, or external approval workflows should be reviewed before it is treated as standard customer migration.

### Order and Historical Transaction Meaning <a href="#order-and-historical-transaction-meaning" id="order-and-historical-transaction-meaning"></a>

Order history is usually one of the most sensitive areas of migration because merchants rely on it after launch for support, revenue review, fulfillment questions, warranty references, refunds, and customer-service continuity.

#### Orders should preserve commercial readability <a href="#orders-should-preserve-commercial-readability" id="orders-should-preserve-commercial-readability"></a>

A migrated order should remain understandable as a historical transaction. That means order numbers, order dates, customer links, billing and shipping addresses, products, variant selections, quantities, line-item prices, discounts, coupons, tax, shipping charges, payment method, shipping method, order status, comments, and history should be interpretable in the target store.

The goal is not to make old orders behave exactly like new J2Commerce 6 orders in every operational workflow. The goal is to preserve enough structure and context for the merchant to understand what happened and use the order history confidently.

#### Statuses, comments, and histories may not be equivalent <a href="#statuses-comments-and-histories-may-not-be-equivalent" id="statuses-comments-and-histories-may-not-be-equivalent"></a>

Order statuses often look similar across platforms but carry different operating meanings. A source status named “processing,” “paid,” “fulfilled,” “shipped,” “canceled,” or “refunded” may not align perfectly with the target status structure. Some stores also use custom statuses for fraud review, backorders, partial fulfillment, supplier confirmation, pickup, or manual approval.

Order comments and status history can also carry important meaning. If the source order history includes customer notes, administrator notes, tracking notes, payment gateway messages, fulfillment messages, or integration logs, the migration plan should specify which details should remain visible and which are outside the scope of ordinary order-history migration.

#### Coupons, discounts, tax, shipping, and payment context need separation <a href="#coupons-discounts-tax-shipping-and-payment-context-need-separation" id="coupons-discounts-tax-shipping-and-payment-context-need-separation"></a>

An order can contain coupon, discount, tax, shipping, and payment information as historical data. That does not mean the same rule is automatically active in J2Commerce 6 after migration. Historical totals should be interpreted separately from live target configuration.

For example, an old order may show a shipping charge and payment method. The target store still needs configured shipping and payment plugins to process new orders. An old order may show tax totals. The target store still needs valid tax profiles, zones, geo-zones, and configuration for future checkout behavior. This distinction is central to J2Commerce 6 data-model validation.

### Cart, Checkout, Tax, Shipping, and Payment Meaning <a href="#cart-checkout-tax-shipping-and-payment-meaning" id="cart-checkout-tax-shipping-and-payment-meaning"></a>

J2Commerce 6 includes modern cart and checkout behavior, including AJAX, multi-step or single-page modes, payment plugins, shipping plugins, tax profiles, geo-zones, currencies, and integration surfaces. Migration planning should separate historical data from live checkout configuration.

#### Checkout behavior is partly data and partly configuration <a href="#checkout-behavior-is-partly-data-and-partly-configuration" id="checkout-behavior-is-partly-data-and-partly-configuration"></a>

Checkout-related records may include customer information, addresses, coupons, tax profiles, shipping methods, payment methods, custom fields, order comments, and status logic. But checkout behavior is not only data. It is also controlled by target configuration, frontend rendering, payment plugin availability, shipping plugin availability, validation rules, and accessibility behavior.

A strong migration plan identifies what should migrate as historical or structural data and what must be configured inside J2Commerce 6 before launch. Treating checkout as a set of fields alone is a common source of weak migration outcomes.

#### Shipping and payment methods need target equivalents <a href="#shipping-and-payment-methods-need-target-equivalents" id="shipping-and-payment-methods-need-target-equivalents"></a>

J2Commerce 6 uses a modern plugin architecture. Existing J2Store v4 payment and shipping plugins do not directly work in v6 when they depend on the old FOF 2 and `onJ2Store*` event model. For a v4-to-v6 migration, historical orders may retain payment and shipping context, but live order processing requires v6-compatible plugins or replacement configuration.

For migrations from other Source Platforms, shipping and payment behavior should be translated into target requirements. The merchant should identify which methods must exist after launch, which are only historical labels on old orders, and which require a v6 extension, marketplace plugin, integration, or Custom Service review.

#### Tax profiles, zones, geo-zones, and currencies are structural rules <a href="#tax-profiles-zones-geo-zones-and-currencies-are-structural-rules" id="tax-profiles-zones-geo-zones-and-currencies-are-structural-rules"></a>

Tax and currency information can appear simple when seen on an invoice, but the live store needs structural rules. J2Commerce 6 includes tax profiles, geo-zones, countries, zones, currencies, and currency update behavior. These should be treated as target configuration and validation concerns.

If the Source Platform uses unusual regional rules, customer tax exemptions, product tax classes, multi-currency pricing, live exchange rates, or external tax services, those requirements should be documented before migration. Some parts may be configured in J2Commerce 6; others may require Add-on review, extension review, or Custom Service.

### Storefront, Discovery, and Route Meaning <a href="#storefront-discovery-and-route-meaning" id="storefront-discovery-and-route-meaning"></a>

Data model translation does not stop at administration records. In a Joomla 6 store, product and category data also need to make sense through menus, modules, templates, frontend framework choices, Smart Search, Schema.org structured data, and SEO-sensitive routes.

#### Frontend framework choice affects presentation meaning <a href="#frontend-framework-choice-affects-presentation-meaning" id="frontend-framework-choice-affects-presentation-meaning"></a>

J2Commerce 6 supports Bootstrap 5 and UIkit 3 frontend systems. That choice affects how product lists, product detail pages, category views, cart, checkout, and account experiences are rendered. The migrated data may be structurally correct but still require implementation review if the selected Joomla template expects a different frontend approach.

For stores moving from J2Store v4, old template overrides may not carry over directly to the v6 architecture. For stores moving from non-Joomla platforms, old theme behavior will not automatically become J2Commerce 6 layout behavior. The migration should support the target data foundation, while storefront implementation should be planned separately.

#### Menus, modules, search, and structured data affect discoverability <a href="#menus-modules-search-and-structured-data-affect-discoverability" id="menus-modules-search-and-structured-data-affect-discoverability"></a>

Joomla menus and modules can shape how shoppers reach products, categories, and account pages. J2Commerce 6 also includes Smart Search indexing and Schema.org structured data support. These features make discovery more than category assignment.

A migrated product should be reachable, searchable, and understandable in the target storefront. High-value product URLs, category entry points, internal links, menus, product modules, related products, and structured data expectations should be reviewed as part of validation. If the source store depends heavily on organic search or campaign landing pages, route and discovery planning should happen before Full Migration.

#### Content-commerce relationships may need rebuilding <a href="#content-commerce-relationships-may-need-rebuilding" id="content-commerce-relationships-may-need-rebuilding"></a>

Many Joomla stores blend content and commerce. Product explanations may live in articles, landing pages, modules, or template sections. J2Commerce 6 can support commerce inside Joomla, but migrated product records do not automatically rebuild all surrounding content relationships.

The migration plan should distinguish product data from Joomla content, menu configuration, module placement, layout overrides, article references, and marketing pages. Some content may be handled as CMS Pages or Blog Posts, depending on the selected migration path and supported behavior; other content may belong to Joomla implementation work outside standard commerce data migration.

### Extension, App, API, and Custom Field Meaning <a href="#extension-app-api-and-custom-field-meaning" id="extension-app-api-and-custom-field-meaning"></a>

J2Commerce 6 is designed for extensibility. That creates opportunity, but it also creates migration planning responsibility. Extension behavior must be treated as behavior, not simply as a field list.

#### App and plugin data must be classified before migration <a href="#app-and-plugin-data-must-be-classified-before-migration" id="app-and-plugin-data-must-be-classified-before-migration"></a>

A source store may use extensions for subscriptions, marketplace vendors, downloadable access, shipping carriers, tax services, marketing automation, reviews, wishlist behavior, analytics, B2B workflows, or reporting. Some of those behaviors may have J2Commerce 6 equivalents. Others may require a marketplace extension, custom development, or a different target workflow.

The data model should classify each extension-dependent area into one of four groups: supported migrated data, target configuration, extension replacement, or Custom Service review. Without this classification, the migration can preserve the visible product or order record while losing the workflow attached to it.

#### REST API and integration surfaces change the meaning of records <a href="#rest-api-and-integration-surfaces-change-the-meaning-of-records" id="rest-api-and-integration-surfaces-change-the-meaning-of-records"></a>

J2Commerce 6 includes REST API and Joomla web services surfaces. For integration-heavy stores, products, orders, customers, inventory, coupons, tax data, shipping methods, payment methods, manufacturers, currencies, countries, and zones may need to support external workflows after migration.

This changes validation. It is not enough for data to look correct inside the target administration area. API-connected workflows may need stable identifiers, mapped fields, correct statuses, clean product references, meaningful customer links, and reliable order structures. If source records contain third-party identifiers or ERP-owned values, those details should be reviewed before assuming standard migration is enough.

#### Custom fields and custom filters require meaning review <a href="#custom-fields-and-custom-filters-require-meaning-review" id="custom-fields-and-custom-filters-require-meaning-review"></a>

Custom fields and custom filters can be valuable in J2Commerce 6, but source custom data should not be blindly copied. A source custom field may represent shopper-facing product detail, internal merchandising information, integration metadata, tax classification, fulfillment instructions, or app-specific logic.

Before migration, the merchant should decide which custom fields are needed in the target store, where they should appear, whether they should be searchable or filterable, whether they affect checkout or reporting, and whether they require Advanced Data Mapping, Advanced Data Configure, or Custom Service.

### J2Store v4 Migration Data and Idmap Meaning <a href="#j2store-v4-migration-data-and-idmap-meaning" id="j2store-v4-migration-data-and-idmap-meaning"></a>

For merchants migrating from J2Store v4, J2Commerce 6 has a specific continuity layer: the v4 migrator. This should be used as a migration-control concept, not as a reason to skip validation.

#### The v4 migrator creates a traceable transition layer <a href="#the-v4-migrator-creates-a-traceable-transition-layer" id="the-v4-migrator-creates-a-traceable-transition-layer"></a>

The v4-to-v6 migration path reads existing J2Store v4 data, writes to new J2Commerce 6 tables, supports dry-run review, and uses idmap tracking while leaving original J2Store tables untouched. This matters because migrated data can be traced back to its source origin during review.

Traceability helps with troubleshooting, rollback planning, cutover confidence, and partial-failure diagnosis. However, traceability does not automatically prove business correctness. A migrated product with an idmap record still needs validation for variant behavior, image handling, category placement, pricing, stock, and storefront display.

#### v4 plugin behavior is not v6 plugin behavior <a href="#v4-plugin-behavior-is-not-v6-plugin-behavior" id="v4-plugin-behavior-is-not-v6-plugin-behavior"></a>

J2Store v4 plugin behavior should be reviewed carefully. Older v4 payment and shipping plugins do not directly work in J2Commerce 6 when they depend on the old FOF 2 and `onJ2Store*` event model. J2Commerce 6 uses a different native Joomla MVC plugin architecture and v6 event model.

That distinction affects data-model planning. A historical payment method may be preserved on an order, but the live target store needs a compatible v6 payment plugin. A source shipping method may appear in history, but future checkout requires a compatible v6 shipping configuration. Custom v4 app data may require transformation or replacement rather than direct migration.

### Custom Platform Source Interpretation <a href="#custom-platform-source-interpretation" id="custom-platform-source-interpretation"></a>

When the Source Platform is Custom Platform, the data model cannot be assumed from platform conventions. Products, customers, orders, categories, custom fields, payment records, shipping rules, tax logic, subscription data, vendor data, or external identifiers may exist in structures that do not match standard commerce exports.

Custom Platform migration into J2Commerce 6 should be reviewed through Custom Service. That review should identify which source structures can become J2Commerce 6 products, variants, categories, customers, addresses, orders, coupons, tax profiles, shipping methods, payment context, custom fields, or integration metadata. It should also identify which requirements need custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, or broader bespoke handling.

The same principle applies when a standard Source Platform contains heavy customization. If the source behaves like a custom system because of apps, extensions, external databases, third-party identifiers, custom checkout logic, or integration-owned records, the migration should be planned as a meaning-translation project rather than a record-count project.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

J2Commerce 6 data model validation should prove that migrated records are commercially meaningful, operationally useful, and technically compatible with the target Joomla 6 implementation.

| Proof area                  | What the migrated result must prove                                                                                                                            |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products and variants       | Products are sellable, variant choices are understandable, images and stock behave correctly, and product records support the intended shopper journey.        |
| Categories and discovery    | Categories, manufacturers, custom filters, menus, modules, Smart Search, and structured data support target browsing and search behavior.                      |
| Customers and accounts      | Customers, addresses, guest checkout context, user-account links, customer groups, and order relationships remain usable.                                      |
| Orders and history          | Historical orders preserve line items, variant selections, totals, discounts, coupons, tax, shipping, payment context, statuses, comments, and customer links. |
| Checkout configuration      | Target checkout, tax profiles, shipping methods, payment plugins, currencies, and zones are configured or clearly separated from migrated history.             |
| Storefront rendering        | Product lists, product detail pages, cart, checkout, account pages, modules, and selected Bootstrap 5/UIkit 3 behavior render correctly.                       |
| Extensions and integrations | Plugin replacements, API needs, custom fields, custom filters, reporting, task scheduler, action log, and third-party workflows are understood.                |
| v4 transition traceability  | For J2Store v4 sources, dry-run review, idmap tracking, partial-failure diagnosis, and cutover confidence are clear.                                           |

A record-count match is not enough. The migrated data should prove that the target J2Commerce 6 store can be managed, browsed, purchased from, supported, integrated, and validated in the way the merchant expects.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Commerce 6 changes the data-model conversation because it is a native Joomla 6 commerce target with modern product, variant, checkout, plugin, frontend, API, and integration assumptions. A successful migration should translate source data into a target structure that preserves commercial meaning, not just visible records.

The most important translation areas are products and variants, customer and address relationships, order history, checkout configuration, tax and shipping structure, payment replacement, storefront rendering, Joomla discovery, plugin compatibility, custom fields, API expectations, and J2Store v4 migrator traceability where relevant. When those areas are reviewed together, the merchant can judge whether the target store is genuinely usable after migration.

Use Demo Migration and Live Chat to review whether your source data translates into J2Commerce 6 with the meaning your store needs. If the source store includes complex variants, old J2Store plugins, custom fields, app-owned data, third-party identifiers, API dependencies, Custom Platform source records, or custom checkout behavior, review the selected migration path early so Standard Service, Managed Service, Custom Service, and Add-on boundaries are clear before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Why does J2Commerce 6 data model planning matter more than simple record counts?**

Because J2Commerce 6 is a native Joomla 6 commerce target with modern product, checkout, plugin, frontend, and API behavior. A product, customer, or order can appear in the target store but still lose important business meaning if variants, addresses, statuses, shipping, payment, tax, images, or integration relationships are not interpreted correctly.

**Are J2Store v4 and J2Commerce 6 data structures the same?**

No. J2Commerce 6 is a separate modern generation. J2Store v4 data can be migrated through the v4-to-v6 path when applicable, but the target structure uses native Joomla 6 architecture and different plugin/event behavior. That is why v4-to-v6 migration results still need review and validation.

**Do old J2Store payment and shipping plugins migrate directly into J2Commerce 6?**

No. Older J2Store plugins were built for the v4 architecture and old event model. Historical payment and shipping context may remain useful on old orders, but live checkout needs J2Commerce 6-compatible payment and shipping plugins or replacement configuration.

**What product samples should be reviewed during Demo Migration?**

Use products that reveal real catalog meaning: simple products, variant-heavy products, products with multiple or variant-linked images, downloadable products, discounted products, inventory-sensitive products, category-heavy products, and records with custom fields, filters, or integration dependencies.

**How should Custom Platform source data be handled when migrating to J2Commerce 6?**

Custom Platform source data should be reviewed through Custom Service because the source structure may not match standard commerce assumptions. Products, variants, customers, orders, custom fields, third-party identifiers, tax logic, shipping logic, and integration-owned records may require custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, or broader bespoke handling.
