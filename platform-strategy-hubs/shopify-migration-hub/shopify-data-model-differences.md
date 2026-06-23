# Shopify Data Model Differences

Shopify migration planning should treat data as meaning, not only as records. Products, categories, customers, orders, CMS Pages, Blog Posts, URLs, custom fields, app-owned information, and storefront behavior may all exist in the Source Platform, but they do not always have the same structure or purpose in Shopify.

The central data-model question is whether each source meaning has a clear Shopify destination. Some data belongs in native Shopify fields. Some belongs in collections, product category, product type, tags, metafields, metaobjects, redirects, app configuration, theme behavior, or integration planning. Some data should be cleaned up instead of carried forward. The migration plan should make those distinctions before the store is treated as ready for Full Migration.

### Why Data Model Differences Matter <a href="#why-data-model-differences-matter" id="why-data-model-differences-matter"></a>

Shopify is a hosted SaaS Target Platform with platform-defined structures for catalog, storefront, customer, order, content, and configuration data. That model can make the target store easier to manage, but it also means the Source Platform should not be copied mechanically.

A Source Platform may use categories, database attributes, extensions, modules, custom fields, custom product types, multi-store logic, or theme-specific data to support business behavior. Shopify may represent the same business purpose through products, options, variants, collections, product category, product type, tags, metafields, metaobjects, apps, themes, Markets, URL redirects, or separate target-store setup.

The goal is not structural sameness. The goal is target-store usability. A good Shopify data model preserves the commercial and operational meaning that matters: customers can choose products correctly, browse the right groups, read the right content, access useful account and order context, follow important URLs, and rely on app-supported functions where those functions are part of the launch expectation.

| Source Platform meaning                | Possible Shopify destination                                                                       | Planning question                                                               |
| -------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Sellable product difference            | Product option, variant, SKU, price, inventory, media, or app-supported behavior                   | Is the difference a real buying choice or only descriptive information?         |
| Category or department                 | Collection, menu, filter, product category, product type, tag, page, or redirect                   | Does the structure support customer discovery or only legacy organization?      |
| Custom field                           | Native field, metafield, metaobject, app field, integration value, or Custom Service scope         | Who will use the value after launch and where should it appear or be processed? |
| Extension, module, or app data         | Shopify app setup, metafields, integration planning, manual configuration, or Custom Service scope | Is the data useful without the behavior that originally used it?                |
| International or multi-store structure | Markets, domains, languages, currencies, catalogs, redirects, or separate store planning           | Which regional differences must be visible and usable after launch?             |
| SEO-sensitive URL                      | Shopify handle, route, redirect, collection path, page path, Blog Post path, or cleanup decision   | Which source paths deserve priority redirect and destination review?            |

### Catalog and Product Structure Differences <a href="#catalog-and-product-structure-differences" id="catalog-and-product-structure-differences"></a>

Shopify catalog planning starts with the relationship between products, options, variants, product category, product type, tags, metafields, media, and inventory. Source stores often use more varied structures, especially when they come from self-hosted platforms, extension-heavy platforms, or custom catalogs.

A product should represent the item being sold. Options should represent customer-facing choice dimensions such as size, color, material, pack size, finish, or configuration. Variants should represent the purchasable combinations created from those options. That logic is clean when the source catalog already separates real buying choices from descriptive details. It becomes more sensitive when the Source Platform uses configurable products, grouped products, custom options, bundles, kits, personalization fields, product add-ons, or extension logic.

Product differences should be classified before migration:

* real customer-facing buying choices;
* SKU, inventory, price, barcode, fulfillment, or tax differences;
* product specifications or compatibility details;
* variant-specific images or media order;
* personalization inputs or custom option behavior;
* bundle, kit, subscription, or add-on logic;
* operational identifiers used by ERP, marketplace, fulfillment, analytics, or reporting systems;
* obsolete fields or extension residue that should not clutter Shopify.

Not every source-side option should become a Shopify variant. Some source values may be better handled as product content, metafields, metaobjects, tags, app configuration, theme display, integration data, or Custom Service scope. The practical test is whether the chosen Shopify structure preserves buying clarity and operational usefulness.

Shopify product category and product type also need separate treatment. Product category aligns a product with Shopify’s standard taxonomy and can affect attributes, sales channels, tax, discoverability, and product organization. Product type is a custom organizational field. Tags and metafields can support additional organization, filtering, or display, but they should not become a dumping ground for every source attribute.

### Category, Collection, Navigation, or Storefront Structure Differences <a href="#category-collection-navigation-or-storefront-structure-differences" id="category-collection-navigation-or-storefront-structure-differences"></a>

Source categories often carry several meanings at once. They may define hierarchy, navigation, landing pages, product filtering, merchandising groups, SEO paths, internal classification, campaign pages, or customer browsing habits. Shopify collections can preserve some of that meaning, but collections are not always a one-to-one replacement for source categories.

