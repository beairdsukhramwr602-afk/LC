# Add-ons

Add-ons are optional service features that give customers more control over specific parts of a migration. They are useful when the selected migration path is generally supported, but the customer needs extra help with filtering, mapping, or data configuration so the target-store result better matches the intended business outcome.

Add-ons should be understood as focused service features. They are not the same as Custom Service. A Standard Add-on can support common migration needs when its available settings and supported behavior are enough. If the expected result requires the Add-on to be modified, expanded, or created for a project-specific requirement, that work should be reviewed through Custom Service.

### What Add-ons Are Designed to Control <a href="#what-add-ons-are-designed-to-control" id="what-add-ons-are-designed-to-control"></a>

Add-ons help customers control selected migration details that may affect the final target-store result.

They are most useful when the customer needs to:

* migrate only selected source-store records;
* control how source-store values map into the Target Platform;
* adjust selected data values before or during migration;
* improve the fit between migrated data and the target-store setup;
* handle a focused requirement without turning the whole migration into a broader custom project.

Add-ons work best when the customer can clearly describe the expected result. A vague goal such as “make the migrated data look better” is usually not enough. A useful Add-on requirement explains what should be filtered, mapped, configured, or adjusted, and why that change matters for the target store.

### Add-on Categories <a href="#add-on-categories" id="add-on-categories"></a>

Next-Cart uses three Add-on categories: Standard Add-ons, Tailored Add-ons, and Custom Add-ons.

| Add-on category  | What it means                                                                                        | Service implication                                                    |
| ---------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Standard Add-ons | Ready-made optional service features available when the default capability fits the customer’s need. | Can be used with Standard Service, Managed Service, or Custom Service. |
| Tailored Add-ons | Modified versions of Standard Add-ons created for a specific requirement.                            | Handled through Custom Service because modification work is required.  |
| Custom Add-ons   | Project-specific Add-ons requested when available Standard Add-ons do not fit the requirement.       | Reviewed and quoted through Custom Service.                            |

This structure keeps standard choices clear while still allowing project-specific handling when a migration needs more than the default Add-on capability.

### Standard Add-ons Currently Available <a href="#standard-add-ons-currently-available" id="standard-add-ons-currently-available"></a>

Next-Cart currently provides three Standard Add-ons:

* Data Filter Add-on
* Advanced Data Mapping
* Advanced Data Configure

These Add-ons support common needs during migration configuration. They can be selected when their default behavior fits the customer’s requirement.

If a Standard Add-on is close to the desired result but needs modification, the requirement becomes a Tailored Add-on. If none of the available Standard Add-ons can support the need, the customer may request a Custom Add-on.

### Data Filter Add-on <a href="#data-filter-add-on" id="data-filter-add-on"></a>

The Data Filter Add-on helps customers migrate only selected source-store records instead of migrating all scanned records by default.

This Add-on is useful when the customer wants to limit migration scope based on specific business criteria, such as:

* products from selected categories;
* orders from a specific time range;
* customers matching defined conditions;
* content records needed for the new store plan;
* records selected for a staged or selective migration strategy.

The Data Filter Add-on is especially important because purchase estimates are not migration filters. Entity counts entered during purchase support capacity and pricing planning. They do not automatically tell the migration process to move only that number of records.

A customer who wants only selected records to move should plan filtering before execution rather than expecting the purchase estimate to control migration scope.

### Advanced Data Mapping <a href="#advanced-data-mapping" id="advanced-data-mapping"></a>

Advanced Data Mapping helps customers control how source-store values are mapped into target-store structures within the supported capability of the Source Platform, Target Platform, and selected migration path.

This Add-on is useful when the default mapping needs more deliberate control, such as:

* aligning source values with target-supported fields;
* mapping customer groups more carefully;
* mapping order statuses more deliberately;
* aligning selected attributes with target-supported structures;
* adjusting how source-store values should be interpreted in the target store.

