# Square Validation Priorities

A Square migration should be validated as an operating environment, not only as a set of imported records. Products may appear in the Square item library, but the result is not ready until item variations, modifiers, categories, images, taxes, discounts, inventory locations, customer profiles, historical orders, payment references, Square Online visibility, and connected workflows make sense together.

Validation should prove that Square can support the merchant’s real selling model after migration. A catalog that looks complete in a dashboard can still fail when staff cannot sell the right item variation, online customers cannot find the expected product page, inventory is attached to the wrong location, or historical orders lose useful payment and fulfillment context. The safest review sequence moves from structural accuracy to operational usability.

### What Square Validation Should Prove <a href="#what-square-validation-should-prove" id="what-square-validation-should-prove"></a>

Square validation should prove that migrated data is usable in Square’s item library, POS-connected workflows, inventory review, customer lookup, historical order reference, and online selling environment. A simple count comparison is only the starting point. The stronger proof is whether representative migrated records behave as expected for staff, customers, support teams, and reporting users.

The validation standard should answer five practical questions:

| Validation question                   | Square-specific proof needed                                                                                                        |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Are the migrated records present?     | Products, customers, orders, categories, images, and supported related records appear in the expected Square areas.                 |
| Do the records preserve meaning?      | Item variations, modifiers, categories, taxes, discounts, customer links, and order line items reflect the intended source meaning. |
| Are operational relationships usable? | Inventory, locations, Square Online visibility, order history, and customer context can be reviewed without confusion.              |
| Are target-side tasks separated?      | Payments, checkout, staff access, hardware, fulfillment, domain, redirects, and integrations are not mistaken for migrated data.    |
| Is launch risk controlled?            | The team knows which findings are acceptable, which need correction, and which require Square-side setup or service escalation.     |

The review should include both ordinary and difficult examples. A store with simple products should still test variations, images, categories, customer-order links, and Square Online display if those areas exist. A store with restaurant, service, multi-location, or omnichannel behavior should validate modifier-heavy items, location-specific stock, pickup or delivery examples, and orders with discounts, taxes, refunds, tips, or service charges.

### Validate the Item Library Before Checking Presentation <a href="#validate-the-item-library-before-checking-presentation" id="validate-the-item-library-before-checking-presentation"></a>

The Square item library is the foundation for many other checks. It contains the merchant’s products or services and the catalog relationships that support selling, reporting, and online display. Validation should begin by confirming that migrated items are not merely present, but structured in a way Square can use.

A practical review should include simple items, variation-heavy items, modifier-heavy items, items with images, items assigned to categories, discounted items, taxable items, service items, online-only items, POS-only items, and items that represent unusual source behavior. The goal is not to review every product manually. The goal is to prove that the migration pattern works for every important product type and selling scenario.

| Item-library area      | What to validate                                                                                        | Failure signal                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Items and item names   | Product or service names are readable and assigned to the right record type.                            | Item count is correct but names are duplicated, truncated, or confusing.                |
| Variations and options | Size, color, package, service, or unit choices appear as usable Square variations where supported.      | Source options become flat text or separate products without a clear reason.            |
| Modifiers              | Add-ons, toppings, service choices, or sale-time adjustments are represented correctly where supported. | Staff cannot reproduce common selling choices in Square.                                |
| Categories             | Categories help grouping, POS use, reporting, or Square Online organization.                            | Categories exist but do not support actual selling or navigation needs.                 |
| Images                 | Important product images are attached to the correct items or variations where supported.               | Images appear mismatched, missing, duplicated, or assigned to the wrong product.        |
| Taxes and discounts    | Historical or catalog-related values preserve reviewable meaning.                                       | The team treats migrated history as proof that live tax and discount setup is finished. |

The merchant should validate item-library samples before spending too much time on Square Online presentation. If item structure is wrong, online pages, menus, categories, and checkout-adjacent display will be harder to interpret.

### Validate Inventory and Location Meaning <a href="#validate-inventory-and-location-meaning" id="validate-inventory-and-location-meaning"></a>

