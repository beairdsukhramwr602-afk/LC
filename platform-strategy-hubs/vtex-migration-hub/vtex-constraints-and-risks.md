# VTEX Constraints and Risks

VTEX migration risk is structural because the target environment connects catalog, SKUs, specifications, pricing, promotions, checkout, orders, logistics, marketplace operations, Master Data, storefront implementation, and external systems. A migration can appear successful when records are present, yet still fail if products are not purchasable, specifications do not support discovery, seller context is lost, pricing behavior is misread, or order history is confused with live operational setup.

Risk control should not begin with a generic warning list. It should begin by identifying which source assumptions may break when interpreted through VTEX. A field that worked inside the source store may belong to VTEX catalog, a price table, Master Data, an integration, a custom front end, or no target structure at all. The migration plan should name those constraints before Full Migration, not after launch review.

### VTEX Risk Comes From Relationship Gaps <a href="#vtex-risk-comes-from-relationship-gaps" id="vtex-risk-comes-from-relationship-gaps"></a>

VTEX risk usually appears between records rather than inside one record type. A product record depends on SKU structure. SKU availability depends on inventory and logistics. Pricing may depend on sales channels, price tables, promotions, or external systems. Orders may depend on checkout, payment, fulfillment, seller context, and historical status interpretation. Storefront behavior may depend on specifications, search, CMS components, routing, and custom implementation.

That means a simple completeness review is not enough. The merchant should ask whether migrated data still carries the relationships needed for the target operation.

| Relationship gap      | What can break in VTEX                                                | Risk control                                                                             |
| --------------------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Product to SKU        | Products exist but cannot be purchased correctly.                     | Validate simple, multi-SKU, option-heavy, and inventory-sensitive examples.              |
| SKU to specifications | Filters, product detail, search, or comparison lose useful structure. | Normalize values by purpose and category relevance.                                      |
| SKU to price/channel  | Prices work in one context but fail in another.                       | Test representative sales channels, customer contexts, and pricing scenarios.            |
| Order to fulfillment  | History exists but staff cannot interpret delivery or seller context. | Review refunded, cancelled, marketplace, and multi-fulfillment examples.                 |
| Content to storefront | Data migrates but the customer journey remains incomplete.            | Separate data migration from storefront implementation, redirects, and search readiness. |

The strongest mitigation is early sample design. Samples should represent the business model, not only easy records.

### Catalog and SKU Structure Can Fail Without Looking Empty <a href="#catalog-and-sku-structure-can-fail-without-looking-empty" id="catalog-and-sku-structure-can-fail-without-looking-empty"></a>

The most common VTEX catalog risk is a false completeness signal. Products may migrate, categories may exist, and SKUs may appear, but shoppers or staff may still face wrong choices, inactive items, missing specifications, inaccurate images, broken discoverability, or incomplete purchasing paths.

This risk is highest when the source store uses configurable products, variant-heavy products, bundles, product builders, marketplace listings, subscription options, custom add-ons, or app-managed attributes. Those structures should not be forced into VTEX as ordinary catalog fields without deciding what each choice controls.

| Source assumption                                    | VTEX constraint                                                                  | Migration consequence                                                      | Mitigation cue                                                                 | Validation signal                                               |
| ---------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------- |
| Every source option should become a SKU.             | SKUs should represent sellable units or versions.                                | Catalog becomes over-split, hard to manage, or commercially confusing.     | Classify each option by price, stock, logistics, display, and customer choice. | Representative products show correct purchasable SKU behavior.  |
| Product attributes can move as plain text.           | Specifications may support filtering, detail, comparison, and category behavior. | Search and discovery weaken even though product pages contain information. | Review specification purpose before mapping.                                   | Filter and product-detail examples match business expectations. |
| Category paths are only admin organization.          | Categories may affect storefront navigation, search, and SEO continuity.         | Catalog grouping migrates but customer discovery remains incomplete.       | Separate catalog category, navigation, and URL/redirect decisions.             | Priority category journeys can be tested after migration.       |
| Bundles and configurable kits are ordinary products. | Component logic may depend on pricing, inventory, or storefront implementation.  | Bundles appear but do not behave as expected.                              | Escalate bundle-like behavior to setup, integration, or Custom Service review. | Bundle examples have an accepted target handling path.          |

Catalog risk should be reviewed before Article 6 service-path decisions are accepted. Otherwise the chosen service path may be too light for the actual product structure.

### Specification and Search Risk Can Damage Discovery <a href="#specification-and-search-risk-can-damage-discovery" id="specification-and-search-risk-can-damage-discovery"></a>

