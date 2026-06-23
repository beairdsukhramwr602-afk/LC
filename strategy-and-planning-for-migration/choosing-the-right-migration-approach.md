# Choosing the Right Migration Approach

Choosing the right migration approach is a planning decision. It should not be based only on where the store is moving, how many records exist, or which option sounds easiest. A strong approach matches the real shape of the project: what must be preserved, how predictable the data is, how much platform difference exists, how much work the internal team can carry, and how much evidence the business needs before launch approval.

A store can look simple until representative review reveals product-structure issues, extension-driven logic, custom fields, selective migration requirements, or acceptance criteria that require more controlled handling. Another store may not require customization at all, but may still need more guided execution because the internal team does not have enough time to coordinate the migration, review results, and make launch decisions without support.

Approach selection works best when it starts with evidence. The goal is not to choose a label early. The goal is to understand what level of handling, responsibility, and risk control the project actually needs.

### Migration Approach Should Follow Project Evidence <a href="#migration-approach-should-follow-project-evidence" id="migration-approach-should-follow-project-evidence"></a>

A migration approach should be chosen after the project has enough evidence to classify its real risk. Surface information can help with early orientation, but it is not enough for a reliable decision.

Common surface indicators include:

* catalog size;
* customer and order volume;
* Source Platform and Target Platform names;
* number of store views, languages, or currencies;
* expected launch timeline;
* whether the business wants a full or selective migration.

Those details matter, but they do not fully explain the migration approach. A small store can require custom handling if business-critical information lives in non-standard fields. A larger store can remain predictable when the data model is clean, relationships are consistent, and the Target Platform can represent the same business meaning without major compromise.

The stronger planning question is:

**Which approach gives the project enough control to preserve the required outcomes without adding unnecessary process weight?**

That question keeps approach selection tied to evidence rather than preference.

### Separate Approach Choice From Service-Model Detail <a href="#separate-approach-choice-from-service-model-detail" id="separate-approach-choice-from-service-model-detail"></a>

Approach selection should not become a full Migration Service explanation. Migration Services belong to service documentation and service comparison content. At the planning stage, the more useful task is to understand what kind of project pattern the migration fits.

Most migrations fall into one of three approach patterns:

| Planning pattern                   | What it means                                                                                                                    | Main planning question                                                         |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Predictable customer-led migration | The data is structurally workable and the customer can carry execution and review responsibility                                 | Can the customer team execute and validate the migration with acceptable risk? |
| Guided or expert-led execution     | The data is feasible within standard capability, but internal bandwidth or coordination risk is high                             | Would expert-led execution reduce avoidable operational risk?                  |
| Customization-driven handling      | The expected outcome depends on mapping, filtering, transformation, Custom Platform handling, or non-standard preservation logic | Is standard handling enough to preserve the required business meaning?         |

These patterns may later connect to Standard Service, Managed Service, or Custom Service, but the planning decision should begin with the project’s needs. Service labels are useful only after the evidence shows what type of responsibility and handling the project requires.

### Start With the Outcome That Must Be Protected <a href="#start-with-the-outcome-that-must-be-protected" id="start-with-the-outcome-that-must-be-protected"></a>

A migration approach should protect the outcomes that matter most to the business. Without that anchor, a project can choose an approach that is convenient but poorly matched to the actual risk.

Important protected outcomes may include:

* customers can find and purchase products correctly;
* product choices, variants, options, and attributes remain understandable;
* categories, collections, menus, and filters still support product discovery;
* customer accounts, address books, order history, and business-customer records remain usable;
* SEO-sensitive URLs, redirects, metadata, and page continuity receive enough planning attention;
* pricing, tax, promotion, or customer-group behavior does not create launch confusion;
* operational teams can confirm that migrated records are acceptable before launch.

Approach selection becomes clearer when these outcomes are named before execution. A project that only needs record movement and basic review can use a lighter approach. A project that needs meaning preservation across platform differences may require deeper handling.

