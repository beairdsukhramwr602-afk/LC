# VTEX Migration Pitfalls and Prevention

VTEX migration pitfalls usually appear when teams approve visible records before proving whether those records work inside the target operating model. Products, customers, orders, CMS Pages, and Blog Posts may transfer successfully, but VTEX readiness also depends on Catalog structure, SKU activation, specifications, trade policies, price behavior, marketplace and seller context, OMS and logistics meaning, Master Data, storefront implementation, apps, APIs, and external-system ownership.

A strong prevention plan treats each pitfall as an operating risk, not only a data-transfer issue. The goal is to identify what can be validated through migration output, what must be configured in VTEX, what belongs to Add-ons, what requires Custom Service, and what remains owned by storefront, app, ERP, PIM, WMS, payment, marketplace, or middleware teams.

The following pitfalls are organized around the points where VTEX migrations most often lose business meaning. Each section defines the failure pattern, early warning signs, prevention actions, a practical recommendation example, and a pass condition that can be used before Full Migration approval.

### VTEX Pitfall Prevention Map <a href="#vtex-pitfall-prevention-map" id="vtex-pitfall-prevention-map"></a>

| Risk layer                    | Common failure pattern                                                                                                                                     | Prevention priority                                                                                    |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Catalog and SKUs              | Products arrive but SKU activation, specifications, category placement, images, stock, attachments, services, kits, or collections do not support selling. | Validate representative product families, not only record counts.                                      |
| Commercial rules              | Base prices appear correct but price tables, promotions, trade policies, sales channels, marketplace pricing, or external price ownership are unresolved.  | Test price behavior by buyer, channel, seller, and sales policy context.                               |
| Operations                    | Historical orders migrate but OMS, seller, logistics, fulfillment, invoice, and external order references lose operational meaning.                        | Separate historical readability from live operational configuration.                                   |
| Customer and Master Data      | Customer contacts migrate but B2B/account context, consent, custom fields, segmentation, or app-owned data is incomplete.                                  | Inventory standard customer records separately from Master Data and custom requirements.               |
| Storefront and content        | Migrated data exists but search, facets, CMS Pages, Blog Posts, redirects, and priority URLs are not launch-ready.                                         | Validate discovery and content continuity with storefront and SEO owners.                              |
| Integrations and custom logic | ERP, PIM, WMS, CRM, marketplace, payment, app, API, or middleware dependencies are discovered too late.                                                    | Build an integration and ownership map before interpreting Demo Migration results.                     |
| Service-scope decisions       | Add-ons, Custom Service, Entity Points, and follow-up migration actions are treated as generic fixes.                                                      | Tie each service decision to a specific data, mapping, filtering, configuration, or custom-logic need. |

### Pitfall 1: Approving VTEX Migration by Record Presence Alone <a href="#pitfall-1-approving-vtex-migration-by-record-presence-alone" id="pitfall-1-approving-vtex-migration-by-record-presence-alone"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

Products, customers, orders, CMS Pages, and Blog Posts appear in VTEX, so the migration is considered successful. The review does not prove whether products are sellable, SKUs are active, specifications support discovery, prices work by trade policy, customer data is usable, orders remain operationally readable, or priority storefront paths can support launch.

This creates a false pass. The migrated records exist, but the business cannot yet confirm whether the target store is commercially, operationally, or storefront-ready.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Warning sign                                                                  | Why it matters                                                                                            |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Reviewers compare only record totals.                                         | Record count does not prove SKU sellability, pricing behavior, searchability, or operational readability. |
| Complex samples are missing from Demo Migration.                              | The easiest records hide the VTEX-specific migration burden.                                              |
| Target storefront, trade policies, apps, or integrations are still undecided. | The same migrated record may need different validation depending on target implementation.                |
| Add-ons or Custom Service needs are discussed only after Full Migration.      | Late scope changes are harder to test and may affect launch timing.                                       |

#### Prevention <a href="#prevention" id="prevention"></a>

Define acceptance by usable outcomes. Each review should answer whether the migrated data can be found, understood, priced, sold, fulfilled, supported, reported, and reconciled in the VTEX environment. Record counts should remain one checkpoint, not the approval basis.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

For a multi-channel merchant, sample one ordinary product, one multi-SKU product, one specification-heavy product, one price/trade policy case, one marketplace or seller case, one varied order, one customer or Master Data case, one content page, and one integration-sensitive identifier. This reveals far more than validating ten simple products with no operational variation.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The migration is accepted only when representative VTEX records prove business behavior, not only presence. Any behavior that depends on configuration, storefront work, Add-ons, Custom Service, or external systems is documented before Full Migration approval.

