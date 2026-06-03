# J2Commerce 6 Migration Pitfalls and Prevention

J2Commerce 6 migrations can produce strong results when the project is planned around the platform’s actual operating model: native Joomla 6 architecture, PHP 8.3+ requirements, modern frontend rendering, rebuilt plugin behavior, REST/API capability, and a deliberate migration path from J2Store v4 where relevant.

The most damaging mistakes usually happen when the project is treated as a simple record transfer. Products, orders, customers, coupons, shipping methods, payment methods, tax data, storefront layouts, and integrations may all appear familiar, but J2Commerce 6 does not behave like a lightly renamed J2Store v4 installation. It has a different foundation, different extension expectations, and different validation requirements.

The recurring failure patterns below should be prevented before Full Migration or launch. Each pitfall explains what goes wrong, how to detect it early, how to prevent it, what a practical recommendation looks like, and what must be true before the issue can be considered resolved.

### Pitfall 1: Treating J2Commerce 6 as a Minor J2Store Version Change <a href="#pitfall-1-treating-j2commerce-6-as-a-minor-j2store-version-change" id="pitfall-1-treating-j2commerce-6-as-a-minor-j2store-version-change"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

A merchant assumes that moving into J2Commerce 6 is mostly a version update from J2Store v4. The migration is planned around familiar entity names such as products, orders, customers, coupons, tax profiles, shipping methods, and payment methods, but the project does not account for the architectural shift into native Joomla 6 MVC, PHP 8.3+, vanilla JavaScript, Bootstrap 5, or UIkit 3 frontend rendering, new event behavior, and separate J2Commerce 6 plugin expectations.

The result may look organized at first because many familiar records can be accounted for. The problem appears later when old assumptions about plugins, templates, checkout behavior, layout overrides, JavaScript dependencies, or source-specific customization no longer match the target platform.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

The project plan uses J2Store v4 and J2Commerce 6 as if they are interchangeable. The team expects old J2Store payment or shipping plugins to continue working without a replacement review. Joomla 6, PHP 8.3+, frontend framework selection, and replacement plugin availability are not included in the migration checklist. Demo Migration review focuses on product and order counts but does not examine whether the migrated result behaves correctly in the J2Commerce 6 environment.

#### Prevention <a href="#prevention" id="prevention"></a>

Confirm the target generation before migration planning begins. J2Commerce 6 should be treated as a modern Joomla 6-native Target Platform with its own implementation requirements. If the source is J2Store v4, review what the v4 migrator can copy, what it can trace through idmap records, what needs dry-run review, and what must be reconfigured or replaced in J2Commerce 6.

This distinction should be visible in the preparation plan, service approach, Demo Migration samples, and validation checklist. It should not dominate every article or become a version-history discussion, but it must be clear enough to prevent wrong expectations.

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

Before Demo Migration, identify the source generation, target generation, Joomla version, PHP version, active payment plugins, active shipping plugins, frontend template framework, custom overrides, and any extension-owned data. If the source is J2Store v4, add a specific review step for migrator output, dry-run findings, idmap traceability, and replacement plugin planning.

#### Pass Condition <a href="#pass-condition" id="pass-condition"></a>

The project team can clearly explain whether the migration targets J2Commerce 6, which source generation is being migrated, which legacy assumptions do not carry forward, and which platform behaviors must be validated after migration.

### Pitfall 2: Skipping Joomla 6 and Hosting Readiness Review <a href="#pitfall-2-skipping-joomla-6-and-hosting-readiness-review" id="pitfall-2-skipping-joomla-6-and-hosting-readiness-review"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

The migration is scoped as a commerce-data project while the Joomla 6 environment is treated as an implementation detail. The merchant prepares product, customer, and order data but does not confirm Joomla 6 readiness, PHP 8.3+ compatibility, database requirements, template compatibility, server configuration, or extension compatibility.

