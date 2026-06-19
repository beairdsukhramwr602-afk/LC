# Pricing and Promotion Logic Across Platforms

Pricing and promotion logic is the commercial rule layer that decides what a customer should pay, why that amount applies, and how the store should explain the result. A product may have a base price, a sale price, a variant-specific price, a customer-tier price, a quantity break, a catalog discount, a coupon, a free-shipping incentive, a subscription adjustment, a loyalty reward, and a tax or regional price condition. The storefront may show only one final amount, but that amount can come from several data objects and calculation rules.

In an e-commerce platform, pricing data is not limited to a product price field. It can be stored across product records, variant records, price lists, customer groups, catalog rules, cart rules, coupon tables, tax settings, shipping rules, currency configuration, subscription systems, loyalty apps, enterprise pricing engines, ERP integrations, or custom extension data. Promotion behavior is even more dependent on surrounding structures because a discount usually needs eligibility conditions, exclusions, date ranges, usage limits, priority, stacking rules, and a calculation sequence.

A technical review of pricing and promotion logic therefore needs to examine where the commercial rule is stored, what data it depends on, how the platform calculates it, and how the result appears in cart, checkout, order records, reports, refunds, and customer communications.

### What Pricing and Promotion Logic Represents in an E-commerce Store <a href="#what-pricing-and-promotion-logic-represents-in-an-e-commerce-store" id="what-pricing-and-promotion-logic-represents-in-an-e-commerce-store"></a>

Pricing and promotion logic represents the store’s commercial decision system. It answers several questions at the same time: what an item normally costs, whether a customer qualifies for a different price, whether the cart qualifies for a discount, which products are excluded, whether shipping is affected, whether tax is calculated before or after a discount, and whether multiple incentives can combine.

The same store may use different pricing layers for different business purposes:

| Pricing or promotion layer      | What it represents                                                               | Store behavior affected                                                                  |
| ------------------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Base price                      | The normal selling price for a product or variant                                | Product page display, cart line amount, feeds, reporting, and order totals               |
| Sale price or compare-at price  | A temporary or merchandising price difference                                    | Storefront badges, crossed-out prices, campaign pages, and conversion messaging          |
| Variant-level price             | Different prices for size, color, material, bundle size, or configuration        | Option selection, cart totals, inventory-linked purchasing, and fulfillment expectations |
| Customer-group price            | A price reserved for wholesale, retail, VIP, B2B, employee, or membership groups | Login-based pricing, account pricing, customer segmentation, and contract selling        |
| Tiered or quantity pricing      | A price that changes by purchase quantity                                        | Bulk purchasing, wholesale behavior, price tables, and cart calculation                  |
| Catalog rule                    | A discount applied before the customer reaches the cart                          | Category merchandising, product listing display, and sale visibility                     |
| Cart rule                       | A discount applied based on cart conditions                                      | Coupon behavior, cart totals, checkout incentives, and threshold offers                  |
| Shipping incentive              | Free or reduced shipping under defined conditions                                | Checkout conversion, regional offers, and margin calculation                             |
| Loyalty or reward rule          | Credit, points, membership discount, or earned benefit                           | Customer retention, account behavior, and repeat purchase economics                      |
| Subscription or recurring price | Price logic for repeat purchases or membership cycles                            | Billing, renewals, account management, and order automation                              |
| External price source           | Price controlled by ERP, POS, PIM, marketplace, or pricing engine                | Source-of-truth management, synchronization, and operational governance                  |

These layers can overlap. A product may have a sale price, a customer-specific price, a category promotion, a coupon, and a free-shipping threshold at the same time. The important technical question is not only whether each layer exists, but which layer wins, which layers combine, and how the platform records the final result.

### Common Data Structures Behind Product Prices <a href="#common-data-structures-behind-product-prices" id="common-data-structures-behind-product-prices"></a>