### Pitfall 2: Treating VTEX Products as Simple Product Rows <a href="#pitfall-2-treating-vtex-products-as-simple-product-rows" id="pitfall-2-treating-vtex-products-as-simple-product-rows"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Source product data is moved into VTEX without preserving how the catalog should behave. Products may appear in the admin interface, but SKU activation, category placement, brand assignment, product specifications, SKU specifications, images, stock, attachments, assembly options, services, kits, collections, or storefront visibility may be incomplete or misinterpreted.

The risk is highest when the Source Platform uses options, variants, configurable products, bundles, modifiers, add-on services, product attributes, or custom catalog fields that do not translate directly into standard VTEX product fields.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Warning sign                                                                      | Why it matters                                                                           |
| --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Demo samples include only simple products.                                        | SKU and specification issues remain invisible.                                           |
| Attribute review is limited to text comparison.                                   | VTEX specifications can affect filters, categories, product discovery, and buyer choice. |
| Attachments, assembly options, services, kits, or collections are not classified. | Some source selling patterns may require configuration, app behavior, or Custom Service. |
| Storefront testing is postponed.                                                  | A product can be present but not purchasable or discoverable.                            |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Create a catalog sample set that reflects the real source store, including ordinary products, multi-SKU items, specification-heavy items, category-sensitive products, service or customization products, kit/bundle-like items, marketplace-relevant SKUs, and high-traffic products.

| Sample type                          | What to inspect                                                                             | Prevention value                                                |
| ------------------------------------ | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Ordinary product                     | Name, description, brand, category, image, SKU, stock, and price.                           | Confirms baseline accuracy.                                     |
| Multi-SKU product                    | Variant choices, SKU records, SKU images, stock, price, and specification values.           | Confirms sellable SKU structure.                                |
| Specification-heavy product          | Product and SKU specifications, filter values, category-linked values, and required fields. | Protects discovery, comparison, and merchandising.              |
| Attachment or service product        | Personalization, warranty, gift wrap, service selection, or required buyer input.           | Identifies app, configuration, Add-on, or Custom Service needs. |
| Kit, collection, or bundle-like item | Component logic, grouping, membership, merchandising, and buying behavior.                  | Prevents forced flattening of source product relationships.     |

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A fashion, electronics, or configurable goods merchant should test products with size/color variation, technical specifications, multiple images, stock-sensitive SKUs, category filters, and storefront selection behavior. A pass should require the buyer to find the item, choose the intended SKU, see the expected information, and reach the cart with the correct commercial context.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative products and SKUs are active, categorized, specified, stocked where expected, priced, discoverable, and purchasable through the intended VTEX storefront or sales channel. Catalog exceptions are assigned to configuration, Add-ons, Custom Service, or accepted exclusions.

### Pitfall 3: Flattening Specifications, Attachments, Assembly Options, Services, Kits, and Collections <a href="#pitfall-3-flattening-specifications-attachments-assembly-options-services-kits-and-collections" id="pitfall-3-flattening-specifications-attachments-assembly-options-services-kits-and-collections"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Catalog details that drive buyer choice or merchandising are migrated as generic text. Product specifications, SKU specifications, attachments, assembly options, services, kit-like structures, collection membership, and source custom options may survive as labels but lose their operational purpose.

This weakens VTEX catalog quality because the target store may no longer support filtering, comparison, product customization, service selection, bundle-like presentation, or merchandising groups in the way the business expects.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Warning sign                                                                           | Risk created                                                       |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Source custom options are mapped without classifying buyer behavior.                   | Required selections may become non-actionable text.                |
| Product and SKU specifications are mixed together.                                     | Filter, variant, and PDP behavior can become confusing.            |
| Services, warranties, personalization, or add-ons are treated as product descriptions. | Revenue or operational choices may disappear from the buying flow. |
| Collections and kit-like groupings are reviewed only as product lists.                 | Merchandising intent and relationship logic can be lost.           |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Separate catalog semantics before mapping. Decide which source values should become VTEX specifications, which should remain descriptive fields, which require target configuration or app behavior, and which need Custom Service because the target behavior cannot be represented through ordinary migration output.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A merchant selling configurable furniture should not approve migration by checking only product title and price. The review should classify material, color, size, assembly service, warranty, accessory bundle, collection membership, and stock behavior separately, then decide which elements must be migrated, configured, handled through an Add-on, or reviewed through Custom Service.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Catalog details preserve their intended use. Buyers can filter, select, customize, compare, or understand products as required, and any unsupported behavior is documented with ownership before launch.

