# Selecting the Right Migration Approach for Magento

A Magento migration approach should be selected by matching the store’s operating structure to the right service responsibility. Magento can support simple catalogs, but it is often chosen for configurable products, attribute-rich catalogs, multi-store or multi-language scope, URL rewrite continuity, customer-group logic, inventory rules, extension-driven workflows, and custom business requirements. Those strengths make the migration approach a planning decision, not only a data-transfer decision.

A reliable approach should define what can move through a supported migration path, what needs additional filtering or mapping, what requires expert-led execution, what belongs in Custom Service, and what must be validated before launch. Entity Points capacity matters, but it should be considered together with structural complexity, service ownership, and the business value of the data being moved.

### Start with Magento Complexity, Not Only Entity Volume <a href="#start-with-magento-complexity-not-only-entity-volume" id="start-with-magento-complexity-not-only-entity-volume"></a>

Entity volume affects the service license and Entity Points Plan, but Magento migration complexity is often created by relationships, scope, and behavior. A smaller source store with multilingual store views, configurable products, extension-owned attributes, custom URLs, and ERP identifiers can require more planning than a larger single-store catalog with simple products and ordinary customer/order history.

Use the first review to separate quantity from complexity.

| Review area                 | Lower-complexity signal                                                 | Higher-complexity signal                                                                                             |
| --------------------------- | ----------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Catalog structure           | Mostly simple products with ordinary categories and media.              | Configurable, bundle, grouped, downloadable, virtual, custom-option, or heavily modified product structures.         |
| Attribute model             | Clean product fields with consistent labels and option values.          | Many custom attributes, duplicate values, layered-navigation dependencies, or attribute-set decisions.               |
| Store scope                 | One website, one store, one store view.                                 | Multiple websites, stores, store views, languages, localized URLs, or scope-specific values.                         |
| Customer and order context  | Customer records and orders are needed mainly for historical reference. | Customer groups, B2B-like segmentation, custom order fields, external identifiers, or integration-dependent history. |
| Inventory                   | Single-source inventory with straightforward quantities.                | Multiple sources, warehouses, pickup locations, dropshippers, reservations, or external stock synchronization.       |
| Extensions and custom logic | Source data mostly uses native structures.                              | Source extensions, custom modules, custom tables, or business rules determine data meaning.                          |

The selected approach should match the highest-risk parts of the store, not the easiest parts. A Magento project can use Standard Service for compatible entities while using Add-ons or Custom Service for specific sections that need additional handling.

### Use Standard Service When the Migration Path Is Structurally Compatible <a href="#use-standard-service-when-the-migration-path-is-structurally-compatible" id="use-standard-service-when-the-migration-path-is-structurally-compatible"></a>

Standard Service is usually the right starting point when the source-store data fits supported entities and the Target Store can accept those entities without significant custom interpretation. It is suitable when the customer wants to self-perform the migration process on the Next-Cart website, review Demo Migration results, and proceed to Full Migration after representative records behave correctly.

Standard Service is most appropriate when:

* products, categories, customers, orders, images, manufacturers, CMS Pages, Blog Posts, or other selected entities fit a supported migration path;
* the Target Store structure is already prepared or simple enough to validate through Demo Migration;
* product types and variant behavior are clear enough for standard mapping;
* attributes do not require heavy restructuring beyond ordinary mapping decisions;
* inventory does not depend on custom source logic or unsupported external systems;
* customer and order history can be migrated for reference without recreating every source-side workflow;
* SEO and URL expectations are documented and can be validated with representative samples;
* no source extension or custom module controls critical business meaning that must be preserved exactly.

Standard Service should not be treated as a shallow option. It can be appropriate for substantial Magento stores when data structures are compatible and the customer can validate the result with confidence. The important boundary is responsibility: Standard Service does not replace unsupported custom-logic review, extension-data interpretation, bespoke target behavior planning, or final result verification.

