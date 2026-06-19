# Shopify Validation Priorities

Shopify validation should confirm that migrated store data works inside Shopify’s hosted operating model, not only that records appear in the Target Store. Products must behave correctly as Shopify products with options and variants. Categories must translate into usable collections and navigation. URLs must preserve priority customer and search-engine paths. Customer, order, content, metafield, app, and market-specific details must support the way the business will operate after launch.

Validation should focus on launch-critical outcomes first. A Shopify Target Store can look clean at a visual level while still containing product-option mismatches, missing variant details, incorrect collection placement, weak redirect coverage, incomplete metafield usage, app-dependent gaps, or customer/order context problems. Final verification remains the customer’s responsibility, even when Next-Cart performs migration actions under Managed Service, Custom Service, or Expert Handle.

### Validate Products as Shopify Buying Experiences <a href="#validate-products-as-shopify-buying-experiences" id="validate-products-as-shopify-buying-experiences"></a>

Product validation should confirm that migrated records support browsing, buying, merchandising, fulfillment, and administration. Shopify product structure is built around products, options, variants, media, pricing, inventory, tags, collections, metafields, and app-supported behavior. A record count alone does not prove that a product is launch-ready.

Review representative products across the main catalog patterns:

* simple products with one sellable configuration;
* products with multiple options and variants;
* products with images, variant images, SKUs, barcodes, weights, inventory quantities, and prices;
* products that previously used custom options, bundles, kits, personalization fields, subscriptions, or source-side product relationships;
* products that depend on metafields, metaobjects, apps, or theme display logic;
* products that support high-revenue categories, campaigns, seasonal sales, or priority landing pages.

A product should pass validation only when the customer can understand how it will appear, how shoppers will select the right variant, how inventory and pricing behave, and what additional Shopify configuration or app setup is still required.

#### Check Options, Variants, and Sellable Choices <a href="#check-options-variants-and-sellable-choices" id="check-options-variants-and-sellable-choices"></a>

Shopify variant validation should test whether source-store sellable choices are represented in a way that shoppers can use and staff can manage. Option names, option values, variant SKUs, variant prices, images, inventory behavior, and unavailable combinations should be reviewed carefully.

Common validation failures include options that are merged too broadly, variant names that lose business meaning, source custom options that do not become true Shopify variants, subscription or personalization choices that require app support, and products whose unavailable combinations appear selectable. These failures should be classified by business impact before launch.

#### Check Images, Media, and Product Presentation <a href="#check-images-media-and-product-presentation" id="check-images-media-and-product-presentation"></a>

Product media validation should confirm that main images, gallery images, variant images, alt text where available, and display order support the intended buying experience. Media should be tested on priority product pages, mobile layouts, collection listings, search results, and theme templates.

Image presence is not enough. Validation should check whether the right image appears for the right variant, whether imported images are attached to the correct products, whether duplicated or obsolete media should be removed, and whether app- or theme-controlled media elements must be configured outside the migration scope.

### Validate Collections, Navigation, and Merchandising Paths <a href="#validate-collections-navigation-and-merchandising-paths" id="validate-collections-navigation-and-merchandising-paths"></a>

Shopify collections are not always a one-to-one replacement for source categories. Some source category structures can become manual collections, automated collections, navigation menus, tags, metafields, redirects, content pages, or merchandising rules. Validation should confirm that customers can still find products through important browse paths.

Review priority paths such as:

* main menu categories and subcategories;
* high-traffic source category URLs;
* campaign and seasonal collections;
* brand, product-type, sale, or audience-based browsing paths;
* automated collection rules;
* collection sorting and product order where business-critical;
* tags, metafields, or app logic used for filtering and merchandising.

Collection validation should include storefront testing, not only admin review. A collection can exist in Shopify but still fail if products are missing, filters are weak, menu placement is unclear, redirects are incomplete, or merchandising rules no longer match the source-store intent.

### Validate Markets, Localization, and Regional Storefront Behavior <a href="#validate-markets-localization-and-regional-storefront-behavior" id="validate-markets-localization-and-regional-storefront-behavior"></a>

Shopify Markets can affect language, currency, domains, product availability, pricing expectations, tax and duty display, and customer experience by region. If the migration includes international or localized business requirements, validation should test the Target Store from regional customer viewpoints.

Priority checks include:

| Area                 | Validation focus                                                                                                                      |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Market structure     | Confirm which countries, regions, domains, languages, and currencies are expected at launch.                                          |
| Product availability | Check whether priority products and collections appear in the correct market context.                                                 |
| Localized content    | Review CMS Pages, Blog Posts, policy content, navigation labels, and campaign pages where localized content matters.                  |
| URLs and redirects   | Test important localized or market-specific paths against the intended Shopify destination.                                           |
| Pricing and display  | Confirm whether regional pricing, currency presentation, or market-specific visibility requires Shopify configuration or app support. |

When market behavior depends on Shopify configuration, third-party apps, manual setup, or custom scope, migration validation should document what has been migrated and what still requires Target Store configuration.

