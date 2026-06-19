# Shopify Pre-Migration Preparation Checklist

Shopify preparation should define how the future Target Store needs to work before migration configuration begins. A clean source export is useful, but it is not enough when the store depends on product options, variants, collection logic, apps, metafields, Markets, customer-account expectations, redirects, or theme behavior.

A prepared Shopify migration turns source-store complexity into target-store decisions. It identifies what should transfer as standard commerce data, what needs mapping or filtering, what must be configured in Shopify, what depends on apps or themes, and what may require Custom Service. Strong preparation also produces practical Demo Migration samples so the customer can review the Shopify result before treating the Full Migration plan as launch-ready.

### Confirm the Target Store Model <a href="#confirm-the-target-store-model" id="confirm-the-target-store-model"></a>

Preparation should begin with the intended Shopify operating model. Shopify is a hosted Target Platform, so infrastructure ownership is lower than on self-hosted platforms, but the Target Store still needs clear decisions around products, collections, customer accounts, Markets, apps, themes, redirects, and operational ownership.

| Preparation area             | What to confirm                                                                                                                   | Why it matters in Shopify                                                                                                  |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Products and variants        | Which source product structures should become Shopify products, options, variants, metafields, app data, or content.              | Buying choices must stay clear and manageable after migration.                                                             |
| Collections and navigation   | Which source categories, product groups, menus, filters, and landing pages should become Shopify collections or navigation paths. | Shopify discovery depends on collections, product data, navigation, filters, theme behavior, and sometimes apps.           |
| Markets and localization     | Which countries, languages, currencies, domains, or regional paths need priority planning.                                        | International structure may affect storefront routing, pricing expectations, content, redirects, and validation samples.   |
| Apps and storefront behavior | Which source functions should be replaced or supported by Shopify apps, theme settings, or custom handling.                       | Apps and themes may control behavior that cannot be migrated as ordinary records.                                          |
| Customer experience          | What returning customers should expect after launch.                                                                              | Customer records may migrate while login, activation, loyalty, wholesale, subscription, or account behavior still changes. |
| URL continuity               | Which legacy URLs need deliberate redirect destinations.                                                                          | High-value paths should protect search visibility, campaign value, and customer trust.                                     |

Target Store decisions should be made before relying on record counts or Entity Points capacity as the main readiness signal. Entity Points help estimate migration capacity. They do not confirm whether Shopify product structure, collection logic, app behavior, customer experience, or URL continuity is ready.

### Prepare Product and Variant Evidence <a href="#prepare-product-and-variant-evidence" id="prepare-product-and-variant-evidence"></a>

Shopify preparation should separate sellable variation from supporting product meaning. Many Source Platforms use product options, attributes, custom fields, configurable products, grouped products, bundles, kits, personalization fields, and extension-driven rules in overlapping ways. Shopify represents buying choices through products, options, and variants, while other product details may belong in product descriptions, metafields, tags, apps, theme sections, or custom handling.

Prepare representative product samples that include:

* best-selling products and high-margin products;
* products with multiple options such as size, color, material, capacity, pack size, or style;
* products with variant-level price, SKU, image, stock, weight, barcode, or fulfillment differences;
* products with custom options, engraving, personalization, build-your-own behavior, or customer input;
* bundles, kits, subscriptions, add-ons, accessories, or product relationships;
* products with rich specifications, compatibility information, size guides, or structured technical data;
* products affected by app logic, metafields, metaobjects, theme display, or external systems;
* products that should be simplified, merged, split, or rebuilt in Shopify.

Each sample should explain the business outcome that must remain clear. The preparation question is not only whether the product record can move. The product should remain understandable, purchasable, searchable, presentable, and operationally usable inside Shopify.

#### Separate variants from descriptive or operational fields <a href="#separate-variants-from-descriptive-or-operational-fields" id="separate-variants-from-descriptive-or-operational-fields"></a>

Not every source option should become a Shopify variant. Some values represent customer choices at purchase. Others support filtering, product comparison, merchandising, fulfillment, compatibility, reporting, product storytelling, or internal administration.

