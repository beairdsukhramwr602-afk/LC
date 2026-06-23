# Shopify Pre-Migration Preparation Checklist

Shopify preparation should turn source-store complexity into clear Target Store decisions before migration execution begins. A source export can show what exists, but it does not decide how products, variants, collections, customer context, CMS Pages, Blog Posts, URLs, apps, metafields, themes, markets, or external identifiers should work after migration.

A prepared Shopify migration gives each important source-store behavior a target destination. Some records can move through standard supported migration behavior. Some need Shopify configuration. Some need apps, theme work, metafields, metaobjects, mapping decisions, filtering, or Custom Service review. The preparation goal is to make Demo Migration and Full Migration review easier to judge because the expected Shopify outcome is already defined.

### Confirm the Target Store Structure <a href="#confirm-the-target-store-structure" id="confirm-the-target-store-structure"></a>

Start by defining the intended Shopify operating model. Shopify is a hosted SaaS Target Platform, so the migration should prepare for Shopify-defined product, collection, content, URL, customer, order, market, app, and theme structures rather than assuming the Source Platform structure can be copied without interpretation.

Target Store preparation should confirm:

| Area to confirm                 | Shopify preparation decision                                                                                                                                    | Why it matters                                                                                                                           |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Product model                   | Decide which source items should become Shopify products, options, variants, metafields, metaobjects, tags, product content, or app-managed behavior.           | Buying choices and product presentation need to remain understandable after migration.                                                   |
| Collection and navigation model | Decide how source categories, product groups, menus, filters, and landing pages should become Shopify collections, menus, filters, redirects, or content pages. | Customers need practical browse paths, not only migrated product records.                                                                |
| Content model                   | Identify CMS Pages, Blog Posts, policy pages, buying guides, and internal links that must remain useful.                                                        | Shopify content and storefront navigation affect trust, SEO continuity, and buying confidence.                                           |
| Customer and order model        | Define what returning customers, support teams, and operational teams need from migrated customer and order history.                                            | Customer and order records may migrate while account access, loyalty, subscriptions, or support context still require separate handling. |
| App and custom-data model       | Identify apps, source extensions, custom fields, metafields, metaobjects, external systems, and custom logic that carry business meaning.                       | App-owned or custom data may not behave like ordinary platform records.                                                                  |
| Market and domain model         | Confirm countries, languages, currencies, domains, subfolders, redirects, and localized content that matter at launch.                                          | International structure can affect storefront routing, pricing expectations, SEO, and customer experience.                               |

This structure should be confirmed before relying on record volume or Entity Points as the main readiness signal. Entity Points help estimate migration capacity, but they do not decide how Shopify should represent source-store meaning.

### Prepare Catalog and Product Data <a href="#prepare-catalog-and-product-data" id="prepare-catalog-and-product-data"></a>

Shopify catalog preparation should separate true buying choices from descriptive, operational, merchandising, and custom data. Source platforms often store product options, attributes, configurable products, grouped products, bundles, kits, personalization fields, specifications, and extension-driven rules in overlapping ways. Shopify requires those meanings to be assigned to the right target structure.

Prepare product samples that include:

* best-selling and high-margin products;
* simple products that should migrate cleanly;
* products with multiple options such as size, color, material, capacity, pack size, or style;
* products with variant-level SKU, price, stock, barcode, image, weight, fulfillment, or tax differences;
* configurable, grouped, bundled, kit, subscription, warranty, or add-on product behavior;
* personalized products that use engraving, file upload, custom text, build-your-own logic, or customer input;
* products with rich specifications, compatibility data, size guides, technical tables, or product relationships;
* products controlled by source extensions, apps, scripts, custom fields, external systems, or manual business rules;
* products that should be merged, split, simplified, retired, or rebuilt in Shopify.

Each sample should explain the commercial outcome that must survive migration. The preparation question is not only whether the product can be transferred. The product should remain understandable, purchasable, searchable, presentable, and operationally useful in Shopify.

The catalog review should classify source product details before migration:

| Source detail                      | Preparation decision                                                                                                                |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Real purchase choice               | Review whether it should become a Shopify option and variant.                                                                       |
| Descriptive product information    | Decide whether it belongs in product content, metafields, metaobjects, or theme display.                                            |
| Filter or merchandising value      | Decide whether it should support collection filters, tags, product type, vendor, metafields, or app-based search.                   |
| Bundle, kit, or subscription logic | Identify whether Shopify setup, an app, or Custom Service review is needed.                                                         |
| External-system identifier         | Preserve only when it remains useful for ERP, PIM, CRM, warehouse, accounting, analytics, marketplace, support, or fulfillment use. |
| Obsolete source field              | Exclude, archive, or deprioritize if it no longer supports the future store.                                                        |

Product preparation should reduce target-store clutter. Moving every source field into Shopify without role classification can produce weak product pages, noisy filters, unnecessary metafields, app conflicts, and harder validation.

### Prepare Customer, Account, and Order Data <a href="#prepare-customer-account-and-order-data" id="prepare-customer-account-and-order-data"></a>

Customer and order preparation should focus on usefulness, not only transferability. A migrated customer name, email address, address, or order record may be present in Shopify while the business context behind that record changes.

Prepare customer samples that include:

* registered customers and guest-checkout customers;
* customers with multiple addresses;
* customers with tags, groups, segments, tax status, or special support history;
* customers associated with loyalty, subscription, membership, wholesale, B2B, or customer-specific pricing expectations;
* customers whose historical orders are important for support, returns, warranty, reporting, or repeat purchase.

Prepare order samples that include:

* paid, pending, refunded, partially refunded, canceled, and partially fulfilled orders;
* orders with discounts, taxes, shipping differences, gift cards, store credit, notes, refunds, or manual adjustments;
* orders linked to marketplace, ERP, accounting, warehouse, fulfillment, subscription, loyalty, CRM, analytics, or support systems;
* orders with source reference numbers or outside-system identifiers that teams still use;
* orders from priority markets, languages, currencies, or regional storefronts.

Returning-customer expectations should be defined before launch planning. Preparation should clarify whether customers need account activation, password reset communication, loyalty or subscription handling, wholesale review, order-history access, customer tags, or support-team instructions after migration.

The main preparation decision is whether customer and order records are enough by themselves. If customer behavior depends on apps, external systems, custom fields, customer groups, wholesale logic, loyalty balances, subscription records, or source-specific identifiers, those dependencies should be documented before the migration scope is approved.

### Prepare Content, URLs, and SEO Inputs <a href="#prepare-content-urls-and-seo-inputs" id="prepare-content-urls-and-seo-inputs"></a>

Shopify preparation should protect commercially important paths, not merely produce a large redirect list. Source platforms may use category paths, product IDs, brand routes, language folders, campaign URLs, CMS Pages, Blog Posts, custom routes, filtered URLs, or platform-specific URL patterns that need deliberate Shopify destinations.

Prepare a URL and content inventory with these groups:

| Input group                            | What to prepare                                                                                                              |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| High-value product URLs                | Source URL, target Shopify product destination, handle expectation, redirect priority, and revenue or traffic value.         |
| Category or collection-equivalent URLs | Source category path, intended Shopify collection or content destination, customer intent, and SEO priority.                 |
| CMS Pages and Blog Posts               | Source paths, target destinations, internal links, page purpose, metadata, and localization needs.                           |
| Campaign and paid-media URLs           | Active campaign routes, landing pages, partner links, affiliate paths, UTM-sensitive destinations, and retirement decisions. |
| External-link destinations             | Backlinks, support documents, marketplace links, social links, email links, and partner references.                          |
| Localized or market-specific URLs      | Domains, subdomains, subfolders, language paths, regional content, and market-specific destination rules.                    |
| Retired or obsolete URLs               | Whether each path should redirect, remain unavailable, or point to a stronger replacement page.                              |

Content preparation should also review product descriptions, collection descriptions, page titles, meta descriptions, media references, internal links, policy pages, trust pages, buying guides, size guides, FAQs, and Blog Posts. Content that supports buying confidence or search continuity should not be treated as a secondary migration detail.

