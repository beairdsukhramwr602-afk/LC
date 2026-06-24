# Selecting the Right Migration Approach for WordPress

Selecting the right WordPress migration approach depends on what the target WordPress site must preserve after launch. A simple publishing site may fit a standard migration path, while a plugin-heavy, custom-field-driven, membership, LMS, booking, directory, multilingual, or commerce-connected site may require more review before the service path is clear.

WordPress is flexible because content can live in core records, custom post types, custom taxonomies, metadata, media relationships, users, roles, page-builder layouts, plugin tables, custom tables, themes, menus, widgets, redirects, and external systems. The right approach is therefore not determined by record count alone. It is determined by how much business meaning can be interpreted through supported WordPress structures and how much requires configuration, Add-ons, or Custom Service review.

### What Migration Approach Means for WordPress <a href="#what-migration-approach-means-for-wordpress" id="what-migration-approach-means-for-wordpress"></a>

A WordPress migration approach defines how the migration should be planned, executed, reviewed, and scoped. It should clarify whether the project can stay within supported standard capability, whether Next-Cart-led execution is helpful, whether Add-ons can cover structured adjustments, or whether custom interpretation is needed.

| Approach layer               | WordPress decision question                                                                                              | Practical meaning                                                                                                     |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| Standard Service             | Can the site be migrated through predictable WordPress records and supported fields?                                     | Suitable when CMS Pages, Blog Posts, media, comments, users, categories, tags, and basic metadata are the main scope. |
| Managed Service              | Can the scope stay within standard capability, but the customer wants Next-Cart-led execution?                           | Suitable when execution support and migration handling are the main needs, not custom data interpretation.            |
| Add-ons                      | Are there supported filtering, mapping, or configuration adjustments that improve the result?                            | Useful when the adjustment is structured and supported without bespoke logic.                                         |
| Custom Service               | Does important meaning live in custom post types, plugin records, custom fields, custom tables, or custom relationships? | Required when the migration needs project-specific interpretation, customization, or non-standard handling.           |
| Additional Migration Options | Will later data movement require renewed scope and validation review?                                                    | Relevant when follow-up migration activity may add new records or change migration expectations before launch.        |

The approach should be selected before Full Migration. Demo Migration should then confirm whether the selected path is realistic for the records that matter most.

### Why WordPress Approach Choice Depends on Site Structure <a href="#why-wordpress-approach-choice-depends-on-site-structure" id="why-wordpress-approach-choice-depends-on-site-structure"></a>

WordPress projects can look similar from the front end while having very different migration requirements behind the scenes. One site may use only posts, pages, categories, tags, media, and users. Another may use custom post types, field groups, page-builder data, membership records, events, bookings, LMS progress, directory listings, donations, forms, multilingual relationships, SEO plugin metadata, and external-system IDs.

| WordPress structure                     | Approach implication                                                                                     | Review priority                                                                                                                        |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Core CMS records                        | Usually easier to evaluate through Standard Service or Managed Service.                                  | Confirm titles, content, slugs, authors, media, taxonomies, comments, and statuses.                                                    |
| Custom post types and custom taxonomies | May still be feasible when structures are clear, but often need Custom Service review.                   | Confirm target post types, taxonomy relationships, archive behavior, and templates.                                                    |
| Metadata and custom fields              | Requires field-level review because hidden data may control display, search, filtering, or integrations. | Separate reusable business data from cache, plugin residue, and abandoned fields.                                                      |
| Plugin-owned records                    | Usually approach-sensitive because data ownership may not match standard WordPress entities.             | Identify whether records are memberships, LMS progress, bookings, forms, events, directories, subscriptions, or commerce records.      |
| Builder/theme data                      | Often affects presentation more than entity migration.                                                   | Decide whether layout should be preserved, rebuilt, simplified, or excluded.                                                           |
| SEO and redirects                       | Can be standard or custom depending on permalink and metadata requirements.                              | Confirm high-value URLs, canonical values, slugs, redirects, and internal links.                                                       |
| WooCommerce-connected scope             | Should not be treated as generic WordPress content.                                                      | Separate WordPress CMS data from commerce data such as Products, Customers, Orders, coupons, subscriptions, taxes, and shipping logic. |

A light approach is acceptable only when the site meaning remains understandable after standard data movement. When records depend on plugin logic, custom code, or target implementation decisions, approach selection must become more conservative.

### Standard Service for WordPress <a href="#standard-service-for-wordpress" id="standard-service-for-wordpress"></a>

Standard Service may be enough when the source site mostly uses ordinary WordPress-compatible content and the customer can manage the migration process through the Next-Cart website.

