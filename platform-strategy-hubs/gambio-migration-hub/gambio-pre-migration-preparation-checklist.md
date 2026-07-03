# Gambio Pre-Migration Preparation Checklist

Preparation for a Gambio migration should start with operating responsibility, not only with product exports. Gambio can be used as a Cloud environment or as a self-hosted shop, and that choice affects what the merchant must prepare before data is moved. A migration plan that ignores that choice may collect products, customers, and orders correctly while leaving hosting, updates, customization access, content ownership, and integration setup unclear.

The preparation phase should therefore answer three questions before Demo Migration: what must be migrated, what must be configured in Gambio, and what must be rebuilt or reviewed outside the migration scope. Products, categories, customers, orders, CMS Pages, Blog Posts where applicable, reviews, coupons, and other supported records may form the visible scope, but the practical readiness depends on the evidence behind those records.

For Gambio, the most important preparation areas are target environment choice, catalog and option structure, stock and downloadable product behavior, content and legal pages, customer and order interpretation, marketplace or payment connections, SEO-sensitive paths, and customization expectations. Each area should produce reviewable evidence before Full Migration.

### Confirm the Target Gambio Operating Model <a href="#confirm-the-target-gambio-operating-model" id="confirm-the-target-gambio-operating-model"></a>

The first preparation decision is whether the target store will use Gambio Cloud or self-hosted Gambio. The migration team should not treat this as a hosting footnote. It changes who is responsible for installation, updates, maintenance, technical access, and the practical boundaries of customization.

A Cloud target is usually better when the merchant wants less responsibility for hosting, installation, and updates. A self-hosted target is more suitable when the merchant needs deeper flexibility, custom development, specific integrations, or server-level control. Both paths can support a professional store, but they require different evidence before migration.

| Preparation item           | Why it matters                                                                             | Evidence to collect                                                                                            |
| -------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------- |
| Target environment         | Cloud and self-hosted Gambio create different responsibility boundaries.                   | Written decision on Cloud or self-hosted target, including hosting, update, access, and customization needs.   |
| Technical access           | Self-hosted projects may require server, file, database, or developer access.              | Hosting details, admin credentials, extension inventory, and access ownership.                                 |
| Update responsibility      | Update handling affects launch planning and post-launch maintenance.                       | Current version awareness, target version plan, maintenance owner, and update window.                          |
| Customization expectations | Deep customization may move work into Tailored Add-ons, Custom Add-ons, or Custom Service. | List of custom fields, modified templates, modules, checkout changes, external identifiers, and special rules. |
| Support expectations       | Support language, support scope, and merchant responsibility must be clear.                | Internal owner for German-language/vendor communication, store administration, and issue triage.               |

This decision should be made before product sampling. Otherwise, the Demo Migration may prove data movement into a target environment that does not match the merchant’s actual operating requirements.

### Audit Products, Articles, Options, and Stock Behavior <a href="#audit-products-articles-options-and-stock-behavior" id="audit-products-articles-options-and-stock-behavior"></a>

Gambio catalog preparation should focus on sellable meaning. The merchant should identify how source products are represented, what shopper choices exist, how inventory is controlled, and whether any products depend on logic outside standard catalog fields.

The word product can hide several different structures: simple articles, option-based products, downloadable products, image-heavy products, products with multiple category placements, bundled products, products with external inventory references, and products with custom fields. A clean preparation checklist separates those cases instead of treating all products as identical rows.

Products selected for Demo Migration should include normal items and edge cases. A representative sample should cover items with options such as size or color, items with stock reduction, items where stock control is not used, downloadable products, products with many images, products placed in deep categories, and products that appear in historical orders.

