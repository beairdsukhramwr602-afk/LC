# VTEX Pre-Migration Preparation Checklist

VTEX migration preparation should make the target result easier to scope, test, and approve. The preparation phase should not only collect product, customer, order, CMS Pages, and Blog Posts exports. It should also clarify how those records are expected to behave across VTEX Catalog, SKUs, specifications, pricing, promotions, trade policies, marketplace operations, OMS, logistics, Master Data, apps, APIs, storefront implementation, and external systems.

The main preparation challenge is separation. Some source-store information should migrate as records. Some behavior should be configured in VTEX. Some dependencies should be rebuilt through apps, APIs, storefront implementation, or external-system integration. Some requirements may fit Add-ons, while others require Custom Service because they involve custom logic, app-owned data, Custom Platform interpretation, tailored transformation, or unsupported migration behavior.

A strong VTEX preparation checklist produces evidence, not assumptions. It gives the migration team representative samples, gives stakeholders a shared review standard, and makes Demo Migration meaningful before Full Migration is approved.

### What VTEX Preparation Should Prove <a href="#what-vtex-preparation-should-prove" id="what-vtex-preparation-should-prove"></a>

Pre-migration preparation should prove that the project team understands what must be migrated, what must be configured, what must be rebuilt, and what must be validated separately. For VTEX, preparation should be organized by operating layer because a clean record transfer can still fail if the data cannot support selling, discovery, pricing, fulfillment, seller operations, customer service, reporting, or storefront experience.

| Preparation layer                | What to prepare                                                                                                                    | What it should prove                                                                   |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Target VTEX context              | Account, workspaces, storefront approach, trade policies, apps, integrations, and enabled commerce layers.                         | The target environment is ready to interpret migrated data correctly.                  |
| Catalog and SKU structure        | Products, SKUs, categories, brands, specifications, images, stock, services, kits, collections, attachments, and assembly options. | Products will be active, discoverable, purchasable, and commercially meaningful.       |
| Pricing and channel behavior     | Base prices, price tables, promotions, trade policies, sales channels, marketplace pricing, and external pricing owners.           | Price and availability expectations are not hidden inside source-store assumptions.    |
| Marketplace, OMS, and logistics  | Seller relationships, marketplace order context, status meaning, delivery/pickup behavior, invoices, and fulfillment references.   | Historical and operational order data can be reviewed with the right business context. |
| Customers, B2B, and Master Data  | Customer records, account relationships, custom entities, custom fields, consent, segmentation, and external IDs.                  | Customer meaning is preserved beyond name, email, and address fields.                  |
| Storefront and content           | Navigation, search, filters, CMS Pages, Blog Posts, landing pages, metadata, redirects, and priority URLs.                         | Migrated data can support launch discovery, SEO continuity, and content expectations.  |
| Apps, APIs, and external systems | ERP, PIM, WMS, CRM, accounting, payment, anti-fraud, marketplace, analytics, and custom frontend dependencies.                     | Ownership is clear for values that cannot be treated as ordinary migrated records.     |
| Service scope                    | Data Filter Add-on, Advanced Data Mapping, Advanced Data Configure, other Add-ons, and Custom Service signals.                     | The selected service path matches the real migration workload.                         |

Preparation is complete only when each layer has representative examples, known exclusions, ownership decisions, and review criteria. A simple export checklist is not enough for VTEX when commercial behavior depends on several connected platform layers.

### Confirm Target Account, Storefront, and Commerce Context <a href="#confirm-target-account-storefront-and-commerce-context" id="confirm-target-account-storefront-and-commerce-context"></a>

Before selecting samples or reviewing Demo Migration output, confirm the target VTEX operating context. VTEX projects may involve different storefront approaches, trade policies, sales channels, marketplaces, seller operations, apps, integrations, and implementation environments. Migration planning should reflect the target account that will actually be used for launch review.

