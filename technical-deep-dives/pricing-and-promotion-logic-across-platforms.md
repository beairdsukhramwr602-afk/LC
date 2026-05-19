# Pricing and Promotion Logic Across Platforms

Pricing and promotion logic often looks simple from the storefront, but it can carry some of the most sensitive commercial behavior in an E-commerce Platform Migration.

A coupon code, sale price, customer-tier discount, or free-shipping offer may still exist after migration, but the way the Target Platform calculates and applies the rule can change. The risk is not only whether the discount record moves. The risk is whether the migrated store still produces the intended commercial result for the right products, customers, carts, regions, and order conditions.

This matters because pricing and promotions affect revenue, margin, conversion, customer trust, support workload, reporting, and launch confidence. A promotion that looks familiar in the admin area can still behave differently when the cart is built, tax is calculated, shipping is selected, or another discount is applied.

### Pricing and promotion logic is not only stored data <a href="#pricing-and-promotion-logic-is-not-only-stored-data" id="pricing-and-promotion-logic-is-not-only-stored-data"></a>

Pricing and promotion behavior usually combine visible records with hidden business rules.

A product price, sale price, coupon code, or discount label is only one part of the system. The commercial result can also depend on rule conditions, product eligibility, category assignment, customer segmentation, quantity thresholds, shipping behavior, tax calculation, date ranges, currency settings, and extension-driven logic.

#### A discount code is different from a discount rule <a href="#a-discount-code-is-different-from-a-discount-rule" id="a-discount-code-is-different-from-a-discount-rule"></a>

The code is what the customer enters or receives. The rule decides what happens after the code is applied.

A promotion rule may define:

* which products qualify
* which categories or collections qualify
* which customers or customer groups qualify
* whether sale items are excluded
* whether the discount has a minimum or maximum order value
* whether the rule has a usage limit
* whether the promotion can combine with other offers
* whether shipping is included or excluded
* whether the rule is active only during a specific period

If those conditions are represented differently in the Target Platform, the promotion can keep the same name while producing a different outcome.

**Why this matters in migration**

A migrated coupon should not be judged only by whether the code exists. It should be tested through the real cart scenarios that the promotion was designed to support.

### Pricing logic can live in different layers <a href="#pricing-logic-can-live-in-different-layers" id="pricing-logic-can-live-in-different-layers"></a>

Platforms can represent pricing and promotions at different levels of the store system.

Some rules apply to a product. Others apply to a variant, customer group, cart subtotal, shipping method, catalog rule, customer segment, payment condition, bundle, subscription, or external pricing source. A migration must account for where the logic lives, not just what the final price appears to be.

#### Common pricing and promotion layers <a href="#common-pricing-and-promotion-layers" id="common-pricing-and-promotion-layers"></a>

Pricing and promotion logic may appear in:

* base product prices
* variant-level prices
* sale prices
* customer-group pricing
* quantity or volume pricing
* catalog price rules
* cart price rules
* coupon codes
* free-shipping incentives
* bundle, subscription, or membership pricing
* app, plugin, module, or extension logic
* external ERP, POS, loyalty, or pricing systems

These layers can interact. For example, a product may have a sale price, belong to a promotional category, qualify for a customer-group discount, and appear in a cart that also uses a coupon or free-shipping threshold. The Target Platform may calculate those layers in a different order or allow fewer combinations.

**Why the calculation layer matters**

Two platforms can show the same headline offer but distribute the discount differently across line items, shipping, tax, and order totals. That difference can affect invoices, refunds, reports, margin analysis, and customer support.

### Common reasons promotions change after migration <a href="#common-reasons-promotions-change-after-migration" id="common-reasons-promotions-change-after-migration"></a>

Promotion behavior usually changes because the Target Platform uses a different rule engine, condition model, or calculation order.

The issue is rarely the coupon name alone. It is the relationship between the promotion and the structures it depends on.

#### Rule-engine differences <a href="#rule-engine-differences" id="rule-engine-differences"></a>

Some platforms support detailed rule builders natively. Others rely more on apps, plugins, modules, or custom logic. Even when both platforms support similar promotion types, they may not support the same conditions, exclusions, priorities, or combinations.

#### Eligibility differences <a href="#eligibility-differences" id="eligibility-differences"></a>

A promotion may depend on products, variants, categories, collections, customer groups, tags, segments, regions, shipping methods, or payment choices. If those structures change during migration, the promotion rule may no longer target the same group of records.

