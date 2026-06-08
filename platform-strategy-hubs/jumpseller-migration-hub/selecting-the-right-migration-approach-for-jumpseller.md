# Selecting the Right Migration Approach for Jumpseller

Choosing a migration approach for Jumpseller depends on how much of the source store can be translated into Jumpseller’s hosted e-commerce structure without custom interpretation. Jumpseller is designed around managed store infrastructure, native products, options, variants, categories, customers, orders, payments, shipping methods, themes, apps, sales channels, languages, redirects, and integrations. A migration approach should be selected by comparing the source store’s real operating model with what Jumpseller can represent cleanly.

A straightforward source store may need only standard product, customer, order, CMS Pages, and Blog Posts migration into a prepared Jumpseller store. A more complex store may depend on custom product fields, dense variants, B2B rules, warehouse logic, external identifiers, unsupported app data, checkout customizations, custom source exports, or integration-owned records. Those differences change the safest service path.

The right approach is not the one that moves the most records with the least review. It is the one that gives the migration enough interpretation, configuration, and validation for Jumpseller to become a usable Target Platform after the data is moved.

### What Migration Approach Means for Jumpseller <a href="#what-migration-approach-means-for-jumpseller" id="what-migration-approach-means-for-jumpseller"></a>

A Jumpseller migration approach should answer four questions before execution:

1. Can the source data fit Jumpseller’s native structures within standard service capability?
2. Does the customer want to self-perform the migration process or have Next-Cart handle execution?
3. Are filtering, mapping, or data-configuration adjustments needed through Add-ons?
4. Does the project include customization, unsupported data, Custom Platform handling, external-system logic, or custom migration logic adjustment that belongs under Custom Service?

These questions should be answered from platform behavior, not only from store size. A small store can need Custom Service if its catalog is built around custom product builders, unsupported subscription logic, external inventory identifiers, or unusual source exports. A large store can sometimes remain within Standard Service or Managed Service when its product, customer, order, CMS Pages, and Blog Posts structure is clean and target expectations are clear.

| Decision area                            | Why it matters for Jumpseller                                                                                                                    | Approach implication                                                                                        |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------- |
| Catalog structure                        | Jumpseller depends on products, options, variants, categories, custom fields, images, stock, and SEO fields behaving coherently                  | Clean structures may fit Standard Service; dense or custom variant logic may need Add-ons or Custom Service |
| Checkout and order meaning               | Payment status, fulfillment status, order fields, shipping method, invoicing, tax, and abandoned-order behavior may not match the source exactly | Standard migration may preserve readable history; custom checkout or order logic needs review               |
| Target configuration                     | Payment methods, shipping rates, tax setup, languages, currencies, apps, customer login, and stock locations are target-side conditions          | Managed Service can help execution, but unavailable target capabilities still need planning                 |
| Custom or unsupported source behavior    | Custom Platform sources, unsupported app data, external identifiers, source-specific logic, or unusual exports need interpretation               | Custom Service is the correct review path                                                                   |
| Filtering, mapping, or data modification | Some projects need only selected records, adjusted mappings, or edited target values                                                             | Standard Add-ons may be enough when the requirement fits their available behavior                           |

A good approach choice starts with scope clarity. The migration should not be treated as standard only because the platform is hosted, and it should not be treated as custom only because the store is large. The real question is whether Jumpseller can represent the migrated business meaning without custom logic.

### When Standard Service Is Usually Enough <a href="#when-standard-service-is-usually-enough" id="when-standard-service-is-usually-enough"></a>

Standard Service can be suitable when the source data is clean, the migration path is supported, the customer is comfortable self-performing the migration process on the Next-Cart website, and the target Jumpseller store has already been prepared for the expected result.

For Jumpseller, this usually means the store has a conventional catalog, predictable product variants, ordinary category assignments, readable customer records, standard historical order records, ordinary CMS Pages or Blog Posts, and no hidden dependency on custom apps, unsupported extensions, external systems, or custom source tables.

