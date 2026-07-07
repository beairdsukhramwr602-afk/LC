# Selecting the Right Migration Approach for Wix

The right Wix migration approach depends on what the merchant expects the future Wix site to operate, not only on how many records need to move. A small product catalog can require deeper planning if it depends on product options, variant-specific inventory, CMS data, memberships, custom forms, external systems, Velo/API logic, or app-owned records. A larger catalog can still follow a straightforward path when the data is supported, the structure is clear, and the merchant can validate the target result with confidence.

For Wix, service-path selection should separate migrated records from Wix setup and site implementation. Products, customers, orders, CMS Pages, Blog Posts, media, and supported metadata may be migration scope. Checkout settings, payment providers, shipping, taxes, domain connection, site design, app configuration, member access, CMS permissions, custom code, and external integrations may require target-side work, Add-ons, Custom Service, or manual implementation. The best approach is the lightest path that protects the intended Wix operating outcome.

### What Migration Approach Means for Wix <a href="#what-migration-approach-means-for-wix" id="what-migration-approach-means-for-wix"></a>

A Wix migration approach defines scope, execution responsibility, support level, special handling, and validation depth. It should answer which records are expected to migrate, which Wix settings must be configured separately, which special requirements need Add-ons, and which unsupported or custom requirements require Custom Service review.

The approach should be chosen from evidence, not from platform assumptions. Wix is hosted and user-friendly, but that does not make every migration simple. A content-heavy site, variant-rich store, member-based business, custom-coded workflow, or app-driven catalog may require more careful service planning than a conventional product/customer/order transfer.

| Workstream                 | Wix example                                                                                                            | Service-path implication                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Supported migrated data    | Products, collections, customers, orders, CMS Pages, Blog Posts, images, and supported metadata.                       | May fit Standard Service or Managed Service depending on complexity and execution support needs. |
| Supported data adjustments | Filtering old records, mapping supported fields, or configuring supported output.                                      | May fit Add-ons when requirements stay within supported behavior.                                |
| Custom or unsupported data | App-owned records, custom fields, external IDs, Velo/API logic, CMS collection complexity, or bespoke transformations. | Requires Custom Service review.                                                                  |
| Wix target setup           | Payments, checkout, shipping, tax, pickup, delivery, discounts, app setup, domain, site design, and member settings.   | Must be configured and tested in Wix, not assumed from migration output.                         |

This distinction prevents two common errors. The first is under-scoping Wix because it is a hosted platform. The second is over-escalating every Wix site-builder or app requirement into Custom Service when the real need is target setup, supported mapping, or a bounded Add-on.

### When Standard Service May Be Enough <a href="#when-standard-service-may-be-enough" id="when-standard-service-may-be-enough"></a>

Standard Service may be suitable when the merchant needs supported Wix data migration with ordinary structure and can manage the preparation, execution, and validation responsibilities. It works best when products are straightforward, collections are not heavily dependent on custom navigation logic, customers and orders are standard, content is limited or supported, and Wix site setup can be handled by the merchant or the site team.

Standard Service can still produce a strong Wix result when expectations are realistic. The merchant should understand that migration can transfer supported records, while site design, live checkout behavior, domains, payment setup, shipping rules, tax configuration, member access, and app setup must be handled in Wix.

| Standard Service signal                                                | Wix-specific reason                                                                   |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Products have simple options or clear variant structures.              | Supported catalog records can be reviewed without bespoke transformation.             |
| Collections are straightforward product groupings.                     | Product discovery does not depend on complex category-to-page reconstruction.         |
| Inventory is product-level or clear variant-level stock.               | The merchant can validate stock meaning without external-system complexity.           |
| Customers and orders are mainly needed for lookup and service history. | Historical records do not require advanced account, member, loyalty, or app behavior. |
| CMS Pages and Blog Posts are limited or easy to review.                | Content migration does not dominate launch risk.                                      |
| Site design and checkout setup are handled directly in Wix.            | The migration scope stays separate from target implementation.                        |

Standard Service becomes weaker when the merchant cannot provide clear samples, does not know which Wix features will own post-launch behavior, or expects custom source functionality to transfer automatically.

### When Managed Service May Be Safer <a href="#when-managed-service-may-be-safer" id="when-managed-service-may-be-safer"></a>

