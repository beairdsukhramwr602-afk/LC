# Shift4Shop Data Model Differences

A Shift4Shop migration should translate source data into the way Shift4Shop organizes products, storefront content, customers, orders, pricing, SEO routes, and business rules. The main challenge is not only whether records can be moved. The harder question is whether the migrated records still mean the same thing inside a hosted Shift4Shop store.

Many source platforms store commercial meaning in different places. Product choices may live in attributes, variants, option sets, custom fields, app records, scripts, or theme-dependent layouts. Customer pricing may be controlled by groups, price levels, custom notes, ERP identifiers, coupon rules, or manual staff procedures. Storefront content may be attached to product pages, category pages, CMS Pages, Blog Posts, landing pages, menu structures, or page-builder blocks. A clean Shift4Shop migration depends on classifying those meanings before deciding how they should be represented.

### How Shift4Shop Changes Data Interpretation <a href="#how-shift4shop-changes-data-interpretation" id="how-shift4shop-changes-data-interpretation"></a>

Shift4Shop is a hosted commerce platform, so many future-store decisions are shaped by the target platform’s native product management, storefront administration, SEO tools, customer tools, promotional features, and integration options. Data that was flexible or developer-controlled in a source store may need to become more structured in Shift4Shop.

That difference affects how migration records should be interpreted. A source field may look like a simple product attribute but actually control buying behavior. A customer note may look descriptive but represent wholesale approval. A category may look like a navigation label but carry SEO value. A historical order status may look like a normal order field but reflect a custom fulfillment workflow that no longer exists in the same form.

| Source-store meaning         | Shift4Shop planning question                                                                            |
| ---------------------------- | ------------------------------------------------------------------------------------------------------- |
| Product attributes           | Are they descriptive details, selectable options, search/filter information, or operational references? |
| Product choices              | Should they become options, Advanced Options, separate products, or rebuilt target-side configuration?  |
| Categories                   | Do they support browsing, SEO, merchandising, internal organization, or outdated source structure?      |
| Customer groups              | Do they only segment buyers, or do they control pricing, tax, access, and order behavior?               |
| Discounts and quantity rules | Are they active selling rules, historical promotions, wholesale logic, or obsolete campaigns?           |
| Content pages                | Do they support conversion, SEO, policy communication, product education, or only legacy navigation?    |
| Integration fields           | Are they supported fields, external IDs, app-owned data, or Custom Service requirements?                |

A data model review should therefore begin with business meaning. Once the meaning is clear, the migration path can decide whether standard migration behavior is enough, whether Add-ons should adjust supported filtering or mapping, or whether Custom Service is needed for unsupported records, app-owned data, external identifiers, or bespoke transformation.

### Product Records, Options, and Advanced Options <a href="#product-records-options-and-advanced-options" id="product-records-options-and-advanced-options"></a>

Shift4Shop product data can include more than a product name, SKU, price, image, and description. Product options, variants, Advanced Options, option templates, product images, video, categories, inventory, product reviews, quantity discounts, and detailed content can all affect how the product works in the storefront. That makes product meaning one of the most important data-model areas to review before migration.

Source platforms often use different structures for product choice. A Shopify source store may rely on variants and metafields. A WooCommerce source may rely on attributes, variations, plugins, and custom fields. A Magento or Adobe Commerce source may use product types, configurable products, attribute sets, customer groups, and custom modules. A legacy or Custom Platform source may store choices in a custom table or hard-coded form.

A Shift4Shop migration should decide what each product choice actually does.

| Product-choice pattern           | Better interpretation before migration                                                                              |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Size, color, material, pack size | Usually buying choices that may need option or variant-style handling.                                              |
| Price-changing options           | May need Advanced Options or a target-side pricing decision.                                                        |
| Inventory-changing options       | Should be checked carefully because stock meaning may attach to the option, not only the parent product.            |
| Option templates                 | Useful when many products share the same buying choices and should remain easy to administer.                       |
| Technical specifications         | Often better treated as product information, tabs, custom fields, or structured content rather than buying options. |
| Bundled or grouped choices       | Need review because bundle behavior may not mean the same thing across platforms.                                   |

The risk is flattening product complexity. If all source fields become static descriptions, buyers may lose the ability to choose the right version. If all descriptive fields become options, the target catalog may become harder to manage. A strong migration separates product information from product behavior.

### Categories, SmartCategories, and Storefront Discovery <a href="#categories-smartcategories-and-storefront-discovery" id="categories-smartcategories-and-storefront-discovery"></a>

Categories and subcategories in Shift4Shop can support browsing, storefront organization, SEO discovery, merchandising, and customer understanding. Source stores may use categories differently. Some platforms distinguish categories from collections, menus, tags, brands, filters, or dynamic product groups. Some legacy stores use categories for internal organization rather than customer-facing navigation.

Shift4Shop also offers dynamic category-style behavior such as SmartCategories, which can group products by rules such as active discounts, release date, free shipping, or keyword-based criteria. That matters because not every source category should be treated as a static category in the target store. Some source groupings may be better rebuilt as dynamic merchandising logic, while others should remain stable navigation structures.