#### Strong Standard Service Signals <a href="#strong-standard-service-signals" id="strong-standard-service-signals"></a>

Standard Service is often reasonable when:

* products have clear names, descriptions, prices, SKUs, images, categories, and statuses;
* product options and variants follow a predictable structure;
* inventory belongs to products or variants without complex warehouse rules;
* category structure can be mapped without rebuilding the full storefront strategy;
* customers mainly need readable account and contact data;
* historical orders mainly need to remain understandable for staff reference;
* CMS Pages and Blog Posts can move without heavy layout reconstruction;
* the target Jumpseller store already has suitable payment, shipping, tax, language, and theme settings;
* no unsupported app, custom checkout, or external-system data is part of the expected migration scope.

Standard Service is not a low-review option. It still requires the customer to understand the source data, configure the target store where needed, run and interpret Demo Migration results, and validate the migrated output before launch.

#### Where Standard Service Can Become Too Light <a href="#where-standard-service-can-become-too-light" id="where-standard-service-can-become-too-light"></a>

Standard Service becomes too light when the migration depends on interpretation beyond standard service capability. Jumpseller’s hosted structure can make certain source behaviors easier to operate after migration, but it can also expose data that does not map cleanly.

Examples include source stores where product options are used as filters, pricing rules, personalization fields, bundles, subscriptions, or custom forms rather than ordinary sellable variants. Another example is a source store where customer groups control B2B prices, payment access, tax behavior, or shipping eligibility. Moving labels alone will not preserve those rules unless the target structure can support them and the migration scope accounts for them.

Standard Service should also be reconsidered when source order data includes custom fulfillment states, external invoices, marketplace identifiers, custom payment references, or app-owned order fields that staff need after migration.

### When Managed Service Is the Safer Choice <a href="#when-managed-service-is-the-safer-choice" id="when-managed-service-is-the-safer-choice"></a>

Managed Service is suitable when the migration can remain within standard service capability but the customer wants Next-Cart-led execution. This can be useful for merchants moving into Jumpseller who prefer support with migration execution, setup review, Demo Migration interpretation, and coordination around the selected migration path.

Managed Service does not remove the need for target-store preparation. Jumpseller still needs the right target settings for product visibility, payment methods, shipping rules, tax behavior, languages, currencies, customer login expectations, apps, theme behavior, and redirects. Managed Service helps with execution responsibility; it does not turn unsupported or custom source logic into standard capability.

| Managed Service is useful when                                             | Why it helps                                                            | Boundary to remember                                                      |
| -------------------------------------------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| The source data is standard but the customer wants Next-Cart-led execution | Reduces execution burden and gives the customer a clearer review role   | It remains within standard service capability unless custom work is added |
| The catalog has many records but predictable structure                     | Execution support can help coordinate a larger run                      | Record volume alone does not decide whether Custom Service is needed      |
| The customer needs help interpreting Demo Migration output                 | Next-Cart-led execution can make review and adjustment more structured  | The customer still needs to confirm business meaning and launch readiness |
| Standard Add-ons are purchased                                             | Managed Service can include purchased Standard Add-ons during execution | Modified Add-ons or custom behavior move into Custom Service              |

Managed Service is often a practical fit for merchants who want Jumpseller’s hosted environment but do not want to manage the migration run themselves. It is especially useful when the main concern is execution responsibility, not custom interpretation.

### When Custom Service Should Be Used <a href="#when-custom-service-should-be-used" id="when-custom-service-should-be-used"></a>

Custom Service is the correct path when the migration requires customization, modification, bespoke handling, Custom Platform work, unsupported data, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment. For Jumpseller, Custom Service is especially relevant when the source store depends on behavior that Jumpseller does not natively represent in the same way.

