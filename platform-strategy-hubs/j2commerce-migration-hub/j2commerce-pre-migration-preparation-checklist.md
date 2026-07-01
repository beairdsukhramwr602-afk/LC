# J2Commerce Pre-Migration Preparation Checklist

Preparing for migration to J2Commerce means preparing both commerce data and the Joomla environment that gives that data meaning. Products, categories, customers, orders, images, coupons, taxes, shipping, payment records, and checkout fields matter, but they should not be reviewed in isolation. J2Commerce stores can depend on Joomla articles, aliases, menus, modules, templates, language settings, access rules, apps, plugins, and storefront configuration.

The preparation phase should make those relationships visible before Demo Migration. A strong checklist helps the merchant decide which records can move through Standard Service, which requirements need Add-ons, which parts belong to target configuration, and which items need Custom Service review. It also prevents a common J2Commerce mistake: approving a migration because the records exist, while product pages, checkout behavior, or storefront discovery remain incomplete.

### What Preparation Should Prove Before Migration <a href="#what-preparation-should-prove-before-migration" id="what-preparation-should-prove-before-migration"></a>

J2Commerce preparation should prove that the future store can operate as a usable Joomla commerce environment. Product pages should keep their commercial meaning. Storefront paths should remain understandable. Customers and order history should support service and reporting. Checkout fields should collect the right information. Payment and shipping history should stay readable without being confused with live target configuration.

For merchants coming from J2Store, preparation should also clarify what belongs to legacy store history and what should become the J2Commerce operating model. Older J2Store stores may include add-ons, custom fields, template overrides, payment plugins, shipping plugins, Joomla article relationships, and checkout behavior that were shaped by years of operational use. Those details should be documented before scope is approved.

| Preparation area              | What to confirm                                                                                                                 | Why it matters for J2Commerce                                              |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Joomla foundation             | Site structure, articles, categories, menus, modules, templates, languages, access rules, and enabled extensions                | Product visibility and storefront behavior can depend on Joomla structure. |
| Product model                 | Product types, SKUs, prices, variants, configurable logic, downloads, bundles, subscriptions, bookings, deposits, and services  | Product meaning may require more than a flat product record.               |
| Checkout and account behavior | Billing fields, shipping fields, guest checkout, registration choices, saved addresses, custom fields, and required field logic | Order handling depends on the information collected during checkout.       |
| Order workflow                | Order statuses, payment labels, shipping labels, refunds, cancellations, comments, invoices, and email expectations             | Historical orders must remain understandable for support and reporting.    |
| Storefront experience         | URLs, aliases, metadata, category pages, modules, product layouts, image galleries, filters, and template behavior              | A correct admin record can still fail customer-facing validation.          |
| Extension ownership           | Apps, payment plugins, shipping plugins, template overrides, custom code, and external integrations                             | Some data or behavior may need Add-ons or Custom Service review.           |

Preparation is complete only when the merchant can explain what should be migrated, what should be configured, what should be simplified, and what needs custom review.

### Confirm the Target Joomla and J2Commerce Environment <a href="#confirm-the-target-joomla-and-j2commerce-environment" id="confirm-the-target-joomla-and-j2commerce-environment"></a>

The target environment should be stable enough to test real store behavior. It does not need final visual polish before Demo Migration, but it should be ready to display representative products, categories, cart behavior, checkout fields, account pages, order history, payment labels, shipping labels, and key storefront paths.

Confirm the Joomla site structure first. Record categories, menus, article settings, template assignments, language configuration, modules, access levels, media handling, and enabled extensions. Then review J2Commerce setup areas such as store information, default currency, weight and length units, product display settings, inventory behavior, checkout configuration, payment methods, shipping methods, order statuses, and apps.

If the project includes a Joomla redesign, template replacement, extension cleanup, or move from J2Store, decide when that work happens. A migration project becomes harder to validate when data movement, site rebuild, extension replacement, and checkout redesign are all happening without a clear sequence. The cleaner approach is to define which target assumptions must be ready for Demo Migration and which can remain post-migration implementation tasks.

| Environment item               | Preparation question                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| Joomla categories and articles | Will migrated products have the correct article and category context?                                        |
| Menus and aliases              | Which product, category, and landing-page routes need to be preserved or redirected?                         |
| Template and modules           | Will product lists, product detail pages, cart modules, and category displays appear in the intended layout? |
| Store configuration            | Are currency, units, inventory, tax display, checkout, and account settings ready for sample testing?        |
| Payment and shipping methods   | Which methods are historical labels, and which must function in the live target store?                       |
| Apps and plugins               | Which features are core behavior, optional enhancement, or custom dependency?                                |

