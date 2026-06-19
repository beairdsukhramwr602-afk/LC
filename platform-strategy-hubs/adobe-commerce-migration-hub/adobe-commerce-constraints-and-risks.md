# Adobe Commerce Constraints and Risks

Adobe Commerce migration risk rarely comes from record volume alone. The larger risk is whether the source store’s commercial rules, buyer relationships, catalog governance, storefront scope, integrations, and operational workflows can be represented correctly in the Target Store.

A migration can look complete at record level while still failing business validation. Products may exist but use the wrong attribute structure. Customers may transfer but lose company-account context. Shared catalogs may be present but expose the wrong assortment or price. Campaign content may migrate but lose timing context. URLs may resolve but fail to preserve high-value routes. Integrations may reconnect but lose the identifiers needed for ERP, CRM, PIM, tax, fulfillment, marketplace, or reporting continuity.

A strong Adobe Commerce migration plan treats constraints as design inputs. The goal is not to remove Adobe Commerce complexity. The goal is to identify which parts of that complexity must be preserved, rebuilt, simplified, configured in the Target Store, or handled through Add-ons or Custom Service before launch.

### Constraint Summary for Adobe Commerce Migration <a href="#constraint-summary-for-adobe-commerce-migration" id="constraint-summary-for-adobe-commerce-migration"></a>

| Constraint area                      | Main risk                                                                                                                                                                                           | Planning response                                                                                                                                  |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| B2B company structure                | Individual customer records migrate, but company hierarchy, administrators, users, permissions, credit behavior, quote access, purchase order logic, or buying authority does not behave correctly. | Audit company accounts, company users, administrators, roles, purchasing controls, and account-level relationships before migration configuration. |
| Shared catalogs                      | Company-specific visibility or pricing differs from the intended buyer experience.                                                                                                                  | Confirm shared catalog ownership, product assignment, customer group assignment, company assignment, and custom pricing requirements.              |
| Website, store, and store-view scope | Data appears correct globally but fails by region, language, brand, storefront, customer segment, or business channel.                                                                              | Define the Adobe Commerce scope model before mapping source storefront differences.                                                                |
| Product and attribute architecture   | Products transfer as records but fail variant selection, filtering, navigation, pricing, reporting, or catalog maintenance.                                                                         | Review product types, child SKU relationships, attributes, attribute sets, and category logic before migration.                                    |
| Content Staging and campaigns        | Scheduled commercial changes become static content or lose launch timing.                                                                                                                           | Separate evergreen content from scheduled campaign behavior and decide what must be recreated or validated in Adobe Commerce.                      |
| Inventory and fulfillment            | Stock values do not reflect source assignment, sales-channel availability, salable quantity, reservations, warehouses, or fulfillment integrations.                                                 | Align stock migration with the target fulfillment model rather than treating inventory as one quantity field.                                      |
| URL and SEO continuity               | Product, category, CMS Page, Blog Post, or custom routes change without proper rewrite and redirect planning.                                                                                       | Audit high-value URLs, rewrite needs, route conflicts, and post-migration redirect behavior before go-live.                                        |
| Extensions and integrations          | Extension-owned fields, ERP identifiers, bespoke workflows, or external-system relationships are omitted or flattened.                                                                              | Classify extension and integration-owned data early and route unsupported behavior through Custom Service when needed.                             |

These constraints do not automatically mean Adobe Commerce is the wrong Target Platform. They mean the migration plan must include the operating behavior behind the records.

### B2B Controls Can Carry More Risk Than Customer Counts <a href="#b2b-controls-can-carry-more-risk-than-customer-counts" id="b2b-controls-can-carry-more-risk-than-customer-counts"></a>

Adobe Commerce B2B migration risk often sits above the individual customer account. A buyer may have a valid email address, billing address, shipping address, and order history, but that does not prove the buyer can act correctly after migration.

A company account can involve company administrators, company users, role-based purchasing permissions, company hierarchy, credit settings, quote permissions, purchase order rules, payment method availability, shipping method availability, customer group assignment, shared catalog access, and external business identifiers. If those relationships are missing or simplified, B2B buyers may see the wrong product set, lose negotiated pricing, fail checkout, bypass approval logic, or lose the purchasing authority they had in the source store.

