# Storeden Validation Priorities

Storeden validation should prove that the migrated store can operate inside the target commerce environment, not only that record counts look complete. Storeden is positioned around cloud commerce, multichannel selling, catalog and inventory management, professional order management, integrated payments, logistics, themes, apps, plug-ins, API resources, marketplace channels, and TeamSystem ecosystem connections. That means validation has to connect migrated data with the way the target store will sell, fulfill, report, and connect after launch.

A clean migration result can still be incomplete if products are present but hard to discover, orders are present but not useful for support, customer records exist but do not match operational expectations, marketplace references are unclear, or logistics and payment context is treated as if it were live configuration. Validation should therefore move from record presence to business proof.

The strongest Storeden validation workflow uses representative samples. It checks ordinary records, complex records, and records tied to external workflows. The purpose is to confirm that migrated data is usable, that target-side configuration is understood, and that any remaining gaps are clearly assigned to configuration, Add-ons, Custom Service, connected apps, TeamSystem setup, or manual operational work.

### Storeden Validation Principle <a href="#storeden-validation-principle" id="storeden-validation-principle"></a>

Storeden validation should answer one practical question: can staff use the migrated store to sell, manage, and support the business without losing the meaning of the original data? The answer depends on product structure, inventory ownership, order history, customer context, content continuity, marketplace assumptions, logistics dependencies, payment references, and integration identifiers.

| Validation layer         | What to prove                                                                                                                            | Why it matters                                                                   |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Record completeness      | Expected products, categories, customers, orders, content, and images exist.                                                             | Confirms that migration scope was applied correctly.                             |
| Commercial meaning       | Products, prices, stock, categories, and product descriptions make sense to shoppers and staff.                                          | Prevents technically present records from becoming weak storefront assets.       |
| Operational context      | Orders, shipping labels, payment labels, customer relationships, and fulfillment notes remain interpretable.                             | Supports customer service, reporting, and post-launch operations.                |
| Configuration separation | Live payments, logistics, theme behavior, apps, marketplace channels, and TeamSystem connections are not confused with migrated history. | Prevents incorrect assumptions about what migration can configure automatically. |
| Exception handling       | Unsupported fields, app-owned data, external IDs, and custom structures are assigned to the right handling path.                         | Makes remaining work visible before launch.                                      |

Validation should be performed after Demo Migration, before Full Migration approval, after Full Migration, and again after any additional migration action that brings new or changed data into the target store.

### Validate Product and Catalog Usability <a href="#validate-product-and-catalog-usability" id="validate-product-and-catalog-usability"></a>

Product validation should begin with the catalog records that drive revenue and support workload. A small set of ordinary products can confirm baseline transfer, but Storeden validation needs more than a quick sample. It should include variant products, inventory-sensitive products, media-heavy products, products tied to marketplace channels, products with app-created values, and products that rely on custom fields or external identifiers.

| Product validation area      | What to inspect                                                                                        | Pass signal                                                                      |
| ---------------------------- | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| Core product fields          | Name, description, price, SKU or product code, status, product images, and product visibility.         | Products are readable, commercially accurate, and ready for target-store review. |
| Category relationships       | Primary and secondary category placement, storefront grouping, and navigation fit.                     | Products appear in the expected discovery paths.                                 |
| Inventory values             | Stock quantity, availability meaning, out-of-stock behavior, and stock-owner assumptions.              | Stock data supports the intended operating model and does not mislead shoppers.  |
| Product media                | Main images, gallery images, image order, missing assets, and image quality.                           | Product pages remain usable without manual image investigation.                  |
| Product attributes           | Specifications, filters, labels, custom values, manufacturer references, and merchandising fields.     | Descriptive data supports buying decisions instead of becoming hidden clutter.   |
| Marketplace-sensitive values | Channel IDs, listing titles, channel categories, feed references, or product availability assumptions. | Marketplace-related data is reviewed separately from storefront catalog data.    |

A product should not pass validation only because it exists. It should pass because the migrated record can be understood and managed in Storeden.

### Validate Categories, Navigation, and Discovery <a href="#validate-categories-navigation-and-discovery" id="validate-categories-navigation-and-discovery"></a>

