# Storeden Pre-Migration Preparation Checklist

Storeden migration preparation should make the target store easier to configure, test, and launch with confidence. Because Storeden is positioned around cloud commerce, catalog and inventory management, professional order management, integrated payments, logistics, themes, apps, plug-ins, marketplace channels, API/developer resources, and TeamSystem ecosystem connections, preparation has to cover more than products, customers, and orders.

The goal is not to document every record manually. The goal is to identify which records, settings, workflows, and external references carry business meaning so Demo Migration and Full Migration can be judged against real Storeden operating needs. A product count, customer count, or order count can confirm transfer volume, but it does not prove that the new store is ready to sell, fulfill, report, or connect to surrounding systems.

A strong preparation file separates three categories before migration begins: data that should migrate, Storeden configuration that must be rebuilt in the target store, and custom or external behavior that requires Add-ons, Custom Service, app review, integration review, or manual setup.

### Storeden Preparation Principle <a href="#storeden-preparation-principle" id="storeden-preparation-principle"></a>

Storeden preparation should be built around operational evidence. The most useful preparation materials are the samples and decisions that show how the current store actually works: which catalog structures drive sales, which stock values control availability, which orders support customer service, which channels create extra identifiers, which apps hold business data, and which TeamSystem or external systems need continuity.

| Preparation question                                | What it reveals                                                                                                     | Storeden planning value                                                                   |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Which records are needed for daily operation?       | Products, stock, customers, orders, categories, content, and URLs that staff or shoppers rely on.                   | Helps prioritize migration review around business-critical records, not only full counts. |
| Which workflows are target-side configuration?      | Payment setup, logistics behavior, marketplace connections, apps, theme layout, and security settings.              | Prevents migrated history from being mistaken for live Storeden configuration.            |
| Which fields come from apps or external systems?    | ERP IDs, accounting references, marketplace IDs, warehouse values, marketing tags, and automation fields.           | Identifies where Custom Service or integration review may be required.                    |
| Which samples should be included in Demo Migration? | Complex products, channel-sensitive records, representative customers, and orders with payment or shipping context. | Makes Demo Migration useful as an approach checkpoint before Full Migration.              |

Preparation is successful when the team can explain why a record matters, how it should appear in Storeden, and whether it belongs to standard migration scope, Add-ons, Custom Service, target configuration, or manual setup.

### Confirm the Target Storeden Store and Operating Scope <a href="#confirm-the-target-storeden-store-and-operating-scope" id="confirm-the-target-storeden-store-and-operating-scope"></a>

Before reviewing data, confirm the target Storeden store and the business role it needs to support. Storeden is a managed commerce environment, so migration quality depends on both the transferred records and the target-side setup. If the target store is incomplete, reviewers may judge migrated data against unfinished settings, missing themes, disabled channels, or unconfigured payment and shipping behavior.

| Readiness area                 | What to confirm                                                                                                                 | Why it matters before migration                                                                    |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Store access and roles         | Administrative access, ownership, language/currency expectations, and review responsibilities.                                  | Ensures the right people can inspect records, adjust settings, and approve migration results.      |
| Commerce scope                 | Whether the store will use storefront selling, marketplace channels, B2B workflows, logistics tools, or TeamSystem connections. | Defines which records and workflows require deeper preparation.                                    |
| Theme and storefront baseline  | Theme status, navigation expectations, important pages, product-page layout, and mobile review needs.                           | Separates data migration quality from design and theme configuration work.                         |
| Payment expectations           | Payment providers, integrated payment behavior, transaction labels, and settlement review needs.                                | Historical payment data does not automatically configure live checkout behavior.                   |
| Shipping and logistics         | Shipping methods, carriers, tracking needs, logistics workflows, and fulfillment ownership.                                     | Shipping labels in old orders do not automatically rebuild Storeden logistics rules.               |
| Apps and plug-ins              | Apps, marketplace connectors, marketing tools, analytics tools, and operational extensions.                                     | App-owned data may need separate handling or Custom Service review.                                |
| API or TeamSystem dependencies | ERP, accounting, warehouse, POS, invoicing, CRM, or external identifiers.                                                       | Integration identifiers may be operationally important even when they are not visible to shoppers. |

