# Selecting the Right Migration Approach for Shopify Plus

Choosing the right Shopify Plus migration approach means matching the Migration Service to the business structure that must work after the data moves. Shopify Plus projects often involve more than products, customers, orders, pages, and redirects. They may include companies, company locations, buyer permissions, catalogs, pricing access, B2B and direct-to-consumer coexistence, organization governance, multiple stores, markets, metafields, metaobjects, apps, integrations, and external-system identifiers.

A lighter approach can be suitable when the future Shopify Plus model is already clear and the Source Platform data can move through supported structures with limited interpretation. A stronger approach is needed when B2B rules, catalog visibility, custom fields, app-owned records, integration keys, or multi-store governance must be interpreted before the result can be trusted. The right decision is not simply whether Shopify Plus is powerful enough. The decision is whether the selected service path gives the migration enough planning, execution responsibility, customization, and review discipline for the Target Platform outcome.

### Start with the Platform Migration Scope <a href="#start-with-the-platform-migration-scope" id="start-with-the-platform-migration-scope"></a>

Shopify Plus migration scope should start with the operating model that the business expects to run after migration. A store moving into Shopify Plus may need to preserve standard commerce records and enterprise structures at the same time. The scope review should separate what can move through standard supported handling, what needs closer managed coordination, what can be addressed with Add-ons, and what requires Custom Service.

A useful Shopify Plus scope assessment should answer these questions before service selection:

| Scope question                                                                                                  | Why it affects the migration approach                                                                                              |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Are B2B companies and company locations clearly defined?                                                        | Company structure affects buyer access, payment terms, tax context, catalog assignment, checkout behavior, and validation samples. |
| Are catalogs, prices, visibility rules, quantity rules, and volume pricing documented?                          | Catalog-controlled access can turn a simple product migration into a commercial-rule migration.                                    |
| Will B2B and direct-to-consumer activity share one store, separate stores, or a market-based structure?         | Store and market governance changes how records, URLs, content, customer accounts, and launch checks are planned.                  |
| Do products rely on complex variants, metafields, metaobjects, category metafields, or app-controlled behavior? | These structures can require advanced mapping, data configuration, or custom interpretation.                                       |
| Are ERP, CRM, subscription, fulfillment, wholesale, or reporting systems part of the record meaning?            | External identifiers and integration logic may require Custom Service if they must remain usable after migration.                  |
| Can the internal team operate and validate the migration confidently?                                           | Limited review capacity can make Managed Service safer even when the data itself is not highly custom.                             |

The approach should be chosen after the real business burden is visible. Shopify Plus can support enterprise migration outcomes, but it cannot automatically infer how a legacy customer group becomes a company, how a branch account becomes a company location, how source price lists should become catalogs, or how a custom field should support downstream operations.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the Shopify Plus target model is already defined, the source data aligns with supported migration behavior, and the customer can actively operate, review, and validate the process. It is strongest when the migration is structurally clear rather than exploratory.

For Shopify Plus, Standard Service is usually strongest when:

* companies, company locations, buyer contacts, permissions, payment terms, and catalog assignments are simple or already mapped;
* B2B catalog logic is limited, documented, and not dependent on hidden custom rules;
* product variants, collections, customers, orders, CMS Pages, Blog Posts, and redirects can move without major transformation;
* metafields, metaobjects, apps, or external IDs are either outside scope, already prepared, or not business-critical;
* one store, one market structure, or a clearly defined set of stores is already confirmed;
* Demo Migration samples show that representative records keep acceptable Shopify Plus meaning;
* the customer has enough internal capacity to review buyer access, catalogs, checkout behavior, URLs, and operational samples.

Standard Service does not mean the migration is unmanaged by quality standards. It means the customer remains more hands-on in configuration decisions, data review, Demo Migration assessment, and final approval. For Shopify Plus, that requires a capable internal reviewer who understands B2B account logic, catalog assignments, product structure, and operational dependencies.

