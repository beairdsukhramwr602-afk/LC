# Bagisto Pre-Migration Preparation Checklist

Bagisto preparation should begin with a practical question: what should the future store be responsible for after migration, and what should remain the responsibility of custom code, extensions, connected systems, or operational teams?

Bagisto is an open-source Laravel e-commerce platform, so migration preparation is not only about exporting products, customers, and orders from the Source Platform. The target environment can be shaped by Laravel development, channels, product attributes, extension modules, marketplace or B2B requirements, headless storefronts, integrations, custom fields, and source-specific business logic. A clean migration plan should make those responsibilities visible before data starts moving.

Preparation is strongest when the merchant can explain the intended Bagisto operating model in business language first, then connect that model to data, configuration, and service requirements. Without that preparation, the migration can produce records that appear present but still require heavy post-migration interpretation before the store is usable.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation gives the Demo Migration and Full Migration a clear standard for evaluation. It should answer what must be preserved, what should be simplified, what should be rebuilt through Bagisto configuration, and what requires Custom Service review.

For Bagisto, preparation should focus on four kinds of clarity:

| Preparation area                        | Why it matters for Bagisto migration                                                                                                                                                                            |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Target operating model**              | Bagisto can support ordinary e-commerce, marketplace, B2B, multi-tenant, POS-connected, mobile, and headless commerce contexts. The migration should know which target model is actually expected after launch. |
| **Catalog and attribute structure**     | Product meaning may depend on attributes, variants, categories, specifications, downloadable content, vendor context, channel visibility, or custom source fields. These should be classified before migration. |
| **Extension and development ownership** | Some target behavior may come from Bagisto modules, third-party extensions, custom Laravel development, or external systems rather than native migrated records.                                                |
| **Validation evidence**                 | Demo Migration samples should be chosen to reveal product, customer, order, channel, and integration issues early, not merely to show that common records can move.                                             |

Preparation should not become a technical build document. It should give the migration team enough evidence to decide what can move through standard migration capability, what needs Add-on support, and what belongs in Custom Service.

### Preparation Priorities <a href="#numbered-preparation-priorities" id="numbered-preparation-priorities"></a>

#### 1. Define the intended Bagisto store model <a href="#id-1-define-the-intended-bagisto-store-model" id="id-1-define-the-intended-bagisto-store-model"></a>

Start by identifying the role Bagisto will play after migration. A simple online storefront, a multi-vendor marketplace, a B2B store, a B2B marketplace, a multi-tenant commerce environment, a POS-connected operation, and a headless commerce build create different preparation needs.

The merchant should document the future store model before export planning. If the future store will include marketplace sellers, company buyers, channel-specific catalogs, mobile commerce, POS workflows, or headless frontend behavior, those requirements should be visible before the migration approach is selected.

This preparation prevents a common issue: treating Bagisto as a generic e-commerce target while the actual project depends on developer-governed or extension-driven behavior.

#### 2. Clean and classify product structure <a href="#id-2-clean-and-classify-product-structure" id="id-2-clean-and-classify-product-structure"></a>

Bagisto migrations need clear product meaning. The merchant should review products, SKUs, categories, attributes, variants, specifications, downloadable items, product groups, related products, inventory signals, images, and source-specific product notes.

The goal is not to make every product perfect before migration. The goal is to separate commercially meaningful structure from source-side clutter. Product fields should be classified as sellable product information, search or filtering information, technical specification, internal reference, channel visibility context, extension-owned data, or custom-field material that may need special handling.

A catalog that is large but well-classified is usually easier to migrate than a smaller catalog where options, attributes, and internal notes are mixed together without clear meaning.

#### 3. Review category, channel, and storefront expectations <a href="#id-3-review-category-channel-and-storefront-expectations" id="id-3-review-category-channel-and-storefront-expectations"></a>

Bagisto preparation should clarify how customers will discover products in the Target Platform. Categories, menus, landing pages, URL paths, channel assignments, storefront language, and content structure should be reviewed before migration.

If the business expects multiple channels, regional storefronts, B2B access areas, marketplace contexts, or headless storefronts, the preparation should define which products and content belong to each context. When channel or storefront expectations are unclear, migrated records may be technically present but difficult to use in the intended customer journey.

#### 4. Document customer groups, company accounts, and buyer rules <a href="#id-4-document-customer-groups-company-accounts-and-buyer-rules" id="id-4-document-customer-groups-company-accounts-and-buyer-rules"></a>

If the migration involves B2B, wholesale, company accounts, buyer roles, negotiated pricing, RFQ behavior, requisition lists, bulk ordering, or buyer-specific catalogs, customer preparation becomes more than account cleanup.

The merchant should identify which buyer groups matter, which accounts require special handling, which users belong to company accounts, which rules affect pricing or visibility, and which order examples prove that the expected buyer context works. For projects that do not use B2B features, preparation should still confirm whether customer groups, tax status, order history, and account data should be preserved in a simple customer-account model.

