# Wix Platform Overview

Wix is a hosted SaaS website and commerce platform. For merchants moving into Wix, the target environment usually combines a website builder, Wix Stores or Wix commerce, storefront templates, product pages, collections, customer-facing checkout, payment and shipping settings, apps, CMS content, marketing tools, SEO controls, and optional developer or API-based extensions.

A migration to Wix should be planned as more than a move into a new product catalog. Products, variants, options, modifiers, categories, customers, contacts, members, orders, Blog Posts, CMS Pages, app-related records, URL behavior, and external-system references need to make sense inside Wix’s hosted operating model. The quality of the final store depends on both migrated data and target setup.

The early planning question is whether the current store’s selling model can be represented cleanly in Wix. Straightforward catalogs, content-led stores, and businesses that want a managed website-and-commerce environment may fit well. Stores with custom checkout logic, deep source-code dependencies, unusual product configurators, specialized B2B pricing, app-owned data, or strict URL and theme parity need closer review before scope is finalized.

### What Changes in a Migration to Wix <a href="#what-changes-in-a-migration-to-wix" id="what-changes-in-a-migration-to-wix"></a>

Moving into Wix changes where commerce meaning is controlled. A self-hosted or heavily customized source store may keep product logic, checkout behavior, content templates, customer records, and SEO rules in database tables, plugins, themes, or custom code. Wix manages those areas through hosted platform structures, apps, editor settings, business tools, and APIs.

| Migration area                                    | What changes in Wix                                                                                                                                                        | Planning implication                                                                                                   |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Hosted website and commerce operation             | The target store runs inside Wix’s managed platform rather than a merchant-controlled server or database.                                                                  | Custom source behavior should be translated into supported Wix settings, apps, Velo/API work, or Custom Service scope. |
| Products and catalog structure                    | Wix products may use product types, options, choices, variants, modifiers, inventory, SKUs, media, collections, and storefront display settings.                           | Demo Migration samples should include complex products, not only simple records.                                       |
| Product options, choices, variants, and modifiers | Customer-selectable buying choices may become Wix options and variants, while some non-inventory choices may be better treated as modifiers or configuration expectations. | Variant-sensitive products should be checked for price, stock, SKU, media, weight, and storefront behavior.            |
| Collections, store pages, and discovery           | Product visibility depends on collections, category-style pages, galleries, filters, sorting, widgets, menus, and landing pages.                                           | A migrated catalog is not complete until shoppers can find products in the intended storefront paths.                  |
| Customers, contacts, members, and accounts        | Customer data may intersect with Wix Contacts, site members, customer accounts, marketing opt-ins, loyalty, reviews, and app-owned customer records.                       | Customer migration should separate commerce records from membership, consent, CRM, and app data.                       |
| Orders and checkout context                       | Historical orders may preserve purchased items, totals, customer details, payment labels, shipping context, discounts, fulfillment, refunds, and tracking where supported. | Readable order history does not prove that live checkout, payment, shipping, tax, or fulfillment is ready.             |
| Content and site structure                        | CMS Pages, Blog Posts, Wix CMS dynamic pages, menus, landing pages, images, and design sections depend on the target Wix site setup.                                       | Website migration should plan content and design continuity separately from commerce records.                          |
| Apps, Velo, APIs, and integrations                | Wix App Market apps, Velo custom functionality, commerce APIs, external payment or shipping services, and connected systems can own important behavior.                    | App-owned data and integration identifiers should be identified before migration scope is accepted.                    |
| SEO, URLs, and redirects                          | Product URLs, page slugs, metadata, canonical behavior, structured data, redirects, images, and domain choices affect search continuity.                                   | Priority URLs and SEO-sensitive pages should be reviewed before Full Migration and launch.                             |

### Where Wix Is Often a Strong Target <a href="#where-wix-is-often-a-strong-target" id="where-wix-is-often-a-strong-target"></a>

Wix is often a strong target for merchants that want a hosted website and store in one environment. It can support businesses that need product selling, site content, templates, storefront customization, payment and shipping setup, marketing tools, apps, and manageable day-to-day store operations without maintaining a self-hosted commerce stack.

#### Website-led businesses adding or rebuilding commerce <a href="#website-led-businesses-adding-or-rebuilding-commerce" id="website-led-businesses-adding-or-rebuilding-commerce"></a>

Wix can fit businesses where the website experience matters as much as the store. Product pages, landing pages, Blog Posts, menus, images, service pages, brand content, and mobile presentation can all be part of the target result. This makes Wix relevant for merchants that want commerce attached to a polished website rather than a purely catalog-driven storefront.

