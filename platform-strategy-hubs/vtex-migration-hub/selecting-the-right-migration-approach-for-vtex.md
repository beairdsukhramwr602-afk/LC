# Selecting the Right Migration Approach for VTEX

The right VTEX migration approach depends on how much of the merchant’s commerce operation must be interpreted, transformed, configured, or validated beyond ordinary record movement. VTEX can support sophisticated catalog structures, storefront implementations, marketplace operations, B2B scenarios, Master Data, integrations, and external services. That strength also means migration planning must separate supported record transfer from target-side implementation and custom business logic.

A small VTEX migration can require careful service-path selection if source data depends on custom fields, external identifiers, marketplace relationships, or headless storefront assumptions. A large migration can still fit a lighter path when the data is supported, the target structure is clear, and the merchant can validate the result confidently. The decision should be made from evidence, not from platform reputation or record count alone.

### What Migration Approach Means for VTEX <a href="#what-migration-approach-means-for-vtex" id="what-migration-approach-means-for-vtex"></a>

A VTEX migration approach is a decision about scope, responsibility, support level, configuration, and validation burden. It should explain which records are expected to migrate, which behaviors must be configured in VTEX, which values require Add-ons, which requirements need Custom Service, and which launch tasks belong to the merchant’s implementation team.

The approach should separate four layers of work:

| Work layer                            | VTEX example                                                                                                                                   | Service-path implication                                                                 |
| ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Supported migrated records            | Products, SKUs, categories, brands, customers, orders, images, CMS Pages, Blog Posts, and supported related fields.                            | May fit Standard Service or Managed Service depending on execution and validation needs. |
| Supported migration adjustments       | Filtering, mapping, or configuration of supported records and fields.                                                                          | May require Add-ons.                                                                     |
| Custom or unsupported migration needs | Master Data entities, app-owned values, marketplace-specific context, external IDs, bespoke transformation, or Custom Platform interpretation. | Requires Custom Service review.                                                          |
| VTEX-side implementation              | Storefront, apps, integrations, live checkout, payments, logistics, search, promotions, seller setup, and operational configuration.           | Should be prepared and validated outside ordinary record migration.                      |

This separation protects the migration from two common mistakes: choosing too light an approach because the record types sound familiar, or choosing Custom Service for work that is actually supported migration adjustment or VTEX-side implementation.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be appropriate when the source data fits supported migration behavior, the VTEX target structure is predictable, and the merchant can manage setup, review, and approval responsibilities. It is strongest when products and SKUs are ordinary, categories and brands are clear, customer records are standard, order history needs readable reference value, and custom platform logic is limited.

Standard Service should not be judged by volume alone. A large supported catalog can be feasible if the product/SKU relationship is clean and the merchant can validate representative samples. A smaller store may be unsuitable if key records depend on custom source fields, Master Data, marketplace ownership, or external system interpretation.

| Standard Service readiness signal                                       | VTEX-specific reason                                                                  |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Products and SKUs have clear source structures.                         | VTEX catalog mapping can be reviewed without bespoke transformation.                  |
| Specifications, categories, and brands are stable and supported.        | Product discovery and merchandising values can be validated through ordinary samples. |
| Customers and orders are mostly standard records.                       | Historical context can remain useful without custom account reconstruction.           |
| Pricing and promotions do not require special transformation.           | Commercial setup can be handled through supported migration or VTEX configuration.    |
| Marketplace, B2B, and Master Data expectations are limited or excluded. | The migration is less likely to depend on unsupported or custom data.                 |
| The merchant can validate the result.                                   | Customer-led review remains practical.                                                |

Standard Service becomes risky when the merchant cannot describe what a passing VTEX sample should look like. If success criteria are unclear, the issue is not only execution; the scope itself needs refinement.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be safer when the migration remains within supported capability but the project needs stronger execution support, sequencing, and coordination. The data may not require custom transformation, yet the merchant may not have the bandwidth or experience to manage migration actions, sample review, issue coordination, and launch timing independently.

For VTEX, Managed Service is often relevant when catalog volume is large, product/SKU review is time-sensitive, multiple stakeholders must approve different layers, or launch planning involves both migration and VTEX implementation work. Managed Service can help coordinate the migration process, but it does not convert unsupported requirements into supported ones.

| Managed Service fit                                      | VTEX scenario                                                                                    |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Supported data with high review burden                   | Large catalog, many SKUs, many images, or broad historical order scope.                          |
| Multiple business owners must approve samples            | Catalog, pricing, operations, support, SEO, storefront, and integration teams all need review.   |
| Launch window is tight                                   | Migration activity must be coordinated with target setup and source-store changes.               |
| Merchant needs execution support                         | Next-Cart-led execution is useful while the merchant remains responsible for final verification. |
| Standard scope is clear but operational pressure is high | The project needs coordination, not bespoke migration logic.                                     |

