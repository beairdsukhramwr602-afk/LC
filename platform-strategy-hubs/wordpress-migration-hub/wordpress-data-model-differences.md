# WordPress Data Model Differences

WordPress is a flexible content management and application foundation. A migration into WordPress should therefore be planned around how each source record becomes meaningful inside WordPress, not only whether a record can be copied into a table or displayed on a page.

The most important difference is that WordPress does not treat every migrated item as a single fixed commerce object. Standard WordPress content uses posts, CMS Pages, media, comments, users, taxonomies, menus, themes, and block content. More specialized behavior may depend on custom post types, custom taxonomies, custom fields, plugins, page builders, theme logic, or custom code. Commerce meaning depends on the commerce plugin or custom implementation used on the target WordPress site.

### How WordPress Interprets Migrated Data <a href="#how-wordpress-interprets-migrated-data" id="how-wordpress-interprets-migrated-data"></a>

WordPress organizes content around flexible content objects and relationships. The same source record may become a standard post, a CMS Page, a media item, a taxonomy term, a user, a menu item, a custom post type entry, a custom field value, or plugin-owned data.

| Source-store meaning                               | Possible WordPress interpretation                                                                          | Migration planning concern                                                                                                    |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Informational page                                 | CMS Page, block content, page-builder layout, template-controlled page, or custom post type                | Page content and visual layout may not mean the same thing unless the target editor, theme, and page-builder model are clear. |
| Blog article                                       | Blog Post with categories, tags, author, publish date, comments, media, and SEO metadata                   | Post history should preserve editorial meaning, not only title and body text.                                                 |
| Product or service record                          | Plugin-owned commerce record, custom post type, custom field group, or custom implementation data          | WordPress alone does not define native product behavior; the target commerce or business plugin determines meaning.           |
| Category or collection                             | Category, tag, custom taxonomy, menu structure, plugin taxonomy, or navigation grouping                    | Source grouping should be mapped to the structure that controls discovery in the target site.                                 |
| Customer or account                                | WordPress user, plugin customer record, member profile, CRM/contact record, or custom user metadata        | Login, membership, commerce, subscription, and customer-service meaning may live in different target structures.              |
| Image or file                                      | Media Library item, featured image, embedded media, gallery image, downloadable file, or plugin attachment | Media continuity depends on file availability, attachment relationships, alt text, captions, and display context.             |
| Custom field                                       | WordPress post meta, user meta, term meta, plugin field, advanced custom field, or custom table value      | Custom fields need meaning-level review because values may be invisible unless the target theme or plugin uses them.          |
| Checkout, booking, course, donation, or event data | Plugin-owned records, custom post types, custom tables, user metadata, or external-system references       | Business behavior is plugin-dependent and should not be treated as native WordPress content.                                  |

### Posts, CMS Pages, and Blog Posts <a href="#posts-cms-pages-and-blog-posts" id="posts-cms-pages-and-blog-posts"></a>

WordPress distinguishes between CMS Pages and Blog Posts, but real-world source stores often use page-like content, blog content, landing pages, product descriptions, help articles, brand pages, and campaign pages in overlapping ways. A migration should decide whether each source content type belongs as a CMS Page, Blog Post, custom post type, block pattern, page-builder layout, or plugin-managed entry.

CMS Pages usually represent stable site content such as about pages, policy pages, contact pages, brand pages, and landing pages. Blog Posts usually represent dated editorial content with authors, categories, tags, archives, comments, and publication history. If the source platform uses content structures that do not match this distinction, the migration should preserve the reader-facing meaning rather than forcing every item into the closest visible page type.

### Block Content, Page Builders, and Layout Meaning <a href="#block-content-page-builders-and-layout-meaning" id="block-content-page-builders-and-layout-meaning"></a>

Modern WordPress sites often use block editor content, block themes, Site Editor structures, reusable patterns, page templates, or page builders. These layers affect how migrated content appears and how site managers edit it after launch.

A paragraph, gallery, product block, hero section, form, button, tab, accordion, or embedded widget may look like ordinary page content in the source store but become a block, shortcode, page-builder element, plugin embed, or static HTML segment in WordPress. Migration planning should distinguish content value from layout behavior.

