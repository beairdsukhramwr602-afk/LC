# Joomla Constraints and Risks

Joomla migration risk usually comes from hidden ownership. Joomla core may hold articles, categories, menus, modules, users, access levels, custom fields, tags, media, and language structure, while commerce behavior may belong to a Joomla extension, a custom component, plugin logic, or a broader Custom Platform implementation.

That makes Joomla different from platforms where catalog, checkout, customer, and order structures are controlled by one native commerce model. A Joomla site can look like a single system on the front end while the data is actually distributed across core tables, installed components, modules, plugins, templates, overrides, language associations, custom database tables, and outside integrations.

Risk control starts by identifying which part of Joomla owns each business meaning. Content risk, navigation risk, access-control risk, multilingual risk, presentation risk, commerce risk, and custom-development risk should be reviewed before assuming that a standard migration path will preserve the operational result.

### Why Joomla Migration Risk Is Usually Ownership Risk <a href="#why-joomla-migration-risk-is-usually-ownership-risk" id="why-joomla-migration-risk-is-usually-ownership-risk"></a>

The central Joomla constraint is not that Joomla lacks flexibility. The constraint is that flexibility creates multiple possible owners for the same visible outcome. A product listing may be rendered by a commerce component, filtered by plugins, surrounded by modules, styled by a template override, reached through a menu alias, restricted by access levels, and translated through language associations. A source record cannot be interpreted correctly until those ownership layers are known.

| Risk area                       | What creates the constraint                                                                                                                 | Why it matters during migration                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Core content ownership          | Articles, categories, fields, tags, media, publishing state, authorship, language, and access levels may all contribute to content meaning. | Moving text alone may not preserve editorial, visibility, classification, or SEO meaning.                |
| Routing ownership               | Menus, aliases, SEF URLs, category views, component routes, language menus, and redirects may shape how content is reached.                 | Records can exist in the target site but lose traffic, navigation context, or internal-link continuity.  |
| Presentation ownership          | Templates, child templates, overrides, modules, page builders, and extension widgets can define page output.                                | Data may be correct in storage but appear incomplete or wrong on the front end.                          |
| Access ownership                | User groups, access levels, permissions, registration behavior, memberships, and extension profiles may overlap.                            | Users may gain too much access, lose required access, or fail to match customer/member roles.            |
| Commerce ownership              | Joomla core does not define one native product, cart, checkout, order, tax, shipping, payment, inventory, or coupon model.                  | Commerce data must be interpreted through the installed component or custom implementation that owns it. |
| Custom implementation ownership | Custom components, modified extensions, plugin-owned records, and external identifiers may sit outside standard structures.                 | Custom Service review may be required to preserve relationships and operational meaning.                 |

A safe Joomla migration plan treats visible pages, storefront sections, account areas, and commerce records as outcomes produced by several layers, not as records with one universal destination.

### Commerce Component Identity Is a Primary Constraint <a href="#commerce-component-identity-is-a-primary-constraint" id="commerce-component-identity-is-a-primary-constraint"></a>

Joomla core should not be treated as a native e-commerce system. Product, order, cart, checkout, payment, shipping, tax, inventory, coupon, discount, invoice, review, and customer-commerce meaning depends on the installed commerce component or custom implementation.

That support structure is important because a migration into Joomla core is not the same decision as a migration into a Joomla commerce extension. If the target commerce owner is a Joomla extension, the commerce-specific data model should be reviewed through that extension context. If the commerce owner is unsupported, abandoned, heavily modified, or custom-built, the migration path may require Custom Service review.

