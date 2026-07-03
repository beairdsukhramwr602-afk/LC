# Selecting the Right Migration Approach for CS-Cart

Choosing the right CS-Cart migration approach depends on how much business meaning sits behind the source data. A clean store with ordinary Products, Customers, Orders, Categories, CMS Pages, Blog Posts, Reviews, Coupons, and URLs may fit a straightforward Migration Service path. A marketplace, B2B-like model, heavily customized catalog, add-on-dependent store, or source with vendor responsibility may need more planning before the service path is selected.

The approach should not be chosen by record count alone. CS-Cart migration planning should consider catalog structure, vendor ownership, customer groups, storefront routes, add-on dependencies, custom fields, external identifiers, and the merchant’s ability to review Demo Migration results. The right approach is the one that preserves business meaning without pretending that configuration, custom behavior, or marketplace logic is ordinary data.

For CS-Cart, the main decision is whether the migration can stay within Standard Service, whether Managed Service is safer because execution should be handled by Next-Cart, whether Add-ons can handle focused filtering or mapping needs, or whether Custom Service is required because the source or target result needs customization, modification, or custom migration logic adjustment.

### What the Migration Approach Must Decide <a href="#what-the-migration-approach-must-decide" id="what-the-migration-approach-must-decide"></a>

A CS-Cart migration approach should decide who owns execution, how much interpretation the source data needs, and which parts of the target result can be handled by standard migration capability. The approach should also define how Demo Migration will be used before Full Migration and whether follow-up changes may require Additional Migration Options.

The first decision is whether the source structure is standard enough for direct handling. Products, categories, customers, orders, reviews, coupons, and content may be suitable for Standard Service when field meaning is clear and target expectations are ordinary. But CS-Cart projects often involve areas that need more interpretation: product features versus options, category hierarchy, vendor-owned products, vendor administrator accounts, customer groups, add-on-created fields, marketplace commissions, and external system IDs.

The second decision is whether the merchant can manage execution. Some merchants can configure the service, run Demo Migration, review samples, adjust settings, and proceed to Full Migration. Others need Next-Cart-led operation because the store is large, business-critical, marketplace-sensitive, or difficult to validate.

| Approach question                                         | Why it matters for CS-Cart                                                             | Direction it suggests           |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------- |
| Is the source data structurally clear?                    | Standard records can be interpreted with less custom review.                           | Standard Service may fit.       |
| Does the merchant want Next-Cart to perform execution?    | The migration may be standard, but customer-led operation may be inefficient or risky. | Managed Service may fit.        |
| Are focused filtering or mapping changes needed?          | Some requirements stay within bounded migration support.                               | Add-ons may help.               |
| Does the source contain custom or unsupported structures? | Custom fields, marketplace logic, or external IDs may need bespoke handling.           | Custom Service may be required. |
| Does Demo Migration expose missing business meaning?      | The selected service path may be too light.                                            | Escalate before Full Migration. |

The approach should be selected before Full Migration, then tested with representative samples. If Demo Migration shows that the selected approach cannot preserve catalog, vendor, customer, order, or route meaning, the merchant should adjust the service path before broader execution.

### When Standard Service Can Fit <a href="#when-standard-service-can-fit" id="when-standard-service-can-fit"></a>

Standard Service can fit a CS-Cart migration when the merchant’s source data is structurally clear and the expected target result fits supported migration behavior. It is most suitable when Products, Categories, Customers, Orders, Reviews, Coupons, CMS Pages, Blog Posts, and URLs can be interpreted without custom logic, unsupported source fields, or marketplace-specific transformation.

For CS-Cart, Standard Service is strongest when the target store is a conventional online store or a clearly structured catalog where product relationships are understandable. Product names, SKU/code values, descriptions, prices, stock, images, category assignments, status, customer accounts, order history, reviews, coupons, and content should have direct business meaning. The merchant should also be comfortable configuring the service, checking Demo Migration, and confirming the result.

Standard Service may also fit some marketplace-adjacent projects if vendor-related requirements are outside migration scope or if marketplace setup is handled separately in the Target Platform. But the merchant should not assume vendor ownership, commissions, payout references, seller dashboards, or marketplace governance will be preserved as ordinary data unless the service scope confirms it.

