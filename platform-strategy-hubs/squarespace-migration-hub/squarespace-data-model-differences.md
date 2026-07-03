# Squarespace Data Model Differences

Squarespace is a hosted content-first commerce Target Platform. Its data model combines website presentation, Store Pages, products, inventory, contacts, orders, transactions, media, SEO, and site settings inside a managed platform. A successful migration into Squarespace depends on understanding which source records become Squarespace-supported data, which details become target-site setup, which details require Add-ons, and which structures need Custom Service review.

The main difference is orientation. Many source platforms organize the store around a commerce catalog first, then attach content, design, and marketing tools around it. Squarespace begins with a hosted site experience and layers commerce into that site through pages, product presentation, checkout, orders, contacts, and integrations. This distinction affects how products, categories, content, URLs, customers, subscriptions, order history, and custom records should be reviewed before migration.

### Why Squarespace Data Model Differences Matter <a href="#why-squarespace-data-model-differences-matter" id="why-squarespace-data-model-differences-matter"></a>

Data-model differences are not just field-mapping details. They determine how the migrated store will behave in the Squarespace admin, storefront, customer experience, SEO structure, and operational workflow.

| Source-store assumption                                                                                | Squarespace interpretation                                                                                                                         | Migration planning impact                                                                                                           |
| ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Commerce data is the main structure and content is secondary.                                          | Site structure, content presentation, Store Pages, and commerce data work together.                                                                | Products, CMS Pages, Blog Posts, media, menus, redirects, and domains should be planned together.                                   |
| Categories, menus, collections, and filters may be separate systems.                                   | Product organization and site navigation must be represented through Squarespace-supported collections, pages, menus, and storefront presentation. | Category hierarchy, filter behavior, and merchandising rules may need simplification or rebuild planning.                           |
| Product types may come from apps, custom code, or source-specific modules.                             | Squarespace supports defined product formats and commerce records, with unsupported behavior handled through scope decisions.                      | Physical, service, gift card, download, subscription, and non-standard product behavior should be classified before Full Migration. |
| Checkout logic may be customized deeply.                                                               | Checkout, payment, tax, shipping, discounts, and fulfillment depend on Squarespace-supported configuration and connected services.                 | Historical order data should be separated from live checkout setup and operational configuration.                                   |
| Customer data may represent buyers, members, subscribers, donors, wholesale accounts, or CRM profiles. | Squarespace distinguishes commerce customers, contacts, profiles, marketing/subscriber meaning, and site-member behavior.                          | Customer/contact meaning must be validated, not assumed from a source database field.                                               |

A data model review should identify the difference between transferable records and behavior that must be configured, rebuilt, simplified, or excluded.

### Products, Product Types, and Store Pages <a href="#products-product-types-and-store-pages" id="products-product-types-and-store-pages"></a>

Squarespace product data is not only a list of items. Product records appear inside a hosted site context, usually through Store Pages and product presentation settings. This makes product migration dependent on both commerce fields and site-display decisions.

| Product area         | What usually maps cleanly                                                                            | What needs review                                                                                                                 |
| -------------------- | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Basic product data   | Name, SKU where applicable, description, price, images, stock, status, and standard product details. | Source-specific product fields, custom product tabs, supplier data, internal notes, and app-owned metadata.                       |
| Product types        | Physical products and many standard commerce items can be reviewed as product records.               | Service products, gift cards, downloads, subscription/payment-plan behavior, donations, bookings, and non-standard selling flows. |
| Store presentation   | Product pages, product images, product descriptions, and visible storefront information.             | Exact layout, source theme sections, custom product templates, merchandising widgets, and design parity.                          |
| Product availability | Published/visible products and inventory state.                                                      | Hidden products, draft products, channel-specific products, schedule-based availability, or app-controlled visibility.            |

The migration plan should clarify whether the product is only being transferred as data or whether its storefront presentation, sales behavior, and surrounding page content must also be rebuilt.

### Variants, Options, Images, and Inventory <a href="#variants-options-images-and-inventory" id="variants-options-images-and-inventory"></a>

Variant structures often differ between source platforms and Squarespace. A source product may use option groups, attributes, configurable products, product options, modifiers, or app-based add-ons. Squarespace-supported variants and inventory records should be validated separately from source-specific selling logic.

