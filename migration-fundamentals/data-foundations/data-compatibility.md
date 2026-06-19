# Data Compatibility

Data compatibility is the difference between moving store records and preserving the business meaning those records carry.

Most e-commerce platforms can store Products, Customers, Orders, categories, content, reviews, discounts, and related data. That does not mean they represent those concepts in the same way. A migration can complete successfully at the record level while the Target Platform interprets product options, category paths, customer groups, order history, discount rules, content URLs, or third-party data differently from the Source Platform.

Compatibility matters because the business does not operate on record totals alone. It depends on behavior: customers finding the right products, staff interpreting orders, customer accounts remaining usable, promotions applying correctly, content retaining continuity, and connected workflows keeping enough context to support daily operations.

### Data Compatibility Is About Preserving Meaning <a href="#data-compatibility-is-about-preserving-meaning" id="data-compatibility-is-about-preserving-meaning"></a>

Data compatibility asks whether the Target Platform can represent migrated data in a way that still supports the store’s intended use after launch.

This is broader than asking whether a data group can be transferred. A product record may move, but option selection may change. A customer record may move, but segmentation logic may not carry the same meaning. An order may move, but staff may lose context that used to come from extensions, custom fields, or outside systems.

| Transfer question          | Compatibility question                                                |
| -------------------------- | --------------------------------------------------------------------- |
| Can the records be moved?  | Will the records still support the same business use?                 |
| Do record totals match?    | Does the Target Platform interpret the data acceptably?               |
| Are Products present?      | Are Products still buyable, discoverable, and understandable?         |
| Are Customers present?     | Are accounts, groups, history, and customer context still usable?     |
| Are Orders present?        | Can staff still interpret order history for service and operations?   |
| Are URLs or pages present? | Do important pages still support navigation, traffic, and continuity? |

A compatibility review therefore looks beyond presence. It asks whether the migrated store still behaves in a way the business can rely on.

### Why Compatibility Breaks Even When Migration Succeeds <a href="#why-compatibility-breaks-even-when-migration-succeeds" id="why-compatibility-breaks-even-when-migration-succeeds"></a>

Compatibility problems usually appear because platforms organize similar concepts differently.

Two platforms may both support variants, categories, discounts, reviews, customer groups, CMS Pages, or Blog Posts. The names may be familiar, but the underlying structure may not match. One platform may treat a concept as a native feature. Another may require an app, extension, rule, field mapping decision, configuration change, or custom handling.

The issue is not always missing data. Often, the data exists but no longer carries the same operational meaning.

Common causes include:

* product options and variants using different structures;
* category, collection, or filter logic changing after migration;
* customer groups or segments losing pricing, visibility, or workflow meaning;
* order history becoming less useful because references or metadata changed;
* discounts, tax rules, reviews, or promotions applying through different models;
* content and URL patterns changing in ways that affect navigation or traffic;
* custom fields, extension data, or outside-system identifiers needing special interpretation.

This is why compatibility should be evaluated with representative examples, not only with record counts.

### Same Label Does Not Mean Same Behavior <a href="#same-label-does-not-mean-same-behavior" id="same-label-does-not-mean-same-behavior"></a>

Many compatibility risks hide behind familiar labels.

A merchant may see Products, categories, Customers, Orders, reviews, and discounts in both platforms and assume that the migration path is straightforward. That assumption can fail when the business depends on a specific behavior behind those labels.

| Familiar label            | Compatibility risk to check                                                                           |
| ------------------------- | ----------------------------------------------------------------------------------------------------- |
| Product options           | Whether option selection, variant pricing, inventory, and media still support purchasing behavior     |
| Categories or collections | Whether browse paths, filters, parent-child meaning, and merchandising logic still work acceptably    |
| Customer groups           | Whether pricing, visibility, tax, approval, loyalty, or segmentation meaning survives                 |
| Orders                    | Whether staff can still interpret purchased items, totals, discounts, taxes, statuses, and notes      |
| Discounts                 | Whether conditions, eligibility, stacking, timing, and product relationships still behave as expected |
| Reviews                   | Whether ownership, product association, visibility, and trust value remain usable                     |
| CMS Pages and Blog Posts  | Whether content structure, metadata, links, media, and URLs retain continuity                         |