| Source grouping              | Shift4Shop interpretation risk                                             |
| ---------------------------- | -------------------------------------------------------------------------- |
| Main categories              | Usually important for navigation and SEO continuity.                       |
| Deep subcategories           | May help browsing or may preserve obsolete source clutter.                 |
| Tags or labels               | May not have the same role as categories and should be classified.         |
| Sale or new-arrival groups   | May be better handled as dynamic or campaign-driven organization.          |
| Brand/manufacturer groupings | May need mapping, metadata, filters, or navigation decisions.              |
| SEO landing categories       | Should be reviewed as URL and content assets, not only product containers. |

Category migration should preserve usable discovery, not only hierarchy. A target store can have the right number of categories and still be difficult to browse if source groupings are carried forward without cleanup.

### Customer Data, Groups, and Buyer Treatment <a href="#customer-data-groups-and-buyer-treatment" id="customer-data-groups-and-buyer-treatment"></a>

Customer records in Shift4Shop can carry different meanings depending on the business model. For a simple retail store, a customer record may primarily support contact information, order history, account access, and marketing. For wholesale, B2B, reseller, or mixed B2C/B2B stores, customer data may also affect pricing, tax treatment, visibility, minimum order behavior, reorder patterns, and service expectations.

Customer groups should be reviewed by operational meaning. A group may represent a loyalty segment, a wholesale approval level, a tax-exempt buyer type, a distributor class, a region, a VIP buyer, or an internal reporting label. Those meanings are not interchangeable.

| Customer data area        | Migration meaning to confirm                                                                       |
| ------------------------- | -------------------------------------------------------------------------------------------------- |
| Account details           | Whether names, emails, phone numbers, addresses, and account records support customer lookup.      |
| Customer groups           | Whether groups control pricing, visibility, tax status, or only segmentation.                      |
| Customer-specific pricing | Whether price treatment is customer-level, group-level, quantity-based, or external-system-driven. |
| Tax-exempt status         | Whether exemption is supported by target configuration, customer data, or manual review.           |
| Historical order links    | Whether customer records connect usefully to order history.                                        |
| External IDs              | Whether ERP, CRM, accounting, or sales-rep identifiers must be preserved through Custom Service.   |

A migration can move customer names and emails correctly while still losing buyer treatment. That is why customer groups, pricing evidence, and representative order samples should be reviewed together.

### Pricing, Discounts, Coupons, and Quantity Rules <a href="#pricing-discounts-coupons-and-quantity-rules" id="pricing-discounts-coupons-and-quantity-rules"></a>

Pricing data is rarely just one price field. A Shift4Shop target store may need ordinary product pricing, sale pricing, quantity discounts, customer-group pricing, customer-specific price lists, coupons, gift certificates, tax rules, shipping-related charges, or promotion logic. Source stores may define these rules differently, especially when promotions come from apps, modules, custom code, or ERP systems.

The data model question is whether each rule should migrate as a record, be rebuilt in Shift4Shop, be retired, or be handled by an integration. Active commercial rules should receive priority because they affect revenue immediately after launch. Historical or expired promotions may be useful for reference, but they should not be mixed with rules that must work in the new storefront.

| Rule type             | Review question                                                                   |
| --------------------- | --------------------------------------------------------------------------------- |
| Regular product price | Is it the active selling price or only a base price for later rules?              |
| Sale price            | Is it active, scheduled, expired, customer-specific, or campaign-related?         |
| Quantity discount     | Does it apply to all buyers, selected groups, B2B buyers, or product families?    |
| Coupon                | Is the coupon active, limited, reusable, customer-specific, or historical?        |
| Gift certificate      | Is it a product, payment-like credit, code record, or customer-service liability? |
| External price list   | Is the source of truth inside the store, ERP, CRM, or another system?             |

A pricing review should not aim to migrate every old promotion. It should preserve rules needed for launch and classify the rest as historical, retired, manually rebuilt, or outside the migration scope.

### Orders, Statuses, and Operational History <a href="#orders-statuses-and-operational-history" id="orders-statuses-and-operational-history"></a>

Order data in Shift4Shop migration planning should be interpreted as operational history, not only as transaction rows. Orders may support customer service, finance review, refunds, reorders, B2B account support, warranty questions, and fulfillment reference. A source order can contain line items, taxes, discounts, shipping, payment references, status history, customer notes, staff notes, tracking numbers, external IDs, and integration-created fields.

The main data-model difference is that order history may not reproduce every source workflow. Some statuses may be platform-specific. Some payment details may only be historical context. Some fulfillment or refund information may need staff-readable preservation rather than live workflow recreation.

