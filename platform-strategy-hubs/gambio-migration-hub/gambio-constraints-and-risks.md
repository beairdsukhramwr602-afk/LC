# Gambio Constraints and Risks

Gambio migration risk is rarely caused by one isolated record type. It usually appears where catalog structure, customer group behavior, order history, storefront presentation, legal and regional settings, integrations, and hosting responsibility meet. A product may migrate as a record, but its commercial meaning depends on variants, categories, filters, stock, images, prices, tax behavior, shipping rules, and how the product appears in the storefront.

The most important constraint in a Gambio migration is therefore not whether data can be moved at all. It is whether the source store’s operating logic can be represented cleanly in the future Gambio environment. Merchants planning a migration should review the areas below before assuming that a standard record transfer will preserve the way the business actually sells, manages, and supports customers.

### Where Risk Concentrates in Gambio Migration <a href="#where-risk-concentrates-in-gambio-migration" id="where-risk-concentrates-in-gambio-migration"></a>

Risk concentrates in Gambio migration when the source store relies on structures that are easy to underestimate: product options, variants, customer group pricing, legal or regional settings, storefront design, SEO routes, self-hosted customization, app or module behavior, and third-party integrations.

For simpler stores, these areas may only require ordinary preparation and Demo Migration review. For stores with long operating history, custom development, segmented pricing, multilingual content, B2B workflows, marketplace connections, or highly tailored storefront behavior, these areas should be reviewed earlier and more deliberately.

| Risk area                                  | Why it matters in Gambio migration                                                                             | Earliest review focus                                                                         |
| ------------------------------------------ | -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Cloud versus self-hosted operating model   | Hosting responsibility, update control, customization flexibility, and implementation burden differ by model.  | Confirm whether the Target Platform will be Gambio Cloud or a self-hosted Gambio environment. |
| Product options and variants               | Buying choices, prices, stock, images, and order line meaning may depend on how source options are structured. | Select variant-heavy products for Demo Migration and compare shopper-facing behavior.         |
| Customer groups and pricing                | Group-specific pricing, B2B context, discounts, and tax treatment can affect commercial meaning.               | Identify customer groups, price rules, and representative customers before migration.         |
| Tax, shipping, payment, and legal settings | These areas often require target configuration, not simple data transfer.                                      | Separate migrated records from Gambio settings and post-migration configuration tasks.        |
| Storefront and SEO continuity              | Product/category paths, content pages, metadata, navigation, and layout affect traffic and usability.          | Identify high-value URLs, content pages, menu paths, and SEO-sensitive records.               |
| Customization and integrations             | Self-hosted modifications, modules, connectors, and custom code may not map through standard capability.       | Inventory custom behavior and decide whether Custom Service review is needed.                 |

### Constraint 1: Cloud and Self-Hosted Gambio Are Not the Same Migration Environment <a href="#constraint-1-cloud-and-self-hosted-gambio-are-not-the-same-migration-environment" id="constraint-1-cloud-and-self-hosted-gambio-are-not-the-same-migration-environment"></a>

#### Description <a href="#description" id="description"></a>

Gambio can be evaluated through cloud and self-hosted operating models. This choice affects the migration because the target environment defines who manages hosting, updates, technical access, customization flexibility, and implementation responsibility.

A cloud setup may reduce infrastructure burden and make the target environment easier to operate for merchants who want a managed shop foundation. A self-hosted setup may offer more control and customization flexibility, but it also increases responsibility for hosting, server readiness, updates, technical maintenance, custom code, and extension compatibility.

#### Who It Affects <a href="#who-it-affects" id="who-it-affects"></a>

This constraint affects merchants who are moving from a hosted SaaS platform, merchants with custom code in their source store, merchants planning self-hosted control, and merchants expecting the migration result to include implementation decisions that actually belong to hosting, environment setup, or development work.

It also affects merchants who compare Gambio Cloud and self-hosted Gambio as if they create the same operational burden. The migrated data may be similar in purpose, but the implementation assumptions around access, configuration, customization, updates, and maintenance are not the same.

#### Mitigation Strategy <a href="#mitigation-strategy" id="mitigation-strategy"></a>

The target operating model should be confirmed before migration planning becomes detailed. The merchant should decide whether Gambio Cloud or self-hosted Gambio is the intended Target Platform environment, then review what that choice means for supported data, configuration work, design implementation, custom development, and ongoing operations.

If the source store depends on custom code, unusual data relationships, non-standard integrations, or server-level behavior, the migration should be reviewed before assuming that a standard service path can preserve the full operating model.

