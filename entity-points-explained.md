# Entity Points Explained

Entity Points are Next-Cart’s way of measuring core migration scope and migration capacity. They help customers estimate how much data the migration plan needs to support before the migration begins.

Entity Points do not measure every kind of migration difficulty. A project can have a clear Entity Points estimate and still require careful review because of platform differences, product complexity, custom fields, third-party data, Add-ons, or Custom Service requirements. Entity Points answer the capacity question. They do not replace compatibility review, service choice, or validation.

### What Entity Points Mean <a href="#what-entity-points-mean" id="what-entity-points-mean"></a>

Entity Points translate selected core data types into a weighted scope value.

Instead of treating every record type as equal, the Entity Points model applies different coefficients to the main counted data types. This creates a more practical estimate of migration capacity than a single raw record count.

Entity Points help customers understand:

* how much core migration scope is being estimated
* which Entity Points Plan is likely to fit the project
* how capacity may be consumed during migration
* why actual source-store data volume matters
* why entered quantities are not automatic filters
* how unused plan capacity can support later eligible migration activity

The system uses Entity Points for migration-capacity planning. The customer should still review the store’s real complexity separately.

### Which Data Types Count Toward Entity Points <a href="#which-data-types-count-toward-entity-points" id="which-data-types-count-toward-entity-points"></a>

Entity Points are calculated from four counted data types:

* Product
* Customer
* Order
* Blog

These are the data types customers enter when estimating migration scope.

Other entities may still be migrated depending on platform support and selected scope. These can include taxes, manufacturers, categories, reviews, coupons, CMS Pages, and supporting structures. They matter for the migration process, but they are not counted in the same way for Entity Points calculation.

This distinction is important because the migration process includes more entity types than the Entity Points model counts.

### Entity Points Coefficients <a href="#entity-points-coefficients" id="entity-points-coefficients"></a>

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

This weighted calculation allows different data types to contribute differently to total plan capacity.

### Example Entity Points Calculation <a href="#example-entity-points-calculation" id="example-entity-points-calculation"></a>

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

If the closest higher available Entity Points Plan provides 500 Entity Points, that plan can be selected for the estimated scope.

This estimate should be as realistic as possible. If the source store contains more records than expected, actual consumption can be higher than the customer planned.

### Entity Points and the Pricing Estimate <a href="#entity-points-and-the-pricing-estimate" id="entity-points-and-the-pricing-estimate"></a>

Entity Points are used to estimate plan capacity during purchase.

Customers enter estimated counts for Product, Customer, Order, and Blog. The system calculates the total Entity Points and recommends the closest higher Entity Points Plan.

The entered numbers support pricing and plan selection. They do not automatically restrict what the migration tool scans or migrates.

This is one of the most important points to understand before execution. A customer who enters 200 Products is estimating plan capacity for pricing. That entry does not automatically tell the migration tool to migrate only 200 Product records.

### Entity Points Plan Capacity <a href="#entity-points-plan-capacity" id="entity-points-plan-capacity"></a>

An Entity Points Plan can support more capacity than the customer’s initial input.

For example, if the customer purchases a plan that supports up to 2,000 Entity Points and the actual scan consumes 1,400 Entity Points, the migration can use those 1,400 points while leaving 600 Entity Points available within that plan.

Unused Entity Points can support later eligible migration activity, such as Recent Data Migration or Re-migration activity involving new records the customer wants to include.

This means the practical capacity limit is the Entity Points Plan, not only the customer’s original estimate.

### Entered Quantities Are Not Migration Filters <a href="#entered-quantities-are-not-migration-filters" id="entered-quantities-are-not-migration-filters"></a>

Entity count inputs should not be confused with filtering rules.

By default, all scanned records are migrated. If the source store contains more eligible records than the customer estimated, the migration tool can continue migrating scanned records as long as the Entity Points Plan still has enough available capacity.

For example, a customer may enter 200 Products during purchase. If the source store contains 400 Product records and no filtering rule is configured, the migration process treats the scanned Product records as eligible for migration. If the selected plan still has enough Entity Points capacity, those records can be migrated and the available balance is consumed accordingly.

If the customer wants to migrate only selected records, that requirement should be planned through the Data Filter Add-on. If the filtering need goes beyond the default capability of the Add-on, it becomes a Custom Service requirement.

### Entity Points Consumption Order <a href="#entity-points-consumption-order" id="entity-points-consumption-order"></a>

Entity Points consumption follows the counted core data sequence: **Product** → **Customer** → **Order** → **Blog**.

This sequence is separate from the full entity migration sequence used during execution.

The full fixed entity migration sequence is:

> Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

The migration process follows the full entity sequence. Entity Points consumption follows Product, Customer, Order, and Blog because those are the counted data types in the Entity Points model.

This distinction helps customers avoid assuming that every migrated entity type consumes Entity Points directly.

