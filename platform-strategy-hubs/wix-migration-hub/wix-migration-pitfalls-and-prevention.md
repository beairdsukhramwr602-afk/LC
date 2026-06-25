# Wix Migration Pitfalls and Prevention

Wix is a hosted site-builder commerce platform. A successful Wix migration is therefore not only a question of whether products, customers, and orders are transferred. The store must also work inside Wix’s managed site environment, Wix Stores, Wix eCommerce services, site design layer, apps, checkout settings, SEO controls, media handling, and integration model.

Many Wix migration issues appear when source-store data is treated like a generic cart export instead of being reviewed against Wix’s actual commerce and site behavior. Product options may not behave like source-platform variants. Historical order details may not recreate live checkout configuration. Customer records may not carry the same account or membership meaning. Page URLs, redirects, site navigation, product media, apps, and custom workflows may need separate review beyond a standard data transfer.

The safest approach is to identify these pitfalls before launch, validate them during Demo Migration, and decide which items can be handled through standard mapping, Add-ons, Custom Service review, target-store configuration, or accepted exclusions.

| Wix prevention area  | What to confirm before launch                                                                                                                                               |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Commerce records     | Products, options, variants, collections, customers, contacts, members, orders, discounts, taxes, shipping, payment labels, and fulfillment data behave as expected in Wix. |
| Site-builder context | CMS Pages, Blog Posts, media, menus, product pages, collection pages, redirects, domains, and SEO fields are validated as part of the full site experience.                 |
| App and custom logic | Wix apps, Velo/API logic, service plugins, custom catalogs, external payment/shipping services, and third-party integrations are separated from standard migrated data.     |
| Launch timing        | Demo Migration, validation, configuration, DNS/domain planning, and any Additional Migration Options are scheduled before the store depends on the new Wix site.            |

### Pitfall 1: Treating Wix Like a Generic Shopping Cart <a href="#pitfall-1-treating-wix-like-a-generic-shopping-cart" id="pitfall-1-treating-wix-like-a-generic-shopping-cart"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

A Wix migration can fail operationally when the project treats Wix only as a destination for products and orders. Wix combines hosted site-building, Wix Stores, eCommerce services, CMS content, site design, apps, contacts, members, SEO settings, and platform-managed checkout behavior. A migration that only checks visible catalog records may miss the site and business settings that make the Wix storefront usable.

This pitfall is common when the source platform is a self-hosted cart, open-source system, heavily customized WooCommerce store, or marketplace-connected catalog. The source may expose database-level fields, theme logic, custom checkout behavior, plugin tables, or app-owned records that do not have a direct Wix equivalent.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Warning sign                                             | Why it matters                                                                                                   |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Validation only counts products and orders               | Wix launch readiness also depends on site pages, navigation, checkout setup, media, redirects, and app behavior. |
| Custom source fields are assumed to appear automatically | Some values require mapping, Add-ons, Custom Service review, or target-side configuration.                       |
| Wix site design is not included in launch planning       | Migrated data can be present while the storefront, menus, mobile layout, or product pages are not ready.         |
| App or Velo logic is treated as migrated data            | Apps and code-driven behavior often need separate configuration or custom work.                                  |

#### Prevention <a href="#prevention" id="prevention"></a>

Separate Wix migration scope into data migration, site readiness, app readiness, and launch configuration. Confirm which records Next-Cart migrates, which values require Add-ons, which custom behavior requires Custom Service review, and which parts must be configured in Wix by the store owner or implementation team.

During Demo Migration, validate more than record counts. Open representative products, customer/contact records, orders, CMS Pages, Blog Posts, product pages, collection pages, redirects, and checkout-facing settings. Confirm that the migrated records behave inside Wix rather than only appearing in lists.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

A merchant moving from WooCommerce to Wix has products, orders, customers, blog content, coupons, SEO fields, and plugin-created product add-ons. The prevention plan separates standard commerce records from plugin-specific fields, site pages, media, redirects, and app behavior. Product options and order history are validated through Demo Migration, while product add-on logic is reviewed separately because it may not map directly to Wix Stores.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

