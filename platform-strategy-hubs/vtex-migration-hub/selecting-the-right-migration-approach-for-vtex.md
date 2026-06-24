# Selecting the Right Migration Approach for VTEX

Choosing the right migration approach for VTEX requires more than checking whether products, customers, and orders can be transferred. VTEX often combines Catalog, SKUs, specifications, pricing, trade policies, marketplace operations, OMS, logistics, Master Data, apps, APIs, and storefront implementation into one operating environment. The right approach should match how much of that operating model must be migrated, reviewed, configured, or customized before Full Migration.

A lighter approach can work when VTEX is receiving clean commerce data and the merchant can handle target-side setup and review. A heavier approach is safer when the project depends on enterprise commerce behavior, marketplace or seller relationships, external identifiers, custom checkout fields, app-owned data, or bespoke transformation logic. The decision should be based on structural evidence from preparation and Demo Migration results, not only record count.

### How to Classify the VTEX Migration Approach <a href="#how-to-classify-the-vtex-migration-approach" id="how-to-classify-the-vtex-migration-approach"></a>

VTEX approach selection works best when the project is classified by operational burden. A migration with many records can still be manageable if the structure is predictable. A smaller migration can require deeper service review if its records depend on complex SKU behavior, trade policies, marketplace relationships, or external systems.

| Decision layer            | What to assess                                                                                                                                              | Approach implication                                                                                           |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Data structure            | Products, SKUs, categories, brands, specifications, images, stock, customers, orders, CMS Pages, and Blog Posts                                             | Determines whether ordinary supported migration handling is likely enough.                                     |
| VTEX configuration burden | Trade policies, sales channels, pricing rules, promotions, logistics, payment, checkout, storefront, and app setup                                          | Usually remains target-side setup unless the data itself requires migration handling or custom interpretation. |
| Execution burden          | Record volume, launch timing, review capacity, team availability, and tolerance for customer-led execution                                                  | Helps separate Standard Service from Managed Service when the migration remains within standard capability.    |
| Transformation burden     | Product-to-SKU restructuring, specification remapping, marketplace/seller interpretation, external IDs, Master Data, custom fields, or unsupported app data | Pushes the project toward Add-ons or Custom Service depending on whether the need is supported or bespoke.     |
| Validation burden         | Demo Migration proof, stakeholder review, downstream system checks, and Full Migration acceptance criteria                                                  | Confirms whether the selected approach can produce a reliable VTEX outcome.                                    |

The practical question is: can the current store’s business meaning be represented in VTEX through supported migration behavior, standard configuration, optional Add-ons, Next-Cart-led execution, or does it require Custom Service?

### Standard Service for VTEX <a href="#standard-service-for-vtex" id="standard-service-for-vtex"></a>

Standard Service may be enough when the Source Platform data is supported, the VTEX target structure is predictable, and the customer can manage the migration steps and review the outcome. This is most realistic when the project is primarily about transferring supported commerce records into a VTEX environment that the customer or implementation team will configure separately.

| Standard Service signal                                          | What it means for VTEX                                                                                                                 | What still needs separate ownership                                                                                               |
| ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Product and SKU relationships are clean                          | Products, SKUs, images, prices, stock, brands, and categories can be reviewed without custom restructuring.                            | VTEX catalog activation, required specifications, storefront display, search behavior, and merchandising setup still need review. |
| Specifications are predictable                                   | Product and SKU specifications can be mapped without unusual inheritance, naming, or category-dependent interpretation.                | Missing or incomplete VTEX-required specification values must be corrected before launch.                                         |
| Customers and orders are conventional                            | Customer accounts, addresses, order totals, statuses, items, payments, shipping, taxes, and discounts remain readable after migration. | Operational teams still need to confirm how historical records should be used after launch.                                       |
| Marketplace or seller structures are not part of migration scope | The migration does not need to recreate seller relationships, marketplace order meaning, or seller-specific identifiers.               | Marketplace operations must be configured outside the standard migration if needed.                                               |
| Master Data and app-owned records are not required               | The project can launch without migrating custom VTEX Master Data documents, app records, or API-owned objects.                         | Any excluded custom data should be documented so stakeholders understand what will not appear in VTEX.                            |
| Storefront rebuild is separate from data migration               | Store Framework, FastStore, CMS, search, facets, content, and URL behavior are handled by the implementation team.                     | Storefront teams must still validate product, category, CMS Page, Blog Post, and SEO continuity.                                  |

Standard Service is a good fit when the migration path is supported and the customer has enough internal capacity to run Demo Migration, review results, make target-side configuration decisions, and approve Full Migration.

### Managed Service for VTEX <a href="#managed-service-for-vtex" id="managed-service-for-vtex"></a>

