# J2Store Pre-Migration Preparation Checklist

Preparing for migration to J2Store requires more than counting products, customers, and orders. J2Store belongs to a Joomla environment where commerce records can depend on Joomla articles, categories, menus, modules, templates, plugins, checkout settings, tax rules, shipping methods, payment methods, and extension-specific behavior.

The preparation goal is to make those relationships visible before Demo Migration or Full Migration. A strong preparation phase helps determine which records can move through Standard Service, which requirements need Add-ons, which tasks belong to target Joomla configuration, and which requirements should be reviewed through Custom Service.

### What Preparation Should Prove Before Migration <a href="#what-preparation-should-prove-before-migration" id="what-preparation-should-prove-before-migration"></a>

For J2Store, preparation should also prove whether the store is being treated as an active operating target, a legacy environment that must remain understandable, or a stepping stone toward a newer J2Commerce path. This distinction changes what evidence matters most. A continuity plan may focus on keeping products and checkout behavior usable, while an exit or modernization plan may focus more heavily on preserving historical evidence and identifying legacy dependencies.

J2Store preparation should prove whether the source store can become a usable J2Store commerce environment, not simply whether records can be copied. Products should retain buying meaning. Categories and menus should support discovery. Customer and order history should remain useful for service and reporting. Checkout-related behavior should be separated from historical data so the merchant understands what migration can preserve and what must be configured in the target store.

| Preparation area            | What to confirm                                                                                                | Why it matters for J2Store                                                           |
| --------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Joomla environment          | Joomla version, template, menus, categories, modules, extensions, and target J2Store version                   | J2Store products and storefront behavior depend on Joomla structure.                 |
| Product model               | Product articles, product types, options, variants, downloadable files, subscriptions, and app-driven behavior | Product meaning may depend on article structure and extension configuration.         |
| Catalog discovery           | Categories, menu items, aliases, filters, modules, metadata, and internal links                                | Shoppers may reach products through Joomla routes, not only through product records. |
| Customer and order evidence | Customer groups, addresses, statuses, discounts, taxes, shipping, payment, and order-line details              | Historical data must remain understandable after migration.                          |
| Operational configuration   | Tax, shipping, payment, checkout fields, invoices, email behavior, and status workflows                        | Configuration-sensitive behavior should not be mistaken for migrated records.        |
| Special handling            | Custom fields, app-owned data, custom code, external identifiers, and integrations                             | These areas may need Add-ons or Custom Service review.                               |

### Confirm the Target Joomla and J2Store Environment <a href="#confirm-the-target-joomla-and-j2store-environment" id="confirm-the-target-joomla-and-j2store-environment"></a>

The environment review should include version status, archived extensions, installed J2Store apps, payment and shipping plugins, template overrides, custom modules, and any developer-maintained code. Legacy stores often contain small implementation decisions that became business-critical over time. Those details should be documented before Demo Migration, not discovered during launch validation.

Start by confirming the target Joomla site and the specific J2Store generation that will receive the migrated data. J2Store is closely tied to Joomla content and extension behavior, so preparation should include the Joomla environment as part of migration scope.

Record the target Joomla version, PHP and database environment, template, enabled extensions, language setup, menu structure, module positions, checkout-related plugins, and any installed J2Store apps. If the project includes a Joomla upgrade, template replacement, or extension cleanup, decide whether those changes happen before Demo Migration, after Demo Migration, or after Full Migration.

A stable target does not need final design polish before Demo Migration, but it should be ready enough to test representative products, categories, account pages, order history, checkout paths, and storefront URLs. If the target is still structurally unstable, validation feedback may confuse migration issues with unfinished Joomla implementation work.

### Prepare J2Store Products as Joomla-Connected Commerce Records <a href="#prepare-j2store-products-as-joomla-connected-commerce-records" id="prepare-j2store-products-as-joomla-connected-commerce-records"></a>

J2Store preparation should classify products by selling behavior. Some stores use simple products inside Joomla articles. Others depend on product options, variants, downloadable files, quantity rules, recurring-like arrangements, booking behavior, bundled offers, or extension-driven fields.

Create a product-behavior inventory before migration. Include simple products, variable products, products with options, downloadable products, products with special pricing, products linked to Joomla articles, products controlled by third-party apps, and products that rely on custom fields. For each group, select representative examples for Demo Migration.

