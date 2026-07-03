# Zen Cart Data Model Differences

A Zen Cart migration is not only a transfer of database rows into another store. It is a translation of store meaning into a self-hosted commerce application where catalog structure, attributes, order totals, modules, templates, EZ-Pages, plugins, and configuration all influence how the data behaves after migration.

The most important planning question is not simply whether a record exists in the target store. The better question is whether Zen Cart can interpret the record in the same business context. Products must remain sellable, attributes must remain selectable, orders must remain readable, discounts must remain understandable, content must remain findable, and custom fields must be separated from standard migration scope before they create false confidence.

### What Data Model Differences Mean for Zen Cart <a href="#what-data-model-differences-mean-for-zen-cart" id="what-data-model-differences-mean-for-zen-cart"></a>

Zen Cart gives merchants direct control over a self-hosted store, but that control also means the data model is closely connected to configuration. A product record may depend on categories, attributes, tax classes, product type, downloadable settings, specials, sale behavior, quantity discounts, images, product model values, and template output. An order may preserve historical customer and line-item data, while the target store still requires separate payment, shipping, tax, coupon, and order-total module configuration for new checkout activity.

This distinction matters because migrated records and target-store behavior are not the same thing. A historical order can show a payment label without activating a payment module. A product can carry an option name without reproducing source-side inventory logic. A content page can migrate as text while its original menu placement, URL behavior, or sidebox visibility needs separate attention.

| Source data area                 | Zen Cart interpretation                                                                                                                                          | Migration planning implication                                                                                                                                                   |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products                         | Catalog entries connected to categories, images, product model values, price, quantity, product status, tax class, product type, and attribute assignment.       | Product samples should include ordinary products, discounted products, attribute-heavy products, downloadable products, inactive products, and products with important metadata. |
| Categories and product placement | Category structure, listing order, category status, linked product behavior, and product-to-category assignment.                                                 | Source collections or departments should be checked for hierarchy, duplicate visibility, linked placement, and navigation continuity.                                            |
| Attributes and options           | Option names, option values, required choices, display behavior, price adjustments, weight adjustments, downloads, and text-style selections.                    | Source variants and modifiers need semantic review, not only field mapping.                                                                                                      |
| Customers                        | Account identity, billing and shipping addresses, newsletter status, order relationship, and customer-group behavior where configured.                           | Customer records should be validated as usable account records, while special memberships or approval logic may need custom review.                                              |
| Orders                           | Order header, address snapshots, product lines, selected attributes, tax, shipping, discounts, coupons, gift certificates, comments, statuses, and order totals. | Order validation should focus on readability for customer service, finance, and fulfillment.                                                                                     |
| Content and navigation           | EZ-Pages, define pages, CMS Pages, product/category descriptions, sideboxes, links, banners, and template-controlled placement.                                  | Content must be matched to the correct target structure, not treated as generic page text.                                                                                       |
| Custom or plugin data            | Plugin tables, custom fields, modified admin screens, template overrides, integration identifiers, and non-standard business logic.                              | Unsupported records or custom behavior should be reviewed through Custom Service when preservation is required.                                                                  |

Zen Cart therefore rewards careful data interpretation. The migration plan should identify which records can move as standard store data, which values require mapping or configuration, and which requirements are actually customization, module, or Custom Service questions.

### Product and Category Translation <a href="#product-and-category-translation" id="product-and-category-translation"></a>

Product data in Zen Cart should be read as a complete selling object. The product name and description are only the visible beginning. The record may also carry model value, manufacturer-style context, product status, quantity, weight, tax class, price, special price, sale behavior, image relationships, product type, metadata, and assignment to one or more categories.

A source product that appears simple in another platform can become more complex when the target store needs Zen Cart-specific decisions. For example, a source product with color and size choices may not be a separate variant record in Zen Cart. It may need option names, option values, assigned attributes, price adjustment rules, selection display settings, and order-line validation. A source product that appears in multiple collections may become a single Zen Cart product linked to multiple categories rather than several duplicate product records.

Category translation also needs attention. Source stores often use collections, departments, brands, menus, landing pages, filters, or automated catalog groups. Zen Cart categories can represent part of that structure, but not every source grouping should automatically become a category. Migration planning should ask whether each source group is a true product location, a merchandising filter, a brand page, an SEO landing page, or a navigation convenience.

