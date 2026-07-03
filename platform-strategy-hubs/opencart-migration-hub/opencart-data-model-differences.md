# OpenCart Data Model Differences

OpenCart migration is not only a transfer of products, customers, orders, and content into another admin panel. It is a translation of storefront meaning into a Target Platform where catalog records, buying choices, descriptive information, discovery tools, customer groups, routes, layouts, and extensions each have different jobs.

A source store can appear simple because many details are stored in the same product field, theme behavior, module setting, or custom database area. OpenCart expects more deliberate separation. Product options support customer-selectable choices. Attributes support product information and comparison. Filters support product discovery. Categories shape browse paths. SEO keywords influence route behavior. Customer groups may affect commercial rules. Extensions and modifications can carry business logic that is not part of ordinary catalog data.

That separation is useful when it is planned. It makes the migrated store easier to manage and validate. It becomes risky when source data is copied without deciding what each value should mean inside OpenCart.

### Why OpenCart data meaning requires translation <a href="#why-opencart-data-meaning-requires-translation" id="why-opencart-data-meaning-requires-translation"></a>

OpenCart is flexible, but the flexibility is organized through several specialized data layers. A migrated product is not complete merely because the name, price, image, and description appear in the admin. The product must still support the correct choice structure, discovery behavior, category placement, route meaning, customer context, and storefront presentation.

The most important data-model difference is that OpenCart separates **buying decisions**, **product knowledge**, and **discovery behavior**. These layers may have been blended together in the Source Platform. During migration, the same source value may need to become an option, an attribute, a filter value, a category assignment, a manufacturer reference, custom data, or extension-related information depending on what the business needs customers and staff to do with it.

| Source-side value pattern                                                     | OpenCart interpretation question                                         | Migration consequence                                                                                                         |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Size, color, finish, warranty length, bundle choice, add-on selection         | Is the value a customer-selectable buying choice?                        | It may need to become an OpenCart option with correct option values and price, stock, weight, or required-selection behavior. |
| Material, compatibility, dimensions, technical specification, model detail    | Is the value informational or comparative?                               | It usually belongs closer to attributes or product details, not selectable options.                                           |
| Use case, product type, specification group, compatibility group              | Should customers narrow catalog lists by this value?                     | It may need to become a filter or support filter planning.                                                                    |
| Brand, supplier, maker, product line                                          | Does it support customer trust or brand browsing?                        | It may need manufacturer review, not only text preservation.                                                                  |
| Old path, readable slug, campaign URL, search landing path                    | Does the path carry SEO or customer-intent value?                        | It needs route and redirect planning, not only target URL generation.                                                         |
| Module field, custom table value, checkout behavior, theme-controlled display | Is the value native OpenCart data or outside ordinary supported records? | It may need Add-ons, Custom Service, or manual target configuration depending on scope.                                       |

The purpose of migration review is therefore not to force every source field into the nearest OpenCart field. The purpose is to preserve the business meaning of the source store in a structure OpenCart can operate, display, and maintain.

### Product records and selectable options <a href="#product-records-and-selectable-options" id="product-records-and-selectable-options"></a>

OpenCart product records can contain many administrative and storefront-facing elements, including general product information, data fields, links, attributes, options, discounts, specials, images, reward points, SEO fields, and design-related settings. That broad product area can make migration look straightforward, but the internal distinction between product fields matters.

Options are especially important because they affect how customers select and purchase a product. A source store may describe size, color, engraving, file format, bundled accessory, service add-on, or configuration choice in many different ways. In OpenCart, the migration question is whether the value should become a customer-facing option and whether that option affects stock, price, points, weight, or required checkout behavior.

A product can migrate with the correct title and image while still failing commercially if its options are wrong. For example, a shirt with visible size text but no selectable size option is not functionally equivalent to the source product. A configurable product with copied option labels but missing price adjustments may appear complete until customers select the wrong variant. A required option that becomes optional can allow invalid orders. An option that should subtract stock but does not can create fulfillment problems.

