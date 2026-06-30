# Adobe Commerce Data Model Differences

Adobe Commerce migration planning is not only about whether products, customers, orders, categories, CMS Pages, Blog Posts, and reviews can be moved. The larger question is whether those records can support the enterprise operating model that Adobe Commerce is expected to run after launch. Product structure, storefront scope, B2B company relationships, shared catalogs, customer groups, content staging, inventory ownership, URLs, and integrations all change how source data should be interpreted.

A source store can show clean records while still lacking the structure needed for Adobe Commerce. A customer may exist without company authority. A product may exist without the correct attribute set, website assignment, child SKU relationship, or shared catalog visibility. A page may migrate but lose campaign timing, localization, or route meaning. Data model review should therefore focus on business behavior, not only field presence.

### Adobe Commerce Data Meaning Starts With Enterprise Operation <a href="#adobe-commerce-data-meaning-starts-with-enterprise-operation" id="adobe-commerce-data-meaning-starts-with-enterprise-operation"></a>

Adobe Commerce inherits much of the Magento-family data foundation, but the migration interpretation is different because Adobe Commerce is often selected for more governed commerce operations. The same product, customer, order, or page record may need to participate in multi-storefront structure, B2B purchasing, approval rules, customer-group pricing, shared catalog visibility, enterprise integrations, or scheduled content activity.

| Data area             | Adobe Commerce interpretation                                                                                                 | Migration planning implication                                                        |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Products              | Product types, child SKUs, attributes, attribute sets, websites, categories, prices, visibility, and inventory relationships. | Catalog data must support enterprise selling behavior, not only storefront display.   |
| Customers             | Individual buyers, customer groups, company users, addresses, order history, and account authority.                           | Customer data may need to preserve both identity and purchasing context.              |
| Companies             | Company administrators, company users, roles, permissions, credit, quotes, purchase orders, and approval status.              | B2B data should be scoped before treating customers as ordinary accounts.             |
| Shared catalogs       | Buyer-specific catalog visibility and pricing through customer groups or company assignment.                                  | Product existence does not automatically mean product visibility for every buyer.     |
| Storefront scope      | Websites, stores, store views, language, currency, content, configuration, and catalog assignment.                            | Multi-brand, regional, or multilingual data must not be flattened.                    |
| Content and campaigns | CMS Pages, CMS blocks, scheduled updates, promotion timing, landing pages, and campaign assets.                               | Static content migration may not preserve time-sensitive commercial intent.           |
| Inventory             | Sources, stocks, salability assumptions, channel assignment, and external stock ownership.                                    | Quantity should be reviewed in relation to fulfillment structure, not only SKU count. |
| URLs                  | URL keys, rewrites, redirects, localized paths, custom routes, and high-value landing pages.                                  | SEO continuity depends on route meaning and scope, not only page transfer.            |

The practical migration question is whether each record has enough structure to keep working inside Adobe Commerce. Supported records may still require stronger mapping, filtering, preparation, validation, or target-side configuration when they carry enterprise business rules.

### Product Data Depends on Type, Attribute, and Governance Logic <a href="#product-data-depends-on-type-attribute-and-governance-logic" id="product-data-depends-on-type-attribute-and-governance-logic"></a>

Adobe Commerce product migration needs careful interpretation because product data can affect storefront behavior, merchandising, filtering, search, pricing, inventory, and integration workflows. Product type is the first meaning layer. Simple, configurable, grouped, virtual, bundle, and downloadable products do not behave the same way. A source item with options may need to become a configurable product with associated child simple products. A source package or kit may require review before being treated as bundle, grouped, custom-handled, or excluded from standard behavior.

Configurable products are especially important. The parent product gives buyers a single product experience, while child simple products carry purchasable SKU-level meaning. Size, color, material, package size, or technical specification may affect SKU identity, price, image, inventory, and integration references. If those relationships are flattened, the catalog may look complete while purchasing, fulfillment, reporting, or ERP synchronization fails.

