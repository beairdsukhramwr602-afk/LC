# Selecting the Right Migration Approach for Shopify

Selecting a Shopify migration approach should begin with the Target Store operating model, not only the number of records being moved. Shopify is a hosted SaaS Target Platform with platform-defined structures for products, options, variants, collections, content, customer records, orders, redirects, apps, metafields, metaobjects, Markets, and storefront behavior. A migration path is sound only when the selected service responsibility matches those structures clearly.

A strong approach separates compatible transfer work, guided execution, optional filtering or mapping, custom handling, Entity Points capacity, and post-launch timing needs before Full Migration begins. That separation prevents a common Shopify planning mistake: treating every requirement as either a simple standard migration or a fully custom project, when many stores need a mixed approach.

### Start with the Platform Migration Scope <a href="#start-with-the-platform-migration-scope" id="start-with-the-platform-migration-scope"></a>

Shopify migration scope should be defined around the business meaning that must remain useful after migration. Record count matters, but it does not explain whether the source-store model can be represented cleanly in Shopify.

Begin by classifying the source store into practical scope groups:

| Scope area                      | Approach question                                                                                                                  | Shopify planning implication                                                                                                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products and variants           | Can source product choices become clear Shopify products, options, and variants?                                                   | Clean product structures may fit Standard Service, while custom options, bundles, personalization, or subscription logic may need Add-ons, Shopify setup, apps, or Custom Service review. |
| Collections and navigation      | Can source categories, filters, and browse paths become Shopify collections, menus, tags, metafields, content pages, or redirects? | Ordinary category-to-collection logic is usually easier than layered navigation, extension-driven merchandising, or complex legacy paths.                                                 |
| Customers and orders            | Are records needed mainly for reference, or do they carry account, loyalty, wholesale, subscription, or external-system meaning?   | Reference history is different from recreating source-side customer behavior or operational workflows.                                                                                    |
| CMS Pages, Blog Posts, and URLs | Which content and paths support trust, SEO, campaigns, support, policies, or buying decisions?                                     | Migration scope should prioritize useful destinations, redirects, and content continuity rather than moving old pages without purpose.                                                    |
| Apps and custom data            | Which values are native source records, and which belong to apps, extensions, custom fields, external systems, or custom logic?    | Compatible values may be mapped or configured; unsupported behavior needs custom review or reconstruction outside ordinary migration.                                                     |
| Markets and localization        | Does the store depend on countries, languages, currencies, domains, localized URLs, or regional catalog behavior?                  | Market-specific expectations should be scoped before choosing the service path because they can affect products, content, redirects, and validation.                                      |

The migration approach should follow the highest-risk scope area, not the easiest one. A small Shopify migration can require Custom Service when custom product logic controls buying behavior. A large Shopify migration can remain suitable for Standard Service when the data is compatible and the customer can review representative results confidently.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be enough when the selected migration path supports the required entities, the Shopify Target Store model is already clear, and the customer is comfortable performing available migration actions on the Next-Cart website.

Standard Service is usually suitable when:

* products, variants, collections, customers, orders, images, CMS Pages, Blog Posts, reviews, coupons, and other selected entities fit supported migration behavior;
* source product options and variants can be reviewed through representative Shopify samples;
* source category or collection-equivalent structures have clear target destinations;
* high-priority URLs have planned Shopify destinations or redirect rules;
* apps are not required to interpret migrated records as business-critical source data;
* customer and order history is mainly needed for reference, service, reporting, or support;
* the customer can review Demo Migration results before approving Full Migration;
* no Custom Platform source structure, unsupported app data, or bespoke source logic controls the core migration outcome.

Standard Service should not be treated as a weak option. For a structurally compatible Shopify migration, it can be the cleanest path because it avoids unnecessary custom scope. The boundary is unsupported meaning. Standard Service can move compatible records; it does not recreate custom applications, source-side business logic, theme behavior, checkout-adjacent workflows, or external-system processes.

### When Managed Service Is a Better Fit <a href="#when-managed-service-is-a-better-fit" id="when-managed-service-is-a-better-fit"></a>

Managed Service is a better fit when the migration path is compatible but the customer wants Next-Cart to handle more of the execution, coordination, review support, or migration-process management.

Managed Service is especially useful when:

* internal teams do not have enough time to manage the migration steps directly;
* the store has many products, variants, collections, customers, orders, CMS Pages, Blog Posts, redirects, or market-specific samples to coordinate;
* Demo Migration results need structured review before Full Migration;
* product, collection, URL, customer, order, and content results must be reviewed by several stakeholders;
* the source store remains active and launch timing requires tighter coordination;
* the migration is compatible but operational pressure makes self-performing the process risky;
* the customer wants clearer responsibility for execution while still keeping scope within supported service behavior.

