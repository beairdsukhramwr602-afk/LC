# CS-Cart Data Model Differences

A CS-Cart migration is not only a transfer of Products, Customers, Orders, Categories, Reviews, Coupons, CMS Pages, and other records. The more important question is how those records will behave after they become part of CS-Cart’s catalog, storefront, customer, vendor, and administration structure. A product that looked simple in the source store may depend on options, features, downloadable files, vendor ownership, category placement, image handling, or external inventory control. A customer account may represent a retail buyer, a B2B buyer, a vendor administrator, or a user group member. An order may be ordinary sales history or a record that needs vendor, payout, fulfillment, tax, and integration context to remain useful.

This distinction matters because CS-Cart can support different commerce patterns. It may be used as a single-seller online store, a marketplace through Multi-Vendor, a B2B/B2C selling environment, or a customized commerce implementation. The same source data can therefore require different interpretation depending on the future operating plan. Migration quality depends on whether the data is translated into the right CS-Cart meaning, not only whether the record count appears complete.

### How CS-Cart Changes Source Data Meaning <a href="#how-cs-cart-changes-source-data-meaning" id="how-cs-cart-changes-source-data-meaning"></a>

CS-Cart uses familiar commerce records, but it gives them specific structural roles. Products sit inside a catalog that may include product codes, prices, list prices, inventory quantities, statuses, images, categories, features, options, downloadable files, and variation-style buying paths. Categories form the browsing structure and can influence which features remain available. Vendors, where Multi-Vendor is used, are not simple labels; they represent independent companies with their own administration context. Import and export may use CSV, but CSV transfer does not remove the need to interpret how each field should be used after migration.

A useful data-model review starts by asking what each source record means commercially. Some data should become native CS-Cart configuration. Some data should become migrated content. Some should be cleaned before migration. Some should be reviewed through Add-ons or Custom Service because it belongs to app logic, custom fields, external systems, or marketplace-specific behavior.

| Source data area          | What may look simple                                        | CS-Cart interpretation to confirm                                                                                                              |
| ------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Products                  | SKU, name, price, image, quantity, status                   | Whether the product remains buyable, visible, categorized, searchable, correctly priced, and tied to the right vendor or storefront context.   |
| Categories                | A list of departments or menu items                         | Whether the category tree supports navigation, feature availability, SEO routes, product assignment, and marketplace catalog control.          |
| Product features          | Attributes, specifications, filters, brand fields           | Whether they should become inseparable product properties, comparison data, filtering signals, or internal-only fields.                        |
| Product options           | Size, gift wrap, warranty, engraving, configuration choices | Whether they are separable choices that affect price or weight without separate stock, or whether they need a different target-side structure. |
| Vendors                   | Seller, supplier, brand, warehouse, department              | Whether the source value should become marketplace ownership, vendor administration context, or only descriptive metadata.                     |
| Customers and user groups | Buyers, members, wholesalers, staff, vendors                | Whether the account carries pricing, access, approval, role, or marketplace meaning.                                                           |
| Orders                    | Historical purchases and statuses                           | Whether order records need vendor, shipment, payment, tax, discount, refund, and integration meaning for service and reporting.                |
| Add-ons and custom data   | Extra fields, app tables, scripts, module behavior          | Whether the data is standard, configurable, add-on dependent, or requires Custom Service interpretation.                                       |

The goal is not to make every source field visible in CS-Cart. The goal is to preserve usable business meaning while avoiding clutter, duplicate logic, broken buying paths, and unsupported assumptions.

### Product, Feature, Option, and Variation Meaning <a href="#product-feature-option-and-variation-meaning" id="product-feature-option-and-variation-meaning"></a>

Product data is the most visible part of a CS-Cart migration, but it is also one of the easiest areas to misread. A product record can include identity, buying logic, merchandising, inventory, media, category placement, digital delivery, filtering information, vendor ownership, and external identifiers. Treating all product-related fields as one flat group can make the migrated catalog technically present but commercially confusing.

CS-Cart product records commonly need to preserve names, product codes, prices, list prices, quantities, statuses, images, and product editing context. That does not mean every source field maps directly. The source may use attributes for buying choices, options for specifications, categories for internal reporting, SKUs without uniqueness discipline, or custom fields that are only meaningful to staff. These differences should be identified before Full Migration because they affect storefront usability.

#### Products need commercial identity, not only record presence <a href="#products-need-commercial-identity-not-only-record-presence" id="products-need-commercial-identity-not-only-record-presence"></a>

