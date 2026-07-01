# VirtueMart Pre-Migration Preparation Checklist

VirtueMart preparation should begin with the structures that make the future Joomla store usable, not only with a count of products, customers, and orders. VirtueMart is a Joomla-connected commerce environment, so the migration plan has to account for both commerce records and the Joomla site layer that presents those records to shoppers.

A strong preparation process gives the migration team enough evidence to understand product relationships, custom fields, child products, shopper groups, prices, taxes, payment and shipment logic, multilingual content, order history, storefront routes, modules, templates, and extension-owned data before the first meaningful validation step.

### What VirtueMart Preparation Needs to Prove <a href="#what-virtuemart-preparation-needs-to-prove" id="what-virtuemart-preparation-needs-to-prove"></a>

VirtueMart preparation should prove that the store’s commercial meaning can be understood before data is moved. A product record is not only a product name and SKU. It may depend on custom fields, child-product relationships, shopper-group pricing, calculation rules, stock behavior, manufacturer data, categories, media, downloadable files, or Joomla display logic.

The goal is to prepare usable evidence. The merchant should be able to explain what the important source records mean, which records must become standard VirtueMart data, which parts belong to Joomla configuration, and which requirements need Add-ons or Custom Service review.

| Preparation question                       | What the answer should clarify                                                                                      | Why it matters for VirtueMart                                                                       |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| What kind of products does the store sell? | Simple products, variants, child products, downloadable products, grouped products, or custom-field-driven products | VirtueMart product meaning often depends on relationships and custom fields, not only product rows. |
| How are prices determined?                 | Base prices, shopper-group prices, tax handling, discounts, currencies, and calculation rules                       | Price meaning can be lost if commercial rules are treated as ordinary product fields.               |
| How do customers buy?                      | Shopper groups, account behavior, checkout fields, payment methods, shipment methods, and order-status flow         | Customer and order records need operational context after migration.                                |
| How is the storefront assembled?           | Joomla menus, aliases, modules, templates, overrides, category pages, and product-page layout                       | Migrated data can be correct but still fail as a storefront if the Joomla layer is not ready.       |
| What data is custom or extension-owned?    | Plugin fields, integration identifiers, custom database records, or modified VirtueMart behavior                    | Unsupported or bespoke data may require Custom Service rather than standard preparation.            |

### Confirm the Joomla and VirtueMart Target Environment <a href="#confirm-the-joomla-and-virtuemart-target-environment" id="confirm-the-joomla-and-virtuemart-target-environment"></a>

VirtueMart runs inside Joomla, so the target environment should be confirmed before migration planning becomes detailed. The Joomla version, VirtueMart version, hosting environment, PHP and database compatibility, template framework, module positions, language setup, user access model, and installed extensions can all influence the final result.

Preparation should include a basic target inventory. That inventory does not need to be overly complex, but it should be specific enough to prevent assumptions during validation. The merchant should know whether the target store is a fresh VirtueMart installation, an existing Joomla site with VirtueMart already configured, or a broader rebuild that combines data migration with theme, module, template, and extension work.

| Target area                 | Confirm before migration                                                                                          | Risk if ignored                                                                              |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Joomla foundation           | Joomla version, user setup, menus, languages, access levels, template framework, and required extensions          | Store data may arrive into a target environment that cannot display or operate it correctly. |
| VirtueMart installation     | VirtueMart version, store configuration, currencies, taxes, order statuses, payment plugins, and shipment plugins | Validation may confuse missing configuration with migration failure.                         |
| Template and modules        | Product layout, category layout, cart module, search/filter modules, checkout presentation, and overrides         | Products may exist but appear incomplete, broken, or commercially misleading.                |
| Language and currency setup | Required languages, translations, currency behavior, regional display, and fallback expectations                  | Multilingual or multicurrency records may appear incomplete if the target is not prepared.   |
| Extension stack             | Payment, shipment, SEO, analytics, ERP, CRM, inventory, subscription, or custom extensions                        | Plugin-owned behavior may need separate review outside standard data migration.              |

### Prepare Product, Category, and Catalog Evidence <a href="#prepare-product-category-and-catalog-evidence" id="prepare-product-category-and-catalog-evidence"></a>

VirtueMart catalog preparation should separate ordinary product fields from the structures that give products selling meaning. Good evidence includes product types, category depth, manufacturer relationships, media behavior, inventory rules, child products, custom fields, downloadable files, and product-page expectations.

The sample set for Demo Migration should not include only clean products. It should include products that expose real complexity. A useful sample often includes a simple product, a product with child products, a product with custom fields, a product with several categories, a product with manufacturer data, a product with multiple media files, a product with discount or tax behavior, a downloadable product, and a product that represents a high-value selling path.