A Shopify Plus project should not remain on a lighter approach only because the entity list looks manageable. A small number of records can still be complex if the records carry company hierarchy, custom pricing, external IDs, or app-dependent workflow meaning.

### When Managed Service Is a Better Fit <a href="#when-managed-service-is-a-better-fit" id="when-managed-service-is-a-better-fit"></a>

Managed Service is often the better fit when Shopify Plus is the right Target Platform but the customer needs Next-Cart to carry more migration execution and coordination responsibility. This is common when the business has many stakeholders, several data owners, multiple review cycles, or limited internal migration capacity.

Managed Service is often appropriate when:

* the target Shopify Plus model is viable, but the customer does not want to operate the migration process independently;
* company, company-location, buyer-contact, catalog, and order-history samples require coordinated review;
* multiple teams need to confirm products, B2B structure, content, SEO, fulfillment, finance, and customer support outcomes;
* the Demo Migration requires structured interpretation, but does not reveal the need for bespoke transformation;
* the project involves many records, several stores, markets, domains, languages, or regional operating contexts;
* the business wants stronger migration coordination while retaining responsibility for business-rule approval and launch decisions.

Managed Service is not a substitute for defining the target model. The customer still needs to confirm how company structure, catalogs, pricing, account access, store governance, and integrations should behave. Managed Service is most useful when the main pressure is execution and coordination, not when the source data requires unsupported transformation or custom migration logic adjustment.

For Shopify Plus, Managed Service often fits enterprise teams that know what the result should be but need a more controlled path to reach it. It can reduce coordination risk when internal teams are busy with merchandising, B2B rollout, ERP readiness, theme work, app setup, and launch planning at the same time.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons should be considered when the project has a specific extra requirement that can be handled within supported migration behavior. They should not be used as a vague answer to every Shopify Plus complexity. Add-ons are useful when the need is bounded, identifiable, and compatible with the selected migration path.

For Shopify Plus, Add-ons may be relevant for:

| Add-on direction        | Shopify Plus use case                                                                                                                                                         |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Excluding retired products, inactive customers, old orders, irrelevant Blog Posts, obsolete CMS Pages, or source records that should not enter the Shopify Plus launch scope. |
| Advanced Data Mapping   | Aligning supported fields, categories, product structures, customer context, or other supported data structures where source and target meaning need clearer mapping.         |
| Advanced Data Configure | Applying extra supported setup where the migration needs more configuration than the default handling.                                                                        |

Add-ons work best when the requirement is narrow enough to describe clearly. For example, filtering old orders by date range is different from transforming legacy B2B account logic into companies, locations, catalogs, payment terms, and external IDs. The first may fit an Add-on. The second may require Custom Service if the source logic is nonstandard or depends on business interpretation outside supported handling.

A Shopify Plus migration should treat Add-ons as precision support, not a workaround for unclear scope. If a requirement involves app-owned data, custom source tables, unsupported fields, external-system identifiers, bespoke pricing relationships, or custom migration logic adjustment, the safer review path is usually Custom Service.

### When Custom Service Is Needed <a href="#when-custom-service-is-needed" id="when-custom-service-is-needed"></a>

Custom Service is needed when the Shopify Plus result depends on customization, modification, bespoke handling, Custom Platform interpretation, unsupported data, custom fields, app-dependent relationships, external-system identifiers, or custom migration logic adjustment. It is the right path when standard supported handling and bounded Add-ons cannot preserve the business meaning of the data.

For Shopify Plus, Custom Service should be considered when:

* source-side customer groups, account hierarchies, wholesale portals, or branch structures must become Shopify Plus companies and company locations through custom interpretation;
* catalog visibility, pricing, quantity rules, volume pricing, or buyer-specific access depends on custom logic rather than clean exportable fields;
* company IDs, location IDs, ERP IDs, CRM IDs, sales-rep assignments, contract references, or other external identifiers must remain usable;
* metafields, metaobjects, category metafields, custom product attributes, or app-owned records carry launch-critical meaning;
* the Source Platform is a Custom Platform or a heavily modified supported platform;
* subscription, fulfillment, ERP, marketplace, loyalty, approval, or reporting workflows make migrated records meaningful only when surrounding relationships are preserved;
* the business needs a transformation that is not simply field mapping, filtering, or supported data configuration.