Redirect preparation should be tied to customer purpose. A discontinued product might need a similar replacement product, a relevant collection, a buying guide, or a retirement decision. A source category might need a Shopify collection, a landing page, a filtered experience, or a redirect to a stronger customer destination. The best redirect target is the one that preserves intent, not necessarily the closest old label.

### Review Apps, Extensions, Integrations, or Custom Data <a href="#review-apps-extensions-integrations-or-custom-data" id="review-apps-extensions-integrations-or-custom-data"></a>

Shopify preparation should identify where source-store meaning is controlled by apps, extensions, modules, custom fields, custom code, external systems, or manual workflows. These dependencies often carry behavior that cannot be understood from ordinary product, customer, order, content, or URL exports alone.

Prepare a dependency inventory that answers:

| Dependency type                          | Preparation question                                                                         | Likely planning outcome                                                                                                         |
| ---------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Source extension, module, plugin, or app | What business function does it control?                                                      | Decide whether Shopify native settings, a Shopify app, configuration, Add-ons, or Custom Service should handle the requirement. |
| Shopify app                              | What target behavior will the app own after migration?                                       | Confirm app setup, import limits, vendor support, configuration responsibility, and review samples.                             |
| Metafield or metaobject                  | What source meaning should become structured Shopify data?                                   | Define namespace, field purpose, display owner, and whether custom migration logic adjustment is needed.                        |
| Theme behavior                           | What storefront display, product page, navigation, or content behavior depends on the theme? | Separate migrated data from theme configuration and design implementation.                                                      |
| External system                          | Which identifiers or records must remain usable outside Shopify?                             | Preserve ERP, PIM, CRM, accounting, warehouse, fulfillment, marketplace, analytics, or support references where needed.         |
| Custom field or custom table             | What business meaning is stored outside standard records?                                    | Decide whether the data should be mapped, archived, configured, transformed, or reviewed under Custom Service.                  |

Add-ons and Custom Service should remain separate during preparation. Add-ons support defined filtering, mapping, or data configuration within supported migration behavior. Custom Service applies when the requirement involves Custom Platform handling, unsupported app or extension data, custom fields, bespoke transformation, outside-system identifiers, or custom migration logic adjustment.

A dependency inventory should not assume that every source function must be recreated exactly. Some legacy behavior should be replaced with Shopify-native settings, some should move to an app, some should be simplified, and some may no longer be commercially useful.

### Prepare Access, Backups, and Migration Inputs <a href="#prepare-access-backups-and-migration-inputs" id="prepare-access-backups-and-migration-inputs"></a>

Operational readiness should be confirmed before Demo Migration or Full Migration work begins. Missing access, unclear permissions, incomplete backups, or unassigned review responsibilities can delay the project even when the data plan is strong.

Prepare these access and control items:

* source-store admin access with permission to review and export relevant records;
* Shopify admin access with enough permission for migration setup and result review;
* collaborator access, staff-account permissions, or app/API access where needed;
* source-store backup or rollback reference appropriate to the Source Platform;
* target-store backup, duplicate theme, staging theme, or controlled pre-launch review method where relevant;
* password protection, storefront visibility, domain timing, tax settings, shipping setup, payment-test settings, notification settings, and launch controls;
* access to app, extension, integration, ERP, PIM, CRM, marketplace, accounting, warehouse, analytics, or fulfillment systems when those systems affect migration review;
* named reviewers for catalog, customer, order, content, URL, app, and operational checks;
* clear responsibility for who can approve launch-critical decisions.

Migration inputs should be prepared in a way that supports execution and review. Useful inputs include source exports, admin access, sample records, URL lists, content inventories, app dependency notes, custom-field maps, market and localization requirements, and service-scope decisions that were already approved.

Access preparation should also clarify whether the customer will perform migration steps directly through the selected Migration Service or whether Next-Cart will perform agreed work under the final service plan. The selected service determines responsibility and included work, not whether the customer can access the migration process.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

Demo Migration should test the Shopify outcome that matters most. A sample made only from simple products and ordinary customers can create false confidence because it does not expose product-structure pressure, app dependencies, URL issues, customer-account expectations, or order-history complexity.

