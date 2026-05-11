# What Custom Service Handles

Custom Service is the Next-Cart path for migration projects that need tailored handling beyond the default migration tool capability or standard Add-ons. It applies when the expected target result depends on customization, modification, exclusive handling, or bespoke configuration.

This can include Add-on-related work, but Custom Service is not limited to Add-ons. It also covers Custom Platform, third-party data, custom fields, outside-system identifiers, migration-tool modification, platform-specific transformation logic, and other requirements that do not fit a standard migration path.

The purpose of Custom Service is to define a workable approach for migration requirements that need more than ordinary configuration.

### What Custom Service Means <a href="#what-custom-service-means" id="what-custom-service-means"></a>

Custom Service is required when the migration outcome depends on tailored work.

This can include:

* modifying how the migration tool handles specific data
* tailoring a standard Add-on
* creating a custom Add-on
* interpreting a Custom Platform structure
* transforming data to fit a target platform’s supported model
* preserving custom fields or outside-system identifiers
* handling third-party app, plugin, module, or extension data
* applying bespoke configuration rules
* supporting a migration outcome that cannot be reached through default settings alone

The key point is that Custom Service protects the expected result when a requirement cannot be handled through the standard path.

### Custom Service Is Broader Than Add-ons <a href="#custom-service-is-broader-than-add-ons" id="custom-service-is-broader-than-add-ons"></a>

Add-ons give customers more control over focused migration needs, such as data filtering, advanced mapping, or data configuration.

Custom Service is broader. It covers the wider set of requirements where the migration approach itself needs to be tailored, whether or not they involve an Add-on.

For example:

* filtering selected data may fit the Data Filter Add-on
* more controlled source-to-target field alignment may fit Advanced Data Mapping
* changing selected data values before migration may fit Advanced Data Configure
* modifying an Add-on beyond its default capabilities requires Custom Service
* building a custom Add-on requires Custom Service
* handling Custom Platform, app-owned data, custom fields, or migration-tool behavior belongs under Custom Service

This distinction keeps Add-ons useful without forcing every custom migration requirement into the Add-on category.

### Tailored Add-ons and Custom Add-ons <a href="#tailored-add-ons-and-custom-add-ons" id="tailored-add-ons-and-custom-add-ons"></a>

Custom Service can include Add-on-related work.

A tailored Add-on is needed when a standard Add-on must be modified beyond its default capability. For example, a customer may need filtering logic, mapping behavior, or data configuration rules that the standard Add-on cannot support through its available settings.

A custom Add-on is needed when the currently available Add-ons do not fit the customer’s migration requirements. In that case, the customer can describe the expected result, and Next-Cart reviews whether a custom Add-on can be provided.

Both tailored Add-ons and custom Add-ons are handled through Custom Service because they require customization or modification work.

### Custom Platform Handling <a href="#custom-cart-handling" id="custom-cart-handling"></a>

Custom Platform as Source Platform or Target Platform requires Custom Service.

A Custom Platform is a platform or store system that is not part of Next-Cart’s standard supported platform list. The challenge is not simply that the connection method may be different. The larger issue is that Custom Platform projects often require more interpretation before the data can be migrated safely.

Custom Platform handling may involve:

* understanding the source or target data model
* reviewing how records are stored
* identifying which data relationships must be preserved
* transforming source data into a structure the Target Platform can support
* adjusting migration logic for non-standard fields or formats
* validating whether the migrated result matches the expected business outcome

Custom Platform migration should be planned carefully because the data structure may not follow a known supported-platform pattern.

### Third-Party App, Plugin, Module, or Extension Data <a href="#third-party-app-plugin-module-or-extension-data" id="third-party-app-plugin-module-or-extension-data"></a>

Many stores rely on apps, plugins, modules, or extensions to support important business functions.

This data may affect:

* product details
* filters and merchandising
* customer segmentation
* loyalty or subscription logic
* reviews
* custom checkout behavior
* shipping or fulfillment information
* promotions or discounts
* reporting identifiers
* ERP, CRM, or automation workflows

If that data must be migrated, interpreted, transformed, or preserved beyond the standard platform model, the project requires Custom Service.

The important question is not only whether the data exists. The important question is whether that data carries business meaning that must remain usable in the Target Platform.

### Custom Fields <a href="#custom-fields" id="custom-fields"></a>

Custom fields can be important even when they look small in the source store.

They may store information used for:

* product classification
* internal merchandising
* customer segmentation
* fulfillment
* reporting
* integrations
* search and filtering
* business-specific workflows

If custom fields need to be preserved, mapped, transformed, or placed into target-supported structures, the requirement may need Custom Service.

Custom fields often require review because the Target Platform may not store or use the same type of field in the same way. The goal is to define the closest workable target result based on platform capability and business need.

### Outside-System Identifiers <a href="#outside-system-identifiers" id="outside-system-identifiers"></a>

Outside-system identifiers connect the store to systems beyond the eCommerce platform.

Examples include:

* ERP IDs
* CRM IDs
* shipping or fulfillment IDs
* subscription references
* marketplace identifiers
* product information management IDs
* accounting or reporting references
* custom customer identifiers

These values may be critical after launch because outside systems may continue relying on them.

If the migration must preserve or reposition these identifiers in a specific way, the project should be reviewed under Custom Service. Losing or misplacing these values can break downstream workflows even if the storefront appears complete.

### Platform Capability Limitations <a href="#platform-capability-limitations" id="platform-capability-limitations"></a>

Sometimes the Target Platform cannot represent source-store behavior exactly.

This can affect:

* product options and variants
* attributes
* customer groups
* order statuses
* category or collection structures
* reviews
* coupons
* CMS Pages
* Blog Posts
* SEO and URL behavior
* custom metadata
* app-supported features

Custom Service helps define a migration approach when the expected result requires tailored handling within the Target Platform’s supported capabilities.

This does not mean every source behavior can be recreated exactly. It means Next-Cart reviews the requirement, defines what can be preserved, and identifies the most suitable supported result.

### Migration-Tool Modification <a href="#migration-tool-modification" id="migration-tool-modification"></a>

Some projects require modification to how the migration tool processes data.

This may happen when the project needs:

* special transformation logic
* custom field handling
* non-standard source interpretation
* target-specific formatting rules
* custom Add-on behavior
* source data normalization
* unusual relationship preservation
* special handling for records that do not fit the standard migration model

Migration-tool modification is a Custom Service work because it changes how the migration is handled beyond the default capability.

### Bespoke Data Transformation <a href="#bespoke-data-transformation" id="bespoke-data-transformation"></a>

Bespoke transformation is needed when source data must be changed in a specific way before it can support the expected target result.

Examples may include:

* restructuring selected product data
* changing how values are grouped or interpreted
* transforming legacy fields into target-supported values
* normalizing data formats
* adjusting labels or codes used by the business
* reshaping content or metadata for the Target Platform

Some simple data adjustments may fit Advanced Data Configure. Broader transformation rules or logic that exceed default Add-on capability are handled through Custom Service.

### Custom Service and Migration Management <a href="#custom-service-and-migration-management" id="custom-service-and-migration-management"></a>

Custom Service does not automatically mean Next-Cart performs the full migration process.

Custom Service means customization or modification work is required.

The final plan may work in different ways:

* the customer purchases customization work and performs the migration themselves
* the customer includes optional migration management so Next-Cart performs the migration process
* the custom work is integrated into a Next-Cart-led migration if migration management is part of the final plan

This distinction matters because service status and execution responsibility are not always the same.

### How Custom Service Is Reviewed <a href="#how-custom-service-is-reviewed" id="how-custom-service-is-reviewed"></a>

A strong Custom Service request describes the expected result clearly.