| Item to confirm                   | Preparation detail                                                                                                                            | Why it matters                                                                                                           |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Account and environment           | Confirm the account, workspace or test environment, launch account, review access, and stakeholder responsibilities.                          | Reviewers need to know where migrated data will be evaluated and which environment represents launch behavior.           |
| Storefront approach               | Identify whether the project uses Store Framework, FastStore, headless implementation, legacy storefront areas, or another frontend approach. | Storefront implementation affects navigation, product display, content rendering, search, routing, and URL expectations. |
| Trade policies and sales channels | List sales channels, regions, B2B/B2C contexts, marketplaces, seller channels, or customer groups that affect availability and pricing.       | A product that looks correct in one context may be unavailable or incorrectly priced in another.                         |
| Apps and extensions               | Inventory VTEX IO apps, storefront apps, search apps, payment apps, marketplace apps, promotion apps, and business-process apps.              | App-owned data or app-controlled behavior may require separate setup, Custom Service, or exclusion.                      |
| Integration stack                 | Document ERP, PIM, WMS, OMS, CRM, accounting, payment, anti-fraud, marketplace, analytics, and data warehouse dependencies.                   | External systems may own product enrichment, price authority, inventory, order updates, or customer attributes.          |
| Operational stakeholders          | Identify catalog, merchandising, pricing, B2B, marketplace, operations, logistics, support, SEO, and integration reviewers.                   | Each reviewer should know which samples and pass conditions they are responsible for approving.                          |

This context prevents a common preparation problem: evaluating migrated records without knowing the target operating model. VTEX preparation should make the target environment readable before the first Demo Migration sample is judged.

### Prepare Catalog, SKU, and Specification Evidence <a href="#prepare-catalog-sku-and-specification-evidence" id="prepare-catalog-sku-and-specification-evidence"></a>

Catalog preparation is usually the most important VTEX readiness task because products and SKUs are separate concepts, categories structure the catalog, brands and specifications affect product meaning, and SKU activation depends on required information. Prepare samples that represent the real catalog, not only ordinary products.

| Sample type                               | Include                                                                                                                      | Readiness question                                                                                         |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Baseline product                          | Name, description, brand, category, image, SKU, stock, and price.                                                            | Does a normal product migrate into a usable VTEX product/SKU structure?                                    |
| Multi-SKU product                         | Multiple SKU choices with different images, prices, stock, specifications, or availability.                                  | Do source variants become sellable and understandable VTEX SKUs?                                           |
| Specification-heavy product               | Product and SKU specifications used for filters, comparison, compliance, or merchandising.                                   | Are structured values preserved for discovery and operation instead of being buried in descriptions?       |
| Category-sensitive product                | Products tied to important departments, categories, subcategories, or category-specific specification groups.                | Does category placement support navigation and the right specification behavior?                           |
| Stock-sensitive product                   | SKU-level inventory differences, fulfillment-sensitive items, warehouse-dependent items, or channel-specific stock concerns. | Can reviewers distinguish migrated stock records from live inventory configuration requirements?           |
| Attachment or customization product       | Products with personalization, required customer input, optional services, warranty, gift wrap, or custom add-on behavior.   | Should the source choice be mapped, configured, implemented, excluded, or reviewed through Custom Service? |
| Assembly, kit, collection, or bundle case | Products involving grouped SKUs, product combinations, special collections, services, or bundle-like selling logic.          | Does the requirement fit available migration handling, target setup, Add-ons, or Custom Service?           |
| Marketplace-relevant product              | Seller, marketplace, offer, external ID, received SKU, channel, or commission-related context.                               | Is marketplace meaning part of migration scope or separate marketplace configuration/integration work?     |

Catalog samples should include commercially important products, edge cases, and products that are structurally difficult. Simple records confirm baseline transfer, but they rarely prove VTEX readiness.

### Prepare Pricing, Promotions, and Trade Policy Evidence <a href="#prepare-pricing-promotions-and-trade-policy-evidence" id="prepare-pricing-promotions-and-trade-policy-evidence"></a>

VTEX pricing and availability can depend on base prices, fixed prices, price tables, promotions, coupons, trade policies, sales channels, marketplace context, B2B eligibility, and external pricing authority. Preparation should distinguish historical pricing information from live pricing behavior expected after launch.

| Commercial evidence           | What to gather                                                                                                       | Why it matters                                                                                              |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Base prices                   | Ordinary SKU price examples, currency expectations, and tax-display assumptions where relevant.                      | Establishes the simplest price baseline before complex rules are reviewed.                                  |
| Fixed prices and price tables | Customer-specific, B2B, regional, channel-specific, or marketplace-related price examples.                           | Prevents price differentiation from being flattened into one default value.                                 |
| Promotions and coupons        | Active, expired, category-specific, customer-specific, order-value, shipping, and campaign examples.                 | Separates promotion history from launch-ready promotional configuration.                                    |
| Trade policies                | Products or SKUs that differ by sales channel, marketplace, region, customer segment, logistics, or payment context. | Proves that channel-specific behavior has review samples, not just general product records.                 |
| Discounts in orders           | Orders where discount labels, totals, coupons, or promotion sources matter for history and support.                  | Helps reviewers interpret historical order totals without assuming live rules were configured by migration. |
| External pricing owner        | ERP, PIM, marketplace, pricing engine, or custom service that controls prices after launch.                          | Clarifies whether migration should preserve values, references, or only historical context.                 |