### Pitfall 4: Ignoring Pricing, Promotions, Trade Policies, and Sales-Channel Logic <a href="#pitfall-4-ignoring-pricing-promotions-trade-policies-and-sales-channel-logic" id="pitfall-4-ignoring-pricing-promotions-trade-policies-and-sales-channel-logic"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Base prices are migrated, but the commercial model does not match how the business sells. VTEX projects can involve price tables, fixed prices, promotions, coupons, B2B or customer-specific pricing, marketplace pricing, regional prices, trade policies, and sales-channel-specific availability. A product may look correct in a generic catalog review but show the wrong price or availability in the actual buying context.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Warning sign                                                           | Why it matters                                                          |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Only base SKU prices are checked.                                      | Differentiated prices remain untested.                                  |
| Trade policies are mentioned after Demo Migration approval.            | Availability and pricing may need revalidation.                         |
| Promotions are treated as migrated history instead of launch behavior. | Historical coupon names do not prove active promotion setup.            |
| External pricing systems are not identified.                           | ERP, PIM, marketplace, or pricing engines may override migrated values. |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Review pricing by commercial context, not by product alone. Identify which price values are migration data, which require VTEX setup, which are controlled by external systems, and which price transformations exceed standard migration scope.

| Pricing context               | Prevention check                                                            |
| ----------------------------- | --------------------------------------------------------------------------- |
| Base price                    | Compare representative product/SKU prices and currency assumptions.         |
| Price table or fixed price    | Validate customer, segment, region, channel, or B2B pricing examples.       |
| Promotion or coupon           | Separate migrated history from active launch setup.                         |
| Trade policy or sales channel | Confirm availability and commercial meaning by selling context.             |
| Marketplace price             | Validate seller, marketplace, commission, and offer context where relevant. |
| External price authority      | Assign ERP, PIM, marketplace, or pricing-engine ownership.                  |

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

A merchant selling retail, wholesale, and marketplace products should test the same SKU across at least two commercial contexts. Reviewers should confirm what price should be migrated, what price should be configured in VTEX, what price is externally owned, and what should be excluded from migration acceptance.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Target VTEX pricing is understandable by product, buyer, seller, channel, promotion, and trade policy context. Differences are explained by migration output, VTEX configuration, external ownership, Add-ons, Custom Service, or accepted exclusion.

### Pitfall 5: Losing Marketplace, Seller, OMS, and Logistics Meaning <a href="#pitfall-5-losing-marketplace-seller-oms-and-logistics-meaning" id="pitfall-5-losing-marketplace-seller-oms-and-logistics-meaning"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Marketplace, seller, order, fulfillment, and logistics context is treated as ordinary product or order text. Seller identifiers, marketplace order references, offer context, sales-channel meaning, fulfillment responsibility, invoice data, delivery methods, pickup points, status history, and external references may become unclear.

The result can hurt customer service, accounting, seller operations, warehouse coordination, and post-launch reconciliation even when historical order totals appear correct.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Warning sign                                                           | Operational risk                                                   |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Marketplace orders are sampled like ordinary orders.                   | Seller and channel context may be lost.                            |
| Fulfillment and logistics values are not reviewed by operations teams. | Historical orders may not support support or reconciliation needs. |
| External order, invoice, WMS, ERP, or marketplace IDs are ignored.     | Connected teams may lose traceability.                             |
| OMS status meaning is assumed to match source status meaning.          | Historical interpretation can become misleading.                   |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Create operational samples that include ordinary orders and marketplace/seller/logistics examples. Separate historical order readability from live VTEX OMS, logistics, payment, tax, and fulfillment configuration.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

For a marketplace merchant, test an order with seller context, fulfillment reference, shipping method, payment label, invoice reference, external marketplace identifier, customer relationship, and order status. The review should prove that support and operations teams can interpret the migrated order without returning to the Source Platform.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Marketplace, seller, OMS, and logistics samples preserve operational meaning, or exclusions and reconfiguration work are accepted before Full Migration.

