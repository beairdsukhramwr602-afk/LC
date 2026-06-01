# J2Store Pre-Migration Preparation Checklist

Preparing for a migration to J2Store requires more than collecting product, customer, and order counts. J2Store v4 / J2Commerce 4 belongs to a Joomla extension environment, where commerce data can depend on Joomla articles, categories, menus, modules, templates, apps, plugins, checkout fields, tax settings, shipping methods, payment methods, customer groups, and storefront presentation decisions.

The goal of preparation is to make those relationships visible before Demo Migration or Full Migration. A clean preparation phase helps the merchant decide what should become standard J2Store data, what should be configured in the target Joomla site, what should be reviewed through Add-ons, and what may require Custom Service because the source behavior is custom, extension-owned, or outside standard service capability.

This checklist is written for the J2Store v4 / J2Commerce 4 target context. J2Commerce 6 should be handled as a separate modern Joomla 6 target because its architecture, plugin model, frontend framework support, and migration assumptions differ from the v4 / J2Commerce 4 branch.

### Preparation Priorities Before Moving to J2Store <a href="#preparation-priorities-before-moving-to-j2store" id="preparation-priorities-before-moving-to-j2store"></a>

The preparation work should begin with target clarity, then move into catalog structure, customer and order meaning, operational configuration, storefront context, and service-path escalation. The strongest preparation documents not only what exists in the Source Platform, but also why it matters after the data appears in J2Store.

| Preparation priority         | What to collect                                                                                                                   | Why it matters for J2Store                                                                                                   |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Target generation            | Joomla version, target J2Store / J2Commerce 4 version, PHP/database environment, required extensions, template assumptions        | Prevents the project from being planned against the wrong J2Store generation or an incompatible Joomla environment.          |
| Product behavior             | Product types, options, variants, downloadable files, advanced pricing, quantity rules, custom fields, and app-driven products    | Shows whether products can be migrated through ordinary structures or need mapping, configuration, or Custom Service review. |
| Joomla content relationships | Product articles, category placement, menus, modules, aliases, metadata, content pages, and layout overrides                      | Helps preserve how shoppers find, read, and purchase products inside Joomla.                                                 |
| Customer and order meaning   | Customer groups, addresses, order statuses, order comments, discounts, tax, shipping, payment, and order-line option details      | Keeps historical data useful for customer service, reporting, and operational reference.                                     |
| Checkout and configuration   | Taxes, shipping methods, payment plugins, coupons, vouchers, checkout fields, email templates, invoice behavior, and status rules | Separates migrated data from target configuration and unsupported custom behavior.                                           |
| Apps and customizations      | Apps, plugins, template overrides, custom code, integrations, external identifiers, and source-specific fields                    | Identifies which requirements belong to standard migration, Add-ons, or Custom Service.                                      |

### 1. Confirm the Target J2Store Environment <a href="#id-1-confirm-the-target-j2store-environment" id="id-1-confirm-the-target-j2store-environment"></a>

Before reviewing records, confirm the exact target environment. For this hub, the target is J2Store v4 / J2Commerce 4. That matters because J2Commerce 6 is a separate Joomla 6-native rebuild with different architecture and plugin expectations. Treating v4 and v6 as the same destination can produce the wrong preparation checklist, the wrong service-path decision, and the wrong validation samples.

#### Record the Joomla and extension baseline <a href="#record-the-joomla-and-extension-baseline" id="record-the-joomla-and-extension-baseline"></a>

Document the current Source Platform, the intended Joomla version, the target J2Store or J2Commerce 4 version, PHP and database requirements, the active Joomla template, and any required extensions. If the project includes a Joomla upgrade, record whether the upgrade happens before, during, or after the migration.

A migration into J2Store is safer when the target Joomla site is already prepared enough to receive and review migrated records. The merchant does not need every design detail finished before Demo Migration, but the target should be stable enough to test products, categories, account pages, checkout paths, and representative storefront routes.

#### Separate v4 continuity from v6 modernization <a href="#separate-v4-continuity-from-v6-modernization" id="separate-v4-continuity-from-v6-modernization"></a>

If the merchant is actually planning to use J2Commerce 6, pause the v4 preparation path and use the separate J2Commerce 6 hub instead. J2Commerce 6 has its own requirements, migration logic, plugin architecture, and validation priorities. The v4 / J2Commerce 4 hub should not become a mixed-version checklist.

For v4 continuity, the preparation focus is the legacy Joomla extension model: existing product structures, apps, plugins, templates, modules, checkout behavior, and operational settings that must make sense inside J2Store.