| Source detail type         | Shopify preparation decision                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| True buying choice         | Review whether it should become a Shopify option and variant.                                                      |
| Descriptive product detail | Decide whether it belongs in product content, metafields, tags, or theme display.                                  |
| Filter or discovery value  | Decide whether it should support collection filters, search, tags, metafields, or app-based filtering.             |
| Personalization input      | Review whether it needs an app, theme behavior, line-item property, Custom Service, or manual configuration.       |
| Bundle or kit logic        | Identify whether Shopify-native structure, an app, or Custom Service is needed.                                    |
| External-system value      | Preserve identifier meaning only when it remains useful for ERP, fulfillment, reporting, support, or integrations. |
| Retired source field       | Exclude, archive, or deprioritize if it no longer supports the business.                                           |

Product preparation should reduce target-store confusion. Moving every available field into Shopify without role classification can create weak product pages, noisy filtering, unnecessary metafields, app conflicts, and harder validation.

### Prepare Collections, Navigation, and Browse Paths <a href="#prepare-collections-navigation-and-browse-paths" id="prepare-collections-navigation-and-browse-paths"></a>

Shopify discovery depends on collections, menus, product data, filters, tags, metafields, themes, redirects, and sometimes search or merchandising apps. Source categories should therefore be reviewed as customer journeys, not only as category labels.

Prepare evidence for:

* source category trees and high-value category-equivalent paths;
* product groups that drive revenue, traffic, seasonal campaigns, or merchandising decisions;
* collections that should be manual, rule-based, app-supported, or rebuilt in Shopify;
* products assigned to multiple categories with different customer meanings;
* filter values, product types, vendors, tags, metafields, or attributes that support discovery;
* navigation menus, mega menus, landing pages, and campaign paths;
* obsolete categories, retired campaigns, duplicated categories, or low-value paths that should not be recreated as active navigation.

A Shopify collection can contain the right products but still fail if the path no longer supports the shopper’s intent. Preparation should identify which browse paths must remain commercially useful, which can be simplified, and which need redirect or content planning.

#### Connect collection planning to URL planning <a href="#connect-collection-planning-to-url-planning" id="connect-collection-planning-to-url-planning"></a>

Collection decisions and URL decisions should be prepared together. A source category may become a Shopify collection, a landing page, a menu item, a filtered view, a redirect destination, or a retired path. High-value category URLs should not be redirected mechanically without considering customer intent and search value.

### Prepare Markets, Domains, and Localization Priorities <a href="#prepare-markets-domains-and-localization-priorities" id="prepare-markets-domains-and-localization-priorities"></a>

Shopify Markets can help organize international selling, but international migration still needs target-state decisions. Source stores may represent regions through separate stores, language paths, country domains, duplicated catalogs, customer groups, currency rules, tax assumptions, apps, or custom logic.

Prepare a market and localization map with these items:

| Planning item                       | What to document                                                                                               |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Priority markets                    | Countries or regions that must work at launch.                                                                 |
| Languages                           | Product, collection, CMS Page, Blog Post, metadata, and policy content that needs localized review.            |
| Currencies and pricing expectations | Whether currency, regional pricing, discounts, or price display expectations need configuration or app review. |
| Domains and paths                   | Domains, subdomains, subfolders, language paths, and localized legacy URLs that matter commercially.           |
| Regional catalog differences        | Products, collections, content, availability, or navigation that differ by market.                             |
| Validation samples                  | Market-specific products, collections, pages, customers, and URLs that should be checked after Demo Migration. |

International preparation should focus on what customers need to see and do in each priority market. The Target Store should guide the customer to the right language, market context, product availability, and buying path.

### Prepare App, Metafield, Metaobject, and Theme Dependencies <a href="#prepare-app-metafield-metaobject-and-theme-dependencies" id="prepare-app-metafield-metaobject-and-theme-dependencies"></a>

Shopify migrations become more sensitive when app-owned or custom-data-owned meaning is treated as ordinary migrated data. Apps, metafields, metaobjects, theme sections, external systems, and custom logic can support product display, reviews, filtering, subscriptions, bundles, loyalty, fulfillment, pricing, reporting, localization, and customer segmentation.

