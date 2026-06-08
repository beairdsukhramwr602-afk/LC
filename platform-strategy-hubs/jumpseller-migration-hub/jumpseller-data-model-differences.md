# Jumpseller Data Model Differences

A migration to Jumpseller changes how store data is interpreted, displayed, managed, and validated. Source records do not simply move into matching fields with the same operational meaning. They become Jumpseller products, variants, categories, customers, orders, pages, checkout details, inventory records, redirects, theme-managed storefront elements, and app or integration dependencies inside a hosted SaaS platform.

The central data-model question is whether each source structure has a clear Jumpseller destination and whether the migrated result still supports how the business sells, fulfills, reviews history, and manages the store after launch. Product rows, customer records, and order history are only part of that answer. Catalog behavior, shopper selection, category discovery, checkout context, payment and fulfillment meaning, multilingual content, SEO paths, app-owned data, and theme presentation also need to make sense inside Jumpseller.

### Product Data Becomes Jumpseller Catalog Structure <a href="#product-data-becomes-jumpseller-catalog-structure" id="product-data-becomes-jumpseller-catalog-structure"></a>

Source platforms can describe products through simple products, configurable products, grouped items, bundles, product builders, downloadable goods, subscriptions, appointment-based products, modifiers, attributes, custom fields, and app-generated product logic. Jumpseller needs that source meaning to become a practical product catalog that can be managed through its product structure.

Core product information usually includes product name, description, SKU, price, images, stock, visibility, categories, SEO fields, and related settings. Those fields are only reliable when their meaning survives the move. A source product that used attributes mainly for search may not need the same target structure as a source product that used attributes for shopper selection, stock tracking, or price changes.

The safest data translation separates product meaning into clear groups:

| Source product meaning              | Jumpseller interpretation question                                                                                      | What the migrated result must prove                                                                                          |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Main product identity               | Does the item become a clear Jumpseller product with the correct name, description, SKU, price, images, and visibility? | Staff can recognize, edit, and publish the product without losing commercial meaning.                                        |
| Shopper-selectable options          | Should the source structure become Jumpseller options, variants, or another target-side representation?                 | Shoppers can select the intended product choices and see the correct price, image, and availability behavior.                |
| Source attributes or specifications | Are these selling options, product details, filter values, SEO information, or custom fields?                           | Attribute meaning is not flattened into generic text when it affects search, filtering, comparison, or purchasing decisions. |
| Custom product fields               | Can Jumpseller store the value as a usable product field, content element, custom field, or target-side configuration?  | Important custom data remains visible or usable where staff and shoppers need it.                                            |
| App-owned product logic             | Does the target platform natively support it, or does it depend on an app, integration, or Custom Service review?       | The migrated catalog does not imply support for behavior that is actually controlled outside the native product record.      |

### Options, Variants, Inputs, and Custom Product Meaning <a href="#options-variants-inputs-and-custom-product-meaning" id="options-variants-inputs-and-custom-product-meaning"></a>

Variant translation is one of the most important Jumpseller data-model topics. Jumpseller product options can represent shopper selections such as size or color, and option combinations can generate variants with their own price, stock, SKU, and images. This makes Jumpseller suitable for many ordinary variant catalogs, but not every source product structure maps cleanly.

Some source platforms separate options, variants, attributes, modifiers, personalization fields, file uploads, and custom line-item data. In Jumpseller, these meanings need careful classification. A color or size option that changes stock is different from a text field used for personalization. A file upload field is different from a variant image. A source modifier that adds an optional paid service is not the same as a stock-tracked variant.

Jumpseller also has a variant-count boundary. Product structures with very large combinations should be reviewed before migration because overly dense source configurations may not fit neatly into a single Jumpseller product. When a source product generates many combinations, the migration plan may need to split products, simplify choices, map some values as descriptive fields, or review whether custom handling is needed.

### Categories Are Product Organization, Not the Whole Storefront Path <a href="#categories-are-product-organization-not-the-whole-storefront-path" id="categories-are-product-organization-not-the-whole-storefront-path"></a>

Categories in Jumpseller organize products, but they should not be treated as the entire storefront navigation model. A source platform may use categories as menus, collections, filters, landing pages, shop departments, brand pages, or SEO landing structures. Jumpseller category migration must preserve product grouping, but storefront discovery also depends on menus, theme layout, page links, product filters, and SEO paths.

