# WordPress Data Model Differences

WordPress data migration is not only a content-transfer exercise. WordPress organizes site information through a CMS model that can include posts, CMS Pages, Blog Posts, media attachments, categories, tags, comments, users, roles, menus, themes, templates, blocks, custom post types, custom taxonomies, metadata, plugin records, custom tables, and external integrations. A source record should therefore be judged by the role it must play in the target WordPress implementation, not only by whether its title and body can be moved.

The most important data-model difference is flexibility. WordPress can represent many structures, but it does not automatically decide whether a source record should become a page, post, custom post type entry, taxonomy term, media attachment, user, plugin record, reusable block, builder layout, or excluded record. That interpretation must be planned before migration, especially when the source site contains content libraries, events, courses, memberships, directories, forms, downloads, SEO metadata, or commerce-like records.

For WordPress, a successful migration preserves management meaning. Editors should understand where content lives. Users should retain the correct account meaning. URLs and media should remain usable. Plugin-owned records should not be mistaken for native CMS content. Custom structures should remain editable and searchable where that is part of the target expectation.

### WordPress Data Meaning Depends on the Target Content Model <a href="#wordpress-data-meaning-depends-on-the-target-content-model" id="wordpress-data-meaning-depends-on-the-target-content-model"></a>

WordPress has native content structures, but most serious WordPress sites extend them. The target content model decides whether migrated records remain easy to manage after launch. A source page may become a CMS Page, but it may also need a custom post type if it belongs to a resource library, event archive, staff directory, course catalog, documentation hub, or listing system.

The first WordPress data-model decision is ownership: which layer should own the record after migration?

| Source record question                     | WordPress interpretation                                                                             | Migration decision it controls                                                                  |
| ------------------------------------------ | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Is the record stable site content?         | CMS Page, parent/child page, template-backed page, landing page, or reusable block.                  | Page hierarchy, layout review, media relationships, redirects, and SEO metadata.                |
| Is the record editorial content?           | Blog Post with author, date, category, tag, excerpt, featured media, comments, and archive behavior. | Publishing history, topic archives, authorship, comments, and blog URL continuity.              |
| Is the record a structured content entry?  | Custom post type with custom fields, custom taxonomies, archives, and templates.                     | Target content model, field mapping, archive behavior, filters, and editor workflow.            |
| Is the record classification data?         | Category, tag, custom taxonomy, plugin taxonomy, menu item, or search filter.                        | Whether grouping affects navigation, archives, filtering, SEO, or plugin behavior.              |
| Is the record operational or plugin-owned? | Plugin record, custom table, user metadata, integration reference, or Custom Service scope.          | Whether standard migration is enough, Add-ons are relevant, or Custom Service review is needed. |

The migration should not flatten all source content into ordinary pages. Flat migration may preserve text but lose the reason records existed as separate content types, topics, filters, archives, or workflow objects.

### Core WordPress Records Are Only the Baseline <a href="#core-wordpress-records-are-only-the-baseline" id="core-wordpress-records-are-only-the-baseline"></a>

Core WordPress records provide the clearest migration baseline. They include pages, posts, media, users, comments, categories, tags, and menus. These records are often easier to identify than plugin or custom records, but they still carry relationships that must be preserved.

| WordPress record | Migration meaning                                                                                                      | What to review                                                                                                             |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| CMS Pages        | Stable site content such as service pages, policy pages, landing pages, brand pages, and information pages.            | Slug, hierarchy, parent page, template, internal links, media, SEO fields, menu placement, and redirect needs.             |
| Blog Posts       | Editorial records with author, date, categories, tags, comments, featured image, excerpt, and archive behavior.        | Publishing history, authorship, taxonomy assignments, comments, featured media, post status, and permalink pattern.        |
| Media            | Images, files, PDFs, downloads, galleries, featured images, captions, alt text, and attachment relationships.          | Whether media remains attached to pages, posts, galleries, custom fields, downloadable resources, and SEO-sensitive paths. |
| Users            | Accounts with usernames, email addresses, display names, roles, capabilities, metadata, authorship, or plugin meaning. | Whether each user is an author, editor, member, subscriber, customer, learner, donor, vendor, or administrator.            |
| Comments         | Comment records linked to posts, pages, custom content, or plugin-owned interaction systems.                           | Whether source comments are blog comments, product reviews, discussions, testimonials, Q\&A, or excluded interactions.     |
| Menus            | Navigation labels, links, hierarchy, page references, taxonomy archives, and custom URLs.                              | Whether navigation should become WordPress menus, page hierarchy, redirects, or theme-controlled navigation.               |