| Product evidence         | Include in preparation                                                                             | Decision value                                                       |
| ------------------------ | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Article relationship     | Product article, category, alias, metadata, and menu path                                          | Confirms whether the product depends on Joomla content structure.    |
| Option behavior          | Size, color, personalization, file upload, date choice, bundle choice, or price modifier           | Shows whether option meaning can remain usable after migration.      |
| Digital product behavior | File location, access rule, download limit, expiry behavior, and order-status dependency           | Separates migrated data from target access configuration.            |
| Pricing behavior         | Base price, sale price, customer-group price, quantity break, tax-inclusive display, and discounts | Identifies records that may need mapping or configuration review.    |
| Media relationship       | Main image, gallery, option-specific media, files, and embedded content                            | Prevents products from validating as records while failing visually. |

Product preparation should also identify what can be simplified. Some source structures may have grown around old platform limitations. Migration is not always a reason to reproduce every workaround. The preparation decision should classify each unusual product pattern as migrate, configure, simplify, exclude, or review through Custom Service.

### Prepare Categories, Menus, and Storefront Discovery <a href="#prepare-categories-menus-and-storefront-discovery" id="prepare-categories-menus-and-storefront-discovery"></a>

J2Store storefront discovery often depends on Joomla categories, menus, aliases, modules, and template output. A product may migrate correctly as a record but still be difficult to find if the target route, menu placement, or module display is not prepared.

Review source categories, product collections, tags, filters, manufacturer-like groupings, featured product areas, search behavior, related products, landing pages, and internal links. Then compare those discovery paths with the target Joomla structure. The goal is to know which relationships should be migrated as data, which should be configured in Joomla, and which require manual content or template work.

Prepare SEO-sensitive routes separately. Record high-value product URLs, category URLs, landing pages, metadata, redirects, canonical patterns, and menu aliases. A J2Store migration can preserve product and category meaning only when routing assumptions are understood early enough to be tested.

### Prepare Customer, Group, and Order Evidence <a href="#prepare-customer-group-and-order-evidence" id="prepare-customer-group-and-order-evidence"></a>

Customer and order preparation should focus on operational meaning. Names, emails, and order IDs are not enough. The target should help the merchant understand who bought what, which options were selected, what discount or tax applied, how the order was paid, how it was shipped, and which status history matters.

Select order samples that expose real store complexity. Include recent orders, older orders, guest orders if supported, registered-customer orders, orders with product options, orders from important customer groups, orders with coupons or discounts, orders with tax and shipping, orders with payment references, refunded or cancelled orders, and orders with custom statuses or comments.

| Evidence type                   | Why it matters                                                                         |
| ------------------------------- | -------------------------------------------------------------------------------------- |
| Customer groups                 | May affect pricing, tax, access, visibility, membership, or B2B handling.              |
| Addresses and profile fields    | May include business data, VAT fields, delivery notes, or custom checkout information. |
| Order-line options              | Preserve what the customer actually bought, not only the product name.                 |
| Discounts and coupons           | Keep commercial context visible for support and reporting.                             |
| Payment and shipping references | Help customer service interpret historical orders after launch.                        |
| Status history                  | Clarifies fulfillment, cancellation, refund, and after-sales review.                   |

If source groups or checkout fields do not translate cleanly into J2Store, classify the requirement before migration. Some fields may map to customer records. Some belong to order history. Some are target configuration. Some require Custom Service because they represent source-specific logic.

### Separate Configuration From Migrated Records <a href="#separate-configuration-from-migrated-records" id="separate-configuration-from-migrated-records"></a>

Tax, shipping, payment, invoice, email, checkout, and status behavior should be prepared as configuration-sensitive areas. Historical records can preserve past tax amounts, shipping labels, payment names, transaction references, and order statuses, but live target behavior usually depends on target setup.

Prepare a configuration inventory that explains what must be recreated, configured, or tested in the target. Include tax zones, tax rates, tax display rules, shipping methods, payment methods, checkout fields, email templates, invoice format, order statuses, coupon behavior, discount rules, and any app-based workflow.

This separation protects the project from a common approval problem: the merchant sees migrated records and assumes the live checkout will behave the same way. J2Store validation should distinguish historical order evidence from future checkout operation.

### Review Extensions, Custom Fields, and Integration-Owned Data <a href="#review-extensions-custom-fields-and-integration-owned-data" id="review-extensions-custom-fields-and-integration-owned-data"></a>

