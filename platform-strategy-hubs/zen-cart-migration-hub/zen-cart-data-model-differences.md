# Zen Cart Data Model Differences

A migration to Zen Cart is not only a movement of records into a new database. It is a translation of store meaning into Zen Cart’s self-hosted catalog, customer, order, module, template, and plugin model. Data that looks simple in a source store can behave differently once it is interpreted through Zen Cart categories, product records, attributes, order totals, EZ-Pages, sideboxes, template overrides, and installed modules.

The most important question is whether each source-store value has a clear operational role in Zen Cart. Product options, customer records, order history, coupons, gift certificates, shipping labels, payment labels, content pages, SEO values, and plugin-owned fields should be reviewed for how they will be read and used after migration.

### What Data Model Translation Means in Zen Cart <a href="#what-data-model-translation-means-in-zen-cart" id="what-data-model-translation-means-in-zen-cart"></a>

Zen Cart is a self-hosted PHP/MySQL store application. Its data model is shaped by product/category administration, attribute assignment, customer accounts, order records, order-total modules, payment and shipping modules, templates, sideboxes, EZ-Pages, plugins, and custom database changes. A source field should not be judged only by whether it can be stored; it should be judged by whether Zen Cart can use it in the expected place.

| Source-store concept            | Zen Cart interpretation                                                                                                                                           | Migration planning impact                                                                                                                                         |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product record                  | Product entry connected to category placement, images, pricing, quantity, status, model value, tax class, shipping behavior, and product-type expectations.       | Product samples should include active, inactive, image-heavy, discounted, taxable, non-taxable, shippable, virtual, and download-related examples where relevant. |
| Variant or configurable product | Often translated through attributes, option names, option values, attribute pricing, attribute weight, and selection rules.                                       | Source variants should be reviewed for how buying choices appear on the product page and how selections appear in the cart and order.                             |
| Category or collection          | Category hierarchy, product assignment, linked products, category status, listing order, metadata, and navigation context.                                        | Category structure should be checked from both admin and storefront views, especially when products appear in more than one category.                             |
| Customer profile                | Customer account, address book, newsletter/subscription status, customer group or pricing behavior where configured.                                              | Customer records should preserve account readability and address usability, but group-pricing or custom-account meaning may need separate handling.               |
| Historical order                | Order header, customer/address snapshot, product line items, selected attributes, order totals, tax, payment label, shipping label, comments, and status history. | Order history should be validated for business readability, not treated as proof that live checkout modules are configured.                                       |
| Page or static content          | EZ-Pages, define pages, information pages, template-controlled content, or plugin/custom content structures.                                                      | CMS Pages should be assigned to the right Zen Cart content type and navigation location instead of being treated as generic text blocks.                          |
| Plugin-owned field              | Data stored by a module, plugin, custom table, template change, or external integration.                                                                          | Unsupported plugin data, custom fields, and custom tables belong in Custom Service review when they must be preserved.                                            |

### Product and Category Meaning <a href="#product-and-category-meaning" id="product-and-category-meaning"></a>

Zen Cart organizes the storefront around categories and products. A product is not only a name, description, and price; it may also carry product status, product model, images, quantity, weight, tax class, shipping behavior, manufacturer-style context, special pricing, sale pricing, meta tags, and product-type behavior. A source product should therefore be reviewed as a selling object, not as a flat catalog row.

Category meaning also changes during migration. A source collection, department, menu branch, brand page, or catalog group may become a Zen Cart category, but the relationship is not always one-to-one. Category depth, product assignment, category status, display order, linked products, and category metadata can affect whether shoppers find the product correctly after migration.

#### Product placement and linked products <a href="#product-placement-and-linked-products" id="product-placement-and-linked-products"></a>

Some stores expect one product to appear in several storefront paths. In Zen Cart, this can be represented through product-to-category assignment and linked product behavior rather than by duplicating the product record. Migration planning should distinguish between a product that should be copied as a separate item and a product that should remain a single product visible in more than one category path.

#### Product types and special product behavior <a href="#product-types-and-special-product-behavior" id="product-types-and-special-product-behavior"></a>

Some Zen Cart product behavior depends on product type or configuration. Downloadable products, music-style products, non-shippable products, variable-price products, donations, and special product displays may not match a source store’s product model exactly. These cases should be sampled before Full Migration when they affect checkout, delivery, product page layout, or order interpretation.

### Attributes, Options, and Option Values <a href="#attributes-options-and-option-values" id="attributes-options-and-option-values"></a>

Zen Cart commonly represents shopper selections through attributes. This makes attribute translation one of the most important parts of a Zen Cart migration. A source variant, option, modifier, custom text field, file upload, downloadable choice, personalization field, or configurable product may need to become an option name, option value, and assigned product attribute in Zen Cart.

The relationship between source variants and Zen Cart attributes should be reviewed carefully because attributes can affect more than display. They can influence customer selection, price, weight, downloads, default values, required choices, text input, and order-line meaning.