| Standard Service fit signal                                       | Why it supports a standard path                                           |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Products and categories are clean and commercially understandable | Catalog data can be moved and validated without extensive interpretation. |
| Product features, options, and variations are documented          | The merchant can review whether target product structure is correct.      |
| Customer and order history are ordinary records                   | Account and order continuity can be validated through samples.            |
| Marketplace logic is not part of required migration scope         | Vendor complexity does not need to be solved by standard data movement.   |
| Add-on or custom-field data is not launch-critical                | The migration can focus on supported entities and target configuration.   |
| The merchant can operate and review the process                   | Customer-led execution is realistic.                                      |

Standard Service should not be chosen just because it is simpler. It should be chosen because the source structure and target expectations are clear enough for a standard path. When there is uncertainty, Demo Migration should include difficult records rather than only clean examples.

### When Managed Service Is the Safer Path <a href="#when-managed-service-is-the-safer-path" id="when-managed-service-is-the-safer-path"></a>

Managed Service is appropriate when the migration can still use standard service capability but the merchant wants Next-Cart to perform the migration. This can be valuable for CS-Cart projects where the source structure is not custom enough to require Custom Service, but the business risk, data volume, marketplace sensitivity, or validation burden makes customer-led execution less practical.

A merchant may choose Managed Service when the store is active and commercially important, when downtime planning matters, when the team lacks migration experience, when vendor or catalog samples need careful review, or when multiple validation rounds are expected. Managed Service does not turn unsupported custom requirements into supported standard migration. It changes execution ownership, coordination, and operational support within the agreed service scope.

Managed Service can be especially useful for CS-Cart when the merchant must coordinate source access, Demo Migration review, Full Migration timing, and post-migration checks around business operations. A marketplace or large catalog project may still need Custom Service for certain requirements, but Managed Service can reduce execution risk when the core migration itself remains standard.

| Managed Service signal                                              | Why it matters                                                                 |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| The source store is active and order flow must be managed carefully | Execution timing and review coordination become more important.                |
| The catalog is large but structurally clear                         | Standard migration may fit, but customer-led operation may be too burdensome.  |
| The merchant wants Next-Cart to operate the migration               | Execution ownership shifts from customer-led to Next-Cart-led handling.        |
| Demo Migration review requires coordination across teams            | Product, order, vendor, content, and SEO checks may need structured follow-up. |
| The business has limited internal migration capacity                | Managed execution reduces avoidable process burden.                            |

Managed Service should be selected for the right reason. It is not a shortcut around source ambiguity. If the source store contains custom marketplace data, unsupported records, modified database structures, external identifiers, or custom migration logic needs, Custom Service may still be required.

### When Add-ons Can Improve the Migration Scope <a href="#when-add-ons-can-improve-the-migration-scope" id="when-add-ons-can-improve-the-migration-scope"></a>

Add-ons can help when the merchant needs focused support that remains within supported migration behavior. For CS-Cart, Add-ons are often useful when the merchant needs to filter records, map supported values, configure selected fields, or adjust bounded migration output. They should not be used as a substitute for Custom Service when the requirement is actually custom transformation or unsupported source interpretation.

A Data Filter Add-on can help when only selected records should be migrated, such as products from specific categories, recent orders, selected customers, or specific content types. Advanced Data Mapping can help when source values need to align with supported target structures, such as customer groups, categories, tax-related values, or product attributes. Advanced Data Configure can help when selected values need controlled adjustment before reaching the Target Platform.

| Add-on type                | CS-Cart use case                                                                                     | Boundary to respect                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Data Filter Add-on         | Migrate selected Products, Customers, Orders, Blog Posts, or other eligible records.                 | Entity counts entered for pricing do not act as filters by themselves.             |
| Advanced Data Mapping      | Align supported source values with target categories, groups, attributes, or other supported fields. | Mapping cannot recreate unsupported marketplace behavior or custom database logic. |
| Advanced Data Configure    | Adjust selected values so the migrated data better fits the target setup.                            | Configuration is bounded; bespoke transformation belongs to Custom Service.        |
| Standard Add-ons           | Use available service extensions for defined migration needs.                                        | They should match a specific requirement, not compensate for unclear planning.     |
| Tailored or Custom Add-ons | Modify or create project-specific add-on support.                                                    | These are reviewed through Custom Service because they require customization.      |

