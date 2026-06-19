# Shopify Data Model Differences

A Shopify migration is not only a transfer of products, customers, orders, and content into a new store. It is a translation of source-store meaning into Shopify’s hosted data model. The target result should prove that customers can still choose products, browse collections, understand content, manage account expectations, and interact with the storefront in a way that supports the intended business outcome.

Shopify is structured around products, options, variants, collections, customers, orders, pages, Blog Posts, metafields, files, redirects, Markets, apps, themes, and storefront configuration. Many source platforms represent those same business needs through categories, product types, option systems, extensions, modules, custom fields, database tables, multi-store structures, or outside systems. The migration plan should identify where each source meaning belongs in Shopify, not simply whether a record can be moved.

### What Changes When Data Moves Into Shopify <a href="#what-changes-when-data-moves-into-shopify" id="what-changes-when-data-moves-into-shopify"></a>

Shopify separates migrated records from target-store behavior. A product record can migrate, but option logic, variant behavior, collection placement, search filters, app-supported functions, theme display, and market-specific presentation may still require target-store decisions.

| Source-store meaning                   | Common Shopify representation                                                                        | Planning implication                                                                                    |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Product record                         | Product, options, variants, media, product category, product type, tags, metafields                  | Confirm which differences are true buying choices and which are descriptive or operational details.     |
| Category or department                 | Collection, menu, filter, product type, tag, metafield, redirect, or page                            | Do not assume source categories should become Shopify collections one-to-one.                           |
| Custom field                           | Native field, metafield, metaobject, app field, or Custom Service item                               | Preserve the field only when it has a clear storefront, operational, integration, or reporting purpose. |
| Extension or module data               | Shopify app configuration, metafields, target-store setup, integration work, or Custom Service item  | App-owned behavior should not be treated as ordinary migrated data.                                     |
| Multi-store or international structure | Markets, domains, languages, currencies, catalogs, redirects, or separate store planning             | Confirm localized selling expectations before launch-sensitive migration work.                          |
| Customer account behavior              | Customer records, addresses, order history, tags, communication plan, or app-supported account logic | Preserved customer records do not guarantee identical login or account behavior.                        |
| Historical order context               | Orders, line items, totals, taxes, shipping, discounts, statuses, customer association, notes        | Validate order usefulness for customer service and operations, not only record count.                   |
| SEO-sensitive paths                    | Shopify handles, URL patterns, redirects, collection/page/blog routes, or cleanup decisions          | Priority URLs need target-path and redirect planning before launch.                                     |

A strong Shopify data model plan separates what should be migrated, what should be configured, what should be recreated with apps or theme behavior, and what requires Custom Service review.

### Product Structure <a href="#product-structure" id="product-structure"></a>

Shopify product structure is built around products, options, and variants. This is straightforward when the source catalog already has clean purchasable choices, such as size, color, material, quantity, or package format. It becomes more sensitive when the source store used product options, configurable products, custom options, grouped products, bundles, kits, personalization fields, or extension logic to represent different meanings.

#### Products, options, and variants <a href="#products-options-and-variants" id="products-options-and-variants"></a>

A product should represent the item being sold. Options should represent the customer-facing dimensions of choice. Variants should represent the actual purchasable combinations created from those options.

Before migration, source product differences should be classified by meaning:

* sellable variation;
* descriptive information;
* inventory or SKU difference;
* price difference;
* image or media difference;
* fulfillment difference;
* personalization input;
* bundle, kit, or add-on behavior;
* internal operational note;
* app, extension, or custom-logic dependency.

Not every source-side option should become a Shopify variant. Some information may belong in product content, metafields, tags, apps, theme configuration, or Custom Service scope. The safest target model preserves buying clarity rather than mechanically copying every source product structure.

#### Product identifiers and operational meaning <a href="#product-identifiers-and-operational-meaning" id="product-identifiers-and-operational-meaning"></a>

SKUs, handles, vendor values, product types, tags, barcodes, and other identifiers can affect merchandising, fulfillment, reporting, search, filtering, integrations, and operational review. These fields should be handled as operational signals, not only product details.

If source identifiers connect to ERP, fulfillment, marketplace, CRM, analytics, product information management, or reporting systems, those relationships should be documented before migration. Outside-system identifiers may require Custom Service when they must be transformed, preserved in a specific structure, or interpreted by target-side processes.

