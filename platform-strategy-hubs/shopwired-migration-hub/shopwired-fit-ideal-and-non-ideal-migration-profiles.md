# ShopWired Fit: Ideal and Non-Ideal Migration Profiles

Choosing ShopWired as a migration target should be based on how well the platform fits the merchant’s operating model, not only on whether products, customers, and orders can be transferred. A good fit exists when the business wants a hosted commerce platform and its catalog, customer, order, checkout, B2B, content, and integration requirements can be represented through ShopWired’s supported structures.

A weaker fit does not always mean ShopWired is the wrong platform. It may mean the project needs better preparation, target configuration, Add-ons, Managed Service support, or Custom Service review. The fit decision should identify where the source store is ordinary, where the migration is configuration-heavy, and where business rules depend on custom code, apps, external systems, or product logic that cannot be assumed to transfer directly.

The most useful ShopWired fit assessment focuses on operating evidence. What product choices do customers make? How are categories, brands, filters, and search used? What makes a customer retail, trade, registered, guest, or newsletter-only? Which order details matter for support or accounting? Which checkout rules are historical labels, and which must work live after launch? Which apps or integrations own records that ordinary migration may not include?

### ShopWired Fit Decision Framework <a href="#shopwired-fit-decision-framework" id="shopwired-fit-decision-framework"></a>

ShopWired is often the right direction when the merchant wants managed platform operations with practical commerce depth. It is usually less suitable when the business requires self-hosted database control, unrestricted backend customization, or highly bespoke checkout and product logic that must remain exactly as built in the source system.

| Fit dimension     | Strong ShopWired signal                                                                                                  | Caution signal                                                                                                                  |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| Operating model   | Merchant wants hosted platform management with configurable commerce features.                                           | Merchant expects direct control of server, database, and backend application code.                                              |
| Catalog structure | Product options can be expressed through variations, choices, extras, bundles, brands, categories, and supported fields. | Products rely on advanced configurators, conditional logic, external rules engines, or unusual option inheritance.              |
| B2B/trade model   | Trade customers, pricing bands, quotes, and account-based behavior can be clearly described and configured or reviewed.  | Pricing, catalog access, approvals, terms, and availability are controlled by ERP logic or bespoke code.                        |
| Checkout model    | Payment, delivery, VAT/tax, offers, and checkout settings can be rebuilt in ShopWired.                                   | Checkout flow depends on custom scripts, source-only gateways, or highly conditional fulfilment rules.                          |
| Content and SEO   | Important pages, URLs, metadata, redirects, images, menus, and landing paths can be planned before launch.               | SEO value depends on app-rendered pages, custom templates, or uncatalogued legacy landing pages.                                |
| Integration model | Apps, API connections, webhooks, and external identifiers are known and can be reconnected or scoped.                    | Operational records are scattered across apps, marketplaces, fulfilment tools, and custom middleware without ownership clarity. |

### Strong-Fit Profiles <a href="#strong-fit-profiles" id="strong-fit-profiles"></a>

ShopWired tends to be strongest for merchants that need a hosted commerce system with enough structure to support real selling operations. The following profiles usually indicate a good fit when the source data is clean enough and the merchant accepts target-side configuration work.

#### Hosted-growth retailers <a href="#hosted-growth-retailers" id="hosted-growth-retailers"></a>

A hosted-growth retailer wants to move away from a simpler platform, an ageing cart, or a self-hosted environment while keeping practical control over catalog, orders, customers, content, checkout, and integrations. ShopWired can fit this profile because it offers a managed environment with operational commerce features rather than requiring the merchant to maintain the full technical stack.

The migration focus should be on preserving business meaning rather than preserving old implementation detail. Product data, customer records, order history, CMS Pages, categories, brands, and SEO assets should be moved into structures that make the target store usable. Delivery, payment, tax, theme, and app setup should be planned as target configuration.

#### Product-choice-driven stores <a href="#product-choice-driven-stores" id="product-choice-driven-stores"></a>

Stores with meaningful product options can be a strong ShopWired fit when the choices are clear and can be mapped properly. Source variants, modifiers, add-ons, personalization fields, bundles, or digital product behavior should be reviewed against ShopWired’s product structures before migration.

