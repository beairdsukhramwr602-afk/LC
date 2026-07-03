# osCMax Data Model Differences

osCMax data should be read as layered store evidence, not as a simple catalog export. A store may contain familiar osCommerce-style records, but those records often sit beside contribution-owned behavior, template-specific display logic, older image handling, custom modules, and version-specific assumptions. A migration plan that treats every osCMax record as standard osCommerce data can preserve the visible objects while losing the commercial meaning that made the original store work.

The important distinction is not whether osCMax resembles osCommerce. It does. The important question is where the store stops behaving like a clean osCommerce base and starts depending on an enhanced package, a pre-installed contribution, a later modification, or a merchant-specific customization. That is where data-model interpretation becomes decision work.

### Why osCMax Data Needs a Layered Reading <a href="#why-oscmax-data-needs-a-layered-reading" id="why-oscmax-data-needs-a-layered-reading"></a>

Many osCMax stores were built from a familiar commerce base: categories, products, customers, orders, addresses, payments, shipping methods, taxes, specials, reviews, and configuration records. Those entities may look migration-ready because their names resemble standard ecommerce records. The risk is that osCMax stores often use these records together with extensions, templates, image modules, order-flow changes, content boxes, article modules, or admin-side shortcuts that change how the data is displayed, priced, filtered, or acted on.

A product record, for example, may not be meaningful by itself. Its catalog value can depend on attributes, image behavior, product-page boxes, category navigation, special pricing, customer-group rules, language files, and template placement. An order may carry the expected customer and line-item information, but the way payment, shipping, free-shipping thresholds, phone-order handling, or export routines were implemented can change how that order history should be preserved and validated.

This means osCMax data review should separate four layers before migration scope is accepted:

| Data layer                        | What it contains                                                                                     | Why it matters in migration                                                               |
| --------------------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Base commerce records             | Products, categories, customers, orders, addresses, reviews, taxes, currencies, languages            | Usually the most direct migration candidates, but still require version and field review. |
| Enhanced package behavior         | Bundled or pre-installed contribution logic, admin improvements, image handling, promotional modules | May not map as a simple field-to-field transfer.                                          |
| Store-specific customization      | Custom files, custom tables, modified modules, local code changes, altered language files            | Often requires Custom Service review before preservation can be promised.                 |
| Presentation and interface assets | Templates, buttons, boxes, navigation layouts, image effects, storefront content blocks              | May need target-side rebuilding or validation rather than direct migration.               |

This layered reading protects the migration from a common mistake: counting records while ignoring the mechanism that made those records usable. The target store needs usable products, intelligible order history, recognizable customers, coherent storefront navigation, and validated commercial rules. Raw record movement is only part of that result.

### Separating osCommerce Base Records from osCMax-Specific Behavior <a href="#separating-oscommerce-base-records-from-oscmax-specific-behavior" id="separating-oscommerce-base-records-from-oscmax-specific-behavior"></a>

The osCommerce-derived foundation makes some osCMax records familiar. Product names, model or SKU values, categories, customer accounts, customer addresses, orders, order statuses, reviews, manufacturers, tax zones, currencies, and language records may appear close to ordinary osCommerce structures. These records often provide the initial migration scope because they represent the core business history of the store.

However, the presence of an osCommerce-like table or field does not guarantee standard behavior. osCMax stores may include contribution-based features that reuse familiar tables, add adjacent tables, or write behavior into configuration records. Some additions behave like simple display features, while others affect price, shipping, payment, customer groups, product visibility, order handling, or admin work. The migration plan must determine whether each feature is data, configuration, presentation, or custom logic.

A practical review should ask three questions for every important record group. First, is the record part of the base commerce model? Second, is the record modified or extended by osCMax-specific behavior? Third, does the target platform support that behavior natively, through Add-ons, through configuration, or only through Custom Service review?

| Record group   | Base meaning                                                                   | osCMax-specific reading cue                                                                                                   |
| -------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Products       | Sellable catalog items with price, status, description, images, and categories | Check for contribution-created fields, custom image behavior, attribute extensions, display boxes, or admin quick-edit logic. |
| Categories     | Catalog grouping and navigation hierarchy                                      | Check whether template navigation, horizontal menus, infoBoxes, or custom category lists affect discovery.                    |
| Customers      | Account records, addresses, and contact information                            | Check for wholesale, distributor, restricted content, phone-order, or customer-group behavior.                                |
| Orders         | Commercial history and transaction evidence                                    | Check for custom payment steps, free-shipping promotions, order exports, altered order statuses, or manual order handling.    |
| Content blocks | Storefront messages, boxes, news, articles, and informational areas            | Check whether they are CMS-like records, template inserts, language files, or contribution-owned content.                     |

This distinction is especially important when migrating from osCMax to a modern Target Platform. Some base records can migrate normally. Some enhanced behavior should be replaced with target-native features. Some legacy behavior should be retired. Some records may need special handling because they were created by custom code, a contribution, or a store-specific module.

### Catalog Records, Attributes, Images, and Presentation Layers <a href="#catalog-records-attributes-images-and-presentation-layers" id="catalog-records-attributes-images-and-presentation-layers"></a>

