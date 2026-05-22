# Shift4Shop Pre-Migration Preparation Checklist

Shift4Shop preparation should focus on how the store needs to operate after migration, not only on which records need to move. Because Shift4Shop combines storefront building, product and order management, SEO, marketing, inventory, shipping, payment-related operations, themes, apps, and support resources in one hosted E-commerce platform, the safest preparation starts by clarifying how those layers should work together in the new store.

A well-prepared Shift4Shop migration gives reviewers enough context to judge whether migrated products remain sellable, categories remain useful, customers and orders remain meaningful, and important storefront routes still support traffic continuity. The preparation work should also identify where older 3DCart-era records, exports, staff notes, or integrations need to be interpreted against current Shift4Shop behavior.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

Pre-migration preparation reduces uncertainty before the migration begins. It helps the business decide what must be preserved, what should be cleaned up, what can be restructured, and what needs deeper review in Demo Migration.

For Shift4Shop, preparation usually concentrates on five practical questions:

* Is the catalog structure clear enough to rebuild product browsing and purchasing behavior?
* Are customer, order, shipping, payment, tax, and promotion records understandable after migration?
* Are priority URLs and SEO-sensitive pages identified before the store changes platform context?
* Are built-in features, apps, themes, scripts, and custom behavior separated from core migrated data?
* Are older 3DCart references understood well enough to avoid planning against outdated assumptions?

### Preparation Priority 1: Clarify the Shift4Shop Store Model <a href="#preparation-priority-1-clarify-the-shift4shop-store-model" id="preparation-priority-1-clarify-the-shift4shop-store-model"></a>

Before reviewing records, define what the Shift4Shop store is expected to become. A merchant moving into Shift4Shop may want a simpler hosted store, a more feature-rich storefront, stronger built-in marketing and SEO support, or a cleaner operating model than the previous platform allowed.

The preparation file should record:

* the main sales model: retail, B2B, wholesale, subscription-like, catalog-first, or content-supported selling
* the expected storefront structure
* important customer groups or buyer types
* payment, shipping, tax, and checkout expectations
* marketing, SEO, promotion, and coupon behavior that must remain meaningful
* whether the store depends on apps, scripts, design customization, or external systems

This prevents the migration from being judged only by record count. A Shift4Shop result should support the way the business expects to sell after launch.

### Preparation Priority 2: Review Product and Option Structure <a href="#preparation-priority-2-review-product-and-option-structure" id="preparation-priority-2-review-product-and-option-structure"></a>

Products are usually the first place where Shift4Shop preparation needs detail. A product can be simple in record count but complex in selling behavior if it depends on options, variants, pricing rules, images, descriptions, stock behavior, related products, or custom display logic.

Prepare product samples that show:

* simple products
* products with multiple options
* products with required and optional selections
* products with price-changing choices
* products with inventory-sensitive choices
* products with multiple images or detailed descriptions
* products that use custom fields, extra tabs, or app-driven content
* products that represent high revenue or high search traffic

Do not prepare only clean examples. Include difficult products because those reveal whether the migration can preserve meaningful buying behavior in Shift4Shop.

### Preparation Priority 3: Map Categories, Navigation, and Storefront Discovery <a href="#preparation-priority-3-map-categories-navigation-and-storefront-discovery" id="preparation-priority-3-map-categories-navigation-and-storefront-discovery"></a>

Shift4Shop preparation should include more than product records. Category hierarchy, navigation structure, featured collections, internal links, filters, and product grouping all affect whether customers can find products after migration.

Prepare a clear record of:

* main category hierarchy
* categories that should be consolidated, removed, or renamed
* products assigned to multiple categories
* high-priority landing pages
* navigation menus that carry commercial value
* internal links from content pages to products or categories
* category URLs that should be preserved or redirected

This is especially important when the source store uses old naming, outdated categories, or duplicated navigation created over time.

### Preparation Priority 4: Identify SEO-Sensitive URLs and Content Pages <a href="#preparation-priority-4-identify-seo-sensitive-urls-and-content-pages" id="preparation-priority-4-identify-seo-sensitive-urls-and-content-pages"></a>

A migration to Shift4Shop can affect page routes, metadata, product URLs, category URLs, blog or content pages, and redirect planning. Prepare URL information before migration so SEO-sensitive paths are not discovered only after launch.