Add-ons should be selected after the merchant identifies the exact problem. If the issue is “migrate only certain products,” Data Filter may help. If the issue is “source customer groups need to become target-supported groups,” mapping may help. If the issue is “vendor commission logic must be interpreted from a custom table,” Custom Service is more likely than a Standard Add-on.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is required when the migration needs customization, modification, Custom Platform handling, unsupported data interpretation, custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, or bespoke handling beyond standard service capability. CS-Cart projects may require Custom Service when source data carries marketplace, B2B, add-on, external-system, or custom-field meaning that cannot be handled as ordinary records.

Common Custom Service triggers include vendor ownership that is not stored in a standard way, custom marketplace commissions, seller payout references, modified product structures, special product configurators, source add-on data, customer-company relationships, custom profile fields, ERP identifiers, fulfillment codes, historical reporting keys, and external system references. A heavily modified Source Platform may also require Custom Service because the data model itself may not match standard assumptions.

| Custom Service trigger                        | Why standard handling may not be enough                                            |
| --------------------------------------------- | ---------------------------------------------------------------------------------- |
| Vendor ownership is custom or incomplete      | Marketplace meaning may need interpretation rather than direct field transfer.     |
| Custom fields are launch-critical             | Unsupported fields may need custom mapping, transformation, or preservation.       |
| Add-on-owned data controls business behavior  | The data may sit outside ordinary product/customer/order records.                  |
| B2B or account rules are source-specific      | Customer groups and pricing logic may not translate cleanly.                       |
| External identifiers must remain stable       | ERP, PIM, POS, fulfillment, or accounting references may require bespoke handling. |
| Source Platform is custom or heavily modified | Standard assumptions may not describe the actual data structure.                   |

Custom Service should be considered early, not after Full Migration fails to show expected behavior. If the merchant suspects custom requirements, the safest path is to prepare examples and discuss the requirement before committing to a standard path. The service decision can then distinguish what is migratable as supported data, what belongs to target configuration, what Add-ons can address, and what requires custom handling.

### How Entity Points Affect CS-Cart Scope Planning <a href="#how-entity-points-affect-cs-cart-scope-planning" id="how-entity-points-affect-cs-cart-scope-planning"></a>

Entity Points help size eligible migrated records. For CS-Cart, they are relevant when Products, Customers, Orders, or Blog Posts are migrated under an Entity Points Plan. The key planning rule is that eligible new Products, Customers, Orders, and Blog Posts consume Entity Points when they are first migrated. Records already counted through the service license do not consume again simply because another action happens on the same migration path.

This matters when a CS-Cart migration includes large catalogs, historical order archives, customer databases, or Blog Posts. The merchant should estimate record scope carefully, then decide whether any filtering is needed before migration begins. A Data Filter Add-on may reduce scope when the merchant wants only selected records, but entering a smaller record count for pricing does not filter the migration by itself.

Entity Points should be treated as scope sizing, not a platform-fit score. A store with fewer records may still require Custom Service if vendor ownership or custom fields are complex. A store with many records may still use Standard Service if the structure is clean and expectations are standard.

| Entity Points planning question                                             | CS-Cart implication                                                                 |
| --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Which Products, Customers, Orders, and Blog Posts are eligible new records? | Estimate service license and Entity Points Plan needs accurately.                   |
| Are all historical orders required?                                         | Filtering may be useful if only recent or operationally relevant orders are needed. |
| Are all products launch-relevant?                                           | Obsolete, test, disabled, or vendor-discontinued products may not need migration.   |
| Will Blog Posts be migrated?                                                | Blog scope should be included if content continuity matters.                        |
| Are records being migrated again only because another action occurs?        | Avoid treating already-counted records as newly consumed points without reason.     |

Entity Points planning should happen before Demo Migration so the sample and Full Migration expectations reflect the intended scope. It should also be revisited when Additional Migration Options are considered, especially if the merchant changes the configuration or performs a new migration.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should test whether the selected service path is strong enough. For CS-Cart, a useful Demo Migration should include records that reveal catalog structure, vendor ownership, customer/account context, order readability, content route behavior, and custom-field expectations. The merchant should not limit the sample to easy products if the final store depends on more complex data.

