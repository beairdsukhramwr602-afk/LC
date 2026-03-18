# Entity Points Explained: How Migration Scope Is Measured

Migration pricing often feels confusing because raw record counts do not tell the whole story.

Two stores can each have the same number of products and still require different migration capacity once customer volume, order history, and blog content are taken into account. That is why Next-Cart uses Entity Points: a weighted model for measuring migration scope across the core data types that drive most migration workload.

Entity Points do not measure every type of data equally. They are designed to turn the core migration scope into a more realistic planning unit, so the plan size can be estimated more consistently.

### What Entity Points are

Entity Points are Next-Cart’s standardized method for measuring migration scope across four core data types:

* Products
* Customers
* Orders
* Blog Posts

Instead of treating every record as equal, Entity Points apply different weights to these core entities. This reflects the fact that not every migrated record creates the same workload or planning impact.

Supporting data may still be included in the migration scope depending on platform support, but it does not increase the Entity Points calculation.

### How Entity Points are calculated

Each core entity type has a coefficient:

* Products: **1.0**
* Customers: **0.5**
* Orders: **0.8**
* Blog Posts: **0.6**

The formula is:

{% code overflow="wrap" fullWidth="false" %}
```
Entity Points = (Products × 1.0) + (Customers × 0.5) + (Orders × 0.8) + (Blog Posts × 0.6)
```
{% endcode %}

This creates a weighted total that helps estimate the migration capacity the project is likely to need.

### Why Entity Points are weighted

Entity Points are weighted because the migration scope is not driven by one record type alone.

A store with modest product volume but a large order history may require more migration capacity than another store with a larger catalog and lighter transaction history. In the same way, a store with a customer-heavy or content-heavy scope may not fit the same plan assumptions as one driven mostly by products. Weighted scope makes these differences easier to plan for.

This is also why Entity Points are more useful than a simple “highest count wins” model. They measure core migration volume across the combined effect of multiple entity types rather than treating one count as the whole pricing story.

#### A simple example

Assume a store has:

* 500 Products
* 100 Customers
* 600 Orders
* 100 Blog Posts

The calculation would be:

* Products: 500 × 1.0 = 500
* Customers: 100 × 0.5 = 50
* Orders: 600 × 0.8 = 480
* Blog Posts: 100 × 0.6 = 60

**Total = 1,090 Entity Points**

This example shows why a store’s migration plan should be based on weighted scope, not only on a single headline count.

### Next-Cart Migration Service Package

A Next-Cart Migration Plan will include

* The migration service model (Standard Migration, Managed Migration, or Custom Migration)
* The Entity Points Plan
* Custom Jobs, where needed and purchased for non-standard requirements

A Migration Plan is valid for one year from the date of purchase. During that license period, the plan authorizes migration activity as long as total Entity Points consumption stays within the purchased Entity Points Plan.

The Migration Plan applies to all migration types:

* Full Migration
* Recent Data Migration
* Re-migration

A Migration Plan only applies to a specific migration direction and it does not transfer to the reverse direction or to a different target platform:

**Source Cart → Target Cart**

For example, a plan purchased for **Shopify → WooCommerce** applies only to that direction. It cannot be reused for **WooCommerce → Shopify** or for a different target platform.

### What Entity Points do and do not measure

Entity Points measure the core migration scope. They do not define relationship logic, migration order, or validation quality by themselves.

They are useful for answering questions such as:

* how large the core migration scope is
* whether the current plan is likely to be sufficient
* how much new-data growth the project may need to accommodate
* whether the business may need a higher plan before go-live

They are not the same thing as:

* relationship-preserving sequence
* platform compatibility
* product-structure complexity
* extension-driven logic
* validation completeness

Those areas still affect migration success and may still require closer review even when the Entity Points estimate is accurate.

### How Entity Points are consumed

Entity Points are consumed only when new data is migrated successfully for the first time.

Data that has already been migrated successfully is recorded in the migration system with a unique identification code for each record and can be re-migrated multiple times without consuming additional Entity Points.

This means:

* first-time successful migration of new records consumes Entity Points
* re-migration of records that were already migrated successfully does not consume additional Entity Points
* newly created source-store data consumes Entity Points when it is migrated for the first time later on

This rule is important because it makes repeat review and correction work more predictable without charging again for records the system has already recognized as migrated successfully.

### Why successful re-migration does not consume more Entity Points

A migration project often needs more than one pass.

Businesses may re-run migration to:

* review corrected results
* validate updated structure
* confirm business behavior before go-live
* continue the project after earlier planning decisions change

When those re-runs involve records that have already been migrated successfully and recorded by the system, additional Entity Points are not consumed for those same records. This makes repeated validation more practical and helps keep scope planning stable across the project.

### What happens if the Entity Points Plan runs out

If the Entity Points Plan is exhausted before all data is migrated, the remaining data will not move until the plan is upgraded.

The safer continuation path is to upgrade the Entity Points Plan and continue through the migration tool where it paused. Manually importing the remaining related data outside the tool can weaken or break relationship integrity, especially where later records depend on earlier records already being present and reconstructed correctly.

This is one of the most important distinctions to keep clear:

* **Entity Points** measure scope
* the migration tool’s defined process preserves relationship integrity

Those are connected decisions, but they are not the same decision.

### How the migration tool processes core data when scope is limited

For Entity Points consumption, core data is processed in this order:

**Product → Customer → Order → Blog**

