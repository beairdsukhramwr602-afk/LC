# VTEX Migration Pitfalls and Prevention

VTEX migration pitfalls usually appear when the project treats VTEX as a simple destination for products, customers, and orders. VTEX is better understood as a connected commerce environment where catalog structure, SKUs, specifications, pricing, promotions, marketplace context, sellers, orders, logistics, Master Data, storefront implementation, and integrations affect whether the migrated result can operate after launch.

A strong prevention plan identifies the assumptions that can break across those layers. It uses representative samples, separates migrated records from VTEX configuration, assigns ownership for external systems, and defines pass conditions before Full Migration. The goal is not to eliminate every difference between the Source Platform and VTEX. The goal is to control the differences that affect selling, support, reporting, fulfillment, and launch readiness.

### Pitfall 1: Treating VTEX as a Simple Storefront Destination <a href="#pitfall-1-treating-vtex-as-a-simple-storefront-destination" id="pitfall-1-treating-vtex-as-a-simple-storefront-destination"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The migration is planned around products, customers, and orders without enough attention to the connected VTEX operating model. Catalog data may transfer, but pricing, trade policies, seller context, logistics, Master Data, search, storefront implementation, or integration requirements remain underplanned.

This creates false confidence. Records can appear in VTEX while the business still cannot explain product availability, price behavior, marketplace ownership, fulfillment context, or storefront visibility.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Warning sign                                                                               | Risk created                                                                 |
| ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| The scope describes only products, customers, and orders.                                  | VTEX-specific operating layers may be missed.                                |
| Pricing, logistics, marketplace, and Master Data owners are not involved in sample review. | Business-critical context may be approved by the wrong reviewers.            |
| Demo Migration checks only ordinary products and completed orders.                         | Complex VTEX behavior remains untested.                                      |
| Checkout, search, storefront, and integration setup are assumed to be migration output.    | Target-side work may be mistaken for migration failure or migration success. |

#### Prevention <a href="#prevention" id="prevention"></a>

Define the VTEX operating model before approving scope. Identify which data should migrate, which behavior should be configured in VTEX, which records belong to external systems, and which requirements need Add-ons or Custom Service.

The first sample set should include catalog, SKU, pricing, promotion, marketplace, order, logistics, customer, Master Data, storefront, and integration examples. Each sample should have an expected outcome and a reviewer who understands the business meaning.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

A merchant moving from a highly customized enterprise platform should test one ordinary product, one complex SKU product, one specification-heavy product, one channel-specific price, one marketplace order, one customer with custom fields, one high-traffic URL, and one integration-owned identifier before approving the migration approach.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The team can explain which VTEX layers are migrated, configured, integrated, customized, excluded, or manually rebuilt. No launch-critical behavior remains hidden behind a generic record-transfer approval.

### Pitfall 2: Flattening Products Without Preserving SKU and Specification Meaning <a href="#pitfall-2-flattening-products-without-preserving-sku-and-specification-meaning" id="pitfall-2-flattening-products-without-preserving-sku-and-specification-meaning"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Source products are migrated as generic catalog records while SKU-level choices, specifications, filters, product attributes, images, stock references, category-specific values, services, attachments, or customization options lose their operating purpose.

VTEX catalog quality depends on more than product titles and prices. SKUs must remain sellable and understandable. Specifications often support search, filtering, comparison, compliance, merchandising, and product detail accuracy. When those values are flattened into descriptions or unmanaged text, the catalog may look complete but behave poorly.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Warning sign                                                                | Risk created                                                 |
| --------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Product and SKU fields are reviewed together without distinction.           | Variant-like choices may be misrepresented.                  |
| Specifications are approved by count rather than by use.                    | Search, filters, comparison, and PDP clarity can fail.       |
| Services, attachments, or customization fields are treated as descriptions. | Buyer choices or revenue-driving options may disappear.      |
| Category-specific requirements are not reviewed.                            | Required values may be missing from important catalog areas. |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Classify catalog data before migration. Decide which source values should become VTEX product fields, SKU fields, specifications, category-specific values, descriptive content, service/attachment behavior, app behavior, Add-on output, Custom Service scope, or accepted exclusion.

