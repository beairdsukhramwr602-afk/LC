# Recent Data Migration Explained

Recent Data Migration helps active stores keep the Target Cart closer to the latest Source Cart state before launch. It is used after earlier migration activity when the source store continues receiving new records, such as new orders, customers, products, or blog content.

Its role is focused: reduce the freshness gap before go-live. It does not replace Demo Migration, Full Migration, validation, service choice, Add-ons, or Custom Service planning. A store can be freshly synchronized and still need careful review before launch.

### What Recent Data Migration Is <a href="#what-recent-data-migration-is" id="what-recent-data-migration-is"></a>

Recent Data Migration syncs newly created source-store data into the Target Cart after previous migration activity has already taken place.

This matters because many businesses keep the Source Cart active while preparing the Target Cart. During that period, customers may place new orders, new accounts may be created, products may be added, and content may change.

Without a freshness step, the Target Cart can become outdated before launch.

Recent Data Migration helps reduce that gap by moving eligible new data into the Target Cart closer to go-live.

### Why Recent Data Migration Matters <a href="#why-recent-data-migration-matters" id="why-recent-data-migration-matters"></a>

A migration timeline can last long enough for the source store to keep changing.

For example:

* new customers register
* new orders are placed
* existing products are updated
* new products are added
* new Blog Posts or CMS Pages are published
* campaign-related content changes before launch

If those changes are not synchronized, the Target Cart may no longer reflect the source store’s most current business state. This can create launch-day confusion, missing order history, incomplete customer data, or content gaps.

Recent Data Migration helps the customer launch with a fresher target store instead of relying only on the earlier Full Migration result.

### Recent Data Migration and the Migration Timeline <a href="#recent-data-migration-and-the-migration-timeline" id="recent-data-migration-and-the-migration-timeline"></a>

Recent Data Migration usually belongs near the end of the migration timeline.

A practical sequence is:

1. run Demo Migration to review early direction
2. configure and run Full Migration
3. validate the migrated result
4. continue preparing the Target Cart
5. run Recent Data Migration closer to launch if the Source Cart stayed active
6. validate the latest synchronized data before go-live

The exact timing depends on how active the source store is and how much new data is likely to appear before launch.

Recent Data Migration should be planned as part of the launch sequence, not treated as a last-minute fix.

### What Recent Data Migration Syncs <a href="#what-recent-data-migration-syncs" id="what-recent-data-migration-syncs"></a>

Recent Data Migration focuses on newly created source-store records that were not included in earlier migration activity.

The most common freshness-sensitive data includes:

* new orders
* new customers
* new products
* new Blog Posts

Depending on the selected scope and platform support, other related or supporting data may also matter for the final target-store state.

The key idea is that Recent Data Migration is about new data created after earlier migration activity, not re-importing the entire store from the beginning.

### Recent Data Migration and Entity Points <a href="#recent-data-migration-and-entity-points" id="recent-data-migration-and-entity-points"></a>

Recent Data Migration uses Entity Points when newly created, counted records are migrated successfully for the first time.

The counted Entity Points data types are:

* Product
* Customer
* Order
* Blog

If the purchased Entity Points Plan still has unused capacity, new counted records can consume that remaining balance. If the remaining capacity is not enough, the customer can upgrade the Entity Points Plan.

For example, if the customer’s plan still has unused Entity Points after Full Migration, those points can support new orders, customers, products, or blog content migrated later through Recent Data Migration.

This is why active stores should consider likely new-data growth before launch when estimating Entity Points capacity.

### Recent Data Migration and Re-Migration <a href="#recent-data-migration-and-re-migration" id="recent-data-migration-and-re-migration"></a>

Recent Data Migration should not be confused with re-migration.

Re-migration repeats migration activity for the entire data set that has already been migrated and recognized by the system, or rerun to include new data and migration settings, depending on the customer's intention. When the same records have already been successfully migrated, re-running those records does not consume additional Entity Points for the same records.

Recent Data Migration focuses on newly created records. Those records consume Entity Points when migrated successfully for the first time.

