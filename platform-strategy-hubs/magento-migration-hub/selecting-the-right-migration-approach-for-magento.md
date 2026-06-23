# Selecting the Right Migration Approach for Magento

A Magento migration approach should be selected by matching the store’s structural burden to the right level of service responsibility. Record volume matters, but Magento decisions are often shaped more strongly by product types, configurable product relationships, attributes, attribute sets, website/store/store-view scope, URL rewrites, inventory behavior, customer groups, extension-owned data, and custom business logic.

The right approach should explain what can move through a supported migration path, what needs Add-ons, what requires Managed Service involvement, what belongs in Custom Service, and how the Entity Points Plan should support the intended scope. It should also define how Demo Migration results will be used before Full Migration and when Additional Migration Options may be needed close to launch.

### Start with Magento Complexity, Not Only Entity Volume <a href="#start-with-magento-complexity-not-only-entity-volume" id="start-with-magento-complexity-not-only-entity-volume"></a>

Entity volume affects service license planning, but Magento complexity usually comes from relationships and behavior. A smaller source store can require careful planning if it has configurable products, heavily customized attributes, multiple store views, extension-owned order fields, external IDs, or inventory rules. A larger store can be more straightforward when products, customers, orders, content, and URLs follow clean structures.

Use the first review to separate size from structural difficulty.

| Review area                | Lower-complexity signal                                                | Higher-complexity signal                                                                                                                    |
| -------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog model              | Mostly simple products, ordinary categories, and consistent images.    | Configurable, bundle, grouped, virtual, downloadable, custom-option, or extension-shaped product behavior.                                  |
| Attribute structure        | Clean product fields with consistent labels and values.                | Many custom attributes, duplicate values, unclear attribute sets, or values used for search and layered navigation.                         |
| Store scope                | One website, one store, and one store view.                            | Multiple websites, stores, store views, languages, localized URLs, or scope-specific values.                                                |
| Customer and order context | Customer and order records are needed mainly for historical reference. | Customer groups, custom statuses, support references, refunds, invoices, shipments, or external identifiers remain operationally important. |
| Inventory behavior         | One source of stock quantity with simple selling availability.         | Warehouses, store pickup, drop shipping, source-level stock, reservations, or ERP-managed availability.                                     |
| Extension and custom data  | Most records use native source structures.                             | Extension-owned records, custom fields, custom database tables, Custom Platform behavior, or bespoke business rules define data meaning.    |

The migration approach should match the highest-risk part of the store. A Magento project can use Standard Service for compatible entities while using Add-ons or Custom Service for specific requirements that need additional handling.

### Use Standard Service When the Migration Path Is Structurally Compatible <a href="#use-standard-service-when-the-migration-path-is-structurally-compatible" id="use-standard-service-when-the-migration-path-is-structurally-compatible"></a>

Standard Service is usually the right starting point when the source data fits supported entities and the Magento Target Store can accept those entities without bespoke interpretation. It works best when the customer can self-perform the migration process on the Next-Cart website, review Demo Migration results, and proceed to Full Migration after representative records behave correctly.

Standard Service is a strong fit when:

* products, categories, customers, orders, images, manufacturers, CMS Pages, Blog Posts, or other selected entities fit a supported migration path;
* the target website, store, and store-view structure is already clear;
* product types and configurable-product relationships are predictable enough for standard mapping;
* attributes and attribute sets do not require broad restructuring;
* inventory does not depend on unsupported warehouse, marketplace, or ERP logic;
* customer and order history can migrate for reference without recreating every source-side workflow;
* SEO-sensitive URLs and redirects can be checked through representative samples;
* no source extension or custom module controls critical data meaning that must be preserved exactly.

Standard Service should not be treated as a shallow option. It can be appropriate for substantial Magento projects when data structures are compatible and the customer can validate the result with confidence. The boundary is responsibility: Standard Service does not replace unsupported custom-logic review, extension-data interpretation, bespoke target behavior planning, or final validation ownership.

### Use Managed Service When Compatible Work Needs Expert-Led Execution <a href="#use-managed-service-when-compatible-work-needs-expert-led-execution" id="use-managed-service-when-compatible-work-needs-expert-led-execution"></a>

Managed Service is better when the migration path is compatible but the customer wants Next-Cart to handle more of the migration process, execution coordination, review support, or launch-window handling. This is common when the Magento project has a large entity scope, multiple stakeholders, limited internal migration capacity, or a need for guided Demo Migration and Full Migration coordination.

Managed Service is a strong fit when:

* the customer prefers Next-Cart-led execution rather than self-performing each step;
* the store has many entity types or a large review workload;
* Demo Migration findings need structured interpretation before Full Migration;
* product, URL, customer, order, content, and inventory checks require coordinated ownership;
* the source store remains active close to launch;
* mapping or configuration decisions may need expert review before the final run;
* the project needs a clearer migration operating plan rather than only technical access.

