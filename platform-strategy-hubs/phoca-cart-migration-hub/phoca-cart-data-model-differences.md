# Phoca Cart Data Model Differences

Phoca Cart migration should be understood as a translation into a Joomla-based e-commerce extension, not only as a transfer of product, customer, and order records. Phoca Cart can support physical products, digital products, catalog-style presentation, shopping cart behavior, invoicing, POS-related workflows, customer benefits, reward points, multilingual and multicurrency selling, tax rules, shipping methods, payment plugins, feeds, modules, template overrides, and open-source customization. Those capabilities create a data model where commerce records, Joomla site structure, extension configuration, and storefront presentation work together.

Phoca Cart 6.1.0 is the current official stable release, so platform behavior should be evaluated against that version unless the migration project targets an older operational installation. Older Phoca Cart versions may still be used when the Joomla environment and Phoca Cart installation remain functional, but older behavior should not be assumed to match the current release. Migration planning should confirm the Phoca Cart version, Joomla version, extension stack, template framework, and customizations before deciding how source data should be interpreted.

A strong Phoca Cart migration result preserves commercial meaning. Products should remain understandable. Attributes, options, specifications, and parameters should retain their correct roles. Customer groups and customer benefits should remain useful. Orders should keep enough historical context to support operations. Tax, payment, shipping, invoices, multilingual content, modules, and templates should be validated as part of the final Joomla store experience.

### Core Structural Layers in Phoca Cart <a href="#core-structural-layers-in-phoca-cart" id="core-structural-layers-in-phoca-cart"></a>

Phoca Cart separates different kinds of commerce meaning across catalog records, selling configuration, customer context, order history, Joomla presentation, and extension-level behavior. A source platform may store these ideas in a single product table, app-owned objects, theme settings, or custom fields. In Phoca Cart, the same business meaning may need to land across multiple layers.

| Phoca Cart layer                                    | What it usually represents                                                                                                                       | Migration interpretation                                                                                                               |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| Product and catalog records                         | Products, categories, manufacturers, images, physical or digital product behavior, catalog organization, and product visibility                  | The migrated catalog should preserve how products are sold, discovered, filtered, displayed, and managed.                              |
| Attributes, options, specifications, and parameters | Product choice, product description, technical comparison, shopper-facing selection, or internal product detail depending on the field type      | These structures should not be treated as interchangeable. Each one affects a different part of the shopping or management experience. |
| Customer and benefit structures                     | Customer accounts, customer groups, reward points, discounts, coupons, and group-specific behavior                                               | Customer data should preserve more than contact details; it may affect pricing, benefits, and store access.                            |
| Order and invoice history                           | Purchased products, quantities, totals, discounts, taxes, shipping, payment context, status meaning, invoice references, and fulfillment history | Order migration should preserve operational readability, not only order numbers and totals.                                            |
| Joomla storefront layer                             | Menus, modules, templates, template overrides, layouts, multilingual routing, and content relationships                                          | A correct data migration can still fail visually if Joomla presentation and discovery paths are not prepared.                          |
| Extensions and custom behavior                      | Payment plugins, shipping plugins, feeds, POS-related workflows, imports/exports, custom fields, custom code, and third-party integrations       | Non-standard behavior may require Add-on review or Custom Service when it cannot be represented through standard migration capability. |

The central data-model question is not whether a source record has somewhere to go. The better question is whether the migrated result preserves the role that record played in the source store.

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

Phoca Cart product data is not just a flat item list. A product can carry shopper-facing information, management information, stock meaning, tax and shipping context, digital product behavior, catalog visibility, attribute-based comparison, option-based selection, multilingual text, images, pricing, and customer-group implications. That makes product migration one of the most important parts of a Phoca Cart project.

#### Products as selling records <a href="#products-as-selling-records" id="products-as-selling-records"></a>

A migrated product should remain sellable, understandable, and manageable. Core product fields such as name, alias, SKU or product code, description, price, images, stock, tax class, category placement, visibility, ordering, and publishing state should be interpreted in relation to how the product will operate in Phoca Cart.

Source platforms often store product meaning differently. One source may use product variations as separate child products. Another may use option combinations. Another may depend on custom fields, app-owned metadata, or theme-specific display logic. Those structures should be reviewed before migration because Phoca Cart needs a clear target interpretation for what the shopper chooses and what the merchant manages.

