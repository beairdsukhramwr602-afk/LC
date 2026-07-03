# Squarespace Pre-Migration Preparation Checklist

Squarespace preparation should begin with a clear decision about what the target store is expected to become. Squarespace is a hosted content-first commerce Target Platform, so preparation is not limited to product and order exports. The store owner should also prepare site structure, Store Pages, content, media, SEO, redirects, domains, checkout settings, integrations, and any records that may need Add-ons or Custom Service review.

A strong preparation phase protects Demo Migration quality. It helps the merchant decide which records should move, which target-side settings must be configured separately, which design or content work is outside migration scope, and which samples should be checked before Full Migration.

### Confirm the Target Store Role <a href="#confirm-the-target-store-role" id="confirm-the-target-store-role"></a>

Before exporting data or requesting a migration setup, define the role Squarespace will play after launch. Squarespace may be used as a content-led storefront with a small product catalog, a portfolio site with commerce, a service-business site with booking or payment needs, a digital product shop, or a compact commerce site with limited operational complexity.

| Preparation question                                                              | Why it matters                                                                                                    | Target-side decision                                                                                    |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Will Squarespace be the main storefront or a content site with commerce attached? | Commerce records and site presentation must be planned together.                                                  | Decide how Store Pages, product pages, content pages, navigation, and checkout will support the launch. |
| Which parts of the source store are still useful?                                 | Old products, outdated pages, inactive customers, and obsolete posts can create unnecessary noise.                | Decide what should migrate, be excluded, redirected, archived, or rebuilt manually.                     |
| Is the launch mainly a data move, a redesign, or a business-model change?         | Migration cannot automatically rebuild every template, app workflow, checkout setting, or content strategy.       | Separate migration scope from site build, copywriting, design, configuration, and operations work.      |
| Are third-party systems still part of the future workflow?                        | CRM, fulfillment, tax, shipping, accounting, subscription, donation, and booking tools may own important records. | Identify which data belongs in Squarespace and which data remains external.                             |

This early framing prevents Squarespace from being treated like a generic cart replacement. It also gives the Demo Migration a meaningful standard for success.

### Prepare Product and Store Page Data <a href="#prepare-product-and-store-page-data" id="prepare-product-and-store-page-data"></a>

Squarespace product preparation should consider both commerce data and storefront presentation. Product records may migrate successfully while Store Page layout, navigation, merchandising, product-page sections, and checkout behavior still require target-side setup.

| Product area                | What to prepare                                                                                                                                                         | Validation sample to include                                                       |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Product types               | Classify physical products, service products, digital downloads, gift cards, subscriptions/payment plans, donation-style products, and unsupported or unusual products. | At least one product from each important product type.                             |
| Product details             | Clean names, descriptions, SKUs, prices, sale prices, weights, stock values, visibility, SEO titles, SEO descriptions, and product slugs.                               | Products with standard fields and products with missing or unusual values.         |
| Variants and options        | Review variant names, option choices, SKU combinations, price differences, inventory differences, and variant images.                                                   | Simple products, single-option products, and multi-option variant products.        |
| Product media               | Prepare main images, galleries, alt text expectations, file quality, image order, and any product-specific media rules.                                                 | Products with multiple images and products that depend on variant-specific images. |
| Store Pages and collections | Decide which products belong on Store Pages, collection-style pages, menus, filters, landing pages, and promotional sections.                                           | A category or collection that matters for customer browsing.                       |

Product preparation should also identify source behaviors that are not simple product data. Bundles, add-ons, custom forms, engraving fields, appointment-style selling, wholesale pricing, advanced subscriptions, marketplace feeds, or external inventory logic may need Add-ons, Custom Service review, manual setup, or accepted exclusion.

### Prepare Customer, Contact, Member, and Profile Records <a href="#prepare-customer-contact-member-and-profile-records" id="prepare-customer-contact-member-and-profile-records"></a>

Squarespace customer preparation should separate commerce history from broader site identity. Source stores may combine customers, contacts, newsletter subscribers, donors, members, account users, booking participants, and CRM profiles in one system. Squarespace may represent these meanings differently.

| Record type                | Preparation focus                                                                                                 | Reason to prepare early                                                          |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Customers                  | Names, emails, billing addresses, shipping addresses, phone numbers, order history links, and customer notes.     | Customer records must match order-history expectations.                          |
| Contacts and subscribers   | Marketing contacts, newsletter subscribers, inquiry contacts, donor contacts, and CRM-style records.              | Not every contact is necessarily a commerce customer.                            |
| Members and account access | Login expectations, member-only content, customer accounts, subscriptions, courses, appointments, or gated pages. | Access control may require Squarespace setup or external-system handling.        |
| Guest buyers               | Orders tied to email addresses without target account login.                                                      | Guest order history should be validated separately from account-based customers. |
| External IDs               | CRM, fulfillment, accounting, tax, loyalty, or customer-service references.                                       | External systems may need original identifiers after launch.                     |

