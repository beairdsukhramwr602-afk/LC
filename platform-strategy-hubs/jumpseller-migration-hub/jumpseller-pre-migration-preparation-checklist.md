# Jumpseller Pre-Migration Preparation Checklist

Preparing for a migration to Jumpseller is not only a data-export task. Jumpseller is a hosted commerce platform with its own way of handling product records, categories, product options, variants, inventory, customer accounts, orders, pages, languages, payment methods, shipping methods, apps, SEO settings, and store administration. The preparation stage should make those expectations clear before the migration run begins.

The most useful preparation work separates three questions. What data should move? What business meaning must remain usable after the move? What must be configured directly in Jumpseller because it is not simply migrated as historical data? A source store can contain clean records and still create operational problems if product options are misunderstood, categories are copied without navigation planning, order statuses lose meaning, or customer groups are expected to preserve pricing or access rules automatically.

Preparation should therefore produce reviewable evidence, not only a checklist of exported files. The store team should know which product examples will be tested, which categories matter for customer discovery, which customer records need special review, which orders represent real operational history, which URLs require redirects, and which app or integration behavior needs separate planning.

### Confirm the Store Role and Launch Expectations <a href="#confirm-the-store-role-and-launch-expectations" id="confirm-the-store-role-and-launch-expectations"></a>

Start by defining what Jumpseller is expected to become after migration. Some projects use Jumpseller as a cleaner hosted replacement for a complex legacy store. Others use it to support a regional catalog, a simpler DTC storefront, multilingual selling, social channels, digital products, appointments, subscriptions, or a more manageable back-office workflow. These choices affect the required preparation.

A Jumpseller migration should not be planned only around record counts. A store with a moderate number of products can be complex if product options drive pricing, stock, shipping, or personalization. A store with fewer customers can still require careful handling if customer accounts include marketing consent, billing history, tax identifiers, language preferences, or B2B-like segmentation. A store with ordinary pages can still need careful SEO review if those pages receive search traffic or support product discovery.

| Preparation question                              | Evidence to prepare                                                                                                                      | Why it matters                                                                                              |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| What is Jumpseller replacing?                     | Full live store, regional store, simplified catalog, campaign store, or new commerce channel                                             | The intended role affects catalog scope, content scope, redirects, payment setup, and validation priorities |
| What must be ready at launch?                     | Products, categories, checkout, payments, shipping, languages, customer access, content, redirects, and integrations                     | Migration can move records before the operational store is ready to sell                                    |
| What requires configuration instead of migration? | Theme navigation, payment gateways, shipping methods, tax settings, app behavior, checkout fields, language settings, and sales channels | These areas often need setup and testing inside Jumpseller, not only transferred data                       |
| What should be tested first?                      | Representative product, customer, order, content, and URL samples                                                                        | Demo Migration should expose real complexity instead of confirming only simple records                      |

A useful readiness test is whether the store team can explain how a customer will find a product, choose its options, complete checkout, receive order communication, and return later for account or order history. If that path is unclear, preparation should continue before the migration is treated as straightforward.

### Prepare Product, Option, and Variant Evidence <a href="#prepare-product-option-and-variant-evidence" id="prepare-product-option-and-variant-evidence"></a>

Jumpseller product preparation should start with catalog behavior. Product records normally include names, descriptions, images, categories, prices, stock, product status, SEO fields, and product-page content. The deeper preparation question is whether a source product is a simple product, an option-based product, a variant-driven product, a digital product, a custom-field product, a made-to-order product, or a product controlled by apps or external systems.

Jumpseller supports product options and variants, but the source platform may not use those concepts in the same way. Some source stores use options only for shopper input, while others use options to create sellable variants with separate SKUs, prices, stock, images, or weights. Some use custom fields as product specifications. Others use app data for bundles, kits, subscriptions, download delivery, product builders, or personalization. These meanings should be classified before migration.

