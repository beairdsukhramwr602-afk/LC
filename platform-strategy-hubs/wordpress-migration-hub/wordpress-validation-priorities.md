# WordPress Validation Priorities

WordPress validation should prove that migrated records are usable inside the target implementation, not only present in the database. A page title, post body, or media file can exist while the layout, taxonomy, custom field, plugin behavior, redirect, user role, or SEO output is still incomplete.

The validation priority is to test representative business meaning. WordPress content should remain editable, discoverable, linked, permission-aware, and visible through the intended theme, builder, plugin, and URL structure after Demo Migration and Full Migration.

### WordPress Validation Layers <a href="#wordpress-validation-layers" id="wordpress-validation-layers"></a>

| Validation layer       | What to validate                                                                                           | Why it matters                                                                           |
| ---------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Core CMS content       | CMS Pages, Blog Posts, media, comments, categories, tags, authors, and menus.                              | Confirms the baseline WordPress migration is complete and editorially usable.            |
| Custom structures      | Custom post types, custom taxonomies, custom fields, relationships, archives, and templates.               | Confirms structured content was not flattened into ordinary pages.                       |
| Presentation           | Blocks, page builders, shortcodes, widgets, templates, theme output, and media display.                    | Confirms visible pages render correctly after migration.                                 |
| Plugin and custom data | Forms, memberships, LMS, bookings, events, directories, donations, custom tables, and integration records. | Confirms business data is either migrated, excluded, or routed to Custom Service review. |
| SEO and routing        | Slugs, permalinks, redirects, canonical values, metadata, internal links, and media URLs.                  | Protects search visibility and user navigation.                                          |
| Users and access       | Authors, editors, members, subscribers, learners, donors, customers, roles, and capabilities.              | Confirms account meaning and permissions survive migration.                              |

### Core Content Validation <a href="#core-content-validation" id="core-content-validation"></a>

| Sample type | What to check                                                                                                 | Pass condition                                                                            |
| ----------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| CMS Pages   | Title, slug, content, hierarchy, template, featured media, menu position, internal links, and status.         | Priority pages are editable, accessible, correctly linked, and visually acceptable.       |
| Blog Posts  | Title, author, date, categories, tags, excerpt, comments, featured media, slug, and archive behavior.         | Blog history remains browsable, attributable, and discoverable.                           |
| Media       | Files, filenames, alt text, captions, descriptions, featured image references, galleries, and download links. | Media remains attached to the right records and visible where expected.                   |
| Comments    | Author, date, status, nesting, related content, and moderation state.                                         | Comment history appears only where expected and remains connected to the correct content. |
| Menus       | Labels, hierarchy, custom URLs, page references, taxonomy links, and menu locations.                          | Navigation points to valid target URLs and reflects approved structure.                   |

### Custom Post Type and Taxonomy Validation <a href="#custom-post-type-and-taxonomy-validation" id="custom-post-type-and-taxonomy-validation"></a>

Custom post types and custom taxonomies should be validated through real examples, not only record counts. Events, courses, listings, directories, resources, staff, locations, portfolios, jobs, or documentation entries must behave as the target WordPress model intends.

| Structure                 | Validation priority                                                                                | Pass condition                                                                         |
| ------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Custom post types         | Record type, title, slug, fields, status, media, relationships, archive behavior, and edit screen. | Records appear in the correct admin section and render through the expected templates. |
| Custom taxonomies         | Terms, hierarchy, assignments, archive pages, filters, and URL paths.                              | Grouping and browsing behavior match the target model.                                 |
| Relationship fields       | Related people, resources, locations, downloads, events, or categories.                            | Relationships remain connected in both admin and front-end output.                     |
| Archive and listing pages | Sort order, filters, pagination, excerpts, images, and template output.                            | Users can browse structured content without broken filters or missing fields.          |

### Metadata, Fields, and Plugin Data Validation <a href="#metadata-fields-and-plugin-data-validation" id="metadata-fields-and-plugin-data-validation"></a>

