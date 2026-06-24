# WordPress Data Model Differences

WordPress data migration is not only a record-transfer exercise. WordPress stores site meaning across a flexible CMS model, a theme and template layer, a plugin layer, metadata, media relationships, user roles, URL behavior, and often custom tables or external systems. A source record should therefore be judged by what it must become inside the target WordPress implementation, not only by whether it can be inserted into WordPress.

The main data-model difference is flexibility. A page-like record may become a CMS Page, Blog Post, custom post type entry, reusable block, builder layout, taxonomy archive, plugin record, or static template section. A customer-like record may become a WordPress user, author, member, subscriber, plugin customer, CRM contact, or custom profile. A product-like record may not belong to WordPress core at all unless WooCommerce, another commerce plugin, a custom post type, or a Custom Platform structure is part of the target architecture.

### Why WordPress Data Model Differences Matter <a href="#why-wordpress-data-model-differences-matter" id="why-wordpress-data-model-differences-matter"></a>

WordPress can represent many kinds of content, but it does not assign business meaning automatically. The target architecture decides whether migrated data remains editable, searchable, filterable, permission-aware, SEO-safe, and operational after Full Migration.

| Data-model question                                        | Why it matters in WordPress                                                                                                             | Migration decision it affects                                                                                            |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Is the record core WordPress content or plugin-owned data? | Posts, CMS Pages, Blog Posts, media, categories, tags, and users behave differently from plugin records and custom tables.              | Whether the item can use standard migration handling or needs Add-ons, mapping, exclusions, or Custom Service review.    |
| Does the record need a custom post type or taxonomy?       | WordPress can model structured content beyond posts and pages, but only when the target structure exists.                               | Whether resources, listings, events, courses, locations, portfolios, or directories need a defined target content model. |
| Which metadata controls display or behavior?               | Custom fields and plugin metadata can exist without appearing on the front end or in the expected editor.                               | Whether field migration is enough or whether theme, builder, plugin, or custom output must also be reviewed.             |
| Which layer controls the final layout?                     | Blocks, page builders, shortcodes, templates, reusable patterns, and theme files may control presentation separately from the record.   | Whether content migration alone is acceptable or whether implementation work is needed.                                  |
| Which URLs and SEO fields carry value?                     | Slugs, permalinks, taxonomy paths, redirects, canonical values, schema settings, and SEO plugin fields may live in separate structures. | Whether high-value paths need redirect planning, SEO field mapping, or accepted exclusions.                              |
| Which IDs matter outside WordPress?                        | CRM, ERP, LMS, donation, booking, analytics, membership, and automation systems may depend on hidden IDs or metadata.                   | Whether external IDs and system references need preservation or custom handling.                                         |

### Core WordPress Records and Their Migration Meaning <a href="#core-wordpress-records-and-their-migration-meaning" id="core-wordpress-records-and-their-migration-meaning"></a>

WordPress core gives the migration a baseline structure. Core records are usually easier to identify than plugin or custom records, but each still has relationships that must be preserved.

| WordPress record type | Data it can carry                                                                                                       | What should be reviewed                                                                                                        |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| CMS Pages             | Title, slug, content, parent page, template, featured media, status, author, metadata, and menu placement.              | Page hierarchy, layout dependencies, internal links, featured image, template assignment, SEO fields, and redirect needs.      |
| Blog Posts            | Title, content, author, dates, excerpt, categories, tags, comments, featured media, status, slug, format, and metadata. | Publishing history, authorship, category/tag assignments, archive behavior, comments, featured image, and URL continuity.      |
| Media                 | Images, files, attachments, captions, alt text, descriptions, filenames, MIME types, and links to content.              | Whether files remain attached to pages, posts, galleries, fields, builders, downloads, and SEO-sensitive image paths.          |
| Users                 | Username, email, display name, role, profile fields, password handling, capabilities, and user metadata.                | Whether users are authors, editors, members, subscribers, customers, learners, donors, vendors, or plugin-controlled accounts. |
| Comments              | Comment author, email, date, status, content, parent comment, and related post.                                         | Whether source comments are blog comments, reviews, discussions, testimonials, Q\&A, or plugin-owned interaction data.         |
| Menus                 | Navigation labels, links, hierarchy, page references, custom URLs, and menu locations.                                  | Whether source navigation should become menus, page hierarchy, taxonomy archives, redirects, or theme-controlled navigation.   |

Core records are often the safest starting point for a WordPress migration, but they are not enough when the site depends on custom content models, plugin behavior, commerce records, or external systems.