Managed Service should not be confused with Custom Service. Managed Service addresses execution responsibility and coordination. Custom Service addresses unsupported, bespoke, or custom-handling scope. A Shopify project can need Managed Service without needing Custom Service, and a different project can need Custom Service even when the customer remains closely involved in review and decision-making.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons should be considered when the core migration is compatible but selected data needs filtering, mapping, or configuration support. Add-ons are useful when the Shopify outcome can still be handled within supported migration behavior, but the default migration setup is not precise enough for the business goal.

| Shopify requirement                    | Add-on direction                   | Planning purpose                                                                                                                                                  |
| -------------------------------------- | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Move only selected records             | Data Filter Add-on                 | Limit migration to launch-relevant products, active customers, selected order statuses, recent orders, chosen content, or priority records.                       |
| Align supported fields more precisely  | Advanced Data Mapping              | Map compatible source values into agreed Shopify fields, tags, metafield-ready values, product content, customer references, or order references where supported. |
| Adjust compatible target behavior      | Advanced Data Configure            | Apply agreed configuration behavior for supported migrated records when the migration path allows it.                                                             |
| Extend an Add-on beyond standard scope | Tailored Add-ons or Custom Add-ons | Adapt filtering, mapping, or configuration behavior when the Shopify requirement is still compatible but more specific than standard Add-on coverage.             |

The Add-on boundary must stay clear. Filtering obsolete products is an Add-on-type decision. Interpreting a source app’s subscription logic is not. Mapping a supported product field is an Add-on-type decision. Rebuilding a custom product-builder workflow is not. If the requirement depends on unsupported app records, bespoke business rules, outside-system identifiers, or custom migration logic adjustment, it should move into Custom Service review.

### When Custom Service Is Needed <a href="#when-custom-service-is-needed" id="when-custom-service-is-needed"></a>

Custom Service is needed when the Shopify migration requirement cannot be handled safely through ordinary supported entity movement, Add-ons, or Shopify configuration alone.

Custom Service should be reviewed when the source store includes:

* product structures that cannot be represented cleanly as Shopify products, options, variants, metafields, metaobjects, app data, or content;
* bundles, kits, build-your-own products, personalization workflows, custom options, subscriptions, or product relationships controlled by unsupported source logic;
* collection, navigation, filter, or merchandising behavior driven by source extensions, custom code, complex layered navigation, or external systems;
* app, plugin, module, or extension data that must remain meaningful after migration;
* custom fields, metafield-like values, external identifiers, or outside-system references required for ERP, PIM, WMS, fulfillment, reporting, support, or analytics;
* customer groups, loyalty records, wholesale relationships, subscription status, account behavior, or customer-specific pricing expectations that require special handling;
* order records with custom statuses, operational notes, external references, custom fields, or source-specific business rules;
* localized catalog, content, URL, pricing, domain, or market behavior requiring bespoke handling;
* a Custom Platform source or heavily customized source environment.

Custom Service should be scoped precisely. Some custom requirements are narrow, such as preserving a specific external product ID or mapping a custom value into a controlled target location. Others are broader, such as interpreting subscription records from a source extension and making them meaningful in the future Shopify operating model. The approved approach should clarify which custom items can migrate, which need Shopify app setup, which should be rebuilt manually, and which should be excluded.

### How Entity Points Affect Planning <a href="#how-entity-points-affect-planning" id="how-entity-points-affect-planning"></a>

Entity Points affect planning by determining whether the selected migration scope fits the appropriate Entity Points Plan. They should not be used as a complete measure of Shopify migration complexity.

A large Shopify migration may need a higher Entity Points Plan while remaining suitable for Standard Service if products, customers, orders, content, URLs, and other selected records are structurally compatible. A smaller migration may require Custom Service if a limited number of records depends on unsupported app data, custom product behavior, external identifiers, or bespoke transformation.

Use Entity Points planning to separate useful migration scope from avoidable clutter:

| Entity group                | Planning treatment                                                                                                                                                                            |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core launch data            | Include records needed for selling, service, SEO continuity, reporting, customer support, and operational readiness.                                                                          |
| Selective historical data   | Filter old orders, inactive products, obsolete customers, retired collections, outdated content, or duplicate records when they no longer support launch goals.                               |
| Structurally uncertain data | Review app-owned values, metafields, metaobjects, custom fields, external identifiers, subscriptions, personalized products, or complex relationships before counting them as ordinary scope. |
| Low-value legacy noise      | Exclude, archive, or deprioritize broken media, obsolete redirects, unused fields, abandoned tags, retired campaigns, or outdated app data.                                                   |

The practical question is not only how many records exist. The stronger question is which records should support the future Shopify store and which records would create cost, clutter, or validation burden without business value.

### How Additional Migration Options Affect the Approach <a href="#how-additional-migration-options-affect-the-approach" id="how-additional-migration-options-affect-the-approach"></a>

