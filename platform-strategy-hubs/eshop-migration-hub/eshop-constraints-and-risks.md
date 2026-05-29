# EShop Constraints and Risks

EShop by Ossolution Team is a flexible Joomla e-commerce extension, but that flexibility also means migration risk is not limited to whether products, customers, and orders can be created in the target administration area. The more important question is whether the migrated store still behaves correctly inside the EShop and Joomla environment.

The highest-risk areas usually appear where source data carries business meaning through options, attributes, customer groups, custom checkout fields, tax zones, shipping logic, payment methods, multilingual content, modules, themes, layout overrides, or custom plugins. These areas can look like ordinary store data during export, but they often depend on configuration, extensions, or implementation choices after migration.

A strong EShop migration plan identifies those constraints early. Some risks can be handled through cleanup, mapping, target configuration, Demo Migration review, or Standard Add-ons. Others need Custom Service because the expected result depends on unsupported data, custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, Custom Platform handling, or bespoke interpretation of plugin-owned behavior.

### Where Risk Concentrates in an EShop Migration <a href="#where-risk-concentrates-in-an-eshop-migration" id="where-risk-concentrates-in-an-eshop-migration"></a>

EShop migration risk concentrates where catalog data, sales history, Joomla structure, and configuration-sensitive behavior overlap. A product may migrate as a product record but still fail to represent shopper choice if options are misunderstood. An order may migrate as an order record but still lose operational value if line-item options, coupons, vouchers, tax, shipping, payment method, or order status meaning is unclear. A category may migrate as a category record but still fail storefront expectations if menus, modules, aliases, metadata, or layout overrides are not reviewed.

| Risk area                        | Why it matters in EShop                                                                                                | Early planning focus                                                                                        |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Product options and attributes   | EShop separates shopper-facing product choices from product specifications used for comparison or product information. | Confirm what should become selectable options, what should become attributes, and what needs custom review. |
| Customer groups                  | Customer groups can affect pricing, discounts, specials, and tax-related behavior.                                     | Review group membership, pricing rules, tax assumptions, and representative customer/order samples.         |
| Taxes, geo-zones, and currencies | Tax and regional behavior depends on target-side configuration, not only migrated records.                             | Document tax classes, tax rates, zones, geo-zones, currencies, and expected calculation behavior.           |
| Shipping and payment plugins     | Shipping and payment behavior depends on active EShop plugins and configuration.                                       | Separate historical order context from live checkout setup and gateway/carrier readiness.                   |
| Joomla storefront layer          | Menus, modules, themes, aliases, metadata, and layout overrides can affect how migrated data appears.                  | Review high-value routes, product/category pages, modules, templates, and implementation responsibilities.  |
| Custom and extension-owned data  | Source extensions, custom fields, plugins, or custom code may create data that does not map to EShop by default.       | Identify unsupported fields, custom relationships, outside identifiers, and Custom Service requirements.    |

The table is only a planning entry point. Each constraint should be reviewed in terms of who it affects, what can be mitigated through preparation, and when the risk should be escalated before migration execution.

### Product Options and Attributes Can Be Misread <a href="#product-options-and-attributes-can-be-misread" id="product-options-and-attributes-can-be-misread"></a>

#### Description <a href="#description" id="description"></a>

A central EShop constraint is the distinction between product options and product attributes. Options are shopper-facing product selections, such as size, color, package, format, or other choices that may affect the purchase. Attributes describe product specifications or comparison information, such as material, dimensions, technical details, or other informational values.

This distinction matters because many Source Platforms do not separate these concepts in the same way. A source store may use variants, modifiers, custom fields, attributes, bundled choices, configurable products, or app-created option sets. If those structures are flattened or assigned to the wrong EShop layer, shoppers may see incomplete buying choices, merchants may lose management clarity, and historical order lines may become harder to interpret.

#### Who It Affects <a href="#who-it-affects" id="who-it-affects"></a>

