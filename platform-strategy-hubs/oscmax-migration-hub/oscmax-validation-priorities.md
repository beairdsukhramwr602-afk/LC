# osCMax Validation Priorities

osCMax validation has to prove more than whether familiar ecommerce records arrived. Many osCMax stores look close to osCommerce at the record level, but their actual business behavior may depend on bundled contributions, later modifications, template choices, admin shortcuts, custom shipping logic, image modules, article boxes, customer-group behavior, or old maintenance history. A validation review that only compares Products, Customers, and Orders can miss the behavior that made the store usable.

The practical goal is to confirm whether the migrated store can operate as the merchant expects in the Target Platform. That means every validation pass should separate three layers: the base ecommerce records, the contribution-shaped behavior around those records, and the storefront or admin behavior that may need configuration, Add-ons, or Custom Service review. When those layers are reviewed separately, Demo Migration and Full Migration evidence becomes much easier to interpret.

### What Validation Means for osCMax <a href="#what-validation-means-for-oscmax" id="what-validation-means-for-oscmax"></a>

Validation for osCMax should start with a simple question: is the store being validated as an ordinary osCommerce-like catalog, or as a contribution-shaped legacy store? The answer changes what the team must prove. If the store is simple, the review may focus on categories, Products, Customers, Orders, images, addresses, order statuses, coupons, and CMS Pages. If the store depends on old modules, templates, article boxes, custom order handling, modified shipping logic, or image behavior, validation must include the additional behavior that sits around the migrated records.

A strong validation process treats osCMax evidence as layered proof. First, confirm that eligible records migrated correctly. Second, confirm that migrated records still carry the right business meaning. Third, confirm that target-side configuration supports the expected storefront, checkout, admin, and reporting behavior. Fourth, identify anything that cannot be proven through Standard Service alone and may need Advanced Data Mapping, Advanced Data Configure, Add-ons, or Custom Service.

| Validation layer | What it proves                                                                                                       | Why it matters in osCMax                                                           |
| ---------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Record presence  | Products, Customers, Orders, categories, addresses, images, and other eligible records exist in the Target Platform. | Basic record counts do not prove contribution-shaped behavior.                     |
| Business meaning | Prices, attributes, order statuses, customer segmentation, shipping references, and content still make sense.        | Legacy modifications can change how ordinary records were interpreted.             |
| Target behavior  | Storefront navigation, checkout, catalog display, search, and admin usage behave as expected.                        | Templates and modules may have created behavior that does not migrate as raw data. |
| Scope boundary   | Unsupported custom logic is identified before launch.                                                                | Contribution-owned behavior may require Custom Service or target-side rebuilding.  |

This approach prevents a common mistake: treating validation as a final record-count check. For osCMax, validation is a business-continuity review. The store passes only when the migrated data and the Target Platform configuration can support the required customer, admin, and commercial behavior.

### Validate Version-Line and Environment Assumptions <a href="#validate-version-line-and-environment-assumptions" id="validate-version-line-and-environment-assumptions"></a>

Version clarity is one of the first validation priorities for osCMax because different stores may sit on different legacy branches, unofficial updates, or custom-maintained packages. Two stores with similar admin screens can still have different database changes, file overrides, contribution sets, and template expectations. A merchant should not assume that an osCMax label alone explains the migration scope.

During Demo Migration, the team should confirm the version evidence available from admin settings, database tables, file timestamps, maintenance notes, and extension history. The review should also check whether the store was upgraded cleanly or maintained through manual patching. If version information is incomplete, validation must be more conservative because unexpected custom columns, missing relationships, or old module traces may appear during data review.

Environment validation also matters because osCMax stores are often self-hosted. PHP version, database version, image paths, rewrite rules, file permissions, mail behavior, cron-like tasks, and hosting-specific configuration can influence what the old store actually did. Some of those settings are not migrated as commerce records, but they may explain why catalog images, contact forms, order exports, or shipping calculations behaved in a certain way.

A pass condition for this layer is not that every old technical setting is reproduced. The pass condition is that the team understands which environment assumptions affect migration scope and which assumptions belong to target-side setup. If the old store relied on server behavior or local file paths, those dependencies must be documented before Full Migration validation is considered reliable.

### Validate Catalog Structure and Contribution-Shaped Product Behavior <a href="#validate-catalog-structure-and-contribution-shaped-product-behavior" id="validate-catalog-structure-and-contribution-shaped-product-behavior"></a>