A strong fit exists when product complexity is manageable and can be represented in the target store without reducing the buying experience. A weaker fit appears when option logic changes price, stock, availability, fulfilment, image selection, tax, or customer eligibility in ways that cannot be expressed through supported structures.

| Product scenario                    | Fit outlook    | Review focus                                                                                   |
| ----------------------------------- | -------------- | ---------------------------------------------------------------------------------------------- |
| Standard size/colour options        | Usually strong | Variation structure, SKU, price, image, stock, and visibility.                                 |
| Optional add-ons or personalization | Conditional    | Whether choices, extras, text input, file upload, or app behavior fits the source meaning.     |
| Bundled or kit products             | Conditional    | Whether bundle behavior is presentational, stock-affecting, pricing-related, or app-supported. |
| Dynamic configurators               | Higher risk    | Whether custom logic or external configuration needs Custom Service review.                    |
| Trade-only product access           | Conditional    | Whether visibility, pricing, and customer eligibility can be handled in target setup.          |

#### Trade and B2B sellers with manageable rules <a href="#trade-and-b2b-sellers-with-manageable-rules" id="trade-and-b2b-sellers-with-manageable-rules"></a>

ShopWired can be suitable for trade and B2B sellers when the business can clearly define customer types, pricing expectations, quote behavior, account handling, and checkout access. A merchant with trade customers, pricing bands, individual trade pricing, or quote-related workflows may find ShopWired more appropriate than a platform aimed only at simple retail selling.

The fit depends on rule clarity. If source B2B behavior is mostly structured customer data plus configurable pricing and account rules, ShopWired may be a strong fit. If the source store depends on ERP-controlled catalogs, customer-specific availability, approval hierarchies, negotiated terms, or custom checkout flows, the platform may still be viable but the migration needs deeper discovery.

#### Stores with manageable integration needs <a href="#stores-with-manageable-integration-needs" id="stores-with-manageable-integration-needs"></a>

ShopWired can also fit merchants that depend on connected services but can identify those services clearly. Apps, APIs, webhooks, payment providers, delivery tools, tax services, accounting systems, stock sync, and marketing tools can support operations after launch when their ownership and configuration are known.

The migration should classify each connected system by role. Some connections only need to be reconfigured after launch. Some require migrated identifiers to remain traceable. Some hold records that ordinary migration does not include. Some create a Custom Service requirement.

### Conditional-Fit Profiles <a href="#conditional-fit-profiles" id="conditional-fit-profiles"></a>

Many ShopWired candidates are not purely strong or weak. They are conditional fits because the platform may work well after specific planning issues are resolved. These cases should not be rejected too quickly, but they should also not be treated as standard migrations without review.

| Conditional profile                     | Why it may still work                                                                                      | What must be resolved first                                                                                         |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Store with messy legacy product options | ShopWired may support the intended buying choices through cleaner product structures.                      | Identify which source option workarounds should be preserved, simplified, or replaced.                              |
| B2B store with mixed customer records   | Trade and customer records can be planned, but identity and pricing rules need separation.                 | Distinguish retail customers, guest buyers, registered accounts, trade customers, pricing bands, and custom fields. |
| SEO-sensitive retailer                  | ShopWired can support product, category, content, and redirect planning.                                   | Prepare priority URLs, metadata, redirects, menus, and landing pages before launch.                                 |
| Store with many apps                    | Apps may be reconnected or replaced, but their data ownership must be known.                               | Inventory app-created product, customer, order, subscription, fulfilment, and reporting data.                       |
| Multi-channel seller                    | ShopWired may support connected operations, but source channel identifiers may not be ordinary store data. | Confirm marketplace IDs, fulfilment references, accounting links, and stock-sync ownership.                         |
| Merchant simplifying operations         | ShopWired can support simplification if the merchant accepts changed workflows.                            | Decide which legacy custom behavior should not be recreated.                                                        |

A conditional fit should move forward only when the uncertain areas have owners and evidence. For example, a product option problem should have representative product samples. A B2B pricing problem should have customer and pricing examples. An integration problem should have system names, identifiers, and data ownership notes. A content problem should have URL and page samples. Without evidence, the migration may appear straightforward during setup and fail during validation.

