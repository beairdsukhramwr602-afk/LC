# BigCommerce Platform Overview

BigCommerce is best understood as a hosted SaaS commerce Target Platform with substantial structure behind the storefront. It can reduce infrastructure ownership compared with open-source or self-hosted systems, but migration planning should not treat it as a simple hosted destination where products, customers, orders, categories, CMS Pages, Blog Posts, and redirects merely need to arrive. BigCommerce stores can depend on product options, variants, modifiers, customer groups, price lists, category trees, channels, storefront assignments, custom fields, metafields, apps, and external-system identifiers. Those structures carry commercial meaning that must be interpreted before the migrated store can be trusted.

A BigCommerce migration should therefore be judged by whether the Target Platform supports the way the business sells. Product-choice behavior, pricing visibility, customer segmentation, category discovery, storefront scope, redirects, content continuity, and integration references can all affect whether the migrated data is usable. Record counts matter, but they are only the beginning. A store can contain the expected number of products and still fail if customers cannot select the right configuration, wholesale buyers cannot see the intended prices, old URLs land in weak destinations, or app-managed data is missing from the operating workflow.

### Where BigCommerce Fits in Platform Migration Planning <a href="#where-bigcommerce-fits-in-platform-migration-planning" id="where-bigcommerce-fits-in-platform-migration-planning"></a>

BigCommerce sits between several familiar migration expectations. It is hosted SaaS, so merchants often choose it to reduce hosting, upgrade, and infrastructure burden. At the same time, it is not a lightweight site builder where most migration concerns end at basic product and page transfer. BigCommerce can support structured catalog, pricing, customer, channel, and integration work, which means migration planning has to respect platform-defined data structures.

This creates a different migration profile from both Shopify-family migrations and open-source migrations. A Shopify-to-BigCommerce migration may need careful comparison of options, variants, metafields, apps, redirects, and customer-pricing expectations. A Magento, Adobe Commerce, WooCommerce, OpenCart, PrestaShop, or custom-platform migration may involve translating configurable products, custom fields, customer groups, category hierarchies, extensions, and external IDs into BigCommerce structures. A legacy hosted-cart migration may look simpler by volume but still hide old URL patterns, product-option conventions, and custom checkout-adjacent behavior.

| BigCommerce planning area        | Why it matters during migration                                                                                                              |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Product choices                  | Source options may need to become variants, variant options, modifiers, custom fields, metafields, or Custom Service scope.                  |
| Category and discovery structure | Category trees, product assignments, navigation, and SEO-sensitive paths affect how shoppers find products.                                  |
| Pricing and customer context     | Customer groups, price lists, bulk pricing, and negotiated pricing can change commercial outcomes.                                           |
| Channels and storefront scope    | Channel assignments and Multi-Storefront expectations affect where products, categories, currencies, and content appear.                     |
| Redirect and content continuity  | Redirects, pages, Blog Posts, media, and high-value URLs need launch and search continuity planning.                                         |
| Custom data and integrations     | Metafields, custom fields, apps, external IDs, ERP references, reviews, subscriptions, or merchandising tools may carry operational meaning. |

The key migration question is not whether BigCommerce can host the future store. The key question is whether the source store’s data and behavior can be translated into BigCommerce in a way that preserves buying, pricing, discovery, support, and operational meaning.

### BigCommerce as Hosted SaaS With Structured Commerce Behavior <a href="#bigcommerce-as-hosted-saas-with-structured-commerce-behavior" id="bigcommerce-as-hosted-saas-with-structured-commerce-behavior"></a>

Hosted SaaS reduces some risks and creates others. The merchant does not need to manage the same infrastructure burden that may exist with self-hosted systems, but the merchant must operate inside BigCommerce’s defined catalog, pricing, storefront, API, and integration structures. This is usually an advantage when the business wants governance and scalability, but it requires precise migration planning when the old store used custom code, plugins, modules, checkout changes, or source-specific product logic.

