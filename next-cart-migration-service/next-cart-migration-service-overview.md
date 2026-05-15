# Next-Cart Migration Service Overview

Next-Cart provides E-commerce Platform Migration Services that help customers move store data from a Source Platform to a Target Platform through a structured service flow. Customers purchase a service license for a selected migration path, then use the service model, migration features, Add-ons, and support options that fit their migration needs.

The selected migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased service license. This helps customers understand the service scope clearly before they move into configuration, execution, review, or launch preparation.

This section explains the service and feature system behind a Next-Cart migration. It is designed for readers who already understand the basic idea of e-commerce migration and now need to understand how Next-Cart structures service responsibility, migration capacity, early proof, pricing, Add-ons, Custom Service, and final service choice.

#### What This Section Helps You Understand <a href="#what-this-section-helps-you-understand" id="what-this-section-helps-you-understand"></a>

The section explains the Next-Cart-specific layer of migration planning.

By the end of this section, readers should understand:

* how the Next-Cart migration process moves from early proof to full execution and final freshness alignment
* how Demo Migration helps reveal whether the migration direction is workable
* how Entity Points measure core migration scope and capacity
* how Entity Points Plan pricing connects to service choice and optional Add-ons
* how Recent Data Migration and Re-Migration support later migration activity within the purchased service
* how Add-ons support focused needs such as filtering, advanced mapping, and data configuration
* how Standard Service, Managed Service, and Custom Service differ
* what broader Custom Service handling covers when standard capability or Standard Add-ons are not enough
* how to use these concepts together when choosing a service path

This section should help customers make better service decisions by understanding how each service concept works, not by treating all migration projects as the same kind of transfer.

#### The Core Parts of Next-Cart’s Migration Service <a href="#the-core-parts-of-next-cart-s-migration-service" id="the-core-parts-of-next-cart-s-migration-service"></a>

A Next-Cart migration can involve several connected service concepts.

The most important ones are:

* **migration path**
* **migration process**
* **Demo Migration**
* **Entity Points**
* **Entity Points Plan**
* **Recent Data Migration**
* **Re-Migration**
* **Add-ons**
* **Standard Service**
* **Managed Service**
* **Custom Service**

Each concept has its own role. Understanding those roles separately prevents common planning mistakes, such as treating a pricing estimate as a migration filter, treating Demo Migration as full validation, or assuming Custom Service always means Next-Cart performs the entire migration process.

#### **Migration Path**&#x20;

The migration path defines the one-way direction of the purchased service license.

A migration path runs from the Source Platform to the Target Platform. For example, a service purchased for Platform A to Platform B should be understood as that selected direction, not as a two-way path between both platforms.

This distinction matters because customers should not assume that a purchased service automatically supports both A to B and B to A. The selected migration path defines the direction covered by the service license.

#### Migration Process <a href="#migration-process" id="migration-process"></a>

The migration process explains how data moves through the Next-Cart service flow at a planning level.

A typical migration path includes early proof, source and target access, configuration, Full Migration, validation, and Recent Data Migration where launch freshness needs to be controlled.

Understanding the process first helps customers interpret later decisions more accurately. Pricing, Add-ons, service responsibility, and Custom Service requirements all become clearer when the customer knows how the migration journey is expected to unfold.

#### Demo Migration <a href="#demo-migration" id="demo-migration"></a>

Demo Migration is the early proof feature.

It helps customers review a limited but meaningful sample before broader execution. Its value is not only showing that data can move. Its value is showing whether representative records still make sense in the Target Platform.

A good Demo Migration can reveal:

* whether products, customers, orders, or content translate cleanly enough
* whether important structure changes in a way the business must review
* whether the customer may need Add-ons
* whether the project shows signs of needing Custom Service
* whether the selected service path still looks realistic

Demo Migration should be treated as evidence for planning, not as a final approval of the full migration.

