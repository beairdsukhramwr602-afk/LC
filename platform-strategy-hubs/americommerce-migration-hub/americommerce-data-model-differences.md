# AmeriCommerce Data Model Differences

A migration to AmeriCommerce should not be judged only by whether products, customers, and orders appear in the Target Platform. AmeriCommerce is built for merchants whose commerce data often carries business rules, buyer relationships, storefront context, pricing logic, fulfillment meaning, and integration dependencies. When those layers exist in the Source Platform, the migration has to preserve the commercial meaning behind the records, not only their visible fields.

The main data-model question is simple: _does each migrated record still support the way the merchant sells, prices, segments buyers, presents products, and fulfills orders after launch?_ A product that appears in the catalog may still be incomplete if its kit structure, subscription context, restricted availability, or technical attributes are lost. A customer record may still be incomplete if it no longer carries the buyer type, portal access, pricing relationship, or tax context that shaped the account. An order may still be incomplete if it loses the invoice, payment, vendor, fulfillment, or integration context needed for business review.

AmeriCommerce can be a strong destination for complex commerce models, but that strength also makes data-model interpretation more important. The clearer the source structure is before migration, the easier it is to decide what should become native AmeriCommerce data, what should be configured after migration, what should be validated through representative samples, and what requires Custom Service.

### Core Data Model Layers in AmeriCommerce <a href="#core-data-model-layers-in-americommerce" id="core-data-model-layers-in-americommerce"></a>

AmeriCommerce data should be understood as a set of connected business layers. These layers may not exist in the same form on the Source Platform, and the migration plan should account for how each layer will be represented after translation.

| Data-model layer                      | What it may include                                                                                                                         | Why it matters during migration                                                                                                                                         |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Catalog and product structure**     | Products, product groups, kits, variants, configurable choices, subscriptions, attributes, specifications, images, and product content      | Product data must support buying decisions, not only recreate item records. Complex product relationships should remain understandable and purchasable.                 |
| **Buyer and account structure**       | Customers, buyer groups, customer types, B2B accounts, portal access, tax status, payment expectations, and account-level rules             | Customer data may control what buyers can see, how they are priced, and how they order. Losing this meaning can break B2B workflows even when customer records migrate. |
| **Storefront and microstore context** | Multiple storefronts, branded sites, customer-specific microstores, restricted catalogs, content areas, navigation, URLs, and theme context | Storefront assignment can affect visibility, SEO continuity, buyer access, and brand-specific presentation.                                                             |
| **Rule and pricing logic**            | Customer-specific pricing, quantity pricing, discounts, rewards, budgets, tax treatment, payment logic, and rule conditions                 | Rules are business logic. They should be reviewed as decision structures rather than treated as ordinary fields.                                                        |
| **Order and operational history**     | Orders, invoices, payment context, shipment details, fulfillment notes, vendor involvement, status history, and reorder context             | Historical records must remain useful for service, accounting, fulfillment review, customer support, and repeat purchasing.                                             |
| **Integration and custom context**    | ERP, accounting, CRM, shipping, tax, marketplace, API/headless workflows, custom fields, external identifiers, and third-party data         | Some meaning may live outside the Source Platform. That context must be identified before deciding what can migrate through standard service capability.                |

These layers are connected. A buyer group can affect catalog visibility. A microstore can affect which products and content appear. A pricing rule can depend on customer type, product group, quantity, or account status. An order can depend on payment, invoice, vendor, fulfillment, or integration data. Treating each entity as isolated can produce a migration that looks complete but does not support the merchant’s operating model.

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

Product data in AmeriCommerce can represent more than sellable items. It can support product groups, kits, configurable products, subscription products, technical specifications, buyer-specific availability, rich content, and recurring or repeat-purchase behavior. A product migration should therefore preserve the structure that helps buyers choose the right item.

#### Products may need relationship context <a href="#products-may-need-relationship-context" id="products-may-need-relationship-context"></a>

A source product may translate differently depending on how it is used. A kit may need to remain understandable as a grouped purchase. A subscription product may require recurring-purchase context. A technical product may depend on specifications, compatibility notes, documents, or content that explains how the item should be selected. A replacement part may depend on category placement, related products, or searchable attributes.

The migration implication is that product completeness cannot be measured only by name, SKU, price, image, and description. Strong product translation should preserve the relationships that affect purchase behavior. If those relationships are inconsistent in the Source Platform, the merchant should decide whether to preserve, simplify, or rebuild them before expecting AmeriCommerce to make the catalog usable.

