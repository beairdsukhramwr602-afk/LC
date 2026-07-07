# Cafe24 Pre-Migration Preparation Checklist

Cafe24 migration preparation should begin with evidence, not assumptions. A store may look ready because products, customers, and orders can be exported from the current system, but Cafe24 migration quality depends on whether those records can be interpreted inside Cafe24’s commerce, storefront, member, order, app, API, and market-configuration environment.

The preparation goal is to separate what can move as structured data from what must be configured, rebuilt, mapped, redesigned, reconnected, or reviewed as a custom requirement. That separation protects the migration from a common planning mistake: treating every visible feature of the source store as ordinary data. Cafe24 can support rich commerce structures, member behavior, product options, variants, order operations, Smart Design work, apps, webhooks, and API-managed workflows, but those areas need different preparation evidence.

A good Cafe24 preparation process should leave the team with a clean source dataset, a realistic target-store structure, a clear list of configuration responsibilities, and representative records for Demo Migration review. The checklist below is designed to help merchants prepare that evidence before migration execution.

### Preparation Starts With Scope Separation <a href="#preparation-starts-with-scope-separation" id="preparation-starts-with-scope-separation"></a>

Before reviewing individual data entities, define the boundaries of the Cafe24 migration. The most important preparation question is not only “what data do we have?” It is “what does each part of the store need to become in Cafe24?”

| Preparation layer              | What to clarify before migration                                                                                           | Why it matters in Cafe24                                                                                            |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Structured commerce data       | Products, categories, product options, variants, customers, orders, coupons, and related records that should move as data. | These records need clean mapping so they remain usable inside Cafe24 administration and storefront workflows.       |
| Store configuration            | Payment, shipping, tax, order, security, member, coupon, SEO, redirect, and storefront settings.                           | Configuration controls how the new store behaves after launch and should not be assumed to follow migrated records. |
| Storefront and design behavior | Smart Design work, theme behavior, product-page layout, menus, modules, scripts, and content presentation.                 | Design and storefront behavior often need rebuild or implementation work separate from data migration.              |
| App and integration behavior   | Apps, APIs, webhooks, Data Bridge, analytics, ERP, fulfillment, marketplace, or external reporting workflows.              | Connected systems may depend on identifiers, event flows, or custom fields that need special review.                |
| Custom business logic          | Custom pricing, membership benefits, market rules, checkout changes, order processing, or source-specific behavior.        | Custom behavior may require Custom Service rather than ordinary migration settings.                                 |

This scope separation should be completed before Full Migration. It also helps decide what Demo Migration must test. If difficult records are not identified early, the sample migration may look successful while avoiding the data that actually controls launch quality.

### Prepare the Product Catalog <a href="#prepare-the-product-catalog" id="prepare-the-product-catalog"></a>

Cafe24 catalog preparation should focus on product usability, not just product availability. The source products should be cleaned and classified so migrated records can support browsing, selection, checkout, fulfillment, reporting, and future administration.

Start by reviewing product identity fields. Product names, SKUs, source product identifiers, slugs or SEO references, images, descriptions, brand or manufacturer details, display status, prices, sale prices, tax-related fields, tags, labels, and internal notes should be checked for accuracy and consistency. Duplicates, discontinued products, hidden products, archived products, and test records should be marked before migration so the team does not waste Entity Points or validation time on records that should not become part of the new Cafe24 store.

Product option and variant preparation deserves special attention. Cafe24 product resources include product options, product variants, and variant inventory, which means source option logic should be reviewed as a purchasable structure rather than just display text. A source store that used size and color combinations is different from one that used bundles, conditional product builders, add-on selections, subscription choices, or custom scripts to create choices.

| Catalog evidence to prepare        | What to check                                                                                                            | Cafe24 preparation outcome                                                                           |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| Product inventory list             | Active, inactive, hidden, archived, duplicate, test, and discontinued records.                                           | Confirms which Products should migrate and which should be excluded or filtered.                     |
| Product identifiers                | SKUs, product IDs, variant IDs, supplier IDs, barcodes, external IDs, or ERP references.                                 | Helps preserve operational matching for fulfillment, reporting, and connected systems.               |
| Product descriptions and images    | HTML content, embedded media, image quality, broken image URLs, missing alt context, and unsupported layout assumptions. | Prevents product detail pages from appearing incomplete or visually broken after migration.          |
| Options and variants               | Option names, values, combinations, SKU assignment, inventory handling, prices, and display status.                      | Confirms how customer choices should become Cafe24 product options, variants, and variant inventory. |
| Custom fields and extra attributes | Source-specific product attributes, app-created fields, metafields, technical specifications, and merchandising labels.  | Identifies which fields can be mapped, which need Add-ons, and which require Custom Service review.  |
| Category assignment                | Primary categories, secondary categories, product-list placement, menus, and curated collections.                        | Preserves product discoverability instead of only moving product records.                            |

