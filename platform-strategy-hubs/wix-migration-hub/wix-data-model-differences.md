# Wix Data Model Differences

Wix migration changes how store and site data is interpreted. The Target Platform is not only a product database or a standalone cart. It is a hosted website, commerce, content, app, member, contact, checkout, order, and integration environment. A source record that looks simple in one platform may become a Wix Stores product, a Wix eCommerce catalog item, a collection assignment, a contact, a member, an order-history record, a Blog Post, a CMS Page, a Wix app record, a Velo/API dependency, or a service-plugin requirement.

The data-model question is therefore not only whether records can be moved into Wix. It is whether the migrated data still keeps its business meaning after it enters Wix: shoppers must understand product choices, staff must read orders, marketers must find customer/contact context, content pages must remain discoverable, SEO-sensitive paths must be protected, and app or integration-owned data must be classified correctly.

### Why Wix Data-Model Differences Matter <a href="#why-wix-data-model-differences-matter" id="why-wix-data-model-differences-matter"></a>

Wix combines storefront management, site building, content tools, member experiences, business apps, and developer extension points inside a hosted environment. That creates a different migration model from platforms where merchants control the database, theme code, extension tables, and checkout logic directly.

| Source-store meaning         | Possible Wix interpretation                                                                                            | Migration planning question                                                                                                    |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Product catalog              | Wix Stores products, Wix eCommerce catalog items, custom catalog integration, or app-owned selling records             | Which records are standard products and which represent services, bookings, pricing plans, donations, events, or custom items? |
| Product options and variants | Product options, choices, variants, modifiers, target simplification, app logic, or Custom Service review              | Do shopper selections still control price, SKU, stock, media, fulfillment, or personalization correctly?                       |
| Categories and navigation    | Collections, menus, filters, search, site sections, landing pages, or redirects                                        | Can shoppers still discover the same product groups in the target storefront?                                                  |
| Customer data                | Customer records, contacts, members, CRM-style records, app records, or external-system profiles                       | Does the data preserve ordering, marketing, login, account, or membership meaning?                                             |
| Orders                       | Historical order records with line items, totals, taxes, discounts, shipping, payment, fulfillment, and status context | Does migrated history remain readable without confusing it with live checkout setup?                                           |
| Content and SEO              | CMS Pages, Blog Posts, site pages, product pages, media, slugs, metadata, redirects, or manually rebuilt pages         | Which content should migrate as data and which needs target design or implementation?                                          |
| App and custom behavior      | Wix apps, Velo/API logic, service plugins, custom catalogs, external systems, Add-ons, or Custom Service               | Which business meaning is data migration, and which is target behavior or integration work?                                    |

A Wix data model should be evaluated through meaning and use, not only record count.

### Wix Products Are Commerce and Site Records <a href="#wix-products-are-commerce-and-site-records" id="wix-products-are-commerce-and-site-records"></a>

A product in Wix is not just a title, SKU, and price. It participates in the site experience: product pages, product media, collections, search, storefront display, SEO metadata, inventory, cart behavior, checkout, payments, fulfillment, and sometimes apps or service plugins.

| Product layer      | Wix interpretation                                                                      | Validation focus                                                        |
| ------------------ | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Product identity   | Name, slug, SKU, visibility, and product-page behavior                                  | Confirm duplicate handling, SKU continuity, and product discoverability |
| Product content    | Description, short content, media, galleries, ribbons, labels, and SEO values           | Confirm formatting, image relationships, alt text, and display quality  |
| Commercial data    | Price, sale price, taxability, inventory, weight, availability, and fulfillment context | Confirm what is migrated and what must be configured in Wix             |
| Collection context | Product assignment to collections, menus, landing pages, or filtered experiences        | Confirm shopper navigation and merchandising paths                      |
| App/custom context | Product data controlled by apps, Velo, custom catalogs, or external systems             | Classify as standard scope, Add-ons, Custom Service, or target setup    |

This distinction matters because a product can migrate as a record while still failing the target business use if options, media, collections, search, or checkout behavior are not interpreted correctly.

