# Adobe Commerce Validation Priorities

Adobe Commerce validation should prove that the Target Store can support the intended operating model, not only that records transferred. Enterprise Adobe Commerce projects often include B2B company accounts, shared catalogs, buyer-specific pricing, website/store/store-view scope, governed catalog visibility, complex product relationships, content timing, inventory configuration, integrations, extensions, and custom business logic. These areas require validation against business behavior, not simple record counts.

Validation should begin with representative samples from the Demo Migration and continue through Full Migration review. A useful sample set includes high-value products, configurable product families, company buyers, shared catalogs, scoped storefront content, priority URLs, inventory-sensitive items, orders, custom fields, integration identifiers, and any records affected by Add-ons or Custom Service. Each sample should have a clear owner and an acceptance decision.

The customer remains responsible for final result verification because only the customer can confirm whether buyer access, pricing visibility, storefront behavior, operational reporting, and integration meaning are correct for the business. Next-Cart can support validation within the selected service scope, but launch approval should be based on documented evidence.

### What Validation Means for Adobe Commerce <a href="#what-validation-means-for-adobe-commerce" id="what-validation-means-for-adobe-commerce"></a>

Adobe Commerce validation checks whether migrated data behaves correctly inside a complex enterprise commerce environment. A product may exist in the Admin but fail validation if its child SKUs, attributes, prices, visibility, inventory, category placement, storefront scope, or shared catalog access does not support buying. A company account may exist but fail validation if buyers cannot log in, see the right catalog, access the correct prices, or place orders according to the expected workflow.

Validation should answer five practical questions:

| Validation question                              | Adobe Commerce proof point                                                                                             |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| Is the migrated data complete enough for launch? | Required products, customers, companies, orders, content, URLs, and operational records are present.                   |
| Does the data behave correctly?                  | Buyers can browse, see prices, select products, and complete expected actions in the right storefront context.         |
| Is enterprise access correct?                    | Company users, roles, customer groups, shared catalogs, and pricing visibility align with the target operating model.  |
| Can internal teams operate the Target Store?     | Admin users can interpret product data, order history, customer relationships, inventory, and integration identifiers. |
| Are unresolved exceptions understood?            | Add-ons, Custom Service items, manual setup, external dependencies, and accepted limitations are documented.           |

A validation pass should be based on evidence, not assumptions. Adobe Commerce has enough scope and configuration depth that a correct-looking record can still be commercially wrong if relationships or visibility are incomplete.

### Validate Product Architecture and Catalog Behavior <a href="#validate-product-architecture-and-catalog-behavior" id="validate-product-architecture-and-catalog-behavior"></a>

Product validation should begin with product families that represent the store’s real catalog complexity. Adobe Commerce may include simple, configurable, grouped, bundle, virtual, and downloadable products. Configurable products need special attention because buying behavior depends on the parent product, child SKUs, option values, attributes, price behavior, stock behavior, URL behavior, and category placement working together.

Review samples from each important product pattern:

| Product sample                  | Validation focus                                                                                                                        |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Simple product                  | SKU, name, price, tax class, stock status, images, categories, URLs, and storefront visibility.                                         |
| Configurable product            | Parent-child relationship, option labels, child SKU assignment, swatch or dropdown behavior, images, price display, and purchasability. |
| Bundle or grouped product       | Component relationships, quantities, price calculation, option display, and checkout behavior.                                          |
| Downloadable or virtual product | Delivery logic, customer access expectations, order history meaning, and product-type interpretation.                                   |
| High-value product              | SEO path, images, attributes, category placement, customer-group pricing, inventory, and launch priority.                               |

Product validation should include storefront checks and Admin checks. Storefront checks confirm whether buyers can find and purchase products. Admin checks confirm whether the migrated data is maintainable by catalog, merchandising, operations, and integration teams.

### Validate Attributes, Attribute Sets, and Searchable Meaning <a href="#validate-attributes-attribute-sets-and-searchable-meaning" id="validate-attributes-attribute-sets-and-searchable-meaning"></a>

