# Gambio Data Model Differences

Gambio migration is not only a transfer of products, customers, and orders into a new administration area. It is a translation of commercial meaning into a Gambio shop structure, where catalog records, variants, stock behavior, customer groups, storefront design, content pages, SEO settings, integrations, and hosting responsibility may all affect how the migrated store works after launch.

This matters because source stores rarely use data in a neutral way. A category may carry navigation meaning. A product option may control price, stock, or shopper choice. A customer group may affect B2B pricing or access. A downloadable product may depend on file handling, order status, or customer account behavior. A content page may support legal, trust, or conversion requirements. After migration, these records need to make sense inside Gambio’s operating model, not merely appear as imported data.

### Core Structural Layers in Gambio <a href="#core-structural-layers-in-gambio" id="core-structural-layers-in-gambio"></a>

Gambio combines a shop administration layer, storefront presentation layer, catalog layer, customer/order layer, configuration layer, integration layer, and hosting/deployment layer. The practical data-model question is how each source concept should be understood after it enters the Gambio environment.

| Gambio layer                     | Migration meaning                                                                                                                                                         | What the migrated result must preserve                                                                                       |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Catalog structure                | Products, categories, product options, variants, images, stock, downloads, base prices, filters, and related product logic become the foundation of the sellable catalog. | Products should remain understandable, purchasable, searchable, and manageable.                                              |
| Customer and pricing structure   | Customers, customer groups, B2B conditions, segmented prices, addresses, and account context can affect commercial behavior.                                              | Customers should remain connected to meaningful pricing, account, and order context.                                         |
| Order history                    | Orders carry product, customer, total, tax, shipping, payment, status, and fulfillment meaning.                                                                           | Historical orders should remain useful for service, accounting reference, fulfillment review, and customer support.          |
| Storefront and content structure | Layout, content pages, SEO paths, navigation, category presentation, product pages, and design elements shape how shoppers experience the store.                          | The store should remain navigable and credible after launch, even where design work is configured separately from migration. |
| Operational configuration        | Taxes, currencies, languages, shipping, payments, inventory, legal/compliance settings, and integrations may depend on Gambio configuration.                              | The merchant should know which behavior comes from migrated data and which must be configured in Gambio.                     |
| Hosting and customization layer  | Cloud and self-hosted Gambio environments do not carry the same operational responsibility or customization surface.                                                      | Migration expectations should reflect the selected Gambio environment.                                                       |

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

#### Products are commercial structures, not isolated records <a href="#products-are-commercial-structures-not-isolated-records" id="products-are-commercial-structures-not-isolated-records"></a>

In Gambio, product data should be interpreted as the foundation of the sellable catalog. A product is not only a title, SKU, description, price, and image. It may also involve product options, variants, inventory, downloadable files, base prices, product images, reviews, specials, cross-selling relationships, shipping implications, category placement, filters, and SEO metadata.

A source platform may use a different product model. Some platforms treat variants as separate products, some attach option values to a parent product, and some use app-owned option logic or custom product fields. During migration, the important question is whether the product remains commercially readable inside Gambio. Shoppers should be able to choose the right item, and the merchant should be able to manage stock, pricing, images, categories, and product relationships without guessing what the migrated records mean.

#### Product options and variants need careful interpretation <a href="#product-options-and-variants-need-careful-interpretation" id="product-options-and-variants-need-careful-interpretation"></a>

Options and variants are often one of the most sensitive catalog translation areas. A source store may use options for color, size, material, package, warranty, engraving, digital format, or bundle selection. Those options may affect price, availability, SKU, stock, product images, shipping behavior, or order line meaning.

In Gambio, these relationships should be reviewed as part of catalog meaning. If source options are simple shopper selections, they may be easier to interpret. If they control inventory, price changes, image changes, or downstream fulfillment, they deserve closer review. A migration can look successful at record level while still failing if shoppers cannot choose the right variant or if order lines no longer show what was purchased.

