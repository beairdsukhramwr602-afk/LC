# BigCommerce Pre-Migration Preparation Checklist

A BigCommerce migration becomes easier to control when preparation is treated as a storefront-structure decision rather than solely a data-cleanup task.

BigCommerce can be a strong Target Platform for merchants that want hosted operations, clearer product-choice governance, structured pricing context, stronger catalog administration, and more deliberate storefront scope. However, those strengths are useful only when the business has already decided how the future store should work. If product options, categories, customer groups, price lists, storefront assignments, redirects, apps, or custom fields remain vague, the migration may look organized in record counts while still creating uncertainty during validation and launch.

This checklist helps merchants prepare for migration into BigCommerce before execution begins. It is not a technical configuration guide. It is a planning framework for clarifying the business meaning that the Target Platform must preserve, formalize, or intentionally change.

### What This BigCommerce Preparation Checklist Is For <a href="#what-this-bigcommerce-preparation-checklist-is-for" id="what-this-bigcommerce-preparation-checklist-is-for"></a>

The purpose of preparation is to reduce interpretation risk before migration results are judged.

A strong checklist should help the business answer practical questions such as:

* Which product-choice structures must remain precise?
* Which categories carry real browse, merchandising, or SEO meaning?
* Which customer groups, price lists, or pricing rules must remain commercially accurate?
* Which storefront contexts should share data and which should differ?
* Which app, theme, custom field, or external system behaviors still affect the customer or operations?
* Which URLs and landing paths need focused continuity planning?
* Which records should be included in Demo Migration because they reveal the highest risk?

The checklist is strongest when it is built around customer behavior, operational meaning, and validation evidence rather than around a generic list of records to move.

### Preparation Priority 1: Define High-Risk Product-Choice Structures <a href="#preparation-priority-1-define-high-risk-product-choice-structures" id="preparation-priority-1-define-high-risk-product-choice-structures"></a>

BigCommerce preparation should begin with product behavior because product-choice interpretation often affects catalog usability, pricing, inventory, and conversion.

#### Identify products that need more than ordinary product transfer <a href="#identify-products-that-need-more-than-ordinary-product-transfer" id="identify-products-that-need-more-than-ordinary-product-transfer"></a>

Before migration, the business should identify:

* product families that generate the most revenue
* products with many options, sizes, colors, materials, bundles, or configurations
* products where some choices are true sellable variants
* products where some choices behave more like modifiers or personalization inputs
* products where source-side option logic depends on apps, extensions, custom code, or theme behavior
* products where incorrect structure would change price, inventory, SKU, order detail, or customer choice

The goal is to decide how each important product choice should be represented in BigCommerce. A product may look simple on the storefront but depend on source-side logic that does not translate cleanly as an ordinary product record.

#### Separate variants, modifiers, and surrounding customization <a href="#separate-variants-modifiers-and-surrounding-customization" id="separate-variants-modifiers-and-surrounding-customization"></a>

A useful preparation step is to classify product-choice behavior into three groups.

**True sellable differences**

These are choices that should behave like distinct purchasable product outcomes, often with their own SKU, inventory, price, weight, image, or availability.

**Modifier-style choices**

These are customer selections that affect the purchase but may not represent a separate stock-managed product variation.

**Surrounding customization logic**

These are behaviors that may depend on custom fields, apps, external systems, manual review, or storefront-specific business rules.

This distinction matters because BigCommerce can support structured product choices, but it still requires the business to decide which meaning belongs in the product model and which meaning belongs in surrounding logic. When the source structure is unclear or custom, the preparation work may signal a need for Custom Service or custom migration logic adjustment.

### Preparation Priority 2: Clarify Category and Discovery Meaning <a href="#preparation-priority-2-clarify-category-and-discovery-meaning" id="preparation-priority-2-clarify-category-and-discovery-meaning"></a>

Categories should be prepared as customer-facing discovery structures, not only as administrative containers.

