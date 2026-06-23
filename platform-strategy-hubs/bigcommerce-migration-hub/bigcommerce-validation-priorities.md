# BigCommerce Validation Priorities

BigCommerce validation should prove that the migrated store works as a complete commercial system. Product records, customer records, orders, categories, redirects, CMS Pages, Blog Posts, and storefront assignments can all appear present while the practical buying experience, pricing behavior, discovery path, or operational workflow still changes in ways that matter.

The strongest validation work focuses on the parts of BigCommerce where structure carries business meaning: products with variants or modifiers, customer groups and price lists, channel and storefront assignments, category trees, URL redirects, custom fields, metafields, app-shaped behavior, and external-system identifiers. A complete-looking BigCommerce store should not be treated as launch-ready until those behaviors are tested with representative examples.

### What BigCommerce Validation Should Prove <a href="#what-bigcommerce-validation-should-prove" id="what-bigcommerce-validation-should-prove"></a>

BigCommerce validation should confirm more than migrated record presence. It should prove that the Target Platform supports the same buying decisions, pricing expectations, customer experience, search or navigation purpose, and operational outcomes the business needs after migration.

A useful validation review should answer practical questions:

| Validation question                                                    | Why it matters in BigCommerce                                                                                                |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Can customers still choose the right product configuration?            | Variants, variant options, modifiers, custom fields, and app-supported options can carry different meaning.                  |
| Do the right customers see the right prices?                           | Customer groups, price lists, and bulk pricing can change commercial results if they are incomplete or misapplied.           |
| Are products and categories available in the right storefront context? | Channel and storefront assignments can affect visibility, discovery, and customer expectations.                              |
| Do important URLs still lead to useful destinations?                   | Redirects can resolve technically while still weakening SEO, campaign, or support intent.                                    |
| Do apps and custom data still support operations?                      | Custom fields, metafields, app data, and external identifiers often connect BigCommerce to workflows outside the storefront. |

Validation should produce clear evidence, not broad approval comments. A result should be marked as acceptable only when the sample proves that the BigCommerce outcome is usable for the intended business purpose.

### Validate Product Choices, Variants, and Modifiers <a href="#validate-product-choices-variants-and-modifiers" id="validate-product-choices-variants-and-modifiers"></a>

Product validation is usually the first BigCommerce priority because product-choice structure can change how customers buy. A product may exist in the Target Platform, but that does not prove that variant behavior, modifier choices, pricing changes, images, inventory, or custom options still work as expected.

A strong product validation sample should include:

* best-selling products with variants, variant options, or modifier-driven choices;
* products where options change price, SKU, image, inventory, fulfillment, or personalization;
* products that previously used custom product fields or app-supported configuration;
* products assigned to several categories or storefront contexts;
* products whose buying path may be simplified, formalized, or restructured in BigCommerce.

The pass condition is not simply that the product appears. The pass condition is that a customer can select the intended configuration, understand the available choices, see the right price or option result, and reach the correct sellable outcome.

### Validate Categories, Channels, and Storefront Discovery <a href="#validate-categories-channels-and-storefront-discovery" id="validate-categories-channels-and-storefront-discovery"></a>

BigCommerce discovery validation should confirm whether categories, category trees, storefront assignments, and product visibility still support the intended shopping journey. A category may be present while navigation, filtering, merchandising, or storefront-specific visibility becomes weaker.

Validation should include the category and storefront paths that influence revenue, SEO, campaign traffic, or customer support. For stores using multiple storefronts or channel-specific assignments, the review should prove that products, categories, and content appear in the intended storefront context and do not appear where they should not.

Useful samples include:

* top navigation categories and high-revenue category groups;
* categories that carry organic search or campaign value;
* products assigned to multiple categories or storefronts;
* category paths with merchandising, sorting, or filtering expectations;
* storefront-specific content or product visibility cases.

The goal is to prove customer discovery. If customers can no longer find products through the intended path, the migrated category structure needs more review even when the underlying records look complete.

### Validate Customer Groups, Price Lists, and Pricing Behavior <a href="#validate-customer-groups-price-lists-and-pricing-behavior" id="validate-customer-groups-price-lists-and-pricing-behavior"></a>

Customer and pricing validation should prove that BigCommerce applies the intended commercial context. Price lists, customer groups, bulk pricing, storefront scope, discounts, and customer-specific visibility can all affect what a buyer sees and pays.

A strong validation sample should include:

* customer groups with special pricing or access expectations;
* price lists that affect high-value products;
* wholesale, reseller, B2B, loyalty, or account-based pricing scenarios;
* products with bulk pricing or tiered commercial behavior;
* test customers and orders that prove pricing is applied, not only stored.

Visible pricing is not enough. BigCommerce validation should confirm that the right customer sees the right product, the right price, and the right buying condition in the intended storefront context. If the store sells to both retail and segmented customer groups, validation should test both sides instead of assuming one pricing view proves the other.

### Validate Customer, Account, and Order Context <a href="#validate-customer-account-and-order-context" id="validate-customer-account-and-order-context"></a>

Customer and order validation should confirm that migrated records still support account continuity, customer-service workflows, and commercial history. A customer can exist in BigCommerce while account expectations, address behavior, pricing group assignment, or order-history usability still creates friction.

Validation should review:

* returning customers with order history;
* customers with multiple addresses or important account attributes;
* customers tied to pricing, loyalty, reseller, or B2B logic;
* order records with tax, shipping, discount, payment, fulfillment, or support meaning;
* customer-service scenarios that depend on migrated history.

