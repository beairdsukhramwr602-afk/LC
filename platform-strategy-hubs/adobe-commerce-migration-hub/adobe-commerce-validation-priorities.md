# Adobe Commerce Validation Priorities

Adobe Commerce validation should prove that the Target Store can operate under the intended enterprise model. A migrated store may contain the expected products, customers, orders, categories, CMS Pages, and Blog Posts, but still fail launch readiness if company users cannot reach the correct account context, shared catalog prices are exposed to the wrong buyers, scoped storefront values appear in the wrong store view, staged content conflicts with the launch calendar, or integration-sensitive identifiers are missing from operational records.

The strongest Adobe Commerce validation process combines record-level review, storefront behavior testing, Admin review, buyer-role testing, operational-owner approval, and documented exception handling. The goal is not only to confirm that data exists in Adobe Commerce. The goal is to confirm that migrated data supports the commercial rules, access controls, storefront scope, catalog behavior, and operational workflows the business expects after launch.

### Start Validation with the Target Operating Model <a href="#start-validation-with-the-target-operating-model" id="start-validation-with-the-target-operating-model"></a>

Adobe Commerce validation should begin with the target operating model, not with record counts alone. Record counts can show whether selected entities transferred, but they do not prove whether the migrated store supports B2B purchasing, catalog visibility rules, scoped storefront behavior, pricing expectations, campaign timing, or downstream operational use.

Before reviewing individual records, confirm the operating assumptions that the migrated result must support.

| Validation question                                | Why it matters                                                                                                                                                                |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Which buyer types must be supported at launch?     | B2C customers, B2B company buyers, company administrators, sales-assisted buyers, and internal users may need different validation evidence.                                  |
| Which storefront scopes are launch-critical?       | Websites, stores, and store views can affect catalog availability, localized content, pricing, URLs, and configuration behavior.                                              |
| Which catalog and pricing rules must be protected? | Shared catalogs, customer groups, negotiated prices, tier prices, and visibility rules can create business exposure if validated only through Admin counts.                   |
| Which systems depend on migrated records?          | ERP, PIM, CRM, WMS, tax, payment, search, analytics, and reporting systems may depend on IDs, references, statuses, or custom fields.                                         |
| Which records are launch-critical?                 | Priority products, company accounts, shared catalogs, URLs, orders, content, and integration-sensitive records should receive deeper review than low-risk historical records. |

This operating model should determine the validation sample. A small set of simple products and ordinary customer records is not enough for an enterprise Adobe Commerce launch when company access, restricted pricing, scoped storefronts, staged campaigns, and custom integrations affect real operations.

### Validate Company Accounts and Buyer Relationships <a href="#validate-company-accounts-and-buyer-relationships" id="validate-company-accounts-and-buyer-relationships"></a>

For Adobe Commerce B2B stores, customer validation should prove company-account behavior, not only customer record transfer. A company account can represent the buying organization, while individual customer records may represent administrators, buyers, approvers, billing contacts, or employees with different permissions. If validation stops at customer names and email addresses, it may miss the relationships that determine whether B2B buyers can actually place orders.

Representative validation should include active companies, inactive or pending companies when relevant, company administrators, ordinary company users, users tied to approval behavior, accounts connected to customer groups, and companies associated with shared catalogs. Each sample should confirm that company identity, legal or billing details, user relationships, account status, and commercial settings are coherent in the Target Store.

| Validation area                | What to prove                                                                                                                                                      | Failure signal                                                                                 |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Company identity               | Company name, status, account details, billing context, and assigned administrator are correct.                                                                    | The buyer exists as an individual customer but is no longer connected to the business account. |
| Company users                  | Users have the intended company association, role, and account access.                                                                                             | Buyers can access areas they should not see, or cannot perform expected purchasing actions.    |
| Company hierarchy or divisions | Parent-child, department, or multi-division structures are represented according to the target plan.                                                               | Related companies are flattened into unrelated accounts or assigned inconsistent settings.     |
| Commercial permissions         | Quote permission, purchase order permission, payment methods, shipping methods, credit handling, or approval behavior matches the approved scope where applicable. | Buyers can bypass intended controls or cannot use expected purchasing workflows.               |

The strongest proof comes from testing real representative buyer profiles. Sign in as the intended buyer type, review the account area, browse the assigned catalog, check product visibility, review cart and checkout behavior, and confirm whether the role can complete the actions expected after launch.