Adobe Commerce catalog meaning often depends on attributes and attribute sets. Product records can transfer while losing the structure that makes them searchable, filterable, comparable, maintainable, or usable in promotions and integrations. Validation should confirm that attribute values did not move as unstructured text when structured product meaning is needed.

Review attribute evidence across representative products:

| Attribute area     | What to validate                                                                                                                                         |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Attribute sets     | Products belong to the expected attribute sets and retain the fields required for merchandising and operations.                                          |
| Option values      | Select, multiselect, swatch, and configurable-option values remain consistent and buyer-readable.                                                        |
| Search and filters | Searchable, filterable, comparable, and layered-navigation values support storefront discovery.                                                          |
| Scoped values      | Store-view-specific names, descriptions, URLs, labels, and localized values appear in the intended scope.                                                |
| Integration values | ERP, PIM, CRM, warehouse, tax, or reporting identifiers remain traceable where they are in scope.                                                        |
| Custom fields      | Custom attributes, extension-owned fields, and nonstandard values are classified as standard, Add-on-supported, Custom Service, manual, or out of scope. |

If an attribute affects buying, pricing, filtering, fulfillment, reporting, or integration matching, it should be validated with a real sample. Cosmetic attributes can be reviewed later only when they do not affect launch-critical behavior.

### Validate B2B Company Accounts and Buyer Access <a href="#validate-b2b-company-accounts-and-buyer-access" id="validate-b2b-company-accounts-and-buyer-access"></a>

Adobe Commerce B2B validation should separate individual customer data from company-level buying relationships. A company account can affect administrators, company users, roles, permissions, credit settings, quote behavior, purchase order behavior, payment access, shipping access, shared catalog assignment, and pricing visibility. A migrated customer record alone does not prove that the B2B operating model works.

Validate B2B samples from the buyer perspective and the Admin perspective:

| B2B validation area        | Pass condition                                                                                                    |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Company account            | The company record is present, understandable, and assigned to the right administrators and users.                |
| Company users              | Buyers can log in and see only the access expected for their role.                                                |
| Roles and permissions      | Purchasing, approval, account management, and administrative actions match the intended structure where included. |
| Credit and payment context | Credit, payment, purchase order, or payment-method expectations are documented and validated where included.      |
| Shipping context           | Company-specific or buyer-specific shipping expectations are documented and tested where included.                |
| External account IDs       | ERP account codes, dealer IDs, procurement IDs, or other identifiers remain traceable when required.              |

For hybrid B2B/B2C stores, validate both buyer models. Retail customers and company buyers may use different account flows, pricing logic, order visibility, and storefront expectations.

### Validate Shared Catalogs and Buyer-Specific Pricing <a href="#validate-shared-catalogs-and-buyer-specific-pricing" id="validate-shared-catalogs-and-buyer-specific-pricing"></a>

Shared catalog and pricing validation should prove that the right buyers see the right products at the right prices. Adobe Commerce projects can fail commercially if catalog records are present but product visibility or pricing is wrong for companies, customer groups, or negotiated buyer relationships.

Use buyer-based test cases, not only Admin record checks:

| Pricing and visibility test          | Validation action                                                                                                               |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| Company assigned to a shared catalog | Log in as a buyer and confirm product visibility, category access, search results, and price display.                           |
| Company with restricted products     | Confirm restricted items are hidden or unavailable to the buyer.                                                                |
| Company with negotiated pricing      | Confirm the intended price appears in product listing, product detail, cart, and checkout where applicable.                     |
| Customer group pricing               | Confirm group-specific prices, tier prices, or discounts appear only for the correct buyers.                                    |
| Price exception                      | Confirm exceptions are documented as migrated, configured, Add-on-supported, Custom Service, external, manual, or out of scope. |

Pricing validation should be conservative. A price that looks correct for one buyer may still be wrong for another company, catalog, group, storefront, or quantity tier.

### Validate Website, Store, and Store-View Scope <a href="#validate-website-store-and-store-view-scope" id="validate-website-store-and-store-view-scope"></a>

