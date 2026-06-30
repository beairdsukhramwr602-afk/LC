---
metaLinks:
  alternates:
    - /broken/spaces/EwOn3si2UOVRL65zVOMg/pages/luwYOn6Ufwa8n5aXiApj
---

# Magento Platform Overview

Magento Open Source is a flexible, implementation-owned commerce Target Platform for merchants that need more catalog control, scope control, and extensibility than a tightly managed hosted storefront usually provides. A Magento migration is not only a transfer of Products, Customers, Orders, Categories, CMS Pages, Blog Posts, images, URLs, and other records. It is a move into an environment where product types, attributes, attribute sets, websites, stores, store views, customer groups, inventory behavior, URL rewrites, modules, integrations, hosting, and custom development can all affect whether migrated data becomes usable after launch.

That flexibility is Magento’s strength, but it also raises the planning standard. A source product that looks like a flat item may need to become a Magento simple product, configurable relationship, grouped product, bundle product, virtual product, or downloadable product. A source field may become a useful attribute, a storefront filter, an internal admin field, a search input, a reporting signal, or a value that should be excluded. A category path may affect navigation, URL continuity, and product discovery. A customer group may influence discounts or tax behavior. A module may own data that does not belong to ordinary platform records.

The right Magento plan therefore starts with meaning, not counts. The merchant should not ask only whether records can move into Magento. The better question is whether those records can support the catalog structure, storefront scope, operational workflows, and maintenance responsibilities the business expects from Magento Open Source.

### Magento Open Source as a Migration Environment <a href="#magento-open-source-as-a-migration-environment" id="magento-open-source-as-a-migration-environment"></a>

Magento Open Source belongs to the Magento-family commerce architecture, but it should be planned as its own Target Platform. It gives merchants control over implementation, extensions, custom development, hosting, catalog modeling, store hierarchy, and data presentation. That control can support complex commerce needs, but it also means the migration cannot be separated from target setup and future ownership.

For migration planning, Magento Open Source usually creates six early decision areas:

| Planning area                | Magento Open Source implication                                                                                       | Early decision                                                                                                 |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Catalog model                | Products may need to become simple, configurable, grouped, bundle, virtual, or downloadable structures.               | Which source product patterns should map to Magento product types and which need review.                       |
| Attribute governance         | Attributes can affect product pages, filtering, search, comparison, reports, promotions, and internal classification. | Which source fields should become Magento attributes and which should be cleaned, merged, hidden, or excluded. |
| Store hierarchy              | Websites, stores, and store views can affect localization, root categories, content, URLs, and configuration scope.   | Which values are global and which vary by storefront, language, brand, or region.                              |
| Customer and pricing context | Customer groups can affect discounts and tax class relationships.                                                     | Whether customer grouping has commercial meaning that should be preserved.                                     |
| URL and content continuity   | Product, category, CMS Page, Blog Posts, and custom route behavior may affect SEO and traffic continuity.             | Which high-value URLs and content areas must be migrated, redirected, rebuilt, or retired.                     |
| Extension and custom data    | Modules and external systems may own fields, behaviors, or identifiers outside standard records.                      | Which requirements fit supported scope, Add-ons, Custom Service, or target-side implementation.                |

These decisions shape every later migration choice. Magento can receive data, but Magento cannot make source assumptions meaningful automatically. A product relationship, attribute value, store-view field, or customer group should be accepted only when the target meaning is clear.

### Why Magento Requires Stronger Catalog Planning <a href="#why-magento-requires-stronger-catalog-planning" id="why-magento-requires-stronger-catalog-planning"></a>

Magento catalog planning is deeper than product import. Magento product types carry structure, inventory meaning, option behavior, and storefront expectations. Simple products are not just ordinary product rows. They can be standalone items or associated products behind configurable, grouped, or bundle structures. Configurable products appear as one product with selectable options, but the options represent associated simple products with distinct SKUs. Bundle products allow the shopper to build from groups of options. Downloadable and virtual products carry different commercial expectations from physical products.

That structure matters during migration because many Source Platforms store product choices differently. A hosted SaaS platform may use variants. A custom platform may use option tables. A WooCommerce store may use variable products and plugin fields. A legacy cart may store custom options as text. A Magento target needs those patterns interpreted before Full Migration.

| Source product pattern                             | Magento planning question                                                | Migration risk if ignored                                                         |
| -------------------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| Flat product with one SKU                          | Should it become a simple product?                                       | Low risk if price, inventory, tax, image, and category data are clean.            |
| Product with size or color choices                 | Should it become a configurable product with associated simple products? | Inventory and SKU-level reporting may be weakened if options are flattened.       |
| Kit or build-your-own product                      | Is bundle structure, custom setup, or Custom Service review needed?      | Component meaning, pricing, and inventory expectations may fail.                  |
| Service, warranty, membership, or nonphysical item | Is virtual product behavior appropriate?                                 | A physical-product assumption may create checkout or fulfillment confusion.       |
| Digital product                                    | Is downloadable product data supported and available?                    | File delivery or link expectations may need target-side setup or custom handling. |
| Extension-generated choice                         | Is the data supported, custom, or owned by a module?                     | Standard mapping may miss the business rule behind the choice.                    |

