# Selecting the Right Migration Approach for PrestaShop

Choosing the right migration approach for PrestaShop is not mainly a question of store size. It is a question of interpretation burden. PrestaShop can support structured product combinations, product features, customization fields, category governance, customer groups, multistore capability, friendly URLs, and module-supported flexibility. Those strengths are useful when the merchant knows how the source store should be translated into PrestaShop. They become risky when product logic, customer segmentation, shop scope, module behavior, or custom data remains unclear.

The safest approach is the lightest service path that still protects the intended PrestaShop outcome. Standard Service may be enough when records are supported, the target structure is clear, and the merchant can validate confidently. Managed Service may be safer when the scope is supported but coordination and execution burden are high. Add-ons can help with bounded filtering, mapping, or configuration needs. Custom Service should be considered when requirements involve unsupported records, modules, custom fields, external identifiers, bespoke transformations, Custom Platform handling, or custom migration logic adjustment.

### What Migration Approach Means for PrestaShop <a href="#what-migration-approach-means-for-prestashop" id="what-migration-approach-means-for-prestashop"></a>

A PrestaShop migration approach defines how much execution support, mapping control, customization review, and validation discipline the project needs. It should not be chosen only from Product, Customer, Order, or Blog Posts volume. Volume matters for planning, but PrestaShop complexity often comes from how records behave after migration.

Products may need to become combinations, features, or customization fields. Categories may affect navigation, SEO metadata, friendly URLs, group access, and multistore root-category planning. Customer groups may carry pricing, access, or segmentation meaning. Modules and overrides may own business logic that ordinary records do not explain. A source store may also contain custom fields, external IDs, ERP references, CRM records, review data, loyalty data, subscription data, or other dependencies outside standard migration behavior.

| Approach decision                       | PrestaShop-specific question                                                                                                            |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Is Standard Service enough?             | Are the required records supported, structured clearly, and easy for the merchant to validate?                                          |
| Is Managed Service safer?               | Is the scope supported but coordination, timing, or customer-side execution capacity a concern?                                         |
| Are Add-ons enough?                     | Is the need bounded to supported filtering, mapping, or configuration?                                                                  |
| Is Custom Service needed?               | Does the requirement involve custom fields, unsupported module data, Custom Platform handling, external IDs, or bespoke transformation? |
| Does launch timing affect the approach? | Will new records, changed configuration, or a refreshed target result require Additional Migration Options?                             |

The selected approach should be grounded in representative source examples, not broad confidence. If no one can explain how the difficult products, categories, groups, shop scope, URLs, and module data should behave in PrestaShop, the approach is not ready.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service can be suitable when the PrestaShop target structure is already clear and the merchant can manage required review tasks responsibly. It is strongest when the source store uses ordinary commerce records, product choices map predictably, categories are clean, customer groups are limited or well documented, multistore is not required or already planned, and module/custom behavior is not central to the migration outcome.

Standard Service is not a low-quality option. It can be the right choice when the merchant’s internal team understands the source store and can validate the PrestaShop result through Demo Migration and Full Migration. The key is not whether the catalog is small; the key is whether the target meaning is clear.

| Standard Service readiness signal                    | Why it matters in PrestaShop                                      |
| ---------------------------------------------------- | ----------------------------------------------------------------- |
| Product combinations are already defined.            | Selectable choices can be reviewed without deep reinterpretation. |
| Features are clean and commercially useful.          | Product comparison data can be preserved without clutter.         |
| Customization fields are simple or not required.     | Personalization does not create heavy fulfillment risk.           |
| Category tree and URLs are manageable.               | Discovery and SEO review remains controlled.                      |
| Customer groups are limited and documented.          | Group meaning can be validated without bespoke logic.             |
| Multistore is absent or simple.                      | Shop assignment does not dominate the project.                    |
| Modules and custom fields are not business-critical. | Standard records can carry most of the migration value.           |

Standard Service becomes risky when the merchant expects it to resolve unclear source logic automatically. If combinations, features, groups, shop assignments, or custom data need interpretation rather than transfer, a stronger approach should be considered.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be the better fit when the PrestaShop migration is within supported capability but the project needs more coordinated execution. This often happens when the merchant wants Next-Cart-led migration handling, the internal team lacks time to manage steps directly, or the scope has enough structure that execution discipline reduces avoidable mistakes.

Managed Service is useful for supported PrestaShop migrations with many moving parts: combination-heavy catalogs, feature-rich product data, important categories and friendly URLs, customer groups, recent orders, image-heavy catalogs, or launch timing that requires careful sequencing. It helps when the merchant can provide business decisions and final validation, but should not carry every operational step alone.

Managed Service should not be confused with Custom Service. A project can be managed without being custom. If the requirement is supported but needs stronger coordination, Managed Service may fit. If the requirement itself needs custom transformation, unsupported data handling, or custom migration logic adjustment, Custom Service should be reviewed.

