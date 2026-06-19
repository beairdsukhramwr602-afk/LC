# Entity Relationships

E-commerce data does not work as a set of isolated records. A store works because Products belong to Categories, Orders refer to Customers and purchased Products, Reviews remain attached to the right Products and Customers, Coupons apply to the right catalog areas, and content continues to support the right business context.

Entity relationships are the connections that preserve that meaning. Without them, a migrated store can look complete while behaving incorrectly. Products may appear, Customers may appear, Orders may appear, and counts may look acceptable, but the Target Platform can still lose the references that make the data usable for browsing, purchasing, reporting, service, and continuity.

The practical planning question is not only whether each entity can move. It is whether the relationships among those entities can still support real store operations after migration.

### What Entity Relationships Mean in Migration <a href="#what-entity-relationships-mean-in-migration" id="what-entity-relationships-mean-in-migration"></a>

An entity is a distinct data group in the store, such as Products, Customers, Orders, Categories, Reviews, Coupons, CMS Pages, or Blog Posts. An entity relationship is the connection that lets one entity retain meaning through another entity.

Examples include:

* Categories connected to Products;
* Products connected to Orders and Reviews;
* Customers connected to Orders and Reviews;
* Orders connected to Customers and Products;
* Reviews connected to Products and Customers;
* Coupons connected to Products or Categories;
* CMS Pages and Blog Posts connected to navigation, URLs, links, media, or content structure.

These relationships matter because the business meaning often lives in the connection, not only in the record. An Order is less useful if staff cannot understand which Products were purchased. A Review loses trust value if it no longer belongs to the correct Product. A Coupon loses practical value if it no longer applies to the intended Product or Category conditions.

### Relationships Are Different From Record Presence <a href="#relationships-are-different-from-record-presence" id="relationships-are-different-from-record-presence"></a>

Record presence answers whether data exists in the Target Platform. Relationship preservation answers whether the data still points to the right related data.

| Migration check        | What it proves                      | What it does not prove                                                                                      |
| ---------------------- | ----------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Product count matches  | Product records are present         | Products are assigned to the right Categories, attributes, variants, or connected records                   |
| Customer count matches | Customer records are present        | Customers still have usable Order history, addresses, groups, or review context                             |
| Order count matches    | Order records are present           | Orders still reference the correct Customers, Products, totals, statuses, notes, and purchased-item context |
| Review count matches   | Review records are present          | Reviews still belong to the correct Products and Customers                                                  |
| Coupon count matches   | Coupon records are present          | Coupons still target the correct Products, Categories, conditions, or eligibility rules                     |
| Content count matches  | CMS Pages or Blog Posts are present | URLs, links, media, navigation, and content relationships still support continuity                          |

This is why migration review should not stop at totals. Counts can confirm scope, but relationship checks confirm usability.

### Independent Relationships and Dependency Structures Are Not the Same <a href="#independent-relationships-and-dependency-structures-are-not-the-same" id="independent-relationships-and-dependency-structures-are-not-the-same"></a>

A strong migration plan separates independent relationships from dependency structures because they create different risks.

#### Independent Entity Relationships <a href="#independent-entity-relationships" id="independent-entity-relationships"></a>

Independent relationships connect separate data groups that can exist as distinct entities but need references between them to preserve business meaning.

Common examples include:

* Products connected to Categories;
* Orders connected to Customers and Products;
* Reviews connected to Products and Customers;
* Coupons connected to Products or Categories;
* Customers connected to Orders and Reviews.

In these cases, both sides of the relationship are meaningful data groups. The migration must preserve the reference between them so the Target Platform can still interpret the connection.

#### Dependency Structures <a href="#dependency-structures" id="dependency-structures"></a>

Dependency structures are child structures that depend on a parent record for meaning.

Common examples include:

* Product variants under a Product;
* Product options under a Product;
* Product images under a Product;
* Customer addresses under a Customer;
* order line items under an Order.

A variant does not have full business meaning outside its Product. A Customer address does not stand alone as a useful commerce record. An order line item needs the Order context that gives it purchase meaning.

Both relationship types matter, but they should not be reviewed in the same way. Independent relationships need reference checks across entities. Dependency structures need parent-child checks within the same business object.

### How to Read Relationship Direction <a href="#how-to-read-relationship-direction" id="how-to-read-relationship-direction"></a>

Relationship direction shows which entity needs to retain a reference to another entity.

When a relationship is written as **Orders → Customers, Products**, the Order must retain usable references to the Customer and the purchased Products. It does not mean Customers and Products are automatically related to each other in every context.

The same rule applies across common relationship groups:

| Relationship line              | How to read it                                                | Practical check                                                                |
| ------------------------------ | ------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Products → Categories          | Products must keep the right Category placement               | Can customers browse and find the Product through the expected Category paths? |
| Orders → Customers, Products   | Orders must retain Customer and purchased-Product context     | Can staff interpret the Order history accurately?                              |
| Reviews → Customers, Products  | Reviews must remain tied to the reviewer and reviewed Product | Do review ownership and storefront trust signals still make sense?             |
| Coupons → Products, Categories | Coupons must retain the intended targeting context            | Do discounts still apply to the correct catalog scope?                         |
| Customers → Orders, Reviews    | Customers must retain history and contribution context        | Does the account still show usable purchase and review information?            |

A relationship map is not a loose list of related data types. It is a directional reference map showing which connections must survive migration.

### Why Migration Sequence Matters <a href="#why-migration-sequence-matters" id="why-migration-sequence-matters"></a>

Some data can only reconnect correctly when the referenced records already exist in the Target Platform. That is why migration sequence matters.

Next-Cart uses a defined entity migration sequence within the migration process:

**Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts**

This sequence helps earlier records exist before later records need to reference them. Products can receive tax, manufacturer, and Category context before Orders and Reviews refer to them. Orders can reconnect to Customers and purchased Products. Reviews can reconnect to reviewers and reviewed Products. Coupons can reconnect to the Products or Categories they affect.

The sequence does not remove every compatibility risk. Different platforms may still represent relationships differently. However, it reduces avoidable reference problems by keeping connected data in a controlled order.

### Where Relationship Risk Usually Appears <a href="#where-relationship-risk-usually-appears" id="where-relationship-risk-usually-appears"></a>

Relationship risk concentrates where the store depends on context across multiple data groups.

#### Catalog Structure <a href="#catalog-structure" id="catalog-structure"></a>

Catalog relationships affect browsing, merchandising, filtering, and product discovery.

Risk appears when:

* Products lose Category placement;
* parent-child Category paths change;
* manufacturer, brand, attribute, or collection context changes;
* filters no longer reflect the intended Product structure;
* product images, variants, or options are disconnected from the Product context.

A store can have all Product records present and still be difficult to use if catalog relationships do not carry over acceptably.

#### Purchase History <a href="#purchase-history" id="purchase-history"></a>

Order relationships affect service, reporting, customer support, and internal operations.

Risk appears when:

* Orders lose Customer context;
* Orders no longer show purchased Products clearly;
* line items, totals, taxes, discounts, statuses, or notes lose usable meaning;
* historical Orders cannot be interpreted by support staff;
* outside-system identifiers used by fulfillment, accounting, ERP, CRM, or reporting workflows are no longer connected to the right records.

Purchase history is especially sensitive because it is often used after launch for support and reconciliation, even when the store no longer edits historical records in the same way.

#### Reviews, Coupons, and Rule-Based Data <a href="#reviews-coupons-and-rule-based-data" id="reviews-coupons-and-rule-based-data"></a>

Reviews and Coupons depend heavily on relationship meaning.

Risk appears when:

* Reviews no longer belong to the right Product;
* review author context is missing or weakened;
* Coupons lose Product or Category targeting;
* discount eligibility rules change between platforms;
* promotional logic depends on attributes, groups, tags, or custom fields that do not map directly.

These data groups should be reviewed through real examples, not just presence checks.

#### Content, URLs, and Navigation <a href="#content-urls-and-navigation" id="content-urls-and-navigation"></a>

CMS Pages and Blog Posts may depend on links, media, navigation, metadata, and URL structure.

Risk appears when:

* internal links point to old paths;
* images or embedded media lose context;
* navigation no longer exposes important content;
* Blog Posts and CMS Pages move but no longer support SEO or customer education in the same way;
* redirects are needed because content or catalog URLs change.

Section 2 should treat this as a relationship-awareness issue. Detailed redirect planning and SEO continuity decisions belong to the dedicated SEO and URL articles later in the section.

### Third-Party and Custom Relationships Need Early Attention <a href="#third-party-and-custom-relationships-need-early-attention" id="third-party-and-custom-relationships-need-early-attention"></a>

Apps, plugins, modules, extensions, and outside systems can add relationships that are not obvious in the standard entity list.

They may add:

* custom Product fields used for filtering, personalization, bundles, or search;
* Customer segmentation or loyalty context;
* Order metadata used for fulfillment, reporting, support, or automation;
* Product or Category rules used by promotions;
* outside-system identifiers used by ERP, CRM, shipping, subscription, loyalty, or accounting systems;
* custom logic that depends on Product, Customer, Order, Category, Coupon, Review, CMS Page, or Blog Post references.

These relationships often depend on standard data being correct first. If Product, Customer, Order, Category, Coupon, or Review references are wrong, custom behavior becomes harder to interpret.

When custom fields, unsupported extension data, outside-system identifiers, or non-standard relationship logic materially affect store operations, the requirement should be reviewed before execution. Depending on the requirement, the solution may involve Add-ons, Custom Service, or custom migration logic adjustment. Add-ons support defined filtering, mapping, or configuration needs. Custom Service covers broader custom handling, Custom Platform work, or bespoke migration logic that falls outside standard assumptions.

