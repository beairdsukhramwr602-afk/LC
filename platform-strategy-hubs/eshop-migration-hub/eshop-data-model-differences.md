# EShop Data Model Differences

EShop by Ossolution Team is not only a destination for imported product and order records. It is a Joomla e-commerce extension with its own way of organizing catalog data, shopper-facing product choice, customer records, checkout information, discounts, vouchers, taxes, shipping, payments, modules, themes, multilingual content, and extension-level customization.

A migration to EShop should therefore be evaluated as a translation of commercial meaning into a Joomla MVC-based store environment. The question is not whether source records can be moved into a new administration area. The more important question is whether those records still explain how the store sells, how customers buy, how orders are understood, and how Joomla presents the commerce experience after migration.

### Core Data Layers in an EShop Migration <a href="#core-data-layers-in-an-eshop-migration" id="core-data-layers-in-an-eshop-migration"></a>

EShop separates store meaning across catalog, sales, system-management, plugin, theme, module, multilingual, and developer-customization layers. These layers may have been combined differently in the Source Platform.

| EShop data layer             | What it usually controls                                                                                                          | Migration interpretation                                                                                                      |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure            | Products, categories, manufacturers, options, attributes, attribute groups, labels, downloads, reviews, and product relationships | Product records must remain sellable, searchable, organized, and understandable inside EShop rather than merely visible.      |
| Sales structure              | Customers, customer groups, orders, coupons, discounts, vouchers, checkout fields, quotes, and notifications                      | Customer and order history must preserve operational meaning, pricing context, and post-launch reference value.               |
| System-management structure  | Countries, currencies, stock statuses, order statuses, zones, geo zones, tax classes, tax rates, reports, and export settings     | Some behavior depends on target configuration rather than record migration alone.                                             |
| Plugin and integration layer | Payment plugins, shipping plugins, miscellaneous plugins, newsletter integration, and related extension behavior                  | Gateway, carrier, membership, search, notification, and integration behavior may need configuration or Custom Service review. |
| Joomla presentation layer    | Menus, modules, templates, themes, layout overrides, aliases, metadata, and multilingual site structure                           | Storefront output depends on Joomla implementation decisions as well as migrated EShop records.                               |
| Customization layer          | Joomla MVC layout customization, EShop plugin development, payment plugin development, and shipping plugin development            | Custom or extension-owned behavior may require custom migration logic adjustment through Custom Service.                      |

This structure is why EShop migration planning must connect data records with store behavior. A product can migrate successfully but still lose commercial meaning if its options, attributes, customer group pricing, downloads, manufacturer relationship, review context, or storefront placement is not interpreted correctly.

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

#### Products are commercial objects, not flat records <a href="#products-are-commercial-objects-not-flat-records" id="products-are-commercial-objects-not-flat-records"></a>

In EShop, a product may carry much more than a name, SKU, price, description, and image. Depending on the source store, the product may include category relationships, manufacturer context, attributes, options, labels, tabs, related products, downloadable files, reviews, discounts, special pricing, tax class behavior, stock behavior, dimensions, weight, metadata, and language-specific content.

When migrating into EShop, product data should be reviewed as a selling structure. A simple source product may translate cleanly into a straightforward EShop product. A product with variations, configurable choices, customer group pricing, downloadable assets, or multiple display sections requires more careful interpretation.

The key distinction is that source fields should not be mapped only by label similarity. They should be mapped by business meaning. For example, a source field that looks like a product option may actually be a shopper selection, an internal attribute, a filter value, a bundled choice, a personalization field, or an extension-generated value. Each of those meanings may require a different treatment in EShop.

#### Categories define organization and discovery <a href="#categories-define-organization-and-discovery" id="categories-define-organization-and-discovery"></a>

Categories in EShop affect how shoppers browse and how the storefront presents the catalog. A migrated category structure should support discovery, navigation, and product grouping inside the Joomla site.

