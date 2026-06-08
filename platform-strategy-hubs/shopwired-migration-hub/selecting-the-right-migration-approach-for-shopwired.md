# Selecting the Right Migration Approach for ShopWired

Selecting the right migration approach for ShopWired depends on how clearly the source store’s data can be interpreted inside ShopWired’s hosted platform model. A simple catalog, ordinary customers, standard orders, and straightforward content may fit standard service capability. A store with complex product choices, B2B rules, quote workflows, app-owned data, API connections, outside-system identifiers, or custom checkout behavior may need deeper review before the migration path is treated as predictable.

The right approach should be chosen from evidence, not from store size alone. A small store can require Custom Service when product configuration or B2B logic is highly customized. A larger store can still fit standard service capability when the source records are structured predictably and the target expectations match supported ShopWired behavior.

### What Migration Approach Means for ShopWired <a href="#what-migration-approach-means-for-shopwired" id="what-migration-approach-means-for-shopwired"></a>

For ShopWired, migration approach means deciding how much responsibility and customization the project requires. It should clarify whether the merchant can use Standard Service, whether Next-Cart-led execution is needed through Managed Service, whether Standard Add-ons can handle filtering or mapping needs, or whether Custom Service review is required because the migration includes custom, app-owned, integration-owned, or unsupported data.

| Planning signal                                                           | What it means for ShopWired                                                                   | Likely approach direction                   |
| ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------- |
| Standard products, categories, brands, customers, orders, and pages       | Source records fit ordinary ShopWired structures.                                             | Standard Service may be enough.             |
| Standard data, but the merchant wants Next-Cart-led execution             | The migration may not be custom, but service responsibility should shift.                     | Managed Service may be safer.               |
| Only selected eligible records should migrate                             | The requirement is filtering, not a change in platform identity.                              | Data Filter Add-on may be relevant.         |
| Supported fields need controlled mapping                                  | The source and target support the data, but field interpretation needs adjustment.            | Advanced Data Mapping may be relevant.      |
| Migrated values need supported modification                               | Values can be configured before reaching the target store within supported behavior.          | Advanced Data Configure may be relevant.    |
| Complex product choices require non-standard transformation               | Variations, choices, extras, bundles, personalization, or stock behavior may not map cleanly. | Custom Service review may be needed.        |
| B2B, quotes, account terms, or customer-group logic is custom             | The requirement may involve more than ordinary customer records.                              | Custom Service review should be considered. |
| App, API, webhook, marketplace, or external-system data must be preserved | The business meaning may sit outside standard platform data.                                  | Custom Service review is likely needed.     |
| Custom Platform is involved as Source Platform or Target Platform         | Custom platform handling is required.                                                         | Custom Service is required.                 |

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the source data is predictable and the target result can fit ShopWired’s ordinary product, customer, order, category, brand, and content structures without custom interpretation.

This is more likely when the source store has:

* standard products with ordinary prices, images, descriptions, SKUs, stock, categories, and brands;
* product variations or choices that map cleanly into supported ShopWired structures;
* customers and addresses without complex B2B rules;
* historical orders that need ordinary reference value;
* content pages and SEO fields that do not require custom transformation;
* no app-owned data that must be migrated as part of the agreed scope;
* no outside-system identifiers that must be preserved through custom mapping;
* a merchant team that is comfortable self-performing the migration and validating results.

Standard Service does not mean the ShopWired store is automatically ready to launch. Payment, delivery, tax, checkout, theme, content, apps, channels, and integrations still need to be configured and tested in the target store. Standard Service only means the migration itself appears to fit standard capability and customer-led execution.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be a better fit when the data appears to fit standard service capability, but the merchant wants Next-Cart to perform the migration. This can be useful when the store has enough data volume, stakeholder coordination, or review burden that customer-led execution is not the preferred operating model.

Managed Service may be safer when:

* the migration requirement is not custom, but the merchant wants Next-Cart-led execution;
* the merchant wants Next-Cart to run the migration using standard capability and purchased Standard Add-ons;
* the source data is mostly standard, but timing and execution coordination matter;
* the merchant wants to reduce hands-on migration operation while still reviewing results;
* the business has internal teams for catalog, B2B, marketing, and operations validation but prefers not to run the migration process itself.

Managed Service should not be used to hide custom requirements. If the project needs custom product transformation, app-owned data handling, custom B2B logic, external ID preservation, or tailored migration behavior, those requirements should be reviewed through Custom Service even if the merchant also wants Next-Cart-led execution.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when the migration includes customization, modification, bespoke handling, Custom Platform logic, unsupported structures, or custom migration logic adjustment. For ShopWired, this often appears around product choices, B2B behavior, apps, integrations, custom checkout fields, and outside-system dependencies.

Custom Service review should be considered when the source includes:

* product options, modifiers, extras, personalization fields, bundles, or kit logic that cannot map cleanly into standard ShopWired structures;
* custom fields that affect buying, fulfillment, delivery, tax, B2B pricing, or customer service;
* customer groups that control trade pricing, quotes, approval, visibility, account terms, payment access, delivery access, or tax behavior;
* app-owned product, customer, order, checkout, SEO, subscription, quote, or integration records;
* API, webhook, marketplace, ERP, CRM, accounting, POS, fulfillment, or inventory identifiers that must remain traceable;
* source checkout fields or workflows that do not fit ordinary ShopWired settings;
* historical order data with custom operational meaning;
* tailored data transformation beyond Standard Add-on behavior.

Custom Service does not automatically mean Next-Cart performs the migration process for the customer. It means customization or modification work is required. Migration management is included only when it is part of the final plan.

### How Add-ons Fit into a ShopWired Migration <a href="#how-add-ons-fit-into-a-shopwired-migration" id="how-add-ons-fit-into-a-shopwired-migration"></a>

Add-ons can help refine a ShopWired migration when the requirement stays within supported service capability. They should not be used as a substitute for Custom Service when the project requires bespoke transformation or unsupported custom data handling.

| Add-on                  | When it may help in a ShopWired migration                                                                                                                           | Boundary                                                                                                        |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | The merchant wants to migrate only selected eligible records, such as active products, specific customers, recent orders, selected pages, or narrowed catalog data. | Estimated entity quantities are not filters. Filtering must be configured as an explicit migration requirement. |
| Advanced Data Mapping   | Supported source fields need to map into supported ShopWired target fields in a controlled way.                                                                     | If the mapping requires custom logic beyond available behavior, it moves into Custom Service.                   |
| Advanced Data Configure | Migrated values need supported modification before reaching the target store.                                                                                       | If the value change requires tailored behavior beyond available settings, it belongs in Custom Service review.  |

Add-ons are useful when the data is supported but needs selective handling. Custom Service is the correct review path when the business meaning itself is custom, app-owned, integration-owned, or outside standard platform interpretation.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should test whether source data can be interpreted inside ShopWired with the chosen approach. It should not only preview a few easy records.

A strong Demo Migration should help decide whether:

* product variations, choices, extras, bundles, images, stock, delivery settings, tax behavior, and SEO values remain usable;
* categories, brands, filters, and storefront discovery paths work as expected;
* customer accounts, groups, addresses, B2B/trade context, quotes, and order links remain interpretable;
* historical orders preserve enough payment, delivery, tax, discount, fulfillment, note, and customer context;
* content pages, menus, metadata, and high-value URLs are included, rebuilt, or accepted as out of scope;
* app-owned, API-connected, webhook-triggered, channel-specific, or outside-system data has been addressed;
* the selected approach is enough or whether Add-ons or Custom Service review should be added before Full Migration.

Demo Migration samples should include the records most likely to reveal difficulty: complex products, B2B customers, quote or trade examples, unusual orders, high-value URLs, app-dependent records, and integration-sensitive identifiers.

### Signals That the Chosen Approach Is Too Light <a href="#signals-that-the-chosen-approach-is-too-light" id="signals-that-the-chosen-approach-is-too-light"></a>