### CMS Pages, Blog Posts, and Editorial Structure <a href="#cms-pages-blog-posts-and-editorial-structure" id="cms-pages-blog-posts-and-editorial-structure"></a>

WordPress separates CMS Pages from Blog Posts. The difference is not cosmetic. CMS Pages usually represent stable site content, while Blog Posts usually carry editorial history, authorship, dates, categories, tags, archive behavior, comments, and publication status.

| Source content pattern                                | Better WordPress interpretation                                                              | Risk if mapped too simply                                                                        |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Static policy, about, contact, brand, or landing page | CMS Page with hierarchy, template, media, menu, and SEO review.                              | Page may exist but lose layout, parent-child structure, internal links, or conversion sections.  |
| Editorial article or news item                        | Blog Post with author, publish date, categories, tags, featured media, and archive behavior. | Blog history may flatten into pages and lose editorial discoverability.                          |
| Resource library entry                                | Custom post type or Blog Post depending on target browsing needs.                            | Resources may become difficult to filter, group, or reuse across templates.                      |
| Help article or documentation entry                   | Blog Post, CMS Page, or custom post type depending on archive/search model.                  | Support content may migrate but become hard to navigate or maintain.                             |
| Campaign landing page                                 | CMS Page, builder layout, reusable block, or template-controlled page.                       | Visible content may survive while forms, tracking, reusable sections, and layout behavior break. |

The migration decision should preserve how content is managed after launch. A record that looks like a page on the source site may need custom structure if it supports filtering, archives, relationship fields, or reusable design patterns.

### Custom Post Types and Custom Taxonomies <a href="#custom-post-types-and-custom-taxonomies" id="custom-post-types-and-custom-taxonomies"></a>

Custom post types and custom taxonomies allow WordPress to model content beyond standard posts and pages. They are often the difference between a clean WordPress implementation and a flat content dump.

| Source data type                         | Possible WordPress model                                                                                     | Review requirement                                                                                |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Events                                   | Custom post type with event dates, venue fields, registration links, organizer fields, and archive behavior. | Confirm date fields, recurring logic, event status, filters, and plugin ownership.                |
| Courses or lessons                       | LMS plugin records, custom post types, lesson hierarchy, enrollment data, and user progress.                 | Separate public content from enrollment, progress, quizzes, certificates, and user relationships. |
| Properties or listings                   | Custom post type with taxonomies, custom fields, media galleries, locations, and search filters.             | Confirm field groups, filters, map/location data, and lead-routing behavior.                      |
| Staff, authors, partners, or vendors     | Custom post type, user records, taxonomy terms, or plugin profiles.                                          | Decide whether the person is content, account, author, vendor, or external-system contact.        |
| Directories or resource hubs             | Custom post types, custom taxonomies, relationships, search fields, and archive templates.                   | Confirm taxonomy model, relationships, filtering, and template output before migration.           |
| Product-like records outside WooCommerce | Custom post type, commerce plugin record, catalog plugin record, or Custom Platform structure.               | Do not assume WordPress core owns product behavior. Confirm target plugin or custom model first.  |

The existence of a custom post type is not enough. The target site also needs the taxonomies, fields, templates, search behavior, archive behavior, and editing interface that make that content useful.

### Taxonomies, Categories, Tags, and Navigation <a href="#taxonomies-categories-tags-and-navigation" id="taxonomies-categories-tags-and-navigation"></a>

WordPress uses categories and tags for Blog Posts, but source categories may not always belong there. Some categories belong to page hierarchy, custom taxonomies, menus, faceted search, plugin filters, or commerce structures.

| Source grouping          | WordPress destination option                                                                 | Planning logic                                                                                          |
| ------------------------ | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Blog topics              | Categories and tags.                                                                         | Preserve archive behavior, internal links, and editorial discovery.                                     |
| Resource types           | Custom taxonomy or category depending on the target content model.                           | Use a custom taxonomy when resources need dedicated filters or templates.                               |
| Product categories       | WooCommerce taxonomy, commerce plugin category, custom taxonomy, or excluded commerce scope. | Do not treat commerce categories as generic WordPress categories unless the target model supports that. |
| Brand or vendor grouping | Custom taxonomy, plugin taxonomy, user/vendor profile, or directory structure.               | Choose based on whether the grouping controls browsing, vendor pages, search, or account logic.         |
| Main navigation          | WordPress menus, page hierarchy, theme navigation, or builder header.                        | Menu labels and category labels can look similar but behave differently.                                |
| Filter values            | Custom taxonomy, custom fields, plugin filters, or search-index fields.                      | Filtering must be validated in the target search/theme/plugin layer.                                    |