### Pitfall 6: Confusing Historical Order Readability with Live Checkout Readiness <a href="#pitfall-6-confusing-historical-order-readability-with-live-checkout-readiness" id="pitfall-6-confusing-historical-order-readability-with-live-checkout-readiness"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Migrated orders show payment labels, shipping labels, coupon names, taxes, or statuses, and the team assumes VTEX Checkout, payment, shipping, tax, coupon, seller selection, and orderForm behavior are ready. Historical order readability and live checkout readiness are different outcomes.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Warning sign                                                           | Risk created                                                       |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Payment and shipping labels in old orders are treated as launch proof. | Live checkout may still be unconfigured.                           |
| No test order is placed in the target VTEX environment.                | Cart, payment, tax, shipping, and promotion flows remain unproven. |
| Checkout custom fields or orderForm behavior are not tested.           | Custom operational values may be missing from live orders.         |
| Payment, anti-fraud, logistics, or tax providers are pending.          | Migrated history cannot validate provider readiness.               |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Validate historical order samples for readability, then run separate live checkout tests after target configuration is ready. Do not accept one as proof of the other.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A project should review a migrated historical order for customer, item, payment, shipping, tax, discount, and status readability. Then it should separately place a target test order that confirms cart behavior, customer profile behavior, delivery option, payment method, promotion or coupon handling, tax behavior, seller context, and OMS progression.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Historical orders are readable for support and reporting, and live checkout is tested through the intended VTEX payment, shipping, tax, coupon, seller, and orderForm behavior.

### Pitfall 7: Overlooking Customers, B2B Data, Master Data, and Custom Fields <a href="#pitfall-7-overlooking-customers-b2b-data-master-data-and-custom-fields" id="pitfall-7-overlooking-customers-b2b-data-master-data-and-custom-fields"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Customer records migrate as basic contacts, but broader customer meaning is incomplete. B2B/account data, segmentation, consent values, approval context, custom profile fields, Master Data objects, app-owned customer data, loyalty references, ERP/CRM IDs, or external identifiers may be missing or treated as ordinary notes.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Warning sign                                                  | Why it matters                                                           |
| ------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Validation checks only name, email, address, and order count. | Customer meaning is reduced to contact presence.                         |
| Master Data schemas and app-owned fields are not inventoried. | Custom records can disappear from migration scope.                       |
| B2B or account-based workflows are sampled late.              | Buyer permissions, segmentation, and approval context may be unresolved. |
| External customer IDs are not reconciled.                     | ERP, CRM, loyalty, or support systems may lose continuity.               |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Separate standard customer migration from account, B2B, Master Data, custom field, and external-reference requirements. Assign each customer-related data type to migration output, VTEX configuration, app setup, external-system ownership, Add-on handling, Custom Service, or exclusion.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A B2B merchant should sample one company or account structure, buyer user, address, segmentation value, custom customer field, consent or preference value, order history, external CRM/ERP ID, and any related Master Data record.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Customer samples preserve the expected account and operational meaning, and Master Data, custom field, consent, app-owned, or external-reference requirements are mapped, excluded, configured separately, or routed to Custom Service.

### Pitfall 8: Assuming Storefront, Search, CMS, and SEO Continuity from Migration Alone <a href="#pitfall-8-assuming-storefront-search-cms-and-seo-continuity-from-migration-alone" id="pitfall-8-assuming-storefront-search-cms-and-seo-continuity-from-migration-alone"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Products, categories, CMS Pages, and Blog Posts migrate, but the storefront does not preserve how shoppers discover and evaluate products. FastStore, Store Framework, headless storefronts, search, facets, navigation, product listing pages, PDP layout, redirects, metadata, landing pages, and priority URLs may require separate implementation work.

A technically successful migration can still create launch risk if storefront discovery and SEO continuity are weak.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Warning sign                                                 | Launch risk                                                |
| ------------------------------------------------------------ | ---------------------------------------------------------- |
| Target storefront approach is unclear.                       | Data validation cannot confirm the buyer experience.       |
| Search and facet behavior are not sampled.                   | Specifications may not support discovery as expected.      |
| Redirects and priority URLs are left for the end.            | SEO and paid-landing continuity can suffer.                |
| CMS Pages and Blog Posts are treated as low-priority extras. | Content-driven traffic and support pages may be disrupted. |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Plan storefront and SEO continuity as a dedicated validation layer. Identify priority products, categories, content pages, Blog Posts, metadata, redirects, search terms, facets, filtered paths, landing pages, and storefront implementation ownership before Full Migration approval.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant with strong organic traffic should test one high-value category, several priority product URLs, a search term, a filter/facet combination, a landing page, a CMS Page, a Blog Post, metadata, redirects, and the PDP experience in the target storefront.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Priority products, categories, search paths, filters, CMS Pages, Blog Posts, redirects, metadata, and storefront paths are discoverable and acceptable for launch, or separate storefront and SEO work is assigned before migration acceptance.