Square inventory validation should confirm where stock belongs and what the migrated stock value is supposed to mean. A single product quantity is not enough when the merchant uses physical locations, online selling, pickup, delivery, warehouse stock, event sales, or POS-only availability. Location meaning must be validated before launch because staff may rely on Square for real selling decisions.

Inventory review should begin with the locations included in the migration scope. The team should know whether each location is active, retired, online-facing, POS-only, warehouse-like, or excluded. Then it should validate item variation stock for representative products across those locations.

| Inventory validation area | Review method                                                                                      |
| ------------------------- | -------------------------------------------------------------------------------------------------- |
| Included locations        | Confirm which Square locations should receive stock values.                                        |
| Excluded locations        | Confirm that old, closed, test, or irrelevant locations did not create misleading stock.           |
| Variation-level stock     | Check that stock attaches to the correct item variation, not only the parent item.                 |
| Online availability       | Confirm which items should appear online and whether stock should affect visibility or purchasing. |
| POS availability          | Confirm that staff can find and sell the expected items in the right location context.             |
| Unusual stock values      | Review negative, reserved, unavailable, backordered, or manually adjusted stock values.            |

Inventory findings should be classified carefully. Some differences are migration issues. Some are Square-side configuration tasks. Some are expected limitations because the source platform and Square define stock availability differently. The validation report should state which type of issue each finding represents.

### Validate Historical Orders and Payment Context <a href="#validate-historical-orders-and-payment-context" id="validate-historical-orders-and-payment-context"></a>

Historical order validation should focus on readability, support value, and financial context. Migrated orders do not replace the need to configure and test live Square payment processing, checkout, fulfillment, tax, shipping, pickup, delivery, or notifications. They should preserve enough context for customer support, operational review, reconciliation, and historical lookup.

Order samples should include ordinary orders and edge cases. A good Square validation set includes paid orders, refunded orders, discounted orders, taxed orders, orders with multiple items, orders tied to customer profiles, orders with shipping or pickup context, orders with tips or service charges where relevant, and orders that include source-specific references.

| Order area                   | What to check                                                                              | Why it matters                                                                 |
| ---------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Order line items             | Items, quantities, prices, discounts, taxes, and totals are understandable.                | Staff need order history that can be interpreted without source-system access. |
| Customer links               | Orders connect to the expected customer profile where supported.                           | Support teams need buyer context.                                              |
| Payment labels or references | Payment context is readable as historical information.                                     | Historical payments should not be mistaken for live processor setup.           |
| Refunds and adjustments      | Refund, cancellation, tip, service charge, or adjustment examples preserve useful meaning. | Financial history can be misleading if exceptions are not checked.             |
| Fulfillment context          | Pickup, delivery, shipping, or fulfillment fields are readable where supported.            | Operational teams need to understand past order handling.                      |

The key validation distinction is between historical context and live Square operation. Historical records help the team look backward. Live Square configuration must be tested separately by placing new orders, testing payment methods, verifying fulfillment settings, and confirming staff permissions.

### Validate Customers and Buyer Identity <a href="#validate-customers-and-buyer-identity" id="validate-customers-and-buyer-identity"></a>

Square customer validation should confirm that customer profiles remain useful after migration. Customer data can look correct at a field level while still losing buyer identity, duplicate handling, customer-order relationships, loyalty context, membership meaning, or external references.

The review should include registered customers, guest buyers, repeat buyers, customers with multiple orders, customers with incomplete contact details, duplicate email or phone examples, customers with notes or custom fields, and customers tied to historical orders. If the source store uses loyalty, subscriptions, memberships, B2B accounts, CRM records, or external IDs, the team should decide whether those fields are supported, require Add-ons, require Custom Service, or should remain outside the migration scope.

