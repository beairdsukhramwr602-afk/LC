# Joomla Validation Priorities

Joomla validation should prove that migrated data still functions inside a Joomla site, not only that records are present in the administrator area. Joomla can hold content, menus, categories, users, access levels, modules, templates, custom fields, tags, media, redirects, multilingual relationships, and extension records. Those elements work together to create the page a visitor sees and the administration experience a site owner uses.

For migration planning, the most important validation question is whether each record keeps its practical meaning after it reaches Joomla. An article without its menu path may not support the same URL. A user without the correct group or access level may not see the intended content. A module without the correct position or assignment may not appear where the site relies on it. A commerce record may look complete only after the owning extension proves product, customer, order, checkout, payment, shipping, tax, coupon, and inventory behavior.

### Validation Should Prove Joomla Usability <a href="#validation-should-prove-joomla-usability" id="validation-should-prove-joomla-usability"></a>

Joomla validation should begin with relationship proof. A record-level review can confirm whether data exists, but it cannot prove whether the site is ready to use. The stronger review asks whether content, navigation, access, language, media, layout, and extension behavior still support the intended visitor and administrator experience.

| Validation question               | Joomla proof required                                                                                                                | Failure signal                                                                               |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| Is the record present?            | Content, users, categories, menu items, modules, media, fields, and supported extension records appear in the expected Joomla areas. | Counts look acceptable, but important samples are missing or disconnected.                   |
| Does the record preserve meaning? | Menus, categories, routes, access levels, language assignments, custom fields, and metadata support the intended purpose.            | Data exists but no longer behaves like the source page, customer area, or storefront record. |
| Does the page experience work?    | Visitor-facing pages render with the expected content, module context, template behavior, media, and permissions.                    | The administrator record exists, but the public page is incomplete or hard to reach.         |
| Is extension ownership clear?     | Commerce, membership, directory, booking, or form data is validated inside the component or extension that owns it.                  | Joomla users or articles are confused with complete commerce or membership records.          |
| Is launch risk classified?        | Findings are separated into migration correction, Joomla setup, Add-ons, Custom Service, manual rebuild, or accepted limitation.     | All findings are treated as generic cleanup with no owner or handling path.                  |

Validation should include ordinary examples and edge cases. A simple Joomla site may only need representative content, menu, user, media, and redirect samples. A commerce-connected or membership-heavy Joomla site needs deeper samples covering extension-owned records, restricted access, checkout-related paths, customer identity, custom fields, and multilingual behavior where applicable.

### Validate Core Content and Category Relationships <a href="#validate-core-content-and-category-relationships" id="validate-core-content-and-category-relationships"></a>

Core content validation should confirm whether Joomla articles, categories, featured content, custom fields, tags, metadata, and media remain useful after migration. Content can be technically present but still fail if it loses page purpose, category assignment, access boundary, language assignment, or media reference.

A practical sample set should include high-traffic pages, long-form pages, policy pages, landing pages, content assigned to nested categories, content with custom fields, tagged content, pages with embedded media, and pages that support commerce, membership, or lead generation. These samples help reveal whether the migrated Joomla structure is usable rather than merely populated.

| Content area           | What to validate                                                                                               | Useful sample choices                                                                                 |
| ---------------------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Articles and CMS Pages | Title, alias, body content, status, category, metadata, language, access, custom fields, and media references. | High-traffic pages, policy pages, content-rich landing pages, pages with images or documents.         |
| Categories             | Parent-child structure, assignments, status, language, access, metadata, and relationship to menus or modules. | Deep category trees, categories used in navigation, categories used by commerce or directory content. |
| Custom fields          | Field values, display context, repeatable patterns, optional values, and template dependency.                  | Records where fields affect display, filtering, structured content, or business interpretation.       |
| Tags                   | Tag assignments and discovery use.                                                                             | Tagged articles, category pages, or content modules that depend on tags.                              |
| Media                  | Images, documents, downloads, thumbnails, paths, and embedded references.                                      | Media-heavy articles, product-like pages, downloadable files, and category images.                    |