### 2. Prepare the Product Catalog as Selling Structure <a href="#id-2-prepare-the-product-catalog-as-selling-structure" id="id-2-prepare-the-product-catalog-as-selling-structure"></a>

Product preparation should classify the catalog by behavior, not only by quantity. A source store with 500 simple products may be easier to migrate than a store with 50 products that use advanced options, downloads, subscriptions, bookings, customer-group pricing, or app-owned behavior.

#### Identify product types and product behavior <a href="#identify-product-types-and-product-behavior" id="identify-product-types-and-product-behavior"></a>

Create a product-behavior inventory. Group products by how shoppers buy them and how the merchant manages them after launch. Include simple products, variable products, configurable products, advanced variable products, flexible variable products, downloadable products, subscription-like products, booking or reservation products, grouped or bundled products, donation-style products, and any product controlled by apps or custom code.

For each group, select representative products for Demo Migration. The samples should include clean products and edge cases. A Demo Migration that only uses simple products will not prove whether option-heavy products, downloadable files, or advanced pricing can be trusted.

#### Review options, variants, and custom fields <a href="#review-options-variants-and-custom-fields" id="review-options-variants-and-custom-fields"></a>

Product options can carry several meanings. They may represent size, color, material, file upload fields, personalization text, bundle choices, price modifiers, stock distinctions, shipping differences, or order-line instructions. J2Store preparation should identify what each option means before migration.

Custom fields and app-owned fields need the same review. Some source fields may map clearly into the target structure. Others may require Advanced Data Mapping, Advanced Data Configure, or Custom Service if the field controls business logic, product behavior, or operational workflow.

#### Prepare product media and downloadable files <a href="#prepare-product-media-and-downloadable-files" id="prepare-product-media-and-downloadable-files"></a>

Review product images, gallery images, option-specific images, downloadable files, and any access rules tied to digital products. Downloadable products can depend on payment status, order status, access limits, expiry behavior, file location, and customer account access. If the source store stores files outside ordinary product records, document where those files live and how the merchant expects customers to access them after migration.

#### Clean category and discovery structure <a href="#clean-category-and-discovery-structure" id="clean-category-and-discovery-structure"></a>

Prepare categories, manufacturers, tags or filters where relevant, related products, product ordering, and product discovery modules. J2Store storefront discovery often depends on Joomla categories, menu items, modules, and template output, so category preparation should include both data structure and storefront use.

### 3. Prepare Customer, Group, and Order Evidence <a href="#id-3-prepare-customer-group-and-order-evidence" id="id-3-prepare-customer-group-and-order-evidence"></a>

Customer and order preparation should preserve operational meaning. Names, emails, and order IDs are only the starting point. A useful migration result should help the merchant understand who bought what, under which pricing conditions, with which options, taxes, discounts, shipping, payment references, and order statuses.

#### Document customer groups and pricing consequences <a href="#document-customer-groups-and-pricing-consequences" id="document-customer-groups-and-pricing-consequences"></a>

Customer groups are especially important when they control pricing, discounts, tax treatment, product visibility, access rules, membership behavior, or wholesale/B2B workflows. Record each group and explain what it changes in the store.

If the Source Platform uses customer groups differently from J2Store, clarify whether each group should be mapped directly, renamed, merged, split, or reviewed through Custom Service. A group assignment without its pricing or access meaning may produce a misleading target result.

#### Select order samples that reveal real behavior <a href="#select-order-samples-that-reveal-real-behavior" id="select-order-samples-that-reveal-real-behavior"></a>

Order samples should include recent orders, older orders, orders from important customers, orders from each customer group, orders with discounts, orders with coupons or vouchers, orders with product options, orders with downloadable products, refunded or cancelled orders if relevant, orders with unusual tax or shipping behavior, and orders tied to custom statuses or app-owned fields.

The purpose is not to validate every order before migration. The purpose is to choose samples that reveal whether J2Store will preserve enough order meaning for customer service, finance reference, fulfillment questions, and internal review.

#### Prepare checkout-field and address evidence <a href="#prepare-checkout-field-and-address-evidence" id="prepare-checkout-field-and-address-evidence"></a>

If the source store uses custom checkout fields, customer profile fields, delivery notes, company fields, VAT fields, address rules, or customer-uploaded information, document what each field means and where it should appear after migration. Some checkout information may belong to customer records. Some belongs to order history. Some may be configuration or implementation work rather than migrated data.

### 4. Prepare Operational Configuration Separately from Migrated Data <a href="#id-4-prepare-operational-configuration-separately-from-migrated-data" id="id-4-prepare-operational-configuration-separately-from-migrated-data"></a>

