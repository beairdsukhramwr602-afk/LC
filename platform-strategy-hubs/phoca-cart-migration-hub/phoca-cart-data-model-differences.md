# Phoca Cart Data Model Differences

Phoca Cart migration requires more than matching source fields to target fields. Phoca Cart is a Joomla-native commerce extension, so migrated records need to operate inside a Joomla site structure as well as inside Phoca Cart’s catalog, checkout, customer, order, and configuration layers. A product may be connected to categories, manufacturers, attributes, options, specifications, stock behavior, downloadable files, customer-group prices, reward points, tax rates, shipping methods, payment plugins, language records, modules, template overrides, and Joomla access levels.

That combination changes the practical meaning of migration. A source store may treat product variants, custom fields, category paths, tax zones, customer groups, or order statuses as ordinary store records. In Phoca Cart, those same ideas may be divided between product data, Phoca Cart configuration, Joomla presentation, plugin behavior, and custom implementation. The migration plan should therefore ask how each record will be used after launch, not only whether the record can be transferred.

### Why Data Model Differences Matter <a href="#why-data-model-differences-matter" id="why-data-model-differences-matter"></a>

Data model differences matter because Phoca Cart operates as part of a Joomla environment. Products, customers, and orders are important, but they are not the whole store. A working Phoca Cart result also depends on how the catalog is organized, how shoppers choose product options, how categories and menus expose products, how customer groups affect price or access, how tax and shipping are configured, and how Joomla templates and modules display the result.

| Source-store assumption                          | Phoca Cart interpretation                                                                                                                                                         | Migration planning implication                                                                                             |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| A product record is a complete selling unit      | A product may depend on categories, manufacturers, options, attributes, specifications, stock status, downloadable files, taxes, images, customer groups, and Joomla presentation | Product samples should include simple, option-heavy, customer-group-sensitive, downloadable, and stock-sensitive products. |
| A category is only a catalog label               | Categories can shape discovery, menus, modules, SEO paths, filtering, multilingual browsing, and product grouping                                                                 | Category migration should be validated with storefront paths, menu placement, and representative product pages.            |
| Product details can be mapped by field name      | Options, attributes, specifications, parameters, and custom fields may represent different roles                                                                                  | Field purpose should be reviewed before deciding where each source detail belongs.                                         |
| Customer data is only contact information        | Customer groups, Joomla users, reward points, customer prices, access levels, and purchase history can affect buyer experience                                                    | Customer examples should include ordinary buyers, group-priced buyers, repeat buyers, and account-linked orders.           |
| Orders are only totals and statuses              | Orders may need readable products, discounts, coupons, taxes, shipping, payment context, invoices, and status meaning                                                             | Order validation should confirm operational readability, not only record count.                                            |
| Tax, shipping, and payment migrate as store data | Future checkout behavior usually depends on target configuration and plugins                                                                                                      | Historical order context should be separated from target checkout configuration.                                           |
| Storefront layout follows data automatically     | Joomla modules, menus, templates, overrides, and language routes shape how migrated data appears                                                                                  | Storefront review should be part of scope planning when presentation continuity matters.                                   |

The main question is whether migrated data preserves business meaning inside Phoca Cart. A record that looks correct in the administration panel can still be wrong if it no longer supports the original buying path, customer rule, order interpretation, SEO route, or operational workflow.

### Catalog and Product Structure Differences <a href="#catalog-and-product-structure-differences" id="catalog-and-product-structure-differences"></a>

Phoca Cart product data can support simple products, large catalogs, catalog-mode presentation, downloadable products, stock-managed products, customer-group pricing, product reviews, related products, wish lists, comparison lists, reward points, and product media. That flexibility is valuable, but it also means source catalog structures should be interpreted carefully.

#### Product records and selling behavior <a href="#product-records-and-selling-behavior" id="product-records-and-selling-behavior"></a>