Specifications are a high-impact VTEX risk area because they can shape filtering, search, category browsing, comparison, and product-detail quality. Source attributes are often inconsistent: duplicate values, mixed units, old labels, app-generated fields, category-specific attributes used globally, or descriptive values mixed with variant-defining values.

If those values are mapped mechanically, VTEX can inherit a messy catalog. If they are dropped too aggressively, shoppers may lose search and filter paths that drive conversion. The migration plan should distinguish values that support customer discovery from values that support operations, compliance, integrations, or historical reference.

| Warning sign                                                    | Why it matters                                                | Prevention                                                                        |
| --------------------------------------------------------------- | ------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Many near-duplicate attribute values exist in the source store. | Filters can become noisy or misleading.                       | Normalize or exclude low-value values before accepting mapping.                   |
| Category-specific values are used across unrelated products.    | Specifications may appear in the wrong browsing context.      | Review representative categories separately.                                      |
| Variant-defining and descriptive fields are mixed.              | SKU selection and product information may blur.               | Decide whether the value defines a purchasable version or describes the product.  |
| Search behavior depends on tags or app fields.                  | Product discovery may not survive ordinary catalog migration. | Identify search-critical fields before scope approval.                            |
| Operational fields are visible to shoppers in the source store. | Target storefront may inherit clutter.                        | Define which fields belong to storefront, back office, integration, or exclusion. |

The pass condition is not that every source attribute appears in VTEX. The pass condition is that product discovery and product understanding remain useful without carrying unnecessary source-platform noise.

### Commercial Logic Risk Sits Outside Simple Price Migration <a href="#commercial-logic-risk-sits-outside-simple-price-migration" id="commercial-logic-risk-sits-outside-simple-price-migration"></a>

VTEX commercial behavior may involve base SKU prices, price tables, sales-channel conditions, promotions, coupons, B2B rules, marketplace seller prices, and external pricing systems. A source platform may store those rules in product fields, customer groups, catalogs, scripts, apps, modules, ERP feeds, or marketplace integrations. Treating them as simple product data creates risk.

The merchant should separate four questions: what prices should appear at launch, what historical price data must remain readable, what commercial rules must be configured in VTEX, and what values are owned by external systems. Without that separation, a migrated price can look correct in a sample while failing in a channel, region, customer segment, or marketplace scenario.

| Commercial risk                                            | Example                                                       | Safer handling                                                               |
| ---------------------------------------------------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Default price hides channel-specific pricing.              | One SKU has different B2B, marketplace, or regional prices.   | Test multiple commercial contexts, not only the base SKU price.              |
| Promotion history is confused with active promotion setup. | Old coupon records exist but launch rules are not configured. | Separate historical order context from active promotion behavior.            |
| External pricing system remains the system of record.      | ERP overwrites launch prices after go-live.                   | Define ownership and synchronization timing.                                 |
| Seller price is treated as product price.                  | Marketplace offer logic is flattened.                         | Identify seller-owned prices and marketplace responsibilities.               |
| Tax or payment assumptions are inferred from old orders.   | Live checkout behaves differently from history.               | Configure and test VTEX-side tax, payment, and checkout behavior separately. |

Commercial risk should be reviewed with real business examples. The most useful samples are rarely the simplest SKUs; they are products with differentiated pricing, active promotions, channel rules, seller context, or external-system ownership.

### Marketplace, Seller, and Operational Ownership Risk <a href="#marketplace-seller-and-operational-ownership-risk" id="marketplace-seller-and-operational-ownership-risk"></a>

VTEX marketplace and seller-related data can create serious migration ambiguity. A source marketplace may have seller ownership, commissions, offer relationships, product matching, inventory ownership, seller fulfillment, channel pricing, split orders, or marketplace governance rules. Some of this information may be historical context. Some may need active configuration. Some may belong to external marketplace, ERP, OMS, or middleware systems.

The risk appears when seller context is flattened into product or order fields. A migrated product may lose who owns the offer. A historical order may lose seller or fulfillment meaning. A marketplace catalog may migrate as products without preserving relationships needed for operations.

| Marketplace area               | What goes wrong                                                  | Risk control                                                                    |
| ------------------------------ | ---------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Seller records                 | Seller identity is treated as a product label.                   | Decide whether seller context is historical, operational, or integration-owned. |
| Offers                         | Offer relationships are flattened into catalog data.             | Review product-to-offer and seller-to-SKU examples.                             |
| Marketplace orders             | Split fulfillment, seller status, or seller references are lost. | Validate marketplace order examples separately from ordinary orders.            |
| Commission or governance logic | Business rules are assumed to migrate as records.                | Treat rules as setup, integration, or Custom Service candidates.                |
| External marketplace IDs       | Reconciliation loses continuity.                                 | Preserve only identifiers needed for reporting, support, or integrations.       |

