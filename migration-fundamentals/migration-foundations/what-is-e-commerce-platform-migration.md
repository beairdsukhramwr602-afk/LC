---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/EwOn3si2UOVRL65zVOMg/getting-started/quickstart-3
---

# What Is E-commerce Platform Migration?

E-commerce platform migration is the planned movement and reconstruction of store data from a Source Platform into a Target Platform. The purpose is not only to transfer records. The purpose is to help the target store continue supporting the business after the platform change.

A migration may include products, customers, orders, categories, reviews, coupons, taxes, CMS Pages, Blog Posts, images, SEO fields, customer addresses, product options, variants, attributes, and other supporting data. Those record groups are the visible layer. The more important question is whether the Target Platform can preserve the meaning behind them.

That is why e-commerce platform migration should be treated as a business-continuity decision, not only as a data-transfer task. A target store can contain the expected records and still be weaker if products cannot be purchased correctly, categories no longer support discovery, order history becomes difficult to use, customer context is incomplete, or important pages lose search and traffic value.

### What E-commerce Platform Migration Includes <a href="#what-e-commerce-platform-migration-includes" id="what-e-commerce-platform-migration-includes"></a>

E-commerce platform migration usually begins with the store data that keeps a business usable. That may include core commerce records, content records, customer records, and operational history.

| Migration area               | What it usually covers                                                                                                                          | Why it matters                                                                                                              |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Catalog data                 | Products, variants, options, attributes, images, categories, prices, inventory-related fields, and product relationships.                       | Customers need to browse, compare, and buy products in a way that still reflects the business model.                        |
| Customer data                | Customer records, customer addresses, account-related information, customer groups, and customer-related context where supported.               | Support, continuity, segmentation, and customer trust often depend on usable customer information.                          |
| Order data                   | Orders, order details, order status context, customer links, product references, totals, discounts, taxes, and related history where available. | Teams may need order history for support, reporting, reconciliation, refunds, fulfillment review, or operational reference. |
| Content data                 | CMS Pages, Blog Posts, landing-page content, metadata, and supporting page information.                                                         | Content can support search visibility, product education, navigation, trust, and conversion paths.                          |
| Commercial rules and context | Coupons, tax-related data, product relationships, merchandising context, SEO fields, and other store-specific structures.                       | A store depends on relationships and supporting rules, not only on isolated records.                                        |

The exact scope depends on the selected migration path, platform capability, service scope, store structure, and any selected Add-ons or Custom Service requirements. Migration scope should therefore not be understood as a flat checklist of records. It should be defined by the business outcomes the target store must support.

### What Migration Is Trying to Preserve <a href="#what-migration-is-trying-to-preserve" id="what-migration-is-trying-to-preserve"></a>

Successful migration preserves usable business meaning. The migrated data should not merely exist in the Target Platform; it should remain useful for customers, staff, operations, and future store management.

#### Purchasability <a href="#purchasability" id="purchasability"></a>

Products need to remain buyable in the way customers expect. That depends on more than product names and descriptions.

Important checks may include whether:

* variants and options still represent real buying choices;
* prices, stock-related fields, and product-specific details still make sense;
* configurable, bundled, grouped, or otherwise complex products still support the intended purchase decision;
* images and supporting product information remain connected to the correct products;
* required product relationships remain understandable in the Target Platform.

A product can appear in the target store and still fail commercially if its buying logic changes.

#### Discoverability <a href="#discoverability" id="discoverability"></a>

Customers still need to find the right products through the paths that matter. Discoverability often depends on category hierarchy, navigation logic, filters, attributes, product relationships, internal links, and page structure.

A catalog can migrate successfully in record-count terms while becoming weaker as a discovery system. For example, products may exist, but the category structure may no longer guide customers properly. Filters may become less useful if attributes are not represented correctly. Important collections, landing paths, or merchandising relationships may require closer review.

#### Customer Continuity <a href="#customer-continuity" id="customer-continuity"></a>

Customer records should still support the business and customer experience after migration. That may include customer account context, addresses, historical order visibility, customer groups, reviews, loyalty-related context, or support workflows where those elements are part of the source store and supported by the migration scope.

The question is not only whether customer records exist. The question is whether the business can still use customer context in a workable way after launch.

#### Order Usability <a href="#order-usability" id="order-usability"></a>

Order history is often more than archive data. Businesses may rely on it for support, reporting, reconciliation, warranty review, refund reference, fulfillment investigation, or customer-service continuity.

