# VTEX Data Model Differences

A migration to VTEX changes more than where store records are stored. VTEX interprets commerce data through a hosted enterprise architecture where catalog structure, SKUs, specifications, pricing, trade policies, checkout data, OMS flows, seller relationships, storefront technology, apps, APIs, and external systems all shape how the migrated store works.

The main data-model question is not whether products, customers, orders, and pages can be moved as records. The question is whether the business meaning behind those records can be represented clearly inside VTEX. A product option, price rule, customer segment, order status, marketplace listing, or app-owned field may need a different target structure from the one used in the Source Platform.

### Why VTEX Data Meaning Is Different <a href="#why-vtex-data-meaning-is-different" id="why-vtex-data-meaning-is-different"></a>

VTEX is a hosted SaaS commerce platform with multiple connected operating layers. Catalog data, storefront discovery, checkout behavior, order management, pricing, promotions, marketplace/seller architecture, apps, and integrations do not behave as one flat database table.

| Source-store concept    | VTEX interpretation                                                                                                                                                              | Migration planning implication                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Product record          | Often becomes a product definition connected to one or more SKUs, categories, brands, specifications, images, and sales-channel availability.                                    | Product samples should include SKU and specification complexity, not only product names and descriptions. |
| Variant or option       | May become a SKU, SKU specification, product specification, attachment, assembly option, service, kit, or custom logic depending on meaning.                                     | Source variants should be classified by business purpose before mapping is accepted.                      |
| Price or discount       | May involve base prices, fixed prices, price tables, computed prices, promotions, coupons, campaign conditions, and trade policies.                                              | Pricing should be validated by trade policy and sales context, not only by visible product price.         |
| Checkout/cart data      | VTEX checkout behavior centers around the `orderForm`, including customer profile, address, payment, shipping, seller, marketing, and custom information.                        | Cart, checkout, and customer-field expectations should be separated from migrated historical orders.      |
| Order history           | Orders may follow marketplace, seller, complete, or chain flows with OMS statuses, payment approval, invoicing, delivery, pickup, tracking, and back-office integration context. | Order validation should confirm readability and business context, not only order count.                   |
| Customer data           | Customer meaning may involve profile information, addresses, B2B context, Master Data, organizations, permissions, and external identifiers.                                     | Customer records may need mapping beyond basic name and email fields.                                     |
| Storefront content      | Storefront meaning depends on FastStore, Store Framework, Legacy CMS Portal, headless implementation, search, CMS, menus, and URL behavior.                                      | Content and SEO continuity should be planned against the target storefront solution.                      |
| App or integration data | Business meaning may live in VTEX IO apps, Master Data, external ERP/PIM/WMS systems, marketplace connectors, or custom APIs.                                                    | App-owned and integration-owned data should be scoped before Full Migration.                              |

This makes VTEX data-model review especially important for merchants with complex catalogs, multiple sales channels, B2B structures, marketplace operations, custom checkout data, external-system identifiers, or storefront modernization goals.

### Products, SKUs, Categories, Brands, and Specifications <a href="#products-skus-categories-brands-and-specifications" id="products-skus-categories-brands-and-specifications"></a>

In VTEX, product data should be understood through the relationship between product definitions and purchasable SKUs. A product describes the commercial item, while a SKU represents the specific purchasable variation or physical unit. This distinction is central to migration quality because many Source Platforms use variant, option, attribute, modifier, or child-product structures differently.

A source product with color and size options may become multiple SKUs. A source product with informational attributes may need product specifications or SKU specifications. A source product with custom fields may need supported field mapping, Master Data handling, app review, or Custom Service if the meaning cannot fit standard structures.

#### Product and SKU translation <a href="#product-and-sku-translation" id="product-and-sku-translation"></a>

Product-to-SKU translation should preserve how shoppers buy, how managers maintain stock, and how external systems recognize items. The review should include:

* product names, descriptions, brands, categories, images, and visibility;
* SKU codes, reference identifiers, stock-sensitive variations, prices, and activation expectations;
* product specifications and SKU specifications used for filtering, display, comparison, or operations;
* products that depend on category or specification group behavior;
* items with multiple SKUs, inactive SKUs, special availability rules, or external identifiers.