#### Categories and catalog discovery <a href="#categories-and-catalog-discovery" id="categories-and-catalog-discovery"></a>

Categories in Phoca Cart are part of product discovery and storefront organization. They can influence browsing paths, menu placement, filtering expectations, SEO structure, and multilingual navigation. A category should therefore be validated as more than a label attached to a product.

When a source store contains deep category trees, duplicate categories, seasonal collections, hidden categories, manufacturer-led browsing, or SEO-sensitive category URLs, the target category structure should be planned before Full Migration. A product can technically migrate into Phoca Cart but still become difficult to find if category placement, menu links, modules, or route behavior are not aligned.

#### Physical, digital, and catalog-style products <a href="#physical-digital-and-catalog-style-products" id="physical-digital-and-catalog-style-products"></a>

Phoca Cart supports use cases beyond a simple physical-product store. Physical products may depend on stock, shipping rules, dimensions, weight, tax classes, and fulfillment assumptions. Digital products may depend on downloadable files, access behavior, customer account context, and post-purchase availability. Catalog-style products may need strong product presentation without ordinary add-to-cart behavior.

These differences matter because a source product type should not be flattened into a generic product record. The migrated result should preserve whether the item is purchased, downloaded, displayed for inquiry, handled through catalog mode, or connected to a special operational process.

### Attributes, Options, Specifications, and Parameters <a href="#attributes-options-specifications-and-parameters" id="attributes-options-specifications-and-parameters"></a>

One of the most important Phoca Cart data-model distinctions is the difference between product choice, product description, product comparison, and product configuration. Many source platforms blur these ideas. Phoca Cart can represent them through different structures, so migration planning should decide what each source field actually means.

#### Product options as shopper choices <a href="#product-options-as-shopper-choices" id="product-options-as-shopper-choices"></a>

Options usually matter when shoppers must choose something before purchasing. Size, color, package, material, engraving, format, license type, file type, or delivery preference may all behave as options if they affect selection, pricing, availability, image behavior, or order line meaning.

A source field should become a Phoca Cart option only when it needs to participate in buying behavior. If the source platform used options for descriptive information only, mapping every option directly may create unnecessary choice fields and a confusing product page. If the source platform used custom fields to represent required choices, those fields may need deeper mapping review so the target product remains purchasable.

#### Attributes and specifications as descriptive or comparative meaning <a href="#attributes-and-specifications-as-descriptive-or-comparative-meaning" id="attributes-and-specifications-as-descriptive-or-comparative-meaning"></a>

Attributes and specifications usually explain what the product is. They may support product comparison, filtering, detail tables, technical information, dimensions, materials, compatibility, ingredients, warranty, or other shopper research needs. They are not always purchase choices.

The migration implication is simple but important: a source attribute should be interpreted by function, not by name. A field called “color” may be a selectable option in one store and a descriptive attribute in another. A field called “size” may affect price and stock, or it may only describe the product dimensions. Misclassifying these fields can distort both the product page and the order record.

#### Parameters and custom product fields <a href="#parameters-and-custom-product-fields" id="parameters-and-custom-product-fields"></a>

Parameters and custom fields may carry store-specific meaning that does not fit a standard product field. They may drive display logic, import/export workflows, custom modules, feed generation, advanced filtering, shipping restrictions, product labels, or custom development.

When these fields exist in the source store, they should be reviewed before assuming standard migration capability is enough. Straight field-to-field mapping may work when the target field exists and has the same meaning. Advanced Data Mapping or Advanced Data Configure may be useful when the supported behavior needs structured mapping or configuration. Custom Service should be reviewed when the field is tied to unsupported extension data, custom code, third-party identifiers, external systems, or bespoke transformation.

### Stock, Pricing, Discounts, and Customer Benefits <a href="#stock-pricing-discounts-and-customer-benefits" id="stock-pricing-discounts-and-customer-benefits"></a>

Product data becomes operational when pricing, stock, discounts, coupons, reward points, and customer group behavior are applied. Phoca Cart can support customer benefits and group-based commerce logic, so migrated data should preserve the relationship between the product, the customer, and the sale condition.

#### Stock meaning <a href="#stock-meaning" id="stock-meaning"></a>