The target setup does not need to be final before migration planning starts, but it must be clear enough to determine what the migrated data will be tested against.

### Prepare Product and Catalog Evidence <a href="#prepare-product-and-catalog-evidence" id="prepare-product-and-catalog-evidence"></a>

Product preparation should focus on business meaning, not only on catalog size. Storeden publicly emphasizes catalog and inventory management, product images and descriptions, price management, marketplace distribution, and order operations. That makes product preparation central to migration quality.

Use product samples that expose different kinds of catalog complexity. A simple product can confirm ordinary field transfer, but it cannot prove that variants, marketplace listings, stock-sensitive products, media-heavy products, or external identifiers will behave correctly.

| Product sample type          | What to include                                                                                                              | What it should prove in Storeden                                                        |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Simple product               | Title, description, image, price, SKU or product code, category, status, and stock.                                          | Standard product records remain clear and commercially usable.                          |
| Variant product              | Size, color, material, package quantity, price differences, stock differences, and image differences.                        | Buying choices remain understandable and operationally valid.                           |
| Attribute-heavy product      | Technical specifications, custom fields, manufacturer values, labels, filters, or merchandising fields.                      | Descriptive values appear where they are useful and do not distort purchasable choices. |
| Inventory-sensitive product  | Low-stock items, out-of-stock items, preorder items, warehouse-controlled items, or products with external stock references. | Stock values and availability expectations can be reviewed before launch.               |
| Marketplace-relevant product | Channel title, channel category, marketplace identifier, availability rule, or channel-specific description.                 | Website catalog data is not confused with marketplace-channel requirements.             |
| Excluded or inactive product | Archived, hidden, discontinued, duplicate, or seasonal products.                                                             | Scope decisions are deliberate rather than accidental.                                  |

Product review should also identify catalog cleanup opportunities. Storeden migration planning is often the right time to decide whether old inactive products, duplicate records, obsolete descriptions, inconsistent images, or unused category assignments should move exactly as they are, be filtered, be mapped differently, or be excluded.

### Prepare Category, Navigation, and Discovery Evidence <a href="#prepare-category-navigation-and-discovery-evidence" id="prepare-category-navigation-and-discovery-evidence"></a>

Categories and product discovery should be prepared separately from product records. A product can migrate correctly and still be difficult to find if category hierarchy, menus, filters, storefront links, or marketplace category assumptions are not reviewed.

Storeden preparation should identify the structures shoppers and staff actually use. That includes main categories, subcategories, landing pages, filters, menu items, product groups, marketplace categories, campaign pages, and priority SEO URLs.

| Discovery evidence     | Preparation focus                                                              | Review signal                                                                         |
| ---------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Main category tree     | Parent/child category relationships and product assignment.                    | Products appear in the expected browsing structure.                                   |
| Menu structure         | Storefront paths, header navigation, footer navigation, and promotional links. | Categories exist and are also reachable through the intended navigation paths.        |
| Filters and attributes | Attributes, tags, labels, custom fields, or other filter-driving values.       | Shoppers can narrow products using meaningful data, not empty or inconsistent labels. |
| Category content       | Category descriptions, SEO copy, banners, and internal links.                  | High-value landing pages retain their commercial and SEO context.                     |
| Marketplace grouping   | Channel categories or marketplace-specific product classification.             | Marketplace preparation is reviewed separately from website navigation.               |
| Priority URLs          | High-traffic category and product URLs.                                        | Redirect or URL continuity planning focuses on pages that matter most.                |

If category or filter behavior affects conversion, it should be represented in Demo Migration. Reviewing only product rows can miss storefront discovery problems that become obvious to customers after launch.

### Prepare Inventory and Availability Evidence <a href="#prepare-inventory-and-availability-evidence" id="prepare-inventory-and-availability-evidence"></a>

Inventory preparation should clarify whether Storeden will hold the authoritative stock value or whether another system will continue to control stock. A merchant using simple stock quantities has a different preparation requirement from a merchant using warehouse feeds, supplier feeds, ERP updates, marketplace stock sync, bundle logic, or manual stock adjustments.

