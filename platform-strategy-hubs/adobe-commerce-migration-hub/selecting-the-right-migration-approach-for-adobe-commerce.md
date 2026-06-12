# Selecting the Right Migration Approach for Adobe Commerce

Selecting the right migration approach for Adobe Commerce depends less on store size alone and more on how much business logic the migrated data must support after launch. A store with many simple products and standard customers may be manageable through a more direct migration path. A smaller store with company accounts, shared catalogs, negotiated pricing, staged campaigns, extension-owned fields, ERP identifiers, and multi-storefront scope may need deeper planning because each transferred record has to work inside a governed enterprise operating model.

Adobe Commerce migration planning should start with a practical distinction: some requirements are about transferring supported records, some are about coordinating the migration process, and some are about adapting data or behavior that does not fit a standard supported structure. Standard Service, Managed Service, Custom Service, and Add-ons answer different needs. Treating them as interchangeable creates weak scoping, unclear responsibility, and poor launch validation.

The strongest approach is to classify the Adobe Commerce migration burden before the service license is finalized. Product types, attribute sets, websites, stores, store views, company accounts, shared catalogs, customer groups, Content Staging, URL rewrites, integrations, and custom fields should be reviewed as migration-planning signals, not as isolated technical details.

### Start With the Business Logic Behind the Data <a href="#start-with-the-business-logic-behind-the-data" id="start-with-the-business-logic-behind-the-data"></a>

Adobe Commerce is often selected because the merchant needs more than basic product, customer, order, and content transfer. It may need B2B account management, company-level buying permissions, shared catalog pricing, quote workflows, purchase orders, content scheduling, scoped storefronts, advanced catalog structures, and integrations with external business systems.

Those capabilities change the approach decision. The question is not only whether entities can be migrated. The question is whether the migrated data can support the intended Adobe Commerce behavior after it reaches the target store.

| Planning signal                   | What to clarify before choosing the approach                                                                           | Why it affects the service path                                                                            |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| B2B company structure             | Whether source customers represent individuals, companies, departments, buyers, approvers, or account administrators.  | Company relationships and buyer roles may require deeper review than ordinary customer migration.          |
| Shared catalog and custom pricing | Whether companies need different product visibility, price lists, negotiated terms, or group-based access.             | Pricing and visibility rules may require mapping, configuration, or Custom Service review.                 |
| Scope model                       | Whether the target will use multiple websites, stores, or store views.                                                 | Scope affects product values, content, URLs, configuration-sensitive data, and storefront validation.      |
| Catalog complexity                | Whether products use configurable, bundle, grouped, downloadable, virtual, or custom structures.                       | Product samples must prove that source catalog meaning survives in Adobe Commerce.                         |
| Content timing                    | Whether promotions, CMS Pages, catalog rules, or merchandising updates are scheduled around launch.                    | Content Staging and campaign timing may affect cutover planning and validation responsibility.             |
| Integrations and custom fields    | Whether ERP, PIM, CRM, warehouse, tax, payment, shipping, analytics, or custom modules depend on migrated identifiers. | Unsupported or outside-system data may require Add-ons or Custom Service rather than standard assumptions. |

If these signals are light and the source structure is supported, Standard Service may be sufficient. If the same data transfer requires migration coordination, sequencing, or guided validation, Managed Service may be more appropriate. If the source behavior cannot be represented safely through supported structures alone, Custom Service should be reviewed.

### When Standard Service Is Usually the Right Starting Point <a href="#when-standard-service-is-usually-the-right-starting-point" id="when-standard-service-is-usually-the-right-starting-point"></a>

Standard Service is usually the right starting point when the migration path is supported, the source data fits expected structures, and the merchant can validate the target store without extensive bespoke planning. This does not mean the store must be small. It means the migration requirements are clear enough to fit the standard service scope.

For Adobe Commerce, Standard Service may be suitable when products, categories, customers, orders, reviews, CMS Pages, Blog Posts, and other selected entities map cleanly into supported Adobe Commerce structures. It can also be suitable when B2B and enterprise features are not part of the launch scope, or when they will be configured separately in the target store without requiring custom source-data transformation.

A Standard Service path is strongest when the merchant can answer these questions with confidence:

