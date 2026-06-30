# WordPress Pre-Migration Preparation Checklist

WordPress preparation should prove how the site will operate after migration, not only which database records or files can be transferred. A WordPress site may contain posts, pages, custom post types, taxonomies, media, menus, users, comments, metadata, block content, builder content, plugin settings, theme dependencies, redirects, and integrations. Some of those records may be standard WordPress content. Some may belong to plugins, custom code, external systems, or a commerce layer such as WooCommerce.

Preparation should therefore classify content by ownership and future use. The strongest WordPress migration plan defines what should migrate as supported content, what must be rebuilt or configured in WordPress, what requires Add-ons, what requires Custom Service review, and what should be intentionally excluded. This keeps the migration scope practical while protecting the site’s editorial, SEO, publishing, and operational continuity.

### Define the Target WordPress Role First <a href="#define-the-target-wordpress-role-first" id="define-the-target-wordpress-role-first"></a>

The first preparation decision is the role WordPress will play after migration. WordPress can be a content publishing environment, a brand website, a documentation site, a blog-led storefront, a landing-page system, a membership site, a multilingual content site, or the CMS layer around a WooCommerce store. Each role changes the evidence that must be prepared.

A content-only site may need careful post, page, taxonomy, media, author, and URL preparation. A publishing-heavy site needs stronger attention to categories, tags, authors, archives, comments, redirects, featured images, and metadata. A plugin-heavy site may need custom post type, shortcode, block, custom table, and integration review. A WordPress site that also uses WooCommerce needs scope separation: WordPress preparation should cover the CMS and site architecture, while WooCommerce preparation should own products, product variations, orders, checkout behavior, payment context, shipping, taxes, coupons, and customer commerce records.

| Target WordPress role      | Preparation priority                                                                     | Why it matters                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Content website            | Pages, posts, menus, media, metadata, URLs, redirects.                                   | The migration must preserve discoverable, readable, editable content.                  |
| Blog or publication        | Posts, categories, tags, authors, comments, archives, featured images.                   | Editorial history and traffic continuity depend on relationships, not just post count. |
| Plugin-driven site         | Custom post types, custom taxonomies, metadata, custom tables, shortcodes, integrations. | Standard content migration may not capture plugin-owned behavior.                      |
| Membership or account site | Users, roles, permissions, profiles, protected content, plugin ownership.                | User records and access rules may not translate as ordinary content.                   |
| WordPress plus WooCommerce | CMS scope plus commerce scope separation.                                                | Content and commerce data need connected planning without merging responsibilities.    |

This role definition should be completed before sample selection. Otherwise, Demo Migration may test easy pages while missing the records that actually determine whether the WordPress target is usable.

### Prepare Core Content and Site Structure <a href="#prepare-core-content-and-site-structure" id="prepare-core-content-and-site-structure"></a>

Core WordPress preparation should start with the content types the merchant expects to use after launch. Standard posts and pages usually matter, but the surrounding structure can matter just as much: authors, publish dates, slugs, parent pages, categories, tags, featured images, comments, excerpts, menus, media references, and SEO metadata can all affect how the migrated site works.

The merchant should prepare representative examples from each content area rather than relying only on totals. A page count can confirm volume, but it does not prove that page hierarchy, block content, images, embedded media, internal links, menus, or redirects will work. A post count can confirm editorial size, but it does not prove that categories, tags, authors, archives, and comment context remain useful.

| Content area         | Evidence to prepare                                                       | Review purpose                                                          |
| -------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Pages                | Parent/child pages, landing pages, policy pages, forms, embedded content. | Confirms hierarchy, layout dependencies, and internal links.            |
| Posts                | Recent posts, older posts, high-traffic posts, posts with comments.       | Confirms editorial history, archives, authors, and public presentation. |
| Categories and tags  | Main categories, nested structures, high-use tags, unused terms.          | Confirms classification and archive behavior.                           |
| Menus and navigation | Primary menu, footer menu, contextual menus, custom links.                | Separates content migration from navigation setup.                      |
| Media library        | Featured images, galleries, PDFs, downloadable files, reused images.      | Confirms media attachment, display, and file-reference continuity.      |
| Comments             | Approved comments, pending comments, spam/irrelevant comments if present. | Clarifies what should migrate and what should be excluded.              |

Preparation should also identify content that should not migrate. Old drafts, test pages, outdated landing pages, duplicate media, broken embeds, obsolete tags, and irrelevant comments can create noise in the target site. A migration is often the right moment to preserve important history while avoiding unnecessary clutter.

