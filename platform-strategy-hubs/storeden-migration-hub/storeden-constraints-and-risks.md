# Storeden Constraints and Risks

Storeden migration risk usually comes from the difference between moving commerce records and recreating a working Storeden operating environment. Products, customers, orders, categories, images, and content may migrate into the Target Platform, but checkout setup, payment availability, shipping logic, marketplace synchronization, app behavior, storefront presentation, and external-system connections still need separate review.

The highest-risk cases are rarely simple record-count problems. They usually involve product meaning, channel-specific data, custom fields, integration identifiers, app-owned workflows, order interpretation, SEO continuity, or expectations carried over from a Source Platform that allowed deeper customization than Storeden’s hosted model.

### Where Storeden Migration Risk Concentrates <a href="#where-storeden-migration-risk-concentrates" id="where-storeden-migration-risk-concentrates"></a>

Storeden should be evaluated as a hosted cloud e-commerce Target Platform, not as a blank database that can reproduce every Source Platform behavior exactly. The following areas deserve early review because they often determine whether the migration remains straightforward or requires deeper planning.

| Constraint area                               | Why it matters                                                                                                                                 | Earliest review priority                                                                                                              |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Hosted operating boundaries                   | Custom code, database behavior, checkout logic, and server-side workflows from the Source Platform may not have a direct Storeden equivalent.  | Identify which behavior must become Storeden configuration, app behavior, integration work, accepted change, or Custom Service scope. |
| Catalog and inventory structure               | Products may carry variants, attributes, SKUs, stock, images, visibility rules, pricing logic, marketplace readiness, and category placement.  | Test complex products during Demo Migration, not only simple catalog records.                                                         |
| Variants and attributes                       | Product options may not preserve the same buying, pricing, image, or inventory meaning after migration.                                        | Review products where options affect price, SKU, stock, images, shipping, or marketplace publication.                                 |
| Categories, filters, and storefront discovery | Category structure, filters, menus, product grouping, and search behavior influence how customers find products.                               | Compare high-value categories, product paths, navigation, and filtered catalog views after migration.                                 |
| Orders and customer history                   | Historical orders may carry payment, shipping, tax, tracking, status, marketplace origin, and external-system meaning.                         | Validate readable order history with real examples from different order states and channels.                                          |
| Payments, shipping, and logistics             | Historical labels do not configure live payment, TS Pay, shipping rules, tracking, carrier services, logistics, or tax behavior.               | Separate order-history validation from live checkout and fulfillment readiness.                                                       |
| Marketplace and channel data                  | Amazon, eBay, Facebook, AliExpress, or other channel records may include channel-specific IDs, listing rules, and synchronization assumptions. | Identify which marketplace values are migrated, reconfigured, excluded, or reviewed through Custom Service.                           |
| Apps, APIs, and TeamSystem integrations       | Apps and external systems may own data or workflows outside ordinary product, customer, and order records.                                     | Document ERP, accounting, inventory, fulfillment, marketplace, and business-system dependencies before scope approval.                |
| Themes, domains, URLs, and SEO                | Storefront presentation and search continuity depend on theme setup, content, metadata, redirects, and domain planning.                        | Prepare priority URLs, metadata, redirect expectations, page content, and visual references before launch review.                     |

### Hosted-Platform Boundary Constraints <a href="#hosted-platform-boundary-constraints" id="hosted-platform-boundary-constraints"></a>

Storeden’s hosted model is useful for merchants that want a managed commerce environment, but it also creates boundaries. A Source Platform may contain custom database fields, module logic, checkout changes, server-side scripts, custom templates, or bespoke integrations that cannot simply be copied into Storeden as-is.

The constraint is not only technical. Custom behavior may carry commercial meaning: special product rules, customer segmentation, pricing conditions, fulfillment logic, marketplace publishing rules, tax behavior, or order-processing steps. If those rules are not identified early, the migrated store may contain familiar records but operate differently from the previous store.

#### Who is most affected <a href="#who-is-most-affected" id="who-is-most-affected"></a>

This constraint is most relevant for merchants moving from highly customized open-source platforms, custom-built stores, legacy systems, or Source Platforms with extensive module and database customization. It also affects stores that rely on external systems to calculate prices, update stock, publish marketplace listings, or control fulfillment.

#### Mitigation strategy <a href="#mitigation-strategy" id="mitigation-strategy"></a>

The migration plan should separate each custom behavior into one of four outcomes:

| Custom behavior outcome     | Meaning for Storeden planning                                                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Native Storeden structure   | The behavior can be represented through supported Storeden data or configuration.                                                           |
| App or integration setup    | The behavior belongs to a Storeden app, API connection, marketplace setup, or TeamSystem workflow.                                          |
| Accepted operational change | The previous behavior will not be reproduced exactly, and the business accepts the target difference.                                       |
| Custom Service review       | The behavior requires custom migration logic adjustment, external-data handling, unsupported app data treatment, or bespoke transformation. |

