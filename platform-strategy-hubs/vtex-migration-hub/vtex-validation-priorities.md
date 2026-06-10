# VTEX Validation Priorities

Validation in a VTEX migration should prove that the migrated store can operate inside VTEX’s enterprise commerce structure, not only that records were copied. VTEX stores often depend on catalog depth, SKU-level detail, specifications, pricing rules, trade policies, promotions, Checkout behavior, OMS flows, marketplace or seller architecture, Master Data, storefront solution choices, apps, APIs, and external business systems.

A useful validation review should therefore combine record checks with operational checks. Products should be readable as sellable VTEX catalog items. Orders should be understandable inside OMS. Customer and B2B data should support the intended account experience. Storefront, search, SEO, and URL behavior should support buyer discovery. App, API, ERP, PIM, WMS, and marketplace references should be checked where they influence daily operations.

### What VTEX Validation Should Prove <a href="#what-vtex-validation-should-prove" id="what-vtex-validation-should-prove"></a>

VTEX validation should confirm whether migrated data behaves correctly in the target commerce environment. A product count, customer count, or order count is only the starting point. The migrated data must also support buying, merchandising, fulfillment, customer service, reporting, and integration workflows.

| Validation area                     | What should be proven                                                                                                                                | Why it matters                                                                                           |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Catalog structure                   | Products, SKUs, brands, categories, specifications, images, attachments, services, kits, and collections are represented in a usable VTEX structure. | VTEX selling behavior is SKU-centered and depends on more than product titles and descriptions.          |
| Pricing and selling context         | Prices, price tables, promotions, trade policies, sales channels, and commercial conditions support the intended buyer experience.                   | A catalog can appear complete while the wrong buyer sees the wrong price, availability, or promotion.    |
| Checkout and order creation         | Checkout behavior, cart structure, shipping options, payment context, tax logic, and order creation are reviewed separately from historical data.    | Migrated order history does not prove that new VTEX orders can be placed correctly.                      |
| OMS and historical orders           | Orders are readable with customer, item, payment, shipping, status, seller, marketplace, and fulfillment context.                                    | Customer service and operations teams need historical orders to remain useful after migration.           |
| Customer and Master Data            | Customer profiles, addresses, consent, custom fields, B2B structures, and Master Data records retain usable business meaning.                        | Customer and account data may affect segmentation, B2B access, compliance, and connected workflows.      |
| Marketplace and seller architecture | Seller, marketplace, fulfillment, commission, product, order, and channel context is preserved or intentionally reconfigured.                        | Marketplace operations can fail even when products and orders look correct at record level.              |
| Storefront and search               | Product discovery, category paths, search behavior, filters, content, CMS areas, and SEO-sensitive URLs support launch expectations.                 | VTEX storefront results depend on the chosen storefront solution and search/discovery configuration.     |
| Apps, APIs, and integrations        | App-owned values, API identifiers, webhook behavior, ERP/PIM/WMS references, and external workflows are checked where they matter.                   | Enterprise commerce migration often fails at integration boundaries rather than simple record migration. |

### Catalog, Product, SKU, and Specification Validation <a href="#catalog-product-sku-and-specification-validation" id="catalog-product-sku-and-specification-validation"></a>

Catalog validation should begin with products that represent real selling complexity. Simple products are useful for baseline checks, but they do not prove that VTEX can support the store’s actual catalog behavior.

#### Product and SKU structure <a href="#product-and-sku-structure" id="product-and-sku-structure"></a>

A strong product sample should show whether source products became usable VTEX products and SKUs. The review should confirm product names, descriptions, brands, categories, images, SEO values, variant relationships, SKU codes, inventory-related identifiers, measurements, and sellable status.

The key question is not only whether the product exists. The product should be understandable to the buyer, manageable by the commerce team, and usable by connected systems.

#### Specifications and attributes <a href="#specifications-and-attributes" id="specifications-and-attributes"></a>

