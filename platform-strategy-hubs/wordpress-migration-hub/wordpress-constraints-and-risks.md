# WordPress Constraints and Risks

WordPress migration risk usually comes from hidden structure rather than from ordinary posts and pages. A site may look like a simple CMS, but important meaning can live in custom post types, custom taxonomies, custom fields, media relationships, theme templates, page-builder data, plugin tables, user roles, SEO settings, redirects, or external systems.

The safest WordPress migration plan separates what WordPress core owns from what plugins, themes, builders, custom code, WooCommerce, or connected systems own. That separation prevents the project from treating visible content as proof that the target site will behave correctly after Full Migration.

### Why WordPress Constraints Matter <a href="#why-wordpress-constraints-matter" id="why-wordpress-constraints-matter"></a>

| Constraint area      | What creates the risk                                                                                                     | What should be clarified                                                                               |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Core CMS content     | Pages, Blog Posts, media, comments, categories, tags, and menus have many relationships.                                  | Which relationships, authors, dates, media, slugs, and statuses must be preserved.                     |
| Custom structures    | Custom post types, custom taxonomies, and fields may carry site-specific meaning.                                         | Target post types, taxonomies, fields, templates, archives, filters, and editing ownership.            |
| Plugin-owned records | Forms, memberships, LMS, events, bookings, directories, donations, and SEO plugins can store data outside ordinary posts. | Whether plugin data is supported, excluded, configured separately, or routed to Custom Service review. |
| Presentation layer   | Blocks, builders, shortcodes, themes, widgets, and templates may control display.                                         | Which pages need visual validation beyond record migration.                                            |
| SEO and routing      | Permalinks, redirects, canonical values, metadata, and internal links affect discoverability.                             | Which paths are business-critical and how redirects will be validated.                                 |

### WordPress Is Not WooCommerce by Default <a href="#wordpress-is-not-woocommerce-by-default" id="wordpress-is-not-woocommerce-by-default"></a>

WordPress and WooCommerce should be scoped separately. WordPress core does not natively own product, cart, checkout, payment, shipping, tax, coupon, subscription, or order behavior. If a source site contains commerce records, the migration must confirm whether the target relies on WooCommerce, another plugin, a connected system, or a Custom Platform structure.

| Risk signal                                                             | Why it matters                                                                     | Safer handling                                                         |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Products and orders are described only as WordPress content             | Commerce behavior may be hidden inside WooCommerce or another plugin.              | Scope commerce records separately from CMS content.                    |
| Checkout or subscription behavior is expected to transfer automatically | Business logic depends on plugin configuration, payment systems, and custom rules. | Treat behavior as configuration, integration, or Custom Service scope. |
| Customer accounts are mixed with WordPress users                        | A user may be an author, member, subscriber, learner, donor, or customer.          | Validate account meaning by role and plugin ownership.                 |

### Custom Post Type and Taxonomy Risks <a href="#custom-post-type-and-taxonomy-risks" id="custom-post-type-and-taxonomy-risks"></a>

Custom post types and custom taxonomies can represent listings, courses, events, resources, portfolios, jobs, staff, locations, directories, documentation, or product-like records. Migrating them as ordinary pages can preserve text while losing filters, archives, relationships, and editorial workflows.

| Source pattern                                         | Migration risk                                                                     | Prevention                                                                               |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Event, course, listing, directory, or resource records | Records may lose field meaning, dates, taxonomy, archive behavior, or filters.     | Confirm target post type, taxonomy, fields, archive, and template before Full Migration. |
| Custom categories or filters                           | Groupings may not belong in ordinary categories or tags.                           | Map them to custom taxonomies or plugin filters when required.                           |
| Relationship fields                                    | Related content, authors, locations, or downloads may not connect after migration. | Validate representative relationships in Demo Migration.                                 |

### Metadata, Custom Fields, and Custom Tables <a href="#metadata-custom-fields-and-custom-tables" id="metadata-custom-fields-and-custom-tables"></a>

Metadata can control layout, SEO, membership status, lead routing, downloads, user profile behavior, or integration references. Custom tables may store data that WordPress core cannot infer.

| Data type         | Risk                                                                               | Review focus                                                                  |
| ----------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Custom fields     | Data may migrate but not display or filter correctly.                              | Field names, types, output templates, search behavior, and editor visibility. |
| SEO plugin fields | Titles, descriptions, canonicals, schema, and redirects may be stored separately.  | Priority URL samples, metadata fields, and redirect behavior.                 |
| Plugin tables     | Important records may sit outside standard post/meta tables.                       | Plugin ownership, table purpose, exportability, and Custom Service signals.   |
| External IDs      | CRM, LMS, booking, membership, or analytics references may be needed after launch. | ID preservation, sync direction, and connected-system ownership.              |

### Media, Layout, and Builder Risks <a href="#media-layout-and-builder-risks" id="media-layout-and-builder-risks"></a>

WordPress media migration must preserve more than files. Images and documents may be connected to featured images, galleries, custom fields, builder modules, downloadable resources, embedded content, and SEO text. Page builders and themes can also store layout in metadata or shortcodes.

