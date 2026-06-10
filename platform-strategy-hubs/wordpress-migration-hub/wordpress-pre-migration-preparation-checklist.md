# WordPress Pre-Migration Preparation Checklist

Preparing for a WordPress migration means defining the target WordPress implementation before records are moved. WordPress is a CMS and application foundation, so migration quality depends on more than posts and pages. The target installation, theme system, plugin stack, custom post types, custom fields, taxonomies, users, media, URLs, SEO layer, and any plugin-owned business data must be clear before Demo Migration or Full Migration begins.

Preparation should separate WordPress core content from plugin-specific behavior. Posts, CMS Pages, Blog Posts, media, comments, users, categories, and tags can be reviewed as WordPress content structures. Commerce, memberships, bookings, events, learning content, forms, donations, subscriptions, multilingual relationships, and page-builder layouts depend on plugins, themes, custom fields, custom tables, or custom code.

### What Preparation Is For <a href="#what-preparation-is-for" id="what-preparation-is-for"></a>

A WordPress migration should not begin with record counts alone. The preparation stage should make the target structure testable. It should show which source records belong in WordPress core, which records depend on plugins, which relationships must remain readable, and which target behaviors require configuration or Custom Service review.

| Preparation goal         | What to confirm                                                                                                     | Why it matters                                                                                                                                 |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Target WordPress context | WordPress version, hosting environment, multisite status, theme type, plugin stack, and target content model        | WordPress behavior can change materially depending on installation, theme, plugins, and custom implementation.                                 |
| Content migration scope  | Posts, CMS Pages, Blog Posts, comments, media, menus, authors, categories, tags, slugs, dates, and statuses         | Core content needs enough structure to remain findable, editable, and readable after migration.                                                |
| Custom data scope        | Custom post types, custom taxonomies, post meta, custom fields, relationship fields, and custom tables              | Business meaning often lives outside standard posts and pages.                                                                                 |
| Plugin-owned data        | Commerce, membership, LMS, booking, event, donation, form, SEO, multilingual, page-builder, or subscription records | Plugin data should not be assumed to migrate unless it is supported and included in scope.                                                     |
| Launch continuity        | URLs, redirects, metadata, media references, templates, navigation, and priority rendered pages                     | A technically migrated page can still fail if it loses layout, routing, or SEO context.                                                        |
| Service implications     | Standard Service, Managed Service, Add-ons, or Custom Service signals                                               | The right approach depends on how much of the target WordPress result relies on standard structures versus custom or plugin-specific behavior. |

### 1. Confirm the Target WordPress Environment <a href="#id-1-confirm-the-target-wordpress-environment" id="id-1-confirm-the-target-wordpress-environment"></a>

The target WordPress installation should be defined before migration samples are chosen. A clean content migration can still create launch risk if the target site uses the wrong theme type, missing plugins, incompatible custom fields, unclear user roles, or unconfirmed permalink behavior.

Prepare the following details:

| Target area                    | Preparation requirement                                                                                                                                                     |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| WordPress version              | Confirm the target WordPress version and whether any older source behavior needs version-specific review.                                                                   |
| Hosting and server environment | Confirm hosting, PHP and database readiness, file permissions, upload handling, caching, security rules, and staging availability where relevant.                           |
| Single site or multisite       | Confirm whether the target is a single WordPress site or a multisite network, because users, roles, media, and site relationships can differ.                               |
| Theme type                     | Identify whether the target uses a classic theme, block theme, Site Editor, custom theme, child theme, or page-builder-driven structure.                                    |
| Plugin stack                   | List required plugins for SEO, forms, multilingual content, memberships, LMS, bookings, events, donations, commerce, custom fields, redirects, analytics, and integrations. |
| Content model                  | Define whether target content uses standard posts and pages only or also custom post types, custom taxonomies, custom fields, and custom tables.                            |
| Permalink and URL plan         | Confirm permalink format, slug rules, domain changes, redirect expectations, taxonomy archives, and priority URLs.                                                          |

### 2. Prepare Core Content Samples <a href="#id-2-prepare-core-content-samples" id="id-2-prepare-core-content-samples"></a>

