# Shopify Plus Validation Priorities

Shopify Plus validation should prove that migrated data can support the enterprise operating model the merchant intends to run after launch. A result can look correct at the Shopify store level while still failing at the Plus level if B2B companies are incomplete, expansion-store scope is unclear, market-specific content is wrong, metafields are not usable, external identifiers are missing, or team permissions and workflows have not been reviewed.

The validation process should therefore test more than record presence. Products, variants, collections, customers, orders, CMS Pages, Blog Posts, redirects, and custom data need to be reviewed in the context of organization structure, business-to-business selling, international markets, integrations, and launch ownership. Shopify Plus validation is strongest when it proves that data is usable for merchandising, B2B sales, localization, fulfillment, support, finance, and external systems.

### Start With the Shopify Plus Operating Model <a href="#start-with-the-shopify-plus-operating-model" id="start-with-the-shopify-plus-operating-model"></a>

The first validation question is not whether records arrived. The first question is whether the migrated records belong to the intended Shopify Plus operating model. A merchant may run one combined B2B and D2C store, separate B2B and D2C stores, multiple regional stores, expansion stores, or a phased rollout where one store launches before others. Each structure changes what validation should prove.

| Operating area           | Validation question                                                                                         | Why it matters                                                                    |
| ------------------------ | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Organization and stores  | Are records assigned to the right store or launch scope?                                                    | A correct product in the wrong store or region can still be a launch failure.     |
| B2B                      | Are companies, buyers, catalogs, pricing expectations, and payment terms represented or prepared correctly? | B2B selling depends on more than customer contact fields.                         |
| Markets and localization | Are market, currency, language, domain, and regional content expectations understood?                       | Global selling can fail if products and content are present but not market-ready. |
| Custom data              | Are metafields, metaobjects, app data, or external IDs usable after migration?                              | Enterprise teams often depend on custom fields for operations and integrations.   |
| Apps and integrations    | Are ERP, PIM, OMS, WMS, CRM, loyalty, subscription, tax, and shipping dependencies validated?               | External systems may define the business value of the migrated record.            |

Validation should classify the target structure before reviewing individual samples. Otherwise, the team may approve clean records that do not support the actual Shopify Plus deployment.

### Validate Organization and Store-Scope Readiness <a href="#validate-organization-and-store-scope-readiness" id="validate-organization-and-store-scope-readiness"></a>

Shopify Plus often introduces organization-level review because teams may manage multiple stores, users, security settings, billing visibility, and expansion-store decisions. Migration validation should confirm which store or stores are included in the current launch, what data belongs to each store, and which decisions remain target-side setup.

For a single-store Shopify Plus migration, store-scope validation may be straightforward. The team checks whether products, customers, orders, content, and redirects appear in the intended store and whether the merchant can operate them. For multi-store or expansion-store projects, the review must be more explicit. A product may need to exist in one store but not another. A region may require different content or pricing. A B2B store may need customer and company context that should not appear in a D2C store.

| Store-scope validation area | Proof required                                                                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Included stores             | The migration result appears in the intended Shopify Plus store or stores.                                                     |
| Excluded stores             | Records not intended for a store are not treated as missing.                                                                   |
| Expansion-store assignment  | Products, content, customers, and orders are reviewed against store-specific expectations.                                     |
| User and team ownership     | The right business team can review the records it owns.                                                                        |
| Organization-level setup    | Permissions, security, billing, and store-management settings are recognized as Shopify-side configuration, not migrated data. |

A validation report should separate migration output from organization administration. A missing user permission, security setting, or store-management workflow may affect launch, but it is not the same type of issue as a missing product, customer, or order record.

### Validate Products, Variants, Collections, and Catalog Governance <a href="#validate-products-variants-collections-and-catalog-governance" id="validate-products-variants-collections-and-catalog-governance"></a>

Product validation for Shopify Plus should test sellable structure and enterprise merchandising expectations. Shopify products can carry options and variants, and inventory can be managed at the variant level. Plus projects may add complexity through combined listings, B2B catalog needs, market-specific availability, app-driven bundles, PIM-controlled attributes, subscriptions, or customized merchandising rules.

Validation should begin with representative products, not only product counts. Include simple products, variant-heavy products, image-heavy products, products assigned to collections, market-sensitive products, B2B-sensitive products, products with metafields, products connected to apps, and products with old URLs that matter for SEO.

