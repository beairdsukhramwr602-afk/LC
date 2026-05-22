# PrestaShop Pre-Migration Preparation Checklist

A PrestaShop migration is easier to control when preparation turns storefront assumptions into clear decisions before execution begins.

PrestaShop can support structured product variation, descriptive product features, customer-entered customization fields, customer groups, multistore scope, friendly URLs, modules, themes, and override-shaped behavior. Those strengths become safer when the business defines how each layer should work in the Target Platform. If the source store contains unclear product logic, inherited customer segmentation, loosely governed shop scope, or module-owned behavior that no one has reviewed, the migration may appear complete while still leaving important storefront meaning unresolved.

This checklist is not a setup guide. It is a planning framework for deciding what must be clarified before a PrestaShop migration can be judged as commercially safe, structurally coherent, and realistic to validate.

### What PrestaShop Preparation Should Prove <a href="#what-prestashop-preparation-should-prove" id="what-prestashop-preparation-should-prove"></a>

A useful PrestaShop preparation checklist should prove that the business knows what the future storefront is supposed to preserve, what it is allowed to formalize, and what needs deeper review before migration execution.

#### Preparation should answer practical questions <a href="#preparation-should-answer-practical-questions" id="preparation-should-answer-practical-questions"></a>

Before migration begins, the business should be able to explain:

* which product structures carry the most revenue or customer-choice risk
* which product meaning belongs in combinations, features, or customization fields
* which categories and discovery paths matter to customers
* which customer groups still affect storefront, pricing, visibility, or account treatment
* whether more than one shop context is genuinely needed
* which friendly URLs and legacy paths deserve focused protection
* which modules, themes, overrides, custom fields, or integrations still carry business meaning
* which sample records should be used to expose risk during Demo Migration

The goal is not to document every field in the source store. The goal is to identify the records and behaviors that would make the PrestaShop result commercially wrong if they were translated loosely.

### Preparation Priority 1: Classify High-Risk Product Structures <a href="#preparation-priority-1-classify-high-risk-product-structures" id="preparation-priority-1-classify-high-risk-product-structures"></a>

Product preparation should begin with the product families most likely to expose structural ambiguity.

#### Identify products where structure affects buying behavior <a href="#identify-products-where-structure-affects-buying-behavior" id="identify-products-where-structure-affects-buying-behavior"></a>

The checklist should include:

* products with selectable variation such as size, color, material, bundle, capacity, or configuration
* products where customer choice changes price, SKU, stock, image, weight, availability, or order detail
* products with descriptive values that customers use for comparison
* products that require customer-entered personalization
* products where the source platform mixes selectable options, descriptive fields, and personalization in the same area
* products whose commercial value would weaken if the wrong PrestaShop structure were chosen

PrestaShop preparation should separate sellable variation from descriptive product information and customer-entered personalization. That distinction matters because combinations, product features, and customization fields do not represent the same kind of storefront meaning.

#### Decide what each product structure should become <a href="#decide-what-each-product-structure-should-become" id="decide-what-each-product-structure-should-become"></a>

For high-risk products, the business should decide:

* which choices should become combinations
* which information should remain product features
* which inputs should become customization fields
* which inherited values should be simplified or removed
* which source-side workarounds should not be copied into the target model

This prevents migration review from becoming a vague comparison between old and new product pages. Reviewers should know what each product structure is supposed to prove in PrestaShop.

### Preparation Priority 2: Clarify Product Feature and Comparison Logic <a href="#preparation-priority-2-clarify-product-feature-and-comparison-logic" id="preparation-priority-2-clarify-product-feature-and-comparison-logic"></a>

PrestaShop product features can support descriptive product understanding and comparison. They should not be treated as a dumping ground for every inherited attribute from the Source Platform.

#### Identify commercially meaningful features <a href="#identify-commercially-meaningful-features" id="identify-commercially-meaningful-features"></a>

The checklist should clarify:

* which feature groups help customers compare products
* which feature values still affect buying confidence
* which technical specifications should remain visible
* which inherited source fields are outdated, duplicated, or no longer useful
* which descriptive data should not be converted into selectable product variation

A cleaner feature model makes the PrestaShop catalog easier to browse, maintain, and validate after migration.

