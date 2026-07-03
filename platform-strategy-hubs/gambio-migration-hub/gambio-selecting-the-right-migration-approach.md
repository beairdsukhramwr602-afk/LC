# Gambio Selecting the Right Migration Approach

Selecting the right migration approach for Gambio begins with the target operating model. A Gambio Cloud target and a self-hosted Gambio target can both support a professional online store, but they do not create the same migration responsibilities. Cloud reduces hosting and update responsibility for the merchant, while self-hosting gives more flexibility and customization control. That difference affects the evidence needed, the service path, and the validation burden.

A Gambio migration should not be scoped only by counting products, customers, and orders. The more important question is whether the source store’s catalog, options, stock behavior, content pages, historical orders, legal/trust content, integrations, and custom logic fit the planned target environment. Standard Service may be sufficient for a clean store with ordinary supported records. Managed Service, Add-ons, or Custom Service become more relevant when the project needs operational judgment, bounded transformation, or unsupported custom handling.

The best service path is the one that keeps four boundaries visible: what can move as supported data, what must be configured in Gambio, what must be validated after Demo Migration, and what requires custom handling outside ordinary migration behavior.

### How Gambio Service Selection Should Be Read <a href="#how-gambio-service-selection-should-be-read" id="how-gambio-service-selection-should-be-read"></a>

Gambio service selection should be read as a scope decision, not as a preference for more or less assistance. The right path depends on the store’s data structure, operating responsibility, customization depth, and validation capacity.

A simple store can often proceed with a lighter migration path because the data meaning is visible. A store with many product options, downloads, custom fields, marketplace records, legal/content dependencies, or external identifiers may need a more controlled approach even if the record count is not large. Complexity is not always volume. Sometimes a small catalog with custom product logic is harder to migrate than a larger catalog with consistent records.

| Decision factor    | Lower-scope signal                                                               | Higher-scope signal                                                                                          |
| ------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Target environment | Cloud or self-hosted responsibility is already clear.                            | Environment choice is undecided or tied to custom access needs.                                              |
| Catalog structure  | Products, categories, images, and stock behavior are standard and consistent.    | Options, downloads, stock rules, custom fields, or external inventory references are important.              |
| Content structure  | CMS Pages are limited and easy to place.                                         | Legal, trust, SEO, or campaign pages require classification and placement decisions.                         |
| Historical orders  | Orders use common statuses, payment labels, shipping methods, and product lines. | Orders include custom statuses, marketplace data, downloads, refunds, tax variation, or external references. |
| Integrations       | Payment, shipping, and marketplace setup can be recreated separately.            | External systems own business meaning that must remain connected to migrated records.                        |

This table should guide service selection before Demo Migration. Demo Migration then tests whether the selected path is realistic.

### When Standard Service Is a Good Fit <a href="#when-standard-service-is-a-good-fit" id="when-standard-service-is-a-good-fit"></a>

Standard Service is most suitable when the Gambio migration involves supported records with predictable structure. The store should have clean products, categories, customers, orders, images, and related data that can be moved without extensive interpretation or custom transformation.

For Gambio, Standard Service is a stronger fit when the merchant already knows whether the target is Cloud or self-hosted, the catalog uses ordinary products and categories, product options are simple, stock behavior is not highly customized, content pages are limited or well organized, and historical orders do not depend on unusual status or external-system logic.

Standard Service can be appropriate when the merchant can review Demo Migration results internally. The merchant should be able to check product completeness, category placement, customer identity, order readability, CMS Pages, and basic storefront behavior without needing the migration team to interpret every decision.

Standard Service is weaker when the source store’s meaning is hidden in modules, custom tables, external integrations, theme logic, marketplace connectors, or special product rules. In those cases, the issue is not whether the store can be exported. The issue is whether the exported records explain enough to create a reliable Gambio target.

### When Managed Service Adds Value <a href="#when-managed-service-adds-value" id="when-managed-service-adds-value"></a>