| Standard Service readiness question                                  | Passing signal                                                                                                                               |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Are the required entities supported for the selected migration path? | The required data types fit the available service scope without unusual source behavior.                                                     |
| Are product types and variants understood?                           | Representative simple, configurable, bundle, grouped, virtual, or downloadable products can be tested through Demo Migration.                |
| Is the target scope model already defined?                           | Websites, stores, and store views are known before Full Migration.                                                                           |
| Are customer and order expectations straightforward?                 | Customer records and order history do not depend on complex company structures, custom approval logic, or unsupported account relationships. |
| Are custom fields and extension data non-critical or out of scope?   | Unsupported fields can be excluded, recreated manually, or handled later without launch risk.                                                |
| Can the merchant validate the result internally?                     | The team can review sample data, compare records, and approve migration readiness without managed coordination.                              |

Standard Service should not be stretched to cover unclear enterprise logic. If a source store has wholesale tiers, company-specific pricing, custom B2B portals, staged promotional rules, heavily customized checkout flows, or extension-owned identifiers that must remain operational after migration, those examples should be escalated before assuming a standard approach is safe.

### When Managed Service Adds Value <a href="#when-managed-service-adds-value" id="when-managed-service-adds-value"></a>

Managed Service is appropriate when the migration is structurally supported but the merchant needs more guidance, coordination, or operational support throughout the process. The need for Managed Service often comes from project risk, internal capacity, timing pressure, stakeholder coordination, or validation complexity rather than from unsupported data alone.

Adobe Commerce projects commonly benefit from Managed Service when several business teams must participate in migration approval. Catalog managers may own product and attribute review. B2B sales teams may own company and pricing expectations. Marketing may own CMS Pages, staged campaigns, and URL priorities. Operations may own inventory and fulfillment dependencies. Finance, ERP, or IT teams may own identifiers and order-history expectations.

| Managed Service signal                                 | Why it matters in Adobe Commerce                                                                                 |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Multiple stakeholder groups must approve the migration | Adobe Commerce data often affects sales, catalog, marketing, operations, IT, and finance workflows.              |
| Demo Migration needs careful sample selection          | Sample records should include B2B, shared catalog, catalog complexity, scope, URL, inventory, and content cases. |
| Launch timing is sensitive                             | Recent Data Migration, Re-Migration, campaign timing, and operational freeze windows need coordination.          |
| The merchant lacks internal migration-review bandwidth | Adobe Commerce validation can be too broad for a team that has not assigned owners.                              |
| Standard structures are supported but complex          | Guided planning can reduce risk without turning the project into a Custom Service requirement.                   |

Managed Service should not be used as a vague label for every difficult case. If the issue is coordination, sequencing, validation support, or project handling around otherwise supported data, Managed Service is likely the right review path. If the issue is unsupported data, custom logic, custom migration behavior, or source structures that do not fit Adobe Commerce safely, Custom Service should be reviewed instead.

### When Custom Service Should Be Reviewed <a href="#when-custom-service-should-be-reviewed" id="when-custom-service-should-be-reviewed"></a>

Custom Service should be reviewed when the Adobe Commerce migration requires bespoke handling beyond a standard supported migration path. This may involve unsupported source structures, extension-owned data, custom fields, outside-system identifiers, custom B2B logic, company-specific price rules, nonstandard order relationships, custom checkout behavior, or a Custom Platform source that cannot be safely interpreted without additional analysis.

Custom Service is especially important for Adobe Commerce because the target platform can represent complex commercial rules. If the source store uses custom wholesale logic, account hierarchies, dealer portals, quote workflows, price lists, purchasing permissions, ERP-specific IDs, nonstandard product relationships, or source-side extensions that create business-critical fields, the migration plan must decide what can transfer, what must be configured in Adobe Commerce, what requires custom handling, and what should be excluded or rebuilt.

| Custom Service trigger                                                       | Adobe Commerce reason to review                                                                                                              |
| ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Source company data does not match Adobe Commerce company-account structures | Business customers may need company administrators, company users, roles, account status, and permissions rather than flat customer records. |
| Shared catalog pricing must be recreated from source-specific rules          | Product visibility and custom pricing may not be simple product-price fields.                                                                |
| Custom B2B workflows affect order placement                                  | Quote, purchase order, approval, payment, shipping, or credit behavior may require target-side configuration and custom scoping.             |
| Extension-owned data is business-critical                                    | Source modules may store fields that standard entity transfer does not interpret as native Adobe Commerce data.                              |
| External systems depend on source identifiers                                | ERP, PIM, CRM, warehouse, accounting, marketplace, or analytics IDs may need preservation or mapped placement.                               |
| The Source Platform is a Custom Platform                                     | The source structure may require bespoke analysis before the migration path can be safely defined.                                           |
| Data transformation is more than field renaming                              | Custom logic may be needed when values must be split, merged, normalized, derived, or interpreted according to business rules.               |

