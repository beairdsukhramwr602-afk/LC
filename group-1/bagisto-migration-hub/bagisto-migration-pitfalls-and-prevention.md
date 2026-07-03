# Bagisto Migration Pitfalls and Prevention

Bagisto migrations usually fail when the project treats Bagisto as a simple destination for product, customer, and order records while ignoring the technical and operational structure that gives those records meaning. Because Bagisto is an open-source Laravel e-commerce platform, the final result can depend on catalog attributes, channels, themes, extensions, custom code, marketplace modules, B2B logic, APIs, headless storefronts, and connected systems working together.

A complete-looking migration is not always a launch-ready Bagisto store. Products may appear in the admin area, customers may exist, and orders may be present, but the business can still run into problems if product attributes do not support filtering, channels do not show the right catalog, B2B buyers cannot access the right pricing, vendor context is unclear, or a headless frontend cannot consume the expected data.

The pitfalls below focus on recurring failure patterns. Each one explains what goes wrong, the warning signs to watch for, how to prevent the issue, a practical recommendation example, and what a passing result should prove before the project moves closer to launch.

### Pitfall Summary <a href="#pitfall-summary" id="pitfall-summary"></a>

| Pitfall                                                    | What usually fails                                                                                                       | Best prevention focus                                                                                                 |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| Treating Laravel flexibility as automatic migration fit    | The project assumes Bagisto can absorb any source behavior because it is customizable                                    | Separate standard migration scope from configuration, development, extension work, and Custom Service needs           |
| Flattening product attributes and variant meaning          | Products exist, but attributes, options, variants, filters, and technical details do not support buying decisions        | Prepare representative product samples and define how source fields should behave in Bagisto                          |
| Misreading channels, storefronts, or headless contexts     | Data migrates but appears in the wrong selling context or fails in the customer-facing frontend                          | Document channel, route, storefront, theme, and API ownership before validation                                       |
| Treating extensions as ordinary data containers            | Extension-owned or custom-code-owned behavior is expected to transfer as native data                                     | Identify extension dependencies and decide what migrates, what is rebuilt, and what needs Custom Service              |
| Underplanning B2B, marketplace, or vendor behavior         | Customers, companies, vendors, or buyer groups migrate without the access, pricing, role, or ownership meaning they need | Validate realistic buyer, company, vendor, and marketplace scenarios, not only record presence                        |
| Preserving orders without operational context              | Orders are present but weak for customer support, fulfillment, accounting, vendor review, or reporting                   | Test historical orders with statuses, payments, shipments, discounts, taxes, vendor context, and external identifiers |
| Using a clean Demo Migration sample                        | Early results look successful but hide real catalog, channel, extension, or integration risk                             | Build Demo Migration samples around difficult records, not only ordinary records                                      |
| Launching before integrations and late data are controlled | Final data, APIs, connected systems, and recent source activity are not aligned before go-live                           | Define ownership, cutover windows, Recent Data Migration use, and final validation checkpoints                        |

### Pitfall 1: Assuming Bagisto Flexibility Solves Every Migration Gap <a href="#pitfall-1-assuming-bagisto-flexibility-solves-every-migration-gap" id="pitfall-1-assuming-bagisto-flexibility-solves-every-migration-gap"></a>

#### What Goes Wrong <a href="#what-goes-wrong" id="what-goes-wrong"></a>

Bagisto’s Laravel foundation can make the platform feel highly adaptable, but flexibility is not the same as automatic migration compatibility. A merchant may assume that because Bagisto can be customized, any source behavior can move into the Target Platform without a clear plan. That assumption can blur the boundary between data migration, Bagisto configuration, extension setup, theme work, integration reconnection, and custom development.

The result is often a migration that appears technically possible but is not scoped correctly. Standard product, customer, and order records may migrate, while the behavior that made the source store work remains unresolved. Custom checkout logic, unusual product structures, marketplace ownership, B2B buyer roles, non-standard identifiers, and API-driven workflows may need review before they can be treated as part of the expected migration outcome.

#### Early Warning Signs <a href="#early-warning-signs" id="early-warning-signs"></a>

* The team describes important requirements as “Bagisto can be customized” without defining what must be migrated, configured, rebuilt, or developed.
* Source behavior depends on custom code, modified database tables, third-party modules, or integration logic that has not been documented.
* Requirements are described by desired appearance rather than by data ownership and behavior.
* Demo Migration samples avoid records that depend on custom logic.
* The project treats Custom Service review as a backup option instead of identifying customization needs early.

