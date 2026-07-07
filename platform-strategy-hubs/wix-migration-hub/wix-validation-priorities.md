# Wix Validation Priorities

Wix validation should prove that the migrated site can operate as a Wix commerce environment, not only that records appear in a dashboard. Wix combines site-builder presentation, Wix Stores catalog data, collections, variants, inventory, orders, payments, contacts, members, CMS collections, Blog Posts, media, apps, Velo/API logic, service plugins, URLs, domains, and launch settings. A record-count check can confirm presence, but it cannot prove that the store is usable for customers, staff, search engines, or connected workflows.

The strongest Wix validation process checks business meaning in layers. Products must be visible and sellable. Options and variants must preserve choice, SKU, stock, and price meaning where supported. Collections must support discovery without being confused with full site navigation. Historical orders must remain readable without being mistaken for future payment or checkout configuration. Contacts, customers, and members must be validated as different identity contexts. Site content, URLs, media, SEO fields, apps, and custom logic must be checked as Wix-specific launch areas, not treated as ordinary product records.

### What Wix Validation Must Prove <a href="#what-wix-validation-must-prove" id="what-wix-validation-must-prove"></a>

A Wix migration should be approved only when the target result is understandable across storefront, admin, content, and operational review. This does not mean every source behavior must be reproduced exactly. It means the agreed migration scope, target-side setup, Add-ons, Custom Service requirements, and accepted exclusions are clear enough for launch decisions.

| Validation layer           | What to prove                                                                                                                      | Why it matters for Wix                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Record presence            | Products, collections, customers, orders, CMS Pages, Blog Posts, media, and supported records appear in the expected Wix areas.    | Presence confirms transfer but not usability.                                                        |
| Business meaning           | Products, choices, variants, orders, contacts, members, content, and URLs still represent the intended source meaning.             | Wix may organize the same business idea differently from the old store.                              |
| Storefront usability       | Customers can find products, select options, see correct media, understand prices, and proceed through the intended purchase path. | Wix is a site-builder commerce platform, so visual and navigation context affects migration quality. |
| Administrative readability | Staff can review product details, customer context, order history, fulfillment information, payment labels, and exception cases.   | Migrated history must remain useful for customer support and operations.                             |
| Launch readiness           | Payment, shipping, tax, domain, redirect, app, content, and integration tasks are separately configured or assigned.               | Migrated records do not automatically complete future Wix operations.                                |

Validation should classify each finding by handling path. Some findings are migration corrections. Some are target-side Wix setup. Some require Add-ons. Some require Custom Service review. Some are outside the agreed scope and should be documented before launch.

### Validate Demo Migration With Representative Wix Samples <a href="#validate-demo-migration-with-representative-wix-samples" id="validate-demo-migration-with-representative-wix-samples"></a>

Demo Migration validation should use records that reveal Wix-specific risk. A sample built only from simple products, ordinary customers, and clean paid orders can pass while the real store still contains complex options, variant-level inventory, content dependencies, CMS collections, member records, app-owned data, custom checkout behavior, or high-value URLs.

A useful Demo Migration sample set should include:

| Sample group              | What to include                                                                                                                                          | Pass condition                                                                                                            |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Simple products           | Standard products with title, SKU, price, image, description, collection, SEO value, and inventory.                                                      | The item appears in Wix with clear storefront and admin meaning.                                                          |
| Complex products          | Products with options, choices, variants, different SKUs, different prices, different stock, multiple media, personalization, or product-specific rules. | Variant and option behavior is clear enough for customers and staff.                                                      |
| Collections and discovery | Products tied to old categories, filters, menus, landing pages, or merchandising groups.                                                                 | Wix collections and site navigation expectations are separated and validated.                                             |
| Orders                    | Paid, refunded, canceled, discounted, taxed, shipped, guest, and multi-item orders.                                                                      | Order history is readable and customer/order relationships are understandable.                                            |
| Customer identity         | Customers, contacts, members, guest buyers, subscribers, loyalty records, booking participants, and app participants where relevant.                     | Each identity type is classified correctly and not collapsed into a misleading record.                                    |
| Content and SEO           | CMS Pages, Blog Posts, media-heavy pages, internal links, high-value URLs, metadata, and redirect samples.                                               | Important content and traffic paths have a confirmed Wix handling plan.                                                   |
| Custom behavior           | Apps, Velo/API logic, service plugins, external catalog data, custom fields, and third-party systems.                                                    | The requirement is assigned to standard scope, Add-ons, Custom Service, Wix setup, external implementation, or exclusion. |