### Pitfall 9: Missing Apps, APIs, ERP, PIM, WMS, Marketplace, and Middleware Dependencies <a href="#pitfall-9-missing-apps-apis-erp-pim-wms-marketplace-and-middleware-dependencies" id="pitfall-9-missing-apps-apis-erp-pim-wms-marketplace-and-middleware-dependencies"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

The migration focuses on platform records while connected systems depend on identifiers, fields, statuses, documents, messages, webhooks, API payloads, or custom objects that are not part of ordinary migration output. Records may exist in VTEX but fail to support daily operations because external systems cannot interpret them.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

| Warning sign                                                                          | Risk created                                                                 |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| There is no integration inventory.                                                    | Unknown dependencies surface during launch testing.                          |
| External IDs and app-owned fields are not listed.                                     | Reconciliation breaks across ERP, PIM, WMS, CRM, marketplace, or middleware. |
| VTEX IO, headless, checkout, or webhook logic is assumed to work after data transfer. | Implementation dependencies are confused with migration output.              |
| Custom objects are discussed only after Demo Migration.                               | Custom Service needs may be discovered too late.                             |

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Build an ownership map before interpreting Demo Migration results. Classify each dependency as migrated data, target configuration, app setup, API/integration setup, external-system work, Add-on output, Custom Service, or exclusion.

| Dependency type              | Ownership question                                                                                 |
| ---------------------------- | -------------------------------------------------------------------------------------------------- |
| ERP/PIM/WMS/CRM IDs          | Must the identifier be preserved, transformed, or replaced?                                        |
| Marketplace middleware       | Which seller, offer, order, and commission references must remain readable?                        |
| App-owned data               | Is the data accessible through migration, app configuration, API, Master Data, or custom handling? |
| Checkout/order custom fields | Are the fields historical only, live-order requirements, or Custom Service candidates?             |
| Headless/frontend APIs       | Which migrated values must power storefront rendering, search, navigation, or personalization?     |

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

A merchant with ERP and PIM dependencies should identify product IDs, SKU IDs, inventory references, pricing references, order status values, customer IDs, API fields, and middleware-owned values. Each value should be marked as preserve, transform, configure, exclude, or review through Custom Service.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Integration-sensitive records and references are mapped, configured, excluded, or routed to Custom Service before Full Migration. No critical external workflow depends on an unreviewed field, identifier, or object.

### Pitfall 10: Misusing Add-ons, Custom Service, Entity Points, and Additional Migration Options <a href="#pitfall-10-misusing-add-ons-custom-service-entity-points-and-additional-migration-options" id="pitfall-10-misusing-add-ons-custom-service-entity-points-and-additional-migration-options"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

Service-scope mechanisms are treated as interchangeable fixes. Add-ons are expected to solve open-ended custom logic, Custom Service is used without clear output ownership, Entity Points are misunderstood during follow-up planning, or Additional Migration Options are treated as a shortcut that avoids revalidation.

This creates preventable confusion around what Next-Cart will migrate, what must be configured in VTEX, what needs custom handling, and what still belongs to external systems or storefront implementation.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

| Warning sign                                                                                    | Why it matters                                                                                                |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Add-ons are described as solving all unsupported VTEX behavior.                                 | Add-ons are bounded service options, not a replacement for Custom Service.                                    |
| Custom Service is requested without defining inputs, transformation logic, and pass conditions. | Custom work cannot be validated reliably.                                                                     |
| Follow-up migration review assumes all records were already counted.                            | New Product, Customer, Order, and Blog Posts records may need Entity Points when migrated for the first time. |
| Additional Migration Options are used without rechecking changed structures.                    | Previously approved validation may not cover new or changed data.                                             |

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Treat each mechanism as a distinct planning tool. Use Add-ons for supported filtering, mapping, configuration, or bounded custom handling. Use Custom Service when source structure, VTEX interpretation, Custom Platform handling, app-owned records, Master Data objects, external-system references, or bespoke transformation exceeds standard capability. Use Additional Migration Options only with renewed review of changed data and business rules.