| Product area                 | What to validate                                                                                   | Failure signal                                                                        |
| ---------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Product identity             | Title, handle, SKU logic, descriptions, vendor, product type, tags, status, and images are usable. | Products exist but cannot be managed or found confidently.                            |
| Variants                     | Options, option values, SKUs, prices, inventory, images, and variant-specific details make sense.  | Source options flatten into unclear products or variant data is mismatched.           |
| Collections                  | Manual and automated grouping expectations are clear.                                              | Collections exist but do not support navigation, merchandising, B2B, or market needs. |
| B2B catalog expectations     | Product visibility, pricing assumptions, and restricted availability are reviewed.                 | Wholesale buyers see the wrong products or pricing expectations are unclear.          |
| Market readiness             | Product availability, localization, and regional presentation are checked where relevant.          | Global storefronts show incomplete or inappropriate product data.                     |
| App-controlled product logic | Bundles, subscriptions, personalization, upsells, or custom product builders are classified.       | App-owned behavior is mistaken for ordinary product migration.                        |

Product validation should also identify what belongs to Shopify setup, app setup, Add-ons, or Custom Service. Supported mapping issues may be Add-on candidates. Unsupported product logic, external identifiers, or bespoke transformation should be reviewed for Custom Service.

### Validate B2B Companies, Customers, and Buyer Identity <a href="#validate-b2b-companies-customers-and-buyer-identity" id="validate-b2b-companies-customers-and-buyer-identity"></a>

B2B validation is one of the main reasons Shopify Plus should not be reviewed like ordinary Shopify. B2B customer meaning can include companies, buyers, locations, catalogs, pricing, currency, products, payment and shipping methods, account access, and personalized content. A customer record may migrate correctly while B2B selling context remains incomplete.

The validation set should include individual customers, B2B buyers, company-linked buyers, repeat buyers, buyers with multiple orders, accounts with incomplete contact details, and accounts with external identifiers. If company structure is part of scope, the team should test companies, locations, buyer relationships, catalog expectations, and account access assumptions.

| B2B validation area         | Proof required                                                                                                                    |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Customer profiles           | Names, emails, phone numbers, addresses, tags, notes, and historical context are readable where supported.                        |
| Companies                   | Company records or target-side company setup expectations are clear.                                                              |
| Buyers and locations        | Buyer-to-company or buyer-to-location context is represented, configured, or intentionally excluded.                              |
| Catalog and pricing context | B2B-specific product visibility and pricing expectations are validated or assigned to setup/integration work.                     |
| External IDs                | ERP, CRM, sales-rep, account, or finance identifiers are preserved, mapped, scoped for Custom Service, or excluded intentionally. |
| Customer-order links        | Representative orders connect to the right buyer context where supported.                                                         |

B2B validation should avoid assuming that a source customer group equals a Shopify Plus company, buyer, or catalog structure. The team should define what must be migrated, what must be configured in Shopify Plus, what belongs to an app or integration, and what requires Custom Service review.

### Validate Markets, Localization, Domains, and Redirects <a href="#validate-markets-localization-domains-and-redirects" id="validate-markets-localization-domains-and-redirects"></a>

International validation should prove that Shopify Plus can support the intended market experience. Markets, currencies, domains, localization, duties and import taxes, payments, and shipping can all affect how customers experience the migrated store. A product record may be correct globally but still wrong for a specific market if visibility, language, domain, pricing, or content expectations are unclear.

Validation should include region-sensitive products, localized product or content examples, high-value URLs, market-specific domain expectations, old-to-new redirect samples, top category or collection URLs, CMS Pages, Blog Posts, and checkout entry points where relevant.

| International and SEO area        | What to validate                                                                                        |
| --------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Markets                           | Which countries or regions are included in the launch scope.                                            |
| Domains and subfolders            | Whether market-specific URL expectations are handled or assigned to Shopify-side setup.                 |
| Languages and localized content   | Product, collection, page, and blog content is reviewed where localization is in scope.                 |
| Currency and pricing expectations | Regional pricing assumptions are validated, configured, integrated, or excluded.                        |
| Redirects                         | High-value old URLs point to accepted Shopify Plus destinations where supported.                        |
| CMS Pages and Blog Posts          | Content is present, readable, localized where needed, and connected to the right storefront experience. |

Redirect validation should be practical. Shopify has URL patterns and redirect constraints that may affect how old paths can be handled. The team should check high-value URLs instead of assuming every old URL can be recreated exactly.