#### Identify categories that matter to the buying journey <a href="#identify-categories-that-matter-to-the-buying-journey" id="identify-categories-that-matter-to-the-buying-journey"></a>

Before migration, the business should identify:

* high-traffic category pages
* categories used in major navigation paths
* categories that support merchandising or seasonal campaigns
* categories that carry organic search value
* categories that customers use to compare products
* categories that are outdated, duplicated, or no longer commercially meaningful

The goal is to separate real catalog meaning from inherited taxonomy clutter. If the source store has accumulated categories over time, not every structure deserves equal preservation.

#### Decide what BigCommerce should preserve or simplify <a href="#decide-what-bigcommerce-should-preserve-or-simplify" id="decide-what-bigcommerce-should-preserve-or-simplify"></a>

Some category structures should remain close to the source because they support customer behavior, SEO continuity, or merchandising logic. Others may be better simplified before migration so that BigCommerce begins with a cleaner catalog structure.

The preparation checklist should identify which category paths are non-negotiable, which can be reorganized, and which should be removed from the future storefront plan.

### Preparation Priority 3: Define Customer Groups and Price Lists <a href="#preparation-priority-3-define-customer-groups-and-price-lists" id="preparation-priority-3-define-customer-groups-and-price-lists"></a>

BigCommerce preparation should treat pricing context as commercial logic, not only as product price data.

#### Identify pricing structures that must remain accurate <a href="#identify-pricing-structures-that-must-remain-accurate" id="identify-pricing-structures-that-must-remain-accurate"></a>

The business should document:

* customer groups that still matter
* wholesale, B2B, retail, loyalty, or negotiated pricing segments
* price lists or pricing structures that affect customer-specific buying experience
* discounts or promotions that depend on customer group, catalog, or storefront context
* inherited workarounds that should be simplified instead of copied
* pricing behavior controlled by apps or external systems

This is especially important when a store sells to different customer types, brands, regions, sales channels, or account groups.

#### Confirm what pricing logic belongs in BigCommerce <a href="#confirm-what-pricing-logic-belongs-in-bigcommerce" id="confirm-what-pricing-logic-belongs-in-bigcommerce"></a>

Not every source-side pricing rule should be copied exactly. Some rules may be outdated, redundant, app-owned, or better represented through a cleaner BigCommerce structure.

Preparation should decide which pricing meaning must be preserved, which should be redesigned, and which needs further review before migration scope is finalized.

### Preparation Priority 4: Decide Storefront Scope and Assignment Logic <a href="#preparation-priority-4-decide-storefront-scope-and-assignment-logic" id="preparation-priority-4-decide-storefront-scope-and-assignment-logic"></a>

BigCommerce storefront planning is strongest when the business decides storefront scope before migration execution begins.

#### Define what should be shared and what should differ <a href="#define-what-should-be-shared-and-what-should-differ" id="define-what-should-be-shared-and-what-should-differ"></a>

The checklist should clarify:

* whether the business needs one storefront or multiple storefront contexts
* which products should appear in each storefront
* which categories should differ by storefront
* which customer groups or price lists belong to which storefront context
* which content, brands, regions, languages, currencies, or campaigns require separate treatment
* which operational workflows should remain shared across storefronts

A Multi-Storefront structure can be useful, but it adds governance burden when product, pricing, content, or customer assignments are unclear.

#### Avoid treating storefront expansion as an afterthought <a href="#avoid-treating-storefront-expansion-as-an-afterthought" id="avoid-treating-storefront-expansion-as-an-afterthought"></a>

If multiple storefronts are part of the target plan, storefront assignment should be included in preparation, Demo Migration sample selection, and validation planning. Otherwise, the migrated store may look correct in one storefront while hiding assignment issues in another.

### Preparation Priority 5: Plan Customer Account Expectations <a href="#preparation-priority-5-plan-customer-account-expectations" id="preparation-priority-5-plan-customer-account-expectations"></a>

Customer migration should be prepared around the real post-migration customer experience, not around assumptions from the Source Platform.

