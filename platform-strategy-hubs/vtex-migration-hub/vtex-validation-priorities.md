# VTEX Validation Priorities

VTEX migration validation should prove that migrated data can support real commerce operations inside VTEX, not only that records arrived. A product may exist but fail review if the SKU cannot be activated, specifications do not support discovery, a trade policy changes availability, pricing is reviewed in the wrong channel, marketplace context is missing, Master Data is incomplete, or external systems cannot reconcile migrated identifiers.

Validation should therefore be organized around proof. Catalog, customer, order, CMS Pages, and Blog Posts checks are still necessary, but they should be tested through the VTEX operating layers that determine whether the migrated store can be used after launch: Catalog, SKUs, specifications, trade policies, pricing, promotions, marketplace and seller operations, OMS, logistics, Master Data, storefront implementation, apps, APIs, integrations, Add-ons, and Custom Service outputs.

For VTEX, a useful validation plan does three things. It confirms baseline transfer accuracy, tests platform-specific behavior, and identifies which exceptions belong to target configuration, Add-ons, Custom Service, or external-system work. This keeps validation practical without reducing VTEX to a simple product/customer/order checklist.

### What VTEX Validation Should Prove <a href="#what-vtex-validation-should-prove" id="what-vtex-validation-should-prove"></a>

VTEX validation should confirm whether migrated records preserve business meaning across connected platform layers. The review should not stop at field comparison. It should test whether the target record can be found, understood, priced, sold, fulfilled, supported, reported, and reconciled by the teams that will operate the store.

| Validation layer             | What to inspect                                                                                                                      | Pass condition                                                                                                   |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Catalog structure            | Products, SKUs, categories, brands, images, specifications, attachments, assembly options, services, kits, and collections.          | Representative products are active, discoverable, commercially understandable, and reviewable by catalog owners. |
| Commercial behavior          | Prices, price tables, promotions, trade policies, sales channels, marketplace context, and B2B/B2C eligibility.                      | Reviewers can explain why each sample is available, unavailable, priced, discounted, or channel-specific.        |
| Marketplace and operations   | Sellers, marketplace order context, OMS status meaning, logistics references, delivery/pickup behavior, and fulfillment identifiers. | Operational teams can read migrated records without losing seller, fulfillment, or external-system context.      |
| Customer and account data    | Customer records, addresses, segmentation, B2B/account relationships, consent indicators, custom fields, and Master Data.            | Customer meaning is preserved beyond basic contact details.                                                      |
| Storefront and content       | Navigation, search, filters, facets, CMS Pages, Blog Posts, landing pages, metadata, redirects, and priority URLs.                   | Migrated data can support launch discovery, content continuity, and SEO-sensitive paths.                         |
| Integrations and custom data | ERP, PIM, WMS, CRM, accounting, marketplace, payment, analytics, middleware, app-owned records, and external IDs.                    | Downstream systems can reconcile migrated records or known exclusions are documented.                            |
| Service-scope outputs        | Add-ons, Custom Service deliverables, Custom Platform interpretation, and accepted exclusions.                                       | Reviewers can separate supported migration results from custom, configured, or externally owned behavior.        |

A VTEX validation plan is complete only when each layer has representative samples, assigned reviewers, expected outcomes, known exclusions, and escalation rules.

### Validate Catalog, SKU, and Specification Outcomes <a href="#validate-catalog-sku-and-specification-outcomes" id="validate-catalog-sku-and-specification-outcomes"></a>

Catalog validation is usually the first proof point because VTEX separates product identity, SKU sellability, category placement, specifications, and commercial visibility. Reviewers should test simple products and complex examples instead of approving only the easiest records.

| Sample to validate                             | What to check                                                                                                 | Why it matters                                                                                              |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Baseline product                               | Product name, description, brand, category, images, SKU, stock, and price.                                    | Confirms ordinary migration accuracy before edge cases are reviewed.                                        |
| Multi-SKU product                              | SKU names, choices, images, prices, stock, and specification values.                                          | Prevents source variants from becoming confusing or inactive VTEX SKUs.                                     |
| Specification-heavy product                    | Product specifications, SKU specifications, filterable values, category-specific groups, and required values. | Validates whether discovery, comparison, compliance, and merchandising data remain usable.                  |
| Category-sensitive product                     | Department, category, subcategory, product-category assignment, and specification behavior by category.       | Category placement affects navigation and the meaning of some specifications.                               |
| Attachment or customization product            | Required input, optional service, personalization, gift wrap, warranty, or configurable add-on behavior.      | Some source choices may require VTEX setup, app behavior, or Custom Service rather than ordinary migration. |
| Assembly, kit, collection, or bundle-like item | Grouped selling logic, component relationships, collection membership, service attachment, or kit behavior.   | Validates whether the result is represented correctly or flagged as a target-side/custom requirement.       |
| Marketplace-relevant SKU                       | Seller identifiers, marketplace association, external SKU, offer context, or channel-specific data.           | Marketplace meaning may not be visible from product fields alone.                                           |