Source categories can become risky when they include duplicate paths, historical cleanup issues, category names used for merchandising rather than structure, SEO-specific landing categories, hidden categories, or app-generated collections. The migration plan should identify whether source categories should remain as EShop categories, become Joomla content or landing pages, be merged, or be excluded from the launch structure.

Category migration also affects validation. A store can have all products present while still being difficult to browse if category placement, parent-child relationships, aliases, metadata, or menu behavior does not match the intended EShop storefront.

#### Options and attributes have different meanings <a href="#options-and-attributes-have-different-meanings" id="options-and-attributes-have-different-meanings"></a>

Options and attributes should not be treated as interchangeable. In EShop, options are typically shopper-facing choices that can affect product selection before adding an item to the cart. Attributes usually describe product characteristics and may support product information, comparison, filtering, or structured display.

This distinction matters because many Source Platforms use different terminology. A source “attribute” might be a shopper choice in one platform, a filter in another, and an informational specification in another. During migration, the planning question is not only where the field can be placed, but what it is supposed to do after launch.

| Source data pattern                                                                       | Likely EShop interpretation question                                                                          | Why it matters                                                                                                              |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Size, color, material, package, or personalization choice                                 | Should this become an EShop option, and is it required before add-to-cart?                                    | Shopper choice affects cart behavior, order line meaning, price, and inventory interpretation.                              |
| Technical specification, material description, dimensions, compatibility, or feature list | Should this become an attribute or attribute-group value?                                                     | Informational characteristics help comparison and product understanding without necessarily controlling purchase selection. |
| App-created product field                                                                 | Is this a standard product field, custom field, attribute, option, tab, or unsupported extension-owned value? | Custom or app-owned data may need Advanced Data Mapping, Advanced Data Configure, or Custom Service review.                 |
| Bundled product logic or configurable package                                             | Can EShop represent the commercial meaning directly, or does the target setup need customization?             | Bundles and packages can affect product choice, fulfillment, inventory, and order interpretation.                           |

A strong EShop data model migration must preserve the difference between what shoppers choose, what merchants use to organize products, and what customers only need to read.

#### Manufacturers, labels, reviews, downloads, and product tabs add context <a href="#manufacturers-labels-reviews-downloads-and-product-tabs-add-context" id="manufacturers-labels-reviews-downloads-and-product-tabs-add-context"></a>

EShop supports product context beyond the core product table. Manufacturers can carry brand or supplier meaning. Labels can support visual merchandising. Reviews may affect buyer confidence. Downloads may support digital products or product attachments. Product tabs and custom display sections may organize product information in a way that matters to shoppers.

These layers should be reviewed before migration because they often reveal hidden source-platform assumptions. A merchant may expect a manufacturer to appear as a brand filter, a label to drive merchandising, a download to remain customer-accessible, or a tab to preserve important product information. If these expectations are not documented, the migrated product may look thinner than expected even when the main product record appears complete.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

#### Customers carry identity, segmentation, and history <a href="#customers-carry-identity-segmentation-and-history" id="customers-carry-identity-segmentation-and-history"></a>

Customer data in EShop should be interpreted as more than contact information. Customer records can support account access, order history, customer group assignment, pricing eligibility, address records, communication, reporting, and customer-service context.

Source customer data may include fields that are standard in the old platform but not directly equivalent in EShop. Examples include B2B account references, customer tags, wholesale roles, loyalty identifiers, membership links, subscription data, external CRM IDs, or custom profile fields. These details should be classified before migration.

If the source customer structure is straightforward, standard migration planning may be enough. If customer meaning depends on customer groups, custom fields, third-party services, membership extensions, or external identifiers, the project may need Add-on review or Custom Service review.

#### Customer groups can affect pricing and access assumptions <a href="#customer-groups-can-affect-pricing-and-access-assumptions" id="customer-groups-can-affect-pricing-and-access-assumptions"></a>

Customer groups are especially important for EShop because they may shape pricing, discounts, visibility expectations, or operational segmentation. A merchant moving from a platform with wholesale accounts, reseller pricing, VIP buyers, internal customer tags, or B2B-specific logic should not assume those meanings will automatically translate into the same behavior.

