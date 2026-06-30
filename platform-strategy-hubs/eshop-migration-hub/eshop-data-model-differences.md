# EShop Data Model Differences

EShop by Ossolution Team stores commercial meaning across Joomla structure, EShop catalog records, checkout behavior, configuration records, modules, templates, plugins, multilingual content, and possible custom development. A migration into EShop therefore needs more than field matching. It needs a clear interpretation of what each source value is supposed to do after launch.

The same source field can mean different things depending on the store. A value labeled as an attribute may be a shopper choice, a filter value, a technical specification, a personalization input, or a value created by an app. A customer group may be a reporting label in one store and a pricing rule in another. A shipping method stored on an order may be historical evidence, while a shipping plugin is live checkout configuration. These distinctions decide whether a record can be migrated through standard handling, needs Add-ons, or requires Custom Service review.

### What Changes When Data Moves Into EShop <a href="#what-changes-when-data-moves-into-eshop" id="what-changes-when-data-moves-into-eshop"></a>

EShop is a Joomla shopping cart extension. That identity affects the data model because the store is not isolated from the Joomla site around it. Product and order records belong to EShop, but store discovery, menus, modules, templates, aliases, metadata, multilingual routing, and page presentation also depend on Joomla implementation decisions.

A useful way to evaluate EShop data is to separate commercial records from site assembly and live behavior. Commercial records explain what was sold, who bought it, and how the store organized its catalog. Site assembly explains how shoppers reach those records and how the storefront presents them. Live behavior explains how checkout, tax, shipping, payment, currency, status, and plugin logic should operate after launch.

| Data area                  | What changes in EShop planning                                                                                                                     | Migration implication                                                                           |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Product records            | Products can include options, attributes, manufacturers, images, attachments, extra tabs, labels, reviews, related items, and downloadable assets. | Product mapping must preserve selling meaning, not only names, SKUs, prices, and descriptions.  |
| Catalog organization       | Categories, manufacturers, filters, tags, metadata, and menu paths may work together.                                                              | Catalog validation must check discovery and SEO paths, not only record presence.                |
| Shopper choice             | Options can affect selection, price, SKU meaning, image choice, and order-line context.                                                            | Source variants and options need meaning-based interpretation before mapping.                   |
| Informational values       | Attributes, custom fields, tabs, and attachments may describe products without controlling purchase choice.                                        | Specifications should not be confused with selectable options.                                  |
| Customer and order history | Customers, customer groups, addresses, order statuses, payment context, shipping context, coupons, and vouchers carry operational evidence.        | Historical data must remain useful for support, reporting, and repeat-customer recognition.     |
| Configuration records      | Tax classes, geo zones, currencies, stock statuses, length units, weight units, shipping methods, and payment plugins support live behavior.       | Configuration usually needs target setup and verification, not blind record transfer.           |
| Joomla presentation        | Menus, modules, templates, layout overrides, aliases, page titles, metadata, and multilingual structure shape storefront output.                   | Data can be correct while the customer-facing store still needs Joomla implementation review.   |
| Custom behavior            | Custom fields, custom checkout data, plugins, integrations, and bespoke database values may sit outside standard records.                          | These areas may need Add-ons or Custom Service depending on ownership and transformation needs. |

This separation prevents a common migration mistake: treating EShop as a single product/order database. EShop is better understood as commerce data inside a Joomla site architecture.

### Product and Catalog Data Differences <a href="#product-and-catalog-data-differences" id="product-and-catalog-data-differences"></a>

Products in EShop can carry several layers of meaning. A straightforward item may need only product name, SKU, price, description, category, image, tax class, stock status, and visibility. A more complex item may include options, attributes, manufacturers, downloadable files, extra tabs, product labels, custom fields, reviews, related products, size or weight data, customer group pricing, discounts, and language-specific content.

The migration plan should identify which of these layers are essential for the store to remain usable. A product that appears in the administration area but loses its option structure, manufacturer association, additional tabs, attachment, or review context may not be commercially complete.