The pass condition is that content can still be found, interpreted, edited, and presented in Joomla with the expected context. If content has to be reconnected manually to menus, modules, language records, or media, validation should classify that as a real launch task rather than a cosmetic issue.

### Validate Menus, Aliases, Routes, and Redirect-Sensitive Pages <a href="#validate-menus-aliases-routes-and-redirect-sensitive-pages" id="validate-menus-aliases-routes-and-redirect-sensitive-pages"></a>

Joomla routing depends heavily on menus, aliases, categories, language structure, and extension behavior. Validation should therefore check public-facing URLs and route context, not just the presence of menu records. A migrated page may exist in Joomla but still fail if visitors reach a different URL, lose the expected module context, or land on the wrong language version.

High-value URL samples should include primary navigation pages, hidden menu paths, category pages, content pages with external links, landing pages used in campaigns, pages with SEO-sensitive metadata, and commerce or membership paths where applicable. Validation should compare what the user expects to reach with what Joomla actually renders.

| Route validation area    | Proof required                                                                           | Risk signal                                                                |
| ------------------------ | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Menu hierarchy           | Menu items preserve the intended navigation structure and target records.                | Pages are present but detached from the expected navigation path.          |
| Aliases and SEF paths    | Important aliases and search-friendly paths produce the expected pages or redirect plan. | URLs change without explanation or land on the wrong content.              |
| Hidden menus             | System or hidden menu paths still support important routes.                              | A page works in the backend but not as a stable public route.              |
| Metadata                 | Titles, descriptions, and route-specific metadata are retained or rebuilt where needed.  | SEO-sensitive pages lose page-level meaning even when content migrates.    |
| Redirect-sensitive pages | Old high-value URLs have an accepted redirect or replacement plan.                       | Broken links, irrelevant redirects, or duplicate paths appear near launch. |

A route should not pass only because it loads. It should land on the intended page, in the intended language, with the intended layout, access rule, metadata, and module context.

### Validate Users, Groups, Access Levels, and Permissions <a href="#validate-users-groups-access-levels-and-permissions" id="validate-users-groups-access-levels-and-permissions"></a>

Joomla user validation should prove identity and visibility, not only account transfer. Joomla sites often use user groups, access levels, permissions, and extension-specific customer records to control what visitors, members, customers, editors, staff, or partners can access.

The strongest validation sample includes public users, registered users, custom groups, restricted pages, restricted menu items, restricted modules, administrator or editor-like accounts, and commerce or membership customers where applicable. The review should separate Joomla account meaning from extension-owned customer meaning.

| User/access area           | Pass condition                                                                | Failure signal                                                                                         |
| -------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| User accounts              | Users can be identified and used in the intended Joomla context.              | Accounts exist but cannot perform expected actions or access expected content.                         |
| User groups                | Group relationships preserve the expected visibility or workflow meaning.     | Users inherit too much access, too little access, or wrong group membership.                           |
| Access levels              | Content, menus, modules, and extension areas appear to the correct audiences. | Restricted content becomes public, or public content becomes restricted.                               |
| Administrative roles       | Staff, editors, or administrators retain appropriate management capability.   | Editorial workflow breaks or risky permissions are introduced.                                         |
| Commerce/customer identity | Customer behavior is checked inside the owning commerce extension.            | A Joomla user exists but addresses, order history, shopper groups, or checkout identity do not follow. |

Permissions should be tested through user behavior, not only configuration screens. A restricted page should be visited as the correct user type. A customer record should be opened in the relevant commerce extension. An editor account should be tested against the workflow it actually supports.

### Validate Modules, Templates, Overrides, and Page Assembly <a href="#validate-modules-templates-overrides-and-page-assembly" id="validate-modules-templates-overrides-and-page-assembly"></a>

A Joomla page is rarely just the main content record. Modules, template positions, template overrides, layouts, plugins, and styling rules often complete the visitor experience. Validation should confirm whether the page still renders with the surrounding elements that make it usable.

Representative page samples should include a homepage, a category page, a content page, a login or account-related page, a search result path, a multilingual page, and commerce or extension pages where applicable. Pages that use custom HTML modules, menu modules, banners, filtered lists, or special template positions should receive special attention.