| Order component         | Migration interpretation                                                     |
| ----------------------- | ---------------------------------------------------------------------------- |
| Order status            | Should be mapped to useful target status meaning, not copied blindly.        |
| Payment references      | Should preserve historical context without implying live payment setup.      |
| Refunds and adjustments | Need representative validation because exceptions often expose mapping gaps. |
| Shipping and tracking   | Should remain readable for support and fulfillment history.                  |
| Customer link           | Should connect orders to the right buyer when supported.                     |
| External IDs            | May need Custom Service when outside-system reconciliation depends on them.  |

Order migration should be judged by staff usefulness. A technically imported order that cannot explain what happened, who bought it, how it was fulfilled, or how it connects to outside systems may not meet the business need.

### SEO Routes, Extra Pages, Blog Posts, and Content Records <a href="#seo-routes-extra-pages-blog-posts-and-content-records" id="seo-routes-extra-pages-blog-posts-and-content-records"></a>

Storefront content is a major source of data-model mismatch. Shift4Shop can include product pages, category pages, Extra Pages, Blog Posts, SEO metadata, navigation structures, product reviews, product Q\&A, and other content-related records. Source stores may store similar information in CMS Pages, Blog Posts, page builders, apps, static files, theme sections, or custom templates.

The migration plan should classify content by function. Some pages are essential for SEO continuity. Some help customers understand products. Some support policies, compliance, trust, or brand explanation. Some are obsolete and should not be recreated. Treating all content as equal creates unnecessary work; treating content as decorative creates launch risk.

| Content record           | Planning question                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------ |
| Product URLs             | Which routes need preservation, redirects, or SEO review?                                        |
| Category URLs            | Which categories carry search value or important navigation value?                               |
| Extra Pages / CMS Pages  | Which pages support trust, policy, conversion, or customer education?                            |
| Blog Posts               | Which posts carry organic traffic, internal links, or product discovery value?                   |
| Product reviews and Q\&A | Which records support buyer confidence and product-page freshness?                               |
| Embedded media           | Which files, scripts, forms, or layout elements need manual rebuilding or Custom Service review? |

Content migration should preserve useful storefront meaning. A page title and body text may migrate, but the result still needs review if the source page depended on custom layout, embedded forms, app widgets, or old routes.

### Integrations, Custom Fields, and 3dcart-Era Records <a href="#integrations-custom-fields-and-3dcart-era-records" id="integrations-custom-fields-and-3dcart-era-records"></a>

Shift4Shop can work with integrations and API-connected workflows, but integration-owned data should be handled carefully. Source stores may use ERP, CRM, accounting, shipping, fulfillment, tax, marketplace, review, email, analytics, or payment systems that create or modify records. Some fields may exist only for an outside system and may not have a native Shift4Shop destination.

Older 3dcart-era records can also appear in exports, staff notes, admin references, integration labels, or historical documentation. Those references can be useful clues, but they should be interpreted against the current Shift4Shop target plan. A legacy label does not automatically prove current compatibility or migration scope.

| Data source                               | Handling path                                                                |
| ----------------------------------------- | ---------------------------------------------------------------------------- |
| Supported native field                    | Standard migration or supported mapping may be enough.                       |
| Supported field needing changed placement | Add-ons may help when mapping or configuration is within supported behavior. |
| App-owned or integration-owned data       | Custom Service or separate integration work may be needed.                   |
| Custom fields and external IDs            | Custom Service review is appropriate when they must remain operational.      |
| 3dcart-era labels                         | Use as source context, then confirm the actual field, record, or workflow.   |
| Target-side integration setup             | Usually configuration and testing, not ordinary data migration.              |

The safest approach is to identify the system of record for each important field. When data is only meaningful because an outside system uses it, migration planning should include that outside system, not only the Shift4Shop admin view.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shift4Shop data model differences are most important where ordinary-looking records carry commercial meaning. Product options can control price and stock. Categories can support navigation and SEO. Customer groups can control buyer treatment. Promotions can affect revenue. Orders can support operational history. Content can preserve discovery and trust. Integrations can own fields that are not native store data.

A strong Shift4Shop migration should therefore translate source records by function, not only by field name. The target result should preserve the meaning that helps buyers shop, staff manage the store, and the business continue operating after launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do product options matter so much in a Shift4Shop migration?**

Product options can affect buying choices, price, inventory, fulfillment, and product-page clarity. They should be reviewed separately from descriptive specifications because not every source attribute should become a selectable option.

**Are Shift4Shop categories the same as source-store categories or collections?**

Not always. Source stores may use categories, collections, tags, menus, or dynamic groups differently. Shift4Shop category planning should preserve useful browsing and SEO meaning rather than mechanically copying every source grouping.

**Should customer groups always migrate as-is?**

No. Customer groups should be reviewed by purpose. A group used only for marketing segmentation is different from a group controlling wholesale pricing, tax exemption, visibility, or B2B ordering.

**Can historical orders recreate the original source workflow?**

Historical orders should preserve useful support and operational context, but they do not automatically recreate old payment, fulfillment, refund, or integration workflows inside Shift4Shop.

**When do custom fields require Custom Service?**

Custom Service should be considered when custom fields, app-owned data, external IDs, or integration-created records must remain operational and do not fit supported migration behavior.
