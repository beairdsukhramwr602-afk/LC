# Entity Points Plan and Migration Pricing

Next-Cart migration pricing combines counted data capacity with the service responsibility and optional service features needed for the selected migration path. The Entity Points Plan defines the maximum migration capacity supported by the purchased service license. The selected service model, Add-ons, and any Custom Service requirements determine how the final price should be understood beyond capacity alone.

Pricing is easier to evaluate when four decisions are separated clearly:

* how much counted data the source store is expected to migrate;
* which Entity Points Plan provides enough capacity for that counted scope;
* whether the migration should be handled through Standard Service, Managed Service, or Custom Service;
* whether Add-ons or custom handling are needed for filtering, mapping, configuration, platform differences, or project-specific requirements.

A store with modest data may still need Managed Service or Custom Service when the migration requires expert handling, custom logic, or unusual data interpretation. A store with large amounts of data may remain operationally straightforward when the Source Platform, Target Platform, and store data structure are well supported.

### What the Entity Points Plan Represents  <a href="#what-the-entity-points-plan-represents" id="what-the-entity-points-plan-represents"></a>

An Entity Points Plan sets the counted migration capacity available under the purchased service license for one migration path. The migration path defines the one-way direction from the Source Platform to the Target Platform. The Entity Points Plan defines the counted capacity available for Product, Customer, Order, and Blog Posts data within that path.

Customers enter estimated quantities for those counted data types during purchase. Next-Cart uses those estimates to calculate the expected Entity Points requirement and help identify a suitable plan.

The selected plan can support the actual counted migration consumption up to its capacity. This means the selected plan matters more than the exact estimate once migration execution reveals the actual counted data volume.

Entity Points Plan capacity should not be confused with migration filtering. Purchase estimates help calculate capacity and price. They do not automatically limit which scanned records are migrated. If the customer wants to migrate only selected records, that requirement should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering capability is not enough.

### How Estimate and Plan Capacity Shape the Purchase <a href="#how-estimate-and-plan-capacity-shape-the-purchase" id="how-estimate-and-plan-capacity-shape-the-purchase"></a>

Upon purchase interface, customers estimate the quantities of Product, Customer, Order, and Blog Posts. Those inputs are converted into Entity Points using the coefficients for the counted data and allocated to the corresponding counted data types.

Assume a customer enters the following source-store estimates:

| Counted data type | Estimated count | Coefficient | Estimated Entity Points |
| ----------------- | --------------- | ----------- | ----------------------- |
| Product           | 200             | 1.0         | 200                     |
| Customer          | 200             | 0.5         | 100                     |
| Order             | 150             | 0.8         | 120                     |
| Blog Posts        | 100             | 0.6         | 60                      |
| **Total**         |                 |             | **480**                 |

The estimated requirement is:

```
200 + 100 + 120 + 60 = 480 Entity Points
```

If the customer chooses a plan with 1,000 Entity Points of capacity, the estimated 480 Entity Points are covered and the remaining 520 Entity Points stay available under the purchased service license.

| Purchase layer                | Entity Points |
| ----------------------------- | ------------- |
| Estimated counted requirement | 480           |
| Selected plan capacity        | 1,000         |
| Remaining available capacity  | 520           |

This remaining capacity can support actual counted data that exceeds the estimate, newly migrated counted records in later migration activity, or other eligible use within the service license. It does not turn the original purchase estimate into a migration filter.

The purchase decision should therefore balance estimate accuracy with practical headroom. A plan that only barely covers the entered estimate may be cheaper at checkout, but it may be less flexible if the source store contains more counted records than expected or continues creating new counted data before launch.

### Entity Points Tier Pricing  <a href="#entity-points-tier-pricing" id="entity-points-tier-pricing"></a>

The Entity Points Plan uses tiered capacity. Each tier supports migration up to a defined Entity Points limit.

