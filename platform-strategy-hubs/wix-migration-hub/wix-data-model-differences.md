# Wix Data Model Differences

Wix migration planning should treat the Target Platform as a hosted site-builder commerce environment, not only as a destination for store records. Products, collections, inventory, customer-related data, orders, content pages, Blog Posts, CMS data, apps, and site URLs can all affect how the migrated store works after launch. A record that looks simple in the source store may need a different interpretation when it becomes part of Wix Stores, Wix site content, Wix CMS, Wix Members, CRM/contact records, Wix apps, Velo logic, or external-system workflows.

The most important data-model question is not whether a record can appear in Wix. The better question is whether the record keeps its business meaning once Wix controls the storefront, product page structure, hosted checkout, site design, apps, URLs, and live configuration. A product with variants, a category page with SEO value, a customer account with member access, or a custom checkout field may all require different handling from a basic data transfer.

### Wix Data Meaning Starts With the Site and Store Together <a href="#wix-data-meaning-starts-with-the-site-and-store-together" id="wix-data-meaning-starts-with-the-site-and-store-together"></a>

Wix data is shaped by the relationship between the website and the store. Some Target Platforms are planned mainly through catalog and checkout structures. Wix often needs a wider site-aware view because commerce records sit inside a built website with pages, sections, navigation, media, apps, CMS collections, member experiences, and search-sensitive URLs.

That does not mean every Wix migration must rebuild the entire site. It means data should be interpreted through the Wix environment the merchant actually plans to launch. If Wix is only used for a small product catalog, the data model can be comparatively simple. If the source store depends on content-rich landing pages, member-only areas, custom forms, app-managed records, or Velo logic, the migration plan should classify those elements before deciding what belongs in ordinary migration scope.

| Source-store meaning       | Wix interpretation question                                                                               | Migration implication                                                                                                  |
| -------------------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Product catalog            | Should the record become a Wix Stores product, a service/app record, a CMS-driven item, or excluded data? | Store products should not be forced to carry unrelated service, booking, event, donation, or custom database behavior. |
| Category or collection     | Is it a product grouping, site navigation path, SEO landing page, or campaign page?                       | Product collections and site pages may need separate handling.                                                         |
| Customer account           | Is the source record a buyer, contact, subscriber, member, or app participant?                            | Customer, contact, and member expectations should be separated.                                                        |
| Order history              | Is the record needed for reference, reporting, support, or live fulfillment behavior?                     | Historical order readability should not be confused with live checkout setup.                                          |
| Content page               | Should it migrate as content, be rebuilt in Wix, redirected, or retired?                                  | CMS Pages and Blog Posts need site-level decisions, not only data-level mapping.                                       |
| Custom field or app record | Is it supported data, Add-on scope, Custom Service scope, target setup, or excluded expectation?          | Unsupported or app-owned data should be classified before Full Migration.                                              |

This site-and-store relationship is the main data-model difference for Wix. The store is not isolated from the website experience.

### Products, Options, Choices, and Variants Need Precise Classification <a href="#products-options-choices-and-variants-need-precise-classification" id="products-options-choices-and-variants-need-precise-classification"></a>

Wix Stores organizes a catalog through products and collections, while product choices can involve options, choices, and variants. Wix’s catalog terminology matters because a source platform may use different words for similar-looking structures. A source “variant” may be a true sellable combination, a visual option, a personalization field, a bundle rule, or an app-generated choice.

In Wix, variants can carry business meaning beyond display. A variant may need its own SKU, price, weight, or inventory behavior. If a source product choice affects stock, fulfillment, media, or pricing, it should not be treated as decorative option text. If the source choice is only a custom note, gift message, engraving input, or file upload, it may not belong in the same structure as a Wix product variant.