The practical test is not whether the Target Platform uses the same word. The practical test is whether the migrated data still supports the outcome the business needs.

### Compatibility Risk Concentrates in Specific Store Areas <a href="#compatibility-risk-concentrates-in-specific-store-areas" id="compatibility-risk-concentrates-in-specific-store-areas"></a>

Compatibility risk is rarely spread evenly across the whole store. Most stores have a few areas where meaning, behavior, or structure matters more than simple transfer.

#### Product Options, Variants, and Purchasability <a href="#product-options-variants-and-purchasability" id="product-options-variants-and-purchasability"></a>

Product compatibility is often the highest revenue-risk area because customers interact with it directly.

Problems can appear when:

* option selection works differently;
* variant-specific pricing, inventory, SKU, image, or availability logic changes;
* configurable, bundled, grouped, personalized, or subscription-like product behavior does not map cleanly;
* attributes move but no longer support the same filtering or comparison behavior;
* app-driven product fields do not become usable Target Platform fields.

A product page can look complete while still creating the wrong buying experience. Compatibility review should therefore include the most complex and commercially important Products, not only simple catalog items.

#### Catalog Structure and Discovery <a href="#catalog-structure-and-discovery" id="catalog-structure-and-discovery"></a>

Catalog compatibility is about whether customers can still find and understand products after migration.

Risk increases when the store depends on:

* deep category trees;
* layered navigation;
* faceted filters;
* attribute-driven search or merchandising;
* collection logic;
* brand, size, color, compatibility, fitment, or use-case browsing;
* category-level content and metadata.

Products may transfer correctly while discovery becomes weaker. If customers used the old structure to browse, compare, filter, or land on search-sensitive pages, catalog compatibility needs early review.

#### Customer Continuity <a href="#customer-continuity" id="customer-continuity"></a>

Customer data is compatible only when it remains useful for account, service, marketing, or operational continuity.

Risk appears when the business depends on:

* customer groups or segments;
* account status or approval workflows;
* B2B pricing or visibility logic;
* tax status;
* loyalty, subscription, or membership context;
* review ownership;
* CRM, support, or outside-system identifiers.

The record may exist after migration, but the business may not be able to use it in the same way. Password behavior also needs realistic planning because platform security rules may prevent exact password continuity.

#### Orders and Operational Usability <a href="#orders-and-operational-usability" id="orders-and-operational-usability"></a>

Order compatibility depends on whether historical orders remain interpretable and useful.

A migrated order should preserve enough context for customer service, reporting, accounting support, refund review, warranty questions, fulfillment reference, and internal operations. Risk increases when orders contain custom fields, complex taxes, discounts, partial shipments, refunds, notes, app-generated metadata, or outside-system references.

An order can be present and still become weaker if staff cannot understand what was purchased, how the total was calculated, which customer context matters, or what operational action the order history supports.

#### Discounts, Taxes, Reviews, and Rule-Based Behavior <a href="#discounts-taxes-reviews-and-rule-based-behavior" id="discounts-taxes-reviews-and-rule-based-behavior"></a>

Some data depends heavily on rules rather than static fields. Discounts, taxes, reviews, customer visibility, product eligibility, and promotion logic may work through different Target Platform models.

Compatibility review should look for rule meaning, not just record presence. A discount that migrates but applies under different conditions is still a compatibility issue. A review that transfers but loses product association or customer trust value is also a compatibility issue.

#### Content, URLs, and Traffic Continuity <a href="#content-urls-and-traffic-continuity" id="content-urls-and-traffic-continuity"></a>