| Product evidence              | What to review                                                                                                       | Strong Demo Migration sample                                                                                |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Simple products               | Name, description, price, SKU, images, category, stock, status, and SEO fields                                       | A normal active product and one hidden, inactive, or low-stock product if the source uses visibility states |
| Variant products              | Option names, option values, SKU differences, price differences, stock differences, images, weight, and availability | A product where the selected option changes SKU, price, stock, and image                                    |
| Dense option products         | Large option matrices, unusual combinations, unavailable combinations, or products close to option/variant limits    | The most complex sellable product, not the cleanest product                                                 |
| Product specifications        | Custom fields, technical attributes, product filters, brand values, material, size charts, and comparison data       | A product where specifications affect shopper decisions or search/filter behavior                           |
| Non-standard product behavior | Digital files, subscriptions, appointments, made-to-order data, bundles, kits, personalization, or app-owned logic   | A product whose purchase behavior cannot be explained by ordinary product-and-variant structure             |

The goal is not to force every source field into a Jumpseller product field. The goal is to decide which data should become product content, which should become product options, which should become variant-level information, which should become custom-field or filterable information, and which requires separate handling.

### Prepare Categories, Filters, and Navigation <a href="#prepare-categories-filters-and-navigation" id="prepare-categories-filters-and-navigation"></a>

Jumpseller categories help organize products and support customer browsing. They should not be treated as a blind copy of the source category tree. Many source stores use categories for several overlapping purposes: navigation menus, SEO landing pages, brand pages, merchandising collections, seasonal campaigns, filtering logic, internal catalog management, and product grouping. Preparation should separate those meanings.

Create a category map before migration. The map should identify current source categories, products assigned to each category, important category URLs, intended Jumpseller category hierarchy, navigation placement, and any categories that should be merged or retired. If the old store has outdated categories or duplicate merchandising paths, migration is an opportunity to preserve useful organization while avoiding unnecessary clutter.

| Category area       | Preparation task                                                                                     | Review signal                                                                           |
| ------------------- | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Category hierarchy  | Decide which categories should exist, which should become subcategories, and which should be retired | The target catalog structure supports browsing rather than copying historical clutter   |
| Product assignments | Check product membership in important categories                                                     | Products appear where shoppers expect them, not only where the old database placed them |
| Navigation menus    | Decide which categories, pages, and campaign areas belong in menus                                   | Storefront navigation is planned separately from raw product category migration         |
| Filters             | Identify values that should help shoppers narrow products                                            | Filters are based on useful product options or custom fields, not accidental attributes |
| SEO landing pages   | List high-value category and collection URLs                                                         | Redirects and destination quality can be reviewed before launch                         |

A strong preparation outcome is a category structure that supports Jumpseller storefront discovery. A weak preparation outcome is a large category tree that technically moved but no longer helps customers find products.

### Prepare Customer, Account, and Segmentation Data <a href="#prepare-customer-account-and-segmentation-data" id="prepare-customer-account-and-segmentation-data"></a>

Customer preparation should clarify how customer records will be used after migration. Some records are mainly needed for historical order lookup. Others support repeat purchase, customer service, email marketing, tax handling, language-specific communication, or special pricing workflows. The preparation stage should identify which customer fields are simple profile data and which fields represent business logic.

Prepare a customer field inventory that includes names, emails, phone numbers, billing and shipping addresses, account status, marketing consent, language preference, customer group labels, tax identifiers, and custom fields. Also check for duplicate customer records, shared email addresses, incomplete addresses, and guest orders that should remain understandable after migration.

| Customer evidence   | What to prepare                                                                                   | Why it matters                                                                              |
| ------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Identity fields     | Name, email, phone, billing address, shipping address, and account status                         | Customer records need a stable identity for service and order review                        |
| Segmentation fields | Customer groups, tags, marketing consent, language preference, tax identifiers, and custom fields | Labels may migrate, but pricing, tax, access, or communication rules need separate planning |
| Account continuity  | Login expectations, password reset communication, and customer-facing account experience          | Password behavior and account activation should not be assumed late in the launch process   |
| Guest history       | Guest orders, duplicate emails, and incomplete customer records                                   | Historical order lookup can become confusing if customer identity is not reviewed           |
| B2B-like behavior   | Trade terms, special pricing, restricted products, payment eligibility, and tax handling          | These are business rules, not just customer fields                                          |

