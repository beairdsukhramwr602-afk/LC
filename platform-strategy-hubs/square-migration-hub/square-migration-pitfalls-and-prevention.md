# Square Migration Pitfalls and Prevention

Square migration pitfalls usually appear when the project treats Square as a simple destination for product, customer, and order records. Square can support storefront, POS, inventory, customer, order, payment, and online selling workflows, so migration mistakes often come from misunderstanding how those areas connect after launch.

A strong prevention plan does not try to eliminate every small data difference before migration begins. It identifies the assumptions most likely to create launch risk, tests representative records through Demo Migration, separates migrated data from Square-side setup, and defines pass conditions before Full Migration. The goal is to prevent avoidable surprises while keeping the migration scope realistic.

### Pitfall 1: Treating Square Like a Generic Storefront <a href="#pitfall-1-treating-square-like-a-generic-storefront" id="pitfall-1-treating-square-like-a-generic-storefront"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The project is planned as if Square were only a storefront database. Products, customers, and orders may be reviewed, but the team does not check how item library records, POS visibility, inventory locations, payment context, customer profiles, and Square Online presentation work together.

This creates a false sense of readiness. The migration may look complete in record counts while staff still cannot sell representative items correctly, online products are hidden or incomplete, stock belongs to the wrong location, or historical orders are difficult to interpret.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Signal                                                                                             | What it usually means                                                                               |
| -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| The migration scope only names products, customers, and orders.                                    | Square-specific operating areas may be underplanned.                                                |
| POS, online storefront, and inventory are reviewed by separate people without a shared sample set. | The team may miss relationship issues between catalog, stock, and selling channels.                 |
| Demo Migration uses only simple products and ordinary orders.                                      | Edge cases are unlikely to surface before Full Migration.                                           |
| Square-side setup tasks are assumed to migrate from the Source Platform.                           | Payments, checkout, hardware, fulfillment, staff access, and online launch settings may be skipped. |

#### Prevention <a href="#prevention" id="prevention"></a>

Build the migration review around Square’s operating model. Validate item library structure, representative variations and modifiers, inventory by location, customer lookup, historical order context, payment references, Square Online display, and target-side setup as related launch areas.

The migration scope should distinguish migrated records from Square configuration. For example, product information may migrate, but domain setup, live payment methods, hardware, staff permissions, pickup/delivery settings, and connected apps usually need Square-side configuration and testing.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

For a retailer using both POS and Square Online, validate a physical-store item, online-only item, variation-heavy product, discounted order, refunded order, repeat customer, item with stock at more than one location, and product page that must remain visible online.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The team can explain how the migrated result supports real selling, customer support, inventory review, historical order lookup, and Square Online launch. Any remaining gaps are classified as migration correction, Square setup, Add-on adjustment, Custom Service review, accepted limitation, or manual cleanup.

### Pitfall 2: Flattening the Item Library <a href="#pitfall-2-flattening-the-item-library" id="pitfall-2-flattening-the-item-library"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Source products are migrated into Square as basic items without enough attention to variations, options, modifiers, categories, taxes, discounts, pricing rules, images, or item-level relationships. The catalog may appear complete by count, but the selling experience becomes unclear.

This pitfall is common when source platforms use product options, configurable products, bundles, menu choices, add-ons, service options, or app-managed product logic. Square’s item library can represent many selling structures, but unsupported or source-specific behavior must be scoped carefully instead of forced into a flat product record.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Signal                                                                             | Risk                                                                      |
| ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Variants, options, modifiers, and bundles are all described with one generic term. | Important selling choices may be mapped incorrectly.                      |
| Modifier-heavy items are not included in Demo Migration review.                    | Restaurant, service, or customization logic may fail late.                |
| Product images are reviewed only by total count.                                   | Images may attach to the wrong item or fail to support online display.    |
| Categories are checked only by name.                                               | POS grouping, reporting, and Square Online navigation may still be wrong. |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Create a catalog sample set that represents the actual source catalog. Include simple items, variation-heavy items, modifier-heavy items, service items, discounted items, taxable items, image-heavy products, products assigned to multiple categories, and any source behavior that may not have a clean Square equivalent.

Classify each difficult pattern before Full Migration. Some needs can be handled through supported mapping or configuration. Some may require Add-ons. Some need Custom Service review. Some may be better rebuilt directly in Square if they belong to target-side operation rather than migration output.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

