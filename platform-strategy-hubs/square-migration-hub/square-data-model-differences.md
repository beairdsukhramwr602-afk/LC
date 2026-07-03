# Square Data Model Differences

Square data-model planning should start with a practical question: after migration, will the data work inside Square’s selling environment, or will it merely appear as transferred records? Square is not only an online storefront destination. It connects the item library, Point of Sale usage, inventory, locations, orders, payments, customers, and Square Online presentation into one operating environment.

That makes Square different from Source Platforms that organize commerce mainly around storefront products, category pages, customer accounts, and web orders. A source product option may become a Square item variation, a modifier, target-side setup, or Custom Service scope depending on how the choice is used. A source category may be useful as a Square catalog category, but the same category may also have been a navigation page, SEO landing page, menu entry, or collection rule in the old storefront. A source order may preserve useful history, but it does not automatically configure live payment processing, hardware, fulfillment workflows, or operational reporting in Square.

The goal is not to force every source field into Square. The goal is to preserve the parts of the old store that still create value when they become Square catalog data, customer context, order history, inventory evidence, Square Online content, or clearly defined Custom Service scope.

### Square Data Meaning Starts With the Item Library <a href="#square-data-meaning-starts-with-the-item-library" id="square-data-meaning-starts-with-the-item-library"></a>

Square organizes products and services through the item library. Items, item variations, categories, modifiers, taxes, discounts, pricing rules, images, and related catalog objects can affect selling, display, reporting, and inventory interpretation. That means product migration should not be judged only by whether product names and SKUs arrive. The stronger test is whether the migrated catalog can be sold, found, edited, reported on, and validated in the way the merchant expects.

A storefront-first Source Platform may allow catalog structures that look familiar but behave differently from Square. A Shopify product, WooCommerce variable product, Magento configurable product, BigCommerce product option, or custom-platform product table may all describe sellable choices, but Square needs those choices to become usable item and variation structures. A product that looked clean online can become difficult in Square if its options were actually sale-time add-ons, bundle logic, hidden custom fields, or app-managed rules.

| Source structure                      | Square interpretation question                                                    | Migration implication                                                                    |
| ------------------------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Simple product                        | Is one Square item and one sellable variation enough?                             | Usually straightforward when SKU, price, tax, and image behavior are clear.              |
| Variant product                       | Do options represent true sellable versions?                                      | Variations should preserve SKU-level selling, inventory, and display meaning.            |
| Product add-on                        | Is the choice a modifier rather than a variation?                                 | Sale-time choices should not be forced into variant structure without review.            |
| Bundle, kit, or package               | Is it a real Square catalog structure, target-side setup, or Custom Service need? | Bundle logic can create scope risk when inventory or pricing depends on custom behavior. |
| Category, collection, or landing page | Is the structure catalog organization, storefront navigation, or SEO content?     | Category migration should not be confused with Square Online site setup.                 |

The item library is therefore the anchor for Square data translation. Products should not simply be “mapped”; they should be interpreted according to how Square will use them.

### Items, Variations, Options, and Modifiers Need Separate Treatment <a href="#items-variations-options-and-modifiers-need-separate-treatment" id="items-variations-options-and-modifiers-need-separate-treatment"></a>

The most important Square catalog distinction is often the boundary between item variations and modifiers. A variation represents a sellable version of an item, such as a size, color, unit, package, or service format. A modifier usually represents a sale-time choice that adjusts the item during checkout, such as toppings, add-ons, preparation choices, gift wrapping, or optional service additions.

This distinction matters because the old platform may not store the boundary cleanly. Some stores treat every choice as a variant. Others use plugins, apps, custom fields, option tables, or theme logic to create choices that look like variants online but behave like modifiers operationally. If modifier-like choices become item variations, staff may face cluttered product lists, inventory may be interpreted incorrectly, and Square Online customers may see confusing product combinations. If true variations become modifiers, SKU-level inventory and reporting can lose meaning.

A strong Square data review should classify product choices before migration:

| Choice type                                              | Better Square direction                               | Reason to check                                                                                             |
| -------------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Size, color, unit, material, flavor, package             | Item variation                                        | These often define distinct sellable versions.                                                              |
| Extra topping, engraving, gift wrap, preparation choice  | Modifier or modifier list                             | These often adjust the sale without creating a separate stock item.                                         |
| Subscription, recurring option, or appointment-like rule | Platform setup, integration, or Custom Service review | These may not be ordinary catalog data.                                                                     |
| Kit, bundle, component-based product                     | Scope review or Custom Service                        | The source logic may depend on inventory or pricing rules Square does not receive as simple product fields. |
| Hidden app field or external ID                          | Supported mapping, Add-on, or Custom Service          | The value may be important for reporting or integrations but may not belong in visible catalog content.     |

This review improves both migration accuracy and merchant usability. Square catalog data should support how the team will actually sell, not only how the old storefront displayed options.

### Categories, Navigation, and Square Online Should Not Be Treated as One Object <a href="#categories-navigation-and-square-online-should-not-be-treated-as-one-object" id="categories-navigation-and-square-online-should-not-be-treated-as-one-object"></a>

Source platforms often combine category structure, collection rules, menu navigation, URL paths, filters, and SEO landing pages. Square can organize items through categories, but Square Online site presentation may require separate planning for pages, navigation, SEO fields, domains, redirects, and storefront layout. That separation is one of the most common data-model gaps in Square migration.

A source category might have served several roles at once. It may have grouped products in the admin, generated a public collection page, appeared in the main menu, supported filtered browsing, and carried a valuable indexed URL. In Square, those roles should be reviewed individually. Product grouping may be part of catalog migration. Menu hierarchy, content blocks, homepage merchandising, redirects, and domain behavior may be Square Online setup or validation work.

| Source role                                   | Square planning decision                                                            |
| --------------------------------------------- | ----------------------------------------------------------------------------------- |
| Admin product grouping                        | Decide whether it should become a Square catalog category.                          |
| Public category page                          | Decide whether Square Online needs a page, navigation entry, or redirect.           |
| SEO landing page                              | Decide whether content should migrate, be rebuilt, redirected, or retired.          |
| Menu hierarchy                                | Treat as storefront setup and validation, not only catalog data.                    |
| Product filter, tag, or rule-based collection | Review whether it has Square value or requires exclusion, setup, or Custom Service. |

This does not make Square Online less important. It makes Square Online more important to plan correctly. Catalog transfer can put the right items into Square, but storefront readiness depends on whether customers can browse, search, land on important URLs, and understand product presentation after launch.

### Inventory and Location Data Depend on Sellable Variations <a href="#inventory-and-location-data-depend-on-sellable-variations" id="inventory-and-location-data-depend-on-sellable-variations"></a>

Square inventory planning is tied to item variations and business locations. A source store may store one stock value per SKU, warehouse quantities, location quantities, marketplace inventory, backorder states, preorder flags, or channel availability. Square migration should identify which stock information remains meaningful after the catalog becomes Square items and variations.

Single-location merchants may only need basic stock validation. Multi-location merchants need more careful interpretation. A global source quantity may not explain which Square location should hold the inventory. A warehouse field may not be equivalent to a Square selling location. Products sold online but not in-store, or in-store but not online, may require visibility and fulfillment review beyond raw stock numbers.

Inventory review should focus on usable evidence:

| Inventory question                                                    | Why it matters in Square                                                             |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Does every stock-managed variation have a reliable SKU or identifier? | Square inventory depends on item variation precision.                                |
| Are quantities global, warehouse-specific, or store-specific?         | Location assignment affects operational trust.                                       |
| Are backorders, negative stock, or preorder states used?              | These may not translate as equivalent Square behavior.                               |
| Are some items excluded from online sale?                             | Catalog visibility and Square Online display may need separate setup.                |
| Do bundles or kits consume component stock?                           | Component inventory logic can require Custom Service review or target-side handling. |

Inventory should never be validated only by total counts. A catalog can have the right number of products but still fail operationally if inventory is attached to the wrong variation, interpreted at the wrong location, or disconnected from the merchant’s selling workflow.