Product pricing usually begins with a price field, but most stores need more structure than one value. A simple product may have one base price. A variant product may store a price per SKU. A marketplace-connected or B2B store may store price lists by market, currency, customer group, catalog, contract, or channel.

Common product-price fields include:

| Field or property               | Typical function                                               | Technical concern                                                                   |
| ------------------------------- | -------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Product ID or variant ID        | Connects a price to the sellable item                          | Determines whether the price applies to the parent product or an individual variant |
| Base price                      | Standard selling price                                         | May be product-level in one platform and variant-level in another                   |
| Sale price                      | Reduced active price                                           | May have independent date ranges or depend on campaign rules                        |
| Compare-at or list price        | Reference price shown beside the active price                  | May affect storefront display without changing the calculated price                 |
| Cost or margin field            | Internal cost basis                                            | Often not customer-facing but important for reporting or margin review              |
| Currency code                   | Currency for the price value                                   | May require price lists, exchange rules, or market-specific values                  |
| Tax class                       | Tax category assigned to the product                           | Affects tax calculation and regional compliance behavior                            |
| Customer group or price list ID | Eligibility relationship                                       | Controls B2B, wholesale, membership, or contract pricing                            |
| Quantity threshold              | Breakpoint for tiered pricing                                  | Determines when a different unit price applies                                      |
| Channel or market scope         | Storefront, region, marketplace, or sales channel relationship | Controls which price appears in each selling context                                |
| Start and end date              | Activation window                                              | Controls campaign timing and stale-price risk                                       |
| Priority or sort order          | Conflict-resolution value                                      | Determines which price or rule wins when several values apply                       |

A platform that stores one product price can behave very differently from a platform that stores many price rows per product, per variant, per customer group, per market, or per channel. That difference affects how prices are displayed, edited, exported, synchronized, and validated.

### Promotion Rules as Condition-Based Data <a href="#promotion-rules-as-condition-based-data" id="promotion-rules-as-condition-based-data"></a>

Promotion records usually contain two parts: a trigger and a rule. The trigger may be a coupon code, an automatic discount, a customer segment, a campaign schedule, or a cart condition. The rule decides what happens when the trigger is valid.

A promotion rule can contain many condition fields:

| Promotion condition  | Examples                                                                                                    | What can change across platforms                                                  |
| -------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Product eligibility  | Specific SKUs, variants, categories, collections, brands, tags, vendors, or attributes                      | Targeting may use different object types or query logic                           |
| Exclusions           | Sale items, clearance items, gift cards, restricted brands, bundles, subscriptions, or certain variants     | Exclusion support may be limited or require a separate rule                       |
| Customer eligibility | Customer groups, tags, segments, email domains, membership status, loyalty level, or B2B account            | Segmentation models may not match one-to-one                                      |
| Cart threshold       | Minimum spend, minimum quantity, maximum spend, item count, or subtotal after exclusions                    | Threshold calculation can happen before or after discount, tax, or shipping       |
| Discount action      | Percentage off, fixed amount off, buy-one-get-one, free item, free shipping, tiered offer, or bundle price  | The Target Platform may support some actions natively and require apps for others |
| Usage limit          | Per-customer, per-code, per-order, lifetime, or campaign-level limit                                        | Historical usage may not transfer in the same way                                 |
| Date range           | Start date, end date, scheduled campaign, time zone, or recurring window                                    | Date/time behavior may depend on platform timezone and scheduler behavior         |
| Stacking rule        | Combine with product discounts, order discounts, shipping discounts, loyalty rewards, or manual adjustments | Discount combination logic is often platform-specific                             |
| Priority             | Which rule applies first or wins conflicts                                                                  | Rule priority can be explicit, implicit, or unavailable                           |

A coupon code can look identical after migration while its rule behaves differently. The code is only the customer-facing identifier. The platform’s rule engine controls qualification, exclusions, discount amount, combination behavior, and final calculation.

### Calculation Order and Discount Stacking <a href="#calculation-order-and-discount-stacking" id="calculation-order-and-discount-stacking"></a>

