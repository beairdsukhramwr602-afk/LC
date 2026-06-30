# Selecting the Right Migration Approach for Adobe Commerce

Selecting the right Adobe Commerce migration approach requires more than estimating record volume. Adobe Commerce projects can involve B2B company accounts, shared catalogs, buyer-specific pricing, configurable products, multiple websites and store views, staged content, external identifiers, ERP/PIM/CRM/WMS dependencies, and custom modules. The service path should match how much of that operating model must be migrated, configured, customized, or validated.

The right approach is not automatically the most complex option. Standard Service can be suitable when the expected data is supported, the source structure is clean, and the customer can manage the process and validation. Managed Service can help when execution coordination and launch pressure are high. Add-ons can support bounded filtering, mapping, or configuration within supported behavior. Custom Service becomes important when the project requires unsupported records, custom logic, custom fields, external-system identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

### Adobe Commerce Approach Selection Starts With Operating Complexity <a href="#adobe-commerce-approach-selection-starts-with-operating-complexity" id="adobe-commerce-approach-selection-starts-with-operating-complexity"></a>

Approach selection should begin with the target operating model. Adobe Commerce may be chosen because the merchant needs enterprise catalog governance, B2B purchasing, regional storefronts, complex pricing, integration ownership, or staged content. Those reasons affect the migration service path.

| Operating signal                              | Approach implication                                                                                             |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Standard catalog and customer/order history   | May fit Standard Service if supported fields and validation capacity are clear.                                  |
| Large but compatible catalog                  | May fit Standard Service or Managed Service depending on execution workload and customer capacity.               |
| B2B company accounts and shared catalogs      | Requires deeper preparation; may need Managed Service, Add-ons, or Custom Service depending on source structure. |
| Buyer-specific pricing or contract visibility | Needs careful scoping because not every price rule is ordinary product price data.                               |
| Multiple websites and store views             | Increases preparation and validation burden; may justify Managed Service or mapping Add-ons.                     |
| ERP/PIM/CRM/WMS dependency                    | May require Custom Service if identifiers or owned records must be preserved beyond supported fields.            |
| Custom modules or unsupported source logic    | Requires Custom Service review before final scope approval.                                                      |

A useful service decision should name the data that migrates, the configuration done in Adobe Commerce, the Add-ons needed for supported adjustments, the Custom Service items requiring review, and the validation responsibility after Demo Migration.

### When Standard Service Can Be Realistic <a href="#when-standard-service-can-be-realistic" id="when-standard-service-can-be-realistic"></a>

Standard Service can be realistic when the Adobe Commerce migration stays within supported data behavior and the customer has enough internal capacity to prepare, execute, and validate the project. This does not mean the store must be small. It means the scope is understandable, supported, and reviewable.

Standard Service is most appropriate when:

* product data can be represented through supported catalog records;
* configurable products, simple products, categories, attributes, images, customers, orders, coupons, reviews, CMS Pages, or Blog Posts are within supported expectations;
* B2B company logic is not part of the required migration outcome, or is handled separately through configuration and implementation work;
* pricing complexity is limited to supported fields rather than contract systems, custom rules, or external price ownership;
* websites, stores, and store views are simple enough for the customer to prepare and validate;
* extensions and integrations do not own critical records expected in the migrated result;
* the customer can review Demo Migration samples and classify issues accurately.

Standard Service becomes risky when the customer expects enterprise behavior to transfer automatically. Adobe Commerce configuration, B2B setup, shared catalog assignment, live payment and shipping setup, staged content, integration wiring, and custom module behavior should not be assumed from standard record migration.

### When Managed Service Is Safer <a href="#when-managed-service-is-safer" id="when-managed-service-is-safer"></a>

Managed Service is safer when the migration remains mostly within supported capability but the project needs more structured execution support. Adobe Commerce projects often involve multiple stakeholders, larger catalogs, launch windows, scope approvals, and validation dependencies. The data may be supported, but the coordination burden can still be high.

Managed Service may be appropriate when:

| Situation                                                                   | Why Managed Service helps                                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Large catalog with many product types and attributes                        | Execution and sample review need stronger coordination.                                                   |
| Multiple websites or store views                                            | Scope, localized values, content, and URL validation need organized sequencing.                           |
| Important B2B records exist but custom migration logic is not yet confirmed | Managed coordination can support preparation while Custom Service items are separated.                    |
| Launch timing is tight                                                      | A managed process helps align Demo Migration review, Full Migration timing, and later migration activity. |
| Internal migration capacity is limited                                      | The customer still validates outcomes, but execution support reduces operational load.                    |
| SEO and content continuity are sensitive                                    | URL, redirect, CMS Page, Blog Posts, and campaign-content review need clear ownership.                    |

