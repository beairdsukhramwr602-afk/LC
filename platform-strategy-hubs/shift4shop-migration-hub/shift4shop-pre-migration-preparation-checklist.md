# Shift4Shop Pre-Migration Preparation Checklist

A Shift4Shop migration is easier to evaluate when the merchant prepares the business meaning behind the source data before the migration process begins. Products, customers, orders, CMS Pages, Blog Posts, pricing rules, SEO routes, integrations, and custom fields may all appear as ordinary records in the Source Platform, but they do not always carry ordinary meaning. Some records decide how buyers find products, how wholesale pricing applies, how staff interpret orders, or how the new storefront preserves search visibility after launch.

Preparation should not become a raw export exercise. The useful question is not only _what data exists_. The useful question is _which data must still work as commerce behavior in Shift4Shop_. A small B2C store with simple products may need a lighter readiness pass. A store with B2B buyers, customer-type pricing, option-heavy products, important content routes, custom fields, or integration-owned workflow needs more deliberate preparation before Demo Migration or Full Migration can be interpreted confidently.

The checklist below is designed to turn preparation into reviewable evidence. It helps identify what should be preserved, what can be simplified, what should be cleaned, what needs Add-on planning, and what should be escalated to Custom Service before migration execution.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation reduces interpretation risk. A migration can appear successful at the record level while still leaving important business logic unclear. Products may move without the right buying choices. Customers may move without the pricing or account treatment they need. Orders may move without enough fulfillment, discount, tax, payment, or staff-note context. Important content may move while high-value routes, SEO meaning, or landing-page purpose becomes weaker.

For Shift4Shop, preparation should answer four practical questions before execution:

| Preparation question                                    | Why it matters for Shift4Shop migration                                                                                                                                      |
| ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **What should the target store do after launch?**       | The answer determines whether the migration should preserve the current operating model, simplify old structures, or support a more deliberate hosted commerce setup.        |
| **Which records carry business behavior?**              | Products, customers, pricing rules, orders, and content may need to preserve more than field values. They may control buying, visibility, account treatment, and operations. |
| **Which source-side structures are unclear or custom?** | Apps, custom fields, old export logic, modified platform behavior, and outside-system identifiers may need mapping, configuration, or Custom Service review.                 |
| **Which samples should prove the migration result?**    | Demo Migration is useful only when the sample includes ordinary records and records that reveal real Shift4Shop-specific planning risk.                                      |

Good preparation also prevents the merchant from treating entered entity counts as migration filters. Product, Customer, Order, and Blog quantities are used for Entity Points calculation and Entity Points Plan selection. They do not decide which records move. All scanned records are migrated by default unless filtering is configured.

### Preparation Priority 1: Define the Target Store Role <a href="#preparation-priority-1-define-the-target-store-role" id="preparation-priority-1-define-the-target-store-role"></a>

Before reviewing source records, define what Shift4Shop is expected to become after launch. This short decision shapes every later preparation task.

#### Preserve, simplify, or redesign <a href="#preserve-simplify-or-redesign" id="preserve-simplify-or-redesign"></a>

Some merchants want Shift4Shop to preserve the existing storefront as closely as possible. Others use the migration to simplify product data, retire old pages, remove unused customer segments, consolidate categories, or reduce dependency on custom maintenance. Both goals can be valid, but they require different preparation.

A preservation-focused migration needs evidence for existing workflows that must continue. A simplification-focused migration needs decisions about what should be migrated, retired, filtered, mapped differently, or reconfigured in the Target Platform.

#### Clarify the selling model <a href="#clarify-the-selling-model" id="clarify-the-selling-model"></a>

Document whether the future store will support:

* ordinary B2C purchasing
* wholesale or B2B buyers
* both B2B and B2C buying from the same business
* customer-type or quantity pricing
* digital products, technical products, configurable products, or product options
* content-supported buying decisions
* integrations that affect payment, shipping, tax, inventory, fulfillment, or reporting