| Scope mechanism              | Correct prevention use                                                                                                                                                             |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Add-ons                      | Handle supported filters, mappings, configurations, and bounded custom needs with clear samples.                                                                                   |
| Custom Service               | Review non-standard transformation, Custom Platform data, app-owned records, Master Data objects, or external-system logic.                                                        |
| Entity Points                | Plan new eligible records accurately; records already counted through the service license do not consume Entity Points again simply because another migration action is performed. |
| Additional Migration Options | Revalidate new or changed records, not only the earlier approved dataset.                                                                                                          |
| Exclusions                   | Document what is not migrated and who owns the target-side or external-system alternative.                                                                                         |

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

If a merchant adds new products, new customer accounts, new orders, and revised price logic after an earlier migration, the follow-up review should separate first-time migrated records from already counted records. It should also revalidate changed SKU, specification, pricing, trade policy, storefront, and integration behavior before accepting the follow-up result.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Add-ons, Custom Service, Entity Points, Additional Migration Options, and exclusions are each used for the right planning purpose. Reviewers can explain what is included, what is custom, what is externally owned, what consumes Entity Points, and what must be revalidated.

### VTEX Pitfall Prevention Matrix <a href="#vtex-pitfall-prevention-matrix" id="vtex-pitfall-prevention-matrix"></a>

| Priority    | Pitfall area                                                                                                         | Primary owner                                                      | Prevention proof                                                                          |
| ----------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Highest     | SKU activation, specifications, pricing, trade policies, checkout-critical values, and priority URLs.                | Catalog, pricing, storefront, and SEO teams.                       | Representative samples prove sellability, discovery, pricing, and launch path continuity. |
| High        | Marketplace, seller, OMS, logistics, customer/account data, Master Data, and external IDs.                           | Operations, support, marketplace, customer, and integration teams. | Records remain readable and reconcilable by the teams that operate them.                  |
| Medium      | CMS Pages, Blog Posts, historical promotions, older order history, secondary redirects, and non-critical content.    | Content, SEO, and support teams.                                   | Continuity is acceptable or documented with known owners.                                 |
| Conditional | Apps, APIs, custom checkout fields, Master Data custom objects, headless storefront needs, and Custom Platform data. | Technical, app, integration, and Custom Service stakeholders.      | Ownership is assigned before migration approval and custom outputs have pass conditions.  |

Use this matrix to prioritize review time. A strong VTEX migration does not try to inspect every record equally; it inspects the records most likely to affect launch, revenue, operations, customer support, SEO, and downstream systems.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX migration pitfalls are preventable when the project treats migration as a business-readiness exercise rather than a record-transfer exercise. Catalog structure, SKU behavior, specifications, price logic, trade policies, marketplace and seller operations, OMS, logistics, Master Data, storefront continuity, apps, APIs, integrations, Add-ons, Custom Service, Entity Points, and follow-up migration activity all need clear ownership and evidence.

The safest approach is to test representative complexity during Demo Migration, turn those findings into explicit pass conditions, confirm them again during Full Migration, and revalidate relevant areas when Additional Migration Options are used. This keeps VTEX migration acceptance practical, consistent, and aligned with the way the target commerce environment will actually operate.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is record-count validation risky for VTEX migration?**

Record count only proves that records exist. VTEX migration review also needs to prove SKU activation, specifications, pricing, trade policies, marketplace context, OMS readability, Master Data, storefront discovery, and integration-sensitive values.

**What is the most common catalog pitfall in a VTEX migration?**

The most common catalog pitfall is approving products before proving the SKU and specification model. A product can exist in VTEX while its SKUs, categories, images, stock, specifications, attachments, or storefront behavior remain incomplete.

**Can migrated orders prove VTEX Checkout is ready?**

No. Migrated orders help validate historical order readability. Live VTEX Checkout readiness requires separate testing of cart behavior, delivery options, payment methods, tax behavior, promotions, seller context, and orderForm behavior after target configuration is ready.

**When should VTEX migration gaps move to Custom Service?**

Custom Service is appropriate when the migration requires non-standard transformation, Custom Platform source interpretation, Master Data custom objects, app-owned records, custom checkout fields, marketplace logic, external-system references, or bespoke behavior beyond standard service capability.

**How should Additional Migration Options be handled for VTEX?**

Use Additional Migration Options with renewed validation. Previously approved records should not be revalidated blindly, but new or changed products, customers, orders, Blog Posts, pricing rules, specifications, marketplace relationships, custom fields, and integration-sensitive values need fresh review.
