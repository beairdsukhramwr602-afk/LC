# Next-Cart Migration Process Explained

A Next-Cart migration follows a structured service process that moves store data from a Source Platform to a Target Platform under the selected migration path. The process is not only a transfer run. It is a sequence of service steps, configuration decisions, execution work, review checkpoints, and final freshness alignment.

The selected migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased service license. Understanding that direction helps customers interpret the migration process, service scope, Add-ons, Entity Points, and final service choice more accurately.

This article explains how the process works at a planning level: how a Next-Cart migration moves from early proof to source and target connection, service configuration, Full Migration, validation, and final freshness alignment.

### What the Migration Process Is Designed to Do  <a href="#what-the-migration-process-is-designed-to-do" id="what-the-migration-process-is-designed-to-do"></a>

The migration process is designed to create a controlled path from initial evidence to a launch-ready target store.

That path supports six practical goals:

* confirm that the Source Platform and Target Platform can be connected
* use Demo Migration to test the migration direction before full execution
* configure the migration scope, settings, mappings, and any purchased Add-ons
* run the Full Migration under the selected migration path
* validate whether the migrated result works as expected
* use Recent Data Migration where the Source Platform continues creating new data before launch

Each stage reduces uncertainty before the next one. A migration becomes riskier when the customer treats it as a single event rather than a process that requires review and adjustment.

### The Migration Process in Six Stages  <a href="#the-migration-process-in-six-stages" id="the-migration-process-in-six-stages"></a>

A practical way to understand the Next-Cart migration process is through six stages:

1. Demo Migration and early review
2. Connecting the Source Platform and Target Platform
3. Migration configuration
4. Full Migration execution
5. Result validation
6. Recent Data Migration and launch readiness

The same general process applies across service models. What changes is the service responsibility, whether standard service capability is enough, and whether customization or modification work is required.

#### Stage 1: Demo Migration and Early Review  <a href="#stage-1-demo-migration-and-early-review" id="stage-1-demo-migration-and-early-review"></a>

Demo Migration gives the customer an early view of how selected source-store data may appear in the Target Platform.

This stage is meant to reveal whether the selected migration path is workable before the customer relies on the full migration. The most useful sample is not always the simplest data. It should include records that can reveal real migration meaning, such as products with options or variants, meaningful customer and order examples, important categories, or content records that need to remain useful after launch.

At this stage, the customer should look for answers to questions such as:

* does the migrated sample appear in the expected structure?
* do products, customers, orders, and content remain understandable?
* do mapped values need adjustment?
* does the sample reveal filtering, mapping, or configuration needs?
* does the result suggest a Custom Service requirement?

Demo Migration gives early evidence for planning. The broader result still needs to be reviewed after the Full Migration.

#### Stage 2: Connecting the Source Platform and Target Platform  <a href="#stage-2-source-and-target-connection" id="stage-2-source-and-target-connection"></a>

After the migration direction is understood, the process depends on reliable access to both platforms.

Depending on the platforms involved, Next-Cart may connect through API access, KitConnect, or file-based data access. The connection method depends on what the Source Platform and Target Platform support and what the migration scope requires.

This stage matters because migration quality depends on whether the process can access the right source data and move it into the target environment in a usable way.

Connection should not be treated only as an access checkpoint. It also helps reveal whether the data is available through the expected platform model or whether important information lives in a place that needs closer review, such as custom fields, extensions, files, or a Custom Platform structure.

#### Stage 3: Migration Configuration  <a href="#stage-3-migration-configuration" id="stage-3-migration-configuration"></a>

Configuration defines how the migration should run within the purchased service.

At a planning level, configuration can include:

* selecting the supported data types to migrate
* choosing migration settings that fit the project goal
* reviewing source-to-target mappings
* aligning mapped values such as languages, customer groups, or order statuses
* selecting purchased Add-ons where filtering, advanced mapping, or data configuration is needed
* identifying requirements that go beyond standard service capability or standard Add-on capability

This stage is where source-store meaning begins to be translated into target-platform behavior. A weak configuration can lead to a target store that appears populated but does not behave as expected in the areas that matter.

The customer should treat configuration as a decision point, not only as a setup step.

#### Stage 4: Full Migration Execution  <a href="#stage-4-full-migration-execution" id="stage-4-full-migration-execution"></a>

Full Migration is the stage where the configured migration moves the selected store data into the Target Platform.

The migration runs through Next-Cart’s service process and can continue in the background during execution. The customer can monitor progress, but the value of this stage is not only seeing whether the run completes. The value is producing a target-store result that can be reviewed against real business expectations.

The fixed entity migration sequence is: Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

Within each data type, records are migrated from oldest to newest based on the source database.

All scanned records are migrated by default. The numbers entered during purchase are used for pricing and Entity Points planning. They do not automatically limit which records are migrated. If the customer wants to migrate only selected records, that should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement if the Standard Add-on capability is not enough.

### Migration Order and Entity Points Consumption Are Different  <a href="#migration-order-and-entity-points-consumption-are-different" id="migration-order-and-entity-points-consumption-are-different"></a>

The fixed entity migration sequence is not the same as the Entity Points consumption sequence.

The migration process follows this entity order:

> Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

Entity Points consumption is processed through the counted core sequence:

> Product → Customer → Order → Blog

This distinction matters because the migration flow includes supporting entities as well as counted core data. Taxes, manufacturers, categories, reviews, coupons, and CMS Pages can be part of the migration sequence, while Entity Points consumption is tied to the counted core data types used for plan capacity.

