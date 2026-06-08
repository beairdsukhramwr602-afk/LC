# Jumpseller Constraints and Risks

A migration to Jumpseller is usually safest when the source store can be translated into Jumpseller’s hosted SaaS structure without expecting the target store to reproduce every source-side customization. Jumpseller gives merchants a managed storefront environment with products, categories, themes, checkout settings, payment and shipping configuration, apps, sales channels, and integrations. That hosted model reduces technical maintenance, but it also creates boundaries that should be reviewed before migration.

The main risk is not simply whether product, customer, order, CMS Pages, or Blog Posts can be moved. The deeper question is whether the source store’s catalog logic, checkout behavior, URL structure, customer expectations, order history, theme experience, language setup, and integration dependencies can operate correctly inside Jumpseller after migration. Constraints should be identified early so the migration plan does not treat unsupported behavior as ordinary data movement.

### Hosted SaaS Boundaries <a href="#hosted-saas-boundaries" id="hosted-saas-boundaries"></a>

Jumpseller is not a self-hosted codebase where merchants can freely reproduce every source extension, server configuration, checkout script, database table, or backend workflow. It is a hosted e-commerce platform with target-side structures, theme editing, apps, integrations, and plan-sensitive capabilities.

This is often a strength for merchants who want a cleaner hosted environment, but it becomes a constraint when the source store depends on source-code customization, custom database behavior, unusual checkout logic, or business rules that were implemented outside standard commerce records.

| Constraint area              | Who it affects                                                                                   | Mitigation strategy                                                                   | Earliest review priority                                                                     | Risk increases when                                                                             |
| ---------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Hosted platform control      | Stores leaving heavily customized self-hosted platforms                                          | Separate data migration from platform rebuild and target-side configuration           | Confirm which source behaviors are native data, theme behavior, app behavior, or custom code | The source store depends on custom modules, private scripts, or database-side logic             |
| Plan-sensitive features      | Stores requiring advanced language, admin, stock-location, filtering, or code-editing capability | Confirm the intended Jumpseller plan before assuming the target behavior is available | Compare required target behavior with the selected plan                                      | The merchant chooses a lower plan without checking required operational features                |
| Backend workflow differences | Teams expecting the same administrative process after migration                                  | Define which workflows must continue and which will be redesigned inside Jumpseller   | Review order handling, fulfillment, product editing, and customer service routines           | Source workflows are tied to old extensions, staff permissions, or custom admin screens         |
| Platform-managed checkout    | Stores with custom checkout steps or source-specific checkout scripts                            | Confirm checkout fields, payment, shipping, and app options before migration          | Identify required checkout information and legal, tax, or delivery fields                    | The source checkout includes custom steps, nonstandard fields, or country-specific requirements |

A safe migration plan should name which parts of the source store are data, which parts are configuration, which parts are storefront presentation, and which parts are custom behavior that needs separate review.

### Product Variant and Option Constraints <a href="#product-variant-and-option-constraints" id="product-variant-and-option-constraints"></a>

Jumpseller can support products with options and variants, but source platforms often model sellable choices in different ways. A source store may use configurable products, product options, attributes, modifiers, bundles, product kits, custom input fields, downloadable files, personalization fields, or app-owned product logic. These should not be treated as the same structure.

The highest-risk catalog cases are usually products where shopper choice changes SKU, price, stock, weight, image, fulfillment, or availability. A simple color or size option may translate cleanly. A product builder, bundle, subscription, custom engraving field, or conditional option set may not.