| Source pattern                                                     | Wix data-model decision                                                           | Planning risk                                                                                           |
| ------------------------------------------------------------------ | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Size, color, style, material, or package                           | Review as product options, choices, and possible variants.                        | The shopper-facing choice may appear, but SKU, price, stock, or media meaning may be lost.              |
| Variant-specific SKU, price, weight, or stock                      | Preserve as variant-level business meaning where supported.                       | Parent-level product data may hide operational differences.                                             |
| Paid add-on or personalization field                               | Classify as supported field, app behavior, target setup, or Custom Service scope. | Order detail and fulfillment instructions may not remain usable.                                        |
| Bundle, kit, or composite product                                  | Review for supported simplification, app dependency, or custom handling.          | Component logic may not become ordinary Wix product data.                                               |
| Digital, service, booking, event, donation, or pricing-plan record | Decide whether Wix Stores or another Wix business app owns the target behavior.   | Non-store commerce records can be forced into the wrong data model.                                     |
| External catalog record                                            | Review integration ownership and target catalog behavior.                         | The merchant may need synchronization or custom catalog planning rather than one-time record migration. |

Product data should be reviewed through how shoppers choose items and how the merchant manages those choices after launch. The visual product page, the product data record, the inventory record, and the order line item all need consistent meaning.

### Collections and Navigation Are Related but Not Identical <a href="#collections-and-navigation-are-related-but-not-identical" id="collections-and-navigation-are-related-but-not-identical"></a>

A source category tree can have many jobs. It may organize products in the admin, create public category pages, define menu paths, support filters, carry SEO metadata, or represent campaign groups. Wix collections can organize products, but Wix site navigation, product galleries, menus, landing pages, and redirects may require separate decisions.

This distinction is important because a source category can migrate as a collection while the customer-facing browsing path still needs Wix site work. A merchant may believe categories are preserved because product grouping exists, but the actual browse experience may depend on page layout, menu structure, collection display, product galleries, filters, and site search behavior.

| Source category role         | Wix planning direction                                                            | What should be protected                                           |
| ---------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Admin grouping               | Product collection or internal organization.                                      | Clean product organization without unnecessary storefront clutter. |
| Public category page         | Collection display, Wix page, product gallery, or redirect target.                | Customer browsing and high-value landing paths.                    |
| SEO landing page             | Page rebuild, metadata review, redirect plan, or accepted retirement.             | Organic visibility, backlinks, internal links, and search intent.  |
| Filterable product attribute | Product option, product data field, app-supported filter, or accepted limitation. | Shopper comparison and discovery behavior.                         |
| Promotional group            | Collection, campaign page, menu area, or manual site section.                     | Merchandising context, seasonal display, and campaign continuity.  |

The migration should not assume that preserving product-to-collection assignment is enough. Wix site structure should be reviewed wherever category meaning affects discovery, SEO, or merchandising.

### Inventory Is Variant-Aware and Must Match Selling Meaning <a href="#inventory-is-variant-aware-and-must-match-selling-meaning" id="inventory-is-variant-aware-and-must-match-selling-meaning"></a>

Inventory planning for Wix depends on how sellable products and variants are represented. A source store may store stock at product level, variant level, warehouse level, channel level, or through external inventory systems. Wix migration should identify which stock values are meaningful after products and variants are interpreted in the Wix catalog.

A basic product with one stock value may be straightforward. A variant-bearing product is more sensitive. If each variant has a different SKU or quantity, stock should be reviewed at the variant level where supported. If the source platform uses warehouses, marketplaces, dropshipping apps, or external inventory ownership, the migration plan should decide whether Wix should receive stock values, whether another system remains the source of truth, or whether inventory setup belongs outside ordinary migration output.

| Inventory pattern                          | Wix data meaning                                             | Review focus                                                                        |
| ------------------------------------------ | ------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| Product-level stock                        | Inventory attached to a simple product.                      | Confirm quantity, visibility, and sellable status.                                  |
| Variant-level stock                        | Inventory tied to choices such as size or color.             | Confirm stock follows the correct variant, not just the parent product.             |
| External inventory source                  | Integration-dependent stock ownership.                       | Decide whether migration should move a snapshot or preserve integration references. |
| Backorder, preorder, or availability flags | Target-side setup, app behavior, or accepted limitation.     | Avoid implying that source availability logic automatically transfers.              |
| Channel-specific stock                     | Wix storefront, marketplace, POS, or app-dependent behavior. | Clarify which channel Wix should represent after launch.                            |