This constraint affects merchants with variant-heavy catalogs, configurable products, option-level pricing, option-level stock, product add-ons, required selections, technical specifications, comparison tables, or source-specific product fields. It also affects merchants whose product pages depend on shoppers making choices before checkout.

#### Mitigation Strategy <a href="#mitigation-strategy" id="mitigation-strategy"></a>

Before migration, identify representative products that show the full range of source product complexity. These should include simple products, option-heavy products, attribute-heavy products, products with price-changing choices, products with inventory-sensitive choices, and products with important specification data. Demo Migration should prove not only that the product exists, but that the product can be understood and purchased correctly inside EShop.

When the source uses custom product structures or app-owned option logic, review whether Advanced Data Mapping, Advanced Data Configure, or Custom Service is needed. Custom Service should be reviewed when option behavior requires bespoke transformation rather than ordinary field mapping.

### Customer Groups Can Carry Pricing and Tax Meaning <a href="#customer-groups-can-carry-pricing-and-tax-meaning" id="customer-groups-can-carry-pricing-and-tax-meaning"></a>

#### Description <a href="#description-1" id="description-1"></a>

EShop customer groups may influence customer segmentation, special prices, discounts, and tax-related behavior. This makes customer groups more than a label. If a customer group in the source store controls B2B pricing, wholesale visibility, tax treatment, discount access, or customer-specific selling rules, the migration plan must preserve the meaning where supported and identify configuration work where the meaning depends on target settings.

The risk increases when the Source Platform uses customer roles, membership levels, wholesale groups, account types, tax-exempt groups, subscription status, or external CRM segments. Those structures may not transfer cleanly into EShop without mapping review or customization.

#### Who It Affects <a href="#who-it-affects-1" id="who-it-affects-1"></a>

This constraint affects B2B stores, wholesale catalogs, member-priced stores, regional price groups, tax-exempt customers, merchants with customer-specific discounts, and stores where customer group behavior affects order totals.

#### Mitigation Strategy <a href="#mitigation-strategy-1" id="mitigation-strategy-1"></a>

Prepare a list of all source customer groups, their business purpose, and the pricing or tax behavior attached to each group. Validate customer group samples during Demo Migration, including customers from different groups and orders that prove how group-related pricing or tax assumptions were represented.

When customer group logic depends on third-party extensions, custom pricing rules, external systems, or non-standard source fields, the requirement should be reviewed before execution. Group names alone are not enough; the migration plan must clarify what the group is expected to do after migration.

### Tax Classes, Geo-Zones, and Currencies Depend on Configuration <a href="#tax-classes-geo-zones-and-currencies-depend-on-configuration" id="tax-classes-geo-zones-and-currencies-depend-on-configuration"></a>

#### Description <a href="#description-2" id="description-2"></a>

Tax and regional behavior in EShop depends on tax rates, tax classes, customer groups, zones, geo-zones, currencies, and target configuration. These structures can be migrated, configured, or recreated depending on the selected migration path and supported behavior, but they should not be treated as simple static data.

The main constraint is that source tax behavior often reflects a combination of platform rules, plugins, location logic, product tax classes, customer type, and historical order calculation. Even if historical order totals are preserved, live checkout tax behavior in EShop still depends on the target-side setup.

#### Who It Affects <a href="#who-it-affects-2" id="who-it-affects-2"></a>

This constraint affects merchants selling across countries, regions, states, provinces, tax zones, VAT areas, tax-exempt customer groups, mixed product tax classes, or multiple currencies. It also affects stores whose historical orders must remain accurate for accounting reference.

#### Mitigation Strategy <a href="#mitigation-strategy-2" id="mitigation-strategy-2"></a>

Separate historical order tax context from future checkout tax configuration. Historical orders should remain readable with their tax amounts and totals. Future checkout behavior should be configured and tested inside EShop with the correct countries, zones, geo-zones, tax classes, tax rates, currencies, and customer group assumptions.