### Evaluate Internal Responsibility Honestly <a href="#evaluate-internal-responsibility-honestly" id="evaluate-internal-responsibility-honestly"></a>

Some migrations are technically feasible but operationally risky because the customer team cannot carry the required execution or review workload. Approach selection should account for internal capacity, not just data complexity.

The customer team may need to handle:

* preparing access and source data;
* confirming what should move and what should be excluded;
* reviewing sample results;
* identifying acceptable differences;
* validating high-value records;
* coordinating business stakeholders before launch;
* making decisions when edge cases appear.

If those responsibilities are unrealistic for the team’s availability, a customer-led approach may create avoidable risk even when the data itself is not highly complex. In that case, the project may need more guided or expert-led execution to keep decisions, review, and launch preparation under control.

This is not the same as Custom Service. Limited internal bandwidth does not automatically mean custom handling is needed. It may simply mean the business needs more execution support for a structurally feasible migration.

### Use Complexity to Decide the Level of Handling <a href="#use-complexity-to-decide-the-level-of-handling" id="use-complexity-to-decide-the-level-of-handling"></a>

Complexity should inform the approach because it changes how much interpretation, control, and review the project needs. Complexity is not only about volume. It can come from structure, behavior, platform differences, third-party dependencies, data quality, or validation expectations.

| Complexity source                   | Why it affects approach selection                                             | Possible planning response                                 |
| ----------------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Product and catalog structure       | Variant, attribute, category, and filter behavior may not map directly        | Require deeper sample review and clear acceptance criteria |
| Relationship-sensitive data         | Products, customers, orders, categories, and content may depend on each other | Validate connected behavior, not isolated records only     |
| Third-party or extension-owned data | Important meaning may live outside standard platform structures               | Assess whether custom mapping or preservation is needed    |
| Target Platform limitations         | The new platform may represent the same business concept differently          | Decide what must remain equivalent and what can change     |
| Data ambiguity                      | Inconsistent or duplicated source data can make meaning unclear               | Clean, exclude, transform, or document acceptable change   |
| Validation burden                   | Launch approval may require stronger proof than basic spot checks             | Define review priorities before execution begins           |

The right approach is the one that matches the strongest source of risk. If risk comes from internal workload, guided execution may be enough. If risk comes from data meaning that cannot be preserved through standard handling, custom handling may be needed.

### Identify Whether the Project Is Predictable Enough for Customer-Led Execution <a href="#identify-whether-the-project-is-predictable-enough-for-customer-led-execution" id="identify-whether-the-project-is-predictable-enough-for-customer-led-execution"></a>

A customer-led standard approach is realistic when the project is predictable and the customer team can take responsibility for execution and review. Predictable does not mean risk-free. It means the project’s main challenge is disciplined execution rather than unclear structure or non-standard preservation logic.

Strong signals include:

* representative records map in a workable way;
* product, category, customer, and order relationships remain understandable;
* platform differences are acceptable or easy to explain;
* business-critical logic does not depend heavily on custom fields, apps, plugins, modules, extensions, or outside systems;
* selective migration rules are simple and clearly documented;
* the internal team can review the result before launch;
* launch timing allows enough time for correction if issues appear.

A customer-led approach becomes weaker when the business wants convenience but cannot realistically perform review. The approach should be selected for the real operating conditions, not for the ideal version of the team’s availability.

### Identify When Guided or Expert-Led Execution Is Safer <a href="#identify-when-guided-or-expert-led-execution-is-safer" id="identify-when-guided-or-expert-led-execution-is-safer"></a>

Guided or expert-led execution is often safer when the migration is feasible within standard capability but operational execution risk is high. The project may not need custom transformation, but it may still need stronger coordination, clearer process control, and more support during execution.

Common signals include:

* the business has limited internal migration bandwidth;
* the launch window is tight;
* multiple stakeholders must approve the result;
* the customer team cannot spend enough time managing repeated execution steps;
* the data is generally workable, but review and correction need careful coordination;
* the business wants less exposure to missed steps or delayed decisions.