The project has a clear Wix-specific scope map that separates migrated data, Add-ons, Custom Service review, target-store configuration, and accepted exclusions before Full Migration begins.

### Pitfall 2: Assuming Source Product Variants Match Wix Product Options <a href="#pitfall-2-assuming-source-product-variants-match-wix-product-options" id="pitfall-2-assuming-source-product-variants-match-wix-product-options"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Product data often looks correct at the product-title level but fails at the option, choice, variant, inventory, media, or pricing level. Source platforms may handle variants, attributes, modifiers, custom options, bundles, configurable products, grouped products, product add-ons, subscriptions, bookings, or digital products differently from Wix.

If those structures are not reviewed, the Wix catalog may show products but lose important selling behavior. Customers may see the wrong option choices, variant prices, stock values, SKUs, or images. Some custom option logic may need Add-ons, Custom Service review, or target-side app configuration.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Warning sign                                      | Why it matters                                                                                    |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Products are validated only by product count      | Count matching does not prove variants, options, inventory, media, and selling rules are correct. |
| Source modifiers are treated as ordinary variants | Modifiers or product add-ons may not behave like Wix product options.                             |
| SKU and stock checks skip variant-level records   | Variant-level inventory errors can affect fulfillment and sales reporting.                        |
| Bundles or custom product types are not sampled   | Complex products may need custom handling or target app decisions.                                |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Build product validation samples around product complexity, not just product volume. Include simple products, multi-option products, high-variant products, discounted products, out-of-stock products, digital products, products with many images, products with SEO fields, products assigned to multiple collections, and products using source-specific customization.

For each sample, compare source values with Wix output: title, description, SKU, price, sale price, stock, weight, product media, options, choices, variants, variant images, collection placement, SEO title, SEO description, and product URL. Any logic that Wix cannot represent through standard product fields should be categorized as Add-on need, Custom Service review, target app configuration, or accepted exclusion.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A Magento source store uses configurable products with size and color attributes, separate child SKUs, tier prices, and custom engraving options. Wix validation should not stop at parent products. The Demo Migration sample must include child SKU mapping, option display, price behavior, inventory behavior, image assignment, and whether engraving requires custom handling or a Wix app.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Representative Wix products show correct product data, option behavior, variant-level values, collection placement, media, SEO fields, and any non-standard product logic is documented with the correct handling path.

### Pitfall 3: Overlooking Collections, Site Navigation, and Product Discovery <a href="#pitfall-3-overlooking-collections-site-navigation-and-product-discovery" id="pitfall-3-overlooking-collections-site-navigation-and-product-discovery"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

A Wix catalog can appear complete while product discovery fails. Source categories, subcategories, filters, tags, brands, menu links, landing pages, and collection assignments may not translate exactly into Wix collections and site navigation. Customers may struggle to find products even though the product records exist.

This issue is especially important for stores that rely on category SEO, brand landing pages, merchandising pages, seasonal collections, menu-driven browsing, or product-filter journeys.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Warning sign                                            | Why it matters                                                                                         |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Collections are checked only by name                    | Product membership, hierarchy meaning, landing pages, menus, filters, and SEO may still be incomplete. |
| Source category URLs are not mapped                     | Search visibility and bookmarked customer paths may be affected after launch.                          |
| Brand or tag logic is assumed to become Wix collections | Source taxonomy behavior may need mapping decisions or target setup.                                   |
| Menu and collection page testing is skipped             | Customers may not reach migrated products through the storefront.                                      |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Validate product discovery as a customer journey. Check collection membership, collection pages, product filters, menu paths, landing pages, internal links, and SEO metadata. Identify which source taxonomies should become Wix collections, which should be preserved as product metadata, which require redirects, and which no longer have a useful Wix equivalent.