Category validation checks whether customers and staff can find products after migration. Storeden emphasizes catalog and inventory management, multichannel distribution, and storefront presentation, so product discovery must be reviewed as its own validation layer.

| Discovery element      | Validation focus                                                                             | Failure signal                                                                             |
| ---------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Category tree          | Parent/child relationships, category names, product counts, and priority category placement. | Products exist but appear in unexpected or empty categories.                               |
| Navigation paths       | Header menus, footer links, campaign links, and category landing paths.                      | Categories exist but are not reachable from expected storefront routes.                    |
| Filters and attributes | Filter-driving values, labels, tags, specifications, and custom fields.                      | Filters are missing, inconsistent, overloaded, or not useful for shoppers.                 |
| Category content       | Descriptions, images, SEO copy, landing-page text, and internal links.                       | Important category pages become thin or disconnected from commercial context.              |
| Marketplace grouping   | Marketplace categories or channel classification.                                            | Marketplace classification is assumed to follow website category structure without review. |

Discovery validation should include a shopper-style test. Reviewers should search for a product, browse through the category structure, inspect filter behavior where relevant, and confirm that key product groups are reachable without relying on direct admin access.

### Validate Inventory and Availability Meaning <a href="#validate-inventory-and-availability-meaning" id="validate-inventory-and-availability-meaning"></a>

Inventory validation should confirm who owns the stock value after launch. Storeden provides catalog and inventory management, but many merchants rely on external systems, marketplace synchronization, logistics providers, ERP connections, or TeamSystem-related workflows. If stock ownership is unclear, migrated inventory can create false confidence.

| Inventory question                     | Validation requirement                                                                           | Handling implication                                                                          |
| -------------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| Is Storeden the stock owner?           | Confirm that migrated stock values will be managed directly in Storeden.                         | Full inventory validation can focus on target-store values and storefront availability.       |
| Is an external system the stock owner? | Confirm which identifiers connect Storeden to ERP, warehouse, logistics, or marketplace systems. | External IDs and integration setup may need Custom Service or separate implementation review. |
| Are all products stock-controlled?     | Separate physical products from digital, service, preorder, made-to-order, or unlimited items.   | Availability behavior may require configuration rather than migration-only validation.        |
| Are stock values channel-sensitive?    | Compare website stock assumptions with marketplace or logistics assumptions.                     | Marketplace and logistics validation should not be skipped.                                   |

A stock value is validated only when the team understands whether it is the launch value, historical reference, placeholder value, or externally controlled value.

### Validate Customer and Account Context <a href="#validate-customer-and-account-context" id="validate-customer-and-account-context"></a>

Customer validation should focus on usability for service, segmentation, and account continuity. Storeden migration may preserve customer details, addresses, order relationships, and selected supported values, but live account behavior, password access, marketing segmentation, and B2B workflows still need target-side review.

| Customer validation area         | What to inspect                                                                        | Pass signal                                                                     |
| -------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Identity                         | Email, name, company, phone, and duplicate handling.                                   | Staff can identify the right customer without confusion.                        |
| Addresses                        | Billing and shipping addresses, country, postal code, region, and formatting.          | Address records remain useful for support and future ordering.                  |
| Order links                      | Customer-to-order relationships and historical purchase visibility.                    | Staff can trace customer history where the target store supports it.            |
| Groups or segments               | B2B groups, pricing labels, marketing groups, or trade context.                        | Group meaning is preserved, mapped, or assigned to a target configuration task. |
| Consent and communication values | Newsletter flags, marketing preferences, or contact labels where available and scoped. | Communication-related values are not assumed to be active automation settings.  |

Validation should avoid promising password continuity unless the target process supports it. Customer records can migrate, but customer login behavior is usually controlled by the target platform and launch process.

### Validate Order History and Operational Evidence <a href="#validate-order-history-and-operational-evidence" id="validate-order-history-and-operational-evidence"></a>

Order validation is not the same as checkout validation. Historical orders show what happened before migration; target settings control what happens next. Storeden validation should make order history useful for customer service, accounting review, fulfillment context, and operational continuity.