Prepare a dependency inventory before migration configuration:

| Dependency type | Preparation question                                                                                | Likely handling                                                                            |
| --------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Shopify app     | Which business behavior will the app own after migration?                                           | App setup, app import, vendor support, or separate configuration may be needed.            |
| Metafield       | What business meaning does the field carry?                                                         | Structure, namespace, field type, visibility, and display/use-case planning may be needed. |
| Metaobject      | Is the data reusable structured content or a repeated business object?                              | Target modeling and theme/app use should be planned before migration.                      |
| Theme behavior  | Does the storefront need to display or use migrated values?                                         | Theme setup, template review, app blocks, or implementation work may be needed.            |
| External system | Does the value support ERP, CRM, PIM, warehouse, marketplace, tax, marketing, or support workflows? | Identifier continuity and integration review may be needed.                                |
| Custom logic    | Does the behavior depend on source code, plugin logic, custom rules, or non-standard storage?       | Custom Service review is usually safer.                                                    |

Do not assume apps, themes, or external integrations will inherit source behavior automatically. The migration may move commerce records while app configuration, app-owned data, theme display, and integration behavior still need separate setup and validation.

#### Classify custom fields by use case before mapping <a href="#classify-custom-fields-by-use-case-before-mapping" id="classify-custom-fields-by-use-case-before-mapping"></a>

Custom fields should have a current purpose before they are mapped into Shopify. Useful categories include storefront display, product comparison, filtering, search, reporting, fulfillment, compliance, merchandising, customer service, integration matching, and internal administration.

Fields with no current purpose can create clutter. Fields with operational or customer-facing purpose need more careful planning, especially when they affect product selection, app behavior, external systems, or launch validation.

### Prepare Customer and Order Context <a href="#prepare-customer-and-order-context" id="prepare-customer-and-order-context"></a>

Customer and order preparation should focus on continuity of business meaning. A migrated customer record does not guarantee the same login, account activation, customer group, loyalty status, subscription access, wholesale experience, or historical-order presentation.

Prepare samples that include:

* registered customers and guest-checkout customers;
* customers with multiple addresses;
* customers with tags, groups, segments, tax status, wholesale context, or loyalty/subscription relationships;
* returning customers who expect order history or account continuity;
* orders with discounts, taxes, refunds, cancellations, partial fulfillment, gift cards, shipping differences, or multiple payment statuses;
* orders linked to external systems, support workflows, marketplaces, accounting systems, fulfillment systems, or reporting references.

Customer and order history should be validated for usefulness, not only presence. Support teams, fulfillment teams, finance teams, and returning customers may rely on historical context differently.

#### Define returning-customer expectations before launch <a href="#define-returning-customer-expectations-before-launch" id="define-returning-customer-expectations-before-launch"></a>

Returning-customer preparation should answer practical questions:

* What should customers expect when they access their account after launch?
* Will account activation, password reset, or communication be needed?
* Which customer groups, tags, or segments affect pricing, communication, or service?
* Which order-history fields need to remain useful for support and reporting?
* Which loyalty, subscription, wholesale, or membership behavior depends on apps or external systems?

These expectations should be prepared before go-live planning. Otherwise, customer-support issues may appear after launch even when customer records migrated successfully.

### Prepare URL, Redirect, and SEO Priority Lists <a href="#prepare-url-redirect-and-seo-priority-lists" id="prepare-url-redirect-and-seo-priority-lists"></a>

Shopify preparation should protect the URLs that matter most rather than treating every legacy path equally. Source stores may use category paths, product IDs, brand paths, language paths, CMS Page paths, Blog Post paths, custom routes, campaign URLs, or platform-specific URL patterns that do not map one-to-one into Shopify.

Prepare a URL priority list with these groups:

| URL group                             | Preparation focus                                                                       |
| ------------------------------------- | --------------------------------------------------------------------------------------- |
| Top organic landing pages             | Preserve or redirect pages that carry search traffic.                                   |
| Revenue-driving product pages         | Confirm target handles, collection context, and redirect destinations.                  |
| Priority collection or category paths | Protect customer discovery paths and high-value search entry points.                    |
| CMS Pages and Blog Posts              | Confirm content paths, old URLs, target destinations, and localization needs.           |
| Campaign and paid-media URLs          | Decide whether to preserve, redirect, retire, or rebuild landing pages.                 |
| External-link destinations            | Review backlinks, affiliate links, partner links, support links, and bookmarked routes. |
| Localized URLs                        | Confirm language, market, domain, and regional path expectations.                       |

A useful URL list should include the source URL, preferred Shopify destination, page type, business value, redirect requirement, language or market context, and validation priority.

### Prepare Access, Backups, and Store Controls <a href="#prepare-access-backups-and-store-controls" id="prepare-access-backups-and-store-controls"></a>

Migration preparation also needs operational readiness. The project should not rely only on content and data decisions while access, permissions, backup expectations, or store controls remain unclear.

Prepare these operational items:

* source-store admin access with permission to review and export relevant data;
* Shopify admin access with enough permission for migration setup and validation;
* collaborator access or staff-account arrangements where needed;
* API or app access required for supported migration steps;
* source-store backup or rollback reference appropriate to the platform;
* target-store backup, duplicate theme, staging theme, or pre-launch review method where relevant;
* password protection, storefront visibility, payment-test mode, shipping setup, tax settings, domain timing, and launch controls;
* agreement on who will validate results and who can approve launch-critical decisions.

Access preparation reduces delays during Demo Migration, Full Migration, validation, and launch review. It also clarifies whether the customer will execute actions directly or whether Next-Cart will perform agreed actions under Managed Service or Custom Service with Expert Handle.

### Prepare Demo Migration Review Samples <a href="#prepare-demo-migration-review-samples" id="prepare-demo-migration-review-samples"></a>

Demo Migration is most useful when the sample is chosen to expose real Shopify risk. A sample made only from simple records can create false confidence. Preparation should select records that reveal whether the source-store meaning can be represented cleanly in Shopify.

A strong Shopify sample usually includes:

* simple products and structurally complex products;
* products with multiple options, variants, images, SKUs, stock differences, and price differences;
* products that depend on metafields, metaobjects, apps, or theme display;
* priority collections and category-equivalent paths;
* CMS Pages and Blog Posts that affect trust, SEO, support, or campaign continuity;
* customer records with addresses, tags, groups, or support importance;
* orders with different statuses, discounts, taxes, fulfillment situations, refunds, and notes;
* important legacy URLs and localized paths;
* source records that may require Add-ons, Custom Service, or post-migration configuration.

Demo Migration review should confirm whether the Shopify result is commercially understandable. It should not be limited to checking whether record counts match.

### Identify Preparation Findings That Affect the Service Path <a href="#identify-preparation-findings-that-affect-the-service-path" id="identify-preparation-findings-that-affect-the-service-path"></a>

Preparation should make service-path selection more evidence-based. It should not force a final service choice too early, but it should identify whether the Shopify migration appears suitable for Standard Service, whether execution support is needed through Managed Service, whether Add-ons are relevant, or whether Custom Service is safer.

| Finding                                                                                                                                                                      | Possible implication                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Supported product, customer, order, content, and collection data with clear target decisions                                                                                 | Standard Service may be enough if the migration path supports the needed entities and the customer can execute and validate the work. |
| Customer wants Next-Cart to execute migration actions and coordinate the process                                                                                             | Managed Service may be appropriate when the migration remains within supported service scope.                                         |
| Selected records, mapped fields, or configured data need special handling within supported capability                                                                        | Data Filter Add-on, Advanced Data Mapping, or Advanced Data Configure may be relevant.                                                |
| App/plugin/module/extension data, Custom Platform source structure, custom fields, outside-system identifiers, broader transformation, or custom migration logic is required | Custom Service review is usually safer.                                                                                               |
| Customer lacks confidence evaluating Shopify-specific results                                                                                                                | Expert Handle or clearer validation planning may be needed depending on the final service model.                                      |
| Late source-store activity may affect launch freshness                                                                                                                       | Additional Migration Options may be relevant after the first Full Migration result is reviewed.                                       |