Managed Service is appropriate when the merchant needs Next-Cart to handle more of the migration process and decision coordination. It does not turn every custom requirement into standard scope, but it can reduce execution burden when the merchant wants more guidance through Demo Migration, Full Migration, configuration checks, and issue review.

For Gambio, Managed Service is useful when the project has several moving parts: Cloud/self-hosting decisions, many catalog samples to review, category and content cleanup, order-history verification, or internal teams that need a clearer sequence for validation. It is also useful when the merchant knows the store is not technically exotic but still wants controlled execution.

Managed Service is not a substitute for Custom Service. If the source store includes unsupported records, custom fields, bespoke transformation rules, external identifiers, or custom migration logic adjustment, those items still need separate review. Managed Service helps manage the process; Custom Service handles cases where the migration behavior itself must be adapted.

| Managed Service is useful when…                                                         | It should not be used to assume…                                              |
| --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| The merchant needs guided execution and clearer review checkpoints.                     | Unsupported custom data will automatically become standard scope.             |
| Demo Migration requires structured feedback across product, order, and content samples. | Target design, legal review, or integration rebuilds are included by default. |
| Several teams must coordinate before Full Migration.                                    | All external-system behavior is recreated through data migration.             |
| The project needs less merchant-side operational burden.                                | Custom source logic can be ignored.                                           |

The best use of Managed Service is to keep the project organized while still separating supported migration, Add-ons, Custom Service, and target-side implementation tasks.

### When Add-ons Are Needed <a href="#when-add-ons-are-needed" id="when-add-ons-are-needed"></a>

Add-ons are appropriate when the required change is bounded and fits supported migration behavior. In Gambio projects, Add-ons may be relevant for filtering records, mapping fields, configuring how data is handled, or adjusting supported migration behavior within clear limits.

The Data Filter Add-on may be useful when the merchant does not want all eligible records moved. For example, the project may need to exclude obsolete products, old customers, old orders, inactive content pages, or records outside a defined date range. Filtering is a scope-control decision; it should not be used to hide uncertainty about which records matter.

Advanced Data Mapping can help when source fields need to be aligned carefully with Gambio fields. This may apply to product attributes, categories, customer fields, order statuses, or other supported data areas where the meaning is clear but field alignment needs control.

Advanced Data Configure can help when supported data needs specific configuration during migration. This may be relevant when the merchant has clear target handling rules for product visibility, category behavior, customer grouping, or order status interpretation.

Tailored Add-ons and Custom Add-ons may support bounded project needs that are not covered by default behavior but still remain within a defined migration adjustment. They should not be confused with Custom Service for unsupported or bespoke migration logic.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is required when the migration needs unsupported custom handling. For Gambio, this is most likely when the source store stores business meaning in custom fields, custom product structures, module-owned data, modified database tables, external-system identifiers, custom checkout rules, marketplace connector data, ERP links, or bespoke transformation rules.

Self-hosted Gambio expectations can increase Custom Service discussion because merchants may expect deep continuity from a heavily customized source store. Flexibility in the target environment does not mean custom source behavior migrates automatically. The project still needs to identify what is native data, what is configuration, what is extension-owned, what is external-system-owned, and what is custom logic.

Custom Service may be needed when:

* product logic depends on custom fields or modified source database structures;
* option or stock behavior does not fit supported product handling;
* downloadable products depend on custom access rules;
* marketplace or ERP identifiers must be preserved in a specific way;
* customer groups, tax behavior, or order status logic need bespoke interpretation;
* CMS Pages include generated or theme-embedded content requiring special extraction;
* the Source Platform or Target Platform requires custom migration logic adjustment.

Custom Service should be scoped explicitly. It should not be buried inside a general migration promise. Clear separation protects the merchant from discovering after Full Migration that critical business meaning was never part of ordinary data movement.