Inventory should be accepted only when stock values support the same selling meaning expected in Wix. A correct total count is not enough when variant-level or channel-specific behavior matters.

### Customers, Contacts, Members, and App Participants Are Different Meanings <a href="#customers-contacts-members-and-app-participants-are-different-meanings" id="customers-contacts-members-and-app-participants-are-different-meanings"></a>

Customer-related data is one of the easiest areas to oversimplify in a Wix migration. A source platform may use “customer” to mean a buyer with order history, a registered account holder, a newsletter subscriber, a loyalty participant, a booking client, a member with restricted access, a wholesale buyer, or a CRM contact. Wix can involve customers, contacts, site members, app records, CRM-style fields, and external profiles.

The migration plan should classify the source meaning before selecting the target path. A buyer with orders may need contact and order association. A site account may involve member access and login expectations. A subscriber may require marketing and consent review. A membership, booking, event, restaurant, donation, loyalty, or pricing-plan participant may belong to a Wix app or external system rather than ordinary store customer data.

| Source customer meaning  | Wix-related interpretation                                                             | Data-model concern                                                                                    |
| ------------------------ | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Buyer with order history | Customer/contact context tied to historical orders.                                    | Order readability and identity matching.                                                              |
| Registered account       | Member-related planning where relevant.                                                | Login, password, member-page access, and account behavior may not transfer as ordinary customer data. |
| Marketing subscriber     | Contact and consent-related data.                                                      | Subscription status, segmentation, and compliance-sensitive fields require careful review.            |
| Wholesale or B2B buyer   | Contact, member, app-supported group, pricing rule, or Custom Service scope.           | Pricing, access, approval, and purchasing rules may not be standard Wix store records.                |
| App participant          | Booking, event, membership, pricing plan, loyalty, restaurant, or donation app record. | App data may be separate from normal store customer migration.                                        |
| External profile         | CRM, ERP, support, loyalty, or marketplace identity.                                   | External identifiers may need mapping or Custom Service review.                                       |

The practical test is whether the migrated customer-related data supports the expected use after launch. Support lookup, order history, marketing segmentation, member access, and app participation are different outcomes.

### Orders Preserve Historical Context, Not Live Wix Configuration <a href="#orders-preserve-historical-context-not-live-wix-configuration" id="orders-preserve-historical-context-not-live-wix-configuration"></a>

Migrated orders should be interpreted as historical records. They may preserve useful context for staff, customer service, reporting, and business continuity, but they do not automatically recreate live checkout behavior, payment provider setup, shipping rules, tax configuration, discount logic, fulfillment services, notifications, or app workflows.

Wix order data can include purchased items, payment details, shipping information, fulfillment status, invoices, transactions, refunds, and order settings in the live environment. For migration planning, the key distinction is between readable history and operational configuration. A migrated historical order may be useful even if the merchant still needs to configure Wix Payments, third-party payment providers, shipping and delivery settings, tax rules, notification behavior, and fulfillment workflows separately.

| Order element                            | Migration meaning                                                | Boundary to protect                                                        |
| ---------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Line items                               | Historical record of purchased products, quantities, and prices. | Product/variant references should remain understandable.                   |
| Payment labels or transaction references | Historical context for support and reconciliation.               | Live payment processing must be configured and tested in Wix.              |
| Fulfillment status                       | Reference for past order handling.                               | Future shipping, delivery, and fulfillment rules require target setup.     |
| Discounts and tax amounts                | Historical pricing context.                                      | Future discount and tax behavior must be configured separately.            |
| Refunds and adjustments                  | Exception history for support and reporting.                     | Refund processing behavior in the new store still needs target validation. |
| External order IDs                       | Integration or reporting continuity.                             | External identifiers may need mapping or Custom Service review.            |

This distinction prevents a common data-model error: treating order migration as proof that the live store is ready to sell.

### Wix Site Content, CMS Data, Blog Posts, and Media Need Separate Ownership <a href="#wix-site-content-cms-data-blog-posts-and-media-need-separate-ownership" id="wix-site-content-cms-data-blog-posts-and-media-need-separate-ownership"></a>