This creates a launch risk because J2Commerce 6 is not only a destination for records. It depends on a modern Joomla 6 operating environment. If the target site is not technically ready, migrated records may exist, but the store may not render, process checkout, run scheduled tasks, support integrations, or remain stable under real usage.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

The target site has not been prepared before migration testing. Joomla and PHP versions are not confirmed. The target template is not reviewed against Bootstrap 5 or UIkit 3 needs. Hosting requirements are discussed late. The merchant expects migration validation to solve environment problems. The implementation team cannot confirm which extensions, overrides, modules, and integrations will remain active on the target site.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Separate environment readiness from data readiness. Before migration execution, confirm that the Joomla 6 site, hosting stack, PHP version, database version, template framework, extension set, and administrative access are ready for J2Commerce 6. Treat these items as prerequisites for meaningful migration testing.

If the target environment is still under development, Demo Migration results should be interpreted carefully. A data issue and an environment issue can look similar when the storefront is not fully prepared.

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

Create a readiness record that includes Joomla version, PHP version, database version, enabled frontend framework, target template, core J2Commerce 6 package status, active modules, required payment and shipping plugins, REST/API expectations, and any custom code planned for the store.

#### Pass Condition <a href="#pass-condition-1" id="pass-condition-1"></a>

The target environment can support J2Commerce 6 before migration results are judged. Any remaining environment gaps are documented separately from migrated-data issues.

### Pitfall 3: Assuming J2Store v4 Migrator Results Prove Launch Readiness <a href="#pitfall-3-assuming-j2store-v4-migrator-results-prove-launch-readiness" id="pitfall-3-assuming-j2store-v4-migrator-results-prove-launch-readiness"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

The merchant relies too heavily on the v4 migrator’s ability to copy and trace records. Dry-run and idmap results may show that products, variants, orders, customers, addresses, coupons, tax profiles, shipping methods, zones, geo-zones, and custom fields have migration paths. However, successful record movement does not automatically prove that the final J2Commerce 6 store is ready for launch.

The migrated data still needs interpretation inside J2Commerce 6. Product variants must be sellable, customer records must be usable, order history must be readable, tax and shipping context must make sense, and old plugin assumptions must be replaced or reconfigured.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

The project treats dry-run success as the main validation result. The idmap is reviewed for traceability but not for business usefulness. The team checks record counts but does not open representative products, variant-heavy products, refunded or discounted orders, customer addresses, shipping methods, payment context, or custom fields inside the target administration and storefront.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Use the migrator’s dry-run and idmap behavior as an important control layer, not as the final proof of quality. After Demo Migration, validate the migrated result in business terms: can shoppers buy the right products, can administrators understand orders, can customers be served, can replacement plugins support expected behavior, and can the storefront render the correct journey?

For J2Store v4 sources, include samples that expose source complexity rather than only the newest or simplest records.

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

Choose Demo Migration samples that include simple products, flexible or variant products, products with multiple images, downloadable products, orders with coupons, orders with shipping and tax, customer addresses, guest checkout examples, custom fields, and source records tied to important payment or shipping behavior.

#### Pass Condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Dry-run and idmap output are reviewed together with storefront, checkout, administration, and operational validation. The migrated result is judged by usefulness, not only by traceable record movement.

### Pitfall 4: Underestimating Plugin Replacement and Event-Model Changes <a href="#pitfall-4-underestimating-plugin-replacement-and-event-model-changes" id="pitfall-4-underestimating-plugin-replacement-and-event-model-changes"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

A source store depends on old J2Store payment plugins, shipping plugins, app plugins, or custom event behavior, and the migration plan assumes these will continue unchanged. J2Commerce 6 uses a different native Joomla plugin/event model, so old J2Store plugin behavior cannot be treated as automatically compatible.

This can affect checkout, shipping rates, payment capture, order statuses, customer communication, tracking, tax handling, subscription behavior, integrations, and custom workflows. If replacement availability is not reviewed early, the merchant may discover after data migration that the store cannot process important transactions the way the business expects.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