### Catalog, Variant, Attribute, and Inventory Constraints <a href="#catalog-variant-attribute-and-inventory-constraints" id="catalog-variant-attribute-and-inventory-constraints"></a>

Product migration into Storeden should not be judged only by product counts. Catalog quality depends on whether products remain sellable, searchable, manageable, and understandable in the target store.

Storeden catalog planning should review product names, descriptions, images, categories, filters, SKUs, stock, attributes, variants, prices, visibility rules, and marketplace-ready fields. When product options affect buying choices, pricing, stock, images, shipping, or marketplace publication, they become high-priority validation samples.

#### Common catalog risks <a href="#common-catalog-risks" id="common-catalog-risks"></a>

| Catalog risk                 | What can go wrong                                                             | Mitigation                                                                                                |
| ---------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Simple-product-only sampling | Demo Migration appears successful, but complex products fail later.           | Include products with variants, attributes, images, stock, category placement, and marketplace relevance. |
| Option meaning changes       | A Source Platform option becomes a weaker target field or loses buying logic. | Validate option display, SKU behavior, pricing, stock impact, and storefront purchase flow.               |
| Inventory mismatch           | Stock values migrate, but channel or fulfillment expectations are not ready.  | Review inventory records together with marketplace, logistics, and external-system workflows.             |
| Category or filter weakness  | Products arrive but are harder to find or group correctly.                    | Compare priority categories, navigation, filters, and customer-facing product discovery.                  |
| Custom fields ignored        | Important product fields are treated as decorative or out of scope.           | Identify fields used by staff, shoppers, marketplaces, ERP, or reporting systems before migration.        |

### Category, Filter, and Storefront Discovery Constraints <a href="#category-filter-and-storefront-discovery-constraints" id="category-filter-and-storefront-discovery-constraints"></a>

Storeden catalog structure affects more than backend organization. Categories, filters, product grouping, menus, storefront sections, search behavior, and landing paths all influence whether shoppers can find products after migration.

A migration can preserve product records but still weaken storefront discovery if products land in the wrong categories, lose important filter values, miss channel-specific fields, or no longer follow the previous navigation logic. This matters especially for stores with broad catalogs, marketplace-driven segmentation, seasonal collections, or SEO-sensitive category pages.

#### Mitigation strategy <a href="#mitigation-strategy-1" id="mitigation-strategy-1"></a>

Review discovery from a shopper’s perspective. Important checks include priority categories, top-selling products, menu paths, filtered product sets, product search, homepage or landing-page product blocks, and URLs that previously attracted traffic.

If category, filter, or menu logic depends on custom rules from the Source Platform, treat that behavior as a planning item instead of assuming it will migrate automatically.

### Customer, B2B, and Account Constraints <a href="#customer-b2b-and-account-constraints" id="customer-b2b-and-account-constraints"></a>

Customer records may look straightforward, but account meaning can vary across Source Platforms. A customer may carry addresses, company information, group membership, pricing eligibility, order history, marketing status, tax-related information, or external-system references.

Storeden planning should distinguish basic customer information from business rules that depend on customer groups, B2B handling, ERP records, accounting systems, loyalty programs, or app-owned workflows. If a Source Platform used custom customer fields or group-based pricing logic, those meanings need review before Full Migration.

#### Risk signals <a href="#risk-signals" id="risk-signals"></a>

Customer-related risk increases when the store depends on:

* customer groups or B2B account roles;
* company records, VAT or tax identifiers, or invoicing references;
* customer-specific pricing or discounts;
* external CRM, ERP, accounting, or loyalty IDs;
* newsletter or marketing segmentation stored outside ordinary customer records;
* app-owned customer data;
* custom fields used by support, sales, or finance teams.

These cases do not automatically prevent migration to Storeden, but they should not be reduced to basic customer-name and email migration.

### Order, Payment, Shipping, Logistics, and Tracking Constraints <a href="#order-payment-shipping-logistics-and-tracking-constraints" id="order-payment-shipping-logistics-and-tracking-constraints"></a>

Historical order migration and live order operation are separate concerns. A migrated order can preserve useful history without proving that Storeden payment, shipping, logistics, tracking, tax, or fulfillment behavior is configured for new sales.

Order records may include products, customer details, totals, tax values, discounts, payment labels, shipping methods, tracking numbers, order status, marketplace origin, carrier information, and external references. These values matter for customer service, reporting, fulfillment, and accounting after migration.

#### What should be reviewed <a href="#what-should-be-reviewed" id="what-should-be-reviewed"></a>