For planning purposes, the safest assumption is that migration execution follows the full entity sequence, while capacity consumption should be interpreted through Product, Customer, Order, and Blog.

#### Stage 5: Result Validation  <a href="#stage-5-result-validation" id="stage-5-result-validation"></a>

After Full Migration, the customer needs to review whether the target store works as expected.

Validation should not stop at checking whether records exist. A useful review should confirm whether the Target Platform still supports the outcomes the business depends on.

Priority review areas often include:

* products and purchasing behavior
* categories and discovery paths
* customer records and account expectations
* order history and customer-service usefulness
* reviews, coupons, CMS Pages, and Blog Posts where relevant
* URL and content continuity where they affect traffic or customer journeys
* records affected by Add-ons or Custom Service requirements

The customer remains responsible for confirming whether the result is acceptable for launch. Next-Cart may provide support, perform execution work, or handle customization depending on the selected service model and final plan, but the business still needs to judge whether the migrated store meets its expectations.

#### Stage 6: Recent Data Migration and Launch Readiness  <a href="#stage-6-recent-data-migration-and-launch-readiness" id="stage-6-recent-data-migration-and-launch-readiness"></a>

If the Source Platform remains active after Full Migration, new data may continue to appear before launch. Recent Data Migration helps synchronize newly created source-store data into the Target Platform closer to go-live.

This stage is useful when the source store continues receiving new orders, customers, products, or content while the target store is being prepared.

Recent Data Migration helps reduce the freshness gap between the earlier migration result and the final launch-ready state. After the sync, the customer still needs to confirm that newly synchronized data appears correctly and that the completed target store is ready for launch.

### How Self-Performance Fits Into the Process <a href="#how-self-performance-fits-into-the-process" id="how-self-performance-fits-into-the-process"></a>

Customers of any service model can access and self-perform the migration process on the Next-Cart website if they want to.

The service model determines the service responsibility and included work, not whether the customer has access. Standard Service is customer-led. Managed Service is Next-Cart-led. Custom Service covers customization or modification work, with migration management included only when part of the final plan.

This access rule does not change the six-stage process. It only clarifies that customers can still access the migration process on the Next-Cart website even when Next-Cart is responsible for execution under Managed Service or a Custom Service plan with migration management.

### Common Misunderstandings About the Process  <a href="#common-misunderstandings-about-the-process" id="common-misunderstandings-about-the-process"></a>

**“The migration is complete when the run completes.”**

A completed run means the configured migration has finished processing. It does not automatically mean the target store is ready for launch. Review and validation still matter.

**“The numbers entered during purchase limit what gets migrated.”**

Entered entity numbers support pricing and Entity Points planning. They are not automatic filters. All scanned records are migrated by default unless filtering is configured.

**“Demo Migration proves the full migration result.”**

Demo Migration gives early evidence from a limited sample. Full validation is still needed after broader migration activity.

**“Migration order and Entity Points consumption order are the same.”**

The migration sequence and Entity Points consumption sequence are related, but they are not the same. The process follows the fixed entity migration order, while Entity Points are consumed through Product, Customer, Order, and Blog.

**“Configuration is only a minor setup step.”**

Configuration is where scope, settings, mappings, and Add-ons are aligned with the expected result. It can strongly affect whether the target store remains usable after migration.

### Conclusion  <a href="#conclusion" id="conclusion"></a>

The Next-Cart migration process is a controlled journey from early proof to full execution, validation, and final freshness alignment. Each stage has a specific purpose: Demo Migration reveals direction, connection confirms access, configuration shapes how data should move, Full Migration executes the transfer, validation confirms whether the result is usable, and Recent Data Migration helps active stores stay current before launch.

The process becomes more reliable when customers understand what each stage is meant to prove and how the selected migration path, migration sequence, Entity Points consumption, Add-ons, and service responsibility affect the decisions made along the way.

Review the migration process as a sequence of decisions, not only as a transfer run. If the process reveals selective-scope needs, mapping uncertainty, Add-on requirements, Custom Service requirements, or launch-timing concerns, Live Chat can help clarify which stage needs closer review before the project moves further.

### FAQs  <a href="#faqs" id="faqs"></a>

**What are the main stages of a Next-Cart migration?**

The main stages are Demo Migration and early review, source and target connection, migration configuration, Full Migration execution, result validation, and Recent Data Migration where final freshness alignment is needed.

**What is a migration path?**

A migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased service license.

**What is the fixed entity migration sequence?**

The fixed entity migration sequence is Taxes, Manufacturers, Categories, Products, Customers, Orders, Reviews, Coupons, CMS Pages, and Blog Posts.

**Are all scanned records migrated by default?**

Yes. All scanned records are migrated by default. If the customer wants to migrate only selected records, that should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement if the Standard Add-on capability is not enough.

**Is the migration sequence the same as the Entity Points consumption sequence?**

No. The migration sequence controls the order in which entity types are processed. Entity Points consumption follows the counted core sequence of Product, Customer, Order, and Blog.

**Can customers self-perform the migration under any service model?**

Yes. Customers of Standard Service, Managed Service, and Custom Service can access and self-perform the migration process on the Next-Cart website if they want to. The service model determines the service responsibility and included work, not whether the customer has access.

**Does Demo Migration prove the full migration is ready?**

No. Demo Migration gives early evidence from a limited sample. Full validation is still needed after broader migration activity.

**Does Recent Data Migration replace validation?**

No. Recent Data Migration helps sync newly created source-store data before launch. The customer still needs to validate that the latest data appears correctly and that the target store is ready for launch.