#### Product complexity should be separated from product clutter <a href="#product-complexity-should-be-separated-from-product-clutter" id="product-complexity-should-be-separated-from-product-clutter"></a>

AmeriCommerce can support complex product models, but complexity is valuable only when it is organized. A catalog with deliberate kits, subscriptions, product groups, or technical attributes is different from a catalog that accumulated duplicate SKUs, inconsistent options, obsolete categories, or internal notes inside customer-facing fields.

During migration planning, the merchant should separate commercially meaningful product structure from historical clutter. Meaningful structure should be preserved or mapped carefully. Obsolete or inconsistent source behavior should be reviewed before it becomes part of the Target Platform.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

Customer data in AmeriCommerce may carry buyer relationship meaning. For B2B, wholesale, distributor, dealer, member, corporate, or hybrid B2B/B2C businesses, a customer is not always just a login record. The customer may belong to a group, receive negotiated pricing, access restricted products, use tax-exempt purchasing, rely on account-level payment terms, or purchase through a portal or microstore.

#### Buyer identity affects what the customer can do <a href="#buyer-identity-affects-what-the-customer-can-do" id="buyer-identity-affects-what-the-customer-can-do"></a>

A migrated customer may need to prove more than successful login. The account may need to show the correct catalog, pricing, tax treatment, payment expectations, order history, invoice history, reorder behavior, and portal access. If buyer groups or account types are lost, the Target Platform can appear populated while still failing the workflows that made the source store valuable.

This matters most when customer-specific behavior was partially configured, partially manual, or stored outside standard customer fields. Staff memory, spreadsheets, ERP records, or account-manager notes may contain rules that are not obvious in a basic export. Those cases should be documented before migration so the intended AmeriCommerce account model is clear.

#### Customer segmentation should be intentional <a href="#customer-segmentation-should-be-intentional" id="customer-segmentation-should-be-intentional"></a>

Not every customer distinction should be migrated as a long-term rule. Some historical exceptions may be obsolete. Some old customer groups may reflect temporary promotions or outdated pricing policies. Some B2B accounts may need new segmentation after migration because the future business model differs from the source structure.

AmeriCommerce migration planning should ask which customer distinctions should continue, change, merge, or retire. That decision keeps the Target Platform from inheriting unnecessary source complexity.

### Order and History Meaning <a href="#order-and-history-meaning" id="order-and-history-meaning"></a>

Orders, invoices, and historical transactions can carry operational meaning. AmeriCommerce merchants may need order history for customer service, reorder support, accounting review, fulfillment follow-up, invoice lookup, payment review, vendor context, or reporting continuity. A migrated order should therefore remain useful, not merely visible.

#### Order records should support business review <a href="#order-records-should-support-business-review" id="order-records-should-support-business-review"></a>

Order translation should preserve the information needed to understand what was purchased, who purchased it, under which buyer or storefront context, how it was priced, how it was paid, and what fulfillment or invoice information matters after launch. If source orders rely on custom statuses, external payment references, vendor assignments, shipping notes, or accounting identifiers, those details should be reviewed early.

A common weak outcome is an order that imports as a historical transaction but no longer explains the commercial situation behind it. For AmeriCommerce, stronger order migration keeps the record useful for support and operations even when not every source-side workflow becomes native target behavior.

#### Historical data may have different launch value <a href="#historical-data-may-have-different-launch-value" id="historical-data-may-have-different-launch-value"></a>

Not all historical records need the same treatment. Recent orders may be needed for active support and fulfillment. Older orders may matter mainly for reference. Subscription-related or B2B order history may need extra attention because customers may use it to reorder, confirm account activity, or review invoice context.

The migration plan should define which order history is launch-critical and which history is reference-only. That distinction helps the team interpret Demo Migration results more accurately.

### Storefront, Discovery, and Route Meaning <a href="#storefront-discovery-and-route-meaning" id="storefront-discovery-and-route-meaning"></a>

AmeriCommerce can support multiple storefront and microstore contexts. That means storefront assignment, catalog visibility, customer access, navigation, page content, and URL behavior may be part of the data model. Migration quality depends on whether those contexts remain understandable after the move.

#### Storefront context can change product and customer meaning <a href="#storefront-context-can-change-product-and-customer-meaning" id="storefront-context-can-change-product-and-customer-meaning"></a>