Managed Service should not be used to hide unclear scope. If the problem is unsupported data, custom fields, custom modules, or external-system logic, the project still needs Custom Service review. Managed Service addresses execution and coordination; it does not turn unsupported requirements into supported ones.

### When Add-ons Are Enough <a href="#when-add-ons-are-enough" id="when-add-ons-are-enough"></a>

Add-ons are appropriate when the requirement is bounded and remains within supported behavior. For Adobe Commerce, Add-ons can help when the merchant needs filtering, mapping, or data configuration that improves the usefulness of supported records.

| Add-on need             | Adobe Commerce example                                                                                  | Boundary                                                                                  |
| ----------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Data Filter             | Exclude obsolete customers, inactive products, old orders, retired CMS Pages, or irrelevant Blog Posts. | Filtering should not remove records needed for B2B context, support, SEO, or reporting.   |
| Advanced Data Mapping   | Align supported source fields with Adobe Commerce destinations, such as attributes or customer fields.  | Mapping cannot create unsupported B2B structures or custom module behavior.               |
| Advanced Data Configure | Adjust supported output behavior for product, customer, order, content, or URL usability.               | Configuration must remain within supported capability.                                    |
| Custom Add-ons          | Address a bounded need that is feasible inside agreed migration behavior.                               | Unsupported records, external IDs, or bespoke transformations may require Custom Service. |

The practical test is whether the data already belongs to supported migration behavior. If the answer is yes, an Add-on may help. If the answer is no, the requirement should not be disguised as an Add-on.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when Adobe Commerce migration expectations go beyond supported standard behavior. Enterprise projects often create custom scope because the source store may use extensions, custom modules, external systems, B2B workflows, pricing engines, integration IDs, or implementation-specific database structures.

Custom Service review is appropriate when the project includes:

* B2B company relationships not present as standard exportable records;
* company hierarchies, role structures, credit rules, approval workflows, or purchasing permissions requiring special handling;
* shared catalog or buyer-specific pricing logic owned by ERP, spreadsheets, procurement tools, or custom modules;
* custom product attributes that require bespoke interpretation rather than supported mapping;
* external identifiers needed by ERP, PIM, CRM, WMS, tax, shipping, fulfillment, analytics, or reporting systems;
* custom modules, source extensions, or unsupported app data that create business-critical records;
* custom order, quote, invoice, refund, purchase order, or fulfillment logic;
* Custom Platform source or target conditions;
* custom migration logic adjustment beyond standard capability.

Custom Service should be scoped through representative samples. A general statement such as “we have custom B2B pricing” is not enough. The customer should provide sample companies, products, price lists, orders, fields, external IDs, and expected target behavior.

### How Entity Points Affect Adobe Commerce Scope Planning <a href="#how-entity-points-affect-adobe-commerce-scope-planning" id="how-entity-points-affect-adobe-commerce-scope-planning"></a>

Entity Points help plan service-license capacity, but they do not define complexity by themselves. Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because another migration action occurs on the same migration path.

Adobe Commerce scope should consider Entity Points alongside business complexity:

| Scope signal     | What it helps estimate                                        | What it does not prove                                                                                             |
| ---------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Product count    | Catalog volume and Product-related Entity Points consumption. | Whether configurable products, attributes, shared catalogs, visibility, and inventory will be usable.              |
| Customer count   | Customer and buyer-record volume.                             | Whether B2B company structure, roles, permissions, or customer-group assignments are correct.                      |
| Order count      | Historical order volume.                                      | Whether invoices, refunds, purchase order references, quotes, company context, and external IDs remain meaningful. |
| Blog Posts count | Content volume where relevant.                                | Whether CMS Pages, staged content, URLs, redirects, and campaign pages are launch-ready.                           |

A project with fewer records can still require Custom Service if the records carry complex business meaning. A project with many records can still fit Standard Service or Managed Service if the data is supported and the customer can validate the result.

### How Additional Migration Options Fit Launch Timing <a href="#how-additional-migration-options-fit-launch-timing" id="how-additional-migration-options-fit-launch-timing"></a>

Adobe Commerce projects often continue while the Source Platform remains active. New records and configuration changes may appear after an initial migration run. Additional Migration Options should be planned when the business expects new source records, revised mappings, changed target configuration, or a refreshed target result before launch.

