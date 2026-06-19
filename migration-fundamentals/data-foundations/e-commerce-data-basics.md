# E-commerce Data Basics

E-commerce data is not just a collection of records. It is the operating memory of the store: what the business sells, who it serves, what customers have bought, which content supports discovery, and which structures make products, accounts, orders, and pages work together.

Before migration planning becomes technical, merchants need a practical data model. The most useful starting point is not every possible field in the store. It is the set of data groups that carry the greatest commercial, operational, customer-facing, and continuity value.

For most stores, that starting point includes Products, Customers, Orders, CMS Pages, and Blog Posts, plus the supporting structure that connects them. These groups do not explain the full migration scope by themselves, but they create a clear foundation for understanding what must remain usable after the store moves from the Source Platform to the Target Platform.

### Basic Store Data Is Business Context <a href="#basic-store-data-is-business-context" id="basic-store-data-is-business-context"></a>

Basic e-commerce data groups matter because they support the everyday work of the store. Products support selling. Customers support account and service continuity. Orders preserve commercial and operational history. CMS Pages and Blog Posts support information, trust, navigation, and traffic continuity.

A migration that only checks whether these records exist in the Target Platform can miss the real issue. The practical test is whether each data group still supports the business role it had before migration.

| Data group           | Basic role in the store         | What migration should preserve                                                                               |
| -------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Products             | Defines what the business sells | Buyable product structure, pricing context, images, categorization, variants, options, and discovery value   |
| Customers            | Defines who the business serves | Account identity, addresses, customer context, service continuity, and order-history access where applicable |
| Orders               | Preserves commercial history    | Order detail, customer relationship, purchased items, totals, statuses, and operational reference value      |
| CMS Pages            | Holds evergreen store content   | Important information pages, internal links, metadata, and customer-facing content structure                 |
| Blog Posts           | Supports content and traffic    | Articles, URLs, metadata, images, internal links, and search or discovery value                              |
| Supporting structure | Makes core records usable       | Categories, attributes, images, relationships, SEO fields, custom fields, and third-party context            |

These groups are simple enough to understand early, but important enough to affect launch quality.

### Products Define What the Store Can Sell <a href="#products-define-what-the-store-can-sell" id="products-define-what-the-store-can-sell"></a>

Products are usually the most visible migration data group because customers, merchandising teams, and store managers interact with them constantly. A product record can include titles, descriptions, prices, SKUs, stock status, product images, categories, tags, attributes, options, variants, reviews, related products, cross-sells, upsells, and other structure that affects buying behavior.

The basic mistake is treating products as flat catalog entries. In a working store, a product often depends on relationships and behavior:

* a parent product may depend on variants, options, or configurable logic;
* prices may depend on tax settings, customer groups, sale rules, or custom fields;
* product discovery may depend on categories, attributes, filters, tags, collections, or search values;
* product pages may depend on images, media, reviews, metadata, internal links, and related-product logic;
* product availability may depend on inventory fields, stock rules, warehouse logic, or connected apps.

A product can migrate and still become weaker if customers cannot select the right option, find the item through the expected path, understand the product page, or trust the displayed information. Product review should therefore include representative examples, not only record totals.

### Customers Preserve Account and Relationship Continuity <a href="#customers-preserve-account-and-relationship-continuity" id="customers-preserve-account-and-relationship-continuity"></a>

Customer data usually begins with names, email addresses, account details, and addresses. For many stores, it also includes customer groups, segmentation rules, review ownership, order-history links, loyalty context, tax status, subscription identifiers, CRM identifiers, or support references.

Customer migration is sensitive because the business is not only preserving records. It is preserving continuity. The store may need customers to recognize their account, access relevant history, receive correct communications, or remain tied to service and marketing workflows.

Important customer questions include:

* will customer identity remain understandable in the Target Platform;
* will addresses remain usable for service and order reference;
* will customer groups or segmentation still support business rules;
* will customer-order relationships remain useful;
* will review ownership, loyalty context, or subscription references need separate review;
* will login expectations need communication or password reset planning.

Password behavior deserves early attention. Some migrations cannot preserve customer password behavior exactly because of platform security models or password storage differences. When that happens, the practical goal is not to force identical login behavior. It is to protect the first-login experience through planning, communication, and the correct account-continuity approach.

### Orders Preserve History, Service, and Operational Reference <a href="#orders-preserve-history-service-and-operational-reference" id="orders-preserve-history-service-and-operational-reference"></a>

Orders are historical records, but they are not only historical. They support customer service, refund review, fulfillment reference, accounting support, reporting, tax review, fraud review, warranty questions, subscription review, and other operational workflows.

A useful order migration should preserve the information needed to interpret what happened. That can include customer details, purchased products, quantities, prices, discounts, taxes, shipping details, billing details, payment references, status history, notes, and metadata.

