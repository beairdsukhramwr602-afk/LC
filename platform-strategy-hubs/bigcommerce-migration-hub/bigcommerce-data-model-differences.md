# BigCommerce Data Model Differences

BigCommerce data-model planning should begin with meaning, not record counts. Products, categories, customers, orders, CMS Pages, Blog Posts, redirects, and supporting fields may all have familiar names, but BigCommerce represents commerce through structured catalog, pricing, channel, customer, content, and integration surfaces that may not behave like the Source Platform.

A source store can appear complete after migration while still being commercially wrong. Product choices can be assigned to the wrong structure. Category paths can exist without preserving discovery. Customer records can arrive without the pricing context that made them valuable. Redirects can resolve but send shoppers to weak destinations. Custom fields and metafields can be present but disconnected from the app, ERP, search, merchandising, or storefront behavior they once supported.

The safest BigCommerce migration plan translates source records into BigCommerce meaning before treating the scope as final.

### Why BigCommerce Data Meaning Needs Separate Review <a href="#why-bigcommerce-data-meaning-needs-separate-review" id="why-bigcommerce-data-meaning-needs-separate-review"></a>

BigCommerce is a hosted SaaS Target Platform with defined commerce structures. That structure can simplify governance after migration, but it also requires clearer decisions before migration. A Source Platform may have allowed product options, personalization fields, customer groups, price rules, landing pages, and app-owned behavior to overlap. BigCommerce usually asks those meanings to become more explicit.

The key question is not whether a source record has a BigCommerce destination. The better question is whether the migrated destination preserves the business use of that record.

| BigCommerce area           | Migration meaning to confirm                                                                                                              |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Product choices            | Whether the source choice should become a variant, variant option, modifier, custom field, metafield, app configuration, or custom scope. |
| Category structure         | Whether source categories preserve catalog organization, navigation, merchandising, and SEO-sensitive discovery.                          |
| Pricing context            | Whether base prices, bulk rules, price lists, customer group logic, and external pricing references remain meaningful.                    |
| Channel scope              | Whether products, categories, pricing, content, and URLs belong to the correct storefront or channel context.                             |
| Customer and order records | Whether customer identity, account context, group membership, order history, and service value remain useful.                             |
| Content and routes         | Whether CMS Pages, Blog Posts, redirects, and page destinations preserve customer intent.                                                 |
| Custom and app data        | Whether custom fields, metafields, app-owned records, and outside-system identifiers need Add-ons, Custom Service, or target-side setup.  |

This review prevents a shallow migration approval. The merchant should not only ask, “Did the record move?” The merchant should ask, “Does BigCommerce now hold this record in the structure that supports selling, service, pricing, discovery, and integration continuity?”

### Product Structure: Products, Variants, Options, and Modifiers <a href="#product-structure-products-variants-options-and-modifiers" id="product-structure-products-variants-options-and-modifiers"></a>

BigCommerce product structure requires careful interpretation because source platforms use product choices differently. Some stores use variants for every selectable choice. Others use custom option fields, plugins, apps, product builders, bundle systems, or theme logic. BigCommerce separates several product-choice concepts, and that separation affects inventory, pricing, fulfillment, storefront display, and reporting.

A product variant usually represents a sellable version of a product. Size, color, material, package, model, finish, or unit may belong to variant structure when the choice affects SKU, inventory, image, weight, price, availability, or fulfillment. Variant options describe the selectable dimensions that create those variant combinations.

Modifiers are different. A modifier can represent a customer-facing choice that changes the buying experience without necessarily creating a separate stock-tracked product. Examples may include personalization text, engraving, gift messages, optional add-ons, file upload fields, warranty selections, or non-inventory customization. When source options are moved into the wrong structure, the product page may look complete while operational behavior becomes wrong.

| Source product choice                    | BigCommerce interpretation question                           | Risk if misread                                                          |
| ---------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Size or color with SKU and stock         | Should it become a variant and variant option?                | Inventory and order line meaning may be weakened.                        |
| Engraving or gift message                | Is it closer to a modifier or custom field?                   | Buyer input may become a fake stock-tracked option.                      |
| Bundle or kit selection                  | Is it supported, app-owned, or custom logic?                  | Pricing, fulfillment, and inventory expectations may break.              |
| Warranty or compatibility field          | Is it display information, product metadata, or app behavior? | Important commercial context may be preserved as text but lose function. |
| Upload field or personalization workflow | Is target-side app setup or Custom Service needed?            | A product may migrate but fail the original buying workflow.             |

