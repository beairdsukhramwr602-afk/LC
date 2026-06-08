# Joomla Pre-Migration Preparation Checklist

Joomla migration preparation starts with one important assumption: the Joomla installation may contain more than one kind of data owner. Joomla core can own content, categories, menus, users, access rules, media, custom fields, tags, templates, and site structure. Commerce behavior, however, may belong to an installed e-commerce extension, a custom component, plugin-owned records, integration logic, or a Custom Platform implementation.

A clean preparation process separates Joomla core site structure from extension-owned commerce data before the migration path is configured. That separation protects the project from a common mistake: preparing only visible storefront content while leaving menus, routing, modules, access levels, multilingual associations, template dependencies, or commerce-component records unclear.

### Start with the Actual Joomla Target Role <a href="#start-with-the-actual-joomla-target-role" id="start-with-the-actual-joomla-target-role"></a>

Preparation should define what the target Joomla environment is expected to become. Joomla may be the site foundation, a CMS destination for content and users, the environment around a Joomla commerce extension, or the base for a custom Joomla implementation. Each case requires different evidence before migration begins.

| Target Joomla role                 | Preparation focus                                                                                                                                                                             | Main risk if skipped                                                                             |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Joomla as CMS foundation           | Confirm articles, categories, menus, modules, templates, users, access levels, fields, tags, media, aliases, and language structure.                                                          | Migrated content may exist but not behave like the intended site.                                |
| Joomla around a commerce extension | Identify the extension that owns products, customers, orders, checkout behavior, tax, shipping, payment, coupons, stock, and store pages.                                                     | Store records may be treated as generic Joomla data instead of extension-owned commerce data.    |
| Custom Joomla implementation       | Document custom tables, custom components, plugin-owned logic, outside identifiers, and integration dependencies.                                                                             | Custom behavior may be invisible during standard planning and require rework after migration.    |
| Joomla to Joomla                   | Compare source and target versions, extension compatibility, menu structures, aliases, templates, modules, access rules, custom fields, multilingual setup, and commerce extension ownership. | A migration may preserve records but lose behavior, routing, permissions, or storefront meaning. |

When Joomla is connected to commerce, preparation should confirm whether the store behavior belongs to a Joomla extension, another supported source system, or a custom implementation.

### Confirm the Joomla Version and Environment <a href="#confirm-the-joomla-version-and-environment" id="confirm-the-joomla-version-and-environment"></a>

Joomla version differences affect extension compatibility, template behavior, routing, available APIs, custom development assumptions, and long-term maintainability. Preparation should confirm the source and target Joomla versions rather than relying on a generic Joomla label.

Review the following early:

* Joomla version and update status;
* PHP version and hosting environment requirements;
* database engine and database version;
* installed templates and template framework dependencies;
* active extensions, disabled extensions, and abandoned extensions;
* custom code, overrides, plugins, cron tasks, or integration scripts;
* target installation version and whether the target is a clean Joomla build, rebuilt site, or existing operational installation.

Older operational installations may require version-specific review, especially when they depend on legacy templates, modified components, or extensions that are no longer actively maintained.

### Inventory Joomla Core Content and Site Architecture <a href="#inventory-joomla-core-content-and-site-architecture" id="inventory-joomla-core-content-and-site-architecture"></a>

Joomla core content is not just a list of pages. Article meaning is shaped by categories, menus, aliases, modules, access levels, language associations, custom fields, tags, media, and templates.

| Area to review         | What to prepare                                                                                                                               | Why it matters                                                                                       |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Articles               | Article inventory, publication state, authorship, access level, language, aliases, metadata, intro/full text behavior, and custom fields.     | Content may migrate without the context that controls visibility, routing, and page meaning.         |
| Categories             | Category tree, parent-child relationships, access levels, language assignments, aliases, and metadata.                                        | Category structure affects content grouping, URLs, menus, and discovery.                             |
| Menus                  | Menu items, menu types, aliases, item types, parent-child hierarchy, default menu items, language-specific menu trees, and linked components. | Joomla routing and visible site navigation depend heavily on menus.                                  |
| Modules                | Module inventory, positions, assignments, access rules, language settings, ordering, and template-position dependencies.                      | Important content blocks may disappear or display on the wrong pages after migration.                |
| Templates              | Active templates, child templates if relevant, template styles, overrides, module positions, layout settings, and framework dependencies.     | Migrated content may not reproduce storefront or site behavior if the template layer is not planned. |
| Media                  | Image paths, downloadable files, folder structure, embedded media references, and external media dependencies.                                | Broken media references can undermine content, catalog, and landing-page validation.                 |
| Tags and custom fields | Field groups, field types, assigned contexts, validation rules, display assumptions, and tagged content relationships.                        | Custom meaning may be lost if fields are treated as plain text or ignored.                           |

