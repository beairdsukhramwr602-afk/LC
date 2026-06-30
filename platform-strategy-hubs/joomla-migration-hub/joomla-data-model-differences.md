# Joomla Data Model Differences

Joomla data model differences begin with one important distinction: Joomla is not organized around one universal store schema. It is a CMS and application framework where content, menus, modules, templates, users, languages, access rules, media, custom fields, and extensions work together to create the public site. Commerce records may exist in a Joomla environment, but their meaning depends on the component or custom implementation that owns them.

For migration planning, this means Joomla data should not be reduced to a simple page export. A visible page can depend on an article record, a menu item, a category, an alias, a template assignment, module positions, access levels, language associations, metadata, plugins, and extension-owned routes. The data model is layered, and the migration must preserve the relationships that make the records usable.

### Joomla Data Meaning Is Layered <a href="#joomla-data-meaning-is-layered" id="joomla-data-meaning-is-layered"></a>

Joomla separates site content from site assembly. Articles may hold the main body content, categories may organize records, menus may define routes and navigation, modules may place supporting content, templates may control presentation, and plugins may alter output or behavior. These layers can be easy to miss when migration is evaluated only by record counts.

A Joomla migration should therefore ask which layer owns the business meaning. A policy page may be mostly an article. A landing page may depend heavily on a menu item, assigned modules, and template output. A members-only page may depend on access levels and user groups. A commerce page may be rendered by a component rather than Joomla core content.

| Joomla layer                 | What it may own                                                                | Migration implication                                                                     |
| ---------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Articles                     | Main content bodies, page text, editorial records, landing content             | Article transfer is important, but it does not recreate the full page alone.              |
| Categories                   | Content organization, editorial grouping, archive structure                    | Categories help structure content but may not define the public URL by themselves.        |
| Menus and aliases            | Navigation, routes, SEF URLs, entry points, page context                       | Menu relationships often matter as much as the content record.                            |
| Modules                      | Sidebar blocks, banners, menus, forms, related content, page-specific displays | Module assignment and position can affect whether a migrated page looks complete.         |
| Templates and overrides      | Layout, output, presentation, page-specific design behavior                    | These may require setup, review, or rebuilding rather than ordinary data migration.       |
| Users, groups, access levels | Login, permissions, restricted content, contributor roles                      | User data must be interpreted by access meaning, not only account fields.                 |
| Extensions and plugins       | Commerce, forms, downloads, directories, memberships, routing, integrations    | Extension-owned records may require Add-ons, Custom Service, or target-side setup review. |

The practical difference is that Joomla migration is relationship-sensitive. Moving records without preserving their ownership and context can produce a site where data exists but public pages, restricted areas, routes, and extension behavior no longer work as expected.

### Articles, Categories, and Menus Do Different Jobs <a href="#articles-categories-and-menus-do-different-jobs" id="articles-categories-and-menus-do-different-jobs"></a>

Joomla articles, categories, and menus are often confused because they can all appear to describe the same page. In practice, they perform different jobs. Articles store content. Categories organize content. Menus create navigation entries and often define public routes. A migrated article may not be reachable in the same way unless the related menu structure and alias behavior are reviewed.

This distinction is especially important for SEO-sensitive sites. A page URL may come from a menu alias rather than from the article title alone. A category may support organization, while the menu item determines the public path that search engines and visitors use. When menus are ignored, migrated content may be present but disconnected from its original entry point.

| Source expectation                  | Joomla interpretation                                                                        | What to check during migration                                               |
| ----------------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| A page is a content record          | The article may hold content, but the menu item may define access and URL context.           | Validate the article and its menu route together.                            |
| A category is a storefront category | Joomla categories may organize content; commerce categories may belong to a store extension. | Separate Joomla content categories from extension-owned commerce categories. |
| A URL can be rebuilt from a title   | Joomla routes may depend on menu aliases, category paths, language, and component routing.   | Review high-value URLs and redirects as relationship records.                |
| A navigation item is only design    | Menus can affect routing, page context, modules, breadcrumbs, and metadata.                  | Validate menus as structural data, not decoration.                           |

A strong Joomla data review should treat menus as part of the data model. They are not just front-end navigation labels. They can carry URL, access, language, metadata, and page-context meaning.

### Modules, Templates, and Overrides Shape Page Meaning <a href="#modules-templates-and-overrides-shape-page-meaning" id="modules-templates-and-overrides-shape-page-meaning"></a>

