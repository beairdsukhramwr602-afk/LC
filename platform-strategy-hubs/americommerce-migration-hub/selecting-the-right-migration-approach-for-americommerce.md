# Selecting the Right Migration Approach for AmeriCommerce

Choosing an AmeriCommerce migration approach is a scoping decision, not just a service preference. The right path depends on how much of the source store is ordinary commerce data and how much depends on buyer rules, storefront boundaries, pricing behavior, custom fields, integrations, or legacy operational workflows.

A lighter approach can work when the store has clean records and predictable relationships. A heavier approach becomes safer when AmeriCommerce must preserve account logic, complex catalog behavior, historical order context, or external-system identifiers that cannot be understood from standard entity lists alone.

### Start with the Platform Migration Scope <a href="#start-with-the-platform-migration-scope" id="start-with-the-platform-migration-scope"></a>

The first step is to define what the AmeriCommerce migration must actually accomplish. A migration that only needs Products, Customers, Orders, Coupons, and CMS pages may be straightforward if the source records are clean and business rules are simple. The same entity list can become more complex when the records depend on customer groups, company accounts, segmented catalogs, pricing tiers, custom attributes, or external systems.

Scope should be evaluated by business behavior. Count the records, but also review what the records control. A customer record may control price eligibility. A product record may control restricted availability. An order record may be needed for customer service, finance, warranty, or account history. A CMS page may carry SEO value or support buyer onboarding.

| Scope question                          | Standard meaning                                                                 | AmeriCommerce planning implication                                 |
| --------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Which entities are included?            | Products, Customers, Orders, Reviews, Coupons, CMS, and related records          | Entity selection determines the baseline service scope.            |
| Which relationships must remain usable? | Product options, buyer groups, pricing rules, content routes, order references   | Relationship complexity may require deeper handling.               |
| Which data should be rebuilt?           | Rules, pages, integrations, custom fields, or obsolete records                   | Rebuild decisions prevent unnecessary migration burden.            |
| Which records are business-critical?    | High-value products, active accounts, recent orders, traffic pages, external IDs | Critical samples should guide Demo Migration review.               |
| Which systems still own behavior?       | ERP, CRM, fulfillment, accounting, tax, shipping, marketplaces                   | External ownership may move the project beyond ordinary migration. |

A good approach decision separates baseline migration from business-critical exceptions. Without that separation, the migration may be scoped either too lightly or too broadly.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the AmeriCommerce target can receive a predictable set of records without heavy interpretation. This is most likely when the source store has clean product data, ordinary customer records, standard order history, limited custom fields, and no major dependency on complex buyer-specific rules.

The key is not whether the merchant is small. A larger store with a clean catalog and straightforward buyer model may fit Standard Service better than a smaller store with complicated account pricing, microstore structures, or custom source logic.

| Standard Service fit signal                     | Why it supports a lighter approach                                                 |
| ----------------------------------------------- | ---------------------------------------------------------------------------------- |
| Products use simple SKU and category structures | Product mapping is less likely to need custom interpretation.                      |
| Product options are limited and easy to sample  | Option behavior can be validated without extensive reconstruction.                 |
| Customers are mostly direct retail buyers       | Customer migration does not need deep company-account or buyer-rule mapping.       |
| Order history is used mainly for reference      | Historical orders need to remain searchable but not recreate complex workflows.    |
| Coupons and CMS pages are limited               | Promotional and content migration can remain within ordinary scope.                |
| Integrations do not own critical IDs            | Migration does not depend heavily on ERP, CRM, accounting, or fulfillment mapping. |

Standard Service still requires review. It should not be chosen simply because the store has a familiar entity list. The decision is safer when Demo Migration samples prove that ordinary records migrate with their expected meaning.

### When Managed Service Is a Better Fit <a href="#when-managed-service-is-a-better-fit" id="when-managed-service-is-a-better-fit"></a>

Managed Service is a better fit when the merchant needs more guidance, coordination, or review support even if the migration does not require heavy custom development. AmeriCommerce projects often benefit from managed handling when stakeholders need help organizing scope, reviewing Demo Migration results, coordinating corrections, or making tradeoffs between migration and rebuild decisions.

Managed Service is especially useful when the source store is operationally active and multiple teams rely on the data. Catalog, sales, operations, finance, marketing, and support teams may each define success differently. A managed approach helps keep validation focused and reduces the risk that important records are missed because they belong to another department.

| Managed Service fit signal                          | Why it may be safer                                                               |
| --------------------------------------------------- | --------------------------------------------------------------------------------- |
| Multiple stakeholders must review the migration     | Coordination matters across catalog, marketing, operations, finance, and support. |
| Data quality is mixed but not deeply custom         | Guidance can help classify cleanup, mapping, exclusion, and rebuild decisions.    |
| Demo Migration findings need interpretation         | The team needs help separating acceptable differences from correction issues.     |
| Buyer groups or pricing rules need careful sampling | Validation must confirm business behavior, not only record presence.              |
| Content and URL planning affects SEO                | Redirect and content priorities need organized review.                            |
| Migration timing is operationally sensitive         | Cutover planning and review discipline reduce disruption.                         |