### Weaker-Fit Profiles <a href="#weaker-fit-profiles" id="weaker-fit-profiles"></a>

ShopWired can be a weaker fit when the source store depends on behavior that conflicts with the expectations of a hosted commerce platform. These cases may still be possible with redesign, simplification, external systems, or custom work, but the merchant should understand the trade-offs before choosing the platform.

#### Stores that require self-hosted technical control <a href="#stores-that-require-self-hosted-technical-control" id="stores-that-require-self-hosted-technical-control"></a>

A store that requires database-level control, unrestricted backend code access, custom checkout application logic, or full ownership of server-side architecture may not be a natural ShopWired fit. ShopWired can support theme work, apps, APIs, webhooks, and integrations, but it remains a hosted platform.

If the merchant expects to reproduce a self-hosted system exactly, migration planning should challenge that expectation. The decision becomes whether the business is willing to translate the old model into ShopWired’s supported operating model.

#### Stores with advanced configurator logic <a href="#stores-with-advanced-configurator-logic" id="stores-with-advanced-configurator-logic"></a>

Product configurators can create fit problems when choices depend on conditional rules, formulas, dimensions, customer eligibility, real-time pricing, external stock, or custom manufacturing logic. Some source behavior may be expressible through product options, extras, bundles, or apps. Other behavior may require custom review or may belong outside the standard migration scope.

A fit decision should use real products. If the merchant cannot show the products that create the complexity, the project cannot confirm whether ShopWired will preserve the buying experience.

#### Stores with deeply customized B2B rules <a href="#stores-with-deeply-customized-b2b-rules" id="stores-with-deeply-customized-b2b-rules"></a>

B2B risk increases when the source store uses customer-specific catalogs, contract pricing, approval workflows, ERP-controlled availability, custom payment terms, multi-user account hierarchies, or custom tax and delivery rules. These requirements are not ordinary customer records.

ShopWired may still be considered, but the migration must identify what belongs to platform configuration, what belongs to apps or integrations, what must be rebuilt operationally, and what requires Custom Service review.

#### Stores whose apps own the business model <a href="#stores-whose-apps-own-the-business-model" id="stores-whose-apps-own-the-business-model"></a>

A store may appear simple in the admin while its real operations depend on apps or external systems. Examples include subscriptions, product personalization, reward logic, fulfilment routing, tax services, inventory sync, marketplace listings, accounting exports, review data, or custom reports.

If those systems own important records, ordinary migration of products, customers, orders, and content may not be enough. The merchant should not choose ShopWired until app ownership and external identifiers are documented.

### Non-Ideal Fit Signals <a href="#non-ideal-fit-signals" id="non-ideal-fit-signals"></a>

Some signs indicate that ShopWired should be reconsidered or scoped very carefully before migration. These are not automatic rejection rules, but they should trigger a senior planning conversation.

| Signal                                                  | Why it matters                                                   | Recommended response                                                                     |
| ------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Source checkout is heavily customized                   | Hosted checkout behavior may not reproduce bespoke source logic. | Confirm whether target checkout can be configured or whether process redesign is needed. |
| Product options depend on formulas or conditional rules | Standard product structures may not preserve buying logic.       | Sample complex products and classify custom behavior before scope is approved.           |
| Customer-specific pricing is ERP-controlled             | Pricing may live outside ordinary customer and product records.  | Identify external ownership and integration requirements.                                |
| Marketplace or fulfilment IDs must remain authoritative | External systems may need exact identifiers after launch.        | Preserve ID strategy or plan Custom Service review.                                      |
| Store relies on source-side database customizations     | Hosted SaaS boundaries may conflict with expectations.           | Confirm whether the business accepts platform-managed operations.                        |
| SEO inventory is incomplete                             | Important landing pages and redirects may be missed.             | Build priority URL and content map before migration.                                     |

### Choosing the Right Level of Migration Support <a href="#choosing-the-right-level-of-migration-support" id="choosing-the-right-level-of-migration-support"></a>

Fit assessment should lead directly into service-path planning. A strong fit with clean data can usually proceed through a more standard path. A conditional fit may need Managed Service support, Add-ons, or targeted preparation before Demo Migration. A weaker fit may require Custom Service review before the merchant can make a reliable platform decision.

