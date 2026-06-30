# EShop Validation Priorities

Validation for EShop by Ossolution Team should prove that the migrated store works as a Joomla shopping cart environment, not only that records appear in administration. EShop can carry catalog structure, product options, attributes, custom fields, attachments, manufacturers, customer groups, orders, checkout fields, coupons, vouchers, tax classes, shipping methods, payment references, multilingual content, modules, templates, and integration-sensitive data. Those records need to be validated as connected business meaning.

A product can exist but lose the option that made it purchasable. An order can exist but no longer show the selected product choice, coupon, voucher, tax context, or shipping method that explains the total. A category can migrate but not support the Joomla menu, module, metadata, or SEF URL path that shoppers use to reach it. Validation should therefore move beyond record counts and confirm whether the migrated EShop store remains usable for shoppers, store administrators, support teams, and future implementation work.

The strongest validation review begins with representative samples. Simple products are useful, but they are not enough. EShop validation should include option-heavy products, attribute-rich products, products with attachments or downloads, manufacturer-linked products, customer group examples, coupon and voucher orders, tax-sensitive and shipping-sensitive orders, multilingual records, SEO-sensitive pages, module-dependent storefront paths, and any custom or integration-owned values that influence operations.

### What Validation Must Prove for EShop <a href="#what-validation-must-prove-for-eshop" id="what-validation-must-prove-for-eshop"></a>

EShop validation should answer whether the target store preserves business meaning in the areas that matter after launch. The review should show what migrated correctly, what requires target-side configuration, what depends on Joomla implementation, and what needs Add-ons or Custom Service review. Without that separation, teams often treat every mismatch as a migration defect or overlook real migration gaps because the visible pages look acceptable.

| Validation area           | What must be proven                                                                                                                                                               | Why it matters for EShop                                                                           |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Catalog meaning           | Products, categories, manufacturers, options, attributes, images, custom fields, attachments, tabs, labels, reviews, and related products remain usable.                          | EShop separates many catalog roles that may be blended in the source store.                        |
| Commercial history        | Customers, customer groups, addresses, orders, order lines, selected options, totals, discounts, coupons, vouchers, tax, shipping, payment context, and statuses remain readable. | Administrators need historical records for support, account review, reporting, and reconciliation. |
| Target configuration      | Tax classes, geo zones, currencies, stock statuses, order statuses, shipping methods, payment plugins, checkout fields, and emails are distinguished from migrated records.       | Future checkout behavior usually depends on target setup, not only historical data transfer.       |
| Joomla storefront context | Menus, aliases, metadata, SEF URLs, modules, templates, search paths, category pages, product pages, cart, checkout, and account pages remain coherent.                           | EShop data becomes useful to shoppers only when Joomla presentation exposes it correctly.          |
| Special handling          | Multilingual records, custom fields, source extensions, plugin-owned values, external identifiers, and custom implementation are classified.                                      | Unsupported or bespoke data should not be silently approved as standard scope.                     |

Validation should produce a decision, not a vague impression. A strong review can say which areas pass, which need configuration, which need Joomla implementation work, which need an Add-on, and which require Custom Service review before the project proceeds.

### Validate Product and Catalog Meaning <a href="#validate-product-and-catalog-meaning" id="validate-product-and-catalog-meaning"></a>

Catalog validation should begin with the products that represent the store’s real selling model. EShop supports products, categories, manufacturers, images, product options, attributes, custom fields, attachments, downloads, extra product tabs, labels, reviews, related products, discounts, specials, stock values, dimensions, weights, and SEO fields. Validation should confirm that these elements remain meaningful inside EShop rather than merely appearing as isolated fields.

The most common validation mistake is approving a catalog after checking only product names, prices, and images. That misses the structures that determine whether shoppers can compare, choose, and buy. Product options should be checked where they affect selection, price, SKU, image, stock, or order-line meaning. Attributes should be checked where they support specifications, comparison, or structured product information. Manufacturers should be checked where brand discovery, supplier grouping, or catalog filtering matters. Attachments and downloads should be checked where product documents, manuals, certificates, or digital assets matter.