| Page assembly element | What to validate                                                                                            | Common launch issue                                                                          |
| --------------------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Modules               | Assignment, position, language, access level, ordering, and visibility.                                     | Modules are imported or recreated but appear on the wrong pages or for the wrong users.      |
| Templates             | Correct template assignment and layout behavior for important pages.                                        | Content exists but renders through an unexpected layout.                                     |
| Overrides             | Template or layout overrides still support the intended display where rebuilt or retained.                  | The migrated data is correct but the page no longer looks or functions as expected.          |
| Plugins               | Content, routing, media, search, form, or commerce behavior triggered by plugins is checked where relevant. | Stored content loses behavior because a plugin dependency was not carried into target setup. |
| Extension pages       | Component output is validated through public pages, not only administrator records.                         | Products, forms, directories, or bookings exist but do not render correctly.                 |

The pass condition is practical: the important pages still make sense to visitors and administrators. When layout behavior belongs to target-side theme or template setup, the validation report should not classify incorrectly it as migrated content failure.

### Validate Multilingual Structure <a href="#validate-multilingual-structure" id="validate-multilingual-structure"></a>

Joomla multilingual validation should prove that language-specific content, menus, modules, categories, associations, metadata, media, and extension records still work together. Translated records alone do not prove readiness. Visitors should reach the intended language version and move between translations where equivalent content exists.

A useful multilingual sample set includes fully translated pages, pages translated into only some languages, language-specific menus, language-specific modules, categories assigned to languages, media references by language, and extension-owned language fields where applicable.

| Multilingual area            | What the result must prove                                                                   | Failure signal                                                                                     |
| ---------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Language-specific content    | Articles, categories, metadata, media, and fields carry the correct language meaning.        | Translated records exist but appear under the wrong language or wrong page path.                   |
| Language menus               | Each language has the right navigation path and landing structure.                           | Language pages load without the expected menu context.                                             |
| Language associations        | Equivalent pages are linked where the site expects language switching.                       | Visitors cannot move between translated versions or land on unrelated content.                     |
| Modules by language          | Modules appear only in the intended language context.                                        | Banners, menus, footer content, or search modules show in the wrong language.                      |
| Extension-owned translations | Commerce, form, directory, or membership records preserve language behavior where supported. | Product pages or customer-facing labels are translated in content but not in the owning component. |

Multilingual validation should also record accepted limitations. If some language relationships are rebuilt manually or handled through target-side setup, the validation report should state that clearly.

### Validate Extension-Owned and Commerce Records Separately <a href="#validate-extension-owned-and-commerce-records-separately" id="validate-extension-owned-and-commerce-records-separately"></a>

Joomla extensions can own data that Joomla core does not define. A commerce extension may own products, categories, options, customer records, orders, payments, shipment methods, tax logic, coupons, discounts, inventory, and storefront routes. A membership, booking, directory, form, event, or page-builder extension can have equally important records outside ordinary content migration.

Validation should identify the owning component before judging the result. A Joomla category is not automatically a product category. A Joomla user is not automatically a commerce customer. A Joomla article is not automatically a product page. Each extension record should be validated inside its own structure and public output.

| Extension data type                        | Validation focus                                                                                                                  | Handling path when unsupported                                                             |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Commerce products                          | Product fields, categories, options, images, pricing, tax context, inventory, and public routes.                                  | Custom Service review, manual rebuild, or accepted exclusion.                              |
| Customers and orders                       | Customer identity, addresses, order history, totals, statuses, payment/shipping context, and ownership by the commerce component. | Custom Service review where records are unsupported or custom.                             |
| Membership or restricted-content records   | Subscription or membership status, access rules, user links, and restricted content behavior.                                     | Custom Service review or target-side configuration.                                        |
| Booking, event, directory, or form records | Record fields, submitted data, public display, notification or workflow expectations.                                             | Custom Service review, integration work, or manual rebuild.                                |
| Page-builder or layout data                | Editability, display, reusable blocks, and relationship to content records.                                                       | Manual rebuild, target setup, or Custom Service review if data transformation is required. |

This classification protects the project from approving a Joomla migration that preserves core CMS data but leaves business-critical extension behavior unproven.