Create a priority URL list that includes:

* top product URLs
* top category URLs
* pages with backlinks or search traffic
* CMS Pages and important content pages
* landing pages used in advertising or email campaigns
* old 3DCart-era URLs that still receive traffic or appear in internal references
* URLs that should be redirected instead of abandoned

URL preparation does not need to solve every redirect decision immediately. It should identify which routes deserve careful review during Demo Migration and launch planning.

### Preparation Priority 5: Prepare Customer and Order Review Samples <a href="#preparation-priority-5-prepare-customer-and-order-review-samples" id="preparation-priority-5-prepare-customer-and-order-review-samples"></a>

Customer and order history should remain useful after migration, even when the old platform and Shift4Shop organize operational details differently.

Prepare representative samples for:

* active customers
* customers with multiple orders
* guest checkout records where available
* customers associated with special pricing, groups, or tax handling
* completed orders
* refunded, canceled, or partially fulfilled orders
* orders with coupons, discounts, shipping rules, or special payment conditions
* orders that are important for support, warranty, or accounting review

The goal is not to recreate the old admin screen exactly. The goal is to preserve enough business meaning for staff to understand customers, order history, and post-launch support context.

### Preparation Priority 6: Separate Built-In Shift4Shop Features from Custom or App-Dependent Behavior <a href="#preparation-priority-6-separate-built-in-shift4shop-features-from-custom-or-app-dependent-behavior" id="preparation-priority-6-separate-built-in-shift4shop-features-from-custom-or-app-dependent-behavior"></a>

Shift4Shop includes many built-in commerce features, but not every source-store behavior is automatically a core migrated data object. Some behavior may come from apps, custom scripts, template changes, external systems, manual workflows, or older 3DCart-era customization.

Before migration, identify whether each important behavior belongs to:

* core product, category, customer, order, coupon, or content data
* Shift4Shop built-in configuration
* an app or integration
* design/theme behavior
* custom code or scripts
* manual staff workflow
* external systems such as ERP, accounting, shipping, marketing, or CRM tools

This distinction helps prevent unrealistic migration expectations. Data migration can preserve records and supported structures, but custom behavior, third-party logic, and outside-system dependencies need separate review.

### Preparation Priority 7: Clarify 3DCart Source Context Without Making It the Project Focus <a href="#preparation-priority-7-clarify-3dcart-source-context-without-making-it-the-project-focus" id="preparation-priority-7-clarify-3dcart-source-context-without-making-it-the-project-focus"></a>

Some migration projects may involve a Source Platform that staff still call 3DCart. This is useful preparation context because older exports, admin labels, support notes, URLs, integrations, or documentation may still use that name.

Treat those references as source-store context. Prepare them only where they help explain current store behavior, historical records, legacy URL structure, or custom dependencies. The migration plan should still evaluate the result through Shift4Shop’s current platform model.

Useful items to collect include:

* old 3DCart export files or field labels that need interpretation
* legacy URLs still used by customers or search engines
* old app or integration references
* staff notes that describe setup rules using older terminology
* historical customization notes that may not match current Shift4Shop behavior

This preparation keeps the rebrand context helpful without turning the project into a platform-history review.

### Preparation Priority 8: Decide Which Records Should Move and Which Should Change <a href="#preparation-priority-8-decide-which-records-should-move-and-which-should-change" id="preparation-priority-8-decide-which-records-should-move-and-which-should-change"></a>

A Shift4Shop migration is a good opportunity to remove obsolete structures if they no longer support the business. However, cleanup should be intentional. Removing or changing data without a clear plan can damage reporting, customer service, SEO, and operational continuity.

Before migration, decide whether to preserve, revise, or exclude:

* outdated products
* inactive categories
* duplicate customers
* obsolete coupons or promotions
* old CMS Pages
* discontinued product images or descriptions
* historical orders that no longer need to be accessible in the new admin context
* old URL paths that should redirect rather than remain active

If only selected records should move, the filtering requirement should be planned clearly. Estimated entity numbers are not migration filters. When the project needs selective migration, the Data Filter Add-on may be relevant where appropriate.