| Product pattern          | Preparation question                                                             | Why it affects Gambio migration                                                |
| ------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Simple physical products | Are title, SKU, price, description, images, category, and stock straightforward? | These prove the baseline catalog transfer.                                     |
| Option-based products    | Do options change price, stock, SKU, image, weight, or fulfillment instructions? | Shopper choices must remain understandable and order lines must stay readable. |
| Downloadable products    | Are files, access rules, and historical purchase expectations clear?             | Digital fulfillment can depend on permissions and order status.                |
| Image-heavy products     | Are images product-level, option-specific, externally hosted, or theme-managed?  | Visual completeness affects product confidence and conversion.                 |
| Custom catalog logic     | Are custom fields, modules, or external systems holding product meaning?         | Unsupported or bespoke logic may require Custom Service review.                |

The preparation output should include a product sample sheet, not just a product count. The sample should state why each item was selected and what must be checked after Demo Migration.

### Map Categories, Navigation, and SEO-Sensitive Paths <a href="#map-categories-navigation-and-seo-sensitive-paths" id="map-categories-navigation-and-seo-sensitive-paths"></a>

Gambio preparation should treat categories as storefront architecture. The merchant should identify not only category names, but also category hierarchy, high-value paths, product placement, internal linking, and SEO-sensitive URLs.

Many source stores use more than categories to create discovery. Collections, tags, menus, brand pages, landing pages, filters, and promotional blocks may all influence how shoppers find products. Some of those structures can become Gambio categories. Others may need content, navigation, redirect, or storefront configuration work.

Before migration, the merchant should prepare a category and URL map that identifies high-value product pages, high-value category pages, campaign landing pages, legal or trust pages, and pages receiving organic traffic. The goal is to avoid a target store where products exist but discovery is weaker.

A useful preparation map should include:

* important source URLs;
* target category or content destination;
* redirect requirement;
* menu placement expectation;
* metadata or SEO title priority;
* whether the page is a product, category, CMS Page, Blog Post, or external landing page;
* whether the page should be migrated, recreated, redirected, or retired.

This work prevents category migration from becoming a blind hierarchy import. It also gives the validation team clear expectations after Demo Migration and Full Migration.

### Prepare Content Pages, Legal Pages, and Trust Content <a href="#prepare-content-pages-legal-pages-and-trust-content" id="prepare-content-pages-legal-pages-and-trust-content"></a>

CMS Pages need preparation because they often carry business meaning beyond plain text. In a Gambio store, content may include legal notices, privacy pages, terms, shipping and return details, contact information, size guides, trust content, brand pages, buying guides, and campaign landing pages.

The merchant should classify pages before migration. Legal and trust pages should be reviewed separately from marketing pages. SEO landing pages should be reviewed separately from obsolete informational pages. Footer links, menu links, internal links, and form behavior should also be checked because moving page text alone does not guarantee that customers can find the content.

| Page type                     | Preparation action                                                                                      | Migration implication                                                       |
| ----------------------------- | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Legal and policy pages        | Confirm whether pages should be migrated, updated, replaced, or handled through a target-side provider. | Migration preserves content but does not validate legal correctness.        |
| Service pages                 | Identify shipping, returns, contact, payment, warranty, and support pages.                              | These pages affect customer trust and service clarity.                      |
| SEO landing pages             | Identify pages with traffic, backlinks, campaign use, or internal linking importance.                   | URL, metadata, and redirect handling may be more important than text alone. |
| Brand or buying-guide content | Decide whether content should become CMS Pages, Blog Posts, or redesigned target content.               | Content structure may need editorial cleanup, not only data movement.       |
| Obsolete pages                | Mark pages that should not be carried forward.                                                          | Migration should not preserve clutter that weakens the new store.           |

Content preparation is especially important when the source store has old legal pages, duplicated policy pages, theme-embedded footer content, hard-coded blocks, or app-generated landing pages. Those items should be reviewed before Full Migration so the target store does not inherit outdated or misplaced content.

### Review Customers, Orders, and Historical Service Context <a href="#review-customers-orders-and-historical-service-context" id="review-customers-orders-and-historical-service-context"></a>

