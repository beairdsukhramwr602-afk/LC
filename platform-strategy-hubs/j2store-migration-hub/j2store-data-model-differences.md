# J2Store Data Model Differences

A J2Store migration should not be evaluated only by whether products, customers, and orders appear in the target administration area. J2Store belongs to a Joomla extension model, and in the v4 / J2Commerce 4 generation, commercial meaning can be distributed across Joomla articles, J2Store product settings, product types, options, apps, modules, templates, payment plugins, shipping plugins, tax configuration, and checkout behavior.

This makes the data model different from platforms where products, catalog pages, checkout rules, and storefront presentation are contained inside one self-contained commerce stack. In J2Store, a product may also be a Joomla article. A storefront path may depend on Joomla menus. A product display may depend on modules or template overrides. A checkout rule may come from an app or plugin. A migrated record is useful only when that surrounding meaning is preserved, configured, or deliberately excluded from the target result.

When source data becomes J2Store data, the central question is how its commercial meaning survives inside a Joomla-connected store. Product records, Joomla content, product types, options, customer groups, orders, checkout fields, apps, modules, and templates may all carry meaning that is not visible from record counts alone.

### Core Structural Layers in J2Store <a href="#core-structural-layers-in-j2store" id="core-structural-layers-in-j2store"></a>

The most important data-model difference is that J2Store operates inside Joomla rather than replacing Joomla. A merchant migrating to J2Store is not only moving commerce records into a store application. The merchant is moving commercial data into a Joomla-based structure where products, categories, menu behavior, modules, templates, and extension settings work together.

| J2Store structural layer           | What it controls                                                                                                                   | Migration meaning                                                                                                 |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Joomla content layer               | Articles, categories, menus, page routes, metadata, and content relationships.                                                     | Product and storefront meaning may depend on Joomla content structure, not only J2Store product records.          |
| J2Store product layer              | Product type, SKU, price, tax profile, images, manufacturer, vendor, shipping status, stock, options, files, and advanced pricing. | Products must be interpreted by selling behavior, not only by title, description, and price.                      |
| Catalog discovery layer            | Categories, manufacturers, filters, specifications, related products, ordering, and product display logic.                         | A product must remain findable and comparable in the target store.                                                |
| Sales and customer layer           | Customers, addresses, orders, line items, discounts, coupons, vouchers, totals, tax, shipping, payment, and statuses.              | Historical records should remain useful for service, accounting reference, repeat buying, and operational review. |
| Extension and implementation layer | Apps, payment plugins, shipping plugins, modules, email templates, invoice templates, layout overrides, and custom code.           | Some behavior may be configuration or implementation work rather than direct data migration.                      |

The table helps define the layers, but the practical migration decision is more specific: each source field or behavior should be classified by what it means in the future store. Some data belongs in J2Store product settings. Some belongs in Joomla content. Some belongs in configuration. Some belongs to an app or plugin. Some may require Custom Service review if it is custom, unsupported, or outside standard service capability.

### Product and Joomla Article Meaning <a href="#product-and-joomla-article-meaning" id="product-and-joomla-article-meaning"></a>

In J2Store v4, product creation can be tied to Joomla articles: a merchant creates or edits a Joomla article, marks it to be treated as a product, and then selects the product type. That structure is central to J2Store data meaning. A product is not simply an isolated commerce object. It can carry Joomla article title, article content, category placement, metadata, menu placement, and product settings together.

For migration planning, this means product title and description should not be treated as generic fields only. They may become part of a Joomla article that supports both content presentation and commerce behavior. If the source platform separates product data from content pages, the migration plan should determine which information becomes J2Store product content, which information becomes Joomla content outside the product, and which information should be recreated through menus, modules, or template work.

#### Article content and product sellability are connected <a href="#article-content-and-product-sellability-are-connected" id="article-content-and-product-sellability-are-connected"></a>

In J2Store, the article content can support the product page while the product settings define commercial behavior such as price, SKU, tax profile, stock, options, shipping status, images, and downloadable files. If the source store has rich descriptions, long-form buying guides, embedded media, technical specifications, or custom content sections, those elements should be interpreted carefully. A short product export may not contain everything that made the original product page useful.

The migration implication is that a product should remain readable and sellable. A product that has a title and price but loses its content structure, key specifications, image relationships, option meaning, or shipping behavior has not fully translated into J2Store meaning.

