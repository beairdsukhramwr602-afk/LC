# Storeden Data Model Differences

Migrating to Storeden requires more than placing records into a new admin environment. Storeden is now presented through TeamSystem Commerce, with a cloud commerce model that brings together catalog management, inventory, order handling, integrated payments, themes, apps and plug-ins, marketplace selling, logistics, API resources, and TeamSystem ecosystem connections. That operating model changes how migrated data should be interpreted.

A source store may contain products, categories, customers, orders, SEO records, app fields, marketplace identifiers, or ERP references that looked complete in the previous platform. After migration, those same values must support Storeden’s catalog structure, sales-channel readiness, order workflows, integrations, and business reporting. The data model question is therefore not only whether records arrive. The question is whether they still carry the right commercial meaning inside Storeden.

### Storeden Data Meaning at a Glance <a href="#storeden-data-meaning-at-a-glance" id="storeden-data-meaning-at-a-glance"></a>

Storeden migration planning should separate record transfer from operational interpretation. A value that appears as a product option, order note, payment label, shipping method, customer group, custom field, or marketplace reference in the source store may need different handling in Storeden.

| Data area                 | Meaning to preserve                           | Storeden interpretation to check                                                                                                  | Why the difference matters                                                                              |
| ------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Products                  | Sellable catalog identity                     | Product name, description, images, price, inventory, category placement, product visibility, and channel readiness                | A product can exist but still be difficult to sell, locate, manage, or publish correctly.               |
| Variants and options      | Shopper choice and operational SKU meaning    | Variant-like choices, attribute values, SKU relationships, stock implications, image logic, and price differences                 | Option structure affects storefront selection, fulfillment, inventory, and marketplace feeds.           |
| Categories and navigation | Product discovery and merchandising hierarchy | Category grouping, menu logic, product placement, filtering expectations, and SEO paths                                           | A migrated catalog can look complete in the back office while shopper discovery becomes weaker.         |
| Inventory                 | Availability and fulfillment confidence       | Stock quantities, SKU references, multichannel availability, logistics dependencies, and TeamSystem-connected inventory sources   | Stock meaning may depend on more than one channel or system.                                            |
| Customers                 | Account, buyer, and service identity          | Customer profile, billing/shipping history, contact details, company context, and external references                             | Customer records need to support service, order lookup, account continuity, and marketing use.          |
| Orders                    | Historical commercial context                 | Products purchased, customer relationship, totals, taxes, payment labels, shipping details, status values, and marketplace origin | Order history is useful only when staff can understand and act on it after migration.                   |
| Payments and shipping     | Historical labels versus live configuration   | Preserved order labels compared with active payment, carrier, logistics, and tax setup                                            | Migrated history does not configure future checkout behavior.                                           |
| Marketplace records       | Channel-specific selling context              | Listing identifiers, marketplace categories, channel prices, availability rules, and order origins                                | Marketplace continuity may require more than ordinary product and order migration.                      |
| Apps and API data         | Workflow ownership and integration identity   | App-owned data, API references, external IDs, automation triggers, and TeamSystem ecosystem connections                           | Connected workflows may need configuration or Custom Service review even when standard records migrate. |
| SEO and content           | Discoverability and continuity                | URLs, redirects, metadata, product descriptions, category content, image names, and theme-controlled pages                        | Search and user continuity depend on presentation and routing, not only imported records.               |

### Product Data Becomes Storeden Catalog Structure <a href="#product-data-becomes-storeden-catalog-structure" id="product-data-becomes-storeden-catalog-structure"></a>

Product records are usually the most visible part of a Storeden migration, but product meaning is broader than the product row itself. A source product may include a title, long description, short description, product code, SKU, brand, supplier, tax behavior, sale price, compare-at price, product status, category relationships, images, image alt text, options, related products, custom fields, downloadable files, marketplace attributes, and external stock references.

In Storeden, those values need to become a catalog that can be managed centrally and used commercially. TeamSystem Commerce publicly emphasizes catalog and inventory management, product images and descriptions, price management, marketplace distribution, and order operations. That means product data should be evaluated through three lenses: how the merchant manages it, how customers experience it, and how connected channels or systems use it.

