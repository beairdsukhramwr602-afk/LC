# PrestaShop Validation Priorities

PrestaShop validation should prove that the migrated store is usable as a PrestaShop operating environment, not merely that records arrived. Product pages can exist while combinations are confusing. Categories can load while discovery is weaker. Customer groups can appear while pricing, visibility, or access meaning is unclear. Multistore contexts can be present while product, category, content, customer, or URL ownership is hard to govern.

The safest validation approach starts with the PrestaShop areas where source-store meaning is most likely to be reinterpreted: attributes and combinations, features, customization fields, category paths, customer groups, multistore scope, friendly URLs, modules, themes, overrides, and custom data. Record counts remain useful, but they are only evidence of presence. The real validation question is whether customers and internal teams can still understand, buy, support, and maintain the migrated store after launch.

### What PrestaShop Validation Must Prove <a href="#what-prestashop-validation-must-prove" id="what-prestashop-validation-must-prove"></a>

A PrestaShop migration should be validated through meaning, behavior, and governance. Meaning asks whether migrated records express the right commercial information. Behavior asks whether the storefront and back office still support real buying and operating scenarios. Governance asks whether the business can maintain the result after migration.

| Validation layer | PrestaShop proof required                                                                                                     | Failure signal                                                                             |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Record presence  | Products, categories, customers, orders, CMS Pages, Blog Posts, images, and supported related records appear where expected.  | Counts look acceptable, but important relationships or storefront behavior are not tested. |
| Catalog meaning  | Combinations, features, customization fields, prices, stock, images, and product descriptions express the right buying logic. | Product pages exist, but customers cannot confidently choose the right item.               |
| Discovery        | Categories, friendly URLs, SEO fields, navigation paths, and important destinations still support customer movement.          | Pages load, but browsing paths or destination meaning are weaker than expected.            |
| Customer context | Customer groups, customer records, order history, and group-sensitive expectations remain understandable.                     | Group names import, but their storefront or operational purpose is unclear.                |
| Shop governance  | Multistore assignments, shop URLs, languages, content, category scope, and shared versus separate data are explainable.       | Multiple shops exist, but ownership and boundaries are confusing.                          |
| Custom behavior  | Modules, themes, overrides, custom fields, and integrations are classified correctly.                                         | The team assumes module-driven behavior migrated as ordinary data.                         |

A result should not be approved because the easiest examples passed. PrestaShop validation needs samples that expose the store’s real operating burden.

### Validate Product Combinations, Features, and Customization Fields First <a href="#validate-product-combinations-features-and-customization-fields-first" id="validate-product-combinations-features-and-customization-fields-first"></a>

Product validation is usually the highest-priority PrestaShop review area because the platform distinguishes between selectable variation logic, descriptive product characteristics, and customer-entered customization. A product may be present in PrestaShop while those layers no longer communicate the right meaning.

The validation sample should include products where attributes create combinations, products with feature-heavy comparison data, products with customer-entered personalization fields, products where selected combinations affect price or stock, and products where images or SKUs vary by option. The goal is to confirm the buying path, not only the product record.

| Product layer        | What to validate                                                                                                      | Practical pass condition                                                                                                         |
| -------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Combinations         | Selectable choices such as size, color, capacity, or other variation-driving options.                                 | Customers can select the intended sellable variant and see the right price, image, SKU, stock, and availability where supported. |
| Features             | Invariable characteristics used for comparison or product detail.                                                     | Customers can compare and understand products without mistaking features for selectable choices.                                 |
| Customization fields | Inputs customers provide for personalization or order-specific detail.                                                | The field appears intentionally, collects the right information, and supports fulfillment or support use.                        |
| Product associations | Related products, packs, accessories, manufacturer/brand context, or structured product relationships where relevant. | Relationships help buying or merchandising instead of creating confusing catalog clutter.                                        |
| Product media        | Images assigned to products or combinations where supported.                                                          | Visuals support the intended product decision and are not mismatched or incomplete.                                              |

Product validation should be performed with real commercial examples. Simple products prove baseline transfer. Complex products prove whether the PrestaShop interpretation is strong enough for launch.

### Validate Category Discovery and Friendly URL Continuity <a href="#validate-category-discovery-and-friendly-url-continuity" id="validate-category-discovery-and-friendly-url-continuity"></a>

PrestaShop categories should be validated as customer discovery structures, not only imported taxonomy records. Category validation should confirm that customers can browse naturally, find high-value products, and reach destinations that still make commercial sense.

Friendly URL validation should be tied to destination quality. A URL that resolves is not automatically successful if it leads to a less relevant page, weaker category path, missing product, duplicate destination, or page that no longer supports the original search or campaign intent.

Priority examples should include:

* top revenue categories;
* categories with deep subcategory structures;
* product pages with strong search demand or backlinks;
* manufacturer, brand, or supplier-led browsing paths where relevant;
* products assigned to multiple categories;
* CMS Pages or Blog Posts that support trust, policy, buying education, or SEO continuity;
* old URLs that should redirect, resolve, or be intentionally retired.

