# Entity Relationships: How Store Data Connects

A migrated store can contain the right records and still behave incorrectly if the connections between those records are broken.

Products, Customers, Orders, Reviews, Coupons, Categories, Taxes, Manufacturers, CMS Pages, and Blog Posts do not work as isolated pieces of information. They support catalog structure, purchase history, customer context, review credibility, promotional behavior, and content continuity because they remain connected in the right way.

Entity relationships explain those connections. They show why migration success should not be judged by record totals alone, and why validation needs to check whether migrated data still supports real business use in the Target Platform.

### What an entity relationship is

An entity is a separate data object in the store, such as a Product, Customer, Order, Category, Review, Coupon, CMS Page, or Blog Post. An entity relationship is a connection between one entity and another entity.

Common relationship examples include:

* Taxes connected to Products
* Manufacturers connected to Products
* Categories connected to Products
* Products connected to Taxes, Manufacturers, Categories, Orders, and Reviews
* Customers connected to Orders and Reviews
* Orders connected to Customers and Products
* Reviews connected to Customers and Products
* Coupons connected to Categories and Products

These relationships matter because the records can exist separately, but the migrated store still needs to rebuild the references between them correctly. If the references are wrong, the Target Platform may contain the records while losing part of the business, meaning those records were supposed to be preserved.

### Independent relationships are not the same as dependency structures

Not every connection in store data works the same way. A useful migration review separates independent-entity relationships from dependency structures.

#### Independent-entity relationships <a href="#independent-entity-relationships" id="independent-entity-relationships"></a>

Independent-entity relationships connect separate entities that can exist as data structures on their own.

Examples include:

* Categories → Products
* Customers → Orders
* Orders → Products
* Reviews → Customers and Products
* Coupons → Categories and Products

In these cases, both sides of the relationship are separate entities. The migration process must preserve the reference between them so the Target Platform can still interpret the connection correctly.

#### Dependency structures

Dependency structures are child structures that depend on a parent entity and do not carry the same meaning on their own.

Examples include:

* Products → Variants
* Products → Options
* Customers → Addresses

A variant does not stand on its own without the Product it belongs to. A Product option does not have useful meaning outside its Product context. A Customer address only makes sense as part of the Customer record.

Both types of structure matter, but they create different migration and validation risks. Treating them as the same can lead to weak review samples and missed issues.

### How to read relationship direction

Relationship direction shows which entity needs to reference which other entity.

> Example: Orders → Customers and Products

When a relationship is written as **Orders → Customers, Products**, it means the Order record must be able to reference the correct Customer and the correct purchased Products.

It does not mean Customers and Products are directly related to each other simply because both appear in the same relationship line.

The same reading rule applies to other relationship groups:

* **Reviews → Customers, Products** means Reviews must reference both the reviewer and the reviewed Product.
* **Coupons → Categories, Products** means Coupons must reference the Categories or Products they affect.
* **Products → Categories** means Products must retain the Category relationships that support catalog structure and browsing.

This distinction matters because relationship validation should test the actual business connection, not just whether related record types exist somewhere in the Target Platform.

### Why relationships matter more than totals

Record counts are useful, but they do not prove that a migrated store works correctly.

A migration can show the expected number of Products, Customers, Orders, Reviews, or Coupons while still having relationship problems such as:

* Products assigned to the wrong Categories
* Orders that no longer connect correctly to purchased Products
* Orders that lose usable Customer context
* Reviews that no longer belong to the correct Product or Customer
* Coupons that lose the Product or Category associations that made them useful
* third-party or outside-system data that no longer points to the expected core record

These issues are more serious than a simple count mismatch because they affect how the store is used after launch. A complete-looking dataset can still be operationally unreliable if the relationships are wrong.

### Core relationship logic for migration planning

A practical relationship map helps identify which references need attention before and after migration.

#### Common relationship groups <a href="#common-relationship-groups" id="common-relationship-groups"></a>