| Risk area                      | What can fail                                                           | Pass condition                                                                           |
| ------------------------------ | ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Media relationships            | Files exist but no longer attach to pages, posts, galleries, or fields. | Priority samples show correct featured media, galleries, embeds, captions, and alt text. |
| Builder layouts                | Content migrates but visual sections break.                             | Key pages render acceptably in the target theme or builder.                              |
| Shortcodes and reusable blocks | Old markup appears as text or loses function.                           | Unsupported shortcodes are replaced, rebuilt, excluded, or scoped for Custom Service.    |
| Theme templates                | Records exist but archives or layouts are incomplete.                   | Target templates support migrated content types and fields.                              |

### SEO, Permalink, and Redirect Risks <a href="#seo-permalink-and-redirect-risks" id="seo-permalink-and-redirect-risks"></a>

WordPress migrations can lose search value when URL behavior is reviewed too late. Slugs, permalinks, taxonomy archive paths, media URLs, internal links, redirects, and canonical values should be prioritized before Full Migration.

| SEO risk                          | Why it matters                                                                    | Prevention                                                    |
| --------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Permalink structure changes       | Existing indexed URLs may no longer resolve.                                      | Create a priority URL map and redirect plan.                  |
| Metadata is plugin-owned          | SEO titles, descriptions, schema, and canonical fields may not be native content. | Identify SEO plugin fields and validate representative pages. |
| Internal links point to old paths | Users and crawlers may hit stale URLs.                                            | Review internal links on priority content samples.            |
| Redirects are assumed             | Redirect behavior depends on target configuration.                                | Validate redirects after Demo Migration and before launch.    |

### Add-ons and Custom Service Risk Boundary <a href="#add-ons-and-custom-service-risk-boundary" id="add-ons-and-custom-service-risk-boundary"></a>

Add-ons can support defined migration needs such as field mapping, filtering, or supported data extensions. Custom Service is needed when WordPress scope depends on unsupported plugin tables, bespoke logic, custom relationships, unusual account meaning, external-system references, or target implementation-specific interpretation.

| Need                                 | Better fit                         | Reason                                                                                |
| ------------------------------------ | ---------------------------------- | ------------------------------------------------------------------------------------- |
| Supported field mapping or filtering | Add-ons                            | The requirement is structured and can be applied within supported migration behavior. |
| Unsupported plugin-owned data        | Custom Service review              | The source structure needs interpretation before scope can be confirmed.              |
| Custom tables or bespoke workflows   | Custom Service review              | Standard content migration cannot infer business logic.                               |
| Accepted exclusions                  | Neither Add-ons nor Custom Service | The merchant accepts that some behavior or history will not migrate.                  |

### WordPress Risk Review Matrix <a href="#wordpress-risk-review-matrix" id="wordpress-risk-review-matrix"></a>

| Review question                      | Low-risk signal                                                                      | Higher-risk signal                                                                          |
| ------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| Is the site mostly standard content? | Posts, CMS Pages, Blog Posts, media, categories, tags, and menus are the main scope. | Custom post types, plugin records, custom tables, or external systems carry business value. |
| Is WooCommerce involved?             | No commerce records are part of WordPress scope.                                     | Products, orders, customers, subscriptions, payment, or checkout behavior are expected.     |
| Is the target content model ready?   | Post types, taxonomies, fields, and templates are already defined.                   | The target model is still undecided.                                                        |
| Are priority URLs known?             | High-value slugs, redirects, metadata, and internal links are documented.            | SEO expectations are assumed rather than evidenced.                                         |
| Are custom requirements scoped?      | Add-ons, Custom Service, and exclusions are separated.                               | Unsupported plugin/custom behavior is treated as standard migration.                        |

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress migration risk is manageable when the project distinguishes native CMS content from plugin data, custom structures, presentation dependencies, SEO routing, user meaning, and WooCommerce or other business layers. The strongest plans define target structures before Full Migration and validate representative examples through Demo Migration.

When custom tables, unsupported plugin data, external IDs, or bespoke workflows carry business value, they should be reviewed as Add-ons, Custom Service, or accepted exclusions rather than hidden inside generic WordPress scope.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why is WordPress migration risky if the site is mostly content?**

Because content may depend on custom fields, templates, media relationships, SEO metadata, menus, redirects, plugins, or builders that are not visible from the page text alone.

**Should WooCommerce data be handled as WordPress data?**

No. WooCommerce is a commerce layer on WordPress. Products, orders, customers, checkout, shipping, payment, tax, coupons, and subscriptions need separate commerce-specific review.

**When does WordPress require Custom Service review?**

Custom Service review is appropriate when the source depends on unsupported plugin tables, custom relationships, custom fields with business logic, external IDs, bespoke workflows, or target implementation-specific interpretation.

**Can Add-ons solve every WordPress custom-data risk?**

No. Add-ons are useful for defined supported needs. Custom Service is more appropriate when the requirement needs custom analysis, unsupported structures, or bespoke handling.

**What should be tested during Demo Migration?**

Test ordinary pages and posts, media-heavy content, custom post types, custom fields, users and roles, plugin-dependent records, priority URLs, redirects, and builder-dependent pages.