A migrated product should answer basic buyer questions: What is it, can I buy it, what does it cost, what choices do I have, is it available, and where does it belong in the catalog? If those answers are scattered across inconsistent source fields, the target catalog may need cleanup or mapping decisions before migration.

Product code discipline also deserves attention. Some source stores treat SKU-like fields as optional, duplicated, or internal. CS-Cart can display and manage product codes, but poor source discipline can still create search, reporting, fulfillment, or integration confusion after migration. Duplicate or missing codes should be identified as a data-quality issue, not hidden behind a successful transfer count.

#### Features are not the same as options <a href="#features-are-not-the-same-as-options" id="features-are-not-the-same-as-options"></a>

CS-Cart features are additional inseparable product properties. They help describe products and can support comparison, filtering, and product information. A feature might represent brand, ISBN, material, compatibility, size specification, color family, technical rating, or another descriptive property. When source attributes are migrated without interpretation, internal notes or inconsistent values may become customer-facing clutter.

Options serve a different purpose. CS-Cart options are additional separable product properties that do not have their own quantity and do not affect stock, though they may affect price or weight. Examples include custom engraving, gift wrap, or extended warranty. This distinction is important because some source platforms mix sellable choices, specifications, and modifiers under one attribute system.

| Source-side pattern                                       | Better CS-Cart reading                          | Migration concern                                                                                                |
| --------------------------------------------------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Technical specifications                                  | Product features                                | Values should be normalized enough to support comparison and filtering.                                          |
| Gift wrap, warranty, engraving, service add-on            | Product options                                 | The option should not be treated as a separate stock-managed product unless the business requires that behavior. |
| Size or color choices with separate inventory needs       | Variation or product-structure review           | A simple option may not preserve stock and purchasing expectations.                                              |
| Brand, model, compatibility, material                     | Feature, feature group, or searchable attribute | Inconsistent source labels can weaken filtering and search.                                                      |
| Internal warehouse, supplier, margin, or purchasing notes | Internal reference or Custom Service review     | Staff-only data should not automatically become storefront product information.                                  |
| App-created merchandising fields                          | Add-ons or Custom Service review                | The target behavior must be confirmed before assuming a direct field mapping.                                    |

When product structure is unclear, the migration should use representative Demo Migration samples. The sample should include simple products, configured products, products with feature-heavy descriptions, products with options that change price or weight, and products with stock-sensitive choices.

### Category and Storefront Data Meaning <a href="#category-and-storefront-data-meaning" id="category-and-storefront-data-meaning"></a>

Categories in CS-Cart are not just folders. They form a tree that helps customers browse products, and every product in the catalog must be assigned to at least one category. Category decisions can also affect feature availability. This makes category migration a storefront-architecture decision, not only a record-transfer task.

A source category tree may contain active navigation, internal reporting groups, temporary campaign pages, brand groupings, vendor catalog sections, archived departments, or SEO landing pages. Migrating all of them without review can preserve confusion. The target category structure should make products easier to find, not merely reproduce old catalog clutter.

#### Category translation should protect navigation and product assignment <a href="#category-translation-should-protect-navigation-and-product-assignment" id="category-translation-should-protect-navigation-and-product-assignment"></a>

The first category question is whether each source category should remain visible in CS-Cart. Some categories are important buying paths. Some exist only because the old platform needed technical grouping. Some are outdated. Some categories should remain for SEO continuity but not be featured prominently in menus. Some belong to vendor-specific marketplace organization.

The second question is how products should be assigned. Because every product needs at least one category, missing or invalid category mapping can create launch issues even when product records are present. Products with many unrelated category assignments also deserve review because they can weaken browsing logic and create confusing storefront paths.

| Category issue                                       | Why it matters in CS-Cart                                                       | Handling direction                                                                               |
| ---------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Products with no valid category                      | Products may be present but poorly discoverable or blocked from clean browsing. | Prepare category mapping before migration and test representative products after Demo Migration. |
| Internal categories mixed with storefront navigation | Customers may see staff-only or obsolete structure.                             | Separate customer-facing categories from internal classification.                                |
| Deep or duplicated category trees                    | Browsing becomes difficult and URL review becomes harder.                       | Consolidate where appropriate before or during migration planning.                               |
| Category-specific feature behavior                   | Moving products can affect available features.                                  | Test products that rely on category-driven feature availability.                                 |
| Marketplace category ownership                       | Vendor products may need correct placement and governance.                      | Confirm whether vendors can use, request, or manage category placement.                          |