This distinction helps customers understand why some repeated activity may not use new capacity, while new data created after the earlier run does.

### Recent Data Migration and All Scanned Records <a href="#recent-data-migration-and-all-scanned-records" id="recent-data-migration-and-all-scanned-records"></a>

The migration tool migrates all scanned records by default unless filtering is configured.

For Recent Data Migration, this means the customer should be clear about which new data should be included before running the sync. If only selected new records should move, that scope should be planned with the Data Filter Add-on included. If the filtering requirement exceeds the default capability of the Add-on, it becomes a Custom Service requirement.

Recent Data Migration is safest when the customer understands whether the goal is to synchronize all newly created eligible data or only a controlled subset.

### Recent Data Migration and Add-ons <a href="#recent-data-migration-and-add-ons" id="recent-data-migration-and-add-ons"></a>

Add-ons can affect Recent Data Migration when the newly synchronized data needs the same focused handling as earlier migrated data.

Examples include:

* using the Data Filter Add-on when only selected new data under a specific rule/condition should be synchronized
* using Advanced Data Mapping when new records need the same mapped structure as earlier migrated records
* using Advanced Data Configure when new records need planned data adjustments before reaching the Target Cart

Consistency matters. If the earlier migration used Add-ons to shape the target result, Recent Data Migration should preserve the same expectations for newly synchronized data.

If new data requires handling beyond standard Add-on capability, the requirement should be reviewed through Custom Service.

### Recent Data Migration and Custom Service <a href="#recent-data-migration-and-custom-service" id="recent-data-migration-and-custom-service"></a>

Recent Data Migration can be more sensitive when the broader project includes Custom Service requirements.

This may happen when the migration involves:

* Custom Cart as Source Cart or Target Cart
* third-party app, plugin, module, or extension data
* custom fields
* outside-system identifiers
* tailored Add-ons
* custom Add-ons
* migration-tool modification
* bespoke data transformation rules

In those cases, the freshness sync should not be treated as a simple new-record transfer. Newly created data may need to follow the same custom logic that made the earlier migration result acceptable.

The customer should confirm whether the new data depends on any custom handling before launch.

### What Recent Data Migration Does Not Do <a href="#what-recent-data-migration-does-not-do" id="what-recent-data-migration-does-not-do"></a>

Recent Data Migration has a specific purpose. It helps synchronize newly created data before launch.

It does not:

* replace Demo Migration
* replace Full Migration
* prove the whole target store is launch-ready
* fix unresolved configuration issues
* correct earlier validation problems by itself
* remove the need for Add-ons when selective handling is required
* remove the need for Custom Service when customization or modification work is required

A freshness sync is useful only when the broader migration result is already moving in the right direction.

### What to Validate After Recent Data Migration <a href="#what-to-validate-after-recent-data-migration" id="what-to-validate-after-recent-data-migration"></a>

After Recent Data Migration, the customer should validate the newly synchronized data and the parts of the store affected by it.

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

### Planning Recent Data Migration Before Launch <a href="#planning-recent-data-migration-before-launch" id="planning-recent-data-migration-before-launch"></a>

A strong launch plan should answer several questions before Recent Data Migration is run:

* Will the Source Cart remain active after Full Migration?
* Which new data types are most likely to appear before launch?
* How much Entity Points capacity may be needed for new counted records?
* Should all newly created eligible data be synchronized, or only selected records?
* Do Add-ons need to apply to the new records?
* Does any custom handling need to apply to the new records?
* Who will validate the synchronized result before go-live?
* How close to launch should the final sync happen?

These questions help the customer avoid treating Recent Data Migration as a simple button press. The feature is most useful when it is aligned with the launch plan.

### Common Recent Data Migration Misunderstandings <a href="#common-recent-data-migration-misunderstandings" id="common-recent-data-migration-misunderstandings"></a>

#### “Recent Data Migration replaces Full Migration.” <a href="#recent-data-migration-replaces-full-migration" id="recent-data-migration-replaces-full-migration"></a>

