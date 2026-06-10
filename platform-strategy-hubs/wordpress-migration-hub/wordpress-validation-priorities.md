# WordPress Validation Priorities

A WordPress migration should be accepted only after the migrated site proves that content, relationships, permissions, presentation dependencies, and plugin-owned meaning still work inside the intended WordPress environment. Record counts alone are not enough. A site can contain the expected number of posts, CMS Pages, Blog Posts, media files, users, or comments while still failing because URLs break, media is detached, taxonomies are incomplete, custom fields are missing, page-builder layouts are unreadable, or plugin-dependent business data has lost context.

Validation should focus on how WordPress will be used after launch. For content-heavy sites, that means checking posts, pages, media, categories, tags, menus, blocks, templates, SEO metadata, redirects, and editorial workflow. For application-style or plugin-driven sites, it also means checking custom post types, custom taxonomies, custom fields, users, roles, capabilities, page builders, membership data, forms, directories, listings, learning content, bookings, donations, events, or commerce data where those behaviors are controlled by plugins or custom implementation.

### What WordPress Validation Must Prove <a href="#what-wordpress-validation-must-prove" id="what-wordpress-validation-must-prove"></a>

WordPress validation should prove that migrated data is not only present, but usable in the target site. The review should confirm that editors can manage content, visitors can navigate pages, users have the right access meaning, media appears in the correct locations, SEO-sensitive URLs remain planned, and plugin-dependent data is either migrated, reconfigured, excluded by decision, or assigned to Custom Service review.

| Validation area                            | What the review should prove                                                                                                                              | Why it matters                                                                                 |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Core content                               | Posts, CMS Pages, Blog Posts, comments, excerpts, publish dates, authors, status values, and featured images are readable and correctly related.          | WordPress value depends heavily on content meaning, not only record presence.                  |
| Media library                              | Images, documents, alt text, captions, file references, featured images, and embedded media display correctly.                                            | Broken media can make otherwise complete content unusable.                                     |
| Taxonomies and navigation                  | Categories, tags, menus, parent-child relationships, archive paths, and navigation labels support the intended site structure.                            | Visitors and editors rely on content organization to find and manage information.              |
| Users and access                           | Users, authors, roles, capabilities, member records, and account-related relationships behave as expected.                                                | Access errors can expose, hide, or misassign content and account records.                      |
| Custom structures                          | Custom post types, custom taxonomies, custom fields, metadata, and plugin-owned relationships retain their intended meaning.                              | Many WordPress sites depend on implementation-specific structures beyond posts and pages.      |
| Themes and builders                        | Block content, theme templates, page-builder output, shortcodes, reusable blocks, and template-dependent layouts remain usable.                           | A technically migrated page can still fail if the content cannot render or be edited properly. |
| SEO and URLs                               | Slugs, titles, meta descriptions, redirects, canonical expectations, image alt text, and priority URL paths are checked.                                  | Search continuity and launch readiness depend on URL and metadata planning.                    |
| Plugin-dependent commerce or business data | Product, order, customer, booking, event, membership, directory, donation, or course data is reviewed within the plugin or custom structure that owns it. | WordPress does not define one native business-data model; plugin context controls meaning.     |

### Validate Core WordPress Content First <a href="#validate-core-wordpress-content-first" id="validate-core-wordpress-content-first"></a>

Core WordPress content validation should begin with representative posts, CMS Pages, Blog Posts, comments, media records, authors, publication dates, statuses, categories, tags, and menus. The goal is to confirm that the migrated site preserves editorial meaning and browsing logic.

A strong review sample should include:

* published, draft, private, scheduled, and archived content where those states matter;
* parent and child CMS Pages;
* Blog Posts with categories, tags, authors, comments, featured images, and embedded media;
* posts with long-form formatting, internal links, galleries, quotes, tables, shortcodes, or reusable blocks;
* pages that appear in menus, landing paths, footer navigation, or high-value SEO flows;
* comments with author, date, moderation, and post relationship context.

The pass condition is simple: editors should be able to recognize and manage the migrated content, and visitors should be able to navigate the content without broken relationships, missing media, or misleading structure.

### Validate Media, Embeds, and File Relationships <a href="#validate-media-embeds-and-file-relationships" id="validate-media-embeds-and-file-relationships"></a>

WordPress sites often depend on the media library more than the raw content count suggests. Images, downloads, PDFs, galleries, product images, featured images, and embedded media may be referenced from posts, pages, custom fields, page-builder data, or plugin records.

Validation should confirm that migrated media is attached to the right content where attachment matters, displays correctly on the frontend, remains accessible in the admin area, and preserves useful metadata such as alt text, captions, titles, and descriptions where available. High-value pages should be checked visually because a page can contain the right text but still fail if images, downloadable files, galleries, or embeds are broken.

### Validate Taxonomies, Menus, and Content Discovery <a href="#validate-taxonomies-menus-and-content-discovery" id="validate-taxonomies-menus-and-content-discovery"></a>