This does not automatically mean Next-Cart performs the migration process. Custom Service defines the customization or modification path. Migration management is included only when it is part of the final plan.

#### Jumpseller-Specific Custom Service Signals <a href="#jumpseller-specific-custom-service-signals" id="jumpseller-specific-custom-service-signals"></a>

Custom Service should be reviewed when the project includes:

* Custom Platform as the Source Platform or Target Platform;
* source data from unsupported apps, plugins, modules, custom components, or external systems;
* custom product builders, bundles, kits, personalization fields, subscription logic, appointment logic, or complex service products;
* variant structures that cannot be represented cleanly as ordinary Jumpseller options and variants;
* product custom fields that affect purchase behavior, filtering, shipping, tax, or staff workflow;
* external identifiers that must remain connected to ERP, accounting, invoicing, marketplace, fulfillment, or CRM systems;
* customer groups that control pricing, payment access, tax treatment, or shipping eligibility;
* custom checkout fields or order metadata that staff must continue using;
* source order statuses that need special transformation into Jumpseller’s order, payment, fulfillment, or invoicing context;
* multi-location stock, warehouse logic, reservations, supplier feeds, or external inventory systems;
* multilingual content that needs custom mapping across products, categories, pages, navigation, and SEO fields;
* source URLs or landing pages requiring complex redirect and destination planning;
* API, webhook, feed, or sales-channel data that must remain usable after migration.

Custom Service is not a penalty for complexity. It is the review path for requirements that need controlled interpretation instead of default assumptions.

#### Custom Platform and Unsupported Source Data <a href="#custom-platform-and-unsupported-source-data" id="custom-platform-and-unsupported-source-data"></a>

Any migration involving Custom Platform requires Custom Service. In a Jumpseller migration, this matters when the source system is not one of the supported Source Platforms or when the source store contains custom-built structures that behave like a separate data model. Custom Platform handling can include custom source exports, custom fields, outside-system identifiers, app-owned records, or custom transformation rules.

Unsupported app or integration data should be handled with the same caution. If a source store relies on external systems for product feeds, stock updates, invoicing, shipping labels, marketplace orders, customer segmentation, or subscriptions, those records should not be assumed to become native Jumpseller data automatically. They need a defined target meaning, a migration scope decision, and validation evidence.

### How Add-ons Fit into a Jumpseller Migration <a href="#how-add-ons-fit-into-a-jumpseller-migration" id="how-add-ons-fit-into-a-jumpseller-migration"></a>

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. They should be considered when the migration requirement fits Add-on capability and does not require broader custom handling.

For Jumpseller, Add-ons are often useful when the source data is structurally compatible but the customer wants more control over what moves, how source values map into target fields, or how selected values are configured during migration.

| Add-on type             | Jumpseller use case                                                                                                                      | Boundary                                                                                  |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Move only selected records, such as active products, recent orders, specific categories, selected customer groups, or relevant CMS Pages | Filtering does not solve unsupported source behavior or custom target logic               |
| Advanced Data Mapping   | Map source fields, statuses, categories, customer labels, or product values more deliberately into Jumpseller-supported structures       | Mapping must remain within platform data-model support and capability                     |
| Advanced Data Configure | Adjust selected migrated values so the target data reaches Jumpseller with updated information                                           | Data configuration is not the same as bespoke transformation or unsupported app migration |

A Standard Add-on is enough only when the requirement fits its available settings and supported behavior. If a Standard Add-on must be modified, the tailored work is handled through Custom Service. If the customer needs a new project-specific Add-on, that Custom Add-on request is also reviewed and quoted through Custom Service.

Add-ons are useful, but they are not the whole Custom Service path. Broader requirements such as Custom Platform handling, third-party app data, custom fields that carry business logic, outside-system identifiers, or bespoke transformation should be reviewed as Custom Service requirements.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should test whether the selected approach is realistic before the full migration is treated as ready. For Jumpseller, the Demo Migration should not use only clean products and ordinary orders. It should include samples that expose the source store’s real complexity.

