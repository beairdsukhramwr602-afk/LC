# WordPress Validation Priorities

WordPress validation should prove that migrated records remain usable inside the target site, not only present in the database. A page title, post body, media file, user account, or taxonomy term can appear correctly while the layout, metadata, permissions, internal links, plugin behavior, redirect path, or template output is still incomplete.

For WordPress, the validation burden is shaped by the site model. A content-led website may depend on pages, posts, media, menus, taxonomies, and redirects. A structured-content site may rely on custom post types, custom taxonomies, metadata, relationships, templates, and archives. A membership, LMS, directory, donation, event, or booking site may place business meaning inside plugin records or custom tables. Validation should therefore test representative business meaning, not only exported counts.

### Validation Should Prove Site Usefulness <a href="#validation-should-prove-site-usefulness" id="validation-should-prove-site-usefulness"></a>

A WordPress migration is successful when important content is editable, discoverable, linked, permission-aware, and visible through the intended theme, block setup, plugin stack, and URL structure. Counts can support the review, but they cannot replace sample-based proof.

| Validation layer      | What should be proven                                                                                                       | Why it matters                                                                 |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Core content          | CMS Pages, Blog Posts, media, comments, categories, tags, authors, menus, and statuses remain usable.                       | Confirms the baseline WordPress site has not lost editorial meaning.           |
| Structured content    | Custom post types, custom taxonomies, relationships, custom fields, archives, and templates behave as intended.             | Prevents structured records from being flattened into ordinary pages.          |
| Presentation          | Blocks, shortcodes, widgets, builder output, reusable sections, theme templates, and embedded assets render acceptably.     | Protects the visible site experience.                                          |
| Users and access      | Authors, editors, members, subscribers, students, donors, or other account types keep the expected role meaning.            | Prevents account records from losing permissions or business context.          |
| URLs and SEO          | Slugs, permalinks, redirects, canonical values, internal links, metadata, media URLs, and archive paths are checked.        | Protects traffic, navigation, and discoverability.                             |
| Plugin or custom data | Forms, memberships, LMS, events, directories, bookings, donations, custom tables, or external IDs are scoped and validated. | Separates supported migration output from Custom Service or target-side setup. |

Validation should begin with the records most likely to expose the WordPress model: homepage, high-traffic pages, recent and older Blog Posts, media-heavy content, custom post type examples, taxonomy archive examples, user/account examples, and plugin-dependent records. A small but well-chosen sample set is more useful than a broad review of only ordinary pages.

### Validate Core Pages, Posts, Menus, and Media <a href="#validate-core-pages-posts-menus-and-media" id="validate-core-pages-posts-menus-and-media"></a>

Core content validation checks whether ordinary WordPress records remain usable for editors and visitors. The review should include both admin-side editing and front-end display. A record that looks correct in the admin area may still break through the theme, menu, shortcode, block, or media layer.

| Sample type   | What to check                                                                                                                     | Pass condition                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| CMS Pages     | Title, slug, content, hierarchy, parent/child relationship, template, featured media, menu placement, internal links, and status. | Priority pages are editable, reachable, visually acceptable, and correctly linked.           |
| Blog Posts    | Title, body, author, date, categories, tags, excerpt, comments, featured image, slug, and archive appearance.                     | Blog history remains browsable, attributable, and discoverable.                              |
| Media Library | Files, filenames, alt text, captions, descriptions, attachment relationships, galleries, downloads, and featured-image links.     | Media remains attached to the right records and displays without relying on the source site. |
| Menus         | Labels, hierarchy, menu locations, custom links, page links, taxonomy links, and external links.                                  | Navigation sends visitors to valid target destinations.                                      |
| Comments      | Author, date, status, nesting, related post/page, and moderation state.                                                           | Comment history is connected to the correct content and appears only where expected.         |

Core validation should also confirm whether the target site has changed content strategy. Some pages may be migrated as editable content, some may be rebuilt, some may be redirected, and some may be retired. The validation result should identify which decision was made rather than treating every missing page as a defect.

