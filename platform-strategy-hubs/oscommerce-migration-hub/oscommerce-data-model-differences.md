# OsCommerce Data Model Differences

Migrating to osCommerce means more than placing source records into a new database. The target store needs to interpret those records through osCommerce product structures, category logic, attributes, properties, product groups, customer groups, order status history, CMS content, sales channels, App Shop modules, themes, and SEO behavior.

This matters because many source platforms use different assumptions for the same business idea. A source option may become an osCommerce attribute, property, product-group relationship, module-owned field, or custom requirement depending on how it was used. A customer group may represent a discount tier, a trade account, a visibility rule, or only a reporting label. An old order may need more than totals and product names to remain useful for service, accounting, fulfillment, or customer support.

The goal of data-model planning is to preserve meaning. Record presence alone is not enough. The migrated store should prove that the target osCommerce structure can support how the business sells, organizes products, serves customers, reads order history, and manages the storefront after migration.

### How osCommerce Interprets Migrated Data <a href="#how-oscommerce-interprets-migrated-data" id="how-oscommerce-interprets-migrated-data"></a>

osCommerce v4 combines open-source e-commerce data structures with administrative configuration, sales channels, CMS content, modules, App Shop extensions, themes, and custom development possibilities. That gives the target store flexibility, but it also means migration planning must identify which data belongs to the platform core and which data depends on modules, custom code, or older source behavior.

| Source-store meaning       | How it may be interpreted in osCommerce                                                                                                                    | What the migrated result must prove                                                                                       |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Product identity           | Product name, SKU or identifier, model, brand, images, descriptions, price, visibility, SEO fields, and category assignment.                               | The product is recognizable, sellable, findable, and attached to the correct catalog context.                             |
| Product choices            | Attributes, properties, product groups, stock-related choices, bundles, downloadable products, or module-supported structures.                             | Shoppers can select the correct choices and the store does not lose pricing, stock, or specification meaning.             |
| Category structure         | Categories, subcategories, menu placement, filters, brands, sales channels, and storefront discovery pages.                                                | Products appear in the correct navigation and discovery paths, not only in the admin catalog.                             |
| Customer records           | Registered customers, guest customers, address books, language, customer groups, B2B or trade context, reviews, and order links.                           | Customer history remains usable and customer segmentation keeps its intended business meaning.                            |
| Historical orders          | Products, totals, taxes, payment method labels, shipping context, status history, invoices, transactions, tracking, comments, and refunds where available. | Orders can be read and interpreted after migration without confusing historical context with live checkout configuration. |
| CMS and content            | CMS Pages, menus, banners, forms, email templates, informational pages, and storefront layout content.                                                     | Content appears in the right target locations and supports the intended customer journey.                                 |
| SEO and URLs               | Product/category/brand page names, metadata, canonical behavior, redirects, sitemap expectations, and high-value landing pages.                            | Important pages remain traceable and target SEO fields support continuity planning.                                       |
| Extensions and custom data | App Shop modules, third-party add-ons, legacy modifications, custom tables, and outside-system identifiers.                                                | Extension-owned data is either included in the agreed scope, reconfigured separately, or reviewed through Custom Service. |

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

Products in osCommerce can carry more than a basic title, description, image, and price. A complete product may depend on identifiers, categories, brands, attributes, properties, product groups, stock behavior, supplier fields, marketing flags, downloadable-product handling, image metadata, reviews, and SEO values.

A source catalog that looks simple at a record-count level can still be complex at a meaning level. For example, one source store may use variants for size and color, another may use options, another may use custom fields, and another may use extension data. In osCommerce, those source structures need to be translated into the closest target structures without losing shopper-facing choice, filter usefulness, or operational stock meaning.

#### Attributes, Properties, and Product Groups <a href="#attributes-properties-and-product-groups" id="attributes-properties-and-product-groups"></a>

Attributes, properties, and product groups should not be treated as interchangeable labels. They may carry different roles:

* **Attributes** often support selectable product choices, such as size, color, material, or other purchase-affecting options.
* **Properties** can describe technical specifications, filterable details, or structured product characteristics.
* **Product groups** can connect products that should be presented together or organized under a shared buying context.
* **Bundles, downloadable products, and special product types** may depend on target capability, extension behavior, or custom handling.

The safest migration planning starts by identifying how the source store uses these structures operationally. If a source option changes price, inventory, image, fulfillment, or purchase behavior, it should not be reduced to plain descriptive text without review.

#### Brands, Categories, and Discovery <a href="#brands-categories-and-discovery" id="brands-categories-and-discovery"></a>

