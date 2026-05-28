# CS-Cart Data Model Differences

CS-Cart migration is not only about whether products, customers, orders, categories, and content can be transferred. The more important question is how those records behave once they become part of CS-Cart’s commerce structure. A source store may treat products as a simple catalog, sellers as internal suppliers, customer groups as labels, or custom fields as notes. In CS-Cart, those same records may need to support storefront structure, marketplace vendor ownership, B2B/B2C access rules, add-on behavior, theme presentation, integrations, and operational workflows.

The data model difference matters because CS-Cart can be used as a conventional online store, a marketplace, a B2B/B2C selling environment, a headless implementation, or a custom e-commerce project. The same migrated data may need different treatment depending on which future model the merchant is building.

A strong CS-Cart migration translates source records into usable commerce meaning. Products must remain buyable and discoverable. Categories must support navigation. Vendors must have the right ownership context when a marketplace model is involved. Customers must retain their account and the meaning of their order. Orders must remain useful for service, accounting, reporting, and fulfillment review. Add-ons, themes, custom fields, and integration-owned data must be identified before anyone assumes they can become native CS-Cart behavior.

### How CS-Cart Changes Commercial Meaning <a href="#how-cs-cart-changes-commercial-meaning" id="how-cs-cart-changes-commercial-meaning"></a>

CS-Cart’s flexibility is valuable because it can support different commercial models, but that flexibility also makes data interpretation more deliberate. A product record is not just a product if it belongs to a vendor, appears in specific storefronts, relies on options, uses add-on-powered behavior, or connects to external inventory and fulfillment systems. A customer record is not just a buyer if the future store uses customer groups, B2B purchasing context, approvals, negotiated pricing, or marketplace buyer history.

The migration should therefore answer two questions for each major data type:

| Data area                | Source-side question                                                                                                              | CS-Cart migration meaning                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Products                 | Is the product a simple sellable item, a configured item, a vendor-owned item, or part of a marketplace catalog?                  | Product migration must preserve buying meaning, ownership context, options, descriptions, images, identifiers, and storefront visibility. |
| Categories               | Are categories used for navigation, SEO, vendor organization, internal reporting, or all of these?                                | Category migration must support discoverability, URL planning, menu structure, and catalog governance in the Target Platform.             |
| Vendors                  | Are sellers, suppliers, departments, brands, or fulfillment owners represented as ordinary fields in the source?                  | Marketplace migrations may require vendor ownership to be planned instead of treating vendor context as incidental product metadata.      |
| Customers                | Do buyers have groups, roles, B2B status, pricing context, or approval expectations?                                              | Customer data must preserve account meaning, not only contact information and addresses.                                                  |
| Orders                   | Do orders carry vendor splits, fulfillment notes, payment state, shipping context, or integration identifiers?                    | Order history should remain operationally interpretable after migration, even when some workflow behavior must be reconfigured.           |
| Add-ons and integrations | Is important behavior controlled by an app, add-on, custom code, ERP, payment system, shipping service, or marketplace connector? | Data ownership must be identified before migration so standard records are not mistaken for complete business behavior.                   |

### Core Data Model Layers in CS-Cart <a href="#core-data-model-layers-in-cs-cart" id="core-data-model-layers-in-cs-cart"></a>

A CS-Cart migration should be planned through several structural layers rather than through a flat entity list.

| CS-Cart layer               | What it controls                                                                              | Migration implication                                                                                                          |
| --------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Catalog layer               | Products, categories, options, features, images, descriptions, and identifiers                | Source catalog data must be translated into a structure that supports browsing, filtering, comparison, and purchase decisions. |
| Vendor or marketplace layer | Seller ownership, vendor product assignment, vendor order context, marketplace administration | Marketplace-oriented migrations must distinguish product data from seller ownership and vendor workflow meaning.               |
| Customer and account layer  | Customer records, addresses, groups, buyer context, B2B/B2C segmentation                      | Account migration must preserve the buyer relationships needed for login, pricing, service, and historical review.             |
| Storefront and route layer  | Navigation, content pages, URLs, storefront presentation, SEO continuity                      | Migrated products and categories must remain discoverable and tied to route planning, not only present in the admin area.      |
| Add-on and theme layer      | Extended features, custom presentation, marketplace apps, theme-dependent display             | Add-on or theme-owned behavior may require configuration, Add-ons, Custom Service, or post-migration reconstruction.           |
| Integration layer           | ERP, CRM, accounting, payment, shipping, fulfillment, inventory, marketplace feeds, APIs      | External ownership must be documented so migration does not overpromise what native record transfer can preserve.              |
| Custom-source layer         | Custom fields, modified database structures, third-party identifiers, bespoke source logic    | Custom Platform or heavily modified Source Platform cases require source interpretation before the data can be safely mapped.  |

