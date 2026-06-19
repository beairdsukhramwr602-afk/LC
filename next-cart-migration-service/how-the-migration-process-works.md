# How the Migration Process Works

A Next-Cart migration follows a structured service process for moving store data from a Source Platform to a Target Platform under a purchased migration service license. The process connects the selected migration path with the practical work needed to prepare source-store access, configure migration behavior, execute the selected scope, review the target-store result, and decide whether additional migration activity is needed later.

The process works best when each stage is treated as a decision checkpoint. Demo Migration gives early evidence, access preparation confirms whether required store data can be reached, configuration defines how data should be handled, Full Migration produces the broader target-store result, validation confirms whether the result can be trusted, and launch readiness helps customers decide whether further migration activity is needed.

### What the Migration Process Is Designed to Control <a href="#what-the-migration-process-is-designed-to-control" id="what-the-migration-process-is-designed-to-control"></a>

The migration process gives customers a controlled path from early proof to a usable target-store result. It is not only an execution run; it is a sequence of planning, configuration, review, and validation decisions.

| Process area             | What it helps clarify                                                                                          |
| ------------------------ | -------------------------------------------------------------------------------------------------------------- |
| Migration direction      | Which Source Platform and Target Platform are covered by the purchased migration path.                         |
| Store access             | Whether the source store and target store can provide the required access for the selected scope.              |
| Migration scope          | Which supported data types, records, content, and settings should be included.                                 |
| Configuration            | How selected data should be mapped, filtered, adjusted, or handled with Add-ons where needed.                  |
| Execution                | How the configured migration is run under the service license.                                                 |
| Validation               | Whether the migrated target-store result is accurate, usable, and ready for the customer’s next business step. |
| Later migration activity | Whether the customer should use additional migration options after earlier migration activity has taken place. |

A migration becomes more reliable when these areas are reviewed before full reliance on the target store. A completed migration run confirms that processing has finished; validation confirms whether the migrated result supports the customer’s business expectations.

### Stage 1: Demo Migration and Early Review <a href="#stage-1-demo-migration-and-early-review" id="stage-1-demo-migration-and-early-review"></a>

Demo Migration gives customers an early view of how selected source-store data may appear in the Target Platform. It helps customers review representative data before broader migration activity.

A useful Demo Migration sample should include records that reveal the real migration meaning of the source store, not only records that are easy to migrate. Strong samples may include:

* products with variants, options, attributes, images, or special pricing;
* customer and order records that represent real business history;
* categories, CMS Pages, Blog Posts, reviews, or coupons that matter after launch;
* records affected by filtering, mapping, language, status, or configuration choices;
* examples that may reveal Add-on or Custom Service requirements.

Demo Migration helps customers answer practical questions:

* Does the migrated sample appear in the expected target-store structure?
* Do products, customers, orders, and content remain understandable?
* Do mapped values need adjustment before broader execution?
* Does the sample reveal filtering, mapping, or data-configuration needs?
* Does the result suggest that standard handling may be insufficient?

Demo Migration provides early evidence. It supports planning and service-scope decisions, but it does not replace validation after broader migration activity.

### Stage 2: Source-Store and Target-Store Access Preparation <a href="#stage-2-source-store-and-target-store-access-preparation" id="stage-2-source-store-and-target-store-access-preparation"></a>

After the migration path is selected, the process depends on reliable access to the source store and target store. The required access method depends on the Source Platform, Target Platform, selected scope, and available platform support.

Depending on the migration path, access may involve API credentials, KitConnect, file-based data access, or another supported connection method. The purpose is not only to connect systems. The purpose is to confirm whether the source-store data needed for the migration can be reached and placed into the target store in a usable way.

Access preparation may reveal planning issues before execution, such as:

* important data stored outside the standard platform data model;
* custom fields, app data, plugin data, module data, extension data, or third-party records;
* files or media that require separate preparation;
* unsupported source-store structures;
* Custom Platform requirements;
* target-store limitations that affect how data should be handled.

Customers should treat access preparation as a readiness checkpoint. If required data cannot be reached through the expected method, or if important records depend on custom structures, the migration may need Add-ons, Custom Service review, or adjusted preparation before execution.

### Stage 3: Migration Configuration <a href="#stage-3-migration-configuration" id="stage-3-migration-configuration"></a>

Migration configuration defines how the selected migration should run under the purchased service license. It turns migration scope into practical handling decisions.

At a planning level, configuration may include:

* selecting supported data types for migration;
* choosing migration settings that fit the project goal;
* reviewing source-to-target mappings;
* aligning values such as languages, customer groups, order statuses, product attributes, or other mapped fields;
* applying purchased Add-ons where filtering, advanced mapping, or data configuration is needed;
* identifying requirements that should be reviewed as Custom Service scope.