A common preparation mistake is assuming that operational behavior will migrate exactly because related records exist. Taxes, shipping methods, payment methods, discounts, coupons, vouchers, order statuses, invoices, email templates, and checkout rules may need target configuration even when source data can be migrated.

#### Tax, shipping, and payment planning <a href="#tax-shipping-and-payment-planning" id="tax-shipping-and-payment-planning"></a>

Prepare a list of tax rules, geo zones, rates, exemptions, shipping methods, shipping conditions, payment methods, payment status behavior, and third-party provider references. Identify which rules are needed for historical order interpretation and which are needed for future checkout behavior.

Historical order data and future checkout behavior should be treated separately. An old order may need its tax, shipping, and payment context preserved for reference. A new order after launch depends on the target J2Store configuration and active plugins.

#### Discount, coupon, voucher, and status planning <a href="#discount-coupon-voucher-and-status-planning" id="discount-coupon-voucher-and-status-planning"></a>

Document discount logic, coupon usage, voucher behavior, special pricing, advanced pricing, and order statuses. Include examples that show how these rules affected real orders. If the source platform used app-based discount logic or custom status workflows, mark those items for review instead of assuming they can be recreated through ordinary migration settings.

#### Email, invoice, and document expectations <a href="#email-invoice-and-document-expectations" id="email-invoice-and-document-expectations"></a>

If the merchant depends on order confirmation emails, invoice templates, delivery notes, packing slips, downloadable documents, or custom customer notifications, record which items are migration expectations and which are target configuration tasks. These items often belong to implementation and configuration, not record migration alone.

### 5. Prepare Joomla Storefront and SEO Context <a href="#id-5-prepare-joomla-storefront-and-seo-context" id="id-5-prepare-joomla-storefront-and-seo-context"></a>

Because J2Store operates inside Joomla, storefront preparation should cover content and presentation. The migration can preserve product data while the customer-facing experience still needs Joomla menu, module, template, and route planning.

#### Identify high-value storefront paths <a href="#identify-high-value-storefront-paths" id="identify-high-value-storefront-paths"></a>

List important product pages, category pages, landing pages, content pages, internal links, menu paths, campaign URLs, search-result pages, and organic search entry points. Mark the URLs or routes that must be preserved, redirected, or deliberately rebuilt.

If a source store has strong SEO traffic, do not wait until validation to discover route changes. Prepare the route and redirect evidence before migration so Demo Migration can be interpreted realistically.

#### Inventory modules, templates, and overrides <a href="#inventory-modules-templates-and-overrides" id="inventory-modules-templates-and-overrides"></a>

Prepare a list of Joomla modules used for product discovery, category navigation, search, featured products, related products, account access, promotions, or checkout support. Also document templates, sub-templates, overrides, content plugins, and design dependencies that affect storefront output.

The preparation question is not whether Next-Cart migrates a design. The question is whether the migrated data will support the target storefront implementation once Joomla menus, modules, templates, and layouts are configured.

### Demo Migration Sample Planning <a href="#demo-migration-sample-planning" id="demo-migration-sample-planning"></a>

Demo Migration should test meaning, not just movement. The sample set should show whether the target J2Store environment can interpret real store behavior.

| Sample type                    | Include examples such as                                                                                           | What the sample should prove                                       |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| Simple products                | Ordinary products with basic price, image, stock, and category assignment                                          | Basic catalog records are readable and manageable.                 |
| Option-heavy products          | Products with size/color choices, price modifiers, personalization fields, or option-level instructions            | Product choice behavior and order-line meaning can be interpreted. |
| Advanced product types         | Downloadable products, subscription-like items, bookings, configurable products, or app-driven products            | Non-standard product behavior is identified before Full Migration. |
| Customer groups                | Wholesale, member, loyalty, tax-exempt, or restricted-access customer groups                                       | Customer segmentation and pricing context are not lost.            |
| Orders with complexity         | Discounts, coupons, vouchers, taxes, shipping, payment references, refunds, custom statuses, and option selections | Historical order meaning remains useful after migration.           |
| Joomla storefront paths        | Key product pages, category routes, menus, modules, and content-to-product journeys                                | Migrated records can support the intended Joomla storefront.       |
| Custom or extension-owned data | Custom fields, app data, external IDs, third-party references, or custom checkout fields                           | Add-on or Custom Service needs are discovered early.               |

A strong sample set should include both clean records and difficult records. Clean records prove basic movement. Difficult records prove whether the migration plan is strong enough for the store the merchant actually runs.

### What to Escalate Before Execution <a href="#what-to-escalate-before-execution" id="what-to-escalate-before-execution"></a>

Escalation is not a failure. It is a way to keep the migration approach aligned with the real structure of the source store.

