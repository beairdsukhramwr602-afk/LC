# OpenCart Pre-Migration Preparation Checklist

Preparing an OpenCart migration is not only a matter of exporting products, customers, and orders. OpenCart stores often look straightforward on the storefront, but important migration decisions sit inside product options, attributes, filters, categories, SEO keywords, customer groups, store settings, installed extensions, theme behavior, and payment or shipping configuration. A strong preparation process makes those layers visible before Demo Migration, so the migration scope can be tested against how the target store is expected to operate.

OpenCart preparation should therefore separate three kinds of work. First, merchants need to confirm which records should be migrated. Second, they need to identify which OpenCart settings or extension-driven behaviors must be recreated, configured, mapped, or reviewed separately. Third, they need to define what proof is required after Demo Migration and Full Migration. When those tasks are handled early, the migration is easier to scope, easier to validate, and less likely to be delayed by missing option values, duplicate SEO keywords, unsupported custom fields, or unclear extension dependencies.

### Start With the OpenCart Store Structure <a href="#start-with-the-opencart-store-structure" id="start-with-the-opencart-store-structure"></a>

Begin by documenting the active store structure rather than relying only on a product export. In OpenCart, the product record connects to catalog organization, customer-facing options, attribute data, manufacturer links, discount logic, images, SEO settings, and sometimes design overrides. A product list alone will not show whether those relationships are complete, whether they are used consistently, or whether some fields are only present because an extension added them.

The most useful first step is to create a short store map. The map should identify the active categories, manufacturers, key product groups, option sets, customer groups, main currencies, languages, tax settings, shipping methods, payment methods, active extensions, and important storefront pages. The goal is not to document every admin field. The goal is to define the parts of OpenCart that make the store usable after migration.

| Preparation area             | What to collect                                                                                                 | Why it matters                                                                            |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Catalog hierarchy            | Active categories, parent-child relationships, manufacturer assignments, filters                                | Helps confirm how products should be discovered after migration.                          |
| Product structure            | SKUs, model values, option sets, attributes, downloads, images, specials, discounts                             | Prevents product records from migrating as incomplete storefront items.                   |
| SEO and URLs                 | SEO keywords, important category/product/manufacturer/information page URLs, duplicate or missing keyword cases | Protects organic traffic and prevents route conflicts after launch.                       |
| Customer logic               | Customer groups, group-specific prices, discounts, approvals, tax-related expectations                          | Helps preserve customer segmentation and purchasing rules where supported.                |
| Extensions and modifications | Installed extensions, modified templates, order total modules, payment/shipping modules, custom fields          | Identifies work that may require Add-ons, Custom Service, or target-side reconfiguration. |

This store map becomes the anchor for Demo Migration review. Without it, validation tends to focus on counts: how many products moved, how many orders moved, how many customers moved. Counts are useful, but they do not prove that OpenCart’s catalog logic, option behavior, SEO routes, and customer-facing rules survived in a usable form.

### Prepare Product Options, Attributes, and Filters Separately <a href="#prepare-product-options-attributes-and-filters-separately" id="prepare-product-options-attributes-and-filters-separately"></a>

OpenCart preparation should not combine options, attributes, and filters into one generic “product details” task. These fields serve different storefront purposes. Options represent selectable purchase choices, such as size, color, file upload, date, or text input. Attributes describe product characteristics and can support product comparison. Filters help shoppers narrow catalog results when they are connected to categories and product groups.

Before migration, review whether options are reused consistently across products. A store may use a color option across hundreds of items, but the option values may not be standardized. One product might use “Navy,” another “Dark Blue,” and another “Blue - Navy.” If the target platform handles variants, modifiers, or option values differently, inconsistent source values can create messy product choice structures after migration.

Attributes need a separate review because they are often descriptive rather than transactional. They may not determine purchasable variations, but they can still affect product comparison, filtering expectations, theme display, or technical specification pages. If attributes are treated as variants during planning, the target structure can become overcomplicated. If variant-like options are treated as simple attributes, customers may lose the ability to choose the correct product configuration.