Stock migration should clarify whether the source store uses global stock, product-level stock, option-level stock, negative-stock permissions, backorder behavior, stock status text, or manual stock management. Older Phoca Cart installations may use different configuration patterns than current Phoca Cart behavior, so stock assumptions should be confirmed for the target installation.

The migrated product should not only show a quantity. It should behave correctly when shoppers add products to the cart, when stock reaches zero, when product options affect availability, and when store owners review inventory after migration.

#### Pricing and customer group meaning <a href="#pricing-and-customer-group-meaning" id="pricing-and-customer-group-meaning"></a>

Pricing can depend on ordinary product price, sale price, discounts, coupons, reward points, tax inclusion, currency, customer group, quantity, or source-specific business rules. If the source platform used B2B-style customer groups, wholesale pricing, loyalty pricing, or group-specific discounts, those rules should be reviewed carefully before migration.

A customer group should not be migrated only as a label if it controls pricing, visibility, tax behavior, or benefits. The data model must preserve how customer identity affects the shopping experience.

#### Coupons, reward points, and benefit logic <a href="#coupons-reward-points-and-benefit-logic" id="coupons-reward-points-and-benefit-logic"></a>

Coupons and reward points can look like simple promotional records, but they often carry conditions: validity dates, usage limits, customer group limits, product/category restrictions, minimum order thresholds, and status rules. Reward points may also connect customer history to future purchasing behavior.

Migration should distinguish between the record and the rule. A coupon code that appears in the target store is not enough if its conditions, limits, and expected behavior are not configured or validated. Reward point balances and customer benefit records should be checked against the target Phoca Cart installation and the selected migration path.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

Customer data in Phoca Cart can connect to account access, addresses, order history, customer groups, benefits, reward points, invoices, and multilingual or regional store behavior. A customer record should therefore be interpreted as operational context, not only as contact data.

#### Customer identity and account continuity <a href="#customer-identity-and-account-continuity" id="customer-identity-and-account-continuity"></a>

A migrated customer should be recognizable in the target store and connected to the appropriate historical orders where supported. Important fields may include name, email, billing address, shipping address, phone number, account status, group membership, tax or company information, and customer-specific benefits.

If the source store allowed guest checkout, merged accounts, duplicate emails, B2B customer records, or imported customer lists from outside systems, those patterns should be reviewed before migration. Account continuity depends on how the source identifies customers and how Phoca Cart expects customer relationships to work inside Joomla.

#### Customer groups and access context <a href="#customer-groups-and-access-context" id="customer-groups-and-access-context"></a>

Customer groups may affect price, discount eligibility, reward behavior, visibility, or store access. They may also overlap with Joomla user groups, depending on the implementation. That relationship should be reviewed because a commerce group and a Joomla permission group may not have the same meaning.

When group behavior affects product visibility, pricing, tax, checkout, or customer benefits, a simple customer import is not enough. Representative customers should be included in Demo Migration so group-sensitive behavior can be validated.

### Order and Invoice Meaning <a href="#order-and-invoice-meaning" id="order-and-invoice-meaning"></a>

Order history should remain useful after migration. In Phoca Cart, order data may connect to products, options, customer identity, addresses, discounts, taxes, shipping, payment, order status, invoice data, email history, and fulfillment workflows.

#### Order records as operational history <a href="#order-records-as-operational-history" id="order-records-as-operational-history"></a>

A migrated order should allow the merchant to understand what was purchased, by whom, under which conditions, and with which financial context. Line items should preserve product names, option selections, quantities, totals, tax, shipping, discounts, coupons, payment references, and status meaning where supported by the selected migration path.

Historical order records are often needed for customer service, warranty review, accounting reference, refund questions, repeat-purchase support, and internal reporting. If the source order data includes custom statuses, third-party fulfillment identifiers, external invoice numbers, POS references, or custom payment fields, those details should be reviewed before migration.

#### Invoice, refund, and payment context <a href="#invoice-refund-and-payment-context" id="invoice-refund-and-payment-context"></a>

Phoca Cart includes invoicing-related workflows and payment plugin support. That does not mean every invoice, refund, or payment detail from a source store automatically becomes native target behavior. Some data may migrate as historical context, while some behavior must be configured in Phoca Cart or reviewed through Custom Service.

The important distinction is between historical readability and active payment behavior. Old payment references may be useful for support and accounting, but current checkout behavior depends on target payment plugins and configuration.