Demo Migration should include orders with different tax scenarios and products assigned to different tax classes if relevant. If the source uses custom tax plugins, external tax services, custom jurisdiction logic, or unsupported tax data, review the requirement under Custom Service.

### Shipping and Payment Behavior Is Plugin-Sensitive <a href="#shipping-and-payment-behavior-is-plugin-sensitive" id="shipping-and-payment-behavior-is-plugin-sensitive"></a>

#### Description <a href="#description-3" id="description-3"></a>

EShop supports payment and shipping through plugins. That creates a clear migration constraint: historical payment and shipping context is not the same as live gateway or carrier behavior. A migrated order can preserve payment method, shipping method, totals, and references where supported, but the future checkout experience depends on installed, configured, and tested EShop payment and shipping plugins.

Shipping may depend on flat rates, price-based rules, item-based rules, free shipping, weight, quantity, postcode logic, carrier integrations, product weight, product dimensions, destination, or source-specific logic. Payment behavior may depend on gateway plugins, transaction references, status flows, security settings, offline payment handling, or third-party provider configuration.

#### Who It Affects <a href="#who-it-affects-3" id="who-it-affects-3"></a>

This constraint affects merchants with regional shipping rules, carrier-calculated rates, weight-based or quantity-based shipping, free-shipping thresholds, postcode shipping, multiple payment methods, offline payment workflows, gateway-specific statuses, or orders that rely on payment/shipping references for support.

#### Mitigation Strategy <a href="#mitigation-strategy-3" id="mitigation-strategy-3"></a>

Document which payment and shipping information must remain visible in historical orders and which behavior must be configured for future checkout. Select order samples with different payment and shipping methods, shipping charges, discounts, tax, coupons, vouchers, and statuses.

If the source store uses custom shipping plugins, external fulfillment logic, carrier-specific identifiers, gateway-owned metadata, or bespoke payment workflows, those items should be escalated before migration. The migration should not assume that historical order context automatically recreates live checkout behavior.

### Catalog Mode, Shopping Behavior, Quote Mode, and Stock Rules Need Early Review <a href="#catalog-mode-shopping-behavior-quote-mode-and-stock-rules-need-early-review" id="catalog-mode-shopping-behavior-quote-mode-and-stock-rules-need-early-review"></a>

#### Description <a href="#description-4" id="description-4"></a>

EShop can support different store behavior depending on configuration and product settings. A store may behave like a selling store, catalog-only store, quote-oriented store, or mixed environment depending on settings such as Catalog Mode, shopping behavior, Call for Price, quote mode, stock checkout, quantity rules, stock statuses, product availability, downloadable products, and require-shipping settings.

This creates risk when the source store uses unusual purchase rules. A product may appear in EShop but not be buyable in the expected way if mode settings, inventory rules, quantity limits, or quote behavior are not aligned.

#### Who It Affects <a href="#who-it-affects-4" id="who-it-affects-4"></a>

This constraint affects catalog-only merchants, quote-based sellers, stores with Call for Price behavior, limited-stock stores, downloadable product sellers, stores with minimum or maximum quantity rules, stores with backorder expectations, and merchants with mixed product types.

#### Mitigation Strategy <a href="#mitigation-strategy-4" id="mitigation-strategy-4"></a>

Document which products should be purchasable, quote-only, hidden from purchase, downloadable, shipping-required, inventory-limited, or managed through special quantity rules. Demo Migration should include products that represent each behavior.

If the source platform uses custom quote workflows, request-for-price logic, subscription behavior, product bundles, external inventory rules, or custom stock handling, the project may need Custom Service review rather than relying on ordinary product migration.

### Custom Checkout Fields and Product Custom Fields Can Break Assumptions <a href="#custom-checkout-fields-and-product-custom-fields-can-break-assumptions" id="custom-checkout-fields-and-product-custom-fields-can-break-assumptions"></a>

#### Description <a href="#description-5" id="description-5"></a>