| Attribute-related source behavior        | Zen Cart planning question                                                                 | Why it matters                                                                                          |
| ---------------------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Size, color, material, or style variants | Should these become option names and option values assigned to each product?               | The storefront must let shoppers select the right value and the order must preserve the selected value. |
| Variant-level price differences          | Should the price be represented through attribute price adjustments or another structure?  | Incorrect translation can make the product look right but calculate the wrong cart total.               |
| Variant-level weight differences         | Does the attribute affect shipping weight?                                                 | Shipping calculation and fulfillment review can change when weight is not carried correctly.            |
| Required selections                      | Should a default value, display-only prompt, or required attribute behavior be configured? | Customers should not accidentally add the wrong selection to the cart.                                  |
| Text or personalization fields           | Should the field become a text attribute or require Custom Service?                        | Free-text or personalized values must remain visible in cart and order context.                         |
| File upload or downloadable content      | Does the source behavior match Zen Cart’s supported attribute/download handling?           | Digital delivery and file-dependent order meaning require special review.                               |
| Plugin-controlled option logic           | Is the behavior owned by a plugin, custom module, or custom table?                         | Unsupported logic is not ordinary attribute migration and should be reviewed separately.                |

### Product Pricing, Discounts, Coupons, and Gift Certificates <a href="#product-pricing-discounts-coupons-and-gift-certificates" id="product-pricing-discounts-coupons-and-gift-certificates"></a>

Zen Cart can represent price information through product prices, special prices, sale behavior, quantity discounts, attribute price adjustments, order-total modules, coupons, gift certificates, group pricing, and tax configuration. A source store may use different terms for similar commercial logic.

Migration planning should separate historical pricing evidence from active pricing configuration. A historical order should show what was paid, discounted, taxed, and shipped. The live Zen Cart store still needs target configuration for prices, tax classes, order totals, coupons, gift certificates, payment modules, and shipping modules before new checkout activity can be trusted.

### Customer, Address, Newsletter, and Group Meaning <a href="#customer-address-newsletter-and-group-meaning" id="customer-address-newsletter-and-group-meaning"></a>

Customer records in Zen Cart should be reviewed as account and operational records. A migrated customer may include login identity, name, email, address book entries, newsletter status, order relationship, and customer group or pricing behavior where configured.

Source stores often carry additional customer meaning such as B2B approval status, wholesale pricing tier, membership role, loyalty points, tax exemption, store credit, external CRM ID, or marketing consent. Some of these values may map cleanly into Zen Cart only when the target store has the right configuration or plugin support. Others may require Custom Service if they depend on custom fields, custom tables, or unsupported plugin logic.

### Order, Status, Comment, and Order-Total Meaning <a href="#order-status-comment-and-order-total-meaning" id="order-status-comment-and-order-total-meaning"></a>

Zen Cart orders are more than customer and product references. They can include billing and shipping addresses, product line items, selected attributes, order totals, tax lines, discounts, coupons, gift certificate activity, shipping labels, payment labels, comments, status history, and module-specific context.

A source order should be validated for readability inside the Zen Cart admin area. Customer service, finance, and fulfillment teams should be able to understand what was purchased, which selections were made, what the customer paid, how tax and shipping were represented, and which status or comment history matters.

Historical order migration does not configure the live checkout. Payment, shipping, tax, coupon, gift-certificate, and order-total modules must be configured and tested separately in the target store.

### Payment, Shipping, Tax, and Order-Total Modules <a href="#payment-shipping-tax-and-order-total-modules" id="payment-shipping-tax-and-order-total-modules"></a>

Zen Cart uses modules for payment methods, shipping methods, order totals, taxes, coupons, fees, discounts, gift certificates, and related checkout behavior. Source stores may store these values as simple labels, but Zen Cart uses module configuration to determine how new checkout activity works.

The data model difference is important: a migrated order may show a payment or shipping label from the source store, but the target payment or shipping module may not exist, may not be enabled, or may calculate differently. This distinction prevents teams from confusing historical order readability with live checkout readiness.

### Content, EZ-Pages, Define Pages, and Navigation Meaning <a href="#content-ez-pages-define-pages-and-navigation-meaning" id="content-ez-pages-define-pages-and-navigation-meaning"></a>

Zen Cart includes several ways to represent non-product content. Some content belongs in EZ-Pages, some belongs in define pages or built-in informational pages, and some may be controlled by templates, sideboxes, plugins, or custom files.

Source content should be reviewed for where it belongs in Zen Cart. A privacy page, shipping information page, terms page, brand landing page, help page, or promotional page may have different target handling depending on whether it needs navigation placement, footer placement, sidebox visibility, metadata, or template control.

CMS Pages should be mapped to the right Zen Cart content structure. Blog Posts are not native Zen Cart core behavior unless the target store uses a plugin or custom implementation to support them.

### Templates, Sideboxes, and Storefront Presentation Meaning <a href="#templates-sideboxes-and-storefront-presentation-meaning" id="templates-sideboxes-and-storefront-presentation-meaning"></a>

