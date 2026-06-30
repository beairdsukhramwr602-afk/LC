# EShop Pre-Migration Preparation Checklist

Preparing for migration to EShop by Ossolution Team means preparing both the commerce records and the Joomla environment that will receive them. EShop is not only a destination for product and order tables. It is a Joomla shopping cart extension where products, options, attributes, manufacturers, custom fields, checkout fields, coupons, vouchers, tax classes, shipping methods, payment plugins, modules, templates, multilingual content, and custom implementation can all affect whether the migrated store is usable.

Strong preparation turns Demo Migration into a real decision tool. Weak preparation only checks record counts and waits for issues to appear. Strong preparation selects examples that prove the store’s actual operating model: option-heavy products, attribute-rich products, customer groups, custom checkout fields, multilingual products, products with attachments or downloads, coupon and voucher orders, tax-sensitive orders, shipping-sensitive orders, and records shaped by Joomla modules, template overrides, plugins, or custom fields.

The goal is not to solve every implementation task before data movement begins. The goal is to know what must be preserved as data, what must be configured in EShop, what belongs to Joomla implementation, and what should be reviewed through Add-ons or Custom Service before execution.

### What Preparation Means for EShop <a href="#what-preparation-means-for-eshop" id="what-preparation-means-for-eshop"></a>

EShop preparation should organize the project around the layers that shape the future store. Product and order data are only one layer. Joomla site structure, target configuration, extension behavior, and storefront presentation also influence the result. A clean preparation process separates those layers before Demo Migration so the review does not confuse missing configuration with missing data, or Joomla layout work with migration output.

| Preparation layer                | What to review                                                                                                                           | Why it matters for EShop                                                                                  |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Joomla environment               | Joomla version, EShop installation, menus, modules, templates, extensions, and administrative access.                                    | Migrated data must operate inside a working Joomla and EShop setup.                                       |
| Catalog structure                | Products, categories, manufacturers, options, attributes, custom fields, attachments, images, tabs, labels, and reviews.                 | Catalog meaning decides whether shoppers can understand and buy products after migration.                 |
| Customer and order history       | Customers, customer groups, addresses, order lines, order statuses, coupons, vouchers, tax, shipping, payment context, and comments.     | Historical records must remain useful for service, reporting, account review, and operational continuity. |
| Configuration-sensitive behavior | Tax classes, geo zones, currencies, length and weight units, shipping methods, payment plugins, checkout fields, emails, and store mode. | Some behavior must be configured and tested in the target store rather than assumed from historical data. |
| Joomla presentation              | Menus, aliases, metadata, SEF URLs, modules, templates, multilingual routes, and redirects.                                              | Data can be present while storefront discovery or page presentation remains incomplete.                   |
| Custom or extension-owned data   | Custom tables, plugins, third-party identifiers, ERP fields, bespoke checkout logic, and unsupported source values.                      | These areas may need Add-ons or Custom Service depending on ownership and transformation needs.           |

Preparation is strongest when each layer has evidence. A statement such as “we have product options” is not enough. The migration plan should identify which products prove option behavior, whether options affect price, SKU, image, stock, or order-line output, and whether those values must remain selectable in EShop.

### Confirm Joomla and EShop Readiness <a href="#confirm-joomla-and-eshop-readiness" id="confirm-joomla-and-eshop-readiness"></a>

Before selecting Demo Migration samples, confirm that the target environment is ready enough to make the review meaningful. EShop is built for Joomla, so target readiness includes more than installing an extension. The team should know which Joomla version will be used, which EShop version is planned, which template or theme will support the storefront, which menus will expose the store, and which modules or plugins are part of launch-critical behavior.

If the target website is still under design, the migration can still be scoped, but the unresolved areas should be named clearly. Demo Migration should not be blamed for missing menus, incomplete modules, unfinished template work, or payment plugins that have not been configured. Those are launch-readiness items that need ownership alongside migration validation.