Order data can become less useful if product references weaken, customer links are incomplete, statuses are interpreted differently, or platform differences change how historical orders can be reviewed. For that reason, order migration should be judged by practical usability, not only by the number of migrated orders.

#### SEO and Content Continuity <a href="#seo-and-content-continuity" id="seo-and-content-continuity"></a>

Migration can affect the pages and structures that support search visibility, traffic, and customer journeys. Product pages, category pages, CMS Pages, Blog Posts, metadata, URL structure, redirects, and internal linking can all influence post-migration continuity.

A store can complete its core data migration and still lose traffic or conversion momentum if important pages become harder to reach, less relevant, or less useful after launch.

### What Migration Is Not <a href="#what-migration-is-not" id="what-migration-is-not"></a>

E-commerce platform migration is not the same as a complete store redesign, a full business-process rebuild, or a broad replatforming strategy, even though those efforts often happen at the same time.

A wider replatforming project may also include:

* storefront redesign;
* theme redevelopment;
* checkout changes;
* app, plugin, module, or extension replacement;
* integration changes;
* new merchandising logic;
* new operational workflows;
* broader content or SEO strategy changes.

Migration is narrower: it is the controlled movement and reconstruction of store data and related meaning so the target store can remain usable. Redesign, integration, marketing, and operating-model changes may affect the same project, but they should not be confused with the migration scope itself.

That distinction matters because teams often mix transfer decisions with redesign decisions. When everything becomes part of one undefined move, migration success becomes harder to define, harder to price, harder to validate, and harder to troubleshoot.

### Why Record Totals Are Not Enough <a href="#why-record-totals-are-not-enough" id="why-record-totals-are-not-enough"></a>

Record totals are useful. They help confirm whether expected groups of data were transferred. They do not prove that the migrated store is ready for business use.

A target store can show the expected number of products, customers, orders, categories, or pages and still be functionally wrong if:

* product options no longer support the intended purchase behavior;
* categories and filters no longer match how customers browse;
* customer accounts or customer groups lose useful context;
* order history is present but difficult to interpret;
* discounts, taxes, or supporting rules behave differently;
* page URLs change without adequate redirect planning;
* Blog Posts, CMS Pages, or landing pages lose metadata or internal-link value;
* app, plugin, module, extension, or outside-system data does not translate cleanly.

Presence is not the same as preserved meaning. Migration quality should be judged by whether the target store can support the outcomes the business needs, not only by whether the visible records arrived.

### What Shapes Migration Complexity <a href="#what-shapes-migration-complexity" id="what-shapes-migration-complexity"></a>

Two stores can have similar data volumes and very different migration difficulty. Complexity is shaped by the structure, meaning, and expected use of the data, not only by quantity.

Common complexity drivers include:

| Complexity driver                | Why it changes the migration decision                                                                                                    |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Target Platform differences      | The Target Platform may store products, customers, orders, content, URLs, or custom fields differently from the Source Platform.         |
| Product structure                | Variants, configurable products, bundles, grouped products, options, attributes, and product relationships may not translate one-to-one. |
| Custom or third-party data       | App, plugin, module, extension, custom-field, or outside-system data may require interpretation beyond standard handling.                |
| Content and SEO dependence       | Stores that rely heavily on organic traffic, landing pages, Blog Posts, CMS Pages, or URL continuity need careful review.                |
| Operational history requirements | Order, customer, and transaction-related context may need to remain usable for support, reporting, or reconciliation.                    |
| Platform capability limits       | Some source-store behavior may not be supported in the same way by the Target Platform.                                                  |

Complexity does not automatically make migration unsuitable. It changes how early review, service scope, Add-ons, Custom Service, and validation should be planned.

### How Custom Platform Cases Fit <a href="#how-custom-platform-cases-fit" id="how-custom-platform-cases-fit"></a>

Some migrations involve a Custom Platform as the Source Platform, the Target Platform, or both. A Custom Platform may be a custom-built store, a heavily modified commerce system, a private commerce environment, or a data structure that does not follow a standard supported platform model.

Custom Platform cases usually require Custom Service review because the project may need interpretation beyond a standard migration path. The important question is not only how the data can be accessed. The more important question is how store meaning is structured and what must be preserved in the target store.

Depending on the case, review may involve APIs, structured files, spreadsheets, database exports, semi-structured content, website access, or other available data sources. Those access methods are only inputs. The migration decision depends on whether the expected business result can be defined, reconstructed, and validated.

### Three Questions to Ask Early <a href="#three-questions-to-ask-early" id="three-questions-to-ask-early"></a>

A practical way to understand migration is to ask three questions before the project becomes too fixed.

