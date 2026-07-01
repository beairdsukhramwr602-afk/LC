# Phoca Cart Selecting the Right Migration Approach

Choosing the right Phoca Cart migration approach starts with scope clarity. Phoca Cart is a Joomla e-commerce extension, so a project can involve both commerce data and Joomla-specific operating context: products, categories, manufacturers, attributes, options, specifications, customers, customer groups, orders, coupons, reward points, tax, shipping, payment plugins, invoices, currencies, languages, modules, templates, access levels, custom fields, integrations, and storefront paths.

The right approach is not determined only by catalog size. It is determined by how much business meaning must be moved as ordinary supported data, how much target setup is required, how much requires Add-ons, and whether custom or extension-owned behavior needs Custom Service review. A small Phoca Cart store can need a more careful approach if product options, customer groups, payment/shipping logic, or custom Joomla extensions are central to business operations.

| Decision area               | Standard implication                                                                | Higher-planning implication                                                                                          |
| --------------------------- | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Catalog structure           | Products, categories, manufacturers, images, and supported product fields are clear | Options, attributes, specifications, downloads, product relationships, or custom fields need interpretation          |
| Buyer and order data        | Customers and orders are ordinary and readable                                      | Customer groups, group prices, coupons, rewards, tax, shipping, payment, and document history carry business meaning |
| Storefront structure        | Joomla presentation can be configured normally after migration                      | Menus, aliases, modules, filters, templates, and SEO paths must preserve continuity                                  |
| Extensions and integrations | Plugins mainly support target configuration                                         | Extension-owned data, POS workflows, external IDs, or custom tables must be reviewed                                 |
| Service control             | Merchant can run and validate the process independently                             | Next-Cart-led execution, Add-ons, or Custom Service review is safer                                                  |

### Start with the Platform Migration Scope <a href="#start-with-the-platform-migration-scope" id="start-with-the-platform-migration-scope"></a>

The service path should begin with a clear view of what the Phoca Cart migration must accomplish. Moving records into Phoca Cart is different from recreating every Joomla storefront behavior, extension dependency, plugin setting, or custom workflow. Scope should identify the target result in practical terms: what data should be available, what should be configured, what should be validated, and what needs separate review.

For Phoca Cart, scope usually begins with products, categories, manufacturers, product images, customers, orders, coupons, reviews where applicable, and other supported records. Scope becomes more sensitive when product options, attributes, specifications, reward points, customer groups, tax, shipping, payment methods, invoices, multilingual data, currencies, downloads, modules, or template behavior affect how the migrated store will be operated.

| Scope question                                                       | Why it matters for Phoca Cart                                                                                                                 |
| -------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Is the target Joomla and Phoca Cart environment already defined?     | The service approach cannot be evaluated accurately when the target version, template, modules, language setup, or plugin stack is uncertain. |
| Are product-detail layers easy to interpret?                         | Attributes, options, specifications, and parameters may need different mapping or configuration treatment.                                    |
| Do customer groups affect prices, access, benefits, or tax behavior? | Buyer segmentation can change the meaning of products and orders.                                                                             |
| Do historical orders need operational detail?                        | Orders may be needed for service, accounting reference, warranty review, invoice review, or customer support.                                 |
| Are plugin-owned or custom records involved?                         | Non-standard data may require Custom Service instead of ordinary service capability.                                                          |

A scope decision should also separate historical data from future behavior. Historical orders may preserve what happened before migration, while future tax, shipping, payment, invoice, email, and checkout behavior depends on target-side configuration. Treating those as one task often leads to choosing an approach that is too light.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the selected migration path supports the required data, the source records are clear, the target Phoca Cart installation is ready, and the merchant can run and review the migration through the standard Next-Cart process. This fit is strongest when the project focuses on supported entities and does not require custom data transformation.

A standard-oriented Phoca Cart migration often has straightforward products, clean category relationships, clear customer records, readable order history, ordinary images, ordinary currencies and languages, and target configuration that can be handled separately inside Joomla and Phoca Cart. It can also work when attributes or options exist but are well documented and fit supported mapping behavior.