### Constraint 2: Product Variants, Options, and Stock Behavior Can Carry Hidden Meaning <a href="#constraint-2-product-variants-options-and-stock-behavior-can-carry-hidden-meaning" id="constraint-2-product-variants-options-and-stock-behavior-can-carry-hidden-meaning"></a>

#### Description <a href="#description-1" id="description-1"></a>

Gambio stores often depend on product structure that is richer than a product title, price, and image. A product may include options, variants, stock behavior, downloadable products, product images, categories, filters, reviews, specials, related items, and base price information. In a source platform, these details may be stored through different structures, extensions, apps, or custom fields.

The risk is that the source product appears to migrate correctly while the shopper-facing buying logic changes. A color, size, bundle, download, stock rule, or price adjustment may not behave the same way unless the source structure is reviewed against Gambio’s target structure.

#### Who It Affects <a href="#who-it-affects-1" id="who-it-affects-1"></a>

This constraint affects merchants with configurable products, apparel catalogs, product bundles, digital downloads, multiple images per product, stock-sensitive sales, product filters, special pricing, base price display requirements, or product records that have been shaped by custom fields or external systems.

It also affects merchants who have inconsistent product data, duplicated options, unclear SKU logic, missing images, mixed variant structures, or years of manual catalog changes.

#### Mitigation Strategy <a href="#mitigation-strategy-1" id="mitigation-strategy-1"></a>

Representative catalog samples should be selected before Demo Migration. These samples should include simple products, variant-heavy products, products with multiple images, products with stock rules, downloadable products, discounted products, products in multiple categories, and products with special display or pricing behavior.

If source product meaning depends on custom fields, unsupported extensions, external identifiers, or bespoke transformation rules, Advanced Data Mapping, Advanced Data Configure, or Custom Service review may be needed.

### Constraint 3: Customer Groups and B2B Pricing Require Early Review <a href="#constraint-3-customer-groups-and-b2b-pricing-require-early-review" id="constraint-3-customer-groups-and-b2b-pricing-require-early-review"></a>

#### Description <a href="#description-2" id="description-2"></a>

Gambio can support customer group and pricing behavior that is important for merchants with segmented customers, wholesale buyers, B2B accounts, or group-specific commercial rules. During migration, customer records alone do not prove that the customer model has been preserved. The target result must also preserve the customer’s intended relationship to pricing, discounts, tax context, visibility, and historical orders where those areas are relevant.

A source platform may handle groups, roles, price lists, wholesale permissions, customer tags, or B2B logic in ways that do not directly match the target structure. This creates a risk that customers migrate but lose the commercial meaning that made the grouping useful.

#### Who It Affects <a href="#who-it-affects-2" id="who-it-affects-2"></a>

This constraint affects merchants with wholesale customers, retail/wholesale segmentation, B2B pricing, logged-in customer pricing, customer-group discounts, tax-sensitive customer types, restricted price visibility, or different purchase conditions by customer group.

It also affects merchants moving from platforms where B2B behavior is controlled by apps, modules, custom code, ERP systems, or external customer records.

#### Mitigation Strategy <a href="#mitigation-strategy-2" id="mitigation-strategy-2"></a>

Before migration, customer groups and representative customer accounts should be documented. The merchant should identify which customers belong to which group, what pricing or rules are attached to each group, and whether any source behavior is native, app-owned, custom, or external.

Demo Migration should include customers and orders from multiple customer groups. If the source uses custom B2B logic, external identifiers, or unsupported pricing relationships, the migration path should be reviewed for Custom Service.

### Constraint 4: Tax, Shipping, Payment, and Legal Settings Are Configuration-Sensitive <a href="#constraint-4-tax-shipping-payment-and-legal-settings-are-configuration-sensitive" id="constraint-4-tax-shipping-payment-and-legal-settings-are-configuration-sensitive"></a>

#### Description <a href="#description-3" id="description-3"></a>

Tax, shipping, payment, regional settings, currencies, order statuses, and legal-compliance-related settings often involve target configuration. They should not be treated as ordinary records that automatically behave the same way after migration.

A source store may have tax rules based on region, product type, customer type, or business model. Shipping may depend on weight, order value, destination, carrier, product group, or custom logic. Payment behavior may rely on gateway identifiers, transaction references, statuses, or third-party systems. Legal and regional display requirements may depend on configuration and storefront presentation.

#### Who It Affects <a href="#who-it-affects-3" id="who-it-affects-3"></a>

This constraint affects merchants selling across regions, using multiple tax zones, offering multiple shipping methods, relying on specific payment providers, managing B2B and B2C buyers in the same store, using multiple currencies or languages, or operating under strict regional compliance expectations.

It also affects merchants who expect migrated orders to fully preserve the operational context behind payment, shipping, tax, invoice, or fulfillment decisions.