### Tax, Shipping, Payment, and Configuration-Sensitive Data <a href="#tax-shipping-payment-and-configuration-sensitive-data" id="tax-shipping-payment-and-configuration-sensitive-data"></a>

Tax, shipping, and payment behavior is often configuration-sensitive in Phoca Cart. Source stores may represent these rules through tax zones, geo zones, shipping methods, carrier plugins, payment gateways, cart rules, customer groups, product classes, or custom extensions. Migration planning should decide what is data, what is configuration, and what is custom logic.

#### Tax and geo-zone meaning <a href="#tax-and-geo-zone-meaning" id="tax-and-geo-zone-meaning"></a>

Tax migration should account for tax rates, tax classes, tax calculation assumptions, country and region rules, product taxability, customer type, and display behavior. Dynamic tax and tax recapitulation can be important in Phoca Cart contexts, especially for stores that operate across regions or customer types.

Older stores may have tax structures that reflect old business rules or older extension behavior. Current Phoca Cart behavior should be used as the target interpretation only when the migration project is actually moving into a current Phoca Cart installation.

#### Shipping and payment plugins <a href="#shipping-and-payment-plugins" id="shipping-and-payment-plugins"></a>

Shipping and payment behavior may depend on plugins rather than ordinary database records. A shipping method might require weight, dimensions, country, region, carrier logic, free-shipping conditions, or custom calculations. A payment method might require gateway configuration, status rules, order confirmation behavior, or external references.

When the source store depends on an unsupported carrier, payment gateway, custom shipping logic, or third-party checkout integration, the migration plan should separate historical records from active behavior. Historical shipping and payment context may be migrated for reference, while live checkout behavior may need target configuration, plugin replacement, or Custom Service review.

### Multilingual, Multicurrency, and Localization Meaning <a href="#multilingual-multicurrency-and-localization-meaning" id="multilingual-multicurrency-and-localization-meaning"></a>

Phoca Cart supports multilingual and multicurrency scenarios, but migration into a multilingual store is more complex than translating product names. Language, currency, tax display, route behavior, category structure, product fields, modules, and templates may all affect the final result.

#### Multilingual catalog structure <a href="#multilingual-catalog-structure" id="multilingual-catalog-structure"></a>

A multilingual Phoca Cart migration should confirm which fields require language-specific values: product names, descriptions, aliases, metadata, category names, manufacturer text, labels, specifications, parameters, and storefront messages. If the source store used multiple languages through a separate translation extension, app, or custom fields, those records should be mapped to Phoca Cart’s target behavior rather than treated as duplicate products.

Multilingual routing and Joomla menu structure should also be checked because product and category discovery depends on the surrounding Joomla site.

#### Currency and localized selling rules <a href="#currency-and-localized-selling-rules" id="currency-and-localized-selling-rules"></a>

Multicurrency data can involve exchange rates, displayed prices, base currency, rounding, payment compatibility, tax display, and customer-region expectations. A price copied from the source store may not preserve the correct selling context if the source platform applied dynamic exchange rates or currency-specific price lists.

Migration planning should identify whether prices are fixed, converted, customer-group-specific, or currency-specific before deciding how they should appear in Phoca Cart.

### Joomla Storefront and Extension Meaning <a href="#joomla-storefront-and-extension-meaning" id="joomla-storefront-and-extension-meaning"></a>

Phoca Cart operates inside Joomla, so a store’s final meaning is partly shaped by Joomla menus, modules, templates, template overrides, plugins, content relationships, and custom development. Data migration should be interpreted alongside the Joomla implementation.

#### Menus, modules, and templates <a href="#menus-modules-and-templates" id="menus-modules-and-templates"></a>

Product pages, category pages, cart pages, account pages, checkout paths, manufacturer pages, and catalog entry points may depend on Joomla menus and modules. Template frameworks such as Bootstrap or UIkit can affect how the storefront renders. Template overrides can change product layouts, category displays, checkout presentation, or module output.

A migration can preserve the product data but still fail to produce a usable storefront if the Joomla presentation layer is not planned. Storefront continuity should therefore be validated through real product, category, cart, checkout, and account samples.

#### Extension ecosystem and custom code <a href="#extension-ecosystem-and-custom-code" id="extension-ecosystem-and-custom-code"></a>

