# VTEX Validation Priorities

VTEX validation should prove that migrated data can support a connected commerce operation, not only that records were transferred. A product that appears in the catalog may still fail launch review if the SKU is not sellable, specifications do not support discovery, pricing is checked outside the correct commercial context, marketplace or seller ownership is unclear, Master Data relationships are incomplete, or integrations cannot reconcile migrated identifiers.

The strongest validation approach reviews VTEX as a set of operating layers. Catalog, SKUs, prices, promotions, customer records, orders, logistics, storefront presentation, search, Master Data, marketplace context, and external systems should be tested through representative examples. Validation should separate migrated data from target-side VTEX configuration and from records that belong to external systems or Custom Service scope.

### Define the Validation Standard Before Reviewing Records <a href="#define-the-validation-standard-before-reviewing-records" id="define-the-validation-standard-before-reviewing-records"></a>

VTEX validation should start with a written standard for what a pass means. A simple count match is useful, but it cannot prove whether a migrated store is operationally ready. The review should define who approves each area, what samples must pass, what differences are acceptable, and which findings require correction, configuration, Add-ons, Custom Service review, or external-system ownership.

| Validation question              | VTEX proof required                                                                                                                                                 |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Are records present?             | Products, SKUs, customers, orders, categories, images, CMS Pages, Blog Posts, and supported related data appear where expected.                                     |
| Do records preserve meaning?     | SKUs, specifications, brands, categories, prices, promotions, sellers, fulfillment context, and customer relationships retain their intended role.                  |
| Can teams operate the result?    | Merchandising, marketplace, operations, customer service, finance, and integration owners can understand and use representative samples.                            |
| Are target-side tasks separated? | Checkout, payments, logistics rules, sellers, trade policies, search behavior, storefront implementation, and live integrations are not mistaken for migrated data. |
| Are service-scope outputs clear? | Add-ons, Custom Service outputs, accepted exclusions, and manual cleanup items are assigned before launch.                                                          |

The validation standard should prevent three common mistakes: approving only record volume, reviewing only clean examples, and mixing migration issues with unfinished VTEX configuration.

### Validate Catalog, SKUs, and Specification Meaning <a href="#validate-catalog-skus-and-specification-meaning" id="validate-catalog-skus-and-specification-meaning"></a>

Catalog validation is usually the first VTEX proof point because the product record alone does not represent the full commercial item. VTEX catalog review should confirm product identity, SKU sellability, category placement, brand consistency, images, specifications, attachments or services where relevant, and any relationship between catalog structure and search or storefront behavior.

A strong sample set includes ordinary products and difficult catalog examples. Review simple items, multi-SKU products, specification-heavy products, category-sensitive products, products with images, products connected to services or attachments, marketplace-relevant SKUs, and products whose source behavior depended on custom options or external catalog systems.

| Sample type                   | What to inspect                                                                                   | Why it matters                                                                                      |
| ----------------------------- | ------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Simple product                | Product name, brand, category, description, images, SKU, price, and stock reference.              | Confirms baseline migration accuracy.                                                               |
| Multi-SKU product             | SKU identity, choices, image association, specification values, availability, and pricing.        | Prevents source variants from becoming confusing VTEX SKUs.                                         |
| Specification-heavy product   | Product and SKU specifications, filterable values, required fields, and category-specific groups. | Protects discovery, comparison, compliance, and merchandising.                                      |
| Service or attachment product | Required buyer input, warranty, gift wrap, personalization, or service selection.                 | Reveals whether behavior belongs to migration, VTEX configuration, app behavior, or Custom Service. |
| Marketplace-relevant SKU      | Seller, offer, external SKU, marketplace association, channel context, and availability.          | Preserves seller or channel meaning beyond the catalog field set.                                   |

Pass condition: catalog stakeholders can locate representative products, understand SKU structure, confirm specifications, identify accepted exceptions, and explain what still belongs to target-side setup or external systems.