Service-path signals should be documented during preparation so Article 6 decisions are based on real Shopify conditions, not assumptions about store size or Entity Points alone.

### A Practical Shopify Preparation Sequence <a href="#a-practical-shopify-preparation-sequence" id="a-practical-shopify-preparation-sequence"></a>

Preparation works best when the team moves from business-critical outcomes to migration configuration details.

#### 1. Start with product families that expose Shopify model pressure <a href="#id-1-start-with-product-families-that-expose-shopify-model-pressure" id="id-1-start-with-product-families-that-expose-shopify-model-pressure"></a>

Prioritize best sellers, complex options, variant-heavy products, bundled products, custom-product behavior, app-dependent products, and products with high support or fulfillment impact.

#### 2. Review collection-led discovery <a href="#id-2-review-collection-led-discovery" id="id-2-review-collection-led-discovery"></a>

Identify the collections, menus, filters, landing pages, and product groups that customers use to find and compare products.

#### 3. Map markets, domains, and priority URLs <a href="#id-3-map-markets-domains-and-priority-urls" id="id-3-map-markets-domains-and-priority-urls"></a>

Prepare international structure, localized paths, old URLs, redirect destinations, high-value pages, and launch-critical routes together.

#### 4. Classify apps, metafields, metaobjects, and custom behavior <a href="#id-4-classify-apps-metafields-metaobjects-and-custom-behavior" id="id-4-classify-apps-metafields-metaobjects-and-custom-behavior"></a>

Separate native Shopify behavior from app data, metafields, theme display, external-system values, and custom logic.

#### 5. Define customer and order continuity expectations <a href="#id-5-define-customer-and-order-continuity-expectations" id="id-5-define-customer-and-order-continuity-expectations"></a>

Clarify account access, order history, customer grouping, subscription/loyalty/wholesale dependencies, and customer-support expectations.

#### 6. Prepare operational access and backups <a href="#id-6-prepare-operational-access-and-backups" id="id-6-prepare-operational-access-and-backups"></a>

Confirm source-store access, Shopify admin permissions, app/API access, backup references, target-store controls, and launch responsibilities.

#### 7. Build Demo Migration samples around highest-risk examples <a href="#id-7-build-demo-migration-samples-around-highest-risk-examples" id="id-7-build-demo-migration-samples-around-highest-risk-examples"></a>

Use Demo Migration to test the future Shopify model, not only to confirm that simple records can move.

### Final Preparation Check <a href="#final-preparation-check" id="final-preparation-check"></a>

A prepared Shopify migration should make the future Target Store easier to configure, test, and approve. Before moving into execution, the customer should know which product structures, collection paths, app dependencies, market assumptions, customer scenarios, URLs, and service-path signals require close review.

#### Common questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to Shopify?**

Start with the product families, collections, URLs, customer scenarios, app dependencies, and market paths most likely to affect revenue, customer trust, or operational continuity. These areas reveal Shopify-specific risk more reliably than record counts alone.

**Why is product classification so important for Shopify preparation?**

Shopify separates product meaning into products, options, variants, metafields, tags, collections, apps, themes, and content. A source detail may migrate but still fail if it lands in the wrong role. Product classification helps protect buying clarity and long-term maintainability.

**Should Shopify preparation include apps and metafields?**

Yes. Apps, metafields, metaobjects, and theme behavior often carry storefront, operational, integration, or customer-experience meaning. They should be classified before migration so the team knows what can be handled through standard data migration and what may need configuration, Add-ons, or Custom Service.

**Does a higher Entity Points Plan solve Shopify preparation risk?**

No. A higher Entity Points Plan increases migration capacity for counted data, but it does not decide how Shopify should represent products, collections, apps, metafields, Markets, URLs, or customer-account expectations. Those decisions still need preparation and validation.

**When should Custom Service be considered during Shopify preparation?**

Custom Service should be considered when the migration depends on Custom Platform source structures, app/plugin/module/extension data, custom fields, outside-system identifiers, custom migration logic adjustments, or broader transformations that cannot be handled safely with standard service capabilities alone.