#### Category placement may serve two purposes <a href="#category-placement-may-serve-two-purposes" id="category-placement-may-serve-two-purposes"></a>

Category meaning can be especially important because Joomla categories and storefront browsing may both affect where products appear. A product category can support content organization, product list views, menu placement, and shopper discovery. Source categories should therefore be reviewed for both data hierarchy and storefront behavior.

If a source product appears in multiple categories, uses landing pages for discovery, or depends on category-specific product lists, the target plan should clarify whether this becomes J2Store category assignment, Joomla menu structure, product display modules, or separate Joomla content implementation.

### Product Type Meaning <a href="#product-type-meaning" id="product-type-meaning"></a>

J2Store product type selection carries more meaning than a simple source field called “type.” It affects how shoppers select products, how the merchant manages stock, how files are delivered, how options are interpreted, and how order lines should be understood after migration.

#### Simple products <a href="#simple-products" id="simple-products"></a>

A simple product is appropriate when the product has one primary stock identity and does not require variant-level inventory or shipping detail. It can still have product options, such as size or color, but inventory is managed for the primary product rather than for each option combination.

When source products use simple add-on choices without separate SKUs, a simple product may preserve the intended meaning. When source products use option-level stock, option-level pricing, or separate SKUs, a simple product may be too shallow as the target interpretation.

#### Variable products <a href="#variable-products" id="variable-products"></a>

Variable products are used when combinations of options need to become sellable variants. A size-and-color example may generate combinations such as Small-Red, Small-Blue, Medium-Red, and Medium-Blue. Those combinations can carry their own pricing, inventory, and shipping details.

This matters during migration because variant data cannot be validated only by seeing option labels. The target result should preserve the option combination logic and the operational fields attached to each combination where supported by the selected migration path. If the source platform stores variants as independent child records, option rows, attribute combinations, or app-owned data, the translation into J2Store must preserve the commercial meaning of those structures.

#### Configurable products <a href="#configurable-products" id="configurable-products"></a>

Configurable products are useful when option availability depends on another option. For example, a color may be available only for a certain size. This creates a dependency relationship that is different from a flat list of options.

If the source catalog uses conditional option behavior, the migration plan should identify it before treating the product as a normal variable product. A product can look complete after migration while still allowing invalid combinations or hiding valid combinations if this dependency meaning is lost.

#### Advanced variable and flexible variable products <a href="#advanced-variable-and-flexible-variable-products" id="advanced-variable-and-flexible-variable-products"></a>

Advanced variable products support cases where some options behave as variants while other options do not. A customizable T-shirt example may use size and color as variant combinations while using custom text as an additional non-variant option. This is a different data structure from treating every option as a variant.

Flexible variable products add another practical layer: individual variant combinations can be published or unpublished without regenerating all variants. That matters for merchants who manage stock, availability, or seasonal combinations at a more granular level.

The migration implication is that source option data should be classified by business function. Some options define product identity. Some define customer personalization. Some affect price. Some affect stock. Some affect shipping. Treating them all as one generic option field can distort the target product model.

#### Downloadable products <a href="#downloadable-products" id="downloadable-products"></a>

Downloadable products represent digital goods such as e-books, software, audio, video, PDFs, images, or other files. In this model, the product is not only a product record. It also depends on file attachment, download access, order/payment status, download limit, and expiration behavior.

A source digital product should therefore be reviewed for more than name, price, and file URL. The target meaning includes whether the customer can access the file after purchase, whether access expires, how many downloads are allowed, and whether order status rules make the download visible in the customer area. File delivery expectations may need configuration or implementation review rather than ordinary product migration alone.

#### Booking, subscription, bundled, and app-driven product behavior <a href="#booking-subscription-bundled-and-app-driven-product-behavior" id="booking-subscription-bundled-and-app-driven-product-behavior"></a>

The v4 ecosystem includes product and app patterns for bookings, subscriptions, grouped or bundled products, quote behavior, additional fees, points and rewards, donation behavior, product shipping restrictions, and other commercial extensions. These structures should not be flattened into ordinary product records without review.

When a source product behaves like a reservation, recurring membership, bundled offer, quote request, donation, or restricted product, the data model question becomes: which part is product data, which part is app behavior, which part is checkout behavior, and which part requires Custom Service review?

### Options, Attributes, Specifications, and Pricing Meaning <a href="#options-attributes-specifications-and-pricing-meaning" id="options-attributes-specifications-and-pricing-meaning"></a>

