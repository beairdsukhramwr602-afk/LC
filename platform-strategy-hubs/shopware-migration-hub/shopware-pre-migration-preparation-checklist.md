# Shopware Pre-Migration Preparation Checklist

A Shopware migration is easier to judge when the business has already defined how the future storefront should behave. Preparation should not only confirm that products, customers, orders, and content are available. It should clarify how Shopware should represent sales channels, product visibility, rule-driven behavior, variants, properties, categories, SEO routes, media, and extension-shaped meaning after migration.

Shopware can support a more deliberate and context-aware storefront than many simpler Target Platforms, but that strength depends on clear decisions before execution. If the business enters migration with vague channel logic, unclear product visibility rules, poorly defined pricing behavior, or undocumented extension dependencies, the migrated result may contain records without supporting the way the storefront actually needs to sell.

This checklist is meant to prepare the business for a safer Shopware migration review. It is not a setup guide. It helps teams define what must be clarified before they judge Demo Migration results, select the right service approach, or approve a full migration plan.

### What This Preparation Checklist Is For <a href="#what-this-preparation-checklist-is-for" id="what-this-preparation-checklist-is-for"></a>

A strong Shopware preparation checklist should help the business answer practical questions before migration begins:

* Which sales channels matter, and what should each one do?
* Which products should be visible, searchable, purchasable, or restricted in each channel?
* Which pricing, promotion, shipping, payment, or customer-facing outcomes depend on rule-driven behavior?
* Which product properties, variants, categories, and media assets shape the buying experience?
* Which URLs, category entry points, and page routes need focused continuity planning?
* Which extensions, themes, custom fields, or integrations still carry business meaning?
* Which sample records should be tested before the migration is treated as safe?

The goal is not to document everything equally. The goal is to identify the structures most likely to affect commercial meaning, customer experience, and launch confidence.

### 1. Define the Sales Channels That Matter <a href="#id-1-define-the-sales-channels-that-matter" id="id-1-define-the-sales-channels-that-matter"></a>

Shopware preparation should begin with sales-channel structure because sales channels shape storefront context.

Before migration, clarify:

* which sales channels should exist in the Target Platform
* what each sales channel is meant to represent
* which products, categories, currencies, languages, or customer contexts belong in each channel
* whether source-store differences should remain separate or be consolidated
* which channel-specific behaviors are commercially necessary

A sales channel should not be created only because legacy structure exists. It should represent a real storefront, market, language, customer context, or selling model that the business intends to manage after launch.

### 2. Clarify Product Visibility by Sales Channel <a href="#id-2-clarify-product-visibility-by-sales-channel" id="id-2-clarify-product-visibility-by-sales-channel"></a>

In Shopware, product presence and product visibility are not the same thing. A migrated product may exist in the catalog, but that does not automatically prove it is visible in the correct storefront context.

Before migration, clarify:

* which products should appear in which sales channels
* which products should be searchable, listed, directly accessible, or restricted
* which product families require different visibility rules by market or storefront
* which products must remain hidden until reviewed
* which source-store visibility workarounds should be simplified in Shopware

This is especially important for stores with multiple storefronts, market-specific catalogs, B2B/B2C separation, seasonal catalogs, or products that should exist operationally without being broadly visible.

### 3. Identify Rule-Driven Behavior Before It Becomes a Validation Surprise <a href="#id-3-identify-rule-driven-behavior-before-it-becomes-a-validation-surprise" id="id-3-identify-rule-driven-behavior-before-it-becomes-a-validation-surprise"></a>

Shopware’s Rule Builder can shape important storefront behavior. Preparation should identify which business outcomes depend on conditions, not only which records need to move.

Before migration, clarify:

* which pricing or promotional outcomes depend on customer, cart, product, channel, or delivery context
* which payment or shipping options should appear only under certain conditions
* which customer groups or selling contexts require different behavior
* which legacy rules are still commercially meaningful
* which inherited workarounds can become cleaner Shopware rules

If rule-dependent behavior matters, it should be described as an expected outcome before migration. Otherwise, the Demo Migration may look technically complete while still failing important buying scenarios.

### 4. Prepare Product Properties, Variants, and Product Families <a href="#id-4-prepare-product-properties-variants-and-product-families" id="id-4-prepare-product-properties-variants-and-product-families"></a>

Shopware product structure should be prepared around how customers compare, select, and buy products.

Before migration, clarify:

* which product families depend on variants
* which product properties are used for filtering, comparison, search, or merchandising
* which source attributes should become Shopware properties
* which attributes are only internal notes and should not shape storefront discovery
* which high-value products require manual review after migration
* whether variant naming, pricing, media, and visibility need special attention

This preparation helps prevent the common mistake of treating product data as flat records. For Shopware, product meaning often depends on the relationship between products, variants, properties, visibility, pricing, and sales-channel context.

