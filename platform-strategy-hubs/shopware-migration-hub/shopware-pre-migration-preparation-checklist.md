# Shopware Pre-Migration Preparation Checklist

A Shopware migration is easiest to control when preparation separates ordinary record transfer from target-side operating decisions. Products, Customers, Orders, Categories, Coupons, Reviews, CMS content, and related records may be part of the expected scope, but Shopware also asks the merchant to define how those records should operate through sales channels, products and variants, properties, rules, Shopping Experiences, extensions, custom fields, translations, and integrations.

Preparation should therefore produce usable evidence, not only a general checklist. The goal is to make the future Shopware store understandable before migration begins: which storefront contexts matter, which catalog samples prove the data model, which rules must be recreated or validated, which content and URLs carry SEO value, and which custom or extension-managed records need Add-ons or Custom Service review.

### Start With the Target Operating Model <a href="#start-with-the-target-operating-model" id="start-with-the-target-operating-model"></a>

Before preparing exports or access credentials, confirm the intended Shopware operating model. Shopware can support simple storefronts, multi-context sales-channel structures, content-commerce experiences, extension-heavy implementations, and integration-led operations. The migration scope changes depending on which model the target store will actually use.

| Preparation decision                | What to collect                                                                                                        | Why it matters                                                                                                     |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Sales-channel plan                  | Domains, languages, currencies, markets, storefronts, and customer-facing contexts.                                    | Imported records need to appear in the right target context, not only exist in the administration area.            |
| Catalog model                       | Representative products, variants, properties, categories, manufacturers, media, and visibility rules.                 | Shopware product meaning depends on surrounding catalog structure.                                                 |
| Commercial behavior                 | Promotions, pricing rules, tax expectations, shipping/payment conditions, customer-group logic, and manual exceptions. | Commercial logic may be configuration, Add-ons scope, or Custom Service scope rather than simple record migration. |
| Content and SEO priorities          | Priority category pages, landing pages, CMS pages, Blog Posts if relevant, media, URLs, and redirects.                 | Storefront readiness requires preserving discoverability and content purpose.                                      |
| Extension and integration ownership | Plugins, apps, external IDs, ERP/PIM/CRM/search/fulfillment references, and custom fields.                             | Unsupported extension data or external-system dependencies should be identified before scope is finalized.         |

This first step prevents the migration from being scoped around source exports alone. Shopware preparation should describe the store the merchant wants to operate after launch.

### Prepare Sales-Channel and Storefront Context <a href="#prepare-sales-channel-and-storefront-context" id="prepare-sales-channel-and-storefront-context"></a>

Shopware sales-channel planning should happen before judging whether imported data is complete. If the source store had multiple storefronts, domains, market views, language folders, store views, marketplace feeds, wholesale paths, or campaign-specific landing pages, those structures should be translated into a Shopware operating plan.

Collect the source evidence that explains how customers currently reach and experience the store. This includes storefront URLs, category paths, navigation logic, language or currency behavior, customer-facing pricing differences, and any channel-specific content or product availability. The merchant should also document which of those patterns should continue, which should be simplified, and which should be redesigned in Shopware.

| Sales-channel evidence            | Preparation question                                                               | Migration use                                                                    |
| --------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Domains and storefront URLs       | Which URLs represent different customer-facing contexts?                           | Helps confirm routing, redirects, and storefront validation priorities.          |
| Languages and currencies          | Which contexts require localized content, prices, or customer-facing labels?       | Helps avoid importing records without usable localization.                       |
| Product availability by context   | Which products should appear or stay hidden in each channel?                       | Supports product visibility and category validation.                             |
| Customer-facing content paths     | Which landing pages, category pages, and content areas matter for buying journeys? | Supports CMS and SEO continuity planning.                                        |
| Channel-specific commercial rules | Which payment, shipping, pricing, or promotion behavior depends on context?        | Helps decide whether configuration, Add-ons, or Custom Service review is needed. |

If these decisions are missing, a Demo Migration may still import records, but the review team may not know whether the target store is actually operating as intended.