Configuration is where source-store meaning begins to be translated into target-store behavior. A target store may contain migrated records but still need review if the configuration does not support how the business needs to operate.

Customers should treat configuration as a decision point. It can determine whether migrated products remain buyable, whether customers and orders remain useful, whether content still makes sense, and whether the selected service model has enough support for the expected result.

### Stage 4: Full Migration Execution <a href="#stage-4-full-migration-execution" id="stage-4-full-migration-execution"></a>

Full Migration is the execution stage where the configured migration moves the selected store data into the target store.

The migration runs through Next-Cart’s service process based on the selected migration path, configured scope, available access, and purchased service scope. Customers may monitor the process, but the main value of this stage is producing a target-store result that can be reviewed against real business expectations.

Next-Cart follows a fixed entity migration sequence:

> Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

Within each data type, records are migrated from oldest to newest based on the source database.

All scanned records are migrated by default unless filtering is configured. The quantities entered during purchase support pricing and Entity Points planning; they do not automatically limit which records are migrated. If the customer wants to migrate only selected records, that requirement should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering capability is not enough.

### Migration Order and Entity Points Consumption Are Different <a href="#migration-order-and-entity-points-consumption-are-different" id="migration-order-and-entity-points-consumption-are-different"></a>

Migration order and Entity Points consumption are related to the same migration project, but they describe different things.

The migration process handles data types in this sequence:

> Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts

Entity Points consumption applies to the counted core data types in this sequence:

> Product → Customer → Order → Blog Posts

This distinction matters because the migration flow includes supporting entities alongside the counted core data. Taxes, manufacturers, categories, reviews, coupons, and CMS Pages can be part of the migration sequence, while Entity Points consumption is tied to the counted data types used for plan capacity.

For process planning, the practical distinction is direct: execution order determines how the store data is processed, while Entity Points define counted migration capacity. Entered purchase quantities should not be interpreted as automatic filters, and supporting entities should not be assumed to consume Entity Points in the same way as counted core data.

### Stage 5: Result Validation <a href="#stage-5-result-validation" id="stage-5-result-validation"></a>

After migration execution, the customer needs to review whether the target store works as expected. Validation should not stop at checking whether records exist. A useful review confirms whether the target store supports the outcomes the business depends on.

Priority review areas often include:

* products, variants, options, attributes, pricing, images, and purchasing behavior;
* categories, menus, collections, navigation, or discovery paths;
* customer records and account expectations;
* order history and customer-service usefulness;
* reviews, coupons, CMS Pages, and Blog Posts where relevant;
* URL and content continuity where they affect traffic or customer journeys;
* records affected by Add-ons, mapping decisions, filtering, or Custom Service requirements.

The customer remains responsible for final result verification and migration outcome. Next-Cart may provide support, perform migration actions, or handle customization depending on the selected service model and agreed scope, but only the customer can confirm whether the target store matches the intended business use.

Validation should produce clear decisions. If the migrated result is accurate and suitable, the customer can continue toward the next launch or business step. If the result exposes mapping issues, missing records, unsupported custom data, or target-store behavior that does not match expectations, the customer should review whether configuration, Add-ons, Custom Service, or another migration action is needed.

### Stage 6: Launch Readiness and Additional Migration Options <a href="#stage-6-launch-readiness-and-additional-migration-options" id="stage-6-launch-readiness-and-additional-migration-options"></a>

If the source store remains active while the target store is being prepared, new records may appear after earlier migration activity. Customers may need to keep the target-store result aligned with current business needs before launch or after further preparation.

After performing a migration with the purchased migration service license, customers may access additional migration options for the same migration path. Depending on migration history and service availability, available options may include:

* Continue the Migration with the last used configuration;
* Continue the Migration with a new configuration;
* Perform a new migration.

These options support different goals. Continuing with the last used configuration can help add later source-store records without rebuilding the configuration decision. Continuing with a new configuration allows the customer to adjust settings before another execution. Performing a new migration is more suitable when the customer wants a fresh migration result for the selected path.

Additional migration options should be chosen around the intended target-store outcome. After any additional migration activity, the customer still needs to verify that the target store contains the expected data and is suitable for the intended use.

### How Customer-Led and Expert-Led Execution Fit into the Process <a href="#how-customer-led-and-expert-led-execution-fit-into-the-process" id="how-customer-led-and-expert-led-execution-fit-into-the-process"></a>

The migration process can be customer-led or expert-led depending on the selected service model and agreed scope.

