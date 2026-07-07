# Jumpseller Data Model Differences

Migrating to Jumpseller is not only a matter of placing records into a new admin panel. The important question is how each record will behave once Jumpseller becomes the operating environment for catalog management, inventory control, checkout, order handling, discovery, and storefront presentation.

Jumpseller is especially sensitive to the difference between catalog structure and storefront behavior. Product names, categories, options, variants, stock values, custom fields, product descriptions, order records, customer records, payment status, fulfillment status, and navigation settings all have operational meaning after migration. A source store may store similar information, but it may not use the same boundaries between product data, page content, checkout configuration, theme code, and app behavior.

The goal of data-model review is to define what each source data element should become inside Jumpseller before the migration is treated as successful. A clean record count is not enough. Products must be usable, variants must represent real buyable combinations, categories must support discovery, customers and orders must preserve business context, and unsupported data must be routed through Add-ons or Custom Service instead of being forced into the wrong field.

### Product Data Becomes Jumpseller Catalog Structure <a href="#product-data-becomes-jumpseller-catalog-structure" id="product-data-becomes-jumpseller-catalog-structure"></a>

Jumpseller product records carry both selling information and merchandising information. A product is not only a title and price. It can include images, categories, pricing, stock behavior, status, options, variants, custom fields, SEO fields, and descriptive content that influences both search and conversion.

A source product may arrive with fields such as SKU, name, short description, long description, regular price, sale price, brand, tags, category IDs, images, meta title, URL key, stock quantity, dimensions, product type, visibility, downloadable file, supplier information, and app-created attributes. During Jumpseller migration, each field needs a destination decision: standard product field, option/variant field, custom field, content block, SEO field, unsupported field, or Custom Service review.

| Source product element       | Jumpseller interpretation                                    | Migration implication                                                   |
| ---------------------------- | ------------------------------------------------------------ | ----------------------------------------------------------------------- |
| Product name                 | Primary product identity and discovery signal                | Needs cleanup if the source uses SKU-like or overly promotional names   |
| Product images               | Product presentation assets, with possible variant image use | Image order and variant association need sampling after migration       |
| Description                  | Product-page persuasion and information layer                | HTML-heavy descriptions may need display review in the active theme     |
| Price and sale price         | Commerce pricing fields                                      | Source discount logic should not be confused with migrated price values |
| Product status or visibility | Availability and storefront exposure                         | Source hidden, archived, draft, or disabled states need mapped meaning  |
| SEO fields and URL data      | Search and continuity inputs                                 | Slugs, meta fields, and redirects need separate review where preserved  |
| App-created attributes       | Extra operational or merchandising logic                     | May require Custom Service if no standard Jumpseller destination exists |

The practical risk is assuming that every source product field is equally important. In Jumpseller, some fields directly affect buying behavior, some affect discovery, and some are only internal reference data. Data-model review should separate these meanings before migration starts.

### Options, Variants, Custom Inputs, and Custom Fields Have Different Roles <a href="#options-variants-custom-inputs-and-custom-fields-have-different-roles" id="options-variants-custom-inputs-and-custom-fields-have-different-roles"></a>

Variant-heavy catalogs require special attention because Jumpseller separates several ideas that source platforms sometimes blur together. Product options can generate variants, and those variants can have their own SKU, price, stock, weight, and images. Other option types collect customer input or support customization without creating a stocked variant.

This distinction matters because a source store may use the same attribute system for size, color, engraving text, gift wrapping, file upload, bundle choice, or internal classification. In Jumpseller, each of these meanings needs a different handling path.

| Source meaning                                  | Better Jumpseller interpretation         | Why it matters                                                           |
| ----------------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------ |
| Size or color with separate stock               | Variant-generating option                | Each combination may need SKU, stock, price, and image validation        |
| Personalization message                         | Text Input or Text Area style input      | It should not create artificial stock combinations                       |
| Customer upload                                 | File input behavior                      | Needs checkout/product-page handling review, not only product import     |
| Gift wrap or optional extra                     | Optional add-on or non-variant selection | It may affect price without becoming a core product variant              |
| Brand, material, region, or technical attribute | Custom field where supported             | Useful for filtering or product information without multiplying variants |
| Source app configurator data                    | Custom Service review                    | Complex configurators rarely map cleanly to standard product options     |