Use representative samples rather than clean products only. Complex products should be tested through catalog review, storefront review, search/filter review, and commercial review.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A fashion merchant should test a size/color product, a product with material and fit specifications, a product with multiple images, a product available only in selected channels, and a product whose source options depended on an app. The sample should prove that shoppers can find the item, select the intended SKU, understand the product, and reach checkout with the correct context.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative products preserve SKU meaning, specification meaning, category placement, storefront visibility, and buyer selection behavior. Unsupported or app-dependent behavior is assigned to target configuration, Add-ons, Custom Service, manual setup, or accepted exclusion.

### Pitfall 3: Reviewing Pricing Without Commercial Context <a href="#pitfall-3-reviewing-pricing-without-commercial-context" id="pitfall-3-reviewing-pricing-without-commercial-context"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

The project validates base prices but ignores how VTEX commercial behavior may depend on price tables, fixed prices, promotions, coupons, B2B pricing, seller pricing, marketplace pricing, trade policies, sales channels, region, customer segment, or external pricing systems.

The result may appear correct in catalog review but fail when a buyer, seller, channel, or customer group receives the wrong price or availability after launch.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Warning sign                                                   | Risk created                                                      |
| -------------------------------------------------------------- | ----------------------------------------------------------------- |
| Reviewers check only one price per SKU.                        | Differentiated commercial logic remains untested.                 |
| Promotions are approved from old coupon names.                 | Historical promotion data may be confused with live launch setup. |
| Trade policies are discussed late.                             | Availability and pricing may need revalidation.                   |
| ERP, PIM, marketplace, or pricing-engine ownership is unclear. | External systems may overwrite or contradict migrated prices.     |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Validate pricing by context. Select products that expose ordinary pricing, segmented pricing, marketplace or seller pricing, discounted pricing, and externally owned pricing. Separate historical values from live VTEX configuration and external price authority.

A pricing issue should be classified as migration correction, VTEX setup, Add-on adjustment, Custom Service review, external-system work, or accepted exclusion. It should not remain a generic “price mismatch” item.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A B2C/B2B merchant should test the same SKU in at least two commercial contexts. Reviewers should confirm which price is migrated, which price is configured in VTEX, which price comes from an external system, and which price should not be accepted until integration or trade-policy setup is complete.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Pricing and promotion samples are understandable by SKU, channel, seller, trade policy, customer segment, and external ownership. Reviewers can explain every launch-critical difference before Full Migration approval.

### Pitfall 4: Losing Marketplace, Seller, OMS, and Logistics Meaning <a href="#pitfall-4-losing-marketplace-seller-oms-and-logistics-meaning" id="pitfall-4-losing-marketplace-seller-oms-and-logistics-meaning"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Marketplace, seller, order-management, and logistics context is treated as ordinary product or order text. Seller identifiers, offer context, marketplace references, order status meaning, package references, invoice data, shipping methods, pickup points, warehouse ownership, carrier details, tracking numbers, or external order IDs become unclear.

This can weaken customer service, seller operations, accounting, warehouse coordination, marketplace reporting, and post-launch reconciliation even when order totals look accurate.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Warning sign                                                 | Operational risk                                                             |
| ------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| Marketplace orders are sampled like ordinary orders.         | Seller and channel ownership may be lost.                                    |
| Logistics values are not reviewed by operations teams.       | Fulfillment history may be incomplete or misleading.                         |
| OMS status values are assumed to match source status values. | Support teams may misinterpret historical orders.                            |
| External IDs are ignored.                                    | ERP, WMS, accounting, marketplace, or support systems may lose traceability. |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Create operational validation samples. Include ordinary orders, marketplace orders, seller-specific records, cancelled or refunded orders, orders with multiple packages, pickup or delivery examples, invoice references, and records with external identifiers.

Separate historical order readability from live VTEX OMS, checkout, payment, tax, logistics, and fulfillment setup. A migrated historical record can support review without proving live operational readiness.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

A marketplace merchant should test an order with seller ownership, marketplace reference, customer relationship, SKU and offer details, payment label, shipping method, invoice reference, tracking reference, and external marketplace identifier. The order should be readable by support, marketplace, fulfillment, and finance teams.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Operational samples preserve seller, marketplace, OMS, logistics, and external-reference meaning, or exclusions and reconfiguration work are accepted before launch.

### Pitfall 5: Confusing Historical Order Readability With Live Checkout Readiness <a href="#pitfall-5-confusing-historical-order-readability-with-live-checkout-readiness" id="pitfall-5-confusing-historical-order-readability-with-live-checkout-readiness"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Migrated orders contain payment labels, shipping labels, coupon names, taxes, totals, or statuses, and the team assumes VTEX Checkout, payment providers, tax rules, shipping rules, seller selection, promotions, and orderForm behavior are ready. Historical readability and live checkout readiness are different outcomes.