| Product sample              | Evidence to prepare                                                                                    | Validation purpose                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- |
| Simple product              | SKU, name, price, stock, category, manufacturer, image, description                                    | Confirms baseline product migration and display.                        |
| Child-product structure     | Parent product, child products, SKU differences, price differences, stock behavior, selectable choices | Tests whether variant-like meaning becomes usable VirtueMart structure. |
| Custom-field product        | Field names, field purpose, display location, shopper selection, price modifier, plugin dependency     | Prevents functional fields from being reduced to incomplete notes.      |
| Discounted or taxed product | Price, tax rule, discount, currency, shopper group, calculation order                                  | Tests commercial interpretation rather than only product visibility.    |
| Media-heavy product         | Main image, gallery, downloadable files, documents, external files                                     | Confirms selling assets remain usable after migration.                  |

Categories should also be prepared carefully. VirtueMart categories may support storefront discovery, but Joomla menus and routes can shape how shoppers and search engines reach those pages. Preparation should identify important category paths, SEO-sensitive pages, redirected URLs, products assigned to multiple categories, and any categories that should be excluded, merged, or cleaned before migration.

### Prepare Custom Fields, Child Products, and Product Relationship Logic <a href="#prepare-custom-fields-child-products-and-product-relationship-logic" id="prepare-custom-fields-child-products-and-product-relationship-logic"></a>

VirtueMart custom fields are often the area where migration planning needs the most discipline. A custom field may be a simple specification, a shopper-selectable option, a pricing modifier, a related-product reference, a downloadable file, a display note, or a plugin-owned behavior. The same label can carry different meanings across stores.

Preparation should document what each important field does, not only where it appears. If a field affects price, stock, checkout, order-line readability, product comparison, or buyer choice, it should be treated as functional data during review.

| VirtueMart structure       | Preparation focus                                                                            | Possible service implication                                                                       |
| -------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Custom fields              | Purpose, source equivalent, display behavior, price effect, order-line effect                | Supported mapping may be enough when the meaning is simple; bespoke logic may need Custom Service. |
| Child products             | Parent relationship, child SKUs, stock, price differences, category behavior, media behavior | Requires clear sample validation because source platforms model variants differently.              |
| Shopper-selectable choices | Options customers choose before purchase                                                     | Must remain understandable on product pages and historical order lines.                            |
| Related products           | Relationship type, display purpose, and business importance                                  | May need separate mapping or manual configuration depending on source structure.                   |
| Plugin-generated fields    | Extension owner, database location, and expected output                                      | Often requires Custom Service review if the data is not standard VirtueMart scope.                 |

Child-product relationships should be prepared from real examples. A source store may model variants as configurable products, option combinations, separate SKUs, grouped products, matrix records, or app-generated structures. The migration plan should not assume that every source variant structure becomes a perfect VirtueMart child-product structure without review.

### Prepare Shopper Groups, Customers, and Account Context <a href="#prepare-shopper-groups-customers-and-account-context" id="prepare-shopper-groups-customers-and-account-context"></a>

VirtueMart stores can use shopper groups to control commercial behavior. Shopper groups may influence prices, tax display, payment access, shipment access, discounts, catalog visibility, or B2B/B2C segmentation. Preparation should identify each group, its purpose, and whether customers must remain assigned to that group after migration.

Customer preparation should include registered customers, guest orders, billing addresses, shipping addresses, company details, tax identifiers, contact information, account status, Joomla user relationship, and order-history expectations. If the source platform separates users, customers, buyers, companies, or account contacts, those relationships should be reviewed before migration.

| Customer evidence        | What to include                                                               | Why it matters                                                            |
| ------------------------ | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Shopper groups           | Group name, business purpose, pricing effect, access effect, sample customers | Preserves commercial segmentation.                                        |
| Joomla user relationship | Login identity, email, username, account status, access expectations          | VirtueMart customer behavior depends on Joomla user context.              |
| Addresses                | Billing, shipping, company, tax ID, region, country, phone, default address   | Order support and checkout continuity depend on address quality.          |
| Customer samples         | Retail buyer, B2B buyer, guest order, international buyer, repeat buyer       | Validates multiple customer scenarios, not only one clean account.        |
| Privacy and cleanup      | Inactive accounts, test accounts, duplicate customers, outdated addresses     | Prevents unnecessary or poor-quality data from entering the target store. |

### Prepare Orders, Payment, Shipment, Tax, and Calculation Rules <a href="#prepare-orders-payment-shipment-tax-and-calculation-rules" id="prepare-orders-payment-shipment-tax-and-calculation-rules"></a>

VirtueMart order history should remain readable for customer service, accounting reference, warranty review, refund questions, and operational continuity. Preparation should include order numbers, dates, statuses, products, product options, discounts, taxes, currencies, payment methods, shipment methods, addresses, customer groups, invoices, notes, and any external references.

Payment and shipment behavior require special attention because historical records and live configuration are different concerns. Migrating a payment method name is not the same as configuring a payment gateway for future checkout. Preserving a shipment label in order history is not the same as recreating source shipping logic in VirtueMart.