#### Product media and presentation <a href="#product-media-and-presentation" id="product-media-and-presentation"></a>

Images and media affect customer confidence and product selection. Shopify can store product media, but display behavior depends on product setup, variant association, theme behavior, and target-store configuration.

Validation samples should include products where media order, variant-specific imagery, alt text, image count, or product-page layout affects commercial meaning. A technically migrated product is not enough if customers cannot see the right image for the selected option.

### Collections and Storefront Discovery <a href="#collections-and-storefront-discovery" id="collections-and-storefront-discovery"></a>

Shopify uses collections and navigation to support product discovery. Source platforms often use categories to carry several meanings at once: hierarchy, navigation, landing-page content, filtering context, merchandising rules, SEO value, and internal classification.

#### Collections are not always categories <a href="#collections-are-not-always-categories" id="collections-are-not-always-categories"></a>

Some source categories should become Shopify collections. Others may be better represented as menus, filters, product types, tags, metafields, search behavior, campaign pages, redirects, or cleanup decisions.

A collection should be validated by customer outcome:

* customers can find the intended products;
* high-value landing pages still make sense;
* merchandising groups remain useful;
* collection content and SEO fields support launch goals;
* menus and filters support browse behavior;
* source category URLs are redirected when needed.

The best Shopify collection model is usually the one that supports target-store discovery, not the one that reproduces the deepest source taxonomy.

#### Navigation and filtering are target-store decisions <a href="#navigation-and-filtering-are-target-store-decisions" id="navigation-and-filtering-are-target-store-decisions"></a>

Navigation menus, filters, search behavior, collection templates, and theme settings help determine how customers browse the target store. These elements may depend on Shopify configuration, theme capabilities, apps, product tags, metafields, or product attributes.

If the source store used category-specific filters, layered navigation, product comparison, advanced search, or custom merchandising rules, those behaviors should be reviewed separately from category record migration. Data can migrate while the browse experience still needs configuration or Custom Service.

### Custom Information, Metafields, and Metaobjects <a href="#custom-information-metafields-and-metaobjects" id="custom-information-metafields-and-metaobjects"></a>

Shopify metafields can preserve structured information that does not fit a standard Shopify field. They are useful for product specifications, compatibility details, customer-service context, operational notes, compliance fields, integration values, or display-ready custom information.

#### Metafields preserve information, not automatic behavior <a href="#metafields-preserve-information-not-automatic-behavior" id="metafields-preserve-information-not-automatic-behavior"></a>

A migrated metafield can keep a value available in Shopify, but it does not automatically recreate source-side behavior. A field that previously controlled storefront display, pricing, eligibility, filtering, personalization, fulfillment, or integration logic may need app configuration, theme work, target-store setup, or Custom Service planning before it behaves as expected.

Metafield planning should answer four questions:

1. Why should this value exist in Shopify?
2. Who will use it after launch?
3. Where should it appear or be processed?
4. Does it require configuration, app behavior, theme behavior, or custom logic?

Fields with no target purpose can make validation harder and the Shopify admin less maintainable.

#### Metaobjects and structured content <a href="#metaobjects-and-structured-content" id="metaobjects-and-structured-content"></a>

Some structured information may be better handled through metaobjects or app-supported content structures rather than simple field movement. This is especially relevant when source data represents reusable specifications, compatibility lists, brand information, size guides, landing-page components, or structured content blocks.

Metaobject planning should remain practical. The goal is not to preserve source technical structure exactly. The goal is to make target-store information usable, governable, and visible where it supports the customer journey or store operations.

### Customers, Accounts, and Order History <a href="#customers-accounts-and-order-history" id="customers-accounts-and-order-history"></a>

Customer and order migration should be evaluated by business usability. A record can be present in Shopify but still fail to support customer service, account expectations, reporting, or operational reference.

#### Customer records and account access are separate concerns <a href="#customer-records-and-account-access-are-separate-concerns" id="customer-records-and-account-access-are-separate-concerns"></a>

Customer profiles, addresses, tags, notes, marketing status, and order relationships may migrate as data. Account access, login behavior, password expectations, activation flow, loyalty context, and customer communication require separate planning.

The target-store question is not only whether the customer exists. It is whether staff can support the customer, whether order history remains understandable, and whether returning customers know how to use the new store after launch.

#### Historical orders need context <a href="#historical-orders-need-context" id="historical-orders-need-context"></a>