The most important data-model question is whether a source attribute represents a real sellable unit, a customer choice, a product descriptor, a filterable attribute, or a custom workflow. If that distinction is skipped, Jumpseller may receive technically valid product data that creates confusing buying paths.

### Variant Limits and Combination Logic Need Source-Side Translation <a href="#variant-limits-and-combination-logic-need-source-side-translation" id="variant-limits-and-combination-logic-need-source-side-translation"></a>

Jumpseller supports structured product options and variants, but variant logic still needs careful translation. A source platform may allow a large number of combinations, app-based option rules, conditional option visibility, dependent selections, pricing formulas, or custom bundles. Jumpseller expects product options and variant combinations to follow its own operational model.

A clean migration plan should identify products that have high variant counts, unusual option dependencies, or mixed option meanings before migration. These products are more likely to need mapping rules, manual cleanup, Add-ons, or Custom Service review.

| Product pattern                  | Data-model concern                                 | Review priority                                                     |
| -------------------------------- | -------------------------------------------------- | ------------------------------------------------------------------- |
| Size x color x material grid     | Combination count and stock accuracy               | Confirm all real variants are created and purchasable               |
| Made-to-order product            | Customer input vs stock control                    | Avoid creating fake inventory variants                              |
| Configurable product from an app | Conditional logic may not be native                | Review whether Custom Service is needed                             |
| Bundle or kit                    | Relationship between parent product and components | Decide whether to migrate as product data, content, or custom logic |
| Digital product                  | No physical inventory or shipping expectation      | Confirm delivery and checkout behavior after migration              |

Variant review should be sample-based and risk-based. The goal is not only to count variants, but to confirm that the migrated product behaves like a real customer-facing product inside Jumpseller.

### Categories Are Product Organization, Not the Whole Storefront Path <a href="#categories-are-product-organization-not-the-whole-storefront-path" id="categories-are-product-organization-not-the-whole-storefront-path"></a>

Jumpseller categories organize products and support browsing, filtering, navigation, and merchandising. However, source platforms may treat categories as multiple things at once: taxonomy, URL structure, menu placement, landing-page content, search facet, campaign grouping, and SEO asset.

When categories migrate, the key question is not only whether the category names exist. The question is whether category structure still supports product discovery in the new store.

| Source category role | Jumpseller planning question                                   | Validation signal                                        |
| -------------------- | -------------------------------------------------------------- | -------------------------------------------------------- |
| Product grouping     | Are products assigned to the correct categories?               | Category pages contain the expected products             |
| Hierarchy            | Does parent-child structure still make sense?                  | Subcategories support natural browsing                   |
| Menu placement       | Should the category appear in navigation?                      | Main menu and category menu are intentionally configured |
| SEO landing page     | Are title, description, URL, and content preserved or rebuilt? | Search-facing category pages remain meaningful           |
| Filter source        | Are filterable attributes category-relevant?                   | Customers can narrow products without confusion          |

A source store may have categories that are useful for internal management but weak for customer browsing. Migration is a good moment to distinguish operational categorization from storefront navigation. Jumpseller can hold product-category relationships, but the merchant still needs to validate menu structure, category order, product sorting, and filter usefulness.

### Product Filters Depend on Options and Custom Product Fields <a href="#product-filters-depend-on-options-and-custom-product-fields" id="product-filters-depend-on-options-and-custom-product-fields"></a>

Jumpseller product filters can be shaped by product options and custom product fields. This makes attribute planning important. A field that looks minor in the source store may become part of the customer’s discovery experience after migration.

For example, a clothing store may rely on color, size, material, gender, brand, and price filters. A parts store may rely on model compatibility, technical specification, year range, and manufacturer. A food store may rely on allergens, package size, diet type, and storage condition. These are not just data fields; they affect whether customers can narrow the catalog efficiently.