This pitfall creates late launch risk because live customer checkout may still need configuration, testing, provider setup, antifraud review, logistics setup, promotion setup, or storefront work.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Warning sign                                                           | Risk created                                                                 |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Payment and shipping labels in old orders are treated as launch proof. | Live checkout behavior may remain untested.                                  |
| No target test order is placed.                                        | Cart, payment, shipping, tax, promotion, and seller behavior remain unknown. |
| Custom checkout fields are not tested.                                 | Operational values may be missing from new orders.                           |
| Provider setup is pending while migration is approved.                 | Migration approval may be confused with go-live readiness.                   |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate historical orders for support and reporting use. Then test live checkout separately in the target VTEX environment after configuration is ready. The two reviews should be connected but not treated as the same proof.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

A project should review a migrated order for customer, line item, payment, discount, tax, shipping, fulfillment, and status readability. Separately, the launch team should place a new VTEX test order that confirms cart behavior, customer profile behavior, payment method, shipping option, tax behavior, seller context, promotion behavior, and OMS progression.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Historical orders are readable for support and reconciliation, and live checkout has been tested through the intended VTEX payment, tax, shipping, promotion, seller, and orderForm behavior.

### Pitfall 6: Overlooking Master Data, Custom Fields, and External Identifiers <a href="#pitfall-6-overlooking-master-data-custom-fields-and-external-identifiers" id="pitfall-6-overlooking-master-data-custom-fields-and-external-identifiers"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Customer or operational context is reduced to standard fields while Master Data objects, custom profile fields, consent indicators, loyalty records, B2B/account references, CRM IDs, ERP IDs, marketplace IDs, app-owned records, or middleware references are missed.

These values may not be visible in ordinary product/customer/order checks, but they can be essential for support, segmentation, integration, reporting, or operational continuity.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Warning sign                                                    | Risk created                                         |
| --------------------------------------------------------------- | ---------------------------------------------------- |
| Custom fields are listed without sample records.                | Scope cannot be evaluated reliably.                  |
| Master Data objects are assumed to be standard customer fields. | Relationships or required values may be lost.        |
| External IDs are treated as optional notes.                     | Integrations may fail to reconcile records.          |
| App-owned data is expected in standard migration output.        | Unsupported records may be missed until late review. |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Create a custom-data inventory. For each field, object, or external identifier, identify the owner, source, target expectation, sample record, business purpose, migration path, and validation proof. Use Add-ons only for supported filtering, mapping, or configuration needs. Use Custom Service review when the requirement involves unsupported records, Master Data objects, bespoke transformations, app-owned records, external identifiers, Custom Platform interpretation, or custom migration logic adjustment.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A merchant with ERP product IDs, loyalty IDs, B2B approval references, and custom customer fields should not approve migration after checking name, email, SKU, and order totals. The team should provide samples and define whether each value must migrate, be rebuilt in VTEX, remain in an external system, or be handled through Custom Service.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Custom records and external identifiers are migrated, mapped, excluded, configured, assigned to Custom Service, or assigned to an external owner with explicit approval. No business-critical custom value remains hidden in generic customer or order validation.

### Pitfall 7: Treating Storefront, Search, and SEO Continuity as Automatic <a href="#pitfall-7-treating-storefront-search-and-seo-continuity-as-automatic" id="pitfall-7-treating-storefront-search-and-seo-continuity-as-automatic"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The team assumes that migrated catalog data automatically creates a complete VTEX storefront experience. Products may exist, but search, filters, navigation, product pages, CMS content, Blog Posts, landing pages, URLs, redirects, metadata, availability display, and checkout entry points may still require implementation and validation.