A migration can look complete at product-count level while still failing commercially if SKUs are inactive, specifications are misclassified, images are attached to the wrong level, or category placement does not support storefront discovery.

#### Category, brand, and specification meaning <a href="#category-brand-and-specification-meaning" id="category-brand-and-specification-meaning"></a>

VTEX categories, brands, specification groups, product specifications, and SKU specifications affect how the catalog is organized and exposed. In some Source Platforms, these values may appear as categories, tags, attributes, filters, brands, custom fields, collections, or extension data. Their business meaning should determine how they are interpreted in VTEX.

A category used only for internal management should not automatically be treated like a storefront navigation path. A product attribute used for filtering should not be flattened into a plain description field. A brand value used in search or merchandising should remain usable after migration.

### Attachments, Assembly Options, Services, Kits, and Collections <a href="#attachments-assembly-options-services-kits-and-collections" id="attachments-assembly-options-services-kits-and-collections"></a>

Some source-store product behavior cannot be represented accurately as a basic variant. VTEX has several structures that can carry additional product meaning, and each one should be considered only when it matches the actual business behavior.

| Source behavior                         | Possible VTEX interpretation                                      | Review point                                                                             |
| --------------------------------------- | ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Add-on choice collected during purchase | Attachment or custom checkout/product behavior                    | Confirm whether the choice affects fulfillment, price, customer input, or only display.  |
| Configurable bundled product            | Kit, assembly option, app behavior, or custom logic               | Confirm whether stock, price, and fulfillment depend on each component.                  |
| Optional service sold with a product    | Service structure or separate product relationship                | Confirm whether the service affects order handling, invoicing, or customer selection.    |
| Curated product group                   | Collection, category, search/filter result, or merchandising rule | Confirm whether the grouping is permanent catalog structure or storefront merchandising. |
| Custom product configurator             | Custom Service review                                             | Confirm what must remain selectable, priced, stored, and visible after migration.        |

This distinction matters because forcing every source option into a SKU can create an overcomplicated catalog, while flattening true purchasable choices can damage the buying experience.

### Prices, Price Tables, Promotions, and Trade Policies <a href="#prices-price-tables-promotions-and-trade-policies" id="prices-price-tables-promotions-and-trade-policies"></a>

VTEX pricing is not limited to a single product price. Price meaning may involve base prices, fixed prices, price tables, computed prices, trade policies, sales channels, promotions, coupons, and campaign audiences. Source-store pricing should be reviewed for the commercial rule behind each value.

A product price used for all buyers may map differently from a price that depends on customer group, region, sales channel, marketplace, B2B account, or promotion. A legacy discount rule may not have the same target meaning as a VTEX promotion. A price stored in an ERP or PIM may need integration planning rather than simple record migration.

#### Trade-policy impact <a href="#trade-policy-impact" id="trade-policy-impact"></a>

Trade policies can affect which products, prices, payment conditions, shipping options, and sales channels are available in a specific commercial context. This means product and price validation should not only check the default storefront view. It should also check whether the intended sales contexts see the correct catalog and price behavior.

Trade-policy-sensitive migration planning should include:

* products with channel-specific availability;
* SKUs with different prices by sales channel or buyer context;
* B2B or negotiated pricing examples;
* marketplace or seller scenarios;
* promotions and coupons that affect specific audiences or channels.

When source pricing logic depends on custom code, external systems, or unsupported rule combinations, the requirement should be reviewed for Advanced Data Mapping, Advanced Data Configure, or Custom Service depending on whether the need is field mapping, value adjustment, or custom logic.

### Customers, Profiles, Master Data, and B2B Context <a href="#customers-profiles-master-data-and-b2b-context" id="customers-profiles-master-data-and-b2b-context"></a>

Customer migration into VTEX should distinguish between basic customer identity and the broader customer context needed for operations. Basic customer records may include names, emails, phone numbers, addresses, and order relationships. More complex scenarios may involve B2B organizations, roles, permissions, price access, sales representatives, credit terms, external IDs, consent values, segmentation, or Master Data records.

Master Data can be important when customer or business information does not fit ordinary customer fields. It may also support custom processes, storefront forms, external integrations, or app behavior. That does not mean every custom field should automatically move into Master Data, but it does mean custom customer meaning should be identified before migration acceptance.

