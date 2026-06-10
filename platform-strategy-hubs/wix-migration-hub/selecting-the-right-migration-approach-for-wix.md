# Selecting the Right Migration Approach for Wix

Choosing the right migration approach for Wix depends on how much of the current store can move into standard Wix structures and how much must be adjusted, rebuilt, configured, or reviewed separately. Wix is a hosted website and commerce Target Platform, so a successful migration is not defined only by moving product, customer, order, CMS Pages, or Blog Posts. The selected approach must also account for Wix Stores setup, storefront structure, checkout readiness, apps, Velo behavior, API dependencies, SEO continuity, and any external systems that support daily operations.

A simple Wix migration may fit standard service capability when the source data is clean, the target structure is predictable, and the merchant can configure the new Wix site after migration. A more complex Wix migration needs stronger planning when products use advanced options or modifiers, when customer meaning depends on members and contacts, when orders need careful payment or fulfillment context, when SEO continuity is sensitive, or when business behavior depends on apps, Velo, APIs, or external systems.

### What the Migration Approach Must Decide <a href="#what-the-migration-approach-must-decide" id="what-the-migration-approach-must-decide"></a>

The migration approach should define who performs the migration process, which parts fit standard service capability, which optional Add-ons are needed, and which requirements require Custom Service because customization or modification is involved.

For Wix, the decision should answer four practical questions:

1. Can the current store data fit Wix Stores, Wix content, and Wix customer structures without custom transformation?
2. Can the merchant prepare and configure the target Wix environment without Next-Cart-led execution?
3. Are filtering, mapping, or data configuration needs covered by available Add-ons?
4. Do product logic, app data, Velo behavior, API dependencies, external identifiers, SEO transformation, or custom business rules require Custom Service?

The answer may be different for different parts of the same project. A store can have standard products and orders, while still requiring Custom Service for app-owned records, custom product configuration, membership logic, or integration-sensitive identifiers.

### When Standard Service Is Usually Enough <a href="#when-standard-service-is-usually-enough" id="when-standard-service-is-usually-enough"></a>

Standard Service is usually suitable when the migration path is predictable and the merchant is comfortable performing the migration process on the Next-Cart website. It works best when the source data can be interpreted inside Wix without custom migration logic adjustment.

For Wix, Standard Service is usually strongest when the store has:

* products that can map into Wix Stores products without unusual transformation;
* product options and variants that can be represented clearly in Wix;
* categories or collections that do not require custom storefront discovery logic;
* customers and orders that mainly need readable historical continuity;
* CMS Pages and Blog Posts that fit supported content migration scope;
* payment, shipping, tax, checkout, and fulfillment behavior that the merchant will configure directly in Wix;
* limited dependency on app-owned records, Velo custom code, or external system identifiers.

Standard Service does not mean every business behavior from the source store automatically becomes live Wix behavior. It means the migration can be performed within standard service capability, while target-site configuration remains a separate responsibility.

| Wix migration condition                    | Why Standard Service may fit                                                                                              |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| Clean catalog structure                    | Products, images, prices, SKUs, and inventory can be checked in Wix without heavy transformation.                         |
| Predictable options and variants           | Customer-selectable choices can be reviewed through product pages and cart behavior.                                      |
| Straightforward customer and order history | Customers and orders mainly need to remain readable for store management and service history.                             |
| Simple content continuity                  | CMS Pages and Blog Posts can be reviewed as migrated content rather than rebuilt design systems.                          |
| Merchant-led target setup                  | The merchant can configure Wix payments, shipping, tax, checkout, apps, store pages, and design settings after migration. |

### When Managed Service Is the Safer Approach <a href="#when-managed-service-is-the-safer-approach" id="when-managed-service-is-the-safer-approach"></a>

Managed Service is useful when the migration still fits standard service capability, but the merchant wants Next-Cart-led execution. It is not the same as Custom Service. Managed Service changes who performs the migration process; it does not automatically add custom transformation, app-data handling, Velo development, storefront design work, or bespoke integration logic.

For Wix, Managed Service is often safer when the merchant wants help executing a migration that includes a larger catalog, multiple content types, many products with variants, or a meaningful order history, but the project still remains inside standard service capability.

Managed Service can be appropriate when:

* the merchant wants Next-Cart’s technician to run the migration process;
* the data is standard enough for normal Wix target structures;
* the merchant still expects to configure Wix payments, shipping, tax, store pages, apps, and design settings separately;
* the project includes purchased Standard Add-ons that remain within their available settings and supported behavior;
* the merchant wants a more guided execution path without custom migration logic adjustment.

Managed Service should not be chosen merely because the store is complex. If complexity requires tailored behavior, modified Add-ons, app-owned data handling, Velo/API work, or custom field transformation, the requirement moves into Custom Service because customization is required.

### When Add-ons Should Be Considered <a href="#when-add-ons-should-be-considered" id="when-add-ons-should-be-considered"></a>

Add-ons are optional service features that help customers adjust filtering, mapping, or data configuration to better match the expected migration outcome. They can be useful in Wix migrations when the source data is mostly compatible with Wix, but the merchant needs more control over which records move or how values are mapped or configured.