### Validate Pricing, Promotions, and Commercial Context <a href="#validate-pricing-promotions-and-commercial-context" id="validate-pricing-promotions-and-commercial-context"></a>

VTEX pricing validation should not stop at base price. Many VTEX projects depend on differentiated commercial behavior: price tables, fixed prices, promotions, coupons, seller pricing, B2B pricing, customer or region-specific pricing, trade policies, and external price authorities. A price may appear correct in one context while being wrong in the buying context that matters after launch.

Validation should select SKUs that expose the commercial logic. Include ordinary products, discounted products, products with customer-specific or channel-specific prices, marketplace offers, B2B examples, and products whose prices are controlled by ERP, PIM, marketplace middleware, or pricing engines.

| Commercial area               | Validation focus                                                                | Handling path when results differ                              |
| ----------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Base price                    | SKU price, currency, rounding, and tax-display assumptions where relevant.      | Migration correction or accepted difference.                   |
| Price table or fixed price    | Customer, segment, region, channel, B2B, or seller-specific values.             | VTEX setup, Add-on, Custom Service, or external-system review. |
| Promotions and coupons        | Active, expired, category, product, cart-value, shipping, or campaign examples. | Separate migrated history from live promotion setup.           |
| Trade policy or sales channel | Product availability, price behavior, and context-specific sellability.         | VTEX configuration or revalidation after setup.                |
| External price authority      | ERP, marketplace, PIM, middleware, or pricing-engine ownership.                 | Integration owner confirmation before launch.                  |

Pass condition: reviewers can explain each commercial difference as migrated data, VTEX configuration, external ownership, Add-on output, Custom Service output, accepted exclusion, or launch blocker.

### Validate Marketplace, Seller, OMS, and Logistics Evidence <a href="#validate-marketplace-seller-oms-and-logistics-evidence" id="validate-marketplace-seller-oms-and-logistics-evidence"></a>

VTEX validation should protect marketplace and operations meaning when those areas are in scope. A migrated order can contain line items and totals but still be weak if seller ownership, marketplace order reference, fulfillment responsibility, invoice data, delivery method, pickup point, warehouse, carrier, tracking reference, or external order identifier is missing or unclear.

Marketplace and operations samples should be chosen by business use, not only by date. Include ordinary orders, seller-specific orders, marketplace orders, cancelled orders, refunded orders, orders with multiple packages, orders with shipping or pickup context, and orders tied to external systems.

| Operational area               | What to validate                                                                                           | Pass condition                                                                                 |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Seller and marketplace context | Seller ID, offer context, marketplace reference, external SKU, channel, and order ownership.               | Marketplace teams understand which seller or channel the record belongs to.                    |
| OMS status meaning             | Payment, cancellation, refund, fulfillment, return, and status progression examples.                       | Support teams can interpret history without assuming source statuses behave the same in VTEX.  |
| Logistics evidence             | Warehouse, carrier, shipping method, delivery window, pickup point, package, invoice, and tracking values. | Fulfillment history is readable and reconciled with expected operational records.              |
| Financial details              | Items, discounts, tax, shipping, payment label, refund, adjustment, and total.                             | Finance and support teams can review representative order history.                             |
| External references            | ERP, WMS, accounting, marketplace, invoice, customer-service, or middleware identifiers.                   | External-system traceability is preserved, customized, excluded, or assigned to another owner. |

Pass condition: operational reviewers can use migrated samples for support, reconciliation, and launch decisions without returning to the Source Platform for basic meaning.

### Validate Customers, B2B Records, and Master Data <a href="#validate-customers-b2b-records-and-master-data" id="validate-customers-b2b-records-and-master-data"></a>

Customer validation should confirm identity and operating context, not only contact fields. VTEX projects may involve customer profiles, addresses, segmentation, consent values, B2B account relationships, approval workflows, app-owned customer data, Master Data objects, CRM references, loyalty IDs, or ERP identifiers. Some of those values may belong in supported migration scope, while others require Add-ons, Custom Service, external integration work, or accepted exclusion.

