# Selecting the Right Migration Approach for Wix

Choosing the right Wix migration approach means deciding how much guidance, configuration review, data handling, and custom evaluation the migration requires. Wix is a hosted site-builder commerce Target Platform, so the right approach depends on more than record count. It depends on catalog complexity, product options and variants, content and SEO continuity, checkout expectations, app dependencies, Velo/API logic, service plugins, integrations, launch timing, and how much the merchant wants Next-Cart involvement during the process.

The approach should separate five things: what the Migration Service can move, what the merchant must configure in Wix, what Add-ons can extend, what requires Custom Service review, and what should be validated through Demo Migration before Full Migration.

### What Migration Approach Means for Wix <a href="#what-migration-approach-means-for-wix" id="what-migration-approach-means-for-wix"></a>

A Wix migration approach should define the operating model for the project. It should not be chosen only by store size. A smaller Wix migration with custom checkout logic can require more review than a larger standard catalog migration.

| Planning question                     | Why it matters for Wix                                                                                                    | Approach impact                                                                 |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Is the catalog standard or custom?    | Products, options, variants, modifiers, custom catalogs, and app-owned items may need different handling.                 | Determines whether Standard Service, Add-ons, or Custom Service is appropriate. |
| How important is content and SEO?     | CMS Pages, Blog Posts, media, product URLs, page URLs, redirects, and metadata affect launch quality.                     | May require Add-ons, Managed Service support, or additional validation.         |
| Is checkout standard?                 | Live checkout behavior depends on Wix settings, payment, shipping, tax, discount, fulfillment, apps, and service plugins. | May require target setup outside migration scope or Custom Service review.      |
| Are apps or integrations central?     | Wix apps, Velo/API logic, custom catalogs, and external systems may own records or workflows.                             | Often moves the project beyond basic migration.                                 |
| How much help does the merchant need? | Some merchants can run and validate migration themselves; others need operational guidance.                               | Helps choose Standard Service or Managed Service.                               |

### Standard Service for Wix <a href="#standard-service-for-wix" id="standard-service-for-wix"></a>

Standard Service is suitable when the merchant can manage the migration process and validation with limited guidance, and the store has a manageable Wix target scope.

| Standard Service fits when                    | Why it works                                                                                                                             | What still needs validation                                                                         |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Catalog is relatively standard                | Products, images, prices, SKUs, options, variants, collections, and inventory can be sampled clearly.                                    | Variant behavior, media, collection assignment, and SEO fields.                                     |
| Customer and order history is straightforward | Historical records can be reviewed without unusual account or integration meaning.                                                       | Customer/contact/member meaning, guest orders, totals, payment labels, tax, shipping, and statuses. |
| Site content scope is modest                  | Priority CMS Pages, Blog Posts, and media can be identified without heavy rebuild expectations.                                          | URLs, redirects, internal links, and target design handling.                                        |
| Merchant can configure Wix settings           | Payment, shipping, tax, discounts, checkout, fulfillment, domains, apps, and site design are not expected as automatic migration output. | Target readiness before launch.                                                                     |

Standard Service should not be selected simply because the store is small. It is best when the target scope is clear and the merchant can make informed validation decisions.

### Managed Service for Wix <a href="#managed-service-for-wix" id="managed-service-for-wix"></a>

Managed Service is appropriate when the merchant wants Next-Cart guidance and closer handling during the migration process. It is especially useful when the store has several moving parts but does not necessarily require fully custom migration work.

| Managed Service signal              | Why it matters                                                                                 | Example Wix use case                                                                          |
| ----------------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Merchant wants operational guidance | Wix migrations can involve commerce data, site content, SEO, apps, and launch timing.          | Coordinating Demo Migration review across catalog, orders, customers, content, and redirects. |
| Large or sensitive catalog          | Product options, variants, collections, media, and SEO need structured review.                 | Sampling best sellers, complex products, product pages, and collection paths.                 |
| Content and SEO are important       | Pages, Blog Posts, media, slugs, redirects, and domain timing affect post-launch continuity.   | Creating a validation checklist for search-sensitive URLs and priority landing pages.         |
| Multiple teams are involved         | Store owner, marketer, developer, agency, and operations team may own different Wix decisions. | Coordinating what is migration scope versus Wix setup.                                        |