CMS Pages, Blog Posts, product URLs, category URLs, metadata, media references, and internal links can affect customer trust and search continuity.

Compatibility risk increases when the store depends on organic traffic, long-lived landing pages, buying guides, policy pages, product education, category content, or content-led conversion paths. URL structure and redirect planning should be reviewed early enough to support Section 2 SEO continuity work and later validation.

### Third-Party and Custom Data Can Change the Service Path <a href="#third-party-and-custom-data-can-change-the-service-path" id="third-party-and-custom-data-can-change-the-service-path"></a>

Many compatibility issues come from data that does not live entirely inside the default platform model.

Apps, plugins, extensions, custom fields, integrations, and outside systems may carry business meaning that standard core records do not explain. They can affect product merchandising, customer segmentation, order operations, subscriptions, loyalty, reporting, shipping, ERP, CRM, automation, or support workflows.

Not every added data layer must be migrated. Some context may be retired, replaced, recreated, or handled through Target Platform configuration. But when the expected result depends on custom fields, third-party data, outside-system identifiers, special transformation rules, or custom migration logic adjustment, the requirement should be reviewed through Custom Service.

This distinction matters. Add-ons can support optional filtering, mapping, or data configuration needs within service planning. Custom Service is the path for broader customization, modification, bespoke handling, Custom Platform work, unsupported extension data, outside-system identifiers, or custom migration logic adjustment.

### Compatibility Risk Is Usually Low, Moderate, or High <a href="#compatibility-risk-is-usually-low-moderate-or-high" id="compatibility-risk-is-usually-low-moderate-or-high"></a>

Compatibility does not need to be treated as a vague concern. Most stores can be grouped by practical risk level once the important data and behavior requirements are visible.

| Risk level | Typical signals                                                                                                                                                    | Planning implication                                                                      |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Low        | Straightforward catalog, mostly native data, simple promotions, limited app dependency, standard content needs                                                     | Standard review is usually enough if sample results are clean                             |
| Moderate   | Complex variants, layered categories, meaningful SEO dependence, important order-history needs, some custom fields or app context                                  | Migration may fit standard capability, but representative review becomes more important   |
| High       | Heavy app or extension dependency, custom fields, advanced product logic, complex pricing or tax behavior, outside-system identifiers, Custom Platform involvement | Deeper discovery, Custom Service review, and more structured validation are usually safer |

High compatibility risk does not mean the migration should stop. It means the project needs a more realistic service path, better evidence, and stronger validation before launch assumptions become fixed.

### How to Evaluate Compatibility Before Migration <a href="#how-to-evaluate-compatibility-before-migration" id="how-to-evaluate-compatibility-before-migration"></a>

A compatibility review should make business risk visible early without turning the whole project into a technical audit.

#### Define What Must Remain True <a href="#define-what-must-remain-true" id="define-what-must-remain-true"></a>

Start with outcomes, not fields. The business should identify what must remain true after launch for:

* complex Products and buying behavior;
* category navigation, filters, and search-sensitive discovery;
* Customer account and segmentation continuity;
* Order history and staff usability;
* discounts, taxes, reviews, and pricing rules;
* CMS Pages, Blog Posts, URLs, and internal links;
* app-driven, plugin-driven, extension-driven, or outside-system workflows.

These outcomes become the compatibility lens for later review.

#### Choose Representative Data <a href="#choose-representative-data" id="choose-representative-data"></a>

A useful review sample should include the records most likely to expose real complexity:

* the most complex Products;
* the highest-value category paths;
* representative Customers;
* representative Orders with discounts, refunds, notes, or taxes;
* reviews, coupons, or pricing rules where they matter;
* priority URLs, CMS Pages, Blog Posts, and landing pages;
* records affected by custom fields, extensions, integrations, or outside systems.

Easy records can make compatibility look better than it is. Representative records show whether the Target Platform can preserve the meaning that matters.