#### Prevention <a href="#prevention" id="prevention"></a>

Separate source data from platform behavior before migration execution. Identify which requirements can be handled through standard migration capability, which require Bagisto configuration, which depend on extensions or connected systems, and which require customization, modification, Custom Platform handling, or custom migration logic adjustment.

Bagisto’s flexibility is most useful when the merchant can define the intended outcome. If the source behavior is custom, undocumented, or dependent on external systems, it should be reviewed before Full Migration so the project does not mistake developer possibility for migration readiness.

#### Recommendation Example <a href="#recommendation-example" id="recommendation-example"></a>

A merchant moving from a heavily modified Source Platform may have custom product visibility rules, modified checkout behavior, special customer approvals, and custom order statuses. Instead of assuming those behaviors will move because Bagisto can be customized, the project should identify which items are standard migration data, which are Bagisto configuration tasks, and which require Custom Service review.

#### Pass Condition <a href="#pass-condition" id="pass-condition"></a>

This pitfall is prevented when every important source behavior has an owner: migrated as data, configured in Bagisto, rebuilt through an extension or integration, excluded intentionally, or reviewed through Custom Service before launch-critical execution.

### Pitfall 2: Flattening Product Attributes, Options, and Variant Meaning <a href="#pitfall-2-flattening-product-attributes-options-and-variant-meaning" id="pitfall-2-flattening-product-attributes-options-and-variant-meaning"></a>

#### What Goes Wrong <a href="#what-goes-wrong-1" id="what-goes-wrong-1"></a>

Products migrate into Bagisto, but the catalog does not behave like a usable Bagisto catalog. Product names, SKUs, images, and prices may exist, while the attributes, product types, variants, configurable relationships, filtering values, technical specifications, and buying choices lose their intended meaning.

This pitfall is common when the Source Platform used custom fields, product option workarounds, technical attribute tables, extension-owned data, or inconsistent variant naming. Bagisto can support structured product information, but migration quality depends on deciding how the source product's meaning should translate into Bagisto’s product model.

#### Early Warning Signs <a href="#early-warning-signs-1" id="early-warning-signs-1"></a>

* Source product fields are numerous, inconsistent, or poorly named.
* Product options, variants, and attributes are mixed together without clear commercial meaning.
* Technical specifications are stored in descriptions, custom fields, spreadsheets, or external systems.
* Products appear in Bagisto, but filters, variant choices, product comparison, or search behavior are weak.
* The team validates only simple products and ignores products with attributes, variants, grouped logic, or extension-owned data.

#### Prevention <a href="#prevention-1" id="prevention-1"></a>

Prepare product samples that reveal the full catalog burden. Include simple products, variant-heavy products, products with many attributes, products assigned to several categories or channels, products with technical specifications, products with downloadable or virtual behavior where relevant, and products affected by extensions or custom fields.

Before Full Migration, decide what each source product structure should become in Bagisto. Some values may become attributes, some may become product content, some may support variants or filtering, and some may require Custom Service if the source structure is non-standard or depends on custom logic.

#### Recommendation Example <a href="#recommendation-example-1" id="recommendation-example-1"></a>

A store selling replacement parts should not validate only a clean product with one SKU and one image. A stronger Bagisto sample includes a product with compatibility attributes, several variants, technical specifications, multiple category assignments, source-specific custom fields, and a high-value storefront route.

#### Pass Condition <a href="#pass-condition-1" id="pass-condition-1"></a>

Product structure passes when customers can find the product, understand its technical details, select the right option or variant, see accurate pricing and availability, and reach the product through the intended category, search, channel, and storefront paths.

### Pitfall 3: Misreading Channels, Storefronts, and Headless Context <a href="#pitfall-3-misreading-channels-storefronts-and-headless-context" id="pitfall-3-misreading-channels-storefronts-and-headless-context"></a>

#### What Goes Wrong <a href="#what-goes-wrong-2" id="what-goes-wrong-2"></a>

Data migrates into Bagisto, but it does not appear in the right selling context. Products may belong to the wrong channel, categories may not support the intended storefront structure, URLs may not match launch expectations, or a headless frontend may fail to consume the migrated data in the way customers actually experience the store.