| Catalog constraint                            | Who it affects                                                                   | Mitigation strategy                                                                                                    | Earliest review priority                                                                      | Risk increases when                                                                                  |
| --------------------------------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Dense variant combinations                    | Stores with many option combinations per product                                 | Test high-combination products in Demo Migration and review target sellability                                         | Identify products with the largest option matrices                                            | Source options create more combinations than the target structure can comfortably manage             |
| Source attributes used for different purposes | Stores where attributes control search, pricing, stock, display, or selection    | Classify each attribute as a variant option, visible product detail, filter value, custom field, or non-migrating rule | Review representative products from each catalog type                                         | Attribute meaning is unclear or mixed across product families                                        |
| Custom input and personalization fields       | Stores selling configurable or personalized products                             | Confirm whether the required information can be captured in target product or checkout behavior                        | Identify products requiring text inputs, uploads, engraving, measurement, or appointment data | Personalization controls price, production, or fulfillment rather than simple display                |
| Bundles, kits, and composite products         | Stores selling grouped products or source-extension product builders             | Decide whether bundles should become separate products, descriptions, app-supported behavior, or Custom Service scope  | Review source bundle logic and inventory dependence                                           | Bundle stock or price depends on multiple child products                                             |
| Digital or special product types              | Stores selling downloads, services, subscriptions, reservations, or appointments | Confirm whether the target store can support the expected selling and fulfillment behavior                             | Separate ordinary products from special product workflows                                     | Source behavior depends on a plugin, recurring billing, booking system, or private fulfillment logic |

Product constraints should be addressed before migration because they affect pricing, stock, checkout, customer experience, fulfillment, and validation. A technically migrated product can still fail if shoppers cannot select the right option or staff cannot manage inventory correctly.

### Category, Navigation, and Discovery Constraints <a href="#category-navigation-and-discovery-constraints" id="category-navigation-and-discovery-constraints"></a>

Categories in Jumpseller organize products, but source stores may use categories as menus, collections, landing pages, brand pages, filters, or SEO structures. A category migration that preserves names and assignments may still produce a weak target storefront if navigation, menus, and discovery behavior are not planned separately.

Deep or legacy category structures also need review. Older stores often accumulate category branches that exist mainly for historical URLs, search engine landing pages, campaign pages, or old menu layouts. Moving those structures without review can make the target catalog hard to browse.

| Discovery constraint       | Who it affects                                                                        | Mitigation strategy                                                  | Earliest review priority                                            | Risk increases when                                                                   |
| -------------------------- | ------------------------------------------------------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Category and menu mismatch | Stores where menus do not mirror category hierarchy                                   | Prepare separate category and navigation maps                        | Compare source category tree with storefront menu and landing pages | Important shopping paths are controlled by menus, not categories                      |
| Filter dependency          | Stores using attributes, tags, brands, specifications, or custom fields for filtering | Confirm which values must remain filterable or visible in Jumpseller | Identify high-value filter pages and product groups                 | Source filters drive most product discovery                                           |
| SEO landing categories     | Stores with indexed category, collection, or brand pages                              | Prioritize high-value category URLs and plan redirect destinations   | Review analytics, search traffic, and top indexed paths             | Historical traffic depends on category URLs that will change                          |
| Deep category trees        | Stores with many nested levels or legacy departments                                  | Simplify where useful and validate shopper discovery                 | Test representative top, mid, and deep categories                   | Deep structures were created for old platform logic rather than current merchandising |

Discovery constraints should be judged by shopper behavior, not just record presence. The target store should make products findable through realistic browsing, search, and navigation patterns.

### Checkout, Payment, Shipping, and Tax Constraints <a href="#checkout-payment-shipping-and-tax-constraints" id="checkout-payment-shipping-and-tax-constraints"></a>

Checkout behavior is a major constraint in any hosted SaaS target. Source stores may use custom checkout steps, custom payment modules, tax exemption fields, delivery instructions, pickup rules, country-specific invoice fields, local payment providers, or shipping logic that does not transfer as ordinary data.

Historical order records and future checkout configuration should be separated. A migration can preserve payment and shipping references in old orders, but the target store still needs payment providers, shipping methods, tax rules, delivery options, and checkout requirements configured for future purchases.

