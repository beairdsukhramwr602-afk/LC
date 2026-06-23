# Next-Cart Migration Service Overview

Next-Cart provides E-commerce Platform Migration Services for moving store data from a Source Platform to a Target Platform under a purchased migration service license. The service license connects the selected migration path with the practical decisions needed to prepare store data, configure migration behavior, choose a Migration Service, review the migrated result, and continue migration activity when needed.

A strong migration plan starts with the service structure, not only with the amount of data being moved. Data volume affects capacity and pricing, but migration quality also depends on platform fit, source-store condition, target-store expectations, configuration decisions, Add-ons, Custom Service needs, execution responsibility, and final result verification.

### What the Service Overview Helps Clarify <a href="#what-the-service-overview-helps-clarify" id="what-the-service-overview-helps-clarify"></a>

The service overview gives customers a first map of the decisions that shape a migration project. It helps separate related concepts that are often confused during early planning.

| Planning area       | What it clarifies                                                                                                 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Migration direction | Which Source Platform and Target Platform are covered by the selected migration path.                             |
| Service license     | Which purchased service access supports the migration path and later available migration actions.                 |
| Store data          | What source-store records, content, settings, and relationships may need to move into the target store.           |
| Capacity            | How Entity Points help estimate counted migration capacity for Product, Customer, Order, and Blog Posts data.     |
| Pricing             | How the Entity Points Plan, Migration Service, Add-ons, and custom requirements affect the total migration price. |
| Configuration       | How settings, filtering, mapping, and data-configuration choices shape the target-store result.                   |
| Responsibility      | Whether migration actions are customer-led, expert-led, or custom-scoped under the selected Migration Service.    |
| Validation          | What the customer must verify before treating the target-store result as ready for business use.                  |

These areas should be considered together. A store with modest data volume may still require deeper review if the source store contains custom fields, third-party data, unusual relationships, or target-store expectations that standard handling cannot fully cover. A store with larger data volume may remain straightforward when the migration path is well supported and the required outcome is predictable.

### Migration Path and Service License <a href="#migration-path-and-service-license" id="migration-path-and-service-license"></a>

A migration path defines the one-way direction from the Source Platform to the Target Platform. The service license is purchased for that selected direction and should not be treated as a reversible path unless the reverse direction is separately supported and purchased.

For example, a service license for Platform A to Platform B covers that migration direction. If the customer later needs Platform B to Platform A, that is a different migration path.

The migration path sets the service boundary. Before reviewing Entity Points, Add-ons, or Migration Services, customers should confirm that the selected Source Platform and Target Platform match the store they intend to migrate and the target environment they intend to prepare.

### Platform and Store Terminology <a href="#platform-and-store-terminology" id="platform-and-store-terminology"></a>

Next-Cart uses **Platform** when referring to the e-commerce system, platform type, data model, platform capability, or migration-path direction.

Examples include:

* Source Platform;
* Target Platform;
* platform data model;
* platform compatibility;
* platform-specific migration path.

Next-Cart uses **store** when referring to the merchant’s actual commerce environment, data source, destination environment, migrated records, storefront, execution result, or validation outcome.

Examples include:

* source store;
* target store;
* store data;
* store records;
* migrated store result;
* target-store validation.

This distinction matters because a Target Platform is the destination system type, while the target store is the actual destination environment that receives migrated data.

### How the Migration Process Fits into the Service <a href="#how-the-migration-process-fits-into-the-service" id="how-the-migration-process-fits-into-the-service"></a>

The migration process is the working path that turns the purchased service license into a migrated target-store result. It covers the practical stages customers move through, including early proof, access preparation, configuration, execution, validation, launch readiness, and later available migration actions.

At overview level, the process helps customers understand:

* whether representative source-store data can be migrated into a usable target-store structure;
* whether the source store and target store can provide the required access;
* how selected records, settings, and relationships should be configured;
* how the selected migration scope is executed;
* what the customer needs to review before relying on the migrated result;
* whether additional migration activity is needed after earlier migration work.

The process should be understood as a sequence of decisions and evidence points. A completed migration run is important, but the business value comes from whether the target store contains the expected data, behaves correctly, and is suitable for the customer’s next step.

### Demo Migration and Early Evidence <a href="#demo-migration-and-early-evidence" id="demo-migration-and-early-evidence"></a>

Demo Migration gives customers an early sample of how selected source-store data may appear after migration. It helps identify whether important records, relationships, and configuration assumptions still make sense in the Target Platform before broader execution.