Customer preparation should avoid overpromising. Moving customer records does not automatically recreate every source account workflow. If groups or custom fields controlled business behavior in the old store, the logic should be reviewed as a configuration, Add-on, or Custom Service question depending on its complexity.

### Prepare Orders, Payments, Fulfillment, and Historical Meaning <a href="#prepare-orders-payments-fulfillment-and-historical-meaning" id="prepare-orders-payments-fulfillment-and-historical-meaning"></a>

Order preparation should preserve historical meaning rather than only record existence. A migrated order should help staff understand what was purchased, who purchased it, how much was paid, where it was shipped, which taxes or discounts applied, whether fulfillment happened, and what the current historical status means. That requires more than moving order IDs and totals.

Review order statuses before migration. Source stores may use statuses such as pending, paid, shipped, partially shipped, cancelled, refunded, partially refunded, returned, failed, abandoned, awaiting payment, awaiting fulfillment, or custom staff-defined statuses. These statuses may not have exact Jumpseller equivalents. The preparation task is to determine which statuses need to remain as readable historical information and which workflows must be configured for future orders.

| Order area          | Evidence to prepare                                                                                                     | Demo Migration sample                                                    |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Order identity      | Order number, order date, customer association, billing email, and source reference                                     | A normal paid order with clear customer linkage                          |
| Line items          | Products, variants, options, quantities, prices, discounts, taxes, shipping, and totals                                 | An order with variant products and discount/tax impact                   |
| Payment history     | Payment method, payment status, transaction reference, failed payment, refund, or partial refund                        | Paid, unpaid, refunded, and partially refunded examples where available  |
| Fulfillment history | Shipping method, fulfillment status, tracking, delivery details, pickup information, or external fulfillment references | Fulfilled, unfulfilled, and partially fulfilled examples where available |
| Custom order data   | Checkout notes, custom fields, gift messages, internal staff comments, external IDs, or app data                        | An order that contains source-specific information important to staff    |

The best order samples are not only the cleanest orders. Include orders that reveal status, payment, fulfillment, refund, and custom-field complexity. If staff cannot interpret migrated order history after Demo Migration, the order preparation set was too narrow.

### Prepare Content, SEO, and Redirect Evidence <a href="#prepare-content-seo-and-redirect-evidence" id="prepare-content-seo-and-redirect-evidence"></a>

Jumpseller migrations often involve more than commerce records. Content pages, Blog Posts, product descriptions, category descriptions, images, metadata, URL slugs, language versions, and redirects can affect customer trust and search performance. Preparation should identify which content must be preserved, which content should be cleaned, and which URLs need special attention.

Build a content inventory before migration. Include CMS Pages, Blog Posts, high-value landing pages, help pages, policy pages, category pages, product URLs, and any source pages that drive organic traffic or paid campaigns. Also identify pages that should not be migrated because they are outdated, duplicated, campaign-specific, or no longer relevant.

| SEO and content area | What to prepare                                                                     | Review focus                                                                    |
| -------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Product URLs         | Source product URLs, intended Jumpseller destinations, and high-value product pages | Product pages that matter for revenue or search should have clear destinations  |
| Category URLs        | Category, collection, brand, and campaign URLs                                      | Important discovery pages need redirect planning and destination-quality review |
| CMS Pages            | About, contact, policies, FAQs, buying guides, sizing guides, and help content      | Pages should be usable in the new storefront, not only present as text          |
| Blog Posts           | Titles, slugs, images, publish dates, author data, metadata, and internal links     | Blog continuity may matter for SEO, education, and campaign history             |
| Internal links       | Links inside pages, posts, product descriptions, and navigation                     | Links should not point back to old URLs or broken destinations                  |
| Metadata             | SEO titles, meta descriptions, image alt text, and language-specific metadata       | Metadata should remain aligned with the new page structure                      |

Redirect preparation should prioritize value, not volume alone. A high-traffic product, category, or content page deserves more review than an old low-value page. The destination should also be meaningful; redirecting many old URLs to the home page can preserve little customer or SEO value.

