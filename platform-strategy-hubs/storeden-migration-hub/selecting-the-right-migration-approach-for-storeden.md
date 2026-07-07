# Selecting the Right Migration Approach for Storeden

Selecting the right Storeden migration approach means matching the service path to the real operating complexity of the store. Storeden’s role as a TeamSystem Commerce environment can make it a practical target for merchants that want cloud commerce, catalog and inventory control, professional order management, integrated payments, logistics, marketplace selling, apps, API resources, and business-system connections. Those same strengths also create planning questions that should be answered before Full Migration.

The right approach is not determined by platform name alone. It depends on the shape of the source data, the target Storeden setup, the amount of execution support the merchant wants, and whether the expected result requires supported data migration, optional Add-ons, Custom Service, or post-migration target configuration.

A Storeden project should be selected through evidence: catalog samples, customer and order examples, marketplace dependencies, app-owned values, TeamSystem or external identifiers, SEO continuity requirements, and Demo Migration results. The decision should be clear enough that everyone understands what Next-Cart is migrating, what Storeden must be configured to handle, and what the merchant or connected providers must prepare outside the migration itself.

### Storeden Approach Selection Principle <a href="#storeden-approach-selection-principle" id="storeden-approach-selection-principle"></a>

A Storeden migration approach should answer two questions at the same time: how much migration support is needed, and how much customization is required. These are related, but they are not the same.

A merchant may have clean supported data but want Next-Cart to manage execution. That points toward Managed Service. Another merchant may be comfortable with self-managed execution but require custom handling for app data, marketplace identifiers, or external-system references. That points toward Custom Service. A third merchant may only need supported filtering or mapping, which may fit an Add-on rather than a custom project.

| Decision factor                 | What it means for Storeden                                                                                                | Likely service implication                                               |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Supported data structure        | Products, Customers, Orders, Categories, Reviews, Coupons, CMS, and SEO values fit supported migration behavior.          | Standard Service or Managed Service may be sufficient.                   |
| Execution burden                | The merchant wants Next-Cart to handle migration execution rather than self-performing key steps.                         | Managed Service may be more appropriate than Standard Service.           |
| Filtering or mapping need       | Eligible records need controlled selection or supported field alignment.                                                  | Add-ons may improve the result while staying within supported scope.     |
| Custom or unsupported data      | App data, external IDs, marketplace values, custom product logic, or TeamSystem-related references need special handling. | Custom Service review is required.                                       |
| Target configuration dependency | Payments, logistics, themes, apps, channels, or integrations must be configured in Storeden.                              | This is target setup work and should not be confused with migrated data. |
| Evidence uncertainty            | Demo Migration samples do not yet prove that the selected path fits the real store.                                       | Review the approach before approving Full Migration.                     |

The safest approach is the lightest path that still protects the expected result. Choosing a heavier path without evidence can waste effort. Choosing a lighter path despite unsupported requirements can create launch risk.

### When Standard Service Can Fit Storeden <a href="#when-standard-service-can-fit-storeden" id="when-standard-service-can-fit-storeden"></a>

Standard Service can fit when the source store has clean supported data, the merchant can prepare the target Storeden store, and the expected result does not depend on custom migration logic. This is most likely when catalog structure is understandable, product options are not unusually complex, orders are needed mainly for historical review, customers and addresses are ordinary, and the merchant can configure Storeden payments, logistics, themes, apps, and marketplace channels separately.

Standard Service is strongest when the merchant has enough internal clarity to review Demo Migration results, identify errors, and continue with Full Migration once the sample result is acceptable.

| Standard-fit signal                | Storeden interpretation                                                                                           | Evidence to confirm                                                                       |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Catalog data is clean              | Products, images, prices, categories, and stock values fit supported target structures.                           | Product samples display correctly in Storeden.                                            |
| Product options are predictable    | Variants or options do not require bespoke transformation.                                                        | Variant products retain SKU, price, stock, and image meaning.                             |
| Customer data is ordinary          | Customers, addresses, and order links do not depend on unusual account logic.                                     | Representative customer histories remain understandable.                                  |
| Orders are historical records      | Past orders are needed for service and finance review, not to rebuild live checkout rules.                        | Order samples show products, totals, payment labels, shipping labels, and status meaning. |
| Storeden setup is owned separately | Theme, payment, shipping, logistics, apps, marketplaces, and integrations will be configured in the target store. | Migration acceptance is not tied to unfinished configuration work.                        |