This does not need to be a long strategy document. It should be clear enough that preparation decisions can be judged against the future operating model, not only against the source database.

### Preparation Priority 2: Classify Catalog Behavior <a href="#preparation-priority-2-classify-catalog-behavior" id="preparation-priority-2-classify-catalog-behavior"></a>

Catalog preparation should group products by selling behavior, not only by category or SKU count. Shift4Shop product data needs to become usable for customers who must find, understand, configure, price, and purchase the correct item.

#### Identify ordinary and high-risk product groups <a href="#identify-ordinary-and-high-risk-product-groups" id="identify-ordinary-and-high-risk-product-groups"></a>

Prepare representative examples from each product behavior type that matters:

| Product behavior to review               | What to prepare                                                                                                  | Why it matters                                                                           |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Simple products**                      | Standard products with ordinary price, SKU, image, description, inventory, and category assignment.              | These prove the baseline product migration result.                                       |
| **Products with choices or options**     | Items with selectable sizes, colors, materials, add-ons, personalization, or variation-like behavior.            | These reveal whether buying choices remain clear and usable.                             |
| **Wholesale or quantity-based products** | Products affected by minimum quantities, tiered prices, customer-type pricing, packs, or bulk buying.            | These connect catalog structure to buyer treatment and pricing behavior.                 |
| **Technical or content-rich products**   | Items with specifications, compatibility notes, videos, documents, Product Q\&A, reviews, or long-form guidance. | These determine whether product pages still support informed purchasing.                 |
| **Custom or extension-shaped products**  | Products whose meaning depends on custom fields, app data, source modifications, or external systems.            | These may need Advanced Data Mapping, Advanced Data Configure, or Custom Service review. |

#### Separate useful complexity from inherited clutter <a href="#separate-useful-complexity-from-inherited-clutter" id="separate-useful-complexity-from-inherited-clutter"></a>

A complex catalog is not automatically a problem. Complexity becomes useful when product relationships, options, specifications, and buying logic help customers choose correctly. It becomes risky when years of duplicated SKUs, inconsistent categories, obsolete options, or staff-only notes are treated as if they should all become customer-facing structure.

Before execution, decide which product details should be preserved as sellable structure, which should become reference information, which should be cleaned, and which should be excluded or escalated.

### Preparation Priority 3: Document Categories, Navigation, and Product Discovery <a href="#preparation-priority-3-document-categories-navigation-and-product-discovery" id="preparation-priority-3-document-categories-navigation-and-product-discovery"></a>

Categories are not only folders. In a Shift4Shop migration, category and navigation preparation should show how customers are expected to discover products after launch.

#### Prepare discovery evidence <a href="#prepare-discovery-evidence" id="prepare-discovery-evidence"></a>

Review the current source store for:

* main category hierarchy and subcategory depth
* products assigned to multiple categories
* category descriptions, banners, images, SEO titles, and meta descriptions
* menu items, footer links, and important internal links
* product finders, filters, compatibility paths, or search-driven discovery
* high-value category pages that attract traffic or support buyer decisions
* landing pages that function like catalog entry points

If the Source Platform uses custom navigation, plugin-driven filtering, special search logic, or page-builder category content, do not treat that behavior as ordinary category data. Document the expected outcome so the migration plan can distinguish native records from configuration or custom handling.

#### Decide what must remain visible <a href="#decide-what-must-remain-visible" id="decide-what-must-remain-visible"></a>

Not every source navigation choice deserves preservation. Some categories may be old campaign structures. Some landing pages may be obsolete. Some filter paths may no longer match the future catalog. Preparation should identify which discovery paths are launch-critical and which can be retired, redirected, or rebuilt differently in Shift4Shop.

### Preparation Priority 4: Separate Customer Identity from Customer Treatment <a href="#preparation-priority-4-separate-customer-identity-from-customer-treatment" id="preparation-priority-4-separate-customer-identity-from-customer-treatment"></a>

Customer preparation should not stop at names, emails, billing addresses, and shipping addresses. For Shift4Shop, customer records may also affect pricing, tax treatment, wholesale access, payment expectations, and repeat-order behavior.