| Product sample                      | Validation question                                                                                                                | Acceptance signal                                                                                   |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Simple product                      | Did the basic product fields, price, image, category, status, stock, and description remain coherent?                              | The product is readable, assigned correctly, and manageable in EShop.                               |
| Option-heavy product                | Did required choices, price-changing values, SKU-changing values, image-changing values, or stock-sensitive options remain usable? | A shopper can select the option and the order record preserves the chosen value.                    |
| Attribute-rich product              | Did specifications remain informational rather than being confused with shopper choices?                                           | Attributes support comparison and product detail without distorting purchase behavior.              |
| Manufacturer-linked product         | Did brand or manufacturer association remain useful?                                                                               | Manufacturer pages, references, or filters can still support discovery where planned.               |
| Product with custom fields or tabs  | Did structured extra information retain meaning?                                                                                   | Important custom values are placed correctly or flagged for Add-ons or Custom Service review.       |
| Product with attachment or download | Did files remain connected to the right product?                                                                                   | Shoppers or administrators can access the expected files according to the intended target behavior. |
| Discounted or special-price product | Did promotional meaning survive as data or configuration?                                                                          | The team understands whether the value is historical, migrated, or target-configured.               |

Validation should also test category and product discovery from the storefront. A product that looks correct in administration may still be difficult to find if categories, menus, modules, aliases, or search behavior are incomplete. Product validation and storefront validation should therefore be connected.

### Validate Customers, Groups, and Order History <a href="#validate-customers-groups-and-order-history" id="validate-customers-groups-and-order-history"></a>

EShop validation should treat customers and orders as commercial history, not only as database records. Customer records may connect to Joomla users, customer groups, addresses, order history, checkout fields, coupons, vouchers, and order statuses. Orders may include product options, quantities, unit prices, discounts, totals, tax, shipping, payment method references, comments, invoice context, and status history. These relationships explain what happened commercially.

A migrated order should allow a store administrator to answer practical questions: who placed the order, what the customer bought, which option values were selected, what discount or voucher was used, how tax and shipping appeared, which payment method was recorded, which status applied, and whether special checkout fields need to remain visible. If those details are unclear, the order count is not enough evidence.

| Record type             | What to inspect                                                                                  | Why it matters                                                                          |
| ----------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- |
| Registered customer     | Joomla user connection, customer profile, addresses, customer group, and account history.        | EShop may rely on Joomla user context as well as commerce-specific customer records.    |
| Guest customer          | Name, email, billing address, shipping address, and order association.                           | Guest orders should remain useful for support even without a full account.              |
| Customer group          | Group assignment, pricing expectations, tax/shipping relevance, or membership-like segmentation. | Group meaning can affect how administrators interpret history and future configuration. |
| Option order            | Selected product options, option price effect, SKU or image effect, and order-line readability.  | Historical orders must explain what the customer actually chose.                        |
| Coupon or voucher order | Discount source, amount, code, and total calculation context.                                    | Promotions should remain understandable for service and reporting.                      |
| Tax and shipping order  | Tax line, geo-zone context, shipping method reference, weight or destination relevance.          | Historical totals must be explainable even when future rules are configured separately. |
| Payment-context order   | Payment method label, transaction reference where available, status, and comments.               | Payment meaning helps reconciliation and support.                                       |

Customer and order validation should include recent records, older records, ordinary records, and edge cases. Clean recent orders may pass while older or more complex records reveal hidden differences in statuses, customer groups, checkout fields, or option handling.

### Validate Configuration-Sensitive Behavior <a href="#validate-configuration-sensitive-behavior" id="validate-configuration-sensitive-behavior"></a>

Some EShop behavior is driven by target configuration rather than migrated historical records. Tax classes, tax rates, geo zones, currencies, length and weight classes, stock statuses, order statuses, shipping methods, payment plugins, checkout fields, notification emails, Catalog Mode, Quote Cart Mode, and one-page checkout behavior may need target-side setup and testing. Validation should separate what has migrated from what must be configured.

This distinction protects the review from two opposite errors. The first error is blaming migration for settings that were never configured in the target store. The second error is approving the migration because data exists while future checkout behavior has not been tested. EShop validation should include both historical-record review and live-behavior testing where launch readiness depends on configuration.