### Preparation Priority 3: Define Customization Field Requirements <a href="#preparation-priority-3-define-customization-field-requirements" id="preparation-priority-3-define-customization-field-requirements"></a>

Customer-entered personalization needs early review because it affects storefront behavior and order interpretation.

#### Separate personalization from variation <a href="#separate-personalization-from-variation" id="separate-personalization-from-variation"></a>

The business should identify:

* products that require customer text, file upload, engraving, note, name, image, message, or other personalization input
* which personalization inputs should remain required, optional, or removed
* how personalized details should appear in orders
* whether fulfillment teams need those details in a specific format
* whether personalization behavior currently depends on a module, theme, or custom code

This prevents customer-entered information from being treated like ordinary product variation or hidden order notes. If personalization is commercially important and does not fit standard PrestaShop behavior cleanly, it should be reviewed before the migration approach is finalized.

### Preparation Priority 4: Prepare Categories and Discovery Paths <a href="#preparation-priority-4-prepare-categories-and-discovery-paths" id="preparation-priority-4-prepare-categories-and-discovery-paths"></a>

Category preparation should focus on how customers find products, not only on whether category records exist.

#### Identify category structures that matter <a href="#identify-category-structures-that-matter" id="identify-category-structures-that-matter"></a>

The checklist should include:

* top navigation categories
* high-traffic category pages
* category paths that support organic search or paid campaigns
* categories used for merchandising, seasonal browsing, brand discovery, or product comparison
* duplicate, outdated, or inherited categories that no longer support the buying journey
* categories whose product assignments are unclear or inconsistent

PrestaShop categories should help the future storefront feel governed rather than inherited. If the source taxonomy is messy, preparation should identify what must be preserved, simplified, merged, or retired before migration results are judged.

### Preparation Priority 5: Define Customer Group Meaning <a href="#preparation-priority-5-define-customer-group-meaning" id="preparation-priority-5-define-customer-group-meaning"></a>

Customer groups should be prepared as commercial logic, not only as account labels.

#### Clarify which groups still matter <a href="#clarify-which-groups-still-matter" id="clarify-which-groups-still-matter"></a>

The business should document:

* active customer groups that affect visibility, pricing, discounts, access, or communication
* groups that are inherited but no longer meaningful
* customer segments that should be merged or simplified
* customer records whose group assignment must remain accurate
* storefront differences customers should experience after migration

This is especially important for B2B, wholesale, loyalty, regional, member-only, or tiered-customer models. Customer groups can be migrated as records, but the business still needs to confirm whether they preserve useful customer treatment in PrestaShop.

### Preparation Priority 6: Decide Shop Scope and Multistore Assignments <a href="#preparation-priority-6-decide-shop-scope-and-multistore-assignments" id="preparation-priority-6-decide-shop-scope-and-multistore-assignments"></a>

PrestaShop multistore should be treated as a governance decision, not an automatic upgrade.

#### Decide whether multistore is genuinely needed <a href="#decide-whether-multistore-is-genuinely-needed" id="decide-whether-multistore-is-genuinely-needed"></a>

Before migration, the business should clarify:

* whether the future PrestaShop target needs one shop or multiple shop contexts
* which products belong in each shop
* which categories, customer groups, prices, languages, regions, or storefront experiences should differ by shop
* which data should remain shared across shops
* which source-side store or website divisions are still commercially meaningful
* whether inherited multistore complexity should be simplified

If multistore scope is unclear, the migration can look correct in one context while hiding assignment problems in another. Shop assignments should be part of preparation, sample selection, and later validation.

### Preparation Priority 7: Prioritize Friendly URLs and Legacy Route Intent <a href="#preparation-priority-7-prioritize-friendly-urls-and-legacy-route-intent" id="preparation-priority-7-prioritize-friendly-urls-and-legacy-route-intent"></a>

Friendly URL capability does not remove the need for URL planning.

#### Identify routes that deserve focused protection <a href="#identify-routes-that-deserve-focused-protection" id="identify-routes-that-deserve-focused-protection"></a>

The checklist should include:

* product URLs with meaningful organic traffic or conversion value
* category URLs used in search, paid campaigns, email, affiliates, or partner links
* CMS Pages or landing pages that still carry trust, support, or informational value
* URLs that should not remain primary destinations because their content is outdated
* destination pages that best satisfy the old URL’s intent

The strongest route plan protects customer intent, not just URL text. A legacy path should be mapped to a destination that still answers the commercial or informational purpose of the original page.

### Preparation Priority 8: List Modules, Themes, Overrides, and Custom Behaviors That Still Matter <a href="#preparation-priority-8-list-modules-themes-overrides-and-custom-behaviors-that-still-matter" id="preparation-priority-8-list-modules-themes-overrides-and-custom-behaviors-that-still-matter"></a>

PrestaShop preparation should identify which surrounding behaviors are business-critical before migration scope is treated as stable.

#### Classify behavior outside ordinary records <a href="#classify-behavior-outside-ordinary-records" id="classify-behavior-outside-ordinary-records"></a>

The checklist should include:

* modules that affect product display, search, filtering, personalization, reviews, subscriptions, pricing, payment, shipping, loyalty, tax, or fulfillment
* theme behavior that affects navigation, trust, product presentation, checkout confidence, or conversion
* overrides that change how standard PrestaShop behavior is expected to work
* custom fields used by storefront output, operations, reporting, customer service, or integrations
* external systems connected to inventory, ERP, CRM, marketing, accounting, logistics, or analytics

The business does not need to preserve every old dependency. It needs to identify which dependencies still carry enough meaning to shape scope, Custom Service review, Demo Migration sample selection, or launch-readiness judgment.

### Preparation Priority 9: Select a Risk-Based Demo Migration Sample <a href="#preparation-priority-9-select-a-risk-based-demo-migration-sample" id="preparation-priority-9-select-a-risk-based-demo-migration-sample"></a>

Demo Migration is most useful when the sample is chosen to reveal structural risk.

#### Include records that expose PrestaShop-specific decisions <a href="#include-records-that-expose-prestashop-specific-decisions" id="include-records-that-expose-prestashop-specific-decisions"></a>

A strong PrestaShop Demo Migration sample should include:

* products with combinations
* products with feature-heavy comparison logic
* products with customization fields or personalization requirements
* high-value category paths
* customer groups with meaningful storefront or pricing differences
* shop-specific product, category, or customer-group cases when multistore matters
* high-value legacy URLs
* records shaped by modules, themes, overrides, custom fields, or integrations
* Custom Platform source records that do not fit ordinary PrestaShop structures cleanly

A sample made only of simple products and straightforward customers may pass while leaving the real PrestaShop risks untested.

### Preparation Priority 10: Define Who Reviews Each Outcome <a href="#preparation-priority-10-define-who-reviews-each-outcome" id="preparation-priority-10-define-who-reviews-each-outcome"></a>

Preparation should decide who will judge the migrated result before the full migration is treated as routine.

#### Assign review responsibility by business area <a href="#assign-review-responsibility-by-business-area" id="assign-review-responsibility-by-business-area"></a>

The checklist should identify reviewers for:

* product combinations, features, and customization fields
* category navigation and discovery
* customer groups and account expectations
* multistore assignments, if relevant
* priority URLs and redirect intent
* module-, theme-, override-, or integration-owned behavior
* historical orders and operational interpretation

The best reviewers are the people who understand how the data is used after launch. A migrated result should not be accepted only because records appear; it should be accepted because the right people can confirm that the records still support real storefront and operational use.

### How Custom Platform as a Source Changes PrestaShop Preparation <a href="#how-custom-platform-as-a-source-changes-prestashop-preparation" id="how-custom-platform-as-a-source-changes-prestashop-preparation"></a>

A migration from a Custom Platform into PrestaShop usually needs earlier structural interpretation.

Custom Platform data may contain product-choice logic, customer segmentation, shop context, personalization behavior, route structure, integration identifiers, or custom fields that do not map cleanly into PrestaShop’s native model. In those cases, preparation should include:

* clearer classification of product meaning before migration setup
* earlier review of customer-group and shop-scope logic
* identification of custom fields and outside-system identifiers
* review of whether modules, themes, overrides, or custom behavior need to be recreated, replaced, or excluded
* risk-based Demo Migration sample selection
* Custom Service review for non-standard transformation, Custom Platform handling, custom migration logic adjustment, or bespoke handling needs