Customer and order preparation should focus on usefulness after launch. A migrated order is valuable only if staff can understand it without repeatedly opening the old store. The preparation phase should identify how customer accounts, addresses, order statuses, product options, taxes, shipping methods, payment labels, discounts, refunds, and order notes are represented in the source store.

Gambio projects need special attention when the source store includes repeat customers, B2B buyers, tax-sensitive orders, marketplace orders, custom statuses, digital purchases, or option-heavy products. Those details can make historical records harder to interpret if they are not sampled before Demo Migration.

The merchant should prepare order samples from several scenarios:

* ordinary completed orders;
* cancelled, refunded, or partially fulfilled orders;
* orders with product options;
* orders with downloadable products;
* orders with discounts or coupons;
* different shipping methods and payment methods;
* orders from important customer groups;
* marketplace or external-system orders if those records exist.

For customers, the preparation should identify required account fields, addresses, newsletter expectations, customer group behavior, tax-exemption expectations if any, and whether customer history needs to remain linked to migrated orders. If customer data has duplicates or inconsistent addresses, that cleanup should be planned before Full Migration.

### Separate Native Data from Integrations and Custom Logic <a href="#separate-native-data-from-integrations-and-custom-logic" id="separate-native-data-from-integrations-and-custom-logic"></a>

Many Gambio migrations involve more than store records. Marketplace connections, payment provider settings, shipping integrations, ERP identifiers, accounting exports, tracking processes, email systems, and analytics scripts may all affect daily operations. These are not the same as product, customer, or order data.

Preparation should create an integration inventory. Each system should be classified as native configuration, connector configuration, external data ownership, custom logic, or post-launch implementation. This prevents the merchant from assuming that data migration recreates every operational connection.

| Dependency               | Preparation question                                                                                      | Likely handling                                                                           |
| ------------------------ | --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Marketplace connection   | Does the source store store channel IDs, imported orders, feed logic, or inventory synchronization rules? | Often requires connector setup or Custom Service review if identifiers must be preserved. |
| Payment provider         | Are transaction references needed for historical support?                                                 | Usually target configuration plus order-reference validation.                             |
| Shipping provider        | Are tracking numbers, shipping labels, or fulfillment statuses stored externally?                         | May require mapping, configuration, or separate integration work.                         |
| ERP or accounting system | Are products, customers, orders, or tax references synchronized externally?                               | Needs external identifier review and possible custom handling.                            |
| Theme or template logic  | Does the storefront display data through custom templates or hard-coded blocks?                           | Usually separate design or implementation work, not ordinary data migration.              |

This separation also helps keep Add-ons and Custom Service decisions clear. A bounded field mapping, filtering, or configuration need may fit an Add-on. Unsupported custom records, external-system identifiers, bespoke transformation, or custom migration logic adjustment may require Custom Service.

### Define Demo Migration Samples and Pass Conditions <a href="#define-demo-migration-samples-and-pass-conditions" id="define-demo-migration-samples-and-pass-conditions"></a>

Demo Migration should be planned before it is run. The merchant should decide which records must be included, what must be checked, and what would count as a pass or failure. Without pass conditions, Demo Migration becomes a visual inspection rather than a decision tool.

For Gambio, Demo Migration should include representative records from the areas most likely to affect launch quality: option-based products, stock-managed products, downloadable products, products in deep categories, image-heavy products, important CMS Pages, customers with multiple addresses, and orders with discounts, tax, shipping, payment, or status complexity.

| Sample area | Pass condition                                                                    | Failure signal                                                                  |
| ----------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Products    | Products are sellable, placed correctly, priced correctly, and visually complete. | Missing options, wrong stock behavior, broken images, unclear product identity. |
| Categories  | Category hierarchy and important product placement remain understandable.         | Products are present but hard to find or placed in weak discovery paths.        |
| CMS Pages   | Important pages are migrated, accessible, linked, and placed where needed.        | Legal, trust, or SEO pages exist as text but are not usable in the storefront.  |
| Customers   | Customer accounts and addresses remain identifiable and serviceable.              | Duplicate customers, missing addresses, broken order relationships.             |
| Orders      | Historical orders are readable for service, accounting reference, and support.    | Status, product option, payment, shipping, tax, or discount context is unclear. |