### Build a Catalog Evidence Set <a href="#build-a-catalog-evidence-set" id="build-a-catalog-evidence-set"></a>

A strong Shopware preparation package includes sample records that represent the catalog’s real complexity. Do not rely only on the simplest products. The best samples expose variant structure, properties, filters, media, categories, SEO fields, pricing behavior, inventory expectations, and integration references.

The catalog evidence set should include high-revenue products, high-traffic category paths, variant-heavy products, products with many properties, products with custom fields, products tied to external systems, products that depend on special pricing or visibility, and products with important media or content relationships.

| Sample type                | Why it belongs in preparation                              | What to check after Demo Migration                                                 |
| -------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Simple product             | Establishes baseline product migration.                    | Name, SKU, price, image, status, tax, category, and visibility.                    |
| Variant-heavy product      | Tests whether buying choices remain clear and purchasable. | Parent-child structure, options, inherited values, media, stock, and SKU behavior. |
| Property-heavy product     | Tests filtering and product discovery.                     | Properties, filters, search relevance, and category listing behavior.              |
| Content-rich category      | Tests whether category meaning goes beyond hierarchy.      | Landing copy, media, CMS block relationship, SEO fields, and product grouping.     |
| Integration-linked product | Tests operational continuity.                              | External IDs, PIM/ERP references, custom fields, and staff-facing identifiers.     |

This evidence set should be used during preparation, Demo Migration, and final validation. It gives reviewers a consistent way to check whether Shopware is preserving business meaning, not just importing counts.

### Clarify Properties, Variants, and Custom Fields <a href="#clarify-properties-variants-and-custom-fields" id="clarify-properties-variants-and-custom-fields"></a>

Shopware preparation should separate source values by function. A source attribute may be a buying option, a filterable property, a staff-only identifier, a marketing label, an ERP reference, or a value used by custom logic. Treating all of these as the same kind of field creates avoidable mapping problems.

Prepare a field inventory that explains what each important value does in the source store. Identify whether customers see it, customers select it, staff use it, external systems reference it, or rules depend on it. This helps determine whether the value fits supported mapping, needs Add-ons, or requires Custom Service review.

| Source value function               | Shopware preparation decision                                     | Service implication                                                                    |
| ----------------------------------- | ----------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Customer selects it before purchase | Confirm whether it belongs to variant structure.                  | Usually needs careful mapping and sample validation.                                   |
| Customer filters or compares by it  | Confirm whether it belongs to properties or filterable structure. | May require mapping decisions or Add-ons if supported behavior needs adjustment.       |
| Staff uses it internally            | Decide whether it belongs in custom fields or operational notes.  | May require mapping review if the field is business-critical.                          |
| External system references it       | Preserve identifier meaning and system ownership.                 | Often needs Custom Service review when standard scope does not cover the relationship. |
| Custom code or plugin uses it       | Identify storage, owner, and target behavior.                     | Unsupported plugin or bespoke behavior belongs in Custom Service review.               |

This step is especially important when the source store has years of accumulated attributes, hidden fields, plugin tables, manual workarounds, or external-system identifiers.

### Document Rule-Driven Commercial Behavior <a href="#document-rule-driven-commercial-behavior" id="document-rule-driven-commercial-behavior"></a>

Shopware stores can depend on condition-based behavior for pricing, promotions, shipping, payment, availability, customer treatment, and workflow triggers. Some of this behavior may be recreated through target-side configuration, while some may depend on extensions or custom implementation.

Preparation should document the behavior in business terms before deciding how it will be handled. The merchant does not need to provide a technical implementation specification at the start, but the migration team must understand what customers and staff expect to happen.

