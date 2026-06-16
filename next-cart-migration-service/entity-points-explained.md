# Entity Points Explained

Entity Points are Next-Cart’s way of measuring core migration scope and migration capacity within the purchased service. They help customers estimate the counted migration capacity needed for core store data under a purchased migration service license. Entity Points translate selected data volume into a weighted capacity value so customers can choose a suitable Entity Points Plan before migration execution.

Although Entity Points are important, they do not cover the entire migration process. A store can have a clear Entity Points estimate and still require closer planning because of platform data differences, custom fields, app data, extension data, Add-ons, Custom Service requirements, or validation expectations. Entity Points measure counted capacity. Migration quality still depends on configuration, platform fit, service scope, and final result verification.

### What Entity Points Are Designed to Measure <a href="#what-entity-points-are-designed-to-measure" id="what-entity-points-are-designed-to-measure"></a>

Entity Points measure the migration capacity for selected core store data. They help customers understand how much data the purchased service license needs to support.

They are designed to clarify:

| Planning question                              | What Entity Points help answer                                                                                   |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| How much counted data is expected?             | Entity Points turn estimated Product, Customer, Order, and Blog Posts quantities into a weighted capacity value. |
| Which plan may fit the migration?              | The calculated total helps customers select an Entity Points Plan with enough capacity.                          |
| How much plan capacity may be used?            | Successfully migrated counted records consume Entity Points based on their data type.                            |
| Can remaining capacity support later activity? | Unused Entity Points can support eligible future migration activity under the purchased service license.         |
| Does the estimate limit what moves?            | No. Entered quantities support capacity planning; they are not migration filters.                                |

Entity Points should be read as a capacity model, not as a full project-risk model. They help plan counted scope, but they do not replace platform review, Add-on planning, Custom Service review, or validation.

### Which Data Types Count Toward Entity Points  <a href="#which-data-types-count-toward-entity-points" id="which-data-types-count-toward-entity-points"></a>

Entity Points are calculated from four data types:

* Product
* Customer
* Order
* Blog

These are the data types customers enter when estimating migration scope.

Other store data may still be migrated depending on platform support and selected scope. This can include taxes, manufacturers, categories, reviews, coupons, CMS Pages, and other supporting structures.

Those supporting entities can matter greatly for migration quality, but they are not counted in the same weighted way for Entity Points calculation. This distinction helps customers understand why the migration process can include more data types than the Entity Points model counts directly.

### Entity Points Coefficients  <a href="#entity-points-coefficients" id="entity-points-coefficients"></a>

Each counted data type has its own coefficient.

| Data type | Coefficient |
| --------- | ----------- |
| Product   | 1.0         |
| Customer  | 0.5         |
| Order     | 0.8         |
| Blog      | 0.6         |

The formula is:

```
Entity Points = (Product × 1.0) + (Customer × 0.5) + (Order × 0.8) + (Blog × 0.6)
```

This weighted model is more useful than a single raw record count because each counted data type contributes differently to total migration capacity.

### Example Entity Points Calculation  <a href="#example-entity-points-calculation" id="example-entity-points-calculation"></a>

Assume a customer estimates the following data volume:

| Data type | Estimated count | Coefficient | Entity Points |
| --------- | --------------- | ----------- | ------------- |
| Product   | 200             | 1.0         | 200           |
| Customer  | 200             | 0.5         | 100           |
| Order     | 150             | 0.8         | 120           |
| Blog      | 100             | 0.6         | 60            |

The total is:

```
200 + 100 + 120 + 60 = 480 Entity Points
```

If the closest higher available Entity Points Plan supports 500 Entity Points, that plan may fit the estimated counted scope.

The estimate should be realistic. If the source store contains more counted records than expected, actual Entity Points consumption can be higher than the original estimate.

### Entity Points and Purchase Estimates <a href="#entity-points-and-purchase-estimates" id="entity-points-and-purchase-estimates"></a>

