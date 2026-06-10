# Storeden Data Model Differences

Migrating to Storeden is not only a matter of moving records into a hosted e-commerce account. The important question is whether each record keeps the same business meaning after it is interpreted inside Storeden’s catalog, inventory, order, storefront, marketplace, app, and integration model.

A source store may store product options, custom fields, category rules, payment labels, shipping methods, ERP references, marketplace identifiers, or app data in ways that do not match Storeden directly. Those differences should be reviewed before Full Migration so the migrated store can be judged by operational usefulness, not only by record counts.

### How Data Meaning Changes in Storeden <a href="#how-data-meaning-changes-in-storeden" id="how-data-meaning-changes-in-storeden"></a>

Storeden organizes commerce around a managed cloud environment. Products, inventory, orders, customers, payments, storefront content, apps, marketplace channels, and TeamSystem ecosystem connections need to fit the structures available in the target account.

| Source-store meaning         | Storeden interpretation to review                                                                                                                                          | Why it matters                                                                                                                      |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Product records              | Product data must become usable Storeden catalog records with descriptions, prices, images, categories, attributes, inventory, and sales-channel readiness where relevant. | A product that exists in the back office may still fail commercially if shoppers, channels, or staff cannot interpret it correctly. |
| Product variants and options | Source options may need to become Storeden variants, attributes, SKUs, or supported configuration values.                                                                  | Variant differences can affect pricing, stock, images, order details, and marketplace publication.                                  |
| Categories and filters       | Source categories, subcategories, tags, filters, and navigation paths need to support Storeden product discovery.                                                          | Product discovery depends on more than product import; the catalog must remain browsable and manageable.                            |
| Inventory values             | Stock quantities, SKU references, warehouse logic, marketplace availability, or ERP-driven stock may require target interpretation.                                        | Inventory mistakes can affect selling availability, fulfillment, and channel synchronization.                                       |
| Customer records             | Customer data may represent buyers, contacts, account holders, B2B users, newsletter records, or external CRM identities.                                                  | Customer meaning should be clear for order lookup, service history, marketing use, and account access expectations.                 |
| Orders                       | Historical orders need readable product, customer, payment, shipping, tax, tracking, and status context.                                                                   | Order history is useful only when staff can understand what happened and act on it after launch.                                    |
| Payment and shipping labels  | Historical labels do not automatically configure live payment gateways, TS Pay, logistics, tracking, or tax behavior.                                                      | Migration proof and target setup proof are different checks.                                                                        |
| Marketplace data             | Marketplace fields, identifiers, listings, availability rules, and channel-specific records may not be ordinary product data.                                              | Marketplace continuity may depend on mapping, reconfiguration, or Custom Service review.                                            |
| App and API data             | App-owned records, API identifiers, external references, and automation logic may sit outside standard commerce records.                                                   | Connected workflows can break even when products, customers, and orders appear present.                                             |
| SEO and content              | URLs, metadata, page content, category paths, redirects, images, and theme-controlled content need target review.                                                          | Search visibility and shopper continuity depend on how migrated content is presented and routed.                                    |

### Product and Catalog Data <a href="#product-and-catalog-data" id="product-and-catalog-data"></a>

Product data is usually the most visible part of a Storeden migration, but it is also where meaning can change quickly. A source product may include title, description, images, price, sale price, SKU, stock, tax class, brand, category, product type, attributes, options, related products, downloadable files, marketplace fields, or external inventory references.

Inside Storeden, those values need to support real catalog use. A migrated product should be understandable in the back office, discoverable in the storefront, available through the right sales channels, and usable in orders and inventory workflows.

#### Variants, Attributes, and SKUs <a href="#variants-attributes-and-skus" id="variants-attributes-and-skus"></a>

Variant and attribute handling should be reviewed carefully. Source platforms often store color, size, material, bundle selections, custom options, or configurable product logic differently. A field that behaves like a buying choice in the source store may become a variant, attribute, descriptive value, app-dependent field, or excluded custom value in Storeden.

The strongest Demo Migration samples should include products where variants affect price, SKU, inventory, images, shipping, category placement, or marketplace publication. These examples reveal whether catalog meaning survives the move into Storeden.

#### Categories, Subcategories, Tags, and Filters <a href="#categories-subcategories-tags-and-filters" id="categories-subcategories-tags-and-filters"></a>

Categories and subcategories are not just labels. They shape browsing paths, menu logic, product grouping, storefront structure, marketplace preparation, and SEO expectations. Filters and tags can also affect how customers locate products.

A clean migration should be checked from both the management side and the storefront side. Products should appear in the right catalog structure, and shoppers should still be able to find important products through the expected browsing paths.

#### Inventory and Channel Availability <a href="#inventory-and-channel-availability" id="inventory-and-channel-availability"></a>

