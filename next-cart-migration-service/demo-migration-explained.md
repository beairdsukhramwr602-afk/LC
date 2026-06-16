# Demo Migration Explained

Demo Migration gives customers an early, practical view of how selected source-store data appears in the Target Platform before broader migration execution. It is not only a preview of whether records can move. It is an evidence stage that helps customers understand whether migrated examples still preserve the product, customer, order, content, and relationship meaning the business needs after migration.

A useful Demo Migration turns migration planning into visible proof. It helps customers review real examples, identify configuration questions, recognize Add-on or Custom Service needs, and decide what should be clarified before moving deeper into the migration process.

### What Demo Migration Is Designed to Prove <a href="#what-demo-migration-is-designed-to-prove" id="what-demo-migration-is-designed-to-prove"></a>

Demo Migration is designed to show how representative source-store data is translated into the Target Platform under the selected migration path and configuration context.

The sample is intentionally limited, but it should still be meaningful enough to answer important planning questions:

| Planning question                                                     | What the demo should help reveal                                                                        |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Does source-store data appear in the expected target-store structure? | Whether migrated examples are placed in a usable way.                                                   |
| Does migrated data keep its business meaning?                         | Whether products, customers, orders, content, and relationships remain understandable.                  |
| Do configuration choices need adjustment?                             | Whether mappings, settings, values, or selected options need closer review.                             |
| Are Add-ons needed?                                                   | Whether filtering, advanced mapping, or data configuration would improve control.                       |
| Is Custom Service required?                                           | Whether the project includes custom fields, third-party data, unsupported structures, or bespoke logic. |
| Is the selected service path still appropriate?                       | Whether the project looks suitable for customer-led execution, expert handling, or custom planning.     |

The demo result should be treated as early evidence. It can strengthen confidence, but it should not replace validation after broader migration execution.

### Why Demo Migration Matters <a href="#why-demo-migration-matters" id="why-demo-migration-matters"></a>

Many migration risks are not visible from record counts alone. A store may have a manageable number of products, customers, and orders while still containing product logic, custom fields, app data, plugin data, language structures, order-history expectations, or content relationships that affect the final result.

Demo Migration helps customers see those risks earlier. Instead of making decisions only from assumptions, customers can review migrated examples and ask more precise questions before execution expands to a larger scope.

The value is especially high when the source store includes:

* products with variants, options, attributes, bundles, grouped products, or special pricing;
* important customer and order history used by support, fulfillment, reporting, or account continuity;
* categories, collections, navigation paths, CMS Pages, Blog Posts, reviews, or coupons that affect customer experience;
* data created or shaped by apps, plugins, extensions, custom fields, or outside systems;
* platform-specific structures that may not have a direct one-to-one equivalent in the Target Platform.

Demo Migration does not need to expose every edge case. It should expose enough representative meaning to help the customer decide what deserves closer planning.

### Choosing a Strong Demo Sample <a href="#choosing-a-strong-demo-sample" id="choosing-a-strong-demo-sample"></a>

The quality of a Demo Migration depends on the quality of the sample. A simple sample can look clean while hiding the harder parts of the source store. A strong sample is selected because it is revealing, not because it is easy.

A useful sample often includes:

* commercially important products;
* products with the most important option, variant, attribute, or pricing behavior;
* categories, collections, or browse paths that customers rely on;
* representative customers with meaningful account or address information;
* representative orders with real operational history;
* reviews, coupons, CMS Pages, or Blog Posts where those records matter after migration;
* examples affected by Add-ons, mapping choices, configuration settings, or Custom Service concerns;
* records that reflect the highest-risk areas of the source store.

A good sample does not need to be large. It needs to show whether the target-store result can preserve the business meaning that matters most.

### What to Review in Demo Migration Results <a href="#what-to-review-in-demo-migration-results" id="what-to-review-in-demo-migration-results"></a>

The strongest review question is not only whether records appeared. The stronger question is whether the migrated examples still support the expected business use.

Review should be focused enough to keep the demo manageable, but practical enough to reveal whether the broader migration needs adjustment.

#### Product and catalog behavior <a href="#product-and-catalog-behavior" id="product-and-catalog-behavior"></a>

Products should be reviewed for whether the target-store result can support the expected buying, merchandising, and catalog-management experience.

Important checks include:

* product titles, descriptions, SKUs, prices, images, and statuses;
* option, variant, attribute, bundle, or grouped-product behavior where relevant;
* product relationships with categories, collections, manufacturers, or tags;
* fields used for search, filtering, merchandising, or reporting;
* product data affected by apps, extensions, plugins, custom fields, or custom logic.