| Validation area    | Proof required                                                                                      | Why it matters                                                               |
| ------------------ | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Category hierarchy | Parent and child categories remain useful and maintainable.                                         | PrestaShop category records can exist while browsing becomes less intuitive. |
| Product placement  | Important products appear in the expected commercial paths.                                         | Misplaced products weaken discovery and merchandising.                       |
| SEO metadata       | Titles, descriptions, friendly URL slugs, and visible content are reviewed where included in scope. | Search continuity depends on more than record presence.                      |
| Priority routes    | High-value URLs lead to the right target destinations.                                              | Customers and search engines need destination continuity.                    |
| Group access       | Category or product visibility behaves correctly for relevant customer groups.                      | Access mistakes can hide or expose products incorrectly.                     |

Category and URL validation should not attempt to treat every page equally. Start with the destinations most likely to affect revenue, customer trust, or organic traffic.

### Validate Customer Groups and Order Context <a href="#validate-customer-groups-and-order-context" id="validate-customer-groups-and-order-context"></a>

PrestaShop customer groups can carry practical meaning for pricing, access, visibility, segmentation, communication, and internal support. Validation should confirm what the group still does after migration, not only whether the group label exists.

Representative customer samples should include ordinary customers, customers assigned to meaningful groups, customers with multiple addresses, guest or historical buyers where applicable, repeat customers, customers tied to important order histories, and customer records affected by modules or external systems.

| Customer or order area         | What to validate                                                                                             | Failure signal                                                                           |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Customer identity              | Names, emails, addresses, customer records, and order associations remain readable.                          | Staff can see records but cannot support the customer confidently.                       |
| Customer groups                | Group assignment and group-sensitive expectations remain explainable.                                        | Group labels import, but pricing, access, or segmentation meaning is uncertain.          |
| Historical orders              | Products, quantities, totals, discounts, taxes, payments, statuses, and references remain useful for lookup. | Orders are present but hard to interpret for support or reporting.                       |
| Module-dependent customer data | Loyalty, review, subscription, B2B, CRM, or external ID behavior is classified correctly.                    | The business expects custom or module-owned data to behave like native customer records. |

Order validation should separate historical readability from live checkout readiness. Migrated historical records help support and operational lookup. Live payment, shipping, tax, carrier, checkout, email, and module behavior still need PrestaShop-side setup and testing.

### Validate Multistore and Shop-Scope Assignments <a href="#validate-multistore-and-shop-scope-assignments" id="validate-multistore-and-shop-scope-assignments"></a>

When PrestaShop multistore is part of the target plan, validation must prove that each shop context remains understandable. Multistore is not only a record container. It can affect storefront identity, domains, languages, product and category assignments, prices, content, customer expectations, and operating responsibility.

A strong multistore validation sample should include at least one product shared across shops, one product limited to a specific shop, one category with shop-specific relevance, one high-value URL per important shop, one customer or group scenario where shop context matters, and one content page or CMS area where local trust or policy information differs.

| Multistore question                                        | Validation proof                                                                                           |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Which shops should exist?                                  | Each shop has a clear business purpose, audience, domain, language, or operating role.                     |
| What should be shared?                                     | Shared products, categories, customers, content, or configuration are intentional and explainable.         |
| What should differ?                                        | Shop-specific products, prices, categories, URLs, content, or modules are reviewed separately.             |
| Who governs each shop?                                     | Internal teams understand ownership and post-launch maintenance responsibility.                            |
| What requires revalidation after later migration activity? | New records, changed configuration, or refreshed target results are checked in the affected shop contexts. |

Multistore validation fails when the target technically contains shops but the business cannot explain which records belong where or why.

### Validate Modules, Themes, Overrides, and Custom Data <a href="#validate-modules-themes-overrides-and-custom-data" id="validate-modules-themes-overrides-and-custom-data"></a>

PrestaShop stores often depend on modules, themes, overrides, integrations, or custom fields to shape the real storefront and operating behavior. Validation should classify those dependencies instead of assuming they are automatically included in normal migration output.

The review should identify whether the dependency affects catalog display, combinations, personalization, discounts, tax, shipping, payment, checkout, reviews, loyalty, subscriptions, marketplaces, ERP/CRM IDs, reporting, analytics, or SEO behavior. Then it should decide whether the outcome is supported migration scope, Add-ons scope, Custom Service review, PrestaShop-side setup, third-party implementation, manual rebuild, or accepted exclusion.