In this pattern, the main concern is not that the data is impossible to migrate through standard handling. The concern is that customer-led execution may not be realistic enough for the project’s timeline, review burden, or operational pressure.

This distinction matters. A project can need more execution support without needing customization. The planning decision should keep those two issues separate.

### Identify When Custom Handling Is Required <a href="#identify-when-custom-handling-is-required" id="identify-when-custom-handling-is-required"></a>

Custom handling becomes necessary when the expected outcome depends on work beyond standard capability or Standard Add-on capability. In these cases, the project is no longer only deciding who performs the migration. It is deciding how business meaning should be preserved when standard structures are not enough.

Custom handling may be relevant when:

* custom fields affect storefront, reporting, fulfillment, customer service, or merchandising behavior;
* app, plugin, module, or extension-managed data must remain usable after migration;
* field values need transformation before they make sense on the Target Platform;
* filtering, mapping, or data configuration needs exceed Standard Add-on capability;
* the Source Platform or Target Platform uses non-standard structures;
* a Custom Platform requires bespoke interpretation;
* outside-system identifiers must remain connected to ERP, CRM, PIM, OMS, fulfillment, marketing, or analytics systems;
* the Target Platform cannot represent an important behavior in the same way by default.

Custom Service is the Next-Cart path for customization or modification-driven handling, including Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, and bespoke transformation. It does not automatically mean Next-Cart performs the full migration unless migration management is included in the final plan.

### Treat Add-ons as Scope and Handling Signals <a href="#treat-add-ons-as-scope-and-handling-signals" id="treat-add-ons-as-scope-and-handling-signals"></a>

Add-ons should not be treated as general feature promotion inside approach planning. They should appear only when the project has a concrete planning need that points to filtering, mapping, or configuration work.

Relevant signals include:

* the project needs to migrate only selected records;
* field relationships require more precise mapping than the standard path covers;
* product, customer, order, category, or content data needs configuration before it can be interpreted correctly;
* source values need to be included, excluded, grouped, adjusted, or mapped in a specific way;
* the customer wants a controlled outcome rather than a broad transfer of available records.

Standard Add-ons can help when the need fits predefined filtering, mapping, or configuration capability. Tailored Add-ons and Custom Add-ons belong under Custom Service when the requirement needs adjustment or bespoke handling beyond standard capability.

This keeps Add-ons connected to real project requirements instead of turning the approach discussion into a service-feature list.

### Build an Approach Decision Matrix <a href="#build-an-approach-decision-matrix" id="build-an-approach-decision-matrix"></a>

A simple matrix can prevent approach selection from becoming subjective. The goal is not to calculate an automatic answer. The goal is to expose the evidence behind the decision.

| Decision area         | Lower-control signal                                      | Higher-control signal                                                        | What it influences                                               |
| --------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Data structure        | Standard records and predictable relationships            | Custom fields, extensions, complex relationships, or non-standard structures | Whether standard handling is enough                              |
| Platform difference   | Similar data models and acceptable representation changes | Major mismatch between Source Platform and Target Platform behavior          | Whether mapping or transformation needs deeper review            |
| Internal capacity     | Customer team can execute and validate on time            | Customer team has limited availability or launch pressure                    | Whether expert-led execution is safer                            |
| Scope selectivity     | Full or simple scope                                      | Precise filtering, exclusions, partial history, or segmented records         | Whether Data Filter Add-on or custom selection logic is needed   |
| Validation burden     | Basic review is enough for launch confidence              | Stakeholders require detailed acceptance proof                               | How much review structure the approach needs                     |
| External dependencies | Few or low-impact external systems                        | ERP, CRM, PIM, fulfillment, subscription, loyalty, or analytics dependencies | Whether external identifiers and workflows need special handling |

A project with low structural uncertainty but high internal workload may need guided execution. A project with high structural uncertainty may need Custom Service evaluation. A project with both may need a combined plan.