The goal is not to document every administrative setting. The goal is to identify which structures must exist, be mapped, or be rebuilt so migrated records continue to make sense inside Joomla.

### Identify the Commerce Component Before Preparing Commerce Data <a href="#identify-the-commerce-component-before-preparing-commerce-data" id="identify-the-commerce-component-before-preparing-commerce-data"></a>

Joomla core does not provide one universal native product, cart, checkout, payment, shipping, tax, coupon, inventory, or order model. Commerce preparation must start by identifying the extension or custom implementation that owns store data.

When the target is a named Joomla commerce extension, preparation should follow the extension-specific commerce model. When the target is Joomla itself, preparation should focus on Joomla core structures, content, users, menus, modules, and custom Joomla data.

Prepare the commerce layer by confirming:

* the installed commerce extension name and version;
* whether the extension is within standard supported coverage or needs Custom Service review;
* whether the target is Joomla itself or a specific Joomla commerce extension;
* product, category, customer, order, tax, shipping, payment, coupon, manufacturer, review, and media ownership inside the extension;
* extension-specific custom fields, option structures, variant structures, order statuses, customer groups, and storefront URLs;
* modified database tables, custom plugins, third-party integrations, or outside-system identifiers;
* whether any data belongs outside the supported standard service capability and may require Custom Service review.

When the target is a known Joomla commerce extension, preparation should follow that extension’s platform-specific behavior rather than relying on general Joomla assumptions.

### Prepare Users, User Groups, Access Levels, and Permissions <a href="#prepare-users-user-groups-access-levels-and-permissions" id="prepare-users-user-groups-access-levels-and-permissions"></a>

Joomla user records may not mean the same thing as customer records inside a commerce extension. A Joomla user can represent a site member, administrator, author, editor, registered visitor, customer login base, or custom application account depending on the implementation.

Before migration, prepare:

* user groups and parent-child hierarchy;
* access levels and which groups can view specific content or modules;
* user activation status and blocked status;
* administrator accounts and elevated permissions;
* customer account links if a commerce extension uses Joomla users as account identities;
* role-related custom fields or plugin-owned profile fields;
* privacy, consent, and account-retention decisions for inactive or obsolete accounts.

Do not assume Joomla users automatically equal commerce customers. If a commerce extension stores customer profiles, addresses, groups, tax details, loyalty data, or order ownership separately, that relationship must be reviewed before migration.

### Review Menus, Aliases, Routing, and SEO Dependencies <a href="#review-menus-aliases-routing-and-seo-dependencies" id="review-menus-aliases-routing-and-seo-dependencies"></a>

Joomla URLs are strongly influenced by menus, aliases, category hierarchy, language configuration, routing settings, and extension behavior. Preserving articles without preserving route logic may still lead to broken URLs, changed canonical pages, or weakened navigation.

Prepare a routing inventory that includes:

* important current URLs and their source menu-item relationships;
* high-value landing pages, category pages, product pages, blog-like content, and policy pages;
* aliases for articles, categories, menus, and commerce records;
* menu item types that point to specific components or views;
* multilingual menu associations and language-specific home pages;
* redirects already configured inside the source site;
* external SEO dependencies such as indexed URLs, backlinks, paid landing pages, and tracked campaign URLs.

For Joomla commerce extensions, confirm whether product and category routes are controlled by Joomla menus, extension routing, plugin rules, or custom SEF behavior. The migration plan should preserve business-critical discovery paths even when the target route format changes.

### Prepare Multilingual Structure <a href="#prepare-multilingual-structure" id="prepare-multilingual-structure"></a>

Joomla multilingual sites can include language-specific content, menu trees, categories, modules, template styles, associations, language tags, and default language rules. A shallow content export may not preserve how languages relate to each other.

Preparation should confirm:

* installed content languages and enabled language plugins;
* language-specific menus and default home pages;
* article, category, menu, module, and commerce-record language assignments;
* multilingual associations between equivalent records;
* untranslated records that intentionally fall back to a default language;
* language-specific aliases, metadata, media, and template behavior;
* commerce extension support for multilingual product, category, checkout, email, and order-facing content.

If multilingual associations are business-critical, they should be included in sample planning for Demo Migration and later validation.

### Review Templates, Modules, Layouts, and Frontend Dependencies <a href="#review-templates-modules-layouts-and-frontend-dependencies" id="review-templates-modules-layouts-and-frontend-dependencies"></a>

Joomla site behavior often depends on the relationship between content, menus, modules, templates, template styles, overrides, and layout rules. Migration preparation should determine whether the target site is intended to reproduce the current frontend, rebuild it, or preserve only data and core structure.

