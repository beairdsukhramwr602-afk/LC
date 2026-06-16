# Next-Cart Migration Service Overview

Next-Cart provides E-commerce Platform Migration Services for moving store data from a Source Platform to a Target Platform through a structured service license. The selected migration path defines the direction of the service, while the service model, Entity Points Plan, Add-ons, and support scope determine how the migration is planned and handled.

A clear service overview helps customers avoid treating migration as a single transfer action. A reliable migration decision depends on understanding what is being migrated, how the migration is configured, who performs the migration actions, when additional configuration support may be needed, and how the migrated result should be verified before launch.

### What the Service Helps Customers Plan <a href="#what-the-service-helps-customers-plan" id="what-the-service-helps-customers-plan"></a>

Next-Cart’s migration service helps customers plan more than data movement. It gives structure to the main decisions that affect migration readiness, cost, responsibility, and result quality.

The most important planning questions are:

| Planning question                              | Why it matters                                                                                              |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| What is the migration path?                    | The purchased service license is tied to a selected Source Platform and Target Platform direction.          |
| What data needs to move?                       | Product, customer, order, blog, content, and other store records affect scope, preparation, and validation. |
| How much counted migration capacity is needed? | Entity Points help estimate capacity for counted migrated entities.                                         |
| How should the migration be configured?        | Configuration choices, Add-ons, and mapping decisions affect the target-store result.                       |
| Who should perform the migration actions?      | Service models define customer-led, Next-Cart-led, or custom-handled responsibility.                        |
| Does the project need custom handling?         | Custom Platform, custom fields, third-party data, or unusual logic may require Custom Service.              |
| What needs to be verified?                     | The customer remains responsible for final result verification and migration outcome.                       |

These questions work together. A migration can have a clear service path but still need Add-ons, Custom Service review, or deeper validation because of how the source store is structured or how the target store should operate.

### Migration Path and Service License <a href="#migration-path-and-service-license" id="migration-path-and-service-license"></a>

A migration path defines the one-way direction of the purchased service license, from the Source Platform to the Target Platform.

For example, a service license purchased for Platform A to Platform B should be understood as that selected direction. It should not be treated as a reversible service path unless that reverse direction is separately supported and purchased.

The migration path gives the project a defined service boundary. It helps customers understand which Source Platform and Target Platform direction is covered before they make decisions about configuration, Entity Points capacity, Add-ons, service model, or Custom Service needs.

### Platform and Store Terminology <a href="#platform-and-store-terminology" id="platform-and-store-terminology"></a>

Next-Cart uses **Platform** when referring to the e-commerce system, supported platform type, data model, service path, or platform capability.

Examples include:

* Source Platform
* Target Platform
* platform data model
* platform compatibility
* platform-specific migration path

Next-Cart uses **store** when referring to the merchant’s actual commerce environment, source data, target environment, migrated records, execution result, or validation outcome.

Examples include:

* source store
* target store
* store data
* store records
* migrated store result
* target-store validation

This distinction matters because a Target Platform is the destination system type, while the target store is the actual destination environment that receives migrated data.

### How the Migration Process Fits into the Service <a href="#how-the-migration-process-fits-into-the-service" id="how-the-migration-process-fits-into-the-service"></a>

The migration process is the customer-level journey for preparing, configuring, executing, reviewing, and validating the migration. It connects the purchased service license to the practical work needed to move store data into the target store.

At overview level, the process usually involves:

* early proof through Demo Migration;
* source-store and target-store access preparation;
* migration configuration;
* execution of the selected migration scope;
* review and validation of the migrated result;
* launch-readiness planning and any later migration actions available through the service license.

The process article explains this flow in more detail. The overview point is simple: service choice should be based on the migration journey as a whole, not only on price or data volume.

### Demo Migration as Early Proof <a href="#demo-migration-as-early-proof" id="demo-migration-as-early-proof"></a>