The source plugin list is not documented. Payment and shipping behavior is described only by the provider name, not by actual business rules. The merchant says “we use the same provider,” but cannot confirm whether the J2Commerce 6 plugin exists or behaves the same way. Custom plugin logic is undocumented. Checkout tests are postponed until late in the project.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Build a plugin replacement map before migration execution. Identify each payment method, shipping method, app plugin, report plugin, marketing integration, checkout extension, and custom plugin involved in the source store. Then classify each item as replaceable by a J2Commerce 6 equivalent, reconfigurable inside J2Commerce 6, outside migration scope, or requiring Custom Service review.

Do not treat provider-name similarity as proof of behavior continuity. A PayPal, Stripe, shipping, tax, or custom integration may still require configuration and testing in the new platform.

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

Create a checkout dependency table with four columns: source behavior, business purpose, J2Commerce 6 replacement or configuration path, and validation sample. Use it to test payment success, payment failure, free shipping, paid shipping, tax calculation, coupons, and order status updates.

#### Pass Condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Every important plugin-dependent behavior has a confirmed target handling plan, and checkout validation proves that the replacement behavior supports the merchant’s real operating needs.

### Pitfall 5: Migrating Products Without Proving Variant and Image Behavior <a href="#pitfall-5-migrating-products-without-proving-variant-and-image-behavior" id="pitfall-5-migrating-products-without-proving-variant-and-image-behavior"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Products are migrated, but variant and image behavior is not validated deeply enough. J2Commerce 6 supports modern product and variant handling, including flexible product variants and improved image workflows, but source stores may use option combinations, option-linked images, custom fields, pricing rules, inventory rules, or old app behavior in different ways.

The storefront may show products, but shoppers may not be able to select the right option, see the right image, understand the price, or purchase the right item. Administrators may also struggle to maintain inventory or product relationships after launch.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

Validation uses only simple products. Product samples do not include size/color combinations, variant-specific images, products with multiple images, inventory-sensitive products, downloadable products, custom fields, or products that were built through old J2Store apps. The team checks product visibility but not shopper selection behavior.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Select product samples by structural complexity. Validate not only whether products exist, but whether the buying decision survives the migration. That includes names, SKUs, descriptions, prices, categories, manufacturers, variants, images, custom fields, downloadable files, inventory behavior, related products, and storefront presentation.

When source behavior depends on apps or custom code, review whether the target behavior fits standard service capability, Add-on capability, or Custom Service.

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

Include at least one simple product, one variant-heavy product, one product with option-linked images, one downloadable product, one product with customer-facing custom fields, one product with special pricing, and one product that represents a major revenue category in the Demo Migration sample set.

#### Pass Condition <a href="#pass-condition-4" id="pass-condition-4"></a>

Representative products are not only present in J2Commerce 6; they are sellable, understandable, visually correct, and manageable after migration.

### Pitfall 6: Treating Storefront Framework Choice as Cosmetic <a href="#pitfall-6-treating-storefront-framework-choice-as-cosmetic" id="pitfall-6-treating-storefront-framework-choice-as-cosmetic"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

The project treats Bootstrap 5 or UIkit 3 selection as a design preference rather than a migration and validation factor. J2Commerce 6 supports both frameworks, but the target Joomla template, modules, overrides, product pages, category views, checkout pages, cart behavior, and custom presentation logic must align with the selected frontend framework.

A store can have accurate data but still fail the customer experience if templates, layout overrides, modules, or framework-specific rendering decisions are not prepared.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

The target template is not chosen before migration testing. Bootstrap 5 and UIkit 3 are discussed late. The merchant expects the old storefront layout to reproduce automatically. Product detail pages, category pages, cart, checkout, mini-cart modules, currency modules, and related product modules are not validated in the selected template environment.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Choose the target frontend framework early and validate migrated data inside the actual Joomla template environment. Separate migration responsibilities from layout implementation responsibilities. If custom overrides are required, document whether they are implementation work, Custom Service review, or post-migration storefront work handled outside the migration.

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