Wix can include ordinary pages, Blog Posts, CMS collections, media, forms, custom pages, app pages, member-only content, and dynamic content. A source store may contain similar data, but the target meaning can vary. Some content can be migrated as CMS Pages or Blog Posts. Some content needs manual site rebuilding. Some records may belong to Wix CMS collections or external database connections. Some app-generated or code-driven content may require custom review.

Wix CMS data deserves special attention because it can define structured data collections, data items, collection permissions, and external database connections. A content-rich source store may contain page-builder layouts, custom post types, product guides, landing pages, forms, directories, or support resources. These should not be collapsed into the same planning bucket as product descriptions.

| Source content          | Wix target interpretation                                                          | Planning question                                                          |
| ----------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Static page             | CMS Page, Wix site page, manually rebuilt page, redirect, or exclusion.            | Is the content data, design, SEO asset, or site implementation?            |
| Blog Post               | Wix Blog content or accepted content migration scope.                              | Are dates, authors, categories, tags, media, and internal links important? |
| CMS/custom post type    | Wix CMS collection, external database, manual rebuild, or Custom Service.          | Is the content structured, dynamic, permission-based, or app-driven?       |
| Media library           | Product media, page media, blog media, gallery media, or manually uploaded assets. | Are images tied to products, pages, blog content, or custom layouts?       |
| Forms or member content | Wix Forms, Members, app setup, or custom implementation.                           | Is the source behavior data, access control, or business process?          |

For Wix, content migration should be planned with site experience in mind. A page can exist as text but still fail if the design, internal links, media, dynamic behavior, or permissions are not rebuilt appropriately.

### URLs, SEO Fields, and Redirects Are Site-Level Data Decisions <a href="#urls-seo-fields-and-redirects-are-site-level-data-decisions" id="urls-seo-fields-and-redirects-are-site-level-data-decisions"></a>

Wix URL and SEO planning should not be left until the end of migration. Source product URLs, category URLs, CMS Pages, Blog Posts, media references, landing pages, and internal links may all affect traffic continuity. Because Wix is a hosted website environment, URL behavior depends on the target site structure, published pages, domains, redirects, multilingual settings, and app-generated paths.

A source platform may allow URL formats that Wix does not reproduce exactly. The goal is not always exact URL parity. The goal is a controlled decision about which URLs should be preserved, redirected, rebuilt, or retired. This is especially important for stores with organic traffic, backlinks, content campaigns, or product/category landing pages.

| Source URL type   | Wix handling decision                                                         | SEO continuity risk                                                 |
| ----------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Product URL       | Product page path, redirect, metadata review, or accepted change.             | Product traffic may land on the wrong page or a missing page.       |
| Category URL      | Collection display, landing page, redirect, or menu change.                   | Category-level ranking and browsing paths may weaken.               |
| CMS Page URL      | Wix page rebuild, content migration, redirect, or retirement.                 | Informational pages may disappear from search or navigation.        |
| Blog Post URL     | Wix Blog path, redirect, metadata review, or content migration scope.         | Blog traffic and internal links may break.                          |
| Dynamic page URL  | CMS/dynamic-page setup, external database behavior, or custom implementation. | Structured content may not preserve its source routing logic.       |
| App-generated URL | App setup, manual recreation, or accepted exclusion.                          | Booking, event, membership, or custom app pages may not carry over. |

SEO fields should be reviewed alongside URLs. Titles, descriptions, headings, image alt text, internal links, canonical behavior, structured data expectations, and indexed page priorities may all require target-side decisions.

### Apps, Velo, Service Plugins, and External Systems Change Data Ownership <a href="#apps-velo-service-plugins-and-external-systems-change-data-ownership" id="apps-velo-service-plugins-and-external-systems-change-data-ownership"></a>

Wix can be extended through apps, Velo/API development, service plugins, embedded scripts, CMS data, and external systems. These capabilities make Wix flexible, but they also create migration scope boundaries. App-managed data is not automatically the same as standard Wix Stores data. Velo logic may connect site behavior to collections, APIs, forms, payment flows, or external systems. Service plugins can influence custom catalog behavior, cart and checkout validation, shipping rates, payment services, and other live commerce behavior.