The goal is to make catalog decisions before migration execution. If the source catalog contains messy option naming, inconsistent SKU conventions, or app-owned product fields, the cleanup should happen before relying on Demo Migration as evidence.

### Prepare Categories, Navigation, and SEO Paths <a href="#prepare-categories-navigation-and-seo-paths" id="prepare-categories-navigation-and-seo-paths"></a>

Cafe24 preparation should treat categories and storefront paths as migration-critical. Categories are not only administrative labels. They influence how products are discovered, how menus are built, how product lists are understood, and how customers reach purchase pages.

The source category tree should be exported or documented with enough detail to show hierarchy, product membership, priority categories, manually curated groups, hidden categories, SEO landing pages, and menu placement. If the source store uses separate category logic for desktop, mobile, market, language, or campaign pages, those differences should be documented before migration.

SEO preparation should include URLs, redirects, metadata, product SEO fields, category-page SEO, high-value landing pages, and internal links. Cafe24 supports redirect and SEO-related resources, but a redirect plan still needs to be prepared. A migration can preserve product and category data while still losing organic visibility if old URLs, menu paths, canonical assumptions, or campaign landing pages are ignored.

| SEO and path area        | Preparation question                                                                 | Evidence to collect                                                                                 |
| ------------------------ | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| Product URLs             | Which product URLs generate traffic, backlinks, ads, or customer support references? | High-value product URL list, redirects, SEO titles, descriptions, and old-to-new path expectations. |
| Category URLs            | Which categories are important for navigation or organic search?                     | Category hierarchy, landing-page copy, product membership, and redirect needs.                      |
| CMS and content pages    | Which content pages support trust, conversion, policies, or SEO?                     | Page URLs, page content, embedded media, internal links, and priority for migration or rebuild.     |
| Internal links           | Which product, category, blog, or policy links appear inside descriptions and pages? | Link inventory and correction plan for changed target-store URLs.                                   |
| Market or language paths | Are URLs segmented by market, language, domain, or subfolder?                        | Domain plan, localization plan, and mapping rules for market-specific paths.                        |

SEO preparation should be practical. Not every old page needs the same treatment, but priority URLs should be identified before migration so redirects and validation can be checked before launch.

### Prepare Customers, Members, and Account Data <a href="#prepare-customers-members-and-account-data" id="prepare-customers-members-and-account-data"></a>

Cafe24 customer preparation should distinguish customer records from member behavior. Customer names, email addresses, phone numbers, addresses, customer groups, account status, memos, purchase history, social-login references, signup fields, and membership benefits may all matter. The migration team should clarify which of these are ordinary customer fields, which are settings, and which belong to custom source logic or third-party systems.

Customer email quality is especially important. Duplicate emails, guest records, inconsistent casing, missing addresses, test accounts, and unsupported account states can create confusion after migration. If customer tiers, membership levels, points, benefits, or B2B-style permissions exist in the source store, they should be reviewed before assuming they will map directly into Cafe24 member behavior.

| Member preparation area         | What to verify                                                                           | Why it matters                                                                                |
| ------------------------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Customer identity               | Email, phone, name, address, customer number, account status, and duplicate records.     | Determines whether repeat customers can be recognized and associated with historical context. |
| Customer groups and tiers       | Membership levels, wholesale groups, benefits, discounts, points, and VIP logic.         | Helps decide whether mapping, configuration, Add-ons, or Custom Service is required.          |
| Guest checkout records          | Orders placed without full account creation or with inconsistent contact information.    | Prevents order history from becoming detached from customer recognition.                      |
| Social-login references         | Naver, Kakao, Apple, or other social account relationships where relevant.               | Helps identify identity behavior that may not be ordinary customer data.                      |
| Customer memos and extra fields | Internal notes, preferences, support flags, custom signup fields, and segmentation data. | Determines whether the fields need mapping, value transformation, or custom handling.         |

Member preparation should also include privacy and consent review. Marketing subscriptions, signup fields, policy acceptance, and consent-sensitive data should be handled according to the merchant’s operational and legal responsibilities.

### Prepare Orders, Payments, Refunds, and Fulfillment Context <a href="#prepare-orders-payments-refunds-and-fulfillment-context" id="prepare-orders-payments-refunds-and-fulfillment-context"></a>