| Customer validation area | Proof required                                                                                     |
| ------------------------ | -------------------------------------------------------------------------------------------------- |
| Contact fields           | Names, emails, phone numbers, addresses, and notes are readable where supported.                   |
| Buyer identity           | Guest buyers and registered customers retain practical support context.                            |
| Customer-order links     | Representative historical orders connect to the right customer profile where supported.            |
| Duplicate handling       | Duplicate emails, phone numbers, or names are understood and documented.                           |
| Custom information       | Loyalty, membership, CRM, external ID, or app-managed fields are handled through the correct path. |

Customer validation should avoid assuming that a source customer account is the same thing as a Square customer profile. The important launch question is whether the migrated result supports customer lookup, service continuity, and historical order review.

### Validate Square Online and Storefront Continuity <a href="#validate-square-online-and-storefront-continuity" id="validate-square-online-and-storefront-continuity"></a>

Square Online validation should confirm what appears to customers and what still needs target-side setup. The item library and Square Online presentation are related, but they are not the same review area. A product can exist in Square without being displayed online as expected. A Square Online page can exist while SEO, redirects, domains, navigation, or content presentation still need work.

A Square Online review should include product pages, category or collection-like navigation, page titles, descriptions, images, product visibility, out-of-stock display, homepage links, menu links, redirects, domain readiness, and checkout entry points. If the source store used CMS Pages, Blog Posts, landing pages, page-builder content, custom scripts, or app-driven content blocks, those expectations should be validated separately from item migration.

| Square Online area         | What to verify                                                                                       |
| -------------------------- | ---------------------------------------------------------------------------------------------------- |
| Product display            | Products, images, prices, options, modifiers, and descriptions appear clearly where expected.        |
| Navigation                 | Categories, pages, links, and menus support the intended customer journey.                           |
| URLs and redirects         | Important old URLs have an accepted handling plan.                                                   |
| SEO fields                 | Titles, descriptions, and visible content are reviewed where included in scope.                      |
| Domain and launch settings | Domain, SSL, checkout entry, and launch settings are confirmed in Square.                            |
| Non-product content        | CMS Pages, Blog Posts, custom landing pages, or scripts are scoped, excluded, or handled separately. |

Square Online findings should not be treated only as design preferences. A missing redirect, hidden product, mismatched item option, or broken navigation path can affect revenue, SEO continuity, and launch confidence.

### Validate Integrations, Custom Data, and Special Handling <a href="#validate-integrations-custom-data-and-special-handling" id="validate-integrations-custom-data-and-special-handling"></a>

Square migrations often involve information that comes from outside the core source platform: apps, plugins, accounting systems, POS systems, loyalty tools, CRM platforms, marketplaces, restaurant tools, booking systems, or custom databases. Validation should confirm whether those records were included, excluded, mapped through Add-ons, reviewed through Custom Service, or left for separate integration work.

Add-ons and Custom Service should remain separate during validation. Add-ons can support bounded filtering, mapping, or configuration within supported behavior. Custom Service is needed when the requirement involves unsupported records, custom fields, app-owned data, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

| Validation finding                                                               | Likely handling path                   |
| -------------------------------------------------------------------------------- | -------------------------------------- |
| Supported field needs a different destination                                    | Advanced Data Mapping may be enough.   |
| Obsolete records should be excluded                                              | Data Filter Add-on may be enough.      |
| Supported records need bounded configuration                                     | Advanced Data Configure may be enough. |
| App-owned loyalty, subscription, or marketplace data is expected                 | Custom Service review is needed.       |
| External IDs must remain connected to ERP, CRM, accounting, or reporting systems | Custom Service review is needed.       |
| Square-side integration must be installed or configured                          | Target-side setup, not migrated data.  |

A validation report should identify special-handling findings early enough to prevent launch surprises. Unsupported expectations should not remain hidden inside a generic “to review later” note.

### Validate Later Migration Activity Before Launch <a href="#validate-later-migration-activity-before-launch" id="validate-later-migration-activity-before-launch"></a>

Many merchants continue selling on the Source Platform while reviewing Demo Migration or preparing for launch. That creates a timing issue: the validation result may be accurate for the first migration run but incomplete for newly created source records. Square validation should therefore include a launch-window decision about whether the merchant expects one migration action, continuation from a previous migration setup, continuation with changed configuration, or a new migration into a refreshed target result.