After Demo Migration, open a product list, product detail page, category page, cart, checkout page, customer account area, and key module positions in the selected framework. Confirm that variant selection, image galleries, cart behavior, checkout fields, and pricing information render correctly.

#### Pass Condition <a href="#pass-condition-5" id="pass-condition-5"></a>

The migrated store can be reviewed in the intended Joomla template and frontend framework, and presentation gaps are separated from data-quality issues.

### Pitfall 7: Ignoring API, Webservices, and Integration Meaning <a href="#pitfall-7-ignoring-api-webservices-and-integration-meaning" id="pitfall-7-ignoring-api-webservices-and-integration-meaning"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

The migration focuses on internal store records but ignores external systems. J2Commerce 6 includes a modern integration surface through Joomla webservices, REST/API capability, console commands, task scheduling, and extensibility. For merchants using ERP, warehouse systems, analytics, reporting, AI assistants, tax systems, shipping services, or custom dashboards, migration quality depends on whether the target data can support those downstream workflows.

If integration meaning is ignored, the store may launch with correct-looking data but fail operationally when external systems cannot identify products, customers, orders, inventory, or statuses correctly.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

External identifiers are not documented. ERP, warehouse, analytics, tax, shipping, or reporting dependencies are mentioned casually but not included in the migration scope. The merchant assumes integrations will reconnect automatically. No API or webhook-equivalent validation sample exists. Custom field mapping is not reviewed.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Identify external dependencies before migration. Determine which identifiers, fields, statuses, product structures, customer groups, inventory values, and order states are required by connected systems. If the integration requires target-specific transformations, custom identifiers, bespoke mapping, or adjustments to custom migration logic, review Custom Service before execution.

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

For integration-heavy stores, validate a sample flow from the migrated product to the order to the external system reference. Confirm product IDs or SKUs, customer identifiers, order statuses, tax values, shipping values, inventory updates, and any required custom fields.

#### Pass Condition <a href="#pass-condition-6" id="pass-condition-6"></a>

The migrated J2Commerce 6 data supports the external systems the merchant depends on, or unresolved integration gaps are clearly assigned to configuration, Add-on review, Custom Service, or post-migration implementation.

### Pitfall 8: Confusing Configuration Work with Migrated Data <a href="#pitfall-8-confusing-configuration-work-with-migrated-data" id="pitfall-8-confusing-configuration-work-with-migrated-data"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

The merchant expects tax, shipping, payment, currencies, checkout rules, free shipping conditions, table rates, live currency updates, reporting, scheduled tasks, and system behavior to migrate exactly as records. Some information may be migrated or mapped, but configuration-sensitive behavior often needs target setup and validation inside J2Commerce 6.

This creates confusion after migration because the record counts may look correct, while the store does not calculate or process orders as expected.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

Configuration behavior is not documented before migration. The team cannot explain which tax rates, geo-zones, shipping rules, payment methods, currency settings, checkout modes, or automation tasks must be recreated or verified. Demo Migration review does not include a checkout test with representative tax, shipping, payment, and coupon examples.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Classify each behavior as migrated data, target configuration, plugin replacement, Add-on-supported mapping/configuration, Custom Service review, or external implementation. This is especially important for payment, shipping, tax, currency, checkout, reporting, and automation behavior.

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

Prepare a configuration evidence sheet with examples of tax calculations, shipping charges, free shipping cases, payment methods, currency display, coupon behavior, order status transitions, and notification expectations. Use those examples during Demo Migration validation.

#### Pass Condition <a href="#pass-condition-7" id="pass-condition-7"></a>

The merchant knows which behaviors were migrated, which were configured in J2Commerce 6, which require replacement plugins, and which require further review before launch.

