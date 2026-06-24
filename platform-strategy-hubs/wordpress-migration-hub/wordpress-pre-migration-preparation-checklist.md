# WordPress Pre-Migration Preparation Checklist

WordPress migration preparation should define what the target site must preserve before data is moved. WordPress can receive standard CMS records, but many real WordPress projects depend on custom post types, plugin records, metadata, page-builder layouts, user roles, media relationships, SEO fields, redirects, forms, memberships, LMS records, booking records, directory listings, or external-system references. Preparation should therefore separate ordinary WordPress content from plugin-owned, implementation-owned, and externally owned records.

The preparation goal is not to list every possible WordPress file or plugin. It is to make the migration scope clear enough that Demo Migration can test the right samples, Full Migration can preserve meaningful records, and unsupported or custom behavior can be handled through Add-ons, accepted exclusions, or Custom Service review before launch pressure begins.

### Why WordPress Preparation Needs More Than a Content Inventory <a href="#why-wordpress-preparation-needs-more-than-a-content-inventory" id="why-wordpress-preparation-needs-more-than-a-content-inventory"></a>

WordPress is flexible because it can represent content through posts, CMS Pages, Blog Posts, custom post types, custom taxonomies, media, user records, metadata, templates, blocks, plugins, and custom tables. That flexibility creates preparation risk: two source sites can both “move to WordPress” while requiring very different migration logic.

| Preparation layer    | What to clarify before migration                                                                                         | Why it matters                                                                                                |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Platform role        | Whether WordPress is the final CMS, a companion CMS, a content layer for a storefront, or a Custom Platform destination. | Prevents generic WordPress assumptions from hiding commerce, membership, LMS, directory, or application data. |
| Content model        | Which records should become CMS Pages, Blog Posts, custom post type entries, taxonomy terms, media, or plugin records.   | Protects editability, archive behavior, filtering, and future content management.                             |
| Plugin ownership     | Which records are controlled by plugins, custom tables, APIs, or external systems.                                       | Determines whether standard handling, Add-ons, exclusions, or Custom Service review is required.              |
| Presentation layer   | Which parts of the site depend on themes, builders, blocks, shortcodes, widgets, menus, or templates.                    | Prevents confusing data migration with layout reconstruction.                                                 |
| SEO and URL behavior | Which slugs, permalink patterns, redirects, canonical values, and SEO fields must be preserved.                          | Reduces post-launch traffic, indexing, and internal-link risk.                                                |
| Validation samples   | Which records must be included in Demo Migration samples.                                                                | Makes Demo Migration a meaningful proof step rather than a random data sample.                                |

### Confirm the Target WordPress Role <a href="#confirm-the-target-wordpress-role" id="confirm-the-target-wordpress-role"></a>

A WordPress migration should begin by defining what WordPress is expected to do after launch. WordPress may be a simple CMS, a headless content source, a marketing site, a publishing hub, a membership site, a learning site, a booking site, a directory, or a companion to a separate commerce platform.

| Target role                    | Preparation requirement                                                                                   | Watch point                                                                                                      |
| ------------------------------ | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Standard CMS site              | Confirm CMS Pages, Blog Posts, media, menus, users, categories, tags, and SEO fields.                     | Do not over-scope plugin data that is no longer needed.                                                          |
| Content-heavy publishing site  | Confirm authors, dates, categories, tags, comments, featured media, archives, and editorial redirects.    | Blog Posts should not be flattened into CMS Pages.                                                               |
| Custom content site            | Confirm custom post types, custom taxonomies, field groups, relationships, archives, and search behavior. | Target structures must exist before migrated records can be useful.                                              |
| Plugin-driven operational site | Identify memberships, LMS, events, bookings, forms, directories, donations, or marketplace records.       | Plugin records may require special handling or Custom Service review.                                            |
| WooCommerce-connected project  | Separate WordPress CMS scope from WooCommerce commerce scope.                                             | Product, Customer, Order, coupon, tax, and shipping behavior should not be treated as generic WordPress content. |
| Headless or composable setup   | Confirm whether WordPress stores source content, exposes API content, or only receives selected records.  | External IDs and API relationships may matter more than visible layout.                                          |

