# Add-ons Explained

Add-ons are optional Next-Cart features that give customers more control over specific parts of a migration. They are designed for focused needs such as selecting which records should move, adjusting source-to-target data mapping, or configuring data values before they reach the Target Cart.

Add-ons are available across Standard Service, Managed Service, and Custom Service. They can support straightforward migration projects when their default capability is enough, and they can also become part of a Custom Service plan when the customer needs modification, tailoring, or a custom Add-on that is not currently available.

Add-ons should not be treated as the full scope of Custom Service. They are one part of Next-Cart’s service system, not a replacement for every kind of custom migration handling.

### What Add-ons Are <a href="#what-add-ons-are" id="what-add-ons-are"></a>

Add-ons are optional service features customers can select when a migration needs more control than the default migration setup provides for a specific requirement.

They help with three common needs:

* filtering selected data for migration
* adjusting data mapping between the Source Cart and Target Cart
* configuring or modifying data values before migration

A standard Add-on can be used when its default capabilities meet the customer’s requirements. If the requirement goes beyond the default capability of the Add-on, the work is handled through Custom Service.

### The Standard Add-ons Currently Available <a href="#the-standard-add-ons-currently-available" id="the-standard-add-ons-currently-available"></a>

Next-Cart currently offers three standard Add-ons:

1. Data Filter Add-on
2. Advanced Data Mapping
3. Advanced Data Configure

These Add-ons are designed for common migration needs. They can be used as standard features when their default settings and supported behavior are enough for the project.

They can also become the basis for tailored work if the customer needs a modified version that better fits the migration requirement.

### Data Filter Add-on <a href="#data-filter-add-on" id="data-filter-add-on"></a>

The Data Filter Add-on lets customers set filter rules to select the desired data for migration.

This Add-on is useful when the customer does not want all scanned records to move by default.

For example, the customer may want to migrate:

* products from selected categories
* orders from a specific time range
* customers matching certain conditions
* content records that support the new store plan
* only the data needed for a staged or selective migration

This is important because the entity numbers entered during purchase are used for Entity Points Plan selection and pricing. They are not migration filters. All scanned records are migrated by default unless filtering is configured.

If the customer wants only selected records to move, the Data Filter Add-on should be planned before execution.

### Advanced Data Mapping <a href="#advanced-data-mapping" id="advanced-data-mapping"></a>

Advanced Data Mapping helps customers configure and modify how source data maps into target data structures within the supported data model and capabilities of the platforms involved.

This Add-on is useful when the default mapping needs more control, but the expected result still fits what the Target Cart can support.

Examples may include:

* aligning source values with target-supported fields
* mapping customer groups more carefully
* mapping order statuses more deliberately
* aligning selected attributes with target-supported structures
* adjusting how source-store values are interpreted during migration

Advanced Data Mapping does not remove the limitations of the Target Cart. It supports more controlled mapping within what the target platform can reasonably represent.

### Advanced Data Configure <a href="#advanced-data-configure" id="advanced-data-configure"></a>

Advanced Data Configure helps customers edit or modify selected data values so the migrated data reaches the Target Cart with updated information.

This Add-on is useful when the customer wants the migrated data to reflect planned adjustments instead of moving every value exactly as it appears in the Source Cart.

Examples may include:

* normalizing selected field values
* updating labels or values before migration
* adjusting selected data content to better fit the target environment
* applying planned data modifications during migration

Advanced Data Configure should be used when the customer knows what data should be changed and why that change matters for the target store.

### Standard Add-ons Within Default Capability <a href="#standard-add-ons-within-default-capability" id="standard-add-ons-within-default-capability"></a>

A standard Add-on stays within default capability when the customer can achieve the intended result using the Add-on’s available settings and supported behavior.

In that case, the Add-on can be used with the selected service model:

* with Standard Service, the customer uses the Add-on while performing the migration
* with Managed Service, Next-Cart integrates the purchased Add-on while performing the migration process
* with Custom Service, the Add-on can be part of the broader custom plan

Using a standard Add-on within the default capability does not automatically make the project Custom.

### Configuration Support Within Default Capability <a href="#configuration-support-within-default-capability" id="configuration-support-within-default-capability"></a>

Sometimes the customer’s issue is not that the Add-on needs modification, but that the Add-on needs to be configured correctly.

