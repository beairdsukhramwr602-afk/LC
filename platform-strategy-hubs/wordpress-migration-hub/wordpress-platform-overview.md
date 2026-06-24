# WordPress Platform Overview

WordPress is a CMS-connected Target Platform and implementation foundation. It can support publishing sites, content hubs, landing-page systems, membership portals, learning websites, directories, service websites, and commerce-connected implementations, but WordPress itself should not be treated as a native e-commerce platform by default.

A migration to WordPress is strongest when the project separates content structure from business functionality. Posts, CMS Pages, Blog Posts, media, categories, tags, authors, menus, comments, users, roles, and templates form the visible CMS layer. Custom post types, custom taxonomies, custom fields, plugin records, theme settings, builder layouts, SEO metadata, redirects, custom tables, and connected systems often determine whether the migrated site is actually usable after launch.

The main planning question is not only whether content can be transferred into WordPress. It is whether the current site meaning can be represented inside the target WordPress architecture without losing layout context, URL continuity, plugin-controlled behavior, user meaning, or custom application logic.

### What WordPress Means as a Target Platform <a href="#what-wordpress-means-as-a-target-platform" id="what-wordpress-means-as-a-target-platform"></a>

WordPress should be understood as a flexible content and application foundation. Its core model supports posts, pages, media, users, comments, categories, tags, taxonomies, themes, templates, menus, widgets, and API-accessible site resources. Many real WordPress sites extend that foundation through plugins, themes, page builders, custom post types, custom fields, shortcodes, custom tables, and external integrations.

| WordPress layer         | Migration meaning                                                                                              | Planning question                                                                                                                             |
| ----------------------- | -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Core CMS records        | Posts, CMS Pages, Blog Posts, media, categories, tags, comments, users, and menus.                             | Can the source content be represented as native WordPress records without losing authorship, media relationships, formatting, or URL meaning? |
| Structure layer         | Custom post types, custom taxonomies, archive pages, permalink rules, templates, and relationships.            | Does the target site need a documented content model beyond ordinary posts and pages?                                                         |
| Metadata layer          | Custom fields, SEO fields, page-builder metadata, plugin settings, and record-level options.                   | Which metadata controls display, filtering, search, SEO, or business behavior?                                                                |
| Presentation layer      | Blocks, reusable blocks, page builders, themes, templates, menus, widgets, and media output.                   | Which pages need visual review because content storage alone will not prove layout quality?                                                   |
| Plugin and custom layer | Forms, memberships, courses, bookings, events, directories, commerce plugins, custom tables, and integrations. | Which records belong to WordPress core and which require Add-ons, configuration, exclusion, or Custom Service review?                         |
| Operational layer       | Hosting, PHP, database, caching, search, security, redirects, deployment, and connected systems.               | Is the target environment prepared to make migrated content behave correctly after Full Migration?                                            |

This distinction matters because two WordPress migrations can look similar from the front end while requiring very different migration plans. A basic publishing site may be mostly posts, CMS Pages, Blog Posts, media, and menus. A custom WordPress application may depend on field groups, relationships, custom tables, external IDs, API synchronization, role permissions, or plugin-specific workflows.

### WordPress Is Different From WooCommerce <a href="#wordpress-is-different-from-woocommerce" id="wordpress-is-different-from-woocommerce"></a>

WordPress and WooCommerce should be planned separately. WordPress provides the CMS foundation, theme layer, user system, plugin framework, media library, and extensibility model. WooCommerce is a commerce plugin that can run on WordPress, but product, cart, checkout, order, tax, coupon, subscription, and customer-commerce behavior should not be assumed in a WordPress migration unless WooCommerce is part of the target scope.

| Target expectation                                   | Correct interpretation                                                           | Migration implication                                                                                                      |
| ---------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| A content website moving into WordPress              | WordPress is the Target Platform.                                                | Focus on posts, CMS Pages, Blog Posts, media, users, menus, taxonomy, SEO, and layout dependencies.                        |
| A WooCommerce store moving into WordPress            | WordPress is the foundation and WooCommerce is the commerce layer.               | Commerce records need WooCommerce-specific review rather than generic WordPress treatment.                                 |
| A membership, booking, LMS, event, or directory site | WordPress is the foundation and plugin/custom structures carry business meaning. | Plugin-owned records and custom fields may require separate mapping, configuration, Add-ons, or Custom Service review.     |
| A custom WordPress application                       | WordPress acts as an application framework.                                      | Custom post types, custom taxonomies, custom tables, external IDs, integrations, and permission logic need deeper scoping. |

