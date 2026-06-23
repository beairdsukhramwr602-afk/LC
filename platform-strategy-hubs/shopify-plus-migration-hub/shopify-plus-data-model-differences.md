# Shopify Plus Data Model Differences

A Shopify Plus migration should not be judged only by whether products, customers, orders, collections, and content appear in the Target Platform. Shopify Plus can change how those records carry commercial meaning because B2B companies, company locations, catalogs, buyer permissions, payment terms, checkout settings, markets, organization-level governance, metafields, metaobjects, and enterprise integrations can all affect how migrated data behaves after launch.

The central data-model question is therefore not only what records move, but what relationships those records must support. A customer can remain a customer, but the business meaning may depend on the company they represent, the company location they buy for, the catalog they can access, the store or market they enter, and the custom fields or integrations that interpret the record. Shopify Plus migration planning should translate source-side meaning into Shopify Plus structures before record counts are treated as success.

### Why Data Model Differences Matter in Shopify Plus <a href="#why-data-model-differences-matter-in-shopify-plus" id="why-data-model-differences-matter-in-shopify-plus"></a>

Shopify Plus keeps the Shopify foundation of products, variants, collections, customers, orders, content, redirects, metafields, metaobjects, apps, and markets. The difference is that enterprise and B2B use cases often place important meaning outside individual records. Product visibility can depend on catalog assignment. Pricing can depend on company or location context. Buyer access can depend on contact permissions. Checkout behavior can depend on B2B settings. Storefront meaning can depend on market, store, organization, or integration context.

That makes Shopify Plus different from a straightforward store-to-store migration. A visible product record might not be commercially ready if it appears to the wrong buyer. A customer record might not be useful if it is not attached to the correct company location. An order history might be incomplete if it does not support service, reporting, or account review in the intended B2B context. A metafield might migrate successfully but still fail if its definition, validation, storefront usage, or app dependency is missing.

| Source-side meaning                     | Shopify Plus translation question                                                                                               |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Wholesale customer groups               | Should they become companies, locations, catalogs, customer segments, tags, app logic, or Custom Service scope?                 |
| Negotiated price lists                  | Should pricing be represented through catalogs, markets, apps, custom data, or revised business rules?                          |
| Branches, departments, or buyer offices | Should they become company locations, addresses, contacts, or separate operational contexts?                                    |
| Custom product attributes               | Should they become standard fields, product options, variants, metafields, metaobjects, category metafields, or app-owned data? |
| Multi-store or regional structures      | Should they become Shopify Plus stores, markets, domains, languages, currencies, catalogs, or integration rules?                |
| Extension-owned logic                   | Can it be represented by supported Shopify Plus structures, or does it require Custom Service?                                  |

The value of Shopify Plus is strongest when these choices are explicit. When the choices are vague, migrated records can look complete while the operating model remains unreliable.

### Company, Location, and Buyer Relationship Differences <a href="#company-location-and-buyer-relationship-differences" id="company-location-and-buyer-relationship-differences"></a>

In many Source Platforms, B2B meaning is stored through customer groups, account records, billing addresses, shipping addresses, custom fields, roles, approval flags, price lists, ERP identifiers, or extension logic. Shopify Plus B2B uses companies and company locations as core relationship structures. That means customer migration must be planned as a business-account model, not only as a profile transfer.

A company can represent the parent business relationship. Company locations can represent the specific buying locations or business units under that company. Contacts are customer profiles connected to those locations, and their access can affect what they can do after logging in. Location-level details can also carry important commercial context, including shipping address, billing address, tax ID, tax exemptions, catalogs, payment terms, contacts, and checkout settings.

This changes the meaning of several common source records:

* a customer group might become a company assignment, catalog rule, segment, or pricing context;
* an address might become an ordinary customer address or a company-location address;
* a branch or department might become a company location rather than a standalone customer;
* a buyer contact might need permission to buy for one location but not another;
* an external account ID might need to remain usable for ERP, CRM, support, reporting, or fulfillment continuity;
* historical orders may need to support company-level or location-level account review.

The strongest migration plans define these relationships before migration begins. If the source store uses customer groups or custom fields to simulate business accounts, those structures should be translated into Shopify Plus B2B meaning rather than copied as flat labels.

### Catalog, Pricing, and Product Visibility Differences <a href="#catalog-pricing-and-product-visibility-differences" id="catalog-pricing-and-product-visibility-differences"></a>

Catalogs are one of the most important Shopify Plus data-model differences for B2B migration. In a standard direct-to-consumer model, a product can often be evaluated by storefront visibility, price, inventory, and collection placement. In Shopify Plus B2B, product availability and pricing can depend on which company or company location is buying.

