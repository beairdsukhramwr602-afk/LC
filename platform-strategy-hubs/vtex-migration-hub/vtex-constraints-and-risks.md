# VTEX Constraints and Risks

A VTEX migration can fail even when the core records appear to move successfully. The main risk is not only missing products, customers, orders, CMS Pages, or Blog Posts. The larger risk is that migrated data may not behave correctly across VTEX Catalog, SKUs, specifications, trade policies, pricing, promotions, marketplace operations, OMS, logistics, Master Data, apps, APIs, and storefront implementation.

VTEX is a strong Target Platform for merchants with structured catalog, multichannel, marketplace, B2B/B2C, and integration requirements. That strength also creates migration constraints. Product data must become active and sellable. SKUs must preserve purchasable choices. Specifications must support filtering and discovery. Trade policies and pricing must reflect the right commercial context. Orders must remain meaningful inside operational history. Custom fields, Master Data, app data, and external identifiers must be classified before migration scope is approved.

A reliable VTEX migration plan should identify these constraints before Demo Migration, not after Full Migration. The goal is to decide which risks can be handled through standard mapping, which need Add-ons, and which require Custom Service or separate target-side implementation work.

### Why VTEX Migration Risk Is Structural <a href="#why-vtex-migration-risk-is-structural" id="why-vtex-migration-risk-is-structural"></a>

VTEX migration risk is structural because business meaning is distributed across multiple platform layers. A source-store field may look simple, but its target behavior may depend on catalog architecture, SKU activation, sales channel rules, pricing context, OMS status meaning, marketplace ownership, logistics setup, Master Data, or storefront implementation.

| Risk signal                                                                       | Why it matters in VTEX                                                                                                                      | What to confirm before migration                                                                                          |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Product choices affect stock, price, fulfillment, or customization.               | The choice may need SKU, specification, attachment, assembly option, service, kit, app behavior, or custom logic.                           | Whether each choice is a purchasable unit, product detail, customer input, bundle component, service, or custom workflow. |
| Product fields are used for filtering, comparison, search, or merchandising.      | VTEX specifications and category-linked specification groups determine much of catalog discovery.                                           | Which fields must remain structured, searchable, filterable, or operationally useful.                                     |
| The same product is sold under different channels, prices, or availability rules. | Trade policies, pricing, promotions, and marketplace context may change commercial behavior.                                                | Which sales contexts need separate review during Demo Migration.                                                          |
| Marketplace or seller data affects offer ownership or order flow.                 | Marketplace migration is not just product and order transfer. Seller, offer, commission, SKU matching, and channel context may be involved. | Whether marketplace history and seller context must be migrated, configured, integrated, or excluded.                     |
| Custom fields or forms affect checkout, fulfillment, reporting, or integrations.  | Master Data, apps, APIs, and custom checkout behavior may be outside ordinary entity mapping.                                               | Which values are business-critical and which system owns them after launch.                                               |
| Storefront redesign is happening with migration.                                  | VTEX storefront implementation can change navigation, layout, search, URL behavior, and content presentation.                               | Which source content is migrated data and which is target storefront work.                                                |

The safest planning approach is to treat VTEX constraints as business-behavior questions. A record-level migration can succeed technically while still producing weak customer experience, incomplete operations, or unreliable reporting if these behavior questions are not addressed.

### Catalog and SKU Activation Constraints <a href="#catalog-and-sku-activation-constraints" id="catalog-and-sku-activation-constraints"></a>

VTEX catalog quality depends on how products, SKUs, categories, brands, specifications, images, and activation requirements work together. A product may exist in VTEX but still be incomplete, inactive, hard to find, or commercially wrong.