The practical test is whether the customer team can support post-launch questions confidently. If order history exists but key context is unclear, the migration may still require explanation, additional mapping, or acceptance criteria before launch.

### Validate Content, URL, Redirect, and SEO Continuity <a href="#validate-content-url-redirect-and-seo-continuity" id="validate-content-url-redirect-and-seo-continuity"></a>

BigCommerce URL and content validation should focus on customer intent and route value, not only redirect status. A redirect can return a successful response while still sending customers to a weak destination, a mismatched product, a generic category, or the wrong storefront context.

Validation should include:

* best-selling product URLs;
* high-traffic category URLs;
* CMS Pages, Blog Posts, policy pages, support pages, and trust-building content;
* routes with backlinks, search value, paid campaigns, or email campaign history;
* pages affected by product consolidation, category restructuring, or storefront changes.

A valid route should preserve the purpose of the old path. For SEO-sensitive or customer-support pages, the destination should still answer the same intent. If the original page cannot be replicated directly, the alternative should be deliberately accepted rather than treated as a technical redirect success.

### Validate Apps, Custom Fields, Metafields, and Integrations <a href="#validate-apps-custom-fields-metafields-and-integrations" id="validate-apps-custom-fields-metafields-and-integrations"></a>

Many BigCommerce migrations depend on data that supports apps, themes, external systems, or operational workflows. Custom fields, metafields, app-owned records, ERP or CRM identifiers, fulfillment references, loyalty data, review data, subscriptions, analytics tags, and marketplace IDs can carry meaning that is not visible in a basic product or order check.

Validation should include records that depend on:

* custom fields or metafields used for storefront display, filtering, reporting, or integration;
* app-supported product, pricing, shipping, tax, subscription, review, loyalty, or fulfillment behavior;
* external IDs that connect BigCommerce with ERP, CRM, marketplace, warehouse, accounting, analytics, or customer-support systems;
* theme logic that affects navigation, comparison, trust messaging, or product presentation;
* Custom Platform records that required interpretation before migration.

If a record looks correct in BigCommerce but no longer connects to the surrounding workflow, the validation result should not pass. That scenario usually needs Custom Service review, integration review, or a documented acceptance decision.

### Validate Demo Migration and Full Migration Evidence <a href="#validate-demo-migration-and-full-migration-evidence" id="validate-demo-migration-and-full-migration-evidence"></a>

Demo Migration and Full Migration validation should use samples that reveal BigCommerce-specific ambiguity. Low-risk samples can make the result look cleaner than it really is. The best samples include records that exercise the platform structures most likely to change meaning.

A Demo Migration validation set should include:

* products with variants, variant options, modifiers, custom fields, and metafields;
* products tied to customer groups, price lists, or bulk-pricing rules;
* categories and category trees that shape discovery;
* channel or storefront-specific product and content assignments;
* CMS Pages, Blog Posts, and high-value redirects;
* customer and order records with pricing, tax, shipping, discount, payment, fulfillment, or support implications;
* app-dependent data and external-system identifiers.

Full Migration validation should then confirm that the same logic holds across the complete scope. A Demo Migration can prove the approach is viable, but it does not replace final acceptance after the complete data set is migrated.

### How Additional Migration Options Affect Validation Scope <a href="#how-additional-migration-options-affect-validation-scope" id="how-additional-migration-options-affect-validation-scope"></a>

Additional Migration Options may become relevant when the customer continues migration activity after an earlier migration step, changes configuration, or performs a new migration for the same migration path. In BigCommerce, that means validation should focus on records or structures affected by the later activity.

If additional migration activity introduces new or changed products, customers, orders, Blog Posts, categories, price lists, redirects, channel assignments, custom fields, metafields, or app-dependent data, those areas should be reviewed again. Follow-up migration activity can reduce data freshness gaps, but it does not prove that the affected BigCommerce structures are launch-ready.

Entity Points should also be interpreted correctly during later migration activity. Records already counted through the same service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when they are migrated for the first time.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce validation should prove that the migrated store works as a BigCommerce business system, not only that records arrived. The most important evidence usually comes from products with options, variants, modifiers, custom fields, or metafields; customer groups and price lists; category and storefront discovery; high-value URLs and redirects; customer account history; and app or integration behavior.

A BigCommerce migration is ready for launch only when representative samples prove that customers can find products, choose the right configuration, see the right price, reach useful content, and rely on the operational workflows connected to migrated records. If a result is technically present but commercially unclear, treat it as a review item rather than a pass.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first in a BigCommerce migration?**

Start with products that expose variants, variant options, modifiers, custom fields, or app-supported configuration. These cases usually reveal whether the migrated BigCommerce structure preserves the buying experience, not only product presence.

**Why are customer groups and price lists important in BigCommerce validation?**

They can affect which customers see specific prices, products, or buying conditions. Validation should prove that the right customer receives the intended price and visibility in the intended storefront context.

**Are working redirects enough to validate BigCommerce URL continuity?**

No. A redirect can work technically while still sending customers to a weak or mismatched destination. Validation should confirm that important routes still support the same search, shopping, trust, support, or campaign purpose.

**How should custom fields and metafields be validated?**

Review whether they still support the intended display, filtering, reporting, integration, or operational workflow. They should not be accepted only because values appear in BigCommerce.

**Do Additional Migration Options remove the need for final validation?**

No. Additional Migration Options can support follow-up migration activity, but changed or newly migrated records still need review before the BigCommerce store is treated as launch-ready.