Options, attributes, specifications, and advanced pricing often get confused during migration because they can all describe products. In J2Store, they do not necessarily serve the same purpose.

Options usually affect shopper selection or product purchase behavior. Attributes and specifications may help describe or compare products. Advanced pricing may apply discounts or special prices by group, quantity, date range, or business rule. A source field labeled “attribute” may need to become an option if shoppers use it to select a purchasable variation. A source field labeled “option” may be better treated as descriptive content if it does not affect purchase behavior.

#### Option meaning should follow shopper behavior <a href="#option-meaning-should-follow-shopper-behavior" id="option-meaning-should-follow-shopper-behavior"></a>

A useful rule is to ask whether the shopper must choose the value before buying. If yes, the source value likely belongs to option or variant logic. If not, it may belong to product description, specification, filter, label, custom field, or content.

This distinction affects product pages, order lines, inventory, and post-migration customer service. If a customer bought a Blue / Large shirt, that selection should remain visible and meaningful in the order. If “cotton” was only a material attribute used for filtering or description, it should not be forced into variant behavior unless it actually controls buying.

#### Advanced pricing has customer and order consequences <a href="#advanced-pricing-has-customer-and-order-consequences" id="advanced-pricing-has-customer-and-order-consequences"></a>

Special pricing, group pricing, date-range pricing, quantity pricing, and other advanced pricing behavior should be interpreted as business rules, not just alternate price fields. The target result should clarify which prices are migrated as record data, which prices must be configured, and which price behavior depends on J2Store capability, Add-on review, or Custom Service review.

This is especially important when source pricing depends on customer group, membership status, B2B account type, coupon stacking, bulk discounts, product bundles, or third-party pricing integrations. The migration plan should preserve the meaning of the rule, not merely choose one price and discard the context.

### Catalog Discovery Meaning <a href="#catalog-discovery-meaning" id="catalog-discovery-meaning"></a>

Catalog discovery in J2Store can involve more than product category assignment. Source discovery logic may translate into Joomla categories, product list views, filters, specifications, manufacturers, related products, product ordering, shortcodes, product display modules, category modules, and search modules.

#### Categories and menus work together <a href="#categories-and-menus-work-together" id="categories-and-menus-work-together"></a>

A source category tree may need to become both product organization and storefront navigation. In Joomla, menu items can shape how category and product pages are reached. The same category data may not produce the same customer journey unless the menu and module structure are also planned.

This matters for SEO and usability. A product that sits in the right category but has no useful menu path, module placement, or internal link structure may be hard for shoppers to find. Article 7 will define validation samples for this; Article 3 establishes the meaning translation that must be preserved.

#### Manufacturers, filters, specifications, and related products carry discovery context <a href="#manufacturers-filters-specifications-and-related-products-carry-discovery-context" id="manufacturers-filters-specifications-and-related-products-carry-discovery-context"></a>

Manufacturers, filters, specifications, and related products can help shoppers compare and navigate products. These should not be dismissed as secondary fields. For many catalogs, they are the difference between a usable storefront and a product archive.

If the source store uses brand pages, manufacturer filters, technical specifications, product comparison, cross-selling, or related product blocks, the migration plan should identify whether J2Store has a clear target structure for each. Some relationships may map cleanly; others may require module, template, app, or custom handling.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

Customer migration should preserve identity, address, and account context in a way that remains useful inside the J2Store environment. Customer data may include names, email addresses, billing addresses, shipping addresses, account status, customer group relationships, order history, and other profile-related fields.

The important point is relationship preservation. A customer record is most useful when it remains connected to the right orders, addresses, discounts, account behavior, and group-based rules. If a source store uses guest checkout, account merging, B2B customer groups, membership rules, or external customer identifiers, those details should be reviewed before assuming customer records alone will preserve the full meaning.

#### Customer groups can affect more than segmentation <a href="#customer-groups-can-affect-more-than-segmentation" id="customer-groups-can-affect-more-than-segmentation"></a>

Customer groups may control pricing, discounts, access, tax behavior, or business workflows. If the source platform uses customer groups for B2B pricing, wholesale access, tax exemption, membership levels, or account-specific rules, those groups should not be treated as labels only.

A migrated customer group relationship should support the intended operational meaning in the target store. If that meaning depends on custom extensions, apps, or external systems, it may require deeper review.