| Product element               | Migration question                                                        | Storeden-facing validation signal                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Product title and description | Does the product remain clear and commercially usable?                    | The storefront product page has a readable title, complete description, and no broken formatting from the source platform. |
| Images                        | Are images attached to the correct products and usable in the storefront? | Primary and secondary images display correctly, without missing associations or incorrect product ordering.                |
| Price and sale price          | Does the migrated price still match the selling logic?                    | Regular and promotional prices are correct in product detail pages, category listings, and order tests.                    |
| SKU or product code           | Is the operational identifier preserved where needed?                     | Staff can locate products and order lines through the expected SKU or code.                                                |
| Categories                    | Does the product sit in the right merchandising structure?                | The product appears in intended categories and browsing paths.                                                             |
| Status and visibility         | Should the product be live, hidden, archived, or excluded?                | Products appear or remain hidden according to launch rules.                                                                |
| Custom fields                 | Does the field carry business meaning or only presentation detail?        | Important operational fields are retained through supported fields, Add-ons, or Custom Service review.                     |

A strong Storeden migration therefore does not treat products as isolated content blocks. Product data has to support catalog control, storefront display, inventory confidence, sales-channel readiness, and post-launch maintenance.

### Variants, Options, and Attributes Need Commercial Interpretation <a href="#variants-options-and-attributes-need-commercial-interpretation" id="variants-options-and-attributes-need-commercial-interpretation"></a>

Variant and option data often changes meaning during migration. In a source store, size, color, material, bundle selection, engraving text, subscription interval, delivery option, or B2B package quantity may be stored as variants, product options, attributes, line-item properties, app fields, or custom product logic. Storeden planning needs to determine which of those values are true purchasable choices and which are descriptive or workflow-related information.

The difference matters because variants are not only storefront choices. They can affect SKU identity, stock quantity, pricing, images, shipping weight, tax behavior, marketplace availability, and order interpretation. If a source option is moved as plain descriptive text when it actually controls SKU or stock, the catalog may look acceptable while fulfillment becomes unreliable.

| Source pattern                     | Storeden interpretation to consider                                                | Planning implication                                                       |
| ---------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Size or color as a variant         | Purchasable choice tied to product selection                                       | Include representative multi-option products in Demo Migration validation. |
| Material or finish as an attribute | Descriptive value or variant-level choice depending on business use                | Decide whether it affects SKU, price, inventory, or only presentation.     |
| Bundle or kit logic                | May require Storeden configuration, app support, or Custom Service review          | Do not assume bundle behavior transfers as ordinary product data.          |
| Personalization text               | May be a custom field, line-item note, app value, or unsupported checkout behavior | Confirm whether it needs to appear in orders after launch.                 |
| Marketplace-specific attributes    | Channel data rather than standard catalog data                                     | Review marketplace feeds and channel listings separately.                  |
| ERP-linked SKU references          | Integration identity rather than visible storefront content                        | Preserve mapping only if external systems still depend on it.              |

The best migration samples for this area are not simple products. They are products where options affect price, stock, images, order lines, or marketplace publication. Those records expose whether the Storeden data model is preserving commercial behavior instead of only visible labels.

### Categories, Navigation, and Product Discovery Are Not the Same Thing <a href="#categories-navigation-and-product-discovery-are-not-the-same-thing" id="categories-navigation-and-product-discovery-are-not-the-same-thing"></a>

Category data is often underestimated because it appears simple. A source category can represent a menu item, SEO landing page, product grouping, marketplace mapping, promotion group, collection, filter condition, or reporting segment. Storeden catalog planning should separate category hierarchy from storefront discovery.

A category may migrate as a product grouping, but that does not guarantee the storefront has the same navigation experience. Menus, theme layout, filters, category descriptions, product sorting, and internal links may need separate review. Storeden’s public positioning around catalog management and multichannel commerce makes this distinction important: product organization needs to serve both back-office maintenance and sales-channel presentation.