Use a redirect and navigation matrix for high-value categories, brands, seasonal pages, campaign landing pages, and collection pages. Do not rely only on the presence of product records.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A source store uses categories for main navigation, tags for product filters, and brand pages for SEO. The Wix preparation and validation plan should map primary categories to Wix collection behavior, test product membership, create or review high-value redirects, and confirm menus point to the intended pages.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Customers can find migrated products through Wix menus, collections, filters, internal links, and priority redirected URLs without relying only on search or manual product lookup.

### Pitfall 4: Confusing Historical Orders With Live Checkout Configuration <a href="#pitfall-4-confusing-historical-orders-with-live-checkout-configuration" id="pitfall-4-confusing-historical-orders-with-live-checkout-configuration"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

Historical orders and live checkout settings serve different purposes. Migrating order history into Wix does not recreate the source platform’s payment gateway setup, shipping rules, tax settings, checkout validation, custom fees, or fulfillment workflow. If those are assumed to transfer automatically, the new Wix store may preserve historical order records but still fail at live checkout.

This pitfall is common when the source store uses custom tax logic, shipping-rate plugins, payment gateway rules, manual fulfillment workflows, coupons, checkout fields, subscriptions, or third-party order management tools.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Warning sign                                                 | Why it matters                                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Historical orders are used as proof checkout is ready        | Orders prove past transaction data, not live checkout configuration.           |
| Payment and shipping labels are mistaken for active services | Labels in migrated orders do not configure payment gateways or shipping rates. |
| Taxes and discounts are validated only on old orders         | Future checkout calculations must be configured and tested in Wix.             |
| Custom fees or validation rules are not reviewed             | They may require service-plugin logic, apps, or Custom Service review.         |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Validate historical orders separately from live checkout. For historical orders, check order number/reference, customer linkage, products, line items, options, totals, taxes, discounts, shipping, payment labels, fulfillment status, refunds, notes, and metadata. For live checkout, test Wix’s configured payment, shipping, tax, discount, and fulfillment workflows independently.

If the source store used custom checkout logic, custom fees, external payment services, shipping-rate logic, or validation rules, review whether the behavior belongs in Wix configuration, a Wix app, a service plugin, or Custom Service scope.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

A source store has custom shipping fees based on product type and local delivery zones. Historical orders may migrate with the correct past shipping amounts, but the live Wix checkout still needs its own shipping-rate setup or custom service-plugin logic.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Historical order data validates correctly, and live Wix checkout has been separately configured and tested for payment, shipping, tax, discount, fulfillment, and any custom checkout behavior.

### Pitfall 5: Misreading Customers, Contacts, and Members <a href="#pitfall-5-misreading-customers-contacts-and-members" id="pitfall-5-misreading-customers-contacts-and-members"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Wix may represent customer-facing identity through customers, contacts, members, subscribers, forms, bookings participants, app-owned records, and CRM-style data. A source platform may instead store customers, WordPress users, newsletter subscribers, wholesale roles, memberships, loyalty records, or CRM contacts in different structures.

If these meanings are not separated, the migrated Wix store may show contact records but fail to preserve the intended customer/account relationship. Order history, addresses, marketing permissions, member access, wholesale segmentation, or app participation may need separate validation.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Warning sign                                                   | Why it matters                                                          |
| -------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Customer count is treated as account validation                | Records can exist without matching the source account meaning.          |
| Contacts, members, and customers are treated as identical      | Wix identity and CRM behavior can differ by feature and app.            |
| Guest customers are not sampled                                | Guest order history may behave differently from registered member data. |
| Membership or loyalty data is assumed to migrate automatically | App-owned records may require separate review or target setup.          |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Define which source records are customers, contacts, members, subscribers, loyalty users, wholesale buyers, booking participants, or app-specific users. Validate sample records across registered customers, guest customers, repeat buyers, customers with multiple addresses, members with access rules, and customers connected to orders.

Document what Next-Cart migrates, what Wix configuration controls, what Add-ons can support, what requires Custom Service review, and what remains an accepted exclusion.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