#### Escalate for Add-on review <a href="#escalate-for-add-on-review" id="escalate-for-add-on-review"></a>

Review Add-ons when the source data needs filtering, mapping, or configuration support that fits available Standard Add-on capability. The Data Filter Add-on may help when the merchant wants to exclude or narrow eligible records. Advanced Data Mapping may help when source values need clearer target alignment. Advanced Data Configure may help when supported behavior needs configuration beyond ordinary settings.

#### Escalate for Custom Service review <a href="#escalate-for-custom-service-review" id="escalate-for-custom-service-review"></a>

Review Custom Service when the migration involves Custom Platform source data, unsupported app-owned data, custom fields that control behavior, bespoke product logic, source-specific checkout workflows, third-party identifiers, external systems, custom Joomla development, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.

Custom Service is the broader path for requirements that cannot be handled as standard migration capability or Standard Add-on capability. It should be reviewed before Full Migration when the source store contains business meaning that cannot be safely inferred from ordinary records.

#### Escalate for Managed Service review <a href="#escalate-for-managed-service-review" id="escalate-for-managed-service-review"></a>

Managed Service may be safer when the merchant wants Next-Cart-led execution but the migration still fits standard service capability and purchased Add-ons. This can be useful when the store is not custom enough for Custom Service, but the merchant wants expert execution and interpretation of Demo Migration results.

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

The preparation sequence should move from identity and environment to data, behavior, and validation samples.

1. Confirm the target generation as J2Store v4 / J2Commerce 4.
2. Record Joomla, PHP, database, template, and extension readiness.
3. Inventory product types, options, variants, downloadable files, pricing rules, and app-owned product behavior.
4. Review categories, manufacturers, filters, specifications, related products, and discovery structure.
5. Document customer groups, customer records, addresses, checkout fields, and customer-account expectations.
6. Select order samples with discounts, taxes, shipping, payment references, statuses, options, and refunds where relevant.
7. Separate migrated data expectations from target configuration work for tax, shipping, payment, coupons, vouchers, invoices, email templates, and checkout rules.
8. Inventory Joomla menus, modules, templates, overrides, content pages, aliases, metadata, and SEO-sensitive routes.
9. Identify app data, custom fields, external identifiers, and Custom Platform source elements.
10. Choose Demo Migration samples that include both normal and difficult records.
11. Review whether Standard Service, Managed Service, Add-ons, or Custom Service is the right starting approach.

### Conclusion <a href="#conclusion" id="conclusion"></a>

J2Store preparation should make store behavior visible before migration begins. Products, product types, options, downloadable files, customer groups, orders, checkout fields, tax rules, shipping methods, payment plugins, apps, modules, templates, content paths, and Joomla version context all influence whether the migrated result will be useful.

A strong preparation phase prevents Demo Migration from being judged too narrowly. It helps the merchant see what is standard data, what needs configuration, what depends on Joomla implementation, and what requires Add-on or Custom Service review. That clarity is especially important for a v4 / J2Commerce 4 target because legacy apps, plugins, templates, and version compatibility can carry business meaning that ordinary record counts do not show.

Before starting Full Migration, use Demo Migration to test representative J2Store records and Joomla storefront context. If the source store includes complex product types, app-owned behavior, custom checkout fields, customer-group pricing, downloadable products, unsupported extension data, Custom Platform source data, or major version-transition requirements, contact Next-Cart through Live Chat so the migration path and service approach are reviewed before execution.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating to J2Store?**

Confirm the target generation, Joomla environment, and target extension version first. J2Store v4 / J2Commerce 4 and J2Commerce 6 should not be planned as the same target because their architecture and compatibility assumptions differ.

**Why should products be grouped by behavior before migration?**

J2Store product complexity depends on how products are sold and managed. Simple products, variable products, downloadable products, subscription-like items, bookings, and app-driven products may require different preparation, mapping, configuration, and validation.

**Should Joomla pages and modules be prepared before migration?**

Yes. J2Store operates inside Joomla, so product pages, content pages, menus, modules, templates, aliases, metadata, and storefront routes can affect whether migrated data becomes usable in the final store.

**What should be included in a J2Store Demo Migration sample?**

Include simple products, option-heavy products, advanced product types, customer groups, orders with discounts or tax/shipping/payment complexity, important storefront paths, and custom or extension-owned data. The sample should test business meaning, not only record presence.

**When should Custom Service be reviewed for a J2Store migration?**

Custom Service should be reviewed when the source store includes Custom Platform data, unsupported app-owned data, custom fields that control behavior, bespoke product logic, third-party identifiers, custom checkout workflows, external systems, Tailored Add-ons, Custom Add-ons, or custom migration logic adjustment.
