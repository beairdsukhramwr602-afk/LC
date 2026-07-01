# Phoca Cart Pre-Migration Preparation Checklist

Phoca Cart preparation should begin with evidence, not assumptions. A Phoca Cart store can combine Joomla site structure, Phoca Cart product records, attributes, options, specifications, manufacturers, categories, customer groups, tax rates, currencies, languages, order statuses, reward points, coupons, payment plugins, shipping plugins, invoices, template overrides, modules, and extension-owned behavior. Preparing only a product export is not enough when the target result must support real storefront use, order review, customer service, and launch validation.

A strong preparation process separates three things before migration begins: the records that should move, the Phoca Cart configuration that must exist in the target Joomla store, and the custom or extension-owned behavior that may need separate review. That separation prevents ordinary data movement from being judged against requirements that actually belong to configuration, Add-ons, Custom Service, or post-migration implementation work.

| Preparation question                                    | Phoca Cart planning answer                                                                                                                                                           |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What must be ready in the target store?                 | Joomla, Phoca Cart, templates, modules, menus, currencies, languages, tax, shipping, payment, and checkout settings should be reviewed before migration.                             |
| Which records need the most careful preparation?        | Products, categories, manufacturers, attributes, options, specifications, customers, customer groups, orders, coupons, reward points, discounts, tax, shipping, and payment context. |
| What should not be assumed to migrate as ordinary data? | Template overrides, module placement, plugin configuration, POS workflows, invoice layouts, custom code, import/export routines, and third-party integrations.                       |
| What should Demo Migration prove?                       | That representative records preserve commercial meaning inside Phoca Cart, not merely that records appear in the administrator area.                                                 |

### Confirm the Target Store Structure <a href="#confirm-the-target-store-structure" id="confirm-the-target-store-structure"></a>

The target store structure should be confirmed before catalog cleanup, sample selection, or service-path decisions. Phoca Cart works inside Joomla, so the target environment includes more than the Phoca Cart component alone. The Joomla version, Phoca Cart version, active template, menu structure, module positions, plugins, language setup, currency settings, and access-level expectations can all affect how migrated data is interpreted after import.

Start by documenting the exact Joomla and Phoca Cart target versions. Phoca Cart can run across different Joomla generations, and the official project highlights compatibility with modern Joomla releases, payment and shipping plugins, modules, multilingual and multicurrency support, template overrides, import/export features, and Joomla CMS integration. Those features are useful only when the target environment is prepared with the same operating assumptions the store will use after launch.

| Target-store area       | What to confirm                                                                                             | Why it matters for Phoca Cart                                                                           |
| ----------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Joomla environment      | Joomla version, PHP and database environment, user/access setup, language structure                         | Phoca Cart behavior depends on the Joomla site that hosts it.                                           |
| Phoca Cart installation | Target Phoca Cart version, enabled features, core settings, modules, plugins                                | Product, checkout, invoice, tax, shipping, payment, and display behavior require target-side readiness. |
| Storefront structure    | Menus, aliases, modules, template overrides, product/category routes                                        | Correct data can still be hard to validate when storefront paths are unfinished.                        |
| Commerce configuration  | Currencies, countries, regions, tax rates, shipping methods, payment methods, order statuses                | These settings give commercial meaning to migrated records and future checkout behavior.                |
| Extension stack         | Phoca modules, payment plugins, shipping plugins, search/filter modules, template framework, custom plugins | Extension-owned behavior may not be ordinary Phoca Cart record movement.                                |

The target store should also be evaluated for catalog mode, standard cart behavior, downloadable products, B2B or wholesale pricing, customer group use, reward points, PDF invoices, POS-related workflows, wish lists, comparison lists, search/filter modules, and multilingual or multicurrency requirements. These areas do not all become migration scope automatically, but they influence preparation and validation.

If the source or target uses an older Phoca Cart installation, collect evidence from that exact installation instead of assuming current-release behavior. Version differences, template choices, extension availability, and Joomla compatibility can change how data appears, how modules display, and how administrators review the migrated result.

### Prepare Catalog and Product Data <a href="#prepare-catalog-and-product-data" id="prepare-catalog-and-product-data"></a>

Catalog preparation should focus on product meaning. Phoca Cart can represent products through categories, manufacturers, prices, images, stock behavior, attributes, options, specifications, parameters, related products, reviews, downloadable files, discounts, reward points, and other product-adjacent structures. A clean SKU count does not show whether the catalog is migration-ready.

Prepare a product inventory that identifies simple products, complex products, products with variations or selectable choices, products with specifications, products with multiple images, products with stock rules, downloadable products, discounted products, products assigned to multiple categories, products tied to manufacturers, and products that depend on special storefront routes. Include products with missing or unusual data as well; migration planning should expose weak records before validation.