### Product Options, Choices, Variants, and Modifiers Are Not the Same Thing <a href="#product-options-choices-variants-and-modifiers-are-not-the-same-thing" id="product-options-choices-variants-and-modifiers-are-not-the-same-thing"></a>

Source platforms often store product choice data in different ways: variants, options, modifiers, custom fields, add-ons, bundles, configurable products, personalization fields, or app-owned structures. In Wix, these meanings should be separated before migration decisions are finalized.

| Source pattern                                                   | Wix-facing interpretation                                                            | Risk if misclassified                                                                     |
| ---------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Size, color, style, material, or other purchase choices          | Product options, choices, or variants                                                | Shoppers may see choices but staff may lose SKU, price, stock, or media detail            |
| Variant-specific price, SKU, stock, or image                     | Variant-level review                                                                 | Options may migrate visually but not remain operationally correct                         |
| Optional personalization or paid inputs                          | Modifiers, app-supported fields, or Custom Service review                            | Customer selections may not appear in order detail or fulfillment context                 |
| Bundles, kits, or composite products                             | Supported target structure, app behavior, accepted simplification, or Custom Service | The target product may not preserve the original buying logic                             |
| Digital items, service items, events, bookings, or pricing plans | Wix Stores, Wix Bookings, Wix Events, Pricing Plans, or app-specific setup           | Non-standard selling models may be forced into the wrong product model                    |
| Custom catalog or external product source                        | Catalog service plugin or integration planning                                       | Wix checkout may depend on external catalog behavior rather than migrated product records |

The important planning decision is whether each choice is only descriptive, shopper-selectable, stock-bearing, price-bearing, fulfillment-relevant, or app-controlled. Each answer leads to a different Wix treatment.

### Collections, Categories, Filters, and Site Navigation Change Meaning <a href="#collections-categories-filters-and-site-navigation-change-meaning" id="collections-categories-filters-and-site-navigation-change-meaning"></a>

A source category tree does not always become an identical Wix browsing model. Wix storefront discovery may depend on collections, menus, search, product galleries, filters, product pages, landing pages, and site-section design.

| Source structure           | Wix data-model decision                                                         | What to protect                                              |
| -------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Primary category hierarchy | Product collections and navigation structure                                    | Main browse paths and high-value category landing pages      |
| Marketing groups           | Collections, campaign pages, menus, or manual storefront sections               | Merchandising context and promotional meaning                |
| Filterable attributes      | Product options, product data fields, app-supported filters, or search settings | Shopper filtering and comparison behavior                    |
| SEO category pages         | Wix site pages, collection pages, redirects, metadata, or accepted redesign     | Organic-search value and internal-link structure             |
| Internal labels            | Tags, collection assignments, or excluded internal data                         | Admin organization without polluting the customer experience |

This is where Wix migrations often need practical target interpretation. A migration can preserve product-to-collection assignment but still need site-level work to make the target storefront feel coherent.

### Customers, Contacts, Members, and CRM Records Need Separate Classification <a href="#customers-contacts-members-and-crm-records-need-separate-classification" id="customers-contacts-members-and-crm-records-need-separate-classification"></a>

Customer data can have several meanings in Wix. A buyer with historical orders, a marketing contact, a site member, a booking customer, a pricing-plan subscriber, a form submitter, and an app-specific profile may all look like customer-related data in the source platform. They do not necessarily belong to the same target object.

| Source meaning                                                     | Wix-related interpretation                                                       | Review focus                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Buyer with order history                                           | Customer/contact association with historical orders                              | Order readability, address context, and identity matching                             |
| Marketing subscriber                                               | Contact and consent-related data                                                 | Subscription status, segmentation, source of consent, and marketing-system continuity |
| Site account or login                                              | Member-related planning                                                          | Access expectations, member pages, passwords, and login behavior                      |
| Wholesale/B2B buyer                                                | Contact, member, app-supported group, pricing rule, or Custom Service scope      | Pricing, approval, access, and purchasing rules                                       |
| Booking, event, restaurant, donation, loyalty, or plan participant | App-owned record or external-system profile                                      | Whether records migrate, reconfigure, integrate, or remain outside scope              |
| Custom customer fields                                             | Contact fields, member fields, app fields, custom data, or Custom Service review | Whether values are visible, searchable, operational, or integration-critical          |