| Source product pattern                                        | EShop interpretation                                                    | Review question                                                                          |
| ------------------------------------------------------------- | ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Simple product with one SKU and one selling price             | Standard product record with ordinary catalog fields.                   | Are category, image, tax, stock, and SEO details enough for launch?                      |
| Product with color, size, package, or personalization choices | Potential EShop option structure.                                       | Does the choice affect price, SKU, image, stock, or order-line meaning?                  |
| Product with technical specifications                         | Potential attributes, attribute groups, custom fields, or product tabs. | Should the value help shoppers compare products or choose before checkout?               |
| Product with many images or downloadable assets               | Product media, attachments, or downloadable product handling.           | Which files must remain visible, accessible, and attached to the correct product?        |
| Product organized by brand, supplier, or maker                | Manufacturer relationship or catalog classification.                    | Is manufacturer a simple label, a filter path, an SEO page, or an operational reference? |
| Product with reviews, labels, related items, or tabs          | Supporting catalog context.                                             | Which supporting records affect buyer confidence or merchandising?                       |

Category data also needs care. EShop supports multi-level categories, but source stores often use categories for several purposes at once: navigation, SEO landing pages, merchandising groups, hidden collections, seasonal campaigns, or app-created product sets. The migration decision should distinguish structural categories from temporary merchandising categories.

Manufacturers create another layer of meaning. In some stores, a manufacturer is a public brand. In others, it is a supplier reference, an internal procurement label, or a filterable catalog value. The migration plan should decide whether manufacturer data must remain public, searchable, hidden, or transformed into another target structure.

### Options, Attributes, Custom Fields, and Product Attachments <a href="#options-attributes-custom-fields-and-product-attachments" id="options-attributes-custom-fields-and-product-attachments"></a>

The most important EShop data-model distinction is the difference between shopper choice and product description. Options usually affect what the customer chooses before adding an item to the cart. Attributes usually describe what the product is. Custom fields and product tabs may support extra presentation or operational notes. Attachments may carry manuals, specification sheets, digital files, or supporting documents.

This distinction matters because many platforms use overlapping labels. A source system may call everything an attribute. Another may store all custom product data as metafields. Another may use third-party apps to create option sets. EShop migration planning should translate meaning before translating fields.

| Source value                                                                 | Possible EShop destination                  | Why the distinction matters                                                          |
| ---------------------------------------------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------------------------ |
| Size or color selected by the shopper                                        | Product option                              | The chosen value may need to appear on the order line and may affect price or image. |
| Material, dimensions, compatibility, care instructions, or technical details | Attribute, product tab, or custom field     | The value informs the buyer but may not control cart behavior.                       |
| Add-on service, engraving text, gift message, or configurable package        | Option, checkout field, or custom handling  | Some values affect product selection, while others belong to order capture.          |
| PDF manual, digital file, certificate, or product document                   | Attachment or downloadable-product handling | File ownership and access rules must be clear before migration.                      |
| App-created field with unclear behavior                                      | Add-on review or Custom Service review      | The data may not belong to a standard EShop field.                                   |

Product options require special validation. If an option affects price, SKU, image, availability, or quantity behavior, a sample product must prove that the meaning survives inside EShop. A migrated option name alone is not enough. The order line should show the selected value clearly, and the storefront should guide the buyer through the choice without confusion.

Attributes require a different review. They should support discovery, comparison, and product understanding. If the old store used attributes as filters, the target setup may need catalog-search or filtering decisions outside the data transfer itself. If attributes were only descriptive, they may need clean grouping and display rather than checkout behavior.

### Customer, Customer Group, and Account Data Differences <a href="#customer-customer-group-and-account-data-differences" id="customer-customer-group-and-account-data-differences"></a>

EShop customer data can include identity, address data, account history, customer group assignment, and relationship to Joomla users. That relationship is important because EShop operates inside Joomla rather than as a standalone hosted storefront.

A clean B2C source store may have customers with ordinary names, emails, addresses, and order history. A more complex store may include wholesale groups, reseller roles, VAT identifiers, membership references, loyalty IDs, external CRM identifiers, custom customer fields, guest checkout behavior, or buyer segmentation. These details must be classified before migration.

| Customer data pattern                      | EShop planning issue                                                              | Likely review direction                                                                |
| ------------------------------------------ | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Standard retail customer records           | Preserve identity, contact details, addresses, and order history.                 | Standard mapping and validation samples may be enough.                                 |
| Guest orders with no lasting account       | Keep historical buyer details usable even without account continuity.             | Sample guest orders should be included in validation.                                  |
| Wholesale, reseller, VIP, or member groups | Customer group meaning may affect pricing, discounts, tax, or access assumptions. | Confirm group purpose before mapping.                                                  |
| Customer tags or custom profile fields     | Source labels may not equal EShop customer groups.                                | Decide whether values are segmentation, reporting, access, or external reference data. |
| Joomla user-linked customer behavior       | Account identity may depend on Joomla user structure.                             | Review Joomla user relationship and account expectations.                              |