### Prepare Languages, Markets, Payments, Shipping, and Taxes <a href="#prepare-languages-markets-payments-shipping-and-taxes" id="prepare-languages-markets-payments-shipping-and-taxes"></a>

Jumpseller can support international and multilingual selling, but language and market preparation should be explicit. Source stores may store translations across product fields, categories, content pages, blog posts, metadata, navigation menus, email templates, or apps. These values need review before migration, especially when the source platform uses custom translation structures or language-specific URLs.

Payment, shipping, and tax behavior also requires configuration. Historical order data can be migrated as records, but future checkout behavior depends on Jumpseller settings, payment gateways, shipping methods, tax rules, and any required apps or custom workflows. Preparation should identify the difference between old transaction history and future checkout readiness.

| Area      | Migration preparation                                                              | Configuration preparation                                                                       |
| --------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Languages | Identify translated product, category, content, SEO, and URL fields                | Confirm language setup and review how translated content will be displayed                      |
| Markets   | Identify countries, currencies, tax zones, delivery regions, and customer segments | Confirm whether Jumpseller setup supports the required selling model                            |
| Payments  | Preserve readable historical payment method and status where relevant              | Configure payment gateways and test checkout before launch                                      |
| Shipping  | Preserve historical shipping method and fulfillment data where relevant            | Configure shipping methods, rates, pickup options, delivery zones, and fulfillment expectations |
| Taxes     | Preserve historical tax amounts and tax identifiers where relevant                 | Configure future tax behavior according to the target selling countries and product rules       |

A migration can move past order history without making future checkout ready. These two tasks should be validated separately.

### Prepare Apps, External Systems, and Custom Requirements <a href="#prepare-apps-external-systems-and-custom-requirements" id="prepare-apps-external-systems-and-custom-requirements"></a>

Apps and integrations are often the hidden source of migration complexity. A source store may depend on apps for reviews, subscriptions, bundles, product feeds, loyalty points, email marketing, invoicing, ERP sync, warehouse sync, marketplace listings, POS workflows, custom checkout fields, or product personalization. Preparation should identify which behavior belongs to native Jumpseller setup, which can be handled by Add-ons, and which requires Custom Service.

Use a dependency inventory. List each app, integration, script, feed, external ID, webhook, API connection, and manual back-office process that affects product, customer, order, inventory, fulfillment, pricing, tax, or content behavior. Then decide whether the dependency should be rebuilt, retired, replaced, or reviewed for custom handling.

| Dependency type            | Preparation question                                                                     | Likely handling                                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Standard source data       | Is the data supported and structurally clean?                                            | Standard Service or Managed Service may be suitable                                                     |
| Filtering or mapping needs | Does the project need selective migration, value adjustment, or supported configuration? | Add-ons may be relevant                                                                                 |
| Custom fields              | Do custom fields only describe records, or do they drive business behavior?              | Add-ons may help with supported mapping; Custom Service may be needed for bespoke behavior              |
| App-owned data             | Is critical data stored in an app, plugin, module, extension, or external database?      | Custom Service review is usually required                                                               |
| External identifiers       | Are IDs used by ERP, fulfillment, accounting, marketplace, or reporting systems?         | Custom Service review may be required if identifiers must be transformed or preserved in a specific way |
| Custom logic               | Does source behavior require custom migration logic adjustment?                          | Custom Service                                                                                          |

Preparation should make these dependencies visible before full migration. Hidden app or integration behavior is one of the easiest ways for a technically successful migration to become operationally incomplete.

### Choose Demo Migration Samples Deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration should prove whether the prepared migration path can handle the real store, not only whether simple records move. A useful sample set includes normal cases, difficult cases, high-value cases, and records tied to external behavior.

