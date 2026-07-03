# Selecting the Right Migration Approach for Bagisto

Selecting the right migration approach for Bagisto means matching the store’s operating complexity to the correct service path. Bagisto can support ordinary ecommerce records, but it can also support product-type complexity, attribute-family planning, channels, inventory sources, customer groups, marketing rules, CMS content, marketplace behavior, B2B logic, APIs, headless storefronts, packages, themes, and custom Laravel development. The correct approach depends on which of those structures must be preserved, configured, mapped, rebuilt, or validated.

A Bagisto migration should not be selected only by record volume. Record volume matters, especially for Entity Points and migration sizing, but complexity often comes from relationships and behavior. A smaller catalog with configurable products, custom attributes, channel-specific visibility, and API dependencies may require more planning than a larger catalog of simple products.

The practical goal is to decide which work belongs in Standard Service, which work needs Managed Service, which bounded changes can be handled by Add-ons, which requirements need Custom Service, how Demo Migration should confirm the choice, and which Additional Migration Options should be prepared before launch.

### What Migration Approach Means for Bagisto <a href="#what-migration-approach-means-for-bagisto" id="what-migration-approach-means-for-bagisto"></a>

The migration approach defines how much of the Bagisto project can be handled through supported migration behavior and how much requires planning, configuration, or custom handling. In a Bagisto project, the key distinction is not only between small and large stores. It is between ordinary commerce records and architecture-sensitive behavior.

A record is usually easier to migrate when it has a clear equivalent in Bagisto and does not depend on hidden logic. A behavior needs deeper review when it affects product type, attribute structure, channel visibility, inventory source assignment, customer group pricing, cart or catalog rules, checkout behavior, CMS delivery, marketplace functions, B2B permissions, APIs, headless usage, or custom packages.

A useful first-pass approach matrix looks like this:

| Store condition                                                                                                | Likely service direction     | Reason                                                                                  |
| -------------------------------------------------------------------------------------------------------------- | ---------------------------- | --------------------------------------------------------------------------------------- |
| Clean catalog, customers, and orders with limited custom behavior                                              | Standard Service             | Core records can be moved through supported paths.                                      |
| Migration is supported but the team needs planning, coordination, or guided execution                          | Managed Service              | Scope is manageable but requires stronger execution ownership.                          |
| Data needs bounded filtering, mapping, or configuration within supported behavior                              | Add-ons                      | The requirement changes how supported data is selected or mapped.                       |
| Custom fields, unsupported records, app or extension data, custom packages, or bespoke logic must be preserved | Custom Service               | The requirement sits outside ordinary supported migration behavior.                     |
| Target build changes after the first run                                                                       | Additional Migration Options | Follow-up migration must match the last valid configuration or a revised configuration. |

This approach keeps service decisions grounded. It prevents overusing Custom Service for ordinary data cleanup, and it prevents forcing custom requirements into a Standard Service path that cannot preserve the needed behavior.

### When Standard Service Fits Bagisto <a href="#when-standard-service-fits-bagisto" id="when-standard-service-fits-bagisto"></a>

Standard Service fits when the migration scope is clear, the current platform data is clean enough to map into supported Bagisto structures, and the target store does not depend on unsupported custom behavior. For Bagisto, this usually means the merchant needs to move core records such as Products, Categories, Customers, Orders, Reviews, Coupons, CMS Pages, or related supported data without preserving complex extension-owned logic.

Standard Service is strongest when products can be represented through Bagisto’s supported product types and attributes without bespoke transformation. Simple products, well-defined configurable products, clear categories, stable customer groups, clean order history, and manageable CMS content are good signals. The migration can still require careful mapping, but the data does not demand custom engineering.

Standard Service should not be selected blindly. Bagisto’s product, attribute, channel, inventory, and marketing structures can create complexity even when record counts are moderate. Before using Standard Service, confirm:

* product types are known and can be represented in Bagisto;
* attributes and attribute families are clean enough for target-side maintenance;
* categories do not depend on old navigation behavior that must be rebuilt;
* channel and inventory-source assumptions are simple or already defined;
* customer groups do not carry complex pricing or access rules beyond supported handling;
* order history can remain understandable without recreating every old checkout behavior;
* CMS, URL, and marketing records are within the supported scope;
* no essential custom package, API, marketplace, B2B, or headless behavior must be migrated as data.

