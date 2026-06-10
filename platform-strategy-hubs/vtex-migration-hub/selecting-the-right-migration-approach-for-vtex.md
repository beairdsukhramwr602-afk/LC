# Selecting the Right Migration Approach for VTEX

Choosing the right migration approach for VTEX depends on how much of the existing store can move into standard VTEX structures and how much depends on enterprise commerce logic, custom integrations, storefront architecture, or external systems.

VTEX is usually selected for more than basic product, customer, and order storage. A VTEX project may involve SKU-level catalog structure, product specifications, price tables, trade policies, promotions, B2B rules, marketplace or seller relationships, Checkout behavior, OMS flows, Master Data, VTEX IO apps, APIs, ERP connections, PIM data, WMS workflows, and storefront decisions. The migration approach should match that operating burden before Full Migration is treated as straightforward.

### The Practical Approach Question <a href="#the-practical-approach-question" id="the-practical-approach-question"></a>

The central question is not only whether the Source Platform is supported. The stronger question is whether the current store’s business meaning can be represented inside VTEX with standard migration handling, optional Add-ons, Next-Cart-led execution, or a Custom Service review.

A lower-complexity VTEX migration usually has clear product and SKU structures, predictable customer and order records, limited custom fields, simple historical order expectations, and no required transfer of app-owned or external-system behavior. A higher-complexity VTEX migration often depends on specialized catalog logic, multiple trade policies, marketplace or seller relationships, B2B structures, ERP or PIM identifiers, custom checkout behavior, or storefront-specific transformation.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the migration path uses supported Source Platform data and the expected VTEX outcome stays within standard service capability. This is most realistic when the store owner can review Demo Migration results, understand what is included, and manage target-side configuration separately.

| Standard Service signal                              | What it means for VTEX                                                                                                                                    |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products and SKUs follow a clean structure           | Product, SKU, image, category, brand, price, and stock data can be reviewed without heavy custom transformation.                                          |
| Specifications are predictable                       | Product and SKU specifications can be mapped into VTEX without unusual logic or source-specific interpretation.                                           |
| Customer and order records are conventional          | Historical customer and order records remain readable without requiring custom customer models, complex B2B hierarchy, or external-system reconstruction. |
| Checkout setup is handled separately                 | Payment, shipping, logistics, tax, and Checkout configuration are planned as target setup work rather than assumed to migrate automatically.              |
| Marketplace and seller data are not central to scope | The project does not require marketplace relationship reconstruction, seller-specific data, or channel-specific operational logic.                        |
| Apps and integrations are limited                    | No app-owned, API-owned, ERP-owned, PIM-owned, WMS-owned, or Master Data-specific records are required as part of standard migration scope.               |

Standard Service can work well when the merchant has internal resources to manage the target VTEX environment, review results, configure storefront and checkout settings, and decide whether any gaps are acceptable before Full Migration.

### When Managed Service Is the Safer Approach <a href="#when-managed-service-is-the-safer-approach" id="when-managed-service-is-the-safer-approach"></a>

Managed Service is usually safer when the migration still fits standard service capability but the merchant wants Next-Cart-led execution. This can reduce operational burden when the project has many records, several review points, or limited internal time for running and checking the migration process.

Managed Service does not turn unsupported customization into standard capability. It is best for VTEX migrations where the data structure is supported, but the merchant needs help executing the migration, coordinating standard settings, reviewing Demo Migration results, and moving toward Full Migration with less hands-on effort.

| Managed Service signal                              | Why it matters for VTEX                                                                                                |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Large catalog or order history                      | More records increase the coordination burden even when data structures are standard.                                  |
| SKU and specification review needs careful checking | The merchant wants assistance running and reviewing a migration that includes meaningful catalog complexity.           |
| Multiple internal reviewers are involved            | Catalog, operations, marketing, finance, and fulfillment teams may each need to confirm different parts of the result. |
| Timing pressure is high                             | A Next-Cart-led process may be safer when launch timing leaves little room for repeated customer-led execution errors. |
| Standard Add-ons are included                       | Managed Service can include purchased Standard Add-ons when their default behavior fits the project.                   |