These native records are usually the safest starting point, but they are not the full WordPress data model. A target site that depends on plugins, builders, field groups, memberships, courses, events, directories, or commerce structures needs a deeper data review.

### CMS Pages and Blog Posts Should Not Be Interchangeable <a href="#cms-pages-and-blog-posts-should-not-be-interchangeable" id="cms-pages-and-blog-posts-should-not-be-interchangeable"></a>

CMS Pages and Blog Posts may look similar in an export, but they behave differently inside WordPress. CMS Pages usually represent stable content. Blog Posts usually preserve editorial chronology, authorship, topics, archive pages, comments, and publication signals.

| Source content pattern                                  | Better WordPress destination                                                      | Risk if mapped incorrectly                                                               |
| ------------------------------------------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| About, contact, policy, service, brand, or landing page | CMS Page with hierarchy, template, menu, media, and SEO review.                   | Page exists but loses hierarchy, internal links, layout context, or conversion sections. |
| News, article, update, announcement, or editorial post  | Blog Post with author, date, category, tag, featured image, and archive behavior. | Editorial history is flattened into pages and becomes harder to browse or manage.        |
| Knowledge base or help content                          | Blog Post, CMS Page, or custom post type depending on search and archive needs.   | Support content moves but loses navigation, filters, or related-content behavior.        |
| Resource library item                                   | Custom post type or Blog Post depending on target browsing model.                 | Records lose filters, relationships, or reusable presentation patterns.                  |
| Campaign page with form or tracking                     | CMS Page plus target-side form, tracking, template, or builder review.            | Visible text migrates while the business function disappears.                            |

The destination should reflect the editorial job of the record. If content needs archives, topics, date-based browsing, author pages, or feeds, Blog Posts may be appropriate. If content needs stable navigation, parent-child hierarchy, or fixed landing-page behavior, CMS Pages may be better. If content needs custom fields, filters, relationships, or a specialized archive, a custom post type may be the right target.

### Custom Post Types and Custom Taxonomies Carry Structured Meaning <a href="#custom-post-types-and-custom-taxonomies-carry-structured-meaning" id="custom-post-types-and-custom-taxonomies-carry-structured-meaning"></a>

Custom post types and custom taxonomies are common in WordPress because they let a site model content beyond ordinary posts and pages. They can represent events, properties, courses, lessons, staff profiles, locations, jobs, testimonials, documentation, resources, directories, portfolios, case studies, vendors, or product-like records.

A custom post type is not valuable merely because it exists. It becomes valuable when its fields, taxonomies, archive pages, templates, filters, editing workflow, and relationships are preserved or rebuilt in the target site.

| Source structure                         | Possible WordPress model                                                                      | Migration requirement                                                                             |
| ---------------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Events                                   | Custom post type with dates, venues, organizers, registration links, and event categories.    | Confirm date fields, recurring logic, status, archive behavior, and plugin ownership.             |
| Courses or lessons                       | LMS plugin records, custom post types, lesson hierarchy, enrollment links, and user progress. | Separate public content from enrollment, progress, quizzes, certificates, and user relationships. |
| Properties or listings                   | Custom post type with location fields, galleries, taxonomies, map data, and search filters.   | Confirm fields, filters, map/location data, templates, and lead-routing behavior.                 |
| Staff, authors, partners, or vendors     | Custom post type, user record, taxonomy, directory entry, or external profile.                | Decide whether the person is content, account, author, vendor, or connected-system record.        |
| Documentation or resources               | Custom post type, Blog Post, CMS Page, taxonomy archive, or search-driven resource model.     | Preserve hierarchy, topics, internal links, downloadable media, and archive behavior.             |
| Product-like content without WooCommerce | Custom post type, catalog plugin record, commerce plugin record, or custom structure.         | Do not assume WordPress core owns product behavior. Confirm the target model first.               |