Calculation order is one of the most important differences between platforms. Two stores can use the same discount label and still calculate different totals if one platform applies the discount to line items before tax while another applies it to order subtotal after other discounts.

Common calculation-order questions include:

* Is the discount applied to the product line, cart subtotal, shipping charge, tax-inclusive amount, or tax-exclusive amount?
* Does the sale price replace the base price before coupon calculation?
* Can a coupon apply to an already discounted item?
* Are product discounts and order discounts allowed to combine?
* Does a free-shipping discount apply before or after shipping method selection?
* Does the platform prorate order-level discounts across line items?
* Does refund logic preserve the original discount allocation?
* Does the platform round each line item, each tax line, or the final order total?

Stacking behavior is especially sensitive. Some platforms allow multiple automatic discounts and coupon codes to combine. Others allow only one discount code, separate product discounts from order discounts, restrict free-shipping combinations, or require app logic for advanced combinations. When stacking rules change, a promotion may become too generous, too restrictive, or commercially different even when the visible discount amount looks familiar.

### How Platform Models Differ <a href="#how-platform-models-differ" id="how-platform-models-differ"></a>

Platforms differ in how much pricing and promotion behavior is native, configurable, extension-driven, or external-system-controlled.

SaaS platforms often provide structured product prices, variant prices, discount codes, automatic discounts, market-specific prices, and app-based extensions. They may simplify administrative work, but they may also limit discount combinations, advanced B2B pricing, rule priority, or complex campaign structures unless the store uses additional apps or higher-tier features.

Open-source platforms often provide deeper access to catalog price rules, cart price rules, customer groups, tax classes, and extension tables. This can support complex commercial logic, but the resulting data may be distributed across core tables, modules, custom attributes, serialized configuration, and custom code. The same visible promotion may depend on several extension-owned records.

Enterprise platforms may separate prices into price books, shared catalogs, customer groups, websites, markets, contracts, and business accounts. B2B pricing may depend on account hierarchy, company permissions, buyer role, negotiated contract, purchase list, or ERP synchronization. A single product can have many commercial prices depending on customer and channel context.

Marketplace-connected or omnichannel stores may not treat the e-commerce platform as the only price source. Prices may be pushed from ERP, POS, PIM, marketplace tools, repricing engines, or channel managers. In that model, the store may display and process prices, but the source of truth may live outside the storefront platform.

### Relationships With Other Store Data <a href="#relationships-with-other-store-data" id="relationships-with-other-store-data"></a>

Pricing and promotions depend heavily on surrounding store structures. A category promotion depends on category or collection assignments. A customer-tier price depends on customer groups or segments. A bundle discount depends on product relationships and inventory logic. A subscription discount depends on recurring billing data. A regional promotion depends on market, currency, shipping zone, tax, or location settings.

Common dependency points include:

| Dependency                        | Pricing or promotion impact                                                                                               |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Product and variant structure     | Determines whether a price or discount applies to the parent product, individual SKU, bundle, kit, or configurable choice |
| Attributes and tags               | Can drive eligibility, exclusions, automated collections, sale pages, or customer-facing labels                           |
| Category and collection structure | Often controls catalog rules, landing-page discounts, seasonal promotions, and merchandising groups                       |
| Customer groups and segments      | Determines B2B, wholesale, loyalty, membership, employee, or VIP pricing eligibility                                      |
| Tax settings                      | Controls tax-inclusive pricing, tax classes, regional calculation, and invoice totals                                     |
| Shipping zones and methods        | Controls free shipping, region-specific offers, threshold behavior, and checkout incentives                               |
| Currency and market settings      | Controls local pricing, rounding, display values, and exchange-rate differences                                           |
| Inventory and fulfillment data    | Can affect bundle offers, backorder promotions, subscription availability, and regional selling                           |
| External systems                  | Can override or synchronize prices, discounts, customer eligibility, or order totals                                      |

