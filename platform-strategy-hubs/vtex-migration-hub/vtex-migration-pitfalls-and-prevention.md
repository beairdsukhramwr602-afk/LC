# VTEX Migration Pitfalls and Prevention

VTEX migrations fail most often when the project treats VTEX like a simple destination for products, customers, orders, and pages. VTEX is a hosted enterprise commerce platform where catalog records, SKUs, specifications, pricing, trade policies, Checkout, OMS, marketplace and seller flows, storefront technology, apps, APIs, Master Data, and external systems can all shape the final result.

Prevention starts before Full Migration. The project should identify the records, rules, storefront paths, and integrations that carry business meaning, then use Demo Migration results to confirm whether those expectations can be represented cleanly in the target VTEX environment.

### Pitfall 1: Treating VTEX as a Simple Product, Customer, and Order Target <a href="#pitfall-1-treating-vtex-as-a-simple-product-customer-and-order-target" id="pitfall-1-treating-vtex-as-a-simple-product-customer-and-order-target"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

The migration is judged mainly by record counts. Products, customers, and orders appear in VTEX, but the review does not check whether SKUs are active, specifications work, prices match expected trade policies, orders remain readable in an OMS context, or shoppers can browse and buy through the intended storefront.

This creates a false sense of readiness. The data may exist, but the target commerce model may still be incomplete.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

* Demo Migration review focuses only on total products, customers, and orders.
* Complex SKUs, specifications, trade policies, seller flows, and storefront paths are not sampled.
* The target VTEX account, storefront solution, app stack, or integration plan is still unclear.
* The launch review does not separate migrated records from configuration and implementation work.

#### Prevention <a href="#prevention" id="prevention"></a>

Define VTEX readiness by business behavior, not by record presence alone. Sample catalog, pricing, checkout, OMS, storefront, marketplace, Master Data, and integration-sensitive records before accepting the migration result.

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

A merchant with multiple sales channels should validate one product family with several SKUs, required specifications, channel-specific prices, a trade policy, a representative order, and the expected storefront discovery path. This gives a more reliable signal than checking ten simple products with no commercial variation.

#### Pass Condition <a href="#pass-condition" id="pass-condition"></a>

The migration result proves that representative VTEX records are usable in the target commerce context: products are structured correctly, SKUs can be sold, prices and policies are interpretable, orders are understandable, storefront discovery works, and integration-sensitive data is either handled or clearly excluded.

### Pitfall 2: Migrating Products Without Proving SKU, Specification, and Category Activation <a href="#pitfall-2-migrating-products-without-proving-sku-specification-and-category-activation" id="pitfall-2-migrating-products-without-proving-sku-specification-and-category-activation"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Products are visible in VTEX Admin, but the purchasable SKU structure is incomplete. Required specifications, images, stock, brands, categories, activation states, or SKU relationships may not support storefront display and buying behavior.

This is especially risky when the Source Platform uses product options, configurable products, bundles, modifiers, custom attributes, or non-standard variation logic.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

* Product samples do not include multi-SKU products.
* Source attributes are reviewed only as text fields, not as VTEX product or SKU specifications.
* Category, brand, stock, image, and activation checks are skipped.
* Storefront validation does not confirm that the buyer can select and purchase the intended SKU.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Use catalog samples that expose the real product model. Include products with multiple SKUs, product specifications, SKU specifications, required attributes, images, stock behavior, category placement, and brand values.

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

For a product with size, color, material, and stock-sensitive variations, check the parent product, each purchasable SKU, specification values, images, inventory, category placement, search behavior, and product detail page behavior in the target VTEX storefront.

#### Pass Condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative products and SKUs are active, discoverable, correctly categorized, properly specified, stocked where expected, priced, and purchasable through the intended VTEX storefront and sales context.

### Pitfall 3: Ignoring Price Tables, Trade Policies, Promotions, and Sales-Channel Logic <a href="#pitfall-3-ignoring-price-tables-trade-policies-promotions-and-sales-channel-logic" id="pitfall-3-ignoring-price-tables-trade-policies-promotions-and-sales-channel-logic"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

