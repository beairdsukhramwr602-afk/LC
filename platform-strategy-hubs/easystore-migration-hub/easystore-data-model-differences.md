# EasyStore Data Model Differences

EasyStore by JoomShaper changes data interpretation because the store operates inside Joomla. A Source Platform may keep catalog data, checkout settings, storefront pages, customer records, order history, theme behavior, and third-party functionality inside one commerce environment. In EasyStore, the migrated result is shaped by EasyStore commerce records and by the Joomla site structure that displays and connects those records.

That distinction matters during migration. A product can exist in the target store but still lose useful selling meaning if variants, categories, images, inventory, discounts, tax context, shipping meaning, or product-page presentation are not interpreted correctly. A customer can migrate as a contact but still fail to support order review. An order can preserve totals but lose useful operational context. A storefront path can appear valid but still require Joomla menus, templates, modules, redirects, or SP Page Builder layouts to make the customer journey complete.

The data model question is therefore not only “which records can move?” The stronger question is how those records should behave after they arrive in EasyStore and Joomla.

### EasyStore Data Lives Across Commerce and Joomla Layers <a href="#easystore-data-lives-across-commerce-and-joomla-layers" id="easystore-data-lives-across-commerce-and-joomla-layers"></a>

EasyStore migration should separate commerce records from Joomla site structure. The two layers work together, but they do not have the same migration meaning. EasyStore owns the store-management layer. Joomla owns much of the site architecture, content context, navigation, templates, permissions, and extension environment.

| Data layer                 | What it may include                                                                                                                                   | Migration implication                                                                                        |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| EasyStore commerce records | Products, variants, categories, tags, images, inventory, customers, orders, coupons, reviews, refunds, tax context, shipping context, payment context | These are the primary store records to map, migrate, and validate for commercial usefulness.                 |
| EasyStore configuration    | Checkout settings, payment integrations, shipping methods, tax setup, notifications, analytics, currency, store preferences                           | Some values may inform historical records, but live behavior usually requires target-side setup and testing. |
| Joomla site structure      | Menus, aliases, internal links, CMS pages, Blog Posts, modules, templates, users, groups, access levels, multilingual structure                       | These elements shape how shoppers reach store records and how administrators control the site.               |
| Presentation layer         | SP Page Builder layouts, landing pages, product sections, category blocks, template overrides, custom modules                                         | These may need implementation or manual rebuild rather than ordinary record migration.                       |
| Extension and custom layer | Third-party extensions, custom fields, external IDs, ERP or fulfillment references, app-created logic, bespoke source behavior                        | These require scope review and may need Add-ons or Custom Service depending on supportability.               |

The practical result is that EasyStore data should not be treated as a flat export/import exercise. Store records, Joomla structure, and presentation work must be interpreted separately so the merchant can tell what was migrated, what must be configured, and what must be rebuilt or reviewed outside standard supported data.

### Product Records Need Selling Meaning, Not Only Presence <a href="#product-records-need-selling-meaning-not-only-presence" id="product-records-need-selling-meaning-not-only-presence"></a>

Product migration is visible, but visibility is not the same as usable selling structure. A migrated product should preserve enough meaning for shoppers to understand it, choose the right version, trust the price and images, and complete purchase. It should also remain manageable for the merchant after launch.

EasyStore product meaning can involve product names, descriptions, SKUs, prices, sale offers, images, categories, tags, variants, inventory, taxability, shipping requirements, product status, reviews, coupons, metadata, and custom fields. Source platforms may store those details in different ways. Some systems use product options. Some use child products. Some use attributes, modifiers, bundles, collections, or app-created merchandising logic. The target result should translate commercial meaning rather than copy source labels mechanically.

| Source product pattern                 | EasyStore migration question                                                                    | Validation focus                                                             |
| -------------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Simple product                         | Does the product carry name, price, image, category, status, and core selling fields correctly? | Product can be viewed, managed, and sold without ambiguity.                  |
| Variant-heavy product                  | Do size, color, material, package, or other choices become usable target product choices?       | Variants remain understandable and order lines preserve the selected option. |
| Image-heavy product                    | Do main images and gallery images attach to the right product or variation context?             | Product pages display accurate visual information.                           |
| Discounted or coupon-sensitive product | Does promotional meaning belong to migrated records, target configuration, or manual setup?     | Sale context is not treated as live promotional setup.                       |
| Custom-field product                   | Is the field supported, mappable, custom, extension-owned, or external-system dependent?        | Add-ons or Custom Service needs are identified before launch.                |

