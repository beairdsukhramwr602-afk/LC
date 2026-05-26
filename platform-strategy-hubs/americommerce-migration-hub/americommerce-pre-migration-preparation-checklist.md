# AmeriCommerce Pre-Migration Preparation Checklist

AmeriCommerce migrations need preparation that goes beyond exporting ordinary product, customer, and order records. The platform is often chosen because the future store must preserve B2B buyer relationships, customer-specific rules, multiple storefront or microstore contexts, flexible product structures, subscriptions, vendor or fulfillment workflows, and connected operational systems. Those layers can make AmeriCommerce a strong Target Platform, but they also make unclear source data more expensive to interpret after migration has already started.

Preparation should answer one practical question: **what business meaning must still be visible and usable after the data reaches AmeriCommerce?** If the merchant can explain who buys, what each buyer can see, how pricing works, which storefront context matters, how products are organized, and which systems affect fulfillment or order handling, the migration process has a clearer target. If those answers are scattered across staff memory, spreadsheets, integrations, custom fields, or old source-side workarounds, preparation should resolve them before the migration approach is treated as straightforward.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation is not only a cleanup exercise. For AmeriCommerce, it is the point where the merchant separates ordinary transferable records from business logic that must be configured, mapped, reviewed, or handled through Custom Service.

A product can be more than a SKU. It may belong to a kit, subscription plan, technical group, replacement relationship, restricted catalog, or buyer-specific availability rule. A customer can be more than a contact. It may represent a wholesale buyer, dealer, member, corporate account, tax-exempt organization, portal user, or account with special payment expectations. An order can be more than a transaction. It may carry invoice, approval, fulfillment, vendor, payment, shipping, or integration context.

The preparation goal is to make those meanings visible before migration, so Demo Migration can be judged against real operating scenarios instead of only record counts.

| Preparation area                    | What should be clarified                                                                                                     | Why it matters for AmeriCommerce                                                                                   |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Buyer relationships                 | Customer groups, buyer types, portal access, account roles, tax treatment, payment expectations, and repeat-order behavior   | AmeriCommerce migration readiness depends on preserving structured buyer relationships, not only customer records. |
| Storefront or microstore boundaries | Brands, regions, portals, customer-specific buying areas, content differences, catalog visibility, and route ownership       | Multi-store or microstore value depends on clear boundaries before data is assigned to the future structure.       |
| Product structure                   | Groups, kits, configurable items, subscriptions, variants, replacement relationships, specifications, and supporting content | Product complexity should become usable buying structure, not migrated clutter.                                    |
| Pricing and rules                   | Customer-specific pricing, quantity pricing, discounts, rewards, budgets, tax rules, and rule priority                       | Rule-driven selling must be tested as business logic after migration, not assumed from field transfer alone.       |
| Operational context                 | Fulfillment, vendors, shipping, payment review, invoices, accounting, ERP, API, marketplace, or headless dependencies        | Some outcomes may be owned outside the source store and should be documented before service scope is chosen.       |

### Preparation Priorities <a href="#numbered-preparation-priorities" id="numbered-preparation-priorities"></a>

#### 1. Define the buyer model before reviewing customer data <a href="#id-1-define-the-buyer-model-before-reviewing-customer-data" id="id-1-define-the-buyer-model-before-reviewing-customer-data"></a>

AmeriCommerce preparation is more important when buyer relationships matter. Before migration, the merchant should identify the buyer types that affect the future store experience: wholesale customers, dealers, distributors, members, retail shoppers, contract buyers, tax-exempt organizations, corporate accounts, portal users, or repeat B2B purchasers.

For each important buyer type, preparation should capture what makes the buyer different. That may include catalog visibility, customer-specific pricing, quantity rules, tax treatment, payment options, approval expectations, account ownership, order history visibility, or reorder behavior. The point is not to document every customer manually. The point is to identify the buyer patterns that must survive migration.

A strong preparation set should include representative accounts for each buyer type. The Demo Migration sample should not include only ordinary customers. It should include buyers that reveal whether AmeriCommerce can support the intended commercial relationships after migration.

#### 2. Map storefront, microstore, and portal boundaries <a href="#id-2-map-storefront-microstore-and-portal-boundaries" id="id-2-map-storefront-microstore-and-portal-boundaries"></a>

Multi-store and microstore planning should happen before data movement, not after. If the merchant operates branded storefronts, customer-specific microstores, regional catalogs, dealer portals, fundraiser stores, employee portals, or restricted B2B buying areas, each context should be documented as a business boundary.

