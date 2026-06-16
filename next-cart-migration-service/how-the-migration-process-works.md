# How the Migration Process Works

A Next-Cart migration follows a structured service process for moving store data from a Source Platform to a Target Platform under the purchased migration service license. The process connects the selected migration path with the practical work needed to prepare source-store access, configure the migration, execute the selected scope, review the target-store result, and decide whether additional migration actions are needed later.

The process is more reliable when customers understand what each stage is meant to prove. Demo Migration gives early evidence, configuration shapes how store data should be handled, execution moves the selected scope, and validation confirms whether the target store is ready for the next business step.

### What the Migration Process Is Designed to Control <a href="#what-the-migration-process-is-designed-to-control" id="what-the-migration-process-is-designed-to-control"></a>

The migration process gives customers a controlled path from early proof to usable target-store results.

It helps control several important areas:

| Process area            | What it helps clarify                                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------- |
| Migration direction     | Which Source Platform and Target Platform are covered by the purchased migration path.                          |
| Store access            | Whether the source store and target store can provide the required data access.                                 |
| Migration scope         | Which supported data types, records, and settings should be included.                                           |
| Configuration           | How selected data should be mapped, filtered, adjusted, or handled with Add-ons where needed.                   |
| Execution               | How the configured migration is run under the service license.                                                  |
| Validation              | Whether the migrated target-store result is accurate, usable, and ready for the customer’s next step.           |
| Later migration actions | Whether the customer should continue the migration or perform a new migration after earlier migration activity. |

The process should be viewed as a sequence of decisions, not only as a transfer run. Each stage reduces uncertainty before the next stage begins.

### Stage 1: Demo Migration and Early Review <a href="#stage-1-demo-migration-and-early-review" id="stage-1-demo-migration-and-early-review"></a>

Demo Migration gives customers an early view of how selected source-store data may appear in the Target Platform.

The strongest Demo Migration sample is not always the simplest data. It should include records that reveal the real migration meaning of the source store, such as:

* products with variants, options, attributes, or special pricing;
* customer and order records that represent real business history;
* categories, CMS Pages, Blog Posts, reviews, or coupons that matter after launch;
* records affected by mapping, filtering, or configuration choices;
* examples that may reveal Add-on or Custom Service requirements.

Demo Migration helps answer practical questions before broader execution:

* Does the migrated sample appear in the expected structure?
* Do product, customer, order, and content records remain understandable?
* Do mapped values need adjustment?
* Does the sample reveal filtering, mapping, or data-configuration needs?
* Does the result suggest that standard handling may be insufficient?

Demo Migration is early evidence. It helps customers make better planning decisions, but it does not replace validation after broader migration activity.

### Stage 2: Source-Store and Target-Store Access Preparation <a href="#stage-2-source-store-and-target-store-access-preparation" id="stage-2-source-store-and-target-store-access-preparation"></a>

After the migration path is selected, the process depends on reliable access to the source store and target store.

Depending on the platforms involved, access may rely on API credentials, KitConnect, file-based data access, or another supported connection method. The correct access method depends on the Source Platform, Target Platform, and migration scope.

This stage matters because migration quality depends on whether Next-Cart can access the required source-store data and place it into the target store in a usable way. Access preparation can also reveal whether important information is stored outside the standard platform data model, such as custom fields, extensions, app data, plugin data, files, or Custom Platform structures.

Access preparation should confirm more than whether the platforms can connect. It should also help customers understand whether the expected store data is available for migration and whether special handling may be required.

### Stage 3: Migration Configuration <a href="#stage-3-migration-configuration" id="stage-3-migration-configuration"></a>

Migration configuration defines how the selected migration should run under the purchased service license.

At a planning level, configuration may include:

* selecting supported data types for migration;
* choosing migration settings that fit the project goal;
* reviewing source-to-target mappings;
* aligning values such as languages, customer groups, order statuses, or product-related fields;
* applying purchased Add-ons where filtering, advanced mapping, or data configuration is needed;
* identifying requirements that should be reviewed as Custom Service scope.