Joomla modules and templates can make a migrated record look complete or incomplete. A source page may include a main article plus a sidebar module, a contact block, a menu module, a banner, a login panel, a language switcher, a related-content block, or a custom HTML module. If the article migrates but the module assignments are missing or changed, the page may lose visible business context.

Templates and overrides add another layer. They can change how articles, categories, components, and modules are displayed. A migrated record may contain the right text and metadata, but if the old page depended on a template override or custom layout, the target display may need manual setup or custom review.

| Page element        | Data-model role                                       | Migration planning question                                                         |
| ------------------- | ----------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Module position     | Places supporting content in a layout area            | Should the module be migrated, rebuilt, reassigned, or excluded?                    |
| Menu assignment     | Controls where a module appears                       | Is the module tied to a specific page, language, menu branch, or user group?        |
| Template assignment | Changes the layout for selected pages                 | Does the target need a matching template relationship or new design setup?          |
| Template override   | Alters component or content output                    | Is this presentation logic, custom behavior, or a Custom Service signal?            |
| Custom HTML module  | Stores reusable content outside the main article body | Does the content need to remain editable, visible, and assigned to the right pages? |

This is why Joomla migration validation should include representative page assemblies, not only lists of articles. The target result must prove that pages are reachable, visible, and contextually complete.

### Users, User Groups, Access Levels, and Customers Are Separate Meanings <a href="#users-user-groups-access-levels-and-customers-are-separate-meanings" id="users-user-groups-access-levels-and-customers-are-separate-meanings"></a>

Joomla user data should not be treated automatically as customer data. Joomla users may represent administrators, authors, members, registered visitors, restricted-content users, event participants, students, partners, staff, or commerce customers depending on the implementation. User groups and access levels add more meaning because they control what a user can see or do.

Commerce extensions may keep separate customer records, addresses, order relationships, shopper groups, or checkout profiles. A user account may connect to a commerce customer, but that relationship belongs to the commerce extension or custom component. Migration planning should avoid merging these meanings too early.

| Record type        | Joomla meaning                                             | Common migration risk                                                               |
| ------------------ | ---------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Joomla user        | Login identity and account record                          | Treated as a complete customer profile without checking extension-owned buyer data. |
| User group         | Permission grouping or role assignment                     | Treated as a marketing segment instead of access control.                           |
| Access level       | Visibility rule for content, modules, menus, or components | Lost during migration, exposing or hiding content incorrectly.                      |
| Commerce customer  | Buyer profile stored by an extension or custom component   | Assumed to be fully represented by Joomla core users.                               |
| Administrator role | Back-end operational permission                            | Migrated without validating operational access and security expectations.           |

A Joomla migration should preserve identity relationships only where they are supported and understood. If customer history, restricted content, membership rules, or commerce profiles depend on extension-owned data, the service path may require Custom Service review.

### Custom Fields, Tags, Media, and Metadata Carry Business Context <a href="#custom-fields-tags-media-and-metadata-carry-business-context" id="custom-fields-tags-media-and-metadata-carry-business-context"></a>

Joomla custom fields, tags, media, and metadata can carry more business value than their names suggest. Custom fields may support content filtering, profile data, structured landing pages, directories, membership data, product-like information, or integration identifiers. Tags may support discovery and related content. Media may include embedded images, downloadable files, protected documents, product-related assets, and reused page resources. Metadata may affect SEO continuity and social sharing.

These records should be classified by business purpose before migration. A custom field used only for editorial notes has a different risk level from a custom field that stores membership status, external IDs, product attributes, event details, or structured SEO content.

| Data area     | Why it matters                                                                          | Review priority                                                                                                 |
| ------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Custom fields | May store structured values attached to articles, users, contacts, or extension records | Identify whether fields are editorial, searchable, access-sensitive, integration-related, or business-critical. |
| Tags          | May replace or supplement categories for discovery and grouping                         | Check whether tags affect navigation, filtering, related content, or internal workflows.                        |
| Media         | May be referenced by articles, modules, extensions, or templates                        | Review paths, embedded links, alt text, protected files, and reused assets.                                     |
| Metadata      | May be stored at article, menu, category, extension, or plugin level                    | Validate titles, descriptions, aliases, redirects, and high-value SEO records.                                  |

This review helps prevent a common Joomla error: migrating visible content while losing structured values that make the content useful for search, filtering, access, integrations, or editorial management.