| Commerce identity signal                                              | Who it affects                                                                                    | Mitigation strategy                                                                                    | When risk increases                                                                                                         |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Commerce extension is clearly identified                              | Merchants using a known Joomla commerce component                                                 | Review the migration scope against the specific extension, not Joomla core alone.                      | Risk increases when the extension version, target extension, or installed plugin stack is unclear.                          |
| Joomla is selected as the target but no commerce component is defined | Merchants expecting store behavior from Joomla core                                               | Confirm whether the target is Joomla site/content migration or a Joomla-based commerce implementation. | Risk increases when product/order/checkout expectations are attached to Joomla without naming the component that owns them. |
| Commerce records belong to an unsupported or legacy extension         | Older Joomla stores, abandoned component users, long-running custom sites                         | Identify record ownership, target equivalent, and required transformation before service selection.    | Risk increases when the extension has no current target equivalent or has custom table changes.                             |
| Commerce behavior is custom-built                                     | Custom Joomla applications, membership stores, quote systems, catalog-only workflows, B2B portals | Treat the implementation as custom data ownership that may require Custom Service review.              | Risk increases when code, database tables, plugins, or external identifiers control business behavior.                      |

The earliest review priority is simple: name the commerce owner before naming the commerce outcome. Without that, product and order migration expectations can become misleading.

### Unsupported, Abandoned, or Modified Extensions Increase Interpretation Risk <a href="#unsupported-abandoned-or-modified-extensions-increase-interpretation-risk" id="unsupported-abandoned-or-modified-extensions-increase-interpretation-risk"></a>

Joomla sites often remain in production for many years. A live site may contain extensions that are no longer maintained, extensions that were modified by a previous developer, extensions with custom fields added directly to tables, plugins that alter behavior during events, or integrations that exchange data with external systems.

The migration risk is not only technical compatibility. The larger issue is whether the data still means what the extension name suggests. A site may appear to use a familiar component, but the operational version may include custom logic, altered database relationships, custom statuses, extra fields, modified checkout behavior, custom access rules, or integration-specific identifiers.

| Extension condition              | Who it affects                                                                                                  | Mitigation strategy                                                                                                            | Earliest review priority                                                                                    |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------- |
| Unsupported or unclear extension | Sites using components outside standard supported coverage, abandoned extensions, or custom components          | Review whether records can map to Joomla core, a known Joomla extension, a replacement structure, or Custom Platform handling. | Identify the extension tables, record types, relationships, and required target behavior.                   |
| Abandoned extension              | Older stores or content applications that depend on discontinued components                                     | Separate historical data preservation from active operational behavior.                                                        | Confirm whether the target needs functional continuity or archive/reference continuity only.                |
| Modified extension               | Sites where developers changed extension tables, statuses, fields, layouts, or logic                            | Compare the installed implementation against the standard extension behavior before mapping.                                   | Identify modifications that affect products, orders, customers, permissions, URLs, fields, or integrations. |
| Plugin-dependent extension       | Sites where plugins alter forms, checkout, content display, authentication, search, routing, or data processing | Review plugins as part of the data model, not as decorative add-ons.                                                           | Identify event-driven behavior and plugin-owned records that may not appear in the main component screen.   |

When extension behavior is unclear, a lighter migration assumption can create false confidence. The safer approach is to treat the extension stack as part of the source evidence, especially when commerce, access, multilingual, routing, or custom fields depend on it.

### Routing, Aliases, and Menus Can Become SEO Constraints <a href="#routing-aliases-and-menus-can-become-seo-constraints" id="routing-aliases-and-menus-can-become-seo-constraints"></a>

Joomla routing is closely tied to menus, menu items, aliases, categories, component views, language menus, and SEF URL behavior. A migrated article or component record may be present in the target installation but still fail if the intended route is missing, duplicated, changed, inaccessible, or disconnected from the correct menu context.

This risk matters for both users and search engines. Menus can define page entry points, active navigation state, breadcrumbs, layout selection, module assignments, and URL structure. Categories organize content, but they do not automatically recreate the navigation logic of the source site. Component routes may behave differently from article routes. Multilingual routes may require language-specific menu items and associations.