Attributes and attribute sets add another governance layer. Attributes may control visible product fields, search, layered navigation, comparison, import/export behavior, promotion conditions, admin maintenance, and integration logic. Attribute sets group product families into structured templates. A source custom field should not automatically become description text if the field drives filtering, pricing, PIM synchronization, search, reporting, or downstream operations.

| Product structure      | What must be interpreted                                                                              | Why it matters in Adobe Commerce                                            |
| ---------------------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Product type           | Simple, configurable, grouped, bundle, virtual, downloadable, or custom-handled structure.            | Product type controls how buyers select and purchase items.                 |
| Child SKU relationship | Parent-child assignment, option labels, images, price differences, stock, and identifiers.            | Broken relationships can make products visible but not commercially usable. |
| Attributes             | Display fields, searchable fields, filterable fields, rule inputs, integration IDs, and admin fields. | Attribute decisions affect catalog governance and buyer discovery.          |
| Attribute sets         | Product-family templates and required fields.                                                         | Poor attribute-set planning makes catalog maintenance hard after migration. |
| Category assignment    | Navigation, merchandising, scope, visibility, and URL behavior.                                       | Wrong category meaning can affect discovery, SEO, and buyer confidence.     |
| Product relationships  | Related products, upsells, cross-sells, accessories, replacements, and compatibility references.      | Relationship loss can weaken conversion and sales workflows.                |

The goal is not to recreate every source field exactly. The goal is to preserve the commercial meaning of the catalog in a form Adobe Commerce can operate, govern, and validate.

### Storefront Scope Changes Record Meaning <a href="#storefront-scope-changes-record-meaning" id="storefront-scope-changes-record-meaning"></a>

Adobe Commerce storefront scope can change the meaning of nearly every migrated record. A source platform may represent brands, regions, languages, B2B portals, retail channels, wholesale areas, and international storefronts through categories, domains, customer tags, markets, plugins, or custom fields. Adobe Commerce may require those distinctions to become websites, stores, store views, category trees, customer groups, shared catalogs, configuration rules, or content variants.

Scope should be planned before detailed mapping. A product name may be global while descriptions vary by store view. A CMS Page may require localized versions. A product may belong to one website but not another. A category path may be valid for a retail storefront but inappropriate for a private B2B catalog. A price may depend on customer group or shared catalog access rather than the product alone.

Scope mistakes are often invisible in record counts. The expected number of products, categories, customers, or pages can migrate while one storefront displays the wrong language, price, category, product visibility, or URL. Review samples should therefore include each important brand, region, language, website, store, store view, B2B segment, and private-catalog context.

### Customer Data May Include Individual Identity and Company Authority <a href="#customer-data-may-include-individual-identity-and-company-authority" id="customer-data-may-include-individual-identity-and-company-authority"></a>

In Adobe Commerce, customer data may represent more than individual account identity. It can include customer groups, company account relationships, company administrators, company users, permissions, quotes, purchase orders, company credit, payment methods, shipping method rules, legal address data, and shared catalog assignment. A customer record can transfer correctly as an individual account while still failing if the buyer loses company authority or catalog access.

B2B migration planning should separate customer identity from purchasing control. A source customer email, address, and order history may be enough for a B2C account, but B2B continuity may require company name, legal address, administrator assignment, user hierarchy, approval status, account manager reference, tax identifiers, credit policy, and external account IDs.

| Customer layer       | What to review                                                                       | Migration implication                                                                 |
| -------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Individual account   | Email, name, address, status, password strategy, and order association.              | Buyers need recognizable customer continuity.                                         |
| Customer group       | Discount, tax, catalog, pricing, or storefront treatment.                            | Group assignment can affect buyer experience and order accuracy.                      |
| Company account      | Company administrator, legal address, company users, hierarchy, and account status.  | Company purchasing may fail if company structure is not planned.                      |
| Purchasing controls  | Quotes, purchase orders, credit, payment methods, shipping methods, and permissions. | B2B workflows may need configuration or Custom Service review.                        |
| External identifiers | ERP ID, CRM ID, dealer ID, account manager reference, contract ID, or tax reference. | External systems may depend on identifiers that are not visible in storefront review. |