### Use Managed Service When Compatible Work Needs Expert-Led Execution <a href="#use-managed-service-when-compatible-work-needs-expert-led-execution" id="use-managed-service-when-compatible-work-needs-expert-led-execution"></a>

Managed Service is better when the migration path is compatible but the customer wants Next-Cart to handle more of the migration process, coordination, review, or execution support. This is common when a Magento project has many entities, a tight launch window, limited internal migration capacity, multiple stakeholders, or a need for guided Demo Migration and Full Migration handling.

Managed Service is a strong fit when:

* the customer wants Next-Cart to manage migration execution instead of self-performing each step;
* the catalog is large enough that review coordination matters;
* the store has multiple entity types and launch dependencies;
* Demo Migration findings need structured interpretation before Full Migration;
* validation follow-up requires clear ownership across products, URLs, customers, orders, and content;
* late source-store activity may require a planned additional migration action before launch;
* configuration or mapping decisions may need expert review before the final migration run.

Managed Service is not automatically the same as Custom Service. A Magento store can need Managed Service because of operational burden, not because its data is structurally custom. Conversely, a store can require Custom Service even if the customer is willing to perform available migration actions manually, because the issue is unsupported logic rather than execution ownership.

### Use Add-ons for Compatible Filtering, Mapping, or Configuration Needs <a href="#use-add-ons-for-compatible-filtering-mapping-or-configuration-needs" id="use-add-ons-for-compatible-filtering-mapping-or-configuration-needs"></a>

Add-ons are optional service features that adjust how compatible migration data is filtered, mapped, or configured. They are not the same as Custom Service. In Magento planning, Add-ons are useful when the data is structurally compatible but the customer needs more control over what moves, how fields align, or how target records are configured.

| Need                                      | Likely service feature             | Magento example                                                                                                                      |
| ----------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Exclude obsolete or low-value records     | Data Filter Add-on                 | Migrate only active products, selected order statuses, specific customer groups, recent historical orders, or chosen content groups. |
| Align fields more precisely               | Advanced Data Mapping              | Map supported source fields into Magento-compatible product attributes, customer fields, order reference fields, or content fields.  |
| Adjust compatible target behavior         | Advanced Data Configure            | Apply agreed configuration behavior for selected migrated records when compatible with the approved migration path.                  |
| Modify an Add-on beyond standard coverage | Tailored Add-ons or Custom Add-ons | Adjust filtering, mapping, or configuration handling when the standard Add-on does not fully match the Magento requirement.          |

The distinction matters because Add-ons shape compatible migration work. They do not automatically interpret unsupported tables, recreate extension logic, rebuild custom workflows, or make a Custom Platform source behave like a standard platform. A Magento migration may use Standard Service, Managed Service, and Add-ons together when the core path is compatible but some data needs more precise handling.

### Review Custom Service When Magento Needs Bespoke Handling <a href="#review-custom-service-when-magento-needs-bespoke-handling" id="review-custom-service-when-magento-needs-bespoke-handling"></a>

Custom Service should be reviewed when the migration depends on structures or business logic that are not safe to treat as standard entity transfer. In Magento projects, this often happens when source data was created by extensions, custom modules, bespoke database tables, marketplace integrations, subscription systems, loyalty programs, quote workflows, ERP/PIM/WMS identifiers, or heavily modified open-source behavior.

Custom Service may be needed when:

* a Custom Platform source context is involved;
* source product relationships do not map cleanly into Magento product types;
* configurable, bundle, grouped, or custom-option behavior depends on nonstandard source logic;
* source attributes are owned by extensions, custom tables, or source-side modules;
* customer groups, company-like structures, pricing rules, permissions, or tax behavior depend on custom logic;
* order history contains custom fields that staff must continue to use operationally;
* inventory depends on external systems, warehouse logic, reservations, marketplace stock, or custom fulfillment rules;
* URLs, redirects, or SEO structures require bespoke handling beyond ordinary migration settings;
* Target Store extensions expect data in a specific structure that standard migration cannot guarantee;
* outside-system identifiers must be preserved for post-launch integrations.