| Standard Service signal                                   | What it suggests                                                              |
| --------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Product records are clean and consistently structured     | Catalog data can likely be handled through the selected migration path.       |
| Product options and attributes are simple                 | Mapping needs may remain manageable without custom transformation.            |
| Customer groups are limited or not business-critical      | Buyer segmentation is less likely to complicate migration scope.              |
| Orders mainly need readable historical reference          | Future checkout configuration can be handled separately.                      |
| Joomla presentation can be rebuilt or configured normally | Templates, modules, menus, and layout are not being treated as migrated data. |

Standard Service should not be chosen simply because the store is small. It should be chosen because the project requirements match standard service capability. If the merchant expects custom product interpretation, extension-owned records, plugin behavior, POS continuity, or advanced storefront reconstruction, another approach should be reviewed.

### When Managed Service Is a Better Fit <a href="#when-managed-service-is-a-better-fit" id="when-managed-service-is-a-better-fit"></a>

Managed Service is a better fit when the merchant wants Next-Cart-led execution while the project still fits standard service capability and supported Add-ons. It can be useful when the store owner does not want to self-perform the migration process or when the data requires careful handling but not bespoke transformation.

Phoca Cart projects often benefit from Managed Service when there are many product-detail layers, many categories, important customer groups, order-history review needs, multiple languages or currencies, discount and reward behavior, tax/shipping/payment context, or Demo Migration samples that require coordinated interpretation. Managed Service can reduce execution burden, but it should not be mistaken for Custom Service.

| Managed Service signal                 | Why it helps                                                                               |
| -------------------------------------- | ------------------------------------------------------------------------------------------ |
| Merchant wants Next-Cart-led execution | The project can be handled with less self-service workload.                                |
| Data is supported but review-heavy     | Catalog, order, and customer examples can be interpreted more carefully during execution.  |
| Multiple Add-ons may be purchased      | Managed coordination can keep filtering, mapping, or configuration-related work aligned.   |
| Demo Migration review needs guidance   | Representative samples can be reviewed against the service path before Full Migration.     |
| Launch timing is important             | Coordinated execution reduces avoidable delays from unclear inputs or missed review steps. |

Managed Service remains bounded by standard service capability. If the project requires unsupported data handling, modified Add-ons, project-specific Add-ons, custom migration logic adjustment, or Custom Platform handling, Custom Service should be reviewed instead.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons should be considered when a defined optional service feature can improve the migration result without changing the project into bespoke custom work. For Phoca Cart, Add-ons are often relevant when the merchant needs filtering, mapping, or configuration-related support for supported records.

The key discipline is to define the exact requirement. Add-ons should not be used as a vague way to cover all complexity. If a requirement cannot be described as a supported optional feature, or if it requires a modified or new service behavior, Custom Service review is safer.

| Add-on area                 | Phoca Cart use case                                                                                                                                 | Boundary to watch                                                                              |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Data Filter                 | Migrating only selected products, customers, orders, categories, groups, or date ranges                                                             | Entered quantities are not filters by themselves; filtering conditions must be explicit.       |
| Advanced Data Mapping       | Aligning source fields with Phoca Cart categories, attributes, options, specifications, customer groups, order statuses, or supported target fields | Mapping must be understandable and supported; unsupported transformations need Custom Service. |
| Advanced Data Configure     | Applying supported configuration-level adjustments during migration                                                                                 | Configuration support does not replace target Joomla/Phoca Cart implementation work.           |
| Additional selected options | Preserving IDs, recent data handling, or other options where available and relevant                                                                 | Options should match the migration goal, not be selected automatically.                        |

If a Standard Add-on needs to be modified, it becomes a Tailored Add-on and belongs under Custom Service. If the project needs a newly created Add-on or a project-specific capability, it becomes a Custom Add-on and also belongs under Custom Service.

### When Custom Service Is Needed <a href="#when-custom-service-is-needed" id="when-custom-service-is-needed"></a>