A migrated category can be technically present while still failing the business test if shoppers cannot find the products through the expected navigation route. Category meaning should therefore be interpreted in relation to product placement, storefront menus, filter expectations, and the target theme experience.

Source category hierarchies may also need simplification. Deep category trees from older platforms can become difficult to use in a hosted storefront if they were originally built around legacy URL structures, plugin behavior, or source-specific menu logic. The target outcome should be a clear Jumpseller catalog structure that supports browsing, search, and merchandising.

### Customer Data Becomes Account and Contact Context <a href="#customer-data-becomes-account-and-contact-context" id="customer-data-becomes-account-and-contact-context"></a>

Customer migration into Jumpseller is not only a matter of names and email addresses. Customer records can include account status, addresses, phone numbers, purchase history links, customer categories or groups, marketing preferences, tax or billing identifiers, and password expectations.

The meaning of customer data depends on how the target store will use it. Some migrated customer records support historical order review. Others support future customer login, repeat purchasing, segmentation, customer service, marketing, or B2B-style account management. These uses should not be assumed to be identical across platforms.

Password continuity is especially sensitive. Source platforms store customer passwords using different hashing systems, and hosted SaaS platforms often do not accept legacy password hashes as direct reusable credentials. The migration result should set realistic expectations for customer login after launch and confirm whether customers will need reset or reactivation communication.

Customer groups or categories also need interpretation. A source customer group may control pricing, tax handling, payment access, shipping eligibility, discounts, or wholesale behavior. If Jumpseller does not use the same group logic in the same way, the migrated field may preserve a label without preserving the original business rule.

### Orders Become Historical and Operational Records <a href="#orders-become-historical-and-operational-records" id="orders-become-historical-and-operational-records"></a>

Order data in Jumpseller carries both historical and operational meaning. A migrated order should show what was purchased, who purchased it, where it was billed or shipped, how payment was recorded, how fulfillment was handled, what discounts or taxes were applied, and what happened during the order lifecycle.

Source platforms vary widely in order structure. Some store payment state separately from order state. Some have custom fulfillment stages, invoice workflows, refund records, shipment packages, partial fulfillment, abandoned cart logic, manual order creation, or app-managed fulfillment history. Jumpseller interprets orders through its own payment, fulfillment, product, address, history, and administrative structures.

The migration plan should distinguish between preserving order history and reproducing source workflow behavior. Historical orders should remain readable and useful for staff. Live order processing, payment capture, fulfillment, shipping labels, customer notifications, invoices, and external fulfillment workflows may require target-side configuration or integration work beyond data migration.

### Payment, Shipping, Tax, and Fulfillment Meaning Changes <a href="#payment-shipping-tax-and-fulfillment-meaning-changes" id="payment-shipping-tax-and-fulfillment-meaning-changes"></a>

Payment and shipping methods are operating configurations, not just data labels. A source order may contain a historical payment method name, but the live Jumpseller store still needs payment providers to be configured inside the target environment. The same applies to shipping rates, shipping zones, fulfillment providers, pickup methods, manual payment instructions, and tax-related settings.

A migration can preserve historical payment and shipping references while still requiring new target-side setup for future orders. This distinction matters because merchants sometimes expect payment, tax, shipping, and fulfillment behavior to transfer as if they were ordinary product fields. In practice, these areas must be re-confirmed inside Jumpseller’s hosted platform structure.

For data-model planning, the key question is whether historical values remain understandable and whether future checkout behavior can be configured to support the business. A source-specific payment plugin or shipping module may not have a direct one-to-one target equivalent.

### Checkout Fields and Additional Order Information Need Separate Review <a href="#checkout-fields-and-additional-order-information-need-separate-review" id="checkout-fields-and-additional-order-information-need-separate-review"></a>

Checkout data can include standard customer fields, shipping and billing details, tax identifiers, delivery notes, business names, marketing consent, gift messages, delivery dates, pickup preferences, or custom checkout fields. Source platforms often store these details in different locations, including order attributes, customer attributes, checkout-field tables, plugin records, or custom database fields.