Prepare evidence for:

* active template and template style assignments;
* template overrides that affect component output;
* module positions and page assignments;
* page-builder or template-framework content if used;
* extension-specific layout overrides;
* embedded shortcodes, plugin syntax, widgets, scripts, or content placeholders;
* checkout, catalog, account, or landing-page layout dependencies if commerce is involved.

When frontend behavior is heavily customized, the migration plan may need Custom Service review or separate implementation work beyond standard data movement.

### Identify Custom Fields, Tags, Plugin-Owned Records, and Custom Tables <a href="#identify-custom-fields-tags-plugin-owned-records-and-custom-tables" id="identify-custom-fields-tags-plugin-owned-records-and-custom-tables"></a>

Joomla sites often carry business meaning outside visible page text. Custom fields, tags, plugin-owned records, custom database tables, and integrations may hold structured data that matters to content, catalog, accounts, workflows, or reporting.

Prepare an inventory of:

* Joomla custom field groups, field types, contexts, and values;
* custom fields owned by commerce extensions;
* plugin-owned profile fields, membership records, subscription data, booking records, downloads, or loyalty records;
* custom database tables and their relationship to Joomla users, content, categories, products, or orders;
* external identifiers from ERP, CRM, marketplace, accounting, shipping, or fulfillment systems;
* synchronization rules or integrations that may need to continue after migration.

Unsupported extension data, custom database tables, outside-system identifiers, bespoke relationships, and custom migration logic adjustment are Custom Service review signals.

### Prepare a Demo Migration Sample Plan <a href="#prepare-a-demo-migration-sample-plan" id="prepare-a-demo-migration-sample-plan"></a>

Demo Migration is most useful when the sample represents the real complexity of the Joomla installation. A sample made only from simple articles or simple products can create false confidence.

A stronger Joomla sample should include:

| Sample area                 | Include examples that prove                                                                                                                                    |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Content structure           | Articles with categories, aliases, metadata, custom fields, tags, media, and access rules.                                                                     |
| Navigation                  | Menu items that control important routes, nested menus, language-specific menus, and component-linked menu items.                                              |
| Modules and templates       | Modules assigned to important pages, template-style differences, and layout dependencies.                                                                      |
| Users and access            | Users from different groups, restricted content, customer-linked accounts, and administrative exclusions where relevant.                                       |
| Multilingual content        | Associated records across languages, translated menus, language-specific aliases, and fallback cases.                                                          |
| Commerce extension data     | Products, categories, variants/options, customers, orders, statuses, taxes, shipping, payments, coupons, reviews, and media owned by the identified extension. |
| Custom or plugin-owned data | Records from custom fields, plugins, integrations, or custom tables that must be preserved or reviewed.                                                        |

Sample planning should reflect risk concentration, not just record count. One complex multilingual product with custom fields, route dependencies, media, and order history can reveal more than a large batch of simple records.

### Decide What Should Be Cleaned Before Migration <a href="#decide-what-should-be-cleaned-before-migration" id="decide-what-should-be-cleaned-before-migration"></a>

Some issues should be corrected before migration because they create avoidable noise in the result. Others should be preserved because they carry historical meaning. Preparation should distinguish cleanup from data loss.

Consider reviewing:

* unpublished, archived, trashed, duplicate, or obsolete articles;
* broken categories or unused menu items;
* old modules assigned to retired pages;
* unused templates and abandoned extensions;
* duplicate aliases or inconsistent route patterns;
* inactive users, blocked accounts, and obsolete administrator accounts;
* orphaned media files or broken media references;
* old commerce records that should remain for history but not appear as active storefront data;
* test orders, demo products, staging records, or duplicate customer profiles.

Filtering or selective handling should be planned carefully. Entered entity quantities are used for Entity Points Plan estimation and are not migration filters. When filtering is required, review whether a Data Filter Add-on, Advanced Data Mapping, Advanced Data Configure, Tailored Add-on, Custom Add-on, or broader Custom Service review is appropriate.

### Escalation Signals to Identify Before Execution <a href="#escalation-signals-to-identify-before-execution" id="escalation-signals-to-identify-before-execution"></a>

A Joomla migration may be straightforward when the source and target are clean, supported, well-documented, and structurally predictable. Escalation becomes more likely when the Joomla implementation carries custom logic or unclear data ownership.

Early escalation signals include:

* the commerce extension is unknown, unsupported, heavily modified, abandoned, or version-sensitive;
* the source or target uses Custom Platform handling;
* product, customer, order, route, access, or multilingual meaning depends on custom code;
* important data lives in third-party extensions, plugin-owned tables, or custom database tables;
* user records must be linked to commerce customers in a non-standard way;
* custom fields carry business-critical meaning that cannot be flattened;
* route preservation depends on menus, aliases, SEF plugins, or custom routing behavior;
* the target Joomla environment is not ready or the intended commerce component is not confirmed;
* migration rules require bespoke transformation or custom migration logic adjustment.