Managed Service should be considered when the merchant needs structured execution support rather than only a technical transfer. It does not replace Custom Service when source data requires special handling, but it can make ordinary and moderately complex migrations safer.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons should be considered when a specific additional migration outcome is needed beyond the baseline scope. They are not a substitute for Custom Service, and they should not be used to hide custom logic. Add-ons are most useful when the requirement is defined, repeatable, and directly connected to a known migration need.

For AmeriCommerce planning, Add-ons may be relevant when the merchant needs additional handling for URLs, recent data, images, additional entities, or other supported options that improve continuity after migration. The decision should be based on the value of the outcome, not on the desire to move everything possible.

| Add-on planning area       | When it may be useful                                                        | Review before selecting                                                   |
| -------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| URL or SEO continuity      | Important product, category, or CMS routes should be preserved or redirected | Confirm which URLs matter and whether old routes still have value.        |
| Additional entity handling | The merchant needs supported data beyond the basic selected scope            | Confirm that the entity is useful in AmeriCommerce after migration.       |
| Image or media handling    | Product or content media must remain connected to records                    | Confirm file availability, source paths, and target display expectations. |
| Recent data handling       | Orders, customers, or other activity may change near launch                  | Confirm timing, record volatility, and validation responsibilities.       |
| Data preservation options  | Historical records need stronger continuity for operations or reporting      | Confirm whether migrated history will be used after launch.               |

Add-ons should clarify the migration plan. If an Add-on requirement cannot be described clearly, the need may be a custom mapping issue rather than an Add-on decision.

### When Custom Service Is Needed <a href="#when-custom-service-is-needed" id="when-custom-service-is-needed"></a>

Custom Service is needed when AmeriCommerce migration requirements cannot be handled through standard mapping, Managed Service coordination, or supported Add-ons. The clearest trigger is business-critical data that exists in custom structures, undocumented logic, nonstandard exports, custom tables, external systems, or source workflows that need interpretation before they can be represented in the target store.

Custom Service should be considered early when the source store uses account-specific pricing, multi-store boundaries, custom buyer rules, unusual product relationships, external IDs, quote or invoice workflows, custom checkout logic, or integration-owned fields that must remain usable after launch.

| Custom Service trigger                       | Why standard handling may not be enough                                  | Evidence needed                                           |
| -------------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------- |
| Custom source fields control buyer behavior  | Field names alone do not explain access, pricing, or checkout meaning    | Field definitions, examples, and stakeholder explanation. |
| Product relationships are nonstandard        | Kits, bundles, assemblies, or custom product forms may not map directly  | Product examples and expected target behavior.            |
| Account pricing is highly specific           | Pricing may depend on customer, contract, quantity, or external logic    | Pricing examples and rule ownership.                      |
| External systems own important identifiers   | ERP, CRM, fulfillment, or accounting IDs may need preserved context      | Integration documentation and sample records.             |
| Multi-store or portal structures are complex | Products, customers, content, or orders may belong to different contexts | Storefront map and representative samples.                |
| Historical orders support operations         | Orders may need more context than basic transaction fields               | Order examples and post-launch use cases.                 |

Custom Service should be scoped around business outcomes. The goal is not to reproduce every old technical detail, but to preserve the data relationships that the AmeriCommerce store needs to operate correctly.

### How Entity Points Affect Planning <a href="#how-entity-points-affect-planning" id="how-entity-points-affect-planning"></a>

Entity Points affect planning because they define how selected data volume contributes to migration scope. The planning mistake is to view Entity Points as a simple count of rows without considering duplicates, repeated records, and selected entities. AmeriCommerce migrations can involve many related records, especially when products, customers, orders, coupons, CMS pages, reviews, addresses, and other records are included.

Duplicate consumption matters. If duplicate records exist in the selected migration scope and are processed as part of the migration, they may still consume Entity Points even if the merchant later considers them unnecessary. Preparation should therefore include cleanup decisions before finalizing the scope.

| Entity Points planning issue | Why it matters                                                             | Practical action                                               |
| ---------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Duplicate products           | Duplicate records can increase selected volume and review effort           | Remove true duplicates before final scope confirmation.        |
| Old customer records         | Inactive or invalid customer records may add volume without business value | Decide whether to migrate, archive, or exclude.                |
| Historical orders            | Full history may be valuable but can increase scope substantially          | Choose the history range based on service and reporting needs. |
| CMS and content pages        | Old pages may increase scope and redirect burden                           | Preserve high-value pages and exclude obsolete content.        |
| Unsupported custom data      | Custom data may not fit ordinary entity selection                          | Separate standard entities from Custom Service needs.          |