| Data area                     | Squarespace migration concern                                                                         | Validation focus                                                                                          |
| ----------------------------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Variants                      | Source combinations may not have the same option structure or display behavior.                       | Check option names, choices, SKU/price/stock differences, visibility, and product-page display.           |
| Product options and modifiers | Source options may represent true variants, personalization fields, add-ons, or custom pricing rules. | Separate variant data from checkout customization, personalization, and custom pricing behavior.          |
| Product images                | Product images and variant images may not attach or display exactly like the source store.            | Validate primary images, gallery order, image quality, alt text where included, and product-page display. |
| Inventory                     | Stock may exist at product or variant level.                                                          | Confirm variant-level inventory, stock status, out-of-stock handling, and any external inventory system.  |

Complex variant, personalization, bundle, subscription, or configurable-product behavior may need Add-ons for specific migrated fields, or Custom Service review when Squarespace does not represent the structure directly.

### Collections, Categories, Navigation, and Merchandising <a href="#collections-categories-navigation-and-merchandising" id="collections-categories-navigation-and-merchandising"></a>

Squarespace does not always treat source categories, collections, menus, and filters as identical objects. A source platform may have category trees, layered navigation, product tags, smart collections, brand pages, merchandising rules, and automated filters. In Squarespace, these may become product organization, Store Page structure, site navigation, content pages, or manual merchandising decisions.

| Source structure               | Target interpretation                                                          | Risk if ignored                                                   |
| ------------------------------ | ------------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| Deep category hierarchy        | May need flatter product organization, navigation menus, and landing pages.    | Customers cannot find products in expected paths.                 |
| Automated collections          | May not behave like the source if rules are app-specific or dynamic.           | Merchandising pages lose intended product grouping.               |
| Brand/manufacturer pages       | May become content pages, product grouping, redirects, or accepted exclusions. | SEO and customer navigation signals weaken.                       |
| Filters and faceted navigation | May depend on Squarespace-supported storefront behavior and product data.      | Browsing and product discovery may not match source expectations. |

For Squarespace, the migration should treat product organization as both a data issue and a site-experience issue.

### Customers, Contacts, Members, and Profiles <a href="#customers-contacts-members-and-profiles" id="customers-contacts-members-and-profiles"></a>

Squarespace customer-related data can involve contacts, customers, subscribers, donors, profiles, and site-member concepts. A source store may hold all of these meanings in one customer table or split them across store, CRM, email marketing, membership, and app systems.

| Source data meaning    | Squarespace-related review                                      | Migration implication                                                                                   |
| ---------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Buyer/customer account | Commerce customer identity and order association.               | Validate names, emails, billing/shipping details, and historical order links.                           |
| Contact or subscriber  | Marketing, email subscription, donor, or contact-list meaning.  | Confirm whether the record belongs in migrated commerce scope, marketing tools, or accepted exclusions. |
| Member/account access  | Login, membership, restricted content, courses, or gated areas. | Treat access behavior separately from ordinary customer data.                                           |
| External CRM profile   | Data owned by CRM, email, analytics, or donation tools.         | Preserve external IDs only when relevant and supported by scope.                                        |

Customer migration should avoid assuming that every source customer field becomes an identical Squarespace account or contact field.

### Orders, Transactions, Subscriptions, and Fulfillment <a href="#orders-transactions-subscriptions-and-fulfillment" id="orders-transactions-subscriptions-and-fulfillment"></a>

Squarespace order history is different from live checkout configuration. A migrated order may preserve important historical evidence, but it does not automatically recreate every source checkout workflow, tax rule, payment gateway action, subscription engine, fulfillment integration, or post-purchase automation.

| Order area                  | What to validate                                                                                       | Why it matters                                                                                         |
| --------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| Order identity              | Order number, date, status, customer/contact link, email, billing, and shipping details.               | Historical records must be searchable and understandable.                                              |
| Line items                  | Product names, variants, quantities, prices, discounts, taxes, shipping, and totals.                   | Financial and support teams rely on accurate historical order interpretation.                          |
| Transactions                | Payment labels, payment references, refund records, and financial transaction meaning where supported. | Payment history may be historical record data, not live gateway control.                               |
| Subscriptions/payment plans | Recurring or subscription-related records may have different target behavior.                          | Active subscription operations may need external setup, accepted exclusions, or Custom Service review. |
| Fulfillment                 | Shipment status, carrier data, tracking, fulfillment references, and external logistics IDs.           | Operational continuity may depend on connected systems beyond migrated order data.                     |

Live checkout setup belongs to Squarespace configuration and connected services. Historical orders belong to migrated data validation. Confusing these two areas is a common source of post-migration misunderstanding.

### Discounts, Taxes, Shipping, Payments, and Checkout Configuration <a href="#discounts-taxes-shipping-payments-and-checkout-configuration" id="discounts-taxes-shipping-payments-and-checkout-configuration"></a>

Some source records look like data but function as configuration. Discounts, tax rules, shipping methods, payment gateways, checkout fields, and fulfillment services often need target-side setup even when historical order data migrates cleanly.

