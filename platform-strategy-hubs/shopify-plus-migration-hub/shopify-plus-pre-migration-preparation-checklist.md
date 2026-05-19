# Shopify Plus Pre-Migration Preparation Checklist



A Shopify Plus migration is safer when preparation defines the future operating model before migration execution begins. For many businesses, the main risk is not whether product, customer, or order records can be transferred. The greater risk is whether the company structure, catalog visibility, account access, store governance, and enterprise workflows have been clarified sufficiently for the migrated store to behave correctly after launch.

Shopify Plus is often selected because the target business needs more than a standard storefront. It may need B2B company accounts, company-location logic, customer-specific catalogs, blended B2B and direct-to-consumer behavior, multiple storefronts, deeper app workflows, or more controlled operational governance. Those advantages become easier to use when the business prepares around the target meaning, not only the source exports.

### What the Shopify Plus Preparation Checklist Is For <a href="#what-the-shopify-plus-preparation-checklist-is-for" id="what-the-shopify-plus-preparation-checklist-is-for"></a>

A Shopify Plus preparation checklist should help the business decide what the Target Platform must support and what must be clarified before migration, so that evidence can be trusted.

The checklist should answer practical questions such as:

* how company, location, buyer, and customer relationships should work in the new environment
* which catalog, pricing, visibility, and access rules are commercially important
* whether the future model should be blended, B2B-focused, or distributed across multiple stores
* which current behaviors depend on apps, custom data, external systems, or source-side workarounds
* which samples should be tested early because they are most likely to reveal structural risk

This keeps preparation tied to business behavior. The goal is not to create a longer checklist. The goal is to prevent important Shopify Plus decisions from being discovered too late.

### Core Shopify Plus Preparation Priorities <a href="#core-shopify-plus-preparation-priorities" id="core-shopify-plus-preparation-priorities"></a>

#### Define company and company-location structure first <a href="#define-company-and-company-location-structure-first" id="define-company-and-company-location-structure-first"></a>

For many Shopify Plus migrations, B2B structure should be prepared before storefront presentation. The business should identify which customers belong to which companies, which company locations carry separate commercial meaning, and whether buyers need different roles, permissions, payment terms, shipping rules, pricing visibility, or approval behavior.

This matters because vague company logic can make the migration appear complete while still producing incorrect buyer access, pricing interpretation, or order context after launch.

#### Clarify catalog access and pricing visibility <a href="#clarify-catalog-access-and-pricing-visibility" id="clarify-catalog-access-and-pricing-visibility"></a>

Catalog planning is one of the most important Shopify Plus preparation steps. The business should identify which products each company or location should see, where pricing should differ, and whether source-side customer groups, price lists, negotiated pricing, or access rules should become Shopify Plus catalog logic.

Preparation is stronger when catalog decisions are described in business terms first. A source-side rule may need to become a clearer target-side access or pricing model rather than a literal copy of the old structure.

#### Decide whether the future model is blended, dedicated, or multi-store <a href="#decide-whether-the-future-model-is-blended-dedicated-or-multi-store" id="decide-whether-the-future-model-is-blended-dedicated-or-multi-store"></a>

A Shopify Plus migration should clarify whether the future operation will use one blended B2B and direct-to-consumer store, a dedicated B2B store, or multiple stores under a broader organization model.

This decision affects customer segmentation, catalog assignment, account access, storefront governance, validation scope, operational ownership, and launch communication. If the model remains unclear, later migration decisions become harder to evaluate because the target structure has no stable reference point.

#### Define customer-account and buyer-access expectations <a href="#define-customer-account-and-buyer-access-expectations" id="define-customer-account-and-buyer-access-expectations"></a>

Customer continuity should be prepared as an identity and access question, not only as a customer-record question. The business should define what B2B buyers should experience when signing in, how company and location context should appear, and what direct-to-consumer customers should experience if the model is blended.

This preparation should also include communication and support expectations. If account access changes during migration, customers and support teams need a clear explanation of what changes, why it changes, and what action may be required after launch.

#### Classify app-owned, metafield-owned, and custom-data-owned behavior <a href="#classify-app-owned-metafield-owned-and-custom-data-owned-behavior" id="classify-app-owned-metafield-owned-and-custom-data-owned-behavior"></a>

Shopify Plus can support more native business structure than standard Shopify, but many enterprise storefronts still depend on apps, custom fields, metafields, integrations, ERP rules, customer-specific workflows, or theme-level behavior.

The preparation checklist should identify which surrounding systems carry business meaning and whether that meaning must be migrated, rebuilt, reconnected, simplified, or handled through Custom Service. This is especially important when app-owned or custom-data-owned logic affects pricing, visibility, product presentation, fulfillment, reporting, B2B access, or customer operations.

#### Identify high-risk product, catalog, and customer combinations <a href="#identify-high-risk-product-catalog-and-customer-combinations" id="identify-high-risk-product-catalog-and-customer-combinations"></a>

Not every record deserves the same level of early review. A stronger Shopify Plus preparation checklist identifies the combinations most likely to expose target ambiguity.

Useful samples often include:

* companies with multiple locations
* locations with different catalog visibility or pricing rules
* products that behave differently for B2B and direct-to-consumer customers
* customer accounts with complex access expectations
* catalog assignments tied to negotiated or restricted product availability
* storefront paths that represent high-value traffic or commercial priority

These samples make Demo Migration more useful because they test whether Shopify Plus is representing the intended business behavior, not only whether records appear.

#### Define store governance and operational ownership <a href="#define-store-governance-and-operational-ownership" id="define-store-governance-and-operational-ownership"></a>

If the business plans to use multiple stores, brands, regions, markets, or B2B/DTC contexts, governance should be clarified before migration execution.