Product data should be reviewed through representative samples. A catalog with only simple products needs a different mapping burden from a catalog with variant combinations, option-specific stock, custom product attributes, embedded media, bundles, or source-specific merchandising rules.

### Variants and Options Require Structural Translation <a href="#variants-and-options-require-structural-translation" id="variants-and-options-require-structural-translation"></a>

Variants are not only product labels. They can affect price, SKU, stock, image selection, shopper choice, fulfillment, and order history. A Source Platform may store variants as child products, options, attributes, configurable combinations, modifier-like choices, or custom extension records. EasyStore has its own way of managing product variations, so the source representation needs interpretation before it can become target behavior.

A weak migration review asks whether variants migrated. A stronger review asks whether the same commercial choice still exists in the target store. If shoppers selected size, color, material, quantity pack, digital/physical format, or other options in the old store, those choices need to remain clear in EasyStore. If the source store used option-level inventory, option-specific pricing, inconsistent option names, duplicated variant values, or app-created product logic, those differences should be handled before approval.

| Variant issue                              | Why it matters in EasyStore                                                             | Likely handling path                                           |
| ------------------------------------------ | --------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Different option names for the same choice | Shoppers and administrators may see duplicated or confusing choices.                    | Source cleanup, mapping review, or bounded data configuration. |
| Option-specific prices                     | Order totals and product display can become misleading if choices lose pricing meaning. | Data mapping and validation samples.                           |
| Option-level inventory                     | Stock may not support the actual product choice after migration.                        | Inventory validation and possible configuration review.        |
| Custom option logic                        | Source behavior may not have a direct target equivalent.                                | Custom Service review if unsupported or bespoke.               |
| App-created variants                       | Data may sit outside normal supported records.                                          | Source ownership review before migration.                      |

This distinction is especially important for EasyStore because the storefront presentation can also depend on Joomla layouts, templates, or SP Page Builder sections. A variant may be structurally migrated, but the product page must still display choices in a way shoppers can understand.

### Categories, Tags, and Joomla Navigation Are Related but Different <a href="#categories-tags-and-joomla-navigation-are-related-but-different" id="categories-tags-and-joomla-navigation-are-related-but-different"></a>

EasyStore can organize products through commerce structures such as categories and tags. Joomla can also organize the customer journey through menus, aliases, modules, landing pages, internal links, and content pages. Those structures may work together, but they should not be collapsed into one category migration assumption.

A source store may use categories, collections, tags, brands, filters, menu groups, SEO landing pages, or page-builder blocks to guide shoppers. EasyStore migration should determine which of those structures should become EasyStore catalog organization and which belong to Joomla implementation.

| Discovery element            | Migration interpretation                                                                              |
| ---------------------------- | ----------------------------------------------------------------------------------------------------- |
| Product category             | Usually belongs to EasyStore catalog structure and should be validated with products.                 |
| Product tag                  | May support filtering, grouping, or merchandising depending on target use.                            |
| Source collection            | Needs interpretation because it may behave like a category, tag, landing page, or merchandising rule. |
| Joomla menu item             | Controls site navigation and route exposure rather than product data itself.                          |
| Landing page or content page | May need CMS page, Blog Post, SP Page Builder, or manual layout work.                                 |
| SEO-heavy source path        | Requires redirect and URL planning, not only product/category migration.                              |

The risk is assuming that category migration automatically recreates the storefront. It does not. Product organization can be correct while the Joomla menu, landing page, internal link, or redirect plan still needs work.

### Customer Records Can Involve EasyStore and Joomla User Context <a href="#customer-records-can-involve-easystore-and-joomla-user-context" id="customer-records-can-involve-easystore-and-joomla-user-context"></a>

Customer data in EasyStore should support recognition, order lookup, support continuity, and administrative review. It should not be judged only by whether names and emails appear. Because EasyStore operates inside Joomla, customer meaning may also intersect with Joomla users, user groups, permissions, access levels, and account behavior.

Source stores may contain registered customers, guest buyers, repeat buyers, customers with multiple addresses, customers with abandoned accounts, customers tied to subscriptions or memberships, and customers created by external systems. EasyStore migration should preserve useful customer context where supported while separating commerce records from Joomla account configuration.