A common migration mistake is to preserve labels without preserving behavior. A category that controls product filtering, editorial archives, menu display, or search facets needs the correct target structure, not only the same name.

### Custom Fields, Metadata, and Display Logic <a href="#custom-fields-metadata-and-display-logic" id="custom-fields-metadata-and-display-logic"></a>

Custom fields are central to WordPress data modeling. They can store technical specs, summaries, labels, external IDs, dates, locations, relationship fields, SEO values, layout settings, and plugin-owned behavior. However, a migrated field may be present in the database but invisible in the editor or front end.

| Metadata type              | Where it may live                                                                                      | What must be proven                                                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Post or page custom fields | Post meta, field-group plugin data, block attributes, builder metadata, or custom tables.              | Field values display correctly, remain editable, and support filtering or search if required.                                 |
| User metadata              | User meta, membership plugin data, role/capability settings, CRM references, or custom profile fields. | Account meaning, role logic, segmentation, and external references remain usable.                                             |
| Term metadata              | Term meta, custom taxonomy settings, SEO plugin fields, or custom display rules.                       | Archive pages, descriptions, images, SEO fields, and filters behave correctly.                                                |
| SEO metadata               | SEO plugin fields, post meta, term meta, redirect plugin records, schema settings, or theme output.    | Titles, descriptions, canonical values, index rules, social previews, and schema output are mapped or intentionally excluded. |
| Integration IDs            | Custom fields, plugin metadata, API records, hidden keys, or external-system references.               | CRM, ERP, automation, LMS, booking, donation, or analytics systems can still identify migrated records where required.        |
| Layout metadata            | Builder fields, shortcodes, block attributes, template assignments, or theme settings.                 | Content remains visually coherent and editable in the intended target tools.                                                  |

Custom fields should be classified by purpose before migration. A field used for display is different from a field used for filtering, permissions, external sync, SEO, checkout logic, or reporting.

### Media, Attachments, and File Relationships <a href="#media-attachments-and-file-relationships" id="media-attachments-and-file-relationships"></a>

WordPress media migration must preserve both files and relationships. A Media Library item has limited value if it is disconnected from the post, page, gallery, field, form, download, or template that uses it.

| Media relationship     | Why it matters                                                                        | Review focus                                                                                  |
| ---------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Featured images        | Control cards, archives, social previews, and many theme layouts.                     | Correct attachment, dimensions, alt text, and preview behavior.                               |
| Inline images          | Appear inside post/page content, blocks, builder layouts, or static HTML.             | Broken image paths, duplicated uploads, image size variants, captions, and responsive output. |
| Galleries and sliders  | Often depend on shortcode, block, builder, or plugin structures.                      | Ordering, captions, links, thumbnails, and mobile behavior.                                   |
| Downloadable files     | May be media attachments, plugin downloads, protected files, or external links.       | Permissions, file URLs, download links, and historical references.                            |
| Media in custom fields | Often powers cards, directories, staff profiles, events, or listings.                 | Field-to-media relationships, alt text, display location, and search/filter behavior.         |
| SEO-sensitive media    | Image paths, alt text, captions, filenames, and redirects may affect organic traffic. | High-value media URLs, internal references, and metadata preservation.                        |

Media validation should include front-end pages, editor views, archives, search results, and high-value landing paths, not only the Media Library count.

### Users, Roles, Authors, Members, and Customer Meaning <a href="#users-roles-authors-members-and-customer-meaning" id="users-roles-authors-members-and-customer-meaning"></a>

WordPress has a user system, but user meaning can vary widely. A migrated person may be an author, editor, administrator, subscriber, member, learner, donor, vendor, customer, employee, directory contact, or external CRM record.

| Source person/account type      | WordPress interpretation                                                              | Risk to avoid                                                                         |
| ------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Blog author                     | WordPress user assigned to Blog Posts.                                                | Authorship may be lost if posts are mapped to generic users.                          |
| Site administrator or editor    | WordPress user with role/capability review.                                           | Permissions may become too broad, too narrow, or insecure.                            |
| Member or subscriber            | WordPress user plus membership/subscription plugin data.                              | Login may exist while membership status, plan, access, or renewal context is missing. |
| Learner or course participant   | LMS plugin user/enrollment/progress data.                                             | User record may migrate without enrollment, progress, quiz, or certificate history.   |
| Donor or nonprofit supporter    | Donation plugin record, CRM contact, user metadata, or external-system reference.     | Donation history and contact segmentation may be disconnected.                        |
| Customer from a commerce source | WooCommerce customer, commerce plugin account, user metadata, or external CRM record. | Commerce meaning should not be flattened into a generic WordPress user.               |