Adobe Commerce company data should not be treated as a normal customer field list. It is a purchasing structure. Migration scope should clarify which parts are migrated, which are configured in Adobe Commerce, which require Custom Service, and which belong to external integration work.

### Shared Catalogs Turn Product Access Into Buyer-Specific Data <a href="#shared-catalogs-turn-product-access-into-buyer-specific-data" id="shared-catalogs-turn-product-access-into-buyer-specific-data"></a>

Shared catalogs make Adobe Commerce product access and pricing buyer-specific. A product can exist in the catalog but not be visible to every company. A price can be correct for one customer group and incorrect for another. A category can be appropriate for a public retail store but inappropriate for a private wholesale catalog.

Source platforms often represent this logic in different ways: wholesale price lists, customer tags, dealer groups, hidden categories, private product lists, contract pricing, ERP-driven rules, or custom fields. During migration, these structures need translation rather than simple transfer.

Shared catalog planning should answer four questions: which companies or groups should see which products, which prices apply, which catalog assignments must be preserved, and which visibility rules should be rebuilt in Adobe Commerce. Some source data may fit supported mapping. Some may require Add-ons for supported mapping or filtering. Unsupported pricing logic, custom access rules, or external catalog ownership may require Custom Service or target-side configuration.

### Orders Carry Commercial, B2B, and Integration Context <a href="#orders-carry-commercial-b2b-and-integration-context" id="orders-carry-commercial-b2b-and-integration-context"></a>

Order migration into Adobe Commerce should preserve useful history, not imply that every source checkout behavior becomes live Adobe Commerce behavior. Historical orders can include line items, products, quantities, discounts, taxes, shipping, billing, customer references, order statuses, payment references, refunds, invoices, shipments, credit memos, purchase orders, quote references, company context, and external IDs.

For B2B and enterprise stores, order history may need additional interpretation. A source order may belong to a company rather than only an individual customer. A historical discount may reflect a contract price or shared catalog price. A payment method may depend on company rules. A purchase order may have approval meaning. An ERP order number may be more important than the storefront order number for support teams.

| Order context                     | What to preserve or classify                                                                   | Why it matters                                                                  |
| --------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Customer and company relationship | Buyer account, company account, administrator or user relationship, and group context.         | Support teams need to understand who placed the order and under which account.  |
| Financial detail                  | Subtotal, discounts, taxes, shipping, refunds, credit memos, invoices, and payment references. | History must remain readable for service and reconciliation.                    |
| B2B workflow context              | Quote, purchase order, account credit, approval, or contract reference.                        | Historical B2B meaning may not be ordinary order data.                          |
| Fulfillment status                | Shipment, partial fulfillment, cancellation, return, warehouse reference, or ERP status.       | Operations need to interpret what happened after purchase.                      |
| External identifiers              | ERP order ID, accounting ID, marketplace ID, CRM opportunity, or warehouse reference.          | Integration continuity may depend on identifiers outside standard order fields. |

Order data should be validated through representative samples, not only totals. The sample set should include B2C orders, B2B orders, refunded orders, discounted orders, tax-sensitive orders, orders with external references, and orders connected to company or customer group context where relevant.

### Content, Campaigns, and URLs Need Separate Interpretation <a href="#content-campaigns-and-urls-need-separate-interpretation" id="content-campaigns-and-urls-need-separate-interpretation"></a>

Adobe Commerce content migration can include CMS Pages, CMS blocks, category content, product descriptions, landing pages, Blog Posts when relevant, media, metadata, and promotional assets. For enterprise stores, content may also connect to campaign timing, regional storefronts, merchandising calendars, brand governance, legal review, or approval workflows.

Content Staging changes how content should be interpreted when timed updates matter. A landing page, category banner, product promotion, or scheduled price change may exist as content but still lose its launch timing if migrated as static text. The migration plan should separate evergreen content, launch-critical content, time-sensitive campaign content, and expired content.