Order migration into Cafe24 should be prepared as historical continuity. Orders help staff answer customer questions, review past purchases, inspect revenue history, and maintain operational context. They do not automatically recreate live checkout, payment gateway setup, shipping rules, tax configuration, return workflows, or order automation.

Before migration, export representative order records and check whether they include order numbers, customer association, order items, product and variant references, quantities, discounts, coupons, totals, taxes, payment status, fulfillment status, shipping addresses, billing addresses, refunds, returns, cancellations, exchanges, tracking data, memos, and labels. Cafe24’s API includes order, payment, shipment, refund, return, and cancellation-related areas, but preparation should still clarify what historical details must remain visible and meaningful.

| Order evidence                       | Preparation focus                                                                            | Validation expectation                                                                             |
| ------------------------------------ | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Recent completed orders              | Items, totals, payment status, shipping status, customer association, and addresses.         | Staff can understand the order after migration and compare it with source records.                 |
| Refunded or returned orders          | Refund amounts, return status, cancellation notes, exchange context, and payment references. | Exceptional order history remains understandable, not flattened into generic order records.        |
| Orders with discounts or coupons     | Coupon codes, promotional discounts, store credits, points, and benefits.                    | Promotional history is interpretable even if future promotion setup must be configured separately. |
| International or multi-market orders | Currency, language, tax, address format, shipping method, and market channel.                | Regional context is preserved enough for support and reporting review.                             |
| App-affected orders                  | Subscription, marketplace, ERP, fulfillment, or custom checkout fields.                      | App-owned or external-system data is flagged for Add-ons or Custom Service review.                 |

The preparation step should also define how far back order history should move. Migrating all historical orders may be valuable for support and reporting, but it also consumes scope. If only a subset is needed, use appropriate filtering decisions before execution rather than treating historical range as an afterthought.

### Prepare Store Configuration and Operational Settings <a href="#prepare-store-configuration-and-operational-settings" id="prepare-store-configuration-and-operational-settings"></a>

Cafe24 migration preparation should list the settings that must be recreated or confirmed in Cafe24. These are not ordinary data-transfer tasks. They affect how the new store behaves after launch.

Payment gateways, shipping methods, tax settings, order-form fields, member signup fields, security settings, store policies, automated messages, currency settings, SEO settings, redirect rules, product display settings, inventory behavior, admin users, and notification settings should be assigned to an owner before launch. Some settings may be configured by the merchant, some by an implementation partner, and some may require coordinated review with Next-Cart when they affect migration results.

| Configuration area         | Preparation requirement                                                                       | Migration boundary                                                                      |
| -------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Payment and checkout       | Payment gateway, payment methods, order form fields, checkout policies, and customer notices. | Live checkout behavior must be configured and tested separately from historical orders. |
| Shipping and fulfillment   | Shipping manager, delivery methods, regions, tracking behavior, and fulfillment ownership.    | Migrated orders do not automatically prove future shipping operations.                  |
| Taxes and currency         | Tax settings, currency behavior, market rules, and regional pricing assumptions.              | Tax and pricing behavior require target-store configuration and validation.             |
| Member settings            | Signup fields, privacy settings, benefits, points, groups, and account-page behavior.         | Customer records do not automatically recreate member program logic.                    |
| SEO and redirects          | Store SEO settings, redirect rules, product/category metadata, and priority URLs.             | URL continuity requires explicit mapping and post-migration checks.                     |
| Notifications and policies | Automated messages, order emails, privacy text, policies, and support messages.               | Communication behavior should be reviewed before launch.                                |

This preparation step prevents a common migration gap: data arrives, but the store is not operationally ready. Cafe24 launch readiness depends on both migrated data and configured behavior.

### Prepare Apps, APIs, Webhooks, and External Systems <a href="#prepare-apps-apis-webhooks-and-external-systems" id="prepare-apps-apis-webhooks-and-external-systems"></a>

Cafe24 can support app development, API workflows, webhooks, Data Bridge, analytics, and developer-led integrations. That ecosystem is a strength, but it also means preparation must identify which workflows depend on something outside ordinary data migration.

Create a dependency inventory before migration. List apps, custom scripts, payment services, shipping services, analytics tools, ERP, POS, marketplace channels, accounting tools, fulfillment platforms, review systems, subscription systems, loyalty tools, and any external reports that depend on source-store identifiers. For each dependency, identify the data it reads, the event it expects, the identifier it uses, and the owner responsible for reconnecting it.