#### What must still work after launch? <a href="#what-must-still-work-after-launch" id="what-must-still-work-after-launch"></a>

This question moves the discussion from vague transfer expectations to specific business outcomes. Products, search paths, customer records, order history, content, URLs, and operational workflows do not all carry equal value for every store.

The first planning task is to identify the areas where loss of meaning would create real business risk.

#### Which parts of the store carry the most risk? <a href="#which-parts-of-the-store-carry-the-most-risk" id="which-parts-of-the-store-carry-the-most-risk"></a>

Risk often appears where the source store depends on complex structure, custom data, third-party behavior, platform-specific logic, high-value landing pages, or important historical context.

Identifying those areas early helps the team focus on representative samples and meaningful validation instead of reviewing only easy records.

#### What needs to be proven before broader execution? <a href="#what-needs-to-be-proven-before-broader-execution" id="what-needs-to-be-proven-before-broader-execution"></a>

Early proof should show whether important source-store data can become usable target-store data. A representative sample can reveal clean translations, structural gaps, mapping needs, filtering needs, platform constraints, Add-on requirements, or Custom Service requirements before the broader migration plan becomes harder to adjust.

### Why Demo Migration Matters <a href="#why-demo-migration-matters" id="why-demo-migration-matters"></a>

Demo Migration gives merchants an early sample of how selected source-store data may appear after migration. It helps test whether records, relationships, and configuration assumptions remain sensible in the Target Platform before broader execution.

A useful Demo Migration can reveal:

* whether representative products, customers, orders, categories, or content migrate in a usable way;
* whether product structure and relationships still make sense;
* whether mapping, filtering, or configuration should be adjusted;
* whether Add-ons may be needed;
* whether Custom Service review should happen before full execution;
* where later validation should focus.

Demo Migration supports planning and decision-making. It does not replace full validation after broader migration activity. The strongest use of Demo Migration is to test representative cases from the parts of the store that matter most, not only the easiest records to move.

### Conclusion <a href="#conclusion" id="conclusion"></a>

E-commerce platform migration is the controlled movement and reconstruction of store data from a Source Platform into a Target Platform so the target store can remain useful after the platform change. Its real purpose is to preserve business meaning: products should remain purchasable, customers should retain continuity, order history should remain useful, content should support discovery, and important pages should keep their commercial value where possible.

Migration should not be judged by record totals alone. The better standard is whether the migrated result supports the business outcomes that matter after launch. That standard begins with clear scope, representative early proof, realistic attention to platform differences, and later validation of the target-store result.

Run a Demo Migration using samples from the parts of the source store that carry the most business meaning. If the sample exposes structural differences, high-risk product behavior, custom data, platform constraints, or unclear preservation requirements, review the migration path, selected Add-ons, and possible Custom Service needs before committing to broader execution.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is e-commerce platform migration just copying store data?**

No. It includes moving store data, but the larger goal is to preserve usable business meaning in the Target Platform. A target store can contain migrated records and still be unsuitable if product logic, category paths, customer context, order usability, content, or SEO continuity no longer work as expected.

**What data is usually included in e-commerce platform migration?**

Common migration scope may include products, customers, orders, categories, reviews, coupons, taxes, CMS Pages, Blog Posts, images, SEO fields, customer addresses, variants, options, attributes, and supporting relationships. Exact scope depends on the migration path, platform capability, selected service scope, Add-ons, and any Custom Service requirements.

**How is migration different from replatforming?**

Migration focuses on moving and reconstructing store data so the target store remains usable. Replatforming is broader and may include redesign, integrations, checkout changes, new apps or extensions, merchandising changes, workflow changes, and business-process decisions. Many projects include both, but they should not be treated as the same scope.

**Why can a migration look complete but still fail?**

A migration can look complete when record counts match, but still fail if the migrated data does not behave correctly. Products may not support the right buying decisions, categories may not guide customers properly, order history may be hard to interpret, customer records may lose context, or important pages may lose traffic value.

**When should Custom Service be considered?**

Custom Service should be considered when the project involves customization, modification, Custom Platform handling, custom fields, app, plugin, module, extension, or third-party data, outside-system identifiers, unsupported structures, custom migration logic adjustment, Tailored Add-ons, Custom Add-ons, or broader bespoke handling beyond standard service capability.

**What should be reviewed first before a larger migration?**

Start with representative proof. Review samples from the parts of the store that matter most: complex products, important categories, customer records, order history, high-value pages, redirects, custom data, or any area where platform differences could change business meaning after launch.
