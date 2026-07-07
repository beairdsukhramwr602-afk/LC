# Squarespace Data Model Differences

Squarespace combines commerce records with the structure of a hosted website. Product data, Store Pages, product URLs, images, SEO fields, inventory, orders, contacts, transactions, and site settings all matter, but they do not behave like a free-form database that can reproduce every source-store object exactly. A migration into Squarespace should therefore translate data meaning, not only field names.

The most important difference is that Squarespace treats commerce as part of the site experience. A product may have a name, description, images, price, product type, variant data, SEO fields, URL slug, and Store Page association. That product can be migrated as a recognizable commerce record, but merchandising layout, page design, navigation placement, checkout behavior, fulfillment rules, and some third-party workflows still depend on target-side setup or external systems.

A strong Squarespace data review separates supported commerce records from presentation choices, configuration settings, historical context, and unsupported custom behavior. That distinction helps merchants avoid the common mistake of expecting a data migration to recreate an entire site experience without reviewing how Squarespace stores, displays, and operates each part of the store.

### Data Meaning Translation Framework <a href="#data-meaning-translation-framework" id="data-meaning-translation-framework"></a>

Squarespace data-model planning should translate each source record into one of four meanings: migrated record, Squarespace configuration, site-content rebuild, or unsupported/custom requirement. That framework is more useful than a simple entity checklist because Squarespace blends commerce with website structure.

| Source expectation               | Squarespace meaning                                                                                                            | Migration planning action                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Product record                   | Product data connected to product type, Store Page context, visibility, images, SEO fields, URL slug, variants, and inventory. | Validate both record accuracy and customer-facing placement.                       |
| Category or collection structure | Store Page, navigation, tag, content, or product-discovery structure rather than a universal category model.                   | Decide how source categories become product discovery and site navigation.         |
| Customer account                 | Contact, customer, subscriber, donor, member, or address-book context depending on how the source platform stored identity.    | Separate purchasable history from marketing, membership, and account expectations. |
| Order history                    | Historical commerce record, transaction context, fulfillment reference, or customer-service history.                           | Validate history without assuming live checkout readiness.                         |
| CMS or design content            | Page, Blog Post, media, template layout, navigation item, or manual rebuild requirement.                                       | Decide what is migrated, rebuilt, redirected, or excluded.                         |
| Custom app data                  | Integration-owned or source-specific behavior.                                                                                 | Review for Add-ons, Custom Service, external ownership, or accepted exclusion.     |

### Why Squarespace Data Model Differences Matter <a href="#why-squarespace-data-model-differences-matter" id="why-squarespace-data-model-differences-matter"></a>

Squarespace data-model differences matter because the same source-store information may become different kinds of target work. Some values can become Squarespace product data. Some become site structure or Store Page placement. Some become SEO or URL planning. Some belong to contacts, orders, or inventory. Some belong to integrations, custom code, booking tools, donation tools, fulfillment systems, or marketing systems that are not the same as core commerce data.

For migration planning, the practical question is not only whether a record exists. The question is what the record is expected to do after it enters Squarespace. A product description must display correctly. A variant must connect to the right option structure and inventory behavior. A product URL must support traffic continuity. A customer record must be understood as a contact or buyer profile, not necessarily as the same account model from the source platform. An order must preserve historical meaning without being confused with live checkout configuration.

| Source-store assumption                                                       | Squarespace interpretation                                                                                                                        | Migration planning impact                                                                                                 |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Product data alone defines the storefront.                                    | Product records work inside Store Pages, site design, navigation, and content presentation.                                                       | Store Page placement, product visibility, page layout, and navigation should be reviewed separately from migrated fields. |
| Categories, menus, collections, and filters have the same meaning everywhere. | Product organization must fit Squarespace-supported Store Page, tag, page, and navigation behavior.                                               | Deep category trees, custom filters, and source-specific merchandising rules may need simplification or target setup.     |
| Variants are just copied combinations.                                        | Variants must align with Squarespace-supported product attributes, SKUs, pricing, inventory, and display behavior.                                | Option names, SKU logic, pricing differences, images, and inventory should be sampled before Full Migration.              |
| Customer data equals customer accounts.                                       | Squarespace commerce data can involve contacts, customers, address books, marketing preferences, donors, and subscribers depending on the source. | Buyer identity, marketing consent, account access expectations, and address data require separate review.                 |
| Historical orders recreate operations.                                        | Orders preserve transaction and fulfillment history, while live payment, shipping, tax, fulfillment, and checkout settings must be configured.    | Order import expectations should be separated from launch configuration.                                                  |

The result should be a target store that is understandable inside Squarespace, not merely a collection of copied records.