Order data can become less useful even when order counts match. Common problems include:

* purchased items become harder to interpret because product references changed;
* customer links are incomplete or less useful;
* discounts, taxes, shipping fields, or totals no longer carry the same meaning;
* status history does not match operational expectations;
* custom order fields or third-party metadata are missing or no longer actionable;
* legacy history is present but difficult for staff to use.

For many businesses, order quality becomes visible after launch when support teams need to answer real customer questions. That is why representative historical orders should be part of early review, especially orders with refunds, discounts, multiple shipments, complex taxes, custom fields, or support value.

### CMS Pages and Blog Posts Support Content Continuity <a href="#cms-pages-and-blog-posts-support-content-continuity" id="cms-pages-and-blog-posts-support-content-continuity"></a>

Content data often receives less attention than products or orders, but it can carry substantial business value. CMS Pages may include About pages, policy pages, shipping information, landing pages, buying guides, sizing information, warranty information, or other evergreen content. Blog Posts may support search traffic, education, internal linking, buying confidence, and long-tail discovery.

Content migration should preserve more than text. It may need to preserve:

* page titles, body content, images, and media references;
* URL values and redirect requirements;
* metadata and search-facing fields;
* internal links to products, categories, CMS Pages, and Blog Posts;
* publishing status, dates, authorship, or content grouping where relevant;
* layout-sensitive content that may need review in the Target Platform.

A content page can migrate but still lose value if images break, URLs change without adequate redirects, internal links point to old paths, formatting becomes unreadable, or metadata is lost. Content should therefore be judged by customer usability and traffic continuity, not by page count alone.

### Categories, Attributes, Images, and Relationships Make Data Usable <a href="#categories-attributes-images-and-relationships-make-data-usable" id="categories-attributes-images-and-relationships-make-data-usable"></a>

Core records rarely work alone. Products need categories, attributes, options, variants, images, and metadata. Customers need addresses, customer groups, and order links. Orders need customer, product, tax, discount, shipping, and payment context. CMS Pages and Blog Posts need URLs, internal links, images, and metadata.

These supporting structures are easy to underestimate because they can look secondary during early scoping. In practice, they often determine whether the migrated data still works.

| Supporting structure       | Why it matters                                                                          |
| -------------------------- | --------------------------------------------------------------------------------------- |
| Categories and collections | Preserve browse paths, merchandising logic, landing-page value, and internal discovery. |
| Attributes and filters     | Help customers compare, narrow, and understand products.                                |
| Variants and options       | Preserve product selection behavior and buyability.                                     |
| Images and media           | Support trust, product evaluation, content continuity, and page completeness.           |
| SEO fields and URLs        | Help preserve search visibility, click-through context, and page intent.                |
| Relationships              | Connect products, customers, orders, content, categories, and supporting records.       |
| Custom fields and metadata | Carry business-specific meaning that may not fit the default Target Platform model.     |

When these structures change, the store may look populated but behave differently. That is why basic data review should include how records connect, not only whether records exist.

### Entity Points Help Size Core Scope, Not Full Meaning <a href="#entity-points-help-size-core-scope-not-full-meaning" id="entity-points-help-size-core-scope-not-full-meaning"></a>

Entity Points give Next-Cart a standardized way to measure core migration scope across major data groups such as Products, Customers, Orders, and Blog Posts. They help translate raw data volume into a more consistent sizing model for a migration path.

However, Entity Points do not replace business review. A store with similar core counts can have very different migration complexity depending on product structure, customer groups, historical order requirements, content value, SEO sensitivity, custom fields, extension data, or outside-system identifiers.

The correct way to use core sizing is to separate two questions:

| Question                                     | What it answers                                                             |
| -------------------------------------------- | --------------------------------------------------------------------------- |
| How much core data is involved?              | Helps size the migration scope using standardized core data measurement.    |
| How much business meaning must be preserved? | Helps identify structure, relationships, custom data, and validation needs. |

A migration can be correctly sized and still need additional planning if the store depends on complex supporting structure. That does not make the sizing model wrong. It means sizing and business-continuity review answer different questions.

### Third-Party and Custom Data Can Redefine the Basics <a href="#third-party-and-custom-data-can-redefine-the-basics" id="third-party-and-custom-data-can-redefine-the-basics"></a>

Many stores depend on apps, plugins, modules, extensions, custom fields, or outside systems that add meaning to otherwise basic data. A product field may control search, merchandising, bundles, subscriptions, personalization, or ERP matching. A customer field may control segmentation, tax handling, or loyalty logic. An order field may support fulfillment, reporting, shipping automation, fraud review, or customer support.

When those fields affect real business behavior, they should not be dismissed as minor details. They may require mapping, configuration, filtering, transformation, or custom migration logic adjustment.