Category and storefront data also affects CMS Pages, Blog Posts, navigation blocks, vendor pages, brand pages, and SEO routes. These records should be reviewed by business importance. A high-value landing page deserves more attention than an old informational page with no traffic or conversion role.

### Vendor, Marketplace, and Account Data Meaning <a href="#vendor-marketplace-and-account-data-meaning" id="vendor-marketplace-and-account-data-meaning"></a>

Vendor data is one of the most important CS-Cart-specific differences. In Multi-Vendor, vendors are independent companies that sell their own products and have separate administration context. A vendor can manage its own settings and products, configure shipping methods, and work with sales, orders, earnings, and payout balance. That means vendor data is not equivalent to a supplier name or brand label.

If the source platform used seller, supplier, warehouse, brand, manufacturer, franchise, branch, or department fields, each field should be interpreted carefully. Some values may belong in product features. Some may belong in manufacturer-style descriptive data. Some may need vendor ownership. Some may only be reporting references. Choosing the wrong interpretation can damage marketplace operations after launch.

#### Vendor ownership changes product and order meaning <a href="#vendor-ownership-changes-product-and-order-meaning" id="vendor-ownership-changes-product-and-order-meaning"></a>

A marketplace product is not only a product. It has ownership, visibility, responsibility, and administration implications. If a product is assigned to the wrong vendor, the marketplace may experience incorrect catalog control, seller reporting confusion, fulfillment mistakes, customer-service delays, or payout disputes.

Vendor meaning also appears in orders. Historical order records may need to show which vendor was responsible, how fulfillment was handled, and how staff should interpret the order after launch. Even when historical payout data is not fully recreated, the order should remain understandable for support, reconciliation, and customer history.

| Marketplace data question                        | Why it matters                                                                        | Evidence to prepare                                                       |
| ------------------------------------------------ | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| What source field identifies the seller?         | Seller identity may be stored as vendor, supplier, brand, warehouse, or custom field. | Source export samples, admin screenshots, seller lists, product examples. |
| Does seller identity affect fulfillment?         | Vendor assignment may influence shipping responsibility and order handling.           | Vendor shipping examples, order samples, fulfillment rules.               |
| Does seller identity affect catalog approval?    | Marketplace governance may require review before products go live.                    | Product approval examples, vendor onboarding requirements.                |
| Does seller identity affect payments or payouts? | Financial context may not be ordinary order data.                                     | Payout reports, commission references, accounting exports.                |
| Do vendors have staff accounts?                  | Vendor administrators should not be merged with ordinary customers.                   | Vendor admin samples, role notes, access requirements.                    |

Customer and account data also needs interpretation. CS-Cart user groups can influence access and commercial behavior. A customer may be a retail buyer, wholesale buyer, approved B2B account, marketplace buyer, vendor staff member, or administrator. Source systems often mix these ideas. Migration planning should prevent account types from collapsing into one generic customer list when the business depends on role separation.

### Order, Payment, Shipping, Tax, and Historical Context <a href="#order-payment-shipping-tax-and-historical-context" id="order-payment-shipping-tax-and-historical-context"></a>

Order migration should preserve history that the business can use. A CS-Cart order is valuable not only because it records that a purchase happened, but because it supports customer service, reporting, fulfillment review, accounting checks, and sometimes marketplace operations. If source order history includes vendor splits, partial shipments, tax adjustments, discounts, payment references, refunds, or external identifiers, those elements should be reviewed before they are treated as ordinary order fields.

Historical orders rarely recreate every source-side operational process exactly. The practical question is whether staff can understand the migrated record. A support agent should know what the customer bought, when they bought it, which address was used, what status the order had, which payment and shipping references matter, and which vendor or external system was involved if applicable.

#### Order data should remain interpretable <a href="#order-data-should-remain-interpretable" id="order-data-should-remain-interpretable"></a>

Some source stores contain old status names, custom payment states, fulfillment notes, abandoned orders, test orders, imported marketplace orders, or ERP-managed order references. These records should be filtered, mapped, or annotated according to business value. Carrying every record without interpretation can make the order archive harder to use.

| Order data element       | Migration interpretation question                                       | Risk if ignored                                                          |
| ------------------------ | ----------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Status history           | Which statuses need to remain meaningful in CS-Cart?                    | Staff may misread pending, paid, shipped, refunded, or cancelled orders. |
| Payment references       | Which identifiers are needed for lookup or reconciliation?              | Accounting and support teams may lose traceability.                      |
| Shipping references      | Which carrier, tracking, fulfillment, or vendor data matters?           | Fulfillment review may become incomplete.                                |
| Discounts and promotions | Are old coupons needed as active rules or historical evidence only?     | Old promotion logic may be mistaken for target-side behavior.            |
| Tax data                 | Is tax needed for history, reporting, or future calculation rules?      | Historical totals may be confusing if tax context is lost.               |
| Vendor context           | Did a vendor own or fulfill the order?                                  | Marketplace history may lose operational meaning.                        |
| External identifiers     | Does ERP, CRM, accounting, marketplace, or support software use the ID? | Integrations may lose matching references.                               |