Catalog validation should go beyond checking product counts. osCMax stores may include standard product information, categories, images, specials, attributes, downloads, and stock, but the way those elements display or behave may be influenced by installed contributions. Image handling, product sliders, quick updates, restricted article visibility, special countdowns, or custom imprint fields are examples of behavior that may sit outside ordinary Product records.

The validation review should compare product identity first: SKU or model, product name, category assignment, product status, base price, special price, tax class, stock, image references, descriptions, and metadata. Then it should inspect behavior: whether product options still represent customer choices correctly, whether downloadable products remain purchasable, whether custom text or imprint-style input still has a target-side equivalent, and whether image galleries or thumbnails require separate configuration.

| Catalog area                    | Validation question                                                                                                  | Failure signal                                                                           |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Categories                      | Are Products assigned to the right hierarchy and visible in the expected navigation context?                         | Products exist but appear under the wrong category path or duplicate menu structure.     |
| Attributes and options          | Do customer choices still affect price, product meaning, or fulfillment correctly?                                   | Options import as labels but no longer support the original selling logic.               |
| Images                          | Are main images and additional image behavior preserved or replaced intentionally?                                   | Product pages load with missing thumbnails, broken gallery patterns, or orphaned images. |
| Specials and promotions         | Does discount timing, sale visibility, and price display still match business expectations?                          | Sale prices exist but expiry, countdown, or promotional presentation is lost.            |
| Content-linked catalog behavior | Are article boxes, news blocks, or restricted content treated as content and configuration, not simple product data? | Content appears as unstructured text or disappears from storefront validation.           |

A strong Demo Migration sample should include simple products, attribute-heavy products, special-price products, downloadable products, image-heavy products, and products affected by installed contributions. If the sample only includes clean products, it does not prove osCMax readiness.

### Validate Customers, Orders, and Commercial Meaning <a href="#validate-customers-orders-and-commercial-meaning" id="validate-customers-orders-and-commercial-meaning"></a>

Customers and Orders need careful validation because osCMax stores may include admin-facing shortcuts, contribution-based customer groups, phone-order behavior, order export routines, or customized status handling. A migrated order should not be treated as valid simply because its total, date, and customer name are present. The review must prove that the order still carries the meaning needed for customer service, reporting, and historical reference.

Customer validation should check account identity, email, addresses, customer group or wholesale status, newsletter preference where relevant, password handling expectations, and customer-to-order relationships. If the old store used restricted article access, distributor pricing, wholesale inquiries, or custom contact forms, the team should decide whether that behavior is part of migrated customer data, target configuration, a Tailored Add-on, or Custom Service.

Order validation should inspect order numbers, dates, customer links, product lines, quantities, taxes, discounts, shipping, payment references, order status history, comments, invoices, and exported reporting needs. For osCMax, order history may also be affected by old order-total modules or custom shipping modules. The validation task is to confirm that the order remains explainable after migration.

A useful pass condition is operational: a support agent should be able to open a migrated order and understand what the customer bought, what they paid, how shipping and tax were represented, what status the order reached, and what historical action may be required. If order data is technically present but not explainable, validation has not passed.

### Validate Storefront Templates, Content, and Navigation <a href="#validate-storefront-templates-content-and-navigation" id="validate-storefront-templates-content-and-navigation"></a>

Template validation is a major osCMax priority because storefront behavior may depend on old template structures, category boxes, infoBoxes, custom buttons, image assets, CSS files, or layout conventions. A migration can preserve catalog records while still producing a storefront that feels broken because the target theme does not reproduce the old navigation model or content placement.

The review should identify which storefront elements are data, which are target design or configuration, and which are legacy template behavior. Product descriptions, category names, CMS Pages, and image files may be migration scope. Template layout, generated button assets, sideboxes, navigation menus, and front-page modules are usually target-side implementation or Custom Service questions if they are deeply tied to custom logic.

Content validation should include homepage blocks, informational pages, contact pages, article/news areas, restricted content, category landing text, policy pages, and SEO-visible content. If the old store used content modules to display news, latest articles, promotional boxes, or special offers, the team should decide whether the target store needs equivalent CMS Pages, Blog Posts, page blocks, or custom configuration.

Search and navigation validation must also look at customer behavior. A merchant should test common product lookups, category browsing paths, header and sidebar navigation, and footer/policy access. The pass condition is not visual identity with the old site. It is that customers can find, evaluate, and purchase products without losing critical commercial context.