The main data-model risk is assuming that source structure and target meaning are the same. In Squarespace, a record can be technically present but commercially incomplete if the surrounding site context is not planned. Product data needs Store Page and visibility review. SEO fields need URL and redirect planning. Contact records need identity interpretation. Order history needs separation from checkout configuration.

For that reason, the most valuable data-model review is not only whether an entity is supported. It is whether the migrated result gives the merchant a usable Squarespace operating state after the site has been configured and validated.

### Products, Product Types, and Store Page Meaning <a href="#products-product-types-and-store-page-meaning" id="products-product-types-and-store-page-meaning"></a>

Squarespace product records carry commerce fields, but they also sit within a site structure. Product migration should account for product type, visibility, Store Page placement, URL slug, SEO data, images, tags, variants, and pricing. A source product may look straightforward until its selling behavior depends on product bundles, bookings, wholesale rules, subscriptions, custom option logic, customer-specific pricing, or an app-owned product model.

Squarespace supports defined product types such as physical, service, gift card, and digital products through its commerce product structure. That matters because source platforms may represent products more broadly. A source catalog can include configurable products, grouped products, event registrations, appointment-based services, membership products, course access, donation items, or product records managed by an external system. During migration, those records should be classified by what Squarespace can store natively and what must be rebuilt, configured, integrated, or excluded.

| Product area         | Squarespace data meaning                                                                                                                  | Review priority                                                                                                                  |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Product identity     | Name, description, product type, visibility, tags, Store Page, URL slug, and SEO fields identify how a product appears and is discovered. | Confirm that products are visible, assigned correctly, and reachable through the intended site structure.                        |
| Product media        | Images can migrate as product assets, but order, alt text, quality, cropping, and display behavior may differ.                            | Review priority products visually, not only by record count.                                                                     |
| Product type         | Squarespace-supported product formats may not match every source selling model.                                                           | Classify physical, service, gift card, digital, subscription-like, booking-like, donation, and custom products before migration. |
| Product URLs         | Product URL and slug behavior affects SEO and internal links.                                                                             | Preserve or redirect priority product paths where possible.                                                                      |
| Product presentation | Store Page layout and design are not the same as migrated data fields.                                                                    | Plan design and content setup separately from data transfer.                                                                     |

This distinction prevents a common planning error: treating product migration as complete when the product exists in the admin, even if shoppers cannot discover it, understand it, or buy it through the intended flow.

### Variants, Product Attributes, and Inventory <a href="#variants-product-attributes-and-inventory" id="variants-product-attributes-and-inventory"></a>

Variant handling is one of the most important Squarespace data-model review areas. Product variants can contain SKU and pricing information, and inventory is managed at the variant level. That means source options should be reviewed as operational selling structures, not only as display labels.

A migration plan should confirm whether each source option becomes a clean Squarespace variant choice, whether SKUs remain unique, whether prices differ by variant, whether weights or shipping implications change, and whether inventory should be finite or unlimited. Complex source catalogs may contain option sets, modifier pricing, option-level images, bundles, personalization fields, or app-managed stock rules that cannot be assumed to become ordinary Squarespace variant data.

| Source pattern             | Potential Squarespace issue                                                                   | Planning response                                                                                |
| -------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Many option dimensions     | Option combinations may become difficult to manage or display cleanly.                        | Sample products with the largest variant sets before approving scope.                            |
| Modifier pricing           | Pricing may not translate if the source uses add-on pricing outside a standard variant model. | Decide whether pricing becomes variant pricing, simplified options, or custom/external behavior. |
| Variant-specific inventory | Stock must connect to the correct variant record.                                             | Validate high-volume SKUs and low-stock items after Demo Migration.                              |
| Option-level images        | Source display behavior may not match Squarespace product image handling.                     | Review image assignment and product presentation for priority products.                          |
| Personalization fields     | Text inputs, gift messages, engraving, or custom files may belong to form or app behavior.    | Separate migrated product records from checkout or custom-order workflow requirements.           |

Inventory review should be practical. A merchant should not only ask whether stock migrated; they should ask whether the migrated stock is attached to the right variant, whether unlimited stock behavior is intentional, whether out-of-stock items display correctly, and whether fulfillment staff can trust the target store after launch.

### Store Pages, Collections, Navigation, and Product Discovery <a href="#store-pages-collections-navigation-and-product-discovery" id="store-pages-collections-navigation-and-product-discovery"></a>

Source platforms often separate categories, collections, menus, filters, landing pages, and merchandising rules. Squarespace can represent product discovery through Store Pages, product organization, tags, page structure, navigation, and content areas, but those concepts may not have a one-to-one relationship with the source platform.

