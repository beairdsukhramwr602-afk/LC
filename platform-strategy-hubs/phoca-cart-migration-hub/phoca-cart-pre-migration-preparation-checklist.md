# Phoca Cart Pre-Migration Preparation Checklist

Preparation for a Phoca Cart migration should begin with the operating model the new Joomla store must support. Phoca Cart is not only a product-and-order destination. It can involve Joomla categories and menus, product attributes and options, specifications, parameters, stock behavior, downloadable products, customer groups, coupons, reward points, tax rules, shipping and payment plugins, invoice expectations, POS-related workflows, multilingual and multicurrency configuration, modules, template overrides, and other Phoca or Joomla extensions.

Phoca Cart 6.1.0 is the current official stable release, so preparation should normally evaluate target behavior against that release. Some merchants still operate older Phoca Cart installations, and Next-Cart can support migration projects from or to Phoca Cart across versions when the selected migration path and project requirements are reviewed correctly. Older operational versions should be prepared with version-specific evidence rather than assumed to behave exactly like the current release.

### Preparation Priorities Before Migration <a href="#preparation-priorities-before-migration" id="preparation-priorities-before-migration"></a>

A strong preparation process should answer four practical questions before the migration process begins:

1. Which Phoca Cart version and Joomla environment will the target store use?
2. Which source data carries selling, pricing, tax, shipping, payment, loyalty, language, or storefront meaning?
3. Which behavior belongs to migrated data, and which behavior must be configured inside Joomla, Phoca Cart, templates, modules, or plugins?
4. Which samples should be used during Demo Migration to prove the migration result before Full Migration?

| Preparation area                | What to confirm                                                                                                | Why it matters                                                                                                            |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Version and environment         | Phoca Cart version, Joomla version, PHP/database environment, template framework, installed Phoca extensions   | Older and current Phoca Cart installations may differ in behavior, extension compatibility, and administrative structure. |
| Catalog structure               | Products, categories, attributes, options, specifications, parameters, stock, downloads, images, manufacturers | Catalog meaning affects shopper selection, filtering, product comparison, inventory, and administration after migration.  |
| Buyer and pricing logic         | Customers, customer groups, group prices, coupons, reward points, discounts, access expectations               | Buyer-specific behavior can change the commercial meaning of migrated products and orders.                                |
| Operational configuration       | Tax, shipping, payment, invoices, order statuses, POS expectations, email/document templates                   | These areas often require target configuration rather than record movement alone.                                         |
| Joomla storefront layer         | Menus, modules, templates, overrides, aliases, language routing, category paths, product pages                 | A correct data result can still feel incomplete if Joomla presentation and discovery are not ready.                       |
| Custom and extension-owned data | Custom fields, third-party plugins, integrations, import/export workflows, bespoke code                        | Non-standard behavior may require Add-on review, Custom Service, or separate implementation work.                         |

### 1. Confirm the Intended Phoca Cart and Joomla Version <a href="#id-1-confirm-the-intended-phoca-cart-and-joomla-version" id="id-1-confirm-the-intended-phoca-cart-and-joomla-version"></a>

Version confirmation should happen before catalog mapping, Demo Migration sample selection, or service-path decisions. A merchant migrating into Phoca Cart 6.1.0 may need different preparation from a merchant targeting an older operational installation or moving from an older Phoca Cart version to a newer one.

#### Confirm the target store environment <a href="#confirm-the-target-store-environment" id="confirm-the-target-store-environment"></a>

Document the Joomla version, Phoca Cart version, PHP and database environment, active template, template framework, extension stack, and any installed Phoca Cart add-on extensions. Also confirm whether the future store will use Bootstrap, UIkit, custom template overrides, multilingual structure, multicurrency display, POS-related features, catalog mode, or standard cart behavior.

#### Confirm whether older-version behavior matters <a href="#confirm-whether-older-version-behavior-matters" id="confirm-whether-older-version-behavior-matters"></a>