Product data should be sampled across real catalog patterns. A simple product, a variant-heavy product, a modifier-heavy product, a bundled product, and a product with custom data reveal more than a product count.

### Custom Fields, Metafields, and Product Metadata <a href="#custom-fields-metafields-and-product-metadata" id="custom-fields-metafields-and-product-metadata"></a>

BigCommerce custom fields and metafields can preserve additional product context, but they should be planned by purpose. Some values support product-page display. Some help internal search, merchandising, comparison tables, warranty compatibility, fitment, technical specifications, personalization, ERP lookup, or storefront behavior. Others belong to app logic or outside systems and may not behave as ordinary migrated fields.

This distinction matters because source stores often hide business meaning inside flexible fields. A custom attribute in Magento, a metafield in Shopify, a product meta field in WooCommerce, or a plugin-owned field in another platform may not have a single BigCommerce equivalent. The migration plan should decide whether the value is customer-facing information, an internal reference, a filterable attribute, an integration identifier, or unsupported behavior.

| Custom-data purpose                             | Likely planning direction                                                 |
| ----------------------------------------------- | ------------------------------------------------------------------------- |
| Product-page display                            | Supported mapping may be enough when the target field is suitable.        |
| Internal product reference                      | Preserve only if staff, reporting, or integrations need it.               |
| Search or filter behavior                       | Confirm whether the value can support the intended storefront experience. |
| ERP, PIM, or accounting identifier              | Review integration continuity and possible Custom Service needs.          |
| App-owned personalization or subscription logic | Treat as app/custom scope, not ordinary product text.                     |
| Bespoke transformation requirement              | Review for Custom Service.                                                |

Add-ons can help when the requirement remains inside supported filtering, mapping, or data configuration. Custom Service should be considered when the requirement involves unsupported app data, custom logic, outside-system identifiers, bespoke transformation, or custom migration logic adjustment.

### Categories, Category Trees, Navigation, and Discovery <a href="#categories-category-trees-navigation-and-discovery" id="categories-category-trees-navigation-and-discovery"></a>

Category migration into BigCommerce should not be treated as a simple folder transfer. Categories, category trees, product assignments, menu logic, storefront discovery, and SEO-sensitive routes can all influence customer navigation. A source category may have served several roles at once: admin organization, public landing page, merchandising collection, campaign grouping, menu entry, search filter, or SEO page.

BigCommerce planning should separate those roles. A category may need to become a BigCommerce category. A menu relationship may need target-side storefront setup. A high-value landing page may require content preservation or a redirect plan. A collection-like source structure may need mapping, manual rebuilding, app support, or exclusion.

| Source structure               | BigCommerce planning question                                                                      |
| ------------------------------ | -------------------------------------------------------------------------------------------------- |
| Product category               | Should it become a BigCommerce category or category-tree entry?                                    |
| Collection or smart group      | Is it a category, a merchandising rule, a storefront setup need, or an app-equivalent requirement? |
| Navigation menu                | Does it belong to catalog data or theme/storefront setup?                                          |
| SEO landing page               | Should it migrate as content, category context, redirect target, or rebuilt page?                  |
| Campaign or temporary category | Should it be migrated, retired, redirected, or excluded?                                           |

For multi-storefront or channel-aware merchants, category meaning also depends on where products are meant to appear. A category that is useful in one storefront may be confusing in another. Product assignments, naming, routes, and redirect destinations should therefore be reviewed in the relevant selling context.

### Pricing, Customer Groups, and Price Lists <a href="#pricing-customer-groups-and-price-lists" id="pricing-customer-groups-and-price-lists"></a>

Pricing is one of the most important BigCommerce data-model differences because it can exist at several levels. A source store may have base product prices, sale prices, bulk pricing, customer-group pricing, wholesale tiers, regional pricing, negotiated buyer prices, price-list behavior, app-managed rules, or external pricing systems.

BigCommerce migration planning should not flatten those relationships into one product price unless the business truly wants a simpler pricing model after migration. Pricing context should be reviewed as a relationship between products, customers, groups, price lists, quantity conditions, storefronts, channels, apps, and external systems.

| Pricing source          | Meaning to preserve                                                          |
| ----------------------- | ---------------------------------------------------------------------------- |
| Product base price      | The default selling value.                                                   |
| Bulk pricing            | Quantity-based pricing expectations.                                         |
| Customer-group price    | Buyer-segment or wholesale logic.                                            |
| Price list              | More structured audience, channel, or business pricing context.              |
| App-managed pricing     | Business logic that may need target-side app setup or Custom Service review. |
| External pricing system | Identifier and synchronization continuity, not only visible price output.    |