| Catalog element               | Preparation action                                                                          | Sample to include in Demo Migration                                                        |
| ----------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Products                      | Confirm names, aliases, SKUs, descriptions, prices, statuses, stock, images, and categories | High-volume products, high-value products, disabled products, discounted products          |
| Categories                    | Confirm hierarchy, category aliases, visibility, product placement, menu relationships      | Deep categories, empty categories, categories used in menus or filters                     |
| Manufacturers                 | Confirm manufacturer records, product relationships, and display expectations               | Products where brand/manufacturer affects discovery or filtering                           |
| Attributes and options        | Separate descriptive characteristics from shopper-selectable choices                        | Products with sizes, colors, packages, add-ons, option prices, or option stock             |
| Specifications and parameters | Identify structured product information and display/behavior settings                       | Technical products, comparison products, products with detailed facts                      |
| Media                         | Confirm main images, gallery images, thumbnails, file paths, and generated image behavior   | Products with multiple images, missing images, downloadable files, or external media paths |

Phoca Cart’s product layers should not be collapsed into one generic attribute list. Attributes, options, specifications, and parameters can carry different storefront meaning. Some source platforms use variants for shopper choice, custom fields for specifications, tags for filters, or app-created fields for inventory behavior. Preparation should identify the business meaning first, then decide whether the target Phoca Cart structure, mapping, configuration, Add-on, or Custom Service review is appropriate.

Downloads deserve separate attention. If the store sells digital products, prepare file paths, access rules, order-completion conditions, download limits, customer expectations, and examples of mixed physical/digital orders. If downloadable files are handled by a Joomla extension outside Phoca Cart, that dependency should be documented separately.

### Prepare Customer, Account, and Order Data <a href="#prepare-customer-account-and-order-data" id="prepare-customer-account-and-order-data"></a>

Customer and order preparation should preserve commercial usefulness. In Phoca Cart, buyer meaning may involve Joomla users, customer records, customer groups, access levels, custom group prices, discounts, coupons, reward points, order statuses, invoices, delivery notes, receipts, payment methods, shipping methods, tax rates, currencies, and historical line-item detail. Names and emails alone are not enough.

Prepare customer examples from each meaningful buyer segment. Include ordinary retail customers, wholesale customers, member groups, restricted-access buyers, customers with reward activity, customers with coupon use, inactive customers, guest-style order records when available, and customers tied to unusual order histories. If the source store uses customer groups differently from Phoca Cart, document the intended target behavior rather than treating the source labels as automatically equivalent.

| Buyer/order area        | What to prepare                                                                                  | Why it matters                                                                            |
| ----------------------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Customers               | Names, emails, addresses, account status, registration context, Joomla user relationship         | Customer records may need to align with Joomla identity and access behavior.              |
| Customer groups         | Group names, group prices, access rules, discounts, rewards, tax or shipping effects             | Group meaning can affect catalog visibility and commercial interpretation.                |
| Orders                  | Order numbers, dates, statuses, line items, options, discounts, tax, shipping, payment, currency | Historical orders should remain usable for service, accounting reference, and validation. |
| Benefits and promotions | Coupons, cart discounts, reward points, customer-specific benefits                               | Benefits may be historical evidence, future configuration, or custom behavior.            |
| Documents               | Invoices, delivery notes, receipts, email templates, POS-related documents                       | Document output often depends on target settings, templates, or extensions.               |

Order samples should include clean completed orders and operationally difficult cases. Use orders with multiple products, options, attributes, coupons, reward points, tax, shipping, different payment methods, multiple currencies, downloadable products, refunds or cancellations if available, unusual statuses, and customer group behavior. These samples should become the evidence set for Demo Migration review.

Historical orders should not be treated as future checkout configuration. A migrated order can preserve what happened in the source store, while future tax, shipping, payment, invoice, and checkout behavior still require target-side setup. Preparation should keep those two expectations separate.

### Prepare Content, URLs, and SEO Inputs <a href="#prepare-content-urls-and-seo-inputs" id="prepare-content-urls-and-seo-inputs"></a>

Phoca Cart preparation should include the Joomla storefront layer because customers do not experience migrated data inside the administrator area. They experience category pages, product pages, menu paths, search results, modules, filters, language routes, image output, page titles, metadata, redirects, and template-driven layouts. Storefront continuity requires preparation before migration, not only after import.

Collect current URLs for important product pages, category pages, manufacturer pages, landing pages, filtered pages, search pages, and campaign destinations. Document aliases, canonical-looking paths, page titles, meta descriptions, redirects, broken but valuable URLs, and pages receiving external traffic. If the source store has strong SEO value, the URL evidence should be prepared before Full Migration.