| Discovery element     | What can change after migration                                           | What to check                                                                   |
| --------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Category hierarchy    | Parent and child relationships may not match the old menu exactly.        | Key categories have the intended hierarchy and product assignment.              |
| Menu placement        | A category can exist without appearing in the same navigation path.       | Primary shopper paths are manually reviewed in the target storefront.           |
| Category descriptions | Source SEO copy may not transfer into the same page area.                 | Important category text remains visible and properly formatted.                 |
| Filters and facets    | Source filter logic may depend on attributes or apps.                     | High-value filters are available, useful, and based on reliable data.           |
| Product sorting       | Sorting behavior may differ from the previous platform.                   | Top categories show products in an acceptable default order.                    |
| Channel categories    | Marketplace category logic may not be identical to storefront categories. | Marketplace preparation is reviewed separately from website category structure. |

The practical issue is that a complete category import can still fail the shopper journey. Storeden validation should include storefront browsing, not only back-office category counts.

### Inventory Data Is a Stock Signal, Not Always the Whole Stock Workflow <a href="#inventory-data-is-a-stock-signal-not-always-the-whole-stock-workflow" id="inventory-data-is-a-stock-signal-not-always-the-whole-stock-workflow"></a>

Inventory values may look straightforward, but their meaning depends on how the source store operated. Some merchants use simple stock quantities. Others depend on warehouse logic, reserved stock, marketplace availability, supplier feeds, ERP updates, bundle stock, preorder rules, or manual adjustments.

Storeden’s catalog and inventory positioning means stock values should be treated as launch-critical, but not every inventory workflow is a migration record. The migration can preserve stock values or SKU references, while ongoing stock updates may depend on Storeden settings, marketplace channels, logistics integrations, API workflows, or TeamSystem ecosystem connections.

| Inventory question                                  | Why it matters                                                         | Recommended handling                                                              |
| --------------------------------------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Does the source use one stock value per product?    | Simple stores are easier to validate after migration.                  | Compare product and variant-level stock against source samples.                   |
| Does stock vary by option or SKU?                   | Option-level stock errors can oversell or hide sellable items.         | Validate products where variants control availability.                            |
| Does an external system own stock?                  | Migrated stock may become stale if the connection is not rebuilt.      | Identify ERP, warehouse, supplier, or marketplace stock owners before acceptance. |
| Are some products non-stock or service items?       | Forcing stock logic onto non-stock items can distort catalog behavior. | Confirm product types and stock settings before launch.                           |
| Do marketplaces need channel-specific availability? | Website stock and marketplace stock may not be the same business rule. | Separate channel availability checks from standard catalog checks.                |

Inventory validation should therefore be evidence-based. A merchant should not accept the migration because the total number of products looks right. They should check whether the products that matter most can be sold, hidden, fulfilled, or synchronized as intended.

### Customer and Account Data Carries Multiple Roles <a href="#customer-and-account-data-carries-multiple-roles" id="customer-and-account-data-carries-multiple-roles"></a>

Customer records may represent buyers, account holders, newsletter contacts, company accounts, B2B purchasing contacts, billing recipients, shipping recipients, marketplace customers, CRM records, or TeamSystem-connected identities. Treating all of these as one flat customer list can weaken the target store’s usefulness.

Storeden migration planning should define what customer continuity means for the merchant. Some stores mainly need past order lookup. Others need account access, customer segmentation, B2B relationships, marketing eligibility, invoice references, or integration continuity.

| Customer-related value         | Data-model question                                               | Storeden migration concern                                                              |
| ------------------------------ | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Name and email                 | Is the customer a real account, buyer record, or contact?         | Duplicate or partial records may affect support and marketing use.                      |
| Billing and shipping addresses | Are addresses complete and tied to the right customer or order?   | Staff need addresses for historical order review and customer service.                  |
| Customer group or segment      | Is the value descriptive, pricing-related, or permission-related? | Pricing and access behavior may need target configuration or Custom Service review.     |
| Company or tax data            | Is the merchant using B2B or invoice workflows?                   | Company information may matter for accounting and order history.                        |
| External IDs                   | Do CRM, ERP, accounting, or marketing tools rely on the ID?       | Preserve or map identifiers when they remain operationally required.                    |
| Consent and marketing data     | Does the source contain legally sensitive preference information? | Do not treat contact migration as permission to reuse marketing records without review. |

