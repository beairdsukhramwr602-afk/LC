# Wix Data Model Differences

A migration to Wix changes more than where store records are stored. The Target Platform interprets products, options, variants, collections, contacts, members, orders, pages, apps, and SEO values through Wix’s hosted website and commerce structure.

For a simple store, this translation may feel straightforward: products become Wix store products, customers become customer or contact records, and orders become historical order records. For a more complex store, the same migration can involve decisions about product options, choices, variants, modifiers, collections, filters, customer accounts, Wix Members, Wix Blog, Wix Bookings, Wix Restaurants, Wix Events, apps, Velo by Wix, custom API behavior, and URL continuity.

The goal is not only to move data into Wix. The migrated result should preserve the business meaning that shoppers, store managers, marketers, and connected systems need after launch.

### Why Wix Data Meaning Changes After Migration <a href="#why-wix-data-meaning-changes-after-migration" id="why-wix-data-meaning-changes-after-migration"></a>

Wix combines website building, storefront design, commerce management, apps, member experiences, content, and developer extension points in a hosted SaaS environment. That means migrated records must fit Wix’s platform-managed structures rather than the database, extension, or custom-code model of the Source Platform.

A source store may treat product options, customer groups, checkout fields, custom order metadata, blog content, page layouts, bookings, subscriptions, or app data as ordinary database records. Wix may represent the same business meaning through store products, variants, collections, contacts, members, business apps, CMS collections, Velo code, third-party apps, or configuration that sits outside the migration dataset.

| Source-store meaning                | How it may need to be interpreted in Wix                                                          | Migration planning concern                                                 |
| ----------------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Product with custom option logic    | Product options, choices, variants, modifiers, or accepted target simplification                  | Buying choices must remain understandable and usable.                      |
| Category tree or layered navigation | Collections, menus, filters, site pages, or storefront layout decisions                           | Discovery paths may change even when product data migrates.                |
| Customer account or group           | Customer record, contact, member, pricing context, or app-supported structure                     | Access, segmentation, and login expectations need separate review.         |
| Historical order record             | Wix order history with customer, product, payment, tax, shipping, status, and fulfillment context | Order readability does not prove live checkout configuration.              |
| Blog or content page                | Wix Blog Posts, CMS Pages, site pages, sections, or manually rebuilt design content               | Content meaning may depend on layout, navigation, and SEO values.          |
| Extension-owned data                | Wix app data, Velo logic, API integration, or Custom Service scope                                | Unsupported app data should not be assumed to migrate as standard records. |
| Custom checkout or workflow field   | Target configuration, app capability, Velo/API work, or accepted exclusion                        | Custom behavior must be separated from data transfer.                      |

### Product Data Becomes Wix Store Product Structure <a href="#product-data-becomes-wix-store-product-structure" id="product-data-becomes-wix-store-product-structure"></a>

Product data in Wix is not only a product name and price. A migrated product may need to carry product type, description, images, SKU, inventory, price, sale price, weight, visibility, ribbons or labels, SEO values, collections, options, choices, variants, modifiers, subscriptions, digital-file context, and storefront display expectations.

Simple products are usually easier to interpret. The risk increases when the Source Platform uses custom product types, unusual option logic, bundled products, add-on choices, subscription behavior, downloadable products, custom pricing rules, or app-owned product information.

#### Product types need target meaning <a href="#product-types-need-target-meaning" id="product-types-need-target-meaning"></a>

Wix can support different selling models through Wix Stores and other Wix business apps. A source product may represent a physical product, a digital item, a booking, a service, a restaurant item, an event ticket, a subscription, a membership-related offer, or an app-managed item.

These should not all be treated as the same commerce object. A physical product may belong in Wix Stores, while a booking, restaurant menu item, event, pricing plan, or app-owned record may need different Wix functionality or Custom Service review.

#### Product options, choices, variants, and modifiers need careful translation <a href="#product-options-choices-variants-and-modifiers-need-careful-translation" id="product-options-choices-variants-and-modifiers-need-careful-translation"></a>

A Source Platform may use option names, option values, configurable products, variants, modifiers, custom fields, add-ons, or bundled choices. In Wix, these meanings may need to become product options, choices, variants, modifiers, or a simplified target structure.

The most important question is whether the shopper can still select the correct item and whether store managers can still manage price, SKU, image, inventory, and fulfillment details correctly.