The target should be documented before Demo Migration so validation feedback can be interpreted correctly. Otherwise, a missing field, broken layout, or checkout issue may be misread as a migration error when the real cause is unfinished target configuration.

### Prepare Product Evidence by Selling Behavior <a href="#prepare-product-evidence-by-selling-behavior" id="prepare-product-evidence-by-selling-behavior"></a>

J2Commerce product preparation should begin with selling behavior, not product count. A store may include simple products, variable products, configurable products, downloadable products, flexivariable products, bundles, subscriptions, bookings, deposits, services, or custom option behavior. Each pattern should have representative samples in Demo Migration.

Because J2Commerce connects products with Joomla articles, product preparation should also include content evidence. Product title, alias, category, description, media, metadata, publication state, access level, tags, layout, and menu path may all affect whether a product remains usable after migration.

| Product evidence             | Include in preparation                                                                                                  | Decision value                                                            |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Article relationship         | Article title, alias, category, status, access level, metadata, and content layout                                      | Confirms whether the product can appear as a usable Joomla product page.  |
| Selling type                 | Simple, variable, configurable, downloadable, subscription, booking, deposit, service, bundle, or custom option pattern | Determines whether standard mapping is enough or deeper review is needed. |
| Option and variant behavior  | Option labels, price modifiers, images, stock rules, required selections, and customer-entered values                   | Prevents variant or option meaning from becoming flattened.               |
| Digital access               | Download files, access conditions, expiry rules, order-status dependency, and customer entitlement                      | Separates migrated records from target access configuration.              |
| Inventory and quantity rules | Stock tracking, minimum quantity, maximum quantity, hold-stock behavior, and low-stock expectations                     | Confirms whether launch behavior matches the source store.                |
| Media and display            | Main images, galleries, embedded content, related products, and product modules                                         | Prevents products from validating in admin while failing visually.        |

Merchants coming from J2Store should review old product structures carefully. Some products may already be tied to Joomla articles and add-ons, but old implementation choices may not be worth reproducing exactly. Preparation should classify unusual product behavior as migrate, configure, simplify, exclude, or review through Custom Service.

### Prepare Categories, URLs, Menus, and Storefront Discovery <a href="#prepare-categories-urls-menus-and-storefront-discovery" id="prepare-categories-urls-menus-and-storefront-discovery"></a>

J2Commerce storefront discovery depends on more than catalog categories. Products may be reached through Joomla category pages, menu items, modules, featured product areas, campaign landing pages, tags, search, filters, breadcrumbs, and internal links. Preparation should identify which discovery paths must continue after migration.

Create a list of high-value product URLs, category URLs, landing pages, menu aliases, campaign pages, indexed pages, and pages receiving external links. Then decide whether the target should preserve routes, use redirects, restructure navigation, or intentionally retire old paths. If the merchant is moving from J2Store, review whether familiar URL patterns should be retained for continuity or replaced with cleaner J2Commerce routes.

| Discovery item     | Preparation task                                                                              |
| ------------------ | --------------------------------------------------------------------------------------------- |
| Product URLs       | Identify high-value pages, aliases, metadata, redirects, and canonical expectations.          |
| Category pages     | Review hierarchy, landing-page content, modules, filters, and SEO value.                      |
| Menus              | Confirm which menu items control storefront routes or product discovery.                      |
| Modules            | Identify product lists, category modules, cart modules, related products, and featured areas. |
| Search and filters | Select sample products that prove shoppers can still find important items.                    |
| Legacy paths       | Decide which old J2Store or source-platform paths need redirects or route preservation.       |

A storefront should not be considered ready because records were imported. It is ready when customers can find products, understand the product page, add the right item to cart, and complete checkout without losing the context that helped them choose.

### Prepare Customer, Account, and Order Evidence <a href="#prepare-customer-account-and-order-evidence" id="prepare-customer-account-and-order-evidence"></a>

Customer and order preparation should focus on operational meaning. A successful J2Commerce migration should help the merchant understand who bought what, which options were selected, what discount or tax applied, how the order was paid, how it was shipped, and what status the order reached.