### Validate Demo Migration and Later Migration Activity <a href="#validate-demo-migration-and-later-migration-activity" id="validate-demo-migration-and-later-migration-activity"></a>

Demo Migration should provide evidence, not just reassurance. For Joomla, a useful Demo Migration sample should test at least one ordinary content page, one menu-linked page, one media-heavy page, one restricted page, one user or group example, one multilingual example if applicable, one redirect-sensitive page, and one extension-owned record where extensions are part of scope.

Later migration activity should also be validated according to what changed. If new content, users, media, redirects, form submissions, products, customers, or orders appear after the first run, the next review should focus on new eligible records and representative regression samples. If the configuration changes, the affected mapping, filtering, or handling rules need renewed validation. If a new migration replaces the earlier target result, the broader target result needs review again.

| Migration activity                        | Validation emphasis                                                                                            |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Continue with the last used configuration | Newly added source records and regression samples from previously reviewed Joomla areas.                       |
| Continue with a new configuration         | Newly migrated records plus the records affected by changed mapping, filtering, or configuration.              |
| Perform a new migration                   | Refreshed target result, replaced earlier migrated data, critical relationships, and launch-readiness samples. |

Entity Points should remain a planning control, not a validation substitute. Newly migrated eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

### Build a Joomla Validation Report <a href="#build-a-joomla-validation-report" id="build-a-joomla-validation-report"></a>

A Joomla validation report should turn findings into launch decisions. It should not only list screenshots, counts, or vague notes. Each finding should identify the sample, the expected result, the observed result, severity, likely owner, handling path, and final status.

| Report field    | Purpose                                                                                                                        |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Sample          | Identifies the article, menu item, user, module, route, extension record, product, order, or multilingual page being reviewed. |
| Expected result | States what the migrated result should prove.                                                                                  |
| Observed result | Describes what Joomla actually shows or does.                                                                                  |
| Severity        | Separates launch blockers from acceptable cleanup.                                                                             |
| Handling path   | Classifies correction, Joomla setup, Add-on adjustment, Custom Service review, manual rebuild, or accepted limitation.         |
| Owner           | Assigns responsibility to the merchant, Next-Cart, Joomla setup team, developer, or external partner.                          |
| Status          | Confirms whether the finding is open, corrected, accepted, deferred, or outside scope.                                         |

The report should include enough representative samples to prove the Joomla migration pattern. A weak report can approve present records while missing broken routes, wrong access rules, disconnected modules, unsupported extension data, or unvalidated commerce behavior.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Joomla validation should prove that migrated records still work as a site, not only as database entries. Content, categories, menus, routes, users, access levels, modules, templates, custom fields, media, multilingual relationships, and extension-owned records all contribute to the final result.

The strongest validation process reviews representative records, tests public-facing behavior, separates Joomla core from extension-owned data, classifies findings by handling path, and confirms whether the result is usable for visitors, administrators, customers, editors, and launch stakeholders. A Joomla migration should be approved because the target result works in context, not because counts look acceptable.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is checking record counts enough to validate a Joomla migration?**

No. Record counts can confirm basic completeness, but Joomla validation also needs relationship checks. Content should connect to categories, menus, routes, access rules, modules, templates, media, language assignments, and extension-owned behavior where applicable.

**Why should Joomla menus and routes be validated separately?**

Menus and aliases strongly influence visitor-facing paths, page context, metadata, and module assignment. A page may exist in Joomla while the expected URL, navigation path, or public display is still wrong.

**Should Joomla users be validated as customers?**

Only when the owning commerce extension uses them that way. Joomla core users should be checked for identity, groups, access levels, and permissions. Customer addresses, shopper groups, order history, or checkout context may belong to the commerce extension instead.

**How should extension-owned records be validated?**

They should be validated inside the component or extension that owns them and through representative public output where relevant. Unsupported or custom extension records should be classified for Custom Service review, manual rebuild, target setup, or accepted exclusion.

**Does continuing migration activity change Joomla validation?**

Yes. Newly added source records, changed configuration, or a new migration can change what needs to be reviewed. Validation should match the action performed and should include regression samples from important Joomla relationships.