### Prepare Custom Post Types and Taxonomies <a href="#prepare-custom-post-types-and-taxonomies" id="prepare-custom-post-types-and-taxonomies"></a>

Custom post types and custom taxonomies are one of the most important WordPress preparation areas because they can look like normal content while depending on plugin or theme registration. WordPress can store custom post type content alongside other post types, but the target site must be able to recognize and display that content correctly after migration.

Examples include portfolio items, testimonials, events, case studies, downloads, directory entries, real estate listings, documentation entries, courses, recipes, product-like content outside WooCommerce, or any plugin-defined content structure. Custom taxonomies may classify those records with topics, locations, industries, brands, series, event types, resource types, or other custom grouping systems.

| Custom structure    | Preparation question                                                        | Possible handling path                                                         |
| ------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Custom post type    | Which plugin, theme, or custom code registers it?                           | Supported migration, Custom Service, or target rebuild depending on ownership. |
| Custom taxonomy     | Is it hierarchical or flat, and which records use it?                       | Supported mapping, Add-on, or Custom Service if behavior is non-standard.      |
| Custom fields       | Are values editorial, display-related, SEO-related, or integration-related? | Supported fields, Add-ons, Custom Service, or exclusion.                       |
| Archive pages       | Does the post type need public archive behavior?                            | WordPress setup, theme configuration, or custom development.                   |
| Template dependency | Does the content rely on a theme or builder template?                       | Target-side setup or Custom Service review.                                    |

A good preparation package should include at least one sample record for each meaningful custom post type and taxonomy. For each sample, identify the source owner, field set, public URL, related taxonomy terms, media usage, and target expectation. Without that evidence, custom structures may be counted as content but fail as usable WordPress records.

### Prepare Metadata, Custom Fields, and Plugin-Owned Data <a href="#prepare-metadata-custom-fields-and-plugin-owned-data" id="prepare-metadata-custom-fields-and-plugin-owned-data"></a>

WordPress metadata can carry significant business meaning. Post meta, user meta, term meta, plugin fields, builder fields, SEO fields, redirect settings, form entries, membership fields, event details, directory fields, and structured content values may all be stored outside the visible post body. Preparation should decide whether those values are part of the migration scope, target-side setup, Custom Service review, or accepted exclusion.

The most important distinction is ownership. A field may be visible in the WordPress admin, but that does not mean it is ordinary WordPress content. It may be created by a plugin, a theme, custom code, a page builder, a SEO tool, a form tool, a membership plugin, a translation plugin, or an external integration.

| Data type             | Preparation action                                                               | Why it matters                                                               |
| --------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| SEO metadata          | Identify titles, descriptions, canonicals, social fields, schema-related fields. | SEO continuity may depend on fields outside the content body.                |
| Page builder data     | Identify builder plugin, layout storage, reusable templates, global blocks.      | Content may render poorly if builder data or target setup is missing.        |
| Shortcodes and embeds | List critical shortcode patterns and embedded content.                           | Migrated text may show broken shortcodes if supporting plugins are absent.   |
| Form entries          | Decide whether submissions should migrate or remain archived elsewhere.          | Forms often store data in plugin-specific tables.                            |
| Membership fields     | Identify roles, access rules, profiles, subscriptions, and protected content.    | User and access behavior may require Custom Service or target configuration. |
| Custom tables         | List plugin or custom tables with business-critical data.                        | Standard content migration may not include them.                             |

Add-ons may help when the data remains within supported filtering, mapping, or configuration behavior. Custom Service should be considered when the requirement involves unsupported plugin data, custom fields, custom tables, bespoke transformation, external identifiers, or custom migration logic adjustment.

### Prepare Users, Roles, Authors, and Access Expectations <a href="#prepare-users-roles-authors-and-access-expectations" id="prepare-users-roles-authors-and-access-expectations"></a>

User preparation should separate author identity, administrative access, subscriber records, membership records, and commerce customer records. WordPress roles and capabilities determine what users can do inside the site, but user meaning varies widely across sites. A user may be an author, editor, administrator, subscriber, customer, member, instructor, vendor, directory owner, forum participant, or imported account from another system.

The merchant should prepare user samples by use case rather than by count only. For a publication, authors and editors may matter most. For a membership site, roles, access rules, user meta, protected content, and plugin ownership matter more. For a WooCommerce site, customer commerce records should be planned in the WooCommerce hub, while WordPress still needs to account for the user accounts and roles that support site access.