Pass condition: selected catalog samples can be located, reviewed, and approved by catalog, merchandising, storefront, and operations stakeholders without relying on hidden assumptions from the Source Platform.

### Validate Pricing, Promotions, and Trade Policy Behavior <a href="#validate-pricing-promotions-and-trade-policy-behavior" id="validate-pricing-promotions-and-trade-policy-behavior"></a>

VTEX pricing review should test more than base prices. Trade policies, sales channels, marketplace context, B2B/B2C segmentation, promotions, and external pricing systems can change how a migrated SKU behaves after launch. A price that looks correct in one context may be wrong in another.

| Commercial area                   | Validation check                                                                                | Pass condition                                                                             |
| --------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Base price                        | Compare ordinary SKU prices, currencies, rounding, and tax-display assumptions where relevant.  | Baseline prices are accurate for representative products.                                  |
| Price tables and fixed prices     | Review customer-specific, regional, channel, B2B, marketplace, or segmented prices.             | Differentiated prices are preserved, configured, excluded, or assigned to the right owner. |
| Promotions and coupons            | Test active, expired, category, product, customer, cart-value, shipping, and campaign examples. | Promotion history and launch promotion behavior are not confused.                          |
| Trade policies and sales channels | Check whether products, prices, and availability behave correctly across selling contexts.      | Reviewers know which results are migrated data and which are VTEX configuration.           |
| Marketplace pricing               | Check seller, offer, commission, marketplace, and external pricing context where in scope.      | Marketplace pricing expectations are documented and reviewable.                            |
| External price authority          | Identify ERP, PIM, marketplace, pricing engine, or middleware ownership.                        | The migration does not overwrite or misrepresent data owned by another system.             |

Pass condition: pricing reviewers can explain each difference between migrated values, configured VTEX behavior, and externally owned pricing logic.

### Validate Marketplace, OMS, and Logistics Context <a href="#validate-marketplace-oms-and-logistics-context" id="validate-marketplace-oms-and-logistics-context"></a>

VTEX projects often depend on marketplace, seller, order-management, and logistics behavior. Historical orders may migrate, but their meaning can be incomplete if seller references, fulfillment responsibility, delivery method, invoice data, or external-system identifiers are not reviewed.

| Operational area               | What to validate                                                                                               | Pass condition                                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Seller and marketplace context | Seller identifiers, marketplace order references, external IDs, channel context, and offer ownership.          | Marketplace teams can understand which seller or channel the record belongs to.                            |
| OMS status meaning             | Source order statuses, payment status, fulfillment status, cancellation, refund, and return context.           | Operational teams can interpret migrated order history without assuming source status logic still applies. |
| Logistics and fulfillment      | Shipping method, delivery window, pickup point, warehouse, carrier, package, invoice, and tracking references. | Fulfillment evidence remains readable for customer service and operations.                                 |
| Order financial detail         | Items, discounts, tax, shipping, total, payment method, refund, and adjustment data.                           | Finance and support teams can reconcile representative orders.                                             |
| External operations systems    | ERP, WMS, marketplace middleware, accounting, invoice, and customer-service references.                        | Records can be reconciled or documented as outside migration scope.                                        |

Pass condition: order and operational samples can be used for support, reporting, and reconciliation without losing marketplace or fulfillment context.

### Validate Customers, B2B Data, and Master Data <a href="#validate-customers-b2b-data-and-master-data" id="validate-customers-b2b-data-and-master-data"></a>

Customer validation should test account meaning, not only contact transfer. VTEX projects may use Master Data, customer segmentation, custom fields, B2B/account relationships, consent data, app-owned customer records, or external IDs that determine how customers are recognized and served.