The risk increases when the Source Platform represents B2B behavior through customer tags, account groups, wholesale apps, custom fields, dealer IDs, ERP accounts, sales-representative assignments, private price lists, hidden categories, or custom checkout logic. Those structures may not map directly to Adobe Commerce company accounts without additional planning.

B2B readiness should therefore be judged by relationship completeness, not only customer count. The migration plan should confirm which accounts are retail customers, which represent companies, which users administer company accounts, which users need purchasing authority, which accounts require shared catalog access, and which company-level rules must be active before launch.

### Shared Catalogs Create Visibility and Pricing Exposure <a href="#shared-catalogs-create-visibility-and-pricing-exposure" id="shared-catalogs-create-visibility-and-pricing-exposure"></a>

Shared catalogs can make Adobe Commerce migration more commercially sensitive than a standard product-and-price transfer. A product can exist in the Target Store but remain invisible to one buyer, visible to another, and priced differently for a third. That behavior is useful for B2B commerce, but it creates migration risk if visibility and pricing relationships are not defined.

The first risk is visibility exposure. A company may see products it should not see, fail to see contracted products, or lose access to a restricted assortment. The second risk is pricing exposure. A base price may be correct, but the commercially relevant price may depend on a shared catalog, customer group, company assignment, tier price, negotiated price, catalog price rule, or external pricing integration.

| Planning question                                                                           | Why it matters                                                                                            |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Which companies use public catalog access, shared catalog access, or both?                  | Buyer visibility depends on account context, not only product status.                                     |
| Which products belong to each shared catalog?                                               | Product migration alone does not prove buyer-specific assortment accuracy.                                |
| Which prices are base prices, customer group prices, tier prices, or shared catalog prices? | Pricing validation must test the buyer context that activates the price.                                  |
| Which company assignments are required at launch?                                           | B2B buyers may be blocked or mispriced if company-to-catalog relationships are incomplete.                |
| Which source rules are stored outside the standard commerce database?                       | ERP, PIM, pricing engine, or custom app logic may require Custom Service or implementation-side handling. |

A representative shared-catalog sample should test both allowed and restricted visibility. It is not enough to confirm that products and companies exist. The practical question is whether the right buyer sees the right product at the right price under the right storefront context.

### Storefront Scope Can Hide Data Problems <a href="#storefront-scope-can-hide-data-problems" id="storefront-scope-can-hide-data-problems"></a>

Adobe Commerce uses websites, stores, and store views to control business context, storefront behavior, language, content, catalog assignment, configuration, currency, and customer experience. This scope model is powerful, but it can also hide migration issues until storefront-level review.

A source store may represent multiple brands, regions, languages, wholesale portals, retail storefronts, or customer segments in a different way. Some source distinctions may become Adobe Commerce websites. Others may become stores, store views, categories, customer groups, shared catalogs, or configuration rules. If those decisions are made late, migrated records may land in the wrong scope or appear globally when they should be localized.

Scope problems are hard to catch through record counts. The Target Store can contain the expected number of products, categories, customers, and pages while showing the wrong language, wrong price, wrong content, wrong category tree, wrong customer access, or wrong URL structure in a specific storefront.

Scope planning should therefore be completed before detailed mapping. Representative Demo Migration and validation samples should include each important website, store, store view, language, region, brand, B2B segment, and storefront context that affects the launch outcome.

### Product Architecture Risk Increases With Catalog Complexity <a href="#product-architecture-risk-increases-with-catalog-complexity" id="product-architecture-risk-increases-with-catalog-complexity"></a>

Adobe Commerce product data can affect more than storefront display. Product types, child SKU relationships, attributes, attribute sets, category assignments, related products, search behavior, layered navigation, inventory, pricing rules, and integration identifiers can all influence how the Target Store operates.

A source platform may store variants, bundles, kits, product options, custom options, personalization choices, or configurable assemblies differently from Adobe Commerce. Treating those differences as simple field transfer can damage purchasability, merchandising, search, filtering, reporting, and maintenance.