For merchants leaving an open-source or custom environment, BigCommerce can simplify maintenance, but it will not automatically reproduce every custom behavior. For merchants leaving a lighter SaaS or legacy hosted cart, BigCommerce may create a stronger structure for catalog and storefront management, but only if the migration plan classifies product choices, customer pricing, categories, redirects, and custom data correctly.

| Source environment                  | BigCommerce migration implication                                                                                                                                                 |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Open-source or self-hosted platform | Confirm which custom fields, modules, pricing rules, and checkout-related behaviors become supported BigCommerce data, Add-ons scope, Custom Service scope, or target-side setup. |
| Hosted SaaS platform                | Compare option, variant, metafield, app, redirect, and customer-pricing behavior rather than assuming SaaS-to-SaaS equivalence.                                                   |
| CMS-connected commerce              | Separate product data from CMS Pages, Blog Posts, menus, content URLs, and SEO-sensitive landing pages.                                                                           |
| Enterprise commerce                 | Review customer groups, price lists, B2B-like expectations, catalogs, storefront/channel scope, and external-system identifiers.                                                  |
| Legacy cart                         | Watch for outdated URL structures, encoding issues, old custom fields, hard-coded categories, and app-equivalent behavior hidden in templates.                                    |

The stronger BigCommerce migration starts from a distinction between records and behavior. Records describe what exists. Behavior explains how the store sells, prices, displays, redirects, segments, and integrates those records.

### Product Choice and Catalog Meaning <a href="#product-choice-and-catalog-meaning" id="product-choice-and-catalog-meaning"></a>

BigCommerce catalog planning requires careful separation between products, variants, variant options, modifiers, custom fields, metafields, images, reviews, category assignments, channel assignments, and complex rules where relevant. These structures may look similar from a source-store perspective, but they do not carry the same meaning in every platform.

A source store may use one option system for several different purposes: size, color, personalization text, add-on services, gift wrapping, subscription choices, warranty plans, file uploads, bundle components, or configuration rules. Some choices should become sellable variants. Some are closer to modifiers. Some may belong in custom fields or metafields. Some may depend on app logic or custom source behavior that requires Custom Service review.

| Source product pattern                                                | BigCommerce planning question                                                        |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Size, color, material, package, or SKU-level choice                   | Should it become a variant or variant option?                                        |
| Engraving, file upload, gift note, service add-on, or personalization | Is it closer to a modifier or custom field?                                          |
| Bundle, kit, product builder, or component logic                      | Is the behavior supported, target-side setup, or Custom Service scope?               |
| Product-specific metadata used by apps or ERP                         | Should it become a metafield, custom field, integration reference, or excluded data? |
| Product assigned to multiple storefronts or channels                  | Should channel assignment and storefront visibility be validated separately?         |

A migration that moves product names, SKUs, descriptions, prices, and images can still be weak if it loses product-choice meaning. BigCommerce planning should identify the products that reveal the catalog pattern: best sellers, variant-heavy products, modifier-like products, custom-field products, products with special pricing, products assigned to several categories, and products dependent on app behavior.

### Categories, Channels, and Storefront Discovery <a href="#categories-channels-and-storefront-discovery" id="categories-channels-and-storefront-discovery"></a>

BigCommerce categories should be treated as discovery and storefront-structure assets, not only as folders. A category tree can affect navigation, merchandising, search intent, SEO continuity, campaign landing behavior, product assignment, and channel-specific visibility. During migration, the merchant should decide which categories are meaningful customer paths, which are only old administrative groupings, and which should be simplified before launch.

Channel and storefront planning can add another layer. BigCommerce documentation exposes channels and related objects such as listings, menus, sites, currency assignments, and channel-level metafields through management APIs. For migration planning, the important point is that products and content may need to be interpreted by storefront or channel context rather than as one universal catalog view.