Catalog migration in osCMax is rarely only Products and Categories. The catalog may also include attributes, product options, image modules, special displays, additional product boxes, and template-driven presentation. Product data can appear correct in the target store while the customer-facing buying path still feels wrong if option labels, image galleries, sale indicators, stock messages, or category placement are not validated.

Attributes need careful interpretation. In an osCommerce-derived system, attributes can represent choices such as size, color, finish, imprint text, downloadable file variants, or service options. Some attributes are straightforward product options. Others may have been altered by contributions to support text input, customer-specific visibility, special pricing, or admin shortcuts. A direct option transfer may preserve labels but fail to preserve the intended buying behavior.

Images also need more than file-copy review. Older osCMax stores may use image subdirectories, automatic thumbnails, popup image behavior, gallery effects, or custom image-management routines. The migration plan should identify whether images are standard product images, derived thumbnails, template references, obsolete gallery artifacts, or files no longer used by active products. Moving every image file can create clutter; moving too few can break product confidence.

Presentation is another source of data-model confusion. Templates and boxes can turn ordinary records into visible merchandising blocks. A latest-news box, free-shipping box, category menu, product scroller, special countdown, or button set may not be a core product record, but it can shape how customers find products and respond to offers. These elements should be classified before migration as one of three outcomes: migrate as content, rebuild as target-store configuration, or retire because the target store has a cleaner native equivalent.

For catalog review, a useful rule is simple: preserve the commercial meaning, not every legacy mechanism. If an old product-scroller contribution existed only to surface featured products, the target store may not need that exact contribution logic. It needs the merchant decision behind it: which products should be featured, where they should appear, and how success should be validated after launch.

### Customer, Order, Payment, and Shipping Meaning <a href="#customer-order-payment-and-shipping-meaning" id="customer-order-payment-and-shipping-meaning"></a>

Customer and order records carry business continuity. In osCMax, the difficulty is that customer and order meaning may be influenced by modules or custom business practices. A customer may be a retail buyer, wholesale contact, distributor, restricted-content user, or account created for a phone-order process. An order may reflect standard checkout, phone payment, free-shipping threshold behavior, custom shipping tables, zone rules, or later export requirements.

Order migration should therefore validate more than order count. It should confirm order dates, customer links, billing and shipping addresses, line items, product option labels, taxes, discounts, shipping charges, payment labels, order statuses, and any historical notes that support customer service. If a store used custom order export routines, the export format may not matter in the target store, but the reporting need behind it does.

Shipping data is particularly sensitive because osCMax stores may use table rates, zone-based shipping, international shipping additions, or free-shipping displays. A shipping module can combine configuration, language text, order-total logic, and customer-facing messaging. Migrating old configuration values without understanding the target platform’s shipping model can create false confidence. Validation must prove that historical orders read correctly and that future shipping behavior has been rebuilt or configured intentionally.

Payment data should be handled with similar care. Historical payment labels and transaction references may need to remain visible for order history, but old payment modules normally cannot be treated as reusable target-side implementations. The migration plan should separate payment history from payment enablement. Preserving past order information is a data task; enabling future payments is target configuration or integration work.

### Content, Templates, Buttons, and Storefront Assets <a href="#content-templates-buttons-and-storefront-assets" id="content-templates-buttons-and-storefront-assets"></a>

osCMax storefront data often includes assets that do not fit neatly into Products, Customers, or Orders. Templates, button sets, language files, content boxes, article/news features, banners, and informational pages may all contribute to the user experience. Some are records. Some are files. Some are generated assets. Some are hard-coded. Some are legacy leftovers.

The first step is to classify storefront assets by business role. Product images and active category images are catalog assets. Store policies, delivery information, and help pages are content assets. Template files, buttons, icons, menu styles, and box layouts are interface assets. Old scripts, unused images, obsolete patches, and abandoned template experiments are technical artifacts. Each group requires a different migration decision.

| Asset type                           | Migration interpretation                               | Validation question                                                                               |
| ------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Product and category images          | Catalog evidence needed for product trust and browsing | Do active products display the correct images in the target store?                                |
| Content boxes and article/news areas | Storefront messaging or merchandising content          | Should the content migrate, be rebuilt, or be replaced with target-native content management?     |
| Templates and layout files           | Interface behavior, not ordinary content               | Which parts define business-critical navigation or conversion paths?                              |
| Button and language assets           | Localization and interface consistency                 | Are buttons and labels still needed, or does the target store provide its own interface language? |
| Obsolete image or template utilities | Legacy maintenance evidence                            | Should these be excluded to avoid carrying technical debris forward?                              |

This classification prevents two opposite mistakes. The first mistake is ignoring storefront assets because they are not core entities. The second is moving every legacy file as if it were still useful. A mature migration keeps active catalog and content value while avoiding unnecessary transfer of obsolete interface machinery.

### Contribution-Owned Records and Custom Tables <a href="#contribution-owned-records-and-custom-tables" id="contribution-owned-records-and-custom-tables"></a>