| Source product behavior                 | Wix-facing interpretation question                                                |
| --------------------------------------- | --------------------------------------------------------------------------------- |
| Size, color, material, or style choices | Should these become product options and choices?                                  |
| SKU-level stock differences             | Does each sellable variant need its own SKU and inventory behavior?               |
| Add-on selections                       | Can modifiers represent the buying choice, or is custom handling needed?          |
| Bundled or kit products                 | Can Wix represent the product clearly, or is app/custom handling required?        |
| Downloadable or digital products        | Does the target Wix setup support the expected file delivery and access behavior? |
| Subscription product behavior           | Should the offer use Wix-supported subscription behavior or app-specific setup?   |

### Collections, Categories, Filters, and Navigation May Not Match the Source Store <a href="#collections-categories-filters-and-navigation-may-not-match-the-source-store" id="collections-categories-filters-and-navigation-may-not-match-the-source-store"></a>

Wix uses collections and storefront organization to help shoppers browse products. A Source Platform category tree may not move into Wix as an identical hierarchy with the same filtering, menu, URL, and page behavior.

This matters because shoppers experience catalog structure through visible navigation, product grids, collection pages, filters, search, menus, and promotional landing pages. A migration that preserves product records but loses discovery logic can still feel incomplete.

Migration planning should identify which source categories are structural, which are marketing groups, which are SEO-sensitive landing paths, and which are only internal organization labels.

### Inventory, SKU, and Product Identifier Meaning Can Change <a href="#inventory-sku-and-product-identifier-meaning-can-change" id="inventory-sku-and-product-identifier-meaning-can-change"></a>

SKU, barcode, GTIN, stock quantity, inventory status, low-stock behavior, product availability, variant-level inventory, and fulfillment references may carry different meanings across platforms. Wix can store important product and inventory values, but the Source Platform’s operational logic may not map one-to-one.

Inventory-sensitive stores should review products where stock differs by variant, marketplace channel, warehouse, fulfillment method, or external inventory system. If a PIM, ERP, marketplace connector, fulfillment app, or custom integration controls stock, that dependency may sit outside standard product migration.

### Customers, Contacts, and Members Are Not the Same Thing <a href="#customers-contacts-and-members-are-not-the-same-thing" id="customers-contacts-and-members-are-not-the-same-thing"></a>

A customer record in a Source Platform may include billing details, shipping addresses, login credentials, order history, customer group, wholesale status, marketing consent, loyalty data, membership access, or app-owned profile fields. Wix may represent related meaning through customers, contacts, site members, business app records, or connected app data.

The distinction matters because each record may serve a different business purpose:

| Source meaning                  | Wix-related planning concern                                                                   |
| ------------------------------- | ---------------------------------------------------------------------------------------------- |
| Customer with order history     | The customer should remain connected to readable historical orders where supported.            |
| Contact used for marketing      | Marketing consent, segmentation, and subscription meaning may need separate review.            |
| Member account                  | Login, restricted access, member pages, or account expectations may need Wix Members planning. |
| Wholesale or B2B customer       | Pricing, access, approval, and purchasing rules may need app or Custom Service review.         |
| Loyalty or subscription profile | App-owned or external-system records should be separated from standard customer migration.     |

Password behavior and member access should be reviewed against the selected Source Platform, target Wix capability, and project scope. Customer data migration does not automatically recreate every login, access, pricing, or marketing workflow.

### Orders Carry History, Not Complete Checkout Configuration <a href="#orders-carry-history-not-complete-checkout-configuration" id="orders-carry-history-not-complete-checkout-configuration"></a>

Orders migrated into Wix should be evaluated as historical commerce records. They may include customer context, purchased products, quantities, totals, discounts, tax, payment labels, shipping methods, fulfillment status, tracking values, refunds, cancellations, notes, and source-specific metadata.

Live checkout behavior is different. Payment methods, tax setup, shipping rates, delivery rules, pickup, fulfillment settings, notifications, abandoned cart behavior, and checkout customization require target setup and testing in Wix.

A readable historical order does not prove that new Wix orders will calculate totals, shipping, tax, payment, or fulfillment behavior in the same way.

### CMS Pages, Blog Posts, and Storefront Content Need Separate Meaning Review <a href="#cms-pages-blog-posts-and-storefront-content-need-separate-meaning-review" id="cms-pages-blog-posts-and-storefront-content-need-separate-meaning-review"></a>

Wix is often chosen because it combines website building with commerce. That makes content migration especially important. Source-store pages, blog posts, landing pages, banners, menus, product descriptions, category descriptions, image assets, metadata, and embedded content may not move as identical page layouts.

CMS Pages and Blog Posts should be reviewed for both content and presentation. A source page may become a Wix site page, CMS-driven page, Blog Post, manually rebuilt landing page, or accepted redesign item. The right interpretation depends on how much of the source value comes from the text itself versus layout, visual hierarchy, navigation placement, forms, scripts, or SEO value.