VTEX specifications can carry important catalog meaning, including filtering, product comparison, storefront display, and integration logic. Validation should confirm whether important source attributes, custom fields, option values, and product properties are represented in a way that supports the intended storefront and management behavior.

If the source store used custom attributes for merchandising, logistics, B2B eligibility, product compliance, or integration workflows, those examples should be included in the validation sample.

#### Attachments, services, kits, and special product behavior <a href="#attachments-services-kits-and-special-product-behavior" id="attachments-services-kits-and-special-product-behavior"></a>

Some VTEX catalogs use attachments, services, kits, bundles, or product relationships that are not equivalent to ordinary variants. These cases should be validated separately because they can affect cart behavior, pricing, fulfillment, and buyer choice.

When a source product behavior has no direct standard equivalent, the validation result should state whether the behavior was mapped, reconfigured, excluded, or moved into Custom Service scope.

### Pricing, Promotions, and Trade Policy Validation <a href="#pricing-promotions-and-trade-policy-validation" id="pricing-promotions-and-trade-policy-validation"></a>

VTEX pricing validation should check the commercial context around the product, not only the visible price field. Price tables, trade policies, promotions, sales channels, currency context, B2B pricing, and customer-specific conditions can all affect what buyers see and pay.

| Pricing proof area   | Validation focus                                                                                                     | Example check                                                                        |
| -------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Base pricing         | Product and SKU prices appear correctly for representative catalog items.                                            | A simple SKU and a variant-heavy SKU show the expected price.                        |
| Price tables         | Different price contexts are reviewed when the source store used customer groups, regions, channels, or B2B pricing. | A wholesale or B2B profile sees the expected pricing behavior.                       |
| Promotions           | Discounts and promotional logic are reviewed as target configuration, not only historical data.                      | A migrated product behaves correctly under the expected promotion conditions.        |
| Trade policies       | Sales channel, market, B2B, or marketplace conditions are checked where they affect selling.                         | The same SKU is reviewed under more than one selling context when relevant.          |
| Accepted differences | Any pricing behavior that is intentionally changed is documented before launch acceptance.                           | A legacy promotion that will not be recreated is treated as a known launch decision. |

Pricing validation should avoid false confidence. A product can display a correct default price while still failing under a specific trade policy, promotion, seller, marketplace, or B2B context.

### Checkout, Cart, and Order Creation Validation <a href="#checkout-cart-and-order-creation-validation" id="checkout-cart-and-order-creation-validation"></a>

Checkout validation should be separated from historical order validation. A migrated order history proves that past orders are readable. It does not prove that new customers can add products to cart, receive correct shipping options, select valid payment methods, and complete new VTEX orders.

Validation should review representative cart cases, including simple products, variant products, products with attachments or services, mixed carts, discounted carts, shipping-sensitive products, marketplace items, and B2B purchase contexts where applicable.

The Checkout `orderForm` should be treated as a launch-readiness proof area. It can expose whether product availability, pricing, promotions, customer profile data, shipping simulation, payment selection, and seller context work together as expected.

### OMS and Historical Order Validation <a href="#oms-and-historical-order-validation" id="oms-and-historical-order-validation"></a>

VTEX OMS validation should confirm that historical orders remain useful for operations. Orders should be reviewed by status, date range, payment context, shipping context, fulfillment status, customer link, seller or marketplace context, refund or cancellation behavior, and external-system references where relevant.

A good validation sample should include different order types, not only recent successful orders. Useful examples include paid orders, canceled orders, refunded orders, partially fulfilled orders, marketplace orders, seller orders, B2B orders, orders with discounts, orders with multiple shipping methods, and orders linked to ERP or fulfillment systems.

The pass condition is practical readability: customer service, finance, fulfillment, and management teams should be able to interpret the migrated orders without relying on hidden source-store knowledge.

### Customer, B2B, and Master Data Validation <a href="#customer-b2b-and-master-data-validation" id="customer-b2b-and-master-data-validation"></a>

Customer validation should confirm more than names and email addresses. VTEX projects may involve customer profiles, addresses, account fields, consent values, company data, B2B organizations, cost centers, roles, permissions, custom Master Data entities, and external identifiers.