### Validate Integrations, Modules, and Customization Boundaries <a href="#validate-integrations-modules-and-customization-boundaries" id="validate-integrations-modules-and-customization-boundaries"></a>

osCMax validation should create a clear boundary between migrated data and old functionality. Installed modules may have controlled shipping rates, payment choices, order exports, email messages, content boxes, customer restrictions, image display, or admin productivity. Some of these can be replaced through native Target Platform configuration. Others may need Add-ons. Some require Custom Service because they involve custom tables, file changes, or contribution-specific records.

The team should make a module inventory before final validation. The inventory does not need to preserve every old module. It needs to identify which modules affected revenue, fulfillment, customer service, compliance, or launch readiness. A module that merely changed visual presentation may not need migration. A module that changed order totals, customer eligibility, shipping rates, product options, or export logic requires stronger review.

| Legacy behavior                | Validation path                                                                          | Likely handling                                                                              |
| ------------------------------ | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Old shipping module            | Compare historical rates and checkout behavior against target configuration.             | Target configuration, Add-ons, or Custom Service depending on complexity.                    |
| Order export routine           | Confirm required historical and operational export fields.                               | Advanced Data Mapping or Custom Service when fields are non-standard.                        |
| Template-specific boxes        | Identify whether they are content, navigation, or custom presentation.                   | Target theme/configuration or Custom Service when logic-driven.                              |
| Custom customer access         | Confirm whether access depends on customer group, content restriction, or bespoke logic. | Advanced Data Configure, Add-ons, or Custom Service.                                         |
| Image or gallery modifications | Validate main images, additional images, thumbnails, and gallery expectations.           | Standard migration for eligible images; target configuration or Custom Service for behavior. |

Validation should not overpromise. Add-ons support bounded migration needs. Custom Service handles requirements that need tailored review or non-standard handling. Neither should be described as automatic target-store development. The important decision is whether the old behavior must be preserved, replaced, retired, or rebuilt outside migration scope.

### Use Demo Migration Evidence to Decide Launch Readiness <a href="#use-demo-migration-evidence-to-decide-launch-readiness" id="use-demo-migration-evidence-to-decide-launch-readiness"></a>

Demo Migration evidence is especially important for osCMax because it gives the team a safe way to test high-risk assumptions before a Full Migration. The Demo Migration should not be limited to ordinary products and clean orders. It should include records affected by attributes, images, specials, downloads, customer groups, custom statuses, legacy modules, content pages, and template-driven behavior.

The merchant should review Demo Migration results against a written pass-condition list. For each record type, the question should be: what must be true for this to be considered usable after launch? That shifts validation away from subjective impressions and toward operational criteria.

| Demo evidence           | Launch-readiness question                                                                         |
| ----------------------- | ------------------------------------------------------------------------------------------------- |
| Product sample          | Do simple, attribute-heavy, image-heavy, and special-price Products remain commercially usable?   |
| Customer sample         | Are account identity, addresses, customer group meaning, and order links clear?                   |
| Order sample            | Are totals, statuses, comments, products, shipping, taxes, and historical references explainable? |
| Content sample          | Are CMS Pages, article-like content, policy pages, and navigation-critical text accounted for?    |
| Module-sensitive sample | Are contribution-owned behaviors identified as native target setup, Add-ons, or Custom Service?   |

If Demo Migration exposes gaps, the next decision should be precise. Continue the Migration with the last used configuration only when the issue is already understood and does not require scope change. Continue the Migration with a new configuration when mapping, filtering, configuration, or Add-ons need adjustment. Perform a new migration when the platform path, source data, or business scope has changed materially.

### Validate Launch Handoff and Post-Migration Ownership <a href="#validate-launch-handoff-and-post-migration-ownership" id="validate-launch-handoff-and-post-migration-ownership"></a>

A final osCMax validation pass should also define who owns each remaining task after migration. Legacy stores often carry small operational habits that are easy to miss: manual image cleanup, manual order export, admin shortcuts, content-box edits, custom email wording, old payment instructions, or a template-specific way to promote products. These habits may not be part of data migration, but they still affect the first week after launch.

The handoff review should separate launch blockers from post-launch improvements. A missing payment rule, broken product option, unexplained order total, or unavailable customer group can block launch because it changes selling or service continuity. A retired visual box or old admin shortcut may be documented as a post-launch improvement if the business no longer depends on it. This distinction keeps validation practical and prevents low-value legacy behavior from expanding migration scope.