| Product structure    | Risk if underplanned                                                                      | Prevention focus                                                                                                                    |
| -------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Product types        | Items appear but do not support the intended buying path.                                 | Decide whether source items should become simple, configurable, bundle, grouped, virtual, downloadable, or custom-handled products. |
| Child SKUs           | Variant options display incorrectly or cannot be purchased correctly.                     | Review SKU relationships, option labels, images, prices, stock, and parent-child assignment.                                        |
| Attributes           | Search, filters, comparison, rules, imports, or admin maintenance fail after launch.      | Separate display fields from operational attributes, integration fields, and rule inputs.                                           |
| Attribute sets       | Product families become hard to maintain or validate.                                     | Group product families by required fields and catalog governance needs.                                                             |
| Category assignments | Navigation, merchandising, and SEO continuity weaken.                                     | Validate category paths, storefront scope, visibility, and URL behavior.                                                            |
| Related products     | Upsells, cross-sells, accessories, replacements, or compatibility relationships are lost. | Include commercial relationship samples in migration review.                                                                        |

The safest plan does not preserve every source field exactly as it appeared. It preserves the business meaning of product data in a structure that Adobe Commerce can operate, maintain, validate, and scale.

### Content Staging and Campaign Timing Require Launch-Aware Review <a href="#content-staging-and-campaign-timing-require-launch-aware-review" id="content-staging-and-campaign-timing-require-launch-aware-review"></a>

Adobe Commerce projects may involve Content Staging, scheduled product updates, category changes, price changes, CMS Page changes, CMS block changes, promotional content, and campaign-specific storefront behavior. These items create risk when the source store contains time-sensitive content or when the merchant expects campaign timing to continue after migration.

A source page, banner, category description, product promotion, or landing page may support a seasonal campaign, a B2B announcement, a localized launch, or a scheduled pricing change. If migrated as static content, the content may exist but no longer follow the intended timing or business approval process.

Content and campaign planning should classify items into four groups:

| Content group                   | Recommended handling                                                       |
| ------------------------------- | -------------------------------------------------------------------------- |
| Evergreen content               | Migrate and validate as stable Target Store content.                       |
| Launch-critical content         | Prioritize in pre-launch validation and URL review.                        |
| Time-sensitive campaign content | Confirm whether timing must be recreated, configured, or manually rebuilt. |
| Legacy or expired content       | Exclude, archive, or deprioritize if it is not needed for launch.          |

The main risk is not only content loss. The risk is launching Adobe Commerce with outdated campaign content, missing scheduled changes, duplicated promotions, broken landing pages, or commercial messaging that no longer matches current pricing and inventory.

### Integration-Owned Data Can Be Invisible During Storefront Review <a href="#integration-owned-data-can-be-invisible-during-storefront-review" id="integration-owned-data-can-be-invisible-during-storefront-review"></a>

Adobe Commerce stores often connect with ERP, PIM, CRM, warehouse, tax, payment, shipping, marketplace, analytics, marketing automation, loyalty, subscription, search, or reporting systems. These systems may own identifiers and relationships that are not obvious in storefront review.

Examples include ERP customer IDs, company account IDs, contract numbers, dealer IDs, PIM product IDs, warehouse location codes, external order references, tax jurisdiction fields, CRM account references, subscription IDs, price-list references, marketplace item IDs, and fulfillment-system SKUs. If those identifiers are omitted or changed without planning, migrated data may look correct in Adobe Commerce but fail in downstream workflows.

Integration risk should be reviewed before deciding whether the migration can follow a standard scope. Unsupported external identifiers, custom data ownership, outside-system relationships, and bespoke transformation rules are often Custom Service signals. The decision should be made early enough to avoid late remapping after Demo Migration or Full Migration.

### Inventory and Fulfillment Constraints Depend on the Target Operating Model <a href="#inventory-and-fulfillment-constraints-depend-on-the-target-operating-model" id="inventory-and-fulfillment-constraints-depend-on-the-target-operating-model"></a>

Inventory migration can look simple when the source store has one stock quantity per product. Adobe Commerce may require a more detailed fulfillment model, especially when the business uses multiple warehouses, stores, pickup locations, sales channels, reservations, ERP-managed stock, supplier feeds, or fulfillment integrations.

The question is not only how much stock each SKU has. The better question is how Adobe Commerce should determine salability after launch. A quantity may be migrated, but that does not automatically define where the stock belongs, which website can sell it, how reservations should behave, whether backorders are allowed, or whether an external system will overwrite stock values after launch.

