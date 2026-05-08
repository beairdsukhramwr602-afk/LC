# Next-Cart Migration Service Overview

Next-Cart’s migration service is built around a practical goal: helping customers move store data from a Source Cart to a Target Cart while keeping the migrated store usable for the business after launch. The service is not only about transferring records. It is also about helping customers understand scope, migration capacity, early proof, service responsibility, optional Add-ons, and situations that require more tailored handling.

This section explains the service and feature system behind a Next-Cart migration. It is designed for readers who already understand the basic idea of eCommerce migration and now need to know how Next-Cart structures the migration path, how service choices differ, and how supporting features such as Demo Migration, Entity Points, Recent Data Migration, and Add-ons fit together.

It is not a tool manual. Its purpose is to help customers understand the service model before they commit to a plan or move deeper into execution.

### What This Section Helps You Understand

Section 4 explains the Next-Cart-specific layer of migration planning.

By the end of this section, readers should understand:

* how the Next-Cart migration process moves from early proof to full execution and final freshness alignment
* how Demo Migration helps reveal whether the migration direction is workable
* how Entity Points measure core migration scope and capacity
* how Entity Points Plan pricing connects to service choice and optional Add-ons
* how Recent Data Migration helps active stores sync newly created data before launch
* how Standard Service, Managed Service, and Custom Service differ
* how Add-ons support focused needs such as filtering, advanced mapping, and data configuration
* what broader Custom Service handling covers when standard capabilities or standard Add-ons are not enough

This section should help customers make better service decisions by understanding the role of each service feature, not by treating all migration projects as the same kind of transfer.

### Where Section 4 Fits in the Learning Center

Section 4 sits between broader migration planning and platform-specific strategy.

Earlier sections explain what migration means, why scope and risk matter, and how businesses should prepare before execution. Section 4 then explains how Next-Cart’s service system supports that work.

After Section 4, platform strategy and technical deep-dive articles can make more sense because the reader already understands the Next-Cart terms behind service choice, capacity planning, early proof, Add-ons, and Custom Service.

A useful reading path is:

1. understand what the migration must preserve
2. identify the risk and planning questions that matter most
3. use Section 4 to understand how Next-Cart structures the migration service
4. move into platform-specific or technical articles when target-cart details become important
5. return to validation content when the project needs launch-readiness criteria

Section 4 should not replace migration fundamentals, planning strategy, platform evaluation, technical deep dives, or validation guidance. It connects those areas to the Next-Cart service model.

### The Core Parts of Next-Cart’s Migration Service

A Next-Cart migration can involve several connected service concepts.

The most important ones are:

* **migration process**
* **Demo Migration**
* **Entity Points**
* **Entity Points Plan**
* **Recent Data Migration**
* **Standard Service**
* **Managed Service**
* **Custom Service**
* **Add-ons**

Each concept has its own role. Understanding those roles separately prevents common planning mistakes, such as treating a pricing estimate as a migration filter, treating Demo Migration as full validation, or assuming Custom Service always means Next-Cart performs the entire migration process.

### Migration Process

The migration process explains how data moves through the Next-Cart system at a planning level.

A typical migration path includes early proof, source and target access, configuration, Full Migration, validation, and Recent Data Migration where launch freshness needs to be controlled.

The process article in this section explains the fixed entity migration sequence and the default rule that all scanned records are migrated unless filtering is specifically configured.

This topic comes early because customers need to understand the migration journey before pricing, service models, Add-ons, or Custom Service decisions can be interpreted correctly.

### Demo Migration

Demo Migration is the early proof feature.

It helps customers review a limited but meaningful sample before broader execution. Its value is not only showing that data can move. Its value is showing whether representative records still make sense in the Target Cart.

A good Demo Migration can reveal:

* whether products, customers, orders, or content translate cleanly enough
* whether important structure changes in a way the business must review
* whether the customer may need Add-ons
* whether the project shows signs of needing Custom Service
* whether the selected service path still looks realistic

Demo Migration should be treated as evidence for planning, not as a final approval of the full migration.

### Entity Points

Entity Points are Next-Cart’s scope and capacity model.

They measure core migration scope across four counted data types:

* Product
* Customer
* Order
* Blog

Entity Points help estimate how much migration capacity the project needs. They also help customers understand how capacity is consumed when new data is migrated successfully.

Entity Points do not measure everything about migration difficulty. They do not decide platform compatibility, data-model complexity, Add-on needs, Custom Service requirements, or validation quality. They answer the capacity question, not the entire migration-planning question.

### Entity Points Plan and Pricing

The Entity Points Plan is the pricing-capacity layer connected to the customer’s estimated migration volume.

Customers enter estimated counts for Product, Customer, Order, and Blog. The system uses those numbers to calculate Entity Points and recommend the closest higher plan.

Pricing also depends on the selected service model and any optional Add-ons.

At a high level:

* Standard Service pricing includes the Entity Points Plan and any purchased Add-ons
* Managed Service pricing includes the Entity Points Plan, any purchased Add-ons, and a service fee
* Custom Service uses a custom quote because it depends on customization work, entity volume, tailored or custom Add-ons, migration-tool adjustment, and optional migration management if included