A source store has customers, newsletter subscribers, wholesale users, and loyalty members. The Wix migration scope should not treat all records as the same. Standard customer data, contact details, order links, marketing/subscriber meaning, and app-specific loyalty behavior each need a separate validation path.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Migrated Wix customer, contact, member, and order-history relationships match the agreed scope, and app-specific identity or access behavior is either implemented, reviewed separately, or documented as excluded.

### Pitfall 6: Forgetting Wix Site Content, Media, and SEO Continuity <a href="#pitfall-6-forgetting-wix-site-content-media-and-seo-continuity" id="pitfall-6-forgetting-wix-site-content-media-and-seo-continuity"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

A Wix migration can preserve products while weakening the store’s site experience. CMS Pages, Blog Posts, product media, collection pages, landing pages, internal links, menus, page titles, meta descriptions, image alt text, redirects, canonical paths, domains, and mobile layout may not carry over as expected unless they are included in scope and validation.

This pitfall is especially serious for businesses that depend on organic search, long-form buying guides, blog-driven traffic, campaign landing pages, or content-commerce relationships.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Warning sign                                    | Why it matters                                                                                              |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| SEO is discussed only at product level          | Category pages, CMS Pages, Blog Posts, redirects, image metadata, and internal links may still be affected. |
| Media files are assumed to equal page readiness | Image availability does not prove layout, placement, alt text, or content relationships are preserved.      |
| Domain changes are left until launch day        | Redirects, canonical paths, analytics, and DNS timing can affect launch stability.                          |
| Blog and page content are not sampled           | Content loss may be discovered after organic traffic drops.                                                 |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Create a content and SEO validation list before launch. Include priority CMS Pages, Blog Posts, product pages, collection pages, landing pages, menus, media-heavy pages, high-traffic URLs, high-value redirects, SEO titles, meta descriptions, alt text, canonical expectations, and internal links.

Separate migrated content from Wix site-design work. Next-Cart can migrate supported content entities according to scope, but layout rebuilding, design recreation, mobile polishing, menu strategy, and on-page conversion design may require target-side work or separate Custom Service review.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A merchant moving from Shopify to Wix has high-ranking collection pages, blog articles, and buyer guides. The prevention plan should include priority URL mapping, product and collection page validation, Blog Posts validation, internal link review, redirect planning, and mobile layout checks before launch.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Priority products, pages, blog content, media, menus, redirects, metadata, and internal links are validated in Wix, and any design or layout work outside migration scope is assigned before launch.

### Pitfall 7: Assuming Apps, Velo Logic, and Service Plugins Are Standard Data <a href="#pitfall-7-assuming-apps-velo-logic-and-service-plugins-are-standard-data" id="pitfall-7-assuming-apps-velo-logic-and-service-plugins-are-standard-data"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Wix can be extended with apps, Velo/API logic, custom catalogs, checkout/cart validation, custom fees, shipping-rate integrations, external payment services, and other service-plugin behavior. These elements are not the same as standard catalog or order records. Source stores may also rely on plugin or app behavior that does not have a direct Wix equivalent.

If custom behavior is treated as ordinary data, the migrated site may pass basic record-count checks but fail real business workflows.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Warning sign                                     | Why it matters                                                                                    |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| App data is not separated from core store data   | App-owned records may need export, mapping, custom work, or exclusion.                            |
| Custom checkout rules are assumed to transfer    | Wix checkout behavior may require configuration, apps, service plugins, or Custom Service review. |
| External systems are validated only after launch | ERP, CRM, PIM, WMS, shipping, accounting, and payment integrations can affect operations.         |
| Velo/API logic is not documented                 | Code-driven behavior may need rebuilding, not migration.                                          |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Inventory all source and target extensions before migration. Identify which functions are standard Wix configuration, which are Wix apps, which use Velo/API logic, which require service plugins, and which depend on external systems. For each item, decide whether the expected result is data migration, target configuration, Add-on support, Custom Service review, third-party setup, or exclusion.