A migrated product should remain understandable to shoppers and manageable for administrators. Core product information such as name, alias, SKU or product code, descriptions, price, images, stock status, publishing state, category placement, manufacturer, tax context, and language content should be reviewed together. These fields do not operate in isolation. A product with correct text but missing option behavior, stock meaning, customer-group price, or category route may still be incomplete.

Source platforms often use different product models. Some stores store every variation as a separate product. Others use variants, options, product modifiers, custom fields, or app-owned records. Phoca Cart supports product attributes and options, but the migration plan should decide what the shopper actually chooses and what the merchant actually manages. A field should not become a Phoca Cart option only because it was called an option in the old store.

| Source catalog pattern                    | Phoca Cart planning question                                                                             | Risk if ignored                                                                      |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Separate child products for color or size | Should these remain separate products, become options, or be organized through categories or attributes? | Product count may look right while shopper selection becomes confusing.              |
| Custom fields used for product choices    | Do those fields control purchase behavior, display only, filtering, or internal management?              | Required choices may become ordinary text instead of selectable buying logic.        |
| App-generated product metadata            | Does Phoca Cart have a standard place for the field, or does it need Add-on or Custom Service review?    | Important product behavior may disappear because it was not in the ordinary export.  |
| Product bundles or kits                   | Are these represented as simple products, grouped presentation, custom logic, or unsupported behavior?   | Order history and future selling behavior may no longer match merchant expectations. |
| Downloadable products                     | How should file availability, account access, and post-purchase delivery be represented?                 | Digital product access may fail even when product records migrate.                   |

#### Attributes, options, specifications, and parameters <a href="#attributes-options-specifications-and-parameters" id="attributes-options-specifications-and-parameters"></a>

Phoca Cart makes it important to distinguish product choice from product description. Options usually matter when the shopper must select something before purchasing. Attributes and specifications may describe the product, support comparison, or help with filtering. Parameters and custom fields may support display rules, import/export workflows, module behavior, or custom development.

A source field called “size” may be a selectable option for clothing, a dimension specification for furniture, or an internal shipping factor for equipment. A source field called “color” may be a purchasable variation, a descriptive attribute, or a search filter. The migration plan should classify fields by function before building the target model.

Phoca Cart also supports manufacturers, related products, reviews and ratings, stock statuses, product discounts, coupons, cart discounts, reward points, and customer group prices. These structures create additional data-model decisions. A catalog that depends on manufacturer browsing, wholesale pricing, product comparison, or reward-point incentives needs representative samples during Demo Migration.

#### Pricing, stock, discounts, and benefits <a href="#pricing-stock-discounts-and-benefits" id="pricing-stock-discounts-and-benefits"></a>

Pricing is not always a single product field. Phoca Cart can involve base prices, product discounts, customer group prices, cart discounts, coupons, reward points, tax rates, currencies, and stock status. A source platform may combine these ideas differently. Migration planning should separate historical pricing context from future pricing behavior.

Historical orders should remain readable with the prices, discounts, taxes, shipping, payment context, and totals that existed at purchase time. Future checkout pricing depends on target Phoca Cart configuration, currency setup, discount rules, reward behavior, tax rates, and plugin behavior. Treating both as the same data layer can create confusion during validation.

### Category, Collection, Navigation, or Storefront Structure Differences <a href="#category-collection-navigation-or-storefront-structure-differences" id="category-collection-navigation-or-storefront-structure-differences"></a>

A Phoca Cart catalog does not exist separately from Joomla storefront structure. Categories, products, modules, menus, templates, and language routes work together to create discoverability. A source store may have collections, smart collections, departments, brands, landing pages, product groups, tags, or menu-driven browsing. These structures need to be interpreted in Phoca Cart and Joomla terms.

