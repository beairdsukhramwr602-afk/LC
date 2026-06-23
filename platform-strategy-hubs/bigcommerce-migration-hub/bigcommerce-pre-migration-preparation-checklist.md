# BigCommerce Pre-Migration Preparation Checklist

BigCommerce migration preparation should define how the future Target Store will work before records are moved. A store can have accurate product, customer, order, category, and content counts while still creating avoidable launch risk if product choices, customer pricing, storefront scope, redirects, apps, or custom fields are not understood before migration begins.

The preparation goal is not to make every detail perfect before Demo Migration. It is to identify the decisions that affect BigCommerce behavior, choose the samples that expose risk, and separate ordinary migration scope from Add-ons or Custom Service needs early enough to plan the right Migration Service path.

### What BigCommerce Preparation Should Clarify <a href="#what-bigcommerce-preparation-should-clarify" id="what-bigcommerce-preparation-should-clarify"></a>

BigCommerce is strongest when the merchant has already defined the commercial meaning behind catalog, pricing, storefront, and content structures. Preparation should therefore answer practical questions before migration execution begins.

| Preparation area             | What to clarify                                                                                    | Why it matters in BigCommerce                                                                         |
| ---------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Product choices              | Which choices are variants, modifiers, customizations, or app-owned behaviors.                     | Incorrect classification can affect SKU, inventory, price, order detail, and buyer selection.         |
| Categories and discovery     | Which categories support navigation, merchandising, SEO, or campaign paths.                        | A copied category tree can still weaken browsing if discovery meaning is not preserved.               |
| Customer and pricing context | Which customer groups, price lists, discounts, and bulk rules matter.                              | Commercial accuracy depends on more than base product prices.                                         |
| Storefront and channel scope | Which products, categories, pages, redirects, and pricing rules apply to which storefront context. | Multi-Storefront or channel-aware plans can hide assignment issues if only one storefront is checked. |
| Content and URLs             | Which CMS Pages, Blog Posts, landing paths, and redirects carry traffic or trust.                  | Route continuity should preserve destination intent, not only redirect existence.                     |
| Custom data and integrations | Which custom fields, metafields, apps, external IDs, or outside systems affect operations.         | Some data belongs in standard fields, while other behavior may require Add-ons or Custom Service.     |

This preparation layer should stay business-led. Technical access and export readiness matter, but they should support clear target-state decisions rather than replace them.

### Prepare Product Options, Variants, and Modifiers <a href="#prepare-product-options-variants-and-modifiers" id="prepare-product-options-variants-and-modifiers"></a>

Product preparation should begin with the products most likely to expose choice-structure ambiguity. BigCommerce can represent structured product data, but the business still needs to decide whether a choice is a sellable variant, a modifier, a customization input, a display attribute, an app-controlled behavior, or custom logic that requires additional handling.

Prepare a product-choice inventory that includes:

* high-revenue products with many options, sizes, colors, materials, bundles, personalization choices, or configuration steps;
* products where each choice affects SKU, inventory, image, weight, price, fulfillment, or order detail;
* products where some choices are true variants and others are modifier-style selections;
* products that rely on apps, custom storefront logic, scripts, external systems, or manual review;
* products where inaccurate option handling would change what customers can buy.

A good preparation file should not simply list product names. It should explain what the choice means commercially. A color-size combination with its own inventory should be treated differently from an engraving message, gift-wrap choice, warranty selection, or upload field. When these meanings are mixed together in the Source Platform, BigCommerce preparation should classify them before migration scope is finalized.

#### Product preparation pass condition <a href="#product-preparation-pass-condition" id="product-preparation-pass-condition"></a>

The product preparation layer is ready when the team can identify representative products for simple variants, complex variants, modifiers, custom fields, app-shaped behavior, and high-value product pages. These examples should be included in Demo Migration review so the business can judge whether BigCommerce preserves the intended buying experience.

### Prepare Categories, Channels, and Storefront Scope <a href="#prepare-categories-channels-and-storefront-scope" id="prepare-categories-channels-and-storefront-scope"></a>