| Service context                      | Execution responsibility                                                                                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Standard Service                     | The customer performs migration actions.                                                                                                                                 |
| Custom Service without Expert Handle | The customer performs migration actions.                                                                                                                                 |
| Managed Service                      | Next-Cart performs migration actions based on the customer’s request and agreed service scope. The customer can still perform available actions manually if they choose. |
| Custom Service with Expert Handle    | Next-Cart performs migration actions based on the customer’s request and agreed custom scope. The customer can still perform available actions manually if they choose.  |

Customers of any service model can access and perform available migration actions manually if they choose. The selected service model determines responsibility, expert handling, and support scope. With any service model, the customer remains responsible for final result verification and migration outcome.

### Common Misunderstandings About the Process <a href="#common-misunderstandings-about-the-process" id="common-misunderstandings-about-the-process"></a>

#### “The migration is complete when the run completes.” <a href="#the-migration-is-complete-when-the-run-completes" id="the-migration-is-complete-when-the-run-completes"></a>

A completed run means the configured migration has finished processing. It does not automatically mean the target store is ready for launch. Review and validation still matter.

#### “The numbers entered during purchase limit what gets migrated.” <a href="#the-numbers-entered-during-purchase-limit-what-gets-migrated" id="the-numbers-entered-during-purchase-limit-what-gets-migrated"></a>

Entered entity quantities support pricing and Entity Points Plan selection. They are not automatic migration filters. All scanned records are migrated by default unless filtering is configured.

#### “Demo Migration proves the full migration result.” <a href="#demo-migration-proves-the-full-migration-result" id="demo-migration-proves-the-full-migration-result"></a>

Demo Migration gives early evidence from a limited sample. Full validation is still needed after broader migration activity.

#### “Migration order and Entity Points are the same concept.” <a href="#migration-order-and-entity-points-are-the-same-concept" id="migration-order-and-entity-points-are-the-same-concept"></a>

Migration order describes the sequence used to process store data. Entity Points describe counted migration capacity. They are related to planning, but they should not be interpreted as the same mechanism.

#### “Configuration is only a minor setup step.” <a href="#configuration-is-only-a-minor-setup-step" id="configuration-is-only-a-minor-setup-step"></a>

Configuration is where scope, settings, mappings, and Add-ons are aligned with the expected target-store result. It can strongly affect whether the migrated store remains usable after migration.

#### “Expert-led service means the customer no longer needs to validate the result.” <a href="#expert-led-service-means-the-customer-no-longer-needs-to-validate-the-result" id="expert-led-service-means-the-customer-no-longer-needs-to-validate-the-result"></a>

Expert-led execution can reduce operational effort, but the customer still needs to verify the final result and migration outcome. Only the customer can confirm whether the target store meets the intended business expectation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The Next-Cart migration process gives customers a structured path from early proof to configured execution, result validation, launch readiness, and additional migration options when needed. Each stage has a specific role: Demo Migration provides early evidence, access preparation confirms whether store data can be reached, configuration shapes how data should be handled, Full Migration executes the selected scope, validation confirms the target-store result, and additional migration options help customers continue or restart migration activity for the same migration path.

A migration becomes more reliable when customers understand the purpose of each stage before moving forward. If the process reveals selective-scope needs, mapping uncertainty, Add-on requirements, Custom Service requirements, service-responsibility questions, or launch-timing concerns, Live Chat can help clarify which part of the process needs closer review.

### FAQs <a href="#faqs" id="faqs"></a>

**What are the main stages of a Next-Cart migration?**

The main stages are Demo Migration and early review, source-store and target-store access preparation, migration configuration, Full Migration execution, result validation, and launch readiness with additional migration options where needed.

**What is a migration path?**

A migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased migration service license.

**What is the fixed entity migration sequence?**

The fixed entity migration sequence is Taxes → Manufacturers → Categories → Products → Customers → Orders → Reviews → Coupons → CMS Pages → Blog Posts.

**Are all scanned records migrated by default?**

Yes. All scanned records are migrated by default unless filtering is configured. If the customer wants to migrate only selected records, that requirement should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering capability is not enough.

**Is migration order the same as Entity Points consumption?**

No. Migration order determines the sequence used to process store data. Entity Points consumption applies to counted core data types: Product, Customer, Order, and Blog Posts.

**Can customers perform migration actions manually under any service model?**

Yes. Customers of any service model can access and perform available migration actions manually if they choose. The selected service model determines responsibility, expert handling, and support scope.

**Does Demo Migration prove the full migration is ready?**

No. Demo Migration gives early evidence from a limited sample. Full validation is still needed after broader migration activity.

**What should customers check after migration execution?**

Customers should verify that the target store contains the expected records, that important data behaves correctly in the Target Platform, and that the migrated result is suitable for the intended launch or business use.
