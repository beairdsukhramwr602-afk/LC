# Joomla Pre-Migration Preparation Checklist

Joomla migration preparation should begin with ownership clarity. A Joomla site can hold core CMS records, extension-owned records, template behavior, module assignments, custom fields, access rules, multilingual relationships, and custom implementation logic in the same installation. Preparing only articles and media is not enough if the public site depends on menus, aliases, modules, templates, users, access levels, plugins, or commerce components.

A practical preparation process separates what Joomla core owns from what extensions or custom components own. That separation keeps the migration scope realistic and prevents a common failure: records are transferred, but pages, routes, restricted content, extension views, or commercial workflows no longer make sense in the target environment.

### Define the Target Joomla Role <a href="#define-the-target-joomla-role" id="define-the-target-joomla-role"></a>

The first preparation decision is the role Joomla will play after migration. Joomla may be used as a CMS destination, a site foundation around a commerce extension, a replacement for an older Joomla installation, or the base for a custom Joomla application. Each role changes what evidence must be prepared before migration.

| Target role                  | Preparation focus                                                                                                                    | Risk if ignored                                                                          |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Joomla as CMS destination    | Articles, categories, menus, modules, users, access levels, custom fields, tags, media, aliases, metadata, and language assignments. | Content may migrate but lose visibility, navigation, or routing meaning.                 |
| Joomla around commerce       | Identify which component owns products, customers, orders, checkout logic, tax, shipping, payment, coupons, stock, and store pages.  | Commerce records may be treated as Joomla core content when they belong to an extension. |
| Joomla-to-Joomla replacement | Compare versions, templates, modules, routing, custom fields, extensions, user groups, access levels, and multilingual setup.        | The target may preserve records but lose behavior or page context.                       |
| Custom Joomla implementation | Document custom components, custom tables, plugins, integrations, outside identifiers, and business rules.                           | Custom data may be invisible to standard migration planning and require late rework.     |

This role decision should be made before file export, service selection, or sample testing. It defines what a successful migration must preserve.

### Prepare a Joomla Version and Environment Inventory <a href="#prepare-a-joomla-version-and-environment-inventory" id="prepare-a-joomla-version-and-environment-inventory"></a>

Joomla preparation should include the source and target environment, not only the content database. Version differences can affect extension compatibility, routing behavior, templates, overrides, PHP requirements, update paths, and administrator workflows. Older sites may also include abandoned extensions, custom code, or template frameworks that influence what can be migrated, rebuilt, or excluded.

Prepare an environment inventory that includes:

* source Joomla version and update status;
* target Joomla version and whether the target is clean, rebuilt, or already operational;
* PHP version, database engine, hosting constraints, and server-level assumptions;
* installed templates, template frameworks, child templates, and overrides;
* active, disabled, and abandoned extensions;
* custom plugins, custom components, override files, scripts, cron tasks, and integration jobs;
* administrator access needed for export, review, and target-side configuration.

| Environment item          | Why it matters during migration                                                                         |
| ------------------------- | ------------------------------------------------------------------------------------------------------- |
| Joomla version            | Determines compatibility expectations for templates, extensions, routing, APIs, and update readiness.   |
| Target installation state | A clean target, rebuilt target, or active target changes replacement and validation strategy.           |
| Template framework        | Page appearance and module positions may depend on framework-specific behavior.                         |
| Extension inventory       | Commerce, forms, directories, downloads, memberships, routing, and SEO behavior may be extension-owned. |
| Custom code               | Custom tables, plugins, and overrides can indicate Custom Service requirements.                         |

The goal is not to recreate the old server blindly. The goal is to know which technical conditions affect data meaning, page behavior, and migration scope.

### Inventory Core Content, Menus, and Page Structure <a href="#inventory-core-content-menus-and-page-structure" id="inventory-core-content-menus-and-page-structure"></a>

Joomla content should be prepared as a relationship system. Articles store content, but menus often define public routes, page context, metadata, and navigation entry points. Categories organize content, but they do not always create public pages by themselves. Modules may provide visible page content outside the main article body. Templates and overrides may decide how records appear.