Jumpseller checkout has its own structure and field behavior. Migrated checkout-related data should be reviewed for whether it belongs to the customer record, the order record, additional order information, custom fields, or external-system handling. This prevents important operational data from being hidden, flattened, or placed where staff cannot use it after launch.

Checkout design should not be confused with checkout data. A source checkout layout or script is not the same as a checkout field value. If the source store depended on custom checkout behavior, the data model should first identify what information must be preserved and then determine whether the target platform can capture and display it appropriately.

### Inventory Becomes Jumpseller Stock and Location Context <a href="#inventory-becomes-jumpseller-stock-and-location-context" id="inventory-becomes-jumpseller-stock-and-location-context"></a>

Inventory meaning depends on how the source store tracked stock. Some stores track stock at the product level. Others track stock by variant, warehouse, location, supplier, bundle component, fulfillment channel, or external inventory system. Jumpseller stock should be interpreted through the target product and variant structure, and stock-location needs should be confirmed against the target plan and operating model.

Variant-level stock is especially important. If the source store tracked inventory per size, color, or SKU combination, that meaning should remain attached to the correct Jumpseller variant after migration. If the source store tracked inventory through an ERP, marketplace, POS, or fulfillment app, the migration plan should separate migrated stock values from future synchronization behavior.

The migrated result should prove that staff can understand available stock, update stock safely, and connect future inventory workflows without confusing historical quantities with live operational control.

### Content, Pages, Blog Posts, and SEO Fields Have Storefront Meaning <a href="#content-pages-blog-posts-and-seo-fields-have-storefront-meaning" id="content-pages-blog-posts-and-seo-fields-have-storefront-meaning"></a>

Jumpseller store content may include pages, legal pages, blog or article-style content, page categories, images, SEO titles, meta descriptions, permalinks, redirects, and custom templates. Source content should not be treated as generic text only. It may support trust pages, policies, SEO landing pages, product education, brand storytelling, and customer support.

CMS Pages and Blog Posts should be reviewed separately from products and categories. A product migration may be successful while content migration remains incomplete if legal pages, SEO metadata, internal links, media, or redirects are not handled correctly.

SEO meaning also changes during migration. Source URLs, slugs, metadata, headings, redirects, and internal links may not have identical target structures. Jumpseller can support target-side SEO fields and redirects, but URL continuity still needs prioritization and validation. The goal is not to promise that every historical URL will behave exactly the same. The goal is to preserve priority paths, reduce avoidable loss, and make target pages understandable to shoppers and search engines.

### Multilingual and Multicurrency Data Need Target-Side Interpretation <a href="#multilingual-and-multicurrency-data-need-target-side-interpretation" id="multilingual-and-multicurrency-data-need-target-side-interpretation"></a>

Jumpseller can support multiple languages and currencies, but multilingual and multicurrency migration is not automatic field duplication. Source platforms may store translations through language tables, duplicated products, translation plugins, localized URLs, language-specific categories, translated menus, or separate storefronts. Each of these models has different migration meaning.

Translated product names, descriptions, categories, pages, SEO fields, navigation labels, checkout labels, and policy pages should be interpreted as target-language content, not only as extra text fields. The validation question is whether shoppers in each intended language can understand the catalog, navigate the store, and complete the purchase path.

Currency behavior also deserves separation from historical order currency. A migrated order may preserve the currency used at purchase, while live multicurrency selling depends on Jumpseller settings, payment availability, country behavior, and target storefront expectations.

### Theme, Liquid, Apps, API, and Webhooks Are Surrounding Meaning Layers <a href="#theme-liquid-apps-api-and-webhooks-are-surrounding-meaning-layers" id="theme-liquid-apps-api-and-webhooks-are-surrounding-meaning-layers"></a>

A Jumpseller migration does not recreate a source theme by moving product, customer, and order records. Storefront appearance and front-end behavior are controlled by the Jumpseller theme system, available theme editing, Liquid-based templates, theme components, content placement, apps, and integrations.

This matters because some source data is only meaningful because of surrounding source code or app behavior. A product badge, comparison block, bundle widget, trust badge, installment-payment message, recommendation carousel, marketplace feed, invoice integration, or ERP status may appear to be part of the product or order record, but it may actually be owned by a source app, template, script, or external system.