| Discovery area               | Migration implication                                                                             |
| ---------------------------- | ------------------------------------------------------------------------------------------------- |
| Category tree                | Preserve, simplify, or rebuild based on shopper discovery and SEO value.                          |
| Product-category assignments | Validate high-value products and categories, not only category count.                             |
| Navigation and menus         | Treat storefront structure as launch readiness, not automatically solved by category migration.   |
| Channels and storefronts     | Confirm which products, categories, content, currencies, and URLs belong in which context.        |
| Redirects                    | Map old high-value product, category, CMS Page, and Blog Post URLs to useful target destinations. |

The strongest BigCommerce category migration does not preserve every old path blindly. It preserves the paths that matter and gives the merchant a clearer storefront structure where legacy categories no longer serve the business.

### Pricing, Customer Groups, and Commercial Context <a href="#pricing-customer-groups-and-commercial-context" id="pricing-customer-groups-and-commercial-context"></a>

BigCommerce pricing migration should be treated as commercial logic. Standard prices, sale prices, bulk pricing, customer groups, price lists, customer-specific or segment-specific pricing, negotiated pricing, and app-controlled pricing can all affect the actual buying outcome.

This is where BigCommerce fit often becomes clearer. A merchant with public retail pricing and basic discounts may need a straightforward pricing review. A merchant with wholesale tiers, distributor pricing, B2B-like buyer groups, regional pricing, contract pricing, or externally managed pricing needs more careful planning. The migration should identify which prices are migrated as product data, which belong in price lists, which are linked to customer groups, and which depend on external systems or custom behavior.

| Pricing context          | Planning concern                                                                                  |
| ------------------------ | ------------------------------------------------------------------------------------------------- |
| Standard and sale prices | Confirm current product pricing and promotion expectations.                                       |
| Bulk pricing             | Validate quantity-based price behavior where it affects key products.                             |
| Customer groups          | Confirm which customers belong to which commercial segment.                                       |
| Price lists              | Preserve pricing context where supported and scoped.                                              |
| External pricing systems | Treat ERP, B2B, quote, contract, or custom pricing logic as integration or Custom Service review. |

A price can look correct in the catalog while still producing the wrong customer outcome. BigCommerce planning should therefore connect pricing data to customer and storefront context, not review it only as a product field.

### Content, Redirects, and SEO Continuity <a href="#content-redirects-and-seo-continuity" id="content-redirects-and-seo-continuity"></a>

BigCommerce migration planning should include content and URL continuity whenever the source store depends on indexed product pages, category pages, CMS Pages, Blog Posts, campaign URLs, or long-lived external links. Redirects are not just a technical SEO step. They preserve customer intent, support navigation, paid campaign continuity, and search equity where the old paths matter.

The merchant should identify high-value URLs before migration rather than waiting until launch. Product URLs, category URLs, CMS Pages, Blog Posts, search landing pages, brand pages, and campaign paths can have different destination logic. Some should redirect to equivalent pages. Some should redirect to improved categories. Some should be retired intentionally. Some content may need to be rebuilt in BigCommerce or handled outside standard migration scope.

| Content or URL item       | Migration decision                                                                  |
| ------------------------- | ----------------------------------------------------------------------------------- |
| Product URLs              | Map to the new product page or approved replacement.                                |
| Category URLs             | Preserve high-value discovery paths and avoid generic destinations where possible.  |
| CMS Pages                 | Decide whether to migrate, rebuild, redirect, merge, or retire.                     |
| Blog Posts                | Preserve where they support organic traffic, buying education, or customer support. |
| Redirects                 | Validate destination quality, not only whether redirects exist.                     |
| Storefront content blocks | Identify whether they are theme, widget, page-builder, app, or migration data.      |

BigCommerce can support content and redirect management, but migration planning should still separate content preservation from storefront design and theme setup.

### Custom Data, Apps, and Integration Boundaries <a href="#custom-data-apps-and-integration-boundaries" id="custom-data-apps-and-integration-boundaries"></a>