### Scope Planning Should Not Override Relationship Logic <a href="#scope-planning-should-not-override-relationship-logic" id="scope-planning-should-not-override-relationship-logic"></a>

Migration scope determines what data groups and record volumes need to move. It does not replace relationship logic.

A store owner may be tempted to move the largest or most urgent dataset first, then manually recreate smaller connected data later. That can create relationship problems because later records may need references to earlier records, and manually imported records may not carry the same tracking context.

Common shortcut risks include:

* migrating Orders before related Products are available;
* moving Reviews before Customers or Products can be referenced correctly;
* importing Coupons separately from the Product or Category structure they depend on;
* recreating Categories manually after Product migration;
* leaving related custom fields or outside-system identifiers for late manual handling.

If the migration scope changes or Entity Points are exhausted before all required records are migrated, the safer planning path is to adjust the Entity Points Plan and continue through the purchased service flow rather than splitting connected data into uncontrolled manual work.

### How to Plan Relationship Review <a href="#how-to-plan-relationship-review" id="how-to-plan-relationship-review"></a>

Relationship review should focus on representative business cases.

A useful review sample includes:

* Products assigned to important Categories;
* Products with variants, options, images, attributes, or manufacturer context;
* Customers with real Order history;
* Orders with multiple Products, discounts, taxes, statuses, notes, and support relevance;
* Reviews connected to representative Products and Customers;
* Coupons tied to Product or Category conditions;
* CMS Pages or Blog Posts with links, media, navigation, or SEO relevance;
* records affected by apps, extensions, custom fields, or outside-system identifiers.

The point is to test connected records, not only clean standalone records. Simple samples may transfer cleanly while the records that matter most operationally reveal relationship risk.

### Practical Relationship Questions Before Full Migration <a href="#practical-relationship-questions-before-full-migration" id="practical-relationship-questions-before-full-migration"></a>

Before committing to Full Migration, the review should answer practical relationship questions.

| Area        | Relationship question                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------- |
| Catalog     | Do Products still belong to the correct Categories and retain enough Product context for browsing and buying? |
| Customers   | Do Customers retain usable addresses, account context, Orders, and review relationships?                      |
| Orders      | Do Orders still point to the correct Customers and purchased Products?                                        |
| Reviews     | Do Reviews still support credible Product and Customer context?                                               |
| Coupons     | Do Coupons still target the intended Products, Categories, or eligibility conditions?                         |
| Content     | Do CMS Pages and Blog Posts still support links, media, navigation, and continuity?                           |
| Custom data | Do custom fields, extension data, and outside-system identifiers still point to the expected core records?    |

If the answer is unclear, the issue should be clarified before launch pressure makes correction harder.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Entity relationships explain why migration success cannot be judged by record totals alone. A store works because records remain connected: Products to Categories, Orders to Customers and Products, Reviews to Products and Customers, Coupons to catalog rules, and content to the navigation and URL context that customers and search engines depend on.

The strongest planning approach is to separate independent relationships from dependency structures, respect the migration sequence that allows references to be rebuilt, and review connected real-world samples before Full Migration. Relationship risk increases when a store depends on apps, extensions, custom fields, outside-system identifiers, or non-standard business logic, so those requirements should be identified early and routed through the right service path.

Run a Demo Migration with records that contain real relationship complexity. If important relationships depend on custom fields, unsupported extension data, or outside-system logic, clarify the requirement before proceeding to Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are entity relationships more important than record counts?**

Record counts show whether records are present. They do not prove that the records still point to the right related records. Orders, Reviews, Coupons, Categories, and Products can all be present while the Target Platform still loses important business context.

**What is the difference between an independent relationship and a dependency structure?**

An independent relationship connects separate entities, such as Orders to Customers or Reviews to Products. A dependency structure is a child structure under a parent record, such as variants under a Product or addresses under a Customer. Both matter, but they require different review methods.

**Why does entity migration sequence matter?**

Later records often need to reference earlier records. A defined sequence helps related records exist before later records need to reconnect to them, reducing avoidable reference problems during migration.

**Can manual imports break entity relationships?**

Yes. Manual imports can weaken relationship tracking when connected data is moved outside the controlled migration sequence. This is especially risky for Orders, Reviews, Coupons, Categories, Product relationships, and outside-system identifiers.

**How do apps, plugins, modules, and extensions affect relationships?**

They can add custom fields, metadata, rules, identifiers, or workflows that depend on standard Product, Customer, Order, Category, Coupon, Review, CMS Page, or Blog Post relationships. If those base relationships are wrong, custom behavior becomes harder to trust.

**What should be checked during Demo Migration?**

Use records with real relationship complexity: Products in important Categories, Customers with Orders, Orders with multiple Products and discounts, Reviews tied to Products and Customers, Coupons with targeting rules, and records affected by custom fields or outside-system identifiers.