| Checkout constraint          | Who it affects                                                                                              | Mitigation strategy                                                         | Earliest review priority                                                   | Risk increases when                                                                      |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Custom checkout fields       | Stores collecting tax IDs, invoice details, delivery notes, pickup preferences, or business-specific fields | Identify required checkout data and confirm target handling                 | Review source checkout form and required order fields                      | Missing fields affect legal compliance, fulfillment, or customer service                 |
| Payment-provider replacement | Stores using source-specific gateways or regional payment modules                                           | Confirm available Jumpseller payment options for the target market          | List all current payment methods and payment-status meanings               | Payment methods are country-specific, manual, subscription-based, or plugin-owned        |
| Shipping-rate logic          | Stores using complex zones, dimensions, live rates, pickup, dropshipping, or rule-based shipping            | Map source shipping rules to target-side configuration or integration needs | Test common and edge-case shipping destinations                            | Shipping depends on source extensions, ERP rules, multiple warehouses, or custom scripts |
| Tax and invoice behavior     | Stores requiring tax exemptions, VAT fields, invoice formats, or country-specific rules                     | Confirm required tax data and target invoice workflow before migration      | Review tax classes, customer tax groups, and invoice data                  | Source tax handling is tied to customer groups, custom fields, or local regulations      |
| Order-status translation     | Stores with custom payment, fulfillment, cancellation, refund, or abandoned-order states                    | Define status meaning before mapping historical orders                      | Review paid, pending, fulfilled, canceled, refunded, and abandoned samples | Staff rely on custom statuses to interpret historical operations                         |

Checkout constraints should be surfaced before Article 6 service selection and before Demo Migration sample design. They affect target readiness as much as migrated data quality.

### Theme, Design, and Storefront Presentation Constraints <a href="#theme-design-and-storefront-presentation-constraints" id="theme-design-and-storefront-presentation-constraints"></a>

Jumpseller provides themes and customization options, including the ability to edit theme code where available. That does not mean a source storefront design, page builder layout, custom template system, or source theme extension can be copied directly into Jumpseller.

A migration should preserve business content and help the target store represent products, categories, pages, and brand information correctly. It should not assume the old theme architecture, HTML structure, app widgets, page-builder modules, or source checkout design will become identical in the target store.

| Storefront constraint           | Who it affects                                                                                        | Mitigation strategy                                                                         | Earliest review priority                                                           | Risk increases when                                                                |
| ------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Source theme dependence         | Stores where product pages, category pages, or landing pages rely on custom theme code                | Separate migrated content from target theme rebuild work                                    | Review product page, category page, home page, and high-value landing page layouts | Important information exists only inside source templates or page-builder sections |
| Custom storefront scripts       | Stores using custom scripts for pricing, personalization, banners, popups, tracking, or merchandising | Identify which scripts are required and whether target-side alternatives exist              | Inventory scripts and app widgets before migration                                 | Scripts affect checkout, pricing, compliance, analytics, or product selection      |
| Page-builder content            | Stores with pages built in source-specific visual builders                                            | Decide whether pages become CMS Pages, Blog Posts, theme sections, or rebuilt landing pages | Review high-value content pages and promotional pages                              | Layout carries important conversion or SEO value                                   |
| Theme-code editing expectations | Stores expecting unrestricted source-level development                                                | Confirm target plan and theme customization boundaries                                      | Identify required template-level changes                                           | The merchant expects full backend or checkout code control                         |

The safest approach is to treat storefront presentation as target design work supported by migrated content, not as a direct theme clone.

### Multilingual and Multicurrency Constraints <a href="#multilingual-and-multicurrency-constraints" id="multilingual-and-multicurrency-constraints"></a>

Jumpseller can support multilingual and multi-market selling, but language and currency behavior should be reviewed against the target plan and market requirements. Source stores may have translations for products, categories, pages, checkout labels, SEO metadata, emails, menus, and app content. They may also use currency conversion, market-specific pricing, tax differences, or payment methods that do not transfer as simple fields.

Multilingual migration risk increases when only part of the source store is translated or when source language behavior depends on plugins. A product description might be translated while category names, URLs, SEO titles, checkout text, or navigation labels are not.

