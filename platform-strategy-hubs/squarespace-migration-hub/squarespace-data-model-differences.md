# Squarespace Data Model Differences

Migrating to Squarespace means translating source-store data into a hosted website and commerce model. Squarespace is not only a product database. It combines commerce records, product pages, storefront design, CMS Pages, blog content, customer/contact data, marketing preferences, orders, transactions, checkout configuration, extensions, APIs, and webhooks inside a managed platform.

A source product, customer, order, or page may not carry the same meaning after it reaches Squarespace. Product options may need to become variants and SKUs. Customer records may need to be distinguished from contacts, subscribers, donors, address books, and marketing preferences. Orders and transactions should not be treated as identical. CMS Pages and product pages follow different target meanings. Extension-owned data, API-connected records, and webhook-triggered workflows may sit outside ordinary store data.

Data-model planning should therefore focus on meaning translation. The migrated Squarespace store should prove that source records remain useful in the target site, storefront, commerce, and marketing context.

### How Squarespace Interprets Migrated Data <a href="#how-squarespace-interprets-migrated-data" id="how-squarespace-interprets-migrated-data"></a>

Squarespace migration planning should separate commerce data from content, presentation, checkout configuration, and integration behavior. A record can be present in the target store while still failing to carry the source-store meaning customers or staff expect.

| Source-store meaning  | Squarespace target interpretation                                                                                                               | What the migrated result must prove                                                                              |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Product record        | Product type, product page, description, images, visibility, URL slug, tags, SEO values, variants, SKUs, inventory, and store-page association. | Products are recognizable, sellable, visible, and connected to the intended storefront paths.                    |
| Product options       | Variants, SKUs, inventory records, product attributes, or unsupported/custom behavior depending on source structure.                            | Buying choices still work as customer-facing selections, not only as descriptive text.                           |
| Product discovery     | Categories, tags, product catalogs, store pages, menus, navigation, search, and page layout.                                                    | Customers can find products through expected browsing and content paths.                                         |
| Customer records      | Commerce customers, contacts, subscribers, donors, address books, marketing preferences, and order relationships.                               | Customer and audience meaning is preserved without merging unrelated records into one simple concept.            |
| Orders                | Historical order records with product, customer, status, payment, shipping, tax, discount, fulfillment, and note context where supported.       | Orders remain readable for service, fulfillment, finance, and management review.                                 |
| Transactions          | Payment or transaction context related to order activity.                                                                                       | Payment history is not confused with live payment configuration.                                                 |
| Checkout behavior     | Target payment, shipping, tax, local pickup, discount, fulfillment, POS, and plan-sensitive commerce settings.                                  | Live checkout readiness is configured and tested separately from migrated order history.                         |
| CMS Pages and content | Pages, blog posts, landing pages, menus, images, blocks, design sections, metadata, and URLs.                                                   | Content meaning, navigation value, and SEO value are included, rebuilt, redirected, or accepted as out of scope. |
| Extensions and APIs   | Connected services, extension-owned data, API records, webhook subscriptions, external identifiers, and workflow dependencies.                  | Integration-sensitive data is mapped, reconfigured, rebuilt, excluded, or escalated intentionally.               |

### Product Types and Product Record Meaning <a href="#product-types-and-product-record-meaning" id="product-types-and-product-record-meaning"></a>

Squarespace product records can represent different selling models, including physical products, service products, gift cards, and digital products. These product types should not be treated as interchangeable during migration planning. Each type can carry different storefront, fulfillment, delivery, access, and customer-expectation meanings.

A source product should be reviewed for:

* product type and selling model;
* title, description, images, media, and visibility;
* category, tag, catalog, or store-page placement;
* URL slug and SEO values;
* product status or scheduling expectations;
* variants, SKUs, inventory, and stock behavior;
* digital delivery or service-specific expectations;
* relationship to content pages, landing pages, or marketing paths.

A product that migrates as a record can still be incomplete if its storefront placement, buying path, SEO value, or fulfillment meaning is not preserved.

#### Physical, Service, Gift Card, and Digital Products <a href="#physical-service-gift-card-and-digital-products" id="physical-service-gift-card-and-digital-products"></a>

Physical products usually need the closest review of variants, SKUs, inventory, shipping, fulfillment, tax, and product discovery. Service products may depend more on description, scheduling expectations, purchase limitations, and how customers understand the service offering. Gift cards carry a different commerce meaning from ordinary products and should be reviewed for target support and launch expectations. Digital products can involve download, file, access, or delivery assumptions that should not be reduced to ordinary product description text.

The migration plan should identify which product types exist in the source store and whether each type has an acceptable Squarespace target interpretation.

### Variants, SKUs, Inventory, and Product Options <a href="#variants-skus-inventory-and-product-options" id="variants-skus-inventory-and-product-options"></a>