Good Magento catalog planning protects both storefront experience and admin maintenance. The goal is not to recreate the old platform exactly. The goal is to build a Magento catalog that preserves business meaning in a structure the target environment can support.

### Attribute Governance Is Central to Magento Quality <a href="#attribute-governance-is-central-to-magento-quality" id="attribute-governance-is-central-to-magento-quality"></a>

Attributes are one of Magento’s most important migration concerns. They can be visible to customers, used in product pages, made searchable, included in layered navigation, used for comparison, connected to merchandising, included in reports, or kept as internal admin information. That power makes poor attribute migration especially risky.

A source store may contain duplicate colors, inconsistent sizes, supplier codes, option labels, old filters, SEO keywords, internal notes, PIM IDs, marketplace fields, and extension-created values. If every field becomes a Magento attribute without review, the result may create noisy filters, confusing product pages, weak search quality, and a harder admin experience. If too few fields are preserved, the merchant may lose product discovery, compatibility filtering, reporting, or integration continuity.

A strong Magento migration plan should classify attributes before migration:

| Attribute type                | Typical Magento value                                                     | Planning action                                                         |
| ----------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Customer-facing specification | Product detail, comparison, or filter value.                              | Preserve and normalize values where useful.                             |
| Variant-driving option        | Size, color, material, package, or other selectable product relationship. | Confirm whether it supports configurable products or another structure. |
| Internal classification       | Admin search, merchandising, or reporting field.                          | Preserve if it supports operations; hide from storefront if needed.     |
| Integration identifier        | ERP, PIM, marketplace, warehouse, or accounting reference.                | Review mapping, Add-ons, or Custom Service depending on support.        |
| Legacy noise                  | Duplicate, obsolete, inconsistent, or abandoned source field.             | Clean, merge, exclude, or document as intentionally not migrated.       |

Attribute sets also require planning. They help organize which attributes belong to which product families. A parts catalog, apparel catalog, furniture catalog, and digital-product catalog may not need the same attribute structure. Migration planning should avoid one uncontrolled attribute set that carries every source field without discipline.

### Store Scope Affects More Than Language <a href="#store-scope-affects-more-than-language" id="store-scope-affects-more-than-language"></a>

Magento’s website, store, and store-view hierarchy can be powerful for merchants with multiple storefronts, languages, brands, regions, or localized content. It also creates migration risk when source data is not scoped clearly.

A store view may support a different locale, but scope can affect far more than translated labels. Product names, descriptions, URL keys, metadata, categories, CMS Pages, Blog Posts, visibility, prices, and configuration assumptions may vary across storefront contexts. If those values are migrated without a scope plan, one language can overwrite another, localized URLs can be lost, or storefront-specific content can appear in the wrong place.

Magento scope planning should answer:

| Scope question                                                       | Why it matters                                                      |
| -------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Which websites, stores, and store views will exist after launch?     | The target hierarchy determines where migrated values should apply. |
| Which product fields vary by language, brand, or region?             | Global values and store-view values should not be mixed.            |
| Which categories and root categories support each storefront?        | Navigation and product discovery may differ by store.               |
| Which CMS Pages and Blog Posts are localized or storefront-specific? | Content migration may require scope-aware review.                   |
| Which URLs and redirects are scope-sensitive?                        | SEO continuity can fail if route ownership is unclear.              |

This is where Magento differs from simpler target environments. A complete product record is not necessarily a correct product record if it appears under the wrong store view or inherits the wrong global value.

### Magento and Adobe Commerce Should Not Be Blurred <a href="#magento-and-adobe-commerce-should-not-be-blurred" id="magento-and-adobe-commerce-should-not-be-blurred"></a>

Magento Open Source and Adobe Commerce share important architectural foundations, but they should not be treated as interchangeable migration destinations. Magento Open Source is the right focus when the merchant wants the open-source Magento foundation and is prepared to own hosting, development, extension selection, configuration, and implementation decisions. Adobe Commerce becomes a different planning conversation when enterprise features, licensing, B2B capabilities, shared catalogs, company accounts, Content Staging, advanced governance, or managed cloud assumptions are part of the target expectation.

This distinction matters because some Adobe Commerce features should not be implied in a Magento Open Source migration. If a merchant expects B2B company-account workflows, shared catalog pricing, enterprise governance, or advanced staging behavior, the plan should confirm whether Adobe Commerce is actually the selected Target Platform. Magento Open Source content should not promise enterprise-layer behavior that belongs to Adobe Commerce.

The safer editorial and planning rule is simple: use Adobe Commerce as a relationship reference only when it clarifies migration expectations. Do not turn Magento Open Source guidance into an Adobe Commerce article, and do not flatten Adobe Commerce into ordinary Magento assumptions.