| Dependency type                          | Validation question                                                                              | Likely handling path                                                             |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| Supported field needing better placement | Does the field map to a supported PrestaShop destination?                                        | Advanced Data Mapping or supported configuration may help.                       |
| Supported records needing exclusion      | Should obsolete products, old orders, retired categories, or inactive customers be filtered out? | Data Filter Add-on may help.                                                     |
| Module-owned records                     | Does a module store business-critical records outside standard fields?                           | Custom Service review is often needed.                                           |
| Theme or override behavior               | Does display or storefront logic depend on code, templates, or overrides?                        | PrestaShop-side setup or Custom Service review may be needed depending on scope. |
| External identifiers                     | Do ERP, CRM, accounting, marketplace, or reporting IDs need preservation?                        | Custom Service review is often needed.                                           |

Validation should not overpromise. Add-ons can support bounded filtering, mapping, or configuration needs. Custom Service is the safer review path when the requirement involves unsupported data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment.

### Validate Additional Migration Activity Before Launch <a href="#validate-additional-migration-activity-before-launch" id="validate-additional-migration-activity-before-launch"></a>

Many merchants continue selling while migration review is in progress. PrestaShop validation should therefore define what must be checked after later migration activity, especially when products, combinations, categories, customers, orders, CMS Pages, Blog Posts, or shop-specific records continue changing.

The validation burden changes depending on the action:

| Later migration activity                                | What to revalidate in PrestaShop                                                                                             |
| ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | New eligible records and regression samples from combinations, categories, groups, URLs, and shop contexts already reviewed. |
| Continue the Migration with a new configuration         | Newly migrated records plus fields, filters, mappings, or settings affected by the changed configuration.                    |
| Perform a new migration                                 | Refreshed target result, replaced earlier migrated target data, and the full set of launch-critical PrestaShop samples.      |

Entity Points should be interpreted correctly when planning later activity. Newly migrated eligible Product, Customer, Order, and Blog Posts records may consume Entity Points when first migrated. Records already counted through the service license do not consume Entity Points again simply because another migration action occurs on the same migration path.

### Build a PrestaShop Validation Report <a href="#build-a-prestashop-validation-report" id="build-a-prestashop-validation-report"></a>

A useful validation report should classify findings by business impact and handling path. It should not be a screenshot collection or a list of counts. Each finding should explain what was expected, what appeared in PrestaShop, how serious the gap is, and what action is needed.

| Report field     | Purpose                                                                                                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Sample record    | Identifies the product, combination, feature, category, customer, order, URL, shop, CMS Page, Blog Post, module behavior, or custom field being reviewed.                      |
| Expected outcome | States what the PrestaShop result should support.                                                                                                                              |
| Observed result  | Describes what the target actually shows.                                                                                                                                      |
| Severity         | Separates launch blockers from minor cleanup.                                                                                                                                  |
| Handling path    | Classifies the issue as migration correction, Add-on adjustment, Custom Service review, PrestaShop setup, third-party work, manual cleanup, accepted limitation, or exclusion. |
| Owner            | Assigns responsibility to the merchant, Next-Cart, PrestaShop-side setup team, developer, agency, or external partner.                                                         |
| Status           | Confirms whether the issue is open, corrected, accepted, or deferred.                                                                                                          |

A validation report passes only when it gives the business enough evidence to decide whether the PrestaShop target is ready for Full Migration approval, launch planning, or correction.

### Conclusion <a href="#conclusion" id="conclusion"></a>

PrestaShop validation should prove more than data arrival. It should prove that the migrated store still supports product choice, catalog discovery, customer context, shop governance, route continuity, historical order lookup, and module-sensitive operating behavior. The strongest validation process uses representative samples, checks the difference between migrated records and target-side setup, classifies custom or unsupported expectations early, and revalidates affected areas when later migration activity changes the result.

A PrestaShop migration is ready for approval only when the business can explain how the target works and trust that customers and internal teams can use it after launch. Record counts help confirm scope, but they do not replace meaning-based validation.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first after a PrestaShop Demo Migration?**

Start with high-risk product examples: combinations, features, customization fields, image behavior, price or stock differences, category placement, and product URLs. These areas reveal whether the migration preserved buying logic rather than only product presence.

**Is matching product and order counts enough for PrestaShop validation?**

No. Counts are useful completeness checks, but PrestaShop validation must also prove meaning. Product combinations, category paths, customer groups, multistore scope, URLs, orders, and module-sensitive behavior need representative review.

**How should customer groups be validated in PrestaShop?**

Customer groups should be tested with realistic customer examples. Confirm that group assignment, pricing or access expectations, customer context, and support interpretation remain understandable after migration.

**Does PrestaShop multistore need separate validation?**

Yes. If multistore is part of the target plan, validate each relevant shop context separately. Products, categories, URLs, customers, content, prices, and modules may need different review depending on how each shop is intended to operate.

**When should custom PrestaShop data be escalated during validation?**

Escalate when the issue involves unsupported records, module-owned data, custom fields, external identifiers, bespoke transformation, Custom Platform handling, or custom migration logic adjustment. Add-ons are appropriate only for bounded supported filtering, mapping, or configuration needs.