The sample set should include ordinary customers, repeat buyers, guest buyers, duplicate contacts, B2B accounts where relevant, customers with multiple addresses, customers tied to historical orders, and customers with custom fields or external IDs.

| Customer area      | What to prove                                                                                                     |
| ------------------ | ----------------------------------------------------------------------------------------------------------------- |
| Core profile       | Name, email, phone, addresses, customer-order association, and account status remain readable.                    |
| Buyer identity     | Guest, repeat, registered, B2B, and segmented customers are not flattened into indistinct contacts.               |
| Custom fields      | Loyalty IDs, ERP references, CRM values, consent fields, or account notes are classified correctly.               |
| Master Data        | Custom objects, relationships, and required fields are migrated, rebuilt, excluded, or scoped for Custom Service. |
| External ownership | CRM, ERP, loyalty, middleware, marketplace, or analytics owners can reconcile required identifiers.               |

Pass condition: customer and Master Data samples support the intended post-launch use case, and unsupported custom-data expectations are not hidden inside generic customer approval.

### Validate Storefront, Search, URLs, and Content Continuity <a href="#validate-storefront-search-urls-and-content-continuity" id="validate-storefront-search-urls-and-content-continuity"></a>

VTEX storefront validation should be separate from data-presence validation. Migrated catalog records may exist while the storefront still needs implementation work, search configuration, navigation setup, redirect planning, CMS content review, metadata updates, or external SEO decisions. The validation should confirm what the migrated data can support and what remains a storefront or launch task.

High-value storefront samples should include top products, top categories, search terms, filters, landing pages, CMS Pages, Blog Posts, product URLs, category URLs, metadata, redirects, and examples affected by multiple channels or marketplaces.

| Storefront area           | Validation focus                                                                                                                       |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Product pages             | Product content, images, SKU selection, specifications, availability, price, and add-to-cart path.                                     |
| Search and filters        | Search terms, category navigation, brand filters, specification facets, and sorting behavior.                                          |
| URLs and redirects        | Important old URLs, target URL structure, redirect ownership, and SEO-sensitive paths.                                                 |
| CMS Pages and Blog Posts  | Content that should migrate, be rebuilt, redirected, consolidated, or intentionally retired.                                           |
| Storefront implementation | Whether missing behavior belongs to migration output, VTEX configuration, storefront development, app behavior, or manual launch work. |

Pass condition: search, navigation, content, and URL samples support launch continuity, and remaining storefront work is assigned rather than treated as migration failure.

### Validate Integrations, Apps, and Custom Scope Outputs <a href="#validate-integrations-apps-and-custom-scope-outputs" id="validate-integrations-apps-and-custom-scope-outputs"></a>

VTEX migration validation should include the systems that make migrated data useful: ERP, PIM, WMS, OMS middleware, CRM, loyalty, marketplace connectors, pricing engines, payment providers, analytics, search tools, storefront apps, and custom VTEX IO apps. The review should identify which identifiers and relationships must survive migration and which are rebuilt by integration setup.

Add-ons and Custom Service should remain clearly separated. Add-ons are suitable for bounded filtering, mapping, or configuration within supported migration behavior. Custom Service is appropriate when unsupported records, bespoke fields, Master Data objects, external identifiers, Custom Platform interpretation, or custom migration logic adjustment must be evaluated.

| Finding                                                                         | Likely handling path                                      |
| ------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Supported field needs better mapping                                            | Add-on, if the destination and behavior remain supported. |
| Supported records need filtering                                                | Add-on or scoped configuration decision.                  |
| App-owned or custom records are business-critical                               | Custom Service review.                                    |
| External IDs are required for ERP, PIM, CRM, WMS, or marketplace reconciliation | Custom Service or integration-owner review.               |
| Live provider setup is incomplete                                               | VTEX target-side setup, not migration acceptance.         |