### Preparation Priority 9: Identify Custom Platform or Non-Standard Source Requirements <a href="#preparation-priority-9-identify-custom-platform-or-non-standard-source-requirements" id="preparation-priority-9-identify-custom-platform-or-non-standard-source-requirements"></a>

If the Source Platform is a Custom Platform or if the source store uses non-standard fields, custom database structures, external identifiers, third-party app data, or bespoke business rules, the requirement should be prepared as Custom Service context.

This can include:

* custom fields not represented in standard Shift4Shop structures
* outside-system identifiers used by ERP, CRM, accounting, or fulfillment systems
* app-specific product, customer, or order data
* custom pricing, tax, shipping, or promotion logic
* custom checkout behavior
* modified source data exports
* special transformation rules needed before data can be meaningful in Shift4Shop

Customization or modification work is handled through Custom Service. Custom Service does not automatically mean Next-Cart performs migration execution; migration management is included only when it is part of the final plan.

### Preparation Priority 10: Choose Demo Migration Samples Carefully <a href="#preparation-priority-10-choose-demo-migration-samples-carefully" id="preparation-priority-10-choose-demo-migration-samples-carefully"></a>

Demo Migration should not use only easy records. For Shift4Shop, the sample should include records that reveal the store’s actual complexity.

A strong sample may include:

* one simple product
* one product with several options
* one high-value or high-traffic product
* one product from a complex category path
* one customer with several orders
* one order with discount, tax, shipping, or payment complexity
* one CMS Page or content page with internal links
* one SEO-sensitive URL path
* one record affected by legacy 3DCart naming or old source-store assumptions

The point of the sample is to expose whether the migration result is understandable, usable, and aligned with current Shift4Shop planning expectations.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

A useful Shift4Shop preparation sequence is:

1. Define the store model and expected selling workflow.
2. Review product, option, category, customer, and order structures.
3. Identify SEO-sensitive URLs and content pages.
4. Separate core data from configuration, apps, themes, scripts, and external systems.
5. Clarify any 3DCart-era source references that still affect data interpretation.
6. Decide what should move, what should change, and what should be excluded.
7. Identify Custom Platform or non-standard source requirements.
8. Choose Demo Migration samples that represent real business complexity.
9. Assign reviewers who understand catalog, customer, order, SEO, and operational meaning.
10. Use Demo Migration results to confirm whether the final migration plan is safe enough.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for Shift4Shop migration means preparing the business logic around the records, not just gathering export files. Product options, category discovery, customer and order meaning, SEO routes, payment and checkout assumptions, built-in features, apps, and legacy source context all influence whether the migrated store will be usable after launch.

Before moving forward, prepare a sample set that reflects the real store: complex products, important categories, active customers, representative orders, priority URLs, and any source-store records that still use older 3DCart references. Use Demo Migration to confirm whether those records remain commercially meaningful in Shift4Shop before finalizing the full migration plan.

### FAQs <a href="#faqs" id="faqs"></a>

**Should I prepare 3DCart information before migrating to Shift4Shop?**

Prepare 3DCart information only when it helps explain the Source Platform context. Older exports, field names, URLs, app references, or staff notes may still use the 3DCart name. Those details should help clarify the source store, while the migration result should be planned around current Shift4Shop behavior.

**What product samples should I include before migration?**

Include more than simple products. Prepare products with options, price-changing selections, inventory-sensitive choices, multiple images, detailed descriptions, important categories, and high search or revenue value. These records make Demo Migration more useful because they show whether the migrated catalog remains sellable.

**Do estimated entity numbers decide which records migrate?**

No. Estimated entity numbers support pricing and Entity Points planning. They are not automatic migration filters. If only selected records should move, the migration needs filtering rules, such as the Data Filter Add-on where appropriate.

**When does a Shift4Shop migration need Custom Service?**

Custom Service is needed when the project requires customization, modification, Custom Platform handling, third-party app or integration data, custom fields, outside-system identifiers, custom migration logic adjustment, or special transformation rules. Custom Service does not automatically include migration management unless that is part of the final plan.

**What should Demo Migration prove before the full migration?**

Demo Migration should prove that important products, options, categories, customers, orders, content pages, and priority URLs remain understandable and usable in Shift4Shop. It should also reveal whether old source-store assumptions, including 3DCart-era references, need cleanup or custom handling before the full migration.