A product’s base price migrates, but the commercial price behavior does not match how the business sells. Price tables, fixed prices, computed prices, promotions, coupons, customer-specific prices, regional pricing, marketplace prices, or trade-policy-specific availability may be missing or misinterpreted.

The result may look acceptable in a generic catalog check while producing incorrect prices for the real customer, seller, channel, or sales policy.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

* Only base product prices are reviewed.
* B2B, marketplace, wholesale, regional, or channel-specific prices are not sampled.
* Promotion and coupon history is confused with live promotion setup.
* Trade policies are mentioned late, after Demo Migration has already been interpreted.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Prepare pricing and promotion samples by selling context. Identify which prices must be migrated, which rules require VTEX configuration, and which scenarios need Custom Service review because price behavior requires transformation beyond standard service capability.

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A merchant using different prices for retail and wholesale buyers should test at least one SKU with its base price, fixed price or price table behavior, expected trade policy, discount context, and buyer-specific visibility or availability.

#### Pass Condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Target VTEX pricing is understandable and correct for the expected products, buyers, sellers, channels, promotions, and trade policies. Any price behavior outside migration scope is documented before Full Migration.

### Pitfall 4: Flattening Marketplace, Seller, and Order-Flow Meaning <a href="#pitfall-4-flattening-marketplace-seller-and-order-flow-meaning" id="pitfall-4-flattening-marketplace-seller-and-order-flow-meaning"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Seller, marketplace, offer, commission, received SKU, matching, approval, sales-channel, fulfillment, or order-flow context is treated as ordinary product or order text. Marketplace orders may migrate as historical records, but the relationships that operations teams need to understand them are lost or unclear.

This can create confusion for customer service, accounting, seller operations, and fulfillment teams after launch.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

* Marketplace and seller records are not separated from ordinary catalog records.
* Order samples do not include seller, marketplace, complete, or chain flow examples where relevant.
* Seller identifiers, commissions, matching states, received SKU references, or sales-channel mappings are not listed in scope.
* The target review checks order totals but not order-flow meaning.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Treat marketplace and seller architecture as a dedicated planning layer. Identify which relationships must remain operationally meaningful, which values can remain historical labels, and which seller or marketplace requirements need Custom Service review.

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

For a marketplace order, review the seller context, fulfillment context, payment and shipping labels, order status, customer relationship, commission or seller reference where relevant, and whether the operations team can interpret the order without looking back at the Source Platform.

#### Pass Condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Marketplace, seller, and OMS samples preserve the necessary business meaning, or exclusions and reconfiguration work are accepted before Full Migration.

### Pitfall 5: Treating Historical Order Labels as Live Checkout, Payment, and Shipping Configuration <a href="#pitfall-5-treating-historical-order-labels-as-live-checkout-payment-and-shipping-configuration" id="pitfall-5-treating-historical-order-labels-as-live-checkout-payment-and-shipping-configuration"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Migrated orders may display payment labels, shipping labels, tax values, coupon names, or fulfillment statuses. These historical values are then mistaken for proof that live VTEX Checkout, payment methods, shipping options, logistics, tax behavior, and orderForm behavior are ready.

Historical order readability and live checkout readiness are separate outcomes.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

* The project accepts payment and shipping labels in old orders as checkout proof.
* No live test order is performed after target configuration.
* orderForm behavior, seller selection, shipping simulation, coupon use, payment data, or custom checkout fields are not tested.
* Payment provider, anti-fraud, logistics, or tax setup is still pending.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate historical orders separately from live checkout setup. Use migrated order samples to confirm history readability, then test live checkout and order creation inside the configured VTEX environment.

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

A project should review a migrated paid order for historical readability, then separately place a test order that confirms cart behavior, customer profile, delivery option, payment method, promotion/coupon handling, tax behavior, and OMS status progression.

#### Pass Condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Historical orders are readable for business review, and live checkout has been tested through the intended VTEX payment, shipping, tax, coupon, seller, and orderForm behavior.

