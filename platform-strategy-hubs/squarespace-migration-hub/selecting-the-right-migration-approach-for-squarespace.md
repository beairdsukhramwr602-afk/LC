# Selecting the Right Migration Approach for Squarespace

Selecting the right migration approach for Squarespace depends on how clearly the source store’s data can fit Squarespace’s hosted website and commerce model. A store with straightforward products, customers, orders, CMS Pages, Blog Posts, and basic SEO fields may fit standard service capability. A store with complex product structures, custom fields, deep content routing, external identifiers, extension-owned records, API workflows, or unusual checkout behavior needs deeper review before the migration path is treated as predictable.

Squarespace is often chosen for its hosted environment, visual site management, content-led commerce, product merchandising, and integrated selling features. That strength also creates a planning boundary: source data must be interpreted through Squarespace-supported structures and target configuration. The migration approach should therefore be chosen from platform fit, data complexity, and service responsibility rather than store size alone.

### What Migration Approach Means for Squarespace <a href="#what-migration-approach-means-for-squarespace" id="what-migration-approach-means-for-squarespace"></a>

For Squarespace, migration approach means deciding whether the project fits standard service capability, whether the merchant wants Next-Cart-led execution, whether Add-ons can handle supported filtering or mapping needs, or whether Custom Service review is needed because the source data depends on custom, app-owned, extension-owned, API-connected, or outside-system behavior.

| Planning signal                                                                         | What it means for Squarespace                                                                                                                     | Likely approach direction                |
| --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| Standard products, categories, customers, orders, CMS Pages, Blog Posts, and SEO fields | Source records can be interpreted through ordinary Squarespace commerce and content structures.                                                   | Standard Service may be enough.          |
| Standard data, but the merchant wants Next-Cart-led execution                           | The data may not be custom, but the merchant wants Next-Cart to perform the migration.                                                            | Managed Service may be safer.            |
| Only selected eligible records should migrate                                           | The requirement is filtering, not custom platform behavior.                                                                                       | Data Filter Add-on may be relevant.      |
| Supported fields need controlled mapping                                                | The source and target support the data, but field interpretation needs adjustment.                                                                | Advanced Data Mapping may be relevant.   |
| Migrated values need supported modification                                             | Data values can be changed within supported migration behavior before reaching the target store.                                                  | Advanced Data Configure may be relevant. |
| Product structure does not fit cleanly                                                  | Product types, variants, SKUs, custom options, subscriptions, donations, digital products, or fulfillment assumptions need deeper interpretation. | Custom Service review may be needed.     |
| Content, URLs, or site structure require bespoke preservation                           | The source website depends on layouts, page routes, redirects, custom blocks, or content relationships that do not map directly.                  | Custom Service review may be needed.     |
| Extension, API, webhook, or outside-system data must be preserved                       | Business meaning may live outside ordinary Squarespace records.                                                                                   | Custom Service review is likely needed.  |
| Custom Platform is involved as Source Platform or Target Platform                       | Custom platform handling is required.                                                                                                             | Custom Service is required.              |

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the source data is predictable and the expected target result fits ordinary Squarespace commerce and content structures. This usually means the migration is primarily about supported records and fields, not custom behavior.

Standard Service is more likely to fit when the source store has:

* standard products with ordinary names, descriptions, images, SKUs, prices, stock, categories, and SEO fields;
* product variants that can be represented without bespoke transformation;
* customers or contacts that do not depend on complex account rules;
* orders that need ordinary historical reference value;
* CMS Pages and Blog Posts that can be migrated or rebuilt without custom layout preservation;
* basic category, tag, and navigation expectations;
* no extension-owned or API-owned data that must be included in the agreed migration scope;
* no outside-system identifiers that require custom preservation;
* a merchant team prepared to self-perform the migration and review results.

Standard Service does not mean the Squarespace site is automatically ready to launch. Payment, shipping, tax, checkout, design, navigation, domains, templates, extensions, marketing settings, and connected services still need target-side setup and testing. Standard Service only means the migration itself appears to fit standard capability and customer-led execution.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be a better fit when the migration appears to fit standard service capability, but the merchant wants Next-Cart to perform the migration. This can be useful when the merchant prefers Next-Cart-led execution even though the project does not require custom transformation.

Managed Service may be safer when:

* the migration requirement is standard, but the merchant wants Next-Cart-led execution;
* the merchant wants Next-Cart to run the migration using standard service capability and purchased Standard Add-ons;
* the project involves enough products, content pages, orders, or review coordination that customer-led execution is not preferred;
* the merchant has teams available to validate products, content, SEO, and orders but does not want to operate the migration process;
* the launch plan requires tighter coordination between migration timing and target-store review.

Managed Service should not be used to hide custom requirements. If the project requires bespoke content handling, custom product transformation, extension-owned records, external identifiers, or tailored API-related data treatment, those requirements should move into Custom Service review even if the merchant also wants Next-Cart-led execution.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when the migration requires customization, modification, bespoke handling, Custom Platform work, unsupported structures, or custom migration logic adjustment. For Squarespace, these signals often appear around product structure, content routing, URL preservation, extensions, API workflows, and external systems.

Custom Service review should be considered when the source includes:

* product structures that cannot map cleanly into Squarespace products, variants, SKUs, inventory, categories, or tags;
* custom product options, personalization fields, subscription-like behavior, donation workflows, booking-related records, or digital-product assumptions that need tailored interpretation;
* CMS Pages, Blog Posts, layouts, page blocks, menus, or design relationships that require bespoke preservation;
* SEO, slug, redirect, or URL requirements that exceed ordinary field migration;
* contacts, subscribers, donors, members, or customer records with custom segmentation or outside-system meaning;
* historical orders, transactions, discounts, fulfillment states, taxes, shipping labels, or payment context with custom operational meaning;
* extension-owned records, connected-service data, automation data, or third-party app data;
* API, webhook, CRM, ERP, accounting, fulfillment, marketplace, POS, inventory, email, or marketing identifiers that must remain traceable;
* source checkout fields or workflows that do not fit ordinary Squarespace target settings;
* a Custom Platform as Source Platform or Target Platform.

Custom Service does not automatically mean Next-Cart performs the migration process for the customer. It means customization or modification work is required. Migration management is included only when it is part of the final plan.

### How Add-ons Fit into a Squarespace Migration <a href="#how-add-ons-fit-into-a-squarespace-migration" id="how-add-ons-fit-into-a-squarespace-migration"></a>

Add-ons can help refine a Squarespace migration when the requirement stays within supported service capability. They should not be treated as a substitute for Custom Service when the project requires bespoke transformation or unsupported data handling.

| Add-on                  | When it may help in a Squarespace migration                                                                                                                                                  | Boundary                                                                                                       |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | The merchant wants to migrate only selected eligible records, such as active products, selected customers, recent orders, chosen CMS Pages, specific Blog Posts, or narrowed product groups. | Estimated entity quantities are not filters. Filtering must be configured as a migration requirement.          |
| Advanced Data Mapping   | Supported source fields need controlled mapping into supported Squarespace target fields.                                                                                                    | If the mapping requires custom logic beyond available behavior, it moves into Custom Service.                  |
| Advanced Data Configure | Migrated values need supported modification before reaching the target store or content structure.                                                                                           | If the value change requires tailored behavior beyond available settings, it belongs in Custom Service review. |

Add-ons are useful when the data is supported but needs selective handling. Custom Service is the correct review path when the business meaning is custom, extension-owned, API-connected, outside-system-dependent, or beyond standard platform interpretation.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should test whether the source store can be interpreted inside Squarespace with the selected approach. It should not only preview simple records.

A useful Demo Migration should help decide whether:

* products, variants, SKUs, inventory, product images, categories, tags, and SEO fields remain usable;
* product structures with custom options, digital-product behavior, subscriptions, donations, or booking-related expectations need deeper review;
* customer, contact, subscriber, donor, or member records retain the meaning needed after migration;
* historical orders and transactions preserve enough payment, shipping, tax, discount, fulfillment, and customer context;
* CMS Pages, Blog Posts, navigation, metadata, slugs, and high-value URLs are included, rebuilt, redirected, or accepted as out of scope;
* checkout-related history is separated from live Squarespace payment, shipping, tax, and order setup;
* extensions, APIs, webhooks, and outside systems have been addressed intentionally;
* Standard Service, Managed Service, Add-ons, or Custom Service is the safer final path.

The sample set should include records that are most likely to reveal difficulty: complex products, important content pages, high-value URLs, varied orders, contact or customer segmentation examples, extension-dependent records, and integration-sensitive identifiers.

### Signals That the Chosen Approach Is Too Light <a href="#signals-that-the-chosen-approach-is-too-light" id="signals-that-the-chosen-approach-is-too-light"></a>