Category preparation should focus on discovery value rather than administrative hierarchy alone. Some categories support main navigation, organic traffic, campaign landing pages, merchandising logic, and buyer comparison. Others may be outdated, duplicated, or inherited from past catalog structures that no longer deserve the same priority.

Prepare a category and storefront scope review that identifies:

* categories that appear in primary navigation or high-traffic browsing paths;
* categories that carry SEO value, campaign value, or merchandising responsibility;
* category paths that should be simplified instead of copied exactly;
* products that need storefront-specific or channel-specific visibility;
* category, product, or content differences across multiple storefront contexts;
* categories that should not be treated as important simply because they exist in the old store.

For merchants using or planning Multi-Storefront, preparation should decide what stays shared and what becomes storefront-specific. A product can be correct globally but wrong for a storefront if its category assignment, channel assignment, visibility, page path, or price context is not prepared deliberately.

#### Storefront-scope pass condition <a href="#storefront-scope-pass-condition" id="storefront-scope-pass-condition"></a>

The storefront preparation layer is ready when each important storefront or channel context has representative products, categories, content pages, redirects, and pricing examples selected for Demo Migration review. A single default-storefront sample is not enough when storefront scope is part of the target plan.

### Prepare Customer Groups, Price Lists, and Pricing Evidence <a href="#prepare-customer-groups-price-lists-and-pricing-evidence" id="prepare-customer-groups-price-lists-and-pricing-evidence"></a>

BigCommerce preparation should treat pricing as commercial context, not only numeric product values. Customer groups, price lists, bulk pricing, discounts, account-based pricing, and app- or system-driven rules can affect what different customers see and pay.

Prepare a pricing evidence file that includes:

* active customer groups and the business reason each one exists;
* price lists or segmented pricing examples that still matter;
* wholesale, B2B-like, loyalty, VIP, regional, retail, or negotiated pricing cases;
* bulk pricing rules, product-specific price exceptions, and customer-specific expectations;
* pricing behavior controlled outside the core store, such as apps, ERP, CRM, or sales systems;
* pricing rules that should be simplified, retired, or redesigned instead of migrated as-is.

The goal is to prevent an apparently complete product migration from failing commercial expectations. A product can have the right base price while still showing the wrong value to a specific customer group, storefront, quantity tier, or account context.

#### Pricing preparation pass condition <a href="#pricing-preparation-pass-condition" id="pricing-preparation-pass-condition"></a>

Pricing preparation is ready when the team can provide exact examples of sensitive customer groups, price-list cases, bulk-pricing cases, and exception rules. These examples should include expected buyer experience, not only expected values in an export file.

### Prepare Content, URLs, and SEO-Sensitive Routes <a href="#prepare-content-urls-and-seo-sensitive-routes" id="prepare-content-urls-and-seo-sensitive-routes"></a>

BigCommerce preparation should protect the URLs and content paths that customers, search engines, campaigns, and partners still use. Redirect preparation should therefore follow page intent, not only technical mapping.

Prepare a URL and content inventory that includes:

* high-value product URLs;
* category and brand paths with organic traffic or conversion value;
* CMS Pages that support trust, policies, buying decisions, or customer service;
* Blog Posts that still attract search traffic or educate customers;
* campaign, affiliate, partner, or email landing paths;
* outdated paths that should be redirected intentionally rather than preserved as primary destinations.

Each important route should have a destination that satisfies the old page intent. A broad redirect to the homepage or a generic category may technically resolve but still weaken customer experience, conversion, and search continuity.

#### URL preparation pass condition <a href="#url-preparation-pass-condition" id="url-preparation-pass-condition"></a>

URL preparation is ready when high-value routes have destination decisions, priority levels, and review owners. The migration sample should include route examples that prove product, category, CMS Page, Blog Post, and campaign destination behavior, not only record transfer.