| Order area          | Constraint                                                                      | Review focus                                                                                           |
| ------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Order statuses      | Source statuses may not match Storeden workflow meaning exactly.                | Confirm how paid, pending, canceled, refunded, partially fulfilled, and completed orders appear.       |
| Payment labels      | Historical payment names do not configure live payment availability.            | Validate historical readability and separately configure live payment methods or TS Pay behavior.      |
| Shipping methods    | Old method labels may not reproduce live shipping rules.                        | Review historical labels, tracking values, carrier expectations, and logistics setup separately.       |
| Marketplace orders  | Channel origin and marketplace identifiers may be operationally important.      | Confirm which channel references are preserved, mapped, or handled outside standard records.           |
| External references | ERP, accounting, warehouse, or fulfillment IDs may be required after migration. | Identify whether these references are standard, app-owned, integration-owned, or Custom Service items. |

### Payment, Shipping, Tax, and Checkout Configuration Constraints <a href="#payment-shipping-tax-and-checkout-configuration-constraints" id="payment-shipping-tax-and-checkout-configuration-constraints"></a>

Storeden checkout readiness depends on target configuration. Historical order data can show what happened in the previous store, but it does not create a working checkout setup in the new environment.

Payment methods, TS Pay, tax settings, logistics services, shipping rules, tracking behavior, carrier relationships, fulfillment workflows, and marketplace order handling should be planned as target setup and launch-readiness tasks. Treating migrated order labels as configuration can lead to a store that has readable history but cannot process new orders correctly.

#### Mitigation strategy <a href="#mitigation-strategy-2" id="mitigation-strategy-2"></a>

Before launch, confirm:

* available payment methods and TS Pay expectations;
* shipping zones, shipping rules, carrier services, logistics setup, and tracking behavior;
* tax configuration and invoice-related requirements;
* marketplace checkout or channel-order handling expectations;
* how new Storeden orders will move into fulfillment, accounting, ERP, or reporting systems;
* who will test checkout, payment, shipping, tracking, notifications, and order status changes.

### Marketplace and Channel Constraints <a href="#marketplace-and-channel-constraints" id="marketplace-and-channel-constraints"></a>

Storeden can support multichannel selling, but marketplace data should not be treated as ordinary product data without review. Marketplace listings may contain channel-specific identifiers, publication rules, category mappings, price behavior, shipping settings, image requirements, synchronization status, and availability logic.

If the Source Platform already sold through Amazon, eBay, Facebook, AliExpress, or other channels, migration planning should define which data belongs in Storeden, which channel settings need reconfiguration, and which references must remain available for staff or external systems.

#### When marketplace risk increases <a href="#when-marketplace-risk-increases" id="when-marketplace-risk-increases"></a>

Marketplace risk increases when products depend on channel-specific IDs, when marketplace listings are synchronized through external apps, when pricing or stock differs by channel, or when marketplace orders must retain origin and fulfillment context.

In these cases, a standard product migration may not be enough to prove operational continuity. Marketplace-sensitive samples should be included in Demo Migration review, and unsupported channel-specific behavior should move into Custom Service review when it requires custom migration handling.

### App, API, ERP, and TeamSystem Integration Constraints <a href="#app-api-erp-and-teamsystem-integration-constraints" id="app-api-erp-and-teamsystem-integration-constraints"></a>

Apps, APIs, ERP systems, accounting tools, warehouse services, fulfillment tools, marketplace connectors, and TeamSystem integrations can carry operational meaning outside the main product, customer, and order records. These systems may store identifiers, synchronization rules, status mappings, invoice references, inventory relationships, or workflow triggers.

The risk is highest when the business expects integrations to keep working immediately after migration without confirming how Storeden will connect to the same systems. Data migration can prepare records, but integration continuity often depends on target setup, credentials, mapping, app configuration, and testing.

#### Mitigation strategy <a href="#mitigation-strategy-3" id="mitigation-strategy-3"></a>

Create an integration inventory before finalizing scope. At minimum, identify:

| Integration type                 | Examples of risk-bearing data or behavior                                                                                |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ERP and accounting               | Customer codes, product IDs, tax references, invoice numbers, order exports, stock synchronization, financial reporting. |
| Inventory and warehouse systems  | SKU mapping, stock locations, fulfillment status, shipping labels, picking workflows, replenishment logic.               |
| Marketplace apps                 | Channel listing IDs, publication status, category mapping, marketplace order origin, price and stock sync.               |
| Marketing and analytics          | Product feeds, customer segments, tracking scripts, campaign data, attribution, reporting continuity.                    |
| Custom API workflows             | External identifiers, webhook-like behavior, automation rules, custom field dependencies, status updates.                |
| TeamSystem ecosystem connections | Business-system workflows, accounting or management references, integration-specific field meaning.                      |