| Data area        | What to validate                                                                                        | Pass condition                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Custom fields    | Field names, values, field types, repeaters, relationships, display behavior, and editability.          | Fields are present and used by the target templates or plugins as intended.                           |
| SEO fields       | SEO title, description, canonical value, index settings, schema data, breadcrumbs, and social metadata. | Priority content has approved metadata and search-sensitive values.                                   |
| Builder metadata | Builder sections, modules, blocks, reusable layouts, shortcodes, and embedded assets.                   | Important pages render acceptably and unsupported builder data is known.                              |
| Plugin records   | Forms, submissions, courses, bookings, memberships, events, donations, directories, and custom tables.  | Plugin-owned data is migrated, excluded, or scoped for Custom Service with clear acceptance criteria. |
| External IDs     | CRM, LMS, ERP, PIM, booking, membership, analytics, or middleware identifiers.                          | Required references are preserved or explicitly replaced by the target operating process.             |

### User, Role, and Account Validation <a href="#user-role-and-account-validation" id="user-role-and-account-validation"></a>

WordPress users can represent different business meanings. A user may be an author, editor, administrator, member, learner, donor, subscriber, vendor, customer, or plugin-controlled account. Validation should test more than login fields.

| Account type                                    | Validation priority                                                          | Pass condition                                                                                      |
| ----------------------------------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Authors and editors                             | Authorship, display name, author archives, and permissions.                  | Content attribution and editorial access are correct.                                               |
| Members or subscribers                          | Role, membership status, profile fields, access level, and plugin ownership. | Access-controlled content behaves according to the target rules.                                    |
| Learners, donors, booking users, or event users | Plugin records, history, metadata, and external references.                  | User history is usable or accepted as excluded/custom scope.                                        |
| WooCommerce customers                           | Customer/order meaning, addresses, subscriptions, and commerce behavior.     | Commerce users are validated through WooCommerce-specific scope, not generic WordPress user checks. |

### SEO, URL, and Redirect Validation <a href="#seo-url-and-redirect-validation" id="seo-url-and-redirect-validation"></a>

| URL area             | What to check                                                                                 | Pass condition                                                |
| -------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Permalinks and slugs | Priority paths, post/page slugs, custom post type URLs, category/tag URLs, and archive paths. | Important URLs resolve to approved target pages or redirects. |
| Redirects            | Source-to-target mapping, chains, status codes, and high-traffic paths.                       | Redirects are active, direct, and correct for priority URLs.  |
| Internal links       | Links inside content, menus, widgets, builder modules, and custom fields.                     | Internal navigation does not point to obsolete source paths.  |
| Media URLs           | Embedded images, downloads, PDFs, galleries, and linked files.                                | Priority media links remain valid and accessible.             |

### Add-ons, Custom Service, and Entity Points Validation <a href="#add-ons-custom-service-and-entity-points-validation" id="add-ons-custom-service-and-entity-points-validation"></a>

Add-ons and Custom Service outputs should be validated as explicit scope, not as assumptions. Entity Points should also be reviewed when new eligible records are migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action.

| Scope area     | Validation priority                                                                                              | Pass condition                                                                    |
| -------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Add-ons        | Confirm mapped, filtered, configured, or extended data behaves as requested.                                     | Add-on output is visible in approved samples and does not blur into custom logic. |
| Custom Service | Validate custom post types, custom fields, plugin tables, external IDs, or bespoke records against agreed scope. | Custom output matches documented acceptance criteria.                             |
| Entity Points  | Review new Product, Customer, Order, and Blog Posts records when relevant to the migration path.                 | New eligible records are counted only when migrated for the first time.           |
| Exclusions     | Confirm unsupported or out-of-scope records are understood.                                                      | Launch expectations do not depend on excluded data.                               |

### Demo Migration and Full Migration Validation <a href="#demo-migration-and-full-migration-validation" id="demo-migration-and-full-migration-validation"></a>

