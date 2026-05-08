# Entity Points Plan and Migration Pricing

Next-Cart migration pricing is built from migration capacity, service involvement, optional Add-ons, and any customization work the project requires. The Entity Points Plan is the capacity layer of that pricing model. It determines how many Entity Points the migration plan can support.

This article explains how Entity Points Plan pricing works, how pricing differs across Standard Service, Managed Service, and Custom Service, how Add-ons affect the total, and what happens when a project needs more capacity after purchase.

### What the Entity Points Plan Represents <a href="#what-the-entity-points-plan-represents" id="what-the-entity-points-plan-represents"></a>

An Entity Points Plan sets the migration capacity available to a customer’s license for the selected Source Cart and Target Cart pair.

Entity Points are calculated from four counted data types:

* Product
* Customer
* Order
* Blog

The customer enters estimated quantities for these data types during purchase. The system calculates the estimated Entity Points and recommends the closest higher plan.

The selected plan can support any migrated counted data within its capacity. If the actual migration consumes fewer Entity Points than the plan allows, the remaining points stay available for later eligible use, such as Recent Data Migration or newly included counted records Remigration.

### How the Plan Is Selected <a href="#how-the-plan-is-selected" id="how-the-plan-is-selected"></a>

During purchase, the customer estimates the number of Products, Customers, Orders, and Blog records to migrate. The system uses those inputs to calculate the estimated total Entity Points and select the closest higher Entity Points Plan.

For example, if the entered data creates an estimate of 1,400 Entity Points, the system selects a plan that can support at least 1,400 Entity Points. A plan with a 2,000-point capacity can support that migration and leave remaining capacity available within the plan.

The entered quantity is used for pricing and plan selection. It is not a migration filter. All scanned records are migrated by default unless filtering is configured.

### Entity Points Tier Pricing <a href="#entity-points-tier-pricing" id="entity-points-tier-pricing"></a>

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

Custom Service does not have a fixed price because it depends on the customer’s specific requirements, customization work, service status, Add-ons, and any optional migration management included in the final plan.

### Capacity Above the Global Tier <a href="#capacity-above-the-global-tier" id="capacity-above-the-global-tier"></a>

The Global tier supports up to 1,024,000 Entity Points.

If the migration plan exceeds 1,024,000 Entity Points, additional capacity is charged by service model:

| Service          | Additional capacity fee                         |
| ---------------- | ----------------------------------------------- |
| Standard Service | $50 for every additional 100,000 Entity Points  |
| Managed Service  | $150 for every additional 100,000 Entity Points |
| Custom Service   | Request Custom Quotes                           |

For Custom Service, additional capacity is reviewed as part of the custom quote because the total price depends on the project’s requirements and any customization work involved.

### Pricing by Service Model <a href="#pricing-by-service-model" id="pricing-by-service-model"></a>

The selected service model changes how the total price is built.

#### Standard Service <a href="#standard-service" id="standard-service"></a>

Standard Service is customer-led migration execution.

The pricing structure is:

```
Entity Points Plan + optional Add-ons
```

There is no additional service fee for Standard Service.

#### Managed Service <a href="#managed-service" id="managed-service"></a>

Managed Service is Next-Cart-led migration execution.

The pricing structure is:

```
Entity Points Plan + optional Add-ons + Managed service fee
```

The service fee is automatically included in the total price shown during purchase.

#### Custom Service <a href="#custom-service" id="custom-service"></a>

Custom Service is used when the project requires customization or modification work.

Custom Service pricing is provided as a custom quote. The quote can consider:

* entity volume
* customization tasks
* tailored Add-ons
* custom Add-ons
* migration-tool adjustment
* Custom Cart handling
* third-party app, plugin, module, or extension data
* custom fields or outside-system identifiers
* optional migration management if included in the final plan

Custom Service does not have a fixed price for select because the work may differ significantly from one project to another.

### How Add-ons Affect Pricing <a href="#how-add-ons-affect-pricing" id="how-add-ons-affect-pricing"></a>

Add-ons are optional features customers can purchase across Standard Service, Managed Service, and Custom Service.

The current standard Add-ons are:

* Data Filter Add-on
* Advanced Data Mapping
* Advanced Data Configure

A standard Add-on has a default price. That default price remains consistent across service models. The total price increases when the customer adds optional Add-ons to the plan.

If a standard Add-on needs modification beyond its default capabilities, the work is handled through Custom Service. If the customer has already purchased the standard Add-on and requests a tailored modification to the Add-on, the customer will need to pay the top-up difference between the default Add-on price and the customized Add-on quote.

For example, if a standard Add-on costs $50 and the customized version is quoted at $75, the customer pays the $25 difference.

### Custom Add-ons and Custom Quotes <a href="#custom-add-ons-and-custom-quotes" id="custom-add-ons-and-custom-quotes"></a>

If the available Add-ons do not fit the customer’s requirements, the customer can request a custom Add-on.

A custom Add-on is reviewed and quoted based on the expected result, technical requirements, and complexity. Because custom Add-ons require customization or modification work, they are handled through Custom Service.

This keeps standard Add-ons clear while still allowing Next-Cart to support project-specific needs that the listed Add-ons do not cover.

### What Happens When Actual Data Is Higher Than the Estimate <a href="#what-happens-when-actual-data-is-higher-than-the-estimate" id="what-happens-when-actual-data-is-higher-than-the-estimate"></a>

The customer’s original input is used for pricing and plan selection. It is not a migration limit.

If the actual scan finds more counted records than the customer entered, the migration can continue as long as the selected Entity Points Plan still has enough capacity.

For example:

* the customer purchased Basic+, which supports up to 2,000 Entity Points
* the customer’s original input estimated 1,200 Entity Points
* the actual migration consumes a total of 1,400 Entity Points

The migration can still function normally because it remains within the purchased plan's capacity. The remaining Entity Points stay available for later eligible use.

The plan capacity matters more than the original estimate once the migration begins.

### What Happens When the Plan Capacity Runs Out <a href="#what-happens-when-the-plan-capacity-runs-out" id="what-happens-when-the-plan-capacity-runs-out"></a>

If the migration consumes all available Entity Points before all counted records are migrated, the migration pauses.

The customer can continue by upgrading the Entity Points Plan.

When upgrading, the customer pays only the price difference between the current plan and the higher plan. The customer does not pay the full price of the new plan again.

The added Entity Points are distributed to the corresponding data types based on what the customer enters in the upgrade purchase interface.

### Why Manual Import Is Discouraged After Capacity Runs Out <a href="#why-manual-import-is-discouraged-after-capacity-runs-out" id="why-manual-import-is-discouraged-after-capacity-runs-out"></a>

When the Entity Points Plan runs out, upgrading the plan and continuing through the migration tool is the safer path.

Manual import of the remaining related data can create problems because the migration system may no longer control how records connect to one another. This can weaken relationships between products, customers, orders, categories, reviews, pages, or other supporting structures.

Keeping the continuation inside the migration tool helps preserve record tracking and migration integrity.

### Upgrade and Renewal Are Different <a href="#upgrade-and-renewal-are-different" id="upgrade-and-renewal-are-different"></a>

Upgrading the Entity Points Plan increases migration capacity. It does not renew the service license.

License renewal is a separate purchase decision. When renewing the service license, the customer pays based on the minimum Entity Points Plan in the account record and the final service status of the license, excluding custom work that has already been charged.

Customers can renew using the previous preferences or upgrade both the Entity Points Plan and the service status during renewal.

For example, an expired license that was Standard Service with Basic Plan can be renewed with upgraded preferences, such as Managed Service with Basic+ Plan, if that better fits the customer’s next migration period.

### Pricing Questions to Clarify Before Purchase <a href="#pricing-questions-to-clarify-before-purchase" id="pricing-questions-to-clarify-before-purchase"></a>

Before checkout, customers should clarify several pricing-related questions:

* Are the Product, Customer, Order, and Blog estimates realistic?
* Does the selected Entity Points Plan have enough capacity for likely actual scan results?
* Will the source store continue creating new data before launch?
* Are Add-ons needed for filtering, mapping, or data configuration?
* Does any Add-on need modification beyond default capability?
* Is the project customer-led, Next-Cart-led, or customization-driven?
* Does the project require Custom Service?
* Is future renewal likely to involve the same service status or an upgraded service status?