A pricing rule should be reviewed together with the structures it depends on. If a product moves from one variant model to another, if category assignments change, or if customer groups are rebuilt as tags or segments, the promotion may require reinterpretation even when the rule name remains recognizable.

### Platform-Specific Features and Exclusive Behaviors <a href="#platform-specific-features-and-exclusive-behaviors" id="platform-specific-features-and-exclusive-behaviors"></a>

Some pricing and promotion behavior is tied to features that do not exist in every platform. These features can be native, app-based, extension-based, enterprise-only, or externally synchronized.

Important examples include:

* market-specific price lists and regional storefront pricing;
* customer-group and B2B account pricing;
* shared catalogs and company-specific price books;
* wholesale quantity breaks and tiered unit prices;
* subscription discounts and recurring-order price rules;
* bundle, kit, and configurable-product price calculations;
* loyalty point redemption and reward-credit behavior;
* gift-card and store-credit interactions;
* automatic discounts that apply without a coupon code;
* buy-one-get-one and free-gift campaign logic;
* price rounding by currency, market, tax rule, or payment provider;
* ERP-controlled pricing and account contract prices;
* marketplace repricing and channel-specific prices.

These behaviors are not interchangeable. A customer-group price is not always the same as a customer tag discount. A catalog rule is not always equivalent to a cart rule. A compare-at price is not the same as a sale price with a campaign schedule. A bundle price calculated by an app is not the same as a native variant price. Preserving the intended commercial behavior requires identifying which platform feature produced the original result.

### What Often Breaks When Pricing Logic Is Misunderstood <a href="#what-often-breaks-when-pricing-logic-is-misunderstood" id="what-often-breaks-when-pricing-logic-is-misunderstood"></a>

Pricing problems can be difficult to detect because the admin record may look correct while the storefront or checkout result is wrong.

Common failure patterns include:

| Failure pattern                                          | Likely cause                                                   | Customer or business impact                                  |
| -------------------------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------ |
| Correct coupon code, wrong discount amount               | Rule action or eligible subtotal changed                       | Customer complaints, campaign errors, margin loss            |
| Discount applies to excluded products                    | Exclusion model did not transfer cleanly                       | Margin risk and brand-policy issues                          |
| Wholesale customers see retail prices                    | Customer group or price list relationship changed              | B2B account friction and support escalation                  |
| Sale badge appears without the intended calculated price | Display price and active price are stored separately           | Storefront confusion and inaccurate merchandising            |
| Cart total differs from expected amount                  | Calculation order, tax handling, or rounding differs           | Checkout abandonment, accounting mismatch, refund complexity |
| Free shipping applies too broadly or not at all          | Shipping rule, zone, threshold, or method relationship changed | Margin loss or conversion drop                               |
| Loyalty or subscription discount disappears              | App-owned or external pricing logic was not recreated          | Retention issues and recurring-order disruption              |
| Multi-currency prices drift unexpectedly                 | Exchange, market price, or rounding behavior changed           | Regional price inconsistency and reporting confusion         |

These issues are structural. They usually come from non-equivalent platform models, not from missing labels alone.

### How to Inspect Pricing and Promotion Data Before Migration <a href="#how-to-inspect-pricing-and-promotion-data-before-migration" id="how-to-inspect-pricing-and-promotion-data-before-migration"></a>

A useful pre-migration review should separate price values from commercial logic. The price value is the number stored on a product or variant. The commercial logic is the condition set that decides whether that number changes.

Merchants should inspect:

* products and variants with non-standard prices;
* active sale prices and scheduled campaign prices;
* customer-group, wholesale, B2B, or membership prices;
* tiered, volume, subscription, and bundle pricing;
* active coupon codes and automatic discounts;
* catalog rules and cart rules;
* usage limits, date ranges, priorities, and stacking rules;
* product, category, customer, region, shipping, and tax dependencies;
* app, extension, ERP, POS, loyalty, subscription, or marketplace-controlled pricing;
* historical rules that should be retired instead of transferred.