The business should decide which teams own which stores or selling contexts, which rules should remain centralized, which decisions can remain independent, and which operational workflows must stay consistent after launch. Shopify Plus can support broader operating models, but the migration still needs clear ownership rules to avoid confusion after launch.

#### Prepare URL, SEO, and priority-path decisions early <a href="#prepare-url-seo-and-priority-path-decisions-early" id="prepare-url-seo-and-priority-path-decisions-early"></a>

Shopify Plus preparation should include high-value URL and traffic-continuity planning, especially when the Source Platform has a different URL structure, localized paths, custom landing pages, or separate B2B and consumer storefronts.

The business should identify priority products, collections, category-like landing pages, content pages, and storefront paths that need careful redirect or preservation planning. This topic should stay coordinated with the SEO and Traffic Continuity section, but Shopify Plus preparation should flag platform-specific traffic risks early enough for validation.

#### Decide what can be clarified and what must be preserved exactly <a href="#decide-what-can-be-clarified-and-what-must-be-preserved-exactly" id="decide-what-can-be-clarified-and-what-must-be-preserved-exactly"></a>

A Shopify Plus migration can be an opportunity to make company, catalog, pricing, and account behavior more explicit. But not every source-side behavior can be simplified without business impact.

The preparation checklist should separate:

* behaviors that can be clarified or standardized in the Target Platform
* behaviors that must be preserved exactly because they affect customers, pricing, access, orders, or reporting
* behaviors that require Custom Service because they involve customization, modification, app-owned logic, Custom Platform source logic, or custom migration logic adjustment

This prevents the business from treating every difference as a problem while also preventing important commercial meaning from being lost as “cleanup.”

### Practical Preparation Sequence <a href="#practical-preparation-sequence" id="practical-preparation-sequence"></a>

#### Start with commercial structure <a href="#start-with-commercial-structure" id="start-with-commercial-structure"></a>

Define companies, locations, buyer roles, customer types, and account-access expectations before focusing on cosmetic storefront details.

#### Map catalog and pricing behavior <a href="#map-catalog-and-pricing-behavior" id="map-catalog-and-pricing-behavior"></a>

Clarify product visibility, pricing rules, restricted availability, and location-specific differences before migration samples are selected.

#### Decide store and governance boundaries <a href="#decide-store-and-governance-boundaries" id="decide-store-and-governance-boundaries"></a>

Confirm whether the future model is blended, dedicated, or multi-store, and define who owns each major operational area after launch.

#### Classify app and custom-data dependencies <a href="#classify-app-and-custom-data-dependencies" id="classify-app-and-custom-data-dependencies"></a>

Identify which app, metafield, integration, or custom-data layers must be preserved, rebuilt, simplified, or reviewed through Custom Service.

#### Build a high-risk Demo Migration sample <a href="#build-a-high-risk-demo-migration-sample" id="build-a-high-risk-demo-migration-sample"></a>

Select samples that include the most important company, catalog, account, product, pricing, URL, and workflow scenarios.

#### Define acceptance signals before execution pressure rises <a href="#define-acceptance-signals-before-execution-pressure-rises" id="define-acceptance-signals-before-execution-pressure-rises"></a>

Decide what evidence will show that Shopify Plus is ready to support the business model. This helps later validation focus on business outcomes rather than scattered record checks.

### When Custom Platform Source Data Changes Preparation <a href="#when-custom-platform-source-data-changes-preparation" id="when-custom-platform-source-data-changes-preparation"></a>

When the Source Platform is a Custom Platform, Shopify Plus preparation usually needs earlier structural interpretation. Company logic, pricing logic, buyer access, customer-group rules, or enterprise workflow meaning may exist in source-side tables, custom fields, external systems, or bespoke business rules that do not map neatly into Shopify Plus without analysis.

In these cases, preparation should identify what the source behavior means, how it should be represented in Shopify Plus, and whether the migration requires Custom Service. Custom Platform source migrations should not be treated as routine field transfer when the source logic affects commercial behavior, access control, pricing, reporting, or customer operations.

### Conclusion <a href="#conclusion" id="conclusion"></a>

A Shopify Plus migration is easier to govern when preparation defines the target business model before migration execution begins. The most important preparation work is often not a file export. It is the clarification of companies, locations, catalogs, account access, store governance, app dependencies, priority URLs, and the highest-risk validation samples.

Before moving deeper into execution, use the preparation checklist to identify which Shopify Plus outcomes must be proven early. If company structure, catalog logic, access behavior, or app-owned enterprise rules remain difficult to classify, review those areas through Demo Migration evidence and Live Chat before assuming that the selected migration path is strong enough.

### FAQs <a href="#faqs" id="faqs"></a>

**What should be prepared first before migrating into Shopify Plus?**

Start with company and company-location structure, catalog logic, account-access expectations, store model, and the enterprise behaviors that still depend on apps, metafields, integrations, or custom data.

**Why are catalogs such an important Shopify Plus preparation topic?**

Catalogs can affect which products customers can access and how pricing should be represented for different company or location contexts. If catalog logic is vague, the target store may look complete while still behaving incorrectly for important buyers.

**Should Shopify Plus preparation focus mainly on products?**

No. Product structure matters, but Shopify Plus preparation is often more sensitive around companies, locations, buyer access, catalog visibility, B2B pricing behavior, app dependencies, and store governance.

**When does Shopify Plus preparation usually need Custom Service?**

Custom Service is usually relevant when the migration involves customization, modification, Custom Platform source logic, app-owned business behavior, custom fields, external system dependencies, or custom migration logic adjustments that cannot be handled as a straightforward standard capability.