Core WordPress content should be sampled deliberately. Simple published pages are useful, but they do not prove whether a migration preserves the full source content model. Samples should include records that carry different statuses, relationships, authors, media attachments, URL patterns, and taxonomy assignments.

Prepare examples for:

* published, draft, private, and scheduled posts where those statuses matter;
* Blog Posts with categories, tags, featured images, excerpts, authors, dates, and comments;
* CMS Pages with parent-child hierarchy, page templates, media, embeds, and menu placement;
* landing pages or high-value pages that must remain visually and structurally reliable;
* comments, comment status, comment authorship, and moderation context where comments are in scope;
* pages or posts that use shortcodes, blocks, reusable patterns, embedded media, or page-builder content.

### 3. Prepare Media Library Evidence <a href="#id-3-prepare-media-library-evidence" id="id-3-prepare-media-library-evidence"></a>

WordPress media is not only a file count. Media records can be attached to posts, used as featured images, embedded in page content, referenced by galleries, reused across templates, or stored by plugins and page builders.

| Media evidence       | What to collect                                                                                      | Review purpose                                                             |
| -------------------- | ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Featured images      | Posts, pages, and custom records with featured images                                                | Confirms image relationships, not only stored files.                       |
| Inline media         | Pages and posts with embedded images, videos, documents, galleries, and downloads                    | Confirms rendered content remains readable.                                |
| Metadata             | Alt text, captions, descriptions, titles, and file names                                             | Supports accessibility, SEO, and content management.                       |
| URL-sensitive files  | Images or documents linked from old content, campaigns, or external pages                            | Helps identify broken media links or redirect needs.                       |
| Plugin-managed media | Media used by galleries, sliders, page builders, product plugins, LMS plugins, or membership content | Determines whether plugin-owned media references require special handling. |

### 4. Map Categories, Tags, Menus, and Navigation <a href="#id-4-map-categories-tags-menus-and-navigation" id="id-4-map-categories-tags-menus-and-navigation"></a>

WordPress discovery depends on more than page titles. Categories, tags, custom taxonomies, menus, archive pages, parent-child page structure, and theme templates can shape how users find content.

Prepare a navigation and taxonomy map that includes:

* post categories and tags;
* custom taxonomies and term relationships;
* page hierarchy and parent-child relationships;
* primary, footer, mobile, sidebar, or contextual menus;
* taxonomy archive URLs and important archive pages;
* custom post type archive behavior;
* content that appears through widgets, navigation blocks, theme areas, or page-builder modules.

### 5. Identify Custom Post Types, Custom Taxonomies, and Custom Fields <a href="#id-5-identify-custom-post-types-custom-taxonomies-and-custom-fields" id="id-5-identify-custom-post-types-custom-taxonomies-and-custom-fields"></a>

Many WordPress sites use custom structures to represent business data. These structures may come from plugins, custom code, theme functions, Advanced Custom Fields-style configurations, page builders, LMS plugins, event plugins, directory plugins, membership plugins, or bespoke applications.

Prepare a custom-data inventory before migration scope is confirmed.

| Custom structure            | Examples to identify                                                                                                            | Why it matters                                                                         |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Custom post types           | Portfolio items, events, courses, lessons, listings, testimonials, locations, downloads, products, forms, donations, or members | These records may not behave like ordinary posts or pages.                             |
| Custom taxonomies           | Event types, course categories, locations, brands, industries, product families, resource types                                 | Taxonomy relationships affect browsing, filtering, and templates.                      |
| Custom fields and post meta | Dates, prices, author bios, external IDs, related records, visibility flags, SEO fields, builder settings                       | Field meaning must be mapped, preserved, transformed, or excluded intentionally.       |
| Relationship fields         | Related posts, speaker-event links, course-lesson links, location listings, membership access rules                             | Relationship loss can make migrated records incomplete.                                |
| Custom tables               | Plugin or custom application tables outside standard WordPress posts and postmeta structures                                    | Custom tables are Custom Service review signals when they matter to the target result. |

### 6. Prepare Users, Roles, Authors, Members, and Account Meaning <a href="#id-6-prepare-users-roles-authors-members-and-account-meaning" id="id-6-prepare-users-roles-authors-members-and-account-meaning"></a>