#### Prepare customer treatment groups <a href="#prepare-customer-treatment-groups" id="prepare-customer-treatment-groups"></a>

Classify customers into practical groups such as:

* ordinary retail customers
* wholesale customers
* customer types or account segments
* VIP or loyalty-related customers
* tax-exempt buyers
* customers with quantity pricing or customer-specific pricing expectations
* buyers linked to sales reps, CRM records, account managers, purchase orders, or external identifiers
* customers whose treatment depends on custom fields, tags, notes, approval states, or third-party data

The purpose is to decide which customer information should become usable platform behavior and which information only needs to remain available for reference.

#### Identify where rules come from <a href="#identify-where-rules-come-from" id="identify-where-rules-come-from"></a>

If customer treatment is controlled by source-store rules, prepare representative examples. If it is controlled by staff memory, spreadsheets, ERP data, CRM records, or custom code, document that dependency before execution. Migration cannot safely preserve buyer treatment that has not been defined.

### Preparation Priority 5: Review Pricing, Coupons, Discounts, and Wholesale Logic <a href="#preparation-priority-5-review-pricing-coupons-discounts-and-wholesale-logic" id="preparation-priority-5-review-pricing-coupons-discounts-and-wholesale-logic"></a>

Pricing records often behave like business rules, not static values. A migrated price is useful only if it reaches the right product, customer, quantity, date, or checkout condition.

#### Classify price-related logic <a href="#classify-price-related-logic" id="classify-price-related-logic"></a>

Prepare examples for:

* base prices and sale prices
* quantity pricing or tiered pricing
* wholesale pricing
* customer-type or customer-group pricing
* coupons and promotion rules
* free shipping conditions
* minimum order requirements
* discounts limited by product, category, customer, date, or order value
* expired promotions or historical rules that should not continue after launch

Mark each rule as **launch-critical**, **active but reviewable**, **historical/reference-only**, or **ready to retire**. This prevents obsolete promotions from receiving the same planning weight as rules that still affect revenue.

#### Decide whether the need is standard, Add-on-supported, or custom <a href="#decide-whether-the-need-is-standard-add-on-supported-or-custom" id="decide-whether-the-need-is-standard-add-on-supported-or-custom"></a>

Some pricing and rule preparation may fit standard migration capability. Some cases may need Standard Add-ons for filtering, mapping, or configuration. Requirements that depend on modified Add-ons, new project-specific Add-ons, custom source behavior, Custom Platform handling, or custom migration logic adjustment belong in Custom Service.

### Preparation Priority 6: Prepare Order History by Operational Use <a href="#preparation-priority-6-prepare-order-history-by-operational-use" id="preparation-priority-6-prepare-order-history-by-operational-use"></a>

Order history preparation should be based on how orders will be used after migration. A merchant may need historical orders for customer service, staff reference, accounting review, fulfillment investigation, tax review, repeat purchasing, or B2B account context.

#### Classify meaningful order examples <a href="#classify-meaningful-order-examples" id="classify-meaningful-order-examples"></a>

Prepare samples of:

* ordinary completed orders
* pending, canceled, refunded, partially refunded, or failed orders
* orders with coupons, discounts, rewards, store credit, or custom fees
* orders with unusual payment methods, payment references, or manual payment handling
* orders with complex shipping, freight, pickup, dropshipping, or multi-package fulfillment
* orders tied to wholesale buyers, purchase orders, quotes, invoices, account managers, or external systems
* orders with staff notes, customer notes, internal statuses, or custom fields

The purpose is not to make every old order behave like a new checkout. The purpose is to preserve enough order meaning that customers and staff can understand historical activity after launch.

### Preparation Priority 7: Inventory CMS Pages, Blog Posts, and High-Value Routes <a href="#preparation-priority-7-inventory-cms-pages-blog-posts-and-high-value-routes" id="preparation-priority-7-inventory-cms-pages-blog-posts-and-high-value-routes"></a>