| User-related area     | Evidence to prepare                                            | Scope note                                                                      |
| --------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Authors               | Users tied to important posts or pages.                        | Needed for editorial continuity.                                                |
| Editors/admins        | Active staff accounts and required roles.                      | Often target-side setup and security review, not simple migration.              |
| Subscribers           | Subscriber records, newsletter connections, membership status. | May involve plugin or external-system ownership.                                |
| User metadata         | Profile fields, preferences, membership fields, IDs.           | May require mapping, Custom Service, or exclusion.                              |
| Passwords/access      | Authentication expectations and reset plan.                    | Password behavior should not be assumed without platform-specific confirmation. |
| WooCommerce customers | Commerce accounts and order associations.                      | Belongs mainly to WooCommerce migration planning.                               |

Preparation should avoid migrating unnecessary admin accounts, inactive users, spam accounts, or compromised records. User migration affects security and governance, not only content ownership.

### Prepare Media, Blocks, Builders, Themes, and Navigation <a href="#prepare-media-blocks-builders-themes-and-navigation" id="prepare-media-blocks-builders-themes-and-navigation"></a>

WordPress presentation depends on more than content records. A migrated page may carry the correct text but lose its intended meaning if media files, image sizes, reusable blocks, block patterns, page-builder structures, menus, widgets, theme templates, or shortcodes are not prepared.

The target WordPress environment should be reviewed as an editable site, not only as a database. The merchant should decide which presentation elements are migration scope, which are rebuild tasks, which belong to theme or builder setup, and which can be retired.

| Presentation layer | Preparation question                                                       | Typical outcome                                            |
| ------------------ | -------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Media files        | Are image/file paths, featured images, galleries, and documents available? | Migrate, relink, replace, or archive.                      |
| Blocks             | Does content use core blocks, reusable blocks, or custom blocks?           | Validate rendering and editing after migration.            |
| Page builders      | Which builder owns layout data?                                            | Target plugin setup, Custom Service, or manual rebuild.    |
| Menus              | Which menus are active and where do they appear?                           | Target-side navigation setup plus validation.              |
| Widgets/sidebars   | Are widgets still used or theme-dependent?                                 | Rebuild, replace, or retire.                               |
| Theme templates    | Does content depend on template files or theme settings?                   | Theme implementation task, not ordinary content migration. |

This preparation prevents a common WordPress problem: approving content because records exist while the public site still feels incomplete, broken, or difficult to edit.

### Prepare URLs, Redirects, SEO, and Search Continuity <a href="#prepare-urls-redirects-seo-and-search-continuity" id="prepare-urls-redirects-seo-and-search-continuity"></a>

WordPress migration can affect search visibility when slugs, permalink structures, taxonomies, archives, media URLs, pagination, canonical fields, or plugin-generated URLs change. Preparation should identify the pages and posts that matter most before migration, not after traffic drops.

The merchant should collect priority URLs, high-traffic pages, high-value posts, important category or tag archives, redirect rules, SEO metadata, canonical expectations, XML sitemap behavior, internal link patterns, and media/document URLs. If WooCommerce is part of the same site, product, category, cart, checkout, account, and order-related URLs should be handled in the WooCommerce workflow rather than diluted inside the WordPress CMS scope.

| SEO/URL input               | Preparation purpose                                                 |
| --------------------------- | ------------------------------------------------------------------- |
| Priority URL list           | Protects high-value landing paths and search traffic.               |
| Current permalink structure | Helps detect slug or path changes after migration.                  |
| Redirect map                | Defines old-to-new handling for changed URLs.                       |
| SEO metadata export         | Preserves fields that may not live in the visible page body.        |
| Internal link samples       | Confirms whether links point to valid target content.               |
| Archive pages               | Protects category, tag, author, date, and custom taxonomy archives. |
| Media/document URLs         | Prevents broken downloads and image references.                     |

Redirect planning should be specific. A broad statement that redirects will be handled later is not enough for a content-heavy WordPress migration. The preparation should identify which URLs are business-critical, which can be redirected broadly, and which can be intentionally retired.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration should test the WordPress structures most likely to reveal scope problems. The sample set should be compact enough to review thoroughly and diverse enough to expose content, metadata, plugin, user, media, and URL risks.