During purchase, customers enter estimated counts for Product, Customer, Order, and Blog Posts. Next-Cart uses those estimates to calculate Entity Points and help identify a suitable Entity Points Plan.

The entered numbers support pricing and capacity planning. They do not automatically restrict what the migration process scans or migrates.

For example, entering 200 Products means the customer is estimating Product capacity for purchase planning. It does not tell the migration process to migrate only 200 Product records.

If the customer wants to migrate only selected records, that requirement should be planned through the Data Filter Add-on. If the filtering needs exceed available settings and supported behavior, they should be reviewed as a Custom Service requirement.

### Entity Points Plan Capacity  <a href="#entity-points-plan-capacity" id="entity-points-plan-capacity"></a>

An Entity Points Plan can support more capacity than the customer originally entered during purchase.

For example, if a customer purchases a plan that supports up to 2,000 Entity Points and the actual migration consumes 1,400 Entity Points, the remaining 600 Entity Points stay available within that plan for eligible future use under the purchased service license.

This means the practical capacity boundary is the Entity Points Plan capacity, not only the estimate entered at purchase.

### How Entity Points Are Consumed <a href="#how-entity-points-are-consumed" id="how-entity-points-are-consumed"></a>

Entity Points are consumed when counted data are successfully migrated for the first time under the service license.

In practical terms:

* newly migrated Product records consume Product points;
* newly migrated Customer records consume Customer points;
* newly migrated Order records consume Order points;
* newly migrated Blog Posts consume Blog Posts points.

Records already recorded through the service license do not consume additional Entity Points when migrated again. New counted records consume Entity Points when they are migrated successfully for the first time.

This helps customers understand the difference between adding new counted data and processing records that have already been recorded by the service.

### Entity Points Consumption Order  <a href="#entity-points-consumption-order" id="entity-points-consumption-order"></a>

Entity Points consumption follows the counted core data sequence:

> Product -> Customer -> Order -> Blog Posts

This sequence is separate from the fixed entity migration sequence used during execution.

The migration process handles entity types in this order:

> Taxes -> Manufacturers -> Categories -> Products -> Customers -> Orders -> Reviews -> Coupons -> CMS Pages -> Blog Posts

The execution sequence describes how the store data is processed. The Entity Points sequence describes how counted capacity is consumed for the four core data types.

### How Entity Points Are Consumed  <a href="#how-entity-points-are-consumed" id="how-entity-points-are-consumed"></a>

Entity Points are consumed when counted records are successfully migrated for the first time.

In practical terms:

* newly migrated Product records consume Product points
* newly migrated Customer records consume Customer points
* newly migrated Order records consume Order points
* newly migrated Blog records consume Blog points

Records that have already been successfully migrated and recognized by the service can be migrated again without consuming additional Entity Points for those same records.

Newly created records still consume Entity Points when they are migrated successfully for the first time, including through Recent Data Migration or another later migration run.

### Entity Points and Later Migration Actions <a href="#entity-points-and-later-migration-actions" id="entity-points-and-later-migration-actions"></a>

After a customer has performed a migration with the purchased service license, later migration actions may involve existing records, newly added records, or a new migration result for the same migration path.

Entity Points should be interpreted by record status:

| Record situation                                                                 | Entity Points effect                                                                        |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| A counted record is migrated successfully for the first time                     | Entity Points are consumed based on the data type coefficient.                              |
| A counted record has already been recorded through the migration service         | Entity Points are not consumed again for that same record.                                  |
| New counted records are added to the source store and migrated later             | Entity Points are consumed when those records are migrated successfully for the first time. |
| A new migration is performed for records already recorded by the service license | Those already recorded records do not consume Entity Points again.                          |

The useful planning point is simple: Entity Points are tied to counted records and their recorded migration status, not only to the number of times a customer runs migration activity.

### How Actual Data Volume Affects Consumption  <a href="#how-actual-data-volume-affects-consumption" id="how-actual-data-volume-affects-consumption"></a>

Actual consumption depends on the counted source-store records that are migrated, not only on the estimate entered during purchase.