### Prepare Custom Fields, Metafields, Apps, and External Identifiers <a href="#prepare-custom-fields-metafields-apps-and-external-identifiers" id="prepare-custom-fields-metafields-apps-and-external-identifiers"></a>

BigCommerce migrations often depend on information that lives outside ordinary catalog, customer, order, category, or content records. Custom fields, metafields, apps, external identifiers, and connected systems may carry storefront, operational, fulfillment, reporting, or integration meaning.

Prepare a custom-data and dependency inventory that identifies:

* product custom fields that appear on product pages or support internal workflows;
* metafields used by apps, storefront logic, integrations, or reporting;
* external IDs used by ERP, CRM, PIM, inventory, fulfillment, accounting, marketing, analytics, or marketplace systems;
* app-owned data that affects subscriptions, loyalty, reviews, personalization, merchandising, search, product options, or pricing;
* theme or storefront behavior that changes how migrated data appears to customers;
* Custom Platform structures that require interpretation before they can become BigCommerce-ready data.

Not every custom field needs the same treatment. Some are descriptive and can be migrated as reference information. Others drive business behavior and may require Add-ons, Custom Service, app configuration, external-system work, or custom migration logic adjustment.

#### Custom-data preparation pass condition <a href="#custom-data-preparation-pass-condition" id="custom-data-preparation-pass-condition"></a>

Custom-data preparation is ready when each important custom field, metafield, app dependency, and external identifier has an owner, purpose, target-state decision, and validation sample. Unclassified custom data should not be assumed safe simply because it can be exported.

### Prepare Access, Backups, and Migration Inputs <a href="#prepare-access-backups-and-migration-inputs" id="prepare-access-backups-and-migration-inputs"></a>

Preparation also needs the operational basics that allow the migration to be executed and reviewed safely. These inputs should be gathered after the business meaning is clear enough to avoid moving incomplete or misunderstood data.

Prepare access and input readiness for:

* Source Platform access, export access, API credentials, admin permissions, and data-owner contacts;
* Target Store access, BigCommerce admin permissions, app setup, storefront/channel readiness, and test environment expectations;
* catalog exports, customer exports, order exports, URL inventories, content inventories, and media references;
* active app and integration lists with owners and business purpose;
* backup or rollback expectations for the Source Platform and operational records;
* freeze-window expectations for product, pricing, customer, content, and order changes before Full Migration.

Access readiness should not be treated as a substitute for planning. A technically complete export can still create migration risk when the business has not clarified target behavior.

#### Input-readiness pass condition <a href="#input-readiness-pass-condition" id="input-readiness-pass-condition"></a>

Input readiness is complete when the migration team can access required systems, understand which data sets are authoritative, identify who owns each business area, and confirm which changes should pause before Full Migration.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration is most valuable when sample records are chosen to reveal BigCommerce-specific interpretation risk. Simple records may prove that migration can run, but they rarely prove that the Target Store will preserve important business behavior.

A strong BigCommerce Demo Migration sample should include:

* products with ordinary variants and products with more complex option/modifier behavior;
* products with custom fields, metafields, app-owned behavior, or external IDs;
* important category paths and product assignments;
* customer groups and price-list examples;
* bulk-pricing or exception-pricing examples, when applicable;
* storefront/channel assignment examples;
* high-value product, category, CMS Page, and Blog Post URLs;
* customer-account and order-history examples;
* Custom Platform records that do not fit ordinary structures cleanly.

Demo Migration samples should be selected by risk, not convenience. If the sample only includes simple records, a successful sample may still leave the highest-risk migration questions unanswered.

#### Demo Migration pass condition <a href="#demo-migration-pass-condition" id="demo-migration-pass-condition"></a>

The sample is ready when each selected record has a reason for inclusion and an expected pass condition. The review team should know what the sample is meant to prove before reviewing the migrated output.

### Prepare Validation Ownership Before Migration Begins <a href="#prepare-validation-ownership-before-migration-begins" id="prepare-validation-ownership-before-migration-begins"></a>