| Standard Service pass signal                          | Watch signal                                       | Escalation signal                                                           |
| ----------------------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------- |
| Records map cleanly into Bagisto-supported structures | Some field cleanup or mapping decisions are needed | Unsupported custom records or behavior must be preserved                    |
| Product types and attributes are understood           | Attribute families need cleanup                    | Product behavior depends on custom product logic                            |
| Orders can remain historical records                  | Order statuses need mapping                        | Payment, fulfillment, or external references require custom treatment       |
| CMS and SEO scope is defined                          | URL rewrite decisions need review                  | Headless or custom frontend logic consumes migrated content in a custom way |

Standard Service is appropriate when the migration can be completed without turning the project into custom architecture work.

### When Managed Service Fits Bagisto <a href="#when-managed-service-fits-bagisto" id="when-managed-service-fits-bagisto"></a>

Managed Service fits when the migration path is supported but the project needs stronger planning, coordination, review, or execution control. Bagisto projects often reach this point when the data is not highly custom, yet the operating scope includes several moving parts: product types, attributes, attribute families, customer groups, channels, inventory sources, CMS, URL rewrites, marketing rules, tax settings, and launch sequencing.

Managed Service is useful when the merchant needs help turning scattered platform information into a coherent migration scope. It can support decisions such as which product types to test in Demo Migration, how to interpret customer groups, which orders should be sampled, how to separate historical records from live target configuration, and when follow-up migration should be planned.

Managed Service does not mean every custom requirement becomes supported. It gives the project a more controlled execution path. Requirements outside supported migration behavior still need Add-ons or Custom Service. The value of Managed Service is coordination: defining what needs to happen, when to test it, how to interpret results, and what should block Full Migration.

Good Managed Service candidates include:

| Scenario                                                                                | Why Managed Service helps                                                          |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Catalog uses several product types and many attributes                                  | Scope review prevents poor attribute-family and product-type mapping decisions.    |
| Store uses multiple channels or inventory sources                                       | Channel and stock behavior need coordinated target preparation and validation.     |
| Order history contains discounts, refunds, shipments, taxes, and customer group effects | Historical meaning needs review before launch.                                     |
| CMS and SEO records are important to continuity                                         | Content, URL rewrites, search terms, and landing pages need controlled validation. |
| Merchant team has limited migration ownership                                           | Managed coordination reduces missed decisions and late escalation.                 |

Managed Service should be selected when the project is not mainly custom engineering, but it is too important or too interconnected to run as an unmanaged record transfer.

### When Add-ons Should Be Used <a href="#when-add-ons-should-be-used" id="when-add-ons-should-be-used"></a>

Add-ons fit bounded requirements that adjust supported migration behavior. In Bagisto projects, Add-ons are useful when the merchant needs filtering, mapping, or configuration assistance that remains inside the supported scope. They should not be used as a substitute for Custom Service when unsupported records, extension-owned data, custom fields, custom packages, or bespoke logic need special treatment.

Common Bagisto Add-on situations include selecting a defined subset of records, mapping old customer groups into a cleaner target structure, applying controlled field mapping, preparing specific CMS or SEO handling, or supporting configuration-sensitive migration behavior that is still within supported boundaries.

The key test is whether the requirement is bounded and supported:

| Requirement                                                 | Add-on candidate?              | Reason                                                            |
| ----------------------------------------------------------- | ------------------------------ | ----------------------------------------------------------------- |
| Move only selected product categories or customer groups    | Yes                            | Data Filter Add-on may support controlled scoping.                |
| Map old fields into known Bagisto attributes                | Yes, when fields are supported | Advanced Data Mapping can help align fields to target structure.  |
| Adjust supported migration configuration for known entities | Yes                            | Advanced Data Configure can support controlled behavior changes.  |
| Migrate custom package tables into Bagisto                  | No                             | This usually requires Custom Service.                             |
| Preserve a custom product type with bespoke cart behavior   | No                             | Custom behavior needs custom handling or target-side development. |
| Rebuild a headless frontend                                 | No                             | This is implementation work, not a migration Add-on.              |

Add-ons should make the supported migration path more accurate. They should not hide uncertainty. If the team cannot explain what record, field, or configuration is being filtered, mapped, or adjusted, the requirement should be clarified before an Add-on is selected.

### When Custom Service Becomes Necessary <a href="#when-custom-service-becomes-necessary" id="when-custom-service-becomes-necessary"></a>