Custom Service should be reviewed when the migration involves unsupported data, Custom Platform handling, complex transformations, custom migration logic adjustment, modified Add-ons, Custom Add-ons, plugin-owned data, custom Joomla tables, or non-standard Phoca Cart behavior. It is also relevant when business meaning cannot be preserved through ordinary field mapping or target configuration.

Common Phoca Cart Custom Service triggers include custom product-option logic, unusual stock rules, POS-related data, external system IDs, third-party payment or shipping records, custom invoice history, bespoke Joomla plugins, custom table structures, old Phoca Cart behavior that differs from the target environment, and source data that combines product, buyer, discount, and checkout meaning in non-standard ways.

| Custom Service trigger             | Why standard handling may be insufficient                                 |
| ---------------------------------- | ------------------------------------------------------------------------- |
| Unsupported extension data         | The records may not belong to ordinary Phoca Cart entities.               |
| Custom fields or custom tables     | The data may need interpretation before it can be moved or transformed.   |
| Complex product logic              | Options, specifications, stock, downloads, or prices may not map cleanly. |
| POS or external-system identifiers | Business workflows may depend on identifiers outside ordinary store data. |
| Modified Add-on requirement        | Changing a Standard Add-on creates Tailored Add-on scope.                 |
| Project-specific new capability    | Creating a Custom Add-on or custom logic belongs under Custom Service.    |

Custom Service does not mean every complex store is impossible to migrate. It means the project needs a reviewed scope, clear requirements, and appropriate handling before Full Migration is approved.

### How Entity Points Affect Planning <a href="#how-entity-points-affect-planning" id="how-entity-points-affect-planning"></a>

Entity Points affect planning because migration cost and scope are tied to the volume and type of data being migrated. In a Phoca Cart project, the practical concern is not only how many products, customers, or orders exist. The concern is also whether records are duplicated, filtered, remigrated, or expanded by selected service options.

Entity planning should consider products, categories, manufacturers, customers, orders, reviews if applicable, coupons, images, and other selected entities. It should also consider whether recent data, re-migration, or duplicate-consumption rules apply under the selected service path. A store with many orders, customer groups, product images, or historical data can have a different planning profile from a store with the same product count but limited history.

| Entity planning area              | Phoca Cart planning question                                                                  |
| --------------------------------- | --------------------------------------------------------------------------------------------- |
| Product volume                    | Are products simple, option-heavy, image-heavy, downloadable, or assigned to many categories? |
| Customer and order volume         | Are all historical records needed, or should a defined subset be considered?                  |
| Category and manufacturer records | Are these structures clean, duplicated, or used for storefront discovery?                     |
| Coupon and reward-related records | Are benefits active, historical, or only needed as order context?                             |
| Repeated migration activity       | Will additional migration runs consume additional Entity Points?                              |

Entity Points should be reviewed before migration activity begins, especially when the merchant expects filtering, recent-data handling, or repeated migration activity. This prevents cost and scope surprises after Demo Migration or Full Migration planning has already begun.

### How Additional Migration Options Affect the Approach <a href="#how-additional-migration-options-affect-the-approach" id="how-additional-migration-options-affect-the-approach"></a>

Additional Migration Options should be selected only when they support a specific Phoca Cart migration goal. They should not be treated as a default checklist. Options can be valuable when they preserve business continuity, improve launch control, or reduce manual cleanup, but they should be connected to the actual target store requirements.

For Phoca Cart, useful Additional Migration Options may relate to preserving identifiers, handling recent data, clearing target data before migration when appropriate, maintaining SEO-related continuity, preserving customer passwords where supported, or handling images and relationships in ways that reduce launch risk. The right choice depends on the source platform, target Phoca Cart setup, selected migration path, and business requirements.

| Additional option concern    | When it may matter for Phoca Cart                                                                        |
| ---------------------------- | -------------------------------------------------------------------------------------------------------- |
| ID preservation              | External systems, historical references, or operational records depend on old identifiers.               |
| Recent data handling         | The source store remains active during the migration window.                                             |
| Target cleanup               | Test data or previous imports could interfere with the final migrated result.                            |
| SEO-related handling         | Product and category paths, aliases, metadata, or redirects are launch-sensitive.                        |
| Image handling               | Product images, galleries, thumbnails, or generated image behavior are important to storefront quality.  |
| Password/customer continuity | Customer account continuity is important and technically supported for the source and target conditions. |