The migration plan should clarify what customer groups are supposed to represent after launch. Are they used for pricing? Are they used for reporting? Are they used for account organization? Are they replacing source tags or roles? Different answers lead to different mapping and validation needs.

### Order and Sales History Meaning <a href="#order-and-sales-history-meaning" id="order-and-sales-history-meaning"></a>

#### Orders must remain readable for operations <a href="#orders-must-remain-readable-for-operations" id="orders-must-remain-readable-for-operations"></a>

Order migration into EShop should preserve the history needed for customer service, fulfillment reference, accounting review, and post-launch support. A useful order record includes more than an order ID and total. It should preserve products ordered, models or SKUs where applicable, quantities, option selections, unit prices, discounts, tax, shipping, payment method, shipping method, comments, order status, customer relationship, and relevant historical context as far as the selected migration path and supported behavior allow.

The challenge is that order records often contain source-specific meaning. A custom order status, external payment reference, marketplace ID, warehouse reference, gift-card transaction, fulfillment note, refund state, or subscription renewal may not be a simple EShop order field. These details should be reviewed before migration so expectations are clear.

#### Order statuses and stock statuses need semantic review <a href="#order-statuses-and-stock-statuses-need-semantic-review" id="order-statuses-and-stock-statuses-need-semantic-review"></a>

Order statuses and stock statuses may look like simple labels, but they often encode operational workflow. A source status such as “Awaiting Pickup,” “Partially Fulfilled,” “Manual Review,” “Backordered,” or “Ready for Vendor” may not have a direct EShop equivalent unless the target workflow is configured deliberately.

The migration plan should identify which statuses need to be preserved as historical labels, which should be mapped into EShop statuses, and which depend on post-migration operational setup. Status mapping is especially important when merchants rely on historical orders for support, reporting, or fulfillment follow-up.

#### Discounts, coupons, vouchers, and quotes have separate meanings <a href="#discounts-coupons-vouchers-and-quotes-have-separate-meanings" id="discounts-coupons-vouchers-and-quotes-have-separate-meanings"></a>

EShop includes multiple sales-related structures, including coupons, discounts, vouchers, and quotes. These should not be collapsed into one generic discount concept during migration planning.

Coupons usually represent promotional codes or conditions. Discounts may represent product-level, customer-group, or configured price behavior. Vouchers may carry store-credit or gift-certificate meaning. Quotes may support pre-purchase negotiation or request-based selling. Source platforms can use these concepts differently, so each should be interpreted by business meaning rather than name similarity.

For example, a source “discount” might be a coupon, a special product price, a customer group rule, a voucher redemption, or a manual order adjustment. The correct EShop destination depends on what the value is expected to do after migration.

### Checkout, Tax, Shipping, and Payment Meaning <a href="#checkout-tax-shipping-and-payment-meaning" id="checkout-tax-shipping-and-payment-meaning"></a>

#### Checkout fields may be data, configuration, or business rules <a href="#checkout-fields-may-be-data-configuration-or-business-rules" id="checkout-fields-may-be-data-configuration-or-business-rules"></a>

EShop supports checkout-related field structures, and source stores may contain custom checkout fields, account fields, address fields, tax fields, shipping preferences, delivery instructions, VAT identifiers, company details, or custom agreement fields. Some of this information may be migratable data. Some may need to be configured in EShop. Some may be source-specific behavior that requires deeper review.

The migration question should be: does the field need to appear in historical records, future checkout, customer accounts, order details, reports, or internal operations? Each use case changes the correct treatment.

#### Taxes and geo-zones depend on target configuration <a href="#taxes-and-geo-zones-depend-on-target-configuration" id="taxes-and-geo-zones-depend-on-target-configuration"></a>

Tax migration should be handled carefully because tax behavior usually depends on target configuration, not only migrated values. EShop tax behavior may involve countries, zones, geo zones, tax classes, and tax rates. A source platform may calculate tax using different rules, third-party services, product classifications, customer exemptions, or region-specific logic.