WordPress user migration requires a clear distinction between core users and plugin-defined account types. An author, editor, subscriber, customer, member, learner, donor, or wholesale buyer may look like a user record but carry different operational meaning.

Prepare samples for:

* authors linked to posts and Blog Posts;
* administrators, editors, authors, contributors, subscribers, and custom roles;
* role and capability expectations;
* users associated with comments, memberships, courses, events, bookings, donations, commerce, or subscriptions;
* password policy expectations and post-migration account access planning;
* multisite user and role relationships if the target is a network.

### 7. Separate Plugin-Owned Business Data from WordPress Core Content <a href="#id-7-separate-plugin-owned-business-data-from-wordpress-core-content" id="id-7-separate-plugin-owned-business-data-from-wordpress-core-content"></a>

WordPress can support many business workflows, but those workflows are usually plugin-owned or custom-built. Preparation should identify which plugin data is inside migration scope, which data will be reconfigured manually, and which data belongs outside the standard target structures.

| Plugin or custom area         | Preparation questions                                                                                                 |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Commerce                      | Which plugin or custom structure defines products, customers, orders, checkout, payments, shipping, tax, and coupons? |
| Memberships and subscriptions | Which records define plans, access rules, renewals, members, content restrictions, and payment history?               |
| LMS and courses               | Which records define courses, lessons, quizzes, enrollments, progress, instructors, and certificates?                 |
| Events and bookings           | Which records define events, appointments, calendars, participants, tickets, locations, and capacity?                 |
| Forms and CRM                 | Which plugin stores submissions, leads, contact records, consent fields, notifications, or external CRM IDs?          |
| Donations and fundraising     | Which records define donors, campaigns, recurring donations, receipts, and payment references?                        |
| Multilingual content          | Which plugin defines translated content, language URLs, hreflang, translated terms, and menu variants?                |
| Page builders                 | Which pages use builder-specific layouts, shortcodes, templates, global widgets, or design metadata?                  |

### 8. Prepare SEO, URL, Redirect, and Domain Evidence <a href="#id-8-prepare-seo-url-redirect-and-domain-evidence" id="id-8-prepare-seo-url-redirect-and-domain-evidence"></a>

WordPress migration planning should protect search and referral continuity where URLs and metadata matter. Slugs, permalinks, category bases, taxonomy archives, author archives, media URLs, canonical rules, redirects, and SEO plugin fields should be reviewed before migration acceptance criteria are set.

Prepare the following:

* priority old URLs for posts, CMS Pages, Blog Posts, categories, tags, custom post types, and archives;
* target permalink structure and slug rules;
* redirects for changed URLs;
* SEO titles, meta descriptions, canonical values, index/noindex settings, and social metadata where managed by plugins;
* image alt text and media metadata;
* XML sitemap expectations;
* domain, subdomain, HTTPS, and trailing-slash behavior;
* multilingual URL patterns where a language plugin is used.

### 9. Prepare Theme, Template, Block, and Page-Builder Evidence <a href="#id-9-prepare-theme-template-block-and-page-builder-evidence" id="id-9-prepare-theme-template-block-and-page-builder-evidence"></a>

WordPress content often depends on how the target theme renders it. A migrated page can preserve text and still appear broken if the theme, template, page builder, block structure, or shortcode behavior changes.

Prepare review samples for:

| Rendering area            | Sample to prepare                                                                                       | What it helps confirm                                                                          |
| ------------------------- | ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Block editor content      | Pages and posts with blocks, columns, embeds, galleries, buttons, reusable patterns, and synced content | Confirms content remains editable and readable.                                                |
| Block theme / Site Editor | Templates, template parts, navigation, global styles, and patterns where used                           | Confirms design structure is not mistaken for migrated data.                                   |
| Classic theme             | Page templates, widget areas, sidebars, menus, and theme-specific fields                                | Confirms older theme behavior is understood.                                                   |
| Page builder              | Elementor, Divi, WPBakery, Beaver Builder, or other builder-driven pages                                | Shows whether layout data is preserved, excluded, rebuilt, or reviewed through Custom Service. |
| Shortcodes                | Pages or posts with shortcode output                                                                    | Identifies whether shortcode content remains meaningful after migration.                       |