Content preparation should separate ordinary content from launch-critical or SEO-critical content. Shift4Shop can support storefront pages, marketing content, themes, and SEO-oriented presentation, but source content may include layouts, embedded scripts, forms, videos, calculators, product education, or campaign pages that do not migrate as simple text.

#### Prepare content by business value <a href="#prepare-content-by-business-value" id="prepare-content-by-business-value"></a>

Create a content inventory that identifies:

* CMS Pages that must remain active at launch
* Blog Posts that still attract traffic or support customers
* policy pages such as shipping, returns, privacy, warranty, wholesale terms, and payment terms
* buying guides, sizing guides, compatibility guides, technical resources, or product education pages
* campaign landing pages and seasonal pages
* high-traffic URLs and high-value SEO routes
* pages with embedded forms, scripts, videos, calculators, or custom layouts
* pages that should be retired, redirected, consolidated, or rewritten

For each important route, decide whether the target outcome is exact route preservation, content migration with a new layout, redirect coverage, or retirement.

### Preparation Priority 8: Map Integrations, External Systems, and Custom Fields <a href="#preparation-priority-8-map-integrations-external-systems-and-custom-fields" id="preparation-priority-8-map-integrations-external-systems-and-custom-fields"></a>

A Shift4Shop migration can look simple at the record level while still depending on data owned outside the ecommerce platform. Integration-owned behavior should be identified before execution because it may affect how migrated data should be interpreted.

#### Identify ownership of operational truth <a href="#identify-ownership-of-operational-truth" id="identify-ownership-of-operational-truth"></a>

Document dependencies such as:

| Dependency area                       | Preparation question                                                                                                                    |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **Payments**                          | Which payment references, methods, statuses, or fraud-review details need to remain understandable after migration?                     |
| **Shipping and fulfillment**          | Which carriers, freight rules, pickup workflows, labels, tracking values, or fulfillment statuses matter historically or operationally? |
| **Tax and accounting**                | Which tax values, invoices, accounting IDs, or reporting references are needed after launch?                                            |
| **Inventory and marketplace systems** | Which system owns stock truth, warehouse context, marketplace orders, or channel synchronization?                                       |
| **Marketing and customer systems**    | Which email, loyalty, segmentation, review, or CRM data should migrate, reconnect, or remain external?                                  |
| **Custom fields and identifiers**     | Which custom product, customer, order, or content fields affect storefront behavior, staff workflow, reporting, or integrations?        |

For each dependency, decide whether the data should migrate as native Shift4Shop data, migrate as reference information, remain external, be reconnected after launch, be transformed during migration, or be reviewed through Custom Service.

### Preparation Priority 9: Clean Up Source Data Without Hiding Risk <a href="#preparation-priority-9-clean-up-source-data-without-hiding-risk" id="preparation-priority-9-clean-up-source-data-without-hiding-risk"></a>

Cleanup can improve the target result, but it should not erase the evidence needed to judge migration complexity. The safest approach is to classify before deleting, merging, or rewriting.

#### Useful cleanup decisions <a href="#useful-cleanup-decisions" id="useful-cleanup-decisions"></a>

Preparation may include:

* identifying duplicate products and deciding which record is canonical
* separating inactive, hidden, discontinued, draft, and test products from active catalog items
* normalizing obvious SKU, title, option, category, or image inconsistencies
* confirming that customer emails, billing addresses, and shipping addresses are usable
* separating real orders from test orders
* marking old coupons, expired promotions, and outdated customer groups
* flagging old URLs that need redirect decisions
* identifying custom fields that should remain meaningful after migration

Do not clean up the source store in a way that makes Demo Migration artificially easy. If a problem represents a launch risk, include a representative example in the sample set.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

A practical Shift4Shop preparation sequence should move from business intent to migration evidence.

