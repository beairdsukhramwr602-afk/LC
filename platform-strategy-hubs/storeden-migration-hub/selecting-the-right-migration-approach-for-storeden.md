# Selecting the Right Migration Approach for Storeden

Choosing the right migration approach for Storeden depends on how much of the current store can move into standard Storeden structures and how much depends on custom logic, apps, marketplace workflows, external business systems, or unsupported data relationships.

Storeden is a hosted cloud commerce environment. That makes service-path selection different from a migration into a fully self-hosted custom stack. Product, customer, order, and content records may fit standard migration capability, while checkout behavior, payment setup, logistics, marketplace synchronization, TeamSystem ecosystem workflows, app-owned data, API references, and storefront theme behavior often need separate review.

The goal is not to choose the largest service model by default. The goal is to match the migration approach to the actual burden: how clean the source data is, how much target configuration is needed, how many connected systems affect the result, and whether any requirement goes beyond standard service capability.

### The Practical Approach Question for Storeden <a href="#the-practical-approach-question-for-storeden" id="the-practical-approach-question-for-storeden"></a>

A Storeden migration approach should answer one practical question:

**Can the current store’s data and operating meaning be represented inside Storeden with standard service capability, or does the project need Next-Cart-led execution, optional Add-ons, or Custom Service review?**

The answer usually depends on five areas:

| Planning area                   | Why it affects the migration approach                                                                                                                    |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure               | Products, variants, attributes, SKUs, categories, filters, images, inventory, and marketplace-ready fields decide how much mapping and review is needed. |
| Order history                   | Orders may include payment labels, shipping methods, tracking numbers, fulfillment status, customer links, marketplace origin, and external references.  |
| Storefront and SEO              | Theme expectations, CMS Pages, Blog Posts, navigation, domains, URLs, redirects, metadata, and content presentation affect launch quality.               |
| Apps and marketplace channels   | Apps, plugins, Amazon, eBay, Facebook, AliExpress, and other channel workflows can create data or behavior outside ordinary Storeden records.            |
| TeamSystem and API integrations | ERP, accounting, POS, inventory, fulfillment, API, webhook, or developer workflows can depend on identifiers and logic that need separate handling.      |

A store with clean catalog records and predictable historical data may not need a complex approach. A store where daily operations depend on apps, marketplaces, TeamSystem integrations, custom attributes, or external IDs should be reviewed more carefully before Full Migration.

### When Standard Service Is Usually Enough <a href="#when-standard-service-is-usually-enough" id="when-standard-service-is-usually-enough"></a>

Standard Service can be suitable when the Storeden migration fits supported data structures and the customer is comfortable self-performing the migration process on the Next-Cart website.

Standard Service is usually a reasonable starting point when the source store has:

* products that can be represented through supported Storeden product structures;
* manageable variants, SKUs, images, prices, descriptions, categories, and stock values;
* customer records that do not depend on unusual account or B2B logic;
* historical orders that mainly need readable order, customer, product, payment, shipping, and status context;
* CMS Pages or Blog Posts that fit supported migration scope;
* no required migration of unsupported app, marketplace, ERP, API, or webhook-owned data;
* no custom migration logic adjustment requirement.

Standard Service does not mean the project is risk-free. It means the customer-led migration can proceed within standard service capability, with support available when questions arise. Target-side setup still matters. Storeden payment methods, TS Pay, shipping rules, logistics services, tax behavior, marketplace publication, app configuration, storefront theme work, and domain settings are not proven merely because records have migrated.

### When Managed Service Is the Better Fit <a href="#when-managed-service-is-the-better-fit" id="when-managed-service-is-the-better-fit"></a>

Managed Service can be suitable when the Storeden migration still fits standard service capability, but the customer wants Next-Cart’s technician to perform the migration instead of self-performing it.

Managed Service is often the better fit when:

| Situation                                                  | Why Managed Service helps                                                                                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| The merchant has limited migration time                    | Next-Cart-led execution reduces the customer’s direct operational burden during migration setup and run.                                 |
| The catalog has many records but standard structures       | The data may not require customization, but execution and result review still benefit from experienced handling.                         |
| The team needs support interpreting Demo Migration results | Next-Cart can run the migration under standard capability while the customer focuses on reviewing business-critical samples.             |
| The store has several ordinary data types                  | Products, customers, orders, CMS Pages, and Blog Posts may fit standard capability but still require careful execution order and review. |
| The customer prefers guided migration responsibility       | Managed Service gives clearer execution responsibility while keeping the project within standard service scope.                          |