B2B customer structures need particular care. A Source Platform may store companies, departments, contacts, approvals, buyer roles, negotiated pricing, tax identifiers, or account hierarchies in different ways. VTEX planning should clarify which parts are customer data, which parts are B2B configuration, which parts are app or integration data, and which parts require Custom Service.

### Orders, OMS Flows, Sellers, and Marketplaces <a href="#orders-oms-flows-sellers-and-marketplaces" id="orders-oms-flows-sellers-and-marketplaces"></a>

Order data in VTEX is interpreted through OMS behavior and the commercial flow behind the order. A migrated order should remain useful for customer service, finance, fulfillment review, reporting, and operational history. It should also be clear which parts of the order are historical record context and which parts belong to live order processing setup.

VTEX can involve different order-flow patterns, including marketplace, seller, complete, and chain flows. These patterns can affect order origin, seller responsibility, marketplace context, fulfillment handling, invoicing, status interpretation, and integration touchpoints.

| Order context      | Meaning to preserve                                                                              | Validation focus                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| Direct store order | Customer, products, totals, payment label, shipping label, tax, status, and fulfillment context. | Confirm the order is readable and connected to the correct customer and purchased items.         |
| Marketplace order  | Marketplace origin, seller relationship, commission or channel context where relevant.           | Confirm marketplace meaning is not reduced to a generic order note if it affects operations.     |
| Seller order       | Seller identity, fulfillment responsibility, order status, shipping, and back-office connection. | Confirm seller context remains visible or otherwise handled in the target operating model.       |
| B2B order          | Company, buyer, negotiated pricing, approval or account context where relevant.                  | Confirm B2B meaning is not lost when order history is reviewed.                                  |
| Integrated order   | ERP, WMS, PIM, accounting, invoice, or external reference values.                                | Confirm integration-sensitive identifiers are migrated, mapped, excluded, or handled separately. |

Historical orders should not be used as proof that live checkout, payment, tax, shipping, invoicing, and fulfillment are fully configured. Those are target setup and validation responsibilities.

### Checkout, orderForm, Payment, Shipping, and Custom Fields <a href="#checkout-orderform-payment-shipping-and-custom-fields" id="checkout-orderform-payment-shipping-and-custom-fields"></a>

VTEX checkout behavior is closely tied to the `orderForm`. It can carry cart items, customer profile data, client preferences, addresses, shipping data, payment data, seller data, marketing data, coupons, and custom information depending on implementation.

Source checkout data may not have a one-to-one target equivalent. A custom checkout field from the Source Platform may become a supported field, Master Data, app-owned data, custom checkout behavior, an integration field, or an accepted exclusion. The right decision depends on whether the value must be displayed, searched, fulfilled, reported, sent to an ERP, or reused in future checkout flows.

Payment and shipping values also need separation:

* historical payment labels help explain old orders;
* live payment methods require VTEX payment configuration and provider setup;
* historical shipping labels help explain old fulfillment choices;
* live shipping and logistics behavior requires target configuration and testing;
* tax values in historical orders do not automatically define live tax behavior;
* payment provider, anti-fraud, gift card, pickup, delivery, and shipping-rate behavior may need separate integration review.

This separation prevents migrated history from being mistaken for operational readiness.

### Storefront, Search, CMS, and URL Meaning <a href="#storefront-search-cms-and-url-meaning" id="storefront-search-cms-and-url-meaning"></a>

Storefront data meaning in VTEX depends on the selected storefront solution and implementation model. FastStore, Store Framework, Legacy CMS Portal, headless storefronts, CMS structures, search behavior, themes, templates, and apps can affect how migrated catalog and content are seen by shoppers.

A product can be migrated correctly while still failing storefront expectations if it is not searchable, does not appear under the right category, lacks usable specifications, has broken images, uses weak metadata, or does not match the target storefront’s content structure.

Search and discovery should be reviewed through:

* categories, departments, filters, facets, and specification behavior;
* product and SKU names, brands, images, and metadata;
* collections, merchandising groups, banners, and storefront placements;
* high-value product and category URLs;
* redirects, canonical expectations, and SEO metadata;
* content pages, landing pages, CMS Pages, and Blog Posts where relevant to the migration scope.