| Managed Service fit signal            | What Managed Service helps with                         | What it does not automatically solve                                                  |
| ------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Large supported catalog               | Migration execution coordination and review sequencing. | Unsupported product logic or custom module behavior.                                  |
| Important SEO paths                   | Better timing and sample review discipline.             | Full SEO strategy, redesign, or external redirect implementation beyond agreed scope. |
| Customer groups need careful checking | Coordinated migration and validation support.           | Rebuilding unsupported pricing or access logic.                                       |
| Internal team has limited bandwidth   | Reduces hands-on migration-operation burden.            | Merchant-side business decisions and final approval.                                  |

Managed Service is safest when the merchant can still define what success looks like. Execution support cannot replace business interpretation.

### When Add-ons Are the Right Layer <a href="#when-add-ons-are-the-right-layer" id="when-add-ons-are-the-right-layer"></a>

Add-ons fit PrestaShop migrations when the requirement is bounded, supported, and specific. They can help with filtering, mapping, or configuration needs, but they are not a substitute for Custom Service when the source behavior itself is unsupported or bespoke.

A Data Filter Add-on can be useful when the merchant wants to migrate only selected products, customers, orders, categories, CMS Pages, Blog Posts, or historical records. Advanced Data Mapping can help when supported source fields need more deliberate target alignment. Advanced Data Configure can help when supported output behavior needs configuration within agreed boundaries.

| Add-on type             | PrestaShop use case                                                                                                         | Boundary to protect                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Data Filter Add-on      | Exclude obsolete products, old orders, retired categories, inactive customers, or content that should not move.             | Filtering does not solve unclear catalog meaning.                             |
| Advanced Data Mapping   | Align supported fields with combinations, features, categories, customer groups, or other supported targets where feasible. | Mapping cannot create unsupported target behavior.                            |
| Advanced Data Configure | Adjust supported configuration choices that affect migration output.                                                        | Configuration is not custom development or module implementation.             |
| Custom Add-ons          | Handle a bounded special requirement within agreed scope.                                                                   | Broad custom data or bespoke transformation belongs to Custom Service review. |

The best way to choose an Add-on is to write the requirement as an acceptance rule. For example: “Exclude orders before a specific date” is bounded. “Rebuild all custom loyalty behavior from the old store” is not.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when the migration requirement exceeds supported standard behavior. PrestaShop’s open-source nature makes this boundary especially important. Many stores rely on modules, overrides, custom fields, custom database tables, ERP/CRM connectors, tax rules, shipping logic, payment behavior, loyalty systems, reviews, subscriptions, marketplace extensions, or internal reporting IDs. Some of that information may not belong to ordinary product, customer, order, category, or content records.

Custom Service is the right review path when the project requires tailored handling, not just extra care. The merchant should provide sample records, source evidence, target expectations, and business reasons for the custom requirement.

| Custom Service trigger            | Why it matters for PrestaShop                                                                  |
| --------------------------------- | ---------------------------------------------------------------------------------------------- |
| Custom fields or database columns | The value may need interpretation, merging, splitting, transformation, or target placement.    |
| Module-owned records              | Standard migration may not include data created or stored by modules.                          |
| Overrides or custom code          | Behavior may not be represented as ordinary records.                                           |
| External identifiers              | ERP, CRM, accounting, warehouse, loyalty, or reporting continuity may depend on preserved IDs. |
| Complex product logic             | Source options may not map cleanly into combinations, features, or customization fields.       |
| Multistore transformation         | Records may need deliberate assignment across shops, domains, languages, or pricing contexts.  |
| Custom Platform source            | The source structure itself may require analysis before PrestaShop mapping can be trusted.     |

Custom Service does not automatically mean full target-store setup, app implementation, theme redesign, or integration deployment. It means the migration requirement needs tailored review or non-standard handling within an agreed scope.

### How Entity Points Affect Planning <a href="#how-entity-points-affect-planning" id="how-entity-points-affect-planning"></a>

Entity Points help plan selected migration volume, but they do not measure PrestaShop complexity by themselves. Product, Customer, Order, and Blog Posts records may be relevant for Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

For PrestaShop, Entity Points should be considered alongside structure burden. A small store can require Custom Service if its product choices depend on custom fields or module behavior. A large store can fit Standard Service or Managed Service if the data is supported, the structure is clean, and validation is realistic.

| Planning signal   | What it tells the team                                    | What it does not prove                                                                               |
| ----------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Product volume    | Expected catalog scale and possible Entity Points impact. | Whether combinations, features, customizations, and categories are correct.                          |
| Customer volume   | Buyer-data scale.                                         | Whether customer groups, duplicates, tax status, or B2B-style treatment is usable.                   |
| Order volume      | Historical record volume.                                 | Whether refunds, discounts, order statuses, payment references, and custom fields remain meaningful. |
| Blog Posts volume | Content volume where included in scope.                   | Whether URLs, redirects, CMS Pages, and navigation are launch-ready.                                 |

Entity Points should support service planning, not replace migration approach selection.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should be treated as the evidence gate for the chosen PrestaShop approach. It should prove more than record presence. It should show whether the selected service path can preserve enough target meaning to proceed with confidence.

A strong Demo Migration review should include:

| Sample area                  | Decision it should support                                                                         |
| ---------------------------- | -------------------------------------------------------------------------------------------------- |
| Combination-heavy product    | Whether attributes and combinations are interpreted correctly.                                     |
| Feature-heavy product        | Whether comparison/specification data remains useful.                                              |
| Personalized product         | Whether customization fields and order detail behave as expected.                                  |
| Category with SEO value      | Whether metadata, friendly URL, visibility, and product assignment are acceptable.                 |
| Customer group example       | Whether pricing, access, communication, or segmentation meaning is preserved or scoped separately. |
| Multistore example           | Whether shop assignment, root category, domain, language, or price context is clear.               |
| Module/custom-field record   | Whether Add-ons, Custom Service, target setup, or exclusion is needed.                             |
| Refunded or discounted order | Whether historical order context remains readable.                                                 |

If Demo Migration exposes issues the team cannot classify, the approach is probably too light. The right response is to refine scope, service path, Add-ons, Custom Service requirements, or target-side setup before Full Migration.

### Additional Migration Options and Launch Timing <a href="#additional-migration-options-and-launch-timing" id="additional-migration-options-and-launch-timing"></a>

PrestaShop launch timing can require follow-up migration planning when the source store continues to change after an earlier run. New products, customers, orders, Blog Posts, categories, images, or content may appear before launch. Configuration may also need to change after Demo Migration shows mapping, filtering, or setup gaps.

Additional Migration Options should be discussed only when they solve a real launch-timing problem. The merchant may need to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration. These choices affect what should be revalidated.

| Later migration need                                  | Practical review focus                                                                      |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| New source records appear before launch               | Validate newly migrated records and regression samples.                                     |
| Configuration changes after Demo Migration            | Recheck affected fields, filters, mappings, or assignments.                                 |
| Target result should be refreshed                     | Validate the new migration result and confirm previous target data is replaced as intended. |
| New eligible entities are migrated for the first time | Review Entity Points usage for those new records.                                           |

This language should remain operational. There is no need to explain old feature names or backend mechanics in publication content.

### Signals That the Approach Is Too Light <a href="#signals-that-the-approach-is-too-light" id="signals-that-the-approach-is-too-light"></a>

A PrestaShop approach is too light when it assumes standard record transfer can solve unclear target meaning. Warning signs should be addressed before Full Migration.

| Warning signal                                                                                        | Likely response                                               |
| ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Products mix selectable choices, feature values, and personalization fields without a decision model. | Rework catalog scope before proceeding.                       |
| Customer groups affect price, visibility, or access but are described only as labels.                 | Strengthen preparation and service-path review.               |
| Multistore scope is unclear.                                                                          | Define shop structure or consider stronger handling.          |
| Modules, overrides, or custom fields own important data.                                              | Review Custom Service requirements.                           |
| URL priorities and category landing pages are not ranked.                                             | Add preparation and validation around SEO continuity.         |
| Demo Migration findings cannot be classified.                                                         | Pause before Full Migration and refine scope or service path. |

Choosing a stronger approach is not about making the project heavier than necessary. It is about matching the support path to the parts of PrestaShop that actually create business risk.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right PrestaShop migration approach is the one that matches the real interpretation burden. Standard Service may be enough when supported records are clear and the merchant can validate confidently. Managed Service may be safer when execution coordination matters. Add-ons can support bounded filtering, mapping, or configuration. Custom Service should be considered when custom data, modules, overrides, external identifiers, Custom Platform handling, or bespoke transformation affect the expected target result.

PrestaShop approach selection should be based on representative evidence: combination-heavy products, feature-rich product data, customer groups, multistore scope, URL priorities, module dependencies, custom fields, and historical order examples. The service path is ready when the merchant can explain what should migrate, what should be configured, what requires special handling, and what must be proven before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for a PrestaShop migration?**

Standard Service may be enough when the required records are supported, product combinations and features are clear, customer groups are documented, multistore scope is simple or absent, module/custom data is not business-critical, and the merchant can validate Demo Migration and Full Migration results confidently.

**When should Managed Service be considered for PrestaShop?**

Managed Service is useful when the migration remains within supported capability but the merchant wants stronger execution support, coordination, and review sequencing. It does not replace Custom Service when the requirement itself needs custom handling.

**How are Add-ons different from Custom Service in a PrestaShop migration?**

Add-ons support bounded filtering, mapping, or configuration within supported behavior. Custom Service is for tailored review or non-standard handling, such as custom fields, module-owned data, overrides, external identifiers, Custom Platform sources, or custom migration logic adjustment.

**Do Entity Points decide the right PrestaShop migration approach?**

No. Entity Points help plan migration volume for eligible records, but they do not measure catalog structure, customer group complexity, multistore scope, module dependency, custom data, or validation burden.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that representative PrestaShop records behave as expected: combinations, features, customization fields, categories, URLs, customer groups, multistore examples, module/custom-field records, and important order samples.

**When are Additional Migration Options relevant?**

They are relevant when launch timing requires follow-up handling, such as adding newly created source records, changing configuration after Demo Migration, or performing a new migration to refresh the target result. The team should define what changes and what must be revalidated.