Source platforms often represent product options in different ways. A source variant, modifier, option set, product attribute, personalization field, bundle, or custom add-on may not translate directly into a Squarespace variant and SKU structure.

Variant and inventory translation should answer:

| Source element             | Translation concern                                                                                                  | Review priority                                                      |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Variant option             | Whether it can become a Squarespace variant choice with the expected SKU, price, image, and stock behavior.          | Validate products where options affect buying.                       |
| SKU                        | Whether SKU-level identity remains traceable after migration.                                                        | Check products used for inventory, fulfillment, or external systems. |
| Inventory quantity         | Whether stock levels and inventory status remain meaningful.                                                         | Validate stock-sensitive products and low-stock examples.            |
| Product modifier or add-on | Whether it can be represented as a variant, product text, target configuration, extension behavior, or custom scope. | Review add-ons that affect price, fulfillment, or customer choice.   |
| Bundle or kit              | Whether the source behavior can be represented by Squarespace product structures or requires custom handling.        | Sample bundle-like products before Full Migration.                   |
| Digital delivery or access | Whether file delivery, content access, or post-purchase behavior can be represented in the target store.             | Review digital-product samples separately.                           |

The main risk is flattening commercial choice into static text. Static text can preserve information, but it does not preserve customer-facing purchase behavior.

### Categories, Tags, Catalogs, Store Pages, and Discovery <a href="#categories-tags-catalogs-store-pages-and-discovery" id="categories-tags-catalogs-store-pages-and-discovery"></a>

Squarespace product discovery can involve categories, tags, product catalogs, store pages, product blocks, navigation, menus, page layout, search behavior, and links from content pages. This makes product discovery more content-aware than a purely catalog-first platform.

A migrated product should be checked in the places where customers are expected to find it:

* category or collection-style browsing paths;
* product catalogs or store pages;
* product blocks or featured areas;
* menus and navigation;
* landing pages that introduce products;
* blog or content pages that link to products;
* high-value SEO entry pages;
* product search or filtering behavior where relevant.

Product migration should not be accepted only because the product exists in the target admin. The storefront path matters.

### Customers, Contacts, Subscribers, Donors, and Marketing Preferences <a href="#customers-contacts-subscribers-donors-and-marketing-preferences" id="customers-contacts-subscribers-donors-and-marketing-preferences"></a>

Squarespace customer and audience data can involve more than commerce customers. Contacts may include customers, subscribers, donors, address books, and marketing preferences. Source systems may combine or separate these concepts differently.

A source customer table may include buyers, newsletter subscribers, donors, prospects, abandoned-checkout contacts, wholesale accounts, or records imported from an external marketing system. Those meanings should be separated before migration expectations are finalized.

| Source concept           | Squarespace interpretation concern                                           | Migration implication                                                              |
| ------------------------ | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Commerce customer        | Buyer identity, address data, and order relationship.                        | Validate customer records with order history and addresses.                        |
| Subscriber               | Marketing audience record or mailing-list relationship.                      | Confirm whether subscriber data is in scope and how preferences should be treated. |
| Donor                    | Contact record with donation-related meaning where used.                     | Do not assume donor records are ordinary buyers.                                   |
| Address book record      | Contact/address relationship that may not match a commerce customer account. | Validate multiple-address and non-buyer records.                                   |
| Marketing preference     | Consent, audience, or communication state.                                   | Treat carefully; do not overwrite or invent consent meaning.                       |
| External CRM or email ID | Outside-system identifier.                                                   | Review mapping or Custom Service needs if traceability is required.                |

Customer migration should prove that account and audience records remain interpretable, not just that names and email addresses appear in the target store.

### Orders, Transactions, and Historical Commerce Context <a href="#orders-transactions-and-historical-commerce-context" id="orders-transactions-and-historical-commerce-context"></a>

Orders and transactions should be reviewed as related but distinct concepts. A historical order may need product lines, customer links, totals, discounts, tax, shipping, fulfillment status, payment labels, transaction references, cancellations, refunds, and notes. A transaction may carry payment-related meaning, but it should not be treated as the same thing as the full order record.

Order validation should include samples with:

* paid and unpaid states;
* fulfilled and unfulfilled states;
* refunded, canceled, or partially fulfilled history;
* different payment and shipping labels;
* discounts, gift cards, coupons, or manual adjustments where used;
* tax-sensitive totals;
* customer links and address context;
* subscription, digital, service, or membership-related orders where relevant;
* external payment, fulfillment, accounting, or POS references.

Historical order readability is different from live checkout readiness. Migrated orders may preserve past labels while the target store still needs payment, shipping, tax, fulfillment, and notification settings configured.