Additional Migration Options affect the approach when the Source Platform remains active, scope changes after an earlier run, or launch timing requires refreshed data close to cutover. For Shopify, the practical question is whether later activity changes only a small set of records, changes the configuration used to generate Shopify output, or requires a new migration run for the same migration path.

Use Additional Migration Options when:

* the Source Platform continues receiving orders close to launch;
* new products, customers, orders, reviews, CMS Pages, Blog Posts, or content updates appear after migration;
* product, collection, URL, or content decisions change after Demo Migration or Full Migration;
* Shopify configuration changes make earlier migrated results unsuitable;
* filtering, mapping, or configuration decisions are corrected after review;
* custom-scope records are intentionally excluded first and added later after review;
* launch timing requires a final refresh before the Target Store goes live.

The selected option should account for duplicate risk, target cleanup, validation effort, Entity Points capacity, launch timing, and whether the changed scope affects products, variants, collections, URLs, apps, Markets, or customer and order history. If records have already been counted in the service license record, migrating those same counted records again should not be treated as a new Entity Points deduction only because additional migration activity is performed. New Products, Customers, Orders, and Blog Posts still consume Entity Points when they are migrated for the first time under the service license.

### Choosing the Right Path Before Full Migration <a href="#choosing-the-right-path-before-full-migration" id="choosing-the-right-path-before-full-migration"></a>

The right Shopify approach should be chosen before Full Migration, after representative samples expose the real migration behavior.

| Migration situation                                                                                                                                                                         | Recommended path                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Compatible source data, clear Shopify Target Store model, and customer confidence in self-performing migration steps                                                                        | Standard Service with representative Demo Migration review.                                                                                                 |
| Compatible source data, limited internal capacity, launch pressure, or need for Next-Cart-led execution                                                                                     | Managed Service with defined review responsibility.                                                                                                         |
| Compatible data requiring selective movement, field alignment, or agreed configuration behavior                                                                                             | Standard Service or Managed Service with appropriate Add-ons.                                                                                               |
| App-owned data, custom product logic, complex source categories, external identifiers, subscriptions, loyalty, wholesale records, Custom Platform source context, or bespoke transformation | Custom Service review before approving scope.                                                                                                               |
| Active Source Platform with new records or updates expected before launch                                                                                                                   | Plan the suitable Additional Migration Option and define the required revalidation scope.                                                                   |
| Changed mapping, corrected Shopify configuration, revised scope, or intentionally refreshed earlier migrated results                                                                        | Choose between continuing with the last used configuration, continuing with a new configuration, or performing a new migration for the same migration path. |

A strong Shopify approach does not force every requirement into one service path. It identifies compatible migration work, guided execution needs, optional filtering or mapping, custom review, Entity Points capacity, launch-timing requirements, and final review responsibility before the migration moves into production execution.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting the right Shopify migration approach requires more than choosing a service by store size. Shopify’s hosted SaaS model, product and variant structure, collections, URLs, apps, metafields, Markets, customer expectations, order history, and launch timing all shape the correct path.

Standard Service, Managed Service, Add-ons, Custom Service, Entity Points planning, and Additional Migration Options each solve different planning problems. The best approach is the one that separates compatible migration work, expert-led execution needs, optional filtering or mapping, bespoke handling, capacity planning, and launch updates before Full Migration begins.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Standard Service enough for a Shopify migration?**

Standard Service can be enough when the selected migration path supports the required entities, the Shopify Target Store model is clear, and Demo Migration confirms that representative products, collections, customers, orders, content, and URLs behave correctly.

**When should a Shopify project use Managed Service?**

Managed Service is appropriate when the migration path is compatible but the customer wants Next-Cart to handle more execution, coordination, or review support. It is especially useful when internal capacity, launch timing, or stakeholder coordination makes customer-led execution risky.

**Are Add-ons the same as Custom Service?**

No. Add-ons support filtering, mapping, or configuration for compatible migration work. Custom Service is used when the requirement involves unsupported structures, app-owned data, custom logic, outside-system identifiers, Custom Platform source context, or bespoke transformation.

**Do Entity Points measure Shopify migration complexity?**

No. Entity Points help determine the Entity Points Plan for the selected migration scope. They do not fully measure product-model pressure, app dependence, metafield strategy, Markets, URL risk, custom business logic, or validation effort.

**Should Additional Migration Options be planned before Shopify launch?**

They should be considered when the source store remains active, new records are expected before launch, or mapping and configuration decisions may change after earlier migration runs. The selected option should match the business need, duplicate risk, validation scope, and launch timing.

**Does Custom Service automatically mean Next-Cart performs the whole migration?**

No. Custom Service defines custom handling scope. Managed Service determines whether Next-Cart handles more of the execution, coordination, and migration-process management.
