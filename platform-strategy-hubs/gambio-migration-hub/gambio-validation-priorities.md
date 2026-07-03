# Gambio Validation Priorities

A Gambio migration should be accepted only when the migrated store can be used with confidence in the selected Gambio environment. Record counts are not enough. Products may exist without the right option behavior, categories may import without supporting navigation, CMS Pages may be present without preserving trust or SEO continuity, and historical orders may be readable without carrying the commercial context the merchant expects.

Validation is especially important because Gambio can support two different operating expectations. Gambio Cloud reduces responsibility for hosting, installation, updates, and support handling, while self-hosted Gambio gives more flexibility and customization potential but also places hosting, maintenance, and update responsibility on the merchant or technical team. A validation plan that ignores that difference can approve a migration that looks complete but does not match the future store’s operating reality.

The goal of validation is not to inspect every record one by one. The goal is to prove that representative records behave correctly, that platform-specific assumptions are visible before launch, and that any remaining gaps are classified before Full Migration. For Gambio, that means validating the operating model first, then catalog behavior, customer and order meaning, storefront continuity, integration boundaries, and scope decisions.

### What Validation Means for Gambio <a href="#what-validation-means-for-gambio" id="what-validation-means-for-gambio"></a>

Validation for Gambio should prove that migrated records keep their meaning after they enter the Target Platform. A product is not only a product name and price. It may include images, options, stock behavior, downloadable-product handling, category placement, tax and shipping implications, and maintenance expectations in the admin area. A customer record is not only an email address. It may include addresses, order history, customer-group meaning, consent context, and commercial interpretation.

Gambio validation should also prove that the selected operating environment supports the merchant’s expectations. A merchant moving into Gambio Cloud should confirm that the migrated data fits the available Cloud-oriented configuration and support model. A merchant moving into self-hosted Gambio should confirm that server readiness, update handling, custom behavior, and technical ownership are not left as hidden post-launch assumptions.

The strongest validation approach separates three layers: migrated records, target-store configuration, and non-migration behavior. Migrated records are the data that Next-Cart moves. Target-store configuration is the setup needed inside Gambio for that data to behave correctly. Non-migration behavior includes custom code, marketplace setup, payment-provider configuration, server-level changes, and external-service logic that may require separate work.

| Validation layer     | What must be proven                                                                                                           | Gambio-specific reason                                                                |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Migrated records     | Products, categories, customers, orders, images, CMS Pages, and other selected data arrive with usable structure.             | Gambio catalog and content behavior depends on more than record presence.             |
| Target configuration | Stock behavior, option display, checkout settings, payment, shipping, tax, and legal or trust content are configured for use. | These areas often require store setup after data migration.                           |
| Operating model      | Cloud or self-hosted responsibility is clear before launch.                                                                   | Hosting, updates, support, customization, and maintenance expectations differ.        |
| External behavior    | Marketplace connections, payment providers, custom features, and integration logic are not treated as migrated records.       | These expectations may require configuration, partner work, or Custom Service review. |

A Demo Migration should be used to test these layers before the Full Migration. If the sample only contains clean products, ordinary customers, and simple orders, it will not reveal whether the real store is ready. The validation sample should include representative complexity: options, multiple images, deep categories, stock-sensitive products, downloadable products, content pages, older orders, customer groups, marketplace-related products, and records tied to custom behavior.

### Validate the Gambio Operating Model <a href="#validate-the-gambio-operating-model" id="validate-the-gambio-operating-model"></a>

The first validation priority is the operating model. Gambio Cloud and self-hosted Gambio can both be valid targets, but they create different proof requirements. Cloud validation should confirm that the store can operate within a managed environment where hosting, installation, updates, and support are handled as part of the package. Self-hosted validation should confirm that the merchant has the technical ownership required to maintain the shop after migration.

This matters because migration results can look identical at the record level while creating different launch risks. A product with custom behavior may appear correctly in both environments, but the future handling of that behavior may depend on whether the merchant expects Cloud convenience or self-hosted flexibility. A storefront content page may migrate, but the responsibility for layout adjustment, legal-text updates, or template behavior may differ. A payment-sensitive order may remain readable, but the payment provider itself still needs target-side setup.

Validation should therefore include an environment-readiness check. The merchant should confirm whether the future store is Cloud or self-hosted, who owns updates, who maintains the shop, who handles technical issues, and which old-store customizations must be retired, configured, rebuilt, or reviewed separately. This check is not a substitute for technical setup; it prevents the migration result from being judged against the wrong expectation.