| Relationship group                                           | What the relationship supports                                       |
| ------------------------------------------------------------ | -------------------------------------------------------------------- |
| Taxes → Products                                             | Product tax context and calculation behavior                         |
| Manufacturers → Products                                     | Product attribution and catalog classification                       |
| Categories → Products                                        | Catalog structure, browsing, and organization                        |
| Products → Taxes, Manufacturers, Categories, Orders, Reviews | Product context across catalog, purchase history, and review history |
| Customers → Orders, Reviews                                  | Customer account history and review ownership                        |
| Orders → Customers, Products                                 | Purchase history, support lookup, reporting, and fulfillment context |
| Reviews → Customers, Products                                | Review credibility and storefront trust signals                      |
| Coupons → Categories, Products                               | Promotional targeting and discount behavior                          |

The key idea is simple: when one entity references another, the referenced entity must exist in the Target Platform before the relationship can be rebuilt correctly.

**Relationship lines are directional**

Each relationship line should be read directionally. The first entity is connected to the entities that follow it. Entities appearing in the same line are not automatically connected to each other.

This prevents a common misunderstanding: a relationship map is not a loose list of related data types. It is a guide to which references must survive migration.

### Why a defined migration process is necessary

Relationship preservation depends on timing. Later records often need to reference records that already exist in the Target Platform.

Next-Cart uses a fixed entity migration sequence within the migration process:

**Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts**

This sequence helps related records exist before later references need to be rebuilt. Products can receive tax, manufacturer, and Category context before they are referenced by Orders or Reviews. Orders can reconnect to the correct Customers and purchased Products. Reviews can reconnect to both the reviewer and the reviewed Product. Coupons can reconnect to the Categories or Products they affect.

If related entities are missing, handled separately, or manually imported outside the migration process, the Target Platform may contain records but still fail to preserve the intended relationship meaning.

The practical takeaway is that selecting related entities is not enough. Related entities also need to be migrated through a process that preserves the references between them.

### Where third-party apps, plugins, and extensions increase relationship risk

Third-party apps, plugins, modules, extensions, and outside systems can make entity relationships more important, not less.

They may:

* add custom fields that extend product, customer, or order meaning
* create extra conditions for categories, products, or promotions
* add outside-system identifiers used by ERP, CRM, shipping, subscription, loyalty, or automation systems
* create custom logic that depends on the core entity relationships still being correct

This means a store can migrate the main entities successfully and still lose important business meaning if extension-driven relationships are not considered.

This often matters in areas such as:

* custom product data used for filtering, search, bundles, or personalization
* customer segmentation, loyalty context, or account-level rules
* order metadata used for fulfillment, reporting, or support
* product or category rules used by promotions
* outside-system IDs required for downstream workflows

Third-party logic does not replace the need for correct core relationships. If the base references are wrong, extension-driven behavior often becomes even harder to interpret and validate later.

When these layers materially affect data meaning, the requirement should be reviewed before execution. If the expected result cannot be handled through standard service capability, the requirement belongs under Custom Service, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment, depending on the nature of the work.

### Scope sizing is not the same as relationship preservation <a href="#scope-sizing-is-not-the-same-as-relationship-preservation" id="scope-sizing-is-not-the-same-as-relationship-preservation"></a>

One of the most common planning mistakes is treating migration scope as if it controls relationship logic.

Scope sizing helps estimate how much data needs to move. It does not change the sequence needed to preserve data meaning.

#### Why manual shortcuts can break relationships <a href="#why-manual-shortcuts-can-break-relationships" id="why-manual-shortcuts-can-break-relationships"></a>

Relationship problems can appear when merchants try to move the largest datasets first and recreate smaller connected datasets later.

Examples include:

* migrating Orders before Products can break Order-to-Product references
* migrating Reviews before Customers can break review-author relationships
* migrating Coupons before Categories or Products can break promotional associations
* manually importing remaining related data can weaken relationship tracking and make validation harder