### CMS Pages, Blog Posts, Product Pages, and Landing Pages <a href="#cms-pages-blog-posts-product-pages-and-landing-pages" id="cms-pages-blog-posts-product-pages-and-landing-pages"></a>

Squarespace is content-led, so content data should not be treated as a minor appendix to product migration. CMS Pages, Blog Posts, product pages, landing pages, menus, images, content blocks, design sections, SEO metadata, and redirects can all affect the final customer experience.

A source CMS Page may become a Squarespace page, a rebuilt landing page, a policy page, a navigation item, or an accepted exclusion. A product page may carry commerce fields and content presentation. A blog post may support SEO, education, brand trust, or product discovery.

Content migration should distinguish:

* commerce product pages;
* CMS Pages;
* Blog Posts;
* landing pages;
* navigation and menu structures;
* page sections or design blocks;
* metadata and URL slugs;
* image assets and alt text where important;
* redirects and high-value legacy URLs.

A Squarespace migration should prove that commerce and content work together after migration.

### Extensions, APIs, Webhooks, and Outside-System Data <a href="#extensions-apis-webhooks-and-outside-system-data" id="extensions-apis-webhooks-and-outside-system-data"></a>

Squarespace can connect with extensions and developer surfaces, including commerce APIs, inventory-related data, orders, transactions, contacts, websites, analytics, and webhook subscriptions. These can create migration complexity because important business meaning may live outside ordinary product, customer, order, and page records.

Integration-sensitive data can include:

* product IDs and variant IDs;
* inventory references;
* customer or contact IDs;
* order IDs and transaction references;
* marketing preferences;
* external app records;
* shipping, fulfillment, accounting, finance, email, translation, review, or inventory-service data;
* webhook-triggered workflows;
* marketplace or feed identifiers;
* POS or in-person selling references.

These records should be classified before scope is finalized. Some data can be migrated or mapped. Some behavior belongs to target configuration. Some workflows must be rebuilt. Some app-owned or external-system data should move into Custom Service review.

### What Migrated Data Must Prove in Squarespace <a href="#what-migrated-data-must-prove-in-squarespace" id="what-migrated-data-must-prove-in-squarespace"></a>

A successful Squarespace migration should prove that data still supports the site and store experience the merchant intends to operate.

The migrated result should prove that:

* product types remain meaningful in the target store;
* variants, SKUs, inventory, visibility, categories, tags, and product URLs are usable;
* product discovery works through storefront, content, menu, and SEO paths;
* contacts, customers, subscribers, donors, addresses, and marketing preferences are not incorrectly merged;
* orders and transactions remain readable for post-migration reference;
* historical payment, shipping, tax, and fulfillment labels are not confused with live configuration;
* CMS Pages, Blog Posts, product pages, and landing pages are included, rebuilt, redirected, or accepted as out of scope;
* extensions, APIs, webhooks, and outside-system identifiers have been reviewed intentionally;
* custom or unsupported structures have been mapped, excluded, reconfigured, or escalated before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace data-model differences matter because the platform combines website, content, commerce, design, audience, checkout, and integration layers. Product records, variants, contacts, customers, orders, transactions, CMS Pages, Blog Posts, SEO values, extensions, APIs, and webhooks should be reviewed for business meaning, not only for record presence.

Use Demo Migration samples to test the records that carry the most meaning: products with variants and inventory, content-linked products, customer/contact examples, varied orders, high-value URLs, CMS Pages, Blog Posts, and integration-sensitive records. If those samples do not translate clearly into Squarespace, mapping, configuration, Add-ons, or Custom Service review should be considered before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**How are product variants handled in Squarespace migration planning?**

Product variants should be reviewed as customer-facing buying choices with SKU and inventory implications. If source options affect price, stock, fulfillment, image, or product selection, they should be sampled before Full Migration.

**Are customers and contacts the same in Squarespace?**

Not always. Commerce customers, contacts, subscribers, donors, address books, and marketing preferences can carry different meanings. Migration planning should avoid treating every audience-related record as one simple customer table.

**What is the difference between orders and transactions?**

Orders represent historical commerce activity and may include products, customers, totals, shipping, tax, status, discounts, and fulfillment context. Transactions carry payment-related meaning. They should be reviewed together, but they are not the same concept.

**Do CMS Pages and product pages migrate the same way?**

No. Product pages carry commerce meaning, while CMS Pages, Blog Posts, landing pages, menus, and design sections carry site, content, SEO, and navigation meaning. They should be reviewed as separate target structures.

**What happens to extension-owned or API-connected data?**

Extension-owned, API-connected, webhook-sensitive, or outside-system data should be classified separately. It may be migrated, mapped, reconfigured, rebuilt, excluded, or escalated to Custom Service depending on the required target outcome.
