# Entity Points

Entity Points measure the migration capacity under a purchased Next-Cart migration service license. They help customers estimate how much capacity is needed for selected core store data before migration execution and choose an Entity Points Plan that can support the expected scope.

Entity Points are important, but they do not describe the entire migration project. A store can have a clear Entity Points estimate and still need closer review because of platform differences, custom fields, app data, extension data, Add-ons, Custom Service requirements, or validation expectations. Entity Points explain the counted capacity. Migration quality also depends on configuration, platform fit, service scope, and final result verification.

### What Entity Points Measure <a href="#what-entity-points-measure" id="what-entity-points-measure"></a>

Entity Points translate selected core data volume into a weighted capacity value. Instead of treating every counted record as equal, Next-Cart applies different coefficients to the main counted data types. This creates a more practical capacity estimate than a raw record count.

Entity Points help answer several planning questions.

| Planning question                              | What Entity Points clarify                                                                                 |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| How much counted data is expected?             | They convert estimated Product, Customer, Order, and Blog Posts quantities into a weighted capacity value. |
| Which Entity Points Plan may fit?              | The calculated total helps customers choose a plan with enough counted capacity.                           |
| How much plan capacity may be used?            | Successfully migrated counted records consume Entity Points according to their data type.                  |
| Can remaining capacity support later activity? | Unused capacity may support eligible future migration activity under the purchased service license.        |
| Does the estimate control what gets migrated?  | No. Entered quantities support planning and pricing; they are not migration filters.                       |

Entity Points should be read as a capacity model, not a full project-risk model. They help customers plan counted scope, but they do not replace platform review, Add-on planning, Custom Service review, or target-store validation.

### Counted Data Types <a href="#counted-data-types" id="counted-data-types"></a>

Entity Points are calculated from four counted data types:

* Product
* Customer
* Order
* Blog Posts

These are the data types customers enter when estimating migration scope.

Other store data may still be migrated depending on platform support and selected scope. This can include taxes, manufacturers, categories, reviews, coupons, CMS Pages, and other supporting structures. Those records can be important to migration quality, but they are not counted in the same weighted way for Entity Points calculation.

This distinction matters because the migration process can include more data types than the Entity Points model counts directly. Entity Points measure selected core capacity; they do not describe every record type that may move from the source store to the target store.

### Entity Points Coefficients  <a href="#entity-points-coefficients" id="entity-points-coefficients"></a>

Each counted data type has its own coefficient.

| Data type  | Coefficient |
| ---------- | ----------- |
| Product    | 1.0         |
| Customer   | 0.5         |
| Order      | 0.8         |
| Blog Posts | 0.6         |

The calculation is:

```
Entity Points = (Product × 1.0) + (Customer × 0.5) + (Order × 0.8) + (Blog × 0.6)
```

The coefficient model helps customers estimate capacity more accurately because different data types contribute differently to the total plan requirement.

### Example Entity Points Calculation  <a href="#example-entity-points-calculation" id="example-entity-points-calculation"></a>

Assume a customer estimates the following data volume:

| Data type | Estimated count | Coefficient | Entity Points |
| --------- | --------------- | ----------- | ------------- |
| Product   | 200             | 1.0         | 200           |
| Customer  | 200             | 0.5         | 100           |
| Order     | 150             | 0.8         | 120           |
| Blog Post | 100             | 0.6         | 60            |

The total is:

```
200 + 100 + 120 + 60 = 480 Entity Points
```

If the closest suitable Entity Points Plan supports 500 Entity Points, that plan may fit the estimated counted scope.

The estimate should be realistic. If the source store contains more counted records than expected, actual Entity Points consumption may be higher than the number entered during purchase.

### Purchase Estimates and Migration Scope <a href="#purchase-estimates-and-migration-scope" id="purchase-estimates-and-migration-scope"></a>

During purchase, customers enter estimated counts for Product, Customer, Order, and Blog Posts. Next-Cart uses those estimates to calculate Entity Points and help identify a suitable Entity Points Plan.