Zen Cart storefront presentation depends on templates, template overrides, layout settings, sideboxes, image handling, language files, and custom files. Migrated data can be present in the database while the storefront still displays it differently from the source store.

A category, product, EZ-Page, or content value should therefore be reviewed in its displayed context. Product names, descriptions, attributes, images, sidebox links, navigation placement, and metadata may all require target theme or template adjustment before the migrated result feels complete.

### Plugins, Custom Fields, Custom Tables, and External References <a href="#plugins-custom-fields-custom-tables-and-external-references" id="plugins-custom-fields-custom-tables-and-external-references"></a>

Zen Cart stores often use plugins, modules, custom code, custom database tables, import/export utilities, analytics scripts, ERP feeds, shipping integrations, accounting systems, product-feed generators, SEO modules, or custom admin workflows. These layers can hold business meaning that does not exist in Zen Cart core.

Plugin-owned and custom data should be separated from ordinary product, customer, order, and content migration. If the data must remain available after migration but depends on unsupported tables, custom fields, custom modules, or external identifiers, it should be reviewed under Custom Service.

| Custom or plugin-dependent source data | Likely interpretation in Zen Cart planning                                                                                    |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Custom product fields                  | Review whether they become product fields, attributes, meta values, plugin data, or Custom Service scope.                     |
| Custom order fields                    | Check whether customer service or finance needs them in order history; unsupported fields may need Custom Service.            |
| Custom customer fields                 | Review account, B2B, approval, tax, loyalty, or membership meaning separately from standard customer data.                    |
| SEO plugin data                        | Confirm whether metadata, URL structures, redirects, canonical values, or page titles need mapping or separate configuration. |
| External system IDs                    | Preserve only when they are needed by ERP, accounting, fulfillment, feeds, reporting, or support workflows.                   |
| Import/export plugin data              | Confirm whether the target store will use the same plugin, a replacement plugin, or a custom workflow.                        |

### SEO, URLs, Meta Tags, and Redirect Meaning <a href="#seo-urls-meta-tags-and-redirect-meaning" id="seo-urls-meta-tags-and-redirect-meaning"></a>

Zen Cart stores can depend heavily on product URLs, category URLs, EZ-Page links, relative URLs, meta tags, SEO plugin behavior, redirects, SSL, and domain configuration. A source URL may not have the same target structure by default.

SEO migration should distinguish between record metadata and routing behavior. Product and category meta tags may be part of the migrated record plan, while URL rewrites, canonical behavior, redirects, SSL settings, and domain changes may need separate target configuration or Custom Service review.

### What Migrated Zen Cart Data Must Prove <a href="#what-migrated-zen-cart-data-must-prove" id="what-migrated-zen-cart-data-must-prove"></a>

A successful Zen Cart data translation should prove that business meaning survived the move, not only that records exist. Products should appear in the right categories. Attributes should create the expected buying choices. Customers should remain understandable. Orders should preserve useful history. EZ-Pages and content should appear in the right navigation context. SEO values should be visible where they matter. Plugin-owned and custom data should be either preserved, replaced, excluded with agreement, or reviewed under Custom Service.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Zen Cart data-model differences are strongest where source stores use modern variants, custom options, plugin-owned fields, external systems, or custom checkout behavior. The target store can support many practical commerce structures, but migration quality depends on translating source meaning into Zen Cart’s category, product, attribute, customer, order, module, template, plugin, and content model.

Before accepting a Demo Migration result, review complex products, attribute-heavy products, categories, linked products, customer records, historical orders, discounts, coupons, gift certificates, EZ-Pages, metadata, custom fields, plugin-dependent records, and external identifiers. This gives the clearest evidence of whether the migration can remain within standard service capability or should involve Add-ons or Custom Service review.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do Zen Cart attributes need special review during migration?**

Zen Cart uses option names, option values, and product attributes to represent many shopper selections. Source variants, personalization fields, downloads, price differences, weight differences, and required choices may not translate correctly unless their target attribute behavior is reviewed.

**Are source product variants always migrated as Zen Cart products?**

Not always. Some source variants may become Zen Cart attributes assigned to a product, while others may need a separate product structure or Custom Service review. The correct handling depends on how the variant affects selection, price, inventory, shipping, and order history.

**Can CMS Pages and Blog Posts migrate into Zen Cart the same way?**

CMS Pages may fit Zen Cart content structures such as EZ-Pages, define pages, or other informational page handling. Blog Posts are not native Zen Cart core behavior unless the target store uses a plugin or custom implementation that supports them.

**Does migrating historical payment and shipping labels configure checkout?**

No. Historical order labels help preserve order readability, but live payment, shipping, tax, coupon, gift-certificate, and order-total behavior must be configured and tested in the target Zen Cart store.

**When does custom Zen Cart data need Custom Service review?**

Custom Service review is needed when the migration must preserve unsupported plugin data, custom fields, custom database tables, custom checkout logic, external system identifiers, SEO transformation rules, or other behavior that is not handled by standard target structures or available Add-on capability.