Customer groups are not just labels when they influence commercial behavior. A group may decide pricing, eligibility, reporting, or operational handling. If the source store uses tags or roles for similar behavior, the migration plan should decide whether those values can become EShop customer groups, need target configuration, or require custom handling.

Account data also affects customer-service continuity. After launch, the merchant may need to look up past orders, verify an address, confirm a payment method label, or understand what the customer purchased. These tasks require useful historical context, even when the target checkout behavior is configured separately.

### Orders, Checkout Fields, Discounts, and Commercial History <a href="#orders-checkout-fields-discounts-and-commercial-history" id="orders-checkout-fields-discounts-and-commercial-history"></a>

Order data in EShop should preserve what the transaction meant at the time of purchase. That includes products, selected options, quantities, prices, discounts, coupons, vouchers, tax, shipping, payment method labels, order statuses, billing and shipping details, comments, customer group context, and custom checkout fields.

Order migration becomes risky when the source platform treats checkout fields, delivery notes, payment metadata, fulfillment instructions, store pickup details, membership references, or tax identifiers as custom extensions. These values may be critical for customer support even if they do not control future checkout behavior.

| Historical order element  | What should remain understandable                                               | Common risk                                                             |
| ------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Product line item         | Purchased product, SKU, quantity, price, and selected option values.            | Options migrate as text but lose relationship to product configuration. |
| Coupon or voucher         | Promotion context and discount amount.                                          | Promotion history appears incomplete or misleading.                     |
| Tax and shipping          | Historical charges and method labels.                                           | Old order data is confused with live checkout configuration.            |
| Payment method            | What method was used historically.                                              | Payment plugin readiness is assumed from historical labels.             |
| Custom checkout field     | Delivery instructions, VAT ID, gift note, pickup detail, or internal reference. | Operational fields disappear because they are not standard.             |
| Order status and comments | Workflow history and service context.                                           | Status meanings do not align with target status labels.                 |

Live checkout configuration should be treated separately from historical order data. A migrated order can show that a payment method was used in the past, but that does not mean the target store is ready to accept that payment method after launch. A shipping label on a historical order does not prove that a shipping plugin or rate rule is configured correctly.

This distinction helps prevent validation errors. Historical orders should be checked for readability and service usefulness. Live checkout should be tested through target configuration, payment readiness, shipping readiness, tax behavior, email behavior, and order-status flow.

### Configuration Data That Should Not Be Treated as Ordinary Records <a href="#configuration-data-that-should-not-be-treated-as-ordinary-records" id="configuration-data-that-should-not-be-treated-as-ordinary-records"></a>

EShop includes configuration-sensitive data such as currencies, countries, zones, geo zones, tax classes, tax rates, stock statuses, order statuses, length classes, weight classes, shipping methods, payment plugins, notification behavior, image settings, reports, export settings, and store-level display preferences. Some of these values may be migrated or referenced, while others are best treated as target configuration.

The planning issue is ownership. Data migration can preserve historical records and supported structured data, but future selling behavior depends on target-side configuration and plugin readiness. Configuration should therefore be reviewed as launch preparation, not only data transfer.

| Configuration area               | Why it matters                                                      | Planning decision                                                                   |
| -------------------------------- | ------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Tax classes and tax rates        | They affect live price calculation and order interpretation.        | Confirm whether old tax history must be preserved separately from future tax setup. |
| Currencies and exchange behavior | Source and target may handle currency differently.                  | Validate historical order currency and future selling currency.                     |
| Zones and geo zones              | Shipping and tax rules may depend on geographic structure.          | Confirm target zones before testing checkout.                                       |
| Shipping methods                 | Live shipping behavior may require plugins, rates, or custom rules. | Treat historical shipping labels and future shipping setup separately.              |
| Payment plugins                  | Live payment acceptance depends on enabled, configured plugins.     | Do not assume payment readiness from migrated order history.                        |
| Stock and order statuses         | Status names may differ between systems.                            | Map meanings, not only labels.                                                      |

Configuration review should happen early enough to influence Demo Migration samples. If sample orders do not include tax, shipping, payment, coupon, voucher, currency, and status variation, the Demo Migration can look clean while important operational differences remain hidden.

### Joomla, SEO, Multilingual, and Presentation Data <a href="#joomla-seo-multilingual-and-presentation-data" id="joomla-seo-multilingual-and-presentation-data"></a>