| Dependency type        | What to document                                                                           | Likely handling path                                                                    |
| ---------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- |
| API integrations       | Endpoints, identifiers, sync direction, data owner, and error handling.                    | Reconnect, remap identifiers, test after migration, or review through Custom Service.   |
| Webhooks and events    | Trigger events, payload expectations, connected systems, and retry behavior.               | Rebuild event flow and validate with representative orders, customers, or products.     |
| Analytics and tracking | Scripts, conversion events, product data layer, order data layer, and campaign parameters. | Reinstall and test after storefront and checkout configuration.                         |
| Apps and extensions    | Data owned by apps, custom fields, app-created records, and embedded storefront behavior.  | Use standard migration only if supported; otherwise consider Add-ons or Custom Service. |
| External reporting     | Data identifiers, order statuses, customer groups, product categories, and date ranges.    | Preserve or map identifiers where required for reporting continuity.                    |

External-system preparation should not wait until after Full Migration. If a workflow depends on source identifiers or custom fields, that dependency should influence migration approach before execution.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration should test representative difficulty, not easy records. For Cafe24, sample selection should include products with complex options, variant inventory, important categories, product images, customer records, member-group examples, normal orders, exceptional orders, coupon-related orders, refunded or returned orders, content-rich pages, priority URLs, and app-sensitive records.

| Sample type                   | Why it should be included                                                                         | What to review after Demo Migration                                                             |
| ----------------------------- | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Complex products              | They reveal option, variant, image, inventory, and custom-field behavior.                         | Product display, variant selection, SKU/inventory accuracy, and operational identifiers.        |
| Priority categories           | They reveal navigation, product membership, and SEO path issues.                                  | Category hierarchy, product placement, menu expectations, and redirect planning.                |
| Member records                | They reveal customer identity, account status, groups, addresses, and consent-related context.    | Customer matching, account interpretation, group mapping, and order association.                |
| Exceptional orders            | They reveal refunds, returns, cancellations, discounts, payment context, and fulfillment history. | Order readability, status interpretation, totals, customer association, and support usefulness. |
| Integration-sensitive records | They reveal external-system assumptions.                                                          | Identifier continuity, custom fields, API dependencies, and Custom Service needs.               |

If the Demo Migration sample avoids these records, it should not be used as evidence that the migration approach is ready for Full Migration.

### Prepare Launch-Window Change Handling <a href="#prepare-launch-window-change-handling" id="prepare-launch-window-change-handling"></a>

Preparation should include a plan for data changes made after Demo Migration or Full Migration. During a launch window, source-store activity may continue. New products, customers, orders, reviews, coupons, content changes, and inventory updates can appear after the main migration run.

Cafe24 planning should clarify whether the merchant needs to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration. The right action depends on the timing of source changes, the type of records involved, and whether the previous configuration still matches the expected result.

Entity Points planning should also be handled carefully. When newly created counted records are migrated successfully for the first time, they consume Entity Points. Entered entity counts are used for pricing and Entity Points Plan selection; they are not filters. If the merchant needs filtering, mapping, or configuration changes, those should be selected and configured as service requirements rather than assumed from entity-count entries.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Cafe24 migration preparation should produce usable evidence: clean catalog decisions, product option and variant classification, customer and member context, order-history expectations, configuration ownership, app and API dependency mapping, Demo Migration samples, and launch-window change planning. Without that evidence, even a technically successful migration can leave the target store unable to support storefront presentation, checkout readiness, repeat-customer recognition, historical order review, or connected-system continuity.

A prepared Cafe24 migration does not try to solve every issue during execution. It identifies which data can move through standard capability, which settings must be configured in Cafe24, which Add-ons may help with filtering or mapping, and which requirements need Custom Service review before launch pressure begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Cafe24 migration?**

Start with scope separation. Identify which parts of the source store are structured commerce data, which are Cafe24 configuration requirements, which are storefront or design work, and which depend on apps, APIs, webhooks, or external systems.

**Should product options and variants be reviewed before migration?**

Yes. Cafe24 product options, variants, and variant inventory can affect purchase behavior, stock control, fulfillment, and reporting. Review option names, values, combinations, SKUs, inventory, prices, display status, and any custom source logic before migration.

**Are payment, shipping, and tax settings included in data migration?**

They should be treated as target-store configuration, not as ordinary migrated data. Historical order records may preserve payment or shipping context, but live checkout, shipping, tax, and gateway behavior must be configured and tested in Cafe24.

**How should Demo Migration samples be selected for Cafe24?**

Use representative records that expose real complexity: products with variants, important categories, member groups, exceptional orders, coupon-related orders, refunds, returns, priority URLs, and integration-sensitive records.

**When should Custom Service be considered during preparation?**

Custom Service should be considered when the migration depends on custom fields, app-owned data, Custom Platform behavior, external identifiers, bespoke transformations, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment that standard capability cannot cover.