A migrated product may show the right base price while still failing for a wholesale buyer, customer group, channel, or regional storefront. Sensitive pricing examples should be identified before migration and checked after Demo Migration.

### Channels, Storefronts, and Selling Context <a href="#channels-storefronts-and-selling-context" id="channels-storefronts-and-selling-context"></a>

BigCommerce channel and storefront structures can affect product availability, category presentation, currency context, theme/site relationships, menus, pricing assumptions, redirects, and customer experience. That makes channel meaning a data-model concern, not only an implementation setting.

Source Platforms may express channel logic through multiple stores, marketplaces, regions, language versions, domains, app integrations, sales channels, or custom code. BigCommerce needs a clear target interpretation: which products appear where, which prices apply, which content belongs to which storefront, and which routes should be preserved.

A migration should clarify:

* whether the merchant uses one storefront or multiple storefronts;
* whether product availability differs by storefront or channel;
* whether category structures differ by audience, region, brand, or language;
* whether content and redirects belong globally or to specific storefronts;
* whether customer groups or price lists affect storefront/channel behavior;
* which external channels or apps must be reconnected after migration.

Without that clarification, the target store may look organized from the admin side while customer-facing storefronts behave inconsistently.

### Customers, Accounts, and Order History <a href="#customers-accounts-and-order-history" id="customers-accounts-and-order-history"></a>

Customer and order data should be interpreted as commercial and service context. A customer record may include identity, addresses, account status, customer group assignment, custom attributes, consent, order relationships, and pricing expectations. An order may preserve product names, SKUs, quantities, discounts, taxes, shipping, billing, fulfillment, payment labels, notes, refunds, and external references.

The migration plan should ask what the business needs customer and order history to support. Customer service, repeat purchasing, wholesale access, support lookup, reporting, refund review, and integration reconciliation may require different levels of detail.

A source account system may not translate exactly into BigCommerce account behavior. Passwords, group memberships, loyalty data, subscriptions, quote workflows, company accounts, customer approvals, or external CRM references may need separate review. Some values can be mapped. Some may require Add-ons. Some may require Custom Service. Some may need target-side app setup or remain outside the migration scope.

Orders require the same discipline. Historical order data should remain readable and useful, but live payment setup, checkout behavior, shipping configuration, tax settings, notifications, and fulfillment workflow belong to target-side setup and validation.

### Content, Pages, Blog Posts, Redirects, and Route Meaning <a href="#content-pages-blog-posts-redirects-and-route-meaning" id="content-pages-blog-posts-redirects-and-route-meaning"></a>

BigCommerce content and URL continuity should be treated as part of data-model translation because pages, Blog Posts, redirects, product paths, category paths, and storefront destinations shape customer trust and search continuity. A redirect may technically work while still weakening the customer journey if it sends an old product, category, or content URL to a broad or unrelated destination.

CMS Pages and Blog Posts should be reviewed by purpose. Some pages support trust, policies, brand explanation, buying guidance, campaign traffic, or SEO discovery. Some Blog Posts may carry long-tail search value or product education. Some source pages may no longer deserve migration but still require a redirect to a useful destination.

| Content or route type     | Migration decision                                                                |
| ------------------------- | --------------------------------------------------------------------------------- |
| Product URL               | Preserve or redirect to the closest matching product.                             |
| Category URL              | Preserve discovery intent where possible.                                         |
| CMS Page                  | Migrate, rebuild, consolidate, redirect, or retire.                               |
| Blog Post                 | Preserve if it carries traffic, education, trust, or internal-link value.         |
| Campaign page             | Decide whether the campaign remains active, needs redirect, or should be retired. |
| Storefront-specific route | Confirm the correct storefront or channel destination.                            |

Route planning should happen before launch, not after traffic starts failing. The strongest BigCommerce migration plans treat redirects as customer journeys, not only technical mappings.

### Apps, Integrations, and External-System Data <a href="#apps-integrations-and-external-system-data" id="apps-integrations-and-external-system-data"></a>

BigCommerce migrations often intersect with external systems. ERP, PIM, CRM, accounting, tax, shipping, subscription, personalization, search, reviews, loyalty, warehouse, marketplace, or marketing systems may rely on identifiers and custom fields that are not visible in a normal storefront review.

The data-model question is whether BigCommerce needs to own the data, display the data, pass the data to an app, preserve it for reconciliation, or ignore it because the workflow will be rebuilt. These are different outcomes.