Demo Migration should decide whether the Wix approach is safe to continue. If the sample does not include Wix’s highest-risk structures, the pass result is weak even when the sample looks clean.

### Validate Wix Products, Collections, Options, and Variants <a href="#validate-wix-products-collections-options-and-variants" id="validate-wix-products-collections-options-and-variants"></a>

Product validation should begin with catalog meaning. Wix Stores organizes products inside a catalog and uses collections to group products. Product options describe selectable properties, choices are the selections under each option, and variants represent combinations of options and choices. Because variants can carry values such as price, SKU, weight, and inventory, product validation should not stop at the parent product.

| Catalog area        | What to validate                                                                                           | Wix-specific failure signal                                                                |
| ------------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Product identity    | Product name, SKU, slug, status, product page visibility, duplicate handling, and product references.      | Products exist but staff cannot identify them or customers cannot reach the expected page. |
| Product content     | Descriptions, media, gallery order, product ribbons, labels, SEO fields, and rich content where supported. | Text or images transfer but do not support the Wix product-page experience.                |
| Options and choices | Size, color, material, style, bundle-like choices, personalization, and other customer selections.         | The selectable choice appears but loses order-detail, price, SKU, image, or stock meaning. |
| Variants            | Variant-level SKU, price, stock, weight, image, and availability.                                          | Parent product looks correct while variant-specific selling data is wrong or missing.      |
| Collections         | Grouping, merchandising, product assignment, and discovery role.                                           | Old category logic is imported but does not support actual Wix browsing or navigation.     |
| Inventory           | Variant-aware stock, tracked/untracked status, stock messages, and availability.                           | Stock is correct only at product level or does not match the sellable choice.              |

The validation set should include ordinary products and edge cases. A Wix migration is not fully proven until a variant-heavy product, media-heavy product, high-traffic product, stock-sensitive product, and collection-dependent product are reviewed in the target site.

### Validate Inventory, Availability, and Selling Context <a href="#validate-inventory-availability-and-selling-context" id="validate-inventory-availability-and-selling-context"></a>

Inventory validation should confirm that stock belongs to the correct sellable record. Wix inventory is tied to catalog item and variant meaning. If the source store stores inventory by parent product, warehouse, channel, marketplace, app, or custom field, the Wix result may need more review than a simple stock-count comparison.

The validator should check:

* whether inventory is expected for the product or variant;
* whether variant-level stock is preserved where supported;
* whether stock status and availability match the launch expectation;
* whether source warehouse or channel quantities were intentionally included, excluded, or simplified;
* whether out-of-stock products behave as expected in Wix;
* whether product visibility and stock behavior support the target storefront.

Inventory findings should be separated from live operational setup. Migrated stock values can support launch, but the merchant still needs to confirm Wix-side inventory settings, ongoing inventory management, integrations, and any external sync process.

### Validate Historical Orders Separately From Live Checkout <a href="#validate-historical-orders-separately-from-live-checkout" id="validate-historical-orders-separately-from-live-checkout"></a>

Wix orders manage the post-purchase lifecycle and include purchased items, payment details, shipping information, fulfillment status, payments/refunds, invoices, fulfillments, and order settings. Historical order validation should confirm that migrated orders remain useful for staff. It should not be treated as proof that live Wix checkout, payment providers, shipping rates, taxes, fulfillment rules, notifications, or order settings are ready.

| Order area          | Historical validation                                                                          | Live-readiness validation                                                    |
| ------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Order identity      | Order number, date, status, source reference, customer link, guest order behavior.             | Future orders are created through the configured Wix purchase path.          |
| Line items          | Products, variants, choices, quantities, prices, discounts, taxes, totals, and notes.          | New orders capture product and option choices correctly.                     |
| Payments            | Historical payment labels, transaction references, refunds, and payment state where available. | Wix payment providers and payment flow are configured and tested.            |
| Fulfillment         | Shipping method labels, addresses, delivery context, fulfillment status, tracking, and notes.  | Shipping, pickup, delivery, fulfillment, and notifications work after setup. |
| Discounts and taxes | Historical discount values, coupon labels, tax totals, and tax meaning.                        | Future tax and discount behavior is configured and tested in Wix.            |

A pass condition should state both results: historical orders are readable, and future Wix order creation has been tested through target configuration. One does not prove the other.

