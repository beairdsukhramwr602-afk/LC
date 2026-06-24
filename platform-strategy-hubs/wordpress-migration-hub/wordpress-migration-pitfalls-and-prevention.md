# WordPress Migration Pitfalls and Prevention

WordPress migration problems usually appear when a site is treated as a simple page-and-post transfer. WordPress can be a publishing system, a membership portal, an LMS, a booking site, a directory, a donation platform, a community site, a headless CMS, or a WooCommerce-connected storefront. Each model stores meaning differently.

A reliable WordPress migration prevents failure before Full Migration by identifying which records are ordinary WordPress content, which records belong to plugins, which fields control display or access, which URLs must remain stable, and which requirements need Add-ons or Custom Service review. The goal is not to avoid every implementation difference. The goal is to prevent avoidable surprises that make migrated content unusable, unsearchable, inaccessible, or disconnected from the target WordPress environment.

### WordPress Pitfall Prevention Map <a href="#wordpress-pitfall-prevention-map" id="wordpress-pitfall-prevention-map"></a>

| Pitfall area                   | What usually creates the problem                                                            | Prevention focus                                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| WordPress vs WooCommerce scope | Commerce data is treated as generic WordPress content.                                      | Separate CMS records from Products, Customers, Orders, coupons, subscriptions, tax, payment, shipping, and checkout behavior. |
| Custom structures              | Custom post types, taxonomies, fields, and plugin tables are not identified.                | Inventory source structures and confirm target ownership before migration.                                                    |
| Layout and media               | Builder data, shortcodes, media references, and embedded assets are assumed to be portable. | Validate front-end rendering, not only database presence.                                                                     |
| Users and access               | Roles, capabilities, membership states, or plugin accounts are treated as simple users.     | Validate access behavior by user type.                                                                                        |
| SEO and routing                | Slugs, redirects, metadata, internal links, and canonical values are reviewed too late.     | Build a priority URL and SEO evidence set before launch.                                                                      |
| Follow-up migration            | New data is added after earlier migration activity without renewed review.                  | Use Additional Migration Options with fresh validation and Entity Points awareness.                                           |

### Pitfall 1: Treating WordPress as Native E-commerce <a href="#pitfall-1-treating-wordpress-as-native-e-commerce" id="pitfall-1-treating-wordpress-as-native-e-commerce"></a>

#### What goes wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

A migration plan assumes WordPress itself owns products, orders, checkout, payment, shipping, customer accounts, subscriptions, memberships, donations, bookings, or event registrations. In practice, those records are controlled by WooCommerce, another plugin, custom post types, custom tables, external services, or a custom implementation.

When commerce-like records are migrated as ordinary WordPress content, the target site may show titles or descriptions but fail to preserve operational meaning. Customers may not have usable order history, products may not behave as products, checkout-related data may not connect to the target plugin, and staff may not be able to manage the records through the expected workflow.

#### Early warning signs <a href="#early-warning-signs" id="early-warning-signs"></a>

| Warning sign                                                                                                        | Why it matters                                                                                    |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Products, orders, subscriptions, bookings, memberships, donations, or events are described only as “WordPress data” | The scope may be hiding plugin-owned commerce or business records.                                |
| Target plugins are not confirmed                                                                                    | Migrated data may have nowhere meaningful to land.                                                |
| WooCommerce is present but not scoped separately                                                                    | Commerce records may require commerce-specific review rather than generic WordPress handling.     |
| Checkout, payment, shipping, tax, or subscription behavior is expected to continue automatically                    | Those functions depend on plugin configuration and business logic, not CMS record movement alone. |

#### Prevention <a href="#prevention" id="prevention"></a>

Separate WordPress CMS content from WooCommerce and other plugin-owned business data before approving scope. Confirm which plugin, custom post type, custom table, or external system owns each business record, and decide whether the target WordPress site will use the same structure.

If the requirement depends on unsupported plugin data, custom tables, custom relationship logic, commerce-specific interpretation, or target plugin behavior that standard migration cannot preserve, route it to Custom Service review. Do not use generic WordPress migration assumptions for commerce-plugin records.

#### Recommendation example <a href="#recommendation-example" id="recommendation-example"></a>