Managed Service does not automatically cover customized data handling. If the migration needs tailored app data handling, marketplace identifier preservation, API-owned records, TeamSystem workflow logic, or custom product transformation, the requirement moves into Custom Service because customization is required.

### Where Add-ons Can Help <a href="#where-add-ons-can-help" id="where-add-ons-can-help"></a>

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. For Storeden, Add-ons are most relevant when the data still fits supported platform behavior but needs more control over which records move, how fields align, or how values are adjusted.

| Add-on                  | Storeden migration use case                                                                                                                                          | Important boundary                                                                                   |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Use when only selected eligible products, customers, orders, CMS Pages, Blog Posts, or other supported records should migrate.                                       | Estimated entity numbers are not migration filters. Filtering should be configured deliberately.     |
| Advanced Data Mapping   | Use when supported fields need clearer alignment between the Source Platform and Storeden structures, such as catalog, customer, order, category, or content values. | Mapping must remain within supported platform data-model capability.                                 |
| Advanced Data Configure | Use when supported migrated values should be modified before they reach Storeden, such as selected labels, names, statuses, or other supported values.               | Configuration does not replace custom logic, app migration, or unsupported external-system behavior. |

Add-ons are not a substitute for Custom Service. If an Add-on needs modification beyond its available settings and supported behavior, the tailored requirement is handled through Custom Service because customization is required.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is required when the Storeden migration includes customization, modification, bespoke handling, Custom Platform source interpretation, unsupported app data, external-system identifiers, or custom migration logic adjustment.

Storeden projects often move into Custom Service when the migration includes:

* a Custom Platform as the Source Platform;
* app or plugin data that is not part of standard migration capability;
* B2B app behavior, customer-group logic, or account rules that need custom handling;
* marketplace identifiers or channel-specific records that must be preserved in a particular way;
* TeamSystem ERP, accounting, POS, inventory, or management-system identifiers that affect operations;
* API, webhook, developer, or external application data that carries business meaning;
* custom product attributes, configurable logic, bundles, nonstandard variants, or bespoke inventory behavior;
* custom order relationships, fulfillment references, payment references, tax logic, or logistics data;
* storefront, SEO, URL, domain, or redirect transformations beyond standard capability;
* custom migration logic adjustment to make the migrated result match project-specific expectations.

Custom Service does not automatically mean Next-Cart-led execution. Custom Service defines the customization or modification path. Migration management is included only when it is part of the final plan.

### Choosing Between Standard, Managed, Add-ons, and Custom Service <a href="#choosing-between-standard-managed-add-ons-and-custom-service" id="choosing-between-standard-managed-add-ons-and-custom-service"></a>

A Storeden project can be evaluated through a simple decision pattern:

| Migration condition                                                                                                 | Better approach                                                     | Reasoning                                                                                       |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Clean supported data, predictable Storeden structures, customer-led execution is acceptable                         | Standard Service                                                    | The migration can remain within standard service capability.                                    |
| Clean supported data, but the customer wants Next-Cart-led execution                                                | Managed Service                                                     | The service burden is execution, not customization.                                             |
| Only selected eligible records should migrate                                                                       | Standard or Managed Service with Data Filter Add-on                 | Filtering is an optional service feature when supported and properly configured.                |
| Supported fields need clearer alignment                                                                             | Standard or Managed Service with Advanced Data Mapping              | Mapping can improve target interpretation without creating custom migration logic.              |
| Supported values should be adjusted before migration                                                                | Standard or Managed Service with Advanced Data Configure            | Value configuration can improve the target result when the change is within supported behavior. |
| Custom Platform source, app data, external identifiers, API records, marketplace IDs, or bespoke logic are required | Custom Service                                                      | The requirement goes beyond standard service capability or Standard Add-on behavior.            |
| The merchant needs customization and wants Next-Cart to manage execution                                            | Custom Service with migration management included in the final plan | Custom work and execution responsibility must both be planned explicitly.                       |

The safest approach is the one that matches actual complexity. A store does not need Custom Service only because it uses Storeden, marketplaces, or TeamSystem-related products. It needs Custom Service when the required migration outcome depends on customization, unsupported structures, app-owned data, external-system data, or custom migration logic adjustment.

### Demo Migration as the Approach Checkpoint <a href="#demo-migration-as-the-approach-checkpoint" id="demo-migration-as-the-approach-checkpoint"></a>

Demo Migration is a practical way to check whether the selected approach is realistic. For Storeden, the Demo Migration should not be limited to simple products or a small set of ordinary orders. It should include records that reveal whether the chosen service path can support the real operating model.

Strong Storeden Demo Migration samples include:

| Sample type                                 | What it should prove                                                                                                    |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Product with variants and attributes        | Product choices, SKU behavior, pricing, images, stock, and storefront presentation remain understandable.               |
| Category, subcategory, and filter sample    | Product discovery works in the target storefront and does not rely only on product record presence.                     |
| Marketplace-relevant product                | Channel-sensitive values, identifiers, availability expectations, and publication requirements are visible for review.  |
| Customer or B2B-related sample              | Account meaning, customer details, contact context, or B2B-related expectations are not flattened.                      |
| Order with payment and shipping context     | Historical order detail remains readable for service, fulfillment, finance, and management review.                      |
| Order with tracking or logistics references | Fulfillment history and shipping context remain useful after migration.                                                 |
| App or integration-sensitive record         | App-owned data, external identifiers, TeamSystem references, or API-linked values are identified before Full Migration. |
| Priority URL or content sample              | SEO, domain, URL, metadata, and storefront continuity risks are visible early.                                          |

If Demo Migration results show that the main records fit Storeden without custom treatment, Standard Service or Managed Service may remain appropriate. If the Demo Migration exposes unsupported app data, broken product meaning, missing external references, marketplace identifier problems, or custom transformation needs, the project should move into Custom Service review before Full Migration.

### Signs the Chosen Approach Is Too Light <a href="#signs-the-chosen-approach-is-too-light" id="signs-the-chosen-approach-is-too-light"></a>

A Storeden migration approach may be too light when it focuses only on record counts or assumes that hosted-platform migration automatically covers every operational dependency.

Common warning signs include:

* marketplace records are important, but only ordinary product fields are sampled;
* TeamSystem ERP, accounting, POS, or inventory identifiers are used operationally but not reviewed;
* app or plugin data affects sales, fulfillment, marketing, or reporting but is not scoped;
* product attributes, variants, filters, or inventory rules are treated as simple text fields;
* B2B behavior is expected without confirming target account or app support;
* historical orders are accepted without checking payment, shipping, tracking, logistics, and customer context;
* live checkout, TS Pay, tax, payment gateway, and shipping readiness are confused with migrated order history;
* SEO review is delayed until after launch planning;
* the customer expects source theme or code behavior to transfer into Storeden without target theme work;
* Demo Migration samples contain only easy records.

When these signs appear, the project should not proceed to Full Migration without approach review. The right next step may be better Demo Migration sampling, Add-on review, Custom Service review, or a clearer separation between migrated data and Storeden configuration work.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Storeden migration approach depends on whether the project is mainly a standard data migration into hosted Storeden structures or whether it also needs filtering, mapping, value configuration, customization, app handling, marketplace-specific treatment, TeamSystem integration review, or custom migration logic adjustment. Standard Service can work for clean supported structures, Managed Service can help when execution support is the main need, Add-ons can refine supported filtering, mapping, and configuration, and Custom Service is required when customization or unsupported data handling is part of the expected result.

Before choosing the final approach, review the most complex Storeden records in Demo Migration: variants, attributes, stock-sensitive products, categories and filters, marketplace-linked records, app-dependent data, TeamSystem references, historical orders, payment and logistics context, and priority URLs. If those samples behave as expected, the selected approach is easier to confirm. If they expose unsupported data or custom logic, discuss the findings through Live Chat before moving into Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for a Storeden migration?**

Standard Service can be enough when the source store uses clean supported product, customer, order, content, and catalog structures, and the customer is comfortable self-performing the migration process. Storeden payment setup, shipping, logistics, apps, marketplace channels, themes, and integrations still need separate target review.

**When should I choose Managed Service for Storeden?**

Managed Service is useful when the migration fits standard service capability but the customer wants Next-Cart-led execution. It is not the same as customization. If the project requires app data handling, marketplace identifier preservation, TeamSystem integration data, or custom migration logic adjustment, Custom Service is the correct review path.

**Can Add-ons help with Storeden migration requirements?**

Yes. The Data Filter Add-on can help select eligible records for migration, Advanced Data Mapping can help align supported fields, and Advanced Data Configure can help adjust supported migrated values. Add-ons remain optional service features and do not replace Custom Service for customized or unsupported requirements.

**When does a Storeden migration need Custom Service?**

Custom Service is required when the migration needs customization, modification, bespoke handling, Custom Platform source interpretation, unsupported app or plugin data, marketplace-specific identifier handling, TeamSystem system references, API or webhook data, or custom migration logic adjustment.

**Does Custom Service automatically mean Next-Cart performs the migration?**

No. Custom Service defines the customization or modification path. Migration management is included only when it is part of the final plan. A Storeden project can involve Custom Service for tailored work without automatically making every execution step Next-Cart-led.
