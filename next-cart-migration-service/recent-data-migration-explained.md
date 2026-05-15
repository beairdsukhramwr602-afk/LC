# Recent Data Migration Explained

Recent Data Migration is a migration feature that helps active stores keep the Target Platform closer to the latest Source Platform state before launch. It is used after earlier migration activity when the Source Platform continues receiving new records, such as new orders, customers, products, or blog content.

Its role is focused: reduce the freshness gap before go-live. A freshness sync supports launch preparation, but the customer still needs to review the synchronized data and confirm that the migrated store is ready for launch.

#### **What Recent Data Migration Is**

Recent Data Migration syncs newly created source-store data into the Target Platform after previous migration activity has already taken place.

This matters because many businesses keep the Source Platform active while preparing the Target Platform. During that period, customers may place new orders, new accounts may be created, products may be added, and content may change.

Without a freshness step, the Target Platform can become outdated before launch.

Recent Data Migration helps reduce that gap by moving eligible new data into the Target Platform closer to go-live.

#### **Why Recent Data Migration Matters**

A migration timeline can last long enough for the source store to keep changing.

For example:

* new customers register
* new orders are placed
* existing products are updated
* new products are added
* new Blog Posts or CMS Pages are published
* campaign-related content changes before launch

If those changes are not synchronized, the Target Platform may no longer reflect the source store’s most current business state. This can create launch-day confusion, missing order history, incomplete customer data, or content gaps.

Recent Data Migration helps the customer launch with a fresher migrated store instead of relying only on the earlier Full Migration result.

#### **Recent Data Migration and the Migration Timeline**

Recent Data Migration usually belongs near the end of the migration timeline.

A practical sequence is:

1. run Demo Migration to review early direction
2. configure and run Full Migration
3. validate the migrated result
4. continue preparing the Target Platform
5. run Recent Data Migration closer to launch if the Source Platform stayed active
6. validate the latest synchronized data before go-live

The exact timing depends on how active the Source Platform is and how much new data is likely to appear before launch.

Recent Data Migration should be planned as part of the launch sequence, not treated as a last-minute fix.

#### **What Recent Data Migration Syncs**

Recent Data Migration focuses on newly created source-store records that were not included in earlier migration activity.

The most common freshness-sensitive data includes:

* new orders
* new customers
* new products
* new Blog Posts

Depending on the selected scope and platform support, other related or supporting data may also matter for the final migrated-store state.

The key idea is that Recent Data Migration is about new data created after earlier migration activity, not importing the entire store from the beginning again.

#### **Recent Data Migration and Entity Points**

Recent Data Migration uses Entity Points when newly created, counted records are migrated successfully for the first time.

The counted Entity Points data types are:

* Product
* Customer
* Order
* Blog

If the purchased Entity Points Plan still has unused capacity, new counted records can consume that remaining balance. If the remaining capacity is not enough, the customer can upgrade the Entity Points Plan.

For example, if the customer’s plan still has unused Entity Points after Full Migration, those points can support new orders, customers, products, or blog content migrated later through Recent Data Migration.

This is why active stores should consider likely new-data growth before launch when estimating Entity Points capacity.

#### **Recent Data Migration and Re-Migration**

Recent Data Migration should not be confused with Re-Migration.

Recent Data Migration focuses on newly created records that appeared in the Source Platform after earlier migration activity.

Re-Migration processes records that have already been migrated and recognized by the service, or applies updated migration settings to records the customer wants to process again. When the same records have already been successfully migrated, Re-Migration does not consume additional Entity Points for those same records.

New records are different. They consume Entity Points when they are migrated successfully for the first time.

This distinction helps customers understand why repeated processing of existing migrated records may not use new capacity, while newly created source-store records can consume available Entity Points.

#### **Recent Data Migration and All Scanned Records**

The migration process includes all scanned eligible records by default unless filtering is configured.

For Recent Data Migration, this means the customer should be clear about which new data should be included before running the sync. If only selected new records should move, that scope should be planned with the Data Filter Add-on. If the filtering requirement exceeds the available settings and supported behavior of the Standard Add-on, it becomes a Custom Service requirement.

Recent Data Migration is safest when the customer understands whether the goal is to synchronize all newly created eligible data or only a controlled subset.

#### **Recent Data Migration and Add-ons**

Add-ons can affect Recent Data Migration when the newly synchronized data needs the same focused handling as earlier migrated data.

Examples include:

* using the Data Filter Add-on when only selected new data under a specific rule or condition should be synchronized
* using Advanced Data Mapping when new records need the same mapped structure as earlier migrated records
* using Advanced Data Configure when new records need planned data adjustments before reaching the Target Platform

Consistency matters. If the earlier migration used Add-ons to shape the target result, Recent Data Migration should preserve the same expectations for newly synchronized data.

If new data requires handling beyond Standard Add-on capability, the requirement should be reviewed through Custom Service.

#### **Recent Data Migration and Custom Service**