Custom taxonomies deserve the same care. A source category may become a WordPress category, tag, custom taxonomy, menu item, filter, WooCommerce product taxonomy, plugin-owned grouping, or excluded record. The decision depends on whether the grouping controls editorial discovery, filtering, navigation, SEO archives, product browsing, or internal administration.

### Metadata and Custom Fields Can Decide Whether Data Is Usable <a href="#metadata-and-custom-fields-can-decide-whether-data-is-usable" id="metadata-and-custom-fields-can-decide-whether-data-is-usable"></a>

WordPress metadata can store values for posts, pages, users, media, terms, and plugin records. Custom fields may control layout, SEO, filters, relationships, downloads, access rules, membership status, lead routing, or external-system references. Migrating the visible body content without the relevant metadata can make the target site look populated but unusable.

| Metadata type        | How it may affect WordPress                                                                                                  | Migration implication                                                                                           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| SEO fields           | Titles, meta descriptions, canonical values, schema fields, social previews, breadcrumbs, redirects, or indexation settings. | Verify where the source stores SEO data and whether target plugin fields are supported or need another path.    |
| Field groups         | Structured values for events, resources, profiles, listings, downloads, locations, authors, or custom templates.             | Confirm field names, types, repeaters, relationships, display templates, and editor visibility.                 |
| Builder metadata     | Layout sections, columns, nested blocks, shortcodes, global modules, or reusable content.                                    | Decide whether the layout migrates, is rebuilt, is simplified, or is accepted as different.                     |
| User metadata        | Membership status, profile fields, preferences, author info, learning progress, donor history, or CRM links.                 | Decide whether the user is a core WordPress user, plugin user, external contact, or Custom Service requirement. |
| External identifiers | CRM IDs, LMS IDs, donation IDs, booking IDs, analytics references, or integration keys.                                      | Preserve only when they have a defined business use after migration.                                            |
| Plugin settings      | Configuration for forms, memberships, SEO, events, redirects, media, or custom workflows.                                    | Treat as plugin setup, Custom Service review, or excluded behavior depending on support.                        |

Metadata should be reviewed through use cases. If a field only existed for an abandoned design, it may not need migration. If a field controls filtering, SEO, permissions, downloads, or connected-system matching, it may be central to the scope.

### Media and Attachments Need Relationship Review <a href="#media-and-attachments-need-relationship-review" id="media-and-attachments-need-relationship-review"></a>

WordPress treats media as records with their own metadata and relationships. Images, PDFs, videos, downloadable files, and embedded assets may appear in page content, featured images, galleries, custom fields, reusable blocks, product-like records, SEO metadata, or plugin records. Moving files alone does not prove that the media layer works.

| Media scenario        | What can fail                                                                                | What should be validated                                                           |
| --------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Featured images       | Image files exist but are not linked to posts, pages, or custom post types.                  | Priority content samples show correct featured media.                              |
| Galleries             | Gallery structure is flattened, broken, or detached from the intended page.                  | Galleries display correctly and keep captions, ordering, and links where required. |
| Downloads             | PDF or file links break, change paths, or lose access rules.                                 | Download URLs, permissions, and related content samples are checked.               |
| Image metadata        | Alt text, captions, titles, or descriptions are lost or mismatched.                          | Accessibility and SEO-sensitive media fields are verified.                         |
| Builder/media modules | Media exists but builder sections cannot render it correctly.                                | Priority page layouts are visually reviewed.                                       |
| External media        | Embedded videos, CDN assets, or externally hosted files are not part of the migration scope. | External dependencies are listed and accepted, reconnected, or rebuilt.            |

Media validation is especially important for content-heavy WordPress sites because broken images and file links can damage credibility even when page text is intact.

### Users, Roles, and Account Meaning Require Interpretation <a href="#users-roles-and-account-meaning-require-interpretation" id="users-roles-and-account-meaning-require-interpretation"></a>

A WordPress user is not always the same thing as a customer, member, author, learner, donor, vendor, staff account, or subscriber. WordPress roles and capabilities control privileges, and plugins can add their own roles, account meanings, profile fields, permissions, and workflows.