Some cases may be handled through Add-ons such as Advanced Data Mapping, Advanced Data Configure, or the Data Filter Add-on. Broader customization, unsupported extension data, outside-system identifiers, Custom Platform conditions, or bespoke handling should be reviewed under Custom Service.

The key point is simple: basic data is only basic when the business uses it in a basic way. Once third-party or custom logic controls real outcomes, that data becomes part of the migration requirement.

### Practical Review Questions for Basic E-commerce Data <a href="#practical-review-questions-for-basic-e-commerce-data" id="practical-review-questions-for-basic-e-commerce-data"></a>

A useful early review should connect each data group to the business outcome it supports. The goal is not to inspect every field immediately. The goal is to identify which records and structures should be sampled, protected, or escalated before assumptions become fixed.

| Review question                                                                          | Why it matters                                                                             |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Which products are most complex or highest value?                                        | Simple products rarely reveal the full product-structure risk.                             |
| Which customer groups or account cases need continuity?                                  | Customer migration quality depends on more than names and emails.                          |
| Which historical orders must remain operationally useful?                                | Support, refunds, reporting, and fulfillment review may depend on preserved order meaning. |
| Which CMS Pages and Blog Posts support trust, traffic, or conversion?                    | Content value can be lost through URL, metadata, image, or internal-link changes.          |
| Which categories, attributes, images, and relationships carry business value?            | Supporting structure often determines whether core records remain usable.                  |
| Which apps, plugins, modules, extensions, or outside systems add important data meaning? | These layers may require Add-ons, Custom Service evaluation, or deeper planning.           |

These questions create a better foundation for Demo Migration review, scope discussion, and later validation because they focus attention on the data that carries real business value.

### Common Mistakes in Basic Data Planning <a href="#common-mistakes-in-basic-data-planning" id="common-mistakes-in-basic-data-planning"></a>

Several mistakes repeat across e-commerce migration projects.

The first is assuming that Products, Customers, Orders, CMS Pages, and Blog Posts are complete because the records are present. Presence is only the starting point. The data must still be usable.

The second is focusing on the largest data group while ignoring the most sensitive one. A store may have many products but depend heavily on a smaller number of historical orders, customer groups, custom fields, or traffic-driving content pages.

The third is treating supporting structure as optional. Categories, attributes, variants, images, metadata, relationships, and internal links often carry the meaning customers and staff depend on.

The fourth is discovering custom and third-party data too late. If apps, plugins, modules, extensions, or outside systems shape store behavior, those dependencies need early review.

The fifth is confusing basic data sizing with migration acceptance. Sizing helps define scope. Acceptance requires proof that the migrated store still supports business use.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Products, Customers, Orders, CMS Pages, Blog Posts, and their supporting structures form the practical foundation of e-commerce migration planning. These data groups explain what the store sells, who it serves, what history it preserves, and which content supports customer trust and traffic continuity.

The safest planning approach treats basic data as business context, not as isolated records. Counts matter, but the more important question is whether the migrated data still supports buying, account continuity, service review, operational reference, content value, and discovery after launch.

When the store depends on custom fields, third-party logic, outside-system identifiers, or unusual platform structure, those requirements should be clarified early. Live Chat can help confirm whether the expected migration path is likely to preserve the required data meaning or whether Add-ons, Custom Service handling, or deeper review should be considered.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What are the main e-commerce data groups to review before migration?**

The main starting groups are usually Products, Customers, Orders, CMS Pages, and Blog Posts. Supporting structures such as categories, attributes, variants, options, images, SEO fields, URLs, relationships, custom fields, and metadata should also be reviewed because they determine how useful the core records remain after migration.

**Why are products more than simple catalog records?**

Products often depend on variants, options, attributes, categories, images, reviews, related products, pricing context, inventory logic, and third-party fields. A product can exist in the Target Platform while selection, discovery, merchandising, or buying behavior becomes weaker.

**Why does order data need careful review?**

Orders preserve historical and operational context. They may support customer service, refunds, reporting, fulfillment review, accounting support, and internal operations. Matching order counts does not prove that order history remains useful for staff or customers.

**Should CMS Pages and Blog Posts be part of early migration planning?**

Yes. CMS Pages and Blog Posts can support trust, navigation, SEO continuity, internal links, and conversion. They should be reviewed for content quality, URL behavior, metadata, images, formatting, and links to important products or categories.

**Do Entity Points explain all migration complexity?**

No. Entity Points help size core migration scope, but they do not fully explain business meaning, custom data, third-party logic, relationships, SEO sensitivity, or validation effort. Sizing and business-continuity review should be treated as separate planning questions.

**When does basic data require Custom Service review?**

Custom Service review may be needed when important data depends on unsupported extension data, outside-system identifiers, Custom Platform conditions, bespoke structure, or custom migration logic adjustment. Some narrower needs may fit Add-ons such as Advanced Data Mapping, Advanced Data Configure, or the Data Filter Add-on.