Phoca Cart can be extended through modules, plugins, feeds, template overrides, import/export tools, invoice tools, and custom code. These layers can create source meaning that is not visible in ordinary product or order records.

If the source store depends on custom Joomla development, unsupported extension tables, external systems, custom import/export structures, or bespoke business logic, the migration should be reviewed through Custom Service. Standard service capability should not be assumed to preserve custom behavior unless the target behavior is supported and mapped clearly.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

A Phoca Cart migration should prove that the target store preserves business meaning across the core data layers. The following proof areas are especially important:

| Proof area                              | What the migrated result should show                                                                                                                     |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products and catalog                    | Products are visible, organized, sellable, and connected to the right categories, images, attributes, options, specifications, and product behavior.     |
| Customer and group behavior             | Customer records, groups, addresses, benefits, reward points, and account relationships remain useful after migration.                                   |
| Orders and invoices                     | Historical orders preserve line items, options, totals, taxes, shipping, payment context, statuses, and invoice-related references where supported.      |
| Pricing and promotions                  | Prices, discounts, coupons, reward logic, customer group prices, and tax behavior are understandable and testable.                                       |
| Shipping and payment context            | Historical shipping/payment records are readable, while active checkout behavior is configured through the correct target plugins.                       |
| Multilingual and multicurrency behavior | Language-specific content, routes, metadata, currency behavior, and localized selling context are coherent in the target store.                          |
| Joomla presentation                     | Menus, modules, templates, overrides, cart paths, checkout paths, and product/category pages support the migrated data.                                  |
| Custom and extension-owned data         | Unsupported fields, custom code, third-party identifiers, feeds, external systems, and bespoke logic are identified for Add-on review or Custom Service. |

The strongest validation samples are not the simplest records. They are the records that reveal the real structure of the store: products with options, products with specifications, digital products, customer-group-specific products, discounted orders, tax-sensitive orders, multilingual product pages, orders with shipping and payment context, and records affected by custom code or extensions.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Phoca Cart data migration is a translation into a Joomla e-commerce extension model where products, attributes, options, specifications, customer groups, rewards, orders, tax, shipping, payment, multilingual behavior, templates, modules, and custom extensions may all shape the final store. A record-count match is not enough. The migrated result must preserve what each record means for shoppers, administrators, customer service, accounting, and future store management.

Migration quality improves when source fields are interpreted by business function before they are mapped into Phoca Cart. Product choices, descriptive attributes, technical specifications, customer benefits, historical orders, and configuration-sensitive rules should each land in the structure that preserves their meaning. Older Phoca Cart installations may require version-specific review, while current release behavior should be evaluated against that release when that is the target environment.

Use Demo Migration results to confirm whether Phoca Cart preserves the meaning of your source data across products, customers, orders, pricing, tax, shipping, payment, multilingual behavior, and Joomla storefront presentation. If the source store includes custom fields, unsupported extension data, external identifiers, bespoke checkout behavior, third-party integrations, or older-version structures that do not clearly match the target installation, review the migration path through Live Chat before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Why are Phoca Cart attributes, options, and specifications treated separately during migration?**

They often serve different purposes. Options may affect shopper selection and order line meaning, while attributes and specifications may describe or compare products. Treating them as interchangeable can create confusing product pages or incomplete order behavior.

**Does the current release behavior apply to every older Phoca Cart store?**

No. The current release is the current official stable release, but older installations may have different data structures, extension behavior, template overrides, or Joomla compatibility assumptions. Older operational stores should be reviewed by version before migration.

**Can product options and customer group pricing be migrated to Phoca Cart?**

They can be included when supported by the selected migration path and when their source meaning can be mapped clearly. Representative products and customer groups should be tested during Demo Migration before Full Migration.

**Are tax, shipping, and payment rules migrated as ordinary data?**

Not always. Historical tax, shipping, and payment context may be part of migrated orders, but active checkout behavior usually depends on target configuration and plugins. Custom rules or unsupported gateway/carrier behavior may require Custom Service review.

**How should custom fields or extension-owned data be handled?**

Custom fields and extension-owned data should be reviewed before migration. Standard mapping may be enough when the target field exists and the meaning is clear. Unsupported data, bespoke logic, external identifiers, or custom Joomla development may require Custom Service.