#### Mitigation Strategy <a href="#mitigation-strategy-3" id="mitigation-strategy-3"></a>

The migration plan should separate data migration from target configuration. Historical orders should be checked for tax, shipping, payment method, totals, discounts, and status readability. Future selling behavior should be configured and tested in Gambio after migration.

If the source uses custom shipping rules, unsupported payment metadata, third-party tax systems, ERP-controlled fulfillment, or custom compliance workflows, Custom Service review may be required.

### Constraint 5: Storefront Layout and SEO Continuity Are Not Just Data Issues <a href="#constraint-5-storefront-layout-and-seo-continuity-are-not-just-data-issues" id="constraint-5-storefront-layout-and-seo-continuity-are-not-just-data-issues"></a>

#### Description <a href="#description-4" id="description-4"></a>

Gambio migration does not automatically recreate the source storefront design. Product records, category records, and content pages may move, but the final customer experience depends on layout, navigation, theme behavior, content placement, metadata, redirects, product paths, category paths, and how the Gambio storefront is configured.

This matters because storefront continuity affects customer trust, search visibility, paid campaign performance, and post-launch usability. A store can have complete data in the administration area but still feel broken if important pages are difficult to find, key product paths change without planning, or content pages lose their role in the buying journey.

#### Who It Affects <a href="#who-it-affects-4" id="who-it-affects-4"></a>

This constraint affects merchants with strong organic traffic, many indexed product/category URLs, content-rich stores, custom landing pages, extensive navigation, marketing campaign pages, legally important content pages, or storefront layouts that influence conversion.

It also affects merchants moving from platforms where theme, content, category display, product display, and SEO behavior were tightly integrated.

#### Mitigation Strategy <a href="#mitigation-strategy-4" id="mitigation-strategy-4"></a>

Before migration, high-value URLs, key categories, important products, content pages, metadata, internal links, and navigation structures should be documented. The target Gambio storefront should be reviewed for how the migrated data will appear, not only whether it exists.

Demo Migration should include SEO-sensitive products and categories, content pages, and records with important metadata. If redirects, custom layout recreation, or theme-level transformation is required, those needs should be planned separately from ordinary data migration.

### Constraint 6: Custom Development and Integrations Can Exceed Standard Migration Assumptions <a href="#constraint-6-custom-development-and-integrations-can-exceed-standard-migration-assumptions" id="constraint-6-custom-development-and-integrations-can-exceed-standard-migration-assumptions"></a>

#### Description <a href="#description-5" id="description-5"></a>

Gambio can support professional store operations and customization, especially in self-hosted contexts, but migration planning must distinguish supported data migration from custom development, integration recreation, module behavior, and bespoke business logic.

A source store may rely on marketplace connectors, ERP systems, accounting integrations, payment gateway metadata, warehouse systems, CRM sync, custom fields, custom checkout logic, modified database tables, or modules that do not have a direct equivalent in Gambio. These elements may carry business meaning that is not visible in ordinary product, customer, or order exports.

#### Who It Affects <a href="#who-it-affects-5" id="who-it-affects-5"></a>

This constraint affects merchants with custom-developed stores, heavily modified open-source platforms, external systems, marketplace workflows, ERP dependencies, app-owned data, custom order logic, non-standard product structures, or custom reporting requirements.

It also affects merchants who expect the migration itself to recreate source-side functionality rather than move supported data into the Target Platform.

#### Mitigation Strategy <a href="#mitigation-strategy-5" id="mitigation-strategy-5"></a>

Custom behavior should be inventoried before migration. The merchant should identify what belongs to supported data migration, what belongs to target configuration, what belongs to Gambio implementation, and what requires Custom Service.

Custom Service should be reviewed when the migration requires Custom Platform handling, unsupported extension data, third-party data, external identifiers, Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, or broader bespoke transformation.

### What Deserves Earliest Review <a href="#what-deserves-earliest-review" id="what-deserves-earliest-review"></a>

The earliest review should focus on the areas most likely to change migration scope or service path. These areas are not always the largest by record count. They are the areas where business meaning is most likely to be hidden inside configuration, custom logic, integrations, or storefront behavior.

#### Target operating model <a href="#target-operating-model" id="target-operating-model"></a>

Confirm whether the merchant is moving into Gambio Cloud or self-hosted Gambio. This decision affects the implementation path, customization expectations, technical access, update responsibility, and the way post-migration work should be assigned.

#### Representative product structures <a href="#representative-product-structures" id="representative-product-structures"></a>

Review simple products, variant-heavy products, products with stock behavior, digital downloads, products with multiple images, products in multiple categories, filtered products, and products with special pricing. Product structure is one of the most common places where a migration can look successful but still lose selling meaning.