#### Categories, filters, and navigation carry discovery meaning <a href="#categories-filters-and-navigation-carry-discovery-meaning" id="categories-filters-and-navigation-carry-discovery-meaning"></a>

Categories are not just containers for products. They shape how shoppers browse, compare, and trust the store. Gambio catalog planning should consider category hierarchy, product placement, filters, manufacturer relationships, specials, cross-selling, and any source structure used to guide discovery.

The data-model difference becomes important when the source platform combines category, tag, collection, menu, and filter behavior differently from Gambio. A product that belongs to several source collections may need a clear category or filtering strategy in Gambio. A source store with deep category trees may require careful validation so products do not become buried. A source store with SEO-sensitive category URLs should also treat route and metadata behavior as part of the storefront interpretation, not only the catalog import.

#### Downloadable products and special product types need source evidence <a href="#downloadable-products-and-special-product-types-need-source-evidence" id="downloadable-products-and-special-product-types-need-source-evidence"></a>

Gambio supports downloadable products, but downloadable product migration should not be assumed to behave like ordinary physical product migration. File references, access expectations, order status dependencies, customer account access, and historical purchase context may all affect whether the migrated result is operationally useful.

Stores with digital products, mixed physical and digital products, or products requiring special fulfillment logic should identify representative samples before migration. If the source platform stores downloads through custom apps, external file systems, membership tools, or third-party services, the migration may require Custom Service review.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

#### Customers are connected to pricing, orders, and account behavior <a href="#customers-are-connected-to-pricing-orders-and-account-behavior" id="customers-are-connected-to-pricing-orders-and-account-behavior"></a>

Customer data in Gambio should remain connected to the merchant’s operating logic. Names, emails, addresses, and account records are only the visible part of the model. The useful meaning often depends on customer groups, historical orders, pricing expectations, tax treatment, B2B account needs, and communication context.

This is especially important for merchants using segmented pricing, customer-group logic, B2B conditions, wholesale pricing, or recurring high-value customer accounts. If customer group meaning is unclear in the source store, the migrated Gambio customer structure may appear complete but fail to support the merchant’s actual pricing or service workflow.

#### Customer groups can change commercial interpretation <a href="#customer-groups-can-change-commercial-interpretation" id="customer-groups-can-change-commercial-interpretation"></a>

Customer groups are a key planning area because they can affect pricing, access, discounts, B2B treatment, or customer segmentation. A source platform may use groups, tags, roles, price lists, company accounts, membership levels, or app-managed segmentation. These structures should not be flattened into ordinary customer records without review.

For a Gambio migration, the merchant should identify which customer groups matter after launch, which customers belong to them, which prices or conditions depend on them, and whether group behavior is standard enough for the selected migration path. When segmentation is used only for marketing, the migration implication may be lighter. When segmentation controls actual commercial rules, it becomes a data-model and validation priority.

### Order and Historical Data Meaning <a href="#order-and-historical-data-meaning" id="order-and-historical-data-meaning"></a>

#### Orders must remain useful beyond order numbers <a href="#orders-must-remain-useful-beyond-order-numbers" id="orders-must-remain-useful-beyond-order-numbers"></a>

Order migration should preserve business meaning, not just order IDs. Historical orders are often used for customer service, fulfillment questions, warranty checks, accounting reference, repeat purchase support, and dispute review. A useful migrated order should retain readable customer identity, product line items, option or variant selections, quantities, totals, discounts, tax, shipping, payment context, status meaning, and address information as far as supported by the selected migration path.

Different source platforms store order meaning differently. Some preserve complete option labels on order lines. Some store source-specific statuses. Some rely on payment gateways, fulfillment apps, ERP references, or shipping integrations to explain what happened. Those details should be reviewed before migration if the merchant expects historical Gambio orders to support operations after launch.