Managed Service may be safer when the data is largely supported but the execution path needs stronger coordination. Wix migrations can involve many review points: catalog samples, variant behavior, inventory, customers, orders, content, URLs, redirects, app dependencies, target setup, and launch timing. Even when no custom transformation is required, a merchant may need help coordinating the migration steps and reviewing results.

Managed Service is especially useful when the merchant wants Next-Cart-led execution support while retaining responsibility for final verification and Wix setup decisions. It can reduce operational pressure, but it does not turn unsupported records into supported records and does not replace the need to configure Wix itself.

| Managed Service fit                    | Wix scenario                                                                                                  |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Supported scope with many review areas | Products, collections, customers, orders, CMS Pages, Blog Posts, URLs, and images all need structured review. |
| Launch timing is sensitive             | The source store remains active while the Wix site is being prepared.                                         |
| Content and SEO matter                 | URLs, redirects, landing pages, Blog Posts, CMS Pages, and internal links need careful sequencing.            |
| Internal bandwidth is limited          | The merchant cannot confidently manage every migration step and review task alone.                            |
| Demo Migration must drive decisions    | Samples need coordinated interpretation before Full Migration.                                                |

Managed Service should be selected for coordination and execution confidence. When the underlying requirement is app-owned records, custom fields, Velo/API logic, external identifiers, or unsupported source behavior, Custom Service may still be needed.

### When Add-ons Are the Right Fit <a href="#when-add-ons-are-the-right-fit" id="when-add-ons-are-the-right-fit"></a>

Add-ons are useful when the merchant needs bounded changes within supported migration behavior. They help refine what is migrated, how supported fields are aligned, or how supported output is configured. They should not be used as a substitute for unsupported data migration or custom business-logic recreation.

For Wix, Add-ons are most useful when the merchant has clear, supported requirements such as excluding obsolete records, narrowing historical orders, mapping supported product fields, organizing supported content output, or configuring supported target data for easier Wix review.

| Add-on need             | Wix example                                                                                              | Boundary check                                                                                 |
| ----------------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Exclude archived products, old orders, inactive customers, unused Blog Posts, or low-value content.      | Filtering should not remove records needed for support, SEO, or launch verification.           |
| Advanced Data Mapping   | Map supported source fields to suitable Wix product, customer, order, content, or metadata destinations. | Mapping cannot create unsupported Wix behavior or custom app logic.                            |
| Advanced Data Configure | Adjust supported data handling so Wix records are easier to review and use.                              | Configuration must remain bounded and supported.                                               |
| Custom Add-ons          | Handle a narrow supported requirement that has a clear output expectation.                               | Unsupported fields, app data, or bespoke transformations should move to Custom Service review. |

The best Add-on request is specific. A vague request such as “make Wix match the old store” is not enough. A useful request states which supported records, fields, filters, or output behavior should change and how the result will be validated in Wix.

### When Custom Service Should Be Considered <a href="#when-custom-service-should-be-considered" id="when-custom-service-should-be-considered"></a>

Custom Service should be considered when the Wix migration requirement goes beyond supported migration behavior. The trigger is not only store size. The trigger is a need for custom evaluation, unsupported records, app-owned data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, Velo/API logic, or custom migration logic adjustment.

Wix custom requirements often appear when the source store has behavior that is not stored as ordinary commerce data. Examples include product configurators, subscription or membership logic, booking or event history, custom customer fields, CRM or loyalty IDs, external inventory references, marketplace records, CMS collections, dynamic pages, custom database structures, Velo-like code, or private integrations.

| Custom Service trigger                                                        | Wix-specific implication                                                             |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| App-owned product, customer, order, or content records                        | Standard migration may not include the app’s data or behavior.                       |
| Custom fields or external identifiers                                         | The fields may need bespoke mapping or transformation to remain useful.              |
| Velo/API or source-code-dependent behavior                                    | The requirement may need custom logic review or target-side implementation planning. |
| Complex CMS collections or external databases                                 | Content and data relationships may not fit ordinary CMS Page or Blog Post migration. |
| Product configurators, forms, memberships, bookings, or pricing-plan behavior | The selling model may belong to Wix apps, target setup, or custom handling.          |
| Non-standard checkout, shipping, tax, fulfillment, or payment logic           | Live behavior may need Wix setup, service-plugin planning, or accepted redesign.     |

