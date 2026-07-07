# ShopWired Validation Priorities

ShopWired migration validation should prove more than record presence. A product can appear in the admin area while still failing the selling model if its variations, choices, extras, bundles, stock behavior, product images, category placement, VAT handling, delivery assumptions, or storefront discovery path no longer work as customers expect.

The strongest validation approach treats ShopWired as a hosted commerce environment with configurable product structures, customer and trade account behavior, checkout settings, apps, API-connected workflows, and content/SEO dependencies. Count checks are useful, but they are only the starting point. The real question is whether the migrated store can be used by customers, support teams, fulfillment teams, finance users, and marketing teams without losing the commercial meaning of the original store.

### What ShopWired Validation Should Prove <a href="#what-shopwired-validation-should-prove" id="what-shopwired-validation-should-prove"></a>

Validation should start with a proof model. A proof model prevents the review from becoming a loose checklist where every record is counted but the important behavior is missed. ShopWired stores often depend on product options, variation attributes, delivery rules, VAT treatment, customer identity, trade pricing, custom fields, apps, and external systems. These areas should be validated through representative samples, not only by reviewing totals.

| Validation question                                              | Why it matters in ShopWired                                                                                                                                | Evidence to collect                                                                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Can customers select and buy the intended product configuration? | Variations, choices, extras, and bundles may carry price, stock, image, delivery, tax, personalization, or fulfillment meaning.                            | Storefront screenshots, admin product settings, selected-option checkout tests, and sample product notes.               |
| Are products discoverable through the expected paths?            | Categories, brands, filters, search, menus, featured areas, and SEO paths shape how customers reach products.                                              | Category/brand samples, search terms, menu checks, redirect checks, and landing-page review.                            |
| Do customers and trade records retain useful identity?           | ShopWired customer records are email-centered, while trade customers and customer fields can affect pricing, account use, and B2B workflows.               | Customer samples, address checks, order links, group/trade evidence, and external reference notes.                      |
| Is order history readable for operations?                        | Historical orders need enough context for customer service, fulfillment, finance, refunds, and management review.                                          | Varied order samples covering statuses, payment labels, delivery labels, tax, discounts, notes, refunds, and B2B cases. |
| Is live checkout actually ready?                                 | Migrated order history does not configure payment gateways, delivery rates, tax settings, trade behavior, or checkout apps.                                | Target checkout test orders, payment tests, delivery-rate tests, VAT/tax checks, and customer-type tests.               |
| Are apps and integrations accounted for?                         | App-owned data, webhooks, external IDs, inventory tools, accounting, marketplace feeds, CRM, and fulfillment systems may not be standard migration fields. | Integration inventory, owner decisions, mapping notes, and post-migration connection tests.                             |
| Are content and SEO paths protected?                             | Products may migrate while CMS Pages, Blog Posts, menus, redirects, metadata, and theme-controlled areas remain incomplete.                                | Priority URL list, redirect samples, metadata review, content-page samples, and theme display checks.                   |

A validation pass should mean the target store is usable in the areas that matter to the merchant. It should not mean every possible limitation has disappeared. Some items may be accepted limitations, manual cleanup tasks, app setup tasks, or Custom Service items. The important point is that each exception is identified, owned, and resolved or accepted intentionally.

### Validate Products as Sellable Records <a href="#validate-products-as-sellable-records" id="validate-products-as-sellable-records"></a>

Product validation should prove that products remain sellable, not merely visible. A migrated ShopWired product should preserve enough business meaning for a shopper to understand the item, choose the right option, see the right price or availability, and proceed through the intended buying path.

A strong product validation set should include simple products and complex products. The sample should not only include clean records. It should include products most likely to reveal migration risk: items with multiple images, stock-sensitive variants, assigned brands, multiple category placements, product descriptions with formatting, delivery assumptions, VAT-sensitive pricing, SEO fields, and products that depend on special selling behavior.

| Product sample                           | What to validate                                                                                  | Pass condition                                                                              |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Simple retail product                    | Name, SKU, price, description, category, brand, image, stock, status, and SEO fields.             | The product is recognizable, correctly organized, and ready for ordinary storefront review. |
| Product with several images              | Main image, gallery order, image quality, and image relationship to product selection.            | Images support the product presentation and do not create customer confusion.               |
| Product assigned to multiple categories  | Category placement, breadcrumbs, menu reachability, and product visibility in each relevant area. | Customers can find the product through expected browsing paths.                             |
| Product with delivery or tax sensitivity | Delivery setting, weight, VAT/tax treatment, and checkout impact where relevant.                  | The product does not pass validation until the live target setup is separately tested.      |
| Product with external reference          | SKU, GTIN, MPN, supplier code, ERP reference, marketplace field, or custom identifier.            | External references are migrated, mapped, excluded, or escalated intentionally.             |