| Sample area                    | What to include                                                                                              | What the result should prove                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| Simple product                 | A normal product with images, category, price, stock, SEO fields, and status                                 | Ordinary catalog records are readable and usable in Jumpseller                       |
| Variant product                | A product where options affect SKU, price, image, weight, stock, or availability                             | Sellable product choices remain operational, not flattened into text                 |
| Complex product                | A product with custom fields, personalization needs, downloads, bundles, or source-specific logic            | The approach can handle the difficult product group or identify Custom Service needs |
| Category and navigation sample | Important categories, nested categories, and high-value landing pages                                        | Product organization and storefront discovery expectations are realistic             |
| Customer sample                | Customers with addresses, language, marketing consent, tax identifiers, customer categories, or group labels | Customer records are usable and do not imply unsupported account logic               |
| Order sample                   | Paid, unpaid, fulfilled, partially fulfilled, refunded, abandoned, or custom-status orders                   | Historical order meaning remains understandable inside Jumpseller                    |
| Content and SEO sample         | CMS Pages, Blog Posts, metadata, permalinks, and redirect-sensitive URLs                                     | Content and URL continuity can be validated instead of assumed                       |
| Integration sample             | Records linked to ERP, fulfillment, invoicing, marketplace, or API workflows                                 | App-owned or external-system dependencies are visible before full migration          |

A Demo Migration result should lead to one of three outcomes: confirm that the selected approach is suitable, identify Add-ons needed for filtering/mapping/configuration, or show that Custom Service review is required.

### Signals That the Chosen Approach Is Too Light <a href="#signals-that-the-chosen-approach-is-too-light" id="signals-that-the-chosen-approach-is-too-light"></a>

A migration approach is too light when it depends on assumptions that the Demo Migration or preparation evidence does not support. The warning signs often appear before a full migration if the review samples are chosen well.

| Warning sign                                                            | What it usually means                                                                            | Safer next action                                                              |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Product variants lose SKU, stock, image, price, or availability meaning | Source product logic does not fit cleanly into standard option/variant handling                  | Review mapping, Add-ons, or Custom Service depending on the cause              |
| Categories move but navigation feels wrong                              | Source categories were also used as menus, SEO landing pages, campaigns, or filters              | Separate category migration from navigation and theme planning                 |
| Customer groups move only as labels                                     | Source groups carried pricing, tax, payment, shipping, or access rules                           | Review target capability and Custom Service needs if logic must be transformed |
| Historical orders are present but hard to interpret                     | Source statuses, payment data, fulfillment states, or custom fields need meaning translation     | Expand order samples and review whether mapping or custom handling is needed   |
| Required checkout fields are missing                                    | Source checkout captured data that Jumpseller does not represent the same way                    | Review target configuration, app options, or Custom Service                    |
| Stock does not match operating needs                                    | Source inventory depends on warehouses, reservations, external feeds, or supplier logic          | Review stock-location limits and integration strategy before full migration    |
| Multilingual content is incomplete                                      | Source translations are not mapped across products, categories, pages, navigation, or SEO fields | Expand multilingual validation and confirm target language setup               |
| URL redirects are unclear                                               | Important source URLs were not identified or target destinations are weak                        | Prioritize high-value URLs and validate destination quality                    |
| App data is expected but not native                                     | Source behavior is owned by apps, integrations, APIs, or external systems                        | Review Custom Service or post-migration integration planning                   |

If several warning signs appear together, the issue is rarely only a settings problem. It usually means the selected approach does not match the source store’s real structure or the target store’s operational expectations.

### Choosing the Safest Approach <a href="#choosing-the-safest-approach" id="choosing-the-safest-approach"></a>

The safest Jumpseller migration approach should be selected from the evidence gathered before and during Demo Migration. The following decision path can help keep the choice practical without turning it into a generic service comparison.