| Add-on area             | Wix migration use case                                                                                               | Boundary to keep clear                                                                                                                 |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Data Filter Add-on      | Useful when only selected products, customers, orders, CMS Pages, Blog Posts, or other eligible records should move. | Estimated quantities in the Entity Points Plan are not migration filters. Filtering requires explicit filtering rules where supported. |
| Advanced Data Mapping   | Useful when supported fields need deliberate mapping between the Source Platform and Wix target structures.          | It does not create unsupported Wix behavior or replace custom migration logic adjustment.                                              |
| Advanced Data Configure | Useful when supported values need editing or modification so migrated data reaches Wix with updated information.     | It does not rebuild Wix apps, Velo code, checkout rules, storefront design, or external integrations.                                  |

Add-ons are not a substitute for Custom Service. If a Standard Add-on must be modified beyond its available settings and supported behavior, the requirement is handled through Custom Service because customization is required.

### When Custom Service Is Required <a href="#when-custom-service-is-required" id="when-custom-service-is-required"></a>

Custom Service is required when the Wix migration needs customization, modification, bespoke handling, Custom Platform source handling, unsupported app data, custom migration logic adjustment, or tailored behavior beyond standard service capability and Standard Add-on capability.

For Wix, Custom Service is especially important when the current store depends on business meaning that cannot be represented as ordinary product, customer, order, CMS Page, or Blog Post data.

#### Custom product and catalog behavior <a href="#custom-product-and-catalog-behavior" id="custom-product-and-catalog-behavior"></a>

Custom Service is required when product behavior must be transformed beyond standard Wix product, option, choice, variant, modifier, inventory, SKU, price, image, or collection handling. This can include source product configurators, unusual bundles, custom product relationships, product personalization logic, non-standard variant structures, or records that need bespoke interpretation before they can work inside Wix.

#### App-owned, Velo, API, or external-system data <a href="#app-owned-velo-api-or-external-system-data" id="app-owned-velo-api-or-external-system-data"></a>

Custom Service is required when the project needs to preserve or transform data owned by apps, Velo custom code, APIs, service plugins, custom catalogs, external payment flows, fulfillment systems, CRM tools, ERP systems, PIM systems, WMS systems, accounting systems, marketing systems, or other outside systems. These records often carry business meaning that is not visible in ordinary store data.

#### Customer, member, and contact transformation <a href="#customer-member-and-contact-transformation" id="customer-member-and-contact-transformation"></a>

Custom Service is required when customer data must be transformed into Wix contacts, members, account-related structures, marketing preferences, app-owned profiles, loyalty data, review data, saved-payment context, or other customer-facing records in a way that goes beyond standard supported migration behavior.

#### Checkout, payment, shipping, tax, and fulfillment logic <a href="#checkout-payment-shipping-tax-and-fulfillment-logic" id="checkout-payment-shipping-tax-and-fulfillment-logic"></a>

Custom Service is required when the migration must preserve custom checkout behavior, custom payment context, custom shipping logic, special tax structures, external fulfillment references, pickup/local-delivery rules, custom fees, or checkout validation logic that cannot be handled as ordinary historical order data.

#### SEO, URL, content, and storefront transformation <a href="#seo-url-content-and-storefront-transformation" id="seo-url-content-and-storefront-transformation"></a>

Custom Service is required when the merchant needs bespoke URL transformation, custom redirect logic, unusual content restructuring, source theme behavior preservation, dynamic-page interpretation, or storefront logic that depends on custom code or non-standard platform behavior.

### How Demo Migration Should Influence the Approach <a href="#how-demo-migration-should-influence-the-approach" id="how-demo-migration-should-influence-the-approach"></a>

Demo Migration is useful for checking whether the selected approach is realistic before Full Migration. For Wix, the Demo Migration should not rely only on simple products or a small set of clean records. It should include examples that expose the actual difficulty of the project.

Strong Wix Demo Migration samples usually include:

* products with options, choices, variants, modifiers, SKUs, inventory, images, and collection placement;
* products with digital delivery, subscriptions, gift-card context, dropshipping, print-on-demand, or app-related behavior where relevant;
* customers that show contact, member, account, consent, or marketing context;
* orders with discounts, payment labels, shipping labels, tax, fulfillment, refunds, cancellations, tracking, and customer links;
* CMS Pages, Blog Posts, landing pages, and content records with SEO value;
* URLs, redirects, metadata, and high-value product or category paths;
* records tied to apps, Velo, APIs, external IDs, or business systems.

If the Demo Migration shows that records are readable and operational meaning is clear, Standard Service or Managed Service may remain suitable. If the Demo Migration exposes missing relationships, app-owned data, custom product logic, unsupported field meaning, or SEO transformation needs, the project should be reviewed for Add-ons or Custom Service before Full Migration.

### Choosing the Right Approach by Wix Complexity <a href="#choosing-the-right-approach-by-wix-complexity" id="choosing-the-right-approach-by-wix-complexity"></a>