| Content layer            | Why it matters in WordPress                                                                                           |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| Raw text and HTML        | Text can often move, but source-specific markup may not remain clean or editable.                                     |
| Blocks                   | Block content can preserve editing flexibility when the target structure supports it.                                 |
| Page-builder layouts     | Builder-specific rows, sections, widgets, and shortcodes may require compatible target tooling.                       |
| Theme templates          | Some page structure is controlled by theme templates rather than the migrated record itself.                          |
| Reusable design elements | Headers, footers, product sections, forms, calls to action, and menus may need target setup outside record migration. |

### Media, Attachments, and File Relationships <a href="#media-attachments-and-file-relationships" id="media-attachments-and-file-relationships"></a>

WordPress stores images and files in the Media Library and connects them to posts, pages, featured images, galleries, blocks, downloads, and plugin records. A successful media migration should preserve both the files and the relationships that make them useful.

Important media relationships include featured images, embedded images, gallery order, alt text, captions, file names, downloadable files, product images where a commerce plugin is involved, and media used inside page-builder content. A record may appear complete in the admin area but still fail from a customer perspective if images are detached, missing, duplicated, or no longer used by the target layout.

### Categories, Tags, Menus, and Custom Taxonomies <a href="#categories-tags-menus-and-custom-taxonomies" id="categories-tags-menus-and-custom-taxonomies"></a>

WordPress uses categories and tags for Blog Posts by default, but it also supports custom taxonomies for specialized content. Menus and navigation are separate from taxonomy terms, even when they use the same labels.

Source categories, collections, departments, brands, product types, article topics, resource types, or landing-page groupings may need different target handling. Some should become standard categories or tags. Others may belong as custom taxonomies, menu items, plugin taxonomies, or page hierarchy.

The key question is what the grouping controls after migration. If it controls editorial archives, use a content taxonomy. If it controls storefront discovery, review the commerce plugin or catalog structure. If it controls navigation, review menus and site structure. If it controls filtering, the target plugin, theme, or search layer may need additional configuration.

### Users, Roles, Members, and Customer Meaning <a href="#users-roles-members-and-customer-meaning" id="users-roles-members-and-customer-meaning"></a>

WordPress users can carry usernames, emails, roles, passwords, profile fields, capabilities, and metadata. However, customer, member, subscriber, author, administrator, student, donor, or wholesale account meaning may depend on plugins or custom fields.

A source customer is not always just a WordPress user. The target meaning may require a user account, plugin customer profile, member record, subscription relationship, order relationship, course enrollment, booking profile, donor history, CRM contact, or custom metadata. This distinction matters for login, permissions, customer service, segmentation, and post-launch management.

Password continuity also depends on platform compatibility and security handling. If passwords cannot be preserved directly, the migration plan should account for password reset or account activation expectations rather than treating user records as fully complete.

### Custom Post Types and Custom Fields <a href="#custom-post-types-and-custom-fields" id="custom-post-types-and-custom-fields"></a>

Custom post types and custom fields are central to many WordPress implementations. They allow WordPress to represent content beyond ordinary posts and pages, such as products, properties, events, portfolios, courses, testimonials, locations, team members, forms, downloads, or directories.

A source record should be mapped to a custom post type only when that structure exists and is intended for the target site. Custom fields should be reviewed for display, editing, filtering, search, and integration meaning. A migrated custom field can exist in WordPress without being visible, searchable, editable in the expected interface, or used by the target theme.

Custom fields are especially important when source data includes product attributes, technical specifications, event dates, booking rules, memberships, recurring charges, external IDs, inventory references, vendor information, or integration keys.

### Plugin-Owned Data and Commerce Dependencies <a href="#plugin-owned-data-and-commerce-dependencies" id="plugin-owned-data-and-commerce-dependencies"></a>

WordPress does not provide native e-commerce behavior by itself. Products, carts, checkout, customer commerce profiles, subscriptions, bookings, courses, events, donations, memberships, loyalty data, and other business objects usually depend on plugins or custom implementations.

This makes plugin ownership a major data-model difference. A product in the source platform may need to become a record owned by a commerce plugin. A booking may belong to a booking plugin. A membership may belong to a membership plugin. A course enrollment may belong to a learning-management plugin. A donation may belong to a donation plugin.

When plugin-owned data is involved, the migration should confirm whether the target plugin supports the needed fields, relationships, statuses, and workflows. Unsupported plugin data, custom plugin tables, or bespoke business logic belong in Custom Service review.

### SEO, Slugs, Redirects, and URL Meaning <a href="#seo-slugs-redirects-and-url-meaning" id="seo-slugs-redirects-and-url-meaning"></a>