osCommerce can use categories, brands, menus, filters, search, featured/new/sale product views, and sales-channel assignment to shape product discovery. A migrated product can be technically present but commercially misplaced if it is attached to the wrong category, omitted from a sales channel, missing brand context, or disconnected from filters.

Category migration should therefore preserve both hierarchy and storefront meaning. Deep category trees, brand-led browsing, product filters, and landing-page categories should be sampled before accepting the result.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

Customer data in osCommerce may include registered accounts, guest orders, addresses, customer groups, language preferences, reviews, credit-related details, and order history. Source platforms differ in how they define a customer. Some treat every order email as a customer. Others distinguish registered users, guests, wholesale accounts, approved accounts, and customer segments.

During migration, the customer record should preserve enough meaning for the merchant to understand who the customer is and how the store should treat that customer after launch. This is especially important when customer groups affect pricing, tax treatment, visibility, approval, payment access, shipping access, or B2B/trade behavior.

| Customer data area            | Meaning risk                                                                                            | Review priority                                                                      |
| ----------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Registered vs guest customers | Guest buyers may be incorrectly treated as full accounts, or registered users may lose account context. | Confirm account status and order linkage in samples.                                 |
| Address books                 | Billing and shipping addresses may lose relationship or default-address meaning.                        | Validate customers with multiple addresses and varied order history.                 |
| Customer groups               | A simple group label may actually affect pricing, access, tax, or approval.                             | Sample standard, wholesale, trade, and special-price customers.                      |
| Reviews and customer activity | Reviews may be product-owned, customer-owned, moderated, or extension-controlled.                       | Confirm where reviews appear and whether author/customer context remains acceptable. |
| Password expectations         | Source password behavior may not translate directly to the target environment.                          | Plan customer login continuity or reset communication at an expectation level.       |

### Order and Historical Transaction Meaning <a href="#order-and-historical-transaction-meaning" id="order-and-historical-transaction-meaning"></a>

Orders are one of the most sensitive data-model areas because merchants often rely on historical orders for service, refunds, accounting reference, repeat customer support, fulfillment review, and reporting.

In osCommerce, order meaning may include order status, payment method, shipping method, tax, discounts, totals, line items, addresses, customer records, transaction details, invoices, packing slips, tracking numbers, admin comments, customer comments, refunds, and status history. A migrated order that only preserves totals and product names may not be enough for day-to-day use.

The main distinction is between **historical order readability** and **live checkout behavior**. Migration can preserve historical payment and shipping labels, but target checkout still depends on configured osCommerce payment modules, shipping modules, tax settings, zones, currencies, and customer-group rules.

A strong order sample set should include paid, unpaid, partially fulfilled, refunded, discounted, manually edited, multi-status, multi-currency, guest, registered-customer, and tracked-shipment orders where those patterns exist in the source store.

### Storefront, Sales Channel, and CMS Meaning <a href="#storefront-sales-channel-and-cms-meaning" id="storefront-sales-channel-and-cms-meaning"></a>

osCommerce storefront meaning can involve more than the product catalog. CMS Pages, menus, banners, forms, informational pages, email templates, design blocks, theme areas, language content, and sales channels may all affect the customer experience.

Source platforms may store content as pages, blocks, blog-like articles, theme sections, menu items, landing pages, or app-owned content. In osCommerce, that content must be interpreted through the target CMS and design structures where appropriate. Some content can migrate as CMS Pages, while other layout behavior may need theme work or post-migration configuration.

Sales-channel behavior also needs attention. If products, languages, currencies, promotions, or storefront content are assigned differently across channels, validation should not be limited to the default storefront.

### SEO, URL, and Metadata Meaning <a href="#seo-url-and-metadata-meaning" id="seo-url-and-metadata-meaning"></a>

SEO data often changes structure during migration. Source stores may use product URLs, category paths, canonical URLs, redirects, meta titles, meta descriptions, image alt text, brand URLs, page names, XML sitemaps, or app-generated SEO fields.

In osCommerce, these values should be reviewed as connected storefront signals. A product may have the correct name and price but still lose search continuity if its target page name, category path, canonical behavior, metadata, or redirect plan is incomplete.

SEO-sensitive migrations should prepare a prioritized sample of high-value URLs rather than trying to treat every URL as equally important. Product pages, category pages, brand pages, CMS Pages, and landing pages with traffic or backlink value deserve early review.

### Extensions, Modules, and Custom Data <a href="#extensions-modules-and-custom-data" id="extensions-modules-and-custom-data"></a>