Custom Service does not automatically mean Next-Cart performs complete migration management. Migration management is included only when it is part of the final plan. The key distinction is that Custom Service creates the path for bespoke handling when the project cannot be safely treated as a standard supported migration.

For Shopify Plus, Custom Service is often less about record volume and more about meaning. A small B2B catalog with custom contract pricing and ERP-linked locations may require more custom planning than a larger but cleaner direct-to-consumer catalog.

### How Entity Points Affect Planning <a href="#how-entity-points-affect-planning" id="how-entity-points-affect-planning"></a>

Entity Points affect Shopify Plus planning when record volume, entity selection, or later inclusion decisions change the capacity required under the selected service license and Entity Points Plan. They should be used for capacity planning, not as a shortcut for risk scoring.

Shopify Plus projects should review Entity Points around counted records such as products, customers, orders, Blog Posts, and other supported entities included in the migration scope. The review becomes especially important when the business plans to filter records, include additional historical orders, migrate more Blog Posts or CMS Pages, add B2B-related customer data, or expand the scope after Demo Migration.

Entity Points should not be confused with complexity. A complex company hierarchy, pricing relationship, app dependency, or custom identifier can create service-scope risk even if the counted record volume is not large. Conversely, a high-volume but clean catalog may require capacity planning without necessarily requiring Custom Service.

The current Entity Points rule should remain clear in Shopify Plus planning: Entity Points consumption depends on whether migrated entities are new to the migration license record. Already recorded entities do not deduct Entity Points again solely because the customer performs later migration activity for the same migration path. If later activity includes new counted records, remaining Entity Points should be reviewed before the project proceeds.

### How Additional Migration Options Affect the Approach <a href="#how-additional-migration-options-affect-the-approach" id="how-additional-migration-options-affect-the-approach"></a>

Additional Migration Options matter in Shopify Plus projects when source-store activity or configuration changes continue after the first migration activity. Enterprise and B2B stores often keep receiving new orders, adding customers, changing products, modifying prices, updating content, or refining company and catalog setup while the launch project is still active.

For Shopify Plus, Additional Migration Options should be planned around platform-specific change areas:

* new products, variants, customers, orders, CMS Pages, or Blog Posts added before launch;
* changed company, company-location, buyer-contact, catalog, payment-term, or checkout settings;
* new filtering requirements after the business decides to exclude or include records differently;
* changed mapping assumptions for product structure, customer account context, B2B identity, or content ownership;
* updated URL, redirect, collection, market, or SEO-sensitive structures;
* Add-on output that changes review samples;
* Custom Service output that requires renewed validation.

Additional Migration Options should not be treated as a generic fix for unresolved Shopify Plus planning. They can help handle later migration activity, but they still require clear source tracking, service-scope decisions, Demo Migration review, and platform-specific validation. If the company model, catalog logic, or custom data scope changes after the first migration activity, the selected approach should include renewed review of the affected records and behaviors.

### Choosing the Right Path Before Full Migration <a href="#choosing-the-right-path-before-full-migration" id="choosing-the-right-path-before-full-migration"></a>

The right Shopify Plus path should be chosen before Full Migration based on the actual burden shown by source review, target setup, Demo Migration, and service-scope classification. A practical decision sequence is:

1. Confirm the Shopify Plus target model: companies, locations, catalogs, stores, markets, products, content, integrations, and launch responsibilities.
2. Identify which requirements fit supported standard handling.
3. Separate bounded Add-on needs from broader Custom Service needs.
4. Review Entity Points for counted records and likely scope changes.
5. Decide whether the customer can operate the project directly or needs Managed Service support.
6. Use Demo Migration results to confirm whether the selected approach is strong enough.
7. Plan Additional Migration Options only where later activity or source changes are likely to affect launch readiness.