### Inventory Core WordPress Content <a href="#inventory-core-wordpress-content" id="inventory-core-wordpress-content"></a>

Core WordPress content is the easiest preparation layer to miss because it feels obvious. Each core record still needs ownership, relationship, and validation decisions before migration.

| Record type          | What to prepare                                                                                                           | Demo Migration sample requirement                                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| CMS Pages            | Page hierarchy, slugs, status, parent pages, templates, featured media, internal links, menu placement, and SEO metadata. | Include top-level pages, nested pages, landing pages, policy pages, and pages with forms or builder layouts.          |
| Blog Posts           | Titles, slugs, dates, authors, excerpts, featured images, categories, tags, comments, and publish status.                 | Include high-traffic posts, older posts, scheduled/draft examples, posts with comments, and posts with complex media. |
| Media                | Image files, document files, captions, alt text, titles, descriptions, attachment relationships, and embedded usage.      | Include featured images, galleries, downloadable files, embedded media, and reused media assets.                      |
| Categories and tags  | Blog taxonomy structure, source category hierarchy, tag cleanup, archive URLs, and redirect needs.                        | Include posts assigned to multiple categories/tags and archive pages with SEO value.                                  |
| Menus and navigation | Menu hierarchy, custom links, category links, page links, footer menus, and mobile navigation assumptions.                | Include primary, footer, utility, and custom menu examples.                                                           |
| Comments             | Comment status, moderation state, author details, nested replies, spam exclusions, and privacy expectations.              | Include approved comments, nested comments, and posts with comment-history value.                                     |

Preparation should also identify content that should not be migrated. Drafts, test pages, duplicate posts, obsolete media, spam comments, unused tags, and legacy landing pages can inflate scope and reduce launch clarity.

### Prepare Custom Post Types and Taxonomies <a href="#prepare-custom-post-types-and-taxonomies" id="prepare-custom-post-types-and-taxonomies"></a>

Custom post types and custom taxonomies often define the real shape of a WordPress site. Events, resources, courses, staff profiles, locations, portfolios, testimonials, directories, jobs, documentation entries, case studies, and listings may all use different target structures.

| Source structure             | Preparation task                                                                                                        | Why it matters                                                                            |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Custom post type records     | Confirm the target post type name, labels, archive behavior, editor support, REST/API exposure, and template ownership. | Records may migrate but remain hidden or uneditable if the target post type is not ready. |
| Custom taxonomies            | Confirm hierarchy, term relationships, archive URLs, and whether taxonomy terms replace source categories.              | Filtering and archive behavior can break if terms are mapped to the wrong taxonomy.       |
| Relationship fields          | Identify parent-child, related content, location, staff, event, product-like, or resource relationships.                | Relationships may require field mapping or Custom Service review.                         |
| Field groups                 | Confirm field names, field types, repeaters, media fields, relationship fields, and conditional fields.                 | Metadata must match how the target template expects to read it.                           |
| Archive and detail templates | Confirm how each record type is displayed after migration.                                                              | Data can be correct while public output is incomplete.                                    |

A clean preparation package should include representative examples for every custom content type, not only the highest-volume type.

### Prepare Custom Fields, Metadata, and Plugin Data <a href="#prepare-custom-fields-metadata-and-plugin-data" id="prepare-custom-fields-metadata-and-plugin-data"></a>

WordPress metadata can carry critical meaning without being visible in the editor or on the front end. Preparation should classify metadata by business value rather than migrate every hidden field blindly.