| Constraint                                                                            | Migration risk                                                                                                   | Prevention focus                                                                                              |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Products require usable SKU relationships.                                            | Product pages may display incomplete options, inactive SKUs, wrong SKU images, or unavailable purchasable items. | Test representative products with simple SKUs, multiple SKUs, image variation, and stock-sensitive choices.   |
| SKU activation depends on required catalog information.                               | Migrated SKUs may exist but not be available for sale.                                                           | Confirm required specifications, images, prices, inventory, and activation conditions during Demo Migration.  |
| Source variants may not equal VTEX SKUs.                                              | Product options may be over-split into too many SKUs or flattened into unusable product text.                    | Classify each option by stock, price, fulfillment, display, and customer-input meaning.                       |
| Categories and brands shape discovery.                                                | Product organization may migrate as record structure but fail as shopper navigation.                             | Review department/category/subcategory placement, brand values, and category-specific specification behavior. |
| Attachments, assembly options, services, kits, and collections carry special meaning. | Customization, bundles, paid services, and merchandising groups may be lost or misrepresented.                   | Separate ordinary variant mapping from advanced catalog behavior and Custom Service candidates.               |

Catalog risk is highest when the source store uses custom product builders, bundles, add-on choices, subscription logic, store-specific modifiers, marketplace offer data, or product fields originally created for a different platform architecture. These areas should not be treated as routine product migration until their VTEX meaning is clear.

### Specification, Attribute, and Category-Linked Risk <a href="#specification-attribute-and-category-linked-risk" id="specification-attribute-and-category-linked-risk"></a>

Specifications are one of the most important VTEX migration constraints because they influence filtering, product details, SKU differences, category behavior, and storefront experience. Source attributes should not be moved mechanically into descriptions or generic custom fields when they support discovery or operations.

| Source pattern                                                 | VTEX risk                                                                            | Better review question                                                                                                |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| Large attribute sets with inconsistent values.                 | Filters become noisy, duplicated, incomplete, or difficult to maintain.              | Which values should be normalized, mapped, excluded, or handled as plain product detail?                              |
| Attributes used differently across categories.                 | A specification may be too broad, too narrow, or applied to the wrong product group. | Should the value be category-specific, SKU-specific, product-level, or excluded?                                      |
| Variant-defining attributes mixed with descriptive attributes. | Shoppers may not see correct SKU choices or comparison values.                       | Does the value define a purchasable variation or simply describe the product?                                         |
| Custom operational attributes.                                 | Fulfillment, reporting, or integration values may disappear from usable workflows.   | Does the value need storefront visibility, back-office visibility, external synchronization, or Master Data handling? |
| Inherited or source-specific metadata.                         | Obsolete platform fields may clutter VTEX without business value.                    | Which fields still support commercial, operational, or compliance decisions?                                          |

The risk is not only field loss. The risk is wrong field purpose. A successful VTEX migration should preserve structured values where they matter and avoid carrying unnecessary source-platform noise into the new catalog.

### Pricing, Promotion, Trade Policy, and Channel Risk <a href="#pricing-promotion-trade-policy-and-channel-risk" id="pricing-promotion-trade-policy-and-channel-risk"></a>

VTEX commercial behavior may depend on price tables, promotions, coupons, trade policies, sales channels, B2B/B2C context, marketplace rules, and external pricing authority. A default product price is only one part of the risk picture.

| Commercial area                   | Common risk                                                                        | Prevention focus                                                                                       |
| --------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Base SKU price                    | Price appears correct in one context but not in another.                           | Validate representative SKUs across the expected sales contexts.                                       |
| Price tables and fixed prices     | Customer-specific or channel-specific values are flattened into a single price.    | Confirm whether differentiated pricing should migrate, be configured, or remain external-system owned. |
| Promotions and coupons            | Historical rules are mistaken for launch-ready rules, or active rules are omitted. | Decide which rules must exist after launch and which only explain past order history.                  |
| Trade policies and sales channels | Products are available, unavailable, or priced incorrectly by channel.             | Test the same SKU under the channels, regions, stores, or business contexts that matter.               |
| Marketplace pricing               | Seller, offer, and channel conditions are not represented.                         | Clarify whether marketplace data is migrated, rebuilt, integrated, or excluded.                        |