Planning should still define which content can migrate, which pages need manual rebuild, and which design expectations belong to Wix templates, editor work, apps, or custom development.

#### Stores with practical product and catalog needs <a href="#stores-with-practical-product-and-catalog-needs" id="stores-with-practical-product-and-catalog-needs"></a>

Wix can be a good target for physical and digital products, moderate option structures, product media, inventory, SKUs, collections, filters, coupons, gift cards, subscriptions where enabled, and store pages that are designed for shopper discovery. These stores often need careful product and collection samples, but they do not always require heavy custom migration logic.

The fit is stronger when product choices can be represented through Wix’s supported product structures. If products depend on complex configurators, custom pricing engines, or non-standard inventory relationships, the product model should be reviewed early.

#### Businesses using Wix’s app and business-tool ecosystem <a href="#businesses-using-wix-s-app-and-business-tool-ecosystem" id="businesses-using-wix-s-app-and-business-tool-ecosystem"></a>

Wix can support broader business needs through apps and native business solutions. Depending on the store, this may include booking, events, restaurants, pricing plans, forms, memberships, reviews, marketing, loyalty, CRM-style contacts, multichannel sales, and fulfillment or shipping services.

Migration planning should identify which business functions are part of the target Wix operation. Commerce records may migrate, while app-specific behavior, membership structures, reviews, loyalty data, booking records, restaurant data, or service-specific records may need separate planning or accepted exclusions.

#### Merchants that want less infrastructure responsibility <a href="#merchants-that-want-less-infrastructure-responsibility" id="merchants-that-want-less-infrastructure-responsibility"></a>

Wix is well suited to merchants that prefer a managed platform over hosting, patching, and maintaining a self-hosted system. This can simplify ongoing ownership, but it also changes how customization is handled. Custom source behavior does not move as raw code or direct database logic; it must be represented through Wix features, app choices, Velo/API development, or Custom Service when the migration requirement goes beyond standard service capability.

### Where Deeper Planning Is Usually Needed <a href="#where-deeper-planning-is-usually-needed" id="where-deeper-planning-is-usually-needed"></a>

Wix migration complexity usually appears when the source store depends on behavior that is not only product, customer, order, or page data. Deeper planning is especially important for product configuration, storefront design, customer-account meaning, app-owned records, external-system identifiers, checkout behavior, and SEO continuity.

#### Product options, variants, modifiers, and inventory <a href="#product-options-variants-modifiers-and-inventory" id="product-options-variants-modifiers-and-inventory"></a>

Products with multiple options, option choices, variant-level inventory, separate SKUs, barcode or GTIN values, cost, weight, preorder behavior, media by choice, or custom product inputs should be tested carefully. A product can appear in Wix while still failing to preserve the buying logic that matters to shoppers or store managers.

Strong samples should include the products that create operational questions, not only the cleanest items in the catalog.

#### Source design, templates, and custom code <a href="#source-design-templates-and-custom-code" id="source-design-templates-and-custom-code"></a>

Wix does not behave like a direct theme-code destination. Storefront design depends on the Wix site, template or editor setup, product page configuration, collection pages, galleries, widgets, mobile presentation, content sections, and apps. A source theme may inspire the target storefront, but it should not be treated as something that migrates automatically into the Wix editor.

Strict design parity, custom frontend behavior, unusual scripts, or deep source-code dependencies should be reviewed before timeline and service expectations are set.

#### Customers, members, contacts, subscriptions, and app-owned records <a href="#customers-members-contacts-subscriptions-and-app-owned-records" id="customers-members-contacts-subscriptions-and-app-owned-records"></a>

Customer data may carry more than billing or order history. A source store may have member accounts, customer groups, marketing preferences, newsletter subscriptions, loyalty points, reviews, saved payment references, wishlists, booking relationships, or app-specific customer fields.

These meanings should be separated before migration. Some data may fit commerce customer records, some may relate to Wix Contacts or Members, and some may require app-level handling or Custom Service review.

#### Checkout, payment, shipping, tax, and fulfillment setup <a href="#checkout-payment-shipping-tax-and-fulfillment-setup" id="checkout-payment-shipping-tax-and-fulfillment-setup"></a>

Historical order labels are not the same as live checkout configuration. Wix checkout, payment providers, shipping rules, pickup, delivery, tax settings, fulfillment services, refunds, tracking, and cart behavior require target setup and testing.

A migration can preserve useful order history while the new store still needs separate launch-readiness work for new transactions.

#### Apps, Velo, APIs, and connected systems <a href="#apps-velo-apis-and-connected-systems" id="apps-velo-apis-and-connected-systems"></a>