| Joomla area            | What to prepare                                                                                                                     | Why it matters                                                                            |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Articles               | Title, alias, category, intro text, full text, status, access level, author, language, metadata, custom fields, and embedded media. | Articles can migrate but lose page context if related structures are missing.             |
| Categories             | Parent-child hierarchy, aliases, access levels, language assignments, metadata, and archived categories.                            | Categories affect content organization, URL paths, and discovery.                         |
| Menus                  | Menu types, menu items, aliases, item types, parent-child structure, default items, language-specific menus, and linked components. | Menus often control routing, page context, and public navigation.                         |
| Modules                | Module content, positions, ordering, access levels, language, menu assignments, and template position dependencies.                 | A page may appear incomplete if supporting modules are missing or reassigned incorrectly. |
| Media                  | Image paths, file folders, downloadable assets, embedded references, alt text where available, and protected files.                 | Broken media can damage content continuity, product display, and landing pages.           |
| Metadata and redirects | Page titles, descriptions, menu metadata, article metadata, old URLs, and redirect records.                                         | SEO continuity depends on more than article bodies.                                       |

For high-value pages, prepare complete page examples rather than isolated records. A strong example should show the article, menu route, modules, media, access level, language, metadata, and any component view that makes the page work.

### Prepare User, Access, and Permission Evidence <a href="#prepare-user-access-and-permission-evidence" id="prepare-user-access-and-permission-evidence"></a>

Joomla user records are not automatically commerce customers. A Joomla user can represent a site member, editor, administrator, registered visitor, restricted-content subscriber, partner, student, customer login base, or custom application identity. User groups and access levels add further meaning because they control what users can view or manage.

Before migration, prepare:

* user groups and group hierarchy;
* access levels and the groups attached to each level;
* administrator roles and elevated permissions;
* active, blocked, inactive, and obsolete accounts;
* custom profile fields and plugin-owned profile data;
* restricted content examples tied to specific access levels;
* customer-account relationships if a commerce extension connects buyers to Joomla users.

| Identity area           | Preparation question                                                                         | Migration implication                                                                              |
| ----------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Joomla users            | Are users site members, authors, administrators, customers, or custom accounts?              | Account meaning determines what should migrate and how it should be validated.                     |
| User groups             | Do groups control permissions, content visibility, workflows, or customer-like segmentation? | Groups should not be treated as ordinary marketing segments unless that is how the site uses them. |
| Access levels           | Which content, modules, menus, or components depend on restricted visibility?                | Missing access rules can expose private content or hide public content.                            |
| Commerce customer links | Does a commerce component store separate customer profiles, addresses, groups, or orders?    | Customer data may require extension-specific review, not only Joomla user migration.               |

Access preparation should include sensitive examples. Test one public page, one registered-user page, one restricted page, one administrator account, and one user connected to commerce behavior if commerce exists.

### Prepare Multilingual Relationships <a href="#prepare-multilingual-relationships" id="prepare-multilingual-relationships"></a>

Joomla multilingual sites require more than translated article text. A working multilingual site may include language-specific articles, categories, menu trees, modules, aliases, metadata, language associations, template assignments, and extension-owned translations. Migration preparation should identify the full language structure before execution.

| Multilingual element       | What to collect                                                                                | Why it matters                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Language-specific articles | Article IDs, aliases, categories, metadata, publication state, access level, and associations. | Translated content may exist but lose its relationship to other languages.        |
| Language-specific menus    | Menu trees, default pages, aliases, item types, and menu associations.                         | Public routes and navigation can break language by language.                      |
| Language modules           | Switcher modules, menu modules, assigned positions, and visibility rules.                      | Visitors may lose language navigation even when translated content exists.        |
| Extension translations     | Component-specific records, product text, category text, order labels, or custom fields.       | Extension-owned translations may not follow Joomla core content rules.            |
| Default language behavior  | Source and target defaults, fallback assumptions, and homepage routing.                        | Incorrect defaults can redirect visitors or search engines to the wrong language. |

Prepare representative samples for each active language. Do not rely only on source language counts. The target should prove that each language has reachable pages, expected routes, correct menu structure, and relevant translated component content where applicable.

### Identify Extension-Owned Records Before Scope Is Confirmed <a href="#identify-extension-owned-records-before-scope-is-confirmed" id="identify-extension-owned-records-before-scope-is-confirmed"></a>