Marketplace risk should be scoped before migration execution. If seller or offer behavior is launch-critical, it should not be hidden inside ordinary catalog or order migration assumptions.

### Checkout, Orders, OMS, Logistics, and Payments Need Separate Validation Paths <a href="#checkout-orders-oms-logistics-and-payments-need-separate-validation-paths" id="checkout-orders-oms-logistics-and-payments-need-separate-validation-paths"></a>

Order history and operational readiness are different VTEX concerns. Migrated orders can help staff understand past purchases, refunds, cancellations, taxes, payment references, fulfillment status, customer links, and seller context. Live VTEX operation depends on checkout behavior, payment providers, fraud controls, logistics setup, warehouses, pickup points, shipping rates, inventory updates, and order orchestration.

A common risk is approving migrated order history as if it proves launch readiness. Historical data can be readable while new checkout flows are still untested. A migrated fulfillment status can preserve support context while live logistics rules remain incomplete.

| Area                 | Migration risk                                                             | Validation direction                                                                          |
| -------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Checkout fields      | Custom values may be missing, misplaced, or unsupported.                   | Decide whether each field belongs to history, checkout setup, Master Data, or Custom Service. |
| Payment references   | Historical labels are mistaken for live payment configuration.             | Treat old payments as context and test live payment providers separately.                     |
| Fulfillment status   | Staff may misread past status after status mapping.                        | Validate completed, cancelled, refunded, and partially fulfilled order samples.               |
| Logistics references | Warehouse, carrier, pickup, or delivery meaning may not transfer directly. | Separate historical readability from VTEX logistics setup.                                    |
| OMS context          | Orders appear but operational ownership is unclear.                        | Confirm which data supports lookup, reporting, and post-launch workflows.                     |

Order and logistics risk should be handled with sample-based review. Use ordinary orders, marketplace orders, cancelled orders, refunded orders, multi-item orders, and fulfillment-sensitive orders to prove that the migrated history remains useful.

### Master Data and Custom Records Can Change Scope Late <a href="#master-data-and-custom-records-can-change-scope-late" id="master-data-and-custom-records-can-change-scope-late"></a>

Master Data and custom records are often where a VTEX migration changes from ordinary scope to specialized scope. The source store may include custom customer fields, CRM records, sales-team notes, B2B identifiers, form submissions, loyalty values, compliance fields, external IDs, or workflow records. Some may fit supported migration behavior. Some may need Add-ons. Some may require Custom Service. Some may be better handled by external systems.

Late discovery is the main risk. If custom records are identified only after Demo Migration, the merchant may have already chosen an approach that cannot preserve the required data meaning. The plan should identify custom-data ownership before scope is locked.

| Custom-data pattern                  | Scope risk                                                           | Handling path                                                                          |
| ------------------------------------ | -------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Master Data record used for workflow | Standard migration may not include the behavior or record structure. | Custom Service or VTEX-side rebuild may be needed.                                     |
| External customer or product ID      | Downstream systems may fail to match records.                        | Preserve through supported mapping, Add-ons, or Custom Service depending on structure. |
| Custom checkout field                | Compliance, fulfillment, or personalization value may be lost.       | Classify by display, storage, export, and workflow need.                               |
| App or middleware record             | The data may not belong to standard commerce records.                | Review app ownership and supported migration behavior.                                 |
| Custom Platform source field         | Structure may need bespoke interpretation.                           | Custom Service review is usually needed.                                               |

The important boundary is clear: Add-ons help when the requirement remains inside supported filtering, mapping, or configuration. Custom Service is for unsupported records, custom data structures, bespoke transformation, external-system complexity, Custom Platform handling, or custom migration logic adjustment.

### Storefront, CMS, Search, and URL Risk Should Not Be Hidden Inside Catalog Migration <a href="#storefront-cms-search-and-url-risk-should-not-be-hidden-inside-catalog-migration" id="storefront-cms-search-and-url-risk-should-not-be-hidden-inside-catalog-migration"></a>

VTEX can support headless and implementation-specific storefront approaches. That means storefront readiness should not be assumed from catalog migration. Product data can migrate while customer-facing pages, search behavior, content routing, redirects, CMS components, menu behavior, and SEO continuity still need implementation and validation.

