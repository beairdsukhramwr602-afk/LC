# X-Cart Data Model Differences

X-Cart is a configurable e-commerce Target Platform, so migration quality depends on more than moving records into new tables. The migrated result must preserve how products are purchased, how categories and filters help shoppers find items, how customers and orders remain useful, and how add-ons, custom fields, SEO values, and integrations continue to support daily operations.

A source store may describe products, customers, orders, content, and custom data in ways that do not map one-to-one into X-Cart. Some values become core X-Cart records, some become configuration, some depend on installed add-ons or custom modules, and some require custom migration logic adjustment before they can remain useful in the target environment.

### Why Data Model Differences Matter in X-Cart <a href="#why-data-model-differences-matter-in-x-cart" id="why-data-model-differences-matter-in-x-cart"></a>

X-Cart can support standard e-commerce structures as well as store-specific customization. That flexibility is valuable, but it also means migration planning should identify where business meaning lives. A product option, customer group, order status, custom field, storefront filter, or integration identifier may look like a simple field in the Source Platform while acting as an operational rule inside X-Cart.

The key question is not only whether the record exists after migration. The stronger question is whether the record behaves correctly in the target store.

| Source-store meaning              | X-Cart meaning to confirm                                                                                                           | Why it matters                                                                            |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Product record                    | Product with name, SKU, price, inventory, images, description, options, attributes, SEO values, and category assignment             | Product records must remain purchasable, discoverable, and manageable.                    |
| Product option or variation       | Option, variant, variation, attribute, extra field, or add-on-supported product logic                                               | Buying choices may affect SKU, price, image, inventory, shipping, or filtering.           |
| Category or collection            | Category structure, navigation path, menu placement, filter behavior, and SEO route                                                 | Products can migrate correctly but become difficult to find if discovery meaning changes. |
| Customer account                  | Customer profile, address, user status, group, membership, order association, and login context                                     | Account usability depends on more than name and email.                                    |
| Order history                     | Order record with line items, totals, taxes, discounts, payment labels, shipping labels, status, invoice, and customer relationship | Historical orders must remain readable for service, accounting, and fulfillment review.   |
| Checkout setup                    | Target payment, shipping, tax, notification, and checkout configuration                                                             | Migrated order labels do not automatically configure live checkout behavior.              |
| Page or content block             | X-Cart content page, static page, storefront block, theme-managed content, or add-on-owned content                                  | Content migration may need design or theme review, not only text transfer.                |
| SEO value                         | Product, category, page, metadata, slug, canonical, redirect, or landing-page value                                                 | SEO continuity depends on URL behavior and target routing, not only metadata fields.      |
| App, module, or custom field data | Add-on/module data, custom field, custom table, API reference, or integration identifier                                            | Non-standard business meaning may need Custom Service review.                             |

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

Products are central to an X-Cart migration, but product meaning can be distributed across several layers. A source product may include catalog identity, price, stock, SKU, images, descriptions, options, variants, attributes, extra fields, SEO values, related products, downloadable files, tax or shipping flags, and add-on-controlled behavior.

Inside X-Cart, these pieces should be reviewed as a working catalog model. A product that appears in the admin area is not necessarily migration-ready if shoppers cannot select the correct option, see the right image, purchase the right variant, or find the item through category and filter paths.

#### Product Options, Variants, Attributes, and Extra Fields <a href="#product-options-variants-attributes-and-extra-fields" id="product-options-variants-attributes-and-extra-fields"></a>

Product options and variants often carry business rules. They may change price, stock, SKU, weight, image, availability, product identity, or fulfillment handling. Attributes and extra fields may support product comparison, storefront filters, technical specifications, merchandising, or integration references.

For X-Cart, these values should be classified before migration acceptance:

| Product data type      | What to confirm in X-Cart                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Options                | Whether selectable choices appear correctly and affect the intended product result.                                             |
| Variants or variations | Whether variant-specific SKU, stock, price, image, and availability remain meaningful.                                          |
| Attributes             | Whether shopper-facing and admin-facing attributes retain their purpose.                                                        |
| Extra fields           | Whether additional product facts remain searchable, filterable, visible, hidden, or integration-ready as needed.                |
| Inventory values       | Whether stock, availability, backorder behavior, and low-stock expectations align with target setup.                            |
| Product media          | Whether images, galleries, thumbnails, downloadable files, or media associations stay attached to the right product or variant. |

When the Source Platform uses custom product logic, a direct record migration may not be enough. Custom logic, custom fields, custom tables, or add-on-owned product behavior should be reviewed through Custom Service when standard service capability or Standard Add-ons cannot preserve the intended meaning.