Inventory data can have different meanings depending on how the source store manages stock. Some stores keep simple stock quantities. Others depend on warehouse logic, ERP synchronization, marketplace availability, backorder rules, reserved quantities, or external SKU references.

Storeden planning should identify whether inventory is only a migrated value or part of a connected workflow. When stock is controlled by ERP, marketplace, warehouse, or app logic, those dependencies should be included in migration scope discussions before acceptance.

### Customer, Account, and Contact Data <a href="#customer-account-and-contact-data" id="customer-account-and-contact-data"></a>

Customer data can represent several different business roles. A record may be a buyer, account holder, newsletter subscriber, B2B company contact, billing recipient, shipping recipient, marketplace customer, CRM contact, or external-system identity.

Storeden migration planning should avoid treating all customer-related records as the same thing. The target result should preserve the information needed for order lookup, customer service, account recognition, marketing decisions, and connected-system continuity where those needs are in scope.

#### B2B and Account-Specific Behavior <a href="#b2b-and-account-specific-behavior" id="b2b-and-account-specific-behavior"></a>

If the source store includes B2B pricing, company accounts, customer groups, restricted catalogs, account approvals, tax handling, credit terms, or buyer roles, those behaviors should be reviewed separately from basic customer migration.

Some B2B behavior may depend on target features, account configuration, apps, or custom handling. Customer records may migrate, while B2B rules, permissions, pricing logic, or approval workflows may need separate configuration or Custom Service review.

#### External Identifiers and Customer Relationships <a href="#external-identifiers-and-customer-relationships" id="external-identifiers-and-customer-relationships"></a>

Customer IDs, CRM references, ERP references, marketing IDs, marketplace buyer IDs, or accounting identifiers may be important even when they are not visible to shoppers. These values can connect migrated customer records to external workflows.

If those identifiers are required after launch, they should be identified early. Otherwise, the migrated customer list may look complete while downstream service, finance, marketing, or reporting workflows lose continuity.

### Order, Payment, Shipping, and Logistics Data <a href="#order-payment-shipping-and-logistics-data" id="order-payment-shipping-and-logistics-data"></a>

Order data carries a history of commercial activity. In Storeden, a migrated order should remain readable for support, fulfillment review, finance, customer service, and management reporting.

A source order may include customer details, product lines, variant labels, prices, discounts, taxes, shipping methods, tracking numbers, payment labels, status history, refund notes, marketplace origin, invoice references, or ERP identifiers. Each part should be reviewed for target meaning.

#### Historical Orders Are Not Live Configuration <a href="#historical-orders-are-not-live-configuration" id="historical-orders-are-not-live-configuration"></a>

Historical order data and live operating configuration are different. A migrated order may show a payment method, shipping method, tax amount, or tracking value from the old store, but that does not prove Storeden is configured for future checkout, TS Pay, payment gateways, logistics, tax settings, or shipping workflows.

This distinction matters during validation. Order history should prove readability and continuity. Live checkout, payment, shipping, tax, and logistics should be tested through the target account setup.

#### Shipping, Tracking, and Fulfillment Context <a href="#shipping-tracking-and-fulfillment-context" id="shipping-tracking-and-fulfillment-context"></a>

Shipping data may include carrier names, delivery methods, shipping prices, tracking numbers, fulfillment statuses, pickup options, warehouse references, or logistics-system values. These details may be important for customer support and operational review.

If shipping and logistics workflows depend on apps, carriers, marketplaces, or TeamSystem-connected systems, those relationships should not be treated as ordinary order fields. They may need mapping, reconfiguration, or Custom Service review.

### Marketplace and Multichannel Data <a href="#marketplace-and-multichannel-data" id="marketplace-and-multichannel-data"></a>

Storeden’s multichannel orientation means marketplace data can be a major part of migration meaning. Product information may be used for the web store, marketplaces, feeds, social commerce, advertising, or external sales channels.

Marketplace-related data can include listing IDs, channel SKUs, product titles, marketplace categories, channel prices, availability rules, synchronization status, image requirements, order origin, and fulfillment behavior. These values may not map cleanly as ordinary product or order fields.

When Amazon, eBay, Facebook, AliExpress, or other channels are important to the business, Demo Migration review should include channel-sensitive products and orders. The goal is to confirm which information appears in Storeden, which must be configured separately, and which dependencies need Custom Service review.

### Apps, Plugins, API Data, and TeamSystem Integrations <a href="#apps-plugins-api-data-and-teamsystem-integrations" id="apps-plugins-api-data-and-teamsystem-integrations"></a>

Storeden can operate with apps, plugins, API-connected workflows, and TeamSystem ecosystem integrations. These layers often carry business meaning that is not stored as standard products, customers, or orders.