The same product may not belong to every storefront. The same customer may not see every catalog. The same content page may matter to one brand, region, dealer group, or portal but not another. When a source store has multiple storefronts, microsites, customer portals, or branded experiences, the migration plan should not treat catalog and content data as globally identical.

AmeriCommerce is strongest when storefront boundaries are deliberate. The merchant should identify which storefronts matter, which customers and products belong to each context, which content and routes are business-critical, and which old contexts can be retired.

#### SEO and content meaning should be reviewed with route ownership <a href="#seo-and-content-meaning-should-be-reviewed-with-route-ownership" id="seo-and-content-meaning-should-be-reviewed-with-route-ownership"></a>

Product, category, CMS, blog, and landing-page routes may affect search continuity, customer bookmarks, dealer access, or sales workflows. For a simple store, route review may focus on common product and category URLs. For an AmeriCommerce migration with multiple storefronts or portals, route meaning can be more specific because the same business may have different audience paths.

The migrated result should prove that high-value routes, navigation paths, and customer-facing content still support discovery. If source URLs, internal links, or content pages depend on custom logic or external systems, that should be reviewed before launch.

### Rules, Pricing, Rewards, and Budgets as Business Logic <a href="#rules-pricing-rewards-and-budgets-as-business-logic" id="rules-pricing-rewards-and-budgets-as-business-logic"></a>

Pricing and rule data should be treated as business logic, not as passive data. AmeriCommerce may support customer-specific pricing, discounts, quantity behavior, rewards, recurring budgets, payment expectations, tax treatment, and other rule-driven outcomes. These rules can be central to buyer trust and revenue.

#### Rules need conditions, priority, and test examples <a href="#rules-need-conditions-priority-and-test-examples" id="rules-need-conditions-priority-and-test-examples"></a>

A pricing rule is incomplete if the team knows only that “special pricing exists.” The useful migration question is who receives it, which products it affects, whether quantity matters, whether it overlaps with discounts or rewards, and whether it should continue after launch.

Rules should be tested with representative examples. A wholesale buyer, a dealer account, a loyalty customer, a budget-controlled buyer, and a retail customer may all need different validation samples. The goal is not to move every old exception blindly; it is to preserve the commercial rules that should shape the future buying experience.

#### Some rules may require Add-ons or Custom Service <a href="#some-rules-may-require-add-ons-or-custom-service" id="some-rules-may-require-add-ons-or-custom-service"></a>

Standard Add-ons can help when filtering, mapping, or data configuration matches available settings and supported behavior. If the expected result requires Tailored Add-ons, Custom Add-ons, custom fields, Custom Platform handling, outside-system identifiers, or custom migration logic adjustment, the requirement should be reviewed through Custom Service.

This distinction matters because a rule-heavy AmeriCommerce migration is not automatically difficult, but undocumented or non-standard rule behavior can quickly move beyond ordinary data translation.

### Integrations, Custom Fields, and External Meaning <a href="#integrations-custom-fields-and-external-meaning" id="integrations-custom-fields-and-external-meaning"></a>

AmeriCommerce merchants may use ERP, accounting, CRM, fulfillment, shipping, tax, marketplace, API/headless, or reporting systems that influence commerce data. Some of these systems may own the real business meaning behind product availability, customer pricing, inventory visibility, order status, invoice handling, vendor assignment, or payment review.

#### External systems can own the meaning behind visible records <a href="#external-systems-can-own-the-meaning-behind-visible-records" id="external-systems-can-own-the-meaning-behind-visible-records"></a>

A source storefront may display data that is actually controlled somewhere else. For example, inventory may be updated by an ERP, tax status may come from accounting, shipping rules may depend on a carrier or freight workflow, and customer pricing may be maintained outside the store. If those ownership relationships are unclear, migration can preserve records while breaking business operations.

Before migration, the merchant should identify which system owns each important outcome. The target-store data model should then be planned around native AmeriCommerce data, post-migration configuration, integration reconnection, and any Custom Service requirements.

#### Custom fields need business interpretation <a href="#custom-fields-need-business-interpretation" id="custom-fields-need-business-interpretation"></a>

Custom fields are not automatically important, and they are not automatically safe to ignore. Some custom fields contain internal notes, obsolete references, or temporary source-side workarounds. Others contain buyer identifiers, ERP keys, vendor references, product compatibility data, subscription context, or fulfillment instructions.