| Inventory situation            | Evidence to prepare                                                                            | Why it matters                                                                             |
| ------------------------------ | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Single stock value per product | Product list with stock quantities and representative out-of-stock examples.                   | Confirms ordinary availability after migration.                                            |
| Variant-level stock            | Variant samples with different SKU and stock values.                                           | Prevents option-level overselling or hidden sellable variants.                             |
| External stock owner           | ERP, warehouse, supplier, POS, or marketplace stock references.                                | Migrated stock may become stale if the connection is not rebuilt.                          |
| Non-stock items                | Services, digital items, preorder products, made-to-order products, or informational products. | Avoids forcing unsuitable stock behavior onto products that do not use ordinary inventory. |
| Channel-specific availability  | Marketplace availability, B2B availability, or region-specific availability.                   | Website stock and channel stock may not share the same rule.                               |

Inventory evidence should be reviewed before Full Migration because stock errors can create immediate launch risk. A store with correct product titles but unreliable stock values can fail operationally on the first day.

### Prepare Customer, Account, and B2B Context <a href="#prepare-customer-account-and-b2b-context" id="prepare-customer-account-and-b2b-context"></a>

Customer preparation should distinguish ordinary customer records from guest buyers, registered account holders, B2B contacts, marketplace buyers, newsletter contacts, CRM identities, and external-system references. These records do not all carry the same meaning after migration.

| Customer area        | What to prepare                                                                                             | What to verify                                                                    |
| -------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Registered customers | Names, emails, addresses, account status, order links, and representative customer histories.               | Customer records remain understandable and useful for service review.             |
| Guest buyers         | Orders with incomplete or no customer account records.                                                      | Historical orders can still be interpreted even when an account does not exist.   |
| B2B context          | Company names, VAT/tax IDs, customer groups, price-list relationships, negotiated terms, or approval rules. | B2B meaning is not flattened into ordinary customer data.                         |
| Marketplace buyers   | Buyer origin, order source, contact details, and marketplace references.                                    | Channel-origin context remains visible where it matters for service or reporting. |
| Marketing context    | Newsletter status, consent values, tags, segments, or external marketing references.                        | Customer migration is not confused with marketing-platform setup.                 |
| External IDs         | ERP, CRM, accounting, support, loyalty, or warehouse identifiers.                                           | Integration continuity can be reviewed before acceptance.                         |

Password continuity should be handled cautiously. If the previous store stores passwords in a format that cannot be migrated safely or compatibly, customers may need to reset passwords after launch. That expectation should be part of communication planning rather than discovered after the store opens.

### Prepare Order, Payment, Shipping, and Logistics Samples <a href="#prepare-order-payment-shipping-and-logistics-samples" id="prepare-order-payment-shipping-and-logistics-samples"></a>

Order preparation should include the records staff will use after launch. Historical orders help customer service, finance, fulfillment, refund review, and management reporting. They should be reviewed for meaning, not only for count.

| Order sample                             | What to include                                                                             | Why it matters                                                                      |
| ---------------------------------------- | ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Paid and unpaid orders                   | Payment status, payment method label, totals, and transaction references.                   | Staff can interpret commercial history after migration.                             |
| Fulfilled and partially fulfilled orders | Shipping method, tracking number, carrier, fulfillment status, and notes.                   | Fulfillment history remains useful for service review.                              |
| Refunded or canceled orders              | Refund values, cancellation status, return notes, or adjustment history.                    | Finance and service teams can understand exceptions.                                |
| Discounted orders                        | Coupons, discounts, taxes, shipping fees, and promotional adjustments.                      | Totals remain explainable after migration.                                          |
| Marketplace orders                       | Channel origin, marketplace references, commissions, shipping labels, and customer context. | Marketplace-origin history is not treated like ordinary website-only order history. |
| External-system orders                   | ERP, accounting, invoicing, warehouse, POS, or customer-service references.                 | External references can be preserved or flagged for Custom Service review.          |