Managed Service is not the same as Custom Service. A Magento store can need Managed Service because of operational burden, even when the data is structurally compatible. A store can also require Custom Service even if the customer is comfortable performing available migration actions manually, because the underlying issue is unsupported data logic rather than execution responsibility.

### Use Add-ons for Compatible Filtering, Mapping, or Configuration Needs <a href="#use-add-ons-for-compatible-filtering-mapping-or-configuration-needs" id="use-add-ons-for-compatible-filtering-mapping-or-configuration-needs"></a>

Add-ons are optional service features for compatible migration work that needs more precise filtering, mapping, or configuration support. They are useful when the data can be handled within a supported migration path but needs additional control.

| Need                                      | Relevant option                    | Magento example                                                                                                                 |
| ----------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Select which records move                 | Data Filter Add-on                 | Migrate active products, selected order statuses, specific customer groups, recent historical orders, or chosen content groups. |
| Align supported fields more precisely     | Advanced Data Mapping              | Map source fields into Magento-compatible product attributes, customer fields, order references, or content fields.             |
| Configure compatible target behavior      | Advanced Data Configure            | Apply agreed target configuration behavior for selected migrated records when supported by the migration path.                  |
| Adjust an Add-on beyond standard behavior | Tailored Add-ons or Custom Add-ons | Refine filtering, mapping, or configuration behavior when standard Add-ons do not fully match the Magento requirement.          |

The distinction matters. Add-ons shape compatible migration work. They do not automatically interpret unsupported extension tables, rebuild custom workflows, recreate source modules, or make a Custom Platform source behave like a standard supported platform. A Magento migration can combine Standard Service or Managed Service with Add-ons when the core path is compatible but certain data groups need tighter control.

### Review Custom Service When Magento Needs Bespoke Handling <a href="#review-custom-service-when-magento-needs-bespoke-handling" id="review-custom-service-when-magento-needs-bespoke-handling"></a>

Custom Service should be reviewed when the migration depends on structures or business logic that are not safe to treat as standard entity transfer. Magento projects often reach this point when data was created by extensions, custom modules, custom database tables, ERP systems, PIM systems, marketplaces, subscription systems, loyalty programs, quote workflows, or heavily modified open-source behavior.

Custom Service may be needed when:

* a Custom Platform source context is involved;
* source product relationships do not map cleanly into Magento product types;
* configurable, bundle, grouped, custom-option, or downloadable product behavior depends on nonstandard source logic;
* source attributes are owned by extensions, custom tables, or source-side modules;
* customer groups, pricing rules, permissions, tax behavior, or approval workflows depend on custom logic;
* order history contains custom fields that staff must continue using operationally;
* inventory depends on external systems, warehouses, reservations, marketplace stock, or bespoke fulfillment rules;
* URLs, redirects, or SEO structures require handling beyond ordinary migration settings;
* Magento extensions in the Target Store expect data in a specific structure;
* outside-system identifiers must be preserved for ERP, CRM, accounting, fulfillment, analytics, or support workflows.

Custom Service should be scoped before it is promised. Some custom needs are narrow, such as preserving a specific external product ID. Others are broader, such as translating subscription history from a source extension into a usable Magento extension structure. The service plan should distinguish which custom data can be migrated, which should be rebuilt manually, which should be excluded, and which should remain historical reference only.

### Plan Entity Points Around Scope and Business Value <a href="#plan-entity-points-around-scope-and-business-value" id="plan-entity-points-around-scope-and-business-value"></a>

The Entity Points Plan should reflect the selected entities and expected migration scope. Magento planning should avoid two opposite mistakes: moving everything without business judgment, or reducing scope so aggressively that the Target Store loses useful operating history.

| Entity group                | Recommended treatment                                                                                                                                             |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core launch data            | Products, categories, customers, orders, images, URLs, CMS Pages, Blog Posts, and other launch-critical entities should be included when compatible and valuable. |
| Selective historical data   | Old orders, inactive products, retired categories, obsolete pages, or legacy customers may be filtered by date, status, category, store view, or business value.  |
| Structurally uncertain data | Extension-owned fields, custom tables, external IDs, unusual relationships, and custom logic should be reviewed before inclusion.                                 |
| Low-value legacy noise      | Duplicate attributes, unused categories, broken media, obsolete fields, and retired campaign pages may be excluded or archived outside the Target Store.          |

Entity Points should support a clean operating model, not an all-or-nothing transfer. New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated for the first time under the service license. Records already counted through the service license should not consume Entity Points again merely because the customer uses later additional migration activity for the same migration path.

### Use Demo Migration to Confirm the Approach <a href="#use-demo-migration-to-confirm-the-approach" id="use-demo-migration-to-confirm-the-approach"></a>

Demo Migration should test the selected approach before Full Migration. For Magento, useful samples should not be random. They should include records most likely to expose product-type, attribute, scope, URL, inventory, customer, order, extension, and mapping issues.

Strong Demo Migration samples include:

* a configurable product with associated simple products, option labels, child SKUs, stock behavior, images, and category placement;
* a product with attributes that support product pages, search, filtering, or comparison;
* localized product or category content assigned to the correct store view;
* products assigned to multiple categories, websites, or stores;
* customers assigned to meaningful customer groups;
* orders with taxes, discounts, shipping fees, invoices, refunds, cancellations, unusual statuses, or external IDs;
* high-value product, category, CMS Page, Blog Post, and custom URLs that require SEO review;
* representative inventory cases for single-source or multi-source expectations;
* records connected to source extensions, custom fields, or external systems.

Demo Migration should decide whether the selected approach is still valid. If samples pass, the project can move toward Full Migration with clearer confidence. If samples reveal unsupported structures, unclear target configuration, or mismatched expectations, the service plan should be adjusted before scale increases the cost of correction.

### Plan Additional Migration Options for Magento Launch Timing <a href="#plan-additional-migration-options-for-magento-launch-timing" id="plan-additional-migration-options-for-magento-launch-timing"></a>

Magento projects often run while the Source Platform remains active. New products, customers, orders, reviews, content updates, mapping corrections, or target configuration changes may appear after an earlier migration run. These changes should be planned through Additional Migration Options when they affect the service license and migration path.

Additional Migration Options can be relevant when:

* the live source store continues receiving orders close to launch;
* new products, customers, reviews, CMS Pages, or Blog Posts appear after Full Migration;
* product attributes, attribute sets, or store views are adjusted after initial testing;
* mapping decisions are corrected after Demo Migration or stakeholder review;
* target configuration changes make a previous migrated result unsuitable;
* SEO URLs or redirects require revised handling;
* extension-related records are excluded first and added later after Custom Service review.

The key planning question is not whether the migration can run again. The key question is which additional action fits the business need: continuing with the last used configuration, continuing with a new configuration, or performing a new migration. The choice should consider target cleanup, duplicate risk, Entity Points capacity, validation effort, and launch timing.

### Match the Approach to the Real Decision <a href="#match-the-approach-to-the-real-decision" id="match-the-approach-to-the-real-decision"></a>

The strongest Magento migration approach separates standard transfer, guided execution, optional Add-ons, custom review, capacity planning, launch timing, and validation responsibility before Full Migration begins.

| Migration situation                                                                                                   | Recommended approach                                                                 |
| --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Compatible source data, simple target structure, and confidence in customer-led execution                             | Standard Service with careful Demo Migration review.                                 |
| Compatible source data, larger scope, limited internal capacity, or launch coordination needs                         | Managed Service with defined validation ownership.                                   |
| Compatible data requiring selective movement or field alignment                                                       | Standard Service or Managed Service with Add-ons.                                    |
| Unsupported structures, extension-owned data, custom modules, external IDs, Custom Platform context, or bespoke logic | Custom Service review before approving scope.                                        |
| Active source store with new records expected before launch                                                           | Plan the appropriate Additional Migration Options and renewed review.                |
| Changed mapping, corrected target configuration, or intentional replacement of earlier migrated output                | Choose the additional action deliberately, with cleanup and validation expectations. |

A Magento migration approach should not be selected from record totals alone. It should reflect the store’s real operating model: catalog structure, attributes, scope, URLs, inventory, customer context, extensions, custom logic, service responsibility, and launch timing.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Choosing the right Magento migration approach means matching the Target Store’s structural burden to the right combination of Standard Service, Managed Service, Add-ons, Custom Service, Entity Points planning, Demo Migration review, Full Migration execution, and Additional Migration Options when they are needed.

When the approach is selected carefully, Magento migration becomes easier to control. Compatible entities can move through the supported migration path, custom requirements can be scoped before they create launch risk, and validation can focus on whether the Target Store is ready to operate with confidence.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a Magento migration?**

Standard Service can be enough when the source data fits a supported migration path, the Magento target structure is clear, and the customer can review Demo Migration results confidently. It becomes less suitable when custom modules, extension-owned data, unusual product behavior, or complex launch coordination require additional service responsibility.

**When should a Magento project use Managed Service?**

Managed Service is useful when the data is broadly compatible but the customer wants Next-Cart to handle more migration execution, coordination, review support, or launch-window handling. It is an execution-responsibility decision, not proof that the data itself is custom.

**When do Magento migrations need Custom Service?**

Custom Service should be reviewed when unsupported structures, extension-owned records, custom fields, Custom Platform behavior, external IDs, bespoke product relationships, unusual order logic, or integration-dependent data must be preserved beyond standard supported behavior.

**Do Entity Points measure Magento complexity?**

No. Entity Points help define service license capacity and migration scope. Magento complexity also depends on product relationships, attributes, scope, inventory behavior, URLs, extensions, custom logic, and validation responsibility.

**How should Additional Migration Options be planned for Magento?**

Additional Migration Options should be planned when the source store remains active, mapping changes after testing, or new records appear before launch. Any additional activity should be followed by renewed review of the affected Magento records, especially products, attributes, URLs, customers, orders, inventory, and custom data.