| Step | Preparation action                                               | Output                                                                                                            |
| ---- | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| 1    | Define the target store role and launch priorities.              | A clear statement of what Shift4Shop must support after launch.                                                   |
| 2    | Classify products by selling behavior.                           | Product groups that reveal simple, complex, wholesale, option-heavy, content-rich, and custom-field cases.        |
| 3    | Review categories, navigation, and SEO-critical routes.          | A discovery and route map for launch-critical storefront paths.                                                   |
| 4    | Separate customer identity from customer treatment.              | Buyer groups, pricing expectations, tax cases, and account-treatment examples.                                    |
| 5    | Review pricing, coupon, discount, and wholesale logic.           | A rule list marked by launch importance and migration handling need.                                              |
| 6    | Classify order history by operational use.                       | Order samples that reveal payment, shipping, discount, fulfillment, staff, and external-system context.           |
| 7    | Inventory CMS Pages, Blog Posts, and high-value content.         | A content list marked preserve, migrate, redirect, rewrite, retire, or review.                                    |
| 8    | Map integrations, custom fields, and outside-system identifiers. | A system ownership map showing what should migrate, reconnect, remain external, or receive Custom Service review. |
| 9    | Choose Demo Migration samples.                                   | A representative sample set that includes ordinary records and high-risk records.                                 |

This is a readiness framework, not a technical setup procedure. Its purpose is to make the migration result easier to judge.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration is most useful when the sample is representative and revealing. A random sample may show that common records can move, but it may miss the records that decide whether Shift4Shop is ready for launch.

#### Strong sample categories <a href="#strong-sample-categories" id="strong-sample-categories"></a>

A strong Shift4Shop Demo Migration sample should include:

* one simple product and one complex product
* products with options, technical specifications, rich content, or rich media
* products with wholesale, quantity, or customer-type pricing where relevant
* active categories and one category with important SEO or navigation value
* ordinary retail customers and customers with wholesale, tax, group, or account treatment
* orders with standard checkout history and orders with discounts, shipping complexity, payment context, staff notes, or external references
* CMS Pages or Blog Posts with commercial or SEO importance
* records that depend on custom fields, integrations, or legacy source assumptions
* one or more high-value URLs where redirect or route behavior matters

#### What the sample should prove <a href="#what-the-sample-should-prove" id="what-the-sample-should-prove"></a>

| Sample area                           | What it should reveal                                                                                   |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Catalog**                           | Whether products remain understandable and purchasable inside Shift4Shop.                               |
| **Customers**                         | Whether buyer identity and buyer treatment remain distinguishable.                                      |
| **Pricing and discounts**             | Whether commercial rules still apply to the right products, buyers, quantities, or checkout conditions. |
| **Orders**                            | Whether staff can interpret historical order activity after migration.                                  |
| **Content and routes**                | Whether important pages, posts, and URLs retain business or SEO value.                                  |
| **Custom or integration-shaped data** | Whether the source behavior needs mapping, configuration, Add-on review, or Custom Service review.      |

A Demo Migration sample should not avoid difficult records. It should expose them early enough for the migration approach to be adjusted before broader execution.

### Custom Platform and Custom Data Preparation <a href="#custom-platform-and-custom-data-preparation" id="custom-platform-and-custom-data-preparation"></a>

If the Source Platform is a Custom Platform, a heavily customized hosted store, a modified open-source installation, or a system shaped by private database structures, prepare the custom data layer before execution. Custom Platform sources require Custom Service because standard service capability cannot assume a stable source data model.

Useful preparation includes:

* source schema samples or export examples
* definitions for custom product, customer, order, content, and integration fields
* explanations of what each custom field means operationally
* examples where custom data changes pricing, visibility, fulfillment, SEO, reporting, or staff workflow
* mapping expectations for what should become native Shift4Shop data, reference information, or custom migration output
* API, database, export-access, or third-party access constraints that may affect review

Without this explanation, custom fields can move as text while the behavior they supported is lost.

### What Should Be Escalated Before Execution <a href="#what-should-be-escalated-before-execution" id="what-should-be-escalated-before-execution"></a>

Escalate requirements before execution when ordinary record movement is not enough to judge the intended result.