### Categories, Navigation, Search, and Filters <a href="#categories-navigation-search-and-filters" id="categories-navigation-search-and-filters"></a>

X-Cart catalog discovery depends on more than assigning products to categories. Category hierarchy, storefront menus, product sorting, search behavior, filters, faceted navigation, landing pages, and SEO URLs all affect how shoppers reach products.

A source category may become an X-Cart category, but the buyer journey can still change if menu placement, filter data, route structure, or search behavior is not planned. This is especially important for stores with deep catalogs, technical products, brand-driven browsing, size/color filtering, or SEO-sensitive category pages.

Strong data-model review should include:

* top-level and deep categories;
* products assigned to multiple categories;
* category descriptions and images;
* search-critical attributes and extra fields;
* filter values that shoppers use to narrow results;
* menu and navigation expectations;
* high-value category and product URLs;
* redirects for important legacy paths.

### Customer, User, Group, and Account Meaning <a href="#customer-user-group-and-account-meaning" id="customer-user-group-and-account-meaning"></a>

Customer data in X-Cart should remain useful for account access, order review, segmentation, pricing logic, communication, and business workflows where applicable. A source customer record may include profile details, email, billing and shipping addresses, account status, user group, membership, tax exemption, marketing preference, reward balance, wholesale context, or external identifiers.

Not every source value has the same target meaning. Some values can become standard customer or address data. Others may belong to user groups, memberships, custom fields, add-ons, or external systems.

| Customer-related data          | X-Cart interpretation risk                                                                                       |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Email and profile details      | Account identity must stay clear and avoid duplication.                                                          |
| Billing and shipping addresses | Address structure should remain usable for order review and future checkout.                                     |
| Customer groups or memberships | Group meaning may affect pricing, permissions, tax, content access, or B2B behavior.                             |
| Marketing or newsletter status | Consent and subscription meaning may depend on the target marketing setup.                                       |
| External customer IDs          | CRM, ERP, accounting, or loyalty references may need custom mapping.                                             |
| Passwords                      | Password continuity depends on platform compatibility and migration feasibility; reset planning may be required. |

### Order and Historical Transaction Meaning <a href="#order-and-historical-transaction-meaning" id="order-and-historical-transaction-meaning"></a>

Orders are often reviewed after migration as proof of operational continuity, but X-Cart order meaning includes more than order count. A usable order record should preserve customer context, purchased products, option or variant details, quantities, totals, taxes, discounts, shipping method, payment label, order status, invoice context, and fulfillment history where available.

Historical payment and shipping labels should not be confused with live target configuration. A migrated order may show that a customer paid with a certain method or used a certain shipping carrier in the past. That does not mean the new X-Cart store is configured to accept the same payment method or calculate the same shipping method for future orders.

#### Order Statuses, Discounts, Taxes, and Returns <a href="#order-statuses-discounts-taxes-and-returns" id="order-statuses-discounts-taxes-and-returns"></a>

Source order states may not align exactly with X-Cart order statuses. Paid, authorized, refunded, partially refunded, canceled, shipped, partially shipped, returned, or abandoned-cart-related records should be sampled deliberately.

Discounts and taxes also need careful review. A migrated order total may be readable, while the target discount or tax configuration for new orders remains separate. If the Source Platform uses custom discount logic, tax rules, return workflows, or fulfillment states, those meanings should be confirmed before Full Migration.

### Checkout, Payment, Shipping, and Tax Boundaries <a href="#checkout-payment-shipping-and-tax-boundaries" id="checkout-payment-shipping-and-tax-boundaries"></a>

Checkout-related data often crosses the boundary between migration and target setup. X-Cart can hold order history and support checkout configuration, payment methods, shipping methods, taxes, notifications, and security-related behavior, but these are not the same type of work.

Migration can preserve historical order information where supported. Target setup must separately confirm how new customers will check out, pay, receive tax calculations, select shipping, receive notifications, and generate new order records.

This distinction should be clear when reviewing Demo Migration results. A historical order can pass migration review while checkout setup still requires separate target configuration and testing.

### Content, Storefront, and Theme-Managed Meaning <a href="#content-storefront-and-theme-managed-meaning" id="content-storefront-and-theme-managed-meaning"></a>

X-Cart is an e-commerce platform, not a CMS-first platform, but stores may still include important content. Static pages, landing pages, category descriptions, product descriptions, banners, menus, footer links, marketing blocks, and theme-managed content can influence conversion and SEO.

Some content can migrate as page or product data. Other content may need theme work, storefront configuration, menu setup, or add-on support. Page-builder-like content, custom templates, embedded scripts, widgets, and design-specific blocks should not be treated as ordinary plain text without review.