| Sample group       | Include                                                                                                                                   | What the result should prove                               |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Catalog basics     | Simple product, hidden product, low-stock product, and important category                                                                 | Ordinary product records are readable and usable           |
| Product complexity | Variant-heavy product, custom-field product, digital product, or made-to-order product                                                    | Product behavior is not flattened or misrepresented        |
| Discovery          | Category hierarchy, filters, product order, SEO landing pages, and internal links                                                         | Customers can find products in the new structure           |
| Customers          | Customer with full addresses, duplicate-risk customer, marketing-consent example, language-specific customer, and group-labelled customer | Customer identity and segmentation remain usable           |
| Orders             | Paid, unpaid, refunded, fulfilled, partially fulfilled, and custom-status examples                                                        | Historical order meaning remains understandable            |
| Content and SEO    | CMS Pages, Blog Posts, metadata, old URLs, and redirect-sensitive pages                                                                   | Content continuity and URL planning are realistic          |
| Integrations       | Records linked to ERP, warehouse, marketplace, invoicing, feeds, or custom apps                                                           | External dependencies are identified before full migration |

The Demo Migration should lead to a decision. If samples look good, the selected approach can proceed. If only ordinary records work, expand the sample set. If complex records fail because the requirement is outside standard behavior, move the project into Add-on or Custom Service review depending on the issue.

### Pre-Migration Readiness Checklist <a href="#pre-migration-readiness-checklist" id="pre-migration-readiness-checklist"></a>

Use the final readiness review to confirm that preparation has produced usable decisions. The goal is not to complete every future store configuration before migration; it is to avoid migration assumptions that will create rework later.

| Readiness area        | Pass condition                                                                                                                |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Store role            | The team knows what Jumpseller must support at launch and what can be configured after migration                              |
| Catalog               | Product types, options, variants, custom fields, images, categories, filters, and inventory cases have representative samples |
| Customers             | Customer identity, groups, addresses, account expectations, and marketing/tax fields have been reviewed                       |
| Orders                | Historical order statuses, payments, fulfillment, refunds, and custom order data have sample coverage                         |
| Content and SEO       | Important pages, posts, metadata, internal links, and URLs have been inventoried                                              |
| Languages and markets | Translation, payment, shipping, tax, region, and currency assumptions have been separated from record migration               |
| Apps and integrations | App-owned data, external IDs, feeds, custom fields, and custom logic are visible before execution                             |
| Demo Migration        | Samples include ordinary, difficult, high-value, and dependency-linked records                                                |

If several areas remain uncertain, the project should not be treated as fully prepared. The safer move is to expand preparation, adjust the migration scope, or review whether the project needs Add-ons, Managed Service, or Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Preparing for a Jumpseller migration means translating the source store into a clear operating plan before execution. Product data, categories, filters, customers, orders, content, redirects, languages, payments, shipping, taxes, apps, and external systems should be reviewed for business meaning, not only export availability.

The strongest preparation work produces representative samples and clear decisions. It shows which records can move through a standard path, which areas need configuration, which fields require mapping or filtering, and which dependencies require Custom Service review. When preparation is done well, Demo Migration becomes a useful decision point instead of a superficial preview.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before a Jumpseller migration?**

Start with the store role, catalog behavior, product option structure, customer/account expectations, order-history requirements, content and URL priorities, and any apps or integrations that affect business operations. These areas shape the migration scope more than record counts alone.

**Should categories be copied exactly from the source store?**

Not automatically. Categories should be reviewed for customer discovery, product assignment, navigation, filters, and SEO value. Some source categories should be preserved, while others may need cleanup, merging, or different storefront placement.

**What product samples should be included in Demo Migration?**

Include simple products, variant-heavy products, products with custom fields, digital or made-to-order products if relevant, high-value products, and products connected to stock, pricing, image, or app behavior. A sample set made only of simple products can hide real migration risk.

**Do payment and shipping settings migrate as part of order history?**

Historical payment and shipping information may be preserved as order data where supported, but future checkout behavior depends on Jumpseller configuration. Payment gateways, shipping methods, taxes, delivery regions, and checkout testing should be handled separately.

**When should app or integration data be reviewed as Custom Service?**

Custom Service review is appropriate when important data is stored in apps, plugins, modules, extensions, external systems, custom fields, external IDs, or bespoke workflows that cannot be represented through standard supported migration behavior.

**How do Add-ons fit into preparation?**

Add-ons can support filtering, mapping, and configuration needs when the requirement fits available supported behavior. They should not be used as a catch-all for unsupported app data, external identifiers, or custom migration logic adjustment; those cases belong in Custom Service review.