### Apps, Velo, APIs, and External Systems Can Own Business Meaning <a href="#apps-velo-apis-and-external-systems-can-own-business-meaning" id="apps-velo-apis-and-external-systems-can-own-business-meaning"></a>

Wix can be extended through apps, Velo by Wix, developer APIs, custom catalogs, checkout and cart behavior, shipping and payment service plugins, CMS collections, and third-party integrations. These layers can carry business meaning that is not stored as ordinary product, customer, order, or page data.

Common examples include loyalty points, reviews, subscriptions, bookings, restaurant workflows, event records, custom checkout fees, custom shipping logic, external product catalogs, CRM data, ERP references, fulfillment records, marketplace identifiers, accounting references, and analytics events.

When these records matter after launch, they should be classified before migration scope is finalized:

| Dependency type                                                         | Likely migration meaning                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Wix App Market equivalent exists                                        | Data may still need app-specific review or reconfiguration.                         |
| Source extension data has no native Wix field                           | Custom Service review may be required.                                              |
| Velo or API logic is expected after launch                              | The requirement should be treated as custom implementation or integration planning. |
| External system owns identifiers or workflow state                      | Mapping and continuity requirements should be documented before Demo Migration.     |
| Checkout, shipping, payment, or catalog behavior depends on custom code | Data migration and target behavior setup must be evaluated separately.              |

### SEO, URLs, Redirects, and Domain Meaning May Change <a href="#seo-urls-redirects-and-domain-meaning-may-change" id="seo-urls-redirects-and-domain-meaning-may-change"></a>

Wix can manage SEO titles, meta descriptions, URL slugs, redirects, structured site navigation, and domain settings. However, the Source Platform’s URL patterns, category paths, product routes, blog URLs, and landing-page structures may not match Wix’s target structure automatically.

SEO-sensitive migration planning should identify high-value product URLs, category URLs, Blog Posts, CMS Pages, landing pages, redirects, metadata, image alt text, and domain behavior before launch. The objective is not only to preserve text values, but to keep important paths discoverable and intentionally redirected where exact continuity is not possible.

### What the Migrated Wix Data Must Prove <a href="#what-the-migrated-wix-data-must-prove" id="what-the-migrated-wix-data-must-prove"></a>

A migrated Wix result should prove that the main business meanings survive inside the target environment. This includes more than record counts.

Useful proof areas include:

* products display with correct names, images, prices, options, choices, variants, and inventory behavior;
* collections, filters, menus, search, and product pages support realistic shopper discovery;
* customers, contacts, members, and order relationships remain understandable;
* historical orders preserve useful payment, shipping, tax, discount, status, and fulfillment context;
* CMS Pages and Blog Posts retain the content and SEO values that matter after launch;
* app-owned, Velo, API, and external-system data is either migrated, reconfigured, documented for Custom Service, or accepted as out of scope;
* priority URLs, redirects, metadata, and domain expectations are ready for launch review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix migration quality depends on how well source-store meaning is translated into Wix’s hosted website, commerce, content, app, and developer ecosystem. Product data, customer records, orders, pages, and SEO values should be judged by whether they remain useful in the way the business will operate after launch.

Before approving a Wix migration path, review sample records that expose real data-model complexity: option-heavy products, variant inventory, important collections, customers with order history, member or contact examples, Blog Posts, CMS Pages, app-dependent records, and SEO-sensitive URLs. If these records do not translate cleanly, Add-ons, configuration work, accepted exclusions, or Custom Service review should be planned before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Are Wix products the same as products in my current store?**

Not always. Product names, prices, images, and descriptions may translate clearly, but product types, options, choices, variants, modifiers, inventory rules, subscriptions, digital delivery, or app-owned behavior may need separate review.

**Do source-store categories become Wix collections automatically?**

Category meaning should be reviewed before assuming a direct match. Some categories can become Wix collections, while others may need menus, filters, landing pages, redirects, or storefront design decisions to preserve shopper discovery.

**Are Wix customers, contacts, and members the same thing?**

No. A customer may be tied to orders, a contact may support communication or marketing use, and a member may support login or access behavior. Source customer data should be reviewed for the specific business meaning it needs to preserve in Wix.

**Does migrated order history configure Wix checkout?**

No. Historical orders help preserve past commerce context. Live checkout, payments, shipping, tax, fulfillment, notifications, and order settings require target setup and testing in Wix.

**What data needs Custom Service review in a Wix migration?**

Custom Service review is appropriate when important source-store meaning depends on unsupported app data, Velo or API behavior, custom checkout logic, external-system identifiers, custom product structures, app-owned customer data, or target behavior beyond standard service capability.