#### Stacking and combination differences <a href="#stacking-and-combination-differences" id="stacking-and-combination-differences"></a>

One platform may allow multiple discounts to be combined. Another may limit how product discounts, order discounts, shipping discounts, and coupon codes interact. A promotion can be technically present but commercially weaker or broader if the stacking rules change.

#### Tax, shipping, and rounding differences <a href="#tax-shipping-and-rounding-differences" id="tax-shipping-and-rounding-differences"></a>

Discount timing affects totals. A platform may apply discounts before tax, after tax, to line items, to the order subtotal, or only to certain charge types. Shipping discounts may also behave separately from product discounts. Small calculation differences can become important when they affect high-volume orders, refunds, customer expectations, or accounting reconciliation.

#### Extension-driven pricing behavior <a href="#extension-driven-pricing-behavior" id="extension-driven-pricing-behavior"></a>

Many stores use apps, plugins, modules, or custom code for advanced promotions. Examples include loyalty pricing, wholesale pricing, tiered pricing, subscription discounts, bundled offers, regional pricing, customer-specific pricing, or automatic merchandising tied to promotions.

When pricing depends on this kind of logic, the migration concern is not only whether the data can move. The concern is whether the Target Platform can reproduce the intended rule behavior or whether custom migration logic adjustment, replacement configuration, or post-migration setup is needed.

### Promotion records depend on surrounding store structures <a href="#promotion-records-depend-on-surrounding-store-structures" id="promotion-records-depend-on-surrounding-store-structures"></a>

Promotions rarely work in isolation.

A category discount depends on category structure. A product-specific offer depends on product and variant mapping. A customer-tier discount depends on customer classification. A free-shipping threshold depends on cart totals, shipping methods, and region rules. A bundle offer may depend on product relationships, inventory rules, and storefront presentation.

#### Structures that often affect promotion behavior <a href="#structures-that-often-affect-promotion-behavior" id="structures-that-often-affect-promotion-behavior"></a>

Promotion logic can depend on:

* Products and variants
* Categories, collections, or catalog groups
* Customer groups, tags, segments, or membership status
* Shipping methods and shipping zones
* Tax settings and tax-inclusive or tax-exclusive pricing
* Currencies and rounding rules
* Inventory availability
* Bundles, subscriptions, and recurring-purchase systems
* Apps, plugins, modules, extensions, or external systems

When one of those structures changes, the promotion may need review even if the coupon record itself appears intact.

**The safest review question**

Instead of asking whether a promotion migrated, ask whether the Target Platform can still produce the intended pricing outcome for the same real-world customer and cart scenarios.

### What to define before migration execution <a href="#what-to-define-before-migration-execution" id="what-to-define-before-migration-execution"></a>

Pricing and promotion planning should begin with the offers that matter most commercially.

Not every expired coupon or small seasonal offer deserves the same review depth. The strongest planning starts by identifying promotions that affect revenue, margin, retention, conversion, launch confidence, or customer trust.

#### Define commercial priority <a href="#define-commercial-priority" id="define-commercial-priority"></a>

Separate active and business-critical pricing behavior from outdated, experimental, or low-impact promotions.

Useful questions include:

* Which promotions drive meaningful revenue or conversion?
* Which offers must remain active near launch?
* Which discounts are tied to campaigns, customer contracts, subscriptions, or loyalty programs?
* Which promotions affect margin, reporting, or support expectations?
* Which old coupons can be retired instead of migrated?

#### Define rule behavior <a href="#define-rule-behavior" id="define-rule-behavior"></a>

For each important promotion, document what the rule is supposed to do.

The definition should include:

* eligible products, variants, categories, or collections
* excluded products, categories, or sale items
* customer groups, tags, segments, or email restrictions
* minimum or maximum cart thresholds
* usage limits and date ranges
* shipping or payment conditions
* whether the promotion can combine with other discounts
* expected line-level and order-level totals

#### Define acceptable differences <a href="#define-acceptable-differences" id="define-acceptable-differences"></a>

Some promotions can be simplified without damaging the business. Others must behave very closely to the original rule.

Before migration execution, decide which differences are acceptable. A renamed campaign label may be harmless. A changed eligibility condition, tax-sensitive total, or stacking rule may not be.

### How Add-ons and Custom Service may relate to promotion logic <a href="#how-add-ons-and-custom-service-may-relate-to-promotion-logic" id="how-add-ons-and-custom-service-may-relate-to-promotion-logic"></a>

Pricing and promotion work should not be flattened into one generic customization bucket.

