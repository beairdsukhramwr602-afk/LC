# BigCommerce Data Model Differences

Migrating to BigCommerce is not only a matter of moving Products, Customers, Orders, categories, CMS Pages, Blog Posts, and related records into a hosted Target Platform. The more important work is translating what those records mean once BigCommerce represents the store through products, variants, variant options, modifiers, categories, category trees, customer context, price lists, channels, redirects, custom fields, metafields, apps, and integration references.

A store can look complete after migration while still behaving incorrectly if the buying logic is assigned to the wrong product-choice structure, price context is detached from the right customer segment, categories no longer support discovery, storefront or channel assignments are unclear, or custom fields and external IDs lose operational meaning. BigCommerce data-model review should therefore focus on commercial interpretation, not simple record presence.

### Why Data Model Differences Matter <a href="#why-data-model-differences-matter" id="why-data-model-differences-matter"></a>

BigCommerce often makes source-store assumptions more explicit. A previous platform may have blended product variants, personalization choices, add-ons, bundled selections, wholesale pricing, category navigation, redirects, and app-owned behavior into a loose or highly customized structure. BigCommerce usually asks those meanings to be placed into clearer target-side structures.

That can improve governance, but it also creates migration risk. If the migration treats every option as the same kind of product choice, every price as a product-level value, every category as an administrative folder, or every custom field as display-only information, the target store may not support the same buying journey after launch.

| Data-model area          | Meaning that must be preserved                                                                                         |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| Product choices          | Whether a choice is a sellable variation, modifier, personalization field, bundle-like behavior, or custom logic.      |
| Catalog discovery        | Whether categories, category trees, product assignments, and navigation still help customers find the right products.  |
| Pricing context          | Whether prices depend on customer groups, price lists, bulk rules, storefront/channel conditions, or external systems. |
| Storefront/channel scope | Whether products, categories, prices, content, and URLs belong to the correct selling context.                         |
| Custom data              | Whether custom fields, metafields, app data, and external IDs still support operations and integrations.               |

The right migration question is not only, “Did the data move?” It is, “Does the data still behave as the business expects inside BigCommerce?”

### Catalog and Product Structure Differences <a href="#catalog-and-product-structure-differences" id="catalog-and-product-structure-differences"></a>

BigCommerce product data should be reviewed through the relationship between products, variants, variant options, modifiers, custom fields, metafields, images, brands, inventory, and pricing-related structures. These elements may resemble product data from another platform, but they do not always carry identical meaning.

#### Products, variants, and variant options <a href="#products-variants-and-variant-options" id="products-variants-and-variant-options"></a>

A true variant usually represents a sellable product choice that can affect SKU, inventory, price, image, weight, availability, fulfillment, or reporting. Size, color, material, package size, finish, and model may need variant treatment when each choice is a distinct purchasable form of the product.

Variant options help describe the selectable dimensions that create those sellable combinations. During migration, variant review should confirm that the source store’s option combinations still produce the intended SKU and inventory behavior after landing in BigCommerce.

#### Modifiers and customer-facing choices <a href="#modifiers-and-customer-facing-choices" id="modifiers-and-customer-facing-choices"></a>

Modifiers are important when a customer-facing choice changes the buying experience without necessarily creating a separate inventory-tracked product. Personalization text, engraving, gift messages, optional add-ons, upload fields, custom notes, or non-stocked selections may need a different interpretation from size or color variants.

This distinction matters because a product can display selectable choices while still being operationally wrong. If a personalization field becomes a stock-tracked variant, or a true inventory-bearing choice becomes a non-stocked modifier, the storefront may confuse customers and create fulfillment or reporting problems.

#### Product custom fields, metafields, and app-shaped product data <a href="#product-custom-fields-metafields-and-app-shaped-product-data" id="product-custom-fields-metafields-and-app-shaped-product-data"></a>

BigCommerce custom fields and metafields can preserve additional product context, but they should not be used as a dumping ground for unclear source data. A custom field that supports product-page display has a different migration meaning from a metafield used by an app, an ERP identifier used for reconciliation, or a rule that controls subscriptions, warranties, compatibility, search, or merchandising.