#### Define what returning customers should experience <a href="#define-what-returning-customers-should-experience" id="define-what-returning-customers-should-experience"></a>

The business should clarify:

* whether returning customers can access accounts as expected
* whether password behavior, login reset, or account activation needs customer communication
* which customer groups or account types are most sensitive
* how order history should appear from the customer perspective
* which support scenarios may appear immediately after launch

Customer records may migrate successfully while the customer experience still requires planning. This is especially important when the source platform and BigCommerce handle accounts, passwords, identities, or customer groups differently.

#### Prepare communication-sensitive scenarios <a href="#prepare-communication-sensitive-scenarios" id="prepare-communication-sensitive-scenarios"></a>

If customer login behavior changes, preparation should include support messaging, launch communication, and internal response guidelines. The goal is to avoid treating customer-account continuity as a hidden technical detail that only becomes visible after go-live.

### Preparation Priority 6: List Apps, Theme Logic, and Custom Behaviors <a href="#preparation-priority-6-list-apps-theme-logic-and-custom-behaviors" id="preparation-priority-6-list-apps-theme-logic-and-custom-behaviors"></a>

A BigCommerce migration can be affected by behavior that does not live neatly inside product, customer, category, or order records.

#### Identify business-critical dependencies <a href="#identify-business-critical-dependencies" id="identify-business-critical-dependencies"></a>

The preparation checklist should identify:

* apps that affect product display, personalization, reviews, subscriptions, loyalty, search, merchandising, pricing, or fulfillment
* theme behaviors that influence navigation, trust, product presentation, or conversion
* custom fields that drive storefront output or operational decisions
* external systems connected to inventory, ERP, CRM, fulfillment, analytics, accounting, or marketing
* workflows that depend on source-side identifiers or custom data

The business does not need to preserve every old dependency. It needs to identify which dependencies still carry business meaning.

#### Separate native BigCommerce structure from surrounding behavior <a href="#separate-native-bigcommerce-structure-from-surrounding-behavior" id="separate-native-bigcommerce-structure-from-surrounding-behavior"></a>

Some source-side behavior can be represented through native BigCommerce structure. Other behavior may need apps, external system updates, theme work, or Custom Service review.

Preparation should classify these dependencies before migration begins so they can be scoped, tested, and validated deliberately.

### Preparation Priority 7: Prioritize Legacy URLs and Redirect Intent <a href="#preparation-priority-7-prioritize-legacy-urls-and-redirect-intent" id="preparation-priority-7-prioritize-legacy-urls-and-redirect-intent"></a>

Redirect capability does not replace URL planning.

#### Identify URLs that deserve focused protection <a href="#identify-urls-that-deserve-focused-protection" id="identify-urls-that-deserve-focused-protection"></a>

Before migration, the business should identify:

* product URLs with meaningful organic traffic or conversion value
* category and landing-page URLs used in search, paid campaigns, email, affiliates, or partner links
* brand, content, or support pages that still carry trust or customer-service value
* outdated URLs that should not be preserved as primary paths
* destinations that best match the old page intent

The most important question is not only whether a redirect exists. It is whether the redirected destination still satisfies the intent of the old URL.

#### Avoid generic destination mapping for high-value pages <a href="#avoid-generic-destination-mapping-for-high-value-pages" id="avoid-generic-destination-mapping-for-high-value-pages"></a>

A redirect from an old product or category page to a generic collection, homepage, or loosely related page can weaken customer experience even if it is technically valid. High-value paths should be mapped with commercial intent in mind and validated before launch.

### Preparation Priority 8: Select High-Risk Demo Migration Samples <a href="#preparation-priority-8-select-high-risk-demo-migration-samples" id="preparation-priority-8-select-high-risk-demo-migration-samples"></a>

Demo Migration is most useful when the sample is chosen because it reveals risk, not because the records are easy.

#### Include records that expose BigCommerce-specific decisions <a href="#include-records-that-expose-bigcommerce-specific-decisions" id="include-records-that-expose-bigcommerce-specific-decisions"></a>