Pricing and trade-policy risk should be reviewed with business examples. A clean migration of default prices does not prove that B2B pricing, marketplace selling, promotional behavior, sales-channel availability, or ERP-owned pricing will work correctly.

### Marketplace, Seller, OMS, and Logistics Risk <a href="#marketplace-seller-oms-and-logistics-risk" id="marketplace-seller-oms-and-logistics-risk"></a>

VTEX is often used for marketplace, seller, order, fulfillment, and logistics operations. These areas create risk because they connect historical data, operational configuration, seller relationships, shipping behavior, and external systems.

| Operating area                    | What can go wrong                                                                                                                             | How to reduce risk                                                                                                     |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Marketplace and seller context    | Seller ownership, offer relationships, SKU matching, commission meaning, or channel context may be flattened into generic product/order data. | Identify which marketplace records must remain meaningful and which must be rebuilt or integrated.                     |
| OMS order history                 | Historical orders may lose payment, fulfillment, delivery, seller, status, or invoice context.                                                | Validate representative orders from different payment, shipping, fulfillment, cancellation, and marketplace scenarios. |
| Logistics and delivery context    | Shipping methods, warehouse references, pickup/delivery context, or fulfillment rules may not translate directly.                             | Separate historical order readability from live logistics setup for new orders.                                        |
| External ERP/WMS/OMS dependencies | The migration may move data that an external system should own after launch.                                                                  | Define system of record for products, prices, inventory, customers, orders, and fulfillment updates.                   |
| Return or post-order workflows    | Past statuses may not align with target operational workflows.                                                                                | Decide whether historical values are preserved for reference or mapped into operational statuses.                      |

The key constraint is ownership. VTEX may display, process, synchronize, or reference operational data, but not every source-store value should become a migrated VTEX record. Some values should be retained for history, some should be configured in VTEX, and some should remain with connected systems.

### Master Data, Checkout, Apps, and Integration Risk <a href="#master-data-checkout-apps-and-integration-risk" id="master-data-checkout-apps-and-integration-risk"></a>

Master Data, custom checkout fields, apps, APIs, and integrations create some of the most easily underestimated VTEX migration risks. They often hold business-critical information that does not appear in standard product, customer, order, CMS Page, or Blog Post exports.

| Risk area                                 | Why it is risky                                                                                    | Required classification                                                                      |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Master Data records                       | Custom records may support forms, customer context, business workflows, or integration references. | Determine whether the data migrates, is rebuilt, stays external, or requires Custom Service. |
| Custom checkout fields                    | Values may affect fulfillment, compliance, personalization, or reporting.                          | Decide whether the field must display, store, export, synchronize, or trigger behavior.      |
| App-owned data                            | App settings and records may not be part of standard migration scope.                              | Identify whether the app data is migratable, reconfigured, excluded, or custom.              |
| API and middleware references             | External IDs may connect products, customers, orders, inventory, pricing, or fulfillment.          | Confirm which identifiers must be preserved for post-launch synchronization.                 |
| Payment, fraud, tax, or analytics context | Historical labels may be confused with live provider configuration.                                | Separate order-history context from target-side provider setup.                              |

This area often determines whether Standard Service is enough, Add-ons can support the requirement, or Custom Service is needed. The decision should be based on business-critical behavior, not simply on whether a custom field exists.

### Storefront, Content, Search, and URL Risk <a href="#storefront-content-search-and-url-risk" id="storefront-content-search-and-url-risk"></a>

VTEX migration often happens alongside storefront modernization. That can improve the launch outcome, but it also increases risk when source content, navigation, search behavior, or URL structure is assumed to transfer automatically.