| Source account type           | Possible WordPress meaning                                                                       | Planning question                                                                     |
| ----------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Blog author or editor         | WordPress user with author/editor role and post ownership.                                       | Should authorship and publishing history be preserved?                                |
| Newsletter subscriber         | Plugin contact, email platform record, subscriber role, or excluded marketing record.            | Does the target WordPress site own this contact, or does an external platform own it? |
| Membership account            | WordPress user plus membership plugin data, access rules, subscriptions, and user metadata.      | Which fields control access, billing, renewal, and protected content?                 |
| Course learner                | LMS user, enrollment record, progress data, quiz result, or certificate record.                  | Which learner records are supported, excluded, rebuilt, or Custom Service scope?      |
| Customer account              | WooCommerce customer, another commerce plugin customer, external CRM contact, or WordPress user. | Is commerce part of the target scope, and which plugin owns the account meaning?      |
| Vendor or marketplace account | User role, plugin vendor record, custom profile, or external-system record.                      | Does the target platform support vendor behavior, or is Custom Service needed?        |

The safest approach is to classify users by business purpose, not only by email address. Otherwise, a migration may create user records while losing the permissions, relationships, or plugin-owned records that made those accounts useful.

### Plugins, Builders, and Custom Tables Need Scope Separation <a href="#plugins-builders-and-custom-tables-need-scope-separation" id="plugins-builders-and-custom-tables-need-scope-separation"></a>

WordPress plugin and builder ecosystems are powerful, but they complicate migration. A source WordPress site may store form submissions, events, courses, memberships, directories, redirects, SEO fields, booking records, donations, field groups, page layouts, or automation settings in plugin tables or metadata. A non-WordPress source may contain equivalent structures that need a target plugin or custom model.

| Dependency                          | What it may own                                                                                             | Better scope decision                                                                       |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Page builder                        | Layout sections, nested modules, shortcodes, global blocks, templates, or styling references.               | Decide whether layouts migrate, are rebuilt, are simplified, or are manually implemented.   |
| SEO plugin                          | Metadata, canonical values, redirects, schema settings, breadcrumbs, sitemap settings, and social previews. | Map priority SEO fields only where supported and validate important URL samples.            |
| Form plugin                         | Forms, fields, submissions, notifications, integrations, and CRM links.                                     | Separate form structure, historical submissions, and email/integration workflows.           |
| Membership or LMS plugin            | Access rules, enrollments, progress, roles, subscriptions, certificates, and protected content.             | Treat plugin behavior and user relationships as special scope, not ordinary user migration. |
| Event, booking, or directory plugin | Custom post types, custom fields, schedules, locations, filters, payments, and notifications.               | Confirm target plugin model and decide whether Custom Service review is needed.             |
| Custom tables                       | Bespoke records, relationships, settings, histories, or integration references.                             | Treat as Custom Service review unless a supported path is clearly confirmed.                |

Add-ons can help when the requirement is supported and bounded, such as filtering records, adjusting supported field mapping, or configuring supported output. Custom Service should be considered when the requirement involves unsupported plugin data, custom tables, bespoke field transformation, external IDs, Custom Platform handling, or custom migration logic adjustment.

### URLs, Permalinks, and SEO Data Are Part of the Data Model <a href="#urls-permalinks-and-seo-data-are-part-of-the-data-model" id="urls-permalinks-and-seo-data-are-part-of-the-data-model"></a>

WordPress data meaning includes routing. A page slug, post permalink, taxonomy archive, media path, redirect, canonical value, or internal link can be as important as the content body. This is especially true when the source site has search traffic, backlinks, resource libraries, blog archives, or structured content sections.