### Pitfall 9: Selecting Demo Migration Samples That Are Too Easy <a href="#pitfall-9-selecting-demo-migration-samples-that-are-too-easy" id="pitfall-9-selecting-demo-migration-samples-that-are-too-easy"></a>

#### What Goes Wrong <a href="#what-goes-wrong-8" id="what-goes-wrong-8"></a>

Demo Migration samples are selected because they are clean, recent, or easy to inspect. The migration then appears successful, but the sample does not include the records most likely to reveal problems: variant-heavy products, old J2Store app-driven products, custom fields, payment/shipping edge cases, discounted orders, guest checkout, customer addresses, failed or refunded orders, multilingual records, downloadable files, or integration-dependent data.

This makes the final migration look safer than it is.

#### Early Warning Signs <a href="#early-warning-signs-8" id="early-warning-signs-8"></a>

All sample products are simple. Orders do not include tax, shipping, discounts, different payment states, or old statuses. No samples include custom fields or legacy app behavior. The target storefront is reviewed only through one product page and one order record.

#### Prevention <a href="#prevention-8" id="prevention-8"></a>

Design samples by risk, not convenience. Every Demo Migration should include records that reveal the platform’s important migration questions. For J2Commerce 6, that means samples that test Joomla 6 rendering, product variants, custom fields, image behavior, tax, shipping, payment, customer addresses, guest checkout, plugin replacement, and source-specific data.

#### Recommendation Example <a href="#recommendation-example-8" id="recommendation-example-8"></a>

Build a sample set with at least five product types, five order types, several customer profiles, configuration-sensitive records, one or more integration-dependent records, and storefront pages using the selected frontend framework.

#### Pass Condition <a href="#pass-condition-8" id="pass-condition-8"></a>

Demo Migration samples prove the hard parts of the migration, not only the simplest records.

### Pitfall 10: Waiting Too Long to Escalate Custom or Unsupported Behavior <a href="#pitfall-10-waiting-too-long-to-escalate-custom-or-unsupported-behavior" id="pitfall-10-waiting-too-long-to-escalate-custom-or-unsupported-behavior"></a>

#### What Goes Wrong <a href="#what-goes-wrong-9" id="what-goes-wrong-9"></a>

The migration proceeds under a lighter service approach even though the source store includes unsupported plugin data, custom fields, external identifiers, bespoke checkout logic, custom order structures, app-owned data, old J2Store behavior that has no direct J2Commerce 6 equivalent, or Custom Platform source records.

By the time the issue is recognized, the merchant may need rework, a delayed launch, extra validation, or a service-path change.

#### Early Warning Signs <a href="#early-warning-signs-9" id="early-warning-signs-9"></a>

The source store has custom development, but no one has documented what it changes. External systems depend on fields that are not part of ordinary product, customer, or order records. The merchant expects old plugin behavior to appear in J2Commerce 6 without replacement planning. Demo Migration shows partial results that require manual explanation.

#### Prevention <a href="#prevention-9" id="prevention-9"></a>

Escalate early when the migration requires more than standard service capability. Use Advanced Data Mapping, Advanced Data Configure, or the Data Filter Add-on only when the need fits those Add-on boundaries. Use Custom Service when the project requires Tailored Add-ons, Custom Add-ons, Custom Platform handling, unsupported extension data, custom fields, external identifiers, bespoke transformation, or custom migration logic adjustment.

#### Recommendation Example <a href="#recommendation-example-9" id="recommendation-example-9"></a>

During preparation, classify each non-standard requirement into one of four outcomes: standard-supported behavior, Add-on review, configuration review, or Custom Service review. Do not wait for Full Migration to determine whether the selected approach is too light.

#### Pass Condition <a href="#pass-condition-9" id="pass-condition-9"></a>

Custom or unsupported behavior has a clear handling path before Full Migration. The selected migration approach matches the actual complexity of the source store and the target J2Commerce 6 result.

