# Shift4Shop Pre-Migration Preparation Checklist

A Shift4Shop migration should begin with a prepared source store, not with an export file alone. Shift4Shop can support a wide range of catalog, storefront, customer, pricing, and B2B operations, but that flexibility only creates a clean migration outcome when the source data is reviewed before transfer begins.

Preparation should identify which records can move directly, which records need cleanup, which business rules need mapping, and which workflows should be rebuilt instead of copied. For stores coming from older 3dcart environments, preparation also needs to separate active Shift4Shop-ready data from outdated terminology, inactive integrations, abandoned custom fields, and legacy operating habits that no longer represent the business.

### Confirm the Target Store Structure <a href="#confirm-the-target-store-structure" id="confirm-the-target-store-structure"></a>

Start by confirming how the Shift4Shop store should operate after launch. The preparation phase should define the intended storefront hierarchy, navigation logic, customer segmentation, product organization, pricing behavior, and integration ownership before migration files are finalized.

A common mistake is to treat Shift4Shop as a blank destination that will simply receive source data. In practice, the target store structure affects how Products, Categories, Customers, Orders, Coupons, Reviews, CMS-like pages, and SEO inputs should be prepared. A product export that looks complete may still fail the launch plan if categories do not match the intended navigation, customer groups are not aligned with pricing rules, or old URLs are collected without redirect priorities.

| Preparation area           | What to confirm before migration                                                                                | Why it matters for Shift4Shop                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Storefront hierarchy       | Primary categories, subcategories, menu logic, landing pages, and key collection paths                          | Shift4Shop supports deep category organization and SmartCategories, so weak planning can create navigation clutter after migration.                 |
| Product presentation       | Which Products need options, Advanced Options, option templates, tabs, images, video, reviews, and Product Q\&A | Shift4Shop product pages can carry rich selling context; incomplete source preparation can reduce product usability even when core records migrate. |
| Customer treatment         | Customer groups, wholesale buyers, tax-exempt buyers, price-list logic, and B2B/B2C overlap                     | Customer records often drive pricing, visibility, tax, and ordering behavior rather than simple account storage.                                    |
| Order history use          | Whether Orders are needed for support, accounting, reorder reference, sales analysis, or legal recordkeeping    | Historical Orders should remain useful after migration, not merely present as static records.                                                       |
| SEO and content continuity | Priority URLs, page titles, metadata, Extra Pages, Blog Posts, redirects, and high-value content                | Shift4Shop migrations often involve storefront route changes, so SEO inputs need preparation before full transfer.                                  |

The target structure should also clarify what does not need to be carried forward. Old categories, inactive customer groups, unused discounts, obsolete integration fields, duplicate products, retired content pages, and legacy 3dcart labels can all increase migration noise. Preparation should reduce that noise before demo migration, not after launch.

### Prepare Catalog and Product Data <a href="#prepare-catalog-and-product-data" id="prepare-catalog-and-product-data"></a>

Catalog preparation is one of the most important parts of a Shift4Shop migration because product records often carry more than names, SKUs, prices, and descriptions. They may include options, variant-level adjustments, inventory rules, digital-product settings, images, videos, reviews, Q\&A records, related items, bundles, quantity discounts, category assignments, and fields created by integrations or custom workflows.

The preparation goal is not to make every source product look identical. It is to make each product usable in Shift4Shop after migration. A simple product may only need standard field cleanup. A configurable product may need option review. A wholesale product may need customer-group pricing validation. A product with large media requirements may need image and video checks. A product tied to abandoned apps may need a decision about whether the custom data is still useful.

| Catalog item                   | Preparation action                                                                                 | Risk if skipped                                                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Product identifiers            | Standardize SKUs, GTINs, manufacturer part numbers, slugs, and source IDs where available          | Duplicate or inconsistent identifiers can make mapping, search, inventory review, and support lookup harder.                                 |
| Product options                | Identify size, color, material, configuration, bundle, personalization, and add-on choices         | Options may migrate as visible choices but lose pricing, inventory, or fulfillment meaning if not reviewed.                                  |
| Advanced Options               | Mark option-level price, weight, inventory, image, or behavior differences                         | Shift4Shop can treat certain option combinations with distinct operational meaning, so flat variant assumptions may under-scope the catalog. |
| Option templates               | Group products that share reusable option structures                                               | Repeated options should be planned consistently instead of recreated as disconnected product-level rules.                                    |
| Categories and SmartCategories | Confirm manual category assignments and dynamic category expectations                              | Storefront discovery may change if dynamic or rule-based merchandising is not planned before migration.                                      |
| Inventory values               | Review stock counts, warehouse assumptions, backorder behavior, waiting lists, and low-stock rules | Migrated stock numbers can be misleading if operational inventory logic is not ready.                                                        |
| Product content                | Clean descriptions, tabs, specifications, images, videos, reviews, and Product Q\&A                | Rich product pages can lose selling value if content is technically present but poorly organized.                                            |