Adobe Commerce scope validation is essential for multi-brand, multi-region, multilingual, multi-currency, B2B/B2C, or staged rollout environments. Websites, stores, and store views can affect catalog visibility, configuration, language, URLs, content, pricing behavior, customer behavior, and operational ownership.

Review scope with samples from each meaningful business context:

| Scope area      | What to validate                                                                                                   |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| Website         | The correct catalog, customer behavior, pricing context, and business channel appear under the right website.      |
| Store           | Category structure, navigation, merchandising, and storefront purpose match the intended store.                    |
| Store view      | Language, localized product values, localized content, labels, URL paths, and buyer-facing text appear correctly.  |
| Domain or route | Priority domains, landing pages, product URLs, category URLs, CMS Page URLs, and Blog Post URLs resolve correctly. |
| Visibility      | Products, categories, content, and prices appear only in the intended scope.                                       |

A scoped value should be validated in the storefront where customers or buyers will actually use it. Admin-level presence alone is not enough for launch approval.

### Validate Inventory, Fulfillment, and Availability Signals <a href="#validate-inventory-fulfillment-and-availability-signals" id="validate-inventory-fulfillment-and-availability-signals"></a>

Adobe Commerce inventory validation should confirm that buyers can see and purchase products according to the intended fulfillment model. Quantity fields are not enough when a store uses multiple sources, stocks, warehouses, reservations, backorders, pickup locations, external fulfillment systems, or integration-driven availability.

Validate inventory-sensitive samples:

| Inventory area            | Validation focus                                                                                                               |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Stock status              | Products appear in stock or out of stock according to the launch plan.                                                         |
| Salable quantity          | Availability matches the target inventory model where applicable.                                                              |
| Multiple sources          | Source assignment, stock assignment, warehouse references, or fulfillment ownership are documented where in scope.             |
| Configurable products     | Child SKU availability supports the parent product’s visible options.                                                          |
| Backorders and thresholds | Special availability rules are documented and tested where relevant.                                                           |
| External inventory        | ERP, WMS, marketplace, or fulfillment-system dependencies are identified and excluded, configured, or custom-scoped as needed. |

Inventory validation should distinguish migrated data from target-side configuration and external synchronization. Otherwise, a launch team may treat an integration or configuration issue as a migration result, or miss a real migration gap.

### Validate URLs, Content, and Campaign Timing <a href="#validate-urls-content-and-campaign-timing" id="validate-urls-content-and-campaign-timing"></a>

Adobe Commerce validation should include SEO-sensitive and content-sensitive records. Product records, categories, CMS Pages, Blog Posts, URL rewrites, redirects, landing pages, and staged campaigns can affect traffic, buyer trust, and launch timing.

Review the routes and content most likely to affect launch:

| Content or URL area        | Validation focus                                                                                                             |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Product URLs               | High-value product paths resolve to the correct Target Store product pages.                                                  |
| Category URLs              | Important category paths, navigation links, and listing pages remain usable.                                                 |
| CMS Pages                  | Priority landing pages, policy pages, brand pages, and support pages display correct content and links.                      |
| Blog Posts                 | Important educational or SEO-sensitive posts retain accessible paths where included.                                         |
| Redirects and URL rewrites | Priority legacy URLs route to the intended target destinations.                                                              |
| Content Staging            | Time-sensitive campaigns, scheduled content, and launch-specific promotions are documented and validated according to scope. |

For staged or campaign-driven stores, validation should record whether campaign content migrated, was configured in Adobe Commerce, was rebuilt manually, or remains outside migration scope.

### Validate Customers, Orders, and Historical Context <a href="#validate-customers-orders-and-historical-context" id="validate-customers-orders-and-historical-context"></a>

Customer and order validation should prove that historical records remain useful for customer service, account management, finance, reporting, and operational review. Adobe Commerce may not reproduce every source workflow exactly, especially when the source used extensions, custom checkout logic, external quote systems, ERP invoicing, procurement workflows, or custom payment rules.

Validate a representative order set:

| Order sample                      | Validation focus                                                                                                            |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Completed order                   | Customer, products, quantities, prices, taxes, shipping, discounts, payment reference, and order status are understandable. |
| Refunded or canceled order        | Historical status and financial context are preserved clearly enough for support and accounting review.                     |
| B2B company order                 | Company, buyer, user, account, pricing, and purchasing context are traceable where included.                                |
| Discounted or tax-sensitive order | Discount, tax, shipping, and total interpretation remain coherent.                                                          |
| Integration-dependent order       | ERP, CRM, fulfillment, payment, marketplace, or reporting identifiers remain traceable where included.                      |

The validation goal is historical coherence, not reactivating old workflows. A migrated order should be understandable to the teams that need to support it after launch.

### Validate Add-ons, Custom Service Items, and External Dependencies <a href="#validate-add-ons-custom-service-items-and-external-dependencies" id="validate-add-ons-custom-service-items-and-external-dependencies"></a>

Adobe Commerce validation should classify each exception clearly. Enterprise migrations often include extension-owned values, custom attributes, ERP/PIM/CRM references, tax logic, payment data, warehouse IDs, company-specific rules, approval workflows, quote behavior, external contract pricing, or custom module logic.

Use this classification during validation:

| Exception class            | Validation decision                                                                           |
| -------------------------- | --------------------------------------------------------------------------------------------- |
| Standard migration scope   | Confirm the record moved and behaves as expected.                                             |
| Add-ons                    | Confirm the filtered, mapped, or configured output matches the accepted request.              |
| Custom Service             | Confirm bespoke handling was scoped, implemented, reviewed, and approved.                     |
| Target-side configuration  | Confirm the customer or implementation team completed and validated the Adobe Commerce setup. |
| External-system dependency | Confirm the dependency is excluded, integrated, manually handled, or custom-scoped.           |
| Out of scope               | Confirm the limitation, workaround, owner, and launch impact are documented.                  |

Add-ons can support defined filtering, mapping, or configuration needs. Custom Service should be reviewed when the result depends on unsupported logic, Custom Platform handling, custom modules, extension-owned structures, or bespoke target-side interpretation. These are related but not interchangeable.

### Validate Additional Migration Options Before Approval <a href="#validate-additional-migration-options-before-approval" id="validate-additional-migration-options-before-approval"></a>

Additional Migration Options should be considered when source-store activity continues after the main migration, when selected new records need to be brought forward before launch, or when a controlled follow-up action is needed after target-side configuration changes. Validation should treat each later migration action as something that can affect launch evidence.

A follow-up migration action should be validated against the affected scope:

| Follow-up condition                                         | Validation priority                                                                                                 |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| New products or content were added after the main migration | Confirm new records appear in the right storefront scope, categories, shared catalogs, URLs, and content locations. |
| New customers, companies, or orders were added              | Confirm account relationships, company context, order history, and buyer visibility remain coherent.                |
| Target configuration changed                                | Recheck the records affected by scope, catalog, B2B, pricing, URL, or inventory configuration changes.              |
| Selected records were brought forward                       | Confirm only the intended records changed and previously approved records were not disrupted.                       |

Entity Points should be interpreted consistently during follow-up validation. New Product, Customer, Order, and Blog Posts records consume Entity Points when migrated for the first time. Records already counted through the service license do not consume Entity Points again simply because the customer performs another migration action. New eligible records may consume Entity Points when migrated for the first time, even when the customer performs a new migration for the same migration path.

### Build a Validation Evidence Set <a href="#build-a-validation-evidence-set" id="build-a-validation-evidence-set"></a>

A launch decision should be based on documented evidence. Adobe Commerce validation should include both business-owner review and technical-owner review because errors can appear in storefront behavior, Admin interpretation, integrations, content, inventory, pricing, and B2B account access.

A strong validation evidence set includes:

* source and target record IDs for each sample;
* screenshots or exports showing before-and-after values;
* buyer-role testing for company accounts, shared catalogs, and pricing;
* storefront checks for product families, scoped views, categories, URLs, content, and checkout-sensitive records;
* Admin checks for attributes, inventory, orders, custom fields, and operational identifiers;
* owner signoff from catalog, B2B, marketing, SEO, operations, IT, finance, and customer service teams where relevant;
* classification of accepted exceptions, launch blockers, Add-on items, Custom Service items, external dependencies, and deferred work.

