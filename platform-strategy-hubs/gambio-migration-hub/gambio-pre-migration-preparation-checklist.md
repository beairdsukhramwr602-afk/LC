# Gambio Pre-Migration Preparation Checklist

Preparing a migration to Gambio means preparing a complete shop operating model, not only a list of records. Gambio can support catalog management, product variants, customer groups, B2B and B2C selling context, SEO, payment and shipping modules, legal-display configuration, content pages, storefront design, integrations, and either cloud or self-hosted operation. A strong preparation phase clarifies which parts should be migrated as supported data, which parts must be configured inside Gambio, and which parts require deeper review before the migration process begins.

The preparation work should make the Demo Migration easier to interpret. If product options, customer groups, tax rules, shipping methods, payment context, order statuses, SEO URLs, and design dependencies are not documented before testing, the Demo Migration may appear incomplete even when the migration process is working as expected. The goal is to enter the migration with enough evidence to judge the result accurately.

### Preparation Priority 1: Confirm the Target Gambio Operating Model <a href="#preparation-priority-1-confirm-the-target-gambio-operating-model" id="preparation-priority-1-confirm-the-target-gambio-operating-model"></a>

The first preparation step is deciding whether the future store will run on Gambio Cloud or a self-hosted Gambio environment. This choice affects implementation responsibility, technical access, hosting work, update expectations, customization flexibility, and integration planning.

#### Prepare the cloud or self-hosting decision <a href="#prepare-the-cloud-or-self-hosting-decision" id="prepare-the-cloud-or-self-hosting-decision"></a>

For Gambio Cloud, the merchant should clarify what will be managed as part of the cloud environment and what still needs merchant-side configuration after migration. Cloud operation can simplify hosting and maintenance concerns, but it does not remove the need to plan catalog structure, storefront layout, payment setup, shipping setup, legal settings, SEO continuity, and validation.

For self-hosted Gambio, the merchant should confirm the hosting environment, software requirements, update responsibilities, technical access, security process, backup expectations, and development workflow. Self-hosting may be appropriate when the business needs greater control, special interfaces, custom theme work, or more technical flexibility, but it also increases the importance of environment readiness.

| Target decision    | What to prepare                                                                                                                    | Why it matters                                                                                                          |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Gambio Cloud       | Account readiness, target configuration access, payment/shipping setup responsibilities, design expectations, and launch workflow  | The migration can be planned around a managed environment, but configuration and validation still need clear ownership. |
| Self-hosted Gambio | Hosting, PHP/MySQL or MariaDB compatibility, backups, update process, developer access, custom code policy, and integration access | The migration depends on a stable technical environment and clear responsibility for maintenance and implementation.    |
| Not decided yet    | Business requirements, customization expectations, integration needs, internal technical capacity, and support expectations        | The migration approach may be too light if the operating model is undecided.                                            |

#### Separate migration readiness from implementation readiness <a href="#separate-migration-readiness-from-implementation-readiness" id="separate-migration-readiness-from-implementation-readiness"></a>

A store can be ready to migrate data but not ready to launch. Gambio may still need payment providers configured, shipping rules reviewed, taxes set, legal display areas checked, email templates prepared, storefront layout adjusted, redirects planned, and integrations reconnected. Preparation should separate these responsibilities clearly so migration quality is judged against the correct scope.

### Preparation Priority 2: Audit the Product and Category Structure <a href="#preparation-priority-2-audit-the-product-and-category-structure" id="preparation-priority-2-audit-the-product-and-category-structure"></a>

Gambio preparation should begin with the catalog because product structure often carries the most visible migration risk. Products should be reviewed as selling structures with category placement, variant or option behavior, images, stock, downloads, pricing, filters, specials, cross-selling, reviews, and customer group relevance.

#### Document the core product records <a href="#document-the-core-product-records" id="document-the-core-product-records"></a>

Create a product inventory that identifies the main product types in the source store. This inventory should include simple products, products with variants or options, products with multiple images, downloadable products, products with stock rules, products with tier prices or customer group prices, products with discounts or specials, products with reviews, products linked to cross-selling, and products that depend on unusual fields.

The preparation should not stop at counting products. It should explain what makes each product type commercially important. A variant-heavy product, for example, may be important because shoppers select size and color. A downloadable product may be important because fulfillment is digital. A product with base-price requirements may be important because regional display expectations affect compliance and customer understanding.