Live checkout must be planned separately from migrated order history. Past payment method labels do not configure integrated payments. Past shipping names do not configure logistics rules. Historical order data can explain what happened before migration; Storeden settings control what happens after launch.

### Separate Migrated Data from Storeden Configuration <a href="#separate-migrated-data-from-storeden-configuration" id="separate-migrated-data-from-storeden-configuration"></a>

One of the most important preparation steps is separating migrated data from configuration work. This prevents unrealistic expectations and makes project scope easier to approve.

| Area                   | Migrated data can preserve                                                                                   | Storeden configuration still controls                                                                              |
| ---------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| Products               | Product information, images, prices, stock values, category relationships, and supported custom values.      | Publication rules, merchandising, channel behavior, and storefront presentation.                                   |
| Customers              | Customer details, addresses, order relationships, and selected supported customer values.                    | Account access behavior, password reset expectations, segmentation setup, and marketing-tool configuration.        |
| Orders                 | Historical order details, totals, products purchased, customer context, payment labels, and shipping labels. | Live checkout, payment providers, fulfillment workflow, logistics rules, and future order processing.              |
| Categories and content | Category names, descriptions, CMS content, SEO values, and redirect planning inputs where supported.         | Theme layout, menu placement, landing-page design, and content hierarchy decisions.                                |
| Apps and integrations  | Some identifiers or exported values if supported and scoped.                                                 | App installation, API connections, TeamSystem integration setup, automation behavior, and ongoing synchronization. |
| Marketplace data       | Channel-related identifiers or product references when scoped.                                               | Marketplace account setup, channel publication, feed rules, and live channel operations.                           |

This distinction should be visible in the preparation file. It helps the merchant understand which concerns belong to migration and which should be handled through Storeden setup, Storeden support, connected apps, or external-system implementation.

### Identify Add-ons and Custom Service Signals Early <a href="#identify-add-ons-and-custom-service-signals-early" id="identify-add-ons-and-custom-service-signals-early"></a>

Add-ons and Custom Service should not be discovered late. Preparation should identify whether the project needs supported filtering, mapping, or configuration, or whether it requires custom handling beyond standard migration behavior.

| Signal                                              | Likely handling path    | Example                                                                                              |
| --------------------------------------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------- |
| Only selected eligible records should migrate       | Data Filter Add-on      | Exclude obsolete products, old test customers, or historical orders before a specific business date. |
| Supported fields need better alignment              | Advanced Data Mapping   | Align catalog fields, customer values, order statuses, or category values where supported.           |
| Supported values need controlled adjustment         | Advanced Data Configure | Adjust selected labels, statuses, names, or other supported values before migration.                 |
| App-owned or unsupported data is required           | Custom Service          | Preserve app fields, marketplace IDs, ERP identifiers, or nonstandard product logic.                 |
| Custom source logic affects business meaning        | Custom Service          | Transform bundle logic, B2B account relationships, external IDs, or bespoke order metadata.          |
| Standard migration output needs custom modification | Custom Service          | Adjust migration logic to match project-specific target expectations.                                |

Add-ons should remain bounded to supported filtering, mapping, or configuration behavior. Custom Service is required when the expected result depends on unsupported structures, app data, external-system references, Custom Platform interpretation, or custom migration logic adjustment.

### Prepare SEO, Content, and Redirect Evidence <a href="#prepare-seo-content-and-redirect-evidence" id="prepare-seo-content-and-redirect-evidence"></a>

Storeden preparation should include URLs and content, especially for stores with meaningful organic traffic or content-led selling. SEO continuity depends on more than importing products. It also depends on product URLs, category URLs, CMS pages, Blog Posts, metadata, internal links, images, redirects, canonical expectations, and domain timing.