Recent Data Migration can be more sensitive when the broader project includes Custom Service requirements.

This may happen when the migration involves:

* Custom Platform as Source Platform or Target Platform
* third-party app, plugin, module, or extension data
* custom fields
* outside-system identifiers
* Tailored Add-ons
* Custom Add-ons
* custom migration logic adjustment
* bespoke data transformation rules

In those cases, the freshness sync should not be treated as a simple new-record transfer. Newly created data may need to follow the same custom logic that made the earlier migration result acceptable.

The customer should confirm whether the new data depends on any custom handling before launch.

#### **What Recent Data Migration Does Not Do**

Recent Data Migration has a specific purpose. It helps synchronize newly created data before launch.

It does not:

* replace Demo Migration
* replace Full Migration
* prove the whole migrated store is launch-ready
* fix unresolved configuration issues
* correct earlier validation problems by itself
* remove the need for Add-ons when selective handling is required
* remove the need for Custom Service when customization or modification work is required

A freshness sync is useful when the broader migration result is already moving in the right direction and the customer needs the Target Platform to reflect newer Source Platform activity.

#### **What to Validate After Recent Data Migration**

After Recent Data Migration, the customer should validate the newly synchronized data and the parts of the migrated store affected by it.

Useful checks include:

* new orders appear with the expected customer and product relationships
* new customers appear with usable contact and account information
* new products appear in the expected category, collection, or browse context
* new Blog Posts or CMS Pages appear correctly where relevant
* mapped values remain consistent with earlier migrated records
* Add-on-influenced records follow the same expected rules
* custom-handled records preserve the agreed result
* priority storefront, admin, and customer-service workflows still make sense

Validation should focus on the new data most likely to affect launch confidence.

#### **Planning Recent Data Migration Before Launch**

A strong launch plan should answer several questions before Recent Data Migration is run:

* Will the Source Platform remain active after Full Migration?
* Which new data types are most likely to appear before launch?
* How much Entity Points capacity may be needed for new counted records?
* Should all newly created eligible data be synchronized, or only selected records?
* Do Add-ons need to apply to the new records?
* Does any custom handling need to apply to the new records?
* Who will validate the synchronized result before go-live?
* How close to launch should the final sync happen?

These questions help the customer avoid treating Recent Data Migration as a simple button press. The feature is most useful when it is aligned with the launch plan.

#### **Common Recent Data Migration Misunderstandings**

**“Recent Data Migration replaces Full Migration.”**

No. Recent Data Migration syncs newly created data after earlier migration activity. Full Migration is still the main migration run.

**“Recent Data Migration proves launch readiness.”**

No. Recent Data Migration improves freshness. The customer still needs to review whether the synchronized data and affected workflows are ready for launch.

**“Recent Data Migration never consumes Entity Points.”**

Newly created counted records consume Entity Points when migrated successfully for the first time.

**“Any new data can be included without planning.”**

New data should still be reviewed for scope, Add-ons, custom handling, and available Entity Points capacity.

**“Recent Data Migration fixes earlier configuration problems.”**

No. Configuration or validation issues should be addressed before the final freshness sync.

#### **Conclusion**

Recent Data Migration helps active stores reduce the gap between the earlier migration result and the final Source Platform state before launch. It is especially useful when the Source Platform continues creating new orders, customers, products, or content while the migrated store is being prepared.

Its value is freshness, not final approval. Newly synchronized data still needs to be reviewed, especially when Entity Points capacity, Add-ons, Custom Service requirements, or launch timing affect the result.

Plan Recent Data Migration as part of the launch sequence. If your Source Platform remains active, review likely new-data growth, remaining Entity Points capacity, Add-on requirements, and any custom handling before the final sync. Live Chat can help clarify the safest timing and scope before go-live.

#### **FAQs**

**What is Recent Data Migration?**

Recent Data Migration is the migration feature used to sync newly created source-store data into the Target Platform after earlier migration activity.

**When should I use Recent Data Migration?**

Use it when the Source Platform remains active after Full Migration and continues creating new records before launch.

**Does Recent Data Migration replace Full Migration?**

No. Full Migration is the main migration run. Recent Data Migration helps synchronize newly created data after earlier migration activity.

**Does Recent Data Migration consume Entity Points?**

Yes. Newly created counted records consume Entity Points when they are migrated successfully for the first time.

**Can unused Entity Points support Recent Data Migration?**

Yes. Unused Entity Points within the purchased plan can support newly created counted records migrated through Recent Data Migration.

**What happens if there are not enough Entity Points for Recent Data Migration?**

The customer can upgrade the Entity Points Plan. The upgrade adds capacity and the customer pays only the price difference between the current plan and the higher plan.

**Can I use Add-ons with Recent Data Migration?**

Yes. Add-ons may apply if the newly synchronized data needs filtering, advanced mapping, or data configuration.

**Does Recent Data Migration replace validation?**

No. Recent Data Migration improves data freshness. The customer still needs to validate the synchronized data and confirm launch readiness.