Password migration is a separate planning issue. If password hashes cannot be preserved safely or compatibly, the plan should include password reset, activation, or login-communication expectations.

### Plugins, Custom Tables, and Business Data <a href="#plugins-custom-tables-and-business-data" id="plugins-custom-tables-and-business-data"></a>

Many WordPress sites rely on plugins for business records that WordPress core does not define. A migration must identify whether data is core WordPress data, plugin-owned data, custom-table data, external-system data, or Custom Platform data.

| Plugin/business area          | Common data-model location                                                                                      | Migration implication                                                                   |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Forms and submissions         | Plugin tables, post meta, entries API, email logs, CRM integrations, or external systems.                       | Submission history may need Custom Service review or may be excluded if not supported.  |
| Memberships and subscriptions | User meta, plugin tables, subscription records, payment references, access rules, and external billing systems. | Access and billing meaning require careful scope definition.                            |
| LMS/courses                   | Custom post types, lessons, enrollments, progress, quizzes, certificates, and user meta.                        | Content migration and learner-history migration are different scopes.                   |
| Events/bookings               | Custom post types, plugin tables, dates, venues, attendees, tickets, calendar feeds, and payments.              | Event content may move separately from bookings, registrations, and attendance history. |
| Directories/listings          | Custom post types, custom taxonomies, custom fields, maps, search indexes, and payments.                        | Filters, location data, relationships, and paid listing logic need target proof.        |
| Donations/nonprofit records   | Plugin tables, CRM contacts, payment IDs, donor profiles, campaigns, and receipts.                              | Historical giving data may require plugin or CRM-specific handling.                     |
| Commerce plugin data          | Products, orders, customers, coupons, taxes, shipping, subscriptions, and payment references.                   | Use WooCommerce or plugin-specific planning rather than generic WordPress assumptions.  |

Plugin-owned records often determine whether Standard Service, Managed Service, Add-ons, accepted exclusions, or Custom Service is appropriate.

### Themes, Builders, Blocks, and Layout Data <a href="#themes-builders-blocks-and-layout-data" id="themes-builders-blocks-and-layout-data"></a>

WordPress separates content storage from visual output. Block editor content, reusable blocks, block patterns, classic editor HTML, shortcodes, page-builder data, theme templates, template parts, menus, widgets, and custom theme logic can all affect how migrated content appears.

| Layout layer         | Data-model concern                                                                               | Review method                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| Block editor content | Blocks may carry structured attributes, reusable blocks, embeds, and media references.           | Review editability, block validity, and front-end output.           |
| Classic HTML content | Source markup may transfer but remain hard to edit or inconsistent with the target theme.        | Review priority pages and clean up accepted exceptions.             |
| Page-builder data    | Builder rows, widgets, modules, shortcodes, and serialized settings may not map directly.        | Confirm target builder strategy before promising layout continuity. |
| Theme templates      | Headers, footers, archives, single templates, page templates, and template parts control output. | Validate representative content types against target templates.     |
| Menus and widgets    | Navigation, sidebars, footers, and reusable site elements may not belong to individual pages.    | Separate record migration from site-structure setup.                |

A visually complete WordPress migration requires both data placement and target presentation readiness. Data can be migrated correctly while layout still needs theme, builder, or implementation work.

### SEO, Permalinks, Redirects, and URL Data <a href="#seo-permalinks-redirects-and-url-data" id="seo-permalinks-redirects-and-url-data"></a>

WordPress URL meaning depends on slugs, permalink settings, parent-child hierarchy, post type archives, taxonomies, media paths, theme routing, plugin routing, redirect tools, and SEO metadata. SEO preservation should be planned as a data-model concern, not an afterthought.