Advanced Data Mapping does not remove Target Platform limitations. It helps create a more controlled result within what the Target Platform can reasonably represent.

### Advanced Data Configure <a href="#advanced-data-configure" id="advanced-data-configure"></a>

Advanced Data Configure helps customers adjust selected data values so the migrated data better fits the intended target-store setup.

This Add-on is useful when the customer knows which data values should be changed and why the change matters. Examples may include:

* normalizing selected field values;
* updating labels or values before migration;
* adjusting selected data content for the target-store environment;
* applying planned data modifications during migration.

Advanced Data Configure should not be used as a vague cleanup request. It works best when the customer can identify the data to adjust and the intended result.

### When a Standard Add-on Is Enough <a href="#when-a-standard-add-on-is-enough" id="when-a-standard-add-on-is-enough"></a>

A Standard Add-on is enough when the customer’s intended result can be achieved through the Add-on’s available settings and supported behavior.

In that case, the Add-on can support the selected service model:

* with Standard Service, the customer uses the Add-on while performing migration actions;
* with Managed Service, Next-Cart experts can integrate the purchased Add-on based on the customer’s request and agreed service scope;
* with Custom Service, the Add-on can be included as part of a broader service plan when relevant.

Using a Standard Add-on within its available settings does not automatically make the migration a Custom Service case. The project becomes a Custom Service case when the requirement needs customization, modification, bespoke handling, Custom Platform handling, unsupported data treatment, or custom migration logic.

### Configuration Support Is Different From Add-on Modification <a href="#configuration-support-is-different-from-add-on-modification" id="configuration-support-is-different-from-add-on-modification"></a>

Sometimes a Standard Add-on can produce the intended result, but the customer needs help understanding or correcting its settings. That is configuration support, not Add-on modification.

For example, if a customer selects the Data Filter Add-on but sets a rule incorrectly, support may help review the setting. The Add-on remains standard because its existing capability is enough.

Modification is different. Modification means the Add-on itself must be changed, expanded, or tailored to produce a result that the standard version does not support.

### Tailored Add-ons <a href="#tailored-add-ons" id="tailored-add-ons"></a>

A Tailored Add-on is a modified version of a Standard Add-on.

Tailored Add-ons are needed when the customer’s expected result cannot be achieved through the Standard Add-on’s available settings and supported behavior.

Examples include:

* filtering logic that is more complex than the Data Filter Add-on supports by default;
* mapping logic that requires treatment beyond standard Advanced Data Mapping behavior;
* data configuration rules that require modification beyond the standard Add-on;
* a project-specific result that needs new logic added to a Standard Add-on.

Tailored Add-ons are handled through Custom Service because they require customization or modification work.

### Custom Add-ons <a href="#custom-add-ons" id="custom-add-ons"></a>

A Custom Add-on is used when the available Standard Add-ons do not fit the customer’s requirement.

A Custom Add-on is not a modified version of a listed Add-on. It is a new or project-specific service feature reviewed for the customer’s expected result, data structure, migration path, and technical complexity.

Custom Add-ons are quoted through Custom Service because the work depends on the requirement. They may be appropriate when a customer has a specific filtering, mapping, or data-configuration need that cannot be solved by the available Standard Add-ons or by tailoring one of them.

### How Add-ons Relate to Pricing <a href="#how-add-ons-relate-to-pricing" id="how-add-ons-relate-to-pricing"></a>

A Standard Add-on has a default price. When selected, that price is added to the migration total.

If a Standard Add-on needs modification, the tailored version is quoted through Custom Service. If the customer already purchased the Standard Add-on and later needs a tailored version, the customer pays only the top-up difference between the default Add-on price and the tailored quote.

Custom Add-ons are quoted individually because the expected result, data structure, and required work can vary.

For full pricing context, customers should review the Entity Points Plan, service model, Add-ons, and any custom work together before purchase.