A source category may become:

| Source category role                 | Shopify treatment to consider                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Customer-facing product group        | Collection, menu item, filter group, or landing page                                                          |
| SEO landing page                     | Collection with content, page, redirect destination, or cleanup decision                                      |
| Internal classification              | Product type, tag, metafield, or no migrated customer-facing structure                                        |
| Filter or layered-navigation context | Search and discovery configuration, tags, metafields, product category attributes, or app-supported filtering |
| Campaign or seasonal grouping        | Manual collection, automated collection, page, menu placement, or archived redirect                           |
| Deep legacy taxonomy                 | Simplified collection model plus redirects for priority paths                                                 |

The collection plan should be judged by customer discovery, not by category-count preservation. Customers should still be able to find the intended products through collections, menus, search, filters, product recommendations, and priority landing pages. A smaller Shopify collection structure can be stronger than a copied legacy hierarchy when it supports clearer navigation and cleaner merchandising.

Theme behavior also matters. Collection layout, product cards, menu depth, filters, badges, recommendations, and custom displays may depend on the selected theme and app configuration. Migrating category or collection data does not automatically recreate the full storefront browsing experience.

### Customer, Account, and Order Data Differences <a href="#customer-account-and-order-data-differences" id="customer-account-and-order-data-differences"></a>

Customer and order migration should be evaluated by post-migration usefulness. A customer record can exist in Shopify while the account experience, password expectations, loyalty context, customer group logic, support scripts, or B2B-style behavior differs from the Source Platform.

Customer data should be separated into practical meanings:

* profile details and contact information;
* billing and shipping addresses;
* customer tags, notes, and segmentation signals;
* marketing status and communication expectations;
* order-history association;
* loyalty, rewards, memberships, wholesale status, or account-tier information;
* customer-specific identifiers used by external systems;
* password, login, or activation expectations.

Customer records and customer accounts are not the same planning area. The migration can preserve useful customer context, but returning-customer access may require communication, account activation, target-store configuration, app review, or support-process planning.

Order data should also be treated as operational context, not only as historical records. Useful order migration usually depends on line items, customer association, totals, tax, shipping, discounts, payment status, fulfillment state, order notes, source reference numbers, and customer-service context. Some source order behavior may come from payment systems, fulfillment tools, invoices, subscriptions, loyalty extensions, fraud tools, or external systems. Those behaviors should be separated from the order records themselves.

The practical target is a Shopify order history that supports customer service, operational reference, reporting review, and customer confidence where order history is visible. Exact source-system behavior should not be assumed unless it has a clear Shopify destination.

### Content, URL, and SEO Data Differences <a href="#content-url-and-seo-data-differences" id="content-url-and-seo-data-differences"></a>

Shopify content migration can involve CMS Pages, Blog Posts, product descriptions, collection descriptions, media, internal links, metadata, handles, menus, and redirects. The meaning of this content is broader than simple text transfer. Some content supports trust, policy compliance, shipping information, returns, sizing, SEO, campaigns, buying advice, customer education, or brand credibility.

Content should be reviewed by purpose:

| Content or URL area                    | Shopify data-model implication                                                                                  |
| -------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| CMS Pages                              | May require page migration, navigation placement, internal-link review, media review, and metadata decisions.   |
| Blog Posts                             | May require blog structure, article paths, media, metadata, author/date expectations, and internal-link review. |
| Product and collection descriptions    | Should support target-store selling logic and theme display, not only preserve old text.                        |
| Source category URLs                   | May need collection destinations, page destinations, redirects, or cleanup decisions.                           |
| Product URLs                           | Need handle review and redirect planning for priority paths.                                                    |
| Filtered, search, or query-string URLs | Need special review because they may not behave like ordinary product, collection, page, or Blog Post paths.    |
| International or localized URLs        | Need market, language, domain, subfolder, and redirect planning where regional selling matters.                 |

Shopify URL structure is controlled by its storefront model. Exact source paths may not be preserved, especially for products, collections, CMS Pages, Blog Posts, filtered routes, and custom paths. That makes redirect planning part of data-model translation, not only a final SEO task.

Priority URLs should be identified before launch-sensitive work. These usually include URLs with organic traffic, paid campaign value, backlinks, customer bookmarks, high-revenue products, important categories, policy pages, Blog Posts, and regional landing pages. The migration should confirm the intended Shopify destination for each priority path.

### App, Extension, Integration, or Custom Data Differences <a href="#app-extension-integration-or-custom-data-differences" id="app-extension-integration-or-custom-data-differences"></a>