No. Recent Data Migration syncs newly created data after earlier migration activity. Full Migration is still the main migration run.

#### “Recent Data Migration proves launch readiness.” <a href="#recent-data-migration-proves-launch-readiness" id="recent-data-migration-proves-launch-readiness"></a>

No. Recent Data Migration improves freshness. Validation proves whether the target store is ready for launch.

#### “Recent Data Migration never consumes Entity Points.” <a href="#recent-data-migration-never-consumes-entity-points" id="recent-data-migration-never-consumes-entity-points"></a>

Newly created counted records consume Entity Points when migrated successfully for the first time.

#### “Any new data can be included without planning.” <a href="#any-new-data-can-be-included-without-planning" id="any-new-data-can-be-included-without-planning"></a>

New data should still be reviewed for scope, Add-ons, custom handling, and available Entity Points capacity.

#### “Recent Data Migration fixes earlier configuration problems.” <a href="#recent-data-migration-fixes-earlier-configuration-problems" id="recent-data-migration-fixes-earlier-configuration-problems"></a>

No. Configuration or validation issues should be addressed before the final freshness sync.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Recent Data Migration helps active stores reduce the gap between the earlier migration result and the final source-store state before launch. It is especially useful when the Source Cart continues creating new orders, customers, products, or content while the Target Cart is being prepared.

Its value is freshness, not final approval. Newly synchronized data still needs to be validated, especially when Entity Points capacity, Add-ons, Custom Service requirements, or launch timing affect the result.

Plan Recent Data Migration as part of the launch sequence. If your source store remains active, review likely new-data growth, remaining Entity Points capacity, Add-on requirements, and any custom handling before the final sync. Live Chat can help clarify the safest timing and scope before go-live.

### FAQs <a href="#faqs" id="faqs"></a>

#### What is Recent Data Migration? <a href="#what-is-recent-data-migration" id="what-is-recent-data-migration"></a>

Recent Data Migration is the feature used to sync newly created source-store data into the Target Cart after earlier migration activity.

#### When should I use Recent Data Migration? <a href="#when-should-i-use-recent-data-migration" id="when-should-i-use-recent-data-migration"></a>

Use it when the Source Cart remains active after Full Migration and continues creating new records before launch.

#### Does Recent Data Migration replace Full Migration? <a href="#does-recent-data-migration-replace-full-migration" id="does-recent-data-migration-replace-full-migration"></a>

No. Full Migration is the main migration run. Recent Data Migration helps synchronize newly created data after earlier migration activity.

#### Does Recent Data Migration consume Entity Points? <a href="#does-recent-data-migration-consume-entity-points" id="does-recent-data-migration-consume-entity-points"></a>

Yes. Newly created counted records consume Entity Points when they are migrated successfully for the first time.

#### Can unused Entity Points support Recent Data Migration? <a href="#can-unused-entity-points-support-recent-data-migration" id="can-unused-entity-points-support-recent-data-migration"></a>

Yes. Unused Entity Points within the purchased plan can support newly created counted records migrated through Recent Data Migration.

#### What happens if there are not enough Entity Points for Recent Data Migration? <a href="#what-happens-if-there-are-not-enough-entity-points-for-recent-data-migration" id="what-happens-if-there-are-not-enough-entity-points-for-recent-data-migration"></a>

The customer can upgrade the Entity Points Plan. The upgrade adds capacity and the customer pays only the price difference between the current plan and the higher plan.

#### Can I use Add-ons with Recent Data Migration? <a href="#can-i-use-add-ons-with-recent-data-migration" id="can-i-use-add-ons-with-recent-data-migration"></a>

Yes. Add-ons may apply if the newly synchronized data needs filtering, advanced mapping, or data configuration.

#### Does Recent Data Migration replace validation? <a href="#does-recent-data-migration-replace-validation" id="does-recent-data-migration-replace-validation"></a>

No. Recent Data Migration improves data freshness. The customer still needs to validate the synchronized data and confirm launch readiness.