Filters deserve their own preparation pass because they affect discovery rather than purchase configuration. Confirm which filters are actively used, which categories rely on them, and whether they are still meaningful. Old filter groups often remain in OpenCart after catalog changes. Migrating outdated filters can make the new store look full but confusing.

| OpenCart field type | Preparation question                                                            | Migration risk if skipped                                       |
| ------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Options             | Which options are required, price-changing, stock-related, or weight-affecting? | Customers may see missing or incorrect purchase choices.        |
| Attributes          | Which attributes are meaningful specifications rather than selectable options?  | Product data may be mapped into the wrong target field type.    |
| Filters             | Which filters are used by active categories and storefront navigation?          | Catalog discovery may become noisy or incomplete.               |
| Option values       | Are naming conventions consistent across products?                              | Duplicated or fragmented values may appear in the target store. |

A strong preparation file should include representative samples, not just a list. Select several products with simple options, several with required options, several with price-changing options, several with many attributes, and several that depend on filters. Those products become the Demo Migration sample set.

### Review Categories, Manufacturers, and Product Links <a href="#review-categories-manufacturers-and-product-links" id="review-categories-manufacturers-and-product-links"></a>

OpenCart products depend on more than their product page fields. Categories, manufacturers, related products, downloads, images, reward points, discounts, and specials can all affect how records appear and behave. These relationships should be reviewed before migration because they are easy to overlook in a flat export.

Category preparation should identify the active hierarchy and any categories that exist only for historical or administrative reasons. If a category no longer appears in navigation, decide whether it should still be migrated. If a category is used for SEO landing pages, confirm its URL, metadata, and product membership. If products belong to several categories, select sample products that prove multi-category assignment after Demo Migration.

Manufacturer preparation should confirm whether manufacturer pages matter to the business. Some OpenCart stores use manufacturers as visible brand landing pages. Others keep them as backend product fields. The migration plan should reflect that difference. A manufacturer field that is visible in storefront navigation or SEO should be validated more carefully than a manufacturer value used only for internal organization.

Related products, downloads, and product images should be treated as relationship data. Images may migrate as files and image references, but the storefront still needs correct ordering, thumbnail behavior, and product association. Downloads may require special handling if digital products are part of the business. Specials and discounts should be reviewed because customer-facing price logic may depend on dates, customer groups, or promotion rules that do not translate exactly into the Target Platform.

### Clean Up SEO Keywords and URL Evidence <a href="#clean-up-seo-keywords-and-url-evidence" id="clean-up-seo-keywords-and-url-evidence"></a>

OpenCart SEO keyword preparation is essential because SEO keywords can apply to products, categories, manufacturers, and information pages. Keywords must be unique. That uniqueness requirement matters during migration because duplicate or missing SEO keywords can create route conflicts, unexpected URLs, or redirect planning gaps.

Before migration, export or record the important storefront URLs. Do not limit the list to product pages. Include category URLs, manufacturer URLs, information pages, and high-traffic landing pages. If the store uses manually edited SEO keywords, preserve those values in the preparation file. If some URLs are generated through extensions or custom rewrites, flag them separately because they may not be part of ordinary OpenCart data.

A practical SEO preparation pass should separate four groups:

| URL group         | What to review                                                            | Preparation output                                       |
| ----------------- | ------------------------------------------------------------------------- | -------------------------------------------------------- |
| Product URLs      | Active products, high-traffic products, products with edited SEO keywords | Sample URL list for redirect and validation review.      |
| Category URLs     | Parent and child categories, important landing categories                 | Category hierarchy with current URLs.                    |
| Manufacturer URLs | Brand pages that receive traffic or support navigation                    | Manufacturer URL list and visibility notes.              |
| Information pages | Terms, policy, shipping, contact, static content pages                    | CMS/content URL list and target-side ownership decision. |

