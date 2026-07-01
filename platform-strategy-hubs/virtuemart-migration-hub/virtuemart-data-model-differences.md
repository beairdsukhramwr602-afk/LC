# VirtueMart Data Model Differences

VirtueMart data model planning starts with a practical distinction: VirtueMart stores commerce data inside a Joomla environment. Product records, shopper groups, custom fields, calculation rules, payment methods, shipment methods, orders, invoices, currencies, and manufacturer relationships belong to the VirtueMart commerce layer, while menus, routes, modules, templates, language structure, access rules, plugins, and page output still depend on Joomla.

This separation makes VirtueMart flexible, but it also means source data rarely translates as a flat record-for-record transfer. A product option from one system may need to become a VirtueMart custom field, a child product relationship, or another catalog structure. A customer group may need to become a shopper group with pricing and visibility consequences. A tax rule may not be only a saved value; it may be part of VirtueMart calculation logic. A product URL may depend on Joomla menu structure as much as the product alias.

A strong VirtueMart migration plan therefore asks what each record means in commercial use. The goal is not only to place products, customers, and orders into VirtueMart. The goal is to preserve catalog behavior, shopper segmentation, pricing meaning, order evidence, checkout context, and storefront continuity in a way the target Joomla store can operate and validate.

### What Changes When Data Moves Into VirtueMart <a href="#what-changes-when-data-moves-into-virtuemart" id="what-changes-when-data-moves-into-virtuemart"></a>

VirtueMart uses a Joomla-connected model rather than a fully isolated hosted-store model. The same migration scope may contain commerce records, Joomla records, plugin records, template behavior, and custom implementation details. That creates more planning responsibility, but it also gives merchants control over how the target store is organized.

| Source-store assumption                          | VirtueMart reality                                                                                                                | Migration planning impact                                                            |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Product data is the main catalog scope.          | Products may depend on categories, manufacturers, media, custom fields, child products, stock, prices, taxes, and shopper groups. | Catalog samples should include real selling relationships, not only simple products. |
| Variants have one universal target structure.    | VirtueMart may use child products, custom fields, or configured product relationships depending on the store model.               | Variant mapping must be decided before validation is meaningful.                     |
| Customer groups are labels.                      | Shopper groups can affect price, visibility, taxes, payment, shipment, and access behavior.                                       | Shopper group meaning should be documented before Demo Migration.                    |
| Tax and discount records migrate as static data. | VirtueMart uses calculation rules and configuration that may depend on context.                                                   | Historical totals and live checkout behavior should be reviewed separately.          |
| Storefront URLs come from products alone.        | Joomla menus, aliases, SEF routing, modules, templates, and language paths shape storefront output.                               | SEO review must include Joomla structure, not only product slugs.                    |

### Joomla Data vs VirtueMart Commerce Data <a href="#joomla-data-vs-virtuemart-commerce-data" id="joomla-data-vs-virtuemart-commerce-data"></a>

Joomla and VirtueMart divide responsibility. Joomla provides the CMS framework: menus, modules, templates, language associations, users, access levels, plugins, routing, metadata, and page assembly. VirtueMart provides the commerce layer: products, categories, manufacturers, shopper data, shopper groups, orders, invoices, prices, taxes, payment methods, shipment methods, currencies, and store configuration.

The distinction matters because a migrated commerce record can be technically present but commercially incomplete. A product can exist in VirtueMart while its route, module placement, template output, or language association is not ready. A shopper can exist while group-based prices or access behavior are wrong. An order can appear in history while payment or shipment context is too thin for customer service review.

| Data area                     | Primary owner in target              | What must be checked                                                                                     |
| ----------------------------- | ------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| Menus and routes              | Joomla                               | Product and category access paths, aliases, SEF URLs, language paths, and redirects.                     |
| Product records               | VirtueMart                           | SKU, title, description, category, manufacturer, media, price, stock, dimensions, tax, and availability. |
| Variant logic                 | VirtueMart configuration             | Child products, custom fields, selectable options, stock behavior, and price differences.                |
| Users and shoppers            | Joomla and VirtueMart                | Joomla user identity, shopper record, shopper group, billing/shipping details, and login continuity.     |
| Storefront output             | Joomla and VirtueMart                | Templates, overrides, modules, filters, search, breadcrumbs, metadata, and product page layout.          |
| Payment and shipment behavior | VirtueMart plugins and configuration | Available methods, restrictions, fees, order statuses, historical labels, and checkout testing.          |

A migration plan should not hide this ownership split. It should use the split to decide what belongs to data migration, what belongs to target configuration, what belongs to Add-ons, and what may require Custom Service.

### Product and Catalog Structure Differences <a href="#product-and-catalog-structure-differences" id="product-and-catalog-structure-differences"></a>

VirtueMart catalog data is relationship-heavy. Products may connect to categories, manufacturers, media, shopper groups, prices, taxes, custom fields, child products, related products, downloads, dimensions, inventory, reviews, and language-specific content. A source platform that stores those relationships differently needs mapping decisions before the data can be judged.