This pitfall is especially risky when Bagisto is used beyond a single ordinary storefront. Marketplace projects, B2B portals, multi-tenant commerce, custom themes, mobile experiences, POS-connected commerce, and headless storefronts can all change what “correct data” means. The same product record may need different visibility, pricing, routing, presentation, or API behavior depending on the channel or frontend context.

#### Early Warning Signs <a href="#early-warning-signs-2" id="early-warning-signs-2"></a>

* The source store has multiple storefronts, sales channels, or presentation layers, but the migration plan treats the target as one generic storefront.
* Channel ownership is unclear for products, categories, currencies, locales, inventory, or content.
* A custom theme or headless frontend is expected to display migrated data, but frontend data requirements have not been documented.
* High-value routes, menus, landing pages, or API-fed pages are not included in validation.
* The team checks admin records but does not test the customer-facing storefront or connected frontend.

#### Prevention <a href="#prevention-2" id="prevention-2"></a>

Document the intended Bagisto selling structure before migration. Identify channels, storefronts, customer-facing routes, theme dependencies, headless/API needs, mobile or POS relationships, marketplace boundaries, and any separate B2B or tenant contexts.

Validation should include both admin review and customer-facing review. If a product, category, customer group, or order record matters to a headless frontend, marketplace, B2B area, or custom theme, test it in that actual context rather than only checking that the record exists.

#### Recommendation Example <a href="#recommendation-example-2" id="recommendation-example-2"></a>

A merchant planning a headless Bagisto storefront should include products, categories, prices, images, attributes, and customer-group examples that the frontend must consume after migration. If the admin record looks correct but the API response lacks the fields the frontend expects, the migration result is not launch-ready.

#### Pass Condition <a href="#pass-condition-2" id="pass-condition-2"></a>

Channel and storefront handling pass when migrated data appears in the correct Bagisto context, supports the intended customer journey, and can be used by the theme, headless frontend, mobile app, POS flow, marketplace structure, or B2B area that depends on it.

### Pitfall 4: Treating Extensions and Custom Code as Ordinary Data <a href="#pitfall-4-treating-extensions-and-custom-code-as-ordinary-data" id="pitfall-4-treating-extensions-and-custom-code-as-ordinary-data"></a>

#### What Goes Wrong <a href="#what-goes-wrong-3" id="what-goes-wrong-3"></a>

The migration plan assumes that extension-owned data, custom fields, modified workflows, or custom Laravel code will behave like ordinary Bagisto records. After migration, the values may exist somewhere, but the behavior they powered no longer works. A field that controlled product fitment, marketplace commission, buyer approval, special pricing, shipping logic, or fulfillment routing may be preserved as text while losing operational function.

In Bagisto projects, extensions and custom code can shape commercial behavior. The risk is not only missing data. The bigger risk is moving data without the logic that was used for it.

#### Early Warning Signs <a href="#early-warning-signs-3" id="early-warning-signs-3"></a>

* Staff refers to “module data,” “custom fields,” or “developer logic” without explaining how it affects the store.
* Source exports contain columns that do not map cleanly into Bagisto’s standard structures.
* The project includes marketplace, B2B, multi-tenant, shipping, payment, search, ERP, CRM, or fulfillment extensions.
* The team expects copied data to recreate automation or workflow behavior.
* There is no distinction between data migration, extension configuration, integration reconnection, and custom migration logic adjustment.

#### Prevention <a href="#prevention-3" id="prevention-3"></a>

Inventory extension-owned and custom-code-owned behavior before migration. For each dependency, decide whether the data should become Bagisto native data, extension configuration, custom field reference information, integration data, excluded legacy information, or Custom Service work.

If the source behavior is non-standard, modified, or not directly supported by standard migration capability, it should not be forced into a generic data migration. Custom Service review should clarify whether the expected outcome requires transformation, custom mapping, custom migration logic adjustment, or post-migration development coordination.

#### Recommendation Example <a href="#recommendation-example-3" id="recommendation-example-3"></a>

A marketplace source may store vendor commission rules, seller ownership, product approval status, payout references, and fulfillment responsibilities in extension tables. Those values should not be treated as ordinary product notes. The migration plan should define how vendor ownership and marketplace behavior will be represented in Bagisto and what falls outside standard migration capability.