A deep category tree from the source store may not translate well as an identical Squarespace structure. A content-led catalog may work better when high-value product groups are represented through curated pages and navigation rather than copied category depth. A store that depends on advanced filtering, faceted navigation, brand pages, compatibility charts, or marketplace-like discovery may need a target-site plan beyond data migration.

| Discovery element         | Migration meaning                                                                           | What to check                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Categories or collections | May become product grouping, Store Page structure, tags, page links, or navigation choices. | Confirm which source groupings need to remain customer-facing.                     |
| Menus and navigation      | Not all navigation is product data.                                                         | Rebuild the main navigation and footer paths intentionally.                        |
| Search and filters        | Source filtering logic may not match Squarespace behavior.                                  | Identify important filters before migration and define acceptable target behavior. |
| Landing pages             | Often include copy, media, featured products, and internal links.                           | Treat them as content and merchandising assets, not only category names.           |
| Internal links            | Product and page links may change when URLs or slugs change.                                | Review high-value links and traffic-sensitive paths.                               |

Squarespace data planning should therefore connect product organization to the way customers will browse the new site. A correct product record is not enough if the path to that product disappears.

### Customers, Contacts, Subscribers, and Address Books <a href="#customers-contacts-subscribers-and-address-books" id="customers-contacts-subscribers-and-address-books"></a>

Customer migration into Squarespace requires careful meaning translation. In many source systems, a customer record may combine login identity, buyer profile, address book, order history, marketing subscription, loyalty status, wholesale group, membership permissions, and CRM attributes. Squarespace commerce data can involve contacts, customer identity, address books, marketing preferences, subscribers, donors, and related profile meaning. These are related concepts, but they are not always the same as the source platform’s customer account model.

The migration plan should identify what the merchant actually needs from customer data. For some stores, the priority is preserving buyer names, emails, addresses, and order history. For others, the priority is preserving marketing consent, membership access, wholesale eligibility, or segmentation. Those expectations should be separated because each may require different handling.

| Customer data area | Squarespace migration meaning                                                                     | Risk if misunderstood                                                   |
| ------------------ | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Buyer identity     | Name, email, customer/contact relationship, and historical orders.                                | Customers appear duplicated, incomplete, or disconnected from history.  |
| Address data       | Shipping and billing details may be stored as contact/address information or order history.       | Fulfillment review becomes unreliable if addresses are incomplete.      |
| Marketing consent  | Subscriber status and marketing preferences may not equal customer status.                        | Merchants may overstate what can be used for campaigns after migration. |
| Account access     | Passwords, login state, membership access, and permissions may not transfer like ordinary fields. | Customers expect old access behavior that must be rebuilt or reset.     |
| Segmentation       | Loyalty groups, wholesale roles, tags, or CRM fields may not map directly.                        | Follow-up marketing and support workflows lose context.                 |

For Squarespace, the safest expectation is to preserve useful customer and order context while separately planning any account-access, membership, subscription, marketing, or CRM behavior that goes beyond standard commerce records.

### Orders, Transactions, Fulfillment, and Historical Context <a href="#orders-transactions-fulfillment-and-historical-context" id="orders-transactions-fulfillment-and-historical-context"></a>

Squarespace order data can include order totals, line items, customer information, billing and shipping addresses, fulfillment status, payment state, refunds, discounts, shipping lines, taxes, tracking data, and related transaction context. That makes historical orders useful after migration, but order data should not be confused with live operational configuration.

A migrated order record can help customer service answer questions, review past purchases, reconcile history, and preserve business context. It does not automatically configure payment gateways, tax rules, shipping methods, fulfillment routing, refund logic, invoices, email automation, or third-party operational systems. Those belong to target setup and integration review.

| Order-related record       | What it preserves                                                                                      | What it does not automatically recreate                               |
| -------------------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- |
| Historical order           | Past purchase context, totals, items, customer details, status, and addresses.                         | Live checkout, tax, payment, shipping, and fulfillment configuration. |
| Line item                  | Purchased product, SKU, quantity, price, selected variant details, and customizations where supported. | Current product availability or exact source checkout behavior.       |
| Payment state              | Historical payment context.                                                                            | Active payment gateway setup or future payment authorization flow.    |
| Fulfillment data           | Shipment status, carrier/tracking data, and delivery context where available.                          | Warehouse logic, fulfillment integrations, or live shipping rules.    |
| Refund/transaction context | Financial history and reconciliation signals.                                                          | Accounting-system continuity unless integrations are planned.         |

This separation is important for launch readiness. A merchant should verify historical order usefulness while also configuring the live store to sell correctly after the migration.

### Content, Blog Posts, Pages, Media, and SEO Data <a href="#content-blog-posts-pages-media-and-seo-data" id="content-blog-posts-pages-media-and-seo-data"></a>