| Commercial behavior             | Evidence to prepare                                                                           | Scope risk if missing                                                        |
| ------------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Promotions and coupons          | Active rules, coupon formats, discount conditions, customer limits, and date ranges.          | Discounts may import as records but fail to behave as expected.              |
| Pricing exceptions              | Customer group pricing, channel pricing, currency behavior, price lists, or manual overrides. | Product prices may appear correct in one context and fail in another.        |
| Shipping and payment conditions | Carrier rules, payment restrictions, region logic, order thresholds, and exceptions.          | Checkout may validate differently from the source store.                     |
| Customer segmentation           | Groups, tags, B2B-like treatment, wholesale access, or account-based conditions.              | Customers may lose the commercial behavior tied to their account context.    |
| Workflow behavior               | Notifications, fulfillment triggers, automation, or post-order handling.                      | Staff may receive migrated records without the expected operational process. |

The preparation goal is not to recreate every rule inside the migration file. It is to know which rules matter, where they are owned, and which ones must be configured or custom-handled outside ordinary record transfer.

### Prepare Content, SEO, and URL Evidence <a href="#prepare-content-seo-and-url-evidence" id="prepare-content-seo-and-url-evidence"></a>

Shopware preparation should include content and SEO evidence whenever categories, CMS pages, Shopping Experiences, landing pages, media, or URLs carry acquisition or conversion value. A clean product import is not enough if high-value pages disappear, resolve incorrectly, lose content context, or no longer support the intended buying path.

Prepare a priority URL list before migration begins. Include top product URLs, category URLs, landing pages, CMS pages, campaign pages, blog or editorial pages if relevant, and any pages with meaningful search traffic, backlinks, ads, or internal navigation value. Also identify pages that can be retired or consolidated, so redirect planning does not preserve outdated clutter.

| SEO/content item                     | Preparation use                                       | Validation outcome                                                   |
| ------------------------------------ | ----------------------------------------------------- | -------------------------------------------------------------------- |
| Priority product URLs                | Preserve product discoverability and redirect intent. | Important products resolve to correct target pages.                  |
| Priority category URLs               | Preserve browsing and organic landing-page value.     | Category paths lead to relevant content and product groups.          |
| CMS and Shopping Experiences content | Preserve content-commerce journeys.                   | Landing pages and content blocks support the intended customer path. |
| Media assets                         | Preserve product trust and content quality.           | Images and files display correctly in important contexts.            |
| Retired or merged pages              | Avoid unnecessary redirect clutter.                   | Deprecated paths are intentionally redirected or left out.           |

This preparation helps Article 7 validation later. Reviewers can test real business-critical pages instead of scanning random imported content.

### Identify Extensions, Apps, Plugins, and Integrations <a href="#identify-extensions-apps-plugins-and-integrations" id="identify-extensions-apps-plugins-and-integrations"></a>

Shopware preparation should classify extension and integration dependencies before service path decisions are made. Extensions, apps, plugins, custom fields, storefront modifications, ERP/PIM/CRM/search connectors, marketplace feeds, and fulfillment systems may affect what data is available, how it should be interpreted, and whether standard migration is enough.

The key question is ownership. Some data belongs to the commerce platform. Some belongs to an extension. Some belongs to an external system and only appears in the store as a reference. Some is produced by custom logic. These differences affect preparation, service choice, and validation.

| Dependency type                      | Preparation evidence                                                | Likely handling                                                      |
| ------------------------------------ | ------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Standard supported commerce records  | Sample exports and target mapping expectations.                     | Standard Service may be realistic when structure is ordinary.        |
| Supported but adjusted mapping needs | Filtering, mapping, or configuration requirements.                  | Add-ons may help if the request stays within supported behavior.     |
| Unsupported extension or plugin data | Storage location, business purpose, and target expectation.         | Custom Service review is needed.                                     |
| External-system identifiers          | ERP, PIM, CRM, search, marketplace, fulfillment, or accounting IDs. | Preserve only when scope and target use are defined.                 |
| Bespoke storefront or workflow logic | Description of behavior, source owner, and target expectation.      | Custom Service or target-side implementation planning may be needed. |

This classification protects both the merchant and Next-Cart from under-scoping. It also keeps Add-ons and Custom Service separate: Add-ons adjust supported migration behavior, while Custom Service handles unsupported or bespoke requirements.

### Prepare Access, Exports, and Review Ownership <a href="#prepare-access-exports-and-review-ownership" id="prepare-access-exports-and-review-ownership"></a>