Demo Migration gives customers an early sample of how representative source-store data appears after migration. It helps show whether important records and relationships still make sense in the target store before broader execution.

Demo Migration is useful because it can reveal:

* whether product, customer, order, or content samples migrate in a usable way;
* whether the target store interprets important data differently;
* whether configuration changes or Add-ons may be needed;
* whether the project shows signs of requiring Custom Service;
* whether the selected service path still looks practical.

Demo Migration supports planning. It should not be treated as final approval of the complete migrated store.

### Entity Points as Migration Capacity <a href="#entity-points-as-migration-capacity" id="entity-points-as-migration-capacity"></a>

Entity Points are Next-Cart’s capacity measurement for counted migrated entities. They help estimate the amount of counted data the purchased service license needs to support.

Entity Points are connected to core migrated entity types such as Product, Customer, Order, and Blog. They help customers understand migration capacity, but they do not measure every source of migration complexity.

A project can have a clear Entity Points estimate and still need careful planning because of platform differences, custom fields, third-party data, Add-ons, Custom Service requirements, or target-store validation needs.

### Entity Points Plan and Migration Pricing <a href="#entity-points-plan-and-migration-pricing" id="entity-points-plan-and-migration-pricing"></a>

The Entity Points Plan is the capacity layer of migration pricing. Customers estimate their counted migration volume, and the plan provides the corresponding service capacity for the selected migration path.

Migration pricing can also be affected by:

* selected service model;
* purchased Add-ons;
* Custom Service scope;
* tailored configuration or custom migration logic;
* expert-handled migration responsibility when included in the service plan.

Entity Points Plan and pricing should be understood together, but they are not the entire service decision. Service responsibility, Add-ons, custom requirements, and validation expectations can be just as important as capacity.

### Add-ons and Configuration Support <a href="#add-ons-and-configuration-support" id="add-ons-and-configuration-support"></a>

Add-ons are optional service features that help customers control specific migration behavior, such as filtering, mapping, or data configuration.

The main Standard Add-ons are:

* Data Filter Add-on;
* Advanced Data Mapping;
* Advanced Data Configure.

Add-ons are useful when the customer needs more control over the target-store result, but the requirement still fits an available Add-on scope. If an Add-on needs modification, or if the requirement cannot be handled by an available Standard Add-on, the need may move into Custom Service.

Add-ons and Custom Service should not be treated as the same thing. Add-ons support focused configuration needs. Custom Service handles broader customization, modification, and bespoke migration requirements.

### Service Models and Responsibility <a href="#service-models-and-responsibility" id="service-models-and-responsibility"></a>

Next-Cart provides three service models: Standard Service, Managed Service, and Custom Service.

At overview level:

| Service model    | Main role                                                                                          |
| ---------------- | -------------------------------------------------------------------------------------------------- |
| Standard Service | Customer-led migration using the purchased service license and any selected Add-ons.               |
| Managed Service  | Next-Cart-led migration execution based on the customer’s request and agreed service scope.        |
| Custom Service   | Customization, modification, or bespoke migration handling when standard capability is not enough. |

Service models define responsibility and included work. They do not remove the customer’s responsibility to verify the final migrated result and migration outcome.

### Custom Service and Custom Requirements <a href="#custom-service-and-custom-requirements" id="custom-service-and-custom-requirements"></a>

Custom Service is the path for requirements that need tailored handling beyond standard service capability or Standard Add-on capability.

Custom Service can apply when the project involves:

* Custom Platform as Source Platform or Target Platform;
* third-party app, plugin, module, or extension data;
* custom fields;
* outside-system identifiers;
* custom migration logic adjustment;
* tailored Add-on behavior;
* custom Add-ons;
* platform-specific transformation requirements.

Custom Service does not automatically mean every migration action is performed by Next-Cart. Expert-handled execution depends on the customer’s request and the agreed custom scope.