### Entity Points and Gambio Scope Control <a href="#entity-points-and-gambio-scope-control" id="entity-points-and-gambio-scope-control"></a>

Entity Points help control scope when eligible new Products, Customers, Orders, and Blog Posts are migrated. The key rule is that eligible new records consume Entity Points when first migrated. Records already counted through the service license do not consume again simply because another action happens on the same migration path.

In Gambio projects, Entity Points matter most when the merchant wants to add new records, expand scope, or handle follow-up migration after the initial path has been defined. They should not be used as a substitute for structural review. A store with fewer Products can still be complex if those Products depend on options, stock rules, downloads, custom fields, or external identifiers.

| Scope situation                                           | Entity Points relevance                                                         | Separate planning question                                                     |
| --------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| New Products are added after initial scope                | Eligible new Products may consume Entity Points when first migrated.            | Do those Products follow the same Gambio structure already validated?          |
| New Customers or Orders appear before launch              | Eligible new Customers or Orders may consume Entity Points when first migrated. | Are statuses, addresses, payments, shipping, and product lines still readable? |
| Blog Posts are added where applicable                     | Eligible new Blog Posts may consume Entity Points when first migrated.          | Should content be migrated, recreated, redirected, or retired?                 |
| Existing counted records are reprocessed on the same path | They do not consume again merely because another action occurs.                 | Has configuration changed enough to require a new migration path?              |

Entity Points answer a consumption question. They do not answer whether the target data is structurally ready for launch.

### Demo Migration as the Service-Path Test <a href="#demo-migration-as-the-service-path-test" id="demo-migration-as-the-service-path-test"></a>

Demo Migration is the practical test of the selected Gambio migration approach. It should include representative records, not only easy records. The point is to discover whether the chosen service path handles the store’s real structure.

A strong Gambio Demo Migration sample should include:

* products with options;
* products with stock behavior;
* downloadable products;
* products with multiple images;
* products in important categories;
* customers with addresses;
* orders with discounts, tax, shipping, payment, and status variation;
* CMS Pages with legal, trust, service, or SEO value;
* records touched by integrations or custom fields where relevant.

After Demo Migration, the team should classify findings into four groups: accepted behavior, configuration adjustment, Add-on need, and Custom Service need. This prevents every issue from being treated as the same kind of problem.

| Demo finding                                                             | Likely response                                                                               |
| ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| Supported data appears correct and readable.                             | Continue toward Full Migration with documented pass conditions.                               |
| Supported data needs bounded field, filter, or configuration adjustment. | Review Add-ons or rerun with revised configuration.                                           |
| Business meaning depends on unsupported custom records or logic.         | Scope Custom Service.                                                                         |
| Target-side setup is missing.                                            | Assign configuration, design, legal/content, or integration tasks outside ordinary migration. |

Demo Migration should produce a decision, not only a preview. The decision should state whether the current path is enough for Full Migration.

### Full Migration and Follow-Up Options <a href="#full-migration-and-follow-up-options" id="full-migration-and-follow-up-options"></a>

Full Migration should proceed when the service path, scope, and validation responsibilities are clear. For Gambio, that means the target environment is confirmed, catalog samples passed, content pages are classified, order readability is acceptable, Add-ons are selected where needed, and Custom Service items are either scoped or separated from the launch plan.

Additional Migration Options become relevant when data changes after the first migration path has been tested or completed. The correct option depends on what changed:

| Follow-up need                                                    | Better option                                           | Reason                                                                         |
| ----------------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------ |
| New records must be added using the same approved setup           | Continue the Migration with the last used configuration | The target handling rules are already validated.                               |
| Mapping, filtering, or configuration has changed                  | Continue the Migration with a new configuration         | The migration path has changed and must be treated as a new controlled action. |
| The project needs a substantially different source-to-target plan | Perform a new migration                                 | The prior path no longer represents the intended target structure.             |