#### Review categories, filters, and discovery paths <a href="#review-categories-filters-and-discovery-paths" id="review-categories-filters-and-discovery-paths"></a>

Gambio catalog preparation should document categories, subcategories, filters, manufacturer relationships, product placement, and high-value discovery paths. Category depth and filter behavior affect how shoppers find products after migration, while manufacturer or brand relationships may affect search, filtering, product credibility, and merchandising.

If the source store contains duplicate categories, outdated categories, unused filters, inconsistent product assignments, or manually built landing paths, those issues should be identified before migration. Otherwise, Gambio may inherit structure that is technically migrated but not useful.

#### Identify catalog records that deserve Demo Migration samples <a href="#identify-catalog-records-that-deserve-demo-migration-samples" id="identify-catalog-records-that-deserve-demo-migration-samples"></a>

Representative product samples should be selected before Demo Migration. The sample set should reveal product behavior, not merely product presence.

| Sample type                         | Why it should be included                     | What to check after Demo Migration                                                                         |
| ----------------------------------- | --------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Simple product                      | Establishes the baseline product structure    | Name, SKU/model, price, description, images, category placement, status, and storefront readability        |
| Variant-heavy product               | Reveals option/property/attribute translation | Shopper selections, price differences, stock behavior, option labels, and order line readability           |
| Product with multiple images        | Tests visual merchandising continuity         | Main image, gallery images, zoom behavior, missing-image issues, and image order                           |
| Downloadable product                | Tests non-physical fulfillment meaning        | Download assignment, order relationship, customer access expectation, and product classification           |
| Discounted or special product       | Tests pricing and promotion interpretation    | Normal price, special price, customer group price, tier price, discount visibility, and timing assumptions |
| Product in multiple discovery paths | Tests catalog organization                    | Category placement, filters, manufacturer assignment, cross-selling, and storefront navigation             |

### Preparation Priority 3: Clarify Variants, Properties, Attributes, and Product Options <a href="#preparation-priority-3-clarify-variants-properties-attributes-and-product-options" id="preparation-priority-3-clarify-variants-properties-attributes-and-product-options"></a>

Gambio catalog structure may use product choices, properties, attributes, combinations, filters, and display fields in ways that differ from the Source Platform. Preparation should identify how the source store represents shopper choices and how those choices should appear inside Gambio.

#### Separate shopper choice from product information <a href="#separate-shopper-choice-from-product-information" id="separate-shopper-choice-from-product-information"></a>

Not every source field has the same purpose. Some fields help shoppers choose a purchasable version of the product. Others describe the product for comparison or filtering. Some affect price or stock. Others are purely informational. If these roles are not separated before migration, the target result may mix selling choices with descriptive attributes.

A strong preparation file should identify:

* which product details are shopper-selectable options;
* which details are attributes or specifications;
* which options affect price;
* which options affect stock;
* which product choices appear in historical orders;
* which fields are used for filtering or comparison;
* which fields come from apps, modules, custom code, or external systems.

#### Prepare the variant evidence <a href="#prepare-the-variant-evidence" id="prepare-the-variant-evidence"></a>

For each important variant or option pattern, collect example products and example orders. Product evidence shows how shoppers choose the item. Order evidence shows how selected options appear after purchase. Both are needed because a product can look acceptable on the storefront while historical order lines lose the detail required for support.

If the source structure is inconsistent, clean-up decisions should happen before migration or be explicitly marked for review. Advanced Data Mapping, Advanced Data Configure, or Custom Service may be needed when product choices, fields, or relationships do not fit standard service capability.

### Preparation Priority 4: Document Customers, Customer Groups, and B2B/B2C Logic <a href="#preparation-priority-4-document-customers-customer-groups-and-b2b-b2c-logic" id="preparation-priority-4-document-customers-customer-groups-and-b2b-b2c-logic"></a>

Gambio preparation should include customer structure, not only customer records. Customer groups, group-specific pricing, B2B and B2C segmentation, guest checkout history, tax context, visibility rules, and account relationships may all affect whether the migrated store remains commercially useful.

#### Identify customer groups and pricing rules <a href="#identify-customer-groups-and-pricing-rules" id="identify-customer-groups-and-pricing-rules"></a>