Managed Service is safer when the migration remains inside standard service capability but the customer wants Next-Cart-led execution. It helps when the project is operationally demanding, review-heavy, or time-sensitive, even if the data itself does not require bespoke migration logic.

| Managed Service signal                        | Why it matters for VTEX                                                                                                           | Boundary to keep clear                                                                   |
| --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Large catalog, SKU, customer, or order volume | More records increase execution and review coordination even when the structure is supported.                                     | Volume alone does not create Custom Service if the data model remains standard.          |
| Multiple business teams must review results   | Catalog, merchandising, operations, finance, fulfillment, marketplace, and storefront teams may each need different proof points. | Managed Service coordinates standard execution; it does not replace business acceptance. |
| Launch timing leaves limited room for retries | Next-Cart-led execution can reduce customer-side process errors and coordination delays.                                          | Timing pressure should not hide unresolved custom-data or integration needs.             |
| Demo Migration needs guided interpretation    | The customer may need help deciding whether sample results are acceptable before Full Migration.                                  | Structural gaps found in the sample may still require Add-ons or Custom Service.         |
| Standard Add-ons are included                 | Managed Service can include purchased Standard Add-ons when their default behavior fits the project.                              | Add-on behavior that needs tailoring belongs in Custom Service.                          |

Managed Service should be chosen for execution support within standard capability. It should not be used as a substitute for Custom Service when VTEX needs bespoke transformation, unsupported data handling, or custom migration logic.

### Add-ons for VTEX Migration Scope <a href="#add-ons-for-vtex-migration-scope" id="add-ons-for-vtex-migration-scope"></a>

Add-ons are useful when the VTEX migration needs supported filtering, mapping, or value configuration beyond a basic transfer, but the requirement still fits available Add-on behavior. They help narrow the gap between generic data movement and a cleaner VTEX-ready result.

| Add-on area             | VTEX use case                                                                                                                    | When it is appropriate                                             | When it is not enough                                                                          |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Migrate selected products, customers, orders, CMS Pages, Blog Posts, or other eligible records instead of every eligible record. | The selection rule is clear and fits supported filtering behavior. | The filter needs custom business logic, multi-system reconciliation, or manual interpretation. |
| Advanced Data Mapping   | Align supported source fields with VTEX product fields, SKU fields, specifications, customer fields, or order-related values.    | The source and target fields are known, supported, and reviewable. | The field needs transformation logic, external lookup, or custom source interpretation.        |
| Advanced Data Configure | Adjust supported values before they reach VTEX, such as selected names, statuses, categories, or field values.                   | The adjustment is within available configuration behavior.         | The adjustment changes business rules, creates new data structures, or depends on custom code. |
| Custom Add-ons          | Address a project-specific need that can be scoped separately from full Custom Service execution.                                | The requirement is specific, bounded, and accepted as custom work. | The broader migration depends on many custom relationships, systems, or logic paths.           |

Add-ons should not be presented as full VTEX implementation work. They can improve supported migration handling, but they do not configure trade policies, build storefronts, reconstruct marketplaces, replace ERP/PIM/WMS integrations, or guarantee that app-owned data can be migrated without custom review.

### Custom Service for VTEX <a href="#custom-service-for-vtex" id="custom-service-for-vtex"></a>

Custom Service is required when VTEX migration success depends on interpretation, transformation, unsupported data, Custom Platform source handling, or project-specific migration logic. VTEX often reaches this threshold when the store’s operating model is embedded in marketplace workflows, Master Data, external systems, apps, checkout customizations, or storefront-specific behavior.

| Custom Service trigger                                 | Why standard handling is not enough                                                                                               | Typical review focus                                                                                         |
| ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Custom Platform source                                 | The source structure must be interpreted before it can become VTEX-ready data.                                                    | Source extraction, field meaning, entity relationships, accepted exclusions, and transformation rules.       |
| Complex product-to-SKU transformation                  | Source variants, options, bundles, kits, services, attachments, or assembly logic do not map cleanly to ordinary VTEX structures. | Product/SKU grouping, specification strategy, activation requirements, image behavior, and business meaning. |
| Trade policy, price table, or promotion reconstruction | Selling logic affects which products, prices, customers, or channels are valid in different contexts.                             | Migration scope versus target-side configuration, required price data, and business acceptance criteria.     |
| Marketplace or seller architecture is central          | Seller relationships, marketplace order meaning, fulfillment responsibility, or channel identifiers must remain usable.           | Seller identifiers, order context, marketplace records, OMS interpretation, and downstream operations.       |
| Master Data or app-owned records are required          | Important data lives outside ordinary product, customer, and order entities.                                                      | Document schemas, API availability, mapping feasibility, data ownership, and accepted exclusions.            |
| External systems must keep usable identifiers          | ERP, PIM, WMS, OMS, finance, marketplace, or middleware references must survive migration.                                        | External IDs, reference fields, reconciliation rules, and post-migration integration testing.                |
| Storefront behavior depends on migrated data           | Search, facets, CMS Pages, Blog Posts, URLs, redirects, and metadata affect launch continuity.                                    | Content/data boundaries, redirect strategy, storefront ownership, and SEO-sensitive records.                 |