### Orders, Payments, Fulfillment, and Refunds Carry Historical Meaning <a href="#orders-payments-fulfillment-and-refunds-carry-historical-meaning" id="orders-payments-fulfillment-and-refunds-carry-historical-meaning"></a>

Order migration into Square should preserve commercial history where supported, but historical order data and live Square payment setup are different concerns. A source order may include order numbers, dates, line items, totals, taxes, discounts, shipping charges, tips, service charges, fulfillment status, refunds, customer links, payment method labels, transaction references, gift card usage, marketplace IDs, and staff notes. Not every part of that history becomes active Square functionality.

The right question is whether order history remains useful for support, lookup, reporting context, and customer review. A merchant may need staff to answer “What did this customer buy?”, “Was this item refunded?”, “Which discount was applied?”, or “Which fulfillment status did the old order have?” Those questions require meaningful order context, not just a total and date.

Payment-related fields need particular care. Preserving historical payment labels or references can help order interpretation, but it does not configure Square to process future payments, connect hardware, set up checkout, or reconcile old processor data as live Square payment activity. The same principle applies to fulfillment and refunds: historical meaning may migrate where supported, while active operational workflows should be configured and tested in Square.

### Customer Profiles Are Not Always Source Customer Accounts <a href="#customer-profiles-are-not-always-source-customer-accounts" id="customer-profiles-are-not-always-source-customer-accounts"></a>

Square customer profiles should be interpreted as buyer identity and relationship context, not as a guaranteed equivalent of every source customer account feature. Source platforms may include registered accounts, guest buyers, newsletter subscribers, customer groups, wholesale roles, B2B permissions, loyalty records, saved addresses, tax exemptions, subscriptions, CRM IDs, and marketplace identities. Some of that information may fit supported Square customer data; some may require Add-ons, Custom Service, target-side configuration, or exclusion.

Customer migration should be planned around how staff and the business will use buyer information after launch. If customers are mainly used for lookup and support, names, emails, phone numbers, addresses, and order links may matter most. If the source platform used customer groups, tax logic, wholesale permissions, or loyalty behavior, the migration plan should not imply that those rules become native Square customer functionality without review.

Duplicate and inconsistent customer records deserve special attention. A person may appear under several emails or phone numbers. Guest buyers may have order history but no account-style identity. CRM and loyalty identifiers may live outside standard commerce data. These patterns can make customer data appear complete while making it difficult for staff to identify repeat buyers or interpret history.

### Taxes, Discounts, Pricing Rules, and Business Logic Need Scope Boundaries <a href="#taxes-discounts-pricing-rules-and-business-logic-need-scope-boundaries" id="taxes-discounts-pricing-rules-and-business-logic-need-scope-boundaries"></a>

Square catalog data can include taxes, discounts, and pricing-related objects, but source platforms often implement business logic in many different ways. Discount rules may come from coupon engines, customer groups, apps, loyalty programs, product bundles, subscription systems, or custom code. Tax behavior may come from platform settings, tax apps, regional rules, marketplace channels, or manual overrides.

The migration plan should separate portable data from target-side business setup. A tax name or discount record may be migrated where supported, but that does not mean the exact old checkout logic, customer eligibility rule, or promotional automation is recreated in Square. This distinction protects merchants from assuming that historical pricing behavior and future selling configuration are the same thing.

| Business logic area    | Scope question                                                                  |
| ---------------------- | ------------------------------------------------------------------------------- |
| Tax records            | Are these historical references, active tax setup, or both?                     |
| Discounts and coupons  | Are they simple records or rule-driven promotion logic?                         |
| Customer-group pricing | Does Square support the intended behavior natively, or is another setup needed? |
| Bundled discounts      | Is the rule part of catalog data, app logic, or custom behavior?                |
| External pricing IDs   | Are they needed for accounting, ERP, loyalty, or reporting continuity?          |

When business logic is outside supported behavior, Custom Service may be required. When the data is supported but needs filtering, mapping, or configuration adjustment, Add-ons may be enough. The two should not be treated as interchangeable.