For a site that combines Blog Posts, WooCommerce Products, subscription records, paid memberships, donation forms, and learning content, validate each business type separately. Blog Posts may follow a standard CMS path, while subscription, membership, order, donation, and course-progress records may require plugin-specific review or Custom Service planning.

#### Pass condition <a href="#pass-condition" id="pass-condition"></a>

Commerce and plugin-owned business data is either migrated into usable target structures, scoped for Custom Service review, or explicitly excluded with clear launch expectations. Generic WordPress content is not used to mask WooCommerce or plugin-specific requirements.

### Pitfall 2: Missing Custom Post Types and Custom Taxonomies <a href="#pitfall-2-missing-custom-post-types-and-custom-taxonomies" id="pitfall-2-missing-custom-post-types-and-custom-taxonomies"></a>

#### What goes wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

WordPress sites often use custom post types and custom taxonomies to represent business-specific content: properties, courses, events, staff, downloads, testimonials, locations, directories, portfolios, documentation, jobs, campaigns, or resource libraries. If these records are treated as ordinary posts or CMS Pages, migration can flatten meaning and break archive pages, filters, templates, internal links, or front-end presentation.

Custom taxonomies can be just as important as the records themselves. A location taxonomy, course-level taxonomy, industry taxonomy, or listing category can control navigation, filtering, access, or reporting.

#### Early warning signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

| Warning sign                                                             | Why it matters                                         |
| ------------------------------------------------------------------------ | ------------------------------------------------------ |
| The WordPress admin has content sections beyond Posts and Pages          | Specialized records may exist.                         |
| Content is grouped by non-standard categories                            | Custom taxonomies may control navigation or filtering. |
| The target site uses a different theme, plugin, or custom implementation | Matching source structures may not exist by default.   |
| Archive pages, listing grids, maps, or filters are business-critical     | Structure loss can affect the front-end experience.    |

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Inventory all custom post types and custom taxonomies before Demo Migration. For each one, confirm the target post type, fields, taxonomy relationships, archive expectations, display templates, and filter behavior. If the target implementation differs, mapping decisions should be approved before Full Migration.

Add-ons may help when the required mapping is structured and supported. Custom Service review is needed when custom records require bespoke interpretation, unsupported relationships, or target implementation-specific handling.

#### Recommendation example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

For a directory site, test business listings, listing categories, location taxonomies, contact fields, map data, featured images, related users, and archive pages. A successful test should prove that the listing behaves as a listing, not just that its title was imported.

#### Pass condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Important custom post types and taxonomies keep their intended meaning, relationships, archive behavior, and front-end usability in the target WordPress site.

### Pitfall 3: Migrating Custom Fields Without Confirming Their Purpose <a href="#pitfall-3-migrating-custom-fields-without-confirming-their-purpose" id="pitfall-3-migrating-custom-fields-without-confirming-their-purpose"></a>

#### What goes wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Custom fields and metadata can store display values, SEO fields, schema data, product-like properties, access rules, event dates, membership states, page-builder settings, lead-source values, integration IDs, and hidden workflow controls. Moving field keys and values does not prove the target site can interpret them.

Some fields are reusable business data. Others are cache, abandoned plugin residue, serialized settings, temporary display values, or data that only a specific plugin or theme can read. Treating all metadata equally can create bloated results while still missing the fields that matter.

#### Early warning signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

| Warning sign                                                                                              | Why it matters                                            |
| --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| The source uses Advanced Custom Fields, Meta Box, Pods, Toolset, theme meta boxes, or custom-coded fields | Business meaning may live outside visible content.        |
| Important pages depend on hidden fields                                                                   | Content may migrate but display incorrectly.              |
| Target theme or plugin stack is different                                                                 | Field names may not be read by the target implementation. |
| Field inventory is large but ownership is unclear                                                         | The migration may carry noise and miss useful meaning.    |

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Classify metadata by purpose before migration: display fields, relationship fields, SEO fields, integration IDs, user fields, plugin settings, cache values, and fields to exclude. Validate high-value fields by front-end behavior, admin usability, search/filter behavior, and integration continuity.

Use Advanced Data Mapping or Advanced Data Configure only when the mapping or value adjustment is supported and well-defined. Unsupported field interpretation, serialized logic, plugin-specific relationships, or custom table dependencies should move to Custom Service review.

