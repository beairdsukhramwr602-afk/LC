# Selecting the Right Migration Approach for Shopware

Choosing the right Shopware migration approach depends on more than the number of Products, Customers, Orders, Categories, Coupons, Reviews, CMS content, and related records to move. Shopware adds structural decisions around sales channels, catalog properties, variants, rules, Shopping Experiences, extensions, custom fields, translations, storefront behavior, and integration ownership. Those decisions determine whether the migration can stay within ordinary supported behavior or needs more guided handling.

A good approach should match the merchant’s actual operating burden. A straightforward Shopware target with ordinary catalog and customer/order records may fit Standard Service. A migration with unclear sales-channel decisions, complex validation, or limited internal review capacity may need Managed Service. Add-ons can help adjust supported filtering, mapping, or data configuration. Custom Service becomes important when unsupported extension data, custom fields, bespoke transformations, Custom Platform handling, or external-system relationships must be handled beyond standard capability.

### Start With Shopware Complexity, Not Package Labels <a href="#start-with-shopware-complexity-not-package-labels" id="start-with-shopware-complexity-not-package-labels"></a>

Service choice should begin with the migration pattern, not with a preferred service name. Shopware can receive simple commerce records, but it can also become a structured commerce environment where products, content, sales channels, rules, APIs, and integrations interact. The migration approach should reflect that reality.

| Shopware migration pattern                                                        | Better starting approach                          | Why                                                                              |
| --------------------------------------------------------------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------------- |
| Ordinary supported records and simple target setup                                | Standard Service                                  | The migration mainly needs record transfer and customer-led review.              |
| Clear data scope but high coordination burden                                     | Managed Service                                   | The merchant may need guided sequencing, review support, and issue coordination. |
| Supported data with specific filtering or mapping requests                        | Add-ons                                           | The request adjusts supported migration behavior without becoming bespoke work.  |
| Unsupported plugins, custom fields, custom logic, or external-system dependencies | Custom Service                                    | The work goes beyond ordinary supported transfer and needs tailored assessment.  |
| Unclear target operating model                                                    | Demo Migration before final approach confirmation | Samples can reveal whether the assumed approach is realistic.                    |

This approach protects the project from both overbuying and under-scoping. A simple Shopware migration should not be forced into custom work, but a complex Shopware implementation should not be treated as ordinary just because the entity list looks familiar.

### When Standard Service Can Be Realistic <a href="#when-standard-service-can-be-realistic" id="when-standard-service-can-be-realistic"></a>

Standard Service can be realistic when the source data is ordinary, the target Shopware setup is clear, and the merchant can lead the preparation and validation work. In this path, the migration expectation should remain close to supported commerce records and supported mapping behavior.

A Standard Service candidate usually has a manageable product catalog, understandable categories, limited custom fields, no critical unsupported plugin data, clear customer and order expectations, and a target store that does not rely on unresolved sales-channel or rule complexity. The merchant should also be able to review Demo Migration results and final migration results with internal stakeholders.

| Standard Service signal                                                                         | What should still be verified                                                                |
| ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Products, customers, orders, categories, coupons, reviews, and CMS content are mostly ordinary. | Representative samples should prove that core fields, relationships, and content are usable. |
| Sales-channel model is simple or already configured.                                            | Products and categories should appear in the intended storefront context.                    |
| Variants and properties are understandable.                                                     | Buying choices and filters should remain clear after migration.                              |
| Custom fields are limited or non-critical.                                                      | Important values should still be checked for supported mapping.                              |
| Extension dependencies are not part of expected migration scope.                                | The merchant should confirm that excluded behavior is acceptable.                            |

Standard Service does not mean no planning is needed. It means the merchant can handle preparation and review within a supported migration path without requiring ongoing guided execution or custom development assessment.

### When Managed Service Is the Safer Choice <a href="#when-managed-service-is-the-safer-choice" id="when-managed-service-is-the-safer-choice"></a>

Managed Service becomes more appropriate when the migration itself may still be supported, but the coordination burden is high. Shopware migrations can involve many decision owners: catalog, SEO, content, operations, finance, integrations, and technical stakeholders. If the merchant cannot keep those decisions aligned, the project can drift even when the data is migratable.

Managed Service can be useful when the target operating model is clear enough to proceed but the merchant needs stronger guidance around sequencing, Demo Migration review, issue prioritization, and readiness confirmation. It is also useful when the source store has enough complexity that internal teams may struggle to classify what is data, configuration, content, custom scope, or target-side implementation.

| Managed Service signal                                    | Why guidance helps                                                                         |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Several teams must review different outcomes.             | Catalog, SEO, content, order, and integration review can be coordinated more deliberately. |
| Sales-channel, language, or content context is important. | The review process needs more than record-count comparison.                                |
| Demo Migration will drive major scope decisions.          | Findings need to be interpreted into next actions.                                         |
| The merchant has limited migration experience.            | Guided review reduces the chance of accepting incomplete outcomes.                         |
| Launch timing is sensitive.                               | Sequencing and issue prioritization matter more under deadline pressure.                   |