| Project profile                                                                                                                                     | Likely approach                                                        | Why                                                                                                          |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Clean supported source data, conventional products, ordinary categories, standard customer/order history, and prepared target settings              | Standard Service                                                       | Customer-led execution can be enough when the target result is predictable and no custom logic is required   |
| Clean supported source data, larger record volume, or customer preference for Next-Cart-led execution                                               | Managed Service                                                        | Execution responsibility shifts to Next-Cart while the migration stays within standard service capability    |
| Standard data with selective scope, special mapping, or value adjustment needs                                                                      | Standard Service or Managed Service with Add-ons                       | Add-ons can support filtering, mapping, or configuration when the requirement fits available behavior        |
| Standard Add-on needs modification beyond available settings                                                                                        | Custom Service                                                         | Tailored Add-ons are handled through Custom Service because customization is required                        |
| Custom Platform source, unsupported app data, custom product logic, external identifiers, unusual stock/order structures, or bespoke transformation | Custom Service                                                         | The migration requires custom interpretation, custom migration logic adjustment, or broader bespoke handling |
| Custom requirements plus customer preference for Next-Cart-led execution                                                                            | Custom Service with migration management if included in the final plan | Custom Service defines the custom work; migration management must be part of the agreed scope                |

The approach should remain flexible until difficult samples have been reviewed. A project may begin as a standard-looking migration and move into Add-on or Custom Service review after Demo Migration reveals hidden complexity. That adjustment is healthier than forcing a light approach to carry requirements it was not designed to handle.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting the right migration approach for Jumpseller depends on how clearly the source store’s business meaning can be represented inside a hosted SaaS Target Platform. Standard Service can fit clean, predictable migrations where the customer is ready to self-perform the migration process. Managed Service can fit standard migrations where Next-Cart-led execution is preferred. Add-ons can support filtering, mapping, and configuration needs when they remain within available capability. Custom Service is the right path when the project includes Custom Platform handling, unsupported data, custom fields, external identifiers, tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

Before choosing the final approach, prepare representative samples and use Demo Migration to test the difficult parts of the source store, not only the easy records. If product variants, categories, checkout data, customer groups, order history, multilingual content, redirects, or app-connected records do not behave as expected, use the findings to adjust the service path before committing to the full migration scope.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for a Jumpseller migration?**

Standard Service can be enough when the source data is clean, the migration path is supported, the customer is ready to self-perform the migration process, and Jumpseller can represent the expected product, customer, order, CMS Pages, and Blog Posts structure without custom handling. Demo Migration should confirm this before the full migration is treated as ready.

**When should Managed Service be chosen instead of Standard Service?**

Managed Service is useful when the migration can remain within standard service capability but the customer wants Next-Cart-led execution. It is often a practical choice for merchants who want help managing the migration run and reviewing results, while still using standard Jumpseller-supported data structures.

**What makes a Jumpseller migration a Custom Service case?**

Custom Service is appropriate when the project requires customization or modification work. Examples include Custom Platform handling, unsupported app data, custom product logic, external identifiers, unusual stock or order structures, tailored transformation, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

**Are Add-ons the same as Custom Service?**

No. Add-ons are optional service features for filtering, mapping, or data configuration. Custom Service is broader and covers customization, modification, Custom Platform handling, unsupported data, Tailored Add-ons, Custom Add-ons, and bespoke migration requirements.

**Can a Jumpseller migration start as Standard Service and later move into Custom Service?**

Yes. If preparation or Demo Migration shows that the source data requires customized handling, the service path should be adjusted. This is common when difficult products, custom fields, external identifiers, app-owned records, or unusual order and stock logic appear during review.

**Does Custom Service automatically mean Next-Cart performs the migration for me?**

No. Custom Service defines the customization or modification path. Migration management is included only when it is part of the final plan. A customer may still self-perform the migration process unless migration management is added.