### Avoid Choosing the Approach Too Early <a href="#avoid-choosing-the-approach-too-early" id="avoid-choosing-the-approach-too-early"></a>

A common mistake is choosing the approach before the project has enough evidence. Early assumptions often come from record counts, platform names, or budget expectations. Those assumptions can change once the team reviews representative data and identifies actual dependencies.

Approach choice should usually wait until the project has at least:

* an initial entity and scope list;
* a clear view of what must remain equivalent;
* representative sample evidence;
* known exclusions or acceptable changes;
* identified custom fields, extension data, and outside-system dependencies;
* a realistic view of internal execution and review capacity;
* preliminary acceptance criteria for launch approval.

This does not mean every project needs a long discovery phase. It means the approach should be based on enough information to avoid solving the wrong problem.

### Match the Approach to the Highest Real Risk <a href="#match-the-approach-to-the-highest-real-risk" id="match-the-approach-to-the-highest-real-risk"></a>

The best approach is usually the one that addresses the highest real risk first.

If the highest risk is internal workload, stronger execution support may be the right answer. If the highest risk is structural mismatch, custom mapping or transformation may be required. If the highest risk is unclear scope, approach selection should wait until the scope is defined. If the highest risk is validation uncertainty, the approach should include stronger review checkpoints and acceptance criteria.

Approach selection becomes weak when it treats all risk as the same kind of risk. A migration can fail because the data is difficult, because decisions are unclear, because the team cannot review the result, or because the Target Platform cannot express the same behavior without adjustment. Each problem points to a different kind of approach.

### Approach Selection Should Produce a Planning Rationale <a href="#approach-selection-should-produce-a-planning-rationale" id="approach-selection-should-produce-a-planning-rationale"></a>

The output of approach selection should be a rationale the team can use during the rest of the project. It should explain why the chosen approach fits the project evidence and what assumptions must remain true.

A strong rationale usually includes:

* the protected outcomes;
* the selected scope and major exclusions;
* the strongest complexity signals;
* the customer team’s execution and review responsibilities;
* the expected level of Next-Cart involvement, if relevant;
* Add-ons or Custom Service considerations, if justified by the project;
* validation priorities that must confirm the approach worked;
* conditions that would trigger approach escalation.

This rationale prevents the approach from becoming a one-time label. It gives the project a decision record that can be revisited if sample results, scope changes, or platform constraints reveal new risk.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Choosing the right migration approach means matching the project to the kind of control it actually needs. A predictable project with enough internal capacity may fit customer-led execution. A feasible but operationally demanding project may need guided or expert-led execution. A project that depends on non-standard preservation, transformation, Custom Platform handling, or deeper mapping may need Custom Service evaluation.

The strongest decision comes from evidence: protected outcomes, scope, representative data, complexity signals, internal capacity, and validation requirements. When approach selection follows those inputs, the migration plan is more likely to control the right risks before execution begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Should the migration approach be chosen before a sample review?**

It can be estimated early, but it should not be treated as final until representative data has been reviewed. A sample can reveal structural issues, custom logic, or review demands that change the safest approach.

**Does a large store always need a more advanced migration approach?**

No. Large stores can be predictable when their data structures are clean and their expected outcomes are straightforward. Smaller stores can require deeper handling when they depend on custom fields, extension data, platform-specific logic, or strict validation requirements.

**What is the difference between needing execution support and needing Custom Service?**

Execution support helps when the migration is feasible but the customer team needs stronger coordination, process control, or workload support. Custom Service is needed when customization or modification work is required to preserve the expected result.

**When should Add-ons be considered during approach selection?**

Add-ons should be considered when the project has a specific filtering, mapping, or configuration need. They should not be added by default; they should solve a defined planning requirement.

**What should trigger approach escalation?**

Approach escalation should be considered when sample results reveal structural mismatch, unsupported data, hidden custom logic, unclear ownership, Target Platform limitations, or validation demands that the current approach cannot control safely.
