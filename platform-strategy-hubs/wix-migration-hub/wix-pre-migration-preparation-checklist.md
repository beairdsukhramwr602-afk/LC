# Wix Pre-Migration Preparation Checklist

Wix preparation should make the future Wix site-commerce environment testable before migration results are accepted. A merchant is not preparing only a product export or a customer list. The merchant is preparing a hosted Wix site, Wix Stores catalog, collections, product options, variants, inventory behavior, historical order context, customers, contacts, members, CMS Pages, Blog Posts, media, URL and SEO decisions, apps, checkout settings, payment and shipping configuration, and any custom logic that affects how the business sells.

The most important preparation principle is separation. Migrated records, Wix target setup, site-editor implementation, app configuration, and custom or external-system behavior should be identified before Demo Migration. Without that separation, a clean product transfer can be mistaken for launch readiness, or a site-design requirement can be incorrectly treated as ordinary data migration.

### Define the Wix Target Operating Scenario <a href="#define-the-wix-target-operating-scenario" id="define-the-wix-target-operating-scenario"></a>

Preparation should begin with the business outcome expected from Wix. A merchant moving into Wix may want a simpler hosted website, a content-led store, a redesigned product experience, a lightweight catalog, a site with booking or membership features, or a commerce site supported by CMS data and custom code. Each scenario changes what should be prepared and what Demo Migration should prove.

A Wix migration is strongest when the target operating scenario is concrete. The team should know whether Wix Stores is the main selling environment, whether the site will include CMS-driven content, whether Wix apps own important records, whether members or contacts matter, whether redirects and SEO continuity are launch-critical, and whether any source behavior must be rebuilt in Wix instead of migrated.

| Wix operating area               | Preparation question                                                                                             | Why it matters                                                                                    |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Wix Stores                       | Will products, collections, variants, inventory, orders, discounts, and checkout be central after launch?        | Store records should be tested against the actual Wix commerce setup.                             |
| Site-builder experience          | Which pages, menus, layouts, product galleries, mobile views, and landing paths must be recreated or redesigned? | Design and page structure are not the same as migrated commerce records.                          |
| Customers, contacts, and members | Which source identities are buyers, CRM contacts, site members, subscribers, or app participants?                | Identity data can lose meaning if every record is treated as a customer.                          |
| CMS and content                  | Which CMS Pages, Blog Posts, dynamic pages, data collections, media, and internal links matter?                  | Content-led stores need a content migration and rebuild plan, not only a catalog plan.            |
| Apps and custom logic            | Which workflows depend on Wix apps, source apps, Velo/API logic, external databases, or custom fields?           | These requirements may affect Add-ons, Custom Service, target-side setup, or accepted exclusions. |
| Launch setup                     | Which domains, redirects, payments, shipping, tax, fulfillment, and notifications must work at launch?           | Target setup should not be confused with transferred history.                                     |

The target operating scenario should be documented in plain business terms. It should answer how the merchant expects to sell, how shoppers will browse, how staff will review customers and orders, and which areas must be ready before launch.

### Prepare Product, Option, Variant, and Inventory Samples <a href="#prepare-product-option-variant-and-inventory-samples" id="prepare-product-option-variant-and-inventory-samples"></a>

Product preparation should use representative examples, not only total product counts. Wix catalog data can include products, collections, options, choices, variants, media, inventory, visibility, SKUs, pricing, ribbons, and other product-related details. The migration plan should test the product patterns that actually drive the business.

A sample set should include straightforward products and difficult products. A simple product may confirm the baseline path. A product with options and choices may reveal whether variants preserve price, SKU, weight, media, and inventory meaning. A product with add-ons, personalization, digital delivery, service-like behavior, or external-system identifiers may reveal whether the requirement belongs in supported migration scope, Add-ons, Custom Service, Wix app setup, or manual rebuild.

| Product sample                          | Evidence to prepare                                                                                                   | Wix planning value                                                                          |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Simple sellable product                 | Title, description, SKU, price, inventory, collection, image, visibility, and product URL.                            | Confirms ordinary catalog transfer and storefront readability.                              |
| Product with options and choices        | Size, color, material, package, price differences, SKU differences, weight differences, and unavailable combinations. | Tests whether source options become usable Wix product behavior.                            |
| Variant-specific inventory product      | Variant SKUs, stock values, inventory tracking, and image differences.                                                | Confirms inventory follows the right sellable version, not only the parent product.         |
| Product with personalization or add-ons | Engraving, gift wrap, file upload, customer notes, custom text, or configured extras.                                 | Identifies target setup, app dependency, Add-ons, Custom Service, or accepted limitation.   |
| Content-rich product                    | Long descriptions, specifications, size guides, embedded media, tabs, FAQs, reviews, and internal links.              | Reveals whether content should migrate, be rebuilt, or become CMS/site implementation work. |
| External-system product                 | ERP ID, PIM ID, supplier reference, marketplace ID, fulfillment rule, or sync status.                                 | Shows whether external references need mapping or custom handling.                          |