| Readiness item                   | Evidence to prepare                                                                                                        | Decision supported                                                                           |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Joomla version and hosting state | Target version, server notes, access level, extension compatibility expectations.                                          | Whether the environment can receive and review migrated records.                             |
| EShop installation               | Installed version, enabled features, store mode, administrative access, and basic configuration status.                    | Whether product, customer, and order samples can be inspected in context.                    |
| Storefront structure             | Menus for categories, products, cart, checkout, customer account, search, manufacturer pages, or quote-related paths.      | Whether shoppers will be able to reach migrated content after launch.                        |
| Modules and templates            | Mini cart module, product modules, category modules, theme notes, overrides, and launch-critical page layouts.             | Whether visual review depends on Joomla implementation work.                                 |
| Plugins and integrations         | Payment plugins, shipping plugins, content plugins, search plugins, email tools, affiliate links, CRM or ERP dependencies. | Whether behavior belongs to migrated data, target configuration, or custom integration work. |

The target environment does not need to be perfect before Demo Migration, but it must be understandable. When a missing target setting affects review, mark it as configuration pending rather than assuming the migration failed.

### Prepare Catalog Structure and Product Samples <a href="#prepare-catalog-structure-and-product-samples" id="prepare-catalog-structure-and-product-samples"></a>

Product preparation should go deeper than product counts. EShop catalog records can include products, multi-level categories, manufacturers, images, options, attributes, custom fields, attachments, downloads, extra tabs, product labels, reviews, related products, discounts, specials, stock values, dimensions, weight, and SEO fields. A sample that contains only simple products will not test whether the store’s real catalog can survive the move.

Select catalog samples that represent how the business sells. For a simple catalog, that may mean ordinary physical products with categories, images, stock, and tax class. For a structured catalog, it may require products with size and color choices, manufacturer relationships, specification tables, product PDFs, download files, reviews, related products, labels, customer-group prices, or special prices.

| Product sample                           | What it proves                                                                                               | Why it should be included                                                |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Simple product                           | Baseline product fields, price, SKU, category, image, published state, stock, and description.               | Establishes the ordinary migration result.                               |
| Option-heavy product                     | Size, color, package, required choice, price-changing option, SKU-changing option, or image-changing option. | Tests whether shopper choice remains buyable and readable on orders.     |
| Attribute-heavy product                  | Specifications, comparison values, grouped attributes, or technical details.                                 | Confirms informational values are not confused with selectable options.  |
| Product with manufacturer                | Brand, maker, supplier, or public manufacturer relationship.                                                 | Tests catalog discovery and manufacturer page expectations.              |
| Product with custom fields or tabs       | Extra product details, structured notes, or source-specific values.                                          | Reveals fields that may need Add-ons or Custom Service review.           |
| Product with attachments or downloads    | Manuals, certificates, digital assets, or downloadable products.                                             | Tests file relationships, access expectations, and product completeness. |
| Product with discount or special price   | Promotional pricing, customer group pricing, or date-sensitive price meaning.                                | Separates historical pricing data from live promotion configuration.     |
| Product with reviews or related products | Buyer confidence and merchandising context.                                                                  | Confirms supporting records are not ignored during validation.           |

This preparation helps the merchant avoid approving a migration based on clean samples that do not represent the real catalog. The most useful Demo Migration samples are not always the easiest records. They are the records most likely to reveal whether the target data model can carry the old store’s meaning.

### Separate Options, Attributes, Custom Fields, and Attachments <a href="#separate-options-attributes-custom-fields-and-attachments" id="separate-options-attributes-custom-fields-and-attachments"></a>

One of the most important EShop preparation tasks is separating values that look similar in the source store but serve different purposes. Options are shopper-facing choices. Attributes are usually product information or specifications. Custom fields may carry structured product detail, operational notes, or values created by old apps. Attachments can support product documents, manuals, certificates, downloadable assets, or other files.

Many source stores blur these boundaries. A platform may call variant choices attributes. Another may store every custom product value as a metafield. Another may use an app to create personalized options or add-on services. EShop preparation should translate business meaning before field mapping.