#### Use Demo Migration as Evidence <a href="#use-demo-migration-as-evidence" id="use-demo-migration-as-evidence"></a>

A Demo Migration is useful because it turns compatibility from an assumption into observable evidence.

The review should ask:

* what mapped cleanly;
* what changed meaning or behavior;
* which data groups need more review;
* whether the result still supports expected business use;
* whether the project fits a standard service path or needs Custom Service.

The goal is not perfection in a sample. The goal is to identify where compatibility is straightforward, where review is needed, and where the service plan should change before full migration work proceeds.

### Custom Platform Compatibility Needs Earlier Review <a href="#custom-platform-compatibility-needs-earlier-review" id="custom-platform-compatibility-needs-earlier-review"></a>

A Custom Platform usually increases compatibility sensitivity because source structure, field meaning, platform behavior, or data extraction logic may require more interpretation.

The important question is not whether visible records can be moved at all. The important question is whether the Target Platform can represent the same business meaning acceptably after the data is interpreted, transformed, mapped, or restructured.

Migration involving a Custom Platform as the Source Platform or Target Platform requires Custom Service because the project depends on custom interpretation, custom structure handling, or custom migration logic adjustment. That does not automatically mean every task is managed end to end by Next-Cart. It means the requirement needs the Custom Service path so the scope and responsibility can be defined correctly.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Data compatibility determines whether migrated records remain useful after the store moves to the Target Platform. The core issue is not only whether data can be transferred. It is whether Products, categories, Customers, Orders, discounts, reviews, CMS Pages, Blog Posts, URLs, custom fields, and connected workflows still preserve enough business meaning to support the store after launch.

The safest approach is to evaluate compatibility with representative data, not easy examples. Product behavior, catalog discovery, customer continuity, order usability, rule-based behavior, content continuity, and third-party context should be checked before the migration path is treated as stable.

When compatibility risk is low, standard service capability may be enough. When the store depends on complex structure, custom data, extension-driven workflows, outside-system identifiers, or Custom Platform handling, Custom Service is usually the safer review path. Use Demo Migration evidence to identify what maps cleanly, what changes meaning, and what needs a stronger service plan before full execution.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the difference between data transfer and data compatibility?**

Data transfer asks whether records can be moved from the Source Platform to the Target Platform. Data compatibility asks whether those records still preserve the same business meaning after migration. A store can transfer Products, Customers, Orders, or content successfully and still have compatibility problems if behavior, structure, rules, or usability changes.

**Why can compatibility break even when record totals match?**

Record totals only show that records exist. They do not prove that the Target Platform interprets those records in the same way. Compatibility can still break through changed variant behavior, weaker category logic, different customer group meaning, less useful order history, changed discount rules, or missing custom-field context.

**Do apps, plugins, extensions, and custom fields increase compatibility risk?**

Yes. They often carry business meaning that is not part of the default platform data model. If important workflows depend on custom fields, extension data, outside-system identifiers, or special transformation rules, the project may need Custom Service review rather than standard mapping assumptions.

**How should a merchant test data compatibility early?**

The best early test is a representative Demo Migration sample. The sample should include complex Products, important category paths, representative Customers and Orders, priority content or URLs, and records affected by custom fields or third-party logic. Reviewing only simple records can hide real compatibility risk.

**Does high compatibility risk mean migration is not possible?**

No. High compatibility risk means the project needs stronger discovery, clearer service planning, and more structured validation. Migration may still be feasible, but the expected result should not be forced into a standard path if preserving business meaning requires customization, transformation, bespoke handling, or custom migration logic adjustment.

**How does Custom Platform involvement affect compatibility?**

Custom Platform involvement usually requires earlier compatibility review because the project may depend on custom interpretation, custom structure handling, or custom migration logic adjustment. Any migration involving a Custom Platform as the Source Platform or Target Platform requires Custom Service so the scope and responsibility can be defined correctly.