The goal is not to promise that every URL can remain identical. The goal is to know which URLs matter and what redirect or target routing decisions will be needed. SEO preparation should also flag duplicate keywords, blank keywords, and outdated pages. Fixing those issues before migration can make post-launch validation cleaner.

### Identify Extensions, Modifications, and Theme-Dependent Behavior <a href="#identify-extensions-modifications-and-theme-dependent-behavior" id="identify-extensions-modifications-and-theme-dependent-behavior"></a>

OpenCart stores often depend on extensions, modules, themes, and modifications that are not part of the standard product/customer/order record set. These dependencies should be inventoried before migration because they can determine whether Standard Service is enough or whether Add-ons or Custom Service need to be reviewed.

The extension inventory should include installed payment gateways, shipping methods, order total modules, marketing extensions, feed integrations, analytics scripts, review modules, marketplace connectors, SEO extensions, product option enhancements, checkout extensions, and any custom admin fields. For each extension, identify whether it creates data, changes storefront behavior, changes checkout behavior, affects URLs, or only changes presentation.

Do not assume every extension needs to be migrated. Some extensions should be replaced by native target features. Some should be configured again on the Target Platform. Some may contain historical data that needs review. Some may be irrelevant after migration. The preparation task is to classify them, not to transfer them blindly.

| Extension role                      | Preparation decision                                                          | Likely handling path                                                             |
| ----------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Presentation/theme module           | Does it affect data or only layout?                                           | Target-side theme rebuild or configuration.                                      |
| Product data extension              | Does it add custom fields, option logic, feeds, bundles, or specifications?   | Add-ons or Custom Service review depending on support.                           |
| Checkout/payment/shipping extension | Does it store order-critical behavior or only connect to a provider?          | Reconfiguration on Target Platform; data migration only if records are involved. |
| SEO/URL extension                   | Does it generate routes, redirects, metadata, or canonical logic?             | SEO mapping, redirect planning, or Custom Service review.                        |
| Integration/feed extension          | Does it connect to ERP, marketplace, POS, accounting, or fulfillment systems? | Integration discovery and target-side replacement planning.                      |

This distinction protects the migration from scope creep. A migration can move commerce records, but it does not automatically reproduce every extension, template customization, external integration, or checkout workflow. Those items need separate planning and ownership.

### Prepare Customer Groups, Orders, and Historical Records <a href="#prepare-customer-groups-orders-and-historical-records" id="prepare-customer-groups-orders-and-historical-records"></a>

Customer and order preparation should confirm what the merchant expects to use after migration. OpenCart customer groups can affect customer organization and pricing behavior. Orders may contain statuses, totals, taxes, shipping/payment labels, coupons, vouchers, product options, and historical customer details. Migrating the records is only useful if the target store can display and interpret them in a way the business can use.

Before migration, prepare samples from ordinary customers, wholesale or special customer groups, guest customers, customers with reward points or store credit where used, and customers tied to important order history. For orders, choose samples with simple products, option-selected products, discounts, specials, taxes, shipping charges, refunds or returns where relevant, and different statuses.

Historical orders should be reviewed for operational purpose. Some merchants need them for customer service lookup. Others need them for accounting references. Others want them visible in customer accounts. The target expectation changes how validation should be conducted. If order history only needs to be searchable by staff, the pass condition is different from a store where customers must see complete historical order details in their accounts.

### Prepare the Target Store Before Demo Migration <a href="#prepare-the-target-store-before-demo-migration" id="prepare-the-target-store-before-demo-migration"></a>

Preparation should include the Target Platform environment, not only the OpenCart source store. A Demo Migration can only prove meaningful results if the target store has enough structure to display migrated records correctly. That does not mean every design detail must be finished, but the store should be prepared enough to test products, categories, options, customer groups, URLs, and order history.

At minimum, confirm the target store is accessible, the admin user has sufficient permission, the destination is not filled with unrelated test data, and core settings such as currency, language, tax, weight, length, stock, and customer account behavior are known. If the target platform requires specific product type decisions, collection setup, customer-group equivalents, URL behavior, or app configuration, those decisions should be documented before Demo Migration.