| Gambio decision           | Validation question                                                          | Launch-readiness signal                                                                      |
| ------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Gambio Cloud              | Does the migrated store fit the Cloud-oriented operating model?              | No critical requirement depends on unsupported server-side customization.                    |
| Self-hosted Gambio        | Has technical ownership been confirmed?                                      | Hosting, maintenance, updates, security, and custom behavior have responsible owners.        |
| Store support expectation | Is the merchant expecting support for data, settings, or custom development? | Questions are separated into migration issues, configuration tasks, and custom requirements. |
| Update planning           | Can the store remain maintainable after launch?                              | No migrated structure relies on obsolete or undocumented behavior from the old store.        |

A pass condition is simple: the validation team can explain what Gambio will own, what the merchant or technical team will own, and what Next-Cart is expected to migrate. If those boundaries are unclear, the migration may still be technically accurate, but it is not launch-ready.

### Validate Catalog Structure and Product Behavior <a href="#validate-catalog-structure-and-product-behavior" id="validate-catalog-structure-and-product-behavior"></a>

Catalog validation should confirm that products remain usable, maintainable, and understandable in Gambio. Gambio can support many articles, images, categories, category levels, product options, downloadable articles, and stock management. Those capabilities are useful only when the migrated catalog is tested against the way the merchant actually sells.

The validation sample should include simple products and complex products. Simple products confirm baseline migration behavior. Complex products reveal whether option logic, image handling, stock rules, downloadable-product settings, and category placement translate cleanly. If the source store used configurable products, variant-specific pricing, product bundles, option-specific stock, custom attributes, or marketplace-oriented catalog fields, those records should be included in Demo Migration review.

A product should be checked from three viewpoints. The admin viewpoint asks whether the merchant can maintain the product after migration. The shopper viewpoint asks whether the product can be found, understood, selected, and purchased. The operational viewpoint asks whether stock, downloadable content, pricing, shipping, and order context behave as expected.

| Catalog area           | What to validate                                                                          | Failure signal                                                                    |
| ---------------------- | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Product identity       | Name, SKU or article number, price, images, description, status, and category assignment. | Product exists but cannot be maintained or recognized confidently.                |
| Options and selections | Size, color, or other choice behavior appears clearly to shoppers.                        | Options display as flat attributes or lose price, selection, or purchase meaning. |
| Stock behavior         | Inventory is reduced or controlled according to the merchant’s expectation.               | Stock values exist but do not match purchasing or fulfillment logic.              |
| Downloadable products  | Downloadable items remain distinguishable from ordinary products.                         | Digital-product handling is treated as a simple description field.                |
| Category depth         | Categories and subcategories preserve browsing logic.                                     | Products are present but navigation becomes shallow, duplicated, or confusing.    |

Validation should not end with a product-count comparison. It should produce evidence that products can be managed, found, selected, purchased, and fulfilled. If complex products fail this test, the issue should be classified before the Full Migration as a mapping issue, target configuration issue, Add-on need, Custom Service requirement, or separate implementation task.

### Validate Customers, Orders, and Commercial Meaning <a href="#validate-customers-orders-and-commercial-meaning" id="validate-customers-orders-and-commercial-meaning"></a>

Customer and order validation should prove that commercial history remains readable and useful. In Gambio, a migrated customer account should not only preserve identity. It should preserve enough account, address, and customer-group context for the merchant to interpret the customer correctly after launch. A migrated order should not only preserve totals. It should preserve line items, discounts, taxes, shipping, payment context, order status, and any notes or historical markers needed for service and reconciliation.

This validation area requires careful sample selection. The sample should include repeat customers, customers with multiple addresses, customers from different groups, guests if relevant, orders with discounts, orders with tax variation, refunded or canceled orders, shipping-sensitive orders, and orders containing products with options or downloadable items. If only clean recent orders are checked, older or unusual history may fail after launch.

The key question is whether the merchant can answer common operational questions after migration. What did this customer buy? Which options were selected? Which tax and shipping context applied? Was the order discounted? Was the product physical or downloadable? Does the order history support customer service? If the answer requires manual interpretation outside Gambio, the order may be present but not fully usable.