| Standard-fit signal                         | Why it supports Standard Service                                                                           | Watch point                                                                                                 |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Core CMS content is the main scope          | CMS Pages, Blog Posts, media, comments, categories, tags, and users are predictable WordPress records.     | Confirm whether SEO metadata, page hierarchy, and media references are included in the expected result.     |
| Customization is limited                    | Few custom post types, custom fields, or plugin-controlled records are business-critical.                  | Do not ignore hidden metadata that controls display or search.                                              |
| Target WordPress setup is ready             | Permalinks, users, roles, theme assumptions, plugins, and basic settings are available for testing.        | A target site that is not ready can make standard migration results appear incomplete.                      |
| Layout expectations are realistic           | The customer understands that data migration is not the same as full page-builder or theme reconstruction. | Builder layouts, shortcodes, and templates may need separate implementation work.                           |
| WooCommerce is not the main migration scope | The migration is primarily WordPress CMS content rather than commerce records.                             | WooCommerce data should be assessed through the relevant commerce scope, not generic WordPress assumptions. |

Standard Service is not the same as a low-effort launch. WordPress still requires review of slugs, internal links, featured images, post statuses, authors, taxonomy assignments, metadata, and redirects. The key question is whether the result can be achieved through standard capability without bespoke interpretation.

### Managed Service for WordPress <a href="#managed-service-for-wordpress" id="managed-service-for-wordpress"></a>

Managed Service may be safer when the migration can remain within standard capability but the customer wants Next-Cart-led execution and operational support.

| Managed Service signal                       | Why it matters                                                                                                                      | Boundary to preserve                                                                 |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Large standard content volume                | Many CMS Pages, Blog Posts, media files, comments, categories, tags, and users create workload even when the structure is standard. | High volume alone does not make unsupported plugin data supported.                   |
| Customer prefers assisted execution          | The customer wants help running Demo Migration, reviewing results, and preparing Full Migration.                                    | Managed Service changes execution support, not the underlying supported scope.       |
| Add-ons are part of the plan                 | Supported filtering, mapping, or configuration adjustments may need careful execution.                                              | Tailored or unsupported Add-on behavior moves toward Custom Service review.          |
| Launch coordination matters                  | Content freeze, data freshness, final checks, and post-migration review need more coordination.                                     | Launch management should not hide unresolved target-site readiness issues.           |
| Business team has limited migration capacity | The customer can validate results but does not want to manage migration steps independently.                                        | Customer-side validation still remains necessary for content meaning and acceptance. |

Managed Service is appropriate when the migration path is clear but execution discipline matters. It should not be used to avoid Custom Service review when plugin-owned data, custom fields, custom tables, custom user roles, or WooCommerce records define the project outcome.

### How Add-ons Fit Into the WordPress Approach <a href="#how-add-ons-fit-into-the-wordpress-approach" id="how-add-ons-fit-into-the-wordpress-approach"></a>

Add-ons can help when the desired WordPress outcome needs supported adjustments but does not require bespoke migration logic. They are useful for structured scope refinement, mapping, or configuration.

| Add-on type                | WordPress use case                                                                                               | Not a substitute for                                                                             |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Data Filter Add-on         | Migrate only selected CMS Pages, Blog Posts, users, comments, or eligible records according to a supported rule. | Custom logic that decides scope record by record without a clear filter.                         |
| Advanced Data Mapping      | Map supported source fields into supported WordPress fields or metadata where the relationship is clear.         | Complex plugin structures, custom tables, or unsupported relationship fields.                    |
| Advanced Data Configure    | Adjust supported values such as statuses, labels, or selected field values before migration.                     | Bespoke transformation, target plugin configuration, or custom-code interpretation.              |
| Standard Add-ons           | Apply standard optional handling where it fits the supported migration path.                                     | Expanding the service beyond supported entity or field behavior.                                 |
| Tailored or Custom Add-ons | Address more specific supported adjustments when reviewed and agreed.                                            | Replacing Custom Service when the requirement itself needs custom development or interpretation. |

Add-ons should be planned before Full Migration because they affect how Demo Migration should be interpreted. A Demo Migration without the expected Add-ons may not prove the final migration outcome.

### Custom Service for WordPress <a href="#custom-service-for-wordpress" id="custom-service-for-wordpress"></a>

Custom Service is the right path when the WordPress migration depends on customization, custom interpretation, unsupported plugin data, custom fields, custom tables, custom post type logic, custom taxonomy logic, Custom Platform behavior, or project-specific transformation.

