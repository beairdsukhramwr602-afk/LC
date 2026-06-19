# What Custom Service Handles

Custom Service is the Next-Cart service model for migration requirements that need custom-scoped review, modification, bespoke handling, or implementation work beyond standard service capability. It applies when the expected target-store result cannot be planned safely through a supported migration path, standard migration handling, and available Standard Add-ons alone.

Custom Service does not mean every part of the migration becomes custom. A project may only need Custom Service for one critical area, such as a modified Add-on, app-owned product data, a Custom Platform source, custom fields, outside-system identifiers, or a specific transformation rule. The value of Custom Service is to identify the parts that need tailored handling, define what can be supported, quote the required work, and set clearer expectations before execution.

Custom Service should be considered when the migration question changes from “which standard settings should be used?” to “how should this requirement be reviewed, adapted, or built so the migrated target store can support the intended outcome?”

### What Custom Service Is Designed to Solve <a href="#what-custom-service-is-designed-to-solve" id="what-custom-service-is-designed-to-solve"></a>

Custom Service is used when the migration depends on data meaning, structure, logic, or platform conditions that require deeper review than standard service capability can provide. It helps turn non-standard requirements into a scoped migration plan.

Custom Service may be needed for:

* Custom Platform handling as the Source Platform, Target Platform, or both;
* custom fields, custom attributes, or non-standard source-store structures;
* app, plugin, module, extension, or third-party data;
* outside-system identifiers used by ERP, CRM, fulfillment, accounting, PIM, reporting, marketplace, subscription, or other business systems;
* Tailored Add-ons that modify Standard Add-on behavior;
* Custom Add-ons created for project-specific filtering, mapping, or configuration needs;
* custom migration logic adjustment;
* bespoke transformation, normalization, splitting, combining, renaming, or restructuring of data;
* target-store requirements that need review against Target Platform capability;
* Expert Handle scope when Next-Cart experts are expected to perform migration actions as part of the agreed Custom Service plan.

The practical goal is not to promise that every source-store behavior can be copied exactly into the Target Platform. The practical goal is to clarify what the source data means, what the target store needs to support, what the Target Platform can accept, and what custom work is required to produce the closest workable result.

### Custom Service, Add-ons, and Expert Handle <a href="#custom-service-add-ons-and-expert-handle" id="custom-service-add-ons-and-expert-handle"></a>

Custom Service is often confused with Add-ons or Expert Handle. These concepts can work together, but they answer different questions.

| Concept          | Main role                                                                                                                          | When it matters                                                                                |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Standard Add-ons | Focused optional service features for filtering, advanced mapping, or data configuration.                                          | The required result fits available Add-on settings and supported behavior.                     |
| Tailored Add-ons | Modified versions of Standard Add-ons.                                                                                             | A Standard Add-on is close to the requirement but needs custom adjustment.                     |
| Custom Add-ons   | Project-specific Add-ons reviewed and quoted through Custom Service.                                                               | No available Standard Add-on fits the required outcome.                                        |
| Custom Service   | Custom-scoped service for bespoke handling, modification, Custom Platform review, custom logic, or non-standard data requirements. | The migration requirement needs work beyond standard capability.                               |
| Expert Handle    | Expert-led execution scope inside Custom Service when included in the agreed plan.                                                 | The customer wants Next-Cart experts to perform migration actions for a custom-scoped project. |

Add-ons focus on what should be filtered, mapped, or configured. Custom Service handles the broader situation when the Add-on must be modified, a new Custom Add-on is needed, unsupported data must be interpreted, or the migration approach itself needs custom handling.

Expert Handle is separate from custom scope. Custom Service without Expert Handle can still be customer-led for migration actions. Custom Service with Expert Handle allows Next-Cart experts to perform migration actions based on the customer’s request and agreed service scope. In both cases, the customer remains responsible for final result verification and migration outcome.

### Custom Platform Handling <a href="#custom-platform-handling" id="custom-platform-handling"></a>