Custom Service does not automatically mean Next-Cart manages every operational step or executes every related setup task. It means the migration scope needs custom review and bespoke handling where standard assumptions are not enough. Migration management is included only when it is part of the final service plan.

### How Add-ons Fit Into the Approach <a href="#how-add-ons-fit-into-the-approach" id="how-add-ons-fit-into-the-approach"></a>

Add-ons are optional service features for filtering, mapping, or data configuration. They are not a substitute for Custom Service when the requirement depends on unsupported logic or bespoke source interpretation. They are also not the same as Managed Service, because they affect migration behavior rather than overall project coordination.

In an Adobe Commerce migration, Add-ons may be relevant when the merchant needs a defined enhancement to the migration scope. For example, a Data Filter Add-on may help narrow which historical records should be migrated. Advanced Data Mapping may help align source fields with target meanings when the mapping is still within supported logic. Advanced Data Configure may help adjust supported configuration-related behavior where the service scope allows it.

The distinction matters because Adobe Commerce complexity can make merchants overuse Add-ons as a catch-all answer. If the source requirement is supported but needs optional filtering, mapping, or configuration, Add-ons may be appropriate. If the requirement involves custom B2B account logic, source-specific shared catalog rules, unsupported extension tables, or custom workflows, Custom Service should be reviewed.

| Requirement type                                                    | Better review path                                 | Reason                                                                            |
| ------------------------------------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------- |
| Exclude old order history before a certain date                     | Data Filter Add-on                                 | Filtering can be a defined migration-scope adjustment.                            |
| Map a supported source field into an appropriate target field       | Advanced Data Mapping                              | The data meaning is clear and fits supported migration logic.                     |
| Adjust supported configuration-related behavior                     | Advanced Data Configure                            | The need is configuration-oriented and within service scope.                      |
| Preserve custom company-pricing rules from a legacy portal          | Custom Service                                     | The requirement depends on bespoke commercial logic, not only field mapping.      |
| Carry extension-owned identifiers needed by an ERP                  | Custom Service, possibly with Add-ons after review | The identifier may need custom placement, transformation, or exclusion decisions. |
| Migrate from a Custom Platform with undocumented data relationships | Custom Service                                     | The source structure must be analyzed before the scope can be trusted.            |

### Entity Points Should Reflect the Selected Scope <a href="#entity-points-should-reflect-the-selected-scope" id="entity-points-should-reflect-the-selected-scope"></a>

Entity Points measure migration scope through the selected Entity Points Plan. They should be considered after the merchant understands which entities matter for the Adobe Commerce launch. A large order history, extensive product catalog, many customers, CMS Pages, Blog Posts, reviews, categories, or related records can affect the required plan.

Entity Points should not be confused with complexity. A store can have many entities but a straightforward supported structure. Another store can have fewer records but heavy B2B, custom pricing, custom fields, and integration requirements. The first case may need the right Entity Points Plan but still remain within Standard Service. The second case may require Custom Service review even with fewer records.

For Adobe Commerce, Entity Points planning should be connected to launch intent. If old order history is not needed in the target store, filtering may reduce unnecessary scope. If company-facing account history, quote context, high-value product records, CMS Pages, Blog Posts, or SEO-critical content are important, those records should be included deliberately rather than added without validation ownership.

### Recent Data Migration and Re-Migration Planning <a href="#recent-data-migration-and-re-migration-planning" id="recent-data-migration-and-re-migration-planning"></a>

Recent Data Migration and Re-Migration are especially important for Adobe Commerce projects because launch preparation often takes time. During that period, the Source Platform may continue receiving new customers, orders, product updates, inventory changes, content updates, or pricing changes. A one-time transfer may not be enough if the source store remains active while the target store is reviewed.

Recent Data Migration is used to bring newly created or recently changed data from the Source Platform into the Target Platform after the main migration activity. This can help reduce the gap between the migration run and launch. Re-Migration is used when the migration needs to be run again, often after configuration changes, corrections, or a revised scope.

Adobe Commerce merchants should plan these services before launch timing becomes urgent. B2B stores should pay particular attention to new company accounts, customer changes, quote-related activity, order history, catalog updates, shared catalog adjustments, URL changes, and campaign-sensitive content. If these areas are active during the migration window, the launch plan should define what will be transferred once, what may need Recent Data Migration, and what would justify Re-Migration.

### A Practical Service-Path Decision Framework <a href="#a-practical-service-path-decision-framework" id="a-practical-service-path-decision-framework"></a>

The safest Adobe Commerce approach is selected by matching the migration condition to the kind of work required. The same project may include more than one layer: Standard Service for supported entities, Add-ons for filtering or mapping, Managed Service for coordination, and Custom Service for bespoke requirements.

