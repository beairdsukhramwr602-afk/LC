# Shopware Validation Priorities

Migrating into Shopware is not proven by record counts alone. A usable result must show that migrated commerce data behaves correctly inside Shopware’s sales-channel model, product and variant inheritance, rule-driven commercial logic, storefront presentation, and extension-influenced operations. Validation should therefore test the relationships that make the migrated store operational, not only whether Products, Customers, Orders, Categories, and other records are present.

Shopware validation is strongest when it combines data review, storefront review, and operational review. Catalog teams need to check product visibility and variant behavior. Merchandising teams need to confirm properties, categories, pricing, promotions, and content presentation. Operations teams need to review customer and order history, tax and shipping assumptions, payment context, and integration dependencies. Technical teams need to confirm custom fields, extension-owned behavior, API-connected systems, search/indexing behavior, and sales-channel scope.

### Validation Starts With Shopware Operating Context <a href="#validation-starts-with-shopware-operating-context" id="validation-starts-with-shopware-operating-context"></a>

Shopware can support different storefront, headless, and sales-channel setups. That flexibility is valuable, but it also means the target store can appear complete in the Administration while still being incomplete from a customer or operational perspective. Validation should begin by confirming which target operating context the migration is expected to support.

A single storefront with a simple catalog needs a different review depth from a multi-channel Shopware implementation with localized content, custom fields, rule-driven promotions, third-party plugins, or external integrations. The validation plan should reflect the real launch model.

| Validation area             | What must be confirmed                                                                                      | Why it matters in Shopware                                                         |
| --------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Sales channels              | Products, categories, currencies, languages, domains, and visibility align with the expected channel scope. | Shopware storefront behavior depends heavily on sales-channel context.             |
| Catalog structure           | Products, variants, properties, categories, media, and relationships are usable together.                   | Imported records can exist but fail commercially if relationships are incomplete.  |
| Rule-driven logic           | Pricing, promotions, shipping, payment, and customer conditions work as expected.                           | Shopware logic may rely on rules rather than static source-store values.           |
| Content and SEO             | Shopping Experiences, CMS content, URLs, metadata, and redirects support launch expectations.               | Storefront presentation and traffic continuity depend on more than catalog import. |
| Extensions and integrations | Custom fields, plugins, apps, and external systems are reviewed within scope.                               | Extension-owned behavior may not be proven by standard entity checks.              |

The first validation question should be: “Does the migrated store behave like the Shopware store the merchant intends to operate?” If the answer is unclear, validation is not complete.

### Catalog, Product, and Variant Validation <a href="#catalog-product-and-variant-validation" id="catalog-product-and-variant-validation"></a>

Catalog validation is the center of a Shopware migration review. Products should not be checked only as flat records. Reviewers should confirm product relationships, product visibility, properties, media, categories, translations, and parent-child behavior where variants are involved.

Shopware’s product and variant behavior can depend on inherited values, property groups, assigned categories, media relationships, and sales-channel visibility. If a source platform stores options or variants differently, migration validation must prove that the new Shopware model still supports customer selection, filtering, merchandising, and order placement.

| Catalog proof point    | Pass condition                                                                                         | Warning signal                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Product identity       | Product names, SKUs, slugs, descriptions, media, and status match the expected target records.         | Products exist but are inactive, duplicated, missing media, or missing canonical identifiers.  |
| Variant relationships  | Parent products and child variants preserve selectable options, SKUs, pricing, stock cues, and images. | Variants appear as separate products or inherit the wrong content, categories, or images.      |
| Properties and options | Product properties support filtering, variant selection, and merchandising expectations.               | Filters appear empty, inconsistent, duplicated, or disconnected from products.                 |
| Category assignment    | Products appear in the correct category hierarchy and storefront navigation context.                   | Products are imported but hidden from expected category or sales-channel views.                |
| Translations           | Localized product, category, and property values display correctly where languages are in scope.       | Default-language content leaks into localized storefronts or translated labels are incomplete. |

For complex catalogs, validation should include sample products from each major pattern: simple products, variant-heavy products, products with extensive properties, products with multiple category assignments, products with media galleries, products tied to custom fields, and products expected to appear in different sales channels.

### Sales Channel and Storefront Visibility Checks <a href="#sales-channel-and-storefront-visibility-checks" id="sales-channel-and-storefront-visibility-checks"></a>

Shopware validation must prove that migrated records are visible in the correct customer-facing context. A product record can be technically present but not available in the expected storefront if sales-channel assignments, active status, visibility settings, domains, language context, or indexing behavior are not aligned.

This matters especially when the target store uses multiple sales channels, localized storefronts, custom storefronts, or headless experiences. The migrated catalog should be reviewed from the Administration and from the customer-facing environment.