| Handoff item                    | Validation decision                                | Ownership after review                                        |
| ------------------------------- | -------------------------------------------------- | ------------------------------------------------------------- |
| Critical checkout behavior      | Must be proven before launch.                      | Migration team and merchant approve jointly.                  |
| Historical order interpretation | Must be explainable for support and reporting.     | Merchant confirms business use.                               |
| Retired module behavior         | Must be documented as intentionally retired.       | Merchant owns acceptance.                                     |
| Target configuration gap        | Must be assigned before Full Migration approval.   | Target-store owner or Custom Service depending on complexity. |
| Post-launch enhancement         | Must not block migration unless business-critical. | Merchant roadmap or implementation team.                      |

The pass condition is a clean decision record. Every unresolved item should have an owner, a handling path, and a launch impact rating. Without that decision record, the team may technically complete migration while leaving the merchant with unclear responsibilities after launch.

### Validation Evidence That Should Block or Clear Launch <a href="#validation-evidence-that-should-block-or-clear-launch" id="validation-evidence-that-should-block-or-clear-launch"></a>

osCMax validation should produce a launch decision, not only a list of checked pages. A sample can look acceptable while still leaving unresolved questions about contribution-owned behavior, template dependency, image handling, shipping logic, or old order meaning. For that reason, validation evidence should be divided into pass evidence, watch evidence, and blocking evidence.

Pass evidence means the migrated records preserve commercial meaning and the Target Platform has a clear owner for related configuration. Product identity, category placement, customer records, order history, tax indicators, shipping references, and content records should be understandable without relying on the old osCMax admin.

Watch evidence means the migration is broadly sound but one behavior needs post-migration attention. For example, a product image may migrate correctly while old gallery behavior needs target-side configuration, or historical orders may migrate while an old export routine is replaced by a new reporting path. These items can proceed only when ownership is explicit.

Blocking evidence means Full Migration should not proceed until the issue is resolved. Examples include unidentified custom tables, missing product-option meaning, unclear customer-group behavior, checkout rules that no one can explain, or templates that hide business-critical navigation. Those are not cosmetic findings; they can change the service path.

| Validation evidence | What it proves                                                              | Launch implication                                       |
| ------------------- | --------------------------------------------------------------------------- | -------------------------------------------------------- |
| Pass evidence       | Data meaning is preserved and target-side ownership is clear.               | Safe to include in Full Migration planning.              |
| Watch evidence      | Data is usable but related behavior needs configuration or business review. | Proceed only with named owner and follow-up task.        |
| Blocking evidence   | Business meaning or behavior cannot be explained from available evidence.   | Resolve before Full Migration or escalate service scope. |

This evidence-based approach makes Demo Migration valuable. It turns legacy uncertainty into a controlled decision instead of postponing old osCMax questions until launch week.

### Conclusion <a href="#conclusion" id="conclusion"></a>

osCMax validation should prove business meaning, not just transfer completion. Because osCMax stores can combine osCommerce-like records with contribution-owned behavior, template dependencies, old version lines, and custom maintenance history, the validation process must inspect data, configuration, storefront behavior, and unsupported legacy logic as separate layers.

A strong validation result gives the merchant a practical launch decision. Products are usable, orders are explainable, customers remain connected to their history, content and navigation support purchasing, and old modules have been classified as preserved, replaced, retired, or escalated. When those conditions are met, Full Migration can move forward with clearer scope control and fewer late surprises.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is osCMax validation different from ordinary osCommerce validation?**

osCMax often carries osCommerce-like records, but the store may also depend on pre-installed contributions, old modules, templates, custom fields, and maintenance history. Validation must prove both the migrated records and the behavior around those records.

**Should every old osCMax module be recreated in the Target Platform?**

No. Each module should be classified by business value. Some behavior can be replaced by native target settings, some may need Add-ons, some may need Custom Service, and some should be retired rather than carried forward.

**What should be included in an osCMax Demo Migration sample?**

The sample should include ordinary records and high-risk records: attribute-heavy Products, image-heavy Products, special-price Products, downloadable Products, customer groups, unusual order statuses, content pages, and records touched by old modules.

**When should Custom Service be considered during osCMax validation?**

Custom Service should be considered when required behavior depends on custom tables, contribution-owned records, bespoke transformations, unsupported fields, old module logic, or external identifiers that cannot be handled through standard migration configuration.