When product-related information controls behavior rather than display, the migration plan should determine whether the data can be mapped through supported handling, needs Add-ons for filtering or mapping, or requires Custom Service because it depends on unsupported app data, outside-system identifiers, or bespoke transformation.

### Category, Collection, Navigation, or Storefront Structure Differences <a href="#category-collection-navigation-or-storefront-structure-differences" id="category-collection-navigation-or-storefront-structure-differences"></a>

BigCommerce category structure affects more than product organization. Categories, category trees, product assignments, storefront navigation, SEO-sensitive paths, and storefront/channel context can shape how customers discover and compare products.

A previous platform may have used categories as menus, landing pages, merchandising collections, SEO folders, internal reporting groups, or temporary campaign structures. During migration, those roles should not be merged without review. A category that exists only for navigation has a different meaning from a category that drives search traffic, product filtering, merchandising, or storefront assignment.

For stores using multiple storefront or channel contexts, catalog structure needs extra care. A product may belong in one storefront but not another. A category may be useful in one brand, region, language, or audience context and confusing elsewhere. The target structure should clarify where the product appears, which categories guide discovery, and which paths need redirect support.

### Customer, Account, and Order Data Differences <a href="#customer-account-and-order-data-differences" id="customer-account-and-order-data-differences"></a>

Customer and order records should be reviewed as commercial context, not only historical data. BigCommerce customer data may need to preserve identity, addresses, customer groups, pricing access, order history, and service-useful context. Orders may need to remain meaningful for customer service, analytics, reconciliation, support, and future selling decisions.

#### Customer groups and price context <a href="#customer-groups-and-price-context" id="customer-groups-and-price-context"></a>

Customer groups and price lists can change how pricing is interpreted. If the original store used wholesale groups, loyalty tiers, distributor accounts, regional pricing, negotiated terms, or app-managed customer segments, BigCommerce needs a clear target-side representation of that commercial logic.

A migrated customer record is not enough when the customer’s buying terms depend on group membership, price-list assignment, or an external pricing system. The migration should preserve the relationship between customer identity and the pricing behavior that matters to the business.

#### Orders as operational history <a href="#orders-as-operational-history" id="orders-as-operational-history"></a>

Order migration should preserve enough context for service, reporting, and internal reconciliation. Product names, SKUs, prices, discounts, taxes, shipping, billing addresses, fulfillment context, customer notes, and historical status details can all affect how useful order data remains after migration.

When historical orders include app-owned fields, custom checkout data, subscriptions, quotes, specialized shipping rules, or external IDs, those details should be classified before migration. Some may be ordinary mapped fields, while others may require Custom Service if they sit outside standard supported behavior.

### Content, URL, and SEO Data Differences <a href="#content-url-and-seo-data-differences" id="content-url-and-seo-data-differences"></a>

BigCommerce content and route continuity should be treated as part of data-model translation because content records, product paths, category paths, pages, Blog Posts, redirects, and storefront destinations work together. A URL can be technically redirected but still weak if it sends visitors to a less relevant product, an overly broad category, a wrong storefront context, or a page that no longer supports the same purchase intent.

CMS Pages and Blog Posts should be reviewed by purpose. Some pages support trust, policies, customer education, landing campaigns, or SEO discovery. Some Blog Posts may carry long-tail traffic or product education value. Migration planning should distinguish content worth preserving from content that needs consolidation, rewriting, or redirect handling.

Redirect review should prioritize high-value product, category, brand, page, blog, and campaign paths. The target destination should preserve customer intent, not merely avoid a broken link.

### App, Extension, Integration, or Custom Data Differences <a href="#app-extension-integration-or-custom-data-differences" id="app-extension-integration-or-custom-data-differences"></a>

BigCommerce migrations often involve more than standard store records. Apps, themes, custom fields, metafields, external IDs, ERP references, CRM references, reviews, subscriptions, fulfillment tools, search systems, personalization logic, tax services, and analytics integrations may carry data that determines how the business operates.

The key distinction is whether a field is informational, operational, or behavioral.