Inventory should be prepared at the level where selling decisions happen. If stock differs by variant, the sample should include variant-level quantities. If stock comes from an external inventory system, the plan should define whether Wix receives a snapshot, whether the integration remains the source of truth, or whether inventory should be configured after migration.

The practical goal is to make products sellable and understandable in Wix. It is not to force every source-platform product behavior into the Wix catalog if the better path is app setup, CMS content, target-side configuration, or Custom Service review.

### Prepare Collections, Site Navigation, and Discovery Evidence <a href="#prepare-collections-site-navigation-and-discovery-evidence" id="prepare-collections-site-navigation-and-discovery-evidence"></a>

Wix collections and site navigation require careful preparation because source categories rarely mean only one thing. A source category may be a product grouping, storefront menu, landing page, filter rule, merchandising campaign, SEO path, or customer browsing habit. In Wix, those meanings may become collections, product galleries, pages, menus, dynamic pages, filters, redirects, or accepted structural changes.

Preparation should separate catalog grouping from customer-facing discovery. A product may belong to a collection, but that does not automatically prove the storefront menu, landing page, or high-value SEO path is ready. The merchant should prepare the structures shoppers actually use to find products.

| Discovery input          | What to prepare                                                                       | Wix readiness question                                                                  |
| ------------------------ | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Source categories        | Category names, hierarchy, product assignments, URLs, and business priority.          | Should the structure become a Wix collection, page, menu, redirect, or simplified path? |
| Menus and internal links | Header links, footer links, product-gallery links, campaign links, and content links. | Will shoppers still reach important products and pages?                                 |
| Filters and attributes   | Size, color, brand, material, price, availability, custom fields, and product labels. | Which filters can be represented through Wix setup and which require another path?      |
| Featured product groups  | Seasonal collections, sale groups, homepage sections, and promotional landing pages.  | Does merchandising need a collection, page, app, or manual site rebuild?                |
| Priority browsing paths  | Top categories, high-traffic pages, paid-search destinations, and backlink targets.   | Which paths need redirects, metadata review, or manual launch verification?             |

This preparation is especially important for stores moving from more catalog-centric platforms into Wix. Wix can support strong product discovery, but the final site experience depends on a combination of data, site layout, menu design, SEO planning, and target-side review.

### Prepare Customers, Contacts, Members, and Marketing Context <a href="#prepare-customers-contacts-members-and-marketing-context" id="prepare-customers-contacts-members-and-marketing-context"></a>

Wix identity preparation should not collapse every source record into one generic customer concept. Source platforms may store buyers, registered users, guest buyers, newsletter subscribers, CRM contacts, site members, loyalty participants, booking customers, membership participants, wholesale-like buyers, and app-specific identities. Wix can involve customers, contacts, site members, subscribers, CRM-style records, app participants, and external-system references.

The merchant should define what each identity type must do after migration. A buyer with order history should support customer service. A site member may need access review. A marketing contact may need consent, segmentation, and subscription review. A pricing-plan or booking participant may belong to a Wix app workflow. A loyalty or external CRM identity may need Custom Service review or separate integration planning.

| Identity sample          | Evidence to prepare                                                                | Planning value                                                   |
| ------------------------ | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Buyer with order history | Name, email, phone, billing/shipping addresses, orders, notes, and tags.           | Confirms commerce lookup and service continuity.                 |
| Guest buyer              | Order connection, contact details, and repeat-purchase evidence.                   | Prevents guest history from being lost or misread.               |
| Site member              | Login expectation, member status, access needs, and profile fields.                | Separates account access from ordinary customer migration.       |
| Marketing contact        | Consent, subscription status, tags, segments, and CRM fields.                      | Keeps marketing usability separate from basic customer transfer. |
| App participant          | Booking, event, pricing plan, restaurant, form, donation, or loyalty relationship. | Identifies app-owned data and target setup needs.                |
| External-system identity | CRM ID, loyalty ID, ERP account code, support ID, or marketplace buyer ID.         | Shows whether mapping or Custom Service review is needed.        |

Duplicate and incomplete identity records should be prepared before migration review. A Wix customer list can look populated while still failing practical support tasks if duplicate emails, missing phone numbers, inconsistent addresses, or disconnected orders make buyer history hard to interpret.

### Prepare Historical Orders, Payments, Fulfillment, and Checkout Context <a href="#prepare-historical-orders-payments-fulfillment-and-checkout-context" id="prepare-historical-orders-payments-fulfillment-and-checkout-context"></a>