The entered numbers support pricing and capacity planning. They do not automatically restrict what the migration process scans or migrates.

For example, entering 200 Products means the customer is estimating Product capacity for purchase planning. It does not instruct the migration process to move only 200 Product records.

If the customer wants to migrate only selected records, the selective-scope requirement should be planned through the Data Filter Add-on. If the filtering needs exceed available settings and supported behavior, it should be reviewed as a Custom Service requirement.

### Entity Points Plan Capacity  <a href="#entity-points-plan-capacity" id="entity-points-plan-capacity"></a>

An Entity Points Plan can support more capacity than the customer originally entered during purchase.

For example, if a customer purchases a plan that supports up to 2,000 Entity Points and the actual migration consumes 1,400 Entity Points, the remaining 600 Entity Points stay available within that plan for eligible future migration activity under the purchased service license.

This means the practical capacity boundary is the Entity Points Plan capacity, not only the estimate entered at purchase.

### How Entity Points Are Consumed <a href="#how-entity-points-are-consumed" id="how-entity-points-are-consumed"></a>

Entity Points are consumed when counted records are successfully migrated for the first time under the purchased service license.

In practical terms:

* newly migrated Product records consume Product points;
* newly migrated Customer records consume Customer points;
* newly migrated Order records consume Order points;
* newly migrated Blog Posts records consume Blog Posts points.

Counted records already recorded through the service license do not consume additional Entity Points when migrated again. New counted records consume Entity Points when they are migrated successfully for the first time.

This helps customers distinguish between adding new counted data and processing records that have already been recorded by the service.

### Entity Points Consumption Order  <a href="#entity-points-consumption-order" id="entity-points-consumption-order"></a>

Entity Points consumption follows the counted core data sequence:

> Product -> Customer -> Order -> Blog Posts

This sequence is separate from the fixed entity migration sequence used during execution.

The migration process handles entity types in this order:

> Taxes -> Manufacturers -> Categories -> Products -> Customers -> Orders -> Reviews -> Coupons -> CMS Pages -> Blog Posts

Execution order describes how store data is processed during migration. Entity Points consumption order describes how counted capacity is consumed for the four core data types.

The practical takeaway is that migration order and Entity Points consumption are related to the same migration activity, but they are not the same concept.

### Entity Points and Later Migration Activity <a href="#entity-points-and-later-migration-actions" id="entity-points-and-later-migration-actions"></a>

After a customer has already performed migration activity under the purchased service license, additional migration actions may involve existing records, newly added records, or a new migration result for the same migration path.

Entity Points should be interpreted by the counted-record status.

| Record situation                                                                  | Entity Points effect                                                                        |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| A counted record is migrated successfully for the first time.                     | Entity Points are consumed based on the data type coefficient.                              |
| A counted record has already been recorded through the service license.           | Entity Points are not consumed again for that same record.                                  |
| New counted records are added to the source store and migrated later.             | Entity Points are consumed when those records are migrated successfully for the first time. |
| A new migration is performed for records already recorded by the service license. | Those already recorded records do not consume Entity Points again.                          |

The useful planning point is simple: Entity Points are tied to counted records and their recorded migration status, not only to the number of times a customer runs migration activity.

### How Actual Data Volume Affects Consumption  <a href="#how-actual-data-volume-affects-consumption" id="how-actual-data-volume-affects-consumption"></a>

Actual consumption depends on counted source-store records that are migrated, not only on the estimate entered during purchase.

If the actual source-store data volume is higher than expected, counted data types can consume more Entity Points than planned. If the selected Entity Points Plan still has enough available capacity, migration can continue within that plan; if not the migration will consume all the available Entity Points to perform the migration.

| Data type | Estimated count | Coefficient | Entity Points |
| --------- | --------------- | ----------- | ------------- |
| Product   | 200             | 1.0         | 200           |
| Customer  | 200             | 0.5         | 100           |
| Order     | 150             | 0.8         | 120           |
| Blog Post | 100             | 0.6         | 60            |