EShop supports custom checkout fields and product custom fields, but custom fields are not automatically equivalent across platforms. A field may be informational, operational, required for checkout, tied to a customer address, connected to a product, used in reporting, or controlled by custom logic. The constraint is not the presence of custom fields; it is whether the source meaning can be represented accurately in the target structure.

Product custom fields may come from source product metadata, app-created fields, custom code, ERP fields, supplier data, downloadable file references, or internal management notes. Checkout fields may come from billing requirements, delivery requirements, customer tax IDs, compliance fields, order notes, delivery instructions, or custom sales workflows.

#### Who It Affects <a href="#who-it-affects-5" id="who-it-affects-5"></a>

This constraint affects stores with many custom product fields, custom checkout fields, delivery instructions, tax identification fields, internal reference fields, product technical fields, custom customer address fields, and non-standard order capture requirements.

#### Mitigation Strategy <a href="#mitigation-strategy-5" id="mitigation-strategy-5"></a>

Create a field inventory before migration. For each field, define where it appears, who uses it, whether it affects checkout or operations, whether it should be searchable or visible, and whether it belongs to products, customers, orders, addresses, checkout, or Joomla content.

Advanced Data Mapping or Advanced Data Configure may help when the field can be handled within standard Add-on capability. Custom Service should be reviewed when fields require bespoke transformation, custom migration logic adjustment, unsupported target handling, or interpretation of plugin-owned data.

### Multilingual Data Requires Translation Completeness <a href="#multilingual-data-requires-translation-completeness" id="multilingual-data-requires-translation-completeness"></a>

#### Description <a href="#description-6" id="description-6"></a>

EShop multilingual behavior may involve translated values inside edit screens and supported multilingual areas such as products, categories, custom fields, messages, attributes, attribute groups, options, manufacturers, labels, downloads, lengths, and weights. This can differ from source systems that use separate records, separate stores, app-based translation layers, language-specific URLs, or translation plugins.

The risk is that the default-language store appears complete while secondary-language content is missing, incomplete, misassigned, or inconsistent. Multilingual defects are often discovered late because reviewers validate the main language first and only later test the full customer journey in other languages.

#### Who It Affects <a href="#who-it-affects-6" id="who-it-affects-6"></a>

This constraint affects multilingual Joomla stores, international catalogs, stores with language-specific product names/descriptions/options, multilingual category trees, translated checkout messages, translated attributes, translated manufacturers, and stores where SEO depends on language-specific pages or aliases.

#### Mitigation Strategy <a href="#mitigation-strategy-6" id="mitigation-strategy-6"></a>

Prepare a translation inventory by data area. Identify which languages must be supported, which records have translated content, which fields are business-critical, and which translation gaps already exist in the Source Platform. Demo Migration should include records with complete multilingual content and records with known translation complexity.

If the source multilingual structure must be restructured to fit EShop’s multilingual model, or if translation content is owned by third-party extensions, Custom Service should be reviewed before execution.

### Joomla Modules, Themes, Layout Overrides, and Routes Affect Storefront Continuity <a href="#joomla-modules-themes-layout-overrides-and-routes-affect-storefront-continuity" id="joomla-modules-themes-layout-overrides-and-routes-affect-storefront-continuity"></a>

#### Description <a href="#description-7" id="description-7"></a>

EShop operates inside Joomla, so storefront continuity depends on more than migrated records. Menus, aliases, metadata, page headings, modules, EShop themes, Joomla templates, template overrides, product filter modules, search modules, product modules, category modules, manufacturer modules, cart modules, and custom layouts may all affect how the migrated store appears and behaves.

The constraint is that data migration cannot automatically recreate every storefront implementation decision. Products and categories may migrate correctly while the site still needs menu setup, module placement, theme selection, layout adjustment, template override review, metadata checks, or redirect planning.

#### Who It Affects <a href="#who-it-affects-7" id="who-it-affects-7"></a>

This constraint affects merchants with strong SEO dependence, custom Joomla templates, custom product/category layouts, module-heavy storefronts, product filters, search-driven shopping, manufacturer pages, custom menus, landing pages, multilingual routes, or heavily designed product pages.