### Validate Custom Post Types and Taxonomies <a href="#validate-custom-post-types-and-taxonomies" id="validate-custom-post-types-and-taxonomies"></a>

Custom post types and custom taxonomies are one of the most important WordPress validation areas because they often carry the real site structure. Events, resources, staff profiles, locations, courses, listings, documentation entries, portfolios, directories, case studies, downloads, or forms may look like content but behave differently from ordinary pages or Blog Posts.

Validation should test the record type, field structure, taxonomy assignments, archive behavior, URL pattern, template output, search/filter behavior, and editor usability. A successful result should show that the migrated record still behaves as the intended content type.

| Structure                 | Validation priority                                                                       | Failure signal                                                              |
| ------------------------- | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Custom post type          | Record type, title, slug, status, fields, media, relationships, archive, and edit screen. | Records appear as ordinary pages or posts and lose their intended workflow. |
| Custom taxonomy           | Terms, hierarchy, assignments, archive pages, filters, and URL paths.                     | Terms migrate but no longer support browsing or grouping.                   |
| Relationship fields       | Related people, locations, resources, events, downloads, or categories.                   | Records exist but their connections disappear.                              |
| Archive and listing pages | Sort order, pagination, filters, excerpts, featured images, and template output.          | Structured content exists in admin but cannot be browsed properly.          |

The pass condition should be based on behavior, not labels. If an event appears as a post but no longer has date, venue, organizer, archive, or filter behavior, the record is not validated simply because its title and body migrated.

### Validate Metadata, Custom Fields, and Plugin-Owned Records <a href="#validate-metadata-custom-fields-and-plugin-owned-records" id="validate-metadata-custom-fields-and-plugin-owned-records"></a>

WordPress metadata can be highly meaningful or completely disposable. Custom fields may store display values, SEO fields, schema values, relationship IDs, event dates, membership states, access rules, builder settings, integration IDs, cache fragments, or abandoned plugin residue. Validation should separate valuable fields from noise.

| Data area        | What to validate                                                                                          | Pass condition                                                                                  |
| ---------------- | --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Custom fields    | Field keys, values, field types, repeaters, relationships, serialized values, and editability.            | Required fields are readable and used by the target templates or plugins.                       |
| SEO metadata     | SEO title, description, canonical value, index settings, schema fields, breadcrumbs, and social metadata. | Priority pages and posts have approved search-sensitive values.                                 |
| Builder metadata | Blocks, reusable blocks, shortcodes, module settings, templates, and embedded assets.                     | Important pages render acceptably or have an approved rebuild path.                             |
| Plugin records   | Forms, submissions, memberships, events, courses, bookings, donations, directories, or custom tables.     | Plugin-owned data is migrated, excluded, or scoped for Custom Service with acceptance criteria. |
| External IDs     | CRM, LMS, ERP, booking, membership, donation, analytics, PIM, or middleware identifiers.                  | Required references are preserved or replaced by a target operating process.                    |

Add-ons can be useful when supported filtering, field mapping, or configuration needs are clear. Custom Service should be reviewed when records depend on unsupported plugin data, custom tables, serialized logic, bespoke transformations, outside-system identifiers, or target implementation-specific interpretation.

### Validate Users, Roles, Permissions, and Account Meaning <a href="#validate-users-roles-permissions-and-account-meaning" id="validate-users-roles-permissions-and-account-meaning"></a>

WordPress users can represent many things: authors, editors, administrators, subscribers, members, learners, instructors, donors, agents, vendors, community accounts, or plugin-controlled profiles. A successful validation process should confirm account meaning, not only username and email transfer.