When integration data is not part of Storeden’s supported standard migration structure, it should be reviewed as Custom Service scope or as a target reconfiguration requirement.

### Theme, Domain, URL, and SEO Constraints <a href="#theme-domain-url-and-seo-constraints" id="theme-domain-url-and-seo-constraints"></a>

Storeden migration quality is also judged by the storefront experience. A technically successful data migration can still create launch risk if the target theme, domain, navigation, page content, metadata, redirect plan, and image usage are not prepared.

SEO-sensitive stores should avoid treating product and order migration as the entire project. Storefront structure affects customer trust, organic traffic, paid campaigns, marketplace landing paths, and post-launch reporting.

#### Mitigation strategy <a href="#mitigation-strategy-4" id="mitigation-strategy-4"></a>

Prepare a list of priority URLs, category pages, product pages, CMS Pages, Blog Posts, landing pages, metadata, redirects, image assets, and domain expectations. After Demo Migration, review whether priority products, categories, and pages are reachable and understandable in the target storefront.

If the Source Platform used custom URL rules, custom landing pages, app-generated pages, or marketplace-specific landing paths, those items should be reviewed before launch instead of being discovered during final acceptance.

### When Risk Increases Enough for Custom Service Review <a href="#when-risk-increases-enough-for-custom-service-review" id="when-risk-increases-enough-for-custom-service-review"></a>

Not every Storeden migration requires Custom Service. A standard migration path may be appropriate when the source data fits supported structures and the merchant accepts target configuration work for checkout, theme, channels, and integrations.

Custom Service review becomes important when the migration requires bespoke handling, custom migration logic adjustment, unsupported data treatment, app-owned data handling, external-system preservation, or transformation beyond standard service capability.

| Risk signal                                                   | Why it points to Custom Service review                                                                                  |
| ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Custom Platform source                                        | Source structures may not match a supported migration path and need custom interpretation.                              |
| Custom product fields or option behavior                      | Storeden may need tailored mapping or custom migration logic adjustment to preserve business meaning.                   |
| Unsupported app, plugin, or module data                       | The data may live outside standard commerce entities and require separate handling.                                     |
| Marketplace-specific identifiers or listing logic             | Channel data may need preservation, mapping, exclusion decisions, or reconfiguration beyond ordinary product migration. |
| ERP, accounting, warehouse, or TeamSystem references          | External identifiers and workflow relationships may need custom treatment.                                              |
| Custom checkout, payment, shipping, tax, or fulfillment logic | Live behavior cannot be assumed from migrated historical labels.                                                        |
| Complex SEO or URL transformation                             | Redirects, URL patterns, metadata, and landing-page structures may need project-specific planning.                      |
| Add-on modification or custom Add-on requirement              | Tailored Add-ons and Custom Add-ons are handled through Custom Service because customization is required.               |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden migration risk is manageable when the project distinguishes standard commerce records from hosted-platform configuration, app behavior, marketplace data, integration logic, storefront presentation, and SEO continuity. The key is to identify what must be migrated, what must be configured, what must be reconnected, and what must be treated as custom scope.

Before approving Full Migration, use Demo Migration results to test the parts of the store that carry the most business meaning: complex products, marketplace-sensitive records, important categories, varied orders, customer account context, shipping and payment labels, integration references, priority URLs, and storefront content. If those samples reveal unsupported structures or bespoke requirements, review Add-ons or Custom Service scope before launch planning depends on incomplete assumptions.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the biggest constraint when migrating to Storeden?**

The biggest constraint is usually the difference between migrated data and a fully configured hosted commerce environment. Product, customer, and order records may migrate, but payment methods, shipping rules, logistics, marketplace connections, apps, themes, integrations, and SEO continuity still need separate planning.

**Can Storeden reproduce every custom behavior from my current store?**

No. Storeden is a hosted Target Platform, so custom database behavior, server-side logic, checkout modifications, app-specific workflows, or external-system dependencies may need target configuration, accepted change, app setup, integration work, or Custom Service review.

**Why are marketplace records a migration risk for Storeden?**

Marketplace records may include channel-specific identifiers, category mappings, publication rules, price behavior, stock synchronization, and marketplace order context. These values may not behave like ordinary product or order fields, so they should be reviewed before migration scope is finalized.

**Do migrated payment and shipping labels configure Storeden checkout?**

No. Historical payment and shipping labels help preserve order history, but they do not configure live checkout, TS Pay, shipping rules, carriers, logistics, tax behavior, or fulfillment workflows in Storeden.

**When should Custom Service be reviewed for a Storeden migration?**

Custom Service should be reviewed when the migration involves a Custom Platform source, unsupported app or plugin data, custom product fields, marketplace-specific identifiers, ERP or TeamSystem references, custom checkout or fulfillment logic, complex URL transformation, or Add-on customization beyond available settings.