#### Recommendation example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

For a real estate site, validate listing price, address, availability, property type, agent assignment, map coordinates, gallery, and contact details in the target listing template. Do not accept the result only because the fields appear in the database.

#### Pass condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Custom-field data needed for display, search, filtering, access, integrations, SEO, or business workflows is readable and usable in the target WordPress environment.

### Pitfall 4: Assuming Page Builders and Themes Will Reconstruct Automatically <a href="#pitfall-4-assuming-page-builders-and-themes-will-reconstruct-automatically" id="pitfall-4-assuming-page-builders-and-themes-will-reconstruct-automatically"></a>

#### What goes wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

WordPress page builders, block systems, themes, and shortcode frameworks can store layout in block markup, shortcodes, serialized metadata, reusable blocks, global widgets, theme options, custom tables, or plugin-specific structures. A migration can preserve page text but lose visual structure, forms, galleries, sliders, call-to-action sections, reusable sections, or template behavior.

This is especially risky when the target site changes theme, builder, block library, or design system.

#### Early warning signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

| Warning sign                                                                                           | Why it matters                                       |
| ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------- |
| Pages use Elementor, Divi, WPBakery, Beaver Builder, Gutenberg blocks, custom blocks, or theme modules | Layout may be stored outside plain content.          |
| Target uses a different builder or theme                                                               | Source layout data may not render.                   |
| The merchant expects an identical visual result                                                        | Data migration may not equal design reconstruction.  |
| Landing pages include forms, sliders, galleries, reusable widgets, or embedded scripts                 | Functional layout elements may need separate review. |

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Separate content migration from visual reconstruction. Identify which pages must preserve layout, which pages only need content, which pages require manual rebuild, and which page-builder structures need Custom Service review.

Demo Migration should include high-value page types, not only simple posts. Review both admin content and front-end rendering.

#### Recommendation example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Sample the homepage, a service landing page, a media-heavy CMS Page, a form page, a Blog Post with blocks, and a custom post type record. Compare the target front end against the intended launch result and identify what belongs to migration versus redesign.

#### Pass condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Priority pages either retain acceptable layout behavior in the target environment or have an agreed rebuild, exclusion, Add-on, or Custom Service plan.

### Pitfall 5: Losing Media Relationships and Embedded Asset Context <a href="#pitfall-5-losing-media-relationships-and-embedded-asset-context" id="pitfall-5-losing-media-relationships-and-embedded-asset-context"></a>

#### What goes wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Media files can exist in the target library while pages still show broken images, missing featured images, old-domain URLs, broken galleries, missing downloads, empty sliders, or embedded assets that point to the source site. WordPress media is not only a file count; it is a relationship layer connecting content, layouts, SEO metadata, alt text, captions, downloadable assets, and design components.

#### Early warning signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

| Warning sign                                                          | Why it matters                                            |
| --------------------------------------------------------------------- | --------------------------------------------------------- |
| Media count looks correct but images do not display on priority pages | File movement and content relationships are not the same. |
| Featured images are missing from archives or custom post types        | Theme and listing layouts may break.                      |
| Galleries, sliders, PDFs, downloads, or embedded files fail           | Business-critical assets may be disconnected.             |
| Image URLs still point to the old domain                              | Launch can create broken assets and SEO issues.           |

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Validate media by relationship, not only by file count. Review inline images, featured images, galleries, downloads, captions, alt text, media metadata, embedded content, page-builder media modules, and files used by custom post types.

If asset references require path rewriting, custom mapping, or builder-specific handling, confirm whether the adjustment fits supported Add-ons or requires Custom Service review.

#### Recommendation example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Review a long-form Blog Post, a media-heavy CMS Page, a custom post type record with a gallery, a downloadable-resource page, and a landing page with builder-controlled images.

#### Pass condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Priority content displays correct images, featured images, galleries, embedded assets, downloadable files, captions, and media references without relying on the source site.

### Pitfall 6: Underestimating Users, Roles, Permissions, and Account Meaning <a href="#pitfall-6-underestimating-users-roles-permissions-and-account-meaning" id="pitfall-6-underestimating-users-roles-permissions-and-account-meaning"></a>