The distinction matters because each action changes what should be validated afterward. Continuing from a previous setup usually focuses on newly added source records and selected regression samples. Continuing with changed configuration requires validation of the changed configuration and representative records affected by the change. Performing a new migration requires checking whether the target result reflects the refreshed scope and whether earlier migrated target data has been replaced as intended.

| Later migration action                    | Validation emphasis                                                                                       |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Continue with the last used configuration | Newly added source records and regression samples from previously migrated data.                          |
| Continue with a new configuration         | Newly migrated records plus the fields, filters, or mapping choices affected by the configuration change. |
| Perform a new migration                   | Refreshed target result, replaced earlier migrated data, scope accuracy, and launch-readiness samples.    |

Entity Points should be interpreted correctly during planning. Continuing migration activity or performing a new migration may consume Entity Points for newly migrated eligible entities, but already recorded entities do not consume Entity Points again just because another migration action occurs on the same migration path.

### Build a Square Validation Report <a href="#build-a-square-validation-report" id="build-a-square-validation-report"></a>

A Square validation report should be practical enough for launch decisions. It should not simply list screenshots or say that records were checked. Each finding should identify the record, the expected result, the observed result, the severity, the handling path, the owner, and the final status.

| Report field     | Purpose                                                                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Record or sample | Identifies the item, variation, modifier, order, customer, page, URL, or inventory record being reviewed.                                     |
| Expected result  | States what the migrated outcome should look like.                                                                                            |
| Observed result  | Describes what actually appears in Square.                                                                                                    |
| Severity         | Separates launch blockers from minor cleanup.                                                                                                 |
| Handling path    | Classifies the issue as migration correction, Add-on adjustment, Custom Service review, Square setup, accepted limitation, or manual cleanup. |
| Owner            | Assigns responsibility to the merchant, Next-Cart, Square-side setup team, or external partner.                                               |
| Status           | Confirms whether the issue is open, corrected, accepted, or deferred.                                                                         |

The report should include enough representative samples to prove the migration pattern, not only isolated examples that are easy to pass. A weak validation report can approve a migration that still fails in POS selling, Square Online launch, customer support, or inventory operation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Square validation should prove that migrated data supports the merchant’s real target operation. The item library, variations, modifiers, categories, inventory locations, historical orders, payment context, customer profiles, Square Online presentation, integrations, and later migration timing all affect launch confidence.

The strongest validation process begins with representative samples, separates migrated records from Square-side setup, classifies findings by handling path, and confirms whether the result is usable for selling, support, reporting, and online launch. A Square migration should not be approved only because record counts look correct. It should be approved because the migrated result makes operational sense inside Square.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is record-count matching enough to validate a Square migration?**

No. Record counts are useful for completeness checks, but Square validation also needs meaning checks. Items, variations, modifiers, categories, inventory, order context, customers, Square Online display, and integration assumptions must be reviewed through representative samples.

**Should Square Online be validated separately from the item library?**

Yes. The Square item library controls core product and catalog structure, while Square Online controls customer-facing presentation, navigation, URLs, redirects, domains, and online launch settings. A product can exist in the item library without being ready for online sale.

**What order samples are most useful for Square validation?**

Use ordinary orders and exception examples: discounted orders, taxed orders, refunded orders, partially fulfilled orders, orders linked to customers, orders with tips or service charges where relevant, and orders with pickup, delivery, or shipping context.

**When should Add-ons be reviewed during validation?**

Add-ons should be reviewed when supported filtering, mapping, or configuration affects the expected result. If the issue involves unsupported records, custom fields, app-owned data, or external identifiers, Custom Service review is the more appropriate path.

**Does continuing migration activity change what needs to be validated?**

Yes. When migration activity continues after an earlier run, validation should check newly added source records and representative existing records. If configuration changes or a new migration is performed, the team should validate the affected scope, replaced results, and launch-critical samples again.