Managed Service should be selected for execution and coordination. Custom Service should still be considered if the migration requires unsupported records, external identifiers, Master Data interpretation, bespoke transformation, or custom migration logic adjustment.

### When Add-ons Are the Right Tool <a href="#when-add-ons-are-the-right-tool" id="when-add-ons-are-the-right-tool"></a>

Add-ons help when the requirement is supported, bounded, and specific. They are useful for filtering records, mapping supported fields, or configuring supported migration output. They should not be used as a substitute for Custom Service when the underlying requirement is unsupported or custom.

A strong Add-on request is written as a concrete acceptance criterion. For example, the merchant may need to exclude obsolete products, map supported source fields to supported VTEX destinations, or adjust supported output behavior for reviewability. A weak Add-on request uses vague language such as “make the VTEX structure match our old custom workflow,” which may actually require Custom Service or target-side implementation.

| Add-on need             | VTEX example                                                                                                      | Boundary check                                                                                      |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Data filtering          | Exclude inactive products, old customers, unnecessary Blog Posts, or historical orders outside the agreed window. | Filtering should not remove records needed for reporting, service, or SEO continuity.               |
| Advanced Data Mapping   | Align supported source fields with supported VTEX product, SKU, customer, order, or content destinations.         | Mapping cannot create unsupported VTEX behavior.                                                    |
| Advanced Data Configure | Adjust supported data handling to improve reviewability or target usability.                                      | Configuration must remain within supported capability.                                              |
| Custom Add-ons          | Handle a bounded special requirement within agreed supported scope.                                               | Unsupported app data, Master Data entities, or external-system logic require Custom Service review. |

Add-ons are strongest when the source and target meaning is clear. They are weakest when the merchant is using them to avoid deciding whether a requirement is custom.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when VTEX migration success depends on data, behavior, or interpretation beyond supported standard capability. The trigger is not simply enterprise size. The trigger is the need for custom migration logic, bespoke transformation, unsupported records, Custom Platform handling, Master Data interpretation, external identifiers, app-owned values, marketplace-specific reconstruction, or integration-sensitive data handling.

Custom Service can be relevant even when the visible record count is small. A limited product set may require custom handling if each product depends on external PIM enrichment, nonstandard specifications, seller offers, custom pricing logic, or source-specific bundle behavior. A larger project may not need Custom Service if the records are supported and target-side implementation handles the operational behavior.

| Custom Service trigger                              | Why it changes the approach                                                                        |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Master Data entities must migrate                   | Custom entities may not behave like ordinary customer, product, or order fields.                   |
| External identifiers must remain usable             | ERP, PIM, WMS, OMS, CRM, marketplace, or accounting continuity may depend on precise preservation. |
| Marketplace or seller context must be reconstructed | Seller, offer, commission, fulfillment, or received-SKU meaning may require custom interpretation. |
| Product/SKU logic requires transformation           | Bundles, kits, assemblies, personalization, attachments, or service logic may not map cleanly.     |
| Storefront-sensitive data must be reshaped          | URLs, CMS content, search/facet behavior, routing, or metadata may need bespoke handling.          |
| Source platform is custom or heavily modified       | The source structure itself may require custom extraction and interpretation.                      |

Custom Service should be scoped from examples. The merchant should provide representative records, expected outcomes, and business reasons for preserving the custom value. Without examples, Custom Service planning can become abstract and difficult to validate.

### Demo Migration as the Service-Path Evidence Gate <a href="#demo-migration-as-the-service-path-evidence-gate" id="demo-migration-as-the-service-path-evidence-gate"></a>

Demo Migration should test whether the selected approach is sufficient before Full Migration. For VTEX, the sample set should challenge the data relationships most likely to affect launch: products and SKUs, specifications, prices, promotions, customers, orders, marketplace context, Master Data, integrations, and storefront-sensitive records.

| Demo Migration sample                  | What it should decide                                                                               |
| -------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Simple product and SKU                 | Whether baseline catalog migration works cleanly.                                                   |
| Multi-SKU product                      | Whether source variants become usable VTEX SKUs.                                                    |
| Specification-heavy product            | Whether discovery, search, filter, and merchandising values remain structured.                      |
| Commercial rule example                | Whether price, promotion, or channel context is migrated, configured, or excluded correctly.        |
| Customer with business context         | Whether customer and account meaning remains usable.                                                |
| Operational order                      | Whether historical order context remains readable for service and finance.                          |
| Master Data or integration-owned value | Whether the requirement is supported, excluded, or custom-scoped.                                   |
| Storefront-sensitive record            | Whether content, URLs, search, and SEO assumptions need separate implementation or custom handling. |

If Demo Migration shows that representative records preserve usable meaning, the selected approach may be appropriate. If it exposes repeated structural gaps, missing external references, marketplace ambiguity, custom field loss, or storefront-sensitive mismatch, the approach should be revised before Full Migration.