| Customer data area           | Validation check                                                                                                  | Pass condition                                                                           |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Core customer record         | Name, email, phone, address, account status, billing/shipping details, and order association.                     | Basic customer history is readable and connected to migrated orders where supported.     |
| B2B or account structure     | Company/account relationship, buyer contacts, roles, approval expectations, or customer segment logic.            | B2B meaning is preserved, rebuilt, excluded, or assigned to Custom Service/target setup. |
| Master Data records          | Custom entities, document schemas, app records, consent fields, loyalty data, or operational customer attributes. | Custom data is migrated, mapped, excluded, or separately scoped with clear ownership.    |
| Segmentation and eligibility | Customer group, price eligibility, promotion eligibility, channel access, or trade-policy relevance.              | Customers are not accidentally treated as one flat audience.                             |
| External IDs                 | ERP, CRM, marketplace, support, accounting, or analytics identifiers.                                             | Downstream systems can recognize migrated customers or known gaps are documented.        |

Pass condition: customer samples preserve the information needed for service, segmentation, account continuity, and downstream reconciliation.

### Validate Storefront, Content, Search, and URL Continuity <a href="#validate-storefront-content-search-and-url-continuity" id="validate-storefront-content-search-and-url-continuity"></a>

VTEX storefront behavior may be implemented through Store Framework, FastStore, headless architecture, storefront apps, search tools, CMS structures, or custom frontend work. Migration validation should confirm that migrated data supports the storefront, while recognizing that frontend implementation is not the same as data migration.

| Storefront area                   | What to validate                                                                                          | Pass condition                                                                                           |
| --------------------------------- | --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Navigation and category discovery | Departments, categories, menus, filters, facets, brand pages, collection pages, and search relevance.     | Priority products are findable through expected discovery paths.                                         |
| Product display                   | Images, descriptions, SKU choices, specifications, attachments, services, and kit/collection information. | Product pages show the right commercial information or gaps are assigned to implementation/custom scope. |
| CMS Pages and Blog Posts          | Page titles, body content, metadata, URLs, links, images, embedded media, and internal navigation.        | Content is readable, linked, and reviewed for launch continuity.                                         |
| SEO-sensitive URLs                | Priority product, category, page, Blog Post, redirect, canonical, and metadata examples.                  | High-value paths are preserved, redirected, or documented for SEO ownership.                             |
| Storefront ownership              | Store Framework, FastStore, headless frontend, custom routes, search apps, and CMS implementation.        | Stakeholders distinguish migrated content/data from frontend build requirements.                         |

Pass condition: migrated records can support storefront discovery and content continuity, and any frontend implementation gaps are assigned to the right owner.

### Validate Apps, APIs, Integrations, and Custom Data <a href="#validate-apps-apis-integrations-and-custom-data" id="validate-apps-apis-integrations-and-custom-data"></a>

VTEX validation should identify data that belongs to apps, APIs, middleware, or external systems. These values may be essential to operations but not suitable for ordinary migration handling. Treating every custom value as a normal field can create misleading approval results.

| Dependency type                     | Validation check                                                                                                      | Pass condition                                                                                    |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| ERP/PIM/WMS/OMS integrations        | Product references, inventory authority, order updates, price ownership, invoice numbers, and fulfillment references. | Integration-critical identifiers are preserved or documented as external-system responsibilities. |
| VTEX IO or storefront apps          | App-owned data, storefront blocks, custom product behavior, search apps, payment apps, and marketplace apps.          | App-dependent behavior is reviewed separately from migrated records.                              |
| API-owned objects                   | Data created or maintained through API workflows, middleware, or custom services.                                     | Ownership and migration feasibility are clear before approval.                                    |
| Custom fields and external IDs      | Source custom fields, Custom Platform fields, external IDs, and integration keys.                                     | Values are mapped, excluded, handled through Add-ons, or escalated to Custom Service.             |
| Custom checkout or order attributes | Gift notes, delivery preferences, loyalty references, tax IDs, marketplace references, or B2B approval values.        | Checkout and order custom meaning remains usable or is documented as outside standard scope.      |

Pass condition: custom and integration-dependent data does not disappear into vague approval language. Each important value has a clear migration, configuration, Custom Service, or exclusion decision.

### Validate Add-ons and Custom Service Outputs <a href="#validate-add-ons-and-custom-service-outputs" id="validate-add-ons-and-custom-service-outputs"></a>

Add-ons and Custom Service outputs should receive explicit validation because they are usually tied to project-specific decisions. A result can pass baseline migration checks while failing the additional logic the customer purchased or requested.