For a restaurant moving menu data into Square, validate base menu items, required modifiers, optional add-ons, price-changing choices, taxes, images, and online visibility rather than approving the catalog after item names and prices appear.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative items can be sold, displayed, grouped, and reviewed in Square as intended. Complex product behavior is mapped, configured, escalated, manually rebuilt, or intentionally excluded with an accepted reason.

### Pitfall 3: Misreading Inventory and Location Behavior <a href="#pitfall-3-misreading-inventory-and-location-behavior" id="pitfall-3-misreading-inventory-and-location-behavior"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Inventory is treated as a product-level number rather than a location-sensitive operational record. This can create confusing stock values, wrong store availability, or mismatched online/POS expectations after migration.

The risk grows when the source store has multiple locations, warehouses, pickup/delivery rules, online-only products, POS-only products, reserved stock, negative stock, or manually adjusted quantities. A migrated stock value may be present but not meaningful if the team does not know which location it belongs to and how Square should use it.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Signal                                                                       | Risk                                                                   |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| The scope says “inventory” without naming included locations.                | Stock may migrate without operational context.                         |
| Pickup, delivery, shipping, and POS availability are mixed in source data.   | Selling-channel assumptions may not translate cleanly.                 |
| Inventory is validated before Square locations are confirmed.                | Stock may appear under the wrong location or be hard for staff to use. |
| Negative, reserved, or unavailable quantities are treated as ordinary stock. | Launch stock values may mislead staff and customers.                   |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Define inventory expectations before Full Migration. Confirm active locations, excluded locations, online stock rules, POS stock needs, products that should not appear online, and items where stock should be rebuilt directly in Square.

Validation should test stock for representative item variations across included locations. If stock values cannot be trusted, the team should decide whether to migrate inventory, exclude inventory, correct source data first, or perform a controlled manual stock update in Square.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

For a merchant with two stores and one warehouse, validate stock for one item sold at both stores, one warehouse-only item, one online-only item, one out-of-stock item, and one item with recent stock adjustments.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Inventory quantities are understandable by location, availability expectations are documented, and any stock values not suitable for migration are corrected, excluded, or moved into a separate Square-side setup task.

### Pitfall 4: Confusing Historical Orders With Live Payment Setup <a href="#pitfall-4-confusing-historical-orders-with-live-payment-setup" id="pitfall-4-confusing-historical-orders-with-live-payment-setup"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Migrated historical orders are expected to recreate live Square payment processing, checkout behavior, refund workflows, shipping rules, taxes, fulfillment settings, or staff procedures. The migration result may preserve useful history, but live Square operations still require configuration and testing.

This pitfall can become serious when teams approve launch because historical orders look correct while live checkout has not been tested. Order history and payment history support review; they do not prove that the new Square store can process current transactions correctly.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Signal                                                                          | Risk                                                                       |
| ------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Payment migration is described as reconnecting the payment processor.           | Historical payment context is being confused with live payment setup.      |
| Refunds, tips, service charges, or discounts are not included in order samples. | Exception handling may be hard to interpret later.                         |
| Live checkout testing is postponed until after Full Migration.                  | Payment, tax, fulfillment, or notification issues may surface near launch. |
| Staff assume historical orders prove operational readiness.                     | Target-side Square configuration may still be incomplete.                  |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Validate historical orders for readability, support value, and reconciliation context. Separately test live Square checkout, payment methods, taxes, discounts, shipping, pickup, delivery, fulfillment, notifications, and staff permissions.

Order validation should include ordinary paid orders and exception cases. Payment labels, transaction references, refunds, discounts, service charges, tips, taxes, and fulfillment details should be checked as historical context, not as live setup proof.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

For a service business, validate an ordinary order, a discounted order, a refunded order, an order with a tip or service charge, and an order linked to a customer profile. Then place a new Square test order to confirm live checkout and payment behavior.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Historical orders are readable and useful for support or reporting, and live Square payment, checkout, tax, fulfillment, and notification behavior has been tested separately.

### Pitfall 5: Losing Customer Identity and Buyer Context <a href="#pitfall-5-losing-customer-identity-and-buyer-context" id="pitfall-5-losing-customer-identity-and-buyer-context"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Customers are migrated as contact records, but buyer meaning is weakened. Guest buyers, repeat customers, duplicate profiles, customer-order links, loyalty references, membership fields, CRM details, and external IDs may not be preserved in a way that supports staff lookup or customer service.