### Pitfall 6: Overlooking B2B Accounts, Customer Profiles, Master Data, and Custom Fields <a href="#pitfall-6-overlooking-b2b-accounts-customer-profiles-master-data-and-custom-fields" id="pitfall-6-overlooking-b2b-accounts-customer-profiles-master-data-and-custom-fields"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Customers migrate as contact records, but the broader business meaning is missing. B2B organization structures, buyer roles, approval rules, customer segments, consent values, custom profile fields, Master Data records, or external identifiers may not be represented correctly.

This is risky for merchants that rely on account-based buying, special pricing, buyer permissions, customer-specific workflows, or custom data used by apps and integrations.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

* Customer validation uses only name, email, and address.
* B2B accounts, company relationships, buyer roles, approval flows, or custom profile fields are not sampled.
* Master Data entities are not inventoried.
* Customer-related external IDs are not checked against ERP, CRM, loyalty, or other connected systems.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Separate ordinary customer migration from B2B and Master Data requirements. Identify which customer values are standard migration records, which values are target configuration, and which custom fields or data entities require Custom Service review.

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A B2B merchant should sample a company account, buyer user, address, permission or approval context, trade-policy relationship, customer-specific pricing expectation, and any related Master Data or external-system references.

#### Pass Condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Customer and B2B samples show the expected account meaning in VTEX, and custom profile, Master Data, consent, or external-reference requirements are mapped, excluded, configured separately, or routed to Custom Service.

### Pitfall 7: Assuming Storefront, Search, CMS, and SEO Continuity from Data Migration Alone <a href="#pitfall-7-assuming-storefront-search-cms-and-seo-continuity-from-data-migration-alone" id="pitfall-7-assuming-storefront-search-cms-and-seo-continuity-from-data-migration-alone"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Products and categories migrate, but the storefront experience does not preserve how shoppers find, compare, and buy products. FastStore, Store Framework, Legacy CMS Portal, headless storefronts, search behavior, facets, menus, landing pages, redirects, metadata, and priority URLs may need separate planning.

A technically successful data migration can still create launch risk if storefront discovery and SEO continuity are weak.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

* The target storefront solution is not confirmed.
* Search, facets, product listing pages, menus, landing pages, and product detail pages are not sampled.
* Priority URLs and redirects are left until after migration.
* CMS Pages, Blog Posts, metadata, and content relationships are treated as low-priority extras even when they drive traffic.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Plan storefront and SEO continuity before Full Migration. Identify the target storefront solution, priority product and category paths, content pages, metadata, redirects, search/facet behavior, and launch-critical landing pages.

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A merchant with strong organic traffic should test one priority category, several high-value product URLs, a filtered search path, a landing page, metadata, redirect behavior, and the product detail page experience in the target storefront.

#### Pass Condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Priority products, categories, search paths, filters, CMS Pages, Blog Posts, redirects, metadata, and storefront paths are discoverable and acceptable for launch, or separate storefront/SEO work is clearly planned.

### Pitfall 8: Missing App, API, ERP, PIM, WMS, and Headless Integration Dependencies <a href="#pitfall-8-missing-app-api-erp-pim-wms-and-headless-integration-dependencies" id="pitfall-8-missing-app-api-erp-pim-wms-and-headless-integration-dependencies"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

The migration focuses on platform records but misses the systems that depend on them. ERP, PIM, WMS, payment, anti-fraud, CRM, marketplace, app, webhook, VTEX IO, headless, or custom API workflows may rely on identifiers, fields, statuses, or data structures that are not part of ordinary migration output.

After launch, records may exist in VTEX but fail to support daily operations because connected systems cannot interpret them.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