BigCommerce’s API and app ecosystem make it attractive for merchants that need integrations, custom workflows, or external system connections. That also means migration planning should identify which source data belongs to the normal commerce record set and which data belongs to apps, scripts, extensions, custom fields, metafields, or outside systems.

Examples include ERP product IDs, customer segmentation fields, product personalization data, reviews, subscriptions, loyalty balances, custom checkout-adjacent fields, merchandising rules, search data, shipping rules, warehouse references, accounting codes, and marketplace identifiers. Some can be handled within supported migration behavior. Some may fit Add-ons when the need is bounded filtering, mapping, or data configuration. Some require Custom Service because the data is unsupported, custom, externally owned, or dependent on bespoke transformation.

The important boundary is not whether the field is valuable. The boundary is whether BigCommerce can receive and use it as supported migration data, whether it requires an Add-on, whether it needs Custom Service evaluation, or whether it belongs to target-side configuration or third-party integration work.

### BigCommerce Migration Planning Priorities <a href="#bigcommerce-migration-planning-priorities" id="bigcommerce-migration-planning-priorities"></a>

BigCommerce planning becomes stronger when the merchant turns platform structure into practical decisions. The first decision is catalog translation: which source product choices should become variants, modifiers, custom fields, metafields, or custom scope. The second is commercial continuity: which prices, customer groups, price lists, promotions, and external pricing references must be preserved or rebuilt. The third is storefront continuity: which categories, channels, content, URLs, and redirects must support the customer journey after launch.

The fourth decision is data ownership. If apps, ERP systems, subscription tools, search tools, merchandising tools, or custom code own important data, the merchant should decide whether that data is supported, Add-on suitable, Custom Service scope, target-side setup, or intentionally excluded. The fifth decision is validation evidence. BigCommerce migration should be judged with samples that prove product choice, price visibility, category discovery, redirect quality, customer history, order context, and custom-data boundaries.

These priorities prevent BigCommerce from being under-scoped as “hosted SaaS.” BigCommerce can be operationally simpler than self-hosted commerce, but the migration still needs careful interpretation of how the old store sold, priced, displayed, segmented, and integrated its data.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce is a strong Target Platform when a merchant wants hosted SaaS operations without abandoning structured catalog, pricing, storefront, content, and integration planning. The migration should not be measured only by record presence. It should preserve commercial meaning: how customers choose products, how prices appear, how categories and channels guide discovery, how important URLs continue, and how custom or app-managed data supports operations.

A successful BigCommerce migration begins with realistic platform interpretation. Products, variants, modifiers, categories, customer groups, price lists, channels, redirects, content, custom fields, metafields, apps, and external identifiers should be reviewed as connected migration decisions rather than isolated fields.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is BigCommerce a simple hosted platform for migration planning?**

No. BigCommerce is hosted SaaS, but migration planning can still be structurally complex when product options, variants, modifiers, customer groups, price lists, channels, redirects, apps, and custom data affect how the store sells.

**Why are product options important in a BigCommerce migration?**

Product options can affect SKU behavior, pricing, personalization, images, inventory, fulfillment, and the buying path. Source options should be classified before migration so they become the right BigCommerce structure or the right custom-handling requirement.

**Does BigCommerce migration automatically preserve storefront discovery?**

No. Categories, navigation, channel visibility, product assignments, CMS Pages, Blog Posts, and redirects need separate review. A product can migrate correctly while the customer path to that product still changes.

**When does BigCommerce migration need Custom Service?**

Custom Service should be considered when unsupported app data, custom fields, metafields with business logic, external identifiers, bespoke transformations, Custom Platform handling, or custom migration logic adjustment is required.

**What should be validated early for BigCommerce?**

Validate representative products with options, important categories, segmented pricing, customer groups, channel or storefront assignments, high-value URLs, customer/order samples, and any app or custom-data examples that affect business operations.