When the requirement aligns with the standard Add-on’s default capabilities, Next-Cart support can guide the customer toward the right configuration. This does not turn the Add-on into a custom Add-on.

For example, if the customer selected the Data Filter Add-on but configured a rule incorrectly, support may help the customer correct the setting. The Add-on remains standard because its default capabilities are still sufficient.

### When an Add-on Needs Modification <a href="#when-an-add-on-needs-modification" id="when-an-add-on-needs-modification"></a>

An Add-on needs modification when the customer’s expected result cannot be achieved through the Add-on’s default settings or supported behavior.

Any Add-on modification is handled through Custom Service.

Examples include:

* filtering logic that is more complex than the standard Data Filter Add-on supports
* mapping logic that requires treatment beyond the default Advanced Data Mapping behavior
* data configuration rules that require tailored modification beyond the standard Add-on
* a project-specific data result that needs new logic added to the Add-on

The service status changes to Custom because customization or modification work is required.

### Custom Add-ons <a href="#custom-add-ons" id="custom-add-ons"></a>

If the currently available Add-ons do not match the customer’s migration requirement, the customer can request a custom Add-on.

A custom Add-on is different from simply selecting one of the three standard Add-ons. It is a request for an Add-on feature that fits the customer’s specific migration need when the listed Add-ons do not solve the problem.

Custom Add-ons are reviewed and quoted through Custom Service because they require customization or development work.

A custom Add-on may be appropriate when the customer has a specific filtering, mapping, or data-configuration requirement that cannot be handled by the available standard Add-ons.

### How Add-ons Affect Service Status <a href="#how-add-ons-affect-service-status" id="how-add-ons-affect-service-status"></a>

Standard Add-ons are available across all service models.

Using a standard Add-on within the default capability does not automatically change the service status.

The service status changes when customization or modification work is introduced.

For example:

* a Standard Service customer who uses a standard Data Filter Add-on within the default capability remains on Standard Service
* a Managed Service customer who uses standard Advanced Data Mapping within the default capability remains on Managed Service
* a customer who needs a modified Data Filter Add-on is handled through Custom Service
* a customer who requests a custom Add-on is handled through Custom Service

The key rule is simple: standard Add-ons can stay within the selected service model; modified Add-ons and custom Add-ons are handled through Custom Service.

### Add-ons and Pricing <a href="#add-ons-and-pricing" id="add-ons-and-pricing"></a>

A standard Add-on has a default price. The default Add-on price remains consistent across Standard Service, Managed Service, and Custom Service.

When a customer selects a standard Add-on, its price is added to the migration total.

If a standard Add-on needs modification beyond its default capabilities, Next-Cart provides a custom quote for the modified version. If the customer has already purchased the standard Add-on and requests a tailored modification, the customer will only have to pay the difference between the default Add-on price and the customized Add-on quote.

For example:

* standard Add-on price: $50
* customized Add-on quote: $75
* top-up amount: $25

This top-up reflects the difference between the standard version and the customized version.

### Add-ons and Migration Execution <a href="#add-ons-and-migration-execution" id="add-ons-and-migration-execution"></a>

Add-ons affect how the migration is configured and executed, but they do not decide who performs the migration process by themselves.

With Standard Service, the customer performs the migration and uses the purchased Add-ons.

With Managed Service, Next-Cart performs the migration process and integrates the purchased Add-ons.

With Custom Service, Add-ons may be part of a broader custom plan, especially when the Add-on is modified or a custom Add-on is created.

This distinction helps customers separate the feature they need from the service responsibility they choose.

### What Add-ons Do Not Cover <a href="#what-add-ons-do-not-cover" id="what-add-ons-do-not-cover"></a>

Add-ons should not be used as a catch-all term for every kind of custom migration work.

Some requirements belong directly under Custom Service rather than the Add-ons article, such as:

* Custom Cart as Source Cart or Target Cart
* third-party app, plugin, module, or extension data
* custom fields
* outside-system identifiers
* migration-tool modification
* platform capability limitations requiring bespoke handling
* special transformation rules outside the standard Add-on scope
* broader exclusive migration handling

Add-ons are focused service features. Custom Service is the broader path for customization, modification, and exclusive handling.