### Extension and Customization Risk Starts Early <a href="#extension-and-customization-risk-starts-early" id="extension-and-customization-risk-starts-early"></a>

Magento is often chosen because merchants want flexibility. That flexibility usually involves modules, extensions, APIs, theme logic, integrations, and custom code. During migration, the key question is not whether Magento can be customized. The key question is whether the source data that supports current business behavior exists in a supported form and has a meaningful target destination.

Examples include loyalty balances, subscription rules, product configurators, custom checkout fields, shipping restrictions, reward points, ERP item IDs, PIM enrichment fields, marketplace listing IDs, tax service identifiers, search boost rules, quote-like workflows, or custom customer attributes. Some values may map cleanly as supported data. Some may require Add-ons when supported filtering, mapping, or data configuration is enough. Some require Custom Service because the requirement involves unsupported module data, custom fields, outside-system identifiers, bespoke transformation, or custom migration logic adjustment.

| Requirement pattern                                      | Likely planning direction                                                     |
| -------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Supported records with selective filtering needs         | Add-ons may be suitable.                                                      |
| Supported fields that need more precise target alignment | Add-ons may be suitable when behavior remains supported.                      |
| Custom fields or extension-owned data                    | Custom Service review may be needed.                                          |
| External-system identifiers                              | Custom Service or integration planning may be needed depending on target use. |
| Live module configuration                                | Target-side implementation, not ordinary migrated content.                    |
| Custom Platform source behavior                          | Custom Service review before scope is accepted.                               |

This boundary protects Magento planning from false certainty. Magento can support sophisticated implementations, but a migration plan still needs to define which data is migrated, which configuration belongs to Magento implementation, and which custom requirements require a separate service review.

### Core Migration Planning Priorities <a href="#core-migration-planning-priorities" id="core-migration-planning-priorities"></a>

A Magento migration plan should turn platform flexibility into concrete controls. The first control is product-type clarity. The merchant should know which source product patterns become simple, configurable, grouped, bundle, virtual, or downloadable products and which patterns require custom review.

The second control is attribute discipline. The merchant should know which fields are visible, searchable, filterable, comparable, operational, excluded, merged, or mapped differently. Magento attributes can improve discovery and merchandising, but only when values are normalized and purposeful.

The third control is scope evidence. Storefronts, store views, localized values, categories, CMS Pages, Blog Posts, and URLs should be prepared before migration when they affect launch. Magento scope can preserve rich storefront differences, but only when source values are identified correctly.

The fourth control is extension and integration classification. Modules, custom fields, external IDs, and integration-owned records should not be hidden inside generic product or customer scope. They should be classified as supported scope, Add-ons, Custom Service, target setup, or excluded expectations.

The fifth control is validation ownership. Magento output should be reviewed by people who understand catalog structure, SEO, customer/account behavior, order history, inventory, and implementation settings. A compliant record count is not enough for a platform where structure determines usability.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Magento Open Source is a strong Target Platform when the merchant needs structured catalog modeling, attribute control, store-scope flexibility, SEO-sensitive URL handling, extension-driven implementation, and ownership over the commerce environment. It is not best approached as a simple storefront transfer. The migration should preserve data in a way that Magento can interpret through product types, attributes, attribute sets, websites, stores, store views, customer groups, inventory expectations, URLs, extensions, and custom requirements.

The strongest Magento migration plans make decisions before data is moved: which product structures matter, which attributes deserve preservation, which scope values vary by storefront, which URLs require continuity, which module or integration data needs review, and which target-side setup remains outside ordinary data migration. That planning discipline helps Magento flexibility become a migration advantage instead of a launch risk.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Magento Open Source the same as Adobe Commerce for migration planning?**

No. Magento Open Source and Adobe Commerce share important foundations, but Adobe Commerce can introduce enterprise capabilities, licensing, B2B functions, shared catalogs, governance, and infrastructure assumptions that should not be implied in a Magento Open Source migration.

**Why do Magento product types matter during migration?**

Magento product types affect how products are sold, displayed, inventoried, and maintained. Source product choices may need to become simple, configurable, grouped, bundle, virtual, or downloadable structures rather than flat product records.

**Should every source field become a Magento attribute?**

No. Attributes should be preserved when they support product pages, filtering, search, comparison, reporting, integration, or internal operations. Duplicate, obsolete, inconsistent, or unsupported fields should be cleaned, merged, excluded, or reviewed for Custom Service.

**Why is store-view planning important for Magento?**

Store views can support different locales and scoped storefront values. Product names, descriptions, URLs, metadata, categories, CMS Pages, Blog Posts, and visibility may need scope-aware review before launch.

**When should Custom Service be considered for a Magento migration?**

Custom Service should be considered when the requirement involves unsupported module data, custom fields, external identifiers, bespoke transformation, Custom Platform interpretation, or custom migration logic adjustment beyond supported migration behavior.