| Order area       | Validation focus                                                                                                      | Pass signal                                                                          |
| ---------------- | --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Order identity   | Order number, date, customer, email, billing address, shipping address, and status.                                   | Orders can be searched and interpreted by staff.                                     |
| Purchased items  | Product names, SKUs, quantities, prices, discounts, taxes, and totals.                                                | Historical purchases remain commercially understandable.                             |
| Payment context  | Payment method label, transaction reference where scoped, paid/unpaid status, and refund information where supported. | Payment history is clear as history and not mistaken for live payment configuration. |
| Shipping context | Shipping method label, tracking value, carrier reference, and fulfillment status where supported.                     | Fulfillment history remains useful for service review.                               |
| Exceptions       | Cancelled orders, refunded orders, partially fulfilled orders, test orders, and manually edited orders.               | Edge cases do not distort reporting or service workflows.                            |

A migrated order should pass when staff can answer a customer question from the record. If a customer service representative cannot interpret what was purchased, paid, shipped, refunded, or cancelled, order validation is not complete.

### Validate Payments, Logistics, and Checkout Separation <a href="#validate-payments-logistics-and-checkout-separation" id="validate-payments-logistics-and-checkout-separation"></a>

Storeden includes payment, logistics, and order-management capabilities, but validation should distinguish migrated history from live configuration. Historical labels can support service and reporting. They do not automatically configure future checkout, payment capture, logistics rules, or shipping automation.

| Area             | Validate as migrated history                                                            | Validate as target configuration                                                            |
| ---------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Payment methods  | Historical payment labels and transaction references where scoped.                      | Active payment providers, settlement behavior, wallets, fraud checks, and checkout testing. |
| Shipping methods | Historical shipping labels, tracking values, fulfillment notes, and carrier references. | Live shipping rates, logistics providers, zones, tracking rules, and fulfillment process.   |
| Taxes            | Historical tax lines and totals where migrated.                                         | Future tax setup, invoicing logic, regional rules, and accounting integration.              |
| Discounts        | Order-level or item-level discount history.                                             | Future promotion rules, coupon behavior, and marketing automation.                          |
| Checkout flow    | Historical order records.                                                               | Live checkout configuration, payment testing, shipping testing, and confirmation emails.    |

Validation should include at least one live checkout test in the target store environment where possible. That test is not proof of migration quality by itself, but it confirms that migrated data is being reviewed alongside real Storeden configuration.

### Validate Content, SEO, and Redirect Readiness <a href="#validate-content-seo-and-redirect-readiness" id="validate-content-seo-and-redirect-readiness"></a>

Content and SEO validation should focus on the pages that carry business value. Storeden migration may include product content, category content, CMS pages, Blog Posts, metadata, images, and redirect planning inputs depending on scope, but the target store still needs review for theme placement, menu links, internal links, and launch timing.

| Content or SEO area | What to check                                                                                    | Pass signal                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- |
| Product URLs        | URL continuity, product slugs, priority product paths, and redirect needs.                       | Important product pages can be reached or redirected.                   |
| Category URLs       | Category landing pages, SEO copy, indexable paths, and redirected legacy paths.                  | High-value category traffic has a clear target path.                    |
| CMS pages           | Trang Hệ thống quản lý nội dung (CMS pages), policy pages, brand pages, and informational pages. | Non-product pages remain accessible and trustworthy.                    |
| Blog Posts          | Article titles, dates, categories, internal links, and media references.                         | Content-led traffic is not lost because posts were treated as optional. |
| Metadata            | Titles, descriptions, image alt text, canonical expectations, and noindex decisions.             | Search-facing information remains intentional.                          |
| Redirects           | Legacy URLs, destination URLs, domain timing, and post-launch crawl review.                      | Priority URLs do not produce avoidable 404 errors after launch.         |

A strong SEO validation process selects high-traffic URLs and representative page types. It does not try to manually inspect every URL before launch, but it does require enough samples to prove that redirect and metadata logic is working.

### Validate Apps, API Data, and TeamSystem Ecosystem Dependencies <a href="#validate-apps-api-data-and-teamsystem-ecosystem-dependencies" id="validate-apps-api-data-and-teamsystem-ecosystem-dependencies"></a>

