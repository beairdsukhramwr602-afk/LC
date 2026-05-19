# Add-ons Explained

## Add-ons Explained <a href="#add-ons-explained" id="add-ons-explained"></a>

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. They are available when a customer needs more control over specific parts of the E-commerce Platform Migration, without turning every migration requirement into a Custom Service request.

Add-ons are available across Standard Service, Managed Service, and Custom Service. A Standard Add-on can support a straightforward migration when its available settings and supported behavior are enough. When the expected result requires the Add-on to be changed or expanded, that requirement becomes part of Custom Service as a Tailored Add-on. If the available Standard Add-ons do not fit the requirement, the customer can request a Custom Add-on.

Add-ons should not be treated as the full scope of Custom Service. They are focused optional service features, while Custom Service covers the broader path for customization, modification, and bespoke migration handling.

### What Add-ons Are  <a href="#what-add-ons-are" id="what-add-ons-are"></a>

Add-ons help customers handle specific migration needs that require more control than the default migration configuration provides.

They are most useful when the customer needs to:

* migrate only selected records
* control how source data maps into the Target Platform
* update or configure selected data values before migration

A Standard Add-on is suitable when its available settings and supported behavior can achieve the customer’s intended result. If the requirement needs new logic or modification beyond those supported settings, it should be reviewed through Custom Service.

### Add-on Types <a href="#add-on-types" id="add-on-types"></a>

Next-Cart uses three Add-on categories:

| Add-on type      | Meaning                                                                                                              | Service implication                                                    |
| ---------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Standard Add-ons | Ready-made optional service features available for purchase when their default capability fits the customer’s needs. | Can be used with Standard Service, Managed Service, or Custom Service. |
| Tailored Add-ons | Modified versions of Standard Add-ons created to fit a specific migration requirement.                               | Handled through Custom Service because modification work is required.  |
| Custom Add-ons   | New or project-specific Add-ons requested when the available Standard Add-ons do not fit the customer’s need.        | Reviewed and quoted through Custom Service.                            |

This structure keeps standard feature selection clear while still allowing project-specific handling when a customer’s migration settings or expected outcome requires something more specific.

### The Standard Add-ons Currently Available  <a href="#the-standard-add-ons-currently-available" id="the-standard-add-ons-currently-available"></a>

Next-Cart currently offers three standard Add-ons:

1. Data Filter Add-on
2. Advanced Data Mapping
3. Advanced Data Configure

These Add-ons are designed for common migration needs. They can be selected as standard optional service features when their default behavior fits the project.

They can also become the basis for Tailored Add-ons if the customer needs a modified version that better fits the migration requirement.

### Data Filter Add-on  <a href="#data-filter-add-on" id="data-filter-add-on"></a>

The Data Filter Add-on lets customers set filter rules to select the desired data for migration.

This Add-on is useful when the customer does not want all scanned records to move by default.

For example, the customer may want to migrate:

* products from selected categories
* orders from a specific time range
* customers matching certain conditions
* content records that support the new store plan
* only the data needed for a staged or selective migration

This distinction matters because the entity numbers entered during purchase are used for Entity Points Plan selection and pricing. They are not migration filters. All scanned records are migrated by default unless filtering is configured.

If the customer wants only selected records to move, the Data Filter Add-on should be planned before execution.

### Advanced Data Mapping  <a href="#advanced-data-mapping" id="advanced-data-mapping"></a>

Advanced Data Mapping helps customers control how source data maps into target data structures within the supported data model and capabilities of the platforms involved.

This Add-on is useful when the default mapping needs more control, but the expected result still fits what the Target Platform can support.

Examples may include:

* aligning source values with target-supported fields
* mapping customer groups more carefully
* mapping order statuses more deliberately
* aligning selected attributes with target-supported structures
* adjusting how source-store values are interpreted during migration

Advanced Data Mapping does not remove the limitations of the Target Platform. It supports more controlled mapping within what the target platform can reasonably represent.

### Advanced Data Configure  <a href="#advanced-data-configure" id="advanced-data-configure"></a>

Advanced Data Configure helps customers edit or modify selected data values so the migrated data reaches the Target Platform with updated information.

This Add-on is useful when the customer wants the migrated data to reflect planned adjustments instead of moving every value exactly as it appears in the Source Platform.