Catalog preparation should include sample products from each product pattern, not only the best-selling items. Include simple products, option-heavy products, products with Advanced Options, wholesale products, discounted products, products with long descriptions, products with many images, products with reviews, and products tied to integrations. Demo migration review becomes much more useful when the samples represent the real catalog complexity.

### Prepare Customer, Account, and Order Data <a href="#prepare-customer-account-and-order-data" id="prepare-customer-account-and-order-data"></a>

Customers and Orders should be prepared together because customer records often explain order history, pricing behavior, support context, and commercial relationships. A Shift4Shop migration that preserves accounts but ignores customer groups, wholesale status, tax treatment, and order-reference requirements can leave staff with records that exist but do not support daily work.

Customer preparation should start with segmentation. Confirm which groups remain active, which groups are obsolete, which groups affect pricing, which groups affect visibility, and which groups exist only because of old source-store workarounds. If a store serves both B2C and B2B buyers, customer preparation should also identify whether wholesale buyers, resellers, tax-exempt accounts, quote-based buyers, or special-price customers need separate validation.

| Data area           | Preparation focus                                                                                                       | Validation sample to collect                                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Customers           | Active accounts, inactive accounts, duplicate emails, customer groups, tax status, addresses, and marketing permissions | A retail customer, a wholesale customer, a tax-exempt customer, and a customer with multiple addresses.                |
| Customer groups     | Pricing rules, visibility rules, quantity-discount eligibility, and special access requirements                         | One account from each active group and one product affected by each group.                                             |
| Orders              | Order numbers, dates, statuses, products, totals, discounts, taxes, shipping, payments, refunds, and notes              | A normal paid order, a discounted order, a tax-exempt order, a multi-item order, and an older support-reference order. |
| B2B records         | Wholesale pricing, minimum order quantity logic, customer-specific price expectations, and reorder behavior             | A buyer who should see special pricing and a product affected by quantity breaks.                                      |
| Operational history | Support notes, staff comments, fulfillment references, and accounting lookup needs                                      | Orders commonly used for support, returns, warranty questions, or reconciliation.                                      |

Order history does not need to recreate every checkout behavior in the new store, but it should remain understandable. Staff should be able to identify what was purchased, who purchased it, when it was purchased, what pricing and discounts applied, which taxes and shipping charges were recorded, and whether the order has enough detail for support or accounting use.

### Prepare Content, URLs, and SEO Inputs <a href="#prepare-content-urls-and-seo-inputs" id="prepare-content-urls-and-seo-inputs"></a>

SEO preparation should not wait until after migration. Shift4Shop storefront structure, category paths, product URLs, Extra Pages, Blog Posts, reviews, Product Q\&A, and navigation decisions can all affect how search engines and customers reach important pages after launch.

Prepare SEO inputs by identifying which URLs deserve priority treatment. Not every old URL has equal business value. Product pages with search traffic, category pages used in paid campaigns, policy pages, evergreen content, product guides, blog posts, high-converting landing pages, and indexed support content should be separated from low-value or inactive pages.

| SEO or content input | What to prepare                                                                        | How to use it during migration                                                 |
| -------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Product URLs         | Current URLs, intended Shift4Shop slugs, priority products, and duplicate URL patterns | Build redirect rules and confirm product-page continuity for priority items.   |
| Category URLs        | Existing category paths, planned category structure, and high-traffic collections      | Avoid redirect gaps when category depth or naming changes.                     |
| Extra Pages          | About, policy, shipping, returns, buying guides, B2B information, and help content     | Decide which pages should migrate, be rewritten, consolidated, or retired.     |
| Blog Posts           | Posts with organic traffic, backlinks, campaign value, or support usefulness           | Preserve useful content instead of importing every old post without purpose.   |
| Metadata             | Page titles, meta descriptions, canonical preferences, and high-value keywords         | Keep SEO context connected to the pages that matter most.                      |
| Reviews and Q\&A     | Product review records and Product Q\&A content                                        | Preserve conversion and search-supporting user-generated content where useful. |