This classification prevents a common mistake: assuming “customers migrated” means all account, CRM, membership, marketing, pricing, and app behavior has also been preserved.

### Orders Preserve History, Not Complete Checkout Behavior <a href="#orders-preserve-history-not-complete-checkout-behavior" id="orders-preserve-history-not-complete-checkout-behavior"></a>

Migrated Wix orders should be evaluated as historical records. They can preserve useful context for staff, customer support, reporting, and launch continuity. They do not automatically recreate live payment, tax, shipping, checkout, fulfillment, notification, or cart behavior.

| Order element                               | Data-model meaning                                       | Migration review question                                                                       |
| ------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Line items                                  | What was purchased and in what quantity                  | Are product names, SKUs, choices, modifiers, and prices readable?                               |
| Customer context                            | Who placed the order and where it shipped or billed      | Are historical identities, guest records, contacts, and addresses understandable?               |
| Totals and discounts                        | Historical calculation result                            | Are subtotal, tax, shipping, discounts, and grand total preserved as usable history?            |
| Payment labels                              | Historical payment context                               | Does the payment method label remain readable without implying gateway setup?                   |
| Shipping and fulfillment                    | Method, tracking, fulfillment state, or delivery context | Can staff interpret the fulfillment history after launch?                                       |
| Refunds, cancellations, notes, and metadata | Operational history and support context                  | Which fields need to migrate, which are accepted exclusions, and which require custom handling? |

Live checkout setup is a separate target configuration and testing task. Wix cart, checkout, discounts, tax, payments, orders, fulfillment, and service plugins can all shape new transactions after launch, but those capabilities should not be confused with migrated order history.

### CMS Pages, Blog Posts, Media, and Site Content Need Target Interpretation <a href="#cms-pages-blog-posts-media-and-site-content-need-target-interpretation" id="cms-pages-blog-posts-media-and-site-content-need-target-interpretation"></a>

Wix migration often includes site content as well as store records. CMS Pages, Blog Posts, landing pages, product pages, collection pages, menus, media, embedded content, forms, galleries, and SEO metadata may not transfer as identical layouts.

| Content type                  | Wix interpretation                                                               | Migration concern                                                     |
| ----------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| CMS Pages                     | Wix site pages, CMS-driven pages, manually rebuilt pages, or accepted exclusions | Content value, layout dependency, forms, scripts, and internal links  |
| Blog Posts                    | Wix Blog content or rebuilt content                                              | Author, date, category/tag, media, slug, metadata, and URL continuity |
| Media files                   | Wix media assets connected to products, pages, posts, galleries, and SEO         | File relationships, alt text, display placement, and broken embeds    |
| Landing pages                 | Site pages, collection pages, campaign pages, or redesigned sections             | SEO value, conversion path, tracking, and navigation placement        |
| Product/category descriptions | Product content, collection content, page sections, or SEO fields                | Whether text supports selling, search, or merchandising               |
| Menus and internal links      | Wix navigation and page-link structure                                           | Whether important customer journeys remain intact                     |

The migration plan should distinguish between content values that can be moved as records and design/page experiences that need Wix target implementation.

### Apps, Velo, APIs, and Service Plugins Can Own Business Meaning <a href="#apps-velo-apis-and-service-plugins-can-own-business-meaning" id="apps-velo-apis-and-service-plugins-can-own-business-meaning"></a>

Wix is extensible through apps, Velo/API development, custom catalogs, and service plugins. These layers can change the meaning of catalog, cart, checkout, shipping, payment, validation, membership, loyalty, booking, event, restaurant, donation, CRM, or integration data.