This weakens customer experience and SEO continuity because storefront behavior depends on more than catalog presence.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Warning sign                                           | Risk created                                                                       |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Product migration is treated as storefront migration.  | Search, filters, navigation, and content may be underplanned.                      |
| High-traffic URLs are not sampled.                     | Redirect and SEO losses may appear after launch.                                   |
| CMS Pages and Blog Posts are not classified.           | Content may need migration, rebuild, redirect, retirement, or exclusion decisions. |
| Search/facet behavior is not tested with real queries. | Customers may not find products even when products exist.                          |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Validate storefront continuity separately from data presence. Test top products, top categories, high-value search terms, filter combinations, key landing pages, CMS Pages, Blog Posts, metadata, redirects, and launch-critical URLs. Assign ownership for storefront implementation, SEO decisions, and manual content work.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A merchant with strong organic traffic should test old-to-new URL behavior for top product and category pages, confirm redirect ownership, validate search results for high-value queries, check specification-based filters, and review whether content pages should migrate, be rebuilt, or be redirected.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

The target VTEX storefront supports product discovery, content continuity, high-priority URLs, redirects, metadata, search, filters, and checkout entry points, or unresolved items are assigned before launch.

### Pitfall 8: Choosing the Wrong Later Migration Action <a href="#pitfall-8-choosing-the-wrong-later-migration-action" id="pitfall-8-choosing-the-wrong-later-migration-action"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

The Source Platform continues changing after an earlier migration run, but the team does not decide whether to continue migration activity with the last used configuration, continue with a new configuration, or perform a new migration. The team may expect one outcome while validating another.

This creates confusion around newly added records, changed mappings, replaced target results, Entity Points usage, and the sample set needed for approval.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Warning sign                                                             | Risk created                                                                  |
| ------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| The team says “run it again” without defining the intended action.       | Target effect and validation responsibility are unclear.                      |
| Mapping changes are requested after an earlier run.                      | Newly affected fields need revalidation.                                      |
| A refreshed target result is expected but only new records are reviewed. | Earlier migrated records may remain or be replaced differently than expected. |
| Entity Points assumptions are not documented.                            | Planning may incorrectly treat already recorded entities as newly consumed.   |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Define the action before execution. Continuing with the last used configuration should focus on newly added source records and regression samples. Continuing with a new configuration should validate affected fields, filters, and mapping choices. Performing a new migration should validate the refreshed target result and whether earlier migrated data was replaced as intended.

Entity Points should be interpreted consistently: newly migrated eligible entities may consume Entity Points when first migrated, while already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant completes Demo Migration, keeps selling for three weeks, then changes catalog mapping expectations. The team should not simply rerun and approve new orders. It should define whether configuration changed, which fields are affected, whether previous target data should remain or be replaced, which samples must be rechecked, and which new eligible records affect Entity Points planning.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

The team can state the selected migration action, expected target effect, configuration status, affected records, validation sample set, ownership, and Entity Points interpretation before execution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX migration pitfalls can be prevented when the project validates VTEX as a connected commerce environment. Catalog, SKUs, specifications, pricing, promotions, marketplace context, sellers, orders, logistics, Master Data, storefront implementation, integrations, and later migration actions each need clear expectations before launch.

The strongest prevention method is practical: classify data meaning early, sample difficult records, separate migration output from VTEX configuration, assign external-system ownership, preserve Add-ons and Custom Service boundaries, and define pass conditions before Full Migration. VTEX migration should be approved only when the target result supports real operation, not merely when records are present.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do VTEX migration issues often appear late?**

Late issues usually appear when validation focuses on record presence rather than operating meaning. VTEX catalog, pricing, marketplace, logistics, Master Data, storefront, and integration layers can affect whether migrated records are actually usable.

**What is the most common VTEX catalog migration pitfall?**

A common pitfall is flattening SKUs, specifications, attachments, services, or source custom options into generic product text. The catalog may look complete but fail search, filtering, product selection, or merchandising expectations.

**Should VTEX pricing be validated separately from product migration?**

Yes. VTEX pricing can depend on context such as price tables, promotions, sellers, trade policies, channels, B2B rules, or external price systems. Product presence does not prove commercial readiness.

**How should marketplace and seller data be reviewed?**

Marketplace and seller records should be reviewed through operational samples that include seller ownership, offer context, marketplace references, OMS status, fulfillment evidence, and external identifiers.

**When does VTEX custom data require Custom Service review?**

Custom Service review is appropriate when the requirement involves unsupported records, Master Data objects, app-owned data, external identifiers, bespoke transformations, Custom Platform interpretation, or custom migration logic adjustment beyond supported behavior.

**How can teams avoid confusion after an earlier migration run?**

They should define whether the next action continues with the last used configuration, continues with a new configuration, or performs a new migration. Validation should then match the selected action, expected target effect, and Entity Points interpretation.