### Validate Metafields, Metaobjects, and Structured Custom Data <a href="#validate-metafields-metaobjects-and-structured-custom-data" id="validate-metafields-metaobjects-and-structured-custom-data"></a>

Metafields and metaobjects can preserve structured information that does not fit Shopify’s standard product, customer, order, collection, or content fields. They are useful only when the migrated values are defined, populated, displayed, and operationally understood.

Validation should answer four questions:

1. Are the expected metafield or metaobject definitions available in the Target Store?
2. Are migrated values attached to the correct Shopify resources?
3. Do themes, apps, or workflows actually use those values after migration?
4. Can store staff maintain those values after launch?

A migrated metafield value that is not displayed, not used by an app, not included in workflow logic, or not understood by the team may not create launch value. For app-owned or custom structured data, validation should confirm whether the requirement belongs to supported migration work, Add-ons, Shopify configuration, app setup, or Custom Service.

### Validate Apps and App-Dependent Business Data <a href="#validate-apps-and-app-dependent-business-data" id="validate-apps-and-app-dependent-business-data"></a>

Shopify apps often control subscriptions, bundles, loyalty, reviews, wholesale behavior, filters, search, product recommendations, customer segmentation, marketplaces, fulfillment workflows, or analytics. Migration validation should not assume that source app, plugin, module, or custom data becomes meaningful inside a Shopify app automatically.

For app-dependent areas, validation should classify each requirement:

| Requirement type                            | Validation decision                                                                                          |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Data migrated into supported Shopify fields | Confirm records display and behave correctly in Shopify.                                                     |
| Data prepared for app configuration         | Confirm the app can consume or interpret the migrated values after setup.                                    |
| Data requiring manual app setup             | Document the setup work outside migration output.                                                            |
| Unsupported source app/plugin/module data   | Escalate to Custom Service or exclude from migration scope.                                                  |
| External-system identifiers                 | Confirm whether identifiers must be preserved for ERP, CRM, warehouse, marketplace, or analytics continuity. |

App validation should be performed with the apps that will be used after launch, not only against the imported data in isolation.

### Validate URLs, Redirects, and SEO Continuity <a href="#validate-urls-redirects-and-seo-continuity" id="validate-urls-redirects-and-seo-continuity"></a>

Shopify URL validation should focus on the paths that matter most for traffic, revenue, search visibility, support, and campaigns. Source platforms often use different category, product, blog, page, and parameter structures from Shopify. Redirects should therefore be tested as customer and search-engine continuity assets.

Review these URL groups before launch:

* top product URLs;
* top collection or source category URLs;
* CMS Pages and policy pages;
* Blog Posts and editorial landing pages;
* campaign pages and paid-media destinations;
* localized or market-specific paths;
* URLs with historical backlinks;
* URLs used in email, ads, marketplaces, or external systems.

A redirect should pass validation when it sends the visitor to the most relevant Shopify destination and avoids unnecessary loops, broken pages, duplicate target confusion, or irrelevant landing pages. Some legacy URL patterns may need manual redirect planning, app support, or Custom Service when source structures are too complex for simple path mapping.

### Validate Customers, Orders, and Account Expectations <a href="#validate-customers-orders-and-account-expectations" id="validate-customers-orders-and-account-expectations"></a>

Customer and order validation should confirm that migrated records support customer service, operational lookup, and business continuity. Shopify customer accounts, order history visibility, payment records, fulfillment information, refunds, discounts, taxes, notes, tags, addresses, and external references may not behave exactly like the source platform.

Validation should include representative customer and order samples:

* customers with multiple addresses;
* customers with tags, segments, wholesale or loyalty context;
* customers with historical orders;
* orders with discounts, coupons, taxes, shipping, refunds, cancellations, unusual statuses, and notes;
* orders linked to fulfillment, warehouse, marketplace, ERP, CRM, or support workflows;
* records with outside-system identifiers that need post-launch continuity.

Customer account validation should distinguish between migrated customer data and post-launch account behavior. Login, password, loyalty, subscription, wholesale, and customer-group behavior may require Shopify configuration, customer communication, app setup, or Custom Service depending on the requirement.

### Validate CMS Pages, Blog Posts, and Trust Content <a href="#validate-cms-pages-blog-posts-and-trust-content" id="validate-cms-pages-blog-posts-and-trust-content"></a>

Content validation should prioritize pages and posts that influence trust, SEO, support, compliance, and conversion. CMS Pages and Blog Posts should be reviewed for structure, links, embedded media, headings, tables, forms, policy text, localized variants, and destination relevance.

Priority content includes:

* homepage-supporting pages;
* About, contact, shipping, return, privacy, and policy pages;
* help or support content;
* high-traffic Blog Posts;
* campaign landing pages;
* pages with embedded forms, scripts, maps, videos, or app widgets;
* SEO-sensitive pages with internal links or backlinks.

Imported content may need manual adjustment when source HTML, shortcodes, scripts, forms, widgets, or embedded app behavior does not translate cleanly into Shopify themes or content fields.