Configuration is where source-store meaning begins to be translated into target-store behavior. A target store may contain migrated records but still require review if the configured result does not support how the business needs to operate.

Customers should treat configuration as a decision point. It shapes the quality of the migrated result and can reveal whether the selected service model, Add-ons, or custom handling need closer review.

### Stage 4: Full Migration Execution <a href="#stage-4-full-migration-execution" id="stage-4-full-migration-execution"></a>

Full Migration is the execution stage where the configured migration moves the selected store data into the target store.

The migration runs through Next-Cart’s service process based on the selected migration path, configured scope, available platform access, and purchased service scope. Customers may monitor the process, but the main value of this stage is producing a target-store result that can be reviewed against real business expectations.

Next-Cart follows a fixed entity migration sequence:

> Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

Within each data type, records are migrated from oldest to newest based on the source database.

All scanned records are migrated by default unless filtering is configured. The entity quantities entered during purchase support pricing and Entity Points planning; they do not automatically limit which records are migrated. If the customer wants to migrate only selected records, that should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering capability is not enough.

### Migration Order and Entity Points Consumption Are Different  <a href="#migration-order-and-entity-points-consumption-are-different" id="migration-order-and-entity-points-consumption-are-different"></a>

The fixed migration sequence describes the order in which entity types are processed during migration. Entity Points describe the counted migration capacity for selected core entity types.

The migration process manages and handles data in this sequence:

> Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

Entity Points consumption is applied with the core data entities in this order:

> Product → Customer → Order → Blog Posts

This distinction matters because the migration flow includes supporting entities alongside the core data. Taxes, manufacturers, categories, reviews, coupons, and CMS Pages can be part of the migration sequence, while Entity Points consumption is tied to the counted core data types used for plan capacity.

For the migration process, the practical takeaway is simple: execution order determines how store data is processed, while Entity Points define the capacity for counted data. You should not treat purchase quantities as automatic filters or assume that every migrated supporting entity is measured the same way as counted core entities.

#### Stage 5: Result Validation  <a href="#stage-5-result-validation" id="stage-5-result-validation"></a>

After migration execution, the customer needs to review whether the target store works as expected.

Validation should not stop at checking whether records exist. A useful review confirms whether the target store supports the outcomes the business depends on.

Priority review areas often include:

* products, variants, options, attributes, pricing, and purchasing behavior;
* categories, menus, collections, or discovery paths;
* customer records and account expectations;
* order history and customer-service usefulness;
* reviews, coupons, CMS Pages, and Blog Posts where relevant;
* URL and content continuity where they affect traffic or customer journeys;
* records affected by Add-ons, mapping decisions, filtering, or Custom Service requirements.

The customer is always responsible for verifying the final results and ensuring the migration outcome meets desired expectations and needs, and that the store is suitable for launch.

Next-Cart may offer and provide support, execute tasks, or handle customization depending on the chosen service model and agreed service scope, but the customer remains responsible for final validation to ensure the outcome aligns with their expectations and migration scope.

### Stage 6: Launch Readiness and Later Migration Actions <a href="#stage-6-launch-readiness-and-later-migration-actions" id="stage-6-launch-readiness-and-later-migration-actions"></a>

If the source store remains active while the target store is being prepared, new records may appear after earlier migration activity. Customers may need to decide how to keep the target-store result aligned with the latest business needs before launch or after further preparation.

After performing a migration with the purchased migration service license, customers can access available migration actions for the same migration path. Depending on migration history and service availability, the customer may be able to:

* Continue the migration with the last used configuration;
* Continue the migration with a new configuration;
* Perform a new migration.

These actions help customers manage different business goals.

* Continuing the migration can help add later source-store records without rebuilding the entire migration decision from the beginning.
* Continuing with a new configuration allows the customer to adjust settings before another execution.
* Performing a new migration is more suitable when the customer wants a fresh migration result for the selected path.