OpenCart option planning should therefore answer four questions:

| Question                                                 | Why it matters                                                                          |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Is the value a choice customers make before purchase?    | Prevents buyable variations from being buried as plain description or attributes.       |
| Does the choice affect price, stock, points, or weight?  | Protects checkout, inventory, fulfillment, and margin assumptions.                      |
| Is the option required or optional?                      | Prevents invalid cart behavior and incomplete product selections.                       |
| Is the option native data or extension-managed behavior? | Determines whether ordinary migration, Add-ons, or Custom Service review may be needed. |

This is why product-option review belongs at the center of OpenCart data-model migration. Product presence is only the first proof. Buyable product behavior is the real proof.

### Attributes, filters, and product understanding <a href="#attributes-filters-and-product-understanding" id="attributes-filters-and-product-understanding"></a>

Attributes and filters should not be treated as spare storage for product details. They support different parts of the customer journey.

Attributes describe products. They help customers and store teams compare or understand product qualities such as material, dimension, compatibility, capacity, technology, style, or specification. Attribute groups can help organize these details so they are not displayed as an uncontrolled list.

Filters support discovery. They help customers narrow products within catalog pages. A filter value is useful only when it matches how customers actually search and compare. If filters are migrated from inconsistent source values, customers may see too many choices, missing choices, duplicate values, or values that do not narrow the catalog meaningfully.

The common migration mistake is to preserve all values while losing their purpose. A value that belongs in attributes may be unhelpful as a filter. A value that customers need for filtering may be buried in product description. A value that should be a selectable option may be migrated as an attribute and become non-buyable.

| OpenCart layer | Primary role                         | Failure signal                                                                                           |
| -------------- | ------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| Options        | Purchase selection                   | Customers cannot choose the correct product configuration, or checkout accepts invalid selections.       |
| Attributes     | Product understanding and comparison | Product specifications exist but are inconsistent, hard to compare, or placed in the wrong group.        |
| Filters        | Catalog narrowing                    | Customers can see the catalog but cannot narrow products by the criteria that matter.                    |
| Descriptions   | Narrative product explanation        | Important structured data is hidden in long text and cannot support selection, comparison, or filtering. |

A high-quality OpenCart migration should preserve the source catalog’s commercial meaning while improving classification discipline where the source store was inconsistent.

### Categories, manufacturers, and browse structure <a href="#categories-manufacturers-and-browse-structure" id="categories-manufacturers-and-browse-structure"></a>

OpenCart categories are more than containers for products. They shape browsing, product grouping, SEO-sensitive landing pages, and storefront navigation. Category hierarchy, product assignments, category naming, sort behavior, and SEO-related route planning can all affect whether migrated products remain discoverable.

The migration risk is subtle because categories can exist without preserving the original browse journey. Products may be assigned to the wrong categories. Legacy categories may be carried over even though they no longer support useful navigation. Important category landing pages may lose their product mix or route relevance. Overlapping categories may become harder to manage after migration.

Manufacturers also require context. In some stores, manufacturers are simple reference values. In others, they support brand trust, catalog browsing, replacement-part discovery, supplier context, or customer comparison. The correct migration treatment depends on how the source store uses manufacturer data commercially.

A useful OpenCart category/manufacturer review should focus on outcomes:

| Data area              | Review focus                                                              | Pass condition                                                                    |
| ---------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Category hierarchy     | Parent-child structure, naming, active categories, landing-page relevance | Customers can still reach important product groups through logical paths.         |
| Product assignments    | Placement of representative and high-value products                       | Key products appear in the right browse contexts.                                 |
| Manufacturer data      | Brand or supplier meaning                                                 | Manufacturer pages or references still support discovery or trust where relevant. |
| SEO route relationship | Product, category, manufacturer, and information-page route meaning       | Important old destinations map to relevant target destinations.                   |