### Pitfall Prevention Summary <a href="#pitfall-prevention-summary" id="pitfall-prevention-summary"></a>

The strongest J2Commerce 6 migrations avoid treating the platform as either a simple J2Store v4 continuation or a generic Joomla extension. They respect the modern Joomla 6 foundation, verify environment readiness, test v4 migration results carefully where relevant, plan plugin replacement, validate storefront rendering, and confirm configuration-sensitive behavior before launch.

| Prevention area                  | What to confirm before launch                                                              | Best review method                        |
| -------------------------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------- |
| Target generation                | J2Commerce 6 is the intended Target Platform, with Joomla 6 and PHP 8.3+ readiness         | Environment readiness review              |
| V4 migration context             | Dry-run output, idmap traceability, and original-data preservation are understood          | Demo Migration and migrator-result review |
| Plugin replacement               | Old J2Store payment and shipping behavior has a J2Commerce 6 handling plan                 | Checkout and plugin-dependency testing    |
| Product behavior                 | Variants, images, inventory, custom fields, and downloads remain sellable                  | Representative product samples            |
| Storefront rendering             | Bootstrap 5 or UIkit 3 output matches the target template direction                        | Frontend page review                      |
| Configuration-sensitive behavior | Tax, shipping, payment, currency, coupons, and checkout behavior are configured and tested | Scenario-based checkout validation        |
| Integrations                     | External identifiers, API needs, and connected-system expectations are documented          | Integration sample testing                |
| Service fit                      | Add-on, Managed Service, and Custom Service needs are identified before Full Migration     | Service-path review                       |

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Commerce 6 migration pitfalls usually come from treating modern platform behavior as if it were ordinary record movement. The platform gives Joomla merchants a new native Joomla 6 foundation, but that foundation also changes what must be prepared, tested, and validated.

A strong migration plan confirms the target environment, treats J2Store v4 migration output as traceable evidence rather than automatic launch proof, reviews plugin replacement early, validates product and checkout behavior deeply, and escalates custom or unsupported requirements before they become launch blockers.

Use Demo Migration results to test the migration areas most likely to affect launch quality: product variants, images, customers, orders, custom fields, payment, shipping, tax, storefront rendering, and integration behavior. If the results show unsupported plugin data, Custom Platform records, external identifiers, custom migration logic adjustment, or broader transformation needs, review the selected migration path through Live Chat before moving to Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the biggest mistake merchants make when moving to J2Commerce 6?**

The biggest mistake is treating J2Commerce 6 as a minor continuation of J2Store v4. It is a modern Joomla 6-native platform with different environments, plugins, frontends, and validation expectations. Migration planning should account for those differences before Full Migration.

**Does a successful J2Store v4 dry-run mean the J2Commerce 6 migration is ready?**

No. A dry-run can show what is expected to migrate and can help identify migration issues, but the migrated result still needs business validation. Products, variants, orders, customers, checkout behavior, tax, shipping, payment, storefront rendering, and plugin replacement should be reviewed in J2Commerce 6.

**Why do old J2Store payment and shipping plugins need special review?**

Older J2Store plugins were built for a different architecture and event model. J2Commerce 6 uses native Joomla 6 patterns and different plugin behavior, so important payment and shipping workflows should be reviewed against available J2Commerce 6 equivalents or replacement plans.

**Should storefront design be validated during migration?**

Yes. J2Commerce 6 supports modern frontend rendering, but the target template, Bootstrap 5 or UIkit 3 choice, modules, product pages, category pages, cart, and checkout should be tested together. Storefront issues can look like data problems if the implementation layer is not ready.

**When should Custom Service be reviewed for a J2Commerce 6 migration?**

Custom Service should be reviewed when the source includes Custom Platform data, unsupported plugin data, custom fields, external identifiers, bespoke checkout or order logic, old J2Store behavior without a clear J2Commerce 6 equivalent, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.