Validation evidence should remain traceable. A pass should identify who reviewed the result, what sample was tested, what behavior was expected, what evidence was captured, and whether the result is approved, rejected, deferred, or accepted with limitations.

### Decide Whether the Adobe Commerce Result Is Launch-Ready <a href="#decide-whether-the-adobe-commerce-result-is-launch-ready" id="decide-whether-the-adobe-commerce-result-is-launch-ready"></a>

Adobe Commerce launch readiness should depend on whether the Target Store can support the intended enterprise operating model with acceptable risk. Small cosmetic issues may be deferred if they do not affect buying, buyer access, pricing visibility, catalog accuracy, checkout, SEO continuity, fulfillment, reporting, or integration traceability. Structural issues should not be treated as minor.

Use a launch-readiness decision table:

| Result status                            | Meaning                                                                                                                           | Launch decision                                                                                     |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Launch-ready                             | Core catalog, B2B, pricing, scoped storefront, content, inventory, URL, order, and integration samples pass.                      | Proceed when final business owners approve the result.                                              |
| Launch-ready with accepted exceptions    | Known gaps are non-blocking, documented, owned, and accepted.                                                                     | Proceed only if the exceptions have timing, owner, and workaround notes.                            |
| Needs correction before launch           | Issues affect buying, company access, price visibility, inventory, checkout, priority URLs, content, or operational traceability. | Resolve before launch or revise launch scope.                                                       |
| Requires Custom Service or external work | The issue depends on unsupported logic, custom modules, external systems, or bespoke transformation.                              | Review Custom Service, implementation work, integration work, or target-side setup before approval. |

Validation should not end with a statement that data exists. It should end with a decision about whether the Target Store can operate as intended.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce validation should prove that enterprise commerce behavior is ready for launch. Product relationships, attributes, scoped storefront values, B2B company access, shared catalogs, buyer-specific pricing, inventory, content, URLs, orders, integrations, Add-ons, Custom Service items, and Additional Migration Options all need evidence when they affect the business result.

A strong validation process uses representative samples, buyer-role tests, Admin review, storefront checks, exception classification, owner signoff, and documented launch decisions. When validation exposes unsupported logic, incorrect visibility, incomplete pricing behavior, missing relationships, or external-system dependencies, those findings should be resolved through the right service path before Full Migration is treated as launch-ready.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is record count matching enough to validate an Adobe Commerce migration?**

No. Record counts are useful, but Adobe Commerce validation also needs behavior checks. Company access, shared catalog visibility, storefront scope, product relationships, inventory availability, URL continuity, content timing, pricing, and order history should be reviewed with representative records.

**What should be validated first for a B2B Adobe Commerce store?**

Start with company accounts, company administrators, company users, shared catalog assignment, pricing visibility, buyer-role access, and purchase-related permissions where included in scope. These areas determine whether business buyers can actually use the Target Store.

**How should shared catalog validation be handled?**

Test at least one company assigned to each important shared catalog or pricing model. Confirm that each buyer sees the intended products, prices, search results, category navigation, and checkout options, and confirm that restricted products or prices are not visible to the wrong buyer.

**Why is scope validation important in Adobe Commerce?**

Adobe Commerce can use websites, stores, and store views. Content, configuration, product values, URLs, language values, and storefront behavior may depend on scope. Multi-brand, multi-region, multilingual, or multi-currency stores should validate each relevant scope before launch.

**When should Additional Migration Options be considered during Adobe Commerce validation?**

Additional Migration Options should be considered when source-store activity continues after the main migration, when selected records need to be brought forward before launch, or when the target result needs another controlled migration action after configuration or scope changes. The selected option should be validated before launch approval.

**Who is responsible for final Adobe Commerce validation?**

The customer is responsible for final result verification because only the customer can confirm whether company access, pricing visibility, storefront scope, order history, integrations, content, and operational workflows are correct for the business. Next-Cart can support the process according to the selected service scope.
