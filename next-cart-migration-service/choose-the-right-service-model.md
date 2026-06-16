# Choose the Right Service Model

Choosing the right Next-Cart service model means deciding how the migration should be handled, who should perform the migration actions, and whether the expected target-store result requires custom work. Price is part of the decision, but the safest choice starts with the migration requirement itself.

A strong service choice uses evidence from the earlier planning steps. The migration process shows what work must be completed, Demo Migration gives early proof, Entity Points clarify counted capacity, the Entity Points Plan defines pricing capacity, Add-ons support focused filtering or mapping needs, and Custom Service covers requirements that need tailored handling.

### The Core Service Choice <a href="#the-core-service-choice" id="the-core-service-choice"></a>

The service model decision should answer three questions:

| Decision question                                          | Why it matters                                                                                                                            |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Can the migration stay within standard service capability? | Supported, predictable requirements may not need Custom Service.                                                                          |
| Who should perform the migration actions?                  | The project may be customer-led or Next-Cart-led depending on the service model and agreed scope.                                         |
| Does the expected result require custom work?              | Custom Platform handling, tailored Add-ons, Custom Add-ons, custom fields, third-party data, or bespoke logic can require Custom Service. |

These questions should be separated. A customer may want Next-Cart to perform a standard migration without needing Custom Service. Another customer may need Custom Service because of custom data requirements while still performing available migration actions manually.

### Quick Service Direction Table <a href="#quick-service-direction-table" id="quick-service-direction-table"></a>

| Situation                                                                                                                    | Most suitable direction                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| The migration path is supported, requirements are predictable, and the customer can perform migration actions                | Standard Service                                                                                   |
| The migration path is supported, requirements are predictable, and the customer wants Next-Cart to perform migration actions | Managed Service                                                                                    |
| A Standard Add-on solves a focused filtering, mapping, or configuration need                                                 | Standard Service or Managed Service, depending on execution responsibility                         |
| A Standard Add-on needs modification beyond available settings and supported behavior                                        | Custom Service                                                                                     |
| A Custom Add-on is needed                                                                                                    | Custom Service                                                                                     |
| A Custom Platform is involved as Source Platform, Target Platform, or both                                                   | Custom Service                                                                                     |
| Custom fields, third-party data, outside-system identifiers, or bespoke migration logic need tailored handling               | Custom Service                                                                                     |
| Custom work is needed, but the customer wants to perform available migration actions manually                                | Custom Service without Expert Handle, unless expert-handled execution is added to the agreed scope |
| Custom work is needed and the customer wants Next-Cart to perform migration actions                                          | Custom Service with Expert Handle when included in the agreed scope                                |

This table should be used as a direction-setting framework. The final service choice should reflect the source store, target store, migration path, Add-ons, Custom Service requirements, service responsibility, and validation expectations.

### Choose Standard Service When the Migration Is Predictable and Customer-Led <a href="#choose-standard-service-when-the-migration-is-predictable-and-customer-led" id="choose-standard-service-when-the-migration-is-predictable-and-customer-led"></a>

Standard Service fits supported migration paths where the customer can perform the migration actions and the expected result can be handled through standard service capability.

It is usually suitable when:

* the Source Platform and Target Platform are supported for the selected migration path;
* the customer can prepare the source store and target store;
* the customer can configure, execute, and monitor migration activity;
* Demo Migration does not reveal serious data-meaning or service-scope concerns;
* any required Add-ons fit available Standard Add-on behavior;
* no Custom Platform, Custom Add-on, tailored Add-on, custom migration logic, or bespoke data handling is required;
* the customer can review the target-store result and confirm the migration outcome.

Standard Service does not mean the customer receives no help. It means the customer leads execution while Next-Cart support remains available for clarification and service-related questions.

### Choose Managed Service When the Migration Is Standard but Expert-Led Execution Is Preferred <a href="#choose-managed-service-when-the-migration-is-standard-but-expert-led-execution-is-preferred" id="choose-managed-service-when-the-migration-is-standard-but-expert-led-execution-is-preferred"></a>