Managed Service is about execution responsibility within standard service capability. It should not be chosen as a substitute for Custom Service when the project requires bespoke transformation, unsupported app data, external-system reconstruction, or custom migration logic adjustment.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. In VTEX migrations, Add-ons are most relevant when the project needs selected data movement, clearer field alignment, or supported data changes before records reach the Target Platform.

| Add-on area             | VTEX use case                                                                                                                                                                      |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Use when only selected products, customers, orders, Blog Posts, or other eligible records should migrate instead of all eligible records in a data type.                           |
| Advanced Data Mapping   | Use when supported source fields need more deliberate alignment with VTEX structures such as product fields, SKU fields, specifications, customer fields, or order-related values. |
| Advanced Data Configure | Use when supported migrated values should be adjusted before they reach VTEX, such as selected naming, status, category, or field-value changes within available capability.       |

Add-ons should not be treated as a full customization path. If an Add-on must be modified beyond its available settings and supported behavior, that requirement is handled through Custom Service because customization is required.

### When Custom Service Is Needed <a href="#when-custom-service-is-needed" id="when-custom-service-is-needed"></a>

Custom Service is the right path when the migration requires customization, modification, bespoke handling, Custom Platform source interpretation, unsupported app data, external-system identifiers, or custom migration logic adjustment.

VTEX migrations move into Custom Service when the project depends on logic that cannot be handled as ordinary supported data or Standard Add-on behavior. This is common in enterprise commerce environments where catalog, pricing, order, customer, marketplace, app, and integration structures carry business meaning outside the standard data layer.

| Custom Service signal                                         | Why it moves beyond standard handling                                                                                                         |
| ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Custom Platform source                                        | The source structure must be interpreted before it can become VTEX-ready data.                                                                |
| Complex product-to-SKU transformation                         | Source products, variants, options, specifications, kits, bundles, attachments, services, or assemblies need bespoke restructuring.           |
| Trade policy or price-table reconstruction                    | Pricing and selling logic depends on rules that must be interpreted, mapped, or rebuilt beyond ordinary record movement.                      |
| Marketplace or seller architecture is central                 | Seller relationships, marketplace order meaning, fulfillment responsibility, channel identifiers, or multi-seller data require custom review. |
| B2B structure is non-standard                                 | Organizations, roles, approval flows, contracts, customer segmentation, or price visibility require bespoke interpretation.                   |
| Master Data or app-owned data is required                     | Data outside ordinary commerce entities needs custom mapping, API work, or accepted exclusion planning.                                       |
| ERP, PIM, WMS, OMS, or finance identifiers must remain usable | External references need preservation, mapping, or transformation beyond standard migration behavior.                                         |
| Storefront transformation is tied to data meaning             | Store Framework, FastStore, Legacy CMS Portal, search behavior, CMS content, URL rules, or SEO structures require coordinated planning.       |

Custom Service does not automatically mean Next-Cart performs the full migration execution. Migration management is included only when it is part of the final plan. A customer may need customization work only, or customization work plus Next-Cart-led migration management.

### How Demo Migration Should Guide the Decision <a href="#how-demo-migration-should-guide-the-decision" id="how-demo-migration-should-guide-the-decision"></a>

Demo Migration is especially important for VTEX because small samples can reveal whether the selected approach is realistic. The sample should not include only simple products or clean orders. It should include the records most likely to expose catalog, pricing, marketplace, order, customer, integration, and storefront complexity.

Strong VTEX Demo Migration samples usually include:

* products with multiple SKUs, specifications, images, categories, brands, and stock-sensitive behavior;
* examples involving attachments, services, kits, bundles, or unusual product relationships when used;
* different price, promotion, customer, or trade-policy scenarios where they affect selling;
* customers with B2B, segmentation, address, or external-reference importance;
* orders with discounts, taxes, shipping, payment labels, statuses, fulfillment details, and marketplace or seller context;
* records that depend on Master Data, VTEX IO apps, APIs, ERP, PIM, WMS, OMS, finance, or other connected systems;
* important storefront, search, CMS, URL, and SEO examples.

If Demo Migration confirms that the data lands in VTEX with clear meaning and only minor configuration remains, Standard Service or Managed Service may be enough. If the result exposes repeated structural gaps, missing relationships, unclear external IDs, custom fields, marketplace complexity, or integration-sensitive behavior, the project should move into Add-on or Custom Service review before Full Migration.