| Storefront checkpoint | What to review                                                                           | Expected outcome                                                                  |
| --------------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Product listing pages | Category pages, listing filters, sorting, thumbnails, and product cards.                 | Products appear in the right categories with usable merchandising signals.        |
| Product detail pages  | Variant selection, product properties, descriptions, media, prices, and availability.    | Customers can understand and select purchasable products without missing context. |
| Search and filters    | Search terms, property filters, category filters, and result relevance for key products. | Search and filtering expose migrated products in a practical way.                 |
| Sales-channel scope   | Product visibility by channel, domain, currency, language, and storefront.               | Records appear where intended and remain hidden where they should not be shown.   |
| Content placement     | CMS blocks, landing pages, product-category content, and navigation links.               | Storefront content supports product discovery and conversion.                     |

A clean validation result should show not just that the catalog is imported, but that customers can browse, filter, select, and buy from the migrated catalog in the intended Shopware storefront.

### Pricing, Promotions, Rules, Shipping, and Payment Logic <a href="#pricing-promotions-rules-shipping-and-payment-logic" id="pricing-promotions-rules-shipping-and-payment-logic"></a>

Many migration problems appear only when commercial logic is tested. Prices, discounts, shipping availability, payment options, customer conditions, and promotion behavior may depend on Shopware rules rather than on one-to-one source-store fields.

Validation should therefore include realistic purchase scenarios. Reviewers should test representative products, customer groups, currencies, shipping destinations, payment methods, promotions, and tax conditions. The goal is to confirm whether migrated data and configured Shopware rules work together.

| Scenario type                   | Review method                                                                 | What a pass proves                                                                       |
| ------------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Standard product purchase       | Add a simple product to cart and complete checkout review.                    | Core catalog, price, cart, shipping, payment, and order creation behavior work together. |
| Variant product purchase        | Select variant options and review price, stock, image, and order line output. | Variant relationships support actual purchase behavior.                                  |
| Promotion or discount           | Apply expected promotion conditions to eligible and ineligible carts.         | Rule logic does not over-apply or fail silently.                                         |
| Customer-specific behavior      | Review customer group, B2B, or account-based conditions where in scope.       | Customer segmentation expectations are reflected in storefront behavior.                 |
| Shipping and payment conditions | Test representative countries, regions, weights, carts, and payment methods.  | Checkout availability matches operational expectations.                                  |

Pricing and promotion validation should not assume that source-store logic automatically transfers into Shopware. When rules, apps, custom scripts, or external systems controlled commercial behavior in the old store, validation must confirm whether those behaviors were rebuilt, mapped, excluded, or assigned to a separate implementation path.

### Customer and Order Validation <a href="#customer-and-order-validation" id="customer-and-order-validation"></a>

Customer and order validation should prove that historical records remain usable for service, reporting, and operational continuity. The goal is not to recreate every old platform behavior. The goal is to confirm that migrated customer profiles, addresses, order histories, line items, statuses, totals, tax/shipping values, payment references, and fulfillment context can be understood in the target store.

Order review should include both ordinary and edge-case records. Historical orders with discounts, refunds, taxes, shipping adjustments, multiple products, variant products, guest checkout, special statuses, or integrations may expose issues that are not visible in a simple record-count audit.

| Entity area               | Validation focus                                                                                   | Practical pass condition                                                                   |
| ------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Customers                 | Names, emails, addresses, customer groups, account status, and key identifiers.                    | Customer records are searchable and recognizable by support teams.                         |
| Addresses                 | Billing and shipping address completeness, formatting, and country/region handling.                | Address data can support service review and future ordering where applicable.              |
| Orders                    | Order numbers, dates, line items, products, totals, taxes, shipping, payment labels, and statuses. | Staff can interpret historical orders without needing the old platform for routine lookup. |
| Discounts and adjustments | Coupons, promotions, refunds, tax adjustments, and shipping changes.                               | Financial history remains understandable even when old logic is not actively recreated.    |
| External references       | ERP IDs, marketplace IDs, accounting IDs, loyalty IDs, or custom fields where in scope.            | Operational identifiers needed outside Shopware remain available or clearly excluded.      |

Passwords and account authentication should be handled carefully because many platforms do not allow direct password migration in a usable form. Validation should confirm the intended customer-account activation or reset workflow rather than assuming old login behavior continues unchanged.

### Custom Fields, Extensions, Apps, and External Systems <a href="#custom-fields-extensions-apps-and-external-systems" id="custom-fields-extensions-apps-and-external-systems"></a>

Shopware projects often rely on custom fields, plugins, apps, ERP integrations, PIM systems, search services, payment providers, shipping tools, or custom storefront work. Validation must separate migrated platform data from behavior that belongs to extension configuration or external-system implementation.

A common validation error is to treat every missing behavior as a migration defect. Some items may be outside the agreed migration scope or dependent on extension setup. The review should identify which data was expected to migrate, which behavior must be configured in Shopware, and which requirements require Custom Service or external implementation work.

| Dependency type            | Validation question                                                                          | Likely action if incomplete                                                    |
| -------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Custom fields              | Are field values present, attached to the correct records, and useful in the target context? | Correct mapping, add missing scope, or classify as custom requirement.         |
| Plugins/apps               | Does the expected behavior come from Shopware core, an extension, or custom logic?           | Reconfigure extension, rebuild behavior, or exclude from migration acceptance. |
| ERP/PIM/accounting         | Are required identifiers and synchronization fields preserved where in scope?                | Confirm integration mapping and external-system ownership.                     |
| Search/indexing            | Are products discoverable after import, indexing, and configuration?                         | Reindex, review property mapping, or adjust search configuration.              |
| Headless/custom storefront | Does the storefront consume the migrated data correctly?                                     | Coordinate with storefront implementation, not only migration review.          |