### Product and Catalog Meaning <a href="#product-and-catalog-meaning" id="product-and-catalog-meaning"></a>

Product data is often the most visible part of a CS-Cart migration, but visibility does not make it simple. A source product may include SKU, title, price, description, image, category assignment, options, attributes, downloadable content, vendor reference, inventory behavior, shipping class, tax handling, or custom fields. In CS-Cart, those details may influence how the product is purchased, displayed, filtered, fulfilled, or assigned to a vendor.

#### Product identity and purchasability <a href="#product-identity-and-purchasability" id="product-identity-and-purchasability"></a>

The migrated product should remain identifiable and buyable. SKU, product name, description, price, stock state, image, URL, and category placement must work together. If the source store used duplicate SKUs, inconsistent option labels, placeholder products, inactive products, or discontinued items, the migration should not treat all product records as equally launch-ready.

A product can technically arrive in the Target Platform but still fail commercially if customers cannot identify the right item, choose the right option, view the right image, or understand whether the product is available.

#### Options, features, and attribute meaning <a href="#options-features-and-attribute-meaning" id="options-features-and-attribute-meaning"></a>

CS-Cart product options, features, and descriptive attributes should be planned around customer decision-making. Source platforms often mix sellable options, descriptive specifications, internal classification fields, filterable attributes, and supplier notes. Those differences matter because a field that was harmless in the source store can become confusing if it appears as customer-facing product information after migration.

A strong data-model translation separates:

| Source data pattern                                                                           | Better CS-Cart interpretation                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Sellable choices such as size, color, pack quantity, or configuration                         | Product option or variant-style buying logic, depending on the intended target behavior.            |
| Technical specifications such as material, voltage, dimension, compatibility, or model number | Product feature or descriptive attribute that supports comparison, filtering, or product education. |
| Internal purchasing, warehouse, supplier, or margin notes                                     | Internal reference or Custom Service review, not automatically customer-facing product data.        |
| Legacy option names or inconsistent values                                                    | Cleanup or mapping review before migration, especially when options affect purchase accuracy.       |

#### Marketplace product ownership <a href="#marketplace-product-ownership" id="marketplace-product-ownership"></a>

When CS-Cart is used for marketplace or multi-vendor commerce, product data may need vendor ownership. A source system may store seller, supplier, brand, department, or fulfillment owner as a field. That does not automatically mean the data is ready for marketplace ownership in the Target Platform.

Before migration, the merchant should clarify whether vendor identity affects product publishing, inventory, order routing, commission logic, fulfillment responsibility, reporting, or marketplace administration. If vendor context is commercially meaningful, it should be treated as a data-model layer, not as a product note.

### Category, Navigation, and Storefront Meaning <a href="#category-navigation-and-storefront-meaning" id="category-navigation-and-storefront-meaning"></a>

Categories in CS-Cart affect more than organization. They influence how buyers browse, how products are grouped, how menus are planned, and how SEO routes can be reviewed after migration.

A source category tree may contain customer-facing navigation, internal reporting groups, vendor catalog sections, brand pages, seasonal collections, archived categories, or temporary campaign structures. Moving all category records without interpretation can preserve clutter rather than improve storefront clarity.

#### Category structure should support buying paths <a href="#category-structure-should-support-buying-paths" id="category-structure-should-support-buying-paths"></a>

A strong CS-Cart category structure should help customers find products. If a source store used categories inconsistently, placed products in many unrelated sections, or mixed internal labels with storefront navigation, the migrated result may look complete but feel difficult to use.

Migration planning should identify:

* which categories should remain customer-facing;
* which categories are obsolete or internal;
* which category paths support important SEO routes;
* which products belong in multiple categories deliberately;
* which category relationships affect marketplace or vendor browsing;
* which content or menu areas need to be rebuilt around the new structure.

#### Storefront and SEO meaning must be preserved deliberately <a href="#storefront-and-seo-meaning-must-be-preserved-deliberately" id="storefront-and-seo-meaning-must-be-preserved-deliberately"></a>

CS-Cart storefront quality depends on route planning, page structure, menus, product/category URLs, and theme behavior. Source URLs, meta information, CMS pages, redirects, and high-value landing pages should not be treated as secondary details if organic traffic, partner links, advertising, or customer bookmarks depend on them.

The data model difference is that content and route data must be understood as storefront meaning. A product page is not only a product record. It is also a destination, a search result, a navigation endpoint, and a buyer decision page.

### Customer and Account Meaning <a href="#customer-and-account-meaning" id="customer-and-account-meaning"></a>

Customer data in CS-Cart should preserve more than names, emails, passwords where supported, addresses, and order history. For some stores, customer records may also carry customer group membership, pricing eligibility, B2B/B2C segmentation, approval status, tax treatment, payment expectations, marketplace buyer history, or account-level notes.

#### Customer groups and segmentation <a href="#customer-groups-and-segmentation" id="customer-groups-and-segmentation"></a>

Customer groups can influence pricing, access, promotions, communication, or service expectations. If the source store used customer groups loosely, migration should not automatically preserve every label as a meaningful target group. If the source store used groups as part of pricing or access control, the group structure should be validated after migration.

A good CS-Cart data translation asks:

| Customer question                                          | Why it matters after migration                                                                           |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Which customers are ordinary retail buyers?                | Standard customer records may be enough when no special pricing or access rules apply.                   |
| Which customers belong to groups with commercial meaning?  | Group membership may affect pricing, discounts, access, B2B workflows, or validation samples.            |
| Which customers require tax, payment, or approval context? | These details may need configuration, Add-ons, or Custom Service if they are not standard record fields. |
| Which account notes are operationally important?           | Internal notes may need custom-field review or a separate handling plan.                                 |

#### B2B/B2C meaning <a href="#b2b-b2c-meaning" id="b2b-b2c-meaning"></a>

When the future CS-Cart store supports both B2C and B2B purchasing, customer data should be interpreted through buying behavior. A B2B customer may need company context, repeat-order expectations, special pricing, quote-related history, negotiated terms, or account-level permissions. Those expectations may not be fully represented by standard customer fields in the source export.

If B2B behavior depends on external systems, staff knowledge, or custom source logic, the migration path should not assume customer records alone preserve the operating model.

### Order and History Meaning <a href="#order-and-history-meaning" id="order-and-history-meaning"></a>

Orders are historical records, but they are also operational evidence. In CS-Cart, migrated order history may be used for customer service, accounting review, fulfillment reference, dispute handling, reorder support, reporting, and marketplace/vendor context.

A source order may include product details, customer details, tax amounts, shipping methods, payment state, discounts, coupons, fulfillment status, vendor assignment, tracking numbers, internal comments, external identifiers, or integration-owned statuses. Some of those elements can map as standard order data. Others may require custom-field handling, Add-ons, Custom Service, or post-migration integration planning.

#### Marketplace and vendor order context <a href="#marketplace-and-vendor-order-context" id="marketplace-and-vendor-order-context"></a>

In marketplace scenarios, order history can become more complex because vendor ownership matters. A single customer order may involve one vendor, several vendors, split fulfillment, vendor-specific payouts, or vendor-admin review. If the source system does not store that context clearly, CS-Cart cannot safely infer it from ordinary order records.

Marketplace order migration should therefore clarify which historical information must remain visible and which operational workflows will only apply to new orders after launch.

#### Status and fulfillment meaning <a href="#status-and-fulfillment-meaning" id="status-and-fulfillment-meaning"></a>

Order statuses should not be migrated as raw labels without interpretation. A source status such as `processing`, `ready`, `paid`, `fulfilled`, `partially shipped`, or `awaiting vendor`may have workflow meaning that differs from CS-Cart’s target configuration.