Product validation should be done in both the admin and storefront. Admin review proves the record exists and the main fields are understandable. Storefront review proves the result is customer-facing, selectable, and commercially usable.

### Validate Variations, Choices, Extras, and Product-Specific Buying Logic <a href="#validate-variations-choices-extras-and-product-specific-buying-logic" id="validate-variations-choices-extras-and-product-specific-buying-logic"></a>

ShopWired product structure deserves a separate validation track because product choices can change the buying experience. Product variations, choices, extras, bundles, personalization fields, and digital-product behavior are not interchangeable. A source product may use options that change price, stock, image, weight, VAT, delivery, fulfillment, or customer input. If those meanings are flattened into descriptions, the product may look complete while failing as a sellable item.

| Product-choice area                     | Validation focus                                                                                                                        | What a failure looks like                                                                            |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Variations                              | Option names, option values, generated combinations, published status, SKU, stock, price, image, weight, GTIN, MPN, and VAT attributes. | Customers can select options, but the selected result has wrong price, stock, image, or SKU meaning. |
| Choices                                 | Shopper-facing choice behavior where the selection does not behave like a full variation.                                               | The choice appears as text but no longer supports the intended selection workflow.                   |
| Extras                                  | Optional add-ons, upgrades, charges, or accessory-style selections.                                                                     | The add-on is missing, free when it should not be, or disconnected from the order context.           |
| Personalization                         | Text input, file upload, engraving, made-to-order notes, or custom customer instructions.                                               | The customer cannot provide the required information at purchase time.                               |
| Bundles and kits                        | Grouped buying logic, included items, pricing assumptions, and stock implications.                                                      | The product displays, but the bundle logic is incomplete or operationally misleading.                |
| Digital or special fulfillment products | Delivery, access, download, or fulfillment expectations.                                                                                | Historical product data exists, but fulfillment behavior is not confirmed.                           |

A product-choice validation pass requires sample products that represent real complexity. If only simple products are reviewed, the validation set is not strong enough for a store that sells configurable products.

### Validate Categories, Brands, Search, Filters, and Storefront Discovery <a href="#validate-categories-brands-search-filters-and-storefront-discovery" id="validate-categories-brands-search-filters-and-storefront-discovery"></a>

A ShopWired migration can preserve products but still weaken how customers find them. Discovery validation should check the storefront paths that drive buying behavior: categories, subcategories, brands, filters, menus, search, featured products, landing pages, and priority product groups.

Discovery validation should not assume that category records alone recreate the customer journey. A store may rely on brand-led navigation, curated menus, filter-heavy product groups, SEO landing pages, or homepage modules. Those areas need validation because they determine whether migrated products are visible in the right customer context.

| Discovery area           | Review action                                                                | Pass condition                                                                  |
| ------------------------ | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Top-level categories     | Open the category page and review representative product placement.          | The category supports the expected browsing path.                               |
| Deep subcategories       | Test products that sit several levels down.                                  | Products are reachable without broken hierarchy or missing navigation.          |
| Brands                   | Review brand pages and brand assignments for priority products.              | Brand-led discovery remains useful.                                             |
| Search                   | Test common customer search terms, SKU searches, and product-name fragments. | Search returns relevant products for realistic customer behavior.               |
| Filters                  | Review filter-heavy product groups and specification-led browsing.           | Filters narrow products in a way that supports purchase decisions.              |
| Menus and featured areas | Check curated navigation, homepage areas, and promotional product sections.  | Important products are not technically present but commercially hidden.         |
| SEO landing paths        | Check high-value category, brand, product, and content URLs.                 | Priority traffic paths land on useful target destinations or planned redirects. |

Discovery should be validated after product data is reviewed. Product data can be correct in isolation while still failing commercial use if category, brand, search, filter, menu, or SEO context is incomplete.

### Validate Customers, Customer Groups, Trade Records, and Account Meaning <a href="#validate-customers-customer-groups-trade-records-and-account-meaning" id="validate-customers-customer-groups-trade-records-and-account-meaning"></a>

Customer validation should prove that migrated customers remain useful for support, marketing, account review, and B2B operations. In ShopWired, customer identity and order relationships require careful review because customer records, email addresses, addresses, order links, customer types, trade accounts, and custom fields can affect how teams interpret the result.