Managed Service should not be used as a substitute for undefined scope. It works best when the merchant has enough evidence to proceed but needs execution support and review discipline.

### When Add-ons Help <a href="#when-add-ons-help" id="when-add-ons-help"></a>

Add-ons help when the requested adjustment stays within supported migration behavior. In a Shopware migration, Add-ons may be relevant for filtering, mapping, or configuration adjustments that refine the migration output without turning the project into bespoke custom work.

The key boundary is whether the requirement modifies supported behavior or introduces unsupported data handling. If a merchant wants certain supported records filtered, mapped, or configured differently, Add-ons may be appropriate. If the merchant needs data from unsupported plugins, custom tables, bespoke fields, or external systems migrated into a custom target structure, the work should be reviewed as Custom Service.

| Add-ons candidate                             | Why it may fit Add-ons                                          | When it becomes Custom Service instead                                      |
| --------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Filtering records by supported criteria       | The data is supported, but the included scope needs refinement. | The filter depends on unsupported custom logic or inaccessible plugin data. |
| Mapping supported fields differently          | The source and target values are within supported behavior.     | The mapping requires bespoke transformation or custom target behavior.      |
| Adjusting category or customer-group handling | The data is supported and the rule is clear.                    | The logic depends on unsupported modules or external systems.               |
| Controlling what content or records migrate   | The decision changes supported output selection.                | The content comes from custom structures not covered by standard behavior.  |
| Refining follow-up migration scope            | The migrated records are recognized and supported.              | The follow-up requires new custom logic or unsupported data extraction.     |

Add-ons are valuable when they improve precision. They should not be used to hide custom complexity inside a standard migration path.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is the right path when the migration requires work beyond supported standard behavior. Shopware’s extensibility makes this especially important. A source store may contain plugin-owned records, custom fields, custom storefront behavior, old module data, ERP/PIM/CRM identifiers, marketplace references, bespoke pricing rules, or content-commerce structures that do not map cleanly through ordinary migration scope.

Custom Service should be considered when the merchant can explain why the unsupported data matters and how it should behave in Shopware. The goal is not to migrate everything simply because it exists. The goal is to preserve business-critical meaning that ordinary migration scope cannot handle.

| Custom Service trigger                              | What must be clarified                                                                                      |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Unsupported app, plugin, module, or extension data  | Where the data lives, what business process uses it, and what target outcome is expected.                   |
| Custom fields that drive operations or integrations | Whether the values should appear in Shopware custom fields, external systems, or another target structure.  |
| Bespoke transformation logic                        | What source meaning should become in Shopware and why ordinary mapping is insufficient.                     |
| External-system identifiers                         | Which IDs must remain usable for ERP, PIM, CRM, search, marketplace, fulfillment, or reporting workflows.   |
| Custom Platform handling                            | Whether the source or target environment requires tailored extraction, transformation, or connection logic. |

Custom Service should be scoped with evidence. Sample records, screenshots, export examples, database notes where available, and expected target behavior help determine whether the custom requirement is feasible and valuable.

### Use Demo Migration to Confirm the Approach <a href="#use-demo-migration-to-confirm-the-approach" id="use-demo-migration-to-confirm-the-approach"></a>

Demo Migration is the safest way to test whether the proposed approach fits the actual Shopware migration. It should include representative records, not only a small random sample. The Demo Migration review should test the same evidence used in preparation: sales channels, variant products, properties, categories, content pages, customers, orders, custom fields, and integration-linked records.

| Demo Migration finding                                               | Approach implication                                           |
| -------------------------------------------------------------------- | -------------------------------------------------------------- |
| Core records migrate cleanly and samples are usable.                 | Standard Service may remain appropriate.                       |
| Records migrate but review coordination is difficult.                | Managed Service may reduce execution risk.                     |
| Supported records need filtering or mapping adjustment.              | Add-ons may improve the migration output.                      |
| Important data is missing because it is unsupported or custom-owned. | Custom Service review is needed before full scope is accepted. |
| Target configuration is incomplete.                                  | The issue may be target readiness, not migration failure.      |

Demo Migration should not be treated as a pass/fail event only. It is a decision point for confirming service path, target readiness, and validation responsibility.

### Entity Points and Shopware Scope Control <a href="#entity-points-and-shopware-scope-control" id="entity-points-and-shopware-scope-control"></a>

Entity Points matter when new eligible data entities are migrated. For Shopware, the relevant planning issue is not only how many records exist, but which records are new, which are already recorded through the migration service license, and which later migration actions introduce new eligible Product, Customer, Order, or Blog Posts records.

A new migration action does not automatically mean the same previously counted records consume additional Entity Points again. The important distinction is whether the action migrates new eligible entities for the first time or repeats already recorded entities within the same migration context.