#### 5. Separate orders from operational workflow history <a href="#id-5-separate-orders-from-operational-workflow-history" id="id-5-separate-orders-from-operational-workflow-history"></a>

Order data should be reviewed for more than order number, customer, product, and total. Bagisto migration planning should identify which historical order details matter for customer service, reporting, fulfillment review, payment reconciliation, returns, vendor handling, or integration continuity.

Older orders may contain source statuses, payment notes, shipping records, coupon usage, refunds, invoices, fulfillment instructions, or integration identifiers. Some of that context may be migrated as supported data, some may need mapping or configuration decisions, and some may remain external to Bagisto. The merchant should decide what the Target Platform must preserve and what can remain archived or handled outside the migration.

#### 6. Identify extensions, custom Laravel logic, and external systems <a href="#id-6-identify-extensions-custom-laravel-logic-and-external-systems" id="id-6-identify-extensions-custom-laravel-logic-and-external-systems"></a>

Bagisto’s flexibility is one of its strengths, but preparation must identify where flexibility changes migration scope. The merchant should list required Bagisto extensions, custom Laravel modules, marketplace modules, B2B modules, payment extensions, shipping extensions, tax services, ERP/accounting systems, PIM systems, CRM systems, warehouse systems, APIs, or headless frontend layers.

This list should explain what each system owns. For example, a PIM may own product enrichment, an ERP may own inventory and fulfillment, a marketplace module may own vendor assignment, and a custom Laravel module may own business-specific workflow logic. If ownership is unclear, the migration team cannot safely decide whether a field is a native target record, a mapped value, an integration dependency, or Custom Service work.

#### 7. Prepare source evidence before execution <a href="#id-7-prepare-source-evidence-before-execution" id="id-7-prepare-source-evidence-before-execution"></a>

The merchant should gather representative exports, screenshots, admin examples, source field notes, integration diagrams, sample buyer accounts, sample products, sample orders, custom-field lists, app or extension data examples, and any source documentation that explains how the current store works.

This evidence is especially important when the Source Platform is heavily modified or custom-built. Custom Platform sources, proprietary database structures, outside-system identifiers, and non-standard field meanings should be reviewed before migration execution because standard export files may not explain the business logic behind the data.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

A strong preparation process moves from business intent to migration evidence. The following sequence keeps the work manageable and prevents teams from jumping into field-level cleanup before the target operating model is clear.

| Step  | Preparation action                        | Output needed before migration                                                                                                                             |
| ----- | ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | Define the future Bagisto operating model | Clear statement of whether Bagisto will support simple e-commerce, B2B, marketplace, multi-tenant, POS-connected, mobile, or headless commerce behavior.   |
| **2** | Review catalog structure                  | Product examples, attribute groups, variant logic, category rules, image/content needs, channel visibility, and fields requiring mapping or custom review. |
| **3** | Clarify buyer and customer context        | Customer groups, company accounts, buyer roles, pricing rules, tax treatment, account permissions, and representative buyer journeys.                      |
| **4** | Review order and fulfillment history      | Sample orders with statuses, invoices, payment context, shipping data, refunds, vendor or warehouse context, and integration identifiers.                  |
| **5** | Identify extensions and connected systems | List of required modules, APIs, integrations, external systems, and ownership responsibilities.                                                            |
| **6** | Choose Demo Migration samples             | Representative products, customers, orders, categories, content, and custom-source examples that reveal real migration risk.                               |
| **7** | Escalate non-standard requirements        | Items that require Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom fields, or custom migration logic adjustment.                        |

This sequence is not a software setup checklist. It is a preparation path for making the migration result testable.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should be designed to reveal whether Bagisto can represent the merchant’s real operating model. Easy samples are not enough. The sample set should include ordinary records, high-value records, and records that expose the difficult parts of the migration.

| Sample type                            | What to include                                                                                                                                                                                         | What the sample should reveal                                                                                          |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Product samples**                    | Simple products, variant-heavy products, attribute-rich items, downloadable items, grouped or related products, products with custom fields, and products assigned to important categories or channels. | Whether product meaning, options, attributes, images, pricing, and visibility can be interpreted correctly in Bagisto. |
| **Category and navigation samples**    | Top categories, deep categories, high-traffic landing pages, redirected URLs, channel-specific content, and SEO-sensitive paths.                                                                        | Whether storefront discovery and route continuity can be planned deliberately.                                         |
| **Customer samples**                   | Ordinary customers, wholesale or B2B buyers, company accounts, tax-exempt customers, high-value accounts, and accounts with meaningful order history.                                                   | Whether customer records retain the account context needed for service, pricing, and validation.                       |
| **Order samples**                      | Recent orders, old orders, refunded or partially fulfilled orders, orders with discounts, orders with shipping/payment details, and integration-sensitive orders.                                       | Whether historical order context remains useful after migration.                                                       |
| **Extension or custom-source samples** | Records shaped by source modules, custom fields, marketplace seller data, ERP identifiers, PIM fields, or custom database logic.                                                                        | Whether the requirement fits standard migration capability, Add-on support, or Custom Service review.                  |