Custom Platform handling is one of the clearest reasons to use Custom Service. It applies when the Source Platform, Target Platform, or both are not part of Next-Cart’s standard supported platform list, or when a store uses a system that behaves differently from the supported platform path.

A Custom Platform project is not only a connection question. The review must clarify how the store data is structured, how records relate to one another, how exports or database access can be provided, and how the expected data should be shaped for the target store.

Custom Platform review may involve:

* identifying the source-store data model;
* reviewing available data exports, databases, files, APIs, or access methods;
* understanding product, customer, order, content, and relationship structures;
* checking how categories, collections, menus, CMS Pages, Blog Posts, reviews, coupons, or other supporting data are represented;
* determining whether the Target Platform can support the expected result;
* defining required mapping, transformation, or custom migration logic;
* confirming what the customer should validate after migration.

A strong Custom Platform request includes sample records, source-store structure details, target-store expectations, and examples of the business result that must be preserved. Without those details, it is difficult to determine whether the target result is feasible, what custom work is needed, or how the project should be quoted.

### Third-Party Data, Custom Fields, and Outside-System Identifiers <a href="#third-party-data-custom-fields-and-outside-system-identifiers" id="third-party-data-custom-fields-and-outside-system-identifiers"></a>

Many stores depend on data that does not belong cleanly to the standard platform data model. That data may come from apps, plugins, modules, extensions, custom fields, integrations, or external business systems. It can be easy to overlook because it may not appear as a standard Product, Customer, Order, CMS Page, or Blog Posts record, but it may carry important business meaning after migration.

Third-party data can affect:

* product merchandising, options, attributes, bundles, subscriptions, or memberships;
* customer segmentation, loyalty, rewards, or account classification;
* shipping, fulfillment, warehouse, or delivery workflows;
* promotions, coupons, pricing rules, or discount logic;
* reviews, ratings, product recommendations, or merchandising displays;
* ERP, CRM, accounting, PIM, marketplace, automation, or reporting workflows.

Custom fields and outside-system identifiers often require the same level of care. A custom product field may support search or filtering. A customer-level identifier may connect the store to a CRM. An order reference may be needed for fulfillment, accounting, or customer service. If these values are lost, renamed incorrectly, placed in the wrong target-store location, or disconnected from the right record, the storefront may look acceptable while operational workflows fail.

Custom Service should be considered when these records or values need to be:

* preserved in the target store;
* mapped into target-supported fields;
* transformed into a different structure;
* combined, split, normalized, renamed, or reformatted;
* kept available for reporting or integration purposes;
* connected to the right migrated Product, Customer, Order, CMS Page, Blog Posts, or supporting record;
* validated as part of the final target-store result.

The most useful review question is not only whether the data exists. The stronger question is what business role the data plays and how the target store needs to use it after migration.

### Platform Capability and Target-Store Fit <a href="#platform-capability-and-target-store-fit" id="platform-capability-and-target-store-fit"></a>

Custom Service can be needed when the Source Platform and Target Platform represent store data differently. A field, relationship, option type, identifier, or workflow that exists in the source store may not have a direct equivalent in the Target Platform.

Platform differences can affect:

* product options, variants, attributes, bundles, grouped products, or configurable products;
* customer groups, company accounts, customer tags, or account structures;
* order statuses, historical order details, invoices, refunds, or customer-service records;
* categories, collections, menus, navigation, or merchandising structure;
* reviews, coupons, CMS Pages, Blog Posts, and content relationships;
* SEO fields, URLs, redirects, metadata, or content hierarchy;
* app-owned records, extension data, plugin data, metafields, custom attributes, or other platform-specific structures.

Custom Service does not remove Target Platform limitations. It helps review what the Target Platform can support, what needs to be adapted, and what result the customer should expect. In some cases, the right outcome is a direct migration. In other cases, the workable outcome may be a transformed structure, a mapped equivalent, a partial preservation of business meaning, or a recommendation to handle some data outside the migration scope.

This is especially important when a requirement sounds simple but depends on platform behavior. For example, “keep product options” may require review of how the Source Platform stores options, how the Target Platform supports variants or custom fields, whether option relationships affect orders, and whether the target store can reproduce the same buying experience.