The total is:

```
200 + 100 + 120 + 60 = 480 Entity Points
```

Let's use this example to demonstrate the most common scenario the customer can encounter

* the customer estimates 480 Entity Points;
* the selected plan supports up to 1,000 Entity Points;
* the actual counted migration consumption is 1,175 Entity Points with 600 Products, 600 Customers, 250 Orders and 125 Blog Posts
* no filtering is configured.

As in the example, the Entity Points will be distributed after purchase as:

* Product: 200 Entity Points
* Customer: 100 Entity Points
* Order: 120 Entity Points
* Blog Post: 60 Entity Points
* Remaining Available Entity Points: 520 Entity Points

The Next-Cart system will automatically consume the corresponding Entity Points required for the migration of the data, in order: Product → Customer → Order → Blog Post, to perform the migration process.

* Product: 600 Entity Points
* Customer: 300 Entity Points
* Order: 100 Entity Points
* Blog Posts: 0 Entity Points

The customer can still execute the migration, but once the Entity Points are exhausted, the migration will pause at the current migration status until the customer upgrades the Entity Points Plan and resumes it.

In the example, the current migration status is 600 Products, 300 Customers, and 125 Orders successfully migrated to the target store, and the remaining data (125 Orders and 125 Blog Posts) will not be processed until the customer continues the migration under the upgraded Entity Points Plan.

### What Happens When Entity Points Run Out <a href="#what-happens-when-entity-points-run-out" id="what-happens-when-entity-points-run-out"></a>

If available Entity Points are consumed before all counted records are migrated, the migration process will automatically pause at the current data process status.

The customer can continue by upgrading the Entity Points Plan. When upgrading, the customer pays the price difference between the current plan and the higher plan, not the full price of the new plan again.

The added Entity Points are distributed to the corresponding data types based on what the customer enters in the plan-upgrade purchase interface.

Continuing through the purchased service license is safer than manually importing remaining related data outside the migration process. Manual import can weaken record relationships or database integrity, especially when products, customers, orders, categories, reviews, CMS Pages, Blog Posts, and supporting structures need to remain connected.

### What Entity Points Do Not Decide <a href="#what-entity-points-do-not-decide" id="what-entity-points-do-not-decide"></a>

Entity Points do not decide the entire migration outcome.

They do not determine:

* whether the Source Platform and Target Platform represent data in the same way;
* whether product options, variants, attributes, or relationships preserve the expected buying behavior;
* whether important data requires Add-ons;
* whether custom fields, app data, plugin data, extension data, or third-party records require Custom Service;
* whether a Custom Platform is involved;
* whether target-store limitations require tailored handling;
* whether the migrated target store is ready for launch.

Entity Points help plan capacity. Migration success still depends on data preparation, configuration, platform fit, service choice, and validation.

### Common Entity Points Misunderstandings <a href="#common-entity-points-misunderstandings" id="common-entity-points-misunderstandings"></a>

#### “The number I entered is the number that will migrate.” <a href="#the-number-i-entered-is-the-number-that-will-migrate" id="the-number-i-entered-is-the-number-that-will-migrate"></a>

Entered data counts support pricing and Entity Points Plan selection. They are not automatic migration filters.

#### “If the real scan is higher than my estimate, migration must stop immediately.” <a href="#if-the-real-scan-is-higher-than-my-estimate-migration-must-stop-immediately" id="if-the-real-scan-is-higher-than-my-estimate-migration-must-stop-immediately"></a>

Not necessarily. If the selected Entity Points Plan has enough available capacity, migration can continue within that plan.

#### “Unused Entity Points disappear after the first migration.” <a href="#unused-entity-points-disappear-after-the-first-migration" id="unused-entity-points-disappear-after-the-first-migration"></a>

Unused Entity Points within the purchased plan can support eligible future migration activity under the service license.