### Multilingual Records Depend on More Than Translated Text <a href="#multilingual-records-depend-on-more-than-translated-text" id="multilingual-records-depend-on-more-than-translated-text"></a>

Joomla multilingual migration is not only a text translation issue. Multilingual structure may include language-specific articles, categories, menus, modules, aliases, metadata, language associations, template assignments, and extension-owned translations. A migrated target can have translated content but still fail if language relationships, menus, or modules are disconnected.

The migration plan should identify whether the source uses Joomla core multilingual features, extension-specific language behavior, custom translation fields, or external translation workflows. Each pattern changes what must be preserved and validated.

| Multilingual element        | Migration meaning                              | Validation focus                                                      |
| --------------------------- | ---------------------------------------------- | --------------------------------------------------------------------- |
| Language-specific article   | Content in a target language                   | Confirm the article exists and carries correct language assignment.   |
| Language-specific menu item | Public route for translated content            | Confirm each language has correct navigation and URL behavior.        |
| Language association        | Relationship between translated versions       | Confirm translated pages remain connected where needed.               |
| Language-specific module    | Supporting content for a language              | Confirm modules display in the correct language and menu context.     |
| Extension-owned translation | Translation stored outside Joomla core content | Confirm whether the extension data is supported, custom, or excluded. |

Multilingual review should include sample pages from each important language. The target should prove that users can move through translated content naturally, not only that translated records exist.

### Extensions and Plugins Define Many Data Boundaries <a href="#extensions-and-plugins-define-many-data-boundaries" id="extensions-and-plugins-define-many-data-boundaries"></a>

Joomla’s extensibility is one of its strengths, but it also makes migration planning more precise. Components, modules, plugins, templates, and packages may each store data or control behavior. A form component may own submissions. A download extension may own file records and access rules. A membership extension may own subscriptions. A commerce extension may own products and orders. A plugin may transform content output or connect the site to an external system.

The migration plan should identify which data belongs to Joomla core and which belongs to installed extensions. Supported extension records may fit the ordinary scope. Unsupported extension data, custom tables, custom components, and modified extensions may require Custom Service.

| Extension dependency | What it may control                                                                                 | Service implication                                                                         |
| -------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Component            | Primary feature data such as store records, forms, directories, downloads, memberships, or bookings | Supported components may be handled normally; unsupported or custom components need review. |
| Module               | Display blocks, navigation, banners, feeds, search boxes, login blocks, or custom HTML              | Often requires layout and assignment validation.                                            |
| Plugin               | Rendering, authentication, routing, field behavior, integrations, or event-driven processing        | May require Custom Service if it stores or transforms important data.                       |
| Template             | Site presentation and overrides                                                                     | Usually a setup/design concern unless custom logic or data relationships are involved.      |
| External integration | CRM, ERP, POS, PIM, analytics, payment, shipping, or membership systems                             | External IDs and sync rules require special review.                                         |

Joomla migration is most reliable when extension ownership is documented before service scope is accepted. Without that ownership map, the project can confuse standard content migration with unsupported extension migration.

### Commerce Data Is Extension-Dependent <a href="#commerce-data-is-extension-dependent" id="commerce-data-is-extension-dependent"></a>

Joomla core does not define one native product, cart, checkout, order, payment, tax, coupon, shipping, inventory, or review model. Those records belong to the selected commerce extension or custom component. This matters because two Joomla-based stores can have completely different data models even though both run inside Joomla.

For a Joomla commerce migration, the owning extension determines how product data is interpreted. One extension may treat product options, attributes, manufacturers, prices, tax rules, addresses, orders, invoices, shipment methods, or payment plugins differently from another. A custom component may store these records in bespoke tables.

| Commerce record                    | Joomla-core status                                      | Migration planning implication                                                    |
| ---------------------------------- | ------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Products and product categories    | Not native Joomla core store records                    | Identify the commerce component or custom implementation.                         |
| Customers and addresses            | May be linked to Joomla users but often extension-owned | Preserve account relationships only where supported and meaningful.               |
| Orders and order statuses          | Extension-owned or custom-owned                         | Validate historical context through the commerce component.                       |
| Coupons, taxes, shipping, payments | Extension-specific configuration or records             | Separate migrated data from target-side setup and payment/shipping configuration. |
| Product reviews and inventory      | Extension-dependent                                     | Confirm whether records are supported, custom, or excluded.                       |