### Custom Migration Logic and Bespoke Transformation <a href="#custom-migration-logic-and-bespoke-transformation" id="custom-migration-logic-and-bespoke-transformation"></a>

Custom migration logic is needed when standard migration behavior cannot produce the intended result. The requirement may involve how records are matched, how values are transformed, how relationships are preserved, or how the target-store structure should be built.

Custom logic or bespoke transformation may be needed when customers need to:

* combine several source fields into one target field;
* split one source value into multiple target fields;
* normalize inconsistent values before migration;
* convert source-store statuses into target-store statuses;
* preserve product, customer, order, or content relationships that do not map directly;
* keep outside-system identifiers connected to migrated records;
* reshape app, plugin, module, or extension data into a target-supported format;
* apply business-specific rules that are not available through standard settings or Standard Add-ons.

A good custom-logic request should describe the source condition, the expected target result, and the validation rule. For example, “map source order statuses into these target statuses” is stronger than “fix order statuses.” “Preserve ERP product IDs in a target-supported field connected to each product” is stronger than “keep ERP data.”

Custom Service works best when the requirement is specific enough to scope. Vague cleanup goals, broad “make it work” requests, or undefined expectations make it harder to quote the work and harder for the customer to validate the result.

### Preparing a Custom Service Request <a href="#preparing-a-custom-service-request" id="preparing-a-custom-service-request"></a>

A Custom Service request should give Next-Cart enough information to understand the source-store condition, the target-store expectation, and the business reason behind the requirement.

Customers should prepare:

| Information to prepare                                          | Why it matters                                                                                                                                   |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Source Platform and Target Platform details                     | Defines the migration path and platform capability context.                                                                                      |
| Sample records                                                  | Shows the exact data structure, values, and relationships involved.                                                                              |
| Expected target-store result                                    | Clarifies what the customer wants the migrated result to look like.                                                                              |
| Business reason                                                 | Explains why the data or behavior matters after migration.                                                                                       |
| Affected data types                                             | Identifies whether the requirement affects Products, Customers, Orders, CMS Pages, Blog Posts, Add-ons, third-party data, or supporting records. |
| Related apps, plugins, modules, extensions, or external systems | Helps detect data that may not belong to the standard platform data model.                                                                       |
| Validation examples                                             | Defines how the customer will confirm whether the custom-scoped result is acceptable.                                                            |

The strongest Custom Service request connects the requirement to a real outcome. A request to “migrate custom fields” should identify which fields matter, where they appear in the source store, where they should appear in the target store, and how the customer will verify them. A request to “handle app data” should identify the app, the data involved, the records affected, and whether the target store has a supported structure for that data.

### What Custom Service Does Not Guarantee <a href="#what-custom-service-does-not-guarantee" id="what-custom-service-does-not-guarantee"></a>

Custom Service creates a review and implementation path for custom-scoped requirements, but it does not guarantee that every source-store behavior can be reproduced exactly in the Target Platform.

Custom Service does not automatically guarantee:

* identical behavior between different platforms;
* support for every app, plugin, module, extension, or third-party data structure;
* preservation of every custom field in the same format or location;
* exact recreation of source-store workflows that the Target Platform does not support;
* Expert Handle unless it is included in the agreed Custom Service scope;
* launch readiness without customer validation;
* migration of unclear, inaccessible, inconsistent, or undocumented data.

The right expectation is practical fit. Custom Service helps define what can be supported, what needs adjustment, what may need a workaround, and what the customer should validate before relying on the migrated result.

### Common Custom Service Misunderstandings <a href="#common-custom-service-misunderstandings" id="common-custom-service-misunderstandings"></a>

#### “Custom Service is only for Custom Platforms.” <a href="#custom-service-is-only-for-custom-platforms" id="custom-service-is-only-for-custom-platforms"></a>