* There is no integration inventory.
* External IDs, app-owned fields, API fields, webhook logic, or Master Data objects are not listed.
* The project assumes integrations will work after records migrate.
* ERP, PIM, WMS, payment, anti-fraud, marketplace, or headless dependencies are discussed only during launch testing.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Build an integration inventory before interpreting Demo Migration results. Mark each dependency as migrated data, target configuration, external-system setup, app configuration, custom logic, or excluded scope.

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant with ERP and PIM dependencies should identify product identifiers, SKU identifiers, inventory references, pricing references, order status values, customer IDs, API fields, and whether each value must be preserved, transformed, reconfigured, or reviewed through Custom Service.

#### Pass Condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Integration-sensitive records and references are mapped, configured, excluded, or routed to Custom Service before Full Migration. No critical external workflow depends on an unreviewed field or identifier.

### Pitfall 9: Accepting Demo Migration by Record Count Only <a href="#pitfall-9-accepting-demo-migration-by-record-count-only" id="pitfall-9-accepting-demo-migration-by-record-count-only"></a>

#### What Goes Wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

The Demo Migration is accepted because the expected number of records appears in VTEX. The review does not test whether those records support buying, pricing, fulfillment, storefront discovery, B2B use, marketplace operation, or integration workflows.

This weakens the value of Demo Migration. The project loses the chance to detect structure, configuration, or Custom Service needs early.

#### Early Warning Signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

* The review checklist contains only counts and spot checks.
* Complex products, orders, prices, trade policies, B2B accounts, seller flows, and integrations are not included.
* The target team cannot explain what a successful VTEX result must prove.
* Full Migration is approved before handling unresolved mapping or configuration questions.

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Use Demo Migration as a decision tool. Review records that expose the real VTEX migration burden, then decide whether the selected approach, Add-ons, configuration work, or Custom Service scope should change before Full Migration.

#### Recommendation Example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

A strong Demo Migration review should include one complex product family, one price/trade-policy case, one B2B or customer-profile case, one marketplace or seller case where relevant, one varied order, one storefront/search path, one SEO-sensitive URL, and one integration-sensitive record.

#### Pass Condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Demo Migration results show whether the planned VTEX migration approach is adequate. Any gaps are resolved through mapping, configuration, Add-ons, accepted exclusions, or Custom Service review before Full Migration begins.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX migration pitfalls usually appear when the project accepts visible records without proving how those records work in the target commerce architecture. SKUs, specifications, price tables, trade policies, Checkout, OMS, marketplace and seller flows, B2B context, Master Data, storefront technology, apps, APIs, and integrations can all affect whether the new store is commercially ready.

Before Full Migration, use Demo Migration to test the scenarios that matter most to real operations. If the sample result exposes unsupported transformations, custom fields, marketplace logic, external-system references, or storefront requirements, resolve the scope through configuration, Add-ons, accepted exclusions, or Custom Service review before treating the migration path as launch-ready.

### FAQs <a href="#faqs" id="faqs"></a>

**Why is record-count validation risky in a VTEX migration?**

Record counts only show that data exists. VTEX validation also needs to prove that SKUs are active, prices and trade policies make sense, orders are readable, storefront discovery works, and integration-sensitive data supports the intended business workflow.

**What is the most common catalog pitfall when moving into VTEX?**

The most common catalog pitfall is treating products as complete when the SKU, specification, category, stock, image, activation, or storefront behavior has not been checked. VTEX readiness depends on the purchasable SKU structure, not only on product records.

**Can migrated orders prove that VTEX checkout is ready?**

No. Migrated orders can help validate historical order readability, but live checkout readiness must be tested separately through the configured VTEX cart, payment, shipping, tax, promotion, seller, and orderForm behavior.

**Why do marketplace and seller records need separate review?**

Marketplace and seller data can include relationships, identifiers, offer states, matching behavior, commissions, fulfillment context, and sales-channel meaning. These values should not be flattened into ordinary product or order notes without confirming whether that outcome is acceptable.

**When should VTEX migration gaps move into Custom Service review?**

Custom Service review is appropriate when the migration requires customization, custom migration logic adjustment, Custom Platform source handling, non-standard SKU or pricing transformation, marketplace or B2B logic, Master Data custom objects, app-owned data, custom checkout fields, or external-system dependencies that exceed standard service capability.