| Area                   | Evidence to prepare                                                                            | Validation question                                                                        |
| ---------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Orders                 | Statuses, products, options, totals, discounts, taxes, currencies, payment and shipment labels | Can staff interpret historical orders accurately after migration?                          |
| Payment context        | Payment method names, transaction references, captured status, refunds, gateway notes          | Are historical references preserved without implying live gateway configuration?           |
| Shipment context       | Shipment method names, rates, tracking references, regions, carrier notes                      | Are historical shipment details readable and operationally useful?                         |
| Calculation rules      | Tax, discount, fee, shopper-group, country, region, and currency behavior                      | Which rules are historical records, configuration tasks, Add-ons, or Custom Service items? |
| Invoices and documents | Invoice numbers, documents, PDF expectations, legal reference needs                            | Which documents must be preserved, recreated, or treated as external records?              |

### Prepare Joomla Storefront, SEO, Multilingual, and Template Dependencies <a href="#prepare-joomla-storefront-seo-multilingual-and-template-dependencies" id="prepare-joomla-storefront-seo-multilingual-and-template-dependencies"></a>

VirtueMart migration readiness also depends on the Joomla storefront. Products and categories may need Joomla menus, aliases, SEF URL behavior, redirects, modules, search/filter presentation, cart modules, template overrides, and language configuration. These elements shape how migrated data becomes a usable storefront.

SEO-sensitive pages should be identified before validation. The merchant should prepare important product URLs, category URLs, landing pages, redirects, canonical expectations, metadata, and search-entry pages. If the new VirtueMart site changes routes, validation should include both content accuracy and discoverability risk.

Multilingual stores need language-specific samples. Preparation should include translated product names, descriptions, categories, custom fields, menus, modules, payment and shipment labels, checkout labels, and fallback behavior. Multilingual readiness is weak if validation only checks the default language.

### Prepare Add-ons, Custom Service, and Demo Migration Samples <a href="#prepare-add-ons-custom-service-and-demo-migration-samples" id="prepare-add-ons-custom-service-and-demo-migration-samples"></a>

Preparation should classify requirements before Full Migration. Some needs may fit standard supported migration. Some may fit Add-ons. Some may require Custom Service because they involve unsupported extension data, Custom Platform sources, bespoke transformations, custom migration logic adjustment, or non-standard VirtueMart behavior.

Demo Migration samples should be selected intentionally. Random records rarely expose the risks that matter most in VirtueMart projects. A strong sample includes the records most likely to prove catalog logic, pricing logic, customer segmentation, order readability, storefront continuity, and custom-data boundaries.

| Demo Migration sample                                 | Why to include it                               | Decision it supports                                                    |
| ----------------------------------------------------- | ----------------------------------------------- | ----------------------------------------------------------------------- |
| Child-product or custom-field product                 | Tests product relationship and selection logic  | Confirms whether standard handling is enough.                           |
| Shopper-group customer                                | Tests customer segmentation and pricing context | Confirms whether customer group meaning is preserved.                   |
| Order with discounts, tax, shipment, and payment data | Tests historical order readability              | Confirms whether support and accounting teams can use migrated history. |
| Multilingual product/category                         | Tests translated content and language behavior  | Confirms whether multilingual setup needs more work.                    |
| Plugin-owned or custom data example                   | Tests data outside ordinary records             | Confirms whether Custom Service review is needed.                       |

### Conclusion <a href="#conclusion" id="conclusion"></a>

VirtueMart preparation should focus on operating meaning. Products, child products, custom fields, shopper groups, calculation rules, orders, payments, shipments, taxes, multilingual content, and Joomla storefront dependencies all need evidence before migration planning can be trusted.

A prepared VirtueMart project gives validation teams real examples of the store’s commercial complexity. If the preparation reveals unsupported extension data, custom product logic, unusual shopper-group behavior, complex calculation rules, or Joomla presentation work that standard migration cannot cover, the scope should be reviewed before Full Migration begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared before migrating to VirtueMart?**

Prepare Joomla and VirtueMart target details, product and category samples, custom fields, child products, shopper groups, customer and order examples, payment and shipment context, tax and calculation rules, multilingual content, storefront routes, modules, templates, and any custom or extension-owned data.

**Why are VirtueMart custom fields important during preparation?**

Custom fields may control shopper selections, price changes, technical specifications, related products, downloadable files, or plugin behavior. Their business purpose should be documented before migration so they are not treated as ordinary notes.

**Should payment and shipping methods be prepared as migrated data or configuration?**

Both contexts should be separated. Historical payment and shipment labels may need to remain readable in old orders, while live payment gateways and shipment rules usually require VirtueMart configuration or plugin setup.

**What should Demo Migration samples include for VirtueMart?**

Demo Migration should include complex products, child products, custom-field products, shopper-group customers, orders with tax and discounts, payment and shipment examples, multilingual records, and custom or plugin-owned data samples.

**When should Custom Service be reviewed before VirtueMart migration?**

Custom Service should be reviewed when the project depends on Custom Platform data, unsupported extensions, custom database fields, bespoke product logic, complex shopper-group rules, plugin-owned records, or custom migration logic adjustment.