#### Pass Condition <a href="#pass-condition-3" id="pass-condition-3"></a>

Extension-dependent data passes when its purpose, destination, and behavior are clear: migrated natively, configured in Bagisto, reconnected through an integration, retained as reference data, excluded intentionally, or handled through Custom Service.

### Pitfall 5: Underplanning B2B, Marketplace, or Vendor Behavior <a href="#pitfall-5-underplanning-b2b-marketplace-or-vendor-behavior" id="pitfall-5-underplanning-b2b-marketplace-or-vendor-behavior"></a>

#### What Goes Wrong <a href="#what-goes-wrong-4" id="what-goes-wrong-4"></a>

Customers, companies, vendors, or buyer groups migrate, but the commercial relationships do not work. B2B buyers may not have the right account context, company users may not have expected roles, customer groups may not see the correct prices, RFQ or quote-related expectations may be missing, and marketplace vendors may lose product or order ownership meaning.

This pitfall happens when the migration treats B2B or marketplace structure as ordinary customer and product data. In Bagisto, the value of these models often comes from relationships: who owns a product, who can buy it, who can approve it, who receives the order, which company or buyer group applies, and which workflow should continue after launch.

#### Early Warning Signs <a href="#early-warning-signs-4" id="early-warning-signs-4"></a>

* Buyer groups, company accounts, vendor records, or seller ownership are undocumented.
* Pricing, quote, RFQ, approval, catalog visibility, or role behavior is discussed only after migration starts.
* Marketplace products are validated as products but not as vendor-owned listings.
* B2B customers are validated as customer records but not as buyer journeys.
* Staff cannot identify which accounts, companies, vendors, or buyer roles should be included in Demo Migration review.

#### Prevention <a href="#prevention-4" id="prevention-4"></a>

Prepare representative B2B, marketplace, and vendor scenarios before Demo Migration. Include ordinary retail customers, B2B buyers, company accounts, role-based users, special price examples, quote or RFQ expectations where relevant, vendor-owned products, vendor order examples, and historical records that staff still use for review.

If marketplace or B2B behavior depends on paid modules, extensions, custom logic, or external systems, identify those dependencies before the migration approach is chosen. Some requirements may fit standard migration capability; others may require configuration, Add-ons, or Custom Service review.

#### Recommendation Example <a href="#recommendation-example-4" id="recommendation-example-4"></a>

A B2B marketplace should not validate only a retail customer and a simple product. A stronger sample includes a company buyer, a buyer with special pricing, a vendor-owned product, a marketplace order, a product awaiting approval where relevant, and an order that needs vendor or fulfillment context.

#### Pass Condition <a href="#pass-condition-4" id="pass-condition-4"></a>

B2B and marketplace handling pass when migrated records support the intended buyer, company, vendor, pricing, ownership, approval, order, and fulfillment behavior instead of existing only as disconnected customers and products.

### Pitfall 6: Preserving Orders Without Preserving Operational Context <a href="#pitfall-6-preserving-orders-without-preserving-operational-context" id="pitfall-6-preserving-orders-without-preserving-operational-context"></a>

#### What Goes Wrong <a href="#what-goes-wrong-5" id="what-goes-wrong-5"></a>

Orders migrate into Bagisto, but staff cannot use them confidently after launch. Line items, statuses, payments, discounts, taxes, shipping details, customer notes, vendor relationships, refund history, invoice references, fulfillment identifiers, or external system IDs may be incomplete or difficult to interpret.

Order history should remain useful for customer support, fulfillment review, accounting checks, reporting, vendor coordination, and dispute investigation. If the migrated order is present but the operational story is unclear, the migration has preserved a record without preserving enough business context.

#### Early Warning Signs <a href="#early-warning-signs-5" id="early-warning-signs-5"></a>

* Validation checks only order totals and dates.
* Source order statuses do not have a clear interpretation in Bagisto.
* Marketplace, B2B, vendor, offline payment, partial shipment, refund, or manual order examples are excluded from the sample.
* ERP, accounting, shipping, tax, payment, or fulfillment identifiers are not documented.
* Staff cannot use migrated orders to answer common post-launch questions.

#### Prevention <a href="#prevention-5" id="prevention-5"></a>

Build an order sample set around operational reality. Include ordinary completed orders, older orders, refunded or partially fulfilled orders, discounted orders, high-value orders, B2B orders, marketplace/vendor orders, offline payment orders, unusual shipping examples, and orders with external identifiers.