Options should be confirmed before Full Migration, not added after validation reveals predictable gaps. If an option depends on technical conditions, source platform limitations, or target setup, those conditions should be reviewed before selection.

### Choosing the Right Path Before Full Migration <a href="#choosing-the-right-path-before-full-migration" id="choosing-the-right-path-before-full-migration"></a>

The final approach should be chosen before Full Migration based on evidence from preparation and Demo Migration. If Demo Migration samples are too simple, the chosen path can appear stronger than it really is. A strong Phoca Cart sample set should include catalog complexity, buyer segmentation, order history, configuration-sensitive behavior, multilingual or multicurrency examples, Joomla storefront paths, and extension-owned data where relevant.

| Demo Migration result                                    | Recommended response                                                                                                        |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Supported records migrate cleanly and behave as expected | Continue with the selected approach after normal validation.                                                                |
| Records migrate but target setup is incomplete           | Complete Joomla, Phoca Cart, template, module, language, tax, shipping, or payment configuration before judging the result. |
| Important fields need clearer alignment                  | Review mapping, configuration, or suitable Add-ons.                                                                         |
| Extension-owned or custom data is missing                | Review Custom Service before Full Migration.                                                                                |
| Entity volume or repeated migration activity is unclear  | Review Entity Points, filtering, and migration-window planning.                                                             |
| Demo samples do not expose real complexity               | Expand samples before approving Full Migration.                                                                             |

The chosen approach is too light when the project depends on hidden logic, custom fields, unsupported extensions, POS workflows, external IDs, unusual product logic, or target behavior that has not been prepared. It is also too light when a merchant expects migration to automatically rebuild Joomla templates, menus, modules, payment plugins, shipping plugins, invoice layouts, or checkout configuration.

A good Phoca Cart approach should be clear enough to answer four questions: what will migrate through the selected path, what must be configured in the target store, which Add-ons are being used, and whether Custom Service is needed before Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Phoca Cart migration approach depends on how much business meaning must be moved, configured, mapped, or customized. Standard Service may be enough when supported data is clean, the target environment is ready, and the merchant can self-perform the process. Managed Service is stronger when the project fits standard capability but needs Next-Cart-led execution. Add-ons help with defined optional features. Custom Service should be reviewed when unsupported data, custom logic, plugin-owned records, modified Add-ons, or Custom Platform handling are involved.

Phoca Cart projects should choose the approach after confirming the Joomla environment, Phoca Cart version, catalog structure, customer groups, order history, tax, shipping, payment context, multilingual requirements, storefront dependencies, extension stack, Entity Points, Additional Migration Options, and Demo Migration samples. Choosing the path early prevents migration scope from being discovered only after validation problems appear.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Can Standard Service be enough for Phoca Cart migration?**

Yes. Standard Service can be enough when the selected migration path supports the required data, the target Phoca Cart store is ready, and the merchant can self-perform the migration without custom data transformation.

**When is Managed Service a better fit for Phoca Cart?**

Managed Service is a better fit when the merchant wants Next-Cart-led execution and the project still fits standard service capability, including any supported Add-ons purchased for filtering, mapping, or configuration-related needs.

**When should Custom Service be reviewed?**

Custom Service should be reviewed when the project includes unsupported extension data, custom Joomla tables, custom fields, POS workflows, external identifiers, custom product logic, modified Add-ons, Custom Add-ons, or custom migration logic adjustment.

**Do Add-ons replace Custom Service?**

No. Add-ons support defined optional service features. If the requirement needs bespoke transformation, modified Add-ons, project-specific Add-ons, or unsupported data interpretation, Custom Service should be reviewed.

**Why should Demo Migration influence the approach decision?**

Demo Migration shows whether representative Phoca Cart data behaves correctly before Full Migration. If complex products, customer groups, orders, tax, shipping, payment context, storefront paths, or custom data do not validate well, the service path should be reviewed before proceeding.