| Source structure                               | Likely Zen Cart question                                                                        | What to validate                                                                                        |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Deep category tree                             | Should the same hierarchy be reproduced, simplified, or redirected?                             | Category depth, parent-child relationships, product visibility, menu behavior, and metadata.            |
| Product assigned to several source collections | Should it become a linked product in multiple Zen Cart categories?                              | Single product identity, category visibility, canonical navigation expectations, and admin readability. |
| Brand or vendor collection                     | Should it become a category, manufacturer-style value, search/filter behavior, or content page? | Shopper navigation, SEO value, and product discovery.                                                   |
| Source product family with child variants      | Should choices become attributes rather than separate products?                                 | Product page selection, cart line display, price changes, and order-line meaning.                       |
| Digital product                                | Should it use downloadable product behavior or another structure?                               | File access, checkout activation, order status dependency, and customer delivery experience.            |

Product placement should be tested both from the admin area and the storefront. A category may look correct in the database while listing order, image handling, product status, or linked-product behavior still affects shopper discovery.

### Attribute, Option, and Product-Choice Meaning <a href="#attribute-option-and-product-choice-meaning" id="attribute-option-and-product-choice-meaning"></a>

Zen Cart attributes are one of the most important translation areas. They can carry shopper selections such as size, color, style, finish, personalization, download choice, text input, or other product-level choices. They can also affect price, weight, required selection behavior, default prompts, and order-line meaning.

The main risk is assuming that source variants, options, configurable products, modifiers, add-on choices, or personalization fields all translate the same way. They do not. Some source choices become straightforward option names and option values. Some require careful price-adjustment logic. Some require text fields or download settings. Some depend on source-side app logic that Zen Cart will not reproduce through ordinary product attributes.

A strong migration plan separates display choices from commercial choices. If a customer selection only changes visible text, validation can focus on product page display and order-line readability. If a selection changes price, shipping weight, download access, fulfillment process, or tax treatment, validation must also check cart totals, shipping behavior, and historical order interpretation.

| Attribute scenario             | Why it changes meaning                                                                     | Planning response                                                                                                                   |
| ------------------------------ | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| Size and color options         | Source platforms may store them as variants, option values, attributes, or child products. | Confirm whether Zen Cart should show choices as assigned product attributes and how those choices appear in cart and order history. |
| Price-changing options         | Zen Cart can represent price adjustments, but source logic may use different rules.        | Test products with positive adjustments, discounts, sale prices, and attribute combinations.                                        |
| Weight-changing options        | Shipping calculation may be affected by selected attributes.                               | Validate cart weight and shipping estimate behavior for representative products.                                                    |
| Required choices               | Source defaults may not match Zen Cart selection prompts.                                  | Confirm required selections, default values, and shopper error handling.                                                            |
| Text or personalization fields | Free-text values may require specific attribute handling or custom interpretation.         | Validate storefront entry, cart display, order-line display, and admin readability.                                                 |
| Downloadable choices           | Digital delivery depends on product, attribute, order status, and file settings.           | Test purchase, order status, download activation, and customer access.                                                              |

Attribute translation should not be approved by looking only at the product edit screen. It must be validated through product page display, add-to-cart behavior, cart calculation, order confirmation, admin order review, and historical order examples.

### Pricing, Discounts, Coupons, and Order Totals <a href="#pricing-discounts-coupons-and-order-totals" id="pricing-discounts-coupons-and-order-totals"></a>

Commercial data changes meaning when it moves into Zen Cart because pricing is distributed across several layers. Product price, specials, sale products, quantity discounts, attribute price adjustments, group pricing, coupons, gift certificates, tax settings, shipping fees, payment fees, and order-total modules may all influence what the customer paid or will pay.

Historical orders and active selling behavior should be separated. Historical orders should preserve what happened: product lines, selected attributes, subtotal, discounts, coupon values, gift certificate use, tax, shipping, fees, and grand total. Active selling behavior requires target configuration: current product prices, tax rules, shipping modules, payment modules, order-total modules, coupon setup, group pricing, and checkout testing.

This is where many migrations create false confidence. A sample order may appear complete because the total is visible, but the store may still not be ready to calculate a new order correctly. Conversely, live configuration may be correct while historical orders need better labels or comments so support staff understand what happened before migration.

| Commercial element               | Historical migration concern                               | Target behavior concern                                                                             |
| -------------------------------- | ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Product price                    | Preserve price shown on historical order lines.            | Confirm current product pricing and sale/special behavior.                                          |
| Attribute price adjustment       | Preserve selected option and price effect where available. | Confirm cart calculation for selected attributes.                                                   |
| Coupon or discount               | Preserve historical discount label and value.              | Configure and test active coupon/order-total behavior separately.                                   |
| Gift certificate or store credit | Preserve historical meaning where supported.               | Confirm whether active balances, redemption, and accounting expectations require separate handling. |
| Tax and shipping                 | Preserve historical tax/shipping lines.                    | Configure tax zones, shipping modules, and test checkout scenarios.                                 |
| Group or wholesale pricing       | Preserve customer/order context where possible.            | Confirm target group-pricing setup and active price visibility.                                     |