Older Phoca Cart versions may remain operational when the Joomla site and extension stack continue to work, but older behavior should not be treated as automatically equivalent to Phoca Cart 6.1.0. If the source or target uses an older version, collect screenshots, exports, configuration notes, sample records, and extension lists from that exact installation.

#### Confirm the selected migration path <a href="#confirm-the-selected-migration-path" id="confirm-the-selected-migration-path"></a>

The selected migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased service license. For Phoca Cart projects, that direction may involve moving from another supported platform into Phoca Cart, moving out of Phoca Cart, or moving from an older Phoca Cart installation into a newer Phoca Cart installation. The migration direction should be confirmed before preparing records and samples.

### 2. Prepare the Product and Catalog Structure <a href="#id-2-prepare-the-product-and-catalog-structure" id="id-2-prepare-the-product-and-catalog-structure"></a>

Catalog preparation should focus on how products are sold and discovered, not only how many products exist. Phoca Cart can involve several product-detail layers, and those layers should be separated before migration so they can be interpreted correctly.

#### Products, categories, and manufacturers <a href="#products-categories-and-manufacturers" id="products-categories-and-manufacturers"></a>

Prepare a clean inventory of products, categories, manufacturers, category depth, product placement, product aliases, product status, pricing, images, product descriptions, product relationships, and any source-side structure used for discovery. Products that appear in more than one category or depend on special routes should be marked for validation.

#### Attributes, options, specifications, and parameters <a href="#attributes-options-specifications-and-parameters" id="attributes-options-specifications-and-parameters"></a>

Source platforms may combine product-choice, product-description, product-filter, and product-display information in ways that do not match Phoca Cart directly. Prepare representative examples for each product-detail layer:

| Product-detail layer | Preparation focus                                                    | Sample records to choose                                                                             |
| -------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Attributes           | Product information that may help describe, filter, or compare items | Technical products, products with detailed characteristics, products used in comparison or filtering |
| Options              | Shopper-selectable choices or configuration values                   | Products with size, color, package, add-on, option-price, or option-stock behavior                   |
| Specifications       | Structured information that explains product qualities               | Products with technical tables, measurement data, material details, or product-grade information     |
| Parameters           | Display or behavior-related product settings                         | Products whose visibility, layout, availability, or presentation depends on source-side settings     |

The exact use of these layers should be confirmed against the target Phoca Cart installation. The goal is not to force every source field into a matching label, but to preserve the commercial meaning customers and administrators rely on.

#### Stock, product availability, and downloadable products <a href="#stock-product-availability-and-downloadable-products" id="stock-product-availability-and-downloadable-products"></a>

Prepare products with ordinary stock, low stock, out-of-stock status, unlimited availability, disabled availability, downloadable files, mixed physical/digital behavior, and any POS-related inventory expectations. For downloadable products, gather file-delivery rules, access behavior, order-completion requirements, and customer download expectations.

#### Images and media <a href="#images-and-media" id="images-and-media"></a>

Document main images, gallery images, product thumbnails, missing images, option-specific imagery, and any modern format expectations. If the source store uses manual image naming, external media paths, or extension-generated image handling, gather examples before migration.

### 3. Prepare Customers, Groups, Benefits, and Order Context <a href="#id-3-prepare-customers-groups-benefits-and-order-context" id="id-3-prepare-customers-groups-benefits-and-order-context"></a>

Customer and order preparation should preserve commercial usefulness. Names, emails, and order numbers are not enough if buyer groups, prices, discounts, reward points, tax, shipping, payment, and invoice context become unclear.

#### Customer groups and buyer segmentation <a href="#customer-groups-and-buyer-segmentation" id="customer-groups-and-buyer-segmentation"></a>

Prepare every customer group that affects product prices, access, discounts, rewards, tax behavior, or order handling. Include at least one customer from each important group in Demo Migration samples. For B2B, wholesale, loyalty, member, or restricted-access stores, customer-group examples are critical.