Managed Service fits supported migration paths where the expected result can stay within standard service capability, but the customer wants Next-Cart experts to perform migration actions based on the customer’s request and agreed service scope.

It is usually suitable when:

* the migration path is supported;
* the source-store data and target-store expectation do not require custom work;
* the customer wants to reduce internal execution workload;
* Standard Add-ons are enough for focused filtering, mapping, or data configuration needs;
* the customer wants Next-Cart to coordinate migration execution;
* the customer can still review the target-store result and confirm the migration outcome.

Managed Service is about execution responsibility. It is not a substitute for Custom Service when the project requires customization, Custom Platform handling, modified Add-ons, Custom Add-ons, custom fields, third-party data, or bespoke migration logic.

### Choose Custom Service When the Expected Result Requires Tailored Handling <a href="#choose-custom-service-when-the-expected-result-requires-tailored-handling" id="choose-custom-service-when-the-expected-result-requires-tailored-handling"></a>

Custom Service is required when the expected target-store result cannot be achieved through standard service capability and available Standard Add-ons alone.

It is usually needed when the project involves:

* Custom Platform handling as Source Platform, Target Platform, or both;
* Tailored Add-ons or Custom Add-ons;
* Standard Add-on modification beyond available settings and supported behavior;
* custom fields or non-standard source-store structures;
* app, plugin, module, extension, or third-party data;
* outside-system identifiers used by ERP, CRM, fulfillment, accounting, reporting, or other business systems;
* custom migration logic adjustment;
* bespoke transformation or configuration rules;
* target-store requirements that need review against Target Platform capability.

Custom Service should be chosen because the project needs custom-scoped work, not simply because the store is large. A high-volume migration can still fit Standard Service or Managed Service if the data is supported, the requirement is predictable, and the selected service model matches execution responsibility.

### Decide Whether Custom Service Needs Expert Handle <a href="#decide-whether-custom-service-needs-expert-handle" id="decide-whether-custom-service-needs-expert-handle"></a>

Custom Service and Expert Handle are related, but they are not the same decision.

Custom Service defines the need for customization, modification, bespoke handling, or custom-scoped review. Expert Handle defines whether Next-Cart experts perform migration actions as part of the agreed Custom Service scope.

| Custom Service situation                                                                      | Execution implication                                                                       |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Custom work is needed, and the customer wants to perform available migration actions manually | Custom Service can focus on the custom work without Expert Handle.                          |
| Custom work is needed, and the customer wants Next-Cart to perform migration actions          | Expert Handle should be included in the agreed Custom Service scope.                        |
| Custom work is needed, but the execution responsibility is unclear                            | The final plan should clarify whether the customer or Next-Cart performs migration actions. |

This distinction helps avoid two common mistakes: assuming every Custom Service project is fully expert-led, or assuming customer-led execution means custom requirements can stay outside Custom Service.

### Use Demo Migration as Service-Fit Evidence <a href="#use-demo-migration-as-service-fit-evidence" id="use-demo-migration-as-service-fit-evidence"></a>

Demo Migration helps reveal whether the service model expectation is realistic.

A predictable Demo Migration result may support Standard Service when the customer can perform the migration actions and validate the target-store result. A predictable result can also support Managed Service when the customer wants Next-Cart to handle execution.

A Demo Migration result that exposes Add-on limitations, Custom Platform issues, custom fields, third-party data gaps, target-store behavior concerns, or business-critical data differences should be reviewed for Custom Service.

The strongest Demo Migration review looks beyond whether records appear. It checks whether the migrated sample preserves business meaning, supports target-store use, and reveals any requirement that should change the service direction before broader migration activity.

### Use Entity Points for Capacity, Not Service Fit Alone <a href="#use-entity-points-for-capacity-not-service-fit-alone" id="use-entity-points-for-capacity-not-service-fit-alone"></a>

Entity Points help estimate counted migration capacity for Product, Customer, Order, and Blog Posts. They support plan selection and pricing, but they do not decide the service model by themselves.