### Entity Points and VTEX Scope Planning <a href="#entity-points-and-vtex-scope-planning" id="entity-points-and-vtex-scope-planning"></a>

Entity Points should support scope planning without replacing complexity review. Product, Customer, Order, and Blog Posts records may consume Entity Points when they are migrated for the first time. New eligible records may also consume Entity Points when later migration activity brings them into scope for the first time.

Already recorded eligible entities do not consume Entity Points again simply because the merchant continues migration activity or performs another migration action on the same migration path. That rule is important for VTEX projects where launch windows may include new products, customers, orders, or Blog Posts after the first migration run.

Entity Points do not measure VTEX complexity by themselves. A migration with modest record volume may still require Custom Service if Master Data, external identifiers, seller context, or bespoke product/SKU transformation is required. A larger migration may fit Standard Service or Managed Service if the records are supported and reviewable.

### Later Migration Actions and Launch Timing <a href="#later-migration-actions-and-launch-timing" id="later-migration-actions-and-launch-timing"></a>

VTEX launch plans often need later migration activity because the source store remains active during review, implementation, or staging. New products, customers, orders, Blog Posts, price updates, catalog changes, or content changes may appear before launch. The service path should define how those later changes will be handled.

The team should decide whether later activity should continue with the last used configuration, continue with a new configuration, or require a new migration. Continuing with the same configuration usually focuses validation on new records plus regression samples. Continuing with a new configuration requires validation of affected fields, filters, mappings, and record types. A new migration requires broader target review if earlier migrated data is replaced or refreshed.

The important point is not the action label alone. The important point is whether the business expects an append-like outcome, a changed configuration outcome, or a refreshed target result. VTEX projects should decide that before launch pressure increases.

### Signals That the Chosen Approach Is Too Light <a href="#signals-that-the-chosen-approach-is-too-light" id="signals-that-the-chosen-approach-is-too-light"></a>

A VTEX migration approach is too light when it treats enterprise structure as ordinary record transfer. The warning signs often appear in sample review, not in the first scope estimate.

| Warning signal                                                           | Likely response                                                                                 |
| ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------- |
| Product/SKU relationships are unclear.                                   | Strengthen catalog scope or review Custom Service.                                              |
| Specifications required for search or filters are missing or flattened.  | Review supported mapping, Add-ons, or custom transformation.                                    |
| Pricing, promotions, or channel values do not preserve business meaning. | Separate migrated data from VTEX configuration and custom logic.                                |
| Marketplace or seller context is expected but not represented.           | Review marketplace scope, target setup, or Custom Service.                                      |
| Master Data or external IDs are business-critical.                       | Review Custom Service unless a supported mapping path is clearly available.                     |
| Storefront-sensitive data is approved only by product count.             | Add URL, content, search, navigation, and SEO validation.                                       |
| The merchant cannot name review owners.                                  | Managed Service may help execution, but scope and acceptance criteria still need to be defined. |

These signals should be resolved before Full Migration. Continuing with a weak approach usually turns preparation gaps into launch defects.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right VTEX migration approach is the lightest service path that can still protect the target operating outcome. Standard Service can fit supported, reviewable records. Managed Service is useful when execution and coordination burden are high. Add-ons support bounded filtering, mapping, and configuration within supported behavior. Custom Service is required when the requirement depends on custom data, unsupported records, external identifiers, Master Data, marketplace interpretation, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

Demo Migration should confirm whether the approach is strong enough before Full Migration. If representative samples show structural gaps, unclear ownership, external-system dependency, marketplace ambiguity, or storefront-sensitive loss, the service path should be revised before the full VTEX migration proceeds.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a VTEX migration?**

Standard Service may be enough when supported records are clean, products and SKUs are predictable, customer and order data are standard, and the merchant can validate the result responsibly. Marketplace, Master Data, external identifiers, or bespoke logic should be reviewed before assuming Standard Service is enough.

**When should Managed Service be chosen for VTEX?**

Managed Service is useful when the data remains within supported capability but the merchant needs Next-Cart-led execution, stronger coordination, sample-review discipline, or help managing migration timing around launch.

**How are Add-ons different from Custom Service for VTEX?**

Add-ons handle supported filtering, mapping, or configuration needs. Custom Service handles unsupported records, app-owned values, Master Data entities, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

**Do Entity Points determine VTEX migration complexity?**

No. Entity Points help plan eligible record volume, but VTEX complexity depends on catalog structure, marketplace context, Master Data, integrations, storefront assumptions, and validation burden.

**What should Demo Migration prove before the VTEX approach is approved?**

Demo Migration should prove that representative products, SKUs, specifications, prices, customers, orders, marketplace values, Master Data examples, integration references, and storefront-sensitive records land with usable meaning or are assigned to the right handling path.