Custom Platform as a Source Platform requires Custom Service. That does not automatically mean Next-Cart performs migration management; migration management is included only when it is part of the final plan.

### Practical PrestaShop Preparation Sequence <a href="#practical-prestashop-preparation-sequence" id="practical-prestashop-preparation-sequence"></a>

A useful PrestaShop preparation flow should move from structural decisions to proof planning.

#### 1. Classify product structures first <a href="#id-1-classify-product-structures-first" id="id-1-classify-product-structures-first"></a>

Start with products most likely to expose combinations-versus-features-versus-customization ambiguity.

#### 2. Clarify customer-group meaning <a href="#id-2-clarify-customer-group-meaning" id="id-2-clarify-customer-group-meaning"></a>

Confirm which customer groups still affect storefront treatment, pricing, visibility, or account experience.

#### 3. Decide shop scope <a href="#id-3-decide-shop-scope" id="id-3-decide-shop-scope"></a>

Determine whether the target should use one shop context or a governed multistore structure.

#### 4. Prioritize routes <a href="#id-4-prioritize-routes" id="id-4-prioritize-routes"></a>

Identify the legacy product, category, CMS, and landing-page URLs that deserve focused protection.

#### 5. Review modules, themes, overrides, and custom behaviors <a href="#id-5-review-modules-themes-overrides-and-custom-behaviors" id="id-5-review-modules-themes-overrides-and-custom-behaviors"></a>

Classify which surrounding behaviors still carry business meaning and which should be simplified or replaced.

#### 6. Choose a Demo Migration sample by risk <a href="#id-6-choose-a-demo-migration-sample-by-risk" id="id-6-choose-a-demo-migration-sample-by-risk"></a>

Build the sample around records most likely to reveal whether the PrestaShop target model is safe.

#### 7. Define review responsibility <a href="#id-7-define-review-responsibility" id="id-7-define-review-responsibility"></a>

Assign the people who will check the results before migration acceptance becomes a launch decision.

### Conclusion <a href="#conclusion" id="conclusion"></a>

PrestaShop preparation is strongest when it turns inherited store structure into deliberate target decisions. Products should be classified by meaning, customer groups should be reviewed by commercial usefulness, multistore scope should be justified before it is used, and route continuity should be planned by customer intent rather than convenience.

When those decisions are made before migration execution, PrestaShop becomes easier to validate and safer to govern after launch. When they remain vague, the target may contain the expected records while still failing to preserve the storefront behavior the business depends on.

Before moving deeper into execution, build the preparation checklist around the product structures, customer-group cases, shop assignments, priority routes, and module-shaped behaviors most likely to affect launch confidence. If those areas are difficult to classify, use Demo Migration and Live Chat to decide whether the need is routine PrestaShop translation, a managed execution concern, or a Custom Service requirement.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating into PrestaShop?**

Start with the product structures most likely to expose ambiguity: combinations, features, and customization fields. Then review customer groups, shop scope, priority URLs, module- or theme-owned behavior, and the sample records that should be included in Demo Migration.

**Why are combinations, features, and customization fields so important in PrestaShop preparation?**

They represent different kinds of product meaning. Combinations support selectable variation, features support descriptive or comparative product information, and customization fields support customer-entered personalization. Treating them as interchangeable can make the migrated catalog look complete while weakening storefront behavior.

**Should PrestaShop preparation focus only on products?**

No. Products are central, but PrestaShop preparation also needs customer-group review, category and discovery planning, multistore scope decisions, friendly URL planning, module and theme review, and customer-account expectations.

**When does PrestaShop preparation usually require Custom Service review?**

Custom Service review is usually needed when the source is a Custom Platform, when important behavior depends on custom fields or outside-system identifiers, when module or override logic must be interpreted, or when the business needs custom migration logic adjustment beyond standard service capability.

**Does Custom Service automatically mean Next-Cart manages the whole migration?**

No. Custom Service covers customization, modification, Custom Platform handling, bespoke transformation, or other non-standard requirements. Migration management is included only when it is part of the final plan.