Managed Service does not remove the need for target Wix configuration. It helps the merchant plan and validate the migration more carefully.

### Add-ons for Wix <a href="#add-ons-for-wix" id="add-ons-for-wix"></a>

Add-ons extend specific migration needs. They are useful when the merchant requires additional handling within a defined area, such as data mapping, filtering, configuration support, or supported data extensions.

| Add-on need              | Wix example                                                                                          | Boundary                                                                            |
| ------------------------ | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Data filtering           | Migrating only selected products, customers, orders, Blog Posts, or date ranges.                     | Filtering does not rebuild app behavior or site design.                             |
| Advanced mapping         | Handling category-to-collection planning, fields, product data, or customer/order attributes.        | Mapping does not guarantee unsupported source behavior becomes native Wix behavior. |
| Content or media support | Supporting CMS Pages, Blog Posts, images, files, metadata, or priority URL context where applicable. | Page design and layout rebuild may still be implementation scope.                   |
| Data configuration       | Improving how selected fields are interpreted during migration.                                      | It does not replace Custom Service when data is non-standard.                       |

Add-ons should be chosen for specific needs. They are not a substitute for Custom Service, custom development, target site design, app implementation, or integration rebuild work.

### Custom Service for Wix <a href="#custom-service-for-wix" id="custom-service-for-wix"></a>

Custom Service should be considered when the migration requires tailored analysis or handling beyond standard scope and specific Add-ons.

| Custom Service trigger              | Why it matters for Wix                                                                                   | Discovery focus                                                                                |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Custom catalog behavior             | Products may be controlled by external systems, custom catalog logic, or service plugins.                | Catalog ownership, identifiers, sync direction, product structure, and checkout impact.        |
| Complex options or modifiers        | Source choices may control SKU, stock, price, media, personalization, fulfillment, or app logic.         | Which choices can map to Wix and which require custom evaluation.                              |
| App-owned records                   | Bookings, events, memberships, pricing plans, forms, loyalty, or other apps may own business data.       | Exportability, target app setup, accepted exclusions, or custom handling.                      |
| Velo/API or service-plugin behavior | Cart, checkout validation, shipping, fees, payment, or integrations may depend on custom logic.          | Required behavior, technical feasibility, and responsibility boundaries.                       |
| External systems                    | ERP, CRM, PIM, WMS, accounting, shipping, payment, tax, and marketing systems may require ID continuity. | Field mapping, external references, order/customer/product identifiers, and reconnection plan. |

Custom Service does not automatically mean Next-Cart performs the entire target build or custom development. It means the requirement needs tailored review and agreed scope.

### Entity Points and Wix Scope Planning <a href="#entity-points-and-wix-scope-planning" id="entity-points-and-wix-scope-planning"></a>

Entity Points matter when eligible records are migrated. For Wix planning, Entity Points should be discussed when the source includes products, customers, orders, Blog Posts, or other supported record types that affect service scope.

New Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the merchant performs another migration action. New eligible records may consume Entity Points when migrated for the first time, even when the merchant performs a new migration for the same migration path.

| Scope question                                       | Why it matters                                                                    |
| ---------------------------------------------------- | --------------------------------------------------------------------------------- |
| Which records are included in the initial migration? | Defines the expected baseline for service license and Entity Points planning.     |
| Which new records may be added before launch?        | Helps plan follow-up migration needs and possible additional Entity Points usage. |
| Are Blog Posts or content records in scope?          | Content scope can affect both migration planning and SEO validation.              |
| Are app-owned records excluded or custom scoped?     | Prevents unsupported records from being counted as ordinary migration records.    |

### Demo Migration as the Approach Decision Point <a href="#demo-migration-as-the-approach-decision-point" id="demo-migration-as-the-approach-decision-point"></a>