URLs require similar separation. Product URL keys, category URL keys, CMS paths, URL rewrites, localized paths, redirects, and custom landing-page routes should be reviewed by business value. A page count may pass while high-value product pages, B2B entry paths, dealer portals, regional URLs, or campaign pages lose continuity.

### Integration-Owned Data Must Be Identified Before Mapping <a href="#integration-owned-data-must-be-identified-before-mapping" id="integration-owned-data-must-be-identified-before-mapping"></a>

Adobe Commerce projects often depend on ERP, PIM, CRM, OMS, WMS, tax, payment, shipping, marketplace, loyalty, subscription, analytics, search, personalization, or marketing systems. These systems may own fields and identifiers that are not obvious in storefront review.

Examples include ERP product IDs, PIM product IDs, company account IDs, dealer IDs, contract IDs, price-list references, warehouse stock codes, tax exemption IDs, CRM account references, marketplace item IDs, subscription IDs, and external order numbers. If these are removed, renamed, or placed in unsupported fields, the migrated store can look correct while downstream workflows fail.

Integration-owned data should be classified before choosing the final migration path. Supported fields may migrate through standard behavior. Supported mapping or filtering needs may fit Add-ons. Unsupported extension data, bespoke transformation, external identifiers, custom database structures, or nonstandard target behavior should be reviewed for Custom Service.

### Adobe Commerce Data Review Should End With Usability Criteria <a href="#adobe-commerce-data-review-should-end-with-usability-criteria" id="adobe-commerce-data-review-should-end-with-usability-criteria"></a>

Adobe Commerce data model review should end with acceptance criteria that show the migrated data is usable. Product records should support catalog governance. Customer records should support account continuity and company purchasing where relevant. Orders should preserve serviceable history. Content should support launch and campaign needs. URLs should support traffic continuity. Integration fields should remain interpretable.

A useful data review asks:

* Can products be maintained by product family, attribute set, website, and storefront scope?
* Can B2B buyers access the right catalog, price, account, quote, purchase order, and credit context?
* Can support teams read historical orders without returning to the source system for basic meaning?
* Can content and URLs support launch, SEO continuity, and campaign requirements?
* Can external systems still recognize the migrated records they depend on?

If those questions cannot be answered from the migration scope, the data model is not ready for Full Migration.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce changes migration planning because data often carries enterprise operating logic. Products are not only items; they are product types, attributes, attribute sets, websites, store views, categories, inventory relationships, and integration references. Customers are not only profiles; they may be companies, users, administrators, customer groups, shared catalog buyers, and approval participants. Content, URLs, orders, and inventory may depend on scope, timing, and external systems.

A strong Adobe Commerce migration treats data model review as business-meaning translation. The goal is to land records in a structure that can support catalog governance, B2B purchasing, storefront scope, content continuity, integration ownership, and launch validation.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why does Adobe Commerce data migration require more than field mapping?**

Because many Adobe Commerce records carry operational meaning. Products, customers, orders, content, URLs, and inventory can affect B2B purchasing, shared catalogs, storefront scope, attribute governance, integrations, and validation responsibility.

**How are Adobe Commerce shared catalogs different from ordinary categories?**

Categories organize catalog navigation and merchandising. Shared catalogs can control buyer-specific product visibility and pricing, usually in relation to companies or customer groups. They should be planned as access and pricing logic, not only catalog structure.

**What makes customer data more complex in Adobe Commerce?**

Customer data may include individual accounts, customer groups, company accounts, company users, administrators, roles, credit, quote permissions, purchase order permissions, and shared catalog assignments. A customer can migrate as an account while still losing B2B purchasing meaning.

**Should Content Staging data be treated as normal CMS content?**

No. Time-sensitive campaign updates, scheduled content, promotional pages, and launch-specific changes should be reviewed separately. Some content may migrate as stable CMS content, while timing and approval behavior may need Adobe Commerce configuration or manual rebuild.

**When does Adobe Commerce data require Custom Service review?**

Custom Service should be reviewed when the scope includes unsupported extension data, custom fields, external identifiers, bespoke transformation, custom database structures, Custom Platform behavior, or custom migration logic beyond supported records and bounded Add-ons.