| External dependency         | BigCommerce migration concern                                                        |
| --------------------------- | ------------------------------------------------------------------------------------ |
| ERP or accounting           | Product IDs, SKUs, order references, customer identifiers, and tax/discount context. |
| PIM                         | Attribute ownership, product copy, images, variants, and custom fields.              |
| CRM or marketing            | Customer identity, consent, segmentation, order history, and custom attributes.      |
| Subscription or loyalty app | App-owned records, behavior, and continuity expectations.                            |
| Search or merchandising app | Filter attributes, custom fields, product tags, rules, and ranking behavior.         |
| Shipping or tax system      | External identifiers and checkout-adjacent behavior.                                 |

If the data is supported and only needs mapping or filtering, Add-ons may help. If the data is unsupported, app-owned, externally controlled, or requires bespoke transformation, Custom Service should be evaluated before the migration path is finalized.

### BigCommerce Data Scope Should Be Judged by Business Use <a href="#bigcommerce-data-scope-should-be-judged-by-business-use" id="bigcommerce-data-scope-should-be-judged-by-business-use"></a>

A BigCommerce migration should not aim for the largest possible transfer by default. It should aim for a target data set that supports selling, discovery, pricing, customer service, reporting, content continuity, and integration stability. The scope is strongest when each record type has a clear post-migration purpose inside BigCommerce rather than simply existing as a copied field from the Source Platform.

Entity volume matters, but entity volume does not prove data meaning. Product, Customer, Order, and Blog Posts counts can support planning, but they do not show whether product choices, price context, storefront scope, redirects, custom fields, metafields, and app-owned data are usable inside BigCommerce. A merchant may have a manageable number of products but still require deeper review if product options rely on rules, modifiers, price lists, channel assignments, or app-owned merchandising fields.

| Scope question                                        | BigCommerce planning implication                                                                                                                         |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Does the record support selling or discovery?         | Products, categories, variants, modifiers, images, and redirects should be reviewed for customer-facing usefulness.                                      |
| Does the record affect pricing or customer treatment? | Price lists, customer groups, discounts, and external pricing identifiers may require closer mapping or Custom Service review.                           |
| Does the record affect a storefront or channel?       | Channel assignments and storefront-specific visibility should be treated as scope decisions, not generic product fields.                                 |
| Does the record come from an app or integration?      | App-owned fields, metafields, subscriptions, reviews, loyalty data, or ERP references may need Add-ons, Custom Service, target-side setup, or exclusion. |

A data scope is strong when the merchant can explain which records migrate normally, which require Add-ons, which require Custom Service, which must be configured in BigCommerce, and which should be excluded or rebuilt. That explanation is more useful than a large transfer promise because it connects migration output to actual BigCommerce operation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce data-model differences matter because the platform gives migrated records structured commercial meaning. Products, variants, modifiers, categories, customer groups, price lists, channels, customers, orders, CMS Pages, Blog Posts, redirects, custom fields, metafields, apps, and external identifiers should be reviewed according to how the business will use them after launch.

The strongest BigCommerce migration plan preserves not only data presence but data behavior. It separates supported records from target-side setup, Add-ons, Custom Service needs, and excluded expectations before Full Migration creates avoidable ambiguity.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are BigCommerce product options important during migration?**

Product options can represent different business meanings. Some choices should become variants, some may be closer to modifiers, some may be custom fields, and some may depend on apps or custom logic. If the meaning is misread, product pages may appear complete while inventory, pricing, fulfillment, or customer selection behaves incorrectly.

**Are BigCommerce custom fields and metafields enough for all source custom data?**

No. They can preserve certain additional data, but they do not automatically reproduce source-platform behavior. App-owned records, external-system identifiers, bespoke product logic, and custom transformations may require Custom Service or target-side setup.

**Do BigCommerce categories preserve source navigation automatically?**

Not always. Categories, category trees, menu structure, SEO landing pages, and storefront/channel context should be reviewed separately. A category can migrate successfully while the buyer discovery path still needs target-side setup or redirect planning.

**How should price lists and customer groups affect migration planning?**

They should be treated as relationships, not isolated fields. A product price may look correct while a customer group, price list, quantity rule, or storefront condition still needs review.

**When should BigCommerce data require Custom Service review?**

Custom Service should be considered when unsupported app data, custom fields with business logic, external-system identifiers, bespoke transformations, Custom Platform interpretation, or custom migration logic adjustment are required.