Content cleanup should focus on business value. Outdated policy pages, duplicate landing pages, old campaign pages, thin blog posts, and unused source-store CMS records can create unnecessary migration scope. A cleaner content set makes redirect planning, search review, and post-launch validation easier.

### Review Apps, Extensions, Integrations, or Custom Data <a href="#review-apps-extensions-integrations-or-custom-data" id="review-apps-extensions-integrations-or-custom-data"></a>

A Shift4Shop migration can be affected by systems outside the storefront. Payment gateways, shipping services, ERP or accounting tools, fulfillment connections, email marketing systems, product feeds, marketplaces, tax services, analytics tools, review platforms, and custom scripts may all create data or depend on data that appears inside the source store.

Preparation should identify which connected systems are still active, which records they created, and whether those records need to move, be rebuilt, or be retired. A field created by an old integration may look like useful product data, but it may no longer be connected to any active process. The opposite can also be true: a small custom field may control fulfillment, reporting, product feeds, or customer-specific handling.

| Integration or custom-data type | Preparation question                                                                     | Migration decision                                                                        |
| ------------------------------- | ---------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Product feeds and marketplaces  | Which fields feed external channels, ads, or comparison shopping engines?                | Preserve, remap, or rebuild fields that support active sales channels.                    |
| Shipping and fulfillment        | Which order, product, weight, option, warehouse, or carrier fields drive fulfillment?    | Confirm whether migrated values are enough or whether setup work is needed in Shift4Shop. |
| Accounting and ERP              | Which customer, order, tax, SKU, and payment references are used for reconciliation?     | Protect historical lookup and active synchronization requirements.                        |
| Marketing systems               | Which customer segments, coupon rules, product lists, or campaign URLs are still active? | Migrate useful records and exclude abandoned campaign artifacts.                          |
| Custom fields or scripts        | Which fields were created for operational logic rather than display?                     | Keep only fields with current business use and document how they should be validated.     |

For older 3dcart-origin stores, integration review should also check whether support links, developer references, API notes, or staff instructions still use 3dcart terminology. These references do not always indicate obsolete functionality, but they can mislead scoping if no one confirms whether the connected process is still active.

### Prepare Access, Backups, and Migration Inputs <a href="#prepare-access-backups-and-migration-inputs" id="prepare-access-backups-and-migration-inputs"></a>

Before demo migration, all access credentials and source materials should be ready. Missing access can delay data export review, prevent file review, block media transfer, or make it impossible to validate custom data. Preparation should include both platform access and operational access.

At minimum, prepare admin access, export permissions, file access, image/media access, database or export files where applicable, API credentials if needed, integration access, DNS and domain access for launch planning, and contact points for internal teams or vendors that own external systems.

| Input type         | What to prepare                                                                                       | Why it matters                                                                      |
| ------------------ | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Store admin access | Admin login with sufficient permissions to view and export store data                                 | Limited roles may hide product, customer, order, coupon, content, or settings data. |
| Export files       | Product, customer, order, category, coupon, review, content, and custom-field exports where available | Export files support source review and fallback analysis.                           |
| Media access       | Product images, videos, downloadable files, documents, and rich content assets                        | Product pages can look incomplete if media is not accessible or properly mapped.    |
| Integration access | Credentials or admin views for active connected systems                                               | External systems often explain fields that appear confusing in exports.             |
| Backup copies      | Source-store exports and file backups captured before migration work begins                           | Backups reduce risk when source data changes during the project.                    |
| Launch access      | Domain, DNS, payment, shipping, tax, and analytics access                                             | Migration readiness depends on launch systems, not only data transfer.              |

Access preparation should also include a freeze or change-control plan when appropriate. If products, prices, categories, or customer records keep changing during preparation, the team should know which changes will be included in demo migration, which will wait for full migration, and which must be reviewed again before launch.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

Demo migration is only useful when the review samples reflect the store’s real complexity. A random sample can miss the exact records that create launch risk. Prepare sample records intentionally before demo migration so the review can test the right areas.

The sample set should include records that represent normal operations, edge cases, and high-risk business rules. Choose products with options, products with Advanced Options, products in multiple categories, wholesale products, discounted products, gift certificate products, digital products if used, products with reviews or Product Q\&A, and products with rich media. Include customers from each active group and Orders that demonstrate taxes, discounts, shipping, payment history, refunds, and support notes.