Custom Service does not automatically mean Next-Cart performs the full migration execution. A project may need only custom migration logic, or it may need custom work plus Next-Cart-led migration management if that is included in the final plan.

### Entity Points and VTEX Scope Planning <a href="#entity-points-and-vtex-scope-planning" id="entity-points-and-vtex-scope-planning"></a>

Entity Points help define service license scope, but they should not be treated as a substitute for VTEX complexity review. A VTEX migration with ordinary records can consume Entity Points predictably while still requiring careful review because of catalog, channel, marketplace, or integration meaning.

| Entity Points consideration                                                                                                                  | VTEX implication                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time.                                 | Scope planning should estimate eligible records before deciding whether the service license is sufficient.           |
| Records already counted through the service license do not consume Entity Points again simply because another migration action is performed. | Follow-up planning should not duplicate-count the same eligible records.                                             |
| New eligible records may consume Entity Points when migrated for the first time.                                                             | New products, customers, orders, or Blog Posts added after the first migration need scope review.                    |
| Entity Points do not measure complexity by themselves.                                                                                       | A small number of records can still require Custom Service if the VTEX structure is custom or integration-sensitive. |

The strongest approach uses Entity Points for scope planning and uses Demo Migration evidence for complexity planning.

### Demo Migration as the Approach Decision Point <a href="#demo-migration-as-the-approach-decision-point" id="demo-migration-as-the-approach-decision-point"></a>

Demo Migration should pressure-test the selected approach before Full Migration. A VTEX sample should include the records most likely to reveal whether the project fits Standard Service, Managed Service, Add-ons, or Custom Service.

| Demo Migration sample area   | Include examples that test                                                                                                       | What the result should prove                                                                       |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Catalog and SKUs             | Multi-SKU products, specification-heavy categories, images, brands, stock, attachments, services, kits, and collections          | Product structure remains usable and reviewable in VTEX.                                           |
| Pricing and channels         | Price variations, promotions, trade policy-sensitive products, customer-specific selling scenarios, or marketplace price context | Selling data is either migrated correctly or clearly assigned to target-side configuration.        |
| Customers and B2B context    | Customer accounts, addresses, segmentation, business-account identifiers, consent-related fields, and external references        | Customer meaning remains usable for account, marketing, and service teams.                         |
| Orders and operations        | Discounts, taxes, shipping, payment labels, statuses, fulfillment context, marketplace orders, and seller references             | Historical orders remain readable for service, finance, and operations.                            |
| Master Data and integrations | Custom fields, API-owned values, ERP/PIM/WMS/OMS identifiers, app fields, and middleware references                              | Required external references are preserved, mapped, excluded, or moved into Custom Service review. |
| Storefront-sensitive records | Categories, CMS Pages, Blog Posts, URLs, redirects, metadata, search/facet examples, and content relationships                   | Storefront and SEO teams can identify what migrated and what needs implementation work.            |

If the sample lands clearly and the remaining work is target-side configuration, Standard Service or Managed Service may be enough. If the sample exposes repeated structural gaps, unclear external references, missing custom fields, marketplace ambiguity, or storefront-sensitive data loss, the approach should be revised before Full Migration.

### How Additional Migration Options Affect VTEX Approach Planning <a href="#how-additional-migration-options-affect-vtex-approach-planning" id="how-additional-migration-options-affect-vtex-approach-planning"></a>

Additional Migration Options matter when the merchant needs follow-up migration activity after an initial migration stage. For VTEX, follow-up handling should be planned carefully because new records may interact with trade policies, marketplace operations, OMS flows, Master Data, integrations, and storefront launch readiness.