| Customer or account area | What to validate                                                                                               | Why it matters                                                                                  |
| ------------------------ | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Customer profiles        | Names, emails, phone numbers, addresses, and account links are readable and usable.                            | Basic customer data supports account access and customer service.                               |
| B2B context              | Company, role, permission, cost center, or buyer-organization data is preserved or intentionally reconfigured. | B2B migration can fail when individual contacts move but account structure does not.            |
| Master Data              | Custom fields and entities retain their intended business meaning where they are part of scope.                | Master Data often carries project-specific data that ordinary customer tables cannot represent. |
| Consent and preferences  | Marketing, communication, or compliance-relevant values are reviewed where they exist in the source.           | Incorrect consent handling can affect marketing and customer communication after launch.        |
| External identifiers     | ERP, CRM, PIM, marketplace, or support-system IDs are preserved or mapped where required.                      | Connected systems may depend on stable identifiers after launch.                                |

If important customer or B2B information cannot be represented through standard migration behavior, the result should be treated as a scope issue rather than a small validation note.

### Marketplace and Seller Validation <a href="#marketplace-and-seller-validation" id="marketplace-and-seller-validation"></a>

VTEX marketplace and seller validation should confirm whether the migrated result supports the intended operating model. Seller data, marketplace-origin orders, product associations, fulfillment responsibility, commission context, channel rules, and external identifiers may need separate review.

Validation should include examples from each important seller, marketplace, sales channel, or fulfillment model. A single ordinary product or order will not prove that marketplace behavior is launch-ready.

When marketplace data is not part of standard migration scope, the validation result should clearly separate migrated commerce records from channel configuration, seller onboarding, synchronization logic, and external marketplace setup.

### Storefront, Search, CMS, URL, and SEO Validation <a href="#storefront-search-cms-url-and-seo-validation" id="storefront-search-cms-url-and-seo-validation"></a>

VTEX storefront validation depends on the chosen storefront solution and the target implementation plan. FastStore, Store Framework, and older storefront implementations can create different expectations for content, layout, search, filtering, category routing, CMS areas, and URL continuity.

Validation should check high-value product pages, category pages, landing pages, search results, filter behavior, breadcrumb paths, metadata, images, redirects, canonical expectations, and important SEO URLs. The review should include pages that generate revenue or organic traffic, not only easy sample URLs.

A strong result proves that shoppers can find, compare, and buy key products without broken paths or misleading page behavior.

### Apps, APIs, Webhooks, and Integration Validation <a href="#apps-apis-webhooks-and-integration-validation" id="apps-apis-webhooks-and-integration-validation"></a>

VTEX migrations often involve external systems. Apps, APIs, webhooks, ERP, PIM, WMS, CRM, marketing systems, tax services, payment providers, fulfillment platforms, and reporting tools may all depend on data values that are invisible in a simple record-count review.

Validation should identify whether these dependencies are migrated, mapped, reconfigured, rebuilt, excluded, or handled through Custom Service. If an external workflow depends on product IDs, SKU IDs, customer IDs, order IDs, seller IDs, or Master Data records, those identifiers should be tested before launch acceptance.

Integration validation should focus on business outcomes: products synchronize correctly, inventory updates are usable, orders reach the right downstream system, customer records remain matchable, and reports can interpret the new VTEX data.

### Strong Validation Samples for VTEX <a href="#strong-validation-samples-for-vtex" id="strong-validation-samples-for-vtex"></a>

A good VTEX validation set should include records that expose complexity. The following sample types are especially useful:

| Sample type                                                  | Why it should be included                                                           |
| ------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| Product with multiple SKUs and specifications                | Confirms product-to-SKU structure, variant behavior, filtering, and display logic.  |
| Product with attachments, services, kits, or custom behavior | Reveals whether special product behavior is represented or needs separate handling. |
| SKU under multiple price or trade policy contexts            | Tests whether commercial rules work beyond default pricing.                         |
| Order with complex fulfillment or marketplace context        | Confirms OMS readability and seller or channel meaning.                             |
| B2B customer or company account                              | Tests account structure, roles, permissions, pricing, and buyer context.            |
| Master Data record with custom fields                        | Confirms whether custom business data remains useful after migration.               |
| High-value category or search path                           | Checks storefront discovery, filter behavior, and search relevance.                 |
| Priority SEO URL                                             | Reveals URL, redirect, metadata, and page-continuity issues.                        |
| App- or API-dependent record                                 | Tests integration-sensitive values before launch.                                   |

Validation should also include negative or edge cases, such as inactive products, out-of-stock SKUs, canceled orders, refunded orders, non-default trade policies, and older records that still matter operationally.

### How to Interpret Validation Results <a href="#how-to-interpret-validation-results" id="how-to-interpret-validation-results"></a>

A validation issue should be classified by cause. Some findings are data issues, some are target configuration issues, some are implementation decisions, and some indicate scope that belongs in Add-ons or Custom Service.

| Finding type                               | Typical meaning                                                                                | Next action                                                       |
| ------------------------------------------ | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Missing or incorrect migrated value        | The source value did not move as expected or needs mapping review.                             | Review mapping, sample records, and migration settings.           |
| Correct data but wrong storefront behavior | The target storefront, search, CMS, or theme layer needs configuration or implementation work. | Separate migration data review from storefront setup review.      |
| Correct order history but checkout failure | Historical order migration does not prove live checkout readiness.                             | Review target payment, shipping, tax, seller, and Checkout setup. |
| Standard data moved but app data is absent | The missing values are likely app-owned, API-owned, or outside ordinary commerce records.      | Review app, API, webhook, integration, or Custom Service scope.   |
| Count matches but records are unusable     | Record totals are not enough to prove business meaning.                                        | Validate representative records by workflow and user need.        |
| Business rule changed intentionally        | The result is a launch decision, not necessarily a migration defect.                           | Document the accepted difference before Full Migration or launch. |

The goal is not to eliminate every difference from the old store. The goal is to confirm which differences are acceptable, which require configuration, and which require migration-scope correction before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX validation should prove that migrated data works inside a complex enterprise commerce environment. Catalog records, SKUs, specifications, pricing, trade policies, Checkout, OMS, marketplace structures, Master Data, storefront behavior, apps, APIs, and integrations all need review where they affect the business outcome.

Use Demo Migration results to test the records and workflows that carry the highest commercial risk. If validation shows that important behavior depends on custom fields, app-owned data, external identifiers, marketplace workflows, or non-standard transformation, review the requirement before Full Migration and confirm whether Add-ons or Custom Service should be included.

### FAQs <a href="#faqs" id="faqs"></a>

**Is matching record count enough to validate a VTEX migration?**

No. Matching counts are only a baseline. VTEX validation should also confirm product-to-SKU meaning, specifications, pricing context, trade policies, Checkout behavior, OMS readability, marketplace or seller context, storefront discovery, Master Data, apps, APIs, and integrations where they affect operations.

**Which VTEX records should be checked first after Demo Migration?**

Start with complex products, SKU-rich catalog items, important categories, trade-policy-sensitive products, B2B accounts, representative orders, marketplace or seller records, Master Data examples, high-value URLs, and integration-dependent records.

**Why should VTEX Checkout be validated separately from order history?**

Historical orders show whether past order data remains readable. Checkout validation proves whether new buyers can add products to cart, receive the right price and promotion context, select shipping and payment options, and create new orders in the target VTEX environment.

**How should Master Data be reviewed during VTEX validation?**

Master Data should be reviewed by business meaning. Custom fields, entities, account values, external IDs, and workflow-specific records should be checked with the teams or systems that depend on them after launch.

**What should happen if VTEX validation finds app or integration gaps?**

App or integration gaps should be classified before Full Migration. Some gaps may be target configuration work, some may require API or webhook reconfiguration, and custom data handling or custom migration logic adjustment is handled through Custom Service.