Inventory planning should identify whether the Target Store needs a simple launch baseline, a multi-source stock structure, or an integration-managed inventory model. That decision affects migration configuration, Demo Migration sample selection, validation priorities, and launch timing.

### URL and SEO Risk Is Higher When Scope and Content Are Complex <a href="#url-and-seo-risk-is-higher-when-scope-and-content-are-complex" id="url-and-seo-risk-is-higher-when-scope-and-content-are-complex"></a>

Adobe Commerce URL continuity can involve product URL keys, category URL keys, CMS Page paths, Blog Post paths, URL rewrites, redirect chains, canonical routes, localized routes, brand or regional paths, and custom landing pages. The risk is especially high when the source store has long-standing SEO value, B2B portals, multiple storefronts, campaign landing pages, or custom route logic.

A page can migrate successfully but still create SEO or customer-experience loss if the route changes without a redirect, if localized paths are flattened, if category/product URL behavior changes, or if high-value pages point to the wrong content. URL risk should be prioritized by business value, not by count.

High-priority URL review should include:

* top product pages by revenue, traffic, search visibility, or sales-team importance;
* top category pages and brand pages;
* key CMS Pages and landing pages;
* high-value Blog Posts when blog content is in scope;
* B2B account entry points, dealer portals, or private catalog access paths;
* discontinued but still-linked URLs that require redirects;
* localized or regional routes that must remain distinct.

URL planning belongs before go-live readiness review. Waiting until after launch can turn a migration issue into an SEO, paid-media, customer-support, or sales-continuity problem.

### Extension and Custom Logic Risk Should Be Classified Early <a href="#extension-and-custom-logic-risk-should-be-classified-early" id="extension-and-custom-logic-risk-should-be-classified-early"></a>

Adobe Commerce migrations often involve data or behavior controlled by extensions, custom modules, custom database tables, app-owned metadata, theme logic, custom checkout rules, account workflows, pricing engines, external systems, or implementation-specific business logic. These structures are not always visible in the standard entity list.

Unsupported extension-owned data should not be assumed to migrate through standard structures. Some items can be handled through Add-ons when the need is primarily filtering, mapping, or data configuration. Others require Custom Service when the project involves unsupported structures, custom logic, bespoke transformation, outside-system identifiers, Custom Platform behavior, or nonstandard target-side handling.

Early classification should separate:

| Item type                             | Typical handling direction                                                                                                |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Standard supported fields             | Standard Service may be enough when the field maps cleanly to supported target structures.                                |
| Filtering or controlled scope         | Data Filter Add-on may be relevant when only selected records should move.                                                |
| Field mapping or value transformation | Advanced Data Mapping or Advanced Data Configure may be relevant when supported structures need more controlled handling. |
| Unsupported extension data            | Custom Service review is usually needed when the source structure is outside standard supported entities.                 |
| Custom workflow or business logic     | Custom Service is usually required because logic must be analyzed, adapted, or rebuilt.                                   |
| External-system identifiers           | Custom Service may be required when identifiers must remain usable across ERP, CRM, PIM, warehouse, or reporting systems. |

Late discovery is the main risk. When extension-owned data is identified only after migration testing, the project may require scope change, remapping, Custom Service review, or target-side implementation work close to launch.

### Performance and Search Risks Should Be Treated as Launch Constraints <a href="#performance-and-search-risks-should-be-treated-as-launch-constraints" id="performance-and-search-risks-should-be-treated-as-launch-constraints"></a>

Adobe Commerce migrations can involve large catalogs, many attributes, complex filters, multiple store views, B2B catalog visibility, shared catalogs, custom search behavior, and integration-driven updates. These factors can affect performance, search relevance, admin usability, indexing behavior, and customer experience after launch.

Migration planning should not assume that transferred data will automatically perform well in the Target Store. Attribute choices, category depth, URL rewrites, shared catalog structure, customer group pricing, inventory updates, and integration feeds can all affect runtime behavior. Search and performance review should be included in launch-readiness planning when the source store has a large catalog, many buyer segments, high order volume, or complex storefront scope.

Performance risk is not only a technical implementation issue. It can become a migration risk when the imported data structure creates slow category pages, weak filtering, inconsistent search, duplicate content paths, excessive index load, or operational friction for catalog managers.