### How to Decide Whether an Add-on Is Needed <a href="#how-to-decide-whether-an-add-on-is-needed" id="how-to-decide-whether-an-add-on-is-needed"></a>

A customer should consider Add-ons when the migration needs focused control over filtering, mapping, or data configuration.

Useful questions include:

* Should all scanned records migrate, or only selected records?
* Do source values need more controlled mapping into the Target Cart?
* Do selected data values need to be updated before migration?
* Can the requirement be handled through a standard Add-on’s default settings?
* Does the expected result require Add-on modification?
* Is the needed Add-on not currently available?
* Does the requirement actually belong under broader Custom Service handling?

These questions help the customer decide whether a standard Add-on is enough or whether the project needs Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Add-ons give customers practical control over focused migration needs. The current standard Add-ons support data filtering, advanced data mapping, and data configuration. They can be used across Standard Service, Managed Service, and Custom Service when their default capability fits the project.

When an Add-on needs modification, or when the customer needs a custom Add-on that is not currently available, the work is handled through Custom Service. This keeps Add-ons focused while preserving a clear path for project-specific requirements.

Use Add-ons when your migration needs specific control over filtering, mapping, or data configuration. If the available Add-ons do not fit the expected result, or if the requirement goes beyond default Add-on capability, Live Chat can help clarify whether a tailored Add-on, custom Add-on, or broader Custom Service review is the right next step.

### FAQs <a href="#faqs" id="faqs"></a>

#### What are Add-ons? <a href="#what-are-add-ons" id="what-are-add-ons"></a>

Add-ons are optional Next-Cart features that help customers handle focused migration needs such as data filtering, advanced mapping, or data configuration.

#### Which standard Add-ons are currently available? <a href="#which-standard-add-ons-are-currently-available" id="which-standard-add-ons-are-currently-available"></a>

The current standard Add-ons are the Data Filter Add-on, the Advanced Data Mapping, and the Advanced Data Configure.

#### Can Add-ons be used with every service model? <a href="#can-add-ons-be-used-with-every-service-model" id="can-add-ons-be-used-with-every-service-model"></a>

Yes. Standard Add-ons can be used with Standard Service, Managed Service, and Custom Service.

#### Does using a standard Add-on make my project Custom? <a href="#does-using-a-standard-add-on-make-my-project-custom" id="does-using-a-standard-add-on-make-my-project-custom"></a>

No. Using a standard Add-on within the default capability does not automatically make the project Custom.

#### When does an Add-on require Custom Service? <a href="#when-does-an-add-on-require-custom-service" id="when-does-an-add-on-require-custom-service"></a>

An Add-on requires Custom Service when it needs modification beyond the default capability or when the customer requests a custom Add-on that is not currently available.

#### Can Next-Cart provide a custom Add-on? <a href="#can-next-cart-provide-a-custom-add-on" id="can-next-cart-provide-a-custom-add-on"></a>

Yes. If the currently available Add-ons do not fit the customer’s migration requirements, the customer can request a custom Add-on. Custom Add-ons are reviewed and quoted through Custom Service.

#### How does Add-on top-up pricing work? <a href="#how-does-add-on-top-up-pricing-work" id="how-does-add-on-top-up-pricing-work"></a>

If a purchased standard Add-on needs modification, the customer pays the difference between the standard Add-on price and the customized Add-on quote.

#### Are Add-ons the same as Custom Service? <a href="#are-add-ons-the-same-as-custom-service" id="are-add-ons-the-same-as-custom-service"></a>

No. Add-ons are focused features for specific migration needs. Custom Service is the broader path for customization, modification, Custom Cart handling, migration-tool adjustment, and other bespoke requirements.

#### When should I use the Data Filter Add-on? <a href="#when-should-i-use-the-data-filter-add-on" id="when-should-i-use-the-data-filter-add-on"></a>

Use the Data Filter Add-on when only selected records should migrate. Entered entity counts are used for pricing and plan capacity, not as automatic filters.

#### What if I need filtering, mapping, or configuration beyond the available Add-ons? <a href="#what-if-i-need-filtering-mapping-or-configuration-beyond-the-available-add-ons" id="what-if-i-need-filtering-mapping-or-configuration-beyond-the-available-add-ons"></a>

If the available Add-ons do not support the expected result, the requirement should be reviewed as a tailored Add-on, custom Add-on, or Custom Service requirement.