Order history is also a good place to test data scope. If the merchant does not need every legacy order, Data Filter Add-on planning may help keep the migration focused. If the order records carry custom fields, external identifiers, or marketplace relationships beyond standard handling, Custom Service may be needed.

### Add-On, Storefront, and Integration-Owned Data <a href="#add-on-storefront-and-integration-owned-data" id="add-on-storefront-and-integration-owned-data"></a>

CS-Cart stores often rely on add-ons, storefront configuration, themes, external systems, or custom development. This data can be difficult because it may not look separate to business users. A discount rule may be controlled by an add-on. A checkout field may come from a customization. A product badge may be theme-driven. A vendor report may come from marketplace configuration. An ERP identifier may be stored in a custom product field.

Migration planning should identify ownership before mapping. If a field or behavior belongs to a source extension, module, custom table, or external system, it should not automatically be treated as native CS-Cart data. It may need Advanced Data Mapping, Advanced Data Configure, a Standard Add-on, a Tailored Add-on, a Custom Add-on, or Custom Service depending on the requirement.

#### Storefront data must be separated from operational behavior <a href="#storefront-data-must-be-separated-from-operational-behavior" id="storefront-data-must-be-separated-from-operational-behavior"></a>

CMS Pages, Blog Posts, navigation content, banners, layouts, and theme-managed elements are not the same as core commerce records. Some content can be migrated as content. Some should be rebuilt in the target theme. Some should be reviewed for SEO value. Some may be outdated and should not be carried into the new store.

| Data source             | Typical meaning                                                                       | Migration decision                                                                    |
| ----------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Built-in CS-Cart fields | Native product, category, customer, order, or content information                     | Plan through Standard Service when the data type is supported and structurally clear. |
| Source add-on fields    | Behavior created by apps, extensions, modules, or plugins                             | Review target-side equivalent through Add-ons or Custom Service.                      |
| Theme/layout data       | Presentation rules, blocks, banners, templates, visual placements                     | Decide what should be rebuilt rather than migrated as ordinary content.               |
| External system data    | ERP, CRM, accounting, tax, shipping, fulfillment, marketplace, or support identifiers | Preserve identifiers only when their target-side use is defined.                      |
| Custom source logic     | Non-standard tables, custom fields, private APIs, bespoke scripts                     | Review through Custom Service before promising a native mapping.                      |

This is where a migration can appear complete but still feel incomplete after launch. The store may contain products, customers, orders, and categories, yet miss the behavior that made the source business operate. Clear ownership prevents this mismatch.

### Storefront, Common Product, and Channel Meaning <a href="#storefront-common-product-and-channel-meaning" id="storefront-common-product-and-channel-meaning"></a>

CS-Cart data may also need to support more than one storefront or sales context. A product can be commercially correct in one storefront and poorly positioned in another if categories, descriptions, prices, images, feature values, SEO routes, or availability rules were inherited without review. Source platforms sometimes use separate stores, language views, sales channels, customer groups, or marketplace feeds to describe what should be shown to different audiences. Those differences should be translated into target-side storefront and governance decisions rather than being flattened into one generic catalog.

Common product planning is especially important when the merchant wants shared catalog governance with different storefront or vendor presentation rules. The migration should clarify which product information is central, which information may vary by storefront, which content is channel-specific, and which fields exist only because the source platform handled merchandising in a different way. Without that review, the target store may look complete in the admin area but fail to support the way buyers actually browse and compare products.

| Storefront data question                                               | Why it changes the data model                                                                        | Migration planning response                                                 |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Does the product appear in more than one storefront or channel?        | The product may need shared identity with different visibility, category, or presentation decisions. | Identify shared product fields separately from storefront-specific content. |
| Are descriptions, images, or prices localized or segmented?            | A single source product may contain several audience-specific meanings.                              | Decide which values should be migrated, rebuilt, localized, or excluded.    |
| Are vendor products shown differently from marketplace-level products? | Marketplace presentation may depend on seller ownership and central governance.                      | Review vendor and category rules together rather than separately.           |
| Are some products used only for feeds or external channels?            | Channel data may not belong on the storefront.                                                       | Preserve only fields that have a defined target-side use.                   |