Preparation should include examples where the same SKU behaves differently across commercial contexts. If no such examples exist, that is useful evidence. If they do exist, they should be tested before Full Migration, not discovered during launch review.

### Prepare Marketplace, Seller, OMS, and Logistics Samples <a href="#prepare-marketplace-seller-oms-and-logistics-samples" id="prepare-marketplace-seller-oms-and-logistics-samples"></a>

VTEX often supports marketplace, seller, OMS, and logistics workflows that cannot be reduced to generic order history. Order records may need to remain readable for customer service, finance, seller operations, fulfillment, shipping, pickup, delivery, and integration reconciliation.

| Sample area                                       | What to include                                                                                                  | Review purpose                                                                                 |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Standard completed order                          | Customer, products, quantities, totals, discounts, shipping, payment label, and status.                          | Establishes ordinary historical order readability.                                             |
| Cancelled, refunded, or partially fulfilled order | Cancellation reason, refund context, partial shipment, replacement, or service case information.                 | Confirms exception history does not become misleading.                                         |
| Marketplace order                                 | Marketplace role, seller identity, received SKU, offer context, commission or channel references where relevant. | Prevents seller and marketplace meaning from being flattened into ordinary order notes.        |
| Seller-handled order                              | Seller responsibility, fulfillment status, invoice context, and delivery ownership.                              | Clarifies whether seller order context is in scope, historical only, or external-system owned. |
| Pickup or delivery example                        | Delivery channel, pickup point, shipping estimate, carrier, tracking, or warehouse reference.                    | Keeps logistics meaning visible when order history is reviewed.                                |
| ERP or WMS-integrated order                       | External IDs, invoice numbers, fulfillment references, status sync, or reconciliation keys.                      | Identifies values that support operations after migration.                                     |

The preparation goal is not to recreate live OMS flows through migration. The goal is to decide which order fields and references must remain understandable, which belong to target configuration, and which require integration or Custom Service review.

### Prepare Customer, B2B, Consent, and Master Data Evidence <a href="#prepare-customer-b2b-consent-and-master-data-evidence" id="prepare-customer-b2b-consent-and-master-data-evidence"></a>

Customer preparation should go beyond names, emails, and addresses. VTEX projects may involve B2C customers, B2B accounts, custom customer fields, segmentation, trade-policy eligibility, consent preferences, Master Data entities, and external IDs used by apps or integrations.

| Data area                      | What to prepare                                                                                                          | Readiness question                                                                                           |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| Ordinary customers             | Name, email, phone, addresses, account status, order relationship, and communication preference where available.         | Can customer records be reviewed clearly after migration?                                                    |
| B2B or account-based customers | Company context, buyer roles, account hierarchy, approval needs, shared addresses, price eligibility, or purchase rules. | Is B2B meaning supported by migration, target setup, external systems, or Custom Service?                    |
| Segmentation and eligibility   | Groups, tags, lists, trade-policy eligibility, marketing lists, or commercial segmentation.                              | Does the segment affect commerce behavior or only reporting/marketing history?                               |
| Consent and preference data    | Newsletter status, opt-in/opt-out values, privacy preferences, and communication flags.                                  | Which values must be preserved, excluded, or revalidated for policy and business reasons?                    |
| Master Data entities           | Entity names, fields, schemas, relationships, external IDs, and operational use cases.                                   | Is the custom data part of ordinary migration scope, Add-ons, Custom Service, or target-side implementation? |
| App-owned customer fields      | Loyalty, subscription, personalization, approval, membership, wallet, or account extension values.                       | Which app or external system owns the value after launch?                                                    |

Master Data and custom customer information should be classified by business use. A field that only appears in the source database may not need migration. A field that controls eligibility, service, reporting, integrations, compliance, or user experience may need structured planning.

### Prepare Storefront, Search, Content, and URL Evidence <a href="#prepare-storefront-search-content-and-url-evidence" id="prepare-storefront-search-content-and-url-evidence"></a>