Prepare Demo Migration samples that include:

* simple products and structurally complex products;
* products with multiple options, variants, images, SKUs, prices, stock differences, and fulfillment differences;
* products using metafields, metaobjects, apps, theme display, or external-system identifiers;
* important collections, source category paths, menus, filters, and discovery journeys;
* CMS Pages and Blog Posts that affect trust, SEO, customer support, or campaign continuity;
* customer records with addresses, tags, groups, loyalty, subscription, wholesale, or support significance;
* orders with different statuses, discounts, taxes, refunds, notes, shipping methods, and fulfillment contexts;
* priority legacy URLs and localized paths;
* source records that may require Add-ons, Custom Service, or post-migration configuration.

Each sample should include an expected result. A useful Demo Migration sample explains what must be checked in Shopify: product buying clarity, variant behavior, collection placement, content usefulness, customer context, order history, URL destination, app dependency, metafield placement, or external identifier continuity.

Demo Migration review should not be treated as final launch validation. It is a preparation tool that helps expose whether the target Shopify model is clear enough before Full Migration decisions are made.

### Final Preparation Check <a href="#final-preparation-check" id="final-preparation-check"></a>

A Shopify migration is ready to move forward when the target structure, migration inputs, and review samples are clear enough to support execution. The final preparation check should confirm:

* the intended Shopify product, collection, content, customer, order, URL, market, app, and custom-data structure is documented;
* important product samples explain the expected Shopify outcome;
* customer and order samples include records that matter for support, reporting, repeat purchase, and operational continuity;
* high-value URLs, CMS Pages, Blog Posts, collection paths, campaign pages, and localized paths have target decisions;
* app, extension, integration, metafield, metaobject, custom-field, and external-system dependencies are inventoried;
* source and target access, backups, permissions, and launch controls are ready;
* Demo Migration samples are selected for risk visibility, not convenience;
* Add-ons and Custom Service signals are documented separately;
* unresolved assumptions are assigned to configuration, mapping, filtering, Custom Service review, validation, cleanup, or business decision.

The final check should make the next step easier, not longer. If preparation still depends on vague statements such as “migrate everything,” “keep the same structure,” or “fix it after launch,” the Shopify migration is not ready for reliable execution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify preparation is strongest when it defines the future Target Store before migration execution begins. Product and variant evidence, collection logic, customer and order context, CMS Pages, Blog Posts, URL priorities, app dependencies, metafields, markets, access, backups, and Demo Migration samples should all point toward a clear Shopify operating model.

A clean preparation process does not remove every platform difference. It makes those differences visible early enough to assign the right handling path: Shopify configuration, supported migration behavior, Add-ons, Custom Service, validation, or business cleanup. That discipline gives Demo Migration and Full Migration results a practical standard for review.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to Shopify?**

Start with the records and behaviors most likely to affect revenue, customer trust, or operational continuity: complex products, priority collections, high-value URLs, important customer and order samples, app dependencies, market requirements, and Demo Migration samples.

**Why is product classification important before Shopify migration?**

Shopify separates product meaning across products, options, variants, metafields, metaobjects, tags, collections, apps, themes, and content. Product classification helps decide where each source detail should live so the migrated catalog remains clear and maintainable.

**Should Shopify preparation include apps and metafields?**

Yes. Apps, metafields, metaobjects, theme behavior, integrations, and custom fields often carry storefront, operational, or customer-experience meaning. They should be reviewed before migration so the team can separate standard data movement from configuration, Add-ons, or Custom Service needs.

**Does an Entity Points Plan solve Shopify preparation risk?**

No. Entity Points help estimate migration capacity for counted data, but they do not decide how products, variants, collections, URLs, apps, markets, customer expectations, or custom fields should work in Shopify.

**When should Custom Service be considered during Shopify preparation?**

Custom Service should be considered when the migration depends on Custom Platform source structures, unsupported app or extension data, custom fields, outside-system identifiers, bespoke transformation, or custom migration logic adjustment that cannot be handled safely through standard supported behavior alone.