Review order samples with the teams that use them after launch. Customer service, fulfillment, accounting, marketplace operations, and sales staff may each notice different gaps. Where order meaning depends on custom statuses, extension-owned data, or outside systems, decide whether the requirement needs Add-on review, integration work, or Custom Service.

#### Recommendation Example <a href="#recommendation-example-5" id="recommendation-example-5"></a>

A marketplace merchant should validate an order involving a vendor-owned product, an order with partial fulfillment, an order with a refund, an order with tax and shipping complexity, and an order tied to an external accounting or fulfillment reference. A clean paid order is not enough to prove operational continuity.

#### Pass Condition <a href="#pass-condition-5" id="pass-condition-5"></a>

Order history passes when staff can understand what was bought, by whom, from which seller or channel where relevant, at what price, with which discounts, taxes, payment context, shipping method, fulfillment state, and operational references.

### Pitfall 7: Using Demo Migration Samples That Avoid Real Bagisto Risk <a href="#pitfall-7-using-demo-migration-samples-that-avoid-real-bagisto-risk" id="pitfall-7-using-demo-migration-samples-that-avoid-real-bagisto-risk"></a>

#### What Goes Wrong <a href="#what-goes-wrong-6" id="what-goes-wrong-6"></a>

Demo Migration is performed with clean, ordinary, or recently created records that do not represent the store’s real migration burden. The sample looks successful, but Full Migration later exposes issues with old products, variants, attributes, channels, B2B buyers, marketplace vendors, custom fields, extension-owned data, headless routes, or integration-dependent orders.

A weak Demo Migration sample creates false confidence. Demo Migration should reveal whether Bagisto can support the intended operating model, not merely prove that easy records can move.

#### Early Warning Signs <a href="#early-warning-signs-6" id="early-warning-signs-6"></a>

* The sample includes only simple products and ordinary customers.
* No variant-heavy, attribute-heavy, channel-specific, B2B, marketplace, headless, or integration-sensitive records are included.
* Staff choose records because they are clean rather than because they expose risk.
* Demo Migration review focuses on record counts instead of behavior.
* Findings are not connected to service approach, Add-on needs, configuration work, or Custom Service review.

#### Prevention <a href="#prevention-6" id="prevention-6"></a>

Design Demo Migration samples around risk and decision value. Include baseline records for comparison and difficult records for stress testing. A strong Bagisto sample should include complex products, variant products, attribute-heavy products, deep categories, channel-specific records, B2B or company accounts where relevant, vendor-owned products where relevant, historical orders, custom fields, extension-owned data, and integration-dependent examples.

After Demo Migration, classify findings clearly. Some issues may be launch-ready after configuration. Some may require data cleanup, Add-ons, Re-Migration, or Custom Service review. The sample should help the merchant choose the right next action before Full Migration.

#### Recommendation Example <a href="#recommendation-example-6" id="recommendation-example-6"></a>

A Bagisto B2B project should include a simple product, a configurable product, a product with technical attributes, a company buyer, a customer group with special pricing, an order with payment and shipping context, and a record affected by an extension or custom field. That sample reveals far more than a large number of clean products.

#### Pass Condition <a href="#pass-condition-6" id="pass-condition-6"></a>

Demo Migration passes when the sample produces enough evidence to confirm the migration approach, refine Bagisto configuration, identify Add-on needs, and escalate Custom Service requirements before Full Migration.

### Pitfall 8: Launching Before Integrations, APIs, and Recent Data Are Controlled <a href="#pitfall-8-launching-before-integrations-apis-and-recent-data-are-controlled" id="pitfall-8-launching-before-integrations-apis-and-recent-data-are-controlled"></a>

#### What Goes Wrong <a href="#what-goes-wrong-7" id="what-goes-wrong-7"></a>

The migrated Bagisto store is reviewed, but connected systems, API consumers, headless frontend dependencies, and late source-store changes are not controlled before launch. The business may continue adding products, taking orders, updating customers, changing pricing, or modifying content while integrations and final validation are still incomplete.

Recent Data Migration can help reduce the freshness gap where applicable, but it does not replace preparation, validation, integration testing, or cutover planning. Newly created counted records consume Entity Points when migrated successfully for the first time.