#### Mitigation Strategy <a href="#mitigation-strategy-7" id="mitigation-strategy-7"></a>

Before migration, identify high-value product pages, category pages, manufacturer pages, landing pages, menu paths, module positions, aliases, metadata, and custom layout areas. Decide which work belongs to migration, which belongs to Joomla implementation, and which requires developer review.

Template overrides, custom layouts, and custom modules should be checked carefully. When the expected migration outcome depends on interpreting Joomla implementation logic rather than migrating supported data, Custom Service should be reviewed.

### Custom Plugins and Developer Behavior Are Custom Service Signals <a href="#custom-plugins-and-developer-behavior-are-custom-service-signals" id="custom-plugins-and-developer-behavior-are-custom-service-signals"></a>

#### Description <a href="#description-8" id="description-8"></a>

EShop is built on Joomla MVC and supports development of EShop plugins, payment plugins, shipping plugins, layout customization, themes, and other extension-level changes. This is valuable for customization, but it also creates migration risk when the source store depends on custom plugin behavior or when the target result requires custom EShop behavior.

The main constraint is that custom code can hide business rules outside ordinary exports. A source plugin may create fields, relationships, statuses, calculations, identifiers, or workflow rules that are not visible in normal product, customer, or order data. Likewise, a target-side EShop customization may require migrated data to be shaped in a specific way.

#### Who It Affects <a href="#who-it-affects-8" id="who-it-affects-8"></a>

This constraint affects merchants using custom Joomla development, custom EShop plugins, custom payment or shipping logic, ERP integrations, external inventory systems, membership integrations, quote workflows, search/filter extensions, custom reporting, or source platforms with bespoke database structures.

#### Mitigation Strategy <a href="#mitigation-strategy-8" id="mitigation-strategy-8"></a>

Inventory custom code and integration points before migration. Identify what each customization does, what data it owns, whether the data must migrate, whether the behavior must be recreated, and whether the migration result depends on custom fields or relationships.

Custom Service should be reviewed when the migration requires unsupported plugin data, custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, external identifiers, Custom Platform interpretation, or broader bespoke transformation. Add-ons should not be used as a substitute for custom development review when the requirement is outside standard service capability.

### What Deserves Earliest Review <a href="#what-deserves-earliest-review" id="what-deserves-earliest-review"></a>

The earliest review should focus on the source areas where ordinary record counts hide structure. Product count, customer count, and order count are not enough to estimate EShop migration complexity. A smaller source store with custom options, group pricing, checkout fields, multilingual products, custom plugins, and complex tax/shipping logic can require more planning than a larger store with clean records.

The most important early-review items are:

1. Products that prove the full product model, including options, attributes, discounts, specials, customer groups, downloads, tax class, stock behavior, quantity rules, and custom fields.
2. Categories, manufacturers, labels, reviews, tags, aliases, metadata, and modules that shape discovery.
3. Customer groups and customer records that affect pricing, discounts, tax, visibility, or order interpretation.
4. Orders with options, coupons, vouchers, tax, shipping, payment method, shipping method, status changes, comments, billing details, and shipping details.
5. Tax rates, tax classes, currencies, countries, zones, geo-zones, stock statuses, order statuses, length units, and weight units.
6. Shipping and payment plugin requirements for both historical order context and future checkout configuration.
7. Custom checkout fields, product custom fields, source extension data, and plugin-owned data.
8. Multilingual content across products, categories, options, attributes, manufacturers, labels, messages, and custom fields.
9. Joomla menus, routes, aliases, metadata, modules, themes, template overrides, and layout customizations.

These areas should be reviewed before Demo Migration sample selection. If the samples are too simple, the Demo Migration may pass while the real migration risk remains hidden.

### When Risk Increases <a href="#when-risk-increases" id="when-risk-increases"></a>