#### Entity Points <a href="#entity-points" id="entity-points"></a>

Entity Points are Next-Cart’s scope and capacity model.

They measure core migration scope across four data types:

* Product
* Customer
* Order
* Blog

Entity Points help estimate how much migration capacity the project needs. They also help customers understand how capacity is consumed when new data is migrated successfully.

Entity Points do not measure everything about migration difficulty. They do not decide platform compatibility, data-model complexity, Add-on needs, Custom Service requirements, or validation quality. They help explain migration capacity, not the entire migration-planning question.

#### Entity Points Plan and Pricing <a href="#entity-points-plan-and-pricing" id="entity-points-plan-and-pricing"></a>

The Entity Points Plan is the pricing-capacity layer connected to the customer’s estimated migration volume.

Customers enter estimated counts for Product, Customer, Order, and Blog. The system uses those numbers to calculate Entity Points and recommend the closest higher plan.

Pricing also depends on the selected service model and any optional Add-ons.

At a high level:

* Standard Service pricing includes the Entity Points Plan and any purchased Add-ons
* Managed Service pricing includes the Entity Points Plan, any purchased Add-ons, and a service fee
* Custom Service uses a custom quote because it depends on customization work, entity volume, Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, and migration management if included in the final plan

This pricing structure helps customers understand what affects cost before they decide whether the project is customer-led, Next-Cart-led, or customization-driven.

#### Recent Data Migration <a href="#recent-data-migration" id="recent-data-migration"></a>

Recent Data Migration is a migration feature that helps active stores reduce the freshness gap before launch.

It is used when the Source Platform remains active after earlier migration activity and new data continues to appear before launch. It helps sync newly created source-store data into the Target Platform closer to go-live.

Recent Data Migration is not the same as Demo Migration. It is not a replacement for Full Migration. It also does not replace validation. It supports launch freshness, while validation confirms whether the migrated store behaves correctly and is ready for launch.

This distinction matters because an active store may need both freshness control and business-outcome validation before cutover.

#### **Re-Migration**

Re-Migration is a migration feature available within the purchased service.

It can help customers process already migrated records again after adjustment, review, or correction. When the same records have already been successfully migrated and recognized by the service, processing those same records again does not consume additional Entity Points for those same records.

New records are different. If new Product, Customer, Order, or Blog records are created after earlier migration activity, those records consume Entity Points when they are migrated successfully for the first time.

Re-Migration should be understood as part of the purchased service flow, not as a separate, standalone service.

#### Add-ons <a href="#add-ons" id="add-ons"></a>

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome.

The current Standard Add-ons are:

* Data Filter Add-on
* Advanced Data Mapping
* Advanced Data Configure

Standard Add-ons can be purchased with Standard Service, Managed Service, or Custom Service.

A Standard Add-on is suitable when its available settings and supported behavior fit the customer’s requirement. If a Standard Add-on needs modification, it becomes a Tailored Add-on and is handled through Custom Service. If the available Standard Add-ons do not fit the requirement, the customer can request a Custom Add-on, which is also reviewed and quoted through Custom Service.

Add-ons should not be treated as a replacement for the full scope of Custom Service. They are optional service features, while Custom Service covers broader customization, modification, and bespoke migration requirements.

#### Standard Service, Managed Service, and Custom Service <a href="#standard-service-managed-service-and-custom-service" id="standard-service-managed-service-and-custom-service"></a>

Next-Cart’s service models differ by service responsibility and whether the project requires customization or modification work.

**Standard Service** is customer-led. The customer purchases a 1-year service license for the selected migration path and self-performs the migration with any purchased Add-ons.

**Managed Service** is Next-Cart-led execution. The customer purchases a 1-year service license for the selected migration path, and Next-Cart’s technician performs the migration for the customer using standard service capability and any purchased Add-ons.

**Custom Service** is for customization or modification work. It covers requirements that go beyond standard service capability or Standard Add-on capability, including Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, or broader bespoke configuration.