A Squarespace migration approach may be too light when source review or Demo Migration shows business meaning that standard migration cannot preserve safely.

| Signal                                                   | Why it matters                                                                                                          | Safer response                                                                              |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Product variants or SKUs do not retain meaning           | Product selection, inventory, pricing, or fulfillment may be weakened.                                                  | Review mapping needs or Custom Service.                                                     |
| Content pages lose structure or purpose                  | Important CMS Pages, Blog Posts, menus, or landing pages may need rebuilding or bespoke handling.                       | Define content scope and confirm accepted exclusions.                                       |
| URLs, slugs, or metadata are incomplete                  | Search continuity and customer-entry paths may be affected.                                                             | Review SEO samples, redirects, and mapping requirements.                                    |
| Orders are readable only at a shallow level              | Payment, shipping, tax, fulfillment, discount, or customer context may be incomplete.                                   | Expand order samples and define required order-history meaning.                             |
| Contacts or customers lose segmentation meaning          | Audience, subscriber, donor, member, or customer context may not fit ordinary records.                                  | Separate ordinary records from marketing, membership, or custom data.                       |
| Extension-owned records are missing                      | Extension data may not belong to ordinary product, order, customer, or content structures.                              | Classify the extension as reconfigured, rebuilt, excluded, mapped, or Custom Service scope. |
| API or outside-system identifiers are not preserved      | CRM, ERP, accounting, fulfillment, marketplace, POS, inventory, or marketing references may be operationally important. | Review mapping or Custom Service requirements before Full Migration.                        |
| Checkout expectations depend on source-specific behavior | Live payment, shipping, tax, and checkout behavior may require target configuration or custom review.                   | Separate historical data from target checkout setup.                                        |

### Choosing the Practical Path <a href="#choosing-the-practical-path" id="choosing-the-practical-path"></a>

The practical approach can be summarized this way:

* choose **Standard Service** when source data is standard, Squarespace structures can support it, and the merchant is ready to self-perform and validate the migration;
* choose **Managed Service** when the requirement fits standard capability but the merchant wants Next-Cart-led execution;
* use **Standard Add-ons** when filtering, field mapping, or supported value configuration is needed;
* move to **Custom Service** when the project requires custom product interpretation, bespoke content or URL handling, extension-owned data handling, outside-system ID preservation, Custom Platform handling, or tailored migration behavior.

The safest approach is the one that reflects the actual source-store structure and the intended Squarespace target outcome, not the lightest available service label.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting the right migration approach for Squarespace requires a clear view of product complexity, content structure, SEO and URL expectations, customer/contact meaning, order history, checkout requirements, extensions, APIs, integrations, and service responsibility. Standard Service can be enough for clean and predictable data. Managed Service can be safer when the merchant wants Next-Cart-led execution. Add-ons can support filtering, mapping, and supported data configuration. Custom Service should be considered when custom, extension-owned, API-connected, outside-system, or unsupported data changes the migration scope.

Use Demo Migration to test the records that carry the most business meaning. If the sample shows that standard capability does not preserve product structure, content purpose, customer context, order history, SEO, extension data, or integration identifiers well enough, adjust the approach before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for every Squarespace migration?**

No. Standard Service may be enough for predictable source data, but complex product structures, custom content handling, high-value URL requirements, extension-owned records, outside-system identifiers, or custom checkout behavior may require Add-ons or Custom Service review.

**When should I choose Managed Service for Squarespace?**

Choose Managed Service when the migration appears to fit standard service capability but you want Next-Cart to perform the migration. Managed Service is about execution responsibility, not custom transformation.

**Does Custom Service mean Next-Cart automatically performs the migration for me?**

No. Custom Service means customization or modification work is required. Migration management is included only when it is part of the final plan.

**Which Add-ons are most relevant to Squarespace migration planning?**

The Data Filter Add-on can help when only selected eligible records should migrate. Advanced Data Mapping can help with supported field mapping. Advanced Data Configure can help when migrated values need supported modification before reaching Squarespace.

**What should Demo Migration prove before choosing the final approach?**

Demo Migration should prove that products, variants, customers or contacts, orders, CMS Pages, Blog Posts, SEO fields, URLs, extension-dependent records, and integration-sensitive identifiers can be interpreted acceptably inside Squarespace. If those samples expose gaps, the approach should be adjusted before Full Migration