The migration should preserve order history in a way that supports realistic review. If old statuses are needed only for reference, that is different from needing them to control future workflow automation.

### Add-On, Theme, and Custom Development Meaning <a href="#add-on-theme-and-custom-development-meaning" id="add-on-theme-and-custom-development-meaning"></a>

CS-Cart’s ecosystem is a major part of its flexibility. Add-ons, themes, custom development, hosting choices, marketplace extensions, and partner-built functionality can extend what the platform does. That flexibility creates an important data-model distinction: not all source behavior belongs inside native product, customer, order, or category records.

#### Add-on-owned behavior <a href="#add-on-owned-behavior" id="add-on-owned-behavior"></a>

A source store may rely on extensions, scripts, plugins, modules, or apps for pricing, shipping, subscription behavior, marketplace routing, product options, checkout rules, promotions, or order updates. When moving to CS-Cart, the important question is not only whether the data exists. The question is whether the behavior has a target location.

If equivalent behavior is handled through a CS-Cart add-on or configuration, the migration may need mapping and setup planning. If the behavior is unique, modified, or unsupported by standard migration capability, it may require Custom Service.

#### Theme-owned presentation <a href="#theme-owned-presentation" id="theme-owned-presentation"></a>

Themes can affect how product data, category navigation, content, promotional sections, marketplace seller pages, and checkout elements appear. A source theme may contain data-like content that is not stored as ordinary products or pages. Examples include hard-coded banners, custom menu blocks, embedded comparison tables, brand panels, landing page sections, or visual merchandising blocks.

These elements should be inventoried before migration. They may need content migration, theme reconstruction, manual setup, or Custom Service depending on how they are stored and what the future CS-Cart storefront must show.

### Integration and Headless Meaning <a href="#integration-and-headless-meaning" id="integration-and-headless-meaning"></a>

CS-Cart can be part of a broader e-commerce environment involving ERP, CRM, accounting, fulfillment, payment, tax, marketplace feeds, vendor systems, analytics, mobile apps, or headless storefronts. When integrations are involved, the data model extends beyond the store database.

A source store may display product, inventory, customer, or order information that is actually owned by an external system. Migrating the visible storefront record does not automatically recreate the operational connection.

#### System ownership must be clarified <a href="#system-ownership-must-be-clarified" id="system-ownership-must-be-clarified"></a>

Integration-heavy CS-Cart migrations should identify which system owns each important outcome:

| Outcome         | Possible owner                                                         | Migration implication                                                             |
| --------------- | ---------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Product truth   | Source store, ERP, PIM, vendor feed, marketplace connector             | Product migration should not overwrite or duplicate the system of record.         |
| Inventory truth | Source store, warehouse system, ERP, vendor feed                       | Stock values may need reconnection rather than one-time historical transfer.      |
| Customer truth  | Storefront, CRM, B2B system, ERP                                       | Customer migration should preserve account meaning and avoid conflicting records. |
| Order workflow  | CS-Cart, fulfillment system, marketplace vendor panel, shipping system | Historical order data may migrate differently from future workflow automation.    |
| Pricing truth   | CS-Cart, ERP, custom script, B2B rule engine                           | Pricing migration may require mapping, Add-ons, configuration, or Custom Service. |
| Analytics truth | Storefront, analytics platform, reporting warehouse                    | Historical reporting continuity may depend on identifiers and external systems.   |

#### Headless storefronts and mobile experiences <a href="#headless-storefronts-and-mobile-experiences" id="headless-storefronts-and-mobile-experiences"></a>

When CS-Cart supports a headless or mobile commerce experience, source data must be validated beyond the admin panel. Product fields, images, URLs, category paths, filters, customer context, and order behavior may need to work through APIs or front-end applications. A record that looks correct in the admin area may still fail if the front-end expects different identifiers, metadata, or structured fields.

Headless and mobile contexts should therefore be treated as validation and integration concerns, not merely presentation choices.

### Custom Platform Source Interpretation <a href="#custom-platform-source-interpretation" id="custom-platform-source-interpretation"></a>