#### Order statuses need interpretation, not direct naming assumptions <a href="#order-statuses-need-interpretation-not-direct-naming-assumptions" id="order-statuses-need-interpretation-not-direct-naming-assumptions"></a>

Order statuses can look simple, but they often carry operational meaning. A source status such as processing, paid, shipped, partially refunded, cancelled, failed, pending review, or awaiting fulfillment may not map one-to-one into the target status structure. The migration should preserve useful meaning where supported, but the merchant may still need to configure or interpret statuses inside Gambio.

The risk is not only that a status label changes. The risk is that the team misunderstands what the status means after launch. If old orders are used for customer service or finance review, status samples should be checked carefully during Demo Migration and final validation.

### Storefront, Content, and SEO Meaning <a href="#storefront-content-and-seo-meaning" id="storefront-content-and-seo-meaning"></a>

#### Storefront data is connected to design and navigation <a href="#storefront-data-is-connected-to-design-and-navigation" id="storefront-data-is-connected-to-design-and-navigation"></a>

Gambio storefront meaning includes more than product and category records. Layout, responsive theme behavior, StyleEdit changes, content pages, navigation, category pages, product pages, internal links, metadata, and SEO paths all affect how shoppers experience migrated data.

A migrated catalog may be technically present but commercially weak if storefront organization is not planned. Product pages need images, descriptions, options, related information, and price context. Category pages need clean product grouping. Content pages may support legal requirements, brand trust, shipping information, returns, payment explanations, or conversion paths. SEO-sensitive stores should identify priority URLs and metadata before launch.

#### Content pages should not be confused with product records <a href="#content-pages-should-not-be-confused-with-product-records" id="content-pages-should-not-be-confused-with-product-records"></a>

Many stores use content pages for legal pages, service information, buying guides, FAQ pages, landing pages, brand pages, and policy pages. These pages may not belong to the same data model as products, categories, customers, or orders. In Gambio, content management and storefront presentation can support this material, but the migration plan should distinguish store records from content implementation.

This distinction matters during validation. A Demo Migration should not be judged only by whether products and orders appear. For stores with important content pages, navigation paths, or SEO traffic, validation should also confirm whether the target storefront supports the content structure needed for launch, even if some design or page work is completed separately by the merchant or implementation team.

### Extension, Integration, and Customization Meaning <a href="#extension-integration-and-customization-meaning" id="extension-integration-and-customization-meaning"></a>

#### Integrations can own data that is not visible in standard exports <a href="#integrations-can-own-data-that-is-not-visible-in-standard-exports" id="integrations-can-own-data-that-is-not-visible-in-standard-exports"></a>

Gambio stores may connect to marketplaces, payment providers, shipping services, ERP systems, analytics, marketing services, product feeds, or other interfaces. Source stores may also use apps, plugins, modules, scripts, custom tables, or external systems to create behavior that standard records do not fully describe.

This creates a data-model boundary. Standard migration can address supported data within the selected migration path, but external identifiers, integration-owned states, marketplace-specific fields, ERP references, custom fulfillment data, or third-party rule behavior may require review. If the target Gambio shop must preserve this meaning, the project may need Advanced Data Mapping, Advanced Data Configure, or Custom Service.

#### Cloud and self-hosted Gambio change implementation expectations <a href="#cloud-and-self-hosted-gambio-change-implementation-expectations" id="cloud-and-self-hosted-gambio-change-implementation-expectations"></a>

The selected Gambio environment can affect how migrated data is implemented and maintained. Gambio Cloud reduces hosting and update responsibility, while self-hosting gives the merchant more control over hosting, technical access, customization, and maintenance. This difference should not change the basic need for clean product, customer, and order data, but it can change how customization, interfaces, and operational responsibility are planned.

A merchant moving into Gambio Cloud should be especially clear about which requirements fit the managed environment and which require configuration rather than code-level intervention. A merchant moving into self-hosted Gambio should be ready to manage hosting, updates, technical dependencies, custom work, and integration maintenance as part of the future operating model.

