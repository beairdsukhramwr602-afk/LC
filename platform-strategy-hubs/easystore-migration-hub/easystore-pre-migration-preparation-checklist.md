# EasyStore Pre-Migration Preparation Checklist

EasyStore by JoomShaper migration preparation should begin with one practical distinction: EasyStore commerce data lives inside a Joomla site. Product records, categories, variants, inventory, customers, orders, refunds, coupons, tax, shipping, payment behavior, checkout settings, product pages, SP Page Builder layouts, menus, aliases, modules, templates, and Joomla users may all influence whether the migrated result is usable.

Good preparation does not mean every target-side setting must be finalized before migration starts. It means the merchant can explain what should migrate as supported data, what must be configured in EasyStore or Joomla, what must be rebuilt as site presentation, and what requires Add-ons or Custom Service review. Without that separation, Demo Migration findings can be misread: a missing layout may be a target implementation task, while a missing variant or broken customer-order relationship may point to migration scope.

### Define the Target EasyStore Operation First <a href="#define-the-target-easystore-operation-first" id="define-the-target-easystore-operation-first"></a>

The target store should be described as an operating environment before records are moved. EasyStore may support a compact catalog, a content-led product site, a visually designed storefront, a service-and-product business, or a store with more complex checkout and fulfillment needs. The preparation work should clarify which version of that future store the merchant intends to run.

A vague target model creates weak validation later. Products may migrate correctly, but the team may still not know where they belong, which menu exposes them, whether SP Page Builder controls important layouts, or whether tax, shipping, payment, inventory, and customer account behavior are ready for launch.

| Target operation question                                                             | Why it matters before migration                                                     |
| ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Will EasyStore be the primary store or one commerce area inside a larger Joomla site? | Defines how much navigation, content, menu, and page-builder work must be reviewed. |
| Will products be simple, variant-heavy, or configuration-sensitive?                   | Shapes product sample selection and mapping expectations.                           |
| Will SP Page Builder control important product or landing-page presentation?          | Separates migrated commerce records from page-layout implementation.                |
| Will checkout require specific tax, shipping, payment, coupon, or refund behavior?    | Prevents historical records from being confused with live configuration.            |
| Will customers need account continuity or only historical reference?                  | Affects customer, order, and Joomla user preparation.                               |

The output of this step should be a short target-operation note. It does not need to be a formal project plan, but it should be specific enough to guide sample selection and service-path decisions.

### Confirm Joomla and EasyStore Readiness <a href="#confirm-joomla-and-easystore-readiness" id="confirm-joomla-and-easystore-readiness"></a>

EasyStore preparation depends on a clear Joomla foundation. The target Joomla site does not need to be visually complete, but the merchant should know the version, template direction, extension stack, menu structure, language structure, user/account expectations, and whether SP Page Builder or other tools will control important storefront pages.

This matters because EasyStore records can be present while the site remains incomplete. A product page may need Joomla menu exposure, a layout may need SP Page Builder work, a category may need a navigation decision, or a checkout step may require target configuration. Preparation should identify these areas before the merchant judges migration quality.

| Readiness area         | What to confirm                                                                               | Migration impact                                                                         |
| ---------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Joomla environment     | Target site access, version, admin permissions, template direction, installed extension stack | Prevents data migration from being reviewed in an unstable or unknown target.            |
| EasyStore installation | EasyStore version, store settings, product/category setup expectations, checkout readiness    | Ensures migrated records have a target structure to enter.                               |
| Menus and aliases      | Store entry points, product/category routes, priority old URLs, internal links                | Supports SEO and storefront continuity planning.                                         |
| SP Page Builder usage  | Product sections, landing pages, promotional blocks, custom layouts                           | Separates data transfer from page-builder implementation.                                |
| Users and access       | Joomla users, groups, permissions, customer account expectations                              | Clarifies whether customer data, login behavior, and access rules are separate concerns. |

If the target environment is not ready enough for a meaningful Demo Migration review, that should be treated as a readiness issue rather than a migration failure.

### Audit Product Data as Selling Structure <a href="#audit-product-data-as-selling-structure" id="audit-product-data-as-selling-structure"></a>

Product preparation should focus on how the store sells, not only how many products exist. EasyStore supports product creation, product organization, product variants, product imagery, inventory management, coupons, order management, refunds, tax, shipping, checkout, and payment integrations. Those capabilities make product structure central to migration planning, especially when the source platform uses variants, options, custom fields, or page-specific merchandising.

The product audit should include simple products, variant-heavy products, image-heavy products, products in multiple categories, products with sale pricing, products with coupons, products with shipping or tax sensitivity, inventory-sensitive products, and products that depend on custom source fields or third-party logic.