| Routing constraint                          | Who it affects                                                               | Mitigation strategy                                                            | When risk increases                                                                             |
| ------------------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------- |
| Source URLs rely on menu aliases            | Sites with SEO-sensitive content, long-standing URLs, or deep internal links | Map important menu items, aliases, and route patterns before migration.        | Risk increases when the target menu structure is redesigned without redirect planning.          |
| Categories are mistaken for navigation      | Sites with category-heavy content or catalogs                                | Separate content taxonomy from menu structure and route ownership.             | Risk increases when a category tree is expected to recreate all navigation automatically.       |
| Component routes differ from article routes | Sites using commerce, directory, booking, membership, or custom components   | Validate routes through the owning component and menu item context.            | Risk increases when extension records are migrated without component-specific routing checks.   |
| Multilingual routes rely on language menus  | Multilingual Joomla sites                                                    | Confirm language-specific menus, associations, aliases, and switcher behavior. | Risk increases when translation records are migrated without preserving language-route context. |

The earliest review should identify high-value URLs, menu-driven routes, component routes, multilingual routes, and internal links. Redirect planning may be needed when the target structure changes.

### ACL, User Groups, and Access Levels Can Change Business Meaning <a href="#acl-user-groups-and-access-levels-can-change-business-meaning" id="acl-user-groups-and-access-levels-can-change-business-meaning"></a>

Joomla access control can be more complex than a simple customer account list. Users may belong to multiple groups. Groups may inherit permissions. Access levels may control who can view content or modules. Permissions may affect editing, publishing, administration, workflow, membership areas, protected resources, or extension behavior.

Commerce extensions may also maintain customer profiles, billing addresses, shipping addresses, group pricing, vendor roles, membership status, subscription access, wholesale segmentation, or other account-related data outside Joomla core users.

| Access constraint                              | Who it affects                                                                     | Mitigation strategy                                                                 | When risk increases                                                                                            |
| ---------------------------------------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Joomla users are treated as commerce customers | Sites with registered users, authors, members, administrators, and store customers | Separate CMS user identity from extension-owned customer profile data.              | Risk increases when the same login account carries different roles across Joomla core and commerce extensions. |
| User groups are flattened                      | Sites with membership, editorial, wholesale, B2B, or restricted-content logic      | Preserve group membership and confirm target access-level interpretation.           | Risk increases when groups drive pricing, content visibility, approvals, or workflows.                         |
| Access levels are ignored                      | Sites with private content, gated downloads, member pages, or internal portals     | Map view access separately from user identity.                                      | Risk increases when migrated content becomes public or disappears for intended audiences.                      |
| Permissions differ between source and target   | Sites with editors, managers, vendors, support teams, or administrators            | Review permission inheritance and administrative roles before accepting the result. | Risk increases when operational staff need precise post-migration capabilities.                                |

Access migration should be judged by behavior, not only by user counts. A correct result proves that the right people can view, edit, manage, buy, order, or administer the right areas after migration.

### Multilingual Structure Adds Relationship Risk <a href="#multilingual-structure-adds-relationship-risk" id="multilingual-structure-adds-relationship-risk"></a>

Joomla multilingual sites may involve language-specific articles, categories, menus, modules, aliases, metadata, associations, language switchers, template assignments, and extension-owned translations. Translation is not only content duplication. It is a relationship structure that affects navigation, routing, visibility, SEO, and user experience.

A multilingual migration can fail even when translated records exist. Users may land on the wrong language route. Language switchers may point to a homepage instead of the associated page. Translated menu aliases may collide. Modules may appear in the wrong language. Commerce products or categories may have partial translation coverage depending on the owning extension.

| Multilingual constraint                                                 | Who it affects                                                                   | Mitigation strategy                                                                   | Earliest review priority                                                                          |
| ----------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Language associations are missing or inconsistent                       | Multilingual content sites and international stores                              | Confirm article, category, menu, and module associations where required.              | Sample equivalent pages across each important language.                                           |
| Language-specific menus are incomplete                                  | Sites where each language has its own navigation tree                            | Review menus, aliases, default pages, and language switcher behavior.                 | Identify whether source navigation is mirrored, localized, or structurally different by language. |
| Extension-owned translations are separate from Joomla core translations | Stores using translated products, categories, checkout labels, emails, or fields | Validate translation behavior inside the commerce component or custom implementation. | Identify which extension owns commerce translations.                                              |
| Metadata and aliases are not localized                                  | SEO-sensitive multilingual sites                                                 | Preserve or rebuild language-specific metadata, slugs, aliases, and redirects.        | Check high-value translated pages and commerce records.                                           |