| Attribute type        | Migration decision                           | Poor outcome if ignored                             |
| --------------------- | -------------------------------------------- | --------------------------------------------------- |
| True option           | Use as product option or variant structure   | Customers cannot choose the correct buyable version |
| Filterable descriptor | Use as suitable custom field where supported | Customers cannot narrow the catalog effectively     |
| Internal-only note    | Keep out of storefront-facing fields         | Sensitive or confusing content appears publicly     |
| App-generated filter  | Review for target-side replacement           | Important discovery behavior disappears             |

The data model should preserve the difference between what customers select, what customers filter by, what staff use internally, and what custom logic uses behind the scenes.

### Customer Data Becomes Account and Contact Context <a href="#customer-data-becomes-account-and-contact-context" id="customer-data-becomes-account-and-contact-context"></a>

Customer data migration into Jumpseller should preserve identity, communication context, and commercial history where supported. The source store may contain customer accounts, billing addresses, shipping addresses, tags, groups, tax IDs, marketing consent, loyalty data, notes, wholesale status, account approval state, password hashes, and app-created segmentation.

Not all of those elements have the same destination. Some belong in standard customer fields, some belong in custom fields or notes if supported, some belong in external CRM systems, and some require Custom Service if they control business logic.

| Customer source data   | Jumpseller meaning                             | Migration consideration                                                           |
| ---------------------- | ---------------------------------------------- | --------------------------------------------------------------------------------- |
| Name and email         | Customer identity                              | Duplicate or shared emails need cleanup before migration                          |
| Address records        | Billing and shipping context                   | Validate formatting and country/region consistency                                |
| Customer group or type | Pricing, segmentation, or operational handling | Confirm whether target configuration supports the same business use               |
| Marketing consent      | Communication permission                       | Do not treat as a generic tag without compliance review                           |
| Password hash          | Authentication behavior                        | Passwords usually cannot be migrated as active login credentials across platforms |
| Loyalty or app data    | External business logic                        | Custom Service or third-party integration review may be needed                    |

The key issue is continuity of customer recognition. A migrated customer record has value only if staff can identify the customer, understand their history, and serve them correctly in the new store.

### Orders Become Historical and Operational Records <a href="#orders-become-historical-and-operational-records" id="orders-become-historical-and-operational-records"></a>

Orders carry commercial history, but they also reflect source-specific checkout, payment, fulfillment, tax, promotion, and shipping behavior. In Jumpseller, order records include payment and fulfillment statuses, purchased products, customer information, billing and shipping details, totals, discounts, taxes, and additional information where present.

Historical orders should be treated as reference records, not as proof that the new checkout has been configured. A migrated order can preserve past business context, but live payment gateways, shipping methods, fulfillment processes, and checkout rules still need target-side setup and testing.

| Order component        | Data-model meaning                   | Validation focus                                                 |
| ---------------------- | ------------------------------------ | ---------------------------------------------------------------- |
| Order ID and date      | Historical reference                 | Confirm ordering, timestamps, and lookup logic                   |
| Purchased items        | Commercial record of what was bought | Confirm product names, quantities, prices, discounts, and totals |
| Customer details       | Order-level contact context          | Confirm email, phone, billing, and shipping fields               |
| Payment status         | Historical payment state             | Do not confuse migrated status with gateway configuration        |
| Fulfillment status     | Operational completion state         | Confirm fulfillment history is interpretable                     |
| Additional information | Checkout-specific extra context      | Review whether source custom checkout fields have a destination  |

The strongest validation sample includes orders across several statuses: paid, pending, canceled, fulfilled, partially fulfilled, discounted, taxed, shipped, and customized. If only simple paid orders are sampled, hidden data-model issues remain easy to miss.

### Inventory Becomes Stock Behavior, Not Just a Number <a href="#inventory-becomes-stock-behavior-not-just-a-number" id="inventory-becomes-stock-behavior-not-just-a-number"></a>

Inventory data in Jumpseller has product and variant meaning. Stock can be tracked at product or variant level, and inventory can be adjusted through the inventory area, CSV, or integrations. Source inventory data should be reviewed for stock ownership, unlimited stock behavior, location logic, backorder rules, preorder handling, and ERP synchronization.