### Validate Customers, Contacts, Members, and CRM Meaning <a href="#validate-customers-contacts-members-and-crm-meaning" id="validate-customers-contacts-members-and-crm-meaning"></a>

Wix identity validation should be careful because a source store may distinguish customers, accounts, subscribers, contacts, members, loyalty users, booking participants, form submitters, wholesale users, and app-specific identities. Wix may handle customer, contact, member, and CRM-related information through different features or apps.

| Identity area            | What to validate                                                                                     | Pass condition                                                                                            |
| ------------------------ | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Customer records         | Names, emails, phone numbers, billing/shipping addresses, and order relationships.                   | Staff can connect customers to migrated orders and support history.                                       |
| Guest buyers             | Orders tied to buyers without full account behavior.                                                 | Guest history remains readable without implying a full member account.                                    |
| Contacts and CRM context | Contact details, subscriber meaning, form context, tags, notes, or marketing status where supported. | Contact meaning is not confused with commerce order history.                                              |
| Members                  | Site membership, login expectations, access rules, paid plans, or gated content where relevant.      | Member behavior is configured or separately scoped, not assumed from customer migration.                  |
| App-specific identity    | Loyalty, bookings, subscriptions, forums, courses, or other app-owned participation.                 | App records are assigned to standard scope, target setup, Custom Service, third-party work, or exclusion. |

The validation goal is practical identity continuity. If staff can find the right buyer and understand the customer’s historical context, the core customer migration may be usable. If the source store depends on membership access, loyalty data, subscriptions, or CRM automation, those expectations need separate review.

### Validate CMS Pages, Blog Posts, Media, URLs, and SEO Continuity <a href="#validate-cms-pages-blog-posts-media-urls-and-seo-continuity" id="validate-cms-pages-blog-posts-media-urls-and-seo-continuity"></a>

Wix is a site-builder commerce platform, so validation must include site content and traffic continuity when they are part of scope. Product migration alone does not prove that the Wix site is ready. Important CMS Pages, Blog Posts, media libraries, dynamic pages, internal links, menus, redirects, page titles, meta descriptions, canonical expectations, alt text, and domains may affect launch quality.

| Site area                       | What to validate                                                                               | Why it matters                                                            |
| ------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| CMS Pages                       | Page content, internal links, images, layout dependencies, and publish status.                 | Content pages may support trust, policies, buying guidance, or SEO.       |
| Blog Posts                      | Post titles, slugs, content, images, categories/tags where supported, and internal links.      | Blog content may bring search traffic and customer education value.       |
| Media                           | Product images, page images, gallery assets, filenames, alt context, and placement.            | Image availability does not prove image placement or page readiness.      |
| URLs and redirects              | Priority product, collection, CMS Page, Blog Post, and landing-page URLs.                      | Old traffic paths need an accepted Wix handling plan.                     |
| SEO fields                      | Page titles, meta descriptions, visible headings, index-sensitive content, and internal links. | Wix launch can lose SEO value if only products are checked.               |
| Domain and multilingual context | Domain assignment, published URL behavior, language paths, and redirect logic.                 | Site launch and traffic continuity depend on more than content migration. |

Validation should make the boundary clear. Migrating supported content is one task. Rebuilding layouts, redesigning pages, configuring menus, setting domains, publishing the site, polishing mobile layout, and managing analytics may be Wix-side or external launch work.

### Validate Apps, Velo/API Logic, Service Plugins, and External Systems <a href="#validate-apps-velo-api-logic-service-plugins-and-external-systems" id="validate-apps-velo-api-logic-service-plugins-and-external-systems"></a>

Wix can be extended with apps, Velo/API development, CMS collections, custom catalogs, checkout and shipping extensions, external payment services, forms, bookings, members, subscriptions, loyalty, and third-party integrations. Source stores can also contain app/plugin/module records that have no standard Wix destination. Validation should identify what is migrated, what is configured, what is rebuilt, and what is excluded.

| Dependency type  | Validation question                                                             | Likely handling path                                                            |
| ---------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Wix apps         | Does the target app need data, setup, or separate migration handling?           | Wix setup, app import, third-party work, or Custom Service review.              |
| Velo/API logic   | Is behavior code-driven rather than data-driven?                                | Rebuild, external implementation, or Custom Service review.                     |
| CMS collections  | Are records content, dynamic-page data, product-like data, or operational data? | Standard scope, Add-ons, Custom Service, or target setup depending on behavior. |
| Service plugins  | Does checkout, shipping, tax, payment, or fulfillment depend on custom logic?   | Wix configuration, service-plugin implementation, or Custom Service review.     |
| External systems | Do ERP, CRM, PIM, WMS, accounting, or marketplace records need continuity?      | External implementation, Custom Service review, or accepted exclusion.          |