These signals do not automatically mean the project requires Next-Cart-led migration management. They do mean the migration plan should be reviewed for Standard Service, Managed Service, Add-ons, and Custom Service boundaries before execution.

### Joomla Pre-Migration Readiness Checklist <a href="#joomla-pre-migration-readiness-checklist" id="joomla-pre-migration-readiness-checklist"></a>

Use the checklist below to confirm that preparation covers the site’s actual operating structure.

| Readiness area          | Confirm before migration                                                                                                                                         |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Joomla target role      | Joomla core, Joomla extension, or custom Joomla implementation is confirmed.                                                                                     |
| Version and environment | Source and target Joomla versions, hosting requirements, PHP, database, and extension compatibility are understood.                                              |
| Core content            | Articles, categories, metadata, aliases, custom fields, tags, access rules, media, and publication states are reviewed.                                          |
| Menus and routing       | Menu trees, aliases, default pages, language-specific menus, redirects, and high-value URLs are identified.                                                      |
| Users and access        | Users, user groups, access levels, permissions, and customer-account relationships are documented.                                                               |
| Templates and modules   | Active templates, template styles, overrides, module positions, page assignments, and layout dependencies are reviewed.                                          |
| Multilingual setup      | Languages, associations, translated menus, language-specific modules, and fallback expectations are confirmed.                                                   |
| Commerce ownership      | The commerce extension or custom implementation that owns product, order, checkout, payment, shipping, tax, coupon, and customer-commerce meaning is identified. |
| Extension data          | Third-party extension records, plugin-owned data, custom fields, custom tables, and integration identifiers are reviewed.                                        |
| Demo Migration sample   | Sample records include high-risk content, routing, access, multilingual, media, extension-owned commerce, and custom-data cases.                                 |
| Service boundary        | Add-on needs and Custom Service review signals are separated before execution.                                                                                   |
| Cleanup decisions       | Records to preserve, exclude, filter, archive, or review are defined without confusing estimates with filters.                                                   |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Joomla pre-migration preparation should prove what the site actually is before data is moved. A Joomla installation may combine CMS content, navigation, templates, modules, users, access rules, languages, extensions, custom fields, media, routing logic, and extension-owned commerce records. Preparing only product-like or page-like records is not enough when business meaning depends on the surrounding Joomla structure.

A reliable preparation process identifies the Joomla role in the migration path, confirms the commerce owner where commerce exists, documents the structures that control behavior, and builds a Demo Migration sample that reflects real complexity. That work reduces the risk of preserving records while losing navigation, visibility, access, routing, multilingual relationships, or commerce meaning.

Before running a Joomla migration, prepare a sample that includes the site’s most complex content, menus, users, access rules, media, language relationships, extension-owned commerce data, and custom fields. If the sample exposes unsupported extension data, custom tables, unclear commerce ownership, or bespoke transformation needs, review the scope through Live Chat before deciding whether Standard Service, Managed Service, Add-ons, or Custom Service is the right path.

### FAQs <a href="#faqs" id="faqs"></a>

**Does Joomla preparation only mean exporting articles and categories?**

No. Articles and categories are only part of Joomla preparation. Menus, aliases, modules, templates, users, user groups, access levels, media, custom fields, tags, multilingual associations, routing behavior, installed extensions, and extension-owned commerce data may all affect the migrated result.

**Why is the commerce extension important before a Joomla migration?**

Joomla core does not provide one universal native commerce model. Product, checkout, order, payment, shipping, tax, coupon, inventory, and customer-commerce data usually belong to a specific extension or custom implementation. The extension must be identified before commerce data can be planned accurately.

**Should inactive users, old content, and obsolete records be removed before migration?**

They should be reviewed before migration, but not automatically removed. Some records may be obsolete storefront data, while others may need to remain for history, compliance, account continuity, or operational reference. Filtering or selective handling should be planned before execution.

**What makes a good Demo Migration sample for Joomla?**

A good sample includes records that reflect real site complexity: content with categories and aliases, menu-driven routes, module assignments, restricted access, media, custom fields, multilingual associations, extension-owned commerce records, and any custom or plugin-owned data that may require review.

**When should Custom Service be reviewed for a Joomla migration?**

Custom Service should be reviewed when the migration involves Custom Platform handling, unsupported or modified extensions, custom database tables, plugin-owned records, bespoke relationships, external identifiers, custom fields with business-critical meaning, or custom migration logic adjustment beyond standard service capability.