Joomla’s strength is extensibility, but extension ownership is also one of the largest migration-planning risks. Forms, downloads, directories, galleries, memberships, events, booking systems, SEO tools, page builders, search tools, and commerce components may store data outside ordinary Joomla articles. Some extensions use Joomla users, categories, custom fields, or media; others maintain separate tables and relationships.

Prepare an extension inventory that separates core Joomla records from extension-owned records:

| Extension type                   | Typical preparation evidence                                                                                             | Scope implication                                                                 |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| Commerce component               | Products, categories, customers, orders, coupons, tax, shipping, payment, stock, manufacturers, reviews, and store URLs. | Usually requires platform-specific commerce review.                               |
| Form or contact extension        | Submissions, form definitions, fields, notifications, and integrations.                                                  | May be excluded, rebuilt, or reviewed as custom data depending on business value. |
| Membership or access extension   | Plans, subscriptions, rules, user links, payment history, and protected content.                                         | Often requires Custom Service review if records must migrate.                     |
| Page builder or layout extension | Page layouts, content blocks, widgets, media references, and shortcode-like output.                                      | May require target-side rebuilding or custom evaluation.                          |
| SEO/routing extension            | SEF rules, redirects, canonical settings, metadata, and route overrides.                                                 | SEO continuity may require separate planning and validation.                      |
| Custom component                 | Custom tables, views, controllers, business logic, integrations, and outside IDs.                                        | Strong Custom Service signal.                                                     |

Not every extension record needs to migrate. The preparation task is to decide which extension-owned records are business-critical, which can be rebuilt manually, which should be excluded, and which require Custom Service review.

### Prepare Commerce-Related Joomla Evidence Separately <a href="#prepare-commerce-related-joomla-evidence-separately" id="prepare-commerce-related-joomla-evidence-separately"></a>

When Joomla is used with a commerce extension, preparation should separate the CMS foundation from the store layer. Joomla core can support menus, users, access, modules, templates, multilingual behavior, and URLs. The commerce component may own products, categories, customers, orders, carts, coupons, taxes, shipping, payment methods, stock, reviews, manufacturers, custom fields, and storefront views.

| Commerce preparation area      | What to clarify before migration                                                                                                   |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| Component identity             | Which commerce extension owns the store records, and which version is installed?                                                   |
| Catalog structure              | Products, categories, variants or options, custom fields, manufacturers, images, stock, and visibility.                            |
| Customer and account structure | Relationship between Joomla users and extension-specific customer profiles, addresses, groups, or shopper records.                 |
| Order history                  | Order statuses, line items, totals, tax, shipping, payment labels, coupons, customer links, invoices, and refunds where available. |
| Storefront routing             | Product URLs, category URLs, menu item relationships, aliases, SEO settings, and redirect needs.                                   |
| Checkout behavior              | Payment, shipping, tax, coupons, carts, custom rules, or third-party plugins that may require setup rather than migration.         |

A Joomla migration should not imply that all commerce behavior belongs to Joomla core. If the target is a named commerce extension, prepare evidence according to that extension’s data model. If the target is Joomla without commerce, commerce records should not be assumed to have a native Joomla destination.

### Prepare Service-Path Signals Early <a href="#prepare-service-path-signals-early" id="prepare-service-path-signals-early"></a>

Joomla preparation should identify whether the expected scope fits supported migration behavior, needs Add-ons, or requires Custom Service review. This should happen before Full Migration, not after a failed validation pass.

| Signal                                                                               | Likely planning response                                                                                           |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| Core articles, categories, menus, users, and media are clean and supported.          | Standard Service may be realistic if validation responsibility is clear.                                           |
| Supported records need filtering, mapping adjustment, or configuration control.      | Add-ons may be appropriate when the need stays within supported behavior.                                          |
| The site depends on extension-owned data outside supported coverage.                 | Custom Service review may be needed.                                                                               |
| Custom components, custom tables, outside IDs, or bespoke integrations are required. | Custom Service review is the safer path.                                                                           |
| The target needs careful execution support, sequencing, or stakeholder coordination. | Managed Service may be safer even when records are supported.                                                      |
| Target-side setup is incomplete.                                                     | Prepare Joomla configuration, extension setup, templates, menus, and permissions separately from migrated records. |