#### “Only Product, Customer, Order, and Blog Posts data can move.” <a href="#only-product-customer-order-and-blog-posts-data-can-move" id="only-product-customer-order-and-blog-posts-data-can-move"></a>

No. Other supported data types may also move depending on platform support and selected scope. Product, Customer, Order, and Blog Posts are the counted data types used for Entity Points calculation.

#### “Every migrated entity consumes Entity Points.” <a href="#every-migrated-entity-consumes-entity-points" id="every-migrated-entity-consumes-entity-points"></a>

No. Entity Points consumption is tied to counted core data types in the Entity Points model.

#### “Migrating the same recorded entities again always consumes more Entity Points.” <a href="#migrating-the-same-recorded-entities-again-always-consumes-more-entity-points" id="migrating-the-same-recorded-entities-again-always-consumes-more-entity-points"></a>

No. Counted records already recorded through the service license do not consume additional Entity Points when migrated again.

#### “Upgrading Entity Points renews my service license.” <a href="#upgrading-entity-points-renews-my-service-license" id="upgrading-entity-points-renews-my-service-license"></a>

No. Entity Points Plan upgrade increases plan capacity. It does not renew the service license.

#### “Entity Points prove migration complexity.” <a href="#entity-points-prove-migration-complexity" id="entity-points-prove-migration-complexity"></a>

No. Entity Points measure counted capacity. Complexity can still come from platform differences, Add-ons, Custom Service requirements, Custom Platform handling, third-party data, or validation needs.

### Conclusion  <a href="#conclusion" id="conclusion"></a>

Entity Points help customers estimate counted migration capacity by applying a weighted model to Product, Customer, Order, and Blog Posts data. They support pricing, plan selection, migration execution, remaining-capacity use, and upgrade decisions under the purchased service license.

The most important distinction is that Entity Points inputs are not migration filters. All scanned records are migrated by default unless filtering is configured, and actual consumption depends on counted records that are successfully migrated. New counted records consume Entity Points when migrated for the first time, while counted records already recorded through the service license do not consume Entity Points again.

Customers should estimate Product, Customer, Order, and Blog Posts counts carefully, consider expected source-store growth, and review selective-scope needs before execution. If the store contains more data than expected, has unused plan capacity, or needs selective filtering, Live Chat can help clarify whether the next step is plan capacity review, Entity Points Plan upgrade, the Data Filter Add-on, or Custom Service review.

### FAQs  <a href="#faqs" id="faqs"></a>

**What are Entity Points?**

Entity Points are Next-Cart’s weighted capacity model for counted migration data. They help estimate how much capacity a project needs for Product, Customer, Order, and Blog Posts data.

**Which data types count toward Entity Points?**

Entity Points are calculated from Product, Customer, Order, and Blog Posts.

**How are Entity Points calculated?**

Entity Points are calculated using coefficients: Product x 1.0, Customer x 0.5, Order x 0.8, and Blog Posts x 0.6.

**Are entered entity counts used as migration filters?**

No. Entered counts are used for pricing and plan selection. They do not automatically limit which records are migrated.

**What happens if the actual counted data is higher than my estimate?**

If the selected Entity Points Plan still has enough capacity, migration can continue and consume the available points. If available capacity runs out, migration pauses until the plan is upgraded.

**Can unused Entity Points be used later?**

Yes. Unused Entity Points within the purchased plan can support eligible future migration activity under the service license.

**How can I migrate only selected records?**

Selective migration should be planned through the Data Filter Add-on. If the filtering needs exceed available settings and supported behavior, it should be reviewed as a Custom Service requirement.

**What happens when Entity Points run out?**

The migration pauses. The customer can upgrade the Entity Points Plan and pay only the price difference between the current plan and the higher plan.

**Does migrating already recorded entities again consume more Entity Points?**

No. Counted records already recorded through the service license do not consume additional Entity Points when migrated again.

**Do new records consume Entity Points when migrated later?**

Yes. New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated successfully for the first time.