The validation sample should include ordinary customers and edge cases. Stores with B2B or trade behavior should not validate customers only as retail accounts. Trade customers, approved customers, quote-related accounts, customer groups, special pricing references, external IDs, account terms, tax behavior, and payment/delivery restrictions may require target configuration, app review, or Custom Service scope.

| Customer sample                   | What to check                                                                               | What a pass should prove                                                                     |
| --------------------------------- | ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Standard registered customer      | Name, email, account data, addresses, and linked order history.                             | The customer remains identifiable and useful for support.                                    |
| Guest buyer                       | Order relationship and buyer identity without assuming full account behavior.               | Guest history is understandable and not misclassified.                                       |
| Customer with multiple addresses  | Billing and delivery address handling.                                                      | Address relationships remain interpretable.                                                  |
| Customer group member             | Group label, segmentation logic, pricing expectation, and target handling decision.         | Segmentation is preserved, configured, or intentionally separated from migration scope.      |
| Trade customer                    | Account status, trade pricing expectation, payment terms, order behavior, and restrictions. | Trade behavior is not mistaken for ordinary customer migration.                              |
| Customer with custom fields       | Field labels, business meaning, display/use location, and handling path.                    | Custom data remains usable or is escalated properly.                                         |
| Customer with external references | ERP, CRM, POS, marketplace, accounting, or fulfillment identifiers.                         | External references are mapped, excluded, or handled through Custom Service where necessary. |

Customer validation should also include permissions and practical admin use. Staff should be able to find customers, understand order history, and identify important account context without relying on the old platform for ordinary lookup.

### Validate Historical Orders, Refunds, Quotes, and Operational Context <a href="#validate-historical-orders-refunds-quotes-and-operational-context" id="validate-historical-orders-refunds-quotes-and-operational-context"></a>

Order validation should focus on operational readability. The goal is not to prove that old checkout behavior has been recreated. The goal is to prove that historical order records can support customer service, fulfillment, finance, management review, returns, refunds, and post-migration questions.

A useful order sample includes normal and exception records. Clean paid-and-fulfilled orders are not enough. The sample should include unpaid, canceled, refunded, partially fulfilled, discounted, tax-sensitive, B2B, quote-related, manually adjusted, externally referenced, and note-heavy orders where those records exist.

| Order type                           | Why it matters                      | Pass condition                                                                            |
| ------------------------------------ | ----------------------------------- | ----------------------------------------------------------------------------------------- |
| Paid and fulfilled order             | Baseline order-history readability. | Products, totals, customer, payment label, delivery label, and status are understandable. |
| Unpaid, pending, or canceled order   | Exception state handling.           | Staff can tell what happened without misreading the record.                               |
| Refunded or partially refunded order | Finance and support continuity.     | Refund context remains visible enough for post-migration review.                          |
| Discounted or voucher order          | Promotion and total interpretation. | Discounts and totals remain explainable.                                                  |
| B2B or trade order                   | Account-based selling context.      | Trade customer and pricing context is readable or intentionally separated.                |
| Quote-related order                  | Quote-to-order relationship.        | The relationship is preserved, documented, rebuilt, or accepted as out of scope.          |
| Order with external IDs              | Integration continuity.             | External references remain traceable or have a documented handling path.                  |

Historical order validation should involve the people who will use the records after launch. Customer service, finance, fulfillment, and operations may notice different problems. A record can look acceptable to a migration reviewer while still being unclear to the team that relies on it every day.

### Validate Checkout, Delivery, Payment, Tax, and Trade Boundaries <a href="#validate-checkout-delivery-payment-tax-and-trade-boundaries" id="validate-checkout-delivery-payment-tax-and-trade-boundaries"></a>

A ShopWired validation pass must separate migrated history from live target configuration. Historical order records may show payment labels, delivery labels, tax values, voucher codes, and customer context. That does not prove that new orders can be accepted through the target checkout.

Live checkout readiness should be tested separately. Payment gateways, delivery zones, delivery rates, collection options, VAT/tax settings, trade customer behavior, customer-group pricing, restricted products, quote workflows, apps, and custom checkout fields all need target-side confirmation where relevant.

| Boundary               | Historical validation                                        | Live target validation                                                                                 |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| Payment                | Past payment labels and transaction context remain readable. | Configured payment methods accept realistic test orders.                                               |
| Delivery               | Past delivery method labels remain understandable.           | Delivery zones, rates, inclusions, exclusions, and collection rules work for new orders.               |
| Tax/VAT                | Historical tax values remain readable.                       | VAT or sales tax behavior calculates according to target settings.                                     |
| Discounts and vouchers | Past discounts remain explainable.                           | New voucher or offer behavior works in the target checkout.                                            |
| Trade customers        | Old B2B order context remains interpretable.                 | Trade pricing, visibility, account terms, payment rules, and delivery rules are configured and tested. |
| Custom checkout fields | Old field data is classified and reviewed.                   | Required checkout fields are rebuilt, app-supported, excluded, or handled as custom scope.             |