A strong BigCommerce Demo Migration sample should include:

* option-heavy products
* products where variant and modifier meaning could be confused
* categories with important navigation or SEO value
* customer groups with meaningful pricing or visibility differences
* price-list examples, where relevant
* storefront-specific product, category, or pricing cases
* high-value legacy URLs
* app- or theme-dependent storefront behavior
* Custom Platform source records that do not fit ordinary structures cleanly

This turns preparation into evidence. If the sample looks correct only for simple records, it may not prove that the full migration approach is safe.

### Preparation Priority 9: Define Validation Ownership Before Execution <a href="#preparation-priority-9-define-validation-ownership-before-execution" id="preparation-priority-9-define-validation-ownership-before-execution"></a>

Preparation should decide who will judge the migrated BigCommerce result and what evidence they will use.

#### Assign reviewers by business area <a href="#assign-reviewers-by-business-area" id="assign-reviewers-by-business-area"></a>

The checklist should identify reviewers for:

* product and variant/modifier behavior
* category and browse experience
* pricing, customer groups, and price-list logic
* storefront assignment and visibility
* customer account and order history review
* high-value URLs and redirect destinations
* app, theme, and custom-field behavior
* operational handoffs to external systems

Different reviewers may notice different issues. A merchandising reviewer may catch category or product-choice problems that a technical reviewer would not treat as failed data.

#### Define pass conditions early <a href="#define-pass-conditions-early" id="define-pass-conditions-early"></a>

Each validation area should have a practical pass condition. For example, a high-risk product sample should prove that customer choices, price behavior, SKU/inventory meaning, and order output still make sense in BigCommerce. A redirect sample should prove that the destination supports the old page intent, not merely that the redirect fires.

### Preparation Priority 10: Decide What Can Change and What Must Remain Exact <a href="#preparation-priority-10-decide-what-can-change-and-what-must-remain-exact" id="preparation-priority-10-decide-what-can-change-and-what-must-remain-exact"></a>

A BigCommerce migration should not blindly copy every source-side structure, but it also should not simplify business meaning without a decision.

#### Clarify acceptable change before migration <a href="#clarify-acceptable-change-before-migration" id="clarify-acceptable-change-before-migration"></a>

The business should decide what BigCommerce is allowed to formalize, simplify, or reorganize in areas such as:

* product options, variants, and modifiers
* category hierarchy and product assignment
* customer groups and pricing structures
* storefront assignment
* URL structure and redirects
* app-owned or theme-owned behavior
* custom fields and operational identifiers

This helps prevent validation disputes later. If a change was planned, it can be judged as an intentional target-state decision. If a change was not planned and weakens business meaning, it should be treated as an issue.

### Practical BigCommerce Preparation Sequence <a href="#practical-bigcommerce-preparation-sequence" id="practical-bigcommerce-preparation-sequence"></a>

A clear preparation sequence helps keep decisions from becoming scattered.

#### 1. Identify high-risk product-choice cases <a href="#id-1-identify-high-risk-product-choice-cases" id="id-1-identify-high-risk-product-choice-cases"></a>

Start with products most likely to expose variant, modifier, personalization, bundle, or app-owned behavior.

#### 2. Clarify category and discovery meaning <a href="#id-2-clarify-category-and-discovery-meaning" id="id-2-clarify-category-and-discovery-meaning"></a>

Decide which categories support navigation, merchandising, SEO, and customer browsing.

#### 3. Define customer-group and pricing logic <a href="#id-3-define-customer-group-and-pricing-logic" id="id-3-define-customer-group-and-pricing-logic"></a>

Document the customer groups, price lists, discounts, and segmentation rules that affect commercial accuracy.

#### 4. Decide storefront scope <a href="#id-4-decide-storefront-scope" id="id-4-decide-storefront-scope"></a>

Clarify whether one storefront is enough or whether multiple storefront contexts are required.