| Tier        | Entity Points   | Standard Service | Managed Service | Custom Service        |
| ----------- | --------------- | ---------------- | --------------- | --------------------- |
| Starter     | Up to 500       | $39.00           | $150.00         | Request Custom Quotes |
| Basic       | Up to 1,000     | $59.00           | $250.00         | Request Custom Quotes |
| Basic+      | Up to 2,000     | $89.00           | $350.00         | Request Custom Quotes |
| Growth      | Up to 4,000     | $119.00          | $450.00         | Request Custom Quotes |
| Growth+     | Up to 8,000     | $149.00          | $550.00         | Request Custom Quotes |
| Pro         | Up to 16,000    | $199.00          | $650.00         | Request Custom Quotes |
| Pro+        | Up to 32,000    | $269.00          | $750.00         | Request Custom Quotes |
| Business    | Up to 64,000    | $349.00          | $850.00         | Request Custom Quotes |
| Advanced    | Up to 128,000   | $449.00          | $950.00         | Request Custom Quotes |
| Enterprise  | Up to 256,000   | $569.00          | $1,050.00       | Request Custom Quotes |
| Enterprise+ | Up to 512,000   | $699.00          | $1,500.00       | Request Custom Quotes |
| Global      | Up to 1,024,000 | $949.00          | $2,250.00       | Request Custom Quotes |

Custom Service is quoted individually because the final price depends on the customer’s requirements, customization work, service status, Add-ons, custom handling, and any expert-handled migration scope included in the final plan.

### Capacity Above the Global Tier  <a href="#capacity-above-the-global-tier" id="capacity-above-the-global-tier"></a>

If the migration plan exceeds 1,024,000 Entity Points, additional capacity is charged by service model:

| Service          | Additional capacity fee                         |
| ---------------- | ----------------------------------------------- |
| Standard Service | $50 for every additional 100,000 Entity Points  |
| Managed Service  | $150 for every additional 100,000 Entity Points |
| Custom Service   | Request Custom Quotes                           |

For Custom Service, additional capacity is reviewed as part of the custom quote because large data volume may interact with custom fields, third-party data, Custom Platform handling, bespoke mapping, custom migration logic, or expert-handled execution requirements.

### How Service Models Affect Pricing <a href="#how-service-models-affect-pricing" id="how-service-models-affect-pricing"></a>

The Entity Points Plan provides the counted capacity layer. The service model determines how responsibility and included work affect the total price.

| Service model    | Pricing structure                                           | Best understood as                                                                                                   |
| ---------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Standard Service | Entity Points Plan + optional Add-ons                       | Customer-led migration execution for supported paths and standard requirements.                                      |
| Managed Service  | Entity Points Plan + optional Add-ons + Managed Service fee | Next-Cart-led execution for customers who want expert handling within supported service capability.                  |
| Custom Service   | Custom quote                                                | Custom-scoped work for requirements that need customization, modification, bespoke handling, or Expert Handle scope. |

Customers on any service model can access and manually perform available migration actions if they choose. The selected service model determines responsibility, expert handling, and service scope, not whether the customer can access the purchased service license.

With any service model, the customer remains responsible for final result verification and migration outcome.

#### Standard Service Pricing <a href="#standard-service-pricing" id="standard-service-pricing"></a>

Standard Service pricing includes the Entity Points Plan and any optional Add-ons selected by the customer.

```
Entity Points Plan + optional Add-ons
```

Standard Service is customer-led. The customer performs migration actions under the purchased service license and verifies the final migration outcome. This model is most suitable when the migration path is supported, the store data is predictable, and the customer can manage configuration, execution, and result review.

#### Managed Service Pricing <a href="#managed-service-pricing" id="managed-service-pricing"></a>

Managed Service pricing includes the Entity Points Plan, optional Add-ons, and the Managed Service fee.

```
Entity Points Plan + optional Add-ons + Managed Service fee
```

Managed Service is expert-led based on the customer’s request and agreed service scope. It is useful when the customer wants Next-Cart experts to perform migration actions, coordinate execution, and reduce operational effort during the migration process.

Managed Service does not remove the customer’s responsibility for final result verification. The customer still needs to confirm whether the target store meets the intended business expectations, launch requirements, and migration outcome.

#### Custom Service Pricing <a href="#custom-service-pricing" id="custom-service-pricing"></a>

Custom Service is quoted individually because the required work can differ significantly across projects.

A custom quote may consider:

* counted data volume;
* Custom Platform handling;
* custom fields, app data, extension data, plugin data, or third-party records;
* custom migration logic adjustment;
* Tailored Add-ons;
* Custom Add-ons;
* unsupported or unusual source-store structures;
* outside-system identifiers or bespoke mapping requirements;
* Expert Handle scope when expert-led execution is included in the agreed plan.

Custom Service without the Expert Handle option remains customer-led for migration actions. Custom Service with the Expert Handle option allows Next-Cart experts to perform migration actions based on the customer’s request and agreed scope. In both cases, the customer remains responsible for final result verification and migration outcome.

### How Add-ons Affect Pricing  <a href="#how-add-ons-affect-pricing" id="how-add-ons-affect-pricing"></a>

Add-ons are optional service features that support filtering, mapping, or data configuration needs. They can be used with Standard Service, Managed Service, or Custom Service when they fit the project requirement.

The current Standard Add-ons are:

* Data Filter Add-on;
* Advanced Data Mapping;
* Advanced Data Configure.

A Standard Add-on has a default price. If the available Standard Add-on behavior is enough, the default Add-on price is added to the service price.

If a Standard Add-on needs modification beyond available settings and supported behavior, the work is handled through Custom Service as a Tailored Add-on. If the customer has already purchased the Standard Add-on and later requests a tailored modification, the customer pays only the top-up difference between the default Add-on price and the customized Add-on quote.

For example, if a Standard Add-on costs $50 and the Tailored Add-on version is quoted at $75, the customer pays the $25 difference.

#### Custom Add-ons and Custom Quotes <a href="#custom-add-ons-and-custom-quotes" id="custom-add-ons-and-custom-quotes"></a>

A Custom Add-on is used when the available Standard Add-ons do not cover the customer’s required outcome.

Custom Add-ons are reviewed and quoted based on expected result, technical requirements, data structure, and complexity. Because Custom Add-ons require customization or modification work, they are handled through Custom Service.

This keeps Standard Add-ons clear while still allowing Next-Cart to support project-specific filtering, mapping, or configuration needs that standard settings do not cover.

### Upgrading the Entity Points Plan and Renewing the Service License <a href="#upgrading-the-entity-points-plan-and-renewing-the-service-license" id="upgrading-the-entity-points-plan-and-renewing-the-service-license"></a>

Upgrading the Entity Points Plan and renewing the service license are separate decisions. They can sometimes appear close together in a customer’s planning timeline, but they solve different needs.

An Entity Points Plan upgrade increases the counted capacity under the purchased service license. It is relevant when the selected plan no longer provides enough capacity for the data the customer needs to migrate. The upgrade keeps the customer within the purchased service process instead of forcing disconnected manual handling for remaining related data.

When upgrading, the customer pays only the price difference between the current plan and the higher plan, not the full price of the higher plan again. The added Entity Points are distributed to the corresponding counted data types based on what the customer enters in the plan-upgrade purchase interface.

For example, a customer may originally choose a Basic plan and later upgrade to Basic+ if the source store contains more counted records than expected. The upgrade increases available capacity for the service license, while the migration path and service context remain tied to the purchased license.

Renewal is different. License renewal extends or restores the service license period. It does not simply add Entity Points to the current plan. When renewing the service license, the customer pays based on the minimum Entity Points Plan in the account record and the final service status of the license, excluding custom work that has already been charged.

Customers can renew using previous preferences or upgrade both the Entity Points Plan and service status during renewal. For example, an expired license that was Standard Service with the Basic plan can be renewed with upgraded preferences, such as Managed Service with the Basic+ plan, if that better fits the customer’s next migration period.

| Decision                          | What it changes                                                              | What it does not automatically change                                                              | Pricing meaning                                                                                                                                     |
| --------------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Entity Points Plan upgrade        | Increases counted capacity under the service license.                        | Does not renew the service license period.                                                         | Customer pays the difference between the current plan and the higher plan.                                                                          |
| Service license renewal           | Extends or restores the service license period.                              | Does not automatically mean the customer is only adding capacity.                                  | Customer pays based on the minimum Entity Points Plan in the account record and the final service status, excluding previously charged custom work. |
| Renewal with upgraded preferences | Extends or restores the service license while changing selected preferences. | Does not re-charge custom work that has already been charged, unless new custom work is requested. | Customer can renew with an upgraded Entity Points Plan, upgraded service status, or both when suitable.                                             |