| Storefront area      | Migration risk                                                                                                  | Prevention focus                                                                              |
| -------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| CMS Pages            | Source layouts, page-builder structures, scripts, or embedded widgets may not become equivalent target content. | Decide which pages are migrated as content, rebuilt in the storefront, or excluded.           |
| Blog Posts           | Editorial content may lose metadata, authorship, tags, media, or URL structure.                                 | Confirm Blog Posts scope, formatting expectations, and Entity Points impact where applicable. |
| Navigation and menus | Source navigation may not match VTEX category, collection, search, or storefront architecture.                  | Treat navigation as target experience design when needed, not only data transfer.             |
| Search and filters   | Product discovery can weaken if specifications and category logic are not configured well.                      | Test search, filtering, sorting, and product listing pages with difficult catalog examples.   |
| URLs and redirects   | SEO-sensitive product, category, CMS Page, Blog Post, campaign, or landing-page URLs may break.                 | Prioritize high-value URLs and verify redirect destinations, not just redirect existence.     |

The risk is highest when the merchant expects a visual clone of the source storefront. Migration can preserve data, but target storefront behavior, layout, search experience, merchandising modules, and interactive components may require separate implementation work.

### Additional Migration Options and Follow-Up Risk <a href="#additional-migration-options-and-follow-up-risk" id="additional-migration-options-and-follow-up-risk"></a>

Additional Migration Options can be useful when launch timing requires later migration activity. In VTEX, follow-up activity should not be treated as a simple rerun when the catalog, pricing, marketplace, OMS, Master Data, or storefront structures changed after the initial migration review.

Follow-up migration risk is higher when new products introduce new specifications, new SKUs rely on different activation requirements, new pricing rules depend on trade policies, new marketplace records involve seller context, or new custom checkout/Master Data values enter the source store after Demo Migration. In those cases, the follow-up action should include renewed review of the changed structures, not only record transfer.

New Product, Customer, Order, and Blog Posts records consume Entity Points when they are migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when they are migrated for the first time, including when the customer performs a new migration for the same migration path.

### Add-ons, Custom Service, and Constraint Ownership <a href="#add-ons-custom-service-and-constraint-ownership" id="add-ons-custom-service-and-constraint-ownership"></a>

Add-ons and Custom Service should be separated during VTEX risk planning. Add-ons can support eligible mapping, filtering, configuration, or value-handling requirements within available service capability. Custom Service is required when the migration depends on unsupported data structures, Custom Platform interpretation, source-specific logic, custom APIs, app-owned records, marketplace behavior, or Master Data logic that cannot be handled through standard mapping.

| Constraint type            | Usually standard scope when                                                       | Add-ons may help when                                                               | Custom Service is needed when                                                                                     |
| -------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Catalog and SKU data       | Products, SKUs, categories, brands, images, and basic specifications map clearly. | Field transformation, filtering, or supported configuration adjustments are needed. | Product builders, custom bundles, app-owned catalog records, or unsupported SKU logic must be interpreted.        |
| Pricing and channel data   | Default prices and basic channel context are enough.                              | Selective price, rule, or value adjustments fit available capability.               | Pricing depends on custom code, external authority, marketplace conditions, or unsupported account/channel logic. |
| Customer and order history | Standard customer and order fields preserve useful history.                       | Select fields or values need supported mapping.                                     | Master Data, B2B, seller, fulfillment, invoice, or integration meaning must be preserved beyond ordinary history. |
| Storefront and content     | CMS Pages, Blog Posts, and priority URLs have clear target representation.        | Metadata, filtering, or supported content adjustments are needed.                   | Layouts, components, route behavior, search logic, or storefront apps must be rebuilt or custom handled.          |
| Integration context        | External IDs are clear and supported.                                             | Data cleanup or selected mapping support is enough.                                 | Middleware, API workflows, app-owned data, or synchronization rules require custom interpretation.                |

A clear ownership decision prevents scope confusion. Some constraints belong to migration mapping, some belong to Add-ons, some belong to Custom Service, and some belong to target setup or external-system implementation outside ordinary migration scope.

### VTEX Risk Review Matrix <a href="#vtex-risk-review-matrix" id="vtex-risk-review-matrix"></a>

A VTEX migration should include risk review across all major operating layers, not only catalog records. The matrix below helps decide where the project needs deeper planning before Full Migration.