osCommerce’s extension and App Shop ecosystem can affect catalog, checkout, payment, shipping, customer, B2B, marketplace, reporting, SEO, social login, integration, and design behavior. Some extension behavior can be reconfigured in the target store. Some extension-owned records may require mapping. Some custom tables or source-specific logic may require Custom Service.

This distinction is important:

* **Standard platform data** can often be interpreted through ordinary target structures.
* **Configurable target behavior** may need setup or post-migration adjustment rather than data migration.
* **Extension-owned data** may need scope review before it can be included.
* **Custom code and custom database tables** require Custom Service review because the business meaning is not guaranteed to match standard osCommerce structures.

A source store should be reviewed for installed add-ons, custom modules, database modifications, custom fields, outside-system identifiers, and integration-owned records before migration scope is considered stable.

### Legacy osCommerce and Forked-Platform Meaning <a href="#legacy-oscommerce-and-forked-platform-meaning" id="legacy-oscommerce-and-forked-platform-meaning"></a>

Older osCommerce installations can differ substantially from osCommerce v4. Long-running stores may have accumulated custom code, old add-ons, modified checkout behavior, custom database columns, template overrides, or fork-specific data structures.

Related platforms or historical forks should not be treated as the same platform merely because they share lineage. If the source store is an older osCommerce build, a fork, or a heavily modified installation, the data model must be reviewed on its own terms. The migration question becomes: what is the actual source structure, and how should that structure be interpreted inside the intended osCommerce target?

### What Migrated Data Must Prove in osCommerce <a href="#what-migrated-data-must-prove-in-oscommerce" id="what-migrated-data-must-prove-in-oscommerce"></a>

A successful osCommerce migration should prove that the target data works as a connected commerce system. It should not be accepted only because expected record counts appear in the admin area.

The migrated result should prove that:

* products are sellable and assigned to the right catalog context;
* attributes, properties, groups, and special product structures still carry their intended meaning;
* categories, brands, filters, menus, and sales channels support product discovery;
* customer records, groups, addresses, and order links remain interpretable;
* historical orders preserve enough context for service and back-office reference;
* CMS Pages, content, metadata, and high-value URLs support storefront continuity;
* payment, shipping, tax, and checkout labels are not confused with live target configuration;
* extension-owned or custom data has been included, excluded, mapped, or escalated intentionally;
* older-version or forked-source structures have not been treated as if they were clean modern osCommerce data.

### Conclusion <a href="#conclusion" id="conclusion"></a>

osCommerce can preserve detailed commerce meaning when source data is translated into the right target structures. The most important work is not copying data fields one by one, but identifying what each field, relationship, option, group, status, module, and content item means in the business. Products, customers, orders, content, URLs, extensions, and custom records all need interpretation before the target store can be judged as migration-ready.

Use Demo Migration samples to test the structures that carry real business meaning: complex products, customer groups, varied order histories, high-value URLs, CMS Pages, multilingual or multicurrency content, module-dependent records, and any legacy or custom source behavior. If those samples cannot be interpreted cleanly in osCommerce, mapping, configuration, Add-ons, or Custom Service review should be considered before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Why can product options change meaning when migrating to osCommerce?**

Different platforms represent options, variants, specifications, filters, and product relationships in different ways. In osCommerce, those details may need to become attributes, properties, product groups, stock-related choices, or module-supported structures. The correct target structure depends on how the source data affects buying, filtering, pricing, and inventory.

**Are categories and menus the same thing in osCommerce migration planning?**

No. Categories organize products, while menus and storefront navigation shape how shoppers reach those products. A migration can preserve category hierarchy while still needing separate review of menu placement, landing pages, filters, sales channels, and storefront discovery paths.

**Will historical payment and shipping information make checkout work automatically?**

No. Historical orders can preserve payment and shipping labels for reference, but live checkout depends on target payment modules, shipping modules, tax settings, zones, currencies, and customer-group rules. Historical order readability and live checkout readiness should be validated separately.

**How should extension-owned data be handled?**

Extension-owned data should be identified before migration scope is finalized. Some extension behavior can be reconfigured after migration, some records may fit standard or Add-on-supported mapping, and custom or module-specific data may require Custom Service review.

**Why do old osCommerce stores need extra data-model review?**

Older osCommerce stores often include legacy add-ons, custom database changes, modified checkout logic, template overrides, or fork-related structures. These differences can change the meaning of products, customers, orders, and extensions, so the source installation should be reviewed before assuming it matches a clean osCommerce v4 target model.