The decision should be made with representative examples, not abstract confidence. The strongest Shopify Plus samples usually include complex products, key companies, multiple locations, important buyer contacts, assigned catalogs, B2B pricing examples, representative orders, SEO-sensitive URLs, custom fields, integration identifiers, and any app-dependent records that influence launch operations.

| Project condition                                                                                                                                | Likely service-path implication                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| Clean source data, clear Shopify Plus setup, capable internal reviewers                                                                          | Standard Service may be enough.                                               |
| Clear target model but heavy execution, many stakeholders, or limited internal migration capacity                                                | Managed Service is often safer.                                               |
| Narrow filtering, mapping, or configuration needs within supported behavior                                                                      | Add-ons may be appropriate.                                                   |
| Custom company logic, bespoke pricing interpretation, app-owned data, external IDs, Custom Platform source, or custom migration logic adjustment | Custom Service should be reviewed.                                            |
| Frequent source changes before launch                                                                                                            | Additional Migration Options should be planned with renewed validation scope. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Shopify Plus migration approach is the one that matches the real enterprise burden behind the data. Standard Service can work when the Target Platform structure is clear, supported handling is enough, and the customer can review results carefully. Managed Service is safer when execution and coordination would place too much pressure on the internal team. Add-ons support bounded filtering, mapping, or configuration needs. Custom Service is the stronger path when Shopify Plus readiness depends on bespoke transformation, app-dependent data, external IDs, Custom Platform handling, or custom migration logic adjustment.

Entity Points should support capacity planning, while Additional Migration Options should support platform-specific follow-up migration planning when source activity or configuration changes continue before launch. Neither should be used as a substitute for defining the Shopify Plus target model. The safest approach is the one confirmed by real source evidence, realistic Demo Migration samples, service-scope boundaries, and a clear validation plan before Full Migration.

For Shopify Plus projects with B2B structure, catalog-controlled pricing, organization governance, custom data, or integration dependencies, use Demo Migration results and Live Chat discussion to confirm whether Standard Service, Managed Service, selected Add-ons, Custom Service, or Additional Migration Options should shape the final migration path.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Shopify Plus always a Custom Service migration?**

No. Shopify Plus does not automatically require Custom Service. Standard Service or Managed Service may be suitable when the Shopify Plus target model is clear and the source data can move through supported handling. Custom Service becomes relevant when the project requires bespoke handling, unsupported custom data, Custom Platform interpretation, or custom migration logic adjustment.

**When is Standard Service enough for Shopify Plus?**

Standard Service is usually enough when company structure, catalogs, products, customers, orders, content, and URLs are clearly prepared, the Demo Migration result is acceptable, and the customer can actively operate and validate the migration.

**When should a Shopify Plus project use Managed Service?**

Managed Service is often better when Shopify Plus is the right Target Platform but the business wants Next-Cart to carry more migration execution and coordination responsibility. It is useful when internal teams need to focus on review, setup confirmation, and launch decisions instead of operating the migration process themselves.

**Can Add-ons substitute for Custom Service in a Shopify Plus migration?**

No. Add-ons support specific extra requirements such as filtering, advanced mapping, or advanced data configuration. Custom Service is needed when the project depends on bespoke handling, unsupported structures, external-system identifiers, Custom Platform handling, or custom migration logic adjustment.

**How should Entity Points be reviewed for Shopify Plus?**

Entity Points should be reviewed around counted records such as products, customers, orders, Blog Posts, CMS Pages, and other included entities. They help confirm whether the selected service license and Entity Points Plan can cover the planned scope. They should not be used as a risk score or a substitute for custom-scope review.

**Do Additional Migration Options remove the need for validation?**

No. Additional Migration Options can help address later migration activity, but Shopify Plus outcomes still need renewed validation when affected records, mappings, company data, catalog assignments, URLs, content, Add-on output, or Custom Service output change before launch.
