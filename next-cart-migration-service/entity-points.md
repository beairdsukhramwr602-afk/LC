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

### Counted Data Types and Coefficients <a href="#counted-data-types-and-coefficients" id="counted-data-types-and-coefficients"></a>

Entity Points are calculated from four data types:

* Product
* Customer
* Order
* Blog Posts

Each counted data type has its own coefficient.

| Counted data type | Coefficient |
| ----------------- | ----------- |
| Product           | 1.0         |
| Customer          | 0.5         |
| Order             | 0.8         |
| Blog Posts        | 0.6         |

The calculation is:

```
Entity Points = (Product x 1.0) + (Customer x 0.5) + (Order x 0.8) + (Blog Posts x 0.6)
```

The coefficient model helps customers estimate capacity more accurately because different data types contribute differently to the total plan requirement.

Other store data may still be migrated depending on platform support and selected scope. This can include taxes, manufacturers, categories, reviews, coupons, CMS Pages, and other supporting structures. Those records can be important to migration quality, but they are not counted in the same weighted way for Entity Points calculation.

This distinction matters because the migration process can include more data types than the Entity Points model counts directly. Entity Points measure selected core capacity; they do not describe every record type that may move from the source store to the target store.

### How Estimate, Plan Capacity, and Consumption Work Together <a href="#how-estimate-plan-capacity-and-consumption-work-together" id="how-estimate-plan-capacity-and-consumption-work-together"></a>

Upon purchase, customers enter estimated quantities for Product, Customer, Order, and Blog Posts. These inputs are converted into Entity Points and allocated to the corresponding counted data types. The selected Entity Points Plan then provides the total capacity available under the purchased service license.

Assume a customer enters the following source-store estimates:

| Counted data type | Estimated count | Coefficient | Estimated Entity Points |
| ----------------- | --------------- | ----------- | ----------------------- |
| Product           | 200             | 1.0         | 200                     |
| Customer          | 200             | 0.5         | 100                     |
| Order             | 150             | 0.8         | 120                     |
| Blog Posts        | 100             | 0.6         | 60                      |
| **Total**         |                 |             | **480**                 |

The estimated requirement is:

```
200 + 100 + 120 + 60 = 480 Entity Points
```

If the customer purchases a plan with 1,000 Entity Points of capacity, the estimated 480 Entity Points are covered and the remaining 520 Entity Points stay available within the purchased plan.

| Capacity layer                   | Entity Points |
| -------------------------------- | ------------- |
| Estimated Product allocation     | 200           |
| Estimated Customer allocation    | 100           |
| Estimated Order allocation       | 120           |
| Estimated Blog Posts allocation  | 60            |
| **Estimated total**              | **480**       |
| **Plan capacity**                | **1,000**     |
| **Remaining available capacity** | **520**       |

The entered quantities support planning and pricing. They do not automatically restrict what the migration process scans or migrates. For example, entering 200 Products estimates Product capacity for purchase planning; it does not instruct the migration process to move only 200 Product records.

If the customer wants to migrate only selected records, the selective-scope requirement should be planned through the Data Filter Add-on. If the filtering needs exceed available settings and supported behavior, the requirement should be reviewed as Custom Service scope.

### When Actual Counted Data Differs from the Estimate <a href="#when-actual-counted-data-differs-from-the-estimate" id="when-actual-counted-data-differs-from-the-estimate"></a>

Actual consumption depends on successfully migrated source-store records, not just on the estimate entered during purchase. If the actual count is higher than expected, the selected Entity Points Plan can still support the migration as long as sufficient available capacity remains.

Consider the same purchase setup: the customer estimates 480 Entity Points and purchases a plan with 1,000 Entity Points of capacity.

| Counted data type | Estimated count | Coefficient | Estimated Entity Points |
| ----------------- | --------------- | ----------- | ----------------------- |
| Product           | 200             | 1.0         | 200                     |
| Customer          | 200             | 0.5         | 100                     |
| Order             | 150             | 0.8         | 120                     |
| Blog Posts        | 100             | 0.6         | 60                      |
| **Total**         |                 |             | **480**                 |

#### Scenario 1: The actual Entity Points usage remains within the plan capacity <a href="#scenario-1-the-actual-entity-points-usage-remains-within-the-plan-capacity" id="scenario-1-the-actual-entity-points-usage-remains-within-the-plan-capacity"></a>

If the actual counted migration consumption reaches 800 Entity Points, the migration can continue within the selected 1,000 Entity Points Plan because the plan has enough available capacity.

| Capacity situation                          | Entity Points |
| ------------------------------------------- | ------------- |
| Plan capacity                               | 1,000         |
| Original estimate                           | 480           |
| Actual counted consumption                  | 800           |
| Capacity remaining after actual consumption | 200           |

The remaining capacity is consumed according to the counted data that is successfully migrated. Customers should not assume the original estimate is a hard limit. The selected plan capacity is the practical boundary.

#### Scenario 2: The actual Entity Points usage exceeds the planned capacity <a href="#scenario-2-the-actual-entity-points-usage-exceeds-the-planned-capacity" id="scenario-2-the-actual-entity-points-usage-exceeds-the-planned-capacity"></a>