Custom Service becomes necessary when Bagisto must receive or preserve data and behavior outside ordinary supported migration paths. This is common when the current store includes custom fields, app or extension data, marketplace records, B2B structures, external-system identifiers, custom product types, custom database tables, bespoke checkout logic, API synchronization records, headless storefront dependencies, or Laravel package requirements.

Custom Service should be considered when the requirement cannot be described as ordinary Products, Customers, Orders, Reviews, Coupons, CMS Pages, Blog Posts, or supported configuration. The deciding question is: does the migration need to transform unsupported records or custom behavior into a usable Bagisto structure? If yes, the project needs custom scoping.

Custom Service can involve custom data extraction, custom field handling, custom transformation, custom mapping into Bagisto-compatible structures, or coordination around records that need target-side implementation. It should not be treated as a last-minute rescue. The earlier custom needs are identified, the easier it is to decide whether they should be migrated, rebuilt, replaced, or retired.

| Custom Service trigger                                                                  | Bagisto implication                                                                          |
| --------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Custom product type from the current platform must be preserved                         | Target product behavior may need custom Bagisto product-type handling or a rebuild decision. |
| Extension-created records affect checkout, pricing, shipping, or fulfillment            | Migration must separate historical data from live target configuration.                      |
| Marketplace records include seller, commission, payout, or vendor-specific catalog data | Supported marketplace behavior must be confirmed or custom mapping scoped.                   |
| B2B records include companies, roles, quotes, credit, or requisition behavior           | B2B structure must be reviewed against Bagisto target capability and project scope.          |
| Headless storefront consumes products, CMS, or search through APIs                      | Migration must support the data contract used by the frontend.                               |
| External systems depend on preserved identifiers                                        | Identifier mapping and post-migration synchronization must be validated.                     |

Custom Service is appropriate when preserving business meaning requires more than record transfer and standard configuration.

### How Entity Points Shape Scope Sizing <a href="#how-entity-points-shape-scope-sizing" id="how-entity-points-shape-scope-sizing"></a>

Entity Points help size eligible new Products, Customers, Orders, and Blog Posts. They are useful in Bagisto planning because Bagisto projects can mix ordinary records with complex behavior. Entity Points show part of the scale, but they do not measure every form of complexity.

The duplicate-consumption rule should remain clear: eligible new records consume Entity Points when they are first migrated. Records already counted through the service license do not consume again merely because another action occurs on the same migration path. For example, a product should not consume again only because it also needs mapping or validation on the same migration path.

Entity Points should be used with a second complexity review:

| Scope factor | What Entity Points show | What they do not fully show                                                                     |
| ------------ | ----------------------- | ----------------------------------------------------------------------------------------------- |
| Products     | New product volume      | Product-type complexity, attributes, variants, bundles, or custom behavior                      |
| Customers    | New customer volume     | Customer group pricing, company roles, B2B access, or segmentation rules                        |
| Orders       | New order volume        | Historical payment, tax, shipping, refunds, invoices, shipments, and transaction interpretation |
| Blog Posts   | New blog-post volume    | CMS layout, headless content consumption, redirects, or theme behavior                          |

This distinction prevents under-scoping. A merchant can have a manageable Entity Points count but still require Managed Service, Add-ons, or Custom Service because Bagisto needs product-type planning, channel configuration, custom mapping, or development-aware validation.

### How Demo Migration Evidence Should Change the Approach <a href="#how-demo-migration-evidence-should-change-the-approach" id="how-demo-migration-evidence-should-change-the-approach"></a>

Demo Migration should confirm or challenge the initial service-path choice. It should not be treated as a formality. For Bagisto, Demo Migration is most useful when the sample includes records that test the actual complexity of the target store.

A strong Demo Migration sample includes product-type variety, important attribute families, category and channel assignment, inventory-source cases, customer groups, discounted and refunded orders, CMS Pages, URL rewrites, search behavior, marketing rules, and records touched by extensions, APIs, marketplace layers, B2B structures, headless components, or custom packages.

After Demo Migration, classify findings into three groups:

| Finding type | Meaning                                                                                  | Service-path response                                                |
| ------------ | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Pass         | Records map correctly and remain usable in Bagisto                                       | Continue toward Full Migration with confirmed scope.                 |
| Watch        | Records migrate but require cleanup, mapping, configuration, or stronger validation      | Add Managed Service control or relevant Add-ons.                     |
| Blocking     | Data loses meaning, unsupported records appear, or custom behavior cannot be represented | Escalate to Custom Service or revise the target implementation plan. |