Customer preparation should include privacy review. Remove records that are no longer needed, confirm which records are legally and operationally appropriate to move, and decide whether inactive customers or marketing-only contacts should be included.

### Prepare Historical Order and Transaction Data <a href="#prepare-historical-order-and-transaction-data" id="prepare-historical-order-and-transaction-data"></a>

Order preparation should distinguish migrated history from live commerce configuration. Historical orders can help customer service, accounting review, warranty lookup, and operational continuity, but they do not recreate live checkout, payment, shipping, tax, fulfillment, or subscription workflows.

| Order area     | What to prepare                                                                                      | What to check during Demo Migration                                                         |
| -------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Order status   | Source statuses, fulfillment states, payment states, cancellation states, and refund states.         | Whether migrated labels are understandable for operations teams.                            |
| Line items     | Product names, variant selections, SKU references, quantities, discounts, tax, shipping, and totals. | Orders with variants, discounts, refunds, shipping fees, tax lines, and manual adjustments. |
| Customer links | Registered customer orders, guest orders, duplicate emails, and historical address changes.          | Whether orders remain associated with the expected customer or email.                       |
| Transactions   | Payment labels, transaction references, refunds, charge states, and gateway identifiers.             | Whether transaction data is useful as historical reference.                                 |
| Fulfillment    | Tracking numbers, carriers, shipment splits, fulfillment notes, and external fulfillment IDs.        | Whether fulfillment details remain readable after migration.                                |

Recurring payment behavior, subscription renewal, saved payment methods, fraud rules, automated emails, and fulfillment automation should be reviewed as live target operations, not as ordinary historical order data.

### Prepare Checkout, Payment, Tax, Shipping, Discount, and Fulfillment Settings <a href="#prepare-checkout-payment-tax-shipping-discount-and-fulfillment-settings" id="prepare-checkout-payment-tax-shipping-discount-and-fulfillment-settings"></a>

Target checkout settings should be prepared separately from migrated data. A merchant can move product, customer, and order history while still needing to configure payment services, tax rules, shipping methods, discount behavior, fulfillment workflows, notification settings, and operational policies in Squarespace or connected tools.

| Operational area | Preparation task                                                                                                   | Boundary to document                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Payment          | Decide payment providers, accepted currencies, transaction workflow, fraud review, and payment notifications.      | Migrated payment history is not the same as live payment processing.      |
| Tax              | Review tax regions, exemption logic, external tax tools, and historical tax-line expectations.                     | Tax setup should be configured and tested on the target store.            |
| Shipping         | Define shipping methods, carrier rules, pickup/local delivery rules, fulfillment locations, and shipping labels.   | Historical shipping data does not rebuild live shipping configuration.    |
| Discounts        | Identify coupons, discount codes, campaign rules, and expired promotions.                                          | Old discounts may be historical references rather than active promotions. |
| Fulfillment      | Confirm internal fulfillment, dropshippers, warehouse tools, third-party logistics, and tracking responsibilities. | Fulfillment integrations may need separate setup or review.               |

Preparation should include a simple checkout test plan. The merchant should know which live checkout scenarios must be tested after migration and before DNS or domain launch.

### Prepare Content, Media, SEO, URLs, and Domains <a href="#prepare-content-media-seo-urls-and-domains" id="prepare-content-media-seo-urls-and-domains"></a>

Squarespace migration planning should treat content continuity as a core readiness item. Product and order migration alone does not protect organic traffic, customer navigation, brand presentation, or launch quality.

| Site area      | Preparation task                                                                                              | Why it matters                                                            |
| -------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| CMS Pages      | List pages to migrate, rewrite, merge, redirect, exclude, or rebuild manually.                                | Old pages may not match the new Squarespace site structure.               |
| Blog Posts     | Review post status, authorship, categories/tags, dates, media, internal links, and high-value posts.          | Blog continuity can affect SEO and customer trust.                        |
| Media          | Prepare image files, video embeds, downloadable files, galleries, alt text expectations, and media ownership. | Missing or low-quality media can make migrated content appear incomplete. |
| URLs and slugs | Export important product, category, page, post, and landing-page URLs.                                        | Redirect planning depends on knowing the source URL structure.            |
| SEO metadata   | Review titles, descriptions, canonical expectations, structured content, and indexed pages.                   | Migration should protect search visibility where possible.                |
| Domains        | Confirm launch domain, subdomain use, DNS timing, SSL readiness, and redirect responsibility.                 | Domain changes can affect launch timing and validation.                   |