### Validate Additional Migration Options by Scope <a href="#validate-additional-migration-options-by-scope" id="validate-additional-migration-options-by-scope"></a>

If Additional Migration Options are used before launch or after launch, validation should match the selected action. The customer should verify not only newly migrated records, but also how the action affected existing Shopify data, redirects, collections, app-dependent fields, and launch-critical flows.

| Additional action context                               | Shopify validation focus                                                                                                                          |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Continue the Migration with the last used configuration | Confirm new source activity was added correctly and existing validated results remain stable.                                                     |
| Continue the Migration with a new configuration         | Confirm changed mapping, filtering, or configuration decisions affected the intended records only.                                                |
| Perform a new migration                                 | Confirm target cleanup, duplicate prevention, replacement expectations, and full result integrity before treating the new output as launch-ready. |

Additional Migration Options do not remove the need for final verification. They usually create a new validation scope because products, variants, collections, customers, orders, URLs, content, or app-dependent values may have changed.

### Prioritize Validation by Launch Risk <a href="#prioritize-validation-by-launch-risk" id="prioritize-validation-by-launch-risk"></a>

A Shopify Target Store should not be approved only because broad record counts look correct. Validation should classify issues by launch risk and business impact.

| Severity | Shopify examples                                                                                                                                                                                             | Launch decision impact                                                    |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Critical | Products cannot be purchased, variants are wrong, priority URLs break, customer/order context needed for support is missing, market-specific storefront behavior is wrong, or app-critical data is unusable. | Resolve before launch or adjust launch scope.                             |
| High     | Important collections are incomplete, redirects are weak for major pages, product media is mismatched, pricing or inventory assumptions are unclear, or key content is incomplete.                           | Resolve before launch unless explicitly accepted by stakeholders.         |
| Medium   | Some historical content, lower-priority products, older orders, tags, or optional fields need cleanup.                                                                                                       | Can be scheduled if customer-facing and operational impact is controlled. |
| Low      | Cosmetic cleanup, old legacy records, duplicate low-value content, or noncritical admin-field differences.                                                                                                   | Can often be handled after launch.                                        |

Launch approval should be based on evidence that the Target Store can support the customer journey, administrative workflow, and operational needs that matter most at cutover.

### Document What Has Been Accepted, Deferred, or Escalated <a href="#document-what-has-been-accepted-deferred-or-escalated" id="document-what-has-been-accepted-deferred-or-escalated"></a>

Final Shopify validation should produce a clear decision trail. The team should know which results passed, which issues were corrected, which differences were accepted, which items were deferred, and which requirements need Add-ons, Custom Service, app setup, manual configuration, or external-system work.

Useful validation notes include:

* validated sample records and why they are representative;
* issue severity and business impact;
* owner for each unresolved item;
* whether the item belongs to migration output, Shopify configuration, app setup, Custom Service, or manual cleanup;
* whether the item affects launch readiness;
* whether another Additional Migration Option is expected;
* final approval status before launch.

Good validation prevents post-launch surprises. It also protects the project from treating Shopify’s clean hosted interface as proof that every migrated business rule, app dependency, and customer-facing path is ready.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify validation should confirm that migrated data supports real storefront, administrative, regional, app, and launch outcomes. Product and variant behavior, collection structure, Markets, metafields, apps, URLs, customers, orders, content, and Additional Migration Options all need review in the context of the intended Target Store.

A Shopify migration is ready for launch only when customer-facing paths, operational records, and business-critical dependencies have been verified by the customer and unresolved issues have been accepted, corrected, deferred, or escalated with clear ownership.

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Is checking Shopify record counts enough for validation?**

No. Record counts help identify broad gaps, but they do not prove that products, variants, collections, URLs, Markets, apps, metafields, customers, orders, or content behave correctly in the Target Store.

**Which Shopify products should be validated first?**

Start with products that represent the main catalog patterns and launch risk: bestsellers, complex variants, products with custom display needs, products in priority collections, products with high traffic, and products affected by apps, metafields, Markets, or redirects.

**Do Shopify apps need separate validation?**

Yes. App-dependent behavior should be tested with the apps that will be used after launch. Migrated data may need app configuration, manual setup, Custom Service, or exclusion if source app data cannot be interpreted through the approved migration scope.

**Should redirects be validated for every old URL?**

Priority should start with high-traffic, high-revenue, SEO-sensitive, campaign, product, collection, CMS Page, and Blog Post URLs. Full redirect review depends on source URL complexity, launch risk, and agreed scope.

**Does using an Additional Migration Option require another validation pass?**

Yes. Any additional action can change products, variants, collections, customers, orders, URLs, content, or app-dependent values. The validation scope should match the selected action and the records affected.

**Who gives final approval after Shopify validation?**

The customer is responsible for final result verification and launch approval. Next-Cart may support or perform migration actions depending on the service model, but the customer must confirm that the Target Store result is acceptable for launch.