Demo Migration should also test ownership. If a product looks correct in the admin but cannot be purchased correctly, the issue may involve product type, inventory source, channel, pricing, or checkout configuration. If an order imports but loses tax or refund meaning, the issue may be historical interpretation rather than raw order transfer. If CMS content exists but the headless frontend does not consume it correctly, the issue may be frontend implementation or API contract.

The service path should change when Demo Migration evidence changes the risk picture. A project that starts as Standard Service can become Managed Service if coordination gaps appear. An Add-on may become necessary if specific mapping needs are discovered. Custom Service may be required if unsupported records or custom behavior are essential to launch.

### How Additional Migration Options Should Be Chosen <a href="#how-additional-migration-options-should-be-chosen" id="how-additional-migration-options-should-be-chosen"></a>

Additional Migration Options are most useful after an initial migration run, Demo Migration review, or target-side configuration change. Bagisto projects often continue changing while the target store is prepared: new orders arrive, products are edited, customer accounts are created, CMS content changes, marketing rules are adjusted, channels are configured, or integrations are tested.

Choose the follow-up option based on what changed:

| Additional Migration Option                             | Use when                                                          | Bagisto-specific decision cue                                                                                           |
| ------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | New records need to move and the original mapping remains correct | Product types, attributes, channels, inventory sources, and customer groups have not materially changed.                |
| Continue the Migration with a new configuration         | Mapping, filtering, or supported configuration must be adjusted   | Attribute mapping, customer group handling, category selection, or data filters changed after review.                   |
| Perform a new migration                                 | The target build or scope changed too much for continuation       | Bagisto channel structure, product-type plan, custom package handling, or target implementation was materially revised. |

The wrong follow-up choice can create inconsistent target data. Continuing with the old configuration after major mapping changes can preserve old mistakes. Restarting unnecessarily can waste time and disrupt target preparation. The decision should come from evidence: what changed, which records are affected, and whether the prior configuration still represents the approved migration path.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Bagisto migration approach depends on the relationship between data volume, data meaning, target configuration, and custom behavior. Standard Service fits clean supported records. Managed Service fits supported migrations that need stronger planning and coordination. Add-ons fit bounded filtering, mapping, or configuration needs. Custom Service fits unsupported records, custom fields, extension data, custom packages, headless dependencies, marketplace or B2B records, and bespoke transformation logic.

Entity Points help size eligible new Products, Customers, Orders, and Blog Posts, but they do not replace complexity review. Demo Migration should test representative records and change the service path when the evidence requires it. Additional Migration Options should be selected based on whether the last configuration remains valid, needs adjustment, or should be replaced by a new migration run.

A strong Bagisto migration approach is chosen through evidence. It connects record scope, Bagisto structure, target-side configuration, and launch risk before Full Migration begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for Bagisto?**

Standard Service is usually enough when Products, Customers, Orders, CMS Pages, and related supported data can map cleanly into Bagisto without preserving unsupported custom fields, extension-created records, custom product behavior, marketplace records, B2B structures, or headless dependencies.

**When should Managed Service be selected instead?**

Managed Service is appropriate when the migration is supported but requires stronger planning, coordination, scope control, Demo Migration review, and launch sequencing. It is useful for Bagisto stores with product-type variety, attributes, channels, inventory sources, customer groups, CMS, SEO, or marketing rules that need guided decisions.

**What is the difference between Add-ons and Custom Service?**

Add-ons handle bounded filtering, mapping, or configuration within supported migration behavior. Custom Service handles unsupported records, custom fields, app or extension data, custom packages, bespoke transformation, external-system identifiers, and custom logic adjustment.

**Do Entity Points measure Bagisto migration complexity?**

Entity Points help size eligible new Products, Customers, Orders, and Blog Posts. They do not fully measure product-type complexity, attribute-family planning, channel behavior, inventory-source logic, marketplace or B2B data, APIs, headless dependencies, or custom packages.

**How should Demo Migration influence the final approach?**

Demo Migration should test representative complexity. If sample records remain usable in Bagisto, the current path may continue. If mapping gaps or validation issues appear, Managed Service or Add-ons may be needed. If unsupported records or custom behavior are essential, Custom Service should be scoped before Full Migration.