### Avoiding a Too-Light Approach <a href="#avoiding-a-too-light-approach" id="avoiding-a-too-light-approach"></a>

A VTEX migration approach is too light when it treats the project as a simple transfer of products, customers, and orders while ignoring the structures that make VTEX operate as an enterprise commerce platform.

Common warning signs include:

* product samples omit complex SKUs, specifications, attachments, kits, bundles, or service-related records;
* pricing review ignores price tables, trade policies, promotions, customer groups, or B2B conditions;
* order review checks totals only, without payment, shipping, marketplace, seller, tax, status, or fulfillment context;
* Master Data, apps, APIs, ERP, PIM, WMS, OMS, and finance references are treated as outside the migration discussion even though teams need them after launch;
* storefront planning ignores Store Framework, FastStore, Legacy CMS Portal, search, CMS Pages, Blog Posts, URLs, redirects, and metadata;
* the team assumes Managed Service can solve custom transformation needs that actually belong in Custom Service.

A realistic approach should separate standard migration work, target-side configuration, Add-ons, Custom Service needs, and post-migration validation before launch planning depends on the result.

### Choosing the Right Path <a href="#choosing-the-right-path" id="choosing-the-right-path"></a>

| Migration condition                                                                                                                                                | Recommended direction                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| Supported Source Platform data, clean catalog, conventional customers and orders, no custom integration requirements                                               | Standard Service may be enough if the customer can self-perform and review the migration process.      |
| Supported data but large volume, limited internal time, or preference for Next-Cart-led execution                                                                  | Managed Service may be safer within standard service capability.                                       |
| Need to include selected records only, improve supported mapping, or adjust supported values                                                                       | Review Standard Add-ons such as Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure. |
| Add-on behavior needs modification beyond available settings                                                                                                       | The requirement is handled through Custom Service because customization is required.                   |
| Custom Platform source, custom data logic, unsupported app data, Master Data complexity, marketplace/seller reconstruction, or external-system identifier handling | Custom Service review is required.                                                                     |
| Custom work plus Next-Cart-led execution is needed                                                                                                                 | Custom Service with migration management should be discussed as part of the final plan.                |

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right VTEX migration approach depends on how deeply the existing store depends on enterprise commerce structures. A straightforward catalog and order history may fit Standard Service or Managed Service, while advanced SKU logic, trade policies, marketplace relationships, Master Data, apps, APIs, integrations, storefront architecture, or custom fields can change the project into an Add-on or Custom Service case.

Before choosing the final approach, use Demo Migration results to compare the expected VTEX outcome against real business records. If the sample exposes structural uncertainty, integration-sensitive fields, marketplace complexity, or custom transformation needs, resolve the service path before Full Migration rather than treating those issues as launch-time cleanup.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for a VTEX migration?**

Standard Service may be enough when the Source Platform data is supported, the VTEX target structure is predictable, and the merchant can self-perform and review the migration process. Complex SKU logic, trade policies, marketplace data, Master Data, apps, integrations, or custom fields should be reviewed before assuming Standard Service is enough.

**When should Managed Service be chosen for VTEX?**

Managed Service is useful when the migration still fits standard service capability but the merchant wants Next-Cart-led execution. It can help when catalog volume, order history, review coordination, or launch timing makes customer-led execution less practical.

**Do VTEX trade policies or price tables require Custom Service?**

They require Custom Service when the project needs custom interpretation, transformation, or reconstruction beyond supported migration behavior and Standard Add-on capability. Simple migrated price values may be easier, but complex selling logic should be reviewed early.

**Can Add-ons handle VTEX-specific mapping needs?**

Add-ons can help when filtering, mapping, or value configuration fits available supported behavior. If a Standard Add-on must be tailored or a project-specific Add-on is needed, that customization is handled through Custom Service.

**What should Demo Migration prove before choosing the final VTEX approach?**

Demo Migration should show whether products, SKUs, specifications, prices, customers, orders, marketplace context, external references, storefront-sensitive data, and integration-relevant records land in VTEX with usable meaning. If the sample exposes repeated structural gaps, the approach should be reviewed before Full Migration.