| Data type                            | Preparation decision                                                                                                      | Recommended action                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| SEO plugin metadata                  | Decide which SEO titles, descriptions, canonical values, index rules, schema fields, and social fields must be preserved. | Map priority fields and test high-value pages in Demo Migration.                                   |
| Builder metadata                     | Identify builder layouts, module settings, shortcode data, reusable blocks, and serialized configuration.                 | Decide whether layout should be preserved, rebuilt, accepted as simplified, or handled separately. |
| Custom field groups                  | Confirm which fields are required for display, filtering, search, relationships, or integrations.                         | Prepare field mapping and sample records with every critical field type.                           |
| Form records                         | Separate form definitions, submissions, notifications, CRM links, and file uploads.                                       | Decide whether submission history is in scope or excluded.                                         |
| Membership/LMS/event/booking records | Identify operational records, user relationships, payments, schedules, progress, tickets, attendance, and access rules.   | Confirm whether plugin-specific migration is supported or needs Custom Service review.             |
| Custom tables                        | Identify table ownership, primary keys, foreign keys, external IDs, and target equivalents.                               | Use Custom Service review when records do not map to ordinary WordPress entities.                  |

Not every metadata field should be migrated. Some fields are cache, old plugin state, layout residue, temporary imports, tracking data, or abandoned settings. Preparation should distinguish reusable business data from technical clutter.

### Prepare Users, Roles, Authors, and Account-Like Records <a href="#prepare-users-roles-authors-and-account-like-records" id="prepare-users-roles-authors-and-account-like-records"></a>

WordPress user records can represent many different meanings. A user may be an author, editor, subscriber, member, learner, donor, vendor, directory owner, customer, staff member, or API identity. Preparation should define user meaning before migration.

| User/account pattern       | Preparation requirement                                                                                | Risk if skipped                                                           |
| -------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Blog authors               | Preserve author assignment, display name, author archive expectations, and historical posts.           | Blog Posts may show generic authors or lose editorial attribution.        |
| Administrators and editors | Review roles, capabilities, inactive accounts, security risk, and required users after launch.         | Old privileged accounts may migrate unnecessarily.                        |
| Members/subscribers        | Confirm membership level, access status, renewal state, subscription references, and plugin ownership. | Login may work while entitlement or access history is wrong.              |
| LMS learners               | Separate user accounts from enrollments, progress, quizzes, certificates, and course access.           | User records may migrate without learning history.                        |
| Donors or form contacts    | Confirm whether the record belongs in WordPress, a donation plugin, CRM, or external system.           | Contact history may be incomplete or duplicated.                          |
| WooCommerce customers      | Separate commerce scope from generic WordPress user handling.                                          | Customer, Order, billing, shipping, and subscription meaning may be lost. |

Password handling should be planned separately. When password hashes cannot be safely or compatibly preserved, the migration plan should include password reset, activation, or customer/member communication expectations.

### Prepare Themes, Builders, Blocks, Menus, and Widgets <a href="#prepare-themes-builders-blocks-menus-and-widgets" id="prepare-themes-builders-blocks-menus-and-widgets"></a>

Data migration does not automatically recreate the WordPress presentation layer. Preparation should identify where the target site relies on theme templates, block patterns, reusable blocks, page-builder modules, shortcodes, menus, widgets, and global template parts.

| Presentation layer     | Preparation task                                                                                         | Acceptance decision                                                               |
| ---------------------- | -------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Block editor content   | Identify reusable blocks, block patterns, embeds, media references, and invalid block risks.             | Decide whether block structure must remain editable or only visually acceptable.  |
| Classic editor content | Review HTML cleanup, shortcodes, embeds, tables, and inline styling.                                     | Decide whether legacy markup is acceptable or should be cleaned.                  |
| Page builders          | Inventory builder plugin, module types, serialized settings, templates, and dynamic fields.              | Decide whether builder content is migrated, rebuilt, simplified, or excluded.     |
| Theme templates        | Identify archive, single, page, header, footer, and taxonomy templates.                                  | Confirm whether template setup is implementation scope, not data migration scope. |
| Menus/widgets          | Prepare menus, sidebars, footer widgets, custom links, and reusable navigation blocks.                   | Confirm which structural elements are migrated versus manually configured.        |
| Shortcodes             | Identify active shortcodes, obsolete shortcodes, embedded forms, galleries, sliders, and plugin outputs. | Decide whether shortcodes remain supported or need replacement.                   |