#### What goes wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

WordPress users may represent authors, editors, subscribers, members, students, instructors, donors, affiliates, vendors, agents, forum users, community members, or plugin-defined account types. Roles and capabilities can control access, publishing rights, private content, downloads, courses, memberships, events, directories, or workflows.

If users are migrated without role and permission context, records may exist but fail to provide usable access.

#### Early warning signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

| Warning sign                                                                             | Why it matters                                        |
| ---------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| The source has membership, LMS, forum, vendor, directory, booking, or community behavior | User meaning may be plugin-defined.                   |
| Roles go beyond default WordPress roles                                                  | Capabilities may need target review.                  |
| Private content or downloads depend on access rules                                      | Simple user migration may not preserve authorization. |
| Password continuity or login behavior is assumed                                         | Authentication may require separate planning.         |

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Inventory user roles, account types, capabilities, access rules, and plugin-owned user metadata. Validate representative users from each important account type during Demo Migration.

If user meaning is tied to memberships, subscriptions, orders, LMS progress, vendor records, forum reputation, or custom tables, confirm whether the scope is supported, excluded, or requires Custom Service review.

#### Recommendation example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

Test administrator, editor, author, subscriber, member, student, instructor, vendor, donor, and customer-like accounts where relevant. Confirm dashboard access, restricted content, authored content, profile fields, and plugin-specific account behavior.

#### Pass condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Important users retain the correct role meaning, access behavior, authored content relationships, and account usability expected in the target WordPress site.

### Pitfall 7: Treating SEO as Only Slugs and Titles <a href="#pitfall-7-treating-seo-as-only-slugs-and-titles" id="pitfall-7-treating-seo-as-only-slugs-and-titles"></a>

#### What goes wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

WordPress SEO continuity depends on slugs, permalink structure, redirects, canonical URLs, SEO titles, meta descriptions, schema fields, taxonomy archives, robots settings, image alt text, sitemap behavior, internal links, and SEO plugin metadata. A migration can preserve content while damaging traffic if routing and metadata are not planned.

The risk increases when the target site changes permalink structure, theme, SEO plugin, taxonomy structure, language setup, or page-builder output.

#### Early warning signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

| Warning sign                                 | Why it matters                                                     |
| -------------------------------------------- | ------------------------------------------------------------------ |
| Target permalink structure is not confirmed  | Existing URLs may break.                                           |
| Source and target SEO plugins differ         | Metadata may not map directly.                                     |
| High-value URLs and redirects are not listed | Traffic-sensitive pages may be missed.                             |
| Internal links point to old URLs             | Migrated content may continue sending visitors to the source site. |

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Prepare a priority URL and SEO evidence set before migration. Include top CMS Pages, Blog Posts, taxonomy archives, landing pages, media-heavy pages, redirects, canonical values, SEO metadata, and internal-link samples.

Redirect planning should be handled explicitly when URL structures change. SEO plugin data should be validated by target field behavior, not database presence alone.

#### Recommendation example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

For a content-heavy site, validate top organic landing pages, category archives, high-value Blog Posts, SEO titles, meta descriptions, canonical values, redirects, image alt text, and internal links after Demo Migration.

#### Pass condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Priority URLs, redirects, canonical values, metadata, taxonomy archives, and internal links match the launch plan or have documented corrections before go-live.

### Pitfall 8: Ignoring Plugin Records, Custom Tables, and Integration-Owned Data <a href="#pitfall-8-ignoring-plugin-records-custom-tables-and-integration-owned-data" id="pitfall-8-ignoring-plugin-records-custom-tables-and-integration-owned-data"></a>

#### What goes wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

Many WordPress sites store important records outside standard posts, pages, users, media, comments, and taxonomies. Plugins can create custom tables, app-specific metadata, API-linked records, form submissions, CRM references, LMS progress, booking calendars, directory claims, donation histories, event registrations, and membership states.

If these records are assumed to be standard WordPress content, the migration may miss them entirely or move fragments that the target system cannot use.

#### Early warning signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