Square customer profiles should be validated for practical use, not only field presence. A name and email address may migrate correctly while the team still cannot connect the profile to historical orders, buyer status, or important source-system context.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Signal                                                                          | Risk                                                          |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Guest checkout records are ignored.                                             | Historical orders may lose buyer context.                     |
| Duplicate emails or phone numbers appear in source data.                        | Customer profiles may be confusing after migration.           |
| Loyalty, membership, or subscription details are assumed to be ordinary fields. | App-owned or unsupported data may need Custom Service review. |
| Customer validation does not include order links.                               | Staff may not be able to use migrated customer history.       |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate different customer types: registered customers, guest buyers, repeat buyers, duplicate profiles, customers with multiple addresses, customers with historical orders, and customers with custom fields or external references. Decide which customer details are supported, which need Add-ons, which require Custom Service, and which belong to separate app or integration work.

When customer identity is messy, define the acceptance rule before Full Migration. The team should decide whether duplicates are cleaned before migration, accepted in Square, or handled later through a separate customer-data process.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

For a store with repeat buyers and guest checkout history, validate one registered repeat buyer, one guest buyer, one duplicate email example, one customer with multiple addresses, and one customer tied to a refunded or high-value order.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Customer profiles support lookup, historical order review, and staff understanding. Unsupported customer context is either scoped for Custom Service, handled through Add-ons where appropriate, rebuilt in connected systems, or excluded intentionally.

### Pitfall 6: Treating Square Online as Automatic Storefront Continuity <a href="#pitfall-6-treating-square-online-as-automatic-storefront-continuity" id="pitfall-6-treating-square-online-as-automatic-storefront-continuity"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

The team assumes that migrated Square item-library data automatically produces a complete Square Online launch. Products may exist in Square, but product visibility, page layout, navigation, SEO fields, redirects, domain settings, checkout entry points, and non-product content may still need separate work.

This pitfall often affects merchants coming from platforms where store content, product pages, menus, blog content, and SEO settings are tightly managed in one system. Square Online requires its own presentation and launch validation.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Signal                                                                          | Risk                                                                |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Product migration is treated as website migration.                              | Pages, navigation, URLs, redirects, and domain setup may be missed. |
| Square Online is not included in Demo Migration samples.                        | Customer-facing defects may appear late.                            |
| CMS Pages, Blog Posts, or landing pages are expected to transfer automatically. | Non-product content may require separate scope or manual rebuild.   |
| Redirect planning is deferred until launch week.                                | SEO and traffic continuity may be weakened.                         |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Separate item-library validation from Square Online validation. Confirm which products should appear online, how categories or navigation should work, which URLs matter, which redirects are needed, which pages must be rebuilt, and which domain or launch settings remain Square-side tasks.

Content-heavy stores should review CMS Pages, Blog Posts, landing pages, embedded scripts, reviews, forms, and page-builder content before assuming Square Online can reproduce them through ordinary product migration.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

For a merchant with strong organic traffic, validate top product pages, top category pages, old-to-new redirect plans, homepage links, key content pages, product visibility, out-of-stock behavior, and domain launch settings before approving go-live.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Square Online has a confirmed product display, navigation, URL, redirect, SEO, domain, and launch-setting plan. Non-product content is migrated, rebuilt, scoped for special handling, or intentionally excluded.

### Pitfall 7: Hiding Custom Data Inside Generic Scope <a href="#pitfall-7-hiding-custom-data-inside-generic-scope" id="pitfall-7-hiding-custom-data-inside-generic-scope"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Custom fields, app-managed records, external identifiers, source-platform extensions, marketplace data, loyalty records, subscription details, appointment information, accounting references, or POS-specific fields are described as normal product, customer, or order data. The migration appears scoped, but the requirement is actually unsupported or custom.

This creates late-stage conflict because the team may only discover the gap after Demo Migration or Full Migration. The issue is not always technical complexity. Sometimes the problem is that nobody identified which system owns the data and how the target should use it.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Signal                                                                           | Risk                                                            |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| The source store depends heavily on apps, plugins, modules, or external systems. | Important records may sit outside supported migration behavior. |
| External IDs are needed for accounting, CRM, ERP, loyalty, or reporting.         | Standard mapping may not preserve operational continuity.       |
| Custom fields are mentioned without examples.                                    | Scope cannot be evaluated accurately.                           |
| The team expects Square to reproduce source-specific workflows exactly.          | Target-side differences or custom work may be underplanned.     |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Create a custom-data inventory before confirming scope. For each custom field or app-owned record, identify the source owner, business purpose, target expectation, sample record, likely handling path, and validation proof. Separate supported Add-on needs from Custom Service needs.