These questions help customers avoid treating the pricing calculator as only a checkout step. Pricing is also a planning checkpoint.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Entity Points Plan pricing connects migration capacity with the selected service model. Standard Service pricing includes the Entity Points Plan and optional Add-ons. Managed Service pricing includes the Entity Points Plan, optional Add-ons, and the service fee. Custom Service uses custom quotes because the required work depends on the customer’s data volume, customization needs, Add-ons, and optional migration management.

The most important pricing distinction is that the selected plan provides capacity, while the customer’s input is only an estimate. If actual scanned data remains within the plan capacity, the migration can continue. If capacity runs out, the customer can upgrade by paying only the price difference between plans.

Review your estimated Product, Customer, Order, and Blog counts carefully before purchase, then consider Add-ons, service responsibility, Custom Service requirements, and possible source-store growth before launch. If pricing, capacity, or custom quoting is unclear, Live Chat can help clarify the right plan before checkout or upgrade.

### FAQs <a href="#faqs" id="faqs"></a>

#### What is an Entity Points Plan? <a href="#what-is-an-entity-points-plan" id="what-is-an-entity-points-plan"></a>

An Entity Points Plan is the capacity tier that determines how many Entity Points the migration license can support.

#### How is the Entity Points Plan selected? <a href="#how-is-the-entity-points-plan-selected" id="how-is-the-entity-points-plan-selected"></a>

The customer enters estimated counts for Product, Customer, Order, and Blog. The system calculates the Entity Points and recommends the closest higher plan.

#### What is included in Standard Service pricing? <a href="#what-is-included-in-standard-service-pricing" id="what-is-included-in-standard-service-pricing"></a>

Standard Service pricing includes the Entity Points Plan and any optional Add-ons the customer purchases.

#### What is included in Managed Service pricing? <a href="#what-is-included-in-managed-service-pricing" id="what-is-included-in-managed-service-pricing"></a>

Managed Service pricing includes the Entity Points Plan, any optional Add-ons, and the service fee. The service fee is automatically included in the total price.

#### Why does Custom Service show “Request Custom Quotes”? <a href="#why-does-custom-service-show-request-custom-quotes" id="why-does-custom-service-show-request-custom-quotes"></a>

Custom Service depends on customization work, tailored Add-ons, custom Add-ons, migration-tool adjustment, Custom Cart handling, entity volume, and optional migration management. Because the work varies, pricing is quoted individually.

#### What happens if my migration exceeds the Global tier? <a href="#what-happens-if-my-migration-exceeds-the-global-tier" id="what-happens-if-my-migration-exceeds-the-global-tier"></a>

For Standard Service, every additional 100,000 Entity Points above 1,024,000 costs $50. For Managed Service, every additional 100,000 Entity Points costs $150. For Custom Service, the additional capacity is handled through custom quoting.

#### What happens if my actual scan is higher than my original input? <a href="#what-happens-if-my-actual-scan-is-higher-than-my-original-input" id="what-happens-if-my-actual-scan-is-higher-than-my-original-input"></a>

If the selected Entity Points Plan still has enough capacity, migration can continue. If the plan capacity runs out, the migration pauses until the customer upgrades.

#### Do I pay the full price when upgrading the Entity Points Plan? <a href="#do-i-pay-the-full-price-when-upgrading-the-entity-points-plan" id="do-i-pay-the-full-price-when-upgrading-the-entity-points-plan"></a>

No. When upgrading, the customer pays only the price difference between the current plan and the higher plan.

#### Does upgrading the Entity Points Plan renew the service license? <a href="#does-upgrading-the-entity-points-plan-renew-the-service-license" id="does-upgrading-the-entity-points-plan-renew-the-service-license"></a>

No. Upgrading the Entity Points Plan increases migration capacity. It does not renew the service license.

#### How do Add-ons affect price? <a href="#how-do-add-ons-affect-price" id="how-do-add-ons-affect-price"></a>

Standard Add-ons add their default price to the total. Modified Add-ons or custom Add-ons are handled through Custom Service and quoted based on the required work.