A good Demo Migration sample should help the merchant answer: does the migrated data look usable in Bagisto, or does the result expose preparation gaps that should be resolved before Full Migration?

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

Custom Platform sources require more preparation than ordinary platform-to-platform migration paths. The merchant should not rely on exports alone when the source structure is custom, heavily modified, or dependent on external systems.

Before execution, prepare:

* source database or export structure explanations
* custom-field definitions
* relationship notes for products, customers, orders, vendors, and content
* external identifiers used by ERP, PIM, CRM, warehouse, marketplace, tax, payment, or shipping systems
* examples of custom logic that affects pricing, visibility, fulfillment, approval, or reporting
* records that show how source data should be interpreted in Bagisto

When this context is missing, the migration may preserve values without preserving meaning. Custom Service should be reviewed when custom source behavior, custom fields, outside-system identifiers, third-party data, Tailored Add-ons, Custom Add-ons, Custom Platform handling, or custom migration logic adjustment is required.

### What Should Be Escalated Before Execution <a href="#what-should-be-escalated-before-execution" id="what-should-be-escalated-before-execution"></a>

Not every preparation issue should delay migration, but some issues should be escalated before execution because they can change the migration approach.

| Escalation signal                                    | Why it matters                                                                                                                                  |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **The future Bagisto model is still undecided**      | A simple storefront, marketplace, B2B store, multi-tenant model, and headless build do not create the same migration requirements.              |
| **Product attributes and variants are inconsistent** | Poorly classified catalog data can migrate but still fail filtering, product selection, or channel presentation.                                |
| **Buyer rules are undocumented**                     | B2B pricing, company accounts, permissions, tax treatment, and buyer-specific catalogs cannot be safely preserved if the rules are not defined. |
| **External systems own key outcomes**                | ERP, PIM, fulfillment, payment, tax, warehouse, CRM, or API systems may need reconnection or custom planning outside basic record migration.    |
| **Custom source logic controls business behavior**   | Custom fields, custom checkout logic, marketplace relationships, app-owned data, or proprietary database structure may require Custom Service.  |
| **Demo Migration samples are too generic**           | If samples do not include difficult products, buyers, orders, channels, or integration-sensitive records, the test will not reveal launch risk. |

Escalation is not a failure. It is the point where the migration plan becomes more accurate.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for a Bagisto migration means clarifying the target operating model before treating data movement as straightforward. Bagisto can support flexible Laravel-based e-commerce, marketplace, B2B, multi-tenant, POS, mobile, and headless commerce scenarios, but those scenarios require deliberate preparation around catalog meaning, customer context, channel behavior, extensions, integrations, custom fields, and source-specific logic.

The strongest preparation does not attempt to solve every technical detail before migration. It identifies what must be preserved, what should be simplified, what needs configuration, what needs Add-on support, and what must be reviewed through Custom Service before execution.

Before starting the migration, use Demo Migration and Live Chat to test representative Bagisto scenarios: complex products, important categories, buyer groups, company accounts, rule-sensitive orders, channel-specific content, integration identifiers, and custom-source records that reveal whether the migration plan is ready for Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Should every Bagisto migration require technical preparation?**

Yes, but the level of preparation depends on the project. A simple storefront may need basic catalog, customer, order, and URL review. A marketplace, B2B, multi-tenant, headless, or custom Laravel-based project needs deeper preparation around extensions, integrations, buyer rules, custom data, and source interpretation.

**What should be cleaned before migrating to Bagisto?**

The most useful cleanup areas are duplicate or obsolete products, unclear attributes, inconsistent variants, outdated categories, unused customer groups, inactive rules, irrelevant content, and source fields that no longer have business meaning. Cleanup should support migration clarity rather than remove data without review.

**Should extensions be installed before migration?**

That depends on the target design. If an extension will own important data meaning, such as marketplace vendors, B2B buyer rules, payment context, shipping behavior, or custom catalog presentation, it should be identified before migration planning. Whether it must be installed before execution depends on the migration approach and target configuration plan.

**How should Demo Migration samples be chosen for Bagisto?**

Samples should include ordinary records and difficult records. Use products with attributes or variants, important categories, B2B or wholesale buyers, company accounts, meaningful order histories, SEO-sensitive content, custom fields, and integration-sensitive records. The goal is to reveal whether the result is usable in Bagisto, not merely whether data appears.

**When should Custom Service be reviewed before a Bagisto migration?**

Custom Service should be reviewed when the project involves Custom Platform sources, custom Laravel logic, non-standard source structures, custom fields, outside-system identifiers, third-party data, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment. These requirements can affect how data is interpreted and transformed before it reaches Bagisto.