Validate custom workflows with real scenarios: adding products to cart, applying discounts, calculating tax and shipping, selecting payment methods, completing checkout, fulfilling orders, syncing external systems, and displaying app-specific customer or product data.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A source store uses a custom product configurator and an ERP integration. Wix products can be migrated, but configurator behavior and ERP synchronization need separate validation. They may require Wix app selection, Velo/API work, Custom Service review, or external implementation.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

All app, Velo/API, service-plugin, custom-catalog, and integration dependencies are identified, assigned to the correct handling path, and validated separately from core migrated records.

### Pitfall 8: Using a Weak Demo Migration Sample <a href="#pitfall-8-using-a-weak-demo-migration-sample" id="pitfall-8-using-a-weak-demo-migration-sample"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

A Demo Migration sample can give false confidence if it contains only simple records. Wix migration risks often appear in edge cases: complex products, multiple options, collections, media-heavy products, guest orders, discounts, refunds, custom fields, app-owned records, CMS Pages, Blog Posts, high-value URLs, and integration references.

A weak sample may pass while the full store still contains unresolved migration issues.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Warning sign                                                             | Why it matters                                                                  |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------------- |
| Sample records are selected randomly                                     | Random samples may miss high-risk structures.                                   |
| Only simple products are checked                                         | Variant, option, media, inventory, and custom product behavior remain untested. |
| Orders are checked without taxes, discounts, refunds, or guest customers | Important order-history cases may fail later.                                   |
| Content and URL samples are omitted                                      | SEO and site-continuity issues may remain hidden.                               |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Build a representative Wix Demo Migration sample. Include simple and complex products, variant-heavy products, products with many images, discounted products, products assigned to collections, customers with multiple addresses, guest orders, refunded orders, orders with discounts/taxes/shipping/payment labels, CMS Pages, Blog Posts, and high-priority URLs.

Treat Demo Migration as a decision checkpoint. Use it to confirm standard mapping, identify Add-ons, escalate custom cases, define accepted exclusions, and adjust launch timing before Full Migration.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant has 30,000 products but selects only five simple products for Demo Migration. A better sample includes best sellers, multi-option products, discontinued products, media-heavy products, SEO-sensitive products, refunded orders, guest orders, CMS Pages, Blog Posts, and app-owned records.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

The Demo Migration sample includes the highest-risk Wix migration structures and produces clear decisions for standard scope, Add-ons, Custom Service review, target configuration, and exclusions.

### Pitfall 9: Misusing Add-ons, Custom Service, and Entity Points <a href="#pitfall-9-misusing-add-ons-custom-service-and-entity-points" id="pitfall-9-misusing-add-ons-custom-service-and-entity-points"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

Migration planning can become unclear when Add-ons, Custom Service, and Entity Points are treated as interchangeable. Add-ons extend specific migration capabilities. Custom Service supports requirements that need separate review, custom handling, or non-standard scope. Entity Points determine how eligible records are counted under the service license and follow-up migration activity.

If these boundaries are unclear, a merchant may expect Add-ons to rebuild custom Wix functionality, assume Custom Service covers every target-store task, or misunderstand how new eligible records affect Entity Points.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

| Warning sign                                                       | Why it matters                                                                                                |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Add-ons are expected to replace custom development                 | Add-ons address defined migration needs; they do not automatically rebuild site functionality.                |
| Custom Service is treated as full storefront build coverage        | Custom Service must be scoped and agreed; it is not a blanket promise for all Wix setup work.                 |
| Entity Points are only checked at the beginning                    | New eligible records can affect scope when migrated for the first time.                                       |
| Records already counted are assumed to consume Entity Points again | Previously counted records do not consume Entity Points again simply because another migration action occurs. |

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Define each scope mechanism clearly before Full Migration. Use Add-ons for specific supported migration needs. Use Custom Service review when source logic, custom fields, apps, service plugins, integrations, or non-standard relationships require separate evaluation. Use Entity Points to plan eligible record volume accurately.