| Wix complexity signal                                                                            | Recommended direction                                   | Why it matters                                                                                          |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Clean products, customers, orders, CMS Pages, and Blog Posts with predictable target structure   | Standard Service may be enough                          | The merchant can self-perform the migration and configure Wix separately.                               |
| Same standard scope, but the merchant wants Next-Cart-led execution                              | Managed Service may be safer                            | Execution responsibility shifts to Next-Cart while the work remains within standard service capability. |
| Selected records only                                                                            | Data Filter Add-on review                               | Entity estimates do not act as filters; selected-record scope needs filtering rules where supported.    |
| Supported field mapping or value updates                                                         | Advanced Data Mapping or Advanced Data Configure review | Mapping and configuration can improve fit when they remain within supported behavior.                   |
| Custom Platform source                                                                           | Custom Service                                          | Custom Platform handling requires bespoke review.                                                       |
| Product configurators, unusual variants, custom bundles, or non-standard product relationships   | Custom Service                                          | Product behavior requires custom interpretation or custom migration logic adjustment.                   |
| Wix app, Velo, API, service plugin, or external-system dependencies                              | Custom Service                                          | App and integration meaning often sits outside ordinary commerce records.                               |
| Customer-to-member/contact transformation or marketing consent handling beyond standard behavior | Custom Service                                          | Customer meaning needs bespoke interpretation.                                                          |
| Custom SEO, URL, redirect, content, or storefront transformation                                 | Custom Service                                          | Target presentation and routing require custom planning beyond ordinary data movement.                  |

### Avoid Choosing an Approach Too Lightly <a href="#avoid-choosing-an-approach-too-lightly" id="avoid-choosing-an-approach-too-lightly"></a>

A Wix project is often underestimated when the planning conversation focuses only on product count or order count. Record volume matters for Entity Points planning, but it does not reveal whether product options, customer meaning, checkout context, app data, URLs, storefront content, or external systems will work correctly after migration.

A too-light approach can lead to these gaps:

* products appear in Wix, but important options, variants, modifiers, SKUs, or inventory behavior is incomplete;
* orders are migrated, but payment, shipping, tax, fulfillment, or refund context is not readable enough for operations;
* customers exist as records, but contact, member, account, consent, or app-owned meaning is not preserved as expected;
* CMS Pages and Blog Posts migrate, but the new Wix site still needs content layout, menu, SEO, and redirect work;
* app, Velo, API, or external-system data is assumed to migrate as ordinary store data;
* the merchant chooses Managed Service when the real issue is customization, not execution responsibility.

The safer approach is to decide from the hardest representative records and workflows, not the cleanest examples.

### Conclusion <a href="#conclusion" id="conclusion"></a>

The right Wix migration approach depends on how much of the current store can fit standard Wix structures and how much requires filtering, mapping, configuration, or custom handling. Standard Service can work well for predictable Wix migrations. Managed Service can be safer when the same standard scope needs Next-Cart-led execution. Add-ons can help with selected filtering, mapping, or supported data configuration. Custom Service is required when the project depends on custom product logic, app-owned data, Velo/API behavior, external systems, custom customer meaning, or bespoke SEO and storefront transformation.

Before choosing the final approach, use Demo Migration results to review the records that carry the most business meaning: complex products, customer/member/contact examples, varied orders, content and SEO samples, app-dependent data, and external-system references. If those samples expose custom behavior or unsupported meaning, the migration should be reviewed before Full Migration scope is confirmed.

### FAQs <a href="#faqs" id="faqs"></a>

**Is Standard Service enough for a Wix migration?**

Standard Service can be enough when products, customers, orders, CMS Pages, Blog Posts, and other supported data fit Wix target structures without custom transformation. The merchant should still plan separate Wix setup for checkout, payment, shipping, tax, storefront design, apps, and integrations.

**When should I choose Managed Service for Wix?**

Managed Service is useful when the migration fits standard service capability but the merchant wants Next-Cart-led execution. It does not automatically include custom product transformation, app-data handling, Velo work, or bespoke integration logic.

**Do Add-ons replace Custom Service in a Wix migration?**

No. Add-ons help with filtering, mapping, or supported data configuration. Custom Service is required when a requirement needs customization, modification, Tailored Add-ons, Custom Add-ons, custom migration logic adjustment, Custom Platform handling, unsupported app data, Velo/API work, or bespoke transformation.

**When does a Wix migration require Custom Service?**

Custom Service is required when the project includes custom product configurators, unusual variant or modifier relationships, app-owned data, Velo or API dependencies, external system identifiers, custom customer/member/contact transformation, custom checkout logic, or bespoke SEO and URL transformation.

**How should Demo Migration affect the service choice?**

Demo Migration should test complex and representative Wix records, not only simple examples. If the sample result shows that standard data moves cleanly, Standard Service or Managed Service may remain suitable. If it exposes unsupported relationships, custom logic, app-owned data, or transformation needs, the project should be reviewed for Add-ons or Custom Service before Full Migration.