The strongest review starts with commercially important scenarios rather than every obsolete coupon. Active launch-period offers, B2B account prices, loyalty discounts, subscription prices, high-margin exclusions, and free-shipping thresholds deserve closer review than expired seasonal campaigns.

### Migration Implications for Pricing and Promotions <a href="#migration-implications-for-pricing-and-promotions" id="migration-implications-for-pricing-and-promotions"></a>

Pricing and promotion migration should preserve intended commercial outcomes where the Target Platform can support them. Some data can be moved as direct values. Some rules need to be recreated in native platform settings. Some behaviors need app replacement, configuration, manual setup, or custom handling because the Target Platform uses a different pricing model.

The main implication is that pricing should be validated through realistic customer and cart scenarios. A rule should not be approved only because a coupon code or price value exists in the admin area.

Important scenarios include:

* a normal retail product with no promotion;
* a variant with a different price from the parent product;
* a product with sale price and compare-at display;
* a category or collection-based discount;
* a customer-group or B2B account price;
* a quantity break or tiered price;
* a coupon with exclusions and usage limits;
* a cart with stacked or non-combinable discounts;
* a free-shipping threshold;
* a tax-sensitive order;
* a multi-currency or regional order;
* a subscription, bundle, loyalty, or extension-driven pricing scenario.

Next-Cart should enter the discussion when pricing rules cannot be represented by direct mapping alone. Supported value adjustments may relate to Advanced Data Configure. Relationship mapping may relate to Advanced Data Mapping. Selected inclusion or exclusion of records may relate to the Data Filter Add-on. When expected behavior depends on unsupported rule transformation, app-owned logic, custom pricing tables, outside-system identifiers, or bespoke calculation logic, Custom Service review is the safer boundary.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Pricing and promotion logic is a data architecture problem, not only a marketing setup problem. The visible price, coupon code, or discount label is only the surface of a larger rule system that may include products, variants, categories, customers, tax settings, shipping zones, currencies, external systems, and platform-specific calculation order.

Before migration, the most important task is to identify which commercial behaviors must remain accurate after launch. Base prices, sale prices, customer-group pricing, tiered pricing, cart rules, catalog rules, shipping incentives, and extension-driven discounts should be reviewed according to the data structures and platform features that produce them.

For complex pricing behavior, use representative cart scenarios to validate the outcome. If a rule depends on unsupported discount structures, custom pricing logic, app or extension data, external price sources, or non-equivalent platform features, clarify the required handling before broader execution.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can the same promotion behave differently on another platform?**

A promotion is controlled by more than its name or coupon code. Eligibility conditions, exclusions, subtotal rules, tax timing, shipping behavior, discount stacking, priority, usage limits, and rounding can all differ between platform rule engines.

**What is the difference between a product price and a pricing rule?**

A product price is a stored value attached to a product, variant, price list, or market. A pricing rule decides when that value changes or when an additional discount applies based on customer, cart, product, category, quantity, date, shipping, or other conditions.

**Should expired promotions be migrated?**

Not always. Expired, obsolete, test, or low-impact promotions can often be retired. Active campaigns, customer-specific pricing, launch-period offers, wholesale prices, loyalty rules, subscription discounts, and margin-sensitive exclusions need closer review.

**How should pricing and promotion behavior be validated?**

Validation should use realistic customer and cart scenarios. Review product-specific discounts, excluded items, customer-group prices, tiered pricing, stacked discounts, free-shipping thresholds, tax-sensitive totals, regional prices, and extension-driven pricing behavior.

**When does pricing logic need custom handling?**

Custom handling may be needed when the expected result depends on unsupported rule transformation, app or extension data, loyalty logic, subscription pricing, customer-specific price books, external ERP or POS pricing, complex stacking rules, or bespoke calculation behavior that the Target Platform cannot recreate directly.