Demo Migration should use representative records, not only easy ones. Include products with required options, price-changing options, attributes, filters, multiple categories, specials, discounts, manufacturer links, images, and SEO keywords. Include customers from different customer groups and orders with meaningful totals and option selections.

### Decide What Belongs in Standard Service, Add-ons, or Custom Service Review <a href="#decide-what-belongs-in-standard-service-add-ons-or-custom-service-review" id="decide-what-belongs-in-standard-service-add-ons-or-custom-service-review"></a>

A preparation checklist should end with a service-scope decision. Standard Service may be appropriate when the store relies mainly on ordinary supported OpenCart records and conventional catalog behavior. Add-ons may help when supported data needs filtering, mapping, or configuration adjustments. Custom Service becomes relevant when extension-owned fields, bespoke tables, modified logic, external identifiers, unusual option structures, or custom checkout records need tailored review.

| Preparation finding                                                                                | What it means                                                              | Likely next step                                                 |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Ordinary products, categories, customers, orders, manufacturers, reviews, coupons, and CMS content | Scope is mostly standard commerce data.                                    | Demo Migration through a standard path may be reasonable.        |
| Large catalog with selected date ranges, category subsets, or mapping adjustments                  | Supported records need bounded control.                                    | Review Add-ons such as filtering or advanced mapping.            |
| Extension-owned product fields or custom tables                                                    | Source data may not exist in ordinary OpenCart exports.                    | Request Custom Service review.                                   |
| Complex options, modified checkout, or external integration IDs                                    | The migration may need tailored logic or target-side replacement planning. | Separate migration scope from integration or configuration work. |
| Later catalog changes are expected before launch                                                   | The migration path may need follow-up handling.                            | Plan Additional Migration Options and revalidation steps.        |

Entity Points should also be considered during preparation. Eligible Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because another migration action happens on the same migration path. That distinction matters when planning a launch window, especially if the source store will continue receiving new products, customers, or orders before final cutover.

### Conclusion <a href="#conclusion" id="conclusion"></a>

OpenCart migration preparation is strongest when it treats the store as a connected operating environment rather than a set of isolated export files. Products, options, attributes, filters, categories, SEO keywords, customer groups, orders, extensions, and store settings all shape the migration outcome. Preparing those layers before Demo Migration gives merchants a clearer scope, better samples, stronger validation evidence, and a more realistic service-path decision.

The best preparation work is practical and selective. It does not require documenting every field in the store. It requires identifying which data structures and behaviors make the OpenCart store usable, which ones are standard enough to migrate directly, which ones need Add-ons, and which ones require Custom Service or target-side configuration planning.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Should every OpenCart extension be migrated?**

No. Many OpenCart extensions control storefront behavior, checkout connections, feeds, or presentation rather than portable data. Each extension should be classified by whether it creates records, changes mapping expectations, affects URLs, or needs to be replaced through target-side configuration.

**Why should options and attributes be prepared separately?**

Options and attributes serve different purposes. Options are customer-facing purchase selections that may affect price, stock, points, or weight. Attributes describe product characteristics and may support comparison or display. Mixing them during preparation can lead to incorrect target structures.

**What OpenCart records should be included in Demo Migration samples?**

Samples should include ordinary products, products with required and price-changing options, products with attributes and filters, multi-category products, customer groups, orders with discounts or taxes, high-value URLs, and records affected by important extensions.

**Do SEO keywords automatically solve URL continuity?**

No. SEO keywords are important evidence, but the target store may route products, categories, manufacturers, and content pages differently. Important URLs should be collected and used for redirect and validation planning.

**When should Custom Service be considered for OpenCart?**

Custom Service should be considered when the store depends on unsupported extension data, custom tables, modified checkout logic, bespoke product fields, external identifiers, or migration behavior that cannot be handled through supported standard records or bounded Add-ons.