If Entity Points are exhausted before all counted records are migrated, the safer continuation path is to upgrade the Entity Points Plan and continue through the purchased service. Continuing through the migration process helps preserve record tracking and relationship handling more reliably than manual import.

### How to validate relationships

Relationship validation should focus on business behavior, not only whether records appear in the Target Platform.

A useful review sample should include:

* Products with important Category placement
* Products that appear in real Orders
* Customers with real Order history
* Reviews tied to representative Products and Customers
* Coupons tied to real Product or Category conditions
* records affected by app-driven, plugin-driven, extension-driven, or outside-system logic

#### Relationship validation questions <a href="#relationship-validation-questions" id="relationship-validation-questions"></a>

Use practical business questions during review:

* Do Orders still point to the Products the Customer actually bought?
* Do Orders still retain usable Customer context?
* Do Reviews still belong to the correct Products and Customers?
* Do Coupons still apply to the Products or Categories they were meant to affect?
* Do Category-Product relationships still support the intended browse paths?
* Does app-driven or outside-system logic still have the base references it depends on?

A Demo Migration sample should include records with real relationship complexity. Simple records may transfer cleanly while more connected records reveal risks that matter before Full Migration.

### Common relationship mistakes

Common mistakes include:

* approving migration results based on totals alone
* treating independent-entity relationships and dependency structures as the same thing
* assuming all entities in one relationship line are directly connected to each other
* selecting related entities but handling them outside the defined migration process
* letting scope-sizing logic override relationship logic
* ignoring third-party app, plugin, module, extension, or outside-system context until late review
* reviewing only simple records that do not expose relationship complexity

These mistakes matter because relationships are part of what makes migrated data usable. They connect records into a working business system instead of leaving the Target Platform with disconnected data fragments.

### Conclusion

Entity relationships explain why migration success cannot be judged by record totals alone. A store works because separate records continue to point to the right related records in the right way. That is true for Orders and Products, Reviews and Customers, Coupons and Categories, and the wider catalog and customer structure that supports daily commerce behavior.

The safest planning approach is to identify the relationships that matter most, distinguish them from dependency structures, preserve the defined migration sequence that allows references to be rebuilt correctly, and review representative cases early, especially where apps, plugins, modules, extensions, custom fields, or outside systems add extra meaning.

Run a Demo Migration with records that contain real relationship complexity, not only simple Products or Customers. If the store depends on custom fields, third-party logic, outside-system identifiers, or non-standard relationship behavior, use Live Chat to clarify what needs closer review before continuing toward Full Migration.

### FAQs

**Why are entity relationships more important than record counts?**

Because counts only show that records exist. They do not show whether the store still works correctly. Orders can be present without pointing to the right Products, Reviews can be present without pointing to the right Customer or Product, and Coupons can be present without the Product or Category associations that make them usable.

**Why does migration sequence matter for relationships?**

Later records often need to reference earlier records. A defined migration sequence helps related data exist in the Target Platform before later references need to be rebuilt.

**Are variants and options the same kind of relationship as Orders and Reviews?**

No. Variants and options are dependency structures under a Product. Orders and Reviews are separate entities that reference other separate entities. This distinction matters because dependency structures and independent-entity relationships create different migration and validation risks.

**What should happen if Entity Points run out before all related data is migrated?**

The safer path is to upgrade the Entity Points Plan and continue through the purchased service. Manually importing remaining related data can weaken record tracking and relationship handling, especially when later records need to reconnect to already migrated records.

**How do third-party apps, plugins, modules, and extensions affect entity relationships?**

They can add custom fields, outside-system identifiers, metadata, or rules that depend on core Product, Customer, Order, Category, Coupon, or Review relationships. If the base relationships are wrong, app-driven or extension-driven behavior becomes harder to trust after migration.

**How can I review whether relationships were preserved correctly?**

Review representative records with real connections: Orders with Products and Customers, Reviews with Products and Customers, Coupons with Product or Category conditions, and records affected by custom fields or third-party logic. The goal is to confirm that migrated records still support the business behavior they supported before migration.