### Custom Platform Source Interpretation <a href="#custom-platform-source-interpretation" id="custom-platform-source-interpretation"></a>

When the Source Platform is a Custom Platform, the data model should not be assumed to match Gambio’s structure. Custom Platform sources may contain bespoke product tables, unusual option logic, non-standard customer segmentation, external order references, custom tax or shipping logic, content relationships, proprietary URLs, or third-party identifiers.

For these cases, the migration should begin with source interpretation. The team must understand what each data field means, how records relate to one another, which relationships are required after launch, and which target structures can represent them. Custom Platform handling points to Custom Service because the work may require custom migration logic adjustment, bespoke transformation, or review beyond standard service capability.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

A successful Gambio migration should prove that the source store’s commercial meaning has survived inside the target environment. The following proof areas are especially important:

| Proof area            | What to confirm in Gambio                                                                                                                                   |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog meaning       | Products, categories, variants, options, images, prices, stock, downloads, filters, and manufacturer relationships remain understandable and usable.        |
| Customer meaning      | Customer records, addresses, customer groups, B2B or pricing context, and order relationships remain clear.                                                 |
| Order meaning         | Historical orders preserve line items, totals, tax, shipping, payment context, statuses, discounts, and option selections where supported.                  |
| Storefront meaning    | Product pages, category pages, content pages, navigation, metadata, and SEO-sensitive paths make sense in the target shop.                                  |
| Configuration meaning | Tax, shipping, payment, currencies, languages, stock behavior, and legal/compliance-related settings are either migrated, configured, or marked for review. |
| Custom meaning        | Custom fields, integration data, external identifiers, and bespoke source behavior are reviewed through the right Add-on or Custom Service path.            |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio data-model differences are mainly about meaning translation. Products must become manageable Gambio catalog records. Options and variants must remain understandable to shoppers and administrators. Customer groups must preserve commercial context. Orders must remain useful for history and support. Storefront, content, SEO, and design structures must support the migrated data instead of merely displaying it. Configuration-sensitive behavior such as tax, shipping, payment, currency, language, inventory, and integration logic must be separated from ordinary record transfer.

The strongest migration plans identify these meaning layers before Full Migration. They treat Demo Migration as a chance to test whether Gambio can represent the source store’s real operating logic, not just whether record counts match.

Use Demo Migration samples to test product variants, customer groups, orders, content pages, SEO-sensitive categories, tax/shipping/payment context, and any custom or integration-owned data. If the source store contains non-standard product logic, customer segmentation, external identifiers, custom development, or Custom Platform data, review the migration path through Live Chat so the correct Add-on or Custom Service boundary is clear before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do Gambio data model differences matter during migration?**

They matter because source records may not carry the same meaning inside Gambio. Products, variants, categories, customer groups, orders, content pages, and configuration settings need to be interpreted so the migrated store remains usable, not merely populated.

**Are product options and variants the same in every migration to Gambio?**

No. Source platforms may represent options, variants, and product choices differently. The migration should verify how option labels, prices, stock, images, and order line meaning appear in Gambio before Full Migration.

**Should customer groups be reviewed before migrating to Gambio?**

Yes. Customer groups can affect pricing, B2B behavior, discounts, tax context, or access. If the source store uses groups, tags, roles, price lists, or membership structures, those meanings should be reviewed before migration.

**Can Gambio content pages be treated like product data?**

No. Content pages, legal pages, buying guides, landing pages, and policy pages usually have different responsibilities from product records. They should be planned as part of storefront and content continuity, not flattened into catalog migration assumptions.

**When do custom source fields require Custom Service for Gambio migration?**

Custom Service should be reviewed when source fields, external identifiers, integration-owned data, Custom Platform structures, bespoke product logic, or custom order relationships need interpretation beyond standard service capability or Standard Add-on behavior.