J2Store stores may rely on apps, plugins, custom Joomla fields, third-party extensions, custom code, ERP identifiers, accounting exports, fulfillment integrations, subscription logic, booking logic, or reporting tables. These areas should be identified before Demo Migration so the selected service path is realistic.

Use the following classification during preparation:

| Requirement                                   | Likely handling path                                              |
| --------------------------------------------- | ----------------------------------------------------------------- |
| Supported standard records                    | Standard Service or Managed Service depending on execution needs. |
| Supported mapping requirement                 | Add-on review, especially when field relationships are clear.     |
| Target setup requirement                      | Joomla or J2Store configuration before validation.                |
| Unsupported app-owned data                    | Custom Service review.                                            |
| Custom source structure                       | Custom Service review.                                            |
| External identifier or integration dependency | Custom Service or implementation review depending on use.         |

Avoid treating every unknown field as a note field. A custom field may control pricing, access, shipping, reporting, digital delivery, or fulfillment. Flattening it can make the migration appear complete while damaging operational meaning.

### Select Demo Migration Samples Carefully <a href="#select-demo-migration-samples-carefully" id="select-demo-migration-samples-carefully"></a>

A strong J2Store sample should include more than clean products. Include at least one article-linked product, one product with options, one order with tax and shipping context, one customer record connected to a Joomla user where relevant, one SEO-sensitive URL, and one item that depends on a plugin or customization. This sample design makes Demo Migration a meaningful proof exercise rather than a surface-level count check.

Demo Migration should test the risks most likely to affect Full Migration. A weak sample that includes only simple products and clean orders can hide the exact issues that matter in J2Store.

Include samples from every meaningful complexity group: simple products, option-heavy products, downloadable products, important categories, products with custom fields, customers from different groups, orders with discounts, orders with tax and shipping, orders with payment references, orders with unusual statuses, and SEO-sensitive storefront paths.

The review should ask practical questions. Can a shopper understand the product? Can the merchant identify what was purchased? Do categories and menus support discovery? Are customer groups meaningful? Does order history remain useful? Are configuration tasks separated from migration issues?

### Decide the Service Path Before Full Migration <a href="#decide-the-service-path-before-full-migration" id="decide-the-service-path-before-full-migration"></a>

Preparation should end with a service-path decision. If the source data is supported, the merchant can operate the process, and Demo Migration confirms that representative records remain meaningful, Standard Service may be enough. If the project fits standard capability but the merchant wants Next-Cart-led execution, Managed Service may be more appropriate. If unsupported data, custom logic, app-owned records, or custom platform behavior shape the result, Custom Service should be reviewed.

Add-ons may help with focused filtering, mapping, and configuration support, but they should not be used as a vague answer for unsupported behavior. Custom Service is the correct path when the requirement needs bespoke interpretation, tailored handling, or custom migration logic adjustment.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Store migration preparation should make Joomla structure, product meaning, customer and order evidence, configuration requirements, extension dependencies, and validation samples visible before Full Migration. The strongest preparation work does not try to make every source behavior look standard. It classifies each requirement into migrated records, target configuration, Add-ons, Custom Service, or intentional exclusion.

When preparation is complete, the merchant should know which data can move through the selected service path, which behaviors must be configured in J2Store, which Joomla storefront relationships need review, and which custom requirements need escalation before execution.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to J2Store?**

Start with the target Joomla and J2Store environment, then prepare product behavior, categories, customer groups, order samples, checkout configuration, storefront paths, and extension-owned data.

**Why do J2Store products need special preparation?**

J2Store products may depend on Joomla articles, categories, options, downloadable files, custom fields, modules, templates, and apps. Preparing only product names and prices may miss the relationships that make products usable.

**Should tax, shipping, and payment settings be treated as migrated data?**

Historical order values can be migrated when supported, but live tax, shipping, payment, checkout, and invoice behavior usually depends on target J2Store configuration and should be prepared separately.

**When should Custom Service be reviewed for J2Store?**

Custom Service should be reviewed when the source depends on unsupported app data, custom fields, custom checkout logic, unusual product behavior, external identifiers, or source-specific workflows that cannot be handled as standard migration scope.

**What should Demo Migration prove for J2Store?**

Demo Migration should prove that representative products, options, categories, customers, groups, orders, discounts, tax, shipping, payment context, and Joomla storefront relationships remain meaningful enough for approval.