| Custom-data type       | Migration meaning                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------------------------ |
| Display information    | Can often be preserved as product or content context if the target field is clear.                     |
| Operational identifier | Must remain stable enough for reconciliation, integration, reporting, or fulfillment.                  |
| App-owned data         | Needs review because the receiving app, field, or workflow may differ in BigCommerce.                  |
| Behavior-driving logic | May require configuration, Custom Service, or post-migration rebuild outside ordinary record movement. |

Custom Platform sources need a particularly careful interpretation layer. The original store may store product logic, pricing context, category relationships, customer segmentation, or external identifiers in structures that do not map cleanly to BigCommerce. If those requirements require bespoke transformation or custom migration logic adjustment, they belong under Custom Service rather than being treated as ordinary field movement.

### How Data Model Differences Affect Migration Scope <a href="#how-data-model-differences-affect-migration-scope" id="how-data-model-differences-affect-migration-scope"></a>

BigCommerce data-model differences affect migration scope because the same entity list can hide very different work. A store with many simple products may be easier to migrate than a smaller store with complex modifiers, customer-specific pricing, app-owned data, channel assignments, and external IDs.

Scope should be reviewed by meaning and risk, not only by entity count.

| Scope question                                           | Why it affects migration planning                                                                     |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Which product choices are true variants?                 | Controls SKU, inventory, price, image, fulfillment, and reporting behavior.                           |
| Which choices are modifiers or customization fields?     | Preserves customer-facing selection without creating false inventory logic.                           |
| Which categories control discovery or SEO?               | Determines category-tree planning, product assignment, navigation, and redirects.                     |
| Which customers receive special pricing or access?       | Affects customer groups, price lists, and validation scenarios.                                       |
| Which records belong to a storefront or channel context? | Prevents products, categories, prices, content, and URLs from appearing in the wrong selling context. |
| Which custom fields or IDs are operational?              | Determines whether Add-ons or Custom Service should be considered.                                    |

Additional Migration Options can support later migration activity when the same migration path needs follow-up handling, but they should not be used to postpone data-model decisions. Product-choice logic, pricing context, category structure, storefront assignment, redirects, and custom-data ownership should be understood before Full Migration because those decisions shape how the target store will operate.

### Conclusion <a href="#conclusion" id="conclusion"></a>

BigCommerce data-model differences matter because the platform asks migrated records to carry clear commercial meaning. Products must distinguish true variants from modifiers and custom fields. Categories must support discovery. Customer and pricing data must preserve buying context. Content and redirects must protect customer intent. Custom data and external IDs must remain usable for the systems and workflows that depend on them.

A successful BigCommerce migration should prove that the Target Platform represents how the business sells, not only that the expected records appear. Demo Migration review should therefore include option-heavy products, customer-group and price-list cases, category trees, storefront or channel examples, high-value URLs, CMS Pages, Blog Posts, custom fields, metafields, app-owned data, and external identifiers before scope is treated as stable.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What is the most important BigCommerce data-model difference to review first?**

Product-choice meaning is often the first priority. The migration should distinguish true variants from modifiers, personalization fields, custom fields, app behavior, and custom logic because those decisions affect SKU, inventory, pricing, fulfillment, and customer experience.

**Are BigCommerce categories just folders for products?**

No. Categories and category trees can affect discovery, navigation, merchandising, SEO-sensitive paths, and storefront/channel context. They should be reviewed as part of the customer journey, not only as administrative grouping.

**Why do customer groups and price lists matter in data migration?**

They can define the commercial context of a customer or product price. When wholesale, loyalty, distributor, regional, or negotiated pricing exists, migrated customer and product data should preserve the pricing relationship that supports the buying outcome.

**Should redirects be reviewed as part of data-model migration?**

Yes. Redirects connect products, categories, pages, Blog Posts, storefront destinations, and search intent. A redirect is only useful when the target destination preserves the meaning of the old path for customers and search engines.

**When does BigCommerce data-model migration require Custom Service?**

Custom Service should be considered when the migration depends on unsupported app data, Custom Platform structures, outside-system identifiers, bespoke transformations, custom fields with operational meaning, or custom migration logic adjustment beyond standard supported handling.