### Validate Shared Catalog Visibility and Pricing Access <a href="#validate-shared-catalog-visibility-and-pricing-access" id="validate-shared-catalog-visibility-and-pricing-access"></a>

Shared catalog validation should be performed from the storefront and buyer perspective. Admin assignments are useful, but they do not prove whether the right buyer sees the right products and prices after signing in. Adobe Commerce validation should confirm both positive access and negative access: the intended buyer sees the right catalog, and the wrong buyer does not see restricted products or negotiated prices.

At minimum, test several buyer contexts.

| Buyer context                                              | Required proof                                                                                                    | Why it matters                                                                           |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Company assigned to a custom shared catalog                | The buyer sees the intended products, prices, search results, category navigation, and checkout options.          | Confirms migrated customer relationships and shared catalog configuration work together. |
| Company assigned to a different catalog or price structure | The buyer sees only the products and prices intended for that segment.                                            | Detects price leakage, overexposure, and incorrect customer-group or catalog assignment. |
| General customer or guest context                          | Restricted products and B2B prices are hidden when they should not be public.                                     | Protects negotiated pricing and private product availability.                            |
| Internal sales-assisted or account-manager context         | Sales-assisted workflows can support expected quote, order, or customer-service behavior where included in scope. | Confirms the store supports operational use, not only storefront browsing.               |

Shared catalog samples should include products included in multiple catalogs, products excluded from specific catalogs, products with custom prices, tiered-pricing assumptions, discontinued items, and products with special visibility rules. A simple product sample is not enough when pricing and access rules are commercially sensitive.

### Validate Product Structure and Catalog Behavior <a href="#validate-product-structure-and-catalog-behavior" id="validate-product-structure-and-catalog-behavior"></a>

Adobe Commerce product validation should prove that catalog relationships work as intended. A product can look correct in an Admin grid while failing on the storefront because variants, attributes, attribute sets, category assignments, bundle options, downloadable files, custom options, pricing rules, visibility settings, or search behavior were not interpreted correctly.

Representative validation should include the product structures that carry the most launch risk: simple products, configurable products with associated child SKUs, bundle or grouped products where used, virtual or downloadable products where used, products with custom options, products relying on important attributes, and products tied to shared catalogs or scoped storefronts.

| Product evidence              | What to confirm                                                                                               | Common failure pattern                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Configurable product          | Parent product, child SKUs, option labels, prices, inventory behavior, and storefront selection are coherent. | The parent product displays but child SKUs, options, availability, or price behavior are wrong.                 |
| Attribute set                 | Product families use the intended attribute set and required attributes are populated.                        | Products inherit incomplete, inappropriate, or inconsistent attributes after migration.                         |
| Category assignment           | Products appear in the intended navigation and merchandising structure.                                       | Products exist in Admin but disappear from storefront categories or appear in the wrong catalog area.           |
| Search and layered navigation | Searchable and filterable values support expected buyer discovery.                                            | Attributes transfer as values but do not support useful filtering, search, or merchandising behavior.           |
| Complex product options       | Bundles, grouped products, custom options, downloads, or virtual products behave as expected.                 | The product page loads, but buying logic, file access, component selection, or grouped purchase behavior fails. |

Validation should separate transferred values from target behavior. A migrated attribute value is not automatically useful in Adobe Commerce unless it is visible, searchable, filterable, comparable, used in pricing or promotions, required by integrations, or otherwise configured according to the target operating model.

### Validate Website, Store, and Store-View Scope <a href="#validate-website-store-and-store-view-scope" id="validate-website-store-and-store-view-scope"></a>

Adobe Commerce scope validation is critical for multi-brand, multi-region, multilingual, or multi-currency operations. Scope affects how data, content, configuration, URLs, and buyer experience are interpreted in the Target Store. A record can be correct at the global level while still being wrong for a specific website, store, or store view.

The validation sample should include every active launch-critical storefront scope. Review product names, descriptions, category names, CMS Pages, Blog Posts, URL keys, meta data, currency context, tax context, customer assignment, catalog visibility, and localized content where relevant.

| Scope level | Validation priority                                                                 | Practical proof                                                                                     |
| ----------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Website     | Confirm regional, brand, currency, customer, catalog, or business-model separation. | Buyers enter the intended website and see the right commercial context.                             |
| Store       | Confirm catalog structure and navigation expectations.                              | Category trees, menus, product assignments, and merchandising structure align with the target plan. |
| Store view  | Confirm localized display values, language-specific content, URLs, and SEO fields.  | Product copy, category labels, CMS Pages, URL keys, and meta data match the intended locale.        |

