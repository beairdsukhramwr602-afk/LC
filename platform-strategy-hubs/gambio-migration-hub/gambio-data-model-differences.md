# Gambio Data Model Differences

Gambio migration planning should treat data as operating structure, not as a flat export of products, customers, and orders. A store can appear complete at record level while still losing selling meaning if product options, categories, stock behavior, content pages, legal pages, customer context, or storefront paths are interpreted too casually in the Target Platform.

Gambio adds a specific planning question that not every platform raises in the same way: the merchant must understand whether the target environment is Gambio Cloud or self-hosted Gambio. That decision changes responsibility for hosting, installation, updates, support expectations, customization surface, and sometimes the way technical evidence is gathered before migration. The data model must therefore be read together with the chosen operating model.

### How Gambio Changes Data Interpretation <a href="#how-gambio-changes-data-interpretation" id="how-gambio-changes-data-interpretation"></a>

A Gambio Target Platform receives migrated data into a shop structure that combines catalog records, storefront presentation, content management, checkout configuration, customer accounts, order history, and environment responsibility. The same source data can have different meaning depending on how it was used in the original store.

A product option may be a simple shopper choice, or it may represent stock, price, fulfillment, image, or SKU logic. A category may be a browsing container, or it may define SEO architecture. A content page may be a marketing page, or it may carry legal and trust meaning. A customer record may be a simple account, or it may be linked to B2B pricing, tax treatment, or repeated service history.

| Source data area          | Gambio interpretation question                                                              | What must be preserved                                                                                       |
| ------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Products and articles     | Does the product remain sellable, readable, and manageable in Gambio?                       | Name, SKU, price, images, stock, options, downloads, category placement, and merchandising meaning.          |
| Categories and navigation | Does the source discovery structure translate into Gambio category and menu logic?          | Browsing paths, parent-child relationships, high-value category pages, and SEO-sensitive structure.          |
| Options and variants      | Are shopper choices simple selections, commercial rules, or inventory-sensitive structures? | Option labels, price impact, stock assumptions, order-line clarity, and product selection accuracy.          |
| Customers and orders      | Do accounts and historical orders remain useful for service and reporting reference?        | Customer identity, addresses, order totals, product lines, tax/shipping/payment context, and status meaning. |
| Content and legal pages   | Are informational pages still accessible and placed correctly?                              | CMS Pages, policy pages, trust content, landing pages, and internal links.                                   |
| Operating model           | Is Gambio Cloud or self-hosted Gambio the intended target?                                  | Correct assumptions about updates, hosting, maintenance, technical access, and customization.                |

These distinctions help define what the migration must prove before the merchant treats the transferred data as operationally ready.

### Product and Article Data <a href="#product-and-article-data" id="product-and-article-data"></a>

Gambio commonly uses the language of articles for sellable products. That matters because source platforms may separate products, variants, options, digital goods, bundles, and custom product types in ways that do not match Gambio one-to-one. The migration question is not whether every source product can be counted. The question is whether the resulting Gambio catalog can be managed and purchased without losing commercial meaning.

Basic product fields such as title, SKU, description, price, images, and inventory are only the visible layer. Real migration difficulty usually appears in the relationships around the product: category placement, option values, download handling, image galleries, stock behavior, base-price expectations, search and filter visibility, and how product data appears in historical order lines.

Gambio’s catalog model supports common merchant needs: many articles, multiple images per article, product options for choices such as size or color, stock management per article, downloadable articles, and categories with subcategories. That breadth is useful for migration planning because typical catalog structures can be represented, but it does not remove the need to translate source-side logic accurately.

A source platform with simple physical products usually maps more cleanly. A source platform with option-level stock, app-managed variants, bundle logic, subscription products, custom product fields, or external inventory references needs closer interpretation. In those cases, product data is not just content; it is a commercial rule system.

### Options, Variants, Stock, and Downloadable Products <a href="#options-variants-stock-and-downloadable-products" id="options-variants-stock-and-downloadable-products"></a>

Options and variants deserve separate attention because they are often where migration quality becomes visible to shoppers. A color or size selector seems simple until it affects price, image display, SKU selection, stock reduction, shipping weight, or fulfillment instructions. If the source platform stores those relationships differently from Gambio, the migrated product may look present but behave incorrectly.

Gambio can let shoppers choose variations through product options and can reduce inventory when an article is sold, while stock control can also be disabled when the merchant does not want to use that functionality. These capabilities create two distinct planning questions: does the source store expect option-level or article-level inventory behavior, and should the target Gambio store use stock control in the same way after launch?

Downloadable products add another layer. A downloadable article is not simply a product with no shipping. It can involve file access, customer account permissions, order status, historical purchase access, and post-payment availability. If a source store manages files through an app, external storage, membership area, or custom logic, that structure may need Custom Service review rather than ordinary field mapping.