| Product preparation area | Evidence to collect                                                                               | Why it matters                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Product basics           | Names, SKUs, descriptions, prices, categories, tags, brands, images                               | Establishes the ordinary migration baseline.                           |
| Variants and options     | Size, color, material, bundle-like choices, option pricing, option inventory, option images       | Tests whether shopper choices remain understandable in EasyStore.      |
| Inventory behavior       | Stock values, availability rules, low-stock examples, variant-level stock examples                | Prevents stock assumptions from being validated only at product level. |
| Coupons and promotions   | Active codes, historic coupon use, discount examples, sale-price behavior                         | Separates historical order context from active promotional setup.      |
| Custom product data      | Source fields, extension-created values, external IDs, ERP references, page-builder-driven fields | Identifies Add-on or Custom Service signals before migration begins.   |

The sample set should include commercially important records, not just clean examples. Best sellers, seasonal items, products used in campaigns, and products that often create support questions are especially useful because they reveal whether the migrated result supports the real business.

### Prepare Customer, Order, and Refund Examples <a href="#prepare-customer-order-and-refund-examples" id="prepare-customer-order-and-refund-examples"></a>

Customer and order data should be prepared for operational review. Historical records may support customer service, refund reference, fulfillment questions, repeat-buyer recognition, warranty review, or financial lookup. The migration does not need to reproduce every live workflow automatically, but it should preserve useful history where those records are included in scope.

Customer preparation should identify guest buyers, registered customers, duplicate emails, customers with multiple addresses, customer profiles connected to important orders, and any source-specific fields such as membership values, tax identifiers, company fields, loyalty data, or external CRM references. Order preparation should include ordinary paid orders plus exception examples.

| Record type           | Samples to prepare                                                     | Review purpose                                                        |
| --------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Registered customers  | Customers with complete contact details and order history              | Checks customer identity and buyer-history continuity.                |
| Guest buyers          | Orders placed without account creation                                 | Shows whether buyer context remains useful.                           |
| Discounted orders     | Orders using coupons, sale prices, or manual discounts                 | Tests discount readability in historical records.                     |
| Refunded orders       | Partial and full refunds where available                               | Checks support and financial reference value.                         |
| Shipping/tax examples | Orders with different regions, tax rates, shipping methods, and totals | Prevents live configuration from being confused with historic values. |
| Variant orders        | Orders containing important product variants                           | Confirms that line-item meaning is preserved.                         |

Payment references, shipping values, tax amounts, coupon use, and refunds should be reviewed as historical context. Live payment integrations, tax rules, shipping methods, and checkout behavior still need target-side configuration and testing.

### Map Storefront, SEO, and Presentation Dependencies <a href="#map-storefront-seo-and-presentation-dependencies" id="map-storefront-seo-and-presentation-dependencies"></a>

EasyStore migration planning should include more than product fields. Joomla menus, aliases, SEF URLs, redirects, template behavior, modules, SP Page Builder layouts, content pages, Blog Posts, and internal links may determine whether customers can find the migrated store after launch.

Preparation should identify high-value product URLs, category URLs, landing pages, navigation paths, content pages that link to products, campaign links, and any page-builder sections that present products or promotions. This does not mean every old page must be rebuilt through migration. It means the merchant should decide which paths need migration, redirect planning, manual rebuild, or separate implementation.

| Storefront area           | Preparation action                                                                        | Risk if skipped                                               |
| ------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Product and category URLs | List priority source URLs and expected target paths                                       | SEO and campaign traffic may lose destination continuity.     |
| Joomla menus              | Identify store entry points and high-value navigation paths                               | Products may exist but remain hard to reach.                  |
| SP Page Builder layouts   | Identify product sections, landing pages, promotional blocks, and custom product displays | Visual expectations may be confused for data migration scope. |
| CMS Pages and Blog Posts  | Identify content that supports commerce decisions                                         | Important buying context may be lost or rebuilt late.         |
| Internal links            | Review links from content to product/category pages                                       | Old paths may remain inside the target site.                  |

This preparation step is especially important for content-led Joomla stores. A migrated product record is only one part of the customer journey.

### Identify Extension-Owned and Custom Data Early <a href="#identify-extension-owned-and-custom-data-early" id="identify-extension-owned-and-custom-data-early"></a>

EasyStore may operate alongside other Joomla extensions, custom fields, custom modules, SP Page Builder addons, ERP or CRM integrations, analytics tools, fulfillment systems, marketplace feeds, or bespoke source logic. These areas need early identification because they may not behave like ordinary product, customer, or order records.