| Source structure                        | Possible Phoca Cart or Joomla destination                                 | Planning implication                                                                             |
| --------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Product categories                      | Phoca Cart categories with Joomla menu exposure where needed              | Validate category hierarchy, aliases, product assignment, and menu paths.                        |
| Brand or manufacturer browsing          | Phoca Cart manufacturers or category/menu strategy                        | Decide whether manufacturer identity should support filtering, browsing, or product detail only. |
| Smart collections or dynamic groups     | Category rules, modules, filters, tags, custom logic, or manual grouping  | Automated source behavior may need target configuration or Custom Service review.                |
| Landing pages with embedded products    | Joomla content, menu items, modules, template positions, or custom layout | Data migration alone may not recreate the page experience.                                       |
| Navigation menus                        | Joomla menu structure and Phoca Cart routes                               | SEO and user flow should be reviewed separately from product record presence.                    |
| Product filters and comparison behavior | Phoca Cart filters, attributes, specifications, modules, or extensions    | Field classification affects filtering usefulness.                                               |

Categories should be checked as operational structures, not just as names. Deep trees, duplicate labels, inactive categories, hidden categories, seasonal collections, manufacturer-led categories, and language-specific category paths can all affect target usability. A clean product count does not prove that products can be found.

Joomla menu items and modules may be required to expose important Phoca Cart pages. Product and category data can exist correctly but remain difficult to reach if menus, module positions, language associations, or template overrides are not prepared. This is especially important when the source store relies on SEO-sensitive category URLs, promotional landing pages, or filter-based discovery.

### Customer, Account, and Order Data Differences <a href="#customer-account-and-order-data-differences" id="customer-account-and-order-data-differences"></a>

Customer and order migration should preserve operational context. In Phoca Cart, buyers may be connected to customer groups, Joomla access levels, group prices, reward points, coupons, order statuses, invoices, tax and shipping context, payment methods, downloadable product access, and customer benefits. A simple customer export rarely explains all of this meaning.

#### Customer identity and group meaning <a href="#customer-identity-and-group-meaning" id="customer-identity-and-group-meaning"></a>

Customer records should be reviewed for more than name, email, phone, and address. Phoca Cart can use customer groups and Joomla access level support, so customer identity may influence pricing, access, benefits, discounts, and storefront visibility. Stores with wholesale buyers, member-only pricing, role-based offers, reward-point programs, or group-specific catalog access need careful mapping.

If a source platform separates customer accounts from buyer groups, memberships, tags, roles, or pricing lists, those relationships should be identified before migration. The target result should show whether a customer is only a contact record or part of a buying rule.

#### Orders as business evidence <a href="#orders-as-business-evidence" id="orders-as-business-evidence"></a>

Orders should remain readable to customer service, accounting, fulfillment, and management teams. A migrated order may need product names, SKUs, quantities, chosen options, prices, taxes, discounts, coupons, reward-point effects, shipping method, payment method, currency, invoice reference, order status, customer group context, billing address, shipping address, and timestamps.

| Order element                          | Why it matters in Phoca Cart validation                                    | Review signal                                                                             |
| -------------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Purchased product and selected options | Proves the order still explains what was bought                            | Complex products should show their chosen options or purchased configuration.             |
| Discounts, coupons, and reward context | Explains why totals differ from base prices                                | Discounted orders should remain understandable after migration.                           |
| Tax, shipping, and payment context     | Supports customer service, finance review, and operational history         | Historical context should be readable even if future configuration is handled separately. |
| Order statuses                         | Supports fulfillment interpretation and post-launch support                | Source statuses should map to meaningful Phoca Cart statuses or documented equivalents.   |
| Invoice and document references        | Supports administrative continuity where invoices are part of the workflow | Invoice expectations should be reviewed separately from raw order transfer.               |
| Currency and language context          | Matters for cross-border and multilingual stores                           | Orders should preserve enough context for historical interpretation.                      |

Historical orders should not be judged only by totals. If order lines lose selected options, discounts, tax context, payment method, or status meaning, the migration may pass a count check but fail operationally.