Demo Migration should confirm whether the chosen approach is realistic. It should include easy and difficult samples.

| Demo sample                      | What to confirm                                                                                    | Approach signal                                                                                       |
| -------------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Simple and complex products      | Options, variants, prices, SKUs, inventory, images, collections, and SEO.                          | Standard if clean; Add-ons or Custom Service if meaning is lost.                                      |
| Orders                           | Line items, totals, discounts, tax, shipping, payment labels, statuses, notes, and customer links. | Managed Service if review needs coordination; Custom Service if order meaning depends on custom data. |
| Customers, contacts, and members | Account, contact, CRM, subscriber, and membership meaning.                                         | Additional review if customer identity is more than commerce history.                                 |
| Pages, Blog Posts, media, URLs   | Content display, media references, slugs, metadata, internal links, and redirects.                 | Add-ons or Managed Service if SEO continuity is important.                                            |
| Apps and integrations            | App-owned fields, external IDs, service-plugin behavior, and API dependencies.                     | Custom Service if business behavior depends on non-standard logic.                                    |

### How Additional Migration Options Affect Approach Planning <a href="#how-additional-migration-options-affect-approach-planning" id="how-additional-migration-options-affect-approach-planning"></a>

Additional Migration Options are relevant when migration activity continues after the initial migration. For Wix, follow-up handling should be planned carefully because new products, customers, orders, Blog Posts, media, URLs, app data, or integration fields can affect launch readiness.

| Follow-up situation                               | Wix planning implication                                                                       |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Source store keeps receiving orders before launch | New orders and customers may need validation before final cutover.                             |
| New products or content are added                 | Product, collection, media, page, Blog Post, SEO, and URL checks may need to be repeated.      |
| Apps or integrations change                       | Follow-up data may include fields or dependencies that were not present during Demo Migration. |
| URL or content structure changes                  | Redirect and internal-link planning may need updates.                                          |

Additional Migration Options should not be treated as a shortcut around validation. They should be planned as controlled follow-up activity.

### Wix Approach Decision Matrix <a href="#wix-approach-decision-matrix" id="wix-approach-decision-matrix"></a>

| Store condition                                                                                     | Recommended approach emphasis                        |
| --------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| Standard catalog, simple history, merchant can self-validate                                        | Standard Service with strong Demo Migration review   |
| Larger store, SEO-sensitive content, or many stakeholders                                           | Managed Service with structured validation           |
| Specific data mapping, filtering, or supported extension need                                       | Add-ons with clear boundaries                        |
| Custom catalog, app-owned records, checkout logic, Velo/API dependency, or external-system workflow | Custom Service review                                |
| Ongoing source activity before launch                                                               | Additional Migration Options with renewed validation |

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Wix migration approach depends on how closely the source store can be represented through Wix-supported commerce, content, app, and integration structures. Standard Service fits clear and manageable migrations. Managed Service fits merchants that need guidance and coordination. Add-ons address specific migration needs. Custom Service should be used when Wix success depends on non-standard data or behavior. Additional Migration Options should be planned when follow-up migration activity affects launch readiness.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for Wix migration?**

Standard Service can be enough when the catalog, customers, orders, content, and target setup are manageable and the merchant can validate results independently.

**When should a Wix migration use Managed Service?**

Managed Service is useful when the merchant wants guidance, has large or SEO-sensitive data, needs coordinated validation, or has several teams involved in launch decisions.

**When does Wix require Custom Service review?**

Custom Service should be reviewed when source behavior depends on custom catalogs, complex product choices, app-owned records, Velo/API logic, service plugins, or external systems.

**Do Add-ons replace Custom Service for Wix?**

No. Add-ons address specific migration needs. They are not a substitute for Custom Service, target site design, app implementation, custom development, or integration rebuild work.

**How should Additional Migration Options be planned for Wix?**

They should be planned as controlled follow-up migration activity with renewed validation for any new records, content, URLs, app data, or integration fields introduced after the initial migration.