Custom Service should be scoped through representative examples. The merchant should provide sample records, source screenshots or exports where appropriate, target expectations, and validation rules. Without examples, custom review becomes too abstract to protect the Wix outcome.

### What Demo Migration Should Decide <a href="#what-demo-migration-should-decide" id="what-demo-migration-should-decide"></a>

Demo Migration should test whether the selected approach can preserve Wix-specific meaning. It should not be treated only as a preview of record counts. For Wix, Demo Migration should answer whether products, collections, variants, inventory, customers, orders, content, URLs, and special handling requirements are moving through the right path.

A strong Wix Demo Migration sample set should include ordinary and difficult examples. The goal is to prove the approach, not to approve the easiest records.

| Sample area                                 | Decision it should support                                                                |
| ------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Simple product                              | Whether baseline Wix catalog transfer is clean.                                           |
| Option/variant product                      | Whether choices, variant SKUs, prices, weights, images, and inventory behave as expected. |
| Collection/category sample                  | Whether source discovery meaning can become Wix collections, pages, menus, or redirects.  |
| Customer with orders                        | Whether buyer identity and historical order context remain useful.                        |
| Guest buyer or duplicate profile            | Whether identity assumptions need cleanup or acceptance rules.                            |
| Refunded or discounted order                | Whether historical order exceptions remain readable.                                      |
| CMS Page, Blog Post, or media-heavy content | Whether content migration, rebuild, or redirect decisions are clear.                      |
| App/custom/external record                  | Whether the requirement belongs to Add-ons, Custom Service, target setup, or exclusion.   |

If Demo Migration shows that important Wix records lose meaning, the approach should be adjusted before Full Migration. The response should not be to continue with a weak path and expect the full data set to solve structural problems.

### Entity Points and Wix Scope Planning <a href="#entity-points-and-wix-scope-planning" id="entity-points-and-wix-scope-planning"></a>

Entity Points help estimate eligible migration volume, but they do not measure Wix complexity by themselves. Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

For Wix, Entity Points should be considered alongside data meaning. A small Wix migration may require Custom Service if it includes app-owned data, CMS collections, custom fields, external identifiers, or Velo/API-dependent behavior. A larger migration may remain suitable for Standard Service or Managed Service if supported records are clear and the merchant can validate the result.

| Scope signal     | What it helps estimate                           | What it does not prove                                                                        |
| ---------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| Product count    | Catalog volume and possible Entity Points usage. | Whether options, choices, variants, images, collections, and inventory are usable in Wix.     |
| Customer count   | Buyer-record volume.                             | Whether contacts, members, subscribers, app participants, and external IDs remain meaningful. |
| Order count      | Historical order volume.                         | Whether payment, refund, fulfillment, discount, and external-reference context is readable.   |
| Blog Posts count | Content volume when relevant.                    | Whether CMS Pages, URLs, redirects, media, and site structure are launch-ready.               |

Entity Points should support planning, not replace service-path evaluation. The chosen approach still depends on supported behavior, target setup, custom requirements, execution responsibility, and validation evidence.

### Additional Migration Options and Wix Launch Timing <a href="#additional-migration-options-and-wix-launch-timing" id="additional-migration-options-and-wix-launch-timing"></a>

Additional Migration Options become relevant when source data continues changing while the Wix site is being prepared. New products, customers, orders, Blog Posts, or content updates may appear after an initial migration run. Mapping or filtering decisions may also change after Demo Migration.

The merchant may need to continue the migration with the last used configuration, continue with a new configuration, or perform a new migration when the target result should be replaced. The choice should be tied to the intended Wix outcome.

| Situation                                                           | Likely action logic                        | Validation emphasis                                                                                  |
| ------------------------------------------------------------------- | ------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| New source records were added and configuration remains acceptable. | Continue with the last used configuration. | Check newly migrated records and regression samples.                                                 |
| Field mapping, filters, or supported configuration changed.         | Continue with a new configuration.         | Check affected fields, record groups, and samples.                                                   |
| The previous Wix target result should be replaced.                  | Perform a new migration.                   | Validate the refreshed target result and confirm outdated migrated data is no longer relied on.      |
| The Wix site launch is delayed while source sales continue.         | Plan continuation timing before launch.    | Confirm new orders, customers, products, and content updates are included or intentionally excluded. |