| Warning sign                                                                                                    | Why it matters                                                          |
| --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Critical information lives in forms, LMS, memberships, events, bookings, directories, donations, or CRM plugins | Data may belong to plugin tables or external systems.                   |
| External IDs connect WordPress to CRM, ERP, analytics, or automation tools                                      | Losing IDs can break integrations.                                      |
| Target plugins differ from source plugins                                                                       | Records may need transformation or exclusion.                           |
| No one owns integration validation                                                                              | The migration can pass content review while failing operational review. |

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Identify plugin-owned records and external-system dependencies before migration. Classify each dependency as standard scope, Add-on candidate, Custom Service candidate, integration rebuild, or accepted exclusion.

Custom tables, unsupported plugin structures, and bespoke API-linked records usually need Custom Service review or separate implementation planning.

#### Recommendation example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

For a membership and event site, validate member profiles, subscription states, event registrations, form submissions, CRM IDs, email automation tags, and access rules as separate evidence categories.

#### Pass condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Plugin-owned and integration-owned records are migrated, excluded, or scoped for Custom Service with clear ownership and validation evidence.

### Pitfall 9: Accepting Demo Migration by Record Counts Alone <a href="#pitfall-9-accepting-demo-migration-by-record-counts-alone" id="pitfall-9-accepting-demo-migration-by-record-counts-alone"></a>

#### What goes wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

A Demo Migration can look successful because counts for CMS Pages, Blog Posts, users, comments, categories, tags, or media are close to expectations. Counts do not prove that relationships, metadata, layouts, roles, redirects, SEO fields, plugin records, custom post types, or front-end behavior work correctly.

For WordPress, the hardest records to interpret often carry the most business value.

#### Early warning signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

| Warning sign                                                                    | Why it matters                                     |
| ------------------------------------------------------------------------------- | -------------------------------------------------- |
| Review focuses on dashboard totals only                                         | Relationship and display errors may stay hidden.   |
| No front-end review is performed                                                | Pages can exist but fail visually or functionally. |
| Custom post types, users, SEO fields, media, and plugin records are not sampled | Critical structures may be untested.               |
| Target theme and plugin stack are not active                                    | Results may not reflect launch conditions.         |

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Design Demo Migration samples around meaning, not only quantity. Include standard posts/pages, media-heavy pages, custom post types, plugin-owned records, role-specific users, SEO-sensitive URLs, page-builder pages, and WooCommerce-adjacent records where relevant.

Use the sample to decide whether the project is ready for Full Migration, requires Add-ons, needs Custom Service review, or needs target-site preparation before migration continues.

#### Recommendation example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

Instead of only checking whether 500 Blog Posts migrated, review the homepage, service pages, high-traffic Blog Posts, category archives, custom post type records, media galleries, users from each role, SEO fields, redirects, and plugin-dependent pages.

#### Pass condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Demo Migration proves that WordPress content, relationships, metadata, roles, URLs, media, layouts, and plugin-dependent structures behave correctly enough to guide Full Migration decisions.

### Pitfall 10: Using Additional Migration Options Without Renewed Validation <a href="#pitfall-10-using-additional-migration-options-without-renewed-validation" id="pitfall-10-using-additional-migration-options-without-renewed-validation"></a>

#### What goes wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

WordPress sites often keep changing while migration is being planned. New CMS Pages, Blog Posts, comments, users, media, forms, membership records, custom post type entries, plugin records, SEO changes, redirects, or WooCommerce-adjacent activity may be added after an earlier migration activity. If follow-up handling is treated as a simple repeat action, new problems can be missed.

Entity Points also need careful interpretation. New eligible records may consume Entity Points when migrated for the first time, but records already counted through the service license do not consume Entity Points again simply because another migration action is performed.

#### Early warning signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

| Warning sign                                                                   | Why it matters                           |
| ------------------------------------------------------------------------------ | ---------------------------------------- |
| New records were added after Demo Migration or earlier Full Migration activity | Validation evidence may be stale.        |
| Plugin structures changed during the project                                   | Earlier assumptions may no longer apply. |
| New custom fields, forms, users, or content types appeared                     | Scope may need renewed review.           |
| Follow-up migration is planned without checking new edge cases                 | Later data can introduce launch risk.    |

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Use Additional Migration Options with renewed validation. Recheck new and changed records, especially custom post types, plugin-owned data, users, permissions, media, SEO URLs, redirects, and WooCommerce-adjacent activity.