### How Entity Points Are Consumed <a href="#how-entity-points-are-consumed" id="how-entity-points-are-consumed"></a>

Entity Points are consumed when counted records are successfully migrated for the first time.

In practical terms:

* newly migrated Product records consume Product points
* newly migrated Customer records consume Customer points
* newly migrated Order records consume Order points
* newly migrated Blog records consume Blog points

Records that have already been successfully migrated and recognized by the system can be re-migrated without consuming additional Entity Points for the same records.

Newly created records still consume Entity Points when they are migrated successfully for the first time, including through Recent Data Migration or Re-migration

### How Actual Data Volume Affects Consumption <a href="#how-actual-data-volume-affects-consumption" id="how-actual-data-volume-affects-consumption"></a>

Actual migration consumption depends on the data the tool scans and migrates, not only on the estimate entered during purchase.

If the actual source-store data volume is higher than estimated, counted data types can consume more capacity than expected. If the selected Entity Points Plan still covers the actual total consumption, the migration can continue.

For example:

* the customer estimates 1,000 Entity Points
* the selected plan supports up to 2,000 Entity Points
* the real scan consumes 1,400 Entity Points
* no filtering rule is configured

In this case, the migration can use the 1,400 Entity Points because it remains within the plan capacity. The remaining 600 Entity Points stay available for later eligible use.

The issue appears when actual consumption exceeds the available plan capacity. If that happens, the migration pauses until the customer upgrades the Entity Points Plan.

### What Happens When Entity Points Run Out <a href="#what-happens-when-entity-points-run-out" id="what-happens-when-entity-points-run-out"></a>

If available Entity Points are consumed before all counted records are migrated, the migration pauses.

The customer can continue by upgrading the Entity Points Plan. When upgrading, the customer pays only the price difference between the current plan and the higher plan, not the full price of the new plan.

The added Entity Points are distributed to the corresponding data types based on what the customer enters in the plan-upgrade purchase interface.

Continuing through the migration tool is the safer and recommended path because it preserves the migration system’s record tracking and relationship handling. Manual import of remaining related data is discouraged because it can break connections between records or weaken database integrity. For example, manually imported records may not connect cleanly to previously migrated products, customers, orders, or supporting structures.

### Entity Points and Re-Migration <a href="#entity-points-and-re-runs" id="entity-points-and-re-runs"></a>

Re-migration can be useful when the customer needs to process already migrated records again after adjustment, review, or correction.

When the same records have already been successfully migrated and recognized by the migration system, processing those same records again does not consume additional Entity Points.

This helps customers correct or re-process existing migrated records without treating the same records as new capacity every time.

New records are different. If the Source Platform creates new Product, Customer, Order, or Blog records after an earlier migration run, those records consume Entity Points when they are migrated for the first time.

### Entity Points and Recent Data Migration <a href="#entity-points-and-recent-data-migration" id="entity-points-and-recent-data-migration"></a>

Recent Data Migration uses Entity Points when it syncs newly created counted records.

If the Source Platform remains active after the Full Migration, it may continue creating new customers, orders, products, or blog content before launch. When those new counted records are migrated for the first time, they consume Entity Points.

Unused Entity Points within the purchased plan can support this later activity. If the plan still has remaining capacity, newly migrated counted records can consume that balance. If the balance is not enough, the customer can upgrade the Entity Points Plan.

Recent Data Migration helps reduce the freshness gap before go-live, but it still depends on available Entity Points for newly migrated counted records.

#### Entity Points Plan Upgrade and License Renewal Are Different  <a href="#entity-points-plan-upgrade-and-license-renewal-are-different" id="entity-points-plan-upgrade-and-license-renewal-are-different"></a>

Upgrading the Entity Points Plan increases migration capacity. It does not renew the service license.

License renewal is a separate decision. When renewing, the customer pays based on the minimum Entity Points Plan in the account record and the final service status of the license, excluding custom work that has already been charged.

This means a customer may renew using the old preferences or renew with upgraded preferences, such as renewing an expired Standard Service license with a higher Entity Points Plan or a different final service status.

### What Entity Points Do Not Decide <a href="#what-entity-points-do-not-decide" id="what-entity-points-do-not-decide"></a>

Entity Points do not decide the entire migration path.

They do not determine:

* whether the source and target platforms represent data in the same way
* whether product options or variants preserve the expected buying behavior
* whether important data requires Add-ons
* whether custom fields or third-party data require Custom Service
* whether Custom Platform is involved
* whether target-platform limitations require tailored handling
* whether the migrated store is ready for launch

Entity Points measure capacity. Migration quality still depends on planning, configuration, validation, platform fit, and service selection.

### Common Entity Points Misunderstandings <a href="#common-entity-points-misunderstandings" id="common-entity-points-misunderstandings"></a>

#### “The number I entered is the number that will migrate.” <a href="#the-number-i-entered-is-the-number-that-will-migrate" id="the-number-i-entered-is-the-number-that-will-migrate"></a>