| Scope situation                                                                       | Entity Points implication                                                                                  |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Existing counted products are migrated again through a later action.                  | They should not be treated as newly consuming Entity Points simply because the action repeats them.        |
| New products, customers, orders, or Blog Posts are added after the earlier migration. | Newly migrated eligible records may consume Entity Points when migrated for the first time.                |
| Custom fields or plugin-owned data need special handling.                             | Entity Points may not be the main planning issue; service scope and Custom Service review may matter more. |
| A new migration replaces previous target data.                                        | Replacement does not automatically reset the duplicate-consumption logic for previously recorded entities. |
| The merchant changes configuration before continuing.                                 | Service path and validation scope should be reviewed, not only point consumption.                          |

Entity Points should be discussed only where they help the merchant plan scope. They should not dominate Article 6 or replace service-path reasoning.

### Later Migration Actions Need Clear Intent <a href="#later-migration-actions-need-clear-intent" id="later-migration-actions-need-clear-intent"></a>

Shopware launch planning may involve continuing migration activity after Demo Migration, after target configuration changes, or after source-store updates. The merchant should choose the later migration action based on intent: continue with the last used configuration, continue with a new configuration, or perform a new migration.

For Shopware, the practical question is whether the same target assumptions still apply. If the merchant changed sales-channel setup, mapping decisions, content expectations, custom fields, or service scope, continuing with a new configuration or performing a new migration may require different validation than simply continuing from the previous setup.

| Later action intent                       | Shopware review focus                                                                             |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Continue with the last used configuration | Confirm that source updates fit the existing mapping and target assumptions.                      |
| Continue with a new configuration         | Recheck affected products, properties, sales channels, custom fields, and content outcomes.       |
| Perform a new migration                   | Confirm whether target replacement, new scope, or changed assumptions require broader validation. |
| Add newly created source records          | Identify whether new eligible Products, Customers, Orders, or Blog Posts affect Entity Points.    |
| Change service scope after Demo Migration | Reconfirm whether Standard Service, Managed Service, Add-ons, or Custom Service is still correct. |

This keeps later migration planning operational. The article should not use retired labels or explain old naming history; it should focus on current actions and validation consequences.

### Choosing the Right Path <a href="#choosing-the-right-path" id="choosing-the-right-path"></a>

The right Shopware migration approach is the one that matches the merchant’s data evidence, target readiness, internal review capacity, and unsupported-scope risk. The decision should be made after reviewing the catalog, sales channels, content, commercial logic, custom fields, extensions, integrations, and Demo Migration results.

| If the migration has…                             | Prefer…                             | Watch for…                                      |
| ------------------------------------------------- | ----------------------------------- | ----------------------------------------------- |
| Ordinary supported records and clear target setup | Standard Service                    | Underestimating validation responsibility.      |
| Supported scope but high coordination burden      | Managed Service                     | Assuming guidance replaces clear scope.         |
| Specific supported filtering or mapping needs     | Add-ons                             | Treating unsupported custom data as an Add-on.  |
| Plugin-owned, custom, or external-system data     | Custom Service                      | Migrating obsolete data without business value. |
| Unclear complexity                                | Demo Migration as decision evidence | Drawing conclusions from too few samples.       |

A strong service decision should make the project easier to validate. If the chosen path leaves the team unsure what should happen to important products, rules, content, custom fields, or integrations, the approach is not ready.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Shopware migration approach depends on the relationship between supported data, target operating model, review capacity, and custom-scope risk. Standard Service can work when the data and setup are ordinary. Managed Service helps when coordination and validation risk are higher. Add-ons refine supported migration behavior. Custom Service handles unsupported, custom, extension-owned, or bespoke requirements.

Shopware rewards clarity. When catalog samples, sales-channel decisions, commercial rules, content priorities, custom fields, integrations, Demo Migration findings, Entity Points implications, and later migration actions are understood before launch, the migration approach becomes easier to choose and easier to defend.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for Shopware?**

Standard Service may be enough when supported records are ordinary, the target setup is clear, custom fields are limited, extension data is not part of expected scope, and the merchant can handle preparation and validation.

**When should a Shopware migration use Managed Service?**

Managed Service is useful when the migration is supported but coordination is difficult, several teams must review outcomes, Demo Migration findings need guided interpretation, or launch timing requires stronger sequencing.

**What is the difference between Add-ons and Custom Service for Shopware?**

Add-ons adjust supported filtering, mapping, or configuration behavior. Custom Service handles unsupported extension data, custom fields, bespoke transformation, Custom Platform handling, external-system identifiers, or custom migration logic beyond standard capability.

**How should Entity Points be considered for Shopware?**

Entity Points matter when new eligible records are migrated for the first time. Repeating records already counted through the service license does not automatically consume additional Entity Points simply because another migration action occurs.

**Why should Demo Migration influence the service path?**

Demo Migration shows whether representative Shopware samples migrate cleanly, whether target configuration is ready, whether Add-ons are needed, and whether unsupported data should move into Custom Service review.