EShop storefront output depends on Joomla and EShop together. Products and categories can have metadata, page titles, headings, aliases, and SEF URL behavior. Joomla menus, modules, templates, themes, layout overrides, product modules, cart modules, search modules, manufacturer pages, and landing pages may define how shoppers actually reach commerce records.

Multilingual data adds another layer. EShop may contain translated product names, descriptions, categories, options, attributes, manufacturers, labels, messages, and other shopper-facing values. Joomla may also manage multilingual menus, associations, aliases, and modules. A target store can look complete in the default language while secondary-language pages are incomplete or misaligned.

| Presentation or language area           | Data-model question                                                              | Validation need                                                 |
| --------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Product and category aliases            | Do source URLs need to be preserved, redirected, or rebuilt?                     | Test high-value product and category paths.                     |
| Metadata and page headings              | Which SEO values must remain attached to products, categories, or manufacturers? | Compare source and target samples.                              |
| Joomla menus and modules                | Which store pages depend on site assembly outside EShop records?                 | Review storefront paths, modules, and landing pages.            |
| Templates, themes, and layout overrides | Does design depend on custom Joomla or EShop presentation work?                  | Separate migration scope from implementation work.              |
| Multilingual product and catalog data   | Which languages and fields are required for launch?                              | Validate translated samples, not only default-language records. |

SEO and presentation data should not be treated as cosmetic. For many Joomla commerce stores, category paths, product aliases, manufacturer pages, module placement, and multilingual routes are part of discoverability. If they are not reviewed, the migrated catalog may be present but harder to find.

### Custom and Extension-Owned Data <a href="#custom-and-extension-owned-data" id="custom-and-extension-owned-data"></a>

EShop supports customization through Joomla development patterns, templates, themes, add-ons, payment plugins, shipping plugins, modules, integrations, custom fields, and custom layouts. That flexibility is useful, but it also means some source or target data may sit outside standard migration paths.

Custom data needs classification before execution. The first question is not whether the value exists. The first question is who owns it and what it does. A custom value may be informational, operational, checkout-related, integration-critical, SEO-related, reporting-only, or required for legal compliance.

| Custom data signal                                      | Why it matters                                                                          | Likely treatment                                                              |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Custom product fields with buyer-facing meaning         | Product pages may lose important selling information.                                   | Advanced Data Mapping, Advanced Data Configure, or Custom Service review.     |
| Custom checkout fields                                  | Orders may lose VAT IDs, delivery instructions, pickup details, or internal references. | Sample orders and field inventory required.                                   |
| Plugin-owned shipping or payment logic                  | Live checkout may not be recreated by migrating records.                                | Plugin readiness and Custom Service review when behavior must be interpreted. |
| External IDs from ERP, CRM, POS, or fulfillment systems | Records may need continuity outside the storefront.                                     | Custom mapping and validation evidence.                                       |
| Bespoke database tables                                 | Values may not belong to standard EShop structures.                                     | Custom Service review.                                                        |

The strongest EShop data-model work happens before mapping begins. Records should be classified by meaning, ownership, target behavior, and validation proof. That classification gives the project a realistic scope and helps the merchant avoid approving a migration that is technically visible but commercially incomplete.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EShop data migration is a meaning-translation exercise inside Joomla. Products, categories, options, attributes, manufacturers, customers, customer groups, orders, coupons, vouchers, tax, shipping, payments, multilingual content, SEO values, modules, templates, and custom fields do not all belong to the same layer of responsibility.

A strong EShop migration plan separates historical records, future checkout configuration, Joomla storefront assembly, multilingual content, and custom behavior. That separation makes the target result easier to validate and prevents important commercial meaning from being hidden behind successful record counts.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is EShop data mapping more than field matching?**

Because source labels do not always describe business meaning. A value called an attribute in the old store may become an EShop option, attribute, custom field, product tab, checkout field, or custom requirement depending on how the store uses it.

**What EShop data areas usually need the most attention?**

Products with options, customer groups, custom checkout fields, multilingual content, order history, tax and shipping context, payment references, Joomla presentation dependencies, and plugin-owned data usually need the closest review.

**Should historical payment and shipping data be treated as live configuration?**

No. Historical order data should remain readable, but future payment and shipping behavior depends on target-side plugin setup, configuration, testing, and checkout validation.

**When does EShop data require Custom Service review?**

Custom Service should be reviewed when important data belongs to unsupported fields, bespoke database structures, custom plugins, external systems, complex transformations, or source behavior that cannot be represented through standard EShop structures.