Content migration should be planned around the target storefront architecture instead of assuming that pages, blocks, banners, and navigation can move without interpretation.

### Apps, APIs, Master Data, and External Systems <a href="#apps-apis-master-data-and-external-systems" id="apps-apis-master-data-and-external-systems"></a>

VTEX stores often depend on apps, APIs, Master Data, marketplace connectors, ERP systems, PIM systems, WMS systems, payment providers, anti-fraud providers, recommendation systems, search apps, marketing tools, analytics tools, and custom middleware. These systems can own data that looks like ordinary store information but functions as integration logic.

Migration planning should classify each dependency:

| Dependency type                         | Typical data meaning                                                                     | Planning decision                                                                                 |
| --------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| VTEX IO or storefront app               | App settings, storefront behavior, merchandising, search, checkout, or integration data. | Decide whether the app data migrates, is reconfigured, or is excluded.                            |
| Master Data                             | Custom records, customer context, forms, operational references, or integration values.  | Decide whether fields map into supported structures or need Custom Service.                       |
| ERP/PIM/WMS                             | Product, inventory, price, fulfillment, invoice, or order synchronization logic.         | Decide which system remains authoritative after migration.                                        |
| Marketplace connector                   | Seller, offer, matching, commission, cataloging, channel, or synchronization data.       | Decide whether marketplace context is target configuration, migrated data, or custom integration. |
| External payment or anti-fraud provider | Payment authorization, risk review, gift card, or transaction context.                   | Separate historical labels from live provider setup and testing.                                  |
| Custom API or middleware                | Business-specific workflows and external identifiers.                                    | Review for Custom Service when standard migration cannot preserve the required behavior.          |

Custom Platform sources and unsupported third-party data should be reviewed through Custom Service. Supported field mapping and value adjustments may fit Add-ons when the requirement stays within available service capability, but custom migration logic adjustment belongs in Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX data-model planning should focus on meaning, not only record movement. Products must become usable VTEX catalog and SKU structures. Prices must make sense with price tables and trade policies. Orders must remain readable inside OMS context. Customer records may need profile, B2B, Master Data, or integration interpretation. Storefront content, search, URLs, apps, APIs, and external systems may carry business meaning that ordinary entity counts do not reveal.

Before approving the migration scope, choose Demo Migration samples that prove the hardest parts of the model: complex products, multiple SKUs, specifications, trade-policy pricing, B2B customers, marketplace or seller orders, custom checkout fields, Master Data, app-owned data, integration identifiers, and priority URLs. Use the results to decide whether Standard Service is enough, whether Add-ons can handle mapping or value changes, or whether Custom Service is required for custom logic or unsupported data.

### FAQs <a href="#faqs" id="faqs"></a>

**Why is product-to-SKU translation important in VTEX?**

VTEX separates product meaning from SKU meaning. A product describes the item, while the SKU represents the purchasable variation or physical unit. If source variants, options, or child products are mapped incorrectly, shoppers may see incomplete choices, wrong prices, inactive SKUs, or unreliable inventory behavior.

**Do source product attributes always become VTEX specifications?**

No. Some source attributes may become product specifications, SKU specifications, filters, descriptions, custom fields, app-owned data, or excluded values. The correct treatment depends on whether the attribute affects discovery, purchase choices, operations, reporting, or integrations.

**How should source-store price rules be reviewed for VTEX?**

Price rules should be reviewed by commercial meaning. A simple default price is different from a price that depends on price tables, customer segment, B2B account, marketplace channel, promotion, coupon, or trade policy. Complex pricing may need mapping, value adjustment, target configuration, or Custom Service review.

**Are historical orders the same as VTEX OMS setup?**

No. Historical orders help preserve past transaction context, but OMS setup controls how new VTEX orders move through payment approval, invoicing, fulfillment, delivery, pickup, seller, marketplace, and integration workflows. Both should be validated separately.

**When does VTEX app or API data need Custom Service?**

Custom Service is required when app-owned data, Master Data, external-system identifiers, custom API behavior, marketplace connector logic, B2B structures, or unsupported third-party data cannot be represented through standard service capability or available Add-on behavior.