The most common mistake is treating product rows as the complete product model. In VirtueMart, product meaning often comes from surrounding records. A configurable product may depend on child products. A product option may depend on custom fields. A price may depend on shopper group or calculation rule. A visible product page may depend on Joomla route and module context.

| Catalog element      | VirtueMart planning question                                                         | Why it affects migration quality                                         |
| -------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Categories           | Will source categories map to VirtueMart categories and Joomla navigation paths?     | Category structure affects browsing, product URLs, breadcrumbs, and SEO. |
| Manufacturers        | Are manufacturers required for product filtering, brand pages, or data completeness? | Manufacturer data may be more than a display label.                      |
| Product media        | Which images, downloadable files, thumbnails, and alt text must remain associated?   | Media loss weakens storefront trust and validation accuracy.             |
| Related products     | Are cross-sell, up-sell, accessory, or replacement relationships present?            | Product relationships affect merchandising and support.                  |
| Stock and dimensions | Do stock, weight, size, and package details influence selling or shipment rules?     | Commercial behavior can change if these values are incomplete.           |

A representative Demo Migration should include simple products, category-heavy products, manufacturer-based products, products with multiple media assets, stock-sensitive products, and items that affect shipping or tax behavior.

### Custom Fields, Child Products, and Variant Meaning <a href="#custom-fields-child-products-and-variant-meaning" id="custom-fields-child-products-and-variant-meaning"></a>

VirtueMart custom fields are powerful, but they can create migration ambiguity. Source platforms may describe product choices as variants, options, modifiers, attributes, personalization fields, bundle selections, add-ons, downloadable choices, or price modifiers. VirtueMart may represent some of these through child products and others through custom fields or additional configuration.

That means the migration plan should avoid assuming that every source variant becomes the same target object. The correct structure depends on what the choice does: whether it changes SKU, price, stock, image, weight, tax, availability, or order-line meaning.

| Source behavior                           | Possible VirtueMart interpretation                     | Validation focus                                         |
| ----------------------------------------- | ------------------------------------------------------ | -------------------------------------------------------- |
| Color or size changes SKU and stock.      | Child products or structured selectable relationships. | Confirm SKU, stock, price, image, and order-line output. |
| Option changes price but not stock.       | Custom field or configured product option.             | Confirm price adjustment and cart calculation.           |
| Personalization text is entered by buyer. | Custom field or custom implementation.                 | Confirm checkout capture and order history visibility.   |
| Bundle or kit behavior combines products. | Extension-specific or custom logic.                    | Confirm whether Standard Service is sufficient.          |
| Download choice controls file access.     | Downloadable product or custom field relationship.     | Confirm access and post-order handling.                  |

This area often determines whether the migration can stay standard, whether Add-ons are enough, or whether Custom Service is needed. The decision should be made before Full Migration, because variant structure affects product validation, order interpretation, and customer support after launch.

### Shopper Groups, Prices, and Calculation Rules <a href="#shopper-groups-prices-and-calculation-rules" id="shopper-groups-prices-and-calculation-rules"></a>

VirtueMart uses shopper groups and calculation rules in ways that can be central to commercial behavior. Shopper groups may control prices, discounts, visibility, taxes, payment availability, shipment availability, or buyer segmentation. Calculation rules may affect tax, discounts, fees, category-based rules, product-based rules, country or state rules, and group-specific outcomes.

A source system may not have a direct equivalent. Customer groups, price lists, wholesale roles, tax-exempt customers, B2B accounts, discounts, and regional fees may need to be translated into VirtueMart structures or rebuilt through configuration.

| Business rule         | VirtueMart-sensitive data                             | What should be preserved or rebuilt                                   |
| --------------------- | ----------------------------------------------------- | --------------------------------------------------------------------- |
| Wholesale pricing     | Shopper groups and prices                             | Group assignment, price visibility, tax behavior, and order examples. |
| Tax exemptions        | Shopper groups, tax rules, country/state data         | Eligibility logic and historical order evidence.                      |
| Promotional discounts | Calculation rules, coupons, date ranges               | Active rules, historical discount labels, and checkout totals.        |
| Regional fees         | Shipment methods, tax rules, country/state conditions | Method availability and fee calculation.                              |
| Multicurrency selling | Currency setup and price display                      | Currency records, exchange behavior, formatting, and order history.   |

Historical records and live behavior should be separated. Migrated orders can preserve what happened in the past, but future checkout behavior depends on target configuration. Validation should test both: old orders must remain understandable, and new carts must calculate correctly.

### Orders, Payments, Shipments, and Historical Evidence <a href="#orders-payments-shipments-and-historical-evidence" id="orders-payments-shipments-and-historical-evidence"></a>

VirtueMart orders are not just totals. They provide business evidence: purchased products, selected variants or custom fields, shopper group context, billing and shipping addresses, tax and discount values, payment method labels, shipment method labels, order statuses, invoices, currencies, notes, and timestamps.

The target store may not reproduce every past plugin calculation as live logic. That does not automatically mean migration failed. The key question is whether historical orders remain usable for customer support, accounting reference, fulfillment review, and compliance needs. Live payment and shipment behavior should be validated through target plugin configuration and checkout testing.