Multilingual risk is highest when language structure is treated as a text-transfer problem instead of a routing, association, visibility, and extension-ownership problem.

### Templates, Modules, and Overrides Can Hide Page-Level Dependencies <a href="#templates-modules-and-overrides-can-hide-page-level-dependencies" id="templates-modules-and-overrides-can-hide-page-level-dependencies"></a>

Joomla output is often assembled from component output plus modules, template positions, layout choices, template overrides, child templates, page-builder sections, language modules, search modules, menu modules, login modules, cart modules, filter modules, and custom HTML blocks. These elements can be just as important as the main content record.

A migrated Joomla page can look incomplete if presentation dependencies are not reviewed. The data may exist, but the front end may lose breadcrumbs, sidebars, banners, filters, language switchers, category modules, product blocks, cart summaries, account links, or landing-page sections.

| Presentation constraint                   | Who it affects                                                              | Mitigation strategy                                                                      | When risk increases                                                                            |
| ----------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Module assignments depend on menu items   | Content sites, commerce landing pages, multilingual sites                   | Review modules together with menu routes and access levels.                              | Risk increases when menus are redesigned or aliases are changed.                               |
| Template overrides change output          | Sites with custom layouts or extension-specific designs                     | Identify overrides that affect Joomla core views or extension views.                     | Risk increases when the target uses a different template or extension version.                 |
| Page builders own visible content blocks  | Marketing-heavy Joomla sites                                                | Determine whether content lives in articles, modules, builder data, or extension tables. | Risk increases when builder data has no direct target equivalent.                              |
| Commerce widgets are module/plugin-driven | Joomla stores with cart, search, filter, promo, account, or product modules | Validate storefront behavior beyond product/order records.                               | Risk increases when the commerce extension is migrated but supporting modules are not planned. |

Presentation constraints should be reviewed early when the target project expects the migrated site to preserve page experience, not only database content.

### Custom Fields, Tags, and Media Can Carry Operational Logic <a href="#custom-fields-tags-and-media-can-carry-operational-logic" id="custom-fields-tags-and-media-can-carry-operational-logic"></a>

Joomla custom fields, tags, and media may look secondary, but they can carry important operational meaning. Custom fields may drive structured content, product attributes, filters, member details, directory data, resource metadata, integration values, or layout output. Tags may support discovery, related content, filters, or editorial organization. Media may be referenced through articles, fields, modules, templates, extensions, or custom code.

| Data feature  | Constraint                                                                                                                  | Mitigation strategy                                                                 | Risk signal                                                                                 |
| ------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Custom fields | Field values may be content-only, layout-driving, filterable, searchable, access-sensitive, or integration-related.         | Classify fields by business purpose before mapping them.                            | Risk increases when fields affect pricing, filtering, access, external IDs, or workflows.   |
| Tags          | Tags may support navigation, discovery, related content, or editorial grouping.                                             | Preserve tag relationships where they remain meaningful in the target structure.    | Risk increases when tags replace formal categories or extension attributes.                 |
| Media         | Images, documents, downloads, videos, and embedded media may be referenced from multiple layers.                            | Review file paths, media references, alt text, embedded links, and access behavior. | Risk increases when protected downloads, product media, or page-builder media are involved. |
| Metadata      | Titles, descriptions, aliases, schema-related fields, and social metadata may be distributed across records and extensions. | Identify SEO-critical metadata sources before migration.                            | Risk increases when source SEO depends on extension-specific fields or custom plugins.      |

These structures should not be dismissed as minor content extras. When they support search, filtering, access, layout, SEO, or integrations, they can affect whether the migrated Joomla site remains usable.