WordPress separates content identity from final URL behavior. Slugs, permalinks, categories, parent pages, custom post type archives, theme routing, plugin routing, SEO plugins, redirects, and server configuration can all affect the final address and search meaning of a migrated record.

A source URL should not be treated as automatically preserved simply because a page, post, or product exists in WordPress. SEO-sensitive migrations should review page slugs, post slugs, taxonomy slugs, media URLs, canonical behavior, metadata, redirect rules, internal links, and high-value landing paths.

SEO metadata may also live in plugin-specific fields. If the target uses a different SEO plugin or no equivalent plugin, titles, descriptions, schema settings, index rules, canonical values, and social preview data may require mapping, configuration, or accepted exclusions.

### Comments, Reviews, Forms, and Interaction Data <a href="#comments-reviews-forms-and-interaction-data" id="comments-reviews-forms-and-interaction-data"></a>

WordPress supports comments, but review, form, rating, survey, discussion, and customer-interaction data often depends on plugins. Source comments may become WordPress comments when the target content model supports them. Product reviews, testimonials, form submissions, lead records, and Q\&A data may belong elsewhere.

Interaction data should be reviewed by use case. A blog comment, product review, contact-form submission, support inquiry, and membership discussion may all look similar as user-generated content, but they serve different operational purposes after migration.

### External IDs, APIs, and Integration Meaning <a href="#external-ids-apis-and-integration-meaning" id="external-ids-apis-and-integration-meaning"></a>

Many WordPress sites connect to external systems such as CRMs, email platforms, payment providers, analytics tools, learning platforms, booking engines, donation systems, fulfillment services, ERPs, or custom APIs. These connections may depend on stable IDs, metadata, webhooks, tags, tokens, or custom fields.

Migrating the visible WordPress record is not enough when external systems use hidden identifiers or plugin metadata. External IDs should be identified early when they affect reporting, automation, customer segmentation, fulfillment, account matching, or historical continuity.

### What the Migrated Data Must Prove <a href="#what-the-migrated-data-must-prove" id="what-the-migrated-data-must-prove"></a>

A WordPress migration result should prove that each data type works in the target structure where people will actually use it. The test is not just whether records exist. The migrated site should show that content can be found, edited, displayed, filtered, linked, indexed, and managed in the target WordPress implementation.

Strong validation samples should include CMS Pages, Blog Posts, media-heavy content, custom post types, custom fields, users, roles, menus, categories, tags, plugin-owned records, SEO-sensitive URLs, page-builder content, and any commerce or business data controlled by target plugins.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress data model differences come from its flexibility. The same source-store record may become a post, CMS Page, media item, taxonomy term, user, custom post type, custom field, plugin-owned record, menu item, or external-system reference. A successful migration depends on choosing the right target meaning for each record type.

Before approving a WordPress migration plan, review which data belongs to WordPress core, which belongs to themes, which belongs to plugins, which belongs to custom fields or custom post types, and which belongs to external systems. Use Demo Migration results to confirm whether the target site preserves the business and editorial meaning of the source data before moving into Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Does WordPress treat products as native data?**

No. WordPress does not provide native product, cart, checkout, or order behavior by itself. Product and commerce meaning depends on the commerce plugin or custom implementation used on the target WordPress site.

**Are WordPress CMS Pages and Blog Posts the same thing?**

No. CMS Pages usually represent stable site content, while Blog Posts usually carry publication dates, authors, categories, tags, archives, and editorial history. Source content should be mapped by how it should be managed and displayed after migration.

**Can custom fields migrate into WordPress?**

Custom fields can be part of a WordPress migration when the target structure supports them. The important question is whether the migrated fields are visible, editable, searchable, and used by the theme, plugin, or custom logic that controls the target site.

**What happens to page-builder content during a WordPress migration?**

Page-builder content should be reviewed carefully because layout elements may depend on builder-specific structures, widgets, shortcodes, or theme behavior. Some content may migrate as editable blocks, while other content may require compatible tooling, rebuilding, or accepted layout changes.

**Why are plugins important in WordPress data migration?**

Plugins can define products, bookings, memberships, donations, forms, courses, events, SEO metadata, reviews, custom fields, and integration data. When important records belong to plugins, migration planning should confirm whether those structures are supported, need mapping, or require Custom Service review.