| Market constraint               | Who it affects                            | Mitigation strategy                                                       | Earliest review priority                                                               | Risk increases when                                                    |
| ------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Partial translations            | Stores with multiple storefront languages | Review which objects must be translated in the target store               | Sample products, categories, CMS Pages, Blog Posts, menus, and SEO fields per language | Source translations are incomplete, plugin-owned, or inconsistent      |
| Language-plan limits            | Stores requiring several active languages | Confirm the intended Jumpseller plan supports the required language count | Count active languages and required localized objects                                  | The target plan does not match the language requirement                |
| Currency and payment mismatch   | Stores selling across multiple markets    | Confirm currency, payment, shipping, and tax behavior for each market     | Test representative checkout paths by market                                           | Currency display differs from payment settlement or tax/shipping rules |
| Localized URLs and SEO metadata | Stores with indexed translated pages      | Prepare priority redirect and SEO metadata samples per language           | Identify high-traffic translated URLs                                                  | Historical localized URLs cannot be replicated exactly                 |

International constraints should be reviewed as operating requirements, not just translation fields. The migrated store must support how customers browse, pay, receive orders, and read information in each market.

### Customer Account and Password Constraints <a href="#customer-account-and-password-constraints" id="customer-account-and-password-constraints"></a>

Customer records may migrate into Jumpseller as account or contact context, but login continuity should not be assumed. Source platforms store passwords differently, and hosted targets typically have strict rules around authentication. A migration plan should set expectations for whether customers can log in with existing credentials, whether password reset is needed, and how customer communication should be handled before launch.

Customer groups or segments also need review. A source customer group may drive discounts, wholesale pricing, tax exemption, payment access, shipping eligibility, or catalog visibility. If those rules are not represented the same way in Jumpseller, the group name alone will not preserve the original business behavior.

| Customer constraint              | Who it affects                                                      | Mitigation strategy                                                                | Earliest review priority                                                              | Risk increases when                                                     |
| -------------------------------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Password continuity              | Stores with existing customer accounts                              | Confirm customer login expectations and reset communication plan                   | Review source password system and target login policy                                 | The launch depends on customers logging in without reset                |
| Customer group meaning           | B2B, wholesale, tax-exempt, loyalty, or segmented stores            | Identify which group rules need target-side configuration or Custom Service review | Review customer groups and the rules they control                                     | Group labels control pricing, payment, shipping, tax, or catalog access |
| Address and profile completeness | Stores with multiple addresses or custom profile fields             | Validate customer samples with varied billing, shipping, and profile data          | Review customers with multiple addresses, phone numbers, tax IDs, and company details | Important customer service data exists in custom fields or app records  |
| Marketing and consent context    | Stores using consent, newsletter, or segmented communication fields | Confirm whether these values can be migrated and used appropriately                | Review source opt-in fields and marketing integration dependencies                    | Consent values are app-owned or legally sensitive                       |

Customer constraints should be handled carefully because they affect launch communication, support workload, and customer trust after migration.

### App, API, Sales Channel, and Integration Constraints <a href="#app-api-sales-channel-and-integration-constraints" id="app-api-sales-channel-and-integration-constraints"></a>

Jumpseller supports apps, integrations, APIs, webhooks, and sales channels, but source-side app data does not automatically become native Jumpseller data. Many stores rely on third-party apps for reviews, loyalty points, subscriptions, ERP synchronization, invoicing, shipping labels, marketplaces, product feeds, analytics, email marketing, or fulfillment automation.

These records and workflows must be separated from the standard migration scope unless they are explicitly supported and mapped. App-owned data is one of the clearest Custom Service review signals when the business expects it to move or remain operational after migration.