Current migration-action planning should distinguish between:

| Need                                                                   | Practical action                                         |
| ---------------------------------------------------------------------- | -------------------------------------------------------- |
| Add newly created records using the last approved setup                | Continue the Migration with the last used configuration. |
| Continue after changing mapping or configuration decisions             | Continue the Migration with a new configuration.         |
| Replace the earlier migrated target result for the same migration path | Perform a new migration.                                 |

For Adobe Commerce, these decisions matter when new products, customers, orders, reviews, CMS Pages, Blog Posts, B2B records, pricing changes, URL changes, or content updates appear before launch. The follow-up action should define what is affected, what must be revalidated, and whether target cleanup is needed.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should test whether the selected service path is strong enough. Adobe Commerce samples should be chosen to expose enterprise complexity, not only ordinary records.

Useful Demo Migration samples include:

* configurable product with child SKUs, attributes, categories, images, price, stock, and URL behavior;
* company account with administrator, users, customer group, and shared catalog expectations;
* shared catalog product with buyer-specific visibility or pricing;
* multi-store or store-view-specific product and content values;
* order with invoice, refund, tax, discount, purchase order, quote, company, payment, shipping, and external reference context;
* CMS Page, Blog Post, campaign page, or landing page with URL and content timing expectations;
* integration-owned field or custom module record that may require Custom Service review.

If Demo Migration reveals unsupported records, unclear B2B expectations, broken shared catalog assumptions, missing external IDs, or weak target-side configuration, the service path should be revised before Full Migration.

### Match the Service Path to the Real Migration Decision <a href="#match-the-service-path-to-the-real-migration-decision" id="match-the-service-path-to-the-real-migration-decision"></a>

A strong Adobe Commerce approach separates four decisions:

1. Which supported records should migrate.
2. Which Adobe Commerce settings must be configured in the target store.
3. Which supported adjustments need Add-ons.
4. Which unsupported or custom requirements need Custom Service review.

| Migration condition                                                                                           | Recommended direction                                              |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Supported catalog, customers, orders, content, and clear customer-led validation                              | Standard Service.                                                  |
| Supported scope but large execution load, many stakeholders, or high launch pressure                          | Managed Service.                                                   |
| Supported data needs filtering, mapping, or configuration adjustment                                          | Add-ons with Standard Service or Managed Service.                  |
| B2B/company/shared catalog/custom pricing/custom module/external ID requirements go beyond supported behavior | Custom Service review.                                             |
| Active source store keeps changing before launch                                                              | Plan Additional Migration Options and validation responsibilities. |
| Existing target result must be replaced                                                                       | Perform a new migration with cleanup and review expectations.      |

Adobe Commerce approach selection should remain practical. The right service path is the lightest path that still protects the business outcome, validation burden, and launch schedule.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce migration approach selection should be based on enterprise operating complexity, not record count alone. Standard Service may be enough when supported data and customer-led validation are realistic. Managed Service may be safer when execution coordination is heavy. Add-ons help with supported filtering, mapping, and configuration needs. Custom Service should be reviewed when B2B structures, shared catalogs, custom pricing, external identifiers, custom modules, or bespoke logic exceed supported behavior.

The strongest decision is evidence-based: representative samples, clear service boundaries, Entity Points planning, Additional Migration Options planning, and Demo Migration results should confirm whether the selected approach can protect the Adobe Commerce launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for Adobe Commerce?**

Standard Service may be enough when the migration scope is supported, B2B or custom logic is limited, product and content structures are clear, and the customer can prepare inputs, run the process, review Demo Migration, and validate Full Migration results responsibly.

**When should Managed Service be considered?**

Managed Service is useful when supported scope still requires more execution coordination, larger sample review, many stakeholder approvals, complex launch timing, or limited internal migration capacity.

**How are Add-ons different from Custom Service for Adobe Commerce?**

Add-ons help with supported filtering, mapping, or configuration. Custom Service handles unsupported records, custom fields, external identifiers, custom modules, B2B structures beyond supported behavior, Custom Platform handling, or bespoke transformation.

**Do Entity Points measure Adobe Commerce complexity?**

No. Entity Points help plan service-license capacity for eligible records, but complexity depends on business meaning, B2B structure, catalog governance, integrations, custom data, and validation burden.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that representative Adobe Commerce records are usable: configurable products, company accounts, shared catalog samples, store-view values, orders, content, URLs, integration-owned fields, and custom-data examples where relevant.