A large store can still fit Standard Service if the migration path is supported, the customer can perform migration actions, and the expected result does not require custom work. A smaller store can require Custom Service if it depends on Custom Platform handling, custom fields, modified Add-ons, Custom Add-ons, third-party data, or bespoke migration logic.

Entity Points answer a capacity question. Service model selection answers a responsibility and requirement question.

### Use Add-ons When the Need Is Focused <a href="#use-add-ons-when-the-need-is-focused" id="use-add-ons-when-the-need-is-focused"></a>

Add-ons are useful when the migration requirement is focused and can be handled through available service features.

Standard Add-ons can support needs such as:

* filtering selected records through the Data Filter Add-on;
* aligning source and target values through Advanced Data Mapping;
* adjusting selected data values through Advanced Data Configure.

Using a Standard Add-on within available settings and supported behavior does not make the service Custom. The service model still depends on whether the migration should be customer-led or Next-Cart-led.

The project becomes a Custom Service case when the Add-on needs modification beyond available behavior or when the customer needs a Custom Add-on that is not covered by the available Standard Add-ons.

### Check Internal Readiness Before Choosing <a href="#check-internal-readiness-before-choosing" id="check-internal-readiness-before-choosing"></a>

A technically standard migration can still be difficult for a customer to manage internally.

Before choosing Standard Service, customers should consider whether their team can:

* prepare source-store and target-store access;
* configure migration settings confidently;
* interpret Demo Migration results;
* decide whether Add-ons are needed;
* monitor migration execution;
* review products, customers, orders, content, relationships, and settings;
* validate the target-store result before launch or business use;
* decide whether later migration actions are needed after earlier migration activity.

If those responsibilities are too heavy, Managed Service may be safer even when the migration does not require Custom Service. If the team can handle execution but the data requires tailored handling, Custom Service may be needed without Expert Handle.

### Practical Service-Fit Scenarios <a href="#practical-service-fit-scenarios" id="practical-service-fit-scenarios"></a>

#### Scenario 1: Predictable migration with a capable internal team <a href="#scenario-1-predictable-migration-with-a-capable-internal-team" id="scenario-1-predictable-migration-with-a-capable-internal-team"></a>

The customer understands the migration process, can perform available migration actions, and the Demo Migration result looks predictable. Required Add-ons fit available Standard Add-on behavior.

**Likely fit:** Standard Service.

#### Scenario 2: Predictable migration with limited execution capacity <a href="#scenario-2-predictable-migration-with-limited-execution-capacity" id="scenario-2-predictable-migration-with-limited-execution-capacity"></a>

The migration appears feasible through standard service capability, but the customer wants Next-Cart to perform migration actions.

**Likely fit:** Managed Service.

#### Scenario 3: Standard Add-on is enough <a href="#scenario-3-standard-add-on-is-enough" id="scenario-3-standard-add-on-is-enough"></a>

The customer needs filtering, mapping, or data configuration that fits a Standard Add-on’s available settings and supported behavior.

**Likely fit:** Standard Service or Managed Service, depending on who should perform migration actions.

#### Scenario 4: Add-on needs modification <a href="#scenario-4-add-on-needs-modification" id="scenario-4-add-on-needs-modification"></a>

The customer needs filtering, mapping, or data-configuration behavior that exceeds Standard Add-on capability.

**Required fit:** Custom Service.

#### Scenario 5: Custom Platform is involved <a href="#scenario-5-custom-platform-is-involved" id="scenario-5-custom-platform-is-involved"></a>

The Source Platform or Target Platform is a Custom Platform and the migration requires interpretation beyond the supported-platform model.

**Required fit:** Custom Service.

#### Scenario 6: Custom work with customer-led execution <a href="#scenario-6-custom-work-with-customer-led-execution" id="scenario-6-custom-work-with-customer-led-execution"></a>

The customer needs a Tailored Add-on, Custom Add-on, custom migration logic, or another custom-scoped requirement, but still wants to perform available migration actions manually.