| Behavior area       | Validation method                                                                                | Decision output                                                               |
| ------------------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| Tax                 | Compare historical tax examples and test target tax configuration where future checkout matters. | Identify migrated tax context versus target tax setup.                        |
| Shipping            | Review historical shipping method labels and test target shipping rules or plugins.              | Confirm whether shipping evidence is historical, configured, or custom.       |
| Payment             | Review payment references on historical orders and verify active payment plugins separately.     | Separate order history from future payment acceptance.                        |
| Currencies          | Check historical currency display, conversion context, and target currency settings.             | Confirm whether currency behavior is preserved, configured, or out of scope.  |
| Checkout fields     | Inspect migrated billing/shipping/custom fields and test future checkout fields.                 | Decide whether fields are standard, configurable, mapping-related, or custom. |
| Order statuses      | Review source status meanings and target status mapping.                                         | Confirm support teams can understand order state after migration.             |
| Emails and invoices | Review whether templates and invoice behavior are migration data, target setup, or design work.  | Prevent late confusion between data migration and Joomla/EShop configuration. |

A good validation report should name configuration gaps explicitly. For example, a historical order may show a shipping method correctly, while the future shipping plugin still needs target setup. That is not the same issue as a missing shipping value in migrated order history.

### Validate Joomla Storefront and SEO Context <a href="#validate-joomla-storefront-and-seo-context" id="validate-joomla-storefront-and-seo-context"></a>

Because EShop operates inside Joomla, validation must include how migrated commerce records appear in the site. Product and category records need storefront paths, menus, aliases, metadata, SEF URLs, modules, templates, layout overrides, search behavior, comparison paths, cart flow, checkout path, account pages, and redirects where relevant. A store can pass backend review and still fail the shopper journey.

Storefront validation should focus on high-value paths first. Identify the categories that drive traffic, products that represent core revenue, manufacturer pages if they matter, campaign pages, account/order pages, cart and checkout pages, and any module-driven pages that expose catalog data. Then confirm that migrated records can support those paths.

| Storefront item       | What to validate                                                                                | Practical pass condition                                                      |
| --------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Product page          | Product content, images, options, attributes, reviews, related products, metadata, and layout.  | The page supports selection, trust, and purchase intent.                      |
| Category page         | Product assignment, ordering, image, metadata, menu path, filter/search expectations.           | Shoppers can discover the right products through planned navigation.          |
| Manufacturer page     | Manufacturer association and page behavior where brand discovery matters.                       | Products appear under the expected manufacturer context.                      |
| Cart and checkout     | Add-to-cart, option capture, totals, shipping/tax/payment steps, customer fields.               | A test purchase path works according to target configuration.                 |
| Customer account      | Login, profile, address, order history, downloadable content if relevant.                       | Returning buyers can review the information the business expects to preserve. |
| SEO-sensitive page    | Alias, metadata, SEF URL, redirect plan, and page title.                                        | Important pages have a clear continuity plan.                                 |
| Module-dependent page | Mini cart, product module, category module, manufacturer module, search or content plugin area. | Joomla modules display migrated records correctly where used.                 |

This review should not turn every layout issue into a migration issue. Instead, it should identify whether the issue belongs to migrated data, EShop configuration, Joomla menus/modules/templates, redirects, or custom implementation.

### Validate Multilingual, Custom, and Integration-Owned Data <a href="#validate-multilingual-custom-and-integration-owned-data" id="validate-multilingual-custom-and-integration-owned-data"></a>

EShop supports multilingual use cases and can sit inside Joomla sites that also rely on multilingual menus, translated content, language-specific metadata, translated product/category names, option labels, attributes, modules, and checkout text. Validation should include active languages rather than checking only the default language. If the source platform stored translations through custom fields, apps, or a separate translation layer, those records should be reviewed carefully.

Custom and integration-owned data also needs explicit classification. Source stores may include external identifiers, ERP fields, CRM references, affiliate data, membership or subscription logic, custom checkout fields, source app records, modified product relationships, or plugin-owned behavior. Some values can be mapped into supported fields. Some belong to target configuration. Some require Add-ons. Some require Custom Service because the old meaning is not part of ordinary EShop records.