| Migration condition                                                               | Service path to review | Reason                                                                                       |
| --------------------------------------------------------------------------------- | ---------------------- | -------------------------------------------------------------------------------------------- |
| Supported entities, clear source structure, limited custom logic                  | Standard Service       | The migration path can focus on transferring supported records and merchant-led validation.  |
| Supported structure but complex coordination or limited internal bandwidth        | Managed Service        | The data may be supported, but the process needs guided planning and review support.         |
| Need to exclude, filter, map, or configure supported data in a defined way        | Add-ons                | Optional service features may adjust the migration without changing the whole service model. |
| B2B company structures need bespoke interpretation                                | Custom Service         | Flat customer migration may not preserve account governance or buyer relationships.          |
| Shared catalog pricing depends on source-specific rules                           | Custom Service         | Target behavior may require custom logic, not only record transfer.                          |
| Custom Platform source, undocumented structures, or extension-owned business data | Custom Service         | The source must be analyzed before safe migration assumptions are made.                      |
| Active source store continues changing during target validation                   | Recent Data Migration  | New or changed records may need to be brought over closer to launch.                         |
| Scope or configuration changed after a migration run                              | Re-Migration           | A repeat run may be needed after correction, restructuring, or revised service scope.        |

A merchant should not choose the highest-touch option by default. The goal is to choose the narrowest reliable service path that still protects launch confidence. Over-scoping wastes time and budget. Under-scoping creates avoidable risk. Adobe Commerce planning should make the risk visible before the migration path is finalized.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Adobe Commerce migration approach is determined by the relationship between supported data, enterprise behavior, and project responsibility. Standard Service can be appropriate when the migration path is supported and the source structure is clear. Managed Service is valuable when the migration needs coordination, sample planning, stakeholder alignment, or guided validation. Custom Service should be reviewed when company data, shared catalogs, custom pricing, integrations, extension-owned fields, or Custom Platform sources require bespoke handling. Add-ons should be used for defined filtering, mapping, or configuration needs, not as a replacement for Custom Service.

Adobe Commerce rewards careful planning because its strongest capabilities are structural. Company accounts, shared catalogs, scoped storefronts, Content Staging, catalog complexity, and integrations can all shape whether migrated data works as intended after launch. A reliable migration approach should match that operational reality before Full Migration begins.

Review the Adobe Commerce target structure, service scope, Entity Points Plan, Add-ons, Custom Service triggers, Recent Data Migration needs, and Re-Migration risk before finalizing the service license. Include representative B2B, catalog, scope, pricing, content, URL, and integration examples in the Demo Migration so the selected approach is based on evidence rather than assumptions.

### FAQs <a href="#faqs" id="faqs"></a>

**Can an Adobe Commerce migration use Standard Service?**

Yes. Standard Service can be appropriate when the selected migration path is supported, the required entities fit the service scope, and the merchant can validate the target store without bespoke source-data handling. B2B, shared catalog, custom pricing, or integration complexity should be reviewed before assuming Standard Service is enough.

**When should Managed Service be considered for Adobe Commerce?**

Managed Service should be considered when the data structure is supported but the migration needs stronger coordination, stakeholder alignment, sample planning, or validation support. Adobe Commerce projects often involve catalog, sales, marketing, operations, IT, and finance teams, which can make process management important even when the underlying data is supported.

**When does Adobe Commerce require Custom Service review?**

Custom Service should be reviewed when the source store includes unsupported structures, company-specific pricing logic, custom B2B workflows, extension-owned fields, outside-system identifiers, custom integrations, or a Custom Platform source. These cases may require bespoke handling rather than standard transfer assumptions.

**Are Add-ons the same as Custom Service?**

No. Add-ons are optional service features for filtering, mapping, or data configuration. Custom Service is broader and applies when unsupported behavior, custom source logic, bespoke field handling, or Custom Platform interpretation is needed. A project may use both, but they solve different problems.

**How do Entity Points affect the Adobe Commerce migration approach?**

Entity Points help determine the required Entity Points Plan for the selected migration scope. They do not fully measure complexity. A store with many standard records may still fit Standard Service, while a smaller store with custom B2B logic or integration-owned data may require Custom Service review.

**Should Recent Data Migration be planned before launch?**

Yes, when the Source Platform remains active during target review. Adobe Commerce projects can involve new orders, customers, company accounts, product updates, pricing changes, content edits, and URL changes during the migration window. Recent Data Migration helps reduce the gap between the main migration and launch.