VTEX storefront readiness may involve Store Framework, FastStore, headless frontend work, search configuration, route planning, filters, CMS Pages, Blog Posts, campaign pages, landing pages, product detail pages, and SEO-sensitive URLs. Migration preparation should separate data migration from storefront implementation.

| Storefront area                 | What to prepare                                                                                                            | Why it matters                                                                                                   |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Product detail pages            | High-value products with images, specifications, price visibility, availability, services, attachments, and buying flow.   | Confirms migrated data can support the intended customer-facing product experience.                              |
| Category and listing pages      | Important departments, categories, subcategories, collections, filters, and merchandising-sensitive listings.              | Helps detect navigation and discovery gaps before launch.                                                        |
| Search and facets               | Priority search terms, filters, facet groups, autocomplete expectations, synonyms, and merchandising-sensitive queries.    | Specifications and category data may need cleanup before they can support search quality.                        |
| CMS Pages and Blog Posts        | Brand pages, buying guides, landing pages, support pages, campaign pages, and editorial content.                           | Content may need migration, rebuilding, restructuring, or exclusion depending on target storefront architecture. |
| URLs and redirects              | Priority product, category, content, campaign, and organic landing-page URLs.                                              | SEO-sensitive paths should have redirect and metadata planning before Full Migration.                            |
| Metadata and structured content | Page titles, meta descriptions, canonical expectations, image alt text, heading priorities, and sitemap concerns.          | Preserves discoverability signals where they matter.                                                             |
| Frontend dependencies           | Custom components, route logic, product cards, account pages, cart behavior, checkout customizations, and content sources. | Separates migrated data from implementation work.                                                                |

Storefront preparation should not assume the source theme can be copied into VTEX through migration. The important question is which data must be available for the target storefront to present, search, filter, and route correctly.

### Prepare Apps, APIs, and External-System Ownership <a href="#prepare-apps-apis-and-external-system-ownership" id="prepare-apps-apis-and-external-system-ownership"></a>

VTEX migrations often depend on app and integration context. ERP, PIM, WMS, CRM, accounting, payment, anti-fraud, marketplace, analytics, search, personalization, loyalty, subscription, and custom frontend systems may own values that appear in the source platform but should not be blindly migrated.

| Dependency type             | What to document                                                                                                      | Planning implication                                                                         |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| ERP                         | Product codes, price authority, stock, invoices, customers, orders, fulfillment, and accounting references.           | Decide which values are migrated as history and which remain system-owned after launch.      |
| PIM                         | Product enrichment, images, categories, specifications, translations, approval workflows, and brand data.             | Catalog fields may need mapping from the PIM model, not only the source commerce platform.   |
| WMS/logistics               | Warehouse IDs, carrier rules, shipping methods, pickup points, delivery promises, tracking, and fulfillment statuses. | Migration should preserve useful references while live fulfillment is configured separately. |
| Marketplace systems         | Seller IDs, offer IDs, received SKUs, commission context, channel rules, and marketplace matching logic.              | Marketplace context may require Custom Service or separate implementation.                   |
| Payment and anti-fraud      | Provider references, authorization states, transaction IDs, gift cards, fraud review, and reporting labels.           | Historical payment labels should be distinguished from live payment configuration.           |
| VTEX IO and storefront apps | App name, related records, owned fields, storefront impact, and launch dependency.                                    | App-owned data may require app setup, mapping, Custom Service, or exclusion.                 |
| APIs and middleware         | External IDs, synchronization keys, webhook needs, feed behavior, and ownership rules.                                | Integration references should be preserved only when they remain useful and correctly owned. |

A good dependency inventory prevents two weak outcomes: losing values that matter to operations, or migrating obsolete technical fields that clutter the new environment without supporting business decisions.

### Choose Demo Migration Samples Deliberately <a href="#choose-demo-migration-samples-deliberately" id="choose-demo-migration-samples-deliberately"></a>

Demo Migration should test the VTEX areas with the highest business risk. It should include ordinary records, but it should also include the structural cases that determine whether the migration approach is realistic.