| Sample group        | Include these examples                                                                                                                   | What the demo should prove                                                    |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Product samples     | Simple product, option-heavy product, Advanced Options product, product with media, product with reviews, product in multiple categories | Product data remains usable, searchable, purchasable, and properly organized. |
| Customer samples    | Retail customer, wholesale customer, tax-exempt customer, customer with multiple addresses, customer tied to special pricing             | Customer identity and commercial treatment are preserved where needed.        |
| Order samples       | Recent order, old support-reference order, discounted order, tax-exempt order, multi-item order, refunded or partially fulfilled order   | Historical order records remain understandable for staff.                     |
| SEO samples         | Priority product URL, category URL, Extra Page, Blog Post, redirected URL, page with metadata                                            | High-value pages can be traced from old structure to new structure.           |
| Integration samples | Product feed field, ERP-related SKU, fulfillment field, marketplace record, custom field                                                 | Integration-dependent data is not mistaken for optional decoration.           |

Demo review should produce decisions, not only observations. If a product option does not map cleanly, decide whether to remap, rebuild, or exclude it. If customer pricing is unclear, decide which group logic needs validation. If old content should not migrate, document the exclusion. These decisions reduce uncertainty before full migration.

### Final Preparation Check <a href="#final-preparation-check" id="final-preparation-check"></a>

The final preparation check should confirm that the Shift4Shop migration has enough source clarity, target-store planning, sample coverage, and access readiness to proceed. It should not be a formality. If major data areas remain unreviewed, full migration can transfer records that are technically present but operationally weak.

Use the final check to verify that key records have owners. Catalog decisions should have a product or merchandising owner. Customer and B2B decisions should have a sales or operations owner. Order-history decisions should have support, accounting, or fulfillment input where needed. SEO decisions should have marketing or technical review. Integration decisions should involve whoever owns the connected systems.

| Readiness checkpoint         | Pass condition                                                                           | Hold condition                                                                  |
| ---------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Target structure             | Categories, content, customer groups, and launch priorities are defined                  | The target store is still being treated as a simple copy of the source store.   |
| Catalog readiness            | Product options, Advanced Options, media, categories, and inventory samples are reviewed | Product behavior is assumed from exports without sample validation.             |
| Customer and order readiness | Customer groups, B2B accounts, tax treatment, and order-history needs are documented     | Customer records and Orders are treated as flat history without business rules. |
| SEO readiness                | Priority URLs, redirects, Extra Pages, Blog Posts, and metadata are prepared             | SEO work is postponed until after full migration.                               |
| Integration readiness        | Active integrations and custom fields are identified and assigned decisions              | Unknown fields are migrated without knowing whether they still matter.          |
| Demo readiness               | Review samples cover common records and edge cases                                       | Demo samples are random or too narrow to test real risk.                        |

A well-prepared Shift4Shop migration should enter demo migration with clear records, clear ownership, and clear review priorities. That preparation does not remove every migration issue, but it makes the issues visible early enough to correct them before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shift4Shop migration preparation should focus on readiness, not volume. Products, categories, customer groups, Orders, SEO inputs, integrations, and custom records all need enough review to determine how they should function in the new store.

The strongest preparation process defines the target store structure, cleans the catalog, documents customer and B2B rules, protects useful order history, prepares SEO and content inputs, reviews integrations, secures access, and builds meaningful demo samples. When these steps are complete, migration decisions become easier to validate and the full migration can proceed with fewer avoidable surprises.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to Shift4Shop?**

Start with the target store structure, catalog scope, customer groups, order-history requirements, SEO priorities, and active integrations. These areas influence how the migration should be scoped and reviewed.

**Why do product options need special preparation for Shift4Shop?**

Product options may affect price, inventory, weight, images, fulfillment, and customer choice. If they are prepared only as display labels, important product behavior may be lost or misrepresented.

**Should old 3dcart references be removed before migration?**

Not automatically. Old 3dcart references should be reviewed to determine whether they describe active processes, legacy documentation, abandoned integrations, or outdated staff terminology.

**How should demo migration samples be selected?**

Select samples that represent actual store complexity, including option-heavy Products, wholesale Customers, discounted Orders, SEO-priority pages, content records, and integration-dependent fields.

**What makes a Shift4Shop migration ready for full migration?**

The migration is ready when core data areas are reviewed, source issues are documented, target-store decisions are made, access is prepared, and demo migration findings have been resolved or assigned clear next actions.