| Review area                       | Low-risk signal                                                 | Higher-risk signal                                                                                                | Review priority                                                       |
| --------------------------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Product/SKU model                 | Simple catalog with clear SKU variations and standard fields.   | Configurators, bundles, services, attachments, assembly options, kits, or inconsistent variants.                  | Validate difficult product samples before scope approval.             |
| Specifications and discovery      | Clean attributes mapped to known product/SKU purposes.          | Noisy attributes, category-specific values, duplicate filters, or operational metadata mixed with display fields. | Normalize and classify fields before Demo Migration.                  |
| Pricing and trade policies        | One main pricing context with limited rules.                    | Multiple trade policies, B2B pricing, promotions, seller conditions, or external price authority.                 | Validate pricing by sales context.                                    |
| Marketplace and seller operations | No marketplace/seller dependency or only historical references. | Seller ownership, offer matching, commission, marketplace orders, or multichannel synchronization.                | Separate historical preservation from live marketplace setup.         |
| OMS and logistics                 | Orders only need readable historical context.                   | Fulfillment status, invoice, delivery, pickup, warehouse, or external OMS/WMS references matter.                  | Validate representative order histories and external ownership.       |
| Master Data and custom checkout   | No business-critical custom records.                            | Custom forms, app-owned data, compliance fields, or integration keys are required.                                | Classify for Add-ons, Custom Service, or exclusion.                   |
| Storefront and URLs               | Content has clear target pages and limited SEO sensitivity.     | Source theme clone expectations, complex landing pages, search behavior, or high-value URL dependencies.          | Separate data migration from storefront implementation.               |
| Follow-up migration handling      | New records are structurally similar to tested samples.         | New records introduce untested specifications, pricing, marketplace, Master Data, or storefront changes.          | Revalidate changed structures before follow-up migration is accepted. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX constraints and risks come from platform structure. Products, SKUs, specifications, pricing, promotions, trade policies, marketplace records, OMS history, logistics context, Master Data, apps, APIs, storefront content, URLs, and external systems can all affect whether migrated data is usable after launch.

A strong VTEX migration plan identifies where data can move through standard mapping, where Add-ons are appropriate, where Custom Service is needed, and where target-side implementation or external-system setup should be handled separately. The highest-risk samples should be tested early: complex products, specification-heavy categories, channel-specific pricing, marketplace orders, B2B/customer context, Master Data records, custom checkout fields, integration identifiers, CMS Pages, Blog Posts, and SEO-sensitive URLs.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Why can a VTEX migration be risky even when products and orders are transferred?**

VTEX data must behave across Catalog, SKUs, specifications, trade policies, pricing, promotions, OMS, logistics, marketplace context, Master Data, apps, APIs, and storefront implementation. Products and orders may exist in the Target Platform but still be incomplete, inactive, incorrectly priced, hard to find, or weak as operational history.

**What is the biggest catalog risk in a VTEX migration?**

The biggest catalog risk is misclassifying source product choices. A choice may need to become a SKU, specification, attachment, assembly option, service, kit, collection, app behavior, or custom logic. Incorrect classification can damage product availability, filtering, pricing, fulfillment, and shopper experience.

**Are VTEX pricing and trade policy risks part of data migration or store configuration?**

They can involve both. Some values may be migrated, some may need supported mapping or Add-ons, and some may belong to target configuration or external pricing systems. The important step is to identify which system owns each commercial value after launch.

**When do VTEX custom fields or Master Data create Custom Service risk?**

Custom Service risk appears when custom fields, Master Data, app-owned records, API references, marketplace data, or checkout values carry business-critical behavior that cannot be preserved through standard migration capability or available Add-ons.

**Should Additional Migration Options be used without rechecking VTEX risks?**

No. If later migration activity introduces new SKUs, specifications, pricing logic, marketplace records, Master Data values, custom checkout fields, or storefront-sensitive content, the changed structures should be reviewed before the follow-up action is treated as low risk.