### Custom Service Escalation Signals <a href="#custom-service-escalation-signals" id="custom-service-escalation-signals"></a>

Adobe Commerce projects should be escalated for Custom Service review when the migration depends on structures or behavior that cannot be handled reliably as standard entity transfer or standard Add-on configuration.

Common escalation signals include:

| Signal                                                                                           | Why it matters                                                                                                     |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| B2B company hierarchy is stored through custom fields, apps, or external systems                 | Company accounts may need bespoke relationship handling.                                                           |
| Shared catalog or contract pricing is source-specific                                            | Buyer visibility and pricing may need custom analysis or transformation.                                           |
| Source storefront scope does not map cleanly to Adobe Commerce websites, stores, and store views | Scope flattening can damage language, brand, regional, or B2B behavior.                                            |
| Product architecture uses nonstandard variant, bundle, kit, or personalization logic             | Product records may need custom interpretation before they can behave correctly.                                   |
| Extension-owned data is business-critical                                                        | Unsupported fields or tables may need custom extraction, mapping, or import logic.                                 |
| External identifiers must remain stable                                                          | ERP, CRM, PIM, warehouse, marketplace, or reporting continuity may depend on identifiers outside standard records. |
| Content Staging or campaign timing is launch-critical                                            | Scheduled changes may need configuration or implementation planning outside ordinary content transfer.             |
| Validation requires business-rule testing rather than record-count confirmation                  | The migration scope depends on behavior, permissions, pricing, or integrations.                                    |

Escalation does not mean the project is unsuitable for Adobe Commerce. It means the migration path should match the business complexity of the target operating model.

### How Constraints Affect Service Path and Validation Planning <a href="#how-constraints-affect-service-path-and-validation-planning" id="how-constraints-affect-service-path-and-validation-planning"></a>

Adobe Commerce constraints should influence both service selection and validation depth. A project with clean products, simple customers, straightforward categories, and limited content may fit a more standard path. A project with governed B2B accounts, company-specific catalogs, staged content, scoped storefronts, custom pricing, and integration-owned identifiers needs deeper planning before migration results can be considered reliable.

Entity Points help plan counted data capacity, but they do not measure Adobe Commerce complexity. A smaller dataset with company-specific pricing, shared catalogs, and custom workflows may require more planning than a larger dataset with simple retail records. Add-ons may support filtering, mapping, or data configuration when the structures are supported. Custom Service becomes more relevant when the issue is unsupported data, custom logic, bespoke transformation, or outside-system continuity.

Validation planning should reflect the same risk pattern. Adobe Commerce validation should include representative business scenarios: company buyer access, shared catalog visibility, configured product selection, scoped storefront content, URL continuity, inventory salability, pricing context, order history usability, and integration-sensitive identifiers. Record counts are useful, but they cannot prove that the Target Store is ready for enterprise commerce operation.

### Common questions <a href="#common-questions" id="common-questions"></a>

**Does every Adobe Commerce migration require Custom Service?**

No. Adobe Commerce projects can follow a standard path when source data maps cleanly to supported structures and the target operating model is straightforward. Custom Service becomes more relevant when the migration depends on unsupported structures, custom logic, extension-owned data, outside-system identifiers, B2B relationship transformation, or bespoke pricing and catalog behavior.

**Are B2B company accounts the same as customer records?**

No. Individual customer records identify buyers, while company accounts can define business identity, users, administrators, permissions, shared catalog access, quote behavior, purchase order behavior, credit settings, and payment or shipping controls. B2B validation should confirm the relationship between buyers and companies, not only the existence of customer accounts.

**Can shared catalog issues be found by checking product counts?**

No. Product counts only confirm that products exist. Shared catalog validation must confirm whether the correct companies and buyer groups can see the correct products at the correct prices under the correct storefront context.

**Do Entity Points show how complex an Adobe Commerce migration is?**

No. Entity Points help plan counted data capacity. They do not measure B2B complexity, shared catalog logic, storefront scope, custom modules, integration dependencies, or validation difficulty.

**When should Adobe Commerce risks be reviewed?**

Risk review should happen before Full Migration planning is finalized. Late discovery of B2B, shared catalog, custom logic, integration, or scope issues can require remapping, service-scope changes, Custom Service review, or additional validation close to launch.