| Demo Migration sample                        | Include when                                                                                              | What it should prove                                                                         |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Baseline catalog sample                      | Ordinary products represent a meaningful share of the catalog.                                            | Standard product, SKU, category, image, price, and stock movement is understandable.         |
| Complex SKU sample                           | Variants, specifications, stock, price, images, or availability differ by SKU.                            | Product choices remain sellable and discoverable.                                            |
| Attachment, service, kit, or assembly sample | Customization, services, bundles, kits, or add-on choices affect selling.                                 | Requirements are classified for standard handling, Add-ons, target setup, or Custom Service. |
| Trade policy or price-table sample           | Pricing or availability changes by channel, customer, region, B2B context, or marketplace.                | Commercial behavior can be evaluated in the right target context.                            |
| Marketplace or seller sample                 | Seller, offer, marketplace order, received SKU, or commission context matters.                            | Marketplace meaning is not misread as generic product or order data.                         |
| Master Data or custom field sample           | Custom entities, app-owned fields, external IDs, or checkout values affect business processes.            | Custom data ownership and service path are clear.                                            |
| Storefront and URL sample                    | Important products, categories, CMS Pages, Blog Posts, landing pages, or organic URLs carry launch value. | Search, navigation, content, and SEO-sensitive paths can be reviewed.                        |
| Integration-sensitive sample                 | ERP, PIM, WMS, payment, marketplace, or middleware references affect review.                              | External-system meaning is preserved or explicitly assigned outside migration.               |

Sample selection should be documented before the Demo Migration starts. Each sample should have a reason, a reviewer, and a pass condition.

### Identify Add-ons and Custom Service Signals Early <a href="#identify-add-ons-and-custom-service-signals-early" id="identify-add-ons-and-custom-service-signals-early"></a>

Preparation should identify where the migration can use standard handling, where Add-ons may support filtering or mapping needs, and where Custom Service is more appropriate. Add-ons and Custom Service should not be used interchangeably.

| Preparation signal                                                                                            | Likely handling path                                                             | Reasoning                                                                               |
| ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Only selected eligible records should migrate.                                                                | Data Filter Add-on, where available.                                             | Estimated entity numbers do not act as migration filters.                               |
| Supported field mapping needs controlled adjustment.                                                          | Advanced Data Mapping, if the mapping fits available capability.                 | Mapping changes can help when both source and target fields are supported.              |
| Supported values need configured transformation.                                                              | Advanced Data Configure, if the change fits available service capability.        | Configuration can help when the value change is supported and bounded.                  |
| Custom Platform source.                                                                                       | Custom Service.                                                                  | Custom source interpretation requires tailored review.                                  |
| Product configurator, bundle, service, kit, attachment, or assembly behavior does not fit supported handling. | Custom Service or separate target implementation.                                | The requirement may involve tailored logic rather than simple record transfer.          |
| Marketplace, seller, received SKU, commission, or offer matching must be preserved.                           | Custom Service review.                                                           | Marketplace data carries workflow meaning that standard entity mapping may not capture. |
| Master Data, app-owned records, custom checkout fields, or external IDs are business-critical.                | Custom Service review.                                                           | Custom data structures require ownership and mapping decisions.                         |
| ERP/PIM/WMS/payment/anti-fraud/headless dependencies affect launch behavior.                                  | Custom Service, integration work, or target-side implementation.                 | External systems may own live behavior after launch.                                    |
| Storefront implementation, search, layout, component behavior, or route logic is expected to change.          | Separate implementation or Custom Service review if migration logic is affected. | Storefront build work should not be hidden inside migration assumptions.                |

Preparation should produce a written service-scope view before Full Migration: what stays standard, what needs Add-ons, what needs Custom Service, what requires target configuration, and what remains outside migration scope.

### Plan for Follow-Up Migration Review <a href="#plan-for-follow-up-migration-review" id="plan-for-follow-up-migration-review"></a>

VTEX stores often continue changing while migration preparation is underway. New products, SKUs, specifications, prices, promotions, marketplace records, customers, orders, CMS Pages, Blog Posts, Master Data, and app records may appear after Demo Migration. Additional Migration Options can help with later activity, but they should not bypass review when the new data introduces new structures.

| Later change                                                        | Preparation action                                                         | Entity Points note                                                                                                                           |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| New records that match already-tested structures.                   | Review whether the follow-up action can proceed with limited revalidation. | New eligible Product, Customer, Order, or Blog Posts records may consume Entity Points when migrated for the first time.                     |
| New products with different SKU/specification behavior.             | Add them to revalidation samples before follow-up activity is approved.    | Records already counted through the service license do not consume Entity Points again simply because another migration action is performed. |
| New price tables, trade policies, promotions, or marketplace rules. | Recheck commercial behavior, not only record existence.                    | New eligible records may consume Entity Points when first migrated, even on the same migration path.                                         |
| New Master Data, app-owned fields, or integration keys.             | Confirm ownership and whether Custom Service is needed.                    | Duplicate consumption should not be assumed for records already counted through the service license.                                         |
| New CMS Pages, Blog Posts, landing pages, or SEO-sensitive URLs.    | Recheck content routing, metadata, redirects, and storefront presentation. | Blog Posts follow the same first-time migration principle when eligible.                                                                     |