The safest approach is to validate commercial data in two passes: historical readability first, live calculation second.

### Customer, Address, and Account Meaning <a href="#customer-address-and-account-meaning" id="customer-address-and-account-meaning"></a>

Customer migration into Zen Cart should preserve account usability and operational meaning. Standard customer data often includes name, email, billing address, shipping address, address book entries, newsletter status, account creation context, and order relationship. These values must be readable and usable after migration.

Additional customer meaning can be harder. Source stores may hold approval status, wholesale tier, customer group, loyalty balance, tax exemption, external CRM ID, B2B account relationship, store credit, marketing consent, or custom fields. Some of those values may fit target configuration. Others may exist only through plugins, custom fields, or external systems.

Customer data should therefore be reviewed by role, not only by field name. Customer service needs account lookup and order history. Finance may need tax or group pricing evidence. Marketing may need newsletter status and segmentation context. Fulfillment may need valid shipping addresses. If one source customer field supports a business process, the migration plan should identify whether Zen Cart can use it, preserve it as reference information, or requires Custom Service.

Address data deserves special attention because older stores often contain inconsistent country names, state values, postal codes, phone formats, or multi-address records. A technically migrated address is not enough if the target store cannot use it for checkout, shipping, tax, or customer-service review.

### Order History, Status, and Admin Readability <a href="#order-history-status-and-admin-readability" id="order-history-status-and-admin-readability"></a>

Orders in Zen Cart are operational records. A historical order should show who purchased, what was purchased, which attributes were selected, which addresses were used, which totals applied, which payment and shipping labels were recorded, what comments or status history matter, and how customer service can read the transaction after launch.

Source orders may carry details that do not have a direct Zen Cart equivalent. Examples include app-created fulfillment states, marketplace order IDs, subscription cycles, fraud review markers, refund reasons, custom payment metadata, external accounting IDs, tax-service calculations, split shipments, or admin notes stored by an extension. These values should be classified before migration, not discovered during launch validation.

| Order area                  | What can go wrong                                                                                    | Validation cue                                                                     |
| --------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Selected attributes         | The product line migrates, but the purchased size, color, text field, or download choice is missing. | Compare source order lines with Zen Cart order lines for attribute-heavy products. |
| Order totals                | Discounts, coupons, fees, shipping, tax, or gift certificate lines appear unclear.                   | Confirm subtotal-to-grand-total logic is readable for finance and support.         |
| Status history              | Status labels are present but do not carry the same operational meaning.                             | Review completed, pending, canceled, refunded, and manually adjusted orders.       |
| Payment and shipping labels | Historical labels are mistaken for active module configuration.                                      | Separate historical order review from live checkout testing.                       |
| Comments and notes          | Important customer-service context is lost or buried.                                                | Sample orders with admin comments, customer comments, and exception handling.      |
| External references         | Marketplace, ERP, accounting, or shipping IDs are missing.                                           | Identify required external identifiers before final scope approval.                |

Historical order validation should include both ordinary and exception cases. The exception cases are often where migration quality is tested most clearly.

### Content, Navigation, SEO, and Storefront Context <a href="#content-navigation-seo-and-storefront-context" id="content-navigation-seo-and-storefront-context"></a>

Zen Cart content can involve EZ-Pages, define pages, CMS Pages, category descriptions, product descriptions, meta tags, sidebox links, header or footer navigation, banners, templates, language files, and SEO-related plugins. Source content should not be treated as a flat set of pages unless the target store’s navigation and SEO expectations are simple.

A source page may become an EZ-Page, a define page, a category description, a product description, a custom template block, or a plugin-controlled landing page. A source URL may need a redirect rather than a direct equivalent. A source menu link may depend on sidebox settings or template behavior rather than content migration.

Content migration should be evaluated by customer path. Can shoppers still find policies, buying guides, landing pages, and product information? Can search engines follow important URLs or redirects? Do category and product metadata survive where they matter? Are sidebox, header, footer, sitemap, and link-placement expectations part of migration scope or target configuration?

The distinction is important because a migrated CMS Page does not automatically recreate the old store’s navigation architecture. Storefront continuity requires both migrated content and target-side placement decisions.