Custom Service should be scoped before it is promised. Some custom needs are narrow, such as preserving a specific external product ID. Others are broad, such as interpreting subscription history from a source extension and making it meaningful for a target Magento subscription extension. The service plan should distinguish which custom data can be migrated, which should be rebuilt manually, which should be excluded, and which should remain historical reference only.

#### Separate Custom Service from Expert Handle <a href="#separate-custom-service-from-expert-handle" id="separate-custom-service-from-expert-handle"></a>

Custom Service defines the scope of custom handling. Expert Handle defines whether Next-Cart performs migration actions and related execution work on the customer’s behalf. A Magento project can require Custom Service without expert-managed execution, or it can combine Custom Service with Expert Handle when the agreed plan includes both custom handling and Next-Cart-led execution.

The distinction prevents two common planning mistakes: assuming every custom requirement includes full migration management, or assuming customer-led execution can resolve unsupported data logic without custom review.

### Plan Entity Points Around Scope and Business Value <a href="#plan-entity-points-around-scope-and-business-value" id="plan-entity-points-around-scope-and-business-value"></a>

The Entity Points Plan should reflect the selected entities and expected migration scope. For Magento, entity planning should avoid two mistakes: counting everything without business judgment, and reducing scope so aggressively that the Target Store loses operational value.

Entity planning should classify data into four groups.

| Entity group                | Recommended treatment                                                                                                                                                    |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Core launch data            | Products, categories, customers, orders, images, URLs, CMS Pages, Blog Posts, or other entities needed for launch should be included when compatible and valuable.       |
| Useful but selective data   | Old orders, inactive products, legacy customers, obsolete pages, or retired categories may be filtered by date, status, category, language, or business value.           |
| Structurally uncertain data | Extension-owned fields, custom tables, external IDs, or unusual relationship data should be reviewed before inclusion.                                                   |
| Low-value legacy noise      | Duplicate attributes, obsolete campaign pages, unused categories, broken media, and retired custom fields should often be excluded or archived outside the Target Store. |

Magento rewards clean structure. Migrating less data can be the right decision when excluded data would create attribute clutter, weak navigation, confusing customer records, or unusable order history. Migrating more data can also be the right decision when historical continuity, support workflows, SEO preservation, or integration references are commercially important. The Entity Points Plan should support the intended operating model, not a reflexive all-or-nothing transfer.

### Use Demo Migration to Confirm the Approach <a href="#use-demo-migration-to-confirm-the-approach" id="use-demo-migration-to-confirm-the-approach"></a>

Demo Migration should test the selected approach before Full Migration. For Magento, a useful Demo Migration sample should not be random. It should include the records most likely to expose product-type, scope, attribute, URL, inventory, customer, order, extension, and mapping issues.

The sample should include expected outcomes such as:

* a configurable product with its associated simple products, option labels, child SKUs, images, stock behavior, and category placement;
* a product with rich attributes that should support storefront display, search, filtering, or comparison;
* localized product or category content assigned to the correct store view;
* products assigned to multiple categories or websites;
* customers assigned to different customer groups;
* orders with discounts, taxes, shipping fees, refunds, cancellations, unusual statuses, or external IDs;
* high-value product, category, CMS page, and custom URLs that require SEO review;
* representative inventory cases for single-source or multi-source stock expectations;
* records connected to source extensions or custom fields.

Demo Migration should decide whether the selected approach is still valid. If sample records pass, the project can move toward Full Migration with clearer confidence. If samples expose unsupported structures, unclear target configuration, or mismatched expectations, the service plan should be adjusted before scale increases the cost of correction.

### Plan Additional Migration Options for Magento Launch Timing <a href="#plan-additional-migration-options-for-magento-launch-timing" id="plan-additional-migration-options-for-magento-launch-timing"></a>