| SEO/URL element         | Where it may live                                                                                           | Why it matters                                                        |
| ----------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Slugs and permalinks    | Post/page records, custom post type settings, parent hierarchy, permalink configuration, and rewrite rules. | Final URLs may differ even when content records exist.                |
| Redirects               | Redirect plugin, server configuration, CDN, SEO plugin, or migration mapping file.                          | High-value old URLs need destination mapping and post-launch testing. |
| SEO titles/descriptions | SEO plugin metadata, post meta, term meta, or custom fields.                                                | Organic snippets and page intent can change if fields are not mapped. |
| Canonical/index rules   | SEO plugin fields, theme output, robots settings, or custom code.                                           | Duplicate-content and indexing behavior may change after migration.   |
| Schema/social metadata  | SEO plugin fields, custom fields, theme output, or external scripts.                                        | Rich result and social preview behavior may need separate review.     |
| Internal links          | Body content, menus, widgets, builders, custom fields, and plugin records.                                  | Links may continue to point to old paths if not transformed.          |

SEO-sensitive WordPress migrations should sample both high-traffic pages and structured content archives. Archive and taxonomy paths can matter as much as individual page URLs.

### External IDs, APIs, and Integration-Owned Records <a href="#external-ids-apis-and-integration-owned-records" id="external-ids-apis-and-integration-owned-records"></a>

WordPress frequently acts as one part of a broader digital stack. External systems may own customer identity, order references, CRM contacts, donor history, course enrollment, booking availability, email segmentation, analytics events, or content synchronization.

| External dependency          | Data-model impact                                                                                 | Scope decision                                                                               |
| ---------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| CRM/contact platform         | WordPress may store only a form submission, tag, user ID, or external contact reference.          | Preserve IDs only when they are needed for post-launch matching or automation.               |
| Email/marketing platform     | Subscribers, segments, consent, preferences, and tags may live outside WordPress.                 | Decide whether records migrate into WordPress, remain external, or are referenced by fields. |
| ERP/PIM/catalog system       | WordPress may display records sourced from external systems.                                      | Avoid migrating display copies as authoritative records unless ownership is clear.           |
| LMS/booking/donation systems | WordPress may host front-end content while operational records stay in plugins or external tools. | Separate public content from operational history and permissions.                            |
| Payment/subscription system  | Payment tokens, invoices, subscriptions, renewals, and billing references may be external.        | Do not promise continuity without plugin/system-specific review.                             |
| Custom API or middleware     | Hidden IDs and sync rules may be more important than visible content.                             | Custom Service review may be needed for non-standard transformation or preservation.         |

The practical test is ownership. If WordPress only displays a record that is owned somewhere else, the migration should not treat the display copy as the authoritative target data.

### Entity Points and WordPress Data Scope <a href="#entity-points-and-wordpress-data-scope" id="entity-points-and-wordpress-data-scope"></a>

Entity Points planning should be tied to the data records that actually enter the migration scope. Standard content such as CMS Pages, Blog Posts, media, users, and other eligible records should be reviewed against the service license and Entity Points Plan before Full Migration.

When later migration activity is performed for the same migration path, records already counted through the service license do not consume Entity Points again simply because another migration action is performed. New eligible Product, Customer, Order, or Blog Posts records may consume Entity Points when they are migrated for the first time, including when the customer performs a new migration for the same migration path.

| Scope question                                 | Why it matters for WordPress                                                                  | Planning response                                                                                   |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Which records are ordinary WordPress content?  | Posts, CMS Pages, Blog Posts, media, users, and comments may be easier to count and validate. | Confirm included entities and volume expectations before Full Migration.                            |
| Which records are plugin-owned?                | Plugin data may not follow ordinary WordPress content assumptions.                            | Confirm whether they are supported, excluded, handled by Add-ons, or require Custom Service review. |
| Which records are new after initial migration? | New eligible records may consume Entity Points when migrated for the first time.              | Separate new records from records already counted through the service license.                      |
| Which records are external references?         | External IDs or display copies may not be migrated as standalone entities.                    | Decide whether they are data records, references, or integration scope.                             |

Entity Points review should not replace data-model review. It confirms scope accounting, while data-model review confirms whether the target structure preserves meaning.

### Add-ons and Custom Service in WordPress Data Modeling <a href="#add-ons-and-custom-service-in-wordpress-data-modeling" id="add-ons-and-custom-service-in-wordpress-data-modeling"></a>

Add-ons and Custom Service affect how WordPress data differences are handled. They should not be merged into the same decision.