The pricing article in this section should help customers understand what affects price without turning the Learning Center into a price-table page.

### Recent Data Migration

Recent Data Migration is the final freshness feature.

It is used when the Source Cart remains active after earlier migration activity and new data continues to appear before launch. It helps sync newly created source-store data into the Target Cart closer to go-live.

Recent Data Migration is not the same as Demo Migration. It is not a replacement for Full Migration. It also does not replace validation. It supports launch freshness, while validation confirms whether the target store behaves correctly and is ready for launch.

This distinction matters because an active store may need both freshness control and business-outcome validation before cutover.

### Standard Service, Managed Service, and Custom Service

Next-Cart’s service models differ by execution responsibility and customization need.

**Standard Service** is customer-led. The customer uses the migration license and migration tool for the selected platform pair, with support and any purchased Add-ons.

**Managed Service** is Next-Cart-led execution. Next-Cart performs the migration process for the customer using default migration-tool capabilities and any purchased Add-ons.

**Custom Service** is for customization or modification work. It covers requirements that go beyond default tool capability or standard Add-on capability, including tailored Add-ons, custom Add-ons, Custom Cart handling, migration-tool adjustment, or broader bespoke configuration.

Custom Service does not automatically mean Next-Cart performs the full migration process unless migration management is included in the final plan. This distinction is important because customization work and managed execution are related but separate decisions.

### Add-ons

Add-ons are optional features that help customers address focused migration needs.

The current standard Add-ons are:

* Data Filter Add-on
* Advanced Data Mapping
* Advanced Data Configure

Add-ons are available across Standard Service, Managed Service, and Custom Service. They are useful when the customer needs more control over filtering selected data, aligning source-to-target mapping, or configuring data values before migration.

Add-ons should not be treated as a replacement for the full scope of Custom Service. If an available Add-on needs modification beyond default capability, or if the customer needs a custom Add-on that is not currently available, that work is handled through Custom Service.

### Custom Service Requirements

Custom Service is the broader path for customization, modification, and exclusive handling.

It can include Add-on-related work, but it also covers requirements that are not Add-ons, such as:

* Custom Cart as source or target
* third-party app, plugin, module, or extension data
* custom fields
* outside-system identifiers
* migration-tool modification
* platform capability limitations
* bespoke transformation rules

This distinction protects the Learning Center from treating every custom migration need as an Add-on. Add-ons are focused features. Custom Service is the broader service path for requirements that need tailored handling.

### How to Use This Section

Readers do not need to memorize every service concept before moving forward. The best approach is to use this section based on the decision in front of them.

If the reader needs to understand the overall journey, start with the migration process article.

If the reader needs early evidence before committing to scope or service choice, read the Demo Migration article.

If the reader is estimating size, price, or plan capacity, read Entity Points Explained and Entity Points Plan and Migration Pricing.

If the reader’s source store will remain active before launch, read Recent Data Migration Explained.

If the reader needs to compare who performs the work and when Custom Service applies, read the service model articles.

If the reader needs filtering, mapping, or data configuration support, read Add-ons Explained.

If the reader has Custom Cart, third-party logic, custom fields, outside-system identifiers, or broader bespoke requirements, read What Custom Service Handles.

### Conclusion

Section 4 explains the Next-Cart service and feature system that supports migration planning, execution, scope measurement, pricing, final freshness, and service-path choice. Each article in the section owns a different part of that system, so readers can build understanding step by step instead of treating migration service selection as one vague decision.

The strongest use of this section is sequential: first understand the service journey, then review early proof, then interpret scope and pricing, then decide which service model, Add-ons, or Custom Service requirements fit the project.

Use this section when you need to understand how Next-Cart’s migration service works before committing to a plan. If your project already shows signs of selective-scope needs, mapping uncertainty, active-store freshness concerns, Add-on requirements, or broader customization needs, Live Chat can help clarify which article and service path should guide the next decision.

### FAQs

#### What does this section explain?

This section explains Next-Cart’s service and feature system, including the migration process, Demo Migration, Entity Points, Entity Points Plan pricing, Recent Data Migration, service models, Add-ons, and Custom Service requirements.

#### Should I read this section before choosing a service model?

Yes. This section helps explain what each service model means, how Demo Migration supports the decision, how Entity Points affect plan capacity, and when Add-ons or Custom Service may be needed.

#### How are Entity Points, pricing, and service choice connected?

Entity Points measure core migration scope and help determine plan capacity. Pricing also depends on the selected service model and optional Add-ons. Service choice depends on execution responsibility and whether customization or modification work is required.

#### Are Add-ons the same as Custom Service?

No. Add-ons are focused, optional features for filtering, mapping, and data configuration. Custom Service is the broader path for customization, modification, exclusive handling, Custom Cart cases, and requirements beyond the default capability.

#### Does Custom Service always mean Next-Cart performs the migration?

No. Custom Service means customization or modification work is required. Migration management can be included, but it is not automatic unless included in the final purchased plan.