### Content, URL, and SEO Data Differences <a href="#content-url-and-seo-data-differences" id="content-url-and-seo-data-differences"></a>

Phoca Cart SEO and storefront continuity depend on both Phoca Cart data and Joomla site structure. Product aliases, category aliases, metadata, menus, modules, multilingual routes, template output, canonical paths, redirects, and SEO-sensitive landing pages can all affect post-migration discoverability.

A source store may store URLs as product slugs, category slugs, collection paths, app-generated routes, CMS pages, or theme-driven landing pages. Phoca Cart operates through Joomla routing and menu exposure, so route planning should be part of migration scope when SEO continuity matters.

| SEO or storefront element | Phoca Cart/Joomla dependency                                  | Migration implication                                                |
| ------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------- |
| Product aliases           | Phoca Cart product fields and Joomla route behavior           | Validate important product URLs, not only product names.             |
| Category aliases          | Phoca Cart categories and menu structure                      | Check category paths and high-value category URLs.                   |
| Metadata                  | Product, category, Joomla page, or custom field ownership     | Confirm where metadata should be stored and displayed.               |
| Landing pages             | Joomla articles, modules, templates, or custom layouts        | Treat content reconstruction separately from product data migration. |
| Multilingual routes       | Joomla language structure and Phoca Cart multilingual content | Validate language-specific products, categories, menus, and URLs.    |
| Template overrides        | Joomla template files and Phoca Cart layout overrides         | Data migration does not recreate custom design logic automatically.  |

Content migration is also relevant when source stores include guides, landing pages, blog-like pages, comparison pages, download pages, or manufacturer pages. Some content may belong in Joomla CMS pages, while product-connected content may belong in Phoca Cart product or category fields. Separating store records from content records prevents unclear scope and poor page ownership.

### App, Extension, Integration, or Custom Data Differences <a href="#app-extension-integration-or-custom-data-differences" id="app-extension-integration-or-custom-data-differences"></a>

Phoca Cart is modular. Payment methods, shipping methods, search behavior, filters, modules, feeds, imports, exports, invoicing, POS-related expectations, newsletters, PDFs, Open Graph behavior, template overrides, and other Joomla extensions can all influence how the store operates. Some of that information is configuration, some is historical data, and some is custom behavior.

| Data or behavior type                     | Standard migration concern                                                       | Scope response                                                                          |
| ----------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Payment and shipping plugin configuration | Future checkout behavior depends on target setup                                 | Configure and test separately from historical order migration.                          |
| Import/export workflows                   | Merchant may rely on XML/CSV processes for operations                            | Confirm whether the workflow is a target implementation requirement.                    |
| POS or offline sales expectations         | Online and offline workflows may share product, stock, order, or invoice meaning | Review operational workflow before treating the migration as ordinary catalog transfer. |
| Custom Joomla fields or tables            | Source meaning may not have a supported Phoca Cart destination                   | Review Custom Service when transformation or custom extraction is required.             |
| External identifiers                      | ERP, POS, accounting, marketplace, or feed systems may rely on stable IDs        | Preserve only where supported or review tailored handling.                              |
| Template overrides and modules            | Storefront appearance and discovery depend on Joomla implementation              | Separate presentation reconstruction from data migration.                               |
| Third-party extensions                    | Data may be outside normal Phoca Cart structures                                 | Identify ownership and supported destination before migration.                          |

Add-ons may help when a requirement fits supported service behavior, such as filtering entities, mapping fields, preserving relevant IDs where supported, or configuring supported migration options. Custom Service should be reviewed when the source includes unsupported extension data, bespoke database structures, external systems, custom code, tailored transformations, or behavior that cannot be represented through standard Phoca Cart fields and configuration.

### How Data Model Differences Affect Migration Scope <a href="#how-data-model-differences-affect-migration-scope" id="how-data-model-differences-affect-migration-scope"></a>