This separation prevents two common planning errors: treating WordPress as if it natively owns commerce behavior, and treating plugin-controlled business records as if they were ordinary pages.

### Where WordPress Migration Value Comes From <a href="#where-wordpress-migration-value-comes-from" id="where-wordpress-migration-value-comes-from"></a>

WordPress is valuable as a migration target when the site depends on long-term content ownership, flexible structure, editorial control, SEO management, plugin extensibility, and implementation freedom. It is not limited to simple pages and posts, but the more customized the target model becomes, the more explicit the migration plan must be.

| Value area               | Why it matters in WordPress                                                                                                          | What must be preserved or rebuilt                                                                                                   |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| Content ownership        | WordPress is widely used for publishing, editorial, marketing, resource, and service-content sites.                                  | Titles, body content, excerpts, authors, statuses, dates, featured images, categories, tags, comments, and internal links.          |
| Flexible structure       | Custom post types and taxonomies can represent resources, events, profiles, courses, directories, portfolios, or listings.           | Content-type definitions, taxonomy hierarchy, relationships, custom fields, archive behavior, and templates.                        |
| Media and layout context | Images, documents, galleries, embeds, featured images, captions, alt text, and layout blocks affect usability.                       | Media files, attachment relationships, display sizes, alt text, captions, galleries, embedded media, and important visual sections. |
| SEO control              | WordPress sites often depend on slugs, permalink structures, metadata, canonical behavior, redirects, and taxonomy archives.         | URL mapping, high-value slugs, redirects, SEO fields, metadata, internal links, schema output, and archive pages.                   |
| Plugin extensibility     | Plugins can support memberships, forms, bookings, courses, events, SEO, multilingual content, search, security, and commerce layers. | Plugin-owned records, custom tables, settings, shortcodes, field groups, user relationships, and external-system references.        |
| Implementation control   | Self-hosted WordPress allows control over hosting, theme, plugins, custom code, caching, deployment, and integrations.               | Target environment readiness, plugin compatibility, theme behavior, PHP/database requirements, and deployment responsibilities.     |

A strong WordPress migration does not only ask whether the data can be imported. It checks whether the target WordPress site can operate with the intended content model, design system, plugins, redirects, and user/account logic.

### What Changes When Moving Into WordPress <a href="#what-changes-when-moving-into-wordpress" id="what-changes-when-moving-into-wordpress"></a>

A migration to WordPress changes how site information is organized. Source pages may become WordPress CMS Pages, Blog Posts, custom post types, taxonomy archives, plugin records, media attachments, or a mix of these elements. The right choice depends on how the target site should be managed after launch.

| Source-site element             | WordPress interpretation                                                                                | Planning impact                                                                                                   |
| ------------------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Standard pages                  | CMS Pages with editor content, template assignment, parent hierarchy, media, and menu relationships.    | Important pages need both record-level and visual review.                                                         |
| Blog or article content         | Blog Posts with authors, dates, categories, tags, featured images, comments, excerpts, and slugs.       | Blog Posts should preserve publishing context, not only title and body.                                           |
| Product-like or listing content | Could become custom post types, plugin records, WooCommerce products, or Custom Platform records.       | The target model must be decided before migration, not inferred from front-end appearance.                        |
| Categories and filters          | Native categories/tags, custom taxonomies, plugin filters, or search/index fields.                      | Filtering and archive behavior should be validated separately from content existence.                             |
| Media assets                    | Media library records and attachment references.                                                        | Images and files must remain connected to posts, pages, galleries, fields, and SEO text.                          |
| Users and accounts              | Users with roles, capabilities, authorship, membership/account meaning, or plugin-specific permissions. | Authors, customers, members, subscribers, instructors, vendors, or administrators may require different handling. |
| Forms and submissions           | Plugin-owned records, custom tables, email workflows, CRM records, or external-system data.             | Form history and workflow behavior may not be native WordPress content.                                           |
| SEO data                        | Slugs, metadata, redirects, canonical values, schema settings, breadcrumbs, and plugin fields.          | SEO preservation requires explicit evidence and redirect planning.                                                |

The most important early decision is whether WordPress will receive content as ordinary CMS records or as a structured implementation with custom content types, plugins, and custom fields.