Wix sites can depend on apps, Velo custom functionality, commerce APIs, service plugins, external payment or shipping services, custom catalogs, ERP, PIM, WMS, CRM, accounting, fulfillment, or marketing platforms. These systems may use identifiers and workflows that are not visible in ordinary product and order tables.

If external systems must continue after launch, migration scope should identify which identifiers must be preserved, which workflows must be rebuilt, and which records should be excluded from the standard migration expectation.

#### SEO, URLs, domains, and search visibility <a href="#seo-urls-domains-and-search-visibility" id="seo-urls-domains-and-search-visibility"></a>

SEO-sensitive stores should not leave URL and metadata decisions until launch. Product slugs, collection paths, page URLs, redirects, canonical behavior, alt text, structured data, social sharing values, domain choices, and priority landing pages may affect traffic continuity.

The safest planning approach is to prepare high-value URL samples before Demo Migration and confirm how the target Wix site will handle redirects and page-level SEO values.

### What Should Be Understood Early Before Moving into Wix <a href="#what-should-be-understood-early-before-moving-into-wix" id="what-should-be-understood-early-before-moving-into-wix"></a>

Before choosing Wix as the Target Platform, merchants should separate four layers: migrated data, Wix target setup, storefront/content rebuild, and app or integration work. Treating all four as one migration task creates avoidable confusion during Demo Migration review and Full Migration acceptance.

The following points should be clear early:

* Wix is a hosted SaaS Target Platform, so custom source behavior should be translated into Wix-supported structures, apps, Velo/API work, or Custom Service scope.
* Wix Stores and Wix commerce is the main commerce layer, but the target result can also depend on Wix CMS, Blog Posts, Members, Contacts, apps, bookings, events, restaurants, pricing plans, or other business tools.
* Products with options, choices, variants, modifiers, media, inventory, SKUs, barcode or GTIN values, cost, weight, and preorder behavior should be sampled during Demo Migration.
* Collections, filters, galleries, product widgets, menus, category-style pages, and landing pages determine whether shoppers can actually find migrated products.
* Customer records should be reviewed separately from contacts, members, subscribers, marketing consent, loyalty, reviews, wishlists, saved payment references, and app-owned data.
* Historical orders should be checked for readability, while live checkout, payment, shipping, tax, fulfillment, refund, and tracking behavior should be tested as target setup.
* Apps, Velo, APIs, custom catalogs, service plugins, payment or shipping extensions, and external business-system identifiers may require separate migration planning.
* URL slugs, redirects, metadata, canonical behavior, structured data, domains, and priority content pages should be prepared before launch readiness is judged.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix can be a strong Target Platform for merchants that want a hosted website and commerce environment with practical store management, templates, apps, content tools, product selling, checkout, payment, shipping, SEO, and marketing capabilities. Migration planning works best when Wix is treated as a full site-and-commerce environment rather than a simple destination for product and order records.

Before starting the full migration path, review whether the current store’s key selling behavior can be represented cleanly in Wix. A focused Demo Migration should include complex products, customer/account examples, varied orders, important collections, high-value pages, SEO-sensitive URLs, and any app or integration records that could affect launch quality.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Wix a hosted or self-hosted Target Platform?**

Wix is a hosted SaaS website and commerce platform. Merchants do not manage the underlying server or database in the same way they would with a self-hosted platform, so migration planning should focus on Wix-supported structures, target configuration, apps, and integrations.

**Is Wix Stores the same as Wix commerce?**

Wix Stores is the main store layer used for selling products on Wix, while Wix commerce often refers to the broader commerce environment that can include checkout, payments, shipping, order management, apps, APIs, and related business tools. Migration planning should use the broader Wix environment when apps, members, CMS content, bookings, restaurants, events, or custom functionality affect the target result.

**Can product variants migrate cleanly to Wix?**

Many product option and variant structures can be planned for Wix, but complex products should be sampled before Full Migration. Variant-level price, inventory, SKU, barcode or GTIN, media, cost, weight, preorder behavior, and modifiers should be checked because these details affect both shopper experience and store management.

**Will the source store design migrate directly into Wix?**

A source design should not be treated as a direct theme-code migration into Wix. The target storefront depends on the Wix site, editor setup, templates, page design, store widgets, collection pages, mobile presentation, apps, and content work. Design continuity should be planned separately from data migration.

**What should be included in a Wix Demo Migration sample?**

A strong Wix Demo Migration sample should include simple and complex products, options, choices, variants, modifiers, inventory-sensitive items, collections, customer and member examples, varied orders, discounts, shipping and payment context, CMS Pages, Blog Posts, priority URLs, and app or integration records that affect daily operations.