Shopify stores often depend on apps, themes, and integrations. That is normal, but app-supported behavior should not be confused with ordinary migrated data. A Source Platform extension may store data that is meaningful only when a target Shopify app, theme, or integration can use it.

Common app or integration-sensitive areas include:

* product reviews and ratings;
* subscriptions, bundles, kits, product add-ons, or personalization logic;
* loyalty, rewards, memberships, and customer tiers;
* advanced search, filtering, recommendations, or merchandising rules;
* wholesale, B2B-style behavior, customer-specific pricing, or gated content;
* ERP, fulfillment, marketplace, PIM, CRM, analytics, accounting, or support identifiers;
* delivery rules, shipping logic, tax assumptions, invoices, and payment-related context;
* custom storefront displays controlled by theme code or app blocks.

For each dependency, the migration plan should identify the business outcome, the source data involved, the Shopify destination, and the target behavior needed after launch. Some data may be migrated into metafields or metaobjects. Some may need app import, manual configuration, integration work, Advanced Data Mapping, Advanced Data Configure, or Custom Service. Some may not be worth moving.

Metafields and metaobjects are useful when custom information has a target purpose. Metafields can extend Shopify resources such as products, customers, and orders. Metaobjects can model structured content with multiple fields and reusable entries. Neither automatically recreates source-side business logic. A value can be present in Shopify but still invisible, unused, or operationally meaningless until the theme, app, workflow, or integration uses it.

### How Data Model Differences Affect Migration Scope <a href="#how-data-model-differences-affect-migration-scope" id="how-data-model-differences-affect-migration-scope"></a>

Shopify data-model decisions should narrow the migration scope, not inflate it. The question is not how many source fields exist. The question is which source meanings must be preserved for the Shopify store to operate correctly.

A practical Shopify scope should separate:

| Scope category              | Shopify planning meaning                                                                                                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Standard migrated records   | Supported products, customers, orders, CMS Pages, Blog Posts, categories or collection-related records, and other ordinary data included in the selected migration path. |
| Target-store configuration  | Collections, menus, theme display, app setup, redirects, markets, filters, and storefront settings that may need configuration beyond record movement.                   |
| Add-on-sensitive work       | Supported filtering, mapping, or data-configuration needs that require controlled adjustment but remain within Add-on boundaries.                                        |
| Custom Service candidates   | Unsupported app data, custom fields with behavior, outside-system identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.   |
| Excluded or cleaned-up data | Obsolete fields, duplicate values, unused extension residue, abandoned URLs, or legacy structures that do not support the Shopify target model.                          |

This separation protects the migration from false completeness. A Shopify store can contain migrated records and still fail if collection meaning, custom fields, URL destinations, app-owned behavior, customer-account expectations, or integration identifiers are not interpreted correctly.

The strongest Article 3 output is a data translation map. It should show what each important source meaning becomes in Shopify, what needs configuration, what needs Add-ons, what needs Custom Service review, and what should be left behind. That map gives later preparation, service selection, validation, and pitfall-prevention work a stable foundation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify data-model differences matter because Shopify translates Source Platform meaning into a hosted platform model. Products, variants, collections, product category, product type, tags, metafields, metaobjects, customers, orders, CMS Pages, Blog Posts, apps, themes, Markets, redirects, and integrations each have a specific role in the Target Platform.

A reliable Shopify migration does not try to preserve every source structure exactly. It preserves the business meaning that should survive after launch. When catalog logic, collection meaning, customer and order context, content, URLs, custom fields, app-supported behavior, and integration identifiers are translated deliberately, the Shopify store is easier to operate and easier to validate.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are Shopify collections the same as source categories?**

No. Shopify collections can replace some source category roles, but source categories may also represent navigation, filters, landing pages, SEO value, internal grouping, or merchandising rules. Priority browse paths should be translated into a Shopify discovery model rather than copied one-to-one.

**Should every custom source field become a Shopify metafield?**

No. Metafields are useful when the field has a clear target purpose. Obsolete fields, duplicate fields, extension residue, or values with no storefront, operational, integration, or reporting purpose can make the target store harder to maintain and validate.

**Do Shopify apps migrate automatically from the Source Platform?**

No. Apps, extensions, modules, and theme behavior are not ordinary migrated records. The migration plan should identify which source behaviors need Shopify app configuration, target-store setup, Add-ons, or Custom Service.

**Can Shopify preserve the same customer account experience as the Source Platform?**

Customer records and customer-account experience should be planned separately. Migrated customers can retain useful profile and order-history context, but login behavior, activation, password expectations, loyalty context, and customer communication may require target-store planning.

**When should Shopify data differences be reviewed through Custom Service?**

Custom Service should be reviewed when source data requires customization or modification work, such as Custom Platform handling, app or extension data interpretation, custom field behavior, outside-system identifiers, bespoke transformation, or custom migration logic adjustment.
