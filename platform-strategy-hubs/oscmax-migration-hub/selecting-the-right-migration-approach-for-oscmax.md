# Selecting the Right Migration Approach for osCMax

Choosing the right migration approach for osCMax requires more than comparing record counts. osCMax stores often combine osCommerce-like records with package behavior, old contributions, templates, custom files, custom tables, and hosting assumptions. That means the right service path depends on how much of the store is standard data and how much of the business meaning is created by legacy behavior around that data.

A simple osCMax store may fit a straightforward Migration Service path. A complex store may need Managed Service, Add-ons, Custom Service, or a combination of service components. The decision should be based on evidence: version clarity, contribution dependency, database structure, file customization, template behavior, record quality, target configuration requirements, and validation burden.

The purpose of service selection is not to overcomplicate the migration. It is to prevent the wrong assumption from entering the project. If the store only needs core records moved, the plan should stay focused. If the store depends on contribution-owned logic, custom fields, modified modules, or old checkout behavior, the plan must say so early.

### Start With the Migration Scope, Not the Service Label <a href="#start-with-the-migration-scope-not-the-service-label" id="start-with-the-migration-scope-not-the-service-label"></a>

The first step is to describe what must move and what must continue to work after migration. Products, Customers, Orders, Categories, Reviews, Coupons, CMS Pages, and Blog Posts may be eligible data areas, but osCMax scope can extend beyond those labels. A product may include attributes, custom fields, image conventions, specials, or contribution-driven display behavior. An order may include payment labels, shipping references, custom export fields, customer group context, or modified status meaning.

The service path should be selected after the store is divided into four groups:

1. standard records that can be migrated through supported behavior;
2. records that need filtering, mapping, or configuration adjustment;
3. target-side behavior that must be configured or rebuilt outside data migration;
4. custom or contribution-owned data that requires tailored review.

This separation prevents Standard Service from being overloaded with old custom behavior. It also prevents Custom Service from being used unnecessarily when the need is only bounded filtering or mapping.

| Scope signal                                | Likely service implication                                           | What to confirm                                                  |
| ------------------------------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Clean products, customers, and orders       | Standard Service may be sufficient.                                  | Confirm field completeness and sample accuracy.                  |
| Many records but standard structure         | Managed Service may help coordinate larger execution and validation. | Confirm timing, scope, and launch responsibilities.              |
| Need specific filtering or mapping          | Add-ons may support bounded needs.                                   | Confirm supported fields and configuration limits.               |
| Contribution-owned tables or custom fields  | Custom Service may be required.                                      | Confirm data location, business meaning, and target expectation. |
| Old modules or template logic must continue | May require target-side replacement or Custom Service review.        | Separate data migration from target implementation.              |

The best starting question is not which service sounds strongest. It is what evidence proves the store’s actual migration scope.

### When Standard Service Is a Good Fit <a href="#when-standard-service-is-a-good-fit" id="when-standard-service-is-a-good-fit"></a>

Standard Service is appropriate when the osCMax migration mainly involves supported core records and the merchant accepts that target-side setup, theme implementation, app installation, and custom development are separate from data migration. It can fit stores with straightforward categories, products, customers, orders, reviews, coupons, CMS Pages, and other eligible data that do not depend heavily on custom tables or legacy contribution logic.

For osCMax, Standard Service should still be chosen carefully. A store can look standard from the storefront while hiding old modules or custom fields in the database. Before Standard Service is treated as sufficient, the merchant should confirm that the primary business value is in transferable records, not in contribution-owned behavior.

Standard Service is usually stronger when:

* the store version is known;
* the database structure is understandable;
* products and orders use mostly expected fields;
* templates are not treated as migration deliverables;
* old modules are not required to behave the same way on the Target Platform;
* validation samples show that migrated records retain business meaning.

The decision cue is simple: Standard Service is appropriate when the migration objective is to transfer supported data, not to recreate the old osCMax environment.

### When Managed Service Adds Value <a href="#when-managed-service-adds-value" id="when-managed-service-adds-value"></a>

Managed Service is valuable when the merchant needs coordination, migration planning support, scope control, and guided validation. It does not turn every unsupported legacy behavior into a standard deliverable, but it helps manage a migration where evidence must be reviewed, decisions must be sequenced, and validation must be more disciplined.

For osCMax, Managed Service often makes sense when the store is older, has several contributions, contains uncertain data quality, or requires coordination between technical stakeholders and business reviewers. The merchant may not need bespoke transformation for every area, but they may need help deciding what to migrate, what to exclude, what to map, and what to validate before Full Migration.

Managed Service is especially useful when:

* the merchant has a large catalog or substantial order history;
* version evidence is available but old changes need interpretation;
* multiple stakeholders must approve catalog, customer, order, content, and SEO outcomes;
* Demo Migration findings are expected to influence mapping or configuration decisions;
* launch timing requires disciplined review rather than ad hoc checking.

| Managed Service need  | osCMax example                                                                  | Planning benefit                                 |
| --------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------ |
| Scope coordination    | Some contributions are active, some are abandoned.                              | Helps decide what belongs in migration scope.    |
| Validation planning   | Images, attributes, orders, and content all need review.                        | Reduces launch surprises.                        |
| Decision sequencing   | Demo Migration may reveal custom fields or old module dependencies.             | Supports staged decisions before Full Migration. |
| Stakeholder alignment | Technical owner and business owner understand different parts of the old store. | Keeps evidence, scope, and approval connected.   |

Managed Service is not a substitute for Custom Service when unsupported data must be transformed. It is a stronger management path for migrations that need supervision and structured decision-making.

### Where Add-ons Fit in osCMax Migration <a href="#where-add-ons-fit-in-oscmax-migration" id="where-add-ons-fit-in-oscmax-migration"></a>

Add-ons support bounded migration needs. They are useful when the requirement is specific, supported, and controlled: filtering records, mapping fields, configuring supported behavior, or applying defined migration adjustments. For osCMax, Add-ons may help when legacy data needs selective handling but does not require bespoke engineering or unsupported source interpretation.

Examples include filtering inactive products, mapping a known field to a supported target field, adjusting supported configuration behavior, or narrowing the data scope for Demo Migration or Full Migration. Add-ons can also help when the merchant needs to control which records move first or how eligible records are handled within supported migration behavior.

Add-ons should not be used as a vague answer for old contribution behavior. If a contribution creates custom tables, stores data in unusual fields, changes checkout behavior, or generates a report that the business still depends on, the requirement may need Custom Service or target-side replacement. The boundary matters because Add-ons are not a promise to recreate old modules, templates, admin functions, or custom applications.

| Need                     | Add-on may fit when                                      | Add-on is not enough when                                  |
| ------------------------ | -------------------------------------------------------- | ---------------------------------------------------------- |
| Data filtering           | The records and filter criteria are supported and clear. | The filter depends on custom logic hidden in code.         |
| Field mapping            | Source and target fields are known and supported.        | Source values come from custom tables or derived behavior. |
| Configuration adjustment | The change stays within supported migration behavior.    | The requirement needs new target functionality.            |
| Sample control           | Demo Migration needs representative scoped records.      | Samples require interpreting unsupported business rules.   |

The practical rule: Add-ons are appropriate for bounded migration adjustments, not for preserving unknown legacy behavior.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is required when the migration need falls outside supported migration behavior and needs tailored review. osCMax is a platform where this boundary appears often because old stores may contain contribution-owned records, custom fields, custom tables, modified files, bespoke reports, old export logic, template-coupled content, or storefront functions created by code rather than standard data.

Custom Service may be needed when the merchant wants to preserve a business outcome but the evidence shows that the outcome depends on non-standard structures. For example, a wholesale form, restricted content logic, special shipping behavior, custom order export, old image treatment, or template-specific navigation may not be ordinary data migration. The team must first identify whether the requirement is data, configuration, target-side functionality, or a custom transformation need.

Custom Service should be scoped carefully. It should not promise automatic full target-store setup, app implementation, custom development, or theme redesign. It is a tailored migration review and handling path for requirements that need non-standard treatment. In some cases, Custom Service may migrate or transform specific data. In other cases, the right recommendation may be to rebuild the behavior directly on the Target Platform.

Custom Service signals include:

* custom database tables or fields tied to active business processes;
* modified core files that change catalog, customer, order, or checkout meaning;
* contribution-owned records without a standard target equivalent;
* old module behavior that must be preserved for operational continuity;
* bespoke transformations required before data becomes usable;
* Custom Platform needs or unsupported source behavior.

For osCMax, Custom Service should be framed as a precision tool. It protects the project from pretending that custom legacy behavior is ordinary data.

### Separate Data Migration From Target-Side Rebuild Decisions <a href="#separate-data-migration-from-target-side-rebuild-decisions" id="separate-data-migration-from-target-side-rebuild-decisions"></a>

One of the most important service-path decisions in an osCMax project is whether a legacy function should be migrated, rebuilt, replaced, or retired. Many osCMax stores gained functionality through contributions and file changes. Some of those functions store data that can be migrated. Others create behavior that belongs to target-side configuration or development. Treating all of them as data migration creates unrealistic expectations.