#### Early Warning Signs <a href="#early-warning-signs-7" id="early-warning-signs-7"></a>

* The Source Platform remains active after Full Migration with no final change window.
* ERP, PIM, CRM, marketplace, shipping, payment, tax, accounting, or fulfillment systems are not assigned clear ownership.
* Headless or API-driven frontend behavior is not tested after migrated data is available.
* New products, customers, orders, or Blog Posts appear after the main migration without a clear handling plan.
* The team assumes Recent Data Migration will automatically resolve every late-stage change.

#### Prevention <a href="#prevention-7" id="prevention-7"></a>

Define a launch cutover plan before final validation. Identify which data can keep changing, which changes must pause, what will be handled through Recent Data Migration where applicable, which integrations must be reconnected, and which affected records must be rechecked.

For API-driven, headless, marketplace, B2B, or integration-heavy Bagisto projects, launch readiness should include system behavior, not only migrated record review. Test the data where it is actually used: storefront, admin, frontend, integration, vendor workflow, buyer journey, or operational system.

#### Recommendation Example <a href="#recommendation-example-7" id="recommendation-example-7"></a>

A merchant using Bagisto with a headless frontend and ERP integration should track new orders, new customers, product edits, inventory-sensitive changes, pricing updates, and API-dependent pages after the main migration. Before launch, the team should confirm what was migrated, what was reconnected, what was manually recreated, and what still needs post-launch handling.

#### Pass Condition <a href="#pass-condition-7" id="pass-condition-7"></a>

Launch readiness passes when the team knows which data is final, which systems own launch-critical outcomes, how Recent Data Migration will be used where applicable, which APIs or integrations have been tested, and which affected records must be rechecked before go-live.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Bagisto migration pitfalls are most damaging when the project underestimates the platform’s technical and structural nature. Bagisto can support simple stores, but it is often chosen because the merchant wants Laravel flexibility, custom architecture, B2B or marketplace behavior, headless commerce, extensions, integrations, or developer-governed control. Those strengths become migration risk when they are not documented, sampled, configured, and validated deliberately.

A stronger Bagisto migration plan prevents failure by identifying what belongs to standard data migration, what belongs to Bagisto configuration, what depends on extensions or integrations, and what requires Custom Service review. The goal is not to avoid complexity. The goal is to make complexity visible early enough that it can be handled before launch.

Before moving from Demo Migration to Full Migration or from Full Migration to launch, review the highest-risk Bagisto scenarios against your own store. If the issue depends on custom Laravel behavior, extension-owned data, B2B or marketplace logic, API/headless requirements, Custom Platform source structures, or late-stage source changes, use Live Chat to confirm whether the requirement fits standard service capability, an Add-on, or Custom Service review.

### FAQs <a href="#faqs" id="faqs"></a>

**Why can a Bagisto migration look complete but still have problems?**

A Bagisto migration can look complete when records are present, but still fail if product attributes, channels, B2B or marketplace relationships, extensions, integrations, headless storefronts, or custom logic do not work as expected in the Target Platform.

**What is the most common Bagisto catalog pitfall?**

The most common catalog pitfall is treating products as flat records. Bagisto product quality often depends on attributes, variants, categories, channel visibility, custom fields, and extension-owned behavior, not only product names and SKUs.

**Why are extensions and custom code a major migration risk?**

Extensions and custom code may control behavior that ordinary data migration does not recreate by itself. A field can be migrated as text while losing the workflow, rule, or automation that made it useful in the source store.

**Should Demo Migration include difficult Bagisto records?**

Yes. Demo Migration should include difficult records that reveal real migration risk, such as variant-heavy products, custom attributes, B2B buyers, vendor-owned products, integration-dependent orders, custom fields, headless route examples, and Custom Platform source structures.

**Can Recent Data Migration fix late changes before a Bagisto launch?**

Recent Data Migration can help reduce the freshness gap where applicable, but it does not replace launch planning, integration testing, or validation. New Product, Customer, Order, or Blog records migrated successfully for the first time consume Entity Points.

**When should a Bagisto pitfall move into Custom Service review?**

A pitfall should move into Custom Service review when the expected outcome requires customization, modification, Tailored Add-ons, Custom Add-ons, Custom Platform handling, custom migration logic adjustment, non-standard source interpretation, extension-owned behavior, or integration-dependent handling beyond standard migration capability.