Examples may include:

* normalizing selected field values
* updating labels or values before migration
* adjusting selected data content to better fit the target environment
* applying planned data modifications during migration

Advanced Data Configure should be used when the customer knows what data should be changed and why that change matters for the target store.

### When a Standard Add-on Is Enough <a href="#when-a-standard-add-on-is-enough" id="when-a-standard-add-on-is-enough"></a>

A Standard Add-on is enough when the customer can achieve the intended result using the Add-on’s available settings and supported behavior.

In that case, the Add-on can be used with the selected service model:

* with Standard Service, the customer can use the Add-on while self-performing the migration
* with Managed Service, Next-Cart integrates the purchased Add-on while performing the migration process
* with Custom Service, the Add-on can be part of a broader custom plan

Using a Standard Add-on within its available settings and supported behavior does not automatically make the project Custom.

### Configuration Support Is Different From Modification <a href="#configuration-support-is-different-from-modification" id="configuration-support-is-different-from-modification"></a>

Sometimes the Add-on is already capable of producing the intended result, but the customer needs help understanding or correcting its settings.

That is configuration support, not Add-on modification.

For example, if the customer selected the Data Filter Add-on but configured a rule incorrectly, support may help the customer adjust the setting. The Add-on remains standard because its existing capability is enough.

Modification is different. Modification means the Add-on itself needs to be changed, extended, or tailored to support a result that the standard version cannot produce.

### Tailored Add-ons <a href="#tailored-add-ons" id="tailored-add-ons"></a>

A Tailored Add-on is a modified version of a Standard Add-on.

Tailored Add-ons are needed when the customer’s expected result cannot be achieved through the Standard Add-on’s available settings and supported behavior.

Examples include:

* filtering logic that is more complex than the Data Filter Add-on supports by default
* mapping logic that requires treatment beyond standard Advanced Data Mapping behavior
* data configuration rules that require modification beyond the standard Add-on
* a project-specific result that needs new logic added to a Standard Add-on

Tailored Add-ons are handled through Custom Service because they require customization or modification work.

### Custom Add-ons  <a href="#custom-add-ons" id="custom-add-ons"></a>

If the currently available Standard Add-ons do not match the customer’s migration requirement, the customer can request a Custom Add-on.

A Custom Add-on is different from selecting one of the three Standard Add-ons. It is a request for a new or project-specific service feature that fits the customer’s migration need when the listed Add-ons do not solve the problem.

Custom Add-ons are reviewed and quoted through Custom Service because they require customization or development work.

A Custom Add-on may be appropriate when the customer has a specific filtering, mapping, or data-configuration requirement that cannot be handled by the available Standard Add-ons.

### How Add-ons Affect Pricing <a href="#how-add-ons-affect-pricing" id="how-add-ons-affect-pricing"></a>

A Standard Add-on has a default price. The default Add-on price remains consistent across Standard Service, Managed Service, and Custom Service.

When a customer selects a Standard Add-on, its price is added to the migration total.

If a Standard Add-on needs modification beyond its available settings and supported behavior, Next-Cart provides a custom quote for the Tailored Add-on. If the customer already purchased the Standard Add-on, the customer pays the difference between the default Add-on price and the tailored quote.

For example:

* Standard Add-on price: $50
* Tailored Add-on quote: $75
* top-up amount: $25

This top-up reflects the difference between the standard version and the tailored version.

Custom Add-ons are quoted through Custom Service because their requirements are reviewed individually.

### How Add-ons Affect Migration Execution <a href="#how-add-ons-affect-migration-execution" id="how-add-ons-affect-migration-execution"></a>

Add-ons affect how the migration is configured and performed, but they do not decide who performs the migration by themselves.

With Standard Service, the customer self-performs the migration and uses the purchased Add-ons.

With Managed Service, Next-Cart performs the migration process and integrates the purchased Standard Add-ons.

With Custom Service, Add-ons may be part of a broader custom plan, especially when the Add-on is tailored or created as a Custom Add-on.

Customers of any service model can access and self-perform the migration process on the Next-Cart website if they want to. The service model determines the service responsibility and included work, not whether the customer has access.