If actual counted data exceeds the selected plan capacity, Entity Points are consumed until the plan capacity is used. Entity Points consumption follows the counted core data sequence:

> Product -> Customer -> Order -> Blog Posts

Suppose the same customer purchased a 1,000 Entity Points Plan after estimating 480 Entity Points, but the actual source-store data requires 1,175 Entity Points:

| Counted data type | Actual count | Coefficient | Required Entity Points |
| ----------------- | ------------ | ----------- | ---------------------- |
| Product           | 600          | 1.0         | 600                    |
| Customer          | 600          | 0.5         | 300                    |
| Order             | 250          | 0.8         | 200                    |
| Blog Posts        | 125          | 0.6         | 75                     |
| **Total**         |              |             | **1,175**              |

The 1,000 Entity Points Plan cannot cover the full actual requirement. Capacity is consumed in the counted Entity Points sequence until the available plan capacity runs out.

| Consumption step | Entity Points consumed | Running consumption | Migration status within available capacity             |
| ---------------- | ---------------------- | ------------------- | ------------------------------------------------------ |
| Product          | 600                    | 600                 | 600 Products can be processed.                         |
| Customer         | 300                    | 900                 | 600 Customers can be processed.                        |
| Order            | 100 of 200 required    | 1,000               | 125 Orders can be processed.                           |
| Blog Posts       | 0 of 75 required       | 1,000               | Blog Posts are not processed before capacity runs out. |

In this scenario, the migration can process 600 Products, 600 Customers, and 125 Orders within the purchased plan capacity. The remaining 125 Orders and 125 Blog Posts are not processed until the customer upgrades the Entity Points Plan and resumes migration activity under the purchased service license.

This consumption sequence is separate from the fixed entity migration sequence used during execution:

> Taxes -> Manufacturers -> Categories -> Products -> Customers -> Orders -> Reviews -> Coupons -> CMS Pages -> Blog Posts

Execution order describes how the store data is processed during migration. Entity Points consumption order describes how the counted capacity is consumed for Products, Customers, Orders, and Blog Posts. The two concepts are related to the same migration activity, but they should not be interpreted as the same mechanism.

### Entity Points and Later Migration Activity <a href="#entity-points-and-later-migration-activity" id="entity-points-and-later-migration-activity"></a>

After a successful migration activity under the purchased service license, additional migration actions may involve existing records, newly added records, or a new migration result for the same migration path.

Entity Points should be interpreted by the counted-record status.

| Record situation                                                                  | Entity Points effect                                                                        |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| A counted record is migrated successfully for the first time.                     | Entity Points are consumed based on the data type coefficient.                              |
| A counted record has already been recorded through the service license.           | Entity Points are not consumed again for that same record.                                  |
| New counted records are added to the source store and migrated later.             | Entity Points are consumed when those records are migrated successfully for the first time. |
| A new migration is performed for records already recorded by the service license. | Those already recorded records do not consume Entity Points again.                          |

The useful planning point is simple: Entity Points are tied to counted records and their recorded migration status, not only to the number of times a customer runs migration activity.

### What Happens When Entity Points Run Out <a href="#what-happens-when-entity-points-run-out" id="what-happens-when-entity-points-run-out"></a>

If available Entity Points are consumed before all counted records are migrated, the migration process pauses at the current data processing status. The customer can continue by upgrading the Entity Points Plan.

When upgrading, the customer pays the price difference between the current plan and the higher plan, not the full price of the new plan again. The added Entity Points are distributed to the corresponding data types based on what the customer enters in the plan-upgrade purchase interface.

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

#### “If the real source-store data is higher than my estimate, migration must stop immediately.” <a href="#if-the-real-source-store-data-is-higher-than-my-estimate-migration-must-stop-immediately" id="if-the-real-source-store-data-is-higher-than-my-estimate-migration-must-stop-immediately"></a>

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

### Conclusion <a href="#conclusion" id="conclusion"></a>

Entity Points help customers estimate counted migration capacity by applying a weighted model to Product, Customer, Order, and Blog Posts data. They support plan selection, migration execution, remaining-capacity use, and upgrade decisions under the purchased service license.

The most important distinction is that Entity Points inputs are not migration filters. All scanned records are migrated by default unless filtering is configured, and actual consumption depends on counted records that are successfully migrated. New counted records consume Entity Points when migrated for the first time, while counted records already recorded through the service license do not consume Entity Points again.

Customers should estimate Product, Customer, Order, and Blog Posts counts carefully, consider expected source-store growth, and review selective-scope needs before execution. If the store contains more data than expected, has unused plan capacity, or needs selective filtering, Live Chat can help clarify whether the next step is plan capacity review, Entity Points Plan upgrade, the Data Filter Add-on, or Custom Service review.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What are Entity Points?**

Entity Points are Next-Cart’s weighted capacity model for counted migration data. They help estimate how much capacity a project needs for Product, Customer, Order, and Blog Posts data.

**Which data types count toward Entity Points?**

Entity Points are calculated from Product, Customer, Order, and Blog Posts.

**How are Entity Points calculated?**

Entity Points are calculated using coefficients: Product x 1.0, Customer x 0.5, Order x 0.8, and Blog Posts x 0.6.

**Are the entered entity counts used as migration filters?**

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