| Area            | Data-model difference                                                                                      | Planning response                                                                                |
| --------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Discounts       | Historical coupon use may appear in orders, while active discount rules need target setup.                 | Validate order discounts separately from live discount configuration.                            |
| Taxes           | Historical tax amounts may migrate as order data, while tax calculation must be configured in Squarespace. | Confirm whether tax history, tax settings, or both are in scope.                                 |
| Shipping        | Shipping labels and totals differ from active shipping rules and rates.                                    | Separate migrated order shipping details from live checkout shipping setup.                      |
| Payments        | Payment labels and transaction references are not the same as gateway reconnection.                        | Reconnect gateways and validate historical payment meaning separately.                           |
| Checkout fields | Source custom fields may not have a direct Squarespace equivalent.                                         | Classify fields as migrated notes, Add-ons, Custom Service, external-system data, or exclusions. |

This distinction keeps migration expectations realistic: historical data can be preserved without implying that all source checkout behavior has been replicated.

### CMS Pages, Blog Posts, Media, and Site Content <a href="#cms-pages-blog-posts-media-and-site-content" id="cms-pages-blog-posts-media-and-site-content"></a>

Squarespace is content-first, so non-product content is central to the migration experience. CMS Pages, Blog Posts, media, page structure, menus, sections, embedded content, forms, and landing pages may carry as much business value as catalog records.

| Content area | What can be migrated or rebuilt                                                                        | What needs careful review                                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| CMS Pages    | Page titles, page body content, visible copy, media, metadata, and key landing pages where supported.  | Section layout, blocks, forms, custom scripts, embedded widgets, and exact design behavior.              |
| Blog Posts   | Titles, post content, publication dates, authors where supported, featured images, metadata, and URLs. | Comment systems, custom post types, taxonomy logic, and source-specific editorial structures.            |
| Media        | Images, documents, product media, gallery assets, and content-media references.                        | Image placement, compression, alt text, broken links, file paths, and layout-specific display.           |
| Site design  | Templates, sections, page layout, navigation, and visual hierarchy.                                    | Design must usually be rebuilt or configured in Squarespace, not treated as a direct database migration. |

Content migration should be scoped with SEO and user navigation in mind, not just as a bulk transfer of page text.

### URLs, Redirects, SEO, and Domain Behavior <a href="#urls-redirects-seo-and-domain-behavior" id="urls-redirects-seo-and-domain-behavior"></a>

Squarespace URL behavior may differ from the source store. Product URLs, collection URLs, blog paths, content page paths, media URLs, domain routing, redirects, canonical behavior, and metadata need validation because they influence both user continuity and search visibility.

| SEO element        | Data-model concern                                                                | Validation focus                                               |
| ------------------ | --------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Product URLs       | Source product paths may not match Squarespace product path behavior.             | Validate priority product URLs, redirects, and internal links. |
| Page and blog URLs | Content paths may change during site rebuild or import.                           | Check high-traffic CMS Pages, Blog Posts, and landing pages.   |
| Metadata           | SEO titles, descriptions, slugs, image alt text, and structured content may vary. | Confirm important metadata and accepted exclusions.            |
| Redirects          | Redirects may be target setup rather than migrated record data.                   | Build and test a redirect map before launch.                   |
| Domains            | Domain switching is a launch operation, not a migrated data entity.               | Coordinate DNS, SSL, redirects, and go-live timing separately. |

The safest approach is to treat SEO as a cross-data-model validation layer over products, content, media, navigation, and launch setup.

### API, Integration, and Unsupported Data Boundaries <a href="#api-integration-and-unsupported-data-boundaries" id="api-integration-and-unsupported-data-boundaries"></a>

Squarespace provides APIs for commerce records, but not every source database table, app record, theme behavior, or external-system workflow has a direct target equivalent. Data owned by a source app, CRM, ERP, PIM, marketplace, email tool, subscription service, booking system, donation tool, accounting platform, or custom module may require separate review.

| Boundary type                  | Typical examples                                                                                                     | Migration handling                                                                                |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| API-supported commerce records | Products, inventory, orders, contacts, transactions, profiles, and webhooks.                                         | Validate supported fields and relationships through Demo Migration and Full Migration checks.     |
| External-system records        | ERP IDs, PIM attributes, CRM tags, fulfillment references, accounting IDs, and marketing segments.                   | Preserve only where supported, scoped, and useful in the target operation.                        |
| App-owned behavior             | Scheduling, donations, subscriptions, digital delivery, memberships, forms, loyalty, and third-party sales channels. | Separate migrated records from app setup, reconnection, or accepted exclusions.                   |
| Unsupported custom structures  | Custom database tables, custom checkout logic, source-specific modules, bespoke themes, and dynamic templates.       | Consider Custom Service review and define what can be migrated, rebuilt, simplified, or excluded. |