### Plugin, Custom Field, and Database Extension Meaning <a href="#plugin-custom-field-and-database-extension-meaning" id="plugin-custom-field-and-database-extension-meaning"></a>

Zen Cart stores frequently include plugins, custom files, custom tables, modified templates, language overrides, reporting extensions, feed generators, SEO modules, shipping integrations, payment modules, marketplace connectors, and admin process changes. These additions may store data outside standard product, customer, order, and content structures.

A plugin can change how data is stored, displayed, calculated, or exported. It may add a customer field, modify order totals, create a product flag, store an external ID, generate a feed, control SEO URLs, or change admin process. When those records are business-critical, they should not be treated as ordinary migration data.

Unsupported plugin data, custom fields, custom database tables, and bespoke transformation requirements belong in Custom Service review. Add-ons can support bounded filtering, mapping, or configuration needs, but they should not be used to imply that custom plugin behavior, target-store development, module setup, or theme rebuilding is automatically included.

### Turning Data Differences Into Migration Scope <a href="#turning-data-differences-into-migration-scope" id="turning-data-differences-into-migration-scope"></a>

The practical outcome of data-model review is a cleaner scope decision. Some Zen Cart data differences can be handled through standard migration behavior. Some require mapping or configuration choices. Some require Add-ons. Some require Custom Service because the data does not fit supported structures or depends on custom interpretation.

| Data difference                                                               | Likely handling path                                                               | Scope decision cue                                                                    |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Standard Products, Customers, Orders, Categories, Reviews, Coupons, CMS Pages | Standard Service when supported fields and structures are ordinary.                | Demo Migration confirms records are readable and usable in target context.            |
| Category or product filtering needs                                           | Data Filter Add-on where supported and bounded.                                    | Filtering rules are clear, field-based, and do not require custom interpretation.     |
| Field remapping or value adjustment                                           | Advanced Data Mapping or Advanced Data Configure where supported.                  | Source values have a clear target meaning but need controlled mapping/configuration.  |
| Plugin-owned fields or custom tables                                          | Custom Service.                                                                    | The data is outside standard entities or requires custom migration logic adjustment.  |
| Custom URL, SEO, or content transformation                                    | Custom Service when transformation goes beyond supported behavior.                 | URLs, metadata, redirects, or content placement require bespoke logic.                |
| External-system identifiers                                                   | Custom Service when they must remain stable and are not supported standard fields. | ERP, PIM, accounting, marketplace, shipping, or reporting continuity depends on them. |

Entity Points may be relevant when eligible new Products, Customers, Orders, or Blog Posts are migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because another action happens on the same migration path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Zen Cart data-model differences are concentrated in the areas where store data becomes operating behavior: attributes, linked product placement, order totals, coupons, gift certificates, group pricing, modules, EZ-Pages, SEO fields, sideboxes, templates, plugins, and custom database changes. A migration plan should not approve the target store because record counts look complete. It should verify whether Zen Cart can interpret each migrated record in the right business context.

The safest scope decision comes from sample evidence. Test complex products, linked categories, selected attributes, discounted orders, coupons, gift certificates, customer groups, content pages, SEO values, plugin-dependent fields, and external identifiers before Full Migration. When the target behavior depends on unsupported data or custom interpretation, Custom Service review is the appropriate path.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Zen Cart attributes need special migration review?**

Attributes can affect shopper choices, selected order values, pricing, weight, downloads, and required selection behavior. A source variant or option should be tested in the product page, cart, checkout, and order record before it is considered safe.

**Does migrating historical orders configure live Zen Cart checkout?**

No. Historical orders preserve past transaction context. Live checkout still requires separate configuration and testing for payment, shipping, tax, coupon, gift-certificate, and order-total modules.

**Can every source collection become a Zen Cart category?**

Not always. Some source collections are real categories, while others are filters, brand pages, landing pages, or merchandising groups. The migration plan should decide which structures belong as Zen Cart categories and which require another handling path.

**When does plugin or custom database data require Custom Service?**

Custom Service is appropriate when required data lives in custom fields, custom tables, unsupported plugin records, modified modules, or external-system identifiers that need custom interpretation or custom migration logic adjustment.

**How should CMS Pages be reviewed for Zen Cart?**

CMS Pages should be matched to the correct Zen Cart content location, such as EZ-Pages, define pages, category descriptions, product descriptions, or another content structure. Navigation placement, redirects, metadata, and sidebox links may require separate target configuration.