### Continuing or Starting a New Migration <a href="#continuing-or-starting-a-new-migration" id="continuing-or-starting-a-new-migration"></a>

After performing a migration with the purchased service license, customers may access available migration actions for the same migration path. These actions help customers continue migration activity when the source store changes, when configuration should be adjusted, or when the target-store result should be created again with a different setup.

Common available actions include:

* Continue the Migration with the last used configuration;
* Continue the Migration with a new configuration;
* Perform a new migration.

These actions are part of how customers continue working with the purchased service license after migration activity has already taken place. The dedicated article explains when each action is useful and what should be checked before and after using it.

### Recommended Reading Path <a href="#recommended-reading-path" id="recommended-reading-path"></a>

The strongest learning path through Section 4 is:

1. **Next-Cart Migration Service Overview** — understand the service system and main planning concepts.
2. **How the Migration Process Works** — understand the migration journey from early proof to execution and validation.
3. **Demo Migration** — understand how early samples support planning decisions.
4. **Entity Points** — understand how counted migration capacity works.
5. **Entity Points Plan and Migration Pricing** — understand how capacity, service model, Add-ons, and custom scope affect pricing.
6. **Add-ons** — understand focused filtering, mapping, and configuration support.
7. **Next-Cart Service Models** — understand Standard Service, Managed Service, and Custom Service responsibility.
8. **What Custom Service Handles** — understand broader customization and bespoke migration needs.
9. **Choose the Right Service Model** — connect the concepts into a practical service decision.
10. **Continue or Start a New Migration** — understand available migration actions after migration activity has already taken place.

This order moves from orientation to process, proof, capacity, pricing, configuration support, service responsibility, custom scope, decision-making, and later migration actions.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Next-Cart’s E-commerce Platform Migration Service works best when each service concept has a clear role. The migration path defines the service direction. The process explains how the migration moves from preparation to validation. Demo Migration provides early proof. Entity Points and the Entity Points Plan clarify capacity and pricing. Add-ons support focused configuration needs. Service models define responsibility. Custom Service handles requirements beyond standard capability.

Customers should use these concepts together rather than treating migration as a single data-transfer event. A stronger migration decision comes from understanding what the source store contains, what the target store needs to become, who should perform the migration actions, which configuration support is needed, and how the final migrated result will be verified.

For migration questions that involve unclear scope, Add-on requirements, custom data, service responsibility, or target-store readiness, Live Chat can help clarify the next decision before the customer commits to a service path.

### FAQs <a href="#faqs" id="faqs"></a>

**What does Next-Cart’s migration service help customers do?**

Next-Cart’s E-commerce Platform Migration Service helps customers move store data from a Source Platform to a Target Platform through a selected migration path, service license, migration configuration, execution process, and result-validation flow.

**What is a migration path?**

A migration path is the selected one-way direction from the Source Platform to the Target Platform under the purchased service license. It defines the service direction covered by the license.

**What is the difference between a platform and a store?**

A platform is the e-commerce system or supported platform type, such as a Source Platform or Target Platform. A store is the merchant’s actual commerce environment, data source, destination environment, or migrated result.

**Why should customers understand Entity Points before choosing a service model?**

Entity Points help customers understand counted migration capacity. Service model choice also depends on responsibility, Add-ons, custom requirements, and validation needs, so Entity Points should be considered as one part of the broader service decision.

**Are Add-ons the same as Custom Service?**

No. Add-ons are focused optional service features for filtering, mapping, or data configuration. Custom Service handles broader customization, modification, Custom Platform cases, custom logic, and requirements that do not fit standard service capability.

**Does Custom Service always mean Next-Cart performs the migration?**

No. Custom Service means the project requires custom or tailored handling. Expert-handled migration execution depends on the customer’s request and the agreed custom scope.

**Can customers perform migration actions manually under any service model?**

Customers of any service model can access and perform available migration actions manually if they choose. Service models define responsibility and included work, while the customer remains responsible for final result verification and migration outcome.