**Required fit:** Custom Service without Expert Handle, unless expert-led execution is added to the agreed scope.

#### Scenario 7: Custom work with expert-led execution <a href="#scenario-7-custom-work-with-expert-led-execution" id="scenario-7-custom-work-with-expert-led-execution"></a>

The customer needs custom work and also wants Next-Cart experts to perform migration actions.

**Required fit:** Custom Service with Expert Handle included in the agreed scope.

### Final Questions Before Choosing <a href="#final-questions-before-choosing" id="final-questions-before-choosing"></a>

Before selecting a service model, customers should ask:

* Can the selected migration path stay within standard service capability?
* Can the customer perform migration actions confidently?
* Should Next-Cart perform migration actions based on the customer’s request?
* Did Demo Migration show predictable results?
* Do Add-ons solve the requirement within available settings and supported behavior?
* Does any Add-on need modification?
* Is a Custom Add-on needed?
* Is a Custom Platform involved?
* Do apps, plugins, modules, extensions, custom fields, third-party data, or outside-system identifiers affect the expected target-store result?
* Is Custom Service needed for custom work, Expert Handle, or both?
* Can the customer validate the final migration outcome before launch or business use?

These questions help separate preference from requirement. The right service model should reflect both how the migration should be performed and what the target-store result requires.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Next-Cart service model depends on execution responsibility and migration requirements. Standard Service fits customer-led migration through standard service capability. Managed Service fits Next-Cart-led migration through standard service capability. Custom Service is required when the project needs Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom fields, third-party data, custom migration logic, or broader bespoke handling.

The strongest decision comes from combining several signals: Demo Migration results, internal execution readiness, Entity Points capacity, Add-on requirements, Custom Service requirements, Expert Handle expectations, and validation responsibility. If the decision remains unclear, Live Chat can help confirm whether Standard Service, Managed Service, or Custom Service is the safest path before purchase, upgrade, or execution.

### FAQs <a href="#faqs" id="faqs"></a>

**How do I choose between Standard Service and Managed Service?**

Choose Standard Service when the migration can stay within standard service capability and the customer can perform migration actions. Choose Managed Service when the migration can stay within standard service capability but the customer wants Next-Cart to perform migration actions based on the customer’s request and agreed scope.

**When is Custom Service required?**

Custom Service is required when the project needs customization, modification, bespoke handling, Custom Platform review, Tailored Add-ons, Custom Add-ons, custom fields, third-party data, outside-system identifiers, custom migration logic, or other custom-scoped work.

**Does Custom Service always include Expert Handle?**

No. Custom Service defines the need for custom work. Expert Handle defines whether Next-Cart experts perform migration actions as part of the agreed Custom Service scope.

**Can customers perform migration actions manually under any service model?**

Yes. Customers of any service model can access and perform available migration actions manually if they choose. The selected service model determines responsibility, expert handling, and service scope.

**Does high Entity Points volume automatically require Managed Service or Custom Service?**

No. Entity Points measure counted capacity. A high-volume migration can still fit Standard Service if the project is predictable and the customer can perform migration actions.

**Can a smaller migration still require Custom Service?**

Yes. A smaller migration can require Custom Service if it involves Custom Platform, modified Add-ons, Custom Add-ons, custom fields, third-party data, outside-system identifiers, or bespoke migration behavior.

**Does using a Standard Add-on make the service Custom?**

No. Using a Standard Add-on within available settings and supported behavior does not make the service Custom. A modified Add-on or Custom Add-on request should be reviewed through Custom Service.

**Should I choose the service model before Demo Migration?**

Customers may have an initial service expectation before Demo Migration, but Demo Migration can provide stronger evidence for confirming whether Standard Service, Managed Service, or Custom Service is the right fit.

**What if I am unsure which service model fits?**

Review Demo Migration results, Add-on needs, internal execution readiness, Custom Platform involvement, custom data requirements, and Expert Handle expectations. Live Chat can help clarify the safest service path.