#### Customer group and pricing logic <a href="#customer-group-and-pricing-logic" id="customer-group-and-pricing-logic"></a>

Document customer groups, wholesale or B2B segmentation, group pricing, tax-sensitive customer types, and representative customers. This helps clarify whether the target result can preserve account meaning, not only customer records.

#### Tax, shipping, payment, and order status behavior <a href="#tax-shipping-payment-and-order-status-behavior" id="tax-shipping-payment-and-order-status-behavior"></a>

Review historical orders and future selling configuration separately. Historical order readability and future checkout behavior are related, but they are not the same validation task.

#### Storefront routes, content, and SEO-sensitive pages <a href="#storefront-routes-content-and-seo-sensitive-pages" id="storefront-routes-content-and-seo-sensitive-pages"></a>

Identify important product URLs, category URLs, content pages, navigation paths, metadata, and landing pages. These records should be included in planning because Gambio migration quality depends on both administration-side data and storefront-side usability.

#### Custom and integration-owned data <a href="#custom-and-integration-owned-data" id="custom-and-integration-owned-data"></a>

Inventory custom fields, modified source tables, app-owned data, ERP identifiers, marketplace references, third-party fulfillment fields, and custom checkout or pricing behavior. These are the strongest indicators that Custom Service may be needed.

### When Risk Increases <a href="#when-risk-increases" id="when-risk-increases"></a>

Risk increases when the source store is structurally unclear, heavily customized, or expected to behave identically after migration without separate target configuration and implementation work.

A Gambio migration deserves deeper review when any of the following conditions apply:

* The source catalog uses complex variants, bundles, downloads, option-level pricing, or inconsistent SKU logic.
* Customer groups, wholesale pricing, or B2B rules affect how buyers see prices or purchase products.
* Tax, shipping, payment, currencies, or legal display behavior depends on region-specific or custom logic.
* The merchant is moving from a heavily customized open-source platform or a Custom Platform source.
* Important store behavior is controlled by apps, modules, custom code, ERP systems, or third-party connectors.
* The target environment is self-hosted and requires technical readiness, custom development, or extension compatibility review.
* SEO-sensitive URLs, content pages, or navigation paths are central to traffic and conversion.
* Demo Migration samples include only simple records and do not represent the store’s real complexity.

These signals do not mean the migration cannot proceed. They mean the migration should be planned with clearer samples, stronger evidence, and the correct service path before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio migration risk is highest where ordinary records carry operational meaning: product variants, customer groups, B2B pricing, tax and shipping behavior, payment context, SEO-sensitive storefront paths, content pages, and custom integrations. A safe migration plan does not treat these areas as afterthoughts. It identifies them early, selects representative Demo Migration samples, and separates data migration from target configuration, design implementation, and custom development.

For straightforward stores with clean products, clear categories, simple customer records, and predictable orders, standard migration planning may be enough. For stores with segmented pricing, complex variants, custom checkout behavior, region-specific rules, self-hosted customization, or integration-owned data, the migration should be reviewed more carefully before execution.

Use Demo Migration results to test the risk areas that matter most to the Gambio target environment. If product structure, customer groups, tax rules, shipping behavior, storefront routes, custom fields, integrations, or Custom Platform source data create uncertainty, review the migration path through Live Chat so Standard Service, Managed Service, Custom Service, and Add-on boundaries are clear before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the biggest risk in a Gambio migration?**

The biggest risk is assuming that migrated records automatically preserve business meaning. Products, variants, customer groups, tax rules, shipping methods, payment context, storefront paths, content pages, and integrations may all need planning beyond basic record movement.

**Does choosing Gambio Cloud reduce migration risk?**

Gambio Cloud can reduce hosting and maintenance responsibility, but it does not remove catalog, order, customer, tax, shipping, payment, SEO, or storefront validation work. The operating model becomes easier in some areas, but the migrated result still needs to be tested.

**When does self-hosted Gambio increase migration complexity?**

Self-hosted Gambio increases complexity when the merchant needs custom development, technical access, hosting control, module compatibility, integration work, or server-level responsibility. These needs should be reviewed before choosing the migration approach.

**Are product variants always straightforward to migrate to Gambio?**

Not always. Variant-heavy products should be reviewed carefully, especially when the source platform uses option-level pricing, option-level stock, bundles, custom fields, or app-controlled product behavior. Demo Migration should include representative variant products.

**When should Custom Service be reviewed for Gambio migration?**

Custom Service should be reviewed when the source store includes Custom Platform data, unsupported extension data, third-party identifiers, custom fields, bespoke product or checkout logic, external integrations, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment beyond standard service capability.