| Integration constraint    | Who it affects                                                                                 | Mitigation strategy                                                           | Earliest review priority                                                           | Risk increases when                                                   |
| ------------------------- | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| App-owned data            | Stores using apps for reviews, subscriptions, loyalty, invoices, quotes, or product enrichment | Identify native data versus app-owned data before migration                   | Export app lists and data examples                                                 | Business-critical records exist only inside third-party apps          |
| External identifiers      | Stores connected to ERP, POS, accounting, fulfillment, or marketplace systems                  | Preserve or remap identifiers only where target-side use is defined           | Review SKU, product ID, customer ID, order ID, and external reference requirements | External systems rely on old IDs or custom fields                     |
| API and webhook workflows | Stores with automated stock, order, customer, or fulfillment synchronization                   | Define which integrations need rebuild, replacement, or Custom Service review | List active API, webhook, and middleware workflows                                 | Live operations depend on source-specific endpoints or payloads       |
| Sales-channel behavior    | Stores selling through marketplaces, social channels, feeds, or external catalogs              | Confirm target channel support and data requirements                          | Review channel-specific product, inventory, and order samples                      | Source channels use app-specific fields or channel-only product rules |

Integration constraints should be reviewed before assuming the migration is only a platform-to-platform data project. Some work belongs to target configuration, some belongs to third-party integration setup, and some belongs to Custom Service.

### URL, Redirect, and SEO Constraints <a href="#url-redirect-and-seo-constraints" id="url-redirect-and-seo-constraints"></a>

URL continuity is a high-risk area when moving into a hosted platform. Source stores may have product, category, brand, blog, search, filter, and landing-page URLs that cannot be recreated exactly in Jumpseller. Search visibility depends on prioritizing the URLs that matter most and validating their target destinations.

A redirect plan should focus on high-value paths rather than promising every historical URL. Product, category, page, and blog URLs that receive organic traffic, paid campaign traffic, backlinks, or customer bookmarks should be reviewed before launch.

| SEO constraint              | Who it affects                                                                       | Mitigation strategy                                                     | Earliest review priority                                        | Risk increases when                                                               |
| --------------------------- | ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Different URL structure     | Stores leaving platforms with source-specific permalink formats                      | Prepare priority redirect list and validate destination quality         | Review high-traffic products, categories, pages, and Blog Posts | Old URLs include IDs, deep category paths, filter parameters, or translated slugs |
| Missing or changed metadata | Stores with SEO titles, descriptions, slugs, alt text, or structured landing content | Map critical metadata where supported and validate key pages            | Sample top pages from search traffic and paid campaigns         | Metadata was generated by plugins or stored in custom fields                      |
| Filter and search URLs      | Stores with indexed filter pages or internal search paths                            | Decide which filter URLs deserve replacement landing pages or redirects | Review indexed filter URLs and analytics                        | Filter pages generate meaningful organic traffic                                  |
| Content-page continuity     | Stores with blogs, CMS Pages, help pages, or campaign pages                          | Validate content migration and redirect destinations together           | Review high-value non-product pages                             | Source content lives inside a page builder or app                                 |

SEO risk should be managed as prioritization and validation. A clean redirect plan is more useful than a broad claim that all old paths can be preserved exactly.

### Custom Platform and Unsupported Data Constraints <a href="#custom-platform-and-unsupported-data-constraints" id="custom-platform-and-unsupported-data-constraints"></a>

A Custom Platform source, unsupported source data, app-owned records, unusual product relationships, custom checkout data, and bespoke business rules all increase migration complexity. In these cases, the risk is not only technical access. It is interpretation: what each source value means, where it should live in Jumpseller, and how the migrated result should be validated.

Custom Service is the correct review path when the migration involves Custom Platform handling, unsupported extension or app data, custom fields beyond standard capability, external identifiers, special transformation rules, or custom migration logic adjustment. Add-ons can help with filtering, mapping, or data configuration when the requirement fits their scope, but Add-ons should not be treated as the full solution for bespoke platform behavior.

| Custom complexity              | Who it affects                                                                         | Mitigation strategy                                                                            | Earliest review priority                                  | Risk increases when                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Custom Platform source         | Stores coming from unsupported or bespoke systems                                      | Review data model, exports, fields, relationships, and validation samples under Custom Service | Gather representative exports and field definitions       | Source relationships are undocumented or inconsistent                            |
| Unsupported app or module data | Stores that rely on non-native records                                                 | Determine whether data should migrate, be recreated, or remain in an external system           | Identify app-owned records and their business purpose     | The app controls active sales, fulfillment, customer history, or compliance data |
| Custom fields and external IDs | Stores using private fields for staff workflow or integrations                         | Map values only when target use is clear; otherwise review as custom scope                     | Review products, customers, and orders with custom fields | External systems depend on those values after launch                             |
| Bespoke transformation rules   | Stores requiring field conversion, structural changes, or target-specific reformatting | Define transformation logic before migration                                                   | Prepare before/after examples                             | Rules differ by product type, customer type, market, or order status             |