A successful customer migration should be judged by whether staff can recognize, serve, and segment customers correctly after launch. It should not be judged only by customer counts.

### Orders Preserve History, Not Future Checkout Setup <a href="#orders-preserve-history-not-future-checkout-setup" id="orders-preserve-history-not-future-checkout-setup"></a>

Order migration is about historical readability. A migrated order may include order number, date, customer information, billing address, shipping address, product lines, variant labels, quantities, prices, discounts, taxes, payment labels, shipping method, tracking details, marketplace origin, invoice references, refund notes, and status values.

Those values need to remain understandable in Storeden, but they should not be confused with live operational setup. A historical payment label does not configure future payment processing. A historical shipping method does not prove that logistics rules, carrier rates, tracking flows, or fulfillment processes are active in the target environment.

| Historical order field | Meaning to preserve                   | What it does not prove                                           |
| ---------------------- | ------------------------------------- | ---------------------------------------------------------------- |
| Payment method label   | How the customer paid in the past     | Future payment gateway or TS Pay setup is active.                |
| Shipping method        | How the old order was delivered       | Future delivery rules and logistics integrations are configured. |
| Tax amount             | What was charged historically         | Storeden tax settings are correct for new orders.                |
| Discount line          | What promotion affected the old order | Future coupon or campaign rules behave the same.                 |
| Order status           | Past operational state                | New fulfillment workflow follows the same states.                |
| Marketplace origin     | Where the order came from             | Marketplace listings and synchronization are active.             |

This separation is essential for acceptance. Historical orders should be validated for readability, support continuity, and reporting context. Future checkout, payment, tax, shipping, fulfillment, and marketplace workflows need separate target configuration and live testing.

### Marketplace and Multichannel Records Require Separate Scope Review <a href="#marketplace-and-multichannel-records-require-separate-scope-review" id="marketplace-and-multichannel-records-require-separate-scope-review"></a>

Storeden’s public positioning emphasizes multichannel selling and marketplace distribution. That is a strength, but it also changes migration meaning. Marketplace data is not always ordinary product data. It may include listing IDs, channel-specific titles, marketplace categories, feed attributes, availability rules, marketplace prices, seller references, order origins, and synchronization status.

If a source store depends heavily on marketplaces, migration planning should separate website catalog migration from channel continuity. Product records may migrate successfully while marketplace listings, channel mappings, and feed rules still require configuration or review.

| Marketplace-related data | Why it is sensitive                                              | Scope decision                                                               |
| ------------------------ | ---------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Listing identifiers      | They connect a product to an existing channel listing.           | Review whether they are required and supported in the target workflow.       |
| Channel categories       | Marketplace taxonomy may differ from web-store categories.       | Validate marketplace category mapping separately.                            |
| Channel price or stock   | Marketplace selling rules may differ from website selling rules. | Decide which system owns price and stock after launch.                       |
| Marketplace order origin | Staff may need origin context for support and reporting.         | Preserve origin where available and useful.                                  |
| Feed attributes          | Attributes may be app-owned or channel-specific.                 | Use Add-ons or Custom Service review where standard fields are insufficient. |

This is where Storeden migrations can become more than a normal catalog move. A merchant migrating into Storeden may be doing so specifically because they want better multichannel operations. The migration should protect that future operating model, not only the web-store surface.

### Apps, API Data, and TeamSystem Connections Need Ownership Clarity <a href="#apps-api-data-and-teamsystem-connections-need-ownership-clarity" id="apps-api-data-and-teamsystem-connections-need-ownership-clarity"></a>

Storeden supports apps, plug-ins, API/developer resources, and TeamSystem ecosystem connections. Those capabilities can extend the store, but they also create ownership questions. Some data belongs to standard commerce records. Some belongs to apps, integrations, external systems, or automation workflows.

Before migration scope is accepted, Storeden planning should identify which values must be migrated as standard data, which can be recreated by configuration, which require Add-ons, and which need Custom Service review. This distinction prevents the common problem where visible products and orders are migrated but the operational workflows around them are not.