Customers of any service model can access and self-perform the migration process on the Next-Cart website if they want to. The service model determines the service responsibility and included work, not whether the customer has access.

#### Custom Service Requirements <a href="#custom-service-requirements" id="custom-service-requirements"></a>

Custom Service is the broader path for customization, modification, and exclusive handling.

It can include Add-on-related work, but it also covers requirements that are not Add-ons, such as:

* Custom Platform as Source Platform or Target Platform
* third-party app, plugin, module, or extension data
* custom fields
* outside-system identifiers
* custom migration logic adjustment
* platform capability limitations
* bespoke transformation rules

This distinction protects the service path from treating every custom migration need as an Add-on. Add-ons are focused service features. Custom Service is the broader path for requirements that need tailored handling.

#### Recommended Reading Order <a href="#recommended-reading-order" id="recommended-reading-order"></a>

For the clearest path through the section, read the articles in this order:

1. Next-Cart Migration Service Overview
2. Next-Cart Migration Process Explained
3. Demo Migration Explained
4. Entity Points Explained
5. Entity Points Plan and Migration Pricing
6. Recent Data Migration Explained
7. Add-ons Explained
8. Next-Cart Migration Service Models Explained
9. What Custom Service Handles
10. How to Choose the Right Next-Cart Service Model

This order moves from orientation to process, proof, capacity, pricing, freshness, optional features, service definitions, broader custom handling, and final service choice.

#### Conclusion <a href="#conclusion" id="conclusion"></a>

This section explains the Next-Cart service and feature system that supports migration planning, execution, scope measurement, pricing, final freshness, Add-ons, Custom Service, and service-path choice. Each concept has a specific role, so readers can build understanding step by step instead of treating migration service selection as one vague decision.

The strongest use of this section is sequential: first understand the selected migration path and service journey, then review early proof, then interpret scope and pricing, then review freshness, Add-ons, service definitions, Custom Service, and final service choice.

Use this section when you need to understand how Next-Cart’s E-commerce Platform Migration Service works before committing to a plan. If your project already shows signs of selective-scope needs, mapping uncertainty, active-store freshness concerns, Add-on requirements, or broader customization needs, Live Chat can help clarify which service concept and next decision should guide the project.

#### FAQs <a href="#faqs" id="faqs"></a>

**What does this section explain?**

This section explains Next-Cart’s E-commerce Platform Migration Service system, including migration path, migration process, Demo Migration, Entity Points, Entity Points Plan pricing, Recent Data Migration, Re-Migration, Add-ons, service models, Custom Service requirements, and service choice.

**What is a migration path?**

A migration path defines the one-way direction from the Source Platform to the Target Platform under the purchased service license. It should not be understood as a two-way migration path that can be reversed for use.

**Should I read this section before choosing a service model?**

Yes. This section helps explain what each service model means, how Demo Migration supports the decision, how Entity Points affect plan capacity, and when Add-ons or Custom Service may be needed.

**How are Entity Points, pricing, and service choice connected?**

Entity Points measure core migration scope and help determine plan capacity. Pricing also depends on the selected service model and optional Add-ons. Service choice depends on service responsibility and whether customization or modification work is required.

**Are Add-ons the same as Custom Service?**

No. Add-ons are focused, optional service features for filtering, mapping, and data configuration. Custom Service is the broader path for customization, modification, exclusive handling, Custom Platform cases, and requirements beyond standard capability.

**Does Custom Service always mean Next-Cart performs the migration?**

No. Custom Service means customization or modification work is required. Migration management can be included, but it is not automatic unless included in the final purchased plan.

**Can customers self-perform the migration under any service model?**

Yes. Customers of Standard Service, Managed Service, and Custom Service can access and self-perform the migration process on the Next-Cart website if they want to. The service model determines the service responsibility and included work, not whether the customer has access.