| Fit result                                       | Likely handling                                                  | Why                                                                              |
| ------------------------------------------------ | ---------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Strong fit with ordinary records                 | Standard Service may be suitable.                                | Data maps cleanly and platform configuration is manageable.                      |
| Strong fit with many records or validation needs | Managed Service may be useful.                                   | The merchant needs guidance, review, or staged validation support.               |
| Conditional fit with specific mapping needs      | Add-ons may help where the requirement is bounded and supported. | Filtering, field mapping, or selected migration behavior may need configuration. |
| Conditional fit with app/custom data             | Custom Service review may be needed.                             | Unsupported records, custom fields, or external IDs may require custom handling. |
| Weak fit because of platform mismatch            | Reconsider platform or redesign expectations.                    | Migration cannot solve an operating-model mismatch by itself.                    |

The fit decision should remain practical. The goal is not to make every requirement appear possible. The goal is to decide whether ShopWired can support the merchant’s business model at an acceptable migration and operating cost.

### What to Confirm Before Choosing ShopWired <a href="#what-to-confirm-before-choosing-shopwired" id="what-to-confirm-before-choosing-shopwired"></a>

Before committing to ShopWired, the merchant should prepare evidence in the areas most likely to affect migration scope.

| Evidence area    | What to prepare                                                                                                 | Why it matters                                                          |
| ---------------- | --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Complex products | Products with the deepest options, variations, extras, bundles, personalization, stock, and pricing behavior.   | Confirms whether customer buying logic can be preserved.                |
| Customer samples | Registered customers, guest customers, newsletter subscribers, trade customers, and records with custom fields. | Confirms identity handling, segmentation, and order linkage.            |
| Order samples    | Orders with discounts, refunds, delivery differences, payment notes, status changes, and trade/customer links.  | Confirms historical readability and support value.                      |
| Checkout rules   | Delivery zones, rates, payment gateways, VAT/tax behavior, offers, and restrictions.                            | Separates migrated history from target configuration.                   |
| SEO assets       | Priority products, categories, brands, CMS Pages, URLs, metadata, redirects, and landing pages.                 | Protects discovery and search continuity.                               |
| Integration list | Apps, APIs, webhooks, accounting, fulfilment, stock sync, marketplaces, and external IDs.                       | Identifies what migrates, reconnects, rebuilds, or needs custom review. |

### Conclusion <a href="#conclusion" id="conclusion"></a>

ShopWired is a strong fit for merchants that want a hosted commerce platform with practical catalog depth, B2B/trade potential, managed operations, theme and content tools, apps, API access, and configurable checkout settings. It is strongest when the source store’s business meaning can be translated into ShopWired’s product, customer, order, content, checkout, and integration structures without needing to clone a bespoke source implementation.

ShopWired is a weaker or more conditional fit when the source store depends on advanced product configurators, deeply customized B2B rules, custom checkout logic, self-hosted backend control, app-owned records, or external-system identifiers that ordinary migration cannot represent. Those cases may still be viable, but they need evidence, target capability review, and the right service path before the project moves forward.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What makes ShopWired a strong migration fit?**

ShopWired is a strong fit when the merchant wants hosted commerce management and the source store’s catalog, customers, orders, content, checkout rules, and integrations can be represented through ShopWired-supported structures and target configuration.

**When is ShopWired a conditional fit rather than an obvious fit?**

It becomes conditional when the source store has complex product options, B2B/trade rules, app-owned data, marketplace identifiers, SEO-sensitive content, or integration dependencies that need review before migration scope can be confirmed.

**Is ShopWired suitable for highly customized stores?**

It depends on what is customized. Theme, app, API, and configuration work may be practical, but database-level control, bespoke checkout logic, advanced configurators, and external rules engines may require redesign or Custom Service review.

**Should B2B merchants consider ShopWired?**

Yes, when trade customer records, pricing expectations, quote behavior, account access, and checkout requirements can be defined clearly. Complex customer-specific catalogs, ERP-controlled pricing, or approval workflows need deeper review.

**What evidence should be prepared before choosing ShopWired?**

Prepare complex product samples, customer and trade customer examples, representative historical orders, checkout rules, SEO-priority pages and URLs, and a list of apps, API connections, webhooks, and external systems that affect store operations.