Risk increases when the source store’s behavior cannot be explained through standard records and target configuration. The strongest escalation signals are custom source structures, unsupported extension data, plugin-owned fields, external identifiers, complex multilingual restructuring, source-specific customer group logic, custom checkout behavior, custom tax/shipping/payment logic, and Joomla implementation dependencies that must be preserved as part of the migration outcome.

| Escalation signal                                                                | Why it increases risk                                                        | Likely review direction                                                         |
| -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Source product choices do not cleanly separate into EShop options and attributes | Shopper choice and product specification meaning may be lost or misassigned. | Mapping review, Demo Migration samples, possible Custom Service.                |
| Customer groups control pricing, tax, access, or discounts                       | Group labels alone may not preserve the expected selling behavior.           | Customer group evidence, sample orders, configuration review.                   |
| Tax, shipping, or payment logic depends on plugins or custom rules               | Live checkout behavior may need target setup or bespoke review.              | Configuration review, plugin readiness review, possible Custom Service.         |
| Custom checkout fields or product custom fields are operationally important      | Fields may not map cleanly without custom interpretation.                    | Advanced Data Mapping, Advanced Data Configure, or Custom Service.              |
| Multilingual source content uses a different translation model                   | Records may need restructuring instead of direct transfer.                   | Translation inventory and Custom Service review when restructuring is required. |
| Joomla layouts, modules, or overrides define the storefront                      | Data migration alone may not recreate the customer-facing result.            | Joomla implementation review and possible developer involvement.                |
| Source or target behavior depends on custom plugins                              | Business rules may exist outside standard data.                              | Custom Service and custom migration logic adjustment review.                    |

A migration approach is too light when these signals are present but the plan still assumes ordinary record transfer. The earlier they are identified, the easier it is to decide whether Standard Service, Managed Service, Add-ons, or Custom Service is the right path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EShop migration constraints are concentrated in the areas where Joomla extension flexibility meets commercial data meaning. Product options, attributes, customer groups, taxes, geo-zones, shipping plugins, payment plugins, checkout fields, multilingual records, modules, themes, layout overrides, and custom plugins can all affect whether the migrated store works as expected.

The safest EShop migration plan does not treat these areas as afterthoughts. It identifies which data can be migrated through standard service capability, which behavior must be configured in EShop, which areas need Add-on review, and which requirements should move into Custom Service because they depend on custom logic or unsupported source structures.

Before starting Full Migration to EShop, use Demo Migration and Live Chat to review the source areas where business meaning may be hidden in options, attributes, customer groups, checkout fields, tax/shipping/payment rules, multilingual content, or Joomla implementation details. Clear early review helps keep the selected migration path aligned with the real complexity of the project.

### FAQs <a href="#faqs" id="faqs"></a>

**Why are product options and attributes a major EShop migration risk?**

Because EShop treats product options and attributes as different kinds of product information. Options affect shopper selection and purchase behavior, while attributes describe or compare products. If a source store mixes these concepts, the migrated result may be visible but commercially confusing.

**Do EShop tax and shipping rules migrate automatically?**

Historical tax and shipping context may be preserved where supported by the selected migration path, but live checkout behavior depends on EShop configuration, tax classes, geo-zones, currencies, shipping plugins, and payment plugins. These areas should be reviewed and tested separately from record migration.

**When should customer groups be reviewed before migration?**

Customer groups should be reviewed early when they affect pricing, discounts, specials, tax behavior, access, or order interpretation. Group names alone do not prove that the business behavior will be preserved in EShop.

**Can custom checkout fields and product custom fields be migrated to EShop?**

They may be handled when supported and properly mapped, but custom fields need review because their meaning can vary by source platform. Fields tied to business logic, plugin behavior, external systems, or unsupported structures may require Advanced Data Mapping, Advanced Data Configure, or Custom Service.

**When does an EShop migration constraint require Custom Service?**

Custom Service should be reviewed when the migration involves Custom Platform source data, unsupported extension data, custom plugins, product or checkout fields requiring bespoke interpretation, multilingual restructuring, external identifiers, custom statuses, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.