#### Coupons, reward points, discounts, and benefits <a href="#coupons-reward-points-discounts-and-benefits" id="coupons-reward-points-discounts-and-benefits"></a>

List active and historical coupons, reward point behavior, customer benefits, discount rules, and promotion examples. Identify whether these rules need to be preserved as historical order context, configured for future selling, or reviewed as custom behavior.

#### Order samples <a href="#order-samples" id="order-samples"></a>

Select orders that reveal operational meaning:

* recent orders and older orders
* orders with multiple products
* orders with attributes, options, or specifications visible in line items
* orders with coupons, discounts, reward points, or special pricing
* orders with tax and shipping charges
* orders using different payment methods
* orders with downloadable products
* refunded, cancelled, pending, completed, or unusual order statuses when available
* orders tied to important customer groups

#### Invoices, documents, and POS-related expectations <a href="#invoices-documents-and-pos-related-expectations" id="invoices-documents-and-pos-related-expectations"></a>

If invoices, receipt behavior, POS workflows, or document templates matter, collect examples before migration. Historical orders may need to remain readable for customer service, accounting reference, warranty questions, or fulfillment review even when future invoice behavior is configured separately in Phoca Cart.

### 4. Prepare Tax, Shipping, Payment, and Checkout Evidence <a href="#id-4-prepare-tax-shipping-payment-and-checkout-evidence" id="id-4-prepare-tax-shipping-payment-and-checkout-evidence"></a>

Tax, shipping, payment, and checkout behavior often combines data, rules, plugins, zones, rates, templates, and business policies. These areas should be prepared as operating behavior, not only as fields.

#### Tax and geographic rules <a href="#tax-and-geographic-rules" id="tax-and-geographic-rules"></a>

Document tax rates, tax zones, country/region behavior, tax-inclusive or tax-exclusive display expectations, product-specific tax behavior, customer-group tax exceptions, and tax recapitulation expectations. Cross-border stores and multilingual/multicurrency stores should be especially careful because tax meaning may depend on location, currency, and language context.

#### Shipping methods and payment plugins <a href="#shipping-methods-and-payment-plugins" id="shipping-methods-and-payment-plugins"></a>

Prepare a list of shipping methods, payment methods, plugin names, carrier relationships, offline payment options, conditional shipping rules, free-shipping thresholds, and payment status behavior. If the source store depends on a third-party plugin, marketplace connector, external service, or custom integration, gather configuration screenshots and sample orders.

#### Checkout and account behavior <a href="#checkout-and-account-behavior" id="checkout-and-account-behavior"></a>

Document guest checkout, registered checkout, required customer information, address fields, terms conditions, checkout steps, email behavior, and any custom fields or custom logic used during checkout. If the migration requires preserving custom checkout data or external payment references, review whether Advanced Data Mapping, Advanced Data Configure, or Custom Service is needed.

### 5. Prepare Joomla Storefront, Multilingual, and Template Context <a href="#id-5-prepare-joomla-storefront-multilingual-and-template-context" id="id-5-prepare-joomla-storefront-multilingual-and-template-context"></a>

A Phoca Cart store is also a Joomla site. Storefront preparation should include Joomla menus, modules, routes, templates, overrides, languages, content, and extension placement.

#### Menus, modules, and routes <a href="#menus-modules-and-routes" id="menus-modules-and-routes"></a>

Identify the most important product URLs, category URLs, menu items, landing pages, cart paths, checkout paths, account areas, content links, and search/discovery paths. Record which paths need redirect planning, which menu items must be recreated, and which modules support product discovery.

#### Templates and overrides <a href="#templates-and-overrides" id="templates-and-overrides"></a>

Document the active Joomla template, template framework, module positions, custom overrides, CSS/JavaScript customizations, and any layout changes made for Phoca Cart. If the target store uses a different template framework or a current Phoca Cart release with newer frontend behavior, layout expectations should be reviewed before Demo Migration is judged.

#### Multilingual and multicurrency structure <a href="#multilingual-and-multicurrency-structure" id="multilingual-and-multicurrency-structure"></a>