### WordPress Architecture Layers to Confirm Early <a href="#wordpress-architecture-layers-to-confirm-early" id="wordpress-architecture-layers-to-confirm-early"></a>

WordPress migration planning should start by separating content, structure, presentation, plugin behavior, and operational ownership. These layers often appear together on the front end, but they require different migration decisions.

| Architecture layer       | What belongs there                                                                                                   | Why it matters before migration                                                                                          |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Content layer            | CMS Pages, Blog Posts, media, comments, authors, categories, tags, and menus.                                        | Establishes the ordinary WordPress baseline that can usually be inspected through the admin and REST-accessible records. |
| Structured-content layer | Custom post types, custom taxonomies, field groups, relationships, archive pages, and templates.                     | Determines whether source content stays editable and searchable instead of becoming flat page text.                      |
| Presentation layer       | Blocks, reusable blocks, page-builder data, shortcodes, templates, widgets, menus, theme settings, and media output. | Explains why migrated records can exist while the visible page still needs implementation or visual QA.                  |
| Plugin and custom layer  | Forms, memberships, LMS, events, bookings, directories, donations, custom tables, and integration records.           | Identifies data that may require Add-ons, configuration, accepted exclusions, or Custom Service review.                  |
| SEO and routing layer    | Slugs, permalinks, canonical settings, redirects, metadata, internal links, sitemap paths, and archive URLs.         | Protects search visibility and prevents content that migrated correctly from becoming hard to find.                      |
| Operations layer         | Hosting, PHP/database compatibility, caching, security, search, backups, deployment, and connected systems.          | Confirms that the target WordPress environment can support the migrated content after Full Migration.                    |

This layered view keeps the platform overview practical without turning it into a fit assessment. It helps merchants understand what WordPress can receive, what the target implementation must already support, and where migration scope may extend beyond standard CMS records.

### WordPress Planning Boundaries <a href="#wordpress-planning-boundaries" id="wordpress-planning-boundaries"></a>

WordPress is flexible, but that flexibility can hide scope. A migration plan should define which parts of the source site will become native WordPress content, which parts will depend on plugins or custom structures, and which parts belong outside WordPress or outside the migration scope.

| Boundary                                   | Correct planning interpretation                                                                   | Typical evidence to collect                                                                                                   |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| WordPress core vs plugin records           | Core records and plugin records should not be treated as the same data type.                      | Post/page samples, plugin list, custom tables, shortcode examples, field groups, and admin screenshots.                       |
| CMS content vs commerce behavior           | WooCommerce or another commerce layer should be scoped separately from WordPress CMS content.     | Product/order/customer examples, checkout requirements, subscription/payment/shipping/tax dependencies, and plugin ownership. |
| Content migration vs design reconstruction | Migrating content does not automatically reproduce a theme, builder, animation, or layout system. | Target theme/builder decision, priority page samples, reusable sections, widgets, templates, and visual acceptance examples.  |
| Standard fields vs custom behavior         | A custom field may store text, but the target site must still know how to display or use it.      | Field names, field types, display examples, filters, templates, API use, and external-system references.                      |
| URL movement vs SEO preservation           | Preserving visible content is different from preserving high-value URLs and metadata.             | URL map, redirects, canonical rules, SEO plugin fields, slugs, internal links, and priority pages.                            |

A clear boundary does not reduce WordPress flexibility. It makes that flexibility usable because the migration can be planned around the right target structures rather than around generic page transfer assumptions.

### What WordPress Requires From the Target Implementation <a href="#what-wordpress-requires-from-the-target-implementation" id="what-wordpress-requires-from-the-target-implementation"></a>

WordPress migration quality depends on the target environment as much as the source data. The target site needs the right post types, taxonomies, plugins, fields, templates, menus, redirects, and operating rules before Full Migration can be evaluated with confidence.

| Target requirement               | Why it matters                                                                                         | Migration impact                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Defined content model            | WordPress can store many content types, but it needs a planned model for each one.                     | Reduces the risk that resources, events, courses, listings, or directories are flattened into pages.      |
| Confirmed plugin stack           | Plugins may own forms, memberships, LMS records, SEO fields, redirects, builders, and commerce layers. | Determines what can be migrated directly, what needs Add-ons, and what may require Custom Service review. |
| Stable URL and redirect approach | Slugs, permalink structure, and redirects affect search visibility and user access.                    | Enables targeted validation of high-value pages, archives, media, and internal links.                     |
| Layout acceptance criteria       | Page builders and themes can change how migrated content appears.                                      | Separates data completion from visual acceptance and implementation work.                                 |
| Operational ownership            | WordPress requires hosting, updates, backups, security, caching, and plugin maintenance.               | Clarifies responsibilities after migration and prevents unsupported launch assumptions.                   |