This step prevents a common misunderstanding: content can be migrated accurately while the new site still needs theme or builder work to display it correctly.

### Prepare SEO, URLs, Redirects, and Search Visibility <a href="#prepare-seo-urls-redirects-and-search-visibility" id="prepare-seo-urls-redirects-and-search-visibility"></a>

WordPress URL continuity depends on slugs, parent hierarchy, permalink settings, custom post type rewrite rules, taxonomy archive paths, media paths, redirect tools, SEO plugin fields, theme output, and server/CDN rules.

| SEO/URL item          | What to prepare                                                                                    | Priority sample                                                                           |
| --------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| High-value URLs       | Export source URLs, traffic-priority URLs, backlink-sensitive URLs, and conversion pages.          | Top landing pages, high-traffic posts, evergreen resources, and campaign pages.           |
| Slugs and permalinks  | Confirm target permalink structure and parent-child page paths.                                    | Nested pages, posts, custom post types, and taxonomy archives.                            |
| Redirects             | Prepare old URL to new URL mapping and define who configures redirects.                            | Changed paths, removed pages, merged content, media URLs, and archive paths.              |
| SEO metadata          | Identify SEO title, meta description, canonical, index/noindex, schema, and social preview fields. | Priority pages, Blog Posts, taxonomy archives, and custom post type records.              |
| Internal links        | Identify content-body links, menus, widgets, builder links, custom fields, and shortcode links.    | Pages with many internal references or old absolute URLs.                                 |
| Search/facet behavior | Confirm how search, archives, filters, and plugin search indexes should behave.                    | Custom post type archives, resource filters, directory filters, and search landing pages. |

SEO preparation should be evidence-based. The migration plan should not promise complete SEO preservation without knowing which SEO plugin, redirect mechanism, permalink settings, and content paths are in scope.

### Prepare Integrations and External-System Ownership <a href="#prepare-integrations-and-external-system-ownership" id="prepare-integrations-and-external-system-ownership"></a>

Many WordPress sites rely on systems outside WordPress for operational truth. Preparation should decide whether each record should be migrated into WordPress, referenced by WordPress, synchronized through an integration, or excluded.

| External dependency                                   | What to prepare                                                                        | Scope decision                                                                       |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| CRM and marketing tools                               | Contact IDs, tags, segments, consent, forms, automation triggers, and hidden fields.   | Migrate, map, preserve references, reconnect, or exclude.                            |
| LMS, membership, donation, booking, and event systems | Operational records, payments, attendance, progress, access rules, and external IDs.   | Confirm whether plugin-specific records are supported or need Custom Service review. |
| ERP, PIM, catalog, or inventory systems               | Display copies, product-like records, sync rules, and ownership of authoritative data. | Avoid treating synchronized display data as standalone WordPress truth.              |
| Analytics and tracking                                | Tracking codes, events, goals, pixels, tag manager settings, and conversion paths.     | Usually implementation/configuration scope, not ordinary data migration.             |
| Payment and subscription systems                      | Tokens, invoices, subscriptions, billing references, and renewal states.               | Do not promise continuity without plugin/system-specific confirmation.               |
| Custom APIs and middleware                            | External IDs, sync keys, payload mappings, and workflow dependencies.                  | Use Custom Service review when transformation or preservation is non-standard.       |

The safest preparation method is to assign ownership: WordPress-owned, plugin-owned, external-system-owned, implementation-owned, or Custom Service review.

### Plan Demo Migration Samples <a href="#plan-demo-migration-samples" id="plan-demo-migration-samples"></a>

Demo Migration is most useful when samples represent real migration risk. A sample limited to ordinary posts and pages may look successful while missing the records that will decide launch readiness.