This review keeps Add-ons and Custom Service separate. Add-ons help with supported filtering, mapping, or configuration. Custom Service is for unsupported extension data, custom fields, custom components, outside-system identifiers, bespoke transformation, and custom migration logic adjustment.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration should test representative Joomla relationships, not only record counts. A good sample set should include content, routing, access, modules, extension-owned records, and commerce examples where relevant.

| Sample type            | What it should prove                                                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Standard article       | Content, category, alias, metadata, media, and publication state behave as expected.                                                |
| Menu-linked page       | Public route, menu hierarchy, alias, metadata, breadcrumb context, and module assignment are understandable.                        |
| Restricted page        | User group and access-level behavior are preserved or correctly rebuilt.                                                            |
| Multilingual page      | Language assignment, translated route, menu relationship, and association are usable.                                               |
| Module-dependent page  | Supporting modules appear in expected positions and only on intended pages.                                                         |
| Extension-owned record | The relevant component data is included, excluded, rebuilt, or escalated intentionally.                                             |
| Commerce example       | Product, category, customer, order, checkout-related field, or storefront route works according to extension-specific expectations. |
| Custom field example   | Structured values retain business meaning or are clearly outside supported scope.                                                   |

A small but representative sample set is better than a large set of easy records. The sample should expose how Joomla relationships survive migration.

### Plan the Launch Window and Later Migration Activity <a href="#plan-the-launch-window-and-later-migration-activity" id="plan-the-launch-window-and-later-migration-activity"></a>

Many Joomla sites remain active while migration review is underway. New articles, users, form submissions, commerce orders, product updates, comments, media files, redirects, or extension records may appear after Demo Migration. Preparation should define whether later migration activity is expected before launch and what needs revalidation afterward.

| Launch-window situation                                       | Preparation decision                                                                                                                                     |
| ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| New Joomla core records appear after the first migration run. | Plan how new articles, users, media, categories, menus, or redirects will be reviewed.                                                                   |
| Extension-owned records keep changing.                        | Identify whether the extension data can be continued, manually reconciled, or needs Custom Service review.                                               |
| Mapping or filtering needs adjustment after Demo Migration.   | Continue with a new configuration only when changed behavior is clear and revalidated.                                                                   |
| The earlier target result should be replaced.                 | Plan a new migration and validate refreshed target records and previously accepted samples.                                                              |
| New eligible entities are migrated for the first time.        | Account for Entity Points where relevant while remembering that already recorded entities do not consume Entity Points again on the same migration path. |

Later migration activity should be tied to validation responsibility. The team should know what changed, what remained stable, and which target records need another review before launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Joomla migration preparation is strongest when it treats the site as a connected system of content, menus, routes, users, access rules, modules, templates, media, custom fields, multilingual relationships, extensions, and possible commerce components. The preparation task is not to collect every possible setting, but to gather the evidence needed to decide what should migrate, what should be configured, what should be rebuilt, what needs Add-ons, and what requires Custom Service review.

A prepared Joomla migration has clear ownership boundaries, representative samples, extension evidence, route and access planning, target-side setup awareness, and launch-window decisions before migration execution begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Joomla migration?**

Start by defining Joomla’s target role: CMS destination, Joomla-to-Joomla replacement, site foundation around commerce, or custom Joomla implementation. That role determines whether preparation should focus on core content, menus, users, access, extensions, commerce records, custom components, or all of them.

**Why are menus important before Joomla migration?**

Menus influence routing, aliases, navigation, page context, breadcrumbs, metadata, and module assignments. Migrating articles without preparing menu relationships can leave content present in the target but unreachable or SEO-disconnected.

**Should Joomla users be prepared as customer records?**

Not automatically. Joomla users are login and permission records. Commerce customers may belong to an extension and can include addresses, order links, groups, tax fields, or buyer-specific data outside Joomla core.

**When does Joomla preparation indicate Custom Service?**

Custom Service should be considered when required data lives in unsupported extensions, custom components, custom tables, bespoke fields, outside-system identifiers, or custom business logic beyond supported migration behavior.

**How should Joomla Demo Migration samples be selected?**

Choose samples that expose relationships: one article, one menu-linked page, one restricted page, one multilingual page, one module-dependent page, one extension-owned record, one commerce record if relevant, and one custom field or custom data example.