Pass condition: integration owners can reconcile key records or formally accept exclusions, and custom-scope outputs have defined acceptance criteria.

### Validate Later Migration Activity Before Launch <a href="#validate-later-migration-activity-before-launch" id="validate-later-migration-activity-before-launch"></a>

VTEX launches may involve a period between the first migration run and go-live while the Source Platform continues receiving products, customers, orders, content, or catalog changes. Validation should define whether the next action continues migration activity with the previous configuration, continues with adjusted configuration, or performs a new migration into a refreshed target result.

Each action changes the review burden. Continuing with the last used configuration emphasizes newly added records and representative regression samples. Continuing with a new configuration requires validation of the changed mapping, filtering, or output behavior. Performing a new migration requires broader target review because earlier migrated results may be replaced.

Entity Points should be interpreted consistently. New eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

Pass condition: launch-window migration activity has a clear action, expected target effect, validation owner, sample plan, and Entity Points interpretation before execution.

### Build a VTEX Validation Report <a href="#build-a-vtex-validation-report" id="build-a-vtex-validation-report"></a>

A validation report should convert findings into launch decisions. It should not be a screenshot collection or a loose issue list. Each finding should show what was tested, what was expected, what happened, who owns the next action, and whether launch is affected.

| Report field    | Purpose                                                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Sample record   | Identifies the product, SKU, customer, order, page, URL, Master Data object, or integration sample.                                  |
| Expected result | Defines what should appear or be usable in VTEX.                                                                                     |
| Observed result | Records what reviewers found.                                                                                                        |
| Severity        | Separates launch blockers from cleanup or accepted limitations.                                                                      |
| Handling path   | Migration correction, VTEX setup, Add-on adjustment, Custom Service review, integration work, manual cleanup, or accepted exclusion. |
| Owner           | Assigns responsibility to the merchant, Next-Cart, VTEX implementation team, external partner, or system owner.                      |
| Final status    | Open, corrected, accepted, deferred, or excluded.                                                                                    |

Pass condition: stakeholders can use the report to approve, correct, defer, or re-scope the migration result without reopening the same questions repeatedly.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX validation should prove that migrated data works inside a connected commerce environment. The review should cover catalog, SKUs, specifications, pricing, promotions, sellers, marketplace context, OMS, logistics, customers, B2B records, Master Data, storefront search, URLs, content, integrations, Add-ons, Custom Service outputs, and later migration actions.

The safest validation process uses representative samples, role-specific reviewers, explicit pass conditions, and clear ownership for every finding. A VTEX migration should be approved because the result is usable for commerce operation, not only because records are present.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is record-count matching enough to validate a VTEX migration?**

No. Record counts help confirm baseline presence, but VTEX validation must also prove SKU sellability, specifications, pricing context, marketplace or seller meaning, order readability, Master Data scope, storefront behavior, and integration reconciliation.

**Should VTEX storefront validation be separate from catalog validation?**

Yes. Catalog validation proves data structure and SKU meaning. Storefront validation proves customer-facing search, filters, navigation, URLs, content, availability, pricing display, and checkout entry behavior.

**What VTEX records need the strongest validation samples?**

Prioritize complex SKUs, specification-heavy products, channel-specific prices, marketplace or seller records, historical orders with operational references, customers with custom fields, Master Data objects, and high-value storefront URLs.

**How should custom VTEX data be validated?**

Custom data should be validated through explicit samples and ownership. Supported mapping may use Add-ons, while Master Data objects, app-owned records, external identifiers, and bespoke transformations may require Custom Service or integration-owner review.

**Does later migration activity change VTEX validation?**

Yes. Continuing with the same configuration, continuing with a new configuration, and performing a new migration each require different validation emphasis. The team should define expected target effect, samples, owners, and Entity Points interpretation before the action runs.