This risk is especially high when the source store uses page-builder content, custom category landing pages, blog content, app-managed reviews, storefront-specific merchandising, or custom search rules. A product may be migrated correctly in the catalog but remain hard to find or poorly presented in the target storefront.

| Storefront risk              | What can go wrong                                                           | Prevention focus                                                                              |
| ---------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Product pages                | Data exists but display is incomplete or implementation-dependent.          | Validate representative product pages, images, specifications, SKU choices, and availability. |
| Category or collection pages | Source navigation does not translate into VTEX browsing paths.              | Separate catalog category data from storefront navigation and SEO routing.                    |
| CMS Pages and Blog Posts     | Content value is lost because content is treated as ordinary commerce data. | Decide what migrates, what is rebuilt, what redirects, and what is excluded.                  |
| Search and filters           | Discovery weakens despite catalog transfer.                                 | Validate specification-driven filters and priority search journeys.                           |
| URL continuity               | Existing traffic lands incorrectly after launch.                            | Prepare redirect and priority URL decisions before go-live.                                   |

Storefront risk belongs in migration planning because merchants often judge launch quality through the customer-facing experience. The migration team should avoid claiming storefront readiness until both migrated data and implementation-dependent presentation are reviewed.

### Risk Review Should End With Ownership, Not Only Severity <a href="#risk-review-should-end-with-ownership-not-only-severity" id="risk-review-should-end-with-ownership-not-only-severity"></a>

VTEX risk classification should identify who owns each issue. Some findings are migration corrections. Some are VTEX-side configuration. Some are storefront implementation. Some belong to integrations. Some require Add-ons. Some require Custom Service. Some are accepted differences because the source behavior should not be recreated.

A risk review that only says “high,” “medium,” or “low” is not enough. The action path matters more than the label.

| Finding type                                                                                 | Likely owner or action path                                      |
| -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Supported field mapped incorrectly                                                           | Migration correction or Add-on adjustment.                       |
| Supported records need filtering or mapping control                                          | Add-ons where the requirement remains within supported behavior. |
| Unsupported custom records, Master Data structures, external IDs, or bespoke transformations | Custom Service review.                                           |
| Checkout, payment, logistics, channel, or promotion setup                                    | VTEX-side configuration and validation.                          |
| Headless storefront display, routing, content rendering, or CMS components                   | Implementation team or storefront setup.                         |
| External ERP, CRM, PIM, WMS, OMS, or marketplace system ownership                            | Integration owner and data-governance review.                    |

This ownership view prevents a useful risk review from turning into a vague warning document. A risk is controlled only when the merchant knows what must be migrated, configured, rebuilt, integrated, escalated, or accepted.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX migration constraints come from the relationships between catalog, SKUs, specifications, pricing, sales channels, marketplace context, checkout, orders, logistics, Master Data, storefront implementation, and external systems. The most serious risks occur when source-store structures are transferred as records without deciding what they should do inside VTEX.

A strong VTEX migration plan controls risk through representative samples, purpose-based mapping, commercial-context review, custom-data classification, storefront-readiness separation, and ownership assignment. The migration should not be approved only because records are present. It should be approved when the target data supports the operating model the merchant expects to run after launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can VTEX migration risk remain hidden after records appear in the target store?**

VTEX risk often sits in relationships between records and services. Products, SKUs, prices, specifications, orders, logistics, and storefront behavior may all depend on separate setup or integration decisions, so visible records do not automatically prove operational readiness.

**What is the biggest catalog risk in VTEX migration?**

The biggest catalog risk is treating source options, attributes, bundles, and custom product behavior as ordinary product fields. VTEX catalog planning should distinguish products, SKUs, specifications, prices, availability, and storefront behavior before accepting the migration result.

**Are VTEX pricing and promotion risks part of migration or setup?**

They can involve both. Historical price and promotion data may be useful for order context, while active pricing, price tables, promotions, coupons, sales-channel rules, and external pricing ownership may require VTEX setup, integration, or custom handling.

**When does Master Data create Custom Service risk?**

Custom Service risk appears when Master Data or custom records must be transformed, preserved, synchronized, or used in ways beyond supported migration behavior. External identifiers, workflow records, custom checkout fields, and app-owned data should be reviewed early.

**How should VTEX migration risks be assigned after review?**

Each finding should be classified by action path: migration correction, Add-on adjustment, Custom Service review, VTEX-side configuration, storefront implementation, external integration, manual cleanup, or accepted limitation.