A useful Demo Migration can reveal:

* whether product, customer, order, or content samples migrate in a usable way;
* whether representative records keep the meaning customers expect;
* whether mapping, filtering, or configuration should be adjusted;
* whether Add-ons may be needed;
* whether Custom Service review should happen before full execution.

Demo Migration supports planning and decision-making. It does not replace full validation after broader migration activity.

### Entity Points as Migration Capacity <a href="#entity-points-as-migration-capacity" id="entity-points-as-migration-capacity"></a>

Entity Points are Next-Cart’s capacity model for counted migration data. They help customers estimate how much capacity the purchased service license needs to support for Product, Customer, Order, and Blog Posts data.

Entity Points are important because they connect data volume with plan selection, but they do not describe the entire migration challenge. They do not decide whether platform structures match, whether custom fields need special handling, whether Add-ons are needed, or whether the target store is ready for launch.

Customers should treat Entity Points as a capacity measure. Migration quality still depends on preparation, configuration, service scope, platform fit, and final verification.

### Entity Points Plan and Pricing <a href="#entity-points-plan-and-pricing" id="entity-points-plan-and-pricing"></a>

The Entity Points Plan is the pricing-capacity layer of the migration service. It defines the available migration capacity under the purchased service license for the selected migration path.

Migration pricing can also be affected by:

* the selected Migration Service;
* optional Add-ons;
* Tailored Add-ons or Custom Add-ons;
* Custom Service requirements;
* expert-handled execution when included in the agreed scope.

The customer’s entered quantities support pricing and plan selection. They should not be treated as automatic migration filters. If the customer wants to migrate only selected records, that requirement should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering is not enough.

### Add-ons and Configuration Support <a href="#add-ons-and-configuration-support" id="add-ons-and-configuration-support"></a>

Add-ons are optional service features that support specific filtering, mapping, or data-configuration needs. They help customers control how selected source-store data should be handled before it becomes part of the target-store result.

The current Standard Add-ons are:

* Data Filter Add-on;
* Advanced Data Mapping;
* Advanced Data Configure.

Add-ons are suitable when the customer needs a focused configuration capability that fits available Add-on behavior. If an Add-on needs modification or the expected result cannot be handled by an available Standard Add-on, the requirement may require Tailored Add-ons, Custom Add-ons, or a broader Custom Service review.

Add-ons should not be confused with Custom Service. Add-ons support focused migration behavior. Custom Service handles broader customization, modification, bespoke handling, Custom Platform cases, and custom migration logic.

### Migration Services and Responsibility <a href="#migration-services-and-responsibility" id="migration-services-and-responsibility"></a>

Next-Cart provides three Migration Services: Standard Service, Managed Service, and Custom Service.

At overview level:

| Migration Service | Main role                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------- |
| Standard Service  | Customer-led migration using the purchased service license and any selected Add-ons.                    |
| Managed Service   | Next-Cart-led migration execution based on the customer’s request and agreed service scope.             |
| Custom Service    | Custom-scoped handling for customization, modification, Custom Platform cases, or bespoke requirements. |

Standard Service and Custom Service without the Expert Handle option are customer-led for migration actions.

Managed Service and Custom Service with the Expert Handle option allow Next-Cart experts to perform migration actions based on the customer’s request and agreed service scope.

Customers using any Migration Service can access and perform available migration actions manually if they choose. Under any Migration Service, the customer remains responsible for final result verification and migration outcome.

### Custom Service and Custom Requirements <a href="#custom-service-and-custom-requirements" id="custom-service-and-custom-requirements"></a>

Custom Service is leveraged when the migration requires customization, modification, or bespoke handling beyond standard service capability or Standard Add-on capability.

Custom Service may apply when the project involves:

* Custom Platform as Source Platform or Target Platform;
* custom fields;
* app, plugin, module, extension, or third-party data;
* outside-system identifiers;
* unsupported or unusual source-store structures;
* custom migration logic adjustment;
* Tailored Add-ons or Custom Add-ons;
* platform-capability limitations that affect the expected target-store result.

Custom Service does not automatically mean Next-Cart performs every migration action. Expert-handled execution depends on the customer’s request and the agreed custom scope.

### Additional Migration Options <a href="#additional-migration-options" id="additional-migration-options"></a>

After performing a migration with the purchased service license, customers may access additional migration options for the same migration path. These options help customers continue migration activity, adjust configuration before another execution, or create a new migration result when the business goal has changed.

Common available options include:

* Continue the Migration with the last used configuration;
* Continue the Migration with a new configuration;
* Perform a new migration.

These options are useful when the source store continues changing, when a later migration action needs different configuration, or when the customer wants a fresh migration result for the selected path. They should be chosen based on the customer’s intended target-store outcome and verified after execution.

### Recommended Reading Path <a href="#recommended-reading-path" id="recommended-reading-path"></a>

The strongest learning path through this service section is:

1. **Next-Cart Migration Service Overview** — understand the service system and the main planning concepts.
2. **How the Migration Process Works** — understand the migration journey from early proof to execution and validation.
3. **Demo Migration** — understand how early samples support planning decisions.
4. **Entity Points** — understand counted migration capacity.
5. **Entity Points Plan and Migration Pricing** — understand how capacity, Migration Service, Add-ons, and custom scope affect pricing.
6. **Add-ons** — understand focused filtering, mapping, and configuration support.
7. **Next-Cart Migration Services** — understand Standard Service, Managed Service, and Custom Service responsibility.
8. **What Custom Service Handles** — understand broader customization and bespoke migration needs.
9. **Choose the Right Migration Service** — connect the section concepts into a practical service decision.
10. **Additional Migration Options** — understand available options after migration activity has already taken place.

This order moves from orientation to process, proof, capacity, pricing, configuration support, service responsibility, custom scope, service choice, and later migration options.

### When to Ask for Clarification <a href="#when-to-ask-for-clarification" id="when-to-ask-for-clarification"></a>

Customers should ask for clarification when the migration decision depends on more than a straightforward supported path.

Useful signs include:

* uncertainty about which data types or records should be migrated;
* source-store growth before launch;
* selective migration requirements;
* mapping uncertainty;
* custom fields or third-party data;
* Custom Platform involvement;
* Add-on requirements that may need modification;
* uncertainty about whether the migration should be customer-led or expert-led;
* unclear validation expectations for the target store.

Clarifying these points before execution helps reduce rework and improves the chance that the migrated target-store result matches the customer’s intended business use.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Next-Cart’s E-commerce Platform Migration Service gives customers a structured way to plan, execute, and validate migration from a Source Platform to a Target Platform. The migration path defines the service direction. The migration process explains how the work moves from early evidence to execution and validation. Entity Points and the Entity Points Plan clarify capacity and pricing. Add-ons support focused configuration needs. Migration Services define responsibility. Custom Service handles requirements beyond standard capability. Additional migration options help customers continue working with the same migration path after earlier migration activity.

A reliable migration decision comes from understanding how these parts work together. Customers should review what the source store contains, what the target store needs to become, who should perform the migration actions, which configuration or custom handling is needed, and how the final migrated result will be verified.

For migration questions involving unclear scope, Add-ons, custom data, service responsibility, pricing capacity, or target-store readiness, Live Chat can help clarify the next decision before the customer commits to a service path.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What does Next-Cart’s migration service help customers do?**

Next-Cart’s E-commerce Platform Migration Service helps customers move store data from a Source Platform to a Target Platform through a selected migration path, service license, configuration process, execution flow, and validation stage.

**What is a migration path?**

A migration path is the selected one-way direction from the Source Platform to the Target Platform under the purchased service license. It defines the service direction covered by the license.

**What is the difference between a platform and a store?**

A Platform is the e-commerce system or supported platform type, such as the Source Platform or Target Platform. A store is the merchant’s actual commerce environment, source data, destination environment, or migrated result.

**Are Entity Points the same as migration complexity?**

No. Entity Points measure counted migration capacity for selected core data types. Migration complexity can also come from platform differences, custom fields, third-party data, Add-ons, Custom Service requirements, and validation expectations.

**Are Add-ons the same as Custom Service?**

No. Add-ons are focused optional service features for filtering, mapping, or data configuration. Custom Service handles broader customization, modification, Custom Platform cases, custom logic, and requirements that do not fit standard service capability.

**Does Custom Service always mean Next-Cart performs the migration?**

No. Custom Service means the project requires custom or tailored handling. Expert-handled migration execution depends on the customer’s request and the agreed custom scope.

**Can customers perform migration actions manually under any Migration Service?**

Yes. Customers using any Migration Service can access and perform available migration actions manually if they choose. Migration Services define the responsibility and include work, while the customer remains responsible for final result verification and the migration outcome.

**What are additional migration options?**

Additional migration options are available to customers after migration activity has already taken place under the purchased service license. They may include continuing with the last used configuration, continuing with a new configuration, or performing a new migration for the same migration path.