Storeden validation should identify where migrated data intersects with apps, plug-ins, APIs, marketplace channels, logistics, and TeamSystem ecosystem connections. These areas are often the difference between a visible storefront migration and an operationally complete launch.

| Dependency type        | Validation focus                                                                                      | Possible handling path                                                                  |
| ---------------------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Apps and plug-ins      | App-owned fields, app settings, automation values, and extension-created records.                     | App reinstall, manual configuration, Add-ons, or Custom Service depending on data type. |
| Marketplace channels   | Channel identifiers, listing references, marketplace categories, pricing assumptions, and feed rules. | Target channel setup, integration review, or Custom Service for unsupported values.     |
| API references         | External IDs, sync keys, ERP references, warehouse IDs, accounting IDs, or CRM values.                | Custom Service or integration implementation review.                                    |
| TeamSystem connections | Management software, invoicing, payment, or ecosystem identifiers.                                    | Separate configuration and testing outside migration-only validation.                   |
| Logistics providers    | Carrier IDs, tracking formats, fulfillment rules, and shipping automation.                            | Target setup and logistics testing.                                                     |

A dependency should not be considered validated because the visible product or order migrated. The integration reference itself must either be present, mapped, recreated, or deliberately excluded.

### Validate Demo Migration and Full Migration Results Differently <a href="#validate-demo-migration-and-full-migration-results-differently" id="validate-demo-migration-and-full-migration-results-differently"></a>

Demo Migration validation is a decision checkpoint. Full Migration validation is launch readiness work. The same records can be reviewed in both stages, but the approval criteria should be different.

| Stage                  | Validation purpose                                                                | Approval question                                                      |
| ---------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Demo Migration         | Test data interpretation, service scope, field alignment, and exception handling. | Is the selected approach suitable before Full Migration?               |
| Full Migration         | Confirm the full approved scope has migrated and target-side review can proceed.  | Is the migrated store ready for final configuration and launch checks? |
| Later migration action | Bring over new or changed data after the last migration step.                     | Did the new data arrive without breaking already-reviewed records?     |
| Post-launch review     | Detect customer-facing, operational, or SEO issues after traffic moves.           | Are shoppers and staff experiencing the target store as intended?      |

Validation should become narrower and more evidence-based as the project moves forward. Demo Migration may reveal scope questions. Full Migration should confirm approved scope. Later migration actions should focus on changes since the last approved migration state.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden validation should prove usable commerce continuity. Products must be sellable, categories must support discovery, stock must make sense, customer and order history must support service, content and SEO must protect priority paths, and apps, APIs, marketplace channels, logistics, payments, and TeamSystem ecosystem references must be assigned to the right handling path.

A Storeden migration should pass validation when the merchant can distinguish migrated data from target configuration, confirm that representative records work in the target store, and explain any remaining gaps without guessing. That is the difference between a data transfer that looks complete and a launch that is operationally ready.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first after a Storeden Demo Migration?**

Start with representative products, categories, inventory, customers, and orders. Then review content, priority URLs, marketplace-sensitive records, logistics references, payment labels, and integration identifiers. The goal is to confirm whether the selected migration approach is suitable before Full Migration.

**Does migrated order history prove that checkout is ready?**

No. Migrated order history helps staff understand past purchases, payments, shipping labels, and customer relationships. Live checkout depends on Storeden payment, shipping, tax, notification, and logistics configuration.

**How should marketplace-related records be validated?**

Marketplace-related records should be checked separately from website catalog data. Product titles, categories, identifiers, availability assumptions, and channel rules may need target-side marketplace setup or Custom Service review if unsupported values must be preserved.

**When should Custom Service be considered during validation?**

Custom Service should be considered when validation reveals required unsupported app data, external-system identifiers, TeamSystem ecosystem references, marketplace-specific data, bespoke product logic, or custom migration logic adjustment.

**How should additional migration actions be validated?**

After any later migration action, compare new and changed records against previously approved records. Focus on recently added products, customers, orders, status changes, stock changes, and records that depend on apps or external systems.