Order preparation should distinguish historical order readability from live Wix checkout readiness. Migrated historical orders can help support teams answer past-order questions, but they do not configure live payment providers, tax rules, shipping methods, pickup and delivery settings, fulfillment notifications, inventory updates, or checkout behavior.

A good order sample set should include normal and exception cases. Wix preparation should include paid orders, refunded orders, canceled orders, partially fulfilled orders, orders with discounts, orders with shipping or pickup context, orders with taxes, orders with customer notes, and orders with external identifiers that staff still use.

| Order sample               | Evidence to prepare                                                                                             | What it should prove later                                                              |
| -------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Paid and fulfilled order   | Line items, totals, taxes, discounts, payment label, fulfillment status, shipping method, and customer details. | Ordinary historical order context remains readable.                                     |
| Refunded or canceled order | Refund amount, status, reason, payment label, notes, and communication context.                                 | Exception history remains understandable.                                               |
| Discounted order           | Coupon code, promotion label, line-item adjustments, and order totals.                                          | Discount history can be interpreted without assuming future discount setup is complete. |
| Shipping or pickup order   | Delivery method, address, tracking, pickup location, fulfillment status, and customer communication.            | Fulfillment context remains meaningful.                                                 |
| External-system order      | Marketplace ID, ERP ID, accounting ID, support reference, or subscription reference.                            | External references are mapped, scoped, excluded, or custom-reviewed intentionally.     |

Live checkout setup should have its own preparation track. The merchant should prepare payment-provider decisions, tax settings, shipping zones, delivery and pickup rules, discounts, abandoned-checkout expectations, notification settings, order settings, and test-order responsibilities. Those items belong to Wix target setup and validation, even when historical order data migrates successfully.

### Prepare CMS Pages, Blog Posts, Media, URLs, and SEO Inputs <a href="#prepare-cms-pages-blog-posts-media-urls-and-seo-inputs" id="prepare-cms-pages-blog-posts-media-urls-and-seo-inputs"></a>

Wix migration can be content-sensitive because the website experience often matters as much as the catalog. Preparation should include CMS Pages, Blog Posts, product pages, collection pages, landing pages, dynamic pages, media, internal links, metadata, redirects, domain plans, multilingual URLs, and high-value search paths where they affect launch value.

Content should be classified by future role. Some content should migrate as supported page or blog content. Some should be rebuilt in Wix because layout, editor sections, forms, galleries, or dynamic behavior cannot be treated as ordinary data. Some should redirect to a stronger target destination. Some should be retired.

| Input group              | What to prepare                                                                                  | Wix planning value                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| Product URLs             | Source URL, target product destination, slug expectations, traffic value, and redirect priority. | Protects product discovery and paid/organic landing paths.        |
| Collection/category URLs | Source path, collection equivalent, landing-page role, and SEO value.                            | Separates catalog grouping from customer-facing page intent.      |
| CMS Pages                | Policy pages, service pages, landing pages, guides, trust pages, and internal links.             | Identifies what migrates, rebuilds, redirects, or retires.        |
| Blog Posts               | Post URLs, authors, dates, categories, tags, media, internal links, and traffic value.           | Protects content-led acquisition where Blog Posts are in scope.   |
| Media assets             | Product images, galleries, downloads, videos, alt text, and file relationships.                  | Prevents content and product presentation gaps.                   |
| Domain and URL plan      | Primary domain, secondary URLs, old paths, multilingual paths, redirects, and launch timing.     | Keeps site launch and SEO continuity from being handled too late. |

SEO preparation should prioritize business value. Not every old URL deserves the same effort. Best-selling products, high-converting categories, ranked content pages, paid-campaign landing pages, backlinks, and support pages deserve stronger mapping than obsolete low-value paths.

### Prepare Apps, Velo/API Logic, External Systems, and Custom Data <a href="#prepare-apps-velo-api-logic-external-systems-and-custom-data" id="prepare-apps-velo-api-logic-external-systems-and-custom-data"></a>

Wix preparation should identify which business behavior belongs to Wix apps, custom code, external systems, or source-platform custom structures. A migration can handle supported records, but app-owned or custom behavior may need Add-ons, Custom Service, target-side setup, or exclusion.

The dependency inventory should include both source-side and target-side systems. Source platforms may use plugins, modules, apps, custom fields, scripts, tables, or private integrations. The target Wix site may use Wix apps, Velo code, APIs, CMS collections, external databases, service plugins, custom forms, or third-party systems.