| Sample group                  | Include examples of                                                                                    | Why it should be tested                                              |
| ----------------------------- | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| Core CMS content              | CMS Pages, Blog Posts, media, categories, tags, comments, menus, and users.                            | Confirms baseline WordPress record handling.                         |
| Custom content                | Custom post types, custom taxonomies, custom fields, relationships, and archive examples.              | Confirms structured content meaning.                                 |
| Plugin-owned data             | Forms, memberships, LMS, events, bookings, directories, donations, or other active plugin records.     | Confirms whether standard handling is enough.                        |
| Builder/theme-dependent pages | Block pages, classic editor pages, builder layouts, reusable sections, shortcodes, and embedded forms. | Confirms the difference between data preservation and visual output. |
| SEO-sensitive records         | Priority URLs, redirects, SEO metadata, taxonomy archives, and media-heavy pages.                      | Confirms URL and search visibility assumptions.                      |
| Integration-sensitive records | External IDs, CRM-linked forms, system-owned profiles, and custom workflow references.                 | Confirms whether hidden fields and references survive.               |

Demo Migration findings should be converted into decisions: proceed as planned, adjust mapping, add Add-ons, exclude unsupported data, or request Custom Service review.

### Decide Add-ons, Custom Service, and Accepted Exclusions <a href="#decide-add-ons-custom-service-and-accepted-exclusions" id="decide-add-ons-custom-service-and-accepted-exclusions"></a>

Preparation should not treat every unusual record as Custom Service, but it should not hide custom requirements inside ordinary migration scope either.

| Requirement                                                 | Likely path                                                         | Preparation evidence needed                                                          |
| ----------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Filter or reduce standard content scope                     | Data Filter Add-on or accepted exclusion.                           | Clear inclusion/exclusion rules for pages, posts, media, users, or comments.         |
| Adjust field mapping within supported scope                 | Advanced Data Mapping or Advanced Data Configure where appropriate. | Source fields, target fields, sample records, and expected output.                   |
| Preserve plugin data with supported structure               | Add-ons or scoped configuration.                                    | Plugin type, record samples, target equivalents, and validation plan.                |
| Transform custom post types, custom tables, or external IDs | Custom Service review.                                              | Source schema, target structure, business logic, and pass conditions.                |
| Recreate layouts, templates, or custom front-end behavior   | Usually implementation or Custom Service review depending on scope. | Target theme/builder strategy and expected visual/editing outcome.                   |
| Preserve commerce behavior                                  | WooCommerce or commerce-plugin-specific planning.                   | Confirm whether commerce scope belongs to WordPress, WooCommerce, or another target. |

Add-ons extend or refine supported migration scope. Custom Service is for non-standard structures, transformations, custom platform behavior, or requirements that cannot be handled by ordinary configuration alone.

### Prepare for Additional Migration Options <a href="#prepare-for-additional-migration-options" id="prepare-for-additional-migration-options"></a>

Additional Migration Options matter when the source WordPress-related content remains active after initial migration activity. Preparation should define how changes will be handled before teams begin editing both sites.

| Preparation question                           | Why it matters                                                                                      | Recommended response                                                                          |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Which records may change after Demo Migration? | Blog Posts, CMS Pages, users, media, comments, and form submissions may continue changing.          | Track changed records and avoid uncontrolled edits on both sides.                             |
| Which new records may appear before launch?    | New Blog Posts, CMS Pages, users, and eligible records may need later migration handling.           | Separate newly created records from records already counted through the service license.      |
| Which plugin records are time-sensitive?       | Form submissions, memberships, LMS progress, bookings, events, and donations may change frequently. | Decide whether they are migrated, excluded, frozen, or handled through Custom Service review. |
| Which URLs may change before launch?           | New slugs, redirected pages, merged posts, and unpublished content can affect launch continuity.    | Update redirect and SEO review before Full Migration acceptance.                              |
| Which teams can edit source and target?        | Parallel editing can create conflict.                                                               | Define freeze windows, ownership, and launch-day editing rules.                               |

Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action for the same migration path. New eligible Product, Customer, Order, or Blog Posts records may consume Entity Points when migrated for the first time, including when the customer performs a new migration for the same migration path.