The output of Demo Migration should be a decision record. It should show what passed, what needs mapping/configuration change, what needs an Add-on, and what may need Custom Service.

### Prepare the Final Migration Window <a href="#prepare-the-final-migration-window" id="prepare-the-final-migration-window"></a>

The final migration window should be planned only after the store has enough evidence from preparation and Demo Migration review. For Gambio, that evidence should include the target operating model, catalog behavior, category structure, content-page readiness, customer and order interpretation, integration boundaries, and launch ownership. A short final window cannot fix unresolved structure. It can only execute decisions that have already been made.

Before Full Migration, confirm which records should be included, which recent changes need to be captured, which records may consume Entity Points when first migrated, and which follow-up needs may require Additional Migration Options. If the merchant expects to continue migration activity after launch, clarify whether that means continuing with the last used configuration, continuing with a new configuration, or performing a new migration. These choices affect planning and should not be discovered during launch week.

The final preparation output should be a launch-readiness checklist with owners. Next-Cart migration scope, Gambio configuration, merchant review, legal or trust content updates, payment and shipping setup, marketplace connection work, and custom implementation should each have a clear place. When ownership is visible, Full Migration becomes a controlled cutover rather than a rushed transfer.

Full Migration preparation should happen only after Demo Migration has clarified the target structure. Before the final run, the merchant should prepare the launch window, freeze expectations, review changed data, and confirm who owns each post-migration task.

The final preparation list should include:

* target Gambio environment confirmed;
* source store access confirmed;
* entity scope confirmed;
* Add-ons selected where needed;
* Custom Service items separated from standard scope;
* product/category/content samples validated;
* high-value URLs and redirects planned;
* payment, shipping, tax, and marketplace configuration owners identified;
* legal/content review owner identified;
* post-launch validation owner assigned;
* Additional Migration Options understood for follow-up needs.

If the merchant expects to keep selling during migration planning, changed records must be handled carefully. Additional Migration Options can be relevant after the initial migration path is validated: continuing with the last used configuration, continuing with a new configuration, or performing a new migration may support different follow-up needs. The correct option depends on whether the target plan has changed or only newer records must be brought forward.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio preparation should make operating responsibility, catalog meaning, content ownership, historical order readability, integrations, and validation evidence visible before Full Migration. The strongest plan does not merely collect products, customers, and orders; it explains how those records will behave inside the chosen Gambio environment.

When Cloud or self-hosted responsibility, product options, stock behavior, CMS Pages, external dependencies, and Demo Migration pass conditions are clear, the project is easier to scope and easier to validate. That preparation reduces the risk of launching a target store that is populated but not operationally ready.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Gambio migration?**

Confirm whether the target will be Gambio Cloud or self-hosted Gambio. That decision affects update responsibility, technical access, customization expectations, and the evidence needed before migration.

**Should every product be reviewed before Demo Migration?**

Not individually at first. The better approach is to select representative products that expose the catalog’s real complexity, including options, stock, downloads, images, categories, and historical order relationships.

**Do content pages need preparation before migration?**

Yes. CMS Pages may include legal, trust, service, SEO, and conversion content. They should be classified so important pages are preserved and obsolete pages are not carried forward blindly.

**When should integrations be reviewed?**

Before Demo Migration whenever they affect products, customers, orders, inventory, marketplace records, payment references, shipping data, or external identifiers.

**What makes a Gambio migration ready for Full Migration?**

The target environment is confirmed, representative Demo Migration samples have passed, scope boundaries are clear, Add-ons and Custom Service needs are separated, and launch validation owners are assigned.