Historical tax values in orders can often be preserved as part of order history, but future tax calculation depends on EShop configuration. These two ideas should be kept separate. Confusing historical order tax with future tax setup can lead to incorrect validation expectations.

#### Shipping and payment behavior is plugin-sensitive <a href="#shipping-and-payment-behavior-is-plugin-sensitive" id="shipping-and-payment-behavior-is-plugin-sensitive"></a>

EShop supports shipping and payment plugin structures. A migrated store may need flat-rate shipping, price-based shipping, item-based shipping, free shipping, weight-based shipping, quantity-based shipping, postcode-based shipping, carrier-based shipping, PayPal, Stripe, Authorize.Net, offline payment, Square, or other payment methods depending on the implementation.

Migration planning should separate record migration from plugin configuration. An order’s historical payment method or shipping method can be useful as history, but the ability to process future payments or calculate future shipping depends on installed, configured, and tested EShop plugins.

### Joomla Storefront and Presentation Meaning <a href="#joomla-storefront-and-presentation-meaning" id="joomla-storefront-and-presentation-meaning"></a>

#### Storefront records depend on Joomla navigation and modules <a href="#storefront-records-depend-on-joomla-navigation-and-modules" id="storefront-records-depend-on-joomla-navigation-and-modules"></a>

EShop store presentation is shaped by Joomla menus, modules, templates, themes, product layouts, category layouts, search modules, cart modules, product modules, category modules, manufacturer modules, and filtering modules. The data model therefore includes a storefront context layer that is not always present in hosted commerce platforms.

A product may exist in EShop, but the shopper experience depends on how Joomla exposes that product through menus, modules, category pages, search, filters, and templates. Migration planning should identify where the source storefront used collections, landing pages, menu hierarchies, SEO paths, or promotional modules that need to be recreated in Joomla rather than migrated as ordinary store records.

#### SEO aliases, metadata, and routes need interpretation <a href="#seo-aliases-metadata-and-routes-need-interpretation" id="seo-aliases-metadata-and-routes-need-interpretation"></a>

EShop and Joomla storefront pages can involve aliases, metadata, menu item routing, and search-engine-friendly URL behavior. Source platforms may store URLs, handles, slugs, metadata, canonical logic, redirects, and collection paths differently.

The data model question is whether source SEO values should become EShop product/category metadata, Joomla menu metadata, redirect rules, content-page metadata, or implementation tasks. This distinction matters because SEO continuity often depends on a combination of migrated data and Joomla site configuration.

### Multilingual and Multicurrency Meaning <a href="#multilingual-and-multicurrency-meaning" id="multilingual-and-multicurrency-meaning"></a>

EShop can be used in multilingual and multicurrency contexts, but multilingual commerce migration is rarely just field copying. Product names, descriptions, categories, attributes, options, metadata, checkout labels, currency display, and localized store configuration can all carry language-specific or region-specific meaning.

A source platform may store translations inside the same product record, separate language tables, third-party apps, custom fields, or external translation systems. Before migration, the merchant should identify which languages must launch, which translated fields matter most, whether URL structures differ by language, and whether currency behavior is display-only or operationally meaningful.

Multilingual migration risk increases when translations are incomplete, language-specific SEO is important, or the target Joomla multilingual structure is not already planned. These situations may require more careful mapping, implementation coordination, or Custom Service review.

### Extension-Owned and Custom Source Data Meaning <a href="#extension-owned-and-custom-source-data-meaning" id="extension-owned-and-custom-source-data-meaning"></a>

EShop is built for Joomla and supports customization through themes, modules, plugins, layout overrides, and developer workflows. That flexibility is useful, but it also means that a source store may contain data and behavior that cannot be understood from standard commerce entities alone.

Custom Platform data, extension-owned fields, external identifiers, ERP references, CRM links, membership data, subscription records, marketplace information, custom shipping logic, custom payment behavior, or bespoke product relationships should not be treated as ordinary product, customer, or order fields without review.