Historical orders should be reviewed for reference usefulness. Important fields often include order number or reference, customer association, products, line items, totals, taxes, shipping, discounts, payment status, fulfillment state, notes, and source-specific context.

Some source order behavior may not transfer as live transactional logic. Old payment methods, fulfillment integrations, fraud tools, subscription behavior, loyalty points, refund workflows, or invoice logic may depend on source extensions or external systems. Those dependencies should be separated from ordinary order record migration.

### Content, Blog Posts, URLs, and Redirects <a href="#content-blog-posts-urls-and-redirects" id="content-blog-posts-urls-and-redirects"></a>

Shopify content migration can involve pages, Blog Posts, product descriptions, collection content, media, metadata, handles, and redirects. The planning focus should be continuity of customer access and search value, not only content presence.

#### Pages and Blog Posts <a href="#pages-and-blog-posts" id="pages-and-blog-posts"></a>

CMS Pages and Blog Posts should be reviewed for business purpose. Some pages support trust, policy, shipping, returns, sizing, buying advice, SEO, campaigns, or customer education. Some source pages may be obsolete and should not be carried forward unchanged.

Content review should include internal links, images, formatting, metadata, priority URLs, and whether the page still makes sense in the Shopify theme and navigation model.

#### URL structure and redirects <a href="#url-structure-and-redirects" id="url-structure-and-redirects"></a>

Shopify uses controlled storefront URL patterns and handles. Source URLs may not be preserved exactly, especially for categories, products, pages, Blog Posts, and filtered paths. Redirect planning is therefore part of data-model translation, not only launch cleanup.

Priority URLs should be identified before Full Migration. Validation should confirm target paths, redirects, internal links, menu links, collection links, blog paths, product handles, and high-value campaign or SEO routes.

### Markets, Localization, and Regional Selling <a href="#markets-localization-and-regional-selling" id="markets-localization-and-regional-selling"></a>

International selling can involve markets, domains, languages, currencies, regional catalogs, localized content, shipping rules, tax assumptions, redirects, and customer expectations. A source platform may have represented these through separate stores, language packs, subdirectories, customer groups, extensions, or custom routing.

Shopify can support international selling through its own structures, but those structures should be planned in Shopify terms. The target model should clarify which regions matter, which localized content must be reviewed, whether product availability differs by market, and how priority URLs should behave for each launch region.

International scope often changes validation priorities. Product availability, pricing display, currency behavior, domain routing, translated content, shipping assumptions, and region-specific redirects should not be left to general product validation.

### Apps, Themes, and External Systems <a href="#apps-themes-and-external-systems" id="apps-themes-and-external-systems"></a>

Many Shopify behaviors depend on apps, theme configuration, or external systems. That dependency is normal for Shopify, but it must be separated from migrated data.

#### App-owned behavior is not ordinary migrated data <a href="#app-owned-behavior-is-not-ordinary-migrated-data" id="app-owned-behavior-is-not-ordinary-migrated-data"></a>

Apps may support reviews, subscriptions, loyalty, search, filters, personalization, bundles, wholesale workflows, marketing, analytics, fulfillment, delivery rules, product recommendations, customer service, or integrations. A source-side extension may have stored data that is not useful unless a Shopify-side app or workflow can interpret it.

When app-dependent data matters after launch, planning should identify:

* the source behavior;
* the target Shopify app or configuration;
* the data required for the target behavior;
* whether the data can be mapped normally;
* whether Advanced Data Mapping, Advanced Data Configure, or Custom Service is needed;
* how the behavior will be validated before launch.

#### Themes affect presentation, not just appearance <a href="#themes-affect-presentation-not-just-appearance" id="themes-affect-presentation-not-just-appearance"></a>

Shopify themes shape how data appears and how customers interact with product pages, collections, menus, filters, content blocks, metafields, and apps. A migrated value may exist in the admin but remain invisible until the theme or app configuration uses it.

Theme-dependent requirements should be captured early when they affect buying decisions, content visibility, custom fields, product recommendations, badges, compatibility tables, size guides, or other customer-facing signals.

### When Shopify Data Translation Needs Add-ons or Custom Service <a href="#when-shopify-data-translation-needs-add-ons-or-custom-service" id="when-shopify-data-translation-needs-add-ons-or-custom-service"></a>