Scope validation should include negative tests. A localized page should not appear under the wrong language context. A product assigned to one website should not become available in another website unless that is intentional. A shared catalog intended for one business segment should not become visible through a broader storefront context.

### Validate Inventory Availability and Fulfillment Assumptions <a href="#validate-inventory-availability-and-fulfillment-assumptions" id="validate-inventory-availability-and-fulfillment-assumptions"></a>

Inventory validation should prove that buyers see accurate availability and that internal teams can trust stock behavior after launch. Adobe Commerce inventory planning may involve sources, stocks, sales-channel assignments, salable quantity, backorder behavior, and reservations. These concepts can affect storefront availability and order acceptance.

Validation should include products with simple stock behavior, products assigned to multiple sources where used, out-of-stock products, backorder-sensitive products, configurable products with child SKU availability differences, and items fulfilled from different warehouses or regions.

| Inventory check                            | What to verify                                                                                  | Why it matters                                                                 |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Source assignment                          | Products are assigned to the intended fulfillment sources where source-based inventory is used. | Prevents orders from routing against the wrong operational inventory model.    |
| Stock and sales channel                    | Stocks support the intended website or sales-channel context.                                   | Confirms that storefront availability reflects the correct commercial channel. |
| Salable quantity                           | Storefront availability aligns with the intended sellable stock behavior.                       | Reduces overselling, false out-of-stock behavior, and checkout disruption.     |
| Configurable product availability          | Parent product availability reflects child SKU availability correctly.                          | Prevents variant selection issues and misleading product availability.         |
| Backorder or special availability behavior | Backorder-sensitive products follow the target launch policy.                                   | Avoids unexpected order acceptance or blocked sales after launch.              |

If inventory is controlled by an external system, validation should identify what was migrated, what is managed after launch by the external system, and what must be manually configured in Adobe Commerce. Inventory results should not be accepted only because quantities exist in Admin.

### Validate URLs, SEO Continuity, and Priority Content Paths <a href="#validate-urls-seo-continuity-and-priority-content-paths" id="validate-urls-seo-continuity-and-priority-content-paths"></a>

Adobe Commerce validation should include URL and SEO continuity because enterprise stores often carry high-value product pages, category pages, CMS Pages, Blog Posts, campaign landing pages, localized paths, and redirected legacy URLs. A successful migration should protect the paths that customers, search engines, campaigns, partners, and internal teams rely on.

Validation should use a priority URL list rather than checking random pages. Include high-traffic products, high-revenue categories, evergreen CMS Pages, campaign pages, localized landing pages, Blog Posts, and pages with important backlink or search visibility.

| URL group                   | Required validation                                                                 | Failure to watch for                                                                      |
| --------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Product URLs                | Product pages resolve to the correct item and storefront scope.                     | Product URL opens a duplicate page, wrong store view, irrelevant product, or 404.         |
| Category URLs               | Category routes preserve navigation value and assigned products.                    | Category exists but URL, title, or product listing does not match the intended structure. |
| CMS Pages and landing pages | Important informational, policy, brand, and campaign pages resolve correctly.       | Page content exists but high-value legacy URL is lost or mapped to the wrong scope.       |
| Blog Posts                  | Migrated blog content resolves under the intended content structure where included. | Blog content exists but URLs, categories, metadata, or internal links are broken.         |
| Redirects                   | Old URLs redirect to the correct new destination when required.                     | Redirect chains, missing 301s, incorrect destinations, or language-scope errors.          |

URL validation should happen before launch and again after final cutover when the source store continues changing before go-live. If new source-store activity or target configuration changes affect URLs, the selected Additional Migration Options should be planned and validated as part of launch readiness.

### Validate Content Staging and Campaign-Sensitive Records <a href="#validate-content-staging-and-campaign-sensitive-records" id="validate-content-staging-and-campaign-sensitive-records"></a>

Adobe Commerce stores that use Content Staging need launch-aware validation. Scheduled updates can affect products, categories, price rules, CMS Pages, CMS blocks, and campaign content. A campaign-sensitive migration can look correct at the time of review but fail when a scheduled update becomes active.

Validation should identify which records are live, which are scheduled, which are part of upcoming campaigns, and which should not become active at launch. Review scheduled product changes, category changes, promotional rules, CMS Pages, and CMS blocks with the marketing or merchandising owner who understands the campaign calendar.