| Source value pattern                                                                           | Possible EShop meaning                                                | Preparation question                                                                                            |
| ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Size, color, bundle, packaging, engraving, personalization, or add-on service                  | Product option, checkout field, or custom handling.                   | Does the shopper choose it before purchase, and does it affect price, SKU, image, stock, or order-line meaning? |
| Material, compatibility, dimensions, care details, technical specifications, or warranty notes | Attribute, product custom field, extra tab, or description structure. | Should the value support comparison, detail display, filtering, or internal reference?                          |
| PDF manual, certificate, specification sheet, or digital file                                  | Product attachment or downloadable product handling.                  | Must the file be publicly visible, available after purchase, or attached only for reference?                    |
| App-created product field                                                                      | Add-on review or Custom Service review.                               | Is the value a standard product detail, a hidden operational value, or behavior created by custom code?         |
| Old variant matrix                                                                             | Product options, separate products, or custom interpretation.         | Does the source variant structure have a clean equivalent in EShop?                                             |

This separation should happen before Demo Migration sample selection. A sample product with complex choices can prove whether option values remain understandable in the storefront and on historical orders. A sample product with specifications can prove whether attribute or custom-field values remain useful without creating false checkout behavior.

### Prepare Customer, Order, and Checkout Evidence <a href="#prepare-customer-order-and-checkout-evidence" id="prepare-customer-order-and-checkout-evidence"></a>

Customer and order preparation should focus on operating meaning. EShop can work with customer accounts, customer groups, addresses, order history, order statuses, payment and shipping context, coupons, vouchers, custom checkout fields, and Joomla user relationships. The source store should be reviewed for the records that prove how customers and orders need to remain useful after migration.

Do not select only the newest or cleanest orders. Select orders that show the store’s real commercial patterns: option selections, discounts, vouchers, taxes, shipping methods, payment methods, customer comments, guest checkout, registered accounts, multiple addresses, customer groups, multilingual orders, downloadable products, and custom checkout values.

| Evidence area          | Sample to prepare                                                                                                   | What the sample should prove                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Customer identity      | Registered customer, guest customer, customer with multiple addresses, customer tied to Joomla user identity.       | Whether account context and historical recognition remain understandable.                                |
| Customer groups        | Retail, wholesale, reseller, member, tax-exempt, or special-price group.                                            | Whether group meaning needs mapping, configuration, or manual target setup.                              |
| Order lines            | Orders with product options, attributes visible in history, downloadable items, or custom product choices.          | Whether purchased-item meaning remains readable for customer service.                                    |
| Discounts and vouchers | Coupon order, voucher order, special-price order, customer-group price order.                                       | Whether historical promotion context remains available and whether live rules need target configuration. |
| Tax and shipping       | Orders with geo-zone tax, multiple shipping methods, weight/dimension sensitivity, or pickup/delivery behavior.     | Whether totals and historical method labels remain clear.                                                |
| Payment context        | Payment method, transaction reference, plugin label, paid/unpaid status, refund context.                            | Whether historical records remain useful without assuming live gateway behavior transfers automatically. |
| Checkout fields        | Billing field, shipping field, delivery note, VAT field, company field, event/date field, or custom checkout input. | Whether the field belongs to ordinary order data, target configuration, or Custom Service review.        |

Order history does not need to recreate every live checkout rule. A historical payment method can remain a label while a live payment plugin must be configured separately. A historical shipping method can remain evidence while live shipping rates require target setup. Preparation should keep that boundary clear.

### Review Tax, Shipping, Payment, Currency, and Store Configuration <a href="#review-tax-shipping-payment-currency-and-store-configuration" id="review-tax-shipping-payment-currency-and-store-configuration"></a>

EShop supports many configuration-sensitive areas, including tax classes, tax rates, geo zones, currencies, shipping methods, payment gateways, store modes, order statuses, length classes, weight classes, email notifications, checkout fields, and invoice behavior. Some of these areas may exist as migrated historical context. Others must be configured in the target store before launch.

The preparation task is to classify each requirement. Historical records need enough context to remain understandable. Live behavior needs configuration, plugin readiness, and testing. Custom behavior needs review before it is included in migration scope.