Add-ons are suitable for bounded filtering, mapping, or configuration within supported behavior. Custom Service is needed for unsupported records, custom fields, external identifiers, app-owned data, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

For a merchant with ERP item IDs and loyalty membership fields, provide sample products, customers, orders, and the expected Square-side use. If the fields must remain connected to reporting or support workflows, treat the requirement as Custom Service review rather than ordinary mapping.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Every custom or external-data expectation is classified as supported migration scope, Add-on adjustment, Custom Service review, Square-side setup, third-party integration work, manual rebuild, or accepted exclusion.

### Pitfall 8: Using the Wrong Later Migration Action <a href="#pitfall-8-using-the-wrong-later-migration-action" id="pitfall-8-using-the-wrong-later-migration-action"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

The merchant continues selling on the Source Platform after an earlier migration run but does not decide whether the next action should continue from the previous setup, continue with changed configuration, or perform a new migration. The team assumes every additional migration action has the same effect.

This can create mismatched validation. Continuing a migration is often reviewed for newly added source records and selected regression samples. A new migration may replace the earlier migrated target result and requires a broader target review. If the team uses the wrong expectation, it may approve the wrong result.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Signal                                                                      | Risk                                                                     |
| --------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| The team says “run it again” without defining the intended action.          | Scope, target result, and validation expectations are unclear.           |
| Source data changed after Demo Migration, but no launch-window plan exists. | New products, orders, customers, or Blog Posts may be missed.            |
| Configuration changes are requested after an earlier migration.             | Validation must include the changed fields, filters, or mapping choices. |
| A refreshed target result is expected but only new records are reviewed.    | Old migrated data may remain or be replaced differently than expected.   |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Decide the intended migration action before execution. Use continuation from the previous setup when the goal is to add newly created source records under the same configuration. Use continuation with a new configuration when field mapping, filtering, or setup choices need adjustment before continuing. Use a new migration when the earlier target result should be replaced with a refreshed scope.

The validation plan should follow the selected action. The team should also understand that Entity Points consumption depends on whether entities are new to the migration license record, not merely on whether another migration action occurs on the same migration path.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant completes Demo Migration, keeps selling for two weeks, and adds new products and orders. If the configuration remains acceptable, continuation from the previous setup may be enough. If the merchant also changes mapping rules, continuation with a new configuration needs validation of the changed mapping. If the target result should be rebuilt from a refreshed scope, a new migration requires broader validation.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

The team can state which migration action is being used, what data should be affected, whether configuration is changing, what target result is expected, and how validation will prove that outcome.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Square migration pitfalls are preventable when the project is planned around Square’s real operating model. Item library structure, variations, modifiers, inventory locations, order and payment history, customers, Square Online, custom data, and later migration actions all need clear expectations before launch.

The strongest prevention method is practical: define representative samples, separate migrated data from Square-side setup, classify unsupported or custom expectations early, validate Square Online separately from the item library, and choose later migration actions deliberately. A Square migration is ready when the team can prove that the target environment supports real selling, customer service, inventory review, order lookup, and online launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Square migration issues often appear late?**

They often appear late because Square records are connected to operational workflows. A product may migrate, but staff selling, inventory location, online visibility, customer lookup, and order history may still need review. Late issues usually mean the validation samples were too narrow.

**What is the most common Square catalog mistake?**

The most common catalog mistake is flattening variations, modifiers, categories, taxes, discounts, images, or source-specific product logic into simple item records. The migration may look complete by count but still fail in real selling or online display.

**How should inventory problems be prevented?**

Confirm locations, selling channels, included stock values, excluded stock values, and unusual stock states before Full Migration. Validate item variation stock across representative locations rather than reviewing one total quantity per product.

**Should Square Online be treated as part of product migration?**

Square Online should be validated as a related but separate launch area. Product records may feed online display, but pages, navigation, redirects, domains, SEO fields, non-product content, and checkout entry points still need their own readiness checks.

**When does custom Square migration scope need Custom Service review?**

Custom Service review is needed when the requirement involves unsupported records, custom fields, app-owned data, external identifiers, bespoke transformations, Custom Platform handling, or custom migration logic adjustment beyond supported migration behavior.

**How can teams avoid confusion after an earlier migration run?**

Before another migration action, define whether the goal is to continue from the previous setup, continue with changed configuration, or perform a new migration. Then validate the exact outcome expected from that action.