| Staging area         | Validation question                                                  | Launch concern                                                                 |
| -------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Product updates      | Are scheduled product changes aligned with the migration timeline?   | A product may launch with outdated price, visibility, copy, or availability.   |
| Category updates     | Are navigation and campaign category changes scheduled correctly?    | Seasonal or campaign categories may appear too early, too late, or not at all. |
| Price rules          | Are promotion windows and eligibility rules correct?                 | Discounts may activate incorrectly or miss the intended launch period.         |
| CMS Pages and blocks | Are campaign pages and content blocks active in the intended window? | Landing pages, banners, or promotional content may be missing during launch.   |

If staging data is recreated manually or configured after migration, the validation record should distinguish between migrated data, target-side configuration, and post-migration merchandising setup. This prevents launch decisions from treating unfinished campaign work as a migration defect or, conversely, treating a real migration gap as a future merchandising task.

### Validate Orders, Customer History, and Commercial Interpretation <a href="#validate-orders-customer-history-and-commercial-interpretation" id="validate-orders-customer-history-and-commercial-interpretation"></a>

Historical order validation should prove that order history remains coherent for customer service, accounting, B2B account management, reporting, and operational review. Adobe Commerce may not reproduce every source workflow exactly, especially when old behavior came from extensions, ERP systems, custom checkout rules, unsupported quote flows, or external approval systems.

Order validation should include completed orders, canceled orders, refunded orders, orders with discounts, orders with tax, orders with shipping rules, B2B orders, quote-originated orders where included, purchase-order-related orders where included, and orders tied to company accounts.

The validation goal is coherence, not artificial reactivation of historical orders. Review whether order details remain understandable, whether customer and company context is preserved where applicable, whether product references and totals make sense, and whether internal teams can trace historical activity after launch.

For B2B stores, order history should be reviewed under the company context. Confirm whether the right users can see the right historical orders, whether account managers can interpret order history, and whether finance or support teams can trace customer, company, product, price, tax, and fulfillment context.

### Validate Add-ons, Custom Service Scope, and External Dependencies <a href="#validate-add-ons-custom-service-scope-and-external-dependencies" id="validate-add-ons-custom-service-scope-and-external-dependencies"></a>

Adobe Commerce validation should confirm the agreed service scope. Not every source behavior belongs to standard migration coverage, and not every missing target behavior is a migration defect. Enterprise projects often include extension-owned data, custom attributes, external identifiers, B2B logic, ERP references, PIM relationships, contract pricing, tax rules, warehouse identifiers, loyalty data, marketplace data, or other operational dependencies.

Add-ons may be used for filtering, mapping, or data configuration where the required adjustment fits the service scope. Custom Service should be reviewed when the migration depends on unsupported source behavior, custom logic, Custom Platform handling, extension-owned structures, outside-system identifiers, or bespoke target-side interpretation.

A useful validation record should classify each exception clearly.

| Exception type                       | Validation decision                                                     | Required documentation                                                             |
| ------------------------------------ | ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Included in standard migration scope | Confirm the record moved and behaves as expected.                       | Sample IDs, before-and-after evidence, and owner approval.                         |
| Covered by Add-ons                   | Confirm the filtered, mapped, or configured result matches the request. | Add-on scope, tested examples, and acceptance criteria.                            |
| Requires Custom Service              | Confirm bespoke handling was scoped and reviewed.                       | Custom requirement summary, target behavior, tested examples, and approval status. |
| Out of scope or deferred             | Confirm the customer understands the limitation and launch impact.      | Exclusion note, workaround, owner acceptance, and timing decision.                 |

This classification should be maintained before launch so unresolved exceptions do not become vague post-launch issues. It also helps determine whether the next action is configuration, Add-on adjustment, Custom Service review, manual setup, or launch-scope acceptance.

### Build a Validation Evidence Set Before Launch <a href="#build-a-validation-evidence-set-before-launch" id="build-a-validation-evidence-set-before-launch"></a>

A launch decision should be based on evidence. For Adobe Commerce, the evidence set should include representative examples from each major operating area: B2C customers if applicable, company accounts, company users, shared catalogs, product families, complex products, scoped storefronts, inventory-sensitive items, URLs, CMS Pages, Blog Posts, promotions, orders, and integration-dependent records.

A practical evidence set should include:

* source and target record IDs for every sample;
* screenshots or exports showing before-and-after values;
* storefront tests from the buyer perspective;
* Admin checks from the operations perspective;
* owner signoff for catalog, B2B, marketing, SEO, operations, IT, and finance areas where relevant;
* a list of exceptions, deferred items, accepted limitations, and launch-blocking issues;
* confirmation of whether Additional Migration Options are needed before launch because source-store activity or target configuration changed after the main migration.

Validation evidence should be stored in a format the launch team can review. A result is safer to approve when stakeholders can see the sample record, the tested behavior, the owner decision, and the remaining exception status.

### Decide Whether the Adobe Commerce Result Is Launch-Ready <a href="#decide-whether-the-adobe-commerce-result-is-launch-ready" id="decide-whether-the-adobe-commerce-result-is-launch-ready"></a>

Adobe Commerce launch readiness should depend on whether the Target Store can support the intended operating model with acceptable risk. Small cosmetic issues may be deferred if they do not affect buying, account access, pricing, fulfillment, SEO continuity, or reporting. Structural issues should not be treated as minor because they can affect business users, customers, integrations, or revenue after launch.

Use a launch-readiness decision table.

| Result status                            | Meaning                                                                                                                                   | Launch decision                                                                         |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Launch-ready                             | Core catalog, B2B, pricing, scope, content, inventory, URL, order, and operational samples pass.                                          | Proceed when final business owners approve the result.                                  |
| Launch-ready with accepted exceptions    | Known gaps are documented, non-blocking, and accepted by the responsible owners.                                                          | Proceed only if the exceptions have owners, timing, and workaround notes.               |
| Needs correction before launch           | Issues affect buying, pricing visibility, company access, checkout, inventory, priority URLs, major content, or operational dependencies. | Resolve before launch or revise the launch scope.                                       |
| Requires Custom Service or external work | The issue depends on unsupported logic, custom modules, external systems, or bespoke transformation.                                      | Review Custom Service, integration work, or target-side implementation before approval. |

The customer remains responsible for final result verification. Next-Cart can support migration execution, service handling, Add-ons, Custom Service, or Expert Handle depending on the selected service scope, but the launch decision should be based on the customer’s review of the migrated business result.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Adobe Commerce validation should prove that the Target Store can operate as intended, not only that records transferred. For simple stores, that may mean confirming catalog, customer, order, content, URL, and storefront completeness. For enterprise or B2B stores, the standard is higher: company users, shared catalog access, pricing visibility, scoped storefront behavior, staged campaigns, inventory availability, order history, integrations, and exceptions must all be tested against the target operating plan.

A strong validation process uses representative records, buyer-role testing, Admin review, storefront checks, documented evidence, and owner signoff before launch. When validation exposes unsupported logic, missing relationships, incorrect visibility, or configuration-dependent behavior, those findings should be resolved through the right service path before Full Migration is treated as launch-ready.

### FAQs <a href="#faqs" id="faqs"></a>

#### Common questions <a href="#common-questions" id="common-questions"></a>

**Is record count matching enough to validate an Adobe Commerce migration?**

No. Record counts are useful, but Adobe Commerce validation also needs behavior checks. Company access, shared catalog visibility, storefront scope, product relationships, inventory availability, URL continuity, staged content, and order history should be reviewed with representative records.

**What should be validated first for a B2B Adobe Commerce store?**

Start with company accounts, company administrators, company users, shared catalog assignment, pricing visibility, quote or purchase-order permissions where included in scope, and buyer login behavior. These areas determine whether business buyers can actually use the Target Store after migration.

**How should shared catalog validation be handled?**

Test at least one company assigned to each important shared catalog or pricing model. Confirm that each buyer sees the intended products, prices, search results, category navigation, and checkout options, and confirm that restricted products or prices are not visible to the wrong audience.

**Why is scope validation important in Adobe Commerce?**

Adobe Commerce uses websites, stores, and store views. Content, configuration, product values, URLs, language values, and storefront behavior may depend on scope. Multi-brand, multi-region, multilingual, or multi-currency stores should validate each relevant scope before launch.

**When should Additional Migration Options be considered during Adobe Commerce validation?**

Additional Migration Options should be considered when source-store activity continues after the main migration, when selected records need to be brought forward before launch, or when the target result needs another controlled migration action after configuration or scope changes. The selected option should be validated before launch approval.

**Who is responsible for final Adobe Commerce validation?**

The customer is responsible for final result verification because only the customer can confirm whether company access, pricing visibility, storefront scope, order history, integrations, content, and operational workflows are correct for the business. Next-Cart can support the process according to the selected service scope.