| Configuration area    | Historical data question                                                                                    | Target setup question                                                                      |
| --------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Tax classes and rates | Do old orders show tax totals and labels needed for support or reporting?                                   | Are target tax rules, geo zones, and VAT expectations configured for future checkout?      |
| Shipping methods      | Do old orders preserve method names, costs, and delivery context?                                           | Are shipping plugins, weight/length units, pickup rules, and rate logic ready for testing? |
| Payment methods       | Do historical orders show method names, statuses, transaction references, and refund notes where available? | Are live payment plugins installed, configured, and validated separately?                  |
| Currencies            | Do historical records preserve useful currency context?                                                     | Is the future currency setup clear, including exchange-rate expectations if relevant?      |
| Order statuses        | Can old statuses be mapped into understandable target statuses?                                             | Are future workflow statuses, emails, and staff processes defined?                         |
| Checkout fields       | Which historical fields should remain attached to orders?                                                   | Which future fields need configuration, validation, and display testing?                   |

This review prevents a common misunderstanding: migrated history and live store behavior are related, but they are not the same task. EShop preparation should preserve what the business needs from the old store while confirming that new checkout behavior is configured and tested in the target environment.

### Prepare Joomla Presentation, SEO, and Multilingual Evidence <a href="#prepare-joomla-presentation-seo-and-multilingual-evidence" id="prepare-joomla-presentation-seo-and-multilingual-evidence"></a>

EShop storefront continuity depends on Joomla presentation as well as migrated records. Menus, aliases, metadata, SEF URLs, modules, templates, theme files, layout overrides, multilingual routes, category pages, manufacturer pages, search behavior, and content plugins can influence how shoppers discover and use the store.

Prepare evidence from the source store and target Joomla plan before Demo Migration. The evidence does not need to be exhaustive, but it should cover pages that matter to traffic, conversion, customer support, and brand trust.

| Presentation area          | Evidence to gather                                                                                                      | Why it matters                                                                            |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Category and product paths | High-traffic URLs, SEO-sensitive products, category trees, manufacturer pages, and landing pages.                       | Redirect and route planning depends on knowing which paths must remain discoverable.      |
| Metadata and page headings | Product titles, category metadata, manufacturer metadata, page titles, and descriptions.                                | Search visibility can be damaged if metadata is ignored.                                  |
| Joomla modules             | Mini cart, product modules, category modules, related products, search modules, content modules, or promotional blocks. | Migrated data may need module assignment to appear in the storefront.                     |
| Templates and themes       | EShop theme notes, Joomla template notes, layout overrides, CSS expectations, and screenshots.                          | Visual continuity may require implementation work beyond data migration.                  |
| Multilingual content       | Product/category translations, associations, aliases, menus, checkout language, and module language assignments.        | Language structure must be validated across Joomla and EShop, not only in product fields. |
| Content plugins            | Products displayed inside articles, search plugins, video displays, affiliate integrations, or email tools.             | Some storefront behavior may depend on plugins rather than ordinary product pages.        |

If SEO and presentation evidence is missing, Demo Migration can still proceed, but the review should not treat migrated records as launch-ready pages. A product existing in EShop administration is not the same as a product being reachable, correctly routed, properly translated, and presented in the intended Joomla layout.

### Identify Add-ons and Custom Service Review Areas <a href="#identify-add-ons-and-custom-service-review-areas" id="identify-add-ons-and-custom-service-review-areas"></a>

EShop migrations often include requirements that are not simply standard record movement. Some needs may fit Add-ons, while others require Custom Service. The preparation checklist should identify these areas early so the migration path is not selected too lightly.

Add-ons can be useful when the requirement fits a defined optional capability, such as filtering unwanted records, supporting available mapping needs, or adjusting available configuration. Custom Service should be reviewed when the project involves Custom Platform data, unsupported extension data, bespoke source structures, custom fields needing interpretation, third-party identifiers, custom checkout logic, integration-owned records, or custom migration logic adjustment.

| Requirement pattern                                                               | Likely review path              | Reason                                                                                          |
| --------------------------------------------------------------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Excluding archived records, test orders, obsolete products, or inactive customers | Data Filter Add-on review.      | Filtering can be appropriate when criteria are clear and supported.                             |
| Mapping clear source values into supported EShop fields                           | Advanced Data Mapping review.   | Mapping can help when the source meaning is understood and the target destination is available. |
| Adjusting available migration configuration                                       | Advanced Data Configure review. | Configuration support can help when the change fits standard capability.                        |
| Custom fields with unclear meaning                                                | Custom Service review.          | Bespoke interpretation may be required before values can be migrated safely.                    |
| Third-party plugin or integration data                                            | Custom Service review.          | Ownership and target behavior may sit outside standard EShop records.                           |
| Tailored Add-ons or Custom Add-ons                                                | Custom Service review.          | Bespoke service handling belongs under Custom Service.                                          |