The most important osCMax data-model difference is contribution ownership. A contribution may create new tables, add fields to existing tables, introduce configuration keys, alter order behavior, change product display, or rely on language files and template snippets. From a migration perspective, contribution-owned data must be reviewed before it is treated as supported scope.

Some contribution-owned behavior can be translated into standard target-store concepts. For example, a free-shipping promotional box may become a target-store promotion message or shipping banner. A restricted article feature may become customer-group content access. A special countdown may become campaign timing or promotional urgency. These are translation opportunities, not necessarily direct data migrations.

Other contribution-owned behavior may require Custom Service review. This is likely when the data lives in custom tables, depends on altered PHP files, creates non-standard product fields, changes order calculation, modifies customer permissions, or has no clear equivalent in the target platform. Add-ons can help with bounded needs such as filtering, mapping, or supported configuration, but they should not be used to imply that old contribution behavior will automatically reappear in the new store.

A good evidence package for osCMax should include a database export, file inventory, list of installed contributions or modified modules, template folder review, admin screenshots, active order samples, product samples with attributes, shipping/payment configuration screenshots, and notes on custom business rules. Without this evidence, the safest conclusion is not that the data cannot migrate. The safer conclusion is that the scope is not yet fully knowable.

A useful translation rule is to ask whether a record explains a business fact or triggers a storefront behavior. Business facts such as product identity, customer contact details, order totals, and address history are usually reviewed as migration data. Storefront behaviors such as image display conventions, promotional boxes, old module outputs, or template-specific navigation are reviewed as target-side behavior. When the two are mixed, the migration plan should document which part is data and which part needs configuration, Add-ons, or Custom Service review.

### Data Translation Rules for Migration Scope <a href="#data-translation-rules-for-migration-scope" id="data-translation-rules-for-migration-scope"></a>

osCMax migration scope should be decided through translation rules. The question is not only “Can this record move?” but “What should this record become in the Target Platform?” The answer can be different for each data group.

| osCMax evidence                                                    | Likely scope treatment                                                        | Service implication                                                                    |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Standard products, categories, customers, orders, reviews, coupons | Usually part of baseline migration scope if fields are readable and supported | Often suitable for Standard Service or Managed Service depending on merchant capacity. |
| Product attributes with custom behavior                            | Needs option/variant interpretation and sample validation                     | May require Advanced Data Mapping or Custom Service depending on structure.            |
| Custom tables from contributions                                   | Needs schema review and business-purpose analysis                             | Usually Custom Service review before commitment.                                       |
| Template-specific boxes and content inserts                        | Classify as content, navigation, promotion, or interface behavior             | May be rebuilt in target configuration rather than migrated as records.                |
| Obsolete patches, unused images, abandoned modules                 | Exclude unless there is active business value                                 | Preparation should reduce clutter before Full Migration.                               |
| Historical order exports or reporting needs                        | Preserve order history and define target reporting requirements               | May require mapping, configuration, or Custom Service depending on fields.             |

Entity Points should be read only as a scope-sizing mechanism, not as a substitute for data-model analysis. New eligible Products, Customers, Orders, and Blog Posts consume Entity Points when first migrated. Records already counted through the service license do not consume Entity Points again simply because another action happens on the same migration path. For osCMax, the harder work is identifying which records are standard eligible entities and which records are contribution-owned data that need separate review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

osCMax data is best understood as layered commerce evidence. The base record model may resemble osCommerce, but the migration scope can change quickly when products, orders, images, templates, content boxes, shipping rules, and customer behavior are shaped by bundled contributions or custom modifications. A reliable migration plan separates standard records from contribution-owned behavior, classifies storefront assets by business role, and validates what each record should become in the Target Platform.

The safest osCMax migration does not try to preserve every old mechanism. It preserves commercial meaning: usable catalog structure, recognizable customer and order history, accurate product options, trustworthy images, understandable shipping and payment history, and storefront content that still supports the buyer journey. Everything else should be reviewed, translated, rebuilt, or retired deliberately.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can osCMax data not be treated exactly like osCommerce data?**

osCMax often starts from an osCommerce-like base, but many stores include enhanced package behavior, bundled contributions, custom files, templates, or old modifications. These layers can change how products, images, shipping, orders, and content behave, even when the database tables look familiar.

**Which osCMax records are usually easiest to migrate?**

Standard products, categories, customers, orders, reviews, coupons, manufacturers, addresses, and basic content are usually the most straightforward when fields are readable and supported. They still need validation because old stores may contain altered fields or contribution-driven behavior.

**When does osCMax data need Custom Service review?**

Custom Service review is usually needed when important data lives in custom tables, depends on modified PHP files, changes product or order behavior, uses contribution-owned records, or has no clear equivalent in the Target Platform.

**Should old templates, buttons, and boxes be migrated as data?**

Not automatically. Some assets represent business-critical navigation or content. Others are interface files or obsolete technical artifacts. They should be classified by business purpose before deciding whether to migrate, rebuild, or retire them.

**How should Demo Migration be used for osCMax data?**

Demo Migration should include products with attributes, image-heavy products, special pricing, customer records, representative orders, shipping/payment examples, and any contribution-dependent behavior. The goal is to prove commercial meaning, not only record counts.