A practical preparation step is to identify the highest-value URLs before migration begins. These URLs should be included in Demo Migration review and post-launch checks.

### Prepare Templates, Design, Navigation, and Site-Builder Dependencies <a href="#prepare-templates-design-navigation-and-site-builder-dependencies" id="prepare-templates-design-navigation-and-site-builder-dependencies"></a>

Squarespace stores depend heavily on presentation. Migration can move selected data, but template behavior, layout sections, navigation menus, product-page presentation, mobile display, checkout appearance, and brand design may require target-site setup.

| Design dependency         | Preparation focus                                                                                               | Recommended action                                           |
| ------------------------- | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Templates and sections    | Source templates, page builders, blocks, custom sections, and landing-page patterns.                            | Decide what will be rebuilt manually in Squarespace.         |
| Menus and navigation      | Header menus, footer menus, collection links, product navigation, and content hierarchy.                        | Map important navigation paths to target pages.              |
| Product-page presentation | Image layout, variant selector display, product detail placement, related products, and merchandising sections. | Validate representative products during Demo Migration.      |
| Mobile behavior           | Mobile menu, content stacking, product images, checkout flow, and responsive sections.                          | Review mobile display before Full Migration acceptance.      |
| Embedded content          | Forms, maps, calendars, videos, scripts, widgets, and external embeds.                                          | Decide whether each embed is rebuilt, replaced, or excluded. |

This preparation avoids a common misunderstanding: migrated content is not the same as a fully recreated visual site.

### Prepare Apps, APIs, External Systems, and Unsupported Data <a href="#prepare-apps-apis-external-systems-and-unsupported-data" id="prepare-apps-apis-external-systems-and-unsupported-data"></a>

Squarespace may interact with third-party services, custom workflows, API-supported records, and externally owned systems. Preparation should classify these before the migration scope is finalized.

| System type            | Preparation question                                                                                                           | Possible handling                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| Commerce APIs          | Does the data align with supported products, inventory, orders, contacts, transactions, profiles, or webhook workflows?        | Include supported records in migration scope where appropriate.                            |
| External systems       | Does an ERP, CRM, accounting, shipping, tax, fulfillment, subscription, booking, donation, or marketing system own the record? | Keep externally owned records outside ordinary migration or review through Custom Service. |
| Third-party apps       | Does an app create fields, workflows, discounts, member access, forms, or custom objects?                                      | Identify supported fields, Add-ons, Custom Service review needs, or accepted exclusions.   |
| Custom source behavior | Does the source store use custom tables, scripts, unusual attributes, or marketplace/channel data?                             | Decide whether the data is migrated, simplified, rebuilt, or excluded.                     |

Unsupported data should not remain vague. If a record cannot be migrated into a useful Squarespace structure, the preparation file should mark it as manual setup, external-system retention, Custom Service review, or accepted exclusion.

### Prepare Demo Migration Samples <a href="#prepare-demo-migration-samples" id="prepare-demo-migration-samples"></a>

Demo Migration should be prepared with representative records, not only easy records. The samples should prove whether Squarespace can represent the store’s real operating patterns.

| Sample group | Include examples of                                                                                                                                                | Pass condition                                                      |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| Products     | Simple products, variant products, product media, inventory differences, Store Page placement, hidden products, and unusual product types.                         | Product data and presentation expectations can be reviewed clearly. |
| Orders       | Guest orders, customer-linked orders, refunded orders, discounted orders, taxed orders, shipped orders, subscription/payment-plan examples, and orders with notes. | Historical order information is readable and operationally useful.  |
| Customers    | Registered customers, guest buyers, contacts, subscribers, members, duplicate emails, and customers with external IDs.                                             | Customer identity is not confused with marketing or member access.  |
| Content      | High-value pages, Blog Posts, media-heavy pages, internal links, SEO fields, redirects, and old URLs.                                                              | Content and SEO continuity can be tested before launch.             |
| Integrations | App fields, external references, CRM IDs, fulfillment IDs, tax/shipping/payment references, and unsupported records.                                               | Scope boundaries are visible before Full Migration.                 |

A weak Demo Migration sample can make the migration appear safer than it is. The preparation checklist should intentionally include edge cases that are important to the merchant.

### Prepare Add-ons, Custom Service, Entity Points, and Additional Migration Options <a href="#prepare-add-ons-custom-service-entity-points-and-additional-migration-options" id="prepare-add-ons-custom-service-entity-points-and-additional-migration-options"></a>