| Order evidence                | Why it matters                                                  | Review method                                                           |
| ----------------------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Product line items            | Shows what was purchased and how product choices were recorded. | Compare simple, child-product, custom-field, and discount-heavy orders. |
| Tax and discount values       | Explain historical totals and business rules.                   | Check totals, labels, rates, and source notes where available.          |
| Payment and shipment labels   | Help customer service understand the order context.             | Confirm labels and statuses are readable after migration.               |
| Invoices and order documents  | Support accounting and post-order operations.                   | Decide whether documents, numbers, or references need special handling. |
| Currency and language context | Preserves localized purchase evidence.                          | Test multilingual and multicurrency order samples.                      |

A strong validation set should include old and recent orders, paid and unpaid orders, refunded or cancelled examples if available, orders with coupons or discounts, shipment-sensitive orders, tax-sensitive orders, and orders from different shopper groups.

### Storefront, SEO, Language, and Template Relationships <a href="#storefront-seo-language-and-template-relationships" id="storefront-seo-language-and-template-relationships"></a>

VirtueMart storefront output is shaped by both VirtueMart and Joomla. Product and category data may be migrated correctly while the customer-facing result still changes because menus, aliases, modules, filters, template overrides, metadata, SEF routing, or language structure are different in the target site.

SEO-sensitive planning should include category paths, product aliases, canonical pages, metadata, redirected URLs, menu items, language-specific pages, and important landing pages. Storefront validation should include search, filtering, breadcrumbs, product detail pages, category pages, cart entry points, and module-driven product blocks.

| Storefront element | Data-model issue                                                            | Validation requirement                                |
| ------------------ | --------------------------------------------------------------------------- | ----------------------------------------------------- |
| Product URL        | Depends on Joomla menu and VirtueMart alias behavior.                       | Compare source and target URLs for priority products. |
| Category route     | Depends on category hierarchy and menu structure.                           | Test navigation depth, breadcrumbs, and redirects.    |
| Template override  | May change field display or product layout.                                 | Review visible page output, not only admin records.   |
| Module output      | May display featured, latest, related, or category-specific products.       | Confirm modules use migrated data correctly.          |
| Language records   | May require translated product, category, menu, and metadata relationships. | Validate representative language versions.            |

This is why VirtueMart migration should be reviewed as a working Joomla store, not only as a database transfer.

### Custom, Plugin-Owned, and Integration-Owned Data <a href="#custom-plugin-owned-and-integration-owned-data" id="custom-plugin-owned-and-integration-owned-data"></a>

VirtueMart stores often include third-party plugins, custom fields, external integrations, ERP references, marketplace connectors, accounting exports, product feed tools, subscription extensions, custom checkout fields, custom reports, or custom database tables. Some of this data may be visible in the store but not part of the standard supported scope.

The migration plan should classify these requirements early. Standard Service can cover supported data within standard mapping. Add-ons can extend supported outcomes where predefined. Custom Service is appropriate when data requires transformation, unsupported source extraction, custom target insertion, plugin-specific interpretation, custom logic, or integration-aware handling.

| Data type                                                       | Usual planning classification | Reason                                                           |
| --------------------------------------------------------------- | ----------------------------- | ---------------------------------------------------------------- |
| Standard VirtueMart products, categories, customers, and orders | Standard Service candidate    | Data follows recognizable supported structures.                  |
| Additional supported relationships or options                   | Add-ons candidate             | Scope can be expanded through defined service options.           |
| Plugin-specific checkout data                                   | Custom Service review         | Meaning depends on a third-party extension or custom schema.     |
| ERP or accounting identifiers                                   | Custom Service review         | External system continuity may require exact preservation rules. |
| Custom product builders or configurators                        | Custom Service review         | Product meaning may not map to native VirtueMart structures.     |

Classification protects the migration from late surprises. It also helps the merchant decide what must be moved, what should be rebuilt, and what should be retired instead of recreated.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VirtueMart data model differences are not only technical. They affect how products sell, how shopper groups behave, how prices calculate, how orders remain useful, how checkout methods appear, and how the Joomla storefront presents migrated records.

A reliable VirtueMart migration plan separates Joomla structure from VirtueMart commerce data, studies product and shopper relationships, reviews calculation rules, tests payment and shipment context, validates storefront paths, and identifies plugin-owned or custom data before Full Migration. The strongest outcomes come from treating data meaning as the core planning unit, not from relying on record counts alone.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do VirtueMart variants require special review?**

Because source variants may translate into VirtueMart child products, custom fields, or another configuration pattern. The right structure depends on SKU, stock, price, image, order-line, and checkout behavior.

**Are VirtueMart shopper groups the same as customer groups on every source platform?**

No. Shopper groups can affect pricing, visibility, tax, payment, shipment, and access behavior, so their business meaning should be reviewed before mapping.

**Do payment and shipment methods migrate as ordinary records?**

Historical payment and shipment labels may be preserved as order evidence, but live checkout behavior usually depends on target VirtueMart plugins and configuration.

**Why does Joomla structure matter in a VirtueMart data model review?**

Joomla controls menus, routes, modules, templates, language structure, metadata, and access rules. These elements influence how VirtueMart data appears and functions in the storefront.