This review should not aim to preserve every old structure blindly. It should preserve useful catalog logic and identify structures that should be cleaned, redirected, consolidated, or handled separately.

### Customers, customer groups, and commercial context <a href="#customers-customer-groups-and-commercial-context" id="customers-customer-groups-and-commercial-context"></a>

Customer migration into OpenCart is not only account migration. Customer groups can influence how the store organizes customers and how commercial rules are applied. For some merchants, groups are minor administrative labels. For others, they reflect wholesale accounts, member tiers, regional customers, tax-sensitive customers, price-treatment groups, or customer-specific expectations.

If customer groups are copied without understanding their original role, the target store may preserve labels while losing commercial meaning. A wholesale customer may arrive as a normal retail customer. A member group may exist but no longer connect to intended pricing or access behavior. A tax-sensitive customer segment may need target configuration beyond the account record.

The safest review pattern is to sample representative customers from each meaningful group and compare account identity, group assignment, order history expectations, email/account status, and customer-facing behavior.

| Customer data layer         | OpenCart migration question                                                                          |
| --------------------------- | ---------------------------------------------------------------------------------------------------- |
| Customer account            | Does the account remain identifiable and usable in the expected customer context?                    |
| Customer group              | Does the group still mean the same commercial thing after migration?                                 |
| Order history               | Can staff and customers interpret historical orders without relying on missing source-side behavior? |
| Pricing/access expectations | Does the target store require configuration beyond migrated records?                                 |

This distinction matters because a data migration can preserve customer records while still requiring target-side setup for the commercial rules attached to those customers.

### Orders, statuses, discounts, and historical interpretation <a href="#orders-statuses-discounts-and-historical-interpretation" id="orders-statuses-discounts-and-historical-interpretation"></a>

OpenCart order history should be reviewed as operational history, not only as a list of past transactions. Staff may rely on historical orders for customer service, returns, repeat purchases, warranty review, tax/accounting reference, and fulfillment context.

Order migration can be complicated when the source store uses statuses, payment labels, shipping methods, coupons, store credits, reward points, partial fulfillment, subscriptions, or extension-driven checkout logic in ways that do not map cleanly into OpenCart’s ordinary structures.

Historical orders do not always need to recreate every old checkout behavior. However, they should remain understandable. Staff should be able to identify what was purchased, who purchased it, the order state, pricing/tax/shipping context where migrated, and whether any value is historical reference rather than active target behavior.

| Order-related area              | Migration meaning to confirm                                                                   |
| ------------------------------- | ---------------------------------------------------------------------------------------------- |
| Order status                    | Whether source statuses remain understandable in OpenCart reporting and customer service.      |
| Coupons/discounts/specials      | Whether historical discount context is preserved separately from active promotion setup.       |
| Payment/shipping labels         | Whether historical labels are reference records or active target configuration.                |
| Recurring/subscription behavior | Whether the source behavior is native, extension-managed, or outside ordinary migration scope. |

The practical goal is to prevent staff from misreading migrated order history as current operational configuration.

### Multi-store, layouts, and storefront scope <a href="#multi-store-layouts-and-storefront-scope" id="multi-store-layouts-and-storefront-scope"></a>

OpenCart can support multiple stores from one installation. This creates a data-model question that many migrations underestimate: does a record belong everywhere, or only in a specific storefront context?

Multi-store scope can affect product placement, categories, information pages, layouts, settings, design assignments, routes, and storefront experience. If the source store had multiple brands, languages, regions, audiences, or domain-specific catalog differences, the target structure needs scope rules before migration is judged successful.

Layouts and design assignments also matter because OpenCart storefront presentation may depend on more than raw catalog data. A product, category, or information page may exist, but its intended display can change if layout assignments, theme behavior, or extension-controlled presentation do not follow.

Multi-store and layout review should not become a design rebuild. The migration-specific point is to identify when data placement and presentation meaning depend on store context.