For follow-up migration activity, confirm whether records are new or already counted. Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because another migration action is performed for the same migration path.

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

A merchant adds new Wix-bound orders after Demo Migration and also asks whether a custom booking workflow can be recreated. New eligible orders may consume Entity Points when migrated for the first time, while booking-workflow behavior may need Custom Service review or target app configuration. These are separate decisions.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

The project clearly separates Add-ons, Custom Service review, accepted exclusions, and Entity Points impact before launch and before any follow-up migration activity.

### Pitfall 10: Treating Additional Migration Options as a Shortcut Around Revalidation <a href="#pitfall-10-treating-additional-migration-options-as-a-shortcut-around-revalidation" id="pitfall-10-treating-additional-migration-options-as-a-shortcut-around-revalidation"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

Additional Migration Options can help handle later migration activity, but they do not remove the need to revalidate Wix output. New or changed products, customers, orders, Blog Posts, URLs, discounts, app records, or integration references can create new Wix-specific issues after the original Demo Migration or Full Migration.

If later migration activity is treated as a simple repeat action, the store may launch with new data that was never checked in Wix.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

| Warning sign                                                                          | Why it matters                                             |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Later migration activity is not assigned a validation window                          | New records may reach Wix without review before launch.    |
| New products are not checked for options, media, collections, or SEO                  | New catalog records can create fresh storefront issues.    |
| New orders are not checked for totals, taxes, shipping, discounts, and customer links | New order data may not match expected operational records. |
| New Blog Posts or URLs are not reviewed                                               | Content and SEO continuity may still be affected.          |

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Plan follow-up migration activity as a controlled validation step. Identify which records are new, which have already been counted, and which Wix areas must be rechecked. Validate representative new records in the same way as Demo Migration samples: products, options, collections, media, customers, contacts, members, orders, discounts, taxes, shipping, payment labels, CMS Pages, Blog Posts, redirects, SEO, and integrations.

Additional Migration Options should be used as part of launch control, not as a substitute for acceptance testing.

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

A merchant keeps selling on the source store while the Wix site is being finalized. Before launch, the team reviews new products, new customers, new orders, new Blog Posts, and high-value URL changes. New eligible records are checked for Entity Points impact, and the migrated results are validated in Wix before DNS/domain changes.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Additional Migration Options are paired with a clear Wix revalidation checklist, Entity Points review for new eligible records, and acceptance testing before the store relies on the updated Wix data.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix migration pitfalls usually come from treating Wix as a simple destination database instead of a hosted site-builder commerce environment. Prevention requires validating commerce records, site content, URLs, apps, custom logic, checkout behavior, customer meaning, Entity Points, Add-ons, Custom Service boundaries, and follow-up migration activity as part of one launch-readiness process.

A strong Wix migration plan uses Demo Migration to expose risk early, assigns each issue to the correct handling path, and validates the full customer journey before the new Wix site becomes the active storefront.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Wix migrations need more than product and order checks?**

Wix combines commerce records with site pages, media, menus, apps, checkout settings, SEO, redirects, domains, and managed storefront behavior. Product and order counts alone do not prove the Wix store is ready for launch.

**What is the most common Wix migration pitfall?**

The most common pitfall is assuming source-store structures behave the same way in Wix. Product options, checkout rules, customer/member relationships, app records, URLs, and custom logic often need separate validation.

**Can Add-ons prevent all Wix migration issues?**

No. Add-ons support specific migration needs, but they are not a substitute for Custom Service, target-store configuration, app setup, design work, or custom development.

**When should Custom Service be considered for Wix migration?**

Custom Service should be reviewed when source behavior depends on custom fields, app-owned records, Velo/API logic, custom catalogs, service plugins, unusual product relationships, external systems, or business rules that standard migration scope does not cover.

**Do Additional Migration Options remove the need for Wix revalidation?**

No. Additional Migration Options should be paired with renewed validation, especially when new products, customers, orders, Blog Posts, URLs, app records, or integration references are introduced before launch.