Categories, tags, custom taxonomies, menus, archive pages, breadcrumbs, sidebar widgets, and internal links shape how WordPress content is discovered. A migration should preserve the logic that helps visitors and editors find the right content.

Review should include top-level and nested categories, frequently used tags, archive pages, content assigned to multiple taxonomy terms, and important menu paths. If the site uses custom taxonomies for directories, portfolios, learning content, real estate listings, events, locations, brands, or other structured content, those structures should be reviewed separately from ordinary post categories and tags.

| Discovery layer           | Validation focus                                                                                 | Common gap                                                                            |
| ------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Categories and tags       | Term names, slugs, hierarchy, assignments, and archive behavior.                                 | Terms exist but content is not assigned correctly.                                    |
| Menus                     | Menu labels, destination pages, hierarchy, and high-value navigation paths.                      | Pages migrate but menu structure is incomplete.                                       |
| Custom taxonomies         | Taxonomy names, term relationships, archives, and plugin or theme usage.                         | Custom classifications are treated like ordinary tags and lose business meaning.      |
| Internal links            | Links inside body content, buttons, blocks, widgets, and page-builder sections.                  | Old URLs remain embedded even when pages migrated successfully.                       |
| Archive and listing views | Category archives, author archives, custom post type archives, search pages, and filtered lists. | Individual records work but listing pages no longer represent the intended structure. |

### Validate Users, Roles, Authors, and Account Meaning <a href="#validate-users-roles-authors-and-account-meaning" id="validate-users-roles-authors-and-account-meaning"></a>

User validation is important because WordPress users can act as authors, editors, administrators, customers, members, students, subscribers, contributors, or account holders depending on the site. The same user record may support editorial workflow, membership access, plugin-owned business data, or login-based content.

Validation should confirm that users are not only present, but correctly connected to content and permissions. Authors should remain linked to their posts. Editors and administrators should have expected access. Member or subscriber records should be reviewed inside the plugin or custom structure that owns membership meaning. If commerce behavior is involved, customer-account meaning should be validated in the relevant commerce plugin, not assumed from the WordPress user table alone.

Password continuity depends on platform compatibility and migration scope. If password migration is not supported for a specific path or setup, the launch plan should include an account reset or customer communication path rather than treating user presence as proof of login readiness.

### Validate Custom Post Types, Custom Fields, and Plugin-Owned Data <a href="#validate-custom-post-types-custom-fields-and-plugin-owned-data" id="validate-custom-post-types-custom-fields-and-plugin-owned-data"></a>

Many WordPress sites use custom post types, custom taxonomies, custom fields, and plugin-owned database structures to represent business meaning. Examples can include portfolios, locations, directories, events, courses, memberships, bookings, forms, donations, listings, products, orders, subscriptions, or other structured records.

Validation should identify which plugin or custom implementation owns each structure. A record should be reviewed by its operational meaning, not only by whether it appears in the database. A migrated event should still behave like an event. A migrated listing should still appear in the intended listing flow. A migrated form entry should still retain field meaning. A migrated course or membership record should still support the expected access or reporting context where that scope is included.

Custom fields require special attention. Field names, field groups, serialized values, repeaters, relationship fields, media references, and plugin-specific metadata can affect frontend output and admin usability. If these values need customized interpretation, tailored transformation, or plugin-specific handling beyond standard service capability, the requirement belongs in Custom Service review.

### Validate Theme, Block Editor, and Page-Builder Output <a href="#validate-theme-block-editor-and-page-builder-output" id="validate-theme-block-editor-and-page-builder-output"></a>

A WordPress migration can preserve content while still requiring separate theme, block, or page-builder work. Content created with the block editor, reusable blocks, patterns, shortcodes, widgets, classic editor markup, or third-party page builders may depend on the target theme and plugin stack.

Validation should check pages that represent the site’s real layout complexity. This includes home pages, landing pages, service pages, product or listing templates, archive pages, forms, media-heavy posts, and pages that rely on page-builder modules. The review should confirm that the migrated content can be viewed, edited, and maintained without exposing broken shortcodes, missing builder modules, detached media, or unusable layout structures.

Design recreation should not be confused with data migration. If the target site needs theme rebuilding, block-theme configuration, page-builder reconstruction, template adjustments, or custom frontend work, those tasks should be planned separately from migrated record acceptance.

### Validate SEO, URLs, Redirects, and Domain-Sensitive Paths <a href="#validate-seo-urls-redirects-and-domain-sensitive-paths" id="validate-seo-urls-redirects-and-domain-sensitive-paths"></a>

SEO validation should focus on the pages and posts that matter most to traffic, revenue, leads, rankings, or brand trust. WordPress migration planning should confirm slug continuity, URL structure, metadata, headings, image alt text, canonical expectations, redirects, sitemap behavior, and internal links.

A strong SEO validation sample should include:

* high-traffic posts and CMS Pages;
* landing pages with important search visibility;
* category, tag, author, or custom taxonomy archive pages;
* pages with embedded internal links and calls to action;
* pages with old URL structures that need redirect planning;
* content managed by SEO plugins or page builders;
* multilingual or multi-domain paths if the site uses those structures.

The pass condition is not that every URL automatically matches the old site. The pass condition is that priority URL outcomes are known, redirect responsibilities are clear, metadata is reviewable, and the launch team knows which SEO-sensitive paths still need configuration or manual adjustment.

### Validate Plugin-Dependent Commerce and Business Records <a href="#validate-plugin-dependent-commerce-and-business-records" id="validate-plugin-dependent-commerce-and-business-records"></a>

WordPress should not be treated as a single native e-commerce data model. Products, orders, customers, subscriptions, coupons, bookings, memberships, donations, events, appointments, courses, listings, downloads, and invoices depend on the plugin or custom implementation that created them.

When a WordPress migration includes commerce or business records, validation should happen inside the relevant plugin context. A product should be checked against its product plugin. A booking should be checked against its booking plugin. A membership record should be checked against its membership plugin. An order should be checked against the commerce plugin that defines order status, payment context, customer relationship, tax, shipping, fulfillment, and reporting meaning.

| Plugin-dependent area         | Validation priority                                                                                                        | Escalation signal                                                                |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Commerce records              | Products, orders, customers, coupons, subscriptions, tax, shipping, and payment context inside the active commerce plugin. | Plugin-owned data requires custom interpretation or unsupported migration logic. |
| Memberships and subscriptions | Member profiles, plans, access rules, subscription status, renewal context, and user relationships.                        | Access behavior depends on plugin rules or external billing systems.             |
| Bookings, events, and courses | Schedules, instructors, attendees, locations, capacity, dates, and registration relationships.                             | Records use custom tables, serialized metadata, or plugin-specific workflows.    |
| Forms and leads               | Field labels, submissions, consent, source page, timestamps, and notification context.                                     | Form data must remain operational beyond archival reference.                     |
| Directories and listings      | Listing fields, taxonomy filters, media, contact details, maps, and search behavior.                                       | Custom fields or external identifiers drive frontend display.                    |

### Interpret Demo Migration Results Carefully <a href="#interpret-demo-migration-results-carefully" id="interpret-demo-migration-results-carefully"></a>

Demo Migration should be used to inspect meaning, relationships, and usability. It should not be accepted only because the record count looks close to expectation. WordPress validation should include samples from the structures that are most likely to fail: custom post types, custom fields, plugin-owned records, media-heavy content, page-builder layouts, user-account relationships, high-value URLs, and SEO-sensitive pages.

If Demo Migration reveals broken relationships, missing field meaning, unsupported plugin data, failed media references, unusable layouts, or unclear access behavior, the next action should be defined before Full Migration. The right response may be field mapping, data filtering, target setup correction, plugin configuration, accepted exclusion, manual content work, or Custom Service review.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress validation should prove that migrated data still has meaning inside the target WordPress site. Core records, media, taxonomies, users, roles, custom fields, plugins, builders, SEO, and URLs should be reviewed through the way the site will actually operate after launch.

Before approving a WordPress migration, review the Demo Migration with representative content samples, not only totals. If important records depend on custom post types, custom fields, page builders, plugins, commerce extensions, memberships, bookings, or external systems, confirm whether those structures are supported by the selected migration path or whether Add-ons, target configuration, manual work, or Custom Service review should be planned before Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be validated first after a WordPress Demo Migration?**

Start with representative posts, CMS Pages, Blog Posts, media, taxonomies, users, menus, and high-value URLs. Then review custom post types, custom fields, page-builder content, plugin-owned data, and commerce records where those structures are included in the migration scope.

**Is matching the number of WordPress records enough to approve migration?**

No. Record counts do not prove that content relationships, media references, author links, taxonomies, custom fields, plugin data, URLs, SEO metadata, or page-builder output are correct. Validation should focus on whether migrated records remain usable in the target WordPress site.

**Should WooCommerce or other commerce data be validated as WordPress data?**

Commerce data should be validated through the plugin that owns it. WordPress provides the CMS foundation, but products, orders, customers, subscriptions, coupons, shipping, payment, and tax meaning depend on the commerce plugin or custom implementation being migrated.

**Why do custom post types and custom fields need separate validation?**

Custom post types and custom fields often carry business meaning that ordinary posts and CMS Pages do not. They may control directories, listings, events, courses, memberships, product details, page layouts, or integrations. If they are incomplete or misinterpreted, the site may look partially migrated while important functionality is missing.

**What should happen if validation finds unsupported plugin data?**

Unsupported plugin data should be separated from ordinary content validation. The project should decide whether the data can be excluded, manually recreated, handled through supported mapping or configuration, or reviewed under Custom Service because custom migration logic adjustment is required.