A migration approach may be too light when source review or Demo Migration exposes business meaning that standard migration cannot preserve safely.

| Signal                                                 | Why it matters                                                                                               | Safer response                                                                        |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Product choices lose buying behavior                   | Variations, choices, extras, personalization, bundles, or stock behavior may need deeper mapping.            | Review Advanced Data Mapping, Advanced Data Configure, or Custom Service.             |
| B2B customers lose group behavior                      | Customer groups may control pricing, quotes, approval, tax, visibility, or checkout rules.                   | Separate customer data from B2B configuration and custom logic.                       |
| Historical orders are readable only at a shallow level | Payment, delivery, tax, discount, fulfillment, notes, or external context may be incomplete.                 | Expand order samples and define required order-history meaning.                       |
| App-owned records are missing                          | App data may not belong to ordinary product, customer, order, or content structures.                         | Classify the app as reconfigured, rebuilt, excluded, mapped, or Custom Service scope. |
| Outside-system identifiers are not preserved           | ERP, CRM, accounting, marketplace, POS, fulfillment, or inventory references may be operationally important. | Review mapping or Custom Service requirements before Full Migration.                  |
| SEO and content paths are incomplete                   | Important URLs, metadata, menus, pages, or landing paths may not be included in standard data scope.         | Prepare priority SEO/content samples and confirm accepted scope.                      |
| Source checkout fields do not fit target settings      | Custom checkout behavior may affect order processing, B2B rules, delivery, or payment.                       | Treat the field as configuration, migrated note, app data, or Custom Service scope.   |

### Choosing the Practical Path <a href="#choosing-the-practical-path" id="choosing-the-practical-path"></a>

The practical approach can be summarized this way:

* choose **Standard Service** when source data is standard, the target ShopWired structures can support it, and the merchant is ready to self-perform and validate the migration;
* choose **Managed Service** when the requirement fits standard capability but the merchant wants Next-Cart-led execution;
* use **Standard Add-ons** when filtering, field mapping, or supported value configuration is needed;
* move to **Custom Service** when the project requires custom product interpretation, app-owned data handling, custom B2B logic, outside-system ID preservation, Custom Platform handling, or tailored migration behavior.

The safest approach is the one that reflects the actual source-store structure and target ShopWired requirements, not the lightest available service label.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting the right migration approach for ShopWired requires a clear view of product complexity, B2B rules, checkout behavior, apps, integrations, content, SEO, and service responsibility. Standard Service can be enough for clean and predictable data. Managed Service can be safer when the merchant wants Next-Cart-led execution. Add-ons can support filtering, mapping, and supported data configuration. Custom Service should be considered when custom, app-owned, integration-owned, or unsupported data changes the migration scope.

Use Demo Migration to test the records that carry the most business meaning. If the sample shows that standard capability does not preserve product choices, B2B behavior, order context, SEO, apps, or integration data well enough, adjust the approach before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for every ShopWired migration?**

No. Standard Service may be enough for predictable source data, but complex product choices, custom B2B rules, app-owned data, outside-system identifiers, or custom checkout behavior may require Add-ons or Custom Service review.

**When should I choose Managed Service for ShopWired?**

Choose Managed Service when the migration appears to fit standard service capability but you want Next-Cart to perform the migration. Managed Service is about service execution responsibility, not custom transformation.

**Does Custom Service mean Next-Cart automatically performs the migration for me?**

No. Custom Service means customization or modification work is required. Migration management is included only when it is part of the final plan.

**Which Add-ons are most relevant to ShopWired migration planning?**

The Data Filter Add-on can help when only selected eligible records should migrate. Advanced Data Mapping can help with supported field mapping. Advanced Data Configure can help when migrated values need supported modification before reaching ShopWired.

**What should Demo Migration prove before choosing the final approach?**

Demo Migration should prove that complex products, B2B customers, varied orders, important content and URLs, app-dependent data, and integration-sensitive identifiers can be interpreted acceptably inside ShopWired. If those samples expose gaps, the approach should be adjusted before Full Migration.