The right question is what the field does for the business. If a custom field affects pricing, visibility, buyer access, fulfillment, reporting, or integration matching, it should be reviewed as business meaning. If it is obsolete, it should not be carried forward simply because it exists.

### Custom Platform Source Interpretation <a href="#custom-platform-source-interpretation" id="custom-platform-source-interpretation"></a>

When the Source Platform is a Custom Platform or a heavily modified store, AmeriCommerce data-model planning starts with source interpretation. The migration team may need to understand custom database structure, outside-system identifiers, custom product relationships, app-owned data, third-party records, custom customer segmentation, and non-standard order logic before deciding how the data can translate.

Custom Platform cases should be reviewed through Custom Service because the work involves interpretation, transformation, or custom migration logic adjustment. The goal is not to force custom source behavior into ordinary AmeriCommerce fields. The goal is to determine which business meanings should become target data, target configuration, connected-system responsibility, or custom handling.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

A strong AmeriCommerce migration should prove that important business meanings still work in the Target Platform. The table below summarizes the main proof areas for data-model review.

| Proof area                            | What the migrated result should demonstrate                                                                                                                                   |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Product and catalog meaning**       | Products, groups, kits, subscriptions, attributes, content, and visibility rules still help buyers choose and purchase correctly.                                             |
| **Buyer and account meaning**         | Customer groups, account relationships, portal access, pricing context, tax treatment, and payment expectations remain clear.                                                 |
| **Storefront and microstore meaning** | Products, customers, content, navigation, and routes appear in the right storefront or microstore context.                                                                    |
| **Rule and pricing meaning**          | Pricing, discounts, rewards, budgets, quantity behavior, and account-specific rules produce expected examples.                                                                |
| **Order and history meaning**         | Orders, invoices, payment context, fulfillment notes, vendor context, and reorder information remain useful for support and operations.                                       |
| **Integration and custom meaning**    | External identifiers, custom fields, API/headless dependencies, and connected-system responsibilities are either preserved, reconnected, or marked for Custom Service review. |

The migrated data does not have to reproduce every source-side habit. It has to support the future operating model clearly. When the merchant can explain what each major data layer should provide, Demo Migration becomes more useful, and the full migration approach becomes easier to confirm.

### Conclusion <a href="#conclusion" id="conclusion"></a>

AmeriCommerce data-model differences matter because the platform often serves businesses with structured buyer relationships, multi-store or microstore contexts, complex product models, rule-driven pricing, operational workflows, and integration dependencies. In that environment, migration quality depends on whether the meaning behind the data survives translation.

The strongest AmeriCommerce migrations are planned around business meaning: who can buy, what they can see, how products are organized, how prices are determined, which storefront context applies, how orders are reviewed, and which systems own operational truth. If those meanings are clear before migration, AmeriCommerce can become a structured Target Platform instead of a place where source complexity is simply copied forward.

Before starting a full AmeriCommerce migration, use Demo Migration and Live Chat to review representative products, buyers, storefronts, pricing, orders, custom fields, and integration examples. A small but meaningful sample is more useful than a broad sample that does not prove the data model behind the business.

### FAQs <a href="#faqs" id="faqs"></a>

**Does AmeriCommerce require every source data structure to transfer exactly?**

No. The goal is not exact source reproduction. The goal is to preserve the business meaning that should continue in AmeriCommerce. Some source structures may be simplified, reconfigured, reconnected through integrations, or reviewed through Custom Service.

**Why is customer data more complex in an AmeriCommerce migration?**

Customer records may carry buyer-group, portal, pricing, tax, payment, account, and B2B relationship meaning. If those meanings are lost, customer records can migrate successfully while buyer workflows fail.

**Should pricing rules be treated as data or configuration?**

They should be treated as business logic. Some pricing details may migrate as data, some may need configuration, and some may require Add-ons or Custom Service depending on how the rule works and what outcome the merchant expects.

**What product examples should be reviewed during Demo Migration?**

Review products that expose real catalog meaning: kits, subscriptions, configurable products, technical products, buyer-restricted items, replacement parts, content-rich products, and products tied to special pricing or storefront visibility.

**When does a Custom Platform source require Custom Service?**

Custom Platform source cases require Custom Service when source structure, custom fields, outside-system identifiers, third-party data, or non-standard business logic must be interpreted or transformed before it can fit AmeriCommerce.