Prepare language lists, translated product names and descriptions, translated categories, language-specific aliases, menu associations, currency lists, exchange-rate expectations, and any language/currency switching behavior. A multilingual store should validate the relationship between translated Phoca Cart records and Joomla language routing.

### 6. Prepare Custom, Extension-Owned, and Integration Data <a href="#id-6-prepare-custom-extension-owned-and-integration-data" id="id-6-prepare-custom-extension-owned-and-integration-data"></a>

Custom behavior should be identified before migration, not discovered during final validation. Phoca Cart can be extended through plugins, modules, template overrides, import/export processes, feeds, custom code, and integrations. Some source behavior may not have a direct standard destination.

#### What to inventory <a href="#what-to-inventory" id="what-to-inventory"></a>

Prepare an inventory of:

* Phoca Cart extensions and plugins
* Joomla plugins connected to commerce behavior
* custom fields or database columns
* import/export workflows
* XML or CSV feed processes
* accounting, ERP, POS, marketplace, payment, shipping, tax, email, analytics, or fulfillment integrations
* custom modules or custom layouts
* third-party identifiers used outside the store
* manual workflows that depend on exported records or order documents

#### When to escalate before execution <a href="#when-to-escalate-before-execution" id="when-to-escalate-before-execution"></a>

Custom Service should be reviewed when the project includes Custom Platform data, unsupported extension data, custom database structures, bespoke product logic, external identifiers, custom plugin-owned fields, older-version transformation, or any requirement that needs custom migration logic adjustment. Add-ons may help with filtering, mapping, or configuration when the requested outcome fits Standard Add-on capability; broader transformation belongs in Custom Service.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

The preparation sequence should move from environment clarity to data samples, then to service-path confirmation. Skipping directly to record counts can hide the structures that matter most.

| Step | Preparation action                                                                             | Output before migration                                   |
| ---- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| 1    | Confirm Phoca Cart version, Joomla version, template, and extension stack                      | Target environment profile                                |
| 2    | Identify the selected migration path and service model expectation                             | Clear migration direction and responsibility boundary     |
| 3    | Review products, categories, attributes, options, specifications, stock, downloads, and images | Catalog structure map and sample list                     |
| 4    | Review customers, groups, coupons, rewards, orders, invoices, tax, shipping, and payment       | Operational data map and sample list                      |
| 5    | Review menus, modules, templates, routes, languages, currencies, and storefront paths          | Joomla storefront dependency map                          |
| 6    | Inventory custom fields, plugins, integrations, import/export workflows, and custom code       | Escalation list for Add-on or Custom Service review       |
| 7    | Run Demo Migration with representative samples                                                 | Evidence for whether the migration approach is sufficient |

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should test meaning, not only movement. The sample set should include ordinary records and edge records that expose how Phoca Cart will behave after migration.

| Sample type                      | Include examples of                                                                                                                                    | What the sample should prove                                                     |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| Products                         | Simple products, products with options, products with attributes, specification-heavy products, downloadable products, products with stock differences | Product meaning remains sellable, searchable, and administratively useful.       |
| Categories and discovery         | Main categories, deep categories, products in multiple locations, filtered or specification-driven discovery                                           | Storefront navigation and product organization remain understandable.            |
| Customers                        | Guest customers, registered customers, important customer groups, loyalty or B2B customers                                                             | Buyer identity, group context, and account meaning remain clear.                 |
| Orders                           | Discounted orders, reward-related orders, tax/shipping/payment variations, downloadable-product orders, unusual statuses                               | Order history remains readable for service, accounting, fulfillment, and review. |
| Configuration-sensitive behavior | Tax examples, shipping examples, payment examples, invoice examples, POS-related examples                                                              | Behavior that requires setup is separated from migrated data.                    |
| Joomla storefront context        | Important URLs, menu items, modules, template-specific pages, multilingual pages                                                                       | Storefront continuity is not judged by records alone.                            |
| Custom or extension-owned data   | Custom fields, third-party identifiers, plugin-owned records, integration-dependent records                                                            | Custom Service or Add-on needs are identified early.                             |