| Dependency type                          | Preparation question                                                                        | Likely handling path                                                       |
| ---------------------------------------- | ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Supported data requiring filtering       | Which records should be included, excluded, or narrowed by date, status, category, or type? | Data Filter Add-on when the requirement remains within supported behavior. |
| Supported fields requiring mapping       | Which source fields should map to supported Wix destinations?                               | Advanced Data Mapping when the destination is supported.                   |
| Supported output requiring configuration | Which supported data needs adjusted handling for better Wix usability?                      | Advanced Data Configure when the configuration is bounded and supported.   |
| App-owned or custom records              | Which records come from apps, plugins, modules, custom tables, or non-standard structures?  | Custom Service review.                                                     |
| Velo/API/external-system logic           | Which custom behavior must remain connected to Wix or another system?                       | Custom Service review, target-side implementation, or accepted exclusion.  |
| Design, checkout, or app setup           | Which behavior must be configured directly in Wix?                                          | Target setup and validation, not ordinary migrated data.                   |

This classification should happen before service-path decisions are finalized. It protects the merchant from assuming that every hidden field, script-driven workflow, membership rule, subscription relationship, or app record belongs in normal migration scope.

### Prepare Demo Migration Samples and Review Ownership <a href="#prepare-demo-migration-samples-and-review-ownership" id="prepare-demo-migration-samples-and-review-ownership"></a>

Demo Migration should be planned as a focused evidence test. The sample set should be small enough to review carefully and broad enough to expose Wix-specific data meaning, site-commerce behavior, and service-path risk.

A useful Wix Demo Migration sample set should include:

* a simple product;
* a product with options and variants;
* a product with variant-specific inventory;
* a collection or category with SEO value;
* a customer with multiple orders;
* a guest buyer;
* a refunded or discounted order;
* a CMS Page or Blog Post with internal links;
* a high-value product or collection URL;
* a record that depends on an app, custom field, Velo/API logic, or external ID.

Review ownership should also be clear. The merchant should know who checks catalog results, who checks content and URLs, who checks orders and customers, who checks live checkout setup, who evaluates app/custom data, and who approves whether the migration approach is sufficient before Full Migration.

### Plan Launch Window and Additional Migration Options <a href="#plan-launch-window-and-additional-migration-options" id="plan-launch-window-and-additional-migration-options"></a>

If the source store remains open while Wix preparation continues, the merchant should plan what happens to records created after the first migration run. This is where Additional Migration Options may matter, but only as launch-window planning rather than a separate article topic.

The merchant may need to continue the migration with the last used configuration, continue the migration with a new configuration, or perform a new migration when the target result should be replaced. The decision should be tied to what changed: new products, new customers, new orders, updated content, changed mapping, revised filters, or a target site that needs to be rebuilt from a refreshed scope.

Entity Points should be understood accurately. New eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

The launch-window plan should also define revalidation. If new records are added, sample those new records. If configuration changes, review affected fields and outputs. If a new migration replaces previous target data, validate that the Wix site reflects the intended refreshed result before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Wix preparation is strongest when it treats migration as a site-commerce readiness project. The merchant should prepare product and variant samples, inventory evidence, collections and navigation inputs, customers, contacts, members, historical orders, CMS Pages, Blog Posts, URLs, media, apps, custom data, external-system references, Demo Migration samples, and launch-window decisions before Full Migration.

The goal is not to gather everything blindly. The goal is to separate what should migrate, what must be configured in Wix, what needs Add-ons, what requires Custom Service review, what should be rebuilt manually, and what can be excluded. That separation makes Demo Migration easier to evaluate and protects the Wix launch from avoidable scope confusion.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Wix migration?**

Start with the Wix target operating scenario. Confirm whether the future site depends mainly on Wix Stores, content pages, CMS data, site members, apps, custom code, or external systems. That decision shapes which records, samples, settings, and launch tasks should be prepared.

**Why are product samples more useful than product counts?**

Product counts show volume, but samples show migration meaning. Wix preparation should test products with options, choices, variants, inventory, collections, images, content, SEO value, and custom behavior because those patterns reveal whether the migration approach is sufficient.

**Should Wix checkout setup be included in data preparation?**

Checkout setup should be prepared as a target-side responsibility, not treated as migrated history. Historical orders may migrate for reference, while live payment providers, tax, shipping, pickup, delivery, discounts, order settings, and notifications need Wix setup and testing.

**When should Wix app or Velo-related data be reviewed?**

Review app, Velo, API, CMS, external database, and custom-field dependencies before Demo Migration. These dependencies can affect whether supported migration, Add-ons, Custom Service, target-side setup, or exclusion is the right path.

**How should Additional Migration Options be planned for Wix?**

Use them as launch-window planning when the source store keeps changing, mapping decisions change, or the target Wix result needs to be replaced. The team should know whether the next action continues the previous setup, uses a new configuration, or performs a new migration, and then revalidate the affected Wix records.