A migration from a Custom Platform or heavily modified Source Platform into CS-Cart requires special attention. Custom fields, database tables, proprietary product relationships, third-party identifiers, checkout modifications, vendor logic, B2B account rules, and integration-owned data may not explain themselves in ordinary exports.

In these cases, the data model difference begins with source interpretation. The project must identify what the source data means before deciding how it should move. Custom Platform source cases point to Custom Service because the migration may require custom migration logic adjustment, Custom Add-ons, Tailored Add-ons, source analysis, field mapping, or bespoke transformation.

### What Migrated Data Must Prove After Translation <a href="#what-migrated-data-must-prove-after-translation" id="what-migrated-data-must-prove-after-translation"></a>

A successful CS-Cart migration should prove that translated data works inside the intended target model. Presence alone is not enough.

| Data area                 | What must be proven                                                                                                                                             |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Products                  | Products are identifiable, purchasable, correctly described, assigned to appropriate categories, and usable within the intended store or marketplace model.     |
| Vendors                   | Vendor ownership, seller context, product assignment, and marketplace order meaning are preserved where they matter.                                            |
| Categories and navigation | Category structure supports browsing, route planning, SEO review, and storefront usability.                                                                     |
| Customers                 | Customer records, addresses, group context, and account history support realistic buyer review.                                                                 |
| Orders                    | Historical order records remain understandable for service, reporting, accounting, vendor, and fulfillment reference.                                           |
| Add-ons and themes        | Extended behavior and presentation-dependent content are identified and handled through configuration, Add-ons, Custom Service, or manual setup as appropriate. |
| Integrations              | External systems of record, APIs, connectors, and workflow owners are separated from one-time migrated data.                                                    |
| Custom source data        | Custom fields, modified database structures, and third-party identifiers are interpreted before target mapping is treated as complete.                          |

### Conclusion <a href="#conclusion" id="conclusion"></a>

CS-Cart data model differences are mostly about context. Products, customers, orders, categories, vendors, content, add-ons, themes, and integrations can all carry business meaning that is not obvious from the record name alone. Migration quality depends on translating that meaning into the Target Platform model the merchant actually plans to run.

A CS-Cart migration is strongest when catalog structure, vendor ownership, customer segmentation, order history, storefront routes, add-on behavior, and integration responsibilities are clarified before execution. When those layers are undocumented, the migrated data may look complete while still failing to support the marketplace, store, B2B, headless, or custom workflow that made CS-Cart the chosen destination.

Use Demo Migration and Live Chat to review representative products, vendors, categories, customers, orders, storefront routes, add-on-dependent behavior, and integration-sensitive records before treating the CS-Cart data model translation as ready for Full Migration.

### FAQs <a href="#faqs" id="faqs"></a>

**Does CS-Cart migration only involve products, customers, and orders?**

No. Products, customers, and orders are important, but CS-Cart migration may also involve vendor ownership, categories, storefront routes, customer groups, B2B context, marketplace logic, add-on behavior, theme-dependent content, integrations, custom fields, and Custom Platform source interpretation.

**Why is vendor ownership important in CS-Cart migration?**

Vendor ownership matters when the target CS-Cart store is a marketplace or multi-vendor environment. Product records may need to be connected to seller responsibility, vendor visibility, order handling, reporting, fulfillment, or marketplace administration.

**Can source custom fields be migrated directly into CS-Cart?**

Some custom fields may be mapped through standard service capability or Add-ons when the target meaning is clear. Fields that depend on custom source logic, modified database structures, third-party identifiers, or unsupported behavior should be reviewed through Custom Service.

**What happens to source add-on or plugin data during migration?**

Add-on, plugin, module, or app data should be reviewed based on what it controls. If it is ordinary product, customer, or order information, it may have a standard mapping path. If it controls behavior such as pricing, shipping, subscriptions, checkout, vendors, or integrations, it may require configuration, Add-ons, or Custom Service.

**How should Demo Migration be used for CS-Cart data model review?**

Demo Migration should include records that reveal data-model meaning: vendor-owned products, complex options, important categories, customer groups, B2B examples, historical orders, SEO-sensitive pages, custom fields, and integration-dependent records. The goal is to prove how migrated records behave inside CS-Cart, not only whether they appear.