App-owned and integration-owned data should be classified before migration. Some values can become native Jumpseller product, customer, order, page, or SEO fields. Some can be recreated through target-side apps or theme work. Some require Custom Service because they need custom migration logic adjustment, outside-system identifiers, unsupported app records, or bespoke transformation.

### What Migrated Data Must Prove Inside Jumpseller <a href="#what-migrated-data-must-prove-inside-jumpseller" id="what-migrated-data-must-prove-inside-jumpseller"></a>

Data-model validation should prove meaning, not only record presence. A migrated Jumpseller store should show that the main business structures are readable, usable, and positioned correctly inside the target platform.

| Proof area                      | What should be checked                                                                                                           | Why it matters                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Product meaning                 | Product identity, SKUs, prices, descriptions, images, SEO fields, visibility, and custom fields                                  | Confirms that the catalog is usable by staff and understandable to shoppers.                |
| Variant meaning                 | Options, variant combinations, stock, price changes, variant images, and SKU behavior                                            | Confirms that shopper selection and inventory logic survived translation.                   |
| Category and navigation meaning | Product placement, category hierarchy, menus, filters, and important landing paths                                               | Confirms that shoppers can find products, not only that categories exist.                   |
| Customer meaning                | Accounts, addresses, categories, marketing fields, password expectations, and order links                                        | Confirms that customer records support future use and historical review.                    |
| Order meaning                   | Products purchased, totals, discounts, taxes, payment status, fulfillment status, addresses, history, and additional information | Confirms that historical orders remain operationally readable.                              |
| Content and SEO meaning         | CMS Pages, Blog Posts, legal pages, media, metadata, permalinks, redirects, and internal links                                   | Confirms that storefront trust, search visibility, and content continuity were not ignored. |
| Integration meaning             | App-owned fields, external IDs, API/webhook data, sales-channel fields, and fulfillment links                                    | Confirms that external-system dependencies are not mistaken for ordinary native records.    |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Jumpseller data-model differences matter because the platform organizes commerce through hosted SaaS structures rather than through the source store’s original database, extension stack, checkout code, or theme logic. A successful migration should make products, variants, categories, customers, orders, content, checkout context, inventory, URLs, languages, and integrations meaningful inside Jumpseller. The safest planning starts by identifying what each source record actually did for the business and then confirming where that meaning belongs in the Target Platform.

Before approving a migration to Jumpseller, review representative source samples for product variants, custom fields, categories, customer accounts, order statuses, checkout fields, inventory, content, redirects, languages, and app-owned data. If those samples reveal unsupported structures, external identifiers, source-specific app behavior, or transformation needs beyond standard service capability, discuss the scope with Next-Cart through Live Chat before relying on the migration result for launch planning.

### FAQs <a href="#faqs" id="faqs"></a>

**Are product options and product attributes always migrated the same way into Jumpseller?**

No. Source platforms use options, attributes, specifications, modifiers, and custom fields for different purposes. Some values should become shopper-selectable options or variants in Jumpseller. Others may belong in descriptions, custom fields, filters, SEO fields, or target-side configuration. The correct mapping depends on what the source value does for shopping, stock, price, search, and staff management.

**Why do variant-heavy catalogs need extra review before moving to Jumpseller?**

Variant-heavy catalogs need review because each option combination may affect stock, price, SKU, images, and availability. If the source platform uses complex configurators, bundles, modifiers, or large option combinations, the product may need restructuring before it can work cleanly inside Jumpseller’s product and variant model.

**Does migrating categories automatically recreate my old storefront navigation?**

No. Categories organize products, but storefront navigation also depends on menus, theme layout, filters, content links, landing pages, and SEO paths. A migrated category may exist correctly while the storefront still needs navigation review before shoppers can browse products in the expected way.

**Can historical orders move even if payment and shipping methods must be reconfigured?**

Yes. Historical order information and future checkout configuration are different concerns. A migration can preserve readable payment and shipping references in past orders, while the live Jumpseller store still needs payment gateways, shipping rules, fulfillment methods, and related settings configured for future sales.

**What happens to source app data or custom fields that do not have a clear Jumpseller destination?**

Data from source apps, custom tables, external systems, or unusual custom fields should be reviewed before migration. If the data cannot be handled through standard service capability or Standard Add-ons, it belongs under Custom Service review because custom interpretation, transformation, or migration logic adjustment is required.