| Customer data area            | Meaning to preserve                                                                        | Risk if misread                                             |
| ----------------------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| Contact details               | Name, email, phone, address, and basic identity fields.                                    | Customers migrate as disconnected contacts.                 |
| Order relationship            | Historical orders remain connected to the right customer where supported.                  | Support teams cannot review buyer history.                  |
| Joomla user context           | Login, user group, permission, or access-level assumptions may require target-side review. | Account behavior is treated as ordinary customer migration. |
| Membership or role-based data | Commercial identity may depend on external logic or Joomla ACL.                            | Custom behavior is hidden inside customer fields.           |
| Duplicate customers           | Emails, names, or phone numbers may not identify the same person cleanly.                  | Target records become confusing after launch.               |

Customer migration should be validated with real examples. Guest buyers, repeat buyers, and customers with multiple historical orders often reveal whether the target result is useful beyond field presence.

### Orders Preserve History, Not Live Checkout Setup <a href="#orders-preserve-history-not-live-checkout-setup" id="orders-preserve-history-not-live-checkout-setup"></a>

Historical orders should remain readable and useful after migration. They can support customer service, internal review, financial context, and operational history. But migrated orders do not configure live checkout, payment integrations, tax rules, shipping rates, refund workflows, or notifications in EasyStore.

Order meaning may include order number, customer, line items, products, variants, quantities, prices, discounts, coupons, tax, shipping, payment references, refund context, fulfillment status, notes, and timestamps. Some of this information is historical. Some of it may resemble live settings but should not be treated as configuration.

| Order component          | Historical migration meaning                     | Separate target-side concern                            |
| ------------------------ | ------------------------------------------------ | ------------------------------------------------------- |
| Line items               | Shows what was purchased and in what quantity.   | Product availability and current product configuration. |
| Discounts and coupons    | Preserves promotional context for history.       | Active coupon setup and future promotion rules.         |
| Tax and shipping amounts | Helps explain past totals.                       | Current tax and shipping configuration.                 |
| Payment references       | Supports historical review.                      | Live payment gateway setup and testing.                 |
| Refunds                  | Explains customer service and financial history. | Current refund workflow configuration.                  |
| Order status             | Supports order interpretation.                   | New target order lifecycle and notifications.           |

A strong migration plan validates ordinary orders and exception orders. Refunded, discounted, high-value, multi-product, tax-sensitive, shipping-sensitive, and customer-linked orders should be included in Demo Migration review.

### Store Settings and Operational Behavior Should Not Be Treated as Records <a href="#store-settings-and-operational-behavior-should-not-be-treated-as-records" id="store-settings-and-operational-behavior-should-not-be-treated-as-records"></a>

EasyStore includes store-management areas such as inventory, orders, customer profiles, refunds, analytics, tax, shipping, checkout, coupons, reviews, and payment integrations. Some records from those areas may be migrated. Operational behavior, however, often needs configuration after data migration.

This distinction prevents a common expectation problem. A merchant may see migrated orders with payment labels and assume payment processing is ready. A merchant may see historical tax amounts and assume current tax rules are configured. A merchant may see shipping values and assume shipping methods are live. These are different outcomes.

| Operational area | Data that may migrate                                           | Behavior that needs configuration or testing                     |
| ---------------- | --------------------------------------------------------------- | ---------------------------------------------------------------- |
| Inventory        | Product stock values where supported.                           | Ongoing stock-management rules and adjustment workflow.          |
| Tax              | Historical tax amounts or tax-related product context.          | Active tax rates and regional tax configuration.                 |
| Shipping         | Historical shipping values or shipping-related product context. | Shipping methods, regions, rates, and live checkout behavior.    |
| Payments         | Historical payment references where supported.                  | Stripe, PayPal, Paddle, or other payment setup and live testing. |
| Reviews          | Review records where supported and scoped.                      | Display rules, moderation, or unsupported source review data.    |
| Analytics        | Historical references may inform reporting context.             | New analytics setup and target reports.                          |

This does not reduce the value of migration. It clarifies ownership so the target store can be launched with realistic expectations.

### SP Page Builder and Presentation Data Need Separate Interpretation <a href="#sp-page-builder-and-presentation-data-need-separate-interpretation" id="sp-page-builder-and-presentation-data-need-separate-interpretation"></a>