Validation should be planned before execution so reviewers know what they are judging. BigCommerce migration output can look complete to one reviewer and incomplete to another if business ownership is unclear.

Assign reviewers for:

* product choices, variants, modifiers, and custom product behavior;
* category structure, navigation, and merchandising;
* customer groups, price lists, bulk pricing, and commercial segmentation;
* storefront/channel scope and visibility;
* CMS Pages, Blog Posts, URLs, redirects, and route intent;
* customer accounts, order history, and support-sensitive scenarios;
* custom fields, metafields, apps, integrations, and external IDs;
* operational handoffs to fulfillment, ERP, CRM, accounting, marketing, analytics, or marketplace systems.

Each reviewer should have concrete evidence to check. A merchandising reviewer may catch category or product-choice issues that a technical reviewer would not treat as failed data. A pricing reviewer may catch a commercially serious issue that is invisible in record counts.

#### Validation-readiness pass condition <a href="#validation-readiness-pass-condition" id="validation-readiness-pass-condition"></a>

Validation readiness is complete when each high-risk area has a reviewer, sample records, expected behavior, and pass condition before migration execution begins.

### How Additional Migration Options Affect Preparation <a href="#how-additional-migration-options-affect-preparation" id="how-additional-migration-options-affect-preparation"></a>

Additional Migration Options can help handle later migration activity, but they do not remove the need for preparation. If the merchant expects new orders, new customers, changed products, updated content, new Blog Posts, or pricing updates between Demo Migration and Full Migration, preparation should identify which changes need later review.

The preparation plan should track:

* which entities are likely to change after Demo Migration;
* which changed records could affect product behavior, pricing, storefront scope, or URL continuity;
* which follow-up migration activity may need renewed validation;
* which already-recorded Product, Customer, Order, or Blog Posts records should not consume Entity Points again simply because migration activity continues under the same service license;
* which new records may still consume Entity Points when migrated for the first time.

Additional Migration Options should be treated as follow-up migration handling, while the preparation plan still needs to define changed records and renewed review needs early. The safer approach is to prepare for changed records and revalidation needs before the final launch window becomes urgent.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce preparation is strongest when the business defines the Target Store’s commercial meaning before migration execution begins. Product options, variants, modifiers, category discovery, price lists, customer groups, storefront scope, redirects, content, custom fields, apps, external identifiers, and validation ownership all need clear preparation because they influence how the migrated store behaves.

Use Demo Migration to test the records that expose the highest BigCommerce-specific risk. If product choices, pricing logic, storefront assignments, custom fields, external identifiers, or Custom Platform structures remain difficult to classify, Live Chat can help determine whether the work fits Standard Service, benefits from Managed Service support, needs Add-ons, or should be reviewed under Custom Service.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to BigCommerce?**

Start with high-risk product-choice structures, especially products where variants, modifiers, personalization, bundles, app-owned behavior, SKU, inventory, price, or order detail could be misinterpreted. Then prepare categories, pricing context, storefront scope, URLs, custom data, and validation samples.

**Should BigCommerce preparation focus mainly on product records?**

No. Products are central, but BigCommerce preparation should also cover categories, customer groups, price lists, channels, redirects, CMS Pages, Blog Posts, custom fields, metafields, apps, external identifiers, and validation ownership.

**Why do customer groups and price lists need preparation?**

They can affect what different customers see and pay. If the relationship between customers, price lists, bulk rules, and storefront context is unclear, migrated records may look complete while pricing behavior is commercially wrong.

**How should URL preparation be handled for BigCommerce migration?**

High-value product, category, CMS Page, Blog Post, campaign, and support routes should be prioritized before migration. Each important old URL should point to a destination that preserves buyer intent, not only to a technically valid redirect.

**When does BigCommerce preparation need Custom Service review?**

Custom Service review is usually safer when the Source Platform has custom product-choice logic, app-owned pricing or merchandising behavior, unusual storefront assignments, custom fields that drive business behavior, external-system identifiers, or Custom Platform data that requires interpretation beyond standard supported behavior.