| Data owner            | Example                                                                 | Recommended interpretation                                                     |
| --------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Store commerce record | Product, customer, category, order                                      | Standard migration may cover the main entity when supported.                   |
| App or plug-in        | Reviews, custom product options, feeds, loyalty data, marketplace tools | Review whether supported Add-ons exist or whether custom extraction is needed. |
| External system       | ERP, accounting, warehouse, CRM, TeamSystem-connected workflow          | Preserve identifiers and confirm integration responsibility.                   |
| API workflow          | Automated import, update, or synchronization logic                      | Treat logic separately from stored records.                                    |
| Theme or template     | Layout, presentation blocks, custom storefront behavior                 | Do not assume design behavior migrates with data.                              |

Custom Service should be reviewed when required data is not available through standard structures, when unsupported app/plugin data is business-critical, when external IDs must be preserved, or when source logic needs transformation rather than ordinary mapping.

### SEO, URLs, and Content Data Must Support Discoverability <a href="#seo-urls-and-content-data-must-support-discoverability" id="seo-urls-and-content-data-must-support-discoverability"></a>

SEO and content data can be scattered across product records, categories, pages, blog content, theme blocks, redirects, metadata fields, image data, and external marketing tools. Storeden migration planning should decide which content is data, which is design, and which is SEO continuity work.

Product descriptions and category copy may be migrated as content, but page layout, theme sections, menus, structured content blocks, and old URL behavior may need separate handling. URL redirects are especially important because a product or category can migrate correctly while old customer and search-engine paths break.

| SEO or content area | Migration concern                                          | Acceptance signal                                                   |
| ------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------- |
| Product URLs        | Source URL paths may not match target routing.             | High-value products have redirect coverage or accepted URL changes. |
| Category URLs       | Category hierarchy and slugs may change.                   | Important category landing pages are reachable and mapped.          |
| Metadata            | Titles and descriptions may not map one-to-one.            | Priority products and categories retain useful SEO metadata.        |
| Rich content        | Page-builder or theme content may not be standard data.    | Important content is migrated, rebuilt, or explicitly excluded.     |
| Images              | Image files, naming, ordering, and alt context may change. | Main images render correctly and support product understanding.     |
| Internal links      | Old links may point to retired URLs.                       | Critical internal links are checked after migration.                |

Storeden data-model review should therefore include both back-office data and the public storefront. SEO continuity is not just a field-mapping exercise; it is a routing, content, and presentation review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden data-model differences are created by the relationship between catalog structure, multichannel selling, inventory management, order history, marketplace readiness, apps, API resources, logistics, and TeamSystem ecosystem connections. A migration can move records successfully but still fail if those records no longer support how the merchant sells, fulfills, reports, or connects systems.

The strongest Storeden migration plan treats product, customer, order, inventory, marketplace, SEO, and integration data as business meanings that need target interpretation. That approach helps merchants validate usable commerce continuity instead of relying on record counts alone.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is product data more than product import in a Storeden migration?**

Product data must support storefront presentation, category placement, inventory confidence, pricing, images, channel readiness, and staff management. A product that imports successfully may still need review if variants, category placement, visibility, or marketplace attributes do not carry the same meaning.

**Do migrated orders configure payment and shipping in Storeden?**

No. Migrated orders preserve historical payment and shipping information for reference. Future checkout, payment processing, shipping rules, logistics, tax behavior, and fulfillment workflows require separate Storeden configuration and testing.

**When should marketplace data be reviewed separately?**

Marketplace data should be reviewed separately when the source store uses channel-specific listings, prices, categories, attributes, stock rules, order origins, or marketplace identifiers. Those values may not behave like ordinary web-store product fields.

**How should custom fields and external IDs be handled?**

Custom fields and external IDs should be reviewed based on business use. If they support ERP, accounting, CRM, logistics, marketplace synchronization, or reporting, they may need mapping, Add-ons, or Custom Service review rather than simple field transfer.

**What is the most important validation principle for Storeden data differences?**

Validate by business meaning. Products, customers, orders, inventory, SEO records, and integration values should be checked for how they work inside Storeden, not only whether the record counts match the source store.