### SEO keywords, information pages, and route meaning <a href="#seo-keywords-information-pages-and-route-meaning" id="seo-keywords-information-pages-and-route-meaning"></a>

OpenCart SEO keyword behavior makes route planning part of data-model translation. Products, categories, manufacturers, and information pages can carry SEO-sensitive route meaning. A migration should not treat these paths as decoration.

The important distinction is between preserving a string and preserving intent. A source URL may have earned traffic because it represented a product family, category landing page, brand page, buying guide, policy page, or campaign destination. OpenCart routes and redirects should maintain the most relevant destination for that intent.

Information pages also deserve attention. Many stores use content pages for shipping policies, return policies, size guides, warranty information, brand content, or buying guidance. If those pages are migrated without route review, navigation review, and content-placement review, customers may still lose supporting information that affects conversion.

A route review should prioritize high-value pages first, then representative samples from product, category, manufacturer, and information-page groups. Complete URL preservation is not always possible, but destination relevance should be planned and validated.

### Extensions, modifications, and custom data <a href="#extensions-modifications-and-custom-data" id="extensions-modifications-and-custom-data"></a>

OpenCart stores often rely on extensions, themes, OCMOD/vQmod modifications, custom fields, custom database tables, or integration logic. These areas are the most likely to create data-model ambiguity because the business outcome may not live in ordinary OpenCart product, customer, order, category, or content fields.

A migration should classify each dependency according to its role:

| Dependency type            | Migration treatment question                                                                       |
| -------------------------- | -------------------------------------------------------------------------------------------------- |
| Native OpenCart data       | Can the value be represented by ordinary supported target structures?                              |
| Extension-managed value    | Is the data accessible, documented, and supported for migration?                                   |
| Theme/display behavior     | Does it affect visible data meaning or only target-side presentation?                              |
| Modification/custom code   | Does it change data structure, checkout logic, catalog behavior, or admin workflow?                |
| External-system identifier | Must the identifier remain usable for ERP, marketplace, PIM, accounting, or fulfillment workflows? |

Some dependencies can be handled through configuration or supported Add-ons. Others require Custom Service because they involve unsupported records, custom fields, bespoke transformation, Custom Platform handling, or custom migration logic adjustment. The important point is to classify the dependency before migration, not after a missing behavior appears in validation.

### Conclusion <a href="#conclusion" id="conclusion"></a>

OpenCart data-model migration succeeds when the target store preserves commercial meaning, not just record presence. Products need correct buyable options. Attributes need to support understanding. Filters need to support discovery. Categories and manufacturers need to preserve useful browse context. Customer groups need to retain commercial meaning. SEO keywords and routes need destination relevance. Extensions, themes, and modifications need scope classification before they are assumed to be part of ordinary migration.

A strong OpenCart migration therefore starts with data interpretation. The merchant should know which source values become native OpenCart structures, which become configuration, which require Add-ons, and which need Custom Service because they depend on custom or extension-managed behavior.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Are OpenCart options the same as attributes?**

No. Options support customer-selectable product choices, while attributes support product information and comparison. Treating them as interchangeable can make products appear migrated while weakening the buying journey or product comparison experience.

**Do filters need separate migration planning?**

Yes, when catalog discovery matters. Filters affect how customers narrow product lists, so they should be reviewed against real customer shopping behavior rather than treated as extra metadata.

**Why do customer groups matter in OpenCart migration?**

Customer groups can carry commercial meaning such as wholesale treatment, member status, tax context, or pricing expectations. The group name alone is not enough; the target behavior attached to the group must also be understood.

**Can OpenCart SEO keywords replace redirect planning?**

No. SEO keywords support readable routes, but migration still needs redirect and destination planning for high-value source URLs. The goal is to preserve customer and search intent, not only create readable target paths.

**When does OpenCart custom data require Custom Service?**

Custom Service becomes relevant when important data depends on unsupported extension records, custom fields, custom database structures, external identifiers, bespoke transformation, or custom migration logic adjustment beyond ordinary supported behavior.