| URL or SEO element   | WordPress data relationship                                                     | Migration decision                                                              |
| -------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| CMS Page slug        | Page URL, hierarchy, menu, redirects, and internal links.                       | Preserve slug where possible or redirect from the old path.                     |
| Blog Post permalink  | Post slug plus date/category permalink structure if used.                       | Decide whether old post paths need exact preservation or redirects.             |
| Taxonomy archive     | Category, tag, or custom taxonomy URL.                                          | Determine whether archive pages should exist, redirect, or be excluded.         |
| Custom post type URL | Single-record and archive URLs for resources, events, listings, or directories. | Confirm target post type slug, archive slug, and redirect plan.                 |
| Media URL            | File path, attachment page, embedded image, downloadable PDF, or external file. | Validate files, links, attachment references, and media redirects where needed. |
| SEO plugin data      | Metadata, canonical fields, schema settings, redirects, and social previews.    | Decide which fields are supported, mapped, rebuilt, or excluded.                |

A migration plan should not wait until after launch to review WordPress URL behavior. The target content model and permalink structure determine which redirects and SEO fields will matter.

### WordPress Data Scope Should End With Usability Decisions <a href="#wordpress-data-scope-should-end-with-usability-decisions" id="wordpress-data-scope-should-end-with-usability-decisions"></a>

The final WordPress data-model question is whether the migrated result will be manageable. Editors, administrators, SEO teams, developers, and external-system owners may all need different proof. A record can exist in WordPress and still fail if it cannot be edited through the right interface, filtered in the right archive, displayed by the target template, linked to the right media, or matched with the right external system.

| Data area                 | Usability question                                                                                            |
| ------------------------- | ------------------------------------------------------------------------------------------------------------- |
| CMS Pages and Blog Posts  | Can editors manage the content, hierarchy, media, status, and SEO fields without relying on the old platform? |
| Custom post types         | Do structured records have the correct fields, taxonomies, archives, and templates?                           |
| Taxonomies                | Do categories, tags, and custom taxonomies support browsing, filtering, internal links, and SEO expectations? |
| Users and roles           | Do users retain the meaning needed for authorship, access, membership, editing, or plugin behavior?           |
| Metadata                  | Are important fields visible, usable, and connected to display or filtering where required?                   |
| Plugins and custom tables | Is unsupported or custom data classified as Add-ons, Custom Service, target setup, or exclusion?              |
| URLs and SEO              | Are priority paths, redirects, internal links, metadata, and archive URLs accounted for?                      |

Entity Points may help plan selected entity volume where eligible records are part of the migration scope, but they do not prove that every WordPress field, plugin record, or custom relationship can migrate. WordPress scope should be accepted only when the team can explain which records are supported, which need Add-ons, which need Custom Service, which require target-side setup, and which are intentionally excluded.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress data model differences matter because the platform separates content, classification, media, users, metadata, presentation, plugin behavior, and routing across multiple layers. A source record should be interpreted according to what it must become in the target WordPress implementation: CMS Page, Blog Post, custom post type, taxonomy term, media attachment, user, plugin record, custom table, redirect, metadata field, or excluded expectation.

A strong WordPress migration plan preserves management meaning, not just visible content. It defines the target content model, separates WordPress core from plugin and custom structures, protects media and URL relationships, classifies users by account meaning, and assigns unsupported or bespoke requirements to Add-ons, Custom Service, target setup, or exclusion before migration approval.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are WordPress custom post types the same as CMS Pages?**

No. CMS Pages are native WordPress content records for stable site pages. Custom post types are structured content models that can represent resources, events, courses, listings, portfolios, directories, or other content types with their own fields, taxonomies, archives, and templates.

**Can all source categories become WordPress categories?**

No. Some source groupings should become categories or tags, but others may need custom taxonomies, menus, plugin filters, WooCommerce taxonomies, redirects, or exclusions depending on how they control browsing and management.

**Why are custom fields important in WordPress migration?**

Custom fields can control layout, SEO, filtering, relationships, permissions, downloads, external IDs, and plugin behavior. Migrating visible page content without important custom fields can make the target site incomplete or difficult to manage.

**Should WooCommerce products be treated as ordinary WordPress content?**

No. WooCommerce products belong to the WooCommerce commerce layer inside WordPress. They require commerce-specific review for product types, variations, attributes, pricing, stock, orders, checkout, tax, shipping, coupons, and payment context.

**When does WordPress data require Custom Service review?**

Custom Service should be considered when the scope involves unsupported plugin records, custom tables, bespoke fields, external-system identifiers, complex user relationships, Custom Platform handling, or migration logic beyond supported behavior.