Standard Service should not be selected simply because the store is small. A smaller store with app-owned data, custom product behavior, or external identifiers may still need Custom Service. A larger store with clean supported structures may remain standard if the merchant can manage preparation and review.

### When Managed Service Is a Better Fit <a href="#when-managed-service-is-a-better-fit" id="when-managed-service-is-a-better-fit"></a>

Managed Service is appropriate when the data can remain within supported migration capability, but the merchant wants Next-Cart to manage the migration execution process. The need is operational assistance, not necessarily customization.

This can be valuable for Storeden projects where the merchant has a meaningful catalog, customer/order history, SEO concerns, or launch timeline, but does not want to manage each migration step independently. Managed Service can help reduce execution burden while keeping the migration within supported structures.

| Managed-fit signal                            | Why it matters                                                                         | What still remains outside migration                                                               |
| --------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| The merchant wants guided execution           | The project needs a clearer process and less customer-side handling.                   | Target Storeden settings still need merchant or platform-side configuration.                       |
| Data is supported but review workload is high | Product, customer, order, and SEO samples require organized review.                    | Business decisions about scope, exclusions, and target setup remain the merchant’s responsibility. |
| Launch timing needs coordination              | Migration timing, Demo Migration review, and Full Migration acceptance need structure. | Live payment, logistics, app, channel, and integration readiness still need separate confirmation. |
| Internal team capacity is limited             | The merchant may not have time to manage each migration step alone.                    | Custom requirements still require Custom Service if they go beyond supported behavior.             |

Managed Service should not be used as a substitute for Custom Service. If the expected result depends on custom field handling, app data, marketplace-specific identifiers, external-system data, or custom transformation, the requirement still needs Custom Service review even if the merchant also wants managed execution.

### Where Add-ons Can Help <a href="#where-add-ons-can-help" id="where-add-ons-can-help"></a>

Add-ons help when the data remains within supported migration behavior but needs more control. For Storeden, Add-ons are most relevant when the merchant wants to filter eligible records, map supported values more carefully, or configure supported migrated values before they reach the target store.

| Add-on                  | Storeden use case                                                                                              | Boundary to keep clear                                                                 |
| ----------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Migrate only selected eligible products, customers, orders, CMS pages, Blog Posts, or other supported records. | Estimated entity numbers are not filters. Filtering should be configured deliberately. |
| Advanced Data Mapping   | Align supported product, customer, order, category, content, or SEO values with Storeden-facing structures.    | Mapping must stay within supported platform capability.                                |
| Advanced Data Configure | Adjust supported values such as selected labels, names, statuses, or other supported fields before migration.  | Configuration does not create custom app migration or unsupported logic.               |

Add-ons are useful when the merchant can clearly describe what should be filtered, mapped, or adjusted and the requested behavior stays within supported migration capability. If the Add-on itself needs modification beyond available settings, the requirement moves into Custom Service because customized handling is required.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is required when the expected Storeden result depends on customization, unsupported app or plug-in data, custom fields, Custom Platform interpretation, external-system identifiers, marketplace-specific handling, or custom migration logic adjustment.

Storeden projects can require Custom Service when the business depends on data that is not ordinary catalog, customer, order, category, content, or SEO migration output. This is especially important when the previous store used apps, ERP connections, marketplace feeds, B2B logic, bespoke checkout behavior, custom order metadata, or integration IDs that staff still need after launch.