Select customer and order samples that expose real complexity. Include registered customers, guest customers, customers with multiple addresses, customers with company or tax fields, orders with coupons, orders with shipping and tax, orders with custom checkout fields, cancelled orders, refunded orders, orders with comments, orders with custom statuses, and orders tied to important product types.

| Evidence type               | Why it matters                                                                                           |
| --------------------------- | -------------------------------------------------------------------------------------------------------- |
| Joomla user relationship    | Some customers may need registered account continuity, while others may remain historical guest buyers.  |
| Billing and shipping fields | Order fulfillment and customer service depend on complete address and contact information.               |
| Custom checkout fields      | Delivery notes, VAT numbers, company details, pickup preferences, or compliance fields may need mapping. |
| Order statuses              | Status labels should preserve workflow meaning, not only source wording.                                 |
| Payment and shipping labels | Historical records should remain readable even when live target methods are configured separately.       |
| Order-line options          | Support teams need to see the exact product choice, not only the parent product name.                    |

Order status preparation is especially important. Source labels may not have the same meaning in J2Commerce. A label such as complete, confirmed, paid, shipped, refunded, or cancelled should be mapped according to business meaning, not copied blindly. If the store uses custom statuses, document when each status is assigned and which team depends on it.

### Separate Migrated Records From Target Configuration <a href="#separate-migrated-records-from-target-configuration" id="separate-migrated-records-from-target-configuration"></a>

A J2Commerce migration can preserve historical values, but live store behavior depends on target configuration. Tax, shipping, payment, checkout fields, email templates, invoice behavior, order statuses, inventory settings, downloadable access, and account behavior should be reviewed as configuration-sensitive areas.

Historical orders may retain tax amounts, shipping labels, payment method names, transaction references, and status history. That does not mean the new store will calculate tax, offer shipping, send emails, or update statuses in the same way unless those settings are configured and tested.

| Area               | Migration can preserve                                        | Target configuration must prove                                                      |
| ------------------ | ------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Taxes              | Historical tax names, amounts, and order context              | Correct rates, zones, display behavior, and checkout calculation.                    |
| Shipping           | Historical shipping method names, costs, and tracking context | Available methods, zones, carrier behavior, and fulfillment workflow.                |
| Payment            | Historical method names and transaction references            | Active gateways, payment validation, default method behavior, and status updates.    |
| Checkout fields    | Stored customer and order field values where supported        | Field placement, required logic, email visibility, and admin visibility.             |
| Email and invoices | Historical record context                                     | Templates, language handling, status triggers, and customer notifications.           |
| Inventory          | Product stock values where supported                          | Stock deduction, backorder expectations, hold-stock behavior, and low-stock notices. |

This separation helps the merchant approve migration with the right expectations. Data movement can make historical information available, but launch readiness requires configuration validation.

### Identify Apps, Add-ons, Custom Fields, and Custom Code <a href="#identify-apps-add-ons-custom-fields-and-custom-code" id="identify-apps-add-ons-custom-fields-and-custom-code"></a>

J2Commerce can be extended through apps, plugins, modules, templates, language packs, payment plugins, shipping plugins, and custom development. Some of these extensions affect presentation only. Others control checkout steps, order handling, product behavior, shipping rates, payment updates, tax logic, downloadable access, analytics, or external integrations.

Create an extension inventory before migration. For each app or extension, record its purpose, data ownership, active status, dependency on source records, replacement plan, and validation sample. This is especially important for stores coming from J2Store, where add-ons or custom code may not behave like current J2Commerce functionality.

| Extension evidence    | Preparation question                                                                            |
| --------------------- | ----------------------------------------------------------------------------------------------- |
| App-created fields    | Does the app store data that should migrate, be configured, or be retired?                      |
| Checkout extensions   | Does the extension add steps, fields, rules, or terms acceptance?                               |
| Payment plugins       | Does the plugin update order status, store references, or trigger emails?                       |
| Shipping plugins      | Does the plugin calculate rates, print labels, update tracking, or change order state?          |
| Template overrides    | Are product and checkout layouts dependent on custom files?                                     |
| External integrations | Do ERP, CRM, fulfillment, accounting, analytics, or email tools depend on stable IDs or fields? |

When the requirement is only a supported field mapping or focused data filter, an Add-on may be enough. When the requirement depends on app-owned data, custom logic, external identifiers, or unsupported source behavior, Custom Service should be reviewed before Full Migration.