A product image gallery, a special shipping table, a restricted content rule, a custom order export, or a template-based navigation box may all matter to the merchant. But they do not all require the same migration response. Image records may be migrated if the structure is supported and assets are available. Shipping logic may need target configuration. Restricted access may require customer-group mapping, target features, or a new access-control approach. Order exports may be replaced by target reporting tools. Template boxes may become content, theme work, or retired interface elements.

The service path should therefore include a behavior disposition review. Each important old behavior should receive one of four outcomes: migrate as supported data, adjust through Add-ons, review through Custom Service, or rebuild outside the data migration scope. This makes the project more controlled and prevents Custom Service from becoming a catch-all for every old feature.

| Legacy behavior type            | Best first question                                     | Likely handling path                                              |
| ------------------------------- | ------------------------------------------------------- | ----------------------------------------------------------------- |
| Data stored in supported fields | Can the field map cleanly to the Target Platform?       | Standard Service, Managed Service, or Add-ons.                    |
| Data stored in custom tables    | What business meaning must be preserved?                | Custom Service review.                                            |
| Behavior created by old modules | Is the behavior still required on the new store?        | Target configuration, replacement, or Custom Service review.      |
| Template-based presentation     | Is this content, navigation, or design?                 | Target-side theme/content planning, not automatic data migration. |
| Admin convenience functions     | Is historical data affected or only admin productivity? | Usually replacement, retirement, or separate target setup.        |

This separation is especially important for merchants who want the new store to be more stable than the old one. The migration approach should preserve business continuity, not rebuild every historical workaround.

### Decide Who Owns Each Validation Decision <a href="#decide-who-owns-each-validation-decision" id="decide-who-owns-each-validation-decision"></a>

Service selection also depends on validation ownership. A migration can be technically well executed and still fail launch review if no one is responsible for confirming business meaning. osCMax migrations often require different reviewers for catalog data, template expectations, order history, customer groups, shipping references, and legacy contribution behavior. The service path should account for this coordination burden.

A small merchant with clean records may validate the results directly after Demo Migration. A larger or more customized store may need Managed Service because the review requires coordination across store owner, developer, operations, SEO, and customer-service stakeholders. Custom Service may be needed when a technical reviewer must interpret custom tables or code behavior before the migration plan can be finalized.

Validation ownership should be defined before Full Migration. The catalog reviewer should confirm product structure, attributes, images, and categories. The operations reviewer should confirm order statuses, payment labels, shipping references, and reporting needs. The storefront reviewer should confirm CMS Pages, navigation, and important assets. The technical reviewer should confirm whether custom data needs tailored handling. This division keeps the service path honest because it shows whether the merchant only needs execution or also needs coordination and tailored interpretation.

| Reviewer role        | osCMax area to confirm                              | Service-path impact                                      |
| -------------------- | --------------------------------------------------- | -------------------------------------------------------- |
| Store owner          | Commercial meaning and launch priorities.           | Clarifies what must continue and what can change.        |
| Catalog reviewer     | Products, attributes, categories, images, specials. | Confirms whether Standard Service or Add-ons are enough. |
| Operations reviewer  | Orders, statuses, shipping, payment, exports.       | Identifies Managed Service or Custom Service triggers.   |
| Technical reviewer   | Custom files, tables, modules, templates.           | Determines whether tailored review is required.          |
| SEO/content reviewer | CMS Pages, URLs, metadata, navigation assets.       | Separates migration scope from target-side SEO work.     |

A service path that ignores validation ownership is incomplete. osCMax complexity is often discovered not in the export, but in the review of what the export means.

### Use Entity Points as Scope Sizing, Not Complexity Scoring <a href="#use-entity-points-as-scope-sizing-not-complexity-scoring" id="use-entity-points-as-scope-sizing-not-complexity-scoring"></a>

Entity Points help size eligible record migration. New eligible Products, Customers, Orders, and Blog Posts consume Entity Points when first migrated. Records already counted through the service license do not consume Entity Points again simply because another migration action occurs on the same migration path.

For osCMax, this rule is important because complexity and record count may not move together. A store with many standard products may be broad but manageable. A store with fewer records but several active contributions may require more tailored review. Entity Points can help plan eligible record volume, but they do not measure version uncertainty, contribution dependency, custom table risk, template coupling, or old checkout behavior.

A merchant should use Entity Points to answer one question: how much eligible data is being migrated? The merchant should use the service-path assessment to answer a different question: how complex is the behavior around that data?

| Planning question                                                                            | Use Entity Points? | Use service-path review?                      |
| -------------------------------------------------------------------------------------------- | ------------------ | --------------------------------------------- |
| How many eligible new Products, Customers, Orders, or Blog Posts are first migrated?         | Yes                | Sometimes                                     |
| Does a custom contribution require tailored handling?                                        | No                 | Yes                                           |
| Does old image or template behavior need validation?                                         | No                 | Yes                                           |
| Should a second migration action consume Entity Points for the same already-counted records? | No                 | Review only if new eligible records are added |
| Does the store need Add-ons or Custom Service?                                               | Not by itself      | Yes                                           |