| Commercial record          | Validation target                                                                   | Pass condition                                                     |
| -------------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Customer account           | Identity, addresses, customer-group meaning, and order connection.                  | Staff can recognize the customer and view useful history.          |
| Historical order           | Products, options, totals, discounts, taxes, shipping, payment context, and status. | Staff can interpret the order without relying on the old platform. |
| Discount or coupon history | Promotional context remains understandable.                                         | Discounts do not appear as unexplained total differences.          |
| Tax and shipping context   | Historical commercial logic remains readable.                                       | Order totals can be reconciled and explained.                      |
| Mixed product orders       | Physical, option-based, and downloadable items remain distinguishable.              | Staff can understand what was sold and fulfilled.                  |

Validation should distinguish historical readability from live configuration. Migrated historical orders do not automatically configure new checkout, payment, shipping, tax, discount, or fulfillment behavior in Gambio. If the merchant expects live behavior to match the old store, those expectations must be checked as target configuration or separate implementation, not approved merely because order history migrated.

### Validate Storefront Content, Navigation, and Search Continuity <a href="#validate-storefront-content-navigation-and-search-continuity" id="validate-storefront-content-navigation-and-search-continuity"></a>

Gambio validation should include storefront content because content affects trust, legal confidence, search visibility, and conversion. CMS Pages, editorial pages, category descriptions, navigation labels, product descriptions, metadata, images, and internal links can all influence whether the new store feels complete after migration.

This is especially important for merchants moving from stores where legal pages, landing pages, buying guides, homepage content, category text, or trust elements are tightly connected to the storefront layout. Gambio supports admin-controlled design adjustments and content management, but migrated content still needs to be checked for placement, formatting, link behavior, and customer-facing readability.

Search continuity should be validated at the URL and content level. Product URLs, category URLs, content-page URLs, metadata, internal links, and redirects should be reviewed against the migration scope. If URLs change, the validation team should confirm whether redirect planning, metadata review, or manual content adjustment is required. A visually complete store can still lose organic search value if content and URL assumptions are left unchecked.

| Storefront area              | What to validate                                                           | Evidence to collect                                         |
| ---------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------- |
| CMS Pages                    | Legal, trust, help, and informational pages are present and readable.      | Page list, rendered page samples, internal-link checks.     |
| Product and category content | Descriptions, images, metadata, and category text remain usable.           | Product and category samples from high-value areas.         |
| Navigation                   | Categories, menus, and content links guide shoppers coherently.            | Browse-path checks from homepage to product detail pages.   |
| SEO continuity               | URLs, metadata, internal links, and redirect needs are known.              | Comparison of important old URLs and new target paths.      |
| Layout-sensitive content     | Content that depended on the old theme is not assumed to render perfectly. | Screenshots or review notes for pages requiring adjustment. |

A pass condition is not that every page looks identical to the old store. The pass condition is that important content remains findable, readable, and aligned with launch expectations. Any design-level or legal-text update that sits outside the migration scope should be classified before launch.

### Validate Integrations, Customization, and External Dependencies <a href="#validate-integrations-customization-and-external-dependencies" id="validate-integrations-customization-and-external-dependencies"></a>

Many Gambio merchants care about marketplace connections, payment providers, shipping tools, remarketing systems, legal-text services, analytics, product feeds, or custom functionality. Validation should confirm which of these expectations are part of migrated data and which require target-side setup or separate review.

Marketplace and payment context is a common source of confusion. Product data may migrate, but the marketplace connection itself is not automatically implemented by moving the product record. Historical order data may migrate, but payment-provider configuration is still a target-store setup task. Content pages may migrate, but legal-text delivery, remarketing behavior, or external tracking may require configuration outside data migration.

Customization creates another validation boundary. Self-hosted Gambio may offer more flexibility for custom functionality or specific integrations, but that does not mean custom source-platform behavior migrates automatically. Cloud-oriented merchants should be even more careful not to assume server-level custom behavior can be carried over as part of standard data migration.

| Dependency type            | Validation question                                                                    | Likely classification                            |
| -------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Marketplace connection     | Are product and order records separate from the marketplace setup itself?              | Target configuration or separate implementation. |
| Payment provider           | Are historical payment details readable, and is live payment setup planned separately? | Target configuration.                            |
| Shipping tool              | Are historical shipping records readable, and are live shipping methods configured?    | Target configuration or integration setup.       |
| Custom code                | Does the expected behavior depend on source-platform logic or server-side changes?     | Custom Service review or separate development.   |
| Legal or marketing service | Is the migrated content separate from the service connection?                          | Target configuration or partner setup.           |