| Follow-up situation                                                                 | VTEX planning implication                                                                     | Service-path question                                                                  |
| ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| New products, customers, orders, or Blog Posts were added after the first migration | New eligible records may need migration and first-time Entity Points review.                  | Can the same approach handle the new records without changing scope?                   |
| Catalog structure changed                                                           | New SKUs, specifications, categories, kits, services, or attachments may need renewed review. | Does the change still fit Standard Service/Add-ons, or does it require Custom Service? |
| Pricing, trade policy, or marketplace context changed                               | Follow-up migration may affect data tied to selling channels or seller operations.            | Is the logic migrated data, target-side configuration, or custom interpretation?       |
| Master Data, apps, or integrations changed                                          | New external IDs or custom fields may affect downstream usability.                            | Is the additional data supported, excluded, or custom-scoped?                          |
| Storefront or SEO launch assumptions changed                                        | CMS Pages, Blog Posts, URLs, metadata, or redirects may need renewed validation.              | Does the migration approach still support launch continuity?                           |

Additional Migration Options should not be treated as a way to bypass approach selection. The same rule remains: if new or changed records introduce custom interpretation, unsupported data, or integration-sensitive behavior, the approach should be reviewed before the next migration activity.

### VTEX Approach Decision Matrix <a href="#vtex-approach-decision-matrix" id="vtex-approach-decision-matrix"></a>

| Project condition                                                          | Standard Service | Managed Service                      | Add-ons                                 | Custom Service                                               |
| -------------------------------------------------------------------------- | ---------------- | ------------------------------------ | --------------------------------------- | ------------------------------------------------------------ |
| Clean supported products, SKUs, customers, and orders                      | Strong fit       | Optional if execution help is needed | Optional only for supported adjustments | Usually unnecessary                                          |
| Large volume with predictable structure                                    | Possible         | Strong fit                           | Optional                                | Usually unnecessary                                          |
| Supported fields need filtering, mapping, or value configuration           | Possible         | Possible                             | Strong fit                              | Only if customization is needed                              |
| Product/SKU/specification restructuring is required                        | Weak fit         | Weak fit                             | Limited                                 | Strong fit                                                   |
| Marketplace, seller, or OMS meaning must be reconstructed                  | Weak fit         | Weak fit                             | Limited                                 | Strong fit                                                   |
| Master Data, apps, APIs, or external identifiers are required              | Weak fit         | Weak fit                             | Limited unless supported and bounded    | Strong fit                                                   |
| Storefront, CMS, search, URL, and SEO data need coordinated interpretation | Conditional      | Conditional                          | Possible for supported records          | Strong fit when transformation or custom ownership is needed |
| Customer wants Next-Cart-led execution but data remains supported          | Possible         | Strong fit                           | Optional                                | Only if custom work is required                              |

The decision matrix should be applied after source review and Demo Migration, not before. It helps prevent two common mistakes: choosing a too-light approach for enterprise VTEX complexity, or over-scoping Custom Service when the real need is execution support or supported Add-on handling.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right VTEX migration approach depends on how deeply the existing store depends on catalog structure, selling logic, marketplace operations, Master Data, integrations, and storefront behavior. Standard Service can work when supported data is clean and reviewable. Managed Service is safer when execution burden is high but the data remains within standard capability. Add-ons help with supported filtering, mapping, or configuration needs. Custom Service is required when VTEX success depends on bespoke transformation, unsupported records, Custom Platform interpretation, external-system references, or custom migration logic.

Demo Migration should confirm whether the selected approach can produce a usable VTEX outcome before Full Migration. If the sample exposes structural uncertainty, integration-sensitive data, marketplace ambiguity, or storefront-sensitive gaps, resolve the approach before moving forward.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a VTEX migration?**

Standard Service may be enough when the Source Platform data is supported, the VTEX target structure is predictable, and the customer can manage review and target-side setup. Complex SKU logic, trade policies, marketplace data, Master Data, integrations, or custom fields should be reviewed before assuming Standard Service is enough.

**When should Managed Service be chosen for VTEX?**

Managed Service is useful when the migration still fits standard service capability but the customer wants Next-Cart-led execution. It is especially helpful when catalog volume, order history, review coordination, or launch timing makes customer-led execution less practical.

**Do VTEX trade policies or marketplace structures require Custom Service?**

They require Custom Service when the migration must interpret, transform, or reconstruct selling logic, seller relationships, marketplace order context, or external identifiers beyond supported migration and Add-on behavior. If those elements are handled as target-side configuration only, they may not need migration customization.

**Can Add-ons handle VTEX-specific mapping needs?**

Add-ons can help when filtering, mapping, or value configuration fits available supported behavior. If the requirement needs tailored logic, external lookup, unsupported records, or a project-specific transformation path, Custom Service should be reviewed.

**What should Demo Migration prove before the final VTEX approach is chosen?**

Demo Migration should prove whether products, SKUs, specifications, prices, customers, orders, marketplace context, external references, storefront-sensitive data, and integration-relevant records land in VTEX with usable meaning. If the sample exposes repeated structural gaps, the approach should be revised before Full Migration.