| Migration stage    | Validation focus                                                 | Evidence to collect                                                                                                                             |
| ------------------ | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Demo Migration     | Representative samples across simple and complex content.        | Pages, Blog Posts, media, custom post types, metadata, users, roles, redirects, builder pages, and plugin examples.                             |
| Full Migration     | Complete accepted scope and launch-critical records.             | Final content counts, priority URL checks, visual samples, user/account samples, Add-on outputs, Custom Service outputs, and exclusion signoff. |
| Post-launch review | Remaining configuration, redirect, SEO, or integration behavior. | Issue list, owner, severity, and resolution path.                                                                                               |

### Additional Migration Options and Follow-Up Revalidation <a href="#additional-migration-options-and-follow-up-revalidation" id="additional-migration-options-and-follow-up-revalidation"></a>

Additional Migration Options should trigger renewed validation when later activity adds or changes WordPress content, Blog Posts, users, media, plugin records, custom fields, or source-site URLs. Follow-up migration handling should not assume that earlier Demo Migration evidence still covers new records or changed structures.

| Follow-up situation                | Revalidation requirement                                                                      |
| ---------------------------------- | --------------------------------------------------------------------------------------------- |
| New Blog Posts or CMS Pages        | Review content, author, date, media, categories, tags, slugs, SEO fields, and internal links. |
| New users or account-like records  | Review roles, profile fields, membership/plugin meaning, and permissions.                     |
| Changed custom post type structure | Review target fields, templates, taxonomies, archives, and filters.                           |
| New redirects or URL changes       | Re-test priority paths and internal links.                                                    |
| New plugin or custom data          | Confirm whether Add-ons, Custom Service, or exclusion handling is needed.                     |

### WordPress Validation Priority Matrix <a href="#wordpress-validation-priority-matrix" id="wordpress-validation-priority-matrix"></a>

| Priority                  | Validate first when                                                                | Why it comes first                                                    |
| ------------------------- | ---------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Content and URL integrity | The site depends on search traffic, editorial archives, or resource content.       | Broken URLs and missing media create immediate launch risk.           |
| Custom structures         | The site uses custom post types, taxonomies, or fields.                            | Structured content can look present but fail operationally.           |
| Plugin-owned data         | The site has memberships, LMS, bookings, events, forms, donations, or directories. | Plugin data may require custom interpretation or accepted exclusions. |
| Users and roles           | Access, authorship, membership, or account history matters.                        | Permission errors can affect both users and staff.                    |
| Visual output             | Builders, themes, blocks, shortcodes, or custom templates shape important pages.   | Content completion does not prove page usability.                     |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress validation should prove that migrated content works inside the target WordPress implementation. The strongest validation plan checks core CMS records, custom structures, metadata, media, users, plugins, layouts, redirects, SEO data, integrations, Add-ons, Custom Service outputs, and follow-up migration effects.

When validation separates WordPress core content from plugin and custom behavior, the project can distinguish completed migration scope from implementation work, accepted exclusions, and items that need further review before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first in a WordPress migration?**

Start with priority content, media relationships, URLs, redirects, custom post types, custom fields, users, roles, and plugin-owned records that affect launch-critical behavior.

**Is checking record counts enough for WordPress?**

No. Counts can confirm volume, but WordPress validation must also prove relationships, fields, media, roles, layouts, plugin behavior, SEO data, and redirects.

**How should WooCommerce-related records be validated?**

WooCommerce records should be validated through WooCommerce-specific scope, not as generic WordPress content. Products, Customers, Orders, coupons, checkout, subscriptions, tax, shipping, and payment behavior need separate review.

**When do Add-ons or Custom Service need validation?**

They need validation whenever mapped, filtered, configured, custom, plugin-owned, or external-system data is part of accepted scope. Output should be checked against agreed examples.

**Do Additional Migration Options require another validation pass?**

Yes. Later migration activity can introduce new or changed records, URLs, fields, users, or plugin data. Those changes need renewed review before acceptance.