| Requirement                                                                                                            | Likely handling                                                                                         | Reasoning                                                                                                                 |
| ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Selective content transfer, filtering, or field refinement                                                             | Add-ons where available.                                                                                | The target model is supported, but the migration needs narrower or enhanced handling.                                     |
| More complex field mapping or source-to-target interpretation                                                          | Advanced Data Mapping, Advanced Data Configure, Tailored Add-ons, or Custom Add-ons depending on scope. | WordPress can receive the data, but field behavior requires more precise planning.                                        |
| Plugin-owned data in supported structures                                                                              | Add-ons or Managed Service depending on available handling and operational needs.                       | Some plugin or metadata output may be within planned scope if clearly supported.                                          |
| Unsupported plugin records, custom tables, serialized data, bespoke business logic, or external-system synchronization | Custom Service review.                                                                                  | The target output needs tailored interpretation, non-standard extraction, transformation, or implementation coordination. |
| WooCommerce or other commerce-layer records                                                                            | WooCommerce-specific path, plugin-specific scoping, or Custom Service depending on target stack.        | WordPress core does not define commerce records by itself.                                                                |

The boundary is important: Add-ons extend or refine supported migration handling; Custom Service addresses non-standard requirements that need tailored review.

### WordPress Data Model Decision Matrix <a href="#wordpress-data-model-decision-matrix" id="wordpress-data-model-decision-matrix"></a>

| Decision area | Low-complexity data model                                                  | Conditional data model                                                                                 | Custom-review data model                                                                              |
| ------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| Content types | Mostly CMS Pages, Blog Posts, media, authors, categories, tags, and menus. | Includes custom post types, custom taxonomies, reusable blocks, builders, or multilingual structures.  | Source uses undocumented content structures, custom applications, or database-specific relationships. |
| Metadata      | Basic SEO fields, excerpts, featured images, and simple custom fields.     | Field groups, relationship fields, filters, external IDs, and theme/plugin display fields.             | Serialized plugin data, custom tables, private fields, or business rules requiring transformation.    |
| Users         | Authors, editors, subscribers, and standard user metadata.                 | Members, learners, donors, vendors, customers, or role-specific access.                                | Business-critical permissions, billing, enrollment, subscription, or external identity logic.         |
| Plugins       | Plugins support display but do not own critical historical records.        | Plugin-owned records are important and need mapping or validation.                                     | Unsupported plugin records, custom tables, or external APIs own the real data.                        |
| URLs and SEO  | Standard slugs, redirects, metadata, and internal links.                   | Custom post type archives, taxonomy paths, SEO plugin fields, multilingual paths, and schema behavior. | Complex routing, custom rewrite rules, or high-risk SEO structures without clear target ownership.    |
| Service scope | Standard Service or Managed Service can cover defined records.             | Add-ons or deeper configuration may be needed.                                                         | Custom Service review should happen before migration assumptions are accepted.                        |

This matrix helps classify WordPress data-model risk before Demo Migration. The goal is to decide whether the project is a standard content migration, a structured WordPress migration, a plugin-dependent migration, or a custom application migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress data model differences come from flexibility. The same source item may become a CMS Page, Blog Post, media item, taxonomy term, user, custom post type, custom field, plugin record, menu item, SEO field, redirect, custom-table record, or external-system reference. Successful migration depends on choosing the target meaning before moving records.

Before approving a WordPress migration plan, separate core WordPress content from custom structures, plugin-owned records, external-system references, layout data, and SEO-sensitive fields. Use Demo Migration results to prove that migrated data can be found, edited, displayed, filtered, linked, indexed, and managed in the target WordPress implementation before moving into Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Does WordPress treat products as native data?**

No. WordPress core does not provide native product, cart, checkout, payment, shipping, tax, or order behavior. Product and commerce meaning depends on WooCommerce, another commerce plugin, a custom post type, an external commerce system, or Custom Platform handling.

**Are WordPress CMS Pages and Blog Posts the same thing?**

No. CMS Pages usually represent stable site content, while Blog Posts usually carry publication dates, authors, categories, tags, archives, comments, and editorial history. Source content should be mapped by how it should be managed and displayed after migration.

**Can custom fields migrate into WordPress?**

Custom fields can be part of a WordPress migration when the target structure supports them. The important question is whether the fields remain visible, editable, searchable, filterable, and used by the theme, plugin, or custom logic that controls the target site.

**What happens to page-builder content during a WordPress migration?**

Page-builder content needs separate review because layout elements may depend on builder-specific structures, widgets, shortcodes, serialized settings, reusable sections, or theme behavior. Some content may migrate as editable records, while other layouts may require compatible tooling, rebuilding, or accepted changes.

**Why are plugins important in WordPress data migration?**

Plugins can define products, bookings, memberships, donations, forms, courses, events, SEO metadata, reviews, custom fields, and integration records. When important records belong to plugins, migration planning should confirm whether those structures are supported, need Add-ons, require Custom Service review, or should be excluded.