Custom Service is appropriate when the source data model requires evaluation beyond standard records or specific Add-ons. It should not be described as a substitute for full target-store setup, design implementation, external system configuration, or ongoing operational management.

### Entity Points and Squarespace Data Scope <a href="#entity-points-and-squarespace-data-scope" id="entity-points-and-squarespace-data-scope"></a>

Entity Points planning should follow the data being migrated for the first time. Squarespace migrations may include products, customers/contacts, orders, CMS Pages, Blog Posts, coupons/discount-related records where supported, and other eligible records depending on scope.

Records already counted through the service license do not consume Entity Points again simply because the merchant performs another migration action for the same migration path. New eligible records may consume Entity Points when they are migrated for the first time. This distinction matters when the merchant adds products, customers, orders, Blog Posts, CMS Pages, or other eligible data after the initial migration scope has already been defined.

Entity Points do not solve platform data-model differences. They help measure migration volume. Data-model review still decides whether each record can be represented in Squarespace, needs an Add-on, requires Custom Service review, should be rebuilt manually, or should be excluded.

### Squarespace Data Model Review Matrix <a href="#squarespace-data-model-review-matrix" id="squarespace-data-model-review-matrix"></a>

| Data area          | Standard review question                                                | Advanced review question                                                                                             | Likely handling                                                       |
| ------------------ | ----------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Products           | Do products, prices, images, stock, and descriptions appear correctly?  | Do product types, variants, downloads, gift cards, subscriptions, or special selling formats need special treatment? | Standard scope, Add-ons, Custom Service, or accepted simplification.  |
| Customers/contacts | Are buyer identities and order links clear?                             | Are members, subscribers, donors, marketing contacts, or CRM profiles mixed into the same source data?               | Scope classification, external-system review, or accepted exclusions. |
| Orders             | Are historical order records understandable?                            | Are subscriptions, transactions, refunds, imported channel orders, fulfillment references, or external IDs required? | Historical migration, Add-ons, Custom Service, or external setup.     |
| Content            | Are CMS Pages, Blog Posts, media, and priority landing pages preserved? | Are layouts, custom blocks, forms, embedded scripts, and editorial structures expected to match exactly?             | Migration, rebuild, redesign, or exclusion.                           |
| SEO                | Are priority URLs and metadata preserved or redirected?                 | Are canonical structures, redirect chains, internal links, and domain changes coordinated?                           | Redirect mapping, validation, target setup, and launch planning.      |
| Integrations       | Are required identifiers visible and useful?                            | Does the source depend on custom tables, app behavior, or external workflows?                                        | Custom Service review, reconnection, or accepted exclusions.          |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace data-model differences come from its content-first hosted architecture. Products, inventory, orders, contacts, transactions, CMS Pages, Blog Posts, media, SEO, redirects, and integrations must be reviewed as parts of a site-and-commerce system rather than as isolated database tables. The right migration plan distinguishes standard transferable records from target setup, design rebuild, external-system reconnection, Add-ons, Custom Service review, Entity Points scope, and accepted exclusions.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Squarespace data-model differences matter during migration?**

They determine how source-store records become usable Squarespace products, contacts, orders, content, media, SEO paths, and operational data. A field may transfer cleanly, but the source behavior behind that field may still require target setup, redesign, integration work, Add-ons, or Custom Service review.

**Do product variants migrate into Squarespace exactly as they worked on the source store?**

Not always. Variant names, choices, prices, SKUs, stock, images, and display behavior should be validated. Source-specific options, personalization fields, bundles, configurators, or custom pricing logic may need separate handling.

**Are historical orders the same as live checkout setup in Squarespace?**

No. Historical orders preserve past order information. Live checkout behavior depends on Squarespace configuration and connected services for payments, shipping, tax, discounts, fulfillment, and checkout settings.

**How should content and SEO be reviewed for Squarespace migration?**

Products, CMS Pages, Blog Posts, media, URLs, redirects, metadata, internal links, and domains should be reviewed together. Squarespace migration should preserve important business and SEO signals while recognizing that page layout and site design often need target-side rebuild.

**When does Squarespace data require Custom Service review?**

Custom Service review is appropriate when the source store includes unsupported product structures, custom database records, app-owned workflows, external-system identifiers, unusual order data, source-specific checkout behavior, or content structures that cannot be handled through standard scope or specific Add-ons.