### WordPress Preparation Readiness Matrix <a href="#wordpress-preparation-readiness-matrix" id="wordpress-preparation-readiness-matrix"></a>

| Readiness area     | Ready signal                                                                                                  | Not ready signal                                                                               | Next action                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Core content       | CMS Pages, Blog Posts, media, users, comments, categories, tags, and menus are inventoried.                   | Source content volume exists but relationships, statuses, authors, or media usage are unclear. | Complete content inventory and select Demo Migration samples.        |
| Custom structure   | Custom post types, taxonomies, field groups, and templates are documented.                                    | Custom content is described only as pages or posts.                                            | Prepare structure map and field samples.                             |
| Plugin data        | Active plugin-owned records are classified by ownership and target handling.                                  | Plugins are listed but their data records are not reviewed.                                    | Separate supported, excluded, Add-on, and Custom Service candidates. |
| Layout layer       | Theme, builder, block, shortcode, menu, and widget expectations are separated from data migration.            | Visual continuity is assumed from data migration alone.                                        | Define accepted layout outcomes and implementation scope.            |
| SEO and URLs       | Priority paths, redirects, metadata, archives, and internal links are identified.                             | SEO is deferred until after migration.                                                         | Prepare URL/redirect/metadata review before Demo Migration.          |
| Integrations       | CRM, forms, LMS, membership, booking, donation, analytics, and API ownership is known.                        | Hidden IDs and external-system references are undocumented.                                    | Prepare integration ownership table.                                 |
| Service scope      | Add-ons, Custom Service, and accepted exclusions are separated.                                               | Custom requirements are hidden inside standard content expectations.                           | Confirm service path before Full Migration.                          |
| Follow-up handling | Additional Migration Options, freeze windows, changed records, and Entity Points implications are understood. | Teams continue editing without a follow-up plan.                                               | Create launch-window data change rules.                              |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress preparation is strongest when it treats the target site as a structured CMS environment, not only a destination for pages and posts. The most important work happens before migration: defining the target role of WordPress, separating core content from plugin and custom records, documenting metadata and layout dependencies, preparing SEO and URL decisions, identifying external-system ownership, and choosing meaningful Demo Migration samples.

A well-prepared WordPress migration gives each record a clear destination, each custom requirement an owner, and each launch-sensitive dependency a validation path. That preparation makes it easier to decide when Standard Service is enough, when Add-ons can refine the scope, and when Custom Service review is needed for non-standard WordPress structures or custom platform behavior.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Should a WordPress migration preparation checklist include WooCommerce data?**

Only when WooCommerce is part of the target scope. WordPress and WooCommerce should be planned separately because WooCommerce commerce records such as products, customers, orders, coupons, tax settings, shipping settings, and subscriptions carry different migration meaning from generic WordPress content.

**What WordPress records should be prepared before Demo Migration?**

Prepare representative CMS Pages, Blog Posts, media, categories, tags, users, comments, menus, custom post types, taxonomies, custom fields, plugin records, builder pages, SEO-sensitive URLs, and integration-linked records. The sample should include records that prove migration risk, not only records that are easy to move.

**Do WordPress plugins automatically migrate with the site data?**

No. Plugin files, plugin settings, plugin-owned records, custom tables, and external integrations need separate review. Some plugin data may be excluded, handled by Add-ons, configured in the target site, or reviewed as Custom Service scope.

**When should Custom Service be considered for WordPress preparation?**

Custom Service should be considered when the migration requires non-standard custom post type transformation, custom table handling, plugin-specific operational records, external ID preservation, custom field relationships, custom platform behavior, or target logic that cannot be handled through supported configuration alone.

**How do Additional Migration Options affect WordPress preparation?**

Additional Migration Options matter when source content, users, Blog Posts, plugin records, or other eligible records may change between migration activity and launch. Preparation should define freeze windows, changed-record tracking, revalidation needs, and Entity Points implications for newly migrated eligible records.