Data model differences affect scope by revealing what can be handled as standard record migration, what needs target configuration, what needs Add-on support, and what needs Custom Service review. Phoca Cart makes this especially important because commerce behavior can be distributed across product records, customer groups, rewards, discounts, plugins, Joomla menus, modules, templates, language structure, and custom extensions.

| Discovery during review                                                             | Likely scope implication                                                   | Best next step                                                                                |
| ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Products are simple and categories are clean                                        | Standard Service may be suitable if supported entities align               | Validate products, categories, customers, and orders through Demo Migration.                  |
| Product options, attributes, specifications, or customer-group prices drive selling | Scope may need deeper sample review or mapping support                     | Include complex product and customer samples before approving Full Migration.                 |
| Tax, shipping, payment, invoice, or currency behavior affects future operations     | Configuration and validation need separate attention                       | Separate historical context from target configuration requirements.                           |
| Joomla menus, modules, templates, or landing pages control discovery                | Storefront readiness may require implementation work beyond data migration | Review presentation and route requirements before launch planning.                            |
| Multilingual content or multicurrency behavior is central                           | Validation samples must include language and currency complexity           | Check products, categories, menus, orders, and customer examples across languages/currencies. |
| Custom fields, third-party extensions, or integrations hold business meaning        | Standard migration may not cover the expected result                       | Review Add-ons or Custom Service before Full Migration.                                       |

A strong Phoca Cart data plan does not try to force every source field into a similar-looking target field. It classifies meaning first. Products, options, attributes, specifications, categories, customers, customer groups, orders, discounts, coupons, reward points, taxes, shipping, payment, invoices, languages, routes, modules, templates, and custom data should each be mapped according to the role they play in the target store.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Phoca Cart data model differences are important because the target store is both a Joomla site and a Phoca Cart commerce environment. Product records, catalog structure, customer groups, benefits, orders, tax, shipping, payment, multilingual content, Joomla routes, modules, template overrides, and custom extensions all shape whether migrated data remains usable.

The safest planning approach is to classify source data by business function before deciding how it should be represented. A product option should remain a shopper choice only when it actually affects buying behavior. A product attribute or specification should support description, filtering, or comparison when that is its real role. A customer group should remain connected to pricing, access, or benefits when those rules matter. Orders should preserve operational evidence, not only totals.

When the source store includes complex products, customer-group pricing, reward points, coupons, tax and shipping rules, multilingual routes, POS expectations, import/export workflows, third-party extensions, custom fields, or external identifiers, scope should be reviewed before Full Migration so Standard Service, Add-ons, Managed Service, and Custom Service boundaries are clear.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why are Phoca Cart data model differences important during migration?**

They affect whether migrated records keep their business meaning. A product, customer, order, category, discount, or tax rule may need a different target structure in Phoca Cart because Phoca Cart works through Joomla, extension configuration, modules, plugins, and storefront presentation.

**Are Phoca Cart options, attributes, specifications, and parameters the same thing?**

No. Options usually affect shopper selection, while attributes and specifications often describe or compare products. Parameters and custom fields may support display, filtering, import/export, or custom behavior. They should be classified by function before mapping.

**Can historical tax, shipping, and payment data be handled like future checkout settings?**

No. Historical order context and future checkout behavior should be reviewed separately. Historical records need readable tax, shipping, payment, and total context, while future checkout depends on configured target tax rates, zones, shipping methods, payment plugins, and currencies.

**Does product migration also cover Joomla menus and storefront routes?**

Not automatically. Product records can migrate successfully while Joomla menus, modules, templates, language routes, and SEO paths still need separate review or implementation work.

**When should Custom Service be considered for Phoca Cart data differences?**

Custom Service should be reviewed when required business meaning lives in unsupported extension data, custom database tables, external identifiers, bespoke product logic, POS or ERP dependencies, custom fields, or transformations that cannot be handled through standard migration capability or supported Add-ons.