Some Squarespace migration requirements are standard, while others need explicit scope handling. Preparation should classify these before the merchant approves the migration path.

| Scope item                   | Preparation rule                                                                                                                                     | Boundary                                                                                                                                                        |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Add-ons                      | Identify specific supported data needs that extend migration output.                                                                                 | Add-ons are not a substitute for Custom Service, custom development, or full site reconstruction.                                                               |
| Custom Service               | Flag non-standard product behavior, external systems, unsupported structures, app-owned records, or unusual content and commerce requirements.       | Custom Service does not automatically mean every workflow is rebuilt inside Squarespace.                                                                        |
| Entity Points                | Separate new eligible records from previously counted records.                                                                                       | Records already counted through the service license do not consume Entity Points again only because another migration action occurs on the same migration path. |
| Additional Migration Options | Plan how later products, customers, orders, Blog Posts, URL changes, or content updates will be rechecked if follow-up migration activity is needed. | Follow-up activity should trigger validation, not automatic launch approval.                                                                                    |

New Product, Customer, Order, and Blog Posts records may consume Entity Points when migrated for the first time. Previously counted records should not be counted again simply because the merchant performs another migration action for the same migration path.

### Squarespace Preparation Checklist <a href="#squarespace-preparation-checklist" id="squarespace-preparation-checklist"></a>

| Checklist area        | Ready when                                                                                                                                                                     |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Target role           | The merchant knows whether Squarespace is the main storefront, content-first site with commerce, service-business site, digital product shop, or compact commerce destination. |
| Product scope         | Product types, variants, media, Store Pages, inventory, SEO fields, and unsupported selling behavior are classified.                                                           |
| Customer scope        | Customers, contacts, subscribers, members, guest buyers, and external IDs are separated.                                                                                       |
| Order scope           | Historical orders, transactions, refunds, subscriptions/payment plans, fulfillment data, and external references are prepared for sample validation.                           |
| Operational setup     | Checkout, payment, tax, shipping, discounts, fulfillment, and notifications are assigned to target configuration or connected services.                                        |
| Content and SEO       | CMS Pages, Blog Posts, media, URLs, redirects, SEO metadata, domains, and internal links are prepared.                                                                         |
| Design and navigation | Templates, sections, page layout, menus, product-page display, mobile behavior, and embedded content are assigned to target-site build work where needed.                      |
| Integrations          | APIs, third-party apps, external systems, unsupported structures, and accepted exclusions are documented.                                                                      |
| Demo Migration        | Representative samples include ordinary records and high-risk records.                                                                                                         |
| Scope controls        | Add-ons, Custom Service, Entity Points, Additional Migration Options, and accepted exclusions are clearly separated.                                                           |

### Conclusion <a href="#conclusion" id="conclusion"></a>

Squarespace preparation works best when the merchant treats migration as both a commerce-data project and a hosted site readiness project. Products, customers, orders, content, media, SEO, redirects, design dependencies, checkout settings, and integrations should be prepared before Demo Migration, not discovered during launch.

The strongest preparation outcome is a clear scope map: what should migrate, what should be configured in Squarespace, what should be rebuilt manually, what needs Add-ons, what needs Custom Service review, and what should be excluded. With that map, Demo Migration becomes a meaningful proof step before Full Migration.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to Squarespace?**

Start by defining the target role for Squarespace. The merchant should know whether Squarespace will be the main storefront, a content-first site with commerce, a service-business site, a digital product shop, or a compact commerce destination. That decision affects products, content, SEO, checkout, integrations, and design planning.

**Does Squarespace preparation only require product and order exports?**

No. Squarespace preparation should also include CMS Pages, Blog Posts, media, Store Pages, URLs, redirects, SEO metadata, domains, checkout settings, payment, tax, shipping, discounts, fulfillment, integrations, and design dependencies.

**How should products be prepared for Squarespace migration?**

Products should be classified by type, variant structure, inventory behavior, media, Store Page placement, SEO fields, visibility, and unsupported selling behavior. Products with variants, unusual options, gift cards, downloads, service products, subscriptions/payment plans, or bundles should be included in Demo Migration samples when relevant.

**What order data should be included in Demo Migration samples?**

Demo Migration samples should include guest orders, customer-linked orders, refunded orders, discounted orders, taxed orders, shipped orders, orders with variant products, orders with notes, and any subscription/payment-plan or external fulfillment examples that matter to operations.

**When should Custom Service be reviewed before migrating to Squarespace?**

Custom Service should be reviewed when the source store includes non-standard product behavior, third-party app records, custom fields, external systems, unsupported structures, unusual content relationships, custom workflows, or integration-owned records that cannot be handled through normal migration scope or specific Add-ons.