| Custom Service signal                      | Storeden example                                                                                                         | Why Standard Service or Add-ons may not be enough                                              |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| App-owned data carries business meaning    | App fields control promotions, customer groups, marketplace listings, or fulfillment context.                            | Standard migration may not include unsupported app data.                                       |
| External identifiers must remain usable    | ERP, accounting, warehouse, POS, CRM, or TeamSystem-related IDs are required after launch.                               | These identifiers may need custom mapping or transformation.                                   |
| Product behavior is bespoke                | Bundles, configurable products, nonstandard variants, custom fields, or channel-specific attributes affect selling.      | The data may not fit ordinary product/variant structures.                                      |
| Marketplace values need special handling   | Marketplace IDs, channel categories, listing statuses, or origin references must be preserved.                           | Channel data may differ from standard storefront catalog data.                                 |
| Orders contain custom operational metadata | Payment references, logistics IDs, fulfillment notes, tax labels, or external references require special interpretation. | Historical order import may not preserve the expected operational context without custom work. |
| Custom Platform source is involved         | The source system is bespoke or lacks predictable export structure.                                                      | Custom interpretation is needed before migration rules can be applied.                         |

Custom Service defines the customization path. It does not automatically mean full execution management unless migration management is included in the final plan.

### Entity Points and Migration Scope Impact <a href="#entity-points-and-migration-scope-impact" id="entity-points-and-migration-scope-impact"></a>

Entity Points matter because a migration may consume allowance based on the selected entities and the way records are migrated. Storeden planning should review Entity Points before Full Migration when the source store has high record volume, duplicate records, multiple language/content versions, marketplace-origin records, or historical order volume that may affect scope.

| Scope signal                  | Why it matters                                                                                           | Planning response                                                                    |
| ----------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Large catalog volume          | Products, variants, images, categories, and attributes can increase review workload and migration scope. | Confirm record counts and representative product complexity before Full Migration.   |
| Large order history           | Historical orders can create significant scope even when the current catalog is small.                   | Decide whether full history is needed or whether filtering is appropriate.           |
| Duplicate or obsolete records | Old test data, archived products, or inactive customers may consume scope without business value.        | Consider cleanup or Data Filter Add-on before migration.                             |
| Multi-channel records         | Marketplace products, channel orders, and duplicated references may create ambiguity.                    | Identify whether records should migrate as standard history or need custom handling. |
| CMS and content volume        | CMS pages, Blog Posts, landing pages, and SEO records may add meaningful scope.                          | Prioritize content that affects trust, SEO, or conversion.                           |

Entity Points should be discussed as a scope-control issue, not only a pricing detail. If the merchant migrates unnecessary historical or duplicate data, they may spend project capacity on records that do not improve launch quality.

### Additional Migration Options and Later Migration Actions <a href="#additional-migration-options-and-later-migration-actions" id="additional-migration-options-and-later-migration-actions"></a>

Additional Migration Options should be considered when they solve a Storeden-specific migration need, not because they are available. The same rule applies to later migration actions after the initial migration.

| Need                                                      | Suitable handling                                                       | Storeden planning note                                                                  |
| --------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Preserve relationships or supported values more carefully | Relevant Additional Migration Options or Add-ons, depending on the need | Confirm the option changes the Storeden result in a useful way.                         |
| Move newly created records after the first run            | Continue the Migration with the last used configuration                 | Useful when new source records were created after the earlier migration run.            |
| Change settings or scope before continuing                | Continue the Migration with a new configuration                         | Useful when the merchant needs a different mapping, filtering, or entity selection.     |
| Start a separate migration plan                           | Perform a new migration                                                 | Useful when the project changes substantially or the target plan is no longer the same. |

Later migration actions should be chosen based on what changed: the data, the configuration, or the whole project plan. They should not be used as generic cleanup labels.

### Demo Migration as the Approach Checkpoint <a href="#demo-migration-as-the-approach-checkpoint" id="demo-migration-as-the-approach-checkpoint"></a>

Demo Migration should confirm whether the selected approach matches Storeden reality. The sample set should include records that expose product, catalog, customer, order, content, marketplace, app, and integration complexity.