JoomShaper positions EasyStore alongside SP Page Builder, and EasyStore can be part of a visually managed Joomla storefront. That creates an important migration distinction: product data is not the same as page design. A product can migrate, but page sections, product-listing layouts, landing pages, custom blocks, and design-specific presentation may still need Joomla-side implementation.

Source platforms often store page design in themes, builders, CMS blocks, widgets, shortcodes, app sections, or custom templates. Some of that content may have no direct EasyStore record equivalent. When presentation is important, the migration plan should classify each item as commerce data, CMS content, layout work, template work, or unsupported/custom behavior.

| Presentation element     | Best interpretation                                                                           |
| ------------------------ | --------------------------------------------------------------------------------------------- |
| Product description      | Usually product data, but embedded layout code may require cleanup.                           |
| Product gallery          | Product media relationship that should be validated in the target display.                    |
| Store landing page       | Joomla content or SP Page Builder implementation, not ordinary product migration.             |
| Product-listing design   | Template or page-builder presentation work.                                                   |
| Custom callout blocks    | CMS/page-builder/manual rebuild or Custom Service review if source-owned data must transform. |
| Embedded scripts/widgets | Separate implementation or custom review.                                                     |

This separation helps merchants preserve commerce data without expecting migration to reproduce every visual or layout behavior from the Source Platform.

### Extension-Owned and Custom Data Require Scope Discipline <a href="#extension-owned-and-custom-data-require-scope-discipline" id="extension-owned-and-custom-data-require-scope-discipline"></a>

EasyStore may be one part of a larger Joomla site. The source store may also depend on third-party extensions, app-created data, external IDs, custom fields, connector records, ERP references, fulfillment logic, marketplace data, or custom code. These records should be identified before they are treated as standard EasyStore migration scope.

Add-ons and Custom Service should be separated clearly. Add-ons can help when supported data requires filtering, mapping, or bounded configuration. Custom Service should be considered when data is unsupported, extension-owned, custom, bespoke, connected to external systems, or requires migration logic adjustment beyond supported behavior.

| Requirement                                               | Better classification                                                         |
| --------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Supported product field needs another target field        | Add-on or mapping review.                                                     |
| Only selected supported records should migrate            | Add-on or filtering review.                                                   |
| Custom source field must remain available after migration | Custom Service review if unsupported by the standard path.                    |
| External ERP or fulfillment ID must remain connected      | Custom Service review.                                                        |
| Third-party extension creates commerce data               | Source ownership review and likely Custom Service evaluation.                 |
| Joomla page-builder design must be rebuilt                | Joomla implementation task unless structured data transformation is required. |

The safest interpretation is to ask what system owns the data and what the target store must do with it. If the answer depends on custom logic, external identifiers, or unsupported records, the expectation should not be hidden inside ordinary product, customer, or order migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EasyStore by JoomShaper migration requires more than matching commerce entities by name. Products, variants, categories, tags, customers, orders, coupons, reviews, refunds, inventory, tax, shipping, payments, Joomla users, menus, pages, templates, modules, SP Page Builder layouts, and custom extension behavior all carry different meanings.

A reliable migration plan separates EasyStore commerce records from Joomla site structure, target configuration, presentation implementation, and custom or extension-owned data. That separation helps merchants preserve the right information, avoid unrealistic launch assumptions, and validate whether the target store is usable for selling, support, administration, and future site management.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why does EasyStore data need Joomla context during migration?**

EasyStore operates inside Joomla, so store data can depend on Joomla menus, pages, templates, modules, users, access rules, and presentation choices. Product, customer, and order records should be reviewed together with the site structure that will expose and support them.

**Are EasyStore categories the same as Joomla menus?**

No. EasyStore categories organize products, while Joomla menus shape navigation and routes. They can work together, but category migration does not automatically rebuild the customer journey.

**Do migrated orders configure EasyStore checkout?**

No. Migrated orders preserve historical context. Live checkout, payment integrations, tax rules, shipping methods, notifications, and refund behavior must be configured and tested in the target environment.

**Can SP Page Builder layouts be treated as product data?**

No. SP Page Builder layouts and store presentation are implementation or content-structure concerns. Product records may support those layouts, but the layouts themselves usually require Joomla-side planning or rebuilding.

**When does EasyStore data require Custom Service review?**

Custom Service should be reviewed when the source includes unsupported extension data, custom fields, external identifiers, app-created commerce logic, bespoke transformations, Custom Platform handling, or custom migration logic adjustment beyond supported behavior.