| Dependency                  | What it can own                                                                                                           | Scope implication                                                                    |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Wix apps or app equivalents | Bookings, events, restaurants, forms, pricing plans, loyalty, donations, reviews, memberships, and other business records | App data may need separate review from standard product/customer/order migration     |
| Velo/API logic              | Custom workflows, field handling, automations, validations, and external-system sync                                      | May require Custom Service or separate implementation work                           |
| Service plugins             | Custom fees, shipping rates, cart/checkout validation, external payment services, and custom catalogs                     | Business behavior may depend on target extension setup rather than migrated records  |
| External systems            | ERP, PIM, CRM, fulfillment, WMS, accounting, marketplace, analytics, and middleware                                       | External IDs and integration state should be preserved only where in scope           |
| Custom catalogs             | Sellable records supplied by external or specialized catalog services                                                     | Products may need catalog-service integration rather than ordinary product migration |

These dependencies should be classified before Demo Migration acceptance. If a record only works because of custom behavior, moving the value alone is not enough.

### SEO, URLs, Redirects, and Domain Data May Not Transfer One-to-One <a href="#seo-urls-redirects-and-domain-data-may-not-transfer-one-to-one" id="seo-urls-redirects-and-domain-data-may-not-transfer-one-to-one"></a>

Wix can manage slugs, metadata, redirects, site URLs, domains, page SEO, product SEO, Blog Post SEO, and site navigation. However, source URL structures may not map exactly into Wix route patterns or page architecture.

| SEO or URL element | Wix data-model consideration                                                                   | Review priority                                                               |
| ------------------ | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Product URLs       | Product page route and slug behavior                                                           | Preserve priority product paths or plan redirects                             |
| Category URLs      | Collection/page route behavior                                                                 | Protect high-value category or landing-page traffic                           |
| Blog URLs          | Wix Blog route and slug behavior                                                               | Confirm post slugs, dates if relevant, internal links, and redirects          |
| CMS Pages          | Wix page route and navigation context                                                          | Check page paths, metadata, internal links, and forms                         |
| Redirects          | Target redirect rules                                                                          | Map high-value URLs before launch                                             |
| SEO metadata       | Titles, descriptions, canonical values, image alt text, and structured content where supported | Identify fields that must migrate, be recreated, or be accepted as exclusions |

URL and SEO planning should be part of the data model because the same content record can have different search meaning depending on its target route, page type, and redirect plan.

### Entity Points and Wix Data Scope <a href="#entity-points-and-wix-data-scope" id="entity-points-and-wix-data-scope"></a>

Entity Points planning should follow the actual migrated data scope, not a generic count of source-store complexity. Wix migration scope can include commerce records, content records, and selected related data, while app-owned or custom records may require separate handling.

| Data area                       | Entity Points implication                                                                                               | Planning note                                                                |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Products, customers, and orders | Eligible records may consume Entity Points when migrated for the first time                                             | Confirm which records are included in the service license and selected scope |
| CMS Pages and Blog Posts        | May be included where supported and selected                                                                            | Review content quality, layout dependency, and URL value before migration    |
| New records added later         | New eligible records may consume Entity Points when migrated for the first time                                         | Use data-freeze and follow-up planning to avoid confusion                    |
| Previously counted records      | Should not consume Entity Points again simply because another migration action is performed for the same migration path | Keep duplicate-consumption logic clear in follow-up planning                 |
| App/custom records              | May be excluded, Add-ons scope, or Custom Service scope                                                                 | Classify before assuming the values are standard migration entities          |

The duplicate-consumption rule is especially important when a merchant performs later migration activity. Records already counted through the service license should not consume Entity Points again simply because another migration action is performed for the same migration path; new eligible records may consume Entity Points when migrated for the first time.

### Add-ons and Custom Service in Wix Data Mapping <a href="#add-ons-and-custom-service-in-wix-data-mapping" id="add-ons-and-custom-service-in-wix-data-mapping"></a>

Add-ons and Custom Service solve different data-model problems. Add-ons extend supported migration behavior. Custom Service is for requirements that need tailored review, custom handling, unsupported structures, or source/target logic that cannot be treated as standard scope.