#### 5. Classify app, theme, custom-field, and external-system behavior <a href="#id-5-classify-app-theme-custom-field-and-external-system-behavior" id="id-5-classify-app-theme-custom-field-and-external-system-behavior"></a>

Identify which non-native behaviors still matter after migration.

#### 6. Prioritize URL continuity <a href="#id-6-prioritize-url-continuity" id="id-6-prioritize-url-continuity"></a>

Map high-value product, category, content, campaign, and support paths before go-live planning begins.

#### 7. Build a risk-based Demo Migration sample <a href="#id-7-build-a-risk-based-demo-migration-sample" id="id-7-build-a-risk-based-demo-migration-sample"></a>

Choose records that expose the hardest structural questions, not only the easiest data.

#### 8. Define validation reviewers and pass conditions <a href="#id-8-define-validation-reviewers-and-pass-conditions" id="id-8-define-validation-reviewers-and-pass-conditions"></a>

Prepare the people and evidence needed to judge whether BigCommerce preserves the intended business meaning.

### How a Custom Platform Source Changes BigCommerce Preparation <a href="#how-a-custom-platform-source-changes-bigcommerce-preparation" id="how-a-custom-platform-source-changes-bigcommerce-preparation"></a>

When the Source Platform is a Custom Platform, preparation usually needs more careful interpretation.

Product-choice logic, pricing rules, customer segmentation, storefront context, route behavior, app-like functions, or operational identifiers may exist in custom structures that do not map directly into BigCommerce. In those situations, preparation should include:

* earlier classification of product-choice and pricing meaning
* more careful separation between native BigCommerce structure and surrounding logic
* review of custom fields, identifiers, and outside-system dependencies
* a stronger Demo Migration sample focused on difficult records
* clearer validation criteria before full migration execution

A Custom Platform source often signals that Custom Service should be reviewed early, especially when the migration requires custom migration logic adjustment, bespoke transformation, or interpretation beyond standard service capability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce preparation is strongest when the business defines the target store’s meaning before migration execution begins.

That means clarifying product-choice structures, category and discovery roles, customer groups, price lists, storefront assignments, customer-account expectations, URL priorities, app or theme dependencies, and validation samples. When those decisions are made early, BigCommerce becomes easier to validate and safer to launch because the migration result can be judged against intended business outcomes rather than vague assumptions.

Before moving deeper into execution, use Demo Migration and the preparation checklist to test the areas where BigCommerce must preserve the most important commercial meaning. If product-choice structure, pricing context, storefront scope, Custom Platform behavior, or app-owned logic remains difficult to classify, Live Chat can help determine whether the issue fits Standard Service, requires Managed Service support, or should be reviewed under Custom Service.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating into BigCommerce?**

Start with the product families most likely to expose product-choice ambiguity, especially products where variants, modifiers, personalization, bundles, or app-owned behavior affect price, inventory, SKU, or order detail. After that, clarify category meaning, customer groups, price-list logic, storefront scope, and high-value URLs.

**Should BigCommerce preparation focus mainly on products?**

No. Products are central, but BigCommerce preparation is also sensitive around categories, customer groups, price lists, storefront assignments, redirects, customer-account expectations, apps, themes, custom fields, and external systems. A product-only checklist can miss important business behavior.

**Why are customer groups and price lists important before migration?**

They can affect what different customers see, what they pay, and how pricing is governed after migration. If customer-group or price-list logic is vague before migration, the target store may contain correct records while still showing commercially incorrect pricing behavior.

**How should legacy URLs be prepared for BigCommerce migration?**

The business should identify high-value products, categories, landing pages, content, campaigns, and support URLs before migration. Each important old URL should have a destination that preserves customer intent, not only a technically valid redirect.

**When does BigCommerce preparation usually need Custom Service review?**

Custom Service review is usually safer when the Source Platform has custom product-choice logic, custom pricing rules, unusual storefront assignments, custom fields that drive behavior, outside-system identifiers, app-like source functions, or route behavior that cannot be represented through standard BigCommerce structures without custom migration logic adjustment.