The number entered is for pricing and plan estimation. It is not an automatic migration filter.

#### “If the real scan is higher than my estimate, migration must stop immediately.” <a href="#if-the-real-scan-is-higher-than-my-estimate-migration-must-stop-immediately" id="if-the-real-scan-is-higher-than-my-estimate-migration-must-stop-immediately"></a>

Not necessarily. If the selected Entity Points Plan has enough capacity to cover the actual scanned and counted data, the migration can continue.

#### “Unused Entity Points disappear after the first migration run.” <a href="#unused-entity-points-disappear-after-the-first-migration-run" id="unused-entity-points-disappear-after-the-first-migration-run"></a>

Unused Entity Points within the purchased plan can support later eligible migration activity, such as Recent Data Migration or new records included in a later run.

#### “Only Product, Customer, Order, and Blog data move.” <a href="#only-product-customer-order-and-blog-data-move" id="only-product-customer-order-and-blog-data-move"></a>

No. Other entities may also move depending on platform support and selected scope. Product, Customer, Order, and Blog are the counted data types used for Entity Points.

#### “Every migrated entity consumes Entity Points.” <a href="#every-migrated-entity-consumes-entity-points" id="every-migrated-entity-consumes-entity-points"></a>

No. Entity Points consumption is tied to the counted core data types in the Entity Points model.

#### “A re-run always consumes more points.” <a href="#a-re-run-always-consumes-more-points" id="a-re-run-always-consumes-more-points"></a>

No. Records already successfully migrated and recognized by the system can be re-migrated without consuming additional Entity Points for the same records.

#### “Upgrading Entity Points renews my service license.” <a href="#upgrading-entity-points-renews-my-service-license" id="upgrading-entity-points-renews-my-service-license"></a>

No. Entity Points Plan upgrade increases plan capacity. It does not renew the service license.

#### “Entity Points prove migration complexity.” <a href="#entity-points-prove-migration-complexity" id="entity-points-prove-migration-complexity"></a>

No. Entity Points measure scope and capacity. Complexity can still come from platform differences, Add-ons, Custom Service requirements, Custom Platform, third-party data, or validation needs.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Entity Points help customers estimate migration capacity by applying a weighted model to Product, Customer, Order, and Blog data. They are useful because they turn core migration scope into a plan capacity number that can support pricing, execution, remaining-capacity use, and upgrade decisions.

The most important distinction is that Entity Points inputs are not migration filters. All scanned records are migrated by default, and actual consumption depends on the counted records that are successfully migrated. If actual scanned data remains within the purchased Entity Points Plan, the migration can continue even when the real count is higher than the original estimate.

Estimate your Product, Customer, Order, and Blog counts carefully, and consider likely source-store growth before launch. If your store contains more data than expected, you still have unused plan capacity, or you only want selected records to move, Live Chat can help clarify whether you should use remaining Entity Points, upgrade the Entity Points Plan, use the Data Filter Add-on, or review a custom filtering requirement before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What are Entity Points?**&#x20;

Entity Points are Next-Cart’s weighted scope and capacity model for core migration data. They help estimate how much migration capacity a project needs.

**Which data types count toward Entity Points?**&#x20;

Entity Points are calculated from Product, Customer, Order, and Blog.

**How are Entity Points calculated?**&#x20;

Entity Points are calculated using coefficients: Product × 1.0, Customer × 0.5, Order × 0.8, and Blog × 0.6.

**Are the entered entity counts used as migration filters?**

No. Entered counts are used for pricing and plan selection. They do not automatically limit which records are migrated.

**What happens if the actual scanned data is higher than my estimate?**&#x20;

If the selected Entity Points Plan still has enough capacity, the migration can continue and consume the available points. If the plan capacity runs out, the migration pauses until the plan is upgraded.

**Can unused Entity Points be used later?**&#x20;

Yes. Unused Entity Points within the purchased plan can support later eligible activity, such as Recent Data Migration or migrating newly included records.

**How can I migrate only selected records?**&#x20;

Selective migration should be planned through the Data Filter Add-on. If the filtering needs exceed the default Add-on capability, it becomes a Custom Service requirement.

**What happens when Entity Points run out?**&#x20;

The migration pauses. The customer can upgrade the Entity Points Plan and pay only the price difference between the current plan and the higher plan.

**Does re-migration consume more Entity Points?**&#x20;

Not for the same records if they have already been successfully migrated and recognized by the system. Newly created records consume Entity Points when migrated for the first time.

**Does Recent Data Migration consume Entity Points?**&#x20;

Yes. Recent Data Migration consumes Entity Points for newly created records when they are migrated successfully for the first time.

**Does upgrading the Entity Points Plan renew the service license?**&#x20;

No. Upgrading the Entity Points Plan increases plan capacity. It does not renew the service license.