| Scope area              | What to validate                                                                                                                                  | Pass condition                                                                                   |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Data Filter Add-on      | Selected records, excluded records, date ranges, status filters, product/customer/order groups, and other supported filters.                      | Included and excluded samples match the approved filter rule.                                    |
| Advanced Data Mapping   | Supported mapped fields, target values, specification fields, customer fields, order fields, CMS Pages, Blog Posts, or identifiers.               | Mapped values appear in the expected target fields and remain reviewable.                        |
| Advanced Data Configure | Configured values, adjusted names, statuses, categories, field values, or supported transformations.                                              | Configured values match the approved rule without creating unintended side effects.              |
| Custom Add-ons          | Bounded custom handling agreed for a specific need.                                                                                               | The custom result matches the accepted scope and is tested with representative samples.          |
| Custom Service          | Custom Platform interpretation, unsupported data handling, bespoke transformation, external-system logic, or project-specific migration behavior. | Accepted custom requirements are demonstrably met, or exceptions are documented before approval. |

Pass condition: reviewers can verify the exact added value of each Add-on or Custom Service item rather than assuming it passed because the general migration passed.

### Validate Demo Migration Before Full Migration <a href="#validate-demo-migration-before-full-migration" id="validate-demo-migration-before-full-migration"></a>

Demo Migration should be used as an evidence checkpoint. It should test representative VTEX complexity before Full Migration, not only prove that a few ordinary records can move.

| Demo Migration sample group | Include                                                                                                  | Approval question                                                        |
| --------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Simple baseline records     | Ordinary products, customers, orders, CMS Pages, and Blog Posts.                                         | Does the migration produce a clean baseline result?                      |
| Catalog complexity          | Multi-SKU products, specifications, images, categories, attachments, services, kits, and collections.    | Does the target catalog preserve commercial meaning?                     |
| Commercial behavior         | Price examples, promotions, trade policies, marketplace context, and channel-sensitive samples.          | Are price and availability expectations clear enough for Full Migration? |
| Operational records         | Orders, statuses, fulfillment references, invoices, returns, and external IDs.                           | Can support and operations teams read the migrated history?              |
| Customer and Master Data    | Customer profiles, B2B/account examples, custom fields, consent values, and external references.         | Does customer meaning survive beyond basic account transfer?             |
| Storefront/content          | Priority pages, Blog Posts, product URLs, category URLs, redirects, metadata, and search/facet examples. | Will launch-critical discovery and content paths be testable?            |
| Custom scope                | Add-ons, Custom Service samples, app-owned records, and integration-dependent values.                    | Are special requirements proven before Full Migration approval?          |

Pass condition: Demo Migration creates enough evidence to approve, adjust, or rescope the Full Migration with confidence.

### Validate Full Migration Acceptance <a href="#validate-full-migration-acceptance" id="validate-full-migration-acceptance"></a>

Full Migration acceptance should compare the approved Demo Migration standard against the full migrated dataset. The review should confirm that known decisions held at scale and that new edge cases did not appear during the full data movement.

| Full Migration review area | What to confirm                                                                                                 | Pass condition                                                                                           |
| -------------------------- | --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Completeness               | Expected products, SKUs, customers, orders, CMS Pages, Blog Posts, and other scoped records are present.        | Missing records are explained by approved filters, exclusions, unsupported scope, or source data issues. |
| Consistency                | Sample decisions from Demo Migration remain valid at larger scale.                                              | Similar data behaves consistently across the full dataset.                                               |
| Exceptions                 | Failed, partial, or unusual records are logged and assigned.                                                    | Exceptions have owners and do not block launch-critical approval without visibility.                     |
| Business readiness         | Catalog, pricing, operations, customer service, storefront, and integration stakeholders approve their samples. | Approval is based on business usability, not only technical transfer.                                    |
| Launch handoff             | Remaining configuration, storefront, integration, and custom tasks are separated from migration acceptance.     | Teams know what is complete, what remains, and what is outside migration scope.                          |

Pass condition: stakeholders can approve the migrated dataset with a shared understanding of what passed, what was excluded, and what still belongs to target setup or external implementation.

### Revalidate After Additional Migration Options <a href="#revalidate-after-additional-migration-options" id="revalidate-after-additional-migration-options"></a>

Additional Migration Options can help handle later data movement on the same migration path, but they should not reduce validation discipline. The main risk is assuming that previous approval covers records, configurations, or business changes that were not part of the original accepted result.