### App, Integration, and Custom Data Should Be Classified Before Migration <a href="#app-integration-and-custom-data-should-be-classified-before-migration" id="app-integration-and-custom-data-should-be-classified-before-migration"></a>

Square merchants may use accounting systems, loyalty programs, delivery platforms, restaurant tools, appointment systems, retail integrations, marketplaces, CRMs, reporting tools, or custom operational workflows. Source platforms may also contain app/plugin/module data that has no direct Square equivalent. This data should be classified before migration because it can affect scope, cost, validation, and expectations.

A useful classification separates supported records from decision-dependent data:

| Data type                                                                   | Likely handling direction                                                    |
| --------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Supported product, customer, order, and content records                     | Standard Service or Managed Service may be suitable depending on complexity. |
| Supported records needing filtering or mapping adjustment                   | Add-ons may help when the requirement stays within supported behavior.       |
| Custom fields, external IDs, app-owned metadata, or bespoke transformations | Custom Service review may be needed.                                         |
| Unsupported app/plugin/module data                                          | Treat as Custom Service scope, manual setup, or excluded expectation.        |
| Live integration configuration                                              | Usually target-side setup and validation, not ordinary migrated content.     |

This classification should happen before the migration scope is finalized. Otherwise, the merchant may count fields as “data to migrate” even though the real requirement is integration planning, custom transformation, or target-side configuration.

### Square Data Scope Should Be Judged by Usable Outcome <a href="#square-data-scope-should-be-judged-by-usable-outcome" id="square-data-scope-should-be-judged-by-usable-outcome"></a>

Square data-model review should end with an acceptance question: does the migrated data support the way the business will use Square? A product should be sellable. A variation should make sense for inventory and display. A modifier should support sale-time choice. A category should help catalog or storefront organization. A customer profile should support useful lookup. An order should preserve meaningful historical context. A URL or page should support launch continuity where included.

Entity Points help plan selected entity volume, but they do not replace data-model analysis. Counting products, customers, orders, or Blog Posts does not prove that source fields, option logic, app metadata, or storefront behavior fit Square. Entity Points should be considered alongside scope, supported behavior, Add-ons, Custom Service needs, and validation evidence.

For Square, the best data scope is not the largest possible transfer. It is the scope that preserves operational value while clearly separating migrated records, Square-side setup, supported configuration adjustments, custom requirements, and excluded expectations.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Square data model differences matter because migrated records become part of a POS-connected commerce environment, not only an online catalog. Products, variations, modifiers, categories, inventory, locations, customers, orders, payments, Square Online content, URLs, taxes, discounts, integrations, and custom fields should be reviewed for Square meaning before the migration scope is accepted. The strongest Square migration plan preserves useful business data while separating supported migration behavior from Add-ons, Custom Service needs, target-side setup, and expectations that should not be promised as ordinary transfer.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why does Square migration focus so much on the item library?**

The item library is central to how Square organizes products, services, variations, modifiers, categories, taxes, discounts, inventory links, orders, and selling behavior. If catalog data is migrated without item-library meaning, products may exist in Square but remain hard to sell, validate, or report on.

**Are Square item variations the same as product variants on every source platform?**

No. A source variant may become a Square variation when it represents a true sellable version of an item. A sale-time choice may be better handled as a modifier, while bundle logic, subscription rules, app fields, or custom product behavior may require separate review.

**Can historical payment data configure Square payment processing?**

No. Historical payment context can help interpret past orders where supported, but live Square payment processing, checkout setup, hardware, and payment account configuration are Square-side operational setup tasks.

**Do Entity Points prove that every source field can migrate to Square?**

No. Entity Points help plan selected entity volume. They do not guarantee that every source field, app record, custom attribute, or business rule has a supported Square destination.

**When should Square data require Custom Service review?**

Custom Service should be considered when the migration requirement involves unsupported app data, custom fields, external identifiers, bespoke transformation, bundle or business-rule logic, custom migration logic adjustment, or source behavior that does not fit supported Square migration behavior.