| Product structure       | Lower-risk interpretation                                  | Higher-risk interpretation                                                           |
| ----------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Simple physical product | One article with direct price, SKU, image, and stock.      | Product depends on external fulfillment or custom stock calculation.                 |
| Shopper option          | Size or color selection with clear labels.                 | Option changes stock, price, SKU, weight, images, or fulfillment logic.              |
| Downloadable product    | Download access is standard and tied to the product/order. | Files are stored externally or controlled by custom membership logic.                |
| Image-heavy product     | Multiple images support product presentation.              | Images are variant-specific, externally hosted, or controlled by source theme logic. |
| Product grouping        | Categories and options explain buying choices.             | Bundles, kits, or configurable sets depend on unsupported source structures.         |

The strongest validation samples should include products from both columns. Simple examples prove baseline migration. Complex examples prove whether the migration preserves selling meaning.

### Categories, Navigation, and Discovery Structure <a href="#categories-navigation-and-discovery-structure" id="categories-navigation-and-discovery-structure"></a>

Categories in Gambio should be treated as discovery architecture. They help shoppers find products, understand assortment structure, and move through the storefront. A source platform may use categories, collections, tags, menus, filters, brands, landing pages, or custom navigation blocks to create the same customer journey. Migration planning must identify which of those structures should become Gambio categories, which should become content/navigation work, and which should be rebuilt separately.

Gambio can represent categories and subcategories, which supports deeper catalog structures. That capability does not automatically solve source stores where categories carry multiple meanings. A product may live in a merchandising collection, a seasonal collection, a technical category, and a sale category. A direct migration without interpretation may create clutter, duplicate paths, or poor discoverability.

SEO-sensitive categories also require attention. If the source store receives organic traffic through category pages, the migration scope must consider page titles, metadata, URLs, redirects, internal links, and whether the new Gambio category structure supports the same browsing intent. Category data is therefore not only a database layer; it affects discoverability and post-launch revenue.

### Content Pages, Legal Pages, and Storefront Meaning <a href="#content-pages-legal-pages-and-storefront-meaning" id="content-pages-legal-pages-and-storefront-meaning"></a>

Gambio supports editorial and content pages through its content management capabilities. For migration planning, that means CMS Pages should be treated as part of the customer experience, not as optional extras. A source store may use content pages for shipping information, returns, privacy, legal notices, size charts, brand storytelling, buying guides, landing pages, or campaign pages.

In a Gambio context, content pages can be especially important because the platform is commonly positioned with legal, support, and German-market expectations. Cloud packages may include legal-text handling through selected partners, while self-hosted merchants may carry more responsibility for ensuring that their storefront content and legal content are current and correctly placed. Migration does not replace that legal review, but it should preserve the pages and relationships that the merchant expects to keep.

Content page migration should therefore answer three questions. Which pages must be migrated? Which pages must be refreshed or reconfigured in Gambio? Which pages require redirects, menu placement, or legal review before launch? Treating all content as equal can bury important trust pages and over-preserve obsolete marketing pages.

### Customer and Order Meaning <a href="#customer-and-order-meaning" id="customer-and-order-meaning"></a>

Customer data has value only when it remains connected to commercial context. Names, emails, addresses, and account records are useful, but many stores depend on more: customer groups, tax status, repeat purchase history, invoice expectations, newsletter consent, B2B relationships, and order history. If the source platform uses tags, roles, memberships, or customer groups to express those relationships, the migration must identify which meanings belong in Gambio and which are external to the migrated data.

Order history must remain readable. A migrated order should help the merchant answer practical questions: what was purchased, by whom, at what price, with which tax/shipping/payment context, and in what status. Historical orders are often used for customer service, accounting reference, warranty handling, and repeat purchase support. If option labels, product names, discounts, tax totals, payment names, or status meanings are unclear after migration, the data may technically exist but fail operationally.

The most useful Demo Migration samples should include ordinary orders, discounted orders, orders with product options, orders with downloads, orders from different customer types, and orders with different payment or shipping methods. Gambio validation should focus on whether staff can understand the order without returning to the source store.

### Cloud and Self-Hosted Data Responsibilities <a href="#cloud-and-self-hosted-data-responsibilities" id="cloud-and-self-hosted-data-responsibilities"></a>

Gambio Cloud and self-hosted Gambio create different responsibilities around the same data. In Gambio Cloud, hosting, installation, updates, and support are part of the managed environment. In self-hosted Gambio, the merchant is responsible for hosting, installation, maintenance, and updates while receiving greater flexibility for customization and integrations.

This distinction affects data-model interpretation because technical access, custom code review, extension behavior, and integration recreation may differ by environment. A source store with extensive custom database fields, modified templates, custom checkout behavior, or integration-owned data may be better suited to a self-hosting conversation, but that does not mean migration becomes automatic. It means the merchant needs clearer evidence about what data is standard, what is custom, and what must be rebuilt.

Cloud-oriented merchants should avoid assuming that every source customization can be carried forward. Self-hosting-oriented merchants should avoid assuming that greater technical freedom removes the need for scope control. In both cases, the migration must distinguish supported data, Gambio configuration, implementation work, and Custom Service needs.

### Data Translation Priorities for Gambio <a href="#data-translation-priorities-for-gambio" id="data-translation-priorities-for-gambio"></a>