This distinction prevents a common planning error: assuming that a low record count means a simple osCMax migration.

### Use Demo Migration to Choose the Final Path <a href="#use-demo-migration-to-choose-the-final-path" id="use-demo-migration-to-choose-the-final-path"></a>

Demo Migration is the safest way to test whether the selected approach is realistic. For osCMax, Demo Migration should include more than clean products and recent orders. It should include representative records that expose version-line, contribution, template, image, customer, content, and order assumptions.

The Demo Migration should answer several questions. Do core records arrive correctly? Do product attributes and images retain usable meaning? Do customer and order relationships remain understandable? Do old statuses, discounts, shipping references, and payment labels make sense in the target context? Are CMS Pages and content records represented appropriately? Are there records that appear in the old database but not in supported migration outputs because they belong to custom or contribution-specific structures?

If Demo Migration confirms the expected results, the project may proceed toward Full Migration with the selected service path. If Demo Migration reveals missing fields, unexpected relationships, unsupported structures, or custom behavior, the service path should be adjusted before Full Migration. The adjustment may involve Add-ons, Managed Service coordination, Custom Service review, or a decision to replace old behavior on the Target Platform instead of migrating it.

Demo Migration is not a ceremonial preview. It is the decision point where assumptions become evidence.

### Plan Additional Migration Options Carefully <a href="#plan-additional-migration-options-carefully" id="plan-additional-migration-options-carefully"></a>

Additional Migration Options become relevant when follow-up migration is needed after the initial migration path. For osCMax, follow-up planning is most useful when the merchant needs to continue after new records are created, adjust configuration after Demo Migration findings, or restart with materially different scope assumptions.

There are three practical paths. The merchant may continue the migration with the last used configuration when the original setup is still valid. The merchant may continue with a new configuration when mapping, filtering, or configuration decisions have changed. Or the merchant may perform a new migration when the project has changed enough that the old path should not be reused.

For osCMax, the choice should depend on evidence. If only new eligible orders appeared after the last migration, continuing with the last configuration may be sufficient. If Demo Migration showed that product fields, customer groups, or content handling need a different configuration, a new configuration may be safer. If the merchant discovers a major contribution-owned data layer or changes the Target Platform plan, a new migration may be more appropriate.

| Follow-up situation                                  | Better option                             | Reason                                                       |
| ---------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------ |
| Same scope, same configuration, new eligible records | Continue with the last used configuration | Keeps the migration path consistent.                         |
| Same store, but mapping or filtering changes         | Continue with a new configuration         | Reflects updated migration decisions.                        |
| Major scope change or new Target Platform direction  | Perform a new migration                   | Avoids carrying old assumptions into a changed project.      |
| Custom data discovered after Demo Migration          | Review before choosing                    | May require Custom Service instead of a simple continuation. |

Additional Migration Options should support control. They should not be used to postpone difficult scope decisions.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right migration approach for osCMax depends on how much of the old store is clean data and how much depends on contribution behavior, custom files, templates, version history, and hosting assumptions. Standard Service can fit clean supported records. Managed Service adds coordination and validation control. Add-ons support bounded filtering, mapping, and configuration needs. Custom Service handles non-standard records, custom tables, bespoke transformations, and contribution-owned behavior that requires tailored review.

Entity Points help size eligible record volume, but they do not measure legacy complexity. Demo Migration should turn assumptions into evidence before Full Migration. Additional Migration Options should be used only when the follow-up path is clear. This keeps osCMax migration practical, controlled, and aligned with the real store rather than with a simplified label.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Can osCMax migration use Standard Service?**

Yes, when the migration mainly involves supported core records and the merchant does not expect old contribution behavior, templates, modules, or custom code to be recreated as part of data migration.

**When does osCMax require Custom Service?**

Custom Service is appropriate when active business meaning depends on custom tables, custom fields, modified files, contribution-owned records, bespoke transformations, unsupported source behavior, or Custom Platform requirements.

**Do Entity Points measure osCMax migration complexity?**

No. Entity Points help size eligible new Products, Customers, Orders, and Blog Posts when first migrated. They do not measure contribution dependency, old code behavior, template coupling, or custom logic.

**How should Demo Migration influence the service path?**

Demo Migration should confirm whether the selected path handles representative records correctly. If it reveals unsupported structures, missing custom fields, or contribution-driven behavior, the service path should be adjusted before Full Migration.