### Plugin-Owned Data and Web Services/API Dependencies Need Separate Review <a href="#plugin-owned-data-and-web-services-api-dependencies-need-separate-review" id="plugin-owned-data-and-web-services-api-dependencies-need-separate-review"></a>

Plugins may change Joomla behavior without appearing as primary content or commerce records. They can affect authentication, content rendering, custom fields, search, routing, redirects, forms, spam protection, membership logic, email behavior, checkout events, analytics, and external integrations. Some plugins store configuration or operational records that need separate review.

Joomla also supports integration and developer patterns, including Web Services/API-related functionality, but implementation details vary by version, extension, permissions, authentication, custom code, and integration design. Migration planning should not assume that an integration will remain functional just because core content or commerce records have moved.

| Dependency type             | Who it affects                                                                                    | Mitigation strategy                                                                          | When risk increases                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Authentication plugins      | Sites using SSO, LDAP, social login, membership login, or custom authentication                   | Confirm login behavior and user identity dependencies separately from user record migration. | Risk increases when account access depends on external identity providers.                        |
| Content or field plugins    | Sites where plugin syntax, shortcodes, embedded blocks, or dynamic fields render front-end output | Identify plugin-dependent content before migration.                                          | Risk increases when visible content is generated from plugin syntax rather than stored body text. |
| Routing or redirect plugins | SEO-sensitive sites and legacy migrations                                                         | Review URL behavior, redirects, canonical handling, and route generation.                    | Risk increases when historical URLs depend on plugin rules.                                       |
| External integrations       | ERP, CRM, POS, fulfillment, PIM, reporting, membership, payment, or marketing systems             | Preserve required identifiers and integration-facing structures where they remain active.    | Risk increases when custom IDs or sync status fields are not mapped.                              |

Custom or integration-heavy Joomla projects often require Custom Service review because the migration must preserve relationships between records, code behavior, outside-system identifiers, and target capabilities.

### Custom Platform and Custom Service Risk Signals <a href="#custom-platform-and-custom-service-risk-signals" id="custom-platform-and-custom-service-risk-signals"></a>

A Joomla migration may stay within standard service capability when the source and target structures are supported, clearly identified, and compatible with the intended migration path. Risk rises when the project depends on custom structures, unsupported extension data, custom fields with business logic, outside-system identifiers, plugin-owned records, or target behavior that Joomla core or a supported extension does not provide by default.

| Complexity signal                                                     | Likely service implication                                | Reason for review                                                                                                         |
| --------------------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Custom Platform implementation                                        | Custom Service                                            | Custom Platform handling requires review of non-standard structure, relationships, and target behavior.                   |
| Unsupported extension data                                            | Custom Service review                                     | Records may not have a standard source reader, target destination, or supported relationship model.                       |
| Custom Joomla component                                               | Custom Service review                                     | Data ownership, schema, permissions, routing, and display behavior may be bespoke.                                        |
| Modified commerce extension                                           | Custom Service review                                     | Standard extension assumptions may not match the actual implementation.                                                   |
| Custom fields used for business logic                                 | Custom Service review or Add-on review depending on scope | Field values may require mapping, transformation, configuration, or custom migration logic adjustment.                    |
| Filtering, mapping, or configuration need within supported capability | Add-on review                                             | Add-ons may address controlled filtering, mapping, or configuration needs without turning every case into Custom Service. |
| Merchant wants Next-Cart-led execution within standard capability     | Managed Service may be safer                              | Execution responsibility is different from customization need.                                                            |

Custom Service should not be treated as a synonym for Next-Cart-led execution. It is the review path for customization, modification, bespoke handling, Custom Platform, unsupported extension data, custom fields, outside-system identifiers, and custom migration logic adjustment. Migration management is included only when it is part of the final plan.

### Earliest Review Priorities for Joomla Risk Control <a href="#earliest-review-priorities-for-joomla-risk-control" id="earliest-review-priorities-for-joomla-risk-control"></a>

The most useful early review does not try to document everything equally. It identifies the areas most likely to control migration meaning.