Preparation should answer which storefronts must exist after migration, which customers belong to each context, which products should be visible, which content and navigation should differ, and which URLs or high-value routes need continuity planning. If several storefronts share inventory, pricing, orders, or administration, those shared responsibilities should also be identified.

This is especially important when the source store has grown through duplication. Multiple storefronts are useful only when they reflect intentional selling contexts. If old storefronts, categories, pages, or portal areas no longer serve a launch purpose, the merchant should decide whether they should be migrated, merged, redirected, or excluded before the migration scope is finalized.

#### 3. Classify product complexity into usable commercial structure <a href="#id-3-classify-product-complexity-into-usable-commercial-structure" id="id-3-classify-product-complexity-into-usable-commercial-structure"></a>

AmeriCommerce can support complex buying experiences, but source product complexity must be understood before it can be migrated well. The merchant should identify product groups, kits, configurable products, subscription products, variant structures, replacement parts, compatibility information, technical specifications, downloadable files, product documents, and content that affects buying decisions.

The practical task is to separate meaningful product structure from accumulated source clutter. A large catalog is not automatically a complex catalog. A complex catalog is one where product relationships affect how buyers search, compare, configure, reorder, subscribe, or purchase.

Preparation should include product examples that reveal important behavior. Choose a kit, a subscription product, a configurable item, a buyer-restricted product, a technical product with specifications, a product with rich content, and a product whose category or navigation placement affects sales. Those examples help determine whether standard migration capability is enough or whether mapping, configuration, or Custom Service review is needed.

#### 4. Document pricing, rules, rewards, budgets, and exceptions <a href="#id-4-document-pricing-rules-rewards-budgets-and-exceptions" id="id-4-document-pricing-rules-rewards-budgets-and-exceptions"></a>

AmeriCommerce preparation often depends on rule-driven commerce. Before migration, merchants should document customer-specific pricing, quantity breaks, discount rules, rewards, budgets, tax handling, payment expectations, contract pricing, and account exceptions that should remain active after launch.

Rules should be reviewed for current business relevance. Not every historical discount, workaround, or one-off exception should move to the Target Platform. The merchant should separate rules that still support revenue from old rules that create confusion. The best preparation identifies which rules must continue, which should be simplified, which should expire, and which require custom handling because they do not match standard migration capability.

The most useful rule documentation includes the affected customer group, affected product or category, expected price or behavior, rule priority, expiration status, and one or two orders that prove how the rule worked in the source store.

#### 5. Identify order, invoice, fulfillment, and vendor context <a href="#id-5-identify-order-invoice-fulfillment-and-vendor-context" id="id-5-identify-order-invoice-fulfillment-and-vendor-context"></a>

Order history preparation should focus on usefulness, not volume alone. AmeriCommerce migrations should preserve the order information needed for customer service, account review, reorder support, fulfillment reference, invoices, payments, tax review, and reporting where applicable.

If fulfillment, vendor, payment, shipping, or invoice details are important, the merchant should document where those details live and who owns them. Some information may be native to the source store. Some may come from an ERP, accounting platform, fulfillment system, shipping provider, marketplace, tax system, or custom integration. Migration planning should not assume that every operational outcome is stored in the source platform in a transferable way.

Representative order samples should include ordinary completed orders and higher-risk orders: B2B orders, tax-exempt orders, discounted orders, subscription-related orders, split-shipment cases, vendor-involved orders, orders with custom fields, orders affected by integrations, and orders that support customer service after launch.

#### 6. Confirm integration and system-of-record ownership <a href="#id-6-confirm-integration-and-system-of-record-ownership" id="id-6-confirm-integration-and-system-of-record-ownership"></a>

AmeriCommerce can be part of a wider operational stack. Before migration, the merchant should identify which system owns product truth, inventory truth, customer truth, pricing truth, tax truth, fulfillment truth, payment status, invoices, reporting, and any API or headless presentation layer.

This preparation step prevents a common planning error: treating the source store as the owner of every business outcome just because the storefront displays the result. If an ERP controls inventory, an accounting system owns invoice status, a shipping system controls fulfillment updates, or a custom API affects storefront presentation, those dependencies should be documented before the migration approach is chosen.

Integration ownership also affects launch planning. Some connections may need to be reconfigured after migration. Some historical data may be migrated for reference but not used operationally. Some integration-dependent behavior may require Custom Service or separate implementation work outside standard migration capability.

#### 7. Prepare custom fields, external identifiers, and Custom Platform source evidence <a href="#id-7-prepare-custom-fields-external-identifiers-and-custom-platform-source-evidence" id="id-7-prepare-custom-fields-external-identifiers-and-custom-platform-source-evidence"></a>