| Demo sample                     | What it should prove                                                                                  | What failure suggests                                        |
| ------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Variant product                 | Options, SKU, stock, price, and images remain meaningful.                                             | Mapping or Custom Service review may be needed.              |
| Marketplace-sensitive product   | Channel identifiers or listing context are visible where required.                                    | Marketplace data may need separate handling.                 |
| Customer with order history     | Account details, addresses, and order links are understandable.                                       | Customer/order relationship review is needed.                |
| B2B or company-related customer | Company, tax, group, or account context is preserved where scoped.                                    | B2B logic may require Custom Service or target setup.        |
| Complex order                   | Products, discounts, taxes, payment labels, shipping labels, and fulfillment context remain readable. | Order-history meaning may require mapping or custom review.  |
| External-system record          | ERP, accounting, warehouse, API, or TeamSystem-related IDs appear as expected.                        | Integration-dependent data may require Custom Service.       |
| Priority URL or content page    | SEO and content continuity can be evaluated.                                                          | Redirect, CMS, or manual content planning may be incomplete. |

If Demo Migration results prove the selected approach, the project can move forward with stronger confidence. If the sample exposes unsupported data, app dependencies, missing external IDs, unclear order context, or weak product meaning, the service path should be reviewed before Full Migration.

### Warning Signs the Approach Is Too Light <a href="#warning-signs-the-approach-is-too-light" id="warning-signs-the-approach-is-too-light"></a>

A Storeden approach may be too light when it focuses on record movement while ignoring operational dependencies. This is most common when merchants assume the target platform will recreate old workflows automatically.

Common warning signs include:

* marketplace products or orders matter, but channel identifiers are not included in scope review;
* TeamSystem, ERP, accounting, warehouse, CRM, POS, or API references are operationally important but not sampled;
* apps or plug-ins control pricing, customer groups, fulfillment, marketing, or reporting;
* product options, attributes, filters, or stock rules are treated as plain text;
* B2B behavior is expected without confirming account, price, tax, or approval logic;
* orders are accepted without checking payment, shipping, fulfillment, refund, tax, or logistics context;
* live checkout, payment providers, logistics, marketplaces, and apps are confused with migrated history;
* SEO review is delayed until after launch;
* Demo Migration samples include only easy records.

When these signs appear, the project should not proceed to Full Migration without approach review. The next step may be better Demo Migration sampling, Add-on configuration, Custom Service review, or a clearer separation between migration scope and Storeden setup.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Storeden migration approach depends on whether the project needs standard supported migration, Next-Cart-led execution, optional filtering or mapping, Custom Service, or a combination of these. Standard Service can work for clean supported structures. Managed Service can help when execution support is the main need. Add-ons can refine supported filtering, mapping, and value configuration. Custom Service is required when the expected result depends on unsupported data, app-owned values, external identifiers, marketplace-specific handling, Custom Platform interpretation, or custom migration logic adjustment.

Demo Migration should be the checkpoint that confirms the decision. If representative products, customers, orders, marketplace records, external identifiers, and priority URLs behave as expected, the selected path is easier to approve. If they expose unsupported data or custom logic, the approach should be adjusted before Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a Storeden migration?**

Standard Service can be enough when the source data fits supported migration behavior, the merchant can manage the target Storeden setup, and the expected result does not require app data, external identifiers, custom transformation, or unsupported logic.

**When should Managed Service be selected instead?**

Managed Service is useful when the data fits supported migration capability but the merchant wants Next-Cart to manage execution. It helps with process burden, but it does not replace Custom Service when customization is required.

**How do Add-ons differ from Custom Service for Storeden?**

Add-ons support bounded filtering, mapping, or configuration for supported migration data. Custom Service is required when the project needs unsupported data handling, app or plug-in data, external identifiers, Custom Platform interpretation, or custom migration logic adjustment.

**Why are Entity Points important when choosing the approach?**

Entity Points help clarify scope impact. Large catalogs, large order histories, duplicate records, marketplace-origin data, and content volume can affect the migration plan. Reviewing scope early helps avoid moving unnecessary data or underestimating complexity.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that representative Storeden records behave correctly: products, variants, stock values, categories, customers, orders, marketplace-sensitive values, external identifiers, and priority URLs or content pages. If those samples reveal unsupported data or custom requirements, the approach should be reviewed before Full Migration.