| Review priority        | What should be confirmed                                                                                                                        | Why it matters                                                                                            |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Target identity        | Whether the target is Joomla core/site structure, a known Joomla commerce extension, or a custom Joomla implementation                          | Prevents Joomla core from being mistaken for a complete commerce target.                                  |
| Commerce owner         | Which component or custom implementation owns products, customers, orders, checkout, payments, shipping, taxes, coupons, inventory, and reviews | Determines whether commerce data can be interpreted through a supported extension or needs custom review. |
| Extension stack        | Installed components, modules, plugins, templates, packages, libraries, and language packs                                                      | Reveals dependencies outside core content records.                                                        |
| URLs and menus         | Important menu items, aliases, SEF URLs, internal links, language routes, redirects, and component routes                                       | Protects navigation, SEO continuity, and page context.                                                    |
| User/access structure  | Users, user groups, access levels, permissions, memberships, customer profiles, and administrative roles                                        | Protects visibility, login behavior, and operational access.                                              |
| Multilingual structure | Languages, associations, menus, modules, metadata, aliases, and extension-owned translations                                                    | Prevents partial translation transfer from being mistaken for multilingual continuity.                    |
| Custom structures      | Custom tables, modified extensions, custom fields, plugin-owned data, outside-system identifiers, and integrations                              | Identifies Custom Service review needs before migration assumptions become fixed.                         |

A Joomla migration is lowest risk when each visible business outcome has a known owner, a target destination, a validation sample, and a service path that matches the implementation complexity.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Joomla constraints are manageable when the migration plan respects Joomla’s layered architecture. The highest-risk assumption is treating Joomla as if it has one universal native store model or one simple page model. Joomla core, menus, modules, templates, access levels, multilingual associations, extensions, plugins, commerce components, and custom code can all own part of the final result.

A sound Joomla migration plan identifies ownership before promising continuity. Commerce data should be tied to the correct extension or custom implementation. URLs should be reviewed as menu and route behavior, not only as slugs. Users should be validated through access meaning, not only account counts. Custom development should be reviewed through Custom Service when standard structures cannot preserve the required relationships.

Before finalizing a Joomla migration path, prepare a representative sample of high-value content, routes, users, access rules, multilingual records, commerce records, extension dependencies, and custom structures. Use that sample to confirm whether the project fits standard service capability, needs Add-ons, benefits from Managed Service execution, or requires Custom Service review through Live Chat.

### FAQs <a href="#faqs" id="faqs"></a>

**Does Joomla have one standard product and order model?**

No. Joomla core does not define one universal product, order, cart, checkout, payment, shipping, tax, inventory, or coupon model. Those meanings belong to the installed commerce component, another business extension, or a custom Joomla implementation.

**Why is commerce extension identity such a major Joomla migration risk?**

Commerce extension identity determines where products, customers, addresses, orders, discounts, stock, checkout behavior, payment data, shipping logic, tax rules, and related records actually belong. Without that identity, a migration plan can mistake Joomla site migration for commerce-system migration.

**Are Joomla menus a migration risk or only a design issue?**

Menus are a migration risk because they affect routing, aliases, page entry points, active navigation state, module assignments, layout context, breadcrumbs, and sometimes multilingual structure. A migrated record may exist but still fail if the correct menu route is missing.

**Can user accounts be migrated as customer accounts in Joomla?**

Only when the target meaning is clear. Joomla users may represent CMS accounts, authors, administrators, members, customers, vendors, or extension-linked profiles. Commerce customer meaning usually depends on the installed commerce extension or custom implementation.

**When does a Joomla migration need Custom Service review?**

Custom Service review is usually needed when the project involves Custom Platform handling, unsupported extension data, custom components, modified extensions, plugin-owned records, custom fields with business logic, outside-system identifiers, bespoke transformations, or custom migration logic adjustment.

**Do Add-ons solve all Joomla complexity?**

No. Add-ons can support defined filtering, mapping, or configuration needs when those needs fit Add-on capability. Broader customization, unsupported extension data, Custom Platform handling, bespoke transformation, or custom migration logic adjustment belongs under Custom Service review.