Customer groups should be documented with their business meaning. A group may represent retail customers, wholesale buyers, resellers, tax-exempt buyers, loyalty segments, regional buyer types, or legacy groups created for one-off pricing rules. The migration plan should identify which groups are still active, which price rules or discounts depend on them, and which customers should be used as validation samples.

#### Prepare customer and order pairings <a href="#prepare-customer-and-order-pairings" id="prepare-customer-and-order-pairings"></a>

Customer samples should be paired with order samples. This helps validate whether migrated customer records connect to the correct historical purchases and whether customer group context remains meaningful.

Useful customer samples include:

* a normal retail customer;
* a wholesale or B2B customer;
* a customer with multiple historical orders;
* a customer with refunded or cancelled order history;
* a guest checkout record if guest purchases are important;
* a customer affected by customer group pricing or tax rules;
* a customer created by an integration, marketplace, or external system.

### Preparation Priority 5: Prepare Order History and Operational Records <a href="#preparation-priority-5-prepare-order-history-and-operational-records" id="preparation-priority-5-prepare-order-history-and-operational-records"></a>

Order history should be prepared as operational evidence. Gambio migration planning should account for order numbers, products, selected options, customer relationships, totals, discounts, tax, shipping, payment context, order statuses, invoices, delivery notes, cancellation or return history, and tracking or package service context where relevant.

#### Choose order samples that reveal real operating behavior <a href="#choose-order-samples-that-reveal-real-operating-behavior" id="choose-order-samples-that-reveal-real-operating-behavior"></a>

A weak order sample set includes only recent successful orders with simple products. A stronger set includes edge cases that reveal whether the migrated order history remains useful for customer service, reporting, fulfillment reference, and internal review.

| Order sample                           | Why it matters                   | Validation focus                                                                             |
| -------------------------------------- | -------------------------------- | -------------------------------------------------------------------------------------------- |
| Recent completed order                 | Confirms current order structure | Customer link, line items, totals, payment method, shipping method, and status               |
| Older order                            | Tests legacy history             | Date handling, customer connection, product references, and status readability               |
| Variant product order                  | Tests option selection history   | Selected options, SKU/model logic, price, and order line clarity                             |
| Discounted order                       | Tests promotion context          | Coupon, discount, special price, totals, tax, and customer group effect                      |
| Refunded, cancelled, or returned order | Tests exception history          | Status meaning, totals, comments, and support usefulness                                     |
| B2B or customer-group order            | Tests segmented selling context  | Group relationship, pricing behavior, tax context, invoice expectations, and account history |

#### Document order statuses and workflow assumptions <a href="#document-order-statuses-and-workflow-assumptions" id="document-order-statuses-and-workflow-assumptions"></a>

Order statuses should be documented before migration, especially if the source platform used custom statuses, automated status changes, fulfillment integrations, marketplace statuses, accounting systems, or payment-provider status updates. Gambio may support order management and statuses, but migration planning should not assume that every historical workflow becomes active operational logic after data movement.

### Preparation Priority 6: Prepare Tax, Shipping, Payment, Currency, and Legal-Display Settings <a href="#preparation-priority-6-prepare-tax-shipping-payment-currency-and-legal-display-settings" id="preparation-priority-6-prepare-tax-shipping-payment-currency-and-legal-display-settings"></a>

Tax, shipping, payment, currency, language, legal-display settings, invoices, delivery notes, and order total behavior are configuration-sensitive. Preparation should identify which information is historical data, which information must be configured in Gambio, and which information requires deeper service review.

#### Separate historical order context from future selling configuration <a href="#separate-historical-order-context-from-future-selling-configuration" id="separate-historical-order-context-from-future-selling-configuration"></a>

Historical orders should remain readable with tax, shipping, payment, discount, and total context. Future selling behavior, however, depends on target configuration. A migration may preserve records while the merchant still needs to configure payment providers, shipping modules, tax rules, countries, currencies, language settings, invoice behavior, legal content, and email templates.

#### Prepare configuration evidence <a href="#prepare-configuration-evidence" id="prepare-configuration-evidence"></a>

Before migration, gather evidence for:

* active payment methods and gateway references;
* active shipping methods and tracking/package-service requirements;
* tax zones, tax rates, country settings, and regional selling expectations;
* currencies and currency display expectations;
* languages used in storefront and administration-facing content;
* order total components such as shipping, discount, tax, voucher, or surcharge values;
* invoice and delivery note expectations;
* legal pages, legal text, display rules, and customer communication requirements.