A product can appear in the target store and still require attention if customers cannot understand, find, configure, or purchase it in the expected way.

#### Category, collection, and browse logic <a href="#category-collection-and-browse-logic" id="category-collection-and-browse-logic"></a>

Catalog structure should be reviewed for whether shoppers can still reach important products through expected paths.

Important checks include:

* category hierarchy or collection membership;
* product assignment accuracy;
* navigation and browse-path meaning;
* filtering-related fields where relevant;
* important category or collection pages that affect merchandising or discovery.

A catalog may look complete by count while becoming weaker as a discovery system. Demo Migration should help reveal whether the structure remains usable.

#### Customer and order usability <a href="#customer-and-order-usability" id="customer-and-order-usability"></a>

Customer and order records should be reviewed together because they often support customer service, account continuity, order lookup, reporting, fulfillment, or post-launch operations.

Important checks include:

* customer names, emails, addresses, and account-related details where supported;
* order line items, totals, statuses, dates, and customer relationships;
* order-to-product relationships;
* historical information needed by support or fulfillment teams;
* mapped values that affect order interpretation.

The goal is not only to confirm that customer and order records exist. The goal is to confirm that they remain useful in the target store.

#### Relationship integrity <a href="#relationship-integrity" id="relationship-integrity"></a>

Migration quality depends heavily on relationships between records. Relationship issues can be harder to detect than missing records because totals may appear correct while the meaning is wrong.

Important checks include:

* products connected to the right categories or collections;
* orders connected to the right customers;
* orders connected to the right purchased products;
* reviews linked to the right products and customers where supported;
* coupons connected to the intended products, categories, or usage context where relevant;
* supporting structures such as manufacturers, taxes, CMS Pages, and Blog Posts appearing in the expected context.

When relationships are wrong, the migrated result may require mapping adjustment, configuration review, Add-on support, or Custom Service review.

#### Content and SEO-sensitive records <a href="#content-and-seo-sensitive-records" id="content-and-seo-sensitive-records"></a>

Content should be reviewed when it affects organic traffic, customer education, merchandising, or conversion.

Important checks include:

* CMS Page content and formatting;
* Blog Post content and structure;
* important page metadata where supported;
* URL behavior for important pages;
* links between content, products, categories, or navigation paths where relevant.

Content migration can look acceptable at a record level while still requiring review for formatting, structure, links, or customer-facing usefulness.

### What Demo Migration Can Reveal <a href="#what-demo-migration-can-reveal" id="what-demo-migration-can-reveal"></a>

Demo Migration findings usually fall into several practical categories.

#### The sample maps cleanly <a href="#the-sample-maps-cleanly" id="the-sample-maps-cleanly"></a>

Some demo results show that representative records appear in the Target Platform with expected structure and behavior. This is a positive signal, especially when the sample includes meaningful complexity.

A clean demo does not remove the need for later validation. It shows that the selected sample does not reveal major early concerns under the current setup.

#### Configuration needs adjustment <a href="#configuration-needs-adjustment" id="configuration-needs-adjustment"></a>

Some findings show that the migration can continue, but settings, mappings, selected options, or value alignment should be reviewed before broader execution.

Examples include order statuses that need a clearer target value, product-related fields that need more careful mapping, or selected records that should be handled differently.

These findings are useful because they appear early enough to improve the configured result.

#### An Add-on may be useful <a href="#an-add-on-may-be-useful" id="an-add-on-may-be-useful"></a>

Some findings show that the project needs more control over a focused migration need.

Examples include:

* only selected records should be migrated;
* source values should be mapped more deliberately into target-supported fields;
* data needs configuration before reaching the target store.

These needs may point to the Data Filter Add-on, Advanced Data Mapping, Advanced Data Configure, or another applicable Add-on depending on scope.

#### Custom Service may be required <a href="#custom-service-may-be-required" id="custom-service-may-be-required"></a>

Some findings go beyond standard service capability or focused Add-on support.

Custom Service may be required when the project involves Custom Platform handling, custom fields, unsupported extension or plugin data, third-party app data, outside-system identifiers, custom migration logic adjustment, bespoke transformation rules, or a Custom Add-on.

Demo Migration is valuable because it can reveal these needs before broader execution makes them harder to address.

### How Demo Migration Supports Service Decisions <a href="#how-demo-migration-supports-service-decisions" id="how-demo-migration-supports-service-decisions"></a>