If the actual source-store data volume is higher than expected, counted data types can consume more Entity Points than planned. If the selected Entity Points Plan still has enough available capacity, migration can continue within that plan.

For example:

* the customer estimates 1,000 Entity Points;
* the selected plan supports up to 2,000 Entity Points;
* the actual counted migration consumption is 1,400 Entity Points;
* no filtering is configured.

In this case, the migration can use 1,400 Entity Points because the consumption remains within plan capacity. The remaining 600 Entity Points stay available for eligible future use under the service license.

The issue appears when actual consumption exceeds the available plan capacity. If that happens, the migration pauses until the customer upgrades the Entity Points Plan.

### What Happens When Entity Points Run Out <a href="#what-happens-when-entity-points-run-out" id="what-happens-when-entity-points-run-out"></a>

If available Entity Points are consumed before all counted records are migrated, the migration pauses.

The customer can continue by upgrading the Entity Points Plan. When upgrading, the customer pays the price difference between the current plan and the higher plan, not the full price of the new plan.

The added Entity Points are distributed to the corresponding data types based on what the customer enters in the plan-upgrade purchase interface.

Continuing through the purchased service is safer than manually importing remaining related data outside the migration process. Manual import can weaken record relationships or database integrity, especially when products, customers, orders, and supporting structures need to remain connected.

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

#### What are Entity Points? <a href="#what-are-entity-points" id="what-are-entity-points"></a>

Entity Points are Next-Cart’s weighted capacity model for counted migration data. They help estimate how much capacity a project needs for Product, Customer, Order, and Blog Posts data.

#### Which data types count toward Entity Points? <a href="#which-data-types-count-toward-entity-points-1" id="which-data-types-count-toward-entity-points-1"></a>

Entity Points are calculated from Product, Customer, Order, and Blog Posts.

#### How are Entity Points calculated? <a href="#how-are-entity-points-calculated" id="how-are-entity-points-calculated"></a>

Entity Points are calculated using coefficients: Product x 1.0, Customer x 0.5, Order x 0.8, and Blog Posts x 0.6.

#### Are entered entity counts used as migration filters? <a href="#are-entered-entity-counts-used-as-migration-filters" id="are-entered-entity-counts-used-as-migration-filters"></a>

No. Entered counts are used for pricing and plan selection. They do not automatically limit which records are migrated.

#### What happens if actual counted data is higher than my estimate? <a href="#what-happens-if-actual-counted-data-is-higher-than-my-estimate" id="what-happens-if-actual-counted-data-is-higher-than-my-estimate"></a>

If the selected Entity Points Plan still has enough capacity, migration can continue and consume the available points. If available capacity runs out, migration pauses until the plan is upgraded.

#### Can unused Entity Points be used later? <a href="#can-unused-entity-points-be-used-later" id="can-unused-entity-points-be-used-later"></a>

Yes. Unused Entity Points within the purchased plan can support eligible future migration activity under the service license.

#### How can I migrate only selected records? <a href="#how-can-i-migrate-only-selected-records" id="how-can-i-migrate-only-selected-records"></a>

Selective migration should be planned through the Data Filter Add-on. If the filtering need exceeds available settings and supported behavior, it should be reviewed as a Custom Service requirement.

#### What happens when Entity Points run out? <a href="#what-happens-when-entity-points-run-out-1" id="what-happens-when-entity-points-run-out-1"></a>

The migration pauses. The customer can upgrade the Entity Points Plan and pay only the price difference between the current plan and the higher plan.

#### Does migrating already recorded entities again consume more Entity Points? <a href="#does-migrating-already-recorded-entities-again-consume-more-entity-points" id="does-migrating-already-recorded-entities-again-consume-more-entity-points"></a>

No. Counted records already recorded through the service license do not consume additional Entity Points when migrated again.

#### Do new records consume Entity Points when migrated later? <a href="#do-new-records-consume-entity-points-when-migrated-later" id="do-new-records-consume-entity-points-when-migrated-later"></a>

Yes. New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated successfully for the first time.