| Follow-up validation area         | What to recheck                                                                                                        | Pass condition                                                                                                                                                                                                                |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| New eligible records              | New products, customers, orders, CMS Pages, Blog Posts, and other supported records added after the earlier migration. | New records are validated as first-time migrated records.                                                                                                                                                                     |
| Changed catalog behavior          | Updated SKUs, specifications, categories, prices, inventory, or storefront-sensitive values.                           | Changes do not break previously accepted VTEX behavior.                                                                                                                                                                       |
| Changed business rules            | New trade policies, promotions, marketplace relationships, seller rules, or logistics expectations.                    | Reviewers confirm whether migration, target setup, or external systems own the change.                                                                                                                                        |
| Add-ons or Custom Service changes | New filters, mappings, configurations, custom fields, or bespoke logic.                                                | Special handling is validated again, not assumed from the earlier run.                                                                                                                                                        |
| Entity Points review              | New Product, Customer, Order, or Blog Posts records that are migrated for the first time.                              | Records already counted through the service license do not consume Entity Points again simply because another migration action is performed; new eligible records may consume Entity Points when migrated for the first time. |

Pass condition: every follow-up migration review distinguishes previously approved records from new or changed data that requires fresh validation.

### VTEX Validation Priority Matrix <a href="#vtex-validation-priority-matrix" id="vtex-validation-priority-matrix"></a>

Use the matrix below to decide where to spend review time first. The best validation plan prioritizes the records and behaviors most likely to affect launch, revenue, operations, support, SEO, or downstream systems.

| Priority    | Validation focus                                                                                                         | Review owner                                                       | Why it matters                                                           |
| ----------- | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Highest     | Catalog/SKU activation, specifications, price/trade policy behavior, checkout-critical values, and launch-critical URLs. | Catalog, merchandising, pricing, storefront, and SEO teams.        | These issues can block buying, discovery, or launch approval.            |
| High        | Marketplace/seller context, OMS/logistics records, customer/account data, Master Data, and external IDs.                 | Operations, support, marketplace, integration, and customer teams. | These issues affect fulfillment, support, reporting, and reconciliation. |
| Medium      | CMS Pages, Blog Posts, historical promotions, older orders, non-critical redirects, and secondary content.               | Content, SEO, and support teams.                                   | These issues affect continuity but may not block launch if documented.   |
| Conditional | App-owned records, custom checkout values, bespoke integration fields, and Custom Platform data.                         | Technical, app, integration, and Custom Service stakeholders.      | These items require ownership decisions before they can be accepted.     |

A strong validation process creates a shared approval trail. It does not try to validate every record with equal intensity; it validates the right records deeply enough to protect launch quality.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX validation should prove that migrated data works inside the target operating model. Catalog records, SKUs, specifications, pricing, trade policies, marketplace context, OMS, logistics, Master Data, storefront content, integrations, Add-ons, and Custom Service outputs should each be reviewed through their business purpose.

The safest approval process starts with representative Demo Migration samples, turns those samples into pass conditions, applies those conditions during Full Migration, and repeats relevant checks after Additional Migration Options when new or changed data is involved. This gives VTEX stakeholders a practical basis for accepting the migration result without confusing migrated records, target configuration, frontend implementation, and external-system behavior.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first in a VTEX migration?**

Start with the records and behaviors that affect launch usability: products, SKUs, specifications, prices, trade policies, priority categories, customer/order samples, checkout-sensitive data, storefront discovery, and high-value URLs. Lower-priority historical or content records can be reviewed after launch-critical behavior is proven.

**Is record count enough to validate a VTEX migration?**

No. Record count confirms only presence. VTEX validation should also prove whether records behave correctly across Catalog, SKUs, specifications, pricing, promotions, trade policies, marketplace operations, OMS, logistics, Master Data, storefront implementation, and integrations.

**Should Demo Migration include complex VTEX cases?**

Yes. Demo Migration should include ordinary records and difficult samples. Multi-SKU products, specification-heavy items, marketplace-relevant orders, Master Data examples, custom fields, Add-on outputs, and Custom Service samples are often more useful than simple baseline records.

**How should Add-ons be validated for VTEX?**

Validate Add-ons against the approved rule or scope. For example, Data Filter Add-on should be checked through included and excluded records, while Advanced Data Mapping should be checked through source values appearing in the expected target fields. Add-ons should not be treated as full Custom Service unless the accepted scope says so.

**Do Additional Migration Options require another validation pass?**

Yes. Additional Migration Options should trigger focused revalidation for new records, changed records, changed business rules, Add-ons, Custom Service outputs, and Entity Points impact. Previously approved records should not be assumed to cover new or changed VTEX behavior.