The pass condition should not be “all apps work.” The pass condition should be that every business-critical dependency is identified and assigned to a realistic handling path.

### Validate Additional Migration Options Before Launch <a href="#validate-additional-migration-options-before-launch" id="validate-additional-migration-options-before-launch"></a>

If the source store remains active while Wix is being reviewed, validation should account for later migration activity. The merchant may need to continue the migration with the last used configuration, continue with a new configuration, or perform a new migration. The selected action changes the validation emphasis.

| Later action                              | Wix validation emphasis                                                                                |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Continue with the last used configuration | Newly added products, customers, orders, Blog Posts, CMS Pages, and representative regression samples. |
| Continue with a new configuration         | New records plus the Wix fields, filters, mappings, or settings affected by the changed configuration. |
| Perform a new migration                   | Refreshed target result, replaced earlier migrated data, scope accuracy, and launch-critical samples.  |

Entity Points should be interpreted consistently. New eligible records may consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because another migration action occurs on the same migration path.

### Build a Wix Validation Report <a href="#build-a-wix-validation-report" id="build-a-wix-validation-report"></a>

A Wix validation report should connect samples, findings, ownership, and decisions. It should not only show screenshots or record counts. Each finding should tell the team whether the issue is a migration correction, Wix setup task, Add-on adjustment, Custom Service review, external-system item, accepted limitation, or manual cleanup.

| Report field     | Purpose                                                                                                                                      |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Record or sample | Identifies the product, variant, collection, order, customer, member, CMS Page, Blog Post, URL, media item, app record, or workflow.         |
| Expected result  | Defines what the Wix result should show or support.                                                                                          |
| Observed result  | Describes what appears in Wix after migration.                                                                                               |
| Severity         | Separates launch blockers, important corrections, and minor cleanup.                                                                         |
| Handling path    | Classifies the issue as migration correction, target setup, Add-on, Custom Service, third-party work, accepted exclusion, or manual cleanup. |
| Owner            | Assigns responsibility to the merchant, Next-Cart, Wix setup team, app provider, developer, or external partner.                             |
| Status           | Confirms whether the finding is open, corrected, accepted, deferred, or excluded.                                                            |

The report should prove that the Wix site can be launched responsibly. It should also protect the team from treating unsupported custom behavior as an unresolved migration defect.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix validation should prove that the migrated result is usable as a Wix site-and-commerce environment. Products, collections, options, variants, inventory, orders, customers, contacts, members, CMS Pages, Blog Posts, media, URLs, redirects, apps, Velo/API logic, service plugins, and external systems all need the right level of review.

A strong validation process separates record presence from business meaning, historical order readability from live checkout setup, customer data from member/access behavior, and migrated content from Wix launch configuration. The result should be a clear validation report that identifies what passed, what needs correction, what belongs to Add-ons, what requires Custom Service review, what must be configured in Wix, and what is intentionally outside scope.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is product-count matching enough to validate a Wix migration?**

No. Product counts confirm presence, but Wix validation also needs product-page display, options, choices, variants, variant-level inventory, collections, SEO fields, media, and customer-facing purchase behavior.

**Should historical Wix orders and live checkout be validated separately?**

Yes. Historical orders prove whether past transaction data remains readable. Live checkout requires separate Wix configuration and testing for payment, shipping, tax, discounts, fulfillment, and notifications.

**What Wix samples are most useful for Demo Migration validation?**

Use samples that expose risk: variant-heavy products, products with multiple media, products tied to collections, guest orders, refunded orders, customer/member examples, CMS Pages, Blog Posts, high-value URLs, app-owned records, and custom logic examples.

**When should Wix app or Velo behavior trigger Custom Service review?**

Custom Service should be reviewed when the requirement involves unsupported app data, custom fields, external identifiers, Velo/API behavior, service-plugin logic, bespoke transformation, or external-system continuity beyond supported migration behavior.

**Do Additional Migration Options change Wix validation?**

Yes. Continuing the migration or performing a new migration changes which records and settings need review. New records, changed configuration, replaced target results, and launch-critical regression samples should be validated according to the selected action.