| SEO or content area | What to collect                                                                                      | Why it matters                                                                           |
| ------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Priority URLs       | High-traffic product, category, CMS, and Blog Post URLs.                                             | Redirect work should prioritize pages with real value.                                   |
| Metadata            | Titles, descriptions, URL slugs, image alt text, and indexation notes.                               | Search presentation may change if metadata is missing or misaligned.                     |
| CMS pages           | Trang Hệ thống quản lý nội dung (CMS pages), policy pages, landing pages, and informational content. | Storefront trust and legal/commercial pages should not be treated as optional leftovers. |
| Blog Posts          | Articles, category relationships, author/date expectations, and internal links.                      | Content continuity may need separate review from product migration.                      |
| Domain timing       | DNS, launch date, redirect activation, and post-launch crawl monitoring.                             | URL continuity depends on launch coordination, not only migrated records.                |
| Internal links      | Navigation links, footer links, collection links, and content-to-product links.                      | Broken links can damage customer experience even if records migrate correctly.           |

Preparation should identify which SEO and content items are migration requirements, which are Storeden configuration tasks, and which need manual rebuild or Custom Service review.

### Build a Demo Migration Evidence Plan <a href="#build-a-demo-migration-evidence-plan" id="build-a-demo-migration-evidence-plan"></a>

Demo Migration should be used as a practical evidence checkpoint. A weak sample set can make a migration look cleaner than it really is. A strong Storeden sample set includes ordinary records and the records most likely to expose data-model, configuration, app, marketplace, or integration issues.

| Demo Migration sample           | What it should test                                                                                                    |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Simple product                  | Baseline product fields, image display, category assignment, and price.                                                |
| Variant or option product       | SKU, stock, price, image, and option meaning.                                                                          |
| Marketplace-sensitive product   | Channel identifiers, listing assumptions, and publication context.                                                     |
| Inventory-sensitive product     | Availability, out-of-stock handling, and stock-owner assumptions.                                                      |
| Representative customer         | Addresses, order links, customer context, and account meaning.                                                         |
| B2B or company-related customer | Business identifiers, groups, tax context, or special account expectations.                                            |
| Complex order                   | Products purchased, discounts, taxes, payment labels, shipping labels, fulfillment context, and customer relationship. |
| External-system record          | ERP ID, accounting reference, warehouse ID, marketplace ID, or API-linked value.                                       |
| Priority URL or CMS page        | SEO and content continuity.                                                                                            |

If Demo Migration samples behave as expected, the project can move forward with stronger confidence. If samples reveal missing app data, broken option meaning, incomplete external identifiers, unclear order history, or weak SEO continuity, the service path should be reviewed before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden preparation should create a clear evidence base for migration scope, target configuration, and service-path choice. Products, categories, inventory, customers, orders, marketplace values, logistics references, payment labels, content, SEO data, apps, API references, and TeamSystem-related identifiers all need review according to their business role.

A Storeden migration is easiest to approve when the merchant knows what will migrate, what must be configured in the target store, what requires Add-ons, what requires Custom Service, and which Demo Migration samples will prove readiness before Full Migration. Preparation is not paperwork. It is the control layer that prevents a technically complete migration from becoming an operationally incomplete launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Storeden migration?**

Start with the target Storeden store scope, then prepare representative products, categories, customers, orders, payment and shipping context, marketplace records, SEO URLs, apps, integrations, and external identifiers. The first goal is to understand business-critical records and configuration dependencies before migration begins.

**Should payment and shipping settings be prepared as migration data?**

Historical payment and shipping labels can be migrated as part of order history where supported, but live payment and shipping behavior must be configured in the target Storeden store. Preparation should separate order-history meaning from future checkout and logistics behavior.

**When do Add-ons become relevant during preparation?**

Add-ons become relevant when supported migration data needs filtering, mapping, or controlled value configuration. For example, a merchant may want to migrate only selected records, align supported fields more carefully, or adjust supported labels before migration.

**When should Custom Service be discussed before Full Migration?**

Custom Service should be discussed when the expected result depends on unsupported app data, external-system identifiers, marketplace-specific records, B2B logic, Custom Platform interpretation, or custom migration logic adjustment. These requirements should be identified before the Demo Migration review is accepted.

**How should Demo Migration samples be chosen for Storeden?**

Demo Migration samples should include ordinary records and the records most likely to expose Storeden-specific issues: variant products, marketplace-linked products, inventory-sensitive items, B2B customers, complex orders, external identifiers, and priority URLs or content pages.