| Sample type             | What it should prove                                                         |
| ----------------------- | ---------------------------------------------------------------------------- |
| Standard page           | Page hierarchy, body content, media, internal links, and editability.        |
| Standard post           | Author, date, category, tag, featured image, comments, and archive behavior. |
| Custom post type record | Whether custom structure survives and displays correctly.                    |
| Custom taxonomy example | Whether grouping and archive expectations remain usable.                     |
| Metadata-heavy page     | Whether SEO, custom fields, or builder values are handled correctly.         |
| Media-rich page         | Whether images, galleries, documents, and embedded content remain connected. |
| User/author example     | Whether user identity and content ownership are preserved.                   |
| Priority URL            | Whether redirect and permalink assumptions are valid.                        |
| Plugin-owned example    | Whether Add-ons, Custom Service, setup, or exclusion is needed.              |

Demo Migration should decide whether the selected approach is sufficient. If custom post types, metadata, builder content, user roles, redirects, or plugin-owned records fail the sample review, the plan should be corrected before Full Migration.

### Prepare Service Scope and Launch-Window Decisions <a href="#prepare-service-scope-and-launch-window-decisions" id="prepare-service-scope-and-launch-window-decisions"></a>

WordPress preparation should conclude with a clear service-scope decision. Standard Service may be enough when the scope is ordinary supported WordPress content and the merchant can validate the result. Managed Service may be safer when the site is large, content-heavy, operationally sensitive, or difficult for the merchant to coordinate alone. Add-ons may be relevant when supported filtering, mapping, or configuration needs are clear. Custom Service should be considered when plugin data, custom fields, custom tables, external IDs, builder dependencies, membership behavior, or custom migration logic adjustment must be handled beyond supported behavior.

The launch window also matters. Content may continue changing between Demo Migration and launch. New posts, pages, media files, users, comments, or URL changes may appear. The merchant should plan whether later migration activity will continue with the last used configuration, continue with a new configuration, or require a new migration into a refreshed target result. This planning should remain role-specific; it is useful when it affects WordPress readiness, not as a standalone feature explanation.

| Decision area            | Preparation output                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------- |
| Supported content scope  | Confirm posts, pages, taxonomies, media, comments, and supported records.                         |
| Add-ons need             | Define filtering, mapping, or configuration requirements within supported behavior.               |
| Custom Service need      | Identify unsupported plugin/custom data, custom fields, custom tables, or bespoke transformation. |
| Target setup             | Separate themes, plugins, menus, redirects, roles, and templates from migrated data.              |
| Later migration activity | Decide how new or changed source records will be handled before launch.                           |
| Accepted exclusions      | Document what should not migrate and why.                                                         |

A strong preparation package is specific enough that the migration path can be selected and evaluated without guessing.

### Conclusion <a href="#conclusion" id="conclusion"></a>

WordPress preparation should focus on evidence, ownership, and launch usability. The merchant should define the target WordPress role, prepare core content, classify custom post types and taxonomies, identify metadata and plugin-owned data, review users and roles, gather media and presentation dependencies, protect URLs and SEO, choose Demo Migration samples, and separate supported migration scope from Add-ons, Custom Service, target-side setup, and accepted exclusions.

A WordPress migration is ready to proceed when the team can explain what each important record means in the target site, how it should be displayed or edited, which dependencies must be configured, and which samples must pass before launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a WordPress migration?**

Start by defining the target role of WordPress after migration. A content site, publication, membership site, plugin-driven site, and WordPress plus WooCommerce environment require different evidence and validation samples.

**Should custom post types be prepared separately from standard posts and pages?**

Yes. Custom post types may depend on plugins, themes, or custom code. Prepare sample records, taxonomies, metadata, public URLs, and target expectations before assuming they can migrate like standard posts or pages.

**Do WordPress plugins automatically migrate with content data?**

No. Plugin-owned records, settings, custom tables, shortcodes, builder layouts, memberships, form entries, and integrations may require setup, Add-ons, Custom Service review, manual rebuild, or exclusion depending on the requirement.

**How should WordPress URL and SEO preparation be handled?**

Prepare priority URLs, permalink structures, redirect rules, SEO metadata, archive pages, internal links, and media/document URLs. High-value pages and posts should be tested during Demo Migration rather than left for launch-week cleanup.

**When should Custom Service be considered for WordPress preparation?**

Custom Service should be considered when the migration requirement involves unsupported plugin data, custom post type behavior, custom fields, custom tables, external identifiers, bespoke transformation, or custom migration logic adjustment beyond supported behavior.