Clarify Entity Points expectations before follow-up activity. New Product, Customer, Order, or Blog Posts records consume Entity Points when migrated for the first time, but already-counted records do not consume Entity Points again simply because another migration action is performed.

#### Recommendation example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

Before launch, sample new Blog Posts, updated CMS Pages, new users, new form entries, new member records, new media assets, changed redirects, and new custom post type entries created after the earlier migration activity. Confirm whether they follow already-proven structures or introduce a new scope issue.

#### Pass condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Additional Migration Options are paired with renewed validation, clear Entity Points expectations, and updated acceptance evidence for new or changed WordPress records.

### WordPress Pitfall Prevention Matrix <a href="#wordpress-pitfall-prevention-matrix" id="wordpress-pitfall-prevention-matrix"></a>

| If the project shows this pattern                                     | Main pitfall risk                                           | Best prevention action                                              |
| --------------------------------------------------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------- |
| Simple CMS content with standard posts and pages                      | Missed media, redirects, authors, or taxonomy relationships | Validate representative content relationships and priority URLs.    |
| Custom post types and custom taxonomies                               | Flattened or missing business structures                    | Inventory source structures and confirm target ownership.           |
| Heavy custom-field usage                                              | Data exists but target cannot read it                       | Classify field purpose and validate display/search/access behavior. |
| Builder or theme-dependent site                                       | Text migrates but layout fails                              | Separate data migration from design reconstruction.                 |
| Membership, LMS, booking, event, donation, directory, or form plugins | Plugin-owned records are missed or unusable                 | Scope plugin data separately and review Custom Service need.        |
| WooCommerce-connected site                                            | Commerce records are mistaken for generic WordPress content | Separate WordPress CMS scope from WooCommerce-specific scope.       |
| SEO-sensitive site                                                    | URLs, metadata, redirects, and internal links break         | Prepare priority URL and SEO evidence before Full Migration.        |
| Follow-up migration activity is expected                              | New records are accepted without fresh proof                | Use Additional Migration Options with renewed validation.           |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Most WordPress migration pitfalls come from underestimating how much meaning lives outside visible page content. A reliable migration must account for custom post types, taxonomies, metadata, media relationships, users and roles, plugins, custom tables, builders, SEO, redirects, integrations, WooCommerce boundaries, and follow-up migration activity.

The safest prevention method is to review WordPress by behavior. Records should not only exist in the target site; they should display correctly, connect to the right relationships, preserve access and SEO meaning, and remain usable by the target theme, plugin stack, and implementation plan. When standard migration cannot preserve that meaning, the project should use Add-ons, Custom Service review, or explicit exclusions before Full Migration is treated as launch-ready.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can a WordPress migration look successful but still fail review?**

A WordPress migration can show the expected number of posts, pages, users, media files, or comments while still missing relationships, metadata, page-builder layout, plugin-owned records, SEO values, user-role behavior, media references, redirects, or front-end usability. Review should test business meaning and target behavior, not only record counts.

**Do WordPress plugins create migration risk?**

Yes. Plugins can define custom post types, custom fields, custom tables, user roles, checkout behavior, SEO metadata, forms, memberships, courses, events, bookings, directories, donations, CRM connections, or other business structures. Plugin-owned records should be identified before migration scope is finalized.

**Should page-builder content be validated separately?**

Yes. Page builders and block systems can store layouts, widgets, reusable sections, galleries, forms, sliders, and design components in plugin-specific structures. A migrated page may contain text but still lose the presentation or function needed for launch.

**Why is SEO review important in a WordPress migration?**

WordPress SEO often depends on permalink structure, slugs, redirects, canonical values, metadata, schema fields, internal links, taxonomy archives, media attributes, sitemap behavior, and SEO plugin fields. These values should be reviewed on priority URLs before launch.

**When should a WordPress migration move into Custom Service review?**

Custom Service review is appropriate when the migration depends on unsupported plugin data, custom post types, custom fields, custom tables, custom user-role behavior, bespoke page-builder handling, external identifiers, WooCommerce-specific interpretation, or custom migration logic adjustment beyond standard service capability.