A strong validation result separates data quality from system behavior. If an integration-dependent record appears correct but the external service is not configured, the migration may still be accurate while the launch remains incomplete. That distinction should be visible before launch, not discovered by customers after the store goes live.

### Use Demo Migration Evidence to Decide Launch Readiness <a href="#use-demo-migration-evidence-to-decide-launch-readiness" id="use-demo-migration-evidence-to-decide-launch-readiness"></a>

Demo Migration evidence should be treated as a decision record. For Gambio, that record should show which sample products, categories, CMS Pages, customers, orders, downloadable items, option patterns, and integration-sensitive records were reviewed and what each sample proved. If the sample is too clean, the project may appear ready while the real catalog remains untested.

Launch readiness should be based on proof, not confidence. The team should be able to say which Gambio behaviors passed, which require target configuration, which require merchant review, and which require Add-ons, Custom Service, Additional Migration Options, or separate implementation. This distinction prevents validation from becoming a last-minute visual check.

A Gambio store is ready for Full Migration when representative records are usable in the admin area, understandable on the storefront, and meaningful for customer service. If validation exposes unclear ownership, unsupported behavior, or incomplete target configuration, the correct response is to classify the issue before launch rather than assume it will be resolved after the store goes live.

Demo Migration should be used as a decision checkpoint for Gambio. It should not be treated as a quick preview that only confirms whether data appears. The sample should be designed to expose the highest-risk assumptions: operating model, product options, stock behavior, category depth, CMS Pages, customer groups, complex orders, downloadable products, integrations, and custom behavior.

After Demo Migration, each finding should be classified. Some findings are normal target-store configuration tasks. Some require better mapping or Advanced Data Mapping. Some require Advanced Data Configure. Some require Add-ons. Some require Custom Service because they involve unsupported data, custom fields, extension behavior, bespoke transformation, or source-specific logic. Some are outside migration and belong to separate implementation.

| Demo Migration finding                                     | Best next decision                                                                        |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Record is missing or mapped incorrectly.                   | Review migration configuration, mapping, or selected data scope.                          |
| Record migrated but does not behave as expected in Gambio. | Check target configuration, platform limits, or mapping assumptions.                      |
| Behavior depends on a custom source-platform feature.      | Review Custom Service or separate implementation.                                         |
| New records must be added before Full Migration.           | Confirm whether they consume Entity Points or are already covered by the service license. |
| The merchant needs another migration action later.         | Choose the right Additional Migration Options path and plan revalidation.                 |

Launch readiness should be based on evidence, not optimism. A Gambio migration is ready to proceed when representative records behave correctly, configuration tasks are known, unresolved issues are classified, and the merchant understands which responsibilities belong to Gambio Cloud, self-hosted Gambio, Next-Cart, and any separate implementation team.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Gambio validation should prove more than record transfer. It should prove that the migrated store can operate in the selected Gambio environment with a usable catalog, readable commercial history, coherent storefront content, clear integration boundaries, and known launch responsibilities.

The most reliable validation path starts with the operating model, then tests catalog behavior, customers and orders, content and SEO continuity, external dependencies, and Demo Migration findings. When those checks are completed with representative samples and clear issue classification, the merchant can decide whether the Full Migration scope is ready or whether mapping, configuration, Add-ons, Custom Service, or separate implementation work should be addressed first.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is product-count validation enough for Gambio?**

No. Product counts only confirm that records exist. Gambio validation also needs to prove category placement, images, options, stock behavior, downloadable-product handling, product visibility, and admin maintainability.

**Should Gambio Cloud and self-hosted Gambio be validated differently?**

Yes. Cloud validation should confirm that migrated data fits the managed operating model. Self-hosted validation should also confirm technical ownership, update responsibility, custom behavior, and hosting readiness.

**Do marketplace and payment connections migrate automatically?**

No. Related product or order data may migrate when supported, but marketplace connections, payment-provider setup, and live integration behavior usually require target-side configuration or separate implementation.

**When should Demo Migration findings change the migration scope?**

Demo Migration findings should change scope when representative records reveal mapping gaps, unsupported behavior, custom fields, integration dependencies, or target configuration requirements that were not visible during planning.