No. Custom Platform handling is one important Custom Service case, but Custom Service can also apply to custom fields, third-party data, outside-system identifiers, modified Add-ons, Custom Add-ons, custom migration logic, bespoke transformation, or other non-standard requirements.

#### “Custom Service always means Next-Cart performs the migration actions.” <a href="#custom-service-always-means-next-cart-performs-the-migration-actions" id="custom-service-always-means-next-cart-performs-the-migration-actions"></a>

No. Custom Service defines custom-scoped work. Expert Handle defines expert-led execution when included in the agreed Custom Service plan. Custom Service without Expert Handle can still be customer-led for migration actions.

#### “Using an Add-on means the project is Custom Service.” <a href="#using-an-add-on-means-the-project-is-custom-service" id="using-an-add-on-means-the-project-is-custom-service"></a>

No. Standard Add-ons can be used with Standard Service, Managed Service, or Custom Service when their available settings and supported behavior fit the requirement. Custom Service becomes relevant when an Add-on must be modified, a Custom Add-on is requested, or the broader requirement needs custom handling.

#### “Custom Service can force the Target Platform to support anything.” <a href="#custom-service-can-force-the-target-platform-to-support-anything" id="custom-service-can-force-the-target-platform-to-support-anything"></a>

No. Target Platform capability still matters. Custom Service helps review the closest workable result, but it does not remove platform limitations.

#### “Small custom fields do not need review.” <a href="#small-custom-fields-do-not-need-review" id="small-custom-fields-do-not-need-review"></a>

Not always. A small custom field can carry important merchandising, fulfillment, reporting, or integration meaning. If it matters after migration, it should be reviewed before execution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Custom Service handles migration requirements that need custom-scoped review, modification, bespoke handling, or implementation work beyond standard service capability. It is used for Custom Platform handling, custom fields, third-party data, outside-system identifiers, Tailored Add-ons, Custom Add-ons, custom migration logic, and target-store requirements that need deeper platform-fit review.

Custom Service is most effective when the expected result is clearly described. Customers should prepare sample records, business context, target-store expectations, affected data types, related apps or systems, and validation examples before requesting a quote. If a requirement cannot be clearly matched to Standard Service, Managed Service, a Standard Add-on, or an available platform capability, Live Chat can help clarify whether Custom Service is the right path.

### FAQs <a href="#faqs" id="faqs"></a>

**What does Custom Service handle?**

Custom Service handles migration requirements that need custom-scoped review, modification, bespoke handling, or work beyond standard service capability. This can include Custom Platform handling, custom fields, third-party data, Tailored Add-ons, Custom Add-ons, custom migration logic, and outside-system identifiers.

**Is Custom Service only for Custom Platforms?**

No. Custom Platform handling is one Custom Service case, but Custom Service also applies to non-standard store data, modified Add-ons, custom Add-ons, custom fields, third-party data, custom migration logic, and other project-specific requirements.

**Does Custom Service always include Expert Handle?**

No. Expert Handle is included only when it is part of the agreed Custom Service scope. Custom Service without Expert Handle can still be customer-led for migration actions.

**How is Custom Service different from Add-ons?**

Add-ons handle focused filtering, mapping, or data configuration needs. Custom Service handles broader or modified requirements that need custom-scoped review, bespoke handling, custom implementation, Custom Platform handling, or custom migration logic.

**What is a Tailored Add-on?**

A Tailored Add-on is a modified version of a Standard Add-on. It is handled through Custom Service because the available Standard Add-on behavior needs adjustment beyond supported settings.

**What is a Custom Add-on?**

A Custom Add-on is a project-specific Add-on requested when available Standard Add-ons do not fit the customer’s required outcome. It is reviewed and quoted through Custom Service.

**What should customers prepare before requesting Custom Service?**

Customers should prepare sample records, source-store structure details, target-store expectations, affected data types, related apps or systems, business reasons, and validation examples.

**Can Custom Service recreate every source-store behavior exactly?**

No. Custom Service helps review what can be supported and how the target-store result can be shaped, but the final result still depends on source data condition, Target Platform capability, agreed scope, and customer validation.