### What to Escalate Before Migration <a href="#what-to-escalate-before-migration" id="what-to-escalate-before-migration"></a>

Some preparation findings should change the migration approach before execution begins. Escalation is not a failure; it is how the project avoids discovering structural gaps after Full Migration.

#### Review Add-ons when filtering, mapping, or configuration is the main need <a href="#review-add-ons-when-filtering-mapping-or-configuration-is-the-main-need" id="review-add-ons-when-filtering-mapping-or-configuration-is-the-main-need"></a>

The Data Filter Add-on, Advanced Data Mapping, and Advanced Data Configure may help when the migration needs selective record handling, clearer field relationships, or data configuration within available settings and supported behavior. Add-ons should not be used to describe broad bespoke transformation.

#### Review Managed Service when execution responsibility is the main need <a href="#review-managed-service-when-execution-responsibility-is-the-main-need" id="review-managed-service-when-execution-responsibility-is-the-main-need"></a>

Managed Service may be safer when the data structure is mostly standard but the merchant wants Next-Cart-led execution using standard service capability and purchased Add-ons. Managed Service does not automatically include customization.

#### Review Custom Service when the structure is non-standard <a href="#review-custom-service-when-the-structure-is-non-standard" id="review-custom-service-when-the-structure-is-non-standard"></a>

Custom Service should be reviewed when the migration involves Custom Platform handling, unsupported extension data, custom fields, older-version transformation, plugin-owned records, third-party identifiers, integration restructuring, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Phoca Cart preparation should confirm more than record availability. The strongest preparation identifies the Phoca Cart and Joomla versions, maps catalog structure, separates attributes from options and specifications, documents customer groups and benefit logic, gathers tax, shipping, payment, invoice, and order examples, and connects store data with Joomla menus, modules, templates, languages, currencies, and extensions.

Phoca Cart 6.1.0 is the current official stable release, but older operational installations may require version-specific review. A migration plan should therefore prove what the selected target installation needs, what the source store actually contains, and which requirements belong to migrated data, Joomla configuration, Phoca Cart setup, Add-ons, Managed Service, or Custom Service.

Before running Full Migration to Phoca Cart, use Demo Migration to test representative products, customers, orders, customer groups, discounts, reward points, tax, shipping, payment, downloadable files, multilingual records, and Joomla storefront paths. If the source store depends on older-version behavior, unsupported extension data, custom fields, third-party identifiers, or custom logic, contact Next-Cart through Live Chat so the migration path, Add-ons, and service model can be reviewed before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to Phoca Cart?**

Confirm the target Phoca Cart version, Joomla version, template, extension stack, and selected migration path first. Catalog mapping, service selection, and Demo Migration samples should be based on the actual target environment rather than a generic assumption about Phoca Cart behavior.

**Should older Phoca Cart versions be handled differently from Phoca Cart 6.1.0?**

Yes. Older Phoca Cart installations may remain operational, but their behavior can differ from Phoca Cart 6.1.0. If the migration project targets or comes from an older version, prepare screenshots, configuration notes, extension lists, sample records, and version-specific validation expectations.

**Which product samples are most useful for Demo Migration?**

Use products that reveal structure: simple products, products with attributes, products with options, specification-heavy products, products with stock differences, downloadable products, products in multiple categories, and products controlled by custom fields or extensions.

**Do tax, shipping, and payment settings migrate automatically?**

Not always. Some historical order context may be migrated where supported, while future tax, shipping, payment, invoice, and checkout behavior may need to be configured in Phoca Cart. Configuration-sensitive behavior should be documented before Demo Migration.

**When should Custom Service be reviewed for a Phoca Cart migration?**

Custom Service should be reviewed when the project involves Custom Platform data, unsupported extension data, custom fields, older-version transformation, third-party identifiers, plugin-owned records, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment beyond standard service capability.