Useful information includes:

* which data types are affected
* where the source data exists
* what the target result should look like
* which records or examples show the requirement clearly
* whether apps, plugins, modules, or extensions are involved
* whether custom fields or outside-system identifiers are involved
* whether Custom Platform is the Source Platform, Target Platform, or both
* whether the request involves an Add-on, a tailored Add-on, or a custom Add-on
* how the customer will validate that the result is acceptable

The clearer the expected outcome, the easier it is to review the request and provide a suitable quote.

### What Custom Service Does Not Guarantee <a href="#what-custom-service-does-not-guarantee" id="what-custom-service-does-not-guarantee"></a>

Custom Service provides a path for reviewing and implementing tailored handling. It does not mean every source-store behavior can always be recreated exactly in the Target Platform.

The final result still depends on:

* the quality and structure of the source data
* what the Target Platform can support
* how the requirement is defined
* whether the expected result is technically feasible
* how the customer validates the result
* whether outside systems need additional configuration beyond the migration itself

A good Custom Service plan defines the closest workable result based on the source data, target platform, and business requirement.

### When Custom Service Should Be Considered Early <a href="#when-custom-service-should-be-considered-early" id="when-custom-service-should-be-considered-early"></a>

Custom Service should be considered early when the customer already knows that the migration includes non-standard requirements.

Early review is especially important when the project involves:

* Custom Platform
* complex product structures
* app-owned or extension-owned data
* custom fields
* outside-system identifiers
* unusual order or customer data
* special transformation logic
* advanced filtering, mapping, or data configuration beyond standard Add-ons
* target-platform limitations that may affect the expected outcome

These requirements should not be left until final validation. They can shape the entire migration approach.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Custom Service handles the migration requirements that go beyond the default migration tool capability and standard Add-ons. It covers tailored Add-ons, custom Add-ons, Custom Platform handling, third-party data, custom fields, outside-system identifiers, migration-tool modification, bespoke transformation, and other exclusive handling needs.

The most important distinction is that Add-ons are focused service features, while Custom Service is the broader path for customization and modification work. Custom Service also does not automatically mean Next-Cart performs the full migration process unless migration management is included in the final plan.

Prepare Custom Service requirements around the outcome that must be preserved, not only the field or data type that needs to move. If your project involves Custom Platform, third-party logic, custom fields, outside-system identifiers, tailored Add-ons, or custom Add-ons, Live Chat can help clarify what information Next-Cart needs to review the request and prepare a suitable quote.

### FAQs <a href="#faqs" id="faqs"></a>

**What does Custom Service handle?**

Custom Service handles customization, modification, exclusive handling, and bespoke configuration needs that go beyond default migration-tool capability or standard Add-on capability.

**Is Custom Service the same as Add-ons?**

No. Add-ons are focused optional features for filtering, advanced mapping, and data configuration. Custom Service is the broader path for requirements that need customization or modification.

**Is Custom Service required for modified Add-ons?**

Yes. Any Add-on modification beyond default capability is handled through Custom Service.

**Can Next-Cart provide custom Add-ons?**

Yes. If the available Add-ons do not fit the customer’s migration requirement, the customer can request a custom Add-on. Custom Add-ons are reviewed and quoted through Custom Service.

**Is Custom Service required for Custom Platform?**

Yes. Any migration involving Custom Platform as Source Platform or Target Platform requires Custom Service.

**Does Custom Service always include migration management?**

No. Custom Service means customization or modification work is required. Migration management can be included, but it is not automatic unless included in the final plan.

**What information should I prepare for a Custom Service request?**

Prepare the expected target result, affected data types, representative examples, source data location, involved apps or custom fields, outside-system identifiers, and how you will validate the result.

**Can Custom Service recreate every source-store behavior exactly?**

Not always. The final result depends on source data quality, target platform capability, technical feasibility, and the agreed migration approach. Custom Service defines the closest workable result for the requirement.