Before migration, any app, code, or integration that owns business-critical data should be classified. The classification should say whether the requirement is standard migration scope, Add-ons scope, Custom Service scope, target-side setup, external-system work, or an accepted exclusion.

| Dependency                                         | Data ownership concern                                                                     | Likely planning path                                                                                |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| Wix app                                            | Records may belong to the app, not to standard store data.                                 | Verify exportability, target setup, and accepted migration scope.                                   |
| Velo/API logic                                     | Business behavior may depend on code, collections, or external calls.                      | Treat as implementation or Custom Service review when data/logic must be preserved.                 |
| Service plugin                                     | Live catalog, cart, checkout, payment, shipping, or validation behavior may be customized. | Separate migration data from target behavior and testing.                                           |
| External database                                  | Wix may query external data as collections through an adapter.                             | Decide whether migration should move records, preserve references, or rebuild integration behavior. |
| ERP, CRM, PIM, WMS, loyalty, or marketplace system | Identifiers and statuses may drive downstream workflows.                                   | Preserve or map required references where feasible, often through Custom Service review.            |

This area is where many Wix projects move beyond ordinary data transfer. If the source store or target Wix site depends on custom logic, the project should not treat those requirements as simple product, customer, or order fields.

### Wix Data Scope Should Be Judged by Business Use <a href="#wix-data-scope-should-be-judged-by-business-use" id="wix-data-scope-should-be-judged-by-business-use"></a>

Wix data-model review should end with a practical decision: which migrated records will help the merchant operate the target site and store, and which expectations belong elsewhere? A product should support shopping and management. A variant should preserve price, SKU, stock, or media meaning when those details matter. A collection should support product discovery. A customer-related record should support support, contact, member, or app use as intended. An order should preserve readable history. A content record should support site experience and SEO continuity. A custom field should have a clear destination or be excluded intentionally.

Entity Points can help plan selected entity volume, but they do not prove that every Wix-specific field, app record, CMS item, URL, or custom behavior has a supported target destination. Add-ons can help with bounded supported filtering, mapping, or configuration. Custom Service is the right review path when the requirement involves unsupported records, app-owned data, Velo/API behavior, external identifiers, bespoke transformation, custom catalog behavior, or other non-standard migration logic.

The best Wix data scope is not the broadest possible transfer. It is the scope that preserves operational value while separating migrated records from Wix setup, site implementation, app configuration, Add-ons, Custom Service, and accepted exclusions.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix data model differences matter because migrated records enter a hosted site-builder commerce environment, not only a product database. Products, options, choices, variants, collections, inventory, orders, contacts, members, CMS content, Blog Posts, URLs, apps, Velo logic, service plugins, and external systems all require business-meaning review before migration scope is accepted.

A strong Wix migration plan preserves the data that can support the target site and store while separating standard migration output from Wix setup, content rebuilding, app configuration, Add-ons, Custom Service, external-system work, and intentional exclusions.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why does Wix data-model planning include site content and URLs?**

Because Wix combines website building, store management, content, apps, and hosted URL behavior. Product data may migrate cleanly while pages, collections, redirects, Blog Posts, CMS content, or dynamic URLs still need separate planning.

**Are Wix product options and variants the same as source-platform variants?**

Not always. Wix product options, choices, and variants should be reviewed according to business meaning. A source choice may affect price, SKU, stock, media, personalization, or app logic, and each case may need different handling.

**Can customer accounts migrate directly into Wix Members?**

Customer, contact, and member data should be classified separately. A buyer with order history is not automatically the same as a site member with login access, permissions, or member-only content expectations.

**Does migrated order history prove Wix checkout is ready?**

No. Historical orders can preserve useful reference data, but live payment, tax, shipping, discount, checkout, notification, and fulfillment behavior must be configured and tested in Wix.

**When does Wix data require Custom Service review?**

Custom Service should be considered when the requirement involves unsupported app data, Velo/API logic, custom catalog behavior, external identifiers, bespoke transformations, external database relationships, or source data that cannot fit supported Wix migration behavior.