### What Add-ons Do Not Cover  <a href="#what-add-ons-do-not-cover" id="what-add-ons-do-not-cover"></a>

Add-ons should not be used as a catch-all term for every kind of custom migration work.

Some requirements belong directly under Custom Service rather than the Add-ons feature set, such as:

* Custom Platform as Source Platform or Target Platform
* third-party app, plugin, module, or extension data
* custom fields
* outside-system identifiers
* custom migration logic adjustment
* platform capability limitations requiring bespoke handling
* special transformation rules outside Standard Add-on scope
* broader exclusive migration handling

Add-ons solve focused feature-level needs. Custom Service handles the wider cases where the migration approach itself must be tailored.

### How to Decide Whether an Add-on Is Needed  <a href="#how-to-decide-whether-an-add-on-is-needed" id="how-to-decide-whether-an-add-on-is-needed"></a>

A customer should consider Add-ons when the migration needs focused control over filtering, mapping, or data configuration.

Useful questions include:

* Should all scanned records migrate, or only selected records?
* Do source values need more controlled mapping into the Target Platform?
* Do selected data values need to be updated before migration?
* Can the requirement be handled through a Standard Add-on’s available settings and supported behavior?
* Does the expected result require a Tailored Add-on?
* Is the needed Add-on not currently available?
* Does the requirement actually belong under broader Custom Service handling?

These questions help the customer decide whether a Standard Add-on is enough or whether the project needs Custom Service.

### Conclusion  <a href="#conclusion" id="conclusion"></a>

Add-ons give customers practical control over focused migration needs. The current Standard Add-ons support data filtering, advanced data mapping, and data configuration. They can be used across Standard Service, Managed Service, and Custom Service when their available settings and supported behavior fit the project.

When a Standard Add-on needs modification, it becomes a Tailored Add-on and is handled through Custom Service. When the available Standard Add-ons do not fit the customer’s requirement, the customer can request a Custom Add-on, which is also reviewed and quoted through Custom Service.

Use Add-ons when your migration needs specific control over filtering, mapping, or data configuration. If the available Standard Add-ons do not fit the expected result, or if the requirement goes beyond standard Add-on capability, Live Chat can help clarify whether a Standard Add-on, Tailored Add-on, Custom Add-on, or broader Custom Service review is the right next step.

### FAQs  <a href="#faqs" id="faqs"></a>

**What are Add-ons?**

Add-ons are optional service features that help customers handle focused migration needs such as data filtering, advanced mapping, or data configuration.

**Which Standard Add-ons are currently available?**

The current Standard Add-ons are Data Filter Add-on, Advanced Data Mapping, and Advanced Data Configure.

**What is a Tailored Add-on?**

A Tailored Add-on is a modified version of a Standard Add-on. It is handled through Custom Service because it requires customization or modification work.

**What is a Custom Add-on?**

A Custom Add-on is a new or project-specific Add-on requested when the available Standard Add-ons do not fit the customer’s migration requirement. It is reviewed and quoted through Custom Service.

**Can Add-ons be used with every service model?**

Yes. Standard Add-ons can be used with Standard Service, Managed Service, and Custom Service.

**Does using a Standard Add-on make my project Custom?**

No. Using a Standard Add-on within its available settings and supported behavior does not automatically make the project Custom.

**When does an Add-on require Custom Service?**

An Add-on requires Custom Service when it needs modification beyond its available settings and supported behavior, or when the customer requests a Custom Add-on that is not currently available.

**How does Add-on top-up pricing work?**

If a purchased Standard Add-on needs modification, the customer pays the difference between the Standard Add-on price and the Tailored Add-on quote.

**Are Add-ons the same as Custom Service?**

No. Add-ons are focused optional service features for specific migration needs. Custom Service is the broader path for customization, modification, Custom Platform handling, custom migration logic adjustment, and other bespoke requirements.

**When should I use the Data Filter Add-on?**

Use the Data Filter Add-on when only selected records should migrate. Entered entity counts are used for pricing and plan capacity, not as automatic filters.

**What if I need filtering, mapping, or configuration beyond the available Standard Add-ons?**

If the available Standard Add-ons do not support the expected result, the requirement should be reviewed as a Tailored Add-on, Custom Add-on, or broader Custom Service requirement.