This distinction prevents a misleading acceptance decision. A migration can preserve historical checkout context while the live target store still requires setup before launch.

### Validate Apps, Custom Fields, API Connections, and External Systems <a href="#validate-apps-custom-fields-api-connections-and-external-systems" id="validate-apps-custom-fields-api-connections-and-external-systems"></a>

ShopWired validation should identify data and workflows owned by apps, custom fields, API connections, webhooks, feeds, external inventory systems, accounting platforms, CRM systems, POS systems, fulfillment tools, email services, marketplace channels, or reporting systems. These items may influence the target store even when they are not ordinary migration entities.

The validation question is not simply whether an integration is connected. It is whether the data or workflow that integration needs has been preserved, rebuilt, mapped, excluded, or escalated. External IDs are especially important because they may link migrated records to downstream systems.

| Connected area        | Validation focus                                                                                      | Handling path                                                                                      |
| --------------------- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Custom fields         | Field labels, values, business meaning, display location, and operational use.                        | Standard migration, Add-on handling, Custom Service review, manual rebuild, or accepted exclusion. |
| Apps                  | App-owned records, storefront behavior, checkout behavior, B2B logic, forms, feeds, or customer data. | Reinstall/configure, migrate where supported, rebuild, exclude, or escalate.                       |
| API connections       | Product, customer, order, stock, price, or status records used by external systems.                   | Reconnect credentials, map IDs, test endpoints, or document changed workflow.                      |
| Webhooks              | Triggered workflows for fulfillment, accounting, CRM, email, inventory, or reporting.                 | Recreate and test triggers after target setup.                                                     |
| Marketplace/feed data | Channel identifiers, product attributes, taxonomies, and feed-specific fields.                        | Map, rebuild, validate feed output, or exclude intentionally.                                      |
| ERP/POS/accounting    | IDs, stock, customer, order, tax, or fulfillment references.                                          | Preserve references where possible or plan post-migration reconciliation.                          |

Custom Service should be considered when the required result depends on unsupported app data, bespoke field transformation, external identifier preservation, custom migration logic, or behavior that standard platform mapping cannot represent safely.

### Validate Content, SEO, Redirects, and Theme-Dependent Areas <a href="#validate-content-seo-redirects-and-theme-dependent-areas" id="validate-content-seo-redirects-and-theme-dependent-areas"></a>

Content and SEO validation should be part of acceptance, not a late launch task. ShopWired stores may depend on product pages, category pages, brand pages, CMS Pages, Blog Posts, menus, banners, landing pages, metadata, canonical behavior, redirects, images, files, and theme-controlled sections. If those areas are not validated, a store can pass data review while still losing traffic, trust, or conversion context.

| Content or SEO area       | What to validate                                                                      | Pass condition                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Product URLs              | Priority product paths, SEO titles, descriptions, and redirects.                      | Important product traffic lands on useful target destinations.                      |
| Category and brand URLs   | High-value category and brand paths.                                                  | Discovery and SEO continuity are protected or intentionally redirected.             |
| CMS Pages                 | Policy pages, delivery pages, support pages, B2B pages, and trust content.            | Critical non-product content is migrated, rebuilt, or accepted as out of scope.     |
| Blog Posts                | Articles that drive organic traffic or customer education.                            | Priority posts are preserved, redirected, rebuilt, or intentionally excluded.       |
| Menus and landing pages   | Curated navigation and campaign pages.                                                | Customer journeys are not broken by missing presentation areas.                     |
| Metadata and redirects    | SEO fields, page titles, meta descriptions, canonical assumptions, and 301 redirects. | Search and referral paths have documented target handling.                          |
| Theme-controlled sections | Homepage modules, banners, product blocks, and custom display areas.                  | Design-dependent content is rebuilt or accepted as theme work, not silently missed. |

SEO validation should prioritize business value. Not every historical URL deserves the same attention. High-traffic, high-revenue, externally linked, campaign-driven, or support-critical paths should be sampled first.

### Validate Demo Migration and Full Migration Evidence <a href="#validate-demo-migration-and-full-migration-evidence" id="validate-demo-migration-and-full-migration-evidence"></a>