Some Shopify migrations can stay close to standard data movement. Others need Add-ons or Custom Service because source data must be filtered, mapped differently, configured beyond default behavior, or transformed into a Shopify-ready model.

#### Add-on signals <a href="#add-on-signals" id="add-on-signals"></a>

Add-ons may be relevant when the migration needs controlled filtering, adjusted field relationships, or data configuration beyond a straightforward standard setup. Typical Shopify signals include selective record scope, field-level mapping needs, product/collection adjustments, URL-related preparation, or target data configuration that remains within supported service capability.

Add-ons should support a defined target outcome. They should not be used as a vague substitute for deciding how Shopify should represent the source store.

#### Custom Service signals <a href="#custom-service-signals" id="custom-service-signals"></a>

Custom Service should be considered when the migration requires customization or modification work beyond Standard Service and Standard Add-ons. Shopify data-model contexts that often require Custom Service include:

* Custom Platform handling;
* app, plugin, module, or extension data that must be interpreted or transformed;
* source-side product logic that cannot be represented cleanly through standard Shopify products, options, variants, collections, metafields, or configuration;
* custom fields with behavior attached;
* outside-system identifiers that must remain meaningful for ERP, CRM, fulfillment, marketplace, analytics, or reporting workflows;
* bespoke transformation rules;
* custom migration logic adjustment.

Custom Service does not automatically mean Next-Cart performs migration execution. Migration management is included only when it is part of the final plan.

### Demo Migration Samples for Shopify Data Differences <a href="#demo-migration-samples-for-shopify-data-differences" id="demo-migration-samples-for-shopify-data-differences"></a>

A Shopify Demo Migration should include records that expose real target-model decisions. Simple products and ordinary orders can confirm basic transfer behavior, but they do not prove that Shopify can represent the source store’s important meanings.

Strong Shopify samples usually include:

* products with multiple options and variant-specific prices, SKUs, images, or stock behavior;
* products with custom fields, specifications, compatibility data, or metafield candidates;
* source categories that carry navigation, SEO, or merchandising value;
* customers with addresses, tags, order history, or support relevance;
* orders with discounts, taxes, shipping, fulfillment, payment, and source reference context;
* CMS Pages or Blog Posts with internal links, media, metadata, and priority URLs;
* app-dependent records or extension-owned information when relevant;
* market-specific products, localized content, or domain-sensitive paths;
* URLs that matter for SEO, paid campaigns, or customer bookmarks.

The Demo Migration should help the business decide whether Shopify’s native structures are enough, whether Add-ons are needed, or whether Custom Service should be planned before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify data-model differences matter because Shopify does not copy every source-store structure in the same shape. It translates the store into a hosted model built around products, options, variants, collections, customers, orders, content, metafields, apps, Markets, redirects, and target-store configuration.

The strongest Shopify migration plans identify which source meanings should become standard Shopify data, which should become metafields or structured content, which depend on apps or themes, which require redirects or market planning, and which need Add-ons or Custom Service. When those decisions are made early, Shopify can become easier to operate after launch. When they are ignored, the target store may look clean while losing important commercial or operational meaning.

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Are Shopify collections the same as source categories?**

No. Shopify collections can replace some source category roles, but source categories may also represent navigation, filters, landing pages, SEO value, internal grouping, or merchandising rules. Priority browse paths should be translated into a Shopify discovery model rather than copied one-to-one.

**Should every custom source field become a Shopify metafield?**

No. Metafields are useful when the field has a clear target purpose. Obsolete fields, duplicate fields, extension residue, or values with no storefront, operational, integration, or reporting purpose can make the target store harder to maintain and validate.

**Do Shopify apps migrate automatically from the source store?**

No. Apps, extensions, modules, and theme behavior are not ordinary migrated records. The migration plan should identify which source behaviors need Shopify app configuration, target-store setup, Add-ons, or Custom Service.

**Can Shopify preserve the same customer account experience as the source store?**

Customer records and account experience should be planned separately. Migrated customers can retain useful profile and order-history context, but login behavior, activation, password expectations, loyalty context, and customer communication may require target-store planning.

**When should Shopify data differences be reviewed through Custom Service?**

Custom Service should be reviewed when source data requires customization or modification work, such as Custom Platform handling, app or extension data interpretation, custom field behavior, outside-system identifiers, bespoke transformation, or custom migration logic adjustment.