Validation should produce clear ownership, not just an issue list. Each problem should be assigned as migration mapping, target configuration, extension setup, storefront implementation, external integration, or out-of-scope custom work.

### SEO, URL, Content, and Shopping Experiences Validation <a href="#seo-url-content-and-shopping-experiences-validation" id="seo-url-content-and-shopping-experiences-validation"></a>

Shopware validation should include storefront content and traffic continuity. Product and category URLs, metadata, landing pages, CMS blocks, Shopping Experiences, navigation, redirects, and internal links can affect discoverability and conversion after launch.

If the source store had important landing pages, campaign pages, blog-like content, category descriptions, or SEO-optimized product pages, validation should confirm whether those assets were migrated, rebuilt, redirected, or intentionally excluded. A technically clean catalog import may still fail launch readiness if traffic-relevant pages are missing or if high-value URLs are not handled.

| SEO/content area     | Validation target                                                                     | Pass condition                                                                     |
| -------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Product URLs         | Key product URLs, slugs, canonical expectations, and redirect coverage.               | High-value product pages resolve to intended Shopware pages or approved redirects. |
| Category URLs        | Category hierarchy, slugs, navigation, and redirect logic.                            | Category paths support browsing and do not strand important traffic.               |
| Metadata             | Titles, descriptions, structured page intent, and storefront snippets where relevant. | Critical pages preserve useful search and conversion context.                      |
| Shopping Experiences | CMS layouts, landing pages, product/category content, and campaign pages.             | Content that supports buying decisions is present or rebuilt with clear ownership. |
| Internal links       | Navigation, footer links, content links, and promotional links.                       | Customers and crawlers can move through the target site without broken paths.      |

SEO validation should be prioritized by business value. Review top product pages, top categories, historical traffic drivers, paid-campaign destinations, and brand-critical pages before checking low-impact URLs.

### Demo Migration and Full Migration Acceptance <a href="#demo-migration-and-full-migration-acceptance" id="demo-migration-and-full-migration-acceptance"></a>

Demo Migration is valuable because it creates a controlled sample for review before full migration. For Shopware, the sample should include records that stress the target model: variant products, property-rich products, multiple categories, localized records, customer groups, orders with discounts, custom fields, and extension-dependent records where relevant.

Full migration acceptance should build from the Demo Migration findings. If the demo exposes structural problems, the acceptance criteria should be updated before the full run. If the demo validates the mapping, the full review should confirm consistency across the complete dataset and then focus on launch-critical edge cases.

| Review stage            | Main purpose                                                                         | Output expected                                                 |
| ----------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------- |
| Demo Migration review   | Test mapping assumptions on a representative sample.                                 | Confirmed adjustments before full migration.                    |
| Full migration review   | Confirm complete data coverage and consistency.                                      | Approved migrated dataset or issue list with owners.            |
| Launch-readiness review | Verify storefront, checkout, content, URLs, integrations, and operational workflows. | Go/no-go decision based on usable target-store behavior.        |
| Post-launch watch       | Monitor customer issues, search behavior, order flow, and integration signals.       | Early correction of issues that only appear under live traffic. |

Acceptance should not be based on “no visible errors.” It should be based on evidence that the target store is usable for customers, staff, and connected systems.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopware validation should prove that migrated data works inside the target operating model. Products, variants, categories, customers, orders, URLs, rules, content, custom fields, extensions, and integrations should be reviewed as connected parts of the same commerce environment.

A strong validation process combines Administration checks, storefront checks, checkout scenarios, operational review, and ownership assignment. When reviewers can prove that the catalog is discoverable, products are purchasable, historical records are understandable, commercial logic behaves correctly, and custom or extension-dependent requirements are accounted for, the Shopware migration is much closer to launch readiness.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is record-count matching enough to validate a Shopware migration?**

No. Record counts are useful, but they do not prove that products are visible, variants are selectable, rules work, URLs resolve, content appears correctly, or orders remain usable.

**Which Shopware records should receive the most validation attention?**

Products, variants, properties, categories, customers, orders, custom fields, URLs, rules, and extension-dependent records usually need the most careful review because they affect storefront usability and operational continuity.

**Should sales channels be validated separately?**

Yes. Product visibility, language, currency, domain, navigation, and storefront behavior can differ by sales channel, so each launch-relevant channel should be reviewed.

**How should extension-dependent behavior be validated?**

Review whether the behavior belongs to Shopware core, an app, a plugin, custom fields, a storefront implementation, or an external system. Then assign ownership before treating the issue as a migration defect.

**What should Demo Migration prove before a full Shopware migration?**

Demo Migration should prove that representative products, variants, properties, categories, customers, orders, URLs, content, and custom fields can be mapped into Shopware in a usable way before the full dataset is migrated.