| Custom Service trigger                              | Why Standard or Managed Service may be insufficient                                                                                             | Evidence to gather                                                                                     |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Custom post types define the site                   | Records such as events, courses, listings, resources, staff, locations, portfolios, or directories may require target structures and templates. | Export samples, target post type definitions, taxonomy relationships, and template expectations.       |
| Plugin-owned records carry business meaning         | Membership, LMS, booking, donation, form, event, directory, multilingual, or subscription records may not map to ordinary WordPress entities.   | Plugin names, database ownership, record examples, field meanings, and acceptance expectations.        |
| Custom fields control output                        | Metadata may drive display, filters, search, relationships, access, downloads, or integrations.                                                 | Field groups, field types, repeaters, relationship fields, media fields, and target field definitions. |
| Custom tables or external IDs are required          | Important records may live outside standard WordPress tables or depend on external systems.                                                     | Table samples, key relationships, IDs, API references, and downstream system dependencies.             |
| Page-builder layout must be preserved               | Builder data may be serialized, theme-specific, or dependent on target plugins.                                                                 | Target builder availability, layout examples, shortcode usage, and rebuild expectations.               |
| WooCommerce or commerce-plugin records are critical | Products, Customers, Orders, coupons, subscriptions, taxes, and shipping logic are commerce scope, not generic WordPress content.               | Confirm whether the migration should be handled as WooCommerce or another commerce-plugin project.     |

Custom Service does not automatically mean Next-Cart performs every migration-management task. It means the project requires customization, modification, or bespoke handling. Execution ownership should be agreed as part of the final plan.

### Entity Points and WordPress Scope Planning <a href="#entity-points-and-wordpress-scope-planning" id="entity-points-and-wordpress-scope-planning"></a>

Entity Points planning helps customers understand how eligible records affect scope when they are migrated for the first time. For WordPress, the most relevant records may include CMS Pages, Blog Posts, media-related records, users, comments, categories, tags, and other eligible records defined for the migration path.

| Entity Points scenario                                                               | WordPress planning implication                                                                                                                                                                     |
| ------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core CMS records are migrated for the first time                                     | Eligible records should be included in scope estimates before service license selection.                                                                                                           |
| Custom records are eligible and supported                                            | The team should confirm whether they are counted as eligible entities or handled through a reviewed custom scope.                                                                                  |
| New records appear before launch                                                     | New eligible records may consume Entity Points when migrated for the first time.                                                                                                                   |
| A later migration action repeats records already counted through the service license | Those records do not consume Entity Points again simply because another migration action is performed.                                                                                             |
| A new migration is performed for the same migration path                             | Previously counted records still should not be counted again only because the migration action is repeated; new eligible records may still consume Entity Points when migrated for the first time. |

Entity Points estimates should not replace structure review. A small WordPress site with custom fields, plugin records, and custom tables may require more approach review than a large content site with predictable posts and pages.

### Demo Migration as the Approach Decision Point <a href="#demo-migration-as-the-approach-decision-point" id="demo-migration-as-the-approach-decision-point"></a>

Demo Migration should prove whether the selected WordPress approach is realistic. The sample should include simple records and the records most likely to expose approach risk.

| Demo Migration sample                                        | What it proves                                                                        | Approach decision impact                                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Standard CMS Page                                            | Content, slug, hierarchy, featured media, internal links, and metadata behavior.      | Helps confirm Standard Service feasibility.                                            |
| Blog Post with author, media, comments, categories, and tags | Editorial relationships, taxonomy handling, comment history, and media references.    | Confirms whether publishing data remains readable.                                     |
| Custom post type record                                      | Business-specific content meaning and target structure readiness.                     | May confirm supported mapping or trigger Custom Service review.                        |
| Custom-field-heavy record                                    | Metadata preservation, mapping, and target display requirements.                      | Helps decide between Add-ons and Custom Service.                                       |
| Page-builder or shortcode-heavy page                         | Layout and presentation expectations.                                                 | Clarifies whether migration should cover data only or require separate implementation. |
| Plugin-dependent record                                      | Membership, LMS, booking, event, form, donation, directory, or multilingual behavior. | Often determines whether Custom Service review is required.                            |
| SEO-sensitive URL                                            | Slug, permalink, metadata, redirect, canonical, and internal-link continuity.         | Confirms whether additional SEO handling is needed.                                    |
| WooCommerce-connected sample                                 | Product/customer/order or commerce-plugin meaning.                                    | Prevents generic WordPress approach selection from hiding commerce scope.              |

Demo Migration should not be accepted only because simple posts look correct. For WordPress, the records that are hardest to interpret often determine whether the chosen approach is safe.

### How Additional Migration Options Affect Approach Planning <a href="#how-additional-migration-options-affect-approach-planning" id="how-additional-migration-options-affect-approach-planning"></a>

Additional Migration Options matter when the customer expects more data movement after an initial migration activity. In WordPress projects, follow-up handling can affect approach planning when new CMS Pages, Blog Posts, users, comments, media, form submissions, membership updates, custom post type records, or plugin-owned records are created before launch.