A strong Demo Migration review should answer whether Products appear with the right content, categories, images, stock, status, features, options, and variation behavior; whether vendor-owned records preserve the expected marketplace meaning; whether Customers and Orders remain linked and readable; whether CMS Pages and Blog Posts support content continuity; and whether source-specific fields require mapping, Add-ons, or Custom Service.

| Demo Migration decision                 | What to inspect                                                                                 |
| --------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Is the catalog usable?                  | Products, categories, images, stock, status, features, options, variations, and route behavior. |
| Is marketplace context preserved?       | Vendor ownership, vendor administrator records, vendor products, seller order context.          |
| Are accounts meaningful?                | Customer groups, addresses, vendor administrators, B2B-like account fields.                     |
| Is order history readable?              | Customer links, products, payment/shipping context, tax references, vendor responsibility.      |
| Does content support launch continuity? | CMS Pages, Blog Posts, metadata, product/category routes, redirects.                            |
| Is the selected approach still valid?   | Whether issues can be solved by standard settings, Add-ons, Managed Service, or Custom Service. |

Demo Migration is not only a preview. It is a service-path checkpoint. If the result shows missing vendor meaning, unsupported custom fields, weak account logic, or unclear product structure, the merchant should correct the approach before Full Migration.

### Using Full Migration and Additional Migration Options <a href="#using-full-migration-and-additional-migration-options" id="using-full-migration-and-additional-migration-options"></a>

Full Migration should proceed when the service path has been confirmed and the merchant understands what must be validated after completion. For CS-Cart, the Full Migration plan should define source-store freeze timing, final data capture expectations, vendor or product changes during the migration window, and responsibility for post-migration review.

Additional Migration Options become important when the source store changes after an earlier migration result or when the merchant needs a different handling path. The merchant can continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration. The right choice depends on whether the underlying assumptions stayed the same.

| Follow-up choice                          | Use when                                                                | CS-Cart example                                                                       |
| ----------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Continue with the last used configuration | New records exist but the mapping and target assumptions are unchanged. | New orders and customers were added after Full Migration preparation.                 |
| Continue with a new configuration         | The merchant corrected source structure or changed mapping assumptions. | Categories, customer groups, vendor assignments, or content rules were updated.       |
| Perform a new migration                   | The target plan, source scope, or service path changed substantially.   | Marketplace model, Custom Service requirements, or target setup changed after review. |

Additional Migration Options should be selected based on evidence. If only new orders appeared, the last used configuration may be enough. If vendor assignments were rebuilt, a new configuration may be safer. If the merchant changed from a simple store plan to a Multi-Vendor marketplace plan, a new migration may be more appropriate.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right CS-Cart migration approach depends on data meaning, execution ownership, customization needs, and validation evidence. Standard Service can fit when the source structure is clean and the merchant can run and review the process. Managed Service is safer when the migration can remain standard but the merchant wants Next-Cart-led execution. Add-ons can help with bounded filtering, mapping, and configuration needs. Custom Service is required when the project needs customization, modification, unsupported source handling, Custom Platform support, or custom migration logic adjustment.

The approach should be tested through Demo Migration before Full Migration. When follow-up changes are needed, Additional Migration Options should be selected according to whether the original configuration still applies, a new configuration is needed, or a new migration is the safer path.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Can Standard Service handle a CS-Cart migration?**

Yes, when the source data is structurally clear, target expectations are standard, and the merchant can run and review Demo Migration and Full Migration. It is less suitable when marketplace logic, custom fields, add-on-owned data, or external identifiers require interpretation.

**When should I choose Managed Service for CS-Cart?**

Choose Managed Service when the migration can use standard service capability but customer-led execution would create unnecessary burden or risk. It is useful for larger stores, active businesses, and migrations that require Next-Cart-led operation and coordinated validation.

**Can Add-ons replace Custom Service?**

No. Add-ons can help with bounded filtering, mapping, or data configuration needs. Custom Service is required when the migration needs customization, unsupported source interpretation, custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, or Custom Platform handling.

**How do Entity Points apply to CS-Cart migration?**

Eligible new Products, Customers, Orders, and Blog Posts consume Entity Points when first migrated. Records already counted through the service license do not consume again simply because another action happens on the same migration path.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that the selected approach preserves CS-Cart catalog meaning, vendor context, account relationships, order readability, content continuity, and any custom-sensitive records that affect launch quality.