The strongest Joomla commerce planning starts with the extension name and implementation state, not with the assumption that Joomla itself owns the store data.

### Custom Joomla Implementations Require Ownership Review <a href="#custom-joomla-implementations-require-ownership-review" id="custom-joomla-implementations-require-ownership-review"></a>

Some Joomla sites include custom components, modified extensions, bespoke database tables, template overrides with business logic, plugin-driven workflows, or integrations with external systems. These cases should be reviewed before migration expectations are finalized because standard records may not explain the actual data relationships.

Custom implementations are not automatically impossible, but they need clearer ownership and acceptance rules. The project should identify which records must be preserved, which fields drive business behavior, which IDs are required by external systems, and which target-side behavior must be rebuilt rather than migrated.

| Custom signal                | Why it changes migration planning                                                       |
| ---------------------------- | --------------------------------------------------------------------------------------- |
| Custom component             | Data structure and business logic may be unique to the site.                            |
| Modified extension           | Standard extension assumptions may no longer match the actual implementation.           |
| Custom database tables       | Records may not have a supported source reader or target destination.                   |
| Plugin-generated output      | Visible content may not exist as ordinary article body text.                            |
| External IDs                 | ERP, CRM, POS, membership, or reporting continuity may depend on preserved identifiers. |
| Template override with logic | Display or workflow behavior may need rebuilding instead of data transfer.              |

Custom Service review is appropriate when required business data sits outside supported Joomla structures or when bespoke transformation is needed. Add-ons may help with supported filtering, mapping, or configuration, but they should not be treated as a substitute for custom handling.

### What Migrated Joomla Data Must Prove <a href="#what-migrated-joomla-data-must-prove" id="what-migrated-joomla-data-must-prove"></a>

A Joomla data migration should prove that the target records remain usable in context. That proof is not limited to whether the data exists. It should show that site structure, access, routing, language, media, extension ownership, and commerce relationships still make sense.

| Data area                     | Proof required                                                                                                                    |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Articles and categories       | Content exists, remains organized, and supports the intended pages or editorial workflows.                                        |
| Menus, aliases, and redirects | Important routes and public entry points remain reachable or redirected appropriately.                                            |
| Modules and templates         | Page-level context is preserved or intentionally rebuilt in the target.                                                           |
| Users and access levels       | Login, permission, restricted content, and role meaning remain clear.                                                             |
| Multilingual records          | Translated content remains connected to correct menus, language assignments, and visible pages.                                   |
| Extensions and custom data    | Ownership, support status, and service path are clearly classified.                                                               |
| Commerce records              | Products, customers, orders, and related records are interpreted through the correct commerce component or custom implementation. |

The right acceptance standard is not “all Joomla data was moved.” The stronger standard is that migrated Joomla records still support the site experience, operational access, content management, SEO continuity, and extension-specific business processes that the merchant expects to preserve.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Joomla data model differences come from how Joomla separates content, routes, access, layout, languages, extensions, and custom implementations. Articles, categories, menus, modules, users, access levels, media, metadata, custom fields, templates, plugins, and commerce extension records each carry different migration meaning.

A successful Joomla migration depends on ownership clarity. Joomla core content should be separated from extension-owned data, custom fields should be classified by business purpose, menus and aliases should be treated as structural records, and commerce data should be interpreted through the component that owns it. When custom components, unsupported extension data, external IDs, or bespoke logic affect the target result, Custom Service review should happen before the migration scope is accepted.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Does Joomla have a native product and order data model?**

No. Joomla core is not a complete native e-commerce data model by itself. Product, order, cart, payment, shipping, tax, inventory, and review records depend on the commerce extension or custom component used by the site.

**Are Joomla categories the same as menus?**

No. Categories organize content, while menus define navigation entries, aliases, routes, page context, and often public URL behavior. Both may be needed to preserve a page correctly.

**Can Joomla users be treated as customers during migration?**

Not automatically. Joomla users represent login and permission identities. Commerce customer profiles may belong to a store extension or custom component, and the relationship between the two should be validated separately.

**What happens to modules and templates during a Joomla migration?**

Modules and templates often require setup or validation beyond ordinary content migration. Their assignments, positions, overrides, and display behavior can affect whether migrated pages look and work as expected.

**When does Joomla custom data require Custom Service review?**

Custom Service review is appropriate when the required data is stored in unsupported extensions, custom components, modified tables, custom fields with business logic, external identifiers, or bespoke transformation requirements beyond supported migration behavior.