### Order and Sales History Meaning <a href="#order-and-sales-history-meaning" id="order-and-sales-history-meaning"></a>

Order history is one of the easiest areas to underestimate. A migrated order should be readable for customer service, internal reference, accounting review, fulfillment questions, warranty support, and repeat buying context. This requires more than order number, date, and total.

J2Store order meaning may involve ordered products, product type context, selected options, line-item prices, discounts, coupons, vouchers, taxes, shipping charges, payment method, shipping method, customer addresses, order status, comments, invoice context, email history, and downloadable access status.

#### Product options must remain visible in order lines <a href="#product-options-must-remain-visible-in-order-lines" id="product-options-must-remain-visible-in-order-lines"></a>

For stores with configurable, variable, advanced variable, flexible variable, or customizable products, order lines should preserve what the customer actually selected. A product title without selected option meaning may be insufficient for customer service or fulfillment.

If the source platform stores selected options in a custom table, app-owned field, serialized value, or third-party export, that structure should be reviewed before migration. The target order should remain understandable to staff after the migration, especially for orders involving size, color, customization, downloadable access, booking dates, subscription periods, or product bundles.

#### Statuses and post-order behavior need interpretation <a href="#statuses-and-post-order-behavior-need-interpretation" id="statuses-and-post-order-behavior-need-interpretation"></a>

Order status meaning may differ across platforms. A source status such as paid, completed, shipped, refunded, cancelled, pending, failed, fulfilled, or partially fulfilled may not have a one-to-one operational equivalent in J2Store. Payment status and fulfillment status may also be stored differently.

The migration should preserve the practical meaning needed after launch. If old statuses were used only for internal notes, they may need a different treatment than statuses that control download access, customer notifications, fulfillment workflow, or accounting reconciliation.

### Checkout, Tax, Shipping, and Payment Meaning <a href="#checkout-tax-shipping-and-payment-meaning" id="checkout-tax-shipping-and-payment-meaning"></a>

Checkout-related data often combines records, settings, plugins, apps, and business rules. It is rarely just data movement. A source shipping method, for example, may represent a carrier integration, a table-rate rule, a postal-code restriction, a free-shipping coupon, a product category restriction, or local pickup behavior. A source payment method may represent a gateway, stored transaction reference, payment status, or manual payment workflow.

In J2Store, payment and shipping behavior depends heavily on installed and configured plugins. Tax behavior depends on tax profiles, regions, rules, and product tax settings. Checkout behavior may also depend on apps such as file upload, additional fee, checkout redirect, open-hours restriction, request quote, or custom fields.

#### Separate migrated data from configured behavior <a href="#separate-migrated-data-from-configured-behavior" id="separate-migrated-data-from-configured-behavior"></a>

A strong migration plan distinguishes between:

1. commerce records that should migrate;
2. target settings that must be configured in J2Store;
3. plugin or app behavior that must be installed, enabled, or reviewed;
4. custom behavior that may require Custom Service.

This distinction prevents a common misunderstanding. A migrated order may show a shipping method name, but that does not automatically recreate the shipping calculation rules for future orders. A product may show tax context, but that does not automatically recreate the full tax configuration. A payment reference may remain useful historically, but future payment processing depends on target gateway configuration.

### Apps, Modules, Templates, and Custom Fields <a href="#apps-modules-templates-and-custom-fields" id="apps-modules-templates-and-custom-fields"></a>

J2Store v4 / J2Commerce 4 stores may depend on apps, modules, templates, layout overrides, and custom fields. These layers can carry business meaning that is not visible in the basic product, customer, or order list.

Apps may control discounts, analytics, checkout redirection, donations, group products, bundled products, file uploads, quantity dropdown behavior, availability notifications, additional fees, request-quote workflows, GDPR behavior, rewards, tax integrations, or other store logic. Modules may control product display, category lists, search, detailed cart behavior, or storefront navigation. Templates and overrides may control how product and checkout data are displayed.

Custom fields can be especially important because they may represent merchant-specific product details, checkout requirements, account fields, order notes, or integration identifiers. If these fields are important to the target result, they should be classified before migration as standard data, mapped data, configured behavior, implementation work, or Custom Service review.

### Version Continuity and J2Commerce 6 Context <a href="#version-continuity-and-j2commerce-6-context" id="version-continuity-and-j2commerce-6-context"></a>