| Account type                                        | Validation priority                                                                                  | Pass condition                                                                                        |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Authors and editors                                 | Authorship, display name, author archive, role, and editorial permissions.                           | Content attribution and publishing access are correct.                                                |
| Members or subscribers                              | Role, access level, profile fields, restricted content, membership status, and plugin ownership.     | Account access behaves according to target rules.                                                     |
| Learners, donors, booking users, or directory users | Plugin history, metadata, external IDs, and related records.                                         | User history is usable, excluded, or custom-scoped by decision.                                       |
| Commerce-adjacent accounts                          | Customer-like records, order history, addresses, subscriptions, and checkout context where relevant. | Commerce meaning is validated through the appropriate commerce scope rather than generic user checks. |

Role and capability validation is especially important when the source site uses custom roles. Default roles may be easier to interpret, but custom roles can control private content, dashboards, submission workflows, vendor pages, course progress, downloads, or membership access. The target result should not grant excessive access or remove access that the business depends on.

### Validate URLs, SEO, Redirects, and Internal Links <a href="#validate-urls-seo-redirects-and-internal-links" id="validate-urls-seo-redirects-and-internal-links"></a>

WordPress validation should treat URLs as part of site continuity. Content may migrate successfully while traffic still suffers because permalink structure, slugs, taxonomy archives, media URLs, canonical values, redirects, or internal links were not handled.

| URL and SEO area     | What to check                                                                                                          | Pass condition                                                               |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Permalinks and slugs | Priority paths, post/page slugs, parent-child page URLs, category/tag paths, custom post type URLs, and archive paths. | Important paths resolve to approved target pages or redirects.               |
| Redirects            | Source-to-target mapping, high-traffic paths, chains, status codes, and retired URLs.                                  | Redirects are active, direct, and aligned with the accepted URL plan.        |
| Internal links       | Links inside page content, menus, widgets, blocks, builder modules, custom fields, and shortcodes.                     | Internal navigation does not point to obsolete source paths.                 |
| Media URLs           | Embedded images, downloads, PDFs, galleries, sliders, and linked files.                                                | Priority assets load from the target environment.                            |
| SEO plugin fields    | Titles, descriptions, canonical values, social fields, schema fields, breadcrumbs, and index settings.                 | High-value pages preserve or intentionally revise search-sensitive metadata. |

The validation team should avoid treating SEO as a final afterthought. If the migration changes the permalink model, taxonomy structure, content hierarchy, language setup, or SEO plugin, validation should include traffic-critical pages and representative archive paths.

### Validate Theme, Block, Builder, and Template Output <a href="#validate-theme-block-builder-and-template-output" id="validate-theme-block-builder-and-template-output"></a>

WordPress content is not only stored text. Themes, templates, blocks, block patterns, reusable blocks, widgets, shortcodes, and builders can determine whether migrated content displays correctly. Validation should identify which visible issues belong to migration output, which belong to target theme setup, and which require manual rebuild.

| Presentation area | What to validate                                                                              | Practical decision                                                     |
| ----------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Block content     | Core blocks, reusable blocks, custom blocks, embeds, columns, media, tables, and galleries.   | Preserve, adjust, or rebuild based on target compatibility.            |
| Shortcodes        | Forms, galleries, sliders, embeds, buttons, downloads, listings, or plugin output.            | Confirm whether shortcode handlers exist and render correctly.         |
| Page builders     | Elementor, Divi, WPBakery, Beaver Builder, or other builder structures where present.         | Migrate content, rebuild layout, or review Custom Service feasibility. |
| Theme templates   | Page templates, archive templates, single templates, header/footer areas, and template parts. | Confirm target-side setup and expected visual result.                  |
| Widgets and menus | Sidebar areas, footer blocks, navigation locations, and custom menu links.                    | Validate display and manual configuration needs.                       |

A page can pass content validation but fail launch readiness if the visible result is unusable. Presentation findings should be classified as migration correction, target-side theme work, manual rebuild, Add-on adjustment, Custom Service review, or accepted limitation.

### Validate Additional Migration Activity Before Launch <a href="#validate-additional-migration-activity-before-launch" id="validate-additional-migration-activity-before-launch"></a>