These requirements make Article 1 a platform overview: they explain how WordPress behaves as a migration target and what must be understood before deeper fit, data-model, risk, preparation, approach, validation, and pitfall articles.

### What Should Be Understood Before Moving Into WordPress <a href="#what-should-be-understood-before-moving-into-wordpress" id="what-should-be-understood-before-moving-into-wordpress"></a>

Before choosing WordPress as the Target Platform, merchants should understand which parts of the current site are content, which parts are structure, and which parts are behavior. That separation is the difference between a clean WordPress migration and a site that technically contains records but does not operate as expected.

| Planning checkpoint          | Why it matters                                                                                                     | Evidence to prepare                                                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Core content inventory       | Establishes the baseline migration scope.                                                                          | Posts, CMS Pages, Blog Posts, categories, tags, media, comments, authors, menus, and key URLs.                              |
| Custom structure inventory   | Prevents custom content from being flattened into ordinary pages.                                                  | Custom post types, custom taxonomies, field groups, relationships, templates, archive pages, and sample records.            |
| Plugin dependency review     | Identifies records that are not native WordPress content.                                                          | Plugin list, plugin versions, data tables, shortcodes, settings, workflow examples, and exported samples where available.   |
| Layout and theme review      | Clarifies what data migration can and cannot reproduce.                                                            | Page-builder usage, block patterns, templates, widgets, theme settings, menus, and visual acceptance samples.               |
| User and role review         | Prevents authors, members, customers, subscribers, and administrators from being treated as the same account type. | User roles, capabilities, membership/account rules, author relationships, customer references, and permission samples.      |
| SEO and redirect review      | Protects traffic, search visibility, and internal linking.                                                         | URL list, slugs, metadata, redirects, canonical rules, sitemap evidence, internal-link samples, and media URL requirements. |
| Custom Service signal review | Finds scope that cannot be represented by standard WordPress records alone.                                        | Custom tables, bespoke plugin data, external IDs, APIs, CRM/ERP/PIM references, and workflow dependencies.                  |

A Demo Migration should include simple content and complex examples. Samples should cover media-heavy pages, Blog Posts with authors and categories, custom fields, custom post types, plugin-dependent records, menus, redirects, SEO-sensitive URLs, and user-role examples.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress can be a strong Target Platform when the migration goal is flexible content ownership, CMS control, plugin extensibility, SEO management, and custom site structure. It should be evaluated as a CMS-connected implementation foundation rather than as a fixed commerce platform.

Migration planning should separate ordinary WordPress content from plugin-owned records, custom post types, custom fields, custom tables, page-builder layouts, themes, redirects, SEO fields, users, roles, and external-system logic. When that structure is clear before Demo Migration, WordPress can support a well-controlled migration path. When that structure is unclear, Add-ons, configuration work, accepted exclusions, or Custom Service review may be needed before Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is WordPress a native e-commerce platform?**

No. WordPress is a CMS and application foundation. E-commerce behavior usually depends on WooCommerce, another commerce plugin, custom development, or connected systems.

**Is WordPress the same as WooCommerce?**

No. WordPress provides the CMS foundation, while WooCommerce is a commerce plugin that runs on WordPress. A WordPress migration should not automatically be treated as a WooCommerce migration unless WooCommerce is part of the target scope.

**What WordPress data should be reviewed before migration?**

Review posts, CMS Pages, Blog Posts, media, comments, users, roles, menus, categories, tags, custom post types, custom taxonomies, custom fields, plugin data, SEO metadata, redirects, and important page layouts.

**Why do plugins matter so much in a WordPress migration?**

Plugins can store business-critical data outside ordinary WordPress posts and pages. Memberships, bookings, courses, forms, events, commerce records, SEO fields, page-builder layouts, and custom workflows may require separate review.

**What should be included in a WordPress Demo Migration?**

A strong Demo Migration should include ordinary posts and pages, complex Blog Posts, media-heavy content, users with different roles, custom fields, plugin-dependent records, important menu or layout examples, and URLs with SEO value.