This hub focuses on J2Store v4 / J2Commerce 4. J2Commerce 6 should not be used as the data model for this article. It has a separate native Joomla 6 architecture, different plugin/event assumptions, and a different target identity.

However, version continuity still matters because some merchants may be maintaining v4 today while thinking about future modernization. In that situation, the migration plan should not blend the two targets. Data should first be interpreted against the actual selected Target Platform. If the selected Target Platform is J2Store v4 / J2Commerce 4, validate against that environment. If the selected Target Platform is J2Commerce 6, use the separate J2Commerce 6 hub and its own data model assumptions.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

A successful J2Store data translation should prove that the target records are commercially meaningful inside the Joomla store, not merely present in the database.

| Data area                    | What the migrated result must prove                                                                                                        |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Products                     | Products are readable, sellable, correctly typed, and connected to the correct Joomla/content structure.                                   |
| Product options and variants | Shopper selections, option combinations, prices, images, stock, shipping behavior, and order-line meaning remain understandable.           |
| Downloadable products        | File access, download limits, expiry behavior, and order-status dependency are correctly represented or clearly configured.                |
| Categories and discovery     | Categories, manufacturers, filters, specifications, ordering, and related products support browsing and comparison.                        |
| Customers and groups         | Customer identity, addresses, order relationships, and group-based meaning remain useful.                                                  |
| Orders                       | Line items, selected options, totals, tax, shipping, payment method, statuses, comments, invoices, and historical context remain readable. |
| Checkout behavior            | Future checkout expectations are separated into migrated data, J2Store configuration, app/plugin setup, and custom review.                 |
| Joomla presentation          | Menus, modules, templates, content relationships, and overrides support the migrated data rather than hiding or distorting it.             |
| Custom and app-owned data    | Important non-standard data has a defined target treatment through mapping, configuration, Add-on review, or Custom Service.               |

This proof requirement is developed further in the Validation Priorities article. For the data model article, the key principle is simple: every migrated field should be judged by the business meaning it carries in J2Store.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Store data migration is a translation into a Joomla-connected commerce model. Products may be Joomla articles. Product behavior may depend on product type, options, variants, downloads, apps, or advanced pricing. Catalog discovery may depend on categories, manufacturers, filters, modules, and menus. Customer and order history may depend on group relationships, selected options, checkout fields, tax, shipping, payment, and status meaning. Storefront continuity may depend on Joomla templates, layout overrides, and content structure.

The strongest migration plans avoid treating J2Store as a generic target database. They identify what each source record means, where that meaning belongs in J2Store, and which behaviors require configuration, Add-on review, or Custom Service before the migration result can be trusted.

Use Demo Migration results to confirm that J2Store preserves the meaning of your most important product, customer, order, checkout, and Joomla-content structures. If your source store includes complex product types, custom fields, app-owned behavior, unusual checkout logic, downloadable access rules, subscriptions, bookings, third-party identifiers, or Custom Platform data, review the selected migration path through Live Chat before relying on standard data assumptions.

### FAQs <a href="#faqs" id="faqs"></a>

**Why is J2Store data migration different from a standard product import?**

J2Store works inside Joomla, and product meaning can depend on Joomla articles, product types, options, categories, menus, modules, templates, apps, and configuration. A product import may create records, but migration quality depends on whether those records remain sellable, discoverable, and useful inside the J2Store implementation.

**Do J2Store products always behave like ordinary products from other platforms?**

No. J2Store supports multiple product-type patterns, including simple, variable, configurable, advanced variable, flexible variable, downloadable, booking, subscription, and app-driven structures. The correct target meaning depends on how the source product behaves, not only on its name or SKU.

**Are product options and product attributes the same thing in a J2Store migration?**

Not necessarily. Options usually affect shopper selection or purchasable product behavior, while attributes, specifications, filters, or descriptive fields may support comparison and discovery. The migration plan should classify each source value by what it does in the buying journey.

**Can downloadable products be migrated like physical products?**

Downloadable products need additional review because their meaning includes file attachment, download availability, order/payment status, download limits, and expiration behavior. A digital product that migrates without usable download access may not be commercially complete.

**What happens to app-owned or custom source data during migration?**

App-owned and custom data should be reviewed before execution. Some data may fit standard migration capability or Add-on review. Unsupported app data, bespoke relationships, third-party identifiers, Custom Platform data, or custom migration logic adjustment should be reviewed through Custom Service.