| Source inventory pattern         | Jumpseller interpretation issue                              | Recommended review                                            |
| -------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------- |
| Variant-level stock              | Stock belongs to each buyable combination                    | Validate high-risk products by SKU and option combination     |
| Unlimited or non-stocked product | Stock should not block purchasing                            | Confirm unlimited or digital-product behavior                 |
| Multi-location stock             | Location-level meaning may need configuration or integration | Review whether target store supports the required stock model |
| ERP-controlled stock             | Inventory may be integration-owned                           | Confirm post-migration sync path before launch                |
| Negative or backorder logic      | Source behavior may not directly match                       | Define target checkout expectation separately                 |

Inventory should be validated through storefront behavior, not only admin values. A product with correct stock in the admin can still fail if the wrong variant is purchasable, unavailable, or displayed with incorrect option imagery.

### Content, Pages, Blog Posts, and SEO Fields Need Storefront Interpretation <a href="#content-pages-blog-posts-and-seo-fields-need-storefront-interpretation" id="content-pages-blog-posts-and-seo-fields-need-storefront-interpretation"></a>

Source content does not automatically become effective Jumpseller storefront content. Product descriptions, category descriptions, CMS pages, blog posts, meta titles, meta descriptions, URL slugs, image alt text, redirects, and internal links all require interpretation.

For Next-Cart planning, CMS pages should be treated as **Trang Hệ thống quản lý nội dung (CMS pages)**&#x77;hen the source store contains pages such as About Us, Shipping Policy, Returns, Privacy Policy, Size Guide, brand pages, or campaign landing pages. These pages may be migrated as content records where supported, rebuilt manually, or handled through Custom Service depending on structure and platform compatibility.

| Content element      | Migration question                               | Quality signal                                           |
| -------------------- | ------------------------------------------------ | -------------------------------------------------------- |
| Product description  | Is formatting usable in Jumpseller theme?        | Description is readable, styled, and complete            |
| Category description | Does it still support SEO and browsing?          | Category page has meaningful content and product context |
| Blog post            | Does the content model map cleanly?              | Article content, images, and URLs remain usable          |
| CMS page             | Should it migrate, be rebuilt, or be redesigned? | Policy and evergreen pages are easy to find and read     |
| Redirect             | Is traffic continuity protected?                 | Priority legacy URLs resolve to the right destination    |
| Internal link        | Does it point to a valid Jumpseller page?        | No source-domain or broken internal paths remain         |

Content migration should be planned as a customer-facing quality issue. A complete content record that renders poorly or links to old URLs is not truly successful.

### Payment, Shipping, Tax, and Fulfillment Data Must Be Separated From Configuration <a href="#payment-shipping-tax-and-fulfillment-data-must-be-separated-from-configuration" id="payment-shipping-tax-and-fulfillment-data-must-be-separated-from-configuration"></a>

Source data often includes payment method names, shipping method names, tax lines, discount rules, fulfillment states, and gateway transaction references. These fields help explain historical orders, but they are not the same as live Jumpseller configuration.

This separation prevents one of the most common migration misunderstandings: assuming that historical order data proves the new checkout is ready. Migration can preserve order context, but payment gateways, shipping rates, fulfillment providers, taxes, and checkout settings must be configured and tested in Jumpseller.

| Source record               | Historical data role            | Target-side setup role                             |
| --------------------------- | ------------------------------- | -------------------------------------------------- |
| Payment method on old order | Explains how the order was paid | Does not activate the gateway                      |
| Shipping line on old order  | Explains what was charged       | Does not create shipping rules                     |
| Tax amount                  | Preserves historical total      | Does not configure future tax behavior             |
| Fulfillment status          | Preserves operational state     | Does not connect a carrier or fulfillment provider |
| Discount on order           | Explains historical promotion   | Does not recreate all promotion rules              |

Article 3 should keep this distinction clear: data meaning and configuration readiness are related, but they are not the same layer.