### Validate Metafields, Metaobjects, and Custom Data <a href="#validate-metafields-metaobjects-and-custom-data" id="validate-metafields-metaobjects-and-custom-data"></a>

Shopify Plus projects often depend on custom data because enterprise stores use specialized product attributes, customer attributes, order references, merchandising content, B2B account fields, or integration identifiers. Shopify metafields can extend existing data models, and metaobjects can represent structured multi-field objects. Validation should confirm whether these structures are usable, not merely present.

A custom-data review should include representative records for products, variants, customers, orders, companies, content, and integration-owned fields. Each field should have a known source, target destination, business purpose, and owner.

| Custom-data finding                              | Validation response                                                              |
| ------------------------------------------------ | -------------------------------------------------------------------------------- |
| Supported field mapped to a suitable destination | Confirm value accuracy and display or admin usability.                           |
| Field requires a definition or validation rule   | Confirm Shopify-side setup and invalid-value handling.                           |
| Field should become a metafield                  | Confirm namespace, key, type, value, and usage.                                  |
| Structured content should become a metaobject    | Confirm fields, relationships, references, and display/use case.                 |
| App-owned data is expected                       | Review whether it belongs to Custom Service, app import, API work, or exclusion. |
| External identifier is business-critical         | Confirm preservation, mapping, integration ownership, or Custom Service scope.   |

Custom-data validation is where Add-ons and Custom Service must remain separate. Add-ons can help with supported filtering, mapping, or configuration. Custom Service is the safer path for unsupported app data, bespoke transformations, external-system identifiers, Custom Platform sources, or custom migration logic adjustment.

### Validate Orders, Fulfillment, Finance, and Integration Context <a href="#validate-orders-fulfillment-finance-and-integration-context" id="validate-orders-fulfillment-finance-and-integration-context"></a>

Historical orders should be validated for enterprise usefulness. Shopify Plus teams may need order history for support, finance, B2B account management, tax review, fulfillment analysis, customer service, or integration reconciliation. Migrated historical orders do not prove that live Shopify payment, fulfillment, tax, shipping, duties, notifications, or app workflows are configured correctly.

The validation set should include ordinary orders and exception cases: refunded orders, partially fulfilled orders, discounted orders, tax-sensitive orders, orders with payment context, orders with fulfillment references, orders linked to customers or B2B buyers, high-value orders, and orders with external system IDs.

| Order validation area   | Proof required                                                                                          |
| ----------------------- | ------------------------------------------------------------------------------------------------------- |
| Line items and totals   | Products, variants, quantities, prices, discounts, taxes, duties, and totals are readable.              |
| Customer or buyer links | Orders connect to expected customer, buyer, or company context where supported.                         |
| Payment context         | Historical payment labels or references are understandable without implying live payment setup.         |
| Fulfillment context     | Shipping, fulfillment, partial fulfillment, tracking, pickup, or delivery meaning is readable.          |
| Refunds and adjustments | Refunds, cancellations, returns, service fees, or adjustments are reviewed through sample orders.       |
| External IDs            | ERP, OMS, WMS, accounting, CRM, loyalty, or sales-channel references are preserved or scoped correctly. |

Live operational readiness requires separate Shopify Plus testing. Teams should test new orders, checkout behavior, payment methods, taxes, duties, shipping, fulfillment, notifications, apps, and permissions in the target environment.

### Validate Apps, Automation, and External Systems <a href="#validate-apps-automation-and-external-systems" id="validate-apps-automation-and-external-systems"></a>

Shopify Plus migrations often depend on apps, custom apps, APIs, Flow automation, ERP, PIM, OMS, WMS, CRM, tax platforms, shipping systems, loyalty tools, subscriptions, marketplaces, or analytics stacks. These systems can own fields, workflows, identifiers, and status meanings that do not migrate as ordinary Shopify records.

Validation should classify each dependency:

| Dependency type                 | Validation question                                                                     |
| ------------------------------- | --------------------------------------------------------------------------------------- |
| App-created product data        | Did the data migrate, remain in the app, require app import, or require Custom Service? |
| ERP or PIM ownership            | Are product, price, inventory, or external IDs aligned with the system of record?       |
| OMS or WMS ownership            | Are order, fulfillment, and inventory references usable after launch?                   |
| CRM or B2B ownership            | Are account, company, buyer, and sales context preserved or integrated?                 |
| Tax, duties, and shipping tools | Are live rules configured and tested outside historical migration review?               |
| Automation                      | Are workflow triggers, tags, statuses, and custom fields reviewed before launch?        |