### SEO, URL, Redirect, and Metadata Meaning <a href="#seo-url-redirect-and-metadata-meaning" id="seo-url-redirect-and-metadata-meaning"></a>

SEO values are part of the data model because they determine how the new store is found and how traffic continuity is protected. Product slugs, category paths, page URLs, metadata, canonical behavior, redirects, image alt text, and filtered-page behavior should be reviewed before launch.

The most important URLs should be tested directly. A migrated product may appear correctly in X-Cart, but the migration can still create business risk if a high-value URL breaks, redirects incorrectly, loses metadata, or points to a product that shoppers cannot reach through the expected path.

### Add-Ons, Modules, Custom Fields, and Integration Data <a href="#add-ons-modules-custom-fields-and-integration-data" id="add-ons-modules-custom-fields-and-integration-data"></a>

X-Cart stores often rely on add-ons, custom modules, API connections, import/export routines, analytics tools, marketing systems, ERP/PIM/WMS integrations, accounting systems, shipping services, or marketplace connectors. These layers may own business meaning that is not visible in standard product, customer, order, or page counts.

Add-on or module data should be classified early:

| Data layer                        | Migration treatment to consider                                                                            |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Standard X-Cart-supported records | May fit standard migration scope when structure is predictable.                                            |
| Custom fields and extra values    | May need mapping, configuration, Advanced Data Mapping, Advanced Data Configure, or Custom Service review. |
| Add-on-owned data                 | Requires review because business meaning may live outside standard fields.                                 |
| Custom module data                | Usually needs Custom Service review when custom logic or custom storage is involved.                       |
| External identifiers              | May need preservation for ERP, PIM, WMS, CRM, accounting, marketplace, or fulfillment workflows.           |
| API/headless references           | May need target-side development, mapping, or custom migration logic adjustment.                           |

Add-ons are optional service features for filtering, mapping, or data configuration needs within supported capability. When an Add-on must be tailored, when custom migration logic adjustment is required, or when custom module data must be handled, the requirement moves into Custom Service because customization is required.

### Custom Platform Sources and Heavily Customized Stores <a href="#custom-platform-sources-and-heavily-customized-stores" id="custom-platform-sources-and-heavily-customized-stores"></a>

When the Source Platform is a Custom Platform, the migration cannot assume a known source data model. Product, customer, order, content, and custom records must be interpreted before they can be matched to X-Cart target structures.

Heavily customized source stores create similar risks even when the platform itself is known. Custom checkout logic, custom catalog tables, custom product fields, custom customer groups, external IDs, custom order workflows, and proprietary integrations may all change how data should be translated into X-Cart.

Custom Platform source cases and bespoke source logic belong in Custom Service review so the migration can be scoped around the actual business meaning of the data.

### Conclusion <a href="#conclusion" id="conclusion"></a>

X-Cart migration quality depends on preserving the meaning of store data inside a configurable e-commerce environment. Products must remain purchasable, categories and filters must support discovery, customers and orders must remain useful, content and SEO values must protect storefront continuity, and add-on or custom data must be handled in line with its business purpose.

Before judging a Demo Migration, compare representative records from the Source Platform against their intended X-Cart behavior. If complex options, custom fields, add-on-owned data, external identifiers, or custom workflows are essential to the business, raise those cases before Full Migration so the service path, Add-ons, or Custom Service review can be selected correctly.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do product options and variants need extra review in an X-Cart migration?**

Options and variants can affect price, SKU, image, inventory, shipping, filtering, and the shopper’s buying path. A product may exist after migration but still fail if its selectable choices do not behave correctly in X-Cart.

**Are migrated order records enough to prove checkout is ready?**

No. Historical orders show past transaction context, while live checkout depends on target payment, shipping, tax, notification, and configuration settings. Both should be reviewed separately.

**What happens to custom fields during migration to X-Cart?**

Custom fields should be reviewed for purpose and target fit. Some values may be handled through supported mapping or configuration, while custom logic, custom module data, or bespoke storage requires Custom Service review.

**Should add-on data be treated as standard product or order data?**

Not automatically. Add-ons can store or control business meaning outside standard records. Add-on-owned data should be identified before migration scope is finalized so it can be migrated, mapped, reconfigured, excluded, or reviewed through Custom Service.

**Why does SEO belong in a data model discussion?**

SEO values affect how migrated products, categories, and pages are found after launch. Slugs, metadata, redirects, canonical behavior, and high-value URLs should be treated as part of migration meaning, not as a last-minute visual check.