Demo Migration should be used as an evidence-building stage. It should not be treated as a preview of only simple records. The sample should include products, customers, orders, content, custom fields, trade behavior, and integration-sensitive records that represent the real migration risk.

Full Migration should then be validated against a launch-readiness checklist. If the configuration changes after Demo Migration, the validation plan should change with it. If additional data is migrated later using a continued or new migration configuration, the changed scope should be revalidated rather than assumed to inherit the earlier pass.

| Evidence stage                 | What to prove                                                             | Decision value                                                                           |
| ------------------------------ | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Demo Migration                 | Representative records migrate with enough meaning to expose risks early. | Confirms whether scope, mapping, Add-ons, or Custom Service decisions need adjustment.   |
| Pre-Full Migration review      | Source cleanup, target setup, mapping, and custom requirements are ready. | Reduces avoidable migration defects and late-stage scope confusion.                      |
| Full Migration validation      | Canonical target data supports launch and operations.                     | Confirms readiness for publication, customer access, and business use.                   |
| Continued migration validation | New or changed data lands correctly after the main migration.             | Prevents post-launch records from being accepted without proof.                          |
| New-configuration validation   | A different configuration produces the intended result.                   | Confirms that changed mapping, filtering, or target handling did not create new defects. |

Entity Points should be reviewed when repeated or later migration activity is part of the plan. If the same entity is migrated again under a new paid execution, Entity Points may be consumed again. That should be accounted for before approving repeated runs.

### Build a ShopWired Validation Report <a href="#build-a-shopwired-validation-report" id="build-a-shopwired-validation-report"></a>

A validation report should convert review findings into decisions. Without a report, teams often lose the distinction between migration defects, target setup tasks, app work, manual cleanup, accepted limitations, and custom requirements.

| Report field     | Purpose                                                                                                                                                                           |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sample or record | Identifies the product, variation, customer, order, category, brand, CMS Page, app record, redirect, or integration item under review.                                            |
| Expected result  | Describes the intended ShopWired outcome in business terms.                                                                                                                       |
| Observed result  | Records what the reviewer actually sees in the target store.                                                                                                                      |
| Severity         | Separates launch blockers from cleanup items, accepted limitations, and post-launch improvements.                                                                                 |
| Handling path    | Classifies the item as migration correction, Add-on adjustment, Custom Service review, ShopWired setup, app/integration work, theme work, manual cleanup, or accepted limitation. |
| Owner            | Assigns responsibility to the merchant, Next-Cart, ShopWired setup owner, app partner, integration owner, or external technical team.                                             |
| Status           | Confirms whether the item is open, corrected, deferred, accepted, or launch-ready.                                                                                                |

The validation report should be reviewed before final acceptance. A clean report is less important than a clear one. Some accepted limitations are reasonable, but unresolved ambiguity is not.

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired validation should prove that migrated data still supports the store’s commercial model. Products need to remain sellable, product-choice structures need to work from the storefront, customers and trade records need to retain useful meaning, orders need to remain operationally readable, checkout needs separate live testing, integrations need ownership decisions, and content or SEO paths need deliberate handling.

A strong validation process does not rely on counts alone. It uses representative samples, storefront checks, admin review, target setup tests, integration review, and a clear validation report. That approach gives the merchant a reliable basis for deciding whether the migration result is ready for launch or still needs correction, configuration, custom handling, or accepted-scope decisions.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be validated first in a ShopWired migration?**

Start with the records that carry the most business meaning: complex products, variations, choices, extras, bundles, trade customers, high-value orders, checkout-sensitive products, important categories, and priority SEO paths. These samples reveal more risk than simple record counts.

**Why are product variations and choices important in ShopWired validation?**

They affect the customer buying experience. A product may appear correct at a summary level while its options, stock, price, image, VAT, personalization, or bundle behavior no longer works as intended.

**Are historical orders enough to prove checkout readiness?**

No. Historical orders prove past context only. Live checkout depends on ShopWired payment methods, delivery rules, tax settings, customer-group behavior, apps, and target configuration, so it needs separate testing.

**How should trade customers be validated?**

Trade customers should be reviewed as business accounts, not only as customer records. Pricing expectations, account status, payment terms, delivery rules, quote behavior, visibility, tax handling, and custom fields should be configured, migrated, rebuilt, excluded, or escalated intentionally.

**Do Add-ons and Custom Service remove the need for validation?**

No. Add-ons and Custom Service can expand or adapt the migration scope, but the target result still needs validation. The merchant should verify that the supported configuration, custom handling, and final records meet the intended ShopWired outcome.<br>