| Storefront input   | Preparation action                                                                                              | Validation use                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Product URLs       | Export or crawl important product paths and aliases                                                             | Confirm that priority products remain reachable or redirected. |
| Category paths     | Document category hierarchy, menus, aliases, and landing pages                                                  | Confirm discovery paths and SEO-sensitive category pages.      |
| Menus and modules  | Identify Joomla menus, Phoca Cart modules, search/filter modules, carts, currency selectors, product slideshows | Confirm page assembly and shopper navigation.                  |
| Metadata           | Gather titles, descriptions, aliases, structured data expectations, and priority pages                          | Confirm SEO continuity and page-level signals.                 |
| Multilingual paths | Confirm language associations, translated products, category names, menu items, and currency/language behavior  | Confirm localized discovery and checkout expectations.         |

Template and module behavior should be prepared as display evidence, not assumed migration scope. Phoca Cart supports template overrides and modules, but the migration should not be expected to rebuild every Joomla layout decision automatically. If presentation continuity is business-critical, capture screenshots, template notes, module lists, layout examples, and priority page comparisons.

### Review Apps, Extensions, Integrations, or Custom Data <a href="#review-apps-extensions-integrations-or-custom-data" id="review-apps-extensions-integrations-or-custom-data"></a>

Phoca Cart stores may depend on more than Phoca Cart’s core records. Payment plugins, shipping plugins, search/filter modules, product display modules, invoice tools, POS-related extensions, import/export routines, external feeds, analytics scripts, ERP connections, custom Joomla plugins, custom tables, and template overrides may own data or behavior that is not standard migration scope.

Review each dependency by asking whether it owns records, calculates behavior, changes display, affects checkout, writes identifiers, or only provides presentation. The answer determines whether it belongs in target setup, Add-on review, Custom Service review, or post-migration implementation.

| Dependency type         | Preparation evidence                                                       | Likely planning implication                                                 |
| ----------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Payment plugins         | Plugin names, transaction references, payment labels, order examples       | Historical payment context may migrate differently from live gateway setup. |
| Shipping plugins        | Method names, zones, rates, carrier rules, order examples                  | Future shipping behavior usually requires target configuration.             |
| Search/filter modules   | Filter fields, attribute/specification use, category behavior, screenshots | Catalog mapping should support expected discovery behavior.                 |
| Invoice/PDF tools       | Invoice samples, receipt examples, document templates, numbering rules     | Historical documents and future document output may need separate handling. |
| POS or external systems | External IDs, order/customer/product references, sync rules                | Custom Service may be needed if identifiers or workflows must be preserved. |
| Custom Joomla data      | Custom fields, custom tables, plugin-owned fields, bespoke code            | Non-standard data should be reviewed before migration scope is approved.    |

Do not classify all extension behavior as Add-ons. Add-ons help when the requirement matches an available optional service feature. Custom Service should be reviewed when the project requires unsupported data interpretation, custom migration logic adjustment, modified Add-ons, project-specific Add-ons, or migration involving Custom Platform behavior.

### Prepare Access, Backups, and Migration Inputs <a href="#prepare-access-backups-and-migration-inputs" id="prepare-access-backups-and-migration-inputs"></a>

Access preparation is part of risk control. The migration cannot be reviewed properly if source data, target access, exports, database access, admin permissions, media files, or plugin lists are incomplete. The preparation package should be strong enough to support Demo Migration, review, and later Full Migration without repeated discovery work.

Prepare administrator access, database or export access if required, media/file access, product image access, downloadable file access, customer/order data exports, source platform credentials, target Joomla administrator access, target Phoca Cart access, plugin/module lists, and recent backups. Backups should include files and database data where possible, especially when the source store is active or when older Joomla/Phoca Cart environments are involved.

| Input type     | What to prepare                                                                                | Risk reduced                                                   |
| -------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Source access  | Admin credentials, exports, database access where relevant, media files, custom-field evidence | Prevents incomplete data review.                               |
| Target access  | Joomla admin, Phoca Cart admin, target configuration notes, plugin/module lists                | Prevents late setup discovery.                                 |
| Backups        | Database backup, file backup, image/download backup, configuration snapshots                   | Protects the source and target during migration activity.      |
| Evidence files | Screenshots, URL lists, sample order screenshots, export files, extension lists                | Supports issue diagnosis after Demo Migration.                 |
| Business rules | Pricing rules, customer group rules, tax/shipping/payment expectations, invoice requirements   | Prevents records from being reviewed without business context. |

Access should be tested before Demo Migration begins. A migration project loses time when missing image folders, blocked exports, incomplete permissions, or unavailable target settings are discovered during validation.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

Demo Migration samples should reveal the store’s real complexity. A sample set made only of clean products and ordinary orders can make the migration look simpler than it is. For Phoca Cart, the sample set should include records that test catalog structure, buyer segmentation, order history, configuration-sensitive behavior, multilingual content, Joomla storefront paths, and extension-owned data.