The practical decision is whether the customer needs more capacity during an active service period, more time or renewed access to the service license, or a changed service preference for the next migration period. If both capacity and service period need to change, renewal with upgraded preferences may be more suitable than treating the situation as a capacity-only question.

### Pricing Questions to Clarify Before Purchase <a href="#pricing-questions-to-clarify-before-purchase" id="pricing-questions-to-clarify-before-purchase"></a>

Before checkout, customers should clarify several pricing-related questions:

* Are the Product, Customer, Order, and Blog Posts estimates realistic?
* Does the selected Entity Points Plan have enough capacity for likely actual migration consumption?
* Will the source store continue creating new counted data before launch?
* Are Add-ons needed for filtering, mapping, or data configuration?
* Does any Add-on need modification beyond available settings and supported behavior?
* Is the migration customer-led, expert-led, or custom-scoped?
* Does the project require Custom Service?
* Is future license renewal likely to use the same service status or an upgraded service status?

These questions help customers treat pricing as a planning checkpoint, not only a checkout calculation.

### Conclusion  <a href="#conclusion" id="conclusion"></a>

Entity Points Plan pricing connects counted migration capacity with the selected service model, Add-ons, and any custom work required for the migration path. Standard Service includes the Entity Points Plan and optional Add-ons. Managed Service includes the Entity Points Plan, optional Add-ons, and the Managed Service fee. Custom Service uses custom quotes because the required work depends on data volume, customization needs, Add-ons, Expert Handle scope, and project-specific requirements.

The selected plan provides capacity, while the customer’s input is an estimate. If actual counted migration consumption remains within the selected plan capacity, migration can continue within that plan. If capacity runs out, the customer can upgrade by paying only the price difference between plans.

Review Product, Customer, Order, and Blog Posts estimates carefully before purchase. Then consider Add-ons, service responsibility, Custom Service requirements, source-store growth, and future license needs before checkout. If pricing, capacity, or custom quoting is unclear, Live Chat can help clarify the right plan before purchase or upgrade.

### FAQs  <a href="#faqs" id="faqs"></a>

**What is an Entity Points Plan?**

An Entity Points Plan is the capacity tier that determines how many Entity Points the purchased migration service license can support for counted data.

**How is the Entity Points Plan selected?**

Customers enter estimated counts for Product, Customer, Order, and Blog Posts. Next-Cart uses those estimates to calculate Entity Points and identify a suitable plan.

**What is included in Standard Service pricing?**

Standard Service pricing includes the Entity Points Plan and any optional Add-ons the customer purchases.

**What is included in Managed Service pricing?**

Managed Service pricing includes the Entity Points Plan, any optional Add-ons, and the Managed Service fee.

**Why does Custom Service require a custom quote?**

Custom Service depends on the customer’s data volume, customization needs, Tailored Add-ons, Custom Add-ons, custom migration logic, Custom Platform handling, and Expert Handle scope when included. Because the work varies, pricing is quoted individually.

**What happens if my migration exceeds the Global tier?**

For Standard Service, every additional 100,000 Entity Points above 1,024,000 costs $50. For Managed Service, every additional 100,000 Entity Points costs $150. For Custom Service, additional capacity is handled through custom quoting.

**Do I pay the full price when upgrading the Entity Points Plan?**

No. When upgrading, the customer pays only the price difference between the current plan and the higher plan.

**Does upgrading the Entity Points Plan renew the service license?**

No. Upgrading the Entity Points Plan increases counted capacity. License renewal is a separate purchase decision.

**How is service license renewal priced?**

When renewing the service license, the customer pays based on the minimum Entity Points Plan in the account record and the final service status of the license, excluding custom work that has already been charged.

**Can I renew with upgraded preferences?**

Yes. Customers can renew using previous preferences or upgrade both the Entity Points Plan and service status during renewal when that better fits the next migration period.

**Do entered quantities limit what gets migrated?**

No. Entered quantities support pricing and plan selection. They are not migration filters. Selective migration should be planned through the Data Filter Add-on or reviewed as a custom filtering requirement when standard filtering is not enough.