Within each data type, records are migrated from oldest to newest.

This matters because when the plan runs out, the tool consumes the remaining balance on the next entity type until it can no longer continue, then stops.

Using the earlier example of a 1,000 Entity Points plan against a 1,090 Entity Points requirement:

* Products migrate first: 500 points
* Customers migrate next: 50 points
* 450 points remain
* Orders require 480 points in total, so only the portion that fits can migrate before the plan is exhausted
* The migration then stops until the plan is upgraded

This consumption order explains why under-scoping can interrupt the project even when the total dataset looks only slightly above the purchased plan.

### Recent Data Migration and new data growth

If the source store continues generating new data after an earlier migration run, those newly created records consume Entity Points when they are migrated for the first time.

For example, after upgrading and completing the migration, assume the customer has consumed 1,090 Entity Points and has 910 remaining on a 2,000 plan. If the store later adds 120 new Products and 30 new Customers, migrating that new data consumes:

(120 × 1.0) + (30 × 0.5) = 120 + 15 = 135 Entity Points

**New Entity Points consumed**: 135\
**Remaining Entity Points**: 775

That is why Entity Points planning should take likely data growth into account, especially if the project timeline includes a gap between early migration activity and go-live. Recent Data Migration is the appropriate feature when the goal is to sync newly created source-store data into the target store after earlier migration activity.

### Plan upgrades and renewal

When a project needs more capacity, an Entity Points Plan can be upgraded. Upgrades are designed to cover the remaining scope so migration can continue without requiring the business to repurchase capacity it already secured. In practice, this is handled as the price difference between plans rather than starting over from scratch.

A Migration Plan is valid for one year from the purchase date. If the plan expires, renewal is needed to continue access to the migration service.

Renewal includes:

* the migration service model
* the Entity Points Plan

Custom Jobs are excluded from renewal of the migration package if you previously purchased it.

#### Entity Points Plan upgrades

When you need more capacity, upgrading your Entity Points Plan is straightforward and cost-effective.

* **Cost Efficiency**

You only pay the difference between your current plan and the new, higher-capacity plan you wish to purchase. This ensures you are never double-charged for capacity you've already secured.

* **Immediate Capacity**

The new plan immediately covers any capacity deficit, ensuring you can continue migrating your remaining data without interruption. This is particularly useful when the migration scope increases unexpectedly, allowing for a seamless continuation of your project.

#### Scalable Pricing for Extremely Large Migrations

Our pricing model is structured to scale predictably, even for the largest and most complex migration projects.

For very large migration runs that exceed the standard Entity Points tiers, the following supplementary pricing logic applies:

If a migration plan surpasses **1,024,000 Entity Points**, an additional fee of **$50** is charged for every extra **100,000 Entity Points**.

This ensures that high-volume enterprise migrations are supported with a clear, predefined, and granular pricing structure.

### A common misunderstanding to avoid

One of the easiest mistakes is treating Entity Points as if they solve the whole migration-planning question.

They do not.

Entity Points tell you how much core migration scope the plan needs to cover. They do not tell you:

* whether platform differences will change data meaning
* whether third-party logic increases risk
* whether filtered scope needs Custom Job handling
* whether the standard process is enough for a structurally complex store

Where platform limitations, third-party logic, integrations, custom fields, or data-model differences make the standard process less likely to preserve the expected result safely, Custom Migration or a Custom Job may be the better path.

### Conclusion

Entity Points give Next-Cart a standardized way to measure migration scope across the four core data types that drive most migration workload: Products, Customers, Orders, and Blog Posts. That makes migration planning more realistic than relying on raw counts alone.

They are most useful when they are understood for what they are: a weighted scope model. They help estimate plan size, predict whether capacity will be sufficient, and make repeated migration work more predictable because already migrated records do not consume additional Entity Points again.

Review core scope early using weighted counts rather than rough estimates. If your store is still growing, include likely new-data volume before go-live so Recent Data Migration does not become an afterthought. If the scope is difficult to estimate because filtered migration, third-party logic, or structural complexity changes what should be moved, Live Chat is a practical way to align Entity Points planning, service fit, and the safest migration path.

#### FAQs

<details>

<summary><strong>Do images, categories, or reviews increase Entity Points?</strong></summary>

No. Entity Points are calculated from Products, Customers, Orders, and Blog Posts only. Supporting data may still be included in migration scope depending on platform support, but it does not increase the Entity Points calculation.

</details>

<details>

<summary><strong>What happens if my Entity Points Plan runs out mid-migration?</strong></summary>

The migration continues only until the remaining capacity is exhausted, then stops. The safer next step is to upgrade the Entity Points Plan and continue through the tool rather than manually importing the remaining related data outside that process.

</details>

<details>

<summary><strong>Can I upgrade my Entity Points Plan after purchase?</strong></summary>

Yes. Plan upgrades are designed to cover remaining scope when needs exceed the current plan, and they are generally handled as the difference between the current plan and the higher plan.

</details>

<details>

<summary><strong>Is Next-Cart pricing a subscription?</strong></summary>

No. The migration purchase is a one-year license for the migration project, not a recurring monthly subscription. Renewal is needed only if the project needs continued access after the license period.

</details>

<details>

<summary><strong>Can I re-migrate data without consuming more Entity Points?</strong></summary>

Yes, if the records were already migrated successfully and recorded by the system. Re-migration of those already recorded records does not consume additional Entity Points.

</details>