| Follow-up situation                    | Approach impact                                                                                | Validation requirement                                                                                       |
| -------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| New standard CMS records are added     | Standard or Managed Service may still be appropriate if the records follow the same structure. | Recheck titles, slugs, media, categories, tags, authors, and statuses.                                       |
| New custom post type records are added | Custom Service review may be needed if the target structure or fields are not already proven.  | Revalidate custom fields, taxonomy relationships, templates, and archive behavior.                           |
| New plugin-owned records are added     | Follow-up handling may be unsafe without confirming plugin data ownership.                     | Review plugin tables, field meaning, user relationships, and target plugin readiness.                        |
| New users or memberships are added     | Access, roles, permissions, and membership states may need renewed review.                     | Confirm user roles, account links, restrictions, and privacy-sensitive fields.                               |
| New commerce-plugin activity appears   | The project may need commerce-specific review rather than generic WordPress handling.          | Separate CMS records from Products, Customers, Orders, coupons, subscriptions, taxes, and shipping behavior. |

Additional Migration Options should be used with renewed validation. They should not be treated as permission to skip scope review, field review, or acceptance testing.

### WordPress Approach Decision Matrix <a href="#wordpress-approach-decision-matrix" id="wordpress-approach-decision-matrix"></a>

| Primary condition                                                                            | Recommended direction                                                           | Reasoning                                                               |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Mostly standard CMS Pages, Blog Posts, media, comments, users, categories, and tags          | Standard Service                                                                | The target meaning fits predictable WordPress structures.               |
| Standard-capability project with limited internal capacity                                   | Managed Service                                                                 | The main need is assisted execution rather than custom interpretation.  |
| Supported filtering, mapping, or value adjustment is required                                | Add-ons with Standard or Managed Service                                        | The adjustment is structured and can be reviewed before Full Migration. |
| Custom post types, custom taxonomies, custom fields, or plugin-owned records define the site | Custom Service review                                                           | Business meaning may not survive through ordinary WordPress records.    |
| WooCommerce or another commerce plugin is central                                            | Commerce-specific review or Custom Service review                               | Commerce records should not be treated as generic WordPress content.    |
| Target requires builder/theme reconstruction                                                 | Separate implementation planning, possibly Custom Service review for data scope | Data migration alone may not reproduce the visual site.                 |
| Follow-up data movement is expected before launch                                            | Additional Migration Options with renewed validation                            | New records and changed structures should be tested before acceptance.  |

The safest approach is the lightest service path that can still preserve the records, relationships, and operational meaning the target WordPress site needs after launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right WordPress migration approach depends on structure, ownership, and target expectations. Standard Service can be enough for predictable CMS content. Managed Service helps when the scope is standard but execution support matters. Add-ons help with supported filtering, mapping, and configuration. Custom Service becomes necessary when custom post types, metadata, plugins, custom tables, WooCommerce scope, or external relationships define the migration outcome.

Demo Migration should confirm the approach with representative records before Full Migration. Additional Migration Options should be paired with renewed validation when more data movement is expected. A WordPress approach is safe only when it reflects how the site actually stores meaning, not just how many visible pages or posts it contains.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a WordPress migration?**

Standard Service may be enough when the migration mainly involves predictable WordPress content such as CMS Pages, Blog Posts, media, comments, users, categories, tags, and supported metadata. If custom post types, plugin records, custom fields, page-builder data, memberships, bookings, LMS records, directories, forms, or WooCommerce records are critical, the project needs deeper review before Standard Service is selected.

**When should a WordPress migration use Managed Service?**

Managed Service is useful when the migration can stay within standard capability but the customer wants Next-Cart-led execution. It is appropriate for workload, coordination, and assisted migration handling. It does not replace Custom Service when the requirement itself depends on unsupported plugin data, custom logic, custom tables, or bespoke field interpretation.

**When does WordPress require Custom Service?**

Custom Service should be reviewed when business meaning lives in custom post types, custom taxonomies, custom fields, metadata, custom tables, page-builder structures, membership records, LMS data, booking records, directory records, form submissions, multilingual relationships, WooCommerce data, or external-system IDs that need project-specific handling.

**Do Add-ons replace Custom Service for WordPress?**

No. Add-ons help with supported filtering, mapping, or configuration. Custom Service is needed when the migration requires unsupported field interpretation, plugin-specific handling, custom table migration, bespoke transformations, Custom Platform interpretation, or project-specific logic adjustment.

**Should Additional Migration Options change the WordPress approach?**

Additional Migration Options should prompt renewed review when new records, plugin data, custom post type entries, user changes, or commerce-related activity appears before launch. They do not automatically change the service path, but they can reveal whether the selected approach remains safe.