| Requirement                                                                                           | Likely handling                                       | Why it matters                                                                    |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------- | --------------------------------------------------------------------------------- |
| Standard product/customer/order/content data with supported fields                                    | Standard Service                                      | The record type and fields fit supported migration behavior                       |
| Additional supported data handling                                                                    | Standard Add-ons, Tailored Add-ons, or Custom Add-ons | The data is still within defined migration-extension logic                        |
| SEO, mapping, filtering, or configuration-related supported enhancements                              | Relevant Add-ons                                      | The work extends migration output without becoming full custom implementation     |
| App-owned records, unsupported source fields, custom catalogs, Velo logic, or service-plugin behavior | Custom Service review                                 | Business meaning depends on non-standard logic or target implementation decisions |
| External-system workflow state                                                                        | Custom Service or separate integration planning       | Data continuity may require coordination beyond migrated record values            |

The boundary should be set before Full Migration because it affects cost, timeline, sample selection, and acceptance criteria.

### Wix Data-Model Decision Matrix <a href="#wix-data-model-decision-matrix" id="wix-data-model-decision-matrix"></a>

| Decision area         | Standard data-model signal                                                                                                   | Escalation signal                                                                                     |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Catalog               | Products, options, variants, collections, media, prices, and inventory fit supported Wix structures                          | Custom catalogs, unusual selling models, bundles, app-managed product logic, or unsupported modifiers |
| Customer/account data | Customers, contacts, members, and order relationships can be classified clearly                                              | Membership, loyalty, B2B, access, pricing, or CRM logic depends on app or custom behavior             |
| Orders                | Historical records remain readable with products, totals, discounts, tax, shipping, payment, status, and fulfillment context | Operational workflow state, custom metadata, or external-system order logic is required after launch  |
| Content               | CMS Pages, Blog Posts, media, slugs, metadata, and redirects can be planned separately from design                           | Layout, scripts, forms, dynamic pages, or apps carry the main business meaning                        |
| Apps/integrations     | External identifiers can be preserved where needed                                                                           | App, API, Velo, service-plugin, or middleware behavior must be rebuilt or synchronized                |
| SEO                   | Priority URLs and metadata can be mapped or redirected                                                                       | Target route structure cannot preserve important pages without redesign or custom planning            |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix data-model planning should translate source-store meaning into the right Wix layer: commerce records, collections, contacts, members, historical orders, content pages, Blog Posts, media, SEO fields, app records, Velo/API logic, service plugins, or external integrations. A clean migration is not only a matter of moving values into fields. It should preserve the way the target site will sell, display, organize, search, support, and operate after launch.

The strongest early proof comes from sample records that expose real complexity: option-heavy products, variant inventory, important collections, customers with order history, contacts or members, varied orders, CMS Pages, Blog Posts, app-dependent records, custom checkout or shipping behavior, and SEO-sensitive URLs. If those samples do not translate clearly, the migration plan should define Add-ons, Custom Service, target setup, accepted exclusions, or implementation work before Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are Wix products the same as products in my current store?**

Not always. Product titles, descriptions, images, SKUs, and prices may transfer clearly, but product options, variants, modifiers, custom catalogs, subscriptions, services, bookings, events, and app-owned selling models may require separate interpretation.

**Do categories become Wix collections automatically?**

Not in every case. Some source categories can become Wix collections, while others may need menus, filters, site pages, landing pages, redirects, or manual storefront planning to preserve shopper discovery and SEO value.

**Are Wix customers, contacts, and members the same thing?**

No. A customer may relate to order history, a contact may support marketing or CRM activity, and a member may support login or restricted access. Source customer data should be reviewed by business meaning, not only by record type.

**Does migrated order history configure live Wix checkout?**

No. Historical orders preserve past transaction context. Live checkout, payment providers, shipping rates, tax setup, fulfillment, notifications, and validation behavior require Wix target configuration and testing.

**When does Wix data require Custom Service review?**

Custom Service review is appropriate when important source data depends on unsupported app records, Velo/API behavior, service plugins, custom catalogs, external-system identifiers, custom checkout logic, or target behavior beyond supported migration scope.