The validation report should identify whether each issue is a migration correction, Shopify Plus setup task, app setup task, integration task, Add-on adjustment, Custom Service requirement, accepted limitation, or manual cleanup. That classification prevents enterprise launch teams from treating every defect as the same kind of migration problem.

### Validate Later Migration Activity Before Launch <a href="#validate-later-migration-activity-before-launch" id="validate-later-migration-activity-before-launch"></a>

Many Shopify Plus projects continue source-store activity while the target is being reviewed. New products, customers, orders, CMS Pages, Blog Posts, redirects, inventory changes, and custom-data updates may appear after an earlier migration run. Validation should therefore include a launch-window plan for continued migration activity, changed configuration, or a new migration.

| Later migration action                    | Shopify Plus validation emphasis                                                                        |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Continue with the last used configuration | Newly added records and regression samples from key products, customers, orders, URLs, and custom data. |
| Continue with a new configuration         | The changed mapping, filtering, or configuration choices plus affected records.                         |
| Perform a new migration                   | Refreshed target result, replaced earlier migrated data, scope accuracy, and enterprise launch samples. |

Entity Points should be interpreted correctly during this planning. Newly migrated eligible entities may consume Entity Points when first migrated, but already recorded entities do not consume Entity Points again simply because another migration action occurs on the same migration path.

### Build the Shopify Plus Validation Report <a href="#build-the-shopify-plus-validation-report" id="build-the-shopify-plus-validation-report"></a>

A Shopify Plus validation report should be useful to business teams, not only technical reviewers. It should identify the sample, expected result, observed result, severity, handling path, owner, and status.

| Report field     | Purpose                                                                                                                          |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Sample or record | Product, variant, company, customer, order, page, redirect, market, metafield, metaobject, or integration record being reviewed. |
| Expected result  | What the target Shopify Plus result should show or support.                                                                      |
| Observed result  | What appears in the target environment.                                                                                          |
| Severity         | Launch blocker, important correction, minor cleanup, accepted limitation, or deferred setup.                                     |
| Handling path    | Migration correction, Add-on, Custom Service, Shopify Plus setup, app setup, integration work, manual cleanup, or exclusion.     |
| Owner            | Merchant, Next-Cart, Shopify-side implementation team, app partner, integration partner, SEO team, or operations team.           |
| Status           | Open, corrected, accepted, deferred, or excluded.                                                                                |

Enterprise validation should not rely on one approver. B2B, merchandising, localization, finance, fulfillment, support, SEO, and IT may each need to approve the records that affect their work.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopify Plus validation should prove enterprise readiness, not only data transfer completeness. The review must connect products, variants, B2B companies, customers, orders, Markets, localization, redirects, metafields, metaobjects, apps, integrations, fulfillment, finance, and later migration activity to the way the business will operate after launch.

A Shopify Plus migration should be approved when representative samples make operational sense, custom and external-system dependencies are classified, live Shopify Plus setup is separated from migrated history, and each launch-critical team can validate the result it owns.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**Is Shopify Plus validation different from regular Shopify validation?**

Yes. Shopify Plus validation often includes organization structure, expansion stores, B2B companies, Markets, integrations, custom data, permissions, and enterprise launch ownership. Regular Shopify validation may focus more heavily on storefront catalog, customers, orders, redirects, and apps.

**What Shopify Plus records should be sampled during validation?**

Use representative products, variant-heavy products, B2B companies or buyers, market-specific content, customers with order history, exception orders, high-value redirects, metafields, metaobjects, integration-owned records, and app-dependent workflows.

**Should B2B companies be validated separately from customer profiles?**

Yes. Customer profiles and B2B company structures are not the same validation area. Companies, buyers, locations, catalogs, payment terms, pricing, and personalized content expectations should be reviewed separately when they are part of the Shopify Plus launch model.

**Does migrated order history prove live Shopify Plus checkout is ready?**

No. Historical order migration helps preserve support and financial context, but live checkout, payment, tax, duties, fulfillment, shipping, notifications, apps, and permissions must be configured and tested directly in Shopify Plus.

**How should custom fields be validated in Shopify Plus?**

Custom fields should be reviewed by source, target destination, business purpose, owner, and usage. Some may become metafields or metaobjects, some may require Add-ons, and unsupported or externally owned data may require Custom Service, app import, integration work, or intentional exclusion.