If the requirement is mainly about mapping supported values into the Target Platform’s available structures, **Advanced Data Mapping** may be relevant. If selected values need adjustment during migration, **Advanced Data Configure** may be relevant. If only selected records or promotion-related data should be included, the **Data Filter Add-on** may be relevant when its available settings and supported behavior fit the requirement.

However, pricing and promotion behavior often moves beyond Standard Add-on capability when the expected outcome depends on bespoke rule transformation, extension-driven pricing, loyalty logic, customer-tier pricing, custom discount behavior, or Target Platform limitations.

#### When Custom Service is the safer boundary <a href="#when-custom-service-is-the-safer-boundary" id="when-custom-service-is-the-safer-boundary"></a>

Custom Service should be considered when promotion continuity requires:

* custom migration logic adjustment
* Tailored Add-ons or Custom Add-ons
* transformation of unsupported discount structures
* Custom Platform handling
* third-party app, plugin, module, or extension data
* outside-system identifiers
* customer-tier or loyalty pricing logic
* bundle, subscription, or regional pricing behavior
* validation of bespoke commercial rules beyond standard service capability

Custom Service does not automatically mean Next-Cart performs the full migration. The final plan should clarify whether the need is customization only, migration management, or both.

### What to validate first <a href="#what-to-validate-first" id="what-to-validate-first"></a>

Pricing and promotion validation should use realistic carts, not only admin-record checks.

The most useful validation sample includes the offers that matter most to revenue, margin, customer trust, and launch timing. It should test how the Target Platform applies the rule, not only whether the promotion appears in a list.

#### High-priority validation scenarios <a href="#high-priority-validation-scenarios" id="high-priority-validation-scenarios"></a>

Review scenarios such as:

* product-specific discounts
* category or collection-based discounts
* sale-item exclusions
* customer-group, tag, segment, or email-based discounts
* minimum-spend and maximum-spend thresholds
* usage limits and date ranges
* stacked discounts or non-combinable discounts
* free-shipping and shipping-threshold offers
* tax-sensitive cart totals
* multi-currency or regional pricing cases
* bundle, subscription, or loyalty pricing behavior

#### What reviewers should check <a href="#what-reviewers-should-check" id="what-reviewers-should-check"></a>

For each important promotion, confirm:

* whether the right products qualify
* whether excluded products remain excluded
* whether the right customers qualify
* whether threshold behavior is accurate
* whether discount stacking behaves as expected
* whether shipping incentives apply under the correct conditions
* whether line-level and order-level totals make sense
* whether reporting and support teams can interpret the result

A Demo Migration can help expose pricing and promotion behavior early, especially when the sample includes representative products, customers, carts, and promotion scenarios. It should be treated as early evidence, not final approval.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Pricing and promotion migration is not only about preserving coupon codes or sale-price records. It is about preserving commercial behavior: who receives the discount, what qualifies, when the rule applies, how it combines with other offers, and how the final cart total is calculated.

The safest approach is to identify the promotions that matter most, document the rule behavior behind each one, test realistic carts early, and clarify whether the Target Platform can represent the same outcome through standard service capability, supported Add-ons, or Custom Service handling.

Before launch, review the offers that have the greatest impact on revenue, margin, customer trust, and support expectations. If an important promotion depends on custom pricing logic, extension behavior, or rule conditions the Target Platform cannot represent cleanly, use Live Chat to clarify whether Custom Service planning is needed before broader execution.

### FAQs <a href="#faqs" id="faqs"></a>

**Why can a coupon code migrate but still behave differently?**

Because the coupon code is only the trigger. The rule behind it controls eligibility, exclusions, thresholds, usage limits, stacking behavior, shipping treatment, tax interaction, and calculation order.

**Should every old promotion be migrated?**

Not always. Expired, low-impact, outdated, or campaign-specific promotions may be better retired. Active promotions, loyalty offers, customer-specific discounts, and revenue-driving campaigns deserve closer review.

**What is the best way to validate pricing and promotion behavior?**

Use realistic cart scenarios. Test important products, categories, customer groups, stacked discounts, shipping incentives, tax-sensitive totals, and extension-driven pricing logic instead of only checking whether the promotion record exists.

**When does promotion logic require Custom Service?**

Custom Service is needed when the expected outcome depends on customization, modification, custom migration logic adjustment, Custom Platform handling, extension-driven pricing, loyalty rules, customer-tier pricing, unsupported discount structures, or bespoke transformation beyond standard service capability.