When this data affects the expected EShop result, the project should be reviewed through Custom Service. Tailored Add-ons, Custom Add-ons, and custom migration logic adjustment belong in Custom Service because they change how the migration must interpret or transform data.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

The migrated result should prove that source business meaning survived the move into EShop. Record counts are useful, but they are not enough.

| Proof area                         | What the migrated data should demonstrate                                                                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product meaning                    | Products are sellable, organized, priced correctly, image-ready, and understandable to shoppers.                                                                     |
| Option and attribute meaning       | Shopper choices, specifications, filters, and product information have not been collapsed into the wrong structure.                                                  |
| Category and manufacturer meaning  | Discovery, navigation, brand/manufacturer context, and catalog grouping support the target storefront.                                                               |
| Customer and group meaning         | Customer records, customer groups, addresses, and historical relationships remain useful after migration.                                                            |
| Order history meaning              | Orders remain readable for support, reporting reference, fulfillment questions, discounts, tax, shipping, payment, and status review.                                |
| Checkout and configuration meaning | Checkout fields, tax behavior, shipping behavior, payment behavior, and order statuses are separated into migrated history, target configuration, or service review. |
| Joomla presentation meaning        | Menus, modules, templates, themes, aliases, metadata, and storefront pages are planned around the migrated data.                                                     |
| Custom data meaning                | Custom fields, extension-owned data, external identifiers, and bespoke source relationships are classified correctly.                                                |

A strong Demo Migration for EShop should therefore include products with options, products with attributes, products in multiple categories, manufacturer-linked products, discounted products, downloadable products if relevant, products with reviews, customers in important customer groups, orders with payment and shipping detail, orders with discounts or vouchers, orders with meaningful statuses, and records that depend on custom or multilingual behavior.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EShop data model differences matter because the platform organizes commerce through a Joomla extension environment rather than a generic store-record structure. Products, categories, options, attributes, manufacturers, customers, orders, checkout fields, discounts, vouchers, tax, shipping, payment plugins, modules, templates, multilingual content, and custom Joomla behavior all help determine whether the migrated store remains commercially usable.

A successful migration to EShop should preserve selling meaning, account meaning, historical order meaning, storefront meaning, and configuration boundaries. When source data is clean and the target Joomla implementation is clear, this translation can be planned with confidence. When the source depends on complex options, customer group logic, custom checkout fields, multilingual structures, plugin-owned data, or bespoke Joomla behavior, those areas should be reviewed before Full Migration.

Use Demo Migration results to test whether EShop preserves the meaning of representative products, customers, orders, options, attributes, discounts, checkout fields, taxes, shipping methods, payment references, and Joomla storefront context. If the source store includes Custom Platform data, unsupported extension records, external identifiers, or custom transformation requirements, review the migration path through Live Chat before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do EShop data model differences matter during migration?**

They matter because EShop organizes commerce through Joomla extension structures. Products, options, attributes, categories, manufacturers, customers, orders, checkout fields, plugins, modules, templates, and multilingual behavior may not match the Source Platform one-to-one.

**Are product options and attributes the same in EShop migration planning?**

No. Options usually represent shopper-facing product choices, while attributes usually describe product characteristics. Source platforms may use these terms differently, so each field should be interpreted by what it is supposed to do after migration.

**Can customer groups be migrated to EShop?**

Customer group handling depends on the selected migration path, source structure, and supported behavior. If customer groups control pricing, access, segmentation, or reporting, they should be included in Demo Migration validation and may need mapping review.

**Does order migration include checkout, tax, shipping, and payment meaning?**

Order history should preserve useful checkout, tax, shipping, payment, discount, product, status, and customer context as far as the selected migration path and supported behavior allow. Future checkout, tax, shipping, and payment behavior still depend on EShop configuration and plugins.

**When does EShop data migration require Custom Service?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported extension data, custom checkout fields, bespoke product relationships, external identifiers, multilingual transformation, third-party system references, or custom migration logic adjustment beyond standard service capability.