### Apps, API, Webhooks, and Theme Code Are Surrounding Meaning Layers <a href="#apps-api-webhooks-and-theme-code-are-surrounding-meaning-layers" id="apps-api-webhooks-and-theme-code-are-surrounding-meaning-layers"></a>

Jumpseller supports apps, APIs, webhooks, and theme-level customization. Source stores may rely on extensions, modules, scripts, checkout customizations, loyalty tools, ERP connectors, CRM syncing, marketplace feeds, custom fields, or custom templates. These elements may create or interpret data, but they do not automatically become standard migration fields.

| Source dependency          | Data-model question                                 | Likely handling path                                                   |
| -------------------------- | --------------------------------------------------- | ---------------------------------------------------------------------- |
| App-created product fields | Are these descriptive fields or business rules?     | Add-ons for supported mapping; Custom Service for unsupported behavior |
| ERP IDs                    | Are they required for future sync?                  | Preserve through suitable fields or Custom Service review              |
| Theme code                 | Does it only display data, or does it create logic? | Rebuild or Custom Service depending on dependency                      |
| Webhook workflow           | Does another system need migrated identifiers?      | Integration planning outside simple content transfer                   |
| Marketplace feed data      | Does it map to Jumpseller or a sales-channel app?   | Review target-side channel configuration                               |

A useful migration plan identifies which data must be migrated, which data must be recreated, which behavior must be reconfigured, and which logic requires Custom Service.

### What Migrated Data Must Prove Inside Jumpseller <a href="#what-migrated-data-must-prove-inside-jumpseller" id="what-migrated-data-must-prove-inside-jumpseller"></a>

The end state of Article 3 is a proof model. Data-model success means the migrated records behave correctly in Jumpseller, not only that they exist.

| Data area       | Required proof                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| Products        | Key products are visible, complete, correctly priced, and assigned to the right categories                         |
| Variants        | Option combinations, SKU, stock, price, image, and availability are accurate                                       |
| Categories      | Product groupings, hierarchy, menu exposure, and discovery behavior are intentional                                |
| Customers       | Identity, addresses, account context, and segmentation are usable                                                  |
| Orders          | Historical status, totals, line items, payment, fulfillment, address, and additional information are interpretable |
| Inventory       | Stock behavior matches real buyable units and operational expectations                                             |
| Content and SEO | Product/category/page content renders cleanly, with priority URLs and metadata reviewed                            |
| Integrations    | External IDs, app fields, and custom logic are preserved only where intentionally supported                        |

If a source data element cannot pass this proof model through standard fields, it should be classified before migration. That classification is what prevents avoidable cleanup after launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Jumpseller migration requires a careful interpretation of data meaning. Products become structured selling records, options and variants control buyable combinations, categories shape discovery, inventory controls availability, customers preserve identity, orders preserve commercial history, and content determines whether the new storefront remains understandable.

The strongest migration plans do not force every source field into the nearest available destination. They decide what each field means, how Jumpseller should use it, and whether standard migration, Add-ons, or Custom Service is the right handling path. That is how migrated data becomes usable, not merely transferred.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are Jumpseller product options and custom fields the same thing?**

No. Product options can represent customer selections and may generate variants, while custom fields are better suited for descriptive product information that does not create a distinct stocked product combination.

**Why do variants need separate review during Jumpseller migration?**

Variants can carry SKU, stock, price, images, and availability. A migration can appear complete at product level while still failing at the variant level if option combinations or variant attributes are wrong.

**Do migrated categories automatically recreate the old storefront navigation?**

No. Categories can preserve product organization, but navigation menus, category ordering, filters, and storefront discovery should be reviewed separately inside Jumpseller.

**Can historical orders prove that payment and shipping are ready?**

No. Historical orders preserve past payment, shipping, tax, and fulfillment context. Live checkout behavior still requires Jumpseller-side configuration and testing.

**What happens to source app data that does not fit standard Jumpseller fields?**

It should be reviewed before migration. Some app-created data can be mapped through supported fields or Add-ons, while unsupported app logic, external IDs, or custom behavior may require Custom Service.