This stage should be planned around the customer’s launch goal, not treated as an automatic substitute for validation. The customer still needs to confirm that the target store contains the expected data and that the result is suitable for the intended use.

### How Customer-Led and Expert-Led Execution Fit into the Process <a href="#how-customer-led-and-expert-led-execution-fit-into-the-process" id="how-customer-led-and-expert-led-execution-fit-into-the-process"></a>

The migration process can be customer-led or expert-led, depending on the selected service model and agreed scope.

* Standard Service and Custom Service without the Expert Handle option are customer-led for migration actions.
* Managed Service and Custom Service with the Expert Handle option allow Next-Cart experts to perform migration actions based on the customer’s request and agreed service scope.
* Customers of any service model can still access and perform available migration actions manually if they choose.

This responsibility model does not change the process stages. It changes who performs or coordinates the work, how much expert handling is included, and where the customer should request assistance before execution.

### Common Misunderstandings About the Process <a href="#common-misunderstandings-about-the-process" id="common-misunderstandings-about-the-process"></a>

**“The migration is complete when the run completes.”**

A completed run means the configured migration has finished processing. It does not automatically mean the target store is ready for launch. Review and validation still matter.

**“The numbers entered during purchase limit what gets migrated.”**

Entered entity quantities support pricing and Entity Points planning. They are not automatic filters. All scanned records are migrated by default unless filtering is configured.

**“Demo Migration proves the full migration result.”**

Demo Migration gives early evidence from a limited sample. Full validation is still needed after broader migration activity.

**“Migration order and Entity Points are the same concept.”**

Migration order describes the sequence used to process store data. Entity Points describe counted migration capacity. They are related to planning, but they should not be interpreted as the same mechanism.

**“Configuration is only a minor setup step.”**

Configuration is where scope, settings, mappings, and Add-ons are aligned with the expected target-store result. It can strongly affect whether the migrated store remains usable after migration.

### Conclusion  <a href="#conclusion" id="conclusion"></a>

The Next-Cart migration process gives customers a structured path from early proof to configured execution, result validation, launch readiness, and later migration actions when needed. Each stage has a specific role: Demo Migration provides early evidence, access preparation confirms whether store data can be reached, configuration shapes how data should be handled, Full Migration executes the selected scope, validation confirms the target-store result, and later migration actions help customers continue or restart migration activity for the same migration path.

A migration becomes more reliable when customers understand the purpose of each stage before moving forward. If the process reveals selective-scope needs, mapping uncertainty, Add-on requirements, Custom Service requirements, or launch-timing concerns, Live Chat can help clarify which part of the process needs closer review.

### FAQs  <a href="#faqs" id="faqs"></a>

**What are the main stages of a Next-Cart migration?**

The main stages are Demo Migration and early review, source-store and target-store access preparation, migration configuration, Full Migration execution, result validation, and launch readiness with later migration actions where needed.

**What is a migration path?**

A migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased migration service license.

**What is the fixed entity migration sequence?**

The fixed entity migration sequence is Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

**Are all scanned records migrated by default?**

Yes. All scanned records are migrated by default unless filtering is configured. If the customer wants to migrate only selected records, that should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering capability is not enough.

**Is the migration order the same as the Entity Points consumption sequence?**

No. The migration sequence determines the order in which entity types are processed. Entity Points consumption only applies to the data in this sequence: Product → Customer → Order → Blog.

**Can customers perform migration actions manually under any service model?**

Yes. Customers of any service model can access and perform available migration actions manually if they choose. The selected service model determines responsibility, including expert handling, and support scope.

**Does Demo Migration prove the full migration is ready?**

No. Demo Migration gives early evidence from a limited sample. Full validation is still needed after broader migration activity.

**What should customers check after migration execution?**

Customers should verify that the target store contains the expected records, that important data behaves correctly in the Target Platform, and that the migrated result is suitable for the intended launch or business use.