### Choose Demo Migration Samples Deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the store’s actual risk profile. A small sample of simple products is not enough if the store’s revenue depends on options, downloads, subscriptions, bookings, custom checkout fields, complex shipping, or legacy J2Store behavior.

Choose samples that include ordinary records and exception records. Ordinary records prove baseline migration quality. Exception records reveal whether the selected approach is strong enough for the real store.

| Sample type        | Include when relevant                                                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Product samples    | Simple products, variants, configurable products, downloads, services, bundles, subscriptions, bookings, and products with custom options.   |
| Category samples   | Main categories, deep categories, SEO-sensitive categories, menu-linked categories, and legacy routes.                                       |
| Customer samples   | Registered customers, guest buyers, multiple-address customers, company buyers, and customers with custom fields.                            |
| Order samples      | Recent orders, older orders, refunded orders, cancelled orders, orders with coupons, tax, shipping, payment references, and custom statuses. |
| Storefront samples | Product pages, category pages, modules, cart behavior, checkout fields, account pages, and email triggers.                                   |
| Legacy samples     | J2Store-origin products, add-on-driven behavior, template overrides, and custom fields.                                                      |

The sample set should be approved before Demo Migration starts. After Demo Migration, review whether each sample remains meaningful in J2Commerce. If the sample set is too simple to prove the risk, expand it before Full Migration.

### Final Preparation Checklist Before Demo Migration <a href="#final-preparation-checklist-before-demo-migration" id="final-preparation-checklist-before-demo-migration"></a>

Before Demo Migration, the merchant should have a practical checklist that separates required evidence from optional cleanup. The goal is not to perfect the entire store before testing. The goal is to make sure the test can answer real migration questions.

| Checklist item              | Ready when                                                                                                                       |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Target environment          | Joomla, J2Commerce, menus, templates, modules, payment, shipping, and checkout areas are stable enough for sample testing.       |
| Product evidence            | Product types, article relationships, media, options, inventory, and custom behavior are documented.                             |
| Customer and order evidence | Representative customer groups, guest orders, order statuses, fields, tax, shipping, payment, and order comments are identified. |
| URL and storefront evidence | High-value URLs, menus, aliases, metadata, redirects, modules, and product display paths are listed.                             |
| Extension evidence          | Apps, plugins, add-ons, custom code, template overrides, and integrations are classified.                                        |
| Service-path questions      | Items needing Add-ons, target configuration, or Custom Service review are marked before testing.                                 |

If the checklist exposes too many unknowns, the right next step is not to rush into Full Migration. Resolve the unknowns, expand the Demo Migration sample set, or review the service path before committing to final scope.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Commerce pre-migration preparation should make the store’s Joomla-commerce relationships visible. Products need article context, categories need storefront meaning, customers and orders need operational clarity, checkout fields need placement, and apps or customizations need ownership review.

The strongest preparation work separates migrated records from target configuration. It also treats J2Store-origin evidence as practical migration context rather than assuming old behavior will carry forward automatically. When the target environment, product samples, customer and order evidence, URLs, checkout behavior, and extension dependencies are ready for Demo Migration, the project is in a stronger position to choose the right migration scope.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for J2Commerce migration?**

Start with the target Joomla and J2Commerce environment, then prepare product evidence, customer and order samples, checkout fields, URLs, payment methods, shipping methods, apps, plugins, and legacy J2Store dependencies if they exist.

**Why are Joomla articles important in J2Commerce preparation?**

J2Commerce products can depend on Joomla article structure, categories, aliases, metadata, media, publication state, and layout. A product record may be accurate but still unusable if the article and storefront context are incomplete.

**Should J2Store-origin stores be prepared differently?**

Yes. J2Store-origin stores should be reviewed for add-ons, custom fields, template overrides, payment and shipping plugins, order history, checkout behavior, URLs, and custom code before assuming the transition will be straightforward.

**Can tax, shipping, and payment settings be migrated as live behavior?**

Historical tax, shipping, and payment values can often remain visible in orders, but live behavior depends on target configuration. The target store still needs working tax, shipping, payment, checkout, and status settings.

**What should Demo Migration prove for J2Commerce?**

Demo Migration should prove that representative products, article relationships, categories, customers, orders, checkout fields, payment and shipping records, storefront paths, and extension-dependent behavior remain meaningful in J2Commerce.