Choose samples intentionally:

* simple products and complex products
* products with attributes, options, specifications, parameters, manufacturers, images, related products, discounts, reward points, and downloadable files
* products in deep or multi-use categories
* customers from each meaningful customer group
* orders with coupons, tax, shipping, payment, currency, multiple statuses, and option-bearing line items
* multilingual products, categories, menus, or content when relevant
* pages with important aliases, metadata, redirects, modules, or filters
* records controlled by third-party plugins, POS workflows, custom fields, or external identifiers

| Sample type                | Why to include it                                                         | What to verify after Demo Migration                        |
| -------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Complex product            | Tests product meaning, options, specifications, stock, media, and pricing | Product remains sellable and understandable in Phoca Cart. |
| Customer group example     | Tests buyer segmentation and group pricing context                        | Customer group meaning remains visible and usable.         |
| Discounted or reward order | Tests commercial history and benefits                                     | Order totals and context remain explainable.               |
| Tax/shipping/payment order | Tests configuration-sensitive history                                     | Historical order details remain interpretable.             |
| Multilingual page/product  | Tests language and localized storefront assumptions                       | Localized content and paths can be validated.              |
| Extension-owned record     | Tests whether the project requires additional review                      | Non-standard data is identified before Full Migration.     |

The Demo Migration review should produce decisions, not just screenshots. If the sample set exposes missing fields, weak mappings, configuration gaps, unsupported extension data, or custom behavior, those findings should be resolved before proceeding.

### Final Preparation Check <a href="#final-preparation-check" id="final-preparation-check"></a>

Before Full Migration, the preparation work should support a clear go/no-go decision. The merchant should know what data is expected to migrate through the selected path, what target configuration remains required, what Add-ons are being used, what requires Custom Service review, and which samples will prove readiness.

| Final check                        | Pass condition                                                                                                                                                        |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Target environment confirmed       | Joomla, Phoca Cart, template, modules, languages, currencies, tax, shipping, payment, and core settings are identified.                                               |
| Catalog evidence prepared          | Products, categories, manufacturers, attributes, options, specifications, stock, images, downloads, discounts, and product relationships have representative samples. |
| Buyer/order evidence prepared      | Customers, groups, orders, coupons, reward points, tax, shipping, payment, invoices, and statuses have representative samples.                                        |
| Storefront/SEO evidence prepared   | Priority URLs, menus, aliases, metadata, redirects, modules, filters, and language paths are documented.                                                              |
| Extension/custom scope reviewed    | Plugins, integrations, POS workflows, template overrides, custom fields, custom tables, and external identifiers are classified.                                      |
| Demo Migration sample set approved | Samples expose real store complexity before Full Migration.                                                                                                           |

A Phoca Cart migration is well prepared when the target store is ready to receive meaningful data, the sample set reflects actual store complexity, and the merchant can distinguish data movement from target configuration and custom implementation needs.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Phoca Cart preparation should be evidence-driven because Phoca Cart combines Joomla site structure with commerce records, product-detail layers, buyer segmentation, operational configuration, modules, plugins, templates, and extension-owned behavior. The strongest preparation work identifies what should migrate, what should be configured in the target store, and what needs Add-on or Custom Service review before migration activity begins.

The most important preparation areas are target store readiness, catalog structure, product options and specifications, customer groups, order history, tax, shipping, payment, multilingual behavior, storefront paths, extension dependencies, access, backups, and Demo Migration samples. When those inputs are ready, validation becomes more objective and migration-scope decisions become easier to make before launch pressure begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Phoca Cart migration?**

Confirm the target Joomla and Phoca Cart environment first. The catalog, customer groups, order history, tax, shipping, payment, language behavior, modules, plugins, and storefront paths should be prepared against the actual target setup.

**Why are Phoca Cart product options and specifications important before migration?**

Options, attributes, specifications, and parameters can carry different product meanings. Preparing examples before Demo Migration helps confirm whether product choice, product description, filtering, comparison, and display behavior are being handled correctly.

**Should Joomla menus and modules be prepared before migration?**

Yes. Phoca Cart storefront continuity depends on Joomla menus, modules, aliases, templates, and sometimes search or filter modules. These areas help reviewers confirm whether migrated products and categories are usable from the storefront.

**What kind of orders should be included in Demo Migration samples?**

Use orders with multiple products, product options, coupons, reward points, tax, shipping, payment methods, different statuses, customer groups, currencies, downloadable products, and unusual operational cases.

**When should custom Phoca Cart data be reviewed before migration?**

Custom data should be reviewed when the store uses custom fields, custom tables, third-party plugins, POS workflows, import/export routines, external identifiers, custom invoice behavior, or bespoke Joomla code that controls commerce meaning.