Magento projects often run while the source store remains active. New products, customers, orders, reviews, content updates, configuration changes, or mapping corrections may appear after an earlier migration run. These changes should be planned through the available Additional Migration Options under the service license, not treated as informal manual fixes.

Additional Migration Options are relevant when:

* the live source store continues receiving orders close to launch;
* new products, customers, reviews, or CMS Pages appear after Full Migration;
* product attributes or store views are restructured after initial testing;
* mapping decisions are corrected after Demo Migration or stakeholder review;
* target configuration changes make a previous migrated result unsuitable;
* SEO URLs or redirects require revised handling;
* extension-related records are excluded first and added later after Custom Service review.

The key planning question is not whether a Magento migration can be run again. The key question is which additional action fits the business need: continuing with the previous configuration, continuing with a new configuration, or performing a new migration. The choice should consider target cleanup, duplicate risk, Entity Points capacity, validation effort, and launch timing.

### Match the Approach to the Real Decision <a href="#match-the-approach-to-the-real-decision" id="match-the-approach-to-the-real-decision"></a>

The strongest Magento migration approach separates standard transfer, guided execution, optional Add-ons, custom review, capacity planning, launch timing, and validation responsibility before Full Migration begins.

| Migration situation                                                                                                                   | Recommended approach                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Compatible source data, simple Target Store structure, and customer confidence in self-performing migration steps                     | Standard Service with careful Demo Migration review.                                                  |
| Compatible source data, larger scope, limited internal capacity, or launch coordination needs                                         | Managed Service with defined validation responsibility.                                               |
| Compatible data requiring selective movement or field alignment                                                                       | Standard Service or Managed Service with Add-ons such as Data Filter Add-on or Advanced Data Mapping. |
| Unsupported structures, extension-owned records, custom modules, external IDs, Custom Platform source data, or bespoke business logic | Custom Service review before approving scope.                                                         |
| Active source store with new records expected before launch                                                                           | Plan the appropriate Additional Migration Option as part of launch readiness.                         |
| Changed mapping, corrected target configuration, or intentional replacement of earlier migrated results                               | Choose the additional action deliberately, with cleanup and validation expectations.                  |

A reliable Magento migration plan does not force every requirement into one service path. It identifies which parts are structurally compatible, which parts need optional filtering or mapping, which parts require custom review, and which parts must be validated before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting a Magento migration approach should begin with the store’s real operating structure: product types, attributes, website and store-view scope, customer groups, inventory, URLs, extensions, custom logic, and launch timing. Standard Service, Managed Service, Custom Service, Add-ons, Entity Points, and Additional Migration Options each answer different planning needs.

The right approach is the one that correctly separates compatible migration work, guided execution, optional filtering or mapping, custom review, capacity planning, launch updates, and final verification responsibility before Full Migration begins.

### FAQs <a href="#faqs" id="faqs"></a>

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a Magento migration?**

Standard Service can be enough when source data fits a supported migration path, the Target Store structure is prepared, and Demo Migration confirms that representative records behave correctly. More complex stores may still need Add-ons, Managed Service, or Custom Service for specific requirements.

**When should a Magento project use Managed Service?**

Managed Service is appropriate when the migration path is compatible but the customer wants Next-Cart to handle more of the process, coordination, execution support, or review workflow, especially for larger scopes or launch-sensitive projects.

**Are Add-ons the same as Custom Service?**

No. Add-ons help with filtering, mapping, or data configuration for compatible migration work. Custom Service is used when the requirement involves unsupported structures, custom logic, extension-owned data, Custom Platform source context, or bespoke handling.

**Should Additional Migration Options be planned before launch?**

They should be considered when the source store remains active, new records are expected before launch, or configuration and mapping decisions may change after earlier migration runs. The selected action should match the business need and validation scope.

**Does Custom Service automatically mean Next-Cart performs the whole migration?**

No. Custom Service defines custom handling scope. Expert Handle or Managed Service determines whether Next-Cart performs migration actions and related execution work on the customer’s behalf.