This creates a commercial control layer above the product record. A migrated product can be accurate as a product but still wrong for a buyer if catalog assignment, product inclusion, price adjustment, market relationship, or location access has not been configured correctly.

Source-side pricing and visibility can appear in many forms:

| Source behavior              | Shopify Plus interpretation                                                                                       |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Customer-group pricing       | May need catalog pricing, company/location assignment, app logic, or Custom Service depending on rule complexity. |
| Hidden wholesale products    | May need catalog-controlled product visibility, separate storefront logic, or product-publication decisions.      |
| Contract price lists         | May need catalog planning, integration review, or custom handling if price logic is not directly supported.       |
| Regional B2B pricing         | May involve catalogs, markets, currencies, tax context, or separate operational rules.                            |
| Distributor-only assortments | May need company-location catalog assignment and validation by representative buyer accounts.                     |

Catalog planning should not be treated as a cosmetic step. It determines whether migrated product and pricing data supports the intended buying experience. For Shopify Plus, product migration and catalog assignment must be reviewed together when B2B access or negotiated pricing matters.

### Product, Variant, Metafield, and Metaobject Differences <a href="#product-variant-metafield-and-metaobject-differences" id="product-variant-metafield-and-metaobject-differences"></a>

Shopify Plus still follows Shopify product architecture. Products can have options and variants, collections organize storefront discovery, and product information can be extended with metafields and metaobjects. The important distinction is that enterprise merchants often bring source-side product complexity that does not map cleanly to simple product fields.

Several source structures need special review:

* configurable, bundled, personalized, or made-to-order product behavior;
* product options that are not equivalent to Shopify variants;
* variant-level identifiers used by ERP, fulfillment, or marketplace systems;
* product attributes used for filtering, tax classification, channel feeds, or merchandising;
* source categories that need to become Shopify collections, product categories, product types, tags, metafields, or navigation logic;
* custom product tables, extension fields, or app-owned attributes;
* category-specific attributes that may align better with Shopify category metafields or metaobjects.

Metafields are useful because they extend Shopify data models such as products, customers, and orders with custom data. Metaobjects can support reusable structured content or data entries. These structures can preserve important business meaning, but they need definitions, field types, validation expectations, display logic, and ownership rules. Migrating a value into a metafield is not enough if the Target Platform lacks the definition, storefront usage, app dependency, or operational process that makes the value useful.

For Shopify Plus, product-data translation should also separate standard record movement from customization. Supported field mapping, filtering, or data configuration can often be handled through Add-ons. Unsupported source structures, bespoke transformations, custom product logic, app-owned data, or Custom Platform source behavior may require Custom Service.

### Store, Market, and Localization Differences <a href="#store-market-and-localization-differences" id="store-market-and-localization-differences"></a>

Shopify Plus merchants often operate across multiple stores, markets, regions, languages, currencies, domains, or brands. These structures can make data-model planning more complex because the same record type might need different meaning depending on where it appears.

A Source Platform might use one back office with store views, language packs, customer groups, regional domains, custom tax rules, or extension-driven price logic. Shopify Plus may represent the future operating model through stores, markets, catalogs, localized content, domains, apps, and organization-level governance. The migration should define which structure owns each commercial difference.

Important questions include:

* Should a regional experience become a Market, a separate Shopify Plus store, a catalog rule, or an app-supported workflow?
* Should translated content move as content records, theme content, metaobjects, app data, or be recreated after migration?
* Should URLs and redirects be validated by market, domain, language, or storefront path?
* Should B2B and direct-to-consumer buyers share one storefront context or operate through different contexts?
* Should product visibility vary by catalog, market, store, or publication state?

Shopify Plus organization-level control can help enterprise teams govern stores, but it does not make every store share the same data meaning automatically. Each store, market, catalog, and buyer path still needs deliberate migration ownership.

### Customer, Order, and Account History Differences <a href="#customer-order-and-account-history-differences" id="customer-order-and-account-history-differences"></a>

Customer and order history can carry different meaning in Shopify Plus than in the Source Platform. A direct-to-consumer customer profile may only need identity, addresses, communication consent, and order history. A Shopify Plus B2B profile may also need company association, location access, buyer permission, payment terms, tax context, and relationship to catalogs or checkout rules.

Order history also needs interpretation. Historical orders can support customer service, account review, reorder decisions, reporting, ERP reconciliation, and internal operations. For B2B merchants, it may matter whether orders can be reviewed by company, location, contact, product, pricing context, or external reference. A migrated order can be present but still less useful if the surrounding account structure does not support the business process.