If the source uses custom tax logic, ERP-controlled shipping, marketplace payment records, external invoice systems, or unsupported gateway metadata, the plan should include Custom Service review.

### Preparation Priority 7: Collect SEO, URL, Content, and Storefront Evidence <a href="#preparation-priority-7-collect-seo-url-content-and-storefront-evidence" id="preparation-priority-7-collect-seo-url-content-and-storefront-evidence"></a>

Gambio migration can affect search visibility and storefront usability if SEO and content paths are not prepared. Product records and category records are only part of the storefront. URLs, metadata, static pages, content pages, navigation, redirects, sitemaps, robots directives, and layout decisions can affect how the migrated store performs after launch.

#### Identify high-value URLs and page types <a href="#identify-high-value-urls-and-page-types" id="identify-high-value-urls-and-page-types"></a>

Create a list of high-value source pages before migration. Include product URLs, category URLs, landing pages, content pages, brand or manufacturer pages, campaign pages, and any pages with significant organic traffic, paid campaign use, backlinks, affiliate traffic, or internal linking importance.

The preparation should also record title tags, meta descriptions, URL patterns, static pages, and content areas that need continuity. If a URL cannot be preserved directly, redirect planning should be handled deliberately rather than discovered after launch.

#### Prepare storefront design and content dependencies <a href="#prepare-storefront-design-and-content-dependencies" id="prepare-storefront-design-and-content-dependencies"></a>

Gambio layout, themes, StyleEdit work, custom themes, content areas, modules, and storefront configuration should be documented separately from migrated records. Migration should provide the data foundation; implementation work may still be needed to make the storefront look and behave as intended.

If the source store depends on custom templates, app-generated landing pages, custom navigation, content modules, or special merchandising blocks, those dependencies should be identified before the migration is judged.

### Preparation Priority 8: Inventory Integrations, Modules, and Custom Behavior <a href="#preparation-priority-8-inventory-integrations-modules-and-custom-behavior" id="preparation-priority-8-inventory-integrations-modules-and-custom-behavior"></a>

Gambio merchants may use payment services, shipping services, ERP/accounting systems, marketplaces, shopping portals, analytics, legal text services, marketing systems, templates, modules, programming services, and other integrations. These dependencies can affect migration scope even when the standard records look straightforward.

#### Build an integration inventory <a href="#build-an-integration-inventory" id="build-an-integration-inventory"></a>

The integration inventory should list each system, what it controls, and whether it affects migrated data, future configuration, or launch readiness.

| Dependency type                            | Examples of what to document                                           | Migration implication                                                              |
| ------------------------------------------ | ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Payment and shipping services              | Gateways, shipping providers, labels, tracking, fulfillment references | Historical order readability and future configuration may require separate review. |
| ERP/accounting systems                     | Product identifiers, stock, invoices, order exports, customer codes    | External identifiers or third-party data may require Custom Service review.        |
| Marketplace and portal feeds               | Product feeds, marketplace orders, shopping portals, advertising feeds | Feed-owned records may not equal native Gambio records.                            |
| SEO, analytics, and marketing systems      | Tracking, metadata, redirects, campaign landing pages, newsletters     | Storefront and reporting continuity may require configuration beyond migration.    |
| Theme, module, or custom code dependencies | Custom templates, modules, design changes, checkout customizations     | Bespoke behavior may require implementation or Custom Service review.              |

#### Escalate custom source behavior before execution <a href="#escalate-custom-source-behavior-before-execution" id="escalate-custom-source-behavior-before-execution"></a>

Custom Service should be reviewed when the source store includes Custom Platform data, unsupported custom fields, app-owned records, bespoke price logic, custom order workflows, third-party identifiers, custom integration data, or custom migration logic adjustment. These issues should be identified before Demo Migration whenever possible so expectations are clear.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

Preparation is easier when it follows a clear sequence. The merchant does not need to solve every configuration issue before the first Demo Migration, but the important evidence should be available before results are interpreted.