Entity Points planning should happen before Full Migration, not after the merchant discovers that obsolete or duplicate records have expanded the migration scope.

### How Additional Migration Options Affect the Approach <a href="#how-additional-migration-options-affect-the-approach" id="how-additional-migration-options-affect-the-approach"></a>

Additional Migration Options should be evaluated only when they support the chosen AmeriCommerce approach. They should not be selected automatically. Some options are valuable because they reduce launch disruption or preserve operational continuity. Others may add complexity without improving the target store.

For AmeriCommerce, additional options are most useful when they support clear business goals: preserving search value, maintaining recent activity, handling media, keeping important historical references, or improving the accuracy of selected entities. Each option should be tied to a specific outcome that the merchant can validate.

| Option decision                | Useful when                                                                                       | Avoid when                                                        |
| ------------------------------ | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Preserve or redirect URLs      | Existing product, category, or CMS routes have SEO, backlink, campaign, or customer-service value | Routes are obsolete, duplicated, or intentionally being retired.  |
| Include recent activity        | Orders or customer records may change close to launch                                             | The source store can be frozen safely before migration.           |
| Preserve historical order data | Support, warranty, finance, or account teams rely on old order records                            | Historical records are rarely used and can be archived elsewhere. |
| Include media-heavy records    | Product images, downloads, files, or page media are needed in the target store                    | Media is outdated, duplicated, or planned for redesign.           |
| Add supported entities         | The entity will be used in AmeriCommerce after launch                                             | The entity exists only as legacy clutter.                         |

The right additional options make validation clearer. If an option creates more review work without a clear post-launch benefit, it should be questioned before migration begins.

### Choosing the Right Path Before Full Migration <a href="#choosing-the-right-path-before-full-migration" id="choosing-the-right-path-before-full-migration"></a>

The final approach decision should be made before Full Migration based on evidence from scope review, preparation work, and Demo Migration samples. The merchant should know which parts of the project fit standard handling, which parts need managed coordination, which outcomes require Add-ons, and which requirements need Custom Service.

A practical decision framework is to classify each major concern by the level of handling required. This avoids treating the whole migration as either simple or custom when the real answer may be mixed.

| Migration concern                  | Standard Service                       | Managed Service                           | Add-ons                      | Custom Service                                   |
| ---------------------------------- | -------------------------------------- | ----------------------------------------- | ---------------------------- | ------------------------------------------------ |
| Clean product and customer records | Usually suitable                       | Useful if review coordination is needed   | Not usually required         | Not usually required                             |
| Mixed data quality                 | Possible after cleanup                 | Often useful                              | Depends on affected outcomes | Needed if custom meaning is business-critical    |
| Buyer groups and pricing rules     | Possible if simple                     | Useful for sample review                  | May support related needs    | Needed if rules require special mapping          |
| URL and content continuity         | Possible for basic content             | Useful for SEO review coordination        | Often relevant               | Needed if content structure is custom or complex |
| External identifiers               | Possible if fields are straightforward | Useful for stakeholder review             | Not usually enough alone     | Needed if identifiers drive workflows            |
| Custom source logic                | Usually not enough                     | Helps coordination but not transformation | Not enough                   | Usually required                                 |

Before Full Migration, the chosen path should have a clear validation plan. The team should know which samples must pass, which exceptions are acceptable, and which issues would require a scope change before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right AmeriCommerce migration approach depends on how much business meaning sits behind the selected records. Standard Service can work for clean and predictable data. Managed Service can help when coordination and review discipline matter. Add-ons can support specific additional outcomes. Custom Service is needed when business-critical records depend on custom structures, external systems, or nonstandard logic.

A strong approach decision separates ordinary migration scope from exceptions that need extra handling. That separation helps protect the target store from avoidable rework, unclear validation, and post-launch data surprises.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for an AmeriCommerce migration?**

Standard Service may be enough when Products, Customers, Orders, Coupons, and CMS records are clean, predictable, and not heavily dependent on custom rules, account-specific pricing, or external systems.

**When should Managed Service be selected?**

Managed Service is useful when the migration needs structured coordination, stakeholder review, Demo Migration interpretation, timing support, or organized decision-making across catalog, operations, marketing, finance, and support teams.

**When does AmeriCommerce migration need Custom Service?**

Custom Service should be considered when business-critical data depends on custom fields, custom tables, nonstandard product relationships, external-system identifiers, account-specific pricing, or source workflows that standard mapping cannot represent safely.

**How do Entity Points affect the selected approach?**

Entity Points affect scope by measuring selected migration volume. Duplicate records, unnecessary history, obsolete CMS pages, and inactive customers should be reviewed before finalizing scope because they can increase migration effort without improving the target store.

**Should Add-ons be selected before Demo Migration?**

Add-ons can be selected during planning when the need is clear, but Demo Migration may reveal whether additional options are truly needed for URLs, recent data, media, history, or other supported outcomes.