This is also where CMS Pages, Blog Posts, category landing pages, and vendor pages should be reviewed by role. A page that supports SEO, buyer education, or marketplace trust should be treated differently from a legacy page that no longer supports the business.

### Data Translation Rules for CS-Cart Migration <a href="#data-translation-rules-for-cs-cart-migration" id="data-translation-rules-for-cs-cart-migration"></a>

A CS-Cart data-model review should end with rules that guide scope. These rules help decide what belongs in standard migration, what needs cleanup, what requires Add-ons, and what should be handled as Custom Service.

| Translation rule                                   | Practical meaning                                                                  | Review trigger                                                                 |
| -------------------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Preserve commercial meaning before visual sameness | The target record should support buying, service, reporting, and management.       | Any field that changes how a buyer or staff member acts.                       |
| Separate features from options                     | Specifications and separable choices should not be merged.                         | Attributes that mix filtering, pricing, and buying choices.                    |
| Treat vendor ownership as structural               | Marketplace sellers are not ordinary descriptive metadata.                         | Any source seller/supplier/vendor field that affects ownership or fulfillment. |
| Keep category mapping intentional                  | Product assignment, navigation, and SEO routes depend on category decisions.       | Deep, duplicated, obsolete, or internal category trees.                        |
| Distinguish history from active behavior           | Old orders and coupons may need historical visibility, not active reconfiguration. | Promotions, statuses, payment references, and tax rules.                       |
| Identify add-on and custom ownership               | Extended behavior may not be ordinary data.                                        | Source apps, custom fields, integrations, and modified database structures.    |
| Use migration scope as a business decision         | Not every record deserves equal priority.                                          | Old records, low-value content, obsolete products, and messy archives.         |

These rules should be applied before the merchant approves the migration scope. They reduce the chance of carrying source-side confusion into CS-Cart.

#### Data scope should follow future use <a href="#data-scope-should-follow-future-use" id="data-scope-should-follow-future-use"></a>

Not every source record deserves the same treatment. A retired product, an obsolete category, a test customer, an abandoned cart, an outdated coupon, or an old CMS Page may be technically movable but commercially unhelpful. CS-Cart migration scope should therefore separate must-preserve records from low-value archive data. This is especially important for stores that are using migration as a cleanup opportunity rather than a one-to-one copy of old operations.

Entity Points planning should be read through that lens. Eligible new Products, Customers, Orders, and Blog Posts consume Entity Points when they are first migrated, but records already counted through the service license do not consume again simply because another action happens on the same migration path. That means scope review should focus on which records are worth migrating, not on duplicating old clutter just because it exists in the source.

### Conclusion <a href="#conclusion" id="conclusion"></a>

CS-Cart data-model differences are concentrated in the way familiar records gain platform-specific meaning. Products must remain buyable and discoverable. Features and options must be separated. Categories must support browsing and product assignment. Vendors must be treated as marketplace structure where Multi-Vendor is involved. Customers and user groups must preserve account meaning. Orders must remain interpretable for service, reporting, and operational review. Add-on, storefront, and integration-owned data must be identified before it is mistaken for standard record migration.

A strong CS-Cart migration does not ask only whether data can be moved. It asks how each source record should behave in the future CS-Cart store or marketplace. That is the difference between a complete-looking transfer and a usable Target Platform.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are CS-Cart features and options treated separately during migration?**

Features describe products as inseparable properties, while options are separable choices that can affect price or weight without their own stock. Mixing them can create poor filtering, confusing product pages, or incorrect buying behavior.

**Do all source product attributes become CS-Cart features?**

No. Some attributes may become features, some may become options, some may need cleanup, and some may be internal-only or custom data. The correct treatment depends on how the field affects buying, filtering, comparison, reporting, or administration.

**Why does vendor data require special review in CS-Cart migration?**

In Multi-Vendor, vendors are independent companies with separate administration context. Seller identity can affect product ownership, order interpretation, shipping responsibility, vendor staff access, earnings, and marketplace governance.

**Can CS-Cart import/export replace data-model planning?**

No. CSV import and export help move structured data, but they do not decide whether a source field should become a feature, option, vendor relationship, internal note, add-on behavior, or custom mapping.

**When should custom source fields be reviewed through Custom Service?**

Custom Service should be reviewed when the source store contains non-standard tables, custom fields, app-owned data, private APIs, external identifiers, marketplace transformations, or business logic that cannot be interpreted as standard CS-Cart records.