A Gambio data-model review should begin by separating record identity from selling behavior. Record identity answers whether a product, customer, order, category, or CMS Page exists in the target. Selling behavior answers whether that record still works as expected in the new store. The second question is often more important, because customers do not experience a migrated database; they experience catalog choices, navigation, content, prices, stock, checkout context, and post-order service.

When a Source Platform uses a different product architecture, data can look correct while meaning changes. A source variant may become a product option, a landing page may become a CMS Page, a navigation node may become a category, or an integration-generated field may have no direct target equivalent. The review should identify these meaning changes before Full Migration so they can be handled through mapping, configuration, Add-ons, Custom Service, or separate target setup.

The practical translation priority for Gambio is to protect commercial meaning first and record form second. A source product should become a usable Gambio article, not merely a row with a name and price. A source category should become a navigable structure, not only a parent-child relationship. A source content page should remain customer-facing and findable, not only text moved into a new field.

The most important review questions are therefore cause-and-effect questions. If a source option changes price, stock, image, or fulfillment expectation, what should that mean in Gambio? If a source category carried SEO value, how should navigation and URL continuity be reviewed? If a source order included discounts, tax behavior, shipping context, or downloadable items, what does staff need to see in Gambio to support the customer later? These questions turn data mapping into migration planning.

Entity Points can help estimate scope when eligible new Products, Customers, Orders, or Blog Posts are migrated for the first time, but they should not be used as a substitute for data-model review. A small number of complex records can create more translation work than a larger number of ordinary records. Gambio planning should therefore combine count-based scope with behavior-based review.

The practical translation priority for Gambio is to protect commercial meaning first and record form second. A source product should become a usable Gambio article, not merely a row with a name and price. A source category should become a navigable structure, not only a parent-child relationship. A source content page should remain customer-facing and findable, not only text moved into a new field.

The most important review questions are therefore cause-and-effect questions. If a source option changes price, stock, image, or fulfillment expectation, what should that mean in Gambio? If a source category carried SEO value, how should navigation and URL continuity be reviewed? If a source order included discounts, tax behavior, shipping context, or downloadable items, what does staff need to see in Gambio to support the customer later? These questions turn data mapping into migration planning.

Entity Points can help estimate scope when eligible new Products, Customers, Orders, or Blog Posts are migrated for the first time, but they should not be used as a substitute for data-model review. A small number of complex records can create more translation work than a larger number of ordinary records. Gambio planning should therefore combine count-based scope with behavior-based review.

The strongest Gambio data-model review starts with representative records, not only totals. Record counts tell the merchant how large the project is. Representative records reveal whether the target structure preserves meaning.

| Priority                            | Why it matters                                                           | Best sample evidence                                                                                             |
| ----------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Product options and stock           | They affect purchase accuracy and fulfillment confidence.                | Products with size/color choices, stock reduction, price differences, and order-line examples.                   |
| Category hierarchy                  | It shapes browsing, SEO, and product discovery.                          | Deep categories, products in multiple categories, and high-traffic category URLs.                                |
| CMS Pages and legal content         | They affect trust, compliance context, and navigation.                   | Terms, shipping, returns, privacy, legal notices, guides, and landing pages.                                     |
| Customer/order relationship         | It determines whether history remains useful after launch.               | Customers with multiple orders, different addresses, group logic, discounts, and tax/shipping/payment variation. |
| Environment-dependent customization | It affects whether data can be migrated, configured, or must be rebuilt. | Custom fields, modified source tables, third-party modules, ERP references, and integration-owned identifiers.   |

These priorities help keep Gambio migration grounded in usable outcomes. The target result should not merely contain records. It should give the merchant a catalog, storefront, account base, and historical order set that can be operated after launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio data migration is best understood as a translation of selling structure into a Cloud or self-hosted Gambio operating model. Products, options, categories, stock, downloads, content pages, customers, and orders all carry meaning beyond their field names. The more a source store depends on custom logic, app-owned fields, complex product choices, or SEO-sensitive navigation, the more important it becomes to review representative records before Full Migration.

A strong Gambio migration plan separates four things clearly: data that can be moved, behavior that must be configured, storefront elements that must be rebuilt or reviewed, and custom structures that may require Custom Service. That separation helps the new store become usable, not just populated.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why do product options require special attention in Gambio migration?**

Product options may affect shopper choice, price, SKU meaning, stock assumptions, images, shipping, and order-line clarity. If the source platform stores option behavior differently, the migrated product can look correct while still selling incorrectly.

**Are Gambio categories just ordinary product containers?**

No. Categories also shape navigation, SEO, product discovery, and customer trust. A source store that uses collections, tags, menus, or landing pages should review how those structures should translate into Gambio.

**Do CMS Pages matter in a Gambio migration?**

Yes. CMS Pages can include legal content, shipping information, returns pages, trust content, guides, and landing pages. They should be reviewed for placement, relevance, links, and redirects, not only migrated as text records.

**Does choosing Gambio Cloud or self-hosted Gambio change data planning?**

Yes. Cloud and self-hosted environments create different expectations for hosting, updates, customization, technical access, and post-migration responsibility. The selected environment should shape how custom data and integrations are reviewed.