The preparation output should not describe everything as an Add-on. Add-ons and Custom Service have different roles. Keeping that boundary clear protects the merchant from approving a scope that cannot preserve the old store’s actual operating meaning.

### Plan Demo Migration Validation Samples <a href="#plan-demo-migration-validation-samples" id="plan-demo-migration-validation-samples"></a>

Demo Migration should be planned, not treated as a random preview. For EShop, the sample should prove whether catalog structure, customer context, order meaning, configuration-sensitive data, Joomla presentation, multilingual content, and custom records can be reviewed reliably.

A strong Demo Migration sample includes records that reveal risk. It should include clean baseline records and difficult records. It should include ordinary products, option-heavy products, attribute-heavy products, products with attachments, products with manufacturer associations, products with reviews or related products, orders with coupons and vouchers, orders with tax and shipping context, customers in different groups, multilingual records, and fields that may need Add-ons or Custom Service.

| Demo Migration sample group | Required examples                                                                                                                            | Validation purpose                                               |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Products                    | Simple product, option-heavy product, attribute-heavy product, manufacturer-linked product, discounted product, attachment/download product. | Confirms product meaning and catalog completeness.               |
| Customers                   | Registered customer, guest customer, customer with multiple addresses, customer group example.                                               | Confirms account and buyer-history continuity.                   |
| Orders                      | Option order, coupon/voucher order, tax-sensitive order, shipping-sensitive order, payment-method example, custom-field order.               | Confirms historical order readability and support usefulness.    |
| Joomla presentation         | High-value category, product URL, module-dependent page, multilingual page, SEO-sensitive page.                                              | Separates migrated data review from site-implementation review.  |
| Custom or unsupported areas | Custom field, plugin-owned value, external ID, integration reference, special checkout behavior.                                             | Determines whether Add-ons or Custom Service should be reviewed. |

The review should produce a clear decision: ready for standard execution, ready with Add-ons, safer under Managed Service, or requiring Custom Service review. A Demo Migration that is only checked for record counts does not provide enough evidence for an EShop project.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EShop preparation works best when it treats the target store as a Joomla commerce environment, not only a product-and-order destination. The merchant should prepare the Joomla environment, EShop installation, catalog samples, product options, attributes, custom fields, attachments, customers, customer groups, orders, coupons, vouchers, tax, shipping, payment context, multilingual records, presentation dependencies, and custom data before approving the migration scope.

The strongest preparation output is a set of representative samples and responsibility notes. It should show what must be migrated, what must be configured in EShop, what belongs to Joomla implementation, what may fit Add-ons, and what needs Custom Service review. That evidence makes Demo Migration useful because it tests the store’s real operating meaning instead of only proving that records can appear in the target system.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should I prepare before migrating to EShop?**

Prepare the target Joomla and EShop environment, product examples, categories, manufacturers, options, attributes, custom fields, attachments, customers, customer groups, orders, checkout fields, tax, shipping, payment context, multilingual records, SEO-sensitive paths, modules, templates, and custom data notes.

**Why do product options need special preparation?**

Product options can affect shopper choice, price, SKU, image, stock, and order-line meaning. A product may look migrated while the actual buying choice is incomplete, so option-heavy products should be included in Demo Migration samples.

**Should tax, shipping, and payment settings be treated as migrated data?**

Historical tax, shipping, and payment context can remain useful on old orders, but future checkout behavior usually needs target-side configuration and testing in EShop. Preparation should separate historical evidence from live configuration.

**When should custom fields be reviewed before migration?**

Custom fields should be reviewed when they affect product display, customer identity, checkout behavior, order meaning, integrations, reporting, or external systems. Clear supported fields may fit mapping review, while unclear or bespoke fields may require Custom Service.

**What should Demo Migration prove for EShop?**

Demo Migration should prove that representative products, options, attributes, customers, orders, discounts, vouchers, tax, shipping, payment context, multilingual records, Joomla presentation dependencies, and custom data can be reviewed in a way that supports the final scope decision.