These options are especially useful when a merchant continues selling while launch preparation continues. They should be planned with validation in mind, not treated as administrative buttons.

### Choosing the Right Gambio Path <a href="#choosing-the-right-gambio-path" id="choosing-the-right-gambio-path"></a>

The right Gambio path is selected by combining record scope with operating-model complexity. A merchant with a clean catalog, ordinary customer records, readable order history, stable categories, and limited external dependencies may fit a simpler path. A merchant with option-heavy products, downloadable items, legal or trust content, marketplace assumptions, custom fields, custom templates, or self-hosted integration needs usually requires more guided review.

The decision should not be based only on the number of records. A store with fewer Products may still require Managed Service or Custom Service if the records carry custom behavior. A store with more Products may remain predictable if the data is consistent and target configuration is already understood. Entity Points help with eligible record volume, but service-path selection should also consider how much interpretation, mapping, configuration review, and validation support is needed.

A strong service-path decision should identify escalation triggers before Demo Migration. If Demo Migration reveals option behavior that does not translate cleanly, historical orders that lose commercial context, CMS Pages that need restructuring, or integration assumptions that were not scoped, the project should decide whether Add-ons, Advanced Data Mapping, Advanced Data Configure, Custom Service, Additional Migration Options, or separate implementation are needed. Waiting until Full Migration to make those decisions increases launch risk.

The practical choice is usually clear when the merchant separates record movement from operating behavior. Standard Service fits clean supported data. Managed Service fits merchants who need more execution support. Add-ons fit bounded filtering, mapping, and configuration needs. Custom Service fits unsupported, custom, external, or bespoke migration requirements.

| Migration path               | Best fit                                                                    | Watch condition                                                                         |
| ---------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Standard Service             | Clean supported records with manageable internal review.                    | Hidden custom logic or integration-owned meaning.                                       |
| Managed Service              | Merchant needs guided execution and coordination.                           | Assuming guidance replaces custom migration work.                                       |
| Add-ons                      | Bounded filtering, mapping, or configuration needs.                         | Using Add-ons to avoid Custom Service when unsupported data is involved.                |
| Custom Service               | Unsupported records, custom fields, external identifiers, or bespoke logic. | Scope must be explicit before Full Migration.                                           |
| Additional Migration Options | Follow-up records or changed configuration after an initial path.           | Must match whether the configuration is unchanged, revised, or substantially different. |

The right path should make the migration easier to validate. If the selected path does not clarify what will be moved, configured, customized, or validated, the path is not ready.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Gambio migration approach depends on operating model, catalog structure, content responsibility, historical order readability, integration dependencies, and customization depth. Standard Service is appropriate for clean supported data. Managed Service adds process control. Add-ons handle bounded filtering, mapping, and configuration needs. Custom Service handles unsupported and bespoke requirements.

A strong decision separates record movement from target configuration, legal/content review, integration setup, and custom logic. Once those boundaries are clear, Demo Migration can test the selected path and Full Migration can proceed with fewer surprises.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for a Gambio migration?**

Standard Service is usually enough when the store has clean supported records, simple products and categories, readable customers and orders, limited content complexity, and no unsupported custom logic.

**When should Managed Service be selected?**

Managed Service is useful when the merchant wants guided execution, coordinated review, and clearer handling of Demo Migration and Full Migration without assuming that custom requirements become standard.

**Can Add-ons handle custom Gambio migration needs?**

Add-ons can handle bounded filtering, mapping, and configuration needs. Unsupported records, custom fields, external identifiers, bespoke transformation, or custom migration logic adjustment require Custom Service review.

**How do Entity Points affect Gambio migration scope?**

Eligible new Products, Customers, Orders, and Blog Posts consume Entity Points when first migrated. Records already counted through the service license do not consume again simply because another action happens on the same migration path.

**When should Additional Migration Options be considered?**

They are relevant when new records need to be added, configuration changes after a migration path has been tested, or a substantially different migration plan is needed.