### 10. Choose Demo Migration Samples Deliberately <a href="#id-10-choose-demo-migration-samples-deliberately" id="id-10-choose-demo-migration-samples-deliberately"></a>

Demo Migration samples should represent the records most likely to reveal migration complexity. A WordPress Demo Migration that only checks simple posts and pages may miss the actual risk in custom fields, plugin records, page builders, SEO, URLs, users, roles, and media relationships.

Include samples such as:

| Sample type         | Strong example                                                                                   |
| ------------------- | ------------------------------------------------------------------------------------------------ |
| Blog Post           | Published post with category, tags, author, comments, featured image, excerpt, and SEO metadata. |
| CMS Page            | Nested page with media, blocks, template selection, menu placement, and old URL priority.        |
| Media record        | Image or document used as featured media, inline content, gallery item, and downloadable file.   |
| Custom post type    | Record with custom fields, custom taxonomy terms, related records, and a dedicated template.     |
| User record         | Author or member with role, capability meaning, profile data, and content relationship.          |
| Plugin-owned record | Membership, event, booking, LMS, form, donation, or commerce record that affects operations.     |
| SEO/URL record      | Priority page or post with slug, redirect, metadata, canonical behavior, and sitemap relevance.  |
| Page-builder record | High-value landing page using builder-specific layout data or shortcode output.                  |

### 11. Identify Add-on and Custom Service Signals Early <a href="#id-11-identify-add-on-and-custom-service-signals-early" id="id-11-identify-add-on-and-custom-service-signals-early"></a>

Preparation should also reveal whether the migration can stay within standard service capability or needs additional planning.

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. They are useful when the requested adjustment fits supported Add-on capability, such as filtering selected eligible records, mapping supported fields, or modifying supported data values before migration.

Custom Service review is appropriate when the target WordPress result depends on custom post types, custom taxonomies, custom fields, custom tables, unsupported plugin data, page-builder conversion, custom migration logic adjustment, multilingual relationship mapping, SEO transformation, Custom Platform source handling, external identifiers, API-dependent data, or a plugin-specific business model outside standard service capability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

A WordPress migration should be prepared around the target implementation, not only around the number of records to move. WordPress can receive content, users, media, taxonomies, and page structures, but the final result depends heavily on themes, plugins, custom fields, custom post types, URLs, SEO rules, roles, and any business data created by plugins or custom code.

Before starting Demo Migration, prepare representative samples for the content and relationships that matter most: priority CMS Pages, Blog Posts, media, users, roles, custom post types, custom fields, plugin-owned records, page-builder layouts, URLs, redirects, and SEO metadata. If those samples reveal custom structures or plugin-specific dependencies, the migration approach should be reviewed before Full Migration begins.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first for a WordPress migration?**

Start with the target WordPress environment: version, hosting, theme type, plugin stack, multisite status, permalink structure, and content model. These choices determine whether source records can map cleanly into WordPress core structures or need plugin-specific or custom handling.

**Should WordPress plugin data be prepared separately?**

Yes. Plugin-owned data should be inventoried separately from WordPress core content. Memberships, forms, bookings, events, LMS records, donations, subscriptions, commerce records, SEO data, multilingual relationships, and page-builder layouts may require separate review.

**Why are custom post types and custom fields important before migration?**

Custom post types and custom fields often carry business meaning that ordinary posts and pages do not. If they are not identified early, the migration may preserve visible content while losing relationships, field values, templates, filtering behavior, or plugin-dependent meaning.

**What should be included in a WordPress Demo Migration sample?**

A strong sample should include more than simple posts and pages. Include CMS Pages, Blog Posts, media relationships, users, roles, comments, categories, tags, custom post types, custom fields, priority URLs, SEO metadata, page-builder pages, and any plugin-owned records that affect the target site.

**When does WordPress preparation point to Custom Service?**

Custom Service review is appropriate when the migration depends on custom post types, custom taxonomies, custom fields, custom tables, unsupported plugin records, page-builder conversion, multilingual relationship mapping, SEO transformation, API-dependent data, Custom Platform source handling, or custom migration logic adjustment.