Custom fields, external identifiers, app-owned data, third-party records, and heavily modified Source Platform structures should be reviewed before migration. These items often carry business meaning that ordinary exports do not explain.

Preparation should identify what each custom field means, where it appears, who uses it, whether it affects buyer access or order handling, and whether it should become native AmeriCommerce configuration, migrated reference data, mapped field content, or custom migration logic adjustment. If the Source Platform is a Custom Platform or heavily modified system, the merchant should prepare schema notes, export samples, database explanations, API references, field definitions, and examples of the expected target outcome.

Custom Platform source cases should be reviewed through Custom Service. They should not be treated as ordinary platform-to-platform migrations because the source interpretation itself may be the first major task.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

The following sequence keeps preparation focused. It starts with business meaning, then moves into samples, rules, systems, and escalation decisions.

<table><thead><tr><th width="85.109375">Step</th><th>Preparation action</th><th>Output that should exist before migration</th></tr></thead><tbody><tr><td>1</td><td>Define the future selling model</td><td>Short description of buyer groups, storefront contexts, product complexity, pricing rules, and operational dependencies that must matter after launch.</td></tr><tr><td>2</td><td>Select representative buyer and product examples</td><td>Sample accounts, products, rules, storefronts, and orders that reveal the most important AmeriCommerce behaviors.</td></tr><tr><td>3</td><td>Clean obvious source noise</td><td>Deprecated categories, inactive rules, obsolete pages, duplicate product structures, unused customer groups, and retired storefront contexts are marked for exclusion, consolidation, or review.</td></tr><tr><td>4</td><td>Document rule and integration ownership</td><td>Pricing, discount, budget, tax, payment, fulfillment, invoice, API, and reporting responsibilities are assigned to the right system or reviewed as unknown.</td></tr><tr><td>5</td><td>Identify custom or non-standard data</td><td>Custom fields, external IDs, third-party data, custom source structures, and app-owned logic are listed with business meaning and expected target handling.</td></tr><tr><td>6</td><td>Choose Demo Migration samples</td><td>The sample set includes ordinary records plus high-value cases that prove whether AmeriCommerce supports the intended operating model.</td></tr><tr><td>7</td><td>Escalate unresolved complexity</td><td>Unclear buyer logic, custom source behavior, integration dependencies, or unsupported transformation needs are reviewed before Full Migration.</td></tr></tbody></table>

This sequence does not require the merchant to perfect every record before migration. It requires enough clarity to prevent the migration from becoming a guessing exercise.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should be used as early evidence. For AmeriCommerce, a useful Demo Migration sample should be intentionally selected rather than filled with only easy records.

#### Buyer and account samples <a href="#buyer-and-account-samples" id="buyer-and-account-samples"></a>

Include buyer accounts that represent the future selling model: retail customers, wholesale buyers, dealers, tax-exempt accounts, contract customers, portal users, members, or corporate buyers. Each sample should help answer whether the customer record carries the right commercial meaning after migration.

#### Storefront, portal, and route samples <a href="#storefront-portal-and-route-samples" id="storefront-portal-and-route-samples"></a>

Include examples from each important storefront, microstore, portal, or restricted buying context. The sample should show whether products, categories, content, navigation, and high-value routes can be interpreted correctly for the future structure.

#### Product and catalog samples <a href="#product-and-catalog-samples" id="product-and-catalog-samples"></a>

Include ordinary products and high-risk products: kits, configurable products, subscription products, product groups, products with technical specifications, restricted products, products with rich content, and products that depend on category placement or buying guidance.

#### Rule and pricing samples <a href="#rule-and-pricing-samples" id="rule-and-pricing-samples"></a>

Include customers and orders affected by price levels, quantity pricing, discounts, rewards, budgets, tax treatment, payment expectations, or contract-style pricing. These samples help determine whether the rule layer is documented clearly enough for the selected migration approach.

#### Order and fulfillment samples <a href="#order-and-fulfillment-samples" id="order-and-fulfillment-samples"></a>

Include orders that prove customer-service and operations value: completed orders, B2B orders, subscription-related orders, tax-exempt orders, discounted orders, invoice-sensitive orders, vendor-involved orders, split-shipment examples, and orders influenced by external systems.

| Demo Migration sample type | Good sample choice                                                       | What the sample should reveal                                                                              |
| -------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| Buyer group                | Wholesale buyer with special pricing and order history                   | Whether customer meaning, pricing expectation, and historical context are preserved well enough to review. |
| Microstore or portal       | Customer-specific buying area with restricted products                   | Whether storefront context and catalog visibility are understandable after migration.                      |
| Complex product            | Kit, subscription product, or configurable product                       | Whether product structure remains usable instead of becoming a flat or confusing record.                   |
| Pricing rule               | Quantity pricing, discount, reward, budget, or tax-exempt case           | Whether rule-related outcomes need standard configuration, Add-ons, or Custom Service review.              |
| Operational order          | Order with fulfillment, vendor, payment, invoice, or integration context | Whether order history carries enough operational meaning for launch and support review.                    |

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