Many WordPress sites continue publishing while migration work is reviewed. New Blog Posts, CMS Pages, media files, users, comments, custom post type records, taxonomy terms, or plugin records can appear after an initial migration run. Validation should define what must be rechecked when migration activity continues.

| Later migration situation         | Revalidation requirement                                                                          |
| --------------------------------- | ------------------------------------------------------------------------------------------------- |
| New CMS Pages or Blog Posts       | Content, author, date, media, categories, tags, slug, SEO fields, and internal links.             |
| New custom post type records      | Fields, relationships, taxonomy assignments, templates, archives, and URL behavior.               |
| New users or account-like records | Roles, profile fields, access rules, plugin meaning, and permissions.                             |
| New redirects or URL changes      | Priority paths, internal links, media URLs, and redirect behavior.                                |
| New plugin or custom data         | Confirm whether supported migration, Add-ons, Custom Service, exclusion, or manual setup applies. |

Entity Points should be interpreted correctly when new eligible records are migrated. New eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time, but records already counted through the service license do not consume Entity Points again simply because another migration action occurs on the same migration path.

### Build a WordPress Validation Report <a href="#build-a-wordpress-validation-report" id="build-a-wordpress-validation-report"></a>

A validation report should be practical enough to guide launch decisions. It should identify the sample, expected result, observed result, severity, handling path, owner, and final status.

| Report field     | Purpose                                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Record or sample | Identifies the page, post, media file, user, custom post type record, taxonomy term, URL, plugin record, or template sample.                                  |
| Expected result  | States what the migrated result should look like or do.                                                                                                       |
| Observed result  | Describes what appears in the target WordPress site.                                                                                                          |
| Severity         | Separates launch blockers from minor cleanup.                                                                                                                 |
| Handling path    | Classifies the issue as migration correction, Add-on adjustment, Custom Service review, target-side setup, manual rebuild, accepted limitation, or exclusion. |
| Owner            | Assigns responsibility to the merchant, Next-Cart, WordPress implementer, designer, SEO team, or external integration partner.                                |
| Status           | Confirms whether the issue is open, corrected, accepted, or deferred.                                                                                         |

The report should not become a loose screenshot collection. Each finding should explain the business impact and the path to resolution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress validation should prove that the target site works as a usable CMS environment. Pages, Blog Posts, media, menus, custom post types, taxonomies, custom fields, users, roles, plugin records, presentation output, SEO fields, URLs, redirects, Add-ons, Custom Service outputs, and later migration activity all require sample-based review.

The strongest validation approach checks content meaning, editing usability, front-end display, permission behavior, URL continuity, and custom-data scope together. A WordPress migration should be approved when the migrated result can support real publishing, navigation, search visibility, account use, and launch operations—not merely because record counts match.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is checking WordPress record counts enough after migration?**

No. Counts help confirm volume, but they do not prove usability. WordPress validation should also check editable content, media relationships, custom post types, taxonomies, metadata, users, roles, URLs, redirects, plugin records, and front-end display.

**Why do custom post types need separate validation?**

Custom post types often carry structured business meaning. Events, listings, courses, resources, directories, or staff profiles need their fields, taxonomy assignments, templates, archives, and URL behavior checked as structured records, not ordinary pages.

**Should page-builder output be part of validation?**

Yes, when page builders, blocks, shortcodes, or theme templates affect important pages. Content may migrate while layout or functional sections still need target-side setup, manual rebuild, Add-on adjustment, or Custom Service review.

**How should plugin-owned records be validated?**

Plugin-owned records should be validated against explicit scope. Some may be supported, some may require Add-ons, some may require Custom Service, and some may be excluded or rebuilt in the target environment.

**What needs to be revalidated after later migration activity?**

Recheck newly migrated records and representative regression samples. For WordPress, that can include new CMS Pages, Blog Posts, custom post type records, media, users, taxonomy terms, SEO fields, redirects, internal links, and plugin-owned records.