Account access deserves separate planning. Password behavior, login method, customer-account experience, company selection, location selection, buyer permissions, and account-management expectations may differ from the source store. Merchants should avoid assuming that migrated customer data automatically recreates the same account experience.

### App, Integration, and Custom Data Differences <a href="#app-integration-and-custom-data-differences" id="app-integration-and-custom-data-differences"></a>

Shopify Plus migrations frequently involve apps, integrations, ERP systems, CRM systems, fulfillment providers, tax services, loyalty systems, subscription systems, marketplaces, review platforms, reporting tools, and custom workflows. These systems can define how data is interpreted after launch.

A field that looks optional during migration can become critical when it controls fulfillment routing, tax calculation, support lookup, buyer approval, contract pricing, product configuration, reporting, or ERP synchronization. External IDs, app-owned fields, custom account rules, and integration-specific flags should be identified before migration scope is finalized.

This is also where Custom Service boundaries become important. Add-ons can support filtering, mapping, and supported data configuration. Custom Service is the correct escalation path when the business needs unsupported source structures, app-owned logic, bespoke transformation, Custom Platform handling, or custom migration logic adjustment. Treating custom operational data as ordinary records can produce a migration that is technically complete but operationally incomplete.

### How Data Model Differences Affect Migration Scope <a href="#how-data-model-differences-affect-migration-scope" id="how-data-model-differences-affect-migration-scope"></a>

Data-model differences should directly shape the migration scope for Shopify Plus. The more the target model depends on company relationships, location context, catalogs, custom product data, market logic, store boundaries, integrations, and custom workflows, the more the migration plan must define what is standard, what needs Add-ons, and what requires Custom Service.

| Scope area                     | Planning implication                                                                                                                      |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Companies and locations        | Define source-to-target account relationships before customer migration is treated as complete.                                           |
| Catalogs and pricing           | Validate product visibility and price outcomes by buyer context, not only by catalog count.                                               |
| Products and custom attributes | Decide which source attributes become standard fields, variants, metafields, metaobjects, apps, or custom scope.                          |
| Store and market structure     | Assign records to the correct store, market, domain, language, currency, and validation path.                                             |
| Customer and order history     | Confirm whether historical data supports support, reporting, reorder, account review, or ERP continuity.                                  |
| Apps and integrations          | Identify external IDs, operational fields, and app-owned data before launch-critical behavior is tested.                                  |
| Later migration activity       | Revalidate affected buyer, catalog, product, order, and configuration behavior when follow-up migration activity changes meaningful data. |

Additional Migration Options should appear in Shopify Plus planning only when later migration activity has real platform-specific impact. For example, new companies, changed company-location assignments, catalog updates, product changes, new orders, or updated custom data may require renewed checks. They do not replace the need to define the correct Shopify Plus target model before migration begins.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify Plus data-model differences are mainly about business meaning. Products, customers, orders, collections, content, and custom data still matter, but enterprise and B2B success depends on whether those records support the intended company, location, catalog, pricing, store, market, account, and integration behavior after launch.

A strong Shopify Plus migration treats data as connected commercial context. The target model should explain who buys, where they buy from, what they can see, which prices apply, which store or market owns the experience, which custom data remains operational, and how each critical scenario will be validated before launch decisions are made.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are Shopify Plus data model differences more complex than standard Shopify differences?**

Shopify Plus can add enterprise and B2B context around baseline Shopify records. Companies, company locations, catalogs, buyer permissions, payment terms, markets, stores, metafields, metaobjects, and integrations can all affect what migrated data means after launch.

**Do customer records automatically become Shopify Plus B2B companies?**

No. Customer records, companies, company locations, and contacts serve different purposes. The migration must define which source accounts become companies, which addresses or branches become locations, which people become contacts, and what access each buyer should have.

**Are catalogs just another way to organize products?**

No. In Shopify Plus B2B, catalogs can control product availability and pricing for companies or company locations. They should be validated as commercial access rules, not treated as ordinary product grouping.

**Can metafields and metaobjects preserve custom source data?**

Often, but they need planning. A custom value should have the right definition, type, validation expectation, storefront or app usage, and operational owner. Unsupported or app-owned custom behavior may require Custom Service rather than simple field mapping.

**Should Additional Migration Options be planned around Shopify Plus data-model differences?**

Only when later migration activity affects meaningful Shopify Plus behavior. New companies, updated catalogs, changed pricing, additional orders, or revised custom data can require renewed validation, but Additional Migration Options do not replace initial data-model planning.