Squarespace migration often involves both commerce and content. CMS Pages, Blog Posts, landing pages, images, product media, internal links, URL slugs, SEO titles, SEO descriptions, redirects, and domain behavior can influence whether the new store retains traffic and customer trust.

Not all source content belongs inside core commerce data. A product description may migrate with a product. A category description may need to become page copy or Store Page context. A blog archive may need separate content migration. A custom landing page may need manual rebuild work. Media may transfer, but formatting, cropping, image order, alt text, and internal references can still need review.

| Content or SEO element | Squarespace data meaning                                                                | Planning implication                                                               |
| ---------------------- | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Product SEO fields     | Search title, description, URL slug, and product URL influence product discoverability. | Validate priority product SEO fields and paths.                                    |
| CMS Pages              | May need to become Squarespace pages or rebuilt content sections.                       | Decide which pages are in scope and which are redesigned.                          |
| Blog Posts             | Preserve content continuity where blog traffic or education matters.                    | Review URLs, dates, authorship expectations, categories, tags, and internal links. |
| Media assets           | Product images and content images may behave differently after transfer.                | Validate image order, display, and broken references.                              |
| Redirects              | URL changes require redirect planning.                                                  | Map priority URLs before launch, especially for traffic-heavy pages.               |

A data model review should not reduce SEO to a metadata checklist. The real issue is whether customers and search engines can still reach the right content and products after the site changes.

### Integrations, Custom Fields, and Unsupported Data <a href="#integrations-custom-fields-and-unsupported-data" id="integrations-custom-fields-and-unsupported-data"></a>

Squarespace supports commerce APIs and connected services, but many source stores carry data that belongs outside standard commerce records. Examples include app-managed reviews, loyalty points, wholesale price lists, product configurators, advanced bundles, subscription rules, booking records, donation records, CRM attributes, custom checkout fields, analytics IDs, accounting references, and fulfillment-system identifiers.

These records should be classified before migration. Some can be handled through supported mapping or Add-ons. Some may require Custom Service review. Some may need to remain in an external system. Some may be excluded because the target store does not need the same operational behavior.

| Data type                | Likely handling path                                                        | Review question                                                          |
| ------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Standard commerce fields | Standard Service or supported configuration.                                | Does the field match a supported Squarespace commerce concept?           |
| Field adjustments        | Add-ons when filtering or mapping changes remain within supported behavior. | Is the adjustment supported, bounded, and clearly defined?               |
| App-owned records        | Custom Service review or external-system planning.                          | Is the source of truth inside an app, integration, or external database? |
| Custom product behavior  | Custom Service review, target rebuild, or accepted simplification.          | Does Squarespace have an equivalent native behavior?                     |
| External identifiers     | Custom mapping or integration planning.                                     | Will staff or systems need these IDs after launch?                       |

This classification prevents unsupported details from being silently treated as ordinary fields. It also helps merchants decide which data matters enough to preserve, rebuild, or connect after migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace data migration is a meaning-translation process. Products, variants, inventory, customers, contacts, orders, content, media, SEO fields, Store Pages, and integrations should be reviewed according to what they need to do in Squarespace after launch. Some records can become supported Squarespace data. Some become target setup. Some require Add-ons or Custom Service review. Some need external-system planning or accepted simplification.

The strongest Squarespace migration plans separate record transfer from site presentation, live configuration, and unsupported behavior. That separation helps the target store become usable, understandable, and operationally safe instead of merely populated with imported data.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do Squarespace data model differences matter during migration?**

They matter because Squarespace combines commerce data with hosted site structure, Store Pages, content, SEO, and configuration. A source record may need to become a product field, a page structure, a URL decision, a contact record, a target setting, or an external-system requirement.

**Can all source product options become Squarespace variants?**

Not always. Standard options may translate cleanly, but modifier pricing, deep option combinations, personalization fields, bundles, and app-managed product logic may require simplification, Add-ons, Custom Service review, or target-side rebuild work.

**Are customer records and contacts the same thing in Squarespace?**

They can overlap, but they should not be treated as identical without review. Buyer identity, address books, marketing consent, subscribers, donors, membership access, and historical order relationships may carry different meanings.

**Does migrated order data recreate live checkout operations?**

No. Historical orders can preserve purchase context, but live payment, tax, shipping, fulfillment, refund, and notification behavior must be configured in the target store or connected services.

**What should be reviewed before migrating custom or app-owned data into Squarespace?**

The source of truth, business purpose, target equivalent, required staff workflow, and service path should be reviewed. Unsupported app records, custom fields, product configurators, loyalty data, or external identifiers may need Custom Service review or external-system planning.