### What Add-ons Do Not Cover <a href="#what-add-ons-do-not-cover" id="what-add-ons-do-not-cover"></a>

Add-ons should not be used as a catch-all term for every migration requirement.

Some needs belong directly under Custom Service rather than the Add-on feature set, such as:

* Custom Platform as Source Platform or Target Platform;
* third-party app, plugin, module, or extension data;
* custom fields;
* outside-system identifiers;
* custom migration logic adjustment;
* platform capability limitations requiring bespoke handling;
* broader exclusive migration handling;
* requirements where the migration approach itself must be tailored.

Add-ons solve focused feature-level needs. Custom Service handles broader cases where the migration approach, migration logic, or unsupported data handling requires custom planning.

### How to Decide Whether an Add-on Is Needed <a href="#how-to-decide-whether-an-add-on-is-needed" id="how-to-decide-whether-an-add-on-is-needed"></a>

A customer should consider Add-ons when the migration needs focused control over filtering, mapping, or data configuration.

Useful questions include:

* Should all scanned records migrate, or only selected records?
* Do source-store values need more controlled mapping into the Target Platform?
* Do selected data values need to be adjusted before migration?
* Can the requirement be handled through a Standard Add-on’s available settings and supported behavior?
* Does the expected result require a Tailored Add-on?
* Is the needed Add-on unavailable as a Standard Add-on?
* Does the requirement actually belong under broader Custom Service handling?

The best Add-on decision is based on the desired target-store result, not only on the Add-on name. If the expected result is clear, it is easier to decide whether a Standard Add-on, Tailored Add-on, Custom Add-on, or broader Custom Service review is appropriate.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Add-ons help customers control focused migration needs such as filtering, advanced mapping, and data configuration. The current Standard Add-ons are Data Filter Add-on, Advanced Data Mapping, and Advanced Data Configure. They can support Standard Service, Managed Service, or Custom Service when their available settings and supported behavior fit the requirement.

When a Standard Add-on needs modification, it becomes a Tailored Add-on and is handled through Custom Service. When available Standard Add-ons do not fit the requirement, the customer can request a Custom Add-on, which is also reviewed and quoted through Custom Service.

Add-ons are most effective when the customer knows what should be filtered, mapped, configured, or adjusted before migration execution. If the available Add-ons do not clearly match the expected result, Live Chat can help clarify whether the right next step is a Standard Add-on, Tailored Add-on, Custom Add-on, or broader Custom Service review.

### FAQs <a href="#faqs" id="faqs"></a>

**What are Add-ons?**

Add-ons are optional service features that help customers control focused migration needs such as data filtering, advanced mapping, or data configuration.

**Which Standard Add-ons are currently available?**

The current Standard Add-ons are Data Filter Add-on, Advanced Data Mapping, and Advanced Data Configure.

**Can Add-ons be used with every service model?**

Yes. Standard Add-ons can be used with Standard Service, Managed Service, and Custom Service when their available settings and supported behavior fit the requirement.

**Does using a Standard Add-on make my migration a Custom Service case?**

No. Using a Standard Add-on within its available settings and supported behavior does not automatically make the migration a Custom Service case.

**What is a Tailored Add-on?**

A Tailored Add-on is a modified version of a Standard Add-on. It is handled through Custom Service because customization or modification work is required.

**What is a Custom Add-on?**

A Custom Add-on is a new or project-specific Add-on requested when the available Standard Add-ons do not fit the customer’s requirement. It is reviewed and quoted through Custom Service.

**When does an Add-on require Custom Service?**

An Add-on requires Custom Service when it needs modification beyond its available settings and supported behavior, or when the customer requests a Custom Add-on that is not currently available.

**Is Add-on pricing the same as Entity Points pricing?**

No. Entity Points Plans define counted migration capacity. Add-ons are optional service features added when the customer needs filtering, advanced mapping, or data configuration support.