Demo Migration helps customers make service decisions based on evidence instead of assumption.

A predictable demo result may support Standard Service when the customer can manage the migration actions and the data fits supported handling. A feasible but operationally sensitive result may support Managed Service when the customer wants Next-Cart experts to execute migration actions based on the customer request and agreed service scope. A result that exposes customization, unsupported structures, bespoke logic, or Custom Platform handling should be reviewed as Custom Service scope.

Service fit should not be based only on data volume or the customer initial expectation. The demo result can show whether the project needs more configuration control, expert handling, or custom planning before broader execution.

### Self-Run and Expert-Assisted Demo Review <a href="#self-run-and-expert-assisted-demo-review" id="self-run-and-expert-assisted-demo-review"></a>

Customers may review Demo Migration directly or ask for expert assistance depending on the selected service model, project complexity, and confidence level.

A self-run demo can be suitable when the customer wants to explore the migrated result directly and has enough internal confidence to judge whether the sample is usable. If the result differs from expectations, Live Chat can help clarify what the sample may reveal about configuration, Add-ons, service fit, or Custom Service needs.

An expert-assisted review can be useful when the source store has complex catalog behavior, sensitive customer or order-history requirements, Custom Platform involvement, third-party logic, or launch timing concerns. Expert assistance can help interpret the result and decide whether the migration should continue with the current approach or be reviewed under a different service scope.

The review goal is the same in both cases: use the demo result to make better migration decisions before broader execution.

### What Demo Migration Does Not Prove <a href="#what-demo-migration-does-not-prove" id="what-demo-migration-does-not-prove"></a>

Demo Migration is limited by design. It gives early evidence, not a final guarantee.

A Demo Migration does not prove that:

* every record will behave the same way during broader migration execution;
* every edge case has been reviewed;
* every platform limitation has been resolved;
* every Add-on or Custom Service need has already been identified;
* target-store validation can be skipped;
* launch readiness has been confirmed.

The safest interpretation is balanced: a strong demo result can reduce uncertainty, but it should not create overconfidence.

### Common Mistakes When Reviewing a Demo <a href="#common-mistakes-when-reviewing-a-demo" id="common-mistakes-when-reviewing-a-demo"></a>

Common mistakes include:

* choosing a sample that is too simple;
* checking only whether records appear;
* ignoring product behavior and relationship integrity;
* overlooking customer and order usability;
* excluding content or SEO-sensitive examples when they matter;
* assuming a clean demo removes the need for validation;
* choosing a service model without interpreting the demo result carefully;
* treating Add-on or Custom Service signals as minor details.

These mistakes usually create false confidence. The best review focuses on whether the migrated sample supports the business outcomes that matter after launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Demo Migration gives customers an early, evidence-based view of how representative source-store data behaves in the Target Platform. It helps reveal what maps cleanly, what needs configuration review, what may require Add-ons, and what points toward Custom Service.

The strongest demo is not the largest sample or the easiest sample. It is the sample that shows whether the target-store result can preserve the business meaning the customer needs to protect. If the findings are unclear, reveal Add-on needs, or suggest Custom Service requirements, Live Chat can help clarify the safest next step before broader migration execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What is Demo Migration?**

Demo Migration is a sample migration used to preview how selected source-store data may appear in the Target Platform before broader migration execution.

**What should be included in a Demo Migration sample?**

A useful sample should include records that reveal real migration meaning, such as complex products, important category or collection paths, representative customers and orders, key CMS Pages or Blog Posts, and records affected by apps, extensions, plugins, custom fields, or outside systems.

**Does a good Demo Migration prove the broader migration will work the same way?**

No. Demo Migration provides early evidence, but it does not prove every record, edge case, or later-stage requirement. Validation is still needed after broader migration execution.

**Can Demo Migration show whether Add-ons are needed?**

Yes. Demo Migration can reveal needs such as selective migration, advanced mapping, or data configuration. Those needs may point to the Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure.

**Can Demo Migration show whether Custom Service is needed?**

Yes. If the demo reveals requirements beyond standard service capability or focused Add-on support, such as Custom Platform handling, custom fields, third-party data, or bespoke transformation, the project should be reviewed as Custom Service scope.

**Should service choice happen before or after Demo Migration?**

Service expectations may exist before Demo Migration, but the demo result often gives stronger evidence for confirming whether Standard Service, Managed Service, or Custom Service is the safest fit.