Custom Platform sources and heavily modified systems need earlier preparation than ordinary platform sources. The merchant should not wait for Demo Migration to discover that source records depend on custom tables, scripts, hidden identifiers, external systems, or business rules that are not visible in standard exports.

Useful evidence includes source database notes, export samples, API field references, screenshots showing how staff use the data, examples of expected AmeriCommerce outcomes, and explanations of any third-party system that created or controls the data. This evidence helps determine whether the requirement is standard migration capability, a Standard Add-on need, a Tailored Add-on, a Custom Add-on, or broader Custom Service work.

Custom data should be judged by business use. A custom field that no one uses may not deserve migration effort. A custom field that controls buyer access, product eligibility, account review, vendor assignment, pricing, or fulfillment may be launch-critical.

### What Should Be Escalated Before Execution <a href="#what-should-be-escalated-before-execution" id="what-should-be-escalated-before-execution"></a>

Some findings should be reviewed before execution because they can change the migration approach, service scope, or validation burden.

| Escalation signal                                                               | Why it should be reviewed early                                                                                                |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Buyer groups or portal rules are undocumented                                   | The migration may depend on buyer-specific behavior that cannot be safely inferred.                                            |
| Multi-store or microstore boundaries are unclear                                | Data may be assigned to the wrong storefront context, creating navigation, access, or reporting problems.                      |
| Product structures are inconsistent or duplicated                               | Complex catalog data may migrate without becoming usable for buyers.                                                           |
| Pricing, discounts, rewards, or budgets conflict                                | Rule outcomes may need mapping, simplification, or custom migration logic adjustment.                                          |
| Fulfillment, vendor, invoice, or payment context lives outside the source store | Standard record migration may not preserve the operational outcome the business expects.                                       |
| Custom fields or external identifiers affect business workflows                 | The migration may require Custom Service, especially when the field meaning is not native to AmeriCommerce.                    |
| The Source Platform is custom or heavily modified                               | Source interpretation, transformation rules, and validation samples should be reviewed before the migration path is finalized. |

Escalation does not mean the project is unworkable. It means the merchant has found an area where preparation should become a service-scope discussion instead of a late-stage surprise.

### Conclusion <a href="#conclusion" id="conclusion"></a>

AmeriCommerce preparation should make the future operating model visible before migration begins. Buyer groups, storefront boundaries, product structures, pricing rules, subscriptions, fulfillment context, vendor workflows, integrations, custom fields, and source-side modifications should be documented according to their business meaning, not treated as ordinary data labels.

The strongest preparation gives Demo Migration a real purpose. Instead of asking whether records moved, the merchant can test whether AmeriCommerce supports the way the business sells, prices, organizes buyers, presents products, and handles orders after launch.

Before starting an AmeriCommerce migration, prepare representative buyer, product, storefront, pricing, order, and integration samples, then use Demo Migration and Live Chat to identify which requirements match standard migration capability and which should be reviewed before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Do I need to clean every AmeriCommerce migration record before starting?**

No. Preparation should focus first on business-critical meaning: buyer groups, storefront boundaries, product structures, pricing rules, order context, integrations, custom fields, and source-side exceptions. Ordinary inactive or low-value records can often be handled later, but unclear business logic should be resolved before execution.

**What should I prepare for Demo Migration?**

Prepare samples that reveal how the future AmeriCommerce store should work: wholesale buyers, customer-specific pricing, microstore context, complex products, subscription examples, rule-driven discounts, representative orders, fulfillment-sensitive orders, and integration-dependent records.

**Should old rules and exceptions always be migrated?**

No. Preparation should identify which rules still support the business and which should be simplified, retired, or reviewed. Carrying every historical exception into the Target Platform can make the new store harder to manage.

**When should Custom Service be considered during preparation?**

Custom Service should be considered when the migration requires customization, modification, Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, custom fields, external identifiers, third-party data, or integration-dependent behavior beyond standard migration capability.

**How should we prepare if the source store is a Custom Platform?**

Prepare schema notes, export samples, field definitions, screenshots, API references, examples of expected AmeriCommerce outcomes, and explanations of any external systems that control important data. Custom Platform source cases should be reviewed through Custom Service before the migration approach is confirmed.