Examples include ERP references, accounting IDs, invoice links, POS data, warehouse records, fulfillment rules, marketing automation, marketplace connectors, product feeds, B2B app records, custom reports, and API-created objects. These items should be reviewed as integration data, not assumed to migrate automatically.

#### App-Owned Data <a href="#app-owned-data" id="app-owned-data"></a>

An app can store settings, identifiers, mappings, statuses, templates, rules, logs, or external references. Some of that information may be necessary after launch, while some may only need reconfiguration in the target account.

If app-owned data affects selling, fulfillment, customer service, marketing, accounting, or reporting, it should be documented before migration scope is finalized. Standard product, customer, and order migration may not cover app-specific records.

#### API and Developer-Created Workflows <a href="#api-and-developer-created-workflows" id="api-and-developer-created-workflows"></a>

API-connected workflows can create a second layer of data meaning. A field may matter because another system reads it, updates it, or uses it as a key. Removing or changing that value can affect automation even when the storefront looks correct.

Custom API behavior, webhook-like workflows, external-system IDs, bespoke synchronization, and developer-created logic are Custom Service review signals when they need migration handling beyond standard service capability.

### Content, Theme, SEO, and URL Data <a href="#content-theme-seo-and-url-data" id="content-theme-seo-and-url-data"></a>

Storeden migration planning should also account for content and presentation. Product pages, category pages, CMS Pages, Blog Posts where supported, menus, static content, banners, images, metadata, redirects, and domain behavior can all affect launch quality.

A source theme or custom frontend normally does not transfer as an identical Storeden theme. The target storefront should be reviewed through Storeden theme, navigation, content, and configuration expectations.

SEO data should be checked through high-value examples. Priority product URLs, category URLs, metadata, page titles, redirects, image details, and landing pages should be included when search continuity matters.

### What Migrated Storeden Data Must Prove <a href="#what-migrated-storeden-data-must-prove" id="what-migrated-storeden-data-must-prove"></a>

A successful Storeden migration should prove that data remains useful inside the hosted target environment. The result should be evaluated by meaning, not only by whether records exist.

Strong validation should confirm that:

* products retain selling meaning through descriptions, images, pricing, SKUs, variants, attributes, inventory, categories, and channel-sensitive values;
* customers remain useful for account lookup, service history, marketing review, B2B context, and external-system continuity where applicable;
* orders remain readable with customer, product, payment, shipping, tax, tracking, status, and marketplace context;
* marketplace-related records are understood as channel-sensitive data, not ordinary product fields;
* app, API, ERP, accounting, POS, fulfillment, and TeamSystem-related values are either migrated, mapped, reconfigured, excluded intentionally, or reviewed through Custom Service;
* URLs, SEO metadata, content, theme presentation, and storefront discovery support launch expectations.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Storeden data model differences matter because a hosted multichannel commerce platform interprets store data through catalog, inventory, order, customer, payment, shipping, theme, app, marketplace, API, and TeamSystem integration structures. A record can be present and still lose business meaning if its relationships, identifiers, workflow role, or storefront use are not preserved.

Before Full Migration, review Demo Migration samples that include complex products, channel-sensitive catalog data, varied orders, customer and B2B examples, app-owned records, external identifiers, and SEO-sensitive pages. If the result shows that source data needs filtering, mapping, configuration changes, or custom migration logic adjustment, review the appropriate Add-ons or Custom Service path before treating the Storeden migration as ready for launch.

### FAQs <a href="#faqs" id="faqs"></a>

**Why do Storeden data model differences matter?**

They matter because Storeden interprets migrated data through a hosted commerce environment. Products, customers, orders, inventory, apps, marketplace data, and external identifiers must remain useful inside Storeden, not only appear as imported records.

**Are product variants always migrated into Storeden in the same structure?**

Not always. Source options, variants, attributes, modifiers, custom fields, and configurable products may need different target handling. Complex product samples should be reviewed during Demo Migration before Full Migration.

**Does migrated order history prove that Storeden checkout is ready?**

No. Historical order data can show previous payment, shipping, tax, and tracking context, but live checkout readiness depends on target payment, TS Pay, shipping, tax, logistics, and account configuration.

**What happens to app or API data during a Storeden migration?**

App and API data should be reviewed separately. Standard commerce records may migrate, while app-owned settings, external identifiers, automation logic, marketplace connector data, or TeamSystem integration values may need reconfiguration, mapping, accepted exclusion, or Custom Service review.

**Should marketplace IDs and ERP references be checked during migration?**

Yes. Marketplace IDs, ERP references, accounting identifiers, POS values, fulfillment references, and external customer or order keys can be important for business continuity. They should be included in migration planning when connected workflows depend on them.