The follow-up plan should identify which changes are safe because they match tested patterns and which changes require renewed review because they introduce new VTEX behavior.

### VTEX Preparation Readiness Matrix <a href="#vtex-preparation-readiness-matrix" id="vtex-preparation-readiness-matrix"></a>

Use the matrix below before Demo Migration and again before Full Migration. The goal is to confirm that preparation is broad enough to support a meaningful review.

| Readiness area            | Minimum evidence                                                                | Strong readiness signal                                                                                                          |
| ------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Target context            | Account, storefront approach, trade policies, apps, and integrations are known. | Reviewers know which target environment and sales contexts must approve results.                                                 |
| Catalog/SKU structure     | Ordinary and complex product samples are selected.                              | Samples include SKU variation, specifications, attachments, services, kits, collections, stock, and category-sensitive products. |
| Pricing/trade policies    | Base prices and major rules are listed.                                         | Channel-specific, B2B, marketplace, promotion, and external pricing examples are prepared.                                       |
| Marketplace/OMS/logistics | Ordinary order samples are available.                                           | Seller, marketplace, pickup, delivery, refund, partial fulfillment, invoice, and external references are represented.            |
| Customer/Master Data      | Customer profiles and addresses are prepared.                                   | B2B, segmentation, consent, Master Data, app-owned fields, and external IDs are classified.                                      |
| Storefront/content/URLs   | Priority products and categories are known.                                     | Search, facets, CMS Pages, Blog Posts, landing pages, redirects, metadata, and frontend dependencies are documented.             |
| Apps/integrations         | Main systems are listed.                                                        | Ownership is assigned for each app/API/external-system value that affects launch behavior.                                       |
| Service path              | Basic service expectation is known.                                             | Standard handling, Add-ons, Custom Service, target setup, and exclusions are separated.                                          |
| Follow-up handling        | Data changes are expected.                                                      | Additional Migration Options review includes structural revalidation and Entity Points implications.                             |

### Conclusion <a href="#conclusion" id="conclusion"></a>

VTEX migration preparation should turn a complex platform move into a controlled review process. Catalog, SKUs, specifications, trade policies, pricing, promotions, marketplace records, OMS history, logistics context, customer data, Master Data, storefront content, CMS Pages, Blog Posts, URLs, apps, APIs, and external-system references should be prepared as connected business evidence.

The strongest preparation set includes ordinary records and difficult examples. It shows where the migration can remain within standard handling, where Add-ons may help, where Custom Service should be reviewed, and where target configuration or external-system implementation must be handled separately. That preparation makes Demo Migration useful and reduces the risk of approving a record transfer that does not support the intended VTEX launch.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first before migrating to VTEX?**

Start with the target VTEX context: account, storefront approach, trade policies, sales channels, marketplace or seller setup, apps, integrations, and operational reviewers. After that, prepare catalog, pricing, customer, order, storefront, Master Data, and integration samples.

**Which VTEX catalog samples are most useful before Demo Migration?**

Use samples that expose real structure: multi-SKU products, specification-heavy products, category-sensitive products, products with different images or stock by SKU, attachments, assembly options, services, kits, collections, marketplace-related products, and high-value products that affect launch confidence.

**Should pricing and trade policies be prepared before migration?**

Yes. VTEX pricing and availability may depend on base prices, price tables, promotions, trade policies, sales channels, B2B context, marketplace behavior, or external pricing systems. Preparing examples early prevents reviewers from mistaking a correct default price for complete commercial readiness.

**Does migrating historical orders configure live VTEX OMS and logistics behavior?**

No. Historical order migration can preserve readable order context, but live OMS, logistics, fulfillment, pickup, delivery, invoicing, and integration behavior require target configuration and separate validation.

**When should VTEX preparation raise Custom Service review?**

Raise Custom Service review when the project involves Custom Platform source data, custom product logic, marketplace or seller workflow data, Master Data entities, app-owned records, custom checkout fields, external-system references, integration-dependent values, or any requirement that needs tailored migration logic beyond available standard handling and Add-ons.