| Special area            | What to include in validation                                                                              | Outcome to record                                                                 |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Multilingual products   | Translated names, descriptions, options, attributes, metadata, aliases, and category relationships.        | Confirm whether translations remain complete or require implementation work.      |
| Multilingual storefront | Language-specific menus, modules, routes, checkout labels, and redirects.                                  | Confirm whether shoppers can use the intended language paths.                     |
| Custom product values   | Source custom fields, tabs, attachments, product files, or app-owned data.                                 | Decide whether values are supported, need mapping, or need Custom Service review. |
| Integration identifiers | ERP, CRM, affiliate, fulfillment, membership, or reporting IDs.                                            | Decide whether identifiers must be preserved and where they should live.          |
| Custom checkout data    | Billing/shipping custom fields, delivery notes, personalization fields, or business-specific order values. | Confirm whether data appears on customer/order records or needs custom handling.  |
| Plugin-owned behavior   | Payment, shipping, search, filter, email, analytics, or marketing extension data.                          | Separate historical evidence from active plugin behavior and custom logic.        |

The validation goal is not to force every old behavior into EShop automatically. The goal is to decide what must be preserved as migrated data, what should be recreated through EShop or Joomla configuration, and what requires a service-path decision before approval.

### Turning Demo Migration Results Into an Acceptance Decision <a href="#turning-demo-migration-results-into-an-acceptance-decision" id="turning-demo-migration-results-into-an-acceptance-decision"></a>

Demo Migration should become a decision checkpoint. A strong EShop review does not simply say that the sample looks correct. It records which sample groups passed, which differences are expected target configuration, which issues need follow-up, and whether the current service path is still appropriate.

| Result pattern                                                                                                         | Meaning                                                                           | Recommended decision                                                |
| ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Core products, customers, and orders are correct; no complex unsupported areas appear.                                 | The selected path likely fits the ordinary data burden.                           | Continue with standard execution and routine validation.            |
| Records migrate, but filtering, mapping, or available configuration adjustments are needed.                            | Scope is mostly understood, but optional service support may improve reliability. | Review relevant Add-ons before approval.                            |
| The merchant needs Next-Cart-led coordination, sample review, and execution support.                                   | Complexity may be manageable but operational risk is high.                        | Consider Managed Service.                                           |
| Custom fields, unsupported extension data, external identifiers, or bespoke checkout behavior affect business meaning. | Standard assumptions may not preserve the store’s operating model.                | Review Custom Service before approval.                              |
| Joomla menus, modules, templates, payment plugins, shipping plugins, redirects, or layout work remain incomplete.      | Some launch risks belong to implementation, not data migration alone.             | Create a separate target-readiness checklist before final approval. |

The final acceptance decision should be evidence-based. Products, options, attributes, customers, orders, discounts, vouchers, tax, shipping, payment context, multilingual content, Joomla storefront paths, and custom records should all be represented in the validation notes where they matter. That evidence protects the project from approving an easy sample while ignoring the records that actually determine launch success.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EShop validation should prove whether the target Joomla store preserves catalog meaning, customer and order history, configuration-sensitive behavior, storefront continuity, multilingual structure, and custom or integration-owned data. The review should not stop at totals or visible product pages. It should test the records that carry real business meaning.

The best validation output is a practical acceptance decision. It shows what passed, what needs target configuration, what belongs to Joomla implementation, what may fit Add-ons, and what should be reviewed through Custom Service. That makes Demo Migration useful as a decision checkpoint instead of a superficial preview.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first after an EShop Demo Migration?**

Start with representative products, options, attributes, categories, manufacturers, customers, customer groups, orders, coupons, vouchers, tax, shipping, payment context, and storefront paths. The first review should prove meaning, not only record counts.

**Why are product options important in EShop validation?**

Options may affect shopper choice, price, SKU, image, stock, and order-line meaning. A product can look present while the buying choice is incomplete, so option-heavy products need direct review.

**Should tax, shipping, and payment behavior be validated as migrated data?**

Historical tax, shipping, and payment context should be checked on old orders. Future checkout behavior should be tested through EShop configuration and active plugins. These are related but not identical validation tasks.

**How should Joomla storefront issues be handled during validation?**

Storefront issues should be classified by ownership. Some relate to migrated data, while others belong to Joomla menus, modules, templates, aliases, redirects, payment plugins, shipping plugins, or target configuration.

**When does validation indicate Custom Service may be needed?**

Custom Service should be reviewed when important meaning depends on custom fields, unsupported extension data, external identifiers, bespoke checkout behavior, integration-owned records, Custom Platform handling, Tailored Add-ons, or Custom Add-ons.