1. Confirm whether the Target Platform will be Gambio Cloud or self-hosted Gambio.
2. Collect source access, export access, target access, and stakeholder responsibilities.
3. Inventory products, categories, variants, properties, attributes, images, stock, downloads, reviews, filters, and special pricing.
4. Document customer groups, B2B/B2C segmentation, guest/customer account behavior, and customer-group pricing rules.
5. Select customer and order samples that reveal normal and exceptional operating behavior.
6. Document taxes, currencies, languages, shipping methods, payment methods, invoice expectations, delivery notes, and legal-display requirements.
7. Collect high-value URLs, metadata, content pages, static pages, sitemap/robots context, and redirect priorities.
8. Inventory themes, StyleEdit changes, modules, custom themes, custom code, and frontend implementation dependencies.
9. Identify integrations and external systems that affect product, customer, order, stock, payment, shipping, or reporting behavior.
10. Decide whether any issue requires Add-on review, Managed Service support, or Custom Service review before execution.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should test the records that expose Gambio-specific meaning. It should not be limited to easy records that are unlikely to reveal structural issues.

A strong Demo Migration sample set should include:

* simple products and variant-heavy products;
* products with multiple images, filters, cross-selling, reviews, downloadable files, or special pricing;
* products linked to customer group prices or B2B behavior;
* categories and subcategories that drive important storefront discovery;
* normal retail customers and customer-group or B2B customers;
* guest checkout examples if important;
* orders with discounts, taxes, shipping, payment methods, different statuses, and variant products;
* content pages, high-value URLs, metadata, or storefront paths that matter for launch;
* records affected by integrations, external identifiers, or custom fields.

The sample should be large enough to expose meaning but focused enough to review carefully. A merchant who cannot explain why each sample was chosen is likely to miss important validation signals.

### What to Escalate Before Migration <a href="#what-to-escalate-before-migration" id="what-to-escalate-before-migration"></a>

Some issues should not wait until after Demo Migration. They should be reviewed early because they can change the service path, Add-on need, or expected outcome.

Escalate early when:

* the source is a Custom Platform;
* product variants, properties, attributes, or custom fields are inconsistent or non-standard;
* customer group pricing, B2B pricing, or tax treatment is controlled by custom logic;
* order statuses, invoices, fulfillment, or returns depend on third-party systems;
* payment, shipping, ERP, accounting, marketplace, or analytics data includes external identifiers that must be preserved;
* SEO continuity requires complex URL mapping or redirect planning;
* the source storefront relies on custom design, modules, or bespoke theme behavior;
* the target requires self-hosted technical customization or custom integration work;
* Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment may be required.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio preparation should create a clear picture of the future shop before migration begins. The most important work is not simply counting products, customers, and orders. It is clarifying how the source store sells, prices, displays, fulfills, communicates, integrates, and supports customers, then deciding how that meaning should appear in Gambio.

The strongest preparation files combine catalog evidence, customer group logic, order examples, configuration notes, SEO priorities, storefront dependencies, integration inventory, and Demo Migration samples. This allows the merchant to judge migration results by operating meaning rather than by surface-level record presence.

Before starting migration to Gambio, prepare representative product, customer, order, SEO, configuration, and integration evidence, then use Demo Migration to test the records that carry real business meaning. If the source store includes Custom Platform data, complex variants, customer-group pricing, custom order workflows, external identifiers, or bespoke integration behavior, review the selected migration path through Live Chat so the right Standard Service, Managed Service, Custom Service, and Add-on boundaries are clear before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to Gambio?**

Confirm whether the target will be Gambio Cloud or self-hosted Gambio, then prepare the catalog structure, customer groups, order samples, tax/shipping/payment settings, SEO priorities, storefront dependencies, and integration inventory. The operating model affects how the rest of the preparation should be interpreted.

**Should Gambio preparation include SEO and content pages?**

Yes. Gambio migration planning should include high-value product URLs, category URLs, content pages, metadata, static pages, navigation paths, sitemap/robots context, and redirect priorities. SEO and content continuity can affect launch quality even when core store records migrate correctly.

**How should product variants be prepared for Gambio migration?**

Prepare examples of simple products, variant-heavy products, products with different prices or stock behavior, products with multiple images, and products with special pricing or customer group relevance. These examples help test whether shopper choices and order line meaning remain clear after migration.

**Why are customer groups important before migrating to Gambio?**

Customer groups may affect pricing, B2B/B2C segmentation, discounts, tax context, visibility, and order interpretation. If these groups are not documented before migration, customers may appear correctly while their commercial meaning is incomplete.

**When should Custom Service be reviewed during preparation?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported custom fields, app-owned data, bespoke price rules, custom order statuses, third-party identifiers, external integration data, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment beyond standard service capability.