| Escalation signal                                                                                                                   | Why it should be reviewed early                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Customer-specific pricing or buyer treatment depends on custom data**                                                             | The result may require mapping, configuration, tailored handling, or custom migration logic adjustment.                                      |
| **Catalog behavior depends on custom product types, bundles, kits, personalization, compatibility rules, or extension-owned logic** | The source behavior may not translate as ordinary product data.                                                                              |
| **SEO or route requirements need deliberate preservation**                                                                          | Important pages may need redirect planning, layout decisions, or route review before launch.                                                 |
| **Order history must preserve custom operational states, invoices, staff notes, or external references**                            | Historical records may need more than basic order fields to remain useful.                                                                   |
| **Integration-owned data is expected to become usable Target Platform behavior**                                                    | Ownership and reconnection responsibilities must be clarified before the migration is judged.                                                |
| **Only selected records should move**                                                                                               | Entered entity counts are not filters; selective migration should be planned through the Data Filter Add-on or custom handling where needed. |
| **Source fields do not naturally align with Shift4Shop-supported structures**                                                       | Advanced Data Mapping, Advanced Data Configure, or Custom Service review may be needed.                                                      |
| **The source is a Custom Platform or heavily modified platform**                                                                    | Custom Service review is required before reliable migration logic can be planned.                                                            |

Standard Add-ons can help when the need fits available settings and supported behavior for filtering, mapping, or configuration. Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, Custom Platform handling, and broader bespoke handling belong in Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for a Shift4Shop migration is not mainly about making larger spreadsheets. It is about identifying which parts of the source store carry business meaning and making that meaning visible before migration execution. Catalog behavior, customer treatment, pricing rules, order interpretation, storefront content, SEO routes, integrations, and custom data should all be reviewed through the question of how they need to work in Shift4Shop after launch.

A well-prepared migration gives Demo Migration a stronger purpose. Instead of showing only that records can appear in the Target Platform, it helps reveal whether the target store can preserve the commercial, operational, and storefront logic that matters most.

Before starting the migration process, prepare a representative record set and use Demo Migration to test the parts of the store that carry the highest business meaning. If the sample exposes unclear mapping, filtering, configuration, custom-field, or integration requirements, use Live Chat to confirm whether the requirement fits standard service capability, a Standard Add-on, or Custom Service before moving into broader execution.

### FAQs <a href="#faqs" id="faqs"></a>

**Should every product be cleaned before migrating to Shift4Shop?**

No. Clean obvious duplicates, outdated records, and inconsistent values where the business decision is clear, but do not remove evidence needed to evaluate migration complexity. Complex products should be included in the review sample, not hidden from it.

**What customer information should be prepared for a Shift4Shop migration?**

Prepare more than names and email addresses. Customer groups, wholesale treatment, tax status, quantity pricing, account notes, approval context, CRM identifiers, and custom fields should be reviewed if they affect how buyers should be treated after migration.

**How should we choose Demo Migration samples?**

Choose samples that reveal real store behavior. Include simple records, high-revenue products, option-heavy products, wholesale or customer-type pricing examples, important customer groups, operationally meaningful orders, key CMS Pages or Blog Posts, and high-value URLs.

**Do entered entity counts filter which records migrate?**

No. Entered Product, Customer, Order, and Blog counts are used for Entity Points calculation and Entity Points Plan selection. They are not migration filters. All scanned records are migrated by default unless filtering is configured through the Data Filter Add-on or custom handling where required.

**When should custom fields be reviewed before migration?**

Custom fields should be reviewed whenever they affect product meaning, customer treatment, pricing, order interpretation, fulfillment, SEO, integration workflows, or staff operations. If those fields require custom migration logic adjustment or cannot be handled through standard service capability, the requirement belongs in Custom Service.

**Should old 3DCart references be removed before planning a Shift4Shop migration?**

Not automatically. Older 3DCart references can help explain source records, exports, URLs, or internal documentation. They should be treated as source context and checked against current Shift4Shop behavior where they affect the target plan.