The key question is ownership. If a field was created by a source extension, custom import, external system, or manual workaround, the team should not assume standard migration behavior. It should be classified before scope approval.

| Custom-data signal                                                                      | Likely preparation response                                                              |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Supported records need filtering, exclusion, or simple mapping adjustment               | Review Add-ons where bounded supported behavior is enough.                               |
| Product/customer/order fields are custom, extension-owned, or source-specific           | Prepare examples for Custom Service review.                                              |
| External IDs connect records to ERP, CRM, accounting, fulfillment, or reporting systems | Confirm whether those identifiers must be preserved and where they should live.          |
| Storefront presentation depends on page-builder or template logic                       | Treat as implementation, custom review, or manual rebuild depending on expected outcome. |
| Business process depends on a third-party Joomla extension                              | Identify whether data is migratable, configurable, or outside supported scope.           |

This classification protects the merchant from assuming that every visible source-field value has a standard EasyStore destination.

### Choose Demo Migration Samples Deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the store’s real structure, not only the easiest records. The sample set should include products, customers, orders, URLs, and presentation examples that reveal the most important migration assumptions.

| Sample group           | Include examples that show                                                                         |
| ---------------------- | -------------------------------------------------------------------------------------------------- |
| Product structure      | Simple products, variants, images, categories, sale pricing, stock, and custom fields.             |
| Customer identity      | Registered customers, guest buyers, duplicates, customer-order links, and important buyer records. |
| Order history          | Ordinary orders, variant orders, discounted orders, refunded orders, shipping/tax examples.        |
| Joomla site continuity | Priority product/category URLs, menu exposure, content links, and page-builder dependencies.       |
| Configuration boundary | Tax, shipping, payment, coupon, refund, review, and checkout behavior that may need setup.         |
| Custom scope           | Extension-owned values, outside-system IDs, custom fields, and bespoke business logic.             |

The review result should classify each finding as migration correction, Add-on adjustment, Custom Service review, EasyStore/Joomla configuration, manual rebuild, accepted limitation, or post-launch cleanup.

### Plan for Launch-Window Changes <a href="#plan-for-launch-window-changes" id="plan-for-launch-window-changes"></a>

Many stores continue operating while migration is being reviewed. New products, customers, orders, refunds, coupons, or content changes may appear after Demo Migration. Preparation should define how those changes will be handled before launch.

| Launch-window question                                                           | Planning reason                                                         |
| -------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Will the Source Platform continue selling during review?                         | Determines whether newly created records need another migration action. |
| Will EasyStore mapping, filtering, or configuration change after Demo Migration? | Changes what must be revalidated.                                       |
| Should the target result be continued or rebuilt with a new migration?           | Controls expectations for replaced or newly added target data.          |
| Which newly created records matter most before launch?                           | Supports Entity Points planning and validation focus.                   |

Entity Points should be planned around newly migrated eligible entities. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path, but newly migrated eligible Products, Customers, Orders, or Blog Posts may consume Entity Points when migrated for the first time.

### Conclusion <a href="#conclusion" id="conclusion"></a>

EasyStore by JoomShaper preparation should clarify what the merchant expects the Joomla commerce environment to do after migration. The important work is not only gathering products, customers, and orders. It is also identifying variants, inventory, coupons, refunds, tax, shipping, payment references, Joomla menus, URLs, SP Page Builder presentation, customer identity, extension-owned data, custom fields, and launch-window changes.

A well-prepared EasyStore migration gives Demo Migration a fair test. It separates migrated data from target-side configuration, highlights Add-on and Custom Service signals early, and gives the merchant enough representative examples to judge whether the target result is suitable for launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Does EasyStore migration preparation require a finished Joomla website?**

No. The target site does not need to be visually complete, but the Joomla and EasyStore environment should be defined well enough to review migrated records. Menus, store entry points, layouts, and key configuration areas should not be completely unknown.

**Which EasyStore product examples should be prepared first?**

Start with simple products, variant-heavy products, products with important images, products in multiple categories, discounted products, inventory-sensitive products, and high-value products that represent real customer buying behavior.

**Should SP Page Builder layouts be treated as migration data?**

Not by default. SP Page Builder may control important storefront presentation, but page layouts, landing sections, and visual blocks often require implementation review or manual rebuild rather than ordinary commerce-record migration.

**When should Custom Service be considered during preparation?**

Custom Service should be considered when migration expectations involve unsupported extension data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment beyond supported behavior.

**How should newly created source records be handled before launch?**

Define whether migration activity will continue with the last used configuration, continue with a new configuration, or be performed as a new migration. The selected action determines what should be checked again before launch.