Additional Migration Options should not be presented as a broad workaround for poor preparation. They are useful when the migration timing and target-result expectation are clear.

### Signals That the Chosen Wix Approach Is Too Light <a href="#signals-that-the-chosen-wix-approach-is-too-light" id="signals-that-the-chosen-wix-approach-is-too-light"></a>

The chosen approach is too light when it treats Wix as a simple import destination while ignoring site-commerce complexity. The warning signs usually appear in sample review, not in record counts.

| Warning signal                                                                                    | Likely response                                                                            |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Product options, choices, variants, and inventory cannot be validated confidently.                | Rework catalog scope or consider stronger execution/custom review.                         |
| Source categories are expected to recreate menus, pages, filters, and SEO paths automatically.    | Separate collection migration from site structure and redirect planning.                   |
| Customer records include members, contacts, subscribers, loyalty, bookings, or app participation. | Classify identity types and review supported versus custom paths.                          |
| Historical orders are expected to configure live Wix checkout.                                    | Separate migrated history from payment, shipping, tax, and order-setting setup.            |
| CMS Pages, Blog Posts, dynamic pages, or custom data collections are central to launch.           | Plan content migration, rebuild, redirects, CMS setup, or Custom Service review.           |
| App-owned fields, Velo/API logic, or external IDs are business-critical.                          | Do not rely on generic migration scope; evaluate Add-ons or Custom Service as appropriate. |
| The merchant cannot define who will validate Wix setup and migration output.                      | Managed Service may help coordination, but acceptance criteria must still be defined.      |

These signals should be addressed before Full Migration because they usually become harder to resolve when launch deadlines are close.

### Choosing the Practical Wix Path <a href="#choosing-the-practical-wix-path" id="choosing-the-practical-wix-path"></a>

The practical Wix path is the lightest service path that can still protect the future site-commerce result. Standard Service may be enough for supported, straightforward data when the merchant can manage target setup and validation. Managed Service is safer when the data is supported but execution and review coordination matter. Add-ons help with supported filtering, mapping, or configuration. Custom Service is required when custom, unsupported, app-owned, external-system, or bespoke transformation needs affect the migration result.

A ready approach can be summarized with four statements:

* which Wix records should migrate;
* which Wix settings and site elements must be configured or rebuilt separately;
* which Add-ons or Custom Service requirements are in scope;
* which Demo Migration samples must pass before Full Migration.

If those statements are not clear, the service path should not be treated as finalized. Wix migration quality depends on matching the chosen approach to the actual site-commerce environment the merchant wants to operate after launch.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Selecting the right Wix migration approach requires more than estimating record volume. The approach must account for Wix Stores catalog structure, options, choices, variants, inventory, customers, contacts, members, orders, CMS Pages, Blog Posts, URLs, apps, Velo/API logic, external systems, target-side setup, Entity Points, Additional Migration Options, and validation responsibility.

The right path is not always the most complex one. It is the path that separates supported migration scope from Wix setup, identifies where Add-ons are enough, escalates true custom requirements to Custom Service review, and uses Demo Migration to prove that the Wix target result will support real selling, site experience, and operational review.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**When is Standard Service enough for a Wix migration?**

Standard Service may be enough when the merchant needs supported Wix records with ordinary structure, can manage Wix setup directly, and can validate products, collections, customers, orders, content, and URLs without extensive coordination or custom handling.

**When should Managed Service be considered for Wix?**

Managed Service is useful when the migration remains within supported capability but the merchant needs stronger execution support, coordination, sample review, launch-window planning, or help managing migration steps before Full Migration.

**How are Add-ons different from Custom Service for Wix?**

Add-ons support bounded filtering, mapping, or configuration within supported migration behavior. Custom Service is for unsupported app data, custom fields, external identifiers, Velo/API logic, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

**Do Entity Points decide whether a Wix migration is complex?**

No. Entity Points help estimate eligible migration volume, but Wix complexity depends on data meaning, site setup, custom behavior, app ownership, content structure, external references, and validation burden.

**What should Demo Migration prove before Full Migration?**

Demo Migration should prove that representative Wix records behave as expected: products, variants, collections, inventory, customers, orders, CMS Pages, Blog Posts, URLs, and any app/custom samples that affect the selected service path.