The safest risk strategy is to identify custom scope early instead of discovering it during final validation.

### What Should Be Reviewed First <a href="#what-should-be-reviewed-first" id="what-should-be-reviewed-first"></a>

The first review should concentrate on the areas most likely to change migration scope or target readiness. For Jumpseller, those areas are variant complexity, checkout requirements, category and navigation differences, customer login expectations, URL redirects, multilingual or multicurrency needs, app-owned data, integration dependencies, and any Custom Platform source structure.

A Demo Migration should include records that expose those risks. Clean products and simple customers are useful, but they are not enough. Strong samples include products with several option combinations, categories tied to navigation, customers with multiple addresses or groups, orders with varied payment and fulfillment states, content pages with SEO value, translated records, and app-owned data examples where relevant.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Jumpseller migration risk is concentrated where source behavior depends on structures that are not ordinary target records: dense variant logic, custom checkout behavior, source-specific themes, complex shipping and tax rules, customer-group business rules, multilingual market behavior, app-owned records, integrations, and SEO-sensitive URLs. These constraints do not make Jumpseller a weak Target Platform by default. They define what must be reviewed before the migration path, service scope, Demo Migration samples, and launch plan can be considered reliable.

Before committing to the final migration scope, use Demo Migration results to test the highest-risk product, customer, order, content, URL, language, and integration samples. If the results show unsupported data, custom field dependencies, external identifiers, or transformation rules beyond standard service capability, review the requirement with Next-Cart through Live Chat before relying on a standard migration plan.

### FAQs <a href="#faqs" id="faqs"></a>

**What is the biggest risk when migrating to Jumpseller?**

The biggest risk is assuming that source-specific behavior will become native Jumpseller behavior automatically. Product records, customer records, and order history may migrate, but custom checkout steps, app workflows, source theme behavior, external integrations, and special product logic need separate review.

**Can Jumpseller preserve every source product option and variant exactly?**

Not always. Ordinary size, color, SKU, price, stock, and image differences may translate well when they fit the target structure. Complex product builders, conditional options, bundles, personalization fields, and very large option combinations should be reviewed before migration.

**Are categories enough to preserve the old storefront navigation?**

No. Categories and navigation should be reviewed separately. A migrated category tree does not automatically recreate source menus, landing pages, filters, promotional links, or SEO-focused browsing paths.

**What happens if my source checkout has custom fields?**

Custom checkout fields should be reviewed before migration. Some values may be preserved as order information, while future checkout behavior may need target-side configuration, an app, or Custom Service review if the field is part of a custom business rule.

**Do payment and shipping settings migrate as live checkout settings?**

Historical payment and shipping references may remain useful in migrated orders, but live payment providers, shipping rates, pickup options, tax rules, and fulfillment settings need to be configured in Jumpseller for future orders.

**Should app data be treated as part of the standard migration?**

No. App-owned data should be reviewed separately. If reviews, subscriptions, loyalty points, invoices, ERP references, product feeds, or fulfillment data are stored outside standard platform records, they may require Custom Service review.

**Can Add-ons solve Jumpseller migration constraints?**

Add-ons can help with filtering, mapping, and data configuration when the requirement fits their supported scope. Broader issues such as Custom Platform handling, unsupported app data, bespoke transformations, external identifiers, or custom migration logic adjustment belong under Custom Service review.

**How should URL and SEO risk be handled?**

Prioritize high-value product, category, page, and Blog Posts URLs. The goal is to validate important destination paths and redirect quality, not to assume every historical URL can be recreated exactly.