### 5. Review Pricing, Advanced Prices, and Commercial Conditions <a href="#id-5-review-pricing-advanced-prices-and-commercial-conditions" id="id-5-review-pricing-advanced-prices-and-commercial-conditions"></a>

Pricing preparation should go beyond base price transfer. Shopware can support pricing that depends on context, rules, quantities, currencies, or customer conditions, so the business should decide which pricing logic still matters.

Before migration, clarify:

* which prices are simple base prices
* which prices depend on customer group, quantity, currency, market, or sales channel
* which promotional or discount patterns need rule-aware review
* which advanced prices should be tested in Demo Migration
* which old pricing workarounds can be simplified instead of copied

Pricing should be reviewed as a commercial outcome, not only as a numeric field. If a price changes correctly only under certain conditions, that condition belongs in the preparation notes.

### 6. Clarify Category Structure and Storefront Entry Points <a href="#id-6-clarify-category-structure-and-storefront-entry-points" id="id-6-clarify-category-structure-and-storefront-entry-points"></a>

Categories in Shopware can shape navigation, browsing, product discovery, landing paths, and sales-channel context. Preparation should separate useful storefront structure from inherited clutter.

Before migration, clarify:

* which categories are essential navigation entry points
* which category structures should be preserved, simplified, merged, or retired
* which categories matter differently by sales channel
* which product-category assignments drive revenue or discovery
* which category pages carry SEO or campaign value

The goal is to avoid moving category structure blindly. The migrated result should support how customers will browse the Shopware storefront after launch.

### 7. Prioritize SEO Routes, Canonical Behavior, and High-Value URLs <a href="#id-7-prioritize-seo-routes-canonical-behavior-and-high-value-urls" id="id-7-prioritize-seo-routes-canonical-behavior-and-high-value-urls"></a>

Shopware preparation should include URL and route planning before SEO continuity becomes a launch issue.

Before migration, clarify:

* which product, category, CMS, or landing page URLs carry traffic or business value
* which routes should be preserved closely where possible
* which legacy URLs can safely redirect to new destinations
* which sales-channel contexts may affect route or canonical behavior
* which pages should be included in the Demo Migration review sample

Do not treat all URLs equally. Focus first on high-value product pages, category entry points, landing pages, branded pages, and pages customers or search engines already rely on.

### 8. Prepare Media, Layout, and Content Expectations <a href="#id-8-prepare-media-layout-and-content-expectations" id="id-8-prepare-media-layout-and-content-expectations"></a>

Shopware product and storefront experience can depend heavily on media quality, layout choices, product presentation, and supporting content. Migration preparation should define what matters most before visual review begins.

Before migration, clarify:

* which product images and galleries are commercially important
* which product descriptions, specifications, and media assets need manual review
* whether media roles or ordering affect buying confidence
* which CMS or landing content should remain active
* which layout-dependent content may need rebuilding rather than direct preservation

This prevents validation from focusing only on whether content exists. The better question is whether the content still supports the customer’s decision in the Shopware storefront.

### 9. Classify Extensions, Themes, Custom Fields, and Integration-Owned Meaning <a href="#id-9-classify-extensions-themes-custom-fields-and-integration-owned-meaning" id="id-9-classify-extensions-themes-custom-fields-and-integration-owned-meaning"></a>

Many Shopware migrations involve meaning that is not fully contained in native catalog, customer, or order records. Extensions, themes, custom fields, and integrations may shape storefront behavior, internal review, external system matching, or operational workflows.

Before migration, clarify:

* which extensions support commercially important behavior
* which theme behavior affects navigation, trust, presentation, or conversion
* which custom fields are still needed after migration
* which outside-system identifiers must remain usable
* which integrations depend on migrated values or record relationships
* which behaviors require Custom Service because they depend on bespoke transformation or custom migration logic adjustment

The business does not need to preserve every historical technical detail. It needs to identify which custom or extension-shaped meanings still affect the future Shopware operation.

### 10. Define Customer and Order Review Expectations <a href="#id-10-define-customer-and-order-review-expectations" id="id-10-define-customer-and-order-review-expectations"></a>

Customer and order data should be prepared around how the business will use it after migration.

Before migration, clarify:

* which customer records are active, valuable, or required for account continuity
* which customer groups or tags still affect pricing, access, marketing, or review
* which order history should remain visible and understandable
* which order statuses, totals, addresses, products, and customer relationships need representative checks
* which historical data is useful for reference but should not be treated as live operational behavior

This helps the business avoid validating customer and order data only by count. A useful Shopware result should support account review, customer service, and business interpretation after launch.

### 11. Prepare a Representative Demo Migration Sample <a href="#id-11-prepare-a-representative-demo-migration-sample" id="id-11-prepare-a-representative-demo-migration-sample"></a>

A Demo Migration is most useful when the sample is selected around risk, not convenience.

For Shopware, the sample should include:

* products assigned to different sales channels
* products with important visibility differences
* products with variants and meaningful properties
* products affected by advanced prices or rule-driven behavior
* categories that matter to browsing and SEO
* customer records tied to meaningful groups or account expectations
* orders that show realistic status, totals, customer, product, and address relationships
* URLs and content pages that need continuity review
* extension-shaped or custom-field cases that could affect scope

A small sample can reveal a lot when it contains the right cases. A convenient sample with only simple records can hide the very issues that make Shopware migration complex.

### 12. Clarify Custom Platform Source Requirements Early <a href="#id-12-clarify-custom-platform-source-requirements-early" id="id-12-clarify-custom-platform-source-requirements-early"></a>

When the Source Platform is a Custom Platform, Shopware preparation needs a more explicit translation layer.

Before migration, clarify:

* how the source represents products, variants, properties, categories, customers, and orders
* which source-side fields have no direct Shopware equivalent
* which custom identifiers must remain usable
* which storefront behaviors were created through custom logic
* which records depend on external systems
* which outcomes require custom migration logic adjustment

Custom Platform handling requires Custom Service because the source structure must be interpreted before it can be translated safely into Shopware. This does not automatically mean Next-Cart performs migration management; migration management is included only when it is part of the final plan.

### Practical Shopware Preparation Sequence <a href="#practical-shopware-preparation-sequence" id="practical-shopware-preparation-sequence"></a>

A useful Shopware preparation sequence usually moves from storefront context to technical proof:

#### 1. Define the future sales-channel model <a href="#id-1-define-the-future-sales-channel-model" id="id-1-define-the-future-sales-channel-model"></a>

Start with the storefront contexts that the business actually intends to operate after launch.

#### 2. Clarify rule-dependent behavior <a href="#id-2-clarify-rule-dependent-behavior" id="id-2-clarify-rule-dependent-behavior"></a>

Identify pricing, promotion, shipping, payment, visibility, and customer-facing outcomes that depend on conditions.

#### 3. Prepare high-value product structures <a href="#id-3-prepare-high-value-product-structures" id="id-3-prepare-high-value-product-structures"></a>

Focus on product families where variants, properties, pricing, visibility, or media affect buying decisions.

#### 4. Review categories and route continuity <a href="#id-4-review-categories-and-route-continuity" id="id-4-review-categories-and-route-continuity"></a>

Decide which entry points, URLs, and canonical expectations matter most before migration results are reviewed.

#### 5. Classify extensions and custom fields <a href="#id-5-classify-extensions-and-custom-fields" id="id-5-classify-extensions-and-custom-fields"></a>

Identify which non-native meanings still affect commercial or operational outcomes.

#### 6. Build a risk-based Demo Migration sample <a href="#id-6-build-a-risk-based-demo-migration-sample" id="id-6-build-a-risk-based-demo-migration-sample"></a>

Choose sample data that can prove whether the migration approach is strong enough for the real Shopware context.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for a Shopware migration means deciding what the future storefront model should prove. Sales channels, rules, visibility, product structure, categories, routes, media, extensions, and customer context should be clarified before migration results are judged. When those decisions are clear, Demo Migration review becomes more useful because the business can evaluate whether the migrated result supports the intended Shopware operation instead of only checking whether records appear.

Before starting full migration, prepare a small set of high-value examples that represent the real Shopware target model: products with variants and properties, rule-dependent commercial behavior, sales-channel differences, priority routes, customer-account cases, and any extension-shaped data that still matters. If those examples require custom handling or source interpretation, discuss them through Live Chat before treating the migration plan as routine.

### FAQs <a href="#faqs" id="faqs"></a>

**Should every product be prepared in detail before migrating to Shopware?**

No. The first priority is to prepare the products that expose the most risk: high-revenue products, products with variants, products with important properties, products with channel-specific visibility, products with advanced pricing, and products tied to important routes or media. Simple products still matter, but they usually do not reveal the strongest Shopware migration risks.

**Why should sales channels be prepared before migration?**

Sales channels shape storefront context in Shopware. If the business has not decided which channels should exist and what each one should represent, product visibility, routing, pricing, customer experience, and validation can become unclear later.

**Should rule-driven behavior be included in the preparation checklist?**

Yes. If pricing, promotions, shipping, payment, discounts, product visibility, or customer-facing behavior depends on conditions, the expected outcome should be documented before migration review. Otherwise, the migrated result may look complete while still failing important selling scenarios.

**What should be included in a Shopware Demo Migration sample?**

A useful sample should include products with variants and properties, sales-channel visibility cases, rule-dependent pricing or promotions, important categories, priority URLs, customer-account examples, realistic order history, and any extension-shaped or custom-field data that may affect scope.

**Does a Custom Platform source always require Custom Service for a Shopware migration?**

Yes. When the Source Platform is a Custom Platform, the source structure must be interpreted before it can be translated safely into Shopware. That handling belongs under Custom Service. Migration management is included only when it is part of the final plan.