Preparation should also cover practical migration readiness. Access credentials, API access, export files, admin permissions, sample records, target-store setup, and reviewer assignments should be ready before Demo Migration. Missing access or unclear ownership can slow migration even when the data model is understood.

| Readiness area  | What to prepare                                                                                              | Why it matters                                                         |
| --------------- | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| Source access   | Admin access, exports, API details if applicable, and source-system limitations.                             | Confirms that required records can be reached.                         |
| Target access   | Shopware admin access, configured sales channels where needed, languages, currencies, and baseline settings. | Lets migrated data be reviewed in meaningful target context.           |
| Sample list     | Priority products, customers, orders, categories, content pages, rules, and custom fields.                   | Creates a repeatable review set for Demo Migration and full migration. |
| Decision owners | Catalog, SEO, operations, integrations, and finance stakeholders.                                            | Ensures each data area is reviewed by the right person.                |
| Launch window   | Timing for Demo Migration, corrections, final migration, later migration actions, and validation.            | Reduces last-minute scope changes and launch pressure.                 |

A Shopware migration should not depend on one reviewer checking everything. Catalog, SEO, content, commercial logic, integrations, and order operations often need different review owners.

### Use Demo Migration as an Evidence Test <a href="#use-demo-migration-as-an-evidence-test" id="use-demo-migration-as-an-evidence-test"></a>

Demo Migration should be treated as a controlled evidence test. It should not be judged only by record counts or a quick visual scan. For Shopware, Demo Migration is most useful when it tests the sample set prepared earlier: sales-channel context, variant-heavy products, property-heavy products, content-rich categories, customer and order samples, custom fields, and integration identifiers.

| Demo Migration question                 | What a useful answer looks like                                                                             |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Do the right records arrive?            | Products, customers, orders, categories, and content samples appear with expected core fields.              |
| Do records operate in Shopware context? | Products are visible where expected, variants and properties make sense, and categories support navigation. |
| Does business meaning survive?          | Pricing context, content purpose, customer treatment, and operational identifiers remain understandable.    |
| Are unsupported needs visible?          | Plugin data, custom fields, external references, or custom logic are clearly classified.                    |
| Is the service path still correct?      | Standard Service, Managed Service, Add-ons, or Custom Service decisions are confirmed or adjusted.          |

When Demo Migration reveals missing structure, the right response is not always to add more data. Sometimes the target store needs configuration, mapping adjustment, Custom Service review, or clearer launch sequencing.

### Conclusion <a href="#conclusion" id="conclusion"></a>

Shopware preparation should produce a practical evidence package for the future target store. The strongest preparation work defines sales-channel context, catalog structure, rules, content and SEO priorities, extensions, custom fields, integrations, access, samples, and review ownership before migration begins.

That discipline makes the migration easier to scope and easier to validate. It also reduces the risk of treating Shopware as a generic data destination when its value depends on structured commerce behavior, storefront context, extensibility, and operational clarity.

### Common Questions <a href="#common-questions" id="common-questions"></a>

**What should be prepared first for a Shopware migration?**

Start with the target operating model: sales channels, languages, domains, catalog structure, content priorities, commercial rules, integrations, and review ownership. Export files matter, but they should be interpreted against the intended Shopware setup.

**Should every source attribute become a Shopware property?**

No. Source values should be classified by function. Some belong to variants, some to properties, some to custom fields, some to content, and some to integrations or custom logic.

**When should extension data be prepared for Custom Service review?**

Prepare it for Custom Service review when the data is unsupported, plugin-owned, stored outside ordinary commerce records, tied to custom fields, or required for bespoke storefront, workflow, or integration behavior.

**How should Demo Migration be used for Shopware?**

Use Demo Migration to test representative samples, not just total counts. Review variant products, property-heavy products, important categories, content pages, customers, orders, custom fields, and integration-linked records.

**Why is reviewer ownership important in Shopware preparation?**

Shopware preparation touches catalog, SEO, content, commercial rules, integrations, and operations. Different stakeholders may need to verify different outcomes before the migration can be considered usable.
